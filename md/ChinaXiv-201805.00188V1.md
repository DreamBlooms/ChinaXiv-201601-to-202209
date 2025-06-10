# 基于分离字典构造的快速压缩感知重构算法

张长伦，余沾，王恒友，何强(北京建筑大学 理学院，北京 102616)

摘要：针对当前压缩感知重构算法存在重构质量偏低、重构时间过长等问题，提出了基于矩阵流形分离字典构造的分块压缩感知重构算法。首先，该算法基于矩阵流形模型训练出可分离稀疏表示矩阵，并对其正交化；其次，构造随机测量矩阵，并利用矩阵运算将其与得到的稀疏表示矩阵进行结合，进而构造出一组分离字典；最后，将该字典用于信号压缩感知中，并通过线性运算实现信号的快速重构。实验结果表明，与当前主流的压缩感知重构算法相比，所提算法在重构精度以及重构时间上都具有一定提升，并在对实时性要求高的领域中具有很好的应用价值。

关键词：压缩感知；矩阵流形；分离字典；快速重构 中图分类号：TN911.73 doi: 10.3969/j.issn.1001-3695.2017.06.0652

# Fast compressive sensing reconstruction algorithm based on separable dictionary construction

Zhang Changlun, Yu Zhan, Wang Hengyou†, He Qiang (Schoolof Science,Beijing UniversityofCivil Engineering&Architecture,Beijing l026l6,China)

Abstract: Because of existing compresive sensing reconstruction algorithms had lower reconstruction quality and longer reconstruction time,this paper proposed a block compressive sensing reconstruction algorithm basedon matrix manifold separabledictionaryconstruction.The proposed algorithm first solved matrix manifold model to getseparable sparse representation matrices and made itorthogonalized.Then,itconstructed arandom measurement matrix andcombined it with thesparserepresentation matrices bymatrix operation togetseparabledictionary.Finaly,thealgorithmappliedthis separable dictionaryinsgnalcompresivesensing,andrealized fastreconstructionofthesignalbylinearoperation.Experimentalesults indicate thatthe proposed algorithm has a great advantage inreconstruction acuracyandrunning timecompared with currnt popular compressvesensingreconstruction algorithms,andithas agood application valuein the field with highreal-time requirement.

Key Words:compressive sensing; matrix manifold; separable dictionary; fast reconstruction

# 0 引言

压缩感知(compressive sensing，CS)[l\~3]作为信号处理领域中诞生的一种全新的理论，受到众多研究人员的关注。由于传统信号采样方式必须遵循奈奎斯特(Nyquist)采样定理，该采样方式会导致采样后数据间具有较大冗余度，所以往往需要对数据进行压缩，这种先采样后压缩的方式不仅耗时，且需要较大的存储空间。压缩感知以远低于传统采样频率的方式对信号进行采样，能使数据采样和压缩同时进行，从而避免了由于采样数据量大而引起的传感元、采样时间等资源的过多浪费，这使其在信号处理领域有着十分重要的地位和广泛的应用前景。

