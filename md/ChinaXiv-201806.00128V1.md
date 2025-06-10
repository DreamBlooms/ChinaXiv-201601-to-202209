# 基于GRU和注意力机制的远程监督关系抽取

黄兆玮，常亮，宾辰忠，孙彦鹏，孙磊(桂林电子科技大学 广西可信软件重点实验室，广西 桂林 541004)

摘要：随着深度学习的发展，越来越多的深度学习模型被运用到了关系提取的任务中，但是传统的深度学习模型无法解决长距离依赖问题；同时，远程监督将会不可避免地产生错误标签，针对这两个问题，提出一种基于GRU（gatedrecurrentuit）和注意力机制的远程监督关系抽取方法，首先通过使用GRU神经网络来提取文本特征，解决长距离依赖问题；接着在实体对上构建句子级的注意力机制，减小噪音句子的权重；最后在真实的数据集上，通过计算准确率、召回率，绘出PR曲线证明该方法与现有的一些方法相比，取得了比较显著的进步。

关键词：深度学习；远程监督；GRU；注意力机制 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.03.0197

# Distant supervision relationship extraction based on GRU and attention mechanism

Huang Zhaowei, Chang Liang,Bin Chenzhong†, Sun Yanpeng, Sun Lei (Guangxi KeyLaboratoryofTrustedSoftware,Guilin UniversityofElectronicTechnologyGuilinGuangxi541o04,China)

Abstract:With the development of deep learning,more and more deep learming models have been applied to the task of relationextraction,but traditional deep learning modelscannotsolve longdistance dependence problems.Atthe same time, distantsupervision willinevitably generate wrong labels.For thesetwoproblems,this work proposesa distantsupervision relationship extractionmethod based on GRU(Gated Recurrent Unit)and the attntion mechanism.First,theGRU neural network is adopted to extract text features and solve long-distance dependence problems.Secondthiswork constructsa Sentence-LevelAtention Mechanismonentitypairs toreduce theweightof noisesentences.Finall,basedontherealdataset, bycalculating the acuracyrate andrecallrate,thePR curve is drawn to prove the proposed method has achieved significant progress compared with some existing methods.

Key words:deep learning; distant supervision; GRU; attention mechanism

# 0 引言

关系抽取[1不仅是信息抽取的任务之一，也是构建和补全知识图谱的关键所在，其研究的主要内容是从文本内容中挖掘出实体与实体之间的语义关系[2]，从纯文本生成关系数据的过程，是自然语言处理（NLP）中的关键任务。该任务可以描述为：给定一段文本 S，确定两个目标实体对 $< e _ { 1 } , e _ { 2 } >$ 的关系类别 $r _ { \mathrm { { c } } }$

近年来，Freebase[3]、DBpedia[4]、YAGO[5]等知识库的建立，在NLP任务中得到广泛的应用，包括搜索、推荐、问答等。这些知识库都是由三元组事实构成，如(姚明，老婆，叶莉)。尽管现有的知识库中已经包含了大量的知识，但随着大数据时代的到来，这些知识仍无法满足人们的需要，迫切的需要从无结构化的文本中提取出结构化的数据。

本文提出了一种GRU（gated recurrent unit）神经网络和注意力机制相结合的远程监督关系抽取方法（GRU_ATT）。采用远程监督的方法，避免了人工在构建数据集上花费的时间与精力，采用GRU 模型克服了传统深度学习模型无法解决长距离依赖的问题，同时在句子层面上引入注意力机制，有效控制了冗杂数据给实验结果带来的影响。最后，在真实的数据集上评估GRU_ATT，实验结果表明，与现有方法相比，GRU_ATT在关系提取方面取得了一些明显的进步。文章的主要贡献在于：a)使用一种在句子层面构建注意力机制的方法;b)提出一种将注意力机制与GRU相结合的关系抽取方法。

# 1 相关工作

