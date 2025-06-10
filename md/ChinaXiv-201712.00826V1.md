技术方法

# 腓肠肌羽状角的超声自动测量

潘庆亚1²,陈朝宏,王 青1²,黄庆华³,陈武凡1²,冯前进1,2  
南方医科大学生物医学工程学院'医学信息研究所，2广东省医学图像处理重点实验室,广东广州 510515,3华  
南理工大学电子与信息学院，广东广州 510640

摘要：目的 本文提出腓肠肌羽状角的一种基于超声射频信号的互相关自动测量方法。方法 本文采集正常人体腓肠肌与仿真腓肠肌体模的超声射频信号,重建超声图像，确定肌束的搜索起始点，采用互相关算法自动跟踪肌束膜和肌腱膜,绘出肌束线和肌腱膜线,计算两线之夹角，即为腓肠肌羽状角，并检验自动与手动两种测量方法的可重复性及一致性。结果 利用互相关自动测量方法可准确测量出体膜中仿真肌束羽状角，其测量值的均值与理论值之间的差异小于 $1 ^ { \circ }$ 。利用互相关自动测量方法与手动测量方法获得的正常人体腓肠肌羽状角分别为 $2 0 . 4 8 ^ { \circ } { \pm } 0 . 4 7 ^ { \circ }$ 与 $2 1 . 4 9 ^ { \circ } { \pm } 1 . 7 9 ^ { \circ }$ ,两种方法的变异系数CV值均小于 $3 \%$ ，,均方根误差均小于 $1 ^ { \circ }$ 。Bland-Altman差值法分析结果表明两种方法的一致性良好。结论 本文所提出的腓肠肌羽状角自动测量方法是基于超声射频信号的互相关算法，其测量结果与手动测量结果基本一致，在较严重的噪声情况下仍可跟踪腓肠肌的肌束走向，自动测量腓肠肌的羽状角。

关键词：腓肠肌；羽状角；超声射频信号；互相关算法

# Automatic extraction of the pennation angle of the gastrocnemius muscles from ultrasound radiofrequency signals

PAN Qingya¹2,CHEN Zhaohong²,WANG Qing¹2,HUANG Qinghua’,CHEN Wufan'2,FENG Qianjinl2 Istituteoficaltiorcialyboodlerosgoocl SouthernMdicalesitygu5a;loflectoncfotionineeingoutiniy Technology, Guangzhou 510640, China

Abstract: Objective We propose a cross-correlation method for automatic extraction of the pennation angle (PA)of the gastrocnemius (GM) muscle from ultrasound radiofrequency (RF) signals. Methods The ultrasound RF signals of the GM musclesin tensionconditionfromnormalsubjectsandthesimulatedultrasoundsignals werecollcted.Afterthestartingpoint of tracking，a fascicle wasselected in the reconstructed GMultrasound image from theRF signals,and thefascicle and deep aponeurosiscould be automatically tracked using thecross-correlationalgorithm.The lines of the fascicle anddeep aponeurosis were then drawnandthePAwascalculated.Thereproducibilityof the proposed methodanditsconsistency with themanual measurement method were tested.Results The angles of the simulated fascicleswere precisely extracted automaticall.The diference between the experimental measurement and the theoretical values was less than $1 ^ { \circ }$ . The PA measured automatically and manually was $2 0 . 4 8 ^ { \circ } { \pm } 0 . 4 7 ^ { \circ }$ and $2 1 . 4 9 ^ { \circ } { \pm } 1 . 7 9 ^ { \circ }$ respectively. The coefficient of variation (CV) of the two methods was less than $3 \%$ and the root-mean square error (RMSE) was less than $1 ^ { \circ }$ . Bland-Altman plot showed a good agreement betwee the proposed automatic method and the manual method. Conclusion The proposed cros-corelation automatic measurement method can detect the orientation of thefascicle and deep aponeurosis and measure the PAbased on ultrasound RF signals with serious speckle noise.

Key words: gastrocnemius muscle; pennation angle; ultrasound radiofrequency signals; cross-correlation algorithm

