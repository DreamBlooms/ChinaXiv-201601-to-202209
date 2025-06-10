# 2006年12月13日太阳射电暴对GPS 观测的影响

黄文耿 阿尔察 刘四清 沈华 陈艳红(中国科学院国家空间科学中心北京 100190)

摘要日地空间环境不仅影响航天器运行和安全，也是导航、定位和通信等无线电应用系统主要的误差源．其中来自太阳L波段的射电暴被认为是全球导航卫星系统（GNSS）稳定和性能的潜在威胁因素，当L波段射电爆发达到一定阈值时，将给用户带来不同程度的射电噪声干扰，严重时会引起接收机失锁和定位服务中断.本文对 2006年 12月13日太阳射电暴对GPS 造成的影响进行了研究，利用太阳射电观测数据、L 波段闪烁观测数据和向阳面不同区域的GPS 观测网数据，分析GPS 观测对射电暴的响应．结果表明，此次事件对GPS 观测产生了明显的影响，射电暴期间GPS 发生幅度闪烁事件和明显失锁现象，多个台站上空的多颗 GPS 卫星信号完全中断长达 $6 \mathrm { { m i n } }$ 左右，且多个台站上空锁定的卫星数目小于4颗，使得GPS 定位完全失效.相对而言，射电暴期间日下点附近的GPS台站受到的影响比远离日下点的大.

关键词GPS,太阳射电暴,无线电波闪烁,导航,失锁 中图分类号P353

# Effect of the 13 December 2006 Solar Radio Burst on GPS Observations

HUANG Wengeng A Ercha LIU Siqing

SHEN Hua CHEN Yanhong (National Space Science Center,Chinese Academy of Sciences,Beijing 100190)

Abstract Solar activity and Earth's space environment can efect the operation and safety of spacecraft,and they are also the main error source of navigation, positioning,and communication based on radio waves applications system. In this field, the L-band solar radio burst is regarded as a potential threat to Global Navigation Satellite System (GNSS) stability and performance. When the solar radio burst exceeds a threshold value,the radio noise from solar emission will increase dramatically， which can give rise to GNSS receiver tracking loss and positioning failure located in the sunlit hemisphere of the Earth. In this paper,by using the solar radio flux data,L-band scintillation data,and GPS receiver observation network data located in different regions, effect of the 13 December 2006 solar radio burst on GPS observations are investigated in detail. Results show that the disruption caused by this radio burst event is obvious,and the amplitude scintillation events occur and GPS signal losses of lock are detected. Furthermore,the GPS satelite signal locked at several GPS station is interrupted and the observed GPS satelite number is less than 4 during this solar radio burst. The event resulted in GPS service failure for about six minutes. By comparison, those stations located nearby sub-solar point are more serious than that of far away from it. Key wordsGPS,Solar radio burst, Scintillation, Navigation,Loss of lock

# 0引言

GPS卫星的发射功率较低，当导航电波到达地面时，地面设备接收到的信号功率只有 $- 1 3 0 \mathrm { d B m }$ 左右，其强度非常微弱，因此地面上的接收信号很容易受到周围环境的干扰[1]．排除人为干扰,自然界中G-PS 信号的主要干扰源有两种.一种是当GPS信号穿过电离层时，电离层中的小尺度不规则体引起无线电波的散射，造成导航信号强度和相位快速无规则起伏和波动，形成电离层闪烁[2]；另一种是来自太阳射电的直接干扰，太阳射电暴期间，太阳射电辐射会突然大幅度增加,如果爆发的频段覆盖了导航信号的频率，就会对GPS 造成不同程度的射电干扰[3]．无论是电离层闪烁还是太阳射电干扰，都会造成信噪比下降，信号强度降低,从而导致定位精度下降,严重时会造成失锁和GPS服务完全中断，极端空间天气是空间应用系统潜在的主要威胁之一[4-5].

