# 多通道三维视觉指导运动想象脑电信号特征选择算法

胡敏，王志强，黄宏程，李冲(重庆邮电大学通信与信息工程学院，重庆 400065)

摘要：针对基于三维视觉指导的运动想象脑机接口多通道冗余信息较多、分类准确率差的问题，提出了一种基于小波包分解（WPD一共空间滤波（CSP）一自适应差分进化（ADE）的模式脑电信号特征提取与选择分类方法。首先，对采集的多通道运动想象脑电信号进行WPD变化，划分出精细的子频带；然后，分别将WPD变换后的每个子空间作为CSP的输入，得到对应的特征向量；最后，使用ADE 算法对特征向量进行选择，选择出用于分类的最佳特征子集。采用WPD-CSP-ADE模式进行特征提取与选择，较经典的WPD-CSP方法在分类正确率、特征个数方面有着更好的表现。同时，所提算法分类性能明显优于遗传算法、粒子群算法。实验结果表明，WPD-CSP-ADE 方法能够有效地提高分类正确率，同时减少了用于分类的特征个数。

关键词：脑机接口；运动想象；脑电信号；特征选择；自适应差分进化中图分类号：TN911.7 doi:10.3969/j.issn.1001-3695.2018.08.0630

Feature selection algorithm for 3D visual guidance multi-channel motor imagery

Hu Min, Wang Zhiqiang, Huang Hongcheng†,Li Chong (School of Communication & Information Engineering,Chongqing Universityof Posts & Telecommunications,Chongqing 400065, China)

Abstract: Concern the problem that multi-channel Motor Imagery(MI)of Brain-Computer Interface (BCI)based on 3D visual guidance with more redundancy information and poorclassfication accuracy，this paper proposeda patern classification method basedon waveletpacket decomposition(WPD)-common spatial pattern(CSP)-adaptive diferential evolution(ADE)for feature extractionof electroencephalogram（EEG）.Firstly,thisalgorithm usedWPD todivide the multi-channel motion imagery EEG signals into finesub-bands.Secondly，it used CSP to obtain theeigenvectors corresponding toeach subspaceof WPD transformation.Finally,itselected the feature vectors through theADEalgorithm to obtain the bestfeature subsets forclassification.Using WPD-CSP-ADE mode for feature extractionand selection,ithad beter performance in clasification accuracy and number offeatures than the classic WPD-CSP method. At the same time, theclasification performanceof theproposed algorithm was significantly beter than the genetic algorithm and particle swarm optimization algorithm.The experiments show that the WPD-CSP-ADE method can effectively improve the classification accuracy and reduce the number of features used for classification.

Key words: brain-computer interface (BCI);motor imagery(MI);electroencephalogram (EEG); feature selection;adaptive differential evolution (ADE)

# 0 引言

脑机接口（BCI）作为一种新兴的人机交互方式，在大脑和计算机等外部电子设备之间建立了不依赖于外周神经和肌肉组织的信息传输通道[1,2]。基于运动想象的脑机接口由于其自发性等特点应用前景广阔[3]。但是，如何有效地获取与识别脑电信号仍是制约运动想象脑机接口发展的主要障碍之一。在脑电信号采集训练过程中，通过视觉诱导方式进行运动想象，保证了脑电信号的信息采集质量，提高了最终分类的正确率[4.5]；同时，为了更好地消除被试者差异以及更加准确地识别被试者的意图，实验通常会采集多路通道的脑电信号。然而，特征复杂且维度较高的多通道信号会消耗大量的计算资源，同时多通道信号存在过多的冗余信息，会干扰到有效的脑电特征，造成分类准确性的下降。

为提高脑电信号分类的准确性，学术界通过使用共同空间模式（common spatial pattern，CSP)对脑电特征信号进行处理[6]。然而由于CSP缺乏频率信息，对特征信息提取不彻底，Yang等人[7]利用小波包分解（waveletpacketdecomposition，WPD）和CSP结合的方式进行特征提取。WPD[8]作为一种快速时频分析算法，能很好地解决CSP 存在的问题。WPD-CSP方法获得了相对较好的方差，有效地提取到脑电的空间特征信息，但不能很好地去除冗余特征，分类性能表现仍然较差。针对这类问题，相关文献中常使用在大搜索空间中有着优异表现的粒子群算法[9]、遗传算法[10]等进化算法对特征进行优化选取。通过去除冗余特征，然后选取最佳的信号特征子集，进化算法在很大程度上提升了分类器的性能，提高了分类的正确率。然而，在对脑电信号特征选择过程中，粒子群算法忽略了脑电特征信号通道间的相关性，而遗传算法对于信号特征的局部能力搜素较差，且其收敛速度较慢[1]。

针对多通道视觉指导运动想象脑机接口中冗余信息较多和经典的进化算法在特征选择过程中存在的问题，本文提出了利用WPD-CSP和自适应差分进化（ADE）算法结合对脑电信号进行特征提取与选择。使用小波包分解方式和共同空间模式对脑电信号进行特征提取，对提取到的特征集采用自适应差分进化算法进行最优选取。经过实验分析，本文所提特征选择算法相对有效地提高了分类正确率。

# 1 特征提取方法

# 1.1小波包分解

