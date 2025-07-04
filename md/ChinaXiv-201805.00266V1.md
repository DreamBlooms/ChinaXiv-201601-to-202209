# 基于混沌Duffing振子的BPSK信号K-means聚类解调方法

蒋亮亮，江虹，曾闵(西南科技大学 信息工程学院，四川 绵阳 621010)

摘要：针对二进制相移键控（binaryphase shift keying，BPSK）信号在低信噪比下解调误码率较高的问题，提出了一种基于混沌 Duffing 振子的 K-means 解调方法。该方法的思想是根据混沌 Duffing 振子系统对初值的敏感性以及对噪声的免疫特性，低信噪比下Duffing 振子系统输入BPSK信号时，由于BPSK信号相位在 $0 ^ { \circ }$ 和π之间的跳变从而导致Dufing振子输出相轨迹状态发生改变。针对相轨迹状态的变化，采用K-means聚类算法对相轨迹进行迭代求质心，根据收敛后的质心间距大小对 BPSK信号进行判决解调。仿真结果表明,与现有的几种解调方法相比较，基于混沌 Duffing振子的 BPSK信号K-means 聚类解调方法在低信噪比下解调速度、解调精度等方面都有了较大的提高。

关键词：Duffing振子；相轨迹；K-means聚类；误码率 中图分类号：TN911.72 doi: 10.3969/j.issn.1001-3695.2017.07.0882

# K-means clustering demodulation method for BPSK signal based on chaotic Duffing oscillator

Jiang Liangliang, Jiang Hong, Zeng Min (School ofInformation Engineering,Southwest UniversityofScience&Technology,Mianyang Sichuan 621010,China)

Abstract:For the binary phase shift keying(BPSK)signal always get high bit error rate(BER)when demodulated in a low signal-to-noiseratio(SNR)environment,aK-means clusteringdemodulation methodbasedonchaos Duffingoscilatorhas been proposed toreducetheBER.This studyaccrding to twocharacteristics ofDuffingoscilltor,notonly isitverysensitive tothe initial value, but also has certain immunity to noise.The phase of BPSK signal change between $0 ^ { \circ }$ and $\pi$ cause state change in theDufng oscilator'sphaseorbits,andusingaK-means clustering methodtofindthecentroidofphaseorbitbyiteration,then BPSK signalcan been demodulating bycalculate the distance ofcentrods.Simulationresults showthatthe K-means clustering demodulation method hasa great improvement in thecalculationrateandthedemodulationaccuracyinalowSNRenvironment.

Key Words:Duffing oscillator; phase orbit; K-means clustering; bit error rate

# 0 引言

在数字通信技术领域中，由于 BPSK 调制信号具有良好的频带利用率，较强的抗干扰性能，硬件易实现等优良品性。因此，BPSK 信号被广泛应用于卫星通信、数字电视等通信系统中。在数字通信系统中，由于信号处于的信道环境日趋复杂，信道背景噪声、码间串扰等因素的影响，导致通信系统在接收端产生较高的解调误码率。为了提升接收端对调制信号的接收解调性能，保障通信质量，因此，在低信噪比环境下降低信号解调误码率具有重要的意义。

针对低信噪比环境下 BPSK信号的解调问题，国内外不少学者将非线性处理方法引入到信号处理领域中，文献[1,2]利用混沌Duffing振子对 BPSK信号进行处理，提出均方差算法解调判决，但是对 BPSK信号采样率过大，且没有考虑到BPSK基带信号的码间串扰；文献[3,4]基于随机共振方法对 2FSK 和 4FSK 信号进行解调，在没有考虑到基带信号码间串扰的同时，信号频率的大小也限制了解调过程。文献[5,6]研究了一种基于参数调整的随机

共振的 BPSK信号解调方法，该方法在一定程度上完成了低信噪比下 BPSK信号的解调，但在求解过程中算法的参数、信号频率以及幅度都对解调过程产生极大的影响，且调节随机共振参数与信号参数使二者匹配十分困难。参考大量文献发现，现有的BPSK 信号解调技术，存在以下几个关键问题：a)现有的一些较先进的解调方法在参数调节上存在很大困难；b)在解调 BPSK 信号时，大都文献均忽略了基带信号的码间串扰现象。

