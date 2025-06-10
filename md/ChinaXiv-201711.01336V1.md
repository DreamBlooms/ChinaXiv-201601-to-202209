# 太阳风对火星探测通信信道的影响及抗闪烁策略研究

薛喜平},²，李春来'，孔德庆}，张洪波(1.中国科学院国家天文台，北京100012；2.中国科学院大学，北京100049)

摘要：太阳上合期间，太阳风严重影响深空通信链路，严重时可能导致通信链路中断。论述了信道与太阳之间的距离是决定太阳风对深空通信信道影响的主要因素，并分析了太阳风对信道影响的具体特征。最后，以中国的火星探测任务为背景，从理论上分析可行的抵抗太阳风影响的通信信道改善策略。

关键词：太阳风；深空探测；强度闪烁；相位闪烁；频率扩展中图分类号：0451 文献标识码：A 文章编号：1672-7673(2017)01-0110-07

2003 年中国探月工程立项，标志着中国深空探测计划大幕的拉开。与此同时，比月球更远的火星以及其他小行星探测计划也逐步启动。深空探测通信具有传输距离远、信噪比低、传输时延大等特点，而且容易受太阳风的影响。太阳风的大量不规则带电粒子导致无线电信号出现闪烁现象，尤其在太阳上合期间，当太阳-地球-探测器夹角(SEP)较小，或当处于太阳活动周期时，导致传输误码率增高，接收性能下降，有可能出现通信间歇式中断甚至完全中断的现象[1]。当地球、太阳、深空探测器大致处于同一直线上，且太阳位于地球和探测器之间时，就是太阳上合现象。图1为太阳风对深空通信的影响示意图。在伽利略探测任务中，上合的一个月之前便出现了明显的下行链路衰减;在上合5天前（SEP角为 $2 . 9 ^ { ^ { \circ } }$ )已经无法跟踪遥测信号；直到7天后（SEP角为 $5 . 8 ^ { \circ }$ )才重新获得遥测信号①。Cassini号 2000 年观测的太阳风对信噪比的影响记录( $S E P$ 角为 $0 . 6 ^ { \circ }$ ，Ka 频段）,观测记录中接收信号的信噪比波动最大已经超过 $1 0 \mathrm { d } \mathbf { B } ^ { [ 2 ] }$ 。

目前，中国自主火星探测计划已经启动，在未来的火星探测任务中，太阳风将是影响火星探测通信信道的重要因素，是卫星通信链路设计时必须考虑的重要影响因素。因此，研究太阳风对深空探测通信信道的影响因素及其相应的抗闪烁策略十分必要，对火星探测计划的制定以及实施具有较大的理论和应用价值。本文概述了太阳风对通信信道的影响因素以及范围，并结合我国未来的火星探测任务总结了几种理论上可行的抗太阳风闪烁影响的技术策略，供研究人员参考。

![](images/403791913c34d3341b16ee92455d6ee019000d8cb8f2e71a733348c45ef662f6.jpg)  
图1太阳风对深空通信的影响示意图 Fig.1Schematic diagram of the impact of solar wind on deep space communication

# 1太阳闪烁对深空通信链路的影响

无线电波穿过不均匀分布介质时，由介质不规则性引起的电波振幅与相位快速随机起伏现象，叫做闪烁。太阳风中带电粒子密度不均匀，并且在太阳磁层内部伴随着明显的波动。相关研究表明[3]，太阳风等离子体密度与径向距离的平方成反比，也就是说，径向距离越大，等离子体密度越低。当探测器距太阳表面超过4个太阳半径时，太阳风等离子体密度基本呈平滑分布，对无线电信号传输的影响主要包括群延迟、色散、法拉第旋转和吸收等。当距离小于4个太阳半径时，太阳风带电粒子密度变化极不规则，当信号穿过这一区域时，信号的幅度、相位和频率都不可避免地受太阳风的强烈影响②，该区域内除了受太阳风平滑分布时的影响外，还出现强度闪烁、频谱扩展和相位闪烁等现象。

# 1. 1 强度闪烁

当无线电信号靠近太阳风区域时，信号被菲涅耳区的湍流介质散射。当无线电信号穿过这个区域时，由于电波射线路径改变以及波前相位改变导致信号幅度围绕其平均值快速变化。把无线电信号的这种幅度起伏叫做幅度闪烁。强度闪烁反映了太阳风中小尺度(小于菲涅耳半径)带电粒子密度的起伏。图2为Cassini号探测器 2000年5月14日观测时，X频段和Ka频段信号的强度闪烁观测结果（ $\cdot S E P = 1 . \ 1 ^ { \circ }$ 、 $1 . 8 ^ { \circ }$ 和 $3 . 1 ^ { \circ }$ )[2]。从Cassini号探测器观测的闪烁结果可知，强度闪烁与 SEP角和频率有关，SEP角越小闪烁越强，频率越低闪烁越强。

