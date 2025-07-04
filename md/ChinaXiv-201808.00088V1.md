# 分段复合多尺度模糊熵和IGWO-SVM的脑电情感识别

魏雪，吴清

(河北工业大学 人工智能与数据科学学院，天津 300401)

摘要：脑电情感识别在辅助测谎、临床医学、人机交互中发挥着重要作用。为提高脑电的情感识别率，提出了分段复合多尺度模糊熵算法，采用分段粗粒化和计算复合多尺度模糊熵的策略，使提取的特征较好的解决了数据缺失和计算不准确的问题；同时构造了应用余弦非线性收敛因子和动静态位置更新的灰狼算法优化支持向量机的分类模型。为证明所提的两种算法的有效性，进行了仿真实验的验证，并在公开DEAP数据库下与几种常见的支持向量机优化模型比较脑电的情感识别率,结果表明在提出的模型下，效价、唤醒度、优势度、喜欢度的平均识别率分别为 $8 7 . 2 7 \% . 8 7 . 8 1 \%$ ，$8 9 . 0 6 \%$ 、 $8 7 . 5 8 \%$ ，均高于其他算法。另外对比了高/低喜欢度下效价和唤醒度的分类，实验说明喜欢度低时情感识别率较高。

关键词：脑电信号；情感识别；改进灰狼优化算法；SVM优化算法；分段复合多尺度模糊熵 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.05.0299

# EEG emotion recognition based on piecewise complex multi-scale fuzzy entropy and IGWO-SVM algorithm

Wei Xue, Wu Qing (School ofArtificial Intelligence&Data Science Hebei University of Technology,Tianjin300401,China)

