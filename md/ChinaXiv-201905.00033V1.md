# Chirp信号多径时延估计算法研究

冯亚丽，刘成，张祥斌(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：针对分数阶傅里叶变换（fractional fourier transform，FRFT）对Chirp 信号进行多径时延估计时的不足，改进了一种按照多径分量能量大小依次消除的FRFT多径时延估计算法。该算法以迭代方式进行，按多径分量的能量大小依次返回多径分量的估计值；在每次迭代中，包含子选代以准确判定当前分量的多径参数和起止时间，然后利用当前多径参数生成探测信号时域副本，将其从残余信号中减去，达到多径信号的分离。以根据功率时延分布的特点拟定的信道模型作为传输环境，对该算法进行了仿真验证。仿真表明，相比于其他三种时延估计算法，改进算法能够更准确的对多径时延进行估计。

关键词：时延估计；Chirp信号；分数阶傅里叶变换；多径分量消除 中图分类号：TN911.7 doi:10.19734/j.issn.1001-3695.2018.11.0872

Research on multipath delay estimation algorithm for chirp signal

Feng Yali, Liu Cheng, Zhang Xiangbin (School of Communication & Information Engineering, Chongqing Universityof Posts & Telecommunications,Chongqing 400065, China)

Abstract: Inorder tosolve the problemofthe fractional Fourier transform（FRFT）in estimating the multipath delay for Chirp signal,this study proposed an improvedFRFTmultipath delay estimationalgorithm based on theenergyof each multipath component.The algorithm sequentially returns the estimated values of multipath components by iteration according to theenergy magnitudeof multipath components.In each iteration,thereareasub-iteration to accurately estimatethe parameterand locationof thecurrentcomponent,andthen generates atime domaincopyof the sounding signal, which issubtracted fromtheresidual signal to reach separation of the multipath signal.This paper made some experiments which use channel model based onthecharacteristics ofpowerdelaydistribution.and theresults show that theimproved algorithm can estimate the multipath delay more accurately than the other three delay estimation approaches.

Keywords: time delay estimation;chirp signal; fractional Fourier transform; multipath component cancelation

# 0 引言

Chirp 信号又称线性调频信号，存在于自然界的很多领域，如天体物理学中的引力波、蝙蝠的回声定位、医学中的心音信号等。因Chirp信号具有高处理增益、低发射功率、抗多普勒频移等优点，所以其在雷达[1]、扩频通信[2]、水下探测[3]和UWB探测[4]等领域中有着相当广泛的应用。对Chirp信号进行多径时延估计是信道探测中对测量数据进行处理的一个关键环节。传统的多径时延估计主要采用匹配滤波、解卷积（de-convolution，DC）算法。Bell等人提出的匹配滤波算法，其时延分辨率为脉冲压缩后sinc函数的主瓣宽度（近似于探测信号带宽的倒数)，sinc函数旁瓣对多径信息的提取影响比较大[5]。DC 算法对噪声的存在较为敏感，只有在信噪比（signaltonoise ratio，SNR）足够好的时候才能很好地估计出多径时延[；传统的这些算法要求探测信号为平稳信号，而Chirp信号为非平稳信号，所以用其来处理Chirp信号存在先天不足。随后的一些基于高阶累积量的算法，如互四阶矩最小范数时延估计算法和四二阶归一化累积量自适应时延估计方法，此类算法首先把Chirp 信号转换为平稳信号，再进行时延估计，时延估计准确度高；但此类算法时间复杂度普遍较大，不适合实际使用[7]。随着FRFT理论的出现和不断发展，作为非平稳信号的有力分析工具，因其变换基底为一组正交的Chirp信号，且具有多种与快速傅里叶变换（fastfouriertranform,FFT）计算相当的离散算法，近年来被广泛应用于Chirp 信号的检测与参数估计[8\~10]。Ozaktas 等人[8]于1996 年提出了一种精确计算FRFT 的离散算法。所提出的算法的时间复杂度为O（NlogN)。至此，FRFT不再停留于理论研究阶段，迈向了工程实践的道路。Tao等人[9在前人的研究基础上，首次推导了FRFT时延估计（FRFTtimedelay estimation,FRTDE)算法的精度与SNR之间关系的数学表达式。Zhou 等人[]基于FRTDE 算法提出了一种新的子样本FRFT 时间延迟估计(subsample FRFT time delay estimationSFRTDE)算法，它进一步利用信号 FRFT 输出峰值的相位信息来搜索匹配的时延，并通过计算机仿真验证了其相对于FRTDE和平均幅度平方分数差分函数算法的有效性和优越性。Sejdic 等人[1]对 FRFT 做了一个较为详细的概述，具体介绍了FRFT定义，数学实现及其应用领域，将其和数学变换联系起来，强调实现FRFT的各种方法，并比较了它们的优缺点，总结了FRFT处理非平稳信号和时变信号所存在的优势。

