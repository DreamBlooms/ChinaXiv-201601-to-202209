# 基于双通道特征融合的WPOS-GRU专利分类方法

余本功ab，张培行a

(合肥工业大学 a.管理学院;b.过程优化与智能决策教育部重点实验室，合肥 230009)

摘要：为提高专利文本的自动分类的效率和准确度，提出一种双通道特征融合WPOS-GRU(word2vec and part ofspeech gated recurrentunit)专利文本自动分类方法。首先获取专利摘要文本，并进行清洗和预处理；然后对专利文本进行词向量表示和词性标注，并将专利文本分别映射为Word2vec词向量序列和POS词性序列；最后使用两种特征通道训练WPOS-GRU模型，并对模型效果进行实验分析。通过对比传统专利分类方法和单通道专利分类方法，双通道特征融合的WPOS-GRU专利分类方法提高了分类效果。本文提出的方法节省了大量的人力成本，提高了专利文本分类的准确度，更能满足大量专利文本分类任务自动化高效率的需要。

关键词：专利分类；词性标注；特征融合；门限递归单元 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.08.0628

WPOS-GRU patent classification method based on dual channel feature fusion

Yu Bengonga,b, Zhang Peihanga (1.School of Management,b.Key Laboratory of ProcessOptimization&Intelligent Decision-Makingof Ministryof Education,Hefei University of Technology,Hefei 2300o9,China)

Abstract: In order to improve theeficiencyand accuracy of patent text automatic classfication,this paper proposes a two-channel feature fusion WPOS-GRU patent text automatic clasification method.Firstly,the patent summary text is obtained,cleanedand pretreated,thenthe patenttextisrepresentedby word vectorand part-of-speech tagging,and the patent text is mapped into word 2vec word vector sequence and POS part-of-speech sequence,respectively.Finaly, WPOS-GRU model is trained bytwo featurechannels，and the effect of the model is analyzed experimentally.By comparing the traditional patent clasification method with the single-channel patent classification method,the WPOS-GRU patent classification method with two-channel feature fusion improves the classification efect.The method proposed in this paper saves a lot of manpower costs,improves the accuracyof patent text clasification,and can met the needs of automation and high efficiency of a large number of patent text classification tasks.

Key words: patent classification; part of speech tagging; feature Fusion; GRU

# 0 引言

近年来，科技创新越来越引起人们的重视，而专利作为创新的重要记录载体，也呈现出爆炸增长的态势[I]。据在专利申请领域，在2016年的一年时间内，中国共受理专利申请130万件，且呈逐年上升趋势。如此海量的专利数据，通过人工分类需要巨大的人力成本，处理效率无法满足实际需要，专利的自动分类方法研究的重要性日渐突显，已成为现阶段一个重要的研究热点问题。目前，专利分类研究多采用IPC分类体系，IPC分类是一种层次结构分类体系，包括部、大类、小类、组等层次，是世界上使用较多普遍认可的一种分类体系。目前，相关研究者通过机器学习来处理专利自动分类问题，通过进行文本分析，提取文本中关键的特征词，并结合机器学习分类器完成分类，取得不错的效果。最近几年，深度学习在自然语言处理领域取得了很好的效果，且端到端的处理流程更能满足专利自动分类的需要，使用深度学习模型实现专利的自动分类是一种较好的解决思路。

# 1 相关工作

