# 基于改进Prony法的电力系统低频振荡快衰分量辩识

![](images/d769a3ebf847ac1dedf963682e1d6be6671cc5f78dfdf09a4ab7bc112d4fa0f8.jpg)

牟建伟男1971年生，工程师，主要从事变电技术及信号辨识技术方面的工作研究。

牟建伟　尚亚男　刘文刚　戴思源　江　澎 王保力 王延勃（国网辽宁省电力有限公司大连供电公司大连116001）

摘要：考虑到传统Prony 算法对电力系统低频振荡模式中含有衰减较快的分量分析非常困难以及容易丢失衰减较快分量的问题，提出一种改进的快速衰减信号的提取方法——基于Givens 变换的Prony 分段分析法。该方法将采样时间划分为两个时段，首先分析第二时段求慢速衰减分量，然后分析第一时段求快速衰减分量。最后通过算例验证了该算法可以准确提取低频振荡模式中的快速衰减分量，同时也使得慢速衰减分量更加准确。

关键词：低频振荡Prony 算法快速衰减分量Givens 变换分段分析精确性中图分类号：TM74

# AnIdentification Method Based on Improved Prony for Fast Attenuate Component of the Power System Low-Frequency Oscillation

![](images/e850ab016e485dd72ef9733c48581f6a1417c35b0ed092dc9512691592dc2622.jpg)

Mu Jianwei Shang Yanan Liu Wengang Dai Siyuan Jiang PengWang baili Wang Yanbo (Dalian Power Supply Company of the State Grid Liaoning Province Electric Power Company LimitedDalian 116001 China)

尚亚男男1986年生，工程师，主要从事电力系统稳定性分析方面的工作研究。

Abstract: Considering that the traditional Prony algorithm is very difficult to analyze the fast attenuate component of the power system low frequency oscillation mode and the fast attenuate component can be missed easily, an improved method of extracting rapid attenuate signal is proposed which is called Prony segment analysis method based on Givens transform. This method divides the data acquisition time into two periods,and the second period is analyzed firstly to calculate the slow attenuate component, then the first period is analyzed for calculating the fast attenuate component. Numerical example proves that this algorithm can accurately extract fast attenuate component of low frequency oscillation mode,and also makes the slow attenuate component more accurate.

Keywords: Low frequency oscillation, Prony method, fast attenuation, Givens transform, segment analysis,accuracy

# 1 引言

随着我国特高压输电网络的引入以及跨大区域联网进程的加快，低频振荡[1成为影响电网安全稳定的重要问题，持续的振荡可能会毁坏电力设备继而诱发相继事故的发生，造成严重的后果。

实测数据分析表明，辨识振荡模式方法有短时傅里叶变换（Short-Time Fourier Transform，STFT）[2]、小波分析法[-4]、Prony 算法和 HHT 变换法[5-7]等。综合考虑运算量、耗时及适用性，选择Prony算法，该算法可以直接从时域中通过拟合求得信号的模态信息，不需要通过频率响应求取，计算量大大减少，适用性较强。

为了更有效地分析系统的低频振荡，提取全部的振荡特征，本文将传统的Prony算法进行改进，将基于Givens变换的Prony算法进行分段分析。Givens变换处理时不用形成法方程，可以直接由特征方程求出特征方程系数，避免了原算法求解法方程困难和误差较大的问题；其次，分段后能够非常准确地辨识出低频振荡模式中的快速衰减分量，并且慢速衰减分量也更加精确。

# 2 Prony算法计算步骤

Prony 算法[8-11]是提取平稳振荡模式的常用算法。它针对等间距采样点，假设模型是由一系列具有任意振幅、相位、频率和衰减因子的 $q$ 个指数函数的线性组合，其离散时间的函数形式为

$$
x ( t ) = \sum _ { i = 1 } ^ { q } A _ { i } \mathrm { e } ^ { \alpha _ { i } t } \cos { ( 2 \pi f _ { i } t + \theta _ { i } ) }
$$

式中， $A _ { i }$ 为振幅； $\theta _ { i }$ 为初相（rad）； $f _ { i }$ 为振荡频率$\left( \mathrm { H z } \right)$ ； $\alpha _ { i }$ 为衰减因子（阻尼）； $q$ 为信号阶数。

设式（1）中有 $q$ 个衰减正弦分量，然后将余弦式用欧拉公式表示，即

$$
\cos \left( 2 \pi f _ { i } t + \theta _ { i } \right) = \frac { 1 } { 2 } \bigg [ \mathrm { e } ^ { \mathrm { j } ( 2 \pi f _ { i } t + \theta _ { i } ) } + \mathrm { e } ^ { - \mathrm { j } ( 2 \pi f _ { i } t + \theta _ { i } ) } \bigg ]
$$

令 $p = 2 q$ ，则离散时间的函数形式可表示为

$$
\hat { x } ( n ) = \sum _ { i = 1 } ^ { p } b _ { i } z _ { i } ^ { n } \quad n = 0 , 1 , \cdots , N - 1
$$

Prony法的关键是要认识到式（1）是一个常系 数线性差分方程的齐次解。即有

$$
\hat { x } ( n ) = - \sum _ { i = 1 } ^ { n } a _ { i } \hat { x } ( n - k )
$$

通过一系列的数学变换，可得到差分方程式为

$$
\hat { x } ( n ) = - \sum _ { k = 1 } ^ { p } \alpha _ { k } \hat { x } ( n - k ) \quad n = p , \cdots , N - 1
$$

为建立Prony算法，定义实际测量值 $x ( n )$ 和估计值 ${ \hat { x } } ( n )$ 的误差为 $e ( n )$ ，即

$$
\begin{array} { c c } { { x ( n ) = \hat { x } ( n ) + e ( n ) } } & { { n = 0 , \cdots , N - 1 } } \end{array}
$$

将式（5）代入式（6)，可得

