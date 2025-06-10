# 一种用于空间VLBI的射电源条纹搜索算法

朱晓娜1²，童力1,3,4.5，郑为民1,3,4.5，张娟1,3,4,.5（1．中国科学院上海天文台，上海 200030；2．中国科学院大学，北京100049;3．国家基础学科公共科学数据中心，北京100190；4.中国科学院射电天文重点实验室，江苏南京 210033；5．上海市导航定位重点实验室，上海 200030)

摘要：我国探月工程嫦娥七号将构建由中继星上4.1m口径抛物面天线及地基射电望远镜组成的首个月地空间甚长基线干涉测量（Very Long Baseline Interferometry，VLBI)试验系统。不同于地基甚长基线干涉测量望远镜，受中继星轨道扰动和设备时延影响，射电源预报时延模型和实际时延有时可能会有较大差异，导致无法引导VLBI相关处理机正常工作，需要通过射电源条纹搜索方法寻找实际时延模型才能解决这一问题。由于4.1m空间天线口径较小，接收信号能力弱。为提高信噪比，需要长时间积分，而线性时延模型无法保证长时间的时延精度。针对这一问题，提出了一种用于空间甚长基线干涉测量的射电源条纹搜索算法，首先通过建立时延和时延率的二维搜索网格，使用每个网格点对应的先验时延和时延率构建线性时延模型；再使用该线性时延模型对原始数据分时段相关处理；然后采用二维傅里叶变换搜索残余时延和时延率，确定最大的相关幅度值对应的网格点；最后使用该网格点的先验时延和时延率以及残余时延和时延率重构二次项时延模型。通过对RadioAstron空间甚长基线干涉测量的地空基线实际数据处理，验证了该射电源条纹搜索算法的正确性。

关键词：空间VLBI；条纹搜索；时延模型；相关处理；射电源中图分类号：TN216 文献标识码：A 文章编号：1672-7673（2022）06

甚长基线干涉测量是一种具有高分辨率、高精度特点的射电干涉技术。它采用原子钟控制的高稳定独立本振系统和数据采集装置，通过多个望远镜同时接收目标源信号，记录数据并发送到异地的数据处理中心，经处理得到观测结果。在VLBI观测中，两台射电望远镜间的距离称为基线，它决定甚长基线干涉测量的最大分辨率2，若有空间望远镜与地面望远镜构成空地甚长基线干涉测量系统，基线长度超过地球直径，可实现更高的分辨率。我国探月工程四期任务将利用嫦娥七号中继星上的4.1m口径抛物面天线，进行月地空间甚长基线干涉测量试验。不同于常规地基甚长基线干涉测量[3，受中继星轨道扰动和设备时延的影响，射电源预报时延模型可能和实际时延有较大差异，无法引导相关处理机正常工作。通过射电源条纹搜索，可确定实际相关处理机所需的高精度时延模型，用于空间甚长基线干涉测量空地基线相关处理。

目前，在探月工程中，探测器信号相关处理时，采用差分单向测距(DifferentialOne-way Ranging，DOR)信号的点频信号特征来设计条纹搜索算法[4]。而射电源信号是白噪声信号，无法利用现有探测器信号搜索算法。目前针对射电源信号的条纹搜索有eFFT条纹搜索算法、CAF-W条纹搜索算法[5]和多重网格条纹搜索算法[6]。eFFT条纹搜索算法和CAF-W条纹搜索算法可实现残余时延和时延率的计算，但主要用于强源的时延模型搜索。多重网格条纹搜索算法的基本思想是建立多层次、不同尺寸的网格，通过这些网格，在不同范围内搜索需要的目标值。多重网格条纹搜索算法使用线性时延模型进行相关处理，在时延-时延率平面中搜索条纹，适用于信号较强，短时间积分就能得到条纹的应用场景。由于空间小口径天线接收信号较弱，获得干涉条纹需要进行较长积分时间。使用通常的线性时延模型无法保证较长时间范围内的相关处理机模型时延精度，需设法构造精度更高的二次项时延模型。如果在常规多重网格中增加时延二次项，会使搜索空间从二维扩展到三维，计算复杂度增加一个量级。

本文基于多重网格条纹搜索算法，提出了一种用于空间甚长基线干涉测量的射电源条纹搜索算法：首先建立关于时延和时延率的二维搜索网格，使用每个网格点对应的先验时延和时延率信息构建线性时延模型，对原始数据分时段相关处理；然后由二维傅里叶变换求解残余时延和时延率后进行补偿，得到每个时段的时延和时延率，计算每个网格点对应的相关幅度值；最后在最大相关幅度值对应的网格点上重构二次项时延模型。采用该算法，对俄罗斯RadioAstron空间甚长基线干涉测量的实际观测数据进行相关处理时取得了较好的效果。

# 1射电源条纹搜索算法

目前中国甚长基线干涉测量网软件相关机使用五次项时延模型进行相关处理。在条纹搜索的过程中，为减少计算复杂度，通常使用由时延常数项和时延一次项系数构成的线性时延模型。但随着时间范围的扩大，线性时延模型的误差与五次多项式模型的误差也会增加。综合考虑到条纹搜索计算量与模型精度因素，我们设法构建由常数项、一次项系数和二次项系数构成的二次项时延模型。

# 1.1相关处理算法

假设两台站接收的目标源射频信号分别为 $\dot { s } _ { 1 } ( t )$ 和 ${ \bf \dot { \sigma } } _ { S _ { 2 } } ( t )$ ，同一波前信号到达两台站时延 差为τ，则

$$
s _ { 2 } ( t ) = s _ { 1 } ( t + \tau ) .
$$

由射频信号得到的基频信号

$$
\begin{array} { r } { x _ { 1 } ( t ) = s _ { 1 } ( t ) e ^ { - j 2 \pi f _ { 0 } t } , \quad \quad } \\ { x _ { 2 } ( t ) = s _ { 2 } ( t ) e ^ { - j 2 \pi f _ { 0 } t } = s _ { 1 } ( t + \tau ) e ^ { - j 2 \pi f _ { 0 } t } , \quad \quad } \end{array}
$$

其中， $f _ { 0 }$ 为通道的天空频率。

相关处理以台站1为参考，使用预报模型 $\boldsymbol { \tau _ { c } }$ 对台站2进行时延补偿，即

$$
x _ { 2 } ( t - \tau _ { c } ) = s _ { 2 } ( t - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } ( t - \tau _ { c } ) } = s _ { 1 } ( t + \tau - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } ( t - \tau _ { c } ) } ,
$$

