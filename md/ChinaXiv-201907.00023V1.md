# 一种激光导引星自适应光学系统中激光上行到达角起伏测

# 量方法的研究

黄凯，曹进，肖啸，李语强²（1 乐山师范学院 物理与电子工程学院，四川 乐山 614000；2 中国科学院云南天文台，云南昆明 650011）

摘要：激光导引星波前倾斜测量问题是限制自适应光学技术在天文领域广泛应用的关键问题之一。测量并改正激光上行到达角起伏是解决这一问题的有效方法。提出一种基于统计平均算法而不依赖自然导引星和辅助望远镜的测量方法，可以有效地测量出激光上行到达角起伏。利用具有子孔径阵列的哈特曼波前传感器对激光信标进行探测，选择部分子孔径进行倾斜量的统计平均以获得激光上行到达角起伏。仿真了统计平均算法的误差随子孔径数量的变化关系。结果表明，最小算法误差相对于望远镜全口径倾斜误差的下降比例与大气Fried常数无关，而与望远镜口径有关。望远镜口径越大，算法误差相对于全口径倾斜误差下降越多。当望远镜口径为10m时，最小算法误差下降为望远镜全口径倾斜误差的 $3 3 \%$ 。

关键词：激光导引星；优选算法；波前倾斜；子孔径中图分类号：TH751 文献标识码：A 文章编号：1672-7673（2020）01

自适应光学系统需要足够亮度的导引星作为波前探测的信标。可以利用目标本身作为信标，也可以在目标的等晕区范围内寻找一颗合适亮度的自然导引星作为信标,这样的系统称为自然导引星自适应光学（NGS-AO）系统。1985年,文[1]提出将人造激光导引星（LGS）应用于天文自适应观测。激光导引星发射在目标的等晕区范围内，用于自适应光学系统的波前探测，这样的系统称为激光导引星自适应光学（LGS-AO）系统。理想的人造信标需要具有足够亮度,并且与目标的相对位置稳定。目前激光导引星虽然能够达到满足天文观测的亮度（KeckII望远镜配备的下一代激光系统-NGL能够在天顶角小于 $1 5 ^ { \mathrm { { \circ } } }$ 范围内制造相当于R波段7.5等亮度的Na导星），但是并不稳定，还需要在倾斜等晕区范围内寻找一颗恒星为其校正波前倾斜。如图1，激光上行光路受大气湍流的影响，瞬时的激光信标与激光发射光轴有一定的偏移，这导致自适应光学系统波前传感器探测到的激光导引星波前倾斜量失真。

![](images/de6ee489e28a992fd60bdcb7ec1da8b02cae49ff5e2367b9f80b40e7d9717331.jpg)  
图1激光导引星受激光上行大气湍流影响  
Fig.1 Laser guide star is affected by laser upward atmospheric turbulence

