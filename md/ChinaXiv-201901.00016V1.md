# 在小波域中实现的奇异谱分析音频隐藏算法

陆诗依，高勇(四川大学 电子信息学院，成都 610065)

摘要：针对许多语音隐藏算法隐藏容量不大，透明性不高等问题提出了一种新的语音隐藏算法。首先将隐蔽信息经过G。729A进行压缩编码，其次将提升小波变换和奇异谱分析应用于音频信息隐藏。实验表明，通过该算法嵌入隐蔽信息后的音频文件不仅在隐蔽信息容量上有显著的提高，而且具有很好的透明性，也能抵抗一定的攻击，算法在隐蔽容量、透明性和鲁棒性方面达到了较高的平衡。

关键词：小波变换；奇异谱分析；隐藏容量；压缩编码 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.09.0660

Singular spectrum analysis audio hidden algorithm implemented in wavelet domain

Lu Shiyi, Gao Yong (College of Electronics& Information Engineering,Sichuan University,Chengdu 61oo65,China)

Abstract:Anew spech concealment algorithm is proposed for many speech concealment algorithms with smallhidden capacityand badtransparency.First,theconcealed information is compresed and encoded byG.729A,and thenthe lifting wavelet transform and singular spectrum analysisareapplied tothe audio information hiding.Experimentsshow thatthe audio file embedded inthe hidden information bythealgorithm notonlyhasa significant improvement in the hidden informationcapacitybutalsohas good transparency,andcanalsoresistcertainatacks.Thealgorithminconcealedcapacity transparency and robustness reaches a higher balance.

Key words: wavelet transform; singular spectrum analysis; hidden capacity; compression coding

# 0 引言

语音隐藏技术是信息安全通信中一个重要的研究内容，它将要保密的语音藏入另一段公开的载体语音中，第三方很难判断一段语音是否含有秘密语音，更加难以提取出其中的秘密语音。

隐蔽信息嵌入到数字音频信号中的算法主要时域嵌入和变换域嵌入分为两种。时域是将隐蔽信息嵌入到音频采样信号中；而变换域嵌入是先将采样的音频信号在变换域处理，然后将隐蔽信息嵌入到处理后的音频信号中。

在变换域算法中，文献[1]给出了DFT的信息隐藏算法，主要用于版权保护。文献[2]提出了一种结合SVD和DWT的隐藏算法，主要是在小波包系数中修改特征矩阵的值。文献[3]给出了混沌与LSB相互结合的音频隐藏算法。文献[4]提出了离散傅里叶变换与离散小波变换相结合的隐藏算法。文献[5\~9]提出了LWT-SVD 算法。这些算法的共同点都是把秘密信息转换为二进制比特，通过改变奇异矩阵的某些值进行嵌入。文献[10]提出了DCT-DWT-SVD算法，通过量化的方法藏入秘密语音。但是这些算法都存在隐藏容量不够大、透明性不高等问题。

本文算法通过使用G.729A压缩编码，将秘密语音提前压缩编码处理，可以提高隐藏容量。同时载体语音经过提升小波变换，得到两个系数，即近似系数和细节系数。本文在近似系数和细节系数中均进行奇异谱分析，通过修改得到的奇异值来进行信息隐藏。

通过实验测试，本文算法显著地提升了语音的隐藏容量和抗干扰能力，与使用传统SVD的方法相比，透明性更高。

# 1 音频隐写算法

# 1.1秘密语音的压缩处理

首先对秘密语音进行G.729A的压缩处理。G.729A是ITU-T制定的使用共轭结构代数码激励线性预测的语音编码标准，以8kbps的波特率对语音进行编码[1I]。本文使用采样频率为 $8 \mathrm { { k H z } }$ ，采样精度为16bit的秘密语音，经过G.729A编码之后，秘密信息相当于压缩了16倍，压缩之后语音信号可以转换为比特流。

# 1.2提升小波变换

