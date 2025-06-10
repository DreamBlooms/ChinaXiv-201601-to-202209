# 太阳系外行星全区域高对比度成像设计与数值模拟

沈宇樑1,2,3，窦江培1,2（1.中国科学院国家天文台南京天文光学技术研究所，江苏 南京 210042;2.中国科学院天文光学技术重点实验室（南京天文光学技术研究所），南京210042;3.中国科学院大学，北京100049）

摘要：太阳系外类地行星直接成像探测极具挑战性。在可见光短波段，行星信号主要来自恒星经由行星大气的反射光，两者对比度在 ${ { 1 0 } ^ { - 1 0 } }$ 量级，导致微弱的系外行星光被淹没。因此，有效抑制来自恒星的强光是实现类地行星探测的关键。本文提出了基于光瞳振幅调制和相位校正的技术方案，以实现全区域高对比度成像。针对上述方案，进行了数值模拟分析来说明其可行性及潜在性能。数值模拟基于点扩散函数的能量分布来评价系统的目标成像对比度，并采用随机并行梯度下降迭代算法进行优化，最终成像对比度在360度全区域内获得达到 ${ { 1 0 } ^ { - 1 0 } }$ 量级。研究表明该方案有望用于未来空间类地行星直接成像探测。

关键词：太阳系外行星；类地行星；直接成像成像；高对比度；数值模拟；优化算法中图分类号：TN216 文献标识码：A 文章编号：

# 0引言

太阳系外行星探测是当今天文学领域的研究热点。截止2019年5月，已经探测发现4000多颗太阳系外行星[。系外行星探测包括间接探测和直接成像方法。间接方法主要包含视向速度法、凌星法天体测量以及微引力透镜法，是通过观测恒星物理信息反演，从而获得相关的行星信息，还难以直接获得行星的有效温度、大气等重要物理信息。对系外行星进行直接成像探测，能够测量行星的质量、轨道，并通过进一步光谱分析能够研究行星大气组成、表面重力和有效温度等重要物理信息，是未来确认系外生命特征信号的关键技术[2]。

恒星经过望远镜孔径会产生衍射，且恒星光强度远高于行星光，导致微弱的行星信号被淹没。由于可见光短波段存在大量的生命特征信号，且在获取同等空间分辨率情况下（正比于λ/D，λ为工作波长，D为望远镜口径），对望远镜口径要求降低。因此，可见光波段是未来成像搜寻类地行星的重要工作波段[3.4]。然而，在短波探测围绕类太阳光谱型恒星宜居带内的类地行星，成像对比度需要达到 $1 0 ^ { - 1 0 [ 5 ] }$ 。高对比度星冕仪能够对恒星光进行有效抑制以获得超高对比度成像区域。近年来，国内外研究学者们提出了不同技术原理的星冕仪，理论上成像对比度可以达到 $1 0 ^ { - 1 0 [ 6 , 7 , 8 ] }$ 。但是，星冕仪系统中的非理想光学元件产生的波前畸变会带来散斑噪声，制约实际的成像对比度。在没有波前校正的情况下，成像对比度只有 $\overline { { { 1 0 } ^ { - 7 } } }$ 左右。因此，有效较正波前畸变以抑制消除散斑噪声是实现类地行星超高对比度成像的关键。Malbert首先提出了一种利用可变形镜（DeformableMirror，简称DM）来产生暗区的优化控制算法9]，该方法可在局部区域上实现高达 ${ 1 0 } ^ { - 8 }$ 的成像对比度。

近几年来，得益于可变形镜技术与器件的发展，星冕仪实验成像对比度已经提高至 ${ 1 0 } ^ { - 9 }$ 量级。然而，目前使用的波前校正方案产生的高对比度成像区域较小，无法实现全区域高对比度成像，影响探测探测效率[10,11]。