对激光导引星波前倾斜测量方法的研究最早由Foy等人在20世纪90年代展开[3]。1995年，文[4]提出利用辅助望远镜发射激光，主望远镜从侧面探测激光导引星的方法，并于2000年报道了实验结果：在西班牙Calar Alto天文台利用3.6m望远镜发射激光，2.2m望远镜从侧面探测激光束，并借助一颗自然导引星成功探测到了目标的一维波前倾斜[5]。2000年，文[6]提出利用主望远镜发射激光，辅助望远镜探测激光投影的方法，对辅助望远镜中成像的激光带使用统计平均算法得到激光上行的波前倾斜。1997年，文[7」对激光导引星自适应光学系统的波前倾斜测量进行理论上的分析，并对多种辅助望远镜方案进行了对比和分析。2000年开始，中国科学院云南天文台和中国科学院光电技术研究所合作展开激光瑞利导引星项目的实验研究[8]，同时开始关注激光导引星用于大气波前倾斜测量的问题[9-10]，并于2014年利用云南天文台1.2m望远镜为主望远镜，25cm望远镜为辅助望远镜实验验证了统计平均算法对于激光导引星波前倾斜测量的有效性[1-2]。2016年，文[13-14]详细分析了倾斜"互补"假设的应用条件，并提出一种非倾斜“互补"条件下基于多层层析技术的激光导引星波前倾斜探测方法。2016年，文[15]提出一种基于涡旋光束的激光导引星，可以在空中形成一个相比高斯光束更稳定的人造信标以解决激光导引星波前倾斜难以探测的问题，研究结果表明，当旋涡光束拓扑电荷数等于10时，激光上行抖动方差相比高斯光束减小 $3 1 \%$ 。

本文提出一种基于望远镜子孔径探测的波前倾斜测量方法，利用优选算法从子孔径探测数据中分离出激光上行光路的到达角起伏。该方案有别于Reeves等人提出的多层层析方法，且只需要一颗激光导引星即可获得稳定的人造信标。同时，可以有效地避免辅助望远镜方案中由辅助望远镜跟踪、指向等问题引入的探测困难。

# 1激光导引星波前倾斜测量方法的系统布局

基于望远镜子孔径探测的激光导引星波前倾斜测量方法系统结构如图2，激光由发射望远镜发射并在高空形成人造信标，信标光经大气湍流传输进入主望远镜。波前畸变的信标光首先通过波前校正系统（由倾斜反射镜TM和可变形反射镜DM组成），再利用分光反射分别进入成像系统和波前探测系统。假设激光导引星和观测目标之间的大气湍流的影响忽略。如果信标足够稳定，可以通过对信标波前的探测实时校正目标的波前畸变，以实现对目标的高分辨率成像。因为激光上行受大气湍流的影响，所以瞬时的激光信标与激光发射光轴有一定的偏移，这导致望远镜接收的波前畸变中有一个附加的倾斜量。波前信号由3部分组成：激光信标下行整体倾斜、波前高阶畸变信号、激光上行附加倾斜。如果不校正激光上行附加倾斜，目标在相机中的像不稳定，难以实现长时间曝光。本文提出一种算法，可以从波前传感器中分离信标上行抖动信息，由控制器生成信号控制激光发射望远镜的快速倾斜镜以稳定激光信标。系统中波前探测器将输出3路信号分别控制：可变形反射镜DM、接收望远镜端倾斜反射镜TM和发射望远镜端快速倾斜镜。

![](images/da7b3715d78351d0b8ba7f10ed82c1d26a7ce0e16187c3e0e66092e7623d32f4.jpg)  
图2系统结构图  
Fig.2 Schematic diagram of system structure

# 2波前倾斜提取方法

图3为激光导引星子孔径测量方法示意图，接收望远镜分割为排列整齐的子孔径，黄色部分为子孔径接收的信标光的下行光路，图中只画出了部分子孔径的光路作为参考。绿色部分为激光上行光路。可以看出，激光束由发射上行到接收下行共经历了两次大气湍流。每个子孔径范围内的波前倾斜使微透镜的聚焦光斑产生横向漂移，测量光斑中心在两个方向上相对于用平行光标定的基准位置的漂移量，可以求出各子孔径范围内的波前在两个方向上的平均斜率 $\theta$ 。

![](images/c8630396ca55623635516db23cf276967df651aaffa0795b0a6464e635f4cb47.jpg)  
图3激光导引星子孔径测量方法  
Fig.3 Laser guide star tip-tilt measurement method based sub-aperture

任意子孔径i探测到的波前倾斜量 $\theta _ { i }$ 都是由激光上行抖动量 $\theta _ { u p }$ 和下行子孔径倾斜量$\theta _ { d o w n , i }$ 之和构成，即

$$
\theta _ { i } = \theta _ { \scriptscriptstyle u p } + \theta _ { \scriptscriptstyle d o w n , i } \quad .
$$

若随机选取 $N$ 个子孔径(图3中红色标记子孔径)，对这 $N$ 个子孔径探测到的波前倾斜量进行统计平均：

$$
\sum _ { i = 1 } ^ { N } \theta _ { i } \Big / N = \sum _ { i = 1 } ^ { N } \big ( \theta _ { u p } + \theta _ { d o w n , i } \big ) \Big / N \mathrm { ~ . ~ }
$$

对于每一个子孔径，虽然下行光路经历的湍流不同，即 $\theta _ { d o w n , i }$ 不同，但是由于激光上行引起的抖动 $\theta _ { u p }$ 是相同的，所以（2）式可以改写为

$$
\sum _ { i = 1 } ^ { N } \theta _ { _ i } \Big / N = \theta _ { _ { u p } } + \sum _ { i = 1 } ^ { N } \theta _ { _ { d o w n , i } } \Big / N \quad ,
$$

或：

$$
\theta _ { u p } = \sum _ { i = 1 } ^ { N } \theta _ { i } \Big / N - \sum _ { i = 1 } ^ { N } \theta _ { d o w n , i } \Big / N \quad .
$$

其中， $\theta _ { i }$ 由子孔径测量得到; $\theta _ { d o w n , i }$ 未知。假设选取的 $N$ 个子孔径的下行光路波前倾斜 $\theta _ { d o w n , i }$ 是相互独立的随机变量，那么其统计平均值 $\begin{array} { r } { \underset { N  \infty } { \operatorname* { l i m } } \Bigl ( \sum _ { i = 1 } ^ { N } \theta _ { d o w n , i } \Bigl / N \Bigr ) = 0 } \end{array}$ 。即此 $N$ 个子孔径探测到的波前倾斜统计平均值 $\textstyle \sum _ { i = 1 } ^ { N } \theta _ { i } { \Big / } N$ 等于激光上行抖动量 $\theta _ { u p }$ 。考虑到实际情况下，（1)选取的子孔径数量不会趋近无穷大；（2）子孔径之间的波前倾斜 $\theta _ { d o w n , i }$ 具有一定的相关性。

