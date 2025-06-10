# 基于线性与非线性特征融合的J波自动识别

毋凡铭，李灯熬，赵菊敏(太原理工大学 信息与计算机学院，山西 晋中 030600)

摘要：临床研究表明，J波可作为一些心脏疾病的高危预警指标。针对当前医生诊断J波仅通过经验进行识别，易造成误诊的问题，从信号处理角度，提出了一种J波自动识别方法。该方法通过提取心电数据极点对称模态分解后的能量特征与高阶累计量特征，融合线性与非线性特征，并采用主成分分析进行特征降维，最后利用人工蜂群算法优化后的支持向量机进行分类，实现J波的自动识别。对比实验结果，提出的方法平均准确率为 $9 7 . 3 \%$ ，可有效地识别J波。

关键词：J波；极点对称模态分解；高阶累计量；人工蜂群算法；支持向量机 中图分类号：TP302.1 doi: 10.3969/j.issn.1001-3695.2018.03.0164

# Automatic recognition of J wave based on combination of linear and nonlinear features

Wu Fanming, Li Dengao†, Zhao Jumin (CollegeofInformation&Computer,Taiyuan UniversityofTechnology,Jinzhong O3o6o,China)

Abstract: Clinical studies have show thatJwavecanbeused as a highrisk early warning index ofsome heart diseases.In viewoftheshortcomingsofJwave diagnosisonlybytheclinicians'experiences,whichcaneasilyleadtomisdiagnosis.From the perspectiveofsignal procesing,this paper proposedaJwave automatic identification method.This method extracted the energy features of electrocardiogramdata after the extreme-point symmetric mode decompositionand higher order statistics, combined linearandnonlinearfeatures,andadopted the principal componentanalysis toreduce thedimensionof thefeatures. Finally,itusedsupportvectormachineoptimizedbyartificialbe colonyalgorithmtorealizeautomaticidentificationofJwave. The experimental results show that the average accuracy rate of identifying J wave is $9 7 . 3 \%$ ,which can effectively identify the J wave.

Key words:Jwave; extreme-point symmetric mode decomposition;higher-order statistics;artificial beecolony algorithm; support vector machine

# 0 引言

J点是心电信号上QRS波与ST段的结合点，表示心脏除极的结束、复极的开始[I]。若J点从基线移位，呈尖峰状、驼峰状或顿挫状，且振幅 $\mathrm { \stackrel { . } { > } = } 0 . 1 \mathrm { m v }$ 、时限 $> = 2 0 \mathrm { m s }$ ，该偏移波即为J波[2.3]。

相关研究表明，当J波幅度超过 $0 . 1 \mathrm { m v }$ 且伴有 ST 段变化时，极易引发致命性心肌梗塞、恶性心律失常，甚至心脏性猝死[4.5]。当前临床上医生通过观察心电图上J波的大小、时限并结合患者的临床表现进行鉴别诊断，依据主观经验来进行J波识别，容易造成误诊和漏诊，因此实现J波的自动识别，可及时对J波进行诊断，有效降低J波的致死率。

为了实现J波的自动识别，本文从信号处理角度对J波研究，通过提取心电数据的线性特征和非线性特征，并通过人工蜂群算法（artificialbeecolony，ABC）改进后的支持向量机(supportvectormachine，SVM)对心电信号进行分类，从而实现J波的自动识别。医生依据J波自动识别的结果，并结合患者的临床状况，提出最佳诊断和治疗方案。

# 1 数据准备及预处理

本文从山西大医院心电数据库中获得了大量含J波的纸质心电数据。使用高分辨率扫描仪将纸质心电数据转换为数字图片，并采用图像处理技术，对转换后的数字图片进行Hough变换、K-means聚类、曲线拟合等，实现纸质心电数据的数字化，具体步骤如下：

a）倾斜校正。采用霍夫（Hough）变换检测心电图纸中背景网格直线，通过计算斜率得到倾斜角度，进而进行旋转校正。b)像素聚类。同为心电数据或同为背景网格像素具有相似性，本位采用K-means聚类算法，分离黑色的心电数据和红色的背景网格。

c）移除干扰。由于纸质心电数据存在导联标志、基准电压等干扰像素点，所以从二值图像中选择联通面积较小的像素点进行移除。d)曲线拟合。读取二值图像中心电数据的各像素点位置坐标，并对缺失的像素点进行插值。通过拟合像素点，获得数字化后的完整心电数据。

