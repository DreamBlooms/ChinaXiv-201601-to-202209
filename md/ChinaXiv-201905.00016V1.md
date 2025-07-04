# 基于PN码随机化的MSAC攻击防御方法

许新忠」，张连成2，燕菊维²

(1．河南艺术职业学院，郑州 450011;2.数学工程与先进计算国家重点实验室，郑州 450001)

摘要：基于流速率的直序扩频（DSSS）流水印技术在嵌入多比特的水印信息时采用同一伪随机（PN）码，使得已标记数据流具有自相似性，均方自相关（MSAC）攻击通过单条已标记数据流就可检测 DSSS 流水印的存在性，严重破坏了DSSS 流水印的隐蔽性。PN码正交化方法虽可消除已标记数据流的自相关性，进而抵御 MSAC攻击的检测，但正交PN码难以生成，应用范围受限。为此，提出基于PN码随机化的MSAC攻击防御方法，在向目标数据流嵌入每个水印位时均采用随机选择的不同长度的PN码进行扩展，使得已嵌入DSSS流水印的数据流速率的均方自相关不再呈现周期性峰值，进而可在MSAC攻击面前保持隐蔽性。理论分析与实验结果表明，基于PN码随机化的 MSAC攻击防御方法可有效抵御MSAC攻击的检测，且所采用的PN码易于生成，便于部署和应用。

关键词：流水印；直序扩频；均方自相关攻击；PN码正交化；PN码随机化 中图分类号：TP309.02 doi: 10.19734/j.issn.1001-3695.2018.11.0891

Pncoderandomizationbasedmsacattackresistancemethod

Xu Xinzhong1, Zhang Liancheng², Yan Juwei² (1.Henan Vocational ColegeofArt,Zhengzhou45ool1,China;2.State KeyLaboratoryfor Mathematical Engineering& Advanced Computing, Zhengzhou 450001, China)

Abstract: The flow rate based direct sequence spread spectrum (DSSS） flow watermarking technique used the same pseudo-random (PN) code to modulate the multi-bit watermark signal,asa result,the DSSS watermarked flow had self-similarity,and themean-square autocorelation (MSAC)attackcoulddetecttheexistenceofthe DSSS flowwatermark byusingsingle DSSS watermarked flow,which seriouslydestroyed thestealthinessof theDSSS flow watermark.Although the PNcodeorthogonalization methodcouldeliminate theautocorrelationof the DSSS watermarkedflowand thus resisted the MSACattack,however,theorthogonalPNcodes weredificult togenerate,which limit itsapplicationrange.Therfore, this paper proposed the PNcode randomization based MSAC atack resistance (PNCR-MAR) method,when the watermark signal wasembedded intothetarget flow,thePNcodes of diferent lengths,randomlyselected fromaPNcodeset,were used tospread each watermark bit,so thatthe mean-squareautocorelationof the flowrate ofthe watermarked flow no longer exhibited periodic peaks,as aresult, this PNCR-MAR method could defend against the MSAC atack.Theoretical analysis and experimentalresults show that this proposed PNCR-MAR methodcan effectivelyresistthe MSACatack,and the adopted PN codes are easy to generate, which is suitable for deployment and application.

Key words: flow watermarking; direct sequence spread spectrum; mean-square autocorrelationatack; pseudo-noise code orthogonalization; pseudo-noise code randomization

# 0 引言

与被动流相关技术相比，主动流水印技术通过主动调制发送者数据流特征（如对特定数据包进行延迟或影响数据流速率等）进而嵌入水印信息来帮助确认发送者和接收者的通信关系[1-3]，在跳板攻击追踪和匿名用户关联等方面具有准确率高、误报率低等优点。典型的流水印技术有基于时间间隔的流水印（interval-basedwatermarking，IBW）[4.5]、基于间隔重心的流水印（interval centroid based watermarking，ICBW)[6]、基于间隔到达时延（inter-packet delay,IPD）的流水印[7]、RAINBOW流水印[8.9]和SWIRL流水印[10]等，分别通过调制时间间隔、间隔重心、间隔到达时延等流量特征来嵌入水印信息。然而，这些流水印技术都需要对目标数据流拥有较为完全的控制权才能进行水印信息的嵌入[]。

相比而言，基于直序扩频（direct sequence spreadspectrum，DSSS）的流水印技术[12]不需对目标数据流具备完全控制权，通过调制目标数据流的速率即可嵌入相应水印信息，可有效追踪恶意匿名用户和跳板攻击源。

然而，DSSS 流水印技术在向目标数据流嵌入水印信息时，对于不同的水印位采用同一PN（pseudo-noise，伪噪声）码进行嵌入，导致嵌入DSSS流水印信息的已标记数据流存在自相似性，其速率的时间序列的均方自相关（mean-squareautocorrelation，MSAC）呈现周期性峰值，Jia等人[l3,l4]据此提出MSAC攻击方法，根据单条已嵌入DSSS流水印的已标记数据流即可检测出其中DSSS流水印的存在性，即使对DSSS 流水印所用的PN码毫无所知，且不需数据流同步[15]。

