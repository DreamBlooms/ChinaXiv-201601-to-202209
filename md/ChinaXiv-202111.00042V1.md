# BLLac天体CGRaBSJ0141-092的光变特性分析

常鑫”²，易庭丰”²，杨星”²，龚云露4，张加健¹，毛李胜‘  
(1云南师范大学 物理与电子信息学院，云南 昆明 650500；2广西相对论天体物理重点实验  
室 广西 南宁 530004；3 广西大学物理科学与工程技术学院 广西 南宁 530004；4 云南大学物理科学与天文学院 云南 昆明 650500)

摘要：Owens Valley Radio Observatory (OVRO)40 米望远镜的观测数据显示了 BL Lac天体CGRaBSJ0141-0928在 15GHz 射电波段的剧烈光变．我们利用Lomb-Scargle-Periodogram (LSP)方法和加权小波 Z 变换(Weight Wavelet Z-transform，WWZ)方法以及Jurkevich方法分析了CGRaBSJ0141-0928的光变周期，结果显示该天体具有约为649 天的准周期振荡(Quasi-Periodic OScillation，QPO)，其置信度为 4.4o，其准周期振荡可能是由喷流的螺旋运动产生．我们用双指数函数拟合了其中2个爆发的过程，从而得到其光变时标，进而估算其平均多普勒因子为3.8，这表明CGRaBSJ0141-0928在射电辐射波段存在显著的聚束效应．采用 DCF(Discrete Correlation Function）方法对射电波段分别与 Gamma-ray、光学 R 波段的光变相关性进行分析，发现光学光变与射电光变有强相关性，且光学光变超前于射电光变 $6 6 \pm 4 0$ 天.

关键词：CGRaBSJ0141-0928；LSP方法；加权小波Z变换方法；Jurkevich 方法；多普勒因子中图分类号：P141.5 文献标识码：A 文章编号：

# 0引言

耀变体（Blazar）是活动星系核(Active Galactic Nuclei，AGNs）中性质较为特殊的子类，其相对论性喷流几乎正对着地球。耀变体具有极端的观测特性，包括高光度、高偏振、快速光变，以及从射电到高能γ射线的非热连续辐射。耀变体的两个子类分别是平谱射电耀变体（FSRQ）和蝎虎座 BL 型天体（BL Lac）[2]。其中 BL Lac 天体的光谱只有一些微弱的发射线或者没有发射线，但是有很强的X射线及 $\gamma$ 射线辐射。研究发现，一些 BLLac 天体的长期尺度变化是周期性的，且不同波段之间可能存在不同的联系。通过对 BLLac天体光变的观测和研究能获得天体的物理机制，辐射过程和内部结构参数等重要信息[4]，对活动星系核的探索和了解有重要意义。

CGRaBS J0141-0928 是一颗红移为0.733 的耀变体[5]，分析 BL Lac 天体光变周期的方法有很多，最常用的有自相关函数分析及周期拟合法，时间序列的功率谱分析方法，Jurkevich 方法，这些方法都十分广泛的应用在 BL Lac 天体的长周期光变观测与研究中[]。本文分别使用Lomb-Scargle periodogram 方法，加权小波 Z 变换方法和 Jurkevich 方法对 CGRaBS J0141-0928天体 $1 5 ~ \mathrm { G H z }$ 射电波段的光变周期进行研究。利用双指数函数拟合了爆发过程，并估算了多普勒因子。使用离散相关函数(DCF)方法分析了 $\gamma$ 和射电波段，以及光学和射电波段的相关性[，其中 LSP 方法和加权小波 Z变换法是初次用于研究 CGRaBS J0141-0928 天体的光变周期。

这三种方法都非常适合处理非等间隔数据，得到的结果是比较稳定的周期。

# 1样本和光变曲线

美国欧文斯谷射电天文台(Owens Valley Radio Observatory，OVRO)的 40m 望远镜是全球观测耀变体理想的设施(https://sites.astro.caltech.edu/ovroblazars/)。如图1是来自于(OVRO)40米望远镜 BLLac天体CGRaBSJ0141-0928在15 GHz射电波段的光变曲线，其中有 575个数据点。从光变曲线可以看出：CGRaBS J0141-0928在射电波段的活动非常激烈，流量随着时间波动起伏，除了在2010年、2013年、2015年、2017年和2019 年有五次明显的大爆发外，还可以看到有一些不同程度的小爆发（光变曲线的尖峰处）。我们通过计算光变幅度Amp8来判断天体的活跃程度：

$$
A m p = 1 0 0 \times \sqrt { \left( A _ { \operatorname* { m a x } } - A _ { \operatorname* { m i n } } \right) ^ { 2 } - 2 \delta ^ { 2 } } p e r c e n t .
$$

其中 $\mathrm { A } _ { \mathrm { m a x } }$ 和 $\mathrm { A } _ { \mathrm { m i n } }$ 分别表示流量的最大值和最小值，Amp 值越大表示天体越活跃。计算得到 PKS0139-097 天体在射电波段的光变幅度为 62.7，表明CGRaBS J0141-0928 是个非常活跃的天体。由于受观测条件的限制，光变曲线数据不连续，因此周期性分析是受到限制的。

![](images/8fa2e38a9a451f7504f27e61233df6e35c91a09d87f05dca31890a3c9b65b6a4.jpg)  
图1CGRaBSJ0141-0928在射电波段的光变曲线  
Fig.1 The light curves of CGRaBS J0141-0928 at radio band

# 2周期分析

# 2.1 Lomb-Scargle periodogram（LSP）方法

Lomb-Scargle periodogram（LSP）是一种广泛用于寻找准周期振荡的方法（Lomb1976;Scargle 1982；Press et al.1992），由 Lomb 发展，经过 Scargle 进一步改进。LSP方法不仅能在一定程度上减弱时域序列的不均匀性产生的虚假信号，还可以有效地从时域序列中提取出弱周期信号9。因此，LSP 方法能很好的寻找隐藏在噪声中的准周期振荡光变。LSP 方法的基本原理是基于傅立叶变换，将一系列三角函数的线性组合 $y = a$ cos $\textit { \textbf { \omega } } t + \textit { \textbf { b } }$ sin $\mathrm { ~ \textit ~ { ~  ~ } ~ }$ 通过最小二乘法来拟合时间序列，将信号特征从时域转换到频域上。基本公式如下[10-11]

$$
P _ { L S } ( f ) = { \frac { 1 } { 2 } } \{ { \frac { [ \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } x { \big ( } t _ { i } { \big ) } \cos \omega { \big ( } t _ { i } - \tau { \big ) } ] ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } \cos ^ { 2 } \omega { \big ( } t _ { j } - \tau { \big ) } } } + { \frac { \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } x { \big ( } t _ { i } { \big ) } \sin \omega { \big ( } t _ { i } - \tau { \big ) } ] ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } \sin ^ { 2 } \omega { \big ( } t _ { i } - \tau { \big ) } } } \}
$$