针对上述问题，本文提出一种360度全区域、超高对比度成像星冕仪技术方案，并给出初步的数值模拟结果。在数值模拟过程中,采用随机并行梯度算法（Stochastic parallel gradientdescentalgorithm，简称SPGD）进行迭代优化，以系统PSF能量反馈控制光瞳能量和波前，使得系统成像对比度达到最优化[12.13]。整个过程分成两步，首先通过优化有限带环状透过率渐变滤光片进行振幅调制，在 $4 \lambda / \mathrm { { D } }$ 处获得 ${ { 1 0 } ^ { - 7 } }$ 的对比度；再使用 $3 2 \mathrm { x } 3 2$ 单元的DM进行波前校正，最终在成像焦面4-14λ/D区域内获得 ${ { 1 0 } ^ { - 1 0 } }$ 的高对比度成像暗区。为了进一步扩大成像区域，还提出一种基于振幅调制和相位校正同时优化的数值模拟方案，最终在成像焦面4-20>/D区域内获得 ${ { 1 0 } ^ { - 1 0 } }$ 的高对比度成像暗区。

# 1优化算法原理

恒星光统通过光学系统在焦面处的点扩散函数如下：

$$
I _ { p s f } ( x , y ) = | \mathrm { F } [ P ( u , v ) e ^ { i \varphi ( u , v ) } | ^ { 2 }
$$

其中，F为相关函数的傅里叶变换， $P ( u , v )$ 为光学系统入瞳处的振幅，本文将对圆形孔径进行讨论； $\varphi ( u , v )$ 为入瞳处的相位。星冕仪系统通过在瞳面处优化 $P ( u , v )$ 和 $\varphi ( u , v )$ 这两个变量来获得高对比对暗区，使用的评价函数如下：

$$
J = \frac { \sum I _ { o u t } ( x , y ) } { \sum I _ { i n } ( x , y ) }
$$

其中 $I _ { i n } ( x , y )$ 为中心区域的能量强度， $I _ { o u t } ( x , y )$ 为高对比对成像区域的能量，该评价函数用于找到成像区域能量相对于中心区域能量的最小值。本文使用的高对比成像区域范围如图1所示，分别在全区域和一半区域内进行优化。

![](images/c8f7c509f27bd0801a8c13211cb679132081f2a008d7897a19df8db6ebea3c39.jpg)  
图1定义优化区域示意图  
Fig.1Definition of optimization region

成像区域的对比度定义如下：

$$
\mathrm { C o n t r a s t } = \frac { I ( x , y ) } { I _ { \mathrm { m a x } } }
$$

其中 $I _ { \mathrm { m a x } }$ 为焦面处的能量最大值， $I ( x , y )$ 为高对比度成像区域内某一点的能量。根据圆孔点扩散函数的分布特点，其能量主要集中在中心艾里斑内，其大小为 $1 . 2 2 \lambda / \mathrm { D }$ ， $I _ { \mathrm { m a x } }$ 为艾里斑中心能量值。又因为圆孔点扩散函数是轴对称的，本文将选择对角线方向来评估成像区域的对比度。

目标函数最优化有诸多不同的优化算法，如遗传算法[13]、SPGD 算法等。本文将使用SPGD算法对振幅和相位进行迭代优化。该算法通过同时施加任意小的扰动到所有的变量上，然后评估评价函数的梯度变化，进行迭代优化[14]。变量更新方程如下：

$$
u ^ { k + 1 } = u ^ { k } - \gamma \delta J ^ { k } \delta u ^ { k }
$$

其中 $k$ 是迭代次数； $u = u _ { 1 } , u _ { 2 } , \ldots , u _ { n }$ 是优化变量； $n$ 是优化的参数个数；γ表时增益系数（目标优化函数最小时取正，反之取负）； $\delta \boldsymbol { u }$ 为服从伯努利分布的任意扰动； $\delta J$ 是评价函数的变化量：

$$
\delta J = J ( \mathfrak { u } + \delta u ) - J ( u ) = J ( u _ { 1 } + \delta u _ { 1 } , \dots , u _ { n } + \delta u _ { n } ) - J ( u _ { 1 } , \dots , u _ { n } )
$$

为了提高计算精度采用双边扰动的方法，此时评价函数的变化量为：

$$
\delta J = J _ { + } - J _ { - } = J \left( u + { \frac { \delta u } { 2 } } \right) - J \left( u - { \frac { \delta u } { 2 } } \right) .
$$

为了加快算法的收敛速度，增益系数 $\gamma$ 将适应于评价函数变化，此时第 $k$ 步的增益系数为：

$$
\gamma ^ { k + 1 } = \gamma ^ { k } \cdot J ^ { k }
$$

# 2数值模拟

# 2.1振幅调制与波前校正分步优化数值模拟

星冕仪结构如图2所示。恒星光通过望远镜焦点（Telescope Focus）并由准直透镜 $\mathbf { L } _ { 1 }$ 进行准直，平行光通过孔径光阑（Pupil Stop）后作用在有限带环状透过率渐变滤光片（Stepped-transmissionFilter）上进行振幅调制，再通过成像镜 $\mathbf { L } _ { 2 }$ 和准直镜 $\mathbf { L } _ { 3 }$ 在瞳面处使用DM进行波前校正；最后通过成像镜 $\mathrm { L } _ { 4 }$ 进行成像，在成像焦面处通过探测器获的高对比度暗区。

![](images/40340281892d52868d10757362c23710069be12479fa1283c9877cfcb6d03aea.jpg)  
图2有限带环状透过率渐变滤光片的星冕仪结构示意图  
Fig.2 Schematic diagram of the coronagraph with circular stepped-transmission filter

使用SPGD优化算法对有限带环状透过率渐变滤光片进行优化设计。滤光片上每一带的透过率作为一个独立变量，多个变量进行同时迭代。经过多次迭代优化后，在4-14>/D 的区域内获得 ${ { 1 0 } ^ { - 7 } }$ 的对比度。图3为优化设计的有限带环状透过率渐变滤光片以及每一环带上对应的透过率。图4为经过有限带环状透过率渐变滤光片调制后在焦面处获得PSF图像。

![](images/e0d3c90ca7d3b91cee6ebd3eccfd6a37dc936f9c16c056cccb4366bf4d3e7848.jpg)

Fig.3Thetransmittancedistributiondiagramofthestepped-transmissonfilter(Leftandthetransmittancecurvealongtheadius

![](images/cc0ecf79a5588b75c3973fedf543e7e8b2e889ec095845dcf01813e2115625c2.jpg)  
图3有限带环状透过率渐变滤光片示意图（左）滤光片沿半径方向上的透过率分布曲线（右)

由于奈奎斯特采样定理的限制[15]，使用 $\mathbf { N } { \times } \mathbf { N }$ 单元的DM进行波前校正时，其可调控理论效范围在 ${ \mathrm { N } } / { 2 } \times \lambda / { \mathrm { D } }$ 之内。理论上可获得的成像对比度可如下经验公式表示[6]：

$$
\begin{array} { r } { \mathrm { C o n t r a s t } = \pi \left( \frac { 2 \pi \sigma } { N \lambda } \right) ^ { 2 } } \end{array}
$$

其中 $\sigma$ 为镜面RMS值， $N$ 为DM的调控单元。根据式（8）可知，可以通过增加DM的单元数或者减小优化范围进一步提高对比度。

本方案模拟了一个 $3 2 \times 3 2$ 的可变形镜，理论优化范围为 $1 6 \lambda / \mathrm { D }$ 。模拟时选用理论优化范围的一半区域进行波前校正。DM中每一块子镜作为一个独立的优化变量，经过多次迭代优化，在 $4 { - } 8 \lambda / \mathrm { D }$ 的全区域内获得 $3 . 5 \times 1 0 ^ { - 1 0 }$ 的对比度，系统通过率 $3 2 . 0 4 \%$ 。图5为DM产生的相位分布图以及经过DM校正之后在焦面处获得PSF 图像（优化范围 $4 { - } 8 \lambda / \mathrm { D }$ 全区域)。图6为 $4 { - } 8 \lambda / \mathrm { D }$ 优化区域内的对比度曲线，其中黑色实线为未调制的对比度曲线，蓝色实线为振幅调制之后的对比度曲线，红色实线为在振幅调制的基础上进行波前校正后的对比度曲线。