为提升DSSS流水印技术的MSAC攻击防御能力，对比分析现有MSAC攻击防御方法的缺点和不足，研究MSAC攻击防御新方法，提出基于PN码随机化的MSAC攻击防御（PN code randomization based MSAC attack resistance,PNCR-MAR）方法，并对PNCR-MAR方法的抗MSAC攻击能力进行理论分析和实验验证。

# 1 MSAC攻击防御研究现状分析

# 1.1 MSAC 攻击

Jia 等人[13,14]提出MSAC攻击方法来检测DSSS 流水印的存在性。由于DSSS流水印技术在调制多比特的水印信息时采用同一个PN码，使得已标记数据流具有自相似性，使得攻击者通过单条已标记数据流的流量速率时间序列的均方自相关即可检测DSSS流水印的存在性，即使对其所用的PN码毫无所知。

该攻击方法复杂度低，比基于多流攻击（multi-flowattack，MFA）的DSSS 流水印检测方案[16,17]更加灵活和准确，对DSSS流水印的隐蔽性造成巨大挑战。

# 1.2现有MSAC攻击防御方法分析

为抵御MSAC攻击，张连成等人提出可抵御MSAC和多流攻击的扩频流水印（MSAC and multi-flow attacksresistant spread spectrumwatermarking，MMAR-SSW）方案[18]和基于时间间隔的扩频流水印（interval-based spread spectrumwatermarking，IBSSW）技术[19,20]，使用多个正交PN码来扩展水印信息的不同水印位，并使用相同的正交PN码来解扩以恢复水印信息。由于这些PN码是正交的，因此已嵌入水印的已标记数据流速率的时间序列的均方自相关就不会显现出周期性峰值，进而可有效抵御MSAC攻击。

在抵御 MSAC 攻击的检测时，MMAR-SSW 方案和IBSSW技术本质上采用的是PN码正交化方法。该方法的MSAC攻击防御效果较好，然而，要求在对水印位进行扩展时采用正交PN码，但是正交PN码并不容易获得，限制了该方法的应用。

张璐等人[21提出基于时隙质心流水印的匿名通信追踪技术，由于时隙组是随机分配的，攻击者在不确定时隙组具体分配方式的情况下难以得到相应码片所具体对应的时隙质心，进而无法判断流是否在短时间内出现了自相似性，因此对MSAC攻击具有免疫力，然而，文献[21]中只进行了文字论述，未进行理论推导与实验验证。不过，其所采取的随机化思想值得借鉴和学习。

# 1.3基于PN码随机化的MSAC攻击防御新思路

针对PN码正交化方法的不足，本文提出“一比特一PN码”的PN码随机化思想，在向目标数据流嵌入每个水印位时均采用随机选择的、长度不同的PN码进行扩展，使得水印信息经由PN码扩展后呈现出随机性，已嵌入流水印的已标记数据流速率的均方自相关不再呈现周期性峰值，进而可在MSAC攻击面前保持隐蔽性，而且此方法下对PN码没有特殊要求，其生成和使用都很容易，应用更为广泛。

# 2 基于PN码随机化的MSAC攻击防御方法

基于PN码随机化的MSAC攻击防御方法的基本框架如图1所示，由水印嵌入器和水印检测器两个部分组成。水印嵌入器负责对原始水印进行扩展，并调制目标数据流，已标记数据流最终被送入网络中进行传输，可能经过匿名通信节点、跳板链等的处理和传递。水印检测器的功能是从被干扰后的已标记数据流中检测、恢复出其中嵌入的水印信息，如果恢复出的水印信息与原始水印相同，那么就可确认发送者和接收者之间的通信关系。

下面分别对水印嵌入器的水印信息扩展和嵌入过程、水印检测器的水印信息检测过程与判决规则进行介绍。假设下面的参数是水印嵌入器和水印检测器共享的（通过某种秘密途径协商或预先设定等）：码片时长 $T _ { c }$ 、i位水印$w = \{ w _ { 0 } , w _ { 1 } , \cdots , w _ { l - 1 } \}$ 、PN 码集(包含多个长度不同的PN码)PN、PN码选取随机值 $s$ 。

![](images/e5286640e3f591a98da3a54b9cfa1ffba8f033b1ba8edc975a8b1646b8b72732.jpg)  
图1PNCR-MAR方法处理流程

# 2.1水印信息扩展和嵌入过程

水印嵌入器采取以下步骤进行水印信息的扩展和嵌入：a)依据PN码选取随机值 $s$ 从PN码集中为每个水印位 $w _ { i }$ （ $: \cdot + 1 ^ { \cdot }$ 或者 $\cdot _ { - 1 } \cdot$ ， $0 \leq i \leq l - 1 \ )$ 随机选取PN码 $c _ { t , i }$ （长度为 $N _ { c , i }$ ）。