其中 $\boldsymbol { \tau }$ 为对应时间 $t$ 的相位修正，计算公式为：

$$
\tan ( 2 \omega \tau ) = { \frac { \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } \sin \left( 2 \omega t _ { i } \right) } { \displaystyle \sum _ { i = 1 } ^ { N _ { 0 } } \cos \left( 2 \omega t _ { i } \right) } }
$$

LSP 方法在对正弦型和数据间隔差距较小的时间序列进行周期分析时有较好的处理效果。为了验证 LSP 方法计算准周期的正确性，我们首先对周期图进行幂率拟合，得到幂率指数 $\beta$ 如图2。然后我们计算了CGRaBSJ0141-0928的置信度，结果如图3所示。图3中，绿色线表示准周期图，其峰值为准周期结果；蓝色、红色、紫色线分别代表蒙特卡罗模拟的 $9 5 \%$ 、 $9 9 \%$ ，99. $7 \%$ 置信度。图3中的绿线有一个明显的峰值为649 天，并且峰的置信度超过了 $9 9 . 7 \%$ ，说明峰值结果是可靠的，所以取649天约为1.78年作为CGRaBSJ0141-0928天体的准周期结果。

![](images/37550f9a50a918e8ccb80b4b24e81656804abed152b1b07c14c474145011acce.jpg)  
图2CGRaBSJ0141-0928天体在射电波段的对数幂率谱  
Fig.2 CGRaBS J0141-0928 object logpower spectrum in radio band

![](images/ee4c46fa18299b0d7c34d84cca3c782492b6d99f1013a0066c21bd252c29f213.jpg)  
图3CGRaBSJ0141-0928天体在射电波段的蒙特卡罗模拟分析结果

Fig.3 CGRaBS J0l41-0928 object Monte Carlo simulation analysis results in radio band

# 2.2加权小波Z变换方法

小波分析（Wavelet Aanlysis）方法是一种新的分析方法，是纯粹数学和应用数学的结合。Morlet小波是高斯包络下的单频复正弦函数，是一种复小波。利用Morlet小波作为小波母函数进行变换，根据复 Morlet 小波[12]：

$$
\psi \mathrm { ( t ) } = e ^ { - t ^ { 2 } / 2 } \big ( e ^ { i w _ { 0 } t } - e ^ { - w _ { 0 } / 2 } \big ) ,
$$

其中 $\omega _ { \textup { 0 } }$ 是衰减因子。

当 $\omega _ { \textup { 0 } }$ 取较大值时，Morlet小波简化为：

$$
\psi ( { \bf t } ) = e ^ { - t ^ { 2 } / 2 } e ^ { i \omega _ { 0 } t } ,
$$

经过伸缩 $a$ 和平移 $b$ 变换， (5)式变为：

$$
\psi \left( { \frac { \mathbf { t - b } } { a } } \right) = e ^ { - { \frac { ( t - b ) ^ { 2 } } { 2 a ^ { 2 } } } } e ^ { i w _ { 0 } \left( { \frac { t - b } { a } } \right) } ,
$$

变形得：

$$
\varphi \mathrm { ( t ) } = e ^ { i w _ { m } \left( t - b \right) - c { w _ { m } } ^ { 2 } \left( t - b \right) ^ { 2 } } .
$$

其中 $\mathrm { W _ { m } { = } W _ { 0 } / a , c { = } 1 / 2 W _ { 0 } } ^ { 2 }$ 业

根据向量投影的方法，可以认为(7)式是一种加权映射，它以 $\mathrm { ~ \boldsymbol ~ { ~ \phi ~ } ~ } ( \mathrm { ~ t ~ } ) \ = \ \mathrm { ~ e ~ } ^ { \mathrm { i ~ } \omega \mathrm { m } ( \mathrm { ~ } \mathrm { t - b } ) }$ 为基函数，wa $= \mathrm { { e } ^ { - c \omega \mathrm { { m } 2 ( \Omega t a - b ) 2 } } }$ 为统计权重因子。另外引入一个常数函数 $\mathrm { \Delta L ( t ) ~ = ~ 1 }$ ，可以得到向量空间的 3个基函数：