Abstract: EEG(Electroencephalography）emotionrecognition are important inauxiliary lie detection,clinical medicineand human-computer interaction.The paperused a piecewisecomplex multi-scale fuzzy entropyto increase therecognitionrate.It proposed piecewisecoarse graining and calculating complex multi-scale fuzzy entropy.It could solve the problemof missing dataand calculating inaccurate entropy.This paper constructed an IGWO-SVM clasification model which used cosine nonlinearconvergence factoranddynamic and staticposition.To prove the validityofthe algorithms,Thepaper performed the simulation experiment. Comparing the EEG emotion recognition rate with severalcommon SVMoptimization models in the public DEAPdatabase,theresults show that the averagerecognitionratesof valance,arousal,dominanceand likingare $8 7 . 2 7 \%$ $8 7 . 8 1 \%$ $8 9 . 0 6 \%$ and $8 7 . 5 8 \%$ in proposed model, which is higher than other algorithms.Comparing the classification of valance andarousalunder high/low liking,experiments show thattherecognitionrate is higher when theliking is lower.

Key Words:EEG signals;emotion recognition;improved grey wolf optimizer algorithm; SVMoptimization algorithm; piecewise complex multi-scale fuzzy entropy

# 0 引言

情感识别是通过对传感器采集的信号进行分析处理从而得出被采集者的情感状态的过程。基于生理信号的情感识别方法比其他指标如面部表情、身体姿势、语音语调等更难以伪装，也能提供更丰富的信息。基于脑电生理信号的情感识别已经广泛用于辅助测谎[1]、心理疾病的识别[2]、与帕金森病人间的人机交互[3]等方面。

近年来，基于非线性动力学的特征提取方法在脑电等生理信号的研究中取得了较好成果，如分形维数[4]、排列熵[5]、谱熵[6]、近似熵[7和样本熵[8]。2007年Chen 等人构造了样本熵的改进一一模糊熵算法[9]，这是一种新的序列复杂度的测量方法，并成功地运用在了体表肌电信号的特征提取和分类。本文借鉴邹晓阳[l0]等人提出的多尺度模糊熵算法（multi-scale fuzzyentropy，MSFE），构建了分段复合多尺度模糊熵算法(piecewisecomplexmulti-scale fuzzyentropy，PCMSFE）作为脑电信号的特征，其选用了分段粗粒化和复合多尺度模糊熵的计算办法。

支持向量机（supportvectormachine，SVM）是脑电信号情感识别中应用最多的一种方法，它可以解决小样本、非线性问题，并且在高维的模式识别中起到了重要作用，但SVM的内部参数对其分类效果影响很大[II。因此，很多研究者将布谷鸟搜索算法（cuckoo search,CS）[12]、粒子群优化算法（particleswarm optimization,PSO)[13]、遗传算法（genetic algorithm,GA)[14]、差分进化（differential evolution,DE)[15]等算法应用到 SVM的参数寻优上，可是这些算法对于SVM参数的优化效果仍有其适应性的问题。Mirjalili 等人[16]创建的灰狼优化算法（greywolfoptimizer,GWO）在寻优方面具有原理简单、需要调整的参数少、易于实现等优点，然而GWO算法也存在过早收敛、容易陷入局部最优、对初始种群有依赖性等问题。为解决上述问题，Zhu等人[17]选取了一种DE和GWO相结合的混合算法，不过两种算法的融合会导致算法体系过于庞大且寻优效果不大理想。Saremi[18]将动态进化种群策略应用到GWO 算法中，提高GWO算法的全局搜索能力。因此，本文创建了一种基于余弦非线性收敛因子和动静态结合进行位置更新的改进灰狼算法（improvedGWO,IGWO），来平衡算法的局部搜索能力和全局搜索能力。

本文主要针对脑电信号情感识别中涉及的特征提取和分类问题进行了如下工作：a）为防止数据的缺失和计算的熵不准确的问题的出现，采取了一种分段粗粒化和计算复合熵的多尺度模糊熵算法,对MSFE和PCMSFE进行了白噪声和1/f噪声的仿真测试和脑电信号的情感识别测试，实验证明PCMSFE的识别准确率高于MSFE;b）对于脑电特征的分类，本文构建了一种改进的灰狼算法优化SVM的参数模型，利用余弦非线性收敛因子和动静态结合的位置更新策略进行改良,选择9个基准测试函数进行了仿真实验，并且对比了在PCMSFE下，IGWO和GWO、PSO、FA（fireflyalgorithm，萤火虫算法）、GA对SVM优化的情感识别准确率，结果表明IGWO对SVM进行优化的识别准确率高于其他算法。另外，比较了分别在喜欢度高和喜欢度低的情况下，效价和唤醒度的分类情况，实验证明喜欢度低时效价和唤醒度的识别率更高。

# 1 相关算法

# 1.1 DEAP数据集

DEAP（database for emotion analysis using physiologicalsignals）数据库[19]是一个公开数据库，是由Koelstra等人提出的对人类情绪状态分析的多通道数据集。DEAP数据库集脑电信号、生理信号和视频信号于一体，提供公开的情感分析数据集，供人们进行实验。数据库记录了32名被试者的脑电图和外围生理信号。

32位健康被试者参与了实验，被试者在实验之前被告知实验方案和自我评估表的含义。被试者在实验中观看40个能够引起情绪显著变化的音乐视频。实验在有可控照明的两个实验室环境中进行，使用BiosemiActiveTwo系统在专用记录PC（Pentium4,3.2GHz）上记录脑电信号和外围生理信号。音乐视频在17英寸的屏幕上呈现，为了最大限度的减少眼球运动，所有视频刺激大致填满2/3的屏幕，被试者大约在离屏幕1米处。实验前每个被试者都会被问及是否舒适，并在必要时进行调整。

实验包括以下几个步骤：a）在屏幕上显示2s的当前视频编号，以通知被试者实验进度;b）5s的基线记录;c）1min的音乐视频的显示;d）被试者进行唤醒度、效价、喜欢度和优势度的自我评估。经过20次实验，被试者进行休息，实验者对信号的质量和电极的位置进行检查。

实验数据集已经经过了简单的预处理，将数据下采样到$^ { 1 2 8 ~ \mathrm { H z } }$ ，并进行了 $4 . 0 { \sim } 4 5 ~ \mathrm { H z }$ 的滤波处理，使用盲源分离技术去除眼电伪迹。每组数据记录总共 $6 3 \mathrm { ~ s ~ }$ ，包括60s实验过程数据和3s的基线数据。本文采用60s的数据段进行实验。

# 1.2脑电信号处理过程

一般的脑电信号情感识别过程主要包括数据的预处理、数据特征的提取、数据特征的分类。本文对脑电信号的处理还包括了对数据的分割和叠加，以提高特征数量，避免因数据量过小而产生分类效果不佳等问题。本文对脑电信号的主要处理步骤和具体流程框架如图1所示。

![](images/703f2afac670e584d3537dce4b7da273554bd6aea6c170036db84257664a1fd8.jpg)  
图1本文脑电信号情感识别的流程框架

a）数据预处理。脑电信号的噪声源头可能是由周围设备产生的静电或电磁场造成的，除了这些外部噪声外，脑电信号还受身体运动和眨眼动作等人为因素的严重影响[20]。对此，DEAP 数据库已经进行了一些相应的处理。根据以往的经验，在实验中Alpha、Beta 波对结果的影响较大，其他波段的影响较小[21]，所以只提取这两个波段进行实验。通过带通FIR滤波器对信号进行过滤，去除小于 $8 \ : \mathrm { H z }$ 和大于 $3 0 \mathrm { H z }$ 的噪声。

b）数据分割。分别对Alpha、Beta 波段的数据进行分割，选取20s的移动窗口对 $6 0 \mathrm { ~ s ~ }$ 数据段进行分割，重叠率为 $1 0 \mathrm { ~ s ~ }$ 共有五段数据，每段数据为 $2 0 ~ \mathrm { s }$ 。

c）特征提取。选择脑电信号中具有显著影响的8个通道（4对）FP1-FP2，AF3-AF4，F3-F4，F7-F8 提取特征，提取每段数据中8个通道的功率谱特征，并计算MSFE特征和PCMSFE特征，以供后续比较不同特征对识别率的影响。

d） 数据叠加。把每段数据提取的12个特征串行叠加，把每段数据并行叠加，每组数据共得到12个Alpha 波段特征 $+ 1 2$ 个Beta波段特征 $= 2 4$ 个特征，每个被试者有40（40个实验）$^ { * } 5 { = } 2 0 0$ 个样本,随机抽取其中 $8 0 \%$ 的样本进行训练,剩余的 $2 0 \%$ 进行测试。

e）特征分类。运用IGWO优化的SVM参数模型（定义为IGWO-SVM模型）对脑电信号进行情感识别，对数据库的效价、唤醒度、优势度、喜欢度进行分类，将GWO、PSO、FA、GA优化的SVM模型与IGWO-SVM模型进行对比。同时，比较IGWO-SVM模型分别在MSFE 特征和PCMSFE 特征下的情感识别率。另外，利用IGWO-SVM模型比较喜欢度高低不同时效价和唤醒度的分类效果。

# 1.3分段复合多尺度模糊熵

脑电信号是非稳定的随机信号，使用传统的波形、能量分析很难达到人们预计的要求。因而，非线性动力学特征被应用到脑电信号的研究中。熵是度量大脑复杂度的重要参数特征，近似熵和样本熵都是衡量时间复杂度的方法，抗噪抗干扰能力较强、所需数据短。但近似熵对参数值的选取不具有一致性；样本熵计算时必须包含一个模板匹配，否则会使计算没有意义。而模糊熵作为样本熵的改进，不仅可以在参数变化时过渡更平滑，还具有更强的抗干扰能力。然而模糊熵是在单一尺度上度量时间序列复杂性的方法，为此文献[10]给出了多尺度模糊熵的概念，用来衡量不同尺度因子下时间序列的复杂性。可这种算法容易导致数据丢失并使计算的熵不够准确，因此本文选用了一种基于分段复合策略的多尺度模糊熵算法进行脑电信号的特征提取。

# 1.3.1传统的多尺度模糊熵

MSFE 方法首先将原始序列 $\left\{ x _ { i } : 1 \leq i \leq N \right\}$ 粗粒化，建立新的粗粒向量 $y _ { j } ( \tau )$ 。

$$
y _ { j } \left( \tau \right) = \frac { 1 } { \tau } \sum _ { i = \left( j - 1 \right) \tau + 1 } ^ { j \tau } x _ { i } , 1 \leq j \leq \frac { N } { \tau }
$$

其中： $\tau = 1 , 2 , \dots$ 是尺度因子。当 $\scriptstyle { \tau = 1 }$ 时， $y _ { j } \left( 1 \right)$ 是原序列。 $\tau > 1$   
时，原始序列被分割成 $\tau$ 个每段长为 $N / \tau$ 的粗粒序列 $y _ { j } ( \tau )$ 。

将粗粒序列顺序排列后，减去序列均值，形成向量 $\pmb { Y } _ { i } ^ { m }$ □利用模糊函数 $\mu { \left( { { d } _ { i j } ^ { m } } , n , r \right) }$ 定义矢量 $\pmb { Y } _ { i } ^ { m }$ 和 $Y _ { j } ^ { m }$ 的相似度 $D _ { i j } ^ { m }$ 。给定函数的嵌入维数 $m$ 和相似容限 $\boldsymbol { r }$ ，定义函数

$$
\phi ^ { \mathrm { m } } \left( n , r \right) = \frac { 1 } { N - m } \sum _ { i = 1 } ^ { N - m } \left( \frac { 1 } { N - m - 1 } \sum _ { j \neq i } ^ { N - m } D _ { i j } ^ { m } \right)
$$

类似地，可扩展到维数 $m { + } 1$

$$
\phi ^ { \mathrm { m + 1 } } \left( n , r \right) = \frac { 1 } { N - m } \sum _ { i = 1 } ^ { N - m } \left( \frac { 1 } { N - m - 1 } \sum _ { j = 1 \atop j \neq i } ^ { N - m } D _ { i j } ^ { m + 1 } \right)
$$

定义多尺度模糊熵为

$$
\mathrm { M S F E } ( m , n , r ) = \operatorname* { l i m } _ { N  \infty } [ \ln ( \phi ^ { m } ( n , r ) ) - \ln ( \phi ^ { m + 1 } ( n , r ) ) ] ( 4 )
$$

当 $N$ 为有限数时，式（4）可表示为

$$
\mathrm { M S F E } \left( m , n , r , N \right) = \ln \left( \phi ^ { m } \left( n , r \right) \right) - \ln \left( \phi ^ { m + 1 } \left( n , r \right) \right)
$$

MSFE为不同尺度因子下的模糊熵，它反映了不同尺度因子下时间序列的复杂性和自相似性。但式（5）定义的MSFE容易导致数据缺失、计算结果不准确，或导致计算的熵未定义。1.3.2基于分段复合策略的多尺度模糊熵

为解决上述MSFE存在的问题，本文采用了分段粗粒化和复合多尺度模糊熵的计算办法。分段粗粒化可以在数据长度不是尺度因子整数倍时，解决数据流失问题；复合多尺度熵的计算能够解决短时间序列在尺度因子大时计算不准确的问题，并且降低诱发未定义熵的概率。主要处理过程如下：

a)原始序列分段粗粒化。传统粗粒化将原始时间序列按尺度因子压缩时，如果数据长度不是尺度因子的整数倍，就会导致部分数据的缺失。受多尺度样本熵的粗粒化改进的启发[22]，将分段粗粒化方法用于多尺度模糊熵，定义