经过条纹旋转后

$$
x _ { 2 } ( t - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } \tau _ { c } } = s _ { 2 } ( t - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } t } = s _ { 1 } ( t + \tau - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } t } .
$$

对台站1和台站2的信号进行傅里叶变换

$$
x _ { 1 } ( \mathrm { t } ) \overset { F F T } { \Longrightarrow } S _ { 1 } ( f + f _ { 0 } ) ,
$$

$$
x _ { 2 } ( t - \tau _ { c } ) e ^ { - j 2 \pi f _ { 0 } \tau _ { c } } \overset { F F T } { \Longrightarrow } S _ { 2 } ( f + f _ { 0 } ) e ^ { - j 2 \pi ( f + f _ { 0 } ) \tau _ { c } } = S _ { 1 } \big ( f + f _ { 0 } \big ) e ^ { - j 2 \pi ( f + f _ { 0 } ) ( \tau _ { c } - \tau ) } .
$$

$S _ { 1 } ( f + f _ { 0 } )$ 为台站1信号经过频率转换后的功率谱，共轭相乘得两台站的互相关功率谱为

$$
P _ { 1 2 } ( f ) = \big | S _ { 1 } \big ( f + f _ { 0 } \big ) \big | ^ { 2 } e ^ { - j 2 \pi ( f + f _ { 0 } ) ( \tau _ { c } - \tau ) } .
$$

由（7）式可知，当残余时延 $\tau _ { c } - \tau$ 达到最小值时，两台站的互相关功率谱达到最大峰值。

1.2残余时延搜索算法

图12-D傅里叶变换残余时延搜索图  
![](images/5fdab7a297fdc85701208333594254ed270e546f89eb293e4674a62c69216562.jpg)  
Fig.1 Search function

根据二维傅里叶变换的性质可知，相关处理得到的互相关谱二维傅里叶变换后，可以得到一个关于残余时延和时延率的二维互相关函数，如图1，其公式为

