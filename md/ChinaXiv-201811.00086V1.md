# 嫦娥四号低频射电频谱仪降低背景噪声方法研究

张韬,2,3，苏彦1，2,3

（1．中国科学院大学，北京100049；2．中国科学院国家天文台，北京100101;

3．中国科学院月球与深空探测重点实验室，北京 100101 ;)

摘要：嫦娥四号着陆器将搭载低频射电频谱仪在月球背面进行低频射电天文观测。该低频射电频谱仪的观测波段为0.1MHz\~40MHz。根据着陆器在中国空间技术研究院的微波暗室进行的电磁兼容性（Electromagnetic Compatibility，简称EMC）试验结果，着陆器平台在该频段内自身存在非常强的噪声，其强度甚至淹没掉大部分来自太阳爆发的信号，难以探测有效信号，实现预期的科学目标探测。本文通过模拟仿真分析谱减法，自适应滤波以及维纳滤波这三种方法对着陆器噪声消除的效果，从而选择更为有效的噪声消除方法，为低频射电频谱仪在轨探测任务的数据处理提供依据。

关键词：低频射电频谱仪；嫦娥四号；谱减法；维纳滤波；自适应滤波

中图分类号：P161

# 0引言

美国的著名工程师卡尔·央斯基在1930 年用他自己建造的“旋转木马”首次观测到了来自银河系的射电辐射[1]，自此展开了对射电天文的广泛研究。经过天文学家的研究发现，不同的天体因为辐射机制的不同会产生不同波段的电磁辐射。因此，对宇宙进行全波段观测是一件非常有意义的事。但是，地球大气的存在使得很多射电波段的信号特别是频率低于10MHz 的甚低频波段难以穿透到地面。然而，低频波段的探测对于研究天体的演化与起源有着至关重要的作用。为了弥补甚低频波段的观测空白，国际上许多国家或组织发射过卫星到\*基金项目：国家天文台（总部）台级调控基金(Y734061V01)资助.收稿日期：\*\*\*\*\*；修订日期\*：\*\*\*\*\*\*\*作者简介：张韬，男，硕士，研究方向：天文技术与方法。Email:zhangtao@nao.cas.cn空间进行观测，比如WIND 和Ulysses。

由于地球以及众多在轨卫星的电磁干扰，空间低频射电观测也面临挑战。因为月球自身可以遮挡来自地球方向的射电干扰，所以月球背面的射电宁静区是十分理想的观测地点。欧航局（ESA）于2015年1月提出了在2025年对月球背面发射一颗载有低频射电频谱仪的着陆器的FARSIDE 计划[2]。我国提出嫦娥四号探月计划。嫦娥四号是世界首颗在月球背面软着陆和巡视探测的航天器。2018年5月21日，嫦娥四号中继星“鹊桥”成功发射，着陆器和巡视器将于年底发射，该着陆器上搭载了一台科学载荷低频射电频谱仪，是人类在月球背面首次实现对宇宙和太阳的低频段（0.1MHz\~40MHz）进行观测。

根据着陆器整器在微波暗室的EMC试验结果，虽然来自外界的信号干扰可以被很好的屏蔽掉，但是着陆器本身搭载的电子设备以及其它的载荷对低频观测存在电磁干扰，由于无法对平台进行工程上的调整，所以只能通过数据处理的方式来消除平台的干扰。目前在语音信号以及雷达信号处理等方面，降低信号的噪声处理主要有三种方法：谱减法、自适应滤波和维纳滤波方法。本文将结合低频射电频谱仪的科学目标，对比分析信号增强效果，得到最优化的方法，为低频射电频谱仪在轨探测任务的数据处理提供依据。

# 1低频射电频谱仪的工作原理以及噪声来源

