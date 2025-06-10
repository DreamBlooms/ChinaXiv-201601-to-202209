# 基于压缩感知法对法拉第色散函数的重构

于衍川，孙晓辉（云南大学物理与天文学院，云南昆明650500）

摘要：观测到的偏振量与法拉第色散函数之间是傅里叶变换对，而法拉第色散函数反映了辐射区域和辐射传播途径的磁场结构。如何通过这一关系精确重构出法拉第色散函数对于研究银河系及河外星系磁场具有重要的作用。目前已提出了基于压缩感知的法拉第色散函数重构方法，模拟结果要优于传统方法，然而是否具有实用性仍然未知。本文主要探究该方法应用于实际观测频率范围时是否依然可行，并进行了大样本统计学实验。结果表明：其重构结果受到各种因素的影响，具有很大的随机性，我们对其重构结果在峰值附近再次进行了最小二乘拟合后，其重构出的法拉第深度更接近真实值。

关键词：压缩感知；偏振量；法拉第色散函数；法拉第深度

法拉第旋转（Faradayrotation）是线偏振电磁波通过磁化星际介质时其偏振角发生旋转的一种物理现象。偏振位置角旋转的大小可以写成 $\phi ( { \vec { r } } ) \lambda ^ { 2 }$ ，其中λ为观测波长， $\phi ( \vec { r } )$ 为辐射产生位置处的法拉第深度，写成：

$$
\begin{array} { r } { \phi ( \vec { r } ) = \int _ { \vec { r } } ^ { \mathrm { o b s e r v e r } } n _ { e } B _ { \parallel } d l ( 1 ) } \end{array}
$$

其中 $\mathfrak { n } _ { \mathrm { e } }$ 为热电子密度， $\mathsf { B } _ { \parallel }$ 为视线方向磁场分量， $d l$ 是视线方向上线元。这样观测到偏振量 $P$ 可以写成[1]：

$$
\begin{array} { l } { { P ( \lambda ^ { 2 } ) = Q ( \lambda ^ { 2 } ) + i U ( \lambda ^ { 2 } ) ~ ( 2 ) } } \\ { { { } } } \\ { { = \int _ { - \infty } ^ { \infty } F ( \phi ) e x p ( 2 i \phi \lambda ^ { 2 } ) d \phi ~ ( 3 ) } } \end{array}
$$

这里 $F ( \phi )$ 为法拉第色散函数（Faradaydispersion function），是法拉第深度的函数， $Q$ 和 $U$ 为斯托克斯参量，是观测波长（频率）的函数。

从（3）式我们可以看出偏振量 $P$ 和法拉第色散函数 $F ( \phi )$ 之间是傅里叶变换对。 $F ( \phi )$ 表示法拉第深度为 $\phi$ 处的偏振强度和偏振位置角，反映辐射区域以及辐射传播途径上的磁场结构。为了研究星际介质的磁场，我们需要重构出法拉第色散函数。

目前已有多种重构法拉第色散函数的方法。Brentjens&de Bruyn 提出了法拉第旋率综合方法（Faraday rotation measure synthesis,简称 RMS)，RMS 通过观测偏振量和法拉第色散函数之间的傅里叶关系来重构法拉第色散函数。因为观测波段是有限的，所以RMS 获得的法拉第色散函数是真实色散函数与窗口函数的卷积，对复杂的源需要解卷积。与RMS方法类似的还有小波方法[2-3]。此外，还有一些假定辐射模型的方法用来重构法拉第色散函数，如Q-U 拟合法[4]。

