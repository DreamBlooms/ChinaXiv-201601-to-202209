# 词向量与LDA相融合的短文本分类方法

张群 王红军 王伦文（中国人民解放军电子工程学院合肥 230037)

摘要：【目的】针对短文本主题聚焦性差以及严重的特征稀疏问题，设计一种基于词向量与LDA主题模型相融合的短文本分类方法。【方法】从“词"粒度及"文本"粒度层面同时对短文本进行精细语义建模，首先基于Word2Vec训练词向量并通过相加平均法合成"词"粒度层面的短文本向量，基于吉布斯采样法训练LDA主题模型并根据主题概率最大原则对短文本进行特征扩展，然后基于词向量相似度计算扩展特征权重得到"文本"粒度层面的短文本向量，最后通过向量拼接构建词向量与LDA 相融合的短文本表示模型，在此基础上通过最近邻分类算法完成短文本分类。【结果】相比传统的基于向量空间模型、基于词向量、基于LDA主题模型这三种基于单一模型的分类方法，词向量与LDA 相融合的分类方法准确率、召回率、 $\mathrm { F } _ { 1 }$ 值均有提升，分别至少提升 $3 . 7 \%$ $4 . 1 \%$ 和 $3 . 9 \%$ 。【局限】仅应用于最近邻分类器，尚未推广应用到朴素贝叶斯和支持向量机等多种不同的分类器。

【结论】基于词向量与LDA相融合的短文本表示模型进行分类，能有效克服短文本的主题聚焦性差及特征稀疏性问题，提高短文本分类性能。

关键词:短文本分类词向量LDA主题模型最近邻分类器分类号：G350

# 1引言

移动终端的智能化催生了移动互联网的飞速发展。为适应移动用户阅读习惯，移动互联网内容更多以短文本形式呈现，例如微博和即时推送新闻等，如何对海量短文本内容进行自动分类已成为研究者关注的热点问题。

在过去几十年里，国内外学者提出及改进了一系列经典的机器学习算法，如k 近邻分类(k-NearestNeighbors，k-NN)[1]、朴素贝叶斯分类(Naive Bayes,NB)[2]和支持向量机(Support Vector Machine,SVM)[3]等，并将其成功应用于文本分类领域，取得了比较满意的效果。然而相比普通长文本，新兴的移动互联网短文本具有内容长度短小、信息描述能力弱、主题分散等特点，使得以上经典文本分类方法应用于该领域时将面临严重的特征稀疏问题[4]，导致短文本分类效果并不理想。

文本数据表示对于文本分类至关重要，数据表示的好坏直接影响分类效果。传统文本分类算法通常基于向量空间模型(Vector Space Model，VSM)，通过特征词及权值构成的向量表示文本数据[5]。该方法忽略了词语间的语义关系，无法体现文本深层次的主题信息，存在数据高维稀疏问题，尤其是在表示短文本时，语义缺失及高维稀疏问题变得更为严重。近年来针对这一问题的研究主要有三个方向。一些学者引入外部知识库(如搜索引擎、维基百科和知网等)对文本进行语义特征扩展以丰富词语间语义关系[6-7]。这些方法能一定程度上缓解稀疏性，其局限性在于严重依赖外部知识库的质量，对于知识库中未收录的主题概念无能为力，且计算量大，耗时长，因此应用于主题分散的短文本效果一般。另有部分学者通过将原始高维特征词空间映射到低维的潜在语义空间或主题空间，挖掘文本潜在的语义结构。如潜在语义分析方法(LatentSemanticAnalysis，LSA)将文本表示为低维潜在语义空间的语义向量[8]，降维去噪的同时改善稀疏性，但是降维过程可能带来分类受损问题且该语义空间每个维度的语义含义并不明确。相比LSA方法，LDA主题模型 (LatentDirichletAllocation,LDA)将文本表示为其隐含主题的概率分布9，能极大改善文本高维稀疏性，克服LSA方法分类受损问题的同时每个主题维度也具有可解释性，因此受到广泛应用。文献[10-11]直接在LDA主题维上进行文本分类，但由于短文本主题聚焦性差，该方法对于改善短文本的稀疏性效果有限;文献[12-14]基于LDA 主题模型对短文本进行特征扩展，相比于单纯直接应用LDA的方法有一定的效果提升。以上的VSM、LSA和LDA模型均为直接导出短文本向量以表示短文本，属于“文本"粒度层面的模型。最新研究考虑从“词"粒度层面进行文本建模从而更精细地表达语义，首先导出词的向量表示，然后将词向量(Word Embedding)合成短文本向量[15]。这种方法有效解决了短文本主题分散和聚焦性差的问题，其局限性在于简单有效的词向量合成方法还有待研究，如文献[16-17]通过神经网络构建词向量的短文本合成模型，具有较高的复杂度。

在以上分析的基础上，本文将词向量与LDA有机融合，提出一种新的短文本分类方法，从“词"粒度及“文本"粒度层面同时进行短文本建模，以解决短文本特征稀疏问题及主题聚焦性差的问题。通过简单直接的相加平均法合成“词"粒度层面的短文本向量，避免了复杂的词向量合成过程；同时在进行“文本"粒度层面建模时，并非直接应用LDA模型将短文本映射到主题维，而是基于LDA主题概率最大原则对短文本进行特征扩展，并基于词向量相似度计算扩展特征权重，从而构建词向量与LDA相融合的短文本表示模型；另外在训练词向量及LDA 模型时并不依赖已标注数据,仅在训练分类器时需要小规模的已标注数据，属于一种半监督学习方法[18]

# 2词向量训练及LDA建模

# 2.1 基于Word2Vec的词向量训练

词向量是词语的一种数学表示方法，向量的每个维度代表一个语义特征，向量间的距离或相似度能够反映词语间的语义相似性。分布假说理论(DistributionalHypothesis)表明词语语义由其上下文决定。依据分布假说理论，一种基于神经网络的词向量获取方法受到广泛研究，该方法通过对目标词的上下文及目标词与其上下文的关系进行建模，能够获取包含丰富语义的低维稠密的词向量。Bengio 等提出神经网络语 言 模型(Neural Network Language Model,NNLM)，词向量作为一种副产品，是在训练该语言模型的同时得到的[19]。NNLM为一个三层前馈神经网络结构，如图1所示[19]