b)依次依据选取的PN 码 $c _ { t , i }$ 对水印位 $w _ { i }$ 进行扩展（即对不同的水印位采用不同的PN码，长度为 $N _ { c , i }$ ，如图2所示），可得待传输的扩展水印 $\boldsymbol { w _ { i } ^ { s } }$ ， $\boldsymbol { w _ { i } ^ { s } }$ 可被表示为

![](images/55ba5b363367c9c696c54869c024e47e6a9a26e136ebf52f1313b07d38273bda.jpg)  
Fig.1PNCR-MAR method and processing procedure   
图2PN码随机化的水印位扩展

![](images/544ebe7e9ebc773f222ea9d0d5ef9a40a5c496b1be78c05d3e552495b2c3ced6.jpg)  
Fig.2Watermark bit spreading of the PN code randomization methoc   
图3PNCR-MAR方法数据流调制  
Fig.3Flow modulation of the PNCR-MAR method

c将 $\boldsymbol { w _ { i } ^ { s } }$ 嵌入目标数据流 $f ^ { u }$ 中。当扩展水印位为 $\cdot _ { + 1 }$ 时，对目标数据流施加弱干涉，因此数据流在 $T _ { c }$ 秒时间段内的速率较大。当扩展水印位为'-1'时，对目标数据流施加强干涉，因此数据流在 $T _ { c }$ 秒时间段内的速率较小。假设数据流的平均速率为 $D$ ，高速间隔的速率为 $D + A$ ，低速间隔的速率为 $D { - } A$ （其中 $A$ 为调制幅度)，如图3所示。因此嵌入水印后的数据流速率 $W$ 为

$$
W = A w c _ { t } + D
$$

d)重复上述步骤b)c)来嵌入i位的水印信息。  
e)将已标记数据流发送到网络上进行传输。

# 2.2水印信息检测过程

已标记数据流经过网络传输、匿名处理等干扰之后，流经放置在接收端附近的水印检测器。水印检测器采取以下步骤进行水印信息的检测：

a)水印检测器捕获到已标记数据流 $f ^ { \scriptscriptstyle { w } }$ 之后，将其分为长度为 $T _ { c }$ 的时间段，计算每个段的平均速率，依据PN码选取随机值 $s$ 从PN码集中为每个水印位选取对应的PN码（获取PN 码本身及对应的PN码长度)，然后计算与所选取PN码长度对应的连续时间段的平均速率。假设网络中的噪声为 $\xi$ ，那么水印检测器接收到的受干扰后的已标记数据流的速率信号 $\textstyle R _ { \scriptscriptstyle w }$ （对于单个水印位 $w _ { i }$ 而言）为

$$
R _ { \nu } = A w _ { i } c _ { t , i } + D + \xi
$$

b)将接收到的 $R _ { \scriptscriptstyle { w } }$ 经过一个高通滤波器滤去分量 $D$ ，那么过滤后的信号 $\boldsymbol { R _ { w } }$ 为

$$
{ R _ { w } } ^ { \prime } = A w _ { i } c _ { t , i } + \xi
$$

c)获取 $\boldsymbol { R _ { w } }$ 后，依据所选取的对应PN码 $c _ { r , i }$ 计算信号 $R _ { b }$ ：

$$
R _ { b } = A w _ { i } c _ { t , i } \cdot c _ { r , i } + \xi \cdot c _ { r , i }
$$

d)再使用低通滤波器滤除高频噪声，根据2.3节给出的判决规则就可获得恢复水印信息位 $w _ { i }$ 。

e)重复步骤a)\~d)即可恢复得到 $\mathbf { \xi } _ { l }$ 位的水印信息 $w ^ { \prime }$ □

f)如果恢复水印 $w ^ { \prime }$ 与原始水印 $w$ 相同，则水印检测器报告发现水印信息，那么发送者和接收者的关系即可确定。

可以看到，在PNCR-MAR方法中，原始水印长度l、码片时长 $T _ { c }$ 、PN 码长度 $N _ { c , i }$ 和水印调制幅度 $A$ 都会影响数据流追踪效果。

# 2.3判决规则

为便于分析，暂时不考虑噪声等干扰，水印检测器接收到的已标记数据流的速率信号 $R _ { \scriptscriptstyle { w } }$ （对于单个水印位 $w _ { i }$ 而言）为

$$
R _ { \mathrm { { w } } } = A w _ { i } c _ { t , i } + D
$$

假设 $t = A w _ { i } c _ { t , i }$ ，对信号 $R _ { \scriptscriptstyle { w } }$ 进行离散傅里叶变换可得

$$
R ( k ) = \sum _ { n = 0 } ^ { N _ { c , i } - 1 } ( t ( n ) + D ) W _ { N _ { c , i } } ^ { k n } = T ( k ) + \sum _ { n = 0 } ^ { N _ { c , i } - 1 } D W _ { N _ { c , i } } ^ { k n }
$$

$$
r ( n ) { = } \frac { 1 } { N _ { c , i } } \sum _ { k = 0 } ^ { N _ { c , i } - 1 } R ( k ) W _ { N _ { c , i } } ^ { - k n }
$$

