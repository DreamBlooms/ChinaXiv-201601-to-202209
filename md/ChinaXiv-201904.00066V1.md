# 基于自适应双阈值的计步算法

王岚，彭敏，周清峰(合肥工业大学 计算机与信息学院，合肥 230009)

摘要：针对现有计步算法对不同运动状态适应性差的问题，设计了一种基于自适应阈值的计步算法。该算法首先通过智能手环的内置三轴加速度传感器采集用户在慢走、快走以及跑步三种步行频率的加速度数据，经过五点滤波预处理，在自适应时间窗内检测波峰波谷，再将波峰均值和波谷均值的平均值作为上阈值，波谷均值作为下阈值，通过动态阈值判定步数，最后根据行走振幅和行走频率存在的规律性进行假步检测。测试表明，该算法对于不同的用户在三种不同频率下平均计步精度可以达到 $91 . 8 8 \%$ 以上。

关键词：自适应；加速度传感器；动态阈值；计步精度 中图分类号：TP301.6 doi: 10.19734/j.issn.1001-3695.2018.11.0793

Pedometer method based on self-adaptive double threshold algorithm

Wang Lan, Peng Min†, Zhou Qingfeng (SchoolofComputer Science&Information Engineering,Hefei UniversityofTechnology,Hefei 2309,China)

Abstract:To solvethe problem that the existing stepcounting algorithms have poor adaptabilityto diferent motion states, this paper proposed a stepcounting algorithmbased on self-adaptive threshold.Byusing the 3-axis accelerometer sensor in smart bracelet，the proposed algorithm frst performed the aceleration data collction when users walked at three frequencies including slow walking,fast walking and runing.After five-pointflter preprocessng,this algorithm detected peaks and valeys in the self-adaptive time window.Then it taken the average of the peak mean and valey mean as the upper threshold,andused the valley mean as the lower threshold.Basedonthis,thealgorithm adopted adynamic threshold analysis toachieve thestepcounting.Finall,inthisalgorithm,false stepscouldalsobedetectedaccordingtotheregularity of walking amplitude and frequency.The test shows that the achievable average step counting accuracy of the proposed algorithm is above $91 . 8 8 \%$ for different users at three different walking frequencies.

Key words: self-adaptive; accelerometer sensor; dynamic threshold; step counting accuracy

# 0 引言

近年来，随着人们越来越注重身体健康问题，健身日益受到关注。由于步检测和计数可以为个体的身体活动水平提供基本的衡量[I]，使得利用智能手环等可穿戴式智能设备来进行计步和获取其他生理数据成为了研究热点。目前，智能手环的种类繁多，计步方法也多种多样。当前计步算法均是基于加速度传感器展开的。文献[2]提出了自相关分析法，通过计算自相关系数和标准差，设置经验阈值来判断空闲和行走的状态，但是该算法未统计当人变速运动导致每步周期发生变化时的计步效果。文献[3]提出一种基于加分减分策略的计步算法，在固定时间窗内比较相邻两个采样点幅值的大小，通过比较得到的关系来统计分数，当分数达到一定要求，则计为1步；但当人物步频变化时，采用固定时间窗往往不能精确计步[4]。文献[5]介绍了一种自适应的波峰检测算法，在正常态和非正常态时计步准确度可以达到 $9 9 \%$ 以上，但是并未统计算法对不同用户行走特征的适应性。根据阈值判定来进行计步是目前常见的一种计步方法，通过给用户系上一个惯性传感器，当测得的加速度传感器数据超过阈值，用户的步数将会增加一步[6-8]。文献[9]提出先求出动态峰值和谷值之差，再将结果和固定阈值比较来判断步数是否增加。但由于每个人的运动状态不同，步幅的差别会比较大，所以该算法存在的缺陷在于对不同运动状态没有普适性。虽然基于阈值的计步方法适用性是很强的，但是对目前而言，还是很难确定一个统一的阈值来适应不同的用户和多样的行走状态[10]。

针对现有算法对不同运动状态适应性差和无法适应不同用户行走特征的问题，设计了一种基于自适应双阈值的计步算法。该算法先将采集到的加速度数据进行符号统一化，经过五点滤波法对加速度数据进行预处理操作，接着在自适应时间窗内根据波峰波谷的值分别计算上阈值和下阈值，再通过动态阈值来判定步数，最后根据行走振幅和行走频率存在的规律性进行假步检测，可以准确地排除非行走因素 (起立、坐下、打字、敲桌子等)对正常步数的干扰，旨在提高计步算法对不同运动状态以及不同用户行走特征的适应性。实验结果表明，本算法在不同用户的慢走、快走、跑步等状态下都能获得较高的计步精度。

