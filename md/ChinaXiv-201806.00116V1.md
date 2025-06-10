# 基于改进混沌分区算法的模糊信息抽取

万福成

(中国民族语言文字信息技术教育部重点实验室，兰州 730000)

摘要：在大数据环境下进行模糊信息挖掘抽取中受到数据之间的小扰动类间干扰的影响，导致信息抽取的特征聚类性不好，提出一种基于改进混沌分区算法的模糊信息抽取方法。对高维数据信息流进行分布式结构重组，以Lorenz 混沌吸引子作为训练测试集进行大数据模糊信息抽取的自适应学习训练，采用相空间重构技术对大数据的混沌吸引子负载特征量进行自相关特征匹配处理，提取模糊信息的平均互信息特征量，结合关联规则模糊配对方法进行大数据混沌分区，实现模糊信息的优化聚类，根据数据聚类结果实现模糊信息准确抽取，对抽取的高维模糊信息进行特征压缩，降低计算开销。仿真结果表明，采用该方法进行大数据样本序列的模糊信息抽取的聚类性较好，抗类间扰动能力较强，模糊信息抽取的准确概率较高，在数据挖掘和特征提取中具有很好的应用价值。

关键词：大数据；混沌；分区算法；聚类；模糊信息抽取中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.03.0209

# Fuzzy information extraction based on improved chaotic partition algorithm

Wan Fucheng (KeyLaboratory of National Language Intelligent Processing,Lanzhou 73oo3o,China)

Abstract:In theenvironmentof big data,the interference between the smalldisturbancesof thedataaffects the fuzzy information extraction，which leads to the poor clustering characteristics of information extraction.We propose a fuzzy informationextraction method basedontheimprovedchaotic partition algorithm.Thehigh dimensionaldata information flow isreorganized with distributed structure,and the Lorenzchaoticatractorisusedasthe training testsetfortheadaptive learning training ofbigdata fuzzy information extraction.We use the phase space reconstruction technique match big data's chaotic atractorload with autocorrelation feature matchingandextract the average mutual information featurequantityof fuzzyinformation.Throughrealizingtheoptimal clusteringoffuzzy information,theacurateextractionoffuzzy information is realizedacordingtotheresultofdata clustering,cariesoutthe featurecompressionoftheextracted high-dimensional fuzzyinformation,andreduces thecomputationaloverhead.The simulationresults show that,usingthis method toextract fuzzyinformation frombigdatasample sequencehas good clustering property,strong ability toresist inter-class disturbance, andhigh accurate probabilityoffuzzy information extraction.It has agood application value in data mining and feature extraction.

Key words:large data; chaos; partition algorithm; clustering; fuzzy information extraction

# 0 引言

在大规模的数据中进行有效的数据区分和挖掘，如何利用和管理好大数据成为人们需要重点解决的问题，在大数据环境下，对模糊信息进行准确的特征分析和抽取，快速挖掘人们需要的数据信息，对数据进行整合，实现信息共享和准确链接传输，成为未来信息处理和大数据分析的重点研究课题，研究大数据环境下的模糊信息抽取方法，在云数据库设计、信息检索、语义分析以及信息融合等领域同样具有重要的应用价值[1]，相关的算法研究受到人们的极大重视。