本文主要讨论压缩感知方法（或称为压缩采样，compressivesensing/sampling，原理参见[5-6])。该方法的优点在于利用极少的采样数据，也有可能重构原始的完整信号。压缩感知理论以信号的稀疏性为前提，通过编码测量和重构算法来实现信号的精确重构。目前，已经提出了基于压缩感知法的法拉第色散函数重构算法,如Lietal采用最小 $\mathbf { \nabla } \cdot l _ { 1 }$ 范数法建立了适用于法拉第薄源（Faraday thin， $\lambda ^ { 2 } \Delta \phi \ll 1$ ，这里 $\Delta \phi$ 为源在法拉第深度域上的延展范围，即 $F ( \phi )$ 的宽度)，法拉第厚源(Faraday thick, $\lambda ^ { 2 } \Delta \phi \gg 1 \rangle$ 和同时含有法拉第薄和法拉第厚源的算法，其模拟结果显示该方法可以用于重构法拉第色散函数，并与RMS进行比较，发现用压缩感知方法重构出的法拉第色散函数在数值和误差上要优于RMS 方法[7]；还有Andrecut et al采用匹配追踪算法建立了对同时含有法拉第薄和法拉第厚源进行重构的方法8。但这些方法目前还处于理论模拟阶段，其实用性还没有好好研究，比如Lietal的算法中设置的频率（波长）范围过大，未将噪声添加到实验数据，对算法中各种参数设置对重构结果的影响也没有进行实验和讨论以及实验样本过少等。在本文中，我们将基于 Li et al方法，在其基础上从实际观测角度进行数值模拟，对以上问题进行更深入研究以此探讨其实用性。这里假定法拉第色散函数是稀疏的（即针对源包含一个或多个法拉第薄成分)，，用Python 语言编写了重构法拉第色散函数的程序。我们采用的频率范围为 $1 . 1 { \ - } { \ - } 3 . 1 \mathrm { G H z }$ ，对应澳大利亚望远镜致密阵 ATCA上L 波段的观测频率范围[9]。

# 1重构方法

我们的问题是已知测量矩阵 $\mathbf { A } \in R ^ { M \times N } ( M \ll N )$ 和未知信号 $\scriptstyle \mathbf { { \pmb { x _ { 0 } } } }$ 在该矩阵的线性投影$\mathbf { y } \in R ^ { M }$ ，即 $y = \mathtt { A } x _ { 0 }$ ，要由测量值y重构该未知信号 ${ \bf { \sigma } } _ { { \bf { x } } _ { 0 } }$ 。在压缩感知理论中，假定该未知信号$\mathbf { \boldsymbol { x } _ { 0 } }$ 为稀疏的，信号 ${ \bf { \sigma } } _ { { \bf { { x } } _ { 0 } } }$ 可以由测量值y通过求解最小 $l _ { 1 }$ 范数问题精确重构：

$$
\mathbf { A } \pmb { x _ { 0 } } = \pmb { y }
$$

若该未知信号 $\scriptstyle \mathbf { { \pmb { x _ { 0 } } } }$ 为非稀疏性时，我们可以通过某种变换（如小波变换）进行稀疏性表示，即  
（204号 $\pmb { x _ { 0 } } = \mathbf { \omega } \mathbf { u }$ ， $\mathbf { X }$ 为该信号在 $\pmb { \omega }$ 变换域下的稀疏性表示，则有：  
$\mathbf { x } = \operatorname* { m i n } \parallel X \parallel _ { l _ { 1 } }$ s.t. $\mathbf { A } x _ { 0 } = A \omega X = y$ (7)

我们将（2）式写成矩阵形式：

$$
\mathbf { Y } f = P
$$

这里 $f$ 为法拉第色散函数，是一个N维矢量， $\mathbf { Y }$ 为 $P$ 和 $\pmb { f }$ 之间傅里叶变换的离散表示，是一个$\mathsf { M } \times \mathsf { N }$ 矩阵， $P$ 为观测偏振量，是一个M维矢量，这里M为观测频率通道数目，每个通道上接受不同波段的偏振量。

由于法拉第色散函数 $f$ 是复变函数，我们可以将其实部和虚部分别写成f.real和f.imag,则（8）式可变为：

$$
\big [ { \begin{array} { c c } { C } & { - S } \\ { S } & { C } \end{array} } \big ] \big [ { \begin{array} { c c } { f . r e a l } \\ { f . i m a g } \end{array} } \big ] = \big [ { \pmb { P . } } r e a l \big ]
$$

这里 $c$ 和 $s$ 都是 $\mathrm { M } \times \mathrm { N }$ 的矩阵， $\ d r _ { j } = \cos 2 \phi _ { j } \lambda _ { i } ^ { 2 } , S _ { i j } = \sin 2 \phi _ { j } \lambda _ { i } ^ { 2 } , i = 1 , 2 , \dots , M , j = 1 , 2 , \dots , N ;$ （2号$\pmb { f } = \left[ \begin{array} { l } { \pmb { f } . r e a l } \\ { \pmb { f } . i m a g } \end{array} \right] .$ ，是一个2N维矢量； [P.real],是一个2M维矢量。