其中: $W _ { N _ { t , i } } = e ^ { - j \left( 2 \pi / N _ { c , i } \right) }$ ，由式(7)可得

$$
\begin{array} { l } { { \displaystyle R \big ( 0 \big ) = \sum _ { n = 0 } ^ { N _ { c , i } - 1 } \big ( t \big ( n \big ) + D \big ) W _ { N _ { c , i } } ^ { 0 n } = \sum _ { n = 0 } ^ { N _ { c , i } - 1 } A w _ { i } c _ { t , i } \left( n \right) + N _ { c , i } D } } \\ { { \displaystyle \qquad = A w _ { i } \sum _ { n = 0 } ^ { N _ { c , i } - 1 } c _ { t , i } \left( n \right) + N _ { c , i } D } } \end{array}
$$

假设 $\sum _ { n = 0 } ^ { N _ { c , i } - 1 } c _ { t , i } \left( n \right) = x$ ，则有

$$
R ( 0 ) = A w _ { i } x + N _ { c , i } D
$$

利用高通滤波器过滤掉 $R ( 0 )$ 后，可得

$$
\begin{array} { l } { { \displaystyle r ^ { * } ( n ) = \frac { 1 } { N _ { c , c } } \left[ \sum _ { k = 0 } ^ { N _ { c - 1 } } R ( k ) W _ { x _ { c , c } } ^ { - \operatorname* { i n } } - R ( 0 ) \right] } } \\ { { \displaystyle \quad = \frac { 1 } { N _ { c , c } } \left[ \sum _ { k = 0 } ^ { N _ { c - 1 } } \left( T ( k ) + \sum _ { m = 0 } ^ { N _ { c - 1 } } D W _ { x _ { c , c } } ^ { - \operatorname* { i n } } \right) W _ { x _ { c , c } } ^ { - \operatorname* { i n } } - R ( 0 ) \right] } } \\ { { \displaystyle \quad = \frac { 1 } { N _ { c , c } } \left[ \sum _ { k = 0 } ^ { N _ { c - 1 } } T ( k ) W _ { x _ { c , c } } ^ { - \operatorname* { i n } } + N _ { c , i } D - A w _ { i } x - N _ { c , i } D \right] } } \\ { { \displaystyle \quad = \frac { 1 } { N _ { c , c } } \left[ \sum _ { k = 0 } ^ { N _ { c - 1 } } T ( k ) W _ { x _ { c , c } } ^ { - \operatorname* { i n } } - A w _ { i } x \right] } } \\ { { \displaystyle \quad = t ( n ) - A w _ { i } x / N _ { c , i } } } \end{array}
$$

因此可知

$$
\begin{array} { c } { { \displaystyle { \sum { R _ { i } } / { N _ { c , i } } = \sum _ { N _ { c , i } } ^ { } \left( r ^ { \prime } c _ { r , i } \right) } = \sum _ { i } ^ { } \left[ \left( t - A w _ { i } x / N _ { c , i } \right) c _ { r , i } \right] } } \\ { { { } } } \\ { { = \displaystyle { \sum \left[ \left( A w _ { i } c _ { t , i } - A w _ { i } x / N _ { c , i } \right) c _ { r , i } \right] } } } \\ { { { } } } \\ { { { } = \displaystyle { \frac { A w _ { i } N _ { c , i } - A w _ { i } x / N _ { c , i } \sum _ { c , i } } { N _ { c , i } } } } } \\ { { { } } } \\ { { { } = A w _ { i } - \displaystyle { \frac { A w _ { i } x ^ { 2 } } { N _ { c , i } ^ { 2 } } } = A w _ { i } \left( 1 - \displaystyle { \frac { x ^ { 2 } } { N _ { c , i } ^ { 2 } } } \right) } } \end{array}
$$

一般情况下，PN 码都是由 $\mathbf { \nabla } _ { m }$ 序列发生器产生，因此，$\left| x \right| < \left| N _ { c , i } \right| , 1 - \mathrm {  { \chi ^ { 2 } } } _ { N _ { c , i } ^ { 2 } } > 0$ 当 $w _ { i } = + 1$ 时 $\sum R _ { b } \mathrm { ~ / ~ } N _ { c , i } > 0$ 当 $w _ { i } = - 1$ 时，$\sum R _ { b } / N _ { c , i } < 0$ ，因此，判决规则如下：