对大数据环境下的模糊信息抽取方法研究是建立在对大数据聚类和信息分区基础上的，根据大数据的分类属性进行信息分区处理，提取大数据的聚类信息特征，采用特征分解和关联规则挖掘方法，实现对大数据的模糊信息抽取，常见的大数据模糊信息抽取方法有HPCC (high performance computing cluster)抽取方法，Roxie（HPCCdatadeliveryengine）信息聚类特征抽取方法、基于频繁项挖掘的特征抽取方法、基于模糊C-均值聚类的模糊数据信息抽取方法等[2.3]，通过提取模糊大数据的属性分区特征。采用相应的聚类算法实现对大数据的模糊信息抽取，结合关联性的信息融合方法，提高模糊信息检测能力，根据上述原理，相关学者进行模糊信息抽取算法研究，取得了一定的研究成果，其中，文献[4]中提出一种基于类间闭频繁项集挖掘的混合大数据的相似度信息抽取方法，采用多层次的语义特征抽取方法进行大数据信息挖掘，根据用户的Jarccad相似度信息实现大数据模糊分区，提高信息的融合聚类能力，但该方法进行模糊信息抽取中存在计算开销过大和相似度特征分布稀疏性较强等；文献[5]中提出一种基于离散高斯随机检验的模糊大数据信息抽取方法，采用分段线性融合方法进行模糊信息的高斯随机信息特征提取，采用匹配滤波进行冗余信息过滤，提高大数据的模糊信息抽取的统计分析能力，该方法对模糊集的特征信息融合中受到类间干扰较大，容易导致模糊信息的错分和漏分。

针对上述问题，本文利用混沌的随机聚类性和抗扰动性，提出一种基于改进混沌分区算法的模糊信息抽取方法。首先构建大数据的模糊信息流模型，进行大数据的信息重组和相空间重构，然后利用混沌分区算法进行特征提取和数据聚类，实现大数据集中模糊信息优化抽取。最后进行实验分析，展示了本文方法在提高大数据模糊信息抽取准确性方面的优越性能。

# 1模糊信息分布式结构重组及相空间重构

# 1.1模糊信息分布式结构重组

为了实现对大数据中的模糊信息抽取，采用混沌分区方法进行关联规则挖掘，提取大数据中的模糊信息特征量，对大数据模糊信息时间序列混沌序列分析的第一步是进行相空间重构[6]，实现对模糊信息的分布式的结构重构和数据结构分析，假设待挖掘的大数据信息流观测时间序列 $\{ x _ { 1 } , x _ { 2 } , \cdots x _ { N } \}$ ，令 $x ( n )$ 为一组非平稳的宽带时间序列，在 $m$ 维分布式特征空间中进行模糊信息的结构映射，得到大数据的分布式重组结构式为

$$
X ( n ) = \{ x ( n ) , x ( n + \tau ) , \cdots , x ( n + ( m - 1 ) \tau ) \}
$$

$$
n = 1 , 2 , \cdots , N
$$

其中： $\tau$ 表示大数据在高维空间中的采样时间延迟，采用自适应的混沌训练方法进行特征融合，在高维特征空间中进行相轨迹演化分析，得到重构的大数据模糊信息的分布轨迹为

$$
X = [ s _ { 1 } , s _ { 2 } , \cdots s _ { K } ]
$$

$$
\begin{array} { r l } & { = \left[ \begin{array} { c c c c c } { \phantom { - } x ^ { 0 } 1 , \phantom { - } x ^ { 0 } 2 , } & { \phantom { - } x ^ { 0 } K ^ { \phantom { - } } } & & & \\ & & { x _ { 2 } } & { \cdots } & { x _ { K } } \\ & & & { x _ { 2 + \tau } } & { \cdots } & { x _ { K + \tau } } \\ { \phantom { - } x ^ { - } } & { \phantom { - } x ^ { - } } & { \cdots } & { \phantom { - } x ^ { - } } \\ & & & { \cdots } & { \cdots } \end{array} \right] } \\ & { \qquad x _ { 1 + ( m - 1 ) \tau } \quad \quad x _ { 2 + ( m - 1 ) \tau } \quad \cdots \quad x _ { M + ( m - 1 ) \tau } \quad } \end{array}
$$

其中: $K = N - ( m - 1 ) \tau$ ，表示的大数据搜索特征空间的嵌入维数， $\tau$ 为时延， $m$ 为信息的语义本体属性的层数，$s _ { i } = ( x _ { i } , x _ { i + \tau } , \cdots , x _ { i + ( m - 1 ) \tau } ) ^ { T }$ 称为相空间的特征矢量集。在模糊信息分布式结构重组模型中，采用模糊集搜索方法确定 $m$ 和时间延迟 $\tau$ 。在高维相空间中进行模糊信息的高阶统计量分析和特

