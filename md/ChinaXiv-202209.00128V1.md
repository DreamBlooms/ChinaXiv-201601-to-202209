# 基于SimpleThresholding和CUSUM联合算法的L波段太阳射电流量

# 可观测频段分析的研究

杨航，董亮²，何乐生1\*\*(1.云南大学 云南 昆明 650504；2.中国科学院云南天文台 云南 昆明 650216)

摘要：L波段太阳射电爆发是导航系统不稳定性的潜在影响因素，通过L波段内精密太阳射电流量的监测可以实时发现太阳射电爆发干扰导航事件，为此云南天文台本部拟建立一个L波段多频点太阳射电监测系统。而对无线电环境的有效评估对于该监测系统观测数据的稳定获取至关重要。本文介绍了该监测平台的无线电监测准备研究,通过对云南天文台本部凤凰山地区的L波段无线电环境进行了100小时的测试。本文提出一种基于 Simple Thresholding 算法与CUSUM算法的改进阈值的算法，遴选出介于北斗 B1、B2、B3 频点，GPSL1、L2频点之间7个5MHz无线电干扰较少的无线电通带，分别为 $1 5 5 1 \mathrm { M H z } { \sim } 1 5 5 5 \ \mathrm { M H z } ,$ 1596MHz\~1600MHz、1161MHz\~1165MHz、1221MHz\~1225MHz、1246MHz\~1250MHz、1291MHz\~1295MHz、1231MHz\~1235MHz，其洁净率分别为 $9 8 . 3 2 9 \%$ 、 $9 8 . 3 0 1 \%$ 、 $9 8 . 3 1 5 \%$ 、 $9 8 . 3 3 5 \%$ 、 $9 8 . 2 2 4 \%$ 、 $9 7 . 6 5 0 \%$ 、 $9 8 . 2 6 0 \%$ ，均符合太阳观测需求。为下一步接收机的设计和信号处理提供了依据。

关键词：L波段；监测系统；无线电环境；阈值；洁净率中图分类号：P161.4 文献标识码：A

# 0引言

