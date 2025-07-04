# 双稳系统中的随机共振乘性信噪作用研究

徐 江1\*，郭锋2,陈勇3

（1.四川压电与声光技术研究所，重庆 400060;2.西南科技大学信息工程学院,四川绵阳 621010;3.中国科学院新疆天文台,新疆乌鲁木齐 830011)

摘要：方波信号和双值噪声在科学领域广泛应用，而乘性信号在工程中广泛存在。但是，就乘性方波信号和乘性双值噪声对双稳系统的非线性影响方面的研究还较少，因此本文研究乘性方波信号和乘性双值噪声作用下双稳系统中的随机共振现象。基于绝热近似条件，推导系统的信噪比的表达式并基于该公式进行了不同输入条件的仿真研究。研究结果表明，信噪比随着乘性方波信号和乘性双值噪声幅度的变化可以取得一个最大值和一个最小值。大的乘性方波信号幅值会抑制信噪比,对于噪声相关率 $\lambda { = } 0 . 6 5$ 情形，方波幅值 $A = 1 . 0$ 时的系统输出幅度比 $A = 0 . 3$ 时的输出幅值下降约 $2 9 \%$ ；而较大的乘性双值噪声强度可以提升系统输出性能，当系统参数 $b = 3 . 8$ ，乘性双值噪声强度为 $\scriptstyle { \varepsilon = 3 . 5 }$ 时的系统输出幅度为 $\scriptstyle { \varepsilon = 0 . 2 5 }$ 时的输出幅值的2.5倍。随着乘性白噪声、加性白噪声及系统参数的变化，信噪比曲线出现一个峰值。

关键词：随机共振；双稳系统；乘性方波信号；乘性双值噪声中图分类号：TN911.7 文献标识码：A 文章编号：1672-7673（2020）03

随机共振是乘性在随机动力系统中的非线性现象。当作用于系统的噪声、系统输入信号和系统三者间协同作用时，噪声对系统输出性能有所影响。随机共振的概念由文[1]提出，用于对周期性出现的地球冰川时代进行合理的建模分析。从此以后，随机共振现象得到广泛研究[2]。随机共振也广泛存在于天文领域，比如，太阳耀斑和喷流中，与磁重联相关的随机共振加速，不但产生电子，而且导致 3He/4He千倍的增强。小行星 Bennu(101955)在行星碰撞和随机共振的联合作用下，经过几百万至几千万年，到达目前的运行轨道[4]。电子与加速圆环面小区域中的湍动磁场相互作用的随机共振加速，可能是人马座A的毫米和短波频谱的产生机制[5]。在射电天文接收机中也满足随机共振条件，即：接收机噪声、输入信号（射电天文信号、无线电干扰信号）以及接收机相关参数，如增益、稳定性、动态范围、噪声系数、矩形系数等相互作用，共同作用决定了整个观测效果。

方波信号可以看作在两个电平间切换的数字信号。随着集成电路的快速发展，方波信号在数字通信系统中起着越来越重要的作用。比如，可以作为数字逻辑系统的输入信号，作为时钟信号准确地触发同步电路。另一方面，双值噪声是工程应用中常见的干扰。比如，随机电报噪声是电子工程领域一种典型的双值噪声。在半导体器件中，闪存产生的随机电报噪声影响信息的正确读取。

系统的输入信号通常具有加性的形式，即以加法的形式作用于系统。然而，在某些情况下，输入信号是状态依赖性的，输入信号应该是与系统状态变量相乘的形式。目前乘性信噪作用对射电天文接收机可能存在干扰,特别是在强干扰信号作用下，均以乘性结果输出[6]。目前，射电天文台址的无线电环境测量较多关注干扰信号频点和噪底水平[7-8]，但对强干扰可能导致的接收机内部交调后的噪声变化却没有相关研究报道。同时该研究结果，可以用于基于锁相放大的微弱信号提取[9-10]，而锁相放大后引起的信噪比提升一直是值得研究的问题。基于此，本文旨在研究乘性方波信号和乘性双值噪声作用下非线性双稳系统中的非线性共振行为。通过仿真定量分析，得到非线性共振行为的能谱分布规律，为强无线电干扰情况下的接收机设计、干扰信号处理提供依据。

