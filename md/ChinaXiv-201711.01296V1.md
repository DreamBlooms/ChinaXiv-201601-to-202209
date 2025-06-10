# Chirp信号在天文观测中的应用

范江涛，马冠一，万庆涛，张杰（中国科学院国家天文台，北京100012)

摘要：Chirp信号是一种频率随时间有规律连续变化的信号，由于其优良的自相关特性，在实时宽带高精度频谱测量中有重要应用。通过对Chirp信号的分析，介绍了基于线性Chirp 信号的脉冲压缩技术及Chirp 变换频谱仪的原理，综述了近30年来Chirp 变换频谱仪在行星和彗星大气红外谱测量中的应用及其发展历程。结合当前电子技术的发展，指出了改善Chirp变换频谱仪性能的研究方向。

关键词：Chirp 信号；脉冲压缩；Chirp 变换频谱仪；行星大气探测；声表面波滤波器中图分类号：P111.4；P407.6 文献标识码：A 文章编号：1672-7673(2017)04-0443-09

Chirp 信号是一种频率随时间有规律连续变化的信号，它占用一段连续的频谱，相比于单频信号，具有更好的自相关性。早在20 世纪50年代，贝尔实验室在改进雷达技术中利用Chirp信号优良的自相关特性实现脉冲压缩技术，提高了测距精度和接收信号的信噪比，从而提高了雷达分辨率和灵敏度，降低了发射功率[1-3]。从此，Chirp信号作为无线电应用中提高测量精度和信噪比的一种关键技术，在雷达、导航定位、空间探测、频谱测量和扩频通信等领域得到了广泛的应用[4]。

在天文研究中，原子、分子和离子的辐射和吸收谱线特性中包含物质成分及其所处的环境信息，频谱测量成为一种重要的观测研究手段。行星大气的辐射和吸收频谱为红外波段，红外波段也称为太赫兹波段，高于常规电子设备的微波射频波段，低于光学设备的可见光波段，受器件性能的局限，行星大气的红外谱测量设备难以同时满足宽带和高精度频谱的实时测量，限制了行星大气科学的红外谱观测研究。根据光谱形态学的原理和大气模型，通过测量行星大气的辐射或吸收谱线的精确形状，可获得行星大气的成分、比例、密度、温度和压力等参数信息[5-7]。对红外谱线观测，通常采用外差接收的方法，将红外波段光谱信号通过红外前端设备变频到满足带宽要求的中频波段，使用高性能的后端处理设备获取宽带和高精度的谱形状，为实现此测量要求，曾研发了一些红外谱后端处理频谱仪，如自相关频谱仪（Autocorrelation Spectrometer）、声光频谱仪（Acousto Optical）、滤波器组频谱仪（FilterBank）、快速傅里叶变换频谱仪等。但这些设备无法同时兼顾高精度和宽带实时测量的要求，或者存在工作不稳定和难以校准的缺点[5]。

20 世纪60年代，文[1]从理论上提出了基于Chirp 信号的脉冲压缩可用于实现傅里叶变换的数学原理，其将频谱测量转换为信号与Chirp信号的相乘和卷积运算。文[3，5]使用电子器件实现了这一频谱测量设备，称之为 Chirp 变换频谱仪（Chirp Transform Spectrometer，CTS）。20 世纪80年代，得益于声表面波滤波器(Surface Acoustic Wave，SAW）在信号处理中的应用，利用声表面波滤波器件实现了宽带线性Chirp信号生成与卷积运算。德国马普天文台运用声表面波滤波器件和Chirp信号测量频谱的原理，解决了传统的大气红外谱实时观测设备无法同时满足带宽和频谱精度要求的问题，首次研制成功了用于地球大气、行星大气和彗星大气的Chirp变换频谱仪。其接收采用超外差的方式，观测频率为几十GHz至几THz，带宽为几百MHz，重量、体积、功耗和稳定性等参数优良，特别适合安装在空间飞行器上使用。随后Chirp 变换频谱仪的性能不断提升，已成功应用于毫米波大气探测（Millimeter wave Atmospheric Sounder，MAS），Rosetta 探测器微波遥感设备（Microwave Instrument forRoseta Orbiter，MIRO），德国太赫兹大气探测接收机（German REceiver for Astronomy at Terahertzfrequency，GREAT)等项目［5-9]。

