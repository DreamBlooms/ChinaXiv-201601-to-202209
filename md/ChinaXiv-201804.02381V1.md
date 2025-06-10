# 动态分组混沌伪随机数发生器

曹艳艳1,²，杨波1,2†

(1.陕西师范大学 计算机科学学院，西安710119;2.中国科学院信息工程研究所，信息安全国家重点实验室，北京100093)

摘要：为了克服计算机处理数据的有限精度导致混沌特性退化的缺陷，改善随机数发生器输出序列的随机性能，设计了一种新的基于Logistic 混沌映射生成伪随机数的方法。在提出的方法中，采用四个一维 Logistic 混沌映射，每次迭代随机选择扰动源对其他三个Logistic映射进行扰动，加入可变扰动参数，组合时随机动态分组，从而提高序列的随机性能，扩大序列周期，避免序列的重复出现。以新方法设计的伪随机数发生器易于软件实现，生成的序列通过随机数检测标准NISTSP800-22，从而具有良好的随机性，可用于保密通信等信息安全领域。

关键词：混沌系统；Logistic映射；伪随机数发生器；S-box 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.02.0103

# Chaotic pseudorandom generators based on dynamically group

Cao Yanyan1, 2, Yang Bo1, 2† (1.Schoolof Computer Science Shaanxi Normal UniversityXi'an710l19,China;2.State Key Laboratoryof Information Security,Institute of Information Engineering, Chinese Academy ofSciences,Beijing 10o093,China)

Abstract: In order to overcome the degration of chaoticand improve therandomnessof the sequence,this paper proposeda new method of generating pseudo-random numbers based onLogisticchaotic mapping.It used fourone-dimensional Logistic chaotic maps.Each iterationrandomly selected one to perturb the other threeLogistic maps,ading variable parameters and randomly grouping them dynamically to improve therandomnessof the sequences.Meanwhile,it enlarged the periodof sequenceand avoided recurence ofsequences.The pseudo-randomnumber generatoris easy to implement bysoftware.The sequencecanpasstheNISTSP8oo-22 randomness test.Ithas goodrandomnessandcanapply inthefieldofinformationsecurity such as secure communication.

Key words:chaotic system; logistic map; pseudorandom generator; S-box

# 0 引言

随机数广泛应用于加密及签名等，其随机性能影响加密及签名方案的安全，因此研究构造性能良好的随机数发生器已成为必然趋势。随机数发生器主要分为真随机数发生器和伪随机数发生器。真随机数发生器一般采用物理方法生成，主要包括直接放大法、振荡采样法和亚稳态采样法。首先，真随机数发生器需要随机性很高的物理熵源，而物理熵源易受到外部环境的影响，从而影响序列的随机性能。其次，真随机数发生器需要的成本高。为了克服真随机数发生器以上缺点，学者们继而研究了伪随机数发生器。伪随机数发生器是确定性算法。输入种子，经过多次迭代，获得与真随机数序列接近的伪随机数序

列。

混沌是确定但不可预测的复杂动力学现象。混沌映射对初始值敏感而表现出的不可预测、类似随机性的特性广泛应用于伪随机数发生器的构造。利用混沌构造伪随机数发生器易于软件实现，生成速率较快。Lorenz[1]于1963 年发现混沌现象。随后，混沌在安全通信[2]、文本加密[3]以及生成随机数[4\~14]等方面，取得了良好的效果。Wang等人[4]利用基于分段Logistic 映射，Garcia-Martinez等人[5]利用k-modal映射和Murillo-Escobar等人[6利用提高的Logistic 映射构造伪随机数发生器。利用这些改进Logistic映射构造的伪随机数发生器，改善生成序列的随机性能，但是其计算量较大。Patidar、Francois和Tamilselvi等人[7\~10]相继提出多个Logistic 映射组合的方式，进一步改善了序列的随机性能，但是在数字化过程中，未能克服混沌退化对序列随机性的影响。Liu等人[I]利用Chen连续超混沌系统和董丽华等人[12]利用六维细胞神经网络构造伪随机数发生器，通过增加计算成本，提高输出序列的随机性能。Bahi等人[13]提出扰动优化和Wang等人[14]将混沌与可变扰动参数相结合构造的伪随机数发生器，扩大随机序列的周期。为了克服有限精度导致混沌退化，提高生成序列的随机性能，本文利用动态分组的随机数生成方法。该方法采用四个一维Logistic映射生成伪随机序列。每次迭代随机选择一个Logistic 映射作为扰动源对其他三个Logistic映射进行扰动，随后生成的数据经过S盒[15]变化，动态分组，每次生成16位伪随机序列。参数进行动态更新，从而有效避免序列重复出现，扩大序列的周期。测试结果表明该方法生成的随机序列符合国际随机数检测标准NISTSP800-22的要求。

# 1 相关混沌映射

Logistic[16混沌映射是一维非线性离散混沌系统，因其实现简单，计算量少，经常用于图像加密及伪随机数的生成。其迭代方程为

$$
x _ { n + 1 } = \mu x _ { n } ( 1 - x _ { n } ) \ _ { \circ }
$$

其中： $\textstyle { \mathfrak { x } } _ { n }$ 为迭代状态值，取值范围为(0.1)； $\mu$ 为控制参数。图1为Logistic的倍周期分叉图，横轴表示控制参数，纵轴表示迭代状态值。当 $\mu$ 不断变化时，其迭代过程发生显著的变化。$\mu > 3 . 5 7$ ,Logistic 映射进入混沌状态。为了提高序列随机性能，Logistic 映射的控制参数取值为：3.9999。

Lyapunov指数刻画混沌系统对初始值的敏感性。给定两个相差微小的初始值，系统会随着时间变化产生两种截然不同的运动轨迹。当Lyapunov指数是负数时，表明该系统的运动轨迹是收缩的，在相应方向上的状态趋于稳定；反之，当Lyapunov指数是正数时，表明系统进入混沌状态，不可预测其运动轨迹。混沌初始值分别为0.000125，0.0001251，迭代100次后的轨迹如图2所示。

![](images/34ad2c14546415a804e3f5d0f7fcbec53f215e969602aa0c5de17a8b81a476b9.jpg)  
图1Logistic 映射的倍周期分叉图

![](images/509bdd2d9159712d2920260b0312860a02cb79af7170744bbefd4bc4c3bd9860.jpg)  
图2不同初值的轨迹图

图2表明随着混沌迭代次数的增加，相差十分微小的两个初始值产生两种截然不同的轨迹，这一特性很难确定混沌的初始值，从而保证了混沌用于加密时的安全性。

# 2 伪随机数生成方法

随机数生成方法具体由以下步骤组成（ $S ( x )$ 表示AES加密的S盒变化）：

a)初始化。密钥流序列 $K$ ：

$$
\begin{array} { r } { K = k _ { 1 - 1 6 } k _ { 1 7 - 3 2 } k _ { 3 3 - 4 8 } k _ { 4 9 - 6 4 } k _ { 6 5 - 7 2 } k _ { 7 3 - 8 0 } k _ { 8 1 - 8 8 } k _ { 8 9 - 9 6 } } \\ { k _ { 9 7 - 1 0 4 } k _ { 1 0 5 - 1 1 2 } k _ { 1 1 3 - 1 2 0 } k _ { 1 2 1 - 1 2 8 } k _ { 1 2 9 - 1 3 6 } k _ { 1 3 7 - 1 4 4 } k _ { 1 4 5 - 1 5 2 } } \end{array}
$$

密钥流序列 $K _ { 1 } ( k _ { 1 - 1 6 } )$ ， $K _ { 2 } ( k _ { 1 7 - 3 2 } )$ ， $K _ { 3 } ( k _ { 3 3 - 4 8 } )$ ， $K _ { 4 } ( k _ { 4 9 - 6 4 } )$ 初始化四个Logistic 的初始值 $x _ { 1 }$ ${ \bf \dot { \tau } } _ { 1 } \ , x _ { 2 } \ , x _ { 3 } \ ,$ $x _ { 4 }$ ，每个密钥16 bits,共 64 bits； $K _ { 5 } ( k _ { 6 5 - 7 2 } )$ ， $K _ { 6 } ( k _ { 7 3 - 8 0 } )$ ， $K _ { 7 } ( k _ { 8 1 - 8 8 } )$ ， $K _ { 8 } ( k _ { 8 9 - 9 6 } )$ ，$\begin{array} { r } { \left( k _ { \mathfrak { g } _ { 7 - 1 0 4 } } \right) , K _ { 1 0 } ( k _ { 1 0 5 - 1 1 2 } ) , K _ { 1 1 } ( k _ { 1 1 3 - 1 2 0 } ) , K _ { 1 2 } ( k _ { 1 2 1 - 1 2 8 } ) , K _ { 1 3 } ( k _ { 1 2 9 - 1 3 6 } ) } \end{array}$ $K _ { \scriptscriptstyle { 1 4 } } ( k _ { \scriptscriptstyle { 1 3 7 - 1 4 4 } } )$ ， $K _ { ^ { 1 5 } } ( k _ { ^ { 1 4 5 - 1 5 2 } } )$ 初始化参数 $C _ { 1 }$ ， $C _ { 2 }$ $\dag \begin{array} { c c } { { , } } & { { C _ { 3 } , ( } } \end{array}$ $, \ C _ { 4 } ,$ $C _ { 5 }$ ，$C _ { 6 }$ ， $C _ { 7 }$ ， $C _ { 8 }$ ， $C _ { 9 }$ ， $C _ { 1 0 }$ ， $C _ { 1 1 }$ ，每个参数8 bits，共88 bits。

b）每个Logistic迭代100次，进入混沌状态。

c）根据随机扰动参数 $C _ { 1 }$ 选择扰动顺序：

$$
i = C _ { 1 } { \bmod { 4 } }
$$

第 $i$ 个Logistic 映射做为扰动源，对其他的Logistic 映射进行随机扰动：

$$
x _ { ( i + 1 ) \mathrm { m o d } 4 } = x _ { i } + x _ { ( i + 1 ) \mathrm { m o d } 4 }
$$

$$
x _ { ( i + 2 ) \mathrm { m o d } 4 } = x _ { i } / 2 + x _ { ( i + 2 ) \mathrm { m o d } 4 }
$$

$$
x _ { ( i + 3 ) \mathrm { m o d } 4 } = x _ { i } / 4 + x _ { ( i + 3 ) \mathrm { m o d } 4 }
$$

四个Logistic 映射输出数据根据 $\left( C _ { 2 } { \bmod { 4 } } \right)$ 奇偶性（ $C _ { 3 }$ ，$C _ { 4 }$ ， $C _ { 5 }$ 相同处理）进行左移或右移（偶数左移，奇数右移）。每个数据移位处理后的四个数据经过S盒变化后形成 $^ { 4 ^ { * } 4 }$ 的矩阵。

d）主对角线、副对角线分别将矩阵分成了两个区域。当参数 $C _ { 6 }$ 为偶数时，输出的两个数据 $P _ { 1 } , P _ { 2 }$ 是主对角线划分的两个区域数据的异或和。当参数 $C _ { 6 }$ 为奇数时，输出的两个数据 $P _ { 1 } , P _ { 2 }$ 是副对角线划分的两个区域数据的异或和。

e）扰动参数 $\boldsymbol { \mathcal { Q } }$ 是由密钥 $( C _ { 7 } C _ { 8 } C _ { 9 } C _ { 1 0 } )$ 控制的可变参数经过S 盒变化后的数据，其中 $\boldsymbol { \mathcal { Q } }$ 如下：

$$
Q = S ( C _ { 7 } C _ { 8 } ^ { 3 } + C _ { 9 } C _ { 1 0 } ^ { 2 } )
$$

f）最后输出的伪随机数分别为

$$
P _ { 1 } ^ { \prime } { = } S ( P _ { 1 } \oplus Q ) ~ , ~ P _ { 2 } ^ { \prime } { = } S ( P _ { 2 } \oplus Q )
$$

g）根据 $\left( C _ { 1 1 } \mathrm { m o d } 4 \right)$ 奇偶性进行拼接，拼接方式如下：若为奇数输出的伪随机序列： $P = P _ { 1 } ^ { \prime } | \left| P _ { 2 } ^ { \prime } \right.$ ,否则 $P = P _ { 2 } ^ { \prime } \left| \left| P _ { 1 } ^ { \prime } \right. \right.$

h）参数 $( C _ { 1 } C _ { 2 } C _ { 3 } C _ { 4 } C _ { 5 } C _ { 6 } C _ { 7 } C _ { 8 } C _ { 9 } C _ { 1 0 } C _ { 1 1 } )$ 更新，参数$( C _ { 2 } C _ { 3 } C _ { 4 } C _ { 5 } C _ { 8 } C _ { 9 } )$ 与 $P$ 的前8位进行异或操作。其他参数与 $P$ 的后8位进行异或操作。

i）重复 $\mathrm { { c ) \mathord { \sim } h } } ,$ 多次，直到输出指定长度的序列为止。

# 3 安全性分析

# 3.1 密钥空间分析

为使随机数发生器拥有足够大的密钥空间来抵抗穷举攻击，本文采用四个Logistic 混沌映射交替扰动，多参数参与运算，动态分组的构造方法。每个Logistic 映射采用16位密钥进行初始值设置，十一个参数分别用8位密钥进行初始值设置。与文献[5,6]进行密钥长度比较，结果如表1。本方案密钥长一共有152位，大于128位，可有效的抵抗穷举攻击。

表1密钥长度分析表  

<html><body><table><tr><td>方法</td><td>密钥长度</td></tr><tr><td>文献[5]</td><td>159</td></tr><tr><td>文献[6]</td><td>128</td></tr><tr><td>本文方法</td><td>152</td></tr></table></body></html>

# 3.2 密钥敏感性分析

利用混沌构造伪随机数发生器，应该保持混沌对初值敏感性的特性。位变化率[17衡量混沌伪随机数发生器对初值敏感性的程度。位变化率即对密钥仅做微小改变后，生成的伪随机序列与之前伪随机序列变化位数的比例。当密钥发生微小改变后，理想位变化率为 $50 \%$ 。在仿真过程中，初始密钥为：0x1F362E5B,0x9ACD5867，0x0C4E4523，0xC6D11B0A， $0 \mathrm { x } 4 8 4 6 \mathrm { D E }$ 。以此生成长度为 ${ 1 0 } ^ { 9 }$ bits 的随机序列，分别改变初始密钥的1bit，测其位变化率如表2，其位变化率接近 $50 \%$ 。因此可知，密钥的微小改变引起生成伪随机序列的巨大改变，从而说明本方法生成的随机序列对密钥有高度敏感性。

表2伪随机序列的初值敏感性分析表  

<html><body><table><tr><td>密钥变化</td><td>位变化率</td></tr><tr><td>0x1F362E5B-->0x1E362E5B</td><td>50.0007%</td></tr><tr><td>0x9ACD5867-->0x9ACD5866</td><td>49.9980%</td></tr></table></body></html>

# 3.3NIST随机性检测

随机数发生器测试标准[18]是美国国家标准和技术研究院（NIST）发行的联邦信息处理标准，简称FIPS标准，此套统计测试方法包括15个检测项，既适用于加密算法的随机性测试，也适用于随机数发生器的性能测试。

NIST-STS检测需要提供长度至少1Gbits的待检验序列，由于NIST-STS 检验包将序列分为1000个长度为1Mbits 的子序列，所以每一种统计检验都会得到1000个值，当 $P > \alpha$ 时，认为该种检验通过。而整个检验包的成功通过需要对如下两点作出判断：

a) $P$ 值分布的均匀性。

b)检验包中每一种检验的通过率，即 $P { > } \alpha$ 的概率。若 $P$ 值落在置信区间：

$$
\left[ 1 - \alpha - 3 \sqrt { \frac { \alpha ( 1 - \alpha ) } { n } } , 1 - \alpha + 3 \sqrt { \frac { \alpha ( 1 - \alpha ) } { n } } \right]
$$

则表明序列通过该项测试。（\*表示该项包含多个子项）。

用NIST随机性测试方法对本方法生成的1000组1Mbit数

据进行检测，得到的测试结果如表3所示。

表3 NIST SP800-22测试结果表  

<html><body><table><tr><td>测试项目</td><td>P-value</td><td>proportion</td><td>测试结果</td></tr><tr><td>Frequence</td><td>0.872425</td><td>0.996</td><td>Pass</td></tr><tr><td>Block Frequence</td><td>0.392456</td><td>0.991</td><td>Pass</td></tr><tr><td>Cumulative Sums *</td><td>0.877083</td><td>0.997</td><td>Pass</td></tr><tr><td>Runs</td><td>0.316052</td><td>0.984</td><td>Pass</td></tr><tr><td>Longest Run</td><td>0.134172</td><td>0.995</td><td>Pass</td></tr><tr><td>Rank</td><td>0.639202</td><td>0.987</td><td>Pass</td></tr><tr><td>FFT</td><td>0.371941</td><td>0.994</td><td>Pass</td></tr><tr><td>Overlapping Template</td><td>0.135720</td><td>0.990</td><td>Pass</td></tr><tr><td>Universal</td><td>0.976878</td><td>0.984</td><td>Pass</td></tr><tr><td>Linear Complexity</td><td>0.984415</td><td>0.985</td><td>Pass</td></tr><tr><td>Approximate Entropy</td><td>0.385543</td><td>0.990</td><td>Pass</td></tr><tr><td>Serial*</td><td>0.848027</td><td>0.991</td><td>Pass</td></tr><tr><td>NonOverlapping Template*</td><td>0.999887</td><td>0.989</td><td>Pass</td></tr><tr><td>Random Excursions*</td><td>0.889743</td><td>0.979</td><td>Pass</td></tr><tr><td>Random Excursions</td><td></td><td></td><td></td></tr><tr><td>Variant*</td><td>0.877436</td><td>0.990</td><td>Pass</td></tr></table></body></html>

# 3.4信息熵分析

图3中，（a）是标准8bit灰度图Lena,用作明文图像进行实验，（b）是将上述方法生成的随机数直接与明文像素值进行异或后生成的密文图像，（c）是原图像的直方图，（d）是加密后图像的直方图。从直方图可以看出，加密后图像的直方图十分均匀，说明原图像的统计规律已经破坏，攻击者很难对原始图像进行恢复。

图像的熵描述图像的平均信息量。熵值越大，图像的随机性越强，其定义如下。

$$
H ( s ) = - { \sum _ { i = 0 } ^ { 2 ^ { N } - 1 } { P ( s _ { i } ) \log _ { 2 } { P ( s _ { i } ) } } }
$$

其中： $s _ { i }$ 是信源发出的 $2 ^ { N }$ 种不同状态， $N$ 是每种状态 $s _ { i }$ 的比特数， $P ( s _ { i } )$ 表示状态 $s _ { i }$ 出现的概率。

8bit灰度图作为信源，可发出 $2 ^ { 8 }$ 种不同状态，且每种状态的概率相同，带入熵定义式，8bit灰度图的理想熵值为8。因此，本方案生成的随机数用于图像加密后，其熵接近8，则表明该图像具有良好的随机性。

![](images/9971c9581a2cfcb678951070cef698baebedb2adbed7239a4f4d5a2438557291.jpg)  
(a) Lena 图

(b）Lena 加密图

![](images/a30de24c3ff12d5750b5d896a63418c33abfe5d25a74b6bc2b5be173eaa46a23.jpg)  
  
图3Lena图

与文献[19,20]的信息熵进行比较，结果如表4。本文生成的随机数用于图像加密后的信息熵接近8，高于文献[19,20]的信息熵。

表4信息熵分析表  

<html><body><table><tr><td>方法</td><td>信息熵</td></tr><tr><td>文献[19]</td><td>7.9890</td></tr><tr><td>文献[20]</td><td>7.9915</td></tr><tr><td>本文方法</td><td>7.9954</td></tr></table></body></html>

# 3.5 相关性分析

明文图像位置相邻的像素具有很强的相关性。敌手可利用图像像素在水平、垂直和斜对角方向的规律，对其进行攻击。因此加密后图像相邻位置像素应具有较低的相关性，才能保证图像的安全。相关系数 $r _ { x y }$ 衡量加密图像像素的相关性，相关系数接近0，表明图像像素的相关性低。相关系数定义如下：

$$
r _ { x y } = \frac { \mathrm { c o v } ( x , y ) } { \sqrt { D ( x ) } \sqrt { D ( y ) } }
$$

$$
E ( x ) { = } \frac { 1 } { \eta } \sum _ { i = 1 } ^ { \eta } x _ { i }
$$

$$
D ( x ) { = } \frac { 1 } { \eta } { \sum _ { i = 1 } ^ { \eta } } ( x _ { i } - E ( x ) ) ^ { 2 }
$$

$$
\mathrm { c o v } ( x , y ) { = } \frac { 1 } { \eta } \sum _ { i = 1 } ^ { \eta } ( x _ { i } - E ( x ) ) ( y _ { i } - E ( y ) )
$$

其中， $x$ 和 $y$ 是两个相邻像素的灰度值， $\eta$ 是选取像素的个数。选取2000组像素与文献[5][19]进行水平、垂直和斜对角方向相邻像素进行相关性分析，其结果如表5（一表示未实现）。本方案生成的随机数用于图像加密相邻像素的相关系数比文献[5]更接近0，表明图像像素的规律已破坏，相关性降低。

表5相关性分析表  

<html><body><table><tr><td>相关性分析</td><td>水平</td><td>垂直</td><td>对角</td></tr><tr><td>文献[5]</td><td>0.0252</td><td>-0.0280</td><td>0.0176</td></tr></table></body></html>

<html><body><table><tr><td>文献[19]</td><td>-0.004</td><td>0.001</td><td>1</td></tr><tr><td>本文方法</td><td>-0.008</td><td>0.0250</td><td>-0.002</td></tr></table></body></html>

# 3.6差分攻击

差分攻击通过分析明文差相对应的密文差从而获取相关图像的信息。像素改变率用来衡量图像加密算法抵抗差分攻击的能力。像素改变率越高，表明算法抵抗差分攻击的能力越强。像素改变率定义如下：

$$
\mathit { N P C R } = \frac { \sum _ { i , j } \delta _ { a } ( i , j ) } { \nu } * 1 0 0 \%
$$

$$
\delta _ { a } ( i , j ) = { \left\{ \begin{array} { l l } { 0 } & { i \mathrm { f } C _ { 1 } ( i , j ) = \mathrm { C } _ { 2 } ( i , j ) } \\ { 1 } & { i \mathrm { f } C _ { 1 } ( i , j ) \neq \mathrm { C } _ { 2 } ( i , j ) } \end{array} \right. }
$$

其中， $\nu$ 是图像像素的总数， $C _ { 1 }$ 和 $C _ { 2 }$ 分别为加密图像。

与文献[5,6,19]像素改变率进行比较，结果如表6。本方案的像素改变率为 $9 9 . 6 \%$ ，表明本方案可完全抵抗差分攻击。

表6差分分析表  

<html><body><table><tr><td>文献</td><td>像素改变率</td></tr><tr><td>文献[5]</td><td>99%</td></tr><tr><td>文献[6]</td><td>99.5%</td></tr><tr><td>文献[19]</td><td>99. 6%</td></tr><tr><td>本文方法</td><td>99.6%</td></tr></table></body></html>

本文生成随机数的方法密钥空间高于文献[6。生成随机数用于图像加密，图像像素的信息熵高于文献[19][20]，相关性低于文献[5]，像素改变率高于文献[5][6]。综合比较分析，本方法生成的随机数具有良好的随机性，可用于图像加密等安全领域。

# 4 结束语

本文设计了一种新的基于Logistic 映射生成伪随机数的方法，该方法通过随机选择扰动源交替扰动动态分组的方法，改善了混沌退化对伪随机数发生器安全性的影响，减少重复序列的出现。对其性能进行仿真分析，表明本方法生成的伪随机序列具有良好的密钥敏感性，并且能通过NIST随机性检测，从而具有良好的统计特性。

# 参考文献：

[1]Lorenz E N.Deterministic nonperiodic flow[J].Journal of the atmospheric sciences,1963,20(2): 130-141.   
[2]Wang Xingyuan，Xu Bing,Zhang Huaguang.A multiary number communication system based on hyperchaotic system of 6th-order cellular neural network[J].Communications in Nonlinear Science and Numerical Simulation,2010,15(1): 124-133.   
[3]Mishra M,Mankar V H. Text encryption algorithms based on pseudo random numbergenerator [J]． International Journal of Computer Applications,2015,111 (2):1-6.   
[4]Wang Yong,Liu Zhaolong,Ma Jianbin,et al.A pseudorandom number generator based on piecewise logistic map [J].Nonlinear Dynamics,2016,

83 (4): 2373-2391.   
[5]Garcia-Martinez M, Campos-Cantón E.Pseudo-random bit generator based on multi-modal maps [J]. Nonlinear Dynamics,2015,82 (4): 2119-2131.   
[6]Murillo-Escobar MA,Cruz-Hernandez C,Cardoza-Avendano L,et al.A novel pseudorandom number generator based on pseudorandomly enhanced logistic map [J]. Nonlinear Dynamics,2017,87(1): 407-425.   
[7]Patidar V, Sud K K,Pareek N K.A pseudo random bit generator based on chaotic logistic map and its statistical testing [J].Informatica,20o9,33 (4): 441-452.   
[8]Francois M, Defour D,Negre C.A fast chaos-based pseudo-random bit generator using binary64 floating-point arithmetic [J]. Informatica,2014,38 (2): 115-124.   
[9]Francois M,Grosges T,Barchiesi D,et al. Pseudo-random number generator based on mixing of three chaotic maps [J]. Communications in Nonlinear Science & Numerical Simulation,2014,19 (4): 887-895.   
[10] Tamilselvi R,Ravindran G. Image encryption using pseudo random bit generator based on logistic maps with radon transform [J].Indian Journal of Science and Technology, 2015,8(11): 439-46.   
[11]Liu Ye,Wang Jun,Fan Jinghui,et al. Image encryption algorithm based on chaotic system and dynamic S-boxes composed of DNA sequences [J]. Multimedia Tools and Applications,2016,75 (8): 4363-4382.   
[12]董丽华，药国莉．基于细胞神经网络的伪随机数生成方法[J].通信学 报,2017,37 (Z1): 85-91. (Dong Lihua, Yao Guoli. Method for generating pseudo random numbers based on cellular neural network [J]. Journal on Communications,2017,37 (Z1): 85-91. )   
[13] Bahi JM, Fang X, Guyeux C.An optimization technique on pseudorandom generators based on chaotic iterations [J].arXiv preprint arXiv: 2017:1706. 08773.   
[14] Wang Kaiyu, Yan Qingxin,Yu Shihua, et al. High throughput pseudorandom number generator based on variableargument unified hyperchaos [J].VLSI Design,2014,2014: 9.   
[15] Selent D.Advanced encryption standard [J].Rivier Academic Journal,2010, 6 (2): 1-14.   
[16] Wang Bin，Wei Xiaopeng,Zhang Qiang.Cryptanalysis of an image cryptosystem based on logistic map [J]. Optik:International Journal for Light and ElectronOptics,2013,124 (14): 1773-1776.   
[17]张雪锋，范九伦．基于线性反馈移位寄存器和混沌系统的伪随机序列 生成方法 [J].物理学报,2010,59 (4):2289-2297.(Zhang Xuefeng,Fan Jiulun.Pseudo-random sequence generating method based on LFSR and chaotic system [J].Acta Physica Sinica,2010,59 (4): 2289-2297.)   
[18] RukhinA, Soto J,Nechvatal J,etal.A statistical test   
[19] suite for random and pseudorandom number generators forcryptographic applications [R]. Booz-Allen and Hamilton Inc Mclean Va,2001.   
[20] Hossain MB,Rahman MT,Rahman AB M S,et al.A new approach of image encryption using 3D chaotic map to enhance security of multimedia component [C]// Proc of International Conference on Informatics, Electronics&Vision.2014:1-6.   
[21] Zahmoul R,Zaied M. Toward new family beta maps for chaotic image encryption [C]//Proc of IEEE InternationalConference on Systems,Man, and Cybernet.2016: 004052-004057.