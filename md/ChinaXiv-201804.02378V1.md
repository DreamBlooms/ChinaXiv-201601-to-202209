# 基于脉冲成形扩频信号伪码周期盲估计\*

李群，张天骐，袁帅(重庆邮电大学 信号与信息处理重庆市重点实验室，重庆 400065)

摘要：针对基带扩频信号的频谱范围较宽，信号在带限的信道中传输时需要对信号进行带宽限制，从而会造成码间干扰和频谱泄露的问题，将基带扩频信号通过脉冲成形器后对其主要参数的抗截获性能进行了研究，并使用两次功率谱的方法对该类信号的伪码周期进行了估计。理论分析证明，做两次功率谱以后的信号以脉冲串的周期来扩展谱线，且信号主要能量将会聚集在一些类似于基带成形脉冲二次谱形状的尖锐脉冲处，通过测量这些尖锐脉冲间的间距即可以估计出基带扩频信号的伪码周期。计算机仿真结果证明，两次功率谱的方法可以在低信噪比的条件下实现对带脉冲成形基带扩频信号伪码周期的估计，且本文算法对伪码周期估计的正确率比文献[1]算法约提高7dB左右。

关键词：扩频信号；脉冲成形；二次功率谱；伪码周期；盲估计 中图分类号：TN911.7 doi: 10.3969/j.issn.1001-3695.2018.02.0106

# Blind Period estimation of PN sequence based on pulse shaping of spectrum signal

Li Qun, Zhang Tianqi, Yuan Shuai (Chongqng KeyLaboratory of Signal& Information Processing,Chongqing Universityof Posts &Telecommunications, Chongqing 400065, China)

Abstract: The spectrumof thebaseband spread spectrum signal has awide frequencyrange,when thesignal is transmite the spectrumofthebasebandspread spectrumsignal hasa wide frequencyrange,when thesignal is tansmited intheband limited channel,thebandwidthofthesignalneedstobelimited,therebycausing intersymbolinterference.Therefore,inordertoreduce theinter-symbol crostalk between baseband spread spectrum signals and theiroccupiedbandwidth,this paper sdudythe main parameters ofits low interception performanceofthe baseband spread spectrum signal after it pases through the pulse shaper. And pseudocodeperiodhas been estimatedbyusing twice power spectrum.The theoreticalanalysis proves thatthesignalafter twice powerspectrumextends spectrallineon theperiodofimpulsesequence,and themainenergyofthe signal willgatherin some sharpnessimilartothatofthe quadratic spectrumofte baseband shaping pulse.Thepseudo-code periodofthebaseband spread spectrum signal can be estimated by measuring the spacing between these sharp pulses. Computer simulation esults showthat the methodoftwice power spectrum can beusedto estimate the pseudo-code periodof pulse shaped spread baseband signalunderlowsignal-to-noiseratiocondition.Andaccuracyofthe algorithmto estimate the pseudo-codeperiod proposed in this paper improves approximately 7dB compared to the method without pulse shaping.

Key words:spread spectrum signal; pulse shaping; power spectrum reprocessng; PN sequence period; blind estimation

# 0 引言

非合作通信中，对直接序列扩频信号的各项参数以及码序列进行准确的估计有着重要的现实意义和应用价值。

直接序列扩频（direct sequence spread spectrum，DSSS）通信具有频谱宽、功率谱密度低、隐蔽性好、保密性及抗干扰能力强等诸多特点，可以工作在低信噪比环境中，所以它在现代民事通信和军事通信中都得到了极为广泛的应用[2]。因此，在

目前，研究人员已经对基带DSSS信号扩频码序列和参数估计做了大量的研究，特别是短码基带扩频信号参数的盲估计。但是，在已有参数和码序列估计的文献中，研究者们为了简化计算和分析，文中所使用的扩频码传输波形皆为切普脉冲所携带。如文献[1]中第一次提出二次谱的方法，即将信号做两次功率谱处理，然后在伪码周期的整数倍得到等间隔峰值谱线去估计直扩信号的伪码周期；文献[3]中使用二次功率谱的方法估计了多径环境下多速率直扩码分多址信号的伪码周期；文献[4]中使用波动相关法结合自相关二阶矩的方法估计信号的伪码周期；文献[5]将四阶累积量和特征值分解相结合的方法估计信号的伪码周期和载波频率；文献[6]提出一种延时相乘相关熵的估计新方法，即利用相关熵可随度量随机过程局部相似的特点，计算相关熵峰值间隔即可估计出扩频码的伪码周期；文献[7]中使用倒谱法将接收到的信号做功率谱运算以后对信号取对数再做功率谱运算的方法估计扩频信号的伪码周期；文献[8]中在已知伪码周期和码片速率的前提下，用两倍伪码周期对信号进行分段，然后使用奇异值分解的方法估计出基带直扩信号的伪码序列；文献[9]使用二阶矩的方法实现伪码周期的估计;文献[10]使用相关检测法实现扩频码周期以及码速率的估计;文献［11］中使用K-means无聚类的方法实现基带扩频码序列的估计;文献[12]在文献[2]的基础上先估计直扩信号的伪码周期，然后再结合矩阵特征值分解的方法对带有强干扰的基带直扩信号的伪码序列进行估计;文献[13]使用LEAP神经网络的方法估计同步多用户直扩信号伪码序列盲估计。由于切普脉冲在通过带限信道时会在时间上进行扩展，将每个符号脉冲扩展到相邻符号的码元内，这就会造成码间串扰和频谱泄露，并导致截获错误概率增大。因此，它在实际的扩频通信系统并不适用，而脉冲成形技术可以在减少基带扩频信号的占用带宽的同时抑制码间串扰，从而提高基带扩频信号伪码序列恢复的准确性，故而对其它脉冲成形技术的扩频信号的主要参数进行检测和估计是非合作通信系统研究中的关键问题，具有重要的现实意义和应用价值。

针对上述存在的问题，本文将基带扩频信号通过脉冲成形器后对其主要参数分析其低截获性能，并使用两次功率谱的方法对该类信号的伪码周期进行了估计。理论分析证明，做两次功率谱以后的信号以脉冲串的周期来扩展谱线，且信号主要能量将会聚集在一些类似于基带成形脉冲二次谱图形的尖锐脉冲处，通过测量这些尖锐脉冲间的间距即可以估计出基带扩频信号的伪码周期。

