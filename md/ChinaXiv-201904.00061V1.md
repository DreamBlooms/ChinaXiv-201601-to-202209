# 基于多特征和深度神经网络的维吾尔文情感分类

买买提阿依甫，吾守尔·斯拉木，艾斯卡尔·艾木都拉，杨文忠，帕丽旦·木合塔尔

(新疆大学 信息科学与工程学院，乌鲁木齐 830046)

摘要：针对传统机器学习的情感分类方法存在长距离依赖问题，深度学习存在忽略情感词库的弊端，提出了一种基于注意力机制与双向长短记忆网络和卷积神经网络模型相结合的维吾尔文情感分类方法。将多特征拼接向量作为双向长短记忆网络的输入捕获文本上下文信息，使用注意力机制和卷积网络获取文本隐藏情感特征信息，有效增强了对文本情感语义的捕获能力。实验结果表明，该方法在二分类和五分类情感数据集上的F1值相比于机器学习方法分别提高了 $5 . 5 9 \%$ 、 $7 . 7 3 \%$ 。

关键词：情感分类；双向长短记忆网络；卷积神经网络；注意力机制；维吾尔语中图分类号：TP391.1 doi:10.19734/j.issn.1001-3695.2018.10.0809

Uyghur sentiment classification based on multi-features and deep neural network

Maimaitiayifu, Silamu Wushouer, Aimudoula Aisikaer†, Yang Wenzhong, Muhetaer Palidan (College of Information Science& Engineering,Xinjiang University, Urumqi 83oo46,China)

Abstract:Inordertosolvethe problemoflong-distance dependence intraditionalmachine learningsentimentclasification method and the disadvantage of ignoring the emotional lexicon indeep learning,this paper proposes a Uyghur sentiment classification method based on atention mechanism combined with bidirectional long-short term memory network and convolutional neural network model.Theconcatenated multi-feature vector is usedas the input of the bidirectional long short-term memory network to capture thecontext information,the atention mechanism and convolution network are used to capture text hidden emotionalfeature information,whichefectivelyenhances thecaptureabilityofthetextsentiment semantics.The experimental results show that theF1 valueof this methodon two-categoryand five-category Uyghur sentiment data sets higher than machine learning method $5 . 5 9 \%$ $7 . 7 3 \%$ ,respectively.

Key words:sentimentclassification；bidirectional long short-term memory network；convolutional neural network: attention mechanism; Uyghur

# 0 引言

情感分析(sentimentanalysis)，也称为观点挖掘，其目标在于挖掘文本中观点的态度、倾向和意见等主观感受[1,2]。人们一般以文本、音频和图像为载体，借助于一定的表情进行表达情感[3]。常见的情感分析研究主要包括情感识别、情感极性分析和主题情感分析[4]等。

随着信息技术的发展，大量基于维吾尔语的新闻网站、论坛、微博等平台也不断建立，促进了新疆地区教育和经济的发展，提升了新疆信息化水平[5]。与此同时，也有网民发布带有负面情感信息，对社会造成负面影响。通过情感分析技术对社交媒介的评论、舆论进行倾向性分析，能够帮助政府和安全部门及时了解网民的民意调查、舆论倾向及动态。因此，如何通过技术手段从文本中捕获用户的情感倾向信息是对新疆社会稳定和长治久安具有很重要的理论意义和应用价值。