$$
\begin{array} { l } { \displaystyle { y _ { j } ^ { ( p ) ( \tau ) } = \frac { 1 } { \tau } \sum _ { k = ( j - 1 ) \tau + 1 + p } ^ { j \tau + p } x _ { k } , } } \\ { \displaystyle { 1 \leq j \leq \left\lfloor \frac { N - p } { \tau } \right\rfloor , p = 0 , 1 , 2 , . . . , \tau - 1 } } \end{array}
$$

其中: $\tau$ 是尺度因子， $N$ 为时间序列的长度。将粗粒化后的序列$y ( i )$ 按顺序排列，计算向量 $\pmb { Y } _ { i } ^ { m }$ ，

$$
\begin{array} { r l } & { ~ y \left( i \right) : 1 \leq i \leq \Big \lfloor \left( N - p \right) / \tau \Big \rfloor , p = 0 , 1 , 2 , . . . , \tau - 1 } \\ & { } \\ & { Y _ { i } ^ { m } = \Big \{ y \left( i \right) , y \left( i + 1 \right) , . . . , y \left( i + m - 1 \right) \Big \} - y _ { 0 } \left( i \right) } \\ & { ~ i = 1 , 2 , . . . , N - m + 1 } \end{array}
$$

$\pmb { Y } _ { i } ^ { m }$ 代表从第 $i$ 个点开始的连续 $\mathbf { \nabla } _ { m }$ 个 $y$ 的值减去均值 $y _ { 0 } ( i )$

$$
y _ { 0 } \left( i \right) = \frac { 1 } { m } \sum _ { j = 0 } ^ { m - 1 } y \left( i + j \right)
$$

令 $\pmb { Y } _ { i } ^ { m }$ 与 $Y _ { j } ^ { m }$ 间的距离 $d \Big [ Y _ { i } ^ { m } , Y _ { j } ^ { m } \Big ]$ 为两个对应元素的最大差值，即

$$
\begin{array} { l } { { d _ { i j } ^ { m } = d \Big [ Y _ { i } ^ { m } , { Y } _ { j } ^ { m } \Big ] = \displaystyle \operatorname* { m a x } _ { k \in ( 0 , m - 1 ) } \left\{ \big | ~ y \big ( i + k \big ) - y _ { 0 } ( i ) - y \big ( j + k \big ) - y _ { 0 } ( j ) \big | \right\} } } \\ { { i , j = 1 , 2 , . . . N - m , i \not = j } } \end{array}
$$

使用模糊函数 $\mu ( d _ { i j } ^ { m } , n , r )$ 计算矢量 $\pmb { Y } _ { i } ^ { m }$ 和 $Y _ { j } ^ { m }$ 的相似度 $D _ { i j } ^ { m }$

$$
D _ { i j } ^ { m } = \mu \big ( d _ { i j } ^ { m } , n , r \big ) = e ^ { - \big ( d _ { i j } ^ { m } \big ) ^ { n } \big / r }
$$

其中 $: n$ 和 $\boldsymbol { r }$ 分别为指数函数 $\mu { \left( { { d } _ { i j } ^ { m } } , n , r \right) }$ 边界的梯度和宽度。

b)计算复合多尺度模糊熵。MSFE在尺度因子过大时会导致数据长度过小，因此，MSFE分析短时间序列时可能存在计算结果不准确的问题。虽然利用文献[23]中的方法可使问题得到改善，但仍然存在计算不准确和诱发未定义熵的可能性。本文运用了一种复合多尺度模糊熵方法CMSFE（complexmulti-scale fuzzyentropy）来提高计算精度，其定义为

$$
\mathrm { C M S F E } \left( y , \tau , m , r \right) = \ln \left( \phi _ { 0 } ^ { m } \left( n , r \right) \right) - \ln \left( \phi _ { 0 } ^ { m + 1 } \left( n , r \right) \right)
$$

$$
\phi _ { 0 } ^ { m } \left( n , r \right) { = } \frac { 1 } { \tau } { \sum _ { k = 1 } ^ { \tau } } \phi ^ { m } \left( n , r \right)
$$