在文献[12]中，Sweldens 提出了一种不依赖于傅里叶变换的新的小波构造的方法，即提升小波变换法。提升小波变换可以实现系数的整数化，使其在运算中减小了计算冗余度。所谓的提升小波变换就是Harr小波变换。Harr小波具有如下特性：a)任一函数都可以由它们的位移函数组成；b)任意函数都可以由常函数以及它们的位移函数所组成；c)具有正交性等。

# 1.3奇异谱分析

奇异谱分析是近年来兴起的一种研究非线性时间序列数据的方法。它根据所观测到的时间序列构造出轨迹矩阵，并对轨迹矩阵进行分解、重构，从而提取出代表原时间序列不同成分的信号。奇异谱分析大致可以分为以下的几个部分：

a)形成轨迹矩阵。

假设一个语音信号为Y，Y是一个 $\mathbf { M } { \times } \mathbf { N }$ 的矩阵， $Z _ { _ i }$ 为

$Y$ 的第 $i$ 行信号， $Z _ { \scriptscriptstyle i } = ( Z _ { \scriptscriptstyle 1 } , Z _ { \scriptscriptstyle 2 } , . . . , Z _ { \scriptscriptstyle r } , . . . , Z _ { \scriptscriptstyle N } )$ ， $Z _ { _ r }$ 为该帧的第 $r$ 个采样点。

设窗长为 $L$ ， $L ( 1 < L < N )$ 是基本奇异谱分析的唯一参数，可以得到第 $i$ 行的轨迹矩阵 $X _ { i }$ 。 $X _ { i }$ 可以表示为

$$
X _ { i } = { \left[ \begin{array} { l l l l } { Z _ { 1 } } & { Z _ { 2 } } & { \cdots } & { Z _ { K } } \\ { Z _ { 2 } } & { Z _ { 3 } } & { \cdots } & { Z _ { K + 1 } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { Z _ { L } } & { Z _ { L + 1 } } & { \cdots } & { Z _ { N } } \end{array} \right] }
$$

$X _ { i }$ 为一个 $\mathbf { L } { \times } \mathbf { K }$ 的矩阵； $K = N - L + 1$ ； $X _ { i }$ 每一条副对角线上的元素都相等,最终可以得到 $M$ 个轨迹矩阵。

b)SVD。

对上述得到的每一个轨迹矩阵作奇异值分解，分解公式如下：

其中： $\pmb { U }$ 和 $\boldsymbol { V }$ 是正交矩阵； $P$ 是半正定 $\mathbf { L } { \times } \mathbf { K }$ 阶对角矩阵，它的对角线元素称为 $X _ { i }$ 的奇异值。 $\{ \sqrt { \lambda _ { j } } , j = 1 , 2 , . . . , d \}$ 是降序排列的 $X _ { i }$ 的奇异值，其中： $d$ 代表了奇异值的个数，它们构成了 $X _ { i }$ 的奇异谱； $\lambda _ { j }$ 是 $X _ { i } X _ { i } ^ { T }$ 的特征值，则矩阵 $X _ { i }$ 还可以写成如下的形式：

$$
X _ { i } = \sum _ { j = I } ^ { d } R _ { j }
$$

其中： $\pmb { R } _ { j } = \sqrt { \lambda _ { j } } \pmb { U } _ { j } \pmb { V } _ { j } ^ { T }$ ， $U _ { j }$ 和 $V _ { j }$ 是 $X _ { i }$ 的左右奇异向量， $j$ 代表振动分量（SVD分解后所得的奇异值）的序号， $\pmb { R } _ { j }$ 代表 $X _ { i }$ 的第 $j$ 个振动分量，奇异值 $\sqrt { \lambda _ { j } }$ 可以看做是振动分量的一个比例因子。

c)信号的还原。

假设得到的 $\operatorname { L } { \times } \operatorname { K }$ 轨迹矩阵还原为 $Y _ { i }$ ，即原来的一维矩阵，需要进行对角归一化。设重构得到的行序列 ${ \pmb R } _ { i }$ ， $r _ { p }$ 为其任意元素方式如下：

