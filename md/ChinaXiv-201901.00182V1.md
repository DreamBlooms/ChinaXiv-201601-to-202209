# 一种识别重叠噪声的交通量检测算法

马庆禄，邹政

(重庆交通大学 交通运输学院，重庆 400074)

摘要：在传统的交通量检测中，短时能量法和短时平均幅度法存在无法识别重叠行车噪声段的问题，而提取与重叠信号最相关的频谱视图（spectrum view，SV）作为重叠行车噪声段的特征有助于解决以上问题。针对以上结论进行研究，提出了一种基于SV特征的交通量检测算法。该算法首先对含有重叠行车噪声段的交通噪声进行滤波降噪;然后将交通噪声通过快速傅里叶变换（fast Fouriertransform，FFT）以提取其 SV特征，并对 SV特征进行平滑处理；最后基于SV特征并以双门限判决原理为依托，对交通噪声进行端点检测并分离出重叠的行车噪声段。实验基于单车道、少流量路段的交通噪声数据集，与传统方法相比，准确率提高了 $20 \%$ ，从而验证了该算法的有效性。

关键词：交通工程；交通量检测；交通噪声；重叠噪声识别；频谱视图；端点检测中图分类号：U495 doi: 10.19734/j.issn.1001-3695.2018.08.0746

Trafic detection algorithm for identifying overlapping noise

Ma Qinglu, Zou Zheng+ (School of Traffic & Transportation,Chongqing Jiaotong University,Chongqing 40oo74, China)

