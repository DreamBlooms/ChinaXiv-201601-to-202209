# 基于DMD-LSTM模型的股票价格时间序列预测研究

史建楠1，邹俊忠1，张见¹，汪春梅²，卫作臣1(1．华东理工大学 信息科学与工程学院，上海 200237;2.上海师范大学 信息与机电工程学院，上海 200234)

摘要：针对股票市场关系复杂导致的有效特征提取困难、价格预测精度低等问题，提出一种基于动态模态分解-长短期记忆神经网络（DMD-LSTM）的股票价格时间序列预测方法。首先通过DMD算法对受市场板块联动效应影响的关联行业板块样本股数据进行分解计算，提取包含整体市场和特定股票走势变化信息的模态特征；然后针对不同市场背景，采用LSTM网络对基本面数据和模态特征进行价格建模预测。在鞍钢股份（sh60000）上的实验结果表明，该方法相较于传统预测方法，在特定的市场背景下能实现更高的价格预测精度，更为准确地描述股票价格的变化规律。

关键词：动态模态分解；长短期记忆神经网络；模态特征；板块联动效应；市场背景 中图分类号：TP391 doi: 10.19734/j.issn.1001-3695.2018.08.0657

Research of stock price prediction based on dmd-lstm model

Shi Jiannan1, Zou Junzhongl†, Zhang Jian1, Wang Chunmei²,Wei Zuochen1 (1.College of Information Science& Engineering,East China University of Science & Technology，Shanghai 200237, China;2.Colegeof Information Mechanical &Electrical Engineering,Shanghai Normal University,Shanghai 200234, China)