$$
\phi _ { 0 } ^ { m + 1 } \left( n , r \right) = \frac { 1 } { \tau } \sum _ { k = 1 } ^ { \tau } \phi ^ { m + 1 } \left( n , r \right)
$$

其中: $\phi ^ { m } \left( n , r \right)$ 和 $\phi ^ { m + 1 } \left( n , r \right)$ 可分别通过式（2）（3）计算得到。

式（11）可进一步被简化为

$$
\mathrm { C M S F E } \left( y , \tau , m , r \right) = \ln \left( \sum _ { k = 1 } ^ { \tau } \left( \phi ^ { m } \left( n , r \right) \right) \right) - \ln \left( \sum _ { k = 1 } ^ { \tau } \left( \phi ^ { m + 1 } \left( n , r \right) \right) \right)
$$

式（12）是将传统MSFE相加平均得到的，这样可以降低产生不准确熵和未定义熵的概率。

# 1.4灰狼算法

SVM在脑电信号的特征分类中应用广泛，由于SVM分类效果受内部参数影响很大。相对于PSO、GA算法，使用GWO优化SVM需要调整的参数少、原理简单。但GWO也存在容易陷入局部最优、位置更新不灵活的问题，于是本文利用余弦非线性收敛因子来平衡全局搜索和局部搜索，选取调和平均数和静态平均数相结合的位置更新策略来更新位置。

# 1.4.1基本灰狼算法

灰狼优化算法是一种模拟灰狼群体狩猎的智能算法。灰狼种群有严格的等级制度，社会等级最高为头狼 $\mathbf {  { a } }$ ，它不一定是最强的狼，但必须有强大的领导能力，负责狩猎、捕猎、食物的分配等等。当缺失 $\mathbf {  { a } }$ 狼时， $\beta$ 狼接替 $\mathfrak { a }$ 狼。紧接着是δ狼，@狼追随，负责平衡种群的内部关系，在狩猎时实现对猎物的包围。

灰狼狩猎时，根据收敛因子 $a$ 计算系数变量 $A$ ，当 $\scriptstyle A \mid > 1$ 时，灰狼的群体扩大搜索范围，寻找更好的食物，这对应于全局搜索; $\mid A \mid < 1$ 时，灰狼群体将包围圈缩小，这对应于局部搜索。收敛因子 $a$ 的计算如下所示，

$$
a = 2 - 2 \biggl ( \frac { t } { \operatorname* { m a x } } \biggr )
$$

其中: $t$ 为当前迭代次数，max为最大迭代次数， $a$ 从2线性递减到0。搜索猎物时，根据猎物位置 $\boldsymbol { { X } } _ { p }$ 和灰狼位置 $X \left( t \right)$ 更新灰狼个体位置。判断到猎物的位置后，根据 ${ \bf { \mathscr { a } } } , { \bf { \mathscr { \beta } } } $ ，δ狼的位置$X _ { \mathrm { a } }$ ， $X _ { \mathfrak { s } }$ ， $X _ { \mathfrak { d } }$ 判断与猎物之间的距离 $\boldsymbol { D } _ { \mathrm { a } }$ ， $\pmb { D } _ { \beta }$ ， ${ \pmb D } _ { \mathsection }$ ，对猎物进行包围。式（14）～（16）分别定义了 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 狼朝 $a , \beta$ 、δ狼的前进步长和方向。

$$
\begin{array} { c } { { X _ { \mathrm { { 1 } } } = X _ { \mathrm { { a } } } - A _ { \mathrm { { 1 } } } D _ { \mathrm { { a } } } } } \\ { { { } } } \\ { { X _ { \mathrm { { 2 } } } = X _ { \mathrm { { \mathrm { { \mathrm { { } } } } } } } - A _ { \mathrm { { 2 } } } D _ { \mathrm { { \mathrm { { } } } } } } } \\ { { { } } } \\ { { X _ { \mathrm { { 3 } } } = X _ { \mathrm { { \mathrm { { } } } } } - A _ { \mathrm { { 3 } } } D _ { \mathrm { { \mathrm { { \mathrm { { } } } } } } } } } \end{array}
$$

$$
X \left( t + 1 \right) = \left( { \frac { X _ { 1 } + X _ { 2 } + X _ { 3 } } { 3 } } \right)
$$

式（17）定义了 $\boldsymbol { \omega }$ 狼的最终前进方向。当 $a$ 递减到0时，灰狼种群进行攻击，捕获猎物，GWO获得最优解。

# 1.4.2改进灰狼算法

# 1)余弦非线性收敛因子

群体智能优化算法一般都面临着全局搜索和局部搜索之间的平衡问题，容易陷入局部最优。由式(13)可知，随迭代次数的增加收敛因子 $a$ 由2线性递减到0，而灰狼算法在收敛过程中是非线性变化的， $a$ 的线性递减不能完全体现算法的实际搜索过程。于是，本文采用了余弦非线性收敛因子的定义方式。

$$
a = 2 \cos \left( \frac { \pi } { 2 } \times \left( \frac { t } { \operatorname* { m a x } } \right) ^ { 2 } \right)
$$

灰狼搜索过程中，更新狼个体的位置。

$$
D { = } { \left| { C X } _ { _ { p } } \left( t \right) - X \left( t \right) \right| }
$$

$$
X \left( t + 1 \right) { = } X _ { _ { p } } \left( t \right) { - } A D
$$

$$
\scriptstyle A = 2 a r _ { 1 } - a
$$

$$
\scriptstyle { C = 2 r _ { 2 } }
$$

其中: $c$ 和 $A$ 为系数变量， $\textbf {  { D } }$ 为灰狼个体与食物的距离， $\boldsymbol { { X } } _ { p }$ 为猎物的位置， $X \left( t \right)$ 为第 $t$ 代时灰狼个体的位置， $r _ { \mathrm { { l } } }$ 和 $r _ { 2 }$ 为[0,1]的随机数。

2)结合调和平均数和静态平均数的位置更新

当灰狼判断到猎物的大概位置时，由头狼 $\mathbf {  { a } }$ 带领 $\beta$ 狼和δ狼指导狼群包围猎物，通过计算 $\mathfrak { a }$ ，β，δ狼与猎物之间的距离$\smash { \mathbf { D } _ { \mathrm { d } } }$ ， $\pmb { D } _ { \beta }$ ， ${ \pmb D } _ { \mathsection }$ 来判断猎物的位置，逼近猎物。

