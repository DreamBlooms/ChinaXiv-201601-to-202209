# CN 53-1189/P ISSN 1672-7673

# CAPS昆明测定轨站

张建华¹，陈亮²

(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院国家授时中心，陕西 西安 710600)

摘要：基于卫星双向时间频率传递技术的转发式卫星测定轨技术，可精确地测定地面站到卫星间的距离，并能实现各站间高精度时间同步。中国区域定位系统（Chinese Area PositioningSystem，CAPS)按国内最佳布局建立了VSAT(小口径终端)转发式卫星地面测定轨网，昆明卫星地面站是中国区域定位系统卫星测定轨网的重要组成部分之一。昆明卫星地面站的仪器频率全部由高精度原子钟提供，仪器参数可以设定，仪器时延能够实时精确地测定，是一个全自动的转发式卫星地面站，为中国区域定位系统高精度卫星测定轨提供有力支撑。

关键词：转发式卫星测定轨；卫星双向时间频率传递；昆明卫星地面站中图分类号：P128.4 文献标识码：A 文章编号：1672-7673(2016)03-0340-05

目前国际上卫星导航系统有全球定位系统（Global Positioning System，GPS）、俄罗斯的全球卫星导航系统格洛纳斯(Global Navigation Satellite System，GLONASS)及中国的北斗卫星导航系统等，这些卫星导航系统的组成和工作原理基本相近[1]：卫星装备高精度的原子钟发射带有时间信息和卫星位置导航信息的扩频码，当接收机接收到多于4颗卫星的信号，便可确定接收机的三维位置和接收机钟差。导航系统的卫星精密轨道均由接收卫星时钟信号与接收机时钟的时差确定，显然卫星导航系统中最基本的是精确的系统时间。