$$
\begin{array} { r } { F ( \Delta \tau , \Delta \dot { \tau } ) = \left| \int _ { 0 } ^ { B } \left\{ \int _ { 0 } ^ { T } P _ { 1 2 } ( f , t ) e ^ { - i 2 \pi f _ { 0 } \Delta \dot { \tau } t } d t \right\} e ^ { - i 2 \pi \Delta \tau f } d f \right| , } \end{array}
$$

其中， $\Delta \tau$ 为残余时延； $\Delta { \dot { \tau } }$ 为残余时延率； $B$ 为通道带宽；7为一组二维傅里叶变换的数据时长； $f _ { 0 }$ 为天空频率； $F ( \Delta \tau , \Delta \dot { \tau } )$ 为不同残余时延和时延率下的相关幅度值； $P _ { 1 2 } ( f , t )$ 为相关处理后的互相关功率谱。

将（8）式离散化，即

$$
\begin{array} { r } { F ( a _ { r } , b _ { r } ) = \left| \frac { 2 B T } { N M } \sum _ { n = 0 } ^ { N - 1 } \left\{ \sum _ { m = 0 } ^ { M - 1 } P _ { 1 2 } ( n , m ) e ^ { - i 2 \pi f _ { 0 } b _ { r } m T / M } \right\} e ^ { - i 4 \pi a _ { r } n B / N } \right| , } \end{array}
$$

其中， $F ( a _ { r } , b _ { r } )$ 为经过二维傅里叶变换后得到的相关幅度值； $a _ { r }$ 和 $b _ { r }$ 分别为离散化后的残余时延和时延率； $N$ 为频域的傅里叶变换点数；M为时域的傅里叶变换点数。

1.3条纹搜索与二次项时延模型重构流程

根据以上原理，对于空间甚长基线干涉测量射电源条纹搜索与二次项时延模型重构流程如图2。

![](images/066748f7add62bca58c334f666da04c512f8dbde58f85d125070b964202bf73e.jpg)  
图2射电源条纹搜索搜索与二次项时延模型重构流程图

Fig.2 Flow chart of radio source fringe search and quadratic term delay model reconstruction

由二维傅里叶变换的性质可知，相关后二维傅里叶变换的残余时延和时延率的范围分别为 $\left[ - \frac { N } { 4 B } , \frac { N } { 4 B } \right]$ ， $\left[ - \frac { M } { 2 f _ { 0 } T } , \frac { M } { 2 f _ { 0 } T } \right]$ ，因此，时延和时延率两个维度搜索步长应在此范围内。根据对实测数据的处理经验，设置时延步长为

$$
\begin{array} { r } { d _ { s t e p } = \frac { N } { 1 0 B } , } \end{array}
$$

时延率步长为

$$
\begin{array} { r } { d r _ { s t e p } = \frac { M } { 2 f _ { 0 } T } . } \end{array}
$$

条纹搜索的步长与时延模型精度和计算量密切相关，如果搜索步长设置过大，可能得到的模型精度太低无法用于后续数据处理；如果步长设置太小，由于目前的算法采用全网格搜索策略，依次计算每个网格点数据会极大影响整体的计算效率。注意到步长设置较小时可能会有多组网格点搜索到满足精度要求的模型，后续会研究基于二维随机游走的网格搜索策略，找到合适的时延模型就停止计算，这样可以有效地提高效率。

确定步长后，根据搜索范围和先验时延模型划分网格点。每个网格点对应不同时延和时延率，代表经过不同时延补偿的数据处理。如图3，以先验时延模型中的时延和时延率为中心点，等步长计算每个网格点对应的时延和时延率值。

由于弱信号使用线性时延模型进行长时间积分无法保证时延精度，获得干涉条纹，所以将原始数据划为I组较短的数据段进行处理，每一组为一个二维傅里叶变换组，时间长度为T。在每个网格点上构造线性时延对原始数据补偿后进行相关处理，相关处理的积分时间为T/M，一个二维傅里叶变换组的数据大小为 $M \times N$ 。得到两台站的互相关功率谱后，利用（9）式对每一组的相关谱进行二维傅里叶变换，得到每个网格点上的组残余时延、时延率和相关幅度值，利用最大相关幅度的平均值确定最优解对应的网格点，在该网格点上进行时延和时延率的拟合，得到最优的二次项时延系数。

![](images/563a994c6f262190b746fe7c111a9af08f2495a65daa0a81ff5eb6e7722a3870.jpg)  
图3二维网格示意图  
Fig.3 Schematic diagram of two-dimensional grids

