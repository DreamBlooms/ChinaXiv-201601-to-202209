# 直接序列扩频广义码索引调制

江治林1，杨 勤²，冯 胜1，葛利嘉1,2

(1.重庆邮电大学 移动通信技术重庆市重点实验室，重庆 400065;2.陆军工程大学通信士官学校 应急通信重庆市重点实验室，重庆 400035)

摘要：针对码索引调制(code index modulation，CIM)在通过增加映射比特数目的方式提升信息传输速率时，需要耗费大量的伪随机(pseudo noise，PN)码资源的问题，提出了广义码索引调制(generalized code index modulation，GCIM)。发射端的信息比特分割为映射比特和调制比特，并分别映射为PN码组的索引和调制符号。调制符号的同相部分和正交部分再分别选择激活的PN码组进行扩频。通过增加每个传输时隙PN码的激活个数，可提高映射比特数目，提升系统的频谱效率和能量效率。仿真结果表明，在相同频谱效率时，该方案相对于CIM会造成高斯信道中约2dB和瑞利衰落信道中约1dB的误比特率性能的不足，但是GCIM耗费更少的PN码资源。

关键词：高速率；能量效率；广义码索引调制；码索引调制 中图分类号：TN927 doi: 10.3969/j.issn.1001-3695.2017.11.1014

# Generalized code index modulation based on direct sequence spread spectrum

Jiang Zhilin1, Yang Qin²,Feng Sheng1,Ge Lijia1,2 (1.Chongqing KeyLaboratoryofMobile Communication Technology,Chongqing UniversityofPosts&Telecommunications, Chongqing 40o065,China; 2.Chongqing KeyLaboratory of EmergencyCommunication,Communication NCO Academyof Army Engineering University,Chongqing 40o035,China)

Abstract:Todeal with theproblemthatcode index modulation(CIM)should consumealotofpseudo noise(PN)coderesources when it increases the information transmissionrate byincreasing the number of mappng bits.This paper proposed a novel generalizedcode index modulation(GCIM).Itdivided theinformation bitsof the transmiter into mapped bitsand modulation bits and mapping modulationbits and mappedbits into modulationsymboland the indexes ofthePNcode groupsrespectively. The in-phase part and the orthogonal partof the modulation symbol spread spectrum by selecting activate PN code group respectively. What’s more,byincreasing thenumberofthe activatePNcode ofpertransmission slot,whichcould increase the numberof mappedbits and improvedthe spectral eficiencyand energy eficiencyofthe system.The simulationresults show that it is not better than CIMabout 2dB in theadditive white Gaussian noisechanneland aboutldB intherayleigh fading channelatthesamespectraleficiency.Neverthelesscompared withCIM,GCIMconsumessignificantlyless PNcodesources. Key Words: high data rate; energy effciency; generalized code index modulation; code index modulation

# 0 引言

直接序列扩频技术（direct sequence spread spectrum，DSSS)[1,2]因具备良好的抗干扰、抗多径性能、隐蔽性好、易于实现码分多址（CDMA）、直扩通信速率高等诸多优点，而在个人通信网、无线局域网、卫星通信、第三代移动通信以及军事通信等领域得到了广泛应用。然而DSSS通常会占用较大的频带宽度，且频谱利用率比较低。索引调制[3\~5]在信息传输过程中，将部分信息比特映射为特定的索引（值)，附加在调制信号中隐性传输，因此这部分信息不会耗费额外的能量，从而提升系统的传输速率和能量效率。

码索引调制[6\~8]在DSSS的基础上增加了PN码索引，发射端信息比特分割为映射比特和调制比特，并分别映射为PN 码索引和调制符号，调制符号的同相部分和正交部分再分别选择激活的PN码进行扩频，并将信号发射出去。由于映射比特通过映射为特定PN码的索引（序号）隐性传输，有效提升了扩频通信的频谱利用率和能量效率；但是随着CIM通过增加映射比特数目进一步提升信息传输速率时，会耗费大量的PN码资

源。

多进制扩频[9\~I在发射端将信息比特直接映射为一个特定的PN码进行信息的传输。由于信息比特仅仅通过映射比特进行传输，并没有调制比特，所以信息传输速率和频带利用率均比较低。并行组合扩频[12\~15]则是对多进制扩频的改进，即发射端信息比特分割为两部分，一部分映射为一个PN 码组，另一部分映射为PN 码组中每个PN 码的相位信息（同相或反相)。一个传输时隙并行传输多个PN 码，且利用每个PN 码的相位信息进行信息传输，有效提升了PN码的利用率以及信息传输速率。