$$
r _ { p } = { \left( \sum _ { j = I } ^ { k } Y _ { i , j } \right) } \mathord { \left/ { \vphantom { \left( \sum _ { j = I } ^ { k } \sum _ { j = I } ^ { j } { B _ { p } } \right. \kern - delimiterspace } \beta _ { p } } \right. }
$$

$$
i = p \textmd { - } j + I
$$

$$
\beta _ { p } = \left\{ \begin{array} { l l } { p } & { p < k } \\ { A - p + I } & { p > A - k + I } \\ { k } & { o t h e r w i s e } \end{array} \right.
$$

在式（6）中： $A$ 代表轨迹矩阵中元素的个数； $k$ 代表轨迹矩阵的列数。

# 1.4秘密语音的嵌入

本文算法是将秘密信息经过压缩编码预处理，得到秘密信息比特流，同时将载体语音进行小波分解，在分解所得的近似系数和细节系数中进行奇异谱分析，通过修改振动分量进行秘密语音比特流的交替隐藏。具体隐藏方式如下：

a)将载体语音 $c$ 先进行一维小波变换，得到两个系数。b)秘密语音 $s$ 进行G.729A的压缩处理，压缩之后语音信号可以转换为比特流。c)对小波变换得到的细节系数 $C H$ 和近似系数 $\mathit { C L }$ 进行奇异谱分析，并将秘密语音嵌入其中。

奇异谱分析如下：

$C H$ 是一个 $1 { \times } \mathbf { M }$ 的矩阵， $\mathit { C L }$ 是一个 $1 \times \mathrm { N }$ 的矩阵，将$C H$ 重新构造为一个 $\mathbf { n } { \times } \mathbf { M } 1$ 的矩阵， $\mathit { C L }$ 重新构造为一个$\mathrm { \ m } { \times } \mathrm { N } 1$ 的矩阵，对 $C H$ 矩阵的第 $i$ 行进行奇异谱分析时，所选择的窗长为 $L$ ，形成 $C H$ 的轨迹矩阵 $X _ { _ { C H i } }$ 如式（7）所示。

