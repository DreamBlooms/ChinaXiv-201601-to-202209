# 面向蓝牙语音加密传输的波形码本设计

洪鹏程，黄一才，郁滨(信息工程大学，郑州 450001)

摘要：针对蓝牙语音信号加密后失去语音特征而不能通过语音信道传输的问题，建立蓝牙语音加密数据传输模型，提出一种面向蓝牙语音加密传输的波形码本生成算法。该算法以子载波调制生成初始调制码本，训练数据得到解调码本，通过设计末位淘汰机制的粒子对算法寻找最优码本。仿真分析表明，本文码本生成算法具有收敛速度快的优势，能够生成不同比特传输速率和符号错误率低的波形码本。实验结果表明，在蓝牙中使用该波形码本传输数据具有较低符号错误率。

关键词：蓝牙；波形码本；波形符号；子载波调制；粒子对算法 中图分类号：TP309.1 doi: 10.19734/j.issn.1001-3695.2018.10.0749

Waveform codebook design for Bluetooth voice encryption

Hong Pengcheng, Huang Yicai, Yu Bin (Information Engineering University,Zhengzhou 45ooo1,China)

Abstract: Aiming atthe problemthatthe Bluetooth voice signalcannot betransmited through the voicechannel after being encrypted,this paper establishesa Bluetoth voice encryptiondata transmissonmodel,and proposesa waveformcodebook generationalgorithm forBluetooth voiceencryption transmission.The algorithmuses subcarier modulation to generate the initial modulation codebook,and trains data toobtain the demodulation codebook.This paperdesigned the Particle-pair algorithm with the last elimination mechanism to find theoptimal codebook.Simulation analysis shows thatthe proposed algorithmhas the advantages offastconvergence rateand cangenerate waveform codebooks with diferent bit transmission rate and low symbol errorrate.Experiments show that using this waveform codebook to transmit data in Bluetoth has low symbol error rate.

Key Words: Bluetooth; waveform codebook; waveform symbol; subcarrier modulation; particle-pair algorithm

# 0 引言

蓝牙是一种短距离无线通信技术，已经成为手机、电脑等智能设备的标配，能够使蓝牙终端设备方便地与不同型号的手机连接并拨打免提电话。针对移动语音通信存在的安全问题[1]，在蓝牙终端设备中实现对语音加密传输是一种安全可靠的解决方案。

蓝牙与移动通信网均存在数据和语音两种信道，其数据信道传输语音难以达到实时性要求，而语音信道均使用了语音编解码器。蓝牙语音采用连续可变斜率增量调制（continuous variable slope delta modulation，CVSD）[2]，每个采样值仅采用1bit量化；移动通信网使用有损的、有记忆的压缩编解码器[3]，且增加了语音激活检测（voice activitydetection，VAD)，这两种编解码器均不能传输不具备语音特征的加密语音信号。

目前国内外学者主要对在移动通信网语音信道上传输任意数据进行了深入研究，其核心思想是将数据转换成类语音后在语音信道上传输，具体又可分为语音合成、频率调制和波形码本三类[16]。

语音合成方案是将数据映射成语音特征参数合成类语音，文献[4,5]将数据映射成基音频率、线性频谱对和帧能量，文献[6]基于共振峰模型设计映射关系，但这类方案参数提取复杂，在嵌入式系统中难以达到实时性要求。在使用频率调制方案中，文献[7]提出的启发调制算法传输速率较低，文献[8\~10]基于正交频分复用技术（orthogonal frequencydivisionmultiplexing，OFDM)，将数据映射到语音频段的子载波生成类语音，但将其应用到蓝牙终端设备时，调制波形多次经过编解码器后出现较大扭曲，解调错误率较高。

相比前两种方案性能，波形码本方案具有计算量小和存储空间小的特点，波形码本能够实现"数据一符号一数据"传输，并由初始码本经遗传算法优化得到[11,12]。文献[13,14]直接选取人类语音筛选得到最优码本，但文献[11\~14]均是仅针对指定的某种声码器设计码本。文献[15]建立波形符号在信道传输前后的平均欧氏距离分布概率模型，以此根据空间模型生成波形码本，实现了数据在声码器上的传输，但该方法忽视了声码器的自动幅值调节特性，使得欧氏距离出现偏差影响解调。文献[16]使用模式搜索算法设计码本，将数据映射在码本上后可以在多种不同声码器上传输，但是方案没有考虑蓝牙语音编解码的影响，不能直接应用到蓝牙终端。

与遗传算法、模式搜索等优化算法相比，粒子群算法具有实现简单、收敛速度快和受所求问题维度影响较小等特点[17]。纪震[17]在粒子群基础上设计了种群规模为2 的粒子对算法，该算法在图像码书更新、基因聚类等应用中表现良好，在求解高维复杂问题上表现出了特别的优势。

综上所述，码本设计是使用码本传输蓝牙加密语音信号的关键，本文提出一种面向蓝牙语音加密传输的波形码本生成算法。该算法以子载波调制生成类语音作为初始调制码本，通过设计末位淘汰机制的粒子对算法，寻找能通过语音信道且符号错误率低的波形码本。

