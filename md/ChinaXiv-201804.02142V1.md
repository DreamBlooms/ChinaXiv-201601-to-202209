# 基于GMD-DPC/THP的两组Alamouti非线性预编码系统

尚应博」，赵悠悠1，穆晓敏1，张建康1,2\*(1．郑州大学 信息工程学院，郑州 450001;2.东南大学 移动通信国家重点实验室，南京 210096)

摘要：针对 Alamouti空时块编码复用增益损失的问题，提出了两组Alamouti编码方案；在此基础上，为了改善系统的误码率(bit errorrate，BER）性能和简化接收端复杂度，提出将几何均值分解（geometric mean decomposition，GMD)算法和非线性预编码技术相结合的两组 Alamouti 传输方案。本方案的设计方法为：首先等效出两组 Alamouti空时块编码系统的信道矩阵；进而，通过GMD 算法对等效信道矩阵进行收发端联合设计；最后，在发射端应用脏纸（dirtypaper coding，DPC）和Tomlinson-Harashimaprecoding（THP）非线性预编码技术，消除发送信号间的干扰，从而使系统获得更好的误码率性能。通过仿真结果对比发现，提出的系统可以显著地改善误码率性能。

关键词：空时块编码；非线性预编码；几何均值分解；脏纸编码；等效信道 中图分类号：TN929.5 doi: 10.3969/j.issn.1001-3695.2018.01.0048

# Two-groups Alamouti nonlinear precoding system based on GMD-DPC /THP

Shang Yingbol, Zhao Youyou1, Mu Xiaomin1, Zhang Jiankang1, 2† (1.SchoolofInformationEnginering,Zhengzhou University,Zhengzhou45ooo1,China;2.NationalMobileCommunication Research Laboratory,Southeast University,Nanjing 21oo96,China)

Abstract: Inorder tosolve the problem of multiplexinggain lossin Alamouti space-time block coding,this paper proposed a two-groups Alamouti transmissionscheme.Onthisbasis,inordertoimprovethebiterrorratio(BER)withlowercomputational complexity atthereceiver,this paper proposed a two-groups Alamouti transmission scheme bycombining Geometric Mean Decomposition(GMD)algorithm and non-linear precoding technique.The design methodofthe proposed solutionconsists of three mainoperations.Firstlyobtainthefectivechannelmatrixoftw-groupAlamoutitransmisiosystems.Secondlyjointly design the transceiver with the obtained efective channel matrix by exploiting thegeometric mean decomposition(GMD) algorithm.Finally,mitigatethe inter-chanel interferencebyutilizing non-linear precoding techniques ofDirtyPaper Coding (DPC)and Tomlinson-Harashima Precoding (THP).The simulationresults demonstrate that the proposed scheme is capableof significantly improving the achievable BER performance.

Key words: space-time block coding; nonlinear precoding; GMD; dirty paper coding; equivalent channel

# 0 引言

多输入多输出（multiple input multiple output，MIMO）系统具有丰富的空间分集增益和复用增益，已被第四代无线通信系统（4G）采用，并成为第五代移动通信系统（5G）的基础技术之一。在分集增益的利用方面，典型的代表是Alamouti[提出的基于两副发射天线的空时码（space-time block coidng，STBC)，该传输方案通过在两幅发射天线上的前后两个时隙，设计空时正交的编码，使得接收端只需简单的线性处理，即可获得发送分集增益。但是，STBC传输技术在利用传输分集的同时，却丧失了空间复用增益。空间复用增益代表性技术是贝尔实验室提出的垂直分层空时编码（belllaboratorieslayeredspace-time,BLAST)传输方案，该方案充分利用空间复用增益，具有较高的发送速率，但却丧失了空间分集增益。

为了同时取得分集增益和复用增益，必须在可靠性和有效性之间进行折中。文献[2,3]提出空时块编码和空间复用技术相结合的混合传输系统。为了提高混合传输系统的误码率性能和系统的容量，并降低接收端的复杂度，文献[4\~7]设计了STBC-VBLAST混合预编码系统。预编码是指在下行链路中，基站通过反馈技术或者互易性原理，在获取信道状态信息（channelstate information，CSI）基础上对发送信号进行预处理。脏纸编码[8\~10]和 THP[11,12]是非线性预编码的代表技术，它们可以在基站端消除信号链路之间的干扰，简化接收端的运算复杂度并改善系统的误码率性能。