![](images/41fe5f1ef9dab4a3d9004b42cb0f9c5144f0f4b4ca6078b0010617f3885f93d5.jpg)  
图4使用有限带环状透过率渐变滤光片调制后，在焦面获得的PSF图像Fig.4 The PSF image on focal plane modulated by stepped-transmission filter  
图5DM相位分布图（优化范围4-8/D）（左）使用DM波前校正后，在焦面获得的PSF图像（右)

3.5DM phase distribution diagram ( $4 { - } 8 \lambda / \mathrm { D }$ optimization range)(Left) the PSF image on focal plane with DM wave-front correct

![](images/31ed4ccb390f26fabc94adbb764f125b81f1f4847576e3967f6ea6729b70c0f7.jpg)  
图 $6 4 – 8 \lambda \mathrm { / D }$ 优化区域内对比度曲线

在 $4 - 1 4 \lambda / \mathrm { D }$ 一半区域进行波前校正，经过多次迭代优化后，在 $4 - 1 4 \lambda / \mathrm { D }$ 一半区域内获得了 $1 . 6 \times 1 0 ^ { - 1 0 }$ 的对比度，系统通过率 $3 2 . 0 4 \%$ 。图7为DM产生的相位分布以经DM校正之后在焦面处获得的PSF图像（优化范围 $4 - 1 4 \lambda / \mathrm { D }$ 一半区域)。图8为 $4 - 1 4 \lambda / \mathrm { D }$ 优化区域内的对比度曲线，其中红色实线为在振幅调制的基础上进行波前校正后的对比度曲线。