征提取。

# 1.2大数据相空间重构

在对高维数据信息流进行分布式结构重组的基础上，进行大数据相空间重构，以Lorenz 混沌吸引子作为训练测试集进行大数据模糊信息抽取的自适应学习训练[8]，在相空间中的两个子空间分别为 $s$ 和 $\boldsymbol { Q }$ ， $s$ 由模糊训练集的解向量 $\{ s _ { 1 } , s _ { 2 } , \cdots , s _ { n } \}$ 构成，满足Lorenz混沌吸引子的聚类属性的条件概率为$P _ { s } ( s _ { i } )$ ， $i = 1 , 2 , \cdots , n$ ， $\boldsymbol { \mathcal { Q } }$ 由大数据模糊测试集的解向量$\{ q _ { 1 } , q _ { 2 } , \cdots , q _ { n } \}$ 构成，对应的大数据模糊信息抽取的检测概率为$P _ { q } ( q _ { j } )$ ， $j = 1 , 2 , \cdots , n$ 。在混沌分区训练下，构建大数据模糊信息的相空间重构模型为

$$
H ( S ) = - \sum _ { i = 1 } ^ { n } P _ { s } ( s _ { i } ) \log _ { 2 } P _ { s } ( s _ { i } )
$$

$$
H ( Q ) = - { \sum _ { i = 1 } ^ { n } P _ { q } ( q _ { j } ) } \log _ { 2 } P _ { q } ( q _ { j } )
$$

其中： $P _ { s } ( s _ { i } )$ 表示模糊信息的语义概念集 $s _ { i }$ 出现在混沌分区区域 $s$ 的概率，类似地， $P _ { q } ( q _ { j } )$ 表示模糊信息的本体特征概念集$q _ { j }$ 出现在混沌分区区域 $\boldsymbol { \mathcal { Q } }$ 的概率。在满足相似度一直的条件下，求相空间 $s$ 中满足模糊信息聚类条件的平均互信息为

$$
I ( Q , S ) = H ( Q ) - H ( Q \vert S )
$$

其中：

$$
H ( Q { \big | } s _ { i } ) = - \sum _ { j } \Biggl [ p _ { s q } ( s _ { i } , q _ { j } ) \Biggl / p _ { s } ( s _ { i } ) \Biggr ] \log _ { 2 } \Biggl [ p _ { s q } ( s _ { i } , q _ { j } ) \Biggl / p _ { s } ( s _ { i } ) \Biggr ]
$$

表示满足条件 $P$ 的分类属性集合，采用平均互信息融合方  
法。根据上述相空间重构结构，提取模糊信息的高维特征量，  
结合混沌分区算法进行模糊聚类，提高模糊信息挖掘的聚类性  
[9]。

# 2 模糊信息抽取算法实现

# 2.1改进的混沌分区算法

在对高维数据信息流进行分布式结构重组和相空间重构预处理的基础上，进行大数据的模糊信息抽取算法优化设计，本文提出一种基于改进混沌分区算法的模糊信息抽取方法。以Lorenz混沌吸引子作为训练测试集，进行大数据的模糊属性分区，给出Lorenz混沌吸引子表达式：