国内外的学者已经对情感分析做了大量的研究，并取得了一些显著的成果。目前常见的情感分析方法主要分为基于词典的方法、基于传统机器学习的方法和基于深度学习的方法三种。基于词典的方法主要是构建包括情感词、情感短语的情感词典，其核心是词典和规则，通过点互信息量（pointwisemutualinformation,MPI）等方法[6来计算词语的情感倾向，从而判断整个句子的情感极性。该方法受限于情感词典的覆盖度和判断规则的质量，而词典的构建和设计一个合适的判断规则一般都需要耗费很多人力和先验知识。基于传统机器学习的方法通常利用朴素贝叶斯(NB)[7]、最大熵（ME）[7]、支持向量机（SVM）[7]等进行情感分类。这些方法已被证明是简单有效的，但过度依赖背景知识和特征的选取，只能在有充足和正确标注的训练语料时才能够取得较高的分类效果，而这些高质量语料的标注和特征的选取仍然受到人为因素影响，需要投入大量人工成本。这些方法容易丢失文本深层语义信息，很难有效捕获文本里的情感信息。此外，此类方法对语料领域非常敏感，用一个领域的语料训练出来的模型不一定适应其他领域。

近几年来，随着深度神经网络技术的快速发展，深度神经网络针对资源丰富的英语或汉语等语言在机器翻译、语音识别、问答系统和文本摘要、关系提取和情感分析等各种NLP任务中取得了良好的性能。而由于维吾尔语资源遗乏，

情感分析研究较少。

维吾尔文情感分析工作起步较晚，目前还没有像英语或汉语一样丰富的情感资料可供使用。维吾尔文情感分析大多是基于情感词典和基于传统机器学习方法。采用深度神经网络进行情感分析的研究较少。

基于深度神经网络的情感分析方法主要是采用词向量对文本中的词语进行表示，进而构建句子、篇章的语义表示。在这些语义表示的基础上，采用深度神经网络模型对文本中蕴涵的情感信息进行学习，从而实现对文本情感的分析。目前常用于情感分析的神经网络模型包括循环神经网络(recurrentneural network，RNN）[8]、卷 积 神 经网络(convolutional neural network,CNN） [9,10,21]、长短记忆网络(long short-term memory,LSTM)[11,12,20]、门控循环单元(gatedrecurrent unit, GRU)等[13,16]。

目前基于深度神经网络的情感分析方法大多是将文本看做整体进行语义表示，对于情感词或情感短语的体现没有突出，而基于情感词典的情感分析方法过度依赖情感词，没有考虑文本整体的语义关系。因此，为了解决上述问题，本文引入了注意力机制，采用注意力模型对维吾尔文本、情感词进行编码，提出了一种基于注意力机制的BiLSTM-CNN模型的维吾尔文情感分析方法。本文主要贡献如下：

a)对现有的维吾尔文情感词典进行梳理，对"HowNet”和"NTUSD"汉文情感词库进行翻译并处理后构建了较完整的维吾尔文情感词库。b）本文使用音节特征向量、词性特征向量和位置特征向量，有效弥补了词向量的不足。c）提出了一种基于注意力机制的深度维吾尔文本情感分类方法（ATT-BiLSTM-CNN)，通过注意力模型使模型获取更深层次的情感特征信息，有效增强了对文本情感语义的捕获能力，从而提高了最好的情感分类效果。d)对比了本文模型和基准模型在情感二分类和五分类数据集上的分类效果，验证了本文模型的有效性。

# 1 相关工作

# 1.1注意力机制

注意力机制模仿人脑关注事物的某关键部分分配更多的注意力，通过计算注意力概率分布，将最关键的重要部分更加突出，从而对传统深度学习模型起到优化作用。2014年Mnih 等人[14]在图像分类任务中第一次引入了注意力机制，达到了较好的分类效果，验证了注意力机制在图像分类任务中的有效性。随后，Bahdanau等人[15]借鉴注意力机制在图像分类任务中的应用，将注意力机制引入到机器翻译任务中，使注意力机制成为自然语言处理领域的热点。随着研究的推进，各种改进的带注意力机制模型在文本摘要生成、文本分类、句法分析、情感分类、短文本对话等任务中均取得了良好的效果。

随着深度神经网络和注意力模型在自然语言处理领域的广泛应用，基于注意力机制的各种改进模型也应运而生，因为深度神经网络能够有效学习到文本特征信息，有效解决特征表示问题，从而提高了情感分类等NLP任务的准确率。Tang等人[16提出了两种带主体信息的基于注意力机制的TD-LSTM和TC-LSTM两种模型，提高了情感分类的准确率。Luong等人[17提出了一种局部注意力模型，通过调整窗口长度，在指定的窗口范围内计算每个单词的对其概率。Wu等人[18]提出了基于注意力机制的CNN-LSTM模型，在主题情感分析任务中达到了最好的性能。2015年Yin 等人[19]提出一种融合注意力机制的CNN网络。这些方法的提出验证了注意力机制和深度神经网络结合的有效性。

受文献[18,19]的启发，本文提出了一种基于注意力机制的BiLSTM-CNN模型，使用BiLSTM和CNN模型分别捕获了文本历史、未来上下文信息和局部信息，并通过注意力机制使模型更加关注文本中的带情感信息的部分，从而提高了维吾尔文情感分类的准确率。

# 1.2神经网络

由于深度神经网络相对于传统的机器学习方法拥有优秀的自学习特征提取的能力，深度学习模型在自然语言处理的各领域得到了广泛应用。CNN最初由LeCun等人[2I]提出用于计算机视觉，在计算机视觉任务中得到了很好的效果。前人已经证明CNN在潜在特征展示方面表现出色。例如词性标注、句子分类等。2014年Kim等人[使用CNN解决了情感分类问题，并通过实验证明了CNN的分类性能优于递归神经网络。Kalchbrenner等人[28]提出了一种采用 $k$ -max池化和多层卷积神经网络相结合的新颖模型。另一个流行的深度学习模型是序列模型，即循环神经网络(RNN)，它通过隐藏状态能够保留文本的历史信息，因此，它更好地捕获文本中词语之间的语义关系。RNN的变体模型已经成功应用于机器翻译、文本生成等任务。LSTM可以捕获到文本中的长依赖关系，能够从整体上理解评论信息的情感语义。

近几年来，由于CNN和LSTM的建模能力是相辅相成的，研究人员一直致力于将它们结合起来。目前未有见到融合注意力机制和深度神经网络的方法来解决维吾尔文情感分类的报道。

# 2 方法

在本章中将详细介绍维吾尔文句子情感分类的基于注意力机制的BiLSTM-CNN神经网络（AT-BiLSTM-CNN）的体系结构。本文所提出的模型主要由词向量表示层、BiLSTM层、注意力层、CNN层和情感计算层组成。每个层次的输出作为下一个网络层的输入，其中词向量表示层中词向量、词性向量、音节向量和位置向量拼接的向量作为BiLSTM网络层的输入进行训练，BiLSTM模型的输出作为注意力层的输入进行编码，注意力层的输出作为CNN网络的输入进行进一步特征提出训练，最后通过情感计算层输出情感分类结果。基于注意力机制的BiLSTM-CNN网络模型框架如图1所示。

# 2.1 词向量表示层

本文模型框架最底层是词向量表示层，是整个框架的输入。假设由 $n$ 个单词组成的句子 $S { = } \{ s _ { 1 } , s _ { 2 } , . . . , s _ { \mathrm { n } } \}$ ，每一条维吾尔文句子由词向量矩阵 $R \ o { w }$ 、词性向量矩阵RPOs、音节向量矩阵 $R _ { S Y L }$ 和位置向量矩阵RLoc构成的句子向量矩阵 $R _ { S } =$ $\left[ R _ { w } ^ { T } \oplus R _ { p o s } ^ { T } \oplus R _ { s y l } ^ { T } \oplus R _ { l o c } ^ { T } \right]$ ，其中 $\oplus$ 是向量拼接操作。

# 2.1.1词向量

词向量表示（wordembedding）[22,23]基本思想是将词语转换为计算机能够处理的低维度，稠密实数向量，将词语间的语义关系较好映射到词向量间的位置关系。词向量具有很好的计算特性，即使对词向量进行简单数学运算后，仍然可以保留文本特征信息，从而在很大程度上缓解了维度灾难。为了生成词向量查询表，本文使用对大规模无标记语料进行训练生成词向量。本文实验中利用Python库中Gensim工具的 skip-gram 模型，用大规模句子语料训练出了维吾尔文词向量模型。对于给定的语料库，本文将单词向量存储在一个词向量查询矩阵 $M = R ^ { | V | \times d _ { w } }$ 。其中： $| \boldsymbol { V } |$ 是给定无标记维吾尔文本语料库的词汇量； $d _ { w }$ 是单词向量的维数。对于句子 $S { = } \{ s _ { 1 }$ ，$s 2  , . . . , s _ { \mathrm { n } } \}$ ， $n$ 是句子长度。句子矩阵表示为 $X = \{ x \}$ ，X2，..,$\left| x _ { \mathrm { n } } \right\}$ ， $x _ { \mathrm { i } }$ 是单词 $s _ { \mathrm { i } }$ 从词向量查询矩阵 $M$ 中获取的词向量。

假设语料库由 $w _ { 1 , w _ { 2 } , \ldots , w _ { \mathrm { m } } }$ 个单词组成，Skip-Gram模型的目标是使以下函数最大化：

$$
F = \frac { 1 } { M } \sum _ { m = 1 } ^ { M } \sum _ { - n \leq j \leq n , j \neq 0 } \log p ( w _ { t + j } \mid w )
$$

其中： $n$ 是训练窗口大小的参数。本文实验在词向量模型训练中，上下文窗口大小设置为5，迭代次数为8词，分别生成了维度为100、200、300和400的词向量模型。对于未登录词，本文采用均匀分布 $U ( - 0 . 0 1 , 0 . 0 1 )$ 来随机初始化词向量。

![](images/bc28ae60110f9608c5ad02bb8e2739c46bf6f69411adb76bb0213946c0e0d4dc.jpg)  
图1基于注意力机制的BiLSTM-CNN网络模型框架 Fig.1Bilstm-CNN model based on attention mechanism

2.1.2词性向量

词性特征包含了词语丰富的语义信息，将词性特征转换成词性向量后，可以将其作为神经网络模型的输入，能够进一步发现语句中词语的结构联系以及单词情感信息。例如“"或者“Gj"等形容词可以用来表示情感强度，神经网络模型通过词性特征可以发现这样的情感词语，因此本文在本文中加入了词性特征，进一步提高了情感分类准确率。

目前，维吾尔文没有一个统一规范的词性标注集。新疆多语种信息技术实验室等各研究单位都建立了自己的词性标注集。新疆多语种信息技术实验室手工建立了包含120万个单词的词性标注集，其中包括一级词性标注集(15个标签)（表1）、二级词性标注集（71个标签）、三级词性标注集（51个标签)。

为了更好地学习句子中情感词的情感特征信息，本文在一级词性标注集的基础上增加了两个词性，即正面情感词重新标注为"POS"标签、负面情感词重新标注为"NEG"标签，使情感词的词性更加突出。实验使用17位的one-hot向量表示词性向量（以下 $\nu _ { p o s }$ 表示词性特征向量， $R _ { p o s }$ 表示词性向量矩阵)，然后与词向量、音节向量和位置向量拼接生成混合向量作为BiLSTM模型的输入，提高了情感分类的准确率。

Table 1Uyghur first level part of speech tag set   

<html><body><table><tr><td>序号</td><td>名称</td><td>标记</td><td>序号</td><td>名称</td><td>标记</td></tr><tr><td>1</td><td>名词</td><td>N</td><td>10</td><td>语气词</td><td>T</td></tr><tr><td>2</td><td>动词</td><td>V</td><td>11</td><td>标点符号</td><td>Y</td></tr><tr><td>3</td><td>形容词</td><td>A</td><td>12</td><td>附加成分</td><td>X</td></tr><tr><td>4</td><td>副词</td><td>D</td><td>13</td><td>后置词</td><td>R</td></tr><tr><td>5</td><td>代词</td><td>P</td><td>14</td><td>拉丁文</td><td>L</td></tr><tr><td>6</td><td>数词</td><td>M</td><td>15</td><td>量词</td><td>Q</td></tr><tr><td>7</td><td>连词</td><td>C</td><td>16</td><td>正面情感词</td><td>POS</td></tr><tr><td>8</td><td>模拟词</td><td>I</td><td>17</td><td>负面情感词</td><td>NEG</td></tr><tr><td>9</td><td>感叹词</td><td>E</td><td></td><td></td><td></td></tr></table></body></html>

# 2.1.3音节向量

维吾尔语中的否定词和程度词对情感词的极性和强度有很大的影响，否定词会改变情感词极性，程度词会增强或削弱句子情感强度。维吾尔语的否定句以动词的否定形式来表示，否定句中的动词作为谓语出现在句末，而句子中的否定意义通过句末尾动词加否定后缀，也就是加[，]等否定音节来表达。譬如：‘ $u _ { 3 } + u = u _ { 3 } , v$ 。同样，维吾尔语中的程度副词，通过名词和形容词词尾加表示程度的后缀，而表达句子的副词程度，构造方法是名词和形容词词尾加 $[ \lrcorner s _ { 0 }$ ，]等音节，譬如： $w _ { u ( u ) } + s _ { 0 } = s _ { 0 } z _ { u 0 } , u _ { }$ 。维吾尔语中表达否定和程度副词的方法，只要通过动词、名词和形容词词尾加表示否定和程度的音节来完成的。因此，在本文中，对给定的维吾尔情感句子，先分词再分音节，找出最关键的决定情感的最小单位进行了更细更深得研究。最终，将音节向量与词向量和词性向量拼接构成的混合向量作为模型的输入进行训练，提高了维吾尔文情感分类的准确率。维吾尔文单词可以由多个音节也可以由一个音节构成，本文可以用以下形式：

单词 $\ O =$ {音节n，音节 $\mathrm { n } { - } 1$ ，…，音节 $_ { 2 }$ ，音节 $_ 1 \}$

切分单词音节时本文使用了新疆多语种实验室开发的音节切分工具。本次实验中采用了从后向前切分的方式，也就是从一个单词的尾部音节依次提取音节。比如，给定的单词（学生们的），它的音节表示形式为$5 1 . 3 + 5 2 + 5 + 3 5 + 3 0 = 5 1 . 3 x \approx 3 5 3 0$ ，则 $F _ { \mathrm { s y l } } { = } [ F _ { \mathrm { s y l 4 } } ; ~ F _ { \mathrm { s y l 3 } } ; ~ F _ { \mathrm { s y l 2 } } ; ~ F _ { \mathrm { s y l 1 } } ] ,$ 其中： $F _ { \mathrm { s y l } } { = } [ \hat { \bar { \sqrt { \lambda } } } \mathrm { i } ]$ ， $F _ { \mathrm { s y l } 2 } { = } [ \mathcal { S } ]$ ， $F _ { \mathrm { s y l 3 } } { = } [ \tilde { \mathbf { \Omega } } ]$ ， $F _ { \mathrm { s y l 4 } } { = } [ \dot { \mathfrak { s s } } _ { 9 } ]$ 。

本次实验中，本文使用均匀分布U(-0.01,0.01)来随机生成维度为30的音节向量。

# 2.1.4情感词位置向量

本文对实验室提供的维吾尔文情感语料库进行详细统计与分析，发现具有情感的感叹词和模拟词一般出现在句首，维吾尔语中感叹词和模拟词一般出现在句首表示句子的情感强劲，后用逗号隔开，感情强烈时，可用感叹号表示。出现在句末的情感词表示肯定或否定，情感词的词性一般为动词。在句中和句末倒数第二个位置出现的词性情感词一般为形容词和程度副词。维吾尔文情感词在句子中的位置示例如表 2所示。

表1维吾尔语词性一级标记集  
表2维吾尔文情感词在句子中的位置示例  
Table 2Examples of location of Uyghur sentimental words in   

<html><body><table><tr><td colspan="3">sentences</td><td></td></tr><tr><td>序号</td><td>示例</td><td>翻译</td><td>情感词位置</td></tr><tr><td>1</td><td></td><td>歌舞太热闹了</td><td>句末</td></tr><tr><td>2</td><td></td><td>哇哇，看这些花儿</td><td>句首</td></tr><tr><td></td><td>3要是您帮我就好了</td><td></td><td>句末</td></tr><tr><td>4</td><td>这个地方太美丽了句末倒数第二</td><td></td><td></td></tr></table></body></html>

为了提高维吾尔情感分类的准确率，本文探索获取更多的情感信息作为特征，从而提高分类准确率。对实验室提供的6万多条维吾尔文情感句子中的情感词的位置进行了统计，大部分情感词出现在句首和句末(表3)。

表3维吾尔情感词在居中的位置统计

Table 3Statistics of locations ofUygur sentimental words in sentence   

<html><body><table><tr><td>序号</td><td>位置</td><td>百分比(%)</td></tr><tr><td>1</td><td>句首</td><td>21</td></tr><tr><td>2</td><td>句末</td><td>45.7</td></tr><tr><td>3</td><td>句末倒数第二位置</td><td>19</td></tr><tr><td>4</td><td>句中</td><td>14.3</td></tr></table></body></html>

在训练模型前，本文对句子中的每个单词使用one-hot表示进行向量化，如果当前单词是情感词，对应的位置设为1，否则为0。本文将情感语料库中最长的句子长度23作为位置向量维度（以下用 $\nu _ { l o c }$ 来表示位置向量， $R _ { l o c }$ 表示由位置向量组成的矩阵)。最后，将词向量、词性向量、音节向量和位置向量拼接生成的混合向量作为模型的输入进行训练。

# 2.2BiLSTM网络层

# 2.2.1长短期记忆单元LSTM

循环神经网络(recurrentneural networks,RNN)[1]作为深度学习领域比较常用的序列学习方法，通过循环递归的结构使得自身具有一定的记忆能力，理论上可以获取任意长度历史信息，然而在实际应用中经常出现梯度消失或梯度爆炸问题，从而无法学习输入序列中距离较远的逻辑关系。

为了解决RNN 模型的不足，Hochreiter 等人[20]提出了LSTM模型，替换RNN模型中的隐含层，从而避免了RNN模型的梯度消失问题。一个LSTM模型包含输入门 $i _ { \mathrm { t } }$ 、输出门 $O _ { \mathrm { t } }$ 、遗忘门 $f _ { \mathrm { t } }$ 和记忆单元 $c _ { t }$ ，其中记忆单元是核心部分，如图2所示。对于一个由 $n$ 个单词构成的维吾尔文句子的词向量序列 $S { = } \{ x _ { 1 } , x _ { 2 } , . . . , x _ { \mathrm { { n } } } \} , x _ { \mathrm { { t } } }$ 为LSTM单元在第 $t$ 步的输入，表示输入序列中单词对应的混合向量。

![](images/e528d24ff49b6da5a30b55c3642923f5712325e11f0cb26deedabc03d5641bb2.jpg)  
图2LSTM单元结构  
Fig.2Structure ofLSTM unit

LSTM单元中的三个门和记忆单元的计算如下：

$$
X = [ \ O _ { x _ { t } } ^ { h _ { t - 1 } } ]
$$

$$
f _ { t } = \sigma ( W _ { f } \cdot X + b _ { f } )
$$

$$
i _ { t } = \sigma ( W _ { i } \cdot X + b _ { i } )
$$

$$
o _ { t } = \sigma ( W _ { o } \cdot X + b _ { o } )
$$

$$
c _ { t } = f _ { t } \odot c _ { t - 1 } + i _ { t } \odot \operatorname { t a n h } ( W _ { c } \cdot X + b _ { c } )
$$

$$
h _ { t } = o _ { t } \odot \operatorname { t a n h } ( c _ { t } )
$$

在上述计算公式中： $W _ { f } , W _ { i } , W _ { o } \in \mathbb { R } ^ { m \times d }$ 表示权重矩阵；

$b _ { f } , b _ { i } , b _ { o } \in \mathbb { R } ^ { m }$ 表示偏置；o是非线性激活函数; $\scriptstyle \mathrm { m = 1 0 0 }$ 是LSTM网络的单元数量； $\odot$ 表示元素逐个点乘积；xt包含LSTM单元的输入向量； $h _ { \tau } \in \mathbb { R } ^ { m }$ 是隐藏层向量。对于一个给定的句子S={x1, $\mathbf { x } 2$ ，，xn}，每个单词xi将映射到对应的词向量$\nu _ { w } ^ { i } \in \mathbb { R } ^ { d w }$ ，每个单词的词性映射到词性向量 $\nu _ { p o s } ^ { i } \in \mathbb { R } ^ { d p }$ ,单词的音节向量映射到音节向量 $\nu _ { s y l } ^ { i } \in \mathbb { R } ^ { d s }$ ，提取当前单词的音节向量根据3.1.3节中介绍的音节切分方法，单词的位置向量映射到位置向量 $\nu _ { l o c } ^ { i } \in \mathbb { R } ^ { d l }$ （上述中 $\scriptstyle \mathrm { d w } = 3 0 0$ 、 $\mathrm { d } \mathsf { p } { = } 1 7$ 、 $\mathrm { d } \mathrm { s } { = } 3 0$ 、 $\scriptstyle 1 1 = 2 3$ 分别为词向量、词性向量、音节向量和位置向量的维度，因此在神经网络的输入层混合词向量的维度为$\mathrm { { d } \mathrm { { = } d w \mathrm { { + } d p \mathrm { { + } d s ^ { \ast } n \mathrm { { + } d l } } } } }$ ，其中 $\mathfrak { n }$ 是从单词提取到的音节特征数量，训练前人工设定)，最后拼接这些向量后生成句子向量矩阵，即

