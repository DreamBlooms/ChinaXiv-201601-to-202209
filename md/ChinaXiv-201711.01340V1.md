# CN 53-1189/P ISSN 1672-7673

# 激光测距系统回波光子分布特性研究

唐美荣},²，和丽娟},²，翟东升},²，李语强}，汤儒峰}，李祝莲(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049)

摘要：激光测距系统回波光子特性分析对激光测距理论研究、系统设计以及性能评估具有重要意义。结合激光测距原理并综合考虑影响激光测距的多种因素，如大气湍流、大气和卷云传输特性、目标距离等，从理论上推导了测距方程以分析研究回波光子的分布特性。同时，利用Matlab软件开发平台编制了相应的激光测距系统回波光子分布特性研究软件，通过设置测距系统中激光器、发射望远镜、接收望远镜以及探测器等相关参数可估算回波光子数，并同时显示相应的函数关系曲线。

关键词：激光测距；回波光子；相关参数；研究软件中图分类号：P228.5 文献标识码：A 文章编号：1672-7673(2017)01-0032-07

激光测距技术是一项综合技术，涵盖激光、电子、微光探测、自动控制、精密光学机械、天文测量和卫星轨道计算等多个学科领域[1]。它通过精确测定激光脉冲从测站到目标的往返飞行时间t，结合光速 $\boldsymbol { \mathbf { \mathit { c } } }$ ，就可获得测站到目标的距离 $R = { _ { c t / 2 } }$ 。激光测距在实际工作中是一个非常复杂的过程，受激光光束的发散角、大气湍流、大气传输特性[2-3]、目标特性[4]、望远镜指向误差[5-6]、距离[7]、接收孔径大小等多种因素的影响，其中任何一个相关因数的变化都会引起激光测距中回波光子数的变化。因此，分析研究回波光子随上述各因素的变化规律，对激光测距理论研究、系统性能评估以及系统设计具有重要意义。

Matlab 是世界上使用最为广泛的数学软件之一，它具有强大的数值计算、数据处理、系统分析、图形显示、符号运算等功能，是一个完整的数学平台[8]。本文利用 Matlab平台开发了用户应用界面，估算上述多种因素对激光测距系统回波光子的影响，通过设置测距系统的相关参数（例如测距波长、能量、接收口径等)可方便直观地对激光测距回波光子分布特性进行分析研究，为测距系统的设计提供理论依据。

# 1回波光子数估算

# 1. 1 激光测距方程