具体而言，文献[6,7]提出一种组间使用Alamouti 编码，组内使用BLAST编码的预编码方案。然而文献[6]在系统接收端采取QR分解和最大似然估计（maximumlikelihood，ML）算法进行检测，接收端计算复杂度较高。为降低运算复杂度，同时消除发送数据流的干扰，文献[7]提出将两组STBC系统的等效信道矩阵做QR分解并在基站端应用DPC和THP非线性预编码方案，有效地降低了接收端的计算复杂度，并改善了系统的BER性能。但是，文献[7]将有效信道矩阵进行QR分解容易受到上三角矩阵的较小对角元素的影响，将会形成较差子信道，因此，误码率性能的提升受到很大限制。

文献[13]中提出了几何均值分解算法辅助MIMO信道分解。GMD分解算法基本原理是将MIMO信道分解为多个相同的并行子信道，子信道之间可以取得相同的增益，将会克服个别较差子信道的影响，使系统取得更好的 BER 性能。针对文献[7]中 QR 分解容易产生较差子信道的问题，本文提出了将两组Alamouti系统的等效信道矩阵做GMD，有效地避免了较差子信道的产生。进而，本文利用DPC和THP非线性预编码技术消除链路之间的干扰，在降低接收端运算复杂度的同时，提升系统的接收性能。也有利用GMD-DPC/THP在其他系统的文献，如文献[14]等。符号说明： $( \cdot ) ^ { T }$ 代表转置， $\left( . \right) ^ { \ast }$ 代表共轭， $( \cdot ) ^ { H }$ 代表共轭转置。

# 1 系统模型

这一节首先阐述以基于LQ-DPC 的两组 Alamouti 非线性预编码系统模型，并以此为基础引出本文提出的GMDDPC/THP的两组Alamouti非线性预编码方案。本章分为等效信道和LQ-DPC 预编码方案两部分介绍基于LQ-DPC 的两组Alamouti非线性预编码系统模型。

![](images/683c7c46c8ab1f76d9a599bc61b46cab73361676e8482538d042bc8c662a901a.jpg)  
图1基于LQ-DPC 的两组Alamouti非线性预编码系统

# 1.1等效信道

