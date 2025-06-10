# 基于调制宽带转换器的频谱分辨率研究

黄振‘柏正尧‘郭少杰²

(1.云南大学信息学院，云南昆明 650500；2.中国科学院云南天文台射电天文与VLBI研究团组，云南 昆明 650216)

摘要：目前，压缩感知的研究热点主要集中在重构算法改进方面，即如何降低重构误差和重构时间，且均在实际应用中所允许的范围内，而对于信号频域分析中的频谱分辨率提升技术的关注较少。本文采用调制宽带转换器对稀疏信号进行采样，采用正交匹配追踪算法进行重构输入信号，通过延长时域采样时长，实现单个通道低速采样的同时提升频谱分辨率。对低频射电天文信号进行仿真实验结果表明，在单个通道采样速率相同时，时域采样样本数由459增加至999时，频谱分辨率由0.4357MHz提升至0.2002MHz，但采样系统的总采样样本数仅由102增加至222。本文的研究为射电天文信号等高频窄带信号处理提供了很好的借鉴。

关键字：调制宽带转换器，频谱分辨率，压缩感知，射电天文信号

中图分类号：TN911.7

# 0引言

频谱分析是信号处理的重要技术手段之一，通过对频谱构成和分布进行分析，可获取信号的某些关键特征。针对高频窄带信号，需在满足香农采样定理的要求下，采用较高速率 ADC对信号采样和进行样本数据分析处理。目前，最高速率的ADC 无法满足学者对频谱分析的需求，因此，国内外学者对信号的结构和特点进行分析，针对自身或通过数学变换后具有稀疏性质的信号，提出了压缩感知（Compressed Sensing，CS）理论[1][2]。压缩感知理论主要包含前端的压缩采样系统和后端的信号重构两个部分，相比传统采样技术，压缩感知理论将采样和压缩合二为一，降低了采样速率、数据传输带宽以及存储空间。近年，国内外的学者对压缩感知的研究内容为重构算法的改进和实际应用，在实际应用的误差允许范围内，压缩感知相关理论能以较低的采样速率对稀疏信号作亚奈奎斯特采样，并能完美的重构出输入信号。但针对高频窄带信号处理的压缩感知理论指导实际应用的研究不足，在理论研究中的输入信号模型是时域长度设定好的信号序列，既频谱的分辨率也因此设定好了，未能有效的指导实际应用中如何提升信号频谱的分辨率。

