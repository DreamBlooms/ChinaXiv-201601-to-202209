# 射流气泡的被动声源成像方法

初 宁　刘竞婷　秦世杰 吴大转(浙江大学能源工程学院化工机械所，杭州310027)

摘要被动声源成像方法近年来越来越成为研究气泡声源的有效手段之一。本文所阐述的气泡声源成像方法，不仅能从有限数量的水听器测量信号中对气泡声源进行高分辨率的空间定位，还能重构出气泡声源的平均功率分布情况。为此，本文首先需要建立一个合适的气泡声源模型、进一步简化气泡声源在空间传播的多径效应，以便充分利用阵列信号处理的优势；然后，本文简要介绍基于波束形成、最小方差无失真响应和子空间分解等信号处理技术的气泡声源成像方法；并针对研究的射流气泡特点、流速和喷管性状等条件，还讨论了有限数量的水听器阵列对声源成像结果的影响。最后，本文通过仿真模拟说明了被动声源成像方法可以揭示气泡声源在气泡形成、生长和脱离喷管等阶段的声源平均功率高分辨率空间分布情况。该方法能够有效“看见”气泡声源、弥补了高超速相机拍摄气泡图像的不足。

关键词射流气泡；被动声源成像；声源定位；阵列信号处理中图分类号：O359.1 文献标识码：A 文章编号:0253-231X(2017)05-0978-06

# Passive Acoustic Imaging for Jet Bubbles

CHU NingLIU Jing-Ting_QIN Shi-JieWU Da-Zhuan (Institute of ProcessEquipment,Collegeof Energyngiheering,Zhejiang University，Hangzhou310027,China)

AbstractNowadays passive acoustic imaging has become one of the most efective methods in studying thesound emissionof jet bubblosat low airfowrates.This paper presents a proofofconcept thatourproosroaetialfieatbt but also reconstruct acoustic power by only using the limited measurements at hydrophone array. First of all, an appropriate acousti& model of jet bubbles should be investigated carefully, and the acoustic propagation should belsimplified appropriately in order to fit for array signal processing. Then the state-of-the-art spatial filters such as Beamforming, Capon and Music methods are extended for bubble acoustic imaging. And the deployment of hydrophone array is discussed according to the conditions of jet bubbles,airflow rates and sparged tank. Finally acoustid imaging results from simulations can show vividly acoustic power distributions with high spatial esolution and moderate dynamics during the jet bubble formation,detachment and vibration. Base on this proof of concept,limited number of hydrophone array can be effctively used in underwater experiments. Moreover our proposed approach allws to visualize the bubble sound distribution with respect to bubble images from high speed camera. 子

Key wordsjet bubble acoustics; passive acoustic imaging; source localization; array signal processing

# 0引言

被动声源成像是一种利用非接触式传感器阵列来获得声源定位和声强度绘制的先进技术。被动声源成像能够对振动和转动、摩擦和爆破、喷气和射流等过程中产生的声源提供深入的机理分析和特性统计[1-5]。近年来，高分辨率的近场被动声源成像方法已成为水下低速射流气泡声源研究的突破性技术之一[6-9]。根据声源的物理机理和求解的数理方法不同，被动声源成像通常能够分为近场声成像方法（NAH）即所谓的“声相机"[10]，基于“波束形成”的空间滤波器方法[11]，以及基于“解卷积”的反问题推断方法[12-15]。考虑到成像性能的稳健性、计算的快速性和水听器阵列布置的简易性，本文重点关注基于“波束形成”被定声源成像方法。

![](images/1a505cccdcaf7f9c3befd6aab2cf007f9093c6bbf9f80f4d83fc76df745d52cf.jpg)  
图1气泡声源测量与信号处理示意图  
Fig.1 Acoustic bubble sources andsenor array signal processing

# 1气泡声源的传播波模型

在建立模型之前，必要的假设如下展1）气泡声源假设是非相关的单极子；虽然这是一种理想的假设情况，但是从统计观点来天量的单极子的整体性能能够在某种程度上体现出实际声源的特性。2）水听器假设是全向的伺一增益的。3）环境背景噪声假设是加性高斯白噪声。4)声源传播服从球面波、多径效应主要考虑一阶的反射和折射。