在拟合时，将每一组的残余时延 $a _ { i } ^ { r }$ 和时延率 $b _ { i } ^ { r }$ ，与相关处理预报时延模型中的初始时延 $a _ { i } ^ { c }$ 和时延率 $b _ { i } ^ { c }$ 相加，可以得到该组的时延 $a _ { i }$ 和时延率 $b _ { i }$ ，即

$$
a _ { i } = a _ { i } ^ { c } + a _ { i } ^ { r } ,
$$

$$
b _ { i } = b _ { i } ^ { c } + b _ { i } ^ { r } .
$$

甚长基线干涉测量观测具有时间连续性，时延模型也应该是连续的。但在求解残余时延的过程中，数据分段导致每一组之间的时延具有间断点，在拟合二次项时延系数时，需要根据连续的约束条件，即保持第1组的时延 $a _ { 0 }$ 不变，修正其余组的时延 $a _ { i }$ ，使之与前一组末的时延相等，即

$$
\displaystyle { \int _ { a _ { i } ^ { m } = a _ { i - 1 } + b _ { i - 1 } T } ^ { a _ { 0 } ^ { m } } , \ 0 < i < I } \quad ,
$$

其中， $a _ { i } ^ { m }$ 为改正后的时延； $I$ 为二维傅里叶变换组的个数。

经过上述时延改正后，再进行二次项时延系数的拟合。设未知的二次项时延系数为$\left[ x _ { 0 } x _ { 1 } x _ { 2 } \right]$ ，求解时延的多项式为

$$
a _ { i } ^ { m } = x _ { 0 } + x _ { 1 } t _ { i } + x _ { 2 } t _ { i } ^ { 2 } ,
$$

其中， $t _ { i } = i \times T$ 为每个二维傅里叶变换组开始的时间。

对（15）式右端求导，得到时延率的多项式为

$$
b _ { i } = x _ { 1 } + 2 x _ { 2 } t _ { i } .
$$

联立（15）式和（16）式建立超定方程组，再利用正交三角分解法求解[9]。

# 2算法验证

RadioAstron项目是苏联在20世纪80年代中期提出的一项空间甚长基线干涉测量（SVLBI）计划。2011年，俄罗斯发射了10m口径的RadioAstron空间射电望远镜（Spektr-R,Ra）卫星。Ra与地面多个大型射电望远镜构成了空间甚长基线干涉测量系统。其接收频段为0.3GHz，1.6GHz，5.0GHz和22GHz，轨道高度近地点 $6 0 0 \mathrm { k m }$ ，远地点 $3 3 0 0 0 0 \mathrm { k m }$ ，通过联合地面望远镜进行干涉测量。

为验证空间甚长基线干涉测量射电源条纹搜索算法，我们使用2014年空间射电望远镜Ra与美国阿雷西博射电望远镜（Arecibo RadioTelescope，Ar）联合观测射电源 $\boldsymbol { 0 8 2 3 + 0 3 3 }$ 的数据进行干涉处理。观测起始时间为2014年4月11日23时07分00秒，结束时间为2014年4月11日23时07分59秒。其中Ar站为2比特量化，4比特扇出的数据，空间站Ra为1比特量化，2比特扇出的数据。天空频率 $4 8 3 6 \mathrm { { M H z } }$ ，带宽 $1 6 \mathrm { M H z }$ ，积分时间为 $8 . 1 9 2 \times 1 0 ^ { - 3 } \mathrm { s }$ ，相关处理后的数据规格为 $6 0 \times 1 2 0 \times 8 1 9 2$ ，利用每 $1 2 0 \times 8 1 9 2$ 个点的数据为一组进行二维傅里叶变换。由（10）式和（11）式确定时延和时延率方向的搜索的步长为

$$
\begin{array} { r } { d _ { s t e p } = \frac { N } { 1 0 B } = 1 . 0 2 4 0 0 \times 1 0 ^ { - 4 } s , } \end{array}
$$

$$
\begin{array} { r } { d r _ { s t e p } = \frac { M } { 2 f _ { 0 } T } = 1 . 2 6 2 1 0 \times 1 0 ^ { - 8 } s / s . } \end{array}
$$