# 1人体行走模型与步数检测算法

人体在行走过程中，手臂在一定方向上会有规律性的摆动，本文可以把这种摆动看做是一种钟摆运动[I]。如图1所示，手臂从A到E 就表示一个完整的步伐，如此双手会有一

个不断交替的运动。

# 1.1行走参数分析

从行走参数角度，行人肢体周期性地运动会导致运动参数如加速度、角速度和旋转角速度等发生周期性的变化。行人在正常行走时进入手臂摆动阶段，在此过程中，切向加速度由小变大，再由大变小。因此，通过分析人体行走过程中的加速度数据的变化可以进行步数检测[12]。

# 1.2步数检测算法

常见的步数检测算法有自相关分析法、加减分计步算法、波峰检测算法。

# 1.2.1自相关分析法

自相关分析法是利用人体在连续运动过程中产生的加速度数据序列之间的相似性来进行步数的计算[2]。人体在行走过程中，加速度数据存在一定的周期性。自相关分析法就是通过计算加速度数据在前后两个周期中的相关性来计步的。计算整体加速度后利用式(1)求整体加速度的自相关系数。

$$
w ( m , t ) = \frac { \sum _ { k = 0 } ^ { k = t - 1 } [ \left( x ( m + k ) - u ( m , t ) \right) \times \left( x ( m + k + t ) - u ( m + t , t ) \right) ] } { t \times \delta ( m , t ) \times \delta ( m + t , t ) }
$$

其中： $\mu ( m , t )$ 和 $\delta \left( m , t \right)$ 分别表示的是当前加速度序列

$\{ x ( k ) , x ( k + 1 ) , . . . , x ( k + t - 1 ) \}$ 的均值和标准差。当采样周期 $\mathbf { \chi } _ { t }$ 接近行人的行走周期时，自相关系数 $w ( m , t )$ 的值接近1。然而不同行人或者同一行人在不同时刻的行走周期是不一样的，所以 $t$ 是一个变量。 $t$ 的动态确定使用加框算法来实现，将 $t$ 选定一个范围区间 $t _ { m i n }  – t _ { m a x }$ ，通过式(2)计算自相关系数 $\rho ( { \mathrm { m } } , { \mathrm { t } } )$ ，当 $\rho ( { \mathrm { m } } , { \mathrm { t } } )$ 达到最大值时的 $t$ 值即为该次行走的周期。

$$
\rho ( \mathrm { m , t } ) = \mathrm { m a x } _ { t = t _ { \mathrm { m i n } } } ^ { t = t _ { \mathrm { m a x } } } \left( w ( m , t ) \right)
$$

# 1.2.2加减分计步算法

该方法的基本思想是对行走过程中加速度数据的峰值进行检测。算法在针对时间窗内峰值可能存在较多的情况，不再依靠分析阈值的方法，而是通过计分机制。

此算法认为[3]，在每次计分时，首先比较相邻加速度值大小。如果左侧相邻两个加速度数据增大则加1分，反之减1分；如果右侧相邻两个加速度数据依次减小则加1分，反之则减1分；如果一个时间窗的计分总和大于某一计分阈值，则认为走了一步。

# 1.2.3波峰检测算法

具体来说，就是分析人体行走时加速度数据出现的正弦波的特性，可以通过检测加速度正弦波的波峰或者波谷的个数来识别步伐，波峰检测算法正是通过检测加速度波峰来实现计步的功能，若连续检测到两个波峰则记为一步[13]。

假设当前算法窗口大小为 $n$ ，窗口内的加速度序列$A ( n , t ) = \{ x ( k + 1 , t ) , x ( k + 2 , t ) , . . . , x ( k + n , t ) \}$ ，则满足条件的加速度峰值 $x _ { p e a k }$ 可以表现为如式(3)所示。

