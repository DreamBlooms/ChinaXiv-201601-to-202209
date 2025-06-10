# SCMA与极化码的联合检测译码技术\*

符杰林，张剑波，王俊义

(桂林电子科技大学 认知无线电与信息处理教育重点实验室，广西 桂林 541004)

摘要：将极化码与 SCMA多址系统相结合，并针对传统的独立检测译码方案（independent detection and decoding，IDD）因缺乏对译码输出信息的再利用而导致系统性能不佳的问题，提出了 SCMA以及极化码联合检测译码方案(jointdetection and decoding,JDD),该方案在接收端借助译码获得的内信息辅助更新 SCMA多用户检测器的初始先验信息，在检测器与译码器之间实现软信息的回溯迭代，从而得到更显著的系统性能增益。仿真结果表明采用了JDD方案的系统性能相比IDD方案得到了显著的提升，误码率相较IDD方案提升了大约2dB。

关键词：极化码；稀疏码分多址；联合检测译码；性能增益 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2018.03.0176

# Joint detection and decoding scheme for SCMA system with polar codes

Fu Jielin, Zhang Jianbo, Wang Junyi† (KeyLaboratoryof CognitiveRadio&Information Processing Information Processing,Guilin Universityof Electronic Technology, Guilin Guangxi 541004, China)

Abstract: This paper combined the SCMA and Polar Codes and proposed a joint SCMAdetection and Polar decoding (JDD) scheme forthe system.The independent SCMAdetectionand Polardecoding(IDD)sheme is unable to take fulladvantageof decoding information which leadtoapoorsystemperformance.Aimed atthis problem,the proposed JDDscheme canachieve asignificantperformance gain which iteratively exchanges thesoft informationbetwen thedetectorand thedecoder by using intrinsic informationtoupdatethe initialpriori probabilitiesinSCMAdetector.Simulationresultsshowthat,theperformance ofthe system with JDDscheme has been significantly improved which obtain about 2dB performance gaincompared with the IDD scheme.

Key words: Polar Codes; Sparse code multiple access; joint detection and decoding; high performance gain

# 0 引言

2009年Arikan[1]首次详细阐述了信道极化现象，并基于该现象提出了极化码编码理论。极化码有明确的编码方案，是一类被严格证明在二元离散无记忆信道下（binary-discretememorylesschannel，B-DMC）可达香农容限的信道编码理论，同时还具有编译码复杂度低的优势。因为极化码优良的容量可达性能，在2016年被3GPP正式讨论通过成为5GeMBB场景下控制信道部分的最终编码方案。而有关极化码的研究也被广泛展开，在极化码译码算法研究领域Arikan基于极化码特殊的编码结构提出了串行抵消（successive cancelation,SC）[1]译码算法，随后串行抵消列表（successive cancelation list,SCL）[2]、CRC-SCL[3]等众多针对 SC的改进译码算法也相继被提出。同时考虑到SC等算法在吞吐量以及低时延等方面的不友好性，提出了基于极化码的置信传播（belief propagation,BP）译码算法[4]，从而使得信息能够以并行的方式在因子图两端迭代更新，并在译码时延和吞吐量方面获得了优异的性能。

稀疏码分多址技术(sparse code multiple access,SCMA)[5]作为一种前景广阔的5G无线空口技术，在设计上能在各种应用场景满足大量的用户连接数，并且拥有远高于4G的数据传输速率。是未来潜在的5G优秀备选多址技术方案之一。SCMA多址技术是基于LDS-CDMA[技术发展而来，在传输过程中将高维调制技术和稀疏扩频技术相融合，直接将编码后的交织比特数据流映射为预先设定在码本里的复数域多维码字，并在接收端进行多用户检测分离，从而获得更高的过载率。在接收端采用最大后验估计算法（maximumaposteriori probability,MAP）可以获得最优的检测性能，同时难以实现的复杂度也限制了MAP算法在SCMA中的应用。得益于SCMA系统中的稀疏码字结构，针对MAP算法的高复杂度，在接收端采用消息传递算法（message passingalgorithm，MPA）[7]能够在保证性能损失较小的基础上有效降低检测的复杂度。

作为5G标准下优秀的多址技术方案以及信道编码方案，本文将SCMA多址技术与极化码编码技术相结合。为了进一步提高系统性能，获得更低的误码率，本文在接收端采用SCMA以及极化码联合检测译码方案（JDD)。该方案将译码输出的软信息与SCMA检测输出信息进行数学操作，提取出内信息即先验信息，并回溯更新SCMA检测器的初始用户先验信息，通过一定次数的迭代更新使得系统性能获得明显增益。解决了传统的独立检测译码方案（IDD）性能提升不明显的问题。

