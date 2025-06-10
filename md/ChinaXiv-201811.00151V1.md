# 情境特征及其在情感分类模型中的应用\*

刘栋ä，张彩环b

(洛阳师范学院 a.信息技术学院;b.数学科学学院，河南 洛阳 471022)

摘要：为研究情境特征在文本分类中的作用，提出了一种层级双向LSTM模型用于情感分类问题。该模型首先将句子分词，把词向量作为第一层双向LSTM模型的输入；其次从文档中提取出稠密、连续的向量作为情境特征；然后将第一层模型的输出向量和情境向量共同输入第二层双向LSTM；最后将这种层级双向的LSTM 模型的输出向量通过sigmoid 函数进行分类。情境向量作用于每个句子，一致的情感得到增强，不一致的情感被弱化，从而提高了分类的精度。在两个公开数据集上的实验表明，整合了情境特征的层级双向LSTM取得较优的精度。除此之外，通过在一个包含2万余条中文评论的公开数据集上对模型进行测试，表明该模型测试正确率相比于普通的LSTM和双向LSTM都有提升，说明情境特征对于提升情感分类的作用比较显著。

关键词：情境特征；情感分类；层级双向LSTM 中图分类号：TP391 doi: 10.19734/j.issn.1001-3695.2018.06.0459

# Context feature and its application on sentiment classification model

Liu Donga, Zhang Caihuanb (a.SchoolofInformationTechnology,b.choolofMathematics,LuoyangNormalUniversityLuoyangHenan4722,Cina)

Abstract: Focusingonthe effect ofcontext feature on sentimentclassificationproblem,this paper presentedahierarchical BiLSTMsentimentclassification model.The modelincludes two level Bi-LSTMs.Themodel acceptedaseriesofwordembedding as inputin sentence-level.The context feature of whole document was transformed into a dense and continuous vector, concatenated withoutput vectors ofthesentence-levelBi-LSTMsandfedinto sigmoidlayerto predictsentimentpolarityof the document.Intuitively,the modelcomputesacontextvector mask for everysentence in document.Theconsistence polarity was enhanced,andthe inconsistent wasweakened.Thisresultedinbeteraccracy.TheexperimentonIMDBandYelp2Ol3dataset shows that this hierarchical modelwithcontextfeatureoutperforms thecommonLSTMandBi-LSTMmodels significantly,nd iscompetitive withthe state-of-the-artresults.Experimentonanoterdataset including20thousands Chinesereviews was used to analyze the causes of this competitive advantage.

Key words:context feature; sentiment classification; hierarchical Bi-LSTM

# 0 引言

文本分析的一个重要研究方向是对文本所表达的情感进行分类。当前，随着互联网以及移动端应用的发展和普及，网络上形成了海量的文本，特别是评论，表达了用户对商品、服务、电影及时政等的观点和看法。对这些文本进行深入的分析和挖掘有着重要的应用价值，并产生巨大的经济效益[1]，比如通过分析商品评论能够为商家提供产品反馈，进一步改进服务质量，优化营销策略；对网络评论进行情感分析，及时了解社情民意等。因此对文本的情感分类进行研究是十分有意义的。