Chirp 变换频谱仪采用声表面波滤波器实现了宽带Chirp信号的生成和卷积运算，相比于其他的红外后端频谱测量设备，具有结构简单、测量带宽宽、测量精度高、功耗小和可靠性高等优点[5,10]但是声表面波滤波器件在插入损耗、色散效应、带宽和频率灵活性方面的问题，限制了基于声表面波滤波器件的Chirp 变换频谱仪性能的进一步提高[5]。随着数字电子技术的发展，马普天文台利用直接频率合成（Direct Digital Synthesis，DDS)芯片生成线性 Chirp 信号，改善了Chirp 变换频谱仪的性能。使用直接频率合成芯片可以生成与器件失真后相匹配的预失真线性Chirp信号，校正模拟电路部分的色散效应，并且直接频率合成芯片可灵活地改变Chirp信号的带宽和频点。基于高性能的直接频率合成芯片可以生成带宽为1GHz 的线性Chirp 信号，从而实现 $2 1 5 \mathrm { M H z }$ 带宽的实时频谱测量[6.9,11]。还有研究人员使用矢量信号发生器生成了一种 $1 ~ \mathrm { G H z }$ 带宽的线性Chirp 信号，用于高精度的分子光谱测量[12]。

在我国Chirp 变换频谱仪早期也被称为“声表面波频谱仪”，“声表面波线性调频变换功率谱仪”[13-18]。中国科学院声学研究所曾为马普天文台的 Chirp 变换频谱仪研制了 Chirp 信号带宽为 400MHz、 $6 0 0 \mathrm { M H z }$ 、 ${ 8 0 0 } \mathrm { M H z }$ 的专用表面波滤波器件[19-20]。20 世纪90 年代我国探讨了Chirp 变换频谱仪在射电天文中观测分子谱线的可行性，论证了在云南天文台和紫金山天文台毫米波射电望远镜后端信号处理中应用 Chirp 变换频谱仪[13-14]。Chirp 变换频谱仪也应用于我国乌鲁木齐 $2 5 \mathrm { ~ m ~ }$ 射电望远镜开展水脉泽观测研究[21-22]。

本文综述基于Chirp 信号和脉冲压缩技术的 Chirp 变换频谱仪，首先介绍 Chirp 信号和基于 Chirp信号的脉冲压缩技术，给出基于Chirp信号和脉冲压缩技术实现频谱测量的数学原理，进而描述了Chirp 变换频谱仪的原理，然后介绍了Chirp变换频谱仪基于声表面波滤波器实现的方法，Chirp 变换频谱仪在行星大气和彗星红外谱测量中的具体应用，以及Chirp 变换频谱仪的发展历程和改进方向。

# 1Chirp信号与脉冲压缩

# 1.1 Chirp信号介绍

Chirp 信号的特征是频率随时间连续变化。频率随时间线性增加或减小的信号称为线性Chirp 信号，频率随时间指数变化的信号称为指数Chirp信号 $\textcircled{1}$ 。Chirp信号在大自然中广泛存在，如多普勒效应、引力波以及其英文本意所指的鸟鸣等。

线性Chirp 信号在天文观测的电子设备中较常使用，其频率随时间线性变化，频率表达式为

$$
f ( t ) = f _ { \mathrm { 0 } } + k t ,
$$

其中， $k = \frac { f _ { 1 } - f _ { 0 } } { T }$ ；f为初始频率；fi为最终频率；T为频率变化周期。信号的相位为频率的积分，相应的表达式为

$$
\phi ( t ) = \phi _ { \mathrm { 0 } } + 2 \pi \left( f _ { \mathrm { 0 } } t + \frac { k } { 2 } t ^ { 2 } \right) ,
$$

相位 $\phi ( t )$ 是时间 $\mathbf { \chi } _ { t }$ 的二次函数，线性Chirp 也常称为二项式相位信号。

在一个频率变化周期内，线性Chirp 信号的时域表达式为

$$
s ( t ) = \exp \Biggl \{ - \mathrm {  ~ j ~ } \Biggl [ \phi _ { \mathrm { 0 } } + 2 \pi \Biggl ( f _ { \mathrm { 0 } } t + \frac { k } { 2 } t ^ { 2 } \Biggr ) \Biggr ] \Biggr \} \ ,
$$

信号的时域波形和频率随时间变化的波形如图1。从图1可以看出，线性Chirp信号随时间呈周期递减的震荡变化，波形随时间逐渐变密，频率由低到高呈线性增加，周期性扫频。因此，线性Chirp 信号也常作为电子设备的扫频信号。

![](images/4889ce237022d32bf8e9107deaaa7263384bd8cca9ff8056ba43c91d1f783fef.jpg)  
图1线性Chirp信号及其频率随时间的变化 Fig.1A linear Chirp signal and it's spectrogram