20 世纪90 年代,Klobuchar[3]提出了太阳L波段射电暴对GPS的观测噪声干扰问题，由于当时还处在GPS应用的初级阶段，而且L波段射电爆发次数不多，爆发强度相对较弱[6-7],太阳射电干扰问题并没有引起太多重视.直到2005年才陆续出现了太阳射电暴对GPS 影响的报道 $[ 8 - 9 ]$ .Cerruti[10] 观测到太阳射电爆发对向阳面GPS 观测台站和 WASS系统的严重影响，Carrano[11]分析了太阳射电暴期间GPS长达数分钟的失锁和高达 $2 0 \mathrm { \sim } 6 0 \mathrm { m }$ 的定位误差,Sreeja[12]研究了2011年9月24日射电暴对单点精密定位(PPP)服务的影响以及对GNSS接收机性能的影响，Yue等[13]研究了太阳射电暴对GNSS掩星信号的影响.Demyanov 理论研究表明[14],对于一般商用GPS接收机而言，当L波段太阳射电辐射达到一定阈值时，其对接收机的影响会非常明显，

本文针对2006年12月13日太阳射电暴对GPS造成的影响，利用观测首次给出亚洲-大洋洲地区太阳射电爆发对GPS信号和性能影响的直接证据，重点评估了事件期间射电爆发对GPS应用系统的影响．根据此次射电暴的多波段观测数据，利用L波段闪烁监测仪数据给出相关性分析，同时利用IGS观测网提供的GPS观测数据，将处于向阳面两个不同区域的GPS台网对此次射电暴的响应进行对比研究,进而结合中国北斗卫星导航的应用和推广[15]提出参考建议.

# 1事件描述与观测

在2006年12月13日02:14UT，位于日面上的 0930 活动区 $( 6 ^ { \circ } \mathrm { S } , \ 2 4 ^ { \circ } \mathrm { W } )$ 爆发了一个X3.4级别的X射线太阳耀斑，伴随此耀斑该活动区爆发Ⅲ型射电暴，此次射电爆发覆盖了多个频段[16]．图1为GOES卫星观测到的 $0 . 1 { \sim } 0 . 8 \mathrm { n m } \mathrm { ~ X ~ }$ 射线流量数据,耀斑发生于 $0 2 { : } 1 4 \mathrm { U T - } 0 2 { : } 5 7 \mathrm { U T } .$ 。此X射线耀斑持续 $3 3 \mathrm { m i n }$ ，于 $0 2 { : } 4 0 \mathrm { U T }$ 达到峰值.

![](images/7319e61491e928e67317fbaa5c3ce50c54611e9fa885056971e0b2ab4dd0e09c.jpg)  
图1GOES 卫星观测的太阳 X 射线流量 Fig.1Solar X-ray flux from GOES observations

太阳射电爆发过程非常复杂[17]，图2 所示为澳大利亚利尔蒙思（Learmonth）射电频谱仪多个频段（245，410，610，1415，2695，4995，8800,$\mathrm { 1 5 4 0 0 M H z } )$ 的太阳射电观测数据．从图2可以看出，在 $\mathrm { 0 2 { : 0 0 U T } { - 0 4 : 0 0 U T } }$ 之间太阳射电在多个频段均有大幅度的突然增加，其中对于GPS 工作的L 波段（目前常用的GPS工作频率有两个，分别为 $1 . 5 7 5 4 2 \mathrm { M H z }$ 和 $1 . 2 2 7 6 0 \mathrm { M H z } \rangle$ ，主要集中在 $0 2 { : } 3 0 \mathrm { U T }$ 和 $0 3 { : } 3 0 \mathrm { U T }$ 左右,其瞬时射电流量最高达到 $1 0 ^ { 5 }$ sfu以上（见图2中的 $1 4 1 5 \mathrm { M H z }$ 子图).一般在太阳宁静条件下，L波段射电流量值在 $5 0 { \sim } 1 5 0$ sfu左右，因此此次爆发事件射电辐射比平常增加了 $1 0 ^ { 3 }$ 倍以上，其最大流量也远远大于Klobuchar 和Demyanov 等给出的太阳射电干扰GPS 性能阈值[3,14].

大洋洲和亚洲扇区正好处于此次爆发事件的向阳面，图3给出射电峰值时的地球晨昏线图，日下点位于澳大利亚境内，可以预计澳大利亚附近的GPS台站受到的影响会最大.

# 2 GPS 影响

为了考察L波段射电暴对向阳面不同地区G-PS的影响，本文选择两个区域GPS接收台站的数据，一个区域是离日下点较近的澳大利亚附近的19个IGS台站，另一个区域为远离日下点的中国境内的9个IGS台站,表1给出了各个台站的编号、地理坐标以及GPS接收机型号等信息.