在天文观测中，射电天文信号的谱线观测成为研究宇宙的重要方式，通过对谱线进行分析可以诊断有关天体的基本物理条件，如动能温度、总粒子数密度、速度、磁感应强度等[3。射电天文信号的谱线观测对终端设备的频率分辨率也提出了很高的要求[4，为了提高观测谱线的频谱分辨率，需在采样速率一定的情况下增加时域的采样时长，需消耗处理器内部的乘法器、累加器以及存储单元等资源。在实际的射电天文观测中，仅对一些指定的谱线感兴趣，这些指定的谱线在频域上具有稀疏特性，因此，本文把压缩感知理论应用到射电天文信号观测中，通过对前端的调制宽带转换器（Modulated Wideband Converter，MWC） 5]采样系统和的正交匹配追踪(Orthogonal Match Pursuit,OMP）」重构算法进行分析，实现低速 ADC 对高频窄带信号的压缩采样，并可接近无失真地重构出输入信号，仿真实验表明，在采样点数低于奈奎斯特速率采样样本数的情况下，本文方法有效地提升了频谱分辨率。

# 1MWC采样系统和重构算法

# 1.1 MWC采样系统

MWC[是由 Mishali 和 Eldar 提出的亚奈奎斯特采样系统，并对系统进行了详细的数学推导过程，其由多个通道组成，每个通道由伪随机序列发生器、低通滤波器和低速ADC 组成，如图1所示。

MWC 采样系统主要参数有： $m$ 为采样系统的通道数， $T _ { p }$ 为伪随机序列 $\dot { p } _ { i } ( t )$ 的周期， $T _ { s }$ 为 ADC采样周期， $a _ { i k }$ 为第i通道上 $p _ { i } ( t )$ 的第 $k$ 序列的值（ $a _ { i k } \in \{ + 1 , - 1 \}$ ）， $M$ 为 $p _ { i } ( t )$ 一个周期内包含 $\pm 1$ 的数量，低通滤波器 $\begin{array} { r } { h ( t ) = \frac { \pi W } { M } s i n c \left( \frac { \pi W } { M } t \right) } \end{array}$ （其截止角频率为 $\frac { \omega _ { s } } { 2 } = \frac { \pi } { T _ { s } } = \frac { \pi W } { M } )$ ， $f _ { N Y Q }$ 为奈奎斯特采样频率。其中， $p _ { i } ( t )$ 的表达式为：

$$
p _ { i } ( t ) = a _ { i k } , k T _ { p } / M \leq t \leq ( k + 1 ) T _ { p } / M , 0 \leq k \leq M - 1
$$

其傅里叶级数展开表达式为：

$$
\begin{array} { r } { p _ { i } ( t ) = \sum _ { l = - \infty } ^ { \infty } c _ { i l } e ^ { - j \frac { 2 \pi } { T _ { p } } l t } } \end{array}
$$

$$
\begin{array} { r } { c _ { i l } = \frac { 1 } { T _ { p } } \int _ { 0 } ^ { T _ { p } } p _ { i } ( t ) e ^ { - j \frac { 2 \pi } { T _ { p } } l t } d t = \frac { 1 } { T _ { p } } \sum _ { k = 0 } ^ { M - 1 } a _ { i k } e ^ { - j \frac { 2 \pi } { T _ { p } } l k } \int _ { 0 } ^ { \frac { T _ { p } } { M } } e ^ { - j \frac { 2 \pi } { T _ { p } } l t } d t } \end{array}
$$

![](images/a773d5b2f45cf7e61fd3662497337f14b255afc778bc0ab338ab7871ce5e5a94.jpg)  
图1MWC采样系统  
Fig.1 The sampling system of MWC

由图1可得如下时域数学表达式：

$$
\begin{array} { r l } { x _ { i } ( t ) = x ( t ) p _ { i } ( t ) , y _ { i } ( t ) = } & { { } ( t ) \otimes x _ { i } ( t ) , y _ { i } [ n ] = y _ { i } ( n T _ { s } ) } \end{array}
$$

式中， $\otimes$ 为卷积运算。令 $X ( f )$ 表示 ${ \bf \ddot { \boldsymbol { x } } } ( t )$ 的傅里叶频谱， $Y _ { i } ( f )$ 表示第 $i$ 通道输出压缩数据 $y _ { i } [ n ]$ 的离散时间傅里叶变换（DTFT），则公式（3）的频谱表达式为：

$$
\begin{array} { r } { Y _ { i } ( f ) = \sum _ { n = - \infty } ^ { \infty } y _ { i } [ n ] e ^ { - j 2 \pi f n T _ { s } } = \sum _ { n = - L _ { 0 } } ^ { L _ { 0 } } c _ { i l } X \big ( f - l f _ { p } \big ) , f \in [ - f _ { s } / 2 , f _ { s } / 2 ] } \end{array}
$$

式中， $\begin{array} { r } { L _ { 0 } = \bigg \lceil \frac { f _ { N Y Q } + f _ { s } } { 2 f _ { p } } \bigg \rceil - 1 } \end{array}$ ， $\left\lceil \bullet \right\rceil$ 表示不小于该整数。则 $m$ 个通道输出压缩数据的频谱表达式的简写为：

$$
y ( f ) = A z ( f )
$$

其中,

$$
\begin{array} { l } { y ( f ) = [ Y _ { 1 } ( f ) , Y _ { 2 } ( f ) , \cdots , Y _ { m } ( f ) ] ^ { T } } \\ { z ( f ) = [ z _ { 1 } ( f ) , z _ { 2 } ( f ) , \cdots , z _ { L } ( f ) ] ^ { T } } \\ { z _ { i } ( f ) = X \big ( f + ( i - L _ { 0 } + 1 ) f _ { p } \big ) } \\ { A = [ c _ { i l } ^ { * } ] _ { m \times L } , L = 2 L _ { 0 } + 1 } \end{array}
$$

# 1.2重构算法

MWC 采样系统的后端重构过程是先计算采样系统各通道之间输出压缩数据的协方差，再采用贪婪算法找出包含有用信息的频谱片段和对应字典的索引。因MWC每个通道上输出数据的长度是有限的，令数据长度为 $N$ ，则各通道输出数据之间的协方差矩阵方程为：

$$
\begin{array} { r } { \hat { R } _ { l , k } = 2 \pi \frac { M } { W } { \sum _ { n = 0 } ^ { N - 1 } } y _ { l } [ n ] y _ { k } ^ { * } [ n ] } \end{array}
$$

Eldar 等利用特征分解方法把对 $z ( f )$ 频谱片段求解过程转化为压缩感知问题，即对 $\hat { R }$ 进行特征分解，可得：

$$
\hat { R } = U ^ { * } \varLambda U = \big ( U ^ { * } \varLambda ^ { 1 / 2 } \big ) \big ( U ^ { * } \varLambda ^ { 1 / 2 } \big ) ^ { * } = V V ^ { * }
$$

$$
V = A S
$$

式中，是 $\hat { R }$ 特征解组成的对角矩阵， $U$ 是对应特征向量的矩阵，求解稀疏矩阵 $s$ 属于多测量矩阵（MMV）问题。重构过程的核心步骤为通过贪婪算法找出 $A$ 中尽可能少的列向量和S中包含有用信息的行向量来表达出V，把少量列向量矩阵 $A _ { S }$ 的伪逆矩阵 $( A _ { S } ^ { H } A _ { S } ) ^ { - 1 } A _ { S } ^ { H }$ 带入公式（5）中进行信号重构。

# 2 频谱分辨率

随着芯片制造工艺的提升，ADC 采样速率可达几个甚至十几个GHZ，信号处理的总带宽得到很大的扩展，但对高频窄带信号的谱线轮廓结构的观测依然难以满足，比如，目前 ADC 的最高采样速率很难满足射电天文观测中高频窄带信号总带宽的要求。根据傅里叶变换原理，在传统奈奎斯特采样方法中，采样时间分辨率 $\varDelta t$ 与接收机总带宽 $B$ 的关系为 $\boldsymbol { \varDelta } t \cdot \boldsymbol { B } = 1$ ，在观测时间 $\tau$ 内的采样点数为$N = \tau / \varDelta t = \tau \cdot B$ 。根据高斯统计， $N$ 个采样样本的总误差AT是单个采样的误差（系统误差） $T _ { s y s }$ 的$1 / \sqrt { N }$ ，接收机的极限灵敏度为 $\Delta T / T _ { s y s } = 1 / \sqrt { \tau B } ^ { \mathrm { ~ [ 8 ] ~ } }$ ，提高接收机总带宽可以提升极限灵敏度，但意味着更高的采样速率。在实际射电天文观测中，ADC的采样速率不小于奈奎斯特速率，并以延长接收机接收信号的时长来提升频谱分辨率，增加了采样样本数和后端处理资源的消耗。较高的频谱分辨率，精细的信号频谱结构，对分析和研究信号特征具有重要意义。

频谱分辨率 $\varDelta f$ 、采样频率 $F _ { s }$ 和采样样本数 $N$ 三者的关系为：

$$
\begin{array} { r } { \varDelta f = \frac { F _ { s } } { N } } \end{array}
$$

由公式（8）可知，可通过降低采样速率或增加采样时长来提高频谱分辨率。在 MWC采样系统中，令伪随机序列 $| p _ { i } ( t )$ 的周期为 $\boldsymbol { M } \cdot \boldsymbol { T _ { N Y Q } }$ ? $\langle T _ { N Y Q }$ 为奈奎斯特采样周期, $T _ { N Y Q } = 1 / f _ { N Y Q } )$ ，每个通道ADC采样速率为 $f _ { N Y Q } / M$ ，MWC 的总采样速率降低 $m / M$ ， $( m < M )$ 倍，频谱分辨率提升 $M / m$ 倍。

# 3实验仿真与分析

# 3.1基于MWC的理论分析

实验仿真信号为稀疏多频带信号，前端采用MWC采样系统进行采样，输出压缩数据，后端采用OMP 算法对压缩数据进行运算，重构出输入信号。稀疏多频带信号的参数为：子频带数 $N$ 为8，带宽均 $B$ 为 $5 \mathrm { M H z }$ ，总占频带宽为 $1 0 \mathrm { G H z }$ （即：奈奎斯特采样频率 $f _ { N Y Q } )$ ，信噪比为20。MWC采样系统参数为：通道数 $\mathbf { \bar { \rho } } _ { m }$ 为 $2 0 \left( m \geq 2 N \right)$ ），伪随机序列周期长度 $M$ 为195, $f _ { s } = f _ { p } = f _ { N Y Q } / M \approx 5 1 . 2 8 \mathrm { M H z }$ $L = M = 1 9 5 ( L _ { 0 } = 9 7 )$ 。设MWC单个通道上采样样本数为 $K$ ，公式(4)中 $y ( f )$ 矩阵大小为 $m \times K , A$ 矩阵大小为 $m \times M$ ， $z ( f )$ 矩阵大小为 $M \times K$ ， $y ( f ) = A z ( f )$ 。输入信号时域采样样本数和频谱分辨率关系如表1所示。