在信道测量系统硬件资源和计算复杂度结合考虑的情况下，经济适用的多径时延估计方法成为当下迫切的需求。本文从现有的时延估计技术入手，同时应用Chirp信号在FRFT域的峰值汇聚特性和时域的脉冲压缩特性来研究新的时延估计算法，以便从测量数据中得到更精确的信道模型。

# 1 信号模型

Chirp信道探测信号的时域表达式为

$$
\begin{array} { r l } { s ( t ) = \exp ( { j 2 \pi f _ { c } t } + j \pi k t ^ { 2 } ) } & { { } - T _ { s } / 2 \leq t \leq T _ { s } / 2 } \end{array}
$$

其中： $f _ { c }$ 为中心频率； $k$ 为调频率； $T _ { s }$ 为Chirp信号的持续时间，Chirp 信号的带宽 $B = k T _ { s }$ 。探测信号在传播过程中可能会遇到建筑物、树木，以及起伏的地形,这就会导致电波出现反射、散射、透射及绕射等现象，所以到达接收端天线的信号不是只从单一路径来的,而是许多路径的信号合成。多径信道时延估计问题的接收信号模型可以表示为

$$
r ( t ) = \sum _ { m = 1 } ^ { M } a _ { m } s ( t - \tau _ { m } ) + e ( t )
$$

其中： $e ( t )$ 为零均值、方差为 $\sigma ^ { 2 }$ 的高斯白噪声； $M$ 、 $a _ { { \scriptscriptstyle m } }$ 、 $\tau _ { m }$ 为未知参数，分别对应信道的多径信号数目，第 $m$ 条多径信号的幅度和时延。

# 2 基本的FRFT多径时延估计算法

# 2.1Chirp 信号的 FRFT

Chirp 信号是FRFT的标准正交基。根据正交基的特性，Chirp信号变换到某个特定阶次的分数阶傅里叶变换域上将是一个冲击函数，产生能量聚集的特性，所以FRFT特别适合处理Chirp信号[12]。实际应用中Chirp信号都是有限长的，即Chirp信号的持续时间是有限的，因此其分数阶傅里叶变换的形式也有所改变。Chirp探测信号 $P$ 阶傅里叶变换为

$$
\begin{array} { c } { { F ^ { P } [ s ( t ) ] = f _ { p } ( u ) = \sqrt { 1 - j \cot \alpha } \times } } \\ { { \displaystyle \int _ { - r _ { s } / 2 } ^ { r _ { s } / 2 } \exp [ j \pi ( t ^ { 2 } \cot \alpha - 2 u t \csc \alpha + u ^ { 2 } \cot \alpha ) ] \cdot } } \\ { { \displaystyle \exp [ j ( 2 \pi f _ { c } t + \pi k t ^ { 2 } ) ] d t = \sqrt { 1 - j \cot \alpha } \cdot \exp ( j \pi u ^ { 2 } \cot \alpha ) \times } } \\ { { \displaystyle \int _ { - r _ { s } / 2 } ^ { r _ { s } / 2 } \exp [ j \pi t ^ { 2 } ( \cot \alpha + k ) ] \cdot \exp [ j 2 \pi t ( f _ { c } - u \csc \alpha ) ] d t } } \end{array}
$$

其中： $\alpha$ 为旋转角度， $\alpha = p \pi / 2$ 。最佳变换阶次与Chirp 信号调频率的关系是[13]:

$$
p = - { \frac { \arctan ( { \frac { 1 } { k } } ) } { \pi / 2 } }
$$

