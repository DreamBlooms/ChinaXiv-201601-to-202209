# 类星体长周期光变分析方法的研究\*

余莲,张雄t,张皓晶，李富婷,徐小林,任国伟，吴月承(云南师范大学物理与电子信息学院，云南昆明650500)

摘要：本文给出了四种分析类星体长周期光变的方法，用一个模拟的周期信号 $_ { y = s i n \theta }$ 检验这四种分析方法，结果表明： $\textcircled{1}$ 、天体光变采样的数据点个数相对少到一定值时，Jurkevich方法，时间补偿离散傅里叶变换分析方法（DCDFT），离散相关分析方法（DCF）和功率谱密度分析方法（PSD）的分析结果不一样，获取最短的连续数据点后，Jurkevich方法分析结果在四种方法中可能最为精确可靠，且计算方法简捷实用。 $\textcircled{2}$ 、获得了Jurkevich分析方法的最佳参数，当 $\scriptstyle m = 9$ 时分析结果最佳。 $\textcircled{3}$ 、用 $\scriptstyle m = 9$ 时的Jurkevich方法分析了类星体3C279天体及3C454.3天体的光变周期，得出3C 279天体的可能光变周期为 $( 2 . 8 1 \pm 0 . 5 4 ) y r$ ，3C454.3天体的可能光变周期为 $4 5 7 d$ 。

关键词：类星体；Jurkevich方法；DCDFT方法；DCF方法；PSD方法；长周期光变中图分类号：文献标识码：文章编号：

长周期光变是研究耀变体性质的重要方法之一，它的确定关系到耀变体的结构和辐射等相关的多个物理量的估算，比如辐射区域的半径、喷流的多普勒因子和黑洞质量等，长周期光变为理论模型的建立提供一定的参数。光变可以被分为长时标光变、中等时标光变、短时标光变[1]。对于长时标光变和中等时标光变来说，由于受到观测仪器、月相和天气等各种原因的影响，很难得到比较完整的光变的观测数据序列[2]。在研究光学剧变类星体光变周期性时，通过研究长周期光变分析方法，可以获取周期光变分析的最佳参数，用有限的实际观测数据序列获得最佳周期估算值。

通常分析周期的方法有：功率谱法、Jurkevich方法、小波、结构函数等，这些方法的特点是可以对高于奈奎斯特采样定律均匀采样的数据进行可靠分析[3-5]。但是实际的数据分析，特别是针对天体观测所获得耀变体的长时标光变周期分析中，这些方法的使用就受到许多条件的限制，比如说Fourier分析回要求连续的等间隔采样，缺失数据点的处理就引进了一些不真实的信息。所以这些方法应用在天体的光变周期分析中，增大了确定周期的误差。而由Jurkevich等人提出的Jurkevich方法，是一种建立在期待值均方误差基础上的统计方法，对于处理不等间隔观测数据有很大帮助[7]。本文将利用四种方法对这一问题进行讨论，并提出相应的改进，使得在不等间隔时间序列的类星体光变曲线中，寻找周期性的分析计算变得更为简便准确。

# 1 类星体长周期光变的计算方法

# 1.1 Jurkevich方法

Jurkevich 基于对天文测量中的非均匀测量问题提出的一种统计法[7]，曾经文献[8]用该方法分析蝎虎天体 $\mathrm { P K S } ~ 0 7 3 5 \substack { + 1 7 8 }$ 的光变特性。假设我们的观测样本数据为N个，Xi为单次测量值， $\overline { { \boldsymbol X } }$ 为所有测量值的平均值， $\boldsymbol { V } ^ { 2 }$ 为测量数据样本方差，S为样本标准偏差，则有：

$$
\overline { { { X } } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } x _ { i } \qquad , \quad ( 1 ) \qquad V ^ { 2 } = \sum _ { i = 1 } ^ { N } X _ { i } ^ { 2 } - N \overline { { { X ^ { 2 } } } } , ( 2 ) \quad S = \sqrt { { { V } ^ { 2 } } / \big ( N - 1 \big ) } .
$$

若样本划分为 $m$ 组，则第组的统计参数应为：

$$
\overline { { { X } } } _ { l } = \frac { 1 } { m _ { _ { I } } } \sum _ { i = 1 } ^ { m _ { _ { I } } } X _ { i } \ , \quad ( 4 ) \quad { V } _ { l } ^ { 2 } = \sum _ { i = 1 } ^ { m _ { I } } X _ { i } ^ { 2 } - m _ { _ { I } } \overline { { { X } _ { l } ^ { 2 } } } \ , \quad ( 5 ) \quad S _ { l } ^ { 2 } = { V } _ { l } ^ { 2 } \big / \big ( m _ { l } - 1 \big ) .
$$

对应 $m$ 组的总方差为：

$$
V _ { _ { m } } ^ { 2 } = \sum _ { i = 1 } ^ { m } V _ { l } ^ { 2 } .
$$

显然， $\boldsymbol { V } _ { m } ^ { 2 } < \boldsymbol { V } ^ { 2 }$ 。上述公式实际上表明，当自变量相同的 $n$ 个样本计算后则变为一个样本。如果分组的平均值相等，那么最后的期待值方差将等于分组的平均方差。如果分组的平均值不同，那么最后的期待值方差将超过分组的平均方差7]。