本文在码索引调制中引入并行组合扩频通信的思想，提出广义码索引调制（generalized code index modulation,GCIM）。即在一个传输时隙中，同相或者正交部分的映射比特能够映射为一个PN 码组合而非一个PN 码，在PN 码总和相同的情况下，GCIM可以传输更多的映射信息比特，提升了系统的信息传输速率和频带利用率。在相同频谱效率时，GCIM与CIM进行PN码资源使用对比分析，再通过仿真验证本方案的误码率性能并与CIM进行对比。

# 发射机模型

广义码索引调制发射机模型如图1所示。发射端采用 $M$ 阶相移键控（M-ary phase shift keying，MPSK）调制。假设PN码个数为 $N _ { { t } }$ ，一个传输时隙同相或正交支路激活的PN码个数为 $N _ { \mathbf { \Phi } _ { u } }$ ，则可以产生 ${ N } _ { c } ^ { \prime }$ 种 PN 码组合，并满足 $N _ { c } { ' } = \binom { N _ { t } } { N _ { u } }$ 由于使用的组合数目 $N _ { c }$ 需为2的整数次方，才可以完整映射所需传输信息比特的各个状态，所以 $\log _ { 2 } ( N _ { c } ) { = } \lfloor \log _ { 2 } ( N _ { c } ^ { \prime } ) \rfloor { = } n _ { \mathrm { ~ \circ ~ } } \lfloor \cdot \rfloor$ 表示向下取整， $n$ 表示同相或正交支路映射部分的比特数。使用的PN码组合表示为 $W = \{ W _ { 1 } \cdots W _ { N _ { c } } \}$ ，其中： $W _ { j } = [ W _ { j , \mathrm { l } } \cdots W _ { j , \mathrm { L } } ] ^ { \mathrm { T } }$ 表示第 $j$ 个PN 码组合， $L$ 代表PN 码组的码长，码片长度为$T _ { c }$ 。则每个传输时隙发送的比特数为 $C = 2 n + m$ ，式中 $m$ 表示调制部分的比特数目，且满足 $\scriptstyle { m = \log _ { 2 } ( M ) }$ 。因而第 $i$ 个传输时隙的数据块 $\pmb { d } _ { i }$ 的分割方式如（1）所示。

$$
\begin{array} { l } { d _ { \mathrm { i } } = \left[ d _ { 1 , i } \dots d _ { \mathrm { c } , i } \right] } \\ { \quad = \left[ d _ { I , i } , d _ { Q , i } , d _ { M - a r y , i } \right] } \end{array}
$$

![](images/266802b6271e95f915fac53ef0f3f1a23d3a4433b20385798456acc353944c16.jpg)  
图1 GCIM发射机模型

其中: $d _ { I , i }$ 和 $d _ { \mathrm { Q } , i }$ 分别表示同相 PN 码映射块与正交 PN 码映射块;长度均为 $n : d _ { M - a r y , i }$ 表示长度为 $m$ 的调制部分映射块，并通过基带调制成为调制符号 $x$ ，如式（2）所示。

$$
x = a _ { i } + j b _ { i }
$$

$a _ { i }$ 和 $b _ { i }$ 分别表示调制符号的实部和虚部。

于是系统发射端信号 $y ( t )$ 可以表示为

$$
\begin{array} { r } { \displaystyle y ( t ) = \sum _ { i = 1 } ^ { B } \sum _ { k = 1 } ^ { L } \{ a _ { i } W _ { I _ { j , i } , k } p ( t - ( i L + k ) T _ { c } ) \mathrm { c o s } ( 2 \pi f _ { 0 } t ) } \\ { \displaystyle + b _ { i } W _ { \mathrm { Q } _ { j ^ { \prime } , i } , k } p ( t - ( i L + k ) T _ { c } ) \mathrm { s i n } ( 2 \pi f _ { 0 } t ) \} ( 3 } \end{array}
$$

其中： $W _ { { \textsc { l } } _ { j , i } , { \bf k } } \setminus W _ { Q _ { j ^ { \prime } , i } , { \bf k } }$ 分别代表由 $d _ { I , i }$ 和 $d _ { \ Q , i }$ 映射后的 PN 码组合;$j$ 、 $j ^ { \prime }$ 代表PN码组的索引值；另外， $B$ 代表传输时隙的个数；$L$ 为 PN 码组的码长； $f _ { 0 }$ 为载波频率； $p \big ( t \big )$ 为矩形脉冲成型函数；码片长度为 $T _ { c }$ 。

# 2 PN 码组映射方式

方案中PN 码映射的同相部分与正交部分，均需要查找索引表选择激活的PN码组。两部分原理一致，这里只阐述同相部分。

假设系统使用的 PN 码个数 $N _ { t } = 5$ ，且同相支路每个传输时隙同时激活PN码个数 $N _ { u } = 2$ ，则可以产生$N _ { c } { } ^ { \prime } \mathrm { = } \binom { N _ { t } } { N _ { u } } \mathrm { = } \binom { 5 } { 2 } \mathrm { = } 1 0$ 种组合，因此该系统可以映射的信息比特个数为 $n = \log _ { 2 } ( N _ { c } ) { = } \lfloor \log _ { 2 } ( 1 0 ) \rfloor { = } 3$ ，需要使用的PN 码组合的个数为 $N _ { c } { = } 8$ 。依据排列组合规律，PN 码组索引表如表1所示。

表1PN码组索引表  

<html><body><table><tr><td>同相 PN码映射块（d,)</td><td>PN 码组索引（编号)</td></tr><tr><td>000</td><td>W = W + W2</td></tr><tr><td>001</td><td>W2 = W1 + W3</td></tr><tr><td>010</td><td>W3 = W1 + W4</td></tr><tr><td>011</td><td>W4 = W1 + W5</td></tr><tr><td>100</td><td>W5 = W2 + W3</td></tr><tr><td>101</td><td>W6 = W2 +W4</td></tr><tr><td>110</td><td>W = W2 + W5</td></tr><tr><td>111</td><td>W8 = W3 + W4</td></tr></table></body></html>