# 1 模型建立

为方便描述，本文相关符号及其含义如表1所示。

# 1.1相关定义

定义1波形符号指包含L个采样值的类语音片段，用$S = \{ s _ { 0 , } , s _ { 1 } , \cdots , s _ { ( L - 1 ) } \}$ 表示。

定义2调制码本指与数据集 $\{ 0 , 1 , 2 , \cdots , N - 1 \}$ 一一对应的波形符号集 $\{ S _ { 0 } , S _ { 1 } , \cdots , S _ { N - 1 } \}$ ，用 $C A$ 表示，在发送语音时用于实现类语音调制。

定义3解调码本指调制码本 $C A$ 中的每个波形符号 $S _ { i }$ $( 0 \leq i \leq N - 1 )$ 经过大量随机数据在语音信道传输后，接收端对应波形符号的所有输出平均值组成的集合 $\{ S O _ { 0 } , S O _ { 1 } \cdots S O _ { N - 1 } \}$ ，用 $\scriptstyle { C B }$ 表示。

波形码本包括调制码本和解调码本。

定义4比特传输速率指使用波形码本在语音信道每秒能够传输的比特数，用 $R$ 表示。

定义5符号错误率指经语音信道传输后解调错误波形符号数占总传输波形符号数的比例，用SER表示。

定义6最优码本指用于传输数据时优化能得到的符号错误率最低的波形码本。

定义7子载波指被调制用来传输信号、有固定频率的正/余弦波。

表1符号及含义  
Table 1Symbol and meaning   

<html><body><table><tr><td>符号</td><td>含义</td><td>符号</td><td>含义</td></tr><tr><td>CA</td><td>调制码本</td><td>CB</td><td>解调码本</td></tr><tr><td>n</td><td>码本表示的比特数</td><td>N</td><td>码本中波形符号数量</td></tr><tr><td>L</td><td>波形符号采样点数</td><td>M</td><td>子载波频率数量</td></tr><tr><td>SER</td><td>符号错误率</td><td>S</td><td>波形符号</td></tr><tr><td>S</td><td>经语音信道传输后的波形 符号</td><td>SO</td><td>接收波形符号的均值</td></tr><tr><td>R</td><td>比特传输速率</td><td>fs</td><td>语音采样率</td></tr><tr><td>E</td><td>求均值</td><td>△f</td><td>子载波频率间隔</td></tr></table></body></html>

# 1.2数据传输模型

根据蓝牙终端语音数据传输过程，建立数据传输模型如图1所示，包括数据发送、数据传输和数据接收三个阶段。因模型传输对象是二进制码流，取 $N = 2 ^ { n }$ （n为整数）方便$C A$ 与比特流建立映射关系。

![](images/6bceb16852872c044f9bcc298f3196e279fcfc6969ad5cad7dcf97fb8ea52aa2.jpg)  
图1数据传输模型  
Fig.1 Data transmission model

在发送数据时，将分好组的二进制转换成数据 $i$ ，然后映射成对应的波形符号，即 $i \to S _ { i } ( 0 \leq i \leq N - 1 )$ ，最后将不同组的波形符号按序拼接成连续类语音 $[ S _ { i _ { 1 } } ^ { 1 } , S _ { i _ { 2 } } ^ { 2 } , \cdots S _ { i _ { k } } ^ { k } \cdots ]$ 发送。其中：$k \geq 1$ ，表示符号的发送序号； $i _ { k }$ 表示符号在码本中的序号。

依据数据传输模型，波形符号 $S _ { i _ { k } } ^ { k }$ 经语音信道传输后的波形为 $S _ { i _ { k } } ^ { k }$ ，其值主要由 $S _ { i _ { k } } ^ { k }$ 决定，但在 $S _ { i _ { k } } ^ { k }$ 之前传输的波形符号$\{ S _ { i _ { 1 } } ^ { 1 } , S _ { i _ { 2 } } ^ { 2 } \cdots S _ { i _ { k - 1 } } ^ { k - 1 } \}$ 也会使得波形 $S _ { i _ { k } } ^ { k }$ 波形出现不同程度的差异。因此，收方直接使用 $C A$ 与 $S _ { i _ { k } } ^ { k }$ 进行比对判决发送的波形并不能达到最好效果。

基于此，为提高解调成功率，使用解调码本 $C B$ 与接收波形 $S _ { i }$ 比对来判决发送的波形，以实现 $S  S O _ { i }  \hat { i }$ $( 0 \leq i \leq N - 1 )$ 。判决方法是通过求接收的波形符号 $S _ { \mathbf { \Phi } _ { i } } ^ { k }$ 与符号集合 $\{ S O _ { i } \}$ 的余弦值来实现匹配，余弦值越大，说明两个波形相似度越高，将余弦值最大的对应波形解调为发送的波形，再还原出发送的数据，即 $\hat { i } = \arg \operatorname* { m a x } _ { i } [ \cos ( S O _ { i } , S _ { _ i } ^ { k } ) ]$ 。