以 $2 5 0 ~ \mathrm { H z }$ 的采样率从数字化后的心电数据中选取40个正常心电数据和40个含J波心电数据，每个记录持续 $2 ~ \mathrm { m i n }$ ，并根据原记录分别标记为类型N和类型 $\mathbf { J } _ { \circ }$

由于外界因素干扰，心电数据中通常包含多种噪声[6]。由于心电数据的频谱主要集中在 $1 ~ \mathrm { H z } { \sim } 4 0 ~ \mathrm { H z }$ 间，本文通过截止频率为 $1 ~ \mathrm { H z }$ 和 $4 0 ~ \mathrm { H z }$ 的二阶巴特沃斯滤波器去除心电数据中的基线漂移和工频干扰。

# 2 J波自动识别

本文通过对预处理后的心电数据提取线性特征与非线性特征，采用极点对称模态分解（extreme-point symmetric modedecomposition，ESMD）提取线性特征，融合心电数据的非线性特征高阶累计量（higher-order statistics，HOS）并对融合特征进行降维处理，将采用主成分分析（principal component analysis,PCA）降维后的特征输入到ABC算法优化后的SVM中进行识别。该算法的整体框图如图1所示。

![](images/c28ff8d43a7540fdaf068c56a63e1adb94ff07f732e5cd9ee76e38ad393947dc.jpg)  
图1算法框图

# 2.1线性特征

本文采用ESMD来提取心电数据的线性特征，提取分解后的本征模态函数(intrinsic mode function,IMF)的能量特征[7,8]。目前对心电数据进行时频分析的方法主要有小波变换和经验模态分解（empirical modedecomposition,EMD）两种方法。小波变换在心电数据识别分类有很好的分析效果，但小波变换是非自适应的，其性能的好坏严重依赖于小波函数的的选择，一旦初始选定小波函数，全局信号必须都使用相同的小波基，很难达到最佳分析效果；EMD是一种自适应的信号处理方法，其根据信号自身的波动规律将信号分解为从低频到高频不同时间尺度分量，更加适用于心电信号的研究分析。

ESMD在EMD的基础上，通过改变外包络线的插值法，用内部极点对称插值法替代EMD中的三阶样条插值，并且给分解的余量赋予了意义，通过最小二乘思想优化余量，使其称为整个信号的“自适应全局均线”，从而确定分解的最佳筛选次数，有效地解决了EMD中的模态混叠问题[9]。

ESMD具体分解过程如下：

a)找出原始心电数据 $x ( t )$ 中的所有极值点，包括极大值点与极小值点，记做 $P _ { i } ( 1 \leq i \leq n )$ □

b)用线段连接所有临近的 $P _ { i }$ ，并将连接的线段的中点标记为 $T _ { i } ( 1 \leq i \leq n - 1 )$ ，同时在左右两端添补边界中点 $T _ { \phantom { } _ { 0 } }$ 和 $T _ { n }$ 。

c)通过 $n { + } 1$ 个中点来构建 $s$ 条内插曲线 $L _ { 1 } , . . . , L _ { s } ( s \geq 1 )$ ，计算其平均值 $\boldsymbol { L } ^ { * } = ( L _ { 1 } + \cdots + L _ { s } ) / s$ 。

d）对 $x ( t ) - L ^ { * }$ 序列重复上述三个步骤，直至 $\left. L ^ { \ast } \right. \leq \varepsilon$ （ε是允许误差）或者筛选次数达到预设的最大值 $K$ ，得到第一个IMF分量 $c _ { 1 }$ 。

e）对剩余序列 $x ( t ) - c _ { 1 }$ 重复上述四个步骤，直到剩余序列$\boldsymbol { r }$ 为单一信号或不再大于预先给定的极值点，便可分别得到IMF分量C,C..。

f)在限定区间 $\left[ K _ { \operatorname* { m i n } } , K _ { \operatorname* { m a x } } \right]$ 内改变 $K$ 值，重复上述五个步骤。然后计算序列 $x ( t ) - r$ 的方差 $\sigma ^ { 2 }$ ，并对 $\sigma / \sigma _ { 0 }$ 和 $K$ 进行绘图（ $\sigma _ { 0 }$ 是 $x ( t )$ 的标准差），在图中找出 $\sigma / \sigma _ { 0 }$ 最小值对应的 $K _ { 0 }$ ，以 $K _ { 0 }$ 作为限制条件再次重复上述五个步骤，最后分解至只剩一定数量极点的剩余项 $\boldsymbol { r }$ ，就是原始信号 $x ( t )$ 的自适应全局均线，亦即趋势项。

