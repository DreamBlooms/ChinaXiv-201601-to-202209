# 街道环境V2V通信信道建模与容量分析

何怡刚，许越，李兵，宁暑光，张超群(合肥工业大学电气与自动化工程学院，合肥230009)

摘要：车车(V2V)通信系统的性能取决于无线信道的特征，因此采用合适的模型来刻画通信信道尤为重要。针对街道 3D散射环境下的车载通信信道，考虑到道路两边高楼、树木等散射体，且收发两端处于移动状态，采用多天线技术，建立椭圆柱散射模型。运用几何分析法，推导了时间自相关函数（ACF）、空间互相关函数（CCF），比较视距(LOS)和非视距(NLOS)情况下ACF和CCF 的差异，验证仿真方法的可行性；研究了信道容量在不同天线阵列和散射环境下的区别，突出了3D模型更加精确。测量结果与理论分析的一致性表明本文3D模型的可用性，拓宽了车载通信系统的研究。

关键词：V2V通信；信道模型；相关函数；信道容量 中图分类号：TN929.5 doi: 10.3969/j.issn.1001-3695.2018.04.0253

# Street environment V2V communication channel modeling and capacity analysis

He Yigang,Xu Yue,Li Bing,Ning Shuguang, Zhang Chaoqun SchoolofElectrical Engineering&Automation,Hefei UniversityofTechnology,Hefei 23oo9,China