低频射电频谱仪系统由四根接收天线（三根5m长的长天线A、B、C，一根 $2 0 \mathrm { c m }$ 长的短天线D)，前置放大器以及电子学单元组成。三根长天线 A、B、C 是相互垂直的[3-4]（如下图1所示)，接收空间的电磁信号的三个方向上的分量，根据电磁的传播理论就可以计算出接收的信号的强度以及方向。短天线D与长天线B、C处于同一个平面，根据电磁波的传播理论以及不同长度的天线的增益的不同，A、B、C 长天线可以同时接收到来自宇宙空间的远场信号和来自着陆器本身的近场信号，而短天线D因天线短且离着陆器近，因此收到主要是来自近场的着陆器噪声信号[3]。

![](images/d16aba0f4dc97f4daddd1b0a568b62cb6367a8740952c00aaf5fffd16c2eaf0a.jpg)  
图1低频射电频谱仪四根天线[3]   
Fig.1 The four antennas of the very low frequency radio spectrometer[3]

嫦娥四号上搭载的低频射电频谱仪的工作频率包括低频(100KHz\~2MHz)和高频(1MHz\~40MHz)两个频段，频谱仪的主要技术参数如下表1所示，

表1低频射电频谱仪主要技术参数[3]

Tab.1 Main technical parameters of Very low frequency radio spectrometer[3]   

<html><body><table><tr><td>项目</td><td>设计参数</td><td>实测结果</td></tr><tr><td>工作频率</td><td>100KHz~40MHz</td><td>100KHz~40MHz</td></tr><tr><td>接收机灵敏度(nV/VHz)</td><td>6</td><td>8.1</td></tr><tr><td rowspan="2">频率分辨率</td><td>低频：5KHz</td><td>4.88 KHz</td></tr><tr><td>高频：100KHz</td><td>97.66 KHz</td></tr><tr><td>最大数据率(bps)</td><td>4.5M</td><td>4.34M</td></tr><tr><td>功耗(W)</td><td>24</td><td>24</td></tr></table></body></html>

在低频射电频谱仪工作的同时,着陆器上其他部分载荷以及一些电子模块也同时处于运行状态，比如电源控制器、数传调制器、发射段RE102、数传控制 SMU等。下图2给出了月球表面的电磁波通量密度，而天线附近区域的电场强度和接收机输出的电压值可以根据下面公式计算得出：

