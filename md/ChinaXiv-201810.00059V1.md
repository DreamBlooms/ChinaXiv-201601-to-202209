# 维吾尔文情感分类特征建设研究\*

热西旦木·吐尔洪太1,²，吾守尔·斯拉木1(1．新疆大学 信息科学与工程学院，乌鲁木齐 830046;2.伊犁师范学院 电子与信息工程学院，新疆 伊宁 835000)

摘要：由于目前缺乏维吾尔文情感分类特征表示方面的系统性研究，以传统n-gram特征为基础，按不同规模从维吾尔文情感标注语料库中提取了新特征及其组合特征，基于支持向量机（SVM）分类器对维吾尔文情感语料库进行了正负情感分类。实验结果表明，所提取的基本特征中unigram特征的分类效率最佳；unigram特征与词组特征的组合可以进一步提高分类效率，其最佳分类效果比unigram 特征的分类效果提高了 $1 . 7 8 \%$ 。首次在统一标注数据集上对不同特征的分类性能进行了综合评价，研究成果可以为今后的维吾尔文情感分类研究提供指导。

关键词：情感分类；特征建设；组合特征；维吾尔文 中图分类号：TP doi:10.3969/j.issn.1001-3695.2018.04.0378

# Research on feature construction of Uyghur text sentiment classification

Raxida Turhuntay1,², Wushour Slamu1 (1.Colegeof Information Science&Engineeing Xinjiang University,Urumqi83046,China;2.ColegeofElectronic& Information Engineering,Yili Normal University,Yili Xinjiang 835ooo,China)

Abstract: Due tothelackofsystematicresearchonthefeature expressionofUyghur textsentimentclasification,this paper uses the traditional n-gram features asthebasis to extract new features and combined features from Uyghur sentimentcorpora on different scales,classified the corpora as positive and negative with support vector machine(SVM)clasifier.Results indicatedthat,intheUyghurtextsentimentclassification,theunigramfeaturesinthebasicfeatureshavethebestclasification efciency.Thecombinationofunigram featuresand phrasefeaturescanfurther improve theclassification eficiency.The best performance of the combined features,the classification accuracy is $1 . 7 8 \%$ higher than that of unigram. This paper first to make acomprehensive evaluationoftheclasificationperformanceofdiferent featuresonaunifieddataset.Theresearchresults can be applied as a reference for future Uyghur sentiment classification research.

Keywords: sentiment classification; feature construction; combined features; Uyghur

# 0 引言

文本情感分类在本质上归属于文本分类问题[1。自康奈尔大学的Pang等人[2]将机器学习技术应用于文本情感分类之后，基于机器学习的情感分类技术已获得了广泛的关注和快速的发展。基于机器学习的分类方法经历了浅层学习（传统学习）[3.4]和深度学习[56]两次发展浪潮。

基于传统机器学习方法的情感分类研究已经取得了较为丰硕的成果，运用该方法的众多研究工作从特征工程（featureengineering)的范式出发，对情感分类中的特征表示进行了较为深入的研究。在此过程中研究者们较系统地研究了各种不同类型的特征，如unigram、bigram 等常用的词袋、语法、语义、否定以及组合特征等。

近年来，深度学习方法在文本情感分类研究领域也获得了日益广泛的运用。深度学习模型将从大量无标注语料中自动学习词向量，并将其作为基本特征，从而克服传统方法依靠人工设计特征的不足，能够降低人力和时间成本的消耗。但在将通过深度学习模型训练出的词向量作为情感分类过程的输入特征时，存在一个不容忽视的问题：根据词汇上下文构建词向量时，由于未考虑情感信息，可能发生基于上下文相似而情感极性相反的词汇训练出相似词向量的现象，可能降低情感分类的效率和质量。为解决该问题，研究者们将情感词向量与传统的人工设计特征相结合，以此改善深度学习模型的性能。

相比于汉文、英文等语言的情感分类研究，维吾尔文文本情感分类研究仍处于起步阶段。维吾尔文是形态丰富的黏着性语言，其形态结构远比中文和英文复杂。因此在对维吾尔文文本进行情感分类的过程中，不仅要考虑技术通用性问题，还需要考虑维吾尔文语言的自身特点。目前维吾尔文文本情感分类研究处于初探阶段，有关维吾尔文文本情感分类特征表示方面的研究尚缺乏系统性，因此维吾尔文文本情感分类的大部分研究工作需要从头做起。

本文从自建的维吾尔文情感标注语料库[7]中提取了unigram、bigram、trigram、情感词汇、词性特征、bi-tagged、generalized bi-tagged 等不同的基本特征，并通过 MI（mutualinformation,互信息）特征选择方法从中提取了最优特征，进而通过组合处理形成了unigram与 bigram 的组合特征、unigram与bi-tagged 的组合特征以及unigram与generalizedbi-tagged的组合特征。进而在本文情感标注数据集上，对不同特征在维吾尔文情感分类过程中的性能进行了评价与对比。

本文既提取了传统的n-gram 特征，也提取了体现词汇之间语义关系的多词特征，并初次较系统地在统一标注数据集上对不同特征的性能进行了评价。该工作不仅可以为后续维吾尔文文本情感分类研究工作提供指导，而且还可以为哈萨克语、柯尔克孜语等亲属语言的文本情感分类提供借鉴。

# 1 相关工作

