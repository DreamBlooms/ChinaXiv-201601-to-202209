# BOC及其衍生信号通用无模糊捕获分析

袁帅，张天骐，刘董华，王胜(重庆邮电大学 信号与信息处理重庆市重点实验室，重庆 400065)

摘要：针对 BOC(binary offset carrer)及其衍生信号通用无模糊捕获方法匮乏的问题，提出了一种基于伪相关函数(pseudo correlation function，PCF)的无模糊捕获改进方法。首先，根据形状码向量的概念构建了BOC 信号的互相关函数统一表达式，并提出了两组新的形状码向量；然后，通过接收信号与形状码向量对应的参考信号做互相关合成得到一个单峰；最后，通过单峰与自相关函数合成得到通用无模糊捕获方法。仿真实验表明，在同一条件下，新提出的捕获方法主峰能量相对于副载波相位消除法提高了 $23 \%$ ，并且能够适用于所有类型和所有调制阶数的BOC信号，能够完全消除同步过程中自相关函数的模糊性。

关键词：二进制偏移载波；无模糊捕获；伪相关函数；副峰消除；形状码向量 中图分类号：TN914 doi:10.3969/j.issn.1001-3695.2018.01.0014

# Analysis of general unambiguous acquisition for BOC and its derivative signals

Yuan Shuai, Zhang Tianqi, Liu Donghua, Wang Sheng (Chongqing Key Laboratoryof Signal&Information Processing,Chongqing UniversityofPosts&Telecommunications, Chongqing 400065,China)

Abstract:Forthe problemof generalunambiguousacquisition forBOC(binaryofsetcarier)andits derivative signals is stil scarceofanalysis,thepaper proposed animproved unambiguous acquisition methodbasedonPCF (pseudo correlationfunction). Firstly,thepaper proposedtheconceptofstep-shapebitsvectortoobtainanifdexpressionofcross-corelationfunctionand designed twonew step-shape vectors,tensynthesized thereceivedsignalandreferenced signalofcorresponding to shapecode vectortoobtainasinglepeak.Finaly,thepaperobtaineda generalizedunambiguous acqusitionmethodbycombinedthe single peak and autocorrelation functions.Theexperimentalresults showthat,underthe sameconditions,itspeak energyofthe main peak increases by $23 \%$ than sub carrier phase cancellation method, the new propose method can deal with all kinds of BOC signals includingcomplex ones with diferent types orordersand completely eliminatetheambiguityof the autocorelation function in the synchronization process.

Key words:binaryofsetcarrier;unambiguousacquisition;pseudo-correlation functions;side-peakcancelation;step-shape vectors

# 0 引言

随着全球导航卫星系统(global navigation satellite system,GNSS)的快速发展，在有限的频带内如何实现资源共享和更精确的捕获信号成为GNSS的研究热点。针对上述问题，一种二进制偏移载波(binaryoffsetcarrier，BOC)调制在文献[1]中被提了出来。这种调制方式实际上是通过一个频率较快的二进制副载波来调制扩频信号。在导航卫星系统中，BOC调制能够通过多种方式实现，比如经常使用的正弦调制BOC(sine-BOC)，余弦调制 BOC(cosine-BOC)，时分数据调制 BOC(TDDM-BOC),多元BOC[2](MBOC)，交替二进制偏移载波调制(AItBOC)。这些信号都能够实现频谱共用和资源共享，并且拥有更好的抗多径和抗噪声性能。但是，这也带来了新的问题，主要是模糊捕获与跟踪问题。

为了解决BOC调制信号无模糊捕获问题，近年来许多无模糊捕获方法被提了出来。文献[3]提出的BPSK-Like方法是将 BOC信号看成两个BPSK信号的叠加，本地产生等价的载波同时剥离主载波和副载波，积分后得到一个类似于BPSK调制信号的单峰。文献[4]提出的Bump-Jumping(BJ)方法新增了超超前和超滞后相关器来辅助接收机对主峰的捕获，该方法只适用于低阶的BOC信号。文献[5]提出的Side-PeaksCancellation(SC)方法是一类方法的统称。目前，SC类方法包括三种基本形式：自相关函数副峰消除技术(autocorrelation side-peakcancellation technique，ASPECT)[6]，副载波相位消除方法(sub carrier phase cancellation，SCPC)[7]和伪相关函数法(pseudo-correlation function，PCF)[8]。ASPECT方法的主要思想是将本地 BOC信号和伪码序列分别与接收信号做相关处理，然后将得到的互相关函数通过平方相减来消除副峰对主峰的影响，但是该方法只适用于 $\mathsf { B O C } ( \mathtt { n } , \mathtt { n } )$ 信号。SCPC方法的主要思想是将接收到的信号分别与两路相互正交的参考信号做相关处理，然后将得到的互相关函数通过平方相加来消除副峰的影响，此方法能够适用于各种BOC调制信号，但是BOC信号的窄主峰特性却遭到了破坏。PCF方法的主要思想是通过引入两个特别设计的本地码来生成一个主峰宽度与 BOC 信号自相关函数主峰宽度相同的单峰相关函数，因此保留了BOC 信号窄主峰的特性。文献[9]提出了只适用于偶数阶sine-BOC信号的方法;文献[10]提出了同时适用于奇数和偶数阶的 sine-BOC 信号的方法;文献[11]提出了适用于cosine-BOC信号的方法;文献[12]提出了一种同时适用于偶数阶sine-BOC和cosine-BOC的PCF改进算法;文献[13,14]分别提出了适用于衍生信号CBOC和AItBOC的PCF 跟踪算法;文献[15]提出了通用的无模糊跟踪方法;文献[16]详细分析了各类BOC信号的无模糊跟踪，但该方法得到的主峰值太低，不适合 BOC 信号的捕获;文献[17]提出了一种适用于偶数阶和奇数阶的 sine-BOC信号的方法，此方法提高了合成相关函数的主峰高度，增大了主峰的斜率。