中国区域定位系统是新颖的卫星导航系统，该系统主体部分在地面，其导航信号发射在地面，空间部分仅租用地球同步轨道(Geostationary Earth Orbit，GEO)通信卫星；通过地球同步轨道通信卫星转发导航信息和信号[2]。地球同步轨道卫星最大的优点是覆盖性能好，特别适用于区域导航系统，日本和印度的区域导航系统均采用地球同步轨道卫星。但是，这类卫星相对于地面运动小[3」，仪器系统误差难于分离，致使地球同步轨道通信卫星的精密定轨有相当大的难度。国家授时中心发明的转发式卫星测定轨方法[3]，其信号发射和接收均在地面，仪器观测系统误差可以在地面实时确定，解决了地球同步轨道卫星精密定轨的难题；本方法最大的优点是卫星轨道与时间的确定相互独立，大大提高了卫星定轨精度。

# 1转发式卫星测定轨方法

转发式卫星测定轨方法如图1。各地面站利用高精度的原子钟发射时间信号，发射的时间信号经卫星转发，各地面站能接收卫星转发器转发的所有站发射的时间信号，码分多址技术使多个站同时用同一频率向同一颗卫星发射各自的时间信号而互不干扰[3]，根据需要接收信号可以进行不同组合(图1)，因此，转发式卫星测定轨方法可以有多种模式进行卫星测定轨：

![](images/71a59e086702eceada273b32b0d18112bcf7a544d0ae95ce6b05edce7cc1db05.jpg)  
图1转发式卫星测定轨原理图  
Fig.1Schematic diagram of Orbit Determination by Transfer

(1)自发自收模式

由 $i$ 站(各站相同)向卫星发射测距信号，经卫星转发后，仍由i站接收，确定测距信号往返路径的时差。在该模式下，对测定轨站时间同步的精度要求不高，各站时间同步误差主要影响卫星观测量的时标[3]。

# (2)一发多收模式

只有一个站发射上行信号，其他各站只接收该站信号，用一发多收技术进行卫星测定轨，精度在很大程度上取决于主站和分站间的原子钟同步精度，这种工作模式特别适用于上行点波束的情况。

# (3)多发一收模式

所有站发射上行信号，只有主站接收其他各站信号，用多发一收技术进行卫星测定轨，主站和分站间的原子钟同步的精度是关键，这种工作模式特别适用于下行点波束的情况，接收数据仅在主站，避免大容量数据传输困难。

# （4)成对观测模式

每2个站组成一组，各自接收对方站的时间信号，由于对称性观测，2个观测量相加消除两站钟差的影响，相当于卫星在这两站为焦点的椭球上，对卫星约束更好，每个站有 $N$ 个独立观测量， $N$ 个站系统总共有 $N \times N$ 个独立观测量，相当于 $N$ 个全球定位系统同时进行冗余测定轨，提高测定轨精度。

# 2昆明站转发式卫星测定轨系统

昆明站是中国区域定位系统转发式卫星测定轨的主要站之一，它的系统配置和其他测轨站完全一样：小口径终端卫星地面站、高精度时间系统、地面站终端、地面站时延校正系统、自动气象站及自动监控等系统组成（图2）。

![](images/8a20210e6af122afc935e298067e1d77ae6903eeb801d1dda42bec15c7717e31.jpg)  
图2转发式卫星测定轨方框图  
Fig.2Diagram of Satellite Orbit Determination by Transfer

昆明站有 $5 \mathrm { m }$ 、 $3 . 7 \mathrm { m }$ 口径抛物面天线，每架天线均有信号收发功能，其收发隔离度优于 $4 0 ~ \mathrm { d B }$ 。昆明站卫星测定轨系统发射上行信号，经天线发射到卫星，卫星转发此信号，地面站接收转发的下行信号。上、下行载波信号工作频率在C波段 $( 4 \ : \mathrm { G } / 6 \ : \mathrm { G } )$ ，计算机控制调制解调器信号发射/接收功能，同时同步接收气象、微波辐射计及其他传感器数据。

高精度时间系统：测轨观测时间系统的核心是高精度的原子钟，它产生高精度的时间及频率。昆明站采用全球定位系统的1pps与原子钟的1pps通过计数器相互比对，使本地原子钟的时间与协调世界时(UTC)时间之间实现初同步，校正原子钟的 $1 \mathrm { \ p p s }$ 与协调世界时间同步在几十纳秒之内，每次观测前需要重复同步过程，通过系统本身时间传递功能，测定轨系统与站内的时间系统实现严格同步，观测中所有指令由工控机按规定程序自动完成，站内测定轨的时间与主控站的时间在实现测定轨的同时实现时间同步。

地面站终端调制解调器(卫星时间距离测量设备：Satelite Time and Rang Equipment，SATRE)具有发射时间扩频信号和接收功能。该终端是中国区域定位系统卫星测定轨系统的关键，用于测量各地面观测站到卫星的伪距。卫星时间距离测量设备包括发射通道和多个接收通道，利用伪码扩频技术各站同时向卫星发射各自不同伪码的时间信号，经卫星转发器，各地面站接收卫星转发的信号，MODEM测量整个路径上的时延。

卫星时间距离测量设备接收终端在发射通道(TX1PPS)产生一个伪噪声调制信号，它包含已知的伪码，产生的信号调制到射频载波为上行信号发射到卫星，经卫星转发，信号经过通信路径成为下行信号，被卫星时间距离测量设备接收机在正确的频率、正确的伪码接收（产生RX1PPS），该时延通过计数器测量，原子钟为计数器提供参考频率，地面站接收机收到信号，读出计数器数据，从而完成路径时延测量，实际的测量过程连续进行。

地面站时延校正系统尤如激光测距的地靶，测定相对于参考点的时延，在系统设计时考虑到仪器时延受温度影响，关键部位均有恒温设计，尽管采取特别恒温设计，为避免因仪器状态不一致引起仪器系统差的变化，专门设计地面站时延校正系统，每小时实时测定仪器的系统误差，时延校正测量的功率及其他状态和卫星测距状态完全一致。实时测定仪器系统有相当高的测量精度，图3是典型的测定昆明站仪器的样本，一般测量精度优于 $0 . 0 2 { \mathrm { n s } }$ ，相当于测定误差在 $6 \mathrm { m m }$ 之内。

![](images/9723c1c930b03f3ad5798a5a3e287553935f2fb833c80e61e55c33c006596294.jpg)  
图3典型的昆明站测定仪器误差效果  
Fig.3A Typical Measurement of Instrumental System Error at Kunming Station

昆明卫星测定轨站有自动监控系统，对所有设备进行设置并实时监控。仪器一旦设置后实现全自动观测：天线自动跟踪卫星、采集卫星测定轨系统的测轨数据和设备状态参数，空间环境，自动气象站气象数据及电离层改正数据，采集卫星地面站的时间同步数据以及地面站系统误差的自校准系统数据，全部数据和设备状态参数通过专用网络传送给主站进行轨道计算。

# 3 卫星双向时间传递

卫星双向时间传递是目前国际上最高的时间比对技术之一，转发式卫星测定轨系统本身具有卫星双向时间传递功能[4]。卫星双向时间传递原理：有 $A$ 、 $B$ 两站， $A$ 站和 $B$ 站处于同等地位，A站主钟秒信号经终端调制后发送给卫星，卫星转发给 $B$ 站， $B$ 站解调来自 $A$ 站的秒信号，用时间间隔计数器测定接收秒信号与 $B$ 站主钟秒信号之间的时间差， $B$ 站过程与 $A$ 站一样，因时间信号通过的路径相同，得到高精度的时间比对结果，同时 $A$ 站和 $B$ 站有时间间隔计数器每秒测定各自终端引起的时延。两站由于对称性，路径的影响基本上可以抵消。

高精度的原子钟是测定轨站观测的时间标准，依托全球定位系统时间实现主站与分站时间粗同步，分站内测定轨设备的时间与主控站的时间在实现测定轨的同时实现时间高精度同步。

# 4卫星地面站测定轨系统特点

借助地面高精度原子钟（比星载原子钟稳定度高2个量级），利用伪码正交性，各个站以码分多址的方式向同一颗卫星以相同的频率上传信号，每一个卫星地面站上传的信号相当于一颗全球定位系统卫星发射的信号，这相当于 $N$ 个全球定位系统卫星的信号。用很高速率的伪码测距（比全球定位系统精码速率高），有很高的测量精度，测距内部精度优于 $1 \mathrm { { c m } }$ 。测距信号生成和信号测量均在地面站进行，仪器发射系统误差和接收系统误差通过设计的仪器自校准系统进行实时校准，单次测定仪器误差的精度优于 $6 \mathrm { m m }$ ，原则上观测结果消除了仪器误差的影响[5]，原理上时间比对和卫星测定轨互不影响,扩频增益大，需要的发射功率低，低于强信号23dB情况下仍可正常工作，可在寄生情况下工作。

基于上述优点，转发式测定轨能实现高精度的测定轨，得到很高的卫星轨道精度[6，一般情况下卫星定轨残差优于 $1 0 \ \mathrm { c m }$ 。

# 5昆明站运行情况

昆明站在2014年及2015年初进行了设备的升级改造，并配备了新铯钟作为系统的时间频率标准（铯钟型号为OSA3235B，其准确度优于$\pm \ : 1 \times 1 0 ^ { - 1 2 }$ ，日稳定度 $\leqslant 2 . 7 \times 1 0 ^ { - 1 3 }$ )。目前昆明站设备状态良好，工作正常。图4是2015年下半年昆明站观测情况的统计。

昆明站在2015年共完成了8颗地球同步轨道通讯卫星的观测任务，其中5颗卫星属于常规观测，3颗卫星为临时观测任务。昆明站在保证常规观测任务顺利进行的情况下，圆满完成临时观测任务。

![](images/b8ffc4c5b0f5e4f192eca0aeed80c10a4af6bf4d9839bcb0ea59a22592cc7bb0.jpg)  
图4昆明站2015年观测情况统计Fig.4Observation statistics of Kunming station in 2015

由于昆明站的地理优势，在卫星观测上有特殊地位，特别是倾斜轨道卫星，能实现卫星全弧段观测，图5是2015年6月17日昆明站对某地球同步轨道通讯卫星观测数据的定轨残差，可以得出昆明站转发式卫星测定轨系统有相当高的观测精度。

![](images/3e1b2990edb870c53f12409828846b8124538afe1f0d57567f04d514df10c207.jpg)  
图5昆明站2015年6月17日观测数据的定轨残差  
Fig.5Orbit determination residuals of observational data obtained by Kunming station on June 17,2015

# 6结束语

转发式卫星测定轨方法具有高精度测轨性能，它具有自校准系统，特别适用地球同步轨道卫星的观测[7]

昆明站中国区域定位系统特点：

(1)测距 $\leqslant 1 0 ~ \mathrm { m m }$ ，采样间隔为1s;  
(2)全天时、全天候、实时、简单、无人值守、仪器运转稳定可靠；  
（3)配备有铯原子钟，时间同步精度优于 $1 ~ \mathrm { n s }$ 。