评价一个波形码本的指标包括比特传输速率、计算量、存储量和符号错误率。其中，前三个指标由码本规模决定。本文对规模设定为 $N \times L$ 的码本生成与优化，即在码本规模确定时得出符号错误率低的波形码本。此外，还研究了码本规模对符号错误率的影响。

# 2 波形码本生成算法

以子载波调制生成类语音波形组成初始调制码本，训练数据生成解调码本，通过设计粒子编码、优化目标函数和粒子更新机制，使用末位淘汰机制的粒子对算法寻找最优码本。

# 2.1码本初始化

# 2.1.1调制码本初始化

为使波形符号满足语音频段要求$\ \cdot \ \left[ f _ { \operatorname* { m i n } } , f _ { \operatorname* { m a x } } \right] = \left[ 3 0 0 H z , 3 4 0 0 H z \right] .$ )，使用子载波调制生成类语音作为波形符号。在 $\left[ f _ { \operatorname* { m i n } } , f _ { \operatorname* { m a x } } \right]$ 频率范围内，以 $\Delta f$ 为相等频率间隔设置子载波频率值，则共需要子载波频率值的数量 $M$ 为

$$
{ \cal M } = \left\lfloor \frac { f _ { \mathrm { m a x } } - f _ { \mathrm { m i n } } } { \Delta f } \right\rfloor + 1
$$

其中每个频率值分别对应一个正弦和余弦子载波。

波形符号 ${ S } _ { i } ~ ( 0 \leq i \leq N - 1 )$ 初始生成流程如下。

a）随机生成子载波幅值 $G _ { i }$ ：

$$
G _ { i } = \{ z _ { i 0 } , z _ { i 1 } , \cdots , z _ { i ( 2 M - 2 ) } , z _ { i ( 2 M - 1 ) } \}
$$

其中： $z _ { i j }$ 0 $0 \leq i \leq N - 1 , 0 \leq j \leq 2 M - 1 )$ 是从[-1,1]区间的随机数，当

$j$ 为偶数和奇数时 $z _ { i j }$ 分别对应正弦和余弦子载波的幅值，则由子载波调制得到的类语音波形时域表达式 $f _ { i } ( t )$ 为

$$
\mathbf { \Sigma } ( t ) = \left\{ \begin{array} { c } { z _ { i 0 } \sin ( 2 \pi f _ { \operatorname* { m i n } } t ) + z _ { i 1 } \cos ( 2 \pi f _ { \operatorname* { m i n } } t ) + } \\ { z _ { i 2 } \sin ( 2 \pi \left( f _ { \operatorname* { m i n } } + \triangle f \right) t ) + z _ { i 3 } \cos ( 2 \pi \left( f _ { \operatorname* { m i n } } + \triangle f \right) t ) + } \\ { \cdots } \\ { z _ { i ( 2 M - 4 ) } \sin ( 2 \pi \left( f _ { \operatorname* { m i n } } + ( M - 2 ) \triangle f \right) t ) + z _ { i ( 2 M - 3 ) } \cos ( 2 \pi \left( f _ { \operatorname* { m i n } } + ( M - 2 ) \triangle f \right) t ) + } \\ { z _ { i ( 2 M - 2 ) } \sin ( 2 \pi \left( f _ { \operatorname* { m i n } } + ( M - 1 ) \triangle f \right) t ) + z _ { i ( 2 M - 1 ) } \cos ( 2 \pi \left( f _ { \operatorname* { m i n } } + ( M - 1 ) \triangle f \right) t ) } \end{array} \right.
$$

b)以语音采样率 $f _ { s }$ 对 $f _ { i } ( t )$ 从 $\scriptstyle t = 0$ 时开始采样，取前L个采样值作为 $s$ 。

c）功率归一化， $S = \frac { S } { | S | }$ ，|S|表示向量的模，即得到一个采样点数为 $L$ 的波形符号，结束。

为使每个波形符号的功率一致，在得到波形符号后，需要对其功率进行归一化运算。

对波形符号的初始生成过程进行分析可知：a)子载波幅值 $G = \{ z _ { 0 } , z _ { 1 } , { } ^ { \cdots } , z _ { ( 2 M - 2 ) } , z _ { ( 2 M - 1 ) } \}$ 决定了波形符号 $s \ ; \ \mathsf { b } )$ 随机生成子载波幅值，生成的波形符号满足语音频段要求；c随机生成$N$ 组子载波幅值，可以得到 $N$ 个波形符号组成初始调制码本$C A$ ；d)最终得到波形符号 $s$ 的采样值位于[-1,1]间，在使用时需要将其转换成蓝牙支持的16bit位宽。

# 2.1.2解调码本初始化

通过初始调制码本 $C A$ 在语音信道传输大量随机数据，从而训练得到初始解调码本 $\scriptstyle { C B }$ 。将数据需要透传的声码器用Vocoder,Vocoder,,VocoderH表示。因此数据经历的编解码组合为CVSD+Vocoder、CVSD+Vocoder、..、CVSD+VocoderH 等H种。

