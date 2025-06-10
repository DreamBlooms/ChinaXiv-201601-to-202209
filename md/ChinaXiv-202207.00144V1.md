# 面向低资源命名实体识别的CharBiLSTM-Att-CRF模型

钟茂生 吴佳华江西师范大学计算机信息工程学院

摘要：当标注数据较少时，现有模型受训练数据量少的限制，参数没有拟合到预期效果，导致在低资源命名实体识别任务中模型识别性能不佳。本文通过采用K折交叉验证法，使模型较好拟合数据。此外，本文在 BiLSTM-CRF 模型基础上融合多层字符特征信息和自注意力机制，结合K折交叉验证法，构建了CharBiLSTM-Att-CRF模型。本文提出的CharBiLSTM-Att-CRF 模型在 $2 0 \%$ 的 CONLL2003 和 $2 0 \%$ 的 BC5CDR 的数据集上，F1值在 BiLSTM-CRF 模型基础上分别提升了 $7 . 0 0 \%$ 、 $4 . 0 8 \%$ 。该模型能较好地适应低资源命名实体识别任务。

关键词：低资源命名实体识别；神经网络;K折交叉验证法;自注意力机制

# CharBiLSTM-Att-BCRF Model for Low Resource Named Entity Recognition

ZhongMaosheng,WuJiahua School of computer information engineering, Jiangxi Normal University

Abstract:whentherearefewlabeleddata,theexisting modelsarelimitedbytheamountoftrainingdata,andtheparametersdonot fittheexpectedefectresutinginporodelrecognitioperformanceintetaskoflowresourceamedetityrecognitio.anwloss functionintegratedwithBeroulidistributionispropoedtomaketeodelfit thedatabeterInaddition,basedontheB-CRF model,thispaerintegatesulti-archaracterfeatureinformationndselftetionmechanism,andtewlssfunctionbasedon Bernoulli distribution is combined to construct the BiLSTM-At-BCRF model.Based on the dataset of $20 \%$ CONLL2003 and $20 \%$ （20 BC5CDR, the F1 value of the BiLSTM-BCRF model proposed in this paper increased by $7 . 0 0 \%$ and $4 . 0 8 \%$ respectively. the model can better adapt to the task of low resource named entity recognition.

Keywords:Low resource named entity recognition；Neural network；Bernouli distribution；selfattntion mechanism

# 1引言

命名实体识别是自然语言处理的基础任务之一，该任务旨在从非结构化的文本中自动识别出实体，并将其标记为预定义的类别，例如人名、地名和组织机构名等。例如，“张无忌，金庸武侠小说《倚天屠龙记》人物角色，中土明教第三十四代教主。”这句话包含的实体有：人名实体“张无忌，金庸”，书名实体“倚天屠龙记”，门派实体“明教”。由此可见,实体识别是文本语义理解的基础。同时命名实体识别技术在知识图谱构建、机器翻译、知识库构建等多种自然语言处理任务中有着广泛应用。

近些年来，深度学习方法被广泛用于命名实体识别，如 Hammerton将长短期记忆网络(LSTM)应用到实体识别研究中，LSTM-CRF 结构成为实体识别的基础结构。Lample 等人[2]在LSTM-CRF 模型的基础上，提出双向长短期记忆网络(Bi-LSTM)和条件随机场(CRF)结合的模型[3-5]等。这类方法虽然在文本实体识别任务中表现优异，但是需要大规模的标注数据，对训练语料中每个词进行人工标注。在标注数据不足的情况下，现有模型的参数不能较好拟合，导致模型预测最大概率标签并不一定是真实标签，模型的识别性能下降，很难应用到如生物、医学这些标注语料较少的领域。针对上述问题，本文通过采用K折交叉验证法，使模型参数在低资源场景下能较好拟合。在此基础上，为增加模型能处理的词汇量和提升模型识别罕见词的能力，本文在BiLSTM-CRF 模型基础上融合多层字符特征信息，构建了CharBiLSTM-CRF 模型。在CharBiLSTM-CRF 模型基础上融合了自注意力机制，获取关键信息隐藏状态表示，构建了CharBiLSTM-Att-CRF 模型,进一步提升了模型的精确率和召回率。

本文的组织结构为：第二节介绍低资源命名实体识别领域的主要工作。第三节介绍本文模型，包括：输入层、BiLSTM层、自注意力层和CRF 层。第四节介绍实验数据、实验内容、实验结果及分析。最后对本文工作进行总结。

# 2相关工作