基于传统机器学习的情感分类方法以人工标注的倾向性文本作为训练集，从中提取情感特征，而后基于机器学习的方法构造情感分类器，再通过训练好的分类器对新文档进行分类。该方法的分类效率很大程度上依赖于对情感特征的质量。国内外已有大量文献比较系统地研究了不同特征对情感倾向标注的影响。

Habernal等人[3]在自建的CzechSocialMedia情感语料库和电影、产品评论语料库上进行了情感倾向性分类实验，验证了几种预处理方法对情感分类效率的影响，并提取了n-gram、charactern-gram、词性、表情符号等几种基本特征以及在其基础上形成的组合特征，进而基于支持向量机（SVM）和最大熵（MaxEnt）机器学习分类器对数据集进行了情感分类。Rehab等人[4研究了词干提取，特征组合和n-gram模型等对分类结果的影响并运用SVM、朴素贝叶斯（NB）和K-近邻（KNN）等三种分类器在两种数据集上进行了情感分类实验，均获得了较好的分类结果。在汉文情感分类方面，李泽魁等人[8基于中文微博语料对词、词组、数值和句法特征进行了对比研究，并提出了基于词典规则的情感评分这一新特征，进而通过大量实验与分析，得出了可靠的特征组合。

随着深度学习方法在图像处理和语音识别等方面的成功应用，近期越来越多的研究者将该方法应用于情感分类任务中。国外Kim[5采用卷积神经网络（CNN）实现情感分析和问题分类，获得了较好的分类效果。国内梁军等人[利用递归自编码模型来主动学习任务的相关特征，避免了人工特征选择，经对比实验证明该模型能够提升情感分类准确率。部分研究者考虑到基于深度学习的词向量特征中情感信息的缺失，将传统人工设计特征与深度学习特征相结合以提高分类效率。孙超红[9将unigram、词性（POS）、情感词典等浅层特征与用Word2vec 训练得到的词向量特征进行融合，基于用LSTM改进的RNN 模型，对微博文本进行情感极性分类。徐莹莹[10]将词向量与传统人工特征相结合，构建了有监督排序模型预测情感强度，该工作在2016年SemEvel（国际标准语义评测）竞赛英文短语情感强度预测任务中获得了第一名的好成绩。

在维吾尔文文本情感分类方面，田生伟等人[1选取unigram、bigram、trigram 等特征，采用文档频率、卡芳检验、信息增益等特征选择方法，基于朴素贝叶斯、支持向量机、最大熵等分类算法进行了相关研究。热依莱木·帕尔哈提等人[12]基于自建的小规模语料库，提取了区分性单词并对语料进行了两类分类。阿不都萨拉木·达吾提等人[13]将从文献[12]中提取的区分性单词与情感词典相结合进行情感分类，获得更佳的分类效果。李敏等人[14]基于栈式自编码神经网络研究维吾尔文文本情感分类，得到了比传统机器学习算法更高的准确率，其中宏观准确率达到 $90 . 5 \%$ 。李冬白等人[15]通过word2vec得到语料库中每个单词的向量表示，再将词向量与词性特征线性结合，利用栈式自编码算法实现了从大规模无标注隐式情感文本中自动学习特征，并通过softmax分类器完成了维吾尔文文本中的隐式情感的自动分类。王树恒等人[16结合维吾尔语言特征及词汇间的情感特征，实现了基于wordembedding 和双向LSTM深度学习的维吾尔文情感分类模型，其实验结果好于RNN、CNN和SVM等分类器的分类结果。

# 2 本文实验数据集及其预处理

# 2.1维吾尔文评论语料库

该语料库7由采集自几个主要的维吾尔文网站的用户对不同主题的评论信息构成。由于评论中包含了丰富的情感信息，所以满足情感语料库所需数据的条件。语料库将每一条评论的情感倾向标注为正面、负面或中性。该语料库总共标注了15814条评论，其中10368条标注为正面、4515条标注为负面、931条标注为中性。语料库具体信息如表1所示。

表1评论语料库的三种倾向分布表  

<html><body><table><tr><td>网站名</td><td>中性</td><td>正面</td><td>负面</td></tr><tr><td>Alkuyi</td><td>315</td><td>878</td><td>657</td></tr><tr><td>TianShan</td><td>407</td><td>3 428</td><td>741</td></tr><tr><td>Putbal</td><td>209</td><td>6062</td><td>3 117</td></tr><tr><td>总共</td><td>931</td><td>10368</td><td>4515</td></tr></table></body></html>

由于本文情感分类研究的范围只限于正面和负面两种倾向，所以本文从标注语料中选择了4515条正面评论和4515条负面评论作为实验语料。

# 2.2 语料库的预处理

维吾尔文具有非常丰富的形态变化和庞大的词汇量，虽然维吾尔文中词干和词缀的数量有限，但是理论上可以组合而成无限多的词汇，其中，绝大多数词汇在语料库中仅仅出现一次

[17]。由此导致在维吾尔文自然语言处理工作中出现特征空间维数极多，以及随之而来的严重的数据相对稀疏问题。因此需要对实验数据进行一些预处理。

# 2.2.1维文词法分析器

维吾尔文词法分析器是由新疆大学多语种重点实验室研究开发的预处理工具，其实现了句子边界识别、词干提取、词性标注等多种标注。该工具用统计与规则相结合的方法识别句子[18]。词干提取工作中，将每个词被描述为一个树状结构，用根节点表示词干，孩子节点表示词缀，边表示词干与词缀之间的约束关系。在词干提取过程中充分考虑了维吾尔语在形态变化过程中发生的音变现象[19]。词性标注实现了如表2所示的15个一级标注规范[20]。

表2词性标注集  

<html><body><table><tr><td>序号</td><td>词性</td><td>标注符号</td><td>序号</td><td>词性</td><td>标注符号</td></tr><tr><td>1</td><td>名词</td><td>N</td><td>9</td><td>叹词</td><td>E</td></tr><tr><td>2</td><td>形容词</td><td>A</td><td>10</td><td>动词</td><td>V</td></tr><tr><td>3</td><td>数词</td><td>M</td><td>11</td><td>拉丁词</td><td>LW</td></tr><tr><td>4</td><td>量词</td><td>Q</td><td>12</td><td>语气词</td><td>T</td></tr><tr><td>5</td><td>副词</td><td>D</td><td>13</td><td>后位词</td><td>R</td></tr><tr><td>6</td><td>介词</td><td>P</td><td>14</td><td>词缀</td><td>X</td></tr><tr><td>7</td><td>模拟词</td><td>I</td><td></td><td>标点</td><td></td></tr><tr><td>8</td><td>练词</td><td>C</td><td>15</td><td>符号</td><td>Y</td></tr></table></body></html>

一条维吾尔文句子通过维文词法分析器进行处理后的结果如下：

[T=P][S=][T-V][S=U] $[ \mathrm { T } = \mathrm { M } ] [ \mathrm { S } = \mathrm { _ { y } } ]$ $[ \mathrm { T } = \mathrm { N } ] [ \mathrm { S } = \{ \cdots \} ]$ 儿 $[ \mathrm { T } = \mathrm { A } ] [ \mathrm { S } = \mathrm { } , \Theta ]$ （ $p o s 2 5$ $[ \mathrm { T } = \mathrm { N } ] [ \mathrm { S } = \mathsf { s o s } ] ^ { \downarrow }$ <EOS>

(他是一个小心眼的人)

其中：“ $\scriptstyle \Gamma = { }$ ”表示词性；“ $\mathrm { \sf S } =$ ”表示单词的词根； ${ < } \mathrm { E O S } { > }$ 是句子结束标记。

# 2.2.2预处理过程

1)分词标注为了得到单词特征，首先要对文本进行分词处理。维吾尔文是一种拼音文字，词语之间以空格和标点符号来分隔。因此分词对于维吾尔文而言不是一个技术问题，可利用空格和标点符号等对维吾尔文文本进行分词。

2)词干提取在维吾尔文中词干是表达词汇语义的主体部分，而形态后缀是表达语法信息和时态信息的部分[2I]。为了减少特征空间维数，避免维数灾难，需要对词汇进行词干提取。完成词干提取之后既能保留原词的基本语义，也能有效降低特征空间维数。例如，“ $\frac { \sin S _ { d _ { w } } , r } { \sin S _ { d _ { w } } }$ （学校）一词通过连接不同词缀可以形成拼写形式略有不同而主干意义相同的词汇。

<html><body><table><tr><td></td><td>在学校</td></tr><tr><td></td><td>从学校</td></tr><tr><td></td><td>学校的</td></tr><tr><td></td><td>去学校</td></tr><tr><td></td><td>把学校</td></tr></table></body></html>

本文通过维文词法分析器对本文语料进行了词干提取处理。

3）词性标注词性信息是发掘情感的重要线索。形容词、副词、动词和名词等可以携带重要的情感信息。本文所设计的实验提取了不同词性的词汇作为特征；同时由于本文提出的bi-tagged特征是根据文本中的词性前后组合规则来提取信息，所以运用维文词法分析器对本文语料进行了词性标注。

4)停用词去除维吾尔文情感文本中有一批出现频率较高，却无助于情感分类的词汇，如"man,u,bir,silar"等。如果将这些词汇作为文本特征，则会增加特征空间的维数，降低分类器的性能，因此有必要对这些词汇进行处理。本文通过自建的维吾尔文情感分类停用词表(包含1305个词)，去除了文本中不表达任何情感的停用词。

# 3 维吾尔文情感特征的选择

# 3.1基本特征

1） $\mathfrak { n }$ -gram 特征从句子中分别提取unigram、bigramtrigram 等特征，分别以 $F _ { u n i }$ 、 $F _ { b i }$ 、 $F _ { t r i }$ 表示。

2)情感词汇特征情感词通常蕴涵着丰富的感情色彩，往往能透露文本所表达的态度和情绪，因此可以将其作为一种重要的特征。本文将作者自建的维吾尔文情感词典[22]中的所有褒义和贬义词作为基本情感特征，并以 $F _ { d i c t }$ 表示。

3)词性特征词性信息一直被认为是衡量情感表达的一个重要指标。因此，本文选择名词、动词、形容词、副词和叹词等词性作为基本情感特征，以 $F _ { p o s }$ 表示。

4）bi-tagged特征通常传统的基于 $\mathbf { n }$ gram（ $\mathbf { n } \geq 2$ ）的特征提取方法会产生高维数的特征向量，高维数不但增大分类难度，而且会延长分类时间。本文受到文献[23]的方法启发，总结了若干词性组合规则，从文本中提取了符合规则的、具有相邻关系和先后顺序的两个单词所构成的短语，并将其命名为bi-tagged 特征，以 $F _ { b i - t a g }$ 表示。bi-tagged特征词性组合规律如表3所示。

表3bi-tagged特征词性组合规则  

<html><body><table><tr><td>序号</td><td>当前词性</td><td>下个词性</td><td>例子</td></tr><tr><td>1</td><td>N</td><td>A</td><td>Kungli parakende心烦意乱</td></tr><tr><td>2</td><td>N</td><td>V</td><td>Erwahi ochmaq 魂飞胆裂</td></tr><tr><td>3</td><td>A</td><td>V</td><td>Achiq yotmaq 忍气吞声</td></tr><tr><td>4</td><td>A</td><td>N</td><td>Xata qedem 错误的一步</td></tr><tr><td>5</td><td>A</td><td>A</td><td>Mihriban ongluq 善良懂事</td></tr><tr><td>6</td><td>D</td><td>A</td><td>Bek chirayliq 很漂亮</td></tr><tr><td>7</td><td>D</td><td>V</td><td>Ejep yarishipto 太好看了</td></tr><tr><td>8</td><td>E</td><td>E</td><td>Way ésit 真可惜</td></tr></table></body></html>

5）Generalized bi-tagged 特征虽然 bigram、trigram、bi-tagged等特征能提取上下文语义信息，但却存在特征过于稀疏、

泛化能力较弱以及特征维数高等不足。例如，训练语料中有这样两条语句：

$\textcircled{1}$ Bügin shundaq tesirlik kénodin birni kurdim, silerningmu kurüpbéqishinglarni tewsiyeqiliman．（我今天看了一部非常感 人的电影，也推荐给你们看。) $\textcircled{2}$ Silerge bir tesirlik kitap tonoshtoray.（给你们介绍一本 感人的书。)