![](images/52c145b0800fdea5a8d26fda91d6078e2d98b501a2a26bdf15e898534271d332.jpg)  
图2解调码本生成过程  
Fig.2Generation process of demodulation codebook   
图3码本生成过程  
Fig.3Generation process of codebook

解调码本生成过程如图2所示。首先生成 $N _ { t o t }$ 个 $\left[ 0 , N - 1 \right]$ 之间的随机数，利用 $C A$ 映射成波形符号并组合成连续的类语音，分别在H个编解码组合中传输；然后求解 $S _ { i } ( 0 \leq i \leq N - 1 )$ 经每种组合传输后的所有输出值平均值作为 $S O _ { i }$ ，进而得到$C B$ 。

# 2.2码本优化

由2.1节分析可知，如图3所示，生成子载波幅值即可得到相应的调制码本和解调码本，进而可以计算码本的 $S E R$ 。因此，问题转换为求使得SER最低的子载波幅值，具体如下。

子载波调制 训练子载波幅值 调制码本 解调码本

2.2.1粒子编码

在优化过程中，使用每个粒子表示一个调制码本，故需将一个调制码本中所有波形符号的子载波幅值$G _ { 0 }$ ， $G _ { \mathrm { r } }$ …、 $G _ { N - 1 }$ 作为一个粒子的编码。

因此，将 $\mathrm { ~ N ~ }$ 组子载波幅值 $G _ { 0 } { \mathrm { : } }$ G、 $G _ { N - 1 }$ 按序排列可得到粒子编码，记为 $Z = \left( z _ { 0 0 } , z _ { 0 1 } , \cdots , z _ { \left( N - 1 \right) \left( 2 M - 1 \right) } \right)$ ，且 $Z$ 是一个2MN维向量，如表2所示。

表2粒子编码  
Table 2Particle coding   

<html><body><table><tr><td>Z00,Z01,,Z0(2M-1)</td><td>Z10,Z11,,Z1(2M-1)</td><td>：</td><td>Z(N-1)0,Z(N-1)1,*·,Z(N-1)(2M-1)</td></tr></table></body></html>

因为子载波幅值设定位于[-1,1]区间，粒子初始化时只需要从[-1,1]区间生成2MN个随机数作为 $Z = \left( z _ { 0 0 } , z _ { 0 1 } , \cdots , z _ { \left( N - 1 \right) \left( 2 M - 1 \right) } \right)$ ，而且该初始粒子对应一个初始调制码本。

# 2.2.2目标函数

判断粒子优劣时，先得到对应的解调码本。然后使用调制码本在 H 个不同编解码组合传输 $N _ { t o t a l }$ 个 $\left[ 0 , N - 1 \right]$ 之间的随机数，通过解调码本得到在不同组合中的解调错误数$N _ { e r r _ { 1 } } , \cdots , N _ { e r r _ { H } }$ ，计算其 $S E R$ 均值作为目标函数。

$$
D = \overline { { S E R } } = \frac { 1 } { H } \sum _ { j = 1 } ^ { H } \frac { N _ { e r r _ { j } } } { N _ { t o t a l } }
$$

$D$ 值越小,粒子性能越好。

# 2.2.3粒子更新机制

优化算法包含两对独立的粒子对 $\{ Z _ { 1 } ^ { ( k ) } , Z _ { 2 } ^ { ( k ) } \}$ 和 $\{ Z _ { 3 } ^ { ( k ) } , Z _ { 4 } ^ { ( k ) } \}$ ，其中 $k$ 表示粒子迭代次数。每次迭代过程中，每对粒子按如下操作更新：

按照 $V _ { t } ^ { k + 1 } = \omega V _ { t } ^ { k } + c _ { 1 } r _ { 1 } ( p _ { t } - Z _ { t } ^ { k } ) + c _ { 2 } r _ { 2 } ( p _ { g } - Z _ { t } ^ { k } )$ 更新速度，按照$Z _ { t } ^ { k + 1 } = Z _ { t } ^ { k } + V _ { t } ^ { k + 1 }$ 更新位置。其中： $r _ { \mathrm { i } }$ 与 $r _ { 2 }$ 为[0,1]之间的随机数；$c _ { 1 }$ 和 $c _ { 2 }$ 是学习因子； $\omega$ 是权重因子。设定粒子位置边界为[-1,1]，速度边界 $[ \nu _ { \mathrm { m i n } } , \nu _ { \mathrm { m a x } } ]$ 0

为使粒子有更好的搜索能力，对性能较差粒子对应调制码本中的波形符号进行末位淘汰并重新生成。具体实现过程如下：首先计算两个粒子目标函数值，取目标函数值较大者对应的粒子；然后计算该粒子对应码本的每个波形符号在H个编解码组合中的 $S E R$ 均值，即

$$
f ( i ) = \frac { 1 } { H } \sum _ { j = 1 } ^ { H } \frac { N _ { e r r _ { j } } ( i ) } { N _ { t o t a l } ( i ) } \mathrm { ~ , ~ } 0 \le i \le N - 1
$$