表1时域采样样本数和频谱分辨率关系  
Tab.1 The relationship between time domain sample number and spectral resolution   

<html><body><table><tr><td>单个通道采 样样本数</td><td>101</td><td>201</td><td>301</td><td>401</td><td>501</td><td>601</td><td>701</td><td>801</td><td>901</td><td>1001</td></tr><tr><td>等效总采样 样本数</td><td>19695</td><td>39195</td><td>58695</td><td>78195</td><td>97695</td><td>117195</td><td>136695</td><td>156195</td><td>175695</td><td>195195</td></tr><tr><td>频谱分辨率 /KHz</td><td>507.7</td><td>255.1</td><td>170.4</td><td>127.9</td><td>102.4</td><td>85.3</td><td>73.2</td><td>64.0</td><td>56.9</td><td>51.2</td></tr><tr><td>重构误差</td><td>0.0029</td><td>0.0023</td><td>0.0014</td><td>0.002</td><td>0.0008</td><td>0.0005</td><td>0.0005</td><td>0.0004</td><td>0.0003</td><td>0.0003</td></tr></table></body></html>

MWC采样系统中伪随机序列的频率要不小于奈奎斯特采样速率才能近乎无失真的重构出输入信号，伪随机序列在硬件实现技术上的难度远低于ADC，因此在采样系统中采用高速伪随机序列生成器对输入信号做数字离散化，经低通滤波器后进行低速采样。在仿真中，伪随机序列的频率等于奈奎斯特采样速率，MWC采样系统总采样样本数为mK，压缩数据经数学变换后的 $z ( f )$ 矩阵样本数为MK，则 MWC 采样系统的等效总采样样本数为MK。因此，从表1得出 MWC 采样系统的等效总采样样本数是单个通道采样样本数的M倍，即频谱分辨率提升M/m倍;随着单个通道采样样本数的增加，