$$
[ x _ { 1 } , x _ { 2 } , . . . , x _ { n } ] \Rightarrow \big [ R _ { w } ^ { T } \oplus R _ { p o s } ^ { T } \oplus R _ { s y l } ^ { T } \oplus R _ { l o c } ^ { T } \big ] \Longrightarrow \left[ { \begin{array} { l } { \nu _ { w } ^ { 1 } \oplus \nu _ { p o s } ^ { 1 } \oplus \nu _ { s y l } ^ { 1 } \oplus \nu _ { l o c } ^ { 1 } } \\ { \nu _ { w } ^ { 2 } \oplus \nu _ { p o s } ^ { 2 } \oplus \nu _ { s y l } ^ { 2 } \oplus \nu _ { l o c } ^ { 2 } } \\ { \vdots } \\ { \nu _ { w } ^ { n } \oplus \nu _ { p o s } ^ { n } \oplus \nu _ { s y l } ^ { n } \oplus \nu _ { l o c } ^ { n } } \end{array} } \right]
$$

# 2.2.2双向长短期记忆网络

LSTM能够捕获输入序列的长期历史信息，但无法捕获未来信息。双向长短期记忆网络（BiLSTM）是由向前LSTM网络与向后LSTM网络叠加构成的网络，它使用向前和向后LSTM网络能够分别获取历史信息和未来信息，从而获取更多上下文依赖关系。向前和向后LSTM的两个隐藏状态 $\overrightarrow { h _ { t } }$ 和$\overleftarrow { h _ { \imath } }$ 分别是关于过去和未来的信息。由它们拼接生成的向量$h _ { t } = \left[ \overrightarrow { h _ { t } } , \overrightarrow { h _ { t } } \right]$ 提供了完整的上下文历史与未来信息，向前向后的输出最后是一个融合的结果ht。句子中每个单词都以词向量的形式嵌入网络，通过使用BiLSTM对维吾尔文本进行编码，实现前向的语义信息和后向的语义信息以相同的地位被考虑从而获取文本中的情感信息。