$$
X _ { C H i } = \left[ \begin{array} { c c c c } { { C H _ { 1 } } } & { { C H _ { 2 } } } & { { \cdots } } & { { C H _ { K } } } \\ { { C H _ { 2 } } } & { { C H _ { 3 } } } & { { \cdots } } & { { C H _ { K + 1 } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { C H _ { L } } } & { { C H _ { L + 1 } } } & { { \cdots } } & { { C H _ { M 1 } } } \end{array} \right]
$$

其中： $X _ { _ { C H i } }$ 为一个 $\mathbf { L } { \times } \mathbf { K }$ 的矩阵； $K = M 1 - L + 1$ ，最终可以得到 $n$ 个轨迹矩阵。

同理可以得到 $\mathit { C L }$ 的轨迹矩阵，如式（8）所示。

$$
\begin{array} { r } { X _ { c L j } = \left[ \begin{array} { c c c c } { C L _ { 1 } } & { C L _ { 2 } } & { \cdots } & { C L _ { K } } \\ { C L _ { 2 } } & { C L _ { 3 } } & { \cdots } & { C L _ { K + 1 } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { C L _ { L } } & { C L _ { L + 1 } } & { \cdots } & { C L _ { N 1 } } \end{array} \right] } \end{array}
$$

其中： $X _ { \mathit { c L j } }$ 为一个 $\mathbf { L } { \times } \mathbf { K }$ 的矩阵； $K = N 1 - L + 1$ ，最终可以得到 $m$ 个轨迹矩阵。

将上述得到的每一个轨迹矩阵做奇异值分解，按式（2)进行分解，得到 $C H$ 和 $\mathit { C L }$ 每一行的奇异值分别为$\{ \sqrt { \lambda _ { H i } } : i = 1 , 2 , . . . , M 1 \}$ 和 $\{ \sqrt { \lambda _ { L i } } : i = 1 , 2 , . . . , N 1 \}$ 。

轻微的修改奇异值并不会影响语音信号的质量，本文通过修改轨迹矩阵特定的奇异值，即修改特定振动分量的比例因子来实现秘密信息的嵌入，最终在 $C H$ 和 $\mathit { C L }$ 中一行各隐藏一个比特的信息，交替隐藏，即在 $C H$ 中藏一比特信息之后又在 $\mathit { C L }$ 中藏一比特，依次循环。修改序号从 $p$ 到 $t$ 的振动分量， $2 \leq p { \prec } t \leq m i n { \big ( } M 1 , N 1 { \big ) }$ ， $d$ 为量化因子，秘密信息的嵌入规则如下：

$$
\begin{array} { r } { \sqrt { \lambda _ { H m } } = \left\{ \begin{array} { l } { \sqrt { \lambda _ { H m } } + d \left[ \frac { ( \sqrt { \lambda _ { H m } } - \sqrt { \lambda _ { H m } } ) } { d } \right] } \\ { f o r \quad p < m < t \quad i f \ b i t = " 0 } \\ { \sqrt { \lambda _ { H m } } + d \left[ \frac { ( \sqrt { \lambda _ { H m } } - \sqrt { \lambda _ { H t } } ) } { d } \right] } \\ { f o r \quad p < m < t \quad i f \ b i t = " 1 " } \end{array} \right. } \end{array}
$$

在式（9）中，当 $\scriptstyle t - p + 1$ 是奇数时, $\sqrt { \lambda _ { H m } }$ 代表的是$\{ \sqrt { \lambda _ { H i } } : i = p , p + 1 , . . . , t \}$ 的中位数, $\lfloor \ \rfloor$ 表示向下取整；当

$t - p + 1$ 是偶数时， $\sqrt { \lambda _ { H m } }$ 代表的是 $\{ \sqrt { \lambda _ { H i } } , i = p , p + 1 , . . . , t \}$ 的中间序号数，即 $\sqrt { \lambda _ { H m } } = \sqrt { \lambda _ { \ H \frac { 2 ^ { * } p + t - p + 1 } { 2 } } }$

同理可以得到秘密语音在 $\mathit { C L }$ 中的嵌入方式：

$$
\begin{array} { r } { \sqrt { \lambda _ { L m } } = ( \overbrace { \sqrt { \lambda _ { L m } } } ^ { ( \sqrt { \lambda _ { L m } }  + \alpha \bigg | } \frac { ( \sqrt { \lambda _ { L p } } - \sqrt { \lambda _ { L m } } ) } { d } ] ^ { ( \sqrt { \lambda _ { L p } } - \sqrt { \lambda _ { L m } } ) } } \\ { \sqrt { \lambda _ { L m } } = \{ f o r \quad p < m < t \quad \mathrm { ~ i f ~ } \ b i t = " 0 ^ { n } } \\ { \sqrt { \lambda _ { L m } } + d \{ \frac { ( \sqrt { \lambda _ { L m } } - \sqrt { \lambda _ { L t } } ) } { d } \} } \\ { f o r \quad p < m < t \quad \mathrm { ~ i f ~ } \ b i t = " 1 ^ { n } } \end{array}
$$

在式（10）中，当 $t - p + 1$ 是奇数时， $\sqrt { \lambda _ { L m } }$ 代表的是$\{ \sqrt { \lambda _ { L i } } : i = p , p + 1 , . . . , t \}$ 的中位数， $\lfloor \ \rfloor$ 表示向下取整；当$t - p + 1$ 是偶数时， $\sqrt { \lambda _ { L m } }$ 代表的是 $\{ \sqrt { \lambda _ { L i } } : i = p , p + 1 , . . . , t \}$ 的中间序号数，即√m= $\sqrt { { \lambda } _ { L m } } = \sqrt { \lambda _ { \ L \frac { 2 ^ { * } p + t - p + 1 } { 2 } } }$

修改奇异值之后得到的轨迹矩阵分别为 $X _ { { { \scriptscriptstyle C H } } }$ 和 $X _ { c L }$ ，在后续的描述中统称为 $Y _ { i }$ □

d)假设得到的 $\mathbf { L } { \times } \mathbf { K }$ 轨迹矩阵为 $\pmb { Y } _ { i }$ ，需要还原为原来的行矩阵，需要进行对角归一化。设重构得到的行序列 $R _ { i } ~ , ~ r _ { p }$ 为其任意元素，重构序列可通过下式获得：

$$
\begin{array} { r } { r _ { p } = \left( \sum _ { j = 1 } ^ { k } Y _ { i , j } \right) / \beta _ { p } } \end{array}
$$

$$
i = p - j + 1
$$

$$
\beta _ { p } = \left\{ \begin{array} { l l } { p } & { p < k } \\ { A - p + 1 } & { p > A - k + 1 } \\ { k } & { o t h e r w i s e } \end{array} \right.
$$

在式（13）中： $A$ 代表 $M 1$ 或者 $_ { N 1 }$ ，即轨迹矩阵中元素的个数； $k$ 代表轨迹矩阵的列数。把上述得到的序列进行矩阵的重构，可恢复为原来的 $c \pmb { H }$ 和 $_ { c L }$ ，将 $c \pmb { H }$ 和 $_ { c L }$ 经过反小波变换即可得到含密语音。

# 1.5秘密语音的提取

对含密语音进行小波变换，得到近似系数 $c \pmb { H }$ 和细节系数 $_ { c L }$ ，按照之前的方式重塑矩阵，分别每一行可形成一个轨迹矩阵，利用SVD变换提取出每一个轨迹矩阵的奇异谱后进行秘密信息的提取。提取规则如下：

$$
b i t = \left\{ \begin{array} { l l } { \ " 1 " } & { \qquad i f \sqrt { \lambda _ { p } } - \sqrt { \lambda _ { \eta } } > \sqrt { \lambda _ { \eta } } - \sqrt { \lambda _ { t } } } \\ { \ " 0 " } & { \qquad i f \sqrt { \lambda _ { p } } - \sqrt { \lambda _ { \eta } } \leq \sqrt { \lambda _ { \eta } } - \sqrt { \lambda _ { t } } } \end{array} \right.
$$

其中： $\sqrt { \lambda _ { \eta } }$ 是 $\left\{ \sqrt { \lambda _ { p } } , \sqrt { \lambda _ { p + 1 } } , . . . , \sqrt { \lambda _ { t } } \right\}$ （奇异值）的中间值。按照之前嵌入的方式，首先得到 $c \pmb { H }$ 第一行的奇异值，从中提取出一个比特的信息；其次按照同样的方式从 $_ { c L }$ 中提出一个比特的消息，依次循环，最后得到秘密的比特流。再将这个比特流经过G.729A解码，就可以恢复出秘密语音。

# 1.6算法参数的选择

奇异谱分析唯一需要确定的参数就是窗长 $L$ ， $L$ 的大小关系着算法的运算速度、奇异值的数目。实验表明窗长不应该超过 $N / 2$ ，本文所选取的为round（N/2），round代表向下取整数。其次应该考虑的是振动分量的修改，应该选取第几个振动分量（奇异值），即 $p$ 和 $t$ 的选择，选择在低序的振动分量中嵌入秘密信息，会增加算法的鲁棒性，但是算法透明性会变差，选择在高序分量中嵌入秘密信息会得到更好的透明性，本文采用自适应的方式来确定所选的振动分量，即 $p = r o u n d \left( a / 4 \right) \qquad , \qquad t = r o u n d \left( 3 ^ { \ast } a / 4 \right)$ $a \in \operatorname* { m i n } ( M 1 , N 1 )$ 。量化因子d的选择取决于区间的大小。

# 2 算法的实验仿真

实验均采用 $8 ~ \mathrm { K H z }$ 采样，16bit量化的语音，取一段 21 s载体语音 $c$ ，取 $1 . 5 4 \mathrm { s }$ 秘密语音 $s$ ， $c$ 的长度大于 $s$ ，分解出来的细节系数 $_ { c L }$ 的长度要大于 $s$ 的长度。

在客观上，用信噪比（SNR）来衡量嵌入秘密语音后载体的失真，定义为

$$
\begin{array} { r } { S N R = 1 0 \mathrm { l o g } \frac { \displaystyle \sum _ { m = 1 } ^ { l e n g t h ( h ) } C ^ { 2 } ( m ) } { \displaystyle \sum _ { m = 1 } ^ { l e n g t h ( h ) } \left( C ^ { \prime } ( m ) - C ( m ) \right) ^ { 2 } } } \end{array}
$$

其中: $C ( m )$ 表示原始载体语音； $C ^ { \prime } ( m )$ 表示含有秘密语音的载体语音； $h$ 代表的是秘密语音的长度。

用归一化相关系（ $N C$ ）来衡量恢复出的秘密语音的失真，定义为

$$
N C = \frac { \displaystyle \sum _ { m = 1 } ^ { l e n g t h ( s ) } s ( m ) s ^ { ' } ( m ) } { \displaystyle \sum _ { m = 1 } ^ { l e n g t h ( s ) } \sqrt { s ^ { 2 } ( m ) } \sum _ { m = 1 } ^ { l e n g t h ( s ) } \sqrt { s ^ { 2 } ( m ) } }
$$

其中： $s ( m )$ 表示原始的秘密语音； $s ^ { \prime } ( m )$ 表示恢复出的秘密语音。SNR与 $N C$ 的值越大，说明算法的透明性越好。由该算法计算出的载体信息的SNR为 $3 6 . 7 8 \mathrm { d B }$ ，密语音的 $N C$ 值为0.9989。这些数据从客观上说明该算法的透明性好，而且恢复出的秘密语音几乎与原始的秘密语音失真很小，语音的舒适度较好。

算法效果如图1\~4所示。

![](images/4cc4571fcc45a0cb3ace5f641635296480949a5f7d14283f6d02a67b8e461560.jpg)  
图1原始载体语音  
Figure1Original carriervoice

取MIMIT语音库中300条纯净语音做对比实验：计算各种攻击之后算法的误码率；对不同算法的含密语音结果测量其 SNR值，进行透明性打分（采用MOS[13]评价标准进行音质主观性打分）；测量隐藏容量。

![](images/99d9f49a7e3faa6ddd8e7c4d310b5901eef0792c9d51a8260b4ee6980a536b81.jpg)  
图3含密语音

![](images/b8451e5a29863ef0babde131df7915e1c65e97f4df67eb1fa6e48deb751aebe8.jpg)  
Figure 3Encrypted speech   
图2嵌入之前的秘密语音

![](images/99311a8e1e5d3da263116be66d4cf3a55ac86188a41b5c8bcf5bbdffa8b45464.jpg)  
Figure 2Secret voice before embedding   
图4算法性能分析  
Figure 4Performance analysis of algorithms

Table 1Robustness analysis (bit error rate $\%$ ）  
表2不同载体音乐的 SNR 值  
表3不同算法的透明程度MOS打分  

<html><body><table><tr><td>攻击方式</td><td>MP3</td><td>带通滤波</td><td>MP4</td><td>重量化</td><td>重采样</td></tr><tr><td>SVDDWT [2]</td><td>47.36</td><td>34.21</td><td>33.10</td><td>0.14</td><td>0.02</td></tr><tr><td>DWT-DCT[5]</td><td>48.56</td><td>40.56</td><td>36.15</td><td>0.15</td><td>0.05</td></tr><tr><td>DWT[7]</td><td>34.02</td><td>23.57</td><td>12.34</td><td>0.10</td><td>0.06</td></tr><tr><td>本文方法</td><td>2.56</td><td>5.10</td><td>3.28</td><td>0.10</td><td>0.01</td></tr></table></body></html>

表1鲁棒性分析（误码率 $\%$ ）  
Table 2 SNR values of different carrier music   

<html><body><table><tr><td>载体音乐类型</td><td>SNR/dB</td></tr><tr><td>流行音乐</td><td>35.77</td></tr><tr><td>乐器纯音乐</td><td>39.02</td></tr><tr><td>播音主持</td><td>36.10</td></tr><tr><td>平均</td><td>36.96</td></tr></table></body></html>

把所选取的300条纯净语音作为载体语音，嵌入秘密信息后，对含密语音进行了各种攻击，攻击实验如下：a）带通滤波。截止频率为 $8 0 0 ~ \mathrm { H z }$ 和 $5 ~ \mathrm { { k H z } }$ ；b）加高斯白噪声，信噪比为20dB；c)重采样，将待测音频先下采样的方法到44.1$\mathrm { k H z }$ ，再上采样到 $9 6 ~ \mathrm { k H z }$ ；d）重量化，将音频从16bit量化到8bit再量化为16bit；e）MP3压缩，将音频信号进行比特率为 $6 4 ~ \mathrm { k b p }$ 的压缩，再解压缩；f）MP4压缩，将音频信号进行比特率为128kbps 的压缩，再解压缩。对被攻击的含密语音进行水印提取，并统计信息误码率的平均值，得到表1 数据。本文算法在抗压缩攻击上鲁棒性明显优于与之对比的三种算法，特别是在抵抗MP3和MP4压缩上，误码率明显低于文献[2],文献[5]和文献[7]所提出的算法，在重采样和重量化的攻击下，误码率优于其他三种算法，由此可以看出本文算法有较好的鲁棒性。

Table 3Degree of transparency of different algorithms is scored by   
表4隐藏容量(bit/s)   

<html><body><table><tr><td colspan="4">MOS</td></tr><tr><td></td><td>流行音乐</td><td>乐器纯音乐</td><td>播音主持</td></tr><tr><td>DWT-DCT[5]</td><td>4.65</td><td>4.67</td><td>4.65</td></tr><tr><td>SVD-DWT[2]</td><td>4.66</td><td>4.70</td><td>4.68</td></tr><tr><td>DWT[7]</td><td>4.66</td><td>4.68</td><td>4.69</td></tr><tr><td>本文方法</td><td>4.70</td><td>4.69</td><td>4.69</td></tr></table></body></html>

Table 4Hidden capacity (bit/s)   

<html><body><table><tr><td>参考文献</td><td>隐藏容量</td></tr><tr><td>DWT[7]</td><td>100</td></tr><tr><td>回声[14]</td><td>9.22</td></tr><tr><td>SVD[15]</td><td>0.89</td></tr><tr><td>本文提出</td><td>9200</td></tr></table></body></html>

表2表示的是用来实验的不同的载体音乐的信噪比。利用表2不同载体的信噪比进行算法对比实验，得出了表3的数据。

在表3中不同算法使用了不同的载体对含秘密语音进行了MOS打分，评分接近5表示语量优质，使用本文算法之后的含密语音，在一定程度的信噪比中仍然具有可听性。

在表4中进行了隐藏容量的对比，本文采用的是一个小波变换系数的一行藏一个比特，相当于 $1 . 7 ~ \mathrm { m s }$ 藏一比特，加上G.729A预处理，将秘密语音压缩了16倍，所以隐藏容量为 $9 2 0 0 \ \mathrm { b i t / s }$ 。从表中对比来说，本文算法提高了隐藏容量。

# 3 结束语

语言隐藏是保密通信中不可缺少的一部分，通过语音隐藏技术可以用公用信道传输秘密语音。本文算法透明性较好，人耳难以察觉出是否隐藏了秘密语音，对带通滤波、加噪声、重采样、重量化等攻击方式具有很强的鲁棒性，攻击者难以察觉和提取秘密语音，从而达到了保障信息安全的目的。

本文所采用的隐藏算法结合了LWT和奇异谱分析，在本文的算法中，将秘密语音信息在细节系数和近似系数中交替嵌入，秘密语音经过了压缩编码，极大程度地提高了隐藏容量，这样一来攻击者很难在不知道算法和解码类型的情况下提取出来秘密语音。本文算法具有较好的鲁棒性和透明性，从而确保了本文算法在保密通信中的安全性。

# 参考文献：

[1]DharPK,Shimamura T.An audio watermarking scheme using discrete fourier transformation and singular value decomposition [C]// Proc of International Conference on Telecommunications and Signal Processing. Piscataway,NJ:IEEEPress,2012:789-794   
[2]Vivekananda,Bhat K,I.Sengupta,and A.Das.An adaptive audio watermarking based on the singular value decomposition in the wavelet domain [M].New York: Academic Press Inc， 2010.   
[3]赵家弘，尹萍．基于改进混沌密码的音频信息隐藏算法研究[J].微 电子学与计算机，2013，30(5):141-144.(Zhao Jiahong，Yin Ping. Research on audio information hiding algorithm based on improved chaotic cryptography [J].Microelectronics & Computer, 2013,30 (5): 141-144)   
[4]Wang,Xiangyang,Zhao Hong.A novel synchronization invariant audio Watermarking scheme based on DWT and DCT [J].IEEE Trans on Image Processing,2006,54(12): 4835-4840.   
[5]蒋晓丹，范航宇，陆哲明．基于Logistic 混沌映射和IWT-SVD 量化 的鲁棒水印算法[J]．传感器与微系统,2018,37(2):131-135.(Jiang Xiaodan,Fan Hangyu,Lu Zheming.Robust watermarking algorithm based on Logistic chaotic map and IWT-SVDquantization [J]. Sensors and Microsystems,2018,37 (2):131-135)   
[6]张亚红，李志梅，覃科．基于混沌和LWT-SVD的盲信息隐藏算法 [J]．西安航空学院学报，2013，31(5):31-34.(Zhang Yahong，Li Zhimei,Ruan Ke.Blind information hiding algorithm based on chaos and LWT-SVD [J]. Journal of Xi'an Aeronautical College,2013,31 (5): 31-34)   
[7]吴秋玲，吴蒙．基于小波变换的语音信息隐藏新方法[J].电子与信 息学报,2016,38 (4):834-840.(Wu Qiuling,Wu Meng.A new method of speech information hiding based on wavelet transform [J]. Journal of Electronics & Information Technology,2016,38 (4):834-840.)   
[8]Sejpal S, Shah N.A novel multiple objective optimized dual Watermarking scheme based on DWT-SVD using firefly algorithm [C]// Proc of International Conference on Computing,Analytics and Security Trends.Piscataway,NJ:IEEE Press,2017: 46-51.   
[9]Islam M,Laskar R H.Geometric distortion correction based robust watermaking scheme in LWT-SVD domain with digital watermark extraction using SVM[J].Multimedia Tools & Aplications,2017,21 (3): 1-26.   
[10] Jiang Zetao, Chen Wei.Color image zero watermarking algorithm based on DWT-DCT-SVD [J].Microelectronics & Computer,2016,33(8): 107-111.   
[11]陈明义，龚玉蓉．基于TMS320VC5509DSP通信系统的G.729算法 实现[J].信息技术,2007,21(2): 95-96.(Chen Mingyi,Gong Yurong. Implementation of G. 729 algorithm based on TMS320VC5509 DSP communication system [J]. Information Technology，2OO7,21 (2): 95-96.)   
[12] Swelddens W.The lifting scheme:a construction of second generation Wavelets [J].SIAM Journal on Mathematic Analysis,1998,29 (2): 511-546.   
[13]张来洪，邱波，刘红玉．一种基于感知特征动态失真度量的语音质 量评估算法[J]．自动化技术与应用，2017，36(4):1-4.(Zhang Laihong,Qiu Bo,Liu Hongyu.A speech quality assessment algorithm based on dynamic distortion measurement of perceptual features [J]. Journal of Automation Technology and Applications,2017,36 (4): 1-4.)   
[14]凌霖．基于回声隐藏法的语音信息隐匿[J].信息安全与通信保密， 2007,12 (5):136-138.(Ling Lin.Speech information hiding based on echo hiding method [J].Information Security & Communication Security,2007,12(5):136-138.)   
[15]Al-Haj A，Twal C,Mohammad A.Hybrid DWT-SVD audio Watermarking [C]// Proc of International Conference on Digital Information Management.Piscataway,NJ:IEEE Press,2O1O:525-529.