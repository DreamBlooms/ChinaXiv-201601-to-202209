# 混合CTC/attention架构的端到端带口音普通话识别

杨威，胡燕

(武汉理工大学 计算机科学与技术学院，武汉 430000)

摘要：针对普通话语音识别任务中的多口音的识别问题,提出了链接时序主义(connectionisttemporalclassification，CTC)和多头注意力(MultiHead attention)的混合端到端模型，同时采用多目标训练和联合解码的方法。实验分析发现随着混合架构中链接时序主义权重的降低和编码器层数的加深，混合模型在带口音的数据集上表现出了更好的学习能力，同时训练一个深度达到48层的编码器-解码器架构的网络，生成的模型表现了超过之前所有端到端模型，在数据堂开源的200h带口音数据集上达到了 $5 . 6 \%$ 字错率和 $2 6 . 2 \%$ 句错率。实验证明了本文提出的端到端模型超过一般端到端模型的识别率，在解决带口音的普通话识别上有一定的先进性。

关键词：口音；混合CTC/Attention的端到端模型；多头注意力；链接时序主义；语音识别 中图分类号：TP912.34 doi: 10.19734/j.issn.1001-3695.2020.02.0036

Hybrid CTC/attention architecture for end-to-end multi-accent mandarin speech recognition

Yang Wei, Hu Yan† (School ofComputer Science&Technology,Wuhan University of Technology,WuHan Hube 43ooo0,China)