针对上述存在的问题，本文考虑了高斯信道传输条件下基带信号码间串扰，并设计符合信道传输的抗码间干扰的成型滤波器。

结合混沌理论将 Duffing 振子应用在 BPSK 信号处理中，针对混沌阵子处理后的信号，采用了K-means 聚类解调算法，使低信噪比环境下BPSK信号解调的误码率得到降低。

# 1 BPSK信号滚降调制及混沌Duffing振子机理简介

# 1.1BPSK信号调制原理

BPSK信号通常用相位 $0 ^ { \circ }$ 和 $\pi$ 表示二进制符号信息“1”和“-1”，其时域表达式为

$$
\mathbf { S } _ { b p s k } ( t ) = A \cos ( 2 \pi f _ { c } t + \varphi )
$$

其中： $A$ 是信号的幅度， $f _ { c }$ 为载波频率， $\varphi$ 为相位，当发送码元"-1”, $\varphi$ 为 $\pi$ ，发送“1”时 $\varphi$ 为 $0 ^ { \circ }$ 。如图1a所示，是未经成型的BPSK信号时域波形：

在大多文献中，均是以图1（a）中的BPSK信号来做相关分析。但是，在实际通信中，由于相邻码元间会因为拖尾现象的存在而导致相互干扰（如图1b所示），故图1（a）中的BPSK信号不能作为信息的载体在信道中传输的。因此，需要对图1（a）中的BPSK信号进行成型滤波处理，达到消除码间串扰的目的。

![](images/5575ad125e1a9e870a82063aae0a637e11ab4590fdca9dd24df147d0d920724a.jpg)  
图1BPSK信号、码间串扰、滚降滤波器冲击响应时域波形图

消除码间串扰常用的手段是设计成型滤波器，采用具有低通特性的冲击响应作为成型滤波器来防止码间串扰[7]，其表达式如下：

$$
{ \mathrm { h } } ( t ) = \frac { \displaystyle \sin ( \frac { \pi } { T _ { s } } t ) \cos ( \alpha \pi \frac { t } { T _ { s } } ) } { \displaystyle \frac { \pi } { T _ { s } } t \quad 1 - 4 \alpha ^ { 2 } \frac { t ^ { 2 } } { T _ { s } ^ { 2 } } } { = } \mathrm { S a } ( \frac { \pi t } { T _ { s } } ) { \bullet } \frac { \cos ( \alpha \pi \frac { t } { T _ { s } } ) } { 1 - 4 \alpha ^ { 2 } \frac { t ^ { 2 } } { T _ { s } ^ { 2 } } }
$$

其中： $T _ { s }$ 是采样时间间隔， $\alpha$ 是升余弦滚降系数，且满足 $0 { \leq } \mathrm { a } { \leq } 1$ ，取 $\scriptstyle a$ 值分别为0，0.5，0.8，1，得到如图1c中不同滚降系数 $\scriptstyle a$ 对应的成型滤波器的冲击响应。可见滚降系数 $\scriptstyle a$ 越大，冲击响应函数 $\mathbf { h } ( \mathrm { t } )$ 的拖尾衰减越快，对位定时的精度要求越低。成型滤波器的滚降系数越大传输带宽增大，带宽增大为 $\scriptstyle \mathbf { B } = \left( \ 1 + \alpha \right) f _ { s }$ ，但是带宽增大会导致带宽利用率减小[8],带宽利用率为 $\scriptstyle \eta = R _ { B } / B = 2 / ( 1 + \alpha )$ 0

因此，由（1）和（2）式，成型后的BPSK调制时域表达式为：

$$
\mathbf { S } _ { b p s k } ( t ) = \mathbf { A } ( t ) { \bullet } \cos ( 2 \pi f _ { c } t + \varphi )
$$