将 $f ( i )$ 最大值对应的波形符号判别为效果不好的波形符号$S _ { q }$ ：最后随机生成一个新的子载波幅值，将子载波幅值$G _ { S _ { q } } = ( z _ { S _ { q } 0 } ^ { t } , z _ { S _ { q } 0 } ^ { t } , \cdots , z _ { S _ { q } ( 2 M - 1 ) } ^ { t } )$ 在粒子相应位置替换。

按上述更新机制， $\{ Z _ { 1 } ^ { ( k ) } , Z _ { 2 } ^ { ( k ) } \}$ 和 $\{ Z _ { 3 } ^ { ( k ) } , Z _ { 4 } ^ { ( k ) } \}$ 分别按照粒子群算法最多迭代 $N _ { \mathrm { m a x } }$ 次后，将 $D$ 较低粒子重新组成精英粒子对 $\{ Z _ { 5 } ^ { ( k ) } , Z _ { 6 } ^ { ( k ) } \}$ ，继续迭代最多 $N _ { \mathrm { m a x } _ { 2 } }$ 次得到最优粒子 $Z _ { 7 }$ ，将 $Z _ { 7 }$ 对应码本作为最优解调码本。

# 2.2.4码本优化算法流程

引入末位淘汰机制的粒子对算法对码本进行优化，其流程如图4所示。

具体流程如下，其中 ${ p _ { t } } ^ { ( k ) }$ 保存当次迭代最优粒子， ${ p _ { g } } ^ { ( k ) }$ 保存自迭代以来全局最优的粒子。

a)设置 $j = 1$ ， $t _ { \mathrm { l } } = 1$ ， $t _ { 2 } = 2$ ，设置阈值 $\varepsilon$ 和最大迭代次数 Nmaxo

b)设置 $k = 0$ ，初始化粒子位置和速度，$Z _ { t } ^ { ( k ) } = \big ( z _ { 0 0 } ^ { t } , z _ { 0 1 } ^ { t } , \cdots , z _ { ( N - 1 ) ( 2 M - 1 ) } ^ { t } \big )$ 、 $V _ { t } ^ { ( k ) } = \big ( \nu _ { 0 0 } ^ { t } , \nu _ { 0 1 } ^ { t } , \cdots , \nu _ { ( N - 1 ) ( 2 M - 1 ) } ^ { t } \big )$ ，其中 $t = t _ { 1 } , t _ { 2 }$ 。

c)粒子 $Z _ { t } ^ { ( k ) }$ 运算得到调制码本 $C A _ { \iota } ^ { ( k ) }$ 。

d)将 $N _ { t o t }$ 个 $\left[ 0 , N - 1 \right]$ 之间的随机数映射到 $C A _ { t } ^ { ( k ) }$ 上在语音信 道传输，训练生成解调码本 $C B _ { t } ^ { ( k ) }$ 。

e)将 $N _ { t o t a l }$ 个 $\left[ 0 , N - 1 \right]$ 之间的随机数映射到 $C A _ { t } ^ { ( k ) }$ 上在语音信道传输，并使用 $C B _ { t } ^ { ( k ) }$ 解调。

f)计算每个粒子 $Z _ { t } ^ { ( k ) }$ 的目标函数值 ${ D _ { t } } ^ { ( k ) }$ ，计算${ D ^ { ( k ) } = \operatorname* { m i n } \{ { D _ { 1 } } ^ { ( k ) } , { D _ { 2 } } ^ { ( k ) } \} }$ ，将 $\boldsymbol { D } ^ { ( k ) }$ 其对应粒子作为局部最优粒子${ p _ { t } } ^ { ( k ) }$ ，将至今目标函数值最好粒子作为全局最优粒子 ${ p _ { g } } ^ { ( k ) }$ 。

$\mathrm { g ) }$ 若 ${ D ^ { ( k ) } < \varepsilon }$ ，结束。

h)设置 $k = k + 1$ ，更新粒子速度和位置，

$$
\begin{array} { r } { V _ { t } ^ { k + 1 } = \omega V _ { t } ^ { k } + c _ { 1 } r _ { 1 } ( p _ { t } - Z _ { t } ^ { k } ) + c _ { 2 } r _ { 2 } ( p _ { g } - Z _ { t } ^ { k } ) \ , \quad Z _ { t } ^ { k + 1 } = Z _ { t } ^ { k } + V _ { t } ^ { k + 1 } \ \mathrm { ~ c ~ o ~ n ~ s ~ t ~ } , } \end{array}
$$

