# 一种多带多Chirp基调制解调技术

肖绵合，郑霖，杨超

(桂林电子科技大学 广西无线宽带通信与信号处理重点实验室，广西 桂林 541004)

摘要：多带线性调频二进制开关键控(Chirp-BOK)调制是在线性调频(Chirp)信号基础上合成的，其传统的检测方案匹配滤波法存在非相关项自干扰问题，在子带个数较多或Chirp 基的时带宽积较小情况下误码性能较差。建立了一种多带 Chirp 信号的数学模型并提出一种简易的调制框图，基于该模型，采用最小二乘法解决了匹配滤波法自干扰问题，相比于匹配滤波法，具有较好的信干噪比增益。更进一步地，通过分析多带Chirp-BOK技术缺陷提出一种多带多 Chirp基调制技术(MMCM)。MMCM技术可以灵活地调整码率与扩频增益之间的关系。仿真表明，扩频增益为0dB情况下，MMCM与OFDM技术有相同频带利用率；对于MMCM的信源组个数为J与时带宽积为P的情况，系统处理增益为P/J。

关键词：多带Chirp-BOK；MMCM技术；线性调频基 中图分类号：TN928 doi: 10.3969/j.issn.1001-3695.2018.02.0108

# Technique of modulation and demodulation based on multi-carrier and multi Chirp-basis

Xiao Mianhe, Zheng Lin, Yang Chao (1.Processing KeyLaboratoryofWideband WirelessCommunications&Signal,Guilin UniversityofElectronic Science& Technology, Guilin Guangxi 541004, China)

Abstract:Themulti-band Chirp-BOK modulation is basedon Chirpsignal,which hasproblemof non-related items selfinterference in traditional detection scheme—matching filtering method(MF).The MFhas lowerbit errorrate performance inthecaseofalarger numberof sub-bands or smaler Chirp-based bandwidth.This paper established amathematical model with multi-band Chirpsignalsand proposedasimple modulationblockdiagram.Basedonthemodel,itcould usethe least square(LS)methodtosolve theself-interference problemofmatchedfilter.LSmethodcan provideabeter SNR gaincompared with the MF.Further, we propose a mult-band multi-chirp-based modulation technique (MMCM)byanalyzing the multi-band Chirp-BOK technique.MMCM technology can flexibly adjust the relationship between code rate and spread-spectrum gain. MMCM has the same frequency band utilization as OFDM technology with spread spectrum gain ofOdB.For the case that the number of source groups of MMCM is Jand the time-bandwidth product is P, the system processing gain is P/J.

Key words:multi-band chirp-BOK;MMCM; Chirp-based

# 0 引言

由于线性调频信号(Chirp)抗噪、抗多普勒频移能力较强，其被广泛应用与雷达、水声通信、低功耗系统中[I\~3]；典型物理层Chirp扩频通信系统标准有Lora、IEEE802.15.4a 等[4,5]。扩频通信中心思想是以牺牲带宽换取扩频增益，从而获得较远的通信距离。未来的扩频通信不但需要扩频增益，同时也需要高通信速率，而大带宽多带Chirp信号能够满足上述需求，因此多带Chirp 信号被广泛研究。

