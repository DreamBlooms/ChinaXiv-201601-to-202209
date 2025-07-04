# 基于改进EMD的滚动轴承故障增长特征提取和损伤评估技术

常竞1，温翔²

(1．四川财经职业学院，成都 610101;2．四川省计算机研究院，成都 610041)

摘要：针对传统滚动轴承损伤评估方法未考虑故障特征的稳定性和有效性导致评估的准确度不高的问题，提出了基于改进 EMD（empirical mode decomposition）的滚动轴承故障增长特征提取和损伤评估技术。使用 EMD将不同损伤程度的故障信号分解为一系列的奇异值分量SVD（singularity value decomposition)，建立不同 SVD分量描述的故障增长趋势，分析各级分量对故障增长过程的稳定性和敏感性，提取能有效感知故障增长过程的奇异值分量作为故障增长特征，建立滚动体、内环和外环故障以及不同故障严重程度下的样本模型，利用智能算法辨识故障类型并评估其严重程度。最后，使用凯斯西储大学公开的滚动轴承振动数据验证所提方法的有效性。实验结果证明，故障增长分析方法能从复杂的奇异值分量中筛选出有效跟踪故障增长过程的特征，对提高损伤评估的准确度具有重要意义。

关键词：滚动轴承；损伤评估；经验模态分解；奇异值分量 中图分类号：TP277 doi:10.3969/j.issn.1001-3695.2017.11.0778

# Fault growth feature extraction and damage assessment for rolling bearing based on improved EMD

Chang Jingl,Wen Xiang²

(1.Sichan VocationalColegeofFinance&Economics,Chengdu610o1,China;2.SichuanInstituteofComputerSciences, Chengdu 610041, China)

Abstract:Traditionaldamageasessmentmethods forrolingbearings didn'tconsidersensitivityandstabilityoffault features to track fault growth proces,itresulted inlowprecisionandaccuracy.This paper proposedanewfeature extractionanddamage assessment method for rolling bearings based on improved empirical mode decomposition (EMD)and singularity value decomposition (SVD).Forthediferent damage severityofeach fault,itdecomposed original vibration signals intoafinite numberofintrinsic mode functions(IMF),andcalculatedtheirsingularvalue sequences,thus builtSVDcomponentsrelated to fault growth trends.Through analyzing thesensitivityand stabilityforfault growthtrends described bySVDcomponents,the optimal SVD sequences which could track fault growth process were selected as faultyeigenvectors offault type recognition and damage asessment.Finally,itverifiedtheeffectiveness ofproposed methods byusing theopen vibration dataofroling bearing providedby case western reserveuniversity.The results shows that the fault growth features can be selected from complex SVDcomponents bycomparing theirabilitiesof monitoring and tracking fault growth process,and theproposed approachcan provide abetter strategy for fault feature extraction of rollng bearings inorder to improve damage assessment precision and accuracy.

Key words: rolling bearing; damage assessment; empirical mode decomposition;singularity value decomposition

# 0 引言

滚动轴承是旋转机械中使用最广泛，也是最容易受到损伤的部件之一，其损伤程度直接关系到部件的使用性能和运行效率。因此，实时监控跟踪滚动轴承故障增长趋势并有效评估其损伤程度，不仅可以最大程度的发挥其工作性能，同时对机械的安全运转具有重要意义[1,2]。