# 1 信号模型

设传输脉冲波形 $p ( t )$ 由长度为 $N$ 的 $m$ 序列 $p ( n )$ 生成，则 其表达式为

$$
p ( t ) = \sum _ { j = - \infty } ^ { N - 1 } p _ { j } g ( t - j T _ { c } )
$$

其中： $g ( t )$ 为归一化成形脉冲， $p _ { i } \in \{ - 1 , + 1 \}$ 为长度为 $N$ 的扩频序列， $T _ { c }$ 为码片宽度。若 $p ( t )$ 包含 $N$ 个脉冲，则每个码片宽度内只含有一个脉冲，即 ${ T _ { e } = T _ { c } }$ 。本文采用的带脉冲成形扩频信号如图1所示，其中信息码 $m ( t )$ 经过下采样后将得到离散信号以每符号比特对一个周期 $p ( n )$ 进行扩频调制，则经过脉冲成形

器后的输出信号为

$$
\begin{array} { c l } { { s ( t ) = \sqrt { \gamma _ { c } } \displaystyle \sum _ { i = - \infty } ^ { \infty } \displaystyle \sum _ { j = 0 } ^ { N - 1 } m _ { i } p _ { j } g ( t - i T _ { 0 } - j T _ { e } ) } } & { { = } } \\ { { \sqrt { \gamma _ { c } } \displaystyle \sum _ { k = - \infty } ^ { \infty } d _ { k } g ( t - k T _ { e } ) } } & { { } } \end{array}
$$

其中: ${ \mathfrak { m } } _ { \mathrm { i } } \in \{ + 1 , - 1 \}$ 为信息码序列； $T _ { e }$ 为帧长， $\sqrt { \gamma _ { c } }$ 为每个传输脉冲的能量， $T _ { 0 } = N T _ { e }$ 为 $N$ 个脉冲串调制的信息符号周期， $d _ { k }$ 为扩频以后的新序列。

将基带信号 $s ( t )$ 经过零均值、方差为 $\delta _ { n } ^ { 2 }$ 高斯白噪声信道后混叠了干扰噪声，则得到的含噪基带DSSS信号表达式为

$$
x ( t ) = s ( t ) + n ( t )
$$

其中: $n ( t )$ 为高斯白噪声,且与信号 $s ( t )$ 与噪声 $n ( t )$ 在概率统计上相互独立。

![](images/58aae9077e6c2409fe4b1a2c1254be3d3b633d88eb1ab116947a6ad3dce5ce8f.jpg)  
图1信号产生系统模型

# 2 扩频理论分析

将扩频信号经过脉冲成形滤波器后使得信号波形滑，调制信号频谱带外衰减加快，从而减少码间串扰。因此本文选择无线通信中常用到的升余弦滤波器、平方根升余弦滤波器、高斯脉冲滤波器以及三角脉冲滤波器等为载体脉冲信号来分析带脉冲成形基带扩频信号的主要参数，并使用二次功率谱的方法去估计信号的伪码周期。

# 2.1成形脉冲信号功率谱和二次谱分析

所谓二次谱，顾名思义就是将接收机接收到的基带信号做两次功率谱处理，即将信号的功率谱作为输入信号再做傅里叶变换取模平方处理，从而得到基带信号的二次功率谱。周期图法和相关图法是求求功率谱的两种经典方法，周期图法直接对信号做傅里叶变换，而相关图法则先对信号做自相关运算，再对其做傅里叶变换得到功率谱，本文则采用相关图法对信号的参数进行分析处理。由于做两次功率谱处理后的基带DSSS信号在伪码周期的整数倍显示出了PN 码序列伪码周期的特征，所以这里从 $x ( t )$ 的相关函数入手研究其功率谱，即

$$
R _ { x } ( \tau ) = \gamma _ { c } E \big \{ [ s ^ { * } ( \mathrm { t } ) + n ^ { * } ( t ) ] [ s ( t + \tau ) + n ( t ) ] \big \} =
$$

$$
\gamma _ { c } \Big [ R _ { \mathrm { s } } ( \tau ) + \sigma _ { \ n } ^ { 2 } \delta ( \tau ) \Big ]
$$

其中： $R _ { s } ( \tau ) = R _ { m } ( \tau ) \cdot R _ { _ p } ( \tau ) \cdot R _ { _ g } ( \tau )$ 由三个不相关的部分组成，即信息码的自相关函数、扩频码的自相关函数和基带成形脉冲函数的自相关函数。这里有用基带DSSS信号 $s ( t )$ 和噪声 $n ( t )$ 相互独立，即 $\mathbb { E } \Big \{ s ^ { * } ( \mathrm { t } ) n ( t ) \Big \}$ 和 ${ \mathrm { E } } { \left\{ s ( { \mathrm { t } } + \tau ) n ^ { * } ( t ) \right\} }$ 等于零。从(5)式可以看出，信号 $x ( t )$ 是有用的基带DSSS信号 $s ( t )$ 的自相关函数 $R _ { \mathrm { s } } ( \tau )$ 与噪声自相关函数之和，由于相关函数与功率谱是一对傅里叶变换对，故求出有用基带DSSS信号 $s ( t )$ 的自相关函数 $R _ { \mathrm { s } } ( \tau )$ 就能计算出信号 $x ( t )$ 的自相关函数及功率谱。由于上式所示的基带DSSS信号 $s ( t )$ 是广义平稳的，则令其子脉冲 $T _ { x }$ 的起点随机化， $T _ { x }$ 是在 $[ 0 , T _ { e } ]$ 上均匀分布的随机时延,于是 $s ( t )$ 的平稳随机过程形式为

$$
s ( t - T _ { x } ) = \sum _ { k = - \infty } ^ { \infty } d _ { k } g ( t - k T _ { c } - T _ { x } )
$$

并有 $s ( t )$ 的自相关函数表示为