设测距激光器发射的单个激光脉冲能量为 $E _ { \mathrm { t } }$ ，波长为 $\lambda$ ，普朗克常数为 $h$ ，光速为 $\mathbf { \Psi } _ { c }$ ，激光器的发射增益为G，发射系统的发射效率为n,，则从地面测距系统发射的单个激光脉冲的光子数为Em,G,，它以发散半角 $\theta _ { \mathrm { d } }$ 均匀地投向目标(以合作目标为例)，测站到目标的距离为 $R$ ，激光穿过大气的单程透过率为 $T _ { \mathrm { a } }$ ，穿过云层的单程透过率为 $T _ { \mathrm { c } }$ ，则激光脉冲到达目标时，形成面积为 $\pi \left( \theta _ { \mathrm { d } } R \right) ^ { 2 }$ 的光斑，发射处激光束半径为r，而只有到达目标的有效反射面积σ上的光子数Ec $E _ { \mathrm { t } } \frac { \lambda } { h c } \eta _ { \mathrm { t } } G _ { \mathrm { t } } T _ { \mathrm { a } } T _ { \mathrm { c } } \frac { \sigma } { \pi \left( \theta _ { \mathrm { d } } R + r \right) { } ^ { 2 } }$ π(R+r）能以角反射器发散半角 $\theta _ { \mathrm { { m } } }$ 反射回测站，目标的反射率 $\rho$ ，考虑到激光在大气和云层中的双程透过率，望远镜有效接收面积为 $\left| A _ { \mathrm { r } } \right|$ ，接收系统的接收效率为 $\eta _ { \mathrm { r } }$ ，则激光测距过程中，单个激光脉冲能够抵达探测器的平均回波光子数 $n _ { \mathrm { s } }$ 为

$$
n _ { \mathrm { s } } = \left( E _ { \mathrm { t } } \frac { \lambda } { h c } \right) \eta _ { \mathrm { t } } G _ { \mathrm { t } } \frac { \sigma } { \pi \left( \theta _ { \mathrm { d } } R + r \right) { } ^ { 2 } } \frac { A _ { \mathrm { r } } } { \pi \left( \theta _ { \mathrm { m } } R \right) { } ^ { 2 } } \rho \eta _ { \mathrm { r } } { T _ { \mathrm { a } } } ^ { 2 } { T _ { \mathrm { c } } } ^ { 2 } .
$$

1. 1. 1 激光指向偏差和望远镜跟踪误差对回波光子数的影响

假设激光器发射的激光为高斯光束，则高斯光束的发射增益 $G _ { \mathrm { t } }$ 可表示如下[9-1]

$$
G _ { \mathrm { t } } = { \frac { 8 } { \theta _ { \mathrm { d } } ^ { 2 } } } \exp { \left[ - 2 \left( { \frac { \theta _ { \mathrm { p } } } { \theta _ { \mathrm { d } } } } \right) ^ { 2 } \right] } ,
$$

其中， $\theta _ { \mathrm { d } }$ 是激光束的发散半角； $\theta _ { \mathrm { { p } } }$ 是激光束的指向误差。

$n _ { \mathrm { s } }$ 是在没考虑指向误差情况下的平均回波光子数，当考虑指向误差时，单个脉冲的平均回波光子数为[9]：

$$
\left. n _ { \mathrm { s } } \right. = n _ { \mathrm { s } } \int _ { - \infty } ^ { \infty } \mathrm { d } ( \delta \alpha ) p ( \delta \alpha ) \int _ { - \infty } ^ { \infty } \mathrm { d } ( \delta \beta ) p ( \delta \beta ) \ \exp \Bigg [ - \ 2 \left( \frac { \alpha + \delta \alpha + \beta + \delta \beta } { \theta _ { \mathrm { d } } } \right) ^ { 2 } \Bigg ] ,
$$

其中， $\alpha , \beta$ 分别为方位、俯仰指向偏差； $\delta \alpha , \ \delta \beta$ 分别为方位、俯仰实时随机误差； $p ( \delta \alpha ) \mathbf { \delta } _ { \mathbf { \alpha } } p ( \delta \beta )$ 分别为方位、俯仰随机指向误差的概率分布函数。

假设 $p ( \delta \alpha )$ 、 $p ( \delta \beta )$ 均是高斯函数，则：

$$
\begin{array} { c } { { p ( \delta \alpha ) = \displaystyle \sqrt { \frac { 2 } { \pi } } \frac { 1 } { \theta _ { \alpha } } \exp \left[ - 2 \left( \frac { \delta \alpha } { \theta _ { \alpha } } \right) ^ { 2 } \right] , } } \\ { { p ( \delta \beta ) = \displaystyle \sqrt { \frac { 2 } { \pi } } \frac { 1 } { \theta _ { \beta } } \exp \left[ - 2 \left( \frac { \delta \beta } { \theta _ { \beta } } \right) ^ { 2 } \right] , } } \end{array}
$$

其中， $\theta _ { \alpha \mathrm { ~ \bf ~ \gamma ~ } } \theta _ { \beta }$ 分别为望远镜的方位、俯仰跟踪误差。

将(3-1）、（3-2)式代入(3)式，得到：

$$
\langle n _ { \mathrm { s } } \rangle = n _ { \mathrm { s } } \frac { \theta _ { \mathrm { d } \alpha } \theta _ { \mathrm { d } \beta } } { \theta _ { \alpha } \theta _ { \beta } } \exp \left[ - 2 \bigg ( \frac { \alpha ^ { 2 } + \beta ^ { 2 } } { \theta _ { \mathrm { d } } ^ { \ 2 } } \bigg ) \right] \exp \left[ \frac { 2 } { \theta _ { \mathrm { d } } ^ { \ 4 } } ( \alpha ^ { 2 } { \theta _ { \mathrm { d } \alpha } } ^ { \ 2 } + \beta ^ { 2 } \theta _ { \mathrm { d } \beta } { } ^ { \ 2 } ) \right] ,
$$

此处定义：

$$
\frac { 1 } { \theta _ { \mathrm { d \alpha } } { } ^ { 2 } } = \frac { 1 } { \theta _ { \mathrm { d } } { } ^ { 2 } } + \frac { 1 } { \theta _ { \alpha } { } ^ { 2 } } \ ,
$$

$$
\frac { 1 } { \theta _ { _ \mathrm { d } \beta } { } ^ { 2 } } = \frac { 1 } { \theta _ { \mathrm { d } } { } ^ { 2 } } + \frac { 1 } { \theta _ { \beta } { } ^ { 2 } } .
$$

在不考虑指向偏差时，即 $\scriptstyle \alpha = \beta = 0$ ，（4)式可简化为

