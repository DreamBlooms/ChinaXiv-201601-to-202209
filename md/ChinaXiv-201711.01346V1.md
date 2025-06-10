# CN 53-1189/P ISSN 1672-7673

# 地基光电望远镜对GEO空间碎片探测能力分析

胡静静1,²，刘静¹，崔双星¹，程昊文11.中国科学院国家天文台，北京100012；2.中国科学院大学，北京100049)

摘要：空间碎片的持续增加已严重威胁人类航天活动的安全。为了规避空间碎片对在轨航天器的威胁，需要通过观测获取空间碎片与航天器的位置等信息进行碰撞预警，为航天器采取规避措施提供参考。地基光电望远镜在高轨空间碎片观测方面有绝对优势，根据探测信噪比公式，计算望远镜最小可探测空间碎片的尺寸，并通过观测实验对尺寸计算公式进行验证，分析设备探测能力的影响因素，对两种观测模式下设备探测地球静止轨道空间碎片的能力进行分析，得到口径和曝光时间对探测能力影响的定量关系，可以为观测空间碎片设备建设等提供参考。

关键词：空间碎片；光电望远镜；GEO空间碎片中图分类号：P123.1 文献标识码：A 文章编号：1672-7673(2017)01-0039-06

空间碎片的数量持续增加，已严重威胁航大器在轨运行的安全。为了规避空间碎片的威胁，需要通过观测获取空间碎片与航天器的位置等信息进行碰撞预警，为航天器进行有效规避提供参考。地基光电望远镜是空间碎片观测的重要手段之一，在中高轨空间碎片观测方面占绝对优势。在进行观测空间碎片的光电探测设备建设之前，对设备的探测能力的预先评估可以对未来设备的运行能力有较为完整的了解，为项目的论证和建设提供科学依据。文[1]分析研究了可能的欧洲光学地球静止轨道卫星观测系统的性能。文[2]对地球静止轨道空间碎片观测的编目能力进行了仿真。文[3]对欧洲空间光学监测网的任务计划制定，包括空间碎片选择、探测器的设备参数影响等进行分析。文[4]提出了可用于未来欧洲空间态势感知系统中的一些光学策略。文[5]提出并分析了用反褶积方法处理图像对观测地球静止轨道空间碎片性能的改善情况。文[6]对影响地基空间碎片探测的因素进行了分析。文[7]针对空间碎片光学特性进行了地球静止轨道空间碎片光度测量研究。文[8]分析了光学测角与激光测距一体化的可行性。

本文研究观测设备本身对空间碎片的探测能力，根据CCD探测的信噪比原理，得到最小可探测空间碎片尺寸的计算公式，并分析影响望远镜探测空间碎片的因素，对观测地球静止轨道空间碎片的设备进行探测能力分析，给出探测能力与望远镜口径和曝光时间的定量关系，并通过观测实验对最小探测尺寸仿真计算进行了验证。

# 1望远镜对空间碎片的探测能力计算和影响因素分析

本文选取最小可探测空间碎片尺寸作为望远镜探测能力的表征。在进行望远镜探测能力分析时，除了设备本身的能力外，需要分析观测对象（空间碎片的光学特征)，并考虑夜天光背景对观测的影响。判断过视场空间碎片是否能被望远镜探测器(本文选CCD)探测到的依据为空间碎片信号的信噪比大于CCD 的探测阈值。

# 1.1最小可探测碎片尺寸的计算模型

空间碎片本身不发光，望远镜通过接收碎片反射的太阳光对其进行观测。空间碎片的光学特性与碎片的尺寸、形状、姿态和相位角(探测器、碎片和太阳的夹角)等都有关系。然而空间碎片的数量巨大，且形状各异，目前无法给出准确反映其全部光学特征的关系。在进行探测仿真时，需要作一些假设。本文假设空间碎片为球体，反射类型为漫反射，空间碎片尺寸为其直径。仿真望远镜探测能力时，对空间碎片的光学特性常用两个量描述：空间碎片的反照率（或称反射系数）和相位角。空间碎片的反照率一般由统计得到，在20世纪90 年代早期反照率估计值为 $0 . 0 9 \sim 0 . 1 2$ ，近年来将其修正为 $0 . 1 7 5 ^ { [ 9 ] }$ 。夜天光背景参考传统天文的方法，用星等/平方角秒来表征亮度。