命名实体识别的研究方法主要有基于规则和词典方法、机器学习方法、深度学习方法等。基于词典和规则的方法过多依赖于语言学家制定的规则模板，容易产生错误，移植性差。传统机器学习方法主要包括：隐马尔可夫模型(Hidden Markov Model,HMM)、最大熵(Maximum Entropy,ME)[]、最大熵马尔可夫模型(Maximum EntropyMarkov Model,MEMM)[7]、条件随机场（Conditional Random Fields,CRF)[8]等。这些传统的机器学习方法在特征提取方面需要人工参与，同时需要大规模的标注语料来训练模型，方法的性能主要依赖于所采用的特征是否具有辨识度。其中CRF 被看作是命名实体识别的主流模型,优点在于在对一个位置进行标注的过程中CRF 可以利用内部及上下文特征信息。随着深度学习的不断发展，命名实体识别的研究重点已转向深层神经网络，Collobert 等学者[]首次提出基于神经网络的命名实体识别方法,该方法中每个单词具有固定大小的窗口,但未能考虑长尾问题。为了克服这一限制,Chiu 和Nichols[1]提出一种双向LSTM-CNNs 架构，该架构可自动检测单词和字符级别的特征。Hammerton[利用 CRF 关注上下文特征信息的特点，提出LSTM-CRF 模型。

近些年来,大量的深度学习方法被应用于低资源命名实体识别任务中，低资源的命名实体识别技术成为当前研究热点之一，其性能的提高是命名实体识别技术走向广泛实际应用的前提。相关研究工作可大致分为以下几类：跨语言迁移的方法、数据增强的方法、集成自动标注语料的方法和其他方法。

跨语言迁移方法的基本思路是利用资源丰富语言的标注数据帮助低资源语言进行命名实体识别，可大致分为数据迁移的方法和模型迁移的方法两大类。基于数据迁移的方法通常借助文本翻译和标签映射等手段把源语言中的标注数据转换成目标语言的标注数据，然后基于这些数据训练模型。Ni等[I提出了一种在语料库上进行标签映射的方法，用于创建自动标记的目标语言数据。Mayhew等[12]利用双语词典，使用一种类似短语机器翻译[13]的方法自动翻译源语言的标注文本。基于模型迁移的方法通常先学习语言无关的特征，然后在源语言的标注语料上训练NER模型直接用于目标语言。Chen 等[14同样基于对抗学习的方法提取语言无关的特征，并动态地计算源语言和目标语言之间的相似度，从而更有效地实现从多个源语言到目标语言的知识迁移。Keung 等[15]在多语言版本 BERT的基础上进一步使用对抗学习[的方法，以学习更好的与语言无关的特征。

数据增强方法的主要目标是，在不增加人工标注成本的前提下,通过增加合理的噪声来提升模型的鲁棒性，在少数据量的场景下对模型性能的提升有很大帮助。Dai等[17]引入了一些词替换的随机操作来增加训练语料多样性;Chen 等[18]在半监督 NER 任务中引入了基于局部可加性的数据增强。基于语言迁移的方法和数据增强的方法虽然能够有效地缓解标注语料短缺的问题，但是具有丰富标注资源的语言是非常少的。

一些研究者提出集成自动标注语料的方法，首先通过某种方法自动标注大量语料，然后集成它们用于提高低资源实体识别模型的性能。Yang等[9]首先基于词典匹配的方法自动标注语料，然后使用Partial-CRF[20]在少量人工标注的语料和大量自动标注的语料上训练实体识别模型。此外，他们还基于强化学习[21训练一个选择器，用于筛选掉具有噪声的标注数据。

除上述三类方法外，低资源实体识别领域还有其他方法如 Zhang 提出渐进式知识提炼方法 PDALN[22]，有效的将高资源域适应于低资源目标域。Chen提出了一种低资源的语言模型的微调方法[23]，使用基于注意力机制的微调策略，从预训练的语言模型中选择相关的语义和句法信息，将其应用于命名实体识别任务。本文的工作主要是探索低资源条件下基于深度学习的命名实体识别方法。

# 3模型

# 3.1基本架构

命名实体识别任务被看作是序列标注问题。输入句子表示为 $\mathbf { x } = ( x \quad ^ { 1 } , x \quad ^ { 2 } , \cdots , x \quad ^ { i } \quad ) ,$ 其中 $x$ i表示第i个字符(包括数字、单词、字母或标点符号等)。输出标注序列为 $\mathbf { y } = { \left( y \quad \begin{array} { l l l l l } { 1 , y } & { 2 , \cdots , y } & { 1 } & { } \end{array} \right) } $ 其中$\begin{array} { r l } { \boldsymbol { y } } & { { } ^ { i } \ } \end{array} \in \{ \mathrm { B } , \mathrm { M } , \mathrm { E } , \mathrm { S } , 0 \}$ 是 $x$ i的标签,B、M、E、S 和0分别代表实体首字,实体中间字,实体结尾字,实体单独字和非实体。命名实体识别就是对每个字符进行B、M、E、S、0的分类标注。

本文通过采用K折交叉验证法，使模型参数在低资源场景下能较好拟合，同时为增加模型能处理的词汇量和提升模型识别罕见词的能力，将多层字符信息融合到 BiLSTM-CRF 模型，构建了CharBiLSTM-CRF 模型。在CharBiLSTM-CRF 模型基础上，融合自注意力机制，获取关键信息隐藏状态表示，构建了CharBiLSTM-Att-CRF模型。CharBiLSTM-Att-CRF 模型基本结构如图1所示。该模型结构主要分为输入层、Bi-LSTM层、自注意力层和 CRF层。

![](images/487a71dc6317552babc0ff624de65addf6e28414afc7298238a2c29627171574.jpg)  
图1CharBiLSTM-Att-CRF模型基本结构

# 3.2输入层

如图2所示，该图为模型输入层的结构图。其中，x表示词向量，是使用Pennington等人提出Glove 英文词向量[24]文件生成的, $c$ 1,C2表示字符; $\mathbf { m } , m$ 1表示由 BiLSTM 训练生成的字符向量, $\begin{array} { r l } { \mathbf { \tilde { \Sigma } } } & { { } = [ x \quad : m } \end{array}$ （20;m $_ 1 ]$ 。最后将词向量与字符向量拼接输入到 BiLSTM 层。

![](images/87b6f26c5161aaca014355430921f06e8238d1d25f5000ae155216d91a1cc72b.jpg)  
Figure1basic structure ofCharBiLSTM-Att-CRF model   
图2模型输入层基本结构图  
Fig.2 basic structure of model input layer

# 3.3BiLSTM层

LSTM 神经网络在命名实体识别任务中表现出良好的建模能力，能较好的学习文本中单词与字符的特征信息，BiLSTM 层结构主要由两个LSTM组合而成。LSTM的网络结构主要分三个阶段：遗忘阶段、选择记忆阶段、输出阶段。LSTM单元结构如图3所示，itft0t分别表示LSTM单元中

![](images/d467383615da43f3c690f945eff34b0f7aa3d61c2f8f184f78e37cbe185e7f0c.jpg)  
图3LSTM单元结构图  
Figure 3 structure diagram of LSTMunit

的输入门、遗忘门、输出门在 t 时刻的状图态。 $h _ { t }$ $^ { - 1 }$ 表示在 $_ \mathrm { t - 1 }$ 时刻的隐藏状态, $c$ t表示在t时刻的细胞记忆状态。σ表示 Sigmoid，tanh 表示双曲正切激励函数,如式 $( 1 ) \sim$ 式(6)所示：

$$
\begin{array} { r l r l r l r l r l r l } { i } & { { } } & { \mathrm { ~  ~ \gamma ~ } _ { t } } & { { } = \sigma } & { ( W } & { { } _ { x } } & { } & { { } x } & { { } _ { t } } & { { } + W } & { { } _ { h i } } & { { } h _ { t } } & { { } _ { - 1 } + b } & { { } _ { i } } & { { } ) } \end{array}
$$

$$
\begin{array} { r } {  { f } _ { \mathbf { \Gamma } _ { t } } (  { \mathbf { \Sigma } } _ { t } ^ { } ) = \sigma \quad ( W \textnormal { \texttt { f } } _ { h } h _ { t } \\ { \mathbf { \Sigma } } _ { - 1 } + W \textnormal { \texttt { f } } _ { { \mathbf { \Sigma } } } \times  { \mathbf { \Sigma } } _ { t } ^ { } + b \textnormal { \texttt { \textbf { f } } } ) } \end{array}
$$

$$
\begin{array} { r l } { h _ { t } } & { { } = o _ { \mathrm { ~ \Delta ~ } _ { t } } \odot t  { a n } \qquad h ( c _ { \mathrm { ~ \Delta ~ } _ { t } } ) } \end{array}
$$

BiLSTM 神经网络中的输出隐藏状态 $\begin{array} { r l } { h _ { t } } & { { } = [ \overrightarrow { h _ { t } } \quad ; \overleftarrow { h } _ { t } \quad ] , \overrightarrow { h } _ { t } } \end{array}$ 和 $\overleftarrow { h } _ { t }$ 分别为前向输出和后向输出。

# 3.4自注意力层

自注意力层的功能是给予上下文的局部信息，使模型加强对重要信息的捕捉，减少非必要信息的噪声影响。将重点放在序列的特定部分，同时不丢弃编码器状态的中间值，而是利用它生成上下文向量，以便解码器给出输出结果，自注意力机制公式如式（7）所示：

$$
\mathrm { H } = \mathrm { s o f t m a x } ( W _ { \mathrm { ~ \scriptsize ~ 2 ~ } } \operatorname { t a n h } \left( W _ { \mathrm { ~ \scriptsize ~ 1 } } h _ { t } \right) )
$$

其中，W $_ 1 W$ $_ 2$ 为权重参数， $h _ { t }$ 是BiLSTM层输出的隐藏状态。

# 3.5 CRF层

模型解码层主要是条件随机场(Conditional Random Field，CRF)。CRF 是由状态特征函数和状态特征转移函数组成，状态特征函数也称发射概率，状态特征转移函数在模型中可以用一个状态转移矩阵表示，最后得到的条件概率如式(8)所示：

其中， $\Phi ( x , y )$ 是 $\mathrm { ~ x ~ }$ 和 $\mathrm { \Delta y }$ 一组特征向量的映射。 $\mathbf { p } ( \mathbf { y } \vert \mathbf { x } )$ 表示模型在给定文本序列 $\mathrm { ~ x ~ }$ 条件下得到标签序列y的概率。损失函数计算公式如式(9)所示：

$$
\begin{array} { r } { \mathrm { L } ( \mathbf { w } , \mathbf { x } ) = - \sum _ { i } \textbf { \textit { l o g } } \qquad \mathrm { p } ( \mathbf { y } | \mathbf { \boldsymbol { x } } \mathbf { \beta } ^ { ( i ) } , \mathbf { w } ) } \end{array}
$$

CRF方法的优点是可以进一步考虑序列标签的依赖关系，同时在训练过程中，采用Viterbi算法用于最大似然估计，使模型对输入文本预测出标签的最大概率如式(10)所示：

$$
\begin{array} { r l } { y } & { { } = a \ r \ g \ m a \ x } \end{array}
$$

其中， $y$ 表示模型预测标签的最大概率。但是在低资源的场景下，模型受标注数据量少的限制，参数没有拟合到预期效果，输出预测概率最大的标签序列并不一定是真实的标签序列，导致模型最后的识别性能下降。在此，本文借鉴 jie 等人[25]在不完全标注实体识别任务上采用交叉验证方式训练数据的思想，采用K折交叉验证法训练模型，使模型参数在低资源场景下也能较好地拟合。

K 折交叉验证法，就是将训练集 $\mathrm { D } = \{ D \ v { r } _ { \mathrm { ~ 1 ~ } } , D \ v { r } _ { \mathrm { ~ 2 ~ } } \cdots D \ v { r } _ { \mathrm { ~ \ v ~ { ~ k ~ } ~ } } \}$ 分为K份，每次训练时将其中(K-1)份做为训练集，剩余的1份做为验证集。将K份训练样本进行交叉训练和验证，可以有效地防止低资源场景下模型参数过拟合。本文经实验得知，当K值为2时模型识别效果较好。采用2折交叉验证法训练模型，在训练样本只有少量时，模型参数能较好拟合，提升模型的精确率和召回率，最后提高模型的识别效果。

# 4实验

# 4.1数据集及评价指标

本文选择CONLL2003[2]数据集和 BC5CDR[27]数据集来证明所提出模型的有效性。CONLL2003 数据集包含4种实体类型以及英语和德语两种语言，BC5CDR 数据集包含两种实体和1500 篇医药文章。由于实体识别的任务主要是对实体的边界和类别的识别，只有当边界及实体的类别都识别正确时，才判断正确。本文通过使用精确率(Precision)和召回率(Recall)来求得F1值，用于衡量该模型的性能，如式(13)～式(15)所示：

$$
\mathrm { P r e c i s i o n } = { \frac { M } { N } }
$$

其中N表示为模型所预测出的实体总数，M表示模型预测的实体中正确预测实体的总数，K表示为数据集中所标注的实体总数。模型中超参数设置如表1所示：

表1超参数设置Table 1 super parameter setting  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>隐层向量维度</td><td>200</td></tr><tr><td>词向量维度</td><td>100</td></tr><tr><td>字符向量维度</td><td>50</td></tr><tr><td>Dropout</td><td>0.5</td></tr><tr><td>学习率</td><td>0. 1</td></tr><tr><td>批尺寸</td><td>10</td></tr><tr><td>训练轮数</td><td>100</td></tr><tr><td>L2 正则化</td><td>1e-8</td></tr></table></body></html>

# 4.2实验结果与分析

本文所做的实验采用的数据集主要是CONLL-2003英语数据集和 BC5CDR专业医学领域数据集，CharBiLSTM-Att-CRF 模型、CharBiLSTM-CRF 模型与 BiLSTM-CRF 模型实验结果如图 4、图5所示：

![](images/40477d68ca39a22ae5dc5df6f23c0c87c6b803fd6152daf6102ce18bb4640ac3.jpg)

![](images/7d056c9bb76626db594e6ad609121c8122f98ab13f56a81972524f8d049f64ab.jpg)  
图4BC5CDR 数据集上CharBiLSTM-Att-CRF 模型、CharBiLSTM-CRF 模型与 BiLSTM-CRF 模型实验结果对比 4 Comparison of experimental results betwee CharBiLSTM-Att-CRF model CharBiLSTM-CRF model and BiLSTM-CR   
图 5CONLL2003 数据集上CharBiLSTM-Att-CRF 模型、CharBiLSTM-CRF 模型与 BiLSTM-CRF 模型实验结果对比

model on BC5CDR dataset

从图4、图5中可以看出该模型在少量标注数据集上的性能是高于BiLSTM-CRF 模型，比较适合低资源领域的实体识别任务。同时该模型在 $2 0 \%$ 的CONLL2003数据集上F1值达到了 $8 8 . 3 0 \%$ ，说明该模型在不需要大量的标注语料的情况下，也能取得比较好的识别效果。

TMN 是Lin 等人[28]在 2020 年提出的一种基于实体和触发词标注的命名实体识别模型。DualNER 是 Zhong 等人[29]在 2022 年提出的一种基于对偶学习和触发词标注的命名实体识别模型。CharBiLSTM-Att-CRF 模型与DualNER 模型、TMN 模型实验结果对比如表2、表3所示。

Table 2 Comparison of experimental results between CharBiLSTM-Att-CRF model and other mode   

<html><body><table><tr><td colspan="4">20%CONLL2003</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>82.17</td><td>80.35</td><td>81.30</td></tr><tr><td>TMN</td><td>85.65</td><td>85.38</td><td>85.51</td></tr><tr><td>DualNER</td><td>86.55</td><td>86.69</td><td>86.62</td></tr><tr><td>CharBiLSTM-CRF</td><td>87.49</td><td>88.63</td><td>88.06</td></tr><tr><td>CharBiLSTM-Att-CRF</td><td>88.28</td><td>88.31</td><td>88.30</td></tr></table></body></html>

如表2所示，该实验是在 $2 0 \%$ 的CONLL-2003数据集上进行的。从表中可以看出CharBiLSTM-Att-CRF模型F1值是高于DualNER 模型和TMN 模型的。

表2CharBiLSTM-Att-CRF模型与其他模型实验结果对比  
表3CharBiLSTM-Att-CRF模型与其他模型实验结果对比  

<html><body><table><tr><td colspan="4">20%BC5CDR</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>79.09</td><td>62.66</td><td>69.92</td></tr><tr><td>TMN</td><td>74.30</td><td>72.44</td><td>73.36</td></tr><tr><td>DualNER</td><td>76.06</td><td>73.66</td><td>74.84</td></tr><tr><td>CharBiLSTM-CRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr><tr><td>CharBiLSTM-Att-CRF</td><td>75. 45</td><td>72.60</td><td>74.00</td></tr></table></body></html>

如表3所示，在 $2 0 \%$ 的BC5CDR 数据集上，CharBiLSTM-Att-CRF 模型F1值比TMN 模型高 $0 . 6 4 \%$ ，比DualNER模型低 $0 . 8 4 \%$ ，主要是该模型识别一些专有名词的性能略低于DualNER 模型。但是，CharBiLSTM-Att-CRF 模型并不需要标注触发词，它所需要的人工成本只是TMN 模型和DualNER 模型的 $3 / 4$ ，同时CharBiLSTM-Att-CRF模型在CONLL2003数据集上F1值比DualNER 模型高 $1 . 6 8 \%$ 。当然，如何提高CharBiLSTM-Att-CRF 模型识别专有名词的性能，也是本文后续工作的重点。

# 4.3词与多层字符信息的融合分析

在3.2节中本文提出如图2所示的模型输入层结构，为验证在模型输入层哪些因素会影响模型进行命名实体识别的性能，本文在CharBiLSTM-CRF模型上进行如下实验：

able 3 Comparison of experimental results between CharBiLSTM-Att-CRF model and other m   
表4词向量与字符向量拼接顺序对模型性能的影响  
Table 4 explores the impact of word vector and character vector splicing order on model performance   

<html><body><table><tr><td colspan="4">20%BC5CDR 数据集</td></tr><tr><td>Method</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>word+char</td><td>71.82</td><td>72.50</td><td>72.16</td></tr><tr><td>char+word</td><td>71. 23</td><td>73.07</td><td>72. 14</td></tr><tr><td>CharBiLSTM-CRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr><tr><td>(word+char*2)</td><td></td><td></td><td></td></tr><tr><td>char+word+char</td><td>72.25</td><td>71. 73</td><td>71. 99</td></tr></table></body></html>

表4中的实验所使用的模型为CharBiLSTM-CRF 模型，采用的数据集为 $2 0 \%$ 的 BC5CDR数据集。其中，word表示为词向量信息，维度设置为100。char 表示为字符向量，维度设置为50；“char\*2”表示为2个字符向量矩阵拼接，“+”表示拼接。

为探究词向量与字符向量拼接顺序是否会影响模型的性能，本文做了以下实验，实验结果如表4所示：在模型输入层采用词向量和一个字符向量矩阵拼接时，将它们的拼接顺序调换，模型F1值与之前相比，稍微下降。当词向量与两个字符向量矩阵拼接时，将词向量放至两个字符向量矩阵中间时，模型的精确率、召回率、F1值与之前相比都有所下降。由此可知，词向量与字符向量的拼接顺序是会影响模型的性能的

Table5explores the impactofthe numberofword vectorstitching character vectormatrices ontheperformanceof the model   

<html><body><table><tr><td colspan="4">20%BC5CDR数据集</td></tr><tr><td>Method</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>CharBiLSTM-CRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr><tr><td>(word+char*2)</td><td></td><td></td><td></td></tr><tr><td>word(200)+char*4</td><td>73.12</td><td>73.20</td><td>73.16</td></tr><tr><td>word(300) +char*6</td><td>70.74</td><td>73.87</td><td>72.27</td></tr><tr><td>word(50)+char</td><td>70.42</td><td>70.70</td><td>70.56</td></tr><tr><td>word+char</td><td>71.82</td><td>72.50</td><td>72.16</td></tr><tr><td>word+char*3</td><td>71. 07</td><td>74.21</td><td>72.60</td></tr><tr><td>(word+char*2)*2</td><td>73.48</td><td>71.37</td><td>72.41</td></tr></table></body></html>

表5中的实验所使用的模型为CharBiLSTM-CRF 模型，采用的数据集为 $2 0 \%$ 的 BC5CDR 数据集。其中，word表示为词向量信息，维度设置为100。“word(200)”表示维度为200的词向量，char 表示为字符向量，维度设置为50；“char\*3”表示为3个字符向量矩阵拼接，“+”表示拼接。

在低资源场景下，模型受标注数据量少的限制，通过在词向量后拼接字符向量，可以提高模型处理罕见词的能力，提高模型的识别性能。为探究拼接字符向量矩阵数量为多少时，模型识别性能提升的最多，本文做了以下实验，实验结果如表5所示：首先将词向量维度设置为100时，拼接一个字符向量矩阵、两个字符向量矩阵、三个字符向量时矩阵，通过实验结果对比，本文发现在词向量后拼接两个字符向量矩阵，模型识别效果最好。然后将词向量维度设置为50、200、300时，后拼接不同数量的字符向量矩阵。通过实验结果对比，本文发现将词向量维度设置为100，拼接两个字符向量矩阵，模型的识别性能提升的最多。

# 4.4消融实验

为探究K折交叉验证法和多层字符信息以及自注意力机制对模型性能的影响,本文将 BiLSTM-CRF 模型设置为基准模型,首先采用K折交叉验证法训练基准模型，命名为CharBiLSTM-CRF(1)模型。然后在CharBiLSTM-CRF(1)模型基础上融合多层字符信息，构建CharBiLSTM-CRF 模型。最后在CharBiLSTM-CRF 模型基础上融合自注意力机制，构建了CharBiLSTM-Att-CRF 模型。以上模型在两个数据集的实验结果如表6所示：

(BiLSTM-CRF模型为基准模型，CharBiLSTM-CRF(1)模型表示采用K折交叉验证法训练模型基准)

表5词向量拼接字符向量矩阵的个数对模型性能的影响  
表6消融实验结果  
(the BiLSTM-CRF modelisthe benchmark model,and the CharBiLSTM-CRF(1)modelrepresents the training modelusing the $\mathbf { k }$ -fold cross validation method)   

<html><body><table><tr><td colspan="3">20%CONLL2003</td><td colspan="4">20%BC5CDR</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>82.17</td><td>80.35</td><td>81.3</td><td>79.09</td><td>62.66</td><td>69.92</td></tr><tr><td>CharBiLSTM-CRF（1)</td><td>82.31</td><td>83.23</td><td>82. 77</td><td>76.53</td><td>65.92</td><td>70.83</td></tr><tr><td>CharBiLSTM-CRF</td><td>87.49</td><td>88.83</td><td>88.06</td><td>74.35</td><td>72.22</td><td>73. 27</td></tr><tr><td>CharBiLSTM-Att-CRF</td><td>88.28</td><td>88.31</td><td>88.30</td><td>75. 45</td><td>72.60</td><td>74.00</td></tr></table></body></html>

Table 6 ablation experimental results

表6所示的消融实验结果表明,CharBiLSTM-CRF 模型在两个数据集上取得的F1值均高于BiLSTM-CRF 模型，表明 K折交叉验证法和多层字符信息对于模型的性能具有提升的作用。从表中模型CharBiLSTM-Att-CRF 在两个数据集取得的精确率、召回率、F1值可以看出，本文提出的CharBiLSTM-Att-CRF 模型识别效果是比较好的。

# 4.5定性分析

为更好的对比 CharBiLSTM-Att-CRF 模型与BiLSTM-CRF 模型在命名实体识别任务上的差异，本文从数据集中选取两个实例句子：“OnlyFranceand Britain backed Fischler‘sproposal.”和“Rare Hendrixsong draft sellsfor almost $\$ 8$ 1700”，人工标注、BiLSTM-CRF 模型和CharBiLSTM-Att-CRF 模型的标注结果如表7、表8所示。

表7模型识别实例1  
Table 7 model identification example 1   

<html><body><table><tr><td></td><td>Only</td><td>France</td><td>and</td><td>Britain</td><td>backed</td><td>Fischler</td><td>`s</td><td>proposal</td><td>：</td></tr><tr><td>人工标注</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-CRF</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>CharBiLSTM-Att-CRF</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表8模型识别实例2  
Table 8 model identification example 2   

<html><body><table><tr><td></td><td>Rare</td><td>Hendrix</td><td>song</td><td>draft</td><td>sells</td><td>for</td><td>almost</td><td>$</td><td>1700</td></tr><tr><td>人工标注</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-CRF</td><td>B-PER</td><td>I-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-Att-BCRF</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

在表7中可以看到该句子共有三个实体，原来的 BiLSTM-CRF 模型只实别出了两个实体，本文提出的CharBiLSTM-Att-CRF 模型将句中包含的三个实体全部识别出来。表8中，该句子只有一个人名实体，但BiLSTM-CRF 模型把句子中前两个单词错误地识别为一个人名实体，而本文提出的模型能将句中人名实体准确地识别出来。

# 5总结

针对低资源领域标注语料较少的问题，本文提出了一种低资源场景下命名实体识别模型(CharBiLSTM-Att-CRF)。该模型通过采用K折交叉验证法，使得模型参数在低资源场景下也能得到较好拟合。同时将多层字符特征信息融合到模型中，提升模型处理罕见词的能力，使得模型在标注数据少量时也能拥有较好的识别性能，能更好的适应低资源命名实体识别任务。但该模型识别专有名词的性能还需继续提升，本文以后的工作会专注于提高模型识别专有名词的能力，同时模型的知识迁移和跨领域的性能提升也是本文以后的研究重点。

# 6参考文献

[1]Hammerton J. Named entity recognition with long short-term memoryC]//Proceedings of the seventh conference on Natural language learning at HLT-NAACL 2003. 2003:172-175.   
[2]LampleG,Ballesteros M, Subramanian S,etal.Neural architectures for named entityrecognition[J].arXiv preprint arXiv:1603.01360，2016.   
[3]Huang Z，Xu W，YuK.BidirectionalLSTM-CRF models for sequence tagging[J].arXiv preprintarXiv:1508.0991,2015. [4]殷章志,李欣子,黄德根,李玖一.融合字词模型的中文命名实体识别研究[J].中文信息学报,2019,33(11):95-100+106. [5]林广和,张绍武,林鸿飞.基于细粒度词表示的命名实体识别研究[J].中文信息学报,2018,32(11):62-71+78.   
[6]Rathaparkhi A. A Maximum Entropy Part of Speech Tagger[J]. Proceedings of EMNLP’96，1996. segmentation[C]//Icml． 2000，17(2000): 591-598.   
[8]Lafferty J, McCallumA, PereiraFCN. Conditional random fields: Probabilistic models for segmenting and labeling sequence data[J]． 2001.   
[9]Collobert R,Weston J，Bottou L，etal.Natural language processng (almost）from scratchJ].Journal of machine learning research，2011，12(ARTICLE): 2493- 2537.   
[10]ChiuJPC， Nichols E.Named entityrecognition withbidirectional LSTM-CNNs[J].Transactions of the Asociation for Computational Linguistics， 2016,4: 357-370.   
[11]Ni J,Dinu G,Florian R. Weakly supervised cross-lingual named entity recognition via effective annotationand representation projection[J]. arXiv preprint arXiv:1707.02483， 2017.   
[12]Mayhew S，TsaiCT,RothD.Cheap translationforcross-lingual named entityrecognition[C]//Proceedings of the 2017 conference on empirical methods in natural language processing. 2017: 2536-2545.   
[13]ToolkitOS，BCK Hoc,MHNNgi,etal.Baocao khoa hoc:"Moses:Open Source Toolkit for Statistical Machine Translation"[J]． tailieu vn.   
[14]Chen X,AwadallahA H,Hassan H,etal.Multi-source cross-lingual model transfer:Learning what to share[J]. arXiv preprint arXiv:1810.03552， 2018.   
[15] Keung P,Lu Y， Bhardwaj V.Adversarial learning with contextual embedings for zero-resource crosslingual classification and NER[J]. arXiv preprint arXiv:1909.00153, 2019.   
[16] GodfellwI，Pouget-AbadieJ，Mirza M,etal.Generativeadversarial nets[J]．Advances in neural information processing systems， 2014， 27.   
[17]Dai X,Adel H.Ananalysis of simple data augmentation for named entity recognition[J].arXiv preprint arXiv:2010.11683，2020.   
[18]Chen J,Wang Z,TianR,etal.Local additivitybased data augmentationfor semi-supervised NER[J].arXivpreprint arXiv:2010.01677，2020.   
[19]Yang Y，ChenW，Li Z，et al.Distantly supervised NER with partial annotation learning and reinforcement learning[C]//Proceedings of the 27th International Conference on Computational Linguistics.2018:2159-2169. [20]TsuboiY,KashimaH, MoriS,etal.Training conditionalrandomfields using incomplete annotations[C]//Proceedings of the 22nd International Conference on Computational Linguistics (Coling 2008)．2008:897-904.   
[21]Feng J,Huang M, ZhaoL,etal. Reinforcement learning for relationclassfication fromnoisydata[C]/Proceedings of the aaai conference on artificial intelligence. 2018,32(1).   
[22]Zhang T,Xia C,Philip SY，etal.PDALN: Progressive Domain Adaptation overa Pre-trained Modelfor Low-Resource Cross-Domain NamedEntity Recognition[C]//Proceeingsof the2021 ConferenceonEmpirical Methods inNaturalLanguage Processing. 2021: 5441-5451.   
[23]Chen S,PeiY,KeZ,etal.Low-ResourceNamed EntityRecognition viathePre-Training Model[J].Symmetry，2021, 13(5) : 786.   
[24]Pennington J，SocherR，ManningCD.Glove:Global vectors for word representation[C]/Proceedingsof the 2014 conference on empirical methods in natural language processing (EMNLP). 2014: 1532-1543.   
[25]Jie Z,XieP,LuW,etal.Better modelingof incompleteannotations for named entityrecognition[C]//Proceedings of the 2019 Conference of the North American Chapter of the Asociation for Computational Linguistics: Human Language Technologies，Volume 1 (Long and Short Papers)． 2019: 729-734.   
[26]SangEF，De MeulderF.Introductiontothe CoNLL-2003 shared task:Language-independent named entity recognition[J]. arXiv preprint cs/0306050, 2003.   
[27]Li J,SunY,JohnsonRJ,etal.BioCreativeVCDRtaskcorpus:aresourceforchemicaldiseaserelation extraction[J]. Database，2016，2016.   
[28]Lin BY，Lee DH， Shen M，et al.TriggerNER: Learning with Entity Triggers as Explanations for Named Entity Recognition[C]// arXiv. arXiv，2020.   
[29]M.Zhong，G.Liu,J.Xiong and J.Zuo，"DualNER:A Trigger based DualLearning Framework forLow-Resource Named Entity Recognition," in IEEE Intelligent Systems，doi:10.1109/MIS.2022.3167168.