即当 $k = - \cot \alpha$ 时，Chirp信号变换到对应的分数阶傅里叶变换域表现出sinc函数的形式，式（4）可化简为

$$
\begin{array} { c } { { f _ { p } ( u ) = \sqrt { 1 - j \cot \alpha } \cdot \exp ( j \pi u ^ { 2 } \cot \alpha ) \cdot } } \\ { { T _ { s } / 2 } } \\ { { \displaystyle \int \phantom { - } \int \phantom { - } \exp [ j 2 \pi t ( f _ { c } - u \csc \alpha ) ] d t = } } \\ { { - T _ { s } / 2 } } \\ { { T _ { s } \sqrt { 1 - j \cot \alpha } \cdot \exp ( j \pi u ^ { 2 } \cot \alpha ) \cdot \sin c [ \pi T _ { s } ( f _ { c } - u \csc \alpha ) ] } } \end{array}
$$

当 $\scriptstyle f _ { c } = u \csc \alpha$ ，sinc 函数取最大值为1，则此时 $\left| f _ { p } ( \mu ) \right|$ 取得最大值。从以上推导过程可以看出，当FRFT的旋转角度 $\alpha$ 满足时 $k = - \cot \alpha$ 的条件时，Chirp信号在频域出现了能量高度汇聚的特性，被压缩成了一条"谱线”，包含了Chirp信号的全部能量，即Chirp的频域压缩。Chirp信号各阶次的分数域三维波形及最佳阶次的分数域波形分别如图1和2所示。

# 2.2FRTDE 算法

FRTDE 算法主要利用Chirp 信号在FRFT域的峰值汇聚特性对多径时延进行估计。Chirp 信号在分数阶傅里叶变换域上有良好的能量聚集特性，而高斯白噪声变换到分数域仍为高斯白噪声，不会在任何阶分数域上产生能量聚集，可以利用Chirp 信号和高斯白噪声的此特性进行多径时延估计[14]。

对接收到的带有噪声的多径信号 $r ( t )$ 进行分数阶傅里叶变换将其变换到使其能量产生聚集的最佳阶傅里叶变换域上，然后在分数域上对信号幅度谱的峰值位置进行检测，获得峰值和峰值点位置的坐标，并与发射信号 $s ( t )$ 在分数域上幅度谱的峰值位置进行比较，就可以获得幅度谱的位置偏移量及峰值比例。为方便推导，假设 $M = 1$ ，幅度 $a _ { 1 } = 1$ ，根据分数阶傅里叶变换的时移特性，则有

$$
F ^ { \cal P } [ s ( t - \tau ) ] = e ^ { j ( \tau ^ { 2 } / 2 ) \sin \alpha \cos \alpha } e ^ { - j u \tau \sin \alpha } f _ { p } \left( u - \tau \cos \alpha \right)
$$

对两边取绝对值得

$$
\left| F ^ { P } [ s ( t - \tau ) ] \right| { = } \left| f _ { p } ( u - \tau \cos \alpha ) \right|
$$

![](images/b2f5a8c65000f06bcd148be8a966e9f8ef499957f27af96cf1362d80704e0a31.jpg)  
图1各阶次的FRFT波形

![](images/a0adb486eabef57ebfa45a206f26d3b138f1e35bbc6ba44c671c665bf5409f97.jpg)  
Fig.1FRFT waveform of each order   
图2最佳阶次的FRFT波形Fig.2FRFT waveform of optimal order

由式（7）可以看出，信号在时域上的时延变换到分数域上表现为信号幅度谱平移 $\tau { \cos } \alpha$ 。只要获得时延信号在分数域上幅度谱的位置偏移量就可以获得对时延的估计：

$$
\hat { \tau } { = } | \hat { u } _ { s } - \hat { u } _ { r } | / \cos { \alpha }
$$