为了能够实现BOC及其衍生信号的通用无模糊捕获。本文在文献[16,17]的基础上提出了两组新的形状码向量。在伪相关函数的基础上，提出了一种新的相关函数结合方法。仿真结果验证了新的结合方法能够完全消除副峰，大大提高主峰高度和减小主峰宽度。

# 1 BOC信号的通用分析模型

# 1.1 BOC调制

BOC调制信号能够表示为一个扩频信号与方波副载波的卷积，它的表达式为

$$
\mathbf { \boldsymbol { s } } \left( t \right) = \mathbf { \boldsymbol { x } } \big ( t \big ) \otimes \mathbf { \boldsymbol { s } } _ { s c } \big ( t \big )
$$

其中： $\otimes$ 为卷积符号； $s _ { s c } ( t )$ 为 BOC 调制信号的副载波； $x ( t )$ 为被调制的基带扩频信号，可以表示为

$$
x \big ( t \big ) = \sum _ { k = - \infty } ^ { \infty } C _ { k } p _ { T _ { c } } \big ( t - k T _ { c } \big )
$$

其中： $\left\{ C _ { k } \right\}$ 为扩频码序列； $P _ { T _ { c } } \left( t \right)$ 是幅度值为1的方波，其广义表达式表示为

$$
p _ { T } \left( t \right) = \left\{ \begin{array} { l l } { 1 } & { 0 \leq t < T } \\ { 0 } & { o t h e r s } \end{array} \right.
$$

1.2sine-BOC、cosine-BOC、MBOC 和 AItBOC 调制信号

a) sine-BOC和cosine-BOC 调制信号的方波副载波可以表示为

$$
\left\{ \begin{array} { l l } { S _ { \mathrm { s i n B O C } } \left( t \right) = \mathrm { s i g n } \left( \mathrm { s i n } { \left( 2 \pi f _ { s } t \right) } \right) } \\ { \qquad } & { 0 \leq t < T _ { c } } \\ { S _ { \mathrm { c o s B O C } } \left( t \right) = \mathrm { s i g n } \left( \mathrm { c o s } { \left( 2 \pi f _ { s } t \right) } \right) } \end{array} \right.
$$

其中： $\mathrm { s i g n } [ \cdot ]$ 代表符号函数， $f _ { s }$ 代表子载波的频率。sine-BOC/cosine-BOC 统称为 $\mathsf { B O C } ( f _ { s } , f _ { c } )$ ，其中 $f _ { s } = m { \times } 1 . 0 2 3 \mathrm { M H z }$ $f _ { c } = n { \times } 1 . 0 2 3 \mathrm { M H z }$ ，简记为BOC $( m , n )$ ， $N = 2 m / n$ 为调制阶数。

b)MBOC 调制方式具有复合BOC(compositeBOC，CBOC)和时分复用BOC(time multiplexedBOC，TMBOC)两种实现方式[2]。本文以CBOC(6,1,1/11)为例进行讨论，此调制方式是 sine-BOC(1,1)信号和 sine-BOC(6,1)信号按一定的比例合成的。

$$
s _ { \mathrm { c B O C } ( 6 , 1 , 1 / 1 1 ) } ( t ) = \sqrt { 1 / 1 1 } s _ { \mathrm { s i n B O C } ( 6 , 1 ) } ( t ) + \sqrt { 1 0 / 1 1 } s _ { \mathrm { s i n B O C } ( 1 , 1 ) } ( t )
$$

c)AltBOC 调制信号是一个复信号，它包括实部和虚部两个部分。本文以AltBOC(15,10)为例进行讨论。

$$
s _ { \mathrm { A l t B O C } ( 1 5 , 1 0 ) } \left( t \right) = s ^ { \mathrm { ( r ) } } \left( t \right) + j s ^ { \mathrm { ( i ) } } \left( t \right)
$$

其中：上标 $r \setminus i$ 分别表示复信号中的实部和虚部；实部信号为sine-BOC(15,10)，虚部信号为 cosine-BOC(15,10)。

利用冲击函数的特性 $s ( t - \tau ) = s ( t ) \otimes \delta ( t - \tau )$ 来建立统一的分析模型。式(1)可以重新表示为

$$
s \left( t \right) = x \left( t \right) \otimes p _ { T _ { s } } \left( t \right) \otimes \sum _ { m = 0 } ^ { N - 1 } d _ { m } \delta \left( t - m T _ { s } \right)
$$

其中： $d _ { m } \in \{ - 1 , 1 \} { \bigl ( } m = 0 , 1 , 2 , \cdots , N - 1 { \bigr ) }$ 代表的是形状码,$d = \left[ d _ { \mathrm { o } } \ d _ { \mathrm { 1 } } \ d _ { \mathrm { 2 } } \cdots \ d _ { N - 1 } \right] _ { N \times 1 }$ 为形状码向量； $N = T _ { c } / T _ { s }$ 表示为形状码个数，其中， $T _ { c }$ 为一个码片的长度， $T _ { s }$ 为每个形状码的持续时间。下面介绍不同BOC信号的形状码向量取值。