# 1乘性方波和乘性双值噪声作用下的双稳系统

乘性信号和乘性噪声作用下的双稳系统满足[1-2]：

$$
\frac { d x ( t ) } { d t } = [ a + f ( t ) ] x ( t ) - b x ^ { 3 } ( t ) + \xi ( t ) x ( t ) + \eta ( t ) ,
$$

其中， $a$ 和 $b$ 为系统参数 $( a > 0 , b > 0 )$ ），

$$
f ( t ) = r + \varepsilon \varsigma ( t ) + A s ( t )
$$

为乘性信号。 $\varsigma ( t )$ 为对称双值噪声， $\varsigma ( t ) = \left\{ 1 , - 1 \right\}$ ，其相关率为 $\lambda _ { \mathrm { 0 } }$ 。 $s ( t )$ 为周期为 $T$ 的方波信号：

$$
s ( t ) { = } \left\{ \begin{array} { l } { 1 , 0 { \leq } t < T / 2 } \\ { - 1 , T / 2 { \leq } t < T } \end{array} \right. .
$$

$r$ 为直流偏置； $\varepsilon$ 和 $A$ 分别为乘性双值噪声和乘性方波信号的幅度。若 $f ( t ) = 0$ ，则系统 (1)为一双稳系统，一个非稳态和两个稳态 $\underline { { x _ { + } } } = \pm \sqrt { a / b }$ 。限制参数 $f ( t )$ 的取值使其满足$a + f ( t ) > 0$ 。 $\xi ( t )$ 和 $\eta ( t )$ 为相关白噪声，其均值为0，相关函数为

$$
\left. \xi ( t _ { 1 } ) \xi ( t _ { 2 } ) \right. = 2 D \delta ( t _ { 1 } - t _ { 2 } ) \nonumber ,
$$

$$
\left. \eta ( t _ { 1 } ) \eta ( t _ { 2 } ) \right. = 2 P \delta ( t _ { 1 } - t _ { 2 } ) \ ,
$$

$$
\left. \xi ( t _ { 1 } ) \eta ( t _ { 2 } ) \right. = \left. \eta ( t _ { 1 } ) \xi ( t _ { 2 } ) \right. = 2 \lambda \sqrt { D P } \delta ( t _ { 1 } - t _ { 2 } ) ,
$$

其中， $D$ 和 $P$ 分别为乘性和加性噪声的强度； $\lambda$ 为两噪声间的耦合强度， $0 < \lambda < 1$ 。由(1)、 (5)和(6)式，系统(1)对应的Fokker-Plank方程可以表示为

$$
\frac { \hat { \mathcal { O } } \rho ( x , t ) } { \hat { \mathcal { O } } t } = - \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } x } [ F ( x , t ) \rho ( x , t ) ] + \frac { \hat { \mathcal { O } } ^ { 2 } } { \hat { \mathcal { O } } x ^ { 2 } } [ G ( x , t ) \rho ( x , t ) ] ,
$$

其中

$$
F ( x , t ) = a x - b x ^ { 3 } + D x + \lambda \sqrt { D P } + x f ( t ) ,
$$

$$
G ( x , t ) = D x ^ { 2 } + 2 \lambda \sqrt { D P } x + P .
$$