![](images/28f87fa694ba7522d6d637d076f57286f587b42aa0d9e54a8f2f3cb0a81d8049.jpg)  
图2Cassini号2000年5月14日观测时的强度闪烁( $S E P = 1 . 1 ^ { \circ }$ )[2]。（a）X频段强度闪烁；（b）Ka频段强度闪烁 Fig.2Intensity flicker of signals from the Cassini in the Xand Ka band induced by solar winds at $S E P \ 1 . \ 1 ^ { \circ \ [ 2 ] }$ （20

# 1.2相位闪烁(多普勒频移)

无线电信号穿过太阳风区域时产生的快速相位变化，叫做相位闪烁。相位闪烁导致信号的频率变化，由于飞行器和地面相对运动产生多普勒频移，相位闪烁也可以看作是多普勒噪声，因此，相位闪烁也叫多普勒闪烁。测量相位闪烁的方法就是测量多普勒噪声。图3为Cassini 号探测器 2000 年首次与太阳交汇时X频段与Ka频段的相位闪烁现象[²( $S E P = 0 . 6 ^ { \circ }$ ）。

![](images/069b858c3abc5c07846f3cc833bfe6d9410c18fedb192da19f7750ae05d62538.jpg)  
图3Cassini号2000年首次与太阳交汇时的相位闪烁( $S E P = 0 . 6 ^ { \circ }$ )[2] （a）X频段频率残余；（b）Ka频段频率残余 Fig.3Frequency residuals in the $\mathrm { \Delta X }$ and $\mathrm { \ K a }$ band from Cassini reflection phase scintillations during thefirst solar conjunction of Cassini[2]

# 1.3 频率扩展

频谱扩展指穿过太阳风中不均匀分布的等离子体无线电信号的半功率带宽会增大。电磁波在随机介质中传播时，相位起伏会产生信号频率变化，表现为频谱扩展。频谱扩展同时反映了太阳风中等离子体密度起伏和太阳风速度。如果传输信号频谱扩展过大，就需要很宽的跟踪环路带宽以捕获所有频率信号，但跟踪环路带宽太宽会引入过多的热噪声而导致接收机锁相环失锁。图4为Cassini号 2000年观测到的频率扩展现象( $S E P = 0 . 6 ^ { \circ }$ 和 $S E P = 3 . \ : 1 \ : ^ { \circ }$ )[2]。

# 2抗闪烁技术策略

# 2.1应用更高频段的无线电波

研究表明，太阳风对无线电信号的影响与信号频率有关，无线电信号的频率越高，受太阳风的影响越小。选择高频段的无线电信号作为传输信号，可以增强抵抗太阳闪烁的能力。相同条件下，Ka波段信号的闪烁指数仅为X波段的 $1 5 \%$ ，Ka 波段的频谱扩展也仅为X波段的 $2 0 \%$ 。根据文[4]仿真（见图5），在相同的信道条件下( $R = 4 R _ { 0 }$ ， $R$ ：太阳半径； $R _ { 0 }$ ：信道与太阳中心的距离），Ka波段闪烁指数0.064，X波段闪烁指数0.37，要达到误码率 ${ { 1 0 } ^ { - 5 } }$ ， $\mathrm { \Delta X }$ 波段的信号信噪比有7.8dB的衰减，而Ka 波段信号几乎没有衰减，也就是说 $\mathrm { K a }$ 频段较X频段有 $7 . 8 \ \mathrm { d b }$ 增益。

但是信号频率越高，信号在穿过地球大气层时信号的衰减越大。在火星全球勘测者探测器首次对Ka波段的通信性能实验中，由于大气和放大器噪声的影响，Ka波段相比X波段的优势实际降为6～8$\mathrm { d B } ^ { \mathcal { \hat { 2 } } }$ 。解决大气衰减问题，可以在近地轨道设置一颗中继转发卫星，负责接收深空探测器的Ka 频段信号，并变频到X频段后再向地球发送数据，可以大大降低信号通过大气层的衰减。因此，采用Ka波段进行通信是今后深空通信的发展趋势，不仅可以提高通信性能，还可以降低探测器的重量，节省功率，提高数据速率。

![](images/853489d52b7801b3b0517c1f2140ac601692db010a05bade121315fcce946664.jpg)  
图4Cassini号2000年观测的频率扩展( $S E P { = } 0 . 6 ^ { \circ }$ 和 $S E P = 3 . 1 ^ { \circ }$ )[2] Fig.4Frequency expansion of signals during the first solar conjunction of Cassini observed in $2 0 0 0 ^ { [ 2 ] }$ （204号

# 2.2应用高增益信道编码方式

目前，多数深空通信信道编码方式采用卷积编码，使用二进制相移键控（BinaryPhase ShiftKeying，BPSK)调制，这种编码方式在强闪烁条件下（闪烁指数大于0.3），纠错能力不足。随着闪烁的不断增强，接收的信号强度和相位起伏不断加剧。一方面，相位起伏可能导致接收机锁相环失锁，另一方面，在锁定的情况下，由于信噪比起伏过大，也可能解不出正确数据。因此，在强闪烁条件下，卷积编码方式已经不再适用。深空通信编码采用低密度奇偶校验码（LowDensityParityCheckCode，LDPC）代替卷积码，低密度奇偶校验码具有高可靠性，已经广泛应用于数字通信系统，并逐步扩展到空间通信系统，在给定误码率情况下的信息传输速率非常接近香农

![](images/9702fa6ca4ccf398c49ad2fbe800693fd13d75e5fbc0dfb74aea7cca6237b069.jpg)  
图5 X/Ka频段信号通信链路性能（ $R = 4 R _ { 0 }$ )[4] Fig.5Telecommunication link performance at X/Ka band（R=4Ro）[4]

（Shannon)极限，对于一些中长码的低密度奇偶校验码，其纠错性能甚至已经超过了 Turbo 码[4-5],③弱太阳闪烁信号（闪烁指数 $\mathbf { \nabla } _ { m }$ 小于0.3时）服从莱斯分布（RiceDistribution）衰减统计模型，假设在无闪烁情况下通信信道为高斯信道，在高斯信道中加入瑞利衰减，将闪烁指数 $m$ 通过其与Rician因子的关系，引入到瑞利衰减信道中，利用MATLAB仿真不同编码方式在太阳风影响下的通信链路性能，仿真结果(见图6)表明，在X频段，低密度奇偶校验编码比卷积码获得3.3dB 的编码增益[5]。