其中， $\mathrm { { A ( t ) } = \ a ( t ) * h ( t ) }$ ， $\mathbf { a } ( \mathrm { t } )$ 为码元符号表达式。取长度 $L e n { = } 2 0$ 个的随机码元，基带码元信号幅度为 $0 . 1 \mathrm { V }$ ，码元速率 $R _ { b } { = } 1 \mathrm { K }$ baud,载频 $f _ { c } { = } 8 \mathrm { K } H z$ ，采样频率 $f _ { s } { = } 4 0 f _ { c } { = } 3 2 0 \mathrm { K } H z$ 滚降系数 $\scriptstyle { a = 0 . 7 }$ ，得到如图2a中BPSK信号成型调制过程，图2b中为不同 SNR下的BPSK信号。

![](images/8e74e1fc9510f464e24cb3c2b358a572e9c5f52262c4ad08e19df52933fc3bf3.jpg)  
图2BPSK滚降调制过程时域波形图

# 1.2混沌 Duffing 振子简介

混沌 Duffing 振子具有初值的敏感性以及对噪声的免疫性。混沌振子系统初值的微小变化会引起系统输出具有很大的改变[9];另外，混沌 Duffng 振子具有对噪声的免疫性，即在噪声的扰动下，混沌振子系统依然可以保持自身丰富的动力学特征[0]。这为低信噪比环境下，弱信号检测处理和接收解调带来巨大的优势。本文利用混沌 Duffing 振子对初值的敏感性以及对噪声的免疫特性完成低信噪比下BPSK信号的解调。

Duffing振子系统的标准动力学行为方程描述为

$$
{ \ddot { x } } + k { \dot { x } } + \operatorname { f } \left( x \right) = \gamma \cos \left( 2 \pi f _ { c } t \right)
$$