$$
\begin{array} { c } { { ( \tau ) = E \Big \{ \displaystyle \hat { s } ^ { * } ( t - T _ { x } ) s ( t + \tau - T _ { x } ) \Big \} = } } \\ { { { } } } \\ { { E \displaystyle \{ \displaystyle \sum _ { k = - \lambda \wedge \alpha  k \atop n = - \alpha } ^ { \infty } d _ { k } d _ { \hphantom { * } k } ^ { * } g ( t - k T _ { e } - T _ { x } + \tau ) g ^ { * } ( t - h T _ { e } - T _ { x } ) \} = } } \\ { { { \displaystyle \sum _ { m = - \alpha } ^ { \infty } E \Big [ \displaystyle \hat { d } _ { k } d _ { \hphantom { * } k + m } \Big ] \displaystyle \sum _ { k = - \infty } ^ { \infty } E \Big [ g ( t - k T _ { e } - T _ { x } + \tau ) * } } } \\ { { { } } } \\ { { g ^ { * } \Big ( t - \big ( k + m \big ) T _ { e } - T _ { x } \Big ) \Big ] } } \end{array}
$$

其中：

$$
\begin{array} { l } { { \displaystyle \sum _ { k = - \infty } ^ { \infty } E \Big [ g ( t - k T _ { e } - T _ { x } + \tau ) g ^ { * } \big ( t - ( k + m ) T _ { e } - T _ { x } \big ) \Big ] = } } \\ { { \displaystyle \sum _ { k = - \infty } ^ { \infty } \frac { 1 } { T _ { e } } \int _ { 0 } ^ { T _ { e } } g ( t - k T _ { e } - T _ { x } + \tau ) g ^ { * } \big ( t - \big ( k + m \big ) T _ { e } - T _ { x } \big ) = } } \\ { { \displaystyle \sum _ { h = - \infty } ^ { \infty } \frac { 1 } { T _ { e } } \int _ { t + h T _ { e } } ^ { t + ( h + 1 ) T _ { e } } g ( \xi + \tau ) g ^ { * } \big ( \xi - m T _ { e } \big ) d \xi = } } \end{array}
$$

$$
\frac { 1 } { T _ { e } } \int _ { - \infty } ^ { \infty } g ( \xi + \tau ) g ^ { * } \big ( ( \xi - m T _ { e } \big ) d \xi
$$

即 $s ( t )$ 的自相关函数可以表示为

$$
R _ { s } ( \tau ) = E { \left\{ s ^ { * } ( t - T _ { x } ) s ( t + \tau - T _ { x } ) \right\} } =
$$

$$
\frac { 1 } { T _ { e } } \sum _ { m = - \infty } ^ { \infty } R _ { d } ( m ) \int _ { - \infty } ^ { \infty } g ( \xi + \tau ) g ^ { * } ( \xi - m T _ { e } ) d \xi
$$

其中： $R _ { d } ( m )$ 表示新序列d的自相关函数。

因 $R _ { \mathrm { s } } ( \tau )$ 与变量时间/无关，将式(8)做傅里叶变换可以获得基带DSSS信号的功率谱为

$$
P _ { \mathrm { s } } ( f ) = \frac { \left| P _ { g } ( f ) \right| ^ { 2 } } { T _ { e } } P _ { d } ( f )
$$

其中： $\left| P _ { g } ( f ) \right| ^ { 2 }$ 是脉冲函数 $g ( t )$ 的能量谱密度； $P _ { d } ( f )$ 为序列 $d$ 的功率谱密度，即得到的基带 DSSS 信号的功率谱由基带成形脉冲的能量谱 $\left| P _ { g } ( f ) \right| ^ { 2 }$ 和扩频序列的功率谱 $P _ { d } ( f )$ 共同决定，由于脉冲函数 $g ( t )$ 的能量谱密度和扩频序列 $d$ 的功率谱都反映了信号在频域的分布情况，这里我们将信号 $s ( t )$ 的功率谱 $P _ { \mathrm { s } } ( f )$ 作为输入信号再对信号在做傅里叶变换处理取其模平方以后即得到基带信号 $s ( t )$ 的二次功率谱，即

$$
P _ { s 2 } ( e ) = \frac { 1 } { T _ { c } } F T \left\{ \left| p _ { g } ( f ) \right| ^ { 2 } . \left| p _ { d } ( f ) \right| \right\} =
$$

$$
\frac { 1 } { T _ { c } } F T \left\{ \left| p _ { g } ( f ) \right| ^ { 2 } \right\} \otimes F T \left\{ \left| p _ { d } ( f ) \right| \right\}
$$

其中： $F T \{ \bullet \}$ 表示傅里叶变换，“ $\otimes$ ”表示卷积运算，即将脉冲函数 $g ( t )$ 的能量谱和扩频序列 $d$ 的功率谱做傅里叶变换后得到脉冲函数 $g ( t )$ 的和扩频序列 $d$ 的两次功率谱，再将其做卷积运算即可得到基带信号 $s ( t )$ 的两次功率谱。

下面本文将以高斯滤波器、三角脉冲滤波器、平方根升余弦滤波器、升余弦滤波器为载体来分析带脉冲成形基带扩频信号的功率谱密度以及两次功率谱密度。

a)成形脉冲函数 $\mathbf { g } ( t )$ 为高斯脉冲，其数学表达式为

$$
g ( t ) = \frac { \sqrt { 2 } } { \alpha } \exp ( - \frac { 2 \pi t ^ { 2 } } { \alpha ^ { 2 } } )
$$

将式(10)所表示的脉冲成形函数做傅里叶变换以后取模平方，即 $\mathbf { g } ( t )$ 的能量谱为

$$
\left| P _ { g } ( f ) \right| ^ { 2 } = \exp ( - \alpha ^ { 2 } f ^ { 2 } \pi )
$$

b)成形脉冲函数 $\mathbf { g } ( t )$ 为三角脉冲，其数学表达式为

$$
{ \bf g } ( t ) { = } 1 { - } \frac { { \lvert { \bf t } \rvert } } { T _ { e } } , \qquad { \lvert { \bf t } \rvert } \le T _ { e }
$$

同理可得，三角脉冲函数 $\mathbf { g } ( t )$ 的能量谱

$$
\left| P _ { g } ( f ) \right| ^ { 2 } = \frac { T _ { e } ^ { 2 } } { 4 } \mathrm { s i n } c ^ { 4 } ( \frac { T _ { e } } { 2 } f )
$$