其中： $\hat { u } _ { s } = \arg \operatorname* { m a x } _ { u } ( F ^ { P } ( s ( t ) ) )$ ，为探测信号的峰值位置；ü =arg max(FP(r(t))，为接收信号的峰值位置。根据分数阶傅里叶变换的线性特性，则有

$$
\begin{array} { l } { { F ^ { P } [ a s ( t - \tau ) ] = a F ^ { P } [ s ( t - \tau ) ] = } } \\ { { a e ^ { j ( \tau ^ { 2 } / 2 ) \sin \alpha \cos \alpha } e ^ { - j u \tau \sin \alpha } f _ { p } ( u - \tau \cos \alpha ) } } \end{array}
$$

对两边取绝对值，得

$$
\begin{array} { r } { \left| F ^ { P } [ a s ( t - \tau ) ] \right| { = } \left| a f _ { p } ( u - \tau \cos \alpha ) \right| { = } \left| a \right| \left| f _ { p } ( u - \tau \cos \alpha ) \right| } \end{array}
$$

同样，由式（10）可以看出，多径信号的幅值变换到分数域上相当于在探测信号的分数域峰值上乘以其幅值，只要获得多径信号在分数域上的峰值和探测信号在分数域的峰值的比例，就可以获得对多径信号幅度的估计：

$$
\hat { a } = \frac { \operatorname* { m a x } ( | F ^ { P } ( r ( t ) ) | ) } { \operatorname* { m a x } ( | F ^ { p } ( s ( t ) ) | ) }
$$

假设接收到的信号为来自单一路径的信号，利用基本的分数阶傅里叶变换算法可以较为精确地对多径时延和幅度进行估计。然而对于实际的传播环境，接收信号为来自各条路径的多分量信号的叠加，各路径分量会不可避免的对彼此产生影响，基本的分数阶傅里叶变换时延估计算法未考虑到路径之间的相互影响，信道估计的精度会受到路径分量的影响。

# 3 改进的FRFT多径时延估计算法

经过多径信道的传播后，接收信号为来自各条路径的多分量信号的叠加，各路径分量会不可避免的对彼此产生影响。受信号分离理论思想的启发，在信道估计中，可以对各路径信号按照能量大小进行依次剥离进而消除高能量信号对其他路径分量估计的影响，本文改进了一种按照多径分量能量大小依次消除的 FRTDE（multipath components are eliminated inorderofenergy-basedFRTDE,MCEE-FRTDE）。

接收信号 $r ( t )$ 在时间段 $\mathrm { [ T _ { s t a r t } , T _ { e n d } ] }$ 上包含第 $m$ 条多径的持续时间[Tmstart,Tmend]。假设接收信号中第 $n$ 条信号分量的幅度 $\scriptstyle a _ { n }$ 最大，式（2）可改写为

$$
r ( t ) = s _ { n } ( t ) + \sum _ { m = 1 , m \ne n } ^ { M } s _ { m } ( t ) + e ( t )
$$

# 3.1多径分量消除方法

多径分量消除方法的思想是：首先通过FRFT算法估计出接收信号中能量最强的信号的时延和幅度，重建该多径分量；然后根据Chirp信号的匹配滤波特性找出该分量在接收信号中的具体位置；最后从接收信号的对应位置将其减去，直至接收信号中无多径分量为止。

基于上一节的讨论，可以通过式（13）和（14）求出第 $n$ 条分量信号对应的时延和幅度：

$$
\hat { \tau } _ { n } = \vert \hat { u } _ { s } - \hat { u } _ { r } \vert / \cos \alpha
$$

$$
\hat { a } _ { n } = \frac { \operatorname* { m a x } ( F ^ { P } ( r ( t ) ) ) } { \operatorname* { m a x } ( F ^ { P } ( s ( t ) ) ) }
$$

根据 $\hat { \tau } _ { n }$ 和 $\hat { a } _ { n }$ 重建第 $n$ 条信号分量 $s _ { n } ( t )$ ：

$$
s _ { n } ( t ) = \hat { a } _ { n } s ( t - \hat { \tau } _ { n } )
$$

根据Chirp信号的匹配滤波特性， $s _ { n } ( t )$ 的共轭信号与 $r ( t )$ 的匹配输出为一个脉冲压缩信号，由脉冲压缩信号的最大值所在位置可求出 $s _ { n } ( t )$ 在 $r ( t )$ 中存在的具体位置。

$$
r _ { o } ( t ) = r ( t ) * s ^ { * } { } _ { n } ( t ) = \intop _ { - \infty } ^ { \infty } s _ { n } ( t - \tau ) s ^ { * } { } _ { n } ( \tau ) d \tau +
$$

$$
\sum _ { m = 1 , m \neq n } ^ { M } \int _ { - \infty } ^ { \infty } s _ { m } ( t - \tau ) s ^ { * } { } _ { n } ( \tau ) d \tau + \int _ { - \infty } ^ { \infty } e ( t - \tau ) s ^ { * } { } _ { n } ( \tau ) d \tau
$$

类似于文献[15],上式右边第一项为匹配输出，可表示为

$$
\begin{array} { l } { { \displaystyle \int \displaylimits _ { - \infty } ^ { \infty } s _ { n } ( t - \tau ) s _ { n } ^ { * } ( \tau ) d \tau = } } \\ { { \displaystyle T \Lambda ( ( t - \tau _ { n } ) / T ) \sin c [ \pi k T ( t - \tau _ { n } ) \Lambda ( ( t - \tau _ { n } ) / T ) ] e ^ { j 2 \pi f _ { c } ( t - \tau _ { n } ) } } } \end{array}
$$

其中: $\Lambda ( t )$ 为定义在[-1,1]上的正三角脉冲函数，在[-1,0]上从0线性增长到1，在[0,1]上从1线性减小到0。式（16）中的第二项为能量较弱的分量的非匹配输出，视为干扰。

结合Chirp信号在FRFT域的峰值汇聚特性和时域的脉冲压缩特性，能够从式（12）中将分量 $s _ { n } ( t )$ 与其他分量分离，在式（16)中的第一项即被移除，在分离能量次强的分量时，便没有了 $s _ { n } ( t )$ 残余能量的干扰。