i)若 ${ D _ { t _ { 1 } } } ^ { ( k - 1 ) } > { D _ { t _ { 2 } } } ^ { ( k - 1 ) }$ ，计算得出 $Z _ { t _ { 1 } } ^ { k - 1 }$ 中解调错误率最高符号$S _ { q _ { 1 } }$ ，重新随机生成粒子 $Z _ { t _ { 1 } } ^ { k }$ 中子载波幅值$G _ { q _ { 1 } } = ( z _ { S _ { q _ { 1 } } 0 } ^ { t _ { 1 } } , z _ { S _ { q _ { 1 } } 1 } ^ { t _ { 1 } } , \cdots , z _ { S _ { q _ { 1 } } ( 2 M - 1 ) } ^ { t _ { 1 } } )$ ；否则计算得出 $Z _ { t _ { 2 } } ^ { k - 1 }$ 中解调错误率最高符号 $S _ { q _ { 2 } }$ ，重新随机生成粒子 $Z _ { t _ { 2 } } ^ { k }$ 中子载波幅值$G _ { q _ { 2 } } = \big ( z _ { S _ { q 2 } } ^ { t _ { 2 } } 0 , z _ { S _ { q 1 } 0 } ^ { t _ { 2 } } , \cdots , z _ { S _ { q 2 } ( 2 M - 1 ) } ^ { t _ { 2 } } \big ) _ { \mathrm { ~ \tiny ~ c ~ } }$ （20

$\mathrm { j } )$ 若 $k < N _ { \operatorname* { m a x } }$ ，跳至步骤c)； $\{ Z _ { 5 } , Z _ { 6 } \}$

$\mathbf { k } )$ 得到较优粒子 $Z _ { j + 4 } = p _ { g } { } ^ { ( k ) } ( j = 1 , 2 , 3 )$ ， $j = j + 1$ ，若 $j = 2$ ， 则跳至步骤b)， $t _ { 1 } = 3 , t _ { 2 } = 4$ ；若 $j = 3$ ，则设置初始种群为 $\scriptstyle t = 5 , 6$ ， 设置 $N _ { \mathrm { m a x } } = N _ { \mathrm { m a x } 2 }$ ，跳至步骤c)；若 $j = 4$ ，结束。

![](images/b5e01d9aa6e07405595e9f3f5fa10d7f76f767a7d266f6c10314521fc0e94f9a.jpg)  
图4码本优化流程

# 3 波形码本生成算法

首先在仿真环境中使用本文算法生成波形码本，其中CVSD和声码器分别按照蓝牙技术联盟和欧洲电信标准化协会所制定的标准实现，然后对波形码本的各指标分析，最后通过手机通话检验码本在蓝牙中应用效果。

# 3.1实验设置

移动通信网使用FR、EFR、HR和AMR等多种声码器，前三种用于2G的GSM通信，第四种用于3G/4G通信。采用本文算法选取CVSD分别和EFR、FR、AMR12.2、AMR10.2和AMR7.95五种声码器组合对码本优化，并得到不同规模码本。在波形码本生成算法中， $\Delta f = 5 0 H z$ ， $N _ { \mathrm { m a x } } = 5 0 0 0$ ，$N _ { \mathrm { m a x } 2 } = 2 0 0 0$ ， $N _ { t o t }$ 和 $N _ { t o t a l }$ 均为 $1 0 ^ { 5 }$ ， $\varepsilon = 1 0 ^ { - 5 }$ ， $c _ { 1 }$ 和 $c _ { 2 }$ 分别为0.3和0.5，码本范围 $C _ { i }$ 范围为[-1,1]，粒子最大速度 $\nu _ { i }$ 取值为[-0.1,0.1]，权值 $\omega$ 取0.1。

在实际验证阶段，使用两部小米手机6和两个CSR8670蓝牙开发平台对码本传输性能进行测试，测试环境如图5所示。

![](images/caa28f6048d51abcd36f3f83ee561cfbfaa1858d63a35683ff4240f5dc38ec7e.jpg)  
Fig.4Codebook optimization flow chart   
图5实测示意图  
Fig.5Schematic diagram in practical testing

# 3.2结果分析

码本指标部分结果如表3所示。其中计算量指对接收波形解调时求解余弦值的运算量，约为 $8 0 0 0 ~ N$ 次/s加法和乘法；存储量指 $C A _ { N \times L }$ 和 $C B _ { N \times L }$ 占用空间，为2LN。

由表3可以看出，相同码本在不同组合中的SER不一样，其中码本在CVSD+EFR和CVSD $^ { + } .$ AMR12.2两种组合中传输效果较好，而在 $\mathrm { C V S D + F R }$ 组合中的传输效果较差。

图6表示在码本中波形符号数量N相同情况下，SER与  
波形符号长度L的关系。波形符号长度L越长，SER越低，  
即 $S E R \propto \frac { 1 } { L }$ 。

Table 3Algorithm performance   

<html><body><table><tr><td colspan="2">码本规模</td><td>32x40</td><td>64x40</td><td>32x30</td><td>64x36</td><td>32x20</td><td>64x24</td><td>64x20</td></tr><tr><td colspan="2">R(kb/s)</td><td>1</td><td>1.2</td><td>1.33</td><td>1.33</td><td>2</td><td>2</td><td>2.4</td></tr><tr><td rowspan="5">SER (%)</td><td>EFR</td><td>0.004</td><td>0.013</td><td>0.008</td><td>0.007</td><td>0.056</td><td>0.048</td><td>0.264</td></tr><tr><td>FR</td><td>0.351</td><td>0.897</td><td>1.798</td><td>1.542</td><td>4.325</td><td>4.214</td><td>12.507</td></tr><tr><td>AMR12.2</td><td>0.002</td><td>0.013</td><td>0.007</td><td>0.006</td><td>0.049</td><td>0.041</td><td>0.278</td></tr><tr><td>AMR10.2</td><td>0.051</td><td>0.092</td><td>0.054</td><td>0.045</td><td>1.218</td><td>1.104</td><td>3.479</td></tr><tr><td>AMR7.95</td><td>0.956</td><td>3.478</td><td>5.914</td><td>4.813</td><td>7.547</td><td>6.957</td><td>15.995</td></tr><tr><td>(10次/秒)</td><td>计算量</td><td>256</td><td>512</td><td>256</td><td>512</td><td>256</td><td>512</td><td>512</td></tr><tr><td>存储量 （双字）</td><td></td><td>2560</td><td>5120</td><td>960</td><td>2304</td><td>640</td><td>1536</td><td>1280</td></tr></table></body></html>