Abstract:Traditionaly,the short-term energy methodortheshort-termaverage magnitude method is notableto identify theoverlapping traffcnoisesegments efectively,inorder tosolvethe problem,thispaper proposes atrafficdetection algorithm which is basedon the Spectrum View(SV)features.First,it filtered and denoised the trafic noise which contained overlapping noise.Next,it extractedtheSVfeaturesofthetraffic noise viaFastFourier Transform (FFT），and thensmoothedtheSVfeatures.Finaly,basedontheSVfeaturesandtheprincipleofdual-thresholds judgment,itetected theendpointsof the trafic noiseand identified theoverlappng noise.In condition of a single lane and low traffic, experiments on dataset of trafic noise demonstrate that the accuracy outperforms other usual methods by $20 \%$ ：

Key words:trafficengineering;traffcdetection;traffcnoise;overlapping noise recognition;spectrum view;endpoint: detection

# 0 引言

城市道路中，每天都在产生大量的交通噪声数据，而噪声污染也是城市交通外部特性之一，会给人们造成不适、烦恼和不快[1。但是交通噪声也携带了大量的有用信息，在对其隔离屏蔽甚至消除之前，可以预先提取出其中的有用信息。目前，语音处理技术已经比较成熟[2]，所以可借鉴其对交通噪声进行分析。交通噪声的研究正在逐步成为智能交通领域信息采集技术研究的新方向。

关于交通噪声，大多数论文都集中在交通评估的研究上[3-8]。Joshi 等人[9]利用交通噪声测量提出了适用于混乱交通条件下的交通密度状态分类方法。Bhandarkar等人[10]提出了训练支持向量机和人工神经网络来分类交通密度等级中的交通流的思路，分类依赖于从行车噪声信号中提取的特征：MFCC和能量。Borkar等人[11]开发了基于MFCC表征的神经模糊分类器以分类三种不同交通密度等级的交通流，结果显示分类精度超过 $9 5 \%$ 。关博文等人[12]对美国印第安纳州I-465高速公路新型LOS声屏障实验段进行噪声测试与TNM分析，研究了路面类型、车辆速度、交通量、降噪系数、声屏障高度与声屏障延长对LOS声屏障降噪水平的影响，结果表明：LOS声屏障设计时，设计降噪幅度宜大于6.7dBA，最低高度应大于路面行驶的大型车辆高度，最大高度不超过6.6m，最佳高度由设计年限内降噪效果模拟分析确定。

利用交通噪声进行车辆识别并检测交通量的研究相对较少。Alexandre 等人[13]将极端机器学习与遗传算法组合选取交通噪声的相关特征并对车辆进行分类，结果显示，正确分类率从 $7 4 . 8 3 \%$ （未选择特征时）提高到了 $9 3 . 7 4 \%$ （选择特征后)。Lefebvre等人[14]提取了多车道情况下的交通噪声的MFCC特征向量并利用支持向量机估算了11.5天的交通量，实验结果显示交通量的估算误差在 $8 5 \%$ 左右；Mato-Mndez等人[15提出了一种基于立体声记录的系统，该系统设计用于检测车辆通过和识别车辆类别。该系统将车辆类型分为了摩托车、汽车和卡车，实验测试了约761个信号，结果显示在每个类别中正确识别的约 $9 5 \%$ 。Torija等人[16]利用实测的交通噪声的声谱剖面作为城市道路实时短时交通流量估计的输入数据，结果显示该方法的平均分类成功率为 $9 6 . 1 \%$ 。

关于交通噪声发生重叠时的交通量检测研究则更少。针对声音信号重叠的问题，Dennis等人[17]利用声音的局部频谱特征识别重叠声音事件并分离背景噪声，该方法在重叠信号的识别上具有一定的效果，可以尝试应用到交通噪声发生重叠的情况。何小华[18提出了在单车道、少流量的情况下对采集的交通噪声进行端点检测的方法，该方法基于短时能量特征，但并未考虑交通噪声重叠的情况。所以，针对交通噪声发生重叠的问题，本文提出了基于交通噪声频谱视图（spectrumview，SV）特征分析的交通量检测方法，并对比了传统的短时能量法和短时平均幅度法，验证了SV算法的有效性。

# 1 基本概念

交通噪声是行车噪声和环境噪声的组合。交通噪声的定义如图1所示。图1表示从126s的交通噪声中截取的35s样本交通噪声，且含有重叠的行车噪声段（为方便后面分析并对比普通行车噪声段和重叠行车噪声段的特征)，重叠行车噪声段是由于相邻两辆车的车头时距较小造成的。在交通噪声的分析过程中会涉及预处理、中值滤波和归一化等技术，所以先对相关概念进行阐述。

![](images/02d26661a7a86e0c0ab50d592b502f9f19fa101eeaf6c0b2edb7564183a3b293.jpg)  
图1LMS滤波器降噪前后的样本交通噪声  
Fig.1Sample-traffic-noise before and after noise reduction by LMS filter

在提取交通噪声的特征之前，需要对交通噪声进行预处理。预处理包括降噪、加窗和分帧。LMS自适应滤波器具有自动调节自身参数的能力且不需要先验知识[19]，所以，可以选取该滤波器对交通噪声进行滤波降噪。经LMS自适应滤波器降噪前的交通噪声波形如图1(a)所示，降噪后的波形如图1(b)所示。可以看出，降噪后的交通噪声波形相比降噪前的更平滑，行车噪声与环境噪声的区分度更高。

相对其他窗函数，汉明窗频谱泄露较小，所以选用汉明窗作为加窗函数。汉明窗函数的定义如式(1)所示。

$$
\begin{array} { c } { { \left\{ w \left( n \right) = 0 . 5 4 - 0 . 4 6 \cos { \left( \frac { 2 \pi \left( n - 1 \right) } { N - 1 } \right) } \right. } } \\ { { n = 1 , 2 , \cdots , \ N } } \end{array}
$$

其中： $w ( n )$ 表示汉明窗； $N$ 为窗长，亦称为帧长（一帧信号的样本点数目）； $n$ 表示窗函数的第 $n$ 个采样点。帧信号加窗后的结果如式(2)所示。

$$
\left\{ \begin{array} { l } { L = \left[ \left( l _ { x } - N \right) / d _ { \mathrm { i n c } } \right] _ { \mathrm { i n t } } + 1 } \\ { \quad \quad i = 1 , 2 , \cdots , L } \\ { \quad m = \left( i - 1 \right) d _ { \mathrm { i n c } } + n } \\ { \quad y _ { i } \left( n \right) = w \left( n \right) x \left( m \right) } \end{array} \right.
$$

其中： $L$ 表示帧数目； $d _ { \mathrm { i n c } }$ 表示帧移； $\boldsymbol { x }$ 表示交通噪声信号； $l _ { x }$ 表示 $\boldsymbol { x }$ 的样本长度； $[ \bullet ] _ { \mathrm { i n t } }$ 表示取整函数； $y _ { i } ( n )$ 为加窗后的第 $i$ 帧信号。实验测试后发现，当 $N { = } 2 0 0$ 和 $d _ { \mathrm { { i n c } } } { = } 1 0 0$ 时，比较适合提取样本交通噪声的相关特征。

交通噪声在经过LMS自适应滤波器降噪后仍然具有较低的信噪比，从而使得交通噪声的相关特征曲线在环境噪声段内起伏较大，所以需要进一步对特征参数曲线进行平滑处理。中值滤波既可以去除少量的野点，又不会破坏数据在两个平滑段之间的阶跃性变化。为了使平滑处理的效果更好，可以适当增加中值滤波的次数。同时，采用最大最小归一化方法可以将所有数据转换为[0.1]间的值，以此消除各维数据间的数量级差别，避免因为数据数量级差别较大而造成计算误差较大。最大最小归一化的计算如式(3)所示。

$$
X _ { p } = \frac { X _ { p } - X _ { \operatorname* { m i n } } } { X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } }
$$

其中： $X _ { p }$ 为序列中的第 $p$ 个值； $X _ { \operatorname* { m i n } }$ 为序列中的最小值; $X _ { \mathrm { m a x } }$   
为序列中的最大值。

# 2 方法原理

传统方法检测交通量的基本思想是：首先提取交通噪声的短时能量（short-termenergy，STE）特征或者短时平均幅度（short-termaveragemagnitude，STAM）特征，之后直接根据STE特征或者STAM特征区分行车噪声和环境噪声并统计行车噪声段数目，该数目即为交通噪声中的车辆数。可以看出，传统算法没有考虑行车噪声段彼此发生重叠的情况，所以会将重叠的多个行车噪声段检测为一个行车噪声段。为解决这个问题，提出了SV算法。SV算法检测交通量的基本思想是：首先对交通噪声的每帧信号进行快速傅里叶变换（fastFouriertransform，FFT）并提取SV特征，之后根据SV特征区分行车噪声和环境噪声并分离重叠的行车噪声段，最后统计行车噪声段的数目并将该数目作为交通噪声中的车辆数。

# 2.1传统算法

交通噪声每帧信号的STE、STAM的定义分别如式(4)和(5)所示。其中： $E _ { i }$ 表示第 $i$ 帧信号的 STE； $M _ { i }$ 表示第 $i$ 帧信号的STAM。

$$
E _ { i } = \sum _ { n = 1 } ^ { N } { y _ { i } } ^ { 2 } \left( n \right)
$$

$$
M _ { i } = \sum _ { n = 1 } ^ { N } \lvert y _ { i } \left( n \right) \rvert
$$

记P表示交通噪声的STE（E）或者STAM（M)， $P _ { i }$ 表示第 $i$ 帧信号的特征值，按式(4)或者式(5)计算。记 $P 1$ 为特征P的较高阈值， $P 2$ 为较低阈值；记 $l _ { \mathrm { n o v e h } }$ 为环境噪声段的最小长度， $l _ { \mathrm { v e h } }$ 为行车噪声段的最小长度， $l _ { \mathrm { n o v e h } }$ 和 $l _ { \mathrm { v e h } }$ 的单位均为帧;记 $Q _ { 0 }$ 为真实车辆数， $\boldsymbol { Q }$ 为执行算法过程中的当前时刻的检测车辆数， $\boldsymbol { \varepsilon } _ { r }$ 为 $\boldsymbol { Q }$ 的相对误差限。则基于 $\mathrm { ~ \bf ~ P ~ }$ 特征的双门限端点检测流程如下[20]：

a)初始化 $P 1$ 、 $P 2$ 、 $l _ { \mathrm { v e h } }$ 、lnoveh和 $\varepsilon _ { r }$ 。

b)依次计算交通噪声每帧信号的特征值 $P _ { i }$ ，若 $P _ { i } \leq P 1$ 且$P _ { r } { \leq } P 2$ （ $r = i + 1$ ， $i + 2$ ，…， $i + l _ { \mathrm { v e h } } - 1 \rangle$ ，则令 $i _ { \mathrm { s t a r t } } ^ { Q } = i$ ，其中 $i _ { \mathrm { s t a r t } } ^ { Q }$ 就为第 $\boldsymbol { \mathscr { Q } }$ 个行车噪声段的起始端点；紧接着从 $i = i + l _ { \mathrm { v e h } }$ 开始继续依次计算 $P _ { i }$ ，直至出现 $P _ { i } < P 2$ 且 $P _ { s } < P 2$ （ $s = i + 1$ ， $i +$ 2，…， $i + l _ { \mathrm { n o v e h } } - 1$ ）的情况时，则令 $i _ { \mathrm { e n d } } ^ { Q } = i + l _ { \mathrm { n o v e h } } - 1$ ，其中 $i _ { \mathrm { e n d } } ^ { Q }$ 就为第 $\boldsymbol { \mathcal { Q } }$ 个行车噪声段的结束端点，区间[ $i _ { \mathrm { s t a r t } } ^ { Q }$ ， $i _ { \mathrm { e n d } } ^ { Q }$ ]就表示第$\boldsymbol { \mathcal { Q } }$ 个行车噪声段。反复执行步骤b)，直到遍历完交通噪声的所有帧信号才执行 Step 3。