# 1 系统简介

如图1所示为简化的上行Polar-SCMA多址系统，其中系统中用户数为 $J$ ,资源块数为 $F$ 。每个用户同时分布在不同的资源块上，且每个资源块叠加不同的用户数据，完成用户与资源块的过载增益。对于用户 $J$ ， $\kappa$ 个信息比特经过极化编码后生成 $N$ 个编码比特 ${ \mathbf b } _ { J }$ ，且码率定义为 $R = K / N$ 。为了减少系统中因突发错误带来的干扰，编码比特 ${ \mathbf b } _ { J }$ 经由交织模块产生交织比特数据 $\mathbf { c } _ { J }$ 并送入 SCMA 编码模块，交织比特数据 $\mathbf { c } _ { J }$ 中每9个比特数据集合 $\left\{ c _ { J } ^ { 1 } . . . c _ { J } ^ { q } \right\}$ 依次按照映射法则在 SCMA 码本中挑选$F$ 维码字进行叠加并送入信道，且映射法则为：$f ^ { J } : \mathbb { B } ^ { q }  X _ { J } \in \chi ^ { J } , | \chi ^ { J } | = M , q = \log _ { 2 } ( M )$ 。在接收端接收信号 $\textbf { y }$ 如下式：

$$
\mathbf { y } { = } \sum _ { \mathrm { j } = 1 } ^ { J } \mathrm { d i a g } ( \mathbf { h } _ { j } ) X _ { j } + \mathbf { z }
$$

其中:接收信号 $\mathbf { y } = ( y _ { 1 } , y _ { 2 } . . . , y _ { F } ) ^ { \mathrm { T } }$ ，用户 $j , j = 1 , 2 . . . , J$ 所在的信道信息 $\mathbf { h } _ { j } = ( h _ { \mathrm { j } } ^ { 1 } , h _ { j } ^ { 2 } , . . . , h _ { j } ^ { F } ) ^ { \mathrm { T } }$ ，经比特映射后的码字符号$X _ { j } = ( x _ { \mathrm { { j } } } ^ { 1 } , x _ { j } ^ { 2 } , . . . , x _ { j } ^ { F } ) ^ { \mathrm { { T } } }$ ， $\textbf { z }$ 为信道中的加性高斯噪声向量。

在用户数据送入极化编码之前要进行码构造，即进行信道可靠性估计。信道可靠性估计是对各子信道进行信道容量（信道容量越大，可靠性越高）计算排序，并将用户数据依次放入可靠性高的子信道上进行传输，其余子信道放入冗余数据（冻结比特)，最终得到用户传输数据 $u _ { 1 } ^ { \scriptscriptstyle N }$ 。目前进行信道可靠性估计的方法有蒙特卡罗法[8],密度进化法[9]以及高斯估计法[10]。

![](images/f896e2371955ed6ff9e19efa03c27ac6b411055d9a9a1540d8f5e14a036fd20c.jpg)  
图1Polar-SCMA简化上行多址系统

在文献[1]中极化码可表示成 $( N , K , A , u _ { { A } _ { c } } )$ 的形式，其中 $\kappa$ 为信息比特长度， $N$ 表示为编码后的比特序列长度， $A$ 表示编码后序列中信息比特所在的子信道位置信息集合而 $u _ { _ { A _ { c } } }$ 表示冻结比特的值，一般冻结比特的值设为0。极化码的编码过程如下式：

$$
b _ { 1 } ^ { N } = u _ { 1 } ^ { N } G _ { N } = u _ { 1 } ^ { N } F ^ { \otimes n } B _ { N }
$$

其中: $N = 2 ^ { n }$ ， $\boldsymbol { u } _ { 1 } ^ { N } = \left\{ u _ { 1 } , u _ { 2 } , . . . , u _ { N } \right\}$ 为用户传输数据，编码后序列$\boldsymbol { b } _ { 1 } ^ { N } = \left\{ b _ { 1 } , b _ { 2 } , . . . , b _ { N } \right\}$ ， $B _ { { } _ { N } }$ 表示比特翻转操作，而 $\boldsymbol { F } ^ { \otimes n }$ 表示矩阵 $F$ 的Kronecker积，且F $F \triangleq { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 1 } & { 1 } \end{array} \right] }$