将CCD接收的信号的信噪比作为判断过视场空间碎片能否被探测器探测到的标准，当空间碎片的信噪比大于探测阈值时认为可以被探测到。信噪比计算公式[0]为

$$
S N R = \frac { S _ { \mathrm { o b j } } } { \sqrt { S _ { \mathrm { o b j } } + S _ { \mathrm { b a c k } } + k _ { \mathrm { d a r k } } t _ { \mathrm { d } } + k _ { \mathrm { r d o u t } } ^ { 2 } } } ~ ,
$$

其中， $S _ { \mathrm { \Phi _ { \mathrm { { o b j } } } } }$ 为过视场的空间碎片辐射量； $S _ { \mathrm { b a c k } }$ 为夜天光背景； $t _ { \mathrm { d } }$ 为曝光时间； $K _ { \mathrm { d a r k } }$ 和 $K _ { \mathrm { r d o u t } }$ 分别为探测器CCD 的暗流和读出噪声。

当已知夜天光的亮度时，背景的辐射量为

$$
S _ { \mathrm { b a c k } } = \frac { \pi } { 4 } D ^ { 2 } k _ { \mathrm { F } } \eta \gamma A T M S _ { \mathrm { 0 } } 2 . 5 1 2 ^ { - M _ { \mathrm { b a c k } } } t _ { \mathrm { d } } s c a l e ^ { 2 } Q _ { \mathrm { E } } ,
$$

其中， $S _ { \mathrm { b a c k } }$ 为望远镜接收天光的光子数； $D$ 为望远镜口径 $\mathrm { ~ ( ~ m ~ ) ~ }$ ， $k _ { \mathrm { { F } } }$ 为投影在CCD上的点光源信号在一个像素的光子数占整个光源总信号数的比值(本文选择单个像素的光子数比值的最大值)，它可以由光斑模拟的点扩散函数的峰值半波全宽(FWHM)确定； $\eta$ 为大气透明度； $\gamma$ 为光学系统效率；ATM为大气透过率，是光信号从太空到地球表面的过程中大气对该信号造成的衰减量； $S _ { 0 }$ 为0等星在望远镜可观测波段中每秒在 $1 ~ \mathrm { m } ^ { 2 }$ 面积上发射的光子数； $M _ { \mathrm { b a c k } }$ 为天光的亮度；scale为单个像元的视场;$Q _ { \mathrm { { E } } }$ 为 CCD 的量子效率。

根据信噪比公式和夜天光背景辐射量公式，对给定探测设备，夜天光、曝光时间和探测阈值共同决定了能被观测到的空间碎片的最小辐射量，从而得到望远镜最小可探测空间碎片的尺寸。CCD接收的空间碎片辐射量与空间碎片半径的关系如下：

$$
S _ { \mathrm { \scriptsize { o b j } } } = \frac { \pi } { 4 } D ^ { 2 } k _ { \mathrm { { F } } } \eta \gamma A T M Q _ { \mathrm { { E } } } S _ { 0 } E _ { \mathrm { { r e c } } } \frac { { r _ { \mathrm { { o b j } } } } ^ { 2 } } { 4 R _ { \mathrm { \scriptsize { o b j - s e n s o r } } } ^ { 2 } } \rho _ { \mathrm { { A } } } t _ { \mathrm { { i n t } } } f ( \theta ) ,
$$

其中， $E _ { \mathrm { r e c } } = 1 ~ 3 5 0$ 为太阳常数； $r _ { \mathrm { o b j } }$ 为空间碎片半径； $R _ { \mathrm { o b j - s e n s o r } }$ 为空间碎片相对测站的斜距； $\rho _ { \mathrm { A } }$ 为空间碎片的反照率； $\theta$ 为空间碎片的相位角； $t _ { \mathrm { i n t } }$ 为空间碎片的积分时间； $f ( \theta )$ 为相位角函数。空间碎片尺寸为其半径的2倍。