$$
\left\{ \begin{array} { l l } { d x / d t = - \sigma x + \sigma y } \\ { d y / d t = - x z + r x - y } \\ { d z / d t = x y - b z } \end{array} \right.
$$

式中各量均为约化后的无量纲量， $t$ 为表示对模糊数据的采样时间； $x$ ， $y$ ，z表示为Lorenz 混沌吸引子的分区变量； $\sigma$ ，$r$ ， $b$ 为模糊约束参量。采用四阶 Runge-Kutta 法进行模糊信息的混沌分区，对于模糊信息的特征矢量 $\boldsymbol { { X } } _ { n }$ ，在混沌分区的有限域中选择近邻轨迹向量 $\boldsymbol { X } _ { \eta ( n ) }$ ，令 $R _ { \ O _ { m n } }$ 为 $X _ { n }$ 与 $\boldsymbol { X } _ { \eta ( n ) }$ 的距离，得到大数据混沌分区的聚类中心欧氏距离为

$$
\begin{array} { l } { { \displaystyle R _ { m n } = \Big \| { \bf X } _ { \eta ( n ) } - { \bf X } _ { n } \Big \| _ { 2 } ^ { ( m ) } = \operatorname* { m i n } _ { j = N _ { 0 } , \cdots , N , j \ne n } \Big \| { \bf X } _ { n } - { \bf X } _ { j } \Big \| _ { 2 } } } \\ { { \displaystyle \quad \quad = \sqrt { \sum _ { l = 0 } ^ { m - 1 } ( x _ { \eta ( n ) + l \tau } - x _ { n + l \tau } ) ^ { 2 } } } } \end{array}
$$

在上述重构的相空间中进行自适应学习，将相空间的嵌入维数从 $m$ 增加到 $m + 1$ 时，得到模糊信息抽取的混沌分区的聚类中心优化值表示为

$$
\begin{array} { r l r } {  { R _ { ( m + 1 ) n } = \Big \| X _ { \eta ( n ) } - X _ { n } \Big \| _ { 2 } ^ { ( m + 1 ) } = \sqrt { \sum _ { l = 0 } ^ { m } ( x _ { \eta ( n ) + l \tau } - x _ { n + l \tau } ) ^ { 2 } } } } \\ & { } & { = \sqrt { \Big [ \Big \| X _ { \eta ( n ) } - X _ { n } \Big \| _ { 2 } ^ { ( m ) } \Big ] ^ { 2 } + \Big [ x _ { \eta ( n ) + m \tau } - x _ { n + m \tau } \Big ] ^ { 2 } } } \end{array}
$$

若 $R _ { ( m + 1 ) n }$ 比 $R _ { ☉ n }$ 大很多，表示模糊信息的类间属性扰动互不影响，可以作为模糊聚类中心，根据这一特性，得到的 $\boldsymbol { X } _ { \eta ( n ) }$ （20为 $X _ { n }$ 的最近邻点。构建判决统计量和判决准确，在混沌分区中进行模糊信息抽取的阈值判断，得到判决准则为

准则1

$$
\sqrt { \frac { { R _ { ( m + 1 ) n } } ^ { 2 } - { R _ { m n } } ^ { 2 } } { { R _ { ( m + 1 ) n } } ^ { 2 } } } = \frac { \left| x _ { \eta ( n ) + m \tau } - x _ { n + m \tau } \right| } { R _ { ( m + 1 ) n } } \ge R _ { t o l }
$$

准则2

$$
\frac { R _ { ( m + 1 ) n } } { \sqrt { \displaystyle \frac { 1 } { N } \sum _ { k = 1 } ^ { N } \biggl [ x _ { k } - \frac { 1 } { N } \sum _ { k = 1 } ^ { N } x _ { k } \biggr ] ^ { 2 } } } > A _ { t o l }
$$

其中： $R _ { t o l }$ 为Lorenz 混沌吸引子的分区阈值，根据经验值， $R _ { t o l }$ 可取15， $A _ { t o l }$ 表示模糊信息混沌分区的判决门限，取 $A _ { t o l } = 2$ 。

根据上述分析，实现对大数据环境下的模糊信息混沌分区，结合判决准则和判决统计量进行大数据模糊信息抽取的自适应学习训练，并进行特征提取和信息抽取[10]。

# 2.2信息抽取和特征压缩

假设模糊信息的分布时间序列 $\{ X _ { n } \} , n = 1 , 2 , \cdots , N$ ，代表原始待分区的大数据特征分布集，在混沌分区处理下，得到混沌分区后的特征分布 $X _ { _ { N } } = X _ { _ { n } } + \eta$ ，其中 $\eta$ 为观测噪声。在 $d$ 个大数据的分布信源中，采用相空间重构技术对大数据的混沌吸引子负载特征量进行自相关特征匹配处理[1I]，得到特征匹配输出：

$$
X _ { n } = \{ X _ { n } , X _ { n - \tau } , X _ { n - 2 \tau } , \cdots , X _ { n - ( d - 1 ) \tau } \}
$$

令 $\boldsymbol { R } _ { d \times L }$ 是 $d \times L$ 的矩阵，在混沌分区的闭频繁项区域中提取模糊信息的平均互信息特征量为

$$
R _ { 1 } = \{ X _ { 1 } , X _ { 2 } , X _ { 3 } , \cdots , X _ { d } \} ^ { T }
$$

模糊信息的关联规则向量集为

$$
\boldsymbol { R _ { 1 } ^ { \textit { T } } R _ { 1 } } = \{ X _ { 1 } , X _ { 2 } , { \cdots } , X _ { m } \} \{ X _ { 1 } , X _ { 2 } , { \cdots } , X _ { m } \} ^ { T }
$$

采用奇异分解方法对模糊信息特征值进行特征分解，得

$$
R _ { 1 } ^ { \ T } R _ { 1 } = V _ { 1 } \sum _ { 1 } V _ { 1 } ^ { T }
$$

对 $L { + } 1$ 到 $2 L$ 维的混沌分区大数据，根据上述方法类推，得到模糊信息抽取的输出特征值为

$$
\boldsymbol { R _ { 2 } } ^ { T } \boldsymbol { R _ { 2 } } = V _ { 2 } \sum _ { 2 } \boldsymbol { V _ { 2 } } ^ { T }
$$

$$
R _ { 2 } = \{ X _ { _ { d + 1 } } , X _ { _ { d + 2 } } , \cdots X _ { _ { d + m } } \} ^ { T }
$$

$$
{ R _ { 2 } } ^ { T } R _ { 2 } = \{ X _ { _ { d + 1 } } , X _ { _ { d + 2 } } , \cdots X _ { _ { d + m } } \} \{ X _ { _ { d + 1 } } , X _ { _ { d + 2 } } , \cdots X _ { _ { d + m } } \} ^ { T }
$$

其中：模糊信息的测试集 $V = [ V _ { 1 } , V _ { 2 } , \cdots , V _ { m } ] \in R ^ { m \times m }$ 是正交的,即 ${ V V } ^ { T } = I _ { \cal M } , { } ~ \sum = d i a g ( \sigma _ { 1 } , \sigma _ { 2 } , { } ^ { , \dots , } \sigma _ { \it m } ) \in R ^ { m \times m }$ ，混沌分区后的关联规则模糊特征向量集 $R ^ { T } R$ 满足类间平衡性，得到抽取的特征值聚类融合度排序为

$$
\sigma _ { 1 } > \sigma _ { 2 } > \sigma _ { 3 } > \cdots > \sigma _ { s + 1 } > \sigma _ { m }
$$

分析可见，采用上述方法抽取的某信息维数较高，需要进行特征压缩，特征压缩的步骤描述为：

a)计算混沌分区区域中的 $l$ 维模糊信息特征向量 $\vec { X } ( l , n _ { i } )$ ，根据分区的聚类属性值得到模糊信息分区离散度 $\hat { S } _ { \scriptscriptstyle { w } }$ ，计算模糊信息的 $l$ 个特征值 $\lambda _ { 1 } , \lambda _ { 2 } , \cdots , \lambda _ { 1 }$ 和对对应的高维特征量$Y = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { l } ] \circ \hat { S } _ { \scriptscriptstyle w } \mathcal { H }$ （204号