从训练语料中可以得到“tesirlikkeno,shundaq tesirlik,tesirlikkitap”（感人的书、感人的电影、非常感人）等bigram和bi-tagged特征序列。虽然这些特征很好地表达了情感，但如果“tesirlikhekaye"（感人的故事）这个特征在测试语料中出现，上述训练语料上训练的分类器无法确定其情感倾向。针对该问题，本文参照文献[24,25]的思路，将本文提取的bi-tagged特征前后两个词汇中的一个替换为其所对应的词性标注符号，并命名为generalized bi-tagged 特征，用 $F _ { G b i - t a g }$ 表示。上述例子中，如果将“tesirlikkeno,tesirlikhekaye,tesirlikkitap”等特征中的后词都替换成对应词性符号，将会得到"tesirlik $\mathbf { N } ^ { \prime \prime } ($ （感人的N）特征，达到不同特征的泛化效果，从而有效保证训练语料中大部分特征的泛化性能。本文对bi-tagged特征分别进行了前置词替换（ $F _ { G b i - t a g \_ h }$ ，对前后两个词中的第一个词汇进行词性符号替换)和后置词替换（ $F _ { G b i - t a g \_ t }$ ，对前后两个词中的第二个词汇进行词性符号替换）的方法，通过对比实验确定了最佳的替换方式。