$$
\begin{array} { l } { { \hat { x } ( n ) = - \displaystyle \sum _ { k = 1 } ^ { p } \alpha _ { k } \hat { x } ( n - k ) + e ( n ) } } \\ { { = - \displaystyle \sum _ { k = 1 } ^ { p } \alpha _ { k } x ( n - k ) + \displaystyle \sum _ { k = 0 } ^ { p } \alpha _ { k } e ( n - k ) } } \end{array}
$$

由式（7）可以看出，此模型是一个由误差 $e ( n )$ 所激励的自回归滑动平均（Auto Regressive MovingAverage）模型 $\operatorname { A R M A } ( p , p )$ ，它具有相同的自回归（Auto Regressive，AR）和滑动平均（MovingAverage，MA）参数 $( a _ { i } )$ 。为使模拟信号更加逼近于真实信号，可采用平方误差最小原则，即关于 $a _ { 1 }$ …, $a _ { p - 1 } , a _ { p }$ 的最小二乘估计使得 $\sum _ { n = p } ^ { N - 1 } \Bigl | e ( n ) \Bigr | ^ { 2 }$ 值最小，由此将得到一组有一定求解难度的非线性方程。

改变误差估计的目标函数可以避免求解非线性方程，令 $\varepsilon ( n ) = \sum _ { k = 0 } ^ { p } \alpha _ { k } e ( n - k )$ ，则式（7）可变为

$$
x ( n ) = - \sum _ { k = 1 } ^ { p } \alpha _ { _ k } x ( n - k ) + \varepsilon ( n ) \quad n = p , \cdots , N - 1
$$

所以，变 $\sum _ { n = p } ^ { N - 1 } \Bigl | e ( n ) \Bigr | ^ { 2 }$ 最小即 $\sum _ { n = p } ^ { N - 1 } \Bigl | \varepsilon ( n ) \Bigr | ^ { 2 }$ 最小，这就是扩展的Prony 算法。扩展的Prony 算法即求解下列矩阵方程

$$
\left( \begin{array} { c c c c } { { x ( p ) } } & { { x ( p - 1 ) } } & { { \cdots } } & { { x ( 0 ) } } \\ { { x ( p + 1 ) } } & { { x ( p ) } } & { { x ( 1 ) } } \\ { { \vdots } } & { { \vdots } } & { { \vdots } } \\ { { x ( N - 1 ) } } & { { x ( N - 2 ) } } & { { \cdots } } & { { x ( N - p - 1 ) } } \end{array} \right) \left( \begin{array} { c } { { 1 } } \\ { { \alpha _ { 1 } } } \\ { { \vdots } } \\ { { \alpha _ { p } } } \end{array} \right) = \left( \begin{array} { c } { { \varepsilon ( p ) } } \\ { { \varepsilon ( p + 1 ) } } \\ { { \vdots } } \\ { { \varepsilon ( N - 1 ) } } \end{array} \right)
$$