在周期分析中我们按照不同的试验周期 $| P |$ 把数据折叠，然后把折叠好的资料按其相位从小到大排列，然后分成 $\textmu m$ 组。若给定一个观测时间为t，试验周期为 $P$ ，则其对应的相位定义为[7]：.

$$
\phi \big ( t \big ) = \mathrm { m o d } ( \frac { t - t _ { 0 } } { P } , 1 )
$$

其中 $\phi ( t )$ 满足 $0 \leq \phi ( t ) \leq 1$ ， $t _ { 0 }$ 表示的是时间原点。计算出每组数据的方差 $V _ { l } ^ { 2 }$ 和总方差$V _ { m } ^ { 2 }$ ，如果所得的实验周期等于实际周期，则 $V _ { m } ^ { 2 }$ 的值将会达到最小，由试验周期 $P _ { n }$ 与 $V _ { m } ^ { 2 }$ 的关系曲线中的 $V _ { m } ^ { 2 }$ 最小值对应的时间即可得到样本的周期。

1.2时间补偿离散傅里叶变换分析方法

时间补偿离散傅里叶变换方法是计算光变周期最常用的方法之一，此方法最早是由Ferraz-mello 在1981年提出的[9]。在过去的研究中文献[10]用该方法分析PKS1510-089 红外光变周期。通过对1、sin $\omega t$ 、cOS@t作Gram-Schmidt 正交化，得到3个正交向量，将数据投影到3个正交向量上就得到了频谱。具体过程如下：

$$
H _ { 0 } = 1 , H _ { 1 } = \cos \omega t H _ { 2 } = \sin \omega t
$$

正交化后： (10)

$$
h _ { 0 } = a _ { 0 } H _ { 0 }
$$

$$
h _ { 1 } = a _ { 1 } H _ { 1 } - a _ { 1 } a _ { 0 } ( h _ { 0 } , H _ { 1 } )
$$

$$
h _ { 2 } = a _ { 2 } H _ { 2 } - a _ { 2 } a _ { 0 } ( h _ { 0 } , H _ { 2 } ) - a _ { 2 } a _ { 1 } ( h _ { 1 } , H _ { 2 } )
$$

小括号表示求两个向量的内积。然后根据以下关系确定 $h _ { 0 } , \ h _ { 1 } , \ h _ { 2 }$

$$
( h _ { 0 } , h _ { 0 } ) = ( h _ { 1 } , h _ { 1 } ) = ( h _ { 2 } , h _ { 2 } ) = 1
$$

在不均匀采样的情况下，加权的时间补偿离散傅立叶变换(DCDFT):

$$
F ( \omega ) = ( f , h _ { 1 } + i h _ { 2 } ) 4 \mu _ { 0 } \sqrt { 2 }
$$

在许多类星体的观测中，观测数据 $f ( t _ { i } )$ 的精度各不相同，考虑到这个问题，引进权重方程 $\omega _ { i } = \omega _ { ( t _ { i } ) }$ 重新定义内积：

$$
\begin{array} { r } { ( g _ { 1 } , g _ { 2 } ) = \sum \omega _ { i } g _ { 1 } ( t _ { i } ) g _ { 2 } ( t _ { i } ) } \end{array}
$$

在内积中引入权重后得到：

$$
{ \tilde { a } } { \bar { \vec { 6 } } } \rangle \mathrm { = } \sum { \tilde { \omega } } _ { i }
$$

$$
\begin{array} { r } { a _ { 1 } ^ { - 2 } = \sum \omega _ { i } ( \cos x _ { i } ) ^ { 2 } - a _ { 0 } ^ { 2 } ( \sum \omega _ { i } \cos x _ { i } ) ^ { 2 } } \end{array}
$$

$$
\begin{array} { r l } & { a _ { 2 } ^ { - 2 } = \sum { \omega _ { i } } ( \sin x _ { i } ) ^ { 2 } - a _ { 0 } ^ { 2 } ( \sum \omega _ { i } \sin x _ { i } ) ^ { 2 } - a _ { 1 } ^ { 2 } [ \sum \omega _ { i } \sin x _ { i } \cos x _ { i } } \\ & { - a _ { 0 } ^ { 2 } ( \sum \omega _ { i } \sin x _ { i } ) ( \sum \omega _ { i } \cos x _ { i } ) ] ^ { 2 } } \end{array}
$$

在内积中引入权重后得到回归系数：

$$
\begin{array} { c } { c _ { 0 } = 0 _ { \begin{array} { c } { ( 1 9 ) } \\ { c _ { 1 } = a _ { 1 } \sum \omega _ { i } f ( t _ { i } ) \cos x _ { i } } \end{array} } } \\ { c _ { 2 } = a _ { 2 } \sum \omega _ { i } f ( t _ { i } ) \sin x _ { i } - a _ { 1 } a _ { 2 } a _ { 0 } [ \sum \omega _ { i } \sin x _ { i } \cos x _ { i } - a _ { 0 } ^ { 2 } ( \sum \omega _ { i } \sin x _ { i } ) ( \sum \omega _ { i } \cos x _ { i } ) ] } \end{array}
$$