这导致以 $\textstyle \sum _ { i = 1 } ^ { N } \theta _ { i } { \Big / } N$ 确定激光上行抖动量 $\theta _ { u p }$ 引入算法误差[16]：

$$
\sigma ^ { 2 } = \left. \left( \sum _ { i = 1 } ^ { N } \theta _ { d o w n , i } \Big / N \right) ^ { 2 } \right. = \left. \sigma _ { d } ^ { 2 } \right. \left( \frac { 1 } { N } + \frac { 2 } { N ^ { 2 } } \sum _ { i = 1 } ^ { N - 1 } \sum _ { j > i } ^ { N } \frac { \left. \theta _ { d o w n , i } \theta _ { d o w n , j } \right. } { \left. \sigma _ { d } ^ { 2 } \right. } \right) ~ ,
$$

其中， $\left. \sigma _ { d } ^ { 2 } \right. = 0 . 1 8 2 \lambda ^ { 2 } d ^ { - 1 / 3 } r _ { 0 } ^ { - 5 / 3 }$ 为子孔径倾斜方差; $d$ 为子孔径的口径； $r _ { 0 }$ 为大气湍流Fried常数; $\frac { \left. \theta _ { d o w n , i } \theta _ { d o w n , j } \right. } { \left. \sigma _ { d } ^ { 2 } \right. }$ 是任意子孔径 $\mathbf { \nabla } _ { \boldsymbol { { i } } }$ ， $j$ 之间的归一化倾斜相关系数，具体表达式为[12]