设方波信号为一个缓变信号，系统(1)在一个周期 $T$ 的时间内足够达到局域平衡，即系统(1)满足绝热近似条件[2，这样可以由(7)-(9)式推导其长时间的渐近分布函数,即

$$
\rho _ { s t } ( x , t ) = \frac { M } { \sqrt { G ( x , t ) } } \exp [ - \Phi ( x , t ) ] ,
$$

其中， $M$ 为归一化常数； $\Phi ( x , t )$ 为修正的势能函数

$$
\Phi ( x , t ) { = } \int _ { - \infty } ^ { x } { - } d x ^ { \prime } \mathrm { F } ( x ^ { \prime } , t ) / G ( x ^ { \prime } , t ) \circ 
$$

在绝热近似条件下，粒子在两稳态的转移率可以表示为

$$
\begin{array} { r l } { \mathcal { L } _ { - } ( \mu ) = \frac { - \alpha } { \sqrt { 2 } \pi } \exp [ \Phi ( x _ { s } ) - \Phi ( x _ { s } ) ] } \\ & { = - \frac { \alpha } { \sqrt { 2 } \pi } \exp [ \frac { \alpha } { 2 D } \mathbf { f } ^ { 2 } ( 2 \sqrt { a b D P ^ { \prime } } D ^ { 2 } ) ^ { 2 } ] } \\ & { \qquad \times \exp [ \frac { \alpha + D + b P / D - 4 b \beta ^ { 2 } P P / D } { 2 D } \ln ( \frac { P } { D \alpha / b \pm 2 \lambda \sqrt { a D P ^ { \prime } / b } + P } ) ] } \\ & { \qquad \times \exp [ \frac { \mu - \lambda \sqrt { D P } - 2 b \lambda \sqrt { D P } / D ^ { 2 } } { \sqrt { D } ( 1 + \lambda ^ { - \frac { \lambda ^ { \prime } } { 2 } } ) P }  } \\ & { \qquad \times [ \mathrm { a r c i a n } ( \frac { \lambda \sqrt { P } } { D \sqrt { 1 ( 1 - \lambda ^ { - \frac { \lambda ^ { \prime } } { 2 } } ) P } } ) - \mathrm { a r c a n } ( \frac { \mathbf { f } \sqrt { a P } + 2 \sqrt { P } / \sqrt { D } } { \sqrt { D } ( 1 - \lambda ^ { - \frac { \lambda ^ { \prime } } { 2 } } ) P } ) ] ] , } \end{array}
$$

系统输出的相关函数可以表示为[12]

$G ( t ) = [ B _ { 1 } ( r , \varepsilon , A ) + B _ { 3 } ( r , \varepsilon , A ) ] \exp ( - \lambda _ { 0 } \left| t \right| ) + B _ { 2 } ( r , \varepsilon , A ) \varphi ( t ) + C ( r , \varepsilon , A ) \delta ( t ) \ ,$ 其中

$$
B _ { 1 } ( r , \varepsilon , A ) = \frac { 1 } { 1 6 } \lbrack w ( r + \varepsilon + A ) - w ( r - \varepsilon - A ) + w ( r + \varepsilon - A ) - w ( r - \varepsilon + A ) \rbrack ^ { 2 } ,
$$

$$
B _ { 2 } ( r , \varepsilon , A ) = \frac { 1 } { 1 6 } \big [ w ( r + \varepsilon + A ) - w ( r - \varepsilon - A ) - w ( r + \varepsilon - A ) + w ( r - \varepsilon + A ) \big ] ^ { 2 } ,
$$

$$
B _ { 3 } ( r , \varepsilon , A ) = \frac { 1 } { 1 6 } [ w ( r + \varepsilon + A ) + w ( r - \varepsilon - A ) - w ( r + \varepsilon - A ) - w ( r - \varepsilon + A ) ] ^ { 2 } ,
$$

$$
C ( r , \varepsilon , A ) = \frac { 1 } { 4 } [ C _ { 0 } ( r + \varepsilon + A ) + C _ { 0 } ( r - \varepsilon - A ) + C _ { 0 } ( r + \varepsilon - A ) + C _ { 0 } ( r - \varepsilon + A ) ] \ ,
$$

$$
w ( \mu ) = \sqrt { \frac { a } { b } } \frac { W _ { - } ( \mu ) - W _ { + } ( \mu ) } { W _ { - } ( \mu ) + W _ { + } ( \mu ) } ,
$$

$$
C _ { 0 } ( \mu ) = \frac { 8 W _ { + } ( \mu ) W _ { - } ( \mu ) } { [ W _ { + } ( \mu ) + W _ { - } ( \mu ) ] ^ { 3 } } ,
$$

$$
\varphi ( t ) = \frac { 4 } { \pi ^ { 2 } } \sum _ { j = 0 } ^ { \infty } \left( 2 j + 1 \right) ^ { - 2 } \exp [ - i ( 2 j + 1 ) \Omega t ] .
$$

对 (10)式两边进行傅里叶变换，得

$$
S ( \omega ) = S _ { 1 } ( 0 ) + S _ { 2 } ( \omega ) ,
$$

其中

$$
\begin{array} { l } { \displaystyle S _ { 1 } ( 0 ) = \frac { 2 } { \lambda } [ B _ { 1 } ( r , \varepsilon , A ) + B _ { 3 } ( r , \varepsilon , A ) ] + C ( r , \varepsilon , A ) , } \\ { \displaystyle S _ { 2 } ( \omega ) = B _ { 2 } ( r , \varepsilon , A ) \phi ( \omega ) , } \\ { \displaystyle \phi ( \omega ) = \frac { 8 } { \pi } \sum _ { i = 0 } ^ { \infty } ( 2 i + 1 ) ^ { - 2 } \delta [ \omega - ( 2 i + 1 ) \Omega ] . } \end{array}
$$

这里 $S _ { 1 } ( 0 )$ 为零频率处的噪声背景功率； $S _ { 2 } ( \omega )$ 为输出信号的功率谱。系统输出信噪比定义为信号的基波频率处功率与背景噪声功率之比，即

$$
S N R = \frac { 8 } { \pi } \frac { B _ { 2 } ( r , \varepsilon , A ) } { C ( r , \varepsilon , A ) + 2 [ B _ { 1 } ( r , \varepsilon , A ) + B _ { 3 } ( r , \varepsilon , A ) ] / \lambda } .
$$

# 2讨论

基于绝热近似条件推导了研究的双稳系统的渐近分布函数和稳态间转移率。由相关函数得到了输出信号的功率谱，进而求得了系统的输出信噪比。现在基于(25)式,分析信噪比的非单调行为。利用图1和表1分析乘性双值噪声对系统信噪比的影响。由图1和表1可见，在 信噪比与乘性噪声幅度 $\varepsilon$ 的关系曲线上出现了两个极值，一个极大值，一个极小值。随着 $\varepsilon$ 的增大，信噪比先快速增大至最大值，然后缓慢地减小到最小值,最后单调增大。较大的乘性双值噪声幅度可以提升系统输出性能，由表1可得，对于 $b = 3 . 8$ 情形， $\varepsilon { = } 3 . 5$ 时系统输出幅度为 $\scriptstyle \varepsilon = 0 . 2 5$ 时的输出幅值的2.5倍；而当 $b { = } 4 . 0$ 时， $\varepsilon { = } 3 . 5$ 时输出幅度为$\scriptstyle { \varepsilon = 0 . 2 5 }$ 时的输出幅值的 2.15倍。本文研究发现，乘性双值噪声对信噪比的影响与文[12-14]中加性双值噪声对信噪比的影响不同。对于加性噪声情形，在信噪比与双值噪声幅度的曲线上或者仅有一个极值，即最大值[12]，或者虽然有两个极值出现，但先出现最小值，而后出现最大值[13-14]。

表1系统参数b和双值噪声幅度 $\varepsilon$ 取不同值时的信噪比 $\left( 1 0 ^ { - 9 } \right)$   
Table1 The SNR for different values of the system parameter $^ b$ and amplitude $\varepsilon$ of the multiplicative dichotomous noise   

<html><body><table><tr><td></td><td>0.25</td><td>0.50</td><td>1.00</td><td>1.50</td><td>2.00</td><td>2.50</td><td>3.00</td><td>3.50</td></tr><tr><td>b=3.8</td><td>3.41</td><td>5.22</td><td>5.56</td><td>5.37</td><td>5.19</td><td>5.17</td><td>5.72</td><td>8.52</td></tr><tr><td>b=4.0</td><td>4.39</td><td>6.71</td><td>7. 15</td><td>6.89</td><td>6.64</td><td>6.53</td><td>6.95</td><td>9.44</td></tr><tr><td>b=4.2</td><td>5.48</td><td>8.35</td><td>8.93</td><td>8.59</td><td>8.26</td><td>8.06</td><td>8.32</td><td>10.44</td></tr><tr><td>b=4.5</td><td>7.30</td><td>11. 17</td><td>11.88</td><td>11. 42</td><td>10.94</td><td>10.58</td><td>10.60</td><td>12.14</td></tr></table></body></html>

![](images/802a34a7a6df8de784415666d64b2bd6205f08aca25618884803bfe228e5889c.jpg)

图1系统参数 $b$ 取不同值时信噪比与双值噪声幅度 $\varepsilon$ 的关系曲线，参数为 $a = 5$ ， $D = 0 . 1$ 5 ${ P = 0 . 1 }$ $\lambda = 0 . 0 5$ ， $r = 0 . 2$ $A = 0 . 1$ ，

$$
\begin{array} { r } { \lambda _ { \mathrm { 0 } } = 1 } \end{array}
$$

Fig.1 The SNR versus amplitude $\varepsilon$ of the multiplicative dichotomous noise for $a = 5$ ， $D = 0 . 1$ ${ P = 0 . 1 }$ ， $\lambda = 0 . 0 5$ ， $r = 0 . 2$ ， $A = 0 . 1$ ， $\mathscr { \lambda } _ { 0 } = 1$ for different values of the system parameter $^ b$ （204号

由图2和表2研究信噪比与乘性方波信号幅值的依赖关系。由图2和表2可见，信噪比随 $A$ 的增大而非单调变化。随着 $A$ 的增大，信噪比先减小至一个极小值，而后增大至一个极大值，最后单调减小。可见，相对居中的幅值 $A$ (如对于 $\lambda { = } 0 . 6 5$ 取 $A \approx 0 . 6 5$ ）可以提升系统输出信号，而较高或较低的幅值 $A$ (对于 $\lambda { = } 0 . 6 5$ ，取 $A > \mathbb { \mathbb { O } }$ 或 $A \approx 0 . 3$ ）则会抑制系统性能。比如，由表2可得，对于 $\lambda { = } 0 . 6 5$ 情形， $\scriptstyle A = 1 . 0$ 时系统输出幅度比 $\scriptstyle A = 0 . 3$ 时的输出幅值下降约 $2 9 \%$ ；而当 $\lambda { = } 0 . 6 7$ 时， $\scriptstyle { \mathcal { A } } = 1 . 0$ 时的系统输出幅度比 $\scriptstyle A = 0 . 3$ 时的输出幅值下降约 $2 0 \%$ 。可见，乘性方波信号与加性方波信号对信噪比的影响是不同的。实际上，文[13-14]的研究结果表明，较高的加性方波信号幅值可以提升系统信噪比,而由图2和表2可见，较高的乘性方波信号幅值会抑制系统输出性能。另外，信噪比随两个白噪声间的耦合强度 $\lambda$ 变化也非单调变化，如图2和表2，当 $A < 0 . 8 5$ ，信噪比随着 $\lambda$ 的增大而减小，而当 $A > 0 . 9$ 时，信噪比随着 $\lambda$ 的增大而增大。

表2噪声耦合强度 $\lambda$ 和波信号幅度 $A$ 取不同值时的信噪比 $\left( 1 0 ^ { - 5 } \right)$   
Table 2 The SNR for different values of coupling strength $\lambda$ between the noises and the amplitude $A$ of the multiplicative square-wave signal   

<html><body><table><tr><td>A</td><td>0.30</td><td>0.50</td><td>0.65</td><td>0.70</td><td>0.75</td><td>0.80</td><td>0.85</td><td>0.90</td><td>0.95</td><td>1.00</td></tr><tr><td>=0.65</td><td>3.17</td><td>3.29</td><td>3.36</td><td>3.33</td><td>3.25</td><td>3.13</td><td>2.97</td><td>2.76</td><td>2.51</td><td>2.26</td></tr><tr><td>2=0.67</td><td>2.95</td><td>3.07</td><td>3.19</td><td>3.20</td><td>3.17</td><td>3.10</td><td>2.98</td><td>2.81</td><td>2.60</td><td>2.36</td></tr><tr><td>=0.69</td><td>2.76</td><td>2.86</td><td>3.02</td><td>3.05</td><td>3.06</td><td>3.03</td><td>2.96</td><td>2.83</td><td>2.67</td><td>2.46</td></tr><tr><td>2=0.72</td><td>2.51</td><td>2.58</td><td>2. 77</td><td>2.83</td><td>2.88</td><td>2.90</td><td>2.88</td><td>2.83</td><td>2.72</td><td>2.58</td></tr></table></body></html>

![](images/14ac902bf4be5d75930ed2006e6196b59eaa1e40150e4374b6ad95a964c5df9f.jpg)  
图2噪声耦合强度 $\lambda$ 取不同值时信噪比与方波信号幅度 $A$ 的关系曲线，参数为 $a = 1 . 9$ ， $b = 0 . 7$ ， $D = 0 . 3 5$ ， ${ P = 0 . 0 3 }$ ， $r = 0 . 4$ ， Fig.2 The SNR versus the amplitude $A$ of the multiplicative square-wave signal for $a = 1 . 9$ $b = 0 . 7$ ， $D = 0 . 3 5$ ， ${ P = 0 . 0 3 }$ ， $r = 0 . 4$ ， $\varepsilon = 0 . 4 5$ ， $\mathscr { \lambda } _ { 0 } = 1$ for different values of the coupling strength $\lambda$ between the noises

系统参数 $^ b$ 取不同值时，信噪比与直流偏值 $r$ 的关系曲线如图3，由图3可见每条曲线上呈现了一个峰值,即广义的随机共振现象。该现象与文[15]中的结果类似。另外，容易看出，信噪比也是参数 $^ b$ 的非单调函数。图4和图5清晰地表明，随着乘性噪声强度的增大，信噪比可以出现一个共振峰，即随机共振现象，该现象与乘性噪声作用下双稳系统[12-14,16]中出现的现象相同。而且，系统参数 $a$ 非单调地影响信噪比，如图4。

![](images/37aa4f0c090bbe794cf72376fbc86d50a582e4a08998fd85bfee3024cc3319bb.jpg)  
图3系统参数 $^ b$ 取不同值时信噪比与偏值 $\boldsymbol { r }$ 的关系曲线，参数为 $a = 2$ ， $D = 0 . 8$ ， $P = 0 . 0 4$ $\lambda = 0 . 4$ ， $\varepsilon = 0 . 8$ ， $A = 0 . 0 1$ ， $\begin{array} { r } { \lambda _ { \mathrm { 0 } } = 1 } \end{array}$ Fig.3 The SNR versus the bias $^ r$ for $a = 2$ ， $D = 0 . 8$ ， $P = 0 . 0 4$ ， $\lambda = 0 . 4$ ， $\varepsilon = 0 . 8$ ， $A = 0 . 0 1$ ， $\mathscr { \lambda } _ { 0 } = 1$ for different values of thesystem parameter $^ b$ （204号

![](images/e80db4c6adba5e6787473ef91172282379bcc11e462eb72dbd50cc0cbd1f132f.jpg)  
Fig.4 The SNR versus the multiplicative white noise intensity $D$ for $b = 0 . 7$ ， $P = 0 . 2 5$ ， $\lambda = 0 . 1 5$ ， $r = 0 . 1$ ， $\varepsilon = 0 . 1$ 5 $A = 0 . 1$ ， $\lambda _ { \mathrm { 0 } } = 1$ for different values of the system parameter $^ a$ （204号

图4系统参数 $a$ 取不同值时信噪比与乘性增大强度 $D$ 的关系曲线，参数为 $b = 0 . 7$ ， $P = 0 . 2 5$ $\lambda = 0 . 1 5$ ， $r = 0 . 1$ ， $\varepsilon = 0 . 1$ ， $A = 0 . 1$ ，$\begin{array} { r } { \lambda _ { \mathrm { 0 } } = 1 } \end{array}$

![](images/8bcb7a5627038959fc4d443c8ea989d343d48a39325254447976ced215505766.jpg)

图5 噪声耦合强度λ取不同值时信噪比与乘性白噪声强度 $D$ 的关系曲线，参数为 $a = 0 . 9$ ， $b = 0 . 9$ ， $P = 0 . 2$ ， ${ r = 0 . 0 1 }$ ， $\varepsilon = 0 . 1$

$$
A = 0 . 1 , \lambda _ { 0 } = 1
$$

Fig.5 The SNR versus the multiplicative white noise intensity $D$ for $a = 0 . 9$ ， $b = 0 . 9$ ， $P = 0 . 2$ ${ r = 0 . 0 1 }$ ， $\varepsilon = 0 . 1$ $A = 0 . 1$ ， $\lambda _ { \mathrm { 0 } } = 1$ for different values of the coupling strength $\lambda$ between the noises

图6 表明，信噪比是加性白噪声强度的非单调函数。随着加性噪声强度的增大，系统输出信噪比先单调增大，直到其最大值，而后随着加性噪声强度的进一步增大而单调减小。故相对于无噪声情形，适量的加性噪声强度可以提升系统输出信噪比。

![](images/a3007cf13ea20eb02eb36902dfccb7d9a94c93e1e2af04780efa34d1b4b14e56.jpg)

图6系统参数 $b$ 取不同值时信噪比与加性噪声强度 $P$ 的关系曲线，参数为 $a = 2$ ， $D = 0 . 2$ ， $\lambda = 0 . 3$ $r = 0 . 2$ ， $\varepsilon = 0 . 2$ ， $A = 0 . 1$ ，

$$
\lambda _ { \mathrm { 0 } } = 2
$$

Fig.6 The SNR versus the additive white noise strength $P$ for $a = 2$ ， $D = 0 . 2$ ， $\lambda = 0 . 3$ $r = 0 . 2$ ， $\varepsilon = 0 . 2$ $A = 0 . 1$ ， $\lambda _ { \mathrm { 0 } } = 2$ for different values of the system parameter $^ b$

综上，随着乘性方波信号幅度的增大，信噪比可以取得一个最大值和一个最小值(对于$\lambda { = } 0 . 7 2$ 情形,在 $\scriptstyle A = 0 . 8$ 时出现最大值为2.9， $\scriptstyle A = 0 . 3 5$ 时出现最小值2.5)，而随着其他参数的变化仅出现一个极值，即最大值。对于加性噪声情形，在信噪比与双值噪声幅度的曲线上或者仅有一个极值，即最大值，或者虽然有两个极值出现，但先出现最小值，而后出现最大值。另外，以前的研究表明，较高的加性方波信号幅值可以提升系统信噪比，而本文的研究结果发现，较大的乘性方波信号幅度会抑制系统输出信号，对于 $\lambda { = } 0 . 6 5$ 情形， $\scriptstyle A = 1 . 0$ 时系统输出幅度比 $\scriptstyle A = 0 . 3$ 时的输出幅值下降约 $2 9 \%$ ；反之，较大的乘性双值噪声幅度则可以提升系统输出信噪比，对于 $b { = } 3 . 8$ 情形， $\varepsilon { = } 3 . 5$ 时系统输出幅度为 $\scriptstyle { \varepsilon = 0 . 2 5 }$ 时的输出幅值的2.5倍。

# 3总结

本文研究了乘性方波信号和乘性双值噪声作用下的双稳系统，观察到了两种随机共振现象，即传统的随机共振与广义的随机共振。当信噪比随着噪声强度变化时，包括乘性双值噪声强度、乘性白噪声强度和加性白噪声强度，乘性传统的随机共振现象。广义的随机共振出现在信噪比与系统参数、直流偏置及乘性方波信号幅度的关系曲线上。那么进一步将研究结果推广，研究拟在天文信号处理方面引入本研究分析，例如在不同接收机性能、无线电干扰信号注入情况下，对接收机噪声的影响情况等。

# 参考文献

[1] BENZI R, SUTERA A, VULPIANI A. The mechanism of stochastic resonance [J]. Journal of Physica A: Mathematic and Generation, 1981,14(11): L453-L457.   
[2] MCNAMARA B,WIESENFELD K. Theory of stochastic resonance [J]. .Physical Review A, 1989,39 (2): 4854-4862.   
[3] REAMES D V. The two sources of solar energetic particles[J]. Space Science Reviews, 2013, 175: 53-92.

[4] BOTTKE WF, VOKROUHLICKY D,Walsh K J，et al. In search of the source of asteroid (101955) Bennu: applications of the stochastic YORP model[J]. Icarus ， 2015,247 (6):191-217.

[5] LIU S M,MELIA F，PETROSIAN,V，et al. Stochastic acceleration in the Galactic center HESS source[J]. The Astrophysical Journal, 2006, 647 (2) : 1099-1105.   
[6]无线电通信局．射电天文手册：第三版[M]．日内瓦：【出版者不详】，2013.   
[7] 陈国强,杨开平,曹文达.微波噪声发生器的改进和检测[J].云南天文台台刊,1993(3):29-33. [8] 陈勇,孙正文,袁建平,等.应用于射电天文的低噪声温度测量方法[J].文研究与技术-国家天 文台台刊，2012,9(2):129-136.   
[9]张贤达.现代信号处理：第二版【M】.北京：清华大学出版社，2002.   
[10]任泽龙,刘松,梁亨茂,等．谐振式 MEMS 磁传感器数字锁相放大器设计[J].传感器与微系 统，2019,38 (4): 86-88.   
[11]GUO F, LUO X D, LI S F, et al. Stochastic resonance in a stochastic bistable system with additive noises and square-wave signal [J]. Chinese Physics B,2O10,19 (8):080502.   
[12]GINZBURG S L, PUSTOVOIT M A. Stochastic resonance in two-state model of membrane channel with comparable opening and closing rates [J].Physical Review E,2OO2, 66 (8):021107. [13] GONG M， GUO F. Phenomenon of stochastic resonance in a time-delayed bistable system driven by colored noise and square-wave signal [J]. Chinese Journal of Physics, 2O11,49 (6): 655-663.   
[14]GUO F, ZHOU Y R, ZHANG Y. Stochastic resonance in a monostable system driven by square-wave signal and dichotomous noise[J]. Chinese Physics B,2O10,19 (4): 080504.   
[15]GUO F, HUANG Z Q,FAN Y, et al. Stochastic resonance in a time-delayed mono-stable system with multiplicative and additive noise [J]. Chinese Physics Letter, 2OO9,26 (10):100504. [16] NICOLIS C and NICOLIS G. Stochastic resonance in the presence of slowly varying control parameters[J]. New Journal of Physics, 2005,7 (4): 8-15.

# Stochastic resonance in a bistable system with multiplicative square-wave signal and multiplicative dichotomous noise

Xu Jiang',Guo Feng², Chen Yong³ (1.SichuaIsiuteofecticcouoticoogg4aail:@olf Information Engineering,Southwest University of Science and Technology,Mianyang 621010,China; 3.XinjiangAstronomicalObseratory,atioalstronmicalObservatories,inesecademyofiences,Uumqi8ia)

Abstract:Square-wavesignalanddichotomous noiseare widelyusedinscientificfields,and multiplicativesignalis widelyused in enginering practice.However,litestudyhasbeendoneonthenonlinear influenceof multiplicativesquare-wavesignaland multiplicativedchotomousnoiseoabistablesystem,sointhispaperweinvestigatethstochasticesonancephenomenoninabistable systemdrivenbymultiplicativesquare-wavesignalandmultiplicativedichotomousoiseisinvestigated.Undertheadiabaticodition theoutputsignal-to-noiseratio(SNR)forthesystemisobtained.ItisfoundthattheSNRcanobtainonemaximumvalueandone minimumvalue with increasing theamplitudeof themultiplicativesquare-wavesignaland multiplicativedichotomous noise.Large valuesof theamplitudeof themultiplicativesquare-wavesignalcandepressthesystem SNR,inthecaseofnoisecorrelationrate $\lambda { = } 0 . 6 5$ ,the system output amplitude for square-wave amplitude $_ { \mathrm { A } = 1 . 0 }$ declines almost $2 9 \%$ by comparison with that for $_ { \mathrm { A } = 0 . 3 }$ ,while a more amount of the multiplicative dichotomous willimprove the system output, in the case of system parameter ${ \sf b } { = } 3 . 8$ ，the system output amplitude for multiplicative dichotomous noise intensity $\scriptstyle \varepsilon = 3 . 5$ is 2.5 times that for $\scriptstyle \varepsilon = 0 . 2 5$ . One resonance peak can be observed whenthesystemSNR varies withthe multiplicative whitenoise,withtheaditive white noise,aswell aswith the system parameters.

Key Words: Stochastic resonance; bistable system; multiplicative square-wave signal; multiplicative dichotomous noise