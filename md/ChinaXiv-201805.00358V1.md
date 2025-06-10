# 基于MCM的多径非相关无线信道改进模型研究‘

殷礼胜，任帅，刘冬梅，何怡刚(合肥工业大学 电气与自动化工程学院，合肥 230009)

摘要：为了改善瑞利衰落信道单径自相关统计特性，提出了一种改进的多径非相关无线信道仿真模型。该模型首次在蒙特卡罗法(MCM)的到达角(AOA)中引入多径因素k,改进了模型AOA的取值方法。通过对信道模型参数 AOA、k、低频振荡器个数N以及均方误差（MSE）的仿真分析，结果表明，该模型在相关统计特性方面与参考模型相比具有极好的吻合性；其次，与MCM相比，在实现开销相同的情况下，改进的新模型在最大允许时间间隔内，衰落信道单径自相关函数的MSE约为MCM的四分之一，精度有了明显的提高，能更加准确地描述无线信道。新模型为无线信道仿真器的设计、频率选择性信道的建模等提供了一种新的方法。

关键词：信道模拟；瑞利衰落信道；多径；自相关；到达角 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2017.09.0950

# Improved model based on MCM for simulation of multiple uncorrelated wireless channel model

Yin Lisheng, Ren Shuai, Liu Dongmei, He Yigang (School ofElectricalEngineering&Automation,Hefei UniversityofTechnology,Hefei23ooo9,China)

Abstract: Inorder to improve the statisticalpropertiesofmultipath fading and more accurate descriptionof wireless channel. This paper proposed an improved simulation modelbased on Monte Carlo method (MCM) foruncorrelated multiple Rayleigh fading channels.Basedon theangleofarival (AOA),the multipath element (k)is introduced into thenewsimulationmodel, which improved the methodofevaluating AOA.Through the simulationanalysisof thechannel model parameters AOA,k,the numberoflow frequencyoscilatorandthe meansquareeror(MSE),theresultsshowthataprettgoodagreementstatistical property ofthe new modeland those of the underlying reference model has been observed.Compared with MCM,the new modelhasasignificant improvement intheautocorelationproperties inthesameconditionsandtheMSEisaboutaquarterof the original.The new method is useful for the design of wireless channel simulator,frequency-selective channel.

Key Words: channel simulation; Rayleigh fading channels; multipath; autocorrelated; angle of arrival

# 0 引言