其中： $x$ 为 Duffing 振子系统的输出， $k$ 为系统的阻尼系数，ycos(2πfet）为Duffing 振子的周期策动力，y为周期策动力的幅值，$\operatorname { f } ( x )$ 是一非线性回复力函数，其表达式为 $\scriptstyle { \mathrm { f } } ( x ) = - a x + b x ^ { 3 }$ 。其中， $\mathbf { \Delta } _ { a }$ 和 $b$ 均是非线性回复力参数[1I][12]，且满足 $a { > } 0 , b { > } 0$ ，故Duffing 振子方程表达式可以为

$$
\stackrel { \cdot \cdot } { x } + k \stackrel { \cdot } { x } - a x + b x ^ { 3 } = \gamma \cos \left( 2 \pi f _ { c } t \right)
$$

式（6）亦可以有如下状态方程描述：

$$
\left\{ \begin{array} { l l } { \dot { x } = y } \\ { \dot { y } = - k y + a x - b x ^ { 3 } - \gamma \cos ( 2 \pi f _ { c } t ) } \end{array} \right.
$$

在 Holmes 型Duffing 振子系统中，取 $\scriptstyle a = 1 , b = 1$ ，阻尼系数 $k { = } 0 . 5$ 。在不考虑载频估计偏差的情况下，根据 Melnikov 方法[13],策动力幅值y分别取0.8，0.826和0.83，并用四阶龙格-库塔法解(6)式，得到Dufing振子输出相轨迹分别如图3中（a）～（c）所示。

![](images/85c6f6179510aa98e10b99a32fae25053685e9084c05a288e731f751b230f2a5.jpg)  
图3不同策动力幅值y对应相轨迹图

由图3可知，随着周期策动力信号幅度的增加，Duffing 振子的相轨迹图由混沌状态到临界混沌状态，最后到周期状态。因此，设置合适的周期策动力信号的幅值（本文中设置周期策动力幅值为0.826)，当加入待测信号时，就可以改变 Duffing 振子输出相轨迹的状态。

在本文中，将待解调的BPSK信号加入到Duffing 振子系统中，式（5）可以写成

$$
\begin{array} { l } { \cdots } \\ { \dot { x } + k \dot { x } - a x + b x ^ { 3 } = \gamma \cos ( 2 \pi f _ { c } t ) } \\ { + \mathrm { s n } ( t ) } \end{array}
$$

其中： $\mathrm { s n ( t ) }$ 是经过传输信道引入噪声后的BPSK信号，即 $\mathrm { \ s n ( t ) { = } S _ { b p s k } ( t ) { + } n ( t ) } _ { \circ }$ ${ \bf n } ( \mathbf t )$ 是均值为0，方差为 $\delta ^ { 2 }$ 的加性高斯白噪声。因此，输入信噪比可定义为

$$
S N R _ { i n } = 1 0 \mathrm { l o g } ( \frac { P _ { b p s k } } { P _ { n } } ) = 1 0 \mathrm { l o g } ( \frac { \mathrm { A } ^ { 2 } ( t ) } { 2 \delta ^ { 2 } } )
$$

其中： $P _ { b p s k }$ 和 $P _ { n }$ 分别为BPSK信号功率和高斯噪声功率，当加入BPSK信号时，Duffing 系统的方程可以写

$$
\begin{array} { r l } & { \ddot { \mathbf { \eta } } _ { x + k } ^ { * } \dot { x } - a x + b x ^ { 3 } = \gamma \cos ( 2 \pi f _ { c } t ) } \\ & { + \mathbf { A } ( t ) \bullet \cos ( 2 \pi f _ { c } t + \varphi ) + \mathbf { n } ( t ) } \end{array}
$$

对式（9）式右边进行辅助角计算可得

$$
\begin{array} { l } { \gamma \cos ( 2 \pi f _ { c } t ) + \mathrm { A } ( t ) { \bullet } \cos ( 2 \pi f _ { c } t + \varphi ) } \\ { = \beta ( t ) { \bullet } \cos ( 2 \pi f _ { c } t + \theta ( t ) ) + \mathrm { n } ( t ) } \end{array}
$$

其中:

$$
\left\{ \begin{array} { l l } { \displaystyle \beta ( t ) = \sqrt { \gamma ^ { 2 } + 2 \gamma \mathrm { A } ( t ) \bullet \cos \varphi + \mathrm { A } ( t ) ^ { 2 } } } \\ { \displaystyle \theta ( t ) = \arctan \frac { \gamma \sin ( \varphi ) } { \gamma + \mathrm { A } ( t ) \cos ( \varphi ) } } \end{array} \right.
$$

对于BPSK信号， $\varphi$ 只有0和 $\pi$ 两种取值，故 $\theta ( { \mathfrak { t } } ) { = } 0$ ，且：

$$
\beta ( t ) = { \left\{ \begin{array} { l l } { \gamma - A ( t ) } & { \varphi = \pi } \\ { \gamma + A ( t ) } & { \varphi = 0 } \end{array} \right. }
$$

因此，根据周期策动力信号与BPSK信号叠加后幅度 $\beta ( { \mathfrak { t } } )$ 的变化，Duffing 振子的相轨迹的处于周期、混沌两种状态的交替，这两种状态的交替正由BPSK信号码元"-1"和“1”交替引起的，可由图4模型描述。

![](images/11b488de90da93eb992f00fcac3168ef4afa6064f3de80885c39a4a571ba7dd8.jpg)  
图4Duffing 振子系统相轨迹状态变化框图

根据图3和4，系统输出相轨迹后，即可设计某种判决机制进行解调，根据混沌 Duffing振子输出相轨迹的特征，本文提出一种K-means 聚类解调方法。

# 2 BPSK信号的K-means聚类解调算法

K-means 聚类算法属于简单的无监督学习算法。在 K-means 聚类中，首先，将样本聚类成K 个簇和随机选取K个聚类质心点；然后，计算K个簇的质心点，并将计算得到的K个质心点进行重新聚类；最后重复计算新的聚类质心点，直到质心收敛[516]。K-means 迭代求聚类质心算法流程图如图5所示。

![](images/f3cc4e1cf0c6fa8dd4cec619030125be4f3feef9060ca683c2c0f84a8b3490ea.jpg)  
图5K-means聚类算法流程图

当Duffing振子系统输入的BPSK信号不加噪声时，1码元（相位0）产生的相轨迹和-1码元（相位π）产生的相轨迹如下图6a所示，当信噪比 $\mathrm { S N R } { = } { - } 2 0 \mathrm { d B }$ 时，1码元和-1码元的相轨迹如下图6b所示。可以看出噪声只是在某种程度上使相轨迹变得粗糙了些，并没有使相轨迹状态发生变化。

![](images/b7d121fd0353628c2524f82e772d9ce41c91e223b17a543805577b22c99f6be5.jpg)

(a)不加噪声和加噪声情况下,码元1产生的相轨迹图

![](images/8a783459c0ad336f07a2374931df8320e84a4bc6fb921afc509c2965e9cae4fc.jpg)  
图6码元1和-1的轨迹及相轨迹K-means质心收敛示意图

根据Melnikov方法求解，Duffing振子相轨迹图具有两个鞍点[14]，为 $( \pm 1 , 0 )$ ，即不加噪声时，相轨迹的初始质心为 $( \pm 1 , 0 )$ ，对于输入加噪声的信号，Duffing振子系统输出的相轨迹经过K-means 聚类算法迭代求质心后，1码元和-1码元质心收敛后如图6c所示，不难看出1码元对应的相轨迹收敛后的质心与初始质心相比偏移量较小，而-1码元对应相轨迹收敛后的质心偏移量较大。以收敛后的两个质心的水平距离 $\scriptstyle d = \left| x _ { l - } x _ { r } \right|$ 为度量，其中 $x _ { l }$ ， $x _ { r }$ 分别为收敛后左右质心的横坐标。在输入信噪比为-15dB、-20dB、-25dB、-30dB 条件下，分别取40个样本1码元和-1码元，经过K-means 聚类算法后两种码元对应相轨迹收敛后的两个质心距离 $d$ 分布如下图7所示。

1.9 1.9   
1.8 1.8   
Ww 1.40 10 20 0-40个-1码元1.40 10 20 0-40个-1码元

(a)SNR=-15dB 时,1码元、-1码元质心收敛后距离分布 $( \mathsf { b } ) \mathsf { S N R { = } } { \mathsf { - } } 2 0 \mathsf { d B }$ 时,1码元、-1码元质心收敛后距离分布$( \mathrm { c } ) \mathrm { S N R = } . 2 5 \mathrm { d B }$ 时,1码元、-1码元质心收敛后距离分布 $( \mathrm { d } ) \mathrm { S N R } { = } { - } 3 0 \mathrm { d B }$ 时,1码元、-1码元质心收敛后距离分布

![](images/810590ef8eae9fce0f6b2bbd0ce7206f53cc4bde258709e4a3652d65ba5ffc2c.jpg)  
图7不同SNR条件下，K-means算法收敛后质心距离分布图

从图7不难看出，经过 K-means 聚类计算收敛后，1码元对应相轨迹质心横坐标距离范围约在1.76\~2.0，而-1码元对应相轨迹质心横坐标距离范围约在 $1 . 4 8 { \sim } 1 . 7 4$ 。设置合适的距离阈值，利用相轨迹数据进行 $\mathrm { \Delta K }$ -means 聚类计算，求出收敛后的质心横坐标距离，并与阈值比较，便能判别出码元信息。其步骤简要描述如下：

a)设Duffing 振子输出相轨迹上有 $\mathfrak { n }$ 个点，设置初始质心为 $\left( \pm 1 , 0 \right)$ ，计算相轨迹上所有点到质心(-1,0)的距离 $d _ { 1 1 } , d _ { 2 1 , . . . d _ { \mathrm { i } 1 } , . . . , d _ { \mathrm { n } 1 } }$ 其中 $d _ { \mathrm { i l } } { = } [ ( x _ { \mathrm { i l } } { + } 1 ) ^ { 2 } { + } ( y _ { \mathrm { i l } } { - } 0 ) ^ { 2 } ] ^ { 1 / 2 }$ ，到质心(-1,0)的距离 $d _ { 1 2 } , d _ { 2 2 , . . . , d _ { \mathrm { i } 2 , . . . , d _ { \mathrm { n } 2 } } }$ ，其中 $d _ { \mathrm { i 2 } } { = } [ ( x _ { \mathrm { i 2 } } { - } 1 ) ^ { 2 } { + } ( y _ { \mathrm { i 2 } } { - } 0 ) ^ { 2 } ] ^ { 1 / 2 } ;$

b)根据 $d _ { \mathrm { i } 1 }$ 和 $d _ { \mathrm { i } 2 }$ 的计算结果，将距离(-1,0)近的点归为一类，距离(1,0)近的点归为一类，这样可将相轨迹上的点重新分成两类，两类点数分别为n1和 ${ \mathtt { n } } 2$ ( $\mathtt { n l + n 2 = n }$ ；

c)重新计算两类点的质心 $( X _ { 1 } , Y _ { I } )$ ， $( X _ { 2 } , Y _ { 2 } )$ 为新的质心点，其中 $X _ { 1 } { = } ( 1 / \mathrm { n } 1 ) \mathrm { S u m } ( x _ { 1 , } x _ { 2 } , . . . , x _ { \mathrm { n l } } )$ ， $Y _ { 1 } { = } ( 1 / \mathrm { n 1 } ) \mathrm { S u m } ( y _ { 1 } , y _ { 2 } , . . . , y _ { \mathrm { n l } } )$ 。同理， $X _ { 2 }$ $Y _ { 2 }$ 亦可计算出；

d)重复a)中的内容，直到质心点不再偏移(或满足某个很小的偏移量);