以先验时延模型作为搜索的中心点，时延和时延率搜索的网格大小为 $2 0 \times 2 0 0$ ，其中时延的搜索范围为 $6 . 3 3 6 0 0 \times 1 0 ^ { - 3 } s { \sim } 8 . 2 8 1 6 0 \times 1 0 ^ { - 3 } s$ ，时延率的搜索范围为 $1 . 6 2 7 0 0 \times$ $1 0 ^ { - 6 } s / s { \sim } 4 . 1 3 8 5 8 \times 1 0 ^ { - 6 } s / s$

算法验证时，首先采用常规多重网格条纹搜索算法，仅使用线性时延模型，对每个网格点相关处理，得到峰值点的干涉条纹图。再使用本文研究的射电源条纹搜索算法构建二次项时延模型，最后对两者的结果比较验证。

图4(a)为直接利用线性时延模型进行条纹搜索的相关幅度图，其峰值点对应的网格位置为（15，158），相关幅度值为 $2 . 8 6 9 0 0 \times 1 0 ^ { - 4 }$ ，图4(b)为峰值点对应的条纹相位。图中没有明显的干涉条纹。

![](images/5ca88ed31cdf78f8ba9165823d54b0c60115aa124d12640572cffe00380b25e4.jpg)  
图4使用条纹搜索和线性时延无法得到正确条纹。（a）相关幅度图；（b）干涉条纹图

Fig.4Fringe search using lineardelaycan not produce the fringe.(a) Correlationamplitude;(b)interference fringe

图5为空间甚长基线干涉测量射电源条纹搜索算法得到的不同网格点对应的相关幅度值，峰值点对应的网格位置为（11，101），相关幅度值为 $1 . 9 6 7 0 0 \times 1 0 ^ { - 3 }$ ，经过拟合后得到二次项时延系数 $\left\lceil 7 . 3 6 8 7 5 \times 1 0 ^ { - 3 } s \right.$ ， $2 . 8 8 7 8 4 \times 1 0 ^ { - 6 } s / s$ ， $- 4 . 2 9 9 8 9 \times 1 0 ^ { - 1 1 } s / s ^ { 2 } ]$ 。使用该二次项模型做相关处理，可得到图6(a)的干涉条纹。图6(b)为解卷绕之后的条纹结果。可见，本文提出的算法在处理RadioAstron数据时要优于多重网格条纹搜索算法。

![](images/85a064bb49c0158feca1f445f3b915927c7438a996f4ace725d073751add8406.jpg)  
图5二次项时延补偿的相关幅度

![](images/6ce8b25792687cbdf792bd8ee325b10f6d45159df06253dabe9ec72ebcd0216c.jpg)  
Fig.5 Correlation amplitude using quadratic delay   
图6 采用二次项时延补偿后获得清晰的干涉条纹。（a）解卷绕之前的干涉条纹；（b）解卷绕之后的干涉条纹 Fig.6 Clear interferencefringes are obtained byquadratic time delaycompensation.(a)Phase wrapping;(b)phase

unwrapping

该算法原理样机在Linux集群平台，采用计算节点间 $\mathrm { M P I ^ { + } }$ 节点内POSIX多线程的两级并行实现，计算节点的中央处理器型号为英特尔的Xeon E5-2620，主频为2GHz，每个节点的中央处理器个数为12，运行耗时如表1。后续通过优化，运行速度可进一步提高。

表1空间VLBI射电源条纹搜索算法运行耗时  
Table 1 Time consuming of the radio source fringe search algorithm for space VLBI   

<html><body><table><tr><td>Number of nodes*Number of threads</td><td>Grid points(delay*delay rate)</td><td>Time consuming</td></tr><tr><td>10*10</td><td>20*200</td><td>About 45 minutes</td></tr></table></body></html>

# 3结论

在将来探月四期任务中，地月空间甚长基线干涉测量试验系统受中继星轨道扰动和设备时延影响，可能导致射电源预报时延模型和实际时延有较大差异。本文在常规多重网格条纹搜索基础上，根据空间甚长基线干涉测量信号弱的特点，提出了一种适用于空间甚长基线干涉测量的射电源条纹搜索算法，该算法先建立关于时延和时延率的二维搜索网格，使用线性时延相关处理，然后由二维傅里叶变换搜索残余时延和时延率，最后重构二次项时延模型。本文使用RadioAstron数据验证算法，结果表明在使用常规线性时延模型搜索无法实现空地基线条纹的情况下，新算法可以得到清晰的空间甚长基线干涉测量射电源干涉条纹。经进一步测试和完善，该算法可应用于我国后续空间甚长基线干涉测量。