# 2 基础算法介绍

本节主要介绍基于MPA的SCMA多用户检测算法以及极化码BP译码算法，MPA算法以及BP译码算法是联合检测译码算法（JDD）的基本组成模块。由图1可看出，译码（BP)输出信息被重新回溯至SCMA检测模块（MPA)，两者组成的信息回溯迭代结构是JDD算法的核心构成。

# 2.1 SCMA检测算法

a）初始化，由于缺少码字的先验信息，初始化时关于码字符号 $\mathbf { X } _ { j } ^ { m }$ ，节点VN传递给节点FN的信息都假设为等概发送，令第 $j$ 个用户节点传递给第 $f$ 层功能节点的信息为 $V _ { j  f } ( \mathbf { X } _ { j } ^ { m } )$ ，即：

$$
V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) = 1 / M , m = 1 , 2 , . . , M
$$

b）初始化后，利用接收到的信号 $\boldsymbol { y } _ { f }$ 以及信道信息 $h _ { f }$ ，令第 $f$ 层功能节点传递给第 $j$ 个用户节点的信息为 $U _ { f  j } ( \mathbf { X } _ { j } ^ { m } )$ ，则消息的更新方式如下：

$$
\begin{array} { l } { { \displaystyle U _ { _ { f  j } } ( { \bf X } _ { j } ^ { m } ) = } } \\ { { \displaystyle \sum _ { { \bf x } _ { p } \in \{ \chi \} } \displaystyle \frac { 1 } { \pi N _ { 0 } } \exp \Biggl [ - \frac { 1 } { N _ { 0 } } \biggl \| y _ { f } - h _ { j j } x _ { j j } - \sum _ { p \in \hat { \mathcal { X } } \backslash j } h _ { f p } x _ { f p } \biggl \| ^ { 2 } \Biggl ] \prod _ { p \in \hat { \mathcal { X } } \backslash j } V _ { j  f } ( { \bf x } _ { p } ) } } \end{array}
$$

上式中 $\partial f \backslash j$ 表示除了用户节点 $j$ 外所有与功能节点 $f$ 相连的用户节点集合，其中 $\mathbf { x } _ { p } \in \{ \chi \} \triangleq \chi _ { p _ { 1 } } \times \chi _ { p _ { 2 } } . . . \times \chi _ { p _ { d j - 1 } }$ ，且$p _ { 1 } , p _ { 2 } , . . . p _ { d f - 1 } \in p \in \partial f \setminus j$ ，表示该 $\partial f \backslash j$ 集合下所有可能码字的组合。

而 $d f$ 表示同一资源层叠加的用户数。

c） $V _ { j  j } ( \mathbf { X } _ { j } ^ { m } )$ 信息更新如下：

$$
V _ { j  f } ^ { } ( \mathbf { X } _ { j } ^ { m } ) = p ( \mathbf { X } _ { j } ^ { m } ) \prod _ { r \in \partial j \backslash f } ^ { } U _ { r  j } ^ { } ( \mathbf { X } _ { j } ^ { m } )
$$

$$
V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) = N o m a l i z e ( V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) )
$$

为了防止数据溢出，需要在 $V _ { j  f } ( \mathbf { X } _ { j } ^ { m } )$ 更新完后对 $V _ { j  f } ( \mathbf { X } _ { j } ^ { m } )$ 进行归一化操作。

d)在经过数次迭代后，节点VN输出每个用户的符号概率值经比特概率转换后送入译码模块：

$$
V _ { j } ( \mathbf { X } _ { j } ^ { m } ) = p ( \mathbf { X } _ { j } ^ { m } ) \prod _ { f \in \hat { \sigma } j } U _ { f  j } ( \mathbf { X } _ { j } ^ { m } )
$$

# 2.2极化码译码算法