$$
{ w _ { i } } ^ { \prime } \mathrm { = } \left\{ { + 1 , \sum _ { k } } ^ { } { R _ { i } / N _ { c , i } } \geq 0 \right.
$$

# 3 MSAC攻击防御能力分析

由随机化的PN码所调制的已标记数据流在频域和时域中都显示出类似白噪声的模式，MSAC攻击者难以在频域和时域中检测到流水印的存在性。

MSAC攻击的有效性所基于的事实是，DSSS流水印重复使用相同的PN码来扩展信号（即水印）的每个水印位。而在PNCR-MAR方法中，每个信号位由不同的PN码来扩展，这些PN码不但码值不一样，且长度也不同。

本章分析中涉及到的各符号的含义与第2章描述的相同，假设信号位 $w _ { i }$ 和 $w _ { j } \ ( i \neq j )$ 是独立的。调制后的水印信号可以写成

$$
w ^ { s } = \left( w _ { 0 } c _ { t , 0 } , w _ { 1 } c _ { t , 1 } , \cdots , w _ { l - 1 } c _ { t , l - 1 } \right)
$$

$$
\mathbf { \Psi } = ( w _ { 0 } c _ { t , 0 , 0 } , . . . w _ { 0 } c _ { t , 0 , N _ { c , 0 } - 1 } , w _ { 1 } c _ { t , 1 , 0 } , . . . , w _ { 1 } c _ { t , 1 , N _ { c , 1 } - 1 } ,
$$

$$
w _ { l - 1 } c _ { t , l - 1 , 0 } , . . . , x _ { l - 1 } c _ { t , l - 1 , N _ { c , l - 1 } - 1 } )
$$

由于 $w _ { i } c _ { t , i , j }$ 是独立且相同分布的，因此 $P ( w _ { i } c _ { t , i , j } = A ) = 1 / 2$ 和$P ( w _ { i } c _ { t , i , j } = - A ) = 1 / 2$ ，因此 $E ( w _ { i } c _ { t , i , j } ) = 0$ 和标准偏差 $\sigma { = } A$ 。以下公式可用于估计由 $\boldsymbol { w ^ { s } }$ 表示的时间序列的自相关：

$$
r ( \gamma ) = 1 / ( l - \gamma ) \sum _ { i = 0 } ^ { l - 1 - \gamma } ( a _ { i _ { j } } a _ { i _ { j + \gamma } } )
$$

其中： $\gamma$ 是时移， $a _ { i _ { j } } = w _ { i } c _ { t , i , j }$ 是 $\boldsymbol { w ^ { s } }$ 的第 $i$ 项，且 $i \in [ 0 , l - 1 ]$ ，$j \in [ 0 , N _ { c , i } - 1 ]$ 0

MSAC攻击方法通过计算 $E ( r ^ { 2 } ( \gamma ) )$ 来检测 DSSS 流水印的存在性。 $r ^ { 2 } ( \gamma )$ 是扩展信号 $\boldsymbol { w ^ { s } }$ 和具有时移的信号 $\boldsymbol { w } ^ { s }$ 的平方自相关。通过计算 $E ( r ^ { 2 } ( \gamma ) )$ ，将出现周期为 $l$ 的周期性峰值。

当 $\gamma = 0$ 时，从式(14)(15)可知

$$
r ( 0 ) = \frac { 1 } { l } \sum _ { i = 0 } ^ { l - 1 } ( w _ { i } c _ { t , i , j } w _ { i } c _ { t , i , j } ) = \frac { 1 } { j } \sum w _ { i } ^ { 2 } c _ { t , i , j } ^ { 2 }
$$

因 ${ w _ { i } } ^ { 2 } = A ^ { 2 }$ ， $c _ { t , i } ^ { 2 } = 1$ ，那么有 $r ( 0 ) = A ^ { 2 }$ 和 $E ( r ( 0 ) ) = A ^ { 4 }$ 。

当 $\gamma \neq 0$ 时，从式(14)(15)可知

$$
r ( \gamma ) = \frac { 1 } { l - \gamma } \sum _ { i = 0 } ^ { l - 1 - \gamma } ( a _ { i _ { j } } a _ { i _ { j + \gamma } } )
$$

$$
= \frac { 1 } { l - \gamma } ( w _ { 0 } c _ { t , 0 } w _ { \gamma } c _ { t , \gamma } + . . . + w _ { l - 1 - \gamma } c _ { t , l - 1 - \gamma } w _ { l - 1 } c _ { t , l - 1 } )
$$

$c _ { t , i }$ 是PN码集所选取的第 $i$ 个PN码，用于扩展第 $i$ 个水印位，因此有 $c _ { t , i } \neq c _ { t , j }$ （如果 $i \neq j$ )。当 $\gamma \neq 0$ 时， $E ( c _ { t , i } c _ { t , i + \gamma } ) \approx 0$ ，因此，有 $E ( w _ { i } c _ { t , i , j } w _ { i + \gamma } c _ { t , i + \gamma , j } )$ $= E ( w _ { i } w _ { i + \gamma } ) E ( c _ { t , i , j } c _ { t , i + \gamma , j } ) = 0$ 和 $r ( \gamma ) = 0$

$( \gamma \neq 0 )$ 。因此， $E ( r ^ { 2 } ( \gamma ) ) = 0$ ? $\stackrel { \prime } { \mathop { \cdot } } \gamma \neq 0$ ）。

由上可知， $E ( r ^ { 2 } ( \gamma ) )$ 的均值为