基于LQ-DPC的两组Alamouti非线性预编码模型如图1所示。假设收发两端均已知CSI。 $N _ { t }$ 和 $N _ { r }$ 分别代表系统的发射天线数和接收天线数，下面我们以 ${ \cal N } _ { t } { = } 4 , { \cal N } _ { r } { = } 2$ 为例阐述基于LQ-DPC的两组Alamouti非线性预编码传输方案的操作。其中，系统模型中的 $\boldsymbol { s ^ { \prime } }$ 代表原始发送符号， $s$ 代表经过DPC预编码以后的发送符号，令 ${ \pmb S } ^ { ' } = [ s _ { 1 } ^ { ' } s _ { 2 } ^ { ' } s _ { 3 } ^ { ' } s _ { 4 } ^ { ' } ] ^ { T }$ 和 $\pmb { S } = \left[ s _ { _ 1 } \ s _ { _ 2 } \ s _ { 3 } \ s _ { 4 } \right] ^ { T } \circ \pmb { B }$ 代表反馈矩阵， $F$ 代表预编码矩阵， $\scriptstyle { \boldsymbol { X } }$ 代表 $s$ 经过预编码矩阵 $F$ 操作后的发送符号，即： $X { = } F S$ 。此外， $\scriptstyle { \mathbf { } }$ 可以进一步表达为$X { = } [ x _ { 1 } x _ { 2 } x _ { 3 } x _ { 4 } ] ^ { T }$ 。 $n _ { \mathrm { i } }$ 、 $n _ { 2 }$ 分别为标量的高斯白噪声， $\textbf {  { G } }$ 为接收端均衡器。 $H$ 为 $2 \times 4$ 维的独立同分布的平坦瑞利衰落信道矩阵，其可表示为

$$
\pmb { H } = \left[ \begin{array} { r r r r } { { h _ { 1 1 } } } & { { h _ { 1 2 } } } & { { h _ { 1 3 } } } & { { . } } \\ { { h _ { 2 1 } } } & { { h _ { 2 2 } } } & { { h _ { 2 3 } } } & { { . . . } } \end{array} \right. \ ( 1 )
$$

预编码后的发送符号 $\scriptstyle { \boldsymbol { X } }$ 经过两组Alamouti编码空时块编码后的发送符号矩阵可以表示为

$$
{ \overline { { \overline { { X } } } } } = { \left[ \begin{array} { l l } { x _ { 1 } } & { - x _ { 2 } ^ { * } } \\ { x _ { 2 } } & { x _ { 1 } ^ { * } } \\ { x _ { 3 } } & { - x _ { 4 } ^ { * } } \\ { x _ { 4 } } & { x _ { 3 } ^ { * } } \end{array} \right] }
$$

于是，接收信号 $Y$ 可表达为

$$
Y = H \overline { { X } } + \left[ n _ { 1 } \right. \quad ( 3
$$

$$
\pmb { Y } = \left[ \begin{array} { l l } { y _ { 1 } ^ { 1 } } & { y _ { 1 } ^ { 2 } } \\ { y _ { 2 } ^ { 1 } } & { y _ { 2 } ^ { 2 } } \end{array} \right]
$$

其中， $y _ { j } ^ { i } , \{ i , \ j \} = 1 , 2$ 是接收信号 $Y$ 中的元素， $j$ 代表接收端的天线序号， $i$ 代表接收的时刻序号。将式(1)(2)代入式(3)中，可将式（3）展开为

$$
\begin{array} { r l } & { y _ { 1 } ^ { 1 } = h _ { 1 1 } x _ { 1 } + h _ { 1 2 } x _ { 2 } + h _ { 1 3 } x _ { 3 } + h _ { 1 4 } x _ { 4 } + n _ { 1 } } \\ & { y _ { 1 } ^ { 2 } = - h _ { 1 1 } x _ { 2 } ^ { * } + h _ { 1 2 } x _ { 1 } ^ { * } - h _ { 1 3 } x _ { 4 } ^ { * } + h _ { 1 4 } x _ { 5 } ^ { * } + n . } \\ & { y _ { 2 } ^ { 1 } = h _ { 2 1 } x _ { 1 } + h _ { 2 2 } x _ { 2 } + h _ { 2 3 } x _ { 3 } + h _ { 2 4 } x _ { 4 } \quad ( 4 ) } \\ & { y _ { 2 } ^ { 2 } = - h _ { 2 1 } x _ { 2 } ^ { * } + h _ { 2 2 } x _ { 1 } ^ { * } - h _ { 2 3 } x _ { 4 } ^ { * } + h _ { 2 4 } x _ { 3 } ^ { * } + n _ { 2 } } \end{array}
$$

对 $y _ { 1 } ^ { 2 } , \ y _ { 2 } ^ { 2 }$ 分别取共轭，则接收信号可重新表达为

$$
\overline { { \boldsymbol { Y } } } = \left[ \begin{array} { l } { y _ { 1 } ^ { 1 } } \\ { \left( y _ { 1 } ^ { 2 } \right) ^ { * } } \\ { y _ { 2 } ^ { 1 } } \\ { \left( y _ { 2 } ^ { 2 } \right) ^ { * } } \end{array} \right] = \left[ \begin{array} { l l l l } { h _ { 1 1 } } & { h _ { 1 2 } } & { h _ { 1 3 } } & { h _ { 1 4 } } \\ { h _ { 1 2 } ^ { * } } & { - h _ { 1 1 } ^ { * } } & { h _ { 1 4 } ^ { * } } & { - h _ { 1 3 } ^ { * } } \\ { h _ { 2 1 } } & { h _ { 2 2 } } & { h _ { 2 3 } } & { h _ { 2 4 } } \\ { h _ { 2 2 } ^ { * } } & { - h _ { 2 1 } ^ { * } } & { h _ { 2 4 } ^ { * } } & { - h _ { 2 3 } ^ { * } } \\ { \frac { \omega } { H } } & { \frac { \omega } { H } } & \end{array} \right] \left[ \begin{array} { l } { x _ { 1 } } \\ { x _ { 2 } } \\ { x _ { 3 } } \\ { x _ { 4 } } \end{array} \right] + \left[ \begin{array} { l } { n _ { 1 } } \\ { n _ { 1 } ^ { * } } \\ { n _ { 2 } } \\ { n _ { 2 } ^ { * } } \\ { n _ { 2 } ^ { * } } \end{array} \right]
$$

# Y=HX (6

（204号 $\overline { { H } }$ 为两组 Alamouti 系统的等效信道矩阵， $N = \left[ n _ { 1 } { \ n } _ { 1 } ^ { * } { \ n } _ { 2 } { \ n } _ { 2 } ^ { * } \right] ^ { T }$ 为等效的噪声向量。

1.2 LQ-DPC

矩阵的LQ分解算法和QR分解算法本质上具有相同的分解特性。本小节将具体介绍基于LQ-DPC的两组Alamouti非线性预编码方案。设计流程主要可以分为以下三步操作：

a)将等效信道矩阵的共轭转置进行QR分解：

$$
\left( \overline { { { H } } } \right) ^ { H } = Q , \left( 7 \right.
$$

则 $\scriptstyle { \overline { { H } } } = R ^ { H } Q ^ { H }$ ，令 $\pmb { L } = \pmb { R } ^ { H }$ 。其中， $\varrho$ 是酉矩阵， $\pmb { { Q } } ^ { H } \pmb { { Q } } = \pmb { { I } } \circ \pmb { { L } }$ 为下三角矩阵，可以表示为

$$
\begin{array} { r } { \boldsymbol { L } = \left[ \begin{array} { l l l l } { \boldsymbol { l } _ { 1 1 } } & { \boldsymbol { 0 } } & { \boldsymbol { 0 } } & { \boldsymbol { 0 } } \\ { \boldsymbol { l } _ { 2 1 } } & { \boldsymbol { l } _ { 2 2 } } & { \boldsymbol { 0 } } & { \boldsymbol { 0 } } \\ { \boldsymbol { l } _ { 3 1 } } & { \boldsymbol { l } _ { 3 2 } } & { \boldsymbol { l } _ { 3 3 } } & { \boldsymbol { 0 } } \\ { \boldsymbol { l } _ { 4 1 } } & { \boldsymbol { l } _ { 4 2 } } & { \boldsymbol { l } _ { 4 3 } } & { \boldsymbol { l } _ { 4 4 } } \end{array} \right] ^ { - } } \end{array} ( \mathrm { 8 }
$$

令 $\pmb { G } = d i a g ( l _ { 1 1 } ^ { - 1 } , l _ { 2 2 } ^ { - 1 } , l _ { 3 3 } ^ { - 1 } , l _ { 4 4 } ^ { - 1 } )$ ，那么预编码矩阵 $F$ 和反馈矩阵$\pmb { B }$ 分别可以表示为

$$
\begin{array} { l } { { F = Q } } \\ { { \ } } \\ { { B = G L } } \end{array}
$$

b)DPC预编码的矩阵可通过如下推导获得：

$$
\begin{array} { c } { { S ^ { ' } - ( B - I ) S { = } S } } \\ { { S { = } B ^ { ' } { \supset } } } \end{array}
$$

将 $X { = } F S$ ，式 $( 9 ) \sim ( 1 1 )$ 代入式（6）中，则接收信号可以展开表达为

$$
\begin{array} { l } { { \overline { { { \cal Y } } } = \overline { { { \cal H } } } { \cal X } + { \cal N } } } \\ { { { } ~ = { \cal R } ^ { H } { \cal Q } ^ { H } { \cal Q } { \cal B } ^ { - 1 } { \cal S } ~ + } } \\ { { { } ~ = { \cal G } ^ { - 1 } { \cal S } ~ + { \cal N } } } \end{array}
$$

c）利用 $G$ 矩阵对接收信号进行均衡：

$$
\pmb { Y } ^ { ' } = \pmb { G } \overline { { \pmb { Y } } }
$$

可恢复出原始信号。

# 2 基于GMD-DPC/THP 的两组Alam outi 非线性预编码系统

式（8）中下的下三角矩阵 $L$ 的对角元素并不相同，物理含义上意味着MIMO系统里的各子信道之间具有不同的信噪比（signal-to-noiseratio，SNR)，因而各个子信道传输质量存在显著差别，对信道间干扰的消除带来难度，从而影响系统总的可达性能。针对于这一问题，本文提出将等效信道矩阵进行GMD分解，使子信道之间拥有相同的SNR，从而获得具有相同增益的子信道。这样便于消除信道之间的干扰，并可简化系统调制/解调和编码/解码等方案的设计，改善系统的误码率性能。

2.1基于GMD-DPC的两组Alamouti非线性预编码传输方案基于GMD-DPC 的两组Alamouti非线性预编码传输方案，如图2所示。

![](images/b5698e73d73a7a91f0de05faafe6a7a831172420092514ccfbb2841a14a2fff2.jpg)  
图2基于GMD-DPC的两组Alamouti非线性预编码系统

类似于第一章节的符号体系， $\boldsymbol { s ^ { \prime } }$ 代表原始发送符号， $s$ 代表经过DPC预编码以后的发送符号， $\textbf {  { B } }$ 为反馈矩阵， $F$ 代表预编码矩阵， $\scriptstyle { \boldsymbol { X } }$ 是S经过预编码矩阵 $F$ 的发送符号， $P ^ { H }$ 和 $\pmb { G }$ 都是接收端均衡器。此外，通过GMD算法[13]得到预编码矩阵$F$ 。具体而言，GMD算法的设计原理如下：

$$
\operatorname* { m a x } _ { Q , P } \operatorname* { m i n } _ { \begin{array} { c } { \left\{ r _ { i i } : 1 \leq i \leq K \right\} } \\ { \eta , P } \end{array} } \left\{ r _ { i i } : 1 \leq i \leq K \right\}
$$

条件： $\pmb { R } = \pmb { \mathcal { Q } } ^ { H } \pmb { H } \pmb { P } \Rightarrow \pmb { H } = \pmb { \mathcal { Q } } \pmb { R } \pmb { P } ^ { H }$

$$
\pmb { R } \in \mathbb { R } ^ { K \times K } , r _ { i j } = 0 , f o r
$$

$$
r _ { i i } \triangleq \left( \prod _ { n = 1 } ^ { K } \lambda _ { H , n } \right) ^ { 1 / K } > 0 , f o r 1 \leq i \leq K
$$

$$
\pmb { \mathcal { Q } } ^ { H } \pmb { \mathcal { Q } } = \pmb { P } ^ { H } \pmb { P } = \pmb { I } _ { \kappa }
$$

其中: $K$ 为信道矩阵的秩， $r _ { i i }$ 和 $r _ { i j }$ 分别是上三角矩阵 $\pmb { R }$ 的等对角元素和对角元素以外的上三角元素。其中，Q、P都是半酉矩阵， $\scriptstyle Q Q ^ { H } = P P ^ { H } = I$ ， $\textbf { \textit { I } }$ 为单位阵。 $\left\{ \lambda _ { H , n } \right\} _ { n = 1 } ^ { K }$ }K，是信道矩阵H的$K$ 个奇异值。从某种程度上，GMD分解算法可以看做是拓展的QR分解算法。

在获取MIMO信道矩阵GMD分解的基础上，基于GMD和DPC方案相结合的两组Alamouti传输技术可通过以下操作实现：

a）将等效信道矩阵的共轭转置矩阵进行GMD，

$$
\left( \overline { { H } } \right) ^ { H } = \mathfrak { L }
$$

则 $\scriptstyle { \overline { { H } } } = P R ^ { H } Q ^ { H }$ 。因此，预编码矩阵 $\pmb { F } = \pmb { Q }$ 。 $\pmb { R } ^ { H }$ 为等对角元素的下三角矩阵，其可以表示为：

$$
\pmb { R } ^ { H } = \left[ \begin{array} { l l l l } { r _ { 1 1 } } & { 0 } & { 0 } & { 0 } \\ { r _ { 2 1 } } & { r _ { 2 2 } } & { 0 } & { 0 } \\ { r _ { 3 1 } } & { r _ { 3 2 } } & { r _ { 3 3 } } & { \mathbb { C } } \\ { r _ { 4 1 } } & { r _ { 4 2 } } & { r _ { 4 3 } } & { r _ { 4 4 } } \end{array} \right]
$$

其中ri1=r22=r33=r44 °

令 $\begin{array} { r } { \pmb { G } = d i a g ( r _ { 1 1 } ^ { - 1 } , r _ { 2 2 } ^ { - 1 } , r _ { 3 3 } ^ { - 1 } , r _ { 4 4 } ^ { - 1 } ) } \end{array}$ ，那么反馈矩阵 $\textbf {  { B } }$ 和经过DPC预编码以后的发送符号 $s$ ，分别可以表达为：

$$
\begin{array} { c } { { B = G R ^ { H } } } \\ { { S = 1 } } \end{array}
$$

b）将 $\scriptstyle { \overline { { H } } } = P R ^ { H } Q ^ { H }$ 、预编码矩阵 $\pmb { F } = \pmb { Q }$ 、 $X = F S$ 、式（17）（18）代入到式（12）中，则接收信号可表达为

$$
\begin{array} { c } { { ( \stackrel { - } { Y } ) _ { G M D \cdot \mathrm { D P C } } = \overline { { { H } } } X + N } } \\ { { = P R ^ { H } { Q } ^ { H } F B ^ { - 1 } { \left\{ \begin{array} { l l } { { } } \\ { { } } \\ { { } } \end{array} \right. } } } \\ { { = P G ^ { - 1 } S ^ { ' } + N } } \end{array}
$$

通过对接收信号均衡：

$$
( { \pmb Y } ^ { ' } ) _ { G M D - D P C } = G { \pmb P } ^ { H } ( \overline { { { \pmb Y } } } ) _ { G M }
$$

可获得原始发送信号。

2.2基于GMD-THP的两组Alamouti非线性预编码传输方案

2.1小节介绍了基于GMD 算法和DPC预编码技术相结合的两组Alamouti的传输方案。然而，该方案由于信号经过预编码并反复反馈累加，将急剧增加系统的系统的峰值工作，对传输端的功放模块的设计带来巨大的挑战。为了解决这个问题，通过在DPC 的基础上加入了模运算，即所谓的THP预编码技术，THP预编码技术通过模运算可以避免信号能量的无限累积，从而实现降低峰值-平均功率比（peak-to-average power ratio,PAPR）[7,15\~17]。基于GMD-THP 的两组 Alamouti 非线性预编码系统模型图，如图3所示。

![](images/e5f696c2b43a968302432a60b4620863f9e01e40c81bb6815cdadc19a4441674.jpg)

图3基于GMD-THP的两组Alamouti非线性预编码系统其中，Mod为模运算，其余变量符号的物理含义和2.1小节系统模型中符号的物理含义相同。按照2.1小节的式（18）展开，表达为

$$
{ \left[ \begin{array} { l l l l } { r _ { 1 1 } } & { 0 } & { 0 } & { 0 } \\ { r _ { 2 1 } } & { r _ { 2 2 } } & { 0 } & { 0 } \\ { r _ { 3 1 } } & { r _ { 3 2 } } & { r _ { 3 3 } } & { 0 } \\ { r _ { 4 1 } } & { r _ { 4 2 } } & { r _ { 4 3 } } & { r _ { 4 4 } } \end{array} \right] } { \left[ \begin{array} { l } { s _ { 1 } } \\ { s _ { 2 } } \\ { s _ { 3 } } \\ { s _ { 4 } } \end{array} \right] } = { \left[ \begin{array} { l } { r _ { 1 1 } { \dot { s _ { 1 } } } } \\ { r } \\ { 0 } \\ { r _ { 2 } } \\ { r _ { 4 4 } { \dot { s _ { 4 } } } } \end{array} \right] }
$$

基于GMD-THP 的两组Alamouti 非线性预编码将DPC 预编码之后的发送信号进行Mod运算，从而构成新的发送符号$S _ { M o d }$ ，有效地避免预编码之后的信号幅值等累积增大。具体操作过程如下：

$$
\begin{array} { l } { s _ { 1 } = M o d ( s _ { 1 } ) , } \\ { s _ { 2 } = M o d ( s _ { 2 } ^ { ' } - \frac { F _ { 2 1 } } { r _ { 2 2 } } s _ { 1 } ) , } \\ { s _ { 3 } = M o d ( s _ { 3 } ^ { ' } - \frac { r _ { 3 2 } } { r _ { 3 3 } } s _ { 2 } - \frac { r _ { 3 1 } } { r _ { 3 3 } } s _ { 1 } ) , ( 2 2 ) } \\ { s _ { 4 } = M o d ( s _ { 4 } ^ { ' } - \frac { r _ { 4 3 } } { r _ { 4 4 } } s _ { 3 } - \frac { r _ { 4 2 } } { r _ { 4 4 } } s _ { 2 } - \frac { r _ { 4 1 } } { r _ { 4 4 } } s _ { 1 } ) } \end{array}
$$

以 M-QAM 的星座映射为例，提出方案的 $M o d$ 模运算可定义为

$$
M o d _ { _ A } ( s _ { 1 } ^ { ^ { \prime } } ) = s _ { 1 } ^ { ^ { \prime } } - 2 A \Bigg \lfloor \frac { s _ { 1 } ^ { ^ { \prime } } + A ^ { . } } { 2 A }
$$

其中: $s _ { 1 }$ 为原始发送符号的其中一个元素， $\lfloor \cdot \rfloor$ 代表向下取整运算。当调制方式为M-QAM映射时， $A = { \sqrt { M } }$ 。将经过预编码和模运算后的新发送符号 $S _ { M o d }$ 代入公式（19）中，接收信号可表示为

$$
\bar { ( \pmb { Y } ) } _ { G M D . \mathrm { T H P } } { = } \overline { { \pmb { H } } } \pmb { F } \pmb { S } _ { _ { M c } }
$$

对接收信号进行均衡并再次进行模运算可得

$$
M o d \Big [ { ( { \cal Y } ^ { \prime } ) } _ { G M D - T H P } \Big ] = M o d \Big [ { \cal G } P ^ { H } ( \overline { { { \cal Y } } } ) _ { G M D - T H P } \Big ]
$$

# 3 计算机仿真与分析

为验证提出方案的有效性，本文以发送天线数为 $N _ { t } { = } 4$ ，接收天线数为 $N _ { { r } } { = } 2$ 为例，进行蒙特卡洛仿真分析。假设信道为独立同分布的瑞利衰落信道，且发射端能够获取完美的信道状态信息。

图4对提出的基于GMD-DPC 的两组Alamouti 非线性预编码系统与基于LQ-DPC的两组Alamouti预编码系统以及未进行预编码的两组Alamouti系统的误码率进行仿真分析对比。本仿真采用的调制方式为QPSK。通过图4可以看出新提出的系统的误码率明显地优于基于LQ-DPC 的两组 Alamouti预编码系统和未进行预编码的两组Alamouti系统。在BER $\scriptstyle = 1 0 ^ { - 4 }$ 时，提出的基于GMD-DPC 的两组 Alamouti 非线性预编码系统相比于LQ-DPC的两组Alamouti预编码系统获得了大约6dB性能增益，相比于未进行预编码的两组Alamouti系统获得了大约9 dB 性能增益。

![](images/570a80dadf7e3b4257e997b456b69f43907c7a7160ded977545062e9faa28e93.jpg)  
图4GMD-DPC、LQ-DPC 和未预编码的两组Alamouti系统误码率对比

图5描述了基于GMD-THP、LQ-THP的两组Alamouti非线性预编码系统和未预编码的系统的BER性能对比，本仿真采用的调制方式为QPSK。通过图5可以看出基于GMD-THP的误码率明显地优于基于LQ-THP的两组Alamouti预编码系统和未进行预编码的两组Alamouti系统。在BER $\scriptstyle = 1 0 ^ { - 4 }$ 时，提出的基于GMD-DPC 的两组Alamouti 非线性预编码系统相比于LQ-DPC的两组Alamouti预编码系统获得了大约 $6 . 5 \mathrm { d B }$ 性能增益，相比于未进行预编码的两组Alamouti系统获得了大约8.5dB 性能增益。

![](images/70ba0d564b91df8f8a04ba082985279a1d84b68549d1d985f6a47a1aa9cfb0d8.jpg)  
图5GMD-THP、LQ-THP和未预编码的两组Alamouti的误码率对比

即可恢复出原始发送信号。

![](images/3e9a09fa3b6a6ac7b4b8cf1406d3bee7bf0b8f11902e6df927e2f80925e30834.jpg)  
图6GMD-DPC 和GMD-THP 的两组Alamouti系统的PAPR的 CCDF 对比

为分析GMD-THP对峰值功率降低方面的优势，图6给出了基于GMD-THP 和GMD-DPC 的两组 Alamouti 非线性预编码系统的PAPR 性能，其中纵坐标为 $1 - ( \mathrm { P } ( \mathrm { P A P R } \leq x )$ ，即PAPR的互补累积函数（Complementary Cumulative DistributionFunction，CCDF)，横轴标为PAPR值。本仿真仍采用QPSK调制。通过仿真图6可看出，通过模运算，GMD-THP比GMD-DPC具有更低的PAPR。具体而言，在 $\mathrm { C C D F = } 1 0 ^ { - 4 }$ 时，GMD-THP获得了大约0.2dB的PAPR增益。

# 4 结束语

传统DPC和THP预编码技术分别具有峰值功率过大和分解的子信道差异过大等缺点，严重影响系统总体可达性能。本文利用GMD矩阵分解对角线元素相等的特性，将其转换MIMO 信道分解后的等增益，分别提出基于GMD-DPC和GMD-THP的两组AImouti非线性预编码系统。蒙特卡洛仿真验证，提出的两种预编码方案可以有效避免显著地改善系统可获得BER性能，且THP预编码比DPC预编码能够带来更好的PAPR性能。

# 参考文献：

[1]Alamouti S M.Simple transmit diversity technique for wireless communications [J].IEEE Journal on Selected Areas in Communications, 1998,16 (8): 1451-1458.   
[2]Zhao Lan,Dubey VK.Detection schemes for space-time block code and spatial multiplexing combined system [J]. IEEE Communications Letters, 2005,9(1): 49-51.   
[3]Onggosanusi E N,Dabak A G, Schmidl T M.High rate space-time block coded scheme: performance and improvement in correlated fading channels [C]//Proc of IEEE Wireless Communications and Networking Conference. 2002:194-199.   
[4]Chen Meng,Tuqan Jamal.Precoded STBC-VBLAST for MIMO wireless communication systems [C]/ Proc of IEEE International Conference on Acoustics, Speech and Signal Processing. 2007: 337-340.   
[5]Lu Jihua,Pei Guangkun,Li Xiangming,et al.Performance of STBCVBLAST hybrid system based on GMD precoding algorithm [C]//Proc of Global Mobile Congress.Washington DC: IEEE Computer Society, 2011: 1-6.   
[6] Zhang Zhenchuan, Chen Bo.A precoding scheme for STBC-VBLAST system[C]//Proc of International Conference on Wire-less Communications, Networking and Mobile Computing. 201: 1-4.   
[7] Deng JH,Jhan S C,Huang Shengyang.A low-complexityprecoding transceiver design for double STBCsystem [C]// Proc of the 35th International Conference on Telecommunications and Signal Processing. 2012: 196-200.   
[8]Costa M H M.Writing on dirty paper(Corresp.）[J]. IEEE Trans on Information Theory,1983,29 (3): 439-441.   
[9] Zois G, Michaloliakos A,Psounis K,et al. Non-asymptotic performance bounds for downlink MU-MIMO scheduling [C]// Wireless On-Demand Network Systems and Services. 2016: 1-8.   
[10] Ginis G, Ciof JM. A multi-user precoding scheme achieving crosstalk cancellation with application to DSL systems [C]//Proc of the 34th Asilomar Conference on Signals,Systems and Computers.2002: 1627-1631 vol.2.   
[11] Fischer R FH, Windpassinger C,Lampe A,et al. Space-time transmission using Tomlinson-Harashima precoding[Cl//Proc of the 4th International ITG Conference on Source and Channel Coding. 2002: 139-147.   
[12]张蕾．非线性预编码技术研究[D]．杭州：浙江大学,2016.(Zhang Lei. Research on nonlinear precoding techniques）[D]. Hangzhou: Zhejiang University, 2016.)   
[13] Jiang Yi,Li Jian，Hager W W.Joint transceiver design for MIMO communications using geometric mean decomposition [J]. IEEE Trans on Signal Processing,2005,53 (10): 3791-3803.   
[14] Li Haitao.Joint dirty paper precoding and user scheduling for downlink coordinated multipoint transmission system [C]//Proc of the 5th International Conference on Wireless Communications，Networking and Mobile Computing. 2009: 1-4.   
[15] Yong S C, Kim J, Yang WY, et al. MIMO-OFDM wireless communications with MATLAB [M].[S.1.]: Wiley Publishing,2010.   
[16] Noune M,Andrew N.Frequency-domain precoding for single carrier frequency-division multiple access [J]. IEEE Communications Magazine, 2009, 47 (6): 68-74.   
[17] Soma S B,Mallikarjuna PA, Muralikrishna K.Peak-to-average-power ratio reduction using low-complexity MIMO SFBC CI-OFDM system [J]. Wireless Personal Comm-unications,2015,80 (2):571-580.