滚动轴承故障信号具有非线性、非平稳调制的特征。传统的傅里叶变换和小波分析的基函数是固定的，难以解调并准确表示故障信号的实际波形和频率分布[2]。经验模态分解（empiricalmodedecomposition,EMD）是一种新的信号处理方法，通过有效地把握信号的局部特征，将信号细分为若干固有模态函数（intrinsic mode function,IMF）之和，在不同选择基函数的基础上可以根据信号自身的特点分解出能够突出数据局部特征的各个IMF分量，非常适合机械系统中的非线性、非平稳信号[3]。国内外学者将EMD 方法广泛应用于机械故障诊断领域。张超等人[4]提出了将 EMD 和谱峭度相结合的滚动轴承故障诊断方法。窦东阳等人[5]采用EMD与Lempel-Ziv 指标对内外圈损伤程度进行研究。夏平等人[提出了一种基于希尔伯特振动分解和Lempel-Ziv复杂性测度的滚动轴承内外圈损伤评估方法。Xiong等人[7使用EMD与峭度结合的方法滤除趋势和噪声成分，指导评估承受不同负载下滚动轴承的故障类型和损伤程度。Dbala等人[8]使用EMD方法将原始信号的IMF分量分解为三个组合模式函数，得到三部分的信号噪声部分、信号部分和趋势部分，进而提取出与故障相关的特征。Guo 等人[9]提出了基于多目标优化的改进EMD分析方法提取滚动轴承外环和内环故障特征。

然而以上机械部件损伤评估方法未考虑滚动轴承整个全寿命运行周期内故障特征的变化趋势，导致故障诊断和损伤评估的精度和准确度不高。其主要存在如下原因：第一，不同损伤程度下的数据特征区别小、间距近，很难有效评估部件的损伤程度，尤其在部件损伤的早期阶段，正常状态和早期损伤状态的数据特征关系模糊，导致损伤评估准确度低；第二，在整个部件损伤过程中，随着部件损伤程度的增长，数据的特征的总体趋势呈现波动、随机变化，采集的原始数据信息不能有效刻画整个损伤增长过程，导致在整个损伤过程中的评估精度低；第三，将大量与损伤增长信息无关的无效成份作为评估算法的输入，导致了评估时间长、效率低。

因此，本文从滚动轴承运行的全寿命趋势分析出发，提出了一种基于经验模态和奇异值分解的滚动轴承故障增长特征提取和损伤程度评估方法，使用EMD将不同故障严重程度的振动信号分解为各个奇异值分量（singularityvalue decomposition,SVD)，建立不同SVD分量描述的故障增长趋势，分析各级分量对故障增长过程的稳定性和敏感性，选择能有效感知故障增长过程的分量作为故障类型训练样本和损伤程度训练样本，以此为基础，使用智能算法辨识滚动轴承故障类型并评估其严重程度，使用美国凯斯西储大学公开的滚动轴承振动数据验证本文所提方法的有效性。

# 1 故障增长趋势分析

# 1.1故障增长特性

在机械系统的运行阶段，若不考虑维修措施，机械部件从正常状态到功能失效状态是一个损伤程度不断增长且不可逆转的过程。由于机械系统复杂的功能结构特点，通过传感器或检测设备采集的原始数据极易受到振动噪声干扰、信号传递耦合等因素的影响。为了有效评估机械部件的损伤程度，采集的原始数据需要包含丰富的损伤增长信息，这些信息涉及两方面：一方面，不同损伤程度下采集的原始数据的特征之间具有显著的距离，以确保更敏感、准确的评估不同损伤状态下机械部件的损伤程度，提高损伤评估的准确度；另一方面，随着机械部件损伤程度不断增长变化，原始数据的特征也呈现单调变化，例如随着损伤程度的增加，特征单调递增或者单调递减，以确保特征能有效刻画机械部件整个损伤增长过程，提高损伤评估的精度[10]。

![](images/b89c5b6dead83506c5a2f31dce4a2106eb004a7767db1568bff06d92adb10b81.jpg)  
图1故障增长趋势曲线

典型机械部件的故障增长趋势如图1所示。从滚动轴承的正常态经历退化态到严重损伤态，故障增长曲线经历了各不相同的斜率变化，从一个短期斜率较大到一个长时的斜率平缓到最终的故障态时的一个明显较大的斜率值，整条曲线近似单调，明显区别了滚动轴承不同状态下的曲线斜率变化。对于同一个滚动轴承相同全寿命实验里，真实的损伤演化是固定的。然而，由于外部噪声、振动耦合等多种原因的影响，故障的特征往往很难准确地表征故障的损伤程度，即使针对相同历程的全寿命数据，采用不同的故障特征提取方法，描述的故障增长趋势也有很大不同。因此，为了有效监控跟踪滚动轴承的故障增长过程，为损伤评估提供合理的数据，需要采用能敏感和稳定跟踪滚动轴承损伤过程的故障增长特征[11,12]。

# 1.2特征对障增长过程的稳定度和敏感度

定义1特征对故障增长过程 $\phi _ { i }$ 的稳定度 $\boldsymbol { \tau }$ 为

$$
\tau _ { i } = \frac { \displaystyle \sum _ { k _ { 1 } = 1 } ^ { N - 1 } \sum _ { k _ { 2 } = k _ { 1 } + 1 } ^ { N } \mathrm { s i g n } ( \Phi _ { i } ( k _ { 1 } ) - \Phi _ { i } ( k _ { 2 } ) ) } { N ( N - 1 ) / 2 }
$$

其中： $\phi _ { i } ( k _ { 1 } )$ 及 $\phi _ { i } ( k _ { 2 } )$ 分别为第 $\mathbf { \chi } _ { i }$ 个故障增长特征描述的故障增长曲线 $\phi _ { i }$ 的第 $k _ { 1 }$ 、 $k _ { 2 }$ 个观测点； $N$ 为故障增长曲线 $\phi _ { i }$ 所有观测点的总数； $\mathrm { s i g n } ( x )$ 为符号函数，表示当自变量 $x { > } 0$ 时，函数值为1；当自变量 $\scriptstyle x = 0$ 时，函数值为0；当自变量 $x { < } 0$ 时，函数值为1。

定义2特征对故障增长过程 $\phi _ { i }$ 的灵敏度 $\beta _ { i }$ 为

$$
\beta _ { i } = \mathrm { m e d i a n } \left( { \frac { \Phi _ { i } ( k _ { 2 } ) - \Phi _ { i } ( k _ { 1 } ) } { \Phi _ { i } ( 1 ) } } \right)
$$

其中： $\varPhi _ { i } ( 1 )$ 表示正常状态时的第 $\mathbf { \chi } _ { i }$ 个特征的输出值； $\phi _ { i } ( k _ { 1 } )$ 及$\phi _ { i } ( k _ { 2 } )$ 分别为第 $i$ 个特征描述的故障增长过程 $\phi _ { i }$ 的第 $k _ { 1 } , k _ { 2 }$ 个观测点；median为中值函数，返回给定数值的中值。

定义3特征对故障增长过程 $\phi _ { i }$ 的跟踪能力 $\eta _ { i }$ 为

$$
\eta _ { i } = ( 1 + e ^ { - 1 0 ( \tau _ { i } - 0 . 5 ) } ) ^ { - 1 } \times ( 1 + e ^ { - 1 0 ( \beta _ { i } - 0 . 5 ) } ) ^ { - 1 }
$$

其中： $\beta i$ 为特征对故障增长过程 $\varPhi _ { i }$ 的灵敏度； $\boldsymbol { \tau } _ { i }$ 为特征对故障增长过程 $\phi _ { i }$ 的稳定度。

# 1.3故障增长特征选择

EMD方法是将非平稳信号中不同尺度的波动或趋势逐渐分解出来，生成若干个IMF分量。具体的分解过程如下[13];

a)确定原始信号 $o ( t )$ 的所有局部极值点，通过三次样条函数求取其上包络 $x _ { 1 } ( t )$ 和下包络 $x _ { 2 } ( t )$ 的局部均值。