c)统计此刻的行车噪声段数目（即检测车辆数） $\boldsymbol { Q }$ ，若$| Q - Q _ { 0 } | / Q _ { 0 } \leq \varepsilon _ { r }$ ，则保存当前的 $P 1$ 、 $P 2$ 、 $l _ { \mathrm { v e h } }$ 、lnoveh、 $\varepsilon _ { r }$ 参数和所有行车噪声段的端点检测结果，然后停止检测算法；反之，则调节 $P 1$ 、 $P 2$ 、 $l _ { \mathrm { v e h } }$ ， $l _ { \mathrm { n o v e h } }$ 或者 $\varepsilon _ { r }$ 参数并从步骤a)重新运行检测算法。

1.5 1.0p 1.0r1.2 0.8 E1 0.8 E1  
0.9 π0.6 E2 50 E250.6 50.40.3 0.2 VF 0.20.0 J 10 时间 25 30 35 0.0 5 10 时间 25 30 35 0 5 10 时间 25 30 35a(a) STE 原始特征曲线 (b)平滑处理后的STE 特征曲线 $[ E 1 \leq \mathrm { V } _ { \mathrm { E } } ]$ (c）平滑处理后的 STE 特征曲线 $\mathbf { \mathop { E 2 } > V _ { E } } ,$ (a) Original characteristic curve of STE (b) Smoothed characteristic curve of STE $( E 1 \leq \mathrm { V } _ { \mathrm { E } } )$ (c)Smoothed characteristic curve of STE $( E 2 > \mathrm { V } _ { \mathrm { E } } )$ 0 1.0 1.084 M2 M0.2 0.28 5 10 时间 25 30 35 0.0 5 10 时间 25 30 35 00 5 10 时间 25 30 35(f)(d) STAM原始特征曲线 (e）平滑处理后的STAM特征曲线 $( M 1 \leq \mathrm { V _ { M } } )$ ）(f）平滑处理后的STAM特征曲线( $[ M 2 > \mathrm { V } _ { \mathrm { M } } )$ （  
(d) Original characteristic curve of STAM (e)Smoothed characteristic curve of STAM $[ M ] \leq \mathrm { V _ { M } } ,$ (f)Smoothed characteristic curve of STAM( $M 2 > \mathrm { V _ { M } } ,$

图2传统算法下含有重叠信号的样本交通噪声端点检测结果

对图1 (b)中的样本交通噪声执行传统算法，端点检测结果（亦即车数检测结果）如图2所示。图2(b)和(c)的车辆数检测结果分别为4veh和2veh；(e)和(f)的车辆数检测结果亦分别为4veh和2veh。

观察图2 (b)和(e)可以发现，前两个非重叠行车噪声段的波峰峰值低于或者等于V( $\mathrm { \Delta V _ { E } }$ 和 $\mathrm { v _ { M } }$ 统称V）点的值，第三个非重叠行车噪声段的波峰峰值高于V点的值。图2(b)的阈值E1由于设置在了 $\mathrm { v _ { E } }$ 点之下，所以检测到了所有的非重叠行车噪声段，但把重叠的行车噪声段也检测成了非重叠行车噪声段；(c)的阈值 $E 2$ 由于设置在了 $\mathrm { v _ { E } }$ 点之上，所以检测到了重叠行车噪声段，但漏检了所有的非重叠行车噪声段。需要注意的是，第3个行车噪声段没有检测出来是因为当前阈值下该行车噪声段长度不满足大于或等于 $l _ { \mathrm { v e h } }$ 的条件。图2(e)(f)的结果分析与图2(b)(c)同理。

# 2.2 SV算法

交通噪声每帧信号 $y _ { i } ( n )$ 的FFT结果 $Y _ { i } ( k )$ 如式(6)所示[21]。其中，当 $k \neq 1$ 时， $\left| Y _ { i } \left( k \right) \right|$ 与 $\left| Y _ { i } \left( N - k + 2 \right) \right|$ 相等，所以，只需要处理 $[ N / 2 ] _ { \mathrm { i n t } } + 1$ 个样本点；同时，频率间隔 $\Delta f = f _ { s } / N$ ， $f _ { \mathrm { s } }$ 表示采样频率。

$$
\begin{array}{c} \left\{ { { Y } _ { i } } \left( k \right) = \sum _ { n = 1 } ^ { N } { { y } _ { i } } \left( n \right) e ^ { - j 2 \pi \left( k - 1 \right) \left( n - 1 \right) / N }  \\ { k = 1 , 2 , \cdots , \ N } \end{array} \right.
$$

由式(6)计算得到的 SV 特征可以用矩阵 $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 表示，如式(7)所示，SV的帧时刻向量 $\mathbf { \Psi } _ { t }$ 和 SV的频率刻度向量 $f$ 如式(8)所示。SV中的横坐标为时间，纵坐标表示频率，坐标点值 $a _ { n i }$ 则表示交通噪声经过FFT后的幅度值； $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 中每一列的频率值与 $f$ 对应， $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 中每一行的时刻值与 $t ^ { \mathrm { T } }$ 相对应。由于是采用二维平面表达三维信息，所以幅度值的大小是通过颜色来表示的，颜色越深则表示该点的幅度值越大，反之则越小。

$$
\begin{array} { r l } & { A _ { \mathrm { s v } } = \left[ a _ { n i } \right] _ { N \times L } = } \\ { \left( \begin{array} { c c c c } { \left| Y _ { 1 } \left( 1 \right) \right| } & { \left| Y _ { 2 } \left( 1 \right) \right| } & { \cdots } & { \left| Y _ { L } \left( 1 \right) \right| } \\ { \left| Y _ { 1 } \left( 2 \right) \right| } & { \left| Y _ { 2 } \left( 2 \right) \right| } & { \cdots } & { \left| Y _ { L } \left( 2 \right) \right| } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { \left| Y _ { 1 } \left( \left[ N / 2 \right] _ { \mathrm { i n t } } + 1 \right) \right| } & { \left| Y _ { 2 } \left( \left[ N / 2 \right] _ { \mathrm { i n t } } + 1 \right) \right| } & { \cdots } & { \left| Y _ { L } \left( \left[ N / 2 \right] _ { \mathrm { i n t } } + 1 \right) \right| } \end{array} \right) } \end{array}
$$

$$
\begin{array} { l } { \displaystyle \int _ { t } = \frac { 1 } { f _ { \mathrm { { s } } } } \big ( ( 0 , 1 , \cdots , \ L - 1 ) ^ { \mathrm { T } } \ d _ { \mathrm { { i n c } } } + \left( 1 , 1 , \cdots , 1 \right) ^ { \mathrm { T } } \big [ N / 2 \big ] _ { \mathrm { { i n t } } } \big ) } \\ { \displaystyle \left( f = \left( 0 , 1 , \cdots , \ L - 1 \right) ^ { \mathrm { T } } \Delta f \right. } \end{array}
$$

根据式 $( 6 ) \sim$ (8)，提取图1 (b)中样本交通噪声的SV特征如图3所示。图3 (a)表示交通噪声 SV特征的提取结果，(b)表示对SV特征的图解分析。其中，黄色S区域表示重叠信号部分上方的噪声区域。可以发现，行车噪声段的颜色相比环境噪声段要深许多。环境噪声段的信息主要分布在低频区域，而行车噪声段的信息则主要从低频连续分布至中高频区域，而且随着频率的增加，行车噪声段的颜色逐渐变浅直至接近环境噪声段的颜色。

对SV特征图解分析后发现：a）非重叠行车噪声段可以根据行车噪声段幅度值大于环境噪声段幅度值的关系直接进行识别；b）S区域几乎没有任何信息且颜色深度几乎与环境噪声的颜色深度相同。所以，根据上述两个特点可以将重叠行车噪声段进行有效分离，然后再转换成识别非重叠行车噪声段的问题。

![](images/bb49570d94bcf15f6eb522c68cbae694dd21c7c31384df4743d0e1fe8618ffd6.jpg)  
Fig.2Endpoints-detection results of sample-traffic-noise with overlapping signals under traditional methods   
图3样本交通噪声的SV特征提取和分析  
Fig.3Extraction and analysis of sample-traffic-noise's SV features

记 $f _ { 0 } , f _ { 1 }$ 分别为预先设定的频率上限和频率下限。记 $\lambda$ 为$f _ { 0 }$ 所在 $| A _ { \mathrm { s v } } \rrangle$ 中的行索引， $\mu$ 为 $f _ { 1 }$ 所在 $| A _ { \mathrm { s v } } \rrangle$ 中的行索引；记tnoveh为前导环境噪声段的时长， $N _ { \mathrm { n o v e h } }$ 为tnoveh 内的样本点数目，$\overline { { a } } _ { \mathrm { n o v e h } }$ 为 $f _ { 1 }$ 上 $t _ { \mathrm { n o v e h } }$ 内的平均幅度值， $\beta$ 为 $\overline { { a } } _ { \mathrm { n o v e h } }$ 的系数且可以调节，用 $\beta \overline { { a } } _ { \mathrm { n o v e h } }$ 表示 SV中无车段的幅度值上限。则 $\lambda \setminus ^ { } \mu \setminus N _ { \mathrm { n o v e h } }$ 和 $\overline { { a } } _ { \mathrm { n o v e h } }$ 的计算如式(9)所示。

$$
\left\{ \begin{array} { l } { \displaystyle \lambda = \big [ f _ { \mathrm { 0 } } / \Delta f \big ] _ { \mathrm { i n t } } + 1 } \\ { \displaystyle \mu = \big [ f _ { \mathrm { 1 } } / \Delta f \big ] _ { \mathrm { i n t } } + 1 } \\ { \displaystyle N _ { \mathrm { n o v e h } } = \big [ f _ { s } t _ { \mathrm { n o v e h } } - N \big ] _ { \mathrm { i n t } } + 1 } \\ { \displaystyle \overline { { a } } _ { \mathrm { n o v e h } } = \frac { 1 } { N _ { \mathrm { n o v e h } } } \sum _ { j = 1 } ^ { N _ { \mathrm { n o v e h } } } a _ { \mu j } } \end{array} \right.
$$

记 $l _ { \mathrm { v e h } }$ ，lnoveh， $Q _ { 0 }$ ， $\boldsymbol { Q }$ 和 $\varepsilon _ { r }$ 均与传统算法中所对应参数的含义相同，记 $\Phi$ 为存放环境噪声端点的集合。SV算法的具体实现步骤如下：

a)初始化fo、 $f _ { 1 }$ 、lveh、lnoveh、tnoveh、 $\beta$ 和 $\boldsymbol { \varepsilon } _ { r }$ ，从 $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 中的第 $\lambda$ 行开始执行。

b)对当前行依次遍历该行的每帧信号的幅度值 $a _ { n i }$ ，若$a _ { n i } > \beta \overline { { a } } _ { \mathrm { n o v e h } }$ 且 $a _ { n r } > \beta \overline { { a } } _ { \mathrm { n o v e h } }$ （ $\dot { \boldsymbol { r } } = \dot { \boldsymbol { { i } } } + 1$ ， $i + 2$ ，…， $i + l _ { \mathrm { v e h } } - 1 )$ ，则令 $i _ { \mathrm { s t a r t } } ^ { Q } = \ i$ ，其中 $i _ { \mathrm { s t a r t } } ^ { Q }$ 就为第 $\boldsymbol { Q }$ 个行车噪声段的起始端点；紧接着从 $i = i + l _ { \mathrm { v e h } }$ 开始继续遍历 $\mathbf { \alpha } _ { a _ { n i } }$ ，直至出现 $a _ { n i } \leq \beta \overline { { a } } _ { \mathrm { n o v e h } }$ 且$a _ { n s } \leq \beta \overline { { a } } _ { \mathrm { n o v e h } }$ （ $s = i + 1$ ， $i + 2$ ，…， $i + l _ { \mathrm { n o v e h } } - 1 )$ 的情况时，则令$i _ { \mathrm { c n d } } ^ { Q } = i \textrm { - } 1$ ，其中 $i _ { \mathrm { e n d } } ^ { Q }$ 就为第 $\boldsymbol { Q }$ 个行车噪声段的结束端点，区间$[ i _ { \mathrm { s t a r t } } ^ { Q }$ ， $i _ { \mathrm { e n d } } ^ { Q }$ ]就表示第 $\boldsymbol { Q }$ 个行车噪声段，同时， $i _ { \mathrm { e n d } } ^ { Q } \mathrm { ~ + ~ } 1$ 表示第 $\boldsymbol { \mathcal { Q } }$ 个环境噪声段的起始端点，然后执行步骤c)。

c)紧接着从 $i = i + l _ { \mathrm { n o v e h } }$ 开始继续遍历 $a _ { n i }$ ，直到出现$a _ { n i } > \beta \overline { { a } } _ { \mathrm { n o v e h } }$ 且 $a _ { n r } > \beta \overline { { a } } _ { \mathrm { n o v e h } }$ （ $r = i + 1$ ， $i + 2$ ，…， $i + l _ { \mathrm { v e h } } - 1 \rangle$ 的情况时，则令 $i _ { \mathrm { s t a r t } } ^ { Q + 1 } = i$ ，其中 $i _ { \mathrm { s t a r t } } ^ { Q + 1 }$ 就为第 $\textstyle Q + 1$ 个行车噪声段的起始端点，即 $i _ { \mathrm { s t a r t } } ^ { Q + 1 } - 1$ 为第 $\boldsymbol { Q }$ 个环境噪声段的结束端点，所以区间$[ i _ { \mathrm { e n d } } ^ { Q } + 1$ ， $i _ { \mathrm { s t a r t } } ^ { Q + 1 } - 1 \mathit { \check { \Omega } } _ { . }$ 就为第 $\boldsymbol { Q }$ 个环境噪声段，然后执行步骤d)。

d)判断区间[ $i _ { \mathrm { e n d } } ^ { Q } + 1$ ， $i _ { \mathrm { s t a r t } } ^ { Q + 1 } - 1 ]$ 是否包含 $\Phi$ 中的某个区间，若不包含，则将该区间放入集合 $\Phi$ ，并将 $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 中由第一行、最后一行、第 $i _ { \mathrm { e n d } } ^ { Q } + 1$ 列和第 $i _ { \mathrm { s t a r t } } ^ { Q + 1 } - 1$ 列所组成的子矩阵的每个值赋值为 $\beta \overline { { a } } _ { \mathrm { n o v e h } }$ ；若包含，则令 $Q = Q \cdot 1$ 。反复执行步骤 b)\~d)，直至遍历完 $ { A _ { \mathrm { s v } } }$ 中第 $\mu$ 行的所有帧信号时才执行步骤e)。