e)计算收敛后左右两个质心的横坐标之间的距离 $d { = } | \boldsymbol { x } _ { l } - \boldsymbol { x } _ { r } |$ ，并与距离阈值 $V _ { t h d }$ 进行比较，当 $d { > } V _ { t h d }$ 时判决为1码元，反之为-1码元。

由以上步骤分析可知，K-means 聚类判决算法复杂度较低，与相干解调相比，在解调端省略了乘以恢复载波和低通滤波等步骤，使解调端的计算量得到降低。与文献[5]中的随机共振算法相比，文献[5]中随机共振算法参数较多，且参数调节过程复杂，参数在很大程度上会影响最后的计算结果，并且要求信号自身参数与随机共振的参数匹配，而本文所提方法避开了算法中参数带来的计算复杂度，也不需要算法参数与信号匹配。

基于 Matlab 仿真环境，信噪比分别设置为-25dB、-20dB、-15dB、-10dB，将本文提出的基于Dufing振子的K-means 解调方法、文献[5]中提出的随机共振解调法以及传统的相干解调法在同一台计算机上运行，从仿真时间（算法复杂度）、解调误码率两个方面进行比较，得到仿真结果如表格1中所示。

表1K-means聚类解调法在不同SNR条件下仿真结果  

<html><body><table><tr><td colspan="3">仿真参数设置：码元长度Len=500，码元速率Rb=1Kbaud载频fe=8KHz，采样频率fs=40fe=320KHz，滚降系数α=0.7，质心距离阈值为 Vthd=1.75。</td></tr><tr><td colspan="3"></td></tr><tr><td>信噪比 SNR(dB)</td><td>本文解调法</td><td>解调误码率(%) 随机共振解调法 相干解调法</td></tr><tr><td>-25</td><td>16.2</td><td>24 30.2</td></tr><tr><td>-20</td><td>10</td><td>16.2 21.8</td></tr><tr><td>-15</td><td>4.4</td><td>8 12.6</td></tr><tr><td>-10</td><td>1.0</td><td>3.8 6</td></tr><tr><td>平均仿真时间(s)</td><td>36.84</td><td>58.64 42.76</td></tr></table></body></html>