# 1.2地基光电望远镜观测空间碎片的影响因素

根据信噪比公式，可将影响探测设备探测空间碎片的主要影响因子分为：望远镜口径、CCD 探测器的量子效率、望远镜光学系统效率、CCD 的暗流和读出噪声。其中信噪比随口径、量子效率和光学系统透过率的增加而增加，并随暗流和读出噪声的增加而减小。于是可以得到提高探测设备能力的方法主要有：（1)增大望远镜的口径，收集更多的目标光信号，从而提高暗弱目标的探测能力;(2)提高量子效率和光学系统效率；（3)降低CCD暗流和读出噪声。然而，由于现在CCD的量子效率、暗流和读出噪声的改善余地已经很小（量子效率的峰值已经可以达到 $9 5 \%$ 以上，暗流在采用液氮制冷的条件下基本可以忽略，读出噪声也可以达到个位数)，现阶段光学系统效率与大气透过率、探测器本身的效率和量子效率的乘积一般情况下小于 $3 0 \% ^ { [ 1 1 ] }$ 。所以，增大口径是提高性能比较有效的方法。

对给定设备，还可通过延长曝光时间观测更小的空间碎片。此外，通过图像处理等方法降低CCD 探测阈值也是一种可考虑的方法，由于该影响比较直观，故本文不作进一步分析。

# 2探测能力评估分析

# 表1仿真参数

望远镜最小可探测空间碎片的尺寸与天光背景和碎片在CCD上的积分时间有关。望远镜观测空间碎片有两种模式：一种是跟踪空间碎片模式，此时空间碎片在CCD呈点像，空间碎片信号的积分时间为曝光时间；一种为凝视恒星模式，此时空间碎片在CCD中呈拖长的星像，空间碎片信号的积分时间与空间碎片的运动角速度有关。假设空间碎片为球体，相位角为0，分别对两种观测模式下的望远镜最小可探测空间碎片的尺寸进行仿真分析。仿真基本输人参数见表1（参考文[1]中ESA $1 \mathrm { m }$ 望远镜的参数设置）。

# 2.1跟踪模式下望远镜最小可探测空间碎片的尺寸

对给定望远镜设备，可观测到的最小空间碎片与天光背景和曝光时间有关，图1是对表1中的望远镜观测到的空间碎片的最小尺寸变化趋势图，其中横坐标为天光背景，单位为星等/平方角秒 $( { \mathrm { m a g / a r c } } ^ { 2 }$ )。图2是天光背景为 $2 0 \mathrm { m a g / a r c } ^ { 2 }$ 时，望远镜最小可探测空间碎片的尺寸在不同曝光时间下随口径变化的趋势图。

Table1 Simulation parameters   

<html><body><table><tr><td>Parameters</td><td>Value</td></tr><tr><td>aperture size/m</td><td>1</td></tr><tr><td>pixel size/μm</td><td>13.5</td></tr><tr><td>FWHM/pixel</td><td>10</td></tr><tr><td>CCD number/pixels</td><td>2 048 × 2 048</td></tr><tr><td>field of view/o</td><td>1.2</td></tr><tr><td>exposure time/s</td><td>2</td></tr><tr><td>threshold</td><td>4</td></tr><tr><td>quantum efficiency</td><td>0.9</td></tr><tr><td>optic system efficiency</td><td>0.6</td></tr><tr><td>dark(e-/s/pixel)</td><td>0.05</td></tr><tr><td>readout noise (e-/pixel)</td><td>10</td></tr><tr><td>scale (arc/pixel)</td><td>2.1</td></tr><tr><td>albedo</td><td>0. 175</td></tr><tr><td>atmospheric transmittance</td><td>0.7</td></tr><tr><td>h</td><td>0.6</td></tr><tr><td>ATM</td><td>0.5</td></tr></table></body></html>