$$
m ( t ) = \frac { 1 } { 2 } \big [ x _ { 1 } ( t ) + x _ { 2 } ( t ) \big ]
$$

b)令 $h ( t ) = o ( t ) - m ( t )$ ，若 $h ( t )$ 不满足IMF 条件，则视其为新的 $o ( t )$ 。重复 $k$ 次。

$$
h _ { 1 k } \left( t \right) = h _ { 1 ( k - 1 ) } \left( t \right) - m _ { 1 k } \left( t \right)
$$

采用标准差 $S _ { D }$ 来作为筛选过程停止的准则。

$$
S _ { D } = \sum _ { t = 0 } ^ { T } \left[ \frac { h _ { 1 ( k - 1 ) } ( t ) - h _ { 1 k } ( t ) } { h _ { 1 ( k - 1 ) } ( t ) } \right] ^ { 2 }
$$

c)得到 $o ( t )$ 的第1个IMF分量 $C _ { 1 } = h _ { 1 k } ( t )$ 及分离后的余项$\begin{array} { r } { r _ { 1 } ( t ) = o ( t ) - C _ { 1 } } \end{array}$ 。

d)将 $r _ { 1 } ( t )$ 进行同样的筛选过程，依次得到后续的IMF分量$C _ { 2 }$ ， $C _ { 3 }$ ，，直到 $r _ { i } ( t )$ 基本呈单调趋势或 $\left| r _ { i } ( t ) \right|$ 很小时终止，则原信号 $o ( t )$ 重构为