# 3 接收机模型

GCIM方案接收机模型见图2。由于无线信道的随机性，在发射端信号到达接收端的过程中，可能会受到衰落的影响，所以接收端信号可以表示为

$$
\mathbf { r } ( t ) = h ( t ) * y ( t ) + u ( t )
$$

其中： $h ( t )$ 代表信道系数； $*$ 表示卷积； $u ( t )$ 代表均值为0、方差为 $n _ { 0 }$ 的加性高斯白噪声。假设信号受到平坦型瑞利衰落的影响，且在接收端已知理想的信道状态信息。

由于接收端的同相支路与正交支路具有相似的结构，下面只分析同相支路。经过理想的载波恢复后，同相支路的基带信

号可以表示为

$$
I ( t ) = \sum _ { i = 1 } ^ { B } \sum _ { k = 1 } ^ { L } h _ { i } ( t ) a _ { i } W _ { I _ { j , i } , k } p ( t - ( i L + k ) T _ { c } ) + u _ { I } ( t )
$$

其中： $u _ { I } ( t )$ 代表同相支路的加性高斯白噪声。

![](images/98e3271b62e7edcc7417e0bc037d81696abc17a4075a992d92f87f95ef5fb78f.jpg)  
图2GCIM接收机模型

经过信道补偿后，同相信号并行与 $N _ { c }$ 个PN码组进行相关运算，并在一个信号周期 $T = L T _ { c }$ 内求和。因此同相支路第 $\hat { j }$ 个分支在第 $i$ 个时隙的输出可以表示为

$$
I _ { \hat { \jmath } , i } = \sum _ { k = 1 } ^ { L } ( \left| h _ { i } \right| ^ { 2 } a _ { i } W _ { I _ { j , i } , k } W _ { I _ { \hat { \jmath } , i } , k } + h _ { i } W _ { I _ { \hat { \jmath } , i } , k } u _ { I , \hat { \jmath } , \mathrm { i } } )
$$

式（6）可以进一步表示为