![](images/b774feffbce88eab5e431ac941eb71325189e65d356b51354cd56908f3f5ee80.jpg)  
图1最小可探测空间碎片尺寸在不同曝光时间下随天光背景变化趋势图  
Fig.1Detectable size variations as a function of sky background with different exposure time

![](images/af21771d685e8ac2bb0ba70f98a467d50966596e6b35c435b78ed82b9d959424.jpg)  
图2最小可探测空间碎片尺寸随口径和曝光时间变化趋势图  
Fig.2Detectable size variations as a function of exposure time with different aperture size（RD)

由图1，探测能力随天光的星等值增大(即天光变暗)而增大，且随曝光时间的延长，变化趋势趋向稳定，图中曝光时间大于15s后，天光从 $1 6 { \mathrm { ~ m a g / a r c } } ^ { 2 }$ 增加到 $2 1 { \mathrm { ~ m a g / a r c } } ^ { 2 }$ 时，最小可探测空间碎片尺寸均降低了约 $6 6 \%$ ；随着曝光时间的延长，最小可探测空间碎片尺寸降低，但变化趋势变慢，曝光时间从 $2 5 \mathrm { ~ s ~ }$ 改变为 $3 0 \mathrm { ~ s ~ }$ 时，最小可探测空间碎片尺寸降低值在 $4 \%$ 到 $5 . 2 \%$ 之间，而曝光时间从2 s改变为5s时，最小可探测空间碎片尺寸降低值均在 $2 0 . 8 \%$ 到 $2 3 . 4 \%$ 之间。

由图2，最小可探测空间碎片尺寸随口径的增大而减小，趋势变缓，在曝光时间为 $2 \mathrm { s }$ ，曝光口径从 $0 . 5 \mathrm { m }$ 改变为 $1 \mathrm { m }$ 时，最小可探测空间碎片尺寸降低值为 $34 \%$ ，从 $4 \mathrm { m }$ 改变为 $5 \mathrm { m }$ 时，最小可探测空间碎片尺寸降低值为 $1 1 \%$ 。这是因为随着口径的增加，信噪比公式中的分子部分（空间碎片的信号辐射量)与口径的平方成正比，而分母部分与口径近似成正比，分子的增长速度大于分母的增长速度，导致最小可探测空间碎片尺寸减小趋势变缓（分母的空间碎片信号辐射量与空间碎片尺寸的平方成正比）。随着曝光时间的延长，最小可探测空间碎片尺寸降低，但当曝光时间大于某一值时（本例中为20s），变化趋势变慢，曝光时间从55s变为 $6 0 \mathrm { { s } }$ 时，最小可探测空间碎片尺寸降低约 $2 . 5 \%$ ，从$2 \mathrm { ~ s ~ }$ 变为5s时，最小可探测空间碎片尺寸均降低值约为 $2 1 . 8 \%$ 。

综上，在跟踪模式下，对给定设备，可以通过延长曝光时间来探测更小的空间碎片；当其它条件不变时，可以通过调整口径提高探测能力，但随着口径的增加，其能力的增长变慢。当口径大于一定值时，增大口径带来的探测能力的提高远小于设备建设的费用，所以，设备建设时，需要根据探测目的对口径进行筛选。

# 2.2凝视恒星模式下望远镜最小可探测空间碎片尺寸

在凝视恒星模式下，望远镜指向恒星不动，即指向的赤经、赤纬不动，此时空间碎片的积分时间与其运动角速度有关，最小尺寸空间碎片由最短积分时间下的空间碎片的信号辐射量决定。由于地球静止轨道空间碎片的角速度一般不超过 $5 \mathrm { ^ { \prime \prime } / s }$ [12]，本文选用 $5 \mathrm { ^ { \prime \prime } / s }$ 为地球静止轨道空间碎片最大角速度。此时空间碎片在单个像元的积分时间固定，延长曝光时间只会增加天光背景的信号，造成探测能力的降低，如图3。图4显示曝光时间为 $2 \mathrm { ~ s ~ }$ 时，增大口径对最小可探测空间碎片的影响（设备基本参数仍为表1中的设置）。