$$
o ( t ) = \sum _ { i = 1 } ^ { n } C _ { i } ( t ) + r _ { n } ( t )
$$

其中： $r _ { n } ( t )$ 代表信号的平均趋势； $\mathbf { C } _ { i } ( t )$ 包含了信号 $x ( t )$ 从高到低不同频率段的成分。

根据奇异值理论，任何 $p { \times } q$ 阶矩阵A的奇异值分解可表示为

$$
\boldsymbol { A } = \boldsymbol { U } \cdot \boldsymbol { \Lambda } \cdot \boldsymbol { V } ^ { T }
$$

其中： $U$ 和 $V$ 分别为 $p { \times } q$ 阶和 $q { \times } q$ 阶正交矩阵；$\Lambda = d i a g \left( \lambda _ { 1 } , \lambda _ { 2 } , . . . , \lambda _ { k } \right)$ 是对角矩阵， $k = \operatorname* { m i n } ( p , q )$ ，为矩阵A 的奇异值并按降序排列。矩阵的奇异值是矩阵的固有特征，具有好的稳定性，采用 SVD可对高维的IMF 分量信息进行压缩[14]。

对滚动轴承的各个部件滚动体、外环、内环而言，从正常状态到功能失效状态往往会经历一个故障程度逐渐加剧的过程。对于滚动轴承不同的故障类型和不同的故障严重程度对应的频率段有较大区别，不同类型的信号经EMD和SVD分解所得到的分量包含的故障增长信息不同，并非每个SVD分量都对损伤评估有利。由于插值误差、边界效应及过分解等原因，信号经分解过程中会产生噪声分量和虚假分量，所以需要从奇异值分解特征向量中选择出能敏感和稳定感知故障增长过程的特征。

# 2 滚动轴承损伤评估流程

滚动轴承的损伤评估流程如图2所示，包括模型训练阶段和损伤评估两个阶段。

![](images/9218a03ddc8190d695dc22bfe4224c007b9541544a0460628c861f9e01228471.jpg)  
图2滚动轴承损伤评估流程

a)采集不同故障严重等级下滚动体故障、内环故障以及外环故障下滚动轴承的原始振动数据。

b)使用EMD-SVD方法得到提取不同故障程度下振动信号的奇异值特征向量 $E _ { 0 } ,$

$$
\pmb { { E } } _ { 0 } = \left[ \begin{array} { c c c c } { \pmb { e } _ { 1 1 } } & { \pmb { e } _ { 1 2 } } & { \cdots } & { \pmb { e } _ { 1 N } } \\ { \pmb { e } _ { 2 1 } } & { \pmb { e } _ { 2 2 } } & { \cdots } & { \pmb { e } _ { 2 N } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \pmb { e } _ { M 1 } } & { \pmb { e } _ { M 2 } } & { \cdots } & { \pmb { e } _ { M N } } \end{array} \right]
$$

其中： $\scriptstyle { E _ { 0 } }$ 每行对应相同故障状态下分解的奇异值特征向量； $N$ 为奇异值特征向量分量数； $E$ 每列表示不同故障程度下EMD-SVD同一分量值； $M$ 为故障演化周期中离散的故障状态数。

c)针对 ${ { E } _ { 0 } }$ 中的每一列分量，采用三次非线性多项式拟合故障增长趋势，建立各个SVD分量描述的故障增长趋势曲线，使用式 $( 1 ) \sim ( 3 )$ 计算各 SVD分量对故障增长过程的灵敏度、稳定度和跟踪能力，选择对故障跟踪能力最大的SVD分量作为SVM模型训练样本，故障增长过程的故障增长特征 $E ^ { * }$ 。

d)使用支持向量机（supportvectormachine,SVM)、隐马尔可夫模型（hiddenMarkovmodel,HMM）、神经网络（ANN）等方法训练滚动轴承正常状态、滚动体故障、内环故障和外环故障四种状态的模型fo、fi、 $f _ { 2 }$ 和 $f _ { 3 }$ ，以当前数据的故障增长特征$E ^ { * }$ 为输入，辨识当前状态。