$$
E ( r ^ { 2 } ( \gamma ) ) \approx \{ { A ^ { 4 } , \gamma = 0 \ } \atop 0 , \gamma \neq 0 
$$

式(18)表明本文所提的PNCR-MAR方法所调制的数据流中不会出现周期性峰值，只在 $\gamma = 0$ 时显示出一个峰值，这与在文献[12]中所提出的基于同一PN码的DSSS流水印技术不同，对于后者，MSAC攻击方法可发现和检测到目标数据流中所嵌入的DSSS流水印的自相似性，然而，由于PNCR-MAR方法所调制的目标数据流中不会出现周期性峰，因此，PNCR-MAR方法在追踪业务流时的隐蔽性较好。

# 4 MSAC攻击防御实验结果与分析

为测试PNCR-MAR方法的MSAC攻击防御能力，搭建MSAC攻击防御实验环境。

# 4.1MSAC攻击防御实验环境搭建

由于DSSS流水印技术采用NS-2网络模拟器进行实验测试，为保持可比性，本文也采用NS-2网络模拟器来搭建测试环境来测试PNCR-MAR方法的MSAC攻击防御能力。实验中使用在互联网占主导地位的TCP数据流[22]进行测试。

![](images/1436c1f62137c3b575f6a8577a392c182c76b7a2e33a9bac0612a4d684ce4f43.jpg)  
Fig.4NS-2 simulation test environment

图4给出了NS-2模拟器中所采用的拓扑结构。其中节点 $n _ { 6 }$ 和节点 $n _ { 7 }$ 为Mix节点，其所使用的批处理策略有简单代理（simple proxy）、计时 mix（timed mix）和 stop-and-go 或连续mix，如表1所示。

表1mix节点的批处理策略  
Table 1Batch processing strategies for mix nodes   

<html><body><table><tr><td>序号</td><td>名称</td><td>可调参数</td><td>算法</td></tr><tr><td>S</td><td>简单代理</td><td>没有</td><td>没有批处理(或包乱序)</td></tr><tr><td>S</td><td>计时mix</td><td><t></td><td>如果计时器周期t过期，就将队列中所有 数据流发出</td></tr><tr><td>S</td><td>stop-and-go mix</td><td></td><td>为每个数据流分配一个延迟（期限)，满 <μ,g²>足均值μ和方差g²的分布，当期限到达 就将该数据包发出</td></tr></table></body></html>

在实验时，目标FTP数据流从节点 $n _ { 0 }$ 流到节点 $n _ { 9 }$ 。干扰器使用恒定比特率（constantbit rate，CBR）的UDP 数据流来调制目标FTP数据流以嵌入水印信息，其中CBR数据流从节点 $n _ { 1 }$ 到节点 $n _ { 4 }$ ，与目标FTP数据流在节点 $n _ { 2 }$ 和节点 $n _ { 3 }$ 之间共享同一链路。根据TCP流控制机制，当CBR流速率增加时，FTP流速率就会降低，而当CBR流速率降低（如没有CBR流量的干扰）时，FTP流速率就会增加。节点 $n _ { 5 }$ 为攻击者节点，该节点负责收集已标记数据流，并进行MSAC攻击。

测试中，当被PN码扩展过后的扩展水印信息的一个码片是 $^ { \circ } { + } 1$ 时，节点 $n _ { \mathrm { { l } } }$ 到节点 $n _ { 4 }$ 的CBR流量就关闭，当该码片是-1时，节点 $n _ { \mathrm { { l } } }$ 到节点 $n _ { 4 }$ 的CBR流量就开启。开启和关闭的时间长度与码片时长保持一致。这样就可使用CBR流量来调制目标FTP数据流的速率来嵌入水印信息。

为从已标记数据流中恢复出其中嵌入的原始水印信息，必须首先获得FTP 流速率的时间序列。根据奈奎斯特一香农采样理论，为恢复扩展水印信息，采样周期应比码片时长的

![](images/7e1f36b7231abd7d57da1080205c6715f5ea37431a28e557a931b276312e22a9.jpg)  
图4NS-2 模拟测试环境

一半还要小。

实际中，由于互联网的复杂性和动态性，发送者和接收者之间的时延很难准确预测。实验中，为同步发送者和接收者之间的PN码，使用延迟的近似估计值，与数据流路径上的累计传播和排队延迟相近。接着使用基于匹配滤波器的方法搜寻特定范围内的最佳匹配，实验中所使用的范围为[-0.5,0.5] s。

# 4.2 检测率测试

因为PNCR-MAR方法主要是从PN码随机化（不但数值随机，长度也不同)的角度对原始DSSS流水印技术做优化，本节主要测试不同的PN码平均长度对检测率（检测率是指从目标数据流中正确检测出其中所嵌入的水印信息的比率）的影响。由图5可看到，检测率随着PN码平均长度的增长而增加，较长的PN码平均长度可以获得较高的检测率，因此，可以使用较长的PN码来对抗嘈杂网络环境对流水印的影响而获得更好的追踪效果。

# 4.3 误报率测试

