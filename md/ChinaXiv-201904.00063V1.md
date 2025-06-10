# 基于混合型MUSIC算法对相干信源DOA估计\*

张权」，李思敏²，唐智灵1

(1．桂林电子科技大学 电子工程与自动化学院，广西 桂林 514004;2.广西科技大学 电气与信息工程学院，广西柳州 545006)

摘要：在实际通信环境中，由于传播环境的复杂性使空间中存在大量的相干信号，从而导致信源协方差矩阵的秩亏缺。为使得矩阵的秩恢复到等于信号源数并解决相干信源波达方向（directionof arrival，DOA）估计问题，提出了一种混合型 MUSIC 算法。该算法通过前后向空间平滑技术对天线阵列进行预处理，并将得到的新协方差矢量矩阵应用于改进的IMUSIC 算法进行信号数据处理分析，得到相干信号的DOA 角度估计。仿真结果表明，在信噪比低的情况下，信号间隔很小且存在相关信号时，混合型MUSIC 算法能准确地估计出信源的DOA，验证了该算法的高分辨率和高性能。

关键词：相干信源；多重信号分类；空间平滑；波达方向估计 中图分类号：TN98 doi:10.19734/j.issn.1001-3695.2018.11.0796

Doa estimation of coherent sources based on hybrid music algorithm

Zhang Quan1, Li Simin², Tang Zhiling1† (1.InstituteofElectrical Engineering&Automation,Guilin UniversityofElectronic Technology,Guilin Guangxi 541004, China;2.InstituteofElectrical&InformationEngineeing,GuangxiUniversityofScience&TechnologyLiuzhouGuangxi 545006, China)

Abstract: In the practical communication environment,becauseofthecomplexityofthe propagation environment,there are alot ofcoherent signals in the space,which leads to therank defect ofthe source covariance matrix.Inorder to restore the rank of the matrix to beequalto the number ofsignal sources andsolve the problemofDOA estimation,this paper proposed a hybrid MUSIC algorithm.It pre-processed the antenna arraybythe forward and backward spatial smoothing technique, andapplied the newcovariance vector matrix to the improved IMUSIC algorithm for signal procesing and analysis,and obtainedthe DOAangle estimationofcoherent signals.Thesimulationresults show that the hybrid MUSICalgorithmcan acuratelyestimate the DOAof thesource when thesignal-to-noiseratio islow,thesignalinterval issmall and the correlation signal exists,which verifies the high resolution and high performance of the algorithm.

Key words: coherent signal; multiple signal classification; spatial smoothing; direction of arrival estimation

# 0 引言

空间信号波达方向估计是阵列信号处理中的关键问题，并用于雷达、声呐以及无线通信等许多场合，可以实现对目标的定位与跟踪和信号的空间滤波。

在众多国内外学者的研究探索下，不同的DOA估计算法相继被提出。文献[1]首次提出多信号分类（multiple signalclassification，MUSIC）算法，该算法以信号方向向量与噪声子空间的正交特性为基础，构造空间谱函数通过谱峰搜索进行DOA估计。MUSIC算法在特定的条件下具有很高的分辨力、估计精度及稳定性，并适用于各种形式的阵列天线。之后在MUSIC算法的基础上，演变出基于特征空间的DOA估计算法、修正MUSIC算法、改进MUSIC 算法、求根MUSIC算法（Root-MUSIC）和加权MUSIC算法等。

文献[2]提出修正MUSIC算法，其实质是取前后向空间平滑算法中子阵个数为1的情况，使得子阵长度等于阵元个数。该算法不会减小阵列的孔径，在信噪比较低的情况下依旧具有较高的分辨力。文献[3\~5]提出一种基于特征分解的

DOA估计Root-MUSIC算法，它将空间谱峰值搜索过程转换为多项式求解过程，该算法测向精度高，处理小样本性能优越。文献[6]提出改进MUSIC算法将信号协方差矩阵进行预处理，使信号协方差矩阵分解得到的噪声子空间与信号子空间正交，降低了噪声干扰。文献[7]提出使用最大似然方法来推导阵列的加权MUSIC（w-MUSIC）算法，其通过组合子阵列的加权MUSIC谱来获得整体空间谱。文献[8]提出基于特征空间的DOA估计算法，该算法结合空间平滑技术并利用阵列协方差矩阵的一个子矩阵快速得到信号子空间。无须特征值分解或奇异值分解，降低算法的复杂度并提高了DOA估计效率。

针对相干信号会导致信源协方差矩阵的秩亏缺，使得常用的信号子空间类算法在DOA估计过程中失效。目前解决秩亏缺的问题，多数方法是使信号协方差矩阵的秩得到有效恢复，或重新构造一个秩等于信号源数的矩阵。