第i个输出 ${ \bf \Psi } = P { \bf \Psi }$ (w| context) softmax ↑   
输出层y OO0..00..000 tanh   
隐藏层h OOO 00 C(wi-r C(w ic(wi)   
输人层xO..OO 0..00 0.00 矩阵C Wi-n+1 Wi-2 Wi-l

NNLM结构图中, $\mathbf { w } _ { \mathrm { i } }$ 为目标词，目标词的上下文为一个词序列，即 context={Wi-n+1,,Wi-2,Wi-1}。NNLM的输入层通过一个矩阵 $\mathbf { C }$ 将上下文序列中的词映射为词向量，然后将词向量顺序拼接作为整个模型的输入，如下所示[19]

$$
\mathbf { x } = \{ \mathbf { C } ( \mathbf { w } _ { \mathrm { i - n + l } } ) , \cdots , \mathbf { C } ( \mathbf { w } _ { \mathrm { i - 2 } } ) , \mathbf { C } ( \mathbf { w } _ { \mathrm { i - 1 } } ) \}
$$

隐藏层与输出层分别如下[19]

$$
\mathbf { h } = \operatorname { t a n h } ( \mathbf { b } + \operatorname { H } \mathbf { x } )
$$

$$
\mathbf { y } = \mathbf { d } + \mathrm { W } \mathbf { x } + \mathrm { U } \mathbf { h }
$$

其中,tanh为隐藏层激活函数,H为输入层到隐藏层的权重矩阵，U为隐藏层到输出层的权重矩阵，W为输入层到输出层的直连边权重矩阵(通常忽略)，b、d为模型偏置项。模型最终需通过Softmax函数将输出层y归一化为目标词的概率分布，如下所示[19]。

$$
\mathrm { P } ( \mathbf { w _ { i } } \mid \mathbf { w _ { i - n + 1 } } , \cdots , \mathbf { w _ { i - 2 } } , \mathbf { w _ { i - 1 } } ) = { \frac { \exp ( \mathbf { y } ( \mathbf { w _ { i } } ) ) } { \displaystyle \sum _ { k = 1 } ^ { | \mathbf { V } | } \exp ( \mathbf { y } ( \mathbf { w _ { k } } ) ) } }
$$

最后，模型通过迭代优化，在使公式(4)最大化的过程中训练出模型参数，其中包括词向量参数矩阵C，从而获得词向量。

NNLM的计算量集中在公式(3)中的隐藏层到输出层的矩阵乘法Uh中；另外，公式(4)中, $| \mathbf { V } |$ 为词汇表大小，因此当词汇表很大时Softmax函数计算非常耗时。

在NNLM的基础上，本文基于Word2Vec进行词向量训练。Word2Vec是基于Mikolov等提出的CBOW(ContinuousBag-of-Words)和Skip-gram 模型开放的一款词向量训练工具[20]。CBOW 及 Skip-gram 这两种模型类似于NNLM，区别在于NNLM是以训练语言模型为目标而间接获得了词向量，而CBOW 和 Skip-gram模型的直接目的即为获取词向量。因此Word2Vec 在NNLM的基础上做了以下简化与改进：

(1）去掉隐藏层，避免了公式(3)中复杂的矩阵乘法运算Uh。(2)NNLM在输入层采用如公式(1)所示的词向量拼接法，而Word2Vec 的CBOW模型采用向量相加求平均法降低了运算复杂度，如下所示[20]。

$$
\mathbf { x } = \sum _ { \mathbf { w _ { j } } \in \mathbf { c } } { \frac { \mathbf { C ( w _ { j } ) } } { \mathbf { n } - 1 } }
$$

其中， $\mathsf { c } = \left\{ \mathbf { w } _ { \mathrm { i - ( n - 1 ) } / 2 } , \cdots , \mathbf { w } _ { \mathrm { i - 1 } } , \mathbf { w } _ { \mathrm { i + 1 } } , \cdots \mathbf { w } _ { \mathrm { i + ( n - 1 ) } / 2 } \right\}$ ，指 CBOW中目标词 $\mathbf { w } _ { \mathrm { i } }$ 前后各 $( { \mathfrak { n } } - 1 ) / 2$ 个词，即 $\mathbf { w } _ { \mathrm { i } }$ 的上下文。相比NNLM仅采用前 $( { \mathfrak { n } } - 1 )$ 个词作 $\mathbf { w } _ { \mathrm { i } }$ 的上下文,Word2Vec更具有上下文完备性。

CBOW与Skip-gram不同之处在于，CBOW是通过上下文预测目标词而 Skip-gram 是通过目标词预测上下文。CBOW与Skip-gram 结构图分别如图2、图3所示[20]

![](images/2d4e4cc7a40517af7b4431d258028838356a72be68a095b40fdb89ca2a657deb.jpg)  
图2 CBOW模型结构

![](images/cdf66b9defeb2324219d95af85924b2cc85b2d774a22bbe703f2007f38385187.jpg)  
图3Skip-gram 模型结构

另外，针对NNLM输出层Softmax函数计算复杂度大的问题，Word2Vec采用两种算法进行优化：结合霍夫曼编码的层次 Softmax 算法[21l及负采样(NegativeSampling)技术[15]。

本文基于Word2Vec训练词向量用于短文本分类任务，发现语料数据集规模及模型的选择会影响词向量质量进而影响短文本分类效果。针对这两个方面，总结以下经验用于指导训练词向量:

（1）语料集规模在200MB以上时,CBOW模型优于Skip-gram模型，在100MB以下则相反，在100MB-200MB之间两模型表现差别不明显。(2)CBOW模型在输入层采用词向量相加平均法代替 NNLM中的词向量拼接法，降低了计算复杂度，但忽略了词序信息；本文尝试在CBOW 模型的基础上仍采用词向量拼接法引入词序信息，但结果表明修改后的模型与原CBOW模型相比性能表现无明显差别。

# 2.2基于吉布斯采样的LDA建模

LDA主题模型是一个“文档-主题-词"的三层贝叶斯概率生成模型，其通过模拟文本的生成过程，将文本建模为混合主题上的概率分布，将主题建模为混合词上的概率分布，模型如图4所示[9]。

![](images/d19deb2ef94dbfe378083e70570117cf39843053063da490ca0a183c7882273f.jpg)  
图4LDA图模型

图4中符号含义如下：M表示总文本数，N表示一篇文本中的总词数,K表示文本集隐含主题数；0为文本-主题分布矩阵， ${ \Phi }$ 为主题-词分布矩阵，0与 $\Phi$ 均服从狄利克雷分布(Dirichlet Distribution)， $\alpha$ 为0的超参数， $\beta$ 为 $\Phi$ 的超参数； $\mathbf { w }$ 表示词， $z$ 为 $\mathbf { w }$ 所属的主题。

令 $\mathbf { d } _ { \mathrm { m } } = ( \mathbf { w } _ { \mathrm { m l } } , \mathbf { w } _ { \mathrm { m } 2 } , \cdots \mathbf { w } _ { \mathrm { m N } } )$ 表示第 $\mathrm { ~ m ~ }$ 篇文本,Zm=(Zml,Zm2,,Zmn）中分量表示 dm中每个词对应所属的主题， $\mathbf { D } = ( \mathbf { d } _ { 1 } , \mathbf { d } _ { 2 } , \cdots , \mathbf { d } _ { \mathrm { M } } )$ 表示整个文本集,（204号 $\mathbf { Z } = ( \mathbf { z } _ { 1 } , \mathbf { z } _ { 2 } , \cdots , \mathbf { z } _ { \mathrm { M } } )$ 中分量表示 $\mathbf { D }$ 中每个文本对应的主题向量。基于图4,LDA模型生成过程描述如下：

(1）对于第 $\mathrm { ~ m ~ }$ 篇文本 ${ \bf d } _ { \mathrm { m } }$ ，根据0服从参数为 $\alpha$ 的Dirichlet分布( ${ \bf \nabla } ( \mathbf { \theta } _ { \mathrm { { m } } } \sim \mathrm { D i r } ( \alpha )$ )，确定一个主题分布 ${ \bf \theta } _ { \mathrm { { m } } }$ ：(2）对于第 $\mathfrak { n }$ 个词 $\mathbf { w _ { m n } }$ ，根据 $z$ 服从0的多项分布

0 $\dot { \bf \zeta } _ { \mathrm { m n } } \sim \bf { M u l t } ( \bf { \bf \theta } _ { \mathrm { m } } ) \dot { \bf \zeta } _ { \mathrm { m } }$ ，为 $\mathbf { w _ { \mathrm { m n } } }$ 确定一个主题编号 $z _ { \mathrm { m n } }$ ：

(3)根据 ${ \Phi }$ 服从参数为 $\beta$ 的Dirichlet 分布（204号 $( \Phi _ { \mathrm { m } } \sim \operatorname { D i r } ( \beta )$ )，确定一个主题-词分布矩阵 $\Phi _ { \mathrm { m } }$ ，同时根据步骤(2)确定的 $z _ { \mathrm { m n } } ,$ 为 $\mathbf { w _ { \mathrm { m n } } }$ 确定一个词分布 $\Phi _ { \mathrm { z _ { \mathrm { m n } } } }$ ·，

(4)根据词 $\mathbf { w } _ { \mathrm { m n } }$ 服从 $\left. \Phi _ { \mathrm { z _ { \mathrm { m n } } } } \right.$ 的多项分布$\left( \mathbf { W } _ { \mathrm { m n } } \sim \mathbf { M u l t } ( \mathbf { \Phi } _ { z _ { \mathrm { m n } } } ) \right) ,$ ，生成词 $\mathbf { w _ { m n } }$ ·，

(5)遍历文本中 $\mathrm { ~ N ~ }$ 个词，重复步骤(2)-步骤(4)，生成 ${ \bf d } _ { \mathrm { m } }$

(6)遍历文本集中M篇文本，重复步骤(1)-步骤(5),生成整个文本集D。

LDA模型的目标是为文本集 $\mathbf { D }$ 中的每个词分配一个潜在主题，从而估计出模型中的文本-主题分布矩阵0与主题-词分布矩阵 ${ \Phi }$ ，由此需要计算如公式(6)所示的后验概率[9]

$$
\mathtt { p } ( \mathbf { Z } | \mathbf { D } ) = \frac { \mathtt { p } ( \mathbf { Z } , \mathbf { D } ) } { \sum _ { \mathbf { z } } \mathtt { p } ( \mathbf { Z } , \mathbf { D } ) }
$$

其中分母计算难度非常大，为避免直接计算公式(6)，一种简单有效的方法是采用吉布斯采样(GibbsSampling)算法。

吉布斯采样算法[22]是一种特殊的基于马氏链的蒙特卡洛方法(Markov Chain Monte Carlo，MCMC),通过对词的主题采样生成马氏链，用 $\mathfrak { p } ( \mathbf { \boldsymbol { z } } _ { \mathrm { i } } \mid \mathbf { \boldsymbol { z } } _ { \mathrm { - i } } , \mathbf { \boldsymbol { D } } )$ 仿真近似 $\mathbf { p } ( \mathbf { Z } | \mathbf { D } )$ 。 $\mathfrak { p } ( \mathbf { \boldsymbol { z } } _ { \mathrm { i } } | \mathbf { \boldsymbol { z } } _ { \mathrm { - i } } , \mathbf { \boldsymbol { D } } )$ 表示对于词汇表中 $\mathbf { V }$ 的一个词t，其当前采样的主题 $Z _ { \mathrm { i } }$ 依赖于其他时刻采样的主题 $\mathbf { z } _ { \mathrm { - i } } \circ \mathbf { \mathsf { p } } ( \mathbf { z } _ { \mathrm { i } } \mid \mathbf { z } _ { \mathrm { - i } } , \mathbf { D } )$ 通过吉布斯采样公式得到[22]。

$$
\mathrm { p } ( \mathbf { z } _ { \mathrm { i } } = \mathbf { k } \mid \mathbf { z } _ { \mathrm { - i } } , \mathbf { D } ) = \frac { \mathbf { n } _ { \mathbf { k } , \mathrm { - i } } ^ { ( \mathrm { t } ) } + \mathsf { \beta } } { \left[ \sum _ { \mathrm { t = l } } ^ { | \mathbf { V } | } ( \mathbf { n } _ { \mathbf { k } } ^ { ( \mathrm { t } ) } + \mathsf { \beta } ) \right] - 1 } \cdot \frac { \mathbf { n } _ { \mathbf { m } , \mathrm { - i } } ^ { ( \mathrm { k } ) } + \mathbf { \alpha } \alpha } { \left[ \sum _ { \mathrm { k = l } } ^ { \mathrm { K } } ( \mathbf { n } _ { \mathbf { m } } ^ { ( \mathrm { k } ) } + \mathbf { \alpha } \mathbf { \alpha } ) \right] - 1 }
$$

其中, $| \mathbf { V } |$ 表示词汇表 $\mathbf { V }$ 的大小; ${ \bf n } _ { \bf k } ^ { \left( \mathrm { t } \right) }$ 表示词t采样为主题 $\mathbf { k }$ 的总次数, ${ \bf n } _ { \bf k , - i } ^ { ( \mathrm { t } ) }$ 表示词t在其他时刻采样为主题k的次数； $\mathtt { n } _ { \mathrm { m } } ^ { \mathrm { ( k ) } }$ 表示文本 ${ \bf d } _ { \mathrm { m } }$ 中采样为主题 $\mathbf { k }$ 的总词数,${ \mathfrak { n } } _ { \mathrm { m , - i } } ^ { ( \mathrm { k } ) }$ 表示文本 ${ \bf d } _ { \mathrm { m } }$ 中在其他时刻采样为主题 $\mathbf { k }$ 的词数。

主题采样完成后，基于采样得到的样本可以估计出模型的文本-主题分布矩阵0及主题-词分布矩阵 $\Phi$ ，公式如下[22]

$$
\begin{array} { l } { { \displaystyle \mathfrak { \theta } _ { \mathrm { m , k } } = \frac { \bar { \bf n } _ { \mathrm { m } } ^ { ( \mathrm { k } ) } + \alpha } { \sum _ { \mathrm { k = 1 } } ^ { \mathrm { K } } ( \bar { \bf n } _ { \mathrm { m } } ^ { ( \mathrm { k } ) } + \alpha ) } } } \\ { { \displaystyle \Phi _ { \mathrm { k , t } } = \frac { \bar { \bf n } _ { \mathrm { k } } ^ { ( \mathrm { t } ) } + \beta } { \sum _ { \mathrm { t = 1 } } ^ { | \mathrm { V } | } ( \bar { \bf n } _ { \mathrm { k } } ^ { ( \mathrm { t } ) } + \beta ) } } } \end{array}
$$

# 3词向量与LDA结合的半监督分类方法

# 3.1方法流程架构描述

LDA主题模型从“文本"粒度层面对文本建模，在传统长文本分类任务中取得不错效果，但应用于短文本分类时效果很差；词向量属于"词"粒度层面的模型,在词语的语义相似度计算方面表现优越，但应用于文本级别的语义表示还有待研究。短文本介于“词"粒度与"文本"粒度之间，鉴于此，本文提出一种词向量与LDA相融合的短文本分类方法，从“词"粒度层面与“文本"粒度层面同时对短文本建模；另外，词向量及LDA模型的训练是在大规模无标注数据集上完成的，仅分类器的训练需要小规模的已标注训练数据，属于半监督学习方法。方法流程如图5所示。

大规模 Y 预处理 小规模训练 新数据数据集 数据集√ ↓ L 牛训练词向量 训练LDA模型 预处理 预处理！√ √ ！  
相加平均合成法 特征权重计算 特征扩展 二二！i? ！ii  
短文本向量d' 短文本向量d" 1立√ 1 词向量与LDA结合向量拼接 的短文本分类模型d计算机 训 菜练」 类经济k-NN分类器： ：体育

(1）构建一个大规模无标注数据集及一个小规模已标注数据集，并进行数据预处理;(2）在大规模无标注数据集上训练词向量及LDA主题模型;(3）在小规模已标注数据集上融合词向量与LDA对短文本建模;(4)构建一个k 近邻分类器(k-NN)对新的短文本进行分类，测试本文方法的分类效果。

# 3.2数据集构建及预处理

数据集的构建对于文本分类至关重要。分类任务属于有监督学习，需要大量已标注数据保证学习的准确性。本文分类方法属于半监督学习，仅需要小部分已标注数据，有效降低了人工数据标注的工作量。需要构建一个大规模无标注数据集D及一个小规模有标注数据集 $\mathbf { D ^ { \prime } }$ ，对两个数据集有以下要求：

(1）数据集应符合正常的语言表达习惯;(2）数据集所包含的领域应与分类任务一致;(3）数据集应最大程度地包含并均衡分布于领域的各个潜在主题;(4）大规模无标注数据集应包含足够多的领域及主题相关词。

数据集预处理主要包括中文分词、停用词过滤等操作。对于小规模已标注训练数据集还需采用 $\chi ^ { 2 }$ 统计进行特征选择。 $\chi ^ { 2 }$ 统计值反映了词语t与数据集类别c的主题相关性，如下所示[2]。

$$
\chi ^ { 2 } ( \mathrm { t , c } ) = \frac { ( \mathrm { A \cdot D - B \cdot C } ) ^ { 2 } } { ( \mathrm { A + B } ) \cdot ( \mathrm { C + D } ) }
$$

公式(10)中各参数含义如表1所示。

表1 $\textstyle \chi ^ { 2 }$ 统计值参数含义表  

<html><body><table><tr><td></td><td>包含词语t</td><td>不包含词语t</td></tr><tr><td>属于c类</td><td>A</td><td>C</td></tr><tr><td>不属于c类</td><td>B</td><td>D</td></tr></table></body></html>

# 3.3词向量与LDA融合的短文本表示模型

在大规模无标注数据集上训练词向量及LDA主题模型，然后融合词向量与LDA对短文本建模。

基于Word2Vec训练词向量，结果记为：

$$
\mathbf { x } = \{ \mathbf { C } ( \mathrm { t } _ { 1 } ) , \mathbf { C } ( \mathrm { t } _ { 2 } ) , \cdots , \mathbf { C } ( \mathrm { t } _ { | \mathrm { V } | } ) \}
$$

其中, $\mathbf { t } _ { \mathrm { n } }$ 表示词汇表 $\mathbf { V }$ 中第 $\mathfrak { n }$ 个词， $\mathbf { C } ( \mathrm { t } _ { \mathrm { m } } )$ 为 $\mathfrak { t } _ { \mathrm { m } }$ 的词向量表示。

基于吉布斯采样训练LDA，输出文件包括文本-主题分布矩阵0、主题-词分布矩阵 $\Phi$ 及主题词文件。主题词文件显示了每个潜在主题下概率最大(即主题相关性最强)的前n个词，主题词文件示例如表2所示。

表2主题词文件示例  

<html><body><table><tr><td>主题编号</td><td colspan="4">主题词及其概率值</td></tr><tr><td>Topic Oth:</td><td>教育 0.020447 人 0.013244</td><td>学校 教师</td><td>0.017544 0.012354</td><td>学生0.015859</td></tr><tr><td>Topic 1th:</td><td>比赛 中国0.011119</td><td>0.020663 中</td><td>0.012811 亚运会0.010645</td><td>选手0.011491</td></tr><tr><td>Topic 2th:</td><td>中 武器</td><td>0.009706 0.006090</td><td>美国 0.007455 系统 0.006072</td><td>美军0.006404</td></tr><tr><td>Topic 3th:</td><td>软件0.009364 程序0.004344</td><td>函数 过程</td><td>0.006048 0.004271</td><td>系统0.005572</td></tr></table></body></html>

词向量与LDA 结合的短文本建模方法具体实施步骤描述如下：

输入： $\textcircled{1}$ 小规模已标注的短文本训练数据集 $\mathbf { D ^ { \prime } }$ $\textcircled{2}$ 大规模无标注数据集 $\mathbf { D }$ 上训练得到的词向量;$\textcircled{3}$ 大规模无标注数据集 $\mathbf { D }$ 上训练得到的LDA模型。  
输出：训练数据集 $\mathbf { D ^ { \prime } }$ 的结合词向量与LDA的表示模型。

# (1）词向量合成

采用向量相加平均法得到 $ { \mathbf { D } } ^ { \prime }$ 的基于词向量合成的短文本表示模型，如下所示。

$$
{ \bf d _ { \mathrm { m } } } ^ { \prime } = \sum _ { \mathrm { w _ { j } \in \bf d _ { \mathrm { m } } ^ { \prime } } } \frac { \bf C ( \bf w _ { j } ) } { \bf N _ { \mathrm { m } } }
$$

其中, ${ \bf { d } } _ { \mathrm { { m } } } ^ { \mathrm { ~ \tiny ~ { ~ \prime ~ } ~ } }$ 表示 $\mathbf { D ^ { \prime } }$ 中第 $\mathbf { m }$ 篇短文本的基于词向量合成的短文本表示, $\mathbf { w } _ { \mathrm { j } }$ 为其中的词, $\mathrm { N _ { m } }$ 为词数, $\mathbf { C } ( \mathrm { w _ { j } } )$ 为词$\mathbf { W } _ { \mathrm { j } }$ 的词向量。

(2）基于LDA进行特征扩展

将 $ { \mathbf { D } } ^ { \prime }$ 中的每个词与LDA模型的主题-词分布矩阵${ \Phi }$ 相匹配，选择该词所属的概率最大的主题 $z _ { \mathrm { m a x } }$ ；然后将 $z _ { \mathrm { m a x } }$ 匹配LDA模型的主题词文件，选择主题 $z _ { \mathrm { m a x } }$ 下的前 $\mathbf { r }$ 个词作为该词的扩展特征，则 $\mathbf { D ^ { \prime } }$ 基于LDA的特征扩展模型如下：

$$
{ \bf d _ { \mathrm { m } } } ^ { \prime } = \{ { \bf w } _ { \mathrm { m l } } , ( { \bf c } _ { 1 1 } , { \bf c } _ { 1 2 } , \cdots , { \bf c } _ { \mathrm { l r } } ) , \cdots , { \bf w } _ { \mathrm { m n } } , ( { \bf c } _ { \mathrm { n l } } , { \bf c } _ { \mathrm { n } 2 } , \cdots , { \bf c } _ { \mathrm { n r } } ) \}
$$

其中, ${ \bf { d } } _ { \mathrm { { m } } } ^ { \quad \prime }$ 表示 $ { \mathbf { D } } ^ { \prime }$ 中第 $\mathbf { m }$ 篇短文本的基于LDA的特征扩展模型， $\mathbf { w _ { m n } }$ 为这篇短文本中的第 $\mathfrak { n }$ 个词,$( \mathbf { c } _ { \mathrm { n 1 } } , \mathbf { c } _ { \mathrm { n 2 } } , \cdots , \mathbf { c } _ { \mathrm { n r } } )$ 为 $\mathbf { w _ { m n } }$ 的 $\mathbf { r }$ 个扩展特征。

(3）基于词向量的扩展特征权重计算

公式(13)中，采用基于词频及逆向文档频(TermFrequency-Inverse DocumentFrequency,TFIDF)的方法计算被扩展特征 $\mathbf { w _ { \mathrm { m n } } }$ 的权重，TFIDF权重反映了特征词表征文本的能力[1]，公式如下。

$$
\mathrm { w e i g h t } ( \mathbf { w } _ { \mathrm { m n } } ) = \mathrm { T F I D F } ( \mathbf { w } _ { \mathrm { m n } } ) = \frac { \mathrm { T F } ( \mathbf { w } _ { \mathrm { m n } } ) \cdot \mathrm { I D F } ( \mathbf { w } _ { \mathrm { m n } } ) } { \sqrt { \sum _ { \mathbf { w } _ { \mathrm { m n } } \in \mathbf { d } _ { \mathrm { m } } ^ { \ast } } \mathrm { [ T F ( \mathbf { w } _ { \mathrm { m n } } ) \cdot I D F ( \mathbf { w } _ { \mathrm { m n } } ) ] } ^ { 2 } } }
$$

其中， $\mathrm { T F } ( \mathrm { w } _ { \mathrm { m n } } )$ 表示 $\mathbf { w } _ { \mathrm { m n } }$ 的归一化词频,$\mathrm { I D F } ( \mathbf { w } _ { \mathrm { m n } } )$ 表示 $\mathbf { w _ { m n } }$ 的逆向文档频，分母部分是对TFIDF权重的归一化操作。

对于公式(13)中的扩展特征 $\mathbf { c } _ { \mathrm { n r } }$ ，其权重与两个因素有关： $\mathbf { c } _ { \mathrm { n r } }$ 所属的主题在文本中的重要性； $\mathbf { c } _ { \mathrm { n r } }$ 与其所属主题的相关度。由于 $\mathbf { c } _ { \mathrm { n r } }$ 所属主题是由被扩展特征$\mathbf { w _ { \mathrm { m n } } }$ 根据概率最大原则匹配LDA的主题-词分布矩阵得到的，因此认为 $\mathbf { w _ { m n } }$ 的 TFIDF 权重代表 $\mathbf { c } _ { \mathrm { n r } }$ 所属的主题在文本中的重要性， $\mathbf { c } _ { \mathrm { n r } }$ 与 $\mathbf { w _ { \mathrm { m n } } }$ 的语义相关度代表 $\mathbf { c } _ { \mathrm { n r } }$ 与其所属主题的相关度。 $\mathbf { c } _ { \mathrm { n r } }$ 与 $\mathbf { w _ { \mathrm { m n } } }$ 的语义相关度通过计算 $\mathbf { c } _ { \mathrm { n r } }$ 与 $\mathbf { w _ { \mathrm { m n } } }$ 的词向量的余弦值得到，记为$\sin ( \mathrm { c _ { \mathrm { n r } } } , \mathrm { w _ { \mathrm { m } } } )$ ，如下:

$$
\sin ( \mathbf { c } _ { \mathrm { n r } } , \mathbf { w } _ { \mathrm { m n } } ) = \frac { \mathbf { C } ( \mathbf { c } _ { \mathrm { n r } } ) \cdot \mathbf { C } ( \mathbf { w } _ { \mathrm { m n } } ) } { | \mathbf { C } ( \mathbf { c } _ { \mathrm { n r } } ) | \times | \mathbf { C } ( \mathbf { w } _ { \mathrm { m n } } ) | }
$$

其中， $\mathbf { C } ( \mathrm { c } _ { \mathrm { n r } } )$ 与 ${ \bf C } ( \mathrm { w } _ { \mathrm { m n } } )$ 分别为 $\mathbf { c } _ { \mathrm { n r } }$ 与 $\mathbf { w } _ { \mathrm { m n } }$ 的词向量表示。

综上，基于词向量的扩展特征权重计算方法如下：

$$
\mathrm { w e i g h t } ( \mathrm { c } _ { \mathrm { n r } } ) { = } \mathrm { T F I D F } ( \mathrm { w } _ { \mathrm { m n } } ) { \times } \mathrm { s i m } ( \mathrm { c } _ { \mathrm { n r } } { , } \mathrm { w } _ { \mathrm { m n } } )
$$

# (4）向量拼接

由于一个词可能含有多重语义，因此对于步骤(2)中的特征扩展模型 ${ \bf { d } } _ { \mathrm { { m } } } ^ { \quad \prime }$ ，可能会出现同一扩展特征多次出现的情况，这时需合并相同的扩展特征，并将其权重相加作为合并后的扩展特征的权重。最终，将此特征扩展模型 ${ \bf { d } } _ { \mathrm { { m } } } ^ { \quad \prime }$ 与步骤(1)中的基于词向量合成的模型 ${ \bf { d } } _ { \mathrm { { m } } } ^ { \mathrm { ~ \tiny ~ { ~ \prime ~ } ~ } }$ 进行顺序拼接，得到词向量与LDA结合的短文本表示模型，如下：

$$
{ \bf { d } } _ { \mathrm { { m } } } = \{ { \bf { d } } _ { \mathrm { { m } } } ^ { \prime } ; { \bf { d } } _ { \mathrm { { m } } } ^ { \prime \prime } \}
$$

其中，“;"表示向量顺序拼接操作， ${ \bf d } _ { \mathrm { m } }$ 为训练集$\mathbf { D ^ { \prime } }$ 中第 $\mathbf { m }$ 篇短文本的词向量与LDA结合的向量表示。

# 3.4构建 $\mathbf { k }$ 近邻分类器

$\mathbf { k }$ 近邻分类(k-NN)算法作为一个经典的机器学习算法，应用于文本分类领域具有较高的稳定性，其原理简单直接：将新数据与训练数据集中的样本进行比较，选择与新数据最相似的前 $\mathbf { k }$ 个样本的类标签作为新数据的候选类标签，最后统计候选类标签中数量最多的类标签作为新数据的分类结果。

本文方法的最后一步通过构建一个k-NN分类器以建模后的短文本训练集与待分类短文本数据作为输入，使用余弦相似度作为新数据与训练集样本的比较函数，完成对新数据的分类并测试本文方法的分类效果。

# 4实验结果及分析

# 4.1 实验设置

采用复旦大学中文文本分类语料库作为大规模数

# 32 现代图书情报技术

据集用于训练词向量及LDA主题模型。选取1000篇少于150字的短文本构建有类别标注的小规模训练数据集用于训练最近邻分类器，数据集均衡分布于计算机、经济、环境、艺术、体育5个领域，每个领域各200篇。另外选取670篇短文本作为测试数据集，其中，计算机类145篇，经济类130篇，环境类135篇，艺术类120篇，体育类140篇，训练集和测试集之间彼此不重叠，不包括重复文本。中文分词采用中国科学院计算技术研究所的NLPIR汉语分词系统。基于Word2Vec训练词向量，依据实验经验设置词向量维数为50，当维数设置超过50时实验结果无明显提升。基于吉布斯采样方法训练LDA主题模型，依据GibbsLDA $^ { + + }$ 手册设置参数[23]，隐含主题数K设置为100，超参数取$\alpha = 0 . 5 \mathrm { ~ , ~ } \beta = 0 . 1$ ，主题词数设置为20。依据实验经验设置 $_ { \mathrm { k - N N } }$ 分类器的近邻数 $\mathbf { k } ,$ 一般不超过训练样本数的平方根，取 $k { = } 2 0$ ○

# 4.2 评价指标

分类结果用准确率(Precision,Pr)、召回率(Recall,$\mathrm { R e } )$ 和调和平均值 $\mathrm { F } _ { 1 }$ 三个指标来衡量，公式如下[1]。

$$
\mathrm { P r } = { \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F P } } }
$$

$$
\mathsf { R e } = \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F N } }
$$

$$
\mathrm { F 1 } = { \frac { 2 \cdot \mathrm { P r } \cdot \mathrm { R e } } { \mathrm { P r } + \mathrm { R e } } }
$$

各参数含义如表3所示。

表3分类评价指标参数含义表  

<html><body><table><tr><td></td><td>分类为c类</td><td>分类非c类</td></tr><tr><td>实际为c类</td><td>TP</td><td>FN</td></tr><tr><td>实际非c类</td><td>FP</td><td>TN</td></tr></table></body></html>

其中，准确率考察的是分类结果的正确性，召回率考察分类结果的完备性。

# 4.3 结果与分析

(1）实验一

对CBOW模型进行修改，在CBOW模型输入层采用向量拼接法代替向量相加平均法引入词序信息，然后比较Word2Vec原版的CBOW与 Skip-gram以及本文修改后的CBOW这三个模型训练的词向量应用于本文分类方法时所取得的分类效果，比较结果如表4所示。

表4词向量训练模型比较结果  

<html><body><table><tr><td>词向量训练模型</td><td>准确率(%)</td><td>召回率(%)F1值(%)</td><td></td></tr><tr><td>Skip-gram</td><td>77.0</td><td>81.5</td><td>79.2</td></tr><tr><td>原版CBOW(向量相加平均)</td><td>81.1</td><td>83.7</td><td>82.4</td></tr><tr><td>修改后 CBOW(向量拼接)</td><td>81.8</td><td>82.6</td><td>82.2</td></tr></table></body></html>

从表4可以看出：在短文本分类任务上，CBOW模型优于 Skip-gram 模型；修改后的CBOW 模型相比原CBOW模型仅在分类准确率上略有提升，而召回率及 $\mathrm { F } _ { 1 }$ 值均略有下降，因此认为修改后的CBOW模型相比原CBOW模型无明显差别。综上，考虑到原CBOW模型计算复杂度低，因此本文方法基于原CBOW模型训练词向量。

# (2）实验二

测试本文方法在短文本分类任务上的分类效果，并与三种基于单一模型的分类方法 $( \mathrm { V S M + k { \mathrm { - } } N N }$ 、词向量 $+ \mathbf { k } { \mathrm { - } } \mathbf { N N }$ 、LDA+k-NN)进行比较，结果如表5、表6所示。

表5本文方法分类效果  

<html><body><table><tr><td>类别</td><td>准确率(%)</td><td>召回率(%)</td><td>F1值(%)</td></tr><tr><td>计算机</td><td>85.3</td><td>87.1</td><td>86.2</td></tr><tr><td>经济</td><td>83.0</td><td>84.7</td><td>83.8</td></tr><tr><td>环境</td><td>79.3</td><td>84.2</td><td>81.7</td></tr><tr><td>艺术</td><td>78.3</td><td>80.6</td><td>79.4</td></tr><tr><td>体育</td><td>79.4</td><td>82.0</td><td>80.7</td></tr><tr><td>平均值</td><td>81.1</td><td>83.7</td><td>82.4</td></tr></table></body></html>

表6不同分类方法比较结果  

<html><body><table><tr><td>分类方法</td><td>准确率(%)</td><td>召回率(%)</td><td>F1值(%)</td></tr><tr><td>VSM+k-NN</td><td>74.7</td><td>77.2</td><td>75.9</td></tr><tr><td>词向量+k-NN</td><td>77.4</td><td>79.6</td><td>78.5</td></tr><tr><td>LDA+k-NN</td><td>66.2</td><td>69.3</td><td>67.7</td></tr><tr><td>本文方法 (词向量+LDA+k-NN)</td><td>81.1</td><td>83.7</td><td>82.4</td></tr></table></body></html>

表5显示本文分类方法在短文本数据集各个领域类别均能获得满意的分类效果，是一种有效的短文本分类方法。表6显示，前三种基于单一模型的分类方法中，基于LDA模型的方法分类效果最差，甚至低于传统的基于词袋模型的分类方法，表明LDA模型并不适用于短文本分类；与三种基于单一模型的分类方法相比，本文方法在三个分类指标上均有提升，其中分类准确率指标至少提升 $3 . 7 \%$ ，召回率至少提升 $4 . 1 \%$

F1值至少提升 $3 . 9 \%$ 这是因为方法融合词向量与LDA主题模型对短文本进行建模，能更精细地表示短文本语义信息，因此有效克服了单一LDA模型主题聚焦性差的缺陷以及词袋模型的特征稀疏问题，从而提高短文本分类效果。

# 5结语

本文提出一种同时从“词"粒度及“文本"粒度层面建模短文本的思路，并由此提出了一个词向量与LDA相融合的短文本分类模型。另外，该分类方法基于无标注数据集进行短文本建模，属于一种半监督学习方法。实验部分比较了该方法与三种传统基于单一模型方法的分类效果，此外还探讨了不同的词向量训练模型应用于本文方法时的优劣。后续将重点研究该分类方法应用于不同分类器的情况。

# 参考文献：

[1]Yang Y,Liu X.A Re-examination of Text Categorization Methods[C]. In: Proceedings of the 22nd Annual International ACM SIGIR Conference on Research and Development in Information Retrieval.ACM,20o3:42-49.   
[2] 邸鹏，段利国．一种新型朴素贝叶斯文本分类算法[J]．数 据采集与处理,2014,29(1):71-75.(Di Peng,Duan Liguo. New Naive Bayes Text Classification Algorithm [J].Journal of Data Acquisition and Processing,2014,29(1): 71-75.)   
[3] Joachims T.Learning to Classify Text Using Support Vector Machines:Methods,Theory and Algorithms [M].Springer Berlin,2002.   
[4] 王仲远，程健鹏，王海勋，等．短文本理解研究[J]．计算机 研究与发展，2016，53(2):262-269.(Wang Zhongyuan, ChengJianpeng， WangHaixun， etal.ShortText Understanding:A Survey [J].Journal of Computer Research and Development,2016,53(2): 262-269.)   
[5] Lebanon G. Metric Learning for Text Documents[J].IEEE Transactions on Pattern Analysis & Machine Intelligence, 2006,28(4):497-508.   
[6] 朱征宇，孙俊华．改进的基于知网的词汇语义相似度计算 [J]．计算机应用，2013，33(8)：2276-2279,2288．(Zhu Zhengyu, Sun Junhua．Improved Vocabulary Semantic Similarity Calculation Based on HowNet [J].Journal of Computer Applications,2013,33(8): 2276-2279,2288.)   
[7]王荣波，谌志群，周建政，等．基于Wikipedia 的短文本语 义相关度计算方法[J]．计算机应用与软件，2015,32(1): 82-85,92.（Wang Rongbo, Chen Zhiqun, Zhou Jianzheng, et al. Short Texts Semantic Relevance Computation Method Based on Wikipedia [J]. Computer Applicationsand Software,2015,32(1): 82-85,92.)   
[8]Deerwester S,Dumais S T, Furnas G W, et al. Indexing by Latent Semantic Analysis [J]. Journal of the Association for Information Science and Technology,1990,41(6): 391-407.   
[9]Blei D M,Ng AY,Jordan MI. Latent Dirichlet Allocation [J]. Journal of Machine Learning Research,2003,3: 993-1022.   
[10]姚全珠，宋志理，彭程．基于LDA模型的文本分类研究[J]. 计算机工程与应用,2011,47(13):150-153.(Yao Quanzhu, Song Zhili,Peng Cheng. Research on Text Categorization Based on LDA [J]. Computer Engineering and Applications, 2011,47(13): 150-153.)   
[11]Rubin T N,Chambers A,Smyth P,et al. Statistical Topic Models for Multi-label Document Classification [J].Machine Learning,2012,88(1-2): 157-208.   
[12]胡勇军,江嘉欣，常会友．基于LDA 高频词扩展的中文短 文本分类[J]．现代图书情报技术，2013(6):42-48.(Hu Yongjun,Jiang Jiaxin, Chang Huiyou. A New Method of Keywords Extraction for Chinese Short-text Classification [J].New Technology of Library and Information Service, 2013(6): 42-48.)   
[13] Chen M,Jin X,Shen D. Short Text Classification Improved by Learning Multi-granularity Topics [C]. In: Proceedings of the 22nd International Joint Conference on Artificial Intelligence.AAAI Press,2011: 1776-1781.   
[14] Phan X H, Nguyen L M, Horiguchi S. Learning to Classify Short and Sparse Text & Web with Hidden Topics from Large-scale Data Collections [C]. In: Proceedings of the 17th Information Conference on World Wide Web (WWW'08). New York: ACM,2008:91-100.   
[15] MikolovT,SutskeverI，Chen K，et al.Distributed RepresentationsofWordsandPhrasesandTheir Compositionality [J].Advances in Neural Information Processing Systems,2013,26: 3111-3119.   
[16]Turney PD,Pantel P.From Frequency to Meaning:Vector Space Models of Semantics [J].Journal of Artificial Intelligence Research,2010,37(1): 141-188.   
[17]Kim Y. Convolutional Neural Networks for Sentence Classification [C].In: Proceedings of the 2014 Conference on Empirical Methodsin Natural Language Processing. Stroudsburg,PA: ACL,2014: 1746-1751.   
[18] Chapelle O, Schlkopf B,Zien A. Semi-Supervised Learning [J].Journal of the Royal Statistical Society,2010,6493(10): 2465-2472.   
[19]Bengio Y,Ducharme R,Vincent P,et al.A Neural Probabilistic Language Model [J]. Journal of Machine Learning Research,2003,3(6):1137-1155.   
[20]Mikolov T,Chen K,Corrado G,et al.Efficient Estimation of Word Representations in Vector Space[C].In:Proceedings of Workshop atICLR.2013.   
[21]Morin F,Bengio Y.Hierarchical Probabilistic Neural Network Language Model [C]. In: Proceedings of Workshopat AISTATS.2005.   
[22]Porteous I,Newman D,Ihler A,et al.Fast Collapsed Gibbs Sampling for Latent Dirichlet Allocation [C].In: Proceedings of the 14th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.Las Vegas,USA. 2008.   
[23]GibbsLDA $^ { + + }$ ：A $\mathrm { C / C ^ { + + } }$ Implementation of Latent Dirichlet Allocation (LDA）Using Gibbs Sampling for Parameter Estimation and Inference [EB/OL]. [2016-05-15]. https:// sourceforge.net/projects/jgibblda/.

# 作者贡献声明：

张群，王红军：提出研究思路，设计研究方案;  
张群：进行实验，采集、清洗和分析数据，论文起草;  
王红军，王伦文：论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据[1]由作者自存储，E-mail:1875586718@qq.com；支撑数据[2-4]见期刊网络版http://www.infotech.ac.cn。  
[1]张群.dataset.zip.用于训练词向量与LDA主题模型的大规模数据集.  
[2]张群.word2vec.zip.用于训练词向量的word2vec 源码.[3]张群.GibbsLDA $^ { + + }$ .zip.基于吉布斯采样的LDA主题模型程序包.  
[4]张群.LDA_result.zip.LDA主题模型训练结果文件.

收稿日期:2016-08-01   
收修改稿日期:2016-10-14

# Classifying Short Texts with Word Embedding and LDA Model

Zhang QunWang HongjunWang Lunwen (Electronic Engineering Institute of PLA,Hefei 23oo37, China)

Abstract: [Objective] This paper proposes a short text classification method with the help of word embedding and LDA model,aiming toaddress the topic-focusand feature sparsityissues.[Methods]First, we built short textsemantic models atthe“word”and“text”levels.Second,we trained the word embeding with Word2Vec and created ashorttext vector at the“word” level. Third, we trained the LDA model with Gibbs sampling,and then expanded the feature of shorttexts in accordance with the maximum LDA topic probability.Fourth,we calculated the weight of expanded features based on word embeddng similarity to obtain short text vector at the“text”level.Finall,we merged the “word"and“text”vectors to establish an integral short text vector and then generated their classification scheme with the k-Nearest Neighbors clasifier.[Results]Comparedtothe traditionalsingleton-based methods,the precision,recall, F1 of the new method were increased by $3 . 7 \%$ ， $4 . 1 \%$ and $3 . 9 \%$ ，respectively. [Limitations] Our method was only examined with the k-Nearest Neighbors classifier.More research is needed to study its performance with other clasifiers.[Conclusions]The proposed method could effectively improve the performance of short text classification systems.

Keywords: Short text classificationWord embeddingLatent Dirichlet Allocation k-Nearest Neighbors

# 哈佛大学图书馆选择ExLibrisAlma为其下一代图书馆平台

近日，哈佛大学图书馆已选择Ex Libris Alma图书馆管理服务作为该图书馆支持研究、教学和学习战略的一部分。哈佛大学是第33 个选择 Alma 解决方案的研究图书馆协会(Association of Research Libraries,ARL)成员。

凭借其统一的资源管理功能、高级工作流程、强大的基础架构和云平台,Alma解决方案将帮助哈佛大学图书馆实现在整个图书馆网络的单一框架内有效管理印刷和在线馆藏的目标。

哈佛大学图书馆馆长 Sarah Thomas 指出：“哈佛大学图书馆的战略目标之一是通过直观的发现系统、专业网络和全球合作，有效地访问知识和数据世界。Alma是一个强大的平台，其强大的功能、易用性和云服务将帮助我们实现直接目标以及长期目标。”

Ex Libris 总裁 Matti Shem Tov 评论说:“哈佛大学图书馆是 Ex Libris 的长期合作伙伴，其自 200 年以来一直在使用Aleph ILS，自2014年以来一直使用Primo的发现和交付解决方案。哈佛大学图书馆采用 Alma 证明了Alma为全球顶级学术机构的图书馆提供管理服务的能力。我非常高兴哈佛大学图书馆现在加入了Alma社区，并期待其对这个活跃团体的贡献。”

(编译自:htp:/www.proquest.com/about/news/2l6/Harvard-Library-elects-the-Ex-Libris-Alma-Next-Generation-Librarytml)

(本刊讯)