频率 $\omega$ 处的强度由下式给出：

$$
I ( \omega ) = c _ { 1 } ^ { 2 } + c _ { 2 } ^ { 2 }
$$

由线性回归理论可知 $0 \leq I ( \omega ) \leq Q$ ，式中：

$$
\begin{array} { r } { Q = ( f , f ) = \sum \omega _ { i } f ( t _ { i } ) ^ { 2 } } \end{array}
$$

利用这一性质，引进标准化因子：统计量 $S ( \omega ) = I ( \omega ) / Q$ ，我们称这一量为谱相关系数，对于所有频率 $\omega$ ， $0 \leq S ( \omega ) \leq 1$ 。

# 1.3离散相关分析方法

离散相关分析方法（DCF）由Edelson 和Krolik（1988年）用来分析两组离散数据相关性的方法之一，文献[11]用此方法分析 PKS 2155-304 的光变。该方法可以指出两个变量时间序列的相关性和时间延迟，并可应用于周期性分析[I]。该方法的具体的步骤如下：

首先计算两组数据的离散相关函数值，如数组 $a _ { i }$ 和 $b _ { i }$ ，则离散相关函数值为：

$$
U D C F _ { i j } = \frac { \big ( a _ { i } - \overline { { a } } \big ) \big ( b _ { j } - \overline { { b } } \big ) } { \sqrt { \sigma _ { a } ^ { 2 } \times \sigma _ { b } ^ { 2 } } }
$$

$\overline { { a } }$ 和 $\overline { { b } }$ 分别为两组数据的平均值； $\sigma _ { a }$ 和 $\sigma _ { b }$ 分别为对应的标准偏差。

其次计算 $\mathrm { { D C F } ( \boldsymbol { \mathbf { \rho } } _ { \tau } ) }$ 值。通过时间延迟 $\Delta t _ { i j } = t _ { i } - t _ { j }$ 把两组数联系起来，假如时间延迟为t，在区间 $\tau \pm \Delta \tau / 2$ 中有 $\mathrm { ~ M ~ }$ 个 $\Delta t _ { i j }$ ，则 $\mathrm { \Delta D C F ( \tau ) }$ 值为

$$
\mathit { D C F } ( \tau ) = \frac { 1 } { M } \sum U D C F _ { i j } ( \tau )
$$

再次离散相关函数的误差为

$$
\sigma ( \tau ) = \frac { 1 } { M - 1 } \Bigl \{ \sum \bigl [ U D C F _ { i j } - D C F ( \tau ) \bigr ] ^ { 2 } \Bigr \} ^ { 0 . 5 }
$$

对于所得到的离散相关图，如果峰值在零的右面，表明数组 $a _ { i }$ 早于数组 $b _ { i }$ 的变化。反之，数组 $a _ { i }$ 就会迟于数组 $b _ { i }$ 。

1.4功率谱密度分析方法

功率谱密度的定义[12]是如果 $u ( t )$ 是一个可以进行傅里叶变换的函数，则

$$
\begin{array} { r } { u ( \nu ) = \sum u ( t ) e ^ { - 2 i c _ { \nu } t } } \end{array}
$$

因为 $u ( t )$ 是实函数， $u ( \nu )$ 一般来说是一个复函数，它们之间满足Parseval公式

$$
{ \Sigma } u ^ { t } ( t ) { = } \Sigma { \left| u ( \nu ) \right| } ^ { 2 }
$$

若 $u ( t )$ 表示光谱，则等式左端表示 $u ( t )$ 在 $( - \infty , \infty )$ 上的总能量，上式右端积分中的被积函数被称之为能谱密度，它是一个非负实数，表示了单位频率所具有的能量。在实际情况下从数学意义上讲大多数 $u ( t )$ 是不能进行傅里叶变换的，如果使用截尾函数 $u r ( t )$ 来截取$u ( t )$ ，

