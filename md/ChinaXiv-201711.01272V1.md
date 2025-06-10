# MUSER可见度数据积分方法与实现

赖铖1，梅盈1²，邓辉1，王锋1²，戴伟¹(1.昆明理工大学云南省计算机技术应用重点实验室，云南 昆明 650500；2.中国科学院云南天文台，云南 昆明 650011)

摘要：射电观测是研究太阳活动的重要探测手段。我国明安图频谱射电日像仪（MingantU SpEctralRadioheliograph,MUSER）主要用以研究太阳爆发活动初始能量释放区的物理过程，其观测将在太阳射电成像开辟一个新的窗口。成像处理是MUSER数据处理的重要组成部分，如何提高成像质量是当前数据处理的研究重点。首先介绍了射电干涉成像的基本理论，随后分析了对MUSER观测得到的可见度数据积分的必要性，细致讨论了短时段可见度数据叠加求平均和长时段UV覆盖叠加两种积分方法，并给出了完整的实现。通过实验验证的方法与实现的正确性，两种积分均可以有效提高信噪比，图像质量明显提高。

关键词：MUSER；UV平均积分；UV覆盖积分；综合孔径成像中图分类号：TP274 文献标识码：A 文章编号：1676-7673

射电天文学是一个天文学分支，它使用射电望远镜系统在无线电波段研究来自深空（包括各类天体）的射电波。为推动射电观测技术的发展，填补国际上对太阳耀斑能量初始释放区分米波段高分辨射电成像观测的空白[2-3]，我国天文学家已建设在0.4\~15GHz 范围内的厘米-分米波日像仪—明安图频谱射电日像仪（MingantU SpEctral Radioheliograph，MUSER）。它可以在超宽频带下同时以高时间、高空间和高频率分辨率观测太阳动力学性质，探索太阳剧烈活动起源[4]。

MUSER天线阵包含低频阵(MUSER-I)和高频阵（MUSER-II)。MUSER-I，共有40面4.5m天线，观测频率为400MHz-2GHz。MUSER-I的观测分为4个波段，两种极化方式（左旋、右旋)，其中每个波段包含16个通道。MUSER-II，共60面2m天线，观测频率范围为2GHz-15GHz，在33个波段和两种极化方式上观测，每个波段包含16个通道[5。MUSER高频和低频阵均以每3ms 的速率产生一帧观测数据（一个波段，一个极化方向上的16个通道数据)。如何从原始观测的可见度数据经过一系列校准和计算得到科学研究用太阳图像，是MUSER科学数据处理的关键。

目前，国外用于太阳射电成像观测的设备主要有日本野边山的太阳射电日像仪,积分时间为 25ms[],法国南茜米波太阳射电日像仪积分时间1s⑪,西伯利亚太阳射电日像仪积分时间0.336s[7]。这些射电日像仪积分处理过程一般直接在接收机完成，因此时间分辨率较低。我国位于内蒙古明安图观测站的明安图频谱射电日像仪已经建成，满足实时和事后科学数据处理的软件已开发完成[8-9]。为进一步提高成图质量，本文通过对成图基本原理的分析，进一步提出基于UV平均积分和UV覆盖积分两种积分方法提高太阳图像的信噪比。

# 1MUSER成像原理

# 1.1综合孔径成像原理

相关干涉仪是将间隔一定距离的两面天线接收的天体辐射分别传送到相关器中进行相关处理。由干涉仪成像原理可知，干涉仪的输出响应和天空亮度存在傅里叶变换关系，假设天空亮度分布为 $I ( l , m )$ ，干涉仪输出为 $V ( u , \nu )$ ，则有如下关系[10]：

$$
V ( u , \nu ) = \sum \sum I ( l , m ) \mathrm { e } ^ { i 2 \pi ( u l + \nu m ) } \qquad .
$$

将离散求和转换成连续积分可以得出如下公式[10]:

$$
V ( u , \nu ) = \int \int I ( l , m ) \mathrm { e } ^ { i 2 \pi ( u l + \nu m ) } d l d m
$$