指数Chirp信号的频率与时间的关系可以表示为

$$
\begin{array} { r } { f ( t ) = f _ { 0 } \boldsymbol { k } ^ { t } , } \end{array}
$$

其中， $f _ { 0 }$ 为初始频率； $k$ 为决定频率呈指数变化率的底数。指数Chirp 信号的相位为

$$
\phi ( t ) = \phi _ { \mathrm { 0 } } + 2 \pi f _ { \mathrm { 0 } } \biggl ( { \frac { k ^ { t } - 1 } { \ln k } } \biggr ) \ .
$$

在一个频率变化周期内，指数Chirp信号的时域表达式为

$$
s ( t ) = \exp \Bigg \{ - \mathrm { ~ j ~ } \Bigg [ \phi _ { \mathrm { 0 } } + 2 \pi f _ { \mathrm { 0 } } \bigg ( \frac { k ^ { \prime } - 1 } { \ln k } \bigg ) \Bigg ] \Bigg \} .
$$

图2给出了指数Chirp信号的时域波形和频率随时间变化的曲线。从图2可以看出，指数 Chirp信号的频率由低到高呈指数增加，且周期性重复，频率变化速度比线性Chirp 更快。

![](images/c712f9a23e321bf2b02588b0f98d8ab1907d5bb58e982a6c39fbc0920dc338cf.jpg)  
图2指数Chirp 信号及其频率随时间变化  
Fig.2An exponential Chirp signal and it's spectrogram

# 1.2基于Chirp 信号的脉冲压缩

脉冲压缩的原理是在信号处理中将一个特征信号调制到发射信号上，在接收端用相同的特征信号做相关以检测发射信号，调制特征信号增加了信号的自相关性，使信号更易于被检测和测量。脉冲压缩常应用于雷达、声呐和回波检测中，用于增加测距精度和提高检测信噪比[4]。

例如在雷达中检测矩形脉冲信号的回波，如果脉冲宽度为 $T$ ，则相关函数是宽度为2T的三角函数，如图3。如果两个回波的间隔小于 $T$ ，则两个相关函数将混叠在一起无法区分。

若采用脉冲压缩技术，在发射信号上调制一个带宽为 $ { \Delta } f$ 的线性Chirp信号，在接收端用相同的

Chirp信号做检测。Chirp信号的自相关函数可表示为

$$
\left. S _ { c } , \ S _ { c } \right. \left( t \right) = T \Lambda \left( \frac { t } { T } \right) \mathrm { s i n c } \Bigg [ \pi \Delta f t \Lambda \Bigg ( \frac { t } { T } \Bigg ) \Bigg ] e ^ { \mathrm { j } 2 \pi f _ { 0 } t } ,
$$

它是一个 sinc 函数，主瓣宽度为 ，△为Chirp信号的频率变化范围，通常 <T。与图3对应的信号检测结果如图4。

![](images/7d3194f938c39a9481973b642f68d07b9c9400926435acfa091aa402feea152c.jpg)  
图3基于矩形脉冲的回波检测 Fig.3Echo detection using rectangular pulse signal

![](images/6f12b48c601c98a92082cd6bc9baafa3b217afedac81c1601114da81920a5eae.jpg)  
图4基于Chirp信号的脉冲压缩的回波检测 Fig.4Echo detection by pulse compression using Chirp signal

相比矩形脉冲信号的回波检测，图4中使用Chirp信号脉冲压缩技术的自相关检测信号的信噪比和分辨率更高。脉冲的宽带与Chirp 信号的频率范围成反比关系，即单位时间内Chirp 信号频率范围越宽，相关峰越尖锐，测量精度越高。

# 2Chirp 变换频谱仪

# 2.1基于Chirp 信号实现频谱测量原理

使用Chirp 信号测量频谱的原理可以由傅里叶变换导出。傅里叶变换可表示为

$$
F ( \omega ) = \int _ { - \infty } ^ { + \infty } s ( t ) e ^ { - \mathrm { j } \omega t } \mathrm { d } t , \omega = 2 \pi f ,
$$

其中， $s ( t )$ 为时域信号; $f$ 为信号频率； $\omega$ 为信号角频率。采用线性Chirp 信号，假设 ${ \scriptstyle f = \mu \tau }$ ， $\mu$ 为频率随时间的变化率； $\tau$ 为频率变化的时间，则傅里叶变换可表示为