e)按照故障严重等级将滚动轴承分为正常、轻度损伤、中度损伤、重度损伤和失效状态，训练不同故障严重程度下的模型 $d _ { 0 }$ 、d1、 $d _ { 2 }$ 和 $d _ { 3 }$ ，根据当前故障类型，评估当前损伤状态。

# 3 案例研究

为了验证该方法在滚动轴承损伤评估的有效性与实用性，本研究采用来自美国CaseWesternReserveUniversity 电气工程实验室实验装置和实验数据[15]。实验装置包括一个2hp 的电动机 $( 1 \mathrm { h p } { = } 7 4 6 \mathrm { w }$ )、扭矩传感器、测力计及电气控制装置。滚动轴承故障测试台如图3所示。

![](images/87be413e00e739628a33ac17d93797f0ecc7fc84df59b655cc63503f68a151cd.jpg)  
图3滚动轴承故障测试台

![](images/293892fe1fc08755e37511f1c5d62e100a569b744f6141a3b9960434d8b40fef.jpg)  
图4滚动轴承的四种故障类型

电动机的功率为746W，输入轴转速为 $1 7 7 2 \mathrm { r / m i n }$ ，实验轴承为6205-2RSJEMSKF型深沟球轴承，轴承的内径、外径分别为 $2 5 ~ \mathrm { m m }$ 、 $5 2 ~ \mathrm { m m }$ ，滚动体的直径、个数分别为 $7 . 9 3 8 ~ \mathrm { m m }$ 、9个，压力角为 $0 ^ { \circ }$ 。使用电火花加工技术设置四种状态（正常、内环故障、外环故障和滚动体故障）下的四种故障严重程度（单点损伤直径为0.007inch、0.014inch、0.021inch和 $0 . 0 2 8 \mathrm { i n c h } \cdot$ ）°在电动机驱动端、风扇端轴承座上方和基座上各放置一个加速度传感器采集16通道故障轴承的振动信号，采样频率为 $1 2 \mathrm { k H z }$ 。由于每个时刻采样点不相同，为了统一分析，提取其中的102

400个点。选择电动机驱动端的加速度计采集的信号进行实验验证，滚动轴承的四种故障类型如图4所示。其中，滚动体故障的四种严重程度波形图如图5所示。

![](images/920c4f4269a2d72bca1ae93d13f191b198ef8a5a146e2f52f2e32eea64ba2b59.jpg)  
图5四种滚动体故障损伤等级

采用EMD的方法将振动信号分解为一系列的IMF分量，由于前5个IMF分量的能量占信号总能量的 $9 5 \%$ ，所以选择分解到的前5个IMF分量作为奇异值分解对象。对5个IMF分量进行SVD分解，得到SVD分解特征向量 $\scriptstyle { E 0 }$ 。滚动轴承四种损伤状态（0.007inch、0.014 inch、0.021inch和0.028inch）振动信号的奇异值分解结果如表1所示。基于表1的数据，作出各个SVD分量描述的故障增长趋势。图6所示为滚动体故障第1个SVD分量描述的故障增长趋势。根据式 $( 1 ) \sim ( 3 )$ 计算各个SVD特征分量对故障增长的灵敏度、稳定度和跟踪能力，如表2所示。从表中对比分析可以得出，SVD的第1分量对滚动体故障的跟踪能力较大，SVD的1、2、3、4分量对内环故障的跟踪能力较大，SVD的1、3、4、5对外环故障的跟踪能力较大。因此，滚动体故障的损伤评估矩阵 $\boldsymbol { E } _ { \mathrm { B } } ^ { * } = [ \boldsymbol { e } _ { i 1 } ]$ ，内环故障 SVD 的损伤评估矩阵 $\boldsymbol { E } _ { \mathrm { I } } ^ { * } = [ e _ { i 1 } e _ { i 2 } e _ { i 3 } e _ { i 4 } ]$ ，外环故障SVD 的损伤评估矩阵 $\boldsymbol { E } _ { 0 } ^ { * } = [ e _ { i 1 } e _ { i 3 } e _ { i 4 } e _ { i 5 } ]$ 。

![](images/0915fa0bf149441f46a4fdc45613562fcabdff3d284b738f1dc3c35040e3afba.jpg)  
图6滚动体故障第一个SVD分量描述的损伤趋势