# 参考文献

[1] BROTEN N W，CLARKE R W，LEGG TH,etal.Diameters of some quasars at a wavelength of 66.9cm［J]．Nature, 1967,10:44-45.   
[2] 钱志瀚，邬林达．甚长基线干涉测量 [M]．北京：测绘出版社，1983:116-119. QIAN ZH,WUL D.Very Long Baseline Interferometry [M].Bejing:SinoMaps Press，1983：116-119.   
[3] LIAO SL,TANG ZH,QIZ X.A model of geometric delay in Space VLBI[J].Research in Astronomy and Astrophysics, 2014,14(8) :1029-1036.   
[4] 郑为民，舒逢春，张冬．应用于深空跟踪测量的VLBI软件相关处理技术［J]．宇航学报，2008,29(1):18-24. ZHENG WM,SHUFC，ZHANG D.Application of software correlator to deep Space VLBI tracking［J].Journalof Astronautics，2008,29(1) :18-24.   
[5] ZHANG TY，MENGQ,CHENCY，etal.A model-free CAF fringe search algorithm with wavelet boosting for VLBI observation ［J].Publications of the Astronomical Society of the Pacifific,2017,129(977):074501.   
[6] 孙晓彤，童力，郑为民，等．基于多重网格的射电源条纹搜索算法研究［J]．天文研究与技术，2021,18(1):52-59. SUN XT,TONG L,ZHENG WM,et al．Research on radio source fringe search algorithm based on multi-grid[J]. Astronomical Research & Technology，2021,18(1) :52-59.   
[7] COTTON W D. Fringe-fitting [C]// Proceedings of the ASP Conference Series.1995:189-208.   
[8] TAKAHASHIF,KONDT,TAKAHASHY,etal.VeryLong Baseline Interferometer[J].AerospaceandElectronic Systems Magazine，2000,17(8):43-44.   
[9] 周玉兴，涂火年，区丽云．基于QR分解的线性方程组 $\operatorname { A x } = 6$ 解的结构[J]．海南大学学报自然科学版， 2013,31(4):289-291,294. ZHOUY X,TUHN,OUL Y. Structure of solutions of linear equations Ax $\boldsymbol { \mathbf { \rho } } = \boldsymbol { \mathbf { b } }$ based on QR decomposition ［J].Natural Science Journal of Hainan University，2013,31(04) :289-291,294.

# A radio source fringe search algorithm for space VLBl

Xiaona Zhu12，Li Tong1,3,4.5 Weimin Zheng1,3,4,5, Juan Zhang1,3,4,5 (1.Shanghai AstronomicalObservatoryChieseAcademyofSciences，hanghaiOoo,China;2.UniversityofChineseAcadeyf Sciences，Beijing 0049，China;3.NationalBasicPublic ScienceDataCenter,Beijing10190,China;4.KeyLaboratoryofRadio Astronomy,CineseAcademyofiences,njingo,China;5.anghaiKeyLboratoryofvigatioandPosiioingai 200030，China)

Abstract: The fourth phase of China's lunar exploration project will build the first lunar terrestrial Space VLBI test system composed of $4 . 1 \mathrm { m }$ antenna on Chang'e 7 relay satellite and ground-based radio telescope.Different from the ground-based VLBI system, due to the influence of relay satellite orbit disturbance and equipment delay,the predicted delay model of radio source may be quite different from the actual delay,which can not guide the relevant processors as the core equipment of VLBI data processing to work normally. In this paper, a radio source fringe search algorithm for Space VLBI is proposed. Aiming at the characteristics of weak signal receiving ability of space small aperture antenna and the need to use quadratic delay model to ensure long-time integration accuracy， firstly,a two-dimensional search grid about delay and delay rate is established, Using the prior delay and delay rate information of each grid point, the linear delay is constructed to process the original data in different time periods,and then the residual delay and delay rate are searched by two-dimensional Fourier transform to determine the grid point corresponding to the maximum correlation amplitude value. Finally, the quadratic delay model is reconstructed by using the delay corresponding to the grid point. The algorithm can be applied to the radio source fringe search of the ground air baseline of the RadioAstron project.

Key words:Space VLBI; Fringe search; Delay model; Correlation processing; Radio source