![](images/73c96d233ce63a6cfcf58f3a9d59c67646ff05de1ba9c45f548285bc948ae764.jpg)  
Fig.6 Contrast curve in the $4 { - } 8 \lambda / \mathrm { D }$ optimization region

Fig.7DMphasedistributiondiagram( $4 { \cdot } 1 4 \lambda / \mathrm { D }$ optimization range)(Left) the PSF image on focal plane with DM wave-front correction

![](images/9e05e125a94fc4488229997a9c0064d7512ebc74e70c530b9a8ae298211fd108.jpg)  
图7DM相位分布图（优化范围4-14/D）（左）使用DM波前校正后，在焦面获得的PSF 图像（右）  
图84-14>/D优化区域内对比度曲线

# 2.2振幅调制与波前校正同时优化数值模拟

本节讨论进行同时振幅调制和波前相位校正。恒星光通过准直透镜 $\mathrm { L } _ { 1 }$ 进行准直后作用在两个调制器件上进行同时振幅调制和波前校正，然后通过成像镜 $\mathbf { L } _ { 2 }$ 进行成像，在成像焦面上通过探测器获取高对比成像图像，其结构具体如图9所示。

![](images/9601cb3de99804fd69ca297d358922fa3537024c785ccbe88d8f6fc8938bc828.jpg)  
Fig.9 Schematic diagram of the coronagraph with simultaneously optimizing amplitude and phase

振幅和相位在均为环带分布，每一环带上的振幅和相位为一个独立变量，经过多次迭代优化后，在 $4 { \cdot } 2 0 \lambda / \mathrm { D }$ 全区域内得到对比度为 $1 \times { 1 0 } ^ { - 1 0 }$ 的成像暗区，整个系统的透过率为 $1 0 . 5 \%$ 。图10为产生的振幅板和在沿半径方向上的振幅分布曲线。图11为产生的相位板以及经振幅相位优化后在焦面处获得的PSF图像。图12为 $ { 4 - 2 0 \lambda } /  { \mathrm { D } }$ 优化区域内的对比度曲线，其中红色实线为同时振幅调制和波前校正后的对比度曲线。