我们将观测通道数目 $\mathtt { M }$ 设置为100，波长范围为0.096m到 $0 . 2 7 3 \mathrm { m }$ （对应于频率$1 . 1 { \ - } { - } 3 . 1 \mathrm { G H z } )$ ，为了更好地描述实验设置，我们引用了Brentjens&de Bruyn 里面的两个定义：最大法拉第深 $| \phi _ { m a x }$ |和法拉第旋率传播函数（RMSF）的半峰全宽（FWHM） $\Delta \phi _ { F W H M }$ ，这两个量是由最大波长的平方 $\lambda _ { m a x } ^ { 2 }$ ，最小波长的平方 $\lambda _ { m i n } ^ { 2 }$ 和观测通道的间隔（即两个相邻波长平方的间隔） $\delta \lambda ^ { 2 }$ 所决定：

$$
| \phi _ { m a x } | = \frac { \sqrt { 3 } } { \delta \lambda ^ { 2 } }
$$

$$
\begin{array} { r } { \Delta \phi _ { F W H M } = \frac { 2 \sqrt { 3 } } { \lambda _ { m a x } ^ { 2 } - \lambda _ { m i n } ^ { 2 } } } \end{array}
$$

在实验中，我们将均值为0，标准差 $\sigma$ 为1（强度单位任意，下同）的高斯噪声加到 $Q$ 和 $U$ 上，并设置在法拉第深度 $\phi$ 空间的分辨率为 $\delta \phi$ 为 $\Delta \phi _ { F W H M }$ 的 $1 / 4$ ，则总的格点数N（ $\phi$ 空间中坐标点 $\phi _ { i }$ 的个数， $\mathrm { i } = 1 , 2$ ，…，N）为:

$$
\mathsf { N } = \mathrm { i n t } ( \frac { 2 | \phi _ { m a x } | } { \delta \phi } )
$$

其中int（表示取整。表1中列出了一些主要的实验参数：

表1实验参数Table 2Experimental parameters  

<html><body><table><tr><td>mmax</td><td>9.2 × 10-³ m²</td></tr><tr><td>2min</td><td>7.5 × 10-² m²</td></tr><tr><td>822</td><td>6.6 × 10-4 m²</td></tr><tr><td>IΦmaxl</td><td>2625 rad m-2</td></tr><tr><td>△FWHM</td><td>53 rad m-2</td></tr><tr><td>N</td><td>384</td></tr><tr><td>8Φ</td><td>13.7 rad m-2</td></tr></table></body></html>

# 2结果与讨论

# 2.1一般情况

在我们的模拟实验中，我们假定一个法拉第色散函数包含5个法拉第薄源,这些源分别是： $F ( - 1 6 4 . 1 ) = 3 + 6 \mathrm { i }$ ， $F ( - 8 2 . 0 ) = - 4 + 3 \mathrm { i }$ ， $F ( 0 . 0 ) = 2 + 3 \mathrm { i }$ ， $F ( 6 8 . 4 ) = - 8 - 5 \mathrm { i }$ ，$F ( 1 3 6 . 7 ) = 5 + 3 \mathrm { i }$ ，对应的信噪比分别为： $6 . 7 , 5 . 0 , 3 . 6 , 9 . 4 , 5 . 8$ 。我们尝试对包含这5个法拉第薄源的法拉第色散函数进行了反解，结果如图1a 所示，这里我们采用 $\phi$ 的加权平均的差值（ $d _ { w m }$ ）来比较重构函数 $\tilde { f }$ 和原始法拉第色散函数 $\boldsymbol { f } ^ { [ 1 0 ] }$ ：

$$
| d _ { w m } | = \left| \sum _ { i = 1 } ^ { N } p _ { i } \phi _ { i } \middle / \sum _ { i = 1 } ^ { N } p _ { i } - \sum _ { i = 1 } ^ { N } \tilde { p } _ { i } \tilde { \phi } _ { i } \middle / \sum _ { i = 1 } ^ { N } \tilde { p } _ { i } \right|
$$

其中 $p$ 表示偏振强度，从图中可以看出没有噪声时该模型准确的重构了原始图像，而加入噪声时重构结果出现了偏差。 $| d _ { w m }$ |分别为： $5 . 8 0 \times 1 0 ^ { - 5 }$ ，11.78。