WPD具有任意多尺度变化的特点，将特征信号映射到一组互相正交的小波基函数张成的空间上，然后细分信号为高频和低频两个部分，接着对已分的低频信号实施再次分解，同时对高频信号也进行再分解处理，多次细分，从而获取更加精细的频率特征信息[12:13]。考虑到 Haar 小波基实现简单、运算速度较快以及开销较小，本文选用Haar波作为小波基对各通道信号进行小波分解。假设脑电信号的尺度空间为 $H$ ，对其进行2层尺度空间划分，其过程如图1所示， $H _ { i } ^ { j }$ 表示第i层尺度第j个小波包空间。

![](images/afd501ba397482e547ad3679ec39209875ccf359a11b7ab9038dcfc15234864c.jpg)  
图1小波包分解示意图  
Fig.1Schematic diagram of wavelet packet decomposition

# 1.2共同空间模式

CSP作为一种有效的特征提取手段已被广泛应用。它是通过构造一个空间滤波器，使得两类信号经过滤波后，一类信号方差最大化，同时另一类方差最小化，达到区分两类信号的作用[14:15]。假设 $X _ { 1 } ^ { N \times M }$ 和 $X _ { 2 } ^ { N \times M }$ 分别表示运动想象的两类任务，其中：M表示采集点数， $\mathbf { N }$ 表示通道数。则CSP的具体实现步骤如下：

a)计算两类运动想象任务 $X _ { 1 }$ 和 $X _ { 2 }$ 的归一化的协方差、协方差矩阵 $C _ { 1 }$ 和 $C _ { 2 }$ 。

$$
\left\{ \begin{array} { l l } { \displaystyle C _ { 1 } = \frac { X _ { 1 } X _ { 1 } ^ { T } } { t r a c e { \left( X _ { 1 } X _ { 1 } ^ { T } \right) } } } \\ { \displaystyle C _ { 2 } = \frac { X _ { 2 } X _ { 2 } ^ { T } } { t r a c e { \left( X _ { 2 } X _ { 2 } ^ { T } \right) } } } \end{array} \right.
$$

其中： $T$ 是矩阵转置运算符；trace表示对应矩阵的迹。

b)根据归一化的协方差矩阵 $C _ { 1 }$ 与 $C _ { 2 }$ 求得混合空间协方差矩阵 $c$ ，并对混合空间协方差特征分解：

$$
C = C _ { 1 } + C _ { 2 } = U \lambda U ^ { T }
$$

其中： $\lambda$ 为特征值对角矩阵； $U$ 为特征向量矩阵。同时，将特征值对角矩阵 $\lambda$ 进行降序排列变换，对应的特征向量矩阵$U$ 也调整变换。

c)构造白化变换矩阵 $P$ ，进行白化：

$$
P = \lambda ^ { - 1 / 2 } U ^ { T }
$$

$$
\left\{ \begin{array} { l l } { S _ { 1 } = P C _ { 1 } P ^ { T } } \\ { S _ { 2 } = P C _ { 2 } P ^ { T } } \end{array} \right.
$$

再对具有相同特征向量的 $S _ { 1 }$ 和 $S _ { 2 }$ 特征值分解：

$$
\left\{ \begin{array} { l l } { S _ { 1 } = U _ { 1 } \lambda _ { 1 } U _ { 1 } ^ { T } } \\ { S _ { 2 } = U _ { 2 } \lambda _ { 2 } U _ { 2 } ^ { T } } \end{array} \right.
$$

其中： $\lambda _ { 1 } , \lambda _ { 2 }$ 是对应特征值对角矩阵； $U _ { \textrm { 1 } } , U _ { \textrm { 2 } }$ 则是相关的特征

向量矩阵。同时可得 $U _ { 1 } = U _ { 2 }$ ， $\lambda _ { 1 } + \lambda _ { 2 } = I$ ，其中 $I$ 为单位矩阵，可以得到当 $S _ { \mathrm { 1 } }$ 对应的特征值比较小时， $S _ { 2 }$ 对应的特征值则较大，反之也成立。

d)选择特征向量矩阵 $U _ { 1 }$ （或 $U _ { 2 }$ ）中的前 $m$ 列和后 $m$ 列进行重新组合，得到新的矩阵 $B ^ { N \times 2 m }$ ，然后结合白化矩阵，构建空间滤波器 $W$ 为

$$
W = B ^ { T } P
$$

□： $m$ 为正整数，同时 $m$ 的取值范围为 $1 \leq m \leq [ N / 2 ]$

e)利用空间滤波器 $W$ 对信号 $\boldsymbol { \cal X }$ 进行滤波，求得新的时间序列 $z$ 为

$$
Z = W X
$$

将时间序列 $z$ 的第 $j$ 行记为 $Z _ { j } \left( { j = 1 , 2 , . . . , 2 m } \right)$ ，同时定义对应方差 $\boldsymbol { \nu } _ { j }$ 为特征向量，得到特征向量 $f$ 。

$$
\nu _ { j } = \lg \left[ { \frac { \operatorname { v a r } \left( Z _ { j } \right) } { \operatorname { \sum _ { \substack { i = 1 } } } \operatorname { v a r } \left( Z _ { j } \right) } } \right]
$$

$$
\boldsymbol { f } = \left[ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { 2 m } \right] ^ { T }
$$

其中： $\mathrm { v a r } \big ( Z _ { j } \big )$ 表示样本 $Z _ { j }$ 对应的方差。

# 2 基于WPD-CSP-ADE的脑电信号处理

# 2.1 自适应查分进化