# 2.3注意力层

众所周知，根据句子的不同部分，句子的情感通常会有所不同。句子中的某些情感词或短语对于句子的情感有决定性作用，而其他单词则无关紧要。因此，本文引入了注意力机制来关注这些重要词语，并将它们的表示形式转换为句子向量。实际上，注意力机制是计算句子中的上下文向量。

本文模型中，将由词向量、词性向量、音节向量和位置向量拼接构成的词向量作为BiLSTM网络的输入进行编码，将BiLSTM网络在每个时间步骤产生的一个隐藏状态向量 $h _ { t }$ 输入到注意力模型中，采用注意力模型对维吾尔文句子进行编码。注意力模型首先使用单层感知器（MLP）对输入隐藏状态 $h _ { t }$ 进行加权，从而为输入的句子构造一个上下文相关的句子文本表示向量 $\boldsymbol { r }$ ，如式（9）所示。

$$
r _ { t } = \alpha _ { t } h _ { t }
$$

其中： $\alpha _ { t }$ 为BiLSTM网络输出的隐藏状态向量 $h _ { t }$ 的注意力权重，它与每一个时间步骤的输入状态和一个随机初始化的上下文向量 $m _ { w }$ 有关， $\alpha _ { t }$ 可以通过式（10）（11）计算得到。

$$
\alpha _ { t } = \frac { \exp ( m _ { t } ^ { T } m _ { w } ) } { \displaystyle \sum _ { t } \exp ( m _ { t } ^ { T } m _ { w } ) }
$$

$$
m _ { t } = t a n h ( W _ { w } h _ { t } + b _ { w } )
$$

式（11）中： $\textstyle \mathcal { W } _ { w }$ 为模型中的权重； $b _ { w }$ 为模型中偏置，它们与 $m _ { w }$ 一起作为模型的参数，通过不断训练学习得到。通过以上的注意力模型，可以为模型的输入构造一个定长的上下文相关的文本表示向量 $\boldsymbol { r }$ ，此向量中的信息包含各个输入状态的重要程度，使模型更加关注文本里带情感信息的情感词或短语，从而提高维吾尔文情感分类的准确率。通过这样的文本表示，可以为特征序列分配不同的注意权重。最后，可以更容易地识别诸如情感词之类的重要信息。