$$
\Phi _ { \mathrm { 1 } } ( \mathrm { t } ) \ = \ \mathrm { L ( t ) } ,
$$

$$
\begin{array} { r } { \begin{array} { r } { \Phi _ { 2 } ( \mathrm { t } ) = \cos \big ( \omega _ { \mathrm { { n } } } ( \mathrm {  ~ t ~ } - \mathrm {  ~ b } ) \big ) , } \\ { \Phi _ { 3 } ( \mathrm { t } ) = \sin \big ( \omega _ { \mathrm { { n } } } ( \mathrm {  ~ t ~ } - \mathrm {  ~ b } ) \big ) \ , } \end{array} } \end{array}
$$

将数据向量 $\mathbf { \boldsymbol { x } } \left( \mathrm { t } \right)$ 投影到这3个基函数上，得：

$$
y ( t ) = \sum _ { a = 1 } ^ { 3 } y _ { a } \varphi _ { a } \bigl ( t \bigr ) .
$$

$y _ { a }$ 的计算式为：

$$
y _ { a } = \sum _ { b = 1 } ^ { 3 } S _ { a b } ^ { - 1 } \langle \varphi _ { b } | x \rangle .
$$

其中 $S _ { a b } { = } { < } \varphi _ { \mathrm { a } } | \varphi _ { \mathrm { b } } { > }$