e)统计行车噪声段的数目（即检测车辆数） $\boldsymbol { \mathcal { Q } }$ ，若$| Q - Q _ { 0 } | / Q _ { 0 } \leq \varepsilon _ { r }$ ，则保存当前的fo、fi、lveh、lnoveh、tnoveh、 $\beta$ 或 $\varepsilon _ { r }$ 参数和所有行车噪声段的端点检测结果，然后终止算法；反之，则调节 fo、fi、 $l _ { \mathrm { v e h } }$ 、lnoveh、tnoveh、 $\beta$ 或 $\varepsilon _ { r }$ 参数并从步骤a)重新运行检测算法。

对图1(b)中的样本交通噪声执行SV算法，端点检测结果（亦即车数检测结果）如图4所示，检测结果为5veh，这与真实结果相同。从图4 (a)中可以看到，重叠的行车噪声段已经被较好地分离出来，端点检测结果如图4(b)所示。

![](images/41eea56d4394bead76e36e501a40f954a921487509088963fc1371c89179787e.jpg)  
图4SV算法下含有重叠信号的样本交通噪声端点检测结果 Fig.4Endpoints-detection results of sample-traffic-noise with overlapping signals under SV algorithm

为了更直观地与传统算法进行比较，参考 STAM的定义式(5)，在 SV 特征基础之上定义的短时平均幅度 $\boldsymbol { M } _ { i } ^ { \prime }$ 如式(10)所示。