差分进化（differentialevolution，DE）算法又称为“差分演化算法”“差异演化算法”，由Store 等人[16]于1995年提出，是一种非常有效的优化算法，与遗传算法（geneticalgorithm,GA）、粒子群优化算法（particle swarm optimization,PSO）一样，差分优化算法通过不断的迭代，进而保留适应度较高的个体。DE 算法的进化流程与GA 非常类似，都包括初始化操作、选择操作、变异操作和选择操作等，但其具体操作有所不同，DE相比于GA，其实施过程中保留种群的全局搜索策略、基于差分的变异操作以及一对一的竞争性策略，在很大程度上降低了遗传操作的复杂度[17]。

差分进化算法作为一个优化算法，其最终的目的是求解最优特征子集：

$$
\begin{array} { r l } & { \operatorname* { m i n } \quad f \left( x _ { 1 } , x _ { 2 } , . . . , x _ { D } \right) } \\ & { s . t \quad x _ { j } ^ { L } \leq x _ { j } \leq x _ { j } ^ { H } } \end{array}
$$

其中： $\mathrm { ~ D ~ }$ 代表解空间的维度； $\boldsymbol { x } _ { j } ^ { L }$ 、 $\boldsymbol { x } _ { j } ^ { H }$ 分别表示是第 $j$ 个分量$x _ { j }$ 取值范围的上、下界。

对式（11）初始化操作，随机产生式（12)。

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { x _ { i } \left( 0 \right) | x _ { j , i } ^ { L } \le x _ { j , i } \left( 0 \right) \le x _ { j , i } ^ { H } } \\ { i = 1 , 2 , . . . , N P ; j = 1 , 2 , . . . , D } \end{array} \right. } \end{array}
$$

$$
x _ { j , i } \left( 0 \right) = x _ { j , i } ^ { L } + r a n d ( 0 , 1 ) \cdot \left( x _ { j , i } ^ { H } - x _ { j , i } ^ { L } \right)
$$

其中： $x _ { \ i } ( 0 )$ 是特征向量集中第0代的第 $i$ 个特征向量子集;$x _ { j , i } \left( 0 \right)$ 是特征向量集中第0代的第 $i$ 个特征向量子集的第 $j$ 个特征向量；NP则代表特征向量集的大小。

a)变异操作。差分策略即随机选取特征向量集中两个不同的特征向量子集，将其向量差缩放，然后与待变异特征向量子集进行向量合成，即

$$
\nu _ { i } \left( g + 1 \right) = x _ { r 1 } \left( g \right)
$$

$$
+ F \cdot { \left( x _ { r 2 } \left( g \right) - x _ { r 3 } \left( g \right) \right) } , i \neq r _ { 1 } \neq r _ { 2 } \neq r _ { 3 }
$$

其中， $F$ 表示缩放因子。

b)交叉操作。对第 $\mathbf { g }$ 代特征向量集合 $\{ x _ { i } \left( g \right) \}$ 及其变异的中间特征向量子集 $\{ x _ { i } \left( g + 1 \right) \}$ 进行特征向量子集间的交叉操作。

$$
u _ { i } ( g + 1 ) = \left\{ \begin{array} { c } { \nu _ { i , j } \left( g + 1 \right) , r a n d \left( 0 , 1 \right) \leq C R } \\ { \nu _ { i , j } \left( g + 1 \right) , j = j _ { r a n d } } \\ { x _ { i } \left( g \right) , o t h e r } \end{array} \right.
$$

其中： $\scriptstyle { C R }$ 表示交叉概率； $j _ { r a n d }$ 为 $[ 1 , 2 , \cdots , \mathrm { D } ]$ 的随机整数。

c)选择操作。利用贪婪算法进行差分进化得到进入下一代特征向量集合的子集：

$$
\displaystyle x _ { i } \left( g + 1 \right) = \left. \begin{array} { c } { u _ { i } \left( g + 1 \right) , f \left( u _ { i } \left( g + 1 \right) \right) \le f \left( x _ { i } \left( g \right) \right) } \\ { x _ { i } \left( g \right) , o t h e r } \end{array} \right.
$$

在DE 算法中， $\scriptstyle { C R }$ 和 $F$ 值选择，决定了特征向量集合多样性，关乎整个算法局部或全局搜索的快慢。基础的DE 算法中， $C R$ 和 $F$ 值一般为固定值，当 $C R$ 与 $F$ 的值较小时，可以提高种群局部搜索能力，加速算法收敛；反之，当 $C R$ 与 $F$ 的值较大时，可以提高种群全局搜索能力，但是收敛速率较慢。为此，对于每次迭代中 $C R$ 和 $F$ 值采用自适应调节，当种群内的个体适应度趋于一致或者收敛于局部最优解时，$C R$ 和 $F$ 适当增大，增加种群的多样性；当种群内的个体适应度较为分散， $C R$ 和 $F$ 适当增大，加快收敛速率。对于 $C R$ 和 $F$ 的自适应调节如下：

在每次变异操作中，对随机选择的三个个体进行从优到劣的排序，得到 $x _ { b } , x _ { m } , x _ { w }$ ，其分别对应的适应度为 $f _ { b } , f _ { m } , f _ { w }$ ，此时变异操作变为

$$
\nu _ { i } \left( g + 1 \right) = x _ { b } \left( g \right) + F _ { i } \cdot \left( x _ { m } \left( g \right) - x _ { w } \left( g \right) \right)
$$

其中: $F _ { i }$ 的取值将根据每次迭代生成差分向量的两个个体自适应变化：