随着多输入多输出(multiple input multiple output,MIMO）、分集技术、宽带无线网络通信系统的发展与应用，无线信道模拟在现代无线通信设备研发与测试的过程中所占的比重越来越大。其中，模拟数字通信的多径衰落信道时，由于真实的无线通信信道复杂多变，能否准确地描述无线信道直接决定着无线通信质量的好坏，因此，生成多个单径自相关统计性能好且各径不相关的衰落信道对无线通信的性能进行研究依然是无线通信信道建模的重点之一[1\~4]。

对于常见的瑞利衰落信道建模，分为滤波法和正弦波叠加法(sum-of-sinusoids,SOS)。 滤波法运算量大且需要产生独立复高斯随机过程，而基于SOS的信道模拟方法能够模拟瑞利、莱斯等多种无线衰落信道，可以根据需要产生特定长度的波形，且具有易于实现和精确有效的优点，在实际仿真模拟中应用更为广泛。基于SOS，Jakes在Clarke提出经典信道参考模型后，提出的简化衰落模型在信道平稳方面以及统计独立性方面存在着不足之处，产生的信号也不是各态历经的，各径信道之间相关性强。

为了提高单径信道的自相关性，减小信道与信道之间的相关性，于是有了文献[5\~12]改进的模型，但是各模型仍有很多不足之处：其中，Pop 等人在文献[5]中引入随机平均分布相位，解决了信道非平稳性问题，但仍不能生成多径非相关信道；Zheng等人文献[6,7]中提出的不确定性模型,大大改善了瑞利衰落信道正交分量间的互相关性，并且Zheng 模型具有很好的统计特性,适用于多径瑞利衰落信道,但是 Zheng 模型的到达角只考虑了同径信道的随机分布特性，并没有包含多径因素；Li等人在文献[8]中合理地设计多普勒频移,实现了多径独立瑞利衰落信道的仿真，但到达角不是随机分布；在文献[9]中MCM模型虽然到达角是随机分布，但是相比之下，同向分量自相关性能差。而文献[10\~12]改进的模型都是在等距法（MED）、等面积法（MEA）或者是精确多普勒扩展法（MEDS）基础上引入多径因素提出的，且模型的自相关，互相关等相关统计特性与参考模型仍然存在着很大的差别。

综上所述，针对多径非相关无线信道的特点，分析了文献中已有的衰落信道模型与各个模型不足之处的基础之上，本文首次尝试在传统MCM模型的AOA中引入多径因素，提出了一种新的AOA模型,改进了MCM的实现方法。本文提出的改进方法在各径的自相关特性上得到了明显提高,而且多径信道之间不相关，能更加准确地描述无线衰落信道。

# 1 瑞利衰落信道参考模型

基于SOS的瑞利衰落信道仿真模型，是通过有限数目的正弦波叠加实现的[13,14]，模型如式(1)和(2)所示。

$$
\widetilde { c } ( t ) = \widetilde { c } _ { 1 } ( t ) + \widetilde { \mathbf { j } } \widetilde { c } _ { 2 } ( t )
$$

$$
\tilde { c } _ { i } ( t ) = \sum _ { n = 1 } ^ { N } c _ { i , n } \cos ( 2 \pi f _ { i , n } t + \theta _ { i , n } )
$$

式(1)中 $\tilde { \dot { c } } _ { 1 } ( t )$ ， $\tilde { \dot { c } } _ { 2 } ( t )$ 分别为同向分量和正交分量；式(2)中 $i = 1 , 2$ ， $N$ 为模拟瑞利信道需要的低频振荡器个数，参数 $f _ { i , n }$ 、$\theta _ { i , n }$ 分别为各支路离散多普勒频率和多普勒相位，参数 $c _ { i , n }$ 为信道多普勒系数，如式(3)和式(4)所示。

$$
\begin{array} { c } { { c _ { i , n } = \sqrt { 2 { \sigma } _ { 0 } ^ { 2 } / N _ { i } } } } \\ { { { } } } \\ { { f _ { i , n } = f _ { d } \sin ( a _ { i , n } ) } } \end{array}
$$

式(4)中 $f _ { d }$ 为最大多普勒频移； $a _ { i , n }$ 为各支路信号的AOA。该模型对应的二阶统计参量表示为

$$
\left\{ \begin{array} { l } { R _ { c _ { 1 } c _ { 1 } } ( \tau ) = R _ { c _ { 2 } c _ { 2 } } ( t ) = \sigma ^ { 2 } \mathbf { J } _ { 0 } \left( w _ { d } \tau \right) } \\ { R _ { c _ { 1 } c _ { 2 } } ( \tau ) = R _ { c _ { 2 } c _ { 1 } } ( t ) = 0 } \\ { R _ { c c } ( \tau ) = 2 \sigma ^ { 2 } \mathbf { J } _ { 0 } \left( w _ { d } \tau \right) } \end{array} \right.
$$

式(5)中 $\mathrm { J } _ { 0 } ( \cdot )$ 表示零阶第一类Bessel 函数； ${ \mathfrak { o } } ^ { 2 }$ 为瑞利衰落的方差； $R _ { c _ { i } c _ { i } } ( \tau )$ 表示单径信道的同向分量自相关函数； $R _ { c _ { 1 } c _ { 2 } } ( \tau )$ （204号表示单径信道的正交分量互相关函数； $R _ { c c } ( \tau )$ 表示单径信道的自相关函数。

# 2 改进的MCM模型

# 2.1改进MCM模型的AOA表示

根据瑞利衰落信道的参考模型表示方法，在AOA中引入多径因素后，非相关多径瑞利衰落信道模型表示为式(6)和 (7)。

$$
C _ { k } \left( t \right) = C _ { 1 , k } \left( t \right) + \mathbf { j } C _ { 2 , k } \left( t \right)
$$

$$
C _ { i , k } \left( t \right) = \sum _ { n = 1 } ^ { N _ { i } } c _ { i , n , k } \cos ( 2 \pi f _ { i , n , k } t + \theta _ { i , n , k } )
$$

式(6)中 $C _ { 1 , k } ( t )$ ， $C _ { 2 , k } ( t )$ 分别表示第 $k$ 径的同向分量和正交分量， $k = 1 , 2 , \cdots , M$ ， $M$ 为不相关波形的个数；式(7)中 $c _ { i , n , k }$ 、$f _ { i , n , k }$ 和 $\theta _ { i , n , k }$ 分别表示第 $k$ 径各支路的多普勒系数、多普勒频率和随机相位。 $c _ { i , n , k } = \sqrt { 2 \sigma _ { 0 } ^ { 2 } / N _ { i } }$ ， $N _ { 1 } = N _ { 2 }$ ， $n = 1 , 2 , \cdots , N _ { i } ( i = 1 , 2 )$ ，$f _ { i , n , k } = f _ { d } \sin ( a _ { i , n , k } )$ ， $\theta _ { i , n , k } \in U ( 0 , 2 \pi ]$ ， $k$ 表示第 $k$ 径。

由传播理论可知，接收信号是由所有散射波的矢量叠加而成，因此各散射波的AOA值会直接影响信道模型的统计特性。文献[13]根据 $c _ { i , n }$ 、 $f _ { i , n }$ 、 $\theta _ { i , n }$ 是否为随机变量将瑞利衰落仿真模型分为四大类，且已证明类型IⅢI（ $c _ { i , n }$ 是确定变量， $f _ { i , n }$ 和 $\theta _ { i , n }$ 是随机变量）是高效的瑞利信道仿真模型。类型IⅢI中有两种典型的仿真模型：MCM模型和Zheng模型。MCM模型的统计特性与参考模型的统计特性偏差较大；Zheng 模型相对而言统计特性与参考模型更接近，但不具备各态历经性。且各模型都不具有多径因素，具体AOA如式(8)和(9）所示。

MCM模型:

$$
a _ { i , n } = \frac { \pi } { 2 } u _ { n }
$$

Zheng 模型: $a _ { i , n } = \frac { 2 \pi n - \pi + \phi } { 4 N }$

式 (8)(9）中 $n = 1 , 2 , \cdots , N _ { i } ( i = 1 , 2 )$ ； $u _ { n } \in U ( 0 , 1 ]$ ；$\phi \in { \cal U } ( - \pi , \pi ]$ 。

由式(9)可知， $\phi$ 取不同值时，Zheng 模型的所有AOA取值在 $( ^ { \pi \left( n - 1 \right) } / _ { 2 N } , \pi n _ { \left/ 2 N \right. } ]$ 内随机分布，当 $n = N$ 时，AOA 有最大值$\pi / 2$ ，如图(1)所示。 $x$ 轴取值 $\left[ 1 , N \right]$ ，且为整数, $y$ 轴取值 $( 0 , \% ]$

![](images/4a77d8438ed5211f2286d94acfebdf77e3e1b5976a1332351a346b149c68aad0.jpg)  
图1AOA随机取值区域

分析比较上述式(8)与(9)的AOA取值范围与特点，在MCM模型的AOA中引入多径因素 $k$ ，重新对AOA取值，使之：

a)无论k取何值，AOA 在((n-1)/N $( ^ { \pi \left( n - 1 \right) } / _ { 2 N } , \pi n \Big / _ { 2 N } ]$ 范围内随机分布，进而改善MCM信道模型的统计特性;

b)当 $n = 1$ 时，AOA大于0， $n = N$ 时，AOA小于等于 $\pi / 2$ ：c)改变 $\mathbf { k }$ 的值可以快速生成所需的不相关瑞利波形。

新模型的AOA如式(10)所示。可以看出各模型的根本区别在于AOA的取值方法不同。

新模型：

$$
\begin{array} { l } { \displaystyle { a _ { i , n , k } = \frac { \pi } { 2 } u _ { n } + \frac { \pi ( n - 1 ) } { 2 ( N - 1 ) } } } \\ { \displaystyle { \phantom { \frac { 1 } { 2 } } - \biggl [ ( n - M ) \bullet \frac { \pi k } { 4 N M } ( 1 - \frac { 5 } { 6 M } ) + \frac { 3 } { 2 } \biggr ] u _ { n } } } \end{array}
$$

式(10)中 $a _ { i , n , k } \in U \bigl [ 0 , \pi / 2 \bigr ) \ i = 1 , 2$ ： $u _ { n } \in U ( 0 , 1 ]$ ; $k = 1 , 2 , \cdots , M$ ：$M$ 为生成的不相关波形的个数。

# 2.2改进的MCM模型分析

根据参考模型，该模型的第 $k$ 径瑞利衰落波形 $C _ { i , k } ( t )$ 的自相关函数 ACF 如式(11)所示[7]。

$$
\begin{array} { r l } { \tilde { \Gamma } _ { { \bf r } , \mathrm { c } , \mathrm { s } , \mathrm { t } , \mathrm { s } } } & { = \displaystyle \operatorname* { l i m } _ { T , \mathrm { r } \to 2 } \frac { 1 } { 2 T } \int _ { - \mathrm { r } } ^ { T } { \bf C } _ { \mathrm { s } } \langle t \rangle { \bf C } _ { \mathrm { s } , \mathrm { t } } ( { \bf t } + { \boldsymbol \tau } ) \mathrm { d } { \bf t } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { = \displaystyle { \bf E } [ c _ { \mathrm { s } , \mathrm { a } } \sum _ { \mathrm { s } = 1 } ^ { N } ( 2 \pi { \bf f } _ { i _ { \mathrm { m a x } } } t + { \bf f } _ { i _ { \mathrm { m a x } } } ) ] } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \end{array}
$$

式(11)中 $i = 1 , 2$ K $k = 1 , 2 , \cdots , M$ ； $\tau$ 为延迟时间； $M$ 为生成的不相关波形的个数。

同理，瑞利衰落波形 $C _ { i , k } ( t )$ 第 $k$ 径的互相关函数CCF如式(12)所示[9] 。

$$
\begin{array} { l } { \displaystyle \tilde { \mathbf { r } } _ { c _ { i , k } \mathbf { c } _ { j , l } } = } \\ { \displaystyle \operatorname* { l i m } _ { T \to \infty } \frac { 1 } { 2 T } \int _ { - T } ^ { T } \mathbf { C } _ { i , k } \left( t \right) \mathbf { C } _ { j , l } ( t + \tau ) \mathrm { d } t } \\ { = \mathrm { E } [ \mathbf { C } _ { i , k } \left( t \right) \mathbf { C } _ { j , l } ( t + \tau ) ] } \\ { = 0 \qquad ( f _ { i , n , k } \neq f _ { j , m , l } ) } \end{array}
$$

即当 $i \neq j ( i , j = 1 , 2 )$ 和 $k \neq l ( k , l = 1 , 2 \cdots , \mathrm { M } )$ ， $C _ { 1 , k } ( t )$ ，$C _ { 2 , l } ( t )$ 的离散多普勒频率无重值， $C _ { i , k } ( t ) ~ , ~ C _ { j , l } ( t )$ 的互相关函数CCF值为零。

为了满足式(12)，模型各径信道间的CCF 期望值为零， AOA应满足

$$
\begin{array} { r l } {  { \cos ( a _ { n , k } ) \neq \pm \sin ( a _ { n , m } ) } } \\ & { \cos ( a _ { n , k } ) \neq \pm \cos ( a _ { l , m } ) , \ l \neq n \not \Xi \backslash k \neq m } \\ & { \sin ( a _ { n , k } ) \neq \pm \sin ( a _ { l , m } ) , l \neq n \not \Xi \backslash k \neq m } \end{array}
$$

式 (13)中 $k , m = 1 , 2 , \cdots , M$ ， $M$ 为不相关波形的个数，$n , l = 1 , 2 , \cdots , N$ ， $N$ 表示需要的低频振荡器个数。

改进模型的AOA满足上面的约束条件，将上式(10)代入到式(11)中，改进模型的自相关函数ACF见式(14)。

$$
\begin{array} { r l } & { \widetilde \Gamma _ { c _ { i , k } c _ { i , k } } = } \\ & { \frac { \underline { { \sigma } } ^ { 2 } } { N } \displaystyle \sum _ { n = 1 } ^ { N } \cos \left\{ 2 \pi f _ { d } \sin \left[ \frac { \pi } { 2 } u _ { n } + \frac { \pi ( n - 1 ) } { 2 ( N - 1 ) } \right. \right. } \\ & { \left. \left. - \left[ ( n - M ) \bullet \frac { \pi k } { 4 N M } ( 1 - \frac { 5 } { 6 M } ) + \frac { 3 } { 2 } \right] u _ { n } \right) ^ { \bullet \tau } \right\} } \end{array}
$$

# 3 仿真分析

# 3.1N值影响仿真分析

以改进的MCM模型、MCM模型与参考模型的单径信道同向分量自相关函数ACF的MSE作为判断标准，分析 $N$ 的不同取值对模型精度的影响，即

$$
\mathit { M S E } = \operatorname { E } \left[ \left| \widetilde { \mathbf { r } } _ { c _ { i , k } c _ { i , k } } - R _ { c _ { i } c _ { i } } \left( \tau \right) \right| ^ { 2 } \right]
$$

在 $N$ 取不同值时，改进MCM与MCM的 $\tilde { \mathbf { r } } _ { c _ { i } c _ { i } }$ MSE值如图2所示。从图中可以很直观地看出，与MCM相比，无论 $N$ 取何值（如 $N = 1 1$ 时，MCM的值为0.04539，而改进MCM的值只有0.01031)，改进MCM得到的结果都明显要好，而且新模型相较于原先的模型，相关性质收敛快。再一次证明了新模型能更加准确地描述无线衰落信道。

![](images/bc756a7b12550fe13fbc5e48720c3bd2cdd44235c094f3fa07949d2b7efcbefb.jpg)  
图2不同 $N$ 取值的均方误差

对于不同的 $N$ 值，改进MCM的单径自相关函数的MSE值如表1所示。

表1不同 $N$ 值的MSE  

<html><body><table><tr><td>N</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td></tr><tr><td>MSE</td><td>0.02436</td><td>0.02255</td><td>0.01526</td><td>0.01031</td><td>0.0090</td></tr></table></body></html>

随着 $N$ 值的增大，自相关函数的MSE逐渐减小，综合考虑精度、 $N$ 值曲线的斜率变化和实现成本，本文选取 $N = 1 1$ 作为仿真条件。

# 3.2AOA值仿真分析

由式(13)知，当AOA值 $a _ { n , k } \in U \left[ 0 , \pi / 2 \right)$ 时，满足

$$
\begin{array} { l l } { { a _ { n , k } + a _ { l , m } \neq \pi / 2 } } \\ { { a _ { n , k } \neq a _ { l , m } } } & { { l \neq n \land \nmid k \neq m } } \end{array}
$$

式(16)中 $k , m = 1 , 2 , \cdots , M$ ， $n , l = 1 , 2 , \cdots , N$ 。

当 $N = 1 1$ ， $M = 2$ 时，根据式(10)随机生成两径信道的AOA，分布及正余弦函数值如图3所示。图中横坐标表示AOA值 $\boldsymbol { a } _ { n , k }$ 的相位取值。可以看出各组值均不相等且满足式(16)。

![](images/7b35db870dd552a2e5676b583580e68e5c8ad8294dee6209e3f6b49a810d4817.jpg)  
图3两组AOA取值及正余弦值

# 3.3 自相关性能仿真分析

为了直观上了解改进模型的性能，且有可比性，选取$N = 1 1$ ， $\sigma ^ { 2 } = 1$ ， $f _ { d } = 1 0 0 \ : \mathrm { H z }$ ， $M = 5$ 。取 $M$ 中的第1径与MCM和参考模型进行仿真对比，可以发现改进的新模型的自相关函数ACF与参考模型的ACF具有极好的吻合性，如图4所示，图中以 $f _ { d } \tau$ 作为横坐标的标准量度， $\boldsymbol { \tau }$ 的最大延时时间取$N / ( 2 f _ { d } )$ □

![](images/87f2ec977e4fe6e820037026d86669d97100d9bd69035145ae2814c5fba6e2bb.jpg)  
图4各模型自相关函数

改进模型与MCM和参考模型的MSE如图5所示。从图中可以看出，在上面的实现条件下，在最大允许时间间隔内改进模型的误差仅为MCM的四分之一，性能得到了极大的提升。

![](images/b452d61afeba44a786bcde9b974e0025092a0491a32ae08161afd0ed99a0d9d1.jpg)  
图5单径信道ACF均方误差

# 3.4各 $\boldsymbol { \mathsf { k } }$ 值的MSE

在 AOA 中引入 $k$ 值会影响各径信道的自相关统计特性，因此，为了更加直观、全面准确地了解改进模型的统计特性，仿真给出了当 $M = 5$ 时模型每一径的自相关MSE的值，如图6所示。

![](images/6420e8b86a79259cee44b37c4cfad5e5058439e2ab916e2d16bcfa97038cd16f.jpg)  
图6各径信道ACF均方误差

改进模型每一径的ACF的精度都有着巨大的提升。图6中$x$ 轴表示 $k = 1 , 2 , \cdots , M$ 的各径， $y$ 轴采用 $f _ { d } \tau$ 作为标准量度，z轴表示各径自相关ACF的MSE。

表2列举了不同 $k$ 值对应的改进MCM的MSE值和MCM的 MSE值。分析表2中的数据可以看出，改进模型单径信道的每一径的自相关MSE的精度均有极大的提到，约为MCM的四分之一。

表2不同 $k$ 值的MSE  

<html><body><table><tr><td>径</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>MCM</td><td>0.04539</td><td>0.04682</td><td>0.04835</td><td>0.04787</td><td>0.04599</td></tr><tr><td>改进MCM</td><td>0.01031</td><td>0.01062</td><td>0.01192</td><td>0.01224</td><td>0.01213</td></tr></table></body></html>

# 3.5非相关信道时域波形

仿真给出了 $M = 5$ 实验中信道的第1条、第3条和第5条衰落信道的时域包络波形，如图7所示。从直观上就可以看出，该三条信道的包络不具有相关性，且有较好的非相关瑞利衰落信道的特点。

![](images/e6143e5f6b550c60e8cb54580dc30525bf95f9c5b925c39c960c603c72c80a48.jpg)  
图7径1、3、5信道时域波形

# 3.6 实验仿真

只需要改变 $k$ 的值，就可以快速生成多个单径自相关统计特性好，且各路径不相关的瑞利衰落。采用本文提出的信道生成方法，直接用于MIMO无线信道的仿真实现。仿真主要参数设置如表3所示

表3参数配置  

<html><body><table><tr><td>收发天线</td><td>调制方式</td><td>编码方式</td><td>检测算法</td></tr><tr><td>1x1</td><td></td><td></td><td></td></tr><tr><td>2x2</td><td>BPSK</td><td>STBC</td><td>MMSE</td></tr></table></body></html>

实验仿真结果如图8所示。图中给出了改进MCM模型和MCM模型在不同天线数目下MIMO系统的误码率。从图中可以看出，在相同的信噪比下，MIMO天线数目从 $1 \times 1$ 增加到$2 \times 2$ 时，系统的误码率依次下降，如实际相符；在BER为0.1处，天线数目为 $1 \times 1$ 时，改进MCM模型相对于MCM模型有2dB的增益；天线数目为 $2 \times 2$ 时，改进MCM模型相对于MCM模型有2.1dB的增益。在改进信道模型下，系统误码率性能得到了优化。图中横坐标表示信噪比，纵坐标表示误码率。

![](images/d342fa626e98ed9154bd7acd8a8e4435d2a38e99ce4e5072d73b63ca4c8d8c4f.jpg)  
图8各模型不同天线数目MIMO系统误码率

# 4 结束语

本文提出了一种基于SOS的多径瑞利衰落信道的改进模型，在MCM的多普勒频率中引入多径因素之后，改进了模型的AOA取值方法。在实现开销相同的情况下，与MCM相比，改进模型各径的自相关函数的精度有了极大的提高，且优于其他的改进模型。改进的模型可以快速生成多个不相关瑞利衰落信道，可直接用于MIMO无线信道和 WSSUS等信道的仿真实现，拓展了研究无线通信系统性能时认识、利用信道的方法。在多普勒频率中引入多径因素提高各信道自相关性能的同时，如何进一步增加生成不相关波形的个数，并在此信道下研究通信系统的性能，是下一步研究的方向。

# 参考文献：

[1]LiJ,Wang C.Research on multiple uncorrelated Rayleigh channels model and performance analysis [C]//Proc of IEEE International Conference on Ubiquitous Wireless Broadband.2016:1-3.   
[2] 李静威，全厚德，崔佩璋．一种改进的非相关多径瑞利衰落信道模型 [J].电讯技术,2013,53(12):1610-1613.   
[3]周生奎，戴秀超，朱秋明，等．无线衰落信道模拟方法及仪器研制[J]. 电子测量与仪器学报,2015,29(7):988-994.   
[4]王艳丽，张鹏，张佳．矿井时变多径信道无线通信技术仿真研究[J]. 计算机仿真,2014,31(7):179-182.   
[5]Pop M F,Beaulieu N C.Limitations of sum-of-sinusoids fading channel simulators [J]. IEEE Trans on Communications,2001,49 (4): 699-708.   
[6] Zheng Y R, Xiao C. Improved models for the generation of multiple uncorrelated Rayleigh fading waveforms [J]. IEEE Communications Letters, 2002,6 (6): 256-258.   
[7]Zheng YR, Xiao C. Simulation models with correct statistical properties for Rayleigh fading channels [J].IEEE Trans on Communications,2oo3,51(6): 920-928.   
[8]LI Y,HUANG X. The simulation of independent Rayleigh faders [J]. IEEE Trans on Communications,2002,50 (9): 1503-1514.   
[9]Patel C S,Stuber GL,Pratt TG.Comparative analysis of statistical models for the simulation of Rayleigh faded cellular channels [J]. IEEE Trans on Communications,2005,53 (6):1017-1026.   
[10] Hu K, Cui C.An improved method for generation of multiple uncorrelated rayleigh fading waveforms [C]/ Proc of IEEE International Conference on Communications and Mobile Computing. [S.1.] : IEEE Computer Society, 2010: 72-76.   
[11] Zhang Y, Shen X,Wang H,et al.An improved model for the simulation of multiple uncorrelated Rayleigh fading waveforms [C]// Proc of IEEE International Conference on Signal Processing， Communicationsand Computing. 2011: 1-4.   
[12] Wang C X,Patzold M, Yuan D.Accurate and efficient simulation of multiple uncorrelated Rayleigh fading waveforms [J].Wireless Communications IEEE Transactions on,2007,6(3): 833-839.   
[13]罗志年，张文军，管云峰．不相关Rayleigh 衰落信道仿真模型[J]．系 统仿真学报,2009,21(13):3872-3875.   
[14] Clarke RH.A statistical theory of mobile-radio reception [J].Journal of Bell System Technical,1968,47 (6): 957-1000.