空间平滑算法由Evans 等人[9,10]首先提出，其核心原理是将等距线阵分成若干个相互重叠的子阵列，各子阵列的阵列流形相同，而各子阵列的协方差矩阵可以进行平均运算，实现去相干。文献[11\~13]通过对空间平滑算法进行改进，使其成为有效预处理相干信源的算法。文献[11]使用多个循环相关（MCC）和空间平滑处理的同相组合对信号进行DOA估计。该方法在使用两个循环相关矩阵和相应的循环后向矩阵（2MCC-CB）情况下估计精度最高，增强了DOA估计性能。文献[12]提出前后向空间平滑（FBSS）算法，首先将前向平滑的子阵列共轭倒置后形成后向空间平滑，再与前向平滑结合形成前后向空间平滑算法。空间平滑技术及其改进算法对相干信号源的DOA估计具有理想的性能，且计算量很小，便于实现。但它是通过牺牲有效阵元数来换取的，对阵列孔径有一定的损失，且在低信噪比时算法性能较差。文献[14\~15]提出了一种改进的前向/后向空间平滑Root-MUSIC算法，通过利用了实值协方差矩阵的特征值分解（EVD)，降低了Root-MUSIC 算法的运算复杂度。文献[16]提出一种改进的加权空间平滑(IWSS)技术用于相干信源DOA估计。该方法通过应用嵌套空间平滑算法来获得权重矩阵，与WSS方法相比在没有先验信息和初步估计角度值的情况下也能获得较高的分辨率和估计性能。文献[17]利用FB技术提出了一种实值MUSIC算法，将测向过程转换为真实域，从而显着降低计算量。文献[18]提出了I-MMUSIC算法，将前后向空间平滑算法与MMUISC算法的结合并应用于车载防撞雷达。

鉴于以上分析，本文在经典MUSIC算法和当前提出的解相干的算法基础上，提出混合型MUSIC 算法。该算法将前后向空间平滑算法和改进的IMUSIC算法进行融合，并通过MATLAB仿真将其与前后向空间平滑和改进的IMUSIC算法以及传统MUSIC算法进行对比。仿真结果表明，混合型MUSIC算法在处理相干信源DOA估计时具有较高的测向精度和分辨率。

# 1 问题描述

# 1.1均匀线阵信号模型

如图1所示，由 $M$ 根天线阵元均匀直线排列，单元间距为 $\boldsymbol { d }$ ，信号的波长为 $\lambda$ ，布置成一个阵列天线。假设有$p \big ( p < M \big )$ 个窄带信号源平面波辐射到线阵上，信源波达方向$\theta _ { i } ( i = 1 , 2 , \cdots , p )$ ，则第 $t$ 次采样点数的信号模型可表示为

$$
X \left( t \right) = A S \left( t \right) + N \left( t \right)
$$

其中： $X \left( t \right) = \left[ x _ { 1 } \left( t \right) , x _ { 2 } \left( t \right) , \cdots , x _ { M } \left( t \right) \right]$ 表示 $M$ 个天线单元数据矩阵；  
$T$ 表示转置。

$S \left( t \right) = \left[ s _ { 1 } \left( t \right) , s _ { 2 } \left( t \right) , \cdots , s _ { p } \left( t \right) \right] ^ { T }$ 是信源矩阵,其中 $S _ { i } \left( t \right)$ 为第 $\mathbf { \chi } _ { i }$ 个平面波的复振幅。

![](images/b014585c3948f7e417ee3eb9a0538ab0a7e1b77b0a5141aff4140079fd9383fe.jpg)  
图1均匀天线线阵示意图  
Fig.1Schematic diagram of uniform antenna line array

$N \left( t \right) = \left[ n _ { 1 } \left( t \right) , n _ { 2 } \left( t \right) , \cdots , n _ { M } \left( t \right) \right] ^ { T }$ 是噪声矩阵,其中 $n _ { i } \left( t \right)$ 是均值

为0、方差为 $\sigma ^ { 2 }$ 的白噪声,且与信号源不相关。

$\pmb { A } = \left[ \pmb { a } \left( \theta _ { 1 } \right) , \pmb { a } \left( \theta _ { 2 } \right) , \cdots , \pmb { a } \left( \theta _ { p } \right) \right]$ 是方向矩阵。其中 $\pmb { a } ( \theta _ { i } )$ 是均匀线阵响应矢量可表示为

$$
\displaystyle { \boldsymbol { a } } ( \theta _ { i } ) = \left[ 1 \exp \left( - j 2 \pi { \frac { d } { \lambda } } \sin \theta _ { i } \right) \cdots \exp \left( - j 2 \pi ( M - 1 ) { \frac { d } { \lambda } } \sin \theta _ { i } \right) \right] ^ { T }
$$

其中 $\theta _ { i }$ 是信源 $i$ 的波达方向, $i = 1 , 2 , \cdots , p$ 。

# 1.2MUSIC 算法原理

根据上述均匀线阵信号模型，由式（1）可求得阵列信号的协方差矩阵为

$$
\begin{array} { l } { { R = E \big [ X \left( t \right) X ^ { H } \left( t \right) \big ] = A E \big [ S \left( t \right) S ^ { H } \left( t \right) \big ] A ^ { H } + \sigma ^ { 2 } I _ { M } } } \\ { { \nonumber } } \\ { { R = A R _ { S } A ^ { H } + \sigma ^ { 2 } I _ { M } } } \end{array}
$$

其中： $\pmb { R } _ { s }$ 是信号的协方差矩阵； $\sigma ^ { 2 } I _ { \ M }$ 为噪声协方差矩阵； $\pmb { I } _ { M }$ 为 $M$ 阶级单位矩阵。对 $\scriptstyle { R }$ 进行特征分解有

$$
\pmb { R } = \pmb { U } _ { S } \pmb { \Sigma } _ { S } \pmb { U } _ { S } ^ { H } + \pmb { U } _ { N } \pmb { \Sigma } _ { N } \pmb { U } _ { N } ^ { H }
$$