$$
{ M _ { i } ^ { \prime } = \sum _ { n = 1 } ^ { N } \lvert a _ { n i } \rvert }
$$

其中： $a _ { n i }$ 表示 $ { \boldsymbol { A } } _ { \mathrm { s v } }$ 中的元素。基于 $\boldsymbol { M } _ { i } ^ { \prime }$ 的端点检测结果如图5所示，仍为5veh，这与基于SV特征所检测的结果是相同的（可以证明，端点也是相同的)，通过计算推导也能证明这个结论。所以，可以用SV特征代替 $\boldsymbol { M } _ { i } ^ { \prime }$ 特征。

![](images/7bbd97749c58a1bdd87a94f572082443895a78dc35e7b7449f011fa2c0a0a641.jpg)  
Fig.5Endpoints-detection results of sample-traffic-noise with overlapping signals based on $\mathbf { \nabla } M _ { i } ^ { \prime }$ features

# 3 实验结果及分析

以某条单车道路段为例，利用音频检测器采集该路段的交通噪声，采样时间为 $1 2 6 \mathrm { ~ s ~ }$ ，采样频率 $8 \mathrm { k H z }$ ，通过实验测试，每帧时长取 $2 5 ~ \mathrm { m s }$ （即200个样本点）、帧移时长取12.5ms 时对行车噪声的分析较为合适。交通噪声滤波降噪前后的波形分别如图6 (a)(b)所示。可以看到，真实车辆数为25，折合成小时交通量为 $7 1 4 ~ \mathrm { v e h / h }$ 。重叠噪声段的数目为7，交通噪声的信噪比在经过LMS自适应滤波器后有了较大提升。