其中, $u , \nu$ 为投影平面也称作空间频率; $l , m$ 为平时的天空面。（2）式表明干涉仪的输出是亮度分布傅里叶变换的一个 $( u , \nu )$ 分量，随着 $u , \nu$ 的不同可以得到不同空间频率分量的值，所有的空间频率分量总称复可见度函数。对复可见度函数进行傅里叶逆变换就能得到天空亮度分布即图像，这被称为综合孔径成像原理[10。

对于任意一个亮度分布 ${ \cal { I } } ( l , m )$ ，总有一个复可见度函数 $V ( u , \nu )$ 与之相对应。复可见度函数是连续的复函数，而天线阵只能构成有限条基线，即只能获得复可见度函数的有限个采样点。采样函数 $S ( u , \nu ) = \sum _ { k } \delta ( u - u _ { k } , \nu - \nu _ { k } )$ ，其中， $k$ 为取遍所有 $( u , \nu )$ 的点。采样函数的输出即为天线得到的真正数据，对这些数据进行傅里叶逆变换就得到脏图 $I _ { D } ( l , m ) ^ { \ : [ 1 ] }$ ：

$$
I _ { _ { D } } ( l , m ) = \int \int S ( u , \nu ) V ( u , \nu ) e ^ { - 2 i \pi ( u l + \nu m ) } d u d \nu
$$

# 1.2MUSER积分基本原理

当前的MUSER数据处理系统流水线已完成从原始观测数据格式到FITS文件格式的转换，观测数据校准，到脏图以及洁化的成图过程8。以高频阵在2016年7月5日4时4分38 秒的观测数据为例，生成的脏图（图1（a)）和洁化图（图1（b)）。

![](images/8a9cd7dc8d4a4eb85ec15f6d2a19e0cdc153072258ce156893bb0309986b3ed7.jpg)  
图1MUSER原始脏图(a)和洁化图(b) Fig.1 Dirty and clean image without integration(MUSER-I,2016-07-05 04:04:38(UTC))