c)成形脉冲函数 $\mathbf { g } ( t )$ 为平方根升余弦脉冲，其数学表达式为

$$
g ( t ) { = } 4 \beta \frac { \cos [ ( 1 + \beta ) \pi t / T _ { c } ] + \sin [ ( 1 - \beta ) \pi t / T _ { c } ] ( 4 \beta t / T _ { c } ) ^ { - 1 } } { \pi \sqrt { T _ { c } } \left[ 1 - 1 6 \beta ^ { 2 } t ^ { 2 } / { T _ { c } ^ { 2 } } \right] }
$$

其中: $\beta \in \left( 0 , 1 \right)$ 为滚降因子。同理可得，平方根升余弦脉冲函数g(t)的能量谱为[14]

$$
\left| P _ { g } \left( f \right) \right| ^ { 2 } = \left\{ \begin{array} { l l } { \displaystyle \mathrm { T } _ { c } , 0 \le \left| \mathbf { f } \right| \le \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } } \\ { \displaystyle \mathrm { 2 } \left[ 1 + \cos \frac { \pi T _ { c } } { \beta } ( \left| f \right| - \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } ) \right] ^ { 2 } , \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } \le \left| \mathbf { f } \right| \le \frac { 1 + \beta } { 2 T _ { \mathrm { c } } } } \\ { \displaystyle 0 , \left| f \right| > \frac { 1 + \beta } { 2 T _ { \mathrm { c } } } } \end{array} \right.
$$

d)成形脉冲函数 $\mathbf { g } ( t )$ 为升余弦脉冲，其数学表达式为

$$
\mathrm { g } ( t ) { = } \frac { \sin \pi t / T _ { c } } { \pi t / T _ { c } } \frac { \cos ( \pi \beta t / T _ { c } ) } { 1 { - } 4 \beta ^ { 2 } t ^ { 2 } / T ^ { 2 } }
$$

同理可得，脉冲函数 $\mathbf { g } ( t )$ 的能量谱为[14]

$$
\left| P _ { g } \left( f \right) \right| ^ { 2 } = \left\{ \begin{array} { l } { \displaystyle \frac { T _ { \mathrm { c } } ^ { 2 } , 0 \le \left| \mathbf { f } \right| \le \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } } { 4 } } \\ { \displaystyle \frac { T _ { \mathrm { c } } ^ { 2 } } { 4 } \Bigg [ 1 + \cos \frac { \pi T _ { c } } { \beta } \big ( \big | f \big | - \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } \big ) \Bigg ] ^ { 2 } , \frac { 1 - \beta } { 2 T _ { \mathrm { c } } } \le \left| \mathbf { f } \right| \le \frac { 1 + \beta } { 2 T _ { \mathrm { c } } } } \\ { 0 , \big | f \big | > \frac { 1 + \beta } { 2 T _ { \mathrm { c } } } } \end{array} \right.
$$

由式(12)(14)(16)(18)可得基带 DSSS 信号能量谱密度再做傅里叶变换可得高斯脉冲、三角脉冲、平方根升余弦脉冲和升余弦脉冲的两次功率谱密度为

$$
p _ { g 2 } ( e 1 ) = F T \left\{ \exp ( - \alpha ^ { 2 } f ^ { 2 } \pi ) \right\} = \frac { 1 } { a } \exp \left[ - \pi \left( \frac { e } { a } \right) ^ { 2 } \right]
$$

$$
p _ { g 2 } ( e 2 ) = F T \left\{ \frac { T c ^ { 2 } } { 4 } \sin c ^ { 4 } \bigg ( \frac { T _ { c } } { 2 } f \bigg ) \right\} \approx \pi ^ { 2 } T _ { c } \left( 1 { - } \frac { \left| \mathrm { e } \right| } { T _ { c } } \right)
$$

$$
p _ { g 2 } ( e 3 ) = F T \left\{ T _ { c } \right\} + F T \left\{ \frac { T _ { c } } { 2 } \left[ 1 + \cos \frac { \pi T _ { c } } { \beta } \left( \left| f \right| - \frac { 1 - \beta } { 2 T _ { c } } \right) \right] \right\} =
$$

$$
S a ( \frac { e } { 2 T _ { c } } ) - e S a ( \frac { e } { 2 T _ { c } } ) . \left\{ - \frac { 1 } { e } \Bigg [ \cos ( \frac { \beta e } { 2 T _ { c } } ) - 1 \Bigg ] \right\} + \frac { - e \cos ( \frac { \beta e } { 2 T _ { c } } ) } { \Bigg ( \frac { \pi T _ { c } } { \beta } \Bigg ) ^ { 2 } - e ^ { 2 } } =
$$