# 3.2组合特征

虽然unigram 特征在情感分类任务中的分类效果总是优于其他特征，但是unigram 特征的劣势在于不能提取文本中的上下文信息。虽然 bigram、trigram、bi-tagged 等词组特征能提高语义含量，但却降低了特征向量的统计质量，使特征变得更加稀疏，导致机器学习算法难以从中提取可用于分类的统计特性。由于该缺点，采用这些特征获得的情感分类效果逊于采用unigram 特征的效果[3]。针对该问题，本文对 $F _ { u n i }$ 和 $F _ { b i }$ 特征、$F _ { u n i }$ 和 $F _ { b i - t a g }$ 特征、 $F _ { u n i }$ 和 $F _ { G b i - t a g - t }$ 特征进行组合，分别形成了Fni-bi、 $\Gamma _ { u n i - b i - t a g } \mathcal { \bar { H } } \mathbb { H } \mathbf { \mathcal { F } } _ { u n i - G b i - t a g }$ 组合特征。

本文对特征进行组合时，设计了一个组合比例控制参数α， $\mathbf { q } = [ 0 . 1 , \emptyset . 2 , \emptyset . 3 , \emptyset . 4 , . . . , \emptyset . 9 ]$ ，即按照不同的组合比例对两种特征进行组合，从而确定每一种特征在组合特征中的重要程度。其中 $\mathfrak { a }$ 是指与unigram 特征进行组合的词组特征在组合特征总体中所占的比例。以组合特征 $\mathrm { F } _ { u n i - b i - t a g }$ 为例，当组合特征总数为N 时，bi-tagged 特征数 $\mathrm { N _ { b i - t a g } = N ^ { * } a }$ ，unigram 特征数 ${ \mathrm { N } } _ { \mathrm { u n i } } { = } { \mathrm { N } } { \mathrm { - } }$ $\mathrm { N _ { b i - t a g } }$ ，即用 $\mathrm { \Delta N _ { u n i } }$ 个unigram 特征和 $\mathrm { N _ { b i - t a g } }$ 个bi-tagged特征进行组合。

# 4 实验与结果分析