我们发现通过压缩感知方法重构出的法拉第色散函数随着法拉第薄源偏振强度的大小，相位以及两个法拉第薄源的法拉第深度之间的间隔 $\Delta \phi$ 的不同而呈现出不同，甚至不能够准确的重构出原始图像。在这里我们分两种情况进行测试说明： $\textcircled{1}$ 假定上述5个法拉第薄源的法拉第深度之间的间隔 $\Delta \phi$ 不变，改变其大小和相位，如 $F ( - 1 6 4 . 1 ) = 3 - 6 \mathrm { i }$ ， $F ( - 8 2 . 0 ) =$ $- 4 + 3 \mathrm { i }$ ， $F ( 0 . 0 ) = 5 + 3 \mathrm { i }$ ， $F ( 6 8 . 4 ) = 8 - 5 \mathrm { i } , F ( 1 3 6 . 7 ) = - 5 + 4 \mathrm { i }$ ，对应的信噪比分别为：6.7,5.0，5.8,9.4,6.4，重构结果如图1b所示； $\textcircled{2}$ 假定大小和相位不变，改变其法拉第深之间的间隔 $\Delta \phi$ ，如： $F ( - 1 5 0 . 4 ) = 3 + 6 \mathrm { i }$ ， $F ( - 6 8 . 4 ) = - 4 + 3 \mathrm { i }$ ， $F ( 0 . 0 ) = 2 + 3 \mathrm { i }$ ，$F ( 1 0 9 . 4 ) = - 8 - 5 \mathrm { i }$ ， $F ( 1 6 4 . 1 ) = 5 + 3 \mathrm { i }$ ，对应的信噪比分别为：6.7,5.0,3.6,9.4,5.8,重构结果如图1c所示。

当假定间隔 $\Delta \phi$ 不变时，从图中可以看出前三个源并没有很好的重构出原始图像，其相位和大小存在一定误差，其中 $| d _ { w m }$ |分别为：6.31，17.03。而假定大小和相位不变时，后面四个源都与原始图像出现了较大偏差，其中 $| d _ { w m }$ |分别为：8.18，17.11。同时，我们也发现在不加入噪声时当我们将这些法拉第薄源的法拉第深之间的间隔 $\Delta \phi$ 设置的足够大时，即$\Delta \phi > 9 0 \mathrm { r a d } m ^ { - 2 }$ 时，无论改变其大小，相位和 $\Delta \phi$ ，该模型能够准确的重构出原始图像，即使在加入噪声时，其产生的误差也很微小。当然，以上测试的这些源的法拉第深度都是设置在该方法的格点N上进行的。

通常，在实际应用中，我们事先并不知道法拉第色散函数的法拉第深度以及两个源的法拉第深度之间的间隔 $\Delta \phi$ ，我们要重构的法拉第色散函数各个成分的法拉第深度是随机的，一般不在这种方法设置的格点N上，并且 $\Delta \phi$ 也是随机的，所以我们也无法确定该模型是否能够很好的重构出法拉第色散函数。这里我们随机选取了一个包含5个法拉第薄源的色散函数（这些法拉第薄源的法拉第深度不在格点N上)： $F ( - 1 1 4 ) = - 6 - 1 \mathrm { i }$ ， $F ( - 6 0 ) = 7 - 4 \mathrm { i }$ ，$F ( 4 8 ) = 3 - 5 \mathrm { i }$ ， $F ( 1 0 2 ) = - 3 . 5 + 3 \mathrm { i }$ ， $F ( 2 1 0 ) = 9 + 3 \mathrm { i }$ ，对应的信噪比分别为：6.1,8.1,5.8,4.6,9.5。其测试结果如图1d 所示，其中 $| d _ { w m }$ |分别为：0.40，10.20。

![](images/0357bd1f0a34e9e8a8a1e321be7e9fa7aaf2b7f3515014b71acb475f20764a0a.jpg)  
Fig.1From leftto right in the firstrow:a,b; in the second row are: c,d.From top to botom ineach panel: the original data,the noiseless reconstruction resultand the noise reconstruction result.The thick solid line shows the amplitude,the thin solid line the real value,the dashed line the imaginary part.

# 2.2大样本实验