在相同频率、相同信道条件下，低密度奇偶校验编码比卷积编码获得更多的编码增益，更加适用

于火星探测任务中对探测信号的编码应用。

2.3应用通信信道衰减预测和自适应控制

解决弱太阳闪烁导致的通信链路衰减问题，可采取提高深空探测器发射功率的办法，但深空探测器发射机功率往往受限，无限制地提高发射机功率将影响深空探测器其它仪器的工作，这对深空探测十分不利[6]。因此，根据通信信道的特性，通过信道预测进行自适应功率控制、码速率和编码方式调整,无论是在陆地无线移动通信领域还是在空间卫星通信领域都得到普遍关注[7],④。在弱闪烁条件下，衰减信道预测的研究主要集中在线性预测算法上，文[8]用自回归模型(Auto-Regression，AR)描述快速衰减信道的动态特性，提出了对于衰减信道较长时间的线性预测算法，较好地预测了弱太阳闪烁条件下探测信号传输的幅度衰减。文 $\textcircled{5}$ 提出了一种基于抽头延迟线滤波器的信道估计方法，计算复杂度低，误码率低。

卫星进行衰减预测与自适应控制其功率、码速率和编码方式等不是唯一的解决途径。地面接收站根据遥测信号进行自适应的衰减补偿。地面站将接收的卫星遥测信号与本地参考信号互相关，得到遥测信号的频率偏差与相位偏差；在正式数据传输时，地面接收系统将相关计算得到的频率偏差和相位偏差补偿到数据传输信号中，使其恢复到正常水平，最后再进行解调处理，地面站数据接收系统自适应补偿原理如图7。