![](images/2e65b2bba6a9f33690c95c0ac7b0da42dd02e77d4b2613fb7025b56638d1ef78.jpg)  
图9相位振幅相位同时优化星冕仪结构示意图

![](images/3245e7955776dfde078d92940203c9c8a00582a09135fef274dbdfaf43476fbd.jpg)  
Fig.1O Amplitude distribution diagram (Left) and the transmitance curve along radius direction (Right)   
图11相位分布图（左）优化后在焦面获得的PSF图像（右)

Fig.11Phase distribution diagram (Left) the PSF image on focal plane after optimization (Right)

![](images/20a81b866749a68c512e2a223313f48d1d885c3cd981011de939d92ac3362fcd.jpg)  
图10振幅分布图（左）沿半径方向上的透过率分布曲线（右）

# 3．结论

本文提出的两种优化方案在全区域内均获得了 ${ { 1 0 } ^ { - 1 0 } }$ 的对比度，为今后对太阳系外类地行星直接成像提供了可能。表1为三个数值模拟的具体结果。

# 表1振幅相位分步优化和振幅相位同时优化数值模拟结果

Tab.2 Results of phase optimization with setted amplitude and simultaneously optimization amplitude and phase simulation   

<html><body><table><tr><td>Simulation</td><td>1</td><td>2</td><td>3</td></tr><tr><td>IWA(λ/D)</td><td>4</td><td>4</td><td>4</td></tr><tr><td>OWA (λ/D)</td><td>8</td><td>14</td><td>20</td></tr><tr><td>Region</td><td>Whole</td><td>Half</td><td>Whole</td></tr><tr><td>Contast</td><td>3.5×10-10</td><td>1.6×10-10</td><td>1×10-10</td></tr><tr><td>Throught（%）</td><td>34.04</td><td>34.04</td><td>10.5</td></tr></table></body></html>

同时优化振幅与相位可以在较大区域内获得更高的对比度，该方案可进行大区域全视场太阳系外行星探测。该方案的透过率较低，导致实际观测时需要较长的曝光时间，一定程度上影响观测效率。此外，同时优化振幅与相位所需要的控制单元较多，目前 DM的可控单元数无法满足此方案的需求，实际实验中可用空间光调制器（SpatialLightModulator，简称SLM）进行优化调制。使用SLM进行振幅调制相较有限带环状透过率渐变滤光片，更加灵活方便，可以根据瞳面的形状进行实时调制。由于SLM的特性，需在系统中加入两块的线偏振片，导致整个系统的透过率降低。下一步将在目前成像对比度基础上进行透过率优化设计，进一步提高系统透过率；进行相关的测试实验；并展开宽波段高对比度成像的研究。

# High-contrast imaging design and numerical simulation of exoplanets detection in full-working area

Shen Yuliang1.2.3，DouJiangpei' (1.NationalAstronomical Observatories/NanjingInstituteofAstronomicalOptics&TechnologyChineseAcademyofSciences, Nanjing 210042, China; 2.CASKeyLboratoryofstronoicalOptics&TchologyNanjingIstituteofstroomicalOtics&Tchnologyjg0042, China 3.University of Chinese Academy of Sciences,Beijing 1Ooo49, China)

Abstract: The direct imaging on Earth-like exoplanets faces great challenges. The faint planet light is the reflective light from the atmosphere of the planet. Thus,the intensity contrast between the planet and its host star is ${ { 1 0 } ^ { - 1 0 } }$ in the visible wavelength, causing the planet light contaminated by the stronger stellar light. Therefore, it is critical to suppress the strong light from the host star in order to detect the Earth-like exoplanets.In this paper, we propose the apodized pupil amplitude modulation and phase correction technique to achieve an extreme high contrast. We then provide a numerical simulation to demonstrate the feasibility and potential performance.