其中： $\pmb { U } _ { s }$ 是由大特征值对应的特征矢量张成的信号子空间；$\pmb { U } _ { N }$ 是由小特征值对应的特征矢量张成的噪声子空间； $\textstyle { \mathcal { Z } } _ { s }$ 为$p$ 个大特征值构成的对角阵。

根据方向矩阵 $A$ 中的各个列向量与噪声子空间正交，故有

$$
{ \pmb U } _ { N } ^ { H } { \pmb a } ( \theta _ { i } ) = { \bf 0 }
$$

考虑到实际接收数据矩阵是有限长的，即数据协方差矩阵的最大似然估计为

$$
\hat { R } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } X X ^ { H }
$$

对 $\hat { R }$ 进行特征分解可得到噪声子空间特征矢量矩阵，由噪声特征向量和信号向量的正交关系，得到阵列空间谱函数：

$$
P _ { \mathit { M U S I C } } \left( \theta \right) = \frac { 1 } { \mathbf { \hat { a } } ^ { H } \left( \theta \right) \hat { U } _ { N } \hat { U } _ { N } ^ { H } \mathbf { a } \left( \theta \right) }
$$

由式 (6)，当 $\pmb { a } ( \theta )$ 与 $\hat { U } _ { N }$ 的各列正交时分母为零，但由于噪声的存在，使得 $P _ { M U S I C }$ 存在尖峰，通过寻找峰值来估计到达角。

# 1.3相干信源对DOA估计影响

下面根据相干信号源数学模型，研究相干信源对DOA估计影响。对于两个平稳信号 $S _ { i } ( t )$ 和 $S _ { j } ( t )$ ，定义它们的相关系数为

$$
\rho _ { i j } = \frac { E \big [ S _ { i } \left( t \right) S _ { j } ^ { \ast } \left( t \right) \big ] } { \sqrt { E \big [ \big | S _ { i } \left( t \right) \big | ^ { 2 } \big ] E \big [ \big | S _ { j } \left( t \right) \big | ^ { 2 } \big ] } }
$$

由施瓦兹不等式可知，相关系数满足 $\big | \rho _ { i j } \big | \leq 1$ 。因此，对于不同信号之间的相关性可表示为：当 $\rho _ { i j } = 0$ 时，称 $S _ { i } \left( t \right)$ 和$S _ { j } \left( t \right)$ 不相关；当 $0 < \mid \rho _ { i j } \mid < 1$ 时，称 $S _ { i } \left( t \right)$ 和 $S _ { j } ( t )$ 部分相关；当$\mid \rho _ { i j } \mid = 1$ 时，称 $S _ { i } ( t )$ 和 $S _ { j } \left( t \right)$ 相干。

当信号源相干时其数学表示为：相干信源间只差一个复常数。假设设有 $n$ 个相干信源，即

$$
S _ { i } \left( t \right) = \alpha _ { i } S _ { 0 } \left( t \right) , i = 1 , 2 , \cdots , n
$$

其中： $S _ { 0 } ( t )$ 为生成信源，因为它生成了入射到阵列上的 $n$ 个相干信号源。故可得相干信号源数学模型：

$$
X \left( t \right) = A \left[ \begin{array} { c } { \alpha _ { 1 } } \\ { \alpha _ { 2 } } \\ { \vdots } \\ { \alpha _ { n } } \end{array} \right] S _ { 0 } \left( t \right) + N \left( t \right) = A \rho S _ { 0 } \left( t \right) + N \left( t \right)
$$

其中： $\rho$ 为复常数组成的 $n { \times } 1$ 维矢量。根据相干信号源模型，假设有 $n$ 个入射信号源 $S _ { 1 } ( t ) , S _ { 2 } ( t ) , \cdots , S _ { n } ( t )$ ，则阵列信号可表示为

$$
X \left( t \right) = \left[ \pmb { a } \left( \theta _ { 1 } \right) \quad \pmb { a } \left( \theta _ { 2 } \right) \quad \cdots \quad \pmb { a } \left( \theta _ { n } \right) \right] \left[ \begin{array} { l } { \pmb { S } _ { 1 } \left( t \right) } \\ { \pmb { S } _ { 2 } \left( t \right) } \\ { \vdots } \\ { \pmb { S } _ { n } \left( t \right) } \end{array} \right] + N \left( t \right)
$$

信源自相关矩阵为 $\pmb { R _ { s } } = E \big [ \pmb { X } \pmb { X } ^ { H } \big ] = \pmb { A } \pmb { R _ { s } } \pmb { A } ^ { H } + \sigma ^ { 2 } \pmb { I }$ ，则信号源相关矩阵为