# 3.2MCEE-FRTDE算法

MCEE-FRTDE算法将同时应用Chirp信号在FRFT域的峰值汇聚特性和时域的脉冲压缩特性对多径时延进行估计。

MCEE-FRTDE以迭代方式进行，按多径分量的能量大小依次返回多径分量的估计值，每次返回多径分量估计值时，对该分量进行重建，同时在残余信号减去当前分量以更新残余信号，下一次迭代时则没有了强分量信号的干扰，迭代结束条件为残余信号的最佳阶次的FRFT不再具有尖峰特性，此理论依据为2.2节中提到的Chirp信号和高斯白噪声在FRFT域的特性；同理，脉冲干扰在频谱的特征类似于高斯白噪声，也不会在任何阶次产生能量汇聚。在每次迭代中，包含子迭代以准确的判定当前分量的多径参数和其在残余信号中的具体位置。多径分量和残余信号中的示意图如图3所示。在子迭代中，通过Chirp 信号的匹配滤波特性来找到当前分量在残余信号中所处的具体位置，然后对当前分量所处的信号段再次做FRFT以估计当前分量参数，迭代结束条件为两次估计的时延和幅度相差小于一个极小量，即认为估计值稳定。

![](images/6ba2dcd43b4766c3eb007825aee8c833e509916a96c55d3871f0e70d96484f1a.jpg)  
图3当前分量与残余信号示意图

Fig.3Diagram of current component and residual signal基于以上的分析，MCEE-FRTDE 算法具体步骤如下：输入：探测信号 $s ( t )$ ；接收信号 $r ( t )$ ；可接受误差小量 $\varepsilon _ { 1 }$ ，$ { \varepsilon } _ { 2 }$ 。

初始化：残余信号 $r _ { e } ( t ) = r ( t )$ ，迭代索引 $n = 1$ ·

a）分别对 $s ( t )$ 和 $r _ { e } ( t )$ 做最佳阶傅里叶变换$\mathrm { ~  ~ { ~ \big ~ ( ~ } ~ } p = - \frac { \arctan ( 1 / k ) } { \pi / 2 } \mathrm { ~  ~ { ~ \big ~ ) ~ } ~ } _ { \circ }$ （204号

b）通过式（13）和（14）分别求出第 $n$ 个分量信号的 $\hat { \tau } _ { n }$ 和 $\hat { a } _ { n }$ 。