等效总采样样本数和频谱分辨率随之增加。

# 3.2基于MWC的低频射电天文信号仿真

低频射电天文信号的数据来源于云南天文台，以 ${ 2 0 0 } \mathrm { M H z }$ 采样速率对频段在55Mhz-65Mhz的射电天文信号进行采集的多组数据，本实验随机选取其中的一组时域采样数据进行仿真，其采样点数为1024，频谱如图2中所示。MWC采样系统的参数设置为：通道数 $m$ 为6，伪随机序列周期长度M为27， $f _ { s } = f _ { p } = f _ { N Y Q } / M \approx 7 . 4 0 7 4 \mathrm { M H Z }$ ， $L = M = 2 7$ （ $L _ { 0 } = 1 3$ ），总采样速率为44.4444MHZ。本次实验中的MWC 非全盲采样系统，需要设置输入信号的子频带数为2，并设定MWC单个通道上采样样本数K为不同值时的仿真数据及频谱图，如表2和图2所示。

表2是K分别为17、27、37时，对应MWC采样系统采样样本数、等效总采样样本数、频谱分辨率、重构误差和OMP 算法的重构时间的仿真实验数据。通过表2可以看出，时域采样样本数由459 增加至999 时，频谱分辨率由0.4357MHz 提升至0.2002MHz，基于 MWC采样系统的总采样样本数仅增加至222，且重构误差在 $1 0 ^ { - 2 }$ 量级、重构时间在 $1 0 ^ { - 3 }$ 量级。图2中黑色频谱是低频射电天文信号的频谱图，红色频谱是K分别为17、27、37时重构信号的频谱图，通过图2可以看出，基于MWC 采样系统重构出的频谱随着的K增加，频谱分辨率得到了提升，频谱带宽逐渐收敛并接近低频射电天文信号。因此，采用MWC采样系统，不仅能实现单个通道低速率采样，而且能通过增加时域采样时长来提升信号的频域分辨率。

表2不同K值的仿真实验数据  
Tab.2 The simulation experimental data at different K values   

<html><body><table><tr><td>单个通道采样样本数</td><td>17</td><td>27</td><td>37</td></tr><tr><td>MWC 采样系统采样样本数</td><td>102</td><td>162</td><td>222</td></tr><tr><td>等效总采样样本数</td><td>459</td><td>729</td><td>999</td></tr><tr><td>频谱分辨率/MHz</td><td>0. 4357</td><td>0.2743</td><td>0.2002</td></tr><tr><td>重构误差</td><td>0.035</td><td>0.063</td><td>0.028</td></tr><tr><td>OMP 算法的重构时间/s</td><td>0.0039</td><td>0.0049</td><td>0.0058</td></tr></table></body></html>