近年来，以Chirp 信号为基础的时-频域调制取得了一定进展。Chirp调制可以分为两大类：二进制正交键控（BOK）[6、直接调制（DM）[7]。对于单带Chirp-BOK 体制，它使用上扫频Chirp信号和下扫频Chirp信号分别代表数字信号0/1，其在大时带宽积情况下有良好的误码性能。为了继承Chirp-BOK信号高扩频增益且易于实现等特点并为了提升频带利用率，多带Chirp-BOK体制是一种合理的选择。但传统的多带Chirp-BOK调制解调方法局限性很大，主要分为三个方面：a）调制方法，文献[8]波形合成采用存储叠加的方法，在子带个数较多的情况下，不易于硬件实现且灵活性较低，无法方便地调整时带宽积参数;b)传统的Chirp-BOK 解调采用的匹配滤波法存在非相关项自干扰的问题，只有在子带个数较少、时带宽积较大的情况下才有良好的误码性能以及实用性；c)频带利用率低下，其时-频域上仍然有大量空闲时频格点可填充。与BOK信号相异的分支是直接扩频调制，直接扩频调制是将已有的基带信号直接与Chirp 信号相乘。而多带直接调制有OFDM-Chirp、OCDM、基于分数傅里叶变换的通信系统等[9\~II]。OFDM信号可以使用方程 ${ \boldsymbol { s } } = { \boldsymbol { W } } _ { N } ^ { \cdot I } \mathbf { \widetilde { \Gamma } } ^ { a }$ 描述，而OFDM-Chirp发射信号可以使用方程$\begin{array} { r } { s = C W _ { N } ^ { - I } a } \end{array}$ 描述；OCDM发射信号可以使用方程 $\begin{array} { r } { s = \pmb { \mathcal { Q } } _ { 1 } ^ { * } \pmb { W } _ { N } ^ { \prime } \pmb { \mathcal { Q } } _ { 2 } ^ { * } \pmb { a } } \end{array}$ 描述；其中 $\pmb { \theta } _ { 1 } ^ { * }$ 、 $\boldsymbol { \Theta } _ { 2 } ^ { * }$ 、 $c$ 均为对角阵，上述三者本质上可以对等，都是基于OFDM信号的直接扩频系统。虽然OCDM/OFDM-Chirp使用Chirp信号做扩频调制在一定程度上可以抵抗时变信道的时延-多普勒弥散问题[12]，但其都已经丧失了Chirp 扩频通信的信噪比增益。

为此，本文基于上述技术，通过解决多带Chirp-BOK匹配滤波自带干扰解调的问题提出一种低复杂度的频域匹配方案，通过进一步改进该方案，提出一种多载波多Chirp 基通信系统（MMCM)。MMCM可以灵活地调整Chirp基的时带宽积并且具有较低实现复杂度。

# 1 多带Chirp-BOK信号

# 1.1单带 Chirp-BOK

考虑随时间线性变化的Chirp 信号，其相位随时间呈二次曲线变化。