由表1不难得出，在相同的信噪比下，本文所提的方法解调误码率明显低于另外两种方法，且计算速度也快于另外两种方法。增加仿真信噪比区间，每种信噪比下仿真20次，其他仿真参数不变。以接收端的输入 SNR 为横轴，BPSK 信号解调误码率BER 为纵轴，分别计算本文所提方法、文献[5]中的随机共振法以及相干解调法的误码率，得到如图8所示的 SNR-BER 曲线。由图8可知，当输入信噪比低至-20dB 时，本文所提解调法误码率约为 $10 \%$ ，随机共振法和相干解调法误码率分别为 $1 6 \%$ 和 $22 \%$ 当输入信噪比为-10dB 时，本文所提解调法误码率仅为 $1 \%$ 左右，随机共振法和相干解调法误码率分别为 $4 \%$ 和 $6 \%$ ，通过仿真再次验证了本文所提方法在低信噪比环境下解调的优越性。

![](images/5a9885c9c676afcec7c2ff2f822040fbbd2f97b2b3611b0c8733b967cf267243.jpg)  
图8K-means聚类解调算法误码信噪比-率曲线

# 3 结束语

在数字通信中，低信噪比环境下的BPSK信号解调十分困难，为了提升通信质量，将混沌振子理论引入到数字通信中，并采用简单易行的K-means 聚类作为解调算法。该方法将低信噪比下的BPSK 信号作为混沌 Duffing 振子的输入信号，经过混沌非线性迭代求解后，得到 Duffing 振子的输出相轨，再经过K-means 聚类算法对相轨迹迭代求质心，并采用收敛后两质心距离的大小为判决依据，进行 BPSK 基带码元判决。仿真表明本文所提方法在信噪比低至-10dB时，解调误码率仅为 $1 \%$ ，且与其他两种解调方法进行比较，得出本文所提方法的可行性和优越性。