Abstract:To improve the performance of multi-accent Mandarin speech recognition task,this paper present a method for hybrid end-to-end automatic speech recognition(ASR） by combining Connectionist Temporal Clasification (CTC）and MutiHead Atentionbyusingamultiobjective training and jointdecoding.Our analysis shows thathybrid modelwith lower CTC weight and deeper encoder layers performance beter learning capacity.And we trained a very deep models with up to 48 layers for encode-decoder Architecture,which outperform all previous end-to-end ASR approaches on Aidatatang 200h multi-accent dataset, achieve $5 . 6 \%$ Character Error Rate(CER) and $2 6 . 2 \%$ Sentence Error Rate(SER) .The experiment proves that therecognitionrateof theend-to-end model proposed inthispaper exceeds the generalend-to-end model,andithas certain advancedness in solving the Mandarin recognition with accents.

Keywords:accent;hybridCTC/attentionend-to-end model; multi-headatention；connectionisttemporal clasification; speech recognition

# 0 引言

随着人工智能技术的飞速发展，语音识别技术已经成为了智能设备的标配，成为人机交互的重要手段之一。在语音识别技术中，口音一直是语音识别技术的难点[1]。对于普通话而言，由于方言众多，大部分人的普通话极易受到当地方言的影响。有研究表明[2]，超过 $7 9 . 6 \%$ 的普通话使用者有□音，他们之中有 $44 \%$ 有严重的口音。

为了解决语音识别中的口音的问题，最早有学者提出使用词典自适应的方法[1,3]，简单来说就是根据方言的发音习惯扩展发音词典，但是这种方法会增加词典的混淆，因此并不会取得明显的提升。所以解决口音问题的关键集中在了声学模型上，最简单直接的方法就是为每一种口音都建立一个声学模型[4]。这种方式对于每一种需要建立声学模型的方言来说都需要大量的方言数据进行训练才能得到较高的识别率，最后使用语音决策树选出最好的模型。因此，最好的方式是建立一个统一的自适应声学模型能够准确的识别不同的口音

针对口音问题建立自适应的声学模型已经有很多学者进行了很多的工作。最早，在高斯-隐马尔可夫模型上(GaussianmixturedensityhiddenMarkovmodel，GMM-HMM)模型上有研究者提出极大似然线性回归(maximumlikelihoodlinearregression，MLLR)的方法[5]。后续也有研究者提出结合极大似然线性回归和最大后验概率估计(maximumaposterioriestimation，MAP)的方法在带上海口音的普通话语音识别中取得了一定的提升[]。随着深度神经网络在自动语音识别(automatic speechrecognition，ASR)中的发展，有学者提出增加一层特定的口音判别层，并用KL散度(Kullback-Leiblerdivergence，KLD)的方法训练该顶层口音模型，在深度神经网络(deep neural networks，DNN)上针对非英语母语说话人的语音识别上取得了显著的提升[]。后来又有学者结合上述模型和增加说话人特定特征(i-vector)[8]特征输入到特定的口音判别层的方式，在带口音普通话的识别上取得了很大的提升效果[9]。也有研究者提出一种融合特征下基于卷积神经网络的说话人语音分割模型，为解决普通话说话人和四川话说话人的语音识别场景的任务提供了一定的研究价值[10]。

在最近的研究中，在语音识别系统中采用长短时记忆循环神经网络(long-short term memory recurrent neural networks,LSTM-RNN)[II的表现可以媲美最新的基于隐马尔可夫模型的深度神经网络(deep neural network hidden Markov models,DNN-HMM)系统的识别效果。研究者在基于长短时记忆循环神经网络的语音识别模型上进行了很多研究，从各个方面显著的改善了普通话语音识别系统的整体性能。由于基于长短时记忆循环神经网络网络的优秀表现，在带口音的语音识别方向，有研究者使用一层深度神经网络作为口音依赖特征层过滤特定口音的特征，用双向长短时记忆循环神经网络(bidirectional long short-term memory recurrent Neural networks

BLSTM-RNN)训练自适应的声学模型，在多口音的普通话识别上也取得了一定的效果[12]。上述方法在训练过程中需要对不同方言信息进行单独的分类和训练，对于部分方言数据缺乏的情况很难取得较好的识别率。同时上述模型仍然是遵循传统的模块化建模的方案，需要进行多阶段的独立训练(声学模型，发音字典，语言模型)，还需要一些丰富的专业知识来进行超参数的配置[13,14]。

相反，端到端的模型可以直接进行语音特征到文本的转录，不包含任何一个中间件，直接建立语音到文本之间的映射，可以潜在的优化最终任务的所有部分，同时在不同的语言系下也可以利用相同的框架训练直接训练。端到端模型已经在很多语音识别任务中表现出来可以媲美最先进的传统模型的识别效果[13\~17]。端到端模型可以分为三种主要的基本模型架构，基于链接时序主义的模型(CTC)[13,14,17,18]借鉴了马尔可夫假设有效的解决序列的动态对齐问题，基于注意力机制的模型(attention)[19,20,23,24]通过一个注意力机制解决了声学帧和标签之间的对齐问题，基于混合架构的模型(CTC/attention)通过对上述两种模型进行联合训练和联合解码，在解码和是被上都取得了优于上述单独一种方式训练的效果[21,22]。研究者针对端到端模型鲁棒性差，固定长的语音帧造成的时频信息和部分高频信息的损失问题，提出了ResNet-BLSTM网络，有效的降低了模型的字错率[25]。

本文提出结合多头注意力(multi-headattention)的编码器-解码器模型[24,25]和链接时序主义(CTC)的混合端到端架构模型，采用联合训练和联合解码的方式[20.21]。在模型中，加深编码器-解码器网络的深度并训练了一个非常深的编码器-解码器网络，研究深层次网络对于语音识别的影响，同时在浅层的编码器-解码器网络中设置不同随机失活比率，研究带口音数据集的训练过程。

# 1 混合CTC/attention模型

本文提出的模型，如图1，本文提出了一个基于多头注意力和链接时序主义的深层编码器-解码器网络，在混合架构中，链接时序主义(CTC)和多头注意力(multi-headattention)联合训练和联合打分，同时通过加深编码器和解码器网络层的方式进一步提升了识别率。

![](images/4f17f15d15493dc7bf166bb393bfa3ee833c5f81b84540b4aadd014483b49d89.jpg)  
图1基于多头注意力和链接时序主义的深层编码器-解码器架构 Fig.1Deep encoder-decoder architecture based on multi-head attention and connectionist temporal classification

对于端到端的语音识别任务，目的是通过一个单一的网络，对于输入序列 $\boldsymbol { x } = \left( x _ { 1 } , \cdots , x _ { T } \right)$ ，计算所有输出标签序列$y = \left( y _ { 1 } , \cdots , y _ { U } \right)$ 的概率，通常 $U { \le } T$ ， $y _ { u } \in L$ ， $\textbf { \em L }$ 是有限字符集的集合，并输出最大概率的标签序列。即：

$$
y ^ { * } = \arg \operatorname* { m a x } _ { y } P ( y \mid x )
$$

# 1.1链接时序主义(CTC)

基于链接时序主义训练的网络如图2所示，在CTC训练中，定义中间标签序列 $\pi = ( \pi _ { 1 } , \cdots , \pi _ { T } )$ ，在序列 $\pi$ 中允许重复的标签存在，并插入一个空白标签 $< - >$ 作为分隔符，即$\pi _ { { \mathfrak { t } } } \in L \cup \{ < - > \}$ 。假设 $y ^ { \prime }$ 是 $y$ 增加了分隔符之后的扩展，例如$y = ( n , i , h , a , o )$ ， $y ^ { \prime } = ( - , n , - , i , - , h , - , a , - , o , - )$ ，定义一个多对一的映射 $B : L ^ { \prime } \ – > L ^ { \varsigma T }$ ，其中 $L ^ {  \leq T }$ 是可能的中间标签序列 $\pi$ 的输出集合，可以得到输出标签的 $P ( y | x )$ 概率:

$$
P ( y \mid x ) = \sum _ { \pi \in B ^ { - 1 } ( y ^ { \prime } ) } P ( \pi \mid x )
$$

![](images/68357e5fe266cbd2c64ae57fa26591008471e281b80ff5e521a8d64a4229051b.jpg)  
图2链接时序主义(CTC)  
Fig.2Connectionist temporal classification

对于 $\pi$ ,在输入序列 $x$ 的每个时间步 $t$ 都要计算对应的输出 $\pi _ { t }$ ，假设每个时间步之间的输出序列是有条件的独立的，可以得到式(3):

$$
P ( \pi | \mathrm x ) \approx \prod _ { t = 1 } ^ { T } P ( \pi _ { t } \mid \pi _ { 1 } , \pi _ { 2 } , \cdots , \pi _ { t - 1 } , x ) , \forall \pi \in \mathrm L ^ { \prime }
$$

由式 $( 1 ) { \sim } ( 3 )$ 可以定义CTC的损失函数负对数概率值：

$$
\begin{array} { r l } & { L _ { \epsilon t c } ( S ) = - \ln p ( \mathbf { y } \mid x ) } \\ & { \qquad = - \ln \underset { \pi \exp ^ { - 1 } ( y ^ { \prime } ) } { \sum } p ( \pi \mid x ) } \\ & { \qquad = - \underset { ( x , y ^ { \prime } ) \in S } { \sum } \ln \underset { \pi \in B ^ { - 1 } ( y ^ { \prime } ) } { \sum } p ( \pi \mid x ) } \\ & { \qquad = - \underset { ( x , y ^ { \prime } ) \in S } { \sum } \ln \underset { \pi \in B ^ { - 1 } ( y ^ { \prime } ) } { \sum } \overset { T } { \underset { t = 1 } { \prod } } q _ { t } ( \pi _ { t } ) , \forall \pi \in L ^ { \prime } } \end{array}
$$

在式(4)中，S代表输入序列 $\mathbf { x }$ 和输出标签之间的映射，$q _ { t } ( \pi _ { t } )$ 代表标签 $\pi _ { t }$ 在时间步 $t$ 的概率。在式(4)中，在计算过程中需要穷举出所有时间步的所有的标签序列，在计算上需要$N ^ { T }$ 次迭代，N代表标签的总数，计算量太复杂。CTC 算法[17]借鉴HMM的前后项算法，优化计算的速度：

$$
\left. P _ { c t c } ( y \vert x ) = \sum _ { t = 1 } ^ { T } \sum _ { u = 1 } ^ { \lfloor y \rceil } \frac { \alpha _ { t } ( u ) \beta _ { t } ( u ) } { q _ { t } ( \pi _ { t } ) } \right.
$$

在式(5)中， $\alpha _ { t } ( u )$ 代表第 $\mathrm { ~  ~ u ~ }$ 个标签在时间步 $t$ 的前向概率，$\beta _ { t } ( u )$ 代表第 $\mathrm { ~  ~ u ~ }$ 个标签在时间步 $t$ 的后向概率。

# 1.2基于多头注意力的编码器-解码器

本文使用的编码器-解码器模型[20,21]受到 google 的transformer 模型[26,27]的启发，采用基于多头注意力的多层编码器-解码器解码器模型，同时在每层输入前都添加一层随机失活层。编码器中的每一层都是由一个多头注意力层和一个全连接的前向网络组成；解码器中的每一层由一个屏蔽当前时刻之前的注意力信息的多头注意力层和计算编码器输入的注意力层，全连接的前向网络三层网络组成。在输入端。如图3，为单层的编码器一解码器网络结构。

编码器根据输入序列 $\boldsymbol { x } = ( x _ { 1 } , \cdots , x _ { T } )$ 计算一个输出的中间序列 $\boldsymbol { z } = ( z _ { 1 } , \cdots , z _ { T } )$ ，解码器将序列<作为输入，在每个时间步都会更新输出标签 $y = \left( y _ { 1 } , \cdots , y _ { U } \right)$ 中的一个标签。在更新输出标签过程中，模型也会根据前面的标签作为输入来更新下一个输出标签。如下：

$$
z _ { t } = E n c o d e r ( x )
$$

$$
y _ { t } = D e c o d e r ( z , y _ { t - 1 } )
$$

![](images/c79467076f89372c470d2c443bd350abe34ce8a98c04770510ee5f3b4449dd18.jpg)  
图3单层编码器-解码器网络结构  
Fig.3Sequence-to-sequence keyword extension model based on attention mechanism

根据最大似然估计，可以最大化输出序列基于输入序列的条件概率作为损失函数：

$$
{ \begin{array} { r l } { \mathrm { L } _ { \mathrm { a t t } } } & { = - \log p ( y _ { 1 } , y _ { 2 } , \cdots , y _ { T ^ { \prime } } \mid x _ { 1 } , x _ { 2 } , \cdots , x _ { T } ) } \\ & { = \displaystyle \sum _ { t ^ { \prime } = 1 } ^ { T ^ { \prime } } p ( y _ { t ^ { \prime } } \mid y _ { 1 } , y _ { 2 } , \cdots , y _ { t ^ { \prime } - 1 } , z ) } \end{array} }
$$

从式(6)(7)可以看出，解码器的输入依赖于相同的序列，$z$ 得到的是由序列 $x$ 计算出的最终时间步的隐藏向量，而在实际的语言序列中，每个时刻标签的输出通常更加依赖于相近时刻的特征，所以在编码器-解码器模型中引入注意力机制。注意力机制在每个时刻都会输出一个结果 $y _ { t }$ ，可以理解为将原来固定的中间序列 $z$ 转换成会根据当前输出的动态变化的序列 $z _ { t }$ 。

多头注意力机制首先对输入做线性转换初始化三个权重矩阵 $\varrho$ 、 $K .$ 、V:

$$
Q = K = V = \mathrm { L i n e a r ( X ) }
$$

然后根据点积的方式计算矩阵 $\varrho$ ， $K$ 的相似度：

$$
f \left( Q , K \right) = \frac { Q ^ { T } K } { \sqrt { d _ { k } } }
$$

对于解码器的输入，只能计算当前时刻和之前时刻输入特征的相似度，屏蔽未来信息，通常填充0将式(10)计算的矩阵变成下三角矩阵。然后用softmax函数做归一化输出，根据注意力分布计算加权平均：

$$
A t t e n t i o n ( Q , K , V ) = s o f t \operatorname* { m a x } ( f ( Q , K ) ) V
$$

为了避免过拟合问题，设置随机失活神经元，本文采用的是随机设置失活神经元的dropout函数，根据多头注意力的计算原则，将上面得到的结果重复计算 $\mathfrak { n }$ 次，最终的结果做拼接，转换成线性输出：

$$
A t t e n t i o n ( Q , K , V ) = s o f t \operatorname* { m a x } ( f ( Q , K ) ) V
$$

$$
M u l t i H e a d ( Q , K , V ) = C o n c a t ( h e a d _ { 1 } , . . . , h e a d _ { n } ) W ^ { Q }
$$

进行完多头注意机制的计算，在编码器和解码器的每一层都要经过一个全连接的前向网络处理，包含两个线性变化和一个激活函数输出：

$$
F F N ( x ) = ( d r o p o u t ( x W _ { 1 } + b _ { 1 } ) ) W _ { 2 } + b _ { 2 }
$$

得到序列得分和注意力分布图。

# 1.3多目标学习和联合解码

本文使用的混合模型受到[17,22]的启发，基于链接时序主义和基于多头注意力的模型联合训练，编码器由链接时序主义(CTC)和多头注意力模型(multi-headattention)共享，训练的过程中采用多目标学习(multiobjective learning，MTL)[22]的方式，相对于单一的数据驱动的注意力模型，利用了CTC的前-后向算法执行语音到标签之间的强制单音对齐，加速了对齐的过程。同时对比单一的CTC模型，由于注意力的目标是字符集的，CTC的目标是序列级的，可以帮助提升CTC目标的准确性。使用交叉损失准则将和相结合的联合打分，提高了鲁棒性，由式(4)和(8)可以得出:

$$
\mathrm { L } _ { \mathrm { M O L } } = \lambda \log p _ { c t c } ( c | x ) + ( 1 - \lambda ) \log p _ { a t t } ( c | x )
$$

其中参数 $\lambda \in [ 0 , 1 ]$ 是一个插值权重。除了利用多目标学习训练网络，在混合模型中还有一个重要的步骤就是联合解码。

混合架构中，通常是使用集束搜索算法(beam searchprocess)来执行解码过程，完整的集束搜索方法需要计算出每一种假设的得分。混合架构中需要联合链接时序主义的得分和注意力得分。在集束搜索中中，利用了动态规划的思想，对于每一个时间步，都由前面可能的路径扩展，得到当前时间步的局部概率g，这个局部概率由前面的路径决定，通过当前时间步可能的标签的概率c，可以得到当前时间步的所有可能的假设h，即当前标签c可不可能出现在当前时间步，得到假设后就可以通过式(15)计算联合得分，到下一个时间步继续扩展节点得到每个路径的打分，当预测到结尾字符时，将满足最小阈值要求的序列加入到最终序列中。比较所有可能序列的得分，取最高分为目标序列。本文在搜索解码过程中，采用多路搜索，每次选择概率最大的 $\mathbf { k }$ 个节点进行扩展，使每一步最多扩展 $\mathbf { k }$ 个节点，而不是随着时间步的增长呈现指数增加，可以很大程度的降低穷举搜索的复杂度。

$$
\mathrm { S c o r e } = \underset { h \in L ^ { \prime } } { \arg \operatorname* { m a x } } \left\{ \lambda \alpha _ { c t c } ( h , x ) + ( 1 - \lambda ) \alpha _ { a t t } ( h , x ) \right\}
$$

# 2 实验

# 2.1实验模型

本文采用的端到端模型为基于链接时序主义和基于多头注意力混合模型。对比采用的传统模块化模型为高斯-隐马尔可夫模型，时延神经网络模型(time-delayneuralnetwork,TDNN)和链式模型(chain)。对比采用的端到端模型为基于链接时序主义和基于位置信息的混合模型，基于多头注意力的模型。

# 2.2数据

在本文的实验中，本文采用数据堂开源的200h带口音普通话数据集，数据集中包含30万条口语化的句子，共6408人，其中男性2999人，女性3301人，录音人员分布于广东、福建、山东等34个省级行政区域。传统的模块化模型在Kaldi[28]平台下完成,端到端实验都在开源的 ESPnet(end-toend speechprocessingtoolkit)[29]端到端语音开发平台下完成，传统的模块化模型在Kaldi[28]平台下完成。在所有的实验中，对于音频数据，都采用 $1 . 6 \mathrm { K H z }$ 的抽样频率，80维的FBANK特征向量，每帧 $2 5 ~ \mathrm { m s }$ ，帧移 $1 0 ~ \mathrm { m s }$ 。

# 2.3 网络结构及参数

本文使用的网络，使用4层的多头注意力，每层输入注意力的维度为256，前向全连接层的输入特征维度为256，隐藏特征维度为2048，双向长短时记忆单元数为2048。联合训练参数入为0.3，随机丢失激活细胞率为0.1，标签平滑为0.1。集束搜索宽度为10，语言模型占比重0.1，epoch次数为50。

# 2.4评价指标

本文在数据堂的开发集和测试集上评价实验结果，采用字错率(Character ErrorRate，CER)和句错率(Sentence ErrorRate，SER)作为评价指标，字错率即为了使识别出来的词序列和标准的词序列之间保持一致，需要进行替换、删除或者插入某些词，这些插入(I)、替换(S)或删除(D)的词的总个数，除以标准的词序列中词的总个数的百分比。句错率中，如果一个词识别错误，那么这个句子被认为识别错误。即：

$$
\mathrm { C E R } ( \vec { \mp } \dot { \nu } \vec { \mathcal { K } } \vec { \mathcal { F } } ) = \frac { S + D + I } { N }
$$

# 2.5对比实验

本文实现了GMM-HMM模型，时延神经网络模型(TDNN)和kaldi的链式模型三个传统模型作为对比实验，这三个传统模型也是数据堂开源的在带口音普通话语音数据集中表现最好的三种模型，采用 kaldi[28]工具包中aidatatang 的方案(https://www.datatang.com)。

高斯一隐马尔可夫模型(GMM-HMM)：经过特征提取之后的语音特征序列，在忽略时序的条件下，研究者发现高斯混合分布非常适合拟合这样的特征序列，因此GMM被整合到HMM中，拟合基于状态的输出分布，提出了GMM-HMM模型。

时延神经网络模型(TDNN)：时延神经网络中可以对长序列的具有依赖时序的序列建模，采用二次采样的方法减少计算量，在训练上比同样对时序建模的循环神经网络要快，同时网络利用i-Vector特征，对自适应说话人和环境都有区分性，在带口音的训练中也有良好的表现。

链式模型(ChainModle)：链式模型是DNN-HMM模型的一种，模型借鉴了CTC的思想，引入了空字符来吸收不确定的边界，使用正确序列的对数作为目标函数，在训练过程中要计算分母和分子的概率，并使用两者之间差异的倒数回传到网络中，链式模型同时可以有效地提高解码的速度。

基于多头注意力的模型[20.21]:多头注意力是基于自注意力机制的，自注意力模型是发生在序列内部，即在编码器内部学习语音特征的序列，在解码器内部学习到标签的特征，相较一般的注意力机制在序列问题上有更好的性能。

LSTM-RNN-CTC模型[30]:结合了LSTM良好的序列建模能力，通过对不同地域的普通话口音做区分性训练，极大的提升了模型识别口音的能力。

# 3 实验结果及分析

# 3.1传统模型与端到端模型对比

表1展示了传统的模块化自动语音识别系统和常见的端到端模型在多口音普通话语音识别上的效果，其中MTL(MultitaskLearning)参数代表联合训练中基于注意力机制的得分所占的比重，表1中混合端到端架构中的多头注意力机制模型采用12层的编码器-06层的解码器架构。相较基于多头注意力机制的模型，混合模型有 $1 0 . 0 \% - 1 0 . 9 \%$ 的字错率和 $6 . 3 \% - 7 . 1 \%$ 的句错率的提升。在单独基于多头注意力的数据集中，大部分的识别错误集中在重口音普通话的说话人语句中。说明单独基于注意力机制的模型在拟合多个地区口音的识别上还存在严重的缺陷，尤其对于同一个字符的发音变异问题。相较传统的模块化识别模型，混合端到端模型展现出来了良好的性能，通常在识别率上领先基于时延神经网络模型(TDNN)和传统的HMM-GMM模型，略低于最先进的链式模型。但端到端的模型由于其良好的整体性可以很方便的达到对模型整体进行调优的目的。

表1带口音普通话语音在各不同模型中的识别率对比

Tab.1 Comparison of the recognition rate ofMandarin speech with   

<html><body><table><tr><td colspan="3">accents in different models</td></tr><tr><td rowspan="2">models</td><td colspan="2">test</td></tr><tr><td>CER(%)</td><td>SER(%)</td></tr><tr><td>GMM-HMM</td><td>12.2</td><td>43.1</td></tr><tr><td>TDNN</td><td>7.1</td><td>31.2</td></tr><tr><td>CHAIN</td><td>5.6</td><td>26.1</td></tr><tr><td>Multi-Head</td><td>17.3</td><td>36.0</td></tr><tr><td>LSTM-RNN-CTC</td><td>15.1</td><td>32.7</td></tr><tr><td>CTC/Attention (Location+MOL(0.5))</td><td>10.5</td><td>39.0</td></tr><tr><td>CTC/Attention</td><td></td><td></td></tr><tr><td>(Content+MOL(0.5))</td><td>10.9</td><td>39.7</td></tr><tr><td>CTC/Attention (Multi-Head+MOL(0.1))</td><td>7.3</td><td>29.7</td></tr><tr><td>CTC/Attention</td><td>6.4</td><td>28.9</td></tr><tr><td>(Multi-Head+MOL(0.3))</td><td></td><td></td></tr><tr><td>CTC/Attention (Multi-Head+MOL(0.5))</td><td>6.5</td><td>29.7</td></tr></table></body></html>

如表1，值得注意的是，随着多任务学习权重(MTL)的提升(0.0，0.1，0.3),识别率也有进一步的提升。如图4所示，在CTC损失权重在多任务训练中所占比重过大，模型的训练效果并不好，出现了严重的过拟合现象。这可能是由于CTC本身基于带条件的独立假设，在多口音的数据集中无法有效利用口音相似的特性，导致模型的收敛效果并不好。但在混合模型上，基于链接时序主义的方式仍然可以有效的帮助提升识别率，同时可以提升模型的收敛速度。在多任务学习的框架下，合理的配置设置训练权重，基于链接时序主义的方法可以强制性的进行特征和标签之间的单调对齐，对于基于多头注意力的模型的训练带来了很大的提升，同时也加快了基于多头注意力模型的收敛速度。

# 3.2混合模型深度与随机失活率研究

为了进一步提升多口音普通话的识别率，加深编码器和解码器的网络层，并在浅层网络中逐步提升随机失活率分别为0.0、0.1、0.5。

如表2所示，实验结果表明了本文提出的基于深层多头注意力机制和链接时序主义的模型，相较于传统的GMM-HMM模型，TDNN模型，在识别率上都有较大的提升。相较常用的基于LSTM-RNN-CTC方法和基于多头注意力机制的模型，不仅在识别率有较大提升，在训练速度上也有一定的提升。同时随着层次的加深，字错率可以达到 $5 . 6 \%$ ，不需要字典就可以媲美目前表现最好的链式模型的识别率，同时模型简单、易优化。

![](images/55f71a2744dda32765893dfed1b3dfeb43b95973ec57f9cf3bf2dc370491678d.jpg)  
表2深度与随机失活率研究

Tab.2Research on Depth and Random Inactivation Rate   

<html><body><table><tr><td rowspan="2">models</td><td colspan="2">test</td></tr><tr><td>CER</td><td>SER</td></tr><tr><td>Dropout Rate 0.0</td><td></td><td></td></tr><tr><td>12Enc-06Dec</td><td>6.4</td><td>28.9</td></tr><tr><td>24Enc-24Dec</td><td>5.9</td><td>27.2</td></tr><tr><td>48Enc-48Dec</td><td>5.6</td><td>26.2</td></tr><tr><td>Dropout Rate 0.1</td><td></td><td></td></tr><tr><td>12Enc-06Dec</td><td>6.3</td><td>28.5</td></tr><tr><td>Dropout Rate 0.5</td><td></td><td></td></tr><tr><td>12Enc-06Dec</td><td>7.3</td><td>31.8</td></tr></table></body></html>

如图5所示，随着编码器层数的加深，编码器学习到音频特征的信息越具有代表性。

![](images/68b700b37cd60dc5e3f083a87a6da773378f96d66bd6aba1a09a6f6e9596b852.jpg)  
图4端到端模型训练损失图  
图5编码器自注意力  
Fig.5Self-attention of Encoder

如图6所示，随着解码器层数的加深，加深了标签之间的相关度，在判定句结尾的静音片段上有显著的提升。相比浅层的网络，更少出现了识别少字的情况。

![](images/0635506ae583829fe5771b76bb29551cdb69fa4ddcd21d0603257b4cc0daeb85.jpg)  
Fig.4End-to-end model training loss graph   
  
Fig.6Self-attention of Decoder

# 4 结束语

在本文中，提出使用链接时序主义(CTC)和多头注意力的编码器-解码器混合架构模型用于带口音的普通话语音识别。相较于传统的模块化模型需要大量的人工准备的资源，不用针对每一种方言准备语料和做模型自适应等复杂过程，只需要训练一个单一模型，不仅可以超过一般的传统方法的识别率，还可以方便的对模型的整体性能进行调优，可以达到最先进的模型的识别率。在提出的深度编码器-解码器层模型下，研究发现编码器的深度的增加可以更好的学到音频特征的信息，可以显著的提高带口音普通话的识别率，而解码器的深度提升对于整个语音系统的提升较小，同时通过在浅层的网络中增加失活率，对于识别率也有微小的改进，后续的研究会通过改进失活方式，在深层的网络中进一步提升识别率。同时针对非常深层的网络训练速度较慢的问题，进行改进和提升。

# 参考文献：

[1]Huang C,Chen T,ChangE.Accent issues in large vocabulary continuous speech recognition [J]. International Journal of Speech Technology,2004, 7 (2-3): 141-153.   
[2] ZHANG D.xin (National Leading Group Office of the Teaching of chinese to Foreigners,Beijing l0o083）[J].My Point of View on the Standard of Newborn Words,2000,5.   
[3]Ding G H. Phonetic confusion analysis and robust phone set generation for Shanghai-accented Mandarin speech recognition [C]// Ninth Annual Conference of the International Speech Communication Association. 2008.   
[4]Elfeky M, Bastani M,Velez X,et al. Towards acoustic modelunification across dialects [C]// 2016 IEEE Spoken Language Technology Workshop (SLT) .IEEE,2016:624-628.   
[5]Wang Z, Schultz T, Waibel A. Comparison of acoustic model adaptation techniques on non-native speech [C]// 20o3 IEEE International Conference on Acoustics，Speech,and Signal Processing，2003. Proceedings. (ICASSP'03).IEEE,2003,1: I-I.   
[6] Zheng Y,Sproat R, Gu L,et al. Accent detection and speech recognition for shanghai-accented mandarin [C]/ Ninth European Conference on Speech Communication and Technology.2005.   
[7]Huang Y, Yu D,Liu C,et al. Multi-accent deep neural network acoustic model with accent-specific top layer using the KLD-regularized model adaptation [C]//Fifteenth Annual Conference of the International Speech Communication Association. 2014.   
[8]DeMarco A,Cox S J.Native accent classification via i-vectors and speaker compensation fusion [C]//Interspeech.2013:1472-1476.   
[9]Chen M, Yang Z,Liang J,et al. Improving deep neural networks based multi-accent mandarin speech recognition using i-vectors and accentspecific top layer $[ \mathrm { C } ] / \AA$ Sixteenth Annual Conference of the International Speech Communication Association.2015.   
[10]张盼．基于卷积神经网络的不同口音对话自适应识别研究[D].重 庆大学,2018.   
[11] Sak H,Senior A,Beaufays F.Long short-term memory based recurrent neural network architectures for large vocabulary speech recognition [J]. arXiv preprint arXiv:1402.1128,2014.   
[12] Yi J,Ni H,Wen Z,et al.Improving blstm rnn based mandarin speech recognition using accent dependent bottleneck features [C]// 2016 AsiaPacific Signal and Information Processing Association Annual Summit and Conference (APSIPA) .IEEE,2016:1-5.   
[13] Graves A,Jaitly N. Towards end-to-end speech recognition with recurrent neural networks [C]// International conference on machine learning. 2014: 1764-1772.   
[14] Miao Y, Gowayed M, Metze F.EESEN: End-to-end speech recognition using deep RNN models and WFST-based decoding [C]// 2015 IEEE Workshop on Automatic Speech Recognition and Understanding (ASRU).IEEE,2015:167-174.   
[15] Chorowski J, Bahdanau D,Cho K,et al. End-to-end continuous speech recognition using attention-based recurrent nn:First results [J].arXiv preprint arXiv: 1412.1602,2014.   
[16] Bahdanau D,Chorowski J, Serdyuk D,et al. End-to-end attention-based large vocabulary speech recognition [C]// 2016 IEEE international conference on acoustics,speech and signal processing (ICASSP) . IEEE, 2016: 4945-4949.   
[17] Lu L,Zhang X,Renais S. On training the recurrent neural network encoder-decoder for large vocabulary end-to-end speech recognition [C]// 2016 IEEE International Conference on Acoustics,Speech and Signal Processing (ICASSP) .IEEE,2016:5060-5064.   
[18] Graves A,Fernandez S,Gomez F,et al. Connectionist temporal clasification: labelling unsegmented sequence data with recurrent neural networks [Cl// Proceedings of the 23rd international conference on Machine learning. ACM,2006: 369-376.   
[19] Cho K,Van Merriénboer B,Gulcehre C，et al.Learning phrase representations using RNN encoder-decoder for statistical machine translation [J].arXiv preprint arXiv: 1406.1078,2014.   
[20] Sutskever I, Vinyals O,Le Q V. Sequence to sequence learning with neural networks [Cl//Advances in neural information processing systems. 2014: 3104-3112.   
[21] Kim S,Hori T, Watanabe S.Joint CTC-atention based end-to-end speech recognition using multi-task learning [C]// 2017 IEEE international conference on acoustics,speech and signal processing (ICASSP).IEEE, 2017: 4835-4839.   
[22] Watanabe S,Hori T,Kim S,etal.Hybrid CTC/attention architecture for end-to-end speech recognition [J]. IEEE Journal of Selected Topics in Signal Processing,2017,11 (8): 1240-1253.   
[23] Chorowski JK, Bahdanau D, Serdyuk D,et al. Attention-based models for speech recognition [C]// Advances in neural information processing systems. 2015: 577-585.   
[24] Chorowski J,Jaitly N.Towardsbeterdecodingand languagemodel integration in sequence to sequence models [J].arXiv preprint arXiv: 1612. 02695, 2016.   
[25]胡章芳，徐轩，付亚芹等．基于 ResNet-BLSTM的端到端语音识别 [J/OL].计算机工程与应用：1-8[2020-03-26].(Hu Zhangfang, Xyu Xuan,Fu Yanqin,et al. End-to-end speech recognition based on ResNetBLSTM[J/OL]. Computer Engineering and Applications: 1-8 [2020-03- 26]) http://kns.cnki. net/kcms/detail/11.2127.TP.20191014.170 6.010. html.   
[26] Vaswani A,Shazeer N,Parmar N,et al.Atntion is all you need [C]/ Advances in neural information processing systems. 2017: 5998-6008.   
[27] Pham N Q,Nguyen T S,Niehues J,et al. Very Deep Self-Attention Networks for End-to-End Speech Recognition [J].arXiv preprint arXiv: 1904. 13377, 2019.   
[28] Watanabe S,Hori T,Karita S,et al. Espnet:End-to-end speech processing toolkit [J]. arXiv preprint arXiv: 1804. 00015,2018.   
[29] Povey D,Ghoshal A,Boulianne G,et al. The Kaldi speech recognition toolkit [C]// IEEE 2011 workshop on automatic speech recognition and understanding. IEEE Signal Processing Society,2011(CONF).   
[30] Yi J,Wen Z,Tao J,et al. CTC Regularized Model Adaptation for Improving LSTM RNN Based Multi-Accent Mandarin Speech Recognition[J].Journal ofSignal Processing Systems,2018,90 (7): 985- 997.