# 2.4CNN网络层

卷积神经网络(convolutional neural network, CNN)[9,10,21]能够捕获文本中的局部特征信息，在句子级别的情感分类任务中表现优秀[9]。因此，在本文中本文使用CNN网络作为BiLSTM模型的补充，实现了带注意力机制的BiLSTM-CNN混合模型（简称为AT-BiLSTM-CNN）。

卷积神经网络由输入层、卷积层、池化层和全连接层组成。本次实验中将注意力模型输出的 $r _ { \mathrm { t } }$ 与情感词向量 $\nu _ { e }$ 拼接的向量矩阵 $r ^ { * }$ 作为输入进行训练。即

$$
r ^ { * } { = } [ r _ { \mathrm { t } } \oplus \nu _ { e } ]
$$

卷积层使用不同的录波器对输入向量进行卷积操作，从而获取输入向量中的局部特征。其计算公式如下：

$$
u ( i ) = f ( W \bullet r _ { i : ( i + h - 1 ) } ^ { \ast } + b )
$$

其中： $r _ { i : ( i + h - 1 ) } ^ { * }$ 表示输入向量的第 $i$ 行至 $i + h - 1$ 行抽取的局部特征矩阵； $u ( i )$ 是某个卷积核在位置 $i$ 的卷积输出； $W$ 是滤波器；$b$ 是卷积偏置项； $f ( \cdot )$ 是非线性卷积核函数，本文用relu作为激活函数。

之后，最大池化层对向量 $\boldsymbol { u }$ 中所有 $u ( i )$ 求最大值以获取其中最显著的特征值，计算公式如下：

$$
\hat { c } _ { i } = \operatorname* { m a x } _ { i } \{ u _ { j } ( i ) \}
$$

其中： $j$ 表示第 $\mathrm { j }$ 个卷积核。本文实验中使用了不同尺寸的卷积核，分别为 $h { = } 3$ ， $h { = } 4$ ， $h { = } 5$ 。对于有 $T$ 个卷积核的窗口采样得到的特征信息如式（15）所示。下采样层输出的特征向量作为全连接层的输入。

$$
\hat { c } = [ \hat { c } _ { 1 } , \hat { c } _ { 2 } , . . . , \hat { c } _ { T } ]
$$

# 2.5情感计算层

本文中使用softmax 函数[24,25]作为情感分类器，将全连接层输出的特征表示 $\hat { c }$ 作为softmax函数的输出情感极性分类判别的结果，计算公式如下：

$$
\hat { y } = s o f t \operatorname* { m a x } ( W _ { f } \bullet \hat { c } + b _ { f } )
$$

其中： $\hat { y }$ 是模型预测的文本情感类别； $\mid W _ { f \natural } \ :$ bf分别是全连接层权重矩阵和偏置。

# 2.6模型训练

本文使用反向传播算法来训练和更新模型，通过最小化交叉熵来优化模型[26,27]。交叉熵损失函数的计算公式如下：

$$
l o s s = - \sum _ { i = 1 } ^ { T } \sum _ { j = 1 } ^ { C } y _ { i } \log \hat { y } _ { i } ^ { j } + \lambda \| \theta \| ^ { 2 }
$$

其中： $T$ 是训练数据集； $C$ 为情感类别数； $y$ 为文本实际情感类别；?为正则项，是损失函数的惩罚项； $\theta$ 是设置的参数。

# 3 实验准备

# 3.1情感词库的构建

情感词库包括情感词、情感短语、跟情感词搭配的否定词、副词、形容词、感叹词、语气词以及一些习惯用语构成的具有情感倾向的单词或短语。

目前尚未有公开的维吾尔文情感词库。对于资源匮乏的语言，有研究通过尝试将资源丰富的语言的情感词库翻译成资源稀缺的语言，并取得较好的分类效果。因此，本文首先使用新疆信息技术实验室开发的汉维翻译接口对目前使用率比较普遍的"HowNet"汉文情感分析词语表中的正面情感、负面情感词语、正面评价词语和负面评价词语四个情感词语表以及大学创建的"NTUSD"汉文情感词典进行翻译；然后人工对齐进行整理，去除部分翻译后失去情感倾向的单词和短语；除此之外，本文人工收集情感句子中的情感词；最后构建了包括5643个词汇的情感词典（UySentiDict)，其中正面情感词语有2411个，负面情感词语有3232个。

本文实验中将句子中的情感词转换为词向量，并与注意力层输出的隐藏状态向量拼接生成的向量作为CNN网络的输入，从而起高了情感分类准确率。

# 3.2情感分析数据集

为了构建维吾尔文句子级情感语料，本文实验选取天山网等维文网站上公开发布的文章和评论信息。本文利用实验室开发的网络爬虫工具下载网页，经过去重、去噪等操作筛选出包含情感倾向的评论信息。对收集好的语料进行分句，然后人工对其进行分类，构建了二分类（UySenti2Data)，如表4所示。

Table 4Uyghur two-group sentimental data set   

<html><body><table><tr><td>数据</td><td>正面句子</td><td>负面句子</td><td>总计</td></tr><tr><td>训练集</td><td>1.2万</td><td>1.2万</td><td>2.4万</td></tr><tr><td>开发集</td><td>0.15万</td><td>0.15万</td><td>0.3万</td></tr><tr><td>测试集</td><td>0.1万</td><td>0.1万</td><td>0.2万</td></tr><tr><td>总计</td><td>1.45万</td><td>1.45万</td><td>2.9万</td></tr></table></body></html>

除了维吾尔文情感二分类（正面、负面）语料库外，本文还构建了情感五分类（中性、高兴、生气、惊讶、难过）语料库（UySenti5Data)，如表5所示。

表4维吾尔二分类数据集  
表5维吾尔五分类数据集  

<html><body><table><tr><td>数据</td><td>中性</td><td>高兴</td><td>生气</td><td>惊讶</td><td>难过</td></tr><tr><td>训练集</td><td>1.5万</td><td>1.2万</td><td>1.2万</td><td>0.8万</td><td>0.8万</td></tr><tr><td>开发集</td><td>0.15万</td><td>0.1万</td><td>0.1万</td><td>0.1万</td><td>0.1万</td></tr><tr><td>测试集</td><td>0.1万</td><td>0.1万</td><td>0.1万</td><td>0.1万</td><td>0.1万</td></tr><tr><td>总计</td><td>1.75万</td><td>1.4万</td><td>1.4万</td><td>1万</td><td>1万</td></tr></table></body></html>

为了验证本文混合模型的有效性，在情感二分类数据集的基础上，构建了情感五分类数据集，表6中给出了每个类别的举例和对应的翻译。

Table 5Uyghur five-group sentimental data set   
表6维吾尔五分类数据举例说明  
Table 6Examples of Uyghur five-group sentimental data set   

<html><body><table><tr><td>类型</td><td>维文情感语句举例</td><td>翻译</td></tr><tr><td>中性</td><td>jlgaa y</td><td>本文在做实验</td></tr><tr><td>高兴</td><td> s </td><td>本文热爱祖国！</td></tr><tr><td>生气</td><td>ls Gil</td><td>你怎么不听话？</td></tr><tr><td>惊讶</td><td></td><td>哇，真的发生了奇迹</td></tr><tr><td>难过</td><td></td><td>哎，很遗憾，没赶上医院</td></tr></table></body></html>

# 3.3评价指标