本文从维吾尔文情感语料库中提取不同类型的特征之后，利用MI特征选择方法对其进行筛选，利用tf-idf特征权重方法判断其区分能力的强弱，随后运用SVM机器学习分类器在维吾尔文评论情感语料库上完成正负二元情感分类。实验采用10倍交叉验证法，即把数据集分成10个子集，在每一轮实验中将其中一个子集作为测试集，其余9个子集作为训练集，共执行10 轮。之后将所得到的结果取平均值作为最终结果。所有实验均用Python 语言和Scikit-learn工具包来完成，实验结果用准确率（Accuracy）来评价。

# 4.1基本特征上的分类结果

为了验证本文提取的特征在维吾尔文情感分类过程中的性能，实验从语料集中提取不同特征，并利用MI特征选择方法对特征进行排序，从中依次选择排在前 $10 \%$ 到 $90 \%$ 的特征并对不同规模特征对分类器性能的影响进行比较。实验结果描述如表4所示。

表4基本特征上的分类结果  

<html><body><table><tr><td>特征数</td><td>Fmi</td><td>Fbi</td><td>F</td><td>Faiet</td><td>E</td><td>Fbi-1ag</td><td>FGbi-tag -h</td><td>FGbi-tag -1</td></tr><tr><td>10%</td><td>87.44</td><td>79.17</td><td>60.16</td><td>81.49</td><td>82.86</td><td>74.77</td><td>74.24</td><td>77.64</td></tr><tr><td>20%</td><td>89.30</td><td>78.65</td><td>63.89</td><td>82.97</td><td>84.72</td><td>76.41</td><td>76.61</td><td>79.13</td></tr><tr><td>30%</td><td>89.47</td><td>78.69</td><td>61.60</td><td>83.36</td><td>85.28</td><td>82.16</td><td>78.68</td><td>81.85</td></tr><tr><td>40%</td><td>89.40</td><td>78.66</td><td>59.59</td><td>84.05</td><td>85.29</td><td>79.31</td><td>81.29</td><td>82.96</td></tr><tr><td>50%</td><td>89.40</td><td>78.34</td><td>58.24</td><td>84.25</td><td>85.78</td><td>81.96</td><td>78.00</td><td>84.66</td></tr><tr><td>60%</td><td>89.26</td><td>78.14</td><td>57.66</td><td>84.17</td><td>85.26</td><td>83.99</td><td>76.91</td><td>85.23</td></tr><tr><td>70%</td><td>89.28</td><td>77.58</td><td>54.68</td><td>84.30</td><td>85.15</td><td>79.97</td><td>76.98</td><td>82.33</td></tr><tr><td>80%</td><td>89.31</td><td>74.87</td><td>57.26</td><td>84.39</td><td>85.13</td><td>77.75</td><td>77.25</td><td>81.85</td></tr><tr><td>90%</td><td>88.82</td><td>72.01</td><td>56.01</td><td>84.65</td><td>85.06</td><td>77.07</td><td>78.87</td><td>82.12</td></tr></table></body></html>

由表4可知，所有基本特征中 $F _ { u n i }$ 特征的分类效果最佳。提取前 $30 \%$ （3324个特征）的特征时，分类器的分类准确率达到了最高值89.47，但是随着特征数的增加，其准确率从峰值下降。本文实验中， $F _ { d i c t }$ 、 $F _ { p o s }$ 等特征也取得了较理想的结果。例如，从 $F _ { d i c t }$ 中提取 $90 \%$ （2316个特征）的特征时，分类器的分类准确率达到了86.50；从 $F _ { p o s }$ 中提取 $50 \%$ （5 269个特征）的特征时，分类器的分类准确率达到了85.78。

基本特征中， $F _ { b i }$ 和 $F _ { t r i }$ 特征对分类结果的影响低于预期。在词组特征中，本文所提出的 bi-tagged 特征与 bigram 特征相比分类效果更佳，其最高分类准确率为83.99，比bigram 的最高分类准确率79.17高出了 $4 . 8 2 \%$ 。对bi-tagged 特征进行泛化后，其分类效果可以进一步增强，两种generalizedbi-tagged 特征中 $F _ { G b i - t a g - t }$ 的分类效率优于 $F _ { G b i - t a g - h }$ 。例如，从 $F _ { G b i - t a g - t }$ 中提取前 $60 \%$ 的特征时，分类准确率达到85.23，比基于同样数目的$F _ { b i - t a g }$ 特征的分类效率提高了 $1 . 2 4 \%$ 。

# 4.2组合特征上的分类结果

为了验证提取的组合特征在维吾尔文情感分类过程中的性能，本文分别运用三种组合特征（ $F _ { u n i - b i } \times F _ { u n i - b i - t a g } \times F _ { u n i - G b i - t a g } \ )$ 在维吾尔文评论情感语料库上进行了情感分类。考虑到（20 $F _ { G b i - t a g - t }$ 的分类效果优于 $F _ { G b i - t a g - h }$ ，对 $F _ { u n i }$ 和 $F _ { G b i - t a g - t }$ 特征进行组合形成组合特征 $F _ { u n i - G b i - t a g }$ 。实验过程中，将特征总数从1000逐步增加到10000，每次增加 $\mathrm { ~ 1 ~ } 0 0 0$ 个特征；将特征数比例控制参数 $\mathbf {  { a } }$ 从 $10 \%$ 逐步增加到 $90 \%$ 。三种组合特征在语料库上分类准确率如表5\~7所示。限于篇幅，本文仅呈现特征数比例控制参数 $\mathbf {  { a } }$ 在相间节点上的结果。