文本情感分类从类别上来分，大多数研究都分成正向和负向两种极性；也有涉及到三分类（正向、负向、中立）[3]和多分类的（将用户的情感按强度量化为多个等级）[4。从所处理的文本粒度来看，可以分为文档级、句子级和词语级[5]。从所处理的语言来看，可以分为单语言和跨语言情感分类。从涉及的领域来看，又可以分为单领域及跨领域。

从文本情感分类技术上来看，早期的研究主要依赖于情感词汇，通过从文本中挑选出情感词作为特征，再利用这些特征进行情感分类，这类方法的准确率并不理想[2]。之后机器学习的方法包括有监督、无监督、半监督学习的方法被应用于文本情感分类问题使得分类结果得以提升[6\~17]。随着深度学习技术在图像和语音方面所取得的巨大成功，人们将此类技术运用于情感分类问题，也取得了一定的进展，Severyn 等人[18]使用无监督的语言模型来训练词向量，这些词向量作为一个深度CNN（convolutionalneural network）的初始化参数来对Twitter进行情感分类，在Semeval-2015的两个子任务中取得很好的结果；Tang等人[19将目标信息整合到LSTM中，建模了目标与它上下文之间的相关性，提升了情感分类的精度；Nguyen 等人[20]提出一种基于RNN（recusiveneuralnetwork）情感分类方法，该方法考虑了依赖和句子的成分组成树。这类方法取得的结果说明深度学习在自然语言理解方面大有可为。然而，这些方法只考虑了短语级，或者句子级的关系，不能建模句子与句子间的情感延续、加强或转折等关系。深度神经网络能够获得不同抽象级别的特征，因此增加神经网络层数无疑是一种重要的方法，但是对于自然语言理解来说，增加神经网络的层数对计算资源和数据集的大小都产生了新的要求，相比来说，使用重复堆叠的层级模型更加合适，比如Denil等人[2I]就使用了一个层级的卷积神经网络来抽取评论中的重要句子；Li等人[22]将层级LSTM（long shorttermmemory）自动编码器应用于段落生成和重构；Ji等人[23]基于RNN（recurrentneuralnetworks）和CNN进行短文本的分类，但该方法是句子级的，并且只考虑了目标前后有限个的句子；与本文采用方法最类似的是Ruder等人[24]的层级模型，他们同样采用了层级的、双向的LSTM模型进行情感分类，但不同的是，他们在句子级加入了产品方面的信息，而本文则是在每个句子中加入了情境信息。

在讨论文档所表示的情感时离不开它的上下文，也就是句子所处在情境，因此在情感分类的模型中加入文档的情境无疑是有益的。本文讨论了文档情境的分布式表示，这种表示方法曾经被Choi等人[27用在神经机器翻译模型中，取得了不错的效果。Ghosh等人[31在模型中整合入了情境特征（主题)，在三个自然语言处理（NLP）任务上评估CLSTM模型：接续词语预测、接续语句预测、语句话题预测，能做到 $20 \%$ 的提升。

本文的贡献和创新之处体现在如下几个方面：a)本文将情境信息表示为一个连续的稠密向量应用于句子的情感表达，与全局情境一致的情感得到了加强，不一致的情感被弱化，因此得到了更好的分类效果；b)通过实验说明了情感分类模型在加入了情境信息后，分类精度不仅优于普通的双向LSTM模型，而且与一些采用注意力机制的模型相比，在经过适当设置超参数后测试精度也有相当大的提高。

# 1情境的表示及情感分类模型

# 1.1情境的分布式表示

将每条评论看成是一个文档（document)，每个文档截断为包含个句子（根据语料选择10)，如果不足个句子的，添加只包含空字符串的句子补全；每个句子通过分词，截断成包含 $\mathcal { m }$ 个词(5)，不足 $\mathcal { m }$ 个的添加空字符串补全。这样第i句子可以由词向量连接起来，表示为

$$
{ \cal S } _ { i } = ( x _ { 1 } ^ { i } , x _ { 2 } ^ { i } , \cdots , x _ { m } ^ { i } )
$$

其中： $\boldsymbol { x } _ { \mathrm { i } } \in \mathbb { R } ^ { \mathrm { k } }$ 是第i个词的k维词向量。

同理，文档第 $i$ 个文档可以由句子连接起来，表示为

$$
w _ { i } = ( s _ { 1 } ^ { i } , s _ { 2 } ^ { i } , \cdots , s _ { i } ^ { i } )
$$

在分析一条评论的情感时，可以把评论认为是一篇文档，整个文档构建了一个情境，因此情境可以表示为文档中所有的词组成的无序集合，同Choi等人[27]采用的方法一样，本文把情境cx定义如下：

$$
c ^ { x } = \frac { 1 } { T } \sum _ { t = 1 } ^ { T } x _ { t }
$$

其中：T为文档中词的个数。

# 1.2层级双向LSTM模型

LSTM是一种特殊类型的RNN，可以学习长期依赖信息[25]LSTM通过在RNN单元增加输入、输出和忘记门来建模长期依赖，在很多问题，LSTM都取得了巨大的成功，并得到了广泛的使用。在对评论的情感分析中，人们认识到长期依赖问题同样有着重要的影响，一条评论不仅前面的句子可以反映出客户所要表达的感情，后面的句子很多时候或者是对情感的加强，或者是情感的反转，因此在模型中使用了层级双向的LSTM，分为句子级和文档级。