$$
s ( t ) = \left\{ \begin{array} { c } { a e ^ { j \pi \mu t ^ { 2 } } , 0 \leq t \leq T } \\ { 0 \quad , o t h e r } \end{array} \right.
$$

其中： $a$ 是Chirp信号的幅度； $\scriptstyle { \mu = B \mid T }$ 是Chirp 信号的调频斜率； $T$ 是Chirp 信号的周期； $B$ 是Chirp信号的带宽。多带Chirp 信号是在单带Chirp信号的基础上在间隔 $\Delta B _ { { _ m } }$ 的频带上叠加不同中心频率的Chirp 信号。多带Chirp 信号的数学表达式为

$$
s ( t ) = \sum _ { m = 0 } ^ { M - 1 } a _ { m } e ^ { j \pi \mu t ^ { 2 } } e ^ { j 2 \pi m \Delta B _ { m } t }
$$

其中： $m$ 为子载波序号， $M$ 为总的子载波个数， $\boldsymbol { a } _ { m }$ 为各自子载波的幅度。图1给出了单带Chirp 信号以及多带Chirp信号示意图。

![](images/ea2702125434ebc7825e9972d3007e6ad155ed7fd7eeb6df1a4334e80d7d328a.jpg)  
图1(a)单带 Chirp.(b)多带Chirp.(c)/(d)多带Chirp-BOK.文献[13]给出了单带Chirp-BOK的数学表达式。以上扫频调频信号(Up-Chirp)： $C h _ { _ { u p } } = ( 2 / T _ { c } ) e ^ { j \pi \mu t ^ { 2 } }$ 代表发射数字信号1；以扫频调频信号Down-Chirp： $C h _ { d n } = ( 2 / T _ { c } ) e ^ { - j \pi \mu t t ^ { 2 } }$ 代表发射

数字信号0，其中 $\left. t \right. \leq T _ { c } / 2$ 。在接收端使用相关器将发射信号匹配出来，对于相关项，它表现出来的是一个sinc函数，且有 $S _ { c o r r } ( t ) = e ^ { \pm j \pi \mu t ^ { 2 } } [ \sin ( \pi \mu t ( T _ { c } - \bigl | t \bigr | ) ) / \left( \pi T _ { c } \mu t \right) ]$ 。同时存在非相关项干扰:  
$S _ { u n c o r r } ( t ) = ( e ^ { j \pi { \mu } ^ { 2 } / 2 } / \sqrt { T _ { m } B _ { w } } ) [ C ( { \pi } ( \sqrt { T _ { m } B _ { w } } - | t | \sqrt { \mu } ) ^ { 2 } / 2 ) + j S ( { \pi } ( \sqrt { T _ { m } B _ { w } } - | t | \sqrt { \mu } ) ^ { 2 } / 2 ] .$ 其中 $C ( z )$ 和 $S ( z )$ 是菲涅尔积分变换。由此可见，Chirp-BOK信号传统匹配滤波法存在非相关项自干扰的问题，而且显然当时带宽积 $T _ { \scriptscriptstyle m } B _ { \scriptscriptstyle { w } }$ 越小，其非相关项干扰值越大。本节的目的在于解决该问题，并将之扩展到多带系统中。

# 1.2多带 Chirp-BOK模型

单带Chirp-BOK 系统中存在非相关项干扰，多带系统中同样存在，为了解决该问题，首先将式（1）离散化。定义 $\Delta f$ 为子载波的最小频移量， $N$ 为一个周期内总采样点数，则$\Delta f { = } f _ { s } / N { = } 1 / T$ 。考虑到 ${ \mu } { = } \boldsymbol { B } \mathrm { ~ / ~ } \boldsymbol { T }$ ， $B$ 为单带 Chirp 信号的带宽，定义时带宽积 $\scriptstyle P = T B$ ，于是 $B { = } P / T = P \Delta f = P f _ { s } / N$ ，$\mu = P \Delta f ^ { 2 }$ 。另外，假设子带间隔为最小频率间隔的整数倍$\Delta B _ { { _ m } } { = } P \Delta f$ 。从而可以将式错误!未找到引用源。离散化为

$$
s ( n ) = e ^ { j \pi P \left( { \frac { n } { N } } \right) ^ { 2 } } \sum _ { m = 0 } ^ { M - 1 } a _ { m } e ^ { j { \frac { 2 \pi } { N } } P m n } , n = 0 , 1 , \cdots , N - 1
$$

其中： $M$ 为子带的总个数， $N$ 为离散Chirp信号的长度。如果采样点数 $N$ 满足 $N = M P$ ，那么，式错误！未找到引用源。恰好是序列 $\boldsymbol { a } _ { { } _ { m } }$ 的逆傅里叶变换。Chirp-BOK 调制就可以描述成

$$
s ( n ) = M e ^ { j \pi P \left( { \frac { n } { N } } \right) ^ { 2 } } { \frac { 1 } { M } } \sum _ { m = 0 } ^ { M - 1 } a _ { m } e ^ { j { \frac { 2 \pi } { M } } m n } + M e ^ { j 2 \pi P { \frac { n } { N } } - j \pi P \left( { \frac { n } { N } } \right) ^ { 2 } } { \frac { 1 } { M } } \sum _ { m = 0 } ^ { M - 1 } b _ { m } e ^ { j { \frac { 2 \pi } { M } } m n }
$$

图1(c)(d)给出了多带Chirp-BOK调制的时-频图案，根据$W _ { N } ^ { n k }$ 的循环性，将式错误!未找到引用源。对 $M$ 归一化写成矩阵形式为

$$
\begin{array} { r } { \pmb { s } = \left( \pmb { o } _ { P } \otimes \pmb { W } _ { M } ^ { - 1 } \pmb { a } \right) \circ \pmb { s } _ { s + } + \left( \pmb { o } _ { P } \otimes \pmb { W } _ { M } ^ { - 1 } \pmb { b } \right) \circ \pmb { s } _ { s - } } \end{array}
$$

$$
s = S _ { s + } E _ { _ { N , M } } W _ { M } ^ { - 1 } { \pmb { a } } + S _ { s - } E _ { _ { N , M } } W _ { M } ^ { - 1 } { \pmb { b } }
$$

其中： $\mathbf { \Omega } \bullet = \left[ a _ { 0 } \quad a _ { 1 } \quad \cdots \quad a _ { M - 1 } \right] ^ { T }$ ， $\pmb { b } = \left[ b _ { 0 } b _ { 1 } \right.$ ： $b _ { M - 1 } \big ] ^ { T }$ 为信源矩阵； $\otimes$ 为克罗内克积； $0$ 为哈达玛积。对于Chirp-BOK 调制而言，有 $b _ { { \scriptscriptstyle m } } = 1 - a _ { { \scriptscriptstyle m } } , a _ { { \scriptscriptstyle m } } \in \{ 0 , 1 \}$ 。傅里叶变换矩阵 $\boldsymbol { W } _ { \scriptscriptstyle N }$ 是由$W _ { N } ^ { n k } { = } e ^ { - j 2 \pi n k / N }$ 为元素构成的矩阵。矩阵 $\pmb { \sigma } _ { P } \triangleq [ 1 , 1 , 1 , \cdots , 1 ] ^ { T }$ 为全1矩阵且 ${ \pmb o } _ { P }$ 的大小为 $P { \times } 1$ 。全1矩阵 $\pmb { \sigma } _ { M } \triangleq [ 1 , 1 , 1 , \cdots , 1 ] ^ { T }$ ， ${ \pmb o } _ { \scriptscriptstyle M }$ 的大小为 $M \times 1$ 。扩频向量矩阵 $\pmb { S } _ { s } .$ ，是由序列（204号 $e ^ { j 2 \pi P ( k / N ) - j \pi P \left( k / N \right) ^ { 2 } }$ $k = 0 , 1 , . . . , N - 1$ 构成的列向量；扩频向量 $\pmb { s } _ { s + }$ 是由序列 $e ^ { + j \pi P \left( k / N \right) ^ { 2 } }$ 构成的列向量， $\pmb { s } _ { s + }$ 和 $\pmb { S } _ { s - }$ 的大小为 $N { \times } 1$ □$\pmb { S } _ { s + } \triangleq d i a g ( \pmb { s } _ { s + } )$ ， $\pmb { S } _ { s - } \triangleq d i a g ( \pmb { s } _ { s - } )$ ， $\pmb { { \cal E } } _ { \scriptscriptstyle M }$ 是大小为 $M \times M$ 的单位阵， $\pmb { { E } } _ { N \times M } = \pmb { \sigma } _ { P } \otimes \pmb { { E } } _ { M }$ 。

由式错误！未找到引用源。可以看出，信源向量矩阵 $\pmb { a }$ 、$\textbf { \textit { b } }$ 的多带Chirp 扩频调制可以简单地描述成 $\pmb { s } = \pmb { C } _ { + } \pmb { a } + \pmb { C } _ { - } \pmb { b }$ 其中 $\pmb { C } _ { + } \triangleq \pmb { S } _ { s + } \pmb { E } _ { N , M } \pmb { W } _ { M } ^ { - 1 }$ ， $\pmb { C } _ { - } \triangleq \pmb { S } _ { s - } \pmb { E } _ { N , M } \pmb { W } _ { M } ^ { - 1 }$ 可以看出， $c _ { \scriptscriptstyle + }$ 、 $\pmb { C } _ { - }$ 是一个 $N$ 行 $M$ 列的矩阵。按照多带Chirp-BOK 调制的数学表达式错误！未找到引用源。，可以得出多带Chirp-BOK调制框图

![](images/43da5fc77386f2be98d38683cd7ad84d42cef9fa83a7456ca5c94dcb3cc51099.jpg)

# 图2基于IFFT的多带Chirp-BOK 调制框图

相比于文献[8]采用波形叠加方法实现多带Chirp-BOK调制，本文提供了一种易于硬件实现的调制方案。

# 1.3基于LS 的检测方法

对于检测方法，考虑多带Chirp-BOK调制模型$\pmb { s } = \pmb { C } _ { + } \pmb { a } + \pmb { C } _ { - } \pmb { b }$ 以约束条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ 且向量 $\pmb { a }$ 以及向量 $\pmb { b }$ 中的元素 $a _ { m } , b _ { m } \in \{ 0 , 1 \}$ 。定义 $\pmb { H } _ { c } \triangleq \left[ \pmb { C } _ { + } \quad \pmb { C } _ { - } \right]$ ，于是 $\scriptstyle { r = { \pmb { H } } _ { c } [ { \pmb { a } } ^ { T } \quad { \pmb { b } } ^ { T } ] ^ { T } }$ 显然，当 $\pmb { H } _ { c }$ 的伪逆矩阵 $\pmb { H } _ { c } ^ { + }$ 存在时，方程是有解的。因此只需要保证 $r a n k ( { \pmb H } _ { c } ) { = } N \geq 2 M$ 即可。

$$
\begin{array} { r l } & { \pmb { H } _ { c } ^ { + } = ( \pmb { H } _ { c } ^ { H } \pmb { H } _ { c } ) ^ { - 1 } \pmb { H } _ { c } ^ { H } = \left( \pmb { E } _ { \jmath } \otimes \pmb { W } _ { M } \right) \pmb { A } ^ { + } \left( \pmb { \sigma } _ { \jmath } \otimes \pmb { E } _ { \scriptscriptstyle N } \right) } \\ & { \quad \quad \triangleq \left( \pmb { E } _ { \jmath } \otimes \pmb { W } _ { M } \right) \left( \pmb { \sigma } _ { \jmath } ^ { T } \otimes [ \pmb { D } _ { a } ^ { T } \quad \pmb { D } _ { b } ^ { T } ] ^ { T } \right) \left( \pmb { \sigma } _ { \jmath } \otimes \pmb { E } _ { \scriptscriptstyle N } \right) } \end{array}
$$

对于 Chirp-BOK 而言， $J = 2$ ，则 $\boldsymbol { E } _ { \scriptscriptstyle J }$ 为 $2 \times 2$ 的单位阵;列向量 $\mathbf { \pmb { \mathscr { o } } } _ { J } { = } [ 1 \mathbf { \epsilon } 1 ] ^ { T }$ ； $\scriptstyle A = ( \pmb { o } _ { J } \otimes [ \pmb { S } _ { s + }$ $\pmb { S } _ { s - 1 } ] ) ( \pmb { E } _ { J } \otimes \pmb { E } _ { N , M } )$ ；因此$\pmb { a } = 2 \pmb { W } _ { _ M } \pmb { D } _ { a } \pmb { r }$ ， $\pmb { b } = 2 \pmb { W } _ { \scriptscriptstyle M } \pmb { D } _ { \scriptscriptstyle b } \pmb { r }$ 其中 $\mathrm { \bf A }$ 矩阵可以使用计算机计算得出。事实上，由于 $\boldsymbol { S } _ { s + }$ 、 $\pmb { S } _ { s - }$ 是一个对角阵，使得矩阵 $\boldsymbol { D } _ { \boldsymbol { a } }$ 和 $\pmb { { \cal D } } _ { b }$ 是一个稀疏矩阵，每一行上N个数据中只有M个位置上有数据，其他位置为零。另外，可以看出 $D _ { a } r$ 、 $D _ { b } r$ 操作实际上只需要做 $P$ 次乘法，这给系统的硬件实现提供了思路：将数据流串行处理，用传统FIR 滤波器结构实现矩阵相乘操作，据此，提出一种基于最小二乘的多带Chirp-BOK 调制解调方法。

![](images/5e0d9bc83c1da75370f010160a933ffd15b2fd73391a0f7ef1882e5ebb676000.jpg)  
图3多带Chirp-BOK 解调框图

![](images/b7fb4252005e514c3adea547079a79a7dc427251d8d440cbfa358981ccea4df8.jpg)  
图4 (a)相同子带个数M，不同子带时带宽积P比较。(b)相同子带时带宽积P，不同子带个数M比较。

图 4(a)仿真表明，在相同子带个数M不同的子带时带宽积P的情况下，本文方法都取得了一定的信噪比增益；在P值较小的情况下，处理增益的改善是显著的；在P值越来越大的情况下，本文方法与传统匹配滤波方法的BER 曲线趋于一致，这是由于随着P的增大，传统匹配法的相干项与非相干项的比值增大使得处理增益增大。图4(b)仿真表明，本文方法相比于传统匹配法，在 $\mathrm { B E R = 1 0 } ^ { - 2 }$ 情况下取得大约3dB的信噪比增益。另一方面，从Chirp-BOK信号的时-频框图上看，仍然有大量空闲的时频格点可用，这将可以进一步提升频谱利用率，本文的第二章将进一步研究这一问题。

# 2 多带多Chirp 基调制解调技术

由多带 Chirp-BOK 调制模型及其约束条件 $\mathbf { \mu } _ { s = 1 } ^ { s } ( C _ { + } \mathbf { \hat { \mu } } _ { a + } C _ { - } \mathbf { \hat { \mu } } _ { b }$ s.t $\mathbf { \nabla } . \pmb { a } = \pmb { o } _ { M } - \pmb { b }$ ，向量 $\pmb { a }$ 以及向量 $\textbf { \textit { b } }$ 中的元素 $a _ { m } , b _ { m } \in \{ 0 , 1 \}$ 。可以看出，约束条件是限制系统传输码率的一大因素。在本章节中，剔除约束条件，并在时-频域上充分填入线性Chirp基。

# 2.1 剔除约束条件

剔除约束条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ ，这就意味着信源从实数 $_ { 0 / 1 }$ 域扩展到复数域。如果使用传统的复矢量调制信源，对于$\pmb { s } = \pmb { C } _ { + } \pmb { a } + \pmb { C } _ { - } \pmb { b }$ 调制，从式错误!未找到引用源。来看，复矢量调制改变了Chirp 基的初始相位与幅度，并且，时频域上的Up-Chirp/Down-Chirp基是实时重叠的。图5剔除条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ $a _ { m } , b _ { m } \in \{ 0 , 1 \}$ 调制解调示意图描绘了重叠式多带 Chirp-BOK 调制解调示意图。对于16QAM的随机信源向量 $\pmb { a }$ 以及向量 $\textbf { \textit { b } }$ ，在同带宽且子带个数 $M = 8$ 时带宽积 $P = 8$ 扩频基个数 $J = 2$ 情况下MMCM-16QAM相比于Chirp-BOK的符号率提升了16倍，但距离传统的OFDM-16QAM符号率仍然有 $P$ 倍差距。可以看出剔除约束条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ 后，系统频谱利用率得到了提升。

![](images/242dd8af06ee5f29ee7ca2f692b076e5c6d1ded13c59e74aa02afcc27df3c97d.jpg)  
图5剔除条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ ， $a _ { m } , b _ { m } \in \{ 0 , 1 \}$ 调制解调示意图

# 2.2引入 Chirp 扩频基

在上一节中，提出了一种多带Chirp-BOK信号的调制解调方案。从Chirp-BOK信号的时频格点角度来看，时-频域上还有很大的利用空间，考虑再填充其他正交Chirp信号。在这里，我们使用基于Chirp信号的短时频移正交信号错误！未我到明用，它是在 Chirp 信号 $e ^ { j \pi \mu t ^ { 2 } }$ 的基础上进行一定的时移得到另外一个正交信号 $e ^ { j \pi \mu ( t - \tau ) ^ { 2 } }$ 。假设系统需要使用 $J$ 组正交扩频基，在这里.我们将原始Chirp 扩频基对 $N$ 均匀地平移 $J$ 份，并统一地将由扩频基构成对角阵记为 $\boldsymbol { S } _ { s j }$ 。使用 $\boldsymbol { S } _ { s j }$ 扩频的多带 Chirp 调制过程记为 $\pmb { C } _ { j } = \pmb { S } _ { s j } \pmb { E } _ { N , M } M \pmb { W } _ { M } ^ { - 1 }$ 。那么，在传输矩阵$\pmb { H } _ { c } { = } [ \pmb { C } _ { 0 } \pmb { C } _ { 1 } \dots \pmb { C } _ { J - 1 } ]$ 伪逆存在的条件下（ $r a n k ( { \pmb H } _ { c } ) = J M$ 或$P { \ge } J$ ）至多可以携带 $J$ 组独立信源。我们将这种对 $M$ 归一化的调制过程称为多带多Chirp基扩频调制(MMCM)

$$
\pmb { S } = \sum _ { j = 0 } ^ { J - 1 } \pmb { C } _ { j } \pmb { a } _ { j } = \sum _ { j = 0 } ^ { J - 1 } \pmb { S } _ { s j } \pmb { E } _ { N , M } \pmb { W } _ { M } ^ { - 1 } \pmb { a } _ { j }
$$

其中 $\boldsymbol { S } _ { s j }$ 是第 $j$ 个扩频信号序列构成的对角阵，扩频序列的长度为 $N$ ，时带宽积为 $P$ 。对于传统的OFDM而言，有 $P = 1 , J = 1$ 。如果让 $P { = } J > 1$ ，这将使得MMCM的码率达到相同条件下的传统的OFDM 码率。另一方面， $\mathrm { P / J }$ 为整数情况下， $\boldsymbol { C } _ { j }$ 具有良好的正交性，即 $\pmb { C } _ { j } ^ { H } \pmb { C } _ { j } = ( P / M ) \pmb { E } _ { M }$ （非归一化情况下有$\pmb { C } _ { j } ^ { H } \pmb { C } _ { j } = N \pmb { E } _ { M }$ )以及 $\pmb { C } _ { i } ^ { H } \pmb { C } _ { j } = \pmb { 0 } _ { M \times M } , \forall i \neq j$ 。对于解调而言，显然有

$$
\begin{array} { r } { \hat { \pmb { a } } _ { j } = W _ { M } \pmb { E } _ { M , N } \pmb { S } _ { s j } ^ { H } \pmb { r } \times ( M / P ) , \vec { \times } \pmb { \mathrm { f } } M ) \exists  \ n U } \\ { \hat { \pmb { a } } _ { j } = W _ { M } \pmb { E } _ { M , N } \pmb { S } _ { s j } ^ { H } \pmb { r } / N , \vec { \mp } \pmb { \mathrm { H } } \varTheta \exists  \ n U } \end{array}
$$

但这对 $\mathrm { P / J }$ 为非整数情况下并不成立。虽然另一方面，可以考虑传输矩阵 $\pmb { H } _ { c } { = } [ \pmb { C } _ { 0 } \pmb { C } _ { 1 } \dots \pmb { C } _ { J - 1 } ]$ 的伪逆存在的条件下( $P { \ge } J$ ）求解传输矩阵 $\pmb { H } _ { c }$ 的伪逆矩阵，虽然该方法不要求Chirp 基的正交性，但复杂度较高，本文不深入研究该方法。根据上述数学模型，提出一种MMCM调制解调方案，如图6/图7所示。

![](images/aad3f9e114825dd95bee34b4510e72f562d38faaabdde9eec04ef07d7beba798.jpg)

![](images/8cfce1d42a642051442eed4de34196259705fe155c38a09298c2cb47c9120636.jpg)  
图6MMCM调制方法  
图7MMCM解调方法

MMCM解调方法相比于多带Chirp-BOK解调方法复杂度得到了大幅度降低。MMCM调制实际上是将信源信息分布在多个连续的频点上。在增加合理短时平移正交信号作为扩频基后，在时-频域上，MMCM信号相比于Chirp-BOK得到了充分填充与较高的时频空间利用率。这样使得 $J { = } P$ 条件下的MMCM调制的频谱利用率达到了OFDM相同的频谱利用率，但这同时，仿真表明MMCM也失去了原有的处理增益。但是在信源组个数 $J < P$ 的情况下，扩频信号 $s$ 的带宽为 $N { = } P M$ ，而信源信号的总带宽为JM，因此MMCM是具有一定的处理增益的，其增益值为 $P / J$ 。

# 3 仿真

# 3.1时域、频域分析

这一节将分析比较相同条件下的MMCM与OFDM信号的时域、频域的波形，如图8所示。为了更好地分析比较信号，本仿真实验中设置 $J = 8 , P = 8 , M = 8$ 。在时域分析中，将发射信源设置为 $1 - 1 j$ ；在频域分析采中，将发射信源设置为随机信源。此外，上述数学分析为了公式编写简洁均对 $\mathtt { M }$ 归一化，本节所有仿真均乘回 $\mathtt { M }$ 。

80 O— real mmen 60 - imag mmcm O real ofdm imag ofdm 40 20 限 0.Gm Bp ) 20 率 -20 15 -40 -60d 10 -80 0.1 0.20.3 0.40.50.60.7 0.80.9 5− 0.1 0.2 0.3 0.4 0.50.6 0.7 0.8 0.9 对T归一化时间 归一化频率 (a)时域波形 (b)频域波形

从图8 (a)时域图可以看出频域上的常数信息对应时域上的一个窄脉冲，这符合传统的OFDM信号相关特性，而MMCM信号在时域上则表现为一连串脉冲，这是因为MMCM调制本质上是将信源信息组调制一连串频点上。从图8 (b)时MMCM信号的频谱图可以看，基于傅里叶分析的MMCM信号功率谱具有较高的功率谱变化。

# 3.2峰均比(PAPR)& 误比特率(BER)

这一小节采用CCDF 衡量MMCM信号的峰均比指标。在这里，仿真结果表明，MMCM与OFDM有相近的PAPR指标。且当信源组个数增多时，PAPR随之增大，结果如图9所示。

![](images/94d5330139d997893eca2a7e642a5290a2cb1eee5e7e14c9e217fdeccd6d9886.jpg)  
图8 MMCM与OFDM信号在时域/频域的一些比较  
图9MMCM-4QAM与OFDM-4QAM性能分析比较

根据理论分析，MMCM信号的处理增益为 $P / J$ 。仿真结果表明，对于 $J / P { = } 1 / 2$ ，相比于OFDM-4QAM系统，在 $\mathrm { B E R = } 1 0 ^ { - 2 }$ 情况下取得大约3dB 信噪比增益；对于 $J / P { = } 1 / 4$ ，相比于OFDM-4QAM系统，在 $\mathrm { B E R = 1 0 } ^ { - 2 }$ 情况下取得大约6dB 信噪比增益。当$J = P$ ，MMCM的处理增益为0dB即没有信噪比增益，误码曲线与OFDM一致，与理论分析一致。

# 4 结束语

本文首先引入限制条件 $N = P M$ 解决了多带 Chirp-BOK 传统匹配滤波法非相关项自干扰的问题；通过建立一种多带Chirp信号的数学模型提出一种调制方案；根据该数学模型，基于最小二乘法提出一种检测方法，该检测方法不受ChirpBOK的约束条件 $\pmb { a } = \pmb { o } _ { M } - \pmb { b }$ 限制。其次通过进一步填充时频空间提出一种基于短时平移正交Chirp信号的多带多载波Chirp 调制方案（MMCM)。对于接收端，利用矩阵 $\boldsymbol { C } _ { j }$ 的正交性，得出MMCM信号的解调方案，相比于传统的Chirp-BOK匹配方法，得到了进一步的简化。在信源组个数 $J$ 与时带宽积 $P$ 相等的情况下，MMCM的频带利用率与OFDM系统一致；对于信源组个数 $J$ 小于时带宽积 $P$ 的情况下，接收端具有 $P / J$ 倍处理增益。这为多用户设计、雷达通信一体化设计提供了思路。