$$
S a { \left( \frac { e } { 2 T _ { \mathrm { { c } } } } \right) } . \mathrm { { c o s } } { \left( \frac { \beta e } { 2 T _ { \mathrm { { c } } } } \right) } { \left( 1 - \left( \frac { \beta e } { \pi T _ { \mathrm { { c } } } } \right) ^ { 2 } \right. }
$$

$$
\begin{array} { r } { p _ { g 2 } ( e 4 ) = F T \left\{ T _ { c } ^ { 2 } \right\} + F T \left\{ \displaystyle \frac { T _ { c } ^ { 2 } } { 4 } \left[ 1 + \cos \displaystyle \frac { \pi T _ { c } } { \beta } \left( \left| f \right| - \displaystyle \frac { 1 - \beta } { 2 T _ { c } } \right) \right] ^ { 2 } \right\} = } \end{array}
$$

$$
\begin{array} { l } { \displaystyle T _ { c } S a ( \frac { e } { 2 T _ { c } } ) - \frac { T _ { c } e } { 2 } S a ( \frac { e } { 2 T _ { c } } ) . } \\ { \displaystyle \left. - \frac { 3 } { 2 e } \left[ \cos ( \frac { \beta e } { 2 T _ { c } } ) - 1 \right] + \frac { - 2 e \cos ( \frac { \beta e } { 2 T _ { c } } ) } { \left( \frac { \pi T _ { c } } { \beta } \right) ^ { 2 } - e ^ { 2 } } + \frac { 1 } { 2 } \frac { \cos ( \frac { \beta e } { 2 T _ { c } } ) - 1 } { \left( \frac { 2 \pi T _ { c } } { \beta } \right) ^ { 2 } - e ^ { 2 } } \right. = } \end{array}
$$

$$
\frac { 3 } { 4 } { T _ { \mathrm { c } } } S a \Bigg ( \frac { e } { 2 T _ { \mathrm { c } } } \Bigg ) . \mathrm { c o s } \Bigg ( \frac { \beta e } { 2 T _ { \mathrm { c } } } \Bigg ) \Bigg / 1 - \frac { 5 } { 4 } \Bigg ( \frac { \beta e } { \pi T _ { \mathrm { c } } } \Bigg ) ^ { 2 } + \frac { 1 } { 4 } \Bigg ( \frac { \beta e } { \pi T _ { \mathrm { c } } } \Bigg ) ^ { 4 }
$$

由式(19)\~(22)可知，脉冲信号做两次功率谱变换后依然具有本脉冲函数的性质，这有利于信号扩频信号在过渡带进行带宽限制，从而减少扩频信号在传输过程中造成的码间串扰和频谱泄露。

# 2.2基带 DSSS 信号一次谱和二功率谱分析

由于信息码 $m ( t )$ 和扩频码 $p ( t )$ 由不同的发射源产生，即它们相互独立，序列 $d$ 的自相关函数等于信息码 $m ( t )$ 自相关函数与扩频码 $m ( t )$ 自相关函数的乘积，即 $R _ { d } ( \tau ) = R _ { _ { p } } ( \tau ) . R _ { _ { m } } ( \tau )$ ，由文献[1]可得序列 $d$ 的功率谱密度为

$$
P _ { d } ( f ) { \approx } \frac { 1 } { N } { \sin } c ^ { 2 } ( { \pi } f T _ { e } ) { \bullet } \sum _ { m = { - \infty } } ^ { \infty } { \delta } ( f - \frac { m } { N T _ { e } } ) { - } \frac { T _ { 0 } } { N } { \sin } c ^ { 2 } ( { \pi } f T _ { 0 } )
$$

由式(23)可知，序列 $d$ 的一次谱分别由离散谱和连续谱两个部分构成，由于连续谱对基带DSSS信号 $s ( t )$ 的伪码周期的估计不会造成太大的影响，因此在计算基带DSSS信号 $s ( t )$ 的二次功率谱时，可以将其省略，即省掉(22)式中的后一项，这里只计算对扩频周期估计有用的离散功率谱密度，即

$$
P _ { d } ^ { \prime } ( f ) { \approx } \frac { 1 } { N } { \sin c ^ { 2 } } ( { \pi f } T _ { e } ) \sum _ { m = - { \infty } } ^ { \infty } { \delta } ( f - \frac { m } { N T _ { e } } )
$$

将式(24)代入式(9)得基带 DSSS 信号 $\mathbf { s } ( t )$ 的功率谱密度为

$$
P _ { s } ( f ) = { \frac { \Big | G ( f ) \Big | ^ { 2 } } { T _ { e } } } P _ { d } ( f ) \approx \left[ { \frac { 1 } { N } } \mathrm { s i n } c ^ { 2 } ( \pi f T _ { e } ) \bullet \right.
$$

$$
\sum _ { m = - \infty } ^ { \infty } \delta ( f - \frac { m } { N T _ { e } } ) \Biggr ] \cdot \left| P _ { g } ( f ) \right| ^ { 2 }
$$

由式(25)可知，基带DSSS信号 $s ( t )$ 功率谱由分别序列 $d$ 的功率谱和成形脉冲函数 $g ( t )$ 的能量密度共同构成，且信号的功率谱密度主要由基带成形脉冲的功率谱形状所决定。则将由式(12)(14)(16)(18)代入式(25)可得基带DSSS 信号的一次谱为

$$
P _ { s } ( f 1 ) = \left[ \frac { 1 } { N } \mathrm { s i n } c ^ { 2 } ( \pi f T _ { e } ) \sum _ { m = - \infty } ^ { \infty } \delta ( f - \frac { m } { N T _ { e } } ) \right] \bullet \frac { 1 } { a } \mathrm { e x p } ( - \alpha ^ { 2 } f ^ { 2 } \pi )
$$

$$
P _ { s } ( f 2 ) = \left[ \frac { 1 } { N } \mathrm { s i n } c ^ { 2 } ( \pi f T _ { e } ) \sum _ { m = - \infty } ^ { \infty } \delta ( f - \frac { m } { N T _ { e } } ) \right] \bullet \frac { T _ { e } ^ { 2 } } { 4 } \mathrm { s i n } c ^ { 4 } ( \frac { T _ { e } } { 2 } f )
$$

$$
P _ { \mathrm { s } } ( f 3 ) { = } \Bigg [ \frac { 1 } { N } { \sin c ^ { 2 } ( \pi f T _ { e } ) } \sum _ { m = - { \infty } } ^ { \infty } { \delta } ( f - \frac { m } { N T _ { e } } ) \Bigg ] .
$$

$$
\frac { T _ { e } } { 2 } \Bigg [ 1 + \cos \frac { \pi T _ { e } } { \beta } ( \left| f \right| - \frac { 1 - \beta } { 2 T _ { e } } ) \Bigg ]
$$

$$
P _ { \mathrm { s } } ( f 4 ) { = } \Bigg [ \frac { 1 } { N } \mathrm { s i n } c ^ { 2 } ( \pi f T _ { e } ) \sum _ { m = - { \infty } } ^ { \infty } { \delta } ( f - \frac { m } { N T _ { e } } ) \Bigg ] .
$$

$$
\frac { T _ { e } ^ { 2 } } { 4 } \Bigg [ 1 + \cos { \frac { \pi T _ { e } } { \beta } ( \left| f \right| - \frac { 1 - \beta } { 2 T _ { e } } ) } \Bigg ] ^ { 2 }
$$

由式(26)\~(29)可知，将DSSS 信号做一次功率谱处理后，信号的功率谱曲线具有脉冲成形函数的功率谱形状，也就是说，信号的一次功率谱的性质主要由脉冲信号决定。则不同基带脉冲成形基带DSSS信号的功率谱密图如图2\~5所示。

![](images/c29acb6cac1f81ea90ed549d990695bf4dbb5f19f97ad56d77ce8b6d490bec89.jpg)  
图2高斯脉冲成形基带DSSS信号的功率谱

![](images/98bddeddc2a8d633435a7b9aaa1a25b0c1d60f166a239af408b3d628541ef62d.jpg)  
图3三角脉冲成形基带DSSS信号的功率谱

![](images/d579974da0fffbf6d774c0efe86c5d8fe08fc509c07b73cc63f0ec96fa4bdc06.jpg)  
图4平方根升余弦脉冲成形基带DSSS信号功率谱

![](images/6e7048da1acda5b297e2d1ab29ef49fc3ae8fd5448f26ea2cb5586e34970f3f7.jpg)  
图5升余弦脉冲成形基带DSSS信号功率谱

将式(23)中的 $p _ { \ d } ^ { \prime } ( f )$ 做傅里叶变换取其模平方以后就可以得到序列 $d$ 的二次谱为

$$
P _ { d 2 } ( e ) = F T \bigl [ p ^ { \prime } { } _ { d } ( f ) \bigr ] \approx T _ { \mathrm { c } } \sum _ { m = - \infty } ^ { \infty } \delta ( e - k N T _ { e } ) \left( \begin{array} { l } { \bigl | e - k N T _ { e } \bigr | \le T _ { e } \vphantom { \biggl | e - k N T _ { e } \bigr | } } \end{array} \right)
$$

故脉冲成形基带扩频信号 $s ( t )$ 的二次功率谱为

$$
P _ { s 2 } ( e ) = \left. F T \Big [ P _ { d 2 } ( e ) \otimes P _ { g 2 } ( e ) \Big ] \right. ^ { 2 } = \Big \{ F T \Big [ P _ { d 2 } ( e ) \Big ] \otimes F T \Big [ P _ { g 2 } ( e ) \Big ] \Big \} ^ { 2 }
$$

其中： $F T \{ \bullet \}$ 表示傅里叶变换，“ $\otimes$ ”表示卷积运算。将式

(19)\~(22)代入式(30)可得成形脉冲分别为高斯脉冲、三角脉冲、平方根升余弦脉冲和升余弦脉冲成形时基带DSSS信号 $s ( t )$ 的二次谱为

$$
P _ { s 2 } ( e 1 ) = \left\{ T _ { \mathrm { e } } \frac { 1 } { a } \mathrm { e x p } \Bigg [ - \pi \Bigg ( \frac { e - k N T _ { e } } { a } \Bigg ) \Bigg ] ^ { 2 } \right\} ^ { 2 }
$$

$$
P _ { s 2 } ( e 2 ) = { \pi ^ { 4 } } { T _ { e } } ^ { 2 } { \left( 1 - { \frac { { \left| { e - k N T _ { e } } \right| } } { T _ { e } } } \right) } ^ { 2 }
$$

$$
P _ { s 2 } ( e ) = \left\{ S \mathrm { a } \Bigg ( \frac { e - k N T _ { e } } { 2 T _ { e } } \Bigg ) . \frac { \mathrm { c o s } \Bigg ( \frac { \beta \big ( e - k N T _ { e } \big ) } { 2 T _ { e } } \Bigg ) } { 1 - \Bigg ( \frac { \beta \big ( e - k N T _ { e } \big ) } { 2 T _ { e } } \Bigg ) ^ { 2 } } \right\} ^ { 2 }
$$

$$
P _ { s 2 } ( e ) = \left( \frac { 3 } { 4 } T _ { e } S \mathrm { a } \Bigg ( \frac { e - k N T _ { e } } { 2 T _ { e } } \Bigg ) . \mathrm { c o s } \Bigg ( \frac { \beta \left( e - k N T _ { e } \right) } { 2 T _ { e } } \Bigg ) \right) \Bigg /
$$

$$
1 - \frac { 5 } { 4 } \Bigg ( \frac { \beta \big ( e - k N T _ { e } \big ) } { 2 T _ { e } } \Bigg ) ^ { 2 } + \frac { 1 } { 4 } \Bigg ( \frac { \beta \big ( e - k N T _ { e } \big ) } { 2 T _ { e } } \Bigg ) ^ { 4 } \Bigg ) ^ { 2 }
$$

