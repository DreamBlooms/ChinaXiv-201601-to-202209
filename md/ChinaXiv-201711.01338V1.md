# 脉冲星搜索技术及FAST望远镜脉冲星搜索展望

潘之辰，钱磊，岳友岭（中国科学院国家天文台，北京100012)

摘要：分析现有的脉冲星搜索方法对于即将开展的FAST望远镜早期脉冲星搜索的可行性和必要性，尝试脉冲星搜索数据处理的软、硬件加速。回顾并总结了现有的脉冲星搜索方法和这些方法对应的发现，分析这些方法的特点。编写了基于PRESTO的并行数据处理程序。估计了使用显卡计算加速来完成单脉冲搜索的可行性和效率。编写的基于PRESTO的并行数据处理程序使得处理帕克斯望远镜多波束巡天的一个典型大小(100 MB)的文件的时间从约 $9 5 ~ \mathrm { m i n }$ 缩短到短于 $1 0 ~ \mathrm { m i n }$ 。使用显卡加速的单脉冲搜索实现了大约20倍的加速，数据处理时间短于获取观测数据的时间。对于使用望远镜早期观测数据进行脉冲星搜索而言，用于短轨道周期脉冲星搜索的相位调制搜索算法是没有必要的，用于搜索较长轨道周期的加速搜索算法也不十分必要，而用于长自转周期脉冲星搜索的快速折叠算法仅在需要搜索长自转周期的弱脉冲星时才需要使用。在数据处理过程中，软、硬件等方面可以加快数据处理的速度，可以使数据处理用时短于获取数据的时间。

关键词：脉冲星；射电望远镜；FAST中图分类号：P162.4 文献标识码：A 文章编号：1672-7673(2017)01-0008-09

到目前为止，已经发现超过2500 颗脉冲星①，其中，一些特殊脉冲星的发现带来了新的认识。脉冲双星[1和双脉冲星[2的发现提供了在更高精度上检验广义相对论的机会；毫秒脉冲星[3」的发现进一步限制了致密星的物态方程；球状星团中大量毫秒脉冲星（例如，文「4]发现Terzan5球状星团中的 21颗毫秒脉冲星)的发现对球状星团的演化过程给出了限制；银心附近脉冲星的发现表明，银心附近具有非常高的电子密度（如位于银心附近的J1745-2900，色散高达 $1 7 7 8 \ \mathrm { c m } ^ { - 3 } \ \mathrm { p c } ^ { [ 5 ] }$ )；在M31视线方向的X射线脉冲星[的发现意味着河外脉冲星的科学即将开始。

更高效地发现新的脉冲星需要在硬件或软件上有新的突破。在硬件方面，更大的望远镜接收面积、更低的接收机噪声都有助于提高观测的灵敏度；而更强大的计算机则可以提高数据处理效率。在软件方面，为了更快地处理观测数据，更有效地移除观测数据中的干扰以及搜索观测数据中可能存在的脉冲星，尝试各种方法用于搜索观测数据中的周期信号。作为目前在建的全世界最大的单天线望远镜， $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜（Five-hundred-meter Aperture Spherical radio Telescope，FAST[7]）已于2016年9月25日竣工。本文回顾过去十几年常用的低频射电脉冲星观测数据的处理方法，分析这些方法对于 $5 0 0 \mathrm { m }$ 口径球面射电望远镜早期脉冲星搜索的必要性和可行性，并尝试使用简单的程序完成并行加速脉冲星搜索的处理流程，还尝试了对搜索过程进行图形处理器加速。

# 1脉冲星搜索方法

最早的脉冲星可以说是Bell女士用肉眼发现的[8]，而数十年后的今天，脉冲星的发现已经离不开电子计算机。从最初在时域信号中搜索，到通过消色散和傅里叶变换获得频域信息，再到今天，脉冲星搜索方法已经发展得相对完善。

如果尝试在脉冲星搜索中应用新技术，那么无论是使用原理稍有改进的程序，还是使用和前人工作完全不同的周期信号搜索技术，通常的做法是基于历史观测数据集，结合新技术，尽可能多地找到数据集中的已知脉冲星，并尝试搜索数据集中可能存在的、在之前的数据处理中未被发现的脉冲星。

在新技术的尝试过程中，倾向于使用帕克斯望远镜多波束脉冲星巡天（Parkes Multibeam PulsarSurvey，PMPS)数据作为基础。从2000 年的第1篇论文[9]（按发表时间)到现在，共有25篇论文记述了基于帕克斯望远镜多波束脉冲星巡天数据发现的脉冲星，共计833 颗②。