经过分解，原始信号 $x ( t )$ 可表示 $x ( t ) = \sum _ { i = 1 } ^ { n } c _ { i } + r$ ，即利用ESMD将时间序列 $x ( t )$ 分解成一系列IMF和一个趋势项 $\boldsymbol { r }$ 。

![](images/54870d027bea523cc35cc71a2e9335279b3e52c719c056c7ab9ec5028d034030.jpg)  
图2心电数据对应的方差比率随最大筛选次数的变化

ESMD分解的一大改进是最大筛选次数由自适应全局均线决定。分解前需设定剩余极点个数 $\boldsymbol { M } _ { \ u { r } }$ ，这决定了趋势项 $r$ 的可能弯曲次数，其形状能否反映数据变化趋势全赖此设定。为满足边界性插值要求，需使 $M _ { r } \geq 4$ 。 $\boldsymbol { M } _ { \ u { r } }$ 如果选择过大，会降低模态分辨率，本文 $M _ { r }$ 取 4个。通过对 $\sigma / \sigma _ { 0 }$ 和 $K$ 进行绘图为图2。在图中找出 $\sigma / \sigma _ { 0 }$ 最小值对应的 $K = 3 6$ ，则心电信号对应36次筛选的最佳分解结果在图3中显示，共分解为7个IMF 和1个趋势项 $r$ 。

![](images/f32567379b0434ed3fc4f898807d47cc050a90a6cadfed9f8777c58443f71923.jpg)  
图3心电数据在36次筛选下的ESMD分解结果

根据ECG的波形特点，观察图3可以看出每一个IMF所代表的意义：前两个分量 $c _ { 1 }$ ， $c _ { 2 }$ 主要代表了频率最高的 QRS 波的成分；从 $c _ { 3 }$ 开始有P波开始分解；从 $c _ { 4 }$ 开始加入T波成分；$c _ { 5 }$ 代表P，QRS，T波低频成分分量叠加； $\mathbf { \Sigma } _ { C _ { 6 } , C _ { 7 } }$ 代表更大时间尺度上的心脏生理调节节律。从图4中可以看出趋势项 $r$ ，即自适应全局均线，很好地反映了ECG信号的变化趋势。

![](images/c48225144d308f07ee5897d5d13e295d1a2aada45c0ed03793ba2fa96e987a79.jpg)  
图4心电数据的自适应全局均线

心电数据通过ESMD分解后得到一系列IMF 和一个趋势项$r$ ，计算IMF 和 $r$ 的能量，可以计算得到能量向量。计算过程如下[10]：

a）对心电数据进行ESMD分解，得到一系列IMF和一个趋势项 $r$ 。

b）计算IMF 分量和 $r$ 的能量 $E _ { i }$ 、 $E _ { r }$ 。

$$
E _ { i } = \sum _ { t _ { 0 } = 0 } ^ { t } \bigl | c _ { i } \bigl ( t _ { 0 } \bigr ) \bigr | ^ { 2 } , i = 1 , 2 , . . . , n
$$

$$
E _ { r } = { \sum _ { t _ { 0 } = 0 } ^ { t } } { \left| r { \left( t _ { 0 } \right) } \right| ^ { 2 } }
$$

c）得到心电数据的能量向量：

$$
V = \left[ E _ { 1 } , E _ { 2 } , { \cdots } , E _ { n } , E _ { r } \right]
$$

对向量 $V$ 做归一化处理，得到

$$
V ^ { \prime } { = } \big [ p _ { 1 } , p _ { 2 } , \cdots , p _ { n } , p _ { r } \big ]
$$

其中：

$$
E = ( \sum _ { i = 1 } ^ { n } E _ { i } ^ { 2 } + E _ { r } ^ { 2 } ) ^ { 1 / 2 } ,
$$

$$
p _ { i } = E _ { i } / E , i = 1 , 2 , . . . , n . ,
$$