为测试PNCR-MAR方法在应用于DSSS流水印技术之后对于DSSS流水印技术的误报率（误报率是指从目标数据流中错误检测出其中所嵌入的水印信息的比率)造成的影响，本实验使用码片时长为 $0 . 5 \mathrm { ~ s ~ }$ ，PN码平均长度为7。DSSS流水印技术误报率的理论值为 $2 ^ { 1 / l }$ ，其中 $l$ 为水印长度[11]。

PNCR-MAR方法在不同水印长度情况下的误报率对比如图6所示，误报率随着水印长度呈指数级降低，符合文献[12]中的分析结果，且PNCR-MAR方法与原始DSSS流水印技术的误报率相近，因此，PNCR-MAR方法在抵御MSAC攻击的同时，并没有增加DSSS流水印技术的误报率。

![](images/b01ee9bf108c99451b72352e6c40d945abb62165521ca50e7852164859dd7728.jpg)  
图5检测率 Fig.5Detection rate   
图6误报率对比  
Fig.6Comparison of false positive rates

# 4.4MSAC攻击防御能力测试

本节测试PNCR-MAR方法的MSAC攻击防御能力。实验中PN码平均长度为7，水印长度为7，干扰数据流的CBR数据流速率为1.2Mbps，码片时长为 $0 . 5 \mathrm { ~ s ~ }$ ，采样间隔为0.1秒。为对比DSSS 流水印技术和PNCR-MAR方法在MSAC攻击面临的隐蔽性，计算嵌入水印信息后的已标记数据流在不同时移情况下的均方自相关并进行归一化（ $r ^ { 2 }$ ）处理后，如图7所示。

如图7(a)所示，采用DSSS流水印技术嵌入水印信息的已标记数据流的流速率时间序列的均方自相关确实出现了周期性峰值，故MSAC攻击可有效检测到DSSS流水印的存在性。

如图7(b)所示，使用PNCR-MAR方法嵌入水印信息的已标记数据流的流速率时间序列的均方自相关没有出现周期性峰值，这是因为PNCR-MAR方法采用PN码随机化思路，对于不同的水印位采用不同的PN码进行扩展，消除了已标记数据流的自相关性，故而其流速率的均方自相关并不出现周期性峰值，因此可抵御MSAC攻击的检测发现。

![](images/40b8a471630e385a38f9aecc6bc7a1aeef7058ef0bac6b62952b7e92b275d1c1.jpg)  
Fig.7Estimation of normalized mean-square autocorrelation

此外，为测试PNCR-MAR方法对MSAC攻击的隐蔽性，使用检测率和误报率作为衡量标准，并使用受试者工作特征（receiveroperatingcharacteristic，ROC）曲线（以检测率为横坐标，以误报率为纵坐标绘制的曲线）表示二者之间的关系。当攻击者检测目标数据流是否含有DSSS流水印时，他希望是低误报率的同时，获得高检测率。理想情况下，为抵御MSAC攻击的检测，应使得检测率和误报率一样高。

如图8所示，可以看到PNCR-MAR方法下的ROC曲线与理想的ROC曲线较为吻合，随着检测率的增加，误报率趋向于线性增长，体现了PNCR-MAR方法的MSAC攻击防御能力，这使得MSAC攻击者的检测结果是没有价值的。

![](images/0bd73be92421dd75400cd2870892d24acc1472d3598b2c38396bea04c37169b4.jpg)  
图8ROC曲线Fig.8ROC curves

# 5 结束语

针对PN码正交化方法存在的正交PN 码难以获取的问题，为提高DSSS流水印技术的MSAC攻击防御能力，提出基于PN码随机化的MSAC攻击防御方法。理论分析及实验结果表明，PNCR-MAR方法可有效抵御MSAC攻击的检测发现，且克服了PN码正交化的应用难题。

后继拟研究PN码随机化方法在抵御多流攻击方面的有效性。此外，Luo 等人[23]提出基于序贯概率比检验（sequentialprobabilityratiotesting，SPRT）的DSSS流水印检测方法，还提出基于TCP流控制机制的DSSS流水印移除方法，使得终端用户可有效移除数据流中的DSSS流水印，且不需要中间路由器、代理或中继节点的支持。对于该检测和移除方法，目前尚无有效防御手段，后继拟研究相应的防御手段，进一步提高DSSS流水印技术的隐蔽性。

# 参考文献：