为了更直观的观察该方法的重构效果，我们从噪声，两个源的法拉第深度之间的间隔 $\Delta \phi$ $\phi$ 空间的分辨率 $\delta \phi$ （ $\delta \phi$ 的不同，会导致总的格点数N的不同）三方面对重构结果的影响分别进行了大样本统计学实验。我们以重构出的源的数目和 $\phi$ 的加权平均的差值来描述重构结果的好坏[10]。

我们首先考察是信噪比对重构结果的影响，这里我们假定法拉第色散函数只包含一个法拉第薄源，固定其法拉第深度为 $\phi = 2 0 \mathrm { r a d } m ^ { - 2 }$ ，随机模拟了1000 个信噪比范围在（3,60）之间的源（这里噪声依然设置为1，信噪比相当于法拉第色散函数的偏振强度)， $\phi$ 空间的分辨率为 $\delta \phi$ 依然为 $\Delta \phi _ { F W H M }$ 的 $1 / 4$ ，由于只含有一个法拉第薄源，我们这里直接以 $\phi$ 的差值$\left| \phi _ { r e c o r v e d } - \phi _ { o r i g i n a l } \right|$ 来描述重构效果，并排除了信噪比小于2的信号。结果如图2a 所示。

从图中可以看出对于含有一个源的情况来说，可以很准确的重构出源的数目，而 $\dot { \phi }$ 的差值总是在两个值上，即重构出的 $\phi _ { r e c o r v e d }$ 出现在相邻的两个格点上（这里设置的 $\phi _ { o r i g i n a l }$ 不在格点上)。为了减小重构误差，我们对重构结果在峰值附近进行了最小二乘拟合（以下实验均采用这种拟合)，结果如图2b所示。经过拟合后，对于大多数源来说， $\phi$ 的差值缩小了 $2 \sim 4$ 倍。由于重构出的法拉第深度 $\phi$ 总在相邻的两个格点上，我们是否也可以通过缩小 $\cdot \phi$ 空间分辨率的方式来减小 $\phi$ 的重构误差呢？

![](images/d6af681f1e4b20c93f257d7c3e6aa8b510a64fd5b014840cf50709b61649df92.jpg)  
图2从左到右为a）无拟合；b）拟合后。每幅图从上往下，上为重构数目，下为 $\phi$ 的差值 Fig.2 From left to right: a)no fitting; b)fitting.From top to bottom in each panel: the number of reconstructions,the difference of $\phi$

我们下面检查两个源的法拉第深度之间的间隔 $\Delta \phi$ 和 $\phi$ 空间的分辨率 $\delta \phi$ 对重构结果的影响。这里我们假定一个法拉第色散函数包含2个法拉第薄源，固定其中一个的源的偏振强度（204号 $p = 1 3 . 2 3 5$ ，偏振位置角 $\chi = 2 . 7 4 9$ ，法拉第深度 $\phi = 1 0 . 2 5 6$ rad $m ^ { - 2 }$ 。第二个源是随机模拟了1000个偏振强度（相当于信噪比）范围在（3,30)，偏振位置角范围在 $( 0 , 2 \pi )$ ，间隔$\Delta \phi$ 范围在(5,200)之间的源。同时，对不同分辨率 $\delta \phi$ 的情况（即 $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的 $1 / 2 , 1 / 3 , 1 / 4$ 1/5，1/6，1/7，1/8，1/9）分别进行了以上实验，这里排除信噪比小于1的信号。结果如图3所示。

![](images/158784be88ef56ffbb86e805bd2b2ff2a0a3d1fbab90ae7150ba0c01802a5050.jpg)

![](images/ee2c54eaa6e1e2c7057ca89db1c5dd2cbe61be2a5c4cb2048ff9d5fbf28ce0f7.jpg)  
图3第一排从左到右为a)&Φ取 $\Delta \phi _ { F W H M }$ 的1/2；b) $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/3；第二排从左到右为c) $\delta \phi$ 取$\Delta \phi _ { F W H M }$ 的 $1 / 4 ; { \mathsf { d } } ) \delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/5；第三排从左到右为e) $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/6; f) $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的$1 / 7$ ；第四排从左到右为 g) $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/8；h) $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/9。每幅图从上往下，上为重构数目，下为 $\phi$ 的加权平均的差值 $d _ { w m }$