![](images/880937c92263f954f244fc9cdb62d503450ec4701486f3a5ccb063b650cdd3b6.jpg)  
图6L不同时的SER

图7表示在码本中波形符号长度L相同情况下，SER与波形符号数量N的关系。符号数量N越小，SER越低，即$S E R \propto N$ 。

![](images/877cc0fc478a8ce25426caa313e92f6a8a9b6b237a5406841c9fec8cca2d04dd.jpg)  
Fig.6SER with different L   
图7N不同时的SER  
Fig.7SER with different $N$

图8表示在 $R$ 相同的情况下，不同 $N$ 和 $L$ 组合的 $S E R$ 。由图8可知，波形符号的采样点数 $L$ 越多，SER也越低。但是随着 $L$ 增大， $N$ 呈指数级增大，计算量和存储量也随之迅速上升；同时，寻找 $N$ 个既具有差异性又能通过语音信道的波形符号的难度会越大，SER降低比例会越来越小。因此，在考虑既定比特传输速率的码本时，需对SER、存储量和计算量折中考虑。

图9表示对规模为 $3 2 \times 2 0$ 的码本优化时，CVSD $^ +$ EFR组合的 $S E R$ 与迭代次数关系。其中，对初始粒子迭代5000次，对精英粒子迭代2000次，每次迭代对两个粒子搜寻，总搜寻次数为24000次。

![](images/37057dfd433851a2cf384f5e1ded31a983b936c2ea664ac76a7373ae5bf032ca.jpg)  
图8相同R时的SER

![](images/2894e1e1d5ecbd533af266f9a36752eac7405b952045ce9ac39f4df451e6aadd.jpg)  
Fig.8 SER in same R   
图9迭代时的 SERFig.9SERin Iteration

表4为文献[16]与本文算法对比。其中文献[16]使用模式搜索算法优化，其实际搜寻次数为迭代次数8000次与每次迭代寻找方向1024之积，即8192000 次。文献[16]整体上SER低于本文算法，但是并没有考虑CVSD，而且运算量大，整体上本文算法性能较优。

表3算法性能  
表4性能对比  

<html><body><table><tr><td></td><td>SER</td><td>CVSD编解码</td><td>总搜寻次数</td></tr><tr><td>文献[16]</td><td>0.0004%</td><td>未考虑</td><td>8192000</td></tr><tr><td>本文</td><td>0.056%</td><td>考虑</td><td>24000</td></tr></table></body></html>

表5表示利用本文算法生成的码本在CVSD和不同声码器组合中所能承载的最大比特传输速率，其中SER 在 $5 \%$ 内时认为可以通过纠错码纠正。

Table 4Performance comparison   
表5不同声码器最大的比特传输速率  
Table 5Maximum bit rate of different vocoders   

<html><body><table><tr><td>声码器</td><td>EFR FR</td><td>AMR12.2</td><td>AMR10.2</td><td>AMR7.95</td></tr><tr><td>Rmax (kb/s)</td><td>3 2</td><td>3</td><td>2.4</td><td>1.33</td></tr></table></body></html>

手机可以设置语音通话的网络，但不能指定声码器，因此在实测时，先将波形码本烧入到CSR8670，然后分别指定2G、3G/4G网络进行语音通话，每次通话循环发送1000个波形符号，在接收方提取接收数据在MATLAB中实现同步后再解调，计算其SER，做10次实验取其平均值，SER结果如表6所示。

由表6可知，实测实验结果比仿真测试要差，原因有：a)语音传输会受到更多因素的影响，如电磁干扰，信号衰减等；b)移动通信网的语音通信会在不同声码器之间切换，如2G可能使用EFR、FR和HR等声码器，而3G/4G网使用的AMR声码器会根据信道采用不同编码速率，但是符号错误率仍在可接受范围内，通过纠错码传输可以较好地解决。

表6测试结果Table 6Test results  

<html><body><table><tr><td rowspan="2">网络类型</td><td colspan="5">码本规模</td></tr><tr><td>32x40</td><td>64x40</td><td>64x36</td><td>64x24</td><td>64x20</td></tr><tr><td>2G</td><td>0.02%</td><td>0.32%</td><td>0.54%</td><td>1.58%</td><td>1.78%</td></tr><tr><td>3/4G</td><td>0.12%</td><td>0.33%</td><td>0.22%</td><td>1.83%</td><td>1.34%</td></tr></table></body></html>