c）根据 $\hat { \tau } _ { n }$ 、 $\hat { a } _ { n }$ 和式（15）重建信号 $s _ { n } ( t )$ 。

d）计算 $s _ { n } ( t )$ 的共轭信号与 $r _ { e } ( t )$ 的卷积、 $s _ { n } ( t )$ 的共轭信号与自身的卷积，得到 $s _ { n } ( t )$ 在 $r _ { e } ( t )$ 中存在的具体位置，记为 $i$ 0

$$
i = \lvert i _ { s \operatorname* { m a x } } - i _ { r \operatorname* { m a x } } \lvert
$$

其中：

$$
i _ { s \mathrm { m a x } } = \arg \operatorname* { m a x } _ { t } ( s _ { n } ^ { \ast } ( t ) \ast s _ { n } ( t ) )
$$

$$
i _ { \mathrm { r m a x } } = \arg \operatorname* { m a x } _ { t } ( s _ { n } ^ { \ast } ( t ) \ast r _ { e } ( t ) )
$$

e）重新对搜索出来的信号段 $r _ { e } [ i : i + T ]$ 做最佳阶次的FRFT，获得一组新的 $\hat { \tau } _ { n } ^ { * }$ 和 $\hat { a } _ { n } ^ { * }$ 。

f)令 $\triangle \tau _ { n } = \rvert \hat { \tau } _ { n } ^ { * } - \hat { \tau } _ { n } \rvert$ ， $\triangle a _ { n } = \left| \hat { a } _ { n } ^ { \prime } - \hat { a } _ { n } \right|$ 。如果 $\triangle \tau _ { n } > \varepsilon _ { 1 }$ 或者 $\triangle a _ { n } > \varepsilon _ { 2 }$ ，令 $\hat { \tau } _ { n } = \hat { \tau } _ { n } ^ { \prime }$ ， $\hat { a } _ { n } = \hat { a } _ { n } ^ { * }$ ，并重复步骤 $\mathbf { c } ) { \sim } \mathbf { e } )$ ；否则，进入下一步。

g）更新残余信号的信号段 $r _ { e } [ i : i + T ]$ ：

$$
r _ { e } [ i : i + T ] = r _ { e } [ i : i + T ] - s _ { n } ( t )
$$

h）对 $r _ { e } ( t )$ 做最佳阶次的FRFT，如果不再有尖峰，即多径分量分离完毕，则停止迭代；否则，令 $n = n + 1$ ，从步骤b)开始重复以上步骤。

输出：多径时延参数估计值 $\left\{ \hat { \tau } _ { n } \right\} _ { n = 1 } ^ { M }$ 。

从MCEE-FRTDE算法的具体步骤可知，其时延分辨率主要取决于Chirp信号匹配滤波的时延分辨率和最佳阶傅里叶变换的时延分辨率,对多径分量进行消除的目的是减少干

扰，使得时延估计结果更加准确。由文献[16]可知，匹配滤波和最佳阶傅里叶变换的时延分辨率都约为1/B，所以MCEE-FRTDE算法的时延分辨率也为1/B。

# 4 仿真结果及性能分析

Chirp 探测信号的仿真参数如表1所示。功率时延分布一般服从指数分布[17]，可通过这一性质拟定信道模型参数，根据功率时延分布的特点拟定的信道模型参数（表2)，过采样因子为5。每次仿真都在信道上附加一定SNR的高斯白噪声和随机脉冲干扰，脉冲干扰出现的概率为0.1，信噪比服从[-20dB,0dB]之间的均匀分布。采用500 次MonteCarlo仿真的平均来得到多径信道时延估计的归一化均方误差（normalized mean square error,NMSE)。NMSE 由式（22）计算。

$$
N M S E = [ \frac { \displaystyle \sum _ { \mathrm { n = 1 } } ^ { M } \big | \hat { \tau } _ { n } - \hat { \tau } _ { n } \big | ^ { 2 } } { \displaystyle \sum _ { n = 1 } ^ { M } \big | \hat { \tau } _ { n } \big | } ]
$$

Table 1 Parameters of Chirp detection signal   
表2拟定的信道模型参数  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>Ts</td><td>1.024 us</td></tr><tr><td>fe</td><td>490 MHz</td></tr><tr><td>B</td><td>100 MHz</td></tr></table></body></html>