$$
\hat { S } _ { w } = \sum _ { i = 1 } ^ { c } p _ { i } \frac { 1 } { n _ { i } } { \sum _ { k = 1 } ^ { n _ { i } } } \Biggl [ \left( \overrightarrow { X } _ { k } ^ { ( i ) } - \overrightarrow { m } _ { i } \right) \left( \overrightarrow { X } _ { k } ^ { ( i ) } - \overrightarrow { m } _ { i } \right) ^ { T } \Biggr ]
$$

b)根据混沌分区的吸引子的中心矢量，得到模糊聚类的离散度矩阵 $S _ { b } = \sum _ { i = 1 } ^ { c } p _ { i } ( \stackrel {  } { m } _ { i } - \stackrel {  } { m } ) ( \stackrel {  } { m } _ { i } - \stackrel {  } { m } ) ^ { T }$ ，其中 $\stackrel { \longrightarrow } { m } = \sum _ { i = 1 } ^ { c } p _ { i } \stackrel { \longrightarrow } { m } _ { i }$ 的加权平均;

c)采用判决统计回归分析方法，在高维空间中进行特征压缩，输出特征量 $J \left( \overrightarrow { X } _ { j } \right) = \frac { y _ { j } ^ { T } S _ { b } y _ { j } } { \lambda _ { j } }$ ， $j = 1 , 2 , \cdots , l$ ，采用K-1. 变换进行特征排序，得到特征排列式$J \left( \overrightarrow { X } _ { 1 } \right) \geq J \left( \overrightarrow { X } _ { 2 } \right) \geq \cdots \geq J \left( \overrightarrow { X } _ { l } \right) ;$