表5组合特征 $F _ { u n i - b i }$ 上的分类结果  

<html><body><table><tr><td>α</td><td>1000</td><td>2000</td><td>3000</td><td>4000</td><td>5000</td><td>6000</td><td>7000</td><td>8000</td><td>9000</td><td>10000</td></tr><tr><td>0.1</td><td>86.47</td><td>88.81</td><td>89.24</td><td>89.28</td><td>89.34</td><td>89.26</td><td>89.73</td><td>89.99</td><td>89.40</td><td>88.72</td></tr><tr><td>0.3</td><td>86.31</td><td>88.68</td><td>89.43</td><td>89.60</td><td>89.35</td><td>89.54</td><td>89.92</td><td>89.59</td><td>89.11</td><td>89.13</td></tr><tr><td>0.5</td><td>85.66</td><td>87.89</td><td>89.06</td><td>89.28</td><td>89.48</td><td>89.71</td><td>89.98</td><td>90.72</td><td>90.35</td><td>90.47</td></tr><tr><td>0.7</td><td>83.82</td><td>87.03</td><td>87.98</td><td>88.69</td><td>89.37</td><td>89.72</td><td>90.67</td><td>89.85</td><td>90.21</td><td>89.75</td></tr><tr><td>0.9</td><td>79.59</td><td>82.31</td><td>85.36</td><td>86.86</td><td>87.89</td><td>88.39</td><td>88.49</td><td>88.69</td><td>88.17</td><td>88.83</td></tr></table></body></html>

表6组合特征 $F _ { u n i - b i - t a g }$ 上的分类结果  

<html><body><table><tr><td>α</td><td>1000</td><td>2000</td><td>3000</td><td>4000</td><td>5000</td><td>6000</td><td>7000</td><td>8000</td><td>9000</td><td>10000</td></tr><tr><td>0.1</td><td>87.11</td><td>89.32</td><td>90.00</td><td>89.51</td><td>89.67</td><td>89.71</td><td>89.75</td><td>89.79</td><td>89.81</td><td>89.75</td></tr><tr><td>0.3</td><td>86.42</td><td>88.26</td><td>89.70</td><td>89.99</td><td>90.15</td><td>90.05</td><td>90.20</td><td>90.29</td><td>90.15</td><td>89.98</td></tr><tr><td>0.5</td><td>85.99</td><td>88.19</td><td>89.14</td><td>90.13</td><td>90.97</td><td>90.18</td><td>89.98</td><td>90.02</td><td>90.02</td><td>90.00</td></tr><tr><td>0.7</td><td>84.29</td><td>87.21</td><td>88.59</td><td>88.82</td><td>89.45</td><td>89.79</td><td>90.05</td><td>90.17</td><td>90.36</td><td>90.20</td></tr><tr><td>0.9</td><td>80.16</td><td>83.88</td><td>85.95</td><td>86.70</td><td>87.26</td><td>87.71</td><td>88.01</td><td>87.98</td><td>88.30</td><td>88.51</td></tr></table></body></html>

表7组合特征 $F _ { u n i - G b i - t a g }$ 上的分类结果  

<html><body><table><tr><td>α</td><td>1000</td><td>2000</td><td>3000</td><td>4000</td><td>5000</td><td>6000</td><td>7000</td><td>8000</td><td>9000</td><td>10000</td></tr><tr><td>0.1</td><td>88.94</td><td>89.14</td><td>89.48</td><td>89.43</td><td>89.33</td><td>89.44</td><td>89.13</td><td>90.18</td><td>90.12</td><td>90.17</td></tr><tr><td>0.3</td><td>86.94</td><td>88.96</td><td>89.42</td><td>89.56</td><td>89.67</td><td>89.76</td><td>90.64</td><td>90.75</td><td>90.93</td><td>89.75</td></tr><tr><td>0.5</td><td>85.10</td><td>88.60</td><td>89.29</td><td>89.46</td><td>89.64</td><td>89.83</td><td>90.28</td><td>91.25</td><td>90.31</td><td>89.84</td></tr><tr><td>0.7</td><td>84.48</td><td>87.22</td><td>88.97</td><td>89.37</td><td>89.36</td><td>89.44</td><td>89.92</td><td>90.48</td><td>90.63</td><td>90.01</td></tr><tr><td>0.9</td><td>82.73</td><td>85.93</td><td>87.05</td><td>87.59</td><td>87.76</td><td>87.92</td><td>88.55</td><td>89.01</td><td>88.14</td><td>87.95</td></tr></table></body></html>

在基于组合特征 $F _ { u n i - b i }$ 的分类实验中（表5)，当特征总数为8000， $F _ { b i }$ 特征占总特征的 $50 \%$ 时，分类器获得最高分类准确率90.72，比 $F _ { u n i }$ 的最高分类准确率提高了 $1 . 2 5 \%$

在基于组合特征 $F _ { u n i - b i - t a g }$ 的分类实验中（表6)，当特征总数为 $5 0 0 0$ ， $F _ { b i - t a g }$ 特征占总特征的 $50 \%$ 时，分类器获得最高分类准确率90.97，比 $F _ { u n i }$ 的最高分类准确率提高了 $1 . 2 3 \%$ ，比$F _ { u n i - b i }$ 的最高分类准确率提高了 $0 . 2 5 \%$