表1Chirp 探测信号的参数  
Table 2Parameters of proposed channel model   

<html><body><table><tr><td>路径</td><td>时延/ns</td><td>幅度/dB</td></tr><tr><td>1</td><td>0</td><td>0</td></tr><tr><td>2</td><td>30</td><td>-1</td></tr><tr><td>3</td><td>100</td><td>-3.3</td></tr><tr><td>4</td><td>170</td><td>-5.6</td></tr><tr><td>5</td><td>240</td><td>-7.9</td></tr></table></body></html>

为了更好地对改进算法的性能作出评价，本文将MCEE-FRTDE算法和DC算法、FRTDE算法以及SFRTDE算法进行分析比较。图4为几种算法估计时延的归一化均方误差与信噪比的关系。总体而言，各种算法的性能都随信噪比的增加而变得越来越好。在图4中，DC算法的性能最差，因DC算法对噪声较为敏感，特别是在低信噪比的时候，因噪声强度较大，其估计准确度受到较大影响；SFRTDE 算法利用信号FRFT输出峰值的相位信息来搜索匹配的时延，比FRTDE算法直接利用峰值信息具有更高的时延估计精度；MCEE-FRTDE算法考虑到了各路径分量之间的相互影响，并且还通过迭代使得FRFT长度能够自适应地调整，最终达到目标分量的起始位置。相比以上算法，MCEE-FRTDE 算法能够更准确对时延进行估计。

利用MCEE-FRTDE算法估计得到的多径信道参数，可以将多尺度多时延的源信号恢复出来。如图5所示，由上到下显示的分别是源信号、加噪声（ $\mathrm { S N R } { = } 1 \mathrm { d B }$ ）的接收信号，以及用多径信道参数估计值重构出来的源信号与源信号的比较。可以看到重构的源信号与源信号比较吻合，再次说明了改进算法的准确性。

为了评估MCEE-FRTDE算法的计算复杂度和实用性，需要对算法进行时间复杂度的对比。假设信号向量长度都为N，MCEE-FRTDE算法中的步骤a)需要进行两次FRFT，复杂度为 $2 O ( N \log N ) { = } O ( N \log N )$ ；步骤d)需要进行两次卷积运算，直接卷积的复杂度为 $O ( N ^ { 2 } )$ ，可通过卷积定理减少其时间复杂度，一次卷积计算需要两次FFT、一次IFFT和一次乘法运算，所以步骤d)的复杂度为 $2 ( 3 O ( N \log N ) + O ( N ) ) = O ( N \log N )$ ·步骤e)和h)需要进行一次FRFT，复杂度 $O ( N \log N )$ 。综上，MCEE-FRTDE算法的时间复杂度为 $O ( N \log N )$ 。DC 算法需要两次FFT、一次IFFT和一次除法运算，然后进行峰值搜索；FRTDE和SFRTDE均只需要进行两次FRFT，然后进行峰值搜索，所以解卷积算法、FRTDE和SFRTDE的算法复杂度也都为 $O ( N \log N )$ ，与MCEE-FRTDE 算法的复杂度是相当的。虽然上述各种算法的时间复杂度相当，但是因为MCEE-FRTDE存在迭代以优化估计出来的参数值，其仿真运行时间高于其他算法，所以其在运行效率方面仍有改进的空间。

![](images/085d91f71ebb34f71d519da7dbd9a2b41ca96fb2b3a777d4f1bef79a347c7593.jpg)  
图4时延估计的归一化均方误差与信噪比的关系  
Fig.4Relationship between NMSE of time delay estimation and SNR   
图5多尺度多时延源信号的恢复  
Fig.5Recovery of multi-scale and multi-delay source signal

/M 源信号  
理  
-2  
0 100 200 300 400 500 600 700采样点  
5加噪声的接收信号  
Hwww  
-5  
0 100 200 300 400 500 600 700采样点  
2  
度 WMMWWM 信源信号  
理  
-2  
0 100 200 300 400 500 600 700采样点

# 5 结束语