为使目标函数 $J ( \alpha ) = \sum _ { n = p } ^ { N - 1 } \bigl | \varepsilon ( n ) \bigr | ^ { 2 }$ 为最小值，令${ \frac { \partial J ( \alpha ) } { \partial \alpha _ { i } } } = 0$ =0，则有

$$
\sum _ { k = 0 } ^ { p } \alpha _ { k } \left[ \sum _ { n = p } ^ { N - 1 } x ( n - k ) x ^ { * } ( n - i ) \right] = 0 \quad i = 1 , \cdots , p
$$

对应的最小误差能量为

$$
\varepsilon _ { p } = \sum _ { k = 0 } ^ { p } \alpha _ { k } \left[ \sum _ { n = p } ^ { N - 1 } x ( n - k ) x ^ { * } ( n ) \right]
$$

定义 $r ( i , k ) = \sum _ { n = p } ^ { N - 1 } x ( n - k ) x ^ { * } ( n - i ) , i , j = 0 , \cdots , p _ { \mathrm { { c } } }$ ，得到Prony算法的法方程形式为

$$
\left( \begin{array} { c c c c } { { r ( 0 , 0 ) } } & { { r ( 0 , 1 ) } } & { { \cdots } } & { { r ( 0 , p ) } } \\ { { r ( 1 , 0 ) } } & { { r ( 1 , 1 ) } } & { { r ( 1 , p ) } } \\ { { \vdots } } & { { \vdots } } & { { } } & { { \vdots } } \\ { { r ( p , 0 ) } } & { { r ( p , 1 ) } } & { { \cdots } } & { { r ( p , p ) } } \end{array} \right) \left( \begin{array} { c } { { 1 } } \\ { { \alpha _ { 1 } } } \\ { { \vdots } } \\ { { \alpha _ { p } } } \end{array} \right) = \left( \begin{array} { c } { { \varepsilon _ { p } } } \\ { { 0 } } \\ { { \vdots } } \\ { { 0 } } \end{array} \right)
$$

求解式（12)，可得参数 $a _ { 1 } , \cdots , a _ { p }$ 和最小误差能量 $\varepsilon _ { p }$ 的估计值。然后将 $a _ { 1 } , \cdots , a _ { p }$ 代入特征方程，进一步求解，得到特征根 $z _ { i }$ ， $i = 1 , 2 , \cdots , p$ 。则式(3)可简化为关于 $b _ { i }$ 的线性方程，用矩阵形式表示为

$$
\boldsymbol { \varPhi } \boldsymbol { b } = \hat { \boldsymbol { x } }
$$

其中

$$
\Phi = \left( \begin{array} { c c c c } { { 1 } } & { { 1 } } & { { \ldots } } & { { 1 } } \\ { { z _ { 1 } } } & { { z _ { 2 } } } & { { z _ { p } } } \\ { { \vdots } } & { { \vdots } } & { { } } & { { \vdots } } \\ { { z _ { 1 } ^ { N - 1 } } } & { { z _ { 2 } ^ { N - 1 } } } & { { \ldots } } & { { z _ { p } ^ { N - 1 } } } \end{array} \right)
$$

$$
\pmb { b } = [ b _ { 1 } , \cdots , b _ { p } ] ^ { \mathrm { T } }
$$

$$
\hat { \pmb x } = \left[ \hat { x } ( 0 ) , \cdots , \hat { x } ( N - 1 ) \right] ^ { \mathrm { T } }
$$

则

$$
\pmb { b } = \left[ \pmb { \mathcal { \pmb { \phi } } } ^ { \mathrm { H } } \pmb { \mathcal { \pmb { \phi } } } \right] ^ { - 1 } \pmb { \mathcal { \pmb { \phi } } } ^ { \mathrm { H } } \hat { \pmb { x } }
$$

式中，上标H代表共轭转置。在求解过程中，可通过下述关系式来减少计算量，提高计算效率，即

$$
\Phi ^ { \mathrm { H } } \Phi = \left( \begin{array} { c c c c } { \beta _ { 1 1 } } & { \beta _ { 1 2 } } & { \cdots } & { \beta _ { 1 p } } \\ { \beta _ { 2 1 } } & { \beta _ { 2 2 } } & { \beta _ { 2 p } } \\ { \vdots } & { \vdots } & { \vdots } \\ { \beta _ { p 1 } } & { \beta _ { p 2 } } & { \cdots } & { \beta _ { p p } } \end{array} \right)
$$

其中

$$
\beta _ { i j } = \frac { ( z _ { i } ^ { * } z _ { j } ) ^ { N } - 1 } { ( z _ { i } ^ { * } z _ { j } ) - 1 }
$$