$$
\begin{array} { r } { \int x _ { p e a k } = x ( k + m , t ) > x ( k + i , t ) } \\ { \quad \left[ m < n \ a n d \ i \in [ 1 , m ) \cup ( m , n ] \right. } \end{array}
$$

# 2 基于自适应双阈值的计步算法设计

![](images/207b44debf4b2bc5a545738dba0fef81f7598ff6b9a44c1023449b4794a1887c.jpg)  
图1手臂摆动模型 Fig.1Arm swing model   
图2三轴加速度数据波形  
Fig. 2 Datawaveformof tri-axial acceleration

上述算法的不足之处在于人体在行走过程中不可能一直以一个速度前进，因此每一步的周期不尽相同。当人行走速度发生变化时，算法的性能明显下降，因此提出了基于自适应双阈值的计步算法。考虑算法对不同用户行走特征的适应性，采集了多个用户的行走数据。算法的基本流程是数据采集、数据预处理、计算自适应时间窗长度，利用计算所得的时间窗长度进行步数检测以及假步检测。

# 2.1数据采集

本算法的数据是由内置在智能手环内的三轴加速度传感器采集得到的。这些加速度数据可以在安卓手机APP的控制下通过蓝牙协议传输至手机中，进而可以通过WiFi或数据线将加速度数据传送至电脑上进行进一步的处理。截取了部分采集数据，其中从左到右包括序号、X轴加速度、Y轴加速度、Z轴加速度、采集时间，如表1所示。

表1部分采集数据格式

Table1 Partialcollected data format   

<html><body><table><tr><td>序号</td><td>X轴</td><td>Y轴</td><td>Z轴</td><td>年/月/日</td><td>时间</td></tr><tr><td>58</td><td>-22</td><td>-5</td><td>16</td><td>2017/1/3</td><td>21:47:38:314</td></tr><tr><td>59</td><td>-22</td><td>-6</td><td>16</td><td>2017/1/3</td><td>21:47:38:314</td></tr><tr><td>60</td><td>-26</td><td>-10</td><td>17</td><td>2017/1/3</td><td>21:47:38:314</td></tr><tr><td>61</td><td>-28</td><td>-10</td><td>15</td><td>2017/1/3</td><td>21:47:38:314</td></tr><tr><td>62</td><td>-31</td><td>-10</td><td>14</td><td>2017/1/3</td><td>21:47:38:314</td></tr><tr><td>63</td><td>-32</td><td>-9</td><td>11</td><td>2017/1/3</td><td>21:47:38:332</td></tr></table></body></html>

# 2.2数据预处理

利用MATLAB分别画出了X、Y、Z三个轴的加速度数据波形，如图2所示。为了方便数据处理，首先通过求取合加速度的方式将数据进行符号统一化。分析可知大部分的Y轴数据波形振幅都较小，出现这种情况的原因是人体在正常行走过程中手臂一般在上下前后两个方向上摆动，左右摆动幅度较小。计算XZ两个轴的合加速度，波形如图3所示。求取合加速度如式(4)所示。

$$
X _ { _ \bigcirc } = \sqrt { \mathrm { X } ^ { 2 } + \mathrm { Z } ^ { 2 } }
$$

由于噪声以及不同人之间行走频率的差异，数据波形有很多毛刺。为了消除毛刺对计步精度的影响，必须要对数据进行滤波。本文所采用的滤波方法是五点平滑滤波，依此得到平滑波形，如图4所示。五点滤波公式如下，其中X(n)表示第 $n$ 个采样点。滤波如式(5)所示.

$$
X ( n ) { = } \sum _ { i = 0 } ^ { 4 } X ( n { - } i ) / 5
$$

0 s/w -20 -40 wMwWMWMMWMMWM 0 50 100 150 200 250 300 350 400 450 500 1/50s 50 心 m 0 W -50 0 50 100 150 200 250 300 350 400 450 500 1/50s 40 su m 20 M>>>5> O 0 50 100 150 200 250 300 350 400 450 500 1/50s

![](images/2a83613d6d68754f8a8fde0f9b17f4575f2e748283422c277e0f13291124e691.jpg)  
图3二轴合加速度数据波形

![](images/88cf4955deefada94d6f134258739b9c1886fe933f8aa0da8398ae537858eeb9.jpg)  
Fig. 3 Datawaveform of biaxial acceleration   
图4二轴合加速度滤波后的数据波形  
Fig.4 Data waveform of biaxial acceleration after filtering

# 2.3 自适应时间窗设计

不同的人有不同的步行频率，如果按照固定的时间窗长度来测量步数肯定会产生误差，因此要找出一种方法来适应不同人的步行频率[14]。

本算法所采用的方法就是自适应时间窗.所谓自适应时间窗，就是通过分析采样数据计算每一有效步数的采样个数的均值，并将其作为检测用户步数的时间窗长度。在计算时间窗长度的过程中，先设置一个时间窗长度初值。之所以这么做有两个原因：一是方便对采样数据进行步数检测，以求取每一有效步数的采样个数；二是由于样本数据较少，先设定时间窗长度不会对计步精度有较大影响，不过在计算过程中可能会存在因为采集的数据不当而导致时间窗过大。为了避免时间窗长度过大而导致计步精度降低的问题，本算法在经过多次数据测试后定义了一个取时间窗长度的条件，即当计算的自适应时间窗长度大于一定值时，就将时间窗长度减半。

算法通过检测样本数据的有效步数，利用双阈值分析法计算出每一步的采样点数，并将其存放在数组中，最终经过假步检测后计算出每一有效步数的平均采样点数，这个采样点数就是本文所计算的自适应时间窗长度。设置的时间窗长度是经过多次数据测试后根据具体的计步精度确定的，减弱了其对计步精度的影响。另外计算时间窗的数据可以通过两种方法获得：一种是单独采样，采集每个人在不同频率下行走一定步数或一定时间后的数据作为样本数据；另一种方法是截取一段进行计步的用户数据作为样本数据，为了保证数据的有效性，一般截取中间部分的数据。本算法所采用的数据是基于第二种方法获得的，采样个数选取为300。计算公式如式(6)所示。

$$
L s = \sum _ { i = 1 } ^ { N } t m p _ { - } \mathrm { d i m } ( i ) / N
$$

# 2.4步数检测

# 2.4.1检测波峰波谷

在一定时间窗长度内，对加速度数据进行滤波等预处理操作，以去除高频噪声产生的毛刺。设加速度经过处理后为X(n)，从第二个数据起开始进行波峰波谷检测。

如果时间窗的加速度数据大小满足

$$
\left\{ \begin{array} { l l } { X \left( n - N + 1 \right) - X \left( n - N \right) > 0 } \\ { X \left( n \right) - X \left( n - 1 \right) > 0 } \\ { X \left( n \right) - X \left( n + 1 \right) > 0 } \\ { X \left( n + N + 1 \right) - X \left( n + N \right) > 0 } \end{array} \right.
$$

即视 $X ( n )$ 为时间窗内的一个峰值，并将其存储在max_data数组中；

同理，如果时间窗的加速度数据大小满足

$$
\left\{ \begin{array} { l l } { X \left( n - N + 1 \right) - X \left( n - N \right) < 0 } \\ { X \left( n \right) - X \left( n - 1 \right) < 0 } \\ { X \left( n \right) - X \left( n + 1 \right) < 0 } \\ { X \left( n + N + 1 \right) - X \left( n + N \right) < 0 } \end{array} \right.
$$

即视 $X ( n )$ 为时间窗内的一个谷值，并将其存储在 $\mathbf { m i n } _ { - } d a t a$ 数组中。

# 2.4.2双阈值

本算法采用的计步方法是双阈值分析法。所选取阈值是否合适对计步精度有决定性的影响。双阈值即以时间窗内波峰均值与波谷均值的平均值作为上阈值，波谷均值作为下阈值。如果采用波峰均值为上阈值就会有很大的几率产生漏检。阈值计算公式如下：

$$
T _ { { \scriptscriptstyle H } } = \big ( H + L \big ) / 2
$$

$$
T _ { \scriptscriptstyle L } = L
$$

其中： $\mathrm { ~ H ~ }$ 是时间窗内的峰值均值； $\mathrm { ~ L ~ }$ 是时间窗内的谷值均值；  
$T _ { \scriptscriptstyle H }$ 是当前时间窗内的上阈值； $T _ { L }$ 是当前时间窗内的下阈值。

不过由于时间窗内极值的个数不定，所以在计算阈值的时候要遵循一定的方法。

# 1）多极值

当时间窗内有两个或两个以上的峰值或谷值时，可以直接计算其波峰波谷的均值，继而得到双阈值，如式（11)（12)所示。

$$
H { = } \sum _ { i = 1 } ^ { N } \mathrm { m a x } _ { - } d a t a ( i ) / N _ { \mathrm { m a x } }
$$

$$
L = \sum _ { i = 1 } ^ { N } \operatorname* { m i n } _ { - } d a t a ( i ) / N _ { \mathrm { m i n } }
$$

其中： $H$ 是时间窗内的峰值均值； $L$ 是时间窗内的谷值均值；$\mathrm { m a x } _ { - } d a t a ( i )$ 是当前时间窗内的波峰值； $\mathrm { m i n } _ { - } d a t a ( i )$ 是当前时间窗内的波谷值； $N _ { \mathrm { m a x } }$ 是时间窗内波峰的个数； $N _ { \mathrm { m i n } }$ 是时间窗内波谷的个数。

# 2）单极值

当时间窗内波峰或者波谷只有一个时，取上个时间窗的对应的阈值与本时间窗的极值的均值作为本时间窗内的阈值，如式（13（14）所示。

$$
\begin{array} { c } { { H = t m p _ { - } H + \operatorname* { m a x } _ { - } d a t a } } \\ { { L = t m p _ { - } L + \operatorname* { m i n } _ { - } d a t a } } \end{array}
$$

其中： $t m p _ { - } H$ 是上一个时间窗内的峰值均值； $t m p _ { - } L$ 是上一个时间窗内的谷值均值；max_data是当前时间窗内的波峰值；

min_data 是当前时间窗内的波谷值。

# 3）零极值

当时间窗内没有波峰或者波谷，取上个时间窗的对应的阈值作为本时间窗内的阈值，如式（15）（16）所示。

$$
H = t m p _ { - } H
$$

$$
L = t m p _ { - } L
$$

其中： $t m p _ { - } H$ 是上一个时间窗内的峰值均值； $t m p _ { - } L$ 是上一个时间窗内的谷值均值。

# 2.4.3步数检测

步数检测以采集到的经过处理的加速度信号波峰值大于上阈值 $T _ { H }$ 且此峰值下面的一到两个采样数据小于下阈值 $T _ { L }$ 时记为一步。图5所示为步数检测与假步检测的整体流程。

![](images/aba9fcdd8a4bd93b3f73754bea38a04f2ec8a14fabf78259ceaa9bf86f97a6e7.jpg)  
图5步数检测与假步检测流程  
Fig.5Flowchart of step number detection and false step detectior

# 2.5假步检测

# 2.5.1行走频率

由于人的正常行进(包括慢走、快走和跑步)步频为0.2\~5$\mathrm { H z } ^ { [ 1 5 ] }$ ，本算法的数据采样频率 $f$ 是 $5 0 ~ \mathrm { H z }$ ，所以在步数检测阶段所检测到的每两步之间的采样点数要在 $0 . 2 f { \sim } 5 f$ 之间(f为手环的数据采集频率)，否则视为假步，并且此峰值不计步。公式如(17)所示。

$$
\dim = t m p _ { - } \dim ( i ) - t m p _ { - } \dim ( i - 1 )
$$

其中：数组tmp_dim中存放着有效峰值，当两个峰值之间的差值即采样点数dim满足 $0 . 2 f { < } d i m { < } 5 f$ ，则将其暂时计为有效步数，否则为无效步数。图6所示为波峰检测中伪波峰干扰的示意图。

# 2.5.2行走振幅

通过波形发现，人体在运动与静止状态下所采集到的数据波形幅度并不一样，其波峰波谷的差值都在一定的范围内。经过大量的数据测试，将波峰波谷的差值小于1的状态定义为静止状态，如图7所示。这种方法有效地排除了用户在静止状态下对计步精度的干扰问题。

![](images/7315b94839be0c671dc0dedfa81ddeff48e2551a0b0abf5084f5914a7fd61719.jpg)  
图6波峰检测中伪波峰的干扰

![](images/005b4a549b4bc1c178f1a2c72b50e0d1c2b0cf3345d7c047a00acb6e5797c836.jpg)  
Fig.6Interference of pseudo-peaks during peak detection   
图7静止状态下二轴合加速度的数据波形  
Fig. 7 Datawaveform ofbiaxial acceleration in static state

# 3 实验与分析

在生活中，每个人的步行频率都不一样，在采集数据时同一个人在行走过程中也不可能一直以相同的速度前进。要使算法具有实用性，就需要能够适应各种步行频率。为了达到这个目的，在数据采集过程中，用不同用户的慢走、快走、跑步这三种方式来代表不同频率。为了使算法更具有代表性，测试了一些在特殊情况下如将手环放在口袋内(即不甩臂慢走)的数据。

# 3.1算法测试

通过对采集到的数据分析发现，在运动状态下波形幅度明显比静止状态下的要大，因此在算法拟合中拟采用波形幅度的大小来区分运动与静止状态。完成算法后，进行了三轴数据测试。对X、Y、Z三轴加速度的合加速度进行分析，得到的测试结果如表2所示。

对算法进行改进，由于人在行走过程中手臂几乎在一个平面上摆动（上下前后方向，左右波动较小)，所以，为了尽可能的排除其他因素的干扰，将数据波形振幅都较小的Y轴不加以考虑，第二次测试只选择分析X与Z轴的数据，并称为二轴数据测试，由式(4)求得合加速度数据，测试结果如表3所示。