![](images/109bada29dd11a2be5b6c53598801a319b3b7805e1d0112ef08ee2dbeb0e8c8c.jpg)  
图2不同K值的频谱  
Fig.2 The spectrum at different K values

# 4结论

本文通过对MWC采样系统的深入分析，以及实验仿真，验证了增加MWC采样系统的时域采样时长，以实现低速率采样条件下，提升信号频域分辨率的可行性和有效性。为提升高频窄带信号和低频射电天文信号频谱分辨率提供一种新的方法和途径，在实际工程应用中，需结合信号特征，进一步考虑输入信号的频带带宽、频谱波形、奈奎斯特带宽等，设计MWC 采样系统的通道数、伪随机系列周期、ADC采样周期以及压缩感知矩阵等重要参数对系统性能的影响。下一步工作将针对射电文信号的频谱特征和频谱分辨率的要求，设计 MWC 采样系统，硬件实现该采样系统并进行实测，力争推进论文研究成果的实际应用。

# 参考文献

[1] Donoho DL. Compressed sensing[J]. IEEE Transactions on Information Theory， 2006, 52(4) :1289-1306.

[2] Candes E J，Romberg J，Tao T. Robust uncertainty principles:exact signal reconstruction from highly incomplete frequency information[J]. IEEE Transactions on Information Theory， 2006， 52(2):489-509.

[3]戴伟，尚振宏，徐永华,等．基于独立成分分析的射频干扰信号消除方法［J]．天文研究与技术，2019，16(3):268-277.

DAI W, SHANG Z H, XU Y H,et al. Radio Frequency Mitigation Using Independent Component Analysis. Astronomical Research & Technology， 2019，16(3): 268-277.

[4]张燕坤，董亮，李明悦,等．比值校正法在射电频谱中的应用[J]．天文研究与技术，2020，17(3): 283-291.

ZHANG Y K, DONG L,LI M Y,et al. The Application of Ratio Correction in Radio Spectrum. Astronomical Research & Technology，2020，17(3): 283-291.

[5]张瑜．基于亚奈奎斯特采样的射电天文信号功率谱密度估计[D]．云南大学，2018.

Zhang Yu. Estimation of Power Spectral Density of Radio Astronomy Signal Based on Sub-Nyquist Sampling[D]. Yunnan University， 2018.

[6] Gao X，Wang X， Zhou J. A Robust Orthogonal Matching Pursuit Based on L 1 Norm[C]// 2020 Chinese Control And Decision Conference (CCDC)． 2020.

[7] Mishali M，Eldar Y C. From Theory to Practice: Sub-Nyquist Sampling of Sparse Wideband Analog Signals[J]. IEEE Journal of Selected Topics in Signal Processing， 2010, 4(2) :375-391.

[8] Wilson T L，Rohlfs K，Huttemefister S. Tools of Radio Astronomy，5th edition. Springer， 2012.

# Research on Spectrum Resolution Based on Modulated Wideband Converter

Huang Zhen'， Bai Zheng-yao'， Guo Shao-jie²

(1.School of Information Science and Engineering， Yunnan University， Kunming 650500, China；2.Yunnan Astronomy Radio Astronomy and VLBl Research Group， Chinese Academy of Sciences，Kunming 650216, China)

Abstract: At present, the research on compressed sensing has mainly focused on reducing the reconstruction error and the reconstruction time by improving the reconstruction algorithm. However， the reconstruction error and reconstruction time lie in the practically allowed range. But researchers less pay attention to improving techniques of spectral resolution in the frequency domain analysis. In this paper，we use the modulated wideband converter (MWC) to sample the sparse signals，and employ the orthogonal matching pursuit (OMP) algorithm to reconstruct the input signals. By extending the sampling time to realize low sampling rate in a channel， and improve the spectral resolution. The experimental results of low-frequency radio astronomical signals show that show that the spectral resolution increases from O.4357MHz to 0.2002MHz when the number of samples in time domain increases from 459 to 999 with the same sampling rate for all channels. Meanwhile, the total sample number of the system increases only from 102 to 222. Our work provides a good reference for processing the narrowband high-frequency signal， such as radio astronomical signals。

Keywords: Modulated Wideband Converter， Spectral Resolution， Compressed Sensing, Radio Astronomical Signal