$$
\pmb { { \cal D } } _ { a } { = } \big | { \cal C } _ { 1 } \pmb { X } _ { \mathrm { a } } - \pmb { X } \left( t \right) \big |
$$

$$
\pmb { { \cal D } } _ { \beta } = \left| \pmb { C } _ { 2 } \pmb { X } _ { \beta } - \pmb { X } \left( t \right) \right|
$$

$$
\pmb { D } _ { \mathrm { 8 } } = \left| \pmb { C } _ { 3 } \pmb { X } _ { \mathrm { 8 } } - \pmb { X } \left( t \right) \right|
$$

其中: $\pmb { C } _ { 1 }$ ， $\boldsymbol { C } _ { 2 }$ ， $\boldsymbol { C } _ { 3 }$ 为随机变量， $X _ { \mathrm { a } }$ ， $X _ { \mathfrak { s } }$ ， $X _ { \mathfrak { s } }$ 分别表示 $a , \beta$ ，δ的当前位置。根据式（14）－（16）计算 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 狼朝 $\alpha , \beta , \delta$ 狼的前进步长和方向 $X _ { \mathfrak { i } }$ ， $X _ { _ 2 }$ ， $X _ { _ 3 }$ 。

基本GWO算法的位置更新采用静态平均数方法，即取适应度值排名前三的个体进行位置的平均计算，但这容易导致位置更新不灵活，有时难以找到算法的最优解。为此本文选用了调和平均数和静态平均数相结合的方法来更新位置。

$$
X ( t + 1 ) = \frac { 3 } { 1 / X _ { 1 } + 1 / X _ { 2 } + 1 / X _ { 3 } }
$$

式（26）和静态平均数（式（17））结合完成位置的更新。设置一个阈值，当 $\mathfrak { a }$ 狼和δ狼的适应度差值大于阈值时，采用调和平均数更新位置；当差值小于阈值时，使用静态平均数更新位置。经反复实验验证，本文阈值设置为0.1。

# 1.4.3IGWO算法实现步骤

a)设定狼群变量的上限和下限，在上下限中随机初始化狼群位置。初始化灰狼算法的参数值，包括种群规模 $N$ ，最大迭代次数max，α、β、δ狼的位置，初始化目标函数值为无穷。

b)计算每个狼个体的适应度值，根据适应度值的大小来确定食物的位置。选择适应度值排名前三的狼个体作为 $\textbf { \em a }$ ，β，δ狼。

c)搜索猎物时，根据式（20）更新位置。捕获过程中，依据式（23）～（25）更新 $\mathfrak { a }$ ，β，δ狼的位置。根据式（17）（26)计算 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 狼朝 $\textbf { \em a }$ ， $\beta$ ，8狼前进的方向和距离，更新整个狼群的位置。

d)保存迭代时计算的最优个体位置和最优值。如果达到最大迭代次数，输出狼群的最优个体位置和最优值;否则，返回b)。

# 1.5改进灰狼算法优化支持向量机模型步骤

a)初始化灰狼种群，每个灰狼个体的位置由要优化的SVM参数 $c$ 和 $g$ 组成。 $c$ 为惩罚系数，即对误差的宽容度。 $g$ 为针对RBF核函数的参数。初始化狼群的数量、最大迭代次数、 $c$ 和 $g$ 取值的范围，初始化 $\mathbf { \alpha } _ { \mathrm { ~ \mathfrak { ~ a ~ } ~ } }$ 、 $\beta$ 、δ狼的位置和狼群的目标函数值。

b)将初始化的 $c$ 和 $g$ 应用到SVM的样本训练和测试中，将测试后的错误率作为灰狼个体的适应度值，以错误率最小化为目标。

c)根据适应度值对 $\mathbf {  { a } }$ 、β、δ狼的目标函数值进行更新，若适应度值小于 $\mathfrak { a }$ 狼的目标函数值，则将 $\mathfrak { a }$ 狼的函数值更新为适应度值；若适应度值在 $\mathfrak { a }$ 狼与 $\beta$ 狼的函数值之间，则将 $\beta$ 狼的目标函数值更新为适应度值；如果适应度值在 $\beta$ 狼和δ狼之间，则将8狼的函数值更新为适应度值。并将此时的 $c$ 和 $g$ 值保存到相应灰狼的位置中。

d)根据式（18）更新收敛因子 $a$ ，随机获取 $r _ { \mathrm { { l } } }$ 和 $r _ { 2 }$ 的值，计算 $\mathfrak { a }$ 、β、δ狼的位置，计算狼群位置更新的步长和方向。返回最优个体的位置。

e)当算法达到最大迭代次数时，输出 $\textbf { \em a }$ 狼的当前位置和最优值，即 $c$ 值， $g$ 值和训练准确率。

# 2 实验结果及分析

本文仿真环境为Intel@CoreTMi5-8400MCPU $\textcircled { a } 2 . 8 0 \textcircled { \mathrm { G H z } }$

8 GB，Windows10，MATLABR2016b。

# 2.1PCMSFE算法的性能分析实验

为了测试PCMSFE 特征的性能，提取512、1024、2048个采样点的随机噪声和1/f噪声，用来对比MSFE和PCMSFE特征，其中的参数设置为：尺度因子 $\tau = 1 { \sim } 1 5$ ，嵌入维数 $\scriptstyle m = 2$ 相似容限 $r = 0 . 2 ^ { * } \mathrm { s t d }$ （std表示时间序列的标准偏差），边界梯度 $\scriptstyle n = 2$ 。图2（a）～（c）分别表示采样点为512、1024、2048点时，随机白噪声下PCMSFE和MSFE对比结果。图3（a）\~（c）分别表示采样点为512、1024、2048点时，1/f噪声下PCMSFE和MSFE对比结果。从图2和3可以看出，随机白噪声随着尺度的增加，复杂度逐渐降低，1/f噪声随着尺度的增加，复杂度趋于平稳。采样点为512点时，由图2（a）和图3（a)可知，在随机白噪声和1/f 噪声中，MSFE 的标准差大于PCMSFE，并且随着尺度的增加，标准差越来越大。对于PCMSFE，各个尺度上产生的均值误差较小。当采样点由1024点增加到2048点时，如图2（b）（c）和图3（b）（c）所示，MSFE的标准差减小，但总体上MSFE的标准差大于PCMSFE。对于1/f噪声，采样点为2048点时，如图3（c）所示，PCMSFE比MSFE曲线更加平稳，标准差差别不大。由此说明数据长度较短时，采用PCMSFE 算法要优于MSFE 算法。