在图1(a）中，气泡声源和水听器阵列布置在同一个平面内。设有 $K$ 个非相关性的单极子信源$\boldsymbol { s } ^ { * } = \left[ \boldsymbol { s } _ { 1 } ^ { * } , \cdot \cdot \boldsymbol { s } _ { k } ^ { * } , \cdot \cdot \boldsymbol { s } _ { K } ^ { * } \right] ^ { \mathrm { T } }$ ，这 $K$ 个信源位于未知位置$\boldsymbol { P ^ { * } } = \left[ \boldsymbol { p } _ { 1 } ^ { * } , \cdot \cdot \cdot \boldsymbol { p } _ { k } ^ { * } , \cdot \cdot \cdot \boldsymbol { p } _ { K } ^ { * } \right] ^ { \mathrm { T } }$ ，其中 $p _ { k } ^ { * }$ 代表声源 $k$ 的3坐标，［]T代表转置算子。为了重构这 $K$ 个声源需要使用数量大于 $K$ 的 $M$ 个水听器 $( M > K )$ 位于已知的位置 $\bar { P } = \left[ \bar { p } _ { 1 } ^ { * } , \cdot \cdot \cdot \bar { p } _ { m } ^ { * } , \cdot \cdot \cdot \bar { p } _ { M } ^ { * } \right] ^ { \mathrm { T } }$ 。为了提高空间分辨率，信源平面被离散化成为 $N$ 个足够小的网格点 $\boldsymbol { s } = \left[ s _ { 1 } , \cdots s _ { n } , \cdot \cdot \cdot s _ { N } \right] ^ { \mathrm { T } }$ ，且 $N \gg K$ ，其网格点的位置已知为 $P = \left[ p _ { 1 } , \cdot \cdot \cdot p _ { n } , \cdot \cdot \cdot p _ { N } \right] ^ { \mathrm { T } }$ ，而每个网格点可以被看作是潜在的声源单极子。所以 $s ^ { * }$ 和 $s , \ p ^ { * }$ 和 $p$ 的关系可表示为：