$$
\begin{array} { c } { { R _ { s } = \left[ \begin{array} { c c c c c } { { S _ { 1 } ( t ) S _ { 1 } ^ { * } ( t ) } } & { { S _ { 1 } ( t ) S _ { 2 } ^ { * } ( t ) } } & { { \cdots } } & { { S _ { 1 } ( t ) S _ { n } ^ { * } ( t ) } } \\ { { S _ { 2 } ( t ) S _ { 2 } ^ { * } ( t ) } } & { { S _ { 2 } ( t ) S _ { 2 } ^ { * } ( t ) } } & { { \cdots } } & { { S _ { 2 } ( t ) S _ { n } ^ { * } ( t ) } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { S _ { n } ( t ) S _ { n } ^ { * } ( t ) } } & { { S _ { n } ( t ) S _ { 2 } ^ { * } ( t ) } } & { { \cdots } } & { { S _ { n } ( t ) S _ { n } ^ { * } ( t ) } } \end{array} \right] } } \\ { { \left[ \begin{array} { c c c c c } { { \sigma _ { 1 } ^ { 2 } } } & { { \rho _ { 1 2 } \sigma _ { 1 } \sigma _ { 2 } } } & { { \cdots } } & { { \rho _ { 1 n } \sigma _ { 1 } \sigma _ { n } } } \\ { { \sigma _ { 1 2 } ^ { 2 } \sigma _ { 1 } \sigma _ { 2 } } } & { { \sigma _ { 2 } ^ { 2 } } } & { { \vdots } } & { { \rho _ { 2 n } \sigma _ { 2 } \sigma _ { n } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { \rho _ { 1 n } ^ { * } \sigma _ { 1 } \sigma _ { n } } } & { { \rho _ { 2 n } ^ { * } \sigma _ { 2 } \sigma _ { n } } } & { { \cdots } } & { { \sigma _ { n } ^ { 2 } } } \end{array} \right] } } \end{array}
$$

其中： $\sigma _ { 1 } ^ { 2 } , \sigma _ { 2 } ^ { 2 } , \cdots , \sigma _ { n } ^ { 2 }$ 为信号 $S _ { 1 } ( t ) , S _ { 2 } ( t ) , \cdots , S _ { n } ( t )$ 的功率。当 $n$ 个信号完全相干时， $\left| \rho _ { i j } \right| = 1$ ，其中 $i$ 和 $j$ 都小于等于 $n$ 。阵列接收的数据协方差 $\pmb { R } _ { s }$ 的秩降为1，导致信号子空间的维数小于信号源数，从而无法正确估计信号源方向。因此针对含有相干信号源的DOA估计核心问题是将信号协方差矩阵 $\pmb { R } _ { s }$ 的秩恢复到等于信号源的个数 $p$ 。

# 2 改进算法

混合型MUSIC算法实质是前后向空间平滑算法和改进的IMUISC算法的融合。首先通过对天线中的阵元分别进行前向和后向平滑预处理后，使得阵列协方差矩阵的秩恢复到信号源个数，将得到的新协方差矢量矩阵按照改进的IMUSIC算法进行信号数据处理分析，得到相干信号的DOA角度估计。下面对该算法的阵列预处理以及具体实现步骤进行说明。

前后向空间平滑算法把前向空间平滑与共轭后向空间平滑算法结合，以此达到增加等效天线数的目的。阵列预处理部分是通过前后向空间平滑算法实现的。两个相干信号同时进入天线阵列时，会使得阵列协方差矩阵的信号子空间的矢量减少；但若两个相干信号同时进入不同的天线阵列，那么这两个阵列协方差矩阵之和的信号子空间的矢量数等于目标数。基于这种思想，利用均匀线阵的平移不变形，将等距线阵划分为若干个相互重叠的子阵列，各子阵列的阵列流形相同，各子阵列的协方差矩阵可以相加后进行平均运算，取代原来意义上的协方差矩阵，从而实现去相干。

![](images/037f781ef20a18c40cd22c446638b7c3fac23b03381a6943d9439c3def379690.jpg)  
图2双向平滑算法子阵划分图

Fig.2Bidirectional smoothing algorithm subarray division diagram如图2所示，均匀线阵含有 $\mathbf { \Omega } _ { M }$ 个阵元，分成相互交错的$\boldsymbol { L }$ 个子阵，每个子阵有 $m$ 个单元，其中 $\scriptstyle { m = M - L + 1 }$ 。

均匀线阵接收到的信号矩阵为

$$
\boldsymbol { X } \left( t \right) = \left[ \boldsymbol { x } _ { 1 } \left( t \right) , \boldsymbol { x } _ { 2 } \left( t \right) , \cdots , \boldsymbol { x } _ { M } \left( t \right) \right] ^ { T }
$$

根据图2的分割，可得第 $\mathbf { \xi } _ { l }$ 个前向子阵收到的信号矩阵为

$$
\mathbf { \ } X _ { l } ^ { f } = \left[ x _ { l } \left( t \right) , x _ { l + 1 } \left( t \right) , x _ { l + 2 } \left( t \right) , \cdots , x _ { l + m - 1 } \left( t \right) \right] ^ { T }
$$

$$
X _ { l } ^ { f } = A \pmb { { \cal D } } ^ { l - 1 } \pmb { { \cal S } } \left( t \right) + N _ { l } \left( t \right) , 1 \leq l \leq L
$$

其中： $\mathrm { ~ \bf ~ \underline { ~ } { ~ D ~ } ~ }$ 是一个对角阵， ${ \cal D } = d i a g \left( \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { p } \right) , \quad \nu _ { i } = \exp \left( - j \omega _ { i } \right)$ 。

$$
D = d i a g \left( e ^ { j \frac { 2 \pi d } { \lambda } \sin { \theta _ { 1 } } } , e ^ { j \frac { 2 \pi d } { \lambda } \sin { \theta _ { 2 } } } , \cdots , e ^ { j \frac { 2 \pi d } { \lambda } \sin { \theta _ { p } } } \right)
$$

则第 $\mathbf { \xi } _ { l }$ 个前向子阵数据协方差矩阵为

$$
\pmb { R } _ { l } ^ { f } = E \Big ( \pmb { X } _ { l } ^ { f } \left( t \right) \pmb { X } _ { l } ^ { f } \left( t \right) ^ { H } \Big ) = \pmb { A } \pmb { D } ^ { l - 1 } \pmb { R } _ { s } \left( \pmb { D } ^ { l - 1 } \right) ^ { H } \pmb { A } ^ { H } + \pmb { \sigma } ^ { 2 } \pmb { I }
$$

利用所有的数据协方差矩阵求矩阵，即为前向空间平滑协方差矩阵 $R ^ { f }$ 为

$$
\pmb { R } ^ { f } = \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \pmb { R } _ { l } ^ { f }
$$

因为子阵阵元数目 $m \geq N$ ，则当 $L { \geq } N$ 时前向空间平滑数据协方差矩阵 $R ^ { f }$ 是满秩的[18]。分析均匀线阵的倒序阵，同理可得后向平滑子阵的接收数据为

$$
X _ { l } ^ { b } = \left[ x _ { M - l + 1 } ^ { * } \left( t \right) , x _ { M - l } ^ { * } \left( t \right) , \cdots , x _ { L - l + 1 } ^ { * } \left( t \right) \right] ^ { T }
$$

$$
{ \pmb X } _ { l } ^ { b } = { \pmb A } { \pmb D } ^ { l - 1 } \big ( { \pmb D } ^ { M - 1 } { \pmb S } ( t ) \big ) ^ { * } + { \pmb N } _ { l } ^ { * } ( t ) \quad 1 \le l \le L
$$

则每个后向平滑子阵的协方差矩阵为

$$
\pmb { R } _ { l } ^ { b } = E \left( X _ { l } ^ { b } \left( t \right) X _ { l } ^ { b } \left( t \right) ^ { H } \right) = A \pmb { D } ^ { l - 1 } \pmb { R } _ { S } \left( \pmb { D } ^ { l - 1 } \right) ^ { H } \pmb { A } ^ { H } + \sigma ^ { 2 } \pmb { I }
$$

同样，后向空间平滑的协方差矩阵为

$$
\pmb { R } ^ { b } = \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \pmb { R } _ { l } ^ { b }
$$

其中： $R ^ { b }$ 是 $R ^ { f }$ 的共轭倒序阵。根据共轭倒序不变性定义前后向平滑协方差矩阵为

$$
R = \frac { 1 } { 2 } \big ( R ^ { f } + R ^ { b } \big )
$$

共轭倒序不变性的优点在于增加子阵数目，改变了基于天线阵列协方差矩阵的特征分解类DOA算法的局限性。

下面将前后向数据协方差 $\scriptstyle R$ 应用于改进的IMUSIC算法进行相干信源DOA估计。改进的IMUSIC算法通过对接收信号协方差矩阵进行重构，使信号协方差矩阵的秩恢复为$r a n k ( \pmb { R } ) = p$ ，从而能有效地估计出信号的DOA。

令 $\boldsymbol { J }$ 为 $M \times M$ 反单位矩阵，即

$$
J = \left[ \begin{array} { c c c c c } { 0 } & { 0 } & { \cdots } & { 1 } \\ { 0 } & { \cdots } & { 1 } & { 0 } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { 1 } & { 0 } & { \cdots } & { 0 } \end{array} \right] _ { M \times M }
$$

在此令改进后的信号相关矩阵为

$$
\pmb { R } _ { 1 } = \pmb { R } + \pmb { J } \pmb { R } ^ { \ast } \pmb { J }
$$

其中： $\pmb { R } ^ { * }$ 为 $\scriptstyle { R }$ 的共轭，此时 $\pmb { R } _ { 1 }$ 成为Hermite 的 Toeplitz 矩阵,$\pmb { R } _ { 1 }$ 是 $\scriptstyle R$ 的无偏估计。

再对 $\pmb { R } _ { 1 }$ 进行奇异值分解得到噪声子空间 $V _ { \ u }$ ：

$$
[ { \pmb U } , { \pmb S } , { \pmb V } ] = s \nu d ( { \pmb R } _ { 1 } )
$$

取 $V _ { u } = { \cal U } \left( : , p + 1 : { \cal M } \right)$ 构造噪声子空间 $V _ { u }$ 。用低秩矩阵代替满秩矩阵 $\pmb { R } _ { 1 }$ ，令

$$
S \left( M - 2 , M - 2 \right) = 0 , S \left( M - 1 , M - 1 \right) = 0 , S \left( M , M \right) = 0
$$

$$
S s = S , R _ { 2 } = U ^ { * } S s ^ { * } V
$$

对于大规模的矩阵，可以用一个秩比较低的矩阵来近似已知矩阵，即矩阵的低秩近似。该问题可转换为一个矩阵分解的问题，即将一个矩阵 $\pmb { R } _ { 1 }$ 分解为

$$
\pmb { R } _ { 1 } = \pmb { R } _ { 2 } + \pmb { Q }
$$

其中： $\pmb { R } _ { 2 }$ 为低秩矩阵； $\varrho$ 为稀疏矩阵。矩阵低秩分解问题可转换为下面的优化问题：

$$
\begin{array} { r } { \operatorname* { m i n } _ { \boldsymbol { r a n k } } \left( \pmb { R } _ { 2 } \right) = \mathbf { \rho } _ { f } \left\| \pmb { R } _ { 1 } - \pmb { R } _ { 2 } \right\| _ { F } } \end{array}
$$

其中： $\left\| \bullet \right\|$ 为谱范数或者Frobenius范数； $f$ 为矩阵 $\pmb { R } _ { 1 }$ 的秩逼近。

对新的协方差矩阵 $\pmb { R } _ { 2 }$ 进行奇异值分解，重复上述步骤，再一次构造噪声子空间 $V _ { u u }$ 。

$$
[ U U , S S , V V ] = s \nu d \left( R _ { 2 } \right)
$$

取 $V _ { u u } = U U ( : , P + 1 : M )$ 作为与噪声特征值对应的特征向量，即噪声子空间 $V _ { u u }$ 。

最后将两次得到噪声子空间矢量进行取平均值，即

$$
V U = \big ( V _ { u u } + V _ { u } \big ) / 2
$$

构造函数的空间谱，即

$$
\hat { P } _ { S I M U S I C } \left( \theta \right) = \frac { 1 } { { \left[ { { \pmb a } ^ { H } \left( \theta \right) V U V U ^ { H } } { \pmb a } \left( \theta \right) \right] } } = \frac { 1 } { { \left\| { { \pmb a } ^ { H } \left( \theta \right) V U } \right\| ^ { 2 } } }
$$

峰值可以通过改变 $\theta$ 值来进行入射信号DOA 估计$\hat { P } _ { S I M U S I C } ( \theta ) \circ$ （204号

根据以上的讨论，混合型MUSIC算法步骤可以总结如下：

a) $M$ 个阵元组成的天线阵列，则第 $\textit { t }$ 次采样点数的信号 模型由式（1）所示。