压缩感知重构算法的设计作为压缩感知理论中的核心问题，对信号的重构起到十分重要的作用，因此吸引了众多学者的深入研究。一些学者致力于压缩感知的信号重构，提出了匹配追踪(OMP)[4]、梯度追踪(GP)[5]等算法，但是这类算法的重构精度往往偏低，且重构时间过长。Li等人[提出了非局部正则化的压缩感知图像重建算法，该算法引入了局部回归模型和非局部自相似性，建立了CS图像重建模型，提高了图像的重建质量，但是其重构十分费时。Lu等人[提出了一种压缩感知快速重构算法(compressive image sensing fast recovery，CISFR)，该算法利用线性算子构造分离字典，并用于压缩感知中，仅利用简单的线性运算就能实现图像的快速近似重构，极大地减少了重构时间。然而，由于该算法所构造的字典是随机生成的，所以对所处理的图像不具有针对性。

最近，基于样本训练的学习字典具有很好的自适应性，能更充分地对图像进行稀疏表示，因此受到了研究人员的高度关注。基于奇异值分解的稀疏字典训练方法 $\mathrm { { K - S V D ^ { [ 8 ] } } }$ 是一种典型的基于样本训练的字典学习方法。但由于奇异值分解过于复杂，从而导致其字典训练过程不仅耗时且占用内存大，仅具有线性收敛速度，所以其字典训练效率不高。Hawe 等人[提出了一种分离字典训练方法 SeDiL(separable dictionary learning，SeDiL),该方法结合了字典的矩阵流形结构和几何共轭梯度法，不仅能对较大维度的信号进行训练，而且其迭代具有超线性收敛速度，大大提高了字典训练效率。此外，针对信号的重构，其重构质量也会有所提升。

针对上述压缩感知重构算法存在重构质量偏低、重构时间过长等问题，本文提出了基于矩阵流形分离字典构造的分块压缩感知重建算法。该算法首先基于流形方法针对某类图像集训练出可分离稀疏表示字典，由于该字典是冗余的，不能保证正交性，所以截取其非冗余部分的列向量，构成矩阵并使其正交化，从而得到一组稀疏表示矩阵；其次，构造随机测量矩阵，并利用矩阵运算将其与得到的稀疏表示矩阵进行结合，进而构造出一组分离字典；最后，将该分离字典用于图像压缩感知中，仅通过简单的线性运算就能实现图像的快速重构。本文算法不仅具有很好的自适应性，能够很好地重构图像的细节信息，而且能极大地减少重构时间。仿真结果表明，与当前主流的压缩感知重构算法相比，本文算法在重构精度和重构时间上都有一定的提升。

# 入 二维可分离字典学习方法SeDiL

设 $\{ X _ { i } \} _ { i = 1 } ^ { N }$ 表示 $N$ 个训练样本， $\boldsymbol X _ { i } \in \mathrm { ~ \mathfrak ~ { i ~ } ~ } ^ { m \times n }$ ， $i = 1 , 2 \Lambda$ ,N，传统的字典训练优化模型[8]表示如下：

$$
\underset { D , S } { \operatorname* { m i n } } \sum _ { i = 1 } ^ { N } ( \left. X _ { i } - D S _ { i } \right. _ { F } ^ { 2 } + \lambda g ( S _ { i } ) )
$$

其中： $\boldsymbol { D } \in \mathrm {  ~ i ~ } ^ { m \times d }$ ， $\{ S _ { i } \} _ { i = 1 } ^ { N }$ 为训练集 $\{ X _ { i } \} _ { i = 1 } ^ { N }$ 所对应的稀疏系数；（20 $S _ { i } \in \mathfrak { i } \ ^ { \ d \times n } \ , \quad i = 1 , 2 \Lambda \ , N \ ; \lambda$ 为正则化参数； $g ( \gamma )$ 为信号稀疏度的度量函数。通过求解式(1)中的优化模型，可以得到矩阵 $D$ ，以及稀疏系数{S,=。

由于上述传统的字典训练方法效率不高，而SeDiL[9能大大提高训练效率。该方法所建立的优化模型如下：

$\operatorname* { m i n } ( \frac { 1 } { 2 N } \sum _ { i = 1 } ^ { N } \left\| X _ { i } - L S _ { i } R ^ { T } \right\| _ { F } ^ { 2 } + \frac { \lambda } { N } g ( S ) + k r ( L ) + k r ( R ) )$ (2)其中： $L \in \mathrm { ~  ~ { ~ \sigma ~ } ~ } ^ { m \times h } , R \in \mathrm { ~  ~ { ~ \sigma ~ } ~ } ^ { n \times k } , S = ( S _ { 1 } , S _ { 2 } , \Lambda \mathrm { ~  ~ { ~ \cal ~ S ~ } ~ } _ { m } )$ $g ( S ) = \sum _ { j = 1 } ^ { N } \sum _ { q = 1 } ^ { h } \sum _ { l = 1 } ^ { k } \ln ( 1 + \rho \big | s _ { q l j } \big | ^ { 2 } )$ 其中， $s _ { q l j }$ 是 $S _ { j }$ 的第 $( q , l )$ 项， $\rho > 0$ 是权重因子； $r ( L )$ 为非一致性公式[10],且 $r ( L ) = - \sum _ { 1 \leq i \leq j \leq h } \ln ( 1 - ( L _ { i } ^ { T } L _ { j } ) ^ { 2 } )$ ，优化问题中加入该约束项，可以使得字典各列之间的相关性更小； $k \in \mathfrak { j } ^ { \ + }$ 是权重因子。称 $\mathbf { \Omega } _ { L }$ 和 $R$ 为一组分离字典，且其具有下列流形结构：

$$
M ( a , b ) = \{ A \in { \mathfrak { i } } ^ { \ a \times b } | d i a g ( A ^ { T } A ) = I _ { b } \}
$$

其中： $d d i a g ( \gamma )$ 是由矩阵对角线元素组成的对角矩阵； $I _ { b }$ 是大

小为 $\boldsymbol { b } \times \boldsymbol { b }$ 的单位矩阵，则 $L \in { \cal M } ( m , h ) ~ , ~ R \in { \cal M } ( n , k ) ~ \circ$

# 2 基于流形分离字典构造的分块压缩感知快速重构算法设计

本文提出了一种分块压缩感知快速重建算法。该算法首先对图像进行分块处理，并根据图像块大小，使用SeDiL算法训练出可分离稀疏表示字典。由于该字典是冗余的，不能保证正交性，所以选取该字典部分列向量并构成方阵，再对其正交化，从而得到一组稀疏表示矩阵。其次，通过矩阵运算将所得到的稀疏表示矩阵以及随机生成的测量矩阵进行结合，进而构造出一组分离字典。最后，将该字典用于图像压缩感知中，并利用线性运算实现图像块的重构，将图像块进行重新拼接得到最终的重构图像。设 $p$ 为图像块的采样率， $\mathbf { \Psi } _ { x \in \textbf { i } ^ { m \times n } }$ 为原始图像，图像分块、分离字典构造及压缩采样具体过程如下：

a)对图像 $x$ 进行分块处理。即，使用大小为 $\boldsymbol { b } \times \boldsymbol { b }$ 的窗口以步长为 $s$ 遍历整幅图像，从而得到图像块集合 $\{ x _ { i j } \}$ ，其中，$x _ { i j } \in \mathfrak { i } \ ^ { \ b \times b } \ , \quad i = 1 , 2 , \Lambda \ , [ ( m - b ) / s ] + 1 \ , \quad j = 1 , 2 , \Lambda \ , [ ( n - b ) / s ] + 1 \ \circ \ ,$ （20b）构造分离字典。即：先选取与 $x$ 同类的图像库作为训练集，记为 $s$ ，并根据 SeDiL 算法训练出两组可分离稀疏表示字典，分别对其正交化，记为 $L _ { 1 } , R _ { 1 }$ 和 $L _ { 2 } , R _ { 2 }$ ，其中， $L _ { 1 } , L _ { 2 }$ 的大小为 $( [ { \sqrt { b ^ { 2 } \cdot p } } ] ) \times ( [ { \sqrt { b ^ { 2 } \cdot p } } ] )$ ， $R _ { 1 } , R _ { 2 }$ 的大小为 $\boldsymbol { b } \times \boldsymbol { b }$ ；再构造随机测量矩阵 $\phi _ { 0 } \in \mathrm { ~ i ~ } ^ { [ \sqrt { b ^ { 2 } \cdot p } ] \times b }$ ；将 $L _ { 1 } , R _ { 1 }$ 以及 $L _ { 2 } , R _ { 2 }$ 分别作用于测量矩阵（204 $\phi _ { 0 }$ ，得到 $T _ { 1 }$ 和 $T _ { _ 2 }$ 。

$$
\begin{array} { r l } & { T _ { 1 } = L _ { 1 } \cdot ( \boldsymbol { \phi } _ { 0 } ) \cdot \boldsymbol { R } _ { 1 } ^ { T } , } \\ & { T _ { 2 } = R _ { 2 } \cdot ( \boldsymbol { \phi } _ { 0 } ^ { T } ) \cdot \boldsymbol { L } _ { 2 } ^ { T } } \end{array}
$$

为了加快重构速度，将丢弃 $T _ { 1 }$ 和 $T _ { 2 }$ 中的高频系数，即：令矩阵 $T _ { 1 }$ 最后 $( b - [ \sqrt { b ^ { 2 } \cdot p } ] )$ 列为0，记为 $( T _ { 1 } ) ^ { z }$ ，以及令 $T _ { _ 2 }$ 最后(b-[√b²·p])行为0，记为(T)²，然后通过逆变换即可得到本文所构造的一组分离字典Φ,Φ。

$$
\begin{array} { r l } & { \Phi _ { 1 } = L _ { 1 } ^ { - 1 } \cdot ( T _ { 1 } ) ^ { z } \cdot ( R _ { 1 } ^ { ^ T } ) ^ { - 1 } } \\ & { \Phi _ { 2 } = R _ { 2 } ^ { ^ - 1 } \cdot ( T _ { 2 } ) ^ { z } \cdot ( L _ { 2 } ^ { ^ T } ) ^ { - 1 } } \end{array}
$$

c）对图像块集合 $\{ x _ { i j } \}$ 进行压缩采样。即：利用分离字典$\Phi _ { 1 } , \Phi _ { 2 }$ 对图像块 $x _ { i j }$ 进行压缩感知，得到测量值 $y _ { i j }$ 。

$$
y _ { i j } = \Phi _ { 1 } \cdot x _ { i j } \cdot \Phi _ { 2 }
$$

下面将以图像块 $x _ { i j }$ 为例，对图像块的重构公式进行推导：首先将 $L _ { 1 } , L _ { 2 }$ 作用于式(6)，即

$$
\begin{array} { r l } & { L _ { 1 } \cdot y _ { i j } \cdot L _ { 2 } ^ { { \scriptscriptstyle T } } } \\ & { = L _ { 1 } \cdot ( \Phi _ { 1 } \cdot x _ { i j } \cdot \Phi _ { 2 } ) \cdot L _ { 2 } ^ { { \scriptscriptstyle T } } } \\ & { = L _ { 1 } \cdot \Phi _ { 1 } \cdot ( R _ { 1 } ^ { { \scriptscriptstyle T } } \cdot R _ { 1 } ) \cdot x _ { i j } \cdot ( R _ { 2 } ^ { { \scriptscriptstyle T } } \cdot R _ { 2 } ) \cdot \Phi _ { 2 } \cdot L _ { 2 } ^ { { \scriptscriptstyle T } } } \\ & { = ( L _ { 1 } \cdot \Phi _ { 1 } \cdot R _ { 1 } ^ { { \scriptscriptstyle T } } ) \cdot ( R _ { 1 } \cdot x _ { i j } \cdot R _ { 2 } ^ { { \scriptscriptstyle T } } ) \cdot ( R _ { 2 } \cdot \Phi _ { 2 } \cdot L _ { 2 } ^ { { \scriptscriptstyle T } } ) } \\ & { = ( T _ { 1 } ) ^ { z } \cdot ( R _ { 1 } \cdot x _ { i j } \cdot R _ { 2 } ^ { { \scriptscriptstyle T } } ) \cdot ( T _ { 2 } ) ^ { z } } \end{array}
$$

由于矩阵 $( T _ { 1 } ) ^ { z }$ 的最后 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 列为0,以及 $( T _ { 2 } ) ^ { z }$ 的最后 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 行为 $0$ ，为了加快重构速度，截去矩阵 $( T _ { 1 } ) ^ { z }$ 的最后 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 列，记为 $( \Phi _ { 1 } ) ^ { t }$ ，截去 $( T _ { 2 } ) ^ { z }$ 的最后$b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 行，记为 $( \Phi _ { 2 } ) ^ { t }$ ，则矩阵 $( \Phi _ { 1 } ) ^ { t }$ 和 $( \Phi _ { 2 } ) ^ { t }$ 是秩为[√b²×p]的满秩矩阵，所以式(7)可以改为

$$
\begin{array} { r l } & { L _ { 1 } \cdot y _ { i j } \cdot { L _ { 2 } } ^ { T } } \\ & { = ( T _ { 1 } ) ^ { z } \cdot ( R _ { 1 } \cdot x _ { i j } \cdot { R _ { 2 } } ^ { T } ) \cdot ( T _ { 2 } ) ^ { z } } \\ & { = ( \Phi _ { 1 } ^ { \ t } ) \cdot ( R _ { 1 } \cdot x _ { i j } \cdot { R _ { 2 } } ^ { T } ) ^ { t } \cdot ( \Phi _ { 2 } ^ { \ t } ) } \end{array}
$$

其中： $( R _ { 1 } \cdot x _ { i j } \cdot R _ { 2 } ^ { \textit { T } } ) ^ { t }$ 为截去矩阵 $( \boldsymbol { R _ { 1 } } \cdot \boldsymbol { x _ { i j } } \cdot \boldsymbol { R _ { 2 } } ^ { T } )$ 最后 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 行和最后 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 列后的矩阵。由于矩阵 $\left. \Phi _ { 1 } ^ { \phantom { \dagger } } \right.$ 和 $\Phi _ { 2 } ^ { ~ t }$ 可逆，所以

$$
( R _ { 1 } \cdot x _ { i j } \cdot R _ { 2 } ^ { \textit { T } } ) ^ { t } = ( \Phi _ { 1 } ^ { \textit { t } } ) ^ { - 1 } \cdot ( L _ { 1 } \cdot y _ { i j } \cdot L _ { 2 } ^ { \textit { T } } ) \cdot ( \Phi _ { 2 } ^ { \textit { t } } ) ^ { - 1 }
$$

由于 $( \boldsymbol { R _ { 1 } } \cdot \boldsymbol { x _ { i j } } \cdot \boldsymbol { R _ { 2 } } ^ { T } ) ^ { t }$ 为矩阵 $( \boldsymbol { R _ { 1 } } \cdot \boldsymbol { x _ { i j } } \cdot \boldsymbol { R _ { 2 } } ^ { T } )$ 截去一定行和列后的矩阵，所以将为矩阵 $( \boldsymbol { R _ { 1 } } \cdot \boldsymbol { x _ { i j } } \cdot \boldsymbol { R _ { 2 } } ^ { T } ) ^ { t }$ 依次增加 $b - ( [ \sqrt { b ^ { 2 } \times p } ] )$ 行和b-([√b²×p])列值均为0的向量，填补后的大矩阵记为U。然后，将通过式（10）实现重构。

$$
\hat { x } _ { i j } = R _ { 1 } ^ { - 1 } \cdot U \cdot ( R _ { 2 } ^ { \ T } ) ^ { - 1 }
$$

其中： $\hat { x _ { i j } }$ 为图像块 $x _ { i j }$ 的重构图像。

最后，将依次拼接所有重构出的图像块，相邻图像块之间重复的部分将取平均。以下为本文重构算法的伪代码。

算法 基于流形分离字典构造的分块压缩感知快速重构算法

输入：原始图像 $x \in \mathfrak { i } ^ { \ m \times n }$ ，图像块的采样率 $p$ ，窗口大小 $\boldsymbol { b } \times \boldsymbol { b }$ ，步长 $s$ ，训练集 $s$ a）将原始图像 $x$ 进行分块，即，使用大小为 $\boldsymbol { b } \times \boldsymbol { b }$ 的窗口以步长为 $s$ 遍历整幅图像，从而得到图像块集合 $\{ x _ { i j } \} ~ , ~ i = 1 \colon [ ( m - b ) / s ] + 1  , ~ j = 1 \colon [ ( n - b ) / s ] + 1 :$ （204号

b）利用 SeDiL 算法训练出两组分离字典，并分别对其正交化，记为 ${ \cal L } _ { 1 } , { \cal R } _ { 1 } ^ { \mathrm { ~ \tiny ~ \bar { ~ \ast } \mathrm { \scriptscriptstyle ~ \perp } ~ } } { \cal L } _ { 2 } , { \cal R } _ { 2 }$ ，其中

$L _ { 1 } , L _ { 2 }$ 的大小为 $( [ \sqrt { b ^ { 2 } \cdot p } ] ) \times ( [ \sqrt { b ^ { 2 } \cdot p } ] )$ ， $R _ { 1 } , R _ { 2 }$ 的大小为 $\boldsymbol { b } \times \boldsymbol { b }$ ：

c）构造随机测量矩阵 $\phi _ { 0 } = o r t h ( r a n d n ( b , [ \sqrt { b ^ { 2 } \cdot p } ] ) ) ^ { T }$ ，并利用式(5)构造一组分离字典 $\Phi _ { \imath }$ $\Phi _ { 2 }$ ·

d）利用分离字典对图像块进行压缩采样，即yij=·xj·Φ；

e）利用式(10)对图像块进行重构；

f）将图像块进行重新拼接，重复的部分取平均。拼接完所有图像块后可得到原始图像的重构图像A  
X  
输出： $\it { \Psi } _ { \it { \frac { \cdot } { \cdot } } }$ 0

# 3 实验结果与分析

为了验证本文算法的重构性能，将选取五幅标准图像Lena( $2 5 6 \times 2 5 6 )$ ）、Barbara( $5 1 2 \times 5 1 2$ ）、Camerama( $2 5 6 \times 2 5 6 )$ ）、Man( $5 1 2 \times 5 1 2 )$ ）、Biker $( 2 5 6 \times 2 5 6 )$ 作为测试图，并从图像库"Cropped Labeled Faces in the Wild Database"[11,12]中随机选择12000幅图像作为训练集，采样率分别取 $1 / 1 6 , 9 / 6 4 , 1 / 4 , 9 / 1 6$ 窗口大小为 $1 6 \times 1 6$ ，步长为2。硬件环境为酷睿i5-3470 CPU、8GBRAM以及64位Windows7旗舰版OS的个人电脑，使用MATLAB-2010a仿真软件。采用峰值信噪比(peak signal-to-noiseratio，PSNR)来衡量图像重建效果。此外，将选取当前主流的压缩感知重构算法作为对比算法，其中包括BCS-SPL-DCT[13]、TSBS-VB[14]、s-HM[15]、CISFR[7]。表1给出了不同采样率下，本文算法和其他算法针对五幅测试图像的重构效果。其中，BCS-SDT(blcok compressive sensing- Separable dictionarytraining)为本文算法

表1各种算法重建图像的PSNR 值  

<html><body><table><tr><td></td><td colspan="3">采样率</td><td></td></tr><tr><td>重构算法</td><td colspan="3">1/16 9/64</td><td>9/16</td></tr><tr><td colspan="3">Lena</td><td></td><td></td></tr><tr><td>BCS-SPL-DCT</td><td>19.87</td><td>21.97</td><td>23.88</td><td>28.53</td></tr><tr><td>BCS-SPL-DWT</td><td>20.24</td><td>22.15</td><td>24.32</td><td>29.21</td></tr><tr><td>TSBS-VB</td><td>17.68</td><td>20.97</td><td>23.02</td><td>29.76</td></tr><tr><td>s-HM</td><td>17.84</td><td>20.19</td><td>22.87</td><td>28.43</td></tr><tr><td>BCS-SDT</td><td>23.00</td><td>24.83</td><td>26.58</td><td>31.92</td></tr><tr><td colspan="5">Barbara</td></tr><tr><td>BCS-SPL-DCT</td><td>21.75</td><td>23.27</td><td>24.62</td><td>29.41</td></tr><tr><td>BCS-SPL-DWT</td><td>21.80</td><td>22.95</td><td>24.20</td><td>28.58</td></tr><tr><td>TSBS-VB</td><td>19.99</td><td>21.71</td><td>23.22</td><td>29.50</td></tr><tr><td>s-HM</td><td>19.73</td><td>21.68</td><td>23.39</td><td>28.25</td></tr><tr><td>BCS-SDT</td><td>23.97</td><td>24.88</td><td>26.10</td><td>33.27</td></tr><tr><td colspan="5">cameraman</td></tr><tr><td>BCS-SPL-DCT</td><td>19.53</td><td>22.52</td><td>24.39</td><td>30.10</td></tr><tr><td>BCS-SPL-DWT</td><td>20.07</td><td>22.30</td><td>24.74</td><td>30.82</td></tr><tr><td>TSBS-VB</td><td>19.28</td><td>21.75</td><td>24.44</td><td>31.42</td></tr><tr><td>s-HM</td><td>18.21</td><td>21.08</td><td>24.16</td><td>30.38</td></tr><tr><td>BCS-SDT</td><td>23.36</td><td>25.49</td><td>27.61</td><td>33.38</td></tr><tr><td colspan="5">man</td></tr><tr><td>BCS-SPL-DCT</td><td>21.37</td><td>23.82</td><td>25.44</td><td>29.61</td></tr><tr><td>BCS-SPL-DWT</td><td>22.36</td><td>24.34</td><td>26.28</td><td>30.61</td></tr><tr><td>TSBS-VB</td><td>20.63</td><td>22.67</td><td>24.38</td><td>28.34</td></tr><tr><td>s-HM</td><td>19.37</td><td>22.24</td><td>24.51</td><td>29.41</td></tr><tr><td>BCS-SDT</td><td>25.22</td><td>27.35</td><td>29.23</td><td>34.45</td></tr><tr><td colspan="5">biker</td></tr><tr><td>BCS-SPL-DCT</td><td>17.32</td><td>18.81</td><td>20.42</td><td>24.35</td></tr><tr><td>BCS-SPL-DWT</td><td>17.74</td><td>19.39</td><td>21.00</td><td>25.04</td></tr><tr><td>TSBS-VB</td><td>15.41</td><td>17.64</td><td>19.20</td><td>23.36</td></tr><tr><td>s-HM</td><td>15.76</td><td>17.77</td><td>19.56</td><td>24.02</td></tr><tr><td>BCS-SDT</td><td>20.64</td><td>22.61</td><td>24.53</td><td>30.47</td></tr></table></body></html>

从表1中可以看出，对于实验中所选取的五幅图像，无论采样率的高低，本文算法的重构效果都优于其他四种算法。对于Lena和Cameraman 图像，本文算法重构图像的PSNR值比BCS-SPL 系列算法高 $2 . 2 6 { \sim } 3 . 8 3 ~ \mathrm { d B }$ ，比 TSBS-VB 算法高$1 . 9 6 { \sim } 5 . 3 2 ~ \mathrm { d B }$ ，比s-HM算法高 $3 . 0 0 { \sim } 5 . 1 6 ~ \mathrm { d B }$ 。这大致说明了本文所提出的BCS-SDT算法能更好地恢复出边缘信息比较复杂的图像。对于Barbara 图像，本文算法的重建图像质量均高于其他算法，比BCS-SPL系列算法高 $1 . 4 8 { \sim } 4 . 6 9 \mathrm { d B }$ ，比TSBS-VB算法高 $2 . 8 8 { \sim } 3 . 9 8 \mathrm { d B }$ ，比s-HM算法高 $2 . 7 1 { \sim } 5 . 0 2 \mathrm { d B }$ 。这可明显说明BCS-SDT算法对边缘纹理较多的图像的重构效果比其他算法更好。对于纹理结构不复杂的Man和Biker图像，该算法依然明显优于其他算法。针对五幅不同结构图的比较，可以总结出本文提出的BCS-SDT具有十分突出的重构效果。

为了直观地对比各算法的重构效果，图1显示了采样率固定为1/4时，各种算法对Cameraman图像的重构效果。图2显示了采样率固定为1/16时，各种算法对Barbara图像的重构效果。根据图1和2，从视觉主观效果上可以看出，针对不同边缘纹理信息的图像，本文算法的图像重构效果均优于其他算法，且减少了图像块之间的块效应，使得重构出的图像更加清晰。

![](images/bf3de1487b566d36b6b6719f9ce71f3b71d97435f3941bbc764612635032f81f.jpg)  
图1 Cameraman 图像的重构效果

![](images/a98f87d0badacef4508ab2901eb00a9e3541f41be7a47b5fea4a2163aef3ca8d.jpg)  
图2Barbara 图像的重构效果

为了进一步验证本文算法重建效果的优越性，图3中给出了各种算法对五幅所选图在不同采样率下重构图像的PSNR平均值对比。从图3中可以看出，本文算法不同采样率下重构图像的平均PSNR值均明显高于其他算法，具有十分明显的优势，即使在采样率偏低的情况下，依然能够保证重构精度。此外，针对不同属性的图像，本文重构算法均具有很好的稳定性以及普适性。

![](images/cf00c3fc786c98068d4f9e2834499cbbacd23c06ced244274d70c4d658549ac9.jpg)  
图3不同采样率下5幅重构图像的平均PSNR对比

为了比较各算法的重构速度，表2列出了各种算法对Cameraman图像的重构时间。从表2中可以看出，本文算法的重构时间远低于其他算法，平均时间仅为 $3 . 8 3 \mathrm { ~ s ~ }$ ，复杂度明显降低。此外，由于本文重构算法的计算复杂度仅仅来源于矩阵之间的乘积，所以计算复杂度为 $O ( m ^ { 2 } )$ 。其中， $\mathbf { \lambda } _ { m }$ 为测量值的维度。故本文算法的实时性比其他算法更加好。

表2各种算法重构时间/s  

<html><body><table><tr><td rowspan="2">重构算法</td><td colspan="4">采样率</td><td rowspan="2">平均时间</td></tr><tr><td>1/16</td><td>9/64</td><td>1/4</td><td>9/16</td></tr><tr><td>BCS-SPL-DCT</td><td>26.50</td><td>24.01</td><td>28.26</td><td>24.33</td><td>25.78</td></tr><tr><td>BCS-SPL-DWT</td><td>123.33</td><td>69.13</td><td>50.00</td><td>36.90</td><td>69.84</td></tr><tr><td>TSBS-VB</td><td>49.57</td><td>56.69</td><td>67.89</td><td>105.69</td><td>69.96</td></tr><tr><td>s-HM</td><td>77.17</td><td>91.82</td><td>114.54</td><td>181.36</td><td>116.23</td></tr><tr><td>BCS-SDT</td><td>3.98</td><td>3.44</td><td>3.57</td><td>4.33</td><td>3.83</td></tr></table></body></html>

# 4 结束语

本文提出了一种分块压缩感知快速重构算法，首先，基于矩阵流形训练出一组可分离稀疏表示字典，由于该冗余字典不能满足各列向量之间均正交，所以截取该字典非冗余部分的列向量，构成矩阵并对其正交化，从而得到一组稀疏表示矩阵；其次，构造随机测量矩阵，并通过矩阵运算将其与得到的稀疏表示矩阵进行结合，从而构造出一组分离字典；最后，将该字典用于压缩感知中，且仅通过简单的矩阵运算就能实现图像的重建。本文算法针对不同边缘纹理结构的图像都可以获得比较高的重构质量。此外，能大大减少重构时间。实验结果也表明，与当前压缩感知算法相比，本文算法重构质量更高，重构时间更短。如何进一步降低重构时间和提升重构质量依然值得继续研究，这将在下一步的研究工作中得到完善和解决。

# 参考文献：

[1]Candes EJ,Romberg J,Tao T.Robust uncertainty principles: exact signal reconstruction from highly incomplete frequency information [J].IEEE Trans on Information Theory,2006,52 (2): 489-509.   
[2]Candes EJ,Romberg J,Tao T. Stable signal recovery from incomplete and inaccurate measurements [J].Communications on Pure and Applied Mathematics,2006,59(8):1207-1223.   
[3]Donoho D L.Compressed sensing [J].IEEE Trans on Information Theory, 2006,52 (4): 1289-1306.   
[4]Donoho DL,Tsaig Y,Drori I.Sparse solution of underdetermined linear equations by stage wise orthogonal matching pursuit [J].IEEE Trans on Information Theory,2006,58(2):1094-1121.   
[5]Blumensath T,Davies M E.Gradient pursuits [J].IEEE Trans on Signal Processing,2008,56(6):2370-2382.   
[6] 李星秀，伟志辉，肖亮，等．非局部正则化的压缩感知图像重建算法 [J]．系统工程与电子技术,2013,35(1):196-202.   
[7] Lu Chunshien，Chen Huangwei.Compressive image sensing for fast recovery from limited samples:a variation on compressive sensing [J]. Information Sciences,2015,325:33-47.   
[8]Aharon M,Elad M, Bruckstein A.The K-SVD: an algorithm for designing of overcomplete dictionaries for sparse representation [J]. IEEE Trans on Signal Processing,2006,54(11): 4311-4322.   
[9]Hawe S,Seibert M,Kleinsteuber M.Separable dictionary learning [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2013: 438-445.   
[10] Elad M. Optimized projections for compressed sensing[J]. IEEE Trans on Signal Processing,2007,55 (12): 5695-5702.   
[11] Hawe S,Kleinsteuber M,Diepold K.Analysis operator learning and its application to image reconstruction [J]. IEEE Trans on Image Processing, 2013,22 (6):2138-2150.   
[12] Rubinstein R,Zibulevsky M,Elad M.Double sparsity: learning sparse dictionaries for sparse signal approximation [J].IEEE Trans on Signal Processing,2010,58 (3):1553-1564.   
[13] Gan Lu.Block compressed sensing of natural images $[ \mathrm { C } ] / \AA$ Proc of International Conference on Digital Siagnal Processing.2o07: 403-406.   
[14] He Lihan, Chen Haojun, Carin L.Tree-structured compressive sensing with variational Bayesian analysis [J].IEEE Signal Processing Letters,2010,17 (3): 233-236.   
[15] Yuan Xin,Rao V,Han Shaobo,et al.Hierarchical infinite divisibility for multiscale shrinkage [J]. IEEE Trans on Signal Processing,2O14,62(17): 4363-4.