$$
\left\{ \begin{array} { l l } { s _ { k } ^ { * } = s _ { n } } \\ { p _ { k } ^ { * } = p _ { n } } \end{array} \right. \quad s _ { n } \neq 0
$$

因 $s$ 的信号长度 $N$ 远大 $s$ 的非零分量个数 $K$ ，所以

$$
\begin{array} { c } { { s = \left[ 0 , \cdots 0 , \cdots , s _ { 1 } ^ { * } , \cdots 0 , \cdots s _ { k } ^ { * } , \cdots 0 , \right. } } \\ { { \left. \qquad \cdot \cdot s _ { K } ^ { * } , \cdot \cdot \cdot 0 , \cdot \cdot \cdot 0 \right] ^ { \mathrm { T } } } } \end{array}
$$

因此， $s$ 是一个 $K$ 维度的 $N$ 长稀疏信号，即 $s$ 包含了较少的 $K$ 个非0分量和较多的 $N - K$ 个0分量。因此，重构 $s ^ { * }$ 等价于重构 $K$ 维度稀疏信号 $s$ 。

在建立了声源模型之后，信号处理过程如图1(b)所示。设第 $m$ 个水听器测量到 $T$ 个采样时间信号点，并将其等分为 $I$ 个时域信号段，每段有 $L$ 个时间信号点，满足 $\mathcal { Q } \overset { \displaystyle \otimes } { = } I \times L$ 。设 $z _ { i , m } ( t )$ 为第 $m$ 个水听器在第 $\mathbf { \chi } _ { i }$ 时间段 $( i \in [ 1 , \cdots , I ] )$ 的第 $\mathbf { \Psi } _ { t }$ 个时间点（204号 $( t \in [ ( i \dot { - } \mathfrak { v } ) \mathbb { Z } , \cdot \cdot \cdot , i L ] )$ 所接收信号向量。由于时间采样信号 $z _ { i , m } ( t )$ 通常具有宽频带信号特性，所以在I个时间段内通过离散傅立叶变换把 $z _ { i , m } ( t )$ 转化到频谱信号 $z _ { i , m } ( f _ { l } )$ ，并宽带频谱独立分为 $L$ 个子频带（204号 $( l \in [ 1 , \cdots , L ] )$ 。那么对于所有的 $M$ 个水听器, $z _ { i } ( f _ { l } )$ 代表全部的频域接收信号。由于 $L$ 个频带信号可以独立并行的处理，后文中省略 $f _ { l }$ 。因此， $z _ { i } ( f _ { l } )$ 能够表示为：

$$
z _ { i } = A ( P ) s _ { i } + e _ { i }
$$

其中， $A ( P ) = [ a ( p _ { 1 } ) , \cdot \cdot \cdot a ( p _ { n } ) , \cdot \cdot \cdot , a ( p _ { N } ) ]$ 代表水听器阵列对于声源 $s$ 的指向矩阵； $a ( p _ { n } )$ 代表水听器阵列对于位于 $p _ { n }$ 位置的声源 $s _ { n }$ 的指向向量；对于球面传播的声源， $a ( p _ { n } )$ 表达为：

$$
a ( p _ { n } ) = \left[ \frac { \exp \left( - j 2 \pi f _ { l } \tau _ { n , 1 } \right) } { r _ { n , 1 } } , \cdot \cdot \cdot , \right.
$$

$$
\frac { \exp \left( - j 2 \pi f _ { l } \tau _ { n , m } \right) } { r _ { n , m } } , \cdot \cdot \cdot \frac { \exp \left( - j 2 \pi f _ { l } \tau _ { n , M } \right) } { r _ { n , M } } \Bigg ] ^ { \mathrm { T } }
$$

其中, $r _ { n , m }$ 代表从声源 $n$ 到水听器 $m$ 的距离, $\tau _ { n , m }$ 代表历经 $r _ { n , m }$ 所用的时间；后文中， $a ( p _ { n } )$ 被简化$\scriptstyle a _ { n }$ 。特别的， $r _ { n , m }$ 应该考虑到反射和折射等多径效应，在作者文章中讨论过[13]。

综上所述，公式（3）中的声源传播模型是一个从 $M$ 次测量中求解 $N$ 个未知数的欠定性线性方程$( N > M )$ 。因此通常情况下，需要增加水听器个数来降低求解的不确定性。但是受到实验条件限制，水听器数量不可能明显增加。并且，被动声源定位的目的是定位声源位置和绘制声功率分布，那么公式 (3)可以通过波束形成技术[11]转化成为

$$
y _ { n } = \tilde { a } _ { n } ^ { \prime } R _ { z } \tilde { a } _ { n }
$$

其中， $y _ { n }$ 是波束形成方法所估计出来的在位置 $p _ { n }$ 处的声源功率。 $R _ { z }$ 是测量声源的互功率谱矩阵 (协方差矩阵)，而an=anl2 是波束形成对于声源 $s _ { n }$ 的指导向量。 $\left( \cdot \right) ^ { \prime }$ 是共轭转置算子。由于声源 $s$ 假设是非相关的单极子，并且与背景噪声 $\boldsymbol { \mathscr { e } }$ 是独立不相的，因此 $R _ { z }$ 可以进一步推导出 学护其中，当时间分段数目足够大 $( I \gg 1 )$ ， $E [ z _ { i } z _ { i } ^ { \prime } ] \approx$ $\frac { 1 } { I } \sum _ { i } ^ { I } z _ { i } z _ { i } ^ { \prime }$ $E [ \cdot ]$ 算子。 $\begin{array} { r } { { \cal { R } } _ { s } ~ = ~ { \cal { E } } [ s s ^ { \prime } ] } \end{array}$ 待测声源的互功率谱。由于声源s的元素是相互非相关的，因此 $R _ { s } = E [ s s ^ { \prime } ] =$ diag $[ x _ { 1 } , \cdot \cdot \cdot , x _ { n } , \cdot \cdot \cdot x _ { N } ]$ ，其中 $x _ { n } = E [ s _ { n } s _ { n } ^ { \prime } ]$ 是在位置 $p _ { n }$ 的声源平均功率; $\mathrm { d i a g [ \cdot ] }$ 是取矩阵对角元素的算子; $J _ { M }$ 是 $M \times M$ 维的单位矩阵；于是将公式(6)带入到公式(3)得到：

其中，波束形成指向向量 $\tilde { a } _ { n } = \frac { a _ { n } } { | | a _ { n } | | ^ { 2 } }$ 并且 $\tilde { a } _ { n } ^ { \prime } \tilde { a } _ { n } =$ $\frac { 1 } { | | a _ { n } | | ^ { 2 } }$ 所以公式（7）得到

$$
y _ { n } = \sum _ { q = 1 } ^ { N } \frac { | | a _ { q } ^ { \prime } a _ { n } | | ^ { 2 } } { | | a _ { n } | | ^ { 4 } } x _ { q } + \sigma ^ { 2 } \frac { 1 } { | | a _ { n } | | ^ { 2 } }
$$

最后，对于 $N$ 个潜在的声源 (网格)，我们用矩阵形式改写公式 (8)，从而得到声源平均功率的传播模型为

$$
y _ { n } = \tilde { a } _ { n } ^ { \prime } \left( \sum _ { q = 1 } ^ { N } x _ { q } a _ { q } a _ { q } ^ { \prime } \right) \tilde { a } _ { n } + \sigma ^ { 2 } \tilde { a } _ { n } ^ { \prime } \tilde { a } _ { n }
$$

$$
y = C x + \sigma ^ { 2 } 1 _ { a }
$$

其中， $\boldsymbol { x } = \left[ x _ { 1 } , \cdot \cdot \cdot x _ { n } , \cdot \cdot \cdot x _ { N } \right] ^ { \mathrm { T } }$ 代表未知的声源功率向量；根据声源功率的定义，以及无关性单极子信源的假设，功率 $\mathbf { \Psi } _ { x }$ 继承了信号 $s$ 的 $K$ 维稀疏性信号的特点。因此狭义上的声源成像能够把从公式 (3)中重构声源 $s$ 转化为从公式（9）中重构声源平均功率 $x$ 。 $\sigma _ { e } ^ { 2 } = E [ e _ { i } ^ { \prime } e _ { i } ]$ 代表背景噪声的功率 (方差)。向量 $I _ { a } = \left[ \frac { 1 } { | | a _ { 1 } | | ^ { 2 } } , \cdot \cdot \cdot \frac { 1 } { | | a _ { n } | | ^ { 2 } } , \cdot \cdot \cdot \frac { 1 } { | | a _ { N } | | ^ { 2 } } \right] ^ { }$ T 代表水听器阵列在不同网格位置上的衰减因子。矩阵 $C$ 代表水听器阵列对声源功率的指向矩阵，其元素 $c _ { \boldsymbol { q } n } \in C$ 为

$$
c _ { \boldsymbol { q } n } = \frac { | | a _ { \boldsymbol { q } } ^ { \prime } a _ { n } | | ^ { 2 } } { | | a _ { n } | | ^ { 4 } } =
$$

$$
\left| \frac { 1 } { \sum _ { m = 1 } ^ { M } \frac { 1 } { r _ { n m } ^ { 2 } } } \sum _ { m = 1 } ^ { M } \frac { 1 } { r _ { q m } r _ { n m } } \right|
$$

$$
\exp \left\{ j \frac { 2 \pi f _ { l } } { c _ { 0 } } ( r _ { q m } - r _ { n m } ) \right\} ^ { 2 }
$$

其中, $a _ { q }$ 和 $\check { \alpha } _ { n } ^ { \times }$ 是传感器阵列在网格位置 $p _ { q }$ 和 $p _ { n }$ 上的指向向量，其定义在公式（4）中。 $r _ { n m }$ 是从网格 $n$ 到水听器 $m$ 的距离； $f _ { l }$ 代表在第 $l$ 子频带上的频率点 $M$ 是水听器的总数量；公式（10)揭示出功率指向矩阵 $C$ 的重要性质：