$$
u r ( t ) = \left\{ { u ( t ) , \left| t \right| \leq T } \right.
$$

那么对于持续时间有限的截尾函数 $u r ( t )$ 而言是可以进行傅里叶变换的，变换式：

$$
\begin{array} { r } { u _ { T } \left( \nu \right) = \sum u _ { T } { \left( t \right) } e ^ { 2 i c _ { \nu } t } = \sum u { \left( t \right) } e ^ { 2 i c _ { \nu } t } } \end{array}
$$

同样它也满足Parseval公式：

$$
\scriptstyle \sum u _ { T } ^ { 2 } ( t ) = \sum \left| u _ { T } \left( \nu \right) \right| ^ { 2 }
$$

联系截尾函数，将上式两端除以 $2 T$ 并令 $T \to \infty$ ，得到

$$
\frac { 1 } { 2 T } \Sigma u ^ { 2 } \big ( t \big ) = \Sigma \frac { 1 } { 2 T } \big | u r \big ( \nu \big ) \big | ^ { 2 }
$$

与能谱密度的定义相对应，上式右端被积函数称为功率谱密度，记为：

$$
P \big ( \nu \big ) = \operatorname* { l i m } _ { T  \infty } \frac { \big | u _ { T } \big ( \nu \big ) \big | ^ { 2 } } { 2 T }
$$

从表达式中可见功率谱密度是一个非负实数，从整个功率谱密度的推导可以看出，功率谱密度是一个频域中的量，它直接反应了在频域中不同频率所对应的值。

# 2 天文观测数据中周期信号的模拟检验

2.1天文观测周期信号的模拟检验结果

为检验上述四种研究方法的可靠性，我们用一个模拟的周期信号作为天文观测数据来分析上述四种方法。在这里我们以 $2 \pi$ 为周期的正弦函数 $y = \sin \theta$ ，来检验分析四种研究方法的准确性，所使用的单位为弧度。在实验中，我们选择0rad为起点，步长为0.lrad，不同的数据点个数共取了15组，所有研究方法考虑噪声等因素的影响。

![](images/9c7d4456e60558440f320914f4c777229f54dde8acf949d332b9b34123b32f3f.jpg)  
图1Jurkevich方法对sin函数不同数据点的周期性分析  
Fig.1Periodic analysis of sin functions'different data points by using Jurkevich method

图1为检验Jurkevich方法分析天体周期的可靠性，在这里我们取80-360个数据点，每组增加20个数据点，通过Jurkevich方法分析得到不同15组数据点的 $V _ { m } ^ { 2 } - P$ 曲线，从而得到的分析结果为 $( 6 . 3 0 \pm 0 . 0 2 ) r a d$ 。

![](images/801bbb28e5f3356a362dfabe2bc0cb215cd9453154d3a5536f06c80c7a1aaccd.jpg)  
图2时间补偿离散傅里叶变换分析方法（DCDFT）对sin函数不同数据点的周期性分析

图2为检验时间补偿离散傅里叶变换分析方法（DCDFT）分析天体周期的可靠性，在这里我们取80-360个数据点，每组增加20个数据点，用时间补偿离散傅里叶变换分析方法（DCDFT）分析得到不同15组数据点的DCDFT-Frequency曲线，从而得到的分析结果为$( 6 . 3 3 \pm 0 . 1 3 ) r a d$ ;

![](images/1fc607ae74595e5a49829123ee524935d3700ea364dd8babf2557377a4d50eee.jpg)  
Fig.2Periodic analysis of sin functions'different data points by using DCDFT method   
图3离散相关分析方法（DCF）对sin函数不同数据点的周期性分析  
Fig.3Periodic analysis of sin functions'different data points by using DCF method

图3为检验离散相关分析方法（DCF）分析天体周期的可靠性，在这里我们取80-360个数据点，每组增加20个数据点，用离散相关分析方法（DCF）分析得到不同15组数据点的DCF-Delay曲线，从而得到的分析结果为 $( 6 . 2 8 7 \pm 0 . 0 8 8 ) r a d$

![](images/d882a4dae932db5b2dd76061a4fb9d7a1676147271e2bbd52a3bac2a799d3107.jpg)  
图4功率谱密度分析方法（PSD）对sin函数不同数据点的周期性分析Fig.4Periodic analysis of sin functions’different data points by using PSD method

图4为检验功率谱密度分析方法（PSD）分析天体周期的可靠性，在这里我们取80-360个数据点，每组增加20个数据点，用功率谱密度分析方法（PSD）分析得到不同15组数据点的Power-Frequency曲线，从而得到的分析结果为 $( 6 . 2 8 7 \pm 0 . 0 4 5 ) r a d$ 。

![](images/78a3f9f387008993901783ff734d85b0491a5911723fc0bb1b86b3a659bb7325.jpg)  
图5sin函数用时间补偿离散傅里叶变换分析（DCDFT）方法、离散相关分析（DCF)方法、Jurkevich分析方法和功率谱密度分析（PSD）方法进行周期分析时要求的最低数据点

Fig.5Theminimumdatapointsrequredforthesinfunction toperformperiodicanalysisusing theDCDFTmethod,DCFmethod,

Jurkevichmethod and PSD method

由图5分析得到Jurkevich方法、DCDFT方法、DCF方法和PSD方法周期需要的数据点最低分别为50个、120个、100个和60个。获取最短的连续数据采样后，Jurkevich方法最为有效。

# 2.2利用天文模拟数据寻找Jurkevich方法的最佳参数

在利用Jurkevich方法分析周期时，分别取360个、720个和1500个数据点时，同时取分组数1-12组，取试验周期 $P = 2 \pi$ ，令步长为0.lrad，用计算可以得到不同 $X { \big ( } X = P { \big ) }$ 所对应的 $Y ( Y = V _ { m } ^ { 2 } )$ 值。

![](images/727698c80e60988f6fafe0ca60ab86d342033f964991b8525d68814667b20f08.jpg)  
图 $6 \sin$ 函数的 $ { \boldsymbol { V } } _ { m } ^ { 2 } -  { \boldsymbol { P } }$ ,左图分组数为1\~6组,右图分组数为7\~12组

Fig.6The $ { \boldsymbol { V } } _ { m } ^ { 2 } -  { \boldsymbol { P } }$ curve of sin,The number of groupings onthe left are1 to6 groups,and the grouping on the right are 7to l2 groups