![](images/1d85129bd2019d9e7159481f25fc78bded9dd224d39fa01767aa702ff6587c51.jpg)  
图2随机白噪声下PCMSFE 和MSFE对比  
图31/f噪声下PCMSFE 和MSFE对比

2 2 2熵 车业委更更 樱霖燃出1.5 重重重車車重車车事里 1.5重重重更重更重重更重重重更車尺多 1 多 1 1PCMSFE 重PCMSFE ΦPCMSFE重-MSFE 重MSFE 重MSFE0.5 0.5 0.55 10 15 5 10 15 5 10 15尺度 尺度 尺度（a）采样点512点 （b）采样点1024点 （c）采样点2048点

# 2.2IGWO 算法的性能分析实验

为了测试IGWO 算法的性能，选取了9个基准测试函数[24]（ $\mathrm { \cdot } \mathrm { F } _ { 1 } { \sim } \mathrm { F } _ { 9 }$ ）进行仿真实验， $\mathrm { F _ { 1 ^ { - } } F _ { 9 } }$ 函数分别为 Sphere Model,GeneralizedRosenbrock'sFunction ，QuarticFunction,GeneralizedRastrigin'sFunction ， GeneralizedGriewankFunction，Ackley's Function， Six-Hump Camel-Back Function,Branin Function，Goldstein-Price Function。其中 $\mathrm { F } _ { 1 } { \sim } \mathrm { F } _ { 3 }$ 函数是单峰基准测试函数； $\mathrm { F } _ { 4 } { \sim } \mathrm { F } _ { 6 }$ 函数是多峰基准测试函数； $\mathrm { F } _ { 7 } { \sim } \mathrm { F } _ { 9 }$ 函数是固定维度多峰基准测试函数。为了确保结果的公平性，所有算法统一设置为，种群规模为30，最大迭代次数为500。

本文采用基本GWO，只改进收敛因子的GWO（记为IGWO1），只改进位置更新的GWO（记为IGWO2）和IGWO分别独立进行30次实验，记录四种算法的平均值和标准差，评价算法的性能，比较结果如表1所示。从表1可以看出，在单峰基准测试函数中，IGWO1在 $\mathrm { F } _ { 1 }$ 中均值和标准差均小于GWO,在 $\mathbf { F } _ { 3 }$ 中标准差小于GWO；IGWO 在 $\mathbf { F } _ { 1 }$ 中均值比GWO更接近于0，在三个函数中标准差均小于GWO。对于多峰基准测试函数，IGWO在 $\mathrm { F } _ { 4 \setminus } \mathrm { F } _ { 5 }$ 中均值和标准差均达到了最优解0;IGWO1、IGWO2、IGWO在F6上的均值均小于GWO的均值，且标准差均为0。对于固定维度多峰基准测试函数，GWO、IGWO1、IGWO2、IGWO在F,F9上均达到了最优解，且IGWO1和IGWO在F7标准差达到0,IGWO2和IGWO在F9中标准差小于GWO。由此可见，IGWO在大多数函数上具有一定的优势，既可以提高函数的搜索精度，又可以使寻优结果更加稳定，综合性能较好。

为了能够进一步说明IGWO的优越性，本文给出了Fi，F4函数的寻优收敛曲线，如图4所示。从图4可以看出，IGWO1可以显著提高GWO的收敛速度和收敛精度，IGWO比GWO具有更快的收敛速度和更高的收敛精度，说明本文提出的IGWO的优化算法是有效的。

表19个基准测试函数的测试结果  

<html><body><table><tr><td rowspan="2">函数</td><td colspan="2">GWO</td><td colspan="2">IGW01</td><td colspan="2">IGW02</td><td colspan="2">IGWO</td></tr><tr><td>均值</td><td>标准差</td><td>均值</td><td>标准差</td><td>均值</td><td>标准差</td><td>均值</td><td>标准差</td></tr><tr><td>F1</td><td>1.80e-27</td><td>2.89e-27</td><td>4.49e-39</td><td>6.06e-39</td><td>1.43e-27</td><td>2.50e-27</td><td>1.58e-39</td><td>4.27e-39</td></tr><tr><td>F2</td><td>27.48</td><td>0.7615</td><td>26.7767</td><td>0.7593</td><td>27.0474</td><td>0.6543</td><td>26.9415</td><td>0.5963</td></tr><tr><td>F3</td><td>0.0019</td><td>0.0012</td><td>0.0013</td><td>6.49e-04</td><td>0.0016</td><td>8.47e-04</td><td>0.0012</td><td>6.10e-04</td></tr><tr><td>F4</td><td>2.2455</td><td>9.03e-16</td><td>5.92e-17</td><td>3.24e-16</td><td>4.91e-11</td><td>0</td><td>0</td><td>0</td></tr><tr><td>F5</td><td>0.0246</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>F6</td><td>1.11e-13</td><td>0</td><td>1.46e-14</td><td>0</td><td>8.61e-14</td><td>0</td><td>1.27e-14</td><td>0</td></tr><tr><td>F7</td><td>-1.0316</td><td>4.51e-16</td><td>-1.0316</td><td>0</td><td>-1.0316</td><td>4.51e-16</td><td>-1.0316</td><td>0</td></tr><tr><td>F8</td><td>0.3979</td><td>0</td><td>0.398</td><td>4.37e-04</td><td>0.3979</td><td>0</td><td>0.3979</td><td>0</td></tr><tr><td>F9</td><td>3</td><td>1.35e-15</td><td>3</td><td>1.35e-15</td><td>3</td><td>4.51e-16</td><td>3</td><td>4.51e-16</td></tr></table></body></html>

![](images/efce94682d8268789e8da51c8ed8c4312e70f21eeb1e335d554d1f94002e6170.jpg)  
图4函数的寻优收敛曲线(左为F1函数,右为F4 函数)

# 2.3脑电信号情感识别实验

本文的实验样本来源于DEAP数据库，使用带通FIR滤波器过滤脑电信号，去除小于 $8 \mathrm { H z }$ 、大于 $3 0 \mathrm { { H z } }$ 的噪声。我们将实验分为效价、唤醒度、优势度、喜欢度四个类别，同时，分别比较在高/低喜欢度下效价和唤醒度的情感识别率。因DEAP数据库不是专门用来评价喜欢度的数据库，有些被试者的数据中喜欢度标签存在不平衡的状况，于是本文忽略了高/低喜欢度比率小于0.3的被试者的数据。最终，有21个被试者的数据被用于测试喜欢度对效价和唤醒度影响的实验。将数据库按照喜欢度的高低分为高喜欢度数据和低喜欢度数据，分别在两个数据库中进行效价和唤醒度分类的实验，训练数据随机取总数据的 $8 0 \%$ ，剩余的 $20 \%$ 为测试数据。为了保证实验数据的公平性，每个被试者的数据以标签数少的数据量为标准。