根据文[10]的描述，帕克斯望远镜多波束脉冲星巡天是指用帕克斯望远镜配合13波束接收机，对银经 $2 6 0 ^ { \circ }$ 到 ${ 5 0 } ^ { \circ }$ 、银纬 $- 5 ^ { \circ }$ 到 $+ 5 ^ { \circ }$ 范围内的天区进行的巡天。此巡天的第1篇综述文章(文［11])发表于 2001年，由于在观测的同时已经开始处理观测数据，一些非常重要的结果已在此之前发表，包括发现J119-6127和 J1814-1744具有很强的磁场[9]；发现 J1141-6545 处于一个轨道周期只有 5小时的双星系统[11]；发现 J1811-1736所处的双星轨道的偏心率高达0.828 02（3）[12]；以及发现J1740-3052的伴星质量可以达到11倍太阳质量[13]。文[14］指出，帕克斯望远镜多波束脉冲星巡天数据中已经发现了很多新脉冲星，但仍有不足，例如，发现了非常少量的轨道周期短于一天的毫秒脉冲双星。文[15]以一些同样使用帕克斯望远镜多波束脉冲星巡天数据发现的新脉冲星回答了这个问题。在文中报告了新发现的11颗脉冲双星、15颗毫秒脉冲星和1颗自转周期长达7.7 s的脉冲星;而用于搜索的方法包括日后被广泛用于双星搜索的加速搜索方法（Acceleration Search）。到 2015 年，帕克斯望远镜多波束脉冲星巡天数据系列论文已经发表了7篇（最近的一篇是文[16]）。

从发现旋转射电暂现源[17]（Rotating Radio Transients，RRTAs）开始，大家在帕克斯望远镜多波束脉冲星巡天数据中尝试各种新的方法，成功发现了新脉冲星的方法都已发表。这些论文总结在表1中。在这10篇论文中，3篇是关于旋转射电暂现源的搜索，3篇是关于搜索结果(疑似信号)的新筛选排序方法，1篇采用了新的消除干扰和噪声的方法，2篇是关于全新的搜索方法，1篇采用了原理稍有改进的另一种软件，共找到了107颗新脉冲星。

表12006年以来使用各种方法在帕克斯望远镜多波束脉冲星巡天数据中找到新脉冲星的总结  
Table1 A summary of pulsars discovered in PMPS data since 2006   

<html><body><table><tr><td>Paper</td><td>Instruction</td><td>New Pulsar Numbers</td></tr><tr><td>McLaughlin et al. 2006[17]</td><td>Finding a new type of object，RRATs</td><td>11</td></tr><tr><td>Keith et al. 2009[18]</td><td>Using new method for candidates ranking</td><td>28</td></tr><tr><td>Eatough et al. 2009[19]</td><td>Using new method for RFIs （Radio Frequency Interferences , RFIs）removing</td><td>4</td></tr><tr><td>Keith et al. 2009[20]</td><td>Using new method for candidates ranking</td><td>1</td></tr><tr><td>Eautough et al. 2010[21]</td><td>Using neural network for candidates ranking</td><td>1</td></tr><tr><td>Keane et al. 2010[22]</td><td>RRATs search</td><td>10</td></tr><tr><td>Keane et al. 2011[23]</td><td>RRATs search</td><td>7</td></tr><tr><td>Mickaliger et al. 2012[24]</td><td>Using SigProc for new pulsar search</td><td>5</td></tr><tr><td>Knispel et al. 2013[25]</td><td>The project of Einstein@ Home，systematical reprocessed the data，volunteers joined for candidates identification</td><td>24</td></tr><tr><td>Eatough et al.2013[26]</td><td>Coherent acceleration search</td><td>16</td></tr></table></body></html>

# 2不同的脉冲星搜索方法对FAST早期脉冲星搜索的必要性和可行性

脉冲星的搜索过程大致可以分为检查并剔除数据中的射频干扰（Radio Frequency Interference，RFI）、数据处理和搜索(包括如消色散、傅里叶变换、搜索周期信号等过程)以及疑似信号筛选3个步骤。

将来 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜首先在低频进行脉冲星搜索，观测频率大约为 $2 8 0 ~ \mathrm { M H z }$ 到1620$\mathrm { \Delta M H z }$ 。在这个频率范围内，包含了电视信号、公共通信频率( $4 3 3 ~ \mathrm { M H z }$ 、手机通信频率( $\mathrm { \Phi 9 0 0 ~ M H z } \mathrm { \cdot }$ 以及全球定位系统信号( $1 2 2 7 \mathrm { M H z }$ 、 $1 5 7 5 \mathrm { M H z }$ )等干扰信号[27]。这些较强的干扰信号在消色散的过程中叠加到观测数据中，对后续的数据分析造成很大影响，甚至对于疑似信号的判断有本质的影响。图1是使用 PRESTO③（PulsaR Exploration and Search TOolkit，PRESTO）中 prepfold 命令处理一个包含了已知脉冲星信号的帕克斯望远镜多波束脉冲星巡天数据文件的结果。一些通道由于受射频干扰的影响已经被程序去除(图1中间一列从上到下第1幅灰度图中的白色区域)，但仍有干扰(图1中左下灰度图中的斜条纹)存在于消色散后的时域信号中。这颗脉冲星信号较强，所以数据处理结果没有受到干扰信号的显著影响。帕克斯望远镜处于非常宁静的射电环境中，仍然面临射频干扰的问题，对于 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜，虽然在规划和建设中试图避免大量可能的干扰信号，但射频干扰的识别和剔除在数据处理中仍然是必须的。

Search Information 2 Pulses of Best Profile Candidate:ACCEL_Cand_1 （204号 $\mathrm { R A } _ { \mathrm { J } 2 0 0 0 } = 1 8 { : } 3 4 { : } 0 3 . 0 6 3 1$ $\mathrm { D E C _ { J 2 0 0 0 } } { = } { - } 0 7 { : } 3 0 { : } 1 3 . 9 3 0 0$ （204号 Telescope:Parkes Folding Parameters Epoch $\dot { \mathbf { \rho } } _ { \mathrm { t o n o } } = 5 1$ 373.496 382 870 37 （204号 $\mathrm { D O F _ { e f f } } = 6 0 . 4 \breve { 2 } \quad \chi _ { \mathrm { \scriptsize ~ r e d } } ^ { 2 } = 4 8 , 6 2 1$ （2 P(Noise)-0 (52.50) Epochbary $\AA = 5$ 1373.502 632 229 65 Dispersion Measure (DM; pc/cm³)=287.116 Tsample=0.000 25 （204号 $\mathrm { P _ { t o p o } ( m s ) } = 5 1 2 . 9 8 7 6 ( 1 4 ) _ { \circ }$ $\mathrm { P _ { b a r v } ( m s ) } = 5 1 2 . 9 7 7 0 ( 1 4 ) _ { \circ }$ Data Folded $= 7 3 4 0 0 3 2$ （202 Ptopo(s/s)=0.1(5.9）X109 $\mathrm { P ^ { ' } b a r v } ( \mathrm { s } / \mathrm { s } ) = 0 . 0 ( 5 . 9 ) \times 1 0 ^ { - 9 } .$ Data $\mathbf { A v g } = 4 9 . 2 6$ （20 （204号 $\mathrm { P } _ { \mathrm { t o p o } } ^ { \prime \prime ^ { \sim } \mathrm { r } ^ { \sim } } ( \mathrm { s } / \mathrm { s } ^ { 2 } ) = 0 . \dot { 0 } ( 2 . 1 ) \times 1 0 ^ { - 1 1 }$ Pbary(s/s2)=0.0(2.1)×10-l1 Data StdDev $= 4 . 7 0 7$ Binary Parameters 重 Profile Bins $= 6 4$ （204号 Porb(s)=N/A e=N/A W Profile $\mathbf { A v g } = 5 . 6 5 \mathrm { e } + 0 6$ asin(i)/c(s)=N/A ω (rad)=N/A Profile StdDev $= 1 5 9 4$ Tperi=N/A 1500 40 zx peonper 80- 20 zh/eeenbH 0 1 500 0.8 10-6 0 -10-6 60- P-dot-5.435 7e-11 (s/s) 1400 Erlreerrr gr iiirrn pueq-qns 40 xpp 0.6 0 20 -1300 0.5 0 -0.5 Period-512.987 622 77(ms) 0.4 Freq-1.949 365(Hz) 0- -2×10-³-10³010³ 2×10-3 0 0.4 0.81.2 1.6 2 ( 500 2×10-6 0.2 zx peonper 40 -2X10-6 20 0 -4X10-6 0 0.5 1 1.5 40200 0 0.5 0 -0.5 Phase Reduced x² 0 500100015002000 Period-512.987 622 77(ms) PM0086_02042.sf DM (pc/cm³) pzc 11-Jun-2015 23:40

Fig.1AnexampleofRFIinobservationdatafromPRESTOoutput.TheRFI（diagonal stripe in thegreyscaleimageatthe lowerleftcorner）canbeseen clearlyinthetime domaindata，butsince the pulsar signalis strongerthan this RFIand the most influential RFI is removed,this RFI does not exert major efect on the data reduction result

搜索脉冲星的周期信号的方法主要有3种：相位调制搜索（Phase Modulation Search[28-29]）、加速搜索（Acceleration Search[15.30]）和快速折叠算法（Fast Folding Algorithm[31]）。结合 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期脉冲星搜索的特点，逐个分析这些搜索方法的必要性和可行性。

$5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期观测采用漂移扫描(Drift Scan)的模式，将望远镜指向观测目标即将经过的位置，等待源从波束中经过，并在源经过波束的时间段记录观测数据。因此，单次的观测时间与波束大小有关，而波束大小与观测频率有关。对于L波段，以 $1 . 4 \ : \mathrm { G H z }$ 为例，波束宽度约为 $3 ^ { \prime }$ ，因而源从波束中经过的时间，也就是单次的观测时间，大约为 $1 2 \mathrm { ~ s ~ }$ ；而如果将观测频率降低到 $3 0 0 \mathrm { M H z }$ ，则波束宽度增加到 $1 4 ^ { \prime }$ ，观测时间增加到 $5 6 ~ \mathrm { s }$ 。在早期观测数据的处理中，主要使用PRESTO软件。

相位调制搜索主要针对轨道周期非常短的脉冲双星，在观测时间接近或长于双星轨道周期的情况下，这种方法可以获得较好的效果。与目前已知脉冲星中的脉冲双星的轨道周期相比， $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期观测的单次观测时间非常短，远远短于轨道周期。在望远镜早期脉冲星搜索数据处理中没有必要使用相位调制搜索方法。

加速搜索采用一个定常加速度近似脉冲双星轨道运动的加速度，从而消除观测数据中由于双星的轨道运动导致的脉冲到达时间的变化。加速搜索适用于双星轨道周期长于观测时间，尤其是双星轨道周期远长于观测时间的情况。可以定性估计加速搜索对于圆轨道的脉冲双星是否有效：

$$
A \_ { \mathrm { m a x } } \_ P = 4 \pi ^ { 2 } x c / { P _ { \mathrm { ~ b ~ } } } ^ { 2 }
$$

其中， $x$ 是天球投影上的轨道半长轴，以光秒为单位； $\mathbf { \Psi } _ { c }$ 是光速； $P _ { \mathrm { ~ b ~ } }$ 是轨道周期，以秒为单位。

$$
{ \cal A _ { - } s u r v e y { \cal - P } } = z m a x c { \cal P } / ( T ^ { 2 } h ) ,
$$

其中，zmax 是PRESTO 中的加速搜索设置的参数，用来控制加速搜索中尝试的加速度的上限； $P$ 是脉冲星的自转周期； $T$ 是观测时间； $h$ 是搜索中叠加的谐波数。如果

$$
A \_ { \bf m a x \_ P } \sim A \_ { \bf s u r v e y \_ P } \
$$

那就说明设置的加速度(zmax值)偏小，轨道运动对于搜索的影响显著。这里选取球状星团杜鹃座47中的已知脉冲双星④，取望远镜观测时间为 $1 ~ \mathrm { m i n }$ ，zmax 数值取10，计算结果见表2。

表2使用球状星团杜鹃座47中的脉冲双星参数估算 $\mathbf { 5 0 0 } \mathbf { m }$ □径球面射电望远镜脉冲星漂移扫描巡天的数据处理中加速搜索的有效性。望远镜无法观测球状星团杜鹃座47，仅使用脉冲星的参数估计搜索的有效性

Table2An Estimationof FASTpulsarsearch eficiencyof the knownpulsars in the globularcluster 47 Tucanae.Because FAST can't observe this globular cluster，we only use the orbit parameters of these pulsars for estimation   

<html><body><table><tr><td rowspan="2">Pulsar</td><td rowspan="2">Spin Period /ms</td><td rowspan="2">Orbit Period day</td><td rowspan="2">x</td><td rowspan="2">A_survey_P 1 minute obs.zmax 10</td><td rowspan="2">A_max_P</td></tr><tr><td>(light second)</td></tr><tr><td>J0024-7205E</td><td>3.536 33</td><td>2. 256 84</td><td>1. 981 842 38</td><td>184.18</td><td>0.62</td></tr><tr><td>J0024-7204H</td><td>3.210 34</td><td>2. 357 7</td><td>2. 152 813 3</td><td>167. 21</td><td>0.61</td></tr><tr><td>J0024-7204I</td><td>3.484 99</td><td>0. 229 79</td><td>0. 038 447 2</td><td>181. 51</td><td>1. 16</td></tr><tr><td>J0023-7203J</td><td>2. 100 63</td><td>0.120 66</td><td>0.040 402 22</td><td>109.41</td><td>4.40</td></tr><tr><td>J0024-72040</td><td>2.643 34</td><td>0. 135 97</td><td>0. 045 151 2</td><td>137. 67</td><td>3.87</td></tr><tr><td>J0024-7204P</td><td>3. 643 02</td><td>0. 147 2</td><td>0.038</td><td>189.74</td><td>2.78</td></tr><tr><td>J0024-7204Q</td><td>4. 033 18</td><td>1. 189 08</td><td>1.462 209 4</td><td>210.06</td><td>1. 64</td></tr><tr><td>J0024-7204R</td><td>3.480 46</td><td>0. 066 2</td><td>0. 033 4</td><td>181.27</td><td>12.09</td></tr><tr><td>J0024-7204S</td><td>2. 830 41</td><td>1. 201 72</td><td>0. 766 270 3</td><td>147. 42</td><td>0.84</td></tr><tr><td>J0024-7204T</td><td>7. 588 48</td><td>1. 126 18</td><td>1. 338 502</td><td>395.23</td><td>1. 67</td></tr><tr><td>J0024-7203U</td><td>4.342 83</td><td>0. 429 11</td><td>0. 526 950 1</td><td>226.19</td><td>4.54</td></tr><tr><td>J0024-7204V</td><td>4.81</td><td>0. 227 16</td><td>0.851 3</td><td>250.52</td><td>26.17</td></tr><tr><td>J0024-7204W</td><td>2. 352 34</td><td>0.133</td><td>0. 243 5</td><td>122. 52</td><td>21.84</td></tr></table></body></html>

在 $1 ~ \mathrm { m i n }$ 的观测数据中，这些脉冲星的轨道运动导致的脉冲到达时间对于搜索的影响很小。一方面，这些脉冲星都是毫秒脉冲星，自转非常快，对于一般的脉冲星，比如自转周期为0.1s，A_survey_ $P$ 的数值会进一步增大，这意味着可以使用更小的zmax值，比如仅取1或者不进行加速搜索( $z m a x = 0$ ，则相当于不进行双星搜索，但是仍然有可能找到脉冲双星的信号）。

对于PRESTO的加速搜索程序来说，10甚至更低的zmax 数值，消耗的计算时间和内存都非常少。因此，对于 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期脉冲星搜索来说，可以不采用加速搜索，如果需要搜索轨道周期特别短的脉冲双星，可以尝试加速度较小的加速搜索。

快速折叠算法主要用于搜索自转周期特别长的脉冲星。尝试用 PRESTO 中的 prepfold 处理包含了自转周期长达7.7s的脉冲星 $\mathrm { J 1 0 0 1 } - 5 9 3 9 ^ { [ 3 2 ] }$ 的帕克斯望远镜多波束脉冲星巡天数据文件，其信号的信噪比可以达到69.3（PM0081_02471.sf)，但使用PRESTO搜索只能得到这个信号的二次谐波，信噪比为51.8。显然，如果在搜索中得到的并非是脉冲星信号的基频信号，而是谐波信号，那么搜索出的谐波信号的信噪比较基频信号有所降低。在这种情况下，较强的长周期脉冲星仍然可能被搜索到，但是也会导致一些弱信号被遗漏。因此，如果要搜索长自转周期的弱脉冲星，有必要尝试快速折叠算法处理观测数据。

PRESTO 中不包含可以进行快速折叠算法的程序，要使用这一算法，需要使用 Sigproc③中的 ffa程序。

另外，文［33]采用分段搜索（Segmented Search）的方法累加了对于球状星团杜鹃座47的大约1100小时的观测数据并成功找到了新的脉冲星。对于 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期观测中单次观测每个源的时间有限这一情况，采用分段搜索的方法，叠加不同时间段的观测数据，提高探测灵敏度是可行的。这一方法可以用于今后 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜脉冲星搜索中。需要指出，文［33]搜索的是球状星团中的脉冲星，所以仅使用了一个色散值，而对于一般的搜索，需要尝试数百个色散值，因而计算量也增加数百倍。

在疑似信号的筛选阶段，显然使用计算机程序，无论是简单的筛选，比如按照信噪比排序，还是使用复杂的方法，比如人工智能，都是可行的。但这些程序或许会遗漏非常少量的真实的脉冲星信号。也可以结合人工，比如Einstein $@$ Home[25]。 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜每年可能产生数以亿计的脉冲星疑似信号。结合计算机和人工可能是更好的选择。对于海量的疑似信号，首先使用计算机程序，将其中质量不好的疑似信号剔除，再人工对剩余的疑似信号作判断。

# 3PRESTO脉冲星搜索加速和Heimdall单脉冲搜索加速的尝试

PRESTO 的脉冲星搜索分步进行。按照操作的先后顺序，PRESTO中的不同程序，先后完成分析数据中的射频干扰并标记，逐个消色散并输出文件，将消色散后的文件逐个进行傅里叶变换得到频域信息，逐个搜索不同色散值的频域数据，疑似信号排序以及生成最终供判断信号质量的图表。

考虑到对于不同的色散数值，消色散、傅里叶变换、搜索以及最终生成图表可以同时进行，自主编写程序将这些过程并行化，并行化的加速效果非常显著。在一台配备了双路 X5690（共12核24 线程)和96GB内存的计算节点上的测试结果如图2。对于单个帕克斯望远镜多波束脉冲星巡天数据文件，12个线程同时处理，用时已经下降到大约 $1 0 7 0 \ \mathrm { s }$ ，使用大约100甚至更多线程时，处理时间降到900s以下。如果不采用并行化处理，单个数据文件的处理时间超过 $9 0 ~ \mathrm { m i n }$ 。并行化处理节约了超过 $8 0 \%$ 的时间。在配置更高的计算节点上，处理时间可以缩短到 $6 0 0 \mathrm { ~ s ~ }$ 以内。

未来 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜脉冲星观测数据也将在配备了多核处理器的大型计算集群上完成。在最初阶段，将一些数据处理过程简单并行化，非常有利于提高处理效率。

另外尝试单脉冲搜索的加速。单脉冲是指带有色散的单个较强的脉冲，它可能来自于已知的脉冲星，旋转射电暂现源，也可能是快速射电暴。如果采用PRESTO进行搜索，其步骤和脉冲星搜索一样，只不过在搜索这一步中使用另一个专门用来搜索此类信号的 python 程序。而作为对照，使用heimdall③[34]。Heimdall 是基于 NVIDIA 硬件和CUDA 的图形处理器(Graphics Processing Unit，GPU)加速的程序。经过测试，在一台安装了NVIDIA M2090计算卡的服务器上，对于帕克斯望远镜多波束脉冲星巡天数据，Heimdall只需要 $3 2 \sim 3 4 ~ \mathrm { s }$ 即可完成搜索，且能搜索出其中来自于旋转射电暂现源的单脉冲信号。如果PRESTO 搜索需要 $6 0 0 ~ \mathrm { s }$ ，Heimdall使用图形处理器实现了约20倍的加速。

![](images/fd8360221e1328fa17b82f8d3193b463d5a98bb288b32fed45b9db62c07f855b.jpg)  
图2使用不同线程数目时单个文件的处理时间。横轴是最大并行线程数目，纵轴是总用时。所有测试在同一个计算节点上运行，使用同一个文件。对于这个计算节点来说，当线程数在大约100以下时，增加线程数对于缩短处理时间有显著效果

Fig.2Data reduction time decreases with increasing thread number. The $\mathrm { \Delta X }$ -axis is the maximal number of thread running at the same time；the Y-axis is the total data reduction time (in the unit of second).In this case, when the thread number is below 10O,increasing the threads is eficient to reduce the data reduction time

帕克斯望远镜多波束脉冲星巡天数据的单个数据文件的时间分辨率是 $2 5 0 ~ \mu \mathrm { s }$ ，共96个通道，观测时长约为 $2 ~ 1 0 0 ~ \mathrm { s }$ 。而 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜如果采用 $1 0 0 ~ \mu \mathrm { s }$ 的时间分辨率，1024个通道，观测时长 $1 \mathrm { m i n }$ 。如果也采样1bit，那么望远镜单次观测的数据量大约是帕克斯望远镜多波束脉冲星巡天数据单个文件的三分之一。因此，在单计算节点上用 PRESTO完成脉冲星搜索的时间大约是 $2 0 0 ~ \mathrm { s _ { \circ } }$ 只要配备超过4个节点，就可以实现处理时间短于数据获取时间。如果使用Heimdall搜索单脉冲，则用时大约为 $1 0 \mathrm { ~ s ~ }$ ，已经短于观测时间。也就是说，一个小规模的集群可以实现观测数据的实时处理。

# 4总结和展望

在分析前人使用的一些搜索脉冲星的方法的基础上得出结论，在 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜早期脉冲星搜索中不需要使用相位调制搜索方法，只在搜索自转周期和轨道周期都非常短的脉冲双星时才需要使用加速搜索方法。这两种搜索方法都可以使用PRESTO软件实现。而在计算资源充足时，也可以考虑使用 SigProc 中的ffa 程序，使用快速折叠算法，试图搜索数据中可能存在的自转周期非常长的脉冲星。

尝试了PRESTO数据处理的并行化，将处理时间缩短到原先的大约 $4 0 \%$ 。也尝试用于搜索单脉冲的图形处理器程序，实现了大约20倍的计算加速。这些搜索计算加速的尝试有助于在今后提高望远镜脉冲星观测数据的处理速度。

配合这些分析和加速的尝试，可以大致实现 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜漂移扫描数据的处理速度快于数据获取的速度。这些数据处理包括脉冲星搜索、单脉冲搜索和搜索到的疑似信号的识别。

借助 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜非常高的灵敏度和脉冲星搜索技术，在望远镜早期漂移扫描的数据中找到一定数量的新脉冲星。在数据处理过程中，建议首先快速搜索数据中的单脉冲，结合图形处理器加速，搜索可以在非常短的时间内完成。搜索单脉冲的同时，使用PRESTO不设置加速度值或者只使用非常小的加速度范围搜索其中的周期信号。最后，可以考虑使用 SigProc 重新处理数据，主要使用 ffa 程序，即使用快速折叠算法搜索其中可能存在的弱的长周期脉冲星信号。

致谢：感谢美国国家射电天文台的 Scott Ransom教授在PRESTO使用方面的帮助，德国马克思普朗克射电天文研究所的Paulo Freire教授在计算加速搜索有效性方面的协助以及加州大学伯克利分校的Dan Werhimer教授在使用Heimdall方面的指点。同时感谢黔科合作人才团队的帮助和支持。

# 参考文献：

[1] Hulse RA,Taylor JH. Discovery of a pulsar in a binary system [J].The Astrophysical Journal, 1975，195: L51-L53.   
[2] Lyne A G,Burgay M,Kramer M,et al.A Double-Pulsar System: arare laboratory for relativistic gravity and plasma physics ［J].Science，2004，303(5661）:1153-1157.   
[3] BackerD C，Kulkarni S R，Heiles C，et al.A millisecond pulsar［J].Nautre，1982，300: 615B.   
[4] Ransom S M, Hessels JW T, Stairs I H,et al. Twenty-one milisecond pulsars in Terzan 5 using the Green Bank Telescope ［J].Science，2005，307(5711）:892-896.   
[5] Mori K，Gotthelf E V，Zhang S，et al. NuSTARdiscovery of a 3.76 s transient magnetarnear sagittarius $\boldsymbol { \mathrm { ~ A ~ } } ^ { * }$ [J].The Astrophysical Journal，2013，770：L23-L27.   
[6] Esposito P， Israel G L，Belfiore A，et al.EXTraSdiscovery of an 1.2-s X-ray pulsar in M31 [J]. Monthly Notices of the Royal Astronomical Society，2016,457(1） : L5-L9.   
[7] Nan Rendong，Li Di, Jin Chengjin，et al. The Five-Hundred Aperture Spherical Radio Telescope (fast）Project [J]. International Journal of Modern Physics D,2011，20(6）：989-1024.   
[8] Hewish A，Bell S J，Pilkington JD H,et al. Observation of a rapidly pulsating radio source [J].Nature，1968，217:709-713.   
[9] Camilo F,Kaspi V M,Lyne A G,et al. Discovery of two high magnetic field radio pulsars [J]. The Astrophysical Journal，2000，541:367C.   
[10] Manchester R N,Lyne A G, Camilo F,et al. The Parkesmulti-beam pulsar survey—I. observing and data analysis systems，discovery and timing of 1OO pulsars [J]. Monthly Notices of the Royal Astronomical Society，2001，328(1） :17-35.   
[11]Kaspi V M,Lyne A G,Manchester R N,et al. Discovery of a young radio pulsar in a relativistic binary orbit [J]. The Astrophysical Journal，2000,543：321-327. -1736，a pulsar in a highly eccentric binary system ［J]. Monthly Notices of the Royal Astronomical Society，2000，312(4）:698-702.   
[13] Stairs IH，Manchester R N,Lyne A G，et al. PSR J1740-3052：a pulsar with a massive companion [J]. Monthly Notices of the Royal Astronomical Society，2001,325(3）: 979-988.   
[14] Faulkner A J， Kramer M，Hobbs G，et al. Yet more PM survey discoveries·.?[EB/OL]. (2003-01-17). htp://adsabs.harvard.edu/cgi-bin/bib_query? arXiv:astro-ph/0301349.   
[15] Faulkner A J,Stairs I H，Kramer M,et al. The ParkesMultibeam Pulsar Survey—V. finding binary and millisecond pulsars [J]. Monthly Notices of the Royal Astronomical Society，2004, 355(1) : 147-158.   
[16] Lorimer D R，Esposito P，Manchester R N，et al. The Parkesmultibeam pulsar survey: VII. timing of four milisecond pulsars and the underlying spin-period distribution of the Galactic millisecond pulsar population [J]. Monthly Notices of the Royal Astronomical Society，2015, 450(2) : 2185-2194.   
[17] McLaughlin M A,Lyne A G,Lorimer D R,et al. Transient radio bursts from rotating neutron stars [J]. Nature，2006,439(7078）: 817-820.   
[18] Keith M J,Eatough R P，Lyne A G,et al. Discovery of 28 pulsars using new techniques from sorting pulsar candidates [J]. Monthly Notices of the Royal Astronomical Society，2009，395 (2) : 837-846.   
[19] Eatough R P，Keane E F，Lyne A G.An interference removal technique for radio pulsar searches [J]. Monthly Notices of the Royal Astronomical Society，2009,395(1）: 410-415.   
[20] Keith M J,Kramer M，Lyne A G，et al. PSR J1753-224O:a mildly recycled pulsar in an eccentric binary system [J]. Monthly Notices of the Royal Astronomical Society，2009，393 (2): 623-627.   
[21] Eatough R P，Molkenthin N，Kramer M，et al. Selection of radio pulsar candidates using artificial neural networks [J].Monthly Notices of the Royal Astronomical Society，2O10，407 (4): 2243-2450.   
[22] Keane E F,Ludovici D A，Eatough R P，et al. Further searches for Rotating Radio Transients in the Parkes Multi-beam Pulsar Survey [J]. Monthly Notices of the Royal Astronomical Society，2010，401(2）:1057-1068.   
[23] Keane E F,Kramer M,Lyne A G,et al. Rotating Radio Transients: new discoveries，timing solutions and musings [J]. Monthly Notices of the Royal Astronomical Society,2011,415(4） : 3065-3080.   
[24] Mickaliger M B,Lorimer D R，Boyles J,et al. Discovery of five pulsars in archival data [J]. The Astrophysical Journal， 2012，759:127-131.   
[25] Knispel B，EatoughRP，KimH,et al.Einstein $@$ Home Discovery of 24 pulsars in the Parkes Multi-beam Pulsar Survey [J]. The Astrophysical Journal，2013，774(2）: 93-108.   
[26] Eatough R P，Kramer M，Lyne A G,et al.A coherent acceleration search of the Parkesmulti beam pulsar survey - techniques and thediscovery and timing of 16 pulsars [J]. Monthly Notices of the Royal Astronomical Society，2013，431(1): 292-307.   
[27] 中华人民共和国工业和信息化部.中华人民共和国无线电频率划分规定［EB/OL]. （2013-11-28).htp://www.mit.gov.cn/n1146285/n1146352/n3054355/n3057735/n3057748/ n3057751/c4713815/part/4713817.doc.   
[28] Jouteux S，Ramachandran R, Stappers B W,et al. Searching for pulsars in close circular binary systems ［J].Astronomy & Astrophysics，2002，384：532-544.   
[29] Ransom S M,Cordes JM，Eikenberry S S.A new search technique for short orbital period binary pulsars [J]. The Astrophysical Journal，2003，589(2）:911-920.   
[30] Ransom S M,Greenhill L J,Herrnstein JR，et al.A binary milisecond pulsar in globular cluster NGC 6544 [J]. The Astrophysical Journal，2001，546(1） :L25-L28.   
[31] Staelin D H.Fast folding algorithm for detection of periodic pulse trains [J]. Proceedings of the IEEE，1969，57: 724-725.   
[32] Lorimer D R,Faulkner A J,Lyne A G,et al. The Parkesmultibeampulsar survey—VI. discovery and timing of 142 pulsars and a Galactic population analysis [J].Monthly Notices of the Royal Astronomical Society，2006，372(2）:777-800.   
[33] Pan Z，Hobbs G，Li D，et al. Discovery of two new pulsars in 47 Tucanae （NGC 104）[J]. Monthly Notices of the Royal Astronomical Society，2016，459(1):L26-L30.   
[34] Benjamin R B，Matthew B，David G B，et al．Accelerating incoherent dedispersion［J]. Monthly Notices of the Royal Astronomical Society，2012，422:379-392.

# Pulsar Searching Techniques and Their Applications to FAST Pulsar Search

Pan Zhichen，QianLei，Yue Youling（NationalAstronomical Observatories，Chinese Academyof Sciences，Beijing10ol2,China,Email：panzc@bao.ac.cn）

Abstract：We aim to see the feasibilities and necessities of applying current pulsar search methods to FAST pulsar search. We test pulsar search data processing with both software and hardware acceleration. We discuss methods used in current pulsar search，discoveries obtained by these methods and their characteristics. Based on PRESTO,we write scripts to run the pulsar search processing in a parallel manner. We evaluate the feasibilities and necessities of GPU acceleration in single pulse search. With the scripts，the time of processing a ParkesMulti-beam Pulsar Survey data file（with a typical size of $1 0 0 \mathrm { M B }$ ）has been shorten from approximately 95 minutes to less than 1O minutes.Our benchmark shows that the single pulse search in one file has been accelerated by 2O times.The single pulse search can be done in shorter time compared withthe data aquisition process.Used to search for binary pulsars with short orbit periods，phase modulation search is not necessary for FAST pulsar search；similarly，used to search for binary pulsars with relative long orbit periods，the acceleration search is not important for FAST binarypulsar search and the fast foldingalgorithm is only necessary when searching for faint pulsars with long spin periods.For data processing，both software and hardware acceleration can and should be used to reduce time cost.

Key words: Pulsar;Radio Telescope;FAST