$p _ { r } = E _ { r } / E$ ， $p _ { * }$ 表示IMF 和 $r$ 的能量在心电数据总能量中的比重。

能量向量 $V ^ { \prime }$ 的分量从 ${ p } _ { 1 }$ 到 ${ { p } _ { r } }$ 代表的频率逐渐降低，本文共提取以上8个线性特征。心电数据类型N和类型J的能量向量分布对比如图5所示。从图中可以看出心电数据类型N能量向量从高频到低频变化趋势呈降低趋势，能量主要集中在高频部分；心电数据类型J能量向量能量最高出现在P。

![](images/b5727b69342ad426ad5aaeb51dfa86fcf49caaf8d6b0b4726a13bb332b049734.jpg)  
图5类型N心电数据与类型J心电数据ESMD 能量向量图对比

# 2.2非线性特征

由于线性特征无法获取信号中的细微变化和不同参数间的非线性信息，所以本文提取心电数据的HOS特征来挖掘心电数据中的J波信息[1]。本文通过提取心电数据的三阶矩，即三阶累积量作为特征，计算公式如下：

$$
C _ { 3 } ^ { x } = m _ { 3 } ^ { x } ( i , j ) = E [ x ( n ) x ( n + i ) x ( n + j ) ]
$$

其中： $E [ \cdot ]$ 表示统计期望运算符； $i$ 和 $j$ 为时延参数。

图6所示为正常心电数据的三阶累积量及其等高线，图7所示为含J波心电数据的三阶累积量及其等高线。从图6和7中可对比HOS可对两种心电数据进行明显区分。本文通过提取两种心电数据的三阶累积量特征，得到40个特征向量作为非线性特征。

![](images/16157c9cce11bbe9d986ebe690b9e407bec15cb1e0afb108ec8a02a46818e50d.jpg)  
图6类型N心电数据的三阶累积量及其等高线

![](images/d12973ebf1d38df31336c950c3ba1abfc7da6baff34f6f148ae8259d88980e4b.jpg)  
图7含J波心电信号的三阶累积量及其等高线

# 2.3 PCA降维

为降低计算量，本文采用PCA来进行特征降维。其基本思想是将高维空间的初始特征经过变换矩阵，使其降到低维空间成为新的特征向量，减少特征维度，但仍能保留初始特征的主要信息[2]。

将心电数据通过ESMD分解后得到的IMF与 $r$ 的能量特征共8个线性特征，与心电数据的三阶累积量共计40个非线性特征进行融合，得到48个特征向量，采用PCA降维后，取前12个主成分作为特征训练测试分类器。

# 2.4 ABC-SVM

SVM对于小样本条件由很好的泛化能力，适用于本文J波心电数据的识别[13]。SVM 的目标是找到一个最优超平面，能够对类型N和类型J的心电数据有效分类，其表达式为

$$
y = \omega ^ { T } \Phi ( x ) + b
$$

其中： $\omega$ 为权向量； $b$ 为阈值。找最优超平面就是要对 $\omega$ 和 $b$ 进行求解，引进目标函数并加入惩罚项后为

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } J \big ( \omega , \xi \big ) = \frac { 1 } { 2 } \big \| \omega \big \| ^ { 2 } + c \displaystyle \sum _ { i = 1 } ^ { n } \xi _ { i } } \\ { \displaystyle s . t . ~ y ( \omega \cdot \Phi ( x _ { i } ) + b ) \geq 1 - \xi _ { i } } \\ { \xi \geq 0 , i = 1 , 2 , . . . , n } \end{array}
$$

其中： $\lambda _ { i }$ 为松弛因子； $C$ 为惩罚因子。引进Lagrange 函数，转换为凸二次规划寻优的对偶问题。

$$
\operatorname* { m a x } \sum _ { i = 1 } ^ { m } \alpha - \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { m } \alpha _ { i } \alpha _ { j } y _ { i } y _ { j } ( x _ { i } , x _ { j } ) ,
$$

$$
\mathrm { s . t . } \sum _ { j = 1 } ^ { m } \alpha _ { j } y _ { j } = 0 , 0 \leq \alpha _ { j } \leq C
$$

其中： $\alpha _ { i } > 0$ 为Lagrange 乘子。

对式（8）进行求解得到 $\alpha _ { i }$ ，那么 $\omega$ 的计算公式为