专利文本是科技创新的一种重要表现形式，对专利的分析和利用一直被世界各国所重视，专利的自动分类，对专利审核、专利检索有着非常重要的意义。使用机器学习进行专利分类一直是该问题的研究热点。李生珍等人[2对文本进行分词并提取特征词，将专利文本映射成特征向量，并使用BP神经网络构建分类器，马芳等人[3使用径向基函数神经网络构建分类模型，并设计了专利自动分类系统。相比于普通文本，专利文本具有其自身的殊性，有针对的构建分类器，更能适应专利自动分类的需要[4]。屈鹏等人[5]认为专利文本有较明显的专业特征，使用专业术语构建特征能提高专利分类的效果，并使用朴素贝叶斯、SVM等分类器进行实验，对比了机器学习相关分类器的效果。基于向量空间模型的分类方法，忽略了词语间的语义信息，廖列法等人[认为用主题代替传统的向量空间模型，在构建分类器时考虑到了语义信息。

深度学习近些年的飞速发展，为自然语言处理很多问题提供了新的解决思路，尤其在文本分类问题上表现出良好的性能。一些学者通过自动编码机来处理特征，提取出文本中深层次的信息[7]，受此启发，马双刚[8将自动编码机应用在专利自动分类中，并取得了不错的效果。目前相关研究者对专利自动分类的研究多集中在特征提取和处理上，而端到端和深度神经网络可以摆脱特征工程的束缚，更适合大量专利数据自动分类的需要[9]。在深度学习模型中，首先要进行word2vec词向量训练，将词映射成一个低维的向量，解决了传统词袋模型词向量维度过大的难题[1o]，且word2vec 向量的训练过程结合了词的上下文内容，包含了词的语义信息，在深度学习研究中应用较多。Kim等人[II使用卷积神经网络构建文本分类器，提取文本深层次的特征，不需要人工干预，相比于传统人工提取特征的方法，更高效快捷，在分类效果上也更优于传统方法。胡杰等人[12]使用卷积神经网络进行特征提取，并使用随机森林构造分类器对专利文本进行分类，通过对比随机森林等方法，该方法较好的提升了分类效果。一些研究者认为，卷积神经网络有着局部联接的特点，所以在提取特征的过程中，会忽略文本的结构特征，而LSTM和GRU等循环神经网络模型是一种序列模型，更适合文本特征的提取[13:14]。王树恒等人[15]使用双向的 LSTM 模型对文本情感进行分类，通过实验LSTM 获得了比CNN更好的分类准确率。李雪莲等人[6通过对比实验分析了LSTM和GRU模型结构和性能，并指出GRU模型继承了LSTM自动学习的功能，但其结构更为简单，大大缩短了模型训练时间，更适合大量文本数据的研究应用。深度学习方法应用在舆情发现、情感分析等方面取得了很好的成绩，而鲜有研究者将深度学习方法用于专利自动分类领域。本文分析了专利文本的特点，提取专利摘要文本，结合LSTM深度学习模型完成专利摘要文本的自动分类。此外，每个词都有不同的词性，词性包含了一些重重要的语义内容[7]，尤其在专利文本中，如名词的重要性一般较高，而word2vec词向量模型忽略了词性信息，所以本文在GRU的基础上，将文本的word2vec 词向量和词性信息进行结合，实现语义和词性双通道建模，提出了双通道特征融合的WPOS-GRU专利摘要自动分类方法。

# 2 相关关键技术

# 2.1word2vec 词向量训练和 POS 词性标注

word2vec模型由Mikolov等人研发的词向量表示工具，包括CBOW模型和Skip-gram 模型，本文使用CBOW模型实现词向量训练。CBOW模型结构如图1所示，包括输入层、映射层和输出层。

![](images/132a7b6c4dc31697adda04924c80b31d8a5e624b2a0ec9fe79480af5817a3548.jpg)  
图1Skipgram 模型结构图  
Fig.1Skipgram model structure diagram

输入层为一个滑动窗口，将该词上下文的n个词向量输入到模型，输出当前词的向量表示。因为其在词向量表示时，考虑到词的上下文信息，所以最终的词向量表示了一定的语义信息，可以通过向量距离计算来求两个词的相似度。

词性标注是自然处理中很重要的工作，主要包括基于规则的方法、基于统计的方法和机器学习方法，常被用于机器翻译、文字识别等领域，为每个词赋予其对应的词性，作为后面语义分析的基础工作。本文使用的词性标注标准为中科院计算所标注集，包括名词、时间词、处所词、方位词、动词、形容词等类别。该标注标准标注信息较为详细，在相关研究中应用较广。

# 2.2GRU循环神经网络模型

GRU循环神经网络模型在传经循环神经网络中加入门的因素，可以保留更长距离的记忆，相比于LSTM，其减少了门的数量，并将LSTM隐层状态和细胞状态合并，减少了冗余信息，所以其模型效果和LSTM相似，而由于参数的减少，计算效率大大提高。GRU包括更新门和控制门，是控制信息选择性通过的机制，由一个sigmoid神经网络层和一个向量点乘组成。门元素的值在[0,1]，当值为1时表示信息完全通过，当值为0时表示信息完全阻塞。GRU结构信息如图2 和式(1)所示。

![](images/d2e8fd339ed5a4bd9f29365a80da26e9506ba79282bf23c17865ecaab64e8e52.jpg)  
图2GRU节点结构图  
Fig. 2 GRU node structure diagram

$$
\begin{array} { r l } & { z _ { t } = \sigma ( U _ { z } x _ { t } + W _ { z } h _ { t - 1 } + b _ { z } ) } \\ & { r _ { t } = \sigma ( U _ { r } x _ { t } + W _ { z } h _ { t - 1 } + b _ { z } ) } \\ & { s _ { t } = \operatorname { t a n h } ( U _ { s } x _ { t } + W _ { s } \cdot r _ { t } * h _ { t - 1 } + b _ { s } ) } \\ & { h _ { t } = ( 1 - z _ { t } ) * h _ { t - 1 } + z _ { t } * s _ { t } } \end{array}
$$

其中： $z _ { t }$ 代表更新门，用来控制当前输入所占的比重， $R _ { t }$ 为重置门，用来控制上一步的记忆中哪些对当前输入起作用。$W _ { z }$ Wr, $W _ { s }$ 代表权重 ${ } _ { J _ { z } b _ { r } b _ { s } }$ 代表偏置量 $\circ X _ { t }$ 代表t时刻的输入，$s _ { t }$ 代表需要更新的信息， $h _ { t }$ 代表t时间步的隐藏层状态， $\sigma$ 代表非线性函数。

# 3 基于双通道特征融合的WPOS-GRU专利摘要的自动分类模型

本文首先对文本数据进行预处理，包括数据清洗、分词、去停用词等工作，然后对文本进行词向量表示和词性标注，并将词向量和标注信息输入进双通道GRU循环神经网络模型，完成训练，最后使用该模型对文本进行分类测试。

# 3.1专利数据获取及数据预处理

专利数据包括题目、摘要、正文、主分类号等文本项，其中摘要文本中包含了该篇专利的核心内容，阅读者通过阅读专利摘要就可以对该专利的类别有所把握，而阅读全文则需要耗费大量时间成本，所以本文需要的获取专利的摘要文本信息和主分类号。

对专利摘要文本进行数据清洗，除去因网络来源产生的噪声，然后进行分词和词性标注处理，词性标注采用中科院计算所的标注标准。对分词和标注后的结果进行向量表示，将词和标注信息分别映射成低维向量。

# 3.2专利文本分类模型

在专利摘要文本中，相比于其他文本数据，语言较为领域化专业化，且其专业术语较广，传统基于特征词的方法无法对术语词进行很好的覆盖，一旦有新的术语词出现，特征向量就要重新设计。所以本文提出基于循环神经网络的方法，其方法通用性较强，新术语词往往是由旧词组成的短语，通过旧词的词向量计算，可以得出新短语的word2vec语义。无须人工提取特征，适用专利摘要文本特征词提取不方便的特征，节约了大量的人力成本，更适应大量专利数据自动分类的需要。本文考虑到专利文本中，不同的词性所代表的重要性不同，而word2vec词向量忽略了词性信息，所以本文在GRU的基础上，提出了融合词性信息的专利分类模型WPOS-GRU。其中词性信息包含了一定的语义信息，可以单独输入模型，也可以作为word2vec向量的补充内容，所以本文设计了word2vec单通道特征GRU、POS单通道特征GRU和双通道融合特征WPOS-GRU三种模型结构,并进行对比实验。

# 3.2.1双通道融合特征WPOS-GRU模型

双通道特征融合WPOS-GRU模型包括word2vec和POS两个通道，其模型结构如图3所示。

![](images/5f53353e91e24ff114c74fef920c9eb0a8d0e20340fccc81cd2e863d6f49e47e.jpg)  
图3双通道特征融合WPOS-GRU结构

$\textcircled{1}$ 表示映射层，即将摘要中的词映射成向量的形式。仍以“保证加强板刚性结构，使其具有良好的承载能力和抗机械冲击能力"为例，将“保证、加强"等词分别映射成word2vec词向量和POS词性向量。

$\textcircled{2}$ 表示GRU序列层。将上一层映射后的word2vec词向量序列和POS词性向量序列分别按照词序输入到第一层GRU的每一个时间步中，每层GRU的输出结果作为下一层GRU 的输入，最后一层GRU节点只保留最后一个节点的输出。其中word2vec词向量特征通道的GRU序列输出为O1,POS词性向量特征通道的GRU序列输出为O2.

$\textcircled{3}$ 表示融合层，将word2vec词向量通道深层GRU输出向量O1和POS词性特征通道GRU输出向量O2进行拼接，拼接后的向量表示为O。

$\textcircled{4}$ 表示全连接层，假设该专利数据集共包含n个类别，全连接层的节点数为n，将融合层的输出向量映射成n维向量。

$\textcircled{5}$ 表示softmax分类层，对上一层的输出向量进行规一化，得到新的 $\mathfrak { n }$ 维向量，其中每个元素代表属于该类别的概率。

其模型训练过程如下：

多通道特征融合WPOS-GRU算法流程输入：训练集 $\mathrm { D { = } \{ ( x _ { k } , p _ { k } , y _ { k } ) \} ^ { m _ { k = 1 } } }$ ，超参数：0。初始化训练参数W

repeat  
for all $( \mathbf { x } _ { \mathrm { k } } , \mathbf { p } _ { \mathrm { k } } , \mathbf { y } _ { \mathrm { k } } ) \in \mathbf { D }$ do  
1 计算当前样本的输出y'k  
2 计算输出y'k和样本标签y的差值E3根据E计算各参数的梯度  
4更新各参数的值  
end for  
until:训练误差收敛到一个比较小的值。输出：各训练参数确定的分类网络。

其中：D为 $\mathbf { m }$ 篇专利摘要训练集， $\mathbf { x } _ { \mathbf { k } }$ 表示第 $\mathbf { k }$ 篇专利摘要的词向量表示序列，pk表示第 $\mathbf { k }$ 篇文档的词性向量表示序列，$\mathrm { y } _ { \mathrm { k } }$ 为第k篇文档的类别向量, $\mathbf { y } _ { \mathrm { ~ k ~ } } ^ { \ast }$ 表示第k篇文本预测类别向量。

# 3.2.2单通道特征GRU模型

单通道特征GRU模型只有一个通道，word2vec通道或者POS通道结构如图4所示。

$\textcircled{1}$ 表示映射层，即将摘要中的词映射成向量的形式。以“保证加强板刚性结构，使其具有良好的承载能力和抗机械冲击能力”为例，将“保证、加强”等词映射成向量形式，在word2vec单通道特征GRU模型中，将词映射成word2vec向量；在POS单通道特征GRU模型中，将词映射成POS词性标注向量。

$\textcircled{2}$ 表示GRU序列层。将上一层映射后的向量序列按照词序步输入到第一层GRU的每一个时间步中，每层GRU的输出结果作为下一层GRU的输入，最后一层GRU节点只保留最后一个节点的输出。

![](images/56b379c4488078b7d00e932daca94f70d5d891fc0e2b459a95857555e91daac5.jpg)  
Fig.3Dual channel feature fusion WPOS-GRU structure   
图4单通道特征GRU模型结构  
Fig.4Single channel characteristic GRU model structure

$\textcircled{3}$ 表示全连接层，假设该专利数据集共包含n个类别，全连接层的节点数为n，将GRU序列层的输出映射成 $\mathfrak { n }$ 维向量。

$\textcircled{4}$ 表示softmaxt分类层，对上一层的输出向量进行规一化，得到新的 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 维向量，其中每个元素代表属于该类别的概率。

其模型训练过程如下：  
word2vec 单通道特征GRU算法流程输入：训练集 $\scriptstyle \mathrm { D = } \{ ( \mathbf { x } _ { \mathbf { k } } , \mathbf { y } _ { \mathbf { k } } ) \} ^ { \mathrm { m } } _ { \mathbf { k } = 1 }$ ，超参数：0。初始化训练参数W

repeat

for all $( \mathbf { x } _ { \mathrm { k } } , \mathbf { y } _ { \mathrm { k } } ) { \in } \mathbf { D }$ do  
1 计算当前样本的输出y'k  
2 计算输出y'k和样本标签y的差值E3根据E计算各参数的梯度  
4更新各参数的值  
end for  
until:训练误差收敛到一个比较小的值。输出：各训练参数确定的分类网络。

其中：D为 $\mathbf { m }$ 篇专利摘要训练集， $\mathbf { x } _ { \mathbf { k } }$ 表示第 $\mathbf { k }$ 篇专利摘要的词向量表示序列， $\mathrm { y } _ { \mathrm { k } }$ 为第 $\mathbf { k }$ 篇文档的类别向量，yk表示第 $\mathbf { k }$ 篇文本预测类别向量。

POS单通道特征GRU算法流程  
输入：训练集 $\scriptstyle \mathrm { D = } \{ ( { \mathrm { p } } _ { \mathrm { k } } , { \mathrm { y } } _ { \mathrm { k } } ) \} ^ { \mathrm { m } } _ { \mathrm { k } = 1 }$ ，超参数：0。初始化训练参数W  
repeat  
for all $( \mathsf { p } _ { \mathrm { k } } , \mathsf { y } _ { \mathrm { k } } ) \in \mathsf { D }$ do  
1 计算当前样本的输出y'k  
2 计算输出y'k和样本标签 $\mathsf { y }$ 的差值E  
3 根据E计算各参数的梯度  
4更新各参数的值  
end for  
until:训练误差收敛到一个比较小的值。  
输出：各训练参数确定的分类网络。

其中：D为m 篇专利摘要训练集， $\mathbf { X } \mathbf { k }$ 表示第k篇专利摘要的词性向量序列，yk为第k篇文档的类别向量，yk表示第k篇文本预测类别向量。

# 3.3模型评价

为设计对比实验，评价本文方法的可行性，本文首先对所有摘要数据划分训练集和验证集。使用上述算法完成模型训练，然后使用精度、准确率、召回率和F1值来对模型效果进行评价。

精度accuracy指的是正确分类的专利文本数T和专利文本总数N的比值，如式（2）所示。

$$
a c c u r a c y = \frac { T } { N }
$$

准确率Precision指的是预测为该类别的专利文本中，实际属于该类别的比例，如式（3）所示，其中TP表示预测为该类别且预测正确的文档数，FP表示预测为该类别且预测错误的文档数。

$$
p r e c i s i o n = \frac { T P } { T P + F P }
$$

召回率Recall指的是实际属于该类别的专利文档中，被预测出来的比例，如式（4）所示，其中TP表示预测为该类别且预测正确的文档数，FN表示实际属于该类别但预测错误的文档数。

$$
r e c a l l = \frac { T P } { T P + F N }
$$

F1值同时兼顾了准确率和召回率，如式（5）所示。

$$
F 1 = \frac { 2 \cdot p r e c i s i o n \cdot r e c a l l } { p r e c i s i o n + r e c a l l }
$$

# 4 实验分析

# 4.1专利数据获取及数据预处理

本文在进行实验时，选择了作者较为熟悉的计算机领域，参考文献[8]选择专利的方法，进行专利文本的分类实验。首先在SooPAR专利搜索引擎上选择中国专利“计算机”主题，专利类型限定为发明专利，检索出和计算机相关的专利文本的主分类号有G06F1/16、G06F1/18、G06F1/20、G06F3/02、G06F3/14五个类别，类别粒度为小组级别。然后在上海知识产权上平台上检索这五个类别的专利，为保证时效性，选择了近4年的专利数据，每个类别选择2000篇进行下载。对下载后的专利数据进行筛选去重，保留专利摘要文本并分类存储。

对摘要文本进行分词和去停用词处理。本实验使用jieba分词工具，该工具分词效果较好，相关研究中使用较多。

因word2vec训练需要大文本语料集，所以本文将维基百科文本和专利文本进行组合，其中维基百科库为网络公开数据，大小约1.3GB，专利数据共10000条。通过组合，既满足大文本语料的要求，也包含了领域信息，保证了词向量训练的效果。最后使用word2vec 模型将评论文本中的词映射成100维向量。

本文词性标注使用jieba工具包，标注标准为中科院计算所的标注集，该标注集较多全面，能为自然语言处理相关工作提供辅助，在相关研究中使用较多。对词性标注内容进行onehot编码，编码成长度为50的向量，如形容词a标注为[0,0,1,00,...]，其中a对应向量中第三个位置。

# 4.2模型训练

本文实验环境配置如表1所示。

表1实验环境参数  
Table1Experimental environmental parameters   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>处理器</td><td>Intel(R CoreTM i5-7300 HQ CPU @ 2.50GHz</td></tr><tr><td>内存</td><td>8GB</td></tr><tr><td>显卡</td><td>NVIDIAGeForceGTX1050</td></tr><tr><td>编程语言</td><td>Python 3</td></tr><tr><td>深度学习库</td><td>Tensorrflow+Keras</td></tr></table></body></html>

GRU循环神经网络序列长度为句子长度，GRU节点数取50，100，150时取得较高的F1值，由于专利文本分类需要较高效率，所以本文节点数定为50。

本文将五个类别的10000 专利文本划分训练集和验证集，其中训练集为8000条，验证集为2000条。模型训练过程中，使用交叉熵作为损失函数，使用Adam方法作为优化函数，模型训练三个epoch后收敛。

为验证本文方法的有效性，分别训练本文三个模型，并设计对比实验，将本文方法与专利分类中常用的NB（朴素贝叶斯）、SVM（支持向量机）、NN（神经网络）和RF（随机森林）相对比，实验结果如表2和图5所示。此外，为验证不同词性的重要程度不同，本文使用仅名词、仅形容词、仅动词的词向量训练word2vec 单通道特征GRU，得出评价结果。

通过对比实验可以看出，在传统机器学习模型中,神经网络表现最好，分类精度为0.92；本文提取的三种方法中，word2vec单通道特征GRU分类精度为0.95，相比传统方法提升较大，所以将深度学习方法应用到专利分类中是有重要价值的；训练单通道特征GRU，若仅使用名词训练，分类精度为0.91，使用动词训练，分类精度为0.81，而仅使用形容词训练，分类精度仅为0.53，说明不同词性的词对分类的贡献是不同的，名词包含的信息量最大；此外，pos单通道特征GRU分类精度为0.46，在五分类实验中，随机值为0.2，说明使用词性特征包含了较多的语义信息，双通道融合后模型分类精度在0.974，能够完成专利文本自动分类任务。从

F1上看，双通道特征融合WPOS-GRU效果也较好，相比传统方法和单通道特征也有较大提升。

# 5 结束语

专利作为科技创新的一种重要表现形式，专利文本的分类，对于专利的分析利用有很重要的作用。本文结合深度学习技术，就大量专利文本的自动高效的分类问题，提出了双通道特征融合WPOS-GRU专利自动分类模型，该模型通过引入词性语义信息，提高了专利文本自动分类的准确度，使得专利自动分类结果更可靠实用。但本文方法仍存在一些不足，如一些新生类别下缺少专利文本数据，本文方法表现可能不佳。

# 表2对比实验结果

Table 2 Contrast experiment results   

<html><body><table><tr><td></td><td>acc</td><td>pre</td><td>recall</td><td>f1</td></tr><tr><td>NB</td><td>0.8177</td><td>0.8238</td><td>0.8087</td><td>0.8162</td></tr><tr><td>SVM</td><td>0.8374</td><td>0.8453</td><td>0.7639</td><td>0.8025</td></tr><tr><td>RF</td><td>0.9078</td><td>0.9631</td><td>0.8799</td><td>0.9196</td></tr><tr><td>NN</td><td>0.9225</td><td>0.9533</td><td>0.9163</td><td>0.9345</td></tr><tr><td>pos</td><td>0.4664</td><td>0.4857</td><td>0.6292</td><td>0.5482</td></tr><tr><td>word2vec</td><td>0.9501</td><td>0.9322</td><td>0.9423</td><td>0.9372</td></tr><tr><td>名词</td><td>0.9161</td><td>0.9141</td><td>0.9101</td><td>0.9121</td></tr><tr><td>动词</td><td>0.8365</td><td>0.8357</td><td>0.8044</td><td>0.8198</td></tr><tr><td>形容词</td><td>0.5778</td><td>0.5907</td><td>0.4927</td><td>0.5373</td></tr><tr><td>WPOS-GRU</td><td>0.9740</td><td>0.9707</td><td>0.9671</td><td>0.9689</td></tr></table></body></html>

![](images/3c502d060ebd6f58209a88cd6c778eb9c09e9db02a467c6a0b332bd7d0f5fa70.jpg)  
图5对比实验结果  
Fig.5Contrast experiment results4.3 实验结果分析

# 参考文献：

[1]WIPO.World intellectual property report 2017 [EB/OL].(2017-12-06). http://www.wipo.int/edocs/pubdocs/en/wipo_pub_944_2017.Pdf.   
[2]李生珍，王建新，齐建东，等．基于BP神经网络的专利自动分类方 法[J]．计算机工程与设计,2010,31(23):5075-5078.(Li Shengzhen, Wang Jianxin,Qi Jiandong,et al.Automated categorization of patent based on back-propagation network [J].Computer Engineering and Design.2010,31(23):5075-5078.)   
[3]马芳．基于RBFNN的专利自动分类研究[J].现代图书情报技术， 2011(12):58-63.(Ma Fang.Research of patent automatic classification based on RBFNN [J].New Technology of Library and Information Service,2011(12):58-63.)   
[4]刘红光，马双刚，刘桂锋．基于机器学习的专利文本分类算法研究 综述[J].图书情报研究，2016(3):79-86.(Liu Hongguang，Ma Shuanggang,Liu Guifeng.A review of research on patent document classification algorithms based on machine learning [J].Library and Information Studies,2016 (3):79-86.)   
[5]屈鹏，王惠临．专利文本分类的基础问题研究[J].现代图书情报技 术,2013,29(3):38-44.(Qu Peng,Wang Huilin.Fundamental research questions in patent text categorization [J].New Technology ofLibrary and Information Service,2013,29(3):38-44.)   
[6]廖列法，勒孚刚，朱亚兰.LDA 模型在专利文本分类中的应用[J]. 现代情报,2017,37(3):35-39.(Liao Liefa,Le Fugang,Zhu Yalan. The application of LDA model in patent text classification [J].Journal of Modern Information,2017,37(3):35-39.)   
[7]刘勘，袁蕴英．基于自动编码器的短文本特征提取及聚类研究[J]. 北京大学学报:自然科学版，2015,51(2):282-288.(Liu Kan，Yuan Yunying. Short Texts Feature Extraction and Clustering Based on Auto-Encoder[J].ActaScientiarumNaturaliumUniversitatis Pekinensis,2015,51(2):282-288.)   
[8]马双刚．基于深度学习理论与方法的中文专利文本自动分类研究 [D]．镇江：江苏大学，2016.(Ma Shuanggang.Study of automatic Chinese patent classification based on deep learning theory and method[D].Zhenjiang: Jiangsu University,2016.)   
[9]Tajbakhsh N,Suzuki K.Comparing two classes of end-to-end machine-learning models in lung nodule detection and classification: MTANNs vs.CNNs [J].Pattern Recognition,2017,63(3): 476-486   
[10] Mikolov T,Chen K,Corrado $\mathbf { G } ,$ et al.Efficient estimation of word representations in vector space [J].Computer Science,2013.   
[11] $\mathrm { { K i m } \ Y . }$ Convolutional neural networks for sentence classification [C]// Proc of Conference on Empirical Methods in Natural Language Processing. Stroudsburg,PA:Association for Computational Linguistics, 2014:1746-1751.   
[12]胡杰，李少波，于丽娅，等．基于卷积神经网络与随机森林算法的专 利文本分类模型[J].科学技术与工程，2018,18(6）.(HuJie，Li Shaobo，Yu Liya，et al.A patent classification model based on convolutional neural networks and rand forest [J]. Science Technology and Engineering,2018,18(6),268-272.）   
[13] Graves A,Schmidhuber J.Framewise phoneme classification with bidirectional LSTM and other neural network architectures[J]. Journal ofInternational Neural Network Society,2Oo5,18(5-6): 602.   
[14] Chung J,Gulcehre C,Cho K,et al.Gated Feedback recurrent neural networks [J].Computer Science,2015:2067-2075.   
[15]王树恒，吐尔根·依布拉音，卡哈尔江·阿比的热西提,等.基于 BLSTM的维吾尔语文本情感分析[J].计算机工程与设计，2017,38 (10):2879-2886．（WangShuheng，Turgun Lbrahim，Kahaerjiang Abiderexiti,et al.Sentiment classification of Uyghur text based on BLSTM [J]. Computer Engineering and Design，2017,38(10): 2879-2886.)   
[16]李雪莲，段鸿，许牧．基于门循环单元神经网络的中文分词法[J]. 厦门大学学报:自然科学版,2017，56(2):237-243.(Li Xuelian,Duan Hong,Xu Mu.A Gated Recurrent Unit Neural Network for Chinese Word Segmentation [J].Journal of Xiamen University,2O17，56(2): 237-243.)   
[17] Tang Xiaoyan,Cao Jing.Automatic genre classification via n-grams of part-of-speech tags [J].Procedia-Social and Behavioral Sciences,2015, 198(7): 474-478..