在基于组合特征 $F _ { u n i - G b i - t a g }$ 的分类实验中（表7)，当特征总数为 $8 0 0 0$ ， $F _ { G b i - t a g - t }$ 特征占总特征的 $50 \%$ 时，分类器获得最高分类准确率91.25，比 $F _ { u n i }$ 、 $F _ { u n i - b i }$ 和 $F _ { u n i - G b i - t a g }$ 特征分别提高了$1 . 7 8 \%$ ， $0 . 5 3 \%$ 和 $0 . 2 8 \%$ 。

实验结果表明，对unigram特征与包含上下文语义信息的词组特征进行组合可以有效地客服这些特征各自存在的不足，并可获得比单独使用其中某个特征更佳的分类结果。在基于组合特征的分类实验中，unigram同与其组合的词组特征在总特征中各占一半时，分类效果最佳。因为当unigram 特征呈现数据稀疏时，词组特征能够提取一些情感丰富的上下文信息，对unigram 特征起到补充作用。本文分类实验中 $F _ { u n i - b i - t a g }$ 组合特征的分类效果优于 $F _ { u n i - b i }$ 组合特征的分类效果。主要原因是 bi-tagged特征可以删除bigram特征中的诸多噪声特征，并能提取结构稳定、语义完整的上下文信息。三种组合特征中， $F _ { u n i }$ -Gbiaig组合特征的分类效率优于前两种组合特征，主要原因是对bi-tagged特征进行泛化能进一步提高bi-tagged特征的统计特性，可以有效解决其存在的数据稀疏问题，所以 $F _ { u n i - G b i - t a g }$ 特征的分类效果更佳。

# 5 结束语

针对目前维吾尔文文本情感分类特征表示相关研究缺乏系统性的问题，本文以传统n-gram特征为基础，按不同规模从自建的维吾尔文情感语料库中提取了八种基本特征和三种组合特征（既包含了传统的BOW特征，又包含了兼顾上下文信息的语义特征）进行实验。实验证明，在基于基本特征的维吾尔文文本情感分类任务中，unigram特征的分类效果最佳，若对unigram 特征与考虑上下文语义信息的词组特征进行组合，能够进一步增强分类效果。本文所涉及的三种组合特征中，unigram与generalizedbi-tagged的组合特征分类效果最佳，比unigram特征的分类效率提高了 $1 . 7 8 \%$ 。

本文所涉及的词组特征是基于词性搭配规则提取具有先后顺序和相邻关系的两个词所组成的特征，目前尚无法以包含两个以上单词的语句为单元进行情感分类。今后的工作将着重研究如何通过拓展词组特征长度及利用长距离词汇之间的依赖关系提高情感分类效率。将本文所提取的特征与深度学习模型的词向量特征进行融合，将其作为深度学习模型的输入特征去评价其在基于深度学习模型的情感分类任务中的性能。

# 参考文献：