极化码的BP译码算法[11过程需要借助如图2所示的因子图进行,图3为因子图的基本构成单元。每个计算单元由4个节点构成，每个节点被整数坐标(j,i)唯一标记，且$1 \leq j \leq N , 1 \leq i \leq n + 1$ 。 $j$ 和i分别表示因子图的行索引和列索引。同时每个节点包含两种信息：从右往左传递的信息（左信息）以及从左往右的信息(右信息)，两种信息分别表示为 $L _ { j , i }$ 和 $R _ { j , i }$ 。

![](images/1a66a47af3d7d4f402a8cde6fbf76cdf1ff017a156a644f779bf1b2d0626adab.jpg)  
图2Polar码BP 算法因子图 $( N = 8 )$

![](images/5dc13efe34a0f7f9ecc24b0977a52cc7320cfde217961e4b70db1dba7cfc6137.jpg)  
图3BP因子图基本构成单元

为了方便计算以及防止数据溢出，节点间传递的信息统一采用对数域的似然值进行计算。具体算法如算法1所示。初始化后左信息 $L _ { j , n + 1 }$ 向左更新到第1列，随后右信息 $R _ { j , 1 }$ 向右更新到第 $^ { n + 1 }$ 列，所有信息通过因子图迭代到预设值 $I _ { { } _ { B P } }$ 后输出序列比特的对数似然比。算法中函数 $f ( x , y ) = \ln ( ( 1 + x y ) / ( x + y ) )$ ，在实际仿真操作中为了减少计算复杂度函数可简化为$f ( x , y ) = 0 . 9 s i g n ( x ) s i g n ( y ) \operatorname* { m i n } ( | x | , | y | )$ 。

# Algorithm 1 Polar BP Decoding

# 1:Initialization :

$\begin{array} { r l } & { 2 : R _ { j , 1 } = \left\{ \begin{array} { l l } { 0 , j \in A } \\ { \infty , j \not \in A } \\ { 0 \not : L _ { j , n + 1 } = \displaystyle \ln \frac { p ( b _ { j } = 0 \not | y ) } { p ( b _ { j } = 1 \big | y ) } } \end{array} \right. } \end{array}$   
$4 { : }$ Iterative Decoding :  
${ \mathsf { S } } : { \mathsf { f o r l } } \leq i _ { B P } \leq I _ { { \scriptscriptstyle B P } } { \bf d o }$   
6:Lj=f（L2j-,Lj1+RN/  
7:Lj+N/2.i=f(Lj-Rj)  
8:R2j-1i+=f(jLji+R.）  
9:Rj1=f(L)+N  
10:end[0,Lj≥0  
11:output : j1,else$\hat { b } _ { j } = \left\{ { \begin{array} { l l } { 0 , L _ { j , n + 1 } + R _ { j , n + 1 } \geq 0 } \\ { 1 , e l s e } \end{array} } \right.$

# 3 联合检测译码算法

传统的独立检测译码方案（IDD）由于缺乏对译码信息的深度利用，所以译码性能仍有较大的增益空间。基于SCMA多址系统的联合检测译码算法已经有了一些不同程度的应用[12-15],本小节将联合检测译码算法（JDD）应用于基于极化码的SCMA多址系统中，通过重新利用译码的输出信息来回溯更新检测器的用户先验概率，获得出色的性能增益。

# 3.1概率转换模块

由式(7)可看出，SCMA检测器的输出为用户的符号概率，而译码模块的输入和输出都为用户的比特概率，所以在检测器和译码器之间需要进行概率转换，即将SCMA输出的用户符号概率转化为比特概率并送入译码器，而译码器的输出也要转化为先验符号概率并送入SCMA检测器更新符号概率 $V _ { j  j } ( \mathbf { X } _ { j } ^ { m } )$ 。为了简化数据计算，比特概率转换为对数域的似然比进行操作。令 $\scriptstyle l = N / q$ ，SCMA符号概率与译码输出的比特概率似然比的转化关系表示如下。

符号概率转换为比特概率似然比为 conver $\mathrm { t } ( \mathbf { P } _ { s } )  P _ { b }  L ( c _ { j } )$ ·

$$
P _ { b } ( c _ { j } ^ { ( l - 1 ) q + \nu } = B ) = \sum _ { \mathbf { x } _ { j } ^ { l m } \in \left\{ \mathbf { x } _ { j } ^ { l } \middle | c _ { j } ^ { \nu } = B \right\} } P _ { s } ( \mathbf { x } _ { j } ^ { l m } )
$$

$$
L ( c _ { j } ) = \ln \frac { P _ { b } ( c _ { j } = 0 ) } { P _ { b } ( c _ { j } = 1 ) }
$$

比特概率似然比转换为符号概率为

$$
\mathrm { c o n v e r t } ^ { - 1 } ( \mathrm { L } ( \mathrm { c } _ { j } ) ) \to P _ { b } \to P _ { s } :
$$

$$
\{ \begin{array} { l l } { P _ { b } ( c _ { j } = 0 ) = \exp ( L ( c _ { j } ) ) \big / ( 1 + \exp ( L ( c _ { j } ) ) )  } \\ {  P _ { b } ( c _ { j } = 1 ) = 1 - P _ { b } ( c _ { j } = 0 )  } \end{array} 
$$

$$
P _ { s } ( \mathbf { x } _ { j } ^ { l m } ) = \prod _ { \nu = 1 } ^ { q } P _ { b } ( c _ { j } ^ { ( l - 1 ) q + \nu } = B )
$$

其中： $B = \left\{ 0 , 1 \right\}$ ， $\nu = 1 , 2 , . . . q$ ， $\mathbf { x } _ { j } ^ { l } \in \left\{ \mathbf { x } _ { j } ^ { l } \left| c _ { j } ^ { \nu } \right. \right\}$ 为用户 $j$ 的映射比特集合中第 $\nu$ 位为 $B$ 的码字集合。

# 3.2联合检测译码结构

本小节详细介绍基于Polar-SCMA系统的联合检测译码算法结构，该结构的主要构成及流程如图4所示。

![](images/c68b61b5b6d05c45f637bf88887159faf460abedcbd7365c88350da1eea4681b.jpg)  
图4联合检测译码结构

其中Converter 模块已在上小节中通过式（8-11）做了详细推导。为了简化数据计算，概率值全部基于对数域进行操作。令 SCMA检测器的输出为 $L ( \mathbf { x } _ { j } ^ { l } )$ ,经过概率转换，符号似然比$L ( \mathbf { x } _ { j } ^ { l } )$ 变为比特似然比 $L ( c _ { j } )$ ，且 $L ( c _ { j } )$ 的定义由下式给出：

$$
L ( c _ { j } ) = \ln \frac { P ( c _ { j } = 0 \big | y ) } { P ( c _ { j } = 1 \big | y ) }
$$

由贝叶斯公式我们可将等式（12）变形为：

$$
\begin{array} { c c c } { { L ( c _ { j } ) = \displaystyle \ln \frac { P ( y | \boldsymbol { c } _ { j } = 0 ) } { P ( y | \boldsymbol { c } _ { j } = 1 ) } + \ln \frac { P ( c _ { j } = 0 ) } { P ( c _ { j } = 1 ) }  } } \\ { {  = L ^ { i } ( c _ { j } ) + L ^ { p } ( c _ { j } )  } } \end{array}
$$

从式（13）可以看出 $L ^ { i } ( c _ { j } )$ 为SCMA检测器产生的外信息，随后经过解交织送入译码模块，而 $L ^ { \boldsymbol { p } } ( c _ { j } )$ 为比特 $c _ { j }$ 的先验概率，且 $L ^ { \boldsymbol { p } } ( c _ { j } )$ 是由相应的译码模块在上一次迭代中计算产生。值得注意的是SCMA初始化输出时比特概率设定为等概，所以$L ^ { \boldsymbol { p } } ( c _ { j } ) = 0$ ，即没有任何先验信息。根据图4定义Transform变换为 $L ^ { \boldsymbol { p } } ( b _ { j } ) = \mathrm { T r a n s f o r m } ( L ( c _ { j } ) )$ ， $L ^ { p } ( c _ { j } ) { = } \mathrm { T r a n s f o r m } ^ { - 1 } ( L ( b _ { j } ) )$ 。具体的联合检测译码算法如算法2所示。

# Algorithm 2 Joint Detection and Decoding

1:Initialization :   
$2 : V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) = 1 / M$   
3: Joint Detection and Decoding :   
$\begin{array} { r l } & { \quad + \mathrm { 1 0 r o r 1 } \simeq I _ { 0 } \mathrm { { s } } I _ { 0 } { \mathrm { { a } } } 0 { \mathrm { { a } } } } \\ & { \quad > \mathrm { { : f } } \mathbf { { o r l } } \leq i _ { s } \leq I _ { s } \mathrm { { d } } { \mathrm { { o } } } } \\ & { \quad 6 : U _ { f  j \mathrm { { o } } } ( \mathbf { X } _ { j } ^ { m } ) = } \\ & { \quad \quad \sum _ { { \boldsymbol { x } } _ { p } ^ { \prime } \in [ \chi ] } \frac { 1 } { \pi N _ { 0 } } \exp [ - \cfrac { 1 } { N _ { 0 } }  y _ { f } - h _ { g } x _ { \bar { p } } - \sum _ { p \in \mathcal { O } / \backslash } h _ { p } x _ { p }  ^ { 2 } ] \prod _ { p \in \mathcal { O } \backslash \mathcal { Y } } V _ { j  f } ( \mathbf { X } _ { p } ) } \\ & { \quad 7 : V _ { j  j \mathrm { { ' } } } ( \mathbf { X } _ { j } ^ { m } ) = p ( \mathbf { X } _ { j } ^ { m } ) \prod _ { p \in \mathcal { O } \backslash f } ( \mathbf { X } _ { j } ^ { m } ) } \\ & { \quad 8 : V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) = N o m a l i z e ( V _ { j  f } ( \mathbf { X } _ { j } ^ { m } ) ) } \end{array}$ 4:forl≤i≤1do   
9 :end for   
$\begin{array} { r l } & { | | \Phi _ { 1 } \rangle \langle \Phi _ { 1 } ^ { \prime } \rangle - p ( { \mathbf { { X } } } _ { 1 } ^ { \prime } ) | \sum _ { \substack { \ell = 0 } } ^ { \infty } \mathrm { i } N _ { \ell } ^ { \prime } \rangle | \prod _ { \ell = 0 } ^ { D } \left( { \mathbf { { X } } } _ { 2 } ^ { \prime } , \mathbf { \Lambda } _ { \ell } ^ { \prime } \right) } \\ & { | \mathbf { 1 } \rangle \cdot | \mathbf { 1 } \langle \mathbf { 1 } \rangle \mathbf { 1 } \rangle \left( \mathbf { 1 } \right) \mathrm { i } \rangle } \\ & { | | \mathbf { 2 } \cdot \hat { \mathbf { L } } _ { \mathrm { a n d } } ^ { \prime } \mathbf { c } \langle \mathbf { c } \langle \mathbf { c } \mathbf { \Lambda } _ { \ell } ^ { \prime } ( \mathbf { X } _ { 1 } ^ { \prime } ) \rangle \rangle } \\ & { | | \mathbf { 3 } \rangle \cdot p _ { \mathrm { i n d } } ^ { \prime } \left( \mathbf { { X } } _ { 2 } ^ { \prime } , \mathbf { \Lambda } _ { \ell } ^ { \prime } \right) } \\ & { | | \mathbf { 4 } \cdot | \mathbf { 5 } \pi | \mathbf { 1 } \langle \mathbf { 1 } \rangle \cdot p _ { \mathrm { i n d } } } \\ & { | | \mathbf { 5 } \cdot \hat { \mathbf { L } } _ { \mathrm { a } } \cdot p _ { \mathrm { i n } } ^ { \prime } \left( \mathbf { L } _ { 2 } ^ { \prime } , \mathbf { \Lambda } _ { \ell } ^ { \prime } , \mathbf { \Lambda } _ { \ell } ^ { \prime } + \hat { \mathbf { W } } _ { \mathrm { e { e } } } \mathbf { W } _ { \mathrm { e } } \mathbf { W } _ { \mathrm { e } } \right) } \\ & { | | \mathbf { 5 } \cdot \hat { \mathbf { L } } _ { \mathrm { a } } \cdot \left( \int U _ { 2 } \mathrm { i } \Phi _ { \mathrm { a } } ^ { \prime } L _ { 2 } \left( \mathbf { { X } } _ { 2 } ^ { \prime } , \mathbf { \Lambda } _ { \ell } ^ { \prime } \right) \right) } \\ & { | | \mathbf { 6 } \cdot \hat { \mathbf { L } } _ { \mathrm { b } } \cdot \mathbf { q } _ { \mathrm { a } } - f \left( L _ { 2 } \nu _ { \mathrm { a } } \mathbf { L } _ { \ell } \right) + L _ { 2 } \nu _ { \mathrm { a } } } \\ & { | | \cdot \mathbf { U } _ { 2 } \cdot \mathbf { a } _ { \mathrm { a } } - f \left( R _ { \ell } , L _ { 2 } \nu _ { \mathrm { a } } + R _ { \ell } \left( \mathbf { X } _ { 2 } ^ { \prime } \right) \right) } \\ &  | | \mathbf { 5 } \cdot \hat { \mathbf { U } } _ { \mathrm { b } } \cdot \mathbf { p } _  \mathrm  \end{array}$   
21:end for   
$2 2 : \mathbf { O u t p u t } : \hat { u } _ { j } = \left\{ 0 , L _ { { \scriptscriptstyle j , 1 } } \geq 0 \right.$

# 4 系统仿真分析

该节主要针对本文提出的联合检测译码方案（JDD）进行

性能仿真验证，并与传统的独立检测译码方案（IDD）进行误码性能的对比分析；其次在相同条件下，对不同码长下的系统性能进行仿真对比分析。

# 4.1系统参数设置

图5和6分别为高斯信道下设置码长为 $N = 2 5 6$ 以及$N = 1 0 2 4$ 时得到的误码性能仿真对比曲线图，且系统码率 $R = 0 . 5$ ，SCMA系统的对应稀疏矩阵为

$$
F _ { _ { s c m a } } = { \left[ \begin{array} { l l l l l } { 0 } & { 1 } & { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 1 } & { 0 } & { 0 } & { 1 } \\ { 0 } & { 1 } & { 0 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } & { 1 } & { 1 } & { 0 } \end{array} \right] }
$$

系统仿真参数主要针对IDD与JDD 两种算法进行设置，系统具体参数如表1所示。

表1系统仿真参数设置  

<html><body><table><tr><td>系统参数</td><td>IDD</td><td>JDD</td></tr><tr><td>SCMA检测迭代数Is</td><td>6</td><td>6</td></tr><tr><td>BP 译码迭代数IBP</td><td>18</td><td>18</td></tr><tr><td>系统外迭代数I</td><td>1</td><td>2、3、4</td></tr><tr><td>极化码构造方式</td><td></td><td>改进高斯估计法[16]</td></tr></table></body></html>

# 4.2 仿真结果分析

![](images/32916e6b148e9404373fda3e711de33602b365101674c62d57ae01634c40f10e.jpg)  
图5JDD与 IDD 的系统误码率曲线对比(256,128)

![](images/1cc2397c6b98845bfe46350c3bb7f2058faba1c345738813cd722a5177c5128e.jpg)  
图6JDD与 IDD 的系统误码率曲线对比(1024,512)

从图5和6可以看出,采用JDD联合检测译码方案的系统误码率明显要好于传统的IDD独立检测译码方案。从图5可看出，在码长 $N = 2 5 6$ ， $\scriptstyle I _ { o } = 4$ 的条件下，JDD方案相比IDD方案误码率提升大约 $1 . 5 \mathrm { d B }$ ；从图6可看出，在码长 $N = 1 0 2 4$ ， $\scriptstyle I _ { o } = 4$ 的条件下，JDD方案相比IDD方案误码率提升大约 $2 \mathrm { d B }$ 。

当 $\scriptstyle I _ { o } = 1$ 即迭代初始化时，由于SCMA检测器缺乏用户的先验概率信息，只能对所有用户都假设为等概发送，所以用户先验概率的缺失导致整体系统性能不佳；当 $\scriptstyle I _ { o } = 2$ 时利用联合检测译码算法，将从译码输出信息中提取的用户先验信息回溯至SCMA 检测器并实时更新用户的先验概率信息 $L ^ { \boldsymbol { p } } ( c _ { j } )$ ，使得检测器模块获得了真实可靠的用户先验概率信息，所以此时系统性能增益明显。码长 $N = 2 5 6$ 时系统增益接近1.3dB，码长$N = 1 0 2 4$ 时系统增益接近2dB。当 $\scriptstyle I _ { o } = 3$ 时，随着迭代次数的增加，回溯的用户信息之间的相关性逐渐增加，导致系统性能增益逐渐减小，当迭代次数 $\scriptstyle I _ { o } = 4$ 时采用JDD方案的系统性能增益逐渐趋于饱和。

![](images/0055a9f1139a6423d17e9821eefd9c62cd4f675e1fe14e60ddf7b5fef7d76455.jpg)  
图7极化子信道可靠性分布( $N = 2 5 6$ ）

![](images/9fc958dd906a511a5d00892e928fdb661c950fad9912d9fc6fa6f6db9abec968.jpg)  
图8极化子信道可靠性分布( $N = 1 0 2 4$ ）

极化码属于长码性能码，码长越长系统性能越佳。图7图8 分别为利用改进高斯估计法[16得出的码长 $N = 2 5 6$ 以及$N = 1 0 2 4$ 时极化子信道的可靠性分布状态。本文定义极化子信道的可靠性为 $\boldsymbol { z } ( i )$ ， $1 \leq i \leq N$ 。按照极化码理论：当码长 $N$ 趋于无限长时，子信道得到完全极化，即子信道的 $\boldsymbol { z } ( i )$ 值完全分布于0与1两端，且信道实现无差错传输。但由于实际仿真达不到理想状态，会有部分子信道的可靠性处于0与1之间，即$0 { < } \mathrm { z } ( m ) < 1$ ， $m \in { i }$ 。 $z ( m ) / N$ 所占比例越高系统性能越差，结合实际的仿真情况，本文令 $0 . 1 { < } \mathrm { z } ( m ) < 0 . 9$ 的子信道为不可靠信道，同时从图7与图8中进行仿真统计得到如下结果：

所以可以得出结论， $N = 1 0 2 4$ 时系统性能更好。结合图5和6可验证上述结论，从图5、6可对比看出码长 $N = 1 0 2 4$ 时的系统性能要明显优于 $N = 2 5 6$ 时的系统性能，整体系统性能增益约为 $1 ~ \mathrm { d B }$ 。

同时也可猜想得出 $N = 2 0 4 8$ 时，整体系统性能更好。

# 5 结束语

本文基于SCMA多址技术以及极化码编码理论，在将两者结合的前提下提出了联合检测译码方案（JDD)。研究结果表明联合检测译码方案(JDD)相比传统的独立检测译码方案(IDD)充分利用了迭代过程中的软信息，获得了明显的系统性能增益。

# 参考文献：

[1]Arikan E.Channel polarization: a method for constructing capacityachieving codes for symmetric binary-input memorylesschannels [J]. IEEE Trans on Information Theory,2009,55(7):3051-3073.   
[2]TalI, VardyA.List decoding ofPolar Codes[J].IEEE Trans on Information Theory,2015,61(5): 2213-2226.   
[3]Niu Kai, Chen Kai.CRC-aided decoding of polar codes [J].IEEE Communications Letters,2012,16 (10): 1668-1671.   
[4]Arikan E.A performance comparison of polar codes and Reed-Muller codes [J]. IEEE Communications Letters,2008,12(6): 447-449.   
[5] Nikopour H,Baligh H. Sparse code multiple access [C]// Proc of International Symposiumon Personal Indoorand Mobile Radio Communications.2013: 332-336.   
[6]HoshyarR,Wathan F P,Tafazolli R.Novel low-density signature for synchronous CDMA systems over AWGN channel[J]. IEEE Trans on Signal Processing,2008,56 (4): 1616-1626.   
[7]Kschischang FR,FreyBJ,Loeliger HA.Factor graphs and the sum-product algorithm[J]. IEEE Trans on Information Theory,2001,47(2): 498-519.   
[8]Arikan E. Channel Polarization: A method for constructing capacityachieving codes for symmetric binary-input memoryless channels [J]. IEEE Trans on Information Theory,2009,55(7): 3051-3073.   
[9]Mori R,Tanaka T.Performance ofpolar codes with theconstructionusing density evolution[J].IEEE Communications Letters,2009,13(7): 519-521.   
[10] Chung S Y,Richardson TJ, Urbanke RL.Analysis ofsum-product dcoding of low-density parity-check codes using a Gaussian approximation[J].IEEE Trans on Information Theory,2001,47(2): 657-670.   
[11] Yang Junmei, Zhang Chuan,Zhou Huayi,et al. Pipelinedbelief propagation polar decoders [Cl//Proc of IEEE International Symposium on Circuits and Systems. 2016: 413-416.   
[12]韩凯宁，张珍兵，胡剑浩，等．基于因子图的 SCMA和LDPC 联合检测 和译码[J].电子科技大学学报,2017,46 (5):685-691.(Han Kaining, Zhang Zhenbing,Hu Jianhao,et al.A factor graph based joint detection and decoding scheme for LDPC coded SCMA system[J].Journal of University of Electronic Science and Technology of China,2017,46 (5): 685-691)   
[13] Wu Yiqun, Zhang Shunqing, Chen Yan. Iterative multiuser receiver in sparse code multiple access systems [C]// Proc of IEEE International Conference on Communications.2015:2918-2923.   
[14] Zhang Zhenbing,Han Kaining,Hu Jianhao,et al. Joint detection and decoding schemes for turbo coded SCMA systems[C]// Proc of

GLOBECOM Workshops.2017:1-6.

[15] Xiao Baisen,Xiao Kexin,Zhang Shutian,et al.Iterative detection and decoding for SCMA systems with LDPC codes[C]//Proc of International Conference on Wireless Communications & Signal Processing.2015:1-5.

[16]Dai Jincheng,Niu Kai, Si Zhongwei,et al.Evaluation and Optimization of Gaussian Approximation for Polar Codes [J].Proceedings of the American Society for Information Science & Technology,2016,51(1):1-2