b)按照前后向空间平滑技术对天线阵列进行划分，求的前向数据信号矢量 $X _ { l } ^ { f }$ 和后向数据信号矢量 $X _ { l } ^ { b }$ 。根据式(16)和（20）分别求出对应的协方差矩阵 $\pmb { R } _ { l } ^ { f }$ 和 $\pmb { R } _ { l } ^ { b }$ 。

c)根据步骤b）中得到的数据矢量，分别求出 $\textbf { \em L }$ 个子阵的数据协方差矩阵的平均值 $R ^ { f }$ 和 $R ^ { b }$ 。

d)由 $R ^ { f }$ 与 $R ^ { b }$ 的均值求前后向数据协方差矩阵 $R ^ { \mathit { \beta } }$ 0

e)令 $\boldsymbol { J }$ 为 $M \times M$ 反单位矩阵，通过对接收信号协方差矩阵$\scriptstyle { R }$ 进行重构，根据式（24）使得 $\pmb { R } _ { 1 }$ 成为Hermite 的 Toeplitz矩阵。

f)再对 $\pmb { R } _ { 1 }$ 进行奇异值分解得到噪声子空间 $V _ { u }$ 。

g)然后用一个低秩矩阵代替满秩矩阵 $\pmb { R } _ { 1 }$ ，构造一个新的协方差矩阵 $\pmb { R } _ { 2 }$ 。重复上述步骤，并重构噪声子空间 $V _ { u u }$ 。