$$
F \left( \omega \right) = \int _ { - \infty } ^ { + \infty } s \left( t \right) e ^ { - \mathrm { j } 2 \pi \mu \tau t } \mathrm { d } t \ ,
$$

其中， $2 \tau t$ 可以分解为

$$
2 \tau t = t ^ { 2 } + \tau ^ { 2 } - ( t - \tau ) ^ { 2 } ,
$$

将(10)式代入(9)式，傅里叶变换可以表示为

$$
F ( \omega ) = e ^ { - \mathrm { j } \pi \mu \tau ^ { 2 } } { \int } _ { - \infty } ^ { + \infty } s \left( t \right) e ^ { - \mathrm { j } \pi \mu t ^ { 2 } } e ^ { \mathrm { j } \pi \mu \left( t - \tau \right) ^ { 2 } } \mathrm { d } t \ .
$$

假设 $h ( \ t ) = e ^ { \mathrm { j } \pi \mu t ^ { 2 } }$ ，则(11)式可以表示为

$$
\begin{array} { r } { F ( \omega ) = e ^ { - \mathrm { j } \pi \mu \tau ^ { 2 } } \cdot \left[ \left( s ( t ) \cdot e ^ { - \mathrm { j } \pi \mu t ^ { 2 } } \right) \ast h ( t ) \right] . } \end{array}
$$

即除去相位差 $e ^ { - \mathrm { j } \pi \mu \tau ^ { 2 } }$ ，傅里叶变换可表示为信号 $s ( t )$ 乘以线性 Chirp 信号 $ e ^ { - \mathrm { j } \pi \mu t ^ { 2 } }$ ，再与具有相反频率变化率的线性 Chirp 信号 $ e ^ { \mathrm { j } \pi \mu t ^ { 2 } }$ 做卷积。

使用上述原理，应用线性Chirp 信号的相乘和卷积运算可以实现傅里叶变换，计算信号的频谱。

# 2.2Chirp 变换频谱仪的原理

基于线性 Chirp 信号的脉冲压缩实现频谱测量设备原理如图 5[5-7]

![](images/ff8418ac15e45c1d0305ac33e33f65c1087edd82667f8ec5bbfe34dc38b80c92.jpg)  
图5Chirp 变换频谱仪的原理Fig.5The principle of CTS

图5中输入信号为红外光谱信号下变频后的中频信号，带宽为 $f _ { 2 } - f _ { 1 }$ 。根据Chirp 信号实现傅里叶变换的原理，将生成的线性Chirp 信号 $C _ { 1 } ( t )$ 调制到该中频信号上，将Chirp 调制后的信号与一个频率变化率相反的Chirp信号 $C _ { 2 } ( t )$ 做卷积，以实现基于Chirp 信号的脉冲压缩检测。在这个过程中，中频信号的频率改变了Chirp信号的相关峰出现的时间偏差，相应的相关峰时延对应被测中频信号的频率。对于一个线性系统，信号可分解为各频率分量的线性相加，测量时延信号形状，即可实时测量出对应的红外谱形状。Chirp 变换频谱仪将信号频率的测量转换为时延信号的测量。

根据图5的原理，一种Chirp 变换频谱仪的实现框图如图 $6 ^ { [ 9 ] }$ 。图6中Chirp 信号发生器产生线性Chirp信号，经过倍频、滤波和放大后，经过混频器与被测中频信号调制，得到有频率偏移的Chirp信号。通过声表面波滤波器实现Chirp 信号的卷积运算，输出带时间偏差的线性Chirp信号相关峰信号，通过数据采集存储和信号分析，测量相关峰信号的时延，从而计算出对应的被测信号频谱。

# 2.3Chirp 变换频谱仪的应用

从20世纪80年代首次研制并应用开始，Chirp变换频谱仪已装备于地基、机载和星载观测设备中，对地球大气、行星大气、彗星和星际介质分子开展了红外谱线测量。

![](images/8939ef96ba4a45126d542ab0486e49a3aa16a7eeec7f6d01ef167a35a71a418c.jpg)  
图6Chirp变换频谱仪的实现框图Fig.6A block diagram of CTS