由式(32)\~(35)可知，基带DSSS信号做二次谱运算后，信号以脉冲串的周期来 ${ N T _ { e } }$ 进行扩展从而得到一系列尖锐的脉冲谱线，这些脉冲谱线具有和基带成形脉冲函数二次功率谱相同的形状。也就是说，基带 DSSS信号 $s ( t )$ 在做第二次傅里叶变换运算后取其模的平方，丢失了相位信息，使得这些类似于基带成形脉冲函数的脉冲峰值都朝着同一个方向，它的脉冲幅度都大于零，且信号的能量将聚集在一系列与基带成形脉冲函数的二次谱相似的谱线处，测量谱线间的间隔就可以得到扩频码的伪码周期，这有利于信号在低信噪比环境下进行累加集平均处理。然后测量不同峰值谱线间的间隔就可以估计出多种基带脉冲成形扩频信号的伪码周期。

最后，将基带DSSS信号的二次谱处理的具体步骤总结如下：

a)分别求出序列 $^ d$ 和基带成形脉冲函数 $g ( t )$ 的一次功率谱 $p _ { d } ( f )$ 、 $p _ { g } ( f )$ 和二次谱 $p _ { d 2 } ( f )$ 和 $p _ { g 2 } ( f )$ ，再将序列和基带成形脉冲函数 $g ( t )$ 的二次谱做卷积运算求平方以后得到基带DSSS信号 $s ( t )$ 的二次谱;

b)按步骤a)求出下一组信号的二次谱，并将求得的二次功率谱与步骤1中的二次谱做累加集平均处理;

c)步骤b)累加后的二次谱在一定的频率范围内进行搜索最高峰和两个次高峰，测量这三个谱线间的距离就可以测量出以脉冲串的帧长来扩展的脉冲串周期。