h)通过计算噪声子空间的平均值，可得到前后向平滑协方差矩阵 $\textbf {  { w } }$ 。

i)构造函数的空间谱 $\hat { P } _ { S I M U S I C } ( \theta )$ 。

# 3 仿真和分析

为了更直观地展现算法性能，采用MATLAB对以上算法进行仿真。假设信号满足远场条件和窄带条件，阵元接收到的噪声为平稳零均值高斯白噪声，方差为 $\sigma ^ { 2 }$ 且与目标源不相关。

实验1仿真模型为8阵元均匀直线阵列，阵元间距$d = \lambda / 2$ ，3个信号源分别以来波方向 $. 4 5 ^ { \circ }$ （2 $\cdot \ 0 ^ { \circ } \cdot \ :$ $3 0 ^ { \circ }$ 入射到天线阵列， $0 ^ { \circ }$ 和 $3 0 ^ { \circ }$ 信号间保持完全相干的关系，信噪比均为 $1 0 ~ \mathrm { d B }$ ，采样数为1024。实验仿真结果如图3所示。

由图3明显地可以得出，如果信号是相干的，则经典MUSIC算法的性能严重下降，无法分辨信号源的DOA；另外三种算法可以从空间谱曲线上看到三个明显的峰值极点，并且都对应着精确的入射角，其中混合型MUSIC算法的谱值明显大于其他算法，说明三种算法均能处理相干信号但混合型MUSIC算法性能更优越。

![](images/48fed75fc32920f24b4b43f2db8b7c1fd14d835230e6dd73297429b0918ef5da.jpg)  
图3信源方向为[ $4 5 ^ { \circ } 0 ^ { \circ } 3 0 ^ { \circ } ]$ 仿真结果

实验2仿真模型为8阵元均匀直线阵列，阵元间距$d = \lambda / 2$ ，三个信号源分别以来波方向为 $[ - 2 ^ { \circ } \ 0 ^ { \circ } \ 2 ^ { \circ }$ ]入射到天线阵列，信号间保持完全相干的关系，信噪比均为 $3 0 ~ \mathrm { d B }$ 采样数为1024。实验仿真结果如图4所示。