从测试结果可以看出，对于使用二轴加速度实现计步，除了将手环放在口袋中行走时准确率有所降低外，在用其他状态行走时，准确率有明显的提升，而且将手环放在口袋中之所以准确率会有所降低，是因为手环内的三轴加速度传感器方向无法确定。在实际生活中，一般手环都会带在手臂上，所以这种状态下精度降低是可以接受的。

Table 2 Test results of 3-axis data   

<html><body><table><tr><td>测试项目</td><td>实际步数</td><td>自适应30 实显步数</td><td>误差步数(步)</td><td>准确率</td></tr><tr><td>甩臂慢走</td><td>200</td><td>202</td><td>2</td><td>99.00%</td></tr><tr><td></td><td>100</td><td>88</td><td>-12</td><td>88.00%</td></tr><tr><td></td><td>100</td><td>88</td><td>-12</td><td>88.00%</td></tr><tr><td>登山慢走</td><td>100</td><td>107</td><td>7</td><td>93.00%</td></tr><tr><td>甩臂快走</td><td>200</td><td>154</td><td>-46</td><td>77.00%</td></tr><tr><td rowspan="3">不甩臂慢走</td><td>200</td><td>162</td><td>-38</td><td>81.00%</td></tr><tr><td>200</td><td>205</td><td>5</td><td>97.50%</td></tr><tr><td>200</td><td>178</td><td>-22</td><td>89.00%</td></tr><tr><td rowspan="4">跑步</td><td>200</td><td>179</td><td>-21</td><td>89.50%</td></tr><tr><td>100</td><td>96</td><td>-4</td><td>96.00%</td></tr><tr><td>100</td><td>76</td><td>-24</td><td>76.00%</td></tr><tr><td>100</td><td>103</td><td>3</td><td>97.00%</td></tr></table></body></html>