运动康复训练有助于恢复运动功能障碍患者的中枢神经系统功能，并可防止肌肉萎缩1，以减轻运动功能障碍给患者及其家庭、社会带来的沉重负担。运动康复训练时，不仅要对患者施加精确的运动控制、记录治疗数据，更需要及时了解肌肉功能的改善情况，以改进训练方法和强度。肌肉结构特征参数，如肌肉厚度、肌纤维长度、羽状角等,常用于评估肌肉功能的变化[2-4]

超声影像(US)技术具有无创、实时和便捷的优点，已经被越来越多地用于肌肉的研究。然而，临床医生往往是通过图像处理软件依靠手工标注的方法来确定这些肌肉结构参数5，这限制了超声影像技术在骨骼肌肉临床研究中的应用。近几年，研究学者尝试通过各种算法对肌肉超声图像进行处理分析，以期自动获得这些参数[-11]。Zhou与Zheng[提出迭代霍夫变换(Revoting

HoughTransform)计算超声图像中肌纤维的羽状角，取得了良好的效果，并进一步应用该算法在肌肉运动过程中动态获取羽状角[8]。Zhao 和Zhang[1]采用雷登变换(RadonTransform)实现肌肉羽状角的自动跟踪和计算。这些方法基于超声灰度图像，斑点噪声对跟踪结果影响较大，需要对超声图像进行一些专门的预处理，例如降采样、插值、希尔伯特变换、幅度-亮度转换、去噪滤波等[1],以获得较好结果。而经预处理的超声灰度图像往往会丢失一部分超声射频原始信号所包含的有用信息，例如相位信息。

超声射频信号是原始信号，是人射超声波经生物组织反射、散射后形成的回波，富含组织内部信息。与基于灰度图的跟踪方法相比，基于射频信号的跟踪方法可利用更多的有用信息，且受斑点噪声影响较小。Luo和Konofagou2提出一种基于超声射频信号的快速归一化互相关方法进行心肌组织的位移估计，取得了较好的结果。

肌肉痉挛等腿部疾病都与腓肠肌有着直接或者间接的关系。当肌肉拉伸或收缩时,羽状角会随之变化[13]。羽状角的变化可反映肌肉的功能与状态，为临床上腓肠肌病变诊断以及运动康复训练提供重要的参考信息。本文提出腓肠肌羽状角的一种基于超声射频信号的自动测量方法，通过选定肌束的超声射频信号，利用互相关算法，分析射频信号的幅值和相位信息，自动跟踪肌束方向和肌腱膜方向，计算肌肉的羽状角。本方法分别用于人体和仿真体膜的超声数据，所检测的羽状角数值分别与手工测量结果和理论数值相比较，检验该算法的有效性。

# 1 材料和方法

# 1.1人体超声数据的获取

采用开放式综合超声系统(SonixRP,Ultrasonix,Canada），该系统配有主机箱（包函PIV $3 . 0 \mathrm { G H z }$ 的双CPU、80GB的系统硬盘、及1GB的存储器）显示器、一张内置10位模/数转换卡(采样频率 $4 0 \mathrm { M H z }$ ，以及一个中心频率 $1 0 ~ \mathrm { M H z }$ 的线阵超声探头（-6dB带宽 $5 \sim$ $1 4 ~ \mathrm { M H z }$ ）。该系统采用开放式PC平台-Microsoft?VisualStudio?环境，可以同时保存超声图像、超声视频和超声射频信号。

受试者为正常男性，22\~26岁，坐姿，膝关节成近$9 0 ^ { \circ }$ ,脚着地，以脚跟为定点，踝关节背屈 $4 0 ^ { \circ }$ ,保持不动。腓肠肌内侧头为研究对象，将超声探头沿腓肠肌纵向放置。当显示器清晰地显示出腓肠肌的羽状肌束结构时，采集超声射频信号(图1A)，并重建超声图像(图1B)。然后，利用本文所提出的互相关自动测量的方法进行羽状角检测（详见1.3节)，检测结果将与3位有经验临床超声医师的手动测量结果进行比较。

![](images/7fb5d306983613364b2c7a4e3da5fd8feffe4da98bd51491d7c8d0493b152594.jpg)

Fig.1Ultrasound radiofrequency (RF) signals (A), B-modeimageof gastrocnemiusmuscle reconstructed using RF signals (B),and a simulated ultrasound image of the gastrocnemius muscle (C).

图1腓肠肌的超声射频信号、由射频信号重建的B型超声图及仿真腓肠肌的超声图  
Deep aponeurosis

# 1.2仿真体膜数据的获取

编写仿真程序，调用FieldⅡ程序包，设计1块 $4 0 \mathrm { m m } \times$ $1 0 \ : \mathrm { m m } { \times } 9 0 \ : \mathrm { m m }$ 的腓肠肌体模，其中100000个散射因子随机分布在体模内部。线阵超声探头为128晶振，中心频率为 $3 \mathrm { M H z }$ ，系统采样频率为 $1 0 0 \mathrm { M H z }$ ，然后利用FieldII计算出128根反射射频信号线，图像动态显示范围压缩到 $4 0 ~ \mathrm { d B }$ 。腓肠肌的仿真超声结果如图1C所示，体模具有5条不同角度的仿真肌束和一条仿真肌腱膜。利用本文所提出的互相关自动测量的方法进行羽状角检测(详见1.3节），测量值与仿真设计时的理论值进行比较，分析本文所提出的方法的有效性。

# 1.3基于超声射频信号的互相关自动测量算法

如图1B所示，羽状肌的肌肉层中含有浅层肌腱膜、多根肌束、和深层肌腱膜，根据肌束的排列方向和深层肌腱膜的方向可以画出肌束线和深层肌腱膜线，两线的夹角即为肌束与深层肌腱膜之间的夹角，称为羽状角[14]本文仅以跟踪一条肌束为例介绍本文所提出的羽状角测量方法。

利用Matlab7.11自编"肌肉形态分析软件”，功能主要包括射频信号读入、超声图像重建、参数选择、测量结果显示与保存等。首先，读入所采集的腓肠肌的超声射频信号(.rf文件)，然后，将超声信号沿纵向方向进行降采样，沿横向方向进行插值，保证重建的超声图像与超声设备所显示的B-型超图像大小一致( $3 4 0 \times 3 2 1$ ，如图1B所示。选择羽状角参数，即可按照下面的互相关算法自动测量羽状角，并将结果显示在结果框中。

互相关自动测量算法

在超声图像中选择一条清晰的、长度适中的肌束作为被测肌束，在其上确定一跟踪起始点，以该点为中心沿该条信号线选取一段信号(含20个采样点)作为感兴趣的肌束信号 $x _ { 1 }$ ，如图2A所示，然后沿两侧相邻的超声射频信号线搜索与 $x _ { 1 }$ 相关性最大的肌束信号，搜索范围设定为以该中心点两侧各20个点的范围，如图2B所示。公式(1)为互相关算法公式

$$
R _ { x _ { 1 } , x _ { 2 } } ( \tau ) = E ( x _ { 1 } ( t ) ^ { * } x _ { 2 } ( t + \tau ) )
$$

其中，E表示期望值， $x _ { 1 }$ 是当前射频信号线上感兴趣的肌束信号， $x _ { 2 }$ 是相邻射频信号线的肌束信号，\*表示卷积。搜索范围为(-20,20)，t表示 $x _ { 2 }$ 相对于 $x _ { 1 }$ 的位移偏移量， $\tau \in ( - 2 0 , 2 0 )$ 。当R值最大时，表明 $x _ { 2 }$ 与 $x _ { 1 }$ 匹配， $x _ { 2 }$ 就是所要找的肌束信号，并记录其位置[公式(2)]。

$$
A _ { 2 } = A _ { 1 } + \tau
$$

![](images/c40302c6e08db6554d25a25c40050d60fd8051817a7033161ebbe2ae50ecfe5a.jpg)  
图2当前超声射频信号与相邻超声射频信号 Fig.2 Ultrasound RF signals of the current line and the neighbor line.A:Current ultrasound RF signals. $x _ { 1 }$ presents the signal of muscle fascicle (marked by red box);B:Adjacent ultrasound RF signals.Two dashed lines indicate the searching range (-20,20). $x _ { 2 }$ presents the signal with the maximum cross-correlation value.

其中， $A _ { 2 }$ 是相邻信号线上肌束 $x _ { 2 }$ 的中心位， $A _ { 1 }$ 是$x _ { 1 }$ 的中心点的坐标， $\tau$ 是 $x _ { 2 }$ 相对于 $x _ { 1 }$ 的位移偏移量。

然后，以这两条相邻超声射频信号为当前信号线，分别向左右方向重复上述互相关搜索过程，跟踪肌束方向。评判跟踪是否结束有两个标准：

(1)跟踪到边界，即搜索到第一条信号线或者最后一条信号线；

(2)跟踪到肌束的终点(若该点的R值远远小于前一个点的R值,则该点为肌束终点。本文设定肌束终点的R值小于前一个点的R值的1/10)。

当跟踪完成时，将各个信号线上的肌束信号位置进行线性拟合，得到跟踪目标一一腓肠肌肌束线。

最后，进行深层肌腱膜线的跟踪，算法同上。公式(3)和公式(4)分别为肌束线和深层肌腱膜线的线性表达公式，由斜率值 $k _ { 1 }$ 和 $k _ { 2 }$ 便可计算肌束线和深层肌腱膜线的夹角 $\alpha$ ，即羽状角[公式(5)]。

$$
\begin{array} { l } { y _ { 1 } = k _ { 1 } \cdot x + b _ { 1 } } \\ { y _ { 2 } = k _ { 2 } \cdot x + b _ { 2 } } \\ { \alpha = \arctan \left| \frac { k _ { 2 } - k _ { 1 } } { 1 + k _ { 1 } \cdot k _ { 2 } } \right| } \end{array}
$$

1.4自动手动两种测量方法的可重复性及一致性检验

本文通过计算变异系数(CV)和均方根误差(RMSE)2个统计学参数来评价本文所提出的互相关自动测量方法的可重复性。

变异系数是衡量各测量值变异程度的一个统计量，定义如公式(6)：

$$
C V { = } \frac { S } { \bar { X } } { \times } 1 0 0 \% 
$$

其中， $\dot { X }$ 及S分别为测量数据的样本平均数和标准差。由定义可以看出，CV是一种相对分散度的衡量指标，可以消除平均数不同对各组数据变异程度比较的影响[15]。

均方根误差的定义如公式(7)：

$$
R M S E = \sqrt { \frac { \sum _ { i = 1 } ^ { n } d _ { i } ^ { 2 } } { n } }
$$

式中， $\mathbf { \Omega } _ { n }$ 为测量次数， $\mathbf { \mathcal { A } } _ { i }$ 为第i个测量值与均值的差值。

通过绘制Bland-Altman差值图，分析手动测量方法和互相关自动测量方法的一致性

# 2结果

# 2.1仿真实验结果

利用本文所提出的互相关自动测量方法检测仿真超声图中的腓肠肌肌束的羽状角，图3A显示该算法可以很好地跟踪肌束及肌腱膜。表1列出仿真超声图中5条肌束线与肌腱膜线之间的夹角(羽状角)和肌腱膜角度的理论值和测量值，以及两者之间的误差值。测量值的均值与理论值之间的差异在 $1 ^ { \circ } .$ 之内。

# 2.2临床实验结果

如图3B-C及表2所示，本文算法自动跟踪人体腓肠肌的肌腱膜线与超声医师手动绘制结果近似，而所跟踪的肌束线的长度往往要短于手动绘制结果。但是，从结果看，这对羽状角的计算影响不大，两种方法所测量的羽状角平均值的差值约为 $1 ^ { \circ }$ ，手动测量的羽状角为$2 1 . 4 9 ^ { \circ } { \pm } 1 . 7 9 ^ { \circ }$ ，自动跟踪的羽状角为 $2 0 . 4 8 ^ { \circ } { \pm } 0 . 4 7 ^ { \circ }$ O

![](images/aa03442b5199828c833c8d0874c0621489e3856a0638a7c9dbbb54385293285f.jpg)  
图3仿真超声图和人体腓肠肌超声图的肌束线和深层肌腱膜线的检测结果  
Fig.3The tracking results of muscle fascicles and deep aponeurosis.A:Five muscle fascicles and one deep aponeurosis are automatically tracked (marked by red line) in the simulated ultrasound image.The five muscle fascicle pennation angles are marked $\alpha _ { 1 } { - } \alpha _ { 5 } { ; }$ B: In reconstructed ultrasound image, the muscle fascicle and deep aponeurosis are automatically detected using the proposed method (marked by red lines).The pennation angle is marked $\alpha ; c { \mathrm { : } }$ In the same ultrasound image as $B ,$ the muscle fascicle and deep aponeurosis are drawn by hand (marked by the blue lines). The pennation angle is marked by $\alpha$ .The white curves in $A$ and $B$ present the traces detected using the proposed method.

表1仿真实验结果Tab.1 Results of the simulation test  

<html><body><table><tr><td rowspan="2"></td><td colspan="5">Pennation angle</td><td rowspan="2">Angle of deep aponeurosis</td></tr><tr><td>α1</td><td>α2</td><td>α3</td><td>04</td><td>05</td></tr><tr><td>Theoretical value (°)</td><td>23.56</td><td>24.79</td><td>25.81</td><td>26.64</td><td>27.26</td><td>0</td></tr><tr><td>Measurement value (°)</td><td>23.30±0.26</td><td>24.05±0.29</td><td>25.86±0.13</td><td>26.05±0.10</td><td>27.44±0.19</td><td>0.10±0.03</td></tr><tr><td>Difference (°)</td><td>-0.26</td><td>-0.74</td><td>0.05</td><td>-0.59</td><td>0.18</td><td>0.10</td></tr></table></body></html>

表2临床实验结果Tab.2Results of theclinical test  

<html><body><table><tr><td></td><td>Pennation angle</td><td>Angle of deep aponeurosis</td></tr><tr><td>Manually measured value (°)</td><td>21.49±1.79</td><td>0.18±0.72</td></tr><tr><td>Automatically measured value ()</td><td>20.48±0.47</td><td>1.12±0.46</td></tr><tr><td>Difference ()</td><td>-1.01</td><td>0.94</td></tr></table></body></html>

2.3自动手动两种测量方法的可重复性及一致性检验结果

自动测量方法与手动测量方法所获得的两组数据的变异系数 $\mathbf { C V } ( 2 . 3 2 \% , 2 . 9 8 \% )$ 和均方根误差RMSE$( 0 . 4 6 ^ { \circ } , 0 . 6 1 ^ { \circ } )$ ,分析两种方法的可重复性。可看出两种方法的CV值都小于 $3 \%$ ,RMSE均小于 $1 ^ { \circ }$ ,表明互相关自动测量方法的可重复性与手动测量方法相似。

图4显示的是Bland-Altman差值法分析结果。手动工测量和自动测量两组数据的差值均值与差值方差分别为 $. 0 . 7 3 ^ { \circ }$ 与 $0 . 9 0 ^ { \circ }$ ，则 $9 5 \%$ 一致性界限为 $\cdot 0 . 7 3 ^ { \circ } \pm$ $1 . 9 6 \times 0 . 9 0 ^ { \circ }$ ,即 $( 1 . 0 4 ^ { \circ } , - 2 . 4 9 ^ { \circ } )$ ,其一致性界限较窄，且只有一个数据点落到 $9 5 \%$ 一致性界限外，表明手动测量与自动测量这两种方法的一致性较良好。

![](images/2d294db9a7331150ded7098e6dd9c366f2457c2f9913eab87b6f3f5163360e13.jpg)  
图4互相关自动测量方法与手动测量方法的Bland-Altman图 Fig.4 The Bland-Altman plot of the pennation angle measured with cross-correlation automatic and manual measurements.

# 3讨论

本文结果表明，互相关自动测量方法可通过跟踪肌束的超声射频信号，在较严重的斑点噪声情况下仍可准确地跟踪腓肠肌肌束和肌腱膜的方向，自动测量腓肠肌的羽状角，与手动测量结果相差较小。羽状角的大小易受多种因素影响，例如受试者的个体差异(年龄、性别、体质量等）、测试姿势、测量位置、肌肉的健康状况、及超声设备的因素。因此，通过限制受试者的年龄体重性别，可减少受试者的个体差异对羽状角测量的影响。而由于测试姿势的不同，腓肠肌的状态不一样，会导致测量的羽状角数值有所不同。本文的受试者取坐姿，膝关节成近 $9 0 ^ { \circ }$ ,踝关节背屈 $4 0 ^ { \circ }$ ,腓肠肌处于拉伸状态，腓肠肌羽状角的测量值为 $2 0 . 4 8 ^ { \circ } { \pm } 0 . 4 7 ^ { \circ }$ 。这一结果与文献[17]的测量结果近似,其实验对象采取踝关节跖屈$4 5 ^ { \circ }$ 姿势,健侧的腓肠肌羽状角为 $2 0 . 3 8 ^ { \circ } \pm 5 . 4 2 ^ { \circ }$ 。最近有文献报道羽状角的动态测量，在跖屈过程中羽状角变化范围在 $1 9 . 3 ^ { \circ } { \pm } 0 . 7 ^ { \circ }$ 至 $3 5 . 4 ^ { \circ } { \pm } 6 . 3 ^ { \circ }$ 之间[18]。另有文献报道腓肠肌内侧头远端的羽状角约为 $1 3 ^ { \circ [ 1 6 ] }$ ，可见腓肠肌的观测位置对羽状角的影响较大。

不同的超声设备也会导致与羽状角测量结果的差异，主要原因是成像算法和图像后处理算法的差异。超声设备系统在超声成像时，会将原始超声射频信号经过降采样或插值处理后，转化为灰度图像，因此不同的成像算法就会影响到羽状角的测量结果。成像处理后，往往还要经过去噪、滤波等处理，以得到的清晰的超声灰度图像。但是，经过这些处理后超声射频信号所含有的生物组织原始信息将部分丢失[13]。本文所提出的互相关自动测量方法直接对超声射频信号进行运算，利用射频信号幅值和相位的信息，受噪声影响小。

然而，这种基于超声射频信号的互相关自动测量方法尚有不足之处，例如有些肌束纤维的连续性不好，在超声图像中呈小段显示，对于射频信号的肌肉纤维，互相关自动测量方法虽然依靠小段肌束仍可确定肌束方向，对羽状角的计算影响不大，但是会对肌束长度的测量产生较大误差，因为羽状肌的肌束长度定义为肌束从浅层肌腱膜到深层肌腱膜之间的长度[17]。因此,若增加肌束长度测量功能时，可基于本文结果，利用先验知识增大搜索范围和改进跟踪终止条件，将断开的肌束纤维连接起来，然后跟踪计算，以期提高肌束参数测量的准确性。

超声定量评价对评估肌肉功能的变化，以及对肌肉运动康复训练都有着重要的意义[2-3.18-19]。然而,肌肉结构化参数的测量目前大多是手工标注测量，面对大量的肌肉超声图像，这样测量工作费时费力，自动测量方法的研究具有现实意义。目前，所报道的腓肠肌羽状角检测方法大多是基于超声灰度图像，通过对超声图像处理分析，自动获得肌肉的结构参数，取得了良好的效果[611.17,202]。而本文直接对超声射频信号跟踪肌束方向，计算羽状角，在噪声环境中也得到了较好的结果。

总之，本文提出一种基于超声射频信号的自动追踪肌束方向并测量羽状角的互相关算法，通过仿真数据和人体数据的检验，该算法的可重复性良好，与手动测量结果基本一致。本方法在较严重的噪声情况下仍可跟踪腓肠肌的肌束走向，自动测量腓肠肌的羽状角。在此研究的基础上可进一步改善以自动测量肌肉厚度和肌束长度等参数形成肌肉形态定量分析软件，用于评估肌肉功能的变化，指导肌肉运动康复的训练。

# 参考文献：

[1]Van Der Kooi EL,Vogels OJ,Van Asseldonk RJ,et al. Strength training and albuterol in facioscapulohumeral muscular dystrophy [J].Neurology,2004,63(4): 702-8.   
[2]Fried GW,Fried KM. Spinal cord injury and use of botulinum toxin inreducing spasticity[J].Phys Med Rehabil Clin N Am,2O03,14 (4):901-10.   
[3]Strasser EM,Draskovits T,Praschak M,et al.Association between ultrasound measurements of muscle thickness,pennation angle, echogenicity and skeletal muscle strength in the elderly[J].Age (Dordr),2013,35(6): 2377-88.   
[4]Chleboun GS,France AR,Crill MT,et al. In vivo measurement of fascicle length and pennation angle of the human biceps femoris muscle[J].Cells Tissues Organs,2001,169(4): 401-9.   
[5]Maganaris CN, Baltzopoulos V, Sargeant AJ. Repeated contractions alter the geometry of human skeletal muscle[J].J Appl Physiol (1985),2002,93(6):2089-94.   
[6]Zhou Y,Zheng YP. Estimation of muscle fiber orientation in ultrasound images using revoting hough transform (RVHT） J]. Ultrasound Med Biol, 2008,34(9): 1474-81.   
[7]Ling S,Chen B,Zhou YJ,et al.An efficient framework for estimation of muscle fiber orientation using ultrasonography[J]. Biomed Eng Online,2013,12(1):98.   
[8] Zhou Y,Li JZ, Zhou G,et al.Dynamic measurement of pennation angle of gastrocnemius muscles during contractions based on ultrasound imaging[J]. Biomed Eng Online,2012,11: 63.   
[9]Zhou Y, Zheng YP.Longitudinal enhancement of the hyperechoic regions in ultrasonography of muscles using a Gabor filter bank approach:a preparation for semi-automatic muscle fiber orientation estimation[J]. Ultrasound Med Biol,2011,37(4): 665-73.   
[10]Rana M,Hamarneh G,Wakeling JM.Automated tracking of muscle fascicle orientation in B-mode ultrasound images[J].J Biomech, 2009,42(13): 2068-73.   
[11] Zhao H, Zhang LQ.Automatic tracking of muscle fascicles in ultrasound images using localized Radon transform[J].IEEE Trans Biomed Eng,2011,58(7): 2094-101.   
[12]Luo J, Konofagou E.A fast normalized cross-correlation calculation method for motion estimation[J].IEEE Trans Ultrason Ferroelectr Freq Control,2010,57(6): 1347-57.   
[13]Lévénez M, Timmermans B and Duchateau J.Effect of myoaponeurotic crocheting of the sural triceps on passive pressure and muscle architecture during stretching [J].Kinesither Rev 2009;9: 56-61.   
[14]Legerlotz K,Smith HK,Hing WA.Variation and reliability of ultrasonographic quantification of the architecture of the medial gastrocnemius muscle in young children[J]. Clin Physiol Funct Imaging,2010,30(3): 198-205.   
[15]吴冬友，杨玉坤.统计学[M].北京:中国税务出版社,2005.   
[16]叶攀,胡海涛.腓肠肌羽状角的高频超声测量及其临床意义[J].中华 医学超声杂志:电子版,2014,11(3):46-9.   
[17] Zhou GQ, Chan P, Zheng YP.Automatic measurement of pennation angle and fascicle length of gastrocnemius muscles using real-time ultrasound imaging[J]. Ultrasonics,2015,57: 72-83.   
[18]刘 鹏,王艳君,毛玉璿,等.减重步行训练改善脑卒中患者小腿肌肉形 态结构的生物力学研究[J].中国康复医学杂志,2012,27(9):792-6.   
[19]杨远滨,张京,冷振鹏,等.抗痉挛治疗前后脑卒中患者超声肌肉结构 参数的比较[J].中国康复理论与实践,2014,20(7):641-4.   
[20]Kawamoto S,Imamoglu N,Gomez-Tames JD,et al.Ultrasound imaging and Semi-Automatic analysis of active muscle features in electrical stimulation by optical flow [C]//2014 36TH abbyak international conference of the ieee engineering in medicine and biology society (EMBC),2014: 250-3.   
[21]Lee D,Li Z, Sohail QZ,et al. A three-dimensional approach to pennation angle estimation for human skeletal muscle[J]. Comput Methods Biomech Biomed Engin,2015,18(13):1474-84. (编辑：经媛)