# 参考文献：

[1]Cheng Shengjuan，Wang Wenqin,So H C.MIMO radar OFDM chirp waveform diversity design with sparse modeling and joint optimization [J]. Multidimensional Systems & Signal Processing,2015,28(1):1-13.   
[2]Li Baosheng，Zhou Shengli， Stojanovic M,etal.Multicarrier communication over underwater acoustic channels with nonuniform Doppler shifts [J].IEEE Journal of Oceanic Engineering,20o8,33 (2):198- 209.   
[3]Dongare A,HeslingC,Bhatia K,et al. OpenChirp:a low-power wide-area networking architecture [C]// Proc of IEEE International Conference on Pervasive Computing and Communications.2017: 569-574.   
[4]Vangelista L.Frequency shift chirp modulation: the LoRa modulation [J]. IEEE Signal Processing Letters,2017,PP(99):1.   
[5]KarapistoliE,Tsetsinas I, Tsetsinas I,et al.An overview of the IEEE 802. 15.4a standard [J].Communications Magazine IEEE,2010,48(1): 47-53.   
[6]Winkler M.Chirp signals for communications [C]//Proc of IEEE WESCON Conference.Piscataway:IEEE Press,1962:14-17.   
[7]Berni A J,Gregg W D.On the utility of Chirp modulation for digital signaling [J].IEEE Trans on Communications,1973,21 (6): 748-751.   
[8] 樊孝明 汪沂．基于 FPGA 的高速多带 ChirpBOK 信号的产生与实现 [J].电视技术,2014,38(15):80-83.(Fan Xiaoming,Wang Yi.Generation and realization of high speed multi-band ChirpBOK based on FPGA [J]. Video Engineering,2014,38(15): 80-83.)   
[9]Wang W Q, Zheng Z,Zhang S.OFDM chirp waveform diversity for codesigned radar-communication system [Cl// Proc of Radar Symposium. 2017.   
[10] Ouyang Xing,Zhao Jian.Orthogonal Chirp division multiplexing for coherent optical fiber communications [J].Journal ofLightwave Technology, 2016,34(18):4376-4386.   
[11] Gaglione D,Clemente C,Ilioudis CV,et al.Fractional fourier based waveform for a joint radar-communication system [C]//Proc of Radar Conference.2016:1-6.   
[12]Martone M.A multicarrier system based on the fractional Fourier transform for time-frequency-selective channels [J]. IEEE Trans on Communications, 2001,49(6):1011-1020.   
[13] Pinkney J.Low complexity indoor wireless data links using chirp spread spectrum [D].Calgary, Canada: University ofCalgary,2003.   
[14] Krieger G.MIMO-SAR:opportunities and Pitfalls [J].IEEE Trans on Geoscience & Remote Sensing,2014,52(5):2628-2645.