表3二轴数据测试结果  
Table 3 Test results of 2-axis data   

<html><body><table><tr><td>测试项目</td><td>实际步数</td><td>自适应30 实显步数</td><td>误差步数（步）</td><td>准确率</td></tr><tr><td>甩臂慢走</td><td>200</td><td>182</td><td>-18</td><td>91.00%</td></tr><tr><td rowspan="4">登山慢走</td><td>100</td><td>96</td><td>-4</td><td>96.00%</td></tr><tr><td>100</td><td>92</td><td>-8</td><td>92.00%</td></tr><tr><td>100</td><td>99</td><td>-1</td><td>99.00%</td></tr><tr><td>200</td><td>186</td><td>-14</td><td>93.00%</td></tr><tr><td rowspan="3">不甩臂慢走</td><td>200</td><td>180</td><td>-20</td><td>90.00%</td></tr><tr><td>200</td><td>186</td><td>-14</td><td>93.00%</td></tr><tr><td>200</td><td>185</td><td>-15</td><td>92.50%</td></tr><tr><td rowspan="4">跑步</td><td>200</td><td>173</td><td>-27</td><td>86.50%</td></tr><tr><td>100</td><td>89</td><td>-11</td><td>89.00%</td></tr><tr><td>100</td><td>80</td><td>-20</td><td>80.00%</td></tr><tr><td>100</td><td>94</td><td>-6</td><td>94.00%</td></tr></table></body></html>