$$
\langle n _ { \mathrm { s } } \rangle = n _ { \mathrm { s } } \frac { \theta _ { \mathrm { d } \alpha } \theta _ { \mathrm { d } \beta } } { \theta _ { \alpha } \theta _ { \beta } } .
$$

如果望远镜方位、俯仰跟踪误差概率分布相同，即 $\theta _ { \alpha } = \theta _ { \beta } = \theta _ { \mathrm { j } }$ ，则(5)式可表示为

$$
\langle n _ { \mathrm { s } } \rangle = n _ { \mathrm { s } } \frac { \theta _ { \mathrm { d j } } ^ { ~ 2 } } { \theta _ { \mathrm { j } } ^ { ~ 2 } } = n _ { \mathrm { s } } \frac { 1 } { 1 + \frac { \theta _ { \mathrm { j } } ^ { ~ 2 } } { \theta _ { \mathrm { d } } ^ { ~ 2 } } } .
$$

其中， $\theta _ { \mathrm { j } }$ 是望远镜的跟踪误差。

将(1）、(2)式代入(6)式，得到单个激光脉冲在接收器光敏面上产生的平均回波光子数方程为

$$
\left. { \boldsymbol n } _ { \mathrm { s } } \right. = \left( E _ { \mathrm { s } } \frac { \lambda } { h c } \right) \eta _ { \mathrm { t } } \frac { \sigma \rho } { \pi \left( \theta _ { \mathrm { d } } R + r \right) ^ { 2 } } \frac { 8 } { \theta _ { \mathrm { d } } ^ { 2 } } \exp \left[ - 2 \left( \frac { \theta _ { \mathrm { p } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } \right] \left[ \frac { 1 } { 1 + \left( \frac { \theta _ { \mathrm { j } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } } \right] \frac { A _ { \mathrm { r } } } { \pi \left( \theta _ { \mathrm { m } } R \right) ^ { 2 } } \eta _ { \mathrm { r } } T _ { \mathrm { a } } ^ { 2 } T _ { \mathrm { c } } ^ { 2 } .
$$

# 1.1.2大气湍流对回波光子数的影响

激光束在大气中传输时，不只受大气散射和吸收的影响，还受大气湍流的影响，当激光束在大气湍流中传输时，由于大气折射率的随机起伏，光束的波前相位发生畸变，从而产生光束扩展、漂移及光强闪烁等现象[12]。

当激光束沿 $Z$ 轴在大气中传输时，对垂直于 $Z$ 轴且在 $R _ { \mathrm { o } }$ 处的一平面取一个曝光非常短的光斑图像

如图1，一个半径为 $\rho _ { \mathrm { { s } } }$ 的扩展了的光斑，光斑漂移至距原中心 $o$ 为 $\rho _ { \mathrm { c } }$ 处，当观测时间较长时，众多短期项漂移量 $\rho _ { \mathrm { c } }$ 和扩展量 $\rho _ { \mathrm { { s } } }$ 综合效应表现为长期项扩展 $\rho _ { \mathrm { { L } } }$ ，其均方值为[9,13]

$$
\langle { \rho _ { \mathrm { L } } } ^ { 2 } \rangle = \langle { \rho _ { \mathrm { c } } } ^ { 2 } \rangle + \langle { \rho _ { \mathrm { s } } } ^ { 2 } \rangle ,
$$

$\langle { \rho _ { \mathrm { L } } } ^ { 2 } \rangle$ 定义为

$$
\langle { \rho } _ { \mathrm { L } } ^ { ~ 2 } \rangle = \frac { \displaystyle \iint \mathrm { d } ^ { 2 } \rho \rho \Gamma _ { 2 } ( z , ~ \rho , ~ \rho ) } { \displaystyle \iint \mathrm { d } ^ { 2 } \rho \Gamma _ { 2 } ( z , ~ \rho , ~ \rho ) } ~ .
$$

在 $z = 0$ 平面上的初始高斯光场分布 $u _ { \mathrm { o } } ( \rho ^ { \prime } )$ 为

$$
u _ { \mathrm { o } } ( \rho ^ { \prime } ) = e ^ { \big ( - \frac { \rho ^ { \prime 2 } } { 2 r ^ { 2 } } - \frac { i k \rho ^ { \prime 2 } } { 2 F } \big ) } ,
$$

![](images/63544ca1b714788c2415f79dd0de6356282cfc12e622e17df22f236568840403.jpg)  
图1远场处的光斑分布 Fig.1Intensity distribution in the far field

其中， $\boldsymbol { r }$ 为光束的初始半径； $F$ 为曲率半径。

光场分布二阶矩公式为[13-14]

$$
{ \cal T } _ { 2 } ( R _ { \circ } , \ \rho _ { 1 } , \ \rho _ { 2 } ) \ : = \ : \left( \frac { k } { 2 \pi R _ { \circ } } \right) ^ { 2 } \iint \mathrm { d } ^ { 2 } \rho _ { 1 } ^ { \prime } \iint \mathrm { d } ^ { 2 } \rho _ { \ 2 } ^ { \prime } u _ { \circ } \left( \rho _ { \ 1 } ^ { \prime } \right) u _ { \circ } ^ { \ast } \left( \rho _ { 2 } ^ { \prime } \right) \ : .
$$

$$
 \exp \{ \frac { i k } { 2 R _ { \circ } } [ ( \rho _ { 1 } - \rho _ { 1 } ^ { \prime } ) ^ { 2 } - ( \rho _ { 2 } - \rho _ { 2 } ^ { \prime } ) ^ { 2 } ]   \exp  i   \exp  \{ \alpha ( \rho _ { 1 } ^ { \prime } - \rho _ { 2 } ^ { \prime } ) ^ { 2 } \} \}
$$

将(10)式代入(11)式，可以得到：

$$
\langle { \rho _ { \mathrm { { L } } } } ^ { 2 } \rangle \approx \frac { { R _ { \mathrm { { o } } } } ^ { 2 } } { k ^ { 2 } r ^ { 2 } } + r ^ { 2 } \left( 1 - \frac { R _ { \mathrm { { o } } } } { F } \right) ^ { 2 } + \frac { 1 7 . 6 { R _ { \mathrm { { o } } } } ^ { 2 } } { k ^ { 2 } { r _ { \mathrm { { o } } } } ^ { 2 } } \ ,
$$

其中， $r _ { \mathrm { { o } } }$ 为大气相干长度；波数 $k = 2 \pi / \lambda$ ； $R _ { \mathrm { o } }$ 为光束受大气湍流影响的传输距离。

由于短期项漂移与扩展体现的是大气湍流对激光束的实时效应，而长期项扩展是包括短期项漂移与扩展的综合效应，因此本文用大气湍流对激光束的长期项扩展来分析激光测距中回波光子数。长期项扩展的半径为 $\sqrt { \langle { \rho _ { \mathrm { L } } } ^ { 2 } \rangle }$ ，将其代入(7)式，得到单个激光脉冲在接收器件光敏面上产生的平均回波光子数方程为

$$
\langle \boldsymbol { n } _ { s } \rangle = \left( E _ { \mathrm { s } } \frac { \lambda } { h c } \right) \frac { \eta _ { \mathrm { r } } \sigma \rho } { \pi \left( \theta _ { \mathrm { d } } R + r + \sqrt { \langle \rho _ { \mathrm { l } } , ^ { 2 } \rangle } \right) ^ { 2 } } \frac { 8 } { \theta _ { \mathrm { d } } ^ { 2 } } \exp \left[ - 2 \left( \frac { \theta _ { \mathrm { p } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } \right] \left[ \frac { 1 } { 1 + \left( \frac { \theta _ { \mathrm { j } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } } \right] \frac { A _ { \mathrm { r } } \eta _ { \mathrm { r } } } { \pi \left( \theta _ { \mathrm { m } } R \right) ^ { 2 } } T _ { \mathrm { a } } ^ { 2 } T _ { \mathrm { e } } ^ { 2 } \mathrm { ~ . ~ }
$$

1.1.3大气和云层对回波光子数的影响

能见度是以气象能见距离度量的[15]。气象能见距离是指正常视力的人在当时天气条件下，能够从天空背景中看到和辨认目标物(黑色，大小适度)的最大水平距离[16]。用经验公式确定的大气衰减计算公式为[17-19]

$$
\beta _ { \mathrm { a } } = \frac { 3 . 9 1 } { V _ { \mathrm { a } } } \left( \frac { \lambda } { 0 . 5 5 } \right) ^ { - q } ,
$$

其中， $V _ { \mathrm { a } }$ 和 $\lambda$ 的单位分别为 $\mathrm { k m }$ 和 $\mu \mathrm { m }$ ；当大气能见度 $V _ { \mathrm { a } } < 6 ~ \mathrm { k m }$ 时， $q = 0 . 5 8 5 V _ { \mathrm { a } } ^ { ~ 1 / 3 }$ ；中等能见度时， $\boldsymbol { q }$ $= 1 . 3$ ；当能见度 $V _ { \mathrm { a } } > 8 0 ~ \mathrm { k m }$ 时， $\textstyle q = 1 . 6$ 。所以大气透过率 $T _ { \mathrm { a } }$ 为

$$
T _ { \mathrm { a } } = 1 - \beta _ { \mathrm { a } } \ .
$$

厚积云的存在限制了光波长的范围，对于总光学厚度小于0.5的云层，波长范围从 $0 . 3 1 7 ~ \mu$ 到$1 2 \mu$ 的卷云透过率的计算公式为[9]

$$
T _ { \mathrm { { c } } } = \exp \left[ - \ 0 . 1 4 \ ( t _ { \mathrm { { c } } } { \mathrm { s e c } } \theta _ { \mathrm { { a } } } ) \ ^ { 2 } \right] ,
$$

其中， $t _ { \mathrm { c } }$ 为平均卷云厚度； $\theta _ { \mathrm { a } }$ 为天顶角。

将 $1 4 \sim 1 6 )$ 式代入(13)式，得到单个激光脉冲在接收器光敏面上产生的平均回波光子数方程为

$$
\langle n _ { \mathrm { s } } \rangle = \left( E _ { \mathrm { t } } \frac { \lambda } { h c } \right) \eta _ { \mathrm { t } } \frac { 8 } { \theta _ { \mathrm { d } } ^ { \textrm { 2 } } } \exp \left[ - 2 \left( \frac { \theta _ { \mathrm { p } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } - 0 . 2 8 \left( t _ { \mathrm { e } } \sec \theta _ { \mathrm { a } } \right) ^ { 2 } \right] \left[ \frac { 1 } { 1 + \left( \frac { \theta _ { \mathrm { j } } } { \theta _ { \mathrm { d } } } \right) ^ { 2 } } \right]
$$

$$
\left( 1 - \frac { 3 . 9 1 } { V _ { \mathrm { a } } } \left( \frac { \lambda } { 0 . 5 5 } \right) ^ { - q } \right) ^ { 2 } \frac { \sigma \rho } { \pi \left( \theta _ { \mathrm { d } } R + r + \sqrt { \left. \rho _ { \mathrm { L } } ^ { 2 } \right.  ^ { 2 } } } \frac\right) { A _ { \mathrm { r } } \eta _ { \mathrm { r } } } { \pi \left( \theta _ { \mathrm { m } } R \right) ^ { 2 } } .
$$

# 1.2 软件设计

由1.1节可见，测距回波光子分布受多种因素的影响，实际的激光测距过程极其复杂。为了更好地对测距回波光子分布特性进行分析与研究，利用Matlab平台下的图形用户界面（Graphical UserInterface，GUI)开发了激光测距回波光子分布特性分析软件，分析研究并实时显示诸因素对回波光子数的影响。软件界面包括：发射系统（如激光能量、波长、发散角、指向偏差、望远镜的跟踪误差等)，接收系统（如望远镜有效接收口径、目标有效光学直径、角反射器反射回测站的光束发散角、目标距离等)，大气和云层透过率，湍流等因素，相关图形和结果显示项等，如图2、图3。

![](images/63234d3f9927dfd441ccdac43e8d008bf32710f4441fabb1ed21be78a860434b.jpg)  
Fig.2Echo photon number variation as a function of distance

![](images/8ddc3ef16370d329d661741112c688e06681dc7456a594058eb6da8254bbde3c.jpg)  
图2回波光子数与距离的关系图  
图3不同天顶角时回波光子数与距离的关系图

Fig.3Echo photon number variationas a functionof distanceunder the condition of diferent zenith angles

平均回波光子数和目标距离的关系如图2。在其它各参数相同的情况下，探测到的回波光子数随距离的增大而减少；当修改任一参数时，回波光子数将作相应的改变。

在界面上可以便捷地选择输出不同的关系图，以图3不同天顶角情况下回波光子数与距离的关系为例，由于随着海拔高度的升高，大气的衰减系数降低，因此，在地面激光测距时，沿竖直方向的探测距离要比沿水平方向大得多。沿各个不同天顶角探测到的平均回波光子数随距离的变化由图可知：在大气条件相同的情况下，沿竖直方向和水平方向探测到的平均回波光子数的差别随距离的增大而减小。当探测距离相同时，天顶角从 ${ 0 } ^ { \circ }$ (竖直方向)到 $9 0 ^ { \circ }$ (水平方向)变化的过程中，在天顶角较小时，随着天顶角的增大，回波光子数减少较慢。当天顶角较大时，随着天顶角的增大，回波光子数减少很快。这主要是受大气中气溶胶对光的吸收和散射的影响[20]。软件根据(17)式编写，综合考虑多种因素，具有较强的通用性。

# 2测距系统回波光子数估算

以云南天文台 $1 . 2 \mathrm { ~ m ~ }$ 望远镜原有的激光测距系统为例，估算测距系统回波光子数。系统参数[13,21]：单个激光脉冲的能量 $E _ { \mathrm { t } }$ 是0.15J，波长 $\lambda$ 是 $5 3 2 \mathrm { n m }$ ，激光束的初始半径 $\boldsymbol { r }$ 是 $3 0 \mathrm { c m }$ ，激光发射系统的发射效率 $\eta _ { \mathrm { t } }$ 是0.5，激光束的发散半角 $\theta _ { \mathrm { d } }$ 是 $1 0 ^ { \prime \prime }$ ，激光束的指向误差 $\Delta \theta _ { \mathrm { { p } } }$ 是 $3 0 ^ { \prime \prime }$ ，望远镜的跟踪误差 $\Delta \theta _ { \mathrm { j } }$ 是 $1 0 ^ { \prime \prime }$ ，目标的有效光学直径 $D _ { \mathrm { o } }$ 是 $\mathrm { ~ 1 ~ m ~ }$ ，角反射器反射回测站的光束发散半角 $\theta _ { \mathrm { { m } } }$ 是 $2 0 ^ { \prime \prime }$ ，目标的反射率 $\rho$ 是0.8，望远镜有效口径 $D _ { \mathrm { r } }$ 是 $1 . 0 6 0 \mathrm { m }$ ，光束受大气湍流影响的传输距离 $R _ { \mathrm { o } }$ 是 $3 0 \mathrm { k m }$ ，大气相干长度 $r _ { \mathrm { { o } } }$ 是 $1 0 \ \mathrm { c m }$ ，接收系统的接收效率 $\eta _ { \mathrm { r } }$ 是0.5，激光穿过大气的单程透过率 $T _ { \mathrm { a } }$ 是0.8，激光穿过云层的单程透过率 $T _ { \mathrm { c } }$ 是0.84。由图4可知，测站到目标的距离 $R$ 范围为 $4 0 0 ~ \mathrm { k m }$ 到 $1 ~ 0 0 0 ~ \mathrm { k m }$ 时，得到的平均回波光子数约为 $2 . 1 \times 1 0 ^ { 1 0 }$ 。

![](images/6380884ca9fdfb45e28de89baea3a5eb216deb93e28272885cb020eecc8661be.jpg)  
图4回波光子数与距离的关系图  
Fig.4Echo photon number variation as a function of distance

# 3结论

本文较全面地考虑了影响激光测距的各种因素，给出了测距方程较详细的推导和表达式，并对测距中回波光子数进行了理论分析和估算；利用Matlab平台编制了一套关于激光测距系统回波光子分布特性的通用分析软件，在界面上可以针对不同的测距系统便捷地调整每个相关参数，还可以通过关系图更直观地对系统的各相关参数和回波光子数进行总体分析，从而为探测器的选择及测距系统的设计提供理论依据。在今后的工作中将对探测器和测距系统进行相关的分析和研究；在实际工作中，由于激光测距过程的复杂性，将对软件部分参数做深一步的探讨，对系统进行进一步优化。

# 参考文献：

[1] 叶叔华，黄城．天文地球动力学［M]．山东：山东科学技术出版社，2000.  
[2] 付强，姜会林，王晓曼.激光在大气中传输特性的仿真研究［J].空军工程大学学报：自然科学版，2011，12(2)：57-61.Fu Qiang， Jiang Huilin，Wang Xiaoman. Study of laser transmission characteristics in atmosphereby simulation [J]. Journal of Air Force Engineering University：Natural Science Edition，2011,12(2): 57-61.  
[3] 严卫，张日伟，代登坡，等.激光大气传输特性及其回波信号仿真研究［J]．电波科学学报，2012，27(3)：564-571.Yan Wei， Zhang Riwei， Dai Dengpo，et al. Simulation research on the atmospheric transmissioncharacteristics and the return signal for laser[J]. Chinese Journal of Radio Science，2012，27(3) : 564-571.  
[4] 张雷洪，杨艳，臧华国，等．目标反射特性对激光测距的影响［J]．中国激光，2008，35(7）：1001-1004.Zhang Leihong，Yang Yan， Zang Huaguo，et al.Reflective characteristics of target in laserrangefinder ［J].Chinese Journal of Lasers，2008，35(7）：1001-1004.  
[5] 瞿锋，卫志斌，程伯辉，等.恒星跟踪与人卫激光测距仪望远镜指向修正［J]．测绘科学，2004，29(2): 55-56.  
[6] 黄宝利，韩兴伟，张楠，等.卫星激光测距系统的指向偏差修正［J].激光与红外，2014,44(7) : 715-719.Huang Baoli， Han Xingwei, Zhang Nan，et al. Axis correction of satellite laser ranging systembased on image processing technique [J]. Laser & Infrared， 2014, 44(7） : 715-719.  
[7] 李语强，李荣旺，李祝莲，等.非合作目标分光路激光测距中距离值的确定方法［J]．天文研究与技术—国家天文台台刊，2012,9(2)：137-142.Li Yuqiang，Li Rongwang，Li Zhulian，et al. Determination of the distance to a non-coorperativetarget in laser ranging with separate optical paths [J]. Publications of the Yunnan ObservatoryPublications of National Astronomical Observatories of China，2012,9(2）:137-142.  
[8] 宋敏，王江，杨向东，等.激光测距参数分析软件的设计［J].激光杂志,2004，25(2)：55-56.Song Min，Wang Jiang，Yang Xiangdong，et al. Designing the laser measurement parameter[J].Laser Journal,2004，25(2) : 55-56.  
[9] Degnan JJ. Millimeter accuracy satelite laser ranging: a review [J]. Contributions of SpaceGeodesy to Geodynamics: Technology，1993:133-162.  
[10]Degnan J J. Theoretical performance of NASA's SGSLR system ranging to GNSS Satelites[C]// Sigma Space Corporation ILRS Technical Workshop. 2015.  
[11]Ndlovu S C，Combrinck L,Exertier P,et al. An estimation of the number of expected returnedphotons for the HartRAO Lunar Laser Ranger system [C]// 19th International Workshop onLaser Ranging. 2011.  
[12］柯熙政，王婉婷.部分相干光在斜程和水平大气湍流中的光强与扩展［J].应用科学学报，2015，33(2): 142-154.Ke Xizheng，Wang Wanting. Intensity and expansion of partially coherent beam propagating inslant and horizontal atmospheric turbulence [J]. Journal of Applied Sciences，2015，33（2）:142-154.  
[13] 熊耀恒．月球激光测距的新技术方法研究［D]．昆明：中国科学院国家天文台云南天文台，2001.  
[14] Fante R L.Electromagnetic beam propagation in turbulent media ［J].Proceedings of theIEEE，1976,63(12）：1669-1692.  
[15] 李景真，苏世学，赵俊民．光学手册［M].北京：清华大学出版社．1998.  
[16] 戴阳，程学武，李发泉，等．目标反射特性与激光测距回波强度关系的研究［J].激光杂志，2007，28(3):83-84.Dai Yang，Cheng Xuewu，Li Faquan，et al. Study on the relationship of return power withdifferent reflection model of object in laser ranging [J]. Laser Journal,2007,28(3）: 83-84.  
[17] 蓝信钜.激光技术［M].北京：科学出版社，2000.  
[18] 王海先，叶艾．大气衰减系数对激光测距能力影响的研究［J]．舰船科学技术，2007，29(6): 116-119.Wang Haixian，Ye Ai. The influence of the coefficient of atmospheric attenuation to thecapability of laser ranging ［J]. Ship Science and Technology，2007，29(6）：116-119.  
[19] 郭豪，邱琪，马娜，等.不同能见度下激光测距仪最大测程的数值算法［J].红外与激光工程，2013，42(12)：3330-3334.Guo Hao,Qiu Qi，Ma Na,et al.Numerical algorithm for maximum range of laser rangefinder indifferent visibility[J].Infrared and Laser Engineering，2013，42(12）:3330-3334.  
[20] 赵少卿，张雏.激光大气传输特性仿真及对激光测距的影响［J］.激光与光电子学进展，2013(11): 55-60.Zhao Shaoqing，Zhang Chu. Simulation on atmospheric transmission characteristic of laser andits impact on laser ranging[J]. Laser & Optoelectronics Progress，2013(11）: 55-60.  
[21] 李祝莲，熊耀恒，何妙婵，等.云南天文台人造卫星激光测距系统原理［J］．天文研究与技术—国家天文台台刊，2008，5(3)：248-252.Li Zhulian，Xiong Yaoheng，He Miaochan，et al. Principle of 1.2m telescope Satelite LaserRanging system ［J]. Publications of the Yunnan Observatory——Publications of NationalAstronomical Observatories of China，2008，5(3）:248-252.

# Research on the Distribution of Echo Photons in Laser Ranging System

Tang Meirong $^ { 1 , 2 }$ ， He Lijuan $^ { 1 , 2 }$ ， Zhai Dongsheng $^ { 1 , 2 }$ ,Li Yuqiang'，Tang Rufeng',Li Zhulian' (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650011,China，Email:lzhl@ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 10oo49,China)

Abstract:Analysis of echo photons‘characteristics in laser ranging system is of great significance for laser ranging theory，system design as wellas performance evaluation.Taking both laser ranging principles and a number of other factors—such as atmospheric turbulence，transfer features of the atmosphere and cirrus， targetrange，etc.—into consideration，this paper provides a laser ranging equation to analyze the distribution characteristics of echo photons.Correspondingly，a set of software is programmed with Matlab to characterize thedistribution feature of echo photons.Once relevant parameters of the laser，the launch，the receive telescope，the detector and soon are set，the software can estimate the number of echo photon and illustrate the relation curve of the corresponding function.

Key words: Laser Ranging；Echo photons ； Relevant parameters ；Research software