d)输出 $d$ 维的模糊信息抽取特征量，抽取前 $d$ 个特征向量$J { \left( \overrightarrow { X } _ { j } \right) }$ 作为训练集，输出 $y _ { j }$ ， $j = 1 , 2 , \cdots , d$ ，得到模糊变换加权矩阵 $W = \left[ y _ { 1 } , y _ { 2 } , \cdots , y _ { d } \right]$

e)输出特征压缩后的信息抽取结果为 ${ \overrightarrow { X } } = W ^ { T } { \overrightarrow { X } }$ 。

通过上述处理，在混沌分区后输出的模糊信息特征量由 $l$ 降到 $d$ 维，从而降低了计算开销。

# 3 仿真实验与结果分析

为了验证本文方法在实现大数据集下的模糊信息抽取的应用性能，进行仿真实验，实验采用Visual $^ { \mathrm { C + + } }$ 进行算法编译，采用MATLAB 进行数据处理的编程设计，在MapReduce 编程框架进行数据抽取和信息聚类分析，大数据集来自于云平台Hadoop，大数据处理工具组件为 Thor（HPCCdatarefinerycluster），大数据测试样本集为OAEI（ontologyalignmentevaluationinitiative)，该大数据库存储了多版本的语义数据，作为本实验的数据测试集能具有较好的信息覆盖能力。数据采样的时间间隔为 $2 . 4 \mathrm { s }$ ，测试集的规模为2400Gbit,大数据训练集的采样样本长度为1024，Lorenz混沌吸引子的初始参数值设定为$[ x , y , z ] = [ - 1 , 0 , 1 ]$ ， $[ \sigma , r , b ] = [ 1 6 , 4 5 . 9 2 , 4 . 0 ]$ ，混沌分区迭代的训练步长为 $h = 0 . 0 1$ ，大数据聚类的信息分布区间为[0,1000]，在信息抽取中的干扰强度为-10dB，根据上述仿真环境和参数设定，进行大数据模糊信息抽取仿真实验，取三组测试样本，得到时域波形如图1所示。

![](images/50a316df6402879308e902cdeeb5364673fb76e453ee09523705aa938b9cc9ba.jpg)  
图2第一组样本的混沌分区和信息抽取结果

![](images/a8e646e80bce2c3fefd743c152957933f47d7d5c4b78634c06b6a27e2310a69c.jpg)  
图1测试样本时域波形

![](images/62c9bbe9b2517347c8535eb20a3032a554dfd5b9185c727541fc5668709abf46.jpg)  
图3第二组样本的混沌分区和信息抽取结果