文本情感分类作为一种文本分类任务，为了评估本文模型的情感分类性能，本文使用准确率（precision）、召回率（recall）和F值作为评价标准。计算情感分类的准确率、召回率和F1值公式如下：

$$
\left\{ \begin{array} { l l } { P = { \frac { T P } { T P + F P } } } \\ { \qquad } \\ { R = { \frac { T P } { T P + F N } } } \\ { \qquad } \\ { F 1 = { \frac { 2 \times P \times R } { P + R } } } \end{array} \right.
$$

其中：TP（truepositive）是将正类预测为正类的句子数；FN（falsenegative）是将正类预测为负类的句子数；FP是将负类预测为正类的句子数;TN是将负类预测为负类的句子数。

# 3.4数据预处理

由于从网上下载的文本语料不是规范正式，这种非正式语料通常包含URL、邮箱、各种标点符号、数字、用户名等，而这些非正式文本给情感分类带来了极大挑战。

为了去除噪声干扰，本文预先对维吾尔文情感文本语料进行预处理。其具体规则如下：a)所有数字都被替换为"0"处理。b）如果句子里存在网址和电子邮件字符串，则本文对其进行删除。c）删除除了句号、逗号、感叹号、问号以外的标点符号，以移除任何可能影响本文情感分类性能的噪声。d)如果句子中存在汉文单词则用实验室提供的汉维翻译接口对齐进行翻译，用翻译结果替换源汉文单词。e）如果情感句子中出现连续的感叹号、问号、句号或其他字符，则只保留一个对应的符号或字符。

# 3.5实验参数设置

为了达到理想的情感分类效果，本文进行了反复实验，调节了模型的超参数。通过交最小化交叉熵证来选择实验参数。单词向量维度设置为300，LSTM单元的大小设置为100。dropout设置为0.5，以防止过度拟合。使用样本数量(mini-batch)为128和Adam优化算法来训练模型。在实验中，模型训练的迭代的次数为19时达到了最好的准确率，更多细节如表7所示。

Table 7Neural network parameter setting   

<html><body><table><tr><td>网络层</td><td>超参数</td><td>取值</td></tr><tr><td>LSTM</td><td>LSTM单元数</td><td>100</td></tr><tr><td rowspan="3">CNN</td><td>滤波器窗口大小</td><td>3,4,5</td></tr><tr><td>滤波器数量</td><td>100</td></tr><tr><td>词向量</td><td>300</td></tr><tr><td rowspan="3">文本表示层</td><td>音节向量</td><td>30</td></tr><tr><td>词性向量</td><td>17</td></tr><tr><td>位置向量</td><td>23</td></tr><tr><td>注意力层</td><td>注意力隐藏层数量</td><td>100</td></tr><tr><td rowspan="5">其他参数</td><td>dropout</td><td>0.5</td></tr><tr><td>优化函数</td><td>Adam</td></tr><tr><td>样本数量(batch size)</td><td>32</td></tr><tr><td>初始学习率(learning rate)</td><td>0.01</td></tr><tr><td>网络选代次数(epoch)</td><td>19</td></tr></table></body></html>

# 3.6 实验对比模型

本文使用不同的情感分类方法与本文提出的基于多特征和注意力机制的BiLSTM-CNN 混合模型进行对比，验证本文提出的方法的有效性，并使用词向量、词性向量、音节向量和位置向量特征提高了本文方法的情感分类准确率。

a）基于情感词典的方法（SentiDict）：根据实验室构建的情感词典来对维吾尔文进行情感分类，如果句子包含正面情

感词就分为正面、如果包含负面情感词就分为负面情感句子。b）多项式朴素贝叶斯 (multinomial naive Bayes，MNB):  
是一个典型的传统机器学习方法之一，在许多文本分类和情  
感分类任务中得到了广泛应用。c)CNN模型：采用单通道和多通道卷积神经网络对维吾  
尔文句子的词向量表示进行学习，通过卷积和最大池化操作  
捕获维吾尔文句子的局部特征实现文本的情感分类。d）支持向量机（supportvector machine，SVM）模型：  
SVM是最常用的传统机器学习情感分类方法，通常采用  
n-gram 作为特征进行分类，本次实验中本文使用unigram、  
bigram和trigram作为SVM的特征进行分类。e）长短记忆网络(LSTM)：使用标准的单向LSTM网  
络对维吾尔文句子进行编码表示映射到可变长目标序列。f）双向长短记忆网络（BiLSTM）：不带注意力机制的  
BILSTM模型对维吾尔文句子进行情感分类。g）BiLSTM-CNN（BiLSTM）：不带注意力机制的  
BiLSTM-CNN混合模型对维吾尔文句子进行情感分类。h）基于注意力机制的BiLSTM-CNN（ATT-BiRNN-CNN）  
模型：本文提出的引入注意力机制的BiLSTM-CNN 混合模  
型。

# 4 实验结果及分析

为了验证本文提出的ATT-BiRNN-CNN模型在维吾尔文情感分类任务上的有效性，在实验室构建的二分类和五分类情感数据集上进行对比实验。两个情感分类数据集中分配的训练数据集、开发集和测试集的具体数据量如表4、5所示。

本文实验中选取了基于词典的分类方法、典型的传统机器学习和简单神经网络模型与本文提出的模型进行了对比。

# 4.1神经网络方法与基准方法对比实验

为了对比神经网络方法与词典方法和传统机器学习方法，第一组实验在UySenti2Data和UySenti5Data两种情感分类数据集上进行了实验。为了公平对比各方法的分类效果，除了词典方法外，其他机器学习方法和神经网络方法都只使用本文预先训练出来的维度为300的词向量作为输入进行实验，如表8所示。

表7神经网络参数设置  
表8基准模型对比实验结果  
Table 8 Benchmark model comparison experiment results   

<html><body><table><tr><td>Tablco</td><td colspan="5"></td></tr><tr><td>模型</td><td>情感2分类 准确率/% 召回率/%</td><td>F1值</td><td>准确率</td><td>情感5分类 召回率</td><td>F1值</td></tr><tr><td>词典方法</td><td>56.23</td><td>61.89</td><td>54.44</td><td>44.5</td><td>46.72</td><td>43.07</td></tr><tr><td>MNB</td><td>62.54</td><td>61.34</td><td>61.93</td><td>52.2</td><td>50.86</td><td>51.52</td></tr><tr><td>SVM-unigram</td><td>77.4</td><td>78.95</td><td>78.12</td><td>64.5</td><td>63.78</td><td>63.14</td></tr><tr><td>SVM-bigram</td><td>84.23</td><td>82.87</td><td>83.54</td><td>72.71</td><td>71.83</td><td>72.27</td></tr><tr><td>SVM-trigram</td><td>81.5</td><td>80.24</td><td>80.87</td><td>71.65</td><td>69.24</td><td>70.42</td></tr><tr><td>LSTM</td><td>72.59</td><td>71.2</td><td>71.89</td><td>59.73</td><td>58.48</td><td>59.1</td></tr><tr><td>CNN</td><td>83.65</td><td>82.64</td><td>83.14</td><td>74.51</td><td>74.24</td><td>74.37</td></tr><tr><td>BiLSTM</td><td>74.23</td><td>73.34</td><td>73.78</td><td>68.82</td><td>67.32</td><td>68.06</td></tr><tr><td>BiLSTM-CNN</td><td>85.47</td><td>84.57</td><td>85.02</td><td>74.57</td><td>73.29</td><td>73.92</td></tr><tr><td>ATT-BiLSTM-CNN</td><td>86.28</td><td>85.89</td><td>86.08</td><td>76.17</td><td>75.83</td><td>76.0</td></tr></table></body></html>