![](images/6e6f3c5c72a67f26dbe5651a6f0dc0beb171d8539ac94efcda24cd38db582c84.jpg)  
图6经LMS滤波器降噪前后的交通噪声  
Fig.6Traffic noise before and after being denoised viaLMS filtei

首先，根据图2和4分别确定出传统算法和SV算法的基本参数（即需要初始化的各个参数)。基于STE、STAM和SV算法的车辆数检测结果分别如图7(a)\~(c)所示。从图中可以直接看出，基于STE 检测的车辆数为18，基于STAM检测的车辆数也为18，基于SV检测的车辆数为23，而真实的车辆数应当为25；STE和STAM算法均没有检测出重叠的行车噪声段，而SV算法检测出了5个重叠行车噪声段，漏检了2个重叠行车噪声段。

按照图3 (b)中的图解分析思路，SV算法应当可以检测出图6中的所有7个重叠行车噪声段，但是仔细观察图7(c)未被分离开的第3个和第5个重叠行车噪声段就会发现：第3个重叠行车噪声段并不存在图3(b)中所描述的S区域；而第5个重叠行车噪声段虽然存在S区域，但S区域却很窄（宽度比lnoveh还小）且处于重叠部分的内部，此时仅仅依靠调节参数还是无法检测出来。其他的重叠行车噪声段之所以可以被准确地检测出来，是因为它们均存在与图3(b)中比较类似的S区域。