选择正常、滚动体故障、外环故障与内环故障四种状态各20 个样本训练 SVM模型fo、fi、f和f，对滚动体故障、外环故障与内环故障四种损伤状态（0.007inch、0.014inch、0.021inch和0.028inch）各选择20组数据训练不同损伤程度的SVM模型。随机选择10个已知故障类型和损伤状态的数据样本作为测试样本。为了对比故障趋势分析前后提取的故障增长特征对损伤评估的效果，将故障趋势分析前的5个SVD分量 $E 0$ 作为特征向量的损伤评估结果与增长趋势分析后优选的SVD 分量 $E _ { 8 } ^ { * }$ 、 $\ v { E } _ { \mathrm { I } } ^ { \ast }$ 和 $E _ { \mathrm { o } } ^ { * }$ 作为特征向量的损伤结果进行对比，测试结果如表3所示。从表中可以看出，在故障增长趋势分析前，将前5个SVD分量作为故障特征向量进行 SVM样本训练和损伤评估，评估效果为：1号和2号测试样本（0.007inch的滚动体故障)错误的分为正常状态；4号测试样本（0.007inch内环故障）错误的评估为损伤度0.014inch；7号测试样本（0.014inch外环故障）错误的评估为0.014inch内环故障，评估的准确率为$60 \%$ 。结果表明，特征向量 $E _ { 0 }$ 中的5个SVD分量包含了故障类型和损伤程度的交叉频率成分，并非每个分量都包含了故障增长信息，因此直接采用Eo作为特征向量指导故障类型辨识和损伤评估导致准确率低，尤其体现在故障早期阶段。经过分析各个SVD分量描述的故障增长趋势后，对不同故障类型和损伤度选择对应的SVD分量作为故障特征后，损伤评估的准确率提高到了 $90 \%$ 。

表1滚动轴承不同损伤状态下振动信号的奇异值分解结果  

<html><body><table><tr><td>故障类型</td><td colspan="5">滚动体故障</td><td colspan="5">内环故障</td><td colspan="5">外环故障</td></tr><tr><td>故障程度</td><td>01</td><td>02</td><td>03</td><td>04</td><td>05</td><td>01</td><td>02</td><td>03</td><td>04</td><td>05</td><td>01</td><td>02</td><td>03</td><td>04</td><td>05</td></tr><tr><td>正常</td><td>3.9</td><td>3.2</td><td>2.8</td><td>2</td><td>1.6</td><td>3.9</td><td>3.2</td><td>2.8</td><td>2.0</td><td>1.6</td><td>3.9</td><td>3.2</td><td>2.8</td><td>2</td><td>1.6</td></tr><tr><td>0.007 inch</td><td>13.6</td><td>2.5</td><td>2.0</td><td>1.6</td><td>1.0</td><td>26.4</td><td>12.1</td><td>7.3</td><td>4.7</td><td>2.0</td><td>53.4</td><td>26.1</td><td>7.9</td><td>5.0</td><td>3.7</td></tr><tr><td>0.014 inch</td><td>14.0</td><td>3.8</td><td>2.9</td><td>2.3</td><td>1.7</td><td>15.4</td><td>3.6</td><td>2.6</td><td>2.5</td><td>1.6</td><td>9.3</td><td>2.7</td><td>2.1</td><td>1.8</td><td>1.3</td></tr><tr><td>0.021 inch</td><td>14.6</td><td>2.6</td><td>2.5</td><td>2.2</td><td>1.5</td><td>43.7</td><td>6.7</td><td>6.1</td><td>5.7</td><td>1.9</td><td>48.6</td><td>12.8</td><td>9.1</td><td>7.6</td><td>5.1</td></tr><tr><td>0.028 inch</td><td>210.3</td><td>18.8</td><td>8.7</td><td>6.2</td><td>3.5</td><td>65.3</td><td>38.6</td><td>32.5</td><td>11.4</td><td>4.4</td><td>80.3</td><td>50.1</td><td>42.8</td><td>20.6</td><td>10.0</td></tr></table></body></html>

表2奇异值分量对故障的跟踪能力  