![](images/44296f6feb851c80ffc4a3087d365b9e34875c21d79d86a4a74f98956d8a9f5e.jpg)

![](images/b47a8a3b211aae78d9d05e7ce507b86835dc89dd62d5a5d09a22e3df0bc8f982.jpg)  
图3最小可探测空间碎片尺寸与曝光时间的关系 Fig.3Detectable size variations as a function of exposure time   
图4最小可探测空间碎片尺寸与口径的关系 Fig.4Detectable size variations as a function of aperture size

对凝视恒星模式，图3表明当曝光时间大于空间碎片积分时间时，延长曝光时间会导致探测能力的降低，但是曝光时间过短，会导致空间碎片的信号量不足（图3中的最低点对应空间碎片在一个像素的停留时间)，所以曝光时间应选择空间碎片信号能被探测到的最短时间。图4表明增大望远镜口径可以提高探测能力，但增长趋势变慢，由此带来性价比的大幅度降低，与图2的分析基本一致。

由图4，表1中的设备在凝视恒星模式下曝光时间为 $2 \mathrm { ~ s ~ }$ 时，最小可探测空间碎片的尺寸约为$0 . 8 2 \mathrm { ~ m ~ }$ ，将口径增大1倍时，最小可探测空间碎片尺寸约为 $0 . 5 6 \mathrm { m }$ ，增大5倍时，最小可探测空间碎片尺寸约为 $0 . 3 5 \mathrm { ~ m ~ }$ ，但成本会大幅度增加，所以需要进行适当的选择。

# 2.3 观测实验

为了验证地基光电望远镜对最小可探测空间碎片尺寸的计算，在2014年11月1日，选取国家天文台兴隆 $1 \mathrm { ~ m ~ }$ 望远镜作为观测设备，目标选择地球静止轨道空间碎片两行轨道根数（Two-LineElements，TLE)编号为30000 的空间碎片在曝光时间为5s时进行拍摄，观测模式为跟踪空间碎片模式，天光背景星等约为20.3，星等测量精度为0.1等。利用IRAF软件进行图像处理，得到空间碎片星等为18.4，并对空间碎片信号最大值所在像元的信噪比进行了计算，基本接近望远镜的探测阈值，利用星等与空间碎片尺寸的关系计算得到空间碎片尺寸约为 $0 . 5 \mathrm { ~ m ~ }$ ，而本文中公式得到的该设备的最小探测尺寸约为 $0 . 4 1 \mathrm { ~ m ~ }$ ，误差为 $1 8 \%$ ，即仿真值比实际值小 $1 8 \%$ 。误差考虑大气传播和模型本身的影响。由观测实验，探测能力仿真基本可以满足对最小可探测空间碎片尺寸的评估。

# 3结论

本文根据探测的信噪比原理，建立了对地基光电望远镜的探测能力即最小可探测空间碎片尺寸的计算模型，并对影响设备探测能力的因素进行了分析。针对探测设备本身，在两种观测模式下，调节曝光时间和口径对地基光电望远镜探测能力的影响进行了分析，发现光学设备探测能力虽然随着曝光时间和口径的增加而增加，但在改进时还需考虑实际情况，如空间碎片信号的可探测性和口径增加对探测能力和成本的影响，曝光时间增加产生CCD满阱现象。由观测实验可知，仿真值比实际值小$1 8 \%$ ，误差考虑大气传播和模型本身的影响，探测能力仿真可以满足对最小可探测空间碎片尺寸的评估，为观测设备建设提供参考。在后续的工作中，将进一步分析引起误差的原因，并对光电观测系统对空间碎片的探测效能进行评估研究，给出覆盖地球静止轨道空间碎片观测的策略建议。

致谢：感谢中国科学院国家天文台兴隆观测基地 $1 \mathrm { m }$ 望远镜的工作人员对本文观测实验提供的支持和帮助。

# 参考文献：