$$
F _ { i } = F _ { L } + \bigl ( F _ { H } - F _ { L } \bigr ) \frac { f _ { m } - f _ { b } } { f _ { w } - f _ { b } }
$$

其中： $F _ { H }$ 为上限缩放因子； $\boldsymbol { F } _ { L }$ 为下限缩放因子。

而交叉操作中交叉概率 $C R$ 变为

$$
C R _ { i } = \left\{ \begin{array} { c c } { C R _ { L } + \left( C R _ { H } - C R _ { L } \right) \displaystyle \frac { f _ { i } - f _ { \mathrm { m i n } } } { f _ { \mathrm { m a x } } - f _ { \mathrm { m i n } } } , f _ { i } > \overline { { f } } } \\ { C R _ { L } } & { , f _ { i } \leq \overline { { f } } } \end{array} \right.
$$

其中： $f _ { i }$ 表示个体 $x _ { i }$ 的适应度； $f _ { \mathrm { m a x } }$ 表示当前种群中的最优个体适应度； $f _ { \mathrm { m i n } }$ 表示当前种群中的最差个体适应度； $\overline { { f } }$ 为当前种群适应度平均值； $C R _ { H }$ 为上限交叉概率； $\ C R _ { { _ L } }$ 为下限交叉概率。

ADE 算法是在DE算法操作流程基础上，使用新的变异操作进行代替，并通过式(17)(18)确定每次进化种群的缩放因子与交叉概率值，ADE算法的具体流程如下：

a)确定ADE算法控制参数，确定适应度函数。控制参数包括：种群大小NP、上限缩放因子 $F _ { H }$ 、下限缩放因子 $\boldsymbol { F } _ { L }$ 、上限交叉概率 $C R _ { H }$ 、下限交叉概率 $\ C R _ { L }$ 。

b)随机产生初始种群。

c)对初始种群进行评价，即计算初始种群中每个个体的适应度值。

d)判断是否达到终止条件或进化代数最大。若是，则终止进化，将得到最佳个体作为最优解输出；若否，继续。

e)按照式(16)进行变异操作，其缩放因子取值由式(17)计算所得。

f)按照式(14)进行交叉操作，得到中间种群，其交叉概率取值由式(18)计算所得。

g)按照式(15)进行选择操作，在原种群和中间种群中选择个体，得到新一代种群。

h)进化代数 $\scriptstyle \mathbf { g = g + } 1$ ，转至d)。

# 2.2基于WPD-CSP-ADE的特征提取与选择

假设对一通过带通滤波器信号进行小波包分解，该信号

的下限截止频率和上限截止频率分别为 $f _ { L }$ 和 $f _ { H }$ ，则通过n阶小波包分解的子频带个数为 $2 ^ { n }$ 。小波包分解等效为通过带宽相同的带通滤波器，则分解的子频带宽度为

$$
w _ { l } = \frac { f _ { H } - f _ { L } } { 2 ^ { n } }
$$

对于经过小波包分解获取的各个子频带脑电信号，其获取到一定的脑电频率特征信息。但是由于脑电信号来自于多个采集通道，且模式分类任务与采集通道存在相关性，因此，使用CSP算法对WPD后的各个子空间频带进行特征提取，可以有效地提取到脑电信号的空间特征信息。但是，在CSP特征提取中，投影矩阵参数 $m$ 值的大小决定了所选特征向量个数，同时也发现投影矩阵前 $m$ 列特征向量和后 $m$ 特征向量方差大小决定了特征差异大小，直接影响最终的分类识别。而对于 $m$ 值的确定，其与脑电信号直接有关，并不存在固定值。通常在脑电信号处理中，采用遍历 $m$ 值的全部取值可能，确定用于该脑电信号的最优值。但是采用这种操作方法，导致了训练过程中计算量消耗较大的问题，尤其对于脑电采集通道较多的情况。而若采取经验值方法确定 $m$ 值，虽然可以提高训练效率，降低计算消耗，但是由于个体间差异，甚至同一个体不同时间段所采集的脑电信号也存在明显特征差异，可能导致选取的 $m$ 值与其最优值存在较大差异，影响到最终的分类识别。

综合考虑m值选取以及WPD-CSP特征提取中的冗余信息，都可能直接影响到脑电信号模式分类的准确性，为此提出对已提取的特征再利用ADE进行特征选择，具体流程如图2所示。首先，使用共同平均参考（common averagereference,CAR）与数字滤波器对运动想象脑电信号进行预处理，获取与运动想象相关的节律频段信号;接着，根据节律频段信号的带宽以及系统处理的精度与开销，选取合适阶数的WPD 进行子频带划分;然后，对WPD每一个子代空间进行CSP特征提取，并保留全部特征向量。此时，通过保留CSP滤波后全部特征的操作，将 $m$ 值取值问题转换为冗余信息处理问题，有效地解决CSP投影矩阵中复杂的 $m$ 值取值问题，即若采集的脑电信号通道为 $N$ ， $m$ 取值就为 $N / \%$ ，则获取特征向量个数为

$$
F V _ { n u m } = 2 ^ { n } \cdot N
$$

由于保留了特征提取后的全部特征，进一步导致 $F V _ { n u m }$ 个特征向量存在更多的频率、空间等维度冗余信息，需要对其进行优化。为此，本文采用ADE算法对WPD-CSP获取的特征进行选择，利用ADE寻优机制，选择出最佳特征子集，再用于最终的分类识别。通过ADE 算法对特征向量集合的处理，目的是为了减少用于分类的特征向量个数，减少特征向量的冗余信息，进而达到提高分类准确性的效果。