昆明站与国家授时中心在转发式卫星测定轨项目中协同工作，原子钟1pps与协调世界时间同步精度优于 $1 \mathrm { n s }$ ，协同整个卫星测定轨系统完成各阶段的联测、常规观测及各项任务，显然昆明站特殊的地理位置，是中国区域定位系统国内布局不可或缺的卫星测轨站。

# 参考文献：

[1] Ai Guoxiang，Shi Huli，Wu Haitao,et al. A positioning system based on communication satelitesand the Chinese Area Positioning System（CAPS）［J]. Chinese Journal of Astronomy andAstrophysics，2008，8(6) : 611-630.  
[2] 余宜珂，王萌.基于CAPS 系统的信号调制方式的比较研究［J]．天文研究与技术——国家天文台台刊，2014，11(3)：224-229.Yu Yike，Wang Meng. Comparitive studies of signal-modulation methods based on the CAPS[J].Astronomical Research & Technology——Publications of National Astronomical Observatoriesof China，2014，11(3):224-229.  
[3] 李志刚，艾国祥，施浒立，等．转发器式卫星测定轨方法：中国，200310102197.1［P].2003-12-30.  
[4] 杜晓辉，施浒立，张丽荣，等.一种转发式卫星授时新方法［J］．天文研究与技术—国家天文台台刊，2012，9(1)：34-38.Du Xiaohui，Shi Huli, Zhang Lirong，et al. Study of a forwarding approach of satellite time service[J].Astronomical Research & Technology——Publications of National Astronomical Observatoriesof China，2012，9(1) :34-38.  
[5] 施浒立，孙希延，李志刚.转发式卫星导航原理［M].北京：科学出版社，2009.  
[6] 李志刚，乔荣川，冯初刚.卫星双向法与卫星测距［J]．飞行器测控学报，2006，25(3）：1-6.Li Zhigang，Qiao Rongchuan，Feng Chugang.Two Way Satellite Time Transfer（TWSTT）andsatellite ranging ［J]. Journal of Spacecraft TT & C Technology，2006,25(3）: 1-6.  
[7] Yang Xuhai，Li Zhigang，Feng Chugang. Methods of rapid orbit forecasting after maneuvers forgeostationary satellites ［J]. Science in China Series G：Physics，Mechanics and Astronomy,2009，52(3):333-338.

# Kunming Satellite Orbit Determination Station for Chinese Area Position System（CAPS)

Zhang Jianhua’，Chen Liang² (1.Yunnam Observatories，Chinese Academy of Sciences，Kunming 650011,China,Email;zjh@ ynao.ac.cn; 2.National Time Service Center,Chinese Academy of Sciences，Xi'an 71O6OO,China)

Abstract:Determination of satelite orbit by transfer，based on the Two Way Satelite Time and Frequency Transfer,is implemented with the observations of multi-stations.The distances between a satelite and ground stations are determined.The net of ground stations with the VAST system is established for the CAPS project. Kunming station is one of them.The frequency of all equipments in Kunming is controlled by anatomic clock and all status can be set upas wellas monitored.The time delay of instruments can be determined.It can carry out functions such as orbit determination and time synchronization at remote stations.

Key words:Satelite Orbit Determination by Transfer；Two Way Satelite Time and Frequency Transfer； Kunming Substation of Satellite Orbit Determination