![](images/0c08b7cfb79f2900bf86b2e81993db206fe26deb6d4efce44b1789239b0d29a7.jpg)  
Fig.3Source direction is $[ - 4 5 ^ { \circ } 0 ^ { \circ } 3 0 ^ { \circ } ]$ simulation result   
图4角度为[ $\cdot 2 ^ { \circ } 0 ^ { \circ } 2 ^ { \circ }$ ]仿真结果 Fig.4Angle is $[ - 2 ^ { \circ } 0 ^ { \circ } 2 ^ { \circ } ]$ simulation result

由图4结果可以得出，在信号间隔很小且存在相干关系时，经典的MUSIC算法和改进的IMUSIC算法完全失效。在同等条件下，混合型MUSIC 算法较之前后向空间平滑算法,更能精确地分辨相邻间隔的相干信源。

实验3仿真模型为8阵元均匀直线阵列，阵元间距$d = \lambda / 2$ ，三个信号源分别以来波方向 ${ - 5 ^ { \circ } }$ 、 $0 ^ { \circ }$ 、 $5 ^ { \circ }$ 入射到天线阵列，信号间保持完全相干的关系，同时设定信噪比SNR分别在30dB、20dB、10dB、5dB，采样数为1024的情况下对四种算法进行仿真。实验仿真结果如图5\~8所示。

![](images/891aaafe1144181c8b26eb5631fc26cf0e9094c92f120879c7cd35bf744ce05d.jpg)  
图5在不同的信噪比下，经典MUSIC算法仿真结果 Fig.5Simulation results of classical MUSIC algorithm at different signal-to-noise ratios

![](images/a94aab552f91a97cbecafa635ef60e7b429d21062964f6030d47d93dff50d1e9.jpg)  
图6在不同的信噪比下，改进的IMUSIC 算法仿真结果 Fig.6.Improved IMUSIC algorithm simulation results at different signal-to-noise ratios

![](images/5fd49149d50cbdcdc4d305ac3b4cec37aa9f3fc985e96bcc45da8da5d163a2ad.jpg)

![](images/88fbce37a4f7863ac9b33f47e8db1becca7e7102f82633acee9973327aef1a25.jpg)  
图7在不同的信噪比下，前后向空间平滑算法仿真结果  
图8在不同的信噪比下，混合型MUSIC算法仿真结果Fig.8Simulation results of hybrid MUSIC algorithmunder differentsignal-to-noise ratios

由图5\~8结果可以得出，随着信噪比的不断递减，算法的分辨能力都出现不同程度的降低。当 $\mathrm { S N R } { = } 3 0$ 时，改进的IMUSIC算法、前后向空间平滑算法和混合型MUSIC算法都能对信号实现DOA估计；当 $\mathrm { S N R } { = } 2 0 \mathrm { d B }$ 或 $1 0 \ \mathrm { d B }$ 时，改进的IMUSIC算法已经无法分辨信号，前后向空间平滑算法出现估计偏差，此时的混合型MUSIC算法依然可以正确分辨；当 $\mathrm { S N R } { = } 5 \mathrm { d B }$ 时，在这种信号间隔很小，信噪比低且信号间完全相干的情况下，混合型MUSIC算法还能很好地估计出信号的DOA，实验证明了混合型MUSIC算法在面对不同信噪比时具有较高的性能及稳定性。

实验4仿真模型为8阵元均匀直线阵列，阵元间距$d = \lambda / 2$ ，两个信号源分别以来波方向 $0 ^ { \circ }$ 、 $5 ^ { \circ }$ 入射到天线阵列，信号间保持完全相干的关系，快拍数为100。选取子阵的阵元数均为6（即对前向平滑算法而言平滑次数为3，对双向平滑算法而言平滑次数为6)。信噪比SNR从 $- 1 0 ~ \mathrm { d } \mathbf { B } \sim 3 0$ dB 变化时，得到四种算法随信噪比变化的估计性能曲线如图9\~11所示。

![](images/eca6d8914a894a3cf7c2cb94159a2f0e7480a516cbb166efa7e4173f0dc62af5.jpg)  
图9成功概率与信噪比的关系

![](images/d2532d3ae7362d193efb1480b340e5c654073333acb3e3c88f7f0c438594e20f.jpg)  
Fig.9Shows relationship between success probability and signal-to-noise ratios   
图10估计偏差与信噪比的关系

![](images/89eec909428e0f83acd5610f596ae01f05b0c063cea3919b916c6acd5a086d68.jpg)  
Fig.7Simulation results of forward and backward spatial smoothing algorithm under different signal-to-noise ratios   
Fig.10Shows relationship between estimated deviation and signal-to-noise ratios   
图11估计方差与信噪比的关系  
Fig.11Shows relationship between estimated variance and signal-to-noise ratios

由仿真结果可以得出，图9说明随着信噪比的增加，四种算法的估计概率都有明显提高；但总体而言，混合型MUSIC算法在低信噪比情况下成功估计概率最高，其次是前后向空间平滑算法，而经典MUSIC算法在低信噪比情况下估计概率最低。图10中说明在信噪比较大时，四种算法的估计偏差都比较小，即有较高的估计精度；而在低信噪比情况下，混合型MUSIC算法依旧有较低的估计偏差。图11说明混合型MUSIC算法的估计标准差最小，也就说明混合型MUSIC算法估计的稳定性较好，其他几种方法相差不大。