# 4 结束语

本文在深入分析CVSD编码和声码器特点的基础上，提出了一种面向蓝牙语音加密传输的波形码本生成算法。该算法使用固定频率在语音频段的子载波调制生成初始调制码本，在语音信道训练数据得到解调码本，设计了粒子编码、优化目标函数和粒子更新机制，使用末位淘汰机制的粒子对算法寻优。仿真分析表明，算法收敛速度快，可以生成不同比特传输速率和符号错误率低的波形码本。在此基础上，设计了实验用于检验波形码本在蓝牙设备中传输数据效果，结果表明符号错误率较低。下一步需要继续实现蓝牙语音加密数据自同步，进而实现蓝牙语音加密数据在语音信道透传。

# 参考文献：

[1]韩心梓.移动通信端到端语音加密传输技术研究[D].南京：东南大 学,2016.(Han Xinzi.Research on end-to-end voice encryption and transmissiontechnologyformobilecommunication[D]. Nanajing:Southeast University,2016.)   
[2]Bluetooth SIG,Bluetooth SIG specification of the Bluetooth system: core package version 5.00 [EB/OL].(2016)[2018-09-01].http:www. bluetooth. org.   
[3]European Telecommunications Standards Institute.Digital cellular telecommunications system (Phase 2) (2oo) enhanced full rate (EFR) speech transcoding (GSM 06.60 version 4.1.1） [EB/OL]. (2000) [2018-09-01].htp://www. etsi.org.   
[4]Kaiugampala N,Villette S,Kondoz A M. Secure voice over GSM and other low bit rate systems [C]//Proc of IEEE Seminar on Secure Gsm& Beyond:End to End Security for Mobile Communications.London: IEEE Press,2003:3/1-3/4.   
[5]杨典兵．端到端保密通信中的类语音调制解调研究[D].郑州：信息 工程大学,20o9.(Yang Dianbing.Research on speech-like modulation anddemodulation inend-to-endsecurecommunication[D]. Zhengzhou:Information Engineering University, 2009.)   
[6]Rashidi M, Sayadiyan A,Mowlaee P.Data mapping onto speech-like signal to transmission over the gsm voice channel [C]//Proc of the 40th Southeasten Symposium on System Theory.New Orleans:IEEE Press, 2008:54-58.   
[7]Sapozhnykov D A, Sharma A,Paik M,et al. Hermes: data transmission over unknown voice channels [Cl//Proc of International Conference on Mobile Computing and Networking.Chicago: DBLP, 2010:113-124.   
[8]Chen L,Guo Q.An OFDM-based secure data communicating scheme in GSM voice channel [C]// Proc of International Conferenceon Electronics,Communications and Control. Ningbo: IEEE Press,2011: 723-726.   
[9]唐旭．数字信号在语音信道中的传输算法研究[D]．西安：西安电子 科技大学,2014.(Tang Xu.Research on algorithm of digital signal transmission in speech channel [D]. Xian:Xidian University,2014.)   
[10]杨于村．基于公众移动通信网的端到端加密语音传输技术研究[D]. 广州：华南理工大学,20o9.(Yang Yucun.Research on transmission technology for end-to-end encrypted voice over public mobile networks [D]. Guangzhou:South China University of Technology,2009.)   
[11] Ladue C K, Sapozhnykov VV,Fienberg K S.A data modem for GSM Voice channel [J]. IEEE Trans on Vehicular Technology, 20o8,57 (4): 2205-2218.   
[12]梁丹，张连海，杨绪魁．一种新型的类语音调制方法[J]．电子设计 工程,2017,25(4):5-10.(Lian Dan,Zhang Lianhai,Yang Xukui.A new method of speech-like modulation [J].Electronic Design Engineering,2017,25(4): 5-10.)   
[13]Boloursaz M,Hadavi AH,KazemiR,et al.A data modem for GSM adaptive multi rate voice channel[C]//Proc of East-West Design & Test Symposium.Rostov-on-Don: IEEE Press,2013:1-4.   
[14]梁丹，陈琦，张连海．一种基于遗传算法的类语音调制方法[J].信 息工程大学学报,2017,18 (2):148-153.(Lian Dan,Cheng Qi, Zhang Lianhai. Speech-like modulation method based on genetic algorithm [J]. Journal of Information Engineering University,2017,18 (2):148-153.)   
[15] Kazemi R,Boloursaz MM, Heidari K M,et al. Modem based on sphere packing techniques in high-dimensional Euclidian sub-space for efficient data over voice communication through mobile voice channels [J].Communications Iet,2015,9 (4): 508-516.   
[16] Sapozhnykov V V.A Low-rate data transfer technique for compressed voice channels [J].Journal of Signal Processing Systems,2012,68 (2): 151-170.   
[17]纪震．粒子群算法及应用[M].北京：科学出版社，2009.(Ji Zhen. Particleswarmoptimizationalgorithmandapplication[M]. Beijing:Science Press,2009.）