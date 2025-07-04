# 面向低资源命名实体识别的BiLSTM-BCRF模型

钟茂生 吴佳华江西师范大学计算机信息工程学院

摘要：[目的]当标注数据较少时，现有模型受训练数据量少的限制，参数没有拟合到预期效果，导致在低资源命名实体识别任务中模型识别性能不佳。[方法]本文提出一种融入伯努利分布(Bermouli distribution)的新型损失函数，让模型较好拟合数据。此外，本文在BiLSTM-CRF模型基础上融合多层字符特征信息，结合基于伯努利分布的新型损失函数，构建了BiLSTM-BCRF 模型。[结果]本文提出的BiLSTM-BCRF模型在 $20 \%$ 的CoNLL2003 和 $20 \%$ 的 BC5CDR的数据集上，F1值在BiLSTM-CRF 模型基础上分别提升了 $6 . 1 6 \%$ 、 $3 . 3 5 \%$ 。[结论]该模型能较好地适应低资源命名实体识别任务。[局限]该模型识别专有名词的性能还有待提升。

关键词：低资源命名实体识别;神经网络;伯努利分布

# BiLSTM-BCRF Model for Low Resource Named Entity Recognition

Zhong Maosheng,Wu Jiahua School of computer information engineering, Jiangxi Normal University

Abstract: [Objective]when there are few labeled data,the existing models are limited by the amount of training data,and the parameters do notfit the expected effect,resulting in poor model recognition performance in the task of lowresource named entityrecognition.[Methods]anew loss function integrated with Bernouli distribution is proposed to make the model fitthe data beter.Inaddition,based onthe BiLSTM-CRF model,multi-layer character feature information is fused,and the new lossfunction based on Bernouli distribution is combined to construct the BiLSTMBCRF model. [Results] Based on the dataset of $20 \%$ CONLL2003 and $20 \%$ BC5CDR, the F1 value of the BiLSTMBCRF model proposed in this paper increased by $6 . 1 6 \%$ and $3 . 3 5 \%$ respectively. [Conclusion] the model can better adaptto the task of low resource named entity recognition.[Limitations]the performance of this model in identifying proper nouns needs to be improved

Keywords: Low resource named entity recognition； Neural network； Bernouli distribution

# 1引言

命名实体识别是自然语言处理的基础任务之一，该任务旨在从非结构化的文本中自动识别出实体，并将其标记为预定义的类别，例如人名、地名和组织机构名等。例如，“张无忌，金庸武侠小说《倚天屠龙记》人物角色，中土明教第三十四代教主。”这句话包含的实体有：人名实体“张无忌，金庸”，书名实体“倚天屠龙记”，门派实体“明教”。由此可见,实体识别是文本语义理解的基础。同时命名实体识别技术在知识图谱构建、机器翻译、知识库构建等多种自然语言处理任务中有着广泛应用。