另外，考虑到ADE 算法实现中，需要对进化的每一个个体进行适应度评价，以获取当前个体的适应度排序，进而完成后续的变异、交叉以及选择等操作。由于ADE算法进行特征选择是为了选择出适应度高特征子集用于后续分类，最终目的是为了提高分类正确率，所以ADE算法的适应度评价函数可以选择分类器分类正确率来评价。考虑到ADE算法中每一个样本在迭代中适应度值越小，实现进化的可能性就越大，因此将分类器的分类错误率作为适应度评价标准。

综合上述分析，使用WPD-CSP-ADE 算法对运动想象脑电进行模式分类的具体步骤如下：使用最近邻对测试集进行识别，得到识别率，然后构造基于选择特征数的适应度函数 $P$ 为

$$
P = R ^ { ( 1 + N ^ { \rho } ) }
$$

其中： $\rho$ 是控制因子，仿真设置为 ${ \rho = 0 . 5 }$ ； $N$ 是特征数； $R$ 表示识别率。

a)将多通道脑电信号分成训练集和测试集;b)对训练集和测试集的脑电信号用CAR进行滤波；c)根据执行的运动想象任务，确定运动想象脑电信号的节律特性，得出用于分析的脑电信号频率带宽，并使用数字滤波器对训练集和测试集进行截取；

d)根据节律频段信号带宽及系统处理精度与开销，选取合适阶数的WPD对训练集和测试集进行子频带划分；

e）对WPD后的每一个子代空间的训练集和测试集进行CSP 特征提取，并保留全部特征向量;

f)使用ADE 算法对训练集的特征向量进行选择，以分类器分类错误率为适应度函数，确定不同特征个数下的最优的特征子集;

g)使用分类器对训练集不同特征个数下的最优特征子集进行训练，得出该分类器的模式分类模型，并使用该分类模型对测试集进行测试。

![](images/c049efd459985b99340ab5cb858490c97721ab4d76590750245af64e279b317f.jpg)  
图2WPD-CSP-ADE 流程框图Fig.2WPD-CSP-ADE flowchart

# 3 数据处理

# 3.1数据集

实验中5名被试者（年龄分布为24\~27岁，且都是右利手，4男1女）首次参加实验，实验前均未告知任何假设。实验脑电设备主要为OpenBCI脑电信号采集系统及具有64通道的脑电帽。依据10/20脑电系统原理，本次脑电信号采集电极主要有FC3、FCz、FC4、C5、C3、C1、Cz、C2、C4、C6、CP1、CP2、CP3、CPz 和CP4 电极点，参考电极为Fpz,右耳乳突处为接地电极，250HZ的采样频率。被试戴好脑电帽后，分别检测各个电极的阻抗，确保各通道阻抗低于 $2 0 \mathrm { k } \Omega$ 且保持稳定，然后开始运动想象脑电信号采集。采集过程中，被试者根据屏幕中提示的运动场景进行运动想象。

实验的具体执行如图3所示，一个实验周期共持续 $1 2 \mathrm { ~ s ~ }$ 其中前7s为训练时期。具体包括：前2秒静止的三维动画场景；第2\~3秒出现箭头并指示方向，提示进行左手或者右手的运动想象任务，在第3秒时产生提示音，同时出现运动的三维动画场景，持续时间为4秒，这期间用户进行运动想象；后5秒为实验间隔。利用头戴式显示器作为呈现环境，在手推盒子动画为视觉指导场景下每个被试者分别进行200组的运动想象脑电采集，实验过程中随机出现左手和右手的视觉指导动画场景。为了避免因被试疲劳而降低数据的有效性和可靠性，每间隔25组被试者休息5分钟，同时保证每测试100组后再休息20分钟。如图4所示，给出了实验范式中左、右手运动想象的三维动画训练场景。

![](images/15acee5f14fb93982b06218d21a352487cb525c7f03e903fc815a545a91cd76c.jpg)  
图3实验范式

![](images/d889f921d2cf105d0853e5f0c882b5b4a262c75d79c3540816c65416d4ff9427.jpg)  
Fig.3Experimental paradigm   
图4左右手运动想象的三维动画视觉指导场景  
Fig.4Three dimensional animation visual guidance scene for left and right motor imagery

# 3.2 脑电信号处理

为验证算法效果，分别对每个被试者的200组脑电实验数据进行划分，训练集和测试集各100组。

首先对脑电数据进行共同平均参考方法，然后，使用FIR数字带通滤波器对脑电信号进行滤波，由于左右手运动想象所诱发的最相关为Mu（ $8 { \sim } 1 3 \ \mathrm { H z }$ ）和Beta（ $1 3 { \sim } 3 0 \ \mathrm { H z }$ ）节律频段的脑电信号，所以通带频率 $8 { \sim } 3 0 \mathrm { H z }$ 。对预处理后脑电数据进行小波包分解，此时脑电信号的下限截止频率为 $f _ { L }$ 和上限截止频率 $f _ { H }$ 分别为 $8 \mathrm { { H z } }$ 和 $3 0 \mathrm { { H z } }$ ，使用二阶小波包分解，数据集将被分别为[8,13.5]，[13.5,19]，[19,24.5]，[24.5,30]，共四个子频带。对每个子频带的脑电信号进行共空间模式滤波，提取对应子频带的特征信息。其中，该数据集的采集通道数为15，全部子频带经过CSP处理后保留全部特征向量，即获得60维特征向量。由于冗余特征的存在，直接进行分类会影响到最终的分类正确率。所以对于待处理的特征向量集，接着使用自适应差分进化算法进行特征集优化，选择出部分适合于分类的特征。具体ADE算法的各项参数如表1所示。