$$
\omega = \sum \alpha _ { i } y _ { i } \Phi ( x _ { i } ) \cdot \Phi ( x )
$$

最后，SVM分类函数为

$$
f ( x ) { = } \operatorname { s g n } ( \alpha _ { i } y _ { i } \Phi ( x _ { i } ) { \cdot } \Phi ( x ) { + } b )
$$

由于径向基核函数仅有核函数宽度 $\gamma$ 一个参数需要进行优化，所以选择其作为SVM的核类函数。径向基核函数表达式如下：

$$
K ( x \cdot x ^ { \prime } ) { = } \exp ( { - } \| x { - } x ^ { \prime } \| ^ { 2 } / \sigma ^ { 2 } )
$$

本文采用ABC算法优化与分类器性能相关的参数 $C$ 和 $\gamma$ ，建立基于 SVM 的J波自动识别模型。具体步骤为[14]：

a）确定人工蜂群的群体数量，同时确定侦查蜂所占比例。b）在参数取值范围内随机选择 $A$ 个（ $C$ ，）的组合，  
也就是确定该 $A$ 个组合即为蜜源，并使所有蜜蜂均成为侦查蜂。c)计算 $A$ 个蜜源的品质。若品质低，则侦查蜂不作变化继  
续搜索或作为跟随蜂去高品质蜜源采蜜；跟随蜂则依据蜜源品

质按照一定比例去蜜源进行采蜜。