Chirp 变换频谱仪最早应用于地基大气探测，测量地球中层大气中臭氧、水蒸气和二氧化碳等分子辐射谱线，得到其分子密度大气剖面，研究在大气中的运动和传输。在挪威的Arctic Lidar 中层大气观测台（Arctic Lidar Observatory for Middle Atmosphere Research，ALOMAR)使用 Chirp 变换频谱仪对地球中层大气中水蒸气分子光谱观测已进行了一个太阳周的常规观测( $1 9 9 6 \sim 2 0 0 6 ^ { \cdot }$ )，研究了地球中层大气的季节变化以及与太阳活动的相关性，并为完善地球大气模型和大气辐射谱形状理论积累了数据[23-24]同温层红外天文台（Stratospheric Observatory For Infrared Astronomy，SOFIA）使用 $2 . 5 \mathrm { m }$ 红外反射式望远镜，搭载多个波段的红外观测设备，用于研究行星表面和大气组成、彗星组成、演化和结构、星际物质的特征和化学性质以及恒星和其他天体的组成。同温层红外天文台使用一架波音747SP 飞机,运行于 $1 5 \mathrm { k m }$ 高空，可以避开地球大气的水蒸气对红外谱的吸收干扰，具有更高的灵敏度，能探测更多的分子谱线，且可以对观测天体开展连续观测。同温层红外天文台上运行的德国太赫兹大气探测接收机基于Chirp 变换频谱仪实现，用于对 $1 . 6 { \sim } 1 . 9 \mathrm { T H z }$ 、 $2 . 6 \mathrm { T H z }$ 和 $4 . 7 \mathrm { T H z } 3 \$ 个频段的碳离子、氘氢分子和氧原子等谱线观测。应用于同温层红外天文台的Chirp 变换频谱仪对Chirp 信号发生器部分做改进，使用直接频率合成数字芯片生成预失真的宽带线性Chirp 信号，用于修正模拟电路部分的色散效应，提高了测量性能[8-9]。

欧洲空间局的Rosetta 彗星探测器是首次成功实现环绕彗星并登陆彗星的深空探测器，用于探索彗星结构、太阳系形成和早期信息以及地球上水的来源与彗星的关联。Rosetta于2004 年3月发射，2014 年8月进人67P/Churyumov-Gerasimenko 彗星轨道，2016 年9月结束探测任务。Rosetta 搭载的MIRO 观测设备基于Chirp变换频谱仪实现，用于测量慧尾和彗星蒸发气体中水、氨气和二氧化碳等气体分子辐射的红外谱线形状，从而得到其成分、密度、风速、温度、气压等信息。MIRO也是首个用于深空探测的亚毫米波外差测量设备[25]。

我国在射电天文观测中应用Chirp变换频谱仪开展了射电天文星际分子谱线观测研究。乌鲁木齐$2 5 \mathrm { ~ m ~ }$ 射电望远镜基于Chirp 变换频谱仪的分子谱线观测系统对水脉泽的观测已发现十几个可能的水脉泽源[21-22]。Chirp 变换频谱仪也应用在紫金山天文台青海站 $1 3 . 7 \mathrm { ~ m ~ }$ 射电天文望远镜的毫米波测量系统中，对 $2 2 \ : \mathrm { G H z }$ 水分子脉泽源开展观测，其中心频率为 $5 2 9 \mathrm { M H z }$ ，实时带宽为 $3 9 . 9 \mathrm { M H z }$ ，分辨率 $\leqslant$ 40 kHz[15]

# 2.4Chirp变换频谱仪的发展趋势

Chirp 变换频谱仪从20世纪80年代初开始研制，到80年代中期实际应用，根据不同的项目应用需求，在 $1 9 8 3 \sim 2 0 0 4$ 实现的Chirp 变换频谱仪的参数指标如表 $1 ^ { [ 5 - 7 ] }$ 。

表1Chirp 变换频谱仪的典型指标  
Table 1 Specification of CTS   

<html><body><table><tr><td>参数</td><td>1983</td><td>1984</td><td>1985</td><td>1987</td><td>1991</td><td>1992</td><td>1996</td><td>2004</td></tr><tr><td>中频频率/MHz</td><td>180</td><td>300</td><td>1 350</td><td>300</td><td>300</td><td>1350</td><td>1350</td><td>2100</td></tr><tr><td>测量带宽/MHz</td><td>25</td><td>22</td><td>40</td><td>40</td><td>40</td><td>40</td><td>178</td><td>215</td></tr><tr><td>谱测量精度/kHz</td><td>500</td><td>150</td><td>50</td><td>50</td><td>22</td><td>50</td><td>43</td><td>41.7</td></tr><tr><td>动态范围/dB</td><td>18</td><td>27</td><td>26</td><td>15</td><td>30</td><td>30</td><td>29</td><td>30</td></tr><tr><td>线性范围/kHz</td><td>20</td><td>8</td><td>1</td><td>1</td><td>1</td><td>1</td><td>2</td><td>7</td></tr><tr><td>功耗/W</td><td>420</td><td>520</td><td>530</td><td>430</td><td>50</td><td>30</td><td>14</td><td>32</td></tr><tr><td>质量/kg</td><td>22</td><td>20</td><td>20</td><td>25</td><td>10</td><td>10</td><td>2.3</td><td>14</td></tr></table></body></html>