$$
\begin{array} { r } { U _ { o u t } = \frac { \Game { { \bf { G } } _ { p r e a m p } } \ { { \bf { G } } _ { R e c e i v e r } } \ { I { L _ { c o a x } } } } { 1 + { Z _ { \alpha } } / { Z _ { p r e a m p } } } * \overrightarrow { h _ { e } } \overrightarrow { E } \ ( \mathrm { ~ 1 ~ } } \end{array}
$$

式中， $\mathrm { \Delta U _ { o u t } }$ 为接收机的输出电压值， $\mathbf { G } _ { \mathrm { p r e a m p } }$ 和 $\mathbf { G } _ { \mathrm { R e c e i v e r } }$ 分别是前置放大器增益和接收机增益，$\mathrm { I L } _ { \mathrm { c o a x } }$ 为高频电缆插损, $Z _ { \mathrm { a } }$ 和 $Z _ { \mathrm { p r e a m p } }$ 分别是天线阻抗和前置放大器阻抗， $\overrightarrow { h _ { e } }$ 为天线有效长度，$\overrightarrow { E }$ 则是天线处的电场强度。

![](images/af9cca4b8901dab8757e40a2d1961c558e2f8e3e4fbbbc881e0ff9964e837dee.jpg)  
图2月球表面的电磁波通量密度[2][2]Fig.2Radio emission levels on the surface of moon

公式（1）中的各项参数可以根据低频射电频谱仪生产方提供的定标报告获取，结合各项参数以及公式（1）可以将接收机测得电压数据反演出空间电场以及通量密度。图2中给出了各天体到达月球表面的通量密度，图中的着陆器噪声是根据在中国空间技术研究院的微波暗室当中对嫦娥四号着陆器整器进行的EMC试验中测得工况三(着陆器电源控制器主份、数管管理单元主份、数传调制器主份、载荷电控箱主份、低频射电频谱仪等依次加电连续工作）天线 A接收到的高频段数据反演得到。从图中可以发现着陆器的噪声通量密度大于普通的太阳爆发产生的通量密度，与太阳爆发峰值通量密度相当。所以不对接收到信号进行降噪处理，我们难以反演出太阳爆发的真实强度。

# 2低频射电频谱仪有效信号提取方法

由于低频射电频谱仪的三根主要天线A、B、C收到的目标信号里都会包含有来自着陆器自身的噪声信号的干扰，所以在对信号进行提取使用之前需要通过降噪算法来抑制噪声并最大限度的分离出有用的信号。用 $\mathbf { x } ( \mathbf { n } )$ 表示观测到信号，s(n)表示有用信号，v(n)表示噪声信号。它们中间的关系可以表示为：

$$
\scriptstyle \mathtt { x ( n ) } = s ( \mathtt { n } ) + \mathtt { v ( n ) }
$$

在本文的模拟仿真中，将一组强度与太阳爆发强度接近的模拟信号作为有用信号 s(n)，用EMC试验测得的工况三的着陆器噪声当作噪声信号 $\mathbf { v ( n ) }$ ，通过自适应滤波，谱减法以及维纳滤波的方法来进行仿真处理。

# 2.1谱减法

谱减法是信号增强的一个常见方法，其原理是在频域上用信号加噪声的幅值减去噪声的幅值得到有用信号的幅值。S.FBoll于1979 年改进了该方法，称为改进的谱减法[5。改进的谱减法在谱减的过程中使用的是噪声的平均功率，可以有效得减小剩余的“音乐噪声”。改进谱减法可以用公式表示为

$$
| S ( n ) | ^ { \gamma } = \Big \{ ^ { | \mathrm { X } ( \mathrm { n } ) | ^ { \gamma } - a * D ( n ) ; | \mathrm { X } ( \mathrm { n } ) | ^ { \gamma } \geq a * D ( n ) }  _ { b * D ( n ) ; | \mathrm { X } ( \mathrm { n } ) | ^ { \gamma } < a * D ( n ) }
$$

其中D(n)为噪声的平均幅值，

$$
\begin{array} { r } { \mathrm { D } ( \mathrm { n } ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } | D _ { i } ( n ) | ^ { \gamma } ( 4 ) } \end{array}
$$

公式（3）、（4）中 $\gamma$ 等于1或2，为1时就是幅值相减， $\gamma$ 为2时就是功率相减。a（a≥1)为过减因子, ${ \mathsf { b } } ( { \mathsf { b } } { > } 0 )$ 是补偿因子，可以通过调节两个参数来减少周期性的误差。结合低频射电频谱仪的结构特点以及对科学数据的要求，可以用长天线A、B、C收到信号的幅值的平均值减去短天线D收到信号的幅值的平均值来获取信号的幅值。

由于在设计上天线A、B、C与天线D的长度以及材质不一样导致其增益也不相同，所以在进行谱减的时候需要补充不同增益带来的信号强度差异。具体来说，先取一小段时间内的信号计算出它们的对消系数。然后在后续的处理过程中将D天线收到信号的平均幅值乘以对消系数来获取噪声幅值。可以结合低频射电频谱仪的结构特点来运用改进的谱减法进行降噪处理，以天线A和天线D为例可以用公式表示为

$$
| S ( f ) | = \left\{ { \begin{array} { l l } { | V _ { A } ( f ) | - | P ( f ) \ast V _ { D } ( f ) | ; } & { | V _ { A } ( f ) | \geq | P ( f ) \ast V _ { D } ( f ) | } \\ { b \ast | P ( f ) \ast V _ { D } ( f ) | ; } & { | V _ { A } ( f ) | < | P ( f ) \ast V _ { D } ( f ) | } \end{array} } \right. ( 5 )
$$

其中 $\mathrm { \Delta V _ { A } ( f ) }$ 是长天线A收到的信号进行傅里叶变换后在相应频点的平均值， $\mathrm { \Delta V _ { D } ( f ) }$ 则是短天线D 收到的信号在相应频点的平均值， $\boldsymbol { \gamma }$ 取1。P(f)通过取太阳宁静时的一小段时间内四个接收机接收到的信号分别算出的，

$$
\mathrm { \bf P _ { \mathrm { \scriptscriptstyle A } } ( f ) = \frac { \bf V _ { \mathrm { \scriptscriptstyle A } } ( f ) } { \bf V _ { \mathrm { \scriptscriptstyle D } } ( f ) } }
$$

处理流程如图3所示。

![](images/80e6cb8e317906a525415ef587bf6bcd9d4c1a257292f8d620f727c4034ca9cf.jpg)  
图3改进谱减法运算示意图  
Fig.3Improved spectral subtraction diagram

下面三种数据处理方法以天线A与天线D数据进行仿真为例，谱减法仿真结果如图 4

所示；

![](images/7f28d34cf4889bd69b43ca14397bdeb17be2a2417464828429615ecf818e7347.jpg)  
图4改进谱减法仿真结果

Fig.4Simulation results by improved spectral subtraction

图4中展示的是FFT后的频域信号，横轴表示频率（单位为MHz），纵轴为幅度（单位为 dBuV)。图4中黑色的曲线是带有噪声的信号，蓝色的曲线是经过改进谱减法处理后的信号，红色的曲线是有用信号。从图4中可以看出该方法在整个波段对噪声都有有效的抑制，在10MHz以下的频段内噪声的幅度下降了20dB 左右，在其它频段也能将噪声降低10dB 左右，且处理后的信号波形基本能还原原本的有用信号，在背景噪声较低的频段（20MHz\~40MHz）处理效果更好。

# 2.2维纳滤波

从公式（2）中可知，我们进行信号处理的目标是得到不含噪声的有用信号 s(n)。但是在实际的信号处理过程中，我们求得的有用信号并不完全等于s(n)，只能是s(n)的逼近值或估计值，因此对信号的处理可以看作是对s(n)的估计，处理信号就是找到一个最佳的估计器。维纳滤波就是一个寻找最佳估计器来估计信号的方法[6-7]。

![](images/a5a3184d697aa376d00550f889a810e126f29df0afc97518fe8cf78f8bac429e.jpg)  
图5维纳滤波器

图5为维纳滤波的原理示意图，其中 $\mathbf { h } ( \mathbf { n } )$ 是维纳滤波器的滤波参数，y(n)是对有用信号s(n)的估计值。用公式可以表示为

$$
y ( n ) = x ( n ) * h ( n ) ( 7 )
$$

根据最小误差准则（LMS）使 $\mathfrak { x } = \mathrm { E } [ \{ s ( \mathrm { n } ) - \mathrm { y } ( \mathrm { n } ) \} ^ { 2 } ]$ 达到最小就可以算出最佳滤波参数，

$$
\mathrm { { h ( n ) } ~ = ~ { \frac { E [ s ( n ) \cdot \mathrm { { x ( n ) } ] } } { \mathrm { { E [ x ^ { 2 } ( n ) ] } } } } ~ }
$$

将上式取傅里叶变换可以导出，

$$
\mathrm { H ( k ) = \frac { P _ { \mathrm { s x } } ( k ) } { P _ { \mathrm { x } } ( k ) } } ,
$$

其中 $\mathbf { P } _ { \mathrm { s x } } ( \mathbf { k } )$ 为 $\mathbf { s } ( \mathbf { n } )$ 与 $\mathbf { x } ( \mathbf { n } )$ 的互功率谱密度， ${ \sf P } _ { \mathrm { { x } } } ( { \bf k } )$ 为 $\mathbf { x } ( \mathbf { n } )$ 的功率谱密度。由于有用信号 s(n)与噪声信号 $\mathbf { v ( n ) }$ 互不相关，即有 $\mathrm { \bf P _ { \mathrm { s v } } ( { \bf k } ) } = 0$ ，则可以得到

$$
\mathrm { P } _ { s x } ( k ) = P _ { s } ( k )
$$

$$
\mathrm { P } _ { x } ( \boldsymbol { k } ) = P _ { s } ( \boldsymbol { k } ) + P _ { d } ( \boldsymbol { k } )
$$

将式（10）和式（11）带入式（9）中可以得到式（12）

$$
\mathrm { H ( k ) } = 1 - \frac { 1 } { \gamma ( \mathrm { k ) } }
$$

公式(12)中， $\gamma ( k )$ 为傅里叶变换以后对应频点处带噪信号的功率谱与噪声功率谱的比值[8]。根据天线D和天线A接收到数据可以计算出 $\gamma ( k )$ ，从而计算出最佳的滤波参数。下面图6为仿真结果。

![](images/803b879c00927ac4bb65ca7c56d8388a7094a0006c5d825767129c2ccbe88e05.jpg)  
图6维纳滤波仿真结果

Fig.6Simulation results byWiener filter

从图6中可以看出维纳滤波也可以降低噪声的影响，但是相对于谱减法的降噪效果要差一些。基本也能还原原有用信号的波形，但是处理后的信号在背景噪声比较大的波段（0\~20MHz）仍难以分辨出有用信号。

# 2.3自适应滤波降噪

不同于维纳滤波，自适应滤波器可以根据收到信号不断地自动的调节自身的参数来最大限度的降低噪声信号[9。自适应滤波已经广泛运用在系统识别、信道均衡、信号增强以及信号预测方面。本文中主要运用的是它的信号增强的功能，它的结构示意图如下图7所示。自适应滤波算法至少需要两套接收设备，其中一套用来接收带有噪声的信号，一套专门用来接收噪声，然后通过自适应算法求得有用信号，而低频射电频谱仪正好有这两套接收设备。

![](images/349b102a421fcb98ff3ead21e46ad40489fb9d48fc6ee4caeb1f03459fa75b67.jpg)  
图7自适应滤波器结构图  
Fig.7Structure of the adaptive e filter

如上图7所示为一个自适应降噪滤波器的结构示意图，其中 $\mathbf { x } ( \mathbf { n } )$ 是指接收机收到信号（其中包括有用的信号 s(n)以及噪声信号 ${ \bf v } ( { \bf n } ) ) ,$ ，而 $\mathbf { v } _ { 1 } ( \mathbf { n } )$ 则是指另一个接收机接收到的噪声信号,e(n)表示误差信号。它们之间的关系可以表示为

$$
\begin{array} { r } { e ( \mathrm { n } ) = \mathrm { x } ( \mathrm { n } ) - \sum _ { i = 1 } ^ { N } [ w ( i ) v _ { 1 } ( n - i ) ] } \end{array}
$$

式(13)中 $\mathbf { w } ( \mathbf { n } )$ 表示的是滤波器的加权系数，该系数可以通过最小均方误差准则(LMS)或者最小二乘法（RLS）评估 $\operatorname { E } [ \mathrm { e } ^ { 2 } ( \mathrm { n } ) ]$ 来调整，使滤波器工作在最佳的状态[10-12]。下面利用最小二乘法（RLS）来进行仿真。

![](images/47f22b55bc79f83a809823588f870d708a207c11d53ba0e4a1004c67398dfc87.jpg)  
图8自适应滤波仿真结果

Fig.8Simulation results byadaptive filter

从图8中可以发现利用自适应滤波的方法仿真的结果比较差，降噪效果不明显，对信号的还原度也不高。在噪声信号中一些幅度比较大的频点处（如1.73MHz、2.32MHz、2.9MHz等)，经过自适应滤波处理后噪声信号幅度没有下降。

# 3低频射电频谱仪背景噪声消除结果分析

2.1到 2.3已经通过三种不同的数据处理方法对着陆器噪声进行了仿真处理，其中自适

应滤波方法是在时域的处理方法，改进谱减法和维纳滤波则是在频域的处理方法。表1给出了这三种信号增强办法对信号信噪比的提升效果的对比。

# 表2三种方法处理数据前后的信噪比

Tab.2 SNR before and after the data processing by three different algorithms   

<html><body><table><tr><td>数据处理方法</td><td>改进谱减法</td><td>维纳滤波</td><td>自适应滤波（RLS)</td></tr><tr><td>处理前信噪比/dB</td><td>-27.64</td><td>-27.64</td><td>-27.64</td></tr><tr><td>处理后信噪比/dB</td><td>1.99</td><td>-4.64</td><td>-25.35</td></tr><tr><td>信噪比提升/dB</td><td>29.63</td><td>23.00</td><td>2.29</td></tr></table></body></html>

从表1中我们可以发现改进谱减法和维纳滤波的处理结果明显好于自适应滤波，且其中改进谱减法的信噪比提升是略大于维纳滤波的。自适应滤波信号增强系统降噪能力受参考输入端的噪声信号 $\mathbf { v } _ { 1 } ( \mathbf { n } )$ 与带噪信号中的噪声信号的相关度有很大的影响。在低频射电频谱仪设计的时候用于接收信号的长天线A、B、C与用于接收着陆器噪声信号的短天线D的各项参数不同，以及仿真的信号中有用信号的信噪比非常的低等因素导致了自适应滤波降噪的效果变差。长天线A、B、C与短天线D的参数不同导致D天线与长天线收到噪声信号的不同可以在频域上通过评估短天线与长天线在不同频点处的增益差异来抵消，所以在频域处理的两种算法在降噪时能取得比较好的效果。

为了验证低频射电频谱仪的性能以及数据处理方法，我们在中国科学院国家天文台密云观测站食堂楼顶安装好低频射电频谱仪以及接收天线进行了外场试验，并且在距离接收天线100米左右的宿舍楼里用任意波形发生器连接天线发射模拟信号。而着陆器噪声信号是采用的 EMC试验工况三的试验结果，由一个放在接收天线下方的1米长的小天线连接波形发生器发出。下图9为其中一组试验天线A接收到的数据在利用改进的谱减法处理后的结果，其中发射的有用信号为1.8MHz的点频信号。

![](images/7375ffda25e4a3ff00dcda8c261a535db4f33f254fce7f15675def7bf42506ba.jpg)  
图9改进谱减法处理结果

Fig.9Noise reductionby improved spectral subtraction

图9中截取了 $1 . 7 \mathrm { M H z } { \sim } 1 . 9 \mathrm { M H z }$ 的信号，从图中可以看出经过改进谱减法处理后，着陆器的噪声被有效的抑制了，幅度下降了10dB，而有用信号的幅度并没有被降低，信噪比也从-25.23dB提升到了-2.60dB。通过改进谱减法处理后的信号，信噪比提升了-22.63dB，说明改进谱减法在外场实验中对于着陆器背景噪声信号的降低也是有效的。

# 4总结

在月球背面进行极低频(0.1～40MHz)探测是非常有科学意义的[13],同时由于该频段信号微弱信噪比低，所以提取有用信号也是十分困难的。本文利用EMC 测试的着陆器噪声以及嫦娥四号搭载的低频射电频谱仪对月球背面能接收到的目标信号强度进行了仿真实验。利用改进的谱减法、维纳滤波以及自适应滤波这三种常见的信号增强的算法对仿真信号进行了提取，其中改进的谱减法对信号的提取效果显著，经处理后信噪比有明显的提升，可以直观的从处理后的波形中看见目标信号波形。并且改进的谱减法对在密云进行的外场试验的数据的处理也有很好的效果。因此，可以将改进的谱减法作为低频射电频谱仪主要的预处理方法，实现对太阳爆发进行较为准确的观测。低频射电频谱仪在月球背面进行探测的过程中，温度等环境的变化可以引起对消系数的改变，所以在实际探测过程中需要结合实际环境情况，每

隔一段时间计算一次对消的系数。

参考文献：   
[1JanskyKG.DirectionalStudiesofAtmosphericsatHighFrequenciesM/Classcs inRadioAstronomy.SpringerNethrlands, 1932:10-22.   
[2]MimounD,Wieczorek MA,AlkalaiL,etal.Farsideexplorer:uniquesciencefromamisiontothefarsideoftheon[J]. Experimental Astronomy,2012,33(2-3):529-585.   
[3]纪奕才，赵博，方广有,等．在月球背面进行低频射电天文观测的关键技术研究[J]．深空探测学报，2017, 4(2) :150-157. JI Yicai, ZHAO Bo,FANG Guangyou,etal. Key Technologies of Very LowFrequency Radio Observations on theLunar Far-Side[J]. Journal of Deep Space Exploration,2017,4(2):150-157.   
[4]施硕彪，董亮，高冠男,等．米波太阳射电频谱仪的科学目标和技术方案[J]．天文研究与技术，2011，8(3):229-235. ShiShuoBiao,DongLiang,Gao Guannan,etal.ScientificObjectivesandTechnicalDesignofaMeter-Wave Spectrometer for Solar Radio Observation [J].Astronomical Research and Technology,2011, 8(3):229-235.   
[5]Boll S.Suppressionofacousticnoise inspeech using spectralsubtraction[J].Acoustics Speech & Signal Procesing IEEE Transactions on,1979,27(2):113-120.   
[6]Brown R G,Hwang PYC.Introductionto random signals and applied Kalman filtering:[M].John Wiley & Sons,1997.   
[7]Wiener,N.Extrapolation,Interpolation,and Smoothingof Stationary Time Series :[M].JohnWiley& Sons,949.   
[8]宋知用．MATLAB 语音信号分析与合成[M]．北京航天航空大学出版社，2017. SONG ZY. MATLAB speech signal analysis and synthesis [M]. Beihang University Press, 2017.   
[9]耿妍，张端金．自适应滤波算法综述[J]．太赫兹科学与电子信息学报，2008，6(4):315-320. GENGY,ZHANGDJ.Surveyofadaptivefiteringalgorithms[J].InformationandElectronic Engineering,2008,6(4):

[10]PauloS.R.Diniz.Adaptivefiltering:algorithmsand practicalimplementation[M].KluwerAcademicPublishers,2008.

[11]沈福民．自适应信号处理[M]．西安：西安电子科技大学出版社，2001.

SHEN Fumin.Adaptive Signal processing [M].Xidian University Press,2001.

[12]王树棠，王蕴红．自适应滤波器阶数与稳态均方误差[J]．电路与系统学报，1997(1):65-67.

Wang Shutang,Wang Yunhong.StudyonOrder Numberof AdaptiveFilterand its Steady State SquareEror[J].Journalof Circuits and Systems,1997(1):65-67.

[13]梅丽，苏彦，周建锋．极低频射电天文观测现状与未来发展[J]．天文研究与技术，2018，15(2):127-149.

MeiLi,SuYan,ZhouJianfeng.TheHistoryandDevelopmentofLow-FrequencyRadio Observation[J].Astronomical

Research and Technology,2018,15(2):127-149.

# Research of The Method forReducing Background of Very Low Frequency Radio Spectrumon Chang'E-4

Zhang Taol 2.3，Su Yan1: 2 3

(1. University of Chinese Academy of Sciences,Beijing 1Ooo49,China,Email: zhangtao@nao.cas.cn;

2.National Astronomical Observatories,Chinese Academy of Sciences,Beijing 1OolO1, China;

3.KeyLaboratory for Exploration in the Moonanddeep Space,Chinese Academyof Sciences,Beijing Oolo1,China)

Abstract: Chang'E-4 will carry a Very Low Frequency Radio Spectrometer(VLFRS), which will land on the far-side of the moon forRadio observation.The VLFRS has an observation frequency of 0.1MHz\~40MHz.According to Electromagnetic Compatibility(EMC) test results in the Microwave darkroom of China Academy of Space Technology, the lander platform is quite noisy in this band,and the intensity of the noise is even stronger than that of most signals from the sun burst. In this pape,we will simulate and optimize background elimination through improved spectral subtraction,adaptive filtering and wiener filtering,and choose a more effective method foreliminating background.

Key word: Very low frequency radio spectrometer;Chang'E-4;Improved spectral subtraction;Wiener filtering;Adaptive filtering