可以看出，对单帧采样数据成像后的太阳图像信噪比很低，不能清楚地看出太阳爆发的位置及其轮廓。脏图洁化后得到的洁图，同样也不能清楚地分析出爆发位置。为达到MUSER重建的太阳图像信噪比提升，得到质量较好的成像结果需要对采样数据进行积分处理改善图像质量提高信噪比[12。本文根据实际科学研究需要，以及积分时段要求从两方面分析，研究了UV平均积分（可见度数据求和再求平均）、UV覆盖积分（利用地球自转增加UV覆盖）两种方法。

# 1.2.1基于UV平均的积分

MUSER 选择观测模式为快照模式，积分时间为3ms进行观测。如此高的时间分辨率情况下，为了提高空间分辨率达到改善图像质量的效果，采取对3ms 观测得到的UV及其输出数据平均的方法实现。

以 MUSER-II为例，其中单帧积分采样时间 $t _ { c }$ ，假设对UV积分时间为 $t _ { \scriptscriptstyle I }$ 单帧采样函数$S ( u , \nu )$ ，采样输出为 $V ( u , \nu )$ ，则UV积分表示如下：

采样函数： ${ S } _ { t _ { I } } \left( u , \nu \right) = \sum _ { i = 1 } ^ { N } S _ { t _ { i } } \left( u _ { i } , \nu _ { i } \right)$ $( N = \frac { t _ { I } } { t _ { c } } )$ 采样输出： $V _ { t _ { I } } \left( u , \nu \right) = \sum _ { i = 1 } ^ { N } V _ { t _ { i } } \left( u _ { i } , \nu _ { i } \right)$ （204 （204号 $( N = \frac { t _ { I } } { t _ { c } } )$

UV平均脏图： $I _ { _ { D } } ( l , m ) = \int \int [ \frac { S _ { t _ { l } } ( u , \nu ) } { N } ] [ \frac { V _ { _ { t _ { l } } } ( u , \nu ) } { N } ] e ^ { - 2 i \pi ( u l + \nu m ) } d u d \nu \qquad ( N = \frac { t _ { _ { I } } } { t _ { . } } )$

(4）式做法即将采样的复可见函数进行平均，同时采样函数也进行平均，用平均采样函数和复可见度函数的方法实现UV平均积分。

# 1.2.2基于UV覆盖增加的积分

UV覆盖对成图起至关重要的作用，由于采样函数 $S ( u , \nu )$ 的傅里叶变换即得到脏束也称综合束，而脏束又直接影响成图，因此可通过增加UV覆盖提高图像质量。增加UV 覆盖有3 种方式，增加阵列望远镜个数、增加子孔径有效半径、利用地球自转[12]。增加阵列望远镜个数对成本有直接需求，在成本固定的情况下不考虑，增加子孔径有效半径可能导致采样率不足。在现有成本下增加UV覆盖通过地球自转是一个非常直接可行的方法。

随着地球自转UV 会发生改变，而短时间内UV 的变化很小，因此假设每间隔 $t _ { \mathrm { i n t } e r \nu a l }$ 增加UV覆盖，总积分时间 $t _ { a }$ ，则增加UV覆盖后的采样函数和采样输出表示为

$S _ { t _ { J } } \left( u , \nu \right) = \sum _ { J = 1 } ^ { N } S _ { t _ { j } } \left( u _ { j } , \nu _ { j } \right) \qquad \quad ( N = \frac { t _ { a } } { t _ { \mathrm { i n t } e r \nu a l } } )$ $V _ { _ { I _ { J } } } ( u , \nu ) = \sum _ { j = 1 } ^ { N } V _ { _ { t _ { j } } } ( u _ { j } , \nu _ { j } ) \qquad ( N = { \frac { t _ { a } } { t _ { _ { \mathrm { i n t e r } \nu a l } } } } )$ UV 覆盖增加脏图： $I _ { _ { D } } ( l , m ) = \int \int S _ { t _ { J } } ( u , \nu ) V _ { t _ { J } } ( u , \nu ) e ^ { - 2 i \pi ( u l + \nu m ) } d u d \nu$ （20

由（5）式可知，在间隔 $t _ { \mathrm { i n t } e r \nu a l }$ 增加UV覆盖，总积分时间 $t _ { a }$ 的情况下可以增加 $\frac { t _ { a } } { t _ { \mathrm { i n t } e r v a l } }$ 倍的UV数据点，假设有 $n$ 面天线构成的天线阵列，可以得到 $n ( n - 1 ) / 2$ 个数据采样点，通过增加UV 覆盖，采样数据点总共有 $( \frac { t _ { a } } { t _ { \mathrm { i n t } e r v a l } } ) ( \frac { n ( n + 1 ) } { 2 } )$ 个，这对稀疏采样的成图质量有很大改善。

上述两种方式均可以提高成图的质量，将两种方法混合到一起同样可以提升图像质量，由此提出先进行UV平均积分再增加UV覆盖积分的方法。

# 1.2.3基于UV平均和增加覆盖的混合积分

假设UV 积分时间为 $t _ { \scriptscriptstyle I }$ ，可以知道在该段时间内的采样函数为 $S _ { t _ { I } } ( u _ { i } , \nu _ { i } )$ ，采样输出$V _ { t _ { I } } ( u _ { i } , \nu _ { i } )$ ，每间隔 $t _ { \mathrm { i n t } e r \nu a l }$ 增加UV 覆盖，总积分时间 $t _ { a }$ ，混合积分采样函数及其采样输出可以表示为

采样函数： $\begin{array} { l l } { \displaystyle S _ { m i x } ( u , \nu ) = \sum _ { j = 1 } ^ { N } \frac { \displaystyle \sum _ { i = 1 } ^ { M } S _ { t _ { i j } } ( u _ { i j } , \nu _ { i j } ) } { M } \qquad } & { ( M = \frac { t _ { I } } { t _ { c } } , N = \frac { t _ { a } } { t _ { \mathrm { i n t e r v a l } } } ) } \\ { \displaystyle V _ { m i x } ( u , \nu ) = \sum _ { j = 1 } ^ { N } \frac { \displaystyle \sum _ { i = 1 } ^ { M } V _ { t _ { i j } } ( u _ { i j } , \nu _ { i j } ) } { M } \qquad } & { ( M = \frac { t _ { I } } { t _ { c } } , N = \frac { t _ { a } } { t _ { \mathrm { i n t e r v a l } } } ) } \end{array}$ 采样输出： 脏图： $I _ { _ { D } } ( l , m ) = \int \int S _ { _ { m i x } } ( u , \nu ) V _ { _ { m i x } } ( u , \nu ) e ^ { - 2 i \pi ( u l + \nu m ) } d u d \nu$ （20

在总时间 $t _ { a }$ 内UV覆盖增加了 $\frac { t _ { a } } { t _ { \mathrm { i n t } e r v a l } }$ 倍，每组增加的UV覆盖是在时间段 $t _ { \scriptscriptstyle I }$ 对UV平均后再叠加的覆盖。

# 2MUSER积分过程实现

MUSER成图过程：目标源放射出天体辐射干涉仪对其进行采样，采样得到的原始数据经过预处理相关校准[13]、对应极化和通道，之后进行积分处理，再网格化傅里叶逆变换得到

脏图，最后经过洁化算法处理得到洁图，过程如图2。

![](images/4519234c8dae5a69207ecdf7bcb1781be083926d6dae502ac3e40a4746ec11e9.jpg)  
图2MUSER积分成图过程 Fig.2TheprocedureofMUSERintegration

# 2.1积分操作流程

MUSER每3ms 接收一帧观测数据，对这些数据进行积分操作得到积分数据，积分数据是观测得到并且经过预处理相关校准、对应极化和通道的可见度数据。UV平均积分具体操作流程如图3。

![](images/fd45ec4ad95536cb9de492296a88a30811207376fc9a27af83f4bdb76459fc2e.jpg)  
Fig.3 Calculation of the average of visibilities

MUSER-II中每一帧完整的数据包含33小帧。UV积分对连续的每一帧数据中UU，VV以及采样得到的实部虚部数据进行累加再求平均，得到的UV平均积分数据量和单帧大小数量一样多，例如在MUSER-II中采样函数UV点为3540个采样得到的实部虚部 3540个，则经过UV平均积分得到的数据同样是3540个UV点及其采样值。

![](images/c2370a18c047a81749b7e6cab7ede366c32ec1bcc89a26079ab2fc4f873cd35f.jpg)  
图3可见度数据平均的计算  
图4UV覆盖积分流程  
Fig.4Procedure of UV coverage overlap

实现UV覆盖积分采取具体操作流程如图4。对MUSER-II中数据进行UV覆盖积分同样用完整的数据帧积分，不同的是由于在短时间采样函数及其采样值都变化很小如果用连续的帧增加UV覆盖显然效果不好，为此需要隔一段时间去增加UV覆盖。UV覆盖积分得到的是一段时间间隔完整数据帧叠加的数据，同样对数据UU，VV及其采样值操作得到的数据量成倍增加，这种操作能极大改善稀疏采样下图像的质量，提高信噪比。

以积分一小时数据为例，积分后增加UV覆盖采样数据成倍增加，对稀疏采样提高图像质量及其信噪比起至关重要的作用。MUSER-II单帧的UV覆盖所包含数据点1770个，共轭之后有3540个数据，得到一张 $2 5 6 0 \times 2 5 6 0$ 像素大小的图像，覆盖率仅仅 $0 . 0 5 4 \%$ 。而对数据总共积分1小时间隔10min叠加UV覆盖后共有10620个数据点，共轭之后数据点21240个，覆盖率提升为 $0 . 3 2 4 \%$ 。选取60ms采样数据进行平均，之后每隔10min增加UV覆盖，得到的UV覆盖图像如图5、图6。

![](images/680e58c9f6949956a020584569db76b043dea2fc6de929983cdc78593f206a51.jpg)  
图53毫秒单帧UV覆盖 Fig.5UVCoverageforasingle frame (3 ms)   
图7MUSER系统运行积分命令

![](images/b08d62aad821adfd4a884931e727a5891e5a1a273c121b6a65fc97fbc06628cb.jpg)  
图61小时积分UV覆盖Fig.6UV Coverage for1hour'sintegration

# 2.2积分代码实现

为了实现UV平均积分、UV覆盖积分以及UV平均积分和UV覆盖积分混合积分，采用 Python 编写，同时为了简化程序将3种模式的积分写入一个接口提供模式的选择，程序接口形式如下：

def clean_integration_R(self, sub_ARRAY,is_loop_mode,start_time,end_time, TASK_TYPE, time_average, time_interval, BAND,CHANNEL,PLOT_ME,WRITE_

主要参数介绍:sub_ARRAY为MUSER 期数的选择MUSER-I或者MUSER-II,start_time和 end_time为积分操作开始积分时间和结束积分时间，TASK_TYPE即为积分模式的选择包含UV平均积分、UV覆盖积分、UV平均积分和UV覆盖积分混合的一种积分模式，time_average 为UV平均积分的积分时间，time_interval是UV覆盖积分时间间隔也即间隔多长时间去叠加一次UV覆盖。在MUSER系统运行情况如图。

<html><body><table><tr><td>Muser<l>: inp integrationuvfits</td><td colspan="4"></td></tr><tr><td></td><td colspan="4">> inp(integrationuvfits)</td></tr><tr><td></td><td>#integrationuvfits :: Integration FITS file for MUSER</td><td></td><td></td><td></td></tr><tr><td>subarray</td><td>=</td><td>1</td><td>#</td><td>MUSER I or II (1，2)</td></tr><tr><td>is_loop_mode</td><td>=</td><td>True</td><td>#</td><td>LOOP Mode or not(True，False)</td></tr><tr><td>start_time</td><td>=</td><td>=</td><td>#</td><td>start time (start_time = "2016-07-05</td></tr><tr><td rowspan="2">end_time</td><td rowspan="2">=</td><td rowspan="2"></td><td># 12:04:38 463")</td><td></td></tr><tr><td>#</td><td>end time (end_time = "2016-07-05</td></tr><tr><td rowspan="3">task_type</td><td rowspan="3">=</td><td rowspan="3"></td><td>#</td><td>12:30:00")</td></tr><tr><td>#</td><td>task type: average，interval or</td></tr><tr><td></td><td># mixture</td></tr><tr><td>time_average</td><td>=</td><td></td><td>#</td><td>time span of average computing</td></tr><tr><td>time_interval</td><td>=</td><td>None</td><td>#</td><td>time_interval</td></tr><tr><td rowspan="2">debug</td><td rowspan="2">=</td><td rowspan="2">0</td><td>#</td><td>Display increasingly verbose debug</td></tr><tr><td>#</td><td>messages (0，1)</td></tr></table></body></html>

Fig7Integration task in MUSER data processing System代码编写可以适用于采集到数据的任何时间段积分模式。

# 3实验分析

积分实例，以混合积分模式为例，进行10min、20min、30 min、40min、50 min 以及1h 的数据做积分处理，对60ms 的数据进行UV平均积分，之后每隔 $1 0 \mathrm { m i n }$ 增加UV覆盖。脏图结果如图8。

![](images/b675a9fe86c2df47e4ceacb0970fc4c6e74dcb01e776f454899cc2e54c6c1647.jpg)  
Fig.8Dirty images of mixed integration

图8 从左到右从上到下分别为积分10，20，30,,60 min之后的脏图，可以很明显f看出从第1张图太阳轮廓到最后一张太阳轮廓略稍清晰。随着积分时间的增加得到的脏图质量越来越好，图像越来越清晰，同时可以清楚地看到太阳的轮廓（图中间类似圆形）以及太阳爆发的亮点位置，很明显积分达到提升图像质量的效果。经过洁化处理得到的洁图如图9。

![](images/6476be0ecae6f36e9d69508ec315998ba26c86706a0fd849a817f652e7eda732.jpg)  
图8混合积分脏图  
图9混合积分洁图Fig.9 Clean images of mixed integration

图9 从左到右从上到下分别为积分10，20，30，，60min之后的洁图，可以很明显地看出，随着积分时间的增加，得到的洁化后图像越来越清晰，同时可以清楚地看到太阳的轮廓以及太阳爆发的位置亮点，从一开始爆发亮点多处到最后一张只有一处非常明显的爆发点，信噪比有很大提升。

图10为2016年7月5日04:04:38UT，射电日像仪高频阵MUSER-II在4.1878GHz上用1小时积分时间观测得到的太阳射电图像结果。与日本野边山射电日像仪 2016年7月5日

04:00:02UT在17GHz上观测得到的太阳图像比较，MUSER-II得到的太阳像与野边山观测得到的太阳像结果基本一致，可见MUSER 积分方法与实现结果是比较可靠的。

![](images/ae9a1142fa5b266284623be652ee9c8212cc414b2f637977c1ab5d4986c8483f.jpg)  
图 10（a）MUSER-II1 小时积分的太阳像（b）野边山射电日像仪观测的太阳像rig.10 (a)One huor's integration solar images of MUSER-I (b)Solar observation images of the Nobeyama Radioheliograp

# 4结论

通过对采样数据积分处理，以每60msUV积分和间隔 $1 0 \ \mathrm { m i n }$ 增加UV覆盖混合积分方法为例可以看出成图效果非常明显，经过一系列数据处理计算得到的脏图可以清楚地看出太阳边缘轮廓及其爆发位置，信噪比有了很大提升。并且随着积分时间的增加得到的图像质量也有所提升。这一积分思路对于获得质量较优的MUSER 观测结果有较好的作用。目前图像处理结果得到很大提升但在成图前需要读取UVFITS数据文件，当前的UVFITS文件生成时间上较慢急需加快生成UVFITS 时间效率。后续积分工作可以在积分时间上进行探索，利用评价指标寻找如何积分才能达到相对比较好的效果，给出UV积分时长、UV覆盖积分时间间隔长度以及总共积分多长时间这些参数的量化值。

# 参考文献

[1］向德琳．射电天文观测[J]．北京：科学出版社,1990.   
[2]GaryDE,KellrCU.Solarand space weatherradiophysics -current statusand future developments[M].Netherland: Kluwer Academic Publishers,2004.   
[3]Wang W,YanY,LiuD,etal.CalibrationandDataProcessingforaChinese SpectralRadioheliographintheDecimeterWave Range[J].Publications of the Astronomical Society of Japan,2O13,65(spl):2226-2237.   
[4]颜毅华，张坚，陈志军,等．关于太阳厘米-分米波段频谱日像仪研究进展[J]．天文研究与技术-国家天文台台刊，2006， 3(2):91-98.   
YanYihua,ZhangJan,ChenZjun,etal.ProgressoChinesesolarradioheliographin-dmwavebandes[J].stronomicaleearh & Technology- -publications of National Astronomical Observatories of China,2Oo6,3(2):91-98   
[5]梅盈．MUSER 海量数据预处理关键技术研究[D]．昆明：昆明理工大学，2015.   
[6]NakajimaH,NishioM,Enome S,etal.The Nobeyamaradioheliograph[J].Procedingsofthe IEEE,1994,82(5):705-713. [7]GrechevsooiSooGYtaleaolardoleoeeurtatefestrunts and data[J]. Solar Physics,2003,216(1-2):239-272.   
[8]WangF,MiYDngH,etal.istrbutddata-procesingpipeeforingantuUraideSectraladiohelograh[J].ublatio of the Astronomical Society of the Pacific,2015,127(950):383-396.   
[9]WeiS,WangF,DengH,etal.OpenCluster:aflexibledistributedcomputingframework forastronomicaldataprocessing[J]. Publications of the Astronomical Society of the Pacific,2016,129(972):1-14.   
[10]ThompsoAR,oranJM,SwesonJrGW.nteferometrydsythsisinadioastroomyM.Berlin:Sringer,648-648. [11]罗洪礼．MUSER 成像中的Grid 技术研究与实现[D]．昆明：昆明理工大学，2016.   
[12]Ségransan D.Observability and UVcoverage[J].New Astronomy Reviews,2OO3,51(8-9):597-603.   
[13]MeiY,LiuDWangF,tal.TedatafatpreproesgsteforsesectraladohegaphJ].ICExpet, PartB:Applications,2015,6(5): 1467-1472.

# Integral Method and Implementation of MUSER Visibility Data

Lai Cheng1,Mei Ying1,2,Deng Hui1,Wang Feng1.2,Dai Weil (1.KeyLaboratoryofApplicationsofComputerTechnologyof theYunnanProvince,UniversityofcienceandTechnologyofKunming, Kunming 6505oo,China; 2.Yunnan Observatories,Chinese Academy of Science,Kunming 650011,China)

Abstract: Radio observations is the most important detection means to research the solar activity. The MingantU SpEctral Radioheliograph(MUSER) is mainly used to research the initial energy release physics process of the solar activity and it's observation will open a new window in solar radio imaging. Imaging processing is an important part of MUSER data processing and improving the image quality is the most important research of data processing. Firstly, we introduces the basic theory of radio interference imaging. Secondly, we analyzed the necessty of visibility data integration obtained from the MUSER observations.Then,we discuss in detail the two kinds of integration method which are short-term visibility data superimposed averaging and long-term UV overlay stacking and gives a complete realization. Through the method of verification and the validity of completion， the two kind of integration method can effectively improve the signal-to-noise ratio and the quality of images.

Key words: MUSER;UV integration; UV coverage integration; aperture synthesis imaging