如图6所示，当取360个数据点时，分组数从1组逐渐分到6组的情况下，要求不等间隔的数据样本周期数不少于6个[7]，因此周期性可忽略；当周期从7组至12组的时候，在第10组、第11组和第12组可能是出现了倍周期，即可能刚好是第一个周期的重复出现。即使出现极小微差的伪周期，显然周期性最好的为第9组。

![](images/33f71b8d522741e633310ef479ced50f77c6893bc8e3871666805057b5a5765e.jpg)  
图7sin函数的 $V _ { m } ^ { 2 } - P$ ，左图分组数为1\~6组,右图分组数为7\~12组

Fig.7The $ { V _ { m } } ^ { 2 } - P$ curve of sin,The number of groupingson the left are l to6groups,andthe grouping on the right are7to 12 groups

当取720的数据点时，如图7所示，分组数从第1组逐渐分到第6组的情况下，同样没有周期性；当周期从7组至12组的时候，在第10组和第12组出现了倍周期，即可能刚好是第一个周期的重复出现；周期在第11组出现了明显的伪周期，因此第9组周期性的分析结果最佳。

![](images/dcd57e1cec555db02ec70d5df24f65b469b4542891d9baa96baa9f58c0fc1c3c.jpg)  
图8sin 函数的 $ { \boldsymbol { V } } _ { m } ^ { 2 } -  { \boldsymbol { P } }$ ,左图分组数为1\~6组,右图分组数为7\~12组  
图93C279在B波段的光变周期 Fig.9The light curve of quasar 3C 279 in Bband

Fig.8The $ { V _ { m } } ^ { 2 } - P$ curve of sin,The number of groupings on the leftarel to 6 groups,and the grouping on the right are7to l2 gro

如图8所示、当取1500个数据点时，分组数从第1组逐渐分到第6组的情况下，周期性不明显，所以这几组的周期可忽略研究。当周期从第7组至第12组时，在第8组、第10组和第12组出现了倍周期，第11组的周期性显然也没有第9组明显。总的来说，周期性的分析结果最佳的应该为第9组。以下将用两个多观测数据的源来验证此结果。

# 3 计算并分析3C279和3C454.3的光变周期

# 3.13C279的数据点及光变周期