d）当跟随蜂抵达蜜源，通过对其附近连续区域进行采蜜，从而确定最优点。e）所有的蜜蜂返回蜂巢，计算各蜜源的品质来重新分配各蜜源的采蜜蜂数量。f)重复上述a) $- \mathrm { e }$ )，最终确定最优蜜源点，即最优的( $C$ ，Y）。

# 3 结果与分析

# 3.1评价指标

本文通过灵敏度（sensitivity，Se）、特异性（specific，Sp）和准确率（Accuracy，Ac）来评价J波自动识别方法的性能。Se 表示准确识别心电数据类型J的比率，Sp表示准确识别心电数据类型N的比率，Ac表示准确识别心电数据类型J和类型N的比率。

# 3.2结果分析

本文的数据集包含80个心电数据，每个记录持续 $2 ~ \mathrm { m i n }$ 共约10400个心拍。通过五倍交叉验证法对本文提出的J波自动识别方法进行分析。将数据集平均分为5个互不相交的子集，取其中的4个子集作为训练集（8320个心拍）训练分类器，1个作为测试集（2080个心拍）测试分类器。每一次实验取其中的一个样本作为测试样本，计算其性能评价指标。这一过程重复5次，取5次的平均值来评估分类器的性能。分别对比ESMD $^ { 1 + } .$ ABC-SVM、HOS $^ +$ ABC-SVM、融合特征 $+ \mathrm { S V M }$ 和本文提出的方法，各识别方法中SVM参数（ $C$ ，7）如表1所示，平均性能结果如表2所示。

表1各种识别J波方法的SVM参数  

<html><body><table><tr><td>方法</td><td>C</td><td>Y</td></tr><tr><td>ESMD+ABC-SVM</td><td>268.09</td><td>23.25</td></tr><tr><td>HOS+ABC-SVM</td><td>172.43</td><td>17.02</td></tr><tr><td>融合特征+SVM</td><td>746.26</td><td>82.18</td></tr><tr><td>本文方法</td><td>98.85</td><td>9.73</td></tr></table></body></html>

表2 各种识别J波方法的平均性能  

<html><body><table><tr><td>方法</td><td>(%)</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>均值</td></tr><tr><td rowspan="3">ESMD+ABC- SVM</td><td>Se</td><td>93.6</td><td>92.3</td><td>93.3</td><td>92.4</td><td>91.8</td><td>92.7</td></tr><tr><td>Sp</td><td>90.1</td><td>89.6</td><td>90.9</td><td>89.4</td><td>90.7</td><td>90.1</td></tr><tr><td>Ac</td><td>94.4</td><td>95.2</td><td>93.1</td><td>93.8</td><td>92.5</td><td>93.8</td></tr><tr><td rowspan="3">HOS+ABC- SVM</td><td>Se</td><td>94.9</td><td>94.2</td><td>96.2</td><td>96.2</td><td>96.6</td><td>95.6</td></tr><tr><td>Sp</td><td>95.3</td><td>95.3</td><td>95.9</td><td>96.6</td><td>94.1</td><td>95.4</td></tr><tr><td>Ac</td><td>97.1</td><td>95.9</td><td>95.3</td><td>97.7</td><td>95.4</td><td>96.3</td></tr><tr><td rowspan="4">融合特征 +SVM</td><td>Se</td><td>95.0</td><td>95.3</td><td>93.3</td><td>94.6</td><td>94.1</td><td>94.5</td></tr><tr><td>Sp</td><td>94.5</td><td>94.5</td><td>93.6</td><td>92.5</td><td>92.9</td><td>93.6</td></tr><tr><td>Ac</td><td>95.5</td><td>94.2</td><td>96.5</td><td>94.1</td><td>95.5</td><td>95.2</td></tr><tr><td>Se</td><td>95.8</td><td>96.7</td><td>96.3</td><td>96.0</td><td>98.9</td><td>96.7</td></tr><tr><td>本文方法</td><td>Sp</td><td>97.5</td><td>96.7</td><td>97.1</td><td>97.9</td><td>95.0</td><td>96.8</td></tr><tr><td></td><td>Ac</td><td>98.2</td><td>97.7</td><td>96.5</td><td>96.6</td><td>97.6</td><td>97.3</td></tr></table></body></html>

识别方法ESMD $+$ ABC-SVM的5倍交叉验证Se、Sp和Ac平均值分别为 $9 2 . 7 \%$ 、 $9 0 . 1 \%$ 和 $9 3 . 8 \%$ ， $\mathrm { H O S + A B C - S V M }$ 比ESMD $^ { + }$ ABC-SVM的Se、Sp和Ac平均值分别提高 $2 . 9 \% . 5 . 3 \%$ 和 $2 . 5 \%$ ，将ESMD与HOS 融合，采用ABC-SVM 进行识别，Se、Sp和Ac平均值达到最高，分别为 $9 6 . 7 \%$ 、 $9 6 . 8 \%$ 、 $9 7 . 3 \%$ 。通过对比融合特征 $+ \mathrm { S V M }$ ，采用 ABC-SVM比 SVM 的 Se、Sp和 Ac平均值分别提高 $2 . 2 \%$ 、 $3 . 2 \%$ 和 $2 . 1 \%$ 。

本文还进一步对比了目前已有的其他两种J波检测方法。Clark 等人错误!未找到引用源。通过形态学和几何学特征来检测J波，进能够对两种类型的J波进行识别检测,存在一定的局限性。Wang等人错误:未找到引用源-提出一种利用 fPCA 和 Jscore 从12 导联心电图中自动检测J波的方法，但算法复杂度较高，且测试组数据的实验结果不理想。

相比于以上两种方法，本文从线性与非线性角度对心电数据提取特征，特征信息较为全面。比较不同方法对J波的识别效果，结果如表3所示。由表中数据可知，本文方法要优于另外两种方法，对J波的识别效果最好。

表3三种J波识别算法的性能比较/%   

<html><body><table><tr><td>文献</td><td>方法</td><td>Se</td><td>Sp</td><td>Ac</td></tr><tr><td>Clark et al. [15]</td><td>形态学+几何特 征</td><td>90.5</td><td>96.5</td><td>92.8</td></tr><tr><td>Wang et al. [16]</td><td>fPCA+J score</td><td>89</td><td>86</td><td>87.6</td></tr><tr><td>本文</td><td>融合特征+ABC- SVM</td><td>96.7</td><td>96.8</td><td>97.3</td></tr></table></body></html>

# 4 结束语

本文提出了一种J波自动识别技术，全面提取心电数据特征，通过融合极点对称模态分解后的能量特征与非线性的高阶累计量特征并进行PCA降维，输入到ABC算法优化后的SVM中进行识别。实验结果表明，该方法可以准确高效地识别出心电数据中的J波，为医生诊断心脏疾病提供辅助。

# 参考文献：

[1]Macfarlane P W, Clark E N,Heng J S.J wave patterns—morphology, prevalence and nomenclature [J].Journal of Electrocardiology,2013,46(6): 505-509.   
[2]AntzelevitchC，严干新,Ackerman MJ,etal.J波综合征专家上海共识： 概念与认知的更新[J].临床心电学杂志，2016,25(3):161-179. (Antzelevitch C,Yan Ganxin,Ackerman MJ,et al.Jwave syndrome expert Shanghai consensus: concept and cognitive updates [J]. Journal of Clinical Electrocardiology,2016,25 (3): 161-179.)   
[3]Antzelevitch C, Yan Ganxin,Ackerman MJ,et al. J-wave syndromes expert consensus conference report: emerging concepts and gaps in knowledge [J]. Journal of Arrhythmia,2016,32(5): 315-339.   
[4]林玥，周白丽.J波综合征研究进展[J]．医学综述,2016,22(16):3228- 3231.(Lin Yue,Zhou Baili. Research progress in J wave syndrome [J].

Medical Recapitulate,2016,22(16):3228-3231.)

[5]沈雁岩，张延勋.J波综合征及其临床意义研究进展[J]．医学综述, 2012,18 (8): 1208-1212.(Shen Yanyan, Zhang Yanxun.Research progress ofJ wave syndromes and its clinical significance [J].Medical Recapitulate, 2012,18 (8): 1208-1212.)   
[6]Wang Ze,Wan Feng,Wong Chiman,et al.Adaptive fourier decomposition based ECG denoising [J]. Computers in Biology and Medicine,2016,77: 195-205.   
[7]王金良，李宗军．可用于气候数据分析的 ESMD方法[J].Climate Change Research Letters,2014,3:1-5.(Wang Jinliang,Li Zongjun. The ESMD method for climate data analysis [J].Climate Change Research Letters,2014,3: 1-5.)   
[8]Wang Jinliang,Li Zongjun. Extreme-point symmetric mode decomposition method for data analysis [J].Advances in Adaptive Data Analysis,2013,5 (3): 1137-1137.

[9]王跃，吕林，李星雨，等．基于极点对称模态分解的混合储能系统容量 配置[J].电力建设,2017,38(6):116-123.(WangYue,LyuLin,LiXingyu et al.Capacity allocation ofhybrid energy storage system based on extremepoint symmetric mode decomposition [J]. Electric Power Construction, 2017,38 (6): 116-123.)

[10]曾彭，刘红星，宁新宝，等．总体经验模态分解能量向量用于ECG能量 分布的研究[J].物理学报,2015,64(7):78701-078701.(Zeng Peng,Liu Hongxing,Ning Xinbao,et al.ECG energy distribution analysis using ensemble empirical mode decomposition energy vector [J].Acta Physica

Sinica,2015,64(7): 78701-078701.)   
[11]谭晓衡，褚国星，张雪静，等．基于高阶累积量和小波变换的调制识别 算法[J]．系统工程与电子技术,2018(1):171-177.(Tan Xiaoheng,Qi Guoxing, Zhang Xuejing, et al. Modulation recognition algorithm based on high-order cumulants and wavelet transform [J]. Systems Engineering and Electronics,2018 (1): 171-177.)   
[12]吴良圆，魏书宁，周棒棒，等．基于PCA降维的分层超限学习机手势识 别方法[J].电子测量技术，2017,40(3):82-88.(WuLiangyuan,Wei Shuning，Zhou Bangbang,et al. Hierarchical extreme learning machine gesture recognitionmethod based on PCA dimension reduction [J]. Electronic Measurement Technology,2017,40 (3): 82-88.)   
[13]KumarDohare A,Kumar V,Kumar R.Detection of myocardial infarction in 12 lead ECG using support vector machine [J].Applied Soft Computing, 2018,64:138-147.   
[14]张柯，杨杰，程琳．基于 ABC-SVM 的土石坝变形监测模型[J].水资 源与水工程学报,2017,28(4):199-204.(Zhang Ke,Yang Jie,Cheng Lin. Earth-rockfill dam deformation monitoring model based on ABC-SVM[J]. Journal of Water Resources and Water Engineering,2017,28 (4): 199-204.)   
[15] ClarkMA EN,Katibi I, Macfarlane PW.Automatic detection of end QRS notching or slurring [J]. Journal of Electrocardiology,2014,47(2):151-154.   
[16] Wang Yi(Grace),Wu HT,Daubechies I,et al.Automated J wave detection from digital 12-lead electrocardiogram [J]. Journal of Electrocardiology, 2015,48 (1): 21-28.