近些年来，深度学习方法被广泛用于命名实体识别，如Hammerton[将长短期记忆网络(LSTM)应用到实体识别研究中，LSTM-CRF 结构成为实体识别的基础结构。Lample等人在LSTM-CRF模型的基础上，提出双向长短期记忆网络(Bi-LSTM)和条件随机场(CRF)结合的模型[3-5等。这类方法虽然在文本实体识别任务中表现优异，但是需要大规模的标注数据，对训练语料中每个词进行人工标注。在标注数据不足的情况下，现有模型的参数不能较好拟合，导致模型预测最大概率标签并不一定是真实标签，模型的识别性能下降，很难应用到如生物、医学这些标注语料较少的领域。针对上述问题，本文提出一种融入伯努利分布的新型损失函数,使模型参数在低资源场景下能较好拟合。在此基础上，为增加模型能处理的词汇量和提升模型识别罕见词的能力，本文在BiLSTM-CRF模型基础上融合多层字符特征信息,进一步提升了模型的精确率和召回率。

本文的组织结构为：第二节介绍低资源命名实体识别领域的主要工作。第三节介绍本文模型包括：输入层、BiLSTM层和BCRF层。第四节介绍实验数据、实验内容、实验结果及分析。最后对本文工作进行总结。

# 2相关工作

命名实体识别的研究方法主要有基于规则和词典方法、机器学习方法、深度学习方法等。基于词典和规则的方法过多依赖于语言学家制定的规则模板，容易产生错误，移植性差。传统机器学习方法主要包括:隐马尔可夫模型(Hidden Markov Model,HMM)、最大熵(MaximumEntropy,ME)、最大熵马尔可夫模型(Maximum Entropy Markov Model,MEMM)[7]、条件随机场（Conditional RandomFields,CRF)[8]等。这些传统的机器学习方法在特征提取方面需要人工参与，同时需要大规模的标注语料来训练模型，方法的性能主要依赖于所采用的特征是否具有辨识度。其中 CRF被看作是命名实体识别的主流模型,优点在于在对一个位置进行标注的过程中CRF 可以利用内部及上下文特征信息。随着深度学习的不断发展,命名实体识别的研究重点已转向深层神经网络,Collobert等学者首次提出基于神经网络的命名实体识别方法,该方法中每个单词具有固定大小的窗口,但未能考虑长尾问题。为了克服这一限制,Chiu 和Nichols[提出一种双向LSTM-CNNs架构,该架构可自动检测单词和字符级别的特征。Hammerton[1利用CRF关注上下文特征信息的特点，提出LSTM-CRF模型。

近些年来,大量的深度学习方法被应用于低资源命名实体识别任务中，低资源的命名实体识别技术成为当前研究热点之一，其性能的提高是命名实体识别技术走向广泛实际应用的前提。相关研究工作可大致分为以下几类：跨语言迁移的方法、数据增强的方法、集成自动标注语料的方法和其他方法。

跨语言迁移方法的基本思路是利用资源丰富语言的标注数据帮助低资源语言进行命名实体识别,可大致分为数据迁移的方法和模型迁移的方法两大类。基于数据迁移的方法通常借助文本翻译和标签映射等手段把源语言中的标注数据转换成目标语言的标注数据，然后基于这些数据训练模型。Ni等提出了一种在语料库上进行标签映射的方法，用于创建自动标记的目标语言数据。Mayhew 等[12]利用双语词典，使用一种类似短语机器翻译[13]的方法自动翻译源语言的标注文本。基于模型迁移的方法通常先学习语言无关的特征，然后在源语言的标注语料上训练NER模型直接用于目标语言。Chen等[4同样基于对抗学习的方法提取语言无关的特征，并动态地计算源语言和目标语言之间的相似度，从而更有效地实现从多个源语言到目标语言的知识迁移。Keung 等[5]在多语言版本 BERT的基础上进一步使用对抗学习[的方法，以学习更好的与语言无关的特征。

数据增强方法的主要目标是,在不增加人工标注成本的前提下,通过增加合理的噪声来提升模型的鲁棒性，在少数据量的场景下对模型性能的提升有很大帮助。Dai等[7引入了一些词替换的随机操作来增加训练语料多样性;Chen 等[18]在半监督NER任务中引入了基于局部可加性的数据增强。基于语言迁移的方法和数据增强的方法虽然能够有效地缓解标注语料短缺的问题，但是具有丰富标注资源的语言是非常少的。为此，一些研究者提出集成自动标注语料的方法，首先通过某种方法自动标注大量语料，然后集成它们用于提高低资源实体识别模型的性能。Yang等[1首先基于词典匹配的方法自动标注语料，然后使用Partial-CRF[20在少量人工标注的语料和大量自动标注的语料上训练实体识别模型。此外，他们还基于强化学习[2训练一个选择器，用于筛选掉具有噪声的标注数据。

除上述三类方法外，低资源实体识别领域还有其他方法如 Zhang 提出渐进式知识提炼方法PDALN[22]，有效的将高资源域适应于低资源目标域。Chen提出了一种低资源的语言模型的微调方法[23]，使用基于注意力机制的微调策略，从预训练的语言模型中选择相关的语义和句法信息，将其应用于命名实体识别任务。本文的工作主要是探索低资源条件下基于深度学习的命名实体识别方法。

# 3模型

# 3.1基本架构

命名实体识别任务被看作是序列标注问题。输入句子表示为,其中表示第i个字符(包括数字、单词、字母或标点符号等)。输出标注序列为,其中 $\in \{ \mathrm { B , M , E , S , O } \}$ 是的标签,B、M、E、S和O分别代表实体首字,实体中间字,实体结尾字,实体单独字和非实体。命名实体识别就是对每个字符进行B、M、E、S、O的分类标注。

本文在BiLSTM-CRF模型损失函数中融入伯努利分布，同时将多层字符信息融合到BiLSTM-CRF模型，构建了BiLSTM-BCRF 模型。BiLSTM-BCRF模型基本结构如图1所示。该模型结构主要分为输入层、Bi-LSTM层和BCRF层。

![](images/5eda72801e9aee3ed2282f6dfa6cf1191e3abf0f94e63b5b056396d9f2e2f820.jpg)  
图1BiLSTM-BCRF模型基本结构

# 3.2输入层

如图2所示，该图为模型输入层的结构图。其中， $\mathbf { \sigma } _ { \mathbf { X } }$ 表示词向量，是使用Pennington等人提出 Glove英文词向量[24文件生成的，；表示由BiLSTM训练生成的字符向量，。最后将词向量与字符向量拼接输入到BiLSTM层。

![](images/62b3b12d8d997a1db83915079823362ab3932980365a1cfce890fd1476490396.jpg)  
Figure 1 basic structure of BiLSTM-BCRF model   
图2模型输入层基本结构图Fig.2 basic structure of model input layer

# 3.3BiLSTM层

LSTM神经网络在命名实体识别任务中表现出良好的建模能力，能较好的学习文本中单词与字符的特征信息，BiLSTM层结构主要由两个LSTM组合而成。LSTM的网络结构主要分三个阶段：遗忘阶段、选择记忆阶段、输出阶段。LSTM单元结构如图3所示，分别表示LSTM单元中

diagram ofLSTM unit的输入门、遗忘门、输态。表示在t-1时刻的刻的细胞记忆状态。σ表示双曲正切激励函数，出门在t时刻的状图隐藏状态,表示在t时表示 Sigmoid，tanh如式 $( 1 ) \sim$ 式(6)所示：

![](images/8027f37c8b187fdae38fbad4e0e4abbac0a2b747683e994dfd3015a62a622a46.jpg)  
图3LSTM单元结构图 Figure 3 structure

BiLSTM神经网络中的输出隐藏状态,分别为前向输出和后向输出。

# 3.4BCRF层

原有命名实体识别模型解码层主要是条件随机场(Conditional Random Field，CRF)。CRF是由状态特征函数和状态特征转移函数组成，状态特征函数也称发射概率，状态特征转移函数在模型中可以用一个状态转移矩阵表示，最后得到的条件概率如式(7)所示：

其中，是 $\mathbf { x }$ 和y一组特征向量的映射。表示模型在给定文本序列 $\mathbf { x }$ 条件下得到标签序列y的概率。损失函数计算公式如式(8)所示：

CRF方法的优点是可以进一步考虑序列标签的依赖关系，同时在训练过程中，采用Viterbi算法用于最大似然估计，使模型对输入文本预测出标签的最大概率如式(9)所示：

其中，表示模型预测标签的最大概率。但是在低资源的场景下，模型受标注数据量少的限制，参数没有拟合到预期效果，输出预测概率最大的标签序列并不一定是真实的标签序列，导致模型最后的识别性能下降。在此，本文借鉴jie等人[2在不完全标注实体识别任务上采用交叉验证方式训练数据的思想，将伯努利分布融入到条件随机场损失函数中，构建新的损失函数，对应的解码模型称为BCRF。

伯努利分布(Bermoulli distribution)又名两点分布或0-1分布，它是指对于随机变量X，参数为$\mathrm { P } ( 0 { < } \mathrm { P } { < } 1 )$ ,它分别以概率P和1-P取1和0为值，该分布是一个离散型概率分布，是 $\mathrm { { N = 1 } }$ 时二项分布的特使情况。将伯努利分布函数融入到CRF中，构建新的损失函数如式(10)所示：

在原有的损失函数计算公式加入一个分布函数q，计算公式如式(11)所示。分布函数q取值为0或1，呈伯努利分布。

其中，表示模型预测最大概率的标签，表示真实标签。在式(10)中，当句子中词预测标签与真实标签一致时，得到的损失值也就较小。那么相反，如果在一个句子中预测标签错误的越多，那么它的损失值也越大。采用新的损失函数公式计算，在训练样本只有少量时，模型参数能较好拟合，提升模型的精确率和召回率，最后提高模型的识别效果。

# 4实验

# 4.1数据集及评价指标

本文选择CONLL20032数据集和BC5CDR[27数据集来证明所提出模型的有效性。CONLL2003数据集包含4种实体类型以及英语和德语两种语言，BC5CDR数据集包含两种实体和1500 篇医药文章。由于实体识别的任务主要是对实体的边界和类别的识别，只有当边界及实体的类别都识别正确时，才判断正确。本文通过使用精确率(Precision)和召回率(Recall)来求得F1值，用于衡量该模型的性能，如式(12)式(14)所示：

其中N表示为模型所预测出的实体总数，M表示模型预测的实体中正确预测实体的总数，K表示为数据集中所标注的实体总数。模型中超参数设置如表1所示：

Table 1 super parameter setting   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>隐层向量维度</td><td>200</td></tr><tr><td>词向量维度</td><td>100</td></tr><tr><td>字符向量维度</td><td>50</td></tr><tr><td>Dropout</td><td>0.5</td></tr><tr><td>学习率</td><td>0.1</td></tr><tr><td>批尺寸</td><td>10</td></tr><tr><td>训练轮数</td><td>100</td></tr><tr><td>L2正则化</td><td>1e-8</td></tr></table></body></html>

# 4.2实验结果与分析

本文所做的实验采用的数据集主要是CONLL-2003英语数据集和 BC5CDR专业医学领域数据集，BiLSTM-BCRF模型与BiLSTM-CRF模型实验结果如图4、图5所示：

图4BC5CDR数据集上BiLSTM-BCRF模型与BiLSTM-CRF模型实验结果对比

Fig.4 Comparison of experimental results between BiLSTM-BCRF model and BiLSTM-CRF model on BC5CDR lataset

图5CONLL2003数据集上BiLSTM-BCRF模型与BiLSTM-CRF模型实验结果对比

Fig.5 Comparison of experimental results between BiLSTM-BCRF model and BiLSTM-CRF model on NLL2003 dataset

从图4、图5中可以看出该模型在少量标注数据集上的性能是高于BiLSTM-CRF 模型，比较适合低资源领域的实体识别任务。同时该模型在 $30 \%$ 的CONLL2003数据集上F1值达到了$8 9 . 3 2 \%$ ，说明该模型在不需要大量的标注语料的情况下，也能取得比较好的识别效果。

TMN 是Lin等人[28在2020 年提出的一种基于实体和触发词标注的命名实体识别模型。BiLSTM-BCRF模型与TMN模型实验结果对比如表2、表3所示。

表1超参数设置  
表2BiLSTM-BCRF模型与TMN模型实验结果对比  
[able 2 Comparison of experimental results between BiLSTM-BCRF model and TMN m(   

<html><body><table><tr><td colspan="4">20%CONLL2003</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>82.17</td><td>80.35</td><td>81.3</td></tr><tr><td>TMN</td><td>86.04</td><td>85.98</td><td>86.01</td></tr><tr><td>BiLSTM-BCRF</td><td>87.49</td><td>88.63</td><td>88.06</td></tr></table></body></html>

如表2所示，该实验是在 $20 \%$ 的CONLL-2003数据集上进行的。从表中可以看出BiLSTM-BCRF模型F1值是是高于TMN模型的。

表3BiLSTM-BCRF模型与TMN模型实验结果对比 Table 3 Comparison of experimental results between BiLSTM-BCRF model and TMN model

<html><body><table><tr><td colspan="4">20%BC5CDR</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>79.09</td><td>62.66</td><td>69.92</td></tr><tr><td>TMN</td><td>77.47</td><td>70.47</td><td>73.97</td></tr><tr><td>BiLSTM-BCRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr></table></body></html>

如表3所示，在 $20 \%$ 的BC5CDR数据集上，BiLSTM-BCRF模型F1值比BiLSTM-CRF模型高 $3 . 3 5 \%$ ，比TMN 模型低 $0 . 7 \%$ ，主要是该模型识别一些专有名词的性能略低于TMN模型。但是，BiLSTM-BCRF 模型并不需要标注触发词，它所需要的人工成本只是TMN模型的3/4，同时BiLSTM-BCRF 模型在CONLL2003数据集上F1值比TMN 模型高 $2 . 0 5 \%$ 。当然，如何提高BiLSTM-BCRF模型识别专有名词的性能，也是本文后续工作的重点。

# 4.3词与多层字符信息的融合分析

在3.2节中本文提出如图2所示的模型输入层结构,为验证在模型输入层哪些因素会影响模型进行命名实体识别的性能，本文进行如下实验：

lable 4 explores the impact of word vector and character vector splicing order on mode   

<html><body><table><tr><td colspan="4">raoie 20%BC5CDR数据集</td></tr><tr><td>Method</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>word+char</td><td>71.82</td><td>72.50</td><td>72.16</td></tr><tr><td>char+word</td><td>71.23</td><td>73.07</td><td>72.14</td></tr><tr><td>BiLSTM-BCRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr><tr><td>(word+char*2) char+word+char</td><td>72.25</td><td>71.73</td><td>71.99</td></tr></table></body></html>

表4中的实验所使用的模型为BiLSTM-BCRF模型，采用的数据集为 $20 \%$ 的BC5CDR数据集。其中，word表示为词向量信息，维度设置为100。char表示为字符向量，维度设置为50；“char\*2"表示为2个字符向量矩阵拼接，“ $+$ 表示拼接。

为探究词向量与字符向量拼接顺序是否会影响模型的性能，本文做了以下实验，实验结果如表4所示：在模型输入层采用词向量和一个字符向量矩阵拼接时，将它们的拼接顺序调换，模型F1值与之前相比，稍微下降。当词向量与两个字符向量矩阵拼接时，将词向量放至两个字符向量矩阵中间时，模型的精确率、召回率、F1值与之前相比都有所下降。由此可知，词向量与字符向量的拼接顺序是会影响模型的性能的

表4词向量与字符向量拼接顺序对模型性能的影响  
表5词向量拼接字符向量矩阵的个数对模型性能的影响  
Table 5 explores the impact of the number of word vector stitching character vector matrices on the performance of t model   

<html><body><table><tr><td colspan="4">20%BC5CDR数据集</td></tr><tr><td>Method</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-BCRF</td><td>74.35</td><td>72.22</td><td>73.27</td></tr><tr><td>(word+char*2) word(200)+char*4</td><td>73.12</td><td>73.20</td><td>73.16</td></tr><tr><td>word(300)+char*6</td><td>70.74</td><td>73.87</td><td>72.27</td></tr><tr><td>word(50)+char</td><td>70.42</td><td>70.70</td><td>70.56</td></tr><tr><td>word+char</td><td>71.82</td><td>72.50</td><td>72.16</td></tr><tr><td>word+char*3</td><td>71.07</td><td>74.21</td><td>72.60</td></tr><tr><td>(word+char*2)*2</td><td>73.48</td><td>71.37</td><td>72.41</td></tr></table></body></html>

表5中的实验所使用的模型为BiLSTM-BCRF模型，采用的数据集为 $2 0 \%$ 的 BC5CDR数据集。其中，word表示为词向量信息，维度设置为100。“word(200)”表示维度为200的词向量，char表示为字符向量，维度设置为50；“char\*3”表示为3个字符向量矩阵拼接，“ $+ ^ { , , , }$ 表示拼接。

在低资源场景下，模型受标注数据量少的限制，通过在词向量后拼接字符向量，可以提高模型处理罕见词的能力，提高模型的识别性能。为探究拼接字符向量矩阵数量为多少时，模型识别性能提升的最多，本文做了以下实验，实验结果如表5所示：首先将词向量维度设置为100时，拼接一个字符向量矩阵、两个字符向量矩阵、三个字符向量时矩阵，通过实验结果对比，本文发现在词向量后拼接两个字符向量矩阵，模型识别效果最好。然后将词向量维度设置为50、200、300时，后拼接不同数量的字符向量矩阵。通过实验结果对比，本文发现将词向量维度设置为100，拼接两个字符向量矩阵，模型的识别性能提升的最多。

# 4.4消融实验

为探究伯努利分布和多层字符信息对模型性能的影响,本文将BiLSTM-CRF 模型设置为基准模型，首先将伯努利分布融入到基准模型的损失函数中，构建 BiLSTM-BCRF(1)模型。然后在BiLSTM-CRF(1)模型基础上融合多层字符信息，构建BiLSTM-BCRF模型，以上模型在两个数据集的实验结果如表6所示：

(BiLSTM-CRF 模型为基准模型，BiLSTM-BCRF(1)模型表示将伯努利分布融入到 BiLSTM-CRF 模型损失函数中)

Table 6 ablation experimental results (the BiLSTM-CRF model is the benchmark model,and the BiLSTM-BCRF(1） model represents the integrationof Bernoulli distribution into the loss function of the BiLSTM-CRF model)   

<html><body><table><tr><td colspan="4">20%CONLL2003</td><td colspan="3">20%BC5CDR</td></tr><tr><td></td><td>Precision</td><td>Recall</td><td>F1</td><td>Precision</td><td>Recall</td><td>F1</td></tr><tr><td>BiLSTM-CRF</td><td>82.17</td><td>80.35</td><td>81.3</td><td>79.09</td><td>62.66</td><td>69.92</td></tr><tr><td>BiLSTM- BCRF(1)</td><td>86.43</td><td>87.75</td><td>87.08</td><td>73.77</td><td>71.98</td><td>72.87</td></tr><tr><td>BiLSTM-BCRF</td><td>87.49</td><td>88.83</td><td>88.06</td><td>74.35</td><td>72.22</td><td>73.27</td></tr></table></body></html>

表6所示的消融实验结果表明，BiLSTM-BCRF(1)模型在两个数据集上取得的F1值均高于BiLSTM-CRF模型，表明新型损失函数对于模型的性能具有提升的作用。从表中模型BiLSTM-BCRF 在两个数据集取得的精确率、召回率、F1值可以看出，本文提出的BiLSTM-BCRF 模型识别效果是比较好的。

# 4.5定性分析

为更好的对比BiLSTM-BCRF模型与BiLSTM-CRF模型在命名实体识别任务上的差异，本文从数据集中选取两个实例句子：“Only France and Britain backed Fischler‘sproposal.”和“Rare Hendrix song draft sells for almost $\ S$ 17000”，人工标注、BiLSTM-CRF 模型和BiLSTM-BCRF模型的标注结果如表7、表8所示。

表6消融实验结果  
表7模型识别实例1  
Table 7 model identification example 1   
表8模型识别实例2  

<html><body><table><tr><td></td><td>Onl y</td><td>France</td><td>an d</td><td>Britai n</td><td>backed</td><td>Fischle r</td><td>`s</td><td>proposal</td><td>：</td></tr><tr><td>人工标注</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-CRF</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-BCRF</td><td>0</td><td>B-LOC</td><td>0</td><td>B-LOC</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

Table 8 model identification example 2   

<html><body><table><tr><td></td><td>Rare</td><td>Hendrix</td><td> song</td><td>draft</td><td>sells</td><td>for</td><td>almost</td><td>$</td><td>1700 0</td></tr><tr><td>人工标注</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-CRF</td><td>B-PER</td><td>I-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>BiLSTM-BCRF</td><td>0</td><td>B-PER</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

在表7中可以看到该句子共有三个实体，原来的BiLSTM-CRF模型只实别出了两个实体，本文提出的BiLSTM-BCRF 模型将句中包含的三个实体全部识别出来。表8中，该句子只有一个人名实体，但BiLSTM-CRF 模型把句子中前两个单词错误地识别为一个人名实体，而本文提出的模型能将句中人名实体准确地识别出来。

# 5总结

针对低资源领域标注语料较少的问题，本文提出了一种低资源场景下命名实体识别模型(BiLSTM-BCRF)。该模型通过在损失函数中融入伯努利分布，使得模型参数在低资源场景下也能得到较好拟合。同时将多层字符特征信息融合到模型中，提升模型处理罕见词的能力，使得模型在标注数据少量时也能拥有较好的识别性能，能更好的适应低资源命名实体识别任务。但该模型识别专有名词的性能还需继续提升，本文以后的工作会专注于提高模型识别专有名词的能力，同时模型的知识迁移和跨领域的性能提升也是本文以后的研究重点。

# 6感谢

# 感谢审稿人提出的建设性意见，本文工作得到了国家自然科学基金(NO.61877031)的支持。

# 参考文献

[1]HammertonJ.Namedentityrecognitionwithlongshort-termmemoryC/ProceedingsoftheseventhconferenceonNaturallanguage learning at HLT-NAACL 2003.2003:172-175.   
[2]LampleG,lsteroubamaan,alealcitecesfodtitycoio[J].XireptaXiv:6 2016.   
[3]Huang Z, Xu W,YuK.BidirectionalLSTM-CRF models forsequence tagging[J].arXivpreprint arXiv:508.01991,2015.   
[4]殷章志,李欣子,黄德根,李玖一.融合字词模型的中文命名实体识别研究[J].中文信息学报,2019,33(11):95-100+106.   
[5]林广和,张绍武,林鸿飞.基于细粒度词表示的命名实体识别研究[J].中文信息学报,2018,32(11):62-71+78.   
[6]Rathaparkhi A.A Maximum Entropy Part of Speech Tagger[J]. Proceedings of EMNLP'96,1996.   
[7]McCallumA,FreitagD,reiraFCN.MaximumentropyarkovodelsforinforationetractionadsgmentatioC/00 17(2000): 591-598.   
[8]LfertyJMcCallumA,ereiraFCNConditionalndomfiels:Probablisticodelsforsegmentingandlabelingsquedata[J]. 2001.   
[9]ColoerttJealggoingtchJ]J 12(ARTICLE): 2493- 2537.   
[10]ChiuJPCichlsE.Namedtitycoitioithdirectioal-s[J]ransactiosfteAocatforomtatioal Linguistics, 2016, 4: 357-370.   
[]NiJ,inuG,loranRWeaklyupvisedo-galedtitoitionviaectiveotationdeprtation projection[J].arXiv preprint arXiv:1707.02483,2017.   
[12]MayhewS,saiCRothDChaptransatinforros-ngualnamedetityecognitioCProceedingsofteoeeo empirical methods in natural language processing. 2017: 2536-2545.   
[13]ToolkitOS,BCKHoc,MHNNgu,etal.Baocaokhoahoc: "Moses:Open SourceToolkitforStatisical MachineTranslation"[J]. tailieu vn.   
[14]ChenX,AwadallahAH,HasaH,etal.Multi-soureros-lingualmodeltrasfer:Leangattshare[J]ivprepint arXiv:1810.03552,2018.   
[15]KeungP,uYadjdvsarialleangihtexalbedingforroesoueo-galaad NER[J].arXiv preprint arXiv:1909.00153,2019.   
[16]GoelugeJaeatisaaJ]aloaipete 2014,27.   
[17]Dai X,AdelH.AaalysisofpledataaugmetatioforamedetityrecogitionJ].rXivpreprintarXiv:O0.60. [18]ChenJ，WangZ，TianR，etal.Localaditivitybaseddataaugmentationforsemi-supervisedNER[J].arXivpreprint arXiv:2010.01677,2020.   
[19]YangYWiZetalistatpsedtaotatiogdforetlegCrf the 27th International Conference on Computational Linguistics.2018: 2159-2169.   
[20]TsuboiYKasaH,ori,tal.TiningonditioaldofeldssingicopleteaotatiosCroceedingsofd International Conference on Computational Linguistics (Coling 2008).20o8: 897-904.   
[21]FengJ,HuangM,ZhaoLetalReinforcementleaingforrelationcassifcationfromnoisydataCProceingofteai conference on artificial intelligence.2018,32(1).   
[22]ZhangT,XiaCPhilipSY,etalDALN:ProgresiveomainAdaptationoverare-traiedModelforLow-ResourceCro-a NamedEntityRecognitionC/Proceedingsofthe1ConferenceonEmpiricalMethods inNaturalLanguageProcessg21:541- 5451.   
[23]ChenS,eiKe,etaloRocedEicoiiitergelJ]try(). [24]PeningtonJSocherR,ManngCD.Glove:GlobalvectorsforwordrepresentationC/Procedingsofthe014coferenceo empirical methods in natural language processing (EMNLP). 2014: 1532-1543.   
[25]JieZ,XiePLuWetalBetemodelingoficompleteotatiosforamedntityrecogtionCroingsofte19 ConferenceoftheNorthAmericanChapteroftheAsocationforComputationalLinguistics:HumanLanguageTechnologiesVolume1 (Long and Short Papers).2019:729-734.   
[26]SangEF,DeMeulderFIntroductiontotheCoNLL-Osharedtask:Language-independentnamedentityrecognitio[J]arXiv preprint cs/0306050,2003.   
[27iJuesselsJ 2016.   
[28]LinBY，LeeDH，ShenM,etal.TriggerNER:LearingwithEntityTrigersasExplanationsforNamedEntityRecognitio[C/ arXiv. arXiv, 2020.

# 作者贡献声明：

钟茂生：设计模型思路、论文撰写和最终版本修订;吴佳华：执行实验和论文修订；  
所有作者声明不存在利益冲突关系

# 支撑数据：

支撑数据由作者自存储，202041600071@jxnu.edu.cn