Fig.3From left to right in first row: a) $\delta \phi$ takes $1 / 2$ of $\Delta \phi _ { F W H M } ; { \bf b } ) \delta \phi$ takes $1 / 3$ of $\Delta \phi _ { F W H M } ,$ in second row: c) $\delta \phi$ takes $1 / 4$ of $\Delta \phi _ { F W H M } ; \ \mathbf { d } ) \ \delta \Phi$ takes $1 / 5$ of $\Delta \phi _ { F W H M }$ ， in third row: $\mathbf { e } ) \delta \Phi $ takes $1 / 6$ of $\Delta \phi _ { F W H M } ; \mathrm { \bf ~ f } ) \delta \phi$ takes $1 / 7$ of $\Delta \phi _ { F W H M }$ ,in fourth row: g) $\delta \phi$ takes $1 / 8$ of $\Delta \phi _ { F W H M } ; \mathbf { h } ) \delta \Phi$ takes $1 / 9$ of $\Delta \phi _ { F W H M }$ .From top to bottom in eachpanel: the number of reconstructions,The difference ( $\phantom { a b s } ( d _ { w m }$ ）ofthe weighted average of $\phi$

确度进行了比较，如图4所示。从图中可以看出当 $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/3和1/4时，精确度最高，达到 $8 3 \%$ 左右。在以上对于噪声影响的实验时，我们曾提出是否可以通过缩小分辨率的方式来减小重构误差的问题，而在这个实验中可以看出，分辨率 $\delta \phi$ 并不是取得越小越好。

![](images/ea8e86f9a32c54e026757ba5305a3d294f4dff2cdccd044c0c3303644d2dc873.jpg)  
图4x轴表示 $\delta \phi / \Delta \phi _ { F W H M }$ 的比值，y轴表示重构数目的精确度 Fig.4X-axis represents the ratio ( $\mathrm { \Delta } \phi / \Delta \phi _ { F W H M }$ ,and $\mathrm { Y }$ -axis represents the accuracy of the number of reconstructions

这里我们以 $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/4时实验为例，随机选取了几幅重构图像，如图5所示。从图中可以看出对重构图像进行最小二乘拟合后的法拉第深度 $\phi _ { f i t t i n g }$ 更接近于输入模型的法拉第深度 $\phi _ { o r i g i n a l }$ ，但拟合（或重构）出的源的偏振强度 $p _ { f i t t i n g }$ 都要低于输入模型的源的偏振强度poriginal 。在图 $\boldsymbol { 4 \mathrm { c } } ( 4 \mathrm { a } , 4 \mathrm { b } )$ 中,可以看出两个源的间隔 $\Delta \phi > 5 0$ 时， $d _ { w m }$ 随着间隔 $\Delta \phi$ 的增大呈现出一个周期性振荡。这里我们认为出现这种振荡的原因可能跟第二个源的法拉第深度的位置有关。为此，我们在 $d _ { w m }$ 随着间隔 $\Delta \phi$ 变化的图上分别标记了当第二个源在格点 $\phi _ { i }$ ，$\phi _ { i } + 1 / 2 \delta \phi$ ， $\phi _ { i } + 1 / 4 \delta \phi$ 附近的 $d _ { w m }$ ，如图6所示。我们发现这种振荡在是一个周期为 $\delta \phi$ 的振荡。

![](images/98ed6a13fb9910fc198a5b5aa8b91320d6eacd348137097c04aac3c815ee47e2.jpg)  
图5以 $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/4时实验为例，随机选取的重构图像 7ig.5 Examples of reconstructed images, when $\delta \phi$ takes $1 / 4$ of △ΦFWHM

![](images/f24a6b2a21d284907925731cc8ba757dd740970ccc340998a29da97684e80aac.jpg)  
图 $6 d _ { w m }$ 随着间隔 $\Delta \phi$ 变化  
Fig.6 This picture shows $d _ { w m }$ varies with $\Delta \phi$

# 3结论

在多个频率上测量弥漫射电辐射的偏振是研究银河系磁场的一种有效的方法。目前的法拉第旋率综合法是利用偏振强度与法拉第色散函数之间是傅里叶变换对，把观测到的偏振强度做傅里叶逆变换得到法拉第色散函数[]。因受观测波段的限制，得出的解需要进行解卷积。所以需要一种更强有力的方法来解决这一问题。

在本文中，我们基于压缩感知的法拉第色散函数重构方法应用到了实际观测频率范围中，并对可能会影响该方法重构效果的因素分别进行了实验。实验结果表明该方法的重构效果会随着法拉第薄源的个数，源偏振强度的大小，相位以及两个法拉第薄源的法拉第深度之间的间隔 $\Delta \phi$ 的不同而出现较大差异，具有较大的随机性。在大样本统计学实验中，我们发现当 $\phi$ 空间的分辨率 $\delta \phi$ 取 $\Delta \phi _ { F W H M }$ 的1/3和1/4时，重构结果精确度最高，我们并对其重构结果各峰值附近再次进行最小二乘法拟合后，拟合后得到的法拉第深度 $\phi$ 值更接近原始值。通过压缩感知法重构后的再次拟合，我们可以得到更为精确的法拉第深度 $\phi$ 值，因此该方法可以作为现有方法的一种补充，同时该方法对于重构得出偏振强度普遍偏低，重构效果具有较大的随机性，所以，我们还需要不断的改进，提高其稳定性和精确度以便更好地应用于实际观测数据中。

# 参考文献:

[1]BrentjensMA，deBruynAG. Faraday rotation measure synthesis [J]. Astronomy and Astrophysics,2005,441(3):1217-1228.

[2]FrickP,SokoloffD,StepanovR,etal.Wavelet-basedFaradayrotation measure synthesis[J].MonthlyNoticesof the Royal Astronomical Society,2010,401(1): L24-L28.   
[3]FrickP,SokolofD，StepanovR，et al.Faradayrotation measure synthesisfor magnetic fieldsof galaxies[J].Monthly Notices of the Royal Astronomical Society,2011,414(3):2540-2549.   
[4] O SulivanSPBrownS, RobishawT,et al. Complex Faraday depth structure of active galactic nuclei as revealed by broad-bandradio polarimetry[J].MonthlyNotices of theRoyal Astronomical Society,2012,421(4):3300-3315. [5]CandesE,TaoT. Near-Optimal Signal Recovery From Random Projections: Universal Encoding Strategies?[J]. IEEE Transactions on Information Theory,2006,52(12): 5406-5425.   
[6] DonohoD.Compressed sensing [J].IEEE Transactions on Information Theory,2006,52(4): 1289-1306. [7]LiF,BrownS,CornwellTJ,et al. The application of compressive sampling to radio astronomy.II.Faraday rotation measure synthesis [J]. Astronomy & Astrophysics,2011,531: A126(8pp).   
[8] AndrecutM,StilJM,TaylorAR.Sparse Faraday Rotation Measure Synthesis [J].The Astronomical Journal, Volume,2012,143(2): 33(12pp).   
[9] Wilson WE,Ferris R H,Axtens P,et al. The Australia Telescope Compact Array Broad-band Backend: description and first results [J].Monthly Notices of the Royal Astronomical Society,2011,416(2):832-856. [10] Sun X H,Rudnick L,AkahoriT,et al.Comparison of Algorithms for Determination of Rotation Measure and Faraday Structure.I.1100-1400 MHz [J]. The Astronomical Journal, 2015,149(2): 60(13pp).

# Reconstruction of Faraday Dispersion Function Based on Compressive Sensing Method

Yu Yanchuan， Sun Xiaohui (SchoolofPhysics and Astronomy Yunnan University,Kunming 65oooo, China, Email:yuchuan9213 $@$ 163.com)

Abstract: Faraday dispersion function (FDF) contains information on magnetic fields within the emitting sources and the medium between sources and observers. However, it is very challnging to properly reconstruct FDFs from observed data. Recently, the compressive sensing algorithm has been proposed to recover FDFs. Whether this method is practicable or not is yet to be explored. In this paper, we aim to thoroughly benchmark compressive sensing algorithm. We make a large sample of simulations with parameters consistent with observations and apply the compressive sensing method to the data. We find that the reconstructed results are affected by various factors， such as the number of emiting components and the separation of these components in Faraday depth domain. We suggest that the peak of FDFs be located with parabolic fitting and the resolution of Faraday depth domain be $1 / 3$ or 1/4 of full width half maximum of the rotation measure spread function.

Key Words:Compressive sensing; Polarization; The Faraday dispersion function; Faraday depth