# 3.2对比分析

算法完成后，将算法与小米手环2的精度作了对比。对比方法是将小米手环2和A10手环(算法经过10次修改与调试，故称为 A10 手环)分别戴在左右手上，在走过一定的步数后记录下小米手环2的步数，再记录下A10手环采集得到的数据经过算法计步得到的步数，然后将两者进行对比。对比数据如表4所示。

从对比结果可以看出：算法在慢走、快走时平均计步精度比小米手环2的精度高，不甩臂慢走(将手环放入口袋中)时平均计步精度比小米2精度稍低一点。一般手环都会戴在手臂上，所以这种状态下精度降低是可以接受的。从总体角度来看，本算法的平均计步精度会比小米手环2的平均计步精度要高。

# 4 结束语

为了解决现有算法对不同运动状态适应性差和无法适应不同用户行走特征的问题，本文设计了一种基于自适应阈值的计步算法，在数据采集阶段采集了不同用户用三种步行频率行走的数据，算法在经过大量的数据测试和不断地改进后，实验结果表明在慢走、快走或跑步三种不同频率下的平均计步精度可以达到 $91 . 8 8 \%$ 以上，并且统计了算法对不同用户的行走特征具有很好的适应性，有效地排除了非行走因素(起立、坐下、打字、敲桌子等)问题的干扰，完成了预期目标。不过现在算法中仍然有需要加强之处，比如对于手环放在口袋中采集得到的数据，算法精度还需继续提高等。下一步的研究方向是继续完善算法，运用机器学习上的分类方法在检测假步方面作出更精确的判定，提高计步的精度。