本文研究的3C 279 B波段和3C 454.3B波段数据点主要是从(http：//www.astro.yale.edu/smarts/glast/home.php)网站获取。

从2008年到近期，由以上网站可搜寻到类星体3C279B波段的数据点就有661个，B波段的光变曲线如图9所示，可以看出有几次大的爆发，最亮时 $\begin{array} { r } { m _ { B } { = } 1 4 . 9 m a g } \end{array}$ ，光变曲线中有6个以上周期存在，这些均满足Jurkevich方法中确认长周期存在的必要条件[13]。

15 A！   
16   
B 杭   
17   
l   
18   
19   
54500 55000 55500 56000 56500 57000 57500 JD2400000+

![](images/992553626dfd927a907a07901f708329b03d71aa779b1846549e4aa92a398d32.jpg)  
图10Jurkevich方法分析3C279B波段的光变周期  
Fig.10Jurkevich methed analysis of the variability period of quasar 3C 279 in B band

利用Jurkevich方法分组数 $\scriptstyle { m = 9 }$ ，图10可得到3C279B波段的光变周期 $( 2 . 8 1 \pm 0 . 5 4 ) y r$ 。周期 $P _ { n }$ 与 $V _ { m } ^ { 2 }$ 的关系曲线中有很多的极小值，为了有效地判断周期 $P _ { n }$ 与 $V _ { m } ^ { 2 }$ 的关系曲线中所得出周期的真实性，参考文献[14]给出了较好的判据：

$$
f = \frac { \left( 1 - V _ { m } ^ { 2 } \right) } { V _ { m } ^ { 2 } }
$$

式中 $V _ { m } ^ { 2 }$ 是进行归一化的值，在归一化的 $\boldsymbol { V } _ { m } ^ { 2 } - \boldsymbol { P } _ { n }$ 图中，若 $V _ { _ { m } } ^ { 2 } = 1 . 0$ ，则有 $\scriptstyle \mathrm { f = } 0$ ，即在样本数据中没有表现出有周期性的存在。若 $V _ { _ m } ^ { 2 } = 0 ;$ ，则有 $f { = } 1$ ，这时样本中存在的最大周期能够从图中识别出来。在通常情况下，当 $f \geq 0 . 5$ 时，则样本数据表现出含有非常强的周期性，当 $f \leq 0 . 2 5$ 时，则表现为不含有周期性。进一步分析 $\boldsymbol { V } _ { m } ^ { 2 }$ 图，选择曲线较“平滑"部分中的最小深度和噪声做实验，如果"平滑"部分的相对最小爆发值比"平滑"部分的$\boldsymbol { V } _ { m } ^ { 2 }$ 大出10倍，则可以进一步讨论相应的断周期性。在计算中分组数 $\mathbf { \dot { \phi } } _ { m }$ 的数目十分重要，组数 $\mathbf { \bar { \rho } } _ { m }$ 分得越多，灵敏度越高，但每组数据中有少数的数据点会在图中产生较大的噪声。分组数 $m$ 选取较多时，还将增加 $\boldsymbol { V } _ { m } ^ { 2 }$ 的计算量。反之，有可能寻找不了周期。对3C 279天体的 $V _ { m } ^ { 2 } - P$ 图的分析，我们很容易寻找到 $V _ { m } ^ { 2 }$ 及 $P$ 值，并用参考文献[14]的判据： $f = \big ( 1 - V _ { m } ^ { 2 } \big ) \big / V _ { m } ^ { 2 }$ 进行检验，结果如表1所示。

表13C279天体周期分析表  
Tab.1 The table of 3C 279 objects cycle analysis   

<html><body><table><tr><td>P</td><td>V</td><td>f=(1-v2)/v2</td><td>T/年</td></tr><tr><td>413</td><td>0.7006</td><td>0.4273</td><td>1.13</td></tr><tr><td>829</td><td>0.529</td><td>0.8604</td><td>2.27</td></tr><tr><td>1222</td><td>0.3521</td><td>1.8401</td><td>3.35</td></tr></table></body></html>

通过对上述表1进行分析，我们发现3C279天体最小值 $V _ { m } ^ { 2 } = 0 . 3 5 2 1$ ， $f { = } 1 . 8 4 0 1$ ，可能的光变周期为 $( 2 . 8 1 \pm 0 . 5 4 ) y r$ 。利用Jurkevich方法分组数 $\scriptstyle { m = 9 }$ ，我们分析了3C279的B波段的光变数据，图10显示了B波段的分析结果。从表一中可以看出，在满足判据 $f$ 的条件下[14],3C279在B波段的 $P _ { 2 , } P _ { 3 , }$ 与 $\mathrm { ~ P ~ } _ { 1 }$ 之间存在着简单的倍数关系： $P _ { 2 } { \approx } 2 \ P _ { 1 } , P _ { 3 } { \approx } 3 \ P _ { 1 , }$ 这说明它们

之间可能存在着天文学倍频关系。

3.23C454.3的数据点及光变周期

3C454.3(1 $\operatorname { P K S } 2 2 5 1 + 1 5 8$ ，OY091）是一个比较亮的、变化比较剧烈的类星体，并且在光学和射电波段存在着比较明显的相关性[15]。本文的数据是从2008年到近期，约765个数据点，获得了如图11所示的历史光变曲线。

![](images/4ee74eecdbe5a7c9ce731d912a4b6851552a63117e2b37ebbd886f1b7c26213a.jpg)  
图113C454.3在B波段的光变周期

![](images/ecf71a658cc85948ff77ed77b33eb6567da96c8e4d16adfb7c430ae7baa11bf1.jpg)  
Fig.11The light curve of quasar 3C 454.3 in B band   
图12Jurkevich方法分析3C454.3B波段的光变周期  
Fig.12Jurkevich methed analysis of the variability period of quasar 3C 454.3 in B band

利用Jurkevich方法分组数 $\scriptstyle { m = 9 }$ ，我们分析了3C454.3的B波段的光变数据，图12显示了B波段的分析结果。从图12中可以看出，3C454.3在B波段的有三个明显的极小值，这意味在3C454.3的B波段光变曲线中可能存在三个可能的周期，它们分别是： $P _ { \mathrm { \ell } _ { 1 } } = 4 5 7 d$ ，$P _ { 2 } { = } 8 9 1 d$ 和 $P _ { 3 } = 1 3 2 0 d$ 。然而，根据Kidger等人的结果，要确定一个周期，数据样本的时间跨度要超过周期的六倍[16]。而我们的数据样本的时间跨度大约 $2 5 0 0 d$ ，这小于 $P _ { 2 }$ ， $P _ { 3 }$ 的六倍，故 $P _ { 2 }$ ， $P _ { 3 }$ 必须排除，并需要更多的观测数据来确定它们。但非常有趣的是 $P _ { 2 }$ ， $P$ 3与 $P _ { 1 }$ 之间存在着简单的倍数关系： ${ \cal P } _ { 2 } { \approx } 2 { \cal P } _ { 1 }$ ， ${ P } _ { 3 } { \approx } 3 { P } _ { 1 }$ ，这说明它们之间可能存在着天文学倍频关系。这意味着3C454.3在B波段的光变曲线中可能存在一个 $P _ { \mathrm { \ell } _ { 1 } } = 4 5 7 d$ 的真正的光变周期。

同样，对3C454.3天体的 $ { V _ { m } } ^ { 2 } - P$ 图的分析，我们很容易寻找到 $V _ { m } ^ { 2 }$ 及 $P$ 值，并用参考文献[14]的判据： $f = \left( 1 - V _ { m } ^ { 2 } \right) \big / V _ { m } ^ { 2 }$ 进行检验，结果如表2所示。

表23C454.3天体周期分析表  
Tab.2The table of 3C 454.3 objects cycle analysis   

<html><body><table><tr><td>P</td><td>V</td><td>f=(1-v2)/²</td><td>T/年</td></tr><tr><td>457</td><td>0.5505</td><td>0.817</td><td>1.25</td></tr><tr><td>891</td><td>0.58</td><td>0.724</td><td>2.44</td></tr><tr><td>1320</td><td>0.4133</td><td>1.420</td><td>3.67</td></tr></table></body></html>

通过对上述表2进行分析，我们发现3C454.3天体当 $V _ { m } ^ { 2 }$ 最小值为0.5505， $_ { f = 0 . 8 1 7 }$ ，对应的光变周期可能为 $P { = } 4 5 7 d$ ，这既满足了图12的分析结果，也满足f判据[14]。

# 4 讨论与结论

本文利用一个以 $2 \pi$ 为周期的正弦函数 $y = \sin \theta$ 来检验四种研究方法的可靠性。在实验中，所使用的单位为弧度，选择0rad为起点，步长为 $0 . 1 r a d$ ，不同的数据点个数共取了15组。得到Jurkevich方法的分析结果为 $( 6 . 3 \pm 0 . 0 1 7 ) r a d$ ；得到时间补偿离散傅里叶变换分析（DCDFT）方法的分析结果为 $( 6 . 3 3 1 \pm 0 . 1 3 0 ) r a d$ ；得到离散相关分析（DCF）方法的分析结果为 $( 6 . 2 8 7 \pm 0 . 0 8 8 ) r a d$ ；得到功率谱密度（PSD）方法的分析结果为$( 6 . 2 8 7 \pm 0 . 0 4 5 ) r a d$ 。分析结果表明Jurkevich 方法、DCDFT方法、DCF 方法和 PSD 方法周期需要的数据点最低分别为50个、120个、100个和60个。获取最短的连续数据采样后，Jurkevich方法最为有效。Jurkevich方法分析结果在本次研究的四种方法中最为精确可靠，且此计算方法简捷实用。

在实际应用中发现Jurkevich方法十分依赖于分组数 $\mathbf { \nabla } _ { m }$ ， $\mathbf { \nabla } _ { m }$ 值越大分析结果就越好，但会产生比较大的噪声；反之则有可能找不到周期[17]。如果数据分布不均匀，则会导致组间数据分布偏差很大，从而影响获得实际的周期。根据图6、图7和图8可以看出，对于不同的 $\mathbf { \nabla } _ { m }$ 值， $\boldsymbol { V } _ { m } ^ { 2 }$ 与 $P _ { n }$ 的关系曲线的倾斜程度不同，周期大的向下倾斜。结合 $f$ 检验公式可知，$\boldsymbol { V } _ { m } ^ { 2 }$ 越小 $f$ 值就越大，就更容易满足 $f$ 检验。由此可知 $f$ 检验依赖于 $\mathbf { \nabla } _ { m }$ 值的大小。进而利用模拟数据寻找到Jurkevich方法的分组数为 $\scriptstyle { m = 9 }$ 组时分析结果为最佳。最后用分组数为$\scriptstyle { m = 9 }$ 组时的Jurkevich方法分析了3C279天体及3C454.3天体的光变周期，我们得出3C 279天体可能的光变周期为 $\big ( 2 . 8 1 \pm 0 . 5 4 \big ) y r$ ，在文献[18]中分析了3C279光变可能周期为$1 3 0 . 6 \pm 1 . 3 d$ ，我们分析得到的可能周期大约是 $1 3 0 . 6 \pm 1 . 3 d$ 的8倍。3C 454.3天体可能的光变周期为 $4 5 7 d$ 。在文献[19]中分析了3C454.3光变可能周期 $1 2 . 3 9 y r$ ，大约是我们得到的周期的10倍。

致谢：感谢编辑和审稿人对我们稿件“类星体长周期光变分析方法的研究”提供的意见。这些意见对我们进行论文修改和提高论文质量非常有帮助。我们根据审稿人的意见对论文做了仔细修改。

# 参考文献：

[1] 谢照华.耀变体的吸积盘与喷流关联及粘滞系数的研究[D].云南大学,2012. XieZhaohua.Studyof jet-disk symbiosisandaccretion diskviscosity parameterofBlazars[DJ.Yunnan University,2012

[2]王文广.耀变体的光变特性及色指数分析[D].云南师范大学,2017. WangWenguang .AnalysisofOptical Variabilityand Color IndexofBlazar[D].JournalofYunnanNormal University,2017.   
[3]FanJH,dG,XieGZ,etal.Celationetweetegmma-rayndthdiomissins[J].Atronmy&stros,98, 338(1):27-30.   
[4] Fan JH,KurtaidzeO,LiuY,etal.OpticalMonitoringofTwoBrightestNearbyQuasars,PH1811and3C73[J].Astrohsical Journal Supplement,2014,213 (2):26.   
[5]R RiegerFM,ManneimK.Implicationsofaposible23dayperiodicityforbinary black hole models inMkn\~501[J].Astronomy & Astrophysics,2012,359(3):948-952.   
[6] Webb JR,SmithAG,LeacockRJ,etal.Opticalbservationsof22violentlyvariableextragalactic sources-968-1986[J]. Astronomical Journal,1988,95(2):374-97.   
[7]Jurkevich J.N.A METHOD OF COMPUTNG PER IODS OF CYCL IC PHENOMENA[J].Applied Surface Science, 1971,13:154-167.   
[8]余莲，张雄，王文广，罗双玲.蝎虎天体PKS $0 7 3 5 + 1 7 8$ 的光变特性分析[J].天文研究与技术，2018，15(01):10-16. YuLian,Zhang Xiong,WangWenguang,LuoShuangling.TheVariability AnalysisofPKS0735+178 [J].Astronomical research and technology,2018，15(01):10-16.   
[9]Feraz-mell SEstimationofPeriods fromUnequallySacedObservations[J].AstronomicalJoural,1981,6(86):619.   
[10]罗双玲,张雄,王文广．时间补偿离散傅里叶变换分析 PKS 1510-089 红外光变周期[J].云南师范大学学报：自然科学 版,2016,36(5): 1-4. Luo Shuangling,Zhang Xiong,Wang Wenguang.TheOptical VariabilityPeriodicityAnalysisof PKS1510-089 BasedonDate CompensatedDiscreteFourierTransform[J.JournalofYunnanNormal University:NaturalSciences Edition,2O16,36(5):1-4.   
[11]FanJH,LinRG.The variabilityanalysisofPKS2155-304[J].Astronomy&Astrophysics,200,355(3):880-884.   
[12]张蓉竹，蔡邦维，杨春林，许乔，顾元元.功率谱密度的数值计算方法[J].强激光与粒子束,200 (06):661-664. ZhangRongzhu,CaiBangwei,YangChunlin,XuQiao,GuYuanyuan.NumericalMethedof the Power Spectral Density[J].HighPower Laser and Particle Beams,2000 (06): 661-664.   
[13]张雄，谢光中，白金明.用Jurkevich方法分析计算BL Lac天体的光变周期[J].天体物理学报,1998(03):33-41. ZhangXiong,XieGuangzhong,BaiJinming.ComputingthePeriodofLightVariabilityinBLLacObjectsusingtheJurkevich Method[J].ACTA ASTROPHYSICA SINICA,1998(03): 33-41.   
[14]Kidger，MR.，Takalo，L.，& Silanp,A.Anewanal2ysisof the11-yearperiodinOJ287:confirmationof its existence[J]. Astronomy and Astrophysics,1992,264:32 - 361.   
[15]PYATUNINATB，KUDRYAVTSEVANA，GABUZDA DC，et al.Frequency-dependent time delays for strong outbursts in selectedBlazarsfromthe MetsahoviandUMRAOmonitoringdatabases-I[J].MonthlyNoticesoftheRoyalAstronomical Society,2007,381(2): 797-8.   
[16]HeidtJ,WagnerSJStatisticsofopticalintradayvariabilityinacompletesampleofadioselectedBLLacjects[J]Astrooy and Astrophysics,1996,305:42-52   
[17]刘凯博,杨东末,侯德东,张雄,丁亮,唐玲,董富通.Jurk evich方法在3C120天体光变周期分析中的应用[J].云南师范大学学报(自 然科学版),2009,29(05):1-5+16. LiuKaiBo,YangDongmo,HouDedong,ZhangXiong,DingLiang,DongFutong.ComputingthePeriodof Light VariabilityinSeyfert Galaxy3C12OUsingtheJurkevichMethod[J].Journal of Yunnan Normal University:Natural SciencesEdition, 2009,29(05):1- $5 { + } 1 6$   
[18]李怀珍.Blazar天体的光变及能谱分布的研究[D].云南大学,2011. Li Huaizhen.Studyonthe lightand energy spectrum distributionof Blazar celestialbodies [D]. Yunnan University,2011.   
[19]苏成悦.类星体PKS $2 2 5 1 + 1 5 8$ 的长期光学光变周期分析[J]. Research in Astronomy and Astrophysics,2000,20(1):11-16. Su Chengyue. Long-term optical photoperiod analysis of quasar PKS $2 2 5 1 \substack { + 1 5 8 }$ [J]. Research inAstronomyand Astrophysics,2000, 20(1):11-16.

# Study on long-period variability analysis methods ofquasars

Yu Lian， Zhang Xiongt， ZhangHaojing，LiFuting，XuXiaoling，RenGuowei，WuYuecheng (College ofPhysics and Electronics，YunnanNormal University，Kunming 6505oo，China，Email: ynzx@yeah.net)

Abstract:This paper first introduces four methods for analyzing long-period variability of quasars, then useing a simulated periodic signal $y = \sin \theta$ to test four methods.The analysis results show:1. When the number of data points sampled by the celestial body is relatively small to a certain value,the analysis results of Jurkevich method,DCDFTmethod,DCFmethod andPSDmethodare different,After geting the shortest continuous data point,the analysis result of Jurkevich method is probably the most accurate and reliable among the four methods,and the calculation method is simple and practical.2.The best parameters of the Jurkevich analysis method were obtained, The best results are when $\mathrm { m } { = } 9 . 3 .$ Using the Jurkevich method withm $_ { ! = 9 }$ to analysis the variability of 3C279 is about $\left( 2 . 8 1 \pm 0 . 5 4 \right)$ years and thevariability of 3C 454.3 is about $4 5 7 d$

Key words:Quasars; Jurkevichmethod; DCDFT method; DCF method; PSD method;Long-period variability