从表8可以看出，本组实验中对词典、MNB、SVM机器学习方法，以及LSTM、CNN、BiLSTM、BiLSTM-CNN、ATT-BiLSTM-CNN模型进行了分类，实验结果表明，本文提出的ATT-BiLSTM-CNN模型的二分类、五分类情感F1值均高于其他基准方法。

在实验过程发现，针对词典方法，如果情感词不在情感词典中就无法对句子进行正确分类。MNB 需要大量的语料才能达到较好的分类效果，SVM方法具有较强的泛化能力，在 SVM几个模型中 SVM-bigram 模型的表现最佳。单独深度神经网络模型中CNN模型的分类性能较好，它可以获取情感词的局部特征来提高分类效果。混合模型中本文提出的混合模型的分类效果最佳。表9是各模型对同一个语句$S = ^ { 6 6 } \cup ^ { \mathfrak { E } }$ ”（未经他人允许不要拿别人的东西）的情感五分类结果.

Table 9 Sentiment classification results of each model for same   

<html><body><table><tr><td colspan="3">instance</td></tr><tr><td>模型</td><td>情感2分类</td><td>情感5分类</td></tr><tr><td>词典方法</td><td>正面</td><td>中性</td></tr><tr><td>MNB</td><td>正面</td><td>中性</td></tr><tr><td>SVM-unigram</td><td>正面</td><td>中性</td></tr><tr><td>SVM-bigram</td><td>负面</td><td>生气</td></tr><tr><td>SVM-trigram</td><td>正面</td><td>难过</td></tr><tr><td>LSTM</td><td>正面</td><td>难过</td></tr><tr><td>CNN</td><td>负面</td><td>生气</td></tr><tr><td>BiLSTM</td><td>负面</td><td>惊讶</td></tr><tr><td>BiLSTM-CNN</td><td>负面</td><td>生气</td></tr><tr><td>ATT-BiLSTM-CNN</td><td>负面</td><td>生气</td></tr></table></body></html>

从表9中可以看出，SVM-bigram、CNN、BiLSTM-CNN模型和 ATT-BiLSTM-CNN 对实例的情感二分类和五分类结果是正确的。

# 4.2多特征对情感分类的影响

为了验证词性特征、音节特征和位置特征对情感分类的有效性，本组实验中采用不同的特征组合作为模型输入。本组实验中依次将词性向量（ $\cdot F _ { \mathrm { p o s } } )$ 、音节向量（ $F _ { \mathrm { s y l } } )$ 和位置向量（ $\cdot F _ { \mathrm { l o c } }$ ）添加到词向量（ $( F _ { \mathrm { w } } )$ 拼接生成的混合向量（ $\scriptstyle \cdot F = F _ { \mathrm { p o s } }$ $\oplus F _ { \mathrm { w } } \oplus F _ { \mathrm { s y l } } \oplus F _ { \mathrm { l o c } } ,$ ）作为模型输入进行训练。首先，本文将词性向量与词向量拼接生成的向量（ $F { = } { \cal F } _ { \mathrm { p o s } } \oplus { \cal F } _ { \mathrm { w } } { , }$ ）作为模型的输入进行训练，其二分类和五分类F1值分别提升了 $0 . 2 6 \%$ ，$0 . 9 6 \%$ 。其次，在词向量和词性向量的基础上增加了音节向量，其中 $F _ { \mathrm { s y l l } }$ 是单词最后一个音节， $F _ { \mathrm { s y l } 2 }$ 是单词最后两个音节， $F _ { \mathrm { s y l 3 } }$ 是单词最后三个音节，其他依此类推，对于音节数不够的单词进行补0的方式进处理。本次实验中尝试最多截取单词最后4个音节作为特征进行测试。从表8可以看出，$F _ { \mathrm { s y l } 3 }$ 作为特征时二分类和五分类准确率均得到了明显的提升，分别提升了 $1 . 5 7 \%$ 、 $2 . 1 9 \%$ 。最后，增加了位置向量作为词向量的补充进行训练，二分类和五分类F1值分别提升了 $3 . 0 5 \%$ $4 . 0 \%$ 。本组实验结果如表10所示。

表9各模型对同一个实例的分类结果  
表10 多特征对比实验  
[able 10Benchmark model comparison experiment results   

<html><body><table><tr><td colspan="2">模型及特征向量</td><td colspan="2">情感2分类</td><td colspan="3">情感5分类</td></tr><tr><td>模型</td><td>特征</td><td>准确率/%召回率/%F1值准确率召回率F1值</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="5"></td><td>FwFpos</td><td>87.67</td><td>86.34</td><td>87.0</td><td>77.68</td><td>76.25 76.96</td></tr><tr><td>FwFposFsyll</td><td>87.78</td><td>87.12</td><td>87.45</td><td>77.9</td><td>76.47 77.18</td></tr><tr><td>FwFposFsyl2</td><td>88.1</td><td>87.71</td><td>87.90 77.43</td><td></td><td>76.63 77.03</td></tr><tr><td>ATT-BiLSTM-CNN FwFposFsyl3</td><td>88.91</td><td>88.23</td><td>88.57 79.49</td><td></td><td>78.82 79.15</td></tr><tr><td>Fw FposFsyl4</td><td>87.82</td><td>87.24</td><td>87.53 78.67</td><td></td><td>77.29 77.97</td></tr><tr><td></td><td>FwFpos④Fsyl3 Floc</td><td>89.76</td><td>88.51</td><td>89.13 80.26</td><td>79.76</td><td>80.0</td></tr></table></body></html>

维吾尔语中兼类词和未登录词数量较多，在文本中出现次数的频繁率也高，传统统计方法和规则方法无法完全解决这些难题。

如：“”（未经他人允许不要拿别人的东西)，在这句中“"是个兼类词（动词：不要拿；名词：苹果)，在本句中是动词，除此之外，对“"进行音节切分后得到两个音节 $u _ { 0 } + u _ { 0 } = u _ { 0 } u _ { 0 } ,$ ，其中“"是句子中的表达否定意义的否定后缀，并出现在句末位置。在实验过程中发现，传统统计模型对这句话的分类结果是中性，而本文提出的混合模型使用词性向量、音节向量和位置向量后句子情感正确分类为生气类。

# 4.3网络参数对情感分类的影响

本组实验中观察优化函数、dropout、迭代次数、词向量维度等主要网络参数对情感分类的影响。首先，本文模型为了缓解过拟合，使用dropout方法进行正则化，通常情况下dropout 的值选为0.5，在本次实验中dropout 的值范围选为[0.2,0.3,0.4,0.5,0.6,0.7]进行实验，其实验结果如图3所示。其次，分别选取RMSprop、SGD、adadelta、Adam作为优化函数观察每个优化函数对情感分类的影响，当优化函数选为Adam函数时，模型达到了最好的分类效果，其实验结果如图4所示。然后，对模型训练迭代次数进行实验，当迭代次数为19时达到了最好的分类效果，其结果如图5所示。最后对词向量的维度进行实验，本文选取100、200、300、400作为词向量的维度观察其对分类效果的影响，当维度为300时达到了最好的分类效果，如图6所示。

![](images/6b441b75f70e29765d0e513b9e5b7032ed58b55eb12a8d48b73e4a08ce0199bb.jpg)  
图3dropout参数实验结果