（a）当调制阶数 $N$ 为偶数时。sine-BOC对应的形状码向量为 $d = \left[ 1 - 1 \ \cdots \ 1 \ - 1 \right] _ { N \times 1 }$ ；cosine-BOC 对应的形状码向量为$d = \left[ 1 - 1 - 1 1 \cdots 1 \right] _ { 2 N \times 1 } \circ$

（b）当调制阶数 $N$ 为奇数时。sine-BOC对应的形状码向量为 $d = \left[ 1 - 1 \cdots 1 \right] _ { N \times 1 }$ ；cosine-BOC 对应的形状码向量为$d = \left[ 1 - 1 - 1 \ 1 \cdots \ - 1 \right] _ { 2 N \times 1 } \circ$ （204

(c）调制信号 sine-BOC(6,1)和调制信号 cosine-BOC(1,1)的形状码向量可以分别表示为 $\begin{array} { r } { d _ { \mathrm { { B O C } ( 6 , 1 ) } } = \left[ 1 , - 1 , \cdots , 1 , - 1 \right] _ { 1 2 \times 1 } } \end{array}$ 和$\begin{array} { r } { d _ { \mathrm { { B O C } ( 1 , 1 ) } } = \left[ \underbrace { 1 \cdots 1 \underbrace { - 1 \cdots - 1 } _ { 6 } } _ { 6 } \right] _ { 1 2 \times 1 } } \end{array}$ 。因此CBOC(6,1,1/11)对应的形状码向量为

$$
d _ { \mathrm { C B O C } ( 6 , 1 , 1 / 1 1 ) } = \sqrt { 1 / 1 1 } d _ { \mathrm { B O C } ( 6 , 1 ) } + \sqrt { 1 0 / 1 1 } d _ { \mathrm { B O C } ( 1 , 1 ) }
$$

通过上面的分析可以知道，可以用形状码向量来表示各种BOC 信号。但是形状码向量的取值必须为 $\{ + 1 , - 1 \}$ ，大大的限制了GNSS信号性能提升空间。为了解决这种限制，允许形状码向量任意取值，则可以设计出任意的阶梯形信号。

# 2 BOC通用无模糊捕获方法设计

# 2.1 互相关函数的推导

若接收信号 $s ( t )$ 和参考信号 $s ^ { \prime } ( t )$ 是两个扩频码速率为 $f _ { c }$ ，调制阶数为 $N$ 的 BOC信号，对应的形状码向量取值分别为$\pmb { d } = \left[ d _ { 0 } , d _ { 1 } , \cdots , d _ { N - 1 } \right] _ { N \times 1 }$ 和 ${ \pmb d } ^ { \prime } = \left[ d _ { 0 } ^ { \prime } , d _ { 1 } ^ { \prime } , \cdots , d _ { N - 1 } ^ { \prime } \right] _ { N \times 1 }$ ，则互相关函数$R _ { s s ^ { \prime } } ( \tau )$ 的定义为

$$
R _ { s s ^ { \prime } } ( \tau ) = \int _ { - \infty } ^ { \infty } s ( t ) s ^ { \prime } \big ( t - \tau \big ) d t
$$

$$
\left\{ \begin{array} { l } { { \displaystyle s \left( t \right) = x ( t ) \otimes p _ { T _ { s } } \left( t \right) \otimes \sum _ { m = 0 } ^ { N - 1 } d _ { m } \delta \left( t - m T _ { s } \right) } } \\ { { \displaystyle s ^ { \prime } \left( t - \tau \right) = x ^ { \prime } \left( t - \tau \right) \otimes \left[ p _ { T _ { s } } \left( T - \tau \right) \sum _ { m = 0 } ^ { N - 1 } d _ { m } ^ { \prime } \delta \left( t - \tau - m T _ { s } \right) \right] } ^ { \displaystyle 0 } } \end{array} \right.
$$

将式(10)代入式(9)可得若 $x ( t )$ 和 $x ^ { \prime } ( t )$ 是两个不同的扩频码序列，则

$$
\boldsymbol { R } _ { s s ^ { \prime } } ( \tau ) = 0
$$

若 $x ( t )$ 和 $x ^ { \prime } ( t )$ 是两个相同的扩频码序列，则

$$
R _ { s s ^ { \prime } } \bigl ( \tau \bigr ) = \frac { 1 } { N } \sum _ { m = 0 } ^ { N - 1 } \sum _ { m _ { 1 } = 0 } ^ { N - 1 } d _ { m } d _ { m } ^ { \prime } \Lambda _ { T _ { s } } \bigl [ \tau - \bigl ( m - m _ { 1 } \bigr ) T _ { s } \bigr ]
$$

其中： $\Lambda _ { T _ { s } } ( \tau )$ 是中心在零点，底部宽度为 $2 T _ { s }$ 的三角波形。

由式(12)可知，互相关函数是由多个三角峰函数$\Lambda _ { T _ { s } } \left( \tau - m ^ { \prime } T _ { s } \right)$ 相加而得到，互相关函数在 $m ^ { \prime } T _ { s }$ 处的值 $r _ { m ^ { \prime } }$ 定义为

$$
r _ { m ^ { \prime } } = \left\{ \begin{array} { l l } { { \displaystyle \frac { 1 } { N } \sum _ { i = 0 } ^ { N - 1 - m ^ { \prime } } d _ { i } d _ { i + m ^ { \prime } } ^ { \prime } } } & { { 0 \leq m ^ { \prime } < N - 1 } } \\ { { \displaystyle \frac { 1 } { N } \sum _ { i = 0 } ^ { N - 1 + m ^ { \prime } } d _ { i - m ^ { \prime } } d _ { i } ^ { \prime } } } & { { 1 - N \leq m ^ { \prime } < 0 } } \end{array} \right.
$$

则将式(12)化简后可以得到[8]

$$
\begin{array} { r } { R _ { s s ^ { \prime } } = \left\{ \begin{array} { l l } { \left( \tau / T _ { s } - m ^ { \prime } \right) \left( r _ { m ^ { \prime } + 1 } - r _ { m ^ { \prime } } \right) + r _ { m ^ { \prime } } , } & { \tau \in \left[ m ^ { \prime } T _ { s } , \left( m ^ { \prime } + 1 \right) T _ { s } \right] } \\ { \left( \tau / T _ { s } - m ^ { \prime } - N \right) \left( r _ { m ^ { \prime } + 1 - N } - r _ { m ^ { \prime } - N } \right) + r _ { m ^ { \prime } - N } , \tau \in \left[ \left( m ^ { \prime } - N \right) T _ { s } , \left( m ^ { \prime } - N + 1 \right) T _ { s } ^ { \dagger } \right] ^ { 2 } } \\ { 0 , } & { o t h e r } \end{array} \right. } \end{array}
$$

从式(14)可以看出，互相关函数 $R _ { s s ^ { \prime } } ( \tau )$ 是一个线性的分段函数，它所有的分段点都位于 $m ^ { \prime } T _ { s }$ 处，此时的互相关函数值可以表示为

$$
R _ { s s ^ { \prime } } \big ( m ^ { \prime } T _ { s } \big ) = r _ { m ^ { \prime } } , 1 - N \leq m ^ { \prime } < N - 1
$$

由上面分析可以知道，互相关函数的形状是由 $r _ { m ^ { \prime } }$ 的值决定的，因而称 $r _ { m ^ { \prime } }$ 为互相关形状点。对于接收机来说，接收信号$s ( t )$ 的形状码向量是确定的。因此通过改变参考信号 $s ^ { \prime } ( t )$ 的形状码向量可以改变互相关函数的形状。

现在有很多的文献[6已经证明，当只使用一路本地码时，是很难获得没有边锋的互相关函数的，因此需要接收机生成多个本地码。一种基于伪相关函数的方法在文献[8]中被提出来，该方法是使用两路本地参考信号分别与接收信号做互相关处理，然后对生成的两路互相关函数合成得到一个单一的窄主峰函数。参照伪相关函数的设计思想，本文重新设计的两路参考信号$s ^ { ( 1 ) } ( t )$ 和 $s ^ { ( 2 ) } ( t )$ 的形状码向量分别为 $d ^ { ( 1 ) }$ 和 $d ^ { ( 2 ) }$ ，与接收信号$s ( t )$ 的互相关函数分别为 $R _ { _ { s s } ( 1 ) } \left( \tau \right)$ 和 $R _ { _ { s s ^ { ( 2 ) } } } ( \tau )$ ，则伪相关合成函数如下：

$$
R \left( \tau \right) = \left| R _ { _ { s s ^ { ( 1 ) } } } \left( \tau \right) \right| + \left| R _ { _ { s s ^ { ( 2 ) } } } \left( \tau \right) \right| - \left| R _ { _ { s s ^ { ( 1 ) } } } \left( \tau \right) + R _ { _ { s s ^ { ( 2 ) } } } \left( \tau \right) \right|
$$

为了得到一个对称的合成相关函数，则互相关函数必须满足下列条件：

$$
R _ { _ { s s ^ { \left( 2 \right) } } } \left( \tau \right) = - R _ { _ { s s ^ { \left( 1 \right) } } } \left( - \tau \right)
$$

为了彻底消除捕获的模糊性，必须保证合成函数 $R ( \tau )$ 是一个单一的主峰函数，则必须满足下列条件：

$$
\begin{array}{c} \begin{array} { r l } & { \left\{ R ( 0 ) \neq 0 \right. } \\ & { \left\{ R \big ( \tau \big ) = R \big ( - \tau \big ) , \tau \in \left( - T _ { s } , T _ { s } \right) \right.} \\ & { \left\{ R \big ( \tau \big ) = 0 , \tau \in \left[ - N T _ { s } , - T _ { s } \right] \cup \left[ T _ { s } , N T _ { s } \right] \right. } \end{array}   \end{array}
$$

根据互相关函数的分段线性特性，可以得到互相关形状点必须满足的条件：

$$
\begin{array} { r } { { \left\{ \begin{array} { l l } { r ^ { \left( 1 \right) } { } _ { m ^ { \prime } } r ^ { \left( 1 \right) } - m ^ { \prime } } { } \leq 0 , m ^ { \prime } \not = 0 \right.} \\ { r ^ { \left( 1 \right) } { } _ { 0 } \not = 0 . } \end{array}  }  \end{array}
$$

由于 $R ( \tau )$ 的构造是非线性的，所以在互相关函数的过零点可能会产生新的边锋[8]。为了解决这个问题，当 ${ r _ { m ^ { \prime } } } ^ { ( 1 ) } { r _ { m ^ { \prime } + 1 } } ^ { ( 1 ) } < 0$ （204时还需要满足条件：

$$
r _ { m ^ { \prime } } ^ { ( 1 ) } r _ { - m ^ { \prime } - 1 } ^ { ( 1 ) } = r _ { - m ^ { \prime } } ^ { ( 1 ) } r _ { ~ m ^ { \prime } + 1 } ^ { ( 1 ) }
$$

# 2.2新提出的合成算法

BOC信号根据副载波的不同，可以概括为sine-BOC和cosine-BOC两种调制信号，它们的调制阶数又分为奇数和偶数两种情况，所以说，BOC调制信号可以分为四种类型。但是根据形状码向量的对称性，可以将四种类型分为下列两种情况：

1）奇对称情况

偶数阶sine-BOC和奇数阶cosine-BOC类型时，有

$$
d _ { m } \cdot d _ { { } _ { N - 1 - m } } \leq 0 , 0 \leq m \leq N - 1
$$

2）偶对称情况

奇数阶 sine-BOC和偶数阶cosine-BOC类型时，有

$$
d _ { m } \cdot d _ { { } _ { N - 1 - m } } \geq 0 , 0 \leq m \leq N - 1
$$

形状码向量还应该满足能量归一化条件：

$$
\sum _ { i = 0 } ^ { N - 1 } \bigl ( d _ { i } \bigr ) ^ { 2 } = N
$$

通过参考伪相关函数波形的取值，本文设计了两组新的形状码向量为

a）偶数阶 sine-BOC 和奇数阶cosine-BOC 类型时，有

$$
\left\{ \begin{array} { l } { { d ^ { ( 1 ) } = \left[ \displaystyle \frac { N ^ { 2 } } { 1 + \alpha ^ { 2 } } , 0 , \cdots , 0 \right] _ { N \times 1 } } } \\ { { d ^ { ( 2 ) } = \left[ 0 , \cdots , 0 , \displaystyle \sqrt { \frac { N ^ { 2 } } { 1 + \alpha ^ { 2 } } } \right] _ { N \times 1 } } } \end{array} \right.
$$

b）奇数阶sine-BOC和偶数阶cosine-BOC类型时，有

$$
\left\{ \begin{array} { l } { { d ^ { ( 1 ) } = \left[ \displaystyle \frac { N ^ { 2 } } { 1 + \alpha ^ { 2 } } , 0 , \cdots , 0 \right] _ { N \times 1 } } } \\ { { d ^ { ( 2 ) } = \left[ 0 , \cdots , 0 , - \displaystyle \sqrt { \displaystyle \frac { N ^ { 2 } } { 1 + \alpha ^ { 2 } } } \right] _ { N \times 1 } } } \end{array} \right.
$$

其中： $\alpha \in \left[ 0 , 1 \right)$ 为控制参数。

借助上面设计的两路参考信号的形状码向量，可以求解不同类型下的伪相关函数 $R ( \tau )$ 。对奇数阶的 sine-BOC 求解。先推导 $m ^ { \prime } \geq 0$ 的情况， $m ^ { \prime } < 0$ 时类似。令 $\beta = \sqrt { 1 / \left( 1 + \alpha ^ { 2 } \right) } < 1$ ，将式(25)代入式(13)中可得

$$
\begin{array}{c} \begin{array} { r } { \{ { \begin{array} { l } { { r ^ { ( 1 ) } } _ { m ^ { \prime } } = \displaystyle { \{ \beta , ~ m ^ { \prime } = 0  } } \\ { 0 , ~ 0 < m ^ { \prime } \leq N - 1 } \\ { { r ^ { ( 2 ) } } _ { m ^ { \prime } } = \displaystyle { \{ - \beta , ~ m ^ { \prime } = 0  } } \end{array}  } } \end{array}    \end{array}
$$

由式(26)可以得到

$$
\begin{array}{c} \begin{array} { r } { \{ \begin{array} { l l } { \displaystyle r ^ { ( 1 ) } m ^ { \prime } + 1 - r ^ { ( 1 ) } m ^ { \prime } = \{ 0 , \quad 1 \leq m ^ { \prime } \leq N - 2  } \\ { \displaystyle 0 , \quad m ^ { \prime } = N - 1 } \\ { \displaystyle \{ { { \sigma } ^ { ( 2 ) } } m ^ { \prime } + 1 - r ^ { ( 2 ) } m ^ { \prime } = \{ 2 \beta , \qquad m ^ { \prime } = 0  } \\ { \displaystyle  [ \beta ^ { ( - 1 ) } { } ^ { m ^ { \prime } } \beta , \ 1 \leq m ^ { \prime } \leq N - 2   } \\ { \displaystyle  \beta , \ \qquad m ^ { \prime } = N - 1 } \end{array}  } \end{array}   \end{array}
$$

将式(26)(27)代入式(14)中，并且令 $p = \tau / T _ { s } - m ^ { \prime }$ ，其中$\tau \in \left[ m ^ { \prime } T _ { s } , ( m ^ { \prime } + 1 ) T _ { s } \right]$ 时， $p \in \left[ 0 , 1 \right)$ 。由此可以得到 $R _ { _ { s s } ( 1 ) } \left( \tau \right)$ 和

$R _ { _ { s s ^ { ( 2 ) } } } ( \tau )$ 的表达式为

$$
\begin{array} { r }  \{ \begin{array} { l l } { R _ { s ^ { ( 0 ) } } ( \tau ) = \{ \begin{array} { l l } { ( 1 - p ) \beta , \ \tau \in [ 0 , T _ { s } ) } \\ { 0 , \quad \quad \tau \in [ m ^ { \prime } T _ { s } , ( m ^ { \prime } + 1 ) T _ { s } ) } \\ { \quad \quad \tau \in [ ( N - 1 ) T _ { s } , N T _ { s } ) } \end{array}  } \\ { R _ { s ^ { ( 0 ) } } ( \tau ) = \{ \begin{array} { l l } { ( 2 p - 1 ) \beta , \ \tau \in [ 0 , T _ { s } ) } \\ { ( - 1 ) ^ { m ^ { \prime } - 1 } ( 1 - 2 p ) \beta , \tau \in [ m ^ { \prime } T _ { s } , ( m ^ { \prime } + 1 ) T _ { s } ) } \\ { \quad \quad \quad \quad \quad \quad \quad \tau \in [ ( N - 1 ) T _ { s } , N T _ { s } ) } \end{array}  } \end{array} \end{array}
$$

将式(28)代入式(16)可以得到伪相关函数 $R ( \tau )$ 的表达式。从上面可以知道两个参考信号和接收信号的互相关函数是分段线性的，所以 $R ( \tau )$ 必须进行分段讨论。

a)当 $\tau \in \left[ \big ( N - 1 \big ) T _ { s } , N T _ { s } \right)$ 时，由于 $R _ { \mathrm { { } _ { \it S S } ( 1 ) } } \left( \tau \right) = 0$ ， $R _ { _ { s s } ^ { ( 2 ) } } < 0$ ，所以 $R ( \tau ) = 0$ 。

b）当 $\tau \in \Bigl [ m ^ { \prime } T _ { s } , \bigl ( m ^ { \prime } + 1 \bigr ) T _ { s } \bigr ) , 1 \leq m ^ { \prime } \leq N - 2$ 时，由于$R _ { \mathrm { { } _ { \it S S } } ^ { ( 1 ) } } ( \tau ) = 0$ ，所以 $R { \big ( } \tau { \big ) } = 0$ 。

c）当 $\tau \in \left[ 0 , T _ { s } \right)$ 时， $R _ { _ { S S } ^ { ( 1 ) } } ( \tau ) { > } 0$ 。

若 $p > \frac { 1 } { 2 }$ ，则 $R _ { _ { S S } ^ { ( 2 ) } } \left( \tau \right) > 0$ ；若 $p \leq \frac { 1 } { 2 }$ ，则 $R _ { _ { s s ^ { ( 2 ) } } } ( \tau ) \leq 0$ 。由上分析可知，当 $m ^ { \prime } \geq 0$ 时，只有 $p \leq \frac { 1 } { 2 }$ 时，伪相关函数 $R ( \tau )$ 才有值，它的表达式为

$$
R ( \tau ) = - 2 R _ { _ { s s ^ { ( 2 ) } } } ( \tau ) = ( 2 - 4 p ) \beta
$$

同理可知，当m'<0，p> $m ^ { \prime } < 0 \ , \quad p > - \frac { 1 } { 2 }$ 1时，伪相关函数R(τ)的表达式为

$$
R \big ( \tau \big ) = \big ( 2 + 4 p \big ) \beta
$$

将 $p = \tau / T _ { s }$ 和 $\beta = \sqrt { 1 / \left( 1 + \alpha ^ { 2 } \right) }$ 代入式(29)和(30)可以得到伪相关函数的最终表达式为

$$
R \left( \tau \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { 2 - 4 \big | \tau \big | / T _ { s } } { \sqrt { 1 + \alpha ^ { 2 } } } , } & { \displaystyle \big | \tau \big | \leq \frac { 1 } { 2 } T _ { s } } \\ { 0 , } & { o t h e r s } \end{array} \right.
$$

上面具体推导了奇数阶sine-BOC类型的表达式，对于其他三种类型来说，也可以同理推出，最终结果相同。对于BOC的衍生信号，也可以用相似的结果表示。以CBOC(6,1,1/11)为例，它的表达式可以表示为

$$
R _ { c } \left( \tau \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { \left( 2 - 4 | \tau | / T _ { s } \right) g } { \sqrt { 1 + \alpha ^ { 2 } } } , } & { \displaystyle | \tau | \leq \frac { 1 } { 2 } T _ { s } } \\ { 0 , } & { o t h e r s } \end{array} \right.
$$

其中： $g$ 的值为 $\sqrt { { 1 0 } / { 1 1 } } + \sqrt { { 1 } / { 1 1 } }$ 。

从式(31)能够知道互相关函数 $R ( \tau )$ 是一个对称的单峰三角函数，它的最大值 $h ( \alpha )$ 和底部宽度 $\omega ( \alpha )$ 的表达式为

$$
\left\{ \begin{array} { l l } { \displaystyle h \big ( \alpha \big ) = \frac { 2 } { \sqrt { 1 + \alpha ^ { 2 } } } } \\ { \omega \big ( \alpha \big ) = T _ { s } } \end{array} \right.
$$

由式(33)可以知道，最大值 $h ( \alpha )$ 受到控制参数 $\alpha$ 的影响，当 $\alpha = 0$ 时， $R ( \tau )$ 的最大值为2，是自相关函数主峰高度的 2倍；同理可得，当 $\scriptstyle { \alpha = 0 }$ 时，式(32)中 $R _ { c } \left( \tau \right)$ 的最大值大约为 2.5。底部宽度 $\omega ( \alpha )$ 保持为 $T _ { s }$ ， $T _ { s }$ 为一个子码片的持续时间，因此主峰的底部宽度会随着调制阶数的改变而变化，若调制阶数越高，则底部宽度变得越窄。本文提出的改进方法彻底解决了BOC及其衍生信号自相关函数的多个边锋问题，大大提高了主峰高度。

![](images/2341b9c85f04b6c649d43a01f990983effb147e980c64c2a95cf19cce8899876.jpg)  
图1相关函数

由图1的仿真图形可以看出，新提出的形状码向量可以让$R ( \tau )$ 成为一个峰值更高，宽度更窄的单一主峰函数，并完全解决了自相关函数带来的模糊性问题。仿真验证了推导的正确性。

为了提高主峰能量，本文提出了一种新的合成算法，它的表达式如下：

$$
R _ { p } \left( \tau \right) = R _ { s s } \left( \tau \right) \cdot \left( \left| R \left( \tau \right) \right| + \left| R _ { s s } \left( \tau \right) \right| - \left| R \left( \tau \right) - R _ { s s } \left( \tau \right) \right| \right)
$$

其中 $R _ { s s } \left( \tau \right)$ 表示的是自相关函数。

# 2.3算法的具体步骤

a）先对BOC信号进行解调，然后对解调后的BOC信号做傅里叶变换;

b)按式(24)或(25)选择本地形状码向量生成伪随机码，调制后生成两路本地参考信号；

c）对步骤b)中得到的两路本地参考信号选取相关序列，然后进行傅里叶变换并取共轭；

d)将步骤c)中得到的两路参考信号分别与傅里叶变换后

的 BOC 接收信号相乘，然后做反傅里叶变换得到 $R _ { _ { s s } ^ { ( 1 ) } } ( \tau )$ 和$R _ { _ { s s } ( 2 ) } \left( \tau \right) ;$ （20

e)按式(16)(34)合成得到无模糊捕获函数，将得到的最大值与门限值进行比较，如果小于门限值，则重复步骤a)\~d)；如果大于门限值，则进入跟踪阶段。

# 3 仿真实验分析

实验中信号的数据码 $d { \big ( } t { \big ) } = 1$ ，伪码的码长为1023，调制信号的采样频率为 $4 9 1 . 0 4 \mathrm { M H z }$ 。为了突出本文算法的优点，实验采用SCPC算法进行对比，它的具体合成函数如下所示：

$$
R _ { \mathrm { { S C P C } } } \left( \tau \right) = R _ { \mathrm { { B O C / Q B O C } } } { } ^ { 2 } \left( \tau \right) + R _ { \mathrm { { B O C } } } { } ^ { 2 } \left( \tau \right)
$$

其中： $R _ { \mathrm { { B O C / Q B O C } } } ( \tau )$ 为接收信号和QBOC 码的互相关函数；  
RBoc(τ)为接收信号和BOC码的相关函数。

实验1BOC及其衍生信号的相关函数分析。实验主要对sine-BOC(15,10)， cosine-BOC(15,10)，cosine-BOC(10,5),TDDM-BOC(4,1)，CBOC(6,1,1/11)，AItBOC(15,10)调制信号做了捕获分析，仿真结果如图2所示。

![](images/a404ead9e1f20f9bb2d4fab4b8eedcfa17778a0ed87dc19f2b5d58fb554e59d9.jpg)  
图2自相关函数对比图

由图2可知，所有BOC信号的自相关函数都存在边锋，并且调制阶数越高边锋越多，这将会给信号的捕获带来麻烦。图中的SCPC算法虽然可以消除副峰，但是得到的相关函数主峰很宽，破坏了原本自相关函数窄主峰的特性，并且BOC信号的副峰越多，仿真得到的曲线越不平滑，这将会大大降低捕获的精度。而本文提出的算法消除了所有边锋，不仅保持了原自相关函数窄主峰的特性，还大大提高了主峰的高度。

实验2主峰比例均值分析。主峰比例均值定义为:

$$
p _ { \nu } = { \mathrm { m a x } } \{ { \mathrm { a b s } } { \big ( } K ( n ) { \big ) } \} / { \mathrm { a v e } } \{ { \mathrm { a b s } } { \big ( } K ( n ) { \big ) } \}
$$

其中： $K ( n )$ 表示相关序列；ave 表示取平均序列。

实验以 sine-BOC(15,10)，cosine-BOC(10,5)，TDDM-BOC(4,1)和CBOC(6,1,1/11)调制信号为例进行了仿真，仿真结果如图3所示。

![](images/ba1a31cc01968ee69811baf18810be008ea786eb20be2c20817cad367da03230.jpg)  
图3主峰比例均值

从图3可以看出，本文算法得到的主峰比例均值明显高于SCPC 算法，因此检测性能也应该优于SCPC 算法；自相关函数的主峰比例均值略高于SCPC算法，这是因为SCPC算法虽然消除了自相关函数的副峰，但是却破坏了窄主峰的特性，导致性能变差。

实验3功率比分析。功率比的表达式定义为

$$
\eta = \frac { p _ { \mathrm { m a i n } } } { p _ { \mathrm { a l l } } }
$$

其中： $p _ { \mathrm { m a i n } }$ 表示主峰的功率， $p _ { \mathrm { a l l } }$ 表示整个信号的功率。

信道的冲击响应表示为

$$
h \left( t \right) = \delta \left( t \right) + \alpha \delta \left( t - \beta \right)
$$

其中： $\delta ( t )$ 表示冲击函数； $\alpha$ 为多径幅度； $\beta$ 为多径时延。

实验以sine-BOC(15,10），cosine-BOC(10,5），CBOC(6,1,1/11)和AItBOC(15,10)调制信号为例进行了仿真，仿真结果如图4所示。

从图4可以看出，在复杂环境下，本文提出的算法比SCPC算法和原自相关函数具有更大的功率比。这说明本文算法得到的主峰具有更大的能量。当时延小于一个码片且多径时延是副载波周期的整数倍时，本文算法的功率比有一小段的下降，但是稳定之后，本文方法的主峰能量相对于SCPC算法提高了

$23 \%$ 总的来说，就主峰能量而言，本文提出的算法是优于SCPC算法和自相关函数法的。

![](images/959a7783108993d189110803bab0b6e355db6b0720659fee6504bc6a73c33d81.jpg)  
图4功率比比较

# 4 结束语

针对BOC及其衍生信号所带来的模糊捕获问题，本文在伪相关函数的基础上提出了一种通用的无模糊改进方法。该方法首先通过接受信号分别与两个本地参考信号做互相关，然后非线性结合得到一个单一主峰函数，最后与自相关函数合成一种无模糊捕获算法。仿真实验结果验证了该方法能够适用于任意类型和任意阶数的BOC调制信号，并且保留了自相关函数窄主峰的特性，提高了主峰高度，能在低信噪比下捕获到信号，各种性能优于SCPC算法和传统方法。这对于BOC信号的无模糊捕获有一定的指导意义。但是在高动态的复杂环境下，影响因素颇多，给BOC信号的捕获带来了更大的挑战，针对这个问题，下一步研究准备使用改进的部分匹配滤波结合快速傅里叶变换方法实现高动态环境下的BOC信号捕获。

# 参考文献：

[1]Betz JW.Binary offset carrier modulations for radio navigation [J]. Navigation,2001,48 (4): 227-246.   
[2] Zitouni S,Rouabah K,Chikouche D,et al.General analytical models characterizing MBOC modulated signal [J].Aerospace Science Technology, 2016,50 (46): 112-126.   
[3]Lohan E S,Burian A,Renfors M.Low-complexity unambiguous acquisition methods for BOC modulated CDMA signals [J].International Journal of Satellite Communications,2008,26(6): 503-522.   
[4]Sui Jingtao,Kou Yanhong.Analysis and test of unambiguous tracking performance for High-Order BOC signals [C]//Proc of the China Satellite Navigation Conference.2012:617-627.

[5]姚彦鑫，杨东凯，张其善.GPS多径信号的自适应滤波估计方[J].航

空学报,2010,31(10):2004-2009.   
[6]Julien O,Macabiau C,Cannon ME,et al.Aspect: unambiguous sine-BOC (n,n) acquisition//tracking technique for navigation applications [J].IEEE Tran on Aerospace and Electronic Systems,2007,43(1): 150-162.   
[7]Shivaramaiah N C,Dempster A G.An analysis of Galileo E5 signal acquisition strategies [C]//Proc of the ENC-GNSS.2008:28-30.   
[8]Yao Zheng,Cui Xiaowei, Lu Mingquan,et al. Pseudo-correlation function based unambiguous tracking technique for sine-BOC signals [J].IEEE Trans on Aerospace and Electronic Systems,2010,46 (4):1782-1796.   
[9]Yao Zheng，Lu Mingquan.Side-peaks cancellation analytic design framework with applications in BOC signals unambiguous processing [C]// Proc of ION International Technical Meeting.2011.   
[10] Yao Zheng,Lu Mingquan,Feng Zhenming.Unambiguous sine-phased binary offset carrier modulated signal acquisition technique [J]. IEEE Trans on Wireless Communications,2010,9(2):577-580.

[11]陈辉华，王榕，贾维敏，等．基于合成相关函数的Cosine-BOC信号无

模糊跟踪方法[J]．系统工程与电子技术,2012,34(6):1090-1096.   
[12] 潘毅，张天骐，李军伟，等．基于PCF的BOC信号无模糊算法分析[J]. 科学技术与工程,2013,13(28):8280-8283.   
[13] Yao Zheng,Lu Mingquan,Feng Zhenming.Unambiguous technique for multiplexed binary offset carrier modulated signals tracking [J]. IEEE Signal Processing letters,2009,16 (7): 608-611.   
[14] Chen Huihua,Wang Rong,Jia Weimin,et al.An unambiguous tracking method based on pseudo correlation function for AltBOC (15,10) signal [J]. Wireless Personal Communications,2013,69(4):1347-1364.   
[15]任嘉伟，杨贵同，贾维敏，等.BOC信号合成函数通用无模糊跟踪方法 [J]．航空学报,2014,35(7):2031-2040.   
[16]刘桢，黄洁，王建涛，等．基于伪相关函数的多级电平编码符号信号通 用无模糊跟踪方法[J].物理学报,2017,66(13):266-277.   
[17] Yin Bo,Wang Gang,Qi Yanjie.Unambiguous sine-phased binary offset carrier modulated signals tracking technique [J]. Optik: International Journal for Light and Electron Optics,2017,132 (5): 284-290.