![](images/2f1227daa4a640db5393ebcc8d6770e723dfa81b4d776711ca88ac52155e509d.jpg)  
图6不同编码方式在太阳风影响下的通信链路性能（ $R = 5 R _ { 0 }$ )[5]Fig.6Telecommunication link performancewith different coding ( $\mathrm { \Delta } R = 5 R _ { \mathrm { 0 } }$ )[5]

![](images/9a12e5971f05eba5a2314f4b8b2a3941421f4aa5ab52176e3a5006ca8955bbe0.jpg)  
图7地面站数据接收系统自适应补偿原理 Fig.7Adaptive compensation principles of the data receiving system in ground station

# 2.4应用天线组阵技术

传统的提高地面站通信能力的方法是增大天线口径，但增大天线口径存在一系列技术问题，如重力下垂、风负荷加大、热变形等。因此，美国对大天线的开发已处于停滞状态。利用中小天线组阵技术不仅能够达到等效的大口径天线性能，而且还具有系统可靠性高、天线设备利用率高和建造维护成本低等优点[9]，是今后深空测控通信技术发展的必然方向。国外已经有过成功案例，在旅行者号任务中，当探测器飞跃天王星和海王星时，都是用天线阵技术提高数据的传输速率[10]。在最近的伽利略号任务中，由于主用通讯天线损坏，只能使用增益较低的测控天线回传科学数据，由于回传信号强度很微弱，单天线无法完成数据接收任务，只能使用天线组阵完成。美国深空网位于北美和澳大利亚的5个大口径天线参与这次任务，天线组阵技术使科学数据的接收效率提高了3倍，信噪比提高2\~3$\mathrm { d B } ^ { [ 1 1 - 1 3 ] }$ 。伽利略任务的成功充分说明了天线组阵技术在接收微弱信号方面的优势，值得学习与借鉴。

我国的研究人员也相继开展了天线组阵技术的研究，中国科学院国家天文台利用已有的北京密云$5 0 \mathrm { m }$ 天线和云南昆明 $4 0 \mathrm { ~ m ~ }$ 天线搭建了异地天线组阵试验系统，密云 $5 0 \mathrm { ~ m ~ }$ 和昆明 $4 0 \mathrm { ~ m ~ }$ 天线分别接收在轨的嫦娥三号着陆器下行探测数据，利用检前记录器采集记录中频数据，经相关处理后进行数据合成，试验系统组成如图8。该试验系统针对我国的火星探测需要开展，试验目的是完成天线组阵相关的算法研究与关键技术验证，尤其是对微弱信号的合成技术验证。图9为2015年5月2日两站记录数据的合成效果，合成后的信号信噪比较单天线信号信噪比高出约2dB，合成效率高达 $9 2 . 5 \%$ 。

![](images/078d3816098092fce715b5b3e25c5f665a151a7dbf010990cbc7de1491e82258.jpg)  
图8天线组阵试验系统组成

根据密云站和昆明站组成的天线组阵合成系统合成结果分析，合成信号的信噪比提高了$2 \mathrm { d B }$ 。结合国外的应用经验，证明天线组阵可以完成对微弱信号的接收，可以用于我国自主火星探测任务的数据接收。

# 3结论与展望

分析表明，在太阳上合期间，太阳风严重影响火星探测通信链路，甚至导致通信链路中断。中国火星探测计划已经启动，对太阳风的影响研究以及抗太阳闪烁技术策略十分必要，尤其是在通信系统链路设计时必须考虑太阳风的影响。提高传输信号频率、应用高增益编码方式、地面站自适应补偿和天线组阵技术都能