<html><body><table><tr><td>故障类型</td><td colspan="3">滚动体故障fi</td><td colspan="3">内环故障f</td><td colspan="3">外环故障f</td></tr><tr><td>奇异值分量</td><td>Ti</td><td>βi</td><td>ni</td><td>Ti</td><td>βi</td><td>ni</td><td>T</td><td>βi</td><td>ni</td></tr><tr><td>01</td><td>1</td><td>2.70</td><td>0.99</td><td>0.9</td><td>6.64</td><td>0.98</td><td>0.67</td><td>5.79</td><td>0.8411</td></tr><tr><td>02</td><td>0.7</td><td>0.31</td><td>0.11</td><td>0.8</td><td>1.87</td><td>0.95</td><td>0.50</td><td>1.45</td><td>0.5000</td></tr><tr><td>03</td><td>0.7</td><td>0.26</td><td>0.07</td><td>0.8</td><td>1.58</td><td>0.95</td><td>0.67</td><td>1.15</td><td>0.8398</td></tr><tr><td>04</td><td>0.8</td><td>0.31</td><td>0.12</td><td>0.9</td><td>1.71</td><td>0.98</td><td>0.67</td><td>1.37</td><td>0.8410</td></tr><tr><td>05</td><td>0.7</td><td>0.30</td><td>0.10</td><td>0.9</td><td>0.15</td><td>0.03</td><td>0.67</td><td>1.05</td><td>0.8378</td></tr></table></body></html>

表3滚动轴承损伤程度评估结果  

<html><body><table><tr><td rowspan="2">测试 序号</td><td rowspan="2">真实损伤状态</td><td colspan="3">Eo评估结果</td><td colspan="3">E*评估结果</td></tr><tr><td>故障类型</td><td>损伤程度</td><td>准确率</td><td>故障类型</td><td>损伤程度</td><td>准确率</td></tr><tr><td>1</td><td>0.007inch 滚动体故障</td><td>正常状态</td><td>0</td><td></td><td>正常状态</td><td>0</td><td rowspan="6">90%</td></tr><tr><td>2</td><td>0.007 inch 滚动体故障</td><td>正常状态</td><td>0</td><td></td><td>滚动体故障</td><td>0.007 inch</td></tr><tr><td>3</td><td>0.007 inch 滚动体故障</td><td>滚动体故障</td><td>0.007 inch</td><td></td><td>滚动体故障</td><td>0.007 inch</td></tr><tr><td>4</td><td>0.007 inch内环故障</td><td>内环故障</td><td>0.014 inch</td><td></td><td>内环故障</td><td>0.007 inch</td></tr><tr><td>5</td><td>0.014 inch 内环故障</td><td>内环故障</td><td>0.014 inch</td><td>60%</td><td>内环故障</td><td>0.014 inch</td></tr><tr><td>6</td><td>0.014inch内环故障</td><td>内环故障</td><td>0.014 inch</td><td></td><td>内环故障</td><td>0.014 inch</td></tr><tr><td>7</td><td>0.014 inch 外环故障</td><td>外环故障</td><td>0.021 inch</td><td></td><td>外环故障</td><td>0.014 inch</td></tr><tr><td>8</td><td>0.014 inch 外环故障</td><td>外环故障</td><td>0.021 inch</td><td></td><td>外环故障</td><td>0.014 inch</td></tr><tr><td>9</td><td>0.021 inch 外环故障</td><td>外环故障</td><td>0.021 inch</td><td></td><td>外环故障</td><td>0.021 inch</td></tr><tr><td>10</td><td>0.028 inch 外环故障</td><td>外环故障</td><td>0.028 inch</td><td></td><td>外环故障</td><td>0.028 inch</td></tr></table></body></html>

表4SVM和HMM的损伤评估对比  

<html><body><table><tr><td>测试样本数</td><td>10</td><td>20</td><td>30</td><td>40</td><td>50</td></tr><tr><td>SVM 准确率</td><td>90</td><td>90</td><td>93</td><td>92.5</td><td>95</td></tr><tr><td>HMM /%</td><td>80</td><td>85</td><td>90</td><td>90</td><td>95</td></tr><tr><td>ANN</td><td>85</td><td>85</td><td>90</td><td>95</td><td>95</td></tr></table></body></html>