$$
\begin{array} { r } { I _ { \hat { \jmath } _ { j , i } } = \left\{ \begin{array} { l l } { \pm \frac { \left| h _ { i } \right| ^ { 2 } E _ { s } } { 2 } + \nu _ { \hat { \jmath } , i } \qquad } & { j = \hat { \jmath } } \\ { \pm \left| \mathrm { h } _ { i } \right| ^ { 2 } E _ { p } + \nu _ { \hat { \jmath } , i } \qquad } & { j \neq \hat { \jmath } } \end{array} \right. } \end{array}
$$

其中： $\textstyle E _ { s } / 2 = \sum _ { k = 1 } ^ { L } W _ { j , k } ^ { 2 }$ 代表同相支路PN 码组的能量； $E _ { \mathfrak { p } }$ 表示发射端使用PN 码组与第 $\hat { j }$ 个分支PN 码组中存在相同 PN 码时，相同 PN 码的能量的和； $\nu _ { \hat { j } , i } = \sum _ { k = 1 } ^ { L } ( h _ { i } W _ { I _ { \hat { j } , i } , k } u _ { I , \hat { \bf j } , \mathrm { i } } )$ 代表相关噪声；且 $h _ { i }$ 表示第 $i$ 个传输时隙的信道系数。

然后对比 $N _ { c }$ 条分支输出值的绝对值，并找出最大值，表达式如下：

$$
J = \arg \operatorname* { m a x } _ { \hat { j } } \left\{ \left| I _ { \hat { j } , i } \right| \right\} \hat { j } \in \left\{ 1 , 2 , . . . N _ { c } \right\}
$$

其中： $J$ 表示检测出的同相支路的PN码组的索引；同理检测出正交支路 PN 码组的索引 $J ^ { \prime }$ 。将索引值对应的输出值 $\mathrm { ~ I } _ { J , i }$ 和$\mathbf { Q } _ { J ^ { \prime } , i }$ 解扩并得出调制符号的实部 $\hat { a } _ { i }$ 和虚部 $\hat { b _ { i } }$ ，再经过解调得出调制部分的信息比特 $\hat { d } _ { M - a r y , i }$ 。随后 $J$ 和 $J ^ { \prime }$ 分别通过反向查找索引表，解映射出信息比特 $\hat { d } _ { { \scriptscriptstyle I } , i }$ 和 $\hat { d } _ { \textsc { q } , i }$ 。最后通过并串转换得到信息比特 $\hat { \pmb { d } } _ { i }$ 。

# 4 分析与仿真

本章将对GCIM进行索引资源分析并采用蒙特卡罗仿真验证方案的性能，再与CIM方案进行对比。PN码为 $L { = } 6 4$ 位的Walsh码。仿真环境有两种，分别为加性高斯白噪声（AWGN)信道和平坦型瑞利衰落信道。且衰落信道的多普勒频移为160$\mathrm { H z }$ ，平均信道增益为 $0 \mathrm { d B }$ 。仿真图中的信噪比表示 $E _ { \mathrm { b } } / N _ { \mathrm { 0 } }$ ，其中 $\scriptstyle { E _ { \mathrm { b } } = E _ { \mathrm { s } } / \mathrm { m } }$ 表示传输符号中每个调制比特的信号能量。每个仿真图的主要参数均在图中左下角列出：从左至右依次代表方案名称、基带调制阶数、方案使用PN码的个数和每个传输时隙同相或正交部分使用的PN码个数。

![](images/c8b4dbc44eaaf79d6baf3eeed27c5656304e9623665645ec77405187a574eb18.jpg)  
图3相同传输比特时，不同方案PN码资源使用对比

图3为相同传输比特时，GCIM（ $\mathrm { N } _ { \mathrm { u } } { = } 2$ ）、GCIM（ $\mathrm { N } _ { \mathrm { u } } { = } 3$ ）和CIM方案索引资源使用情况对比，且各方案均采用4PSK调制。当频谱效率为 $1 2 ~ \mathrm { b i t / s / H z }$ 时，CIM需要使用32个PN码，而GCIM（ $\mathrm { N } _ { \mathrm { u } } { = } 2$ ）则需要使用9个PN码，GCIM（ $\mathrm { N _ { u } } { = } 3$ ）需要使用7个PN码。当频谱效率增至 $1 4 ~ \mathrm { b i t / s / H z }$ 时，CIM需要使用的PN 码数增至64个，GCIM（ $\mathrm { N _ { u } } { = } 2$ ）需要使用的PN 码数则增至12个，GCIM( $\mathrm { N _ { u } } { = } 3$ )需要使用的PN 码数增至9个。因此，相同频谱效率时，GCIM比CIM使用更少的PN码资源，且频谱效率越高，同相或正交支路每个传输时隙使用的PN 码个数 $N _ { \mathfrak { u } }$ 越大，效果越明显。

![](images/7f57797cbfa154399721db7a47bd17b1e89c427463651d269fad9bbbc3157fcf.jpg)  
图4不同参数配置时，GCIM与CIM在AWGN信道中的误比特率性能对比