![](images/7e17f24467b33ce86cfd16dcf3ebb9e2598046feed90fa3dde2fc6965acad54c.jpg)  
(a)STE特征下的交通噪声端点检测结果

![](images/cc63ca9a3bff78f3491ce50fdaf397a87606f47c63ef3183a765d6443a79e9fe.jpg)  
(a) Endpoints-detection results of traffic noise based on STE

(b)Endpoints-detection results of traffic noise based on STAM

![](images/52c7729d1409fbf7c48446e2e8d04589fc39b9a3302628ad459520410e53c768.jpg)  
(b)STAM特征下的交通噪声端点检测结果  
图7传统算法下和SV算法下的端点检测结果 Fig.7Endpoints-detection results separately based on traditional algorithmand SValgorithm

基于STE、STAM和SV 的端点检测算法在126 s内检测出的车辆数折合成小时交通量分别为514veh/h、514veh/h和657veh/h，计算出绝对误差、相对误差和准确率并整理成表格，结果如表1所示。

从表1可以看出，基于STE 算法的检测交通量与基于STAM算法的检测交通量的准确率均为 $7 2 \%$ ，基于SV算法的检测交通量的准确率为 $9 2 \%$ ，SV 算法比传统算法的准确率高出 $20 \%$ 。

# 表1各个特征参数下的交通量检测结果

Table1Traffic detection results under various features   

<html><body><table><tr><td>特征</td><td>检测交通量/veh/h</td><td>实际交通量/veh/h</td><td>e/veh/he/%</td><td></td><td>准确率/%</td></tr><tr><td>STE</td><td>514</td><td>714</td><td>200</td><td>28</td><td>72</td></tr><tr><td>STAM</td><td>514</td><td>714</td><td>200</td><td>28</td><td>72</td></tr><tr><td>SV</td><td>657</td><td>714</td><td>57</td><td>8</td><td>92</td></tr></table></body></html>

# 4 结束语

鉴于短时能量、短时平均幅度特征无法有效分离重叠行车噪声信号的问题，本文提出了一种利用交通噪声检测交通量的新方法一一SV算法，并对比了传统的STE 和STAM算法，得出结论如下：