[1]Liu Bing.Sentiment analysis and opinion mining [C]// Proc of Synthesis Lectures on Human Language Technologies.[S.1.] $\because$ Morgan& Claypool, 2012:152-153.   
[2]Pang Bo,Lee L,Vaithyanathan S.Thumbs up?: sentiment classification using machine learning techniques [Cl// Proc of Acl-02 Conference on Empirical Methods in Natural Language Processing. Association for Computational Linguistics.20o2:79-86.   
[3]Habernal I, Steinberger J. Supervised sentiment analysis in czech social media [M].[S.1.] : Pergamon Press,Inc,2014.   
[4]Duwairi Rehab,EI-Orfali M.A study of the effects of preprocessing strategies on sentiment analysis for arabic text [J]. Journal of Information Science,2014,40 (4): 501-513.   
[5]Kim Y.Convolutional neural networks for sentence classification [J].arXiv: 1408.5882v2,2014.   
[6]梁军，柴玉梅，原慧斌，等．基于深度学习的微博情感分析[J]．中文 信息学报,2014,28(5):155-161.(Liang Jun,Chai Yumei,Yuan Huibin,et al.Deep learning for Chinese micro-blog sentiment analysis [J]. Journal of Chinese Information Processing,2014,28(5):155-161.)   
[7] 伊尔夏提·吐尔贡，吾守尔·斯拉木，热西旦木·吐尔洪太，等.维吾尔 文情感语料库的构建与分析[J].计算机与现代化,2017(4):67-72. (Yierxiati Tuergong,Wushouer Silamu,Rexidan Tuerhongtai,etal. Construction and analysis of Uyghur emotional corpus [J]. Jisuanji Yu

Xiandaihua,2017(4):67-72.)

[8]李泽魁，赵妍妍，秦兵，等．中文微博情感倾向性分析特征工程[J].山西大学学报：自然科学版,2014,37(4):570-579.

[9] (Li Zekui, Zhao Yanyan,Qin Bing,et al.Feature engineering for Chinese microblog sentiment classification [J]. Journal of Shanxi University: Natural Science Edition,2014,37(4): 570-579.)

[10]孙超洪．基于递归神经网络的微博情感分类研究[D].杭州：浙江理工 大学，2017．(Sun Chaohong.Research on micro-blog sentiment classification based on recurrent neural network [D].Hangzhou: Master’ s Thesis of Zhejiang Sci-Tech University,2017.)

[11]徐莹莹．基于深度神经网络模型的句子级文本情感分类研究[D].深 圳：深圳大学,20l6.(Xu Yingying.Research of sentence-level sentiment classification for text based on deep neural network [D]. Shenzhen: Master' s Thesis of Shenzhen University,2016.)

[12]田生伟，禹龙，王宇光．维吾尔语情感分类算法[J].计算机工程与应 用，2011,47 (36):147-150.(Tian Shengwei,Yu Long,Wang Yuguang. Research on sentiment classification of Uighur reviews [J].Computer Engineering and Applications,2011,47(36): 147-150.)

[13]热依莱木·帕尔哈提，孟祥涛，艾斯卡尔·艾木都拉．基于区分性关键 词模型的维吾尔文本情感分类[J].计算机工程,2014,40(10):132-136. (Rayila Parhat,Meng Xiangtao,Askar Hamdulla.Uyghur text sentiment classification based on discriminative keyword model [J]. Computer Engineering,2014,40 (10):132-136.)

[14]阿不都萨拉木·达吾提，于斯音·于苏普，艾斯卡尔·艾木都拉．类别 区分词与情感词典相结合的维吾尔文句子情感分类[J].清华大学学报： 自然科学版,2017,57(2):197-201.(Abdusalam Dawut,Hussein Yusuf, Askar Hamdulla.Emotion recognition from Uyghur sentences based on combinations of class discrimination words and a sentiment dictionary [J]. Journal of Tsinghua University:Natural Science Edition,2017,57(2):197- 201.)

[15]李敏，禹龙，田生伟，等．基于深度学习的维吾尔语语句情感倾向分析 [J].计算机工程与设计,2016,37(8):2213-2217.(LiMin,Yu Long,Tian Shengwei, et al. Emotional tendency analysis ofUyghur statement based on deep learning [J]. Computer Engineering and Design,2016,37(8): 2213- 2217. )

[16]李冬白，田生伟，禹龙，等．深度学习的维吾尔语语句隐式情感分类 [J]．计算机工程与设计，2016,37(9):2577-2580.(LiDongbai,Tian Shengwei, Yu Long,et al. Deep learning for implicit sentiment classification of Uyghur sentence [J]. Computer Engineering and Design,2016,37(9):

# 2577-2580.)

[17]王树恒，吐尔根·依布拉音，卡哈尔江·阿比的热西提，等．基于 BLSTM的维吾尔语文本情感分析[J].计算机工程与设计，2017,38 (10): 2879-2886.(Wang Shuheng,Turgun Ibrahim,Kahaerjiang Aviderexiti, et al.Sentiment classification of Uyghur text based on BLSTM [J]. Computer Engineering and Design,2017,38 (10): 2879-2886.)

[18]Abdukelimu H,Liu Yang,Chen Xinxiong,et al. Learning distributed representations of Uyghur words and morphems [M].Cham: Springer International Publishing,2015:202-211.

[19]艾山·吾买尔，吐尔根·依步拉音.统计与规则相结合的维吾尔语句子 边界识别[J]．计算机工程与应用，2010,46(14):162-165.(Aishan Wumaier, Tuergen Yibulayin.Sentence boundary detection ofUyghur based on rules and statistics [J].Computer Engineering and Applications,2010,46 (14): 162-165.)

[20]麦热哈巴·艾力，姜文斌，王志洋，等．维吾尔语词法分析的有向图模 型[J]．软件学报,2012,23(12):94-100.(MaierhabaAili,JiangWenbin Wang Zhiyang,et al.Directed graph model of Uyghur morphological analysis [J]. Journal of Software,2012,23(12): 94-100.)

[21]Maimaiti M,WumaierA,AbiderexitiK,et al.Bidirectional long short-term memory network with a conditional random field layer for Uyghur part-ofspeech tagging[J]. Information,2017,8 (4): 157.

[22]力提甫·托乎提．现代维吾尔语参考语法[M].北京：中国社会科学出版社，2O12.(Litip Tohti. The reference grammar of modern Uyghurlanguage [M].Beijing: China Social Sciences Press,2012.)

[23]热西旦木·吐尔洪太，吾守尔·斯拉木，伊尔夏提·吐尔贡.词典与机 器学习方法相结合的维吾尔语文本情感分析[J]．中文信息学报.2017, 31(1):177-183.(Rexidanmu Tuerhongtai,Wushour Silamu,Yierxiati Tuergong. Uyghur text sentiment analysis by combining lexical knowledge with machine learning methods [J].Journal of Chinese Information Processing,2017,31(1): 177-183.)

[24] Turney PD.Thumbs up or thumbs down?: semantic orientation applied to unsupervised classification of reviews [C]// Proc of Annual Meeting of the Association for Computational Linguistics.20o2:417-424.

[25] Gamon M. Sentiment classification on customer feedback data: noisy data, large feature vectors,and the role of linguistic analysis [C]//Proc of International Conference on Computational Linguistics.2oo4: 841-847.

[26] Joshi M,Penstein-Rosé C.Generalizing dependency features for opinion mining [C]//Proc of the ACL-IJCNLP 2009 Conference Short Papers.2009: 313.