为了验证IGWO-SVM模型在脑电信号情感识别中的性能，本文将其与GWO、PSO、GA、FA优化的SVM模型进行比较。统一设置优化算法的种群规模为20，最大迭代次数为200，此参数设置保证了寻优算法都可以达到收敛状态。SVM的寻优参数范围设置为： $C \in [ 0 . 0 1 , 1 0 0 ] , g \in [ 0 . 0 1 , 1 0 0 ]$ 。通过寻优算法训练数据集，建立IGWO-SVM（图表中标记为OURS），GWO-SVM，PSO-SVM，GA-SVM，FA-SVM，SVM分类模型。同时，本文建立了传统的MSFE在IGWO-SVM分类下的模型，记为MSFE-IGWO模型。

几个分类模型的平均识别率对比如图5所示，GWO-SVM模型的情感识别率高于其他模型的情感识别率，说明灰狼算法对SVM优化的分类效果高于其他各个算法对SVM的优化效果。IGWO-SVM模型在效价、唤醒度、优势度和喜欢度上的分类效果均高于其他模型，证实本文对于GWO的改进是有效的。MSFE-IGWO模型在各个方面的情感识别率均低于IGWO-SVM模型，表示本文使用的PCMSFE特征比MSFE特征更具有识别性。表2为每个模型对一位被试者识别的时间。由表2可知,IGWO-SVM模型识别一名被试者的情感的时间是最短的，说明IGWO-SVM模型可以缩短运行时间，提高情感识别的效率。表3为每个模型在效价、唤醒度、优势度、喜欢度下的情感识别率的平均值、标准差、最大值和最小值。从表

3可知，IGWO-SVM模型在各个分类上的平均情感识别率均大于其他模型，标准差值小于其他大多数模型的标准差，最高情感识别率可达到 $100 \%$ 。

喜欢度的不同对效价、唤醒度的影响如图6所示，低喜欢度下的效价和唤醒度的分类效果比高喜欢度下的分类效果好，而且比在所有标签下的情感识别率高。可以看出，喜欢度的高低对效价和唤醒度的分类具有一定的影响，观看低喜欢度的视频会有更高的情感识别率。

表2各个模型识别时间  

<html><body><table><tr><td>模型</td><td>OURS</td><td colspan="4">GWO-SVMFA-SVMPSO-SVMGA- SVM</td></tr><tr><td>时间（s）</td><td>6.778</td><td>7.403</td><td>7.123</td><td>14.646</td><td>35.862</td></tr></table></body></html>

![](images/fec4502c4ddc958b8368828d112638423d7412c8edcde34a0dc26a095768a481.jpg)  
图5四个分类标准下各个模型情感识别率对比

![](images/69abfc2e06bd6f91dcd2346636c4504d2cc543b74470b5847bca79b56fcaf951.jpg)  
图6高/低喜欢度下效价和唤醒度分类

表3各个模型在效价、唤醒度、优势度、喜欢度下的分类效果  

<html><body><table><tr><td colspan="2">分类标准</td><td>OURS</td><td>GWO- SVM</td><td>FA-SVM</td><td>PSO- SVM</td><td>GA- SVM</td><td>SVM</td><td>MSFE- IGWO</td></tr><tr><td rowspan="4">效价</td><td>平均值</td><td>87.27</td><td>86.25</td><td>84.84</td><td>80.23</td><td>79.92</td><td>67.25</td><td>84.92</td></tr><tr><td>标准差</td><td>5.832</td><td>5.923</td><td>6.155</td><td>6.879</td><td>7.580</td><td>5.880</td><td>5.626</td></tr><tr><td>最大值</td><td>100</td><td>97.5</td><td>100</td><td>92.5</td><td>95</td><td>81</td><td>92.5</td></tr><tr><td>最小值</td><td>75</td><td>72.5</td><td>72.5</td><td>67.5</td><td>67.5</td><td>57</td><td>72.5</td></tr><tr><td rowspan="4">唤醒度</td><td>平均值</td><td>87.81</td><td>86.17</td><td>85.16</td><td>80.31</td><td>81.17</td><td>69.59</td><td>85.70</td></tr><tr><td>标准差</td><td>5.379</td><td>5.499</td><td>5.783</td><td>6.246</td><td>6.985</td><td>7.820</td><td>6.514</td></tr><tr><td>最大值</td><td>100</td><td>100</td><td>97.5</td><td>90</td><td>95</td><td>85</td><td>97.5</td></tr><tr><td>最小值</td><td>75</td><td>75</td><td>75</td><td>67.5</td><td>65</td><td>56</td><td>72.5</td></tr><tr><td rowspan="4">优势度</td><td>平均值</td><td>89.06</td><td>88.44</td><td>87.73</td><td>82.89</td><td>83.75</td><td>70.09</td><td>87.11</td></tr><tr><td>标准差</td><td>5.950</td><td>6.049</td><td>5.550</td><td>7.435</td><td>6.780</td><td>10.69</td><td>6.633</td></tr><tr><td>最大值</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td></tr><tr><td>最小值</td><td>77.5</td><td>75</td><td>77.5</td><td>65</td><td>70</td><td>59.5</td><td>75</td></tr><tr><td rowspan="4">喜欢度</td><td>平均值</td><td>87.58</td><td>86.33</td><td>80.15</td><td>81.48</td><td></td><td></td><td></td></tr><tr><td>标准差</td><td>6.397</td><td>6.690</td><td>10.32</td><td>8.703</td><td>81.56 9.370</td><td>71.91 8.930</td><td>86.48</td></tr><tr><td>最大值</td><td>97.5</td><td>97.5</td><td>95</td><td>97.5</td><td>95</td><td>95</td><td>6.564</td></tr><tr><td>最小值</td><td>75</td><td>72.5</td><td>55</td><td>62.5</td><td>62.5</td><td>57.5</td><td>97.5 72.5</td></tr></table></body></html>

# 3 结束语