GCIM与CIM两方案在AWGN信道和平坦瑞利衰落信道的BER性能分别如图4、5所示，且图4与5中相同序号的曲线参数配置均相同，仅仿真环境不同。

曲线 $\textcircled{1}$ 和 $\textcircled{4}$ 的频谱效率均为8bit/s/Hz。GCIM比CIM少使用了3个PN码，但在AWGN信道中误比特率为 $1 0 ^ { - 5 }$ 时，性能差了约2dB。在瑞利衰落信道中误比特率约为 $1 0 ^ { - 2 }$ 时，性能同样差了约 $2 ~ \mathrm { d B }$ 。通过增加两个调制方案中PN码的使用个数，曲线 $\textcircled{2}$ 和 $\textcircled{5}$ 的频谱效率均为 $1 0 ~ \mathrm { b i t / s / H z }$ 。GCIM比CIM少使用了9个PN码，但是在AWGN信道中误比特率为 $1 0 ^ { - 5 }$ 时，性能差了约2dB。在瑞利衰落信道中误比特率约为 $1 0 ^ { - 2 }$ 时，性能同样差了约2dB。通过增加两个调制方案中调制阶数，曲线 $\textcircled{3}$ 和$\textcircled{6}$ 的频谱效率均为 $9 ~ \mathrm { { b i t / s / H z } }$ 。GCIM比CIM少使用了3个PN码，在AWGN信道中误比特率为 $1 0 ^ { - 5 }$ 时，性能差了约 $2 \mathrm { d B }$ 。而在瑞利衰落信道中误比特率约为 $1 0 ^ { - 2 }$ 时，性能差了约1dB。

![](images/1d06c301fa78a6c8ebe25ea1ffa336b832dbe62b831434eb210b51d8a4576725.jpg)  
图5不同参数配置时，GCIM与CIM在瑞利衰落信道中的误比特率性能对比

另外，由曲线 $\textcircled{1}$ 、 $\textcircled{2}$ 和 $\textcircled{3}$ 可得，无论在AWGN信道还是在瑞利衰落信道中，GCIM通过增加PN 码的使用个数提升频谱效率比增加调制阶数时，误比特率更低。这是因为增加PN 码使用个数不会减小调制符号间的欧氏距离，而增加调制阶数时，则会明显减小符号间欧氏距离[8]。

![](images/ab6cf535f157689d09a9debd4686f790ea77bcc0051f6f1b11be81b5d586b16a.jpg)  
图6GCIM（ $N _ { u } { = } 2$ 、 $N _ { u } { = } 3$ ）与CIM在AWGN信道中的误比特率性能对比

图6、7中各方案的仿真环境分别为AWGN信道与平坦瑞利衰落信道，相同序号的曲线参数配置相同，且频谱效率均为$1 2 ~ \mathrm { b i t / s / H z }$ 。曲线 $\textcircled{2}$ 表示GCIM每个传输时隙的同相或正交部分，并行传输两个PN码。由曲线 $\textcircled{1}$ 和 $\textcircled{2}$ 对比可知，在AWGN信道中，误比特率为 $1 0 ^ { - 5 }$ 时，性能相差略大于 $2 ~ \mathrm { d B }$ ，而在瑞利衰落信道中，误比特率约为 $1 0 ^ { - 2 }$ 时，性能差了约1dB，但节省了23个PN码。曲线 $\textcircled{3}$ 表示GCIM每个传输时隙的同相或正交部分，并行传输3个PN码。由曲线 $\textcircled{1}$ 和 $\textcircled{3}$ 对比可知，在AWGN信道中，误比特率为 $1 0 ^ { - 5 }$ 时，性能相差约为4dB，而在瑞利衰落信道中，误比特率约为 $1 0 ^ { - 2 }$ 时，性能差了约2dB，但节省了25个PN码。因此，随着GCIM方案中，每个传输时隙同相或正交部分并行传输的 PN 码个数 $N _ { u }$ 的逐渐增加，需要使用的PN 码个数不断减小，但是误码率性能会有略微下降。

![](images/0d696291ecbb1769add24b5f24a91563461575165cecfe7bdde69e8dadca4452.jpg)  
图7GCIM（ $N _ { u } { = } 2$ 、 $N _ { u } { = } 3$ ）与CIM在瑞利衰落信道中的误比特率性能对比