太阳活动是空间天气的源头，日冕物质抛射(coronal mass ejection，CME)[]事件是影响日地空间环境最主要因素，射电观测反映了不同日冕高度的等离子体信息[2，包括密度、磁场等，进一步，随着等离子体从太阳上抛射出来，其密度随着远离太阳的距离而降低随着CME 物质远离太阳，其发射出来的无线电频率也在随之降低，为此太阳物理界一致认为地基太阳射电望远镜所能观测到的无线电爆发频率越低，CME 物质离地球就越近。那么在不同频率上的太阳射电进行观测，必然可以反演这个日冕高度上的动态信息[3-5]。

同时，在长期的太阳射电流量监测中发现其不同频段的流量变化与太阳活动周高度相关，其是重要的空间天气观测指标。但另一方面，射电的观测频段与民用无线电使用频段重合，这样极易容易造成对观测数据的干扰，造成误判。在射电望远镜建设之前的无线电环境测试与评估尤为重要，与脉冲星、活跃星系核(active galactic nucleus，AGN)光变等需要宽带观测不同[6-7]。由于高时间分辨率要求，太阳射电精密流量观测时对一些偶发性的干扰并不敏感,这个短时"坏点"可以通过后期与太阳光学等数据进行比较排除爆发可能。

L波段太阳射电爆发是导航通信的潜在干扰因素，与其他空间天气事件不同的是，太阳爆发的强信号以光速传播，是作用最快的空间天气事件，且从理论上来说整个迎日面的导航接收机均有可能受到干扰[8-10];董亮、黄文耿、闫小娟等人提出了采用L波段多通道精密太阳射电望远镜同步监测的办法，实时监测L波段太阳射电流量，在爆发早期发出预警信号[11-13]。

但是L波段存在大量无线电干扰，在建设望远镜前本文需要评估MHz级的观测带内无线电干扰信号的分布规律，判断可观测太阳时间，对于长时间被干扰占用的信道进行排查。以防发生误报等情况，针对即将在云南天文台凤凰山本部建设的L波段的精密流量太阳射电望远镜(针对中高日冕进行研究和太阳射电爆发干扰导航通信预警，并作为廊坊太阳射电望远镜的备份)，本文介绍了对台址的无线电测试结果和观测频段遴选方法以及遴选出介于北斗B1、B2、B3频点，GPSL1、L2频点之间7个5MHz无线电干扰较少的

无线电通带。

# 1 系统组成

1.1 系统组成

测试系统由HL050天线、低噪声放大器、稳压电源、FSU26频谱仪和计算机组成，测试系统框图如图1所示。

![](images/bd7b5e14d30a2e5faea4109621f631324a3400cbdbcffd9173792a8bbc29dd9a.jpg)  
图1测试系统  
Fig.1 Test system

系统框图中，由HL050天线将采集的信号通过低噪声放大器放大信号，再传输到FSU26频谱仪转化成频谱，并把数据传输给计算机进行显示和存储。其中稳压电源为放大器提供稳定电压，保证数据的准确性，计算机通过LabView 图形化编程实现控制频段范围和极化方式，主要分为两个部分：HL050天线频段控制和频谱仪控制程序[14]。

# 1.2 测试设备及参数

天线采用的是HL050对数周期天线，参数见表1，HL050 天线是一种应用广泛的天线，其优点是结构简单、频带宽、功率容量大、调整与使用方便①。

频谱仪采用德国罗德施瓦茨公司的 FSU26，工作频率 $2 0 \mathrm { H z } { \sim } 2 6 . 5 \mathrm { G H z }$ ，平均噪声电平为- $1 5 8 \mathrm { d B m } ^ { \textcircled { 2 } }$ ，参数见表1。

计算机利用LabView软件图形化编程实现，在LabView 软件图形化编程中，可以调节测试的频段起始频率、极化方式、分辨率带宽、积分时间及执行次数，并将采集到的信号保存在预设地址中，便于对后续数据的处理分析。

# 表1测试设备及参数[15]

Tab.1 Test equipment and parameters[5]   

<html><body><table><tr><td>Equipment</td><td>Model</td><td>Frequency range</td><td>Technical specifications</td></tr><tr><td>R&S logarithmic periodic antenna</td><td>HL050</td><td>0.85MHz~26GHz</td><td>StandingWavebie: ≤2.5 gain/dBi: 8~8.5</td></tr><tr><td>B&Z low noise amplifier</td><td>BZ-0218-201030-202525</td><td>2GHz~18GHz</td><td>Standing Wavebie: ≤2.5 gain /dBi: 30</td></tr><tr><td>R&SFSU26 spectrometer</td><td>RS-HL050</td><td>20Hz~26.5GHz</td><td>Phase noise: 137dBc /Hz</td></tr></table></body></html>

# 1.3 监测过程

测试地点为云南省昆明市中国科学院云南天文台，主要对天文台凤凰山本部天文台台址( $2 5 ^ { \circ } 1 ^ { \prime } 4 8 . 5 3 8 ^ { \prime } \mathrm { N }$ $1 0 2 ^ { \circ } 4 8 ^ { \prime } 1 4 . 1 8 0 " \mathrm { E }$ )东、西、南、北4个方向L波段的测试，系统频率范围在 $1 \mathrm { G H z } { \sim } 2 \mathrm { G H z }$ ，频谱仪扫频宽度设置为 $1 0 0 0 \mathrm { M H z }$ 。频谱仪显示带宽和分辨率带宽设置为 $3 0 0 \mathrm { K H z }$ ，扫描时间30s。4个方向都测试了4次且时间超过8小时，共16次测试，每组数据均超过800组。具体测试日期及其组数如表2所示。

# 表2测试日期及组数（2022年）

Tab.2 Date of test and number of groups (in 2022)   

<html><body><table><tr><td>Test the orientation</td><td>First</td><td>Second</td><td>Third</td><td>fourth</td></tr><tr><td>East</td><td>04/04 831 group</td><td>04/13 1306 groups</td><td>04/24 1175 groups</td><td>04/25 1088 groups</td></tr><tr><td>South</td><td>04/03 820 groups</td><td>04/14 1368 groups</td><td>04/23 924 groups</td><td>04/26 1117 group</td></tr><tr><td>West</td><td>04/07 1062 groups</td><td>04/15 882 groups</td><td>04/21 988 groups</td><td>04/27 2219 Group</td></tr></table></body></html>

<html><body><table><tr><td>North</td><td>04/11 1074 groups</td><td>04/12 1270 groups</td><td>04/22 1137 groups</td><td>04/28 804 groups</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 2 数据处理

本节主要介绍采集数据的格式、数据阈值遴选及确定和本次最终信道的遴选过程及确定。

# 2.1 数据介绍

本文采集的数据记录格式为TXT文件的格式，单位为 $d B i$ ，缩小数据的绝对数值，方便记录。由于整个测试过程设置频谱仪输出两条线，所以每一组检测数据里面分为两列，如图2如示。第一列为所采集数据的最大保持值，第二列为所扫描时间内的平均值，为每次检测时判断测试系统的稳定效果。且数据储存为非线性的数据格式，这是一种对数的关系，底数为10，数学关系为 $\log 1 0 ( P _ { 2 } / P _ { 1 } )$ ，其中 $P _ { 2 } / P _ { 1 }$ 表示功率比。故后续数据处理需要对数据进行数据的线性转化[16-17]。

![](images/d496c5bef57f3d358cd3de30b94401abeda07359f3534beac0a3bd90db7e4897.jpg)  
图2测试系统实测图  
Fig.2Actual measurement diagram of the test system.

# 2.2 阈值遴选方案

针对即将在云南天文台凤凰山本部建设的L 波段的精密流量太阳射电望远镜，遴选出介于北斗B1(1559.052 MHz\~1591.788 MHz)、B2(1166.220MHz\~1217.370 MHz)、B3(1250.618 MHz\~1286.432 MHz)频点，GPS L1(1574.397 MHz\~1576.443 MHz)、L2(1226.577 MHz\~1228.623 MHz)频点之间7个 5MHz无线电干扰较少的无线电通带，由上述知道GPS 中L1频点在北斗B1频点的范围中，且B2与L2频点之间相差没有超过10MHz,无法遴选两处相对洁净的5MHz的通带,B2右边遴选的通带与L2左边遴选的通带相重合，一共7个通道（经过无线电环境监测带内无干扰信号)，使得GPS、北斗的所有通信频点都穿插在监测频点之间。[18-21]。

本次测试的目的是从L波段中遴选出洁净率（无线电干扰的时间占总监测时间的百分比）高于 $9 5 \%$ 的可用信道。遴选方式则是通过绘制出的频谱瀑布图中能直观的选出较为干净的信道，通过遍历观测数据超过阈值的占比来确定频谱洁净率，当遴选出的信道的洁净率都大于 $9 5 \%$ 则说明该信道可用。处理流程如下：

第一步，先选取一个短时"宁静"的观测频段作为阈值计算数据样本;

第二步，在上述数据样本中通过本文提出的阈值算法计算，得到阈值；

第三步，以此阈值再遍历其余观测时间段数据，对比阈值，超过阈值时间和低于阈值时间进行对比，求取得到该时间段的干扰信号所占比例；

第四步，利用算法计算得到的阈值对本文遴选的7个5MHz无线电干扰较少的无线电通带进行评估。

# 2.2.1 阈值计算方案

阈值分析法因其实现简单、检测结果精度较高而被广泛应用。代表性阈值分析法有CUSUM(cumulativesum)法[22]和 Simple Thresholding 法[23]，在检测某行(列)的观测数据时，CUSUM算法是通过估算累积样本的方差与平均值得到阈值,Simple Thresholding 算法是使用该行(列)的中位数作为其阈值[24]。

首先本文监测过来的数据取对数之后的数据，取对数之后不会改变数据的性质和相关关系，且压缩了变量的尺度，数据更加平稳，也消弱了模型的共线性、异方差性等，所以计算阈值时需要将数据线性化，如式(1)所示。

$$
x _ { i } = ( 1 ^ { * } 1 0 ^ { - 3 } ) 1 0 ^ { \frac { d B m V } { 1 0 } }
$$

样本的方差是表示 RFI 的统计异常值的重要估计值。由于绝对中位差(median absolute deviation,MAD)和中位数是消除异常值的最有效估计，因此本文提出了一种基于 Simple Thresholding 算法与CUSUM 算法的改进阈值算法对台址的L 波段无线电测试结果和观测频段进行遴选，如果所选取信道阈值水平超过 $ { \boldsymbol { { \pi } } } _ {  { \mathbf { { h } } } }$ ，则视为RFI。 $\pi$ 如式(2)所示。

$$
\scriptstyle { T \ h = { \bar { X } } - \alpha M A D }
$$

式(3)中， $\pi$ 为CUSUM算法所求线性阈值， $\bar { X }$ 为线性数据的均值,其中 $0 . 0 < \alpha < 5 . 0$ ，一般默认 $\alpha = 3 . 0$

$$
M A D = 1 . 4 2 8 6 \times m e d _ { _ { 1 \leq i \leq n } } \{ \left| x _ { i } - m e d ( x _ { i } ) \right| \}
$$

且 $m e d = 0 . 5 ( x _ { m } + x _ { m + 1 } )$ ， $n = 2 m$ ； $m e d = x _ { ( m + 1 ) }$ ， $n = 2 m + 1$ 。式中， $M A D$ 是 Simple Thresholding 算法中使用的方差估计值，由等式(3)定义，其中中位数是原始总体数组 $x _ { i }$ 的中位数。然后用此中位数减去原始样本每个元素，创建与原始元素大小相同的新修改样本。然后计算这个新样本的中位数，并用恒定的比例因子1.4286 相乘[25]，以使该估计与预期的高斯分布一致。

得到线性计算的阈值 $\pi$ 之后，需要将阈值取对数转换在监测的数据中去计算通带的洁净率，如式(4)所示，得到最后的阈值结果 $T \mathbf { h } ^ { * }$ 。整个阈值算法框图以及算法伪代码如图3所示。

$$
T \mathrm { h } ^ { \ast } { = } 1 0 ^ { - 3 } \ast \mathrm { l o g } 1 0 \mathrm { ( } T \mathrm { h } )
$$

![](images/2e961c8c8d9fc65fe1e37c15c80f1aef287ff3e94b9d97023562abf77681a7d9.jpg)  
图3阈值算法框图及算法伪代码(a）阈值算法框图；(b）阈值算法伪代码，

Fig.3Thresholdalgoritblockdagaadalgorithpsedocode(a)Thsholdalgortblockdagam;(b)resoldalgoritsedoode

# 2.2.2信道选取与数据比较

第一步，先选取一个短时“宁静"的观测频段作为阈值计算数据样本，初选是从表2中选取此次检测组数最多的一次作为信道的初选，西向测试在第四次04月27日时共采集了2219 组数据，故此次选取短时“宁静"的观测频段是在西向第四次数据所画的频谱瀑布图中选取，频谱图如图4\~图6所示;

第二步，在上述数据样本中通过上述的阈值算法计算得到阈值;

第三步，以此阈值再遍历其余观测时间段数据，对比阈值，超过阈值时间和低于阈值时间进行对比，求取得到该时间段的干扰信号所占比例，对比结果如表3所示;第四步，利用算法计算得到的阈值对本文遴选的7个5MHz无线电干扰较少的无线电通带进行评估。

![](images/36e1a5313b2591708becdc1405e358a8e9d4b80b2cc95aba425de332c2d64d17.jpg)  
图4L波段频谱瀑布图

图4中横坐标为L波段 $1 \mathrm { G H z } { \sim } 2 \mathrm { G H z }$ ，纵坐标为数据采样的组数，竖轴为采样的的信号强度，因为能较为直观的从图中看出本文所需频段的初步干扰情况，故此次L波段的所有测试均采用此种绘制方法。

![](images/a1baab629466f72a7217c7d96c2476939a0692ce23f025d336945aa2b51706d4.jpg)  
Fig.4L-band spectral waterfall   
图5L波段频谱右视图  
Fig.5L-band spectrumright view

图5为L波段频谱瀑布图的右视图，图中能清晰看到所有测试组数的信号强度，且能直观看到本文所需的频段的干扰情况，能为本文寻找短时"宁静"的观测频段确定的初步筛选工作。图6为L波段频谱瀑布图的下视图，图中标记出北斗B1、B2、B3频点及GPSL1、L2频点位置，为后续通带的遴选起辅助作用。

![](images/cf68254924f82e4c8f21050602b3d764609b736f40a9efc5128d9f2728bdf6f8.jpg)  
图6L波段频谱左视图

通过阈值算法对数据阈值的确定，实现对整个L波段监测数据遴选的多个5MHz无线电干扰较少的无线电通带中确定最终遴选的介于北斗星及GPS频点附近的7个无线电通带如图8所示，具体的信道选取的流程框图如图7所示。本文初步遴选了13个通带，但经过最终信道选取之后确定了7个5MHz无线电干扰较少的无线电通带。

![](images/fb206d096d13c8932e21a812f4eee7f72f4d89654851adaf120de0ec70039ab2.jpg)  
Fig.6L-band spectrumleftview   
图7遴选信道流程框图  
Fig.7Block diagram of the selection channel flow

本次测试主要是为了遴选出介于北斗 B1、B2、B3频点，GPS L1、L2频点之间7个5MHz无线电干扰较少的无线电通带，首先从图4\~图6中L波段频谱图中初选出 5MHz无线电干扰较少的无线电通带1161MHz\~1165MHz频段作为初选阈值确定的可用信道，再根据上述算法对阈值的确定后，通过阈值遍历对比程序将考察信道的洁净率进行计算，得到各组监测数据考察信道的洁净率如表3所示。从表3中可以看出在总的16次L波段的测试中所遴选的5MHz无线电干扰较少的无线电通带1161MHz\~1165MHz频段的信道洁净率都在 $9 5 \%$ 以上，符合太阳观测需求，所以本文选用此阈值为所遴选的7个5MHz无线电干扰较少的无线电通带的阈值。

表31161MHz\~1165MHz频段洁净率   
Tab.3 Cleanliness rates in the 1161MHz\~1165MHz band   

<html><body><table><tr><td>Test the orientation</td><td>First</td><td>Second</td><td>Third</td><td>fourth</td></tr><tr><td>East</td><td>98.580%</td><td>98.285%</td><td>98.366%</td><td>98.106%</td></tr><tr><td>South</td><td>97.829%</td><td>98.509%</td><td>98.051%</td><td>98.388%</td></tr><tr><td>West</td><td>98.418%</td><td>98.413%</td><td>98.744%</td><td>98.215%</td></tr><tr><td>North</td><td>98.585%</td><td>98.472%</td><td>98.205%</td><td>97.869%</td></tr></table></body></html>

本文结合图5\~图7以及表3初步遴选介于北斗B1、B2、B3频点以及GPSL1、L2频点之间7个5MHz无线电干扰较少的无线电通带如图8所示，图8为L波段频谱瀑布图中所遴选的通带情况，从图中看到本文所选的通带具体的干扰情况：

图中B2a(1161MHz\~1165MHz)和 $\mathrm { B } 2 \mathrm { b } / \mathrm { L } 2 \mathrm { a } ( 1 2 2 1 \mathrm { M H z } { \sim } 1 2 2 5 \mathrm { M H z } )$ 为B2频点附近通带;   
B2b/L2a(1221MHz\~1225MHz)和 $\mathrm { L 2 b } ( 1 2 3 1 \mathrm { M H z } { \sim } 1 2 3 5 \mathrm { M H z } )$ 为L2频点附近通带；   
B3a(1246MHz\~1250MHz)和B3b(1291MHz\~1295MHz)为B3频点附近通带;   
Lla(1551MHz\~1555MHz)和L1b(1596MHz\~1600MHz)为B1/L1频段附近通带。

![](images/aaa2e848dd2bf350bb18bc4321296f25e055bc195a830772f8c72ed32a280e5a.jpg)  
图8L波段频谱遴选通带   
Fig.8L-band spectrum selection channel

利用上述所求阈值确定遴选的7个5MHz无线电干扰较少的无线电通带的洁净率如下表4所示：北斗星B1、GPSL1频点遴选通带为1551MHz\~1555MHz、1596MHz\~1600MHz，其洁净率为 $9 8 . 3 2 9 \%$ 、$9 8 . 3 0 1 \%$ ;

北斗星B2频点遴选通带为1161MHz\~1165MHz、1221MHz\~1225MHz,其洁净率为 $9 8 . 3 1 5 \%$ 、 $9 8 . 3 3 5 \%$ ：北斗星B3频点遴选通带为1246MHz\~1250MHz、1291MHz\~1295MHz,其洁净率为 $9 8 . 2 2 4 \%$ 、 $9 7 . 6 5 0 \%$ ·GPSL2频点遴选通带为1221MHz\~1225MHz、1231MHz\~1235MHz，其洁净率为 $9 8 . 3 3 5 \%$ 、 $9 8 . 2 6 0 \%$ ，且所遴选出的通带的洁净率都大于 $9 5 \%$ 以上，符合太阳观测需求。

表4遴选通带洁净率  
Tab.4 Selection belt cleanlinessrate   

<html><body><table><tr><td rowspan="2">Beidou/GPS frequency point</td><td rowspan="2">Selection pass belt</td><td colspan="5">Cleanliness rate</td></tr><tr><td>East</td><td>South</td><td>West</td><td>North</td><td>average value</td></tr><tr><td>B1/L1</td><td>1551MHz~1555 MHz</td><td>98.367%</td><td>98.340%</td><td>98.245%</td><td>98.363%</td><td>98.329%</td></tr><tr><td></td><td>1596MHz~1600MHz</td><td>98.355%</td><td>98.335%</td><td>98.226%</td><td>98.286%</td><td>98.301%</td></tr><tr><td>B2</td><td>1161MHz~1165MHz</td><td>98.334%</td><td>98.194%</td><td>98.448%</td><td>98.283%</td><td>98.315%</td></tr><tr><td></td><td>1221MHz~1225MHz</td><td>98.330%</td><td>98.351%</td><td>98.296%</td><td>98.362%</td><td>98.335%</td></tr><tr><td>B3</td><td>1246MHz~1250MHz</td><td>98.321%</td><td>98.258%</td><td>98.313%</td><td>98.004%</td><td>98.224%</td></tr><tr><td></td><td>1291MHz~1295MHz</td><td>98.213%</td><td>98.069%</td><td>97.319%</td><td>96.998%</td><td>97.650%</td></tr><tr><td>L2</td><td>1231MHz~1235MHz</td><td>98.421%</td><td>98.350%</td><td>98.221%</td><td>98.046%</td><td>98.260%</td></tr></table></body></html>

# 3总结与展望

针对即将在云南天文台凤凰山本部建设的L波段的精密流量太阳射电望远镜，本文提出一种基于 SimpleThresholding算法与CUSUM算法的改进阈值算法，并对台址的L波段无线电测试和观测频段遴选出介于北斗 B1、B2、B3频点,GPSL1、L2频点之间7个5MHz无线电干扰较少的无线电通带,分别为1551MHz\~1555MHz、1596MHz\~1600MHz、1161MHz\~1165MHz、1221MHz\~1225MHz、1246MHz\~1250MHz、1291MHz\~1295MHz、1221MHz\~1225MHz、 $1 2 3 1 \mathrm { M H z } { \sim } 1 2 3 5 \mathrm { M H z }$ ，其洁净率分别为 $9 8 . 3 2 9 \%$ 、 $9 8 . 3 0 1 \%$ 、$9 8 . 3 1 5 \%$ 、 $9 8 . 3 3 5 \%$ 、 $9 8 . 2 2 4 \%$ 、 $9 7 . 6 5 0 \%$ 、 $9 8 . 3 3 5 \%$ 、 $9 8 . 2 6 0 \%$ ，均符合太阳观测需求。为下一步接收机的设计和信号处理提供了依据。

# Research on observable frequency band analysis of solar radio current in L-band based on Simple Thresholding and CUSUM joint

# algorithm

YANG Hang1 DONG Lang² HE Lesheng

(1.Yunna University，Kunming，Yunnan;2.YunnanAstronomicalObservatory，ChineseAcademyofSciences，Kunming，Yuan;)

Abstract: L-band solar radio burst is a potential influencing factor of navigation system instability,through the L-band precision solar current volume monitoring can be found in real time solar burst interference navigation events，for this reason Yunnan Astronomical Observatory headquarters intends to establish an L-band multi-frequency point solar radio monitoring system. An efective assssment of the radio environment is essential for the stable acces to observational data from the monitoring system. This paper introduces the radio monitoring readiness studyof the monitoring platform,and conducts a 1OO-hour test of the L-band radio environment n the Fenghuangshan area of the Headquarters of the Yunnan Astronomical Observatory. In this paper,an algorithm based on the improved threshold of Simple Thresholding algorithm and CUSUM algorithm is proposed,and 7radio passbands with less 5MHz radio interference between the Beidou B1,B2,B3 frequency points,GPS L1 and L2 frequency points are selected，namely 1551MHz\~1555 MHz, $1 5 9 6 \mathrm { M H z } { \sim } 1 6 0 0 \mathrm { M H z }$ ， $1 1 6 1 \mathrm { M H z } { \sim } 1 1 6 5 \mathrm { M H z }$ 1221MHz\~1225MHz， respectively. $1 2 4 6 \mathrm { M H z } { \sim } 1 2 5 0 \mathrm { M H z }$ ，1291MHz\~1295MHz，1231MHz\~1235MHz，its cleanliness rates are $9 8 . 3 2 9 \%$ ， $9 8 . 3 0 1 \%$ ， $9 8 . 3 1 5 \%$ ， $9 8 . 3 3 5 \%$ ， $9 8 . 2 2 4 \%$ ， $9 7 . 6 5 0 \%$ ， $9 8 . 2 6 0 \%$ , all of which meet the needs of solar observation. It provides a basis for the next step of receiver design and signal processing.

Key words: L-band; monitoring systems; radio environment; threshold; cleanliness rates

# 参考文献：

[1]宋丽敏，张军，杨志良，汪毓明，汪景绣.对地日冕物质抛射研究[J].天文学进展,2002(01):33-44. SONG L, ZHANG J, YANG Z L, WANG Y M, WANG JX. Study on coronal mass ejection from the Earth[J]. Progress in Astronomy, 2002(01):33-44.   
[2]王林萍，王华宁，黄鑫.日冕物质抛射的偏转特性研究[J].天文研究与技术，2016, 13(02):143-149.DOI:10.14005/j.cnki.issn1672-7673.20150928.010. Wang L P, Wang H N,Huang X. Deflection characteristics of coronal mass ejection[J]. Astronomica 1Research & Technology， 2016, 13(02):143-149.DO1:10.14005/j.cnki.issn1672-7673.20150928.010.   
[3]Louise K.Hara.Transequatorial Filament Eruption and Its Link toa Coronal MassEjection[J].Chinese Journal of Astronomy and Astrophysics, 2006(02):247-259.   
[4]周桂萍，曹卓良，汪景琇.日冕物质抛射和太阳表面磁活动的关系[J].天文学进展，2003(01):41-54. Zhou G P, Cao Z L，Wang J X. The relationship between coronal mass ejection and magnetic activit y on the surface of the Sun[J].Progress in Astronomy， 2O03(O1):41-54.   
[5]邵承文．日冕物质抛射(CME)的射电研究[D].中国科学院研究生院(云南天文台),2005．Shao CG.Rad io research on coronal mass ejection (CME)[DJ.Graduate School of Chinese Academy of Sciences （Yu nnan Astronomical Observatory)， 2005.   
[6]戴宏．AGN 的多波段性质与演化研究[D].中国科学院研究生院(云南天文台)，2006. Dai H.Multi-band properties and evolution of AGN[D].Graduate School of Chinese Academy of Scie nces (Yunnan Astronomical Observatory)， 2006.   
[7] 李富婷，张雄，张皓晶，余莲，徐小林，任国伟，吴月承．AGN 吸积盘辐射区半径的多方法研究[J].天文 研究与技术，2019，16(04):381-389.DOI:10.14005/j.cnki.issn1672-7673.20190426.003. Li F T, Zhang X, Zhang H J, Yu L, Xu X L, Ren G W,Wu Y C. Multi-method study on the radiu S of the radiation region of the AGN accretion disk[J].Astronomical Research & Technology,2019,16 (04):381-389.DOI:10.14005/j.cnki.issn1672-7673.20190426.003.   
[8]Klobuchar,J.A.,J.M. Kunches,and A.J.Van Dierendonck (1999),Eye on the ionosphere: Potentia 1 solar radio burst effects on GPS signal to noise,GPS Solut.，3(2)，69-71.   
[9]Bala,B.,L.J.Lanzeroti, D.E. Gary，and D.J. Thomson (2O02)，Noise in wireless systems produce d by solar radio bursts，Radio Sci.，37(2)，2018,doi:10.1029/2001RS002481.   
[10] Chen，Z.，Y. Gao,and Z.Liu (2O05)，Evaluation of solar radio bursts'efect on GPS receiver signal t racking within International GPS Service network，Radio Sci.，40,RS3012，doi:10.1029/2004RS00306 6.   
[11] 董亮 博士论文"太阳射电爆发对无线通信影响、评估及预警平台建立关键技术的研究"[D].2016. Dong L，Ph.D. thesis,"Research on the Impact of Solar Radio Bursts on Wireless Communication，E valuation and Establishment of Key Technologies for Early Warning Platforms"[D]. 2016.   
[12]董亮，闫小娟，黄文耿等.“太阳射电爆发对不同波段无线电信号影响分析”2018，全国第三十五届 气象年会文集. Dong L，Yan X J， Huang W G, et al.， "Analysis of the Impact of Solar Radio Bursts on Radio Sign als in Diferent Wavelength Bands"，Proceedings of the 35th National Meteorological Annual Conferen ce，2018.   
[13]董亮，闫小娟，黄文耿等．“2015年11月4日太阳射电爆发干扰导航信号事件中的X射线先兆分 析”[]．天文研究与技术．2021，18(03):294-300. Dong Liang，Yan Xiaojuan, Huang Wengeng,et al., "X-ray aura analysis in solar radio burst interfere nce navigation signal event on November 4，2015"[J]. Astronomical Research & Technology. 2021，18 (03):294-300.   
[14] Li F T, Zhang X, Zhang H J, Yu L, Xu X L,Ren G W, Wu Y C. Multi-method study on the radiu S of the radiation region of the AGN accretion disk[J].Astronomical Research & Technology,2019,16 (04):381-389.DOI:10.14005/j.cnki.issn1672-7673.20190426.003.   
[15] Rauscher C.Fundamentals of spectrum analysis [EB/OL]. 2001 [2013-11-16].htp://www.rohde-schwarz. com.   
[16]袁惠仁.小型天线增益的射电天文测量[J].无线电工程，1992(04):50-53. Yuan H R.Radio Astronomy Measurement of Small Antenna Gain[J].Radio Engineering，1992(04):50-5 3.   
[17] 袁惠仁.射电天文测量微波天线增益的测量技术[J]．天文研究与技术，1995(02):26-35. Yuan H R. Measurement technology of radio astronomy to measure the gain of microwave antenna[J]. Astronomical Research & Technology， 1995(02):26-35.   
[18] 李剑，宋文明，崔恒乐，张自潘，李文鹏.北斗三号与GPS 组合实时动态精密单点定位精度分析[J/OL].工 程勘察:1-9[2022-07-07].htp://kns.cnki.net/kcms/detail/11.2025.TU.20220616.2016.002.html. LI J, SONG W M, CUI H L, ZHANG Z P, LI W P. Real-time dynamic precision single-point positi oning accuracy analysis of Beidou-3 and GPS combination[J/OL].Engineering survey:1-9[2022-07-07].ht tp://kns.cnki.net/kcms/detail/11.2025.TU.20220616.2016.002.html.   
[19] 傅圣友，李圣明，王兆瑞.基于CAPS，BDS 和GPS 的组合卫星定位精度分析[J].天文研究与技术，2018, 15(04):397-403.DO1:10.14005/j.cnki.issn1672-7673.20180426.013. Fu S Y,Li S M, Wang Z R. Accuracy analysis of combined satellite positioning based on CAPS，B DS and GPS[J].Astronomical Research & Technology,2018,15(04):397-403.DOI:10.14005/j.cnki.issn167 2-7673.20180426.013.   
[20] 李佳威，李芳，何瑞珠.利用GPS 测速估算接收机载体运动方位角[J].天文研究与技术，2017，14(01):45- 51.DOI:10.14005/j.cnki.issn1672-7673.20160608.003. Li J W,Li F, He R Z.Estimation of receiver carrier motion azimuth using GPS speed measurement[J]. Astronomical Research & Technology,2017,14(01):45-51.DOI:10.14005/j.cnki.issn1672-7673.20160608.0 03.   
[21] 卢伟俊，万庆涛，范江涛，张杰，王晓岚.北斗/GPS 双频静态伪距单点定位结果对比分析[J].天文研究与 技术，2016，13(04):433-440.DOI:10.14005/j.cnki.issn1672-7673.20160316.005. Lu W J，Wan Q T,Fan J T, Zhang J，Wang X L. Comparative analysis of Beidou/GPS dual-band st atic pseudo-distance single-point positioning results[J].Astronomical Research & Technology,2016,13(0 4):433-440.DOI:10.14005/j.cnki.issn1672-7673.20160316.005.   
[22] Baan W A, Fridman P A，Millenaar R P. AJ,20O4,128:933.   
[23] Schoemaker L. Removing Radio Frequency Interference in the LOFAR Using GPUs.Amsterdam: Vrij e Universiteit Amsterdam，2015:5-18.   
[24] Offfringa A R,de Bruyn A G,Biehl M,et al. MNRAS,2010,405: 155.   
[25]Fridman P,et al. Statistically Stable Estimates of Variance in Radioastronomical Observationsas Tools for RFI Mitigation. The Astronomical Journal, 2008:04-10.