[1]Iacovazzi A,Elovici Y.Network flow watermarking:a survey[J]. IEEE Communications Surveys & Tutorials.2017,19(1):512-530.   
[2]Lu Tianbo,Guo Rui,Zhao Lingling,et al.A systematic review of network flow watermarking in anonymity systems [J]. International Journal of Security and Its Applications.2016,10(3):129-138.   
[3]Khan S,Gani A,Wahab A WA,et al.Network forensics:review, taxonomy,and open challenges [J]. Journal of Network and Computer Applications，2016,66:214-235.   
[4]Pyun YJ,Park Y H,Wang Xinyuan,et al.Tracing traffic through intermediate hosts that repacketize flows [C]// Proc of the 26th IEEE International Conference on Computer Communications.Piscataway,NJ: IEEE Press,2007: 634-642.   
[5]Pyun YJ，Park Y H,Reeves D S，et al.Interval-based flow watermarking for tracing interactive trafic [J]. Computer Networks. 2012,56(5): 1646-1665.   
[6]Wang Xinyuan, Chen Shiping,Jajodia S.Network flow watermarking attack on low-latency anonymous communication systems [C]//Proc of the 28th IEEE Symposium on Security and Privacy. Washington DC: IEEE Computer Society,2007:116-130.   
[7]Wang Xinyuan,Reeves D S.Robust correlation of encrypted attack traffic through stepping stones by flow watermarking [J].IEEE Trans on Dependable and Secure Computing.2010,8(3): 434-449.   
[8]Houmansadr A,Kiyavash N,Borisov N.Non-blind watermarking of network flows [J]. IEEE/ACM Trans on Networking.2014,22(4): 1232-1244.   
[9]Houmansadr A,Kiyavash N,Borisov N.RAINBOW:a robust and invisible non-blind watermark for network flows [C]//Proc of the 16th Annual Network & Distributed System Security Symposium. San Diego: Internet Society,2009:224-236.   
[10] Houmansadr A,Borisov N.SWIRL:a scalable watermark to detect correlated network flows [C]//Proc of the 18th Annual Network & Distributed System Security Symposium. San Diego: Internet Society, 2011: 1-15.   
[11]张连成，王振兴，刘慧生．网络流水印技术研究进展[J].计算机科 学，2011，38(11):7-11,42.(Zhang Liancheng，Wang Zhenxing,Liu Huisheng. Survey on network flow watermarking technologies [J]. Computer Science,2011,38(11): 7-11,42.)   
[12] Yu Wei,Fu Xinwen,Graham S,et al.DSSS-Based flow marking technique for invisible traceback [C]// Proc of the 28th IEEE Symposium on Security and Privacy.Washington DC:IEEE Computer Society,2007: 7-21.   
[13]Jia Weijia,TsoFP,Ling Zhen,etal.Blind detection of spread spectrum flow watermarks [J]. Security and Communication Networks.2013,6 (3): 257-274.   
[14] Jia Weijia,Tso FP,Ling Zhen,et al.Blind detection of spread spectrum flow watermarks [C]//Proc of the 28th IEEE International Conference onComputer Communications. Washington DC:IEEE Computer Society,2009:2195-2203.   
[15]张连成，王禹，孔亚洲，等．网络流水印安全威胁及对策综述[J]. 计算机研究与发展,2018,55(8):1785-1799.(Zhang Liancheng,Wang Yu,Kong Yazhou,et al.Survey on security threats and countermeasures of network flow watermarking [J]. Journal of Computer Research and Development,2018,55(8):1785-1799.)   
[16] Kiyavash N,Houmansadr A,Borisov N.Multi-flow attacks against network flow watermarks:analysis and countermeasures [J].Columbia LawReview.2012,97:1343-2470.   
[17]Kiyavash N,Houmansadr A,Borisov N.Multi-flow attacks against network flow watermarking schemes [C]//Proc of the 17th USENIX Security.Berkeley:USENIX Association,2008:307-320.   
[18] Zhang Liancheng,Wang Zhenxing,Wang Qinglong,et al.MSAC and multi-flow attacks resistant spread spectrum watermarks for network flows [C]// Proc of the 2nd IEEE International Conference on Information and Financial Engineering. Piscataway,NJ:IEEE Press, 2010:438-441.   
[19] Zhang Liancheng，Wang Zhenxing,Wang Yu,et al. Interval-based spread spectrum watermarks for tracing multiple network flows [C]// Proc of the 12th IEEE International Conference on Communication and Technology.Piscataway,NJ:IEEE Press,2010:394-397.   
[20]张连成，王振兴，孙建平．基于时间间隔的扩频流水印技术[J].计 算机应用研究，2011，28(8):3049-3053.(Zhang Liancheng，Wang Zhenxing,Sun Jianping. Interval-based spread spectrum watermarking scheme for tracing network flows [J].Application Research of Computers,2011,28(8):3049-3053.)   
[21]张璐，罗军舟，杨明，等．基于时隙质心流水印的匿名通信追踪技术 [J]．软件学报，2011,22(10):2358-2371.(Zhang Lu,Luo Junzhou, Yang Ming,et al.Interval centroid based flow watermarking technique for anonymous communication traceback [J].Journal of Software,2011, 22(10):2358-2371.)   
[22] Paxson V.Growth trends in wide-area TCP connections [J].IEEE Network，1994,8(4): 8-17.   
[23] Luo Xiapu,Zhang Junjie,Perdisci R,et al.On the secrecy of spread-spectrum flow watermarks [C]// Proc of the 15th European Symposium on Research in Computer Security.Athens: Springer,2010: 232-248.