同时，为了对比ADE算法用于特征选择的效果，仿真实验也对GA、PSO以及DE 算法进行验证，即GA、PSO、DE 同样对基于WPD-CSP特征提取后特征集进行选择，三种算法的具体参数设置如表2\~4所示。

Table1Parameter description of ADE algorithm   

<html><body><table><tr><td>参数名</td><td>参数值</td><td>描述</td></tr><tr><td>NP</td><td>200</td><td>种群规模</td></tr><tr><td>G</td><td>100</td><td>迭代次数</td></tr><tr><td>CRH</td><td>0.6</td><td>上限交叉概率</td></tr><tr><td>CRL</td><td>0.1</td><td>下限交叉概率</td></tr><tr><td>FH</td><td>0.95</td><td>上限缩放因子</td></tr><tr><td>FL</td><td>0.35</td><td>下限缩放因子</td></tr><tr><td>fitness</td><td>分类错误率</td><td>适应度函数</td></tr></table></body></html>

表1ADE 算法的参数描述  
表3PSO 算法的参数描述  

<html><body><table><tr><td>参数名</td><td>参数值</td><td>描述</td></tr><tr><td>PopulationSize</td><td>200</td><td>种群规模</td></tr><tr><td>Generations</td><td>100</td><td>遗传代数</td></tr><tr><td>PopulationType</td><td>二进制编码</td><td>编码方式</td></tr><tr><td>FitnessFcn</td><td>分类错误率</td><td>适应度函数</td></tr><tr><td>SelectionFcn</td><td>轮盘赌算法</td><td>选择算子</td></tr><tr><td>CrossoverFcn</td><td>单点交叉算法</td><td>交叉算子</td></tr><tr><td>MutationFcn</td><td>均匀变异算法</td><td>变异算子</td></tr><tr><td>EliteCount</td><td>2</td><td>下一代的个体数</td></tr><tr><td>StallGenLimit</td><td>50</td><td>停止代数</td></tr></table></body></html>

Table2 Parameter description of GA algorithm   
Table 3Parameter description of PSO algorithm   

<html><body><table><tr><td>参数名</td><td>参数值</td><td>描述</td></tr><tr><td>m</td><td>200</td><td>粒子数</td></tr><tr><td>MaxDT</td><td>100</td><td>最大迭代次数</td></tr><tr><td>@</td><td>0.7298</td><td>惯性权重</td></tr><tr><td>C1</td><td>1.4962</td><td>学习因子1</td></tr><tr><td>C2</td><td>1.4962</td><td>学习因子2</td></tr><tr><td>fitness</td><td>分类错误率</td><td>适应度函数</td></tr></table></body></html>

表4DE 算法的参数描述

表2GA算法的参数描述  
Table 4Parameter description of DE algorithm   

<html><body><table><tr><td>参数名</td><td>参数值</td><td>描述</td></tr><tr><td>NP</td><td>200</td><td>种群规模</td></tr><tr><td>G</td><td>100</td><td>迭代次数</td></tr><tr><td>CR</td><td>0.5</td><td>交叉概率</td></tr><tr><td>F</td><td>0.6</td><td>缩放因子</td></tr><tr><td>fitness</td><td>分类错误率</td><td>适应度函数</td></tr></table></body></html>

# 4 实验结果与分析

# 4.1SVM分类器分类结果

仿真实验中选用径向基函数构造的支持向量机（supportvectormachine,SVM）分类器，利用 $5 { \times } 5$ 交叉验证方法动态自适应的确定最优的参数值。对于五名被试者，分别使用GA、PSO、DE及ADE方法选择不同的特征个数作为特征子集，测试其分类正确率，结果如图5所示。

从图5中可以看出，五名被试者的分类正确率随着选择个数的增加，分类正确率也随之提高，当特征个数达到一定数量后，分类正确率趋于稳定。为了进一步分析，在仅考虑被试者差异的情况，对GA、PSO、DE以及ADE在不同特征个数下的分类正确率进行统计，发现五名被试者（S1\~S5)在特征个数分别在12、10、10、13、8时，达到其最高平均分类正确率。由此可以得出，在相同的运动想象任务下，由于个体间差异，最佳的用于分类的特征子集数量是不同，应根据具体情况进行设定。另一方面，为了对比特征选择前后分类性能以及不同特征选择算法间性能的差异，对五名被试者在不同特征个数及特征选择算法下最佳分类正确率及特征数进行了统计，统计结果如表5所示， $C S P _ { m = 4 }$ 表示仅使用CSP进行特征提取，未进行特征选择。从表5可以看出，GA、PSO、DE 和 ADE较 $C S P _ { m = 4 }$ 情况，平均分类正确率分别提高了 $5 . 5 3 \%$ ， $0 . 2 5 \%$ ， $3 . 2 7 \%$ ， $8 . 0 4 \%$ ，且特征个数分别平均下降了 $6 5 . 0 0 \%$ ， $7 0 . 0 0 \%$ ， $8 2 . 5 0 \%$ ， $6 3 . 7 5 \%$ 。但是，PSO 算法在被试S2和S3分类正确率存在低于 $C S P _ { m = 4 }$ 的情况，同时也发现其较 $C S P _ { m = 4 }$ 算法平均分类正确率无太大差异。