另外，为了证明本文方法的鲁棒性，以优选后的SVD分量$E _ { \mathsf { { B } } } ^ { * }$ 、 $\boldsymbol { E } _ { \mathrm { I } } ^ { \ast }$ 和 $\boldsymbol { E } _ { 0 } ^ { * }$ 作为故障增长特征向量，采用 SVM、HMM 和ANN对10、20、30、40和50个测试样本进行故障类型辨识和损伤评估，结果如表4所示。从表中可以看出，当训练样本较少时，SVM评估的准确率高于HMM和ANN，这说明SVM更适合小样本识别；随着训练样本的增多，三种方法的损伤评估准确率逐渐提高。因此，本文提出的损伤评估方法具有很好的泛化能力。

# 4 结束语

滚动轴承振动信号的SVD分量包含了不同故障类型、不同损伤程度的故障信息，甚至还有可能发生故障信息交叠的现象，这在故障早期阶段尤为突出，这增加了故障诊断和损伤评估的难度。采用故障增长趋势分析的方法可以针对不同故障类型和不同损伤程度故障的特征选择具有更好的敏感度和稳定跟踪故障增长过程的SVD分量，SVD的第1个分量1对滚动体故障的跟踪能力较大，第1、2、3、4分量对内环故障的跟踪能力较大，第1、3、4、5分量对外环故障的跟踪能力较大。根据SVD分量对不同故障增长趋势的跟踪能力大小，建立故障特征矩阵作为损伤评估的模型训练样本和测试样本，可以减少无效和冗余SVD分量对滚动轴承损伤评估的影响，能显著提高故障类型辨识和损伤评估的效率和准确率。

# 参考文献：

[1]许凡，方彦军，张荣，等．基于LMD基本尺度熵的AP聚类滚动轴承故 障诊断[J]，计算机应用研究,2017,34(6):1732-1736.   
[2]李玉庆，王日新，徐敏强，等.针对滚动体损伤的滚动轴承损伤严重程 度评估方法 [J].振动与冲击,2013,32(18):169-173.   
[3]郭艳平，颜文俊.基于EMD和优化K均值聚奕昇法诊断滚动轴承故 [J]．计算机应用研究,2012,29(7):2555-2557.   
[4]张超，陈建军．基于EMD降噪和谱峭度的轴承故障诊断方法[J].机械 科学与技术,2015,34(2):252-256.   
[5]窦东阳，赵英凯．基于EMD和Lempel-Ziv 指标的滚动轴承损伤程度识 别研究[J].振动与冲击,2010,29(3):5-8.   
[6]夏平，徐华，马再超，等．采用改进HVD与Lempel-Ziv 复杂性测度的 滚动轴承早期损伤程度评估方法 [J]．西安交通大学学报,2017,51(6): 8-13.   
[7]Xiong Qing,Xu Yanhai,Peng Yiqiang,et al. Low-speed rolling bearing fault diagnosis based on EMD denoising and parameter estimate with alpha stable distribution [J]. Journal ofMechanical science and technology,2017,31 (4): 1587-1601.   
[8]Dybala J，Radoslaw Z.Rolling bearing diagnosing method based on empirical mode decomposition of machine vibration signal [J].Applied Acoustics,2014,77(3): 195-203.   
[9]Guo Tai, Deng Zhongmin.An improved EMD method based on the multiobjective optimization and its application to fault feature extraction of rolling bearing [J].Applied Acoustics,2017,127: 46-62.   
[10]谭晓栋．一种基于故障增长趋势相关度分析的传感器优化部署方法： 中国,201710482168.4[P].2017-06-22.   
[11]罗建禄，谭晓栋，刘颖，等．一种基于故障演化分析的故障预测特征选 择方法：中国,201410531775.1[P].2014-10-10.   
[12]傅鹏程，王昌明，段俊斌，等．基于故障演化分析的齿轮故障预测特征 选择[J].深圳大学学报,2015,32(4):434-440.   
[13] Han Te,Jiang Dongxiang,Wang Nanfei. The fault feature extraction of rolling bearing based on EMD and diference spectrum of singular value [J]. Shock and Vibration,2016,2016 (13): 1-14.   
[14] Tian Ye,Ma Jian,Lu Chen,etal,Rolling bearing fault diagnosisunder Variable conditions using LMD-SVD and extreme learning machie [J]. Mechanism and Machine Theory,2015,90(1): 175-186.   
[15] The case western reserve university bearing data center [EB/OL]. (2012-11- 07）[2013-12-01].http://csegroups.case.edu/bearingdatacenter/pages/

download-data-file.