a）传统算法与SV算法的相同之处在于，两者均利用了双门限判决原理，且都能很好地实现非重叠行车噪声段的检测；不同之处在于，传统算法无论怎样调节双门限阈值等参数，均不能保证在检测出重叠行车噪声段的同时，也能较多地检测出非重叠行车噪声段，而后者却可以。b）从检测交通量的结果来看，SV算法的准确率比传统算法提高了 $20 \%$ ，关键就在于SV算法比传统算法多检测出了重叠行车噪声段数目。c）本文提出的SV算法仍然不能 $100 \%$ 检测出所有的重叠行车噪声段，原因在于，并非所有的重叠行车噪声段均符合图3(b)中的S区域的特点，满足该特点的重叠行车噪声段则可以被准确地检测出来，反之则不行。d）接下来的研究中会对SV算法进行改进以适应当前存在的问题，也会继续增大实验数据量，以验证并提高算法的准确性和稳定性。

# 参考文献：

[1]Basner M,Babisch W,Davis A,et al.Auditory and non-auditory effects of noise on health [J]. The Lancet,2014,383 (9925):1325-1332.   
[2]Khademian M,Homayounpour M M.Monaural multi-talker speech recognition using factorial speech processing models [J].Speech Communication,2018,98:1-16.   
[3]Kumar P,Nigam S P, Kumar N. Vehicular traffic noise modeling using artificial neural network approach [J]. Transportation Research Part C: Emerging Technologies,2014,40:111-122.   
[4]Morel J,Marquis-Favre C,Gille L A.Noise annoyance assessment of various urban road vehicle pass-by noises in isolation and combined with industrial noise:a laboratory study [J].Applied Acoustics,2016, 101: 47-57.   
[5]Coensel B D,Brown AL,Tomerini D.A road traffic noise pattern simulation model that includes distributions of vehicle sound power levels [J]. Applied Acoustics,2016,111: 170-178.   
[6]Can A,Leclercq L,Lelong J,et al.Accounting for traffic dynamics improves noise assessment:experimental evidence [J].Applied Acoustics,2009,70 (6): 821-829.   
[7]Can A,Leclercq L,Lelong J,et al. Traffic noise spectrum analysis: dynamic modeling Vs.experimental observations [J].Applied Acoustics, 2010,71 (8): 764-770.   
[8]Tyagi V,Kalyanaraman S,Krishnapuram R.Vehicular traffic density state estimation based on cumulative road acoustics [J]. IEEE Trans on Intelligent Transportation Systems,2012,13 (3): 1156-1166.   
[9]Joshi V,Rajamani N,Prathapaneni N,et al. Traffic density state estimation based on acoustic fusion [C]//Proc of IEEE International Conference on Acoustics，Speech and Signal Processing.Vancouver, BC:IEEEPress,2013:478-482.   
[10]BhandarkarM,WaykoleT.Vehicularmechanicalcondition determination and on road traffic density estimation using audio signals [C]/Proc of CICN International Conference on Computational Intelligence and Communication Networks.New York:CICN Press, 2014:395-401.   
[11]Borkar P,Sarode M,Malik L.Employing speeded scaled conjugate gradient algorithm for multiple contiguous feature vector frames:an approach for traffic density state estimation [J].Procedia Computer Science,2016,78: 740-747.   
[12]关博文，李硕，姜艺，等.LOS声屏障降噪效果评价[J].交通运输 工程学报,2015,15 (4):26-33.(Guan Bowen,Li Shuo,Jiang Yi,et al. Noise reduction effect evaluation of LOS noise barrier [J].Journal of Traffic and Transportation Engineering,2015,15(4):26-33.)   
[13]Alexandre E,Cuadra L,Salcedo-Sanz S,et al.Hybridizing extreme learning machines and genetic algorithms to select acoustic features in vehicle classification applications [J]．Neurocomputing，2O15,152: 59-68.   
[14]Lefebvre N,Chen Xiaodong,Beauseroy P,et al.Traffic flow estimation using acoustic signal [J].Engineering Applications of Artificial Intelligence,2017,64:164-171.   
[15] Mato-Mndez FJ,Sobreira-Seoane M A.Blind separation to improve classification of traffic noise [J].Applied Acoustics,2011,72 (8): 590-598.   
[16] TorijaJA,Ruiz PD.Using recorded sound spectra profile as input data for real-time short-term urban road-traffic-flow estimation [J]. Science of the TotalEnvironment,2012,435:270-279.   
[17] Dennis J,Tran H D,Chng E S.Overlapping sound event recognition using local spectrogram features and the generalised hough transform [J].Pattern Recognition Letters,2013,34:1085-1093.   
[18]何小华．基于车辆运行噪声的交通量在线统计算法研究[D].长春： 东北师范大学,2Oo8.(He Xiaohua.Research on online traffic volume statistics algorithm based on vehicle running noise [D]. Changchun: Northeast Normal University,2008.)   
[19] Gao Ye,Ni Jing'en,Chen Jie,etal.Steady-state and stability analyses of diffusion sign-error LMS algorithm[J]. Signal Processing,2O18,149: 62-67.   
[20] Onumanyi AJ,Abu-Mahfouz AM,Hancke G P.A comparative analysis of local and global adaptive threshold estimation techniques for energy detection in cognitive radio [J].Physical Communication,2O18,29: 1-11.   
[21] JodraLJ,Gurrutxaga I,Muguerza J,et al.Solving Poisson's equation using FFT in a GPU cluster [J].Journal of Parallel and Distributed Computing,2017,102:28-36.