通过上述分析可以看出，四类特征选择算法可以有效的对全部特征集进行选择，改善分类准确性，降低分类器开销。与此同时，使用GA、DE以及ADE 特征选择算法也比仅通过改变CSP算法中投影矩阵参数的分类效果好，其可以有效地解决CSP 算法中 $\mathrm { ~ m ~ }$ 值调参问题。

进一步对四种特征选择算法进行对比，发现ADE的平均分类正确率最高，相较于GA、PSO以及DE，平均分类正确率分别提高了 $2 . 3 8 \%$ 、 $7 . 7 7 \%$ 、 $4 . 6 2 \%$ ，且特征个数ADE较GA和DE无明显差异，比PSO增加2个。整体对比来说，在SVM分类器下，ADE分类表现最好，GA、DE次之，PSO分类表现相对最差。

# 4.2LDA分类器分类结果

为了更加精确地对比四种算法的差异，减少由分类器性能的影响造成的实验差异，又选用了线性判别分析（latentdirichletallocation,LDA）分类器进行实验，统计五名被试者在四种算法下的最佳特征数及其分类正确率，如表6所示。由表6可以看出，ADE的平均分类正确率仍是最高，相较于GA、PSO以及DE，平均分类正确率分别提高了 $2 . 6 \%$ 、$1 1 . 5 2 \%$ 、 $3 . 4 0 \%$ ，特征个数ADE较GA、PS以及DE分别增加0.8、3、1.2个。

另外，对比SVM和LDA作为分类器，四种算法的性能差异。除在DE 算法下，LDA整体分类正确率略高于SVM分类正确率 $0 . 2 \%$ 。其他情况下，GA、PSO以及ADE 在SVM的平均分类正确率都优于LDA。整体对比来看，SVM的平均分类正确率比在LDA下提高了 $2 . 3 5 \%$ ，选择的特征个数无明显差异。

综合SVM和LDA的分类情况，可以得出ADE用于运动想象脑电特征选择的分类正确率表现最好，且选择的特征个数无明显增多。使用WPD-CSP-ADE方法有效的提高了分类正确率，降低了分类器开销。

![](images/e978f0122a0123662fd2bb5d33de11544b8240b5327c1a95b1c5dc13de465f04.jpg)