d)若累加后基带 DSSS 信号的二次功率谱峰值谱线在一定时间内保持稳定，则停止累加，求得的间距即为基带DSSS 信号的伪码周期。

接收机接收到的每组数据中噪声 $n ( t )$ 与信号 $s ( t )$ 在概率统计上是相互独立的，可以通过集平均的方法来提高信号的信噪比，接收的基带DSSS数据越多，噪声抑制的效果越好，同时也提高了估计伪码周期的性能及精度。

# 3 计算机仿真

实验1验证本文所提算法对多种脉冲成形基带扩频码周期估计的可行性。加入均值为零的归一化高斯白噪声，信噪比$S N R = 2 0 d B$ ，取 PN 码长 $N { = } 6 3 b i t$ ，采样率 $S a = 1 6 b i t / c h i p$ ，本文选取高斯脉冲、三角脉冲、平方根升余弦脉冲、升余弦脉冲为载体来分析信号的低截获性，对基带DSSS信号做两次功率谱处理后，将其中一个位于 $\mathbf { \nabla } N T _ { e }$ 处的谱峰局部放大，得到多种脉冲成形基带DSSS信号扩频码周期估计的样本曲线，如图6-9所示。

![](images/309c57c494244a00a309a0187bee30493c81d2519b4d5c3d3c412e7eac89168e.jpg)  
（b）DSSS信号二次功率谱一段放大信号

![](images/d45ac28400216312048bd8ee461a7b85ec54cc614ea251d56cb427b5f5c3e2da.jpg)  
图6 平方根升余弦脉冲成形时基带DSSS信号二次功率谱及其一段放  
图7升余弦脉冲成形时基带DSSS信号二次功率谱及其一段放大信号

![](images/146a3113fa6a3eecef028ceab7365c9a0343d0e7d1ec505dc64d1fc31380ca33.jpg)  
（b）DSSS信号二次功率谱一段放大信号

![](images/c46716b9e23d4e4fcd00d6ad586fcda9313ef048211d2a4d0e03cead8c1da5de.jpg)  
图8三角脉冲成形时基带DSSS信号二次功率谱及其一段放大信号  
（b）DSSS信号二次功率谱一段放大信号  
图9高斯脉冲成形时基带DSSS信号二次功率谱及其一段放大信号

图5\~8中（a）分别表示平方根升余弦脉冲、升余弦脉冲、三角脉冲、高斯脉冲成形时基带DSSS信号的二次功率谱，图5\~8中（b）分别表示平方根升余弦脉冲、升余弦脉冲、三角脉冲、高斯脉冲成形时基带DSSS信号做两次功率谱处理以后的一段放大信号。从图5\~8（a）可知接收信号的二次功率谱不仅具有时间的量纲且出现了间距相等的尖峰谱线，图6\~9中（a)信号二次谱主峰两边的峰值谱线呈对称的状态，信号主峰右边的前四条峰值谱线的位置依次为1008、2016、3024、4032处，相邻谱线之间的间距都等于 $1 0 0 8 { = } N \times S a { = } 6 3 { \times } 1 6$ ，所以通过检测二次谱峰值谱线间的间距就可以估计平方根升余弦脉、升余弦脉冲、三角脉冲以及高斯脉冲下直扩信号的伪码周期。将接收到信号进行两次功率谱处理运算后，将其中一个位于 $N T _ { e }$ 处的谱峰局部放大如图5（b） $^ { \sim 8 }$ 中（b）所示。可以发现，信号以脉冲串的周期来 $N T _ { e }$ 进行扩展从而得到一系列尖锐的脉冲谱线，这些脉冲谱线具有和基带成形脉冲函数二次功率谱相同的图形其能量聚集的脉冲串波形具有、升余弦脉冲、三角脉冲以及高斯脉冲二次功率谱的形状，这些类似于基带脉冲成形函数的脉冲峰值都朝着同一个方向，且它的脉冲幅度都大于零，这将有利于基带成形DSSS信号伪码周期的检测。

实验2比较基带脉冲成形DSSS信号伪码周期的估计性能，伪码长度分别取 $N { = } 6 3 b i t$ 和 $N { = } 1 2 7 b i t$ ，采样率为$S a = 1 6 b i t / c h i p$ 。所得仿真结果如图10所示。

![](images/5ba0cbdbfbc2883c8d84edb437f7b6cf82dfb6bfff67282c1cc5650ae92b9c89.jpg)  
图10不同伪码长度下的均值性能曲线

图10（a）(b)分别表示为伪码序列长度 $\scriptstyle \mathbf { N = } 6 3$ bit、 $N { = } 1 2 7$ bit时对比其累加次数。从图10（a）（b）可知，随着信噪比的逐渐降低，基带脉冲成形DSSS信号所能携带的伪码长度逐渐变短，二次谱估计基带脉冲成形DSSS信号伪码周期的平均累加次数逐渐增加。因为基带脉冲成形DSSS信号的伪码长度越长，基带脉冲成形DSSS信号的频谱被扩展得越宽，系统的处理增益也会越高，信号的抗干扰的能力越强，从而使得估计基带脉冲成形DSSS信号的伪码周期时性能极好。由图10(a)(b)可知，在相同的条件下，脉冲成形为矩形时，DSSS信号的累加次数所需要的平均累加次数均小于其它几种成形脉冲，平方根升余弦脉冲次之、其次是升余弦脉冲和三角脉冲、高斯脉冲所需的累加次数最多，这是由于矩形脉冲带宽较宽，它的频谱相对于其它几种脉冲被扩展得更宽，使得基带DSSS信号的处理增益越大，从而使得伪码周期估计时效果较好。

实验3比较本文算法与文献[1]对伪码周期估计的性能的影响，本文取 $N { = } 1 2 7 b i t$ ，采样率为 $S a = 1 6 b i t / c h i p$ 。所得仿真结果如图11所示。

![](images/e5459333f45e4039990355b579263d9afc0fc2f9004652844c6fa8ae9057971c.jpg)  
图11不同方法下的估计性能曲线

由图11可知，随着新信噪比的逐渐增加，伪码周期估计的正确率也逐渐增加，在较低的信噪比高于， $- 1 0 ~ \mathrm { d B }$ 时能正确地估计出基带扩频信号的伪码周期，当信噪比越大时体现出了较好的抗截获性，且本文算法对伪码周期估计 的正确率比文献[1]高出7个数量级，性能优于文献[1]。