传统的关系分类的方法大多都是基于模式匹配，例如Harabagiu等人[7提出一种通过结合词汇和语义关系来进行关系分类的方法；Kambhatla[8提出一种基于逻辑回归的关系抽取方法。这些基于模式匹配方法都取得了较好的性能。但是不足之处在于：许多传统的NLP系统被用来提取高级特征，如词性标签、最短依赖路径和命名实体，从而导致计算成本的增加和额外的传播误差。另一个缺点是，由于不同的训练数据集的覆盖率较低，在通用性方面表现不佳。

大多数现有的受监督关系提取方法需要大量的标记关系训练数据，这样非常耗时费力。2009年Mintz等人[9首次提出了远程监督，他们通过对齐三元组知识库（KB）和文本，自动生成训练数据集。他们假设：如果两个实体在KB中有关系，那么包含这两个实体的所有句子将表达这种关系。例如，（姚明，老婆，叶莉）是KB中的三元组事实。远程监督将把包含这两个实体的所有句子视为该关系的正例。尽管远程监督是自动标记训练数据的有效策略，但它还是会带来一些错误的标签问题。例如，“姚明被邀参加腾讯体育名人赛，叶莉表示非常支持"姚明与叶莉共同出现在上海浦东国际机场”，虽然这两个句子中都出现了“姚明”和“叶莉”，但却都没有表达出“老婆”的关系，在远程监督中仍将被视为一个正例。因此，Riedel等人[10]采取多示例问题的处理办法，将一个关系所标记的所有句子看作是一个集合，并假设集合中至少有一个句子能表达出两个实体所对应的关系，从而有效的减少了冗杂数据对应远程监督的影响。文献[11]提出了基于概率图模型的多实例多标签模型，不仅对噪声训练数据进行建模，而且针对实体对和所属关系进行多分类建模，实验结果表明该模型在关系抽取效果上有了比较显著的提高。Liu 等人[12提出一种基于卷积神经网络的弱监督关系抽取方法，将关系抽取技术运用到特定的领域中。他们构建了半自动化模式抽取系统EARES，通过该系统生成训练语料，转换成向量特征矩阵，最后使用卷积神经网络（CNN）进行分类模型训练实现关系提取。Santos等人[13]提出了一种在没有手工特征的情况下使用深度神经网络进行关系分类的方法，该方法是基于句子构建分类器，由于缺乏人工注释的训练数据，不能在大规模的知识库中应用。Zeng等人[14]将多实例学习与神经网络模型相结合，建立了基于远程监督的关系提取器，虽然该方法在关系提取方面取得了显着的改进，但是效果还远远不能令人满意。

注意力机制和人类的选择性视觉注意力机制类似，核心目标也是从众多信息中，通过计算概率分布，选择出对当前任务目标更关键的信息。文献[15]在使用RNN模型做图像分类时，加入了注意力机制，之后Bahdanau 等人[6使用类似的注意力机制在机器翻译任务上，将翻译和对齐同时进行，这也是注意力机制首次应用到NLP领域中。Lin等人[17提出了一种基于远程监督关系提取的方法，使用CNN来提取句子特征，之后为解决错误的标签问题，构建句子层面的注意力机制。

# 2 关系抽取模型GRU_ATT

模型总体结构如图1所示，首先得到包含同一对实体的所有句子集合 $S = \{ s _ { 1 } , s _ { 2 } , s _ { 3 } , . . . , s _ { n } \}$ ，将 $s _ { i }$ 转化成向量表示 $x _ { i }$ ，再使用GRU来提取句子的语义，得到句子的语义特征向量 $X _ { i }$ 之后，再通过注意力机制计算得到相应的权重 $\theta _ { i }$ ，最后将句子的语义特征向量点乘它们的权重 $\theta _ { i }$ 再求和，得到集合 $s$ 的向量表示Sv。

![](images/794723a02d090cbd67f90eaeb1b0839c9cfdc10a1f75a3867dd6b744ff8f12dd.jpg)  
图1基于注意力机制和GRU神经网络的关系抽取模型

# 2.1 向量化

2.1.1词向量化

给定一个由t个单词组成的句子 $s = \{ w _ { 1 } , w _ { 2 } , w _ { 3 } , . . . w _ { t } \}$ ，运用word2vec[18]将每一个单词 $w _ { i }$ 映射到一个低维实值向量空间中，将句子中的每个单词的向量拼接起来形成句子的向量。通过式（1）对句子进行词向量处理。

其中： $e _ { i }$ 是词 $w _ { i }$ 的向量形式, $W ^ { w o r d } \in R ^ { d ^ { w } | m | }$ 是句子的向量矩阵，其中 $\mathrm { ~ m ~ }$ 是一个固定尺寸的单词表， $d ^ { w }$ 表示词向量的维数， $\boldsymbol { V } ^ { i }$ 是词 $w _ { i }$ 的one-hot表示。最终得到句子中每个单词的向量化表示：  
$V _ { s } = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . x _ { t } \} _ { \mathrm { ~ c ~ } }$ 0

# 2.1.2位置向量化

在关系抽取的任务中，往往靠近实体的单词更能突显出句子中两个实体之间的关系，因此为了能够更加准确地表达句子的含义，将句子中每一个单词到两个实体的距离拼接到该单词的词向量表示中。若在句子向量化中，词向量化的维度为 $d ^ { w }$ ，位置向量化的维度为 $d ^ { p }$ ，则句子向量的维度为

$$
\boldsymbol { d } ^ { s } = \boldsymbol { d } ^ { w } + 2 \boldsymbol { d } ^ { p }
$$

例如"Beijingis the capitalofChina"向量化如图2所示，在这个句子中"Beijing"和"China"作为两个实体，那么"is"到“Beijing"的距离的为-1，到"China"的距离为4；“the"到"Beijing"的距离为-2，到"China"的距离为3。

![](images/dbeb8806584656e674f850e8b5daa62ef0e6e434e044aea6dafa929c149eb98b.jpg)  
图2句子向量化

# 2.2 构建GRU

LSTM（long short termmemory）是一种改进的RNN，可以学习长期依赖信息，由Hochreiter& Schmidhuber在1997年提出，最近又被AlexGraves 进行了改良和推广。GRU[19]是LSTM的一种变体，保持了LSTM的效果，同时又使结构更加简单，减少了训练参数，提高了模型训练的速率。

LSTM是一种复杂的网络结构，包含三个门计算即忘记门、输入门和输出门。三个门计算用来增加或者减少细胞状态中的信息，GRU 将LSTM 中的忘记门和输入门合成为一个单一的更新门，同时还混合了细胞状态和隐藏状态，更新门用于控制前一时刻的信息是否被带入到当前细胞状态中，GRU结构如图3所示。

![](images/c77fb202106c5259f2e315dd809a8e911f62639d4ad3b589e75ac6941c639284.jpg)  
图3 GRU模型

将上一节中得到的句子的向量化表示作为该步输入，以第$i$ 个单词为例，说明第 $i$ 个单词在GRU单元各个状态的特征值：

$$
z _ { t } = r e c ( W _ { h z } h _ { t - 1 } + W _ { x z } x _ { t } + b _ { z } )
$$

$$
r _ { t } = r e c ( W _ { h r } h _ { t - 1 } + W _ { x r } x _ { t } + b _ { r } )
$$

$$
\widetilde { h } _ { t } = \operatorname { t a n h } ( W _ { r h } r _ { t } h _ { t - 1 } + W _ { w x } x _ { t } + b _ { h } )
$$

$$
h _ { t } = ( 1 - z _ { t } ) \ast h _ { t - 1 } + z _ { t } \ast \widetilde { h } _ { t }
$$

其中：rec 激活函数选用relu 函数， $x _ { t }$ 表示当前时刻的输入， $h$ 表示记忆体， $W$ 表示权值矩阵， $b$ 表示偏置量。

# 2.3 引入注意力机制

假设包含实体对 $< e _ { 1 } , e _ { 2 } >$ 所有句子的集合$S = \{ s _ { 1 } , s _ { 2 } , s _ { 3 } , . . . , s _ { n } \}$ ，本小节中为了充分利用集合中每一个句子的信息，引入注意力机制来计算注意力概率，从而体现集合中某一个句子对于集合的重要程度。假设现在判断实体对$< e _ { 1 } , e _ { 2 } >$ 是否具有关系矢量 $\boldsymbol { r }$ ，那么集合 $s$ 中的每一个句子 $s _ { i }$ 都包含了该句子是否表达了 $\textbf { \textit { r } }$ 关系的信息，首先，将集合 $s$ 转化为向量的形式 $S _ { \nu }$ ，计算公式如下：

$$
{ { S } _ { \nu } } = \sum _ { i } { { { \beta } _ { i } } } { { { x } _ { i } } }
$$

$\beta _ { i }$ 表示句子 $x _ { i }$ 的权重。为了验证注意力机制的引入给实验结果带来的影响，用两种方式定义 $\beta _ { i }$ ：第一种，令 $\beta _ { i } = \frac { 1 } { n }$ ，也就是说，认为集合中所有的句子对于表达关系 $\textbf { \textit { r } }$ 都同等重要。显然，这样是不合理的，因为集合中总会有句子不表达关系 $\textbf { \textit { r } }$ 这种冗杂数据就会给实验的结果产生不好的影响。第二种，为了避免这种情况的发生，减小这种噪音数据对实验结果的影响，准确给出集合中每个句子的权重，首先定义一个关于 $s _ { i }$ 和 $\textbf { \textit { r } }$ 的函数：

$$
s c o r e s ( i ) = s _ { i } A r
$$

该函数描述集合中某一个句子 $s _ { i }$ 与预测关系 $\textbf { \em r }$ 之间的匹配程度,将该函数的取值范围定义在[0,1]，0表示某个句子 $s _ { i }$ 完全不可能表达 $r$ 关系；相反，1表示某个句子一定会表达 $\boldsymbol { r }$ 关系。$A$ 为一个对角矩阵。接下来将式（8）通过softmaxfunction 就得到第 $i$ 个句子在集合中的权重：

$$
\beta _ { i } = \frac { \exp ( s c o r e s ( i ) ) } { \sum _ { k } \exp ( s c o r e s ( k ) ) }
$$

接着将式(9)代入式(7),就得到了集合 $s$ 的向量形式:

$$
S _ { \nu } { = } { \sum _ { i } } { \frac { \exp ( s c o r e s ( i ) ) } { { \sum _ { k } } \exp ( s c o r e s ( k ) ) } } x _ { i }
$$

再得到 $\boldsymbol { S } _ { \nu }$ 后，接下来定义一个线性函数就可以计算每一个可能的关系 $\mid r \mid$ 的得分：

$$
\boldsymbol { y } = \boldsymbol { M } \boldsymbol { S } _ { \nu } + \boldsymbol { b }
$$

M是一个关系矩阵， $b$ 是一个偏置量。

# 2.4模型训练与优化求解

采用最小化负对数似然函数来进行模型训练，接着将式（11）通过softmax层定义条件概率如下：

$$
P ( r | S , \alpha ) { = } \frac { \exp ( y _ { r } ) } { { \sum } _ { j = 1 } ^ { n _ { r } } \exp ( y _ { j } ) }
$$

$n _ { r }$ 表示所有可能的关系。接下来采用随机梯度下降算法来最小化负对数似然函数，定义优化目标函数 $J ( \alpha )$ 计算如下：

$$
J ( \alpha ) = - \sum _ { i = 1 } ^ { D } \log p ( r _ { i } | S _ { i } , \alpha ) = - \sum _ { i = 1 } ^ { D } \log ( \frac { \exp ( y _ { r _ { i } } ) } { \sum _ { j = 1 } ^ { n _ { r } } \exp ( y _ { j } ) } )
$$

其参数 $\alpha ( M , b , A )$ 表示模型训练参数，初始值随机给定。 $D$ 表示训练样本数。

# 3 相关工作实验结果

# 3.1实验数据与实验环境

实验环境：操作系统windows7,64位；处理器Intel(RCoreTMi5-4690；内存大小为8GB；编程平台Pycharm，Python2.7版本。

实验数据：本次实验采用的数据集，是通过将Freebase中的实体对与纽约时报语料库（NYT）对齐而生成的。该数据集[0]是Riedel在2010 年首次开发使用的，之后也被RaphaelHoffmann、MihaiSurdeanu、Lin等人使用，该数据集使用斯坦福大学的命名实体识别工具对纽约时报语料库进行实体标注，然后再与Freebase中的实体进行匹配，生成数据集格式如表1所示。第一列中的两行分别表示第一个实体和第二个实体的id，第二列中的两行分别表示两个实体，第三列表示关系，第四列表示句子。假设（Hunan，contains，changsha）就是表示Freebase中的一条三元组数据：“one reason is that hunan's fast-growingprovincial capital changsha is beginning to siphon some workers "就是纽约时报语料库的一个句子，将Hunan和changsha与句子中相同实体对应起来就行了一条数据。

该数据集包含特殊关系NA（NA：句子中的两个实体没有任何关系)在内，一共53种关系、39528个实体。训练集包含522611个句子，281270个实体对，18252个关系事实；测试集包含172448个句子，96678个实体对，1950个关系事实。

表1数据集格式  

<html><body><table><tr><td>实体 Aid/ 实体Bid</td><td>实体A/ 实体B</td><td>关系</td><td>句子</td></tr><tr><td>m.01669t/</td><td></td><td></td><td>one reason is that hunan's fast-growing provincial capital</td></tr><tr><td>m.01cw6l</td><td>Hunan/ changsha</td><td>../contains</td><td>changsha is beginning to siphon</td></tr><tr><td rowspan="5">m.0dlw0/ m.03rjj</td><td rowspan="5">Umbria/ italy</td><td rowspan="5">../country</td><td>some workers</td></tr><tr><td>it echoed the insistence of his</td></tr><tr><td>grandfather an immigrant from</td></tr><tr><td>umbria in italy that nary a word of</td></tr><tr><td>italian be heard in the family's new</td></tr><tr><td rowspan="4">m.045c7b/m.01cw6</td><td></td><td></td><td>home in nice</td></tr><tr><td rowspan="3">Google/</td><td rowspan="3">NA</td><td>Since it bought youtbe last october</td></tr><tr><td>google has been chasing deals that</td></tr><tr><td>would give it the right to put</td></tr><tr><td></td><td>youtube</td><td></td><td>mainstream video programming on the site.</td></tr></table></body></html>

# 3.2评测指标

本文通过采集准确率（precision）、召回率（recall）绘制PR 曲线，作为评价指标。准确率、召回率计算公式如下：

$$
p r e c i s i o n \mathrm { = } \frac { r i g h t \_ n u m } { o u t }
$$

$$
r e c a l l = \frac { r i g h t \_ n u m } { a l l }
$$

right_num表示模型预测正确的数据条数；out表示一共预测的数据条数；a表示测试集总共的数据条数。在准确率相同的情况下召回率越高越好，在召回率相同的情况下准确率越高越好，因此PR曲线越在右上方指标越好。

# 3.3参数设置

采用Softmax作为分类器。采用L2正则化方法对网络参数进行约束，训练过程引入了采用dropout 策略，采用批量的Adadelta优化方法用于模型训练，具体参数设置如表2所示。

表2参数设置  

<html><body><table><tr><td>Vocab_size</td><td>16691</td></tr><tr><td>Steps_num</td><td>70</td></tr><tr><td>Classes_num</td><td>12</td></tr><tr><td>Gru_size</td><td>230</td></tr><tr><td>Layers_num</td><td>1</td></tr><tr><td>Epochs_num</td><td>10</td></tr><tr><td>Dropout_rate</td><td>0.5</td></tr></table></body></html>

# 3.4实验结果与分析

# 3.4.1与现有方法比较

首先将GRU_ATT与传统基于特征的关系抽取方法相比较得到图4所示实验结果。红色曲线代表GRU_ATT的实验结果；绿色曲线是Mintz[9]，2009年提出的传统基于远程监督的关系抽取模型。黑色曲线是MultiR[20]，2011年Hoffmann 提出的处理重复关系的多实例学习模型。在整个召回范围内，GRU_ATT都好于Mintz与MultiR两种基于特征的方法。Mintz和MultiR在召回大于0.2左右的时候开始迅速下降，而GRU_ATT在整个过程中都相对稳定，这表明通过人工设计的特征不能够准确的表达出句子的语义。

![](images/bc89be17d8ad4356bc1938b49efc5509d6478b0051fbe2dec0c44f619d4db76b.jpg)  
图4GRU_ATT与传统基于特征的方法比较

为了显示GRU模型的优势，将该方法与2015年Lin 提出了一种基于远程监督关系提取的方法[I7CNN_ATT 相比较，他们通过CNN来提取句子特征，之后为解决错误的标签问题，构建句子层面的注意力机制。GRU_ATT与CNN_ATT对比实验结果如图5所示。

![](images/2d0fd869c12b45a0784e1c58681cadd67d74806ac30dd9ce09f3fca3ec1464d1.jpg)  
图5GRU_ATT与CNN_ATT对比实验结果

黑色线条是CNN_ATT，红色线条是GRU_ATT。在该任务中，CNN只能抽取位置不变的特征，不能学习时序序列。而GRU因为有了记忆模块，能够充分利用整个句子的序列信息，包括各个词之前的关联信息，更适合自然语言处理的任务。因此，由实验结果可以看出，GRU_ATT要好于CNN_ATT。

# 3.4.2注意力机制对实验结果产生的影响

该实验部分是为了验证注意力机制的引入给实验结果带来的影响。设定三个模型，第一个模型只采用GRU，不引入注意力机制；第二个模型采用 GRU_AVE，也就是 $\beta = \frac { 1 } { n }$ ，将同对实体对的所有句子的权重都看做一样；第三个模型就是GRU_ATT，对比实验结果如图6所示。

![](images/60aea2034f05f9d310abf68da30c44f343f554eb7307391f311cc849e7b44d54.jpg)  
图6注意力机制对实验结果的影响

红色线条代表GRU_ATT；黑色线条代表GRU_AVE；绿色线条GRU。GRU_AVE引入注意力机制，考虑了句子表达的意义，从而减小了冗杂数据对于实验结果的影响，而GRU没有引入注意力机制，完全不考虑噪声数据的影响，因此GRU_AVE的实验结果要好于GRU。但是GRU_AVE将所有的句子都看做是平等的，因此也会带入一些冗杂数据，那些表达错误关系的句子就对实验结果产生了负面的影响。GRU_ATT在整个召回范围实现了最高的精度，这表明注意力机制的引入可以有效的减小远程监督中冗杂数据对于实验结果的影响。

# 4 结束语

本文提出了一种新的神经网络模型GRU_ATT，用于文本关系提取。该模型克服了传统深度学习模型无法解决长距离依赖问题，大大减小了人工对数据标记所耗费的时间和精力，减小了冗杂数据对于实验结果的影响。在公共语料库上的实验结果，PR曲线也有所提高。尽管由于注意力机制的引入，是减小了冗杂数据对于实验结果的影响，但该问题并没有完全解决。下一步工作，将着重考虑如何在开放领域自动发现关系，进行关系抽取。

# 参考文献：

[1]赵妍妍，秦兵，车万翔，等．中文事件抽取技术研究[J]．中文信息学报,2008,22(1): 3-8.(Zhao Yanyan,Qin Bing,Chen Wanxiang,Liu Ting,et al.Research on Chinese Event Extraction [J].Journal of ChineseInformation Processing,2008,22(1):3-8.)  
[2]陈宇，郑德权，赵铁军．基于DeepBeliefNets 的中文名实体关系抽取[J]．软件学报，2012,23(10):2572-2585.(Chen Yu，Zheng Dequan+,

Zhao Tiejun.Chinese Relation Extraction Based on Deep Belief Nets [J]. Journal of Software,2012,23(10):2572-2585.)

[3]Huang Xun, You Hongliang,Yu Yang.A Review of Relation Extraction [J]. NewTechnologyof Library and Information Service,2O13 (11): 30-39   
[4]Kurt B, Colin E,Praveen P,etal. Freebase: acollboratively created graph database for structuring human knowledge [C]// Proc of KDD.2008: 1247-1250.   
[5]Lehmann J.DBpedia:a nucleus for a web of open data [C]// Proc of Semantic Web, International Semantic Web Conference,Asian Semantic Web Conference. 2007: 11-15.   
[6]Hochreiter S,Schmidhuber J.Long short-term memory.[J].Neural Computation,1997,9(8): 1735.   
[7]Rink B,Harabagiu S. UTD: classifying semantic relations by combining lexical and semantic resources [C]// Proc of International Workshop on Semantic Evaluation.Association for Computational Linguistics. 2010: 256-259.   
[8]Kambhatla,N. Combining lexical,syntactic,and semantic features with maximum entropy models for extracting relations [C]// Interactive Poster and Demonstration Sessions. Stroudsburg:Association for Computational Linguistics, 2004: 22.   
[9]Mintz M, Steven B,Rion S,et al.Distant supervision for relation extraction without labeled data [C]// Proc of Joint Conference of the Meeting of the ACL and the,International Joint Conference on Natural Language Processing of the Afnlp:Volume. Stroudsburg:Association for Computational Linguistics,2009: 1003-1011.   
[10] Riedel S,Yao Limin, Mccallum A.Modeling relations and their mentions without labeled text [C]// Procof European Conferenceon Machine Learning and Knowledge Discovery in Databases.Springer-Verlag,2010: 148-163.   
[11] Surdeanu M,Tibshirani J,NallapatiR,et al.Multi-instance multi-label learning for relation extraction [C]//Proc of Joint Conference on Empirical Methods in Natural Language Processing and Computational Natural Language Learning. 2010: 455-465.   
[12]刘凯，符海东，邹玉薇，等．基于卷积神经网络的中文医疗弱监督关系 抽取[J].计算机科学，2017,44(10):249-253.(Liu Kai,Fu Haidong, Zou Yuwei, Gu Jinguang,et al. Chinese medical weak supervised relation extraction based on convolution neural network [J]. Computer Science, 2017,44 (10): 249-253.)   
[13] Santos CND, Gatit M. Deep convolutional neural networks for sentiment analysisof short texts[C]// Proc of International Conferenceon Computational Linguistics.2014   
[14] Zeng Daojian,Liu Kang,Chen Yubo,et al.Distant supervision for relation extraction via piecewise convolutional neural networks [Cl// Proc of Conference on Empirical Methods in Natural Language Processing. 2015: 1753-1762.   
[15] Mnih V, Heess N,Graves A,et al. Recurrent models of visual attention

[EB/OL].(2014-12-03）．https://papers.nips.cc/paper/5542-recurrentmodels-of-visual-attention. pdf.

[16] Bahdanau D,Cho K,Bengio Y.Neural machine translation by jointly learning to align and translate [J]. Computer Science,2014.

[17]Lin Yankai, Shen Shiqi,Liu Zhiyuan,et al.Neural relation extraction with selective attention over instances [C]//Proc ofMeeting of the Association for Computational Linguistics.2016: 2124-2133.

[18] Mikolov T, Sutskever I,Chen Kai,et al.Distributed representations of words and phrases and their compositionality [EB/OL].(2014-11-25）. https://papers.nips.cc/paper/5o21-distributed-representations-of-words-and -phrases-and-their-compositionality. pdf.

[19]Dey R,SalemtFM.Gate-variants of Gated Recurrent Unit (GRU) neural networks [C]//Proc of IEEE nternational Midwest Symposium on Circuits and Systems.2017:1597-1600.

[20]Hoffmann R,Zhang Congle,Ling Xiao,et al.Knowledge-based weak supervision for information extraction of overlapping relations [C]//Proc of the Association for Computational Linguistics: Human Language Technologies. Stroudsburg:Association for Computational Linguistics, 2011: 541-550.