以图1的数据样本为研究对象，采用本文方法进行混沌分区聚类和信息抽取，得到在最佳的相空间嵌入维和时间延迟下的各组样本的混沌分区和模糊信息抽取结果如图2\~4所示。

抽取的准确度较高，性能优于传统方法。

![](images/b79d4d175d95e1257da8a9a9239e1d6cd3d1ee1348006057dc0f780c22b4d4cd.jpg)  
图4第三组样本的混沌分区和信息抽取结果

表1模糊信息抽取的时间开销性能对比(单位:s)  

<html><body><table><tr><td>样本</td><td>本文方法</td><td>FCM</td><td>K-means</td></tr><tr><td>第一组</td><td>0.24</td><td>1.43</td><td>1.25</td></tr><tr><td>第二组</td><td>0.31</td><td>2.78</td><td>3.21</td></tr><tr><td>第三组</td><td>0.52</td><td>2.96</td><td>4.32</td></tr><tr><td></td><td>表2</td><td>抽取精度性能对比(%)</td><td></td></tr><tr><td>样本</td><td>本文方法</td><td>FCM</td><td>K-means</td></tr><tr><td>第一组</td><td>98.23</td><td>92.34</td><td>89.32</td></tr><tr><td>第二组</td><td>99.34</td><td>94.93</td><td>92.45</td></tr><tr><td>第三组</td><td>99.98</td><td>95.65</td><td>94.31</td></tr></table></body></html>

图2对应第一组数据样本，该组样本的时域波形波动较为稳定，表明该组数据的信息覆盖能力较强，而由图2可以看出，利用本文方法进行混沌分区聚类和信息抽取，得到在最佳的相空间嵌入维和时间延迟下的混沌分区和模糊信息抽取结果清晰，属性聚类性较好，表明所提方法对大数据信息可以实现准确信息抽取，这是由于所提方法在数据环境下，结合了判决准则和判决统计量进行了大数据模糊信息抽取和自适应学习训练，并进行特征提取，由此使其更加适用。图3对应的第二组数据样本，该组样本数据整体波动次数少，幅度较为一致，表明其数据分布较为分散、数据维数较高，本身聚类效果较差。而使用所提方法对其进行混沌分区和模糊信息抽取后，其混沌分区的属性聚类性较好，信息抽取的类间聚敛性较高，这是由于所提方法利用了自适应混沌训练方法进行特征融合，在高维特征空间中进行了相轨迹演化分析，重构了大数据模糊信息，从而提高了其混沌分区与模糊信息抽取能力。图3对应第三组数据样本，该组数据样本的时域波形波动无规律，且幅度较大，表明该组数据受到的类间干扰较大，而使用本文所提方法仍可以保证较好的混沌分区和模糊信息提取性能，表明所提方法的抗类间干扰能力较强，这主要是由于本文所提方法在对维数较高的信息抽取时，同时进行了特征压缩，降维处理有效降低了处理数据样本受干扰程度，改善其性能。

分析上述结果得知，采用本文方法进行大数据信息的混沌分区的属性聚类性较好，信息抽取的类间聚敛性较高，抗类间扰动能力较强，具有很好的模糊信息抽取能力。为了对比性能，采用不同方法，对各组样本进行模糊信息抽取，分析抽取精度和计算开销等参数指标，得到性能对比结果见表1和表2，分析表中结果得知，本文方法进行模糊信息抽取时间开销较小，

# 4 结束语

在大数据环境下，对模糊信息进行准确的特征分析和抽取，快速挖掘人们需要的数据信息，对数据进行整合，实现信息共享和准确链接传输，本文利用混沌的随机聚类性和抗扰动性，提出一种基于改进混沌分区算法的模糊信息抽取方法。采用Lorenz混沌吸引子进行大数据混沌分区，在重构的相空间中实现模糊信息抽取，并对抽取的高维数据进行特征降维。研究得知，本文方法能提高模糊信息抽取的精度，计算开销较小，抗类间干扰能力较强，性能优越。