另外，当GCIM与CIM使用相同个数的PN码时，GCIM的频谱效率明显增加。假设一个调制符号内传输每个调制比特的能量为 $E _ { \mathrm { { b } } }$ ，通过增加PN码映射部分的信息比特，平均每个信息比特耗费的传输能量减小，因此GCIM的传输能量效率优于 $\mathrm { C I M ^ { [ 8 ] } }$ 。当然付出的代价同样是误比特率性能的略微下降。

# 5 结束语

本文以码索引调制为基础，并结合并行组合扩频调制的思想，提出广义码索引调制。在一个传输时隙中，同相或者正交部分的映射比特可以映射为一组PN 码，增加了映射比特的数目，有效提升了系统的PN码利用率和信息传输速率。对比分析可知，相同频带利用率时，GCIM比CIM使用更少的PN码资源，且频带利用率越高，优势越明显。仿真分析表明，相同频谱效率时，GCIM在高斯信道中误比特率为 $1 0 ^ { - 5 }$ 时的性能比CIM差了约 $2 ~ \mathrm { d B }$ 。另外，随着GCIM中一个传输时隙激活的PN码个数 $\boldsymbol { N } _ { u }$ 增加，相对与CIM节约的PN码资源越明显，同时也会带来误码率性能的略微下降。由于本文在仿真过程中只考虑了较为理想的高斯信道和平坦瑞利衰落信道，实际通信中往往存在多径瑞利衰落、多用户等复杂情况，针对以上情况的GCIM的误码率性能分析以及解调算法的改进将是笔者下一步研究的重点。

# 参考文献：

[1]朱运航，张平华，邓明元．直接序列扩频通信系统性能研究[J].兵工自动化,2013,32(2):84-87.[2]俞斌，王炼红，贾雅琼．基于改进混沌扩频序列的多用户混沌扩频通信

系统的研究与仿真[J].计算机应用研究,2013,30(4):1161-1165.   
[3]Basar E.Index modulation techniques for 5G wireless networks [J].IEEE Communications Magazine,2016,54(7): 168-175.   
[4]Datta T,Eshwaraiah H S,Chockalingam A.Generalized space and frequency index modulation [J].IEEE Trans on Vehicular Technology,2016, 65 (7): 4911-4924.   
[5]Basar E.On multiple-input multiple-output OFDM with index modulation for next generation wireless networks [J]. IEEE Trans on Signal Processing, 2016,64(15): 3868-3878.   
[6]Kaddoum G,Ahmed M,Nijsure Y.Code index modulation: a high data rate and energy efficient communication system [J].IEEE Communications Letters,2015,19(2): 175-178.   
[7]Kaddoum G,Soujeri E.On the comparison between code index modulation and spatial modulation techniques [C]//Proc of International Conference on Information and Communication Technology Research.Abu Dhabi:IEEE Press,2015:24-27.   
[8]Kaddoum G,Nijsure Y,Tran H.Generalized code index modulation technique for high data rate communication systems [J].IEEE Trans on Vehicular Technology,2016,65(9): 7000-7009.   
[9]高红涛，王振玉，齐军．多进制扩频系统性能分析与仿真[J].无线电 工程,2007,37(8):22-24.   
[10]夏高峰，罗宇，金哲仕．多进制直接序列扩频系统性能分析及仿真[J]. 航空电子技术,2015,46(2):12-15.   
[11]洪亮，云颖．一种多进制扩频通信基带接收的实现方法[J]．无线电通 信技术,2015,41(4):104-107.   
[12] Liu Mingduo, Qu Zhaowei, Guo Lili. Improved parallel combinatory spread spectrum communication system [C]//Proc of International Computer Conference on Wavelet Active Media Technology and Information Processing. Chengdu: IEEE Press,2016:277-280.   
[13]Qi Lin,Guo Lili,Jiang Xiaofei.Performancestudiesof UWB communication system based on parallel combinatory spread spectrum [C]// Proc of International Conference on Wireless Communications,Networking and Mobile Computing.[S.1.] : IEEE Press,2009:1-4.   
[14]齐琳，郭黎利，姜晓斐．基于脉冲调制的并行组合扩频通信系统性能研 究[J].计算机应用研究,2011,28(6):2286-2288,2296.   
[15]李北明，王俊，薛伟，等．基于循环映射算法的并行组合扩频通信[J]. 系统工程与电子技术,2016,38(7):1654-1659.