Abstract: Aiming atthe problems oflow prediction accuracy and feature extraction dificultyin complicated stock market, this paper proposed a stock price prediction method based on dynamic mode decomposition and long short-term memory neural network (DMD-LSTM).Firstly,it used the DMD algorithm to decompose the industry specific stock in the background of plate linkage phenomenon,and extractedthe mode feature which included stock trend information.Then, built theLSTMnetwork toestablish therelations betweenstock priceand the featureof modeandbasic index in different marketconditions.Theexperimental resultson Angang Stee (sh6Ooo0）show that,the proposed method has the higher forecasting precision compared withthetraditional ways in specificcondition,，which can characterize the trendof stock price changes better .

Key words:dynamic mode decomposition ；long short-term memory neural network；mode feature；plate linkage phenomenon;market condition

# 0 引言

股票市场作为国家经济的晴雨表，已经成为国家经济发展不可或缺的一部分。由于股票市场的重要性，通过分析挖掘股市历史数据和各项技术指标，并依据相关理论和算法模型来预测市场的价格走势情况具有重要的理论意义和社会价值[1。股票市场作为复杂且时变的巨系统，其价格波动往往表现为较强的非线性[2，因此如何从海量的市场数据中获取有价值的信息为决策服务是一个难点。

股票市场中，不同行业板块间的股票价格和收益率波动变化往往存在着一定的关联性，通常称之为联动效应。Bradly[3]采用方差分析法对同一证券市场不同板块股价联动效应进行深入研究，发现标普指数下不同行业指数间存在明显的联动效应；周武4在对国内A股市场多组行业板块进行分析后发现，不同市场经济周期下行业板块联动效应存在明显差异；魏国林[5]利用数据挖掘技术分析得出我国股市行业板块间的联动效应高于板块内各股联动效应。而在国内股市发展历程中，很多行情的大幅变化通常由多个板块带动发展而来[6]。因此借助相关行业板块趋势变化来发掘潜在关联信息，在股票价格预测上具有重要的研究意义。

由于股票市场数据指标众多且存在高维非线性的特性，目前的价格股票预测方法主要是将数据特征提取和模型预测过程相结合来进行研究。比如Xu等人7采取改进的经验模态分解算法（EEMD）对股票时间序列进行模态分解，并根据分解得到的模态信息成功预测市场价格趋势；Mann[8]将动态模态算法（DMD）用于证券市场这个高维非线性系统的信息提取上，并利用时空相干性结构信息来表征系统动态特征，准确的描述了市场价格变化和形态走势；李晋[9利用离散小波分析来挖掘期货价格序列中隐含的趋势信息，然后引入支持向量机对重构的小波系数进行训练，大大提高了预测精度；郭志强[10利用多线性主成分分析法（MPCA）进行特征提取和数据降维，并结合RBF神经网络在日经指数上进行了建模研究；史文静[11]对股指期货价格序列采用EMD算法得到IMF本征模函数，并结合RBF神经网络对提取出高低频IMF 进

行建模来实现价格预测。

当前的股票预测方法大多直接选取市场数据为研究对象，没有考虑板块联动效应下关联行业板块整体走势间的影响和潜在关联因素；在特征提取方面对数据进行降维和转换等操作，缺乏业务可解释性；预测模型通常选取以统计学理论为基础的时间序列分析方法和传统机器学习方法，其在非线性时间序列预测准确性和时序信息利用方面均存在不足。

针对以上问题，本文从关联行业板块存在的联动效应出发，首先针对不同算法分别进行数据集构造，并通过DMD（动态模型分解）算法对关联行业板块下样本股数据进行分解计算，提取代表行业板块的市场整体趋势以及股票自身价格趋势信息的模态特征。后续利用LSTM神经网络对非线性时间序列良好的拟合预测能力，分别构建LSTM模型对不同市场背景下股票基本面数据和模态特征进行学习，最终建立基于DMD-LSTM模型的股票价格预测方法及其融合模型。通过将不同市场背景下的模型预测结果与传统的机器学习方法进行分析对比，检验模型的有效性。

# 1 算法原理

# 1.1 DMD 算法

DMD（dynamic mode decomposition）动态模态分解由Schmid提出，并应用于流体分析、复杂系统构建以及数据挖掘方面[2]。DMD 算法围绕Koopman 算符发展而来，其创新性的结合了时间维度上的功率谱分析和空间维度上的主成分分析的特点，通过将时间序列数据分解为特征值和特征向量，将高维非线性系统近似简化为低维线性系统表示，最终实现系统当前状态重构和短期状态预测[13]。

设 $x _ { 1 } , x _ { 2 } , \cdots , x _ { M }$ 为原始数据中 $M$ 个时间序列截面数据，每个时间序列截面数据包含 $N$ 个样本，记为 $N { \times } M$ 矩阵$X = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { M } ]$ ，称为数据快照（data shot）。

根据Koopman算符线性映射的思想，总能找到一个矩阵$A$ 使得系统下一时刻的状态由上一时刻的状态进行表示，即$x _ { j + 1 } = A x _ { j }$ 。将数据快照数据表示为Krylov子序列形式

$$
X _ { 1 } ^ { M - 1 } = [ x _ { 1 } , x _ { 2 } , . . . . , x _ { M - 1 } ] = [ x _ { 1 } , A x _ { 1 } , . . . , A ^ { M - 2 } x _ { 1 } ]
$$

$$
X _ { 2 } ^ { M - 1 } = [ x _ { 2 } , x _ { 3 } , . . . , x _ { M } ] \ = A X _ { 1 } ^ { M - 1 }
$$

矩阵 $A$ 为系统由 $X _ { 1 } ^ { M - 1 }$ 向 $X _ { 2 } ^ { M - 1 }$ 状态演变规律的线性估计，则 $X _ { 2 } ^ { M - 1 }$ 中 $x _ { M }$ 可以由上一个时刻 $X _ { 1 } ^ { M - 1 }$ 中线性独立的 $x _ { i }$ （列矢量）的加权线性组合来表示：

$$
x _ { M } = \sum _ { m = 1 } ^ { M - 1 } a _ { m } x _ { m } + r \ = X _ { 1 } ^ { M - 1 } a + r
$$

其中：a为加权线性组合的权值矢量， $\boldsymbol { r }$ 为长度为 $N$ 的残差矢量。根据上式可得关系：

$$
A X _ { 1 } ^ { M - 1 } = X _ { 2 } ^ { M - 1 } = X _ { 1 } ^ { M - 1 } S + r e _ { M - 1 } ^ { T }
$$

$e _ { M - 1 } ^ { T }$ 为单位矢量，通过极小化残差矩阵 $r e _ { M - 1 } ^ { T }$ 来寻找矩阵$A$ 分解后最优的低维特征值和特征矢量，可以使得系统估计值和目标 $x _ { M }$ 最接近。 $s$ 为低维近似矩阵，矩阵 $A$ 的特征值可由矩阵 $s$ 的特征值来近似替代。

$$
S = \left[ \begin{array} { c c c c c } { 0 } & & & & { a _ { 1 } } \\ { 1 } & { 0 } & & & { a _ { 2 } } \\ & { \ddots } & { \ddots } & & { \vdots } \\ & & { 1 } & { 0 } & { a _ { M - 2 } } \\ & & & { 1 } & { a _ { M - 1 } } \end{array} \right]
$$

矩阵 $s$ 最后一列矢量 $\mathbf { \Delta } _ { a }$ 的值可以表示为

$$
a = ( X _ { 1 } ^ { M - 1 } ) ^ { - 1 } x _ { M }
$$

实际求解中矩阵 $s$ 的性质通常较差不易求解，因此进一步采用 $s$ 的相似矩阵 $\tilde { s }$ 来进行计算求解。对式(5)中矩阵 $X _ { 1 } ^ { M - 1 }$

进行约化SVD分解，并进行转换可得

$$
X _ { 2 } ^ { M - 1 } = U \Sigma \ V ^ { H } S
$$

$$
S = V \Sigma ^ { - 1 } U ^ { H } X _ { 2 } ^ { M - 1 }
$$

$$
\tilde { S } = U ^ { H } X _ { 2 } ^ { M - 1 } V \ \Sigma ^ { - 1 } = U ^ { H } A U \equiv \tilde { A }
$$

将计算矩阵 $A$ 的特征值问题转换为计算矩阵 $\tilde { s }$ 的特征值$u _ { k }$ 和特征矢量 $y _ { k }$ ，特征值 $u _ { k }$ 包含着以 $\Delta t$ 为时间间隔的系统向下一个时刻状态变化的时间动态特征

$$
\tilde { S } y _ { k } = u _ { k } y _ { k } k = 1 , 2 , . . . . , K
$$

系统的DMD动态模态可以由矩阵 $A$ 第 $k$ 个特征矢量 $\psi _ { \star }$ 表示，根据相似矩阵的性质可得

$$
\psi _ { k } = U y _ { k }
$$

最终，利用 $\psi _ { k }$ 和 $u _ { k }$ 可以实现系统当前状态重构和将来状态预测。改写特征值形式为 $\omega _ { k } = \ln ( \mu _ { k } ) / \Delta t$ ，则系统 $t$ 时刻截面数据可以表示为

$$
x _ { D M D } ( t ) = \sum _ { k = 1 } ^ { K } b _ { k } ( 0 ) \psi _ { k } \left( x \right) \exp ( \omega _ { k } t ) = \Psi d i a g ( \exp ( \omega t ) ) b
$$

其中： $b _ { k } ( 0 )$ 为模态初始幅值， $\Psi$ 为特征向量 $\psi _ { k }$ 组成的矩阵，$d i a g ( \omega t )$ 是对角元为 $\exp ( \omega t )$ 的对角阵， $\mathbf { b }$ 为 $b _ { k } ( 0 )$ 构成的向量。向量 $\mathbf { b }$ 通过0时刻的截面数据 $x _ { 1 }$ 进行求解，利用DMD进行状态重构得到 $x _ { 1 }$ ，然后求矩阵伪逆即可。

$$
x _ { 1 } = x _ { D M D } ( 0 ) = \Psi d i a g ( \exp ( 0 ) ) b = \Psi \cdot b
$$

$$
b = \Psi ^ { + } x _ { 1 }
$$

DMD算法通过提取低维动态特征来表征系统变化，实现以线性映射去最优拟合系统的非线性动态情况，最终利用提取的DMD动态模态实现对系统任意时刻的状态估计。

# 1.2LSTM神经网络

循环神经网络（RNN）是目前较为流行的应用于时间序列预测的神经网络模型。传统的前向神经网络比如BPNN，神经元信号只能单向流动，导致对样本的处理在时间上是独立的，对时间序列数据而言损失了重要的时序信息[14]。RNN在传统神经网络结构基础上进一步对隐层神经元之间也引入了权连接，使得隐层神经元每个时刻的输出都依赖于之前时刻的信息，网络单元既存在前馈连接又有内部反馈连接，实现了动态时序行为在神经网络单元内部状态的转换。

但在实际应用中，RNN存在梯度消失和梯度爆炸导致的长期依赖问题，使得其无法应用于较长时间序列数据的建模。而由Grves[15]改进提出的LSTM（Long Short-Time Memory）模型作为RNN的一种完善成功解决了上述问题。LSTM利用特定的记忆单元代替了RNN 链式结构中的隐层节点，实现了时序信息保留和长期记忆的能力。图1为LSTM中的记忆单元结构。

LSTM记忆单元的主要结构是门(gates)和记忆细胞（cell），门结构可以让信息选择性的通过实现信息的去除或者增加，实现记忆细胞状态的保持和更新，具体包括输入门（input gates）、输出门（output gates）、遗忘门（forget gates）;记忆细胞负责存储细胞状态信息。

遗忘门将当前时刻的输入值 $x ^ { ( t ) }$ 和上一时刻的隐藏状态值 $h ^ { ( t - 1 ) }$ 作为sigmoid函数的输入，产生一个[0,1]的权值输出$f ^ { ( t ) }$ 。权值可看做记忆单元遗忘上一层细胞状态的概率，通过将 $f ^ { ( t ) }$ 乘以记忆单元上一刻的细胞状态 $C ^ { ( t - 1 ) }$ 来控制上一单元信息被保留程度。

$$
f ^ { ( t ) } = \sigma ( W _ { f } \cdot [ h ^ { ( t - 1 ) } , x ^ { ( t ) } ] + b _ { f } )
$$

输入门利用sigmoid函数和tanh函数配合来控制能够进入细胞状态的新输入信息的量。其中tanh函数生成新信息$\tilde { C } ^ { ( t ) }$ ，sigmoid 函数产生[0,1]的权值来控制进入细胞状态的信息量大小。进一步将输入门和遗忘门相结合就可以实现将细

胞状态由 $C ^ { ( t - 1 ) }$ 更新为 $C ^ { ( t ) }$ 。

$$
\begin{array} { r } { \dot { \iota } ^ { ( t ) } = \sigma ( W _ { i } \cdot [ h ^ { ( t - 1 ) } , x ^ { ( t ) } ] + b _ { i } ) } \end{array}
$$

$$
\tilde { C } ^ { ( t ) } = \operatorname { t a n h } ( W _ { a } \cdot [ h ^ { ( t - 1 ) } , x ^ { ( t ) } ] + b _ { a } )
$$

$$
C ^ { ( t ) } = f ^ { ( t ) } * C ^ { ( t - 1 ) } + i ^ { ( t ) } * \tilde { C } ^ { ( t ) }
$$

输出门通过对当前细胞状态 $C ^ { ( t ) }$ 使用tanh函数进行处理得到进入下一时刻的细胞状态信息，然后配合sigmoid函数得到的权值 $o ^ { ( t ) }$ 来控制细胞状态信息的过滤程度，并最终得到下一时刻的隐藏信息 $h ^ { ( t ) }$ 。

$$
O ^ { ( t ) } = \sigma ( W _ { o } \cdot [ h ^ { ( t - 1 ) } , x ^ { ( t ) } ] + b _ { o } )
$$

$$
h ^ { ( t ) } = o ^ { ( t ) } * \operatorname { t a n h } ( C ^ { ( t ) } )
$$

LSTM通过更换RNN链式结构中记忆单元实现了对信息流的控制，较为成功的解决了RNN中出现的梯度问题，实现了长周期信息的记忆。目前LSTM已经在多种时间序列数据预测上获得了广泛的应用，包括NLP任务，证券市场价格预测等。

![](images/7624fe06fb4b6c397b2c9430e9332c344a9e6c25c91973f8c887ae17d8941821.jpg)  
图1LSTM记忆单元结构

# 2 基于DMD和LSTM的股票价格预测方法

# 2.1模型数据集构造

在时间序列分析中，数据样本通常采用滑动时间窗技术来进行切分构建，本文针对DMD算法和LSTM模型的不同分别进行数据样本构建。

![](images/c025900cbd6dcb59fab695d34673a5ef3ffb98e02506f88ca4822f72776ae088.jpg)  
Fig.1Structure of LSTM memory unit   
图2DMD数据快照矩阵切分构建

图2展示了DMD数据快照矩阵的构建过程。DMD算法提取模态特征（modefeature）的源数据为关联行业板块下M支样本股的N天的收盘价数据集合，设定滑动步长为1，通过滑动时间窗来切割源数据获取DMD算法所需的数据快照矩阵X。为了消除不同股票价格间的差异性，对数据快照X中样本股数据分别进行归一化（minmaxscaler）处理。

LSTM模型进行建模的数据为股票的基本面特征（rawfeature）和提取的DMD模态特征数据组成。设滑动窗口宽度为L，采用滑动时间窗从数据集中截取数据单元构建样本，并取窗口后一天的收盘价为作为预测目标。通过不断后移，形成一系列相互覆盖的样本数据，在降低数据时变特性的同时，利用了数据的时序信息。

![](images/056719234aa118267f7f69b86c2c2446d37c1d68717f5ca239377e61356b5520.jpg)  
图3LSTM数据集样本切分构建 Fig.3Construction of LSTM dataset

最终得到的数据集中不同特征值范围差异较大，不利于LSTM模型收敛，同样需要对LSTM数据集中特征分别进行归一化操作来调整数据分布。

# 2.2基于DMD 模态分解的特征提取

DMD 算法适用于复杂系统分析，但其应用于股票市场的前提假设是：股票市场是整体相关的复杂系统，即某个行业板块的股票价格波动可能受到相关行业板块的影响。在此基础上利用DMD分别提取代表过去 $\mathfrak { n }$ 天的市场整体趋势变化和特定股票价格变化的模态特征，捕捉股票价格变化的动态特性和潜在行为模式。实证研究中DMD 算法的应用对象来自于沪深股市中5个行业板块，其中主导行业为钢铁行业，关联行业为有色金属、金属制品、汽车制造业、建筑业。

利用DMD对数据快照矩阵X进行模态分解后可以获取整个系统的动态模态，以特征值 $u _ { k }$ 来表示。特征值 $u _ { k }$ 分解顺序对应着市场动态模态信息量的大小，将系统分解得到的第一个特征值 $u _ { 1 }$ 称为主导特征值，又称主导模态（domainmode），其代表整个市场的主要趋势信息。由于特征值一般为复数，Mann[8指出当特征值位于在单位圆外，其模值大于1，意味着市场有扩张趋势；当特征值位于在单位圆内，其模值小于1，市场有紧缩趋势；当特征值位于在单位圆上时，表示市场整体趋势平稳。特别对于位于横轴没有虚部的特征值，对应模态下的市场趋势变化速率是指数形式的，因此该模态对于系统的影响相比于其他模态更加显著，是主导市场变化的重要因素之一。

图4为某个时间窗为20的数据快照矩阵X进行DMD模态分解运算的结果。左子图为分解得到的特征值 $u _ { k }$ 在复平面上的分布，对应于总体市场的模态特征；右子图为 $u _ { k }$ 经过傅里叶转换后的 $\omega _ { k }$ 在复平面的分布。图中三角形点为单位圆外包含扩张趋势信息的特征值，对应于复平面中实部大于0的 $\omega _ { k }$ 。

![](images/647c8fa9bf2306e644b1cac88120a69c50b12345a400c567cc102d0cb5ba351a.jpg)  
Fig.2Construction of DMD Snapshot matrix   
图4市场模态特征分布  
Fig.4Distributions of market's mode feature

图5为选取的鞍钢股份（sh00898）经过DMD分解得到的前10个动态模态，来源于特征向量 $\psi _ { k }$ ，对应价格趋势变化中不同层次的潜在信息。前三个主要模态值大于0呈现扩张趋势，后面影响因素较小的模态值小于0呈现下跌趋势。

![](images/75f452422bf51c4219296cd1fc0a4c56bfe14a74227ef243fb64d0d3800eeba5.jpg)  
图5鞍钢股份分解得到的动态模态

# 2.3DMD-LSTM价格预测模型

本文综合DMD算法和LSTM模型来进行股票价格预测，DMD算法用来对特定板块下的股票集合的日收盘价数据快照进行分解计算来提取模态特征，LSTM结合股票市场的基本面特征和提取的模态特征来进行模型训练，将股票收盘价的一步预测问题转换为监督学习问题。

股票市场形态主要分为单边形态、震荡形态、平稳形态和其他特定形态，不同的市场形态下数据变化情况不同，模型的预测效果存在差异。DMD主要依据数据历史趋势来进行模态的提取，因此模态分解得到的结果存在一定的滞后性。当市场处于单边形态时，DMD抽取的模态在市场趋势惯性下能较为准确的抓取市场变化的趋势信息；当市场处于震荡市场的时候，由于滞后性会使得DMD分解得到的模态对市场趋势变化的跟踪效果会减弱。因此本文分别就单边上涨、单边下跌、震荡三种不同的市场形态进行实证研究。

LSTM对股票价格进行建模需要指定数据的时间步和合适的特征。设定LSTM模型的样本时间步 $\scriptstyle { \mathrm { L } } = 2 0$ ，样本特征由两部分总计9维特征组成，其中基本面特征包括单只特定股票的交易日收盘价（close）、开盘价（open）、最高价（high）、最低价（low）、成交量（volume）5维特征，DMD模态特征为市场主导模态特征和对应股票的前3个动态模态特征共计4维特征。LSTM模型的网络结构和参数设置决定着模型的性能，因此需要通过相关指标定量的评价网络模型预测性能来获取最优的网络结构配置，实现股票价格与特征关系最佳映射。

在确定LSTM模型结构后，基于已训练的模型对测试集样本进行预测。在DMD-LSTM单模型基础上，根据模型融合的思路，将DMD-LSTM模型和基于基本面特征的LSTM单模型的预测结果加权平均作为预测值。最后对预测价格进行反归一化转换为实际价格量纲，通过评价指标来判断模型预测性能，整体模型预测流程见图6。

# 3 实证分析

# 3.1数据来源

选取钢铁行业板块中的鞍钢股份(sh00898)为研究对象，同时为了配合DMD计算需求，选取钢铁行业及相关行业下共计117支股票的收盘价来构建数据快照。

鉴于市场形态的不同，本文分别就股票单边上升期，单边下降期和价格震荡期三种市场形态进行实证研究。源数据为鞍钢股份2014-05-27到2018-05-27期间的日交易数据，选取2017-05-08到2017-08-02的股票价格单边上涨期，共计60天数据作为验证集，对应选取2014-05-27到2017-05-07约 700个交易日数据作为训练集；选取2017-02-22到2017-05-22的股票价格单边下跌期，共计60天数据作为验证集，对应选取2017-05-27到2017-02-21约650个交易日数据作为训练集；选取2017-09-27到2017-12-27的价格震荡期，共计60天数据作为验证集，对应选取2014-05-27到2017-09-26约800个交易日数据作为训练集。实验数据来源于新浪财经接口，数据集样本的划分构建和预处理见2.1节。

![](images/d94f71bc8b4305a0d724a8282714f9bb714595667b53848b5290ebbc61e97529.jpg)  
Fig. 5 DMD mode value of decomposition's result(Angang Steel)   
图6DMD-LSTM模型进行股票价格预测流程图 Fig.6Prediction procedure of DMD-LSTM model

# 3.2模型评价指标

在对模型预测效果进行定量评价时，本文对于价格预测能力的评价指标选取为均方根误差RMSE、平均绝对误差MAE、确定系数 $\mathbf { R } ^ { 2 }$ ，其中RMSE和MAE越小，模型对于真实值拟合的偏差越小，结果越准确；确定系数 $\mathbf { R } ^ { 2 }$ 越接近1，代表拟合优度越大，模型拟合数据能力效果越好。价格趋势变化预测能力的评价指标选取为方向准确率DA，其定义为模型对股票价格变化方向预测的准确性，具体公式定义如下：

$$
R M S E = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( \hat { y } _ { i } - y _ { i } ) }
$$

$$
R ^ { 2 } = S S R / S S T = { \sum _ { i = 1 } ^ { N } ( \hat { y } _ { i } - \overline { { y } } ) ^ { 2 } } \bigg / { \sum _ { i = 1 } ^ { N } ( y _ { i } - \overline { { y } } ) ^ { 2 } }
$$

$$
\ M A E = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \left| ( \hat { y } _ { i } - y _ { i } ) \right|
$$

$$
D A = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } d _ { i }
$$

其中： $N$ 为真实值和预测值对比次数， $\hat { y } _ { i }$ 为模型预测值， $y _ { i }$ 为真实值， $\overline { { y } }$ 为 $y _ { i }$ 的均值， $d _ { i }$ 为预测方向标志位，方向预测正确 $d _ { i }$ 置1，方向预测错误 $d _ { i }$ 置0。

# 3.3DMD-LSTM模型预测方法实现

# 3.3.1DMD 模态特征提取

DMD通过模态的提取来描述价格的变化规律，其中市场主导模态的变化代表着市场总体趋势随着时间变化的规律。如图7，主导模态模值总体围绕1进行波动，对于模值偏离1的模态，代表市场中有较强的上涨或者下跌的动力。

![](images/18cb28b22b22cf24107450467f1df01f09d6968cb711b25a0191829863b1dc6c.jpg)  
图7市场主导模态的时间序列曲线

图8为鞍钢股份全量数据进行DMD模态分解后，前三个主要的动态模态的日变化曲线。通常股票价格中长期走势相对来说变化较缓，可看做低频信号；而短期价格走势波动较大，可看做高频信号。类似的，动态模态1可看做低频高能量模态，其波动范围较为稳定，表示该股票的价格变化趋势相对较慢。模态2、3波动相较于模态1有所增加，相比于模态1为高频低能量的模态，波动相对较大，说明短期价格波动会比较显著。

0.25  
0.00 U ULTUNAPHA T  
-0.25  
0.25 Pa  
-0.25  
0.25  
0.00  
-0.250 200 400 600 800 1000交易日数

# 3.3.2LSTM模型结构选定

神经网络的网络结构和参数设置决定着模型的性能。为了客观分析模型的真实预测能力，消除参数选取差异对实证结果的影响，本文通过模型参数调优实现股票价格与特征关系的最佳映射。

本文的LSTM模型结构由输入层、两层LSTM层和输出层组成，损失函数使用均方根误差，模型训练过程中采用Adam算法进行优化。模型参数选择上包括学习率、隐层神经元个数、训练次数和正则化参数，网络模型的搭建在Tensorflow框架下实现。

以股票价格单边上涨情况为例，LSTM神经网络调参过程如下：首先固定训练次数epoch $\scriptstyle = 8 0 0$ ，进行隐层神经元个数和学习率的调节，将两层LSTM层中的节点个数从10到30间隔为2进行选取，调节学习率以间隔为0.0001从0.0001到0.001进行选取，两者总计100组参数，确定最佳的的隐层节点数和学习率组合为（14，14，0.0005）。epoch的大小会对模型的预测精度和运行效率造成较大影响，较大的epoch导致运行效率低并可能伴随过拟合现象，较小的epoch会使模型训练不充分出现欠拟合现象。图9为LSTM模型在训练过程中loss关于epoch 的变化曲线，根据loss 变化曲线确定最佳epoch为140。为了增加模型泛化能力消除过拟合现象，本文在LSTM网络结构中增加L2正则项，正则项系数为0.0001。

![](images/41ab62e26cdc92322f5d8f509a0c14edcb97dda3cefe4243d034b095d4fd7a48.jpg)  
Fig.7The curve of market's domain mode value   
图9单边上涨形态下LSTM的loss变化曲线 Fig. 9 The loss in LSTM training of single market

参照上述参数配置过程，选取对比实验模型的最佳的模型参数，基于RBF核的支持向量回归机(SVR)的正则化系数和gamma参数组合为（4，0.1）；基于SGD优化的BP神经最佳的学习率、隐层层数、隐层节点数、epoch的参数组合为（0.15，2，40，4500），DMD滑动窗口参数为20。对于股票价格单边下降和震荡形态，LSTM模型参数配置过程相同。

# 3.3.3结果对比与分析

为了检验模型的真实预测性能，消除偶然因素的影响，实证中针对不同的市场情况，分别对每种模型进行10次实验来取平均结果进行比较。

股票价格单边上涨阶段，市场趋势总体走强，相关模型的预测结果如表1所示。SVR模型和BP模型作为传统的预测方法，实证中以两者的预测结果作为基准进行对比。DMD作为无监督的数据挖掘方法，由结果可知其在价格预测上的精度较差，在RMSE指标上比基准水平低了平均 $3 5 . 6 1 \%$ 。由于市场趋势较为显著，DMD在价格趋势方向的预测准确性相对较高，DA指标比基准模型高了平均 $2 2 . 6 0 \%$ ，主要原因是DMD 能利用时序信息从市场行为中发掘趋势变化的有效信息。DMD-LSTM模型的价格预测精度高于其他单模型，包括仅利用基本面指标的LSTM模型，这说明DMD提取的模态特征一定程度上包含着市场行为变化的潜在信息，能提高LSTM模型的预测精度，其在RMSE 指标上比基准水平高了平均 $1 2 . 0 2 \%$ 。在模型融合方面，将LSTM单模型和DMD-LSTM单模型的预测结果进行加权平均，价格预测精度比DMD-LSTM模型高了 $1 . 3 4 \%$ ，同时模型的模型拟合优度最佳和DA值也有所提升，实现了预测效果的最优。图10为选取的三个结果差异较大的模型DMD、BP、融合模型的预测结果。

![](images/ed90b9de8d0d90393489594343ad76b7cc5bea91a7114880b7412e81952f8783.jpg)  
图8鞍钢股份前三个主要模态的变化曲线  
Fig.8The curve of the first three mode values(Angang Steel)   
图10单边上涨形态下模型预测结果对比图  
Fig.1OComparison results of various models in stronger markel

Table 1 Comparing the predict results of various models in stronge   

<html><body><table><tr><td colspan="5">market</td></tr><tr><td>预测模型</td><td>RMSE</td><td>MAE</td><td>R2</td><td>DA</td></tr><tr><td>SVR</td><td>0.1160</td><td>0.0879</td><td>0.9307</td><td>0.4576</td></tr><tr><td>BP</td><td>0.0921</td><td>0.0708</td><td>0.9564</td><td>0.4548</td></tr><tr><td>DMD</td><td>0.1389</td><td>0.1136</td><td>0.9006</td><td>0.5593 *</td></tr><tr><td>LSTM</td><td>0.0914</td><td>0.0702</td><td>0.9570</td><td>0.5198</td></tr><tr><td>DMD-LSTM</td><td>0.0898</td><td>0.0698</td><td>0.9592</td><td>0.4934</td></tr><tr><td>融合模型*</td><td>0.0886 *</td><td>0.0686 *</td><td>0.9596 *</td><td>0.5127</td></tr></table></body></html>

股票价格单边下跌阶段，市场总体走弱，相关模型的预测结果如表2所示。类似于单边上涨形态的预测结果，DMD在价格预测方面精度较差，但在预测价格趋势方向准确性依然好于BP和SVR两种基准模型。DMD-LSTM在单模型上的预测精度和LSTM单模型相当，取得了较高的预测准确性，RMSE误差比基准模型低了平均 $1 7 . 1 7 \%$ 。值得注意的是该模型在这个市场形态下的预测DA值相对较高，这与单边上涨情况的预测情况不同，可能原因是单边市场下的局部波动导致了这种不稳定的情况。在模型融合方面，预测结果进行加权平均后的预测误差RMSE在DMD-LSTM模型的基础上进一步下降了 $3 . 7 2 \%$ ，同时模型拟合优度最佳且DA值最大，实现了模型预测性能的最优。

![](images/59d842a128bedf11ac2a2fa532aa149e35963d287e42ba879dd42c952a416717.jpg)  
图11单边下跌形态下模型预测结果对比图  
Fig.11Comparison results of various models in weaker market 表2单边下跌形态下各个模型预测结果对比

Table 2Comparing the predict results of various models in weaker   

<html><body><table><tr><td colspan="5">market</td></tr><tr><td>预测模型</td><td>RMSE</td><td>MAE</td><td>R2</td><td>DA</td></tr><tr><td>SVR</td><td>0.1094</td><td>0.0809</td><td>0.9104</td><td>0.4746</td></tr><tr><td>BP</td><td>0.1247</td><td>0.0968</td><td>0.8834</td><td>0.5051</td></tr><tr><td>DMD</td><td>0.1593</td><td>0.1268</td><td>0.8102</td><td>0.5424</td></tr><tr><td>LSTM</td><td>0.0984</td><td>0.0801</td><td>0.9275</td><td>0.5424</td></tr><tr><td>DMD-LSTM</td><td>0.0989</td><td>0.0798</td><td>0.9235</td><td>0.5953</td></tr><tr><td>融合模型*</td><td>0.0970 *</td><td>0.0772 *</td><td>0.9294 *</td><td>0.5953 *</td></tr></table></body></html>

DMD方法进行有效的模态特征提取的前提是市场趋势存在延续性，当市场进入震荡调整期，行业板块联动效应较弱，DMD 算法较难从短期的时间序列数据中分解出有效的趋势信息。

股票价格震荡阶段，价格波动变化较大，相关模型的预测结果如表3所示。由于预测结果滞后性严重，DMD算法对于价格的拟合预测精度出现大幅下降，拟合优度为负数，表明无法进行有效的价格预测。相比于其他单模型，LSTM模型的预测精度最高，由于行业板块下提取的趋势变化的信息不准确，DMD-LSTM中的模态特征相当于引入外部噪声，因此其预测精度低于LSTM模型。进一步将预测结果平均加权进行模型融合后，尽管预测结果的RMSE和 $\scriptstyle \mathbf { R } ^ { 2 }$ 都实现了小幅度提升，但不排除偶然因素导致的影响。实证结果表明，基于DMD-LSTM模型的股票价格预测方法在市场震荡的情况进行应用还存在一定的缺陷。

![](images/62863bf37905a89d7a275559cebc1614c7684df5e6fbb104c606d3d4a33b5eea.jpg)  
图12震荡阶段下模型预测结果对比图  
Fig.12Comparison results of various models in shocking market 表3震荡阶段下各个模型预测结果对比

表1单边上涨阶段各模型预测结果比较  
Table 3Comparing the predict results of various models in shocking   

<html><body><table><tr><td colspan="5">market</td></tr><tr><td>预测模型</td><td>RMSE</td><td>MAE</td><td>R2</td><td>DA</td></tr><tr><td>SVR</td><td>0.1222</td><td>0.0956</td><td>0.5561</td><td>0.4746</td></tr><tr><td>BP</td><td>0.1183</td><td>0.0934</td><td>0.5830</td><td>0.5627</td></tr><tr><td>DMD</td><td>0.2012</td><td>0.1600</td><td>-0.2033</td><td>0.5254</td></tr><tr><td>LSTM</td><td>0.1109</td><td>0.0908 *</td><td>0.6340</td><td>0.5720 *</td></tr><tr><td>DMD-LSTM</td><td>0.1150</td><td>0.0965</td><td>0.6059</td><td>0.4814</td></tr><tr><td>融合模型*</td><td>0.1106 *</td><td>0.0930</td><td>0.6359 *</td><td>0.5322</td></tr></table></body></html>

# 4 结束语

本文提出的基于DMD-LSTM模型的股票价格预测方法，从国内股市相关行业板块存在的关联效应出发，通过DMD 算法进行模态特征提取来获取行业板块间的潜在关联因素和趋势信息，然后将LSTM模型应用于股票价格预测，充分的利用了时序信息和模态特征。

通过鞍钢股份不同市场背景下的对比实验表明，相比于传统机器学习预测方法，本文模型在单边市场趋势显著的前提背景下，能取得更加准确的预测结果，包括更低的预测误差和更高的方向准确性。这表明在单边市场情况下，行业板块关联效应较为显著，利用DMD提取的模态特征能有效提升模型的预测性能。在震荡市场情况下，模型效果并不理想，其原因在于市场价格波动明显，价格变化影响因素复杂，行业板块联动效应较弱，相关模态特征提取方法很难获取有效的趋势信息。之后工作将进一步研究震荡市场情况下，板块关联效应同动态模态特征提取间的关系。

# 参考文献：

[1]Nazärio RTF,SilvaJLE,Sobreiro VA,etal.A literature review of technical analysis on stock markets [J].Quarterly Review of Economics & Finance,2017,66(1):115-126.   
[2]Weng Bin,Ahmed M A,Megahed FM. Stock market one-day ahead movement prediction using disparate data sources [J].Expert Systems with Applications,2017,79(2):153-163.   
[3]Bradley T E.The transmission of shocks among S&P indexes [J]. Applied Financial Economics,2002,12(4): 285-290.   
[4]周武．股改以来我国股市行业板块间联动效应的实证研究[D].合肥： 安徽财经大学,2012.(Zhou Wu.Co-movement in different industry index after stock reform in China [D].Hefei: Anhui University of Finance and Economics,2012.)   
[5]魏国林．我国股市联动效应和龙头股研究[D].成都：西南财经大 学，2013.(Wei Guolin.The research of stock linkage effect and bellwether [D].Chengdu: Southwestern University of Finance and Economics,2013.)   
[6]温凯迪．我国证券市场板块联动效应研究[D].合肥：安徽大学, 2013.(Wen Kaidi.Research on plate linkage phenomenon in China’s securities market [D].Hefei: Anhui University,2013.)   
[7]Xu Mengjia,Shang Pengjian,Lin Aijing.Cross-correlation analysis of stock markets using EMD and EEMD [J].Physical A Statistical Mechanics & Its Applications,2016,442(1): 82-90.   
[8]Mann J,Kutz JN.Dynamic mode decomposition for financial trading strategies [J].Quantitative Finance,2015,2015(8):Article ID1170194.   
[9]李晋．基于小波分析和GA-SVR模型的股指期货价格预测方法研究 [D].广州:华南理工大学,2011.(Research on stock index future price forecasting methods based on wavelet transform and GA-SVR model [D].Guangzhou: South China University of Technology,2011.)   
[10]郭志强，曾亚丽，杨杰，等．基于MPCA-RBF 模型的证券市场指数 时间序列预测[J].计算机应用研究，2017,34(11):3299-3302.(Guo Zhiqiang,Zeng Yali,Yang Jie,et al.Time series forecasting of stock market index based on MPCA-RBF model [J].Journal of Application Research of Computers,2017,34(11):3299-3302.)   
[11]史文静，高岩.EMD结合RBF神经网络新混合模型及股指期货价格 预测[J].经济数学，2015(1):47-51.(Shi Wenjing，Gao Yan. Prediction of the Chinese stock index futures market based on new EMD-RBF model [J]. Journal of Quantitative Economics,2015(1): 47-51. )   
[12] Schmid P J.Dynamic Mode Decomposition of numerical and experimental data[J]. Journal of Fluid Mechanics,2O1O,656(1O): 5-28.   
[13] Cui Lingxiao,Long Wen.Trading strategy based on dynamic mode decomposition: Tested in Chinese stock market [J].PhysicaA Statistical Mechanics & Its Applications,2016,461(1):498-508.   
[14]龙奥明，毕秀春，张曙光．基于LSTM 神经网络的黑色金属期货套 利策略模型[J]．中国科学技术大学学报，2018，48(2)：125-132. (Long Aoming,Bi Xiuchun, Zhang Shuguang.An arbitrage strategy model for ferrous metal futures based on LSTM neural network [J]. Journal of University of Science and Technology of China,2O18,48(2): 125-132. )   
[15] Graves A.Supervised Sequence Labelling [M]//Supervised Sequence Labelling with Recurrent Neural Networks.Berlin: Springer,2012: 5-13.