表2三轴数据测试结果  
表4提出的算法与小米手环的对比结果  
Table 4 Comparison between proposed algorithm and xiaomi   

<html><body><table><tr><td colspan="6">bracelet</td></tr><tr><td rowspan="2">手环</td><td rowspan="2">测试项目</td><td>实际</td><td>实显</td><td rowspan="2">误差步数（步)</td><td rowspan="2">准确率</td></tr><tr><td>步数</td><td>步数</td></tr><tr><td>A10</td><td>甩臂慢走</td><td>200</td><td>165</td><td>-35</td><td>82.50%</td></tr><tr><td>小米</td><td>甩臂慢走</td><td>200</td><td>177</td><td>-23</td><td>88.50%</td></tr><tr><td>A10</td><td>甩臂慢走</td><td>200</td><td>147</td><td>-53</td><td>73.50%</td></tr><tr><td>小米</td><td>甩臂慢走</td><td>207</td><td>77</td><td>-130</td><td>37.20%</td></tr><tr><td>A10</td><td>甩臂慢走</td><td>200</td><td>153</td><td>-47</td><td>76.50%</td></tr><tr><td>小米</td><td>甩臂慢走</td><td>200</td><td>104</td><td>-96</td><td>52.00%</td></tr><tr><td>A10</td><td>甩臂慢走</td><td>200</td><td>173</td><td>-27</td><td>86.50%</td></tr><tr><td>小米</td><td>甩臂慢走</td><td>200</td><td>142</td><td>-58</td><td>71.00%</td></tr><tr><td>A10</td><td>甩臂快走</td><td>200</td><td>186</td><td>-14</td><td>93.00%</td></tr><tr><td>小米</td><td>甩臂快走</td><td>200</td><td>160</td><td>-40</td><td>80.00%</td></tr><tr><td>A10</td><td>甩臂快走</td><td>200</td><td>165</td><td>-35</td><td>82.50%</td></tr><tr><td>小米</td><td>甩臂快走</td><td>200</td><td>190</td><td>-10</td><td>95.00%</td></tr><tr><td>A10</td><td>甩臂快走</td><td>200</td><td>170</td><td>-30</td><td>85.00%</td></tr><tr><td>小米</td><td>甩臂快走</td><td>200</td><td>121</td><td>-79</td><td>60.50%</td></tr><tr><td>A10</td><td>甩臂快走</td><td>200</td><td>132</td><td>-68</td><td>66.00%</td></tr><tr><td>小米</td><td>甩臂快走</td><td>205</td><td>173</td><td>-32</td><td>84.39%</td></tr><tr><td>A10</td><td>不甩臂慢走</td><td>200</td><td>186</td><td>-14</td><td>93.00%</td></tr><tr><td>小米</td><td>不甩臂慢走</td><td>200</td><td>201</td><td>1</td><td>99.50%</td></tr><tr><td>A10</td><td>不甩臂慢走</td><td>200</td><td>168</td><td>-32</td><td>84.00%</td></tr><tr><td>小米</td><td>不甩臂慢走</td><td>207</td><td>213</td><td>6</td><td>97.10%</td></tr><tr><td>A10</td><td>不甩臂慢走</td><td>200</td><td>173</td><td>-27</td><td>86.50%</td></tr><tr><td>小米</td><td>不甩臂慢走</td><td>200</td><td>242</td><td>42</td><td>79.00%</td></tr><tr><td>A10</td><td>不甩臂慢走</td><td>200</td><td>168</td><td>-32</td><td>84.00%</td></tr><tr><td>小米</td><td>不甩臂慢走</td><td>200</td><td>177</td><td>-23</td><td>88.50%</td></tr></table></body></html>

# 参考文献：