式（19）中，“\*”代表共轭。

上述过程中，由于事先不知道低频振荡中各频率分量的个数，即式（9）中的 $p$ 不确定，同时为了

提高算法的精度，可以把模型的阶数取得大些（即取 $p _ { \mathrm { { e } } } > p \mathrm { { \bar { . } } }$ )，再通过相应方法计算出方程组系数矩阵的有效秩 $p$ 。

利用式（20）计算频率 $f _ { i }$ 、衰减因子 $\alpha _ { i }$ 、相位$\theta _ { i }$ 、振幅 $A _ { i }$ ，即

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { f _ { i } = \arctan { \left[ \operatorname { I m } ( z _ { i } ) / \operatorname { R e } ( z _ { i } ) \right] } / ( 2 \pi \Delta t ) } \\ { \alpha _ { i } = \ln { \bigg | z _ { i } \bigg | } / \Delta t } \end{array} \right. } \\ & { \left\{ \begin{array} { l l } { \theta _ { i } = \arctan { \left[ \operatorname { I m } ( b _ { i } ) / \operatorname { R e } ( b _ { i } ) \right] } } \\ { A _ { i } = \left| b _ { i } \right| } \end{array} \right. } \end{array}
$$

# 3 Prony算法的改进

# 3.1传统计算方法

在利用Prony算法对电力系统低频振荡信号进行求解的过程中，对于特征方程系数的求解是整个求解过程的核心。传统的计算方法是利用Prony算法的法方程形式进行求解，得到特征方程系数 $\boldsymbol { a }$ 的值。

将式（9）简写为

$$
X a = \pmb { d }
$$

式中， $X$ 为由采样数据形成的系数矩阵； $\boldsymbol { a }$ 为特征方程系数； $\pmb { d }$ 为信号误差。

式（21）的法方程形式为

$$
X ^ { \mathrm { { T } } } X a = X ^ { \mathrm { { T } } } { \pmb d }
$$

利用高斯消去法对式（22）进行求解，求得特征方程系数 $\mathbf { \Delta } _ { a }$ 。

上述即为基于法方程[12-13]形式的 Prony 算法的传统计算方法。

# 3.2分段分析法

现选用Givens方法对特征方程系数进行求解。利用Givens 变换[14-16]对方程进行求解，得到特征方程系数时，不用形成法方程，可以直接对式(21)进行求解。Givens变换方法在处理不含快速衰减分量的信号时，能够非常准确地求出信号的参数值，但在处理含快速衰减分量的信号，尤其是含有两个以上快速衰减分量的信号时，Givens方法及其他传统方法不一定能够取得较好的计算结果，有时甚至会丢失衰减较快的分量。

为解决上述问题，本文在Givens变换方法的基础上，提出了一种改进方法一一分段分析法。其具体实施步骤如下：

（1）读入采样数据。设采样间隔为 $\Delta t$ ，采样时长为 $T _ { \cdot }$ 。为了能够精确提取快速衰减分量，要求采样频率在0.01s附近取值，则此采样数据的采样间隔为 $\Delta t$ ，时长为 $T$ ，采样值个数为 $T / \Delta t$ 。

（2）时段划分。将总的时间长度分为两个时段，即第一时段时长为 $t _ { 1 }$ ，剩余时段划为第二时段，时长为 $T - t _ { 1 }$ 。第一时段和第二时段的分割点为 $t _ { \mathrm { s } }$ 。

(3）第二时段Prony法低频振荡分析。此时段分析慢速衰减分量，采样间隔 $\Delta t _ { 2 }$ 为 $t _ { \mathrm { b } }$ ，从 $t _ { \mathrm { s } }$ 时刻开始每间隔 $t _ { \mathrm { b } }$ 从采样数据中取一个采样值，即每隔 ${ t _ { \mathrm { b } } } ^ { \prime }$ $\Delta t$ 个采样数据取一个分析。具体分析过程为： $\textcircled{1}$ 从$t _ { \mathrm { s } }$ 时刻开始每间隔 $t _ { \mathrm { b } }$ 从采样数据中取一个采样值，直到 $T$ 结束； $\textcircled{2}$ 对经过消噪处理后的采样数据进行滤波，滤掉信号中的高频成分； $\textcircled{3}$ 首先选取阶数$q _ { \mathrm { e } }$ ， $q _ { \mathrm { e } }$ 大于有效秩 $p$ ，然后根据滤波后的采样数据形成扩展阶矩阵 $\pmb { R } _ { \mathrm { e } }$ ，采用奇异值分解法对扩展阶矩阵 $\pmb { R } _ { \mathrm { e } }$ 进行计算，求出扩展阶矩阵的所有奇异值，进而确定扩展阶矩阵 $\pmb { R } _ { \mathrm { e } }$ 的有效秩 $p$ ； $\textcircled{4}$ 重新选取阶数$n$ ， $n$ 稍大于有效秩 $p$ ，小于 $q _ { \mathrm { e } }$ ； $\textcircled{5}$ 用Givens 变换求式（21）的系数 $\mathbf { \nabla } _ { a }$ ； $\textcircled{6}$ 将第 $\textcircled{5}$ 步求出的系数代入特征方程，求出特征根 $z _ { i }$ ； $\textcircled{7}$ 将特征根代入式（20），求出频率和衰减因子； $\textcircled{8}$ 利用式 (17）～式(19)求出参数 $b _ { i }$ ； $\textcircled{9}$ 将 $b _ { i }$ 代入式 (20)，求出幅值和初相； $\textcircled{10}$ 最后将四个参数一一频率、衰减因子、幅值和初相代入式（1）得到慢速衰减分量信号的表达式（204号 $x _ { 2 } ( t )$ 。

(4）第一时段采样数据处理。第一时段中有快速衰减分量和慢速衰减分量。设第一时段采样间隔$\Delta t _ { 1 }$ 为 $t _ { \mathrm { a } }$ ，从0s开始进行采样，直到 $t _ { \mathrm { s } }$ 时刻为止。将这些时刻点代入第（3）步已经求出的慢速衰减分量表达式 $x _ { 2 } ( t )$ 中，得到这一时间段每个时刻点对应的慢速衰减数据，然后用第一时间段的采样数据减去刚才求出的慢速衰减数据，得到快速衰减数据。

(5）第一时段Prony法低频振荡分析。同理，采用与第（3）步相同的方法分析已经得到的快速衰减数据，就可以求出快速衰减分量的四个模态信息。

下图为本文采用的Prony法分段分析法低频振荡模式分析的流程图。

采用分段分析法后，使得Givens方法在对含快速衰减分量低频信号的求解效果得到了很大的改善。

# 4 算例分析

为验证本文采用改进的Prony法分段分析法能够准确地提取含快速衰减分量的低频振荡信号，本

开始  
读入采样数据  
(经过消噪处理后的信号)  
滤波(滤掉高频信号)  
设采样时间间隔为△t，采样时长为T  
将总时段划分为两个时段：  
第一时段为含快速衰减分量时段；第二时段为慢速衰减分量时段  
第二时段Prony法低频振荡分析，得到慢速衰减分量信号的  
表达式 $x _ { 2 } ( t )$   
第一时段采样数据处理：设第一时段采样间隔 $\dot { \Delta t _ { \parallel } }$ 为ta，从0s开始进行  
采样至ts时刻结束。将这些时刻点代入 $x _ { 2 } ( t )$ ，得到该时间段每个时刻  
点对应的慢速衰减数据，然后用该段采样数据减去已经求出的慢速  
衰减数据，得到快速衰减数据  
第一时段采用Prony法低频振荡分析：同理，采用与第二时段相同的  
分析方法便可得到信号的四个模态信息  
开始

节首先将本改进算法和基于法方程形式的Prony 法分段分析算法进行分析，其次将本改进算法与基于Givens变换不分段时的情况进行算例分析对比，最后验证了本改进算法具有很好的提取效果，能够十分准确地提取快速衰减分量。

构造输入信号为

$$
\begin{array} { r l } & { \mathbf { \boldsymbol { { x } } } ( t ) = \mathrm { { l o e } } ^ { - 0 . 0 0 2 \tau } \cos { \left( 2 \pi \times 0 . 4 2 3 t + 1 1 0 ^ { \circ } \right) } + } \\ & { \quad \mathrm { { 2 e } } ^ { - 0 . 2 6 5 2 t } \cos { \left( 2 \pi \times 0 . 4 2 t + 1 3 ^ { \circ } \right) } + } \\ & { \quad \mathrm { { 1 0 e } } ^ { - 0 . 0 3 1 1 t } \cos { \left( 2 \pi \times 0 . 2 4 7 3 t + 2 0 ^ { \circ } \right) } + } \\ & { \quad \mathrm { { 1 } } { \mathrm { { e } } } ^ { - 0 . 2 9 3 6 t } \cos { \left( 2 \pi \times 1 . 0 3 4 9 t + 6 0 ^ { \circ } \right) } + } \\ & { \quad \mathrm { { 5 . 8 } } { \mathrm { e } } ^ { - 4 . 5 . 8 7 8 8 t } \cos { \left( 2 \pi \times 2 . 4 t + 1 0 ^ { \circ } \right) } + } \\ & { \quad \mathrm { { 6 . 3 } } { \mathrm { e } } ^ { - 5 5 . 1 1 5 6 t } \cos { \left( 2 \pi \times 0 . 9 t + 6 0 ^ { \circ } \right) } } \end{array}
$$

信号模型阶数 $n$ 统一取为15。上述信号包含6个正弦分量，等效为12个复指数分量。对上述信号每0.01s计算一个值，共计算1000个值，用来模拟采样值，则此采样数据的采样间隔为0.01s，时长为10s，采样值个数为1000。各信号分量参数见表1。

# 4.1改进算法和基于法方程形式的Prony分段分析

这里取信号分段点为1s。第一时段分析快速衰减分量，采样时间间隔取0.01s；第二时段分析

# 表1算例信号的参数

Tab.1The parameters of the example signal   

<html><body><table><tr><td>分量序号</td><td>频率f/Hz</td><td>衰减因子α</td><td>幅值A</td><td>初相0/()</td></tr><tr><td>1</td><td>0.423 0</td><td>-0.002 7</td><td>10.000 0</td><td>110.000 0</td></tr><tr><td>2</td><td>0.420 0</td><td>-0.265 2</td><td>2.000 0</td><td>13.000 0</td></tr><tr><td>3</td><td>0.247 3</td><td>-0.0311</td><td>10.000 0</td><td>20.000 0</td></tr><tr><td>4</td><td>1.034 9</td><td>-0.293 6</td><td>1.000 0</td><td>60.000 0</td></tr><tr><td>5</td><td>2.400 0</td><td>-45.878 8</td><td>5.800 0</td><td>10.000 0</td></tr><tr><td>6</td><td>0.900 0</td><td>-55.115 6</td><td>6.300 0</td><td>60.000 0</td></tr></table></body></html>

慢速衰减分量，采样时间间隔取0.1s。表2为基于Givens变换和法方程形式Prony法分段分析法计算结果比较。

表2两种算法的计算结果比较  

<html><body><table><tr><td>分量序号</td><td>方法</td><td>频率f/Hz</td><td>衰减因子α</td><td>幅值A</td><td>初相0/()</td></tr><tr><td rowspan="2">1</td><td>Givens 变换</td><td>0.423 0</td><td>-0.002 7</td><td>10.000 0</td><td>110.000 0</td></tr><tr><td>法方程形式</td><td>0.423 0</td><td>-0.002 7</td><td>9.999 9</td><td>109.999 3</td></tr><tr><td rowspan="2">2</td><td>Givens 变换</td><td>0.420 0</td><td>-0.2652</td><td>2.000 0</td><td>13.000 0</td></tr><tr><td>法方程形式</td><td>0.420 0</td><td>-0.265 2</td><td>1.999 8</td><td>13.000 9</td></tr><tr><td rowspan="2">3</td><td>Givens 变换</td><td>0.2473</td><td>-0.0311</td><td>10.000 0</td><td>20.000 0</td></tr><tr><td>法方程形式</td><td>0.247 3</td><td>-0.031 1</td><td>10.000 0</td><td>20.0000</td></tr><tr><td rowspan="2">4</td><td>Givens 变换</td><td>1.034 9</td><td>-0.293 6</td><td>1.000 0</td><td>60.000 0</td></tr><tr><td>法方程形式</td><td>1.034 9</td><td>-0.293 6</td><td>1.000 0</td><td>60.000 0</td></tr><tr><td rowspan="2">5</td><td>Givens 变换</td><td>2.400 0</td><td>-45.878 7</td><td>5.800 1</td><td>9.999 1</td></tr><tr><td>法方程形式</td><td>2.365 9</td><td>-45.923 0</td><td>6.214 1</td><td>12.011 8</td></tr><tr><td rowspan="2">6</td><td>Givens 变换</td><td>0.900 0</td><td>-55.115 8</td><td>6.3001</td><td>60.0028</td></tr><tr><td>法方程形式</td><td>1.528 5</td><td>-56.554 5</td><td>2.421 7</td><td>60.193 5</td></tr></table></body></html>

由表2可见，对于分量 $1 \sim$ 分量4即慢速衰减分量，基于Givens变换的分段分析和基于法方程形式的分段分析都能准确地提取模态信息，但对于快速衰减分量，后者辨识出的分量6的频率为 $1 . 5 2 8 \mathrm { ~ 5 ~ H z }$ ，而理论值为 $0 . 9 0 0 ~ 0 \mathrm { H z }$ ；幅值为2.4217，理论值为6.3001，已出现严重偏差。基于Givens变换的分段分析法辨识出的快速衰减分量精确度很高，与理论值误差很小。

# 4.2Givens变换方法的分段和不分段分析

信号分段点选为1s。表3为基于Givens变换的分段和不分段分析的计算结果比较。

由表3可见，基于Givens变换的分段法能十分准确地提取各振荡特征的低频信号的模态信息；不

# 表3Givens变换方法的分段和不分段计算结果比较

Tab.2Comparison of calculation results of two kinds of algorithms   
Tab.3Comparison of the results of the segmentation and the whole calculation of the Givens transform method   

<html><body><table><tr><td>分量序号</td><td>方法</td><td>频率f/Hz</td><td>衰减因子α</td><td>幅值A</td><td>初相0/()</td></tr><tr><td rowspan="2">1</td><td>分段</td><td>0.423 0</td><td>-0.002 7</td><td>10.000 0</td><td>110.000 0</td></tr><tr><td>不分段</td><td>0.423 0</td><td>-0.002 7</td><td>10.000 0</td><td>110.000 0</td></tr><tr><td rowspan="2">2</td><td>分段</td><td>0.420 0</td><td>-0.265 2</td><td>2.000 0</td><td>13.000 0</td></tr><tr><td>不分段</td><td>0.420 0</td><td>-0.265 2</td><td>2.000 0</td><td>13.000 0</td></tr><tr><td rowspan="2">3</td><td>分段</td><td>0.2473</td><td>-0.0311</td><td>10.000 0</td><td>20.000 0</td></tr><tr><td>不分段</td><td>0.2473</td><td>-0.0311</td><td>10.000 0</td><td>20.000 0</td></tr><tr><td rowspan="2">4</td><td>分段</td><td>1.034 9</td><td>-0.293 6</td><td>1.000 0</td><td>60.000 0</td></tr><tr><td>不分段</td><td>1.0349</td><td>-0.2936</td><td>1.0000</td><td>60.000 0</td></tr><tr><td rowspan="2">5</td><td>分段</td><td>2.400 0</td><td>-45.878 7</td><td>5.8001</td><td>9.999 1</td></tr><tr><td>不分段</td><td>2.4266</td><td>-46.663 1</td><td>7.6938</td><td>4.600 2</td></tr><tr><td rowspan="2">6</td><td>分段</td><td>0.900 0</td><td>-55.115 8</td><td>6.3001</td><td>60.0028</td></tr><tr><td>不分段</td><td>1</td><td>一</td><td>1</td><td>二</td></tr></table></body></html>

分段时，对于快速衰减分量6却无法辨识。该算例说明，本文采用的分段法效果较好，能十分准确地辨识出信号中的快速衰减分量。

# 5 结论

（1）在振荡模式不含快速衰减分量情况下，传统Prony算法能够较准确地辨识振荡模态信息。当振荡模式含有两个及以上快速衰减分量时，传统Prony 算法由于采用固定的采样频率，无法捕捉衰减较快的分量，继而影响慢速衰减分量的辨识精度。

(2）本文的改进算法综合了Givens变换和分段Prony法的优点，对处理消噪后的低频振荡信号有独特优势。采用Givens变换避免了传统算法求解法方程困难的问题，提高了数值稳定性，减少了计算量；利用分段分析设置不同的分辨率 (采样频率)避免了采用同一采样频率而丢失快速衰减分量。该算法占用内存小，能非常准确地提取快速衰减分量，适用于辨识电力系统低频振荡模式。

# 参考文献

[1] Calderon-Guizar JG,Ramirez-Gonzalez M, Castellanos-Bustamante R,et al.Identification and monitoring inter-area oscillations in power systems[C].IEEE Trans.Power Tech.,Eindhoven, 2015:1-6.   
[2] 郑武．短时傅里叶变换在火成岩裂缝中的测井评 价方法研究[D]．吉林：吉林大学，2016.   
[3]孙庆森，张海峰，王猛，等．小波算法在变压器 励磁涌流中的应用研究[J]．电力系统保护与控制, 2017，45(8):121-125. Sun Qingsen, Zhang Haifeng, Wang Meng, et al. Application of wavelet algorithms in transformer inrush current[J]. Power System Protection and Control,2017,45 (8): 121-125.   
[4] 陈国雄．基于分形与小波理论的成矿复杂信息提取 与识别方法研究[D]．北京：中国地质大学，2016.   
[5] 胡昊明，郑伟，徐伟，等．Prony 和HHT算法在 低频振荡在线辨识中的适用性比较[J]．电力系统 保护与控制，2013，41(14)：33-40. Hu Haoming, Zheng Wei, Xu Wei, et al.Applicability comparison of Prony and HHT algorithms in on-line identification of low-frequency oscillations[J]. Power System Protection and Control, 2013,41(14): 33-40.   
[6] 杨德昌,RehtanzC,李勇,等．基于改进希尔伯特- 黄变换算法的电力系统低频振荡分析[J]．中国电 机工程学报，2011，31(10)：102-108. Yang Dechang, Rehtanz C, Li Yong, et al. Lowfrequency oscillation analysis of power system based on improved Hilbert-Huang transform[J]. Proceedings of CSEE,2011,31(10): 102-108.   
[7] 李天云，高磊，赵妍．基于HHT的电力系统低频 振荡分析[J]．中国电机工程学报，2006，26(14): 24-30. Li Tianyun, Gao Lei and Zhao Yan. Low-frequency oscillation analysis of power system based on HHT[J]. Proceedings of CSEE, 2006,26(14): 24- 30.   
[8] Hauer JF,Demeure C J, Scharf L L. Initial results in prony analysis of power system response signals[J]. IEEE Trans. Power Systems,1990,5(1): 80-89.   
[9] Grund C E,Paserba JJ, Hauer JF,et al. Comparison of Prony and eigenanalysis for power system control design[J].IEEE Trans.Power Systems,1993,8(3): 964-971.   
[10] 李安娜，吴熙，蒋平，等．基于形态滤波和Prony 算法的低频振荡模式辨识的研究[J]．电力系统保 护与控制，2015，43(3)：137-142. Li Anna, Wu Xi, Jiang Ping, et al. Research on low frequency oscillation mode identification based on morphological filtering and Prony algorithm[J]. Power System Protection and Control, 2015, 43(3): 137-142.   
[11]张晓威，牛晓红，翟广锐．改进的 Prony 算法在多 正弦信号频率估计中的应用研究[J]．电力系统保 护与控制，2017，45(15)：140-145. Zhang Xiaowei, Niu Xiaohong, Zhai Guangrui. Application of improved Prony algorithm in frequency estimation of multi-sinusoidal signals[J]. Power System Protection and Control, 2017, 45(15): 140-145.   
[12]邢志斌，李姗姗，王伟，等．利用垂线偏差计算 高程异常差法方程的快速构建方法[J]．武汉大学 学报（信息科学版），2016，41(6)：778-783. Xing Zhibin,Li Shanshan,Wang Wei,et al. Fast construction method of normal equation for calculating elevation anomaly difference by vertical deviation[J].Journal of Wuhan University (Information Science Edition),2016,41(6): 778-783.   
[13]黄德伦，史经俭，廉琦，等．基于法方程病态 的谱修正迭代算法的探讨[J]．测绘科学，2013, 38(2): 35-37. Huang Delun, Shi Jingjian,Lian Qi, et al. Exploration of spectral correction iteration algorithm based on normal equation morbidity[J]. Surveying and Mapping Science,2013, 38(2): 35-37.   
[14]魏子卿．用Givens 变换解最小二乘问题[J]．测绘 工程，1996，5(2)：1-7. Wei Ziqing. Solving the least square problem by givens transform[J]. Surveying and Mapping Engineering, 1996, 5(2): 1-7.   
[15]Pandian A,Parthasarathy K,et al. Towards faster givens rotations based power system state estimator[J]. IEEE Trans. Power Systems, 1999, 14(3): 837-843.   
[16]杜鹃，冯思臣．复矩阵的Givens 变换及其qr分 解[J]．成都理工大学学报（自然科学版)，2011, 38(6): 693-696. Du Juan,Feng Sichen. Givens transformation of complex matrix and its QR decomposition[J]. Journal of Chengdu University of Technology (Natural Science Edition),2011,38(6): 693-696.