a)在句子级设置双向LSTM，对于句子中的词 $\boldsymbol { w } _ { t }$ ，将 $\boldsymbol { w } _ { t }$ 对应的词向量 $\cdot _ { x _ { t } }$ 、前一个单元的输出 $\scriptstyle \mathcal { k } _ { t - 1 }$ 和单元状态 $C _ { t ^ { - 1 } }$ 输入前向LSTM来计算下一个输出 $\mathbf { \nabla } _ { \cdot t }$ 和单元状态 $C _ { t }$ 。先计算输入门 $i _ { t }$ 和单元状态候选值 $\boldsymbol { C } _ { t } ^ { ' }$ 以及忘记门 $f _ { t }$ ：

$$
\begin{array} { r l } & { i _ { t } = \sigma ( W _ { i } x _ { t } + U _ { i } h _ { t - 1 } + b _ { i } ) } \\ & { C _ { t } ^ { ' } = \operatorname { t a n h } ( W _ { c } x _ { t } + U _ { c } h _ { t - 1 } + b _ { c } ) } \\ & { f _ { t } = \sigma ( W _ { f } x _ { t } + U _ { f } h _ { t - 1 } + b _ { f } ) } \end{array}
$$

由此计算新单元状态值：

$$
C _ { t } = i _ { t } * C _ { t } ^ { ' } + f _ { t } * C _ { t - 1 }
$$

最后计算出输入门的值和本LSTM 单元的输出 $h _ { \scriptscriptstyle t }$ ：

$$
\begin{array} { l } { o _ { t } = \sigma ( W _ { o } x _ { t } + U _ { o } h _ { t - 1 } + b _ { o } ) } \\ { h _ { t } = o _ { t } * \operatorname { t a n h } ( C _ { t } ) } \end{array}
$$

其中： $W _ { i } , W _ { c } , W _ { f } , W _ { o } , U _ { i } , U _ { c } , U _ { f } , U _ { o }$ 为权重矩阵， $b _ { i } , b _ { c } , b _ { f } , b _ { o }$ 为偏置向量。

这个前向LSTM是按照词出现的先后次序进行处理的，因此可以充分利用先前的信息；同理，后向LSTM以相反的次序处理，可以充分利用后面的信息。某时刻的输出由两个LSTM对应时刻的相应状态连接而成。

b)在句子级上面堆叠一个双向LSTM。不同的是，这个双向LSTM是把句子级LSTM的输出与情境向量 $E$ 连接起来作为输入的，构成了第二层的双向LSTM，增加了情境向量后的输入门 $i _ { t }$ 和单元状态候选值 $\boldsymbol { C } _ { t } ^ { ' }$ 以及忘记门 $f _ { t }$ 修改为如下公式：

$$
\begin{array} { r l } & { \boldsymbol { i } _ { t } = \sigma ( \boldsymbol { W } _ { i } \boldsymbol { x } _ { t } + \boldsymbol { U } _ { i } \boldsymbol { h } _ { t - 1 } + \boldsymbol { W } _ { e } \boldsymbol { E } + \boldsymbol { b } _ { i } ) } \\ & { \boldsymbol { C } _ { t } ^ { ' } = \operatorname { t a n h } ( \boldsymbol { W } _ { c } \boldsymbol { x } _ { t } + \boldsymbol { U } _ { e } \boldsymbol { h } _ { t - 1 } + \boldsymbol { W } _ { e } \boldsymbol { E } + \boldsymbol { b } _ { c } ) } \\ & { \boldsymbol { f } _ { t } = \sigma ( \boldsymbol { W } _ { f } \boldsymbol { x } _ { t } + \boldsymbol { U } _ { f } \boldsymbol { h } _ { t - 1 } + \boldsymbol { W } _ { e } \boldsymbol { E } + \boldsymbol { b } _ { f } ) } \\ & { \boldsymbol { C } _ { t } = i _ { t } \boldsymbol { C } _ { t } ^ { ' } + \boldsymbol { f } _ { t } \boldsymbol { C } _ { t - 1 } } \\ & { \boldsymbol { O } _ { t } = \sigma ( \boldsymbol { W } _ { o } \boldsymbol { x } _ { t } + \boldsymbol { U } _ { o } \boldsymbol { h } _ { t - 1 } + \boldsymbol { W } _ { e } \boldsymbol { E } + \boldsymbol { b } _ { o } ) } \\ & { \boldsymbol { h } _ { t } = \boldsymbol { O } _ { t } \operatorname { t a n h } ( \boldsymbol { C } _ { t } ) } \end{array}
$$

c)第二层LSTM的输出连接起来形成的向量被传递给一个sigmoid函数，产生该文档在情感分类上的概率分布。模型的结构如图1所示。

![](images/cbca1439cd6f3eaad283a1bb0d187cee124fb4bb15a788e3240edde0dea087b9.jpg)  
图1HB-LSTM 模型结构图 Fig.1 Structure of HB-LSTM

# 2 实验及结果分析

# 2.1 数据集与训练

本文在两个数据集上进行了评估：IMDB和Yelp2013。数据集由Tang 等人[30建立并进行了相应的处理，训练集、开发集、测试集的比例为：8:1:1，与Chen等人[29]使用了相同的数据集，不同的是，在训练中Chen 等使用了200 维的预训练词向量，而本文是在模型中增加了嵌入层，生成了256维的词向量。基本的统计信息如下表所示：

<html><body><table><tr><td colspan="5">Table 1 Statistics of datasets</td></tr><tr><td>数据集</td><td>类别数</td><td>文档数</td><td>句子/文档</td><td>词/句子</td></tr><tr><td>IMDB</td><td>10</td><td>84919</td><td>16.08</td><td>24.54</td></tr><tr><td>Yelp2013</td><td>5</td><td>78966</td><td>10.89</td><td>17.38</td></tr></table></body></html>

实验中采用的基线模型是Bi-LSTM，评价指标为测试精度（accuracy），模型的训练目标是最小化交叉熵函数（binary_crossentropy）,使用Adam优化器，mini-batches设为128。

为了便于对实验结果进行分析，将模型应用于另一个中文数据集[26]，数据集涉及6个领域，包含了2万多条评论。主要是商品及酒店等服务评论，最短的评论只有一个字，如“好”,“赞”等，最长的评论2968个字，是关于旅游和酒店服务投诉的。所有的评论都被标注了正面或者负面情感。经过打乱次序后取前15000个作为训练集，其余的作为测试集。

在模型的输入层，使用了256维的词向量，情景向量256维；LSTM隐藏节点128个，Dropout设为0.5。在训练前所有文本进行了分词，使用的分词软件是jieba分词。

# 2.2 结果与比较分析

之前在数据集IMDB和Yelp2013上进行了测试，并且与单层的LSTM、Bi-LSTM进行了比较，通过情境向量的作用，分类正确率有了一定的提升。本次实验主要是以Bi-LSTM作为基线，验证情境向量的作用，因此将之与带情境特征的Bi-

LSTM和带情境特征的HB-LSTM两个模型进行比较，结果如表2所示，与之前一样采用了提前停机（early_stopping）的策略，容忍度(patience)为2个epoch。

Table2Results on IMDB and Yelp2013   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="2">IMDB</td><td colspan="2">Yelp 2013</td></tr><tr><td>训练精度</td><td>测试精度</td><td>训练精度</td><td>测试精度</td></tr><tr><td>Bi-LSTM</td><td>91.67</td><td>90.04</td><td>82.44</td><td>80.13</td></tr><tr><td>Bi-LSTMwith Context</td><td>91.68</td><td>90.21</td><td>82.40</td><td>80.49</td></tr><tr><td>HB-LSTM with Contex</td><td>91.63</td><td>90.32</td><td>82.53</td><td>80.94</td></tr></table></body></html>

从表2可以看出，和Bi-LSTM相比，HB-LSTM在两个数据集上的测试精度均有不同程度的提升。

由于使用了与Chen 等人[29]使用的相同数据集，并且同样是情感分类，因此可以与该结果进行比较分析。Chen等人实验中选择了RMSE作为损失函数，而本文采用的是交叉熵函数。表3中显示在这两种情况HB-LSTM与采用了注意力机制的NSC模型（ $\mathrm { { N S C + U P A } }$ 表示 neural sentiment classification withuserand products information）的测试精度比较。

表3两种损失函数情况下HB-LSTM与NSC+UPA的比较

表2在IMDB 和Yelp2013上的结果  
Table 3Effect of HB-LSTMand NSC+UPA with RMSE or binary_crossentropy as loss function.   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="2">IMDB</td><td colspan="2">Yelp 2013</td></tr><tr><td>RMSE</td><td>Binary Crossentropy</td><td>RMSE</td><td>Binary Crossentropy</td></tr><tr><td>NSC+UPA</td><td>53.3</td><td>N/A</td><td>65.0</td><td>N/A</td></tr><tr><td>HB-LSTM</td><td>50.03</td><td>90.32</td><td>48.78</td><td>80.94</td></tr></table></body></html>

从表3中可以看到结果的差异非常大，同样采用RMSE作为损失函数，HB-LSTM 的精度要比较 $\mathrm { { N S C + U P A } }$ 差3\~7个百分点。但如果采用Binary_Crossentropy作为损失函数，精度几乎提升一倍，其中的原因有可能是一些超参数的设置不同，这还有待于进一步研究。

中文数据集是有关商品及服务评论的情感数据集，属于二分类问题。LSTM模型在这样的二分类问题上已经取得了不错的效果。为了验证情境向量能否进一步改进模型的分类效果，实验选取单层LSTM作为基线模型，分别与双向LSTM（Bi-LSTM）、层级双向LSTM（HB-LSTM）进行比较。实验结果如表4所示。

表1数据集统计  
表4中文评论数据集上的结果比较  
Table 4Experimental result and comparision   

<html><body><table><tr><td>模型</td><td>训练精度</td><td>测试精度</td></tr><tr><td>LSTM</td><td>96.60</td><td>89.31</td></tr><tr><td>Bi-LSTM</td><td>96.62</td><td>89.45</td></tr><tr><td>HBLSTM</td><td>98.87</td><td>90.75</td></tr></table></body></html>

如表4所示，采用LSTM了的模型总体表现良好，LSTM对邻近的信息进行了整合，较好地考虑了每个句子中前后一定范围内的依赖关系，双向LSTM的改善空间不大。但是增加了情境特征后的层级双向LSTM（HB-LSTM）正确率则有着明显的提升，实验结果说明，增加了情境向量后，全局的情境信息在特征中产生了作用，取得了优于基线模型的改善。表5中列出的几个例子都是LSTM错分的，用于对比LSTM和HB-LSTM。

表5LSTM错分的例子  
Table 5Some wrong classification example by LSTM   

<html><body><table><tr><td>评论</td><td>LSTM</td><td>HBLSTM</td></tr><tr><td>很不错，到货很快，当天给客服打电话，下午安装人员就上</td><td></td><td></td></tr><tr><td>门了，速度啊！但但当时没有水，没有试试，应该没事的，万</td><td>negative</td><td>positive</td></tr><tr><td>一有问题还可以找厂家维护人员</td><td></td><td></td></tr><tr><td>原装用的气的热水器坏了，，换上了，，好用多，不会再出现</td><td></td><td></td></tr><tr><td>要等40秒以上才会有热水，且还不稳定的情况了，，现在用</td><td></td><td>positive</td></tr><tr><td>上美的电热水器5秒后就出热水，且稳定的恒温，好用，，建negative</td><td></td><td></td></tr><tr><td>议千万不要去买烧气的，!！就美的电热水器，经济且很实 用！</td><td></td><td></td></tr><tr><td>网速快，且方便VPN连到公司内部网，IT负责人把网络设</td><td></td><td></td></tr><tr><td>置得不错，表扬一下。但前台服务员态度达不到满意的标</td><td></td><td></td></tr><tr><td>准。酒店没有熨斗，因要见客户，只得拜托熨一件衬衫，说</td><td></td><td></td></tr><tr><td>了5块，结帐时却要价8块，说是服务费和加急费要3块。</td><td></td><td></td></tr><tr><td>打开玻璃淋浴间的门，才发觉右手至少要有2米长才可够得</td><td>postive</td><td>negative</td></tr><tr><td>着浴巾，只好滴着水出来拿。琢磨了一下，浴巾也不能带进</td><td></td><td></td></tr><tr><td>小小的淋浴间呀，不知谁设计的。没找到比其他宾馆更多的</td><td></td><td></td></tr><tr><td>优点，560块大洋花得有点冤，不再来了</td><td></td><td></td></tr></table></body></html>

第一个例子是一个比较明显的正向情感的表达，LSTM之所以用错分，是由于句子中使用了过多的否定词，如“没有水”“没事”“问题”等；第二条评论陈述了商品使用前后的对比情况，给出了“千万不要去买燃气的”这样的建议，这可能误导了LSTM，但HB-LSTM较好地把握了全局信息；第三条评论前后句子表达的含义出现了转折，前面夸赞了酒店的网络，但后面大段内容表达了对酒店设施、服务的不满，并表示“以后不会再来了”，因此总体来讲应该负面的情感占主导地位，对此HB-LSTM同样把握了总体信息，更好地考虑了总体情境在特征中的比重，作出了正确的判断。

# 3 结束语

目前在情感分析技术中一种常用的方法是将文档进行分词，去除停用词等预处理，经由一个前馈神经网络将词表示成稠密连续的词向量，再通过诸如LSTM、CNN等深度学习模型进行特征提取和情感分类，这种方法取得了一定的成果。本文分析了这种一般方法中存在的问题，比如情感在文档中的长期依赖问题，提出了利用文档整体所提供的情境信息来增强深度学习模型的特征提取能力，从而提高情感分类效果的假设。实验结果表明，这种整合了情境特征的模型与基线模型相比对于情感分类问题的作用是比较明显的。

在接下来的研究中将探索将情境特征的应用于更加广泛的分类问题，尤其是对社交网络文本的分析，将会在社区划分、舆情监控和分析等应方面有更大的价值。另一方面，类比于英文中字符级的深度学习模型[28]、图像处理中的基于像素点的模型，本文认为汉字是中文的基本单位，基于汉字的情感分析深度字习模型非常值得深入研究。

参考文献：   
[1]Tsytsarau M,Palpanas T. Survey on mining subjective data onthe Web[J]. Data Mining and Knowledge Discovery,2012,24 (3): 478-514.   
[2]Pang Bo,Lee L, Vaithyanathan S. Thumbs up?Sentiment classification using machine learning techniques [C]//Proc ofConference on Empirical Methods in Natural Language Processing. 2002: 79-86.   
[3] Xia Rui, Xu Feng,Zong Chengqing,et al. Dual Sentiment Analysis: Considering Two Sides of One Review [J]. IEEE Trans on Knowledge and Data Engineering,2015,27: 2120-2133.   
[4]Pang Bo,LeeL.Seeing stars:exploring class relationships for sentiment categorationwithrespect to rating scales[C]//Procof the 43rd Annual Meetingon Association for Computational Linguistics.Stroudsburg: Association for Computational Linguistics,20o5,115-124.   
[5]赵妍妍，秦兵，刘挺．文本情感分析[J]．软件学报,2010,21(8):1834- 1848.(Zhao Yanyan,Qin Bing,Liu Ting. Sentiment analysis [J]. Journal of Software,2010,21(8): 1834-1848. )   
[6]Li Shoushan,Xia Rui, Zong Chengqing,et al.A framework of feature selection methods for textcategorizatio[C]//Procof the47th Annual meeting of ACL. Stroudsburg: Association for Computational Linguistics. 2009, 692-700.   
[7]Wan Xiaojun. Using bilingual knowledge and ensemble techniques for unsupervised Chinese sentiment analysis [C]//ProcofEMNLP.Stroudsburg: Association for ComputationalLinguistics.20o8,553-561.   
[8]Lin Chenghua,He Yulan，Everson R，etal.Weakly supervised joint sentiment-topic detection from text[J].IEEE Transon Knowledge and Data Engineering,2012,24 (6): 1134-1145.   
[9] 孙艳，周学广，付伟．基于主题情感混合模型的无监督文本情感分析 [J].北京大学学报：自然科学版,2013,49(1):102-108.(Sun Yan,Zhou Xueguang,Fu Wei. Unsupervised Topic and sentiment unification model for sentiment analysis[J].ActaScientiarum Naturalium Universitatis Pekinensis,2013,49(1): 102-108.）   
[10]李素科，蒋严冰．基于情感特征聚类的半监督情感分类[J].计算机研 究与发展，2013,50(12):2570-2577.(Li Suke,Jiang Yanbing.Semisupervised sentiment classification based on sentiment feature clustering [J] Journal ofComputer Research and Development,2013,50 (12): 2570-2577.)   
[11]周志华．基于分歧的半监督学习[J]．自动化学报,2013,39(11):1871- 1878.(Zhou Zhihua.Disagreement-based Semi-supervised Learning [J]. Acta Automatica Sinica.2013,39 (11): 1871-1878.)   
[12]张晓梅，李茹，王斌，等．基于融合特征的微博主客观分类方法[J] 中文信息学报,2014,28 (4): 50-57.(Zhang Xiaomei,LiRu,Wang Bin,et al. Subjective and objective classification of micro-blog based on feature fusion [J].Journal of Chinese Information Processing,2014,28(4): 50-57.)   
[13] Zhao Yanyan,Qin Bing,Che Wanxiang，et al. Appraisal expression

recognition with syntactic path for sentence sentiment classification [J].

International Journal of Computer Processing of Oriental Languages.2011, 23 (1): 21-37.   
[14]宋艳雪，张绍武，林鸿飞．基于语境歧义词的句子情感倾向性分析[J]. 中文信息学报,2012,26 (3):38-44.(Song Yanxue,Zhang Shaowu, Lin Hongfei. Sentence sentiment analysis based on ambiguous words [J]. Journal of Chinese Information Processing,2012,26(3): 38-44.)   
[15] SocherR,Perelygin A,Wu JY,et al.Recursive deep models for semantic compositionality over a sentiment treebank [C]// Proc of Conference on Empirical Methods in Natural Language Processing. 2013.1631-1642.   
[16]路斌，万小军，杨建武，等．基于同义词词林的词汇褒贬计算[C]/第 七届中文信息处理国际会议论文集.2007:17-23.(Lu Bin,Wan Xiaojun, Yang Jianwu,et al. Using tongyici cilin to compute word semantic polarity [C]//Proc of the 7th International Conference on Chinese Computing.2007: 17-23.)   
[17]张磊，李梦诗，陈黎，等．基于双层 HHMM 的产品评论特征和情感分 类[J].四川大学学报：工程科学版,2013,45(2):94-102.(Zhang Lei,Li Mengshi, Chen Li,et al.Features and opinions classification of Chinese product reviews based on two level HHMMs [J]. Journal of Sichuan University Engineering: Science Edition,2013,45 (2): 94-102.)   
[18] Severyn A,Moschitti A.UNITN: training deep convolutional neural network for Twitter sentiment classification [C]// Proc of the 9th International Workshop on Semantic Evaluation.2015: 464-469.   
[19] Vo D,Zhang Yue.Target-dependent Twitter sentiment classification with rich automatic features [Cl/ Proc of International Joint Conference on Artificial Intelligence.Palo Alto,CA: AAAI Press,2015:1347-1353.   
[20] Nguyen T H, Shirai K.PhraseRNN: phrase recursive neural network for aspect-based sentiment analysis [C]// Proc of Conference on Empirical Methods in Natural Language Processing. 2015: 2509-2514.   
[21] Denil M,Demiraj A,Freitas N D.Extraction of salient sentences from labelled documents [EB/OL].[2018-04-25] https://arxiv.org/pdf/1412.6815.

[22]Li Jiwei,Luong M T,Jurafsky D.A hierarchical neural autoencoder for paragraphs and documents [C]// Proc of the 53rd Annual Meeting of the Association for Computational Linguistics.2015:1106-1115.

[23] Lee JY,Dernoncourt F. Sequential short-text classification with recurrent and convolutional neural networks [C]// Proc of Conference of the North American Chapter of the Association for Computational Linguistics [C]. Stroudsburg: Association for Computational Linguistics,2016,515-520.   
[24] Ruder S,Ghaffari P,Breslin JG.Ahierarchical model ofreviews for aspectbased sentiment analysis [C]//Proc of Conference on Empirical Methods in Natural Language Processing. 2016: 999-1005.   
[25] Hochreiter S,Schmidhuber J.Long short-term memory [J].Neural Computation,1997,9(8): 1735-1780.   
[26]数据集来源[EB/OL] (2016-06-29），[2018-04-25].http://spaces．ac. cn/archives/3863/   
[27] Choi H, Cho K,Bengio Y.Context-dependent word representation for neural machine translation [J]. Computer Speech & Language,2016.   
[28] Xiang Zhang,Yann LeCun,Text Understanding from Scratch [EB/OL], (2015)[2018-04-25]https://arxiv.org/abs/1502.01710   
[29] Chen Huimin，Sun Maosong,Tu Cunchao,et al. Neural sentiment classification with user and product attention [Cl//Proc of Conference on Empirical Methodsin Natural Language Processing. Stroudsburg: Association for Computational Linguistics,2016:1650-1659.   
[30] Tang Duyu,Qin Bing,Liu Ting.Learning semantic representations of users and products for document level sentiment classification C]// Proc of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing. 2015:1014-1023.   
[31] Ghosh S,Vinyals O,Strope B,et al. Contextual LSTM(CLSTM) models for Large scale NLP tasks [EB/OL].(2016) [2018-04-25].http://arxiv. org/abs/1602.06291.