本文构建了一种基于分段复合策略的多尺度模糊熵方法作为脑电信号的特征，利用分段粗粒化方法来解决数据丢失的问题，同时为防止因尺度因子过大而导致多尺度模糊熵计算不准确的问题，选取了复合多尺度模糊熵的方法。然后使用改进的灰狼算法优化的SVM模型来实现脑电信号的情感识别，采用余弦非线性收敛因子和动静态结合的位置更新策略对灰狼算法进行优化，实现了效价、唤醒度、优势度和喜欢度四个类别的分类，并且比较了喜欢度的高低对效价和唤醒度分类的影响。比起其他自发或诱发脑电，用于情感识别的脑电信号反映了被试的情绪状态，提出的算法为脑电信号在人机交互、辅助测谎等领域的应用打下了基础。

# 参考文献：

[1]顾凌云，吕文志，杨勇，等．基于PCANet和SVM的谎言测试研究[J]. 电子学报,2016,44(8):1969-1973.(Gu Lingyun,Lyu Wenzhi, Yang Yong, et al.Deception detection study based on PCANet and support vector machine [J].Acta Electronica Sinica,2016,44(8): 1969-1973.)   
[2]Auerbach RP, Stewart JG, Stanton CH,et al. Emotion-processing biases and resting EEG activity in depressed adolescents [J].Depression & Anxiety,2015,32 (9):693-701.   
[3]Yuvaraj R, Murugappan M,Palaniappan R. The efect of lateralization of motor onset and emotional recognition in PD patients using EEG [J]. Brain Topography,2017,30 (3): 333-34.   
[4]Sharma M,Pachori R B,Acharya U R.A new approach to characterize epileptic seizures using analytic time-frequency flexible wavelet transform and fractal dimension [J]. Pattern Recognition Letters,2O17,94: 172-179.   
[5]Zeng Ke,Ouyang Gaoxiang, Cheng He,et al. Characterizing dynamics of absenceseizure EEG with spatial-temporalpermutation entropy[J]. Neurocomputing,2017,275:57-85.   
[6]Zhang Rui,Xu Peng, Chen Rui,et al.Predicting inter-sesson performance of SMR-based brain-Computer interface using the spectral entropy of resting-state EEG[J]. Brain Topography,2015,28 (5): 680-690.   
[7]Zhang Zhen,Chen Ziyi, Zhou Yi,et al.Construction of rules for seizure prediction based on approximate entropy [J]. Clinical Neurophysiology, 2014,125 (10): 1959-1966.   
[8]Song Yuedong, Zhang Jiaxiang.Discriminating preictal and interictal brain states in intracranial EEG by sample entropy and extreme learning machine [J]. Journal of Neuroscience Methods,2016,257: 45-54.   
[9]Chen Weiting，Wang Zhizhong，Xie Hongbo,et al.Characterization of surface EMG signal based on fuzzy entropy[J]. IEEE Trans on Neural Systems and Rehabilitation Engineering,2007,15(2): 267-272.   
[10]邹晓阳，雷敏．基于多尺度模糊熵的动作表面肌电信号模式识别[J]. 生物医学工程学杂志,2012,29 (6):1184-1188.(Zou Xiaoyang,Lei Min. Paternrecognition of surfaceelectromyography signal basedon multi-scale fuzzy entropy [J]. Journal of Biomedical Engineering,2012,29 (6): 1184-1188. )   
[11] Wu Kuoping,Wang Shengde.Choosing the kernel parameters for support vectormachines by the inter-cluster distance in the feature space [J]. Pattern Recognition,2009,42 (5): 710-717.   
[12]Jiang Minlan,Luo Jingyuan,Jiang Dingde,et al.Acuckoo search-support vector machine model for predicting dynamic measurement errors of sensors [J]. IEEE Access,2017,4(99): 5030-5037.   
[13] Kumari A,Mehra R.Design of hybrid method PSO and SVMfor detection of brain neoplasm [J].International Journal of Engineering and Advanced Technology,2014,3(4): 262-266.   
[14] Shen Chiaping,Lin Jengwei,Lin Fengsheng,et al. GA-SVM modeling of multiclass seizure detector in epilepsy analysis system using cloud computing [J]. Soft Computing,2017,21(8): 2139-2149.   
[15] Xing Baixi, Zhang Kejun,Sun Shouqian,et al.Emotion-driven Chinese folk music-image retrieval based on DE-SVM[J].Neurocomputing,2015, 148: 619-627.   
[16] Mirjalili S,Mirjalili SM,LewisA. Grey wolf optimizer [J].Advances in Engineering Software,2014,69 (3): 46-61.   
[17] Zhu Aijun, Xu Chuanpei,Li Zhi,et al. Hybridizing grey wolf optimization with differential evolution for global optimization and test scheduling for 3D stacked SoC [J]. Journal of Systems Engineering and Electronics,2015, 26 (2): 317-328.   
[18] Saremi S,Mirjalili S Z,Mirjalili S M. Evolutionary population dynamics and grey wolf optimizer [J]. Neural Computing & Applications,2015,26 (5): 1257-1263.   
[19] Koelstra S,Muhl C,Soleymani M,et al.DEAP:a database for emotion analysis；using physiological signals [J]． IEEE Trans on Affective Computing,2012,3 (1):18-31.   
[20] Atkinson J,Campos D. Improving BCI-based emotion recognition by combining EEG feature selection and kernel classifiers [J]. Expert Systems with Applications,2016,47: 35-41.   
[21] Chatchinarat A,Wong K W, Fung C C.A comparison study on the relationship between the selection of EEG electrode channelsand frequency bands used in classfication for emotion recognition [C]/ Proc of International Conference on Machine Learning and Cybernetics. Piscataway,NJ: IEEE Press,2016: 251-256.   
[22] Chang YC,Wu HT, Chen HR,et al. Application of a modified entropy computational method in assessing the complexity of pulse wave velocity signalsin healthy and diabetic subjects [J].Entropy，2014,16(7): 4032-4043.   
[23] Han Tian,Shi Chengcheng,Wei Zhenbo,et al.Analysis of complex time series using a modified multiscale fuzzy entropy algorithm [C]// Proc of International Conference on Identification,Information and Knowledge in the Internet of Things.Piscataway,NJ: IEEE Press,2O16: 45-51.   
[24]郭振洲，刘然，拱长青，等．基于灰狼算法的改进研究[J].计算机应 用研究，2017，34(12):3603-3606.(Guo Zhenzhou,Liu Ran,Gong Changqing,et al. Study on improvement of gray wolf algorithm [J]. Application Research of Computers,2017,34 (12): 3603-3606.)