从表1指标数据可以看出，随着时间的推移，Chirp 变换频谱仪的中频频率、测量带宽、频谱测量精度、信号测量动态范围均有提高，功耗和质量也得到显著改善。这是由于声表面波滤波器件、射频器件和数字处理器件性能的提高，中频频率和测量带宽的提高也得益于信号采样率和数据处理速度的提高。进人20 世纪90年代，Chirp 变换频谱仪的功耗和质量得到1\~2个量级的显著改善。1996 年以后研制的Chirp 变换频谱仪，相比之前，在测量带宽上有了4倍以上的提升。深空探测对 Chirp 变换频谱仪的功耗和质量提出了更为严格的要求。搭载于Rosetta 深空探测器的 MIRO-CTS，质量 $2 . 3 \mathrm { k g }$ 、功耗 $1 4 ~ \mathrm { { W } }$ 。2004年搭载于同温层红外天文台的德国太赫兹大气探测接收机，最高测量频率为 $4 . 7 \ : \mathrm { T H z }$ ，直接频率合成的应用使得Chirp变换频谱仪的频谱测量带宽为 $2 1 5 ~ \mathrm { { M H z } }$ ，精度为 $4 1 . 7 \mathrm { k H z }$ ，保证了行星大气和彗星大气的红外波段谱线形状测量的效率和精度，为大气模型提供了丰富准确的数据。

近年来，信息化潮流促进了电子技术的普及应用，尤其是数字处理相关技术的发展日新月异。Chirp 变换频谱仪第一次采用直接频率合成生成宽带Chirp 信号以来，十几年过去了，我们相信把性能更好的声表面波滤波器件和其它新型数字处理技术引入Chirp 变换频谱仪中，一定能够进一步提升Chirp 变换频谱仪的性能，满足更宽频带和更高精度的红外谱线实时观测需求，并实现设备的低功耗和高稳定性，为我国的行星大气、彗星、星际介质研究提供更好的观测手段。如基于现场可编程门阵列实现快速傅里叶变换可与Chirp变换频谱仪测量频谱结合使用，射频信号的数字采集回放技术和软件无线电技术[26-28]，静磁表面波滤波器技术等都可尝试应用于Chirp 变换频谱仪[29]。特别是随着微电子技术的进步，可以制造出高速率低功耗的数字自相关器，数字器件相比声表面波滤波器等模拟器件有更好的灵活性和性能，采用数字自相关器实现的红外谱后端测量设备可能逐步替代基于声表面波滤波器件的Chirp变换频谱仪。需要指出的是，对于稳定性和功耗要求严格的机载和星载应用，基于声表面波滤波器实现的Chirp 变换频谱仪仍然是一种有效的测量手段。

# 3结语

Chirp 信号具有良好的自相关特性，基于Chirp信号和脉冲压缩测量频谱原理实现的Chirp 变换频谱仪用于测量红外波段分子谱线形状，为获取行星和彗星大气的成分、比例、密度、温度和压力等参数提供了测量手段。Chirp 变换频谱仪使用声表面波滤波器件实现Chirp 信号的生成和卷积运算，得益于声表面波滤波器件的优良性能，Chirp 变换频谱仪相比于自相关频谱仪、声光频谱仪、滤波器组频谱仪、快速傅里叶变换频谱仪等频谱测量设备，具有体积小、功耗小和可靠性高等优点。直接频率合成器件的应用使得Chirp 变换频谱仪的性能进一步提高。Chirp 变换频谱仪已装备于地基、机载和星载探测设备中，用于测量地球大气、行星大气、彗星以及星际介质分子的谱线形状。

随着电子技术的发展，可以将直接频率合成、现场可编程门阵列等高性能数字器件引入Chirp 变换频谱仪中，用于生成带宽更宽的Chirp信号，修正系统非线性误差，以提高测量性能。射频信号的数字采集回放技术和软件无线电技术，静磁表面波滤波器件等技术，也可以尝试应用到Chirp 变换频谱仪中。基于数字芯片实现的快速傅里叶变换频谱仪在带宽和频谱精度性能上也不断提高，可与Chirp 变换频谱仪结合使用。