本文改进了一种按照多径分量能量大小依次消除的新方法MCEE-FRTDE。在该方法中，利用FRFT对Chirp信号的汇聚特性，以迭代的方式，按照路径能量从大到小的顺序将多径分量的位置及参数估计出来，并从接收信号中分离。与DC,FRTDE和SFRTDE相比，所提出的时延估计方法可以为Chirp信号提供更好的时延估计结果，但同时也增加了测量系统对其进行处理的时间。在实际进行信道测量的过程中，一般都是对接收端信息进行离线处理，对算法的实时性要求不高。综合算法的估计精度、时间复杂度和系统要求来说，MCEE-FRTDE算法具有很好的性能。

# 参考文献：

[1]Othman MAB,Belz J,Farhang-Boroujeny B.Performance analysis of

matched filter bank for detection of linear Chirp signals [J].IEEE Trans on Aerospace & Electronic Systems,2017,53(1): 41-51.   
[2]Vangelista L.Frequency shift Chirp modulation:the LoRa modulation [J].IEEE Signal Processing Letters,2017,24(12): 1818-1821.   
[3]Yuan Fei,Wei Qian，Cheng En.Joint virtual timereversal communications with an orthogonal chirp spread spectrum over underwater acoustic channel [J].Applied Acoustics，2017，117: 122-131.   
[4]Dezfooliyan A,Weiner A M. Evaluation of time domain propagation measurements of UWB systems using spread spectrum channel sounding [J].IEEE Trans on Antennas and Propagation,2012,60 (10): 4855-4865.   
[5]Xiao Yongxin.A matched filtering with Chirp scaling SAR processing algorithm[J].Journal of Remote Sensing,1998,2(1): 37-41.   
[6]MarJ,Lin YR,Yeh Y C.Ultra-wide bandwidth in-vehicle channel measurements using chirp pulse sounding signal [J].IET Science, Measurement & Technology,2009,3(4):271-278.   
[7]Yu Xiaohui,Shi Yaowu,Ma Yan.A cross fourth order moment minimum norm method for Chirp time delay estimation [C]// Proc of International Conference on Mechatronics & Automation. Changchun, China: IEEE Press,2009:9-12.   
[8]Ozaktas H M,Arikan O,Kutay MA,et al.Digital computation of the fractional Fourier transform [J].IEEE Trans on Signal Processing,1996, 44 (9): 2141-2150.   
[9]Tao Ran,Li Xuemei,Li Yanlei,et al.Time-delay estimation of Chirp signals in the fractional Fourier domain [J].IEEE Trans on Signal Processing,2009,57(7): 2852-2855.   
[10] Zhou Tian,Li Haisen,Zhu Jianjun,et al. Subsample time delay estimation of Chirp signals using FrFT[J]. Signal Processing,2014,96 (5): 110-117.   
[11] Sejdic E,Djurovic I, Stankovic L J.Fractional Fourier transform as a signal processing tool: an overview of recent developments [J]. Signal Processing,2011,91 (6):1351-1369.   
[12] Almeida L.The fractional Fourier transform and time-frequency representations [J].IEEE Trans on Signal Processing,1994,42 (11): 3084-3091.   
[13] Capus C,Brown K.Short-time fractional Fourier methods for the time-frequency representation of chirp signals [J]. The Journal of the Acoustical Society of America,2003,113 (6):3253-3263.   
[14]田达．非平稳信号阵列多参量估计技术研究[D]．成都：电子科技 大学，2O04.(Tian Da.Research on multi-parameter estimation technology for non-stationary signal array [D]. Chengdu: University of Electronic Science and Technology,2004.)   
[15] Hein A. Processing of SAR data: fundamentals,signal processing, interferometry [M].[S.1.] : Springer Publishing Company,2010.   
[16]李昕，李良光，姜媛媛．基于DFRFT的脉压方法及与匹配滤波性能 对比[J].计算机工程与应用，2012,48(11):16-21.(Li Xin,Li Liangguang,Jiang Yuanyuan.Pulse compression method based on DFRFT and its performance comparison with matched filtering [J]. Computer Engineering and Application,2012,48(11):16-21.)   
[17] Schniter P,Albornoz JM,Albornoz JM,et al.A wideband channel sounder by [D].Columbus:The Ohio State University, 2001.