Abstract:The performance ofthe V2Vcommunicationsystem depends on the characteristicsof the wireless channel,so itis very important to use a suitable model to characterize thecommunicationchannel.This paper studied the vehicular communicationchannel inte 3D street scattring environment. Considering the scaterers such as tallbuildings and trees on both sidesof theroad,andthetransmitingandreceivingendsaremoving,usemulti-antenna technologyto establish the eliptic column scatering model. Using geometric analysis,this paper duduced the time auto-corelation function (ACF)and cross-correlation function（CCF）；compare the difference of ACFand CCF in thecase of line-of-sight(LOS）and non-line-of-sight(NLOS),this paper verifiedthe feasibilityof thesimulationmethod;studythediference inchannelcapacity underdiffrent antenna arrays and scatering environments，which highlight3D models more accurately.Theconsistency betweenthe measurements resultsandthe theoretical analysis shows theusabilityofthis 3Dmodeland broadens theresearch of vehicular communication systems.

Key words: V2V communication; Channel model; Related functions; Channel capacity

# 0 引言

大数据、5G及无人驾驶时代即将来临，交通信息的快速传递能提高运输效率并减少事故发生率，所以V2V（vehicle-to-vehicle）通信的研究逐渐受到关注。V2V通信信道相比传统信道而言，行驶环境比较复杂，表现出更大的动态性和更严重的衰落性，因而根据特殊的散射环境建立准确的模型以及提高信道的传输效率对V2V通信来说尤为重要[I]。多输入多输出技术（multiple-input multiple-output,MIMO）能提高通信系统的性能，所以将MIMO技术应用到V2V通信中也是目前

的研究热点之一[2]。

根据几何散射环境的不同，所建模型也会不一样。一般有单环模型[I]、双环模型[2]、椭圆模型[3]等等，在此之上还有 $2 \mathrm { D } ^ { [ 1 \sim 3 ] }$ 和 $ { 3 \mathrm { D } ^ { [ 4 \sim 7 ] } }$ 模型之分。现实环境中的散射体数目趋于无穷，分为各向同性和非各向同性环境。各向同性采用均匀分布[]，而非各向同性可采用VonMises分布、高斯分布、拉普拉斯分布等[5]，要根据现实环境选择合适的分布来刻画散射体。V2V通信环境通常包括街道环境[8]、高速公路[9,10]以及隧道[11,12]等，研究这些环境下信号的散射性质意义重大。在可以忽略散射环境中信号传播的仰角(elevation-angel)时，为简化计算应当建立2D的信道模型。而散射体的高度不可忽略时，应建立3D模型，这样刻画的信道才更加准确[]。文献[3]仅考虑了2D模式下椭圆信道的相关函数和信道容量，忽略了仰角的影响。本文考虑到街道环境中路边高楼、树木等散射体的高度严重影响信号传播方向，所以考虑仰角并建立复杂的3D模型。

本文选取车流量稀少的街道环境，忽略移动散射体，仅考虑静态散射体，采用3D椭圆柱散射模型来刻画V2V信道。信道的ACF（auto correlation function）、CCF（cross correlationfunction）和容量是衡量通信系统性能的重要指标。基于MIMO技术，本文将研究LOS（line of sight）与 NLOS（not line of sight）两种情况下，MIMO信道ACF、CCF 的差异，并验证所用仿真方法的可行性；借助仿真分析来探究天线阵列和散射环境等多种因素对信道容量的影响，以实际测量的数据来证明本文理论分析的准确性。

# 1 椭圆柱散射模型

图1是本文所考虑的3D街道椭圆柱模型，地平面上的椭圆长轴为a，短轴为 $\mathbf { b }$ ，焦距为f。 $T _ { X }$ 和 $R _ { X }$ 分别表示移动发射端和移动接收端，取发射端 $T _ { X }$ 为原点，收发端均位于椭圆的焦点上，两端之间距离为D（即为2f）。发射端 $T _ { X }$ 的速度和方向分别为 $\nu _ { T } , \alpha _ { T } ^ { \nu }$ ，接收端 $R _ { X }$ 的速度和方向分别为 $\nu _ { R } , \alpha _ { R } ^ { \nu }$ 。 $T _ { X }$ 和 $R _ { X }$ 都配备均匀线性天线阵列，分别有L和K个天线单元，阵列与 $\textbf { \em x }$ 轴的夹角分布为 $\theta _ { T }$ 和 $\theta _ { R }$ ，天线单元的间距分别为 $d _ { T }$ 和 $d _ { R }$ 。椭圆柱表面分布了无数的散射体， $S ^ { n }$ 是上面的第 $\mathfrak { n }$ 个静态散射体（通常指高楼、树木和路标等； $0 { < } \mathrm { n } { \le } \mathrm { N }$ ， $\mathbf { N }$ 趋于无穷）。 $T _ { X }$ 发射的信号经 $S ^ { n }$ 散射到 $R _ { X }$ 接收，因为 $( L - 1 ) d _ { T } \ll a - f$ 和$( K - 1 ) d _ { R } \ll a - f$ ，发射角的方位角(azimuthal-angel-of-departure,AAOD）为 $\alpha _ { T } ^ { n }$ ，仰角(elevation-angel-of-departure,EAOD)为 $\beta _ { T } ^ { n }$ ；同理，到达角的方位角（azimuthal-angel-of-arrival,AAOA）为 $\alpha _ { R } ^ { n }$ ，仰角(elevation-angel-of-arrival,EAOA)为 $\beta _ { R } ^ { n } \circ d _ { l n }$ 是第 $l ~ ( l { = } 1 , { \ldots } , \mathrm { L } )$ 个发射天线单元 $A _ { l }$ 与 $S ^ { n }$ 的距离， $d _ { n k }$ 是第 $k$ $\mathbf { \Xi } ( k { = } 1 , . . . , \mathrm { K } )$ 个接收天线单元 $A _ { k }$ 与 $S ^ { n }$ 的距离， $h _ { n }$ 是 $S ^ { n }$ 到水平面的垂直距离， $l _ { t n }$ 是发射端 $T _ { X }$ 与 $S ^ { n }$ 的水平距离， $l _ { n r }$ 是接收端 $R _ { X }$ 与 $S ^ { n }$ 的水平距离。本文以发射端 $T _ { X }$ 为坐标原点， $R _ { X }$ 在 $\mathrm { ~ x ~ }$ 轴的正半轴上， $\mathrm { ~ x ~ }$ 轴y轴所构平面为水平面。

![](images/12b26c1ac018549dfb2e713945e4df54df91077170678c35b008fa2be4b084e5.jpg)  
图1椭圆柱散射模型

本文MIMO信道参考模型的复增益可描述为矩阵$\begin{array} { r } { H ( t ) = [ h _ { \scriptscriptstyle { l k } } ( t ) ] _ { \scriptscriptstyle { L \times K } } } \end{array}$ ，在载波频率 $f _ { C }$ 下从发射端第 $\mathbf { \xi } _ { l }$ 个天线单元到接收端第 $k$ 个天线单元的信道复增益为 $h _ { l k } \left( t \right)$ ，在视距LOS情况下由直射成分和单次散射成分组成。 $\left. h _ { l k } \left( t \right) \right.$ 在LOS下服从莱斯分布，而在NLOS下服从瑞利分布。

$$
h _ { \mathit { l k } } ( t ) = h _ { \mathit { l k } } ^ { L O S } ( t ) + h _ { \mathit { l k } } ^ { S } ( t )
$$

$$
h _ { l k } ^ { L O S } \left( t \right) = \sqrt { \frac { C _ { r } } { C _ { r } + 1 } } e ^ { - j \frac { 2 \pi } { \lambda } d _ { l k } ^ { L O S } } e ^ { j 2 \pi f _ { L O S } t }
$$

$$
h _ { l k } ^ { S } \left( t \right) = \sqrt { \frac { 1 } { C _ { r } + 1 } } \sum _ { n = 1 } ^ { N } { \frac { 1 } { \sqrt { N } } } e ^ { j ( \theta - \frac { 2 \pi } { \lambda } d _ { l k n } ^ { S } ) } e ^ { j 2 \pi f _ { S } t }
$$

上式中的 $C _ { r }$ 是莱斯因子， $d _ { l k } ^ { L O S }$ 是直射径的距离， $d _ { l k n } ^ { s }$ 是经$S ^ { n }$ 散射路径的总距离， $f _ { L O S }$ 是直射径的多普勒频移， $f s$ 是散射路径的多普勒频移，相关计算如下：

$$
d _ { \scriptscriptstyle { l k } } ^ { \scriptscriptstyle { L O S } } = D - ( L - 2 l + 1 ) \frac { d _ { \scriptscriptstyle { T } } } { 2 } \cos \theta _ { \scriptscriptstyle { T } } + ( K - 2 k + 1 ) \frac { d _ { \scriptscriptstyle { R } } } { 2 } \cos \theta _ { \scriptscriptstyle { R } }
$$

$$
d _ { l k n } ^ { S } = d _ { \mathrm { { l n } } } + d _ { n k }
$$

$$
d _ { n k } = \frac { l _ { n r } } { \cos \beta _ { R } ^ { n } } - \frac { ( K - 2 k + 1 ) } { 2 } d _ { R } \cos ( \alpha _ { R } ^ { n } - \theta _ { R } ) \cos \beta _ { R } ^ { n }
$$

$$
d _ { \ln } = \sqrt { { l _ { t n } } ^ { 2 } + h ^ { 2 } } - \frac { ( L - 2 l + 1 ) } 2 d _ { T } \cos ( \alpha _ { T } ^ { n } - \theta _ { T } ) \cos \beta _ { T } ^ { n }
$$

$$
\displaystyle l _ { n r } = \frac { b ^ { 2 } } { a + f \cos \alpha _ { R } ^ { n } }
$$

$$
l _ { t n } = 2 a - l _ { n r }
$$

$$
h = l _ { n r } \tan \beta _ { R } ^ { n }
$$

$$
f _ { L O S } = \frac { \nu _ { T } } { \lambda } \cos \alpha _ { T } ^ { \nu } - \frac { \nu _ { R } } { \lambda } \cos \alpha _ { R } ^ { \nu }
$$

$$
f _ { S } = \frac { \nu _ { T } } { \lambda } \cos ( \alpha _ { T } ^ { n } - \alpha _ { T } ^ { \nu } ) \cos \beta _ { T } ^ { n } + \frac { \nu _ { R } } { \lambda } \cos ( \alpha _ { R } ^ { n } - \alpha _ { R } ^ { \nu } ) \cos \beta _ { R } ^ { n }
$$

本模型中发射角AOD与到达角AOA是相关的，即一旦确定到达角的方位角 $\alpha _ { R } ^ { n }$ 和仰角 $\beta _ { R } ^ { n }$ ，就可以得到发射角的方位角$\alpha _ { T } ^ { n }$ （仅与 $\alpha _ { R } ^ { n }$ 相关）和仰角 $\beta _ { T } ^ { n }$ （与 $\alpha _ { R } ^ { n }$ 和 $\beta _ { R } ^ { n }$ 都相关）。

$$
\begin{array} { r } { \alpha _ { T } ^ { n } = \left\{ \begin{array} { c c } { f ( \alpha _ { R } ^ { n } ) } & { 0 < \alpha _ { R } ^ { n } < \alpha _ { 0 } } \\ { f ( \alpha _ { R } ^ { n } ) + \pi } & { \alpha _ { 0 } < \alpha _ { R } ^ { n } < 2 \pi - \alpha _ { 0 } } \\ { f ( \alpha _ { R } ^ { n } ) + 2 \pi } & { 2 \pi - \alpha _ { 0 } < \alpha _ { R } ^ { n } < 2 \pi } \end{array} \right. } \end{array}
$$

根据文献[13]，式（13）中：

$$
f ( \alpha _ { R } ^ { n } ) = \arctan \frac { ( e ^ { 2 } - 1 ) \sin \alpha _ { R } ^ { n } } { 2 e + ( e ^ { 2 } + 1 ) \cos \alpha _ { R } ^ { n } } \ , e = \frac { a } { f } \ , \alpha _ { 0 } = \pi - \arctan \frac { e ^ { 2 } - 1 } { 2 e } \nonumber \infty .
$$

$$
\beta _ { T } ^ { n } = \arctan \frac { h } { l _ { t n } } = \frac { b ^ { 2 } \tan \beta _ { R } ^ { n } } { 2 a ( a + f \cos \alpha _ { R } ^ { n } ) - b ^ { 2 } }
$$

由于现实环境中散射体的分布并不会完全均匀，所以用vonMises分布[3来描述方位角，用余弦分布[来描述仰角。

$$
p ( \alpha ) = \frac { \exp [ k \cos ( \alpha - u ) ] } { 2 \pi I _ { 0 } ( k ) }
$$

$$
p ( { \boldsymbol { \beta } } ) = \left\{ { \begin{array} { l l } { \displaystyle { \frac { \pi } { 2 \beta _ { m } } } \cos ( { \frac { \pi } { 2 } } { \frac { \beta } { \beta _ { m } } } ) } & { \quad \beta \leq \beta _ { m } \leq { \frac { \pi } { 2 } } } \\ { 0 } & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array} } \right.
$$

其中: $\beta _ { m }$ 表示仰角的最大值， $\mathbf { u }$ 表示方位角的均值，k表示方位角集中于均值的程度。当k越大时，越集中于均值；当 $\scriptstyle \mathbf { k } = 0$ 且$\beta _ { m } = 0$ ，则表示各向同性散射。

# 2 参考模型的空间-时间相关函数

信道复增益的空间-时间相关函数（space-time correlationfunction ， ST-CF）能够用公式（204 $r _ { \mathit { l k } , \mathit { i k } } \left( d _ { T } , d _ { R } , \tau \right) = E \left\{ h _ { \mathit { l k } } ^ { * } \left( t \right) h _ { \mathit { i k } } \left( t + \tau \right) \right\}$ 来得到，可分解为LOS 分量 $r _ { l k , l k } ^ { L O S } ( d _ { T } , d _ { R } , \tau )$ 和散射分量 $r _ { l k , l k } ^ { s } ( d _ { r } , d _ { R } , \tau )$ 。 $h _ { l k } \left( t \right)$ 取式(1)，其中（\*）代表复共轭，E{.}表示求均值， $l k$ ， $l ^ { ' } k$ 表示天线 $\mathbf { \xi } _ { l }$ 到天线 $k$ 信道和天线 $l$ 到天线 $k$ 的信道。推导相关函数公式如下，$\rho ( \alpha ) , \ \rho ( \beta )$ 是角度分布概率密度函数。

$$
r _ { _ { l k , l k } } ( d _ { T } , d _ { R } , \tau ) = r _ { _ { l k , l k } } ^ { L O S } ( d _ { T } , d _ { R } , \tau ) + r _ { _ { l k , l k } } ^ { S } ( d _ { T } , d _ { R } , \tau )
$$

$$
r _ { l k , l i \dot { k } } ^ { L O S } ( d _ { T } , d _ { R } , \tau ) = \frac { C _ { r } } { C _ { r } + 1 } e ^ { j \frac { 2 \pi } { \lambda } ( ( l - \dot { l } ) d _ { T } \cos \theta _ { T } - ( k - \dot { k } ) d _ { R } \cos \theta _ { R } ) }
$$

$$
\times e ^ { j \frac { 2 \pi } { \lambda } ( \nu _ { T } \cos \alpha _ { T } ^ { \nu } - \nu _ { R } \cos \alpha _ { R } ^ { \nu } ) \tau }
$$

$$
r _ { l k , l i . k } ^ { S } \left( d _ { T } , d _ { R } , \tau \right) = \frac { 1 } { C _ { r } + 1 } E \left\{ e ^ { j \frac { 2 \pi } { \lambda } ( l - l ) d _ { T } \cos { \left( \alpha _ { T } ^ { n } - \theta _ { T } \right) } \cos { \beta _ { T } ^ { n } } } \right.
$$

$$
\times e ^ { j \frac { 2 \pi } { \lambda } ( k ^ { ' } - k ) d _ { R } \cos ( \alpha _ { R } ^ { n } - \theta _ { R } ) \cos \beta _ { R } ^ { n } }
$$

$$
\left. \times e ^ { j \frac { 2 \pi } { \lambda } ( \nu _ { T } \cos ( \alpha _ { T } ^ { n } - \alpha _ { T } ^ { \nu } ) \cos \beta _ { T } ^ { n } + \nu _ { R } \cos ( \alpha _ { R } ^ { n } - \alpha _ { R } ^ { \nu } ) \cos \beta _ { R } ^ { n } ) \tau } \right\}
$$

$$
 = \frac { 1 } { C _ { r } + 1 } \displaystyle \int \int \int \ d \mathbf { e } ^ { j \frac { \pi } { \lambda } ( l - l ^ { ' } ) d _ { T } \cos ( \alpha _ { T } ^ { n } - \theta _ { T } ) \cos \beta _ { T } ^ { n } }
$$

$$
\times e ^ { j \frac { 2 \pi } { \lambda } ( k ^ { ' } - k ) d _ { R } \cos ( \alpha _ { R } ^ { n } - \theta _ { R } ) \cos \beta _ { R } ^ { n } } e ^ { j \frac { 2 \pi } { \lambda } \nu _ { T } \cos ( \alpha _ { T } ^ { n } - \alpha _ { T } ^ { \nu } ) \cos \beta _ { T } ^ { n } \tau }
$$

$$
\times e ^ { j \frac { 2 \pi } { \lambda } \nu _ { R } \cos ( \alpha _ { R } ^ { n } - \alpha _ { R } ^ { \nu } ) \cos \beta _ { R } ^ { n } \tau } \rho ( \alpha _ { R } ^ { n } ) \rho ( \beta _ { R } ^ { n } ) d \alpha _ { R } ^ { n } d \beta _ { R } ^ { n }
$$

复增益 $h _ { \scriptscriptstyle { l k } } ( t )$ 的时间自相关函数（ACF）采用

$r _ { l k } \left( \tau \right) = E \left\{ h _ { l k } ^ { \ast } \left( t \right) h _ { l k } \left( t + \tau \right) \right\}$ ，等价于设置时间-空间相关函数公式（18,19）的收发端天线单元间的间距 $d _ { T } , d _ { R }$ 为0就可得到ACF。

$$
r _ { \mathit { l k } , \mathit { l } \mathit { k } } ^ { } \left( \tau \right) { = } r _ { \mathit { l k } , \mathit { l } \mathit { k } } ^ { \mathit { L O S } } \left( \tau \right) { + } r _ { \mathit { l k } , \mathit { l } \mathit { k } } ^ { \mathit { S } } \left( \tau \right)
$$

复增益的空间互相关函数(CCF)采用（204号 $r _ { \mathit { l k } , \mathit { l } \mathit { k } } \left( d _ { \mathit { T } } , d _ { \mathit { R } } \right) = E \left\{ h _ { \mathit { l k } } ^ { * } \left( t \right) h _ { \mathit { l } \mathit { k } } \left( t \right) \right\}$ ,等价于设置时间-空间相关函数公式(18,19)时间间隔 $\tau$ 为0就可得到 $\mathrm { C C F }$ 。

$$
r _ { \scriptscriptstyle { l k , i k } } ( d _ { \scriptscriptstyle { T } } , d _ { \scriptscriptstyle { R } } ) = r _ { \scriptscriptstyle { l l k , i k } } ^ { \scriptscriptstyle { L O S } } ( d _ { \scriptscriptstyle { T } } , d _ { \scriptscriptstyle { R } } ) + r _ { \scriptscriptstyle { l l k , i k } } ^ { s } , ( d _ { \scriptscriptstyle { T } } , d _ { \scriptscriptstyle { R } } )
$$

# 3 相关函数数值仿真与分析

根据上节推导的相关函数公式，本节将对非视距(NLOS)和视距(LOS)这两种情况下信道的相关性作仿真分析。采用修正的等面积法(MMEA)来仿真信号的方位角 $\alpha$ 和仰角 $\beta ^ { \ [ 1 4 ] }$ ，即求解下式得到所需的仿真角度。

$$
\frac { n - 1 / 4 } { N } - \intop _ { u - \pi } ^ { \alpha } p _ { \alpha } ( \alpha ) d \alpha = 0 , n = 1 , 2 , . . . , N
$$

所取参数如下：莱斯因子 $C _ { r } = 3$ ，载波频率 $f _ { O = 5 . 9 } \times 1 0 ^ { 9 } \mathrm { { H z } }$ $\mathrm { a } { = } 1 0 0 \mathrm { m } , \mathrm { b } { = } 8 0 \mathrm { m } ; \theta _ { T }$ 和 $\theta _ { R }$ 均取 $4 5 ^ { \circ }$ ，两车的行驶方向均为 $0 ^ { \circ }$ 且$\nu _ { T } = \nu _ { R } = 5 m / s$ - $\scriptstyle \cdot f _ { m a x } = 1 0 0 \mathrm { H z }$ ） $\mathrm { k } { = } 1 0$ ,AAOA均值 $u _ { R } = 4 5 ^ { \circ }$ ，最大仰角 $\beta _ { m } = 2 0 ^ { \circ }$ [15]（除非特殊说明，否则以下仿真均采用这些参数）。

图2是NLOS 情况下的信道时间相关函数 $r _ { \mathit { l k } , \mathit { i } \mathit { k } } ^ { S } ( \tau )$ ，由图2 可以看出：当标准时间间隔很小时，相关性呈现振荡性，若时间间隔越来越大，相关性则逐渐趋于0。

![](images/c0c382d6faf91b1b0fb308911736228e102233b91ce1114857447776a04a66c4.jpg)  
NLOS下时间自相关函数ACF  
图2NLOS情况下时间自相关函数

图3是LOS情况下的信道时间相关函数，所取的参数与LOS情况相同，并设莱斯因子 $\scriptstyle C _ { r = 0 }$ 。函数呈现的振荡性与图2相似，但终值却不是0。文献[6]的图2\~7的LOS情形ACF的终值也停留在0.7左右，这与图3相似。由此说明：存在视距传播路径时，即使标准时间间隔很大，信道依然保持着时间相关性。

![](images/6fefb07f718a0f696287f5db8ca529ede019c0de54b7083ce5718a0fb706f669.jpg)  
图3LOS情况下时间自相关函数

图4和5分布是NLOS和LOS情况下，信道11与22间参考模型的空间相关性函数，参数同上。与时间相关函数ACF类似，在LOS情况下两个信道间的空间相关性并不会随着天线间距的变大而趋于0。说明LOS情形下即使天线间距很大，两个信道间仍存在着一定的相关性，而NLOS情况则不会。

为验证仿真方法的可行性，作出了NLOS情况下CCF仿真函数图、参考与仿真模型的CCF误差图(即图4与图6的差距），如图6、7所示。从图7来看，误差error的最大值仍小于0.06，这个误差精度在可容许的范围之内，故可认为MMEA法适合本模型的仿真，下一节的仿真即使用此方法。

![](images/7da0eaf5d42c3d33161e16b6b09290ad6cc44e59c7116de26d8aab9bd1a14faa.jpg)  
图4NLOS情况下空间互相关函数

![](images/0178fd05e4f88490a0ec34aa390aa14257bddbf49a9e5fa1b7fb2d54f0ef7d56.jpg)  
图5LOS情况下空间互相关函数

![](images/cc51ffa90419b7f6871573f6732a6fd363a7a2002501360366d30689ebcbb88f.jpg)  
图6NLOS情况下仿真模型的空间互相关函数

![](images/1ac7f5c521469d810e0153e46b50d1c2856efcaaf47546a84eef462ef1bcce0a.jpg)  
图7参考模型与仿真模型的空间互相关函数的误差

# 4 信道容量分析

MIMO通信系统的信道容量反应了系统传输数据的能力，单位为bit/s/Hz。通常为使得容量被最大化，将功率平均分配给每一个天线单元。容量计算方法如下，L和K分别是发送端接收端的天线数量， $I _ { \kappa }$ 表示K维的单位矩阵， $\rho$ 表示信噪比（signal-noiseratio，S/N）,H表示信道增益矩阵 $( \mathbf { L } \times \mathbf { K }$ ）（采用式（3），即NLOS情形）。影响信道容量的因素有很多，比如天线单元间距、天线阵列偏角、天线数量、信噪比、莱斯因子等。下面将探讨这些因素对信道容量的影响，以便在实际系统中最大化信道容量。

$$
C = E { \big [ } C ( t ) { \big ] } = E { \Bigg [ } \log _ { 2 } \operatorname* { d e t } ( I _ { K } + { \frac { \rho } { L } } H ( t ) H ^ { T } ( t ) ) { \Bigg ] }
$$

文献[16]做了容量测量实验，选取城市低车流场景（与本文所设场景相似），用 $2 \times 2$ 天线阵列，间距取0.5米，信噪比取 $2 0 \mathrm { d B }$ 。从文献[16]提取测量数据，表1、2分别是大学校园和购物街场景下容量测量值，单位为 $\scriptstyle \mathrm { { b p s / H z } }$ 。

表1校园场景信道容量测量值  

<html><body><table><tr><td>车距</td><td>10m 15m</td></tr><tr><td>NLOS</td><td>8.70 8.67</td></tr><tr><td>LOS</td><td>9.28 9.27</td></tr><tr><td>表2</td><td>购物街场景信道容量测量值</td></tr><tr><td>车距</td><td>10m 15m</td></tr><tr><td>NLOS</td><td>5.81 7.18</td></tr><tr><td>LOS</td><td>8.65 7.85</td></tr></table></body></html>

图8给出了天线单元间距对容量的影响， $2 \times 2$ 天线阵列，信噪比取 $1 7 \mathrm { d B }$ 。观察这4条线可发现：当两端间距 $d _ { T }$ 和 $d _ { R }$ 从0开始变大后，信道容量也随之变大。但间距大于一定值后，容量随间距的增大而不再明显增大，这与文献[3]的图6中2D 椭圆模型情况相同，符合实际情况。

图9给出了天线单元数量对容量的影响，天线间距取 $0 . 2 \mathrm { m }$ 。当信噪比S/N越大，容量越大；当天线数量越多时，信道容量越大。表1的NLOS情形下，车距为 $1 0 \mathrm { m }$ 和 $1 5 \mathrm { m }$ 时信道容量为8.7和8.67。本文在图9相同条件下容量约为10，两者接近，产生差距是因为实际散射环境更加复杂而且本文仿真的两车距离大于文献[16]的车距。

![](images/9c4052baa753abc3406ba3d5fbea4bf81d0d5571f0ef32b369441dc0895c0a3d.jpg)  
图8天线单元间距对容量的影响

![](images/ac1d893717a4e935ebf71dbfb2cbea32daea16eab44dfac957c6c0b31d6fd57d.jpg)  
图9天线单元数量对容量的影响

图10是天线阵列偏角对容量的影响， $2 \times 2$ 天线阵列，信噪比取 $1 7 \ \mathrm { d B }$ ，天线间距 $0 . 2 \mathrm { ~ m ~ }$ 。本文采用线性均匀阵列，其偏角的影响值得研究。观察图中3条线：容量在接收阵列偏角 $\theta _ { R }$ 为$4 5 ^ { \circ }$ 时最小；发射阵列偏角 $\theta _ { T }$ 为 $5 ^ { \circ }$ 的信道容量比另外两个发射阵列小一点。 $\theta _ { R } = 4 5 ^ { \circ }$ 时，得出 $\big | \theta _ { R } - u _ { R } \big | = 0$ （ $u _ { R }$ 是散射体相对接收端的方位角AAOA均值，上一节已取 $4 5 ^ { \circ }$ ）。 $\theta _ { T } = 5 ^ { \circ }$ 时，得出 $\left| \boldsymbol { \theta } _ { T } - \boldsymbol { u } _ { T } \right| \approx 0$ （散射体相对发送端的方位角AAOD均值 $u _ { T }$ 经计算约为 $5 ^ { \circ }$ ）。所以综上分析可知：当 $\left| \theta _ { R } - u _ { R } \right|$ 或 $\left| \theta _ { T } - u _ { T } \right|$ 越小，即阵列的指向越偏向散射体中心，则容量越小。

![](images/17c895c3e3b65391fa2fe283e89e9a43af6f9dbf5fd2ea9edf30bd0b372a0966.jpg)  
图10天线阵列偏角对容量的影响

除了天线会对容量产生影响，通信环境的性质也会对容量产生不可忽略的影响。比如因环境而变化的莱斯因子 $C _ { r }$ 、散射体的高度而决定的最大仰角 $\beta _ { m }$ 。图11、12采用 $1 \times 1$ 天线阵列。

图11给出了莱斯因子 $C _ { r }$ 对容量的影响，信噪比取17dB。$\boldsymbol { C } _ { \boldsymbol { r } } = 0$ （即非视距NLOS情况)时的容量比 $\textstyle C _ { r } = 2$ 或5要小一点。观察表1表2中NLOS和LOS情形的测量数据，两表的数据均表明：LOS情形的容量略大于NLOS情形。本文仿真所作出的分析与文献[16]的实测数据相一致，说明LOS 情况有利于信道容量的最大化。

图12表示最大仰角对容量的影响。仰角的引入是椭圆柱信道区别于2D椭圆信道的最大特征，也更贴近现实环境。图11中给出了 $\beta _ { m } = 1 ^ { \circ }$ 、 $1 0 ^ { \circ }$ 和 $2 0 ^ { \circ }$ 时，容量随波长变化的特征曲线图。观察可知：最大仰角越大，容量也相应地变大，即使增加的量相比改变天线阵列要小得多。 $\beta _ { m } = 1 ^ { \circ }$ 可认为是2D椭圆散射情况，因此说明2D 信道模型低估了信道容量。文献[17]中3D双环模型的情况下，其图6也表明了3D模型的容量比2D 模型大，与此处分析的结论一致。

![](images/d090a05544186d7a48c88f7f2b195606986c3f03bdf41d706b3b52a4d0eaea19.jpg)  
图11莱斯因子对容量的影响

![](images/8111b6a4b54f09428ecfced10dec788142fce764876ea90e735ef78d6e3e9355.jpg)  
图12最大仰角对容量的影响

# 5 结束语

针对车辆稀少的街道环境，本文采用了3D 椭圆柱散射模型来描述V2V信道。根据几何分析法，推导了发射角和到达角的关系。基于MMEA法仿真，仿真模型的ACF、CCF与参考模型的接近一致表明了MMEA法的可用性。根据ACF和CCF图：存在视距（LOS）时，信道将维持一定的时间和空间相关性。V2V信道容量会受到天线间距、天线数量、信噪比、天线阵列偏角等因素的影响，因此优化通信系统时应当考虑这些因素。结合实测数据以及本文分析结果，视距（LOS）时信道表现出更大的容量。最后比较2D与3D模型信道容量，2D椭圆散射模型低估了信道容量，表明本文考虑建立3D 模型的正确性。本文对椭圆柱散射信道的准确刻画以及对ACF、CCF和信道容量的分析，为研究V2V通信信道模型与评估信道的传输特性提供了依据。

# 参考文献：

[1]杨晓丽，孙学宏，白冰．一种V2V 多天线几何去极化信道建模[J].计算机应用研究,2016,33(10):3117-3122.(Yang Xiaoli,Sun Xuehong, BaiBing.A kind of V2V multi-antenna geometric depolarization channelmodeling [J].Application Research of Computers，2016,33 (10):3117-3122. )

[2]Zajic A G, Stuber G L. Space-time correlated mobile-to-mobile channels: modelling and simulation [J].IEEE Trans on Vehicular Technology,2008, 57 (2): 715-726.

[3]周杰，袁梅，唐登洪．Von Mises 分布下椭圆散射信道建模[J].北京邮 电大学学报,2017,40(2):36-42.(Zhou Jie,Yuan Mei,Tang Denghong. Modeling of ellptical scattering channels with Von Mises distribution [J]. Journal of Beijing University of Posts and Telecommunications,2017,40 (2): 36-42.)   
[4]Yuan Yi,Wang Chengxiang,Cheng Xiang,et al.Novel 3D geometry-based stochastic models for non-isotropic MIMO vehicle-to-vehicle channels [J]. IEEE Trans on Wireless Communications,2014,13 (1): 298-309.   
[5] Zajic A G, Stuber G L. Three-dimensional modeling，simulation，and capacity analysis of space-time correlated mobile-to-mobile channels [J]. IEEE Trans on Vehicular Technology,2008,57(4): 2042-2054.   
[6] Du Derong，Zeng Xiaoping，Jian Xin,et al.Three-dimensional vehicle-to-vehicle channel modeling with multiple moving scaterers [J]. Mobile Information Systems,2017,2017: 1-14.   
[7]Bakhshi G, Shahtalebi K,Rad H S.A novel ful-three-dimensional MIMO mobile-to-mobile channel reference model [C]// Proc of International Conference on Signal Processing and Communication Systems.2009:1-6.   
[8] 周杰，姚颖莉，邵根富，等．基于车载通信标准街道场景的电磁散射信 道模型 [J].物理学报,2016,65(14):24-34.(Zhou Jie,Yao Yinli,Shao Genfu,etal. Electromagnetic scattering channel model based on street scenes of vehicle-mounted communication standards [J].Acta Physica Sinica,2016,65 (14): 24-34. )   
[9] Cheng Xiang，Wang Chengxiang，Laurenson D I,et al. An adaptive geometry-basedstochasticmodelfornon-isotropic MIMO mobile-to-mobile channels [J]. IEEE Trans on Wireless Communications, 2009, 8 (9): 4824-4835.   
[10] Cheng Xiang,Yao Qi,Wen Maowen,et al.Wideband channel modeling and intercarrier interferencecancellation for vehicle-to-vehicle communication systems[J]. IEEE Journal on Selected Areasin Communications,2013,31(9):434-448.   
[11] Avazov N,Islam S MR,Park D,et al. Statistical characterization of 3D propagation model for V2V channels in rectangular tunnels [J]. IEEE Antennas & Wireless Propagation Letters,2017,PP (99): 1-1.   
[12] Avazov N,Pätzold M.A novel wideband MIMO car-to-car channel model based on a geometrical semi-circular tunnel scattering model [J].IEEE Trans on Vehicular Technology,2016,65 (3):1070-1082.   
[13]Pätzold M,Hogstad B O.A wideband MIMO channel model derived from the geometric elliptical scattering model[J].Wireless Communications $\&$ Mobile Computing,2008,8(5): 597-605.   
[14] Gutierrez-Diaz-De-Leon C A，Patzold M.Sum-of-sinusoids-based simulation of flat fading wireless propagation channels under non-isotropic scattering conditions [C]// Proc of IEEE Global Telecommunications Conference.2007:3842-3846.   
[15] Zajic AG. Impact of moving scatterers on vehicle-to-vehicle narrow-band channel characteristics [J].IEEE Trans on Vehicle Technology,2O14,63 (7): 3094-3106.   
[16] Adhikari N,Kumar A，Noghanian S. Multiple antenna channel measurements for car-to-car communication [J].IEEE Antennas& Wireless Propagation Letters,2016,15: 674-677.   
[17]梁晓林，赵雄文，李树，等．移动端到移动端3DMIMO 宽带信道建模 与仿真[J].北京邮电大学学报，2017,40 (4):91-97.(Liang Xiaolin, Zhao Xiongwen,Li Shu,etal.Mobile-to-mobile 3D MIMO wideband channel modeling and simulation [J].Journal of Beijing University of Posts and Telecommunications,2017,40(4): 91-97.)