表5SVM分类器下，五名被试的最佳分类正确率及特征数(a）被试S1不同特征个数下的分类正确率

Table 5The best classification accuracy and number of features of   

<html><body><table><tr><td colspan="8">fivesubjectsunderSVMclassifier</td></tr><tr><td rowspan="2">被试编号</td><td colspan="4">最佳分类正确率/%</td><td colspan="4">特征数/个</td></tr><tr><td>CSPm=4</td><td>GA PSO</td><td>DE</td><td>ADE</td><td>CSPm=4</td><td>GA</td><td>PSO</td><td>DE ADE</td></tr><tr><td>S1</td><td>83</td><td>87</td><td>80 84</td><td>89</td><td>32</td><td>11</td><td>8</td><td>12</td><td>13</td></tr><tr><td>S2</td><td>70</td><td>76</td><td>69 71</td><td>74</td><td>32</td><td>13</td><td>10</td><td>15</td><td>14</td></tr><tr><td>S3</td><td>86</td><td>89</td><td>84 90</td><td>94</td><td>32</td><td>8</td><td>7</td><td>10</td><td>10</td></tr><tr><td>S4</td><td>79</td><td>84</td><td>83 83</td><td>86</td><td>32</td><td>13</td><td>11</td><td>9</td><td>13</td></tr><tr><td>S5</td><td>80</td><td>84</td><td>83 83</td><td>87</td><td>32</td><td>11</td><td>12</td><td>10</td><td>8</td></tr></table></body></html>

表6LDA分类器下，五名被试的最佳分类正确率及特征数

![](images/2de5afbb8c7ec2c4eee89196ee2511bb3221b02d5bb3aa243f0ad92ce68687cf.jpg)  
(b）被试S2不同特征个数下的分类正确率

Table 6The best classification accuracy and number of features of five subjects underLDAclassifier   

<html><body><table><tr><td rowspan="2">被试编号</td><td colspan="4">最佳分类正确率/%</td><td colspan="4">特征数/个</td></tr><tr><td>GA</td><td>PSO</td><td>DE</td><td>ADE</td><td>GA</td><td>PSO</td><td>DE</td><td>ADE</td></tr><tr><td>S1</td><td>85</td><td>81</td><td>84</td><td>91</td><td>10</td><td>7</td><td>11</td><td>13</td></tr><tr><td>S2</td><td>74</td><td>65</td><td>71</td><td>73</td><td>8</td><td>12</td><td>12</td><td>12</td></tr><tr><td>S3</td><td>87</td><td>80</td><td>91</td><td>92</td><td>12</td><td>9</td><td>9</td><td>14</td></tr><tr><td>S4</td><td>82</td><td>79</td><td>84</td><td>86</td><td>13</td><td>8</td><td>9</td><td>9</td></tr><tr><td>S5</td><td>85</td><td>77</td><td>82</td><td>84</td><td>10</td><td>6</td><td>10</td><td>9</td></tr></table></body></html>

# 5 结束语

针对运动想象脑电模式分类中，由于多通道脑电特征复杂、维度较高、冗余信息量大导致的分类正确性的下降、计算消耗量大的问题，提出了利用WPD-CSP-ADE模式对脑电信号进行特征提取与选择。ADE特征选择算法通过自适应调节缩放因子和交叉概率，在全局搜索能力和种群多样性中保持平衡。最后，通过对比研究了GA、PSO、DE以及ADE用于特征选择的性能结果。实验结果表明，ADE用于运动想象脑电特征选择的分类正确率表现最好，且选择的特征个数无明显增多，其能够有效提高分类正确率，降低分类器计算开销。

![](images/d2adf83d9e72b5f9a1f3da991d25ec6a25b58f80a6f02e87a6c7045eaed0e9f6.jpg)  
(c）被试S3不同特征个数下的分类正确率

# 参考文献：

![](images/5dccb8dd54bd57533e1ec1e0e020aae5b761b67376fb955046089f31d7da331b.jpg)

[1]Li Wenyu,Duan Feng， Sheng Shili,et al.A human-vehicle collaborative simulated driving system based on hybrid brain-computer interfaces and computer vision [J].IEEE Trans on Cognitive & Developmental Systems,2018,10(3): 810-822.   
[2]王行愚，金晶，张宇，等．脑控:基于脑一机接口的人机融合控制 [J]. 自动化学报,2013,39(3):208-221.(Wang Xingyu,Jin Jing,Zhang Yu, et al.Brain control:Human-computer integration control based on brain-computer Interface approach [J].Acta Automatica Sinica,2013, 39 (3):208-221.)   
[3]Hamedi M,Salleh S H,Noor A M.Electroencephalographic motor imagery brain connectivity analysis for bci:a review [J].Neural Computation,2016,28 (6): 1-43.   
[4]胡敏，李冲，路荣荣，等．基于三维视觉指导的运动想象训练性能分 析[J]．计算机应用，2018.38(3):836-841.(Hu Min，Li Chong，Lu Rongrong,et al.Performance analysis of motor imagery training based on 3D visual guidance [J]. Journal of Computer Applications,2018, 38(3):836-841.)   
[5]Liang S,Choi K S,Qin J,et al. Enhancing training performance for brain-computer interface with object-directed 3D visual guidance [J]. International Journal of Computer Assisted Radiology & Surgery,2016, 11(11): 1-9.   
[6]Cheng Minmin，Lu Zuhong，Wang Haixian．Regularized common spatial patterns with subject-to-subject transfer of EEG signals [J]. Cognitive Neurodynamics,2017,11(2):173-181   
[7]Yang Banghua,Li Huarong,Wang Qian,et al. Subject-based feature extraction by using fisher WPD-CSP in brain-computer interfaces[J]. Computer Methods & Programs in Biomedicine,2016,129(C): 21-28.   
[8]Lu Na,Li Tengfei,Ren Xaiodong,et al.A deep learning scheme for motor imagery classification based on restricted Boltzmann machines [J].IEEE Trans on Neural Systems & Rehabilitation Engineering A Publication of the IEEE Engineering in Medicine & Biology Society, 2017,25(6):566-576..   
[9]Atyabi A,Luersen M H,Powers D M W.PSO-based dimension reduction of EEG recordings:implications for subject transfer in BCI [J].Neurocomputing,2013,119 (16): 319-331.   
[10] Chai R,Ling SH,Hunter GP,et al.Brain-computer interface classifier for wheelchair commands using neural network with fuzzy particle swarm optimization. [J].IEEE Journal Biomedical & Health Informatics,2014,18(5): 1614-1624.   
[11]Poli R,Kennedy J,Blackwell T. Particle swarm optimization [J]. SwarmIntelligence,2007,1(1):33-57.   
[12]王登，苗夺谦，王睿智．一种新的基于小波包分解的 EEG 特征抽取 与识别方法研究[J]．电子学报，2013,41(1):193-198.(Wang Deng, Miao Duoqian,Wang Ruizhi.A new method of EEG classification with feature extraction based on wavelet packet decomposition [J].Acta Electronica Sinica,2013,41(1):193-198.)   
[13] Hu Dingyin,Li Wei,Chen Xi.Feature extraction of motor imagery EEG signals based on wavelet packet decomposition [C]//Proc of IEEE/ICME International Conference on Complex Medical Engineering. Piscataway,NJ:IEEE Press,2011:694-697.   
[14] Mishuhina V, Jiang Xudong.Feature weighting and regularization of common spatial patterns in EEG-based motor imagery BCI[J].IEEE Signal Processing Letters,2018,25(6): 783-787.   
[15] Park SH,Lee S G. Small sample seting and frequency band selection problem solving using subband regularized common spatial pattern [J]. IEEE Sensors Journal,2017,17(10): 2977-2983.   
[16] Al-Ani A,Alsukker A,Khushaba R N.Feature subset selection using differential evolution and a wheel based search strategy [J]. Swarm & Evolutionary Computation，Swarm and Evolutionary Computation, 2013,9(4): 15-26.   
[17]Bhattcharyya S,Sengupta A,Chakraborti T,et al.Automatic feature selection of motor imagery EEG signals using differential evolution and learning automata [J].Medical & Biological Engineering & Computing, 2014,52(2): 131.

![](images/13c06c093c943590e7fa294ec1ec30c5c04d653c4e0e1d93ea21f76935e119f5.jpg)  
(d）被试S4不同特征个数下的分类正确率  
(e）被试S5不同特征个数下的分类正确率 图5SVM分类器下,五名被试的最佳特征数及分类正确率 Fig.5The best features and classification accuracy of five subjects under SVMclassifier