根据上述过程，Foster 定义了加权小波变换(WWT）[13]：

$$
W W T = \frac { \left( N _ { \mathrm { e f f } } - 1 \right) V _ { y } } { 2 V _ { x } } ,
$$

$$
N _ { \mathrm { e f f } } = \frac { \displaystyle \left( \sum \omega _ { \alpha } \right) ^ { 2 } } { \displaystyle \sum \omega _ { \alpha } ^ { \prime } } , V _ { x } = \frac { \displaystyle \sum \omega _ { \alpha } x ^ { 2 } \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } - \left[ \frac { \displaystyle \sum _ { \alpha } \omega _ { \alpha } x \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } \right] ^ { 2 } , V _ { y } = \frac { \displaystyle \sum \omega _ { \alpha } y ^ { 2 } \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } - \left[ \frac { \displaystyle \sum _ { \alpha } \omega _ { \alpha } y \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } \right] ^ { 2 } ,
$$

由于小波形状产生变化，低频部分的有效数据 $\mathrm { N _ { e f f } }$ 会多于高频部分的有效数据，因此WWT的值会偏向高频部分，使得结果出现偏差。于是 Foster 根据Z统计量定义了加权小波Z变换为[14]:

$$
Z = \frac { \big ( N _ { \mathrm { e f f } } - 3 \big ) V _ { y } } { 2 \big ( V _ { x } - V _ { y } \big ) } ,
$$

它满足F分布，自由度为3和2，期望值为1。利用(14)式可以得到如图4的周期性图，在 WWZ 图中，频率轴上的WWZ值表示数据向量的周期性，时间轴上的WWZ值则表示数据向量随时间的波动情况[15]。根据 WWZ 图的极大值可以确定天体光变曲线的周期。图中的蓝色、红色、紫色线分别代表 $9 5 \%$ 、 $9 9 \%$ 、 $9 9 . 7 \%$ 置信度。从图4中可以得到CGRaBSJ0141-0928天体射电波段的光变周期约为636天，并且置信度超过了 $9 9 . 7 \%$ 。

![](images/8952d7bf6e210f983ff5eed344d7dc9c059a8aac6f0062abc33223df7663d128.jpg)  
图4WWZ方法对CGRaBSJ0141-0928在射电波段的分析结果  
Fig.4 WWZ test result for period search in CGRaBS J0141-0928 at radio band

# 2.3 Jurkevich方法

Jurkevich 方法[35由 Jurkevich 提出于1971年，是一种基于期待值的均方差的周期算法，通过测试周期来折叠数据，适用于观测数据不均匀的天体光变周期。假设有 $N$ 个观测的样本数

据，每次的测量值为 $X _ { i } ,$ $\bar { X }$ 为所有样本的平均值， $\boldsymbol { V } ^ { \mathrm { ~ 2 ~ } }$ 为测量数据样本的方差， $S ^ { \mathrm { ~ 2 ~ } }$ 为标准差，则有：

$$
\overline { { \boldsymbol X } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \boldsymbol X _ { i } ,
$$

$$
V ^ { 2 } = \sum _ { i = 1 } ^ { N } X _ { i } ^ { 2 } - N \overline { { { X } } } ^ { 2 } ,
$$

$$
S ^ { 2 } = \frac { V ^ { 2 } } { N - 1 } ,
$$

根据测试周期附近的相位把数据样本划分为 $\boldsymbol { \mathit { m } }$ 组，则第1组的统计参数为：

$$
\overline { { \boldsymbol X } } _ { i } = \frac { 1 } { m _ { i } } \sum _ { i = 1 } ^ { N } \boldsymbol X _ { i } ,
$$

$$
V _ { i } ^ { 2 } = \sum _ { i = 1 } ^ { m _ { i } } X _ { i } ^ { 2 } - m _ { i } \overline { { { X } } } _ { i } ^ { 2 } ,
$$

$$
S _ { i } ^ { 2 } = \frac { V _ { i } ^ { 2 } } { m _ { i } - 1 } ,
$$

对应于 $\boldsymbol { \mathit { m } }$ 组的总方差为：

$$
V _ { m } ^ { 2 } = \sum _ { i = 1 } ^ { m } V _ { i } ^ { 2 } ,
$$

当测试周期接近于真实周期时， $\textit { V } _ { m } ^ { 2 }$ 得到极小值。

此外，Kidger 等人[3]在 Jurkevich 方法的基础上给出了判断周期可靠性的方法，即：

$$
f = \frac { 1 - V _ { m } ^ { 2 } } { V _ { m } ^ { 2 } }
$$

$\textit { V } _ { m } ^ { 2 }$ 是归一化之后的值。通常在 $f \geqslant 0 . 2 5$ 时，表明光变可能具有周期性，当 $\mathrm { \Delta } f \geqslant 0 . 5$ 时，表明有非常显著的周期。

通过Jurkevich方法，对天体PKS0139-097射电波段光变曲线的分析结果如图5。图5中的绿色线以下代表 $f \geqslant 0 . 2 5$ 时的置信度，红色线以下代表 $\mathrm { \Delta } f \geqslant 0 . 5$ 时的置信度。寻找周期时，一般满足以下两个条件的周期比较可靠，一是分析的数据样本时间跨度大于周期的六倍，二是作出的曲线有明显的振幅。从图5中可以看出，对应于 $\textit { V } _ { m } ^ { 2 }$ 的最小值，CGRaBS J0141-0928的射电波段可能存在650天的比较可靠的周期，对应的 $\boldsymbol { f }$ 值为0.37。Jurkevich方法获得的650天周期的结果和LSP方法以及WWZ方法的结果非常接近。650天以后的极小值的周期结果明显不满足以上两个条件，所以不予采纳。

![](images/ae0faa1f5c6e1be558ab312bc0f778bef6bed17a3047e2aa9b9ff82b7d804429.jpg)  
图5Jurkevich方法对CGRaBSJ0141-0928在射电波段的分析结果

Fig.5 The normalized Jurkevich test result for period search in CGRaBS J0141-0928 at radio band

# 3多普勒因子分析

我们从射电的光变曲线中挑选出2个包含上升和下降阶段的爆发过程，分别为MJD 时间56167.4-56410.7 和 $5 6 7 6 2 . 8 \substack { - 5 7 2 2 8 . 5 }$ 。我们使用双指数函数爆发拟合公式[34]来拟合这2个爆发过程。双指数函数公式如下：

$$
F \left( t \right) = F _ { c } + F _ { 0 } \left( e ^ { \frac { t _ { 0 } - t } { t _ { r } } } + e ^ { \frac { t - t _ { 0 } } { t _ { d } } } \right) ^ { - 1 } ,
$$

公式(23)中， $F _ { c }$ 表示基底流量， $t _ { \theta }$ 表示峰对应的时间， $t _ { r }$ 和 $t _ { d }$ 分别表示指数上升和下降的时标， $\mathrm { F } _ { 0 }$ 衡量爆发的幅度。

双指数函数拟合的2个爆发过程如图6所示。每个爆发过程的拟合参数如表1，第1列为约化儒略日的范围；第2列为拟合所得的约化最小残差平方和；第3列为拟合峰值对应的约化儒略日及误差；第4列为基底流量及误差；第5列为爆发的幅度及误差；第6列和第7列分别为指数上升时标和下降时标及误差；第8列为每个爆发过程所对应的多普勒因子。另外，在图6 中的右图中可以看到一个额外的小峰，这很可能是由于相对论喷流中的激波产生的耀斑导致的[43]。

多普勒因子（δ)与喷流中物质流速度和视角有关，但是这两个量都是不可直接观测的量，故用间接方法来估算多普勒因子是有必要的，其中通过射电光变估算多普勒因子 $( \delta _ { R } )$ 相对比较准确[27-29]。假定光变化是内禀的，基于光变时标所限定的源的线度大小，文[30]给出了耀变体亮温度的计算公式：

$$
T _ { \mathrm { b } } = \big ( 4 . 5 \times 1 0 ^ { 1 0 } \big ) \Delta F \Bigg [ \frac { \lambda D } { t _ { o b } \big ( z + 1 \big ) } \Bigg ] ^ { 2 } K
$$

式中， $T _ { b }$ 为亮温度， $\triangle F$ 是以Jy计的流量变化值， $t _ { o b }$ 是以天计的光变时标， $\lambda$ 是以厘米计的观测波长，D 是以百万秒差距 (Mpc)计的光度距离(采用宇宙学参数 $\mathrm { H _ { 0 } \ = 7 2 k m s ^ { - 1 } M p c ^ { - 1 } }$ 和$\Omega _ { \mathrm { m } } { = } 0 . 3 )$ 。

一般认为耀变体的喷流成分对应的亮温度 $T _ { b }$ 不能超过平衡亮温度 ${ T _ { e q } } \mathrm { { = } } 5 \mathrm { { \times } 1 0 ^ { 1 0 } K }$ [31]。我们计算出来的亮温度为 $T _ { b } { = } 2 . 5 7 4 { \times } 1 0 ^ { 1 2 } \mathrm { K }$ 和 $T _ { b } { = } 2 . 9 2 3 { \times } 1 0 ^ { 1 2 } \mathrm { K }$ ，超过平衡亮温度几个量级，表明存在显著的多普勒增亮效应。类似文[28]，我们选择 $T _ { e q }$ 作为内禀亮温度。利用如下公式，进一步估算了射电波段的光变多普勒因子：

$$
\delta _ { R } = \left( \frac { T _ { b } } { T _ { e q } } \right) ^ { 1 / 3 }
$$

由 (25)式得到多普勒因子 $\delta _ { R }$ 的值分别为3.72 和3.88，平均值约为3.8，Fan 等人[32估算出了γ-ray 的多普勒因子 $\delta \mathrm { = } 5 . 5 0$ ，其结果和我们估算的多普勒因子比较接近。

![](images/8361121db22a1f3cc6fdfb7556eb467ea92e5569dec6db311b60a1b65468ec47.jpg)  
图6双指数函数对CGRaBSJ0141-0928的2个爆发（flare）过程的曲线拟合  
Fig.6 Thedouble exponential function fits the curves of the 2 burst processes of CGRaBS JO141-0928 object

表1爆发过程的拟合结及多普勒因子  
Table1 The results of flare fitting and the Doppler factor   

<html><body><table><tr><td> peak</td><td>β</td><td>t。</td><td>F.</td><td>Fo</td><td>t</td><td>td</td><td>8R</td></tr><tr><td>56167.4-</td><td>5.55e-04</td><td>56315.94±20.26</td><td>0.43±0.03</td><td>0.97±0.14</td><td>52.58±21.08</td><td>76.74±27. 60</td><td>3.72</td></tr><tr><td>56410. 7</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>56762.8- 57228. 5</td><td>1.82e-03</td><td>57028.54±12.97</td><td>0.39±0.06</td><td>0.72±0.06</td><td>34.92±7. 61</td><td>94.98±24. 74</td><td>3.88</td></tr></table></body></html>

# 4 相关性分析

离散相关函数分析法(DCF)可以用来分析两组离散的数据的相关性[16-18]。该方法不需要对数据样本做任何的处理就可以判断出两组数据的相关性。DCF方法是由Edelson研究时间延迟时引入的，这种方法可以通过计算时间延迟来研究天体的结构和其他性质[19]。

离散相关函数方法的定义为：如有任意两个离散数据的序列 $\mathrm { a } _ { \mathrm { i } }$ 和 $\mathbf { b } _ { \mathrm { j } }$ ，则离散相关函数的值为

$$
U D C F _ { \mathrm { i j } } = \frac { \big ( a _ { i } - \overline { { a } } \big ) \times \big ( b _ { j } - \overline { { b } } \big ) } { \sigma _ { a } \times \sigma _ { b } } ,
$$

式中，a和 $\overline { { \mathrm { b } } }$ 分别为数据序列 $\mathrm { a } _ { \mathrm { i } }$ 和 $\boldsymbol { \mathrm { b } } _ { \mathrm { j } }$ 的平均值， $\sigma$ a和 $\sigma _ { \mathrm { ~ b ~ } }$ 分别为相应的标准偏差。

每一个数值 $\mathrm { U D C F _ { i j } }$ 与延时 ${ \tau } = \triangle { \tau } = { \tau } _ { \mathrm { j } } - { \ t } _ { \mathrm { i } }$ 有关。而对于有噪的数据，我们可以使用式子(²-e²)²-e²)来代替上式中的σ和σb。对一给定的τ,如果有M个UDCFij满足τ-△τ/2$\leqslant \triangle \mathrm { t } _ { \mathrm { i } \mathrm { j } } < \tau + \triangle \mathrm { ~ \tau / 2 , }$ 然后将这 $\mathtt { M }$ 个数据点求平均值得到:

$$
D C F ( \tau ) = \frac { 1 } { M } \sum U D C F _ { \mathrm { i j } } .
$$

DCF（t)就是离散相关函数，在延时域内对延时进行区间划分，每一区间间隔为△τ，这样我们就可以得到一个非常有用的 $\mathrm { D C F } \left( \tau \right)$ 。如果在某个区间没有数据点，则DCF（τ）不取值。当两个相关序列不相同时，可以得到离散互相关系数。当两个相关序列相同时，则得到离散自相关系数。在离散相关函数的分析图中，如果DCF 的峰值越大，则说明两列数据的相关性越强，反之则越弱。当DCF 的峰值在大于零的一侧时,表示数据a超前于数据b，当DCF 的峰值在小于零的一侧时，则表示数据a滞后于数据b。通过离散相关函数对CGRaBS J0141-0928 射电波段分别和来自Fermi Gamma-ray 空间望远镜 $\gamma$ 波段、来自KAIT Fermi AGNLight-CurveReservoir(http://herculesii.astro.berkeley.edu/kait/agn/)光学R波段的数据进行相关性分析，运用Fortran编写程序计算结果如图7、8，图中的顶部是射电波段和〉波段/光学R波段的流量图，底部是射电波段和 $\gamma$ 波段/光学R波段的相关性结果图，峰值越接近1说明相关性越好。所以从图7中可以看到 $\gamma$ 和射电波段的DCF最大值为0.3，相关性非常弱，这表明它们的辐射区域不同并且辐射过程也是不一致的；图8中显示光学和射电波段的DCF 最大值达到了0.71，光学波段超前于射电波段 $1 6 \sim 1 1 0$ 天，说明它们的辐射过程是一致的。

![](images/9e2a2dd1b0066d499aa4eb578a77b78c1e578e54cb2eb9adeb95a69b8ab5b377.jpg)  
图7DCF方法对CGRaBSJ0141-0928 在射电和 $\gamma$ 波段的相关性分析。顶图中红色和黑色分别表示Gamma-ray 和射电波段的光变曲线，左边标注表示射电波段的单位，右边标注表示Gamma-ray 波段的单位。底图表示Gamma-ray 和射电波段之间的相关性结果即 DCF 值。Fig.7 Correlation analysis of CGRaBS J0141-0928 in radio and $\gamma$ bands by DCF method

![](images/6b908a224c9aaa48b73da38d9c4d7865150c90c0a2f2627d180abc56a61569a6.jpg)  
图8 DCF 方法对CGRaBS J0141-0928 在射电和光学R波段的相关性分析。顶图中蓝色和黑色分别表示Optical 和射电波段的光变曲线，左边标注表示射电波段的单位，右边标注表示Optical 波段的单位。底部表示Optical 和射电波段之间的相关性结果即 DCF 值。Fig.8 Correlation analysis of CGRaBS J0141-0928 in radio and optical R bands by DCF method

# 5讨论与结论

通过收集 BL Lac 天体 CGRaBSJ0141-0928 的光变数据，运用Lomb-Scargleperiodogram 方法，加权小波 Z变换法以及 Jurkevich 方法对其射电波段的光变曲线的周期进行分析，分析的结果相互印证。Lomb-Scargle periodogram 方法分析射电波段得到的周期约为649 天，加权小波Z变换法分析射电波段得到的周期大致为636天，Jurkevich 方法得到的周期大致为 650 天。加权小波Z 变换法和 Jurkevich 方法的计算结果进一步支持了CGRaBS J0141-0928天体的射电波段有一个可靠的约为649 天左右的光变周期。利用双指数函数我们拟合了其中2 个爆发的过程，估算了多普勒因子 $\delta _ { \scriptscriptstyle R } = 3 . 8$ 。结果表明 CGRaBS J0141-0928 天体射电波段的辐射存在显著的聚束效应，支持了相对论性喷流模型。通过离散相关分析法对射电波段和Gamma-ray、射电波段和光学R波段分别进行相关性分析，结果显示Gamma-ray 和射电波段之间存在弱的相关性，光学R波段和射电波段之间存在比较强的相关性，并且光学R波段超前于射电波段 $1 6 ^ { \sim } 1 1 0$ 天。对于类星体长周期光变的物理模型现在仍然不是很清楚，为了解决这些问题提出了一些物理模型。常见的物理模型有双黑洞模型[20-21]、螺旋喷流模型[22-25]和薄盘的热不稳定性等。

CGRaBS J0141-09287 天体产生的准周期可能是由喷流的螺旋运动[]产生的。喷流的螺旋进动由超大质量黑洞（SMBBH）系统的轨道运动驱动。Rieger 给出了实际物理驱动周期 $P _ { d }$ 和观测准周期 $P$ 之间的关系公式为：

$$
P _ { \mathrm { \it d } } ~ \approx ~ \frac { \gamma _ { b } ^ { 2 } } { 1 ~ + ~ z } ~ P
$$

其中 $\gamma _ { b }$ 是体洛伦兹因子，约等于 $7 . 5 ^ { [ 3 8 ] }$ ， $z$ 是红移。我们使用649 天的准周期得到实际物理驱动周期 $P _ { d } { \approx } 5 7 . 7 1 \mathrm { y r }$ 。另外，如果使用 $\gamma _ { b } = 1 5$ 作为参数[39]，可以得到 $\mathrm { \mathit { P } _ { \mathit { d } } } { \approx } 2 3 0 . 8 5 \mathrm { y r }$ 。主黑洞和次黑洞之间的质量比为 $R \leqslant 1 / 3$ 时，称为“Majormerger”（主合并）。若质量比为 $3 \leqslant R \leqslant$

${ 1 0 } ^ { 4 }$ ，则称之为“Minor merger”（次合并）[40]。无论质量比为多少，主黑洞的质量都可以用以下公式估计[41]：

$$
M \approx P _ { d } ^ { \frac { 8 } { 5 } } R ^ { \frac { 3 } { 5 } } 1 0 ^ { 6 } \mathrm { M } _ { \odot }
$$

其中 $P _ { d }$ 以年为单位，对于SMBBH系统的主并合，质量比可以假设为 $R = 3 / 2$ 。将参数代入(29)式中，得到 PKS 0139-097 的主黑洞质量大约为 $M \approx 1 0 ^ { 8 . 9 3 } \mathrm { { M } \odot }$ 。如果使用 $\gamma _ { b } = 1 5$ 作为参数[42]，次并合的 SMBBH系统的主黑洞质量为 $\mathcal { M } \approx 1 0 ^ { 9 . 8 9 } \mathrm { \ : M odot }$ 。 $\mathtt { W u }$ 等人[2给出了CGRaBS J0141-0928 天体的黑洞质量为 $M \approx 1 0 ^ { 9 . 6 3 \pm 0 . 7 0 } \mathrm { M } _ { \odot }$ ，其结果和我们估算的主黑洞质量一致。

# 参考文献：

[1]AngelJRPStockmanHS.Opticaland InfraredPolarizationof ActiveExtragalacticObjects[J].AnnualReviewof Astroom& Astrophysics,1980,18.   
[2]UryCMegan,adovaniPaolo.UnifidShemesforRadio-LoudActiveGalacticuclei[J].PublicatiosoftheAstronomicalociety of the Pacific,1995,107 (715): 803-845.   
[3] Zhang Xiong,Yang Weiguo,Hou Dedong,et al.The variations characteristics and black hole mass of $\mathrm { H } 0 3 2 3 + 0 2 2$ objects research [D].,2005.   
[4] XieGZ,BaiJM,ZhangX,eta.The massiveblackholeinthecenteroftheactivegalaxyMRK421[J].AstronomyandAstrohsics, 1998,334: L29-L31.   
[5]PursimoT,NilssonK,TakaloLO,etal.DeepopticalimagingofradioselectedBLLacertaeojects[J].Astronomy&strohsics, 2002,381(3):810-824.   
[6] Zhang Haojing,Zang Xiong,DongFutong,etal.Usingawaveletanalysis methodtocalculatetheVariationsperiodofBLLacobject S50716+714.Astronomy,2009,50 (2): 141-151.   
[7]EdelsonRA,KrolikJH.Thediscretecorrelationfunction-Anewmethodforanalyzingunevenlysampledariabilitydata[J].Te Astrophysical Journal,1988,333: 646-659.   
[8]Heidt J, Wagner SJ.Intradayvariability in x-rayselectedBLLacertae objects.Astronomy&Astrophysics,1997.   
[9]SeperuelouarteE,AlencarSHP,BatalaCetal.SpectrophotometricanalysisoftheTTauristarGQLupiA[J].Astrooad Astrophysics,2008,489(1):349-357.   
[10]RejkubaM,MinitiD,SilvaDR.Long periodvariablesinNGC5128-I.Catalogue[J].AstronomyandAstrophysics,003, 406(1).   
[11] Yang X, Yi TF,et al. The $\boldsymbol { \gamma }$ Rayand Optical Variability Analysis of the BLLac Object 3FGL J0449.4-4350[J].Publications of the Astronomical Society of the Pacific,2020,132(1010): 044101.   
[12]徐斌，杨涛，谭保华,等．基于 Lomb-Scargle 算法的周期信号探测的模拟研究[J].核电子学与探测技术，2011(06)111-114. XuB,YangT,TanBH,etal.The Simulate StudyofSignalDetectionBasedonLomb-ScargleAlgorithm.NuclearElectronics & Detection Technology,2011(06):111-114.   
[13]FOSTER G.Wavelets for period analysis of unevenly sampled time series[J]．AJ，1996，（112):1709－1729.   
[14]FOSTERG..Time Series Analysis byProjection．I．StatisticalPropertiesofFourier Analysis[J]．AJ，1996，（111):541一 554.   
[15]Xu Yunbing，ZhangRongjing，Zhang Xiong.The variationsperiodofBLLacobjectisanalyzed with weighted wavelet transformation [J].Journal of Yunnan Normal University: Natural Science,2O13,33 (5): 9-17.   
[16]GaoWei,YangJinxue,LiWaizhen.BLLacobjectPKS155-304variationsPropertiesAnalysis[J].JourmalofYuanNoal University: Natural Science Edition,2015,35 (1): 1-4.   
[17]EdelsonRA,KrolikJHhediscretecoreationfunction-Anewmehodforanalyingunevenlysampledvariabilityata[J]. Astrophysical Journal,1988,333(134):646-659.   
[18]HufnagelBR,BregmanJN.Opticalandradiovariabilityinblazars[J].AstrophysicalJoural,992,386(2):47-484.   
[19] lvisM,W ikes B J,McDowel,JC, et al.A tlas of quasar energy distributions[J].APJ.1994,95.   
[20]ValtaojaE,TeräsrantaH,TokoskiM,etal.RadioMoitoringofO87andBinaryBlackHole ModelsforPeriodicOutbursts[J]. Astrophysical Journal,2008,531(2):744.   
[21]XieGZ,LangEW,ZouS,etal.Potometryof trgmma-rayoudasarsndipicaiosforupeasivebacoles[]. Monthly Notices of the Royal Astronomical Society,2010,334(2):459-470.   
[22]Rani B,Wita PJ, Gupta A C. NEARLY PERIODIC FLUCTUATIONS IN THE LONG-TERM X-RAYLIGHT CURVES OF THE BLAZARS AO $0 2 3 5 \substack { + 1 6 4 }$ AND 1ES 2321+419[J].Astrophysical Journal,2009,696(2):2170-2178.   
[23]Lainela M,TakaloLOSilanpaa A,etal.The65DayPeriodin3C66duringBrightState[J].AstrophysicalJoual999, 521(521):561.   
[24]VillataM,RaiteriCM.Helicaljetsinblazars.IThecaseofMK50l[J].Astronomy&Astrophysics,99,347(1):3-6.   
[25]LiHZ,XieGZ,ChenLE,etal.ThePeriodicityAnalysisoftheLightCurveof3C279andImplicationsfortePrecessioJet[J]. Publications of the Astronomical Society of the Pacific,2009,121(885):1172-1179.   
[26] Wu Z Z,GuMF,Jiang DR.The debeamed luminosity，sychrotron peak frequencyand black hole massof BLLacobjects[J]. Research in Astronomy and Astrophysics,2009,9(2): 168.   
[27]Valtaoja,EtekiAsrantHtaotalFesityatiosiEtrgalactidiooues.oof Variations into Exponential Flares[J].ApJS,1999,120,95.   
[28]LahteenmakiA.,，ValtaojaE.，WikK,tal.TotalFux DensityVariations inExtragalacticRadioSources.IDeteiningthe Limiting Brightness Temperature for Synchrotron Sources[J]. ApJ,1999,511,112.   
[29]LiodakisI,archiliN,AngelaisE.,etal.F-GAM:vrabilitoplerfctorsofblazarsfrommultiwavelengthmotog[]. MNRAS,2017,466, 4625.   
[30] Wagner S.J., Witzel A.Intraday Variability In Quasars andBLLac Objects[J]. ARA&A,1995,33,163.   
[31]Readhead,AnthonyC.S.EqupartitionbghtesstmperatureandtheiverseComptocatastrophe[J].ApJ,994,426,51.   
[32]FanJH,YangJH,iu,etalegam-raoprfctordeteatiosforFeiblazarsaple[J].Researchitoy and Astrophysics,2013,13(3): 25. [33] Wagner S.J,A Witzel. Intraday variability in the BLLac object $\phantom { 0 } { 0 9 5 4 } + 6 5 8 [ \mathrm { J }$ l. astronomy& astrophysics,1993,271(1):344.   
[34] Ackermann M,Ajello M,Baldini L,et al.FERMI GAMMA-RAY SPACE TELESCOPE OBSERVATIONS OF GAMMA-RAY OUTBURSTSFROM3C454.3IN2009 DECEMBERAND2010APRIL[J].The AstrophysicalJourmal,2010,721(2):1383-1396.   
[35]JurkevichI. Amethodofcomputing periods ofcyclicphenomena[J]Astrophysicsand Space Sciene,1971,13(1):154-167.   
[36]KidgeraloL.Aasisof-arpdin7oaooftseistce[J]trd Astrophysics,1992,264:32361.   
[37]NemmenRS,GeorganopoulosM,GuiriecS,etal.AUniversal ScalingfortheEnergeticsofRelativisticJetsfromBlackHole Systems[J].Science,2012,38(6113):1445-1448.   
[38] Henri,G.,& Sauge,L.The bulk Lorentz factor crisisof TeVblazar $\because$ evidence for an inhomogeneous pileup energy distribution ?[J]. The Astrophysical Journal,2006,640(1):185.   
[39]GuinevereK,MartinH.Auifid modelfortheevolutionofgalaxiesandquasars[J].MonthlyNoticesoftheRoyalAstrooical Society. 2000,311(3):576-588.   
[40]BegelmanMC,BladfordRD,ReesMJ.MassiveblackholebiariesinactivegalacticnucleiJ].Nature,98o27(78):30

309.

[41]William,H,Lee,etalResoanceinForcedOscilltionsofanAretionDiskandKiloertQuasi-priodicOscilatios[J] Astrophysical Journal Letters,2004. 603:L93-L96.   
[42]Kauffmann,G.,&Haelnelt,M.Aunifiedmodelfor theevolutionof galaxiesandquasars[J].2Ooo,MNRA,31,576.   
[43]MarscherAP,GearWK.Modelsforhigh-frequencyadiooutburstsinextragalacticsources,withapplicationtothearly983 millmeter-to-infrared flare of 3C 273[J].Astrophysical Journal,1985,298:114-127.

# Analysis of optical property of BL Lac object CGRaBS J0141-0928

Xin Chang'²， Tingfeng Yi1²， Xing Yang²， Yunlu Gong'， Jiajian Zhang' Lisheng Mao' (1Schoolofphysicsandelectronicinformation，YunnanNormalUniversity，Kunming 65o5o0，China;2GuangxiKeyLaboratoryfor RelativiticAstrois,go;inaoloficalcedgioagiUiveit 530004,China; 4 School of Physics and Astronomy, Yunnan University,Kunming 65o5oo，China

Abstract: Observation data from the Owens Valley Radio Observatory (OVRO） 40-meter telescope showed multiple dramatic light variations in the $1 5 \ : \mathrm { G H z }$ radio band of the blazar CGRaBS J0141-0928. LSP (Lomb-Scargle-periodogram） method， WWZ method (Weighted Wavelet Ztransform,WWZ) and Jurkevich method are used to analyze the light variable period of CGRaBS J0141-0928. The results show that the object has a light variable period of about 649 days ( $_ { ( 4 . 4 \sigma }$ significance level),and its quasi-periodic oscillation(QPO) may be caused by the helical motion of the jet.The brightness temperature,time scale of light variability and Doppler factor were estimated by fitting the processes of two bursts with double exponential function.The Doppler factor estimated by the optical time scale of variability is 3.48,and the results show that CGRaBS J0141-0928 has a significant beaming effect in the radio radiation band. The DCF (Discrete Correlation Function) method is used to analyze the correlation between the radio band and Gamma-ray and optical R band. It is found that there is a strong correlation between optical light variability and radio light variability, and the optical light variability is $6 6 \pm 4 0$ days ahead of the radio variability.

Key words: CGRaBS JO141-O928;LSP method; weighted wavelet $Z$ transformation method; DCF method; Jurkevich method; Doppler factor