[1]Jiang X,Chu K H,Menon C.An easy-to-use wearable step counting device for slow walking using ankle force myography $[ \mathrm { C } ] / \hbar$ Proc of IEEE International Conference on Systems,Man，and Cybernetics. [S.l.]:IEEE Press,2017: 2219-2224.   
[2] 陈国良，张言哲，杨洲．一种基于手机传感器自相关分析的计步器 实现方法[J].中国惯性技术学报，2014，22(6):794-798.(Chen Guoliang,Zhang Yanzhe,Yang Zhou.Realization of pedometer with auto-correlation analysis based on mobile phone sensor[J].Journal of Chinese Inertial Technology,2014,22(6): 794-798.)   
[3]王文杰，李军．基于手机加速度传感器的计步算法设计[J].工业控 制计算机,2016,29(1):75-76.(Wang Wenjie,Li Jun.Algorithm design of counting steps based on mobile acceleration sensor [J].Industrial Control Computer,2016,29(1):75-76.)   
[4]Tang Z,Guo Y, Chen X. Self-Adaptive step counting on smartphones under unrestricted stepping modes [C]//Proc of Computer Software and Applications Conference.[S.l.]:IEEE Press,2016:788-797.   
[5]陈国良，李飞，张言哲．一种基于自适应波峰检测的 MEMS计步算 法[J].中国惯性技术学报,2015,23(3):315-321.(Chen Guoliang,Li Fei,Zhang Yanzhe.Pedometer method based on adaptive peak detection algorithm [J]. Journal of Chinese Inertial Technology,2015, 23 (3):315-321.)   
[6]Hu WY,LuJL,Jiang S,etal.WiBEST:Ahybrid personal indoor positioning system [C]//Proc of IEEE Wireless Communications and Networking Conference.[S.1.]:IEEE Press,2013:2149-2154.   
[7]Jimenz A R,Seco F,Prieto C,et al.A comparison of pedestrian dead-reckoning algorithms using a low-cost MEMS IMU [C]// Proc of IEEE International Symposium on Intelligent Signal Processing. [S.1.]:IEEE Press,2009:37-42.   
[8]Zhang R,Bannoura A,Hoflinger F,et al.Indoor localization using a smart phone [C]//Proc of Sensors Applications Symposium.[S.l.]:IEEE Press,2013:38-42.   
[9]Chien JC,Hirakawa K,Shieh JS,et al.An effective algorithm for dynamic pedometer calculation [C]//Proc of International Conference on Intelligent Informatics and Biomedical Sciences.[S.l.]:IEEE Press, 2016:366-368.   
[10]Brajdic A,Harle R.Walk detection and step counting on unconstrained smartphones [C]// Proc of ACM International Joint Conference on Pervasiveand UbiquitousComputing.[S.l.]:ACM Press,2013: 225-234.   
[11]陈丹华．计步器计步方法专利技术综述[J]．中国科技信息，2017 (22):24-25.(Chen Danhua.Summary of patented technology for pedometer step counting method [J].China Science and Technology Information,2017 (22): 24-25.)   
[12]韩文正，冯迪，李鹏．基于加速度传感器LIS3DH的计步器设计[J]. 传感器与微系统,2012,31(11):97-99.(Han Wenzheng,Feng Di,Li Peng.Design of pedometer based on acceleration sensor LIS3DH[J]. Transducer and Microsystem Technologies,2012,31(11): 97-99.)   
[13]谢光强，黄向龙，李杨，等．基于MEMS加速度传感器的步数检测 算法研究综述[J].计算机应用研究，2018,35(12):3526-3532.(Xie Guangqiang,Huang Xianglong,Li Yang,et al.Review of research on step detection algorithm with MEMS-based acceleration sensor [J]. Journal of Application Research of Computers，2018，35(12): 3526-3532.)   
[14]宋浩然，廖文帅，赵一鸣．基于加速度传感器ADXL330的高精度计 步器[J].传感技术学报,2006,19(4):1005-1008.(Song Haoran,Liao Wenshuai,Zhao Yiming.Using 3-axis accelerometer ADXL33O to high accuracy pedometer [J]. Chinese Journal of Sensors and Actuators.2006. 19(4):1005-1008.)   
[15]刘程，阳洪．自适应计步检测算法研究[J]．压电与声光，2015,37 (2):258-261.(Liu Cheng,Yang Hong.Study on adaptive pedometer detection algorithm [J].Piezoelectrics & Acoustooptics,2015,37 (2): 258-261.)