综上所述，混合型MUSIC算法的估计信噪比门限更低，估计偏差和估计标准差都较低，具有较高的估计精度和稳定性，特别是当空间信源方位相距较近、信噪比较低时，混合型MUSIC算法性能的优越性会更加突出。

# 4 结束语

本文提出了一种用于相干信源DOA估计的混合型MUSIC算法。该算法实质上是将前后向空间平滑算法和改进的IMUSIC算法进行融合，通过前后向平滑技术对天线阵列进行预处理，并将得到的新协方差矢量矩阵应用于改进的IMUSIC算法进行信号数据处理分析，最后根据数值仿真分析，将混合型MUSIC算法与前后向空间平滑算法和改进的IMUSIC算法进行对比。仿真结果表明，混合型MUSIC算法具有较高的测向分辨力，能够有效估计出独立信号源和相干信号源的来波方向，并且在信噪比较低、信号间隔很小且存在强相关时，混合型MUSIC算法也能很好地估计出信号的DOA，验证了本文提出的混合型MUSIC算法的高分辨率和高性能。

# 参考文献：

[1]Schmidt R,Schmidt R O.Multiple emitter location and signal parameters estimation [J]. IEEE Trans on Antennas & Propagation, 1986,34(3):276-280.   
[2]张小飞．阵列信号处理及MATLAB 实现[M].北京电子工业出版 社，2015.(Zhang Xiaofei.Array signal processing and MATLAB implementation [M].Beijing:Electronics Industry Press,2015.)   
[3]Gupta P,Kar SP.MUSIC and improved MUSIC algorithm to estimate directionofarrival[C]//ProcofInternationalConferenceon Communications and Signal Processing.[S.l.]:IEEE Press,2015: 0757-0761.   
[4]KunDU D.Modified MUSIC algorithm for estimation DOA of signals [J]. Signal Processing,1996,(48): 85-891.   
[5]Qian Cheng,Huang Lei,So H C.Improved unitary root-MUSIC for DOA estimation based on pseudo-noise resampling [J].IEEE Signal Processing Letters,2013,21 (2):140-144.   
[6]Gupta P,Kar S.P.MUSIC and improved MUSIC algorithm to estimate directionof arrival.[C]//Procof International Conferenceon Communicationsand Signal Processing.[S.l.]:IEEE Press,2015: 0757-0761.   
[7]Yan Fenggang,Shen Yi,Jin Ming，et al. Computationally efficient direction finding using polynomial rooting with reduced-order and real-valued computations [J]. Journal of Systems Engineering and Electronics,2016,27 (4): 739-745.   
[8]熊轶．基于特征子空间的波达方向(DOA）估计算法研究[D]．武 汉：华中科技大学,2007.(Xiong Wei.Research on direction of arrival (doa）estimationalgorithmbasedonfeaturesubspace[D]. Wuhan:Huazhong University of Science and Technology,2007.)   
[9]Evans JE, Johnson JR, Sun Fuding. High resolution angular spectrum estimation techniques for terrain scattering analysis and angle of arrival estimation [Cl//Proc of Assp Workshop Spectral Estimation.1982.   
[10] Evans JE,Sun Fuding,Johnson JR.Application of advanced signal processing techniques to angle of arrival estimation in atc navigation and surveillance systems [J]. Calculation,1982.   
[11] Kamiya Y, Kikuma N,Sakakibara K.DOA estimation of desired signals using in-phase combining of multiple cyclic correlations and spatial smoothing processing [C]// Proc of International Symposium on Antennas & Propagation.[S.l.]:IEEE Press,2017.   
[12] Iwai T,Hirose N,Kikuma N,et al.DOA estimation by MUSIC algorithm using forward-backward spatial smoothing with overlapped and augmented arrays [C]// Proc of International Symposium on Antennas and Propagation.[S.l.]:IEEE Press,2015: 375-376.   
[13] Mei Feng,Kammeyer K D.Modified subspace smoothing technique for multipath direction finding [C]// Proc of Signal Processing Conference. [S.l.]:IEEE Press,2015.   
[14] ChoiYangho.Onconditionsfortherankrestorationin forward/backward spatial smoothing [J].IEEE Transon Signal Processing,2002,50 (11): 2900-2901.   
[15] Shu, Changgan,Liu Yumin.An improved forward/backward spatial smoothing Root-MUSIC algorithm based on signal decorrelation[C]// Advanced Research and Technology in Industry Applications. [S.l.]:IEEE Press,2014: 1252-1255.   
[16] Wu Xiangdong,Ma Lun,Liang Zhonghua.Improved weighted spatial smoothing algorithm [J]. Journal of Data Acquisition & Processing, 2015.   
[17] Wang Yan,Si Weijian,Wang Kun.A real-valued MUSIC algorithm with forward/backward technique [C]// Proc of Applied Computational Electromagnetics Society Symposium.[S.l.]:IEEE Press,2017:1-2.   
[18] 贾洁民．基于 MUSIC 算法的相干信号 DOA 估计研究[D].西安： 西安电子科技大学,2015.(Jia Jiemin.Research on DOA estimation of coherent signals based on MUSIC algorithm [D].Xi’an:Xidian University, 2015.)   
[19] Shan Tiejun,Wax M,Kailath T. On spatial smoothing for estimation of coherent signals [J].IEEE Trans on Acoustics Speech & Signal Processing,1985,33 (4): 806-811.