基于最新的数字器件和声表面波滤波器件，我国可以研制新型的Chirp 变换频谱仪，实现实时、更宽频段和更高精度的红外谱线测量指标，为我国的地球大气、行星大气、彗星和星际介质研究提供更好的观测手段，也为我国未来的深空探测和机载红外天文观测项目提供技术储备。

# 参考文献：

[1] Klauder JR，Price A C，Darlington S,et al. The theory and design of chirp radars [J].TheBell System Technical Journal，1960，39(4）:745-808.  
[2] Cook C E.Pulse compression，key to more eficient radar transmission [C]// Proceedings ofthe IRE.1960，48(3):310-316.  
[3] Darlington S.Demodulation of wide band low power FM signals [J]. The Bell System TechnicalJournal，1964，43(1） : 339-374.  
[4] Djuric P M,Kay S M.Parameter estimation of chirp signals[J].IEEE Transactions on Acoustics,Speech and Signal Processing，1990，38(12）: 2118-2126.  
[5] Hartogh P.Present and future chirp transform spectrometers for microwave remote sensing [C]//Proceedings of the SPIE.1997：328-339.  
[6] Villanueva G L. The high resolution spectrometer for SOFIA-GREAT: instrumentation，atmosphericmodeling and observations [D]. Germany：Freiburg University，2004.Germany:Freiburg University，2008.  
[8] Villanueva G，Hartogh P.The high resolution chirp transform spectrometer for the SOFIA-GREAT instrument [J]. Experimental Astronomy，2004，18：77-91.  
[9] Villnueva GL,Hartogh P,Reindl L.A digital dispersive matching network for SAW devices inChirp Transform Spectrometers [J]. IEEE Transactions on Microwave Theory and Techniques,2006, 54(4) : 1415-1424.  
[10] Hartogh P，Hartmann G.A high-resolution chirp transform spectrometer for microwave measurements[J].Measurement Science & Technology，1990，1(1） : 592-595.  
[11] Güsten R，Huebers H W，Graf U U，et at.GREAT-the first generation German heterodynereceiver for SOFIA [C]// Proceedings of SPIE. 2003： 23-30.  
[12] Mani D,Bhat V,Vinoy KJ,et al. Towards a broadband chirped pulse Fourier transform microwavespectrometer [J]. Indian Journal of Physics，2012，86(3）:225-235.  
[13] 杜鸿，苏步美.云台射电频谱仪预研［J].云南天文台台刊，1993(1)：25-31.Du Hong，Su Bumei. Investigation of radio spectrographs for the Yunnan Observatory [J].Publications of Yunnan Observatory，1993(1）：25-31.  
[14] 徐之材．紫金山天文台新建的毫米波射电望远镜［J].电波科学学报，1991(Z1)：22-25.Xu Zhicai. The new millimeter wave radio telescope built by Purple Mountain Observatory [J].Chinese Journal of Radio Science，1991(Z1） : 22-25.  
[15] 陈东培，宫俊杰，周献文，等.一种新型射电天文频谱仪——声表面波频谱仪［J]．天体物理学报，1993，13(1)：85-91.Chen Dongpei, Gong Junjie, Zhou Xianwen，et al. A new type of radio astronomical spectrometer-SAW spectrometer[J].Acta Astrophysica Sinica，1993，13(1）:85-91.  
[16] 陈东培，宫俊杰，周献文，等.实用声表面波线性调频变换功率谱仪设计与分析的一些问题［J]．声学学报，1991，16(2)：81-90.Chen Dongpei， Gong Junjie， Zhou Xianwen， et al. Problems in design and analysis of practicalSAW CZT spectrometer [J]. Acta Acustica，1991,16(2): 81-90.  
[17] 陈东培，宫俊杰，周献文，等．实用宽带高分辨率声表面波线性调频变换功率谱仪［J].声学学报，1991，16(1)：37-46.Chen Dongpei，Gong Junjie，Zhou Xianwen，et al.A practical spectrometer based on SAWchirp z transform [J]. Acta Acustica，1991,16(1）:37-46.  
[18] 陈东培，宫俊杰.SAW 线性调频变换实时功率谱分析技术中测频温度特性分析［J]．声学学报，1990，15(2)：121-129.Chen Dongpei，Gong Junjie. Analysis on dependence of frequency determination upontemperature in SAW-based real time chirp z transformation processr [J]. Acta Acustica,1990,15(2): 121-129.  
[19] Zhang Yuxing，Gong Junjie， Zhou Xianwen，et al. High-resolution spectrometer systems basedon SAW chirp filter [C]// Ultrasonics Symposium，IEEE Xplore.1997:89-92.  
[20] Gong Junjie, Zhang Yuxing，Zhou Xianwen，et al. Wide bandwidth SAW chirp filters with improvedmagnitude response [C]// Proceedings of the IEEE Ultrasonics Symposium. 2006: 1895-1898.  
[21] 郑兴武，加尔肯，周建军.乌鲁木齐 $2 5 \mathrm { ~ m ~ }$ 射电望远镜首次水脉泽观测［J]．中国科学（A辑），2001，31(3)：267-271.Zheng Xingwu， Jerken Esimbek， Zhou Jianjun. The first observation of water maser at UrumchiAstronomical Observatory [J]. Science in China（Series A），2001，31(3）:267-271.  
[22] 张晋，王娜，艾力·伊，等.乌鲁木齐 $2 5 \mathrm { ~ m ~ }$ 射电望远镜的单天线观测研究［J］．天文学进展，2000，18(4)：271-282.Zhang Jin，Wang Na，Esamdin Ali，et al. Single dish astrophysics observations at UrumchiAstronomical Observatory [J]. Progress in Astronomy，2000，18(4）:271-282.  
[23] Hartogh P， Sonnemann G,Grygalashvyly M,et al. Water vapor measurements at ALOMAR overa solar cycle compared with model calculations by LIMA[J]. Journal of Geophysical ResearchAtmospheres，2010，115(D1）:736-744.  
[24] Hartogh P，Jarchow C.Millimeter wave detection of mesospheric ozone using a high resolutionChirp Transform Spectrometer backend [C]// Surface and Atmospheric Remote Sensing:Technologies，Data Analysis and Interpretation.1994：3-5.  
[25] Ulkisl S，Frerkingl M，Crovisier J，et al.MIRO：Microwave Instrument for Rosetta Orbiter[J].Space Science Reviews，2007，128(1） : 561-597.  
[26] 吴亚军，刘庆会，李娟，等.上海天文台 $6 5 \mathrm { ~ m ~ }$ 射电望远镜谱线观测及数据校准［J]．天文研究与技术，2017，14(1)：1-7.Wu Yajun，Liu Qinghui,Li Juan,et al. Spectral line observation and data calibration of Tianma$6 5 \mathrm { m }$ Radio Telescope ［J].Astronomical Research & Technology，2017，14（1）：1-7.  
[27] 印琪骏，朱亮，何乐生，等.基于高性能芯片的射电天文厘米-分米波谱线观测方法［J].天文研究与技术，2017，14（1)：103-109.Yin Qijun，Zhu Liang，He Lesheng，et al.A new method to observe radio astronomy signal:centimeter-decimeter spectral line-—based on highperformance integrated circuit [J].Astronomical Research& Technology，2017，14（1）：103-109.  
[28] 托乎提努尔，张海龙，王杰.基于CUDA的射电天文多相滤波器组设计［J]．天文研究与技术，2017，14(1)：117-123.Tohtonur， Zhang Hailong，Wang Jie.A design of polyphase filter bank for radio astronomy basedon CUDA[J].Astronomical Research & Technology，2017，14（1）：117-123.  
[29] Manuilova S A，Forsb R，Khartsevc S I，et al. Pulsed laser deposited $\mathrm { Y } _ { 3 } \mathrm { F e } _ { 5 } \mathrm { O } _ { 1 2 }$ films formagnetostatic wave band pass filters [J]. Solid State Phenomena，2009，152-153：377-380.

# Application of Chirp Signal in Astronomical Observation

Fan Jiangtao，Ma Guanyi，Wan Qingtao，Zhang Jie (NationalAstronomicalObservatories，Chinese Academyof Sciences，BeijingOool2,China,Email：jtfan@bao.ac.cn）

Abstract:Chirp signal is a signal whose frequency changes continuously with time according to a certain rule.Due to its excellent autocorrelation characteristics，Chirp signal has importantapplication in real-time high-precision spectrum measurement.This paper introduces the characteristics of the Chirp signal and the principle of spectrum measurement based on the pulse compresion.It reviews the development of Chirp Transform Spectrometer（CTS）and its application in measurement of infrared spectrum of planetary atmosphere and comets for the last 3O years.Considering the latest electronic technologies，the development trend of CTS is pointed out.

Key words: Chirp signal；Pules compresion；Chirp transform spectrometer； Spectral analysis of planetary atmosphere ；Surface acoustic wave