$$
c _ { q n } = \left\{ { \begin{array} { l l l } { \geqslant 0 } & { f o r } & { q \neq n } \\ { 1 } & { f o r } & { q = n } \end{array} } \right.
$$

事实上, $c _ { \boldsymbol { q } n }$ 可以被解释为邻域网格 $q$ 对计算网格 $n$ 位置处的波束形成功率的权重。例如公式(8）中$y _ { n } = \sum _ { q = 1 } ^ { N } c _ { q n } x _ { q } + \frac { \sigma ^ { 2 } } { | | a _ { n } | | ^ { 2 } }$ 意味着，在网格 $n$ 处的波束形成功率是 $N$ 个潜在声源功率的加权平均值；该权重 $c _ { \boldsymbol { q } n }$ 由阵列的结构和阵列与声源之间的位置决定；在理想条件下, $c _ { \boldsymbol { q } n } \approx \delta _ { \boldsymbol { q } n }$ 接近 Dirac 函数、 $C \approx I _ { N }$ 退化为单位矩阵，从而公式(6)简化为 $y = x + \sigma ^ { 2 } 1 _ { a }$ 从中非常容易的求解出声源功率 $\mathbf { \Psi } _ { x }$ 。这从侧面说明，合适的阵列结构能够大大有助于获得高分辨率和准确的声源成像结果。

![](images/a6d857f8e9136620237913dd3fa1d7b31fba57fd1b863cd04e4d2901885fbb89.jpg)  
图2极子声源在均匀线阵列的分辨率比较  
Fig.2 Comparison of spatial resolution for monopole source signal at linear uniform sensor

综上所述，相对于声源传播公式 (3)，声源功率传播公式(9）是一个线性齐次方程组，并且未知声源功率 $\mathbf { \Psi } _ { x }$ 是 $K$ 维稀疏性向量。波束形成的重构结果是把 $y$ 当作 $\mathbf { \Psi } _ { x }$ 的估计值，虽然计算简单和稳健,但是空间分辨率往往比较低。为此，基于最小方差无失真响应[11]（Capon 滤波技术）的声源成像方法能够有效提高分辨率，并且合理的估计出声源功率值。Capon 滤波的主要思想是保持某一声源方向的传感器阵列的测量功率，并且抑制其他方向的测量功率，因此Capon对声源成像的估计值为：

$$
y _ { n } ^ { \mathrm { C a p o n } } = \frac { \mathcal { A } ^ { \mathbb { N } ^ { 2 } } } { a _ { n } ^ { \mathrm { A } } \mathbb { R } _ { z } ^ { 2 } a _ { n } }
$$

进一步，为了得到空间上的超高分辨率，基于子空间分解[1](MUSIC）的声源成像方法能够从测量信号的互功率谱中通过奇异值分解出相互正交的声源空间 $E _ { s }$ 和噪声空间 $E _ { e }$ ，当位于网格 $\mathbf { n }$ 的声源空间与噪声空间的正交性越大时，该网格 $n$ 处越有可能存在声源信号。因此MUSIC对声源成像的伪功率为： htt

$$
y _ { n } ^ { \mathrm { M U S I C } } = \frac { 1 } { \left\| a _ { n } ^ { \prime } E _ { e } \right\| ^ { 2 } }
$$

# 2射流气泡声源成像仿真

在图2(a）中， $M$ 个水听器均匀分布为线性阵列，其间距为 $\Delta$ ，满足 $\Delta \leqslant \lambda / 2$ 空间采样条件，其中 $\lambda _ { l } = c _ { 0 } / f _ { l }$ 是声源中心频率对应的波长, $\theta$ 是声源的到达阵列中心的方向角；那么，声源 $s _ { n }$ 的信号传播到水听器 $\mathrm { ~ m ~ }$ 的时间延迟可以表示为

$$
\begin{array} { c } { \displaystyle { \tau _ { n m } = \tau _ { n 0 } + ( m - 1 ) \frac { \Delta \sin \theta } { c _ { 0 } } = } } \\ { \displaystyle { \tau _ { n 0 } + ( m - 1 ) \frac { \Delta \sin \theta } { \lambda _ { l } f _ { l } } } } \end{array}
$$

其中, $\tau _ { n 0 }$ 代表声源 $s _ { n }$ 到达参考水听器 (例如图2(a)的水听器的时间延迟。设 $r _ { n m } \approx \bar { r } = \frac { 1 } { M } \sum _ { m = 1 } ^ { M } r _ { n m }$ 近独手平均距离，那么式（8）可以合理简化为：

$$
 y _ { n } \approx \frac { 1 } { | | a _ { n } | | ^ { 2 } } \frac { 1 } { \bar { r } _ { n } ^ { 2 } } | \frac { \sin [ \frac { \pi \Delta \sin \theta } { \lambda _ { l } } ( M - 1 ) ] } { \sin [ \frac { \pi \Delta \sin \theta } { \lambda _ { l } } ] } | ^ { 2 } + \frac { \sigma ^ { 2 } } { | | a _ { n } | | ^ { 2 } }
$$

该式中含有Dirichlet函数，其角分辨率可以表示为：

$$
\stackrel { \delta _ { \theta } ^ { \mathrm { B F } } } { \langle \bar { \Gamma } ^ { \mathrm { \tiny ~ ( M - 1 ) } \Delta \cos \theta } }
$$

图 $2 ( \mathrm { b } )$ 中显示了基于波束形成、最小方差无失真响应和子空间分解等技术的空间角定位能力。该仿真中有两个独立的高斯白噪声的声源！ $\left( K = 2 \right)$ ）从位于$1 4 5 \%$ 和 $+ 5 ^ { \circ }$ 的两个方向传播的声信号，且振动频率为 $2 0 0 \ \mathrm { H z }$ (低频声源)，平均功率均为单位1；信号比为 $0 \mathrm { d B }$ ，即声源功率和背景噪声功率相当； ${ \cal T } \mathrm { = } 1 0 0 0 0$ 个时间采样点；声源平面被等分成为 $N { = } 3 6 1$ 个网格,且在 $[ - 4 5 ^ { \circ } , \ + 4 5 ^ { \circ } ]$ 之间。通过公式(14)的讨论，波束形成的空间分辨率仅仅为 $1 1 ^ { \circ }$ ，不能分辨 $1 0 ^ { \circ }$ 以内间距的两个声源。但是，Capon 和 MUSIC 方法都能很好地分辨出两个声源，并且，Capon较为准确地分辨出两个声源的功率，而MUSIC只获得了高超空间分辨率。

同样的结果如图3所示，分别模拟了喷管直径是 $0 . 1 \mathrm { m m }$ 和 $\mathrm { 5 ~ m m }$ 的气泡生成、脱落情况，流速0.1$\mathrm { m } / \mathrm { s }$ ，气泡平均直径 $0 . 3 ~ \mathrm { m m }$ ，网格划分 $0 . 1 ~ \mathrm { m m } \times 0 . 1$ $\mathrm { m m }$ 。10个水听器组成2列线性均匀阵列，声源成像的频率是 $1 0 0 0 ~ \mathrm { H z }$ 。

![](images/b448fb4e6db0a5de7555e5382eb5dc1e14cfcbed8d8ba762545a37ce70ea1697.jpg)  
图3不同喷管直径下的波束形成、最小方差无失真、子空间分解等成像结果  
ig.3 Beamforming,Capon and MUSIC methods for acoustic bubble imaging at nozzles $\mathrm { ( 0 . 1 { \sim } 5 ~ m m }$

# 3结论

本文阐述了一种基于空间滤波器技术的声源成像方法，不仅能从数量有限的水听器测量中定位气泡声源的位置，还能够重构声源平均功率的分布情况。事实上，基于波束形成的声源成像是一种稳健地、快速地和直接的方法，它可以被看作是被测声源的功率分布与测量阵列的传递函数的卷积结果。当测量阵列足够理想时，波束形成成像即为被测声源功率分布。所以通常情况下，波束形成的成像分辨率会比较低、其功率分布比被测声源的放大许多。相反的，子空间分解方法理论上可以达到无限好的空间分辨率，但是其不能重构声源的功率分布。折衷来看，最小方差无失真成像方法既能够提供足够高的空间分辨率、又能够相对准确地估计出声源的平均功率分布情况，并且所利用的水听器阵列结构简单、架设容易，还能根据射流气泡的特性、流速以及喷管形状和容器大小来调整水听器的阵列结构，以便自适应获得气泡声源的成像结果。 >

任任辰的士P」，ンー面而女1）应用具有相关性的单极子或空间分布式信源的物理特性来建立气泡群的声源模型，其在高速射流条件;2）在密闭容器空间中，校正声源传播的多径效应以便减弱混响等干扰;3)针对在气泡生成、高速射流以及气泡空化条件下的实际数据，改进基于空间滤波技术、探索解卷积技术的声源成像方法。

# 参考文献

[1]Lanslots J，Deblauwe F，Janssens K.Selecting Sound Source Localization Techniques for Industrial Applica tions [J].Sound and Vibration,2010,44 (6):6-10   
[2]Magalhaes,M, Tenenbaum R. Sound Sources Recohstruction Techniques: A Review of Their Evolution and New Trends [J].Acta Acustica United with Acustica,2004, 90(2):199-220   
[3]Crake C,Victor M S,Owen J,Coviello C,CollinJ,Coussios C C, Stride E.Passive Acoustic Mapping of Magnetic IVicroDubDies Ior Cavitation EInanceent and Localiza tion [J].Physics in Medicine and Biology， 2015,60(2): 785-806 [4] Nikolovska A,Manasseh R,Ooi A. On the Propagation of Acoustic Energy in the Vicinity of a Bubble Chain [J]. Journal of Sound and Vibration, 2007, 306(3-5): 507-523 [5] Deane G B, Czerski H.A Mechanism Stimulating Sound Production from air Bubbles Released from a Nozzle [J]. The Journal of the Acoustical Society of America,2008, 123(6): 126-32 [6] Vazquez A，Manasseh R,Chicharro R. Can Acoustic Emissions be Used to Size Bubbles Seeping from a Sediment Bed [J].Chemical Engineering Science,2015,131, 187-196 [7] Vazquez A,Manasseh R, Snchez R M,Metcalfe G.Experimental Comparison Between Acoustic and Pressure Signals from a Bubbling Flow [J]. Chemical Engineering Science,2008,63(24): 5860-5869 [8] Manasseh R,Riboux G,Risso F. Sound Generation on Bubble Coalescence Following Detachment [J]. International Journal of Multiphase Flow,2008,34(10): 938-949   
[Lehman S, Devaney A. Transmisson Mode Time-reversal Super-resolution Imaging[J]. The Journal of the Acoustical Society of America, 2003,113(5): 2742-2753   
[10] Maynard JD,Williams EG,Lee Y.Nearfield Acoustic Holography: I. Theory of Generalized Holography and the Development of NAH [J].The Journal of the Acoustical Society of America,1985,78(4):1395-1413   
[11] Van Veen B,Buckley K.Beamforming:A Versatile Approach to Spatial Filtering [J]. IEEE ASSP Magazine, 1988, 5(2): 4-24   
[12] Antoni J.A Bayesian Approach to Sound Source Reconstruction: Optimal Basis, Regularization, and Focusing [J].The Journal of the Acoustical Society of America, 2012,131(4): 2873-2890   
[13] Chu N,Mohammad-Djafari A，Picheral J. Robust Bayesian Super-resolution Approach Via Sparsity EnforcCing a Priori for Near-field Aeroacoustic Source Imaging [J].Journal of Sound and Vibration,2013,332(18):4369- 4389   
[14] Chu N, Picheral J, Mohammad-Djafari A,Gac N.A Robust Super-resolution Approach with Sparsity Constraint in Acoustic Imaging [J]. Applied Acoustics,2014,76:197- 208   
[15] Longuet-Higgins M S. Monopole Emission of Sound by Asymmetric Bubble Oscillations.Part 1.Normal modes [J]. Journal of Fluid Mechanics,1989, 201: 525-541