![](images/846ee3f3b31109ad749baeb01466bca5e91c03bba4cd1e8bc1d0448586e08843.jpg)  
Fig.3Dropout parameter experiment result   
图4优化函数实验结果

![](images/71cc9162fc7352d21383a68d91517e41f32a1d371b51edc8bcfe1a7e4d353a33.jpg)  
Fig.4Optimization function experiment result   
图5优化函数实验结果  
Fig.5Experimental results of training epoches

![](images/98446fabfd3420c82b6214fbbd5249f3d3f5afc37047374162f1ed781039b46a.jpg)  
图6优化函数实验结果  
Fig.6Experimental results ofword vector dimensions

# 5 结束语

本文针对维吾尔文情感分类任务，提出了一种多特征与带注意力机制的深度学习方法融合的混合模型。首先将词性特征、音节特征和位置特征向量作为词向量的补充，有效地将维吾尔文句子映射到低维抽象特征矩阵，并使用拼接生成的混合向量挖掘单词本身固有的特性；然后通过BiLSTM网络对文本进行编码，获取了文本历史上下文依赖信息；随后通过注意力机制更加关注文本中的带情感信息的词语，并将情感词向量与注意力层的输出的隐藏状态向量的拼接向量作为CNN网络的输入，从而获取了文本带有情感信息的局部信息；最后使用softmax 函数得到了情感分类结果。实验结果表明，本文提出的混合模型在维吾尔文情感二分类和五分类任务的准确率、召回率和F1值上要明显高于传统机器学习方法和简单深度学习方法，本文模型的有效性得到了验证。在今后的工作中，本文将本文模型应用到其他NLP任务中评估其效果，并进一步对其网络参数进行优化和改进。

# 参考文献：

[1]Shin B,Timothy L,Jinho C.Lexicon integrated CNN models with attention for sentiment analysis[J].arXiv preprint arXiv:161o.06272, 2016.   
[2]赵妍妍，秦兵，刘挺．文本情感分析[J]．软件学报．2010,21(8): 1834-1848.(Zhao Yanyan,Qin Bing,Liu Ting. Sentiment analysis [J]. Journal of Software.2010,21(8):1834-1848.)   
[3]Pang B,Lee L,Vaithyanathan S.Thumbs up?:Sentiment classification using machine learning techniques [C]//Proc of ACL-O2 Conference on Empirical Methods in Natural Language Processing.[S.l.]:Association for Computational Linguistics,20o2:79-86.   
[4]Wang Yequan,Huang Minlie,Zhu Xiaoyan,et al.Attention-based LSTM for aspect-level sentiment classification [C]//Proc of Conference on Empirical Methods in Natural Language Processing.2O16: 606-615.   
[5]Tong Yixuan，Zhang Yangsen，Jiang Yuru.Study of sentiment classification for Chinese microblog based on recurrent neural network [J].Chinese Journal of Electronics.2016,25 (4): 601-607.   
[6]刘金硕，李哲，叶馨，等．文本情感倾向性分析方法：bfsmPMI-SVM. 武汉大学学报：理学版[J].2017,63(3):259-264.(Liu Jishuo,Li Zhe, Ye Xin,et al.Sentiment orientation of text:bfsmPMI-SVM[J].Journal of Wuhan University:Natural Science Edition [J].2017,63 (3): 259-264.)   
[7]Zhang Dongwen，Xu Hua,Su Zengcai,et al.Chinese comments sentiment classification based on word2vec and SVM perf[J].Expert Systems with Applications.2015,42 (2):1857-1863.   
[8]Wang Jin,Yu Liangchih,Robert Lai K,et al.Dimensional sentiment analysis using a regional CNN-LSTM model [C]// Proc of the 54th 225-230.   
[9] Yoon Kim. Convolutional neural networks for sentence classification [C]// Proc of Conference on Empirical Methods in Natural Language Processing. 2014: 1746-1751.   
[10] Gichag L, Jeong J,Seungwan S,et al. Sentiment clasification with word localization based on weakly supervised learning with a convolutional neural network [J]. Knowledge-Based Systems,2018, 152(7): 70-82.   
[11] Hochreiter S,Schmidhuber J. Long short-term memory [J].Neural Computation.1997,9 (8): 1735-1780.   
[12] Miyazaki R,Komachi M. Japanese sentiment classification using a tree-structured long short-term memory with attention [Z]. 2017.   
[13] Kuta M,Morawiec M,Kitowski J. Sentiment analysiswith tree-structured gated recurrent units [Z]. 2017.   
[14] Mnih V.，Heess N.,Graves A.，et al.Recurrent models of visual attention [C]// Advances in Neural Information Processing Systems, 2014: 2204-2212.   
[15] Bahdanau D,Cho K,Bengio Y. Neural machine translation by jointly learming to align and translate [J]. Computer Science,2014.   
[16] Tang Duyu,Qin Bing,Liu Ting.Document modeling with gated recurrent neural network for sentiment classification [C]// Proc of Conference on Empirical Methods in Natural Language Processing. 2015: 1422-1432   
[17] Luong M T,Pham H, Manning C D. Effective approaches to attention-based neural machine translation [J].Computer Science,2015: 1412-1421   
[18] Wu C,Wu F,Liu J,et al.THU_NGN at SemEval-2018 task 1: fine-grained tweet sentiment intensityanalysiswith attention CNN-LSTM[C] /Proc of the 12th International Workshop on Semantic Evaluation. 2018:186-192.   
[19] Yin Wenpeng,Schuitze H,Xiang Bing,et al.ABCNN:attention-based convolutional neural network for modeling sentence Pairs [J]. Transactions of the Association for Computational Linguistics,arXiv preprint arXiv:1512.05193,2015.   
[20] Hochreiter S,Schmidhuber J.Long short-term memory [J].Neural Computation,2012,9(8): 1735-1780.   
[21] Lecun Y,Bengio Y,Hinton G.Deep learning [J]. Nature.2015,521 (7553) :436-444.   
[22] Mikolov T,Chen Kai, Corrado G,et al.Efficient estimation of word representations in vector space [C/OLl//Proc of Workshop at ICLR. 2013.arXiv: 1301.3781.   
[23] Mikolov T, Sutskever I, Chen Kai, et al.Distributed representations of wordsand phrases and their compositionality[C/OL]// Advances in Neural Information Processing Systems,2013,arXiv: 1310. 4546.   
[24] Rush A M,Chopra S,Weston J.A neural attention model for sentence summarization [C]//Proc of Conference on Empirical Methods in Natural Language Processing.2015: 379-389.   
[25] Feng Shi,Wang Yang,Liu Liran,et al.Attention based hierarchical LSTM network for context-aware microblog sentiment classification [J]. World Wide Web,2018 (2): 1-23.   
[26] Rush A M, Chopra S,Weston J. A neural atention model for sentence summarization [Cl// Proc of Conference on Empirical Methods in Natural Language Processing.2015: 379-389.   
[27] Wang Yequan,Huang Minlie,Zhu Xiaoyan，et al. Attention-based LSTM for aspect-level sentiment classification [Cl//Proc of Conference

on Empirical Methods in NaturalLanguage Processing.2O16:606-615. [28] Kalchbrenner N,Grefenstette E,Blunsom P.A convolutional neural network for modelling sentences[Cl// Proc of the 52nd Annual Meeting of the Association for Computational Linguistics.2014:1749-1751.