# 参考文献：

[1]徐立振．基于混沌理论的微弱 BPSK信号检测技术研究[D].哈尔滨：哈尔滨工业大学,2012.  
[2] 季锦杰．基于混沌同步的低信噪比 BPSK信号接收技术[D].哈尔滨：哈尔滨工业大学,2014.  
[3LiJin

COIumcauons Leuers,zU14: 42/-450.[4]王瑞峰，张宏雁．基于Dufing 振子的 2FSK信号检测方法研究[J]．铁道学报,2013,7(35):63-67.[5]尚金红，王辅忠，张光璐．基于随机共振的 2PSK信号相干接收误码率的研究[J].应用声学,2015,34(6):495-500.[6] 张福佳，江虹，张秋云．基于随机共振的大频率信号相干接收误码率研究[J]．自动化仪表,2017,38(7):50-53.[7]詹亚峰，曹志刚，马正新．滚降系数误差对 MPSK信号误码性能的影响[J].通信学报,2003,10(24):125-130.[8]左金钟，马伊民，习清伶．滚降系数不匹配对基带传输系统的性能影响[J].外国电子测量技术,2011,30(8):21-28.[9]谢涛，魏学业．混沌振子在微弱信号检测中的可靠性研究[J].仪器仪表学报,2008,29(6):1265-1270.[10]范剑．随机共振和混沌理论在微弱信号检测中的应用研究[D]．天津：河北工业大学.2014.[11]冷永刚，赖志慧．基于Kramers 逃逸速率的 Dufing振子广义调参随机共振研究[J].物理学报,2014,63(2):25021-25029.[12]赖志慧．基于 Dufing 振子混沌和随机共振特性的微弱信号检测方法研究[D].天津：天津大学,2014.[13]WangieESystems.2003: 945-953.[14]聂春燕．混沌系统与弱信号检测[M].北京：清华大学出版社,2009.[15]万静，张义，何云斌，等．基于KD-树和K-means动态聚类方法研究[J].计算机应用研究,2015,32(12):3590-3595.[16]翟东海，鱼江，高飞，等．最大距离选取初始簇中心的K-means文本聚类算法的研究[J].计算机应用研究,2014,31(3):713-716.