![](images/9baa06e7ba2284e91c1357aaf6ed21066fbf4d9d761317bc423cbfa7ae788ba9.jpg)  
Fig.8Test system of the antenna array   
图9天线组阵合成效果分析Fig.9Analysis of the antenna array's synthesis ffect

在一定程度上起到抵抗太阳闪烁的作用。研究人员应该在抗闪烁技术策略上进行深入分析与研究，探索更加有效的深空通信方式抵抗太阳闪烁的影响，才能保证顺利完成火星探测的星地通信任务。

# 参考文献：

[1] Morabito D，Hastrup R. Communicating with Mars during periods of solar conjunction [C]// Aerospace Conference Proceedings.2002：1271-1281.   
[2] Morabito D，Hastrup R. Communications with Mars during periods of solar conjunction：initial study results ［R]// The Interplanetary Network Progress Report. 2OO1:1-16.   
[3] 赵娜．太阳闪烁及其对深空通信影响的研究［D].北京：中国科学院研究生院（空间科学 与应用研究中心），2009.   
[4] MacKay D JC，Neal R M. Near Shannon limit performance of low density parity check codes [J].IEE Electronics Letters，1996，32(18）：1645-1646.   
[5] Li Qi，Yin Liuguo,Lu Jianhua. Performance study of a deep space communications system with low-density parity-check coding under solarscintillation[J]. International Journal of Communications，2012，1(6):1-9.   
[6] 刘嘉兴.深空测控通信的特点和主要技术问题［J]．飞行器测控学报，2005，24(6)：1-8. Liu Jiaxing.Features and main technical issues in deep space TT&C and telecommunication systems [J]. Journal of Spacecraft TT&C Technology，2O05，24(6）：1-8.   
[7] Eyceoz T,Duel-Hallen A,Hallen H.Prediction of fast fading Parameters by resolving the interference pater [C]// Proceedings of the 31st ASILOMAR Conference on Signals，Systems，and Computers. 1997: 167-171.   
[8] Ekman T,Kubin G.Nonlinear prediction of mobile radio channels:measurements and MARS model designs [C]// IEEE International Conference on Acoustics，Speech and Signal Processing. 1999.   
[9] Vilnrotter VA，Rodemich ER,Dolinar S J. Real-time combining of residual carrier array signals using ML weight estimates [J]. IEEE Transactions on Communications，1992,40(3）: 604-615.   
[10] Thompson A R，Moran JM，Swenson G W. Book review:interferometry and synthesis in radio astronomy［M].New York：Wiley，1986.   
[11] 刘嘉兴.走向深空—测控通信的发展方向［J].电讯技术，2006(2)：1-8. Liu Jiaxing. Forward to the deep space developing trend of TTC&DC technology [J]. Telecommunication Engineering，2006(2）:1-8.   
[12] Rogstad D H. The SUMPLE algorithm for aligning arrays of receiving radio antennas:coherence achieved with less hardware and lower combining loss ［R]// The Interplanetary Network Progress Report. 2005.   
[13] Cheung K M. Eigen theory for optimal signal combining:a unified approach ［R]// The Telecommunications and Data Acquisition Progress Report. 1996.

# Analysis of the Influence of Solar Wind and Anti Solar Wind Flicker Strategy on the Transmission Channel of Mars Probes

Xue Xiping $^ { 1 , 2 }$ ，Li Chunlai'，Kong Deqing'， Zhang Hongbo' (1.National Astronomical Observatories，Chinese Academyof Sciences，Beijing 10ol2,China,Email:xuexp@bao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China)

Abstract:During Superior Solar Conjunction，solar wind exerts severe effects on deep space communication link，which may lead to serious disruption.Distance between a channel and the Sun is the main factor to determine how serious the impact is on deep space communication. In this article，specific features of the impact caused by solar wind are analyzed.Atlast,basedon China's Mars exploration mission，several feasible communication strategies verified by theoretical analysis are proposed to resist the impact of solar wind.

Key words: Solar wind；Deep space exploration；Intensity flicker；Phase flicker；Frequency expansion