# 4 结束语

本文将基带扩频信号通过脉冲成形器后对其主要参数分析其低截获性能，并使用两次功率谱的方法对该类信号的伪码周期进行了估计。计算机仿真实验的结果表明，二次功率谱的方法可以在低信噪比的条件下完成对多种脉冲成形基带DSSS 信号伪码周期的估计，并分析了不同伪码长度对基带脉冲成形DSSS信号的伪码周期估计的影响，得出伪码长度越长，基带脉冲成形DSSS信号所需要的累加次数越少。根据不同伪码长度的估计性能均值曲线可以得知，矩形脉冲成形时的估计效率和估计性能均优于其它几种成形脉冲，平方根升余弦脉冲次之、其次是升余弦脉冲和三角脉冲、高斯脉冲的性能相对来说较差。最后根据不同方法下对伪码周期估计性能的对比曲线可知，随着新信噪比的逐渐增加，伪码周期估计的正确率也逐渐增加，在较低的信噪比高于-10dB时能正确地估计出基带扩频信号的伪码周期，当信噪比越大时体现出了较好的抗截获性，且本文算法对伪码周期估计的正确率比无脉冲成形约提高7dB左右。因此，要从截获的扩频信号中正确地估计出扩频信号的伪码序列，仅仅知道伪码周期是远远不够的，还需要估计出其他脉冲成形的参数，将其推广至其它的通信信号将是下一步的研究工作。

# 参考文献：

[1]张天骐，张传武，林孝康，等．直扩信号伪码周期及序列的估计[J]系统工程与电子技术，2005,27(8):1365-1368.(Zhang Tiqi,Zhang

Chuanwu,Lin Xiaokang,et al.Estimation algorithm for sequence and period of PN codes of DSSS Signals [J].Systems Engineering and Electronic Technology,2005,27(8): 1365-1368.).   
[2]郭黎利，孙志国．通信对抗技术[M].哈尔滨：哈尔滨工程大学出版, 2007:2-4.2-4.(Guo Lili,Sun Zhiguo. Communication countermeasure technology [M].Harbin: Harbin Engineering University Press,20o7: 2-4).   
[3]Zhang Tiqi,Wu Wangjun,Shi Sui,et al.The blind periodic estimation of the pseudo noise sequence in multi-rate DS//CDMA transmissions [C]//Proc of the 7th International Congress on Image and Signal Processing.2014: 24- 26.   
[4] Burel G. Detection of spread spectrum transmissions using fluctuations of correlation estimators [C]// Proc of IEEE International Symposium on Intelligent Signal Processing and Communication System. 20o0: 5-8.   
[5]Guan Mingxiang,Wang Le.A novel recognition method for low snr dsss signals based on four-order cumulate and eigenvalue analysis [J]. Chinese Journal of Electronics,2015,24(3): 650-653   
[6] 金艳，孙玖玲，姬红兵．基于相关熵的扩频周期估计方法[J]．系统工 程与电子技术,2018,40(1):17-22.(Jin Yan,SunYuling,Ji Hongbing.PN sequence period estimation method based on corrnentropy [J]. System Engineering and Electronics,2018,40(1):17-22).   
[7]汪旭．基于改进倒谱法的直扩信号伪码周期估计[D].哈尔滨工业大 学,2007: 61(Wang Xu.PN code period estimation of DSSS signal based on the improved cepstrum method [D]. Harbin: Harbin Institute of Technology, 2007: 61) .   
[8] 张天骐，杨强，宋玉龙，等．一种 K-means 改进算法的软扩频信号伪码 序列盲估计 [J]．电子与信息学报,2018,40(1):226-234.(Zhang Tianqi, Yang Qiang,Song Yulong,et al. Blind estimation of PN sequences of soft

spread spectrum signals using an improved K-means algorithm [J]. Journal

of Electronics & Information Technology,2018,40 (1): 226-234.）.   
[9]张天骐，杨柳飞，代少升，等.DS信号伪码周期及码片速率估计的自相 关法[J]．航天电子对抗,2007(4):53-57.(Zhang Tianqi,Yang Liufei,Dai Shaosheng,et al.Autocorrelation method for estimating the pseudo-code period and chip rate of DS signal [J].Aerospace Electronic Warfare,2007 (4): 53-57.) .   
[10]刘永冲．脉冲方式的超宽带系统的研究与设计[D].武汉：武汉理工大 学，2010.(Liu Yongchong.Research and design of pulse-based UWB systems [D]. Wuhan: Wuhan University of Technology,2010: 22.)   
[11]强幸子，张天骐，赵军桃，等．非合作直扩信号伪码及信息序列联合盲 估计[J].重庆邮电大学学报：自然科学版,2016(4):468-472.(Qiang Qiangzi, Zhang Tianshao,Zhao Juntao,et al. Joint blind estimation of nonconfidence information sequences [J]. Journal of Chongqing University of Posts & Telecommunications:Natural Sciences Edition,2016(4): 468-472.)   
[12] Bai Jun,Zhang Tianqi, Yu Xi.Et al.The estimation of the pn sequence's period of the DSSS signals in narrowband interference channels environment [C]// Proc of IEEE International Conference on Signal Processing, Communications and Computing.2011: 1-4.   
[13]赵军桃，张天骐，江晓磊，等．基于LEAP 神经网络同步DS-CDMA伪 码序列盲估计[J].计算机应用研究,2017,34(2):552-556.(Zhao Juntao, Zhang Tianshen, Jiang Xiaolei,et al. Blind estimation of synchronous DSCDMA pseudo-code sequences based on LEAP neural network [J]. Journal of Computer Applications,2017,34 (2): 552-556.).   
[14]刘孟孟，张立民，钟兆根．基于二阶矩的直扩信号伪码周期估计算法 [J].科学技术与工程.2013(5):1307-1310.(Liu Mengmeng,Zhang Limin, Zhong Zhaogen.Pseudo-random period estimation algorithm ofDSSS based on second moments [J]. Science Technology and Engineering.2013 (5): 1307-1310.) .