[1] Flohrer T,Schildknecht T，Musci R，et al.Performance estimation for GEO space surveillance [J].Advances in Space Research，2005，35(7）:1226-1235.   
[2] Olmedo E，Nomen J,Sánchez-Ortiz N，et al. Cataloguing capability of objects in the GEO ring [C]//Proceedings of the 6Oth International Astronautical Congress.2009.   
[3] Frih C，Schildknecht T,Hinze A，et al. Optical observation campaign in the framework of the ESA space surveillnce system precursor services [C]// Proceedings of the European Space Surveillance Conference.2011.   
[4] Olmedo E， Sanchez-Ortiz N，Guijarro N，et al. Survey-only optical strategies for cataloguing space debris objects in the future European space surveillance system [J].Advances in Space Research，2011，48(3):535-556.   
[5] Nufez J, Nunez A， Montojo F J,et al. Improving space debris detection in GEO ring using image deconvolution [J]. Advances in Space Research，2015，56(2）:218-228.   
[6] 张己化，姚东升，谈斌.地基光电系统空间目标探测影响因素分析［J］．光学学报，2008， 28(6): 1178-1182. Zhang Yihua，Yao Dongsheng，Tan Bin. Analysis on effct factors of ground-based electro-optic system detection ability on space object[J]. Acta Optica Sinica，2008，28(6):1178-1182.   
[7] 庄诚，隋成华，唐轶峻.GEO空间碎片光度测量标定方法的研究［J]．天文研究与技术 -国家天文台台刊，2011，8(4)：343-346. Zhuang Chen，Sui Chenghua，Tang Yijun. Research of photometric calibration of GeosynchronousOrbit（GEO）space debris ［J]．Astronomical Research & Technology——Publications of National Astronomical Observatories of China，2011，8(4）：343-346.   
[8] 于涌，李岩，毛银盾，等.空间碎片激光测距与光学测角一体化观测试验［J].天文研究与 技术——国家天文台台刊，2013，10(4)：359-364. Yu Yong，Li Yan，Mao Yindun，et al.Expermental observations of space debris integrating laser ranging and optical direction measurement ［J]. Astronomical Research & TechnologyPublications of National Astronomical Observatories of China，2013，10(4） :359-364.   
[9] Mulrooney M K，Matney MJ，Hejduk M D，et al. An investigation of global albedo values [C]// Proceedings of the Advanced Maui Optical and Space Surveillance Technologies Conference.2008.   
[10] Schildknecht T. Optical astrometry of fast moving objects using CCD detectors [M]. Zurich: ETH Zurich Honggerberg，1994.   
[11] 胡企千，姚正秋．天文望远镜设计［M]．北京：中国科学技术出版社，2012：483.   
[12] Shell R J. Optimizing orbital debris monitoring with optical telescopes [C]// Proceedings of the Advanced Maui Optical and Space Surveillance Technologies Conference.2010.

# Analysis of the Detection Ability for the GEO Region of the Ground-Based Electro-Optic Telescope

Hu Jingjing $^ { 1 , 2 }$ ，Liu Jing'，Cui Shuangxing'，Cheng Haowen1 (1.National Astronomical Observatories，Chinese Academy of Sciences，Beijing 10ool2,China; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China，Email：jinghu@ bao.ac.cn)

Abstract: The number of space debris is growing in recently years，and it poses grave threats to the security of spacecrafts.Inorder to manage the risk,itis of vital importance toobtainthe position informationof space debris and spacecrafts by observation and therefore provide pre-warning service.The Ground-Based Electro-Optic Telescope has absolute advantages in terms of observing the GEO region.In this paper，we get the minmum detectable size of debris byusing simulated formula based on signal to noise ratio theory and then use observational tests to verify the computational formula.After analyzing the influencing factors of detection ability and comparing its debris detection ability of the GEO region in two observation modes，we get the quantitative relation between aperture size and exposure time.This paper can provide some reference to devices designed for space debris detection.

Key words: Space debris ；Electro-optic telescope；GEO region debris