# 参考文献：

[1]梁聪刚，王鸿章．微分进化算法的优化研究及其在聚类分析中的应用 [J]．现代电子技术，2016，39(13):103-107.(Ling Conggang，Wang Hongzhang. Optimization research on differential evolution algorithm and its application in clustering analysis [J]. Modern Electronic Technology, 2016,39 (13): 103-107.)   
[2]米捷，张鹏，于海鹏．粒子群差分扰动优化的聚类算法研究[J]．河南 工程学院学报,2016,28(1):63-68.(Mi Jie,Zhang Peng，Yu Haipeng. Large data clustering algorithm based on particle swarm differential perturbation optimization [J]. Journal of Henan University of Engineering (Natural Science Edition),2016,28(1): 63-68.)   
[3]邢淑凝，刘方爱，赵晓晖．基于聚类划分的高效用模式并行挖掘算法 [J].计算机应用，2016,36(8):2202-2206.(Xing Shuning,Liu Fang'ai, Zhao Xiaohui.Parallel high utility pattern mining algorithm based on cluster partition [J].Journal of Computer Applications,2O16,36(8): 2202-2206.)   
[4]Palomares I,Martinez L,Herrera F.A consensus model to detect and manage non-cooperative behaviors in large scale group decision making [J]. IEEE Trans on Fuzzy System,2014,22(3): 516-530.   
[5]李梓杨，于炯，卞琛，等．基于负载感知的数据流动态负载均衡策略 [J].计算机应用,2017,37(10):2760-2766.(Li Ziyang，Yu Jiong，Bian Chen,et al.Dynamic data stream load balancing strategy based on load awareness [J].Journal of Computer Applications，2017，37(10): 2760-2766.

[6]孙力娟，陈小东，韩 崇，等．一种新的数据流模糊聚类方法[J].电子与信息学报,2015,37(7):1620-1625.(Sun Lijuan,Chen Xiaodong,HanChong,et al.New Fuzzy-Clustering Algorithm for Data Stream [J]. JEIT,2015,37(7): 1620-1625.)

[7]邢长征，刘剑．基于近邻传播与密度相融合的进化数据流聚类算法[J]. 计算机应用，2015，35（7):1927-1932.XING Changzheng，LIU Jian. Evolutionary data stream clustering algorithm based on integration of affinity propagation and density. Journal of Computer Applications,2015, 35 (7):1927-1932.)

[8] 侯森，罗兴国，宋克．基于信息源聚类的最大熵加权信任分析算法[J]. 电子学报,2015,43 (5):993-999.(Hou Sen,Luo Xingguo,Song Ke.A maximum entropy weighted trust-analysis algorithm based on sources clustering [J].Chinese Journal of Electronics,2015,43 (5): 993-999.)

[9]毕安琪，王士同．基于Kullback-Leiber 距离的迁移仿射聚类算法 [J]

电子与信息学报，2016,38(8):2076-2084.(Bi Anqi，Wang Shitong. Transferaffinitypropagationclusteringalgorithmbased on Kullback-Leiber Distance [J].JEIT,2016,38 (8): 2076-2084.)   
[10]刘俊，刘瑜，何友，等．杂波环境下基于全邻模糊聚类的联合概率数据 互联算法 [J]．电子与信息学报,2016,38(6):1438-1445.(Liu Jun,Liu Yu,He You,et al. Joint Probabilistic data association algorithm based on all-neighbor fuzzy clustering in clutter [J].JEIT,2016,38 (6):1438-1445.)   
[11]吴鸿华，穆勇，屈忠锋，等．基于面板数据的接近性和相似性关联度模 型[J].控制与决策,2016,31(3): 555-558.(Wu Honghua,Mu Yong,Qu Zhongfeng,et al. Similarity and nearness relational degree based on panel data [J]. Control and Decision,2016,31(3): 555-558.)