$$
\frac { \left. \theta _ { d o w n , i } \theta _ { d o w n , j } \right. } { \left. \sigma _ { d } ^ { 2 } \right. } = \frac { \int _ { 0 } ^ { H } d h \left( \displaystyle \frac { H - h } { H } \right) ^ { 5 / 3 } C _ { n } ^ { 2 } \left( h \right) I \left( \displaystyle \frac { \rho } { d } , 1 \right) } { \int _ { 0 } ^ { H } d h \left( \displaystyle \frac { H - h } { H } \right) ^ { 5 / 3 } C _ { n } ^ { 2 } \left( h \right) I \left( 0 , 1 \right) } ,
$$

$I ( x , y ) = \int _ { 0 } ^ { \infty } d K ^ { ' } \left( K ^ { ' } \right) ^ { - 1 4 / 3 } J _ { n + 1 } \big ( K ^ { ' } \big ) J _ { n + 1 } \big ( K ^ { ' } y \big ) \times [ J _ { 0 } \big ( K ^ { ' } x \big ) + k J _ { 2 m } \big ( K ^ { ' } x \big ) ] ,$ （20其中， $K ^ { ' } = 2 \pi K$ ； $C _ { n } ^ { 2 } \left( h \right)$ 为大气湍流折射率结构常数； $J _ { n } \left( x \right)$ 为 $n$ 阶贝塞尔函数;$k = 2 \pi / \lambda$ 为波数； $H$ 为激光导引星的高度； $\rho$ 为两子孔径中心间距。

在激光导引星高度固定，湍流条件不变的情况下，任意子孔径之间的倾斜相关系数$\frac { \left. \theta _ { d o w n , i } \theta _ { d o w n , j } \right. } { \left. \sigma _ { d } ^ { 2 } \right. }$ 随着子孔径之间距离 $\rho$ 的增加而减少。所以，由（5）式-（7）式可知，算法误差 $\sigma ^ { 2 }$ 与选取的子孔径数量 $N$ 和任意子孔径之间的距离 $\rho$ 有关。

# 3数值计算结果分析

利用（5）式对随机选取的子孔径计算其算法误差的大小。如图4，在望远镜口径范围内选定任意 $N$ 个子孔径，对于任意两个子孔径之间的归一化倾斜相关系数由(6)式计算得出，其中子孔径之间的距离值由子孔径之间的坐标关系给出，大气湍流Fried常数由下式计算：

$$
r _ { \scriptscriptstyle 0 } = \left[ 0 . 4 2 3 k ^ { 2 } \sec \left( \beta \right) \int _ { 0 } ^ { L } { C _ { _ n } } ^ { 2 } \left( z \right) d z \right] ^ { - 3 / 5 } \ .
$$

这里采用Hufnagel湍流结构常数剖面模型：

$$
C _ { n } ^ { 2 } \left( h \right) = 2 . 7 2 \times 1 0 ^ { - 1 6 } \Biggl [ 3 \nu ^ { 2 } \Biggl ( \frac { h } { 1 0 } \Biggr ) ^ { 1 0 } \exp \bigl ( - h \bigr ) \Biggr ] + 1 0 ^ { - 1 6 } \left( h / 1 . 5 \right) ^ { - 2 / 3 } .
$$

以上两式中， $\beta$ 为天顶角； $\nu$ 为风速，是与海拔有关的变量。为了简化计算，天顶角设为 $0 ^ { \circ }$ ，风速设为常数参与计算。（6）式-（9）式将归一化倾斜相关系数与Fried常数 $r _ { 0 }$ 连系起来。

![](images/a390ea41b866136f639b0eeea9e05328631ef4dfc8ad7b2a6783798ecd0176a8.jpg)  
图4子孔径选择示意图，图中大圆表示望远镜口径，实心小圆表示子孔径，

Fig.4 Schematic diagram of subaperture selection.The large circle represents the telescope aperture，while

the small circle represents the selected subaperture

将归一化倾斜相关系数代入（5）式可计算出算法误差。多次随机选择获得仿真结果。仿真结果见图5，图中描述了基于子孔径优选算法的误差随子孔径数量的关系。其中，图中给出的两根参考线分别是子孔径倾斜误差和望远镜全口径倾斜误差，由下式[17-18]计算得到。

$$
\sigma { = } \sqrt { 0 . 1 8 2 \lambda ^ { 2 } D ^ { - 1 / 3 } { r _ { 0 } } ^ { - 5 / 3 } } \ ,
$$

其中， $D$ 为孔径的直径。仿真结果显示，当仅选择1个子孔径时，缺乏统计效应，算法误差等于子孔径倾斜误差。随着子孔径数量增多，统计效应显现，算法误差下降。对于1m口径的望远镜，选择的子孔径数量在10-20个之间时算法误差最小，对于3m口径的望远镜，选择的子孔径数量在20-50个之间时统计误差最小。当选择的子孔径继续增多时，误差将接近望远镜全口径时的倾斜误差，这是因为选择的子孔径越多，对望远镜全口径波前的采样越密，这也就越接近望远镜全口径的波前倾斜。

望远镜口径为1m时，最小算法误差下降为望远镜全口径倾斜误差的 $7 0 \%$ ，当望远镜口径为3m时，最小算法误差下降为望远镜全口径倾斜误差的 $5 0 \%$ 。从图5可以看出，最小算法误差相对于望远镜全口径倾斜误差的下降程度并不随大气湍流（由 $r _ { 0 }$ 表征）的变化而变化，而只与望远镜口径有关，望远镜口径越大，算法误差相对于全口径倾斜误差的下降越多。仿真结果显示，当望远镜口径为10m时，最小算法误差下降为望远镜全口径倾斜误差的 $3 3 \%$ 。这种情况下，如果激光为扩束到1m发射，激光上行抖动误差相比于未校正时的减小 $78 \%$ 0

![](images/454b9a417da6e4b884d02681ad771e0acc3f096b943172ed9eee0ee66cb1e7f0.jpg)  
图5倾斜测量的算法误差随被选择的子孔径数量的变化关系  
Fig.5 Algorithm error of tilt measurement varies with the number of selected subapertures

# 4结论：

本文提出的子孔径优选算法中，当从望远镜子孔径中随机选取部分子孔径时，各子孔径之间受大气湍流的影响相对独立，每个子孔径范围内的波前倾斜将使微透镜的聚焦光斑产生的漂移量也是相对随机的。用平行光标定的基准位置为0点，多个随机漂移量的平均值将接近0值，而且随着子孔径的个数增加越接近0值。但是随着选择的子孔径数量继续增加，各子孔径之间受大气湍流影响的独立性下降，导致各子孔径的平均值更接近全口径的波前倾斜量。仿真结果说明，选择适当的子孔径做统计平均，可以有效的降低信标下行受大气湍流波前倾斜的影响，再由（4）式可以获得激光上行光路的到达角起伏信息，这将用于对激光导引星发射系统的校正，从而获得更加稳定的激光导引星。随着望远镜口径的增大，统计平均算法引入的相对误差越小，当望远镜口径为10m时，算法误差仅为望远镜全口径倾斜误差的 $3 3 \%$ 。

# 参考文献：

[1] FOY R,LABEYRIE A . Feasibility of adaptive telescope with laser probe[J]. Astronomy and Astrophysics, 1985, 152(2):L29-L31.

[2]RAGLAND S, CHINJ, WIZINOWICHP, etal. Recent improvements to the Keck II laser guide star facility[C]// Adaptive Optics for Extremely Large Telescopes 4-Conference Proceedings. 2015.

[3] FOYR,MIGUS A,BIRABENF, et al. The polychromatic artificial sodium star: a new concept for correcting the atmospheric tilt[J].

Astronomy & Astrophysics Supplement Series,1995, 111(3):569-578.

[4] RAGAZZONI R, ESPOSITO S,MARCHETTI E. Auxiliary telescopes for the absolute tip-tilt determination of a laser guide star[J]. Monthly Notices of the Royal Astronomical Society, 1995, 276(1):L76-L78.

[5]ESPOSITO S, RAGAZZONI R, RICCARDI A, et al. Absolute tilt from a Laser Guide Star: a first experiment[J]. Experimental Astron0my, 2000, 10(1):135-145.

[6] BELENKII M S. Tilt angular anisoplanatism and a full-aperture tilt-measurement technique with a laser guide star[J]. Applied Optics, 2000, 39(33):6097-6108.

[7]范承玉,宋正方．人造导引星自适应光学的倾斜决定问题[J]．天体物理学报,1997，17(1):103-106

[8]沈锋．自适应光学的激光导引星及微光波前探测技术[D]．上海：中国科学院上海光学精密机械研究所，2002.

[9]熊耀恒．用于自适应光学系统的激光引导星[J]．天文学进展，2000,

18(1):1-8.

[10] 熊耀恒，白金明．应用自适应光学望远镜所取得的天文观测成 果[J]．云南天文台台刊,2000(2):48-57.

[11] HUANG K, XIONG Y H, LI R W, et al. Experimental result from tip-tilt measurement with a laser guide star at Yunnan Observatories[C]// Proceedings of the SPIE.2016.

[12] 黄凯，周钰，李荣旺,等．激光收发望远镜的几何布局对光束到达角起伏相关性的影响[J]．光学学报,2015,35(7):17-24.

[13] MEILARD N, FOY R, TALLON M, et al. End-to-end model for the Polychromatic Laser Guide Star project (ELP-OA)[C]// 1't AO4ELT Conference-Adaptative Optics for Extremely Large Telescopes.2010.

[14] PAUL R A. Laser Guide Star only adaptive optics : the development of tools and algorithms for the determination of Laser Guide Star tip-tilt[D]. Durham : the University of Durham, 2015.

[15] LUO R Y, CUI WD,LIL ,et al. Vortex beam based more stable annular laser guide star[C]// Proceedings of the SPIE. 2016.

[16] RICCARDI A, ESPOSITO S, RAGAZZONI R. Subpupil estimation of the laser guide star tilt term[C] // Proceedings of the SPIE. 1997.

[17] TYSON R. Principles of adaptive optics [M]. 3rd ed. Florida: CRC Press,2010.

[18] Tyson R K, Frazier B W. Field guide to adaptive optics[M]

Washington: SPIEPress，2012.

# Research on Laser Uplink Angle-of-Arrival Fluctuations Measurement Method for Laser Guided Star Adaptive Optics System

Huang Kai¹ ,Cao Jin' ,Xiao Xiao',Li Yuqiang .School of physics and electrical engineering,Leshan Normal University,Leshan,614ooo,China

2.Yunnan Observatories,Chinese academy of sciences,Kunming,65O216,China)

Tip-tilt indetermination with Laser Guide Star(LGS) is one of the important factors to limit the sky coverage for laser guide star adaptive optics(LGS-AO). Measuring and correcting the angle-of-arrival fluctuations of laser uplink is an effective method to solve this problem. This paper proposed a method to measure angle-of-arrival fluctuations of uplink laser,which without natural guide star and auxiliary telescope.The mean idea of that method is that LGS is detected by Shack-Hartmann wave front sensing and the laser uplink angle-of-arrival fluctuations is reconstructed by the data from selected sub-apertures.In this paper, the relationship between the eror of the optimal algorithm and the number of selected sub-apertures is simulated. The results show that the decline ratio of the minimum algorithm error relative to the telescope's full-aperture tilt error is not related to $\mathbf { r } _ { 0 }$ ，but is related to the telescope's aperture. The larger the telescope aperture is,the more the algorithm error decreases.When the telescope diameter is $1 0 \mathrm { m }$ ，the minimum algorithm error drops to $3 3 \%$ of the telescope's full diameter tilt error.

Key words: Laser guide star; optimization selected; tip-tilt; subapertures