太阳射电暴对无线电波的影响主要表现为噪声增加及信号幅度波动.图4(a）所示为位于澳大利亚境内的 NIUE 台站（ $1 9 . 1 ^ { \circ } \mathrm { S }$ 。 $1 6 9 . 9 ^ { \circ } \mathrm { E }$ ）电离层幅度闪烁 $( S _ { 4 } )$ 的分布情况．NIUE台站闪烁观测设备型号为加拿大NOVATEL 公司生产的GSV4004B，采集的GPS卫星L1点数据能给出幅度闪烁指数，但是缺乏相位闪烁指数．图4(b）(c）给出的是位于中国地区的两个台站L波段闪烁监测仪一分钟相位闪烁 $( \sigma _ { 6 0 } )$ 和幅度闪烁指数随时间的变化.这两个台站的设备采用NOVATEL公司生产的OEM4板卡并经

![](images/4b7d3a3d0304bf3c6bd1e81b3bfbad2c19697bdf28132aeb2b3284f680e2ed9c.jpg)  
图22006年12月13日多频段太阳射电流量的地基观测

Fig.2Multi-band observation of solar radio fux from Learmonth solar observatory on 13 December 2006过改造，幅度闪烁指数与NIUE台站类似，由于增加了高精度的外接频标，因此能得到相位闪烁指数为消除多路径效应的影响，忽略了射线仰角小于 $2 5 ^ { \circ }$ 的数据．从图4可以明显看出，射电暴期间 NIUE台站上空发生了幅度闪烁事件，NIUE 台站的幅度闪烁指数达到了强闪烁事件！ $\mathit { ^ { \prime } S _ { 4 } } > 0 . 6 )$ 级别，观测到闪烁的卫星为PRN1，PRN14，PRN16，PRN25,

![](images/06aebb67c7bf862eca65dd7601f49ac4b456d5f07359f8529ab26cada62857e4.jpg)  
图3射电暴期间太阳星下点(日下点)和部分台站的位置 (阴影分界线表示晨昏线) Fig.3Schematic diagram of sub-solar point and GPS stations position during solar burst (shadow boundaryrepresents twilight arch)

![](images/3da0b98ca48ba16cb3b4ffa664cac2f9bcc9281bbf0104b7bd3c7ba87eb5d65f.jpg)  
图4射电暴期间L 波段幅度闪烁 $S _ { 4 }$ 和相位闪烁 $\sigma _ { \varphi }$ 指数 Fig.4L-band scintillation index during solar radio burst

表1所选取的IGS台站编号、位置与接收机型号信息Table 1Site information for 28 selected IGS stations  

<html><body><table><tr><td>site ID</td><td>latitude/(°)</td><td>longitude/(°)</td><td>receiver type</td><td>country</td></tr><tr><td>BJFS</td><td>39.60N</td><td>115.89E</td><td>ASHTECH Z-XII3</td><td>China</td></tr><tr><td>CHAN</td><td>43.79N</td><td>125.44E</td><td>ASHTECH Z-XII3</td><td>China</td></tr><tr><td>GUAO</td><td>43.47N</td><td>87.7E</td><td>ASHTECH UZ-12</td><td>China</td></tr><tr><td>KUNM</td><td>25.02N</td><td>102.79E</td><td>ROGUE SNR-8000</td><td>China</td></tr><tr><td>LHAZ</td><td>29.65N</td><td>91.10E</td><td>TPS E_GGD</td><td>China</td></tr><tr><td>TWTF</td><td>24.95N</td><td>121.16E</td><td>ASHTECHZ-XII3T</td><td>China</td></tr><tr><td>URUM</td><td>43.80N</td><td>87.60E</td><td>AOA SNR-8000 ACT</td><td>China</td></tr><tr><td>WUHN</td><td>30.53N</td><td>114.35E</td><td>ASHTECH Z-XII3</td><td>China</td></tr><tr><td>XIAN</td><td>34.36N</td><td>109.22E</td><td>ASH701945C_M</td><td>China</td></tr><tr><td>ADE1</td><td>33.27S</td><td>138.64E</td><td>ASHTECH Geodetic 3</td><td>Australia</td></tr><tr><td>ADE2</td><td>34.43S</td><td>138.38E</td><td>ASHTECH Geodetic 3</td><td>Australia</td></tr><tr><td>ALIC</td><td>22.32S</td><td>133.88E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>BAKO</td><td>5.50S</td><td>106.84E</td><td>LEICA GRX1200</td><td>Indonesia</td></tr><tr><td>CEDU</td><td>30.13S</td><td>133.80E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>JAB1</td><td>11.34S</td><td>132.89E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>KARR</td><td>19.01S</td><td>117.09E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>KOUC</td><td>19.44S</td><td>164.28E</td><td>TRIMBLE NETRS</td><td>New Caledonia</td></tr><tr><td>MOBS</td><td>36.17S</td><td>144.97E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>NNOR</td><td>30.95S</td><td>116.19E</td><td>ASHTECH Z-XII3</td><td>Australia</td></tr><tr><td>PARK</td><td>31.00S</td><td>148.26E</td><td>JPS E_GGD</td><td>Australia</td></tr><tr><td>PERT</td><td>30.19S</td><td>115.88E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>STR1</td><td>35.18S</td><td>149.00E</td><td>LEICA GRX1200</td><td>Australia</td></tr><tr><td>STR2</td><td>34.68S</td><td>149.01E</td><td>TPS E_GGD</td><td>Australia</td></tr><tr><td>SUNM</td><td>26.51S</td><td>153.03E</td><td>JPS LEGACY</td><td>Australia</td></tr><tr><td>SYDN</td><td>32.21S</td><td>151.15E</td><td>JPSE_GGD</td><td>Australia</td></tr><tr><td>TOW2</td><td>19.73S</td><td>147.05E</td><td>ASHTECH UZ-12</td><td>Australia</td></tr><tr><td>XMIS</td><td>10.26S</td><td>105.41E</td><td> JPS LEGACY</td><td>Australia</td></tr><tr><td></td><td>28.95S</td><td></td><td>ASHTECH Z18</td><td></td></tr><tr><td>YARR</td><td></td><td>115.34E</td><td></td><td>Australia</td></tr></table></body></html>

PRN30,PRN31,中国境内的 $\mathrm { H A I N } ( 1 9 . 4 ^ { \circ } \mathrm { N } , 1 0 9 . 1 ^ { \circ } \mathrm { E } )$ 和GUAZ $( 2 3 . 1 ^ { \circ } \mathrm { S }$ ， $1 0 8 . 3 ^ { \circ } \mathrm { E }$ ）也发生了中等水平的幅度闪烁事件，两台站距离较近，观测到闪烁的卫星相同，均为 PRN5，PRN14，PRN18，PRN21，PRN22,PRN30卫星.对比图2与图4可以看出，闪烁事件的发生和结束时间与太阳射电爆发时间一一对应.

根据定义[18]，相位闪烁指数为高采样率下相位观测值在一分钟内的标准差，幅度闪烁指数表征接收信号功率的起伏，其表达式分别为

$$
\begin{array} { l } { \displaystyle \sigma _ { \varphi } = \sqrt { E ( \delta _ { \varphi } ^ { 2 } ) } , \qquad \mathrm { ( ) } } \\ { \displaystyle S _ { 4 } = \sqrt { \frac { E ( S _ { \mathrm { I } } ^ { 2 } ) - E ( S _ { \mathrm { I } } ) ^ { 2 } } { E ( S _ { \mathrm { I } } ) ^ { 2 } } - \frac { 1 0 0 } { S / N _ { 0 } } \Big ( 1 + \frac { 5 0 0 } { 1 9 S / N _ { 0 } } \Big ) } . } \end{array}
$$

式中， $E$ 表示期望值， $\delta _ { \varphi }$ 表示相位， $S _ { \mathrm { I } }$ 表示信号强度$S / N _ { 0 }$ 表示信噪比, $\delta _ { \varphi }$ 和 $S _ { 4 }$ 分别描述相位波动和接收信号强度 (功率)波动大小.由于射电暴增加所观测信号的噪声，因此射电暴期间相位闪烁指数不会有明显的变化，即不会发生相位闪烁现象，图4显示结果与分析结果完全一致.电离层闪烁也会导致接收机失锁等效应，但其与射电暴引起的闪烁现象具有本质区别.

根据统计[19]，电离层闪烁现象一般发生在夜间,在地磁平静条件下，白天发生电离层闪烁事件的可能性不大．图5给出了太阳射电暴期间的地磁 $K p$ 指数，从图中可以看出 $K p$ 指数均小于3，表明当天地磁平静.另外，电离层导致的闪烁事件有明显的地域特征和季节分布特征，电离层闪烁主要发生在赤道异常区和极区，一般春秋两个季节发生的频次多，且多发生于夜间，地磁平静条件下，在12月份北半球冬季及南半球夏季白天时间段内均不太可能发生电离层闪烁事件

以上分析结果表明，2006年12月13日发生的太阳射电暴事件给向阳面台站的GPS信号造成明显影响.太阳射电暴的影响主要是压制接收到的无线电信号，当噪声达到一定强度时，能使GPS接收机失去对卫星信号的锁定，从而导致失锁和服务中断.图6给出了表1中所选取的各个GPS台站上空锁定卫星数目的变化情况 (本文提到的失锁指同时失去L1和L2信号).在射电暴期间，所选取的位于澳大利亚境内的全部IGS台站和中国境内的部分台站(KUN-M和XIAN)锁定GPS卫星数目明显下降.图6同时显示，射电暴期间，部分台站锁定卫星数目小于等于4颗.一般而言，GPS定位服务至少需要4颗卫星，因此射电暴期间，澳大利亚境内部分台站的定位服务完全中断，主要发生在03:31UT-03:37UT时间段.事件期间，由于中国地区离日下点较远，此次射电暴的影响相对较弱，只有部分台站受到影响，

![](images/4d08fd4571a24c4d642d7491e7311d649c18f18202729c341a6e1a366e3e4861.jpg)  
图52006年12月13日 $\mathrm { 3 h }$ 地磁 $K p$ 指数Fig.53-hour $K p$ index during solar radio burston December 13,2006

对于普通的商用GPS双频接收机而言，由于缺乏Y码，一般采用半无码和无码跟踪技术,因此在L2濒率上信噪比会有较大的损失，相对L1信号而言，射电暴对L2 信号的影响会更大[20]，这主要是由于GPS信号在两个频率上的不同而导致的.

# 3讨论与结论

利用太阳射电观测数据、L波段闪烁观测数据、不同地区的GPS观测网数据，以及部分空间环境数据，分析了2006 年12月13日太阳射电暴期间向阳面GPS的性能和效应，结果显示太阳射电暴对GPS的完整性和连续性产生了明显影响，主要结论如下.

(1）射电暴对向阳面的GPS台站观测造成不同程度的影响，两个不同区域台站均观测到幅度闪烁现象，而没有观测到相位闪烁的发生.(2）此次射电暴期间，GPS发生明显失锁现象，而且多个台站及多颗GPS卫星信号完全中断长达 $6 \mathrm { { m i n } }$ (3）射电暴期间，多个台站锁定的卫星数目小于4颗，使得GPS定位服务完全失效(4)相对而言，射电暴期间，日下点附近的GPS台站受到的影响比远离日下点的影响要大，

虽然爆发L波段太阳射电暴的频次不多，但对于卫星导航定位而言，其影响不能忽视.太阳射电暴对无线电系统的影响不可能完全消除，只能采取不同措施来降低和减缓由此带来的危害，例如加强太阳活动预报，认识太阳射电暴对GNSS的影响;增强天线的抗干扰能力；采用多系统集成接收机提高系统的观测能力；重要的测量活动避开射电暴时间段等.另外值得注意的是，中国自主北斗卫星导航系统与G-PS系统的轨道和信号频率均很相近，随着北斗导航系统的成熟，基于北斗和其他导航系统的应用不断推广[21-22]，因此北斗系统不可避免地会受到太阳射电暴的影响，本文结果将对未来北斗导航系统在应对太阳射电暴的影响方面具有一定借鉴意义，

![](images/44363d6588b7ef42d3be461dd7fa836db63a5f0cf567775c16b97bb7f2a18ae5.jpg)  
图6射电暴期间不同台站上空锁定的GPS卫星数随时间的变化 Fig.6Locked number of GPS satellites with respect to time during this event

致谢观测数据由国际GNSS 服务网(IGS)、世界数据中心(WDC)、美国空间天气预报中心和中国电波环境特性及模化重点实验室提供.

# 参考文献

[1]Hofmann-Wellenhof B,Lichtenegger H,Wasle E.GNSSGlobal Navigation Satellite Systems: GPS,GLONASS, Galileo and More [M].Austria:Springer,2007:1-100   
[2] Coco D.GPS-satellites of opportunity for ionospheric monitoring[J].GPS World,1991,2(9):47-50   
[3]Klobuchar JA,Kunches J M,Van Dierendonck A J.Eye on the ionosphere:Potential solar radio burst effects on GPS signal to noise[J]. GPS Solut., 1999,3(2):69-71   
[4]MacAlester MH,Murtagh W.Extreme space weather impact:An emergency management perspective [J].Space Weather, 2014,12(8):530-537   
[5]Ji Shengyue,Chen Wu,Weng Duojie,et al.A study on cycle slip detection and correction in case of ionospheric scintillation[J].Adu.Space Res.,2013,51(5):742-753 [6] Bala B,Lanzerotti L J,Gary D E,et al.Noise in wireless systems produced by solar radio bursts [J].Radio Sci.,   
2002,37(1):2253-2257 [7]Nita G M,Gary DE,LanzerottiLJ,et al. The peak flux distribution of solar radio bursts [J].Astrophys.J.,2002,   
570:423-438 [8] Chen Zhiyu,Gao Yang,Liu Zhizhao.Evaluation of solar radio bursts’effect on GPS receiver signal tracking within International GPS Service network[J].Radio Sci.,2005,   
40,RS3012,doi:10.1029/2004RS003066 [9]Afraimovich E L，Demyanov V V，Ishin A B,etal. Powerful solar radio bursts as a global and free tool for testing satellite broadband radio systems，including GPSGLONASS-GALILEO[J].J.Atmos. Solar-Terr. Phys.,2008,70(15):1985-1994 [10] Cerruti A P,Kintner P M,Gary D E,et al.Observed solarradio burst effects on GPS/Wide Area Augmentation System carrier-to-noise ratio[J].Space Weather, 2006,4, S10006,doi:10.1029/2006SW000254 [11]Carrano CS，Bridgwood C T，GrovesK M.Impacts of the December 2Oo6 solar radio bursts on the performance of GPS[J].Radio Sci.，2009，44，RS0A25, doi:10.1029/2008RS004071 [12] Sreeja V,Aquino M,De Jong K,et al.Effect of the 24 September 2O1l solar radio burst on precise point positioning service[J]. Space Weather, 2014,12(3):143-147 [13]Yue X,Schreiner WS,Kuo YH,et al.The effect of solar radio bursts on the GNSS radio occultation signals [J]. J. Geophys.Res.,2013,118(9):5906-5918   
[14]Vladislav V,Demyanov V,Afraimovich EL,et al.An evaluation of potential solar radio emission power threat on GPS and GLONASS performance[J].GPS Solut., 2012,16(1):411-424   
[15]Shi C,Jin SG,Dang YM,et al.Research advances in BDS/GNSS navigation applications [J]. J. Satell. Navig., 2013,1(3):1-6   
[16]Gennady G P.Fine Structure of Solar Radio Bursts [M]. Berlin:Springer,2011:1-10   
[17] Schmidt J M,Cairns IH,Lobzin V V.The solar type II radio bursts of 7 March 20l2:Detailed simulation analyses[J].J.Geophys.Res.,2014,119(8):6042-6061   
[18]Van Dierendonck A J,Klobuchar J,Hua Q.Ionospheric scintillation monitoring using commercial single frequency C/A Code Receivers [C]//Proceeding of ION GPS-93. Salt Lake City:The Institute of Navigation,1993:1333- 1342   
[19] Sreeja V,and Aquino M. Statistics of ionospheric scintillation occurrence over European high latitudes [J].J. Atmos. Solar-Terr. Phys.,2014,120:96-101   
[20] Skone S H.The impact of magnetic storms on GPS receiver performance [J].J. Geod.,2001,75(9):457-468   
[21] Jin S G.Recent progresses on Beidou/COMPASS and other Global Navigation Satellite Systems (GNSS）I[J]. Adu.Space Res., 2013,51(6):941-946   
[22] Jin S G.Recent progresses on Beidou/COMPASS and other Global Navigation Satellite Systems (GNSS) II[J]. Adv.Space Res.,2014,54(5):809-810