An iterative Stochastic Parallel Gradient Descent (SPGD) algorithm is applied in the numerical simulation to optimize the target imaging contrast by evaluating the point spread function. Finally, it has demonstrated a contrast on the order of ${ { 1 0 } ^ { - 1 0 } }$ in a whole 360-degree working area. The research demonstrates that the proposed approaches are promoting for the future Earth-like direct imaging detection in the space.

Key words: Exoplanet； Terrestrial planet; Direct imaging;High contrast; Numerical simulation; Optimization algorithm

# 参考文献：

[1]http://exoplanet.eu/catalog/   
[2] 窦江培，朱永田，任德清．太阳系外行星的研究现状[J]．自然杂志,2014,36(2):124-128. DOU JIANGPEI,ZHUYONGTIAN,RENDEQING.Currnt research status of exoplanets[J].Chinese Jourmal of Nature,2014,   
36(2):124-128   
[3] WOOLFNJ,SMITHPS,TRAUB WA,etal.Thespectrum of earthshine:a pale blue dotobserved from the ground[J]. Astrophysical Journal,2002,574: 430-433.   
[4]TURNBULL MC,TRAUB WA,JUCKS K W,etal.The spectrumof earthshine: apale blue dotobserved fromthe ground[J]. Astrophysical Journal,2006,644: 551-559.   
[5]DOUJIANGPEI,REN DEQING.Phasequantizationstudyof spatial lightmodulatorforextreme high-contrast imaging[J]. Astrophysical Journal,2016,832(1).   
[6]GUYONOIVIER,PLUZHNKEUGENE,KUCHNERMARCJ,etal.Theoretical limitsonextrasolarterrestrialplaetdetection with coronagraphs[J].Astrophysical Journal Supplement Series,2006,167(1): 81-99   
[7]RENDEQING,ZHU YONGTIAN.ACoronagraph Basedon Stepped-Transmision Filters[J].Publicationsof theAstronomical Society of the Pacific,2007,119(119):1063-1068.   
[8]DOU JIANGPEI,RENDEQING,ZHUYONGTIAN,etal.Designandtestof ahighcontrastimagingcoronagraphbasedontwo 50-step transmission filters[J].Proceedings of SPIE,2011   
[9]MALBETF,YUJW,SHAOM.Highdynamicrangeimagingusingadeformable mirorforspacecoronography[J].Publcatiosf the Astronomical Society of the Pacific,1995,107(710)   
[10]TRAUGERJT,AUBWA.AlaboratorydmonstrationofthecapabiltytomageanEarth-lkeextrasolarplaet[J].Nature,0 446(7137):771.   
[1] GROFFTD,CARLOTTIA,KASDINNJ,etal.Progressonbroadbandcontrolanddeformable mirrortolerances ina-DM system[J]. Proceedings of SPIE,2010.   
[12]DOUJIANGPEI,RENDEQING,ZHUYONGTIAN.Aniterative wavefrontsensingalgorithforhighcontrastimagingsstems[J]. Research in Astronomy and Astrophysics,2011,11(2): 198-204   
[13]曹芳，赵继勇，吴桢．基于遗传算法的相位差法波前检测 piston 误差[J].天文研究与技术,2011,8(4):369-373. CAO FANG, ZHAO JIYONG, WU ZHEN.Detection of piston errors in wavefront sensing using a genetic-algorithm based phase diversity method[J].AstronomicalResearch& Technology,2011,8(4):369-373.   
[14] REN DEQING,DONGBING,ZHU YONGTIAN,etal.Corectionof noncommon-path errforextremeadaptiveoptics[J]. Publications of the Astronomical Society of the Pacific,2012,124(913):247-253.   
[15] DOUJIANGPEI,RENDEQING,ZHANG XI,etal.Acoronagraphbasedontwospatiallight modulators foractiveamplitude apodizing and phase corrections[J]. Proceedings of SPIE,2014.   
[16]BrownRrosCCasea,taeaetelesefoesigagetrsolaeplatsiaht is HST2[J].Astronomical Telescopes and Instrumentation,2oo3: 95-108.