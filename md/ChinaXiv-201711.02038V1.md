# 基于Word2Vec及大众健康信息源的疾病关联探测

罗文馨陈 邓思艺(北京师范大学政府管理学院北京 100875)

摘要：【目的】利用Word2Vec深度学习技术从面向大众的健康信息中寻找疾病关联，解决非医学人士通常不了解多种疾病之间存在的关联，从而影响到健康信息搜寻中的全面性和有效性的问题。【方法】由专家选取 30 个常见疾病主题，从高质量医学新闻网站上采集对应疾病的文档，运用Word2Vec技术对各疾病的相关文档构造词向量，计算向量距离判断疾病关联。通过与专家评分的相关分析衡量判断结果的准确性。【结果】最优情况下，Word2Vec 得到的结果与专家评分相关系数达到0.635。通过对比不同的算法模型、优化方法、数据规模及重要参数对结果的影响，发现 Skip-Gram模型结合负样本数为20的 Negative Sampling优化方法在大规模数据集上的实验结果最优。【局限】疾病主题选取宽泛时，影响Word2Vec判断准确性，本文的疾病主题选取粒度有待改善。

【结论】利用Word2Vec技术在面向大众的健康信息源中也可以探测疾病关联，其有效性表明该技术可用于改善大众的健康信息搜寻的个性化服务。

关键词：Word2Vec 疾病关联非专业医学文本 健康信息个性化分类号:TP391G350

# 1引言

以往，普通大众多从专业医学人士处获取疾病健康知识。互联网的发展可以让大众更加主动地去上网搜寻自己所需的健康信息。近年来，各种新型健康服务平台不断兴起，这些服务多以疾病知识科普、在线咨询为主，极大丰富了人们获取医学信息的渠道。然而，大众由于缺乏专门的医学知识，并不了解疾病之间复杂的关联，例如牙周疾病可能由糖尿病引起。对这种关联缺乏了解会影响到大众管理自身健康、搜寻全面有效的医学信息。如果能通过技术手段寻找疾病主题之间的关联，可用于改善健康信息的个性化服务，提高信息服务平台的内容组织和导航质量。由于专业医学文献使用的术语不易被大众理解，本文使用非专业医学信息，如高质量的健康新闻，通过Word2Vec深度学习技术，基于疾病相关文档探测疾病主题之间的关联，并与专家评判结果对比，发现这种技术能有效地用于疾病之间的关联探测。

# 2相关工作

面向普通大众的健康信息服务早就引起关注[]Eysenbach明确提出了结合信息技术手段为消费者提供健康信息服务，包括分析消费者的健康信息需求，研究并实现能为消费者提供信息的方法，依据消费者的偏好设计模型构建信息系统等[2]。国内称这一研究范畴为“用户健康信息学”。目前面向消费者的健康服务不断涌现，提供疾病知识科普、定制的信息推送或疾病问题在线咨询等，推动人们管理自身健康，提高

大众健康信息素养。

为帮助人们更高效准确地获取健康信息，研究人员开展了很多工作，主要分为几个方面：

(1）调查消费者的信息查寻行为3，弄清他们在互联网上查找医学健康信息时最关心什么类型的内容;

(2）帮助人们理解医学术语，解决由于"词汇之间的鸿沟"带来的难以理解信息或者理解有偏差的问题[4]，例如研制用户健康词表(CHV)[5]、预测用户对健康术语的熟悉度[];

(3）建立从医学专业领域概念到普通认知范畴的映射[7，处理用户健康词汇与UMLS词表匹配的问题[8]。

然而，由于疾病之间存在着复杂的关联，未经专业医学训练的普通大众很难了解疾病之间的关联。这影响他们在信息搜寻的时候获取全面的相关信息。目前这方面的研究还比较欠缺。

传统上疾病关联探测是临床医学研究或生物医学实验的任务。现有的利用文本挖掘探测疾病关联的研究主要以专业医学文献为研究对象。比如有学者采用语义扩展模型和神经网络聚类方法，将疾病类型与致病基因关联起来[9-11]。这些研究结论多为分子生物学、基因、化学成分等层面的解释，缺乏专业知识的普通大众是很难理解的。

面向大众的医学健康信息源包括健康门户网站、医学新闻网站、在线健康社区、公共健康知识库等。对在线健康社区MedHelp的用户发帖的研究，发现药物与其不良反应的关系，有助于药品安全监管者有效地识别早期药品不良反应信号[12]。对特定疾病社区中的用户帖子进行文本聚类分析，分析三类疾病之间的联系与差异[13]。这些研究说明利用大众健康信息源可以找到一些对用户很有参考意义的联系。但在线健康社区的信息内容质量不佳，为了保证研究结论的可靠性，本文选择高质量的医学新闻。此外，还有利用社会网络分析法来探究健康主题之间关系的研究，如刘红霞等[14]对 WHO 网站的健康信息主题进行分析，采用文本相似性算法，挖掘它们之间的链接关系和语义关系，用社会网络的方式来呈现。但该方法过于依赖特定网站的链接结构，所能找到的关联比较受限；研究中采用文本相似性算法，也没有充分反映其语义层面的关系。

据笔者调研所知，利用大众健康信息挖掘不同疾病或主题间关系的研究有很值得深入的空间。本文将疾病关联的发现任务转换为探测疾病相关文档的语义关联，利用Word2Vec(Wordto Vector)技术找到与特定疾病关系密切的词汇，利用这一桥梁发现疾病关联。

2003年，Bengio等提出神经网络语言模型(NeuralNetworkLanguageModel,NNLM)，利用神经网络结构对自然语言建模的同时，得到了词向量[15]。2013 年,Mikolov 等简化NNLM模型，提出 CBOW(ContinuousBag-Of-Words)模型和 Skip-Gram 模型[16]，旨在更高效地实现词语的向量表示。同年，Google公司推出这两个模型的C语言实现版本，称之为Word2Vec；目前Python库中gensim包也集成了该算法。Word2Vec 是基于深度学习思想[17]，通过训练文本数据集，将词语不同的语法和句法特征映射到向量的不同维度上去,将单个词语表示为高维向量空间中的某个点。它用于实现词语的向量表示时主要有CBOW和Skip-Gram两种模型。两者的区别在于,CBOW模型是已知上下文,预测中心词；而Skip-Gram 模型则是已知当前词，预测其上下文。相关研究证明，该技术应用在词语相似度计算[18]、机器翻译、特征抽取[19-20]、情感分类[21]等领域效果较好。Word2Vec技术具有通用性并且使用方法相对较简单。

# 3疾病关联探测

不同于以往从生物实验和临床角度寻找疾病关联，本文将探测疾病关联的任务转换为从疾病相关文档中发现语义关联。具体采用Word2Vec技术，利用医学健康新闻寻找疾病关联，旨在探讨一种通用的方法找到疾病主题之间的关联关系，改进人们搜寻健康信息的效率和效果。本文主要围绕以下两个问题：

(1)如何利用Word2Vec寻找疾病之间的关联关系?(2)如何评估Word2Vec应用在疾病关联探测上的效果?

在特定疾病的相关文档集合上，用Word2Vec技术找到揭示不同疾病主题的词汇向量，借助其相似度确定疾病主题的关联；通过统计分析方法将结果与专家评分结果进行对比，结合参数调优实验确定可令结果最优的参数配置。

# 3.1 数据采集

不同于以往在专业医学文献中挖掘疾病关联的研究，本文选用普通人能理解的健康信息，原因是专业医学文档的术语难以为大众所理解，即使找到了关联，也难以直接应用于普通大众经常浏览的信息源。

数据来自于MedicalNewsToday网站。该网站新闻由具有医学背景的专业人员撰写，并由网站人工添加类别标签。内容质量较高且易于被普通人理解。其类别标签按大众关心的健康问题分为144个类，每个类都有对应的新闻文档。

本研究采用其中30种有代表性的疾病类别，Addiction（成瘾)、Allergy(过敏)、Alternative Medicine(补充和代替医疗)、Anxiety(焦虑)、Arthritis(关节炎）Asthma(哮喘)、BreastCancer(乳腺癌)、Cardiovascular(心血管)、Cholesterol(胆固醇)、COPD(慢性阻塞性肺疾病)、Dentistry(牙科)Depression (抑郁)、Diabetes(糖尿病)、Eating Disorders（饮食失调)、Flu（流感）、Headache(头痛)、HeartDisease(心脏病)、HIV（艾滋病)、Hypertension(高血压)、Men's Health(男性健康)、MentalHealth（心理健康)、Neurology（神经病学）、Nutrition(营养学)、Obesity(肥胖)、Pregnancy（怀孕)、Prostate(前列腺)、Seniors(老年人疾病)、Sleep(睡眠问题)、Women's Health(女性健康)、Stroke(中风)。

采集每个选定类别的疾病中的健康新闻。对医学健康新闻网页使用Python的自然语言工具包NLTK3.2版本进行文本预处理，经过清除网页噪音、分词、统一大小写、词形归并、去除停用词等步骤。

为了对比数据集对算法结果的影响，使用的数据集分为3000、6000和9000个网页三种，分别记为3K、6K、9K。其中6K数据集是在每个类别已经抓取前100个网页基础上，又继续抓取100个网页得到的,9K同理。

# 3.2 Word2Vec模型构建

Word2Vec[16-17]用于实现词语的向量表示有CBOW 模型和Skip-Gram 模型；用于优化算法效率的方法包括 Hierarchy SoftMax(HS)和 Negative Sampling(NS)两种。将它们两两组合，得到4种训练框架，如表1所示：

表1训练框架  

<html><body><table><tr><td>训练框架</td><td>HierarchySoftMax</td><td>Negative Sampling</td></tr><tr><td>CBOW</td><td>CBOW&HS</td><td>CBOW&NS</td></tr><tr><td>Skip-Gram</td><td>Skip-Gram&HS</td><td>Skip-Gram&NS</td></tr></table></body></html>

(1) CBOW 模型和 Skip-Gram 模型

CBOW模型与Skip-Gram模型实际上是对神经网络语言模型(NNLM)的优化。NNLM 是统计语言模型的一种，工作原理见图1:

![](images/1e10161ac5ba79e092e45fa443f44f776e9a33788016294f22204637e5b9fbfa.jpg)  
图1神经网络语言模型

输入语料库C，构建词汇表V，词汇表V中词语总量为V，假设通过语言模型预测的词为 $\mathbf { w } _ { \mathrm { i } }$ ，其上下文为 $\mathbf { w } _ { \mathrm { i } }$ 的前(n-1)个词；上述条件下，NNLM模型目标为最大化式(1):

$$
\operatorname { P } ( \mathbf { w _ { i } } \mid \mathbf { w _ { i - ( n - 1 ) } } , \mathbf { w _ { i - ( n - 2 ) } } \cdots \mathbf { w _ { i - 1 } } )
$$

NNLM为三层前馈神经网络结构，输人层 $\mathbf { x }$ 为前(n-1)个词的词向量的顺序拼接，隐藏层 $\mathbf { h }$ ，输出层y为剩余两层神经网络。其中 $\mathrm { ~ H ~ }$ 为输人层到隐藏层的权重矩阵,U为隐藏层到输出层的权重矩阵， $\boldsymbol { \mathbf { b } } ^ { ( 1 ) } , \boldsymbol { \mathbf { b } } ^ { ( 2 ) }$ 为偏置项,tanh为双曲正切函数。

$$
\mathbf { x } = [ \mathbf { e } ( \mathbf { w _ { i - ( n - 1 ) } } ) ; \mathbf { e } ( \mathbf { w _ { i - ( n - 2 ) } } ) \cdots \mathbf { e } ( \mathbf { w _ { i - 1 } } ) ]
$$

$$
\mathrm { h } { = } \mathrm { t a n h } ( \mathbf { b } ^ { ( 1 ) } { + } \mathrm { H x } )
$$

$$
\scriptstyle \mathbf { y } = \mathbf { b } ^ { ( 2 ) } + \mathbf { U } \mathbf { h }
$$

值得注意的是，输出层 $\mathsf { y }$ 共有V个元素，分别对应下一个词为 $\mathrm { \Delta V }$ 中某词的可能性，需要利用SoftMax函数，将其转成概率值:

$$
\mathrm { P } ( \mathbf { w _ { i } } \mid \mathbf { w _ { i - ( n - 1 ) } } , \mathbf { w _ { i - ( n - 2 ) } } \cdots \mathbf { w _ { i - 1 } } ) = \frac { \exp ( \mathrm { y } ( \mathbf { w _ { i } } ) ) } { \displaystyle \sum _ { \mathrm { j = 1 } } ^ { \mathrm { N } } \exp ( \mathrm { y } ( \mathbf { w _ { j } } ) ) }
$$

训练时，优化的目标为最大化式(6):

$$
\sum _ { \mathbf { w _ { i - ( n - 1 ) } } } \log \mathbf { P } ( \mathbf { w _ { i } } \mid \mathbf { w _ { i - ( n - 1 ) } } , \mathbf { w _ { i - ( n - 2 ) } } \cdots \mathbf { w _ { i - 1 } } ) \quad { \mathrm { ~ i \in C ~ } }
$$

在实际训练时，通过随机梯度下降法来不断迭代，每次迭代都会对词向量及训练时中间矩阵等参数进行一次更新。优化完成后，相应的词向量也生成完毕。

由于从隐藏层到输出层的矩阵计算最耗费时间，故CBOW和Skip-Gram模型在NNLM的基础上去掉了隐藏层，使得计算量大大减小，而准确性则由训练样本的扩大来保证。

CBOW模型结构见图2。上下文c取词 $\mathbf { w } _ { \mathrm { i } }$ 的前后各 $( { \mathrm { n } } { - } 1 ) / 2$ 个词，假设上下文中所有的词对当前词出现概率影响的权重一样，不考虑出现的先后顺序，将输入层的上下文c的词向量 $\mathrm { { e } ( w _ { i } ) }$ 拼接改为词向量的平均值(或求和)，如式(7)所示；迭代时优化目标为最大化式(8)，迭代过程中也实现了词向量的优化。

$$
\mathrm { x = \frac { 1 } { n - 1 } \sum _ { w _ { j } \in c } e ( w _ { i } ) }
$$

$$
\sum _ { \mathrm { ( w , c ) } \in \mathrm { C } } \log \mathrm { P ( w \mid c ) }
$$

V 输出层y OO○O③OOO○○OO 输入层:OOO：OOOOOO：OOO ↑e(Wi-(n-1y2) ↑e(wi-) ↑e(wi+1) ↑e(Wi+(n-1y2) 原始文本 Wi-(n-1)/2 Wi-1 Wi+1 Wi+(n-1)/2

Skip-Gram 模型见图3，它采用"跳过某些单元"①的方式来扩大训练样本，上下文词语组合情况增多;从词 $\mathbf { w } _ { \mathrm { i } }$ 的上下文c中随机选择一个词的词向量 $\mathbf { w } _ { \mathrm { j } }$ 作为输入；优化的目标为最大化式(9):

$$
\sum _ { \mathrm { ( w , c ) { \in } C w _ { j } { \in } c } } \log \mathrm { { P } ( w \mid w _ { j } ) }
$$

![](images/21db7a871532ddbc43f08cf87c0f7b0ec7904381cacd71504cabefe464135ba1.jpg)  
图2 CBOW模型  
图3Skip-Gram 模型

(2) Hierarchy SoftMax 和 Negative Sampling

为了降低模型的时间复杂度，Hierarchy SoftMax借助分类的方式，对词语按照词频、词性或者主题进行区分，将某个类型下的词群抽象为一个词向量，计算时用这个抽象的词向量代表这类词，从而减小计算的复杂度。比如利用词频特征构造哈夫曼树来进行分层，用抽象的中间节点的向量来近似代替它的所有子节点的向量。Negative Sampling 相对更简单，采用负采样来提高训练速度。模型迭代时，采用随机负采样的方法进行计算并更新，而不是将下一个词为词汇表中的任意词的概率都计算一遍。使用负采样样本作为所有非当前词w(i)的替代。它的实现有多种算法，比如根据词频的带权采样算法。

# 3.3 模型训练

本文采用Python的gensim模块提供的Word2Vec工具包。训练过程中影响实验准确性和效率的参数主要如表2所示：

表2关键参数及解释  

<html><body><table><tr><td>参数</td><td>解释</td></tr><tr><td>sg</td><td>训练模型选择，取0为CBOW模型；取1为Skip-Gram 模型</td></tr><tr><td>hs</td><td>优化方法选择，取0为NS方法；取1为HS方法</td></tr><tr><td>negative</td><td>负采样样本值，默认为5</td></tr><tr><td>size</td><td>词向量维度，一般而言，几十到几百之间效果比较好</td></tr><tr><td>min_count</td><td>词频最低值，一般为10~100之间，用于限制词汇量 大小</td></tr><tr><td>sample</td><td>高频词采样样本数,Google文档推荐值为1e-5~1e-3 之间</td></tr><tr><td>window</td><td>训练窗口大小，表示句子中当前词和预测词最远距离, 一般取值越大越好，直到某个临界值</td></tr><tr><td>workers</td><td>训练模型的并行线程数，一般取4~6</td></tr></table></body></html>

sg 参数对应模型的选择，取1代表 Skip-Gram 模型；取0代表CBOW模型。hs参数对应优化算法的选择，取1代表HierarchySoftMax算法；取0代表NegativeSampling算法。negative参数对应NegativeSampling算法中负采样样本的数量。size 是词向量的维度，随着size值的增大，词向量准确性会先提高，到达某极值后，size值继续增加，准确性反而会降低。mincount参数是用来过滤低频词的，相当于进行一次词频低于min_count的词删除的预处理。sample参数是对高频词进行处理的。迭代过程中更新高频词会占用一定的时间，而高频词对应的词向量变化不大,故采用 Subsampling 技术(二次采样)在训练时跳过某些高频词。如公式(10)所示, $\mathsf { p } ( \mathrm { w } )$ 代表词语w被跳过的概率，其中 f(w)为该词在语料库C中出现的概率:$\mathrm { f ( w ) { \tt > } t }$ 时,f(w)越大,p(w)越大，被跳过的概率越大。

$$
\mathfrak { p } ( \mathrm { w } ) = 1 - \sqrt { \frac { \mathfrak { t } } { \mathfrak { f } ( \mathrm { w } ) } }
$$

window参数指训练窗口的大小，与上下文构造相关。每次构造词w 的上下文context(w)时，生成[1,window]上一个随机整数c，在w前后各取c个词，构成context(w)。一般而言,window值越大越好，直到到达某个极值。

workers参数则是并行线程数,workers越大，训练速度越快；可以根据计算机性能尽可能增加workers值。

# 3.4疾病主题语义相似性计算

模型训练的结果是将每个疾病主题词都映射为 N维向量空间中的一个点，根据向量空间中余弦距离公式求解词向量之间的距离，作为其语义相似性。假设两个疾病主题的 $\mathrm { ~ N ~ }$ 维词向量分别为：

$$
\begin{array} { r l } & { \mathbf { t } _ { 1 } = ( \mathbf { w } _ { 1 1 } , \mathbf { w } _ { 1 2 } , \mathbf { w } _ { 1 3 } , \cdots , \mathbf { w } _ { 1 ( \mathrm { n - 1 } ) } , \mathbf { w } _ { 1 \mathrm { n } } ) , } \\ & { \mathbf { t } _ { 2 } = ( \mathbf { w } _ { 2 1 } , \mathbf { w } _ { 2 2 } , \mathbf { w } _ { 2 3 } , \cdots , \mathbf { w } _ { 2 ( \mathrm { n - 1 } ) } , \mathbf { w } _ { 2 \mathrm { n } } ) } \end{array}
$$

余弦值越大，表示疾病主题 $\mathbf { t } _ { 1 }$ 和疾病主题 $\mathbf { t } _ { 2 }$ 在语义上越相似。计算公式如下：

$$
\cos ( \theta ) = \frac { \displaystyle \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n } } \mathbf { w } _ { \mathrm { 1 k } } \mathbf { w } _ { \mathrm { 2 k } } } { \displaystyle \sqrt { \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n } } { \mathbf { w _ { \mathrm { 1 k } } } } ^ { 2 } } \sqrt { \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n } } { \mathbf { w _ { 2 k } } } ^ { 2 } } }
$$

分别计算30个疾病主题两两之间的语义距离，得到435组值。

# 4实验设计与结果

Word2Vec的效果受到数据规模、模型的选择、参数的设定等因素影响。实验将对上述内容进行一一检测，并与专业医生对30种疾病关联关系的评分结果对比。记专家评分值为base值，利用SPSS计算训练值与base值的相关性分析，可得到各种因素对结果的影响，并评估该方法在实际中的可用性。

# 4.1 数据规模

图4中的纵坐标代表训练结果与base值的Pearson相关系数。数据集从3K扩大到6K时，效果有了一定的提高，而扩大到9K时，相关系数明显增大。另外在

3K数据集下，即使效果最好的Skip-Gram&HS结果，相关关系仍然不太显著。分别对各类参数进行调整，使用3K数据集时最优结果在0.01水平下相关系数为0.394，小于0.4。而数据集增大到9K时,Skip-Gram 模型的初始相关系数就达到0.454。可见数据规模是影响Word2Vec训练质量的关键性因素。数据规模越大，模型效果越好。

0.50 3K 6K 9K   
0.45   
0.40   
0.35   
0.30   
0.25   
0.20 CBOW&HS CBOW&NS Skip- Skipgram&HS gram&NS   
3K 0.269 0.251 0.306 0.297   
6K 0.293 0.266 0.354 0.306   
9K 0.294 0.379 0.454 0.424

Word2Vec是基于词的上下文关系来建立词的语义关系，数据集增大，词的上下文语境更全，训练得到的词向量更能够反映出该语料集里词汇的语义。实验说明3K数据集过小，难以很好地衡量词与词之间的语义相似性。Word2Vec技术在样本数较小时表现并不好。

# 4.2 模型选择

图4对4种训练架构的结果也进行了比较，SkipGram效果明显比CBOW好；但是后者的实际运行时间较短。对于同一语料库，Skip-Gram 会利用"跳过某些单元"的方式来扩大训练样本，这也可以看成"数据规模"的增加，从而带来了模型性能的增加与训练时间的增长。

从优化算法来看，以 Skip-Gram 模型为前提，虽然在数据集为9K时,Skip-Gram&HS比 Skip-Gram&NS 准确一些，但在3K和6K数据集下两者差别并不大，见图4。此处用于比较的 Negative Sampling 采样中负样本取值(negative)为5，事实上，负样本取值也会影响Negative Sampling方法的效果。

表3显示了对负样本取值的进一步对比。由于9K数据集训练时间太长，先缩小词向量维度size值为50以缩短训练时间，再探究negative 值对结果的影响。

在 Skip-Gram&NS方法中,negative 值越大，相关系数越高。虽然negative取5时，训练结果不如HierarchySoftMax算法；但当negative取20时，相关系数达到0.539，比HierarchySoftMax 算法高很多。

表3对 negative 因素的对比( $\scriptstyle \mathbf { \dot { s g } } = 1$ ，size $_ { : = 5 0 }$ ,9K数据集)  

<html><body><table><tr><td rowspan="2">Skip-Gram 模型</td><td rowspan="2">Hierarchy SoftMax</td><td colspan="3">Negative Sampling (negative取值)</td></tr><tr><td>10</td><td>15</td><td>20</td></tr><tr><td rowspan="2">Pearson 相关性 base N</td><td>.497**</td><td>.511**</td><td>.521**</td><td>.539**</td></tr><tr><td>435</td><td>435</td><td>435</td><td>435</td></tr></table></body></html>

综上所示，Skip-Gram 和 Negative Sampling，当负样本采样值为20时，训练模型得到的结果较优。以下参数选择均以 Skip-Gram&NS 方法为前提来开展实验。

# 4.3 参数对比

为了掌握词向量维度的大小(size)对算法结果的影响，首先利用规模较小、训练速度较快的数据集寻找size参数变化对结果的影响，再选择可使结果达到最优的参数取值区间进一步观察。在3K数据集控制size值在[50，500]范围内，发现词向量维度值并不是越大越好，取值在[50,100]结果较优，如图5所示。进而在9K 数据集缩小size 的取值在[50，100]区间范围,发现词向量维度为50的时候，Skip-Gram&NS与专家评分的相关性最高，如图6所示。

![](images/9bd53874fdfc4bdd61c3adfc6a007ecbaae787c03f4b02a22bff792f8df6800e.jpg)  
图5size因素取值对结果影响 $( \mathrm { s g } { = } 1$ ,3K数据集)

在Skip-Gram&NS方法中，固定已测参数负采样值、词向量维度为最佳取值(negativ $\scriptstyle \mathtt { a } = 2 0$ ， $\mathrm { s i z e } { = } 5 0$ ，研究高频采样阈值 sample对结果的影响。在Google 给出的Word2Vec 工具包中推荐在[1e-5，1e-3]范围内改变 sample值，因此将该参数设置为图7所示的几个取值。结果发现，sample 值越小训练结果与base 值的相关性越高，训练时间也明显变短。高频词在语料库中出现次数很多并且提供的有用信息更少，训练时对应的词向量变化也较小。由公式(10)可知,sample 值越小,语料库中出现概率高于sample 的词语越多，二次采样中，被跳过的高频词越多，准确性越高。在9K数据文本作为训练集的情况下,sample 值取le-5 时结果较优。两者相关系数达到0.614，结果有明显提高。

![](images/9a3b8ab3b448abd3a83672c8c2c063e379dcfb121b38a293e3565d7c3eca5dd8.jpg)  
图6在图5的最优区间细粒度观察size取值对结果的影响 $\scriptstyle \left( \displaystyle \operatorname { s g } = 1 \right.$ $\scriptstyle \mathrm { h s } = 1$ ,9K数据集)

![](images/7ea33c38c7372eec911ea0a257dc73d99e7cade41d8b6b47c89c3bb1e11ac1cc.jpg)  
图7sample 因素对结果的影响( $\mathrm { \stackrel { \cdot } { s g } } = 1$ ， $\scriptstyle \mathrm { h s } = 0$ negative $: = 2 0$ ，size $= 5 0$ ,9K数据集)

令sample $\ L =$ le-5，进一步考察低频词阈值min_count对其取值从40开始，以步长为20变化。由表 4可知，在(40,100)范围内min_count 的改变对结果影响不大。训练前创建词表时，去掉词频低于40的词可以使结果更优。

表4min_count因素对结果的影响 $( \mathrm { s g } { = } 1$ $\scriptstyle \mathrm { h s } = 0$ negative $\scriptstyle : = 2 0$ ，size $\scriptstyle : = 5 0$ ，sample $\ L =$ 1e-5,9K数据集)

<html><body><table><tr><td>min_count 参数</td><td>40</td><td>60</td><td>80</td><td>100</td></tr><tr><td>Pearson 相关性</td><td>.614**</td><td>.610**</td><td>.611**</td><td>.606**</td></tr><tr><td>base N</td><td>435</td><td>435</td><td>435</td><td>435</td></tr></table></body></html>

上下文窗口window的取值理论上是越大越好,但是window 扩大将致使训练时间加长。在[50，200]区间上改变window参数，与专家评分比较得到如图8所示的结果：window为50左右相关系数就不再增加,为 0.635。此时 Skip-Gram取上下文样本时，在[1，50]区间上生成一个随机整数c，然后在词w前后各取c个词，构成 context(w)。

![](images/50dcb30c352839c0294ff558e3195072656e09066ad2d338b58c3da04c5a76e3.jpg)  
图8window 因素对比( $\mathrm { \stackrel { } { s g } } = 1$ ， $\scriptstyle \mathrm { h s } = 0$ ,negative $\scriptstyle : = 2 0$ size $\scriptstyle : = 5 0$ ，sample $\mathbf { \Psi } =$ le-5,min_coun $\scriptstyle 1 = 4 0$ ,9K数据集)  
图9 base&W2V散点图

综合以上对参数因素的探究，发现采用Skip-Gram模型和Negative Sampling(负样本采样值为20)算法组合，词向量维度取50，高频词采样阈值取1e-5，低频词阈值取40，上下文窗口取50的时候，训练模型得到的相似性度量结果最优，与base 值的相关系数达到0.635，将此结果记为W2V。

# 5Word2Vec的疾病关联探测效果分析

将实验得到的最优结果W2V与base值进行详细对比分析，对W2V值归一化处理，得到散点图如图9所示。将435组值按照base值从大到小排序，从1开始编号到435，以编号作为横坐标，base值和W2V值作为纵坐标。

1.2●base  
1.0 + 十 +W2V  
0.8 十十+ +中 + 好01 1 十+  
0.6 车 1 +再车= 车十  
0.4十车 + 中 车十 # 十 XX 中  
0.2 ++ 上+ + 品 年年年年#+ +车00 100 200 300 400 500

在base值从大到小降低时，W2V值也是整体降低的趋势。语义相似性较高的区域，W2V值更分散；相似性低的区域,W2V的值相对而言更集中。Word2Vec计算结果的整体性较好，局部性需要进一步改进。

按照base 值的取值范围，将数据分成7个区间,对应的base值从高到低。由表5容易发现，base值较高的区间上，相应的W2V的最小值要比低区间上最小值高。均值的分布与base值区间值的高低变化趋势一致，区间越高，均值越大，这也与图9结论相吻合;但是相对而言，W2V的均值变化范围更小。中位数的变化趋势与均值基本保持一致。base取1的区间上，标准差最大，为0.157；base取0的区间上，标准差最小,为0.127；这表示，相似性最高的区间上，W2V点的离散程度更大，相似度最低的区间上，W2V点的分布情况最集中。

表5W2V值在不同水平base 值上统计值  

<html><body><table><tr><td rowspan="2">base值</td><td rowspan="2">编号 范围</td><td colspan="5">W2V值</td></tr><tr><td>最小值</td><td>最大值</td><td>均值</td><td>中位数</td><td>标准差</td></tr><tr><td>1</td><td>2:43</td><td>0.244</td><td>0.971</td><td>0.709</td><td>0.710</td><td>0.157</td></tr><tr><td>0.833</td><td>44:105</td><td>0.148</td><td>0.910</td><td>0.562</td><td>0.562</td><td>0.157</td></tr><tr><td>0.667</td><td>106:176</td><td>0.162</td><td>0.962</td><td>0.522</td><td>0.522</td><td>0.150</td></tr><tr><td>0.5</td><td>177:233</td><td>0.119</td><td>1.000</td><td>0.426</td><td>0.399</td><td>0.156</td></tr><tr><td>0.333</td><td>234:296</td><td>0.085</td><td>0.704</td><td>0.372</td><td>0.384</td><td>0.147</td></tr><tr><td>0.167</td><td>297:372</td><td>0.000</td><td>0.572</td><td>0.327</td><td>0.338</td><td>0.130</td></tr><tr><td>0</td><td>373:436</td><td>0.032</td><td>0.609</td><td>0.311</td><td>0.282</td><td>0.127</td></tr></table></body></html>

由Word2Vec训练得到的疾病主题语义关联中，按照相似性从高到低排序，得到的前10对相似的疾病主题对如表6所示。对应的base值中，有6组疾病是高度相关的,3组疾病相关性也较高。唯有男性健康与女性健康这组关系，Word2Vec计算得到是高度相关,而专家评分仅为0.5，差异较大。这可能是因为Word2Vec中表示词组时用向量相加表示，Men'sHealth、Women'sHealth的向量分别为词语health与词语 men、women的向量加合，计算时两者相似性会随之增高。尤其词语men与词语women在语料库中出现频率较高，特指性不强，在语义上还很相似，从而高估了Men's Health(男性健康)与Women's Health(女性健康)之间的关联。并且这两种疾病本身涵盖的范围也比较宽泛，影响了Word2Vec判断准确性。

表6Top10 相似疾病主题  

<html><body><table><tr><td>疾病主题i</td><td>疾病主题j</td><td>W2V 相似性</td><td>W2V 归一化</td><td>对应 base 值</td></tr><tr><td>Men's Health</td><td>Women'sHealth</td><td>0.848</td><td>1.000</td><td>0.5</td></tr><tr><td>Cardiovascular</td><td>Cholesterol</td><td>0.822</td><td>0.971</td><td>1</td></tr><tr><td>Breast Cancer</td><td>Prostate</td><td>0.814</td><td>0.962</td><td>0.667</td></tr><tr><td>Cardiovascular</td><td>Heart Disease</td><td>0.801</td><td>0.948</td><td>1</td></tr><tr><td>Mental Health</td><td>Women'sHealth</td><td>0.767</td><td>0.910</td><td>0.833</td></tr><tr><td>Anxiety</td><td>Depression</td><td>0.766</td><td>0.909</td><td>1</td></tr><tr><td>Allergy</td><td>Asthma</td><td>0.766</td><td>0.908</td><td>1</td></tr><tr><td>Cardiovascular</td><td>Hypertension</td><td>0.746</td><td>0.886</td><td>1</td></tr><tr><td>Cardiovascular</td><td>Stroke</td><td>0.729</td><td>0.867</td><td>1</td></tr><tr><td>Men's Health</td><td>Mental Health</td><td>0.724</td><td>0.862</td><td>0.667</td></tr></table></body></html>

# 6结语

本文选取 30 个疾病主题，采集 MedicalNewsToday上的新闻文本，利用Word2Vec技术计算疾病间关联关系，并与专家评分结果进行对比。研究发现，数据规模越大，模型效果越好，但训练时间更长；Skip-Gram模型结合负样本数为20的NegativeSampling优化方法在大规模数据集上的实验结果最优；高频词二次采样阈值越小，训练效果越好，训练时间也越短。最优条件下，训练结果与专家评分的相关系数达到0.635；语义相似性较高的区域，Word2Vec训练值更分散；相似性低的区域，Word2Vec训练值相对而言更集中。将Word2Vec训练结果按照相似性从高到低排序，得到的前10组疾病关系中，有9组在专家评分中相关性也很高。

利用Word2Vec技术在面向大众的健康信息源中也可以探测疾病关联，其有效性表明该技术可用于改善大众的健康信息搜寻的个性化服务。

未来将从以下方面开展研究：扩大数据集，Word2Vec在数据规模增大时效果提升明显，实际中使用更多数据可得到更理想的结果；调整疾病类型，从更细的粒度开展关联关系研究。

# 参考文献：

[1] Kempson E.Review Article:Consumer Health Information Services [J].Health Libraries Review,1984,1(3):127-144.   
[2] Eysenbach G.RecentAdvances: Consumer Health Informatics [J].BMJ Clinical Research,2000,320(7251): 1713-1716.   
[3]侯小妮，孙静．北京市三甲医院门诊患者互联网健康信息 查寻行为研究[J]．图书情报工作，2015，59(20)：126-131, 11.(Hou Xiaoni,Sun Jing.Research on Internet Health Information Searching Behaviors of Outpatients from Tertiary Referral Hospital in Beijing [J].Library and Information Service,2015,59(20): 126-131,11.)   
[4]Klavans JL,Muresan S.Evaluation of the DEFINDER System for Fully Automatic Glossary Construction[C]. In: Proceedings AMIA Annual Symposium. 2001: 324-328.   
[5]Zeng-Treitler Q, Tse T. Exploring and Developing Consumer Health Vocabularies [J]. Journal of the American Medical Informatics Association,2006,13(1): 24-29.   
[6]Zeng-Treitler Q，Goryachev S,Tse T,et al. Estimating Consumer Familiarity with Health Terminology:A Contextbased Approach [J]. Journal of the American Medical Informatics Association,2008,15(3): 349-356.   
[7]Burgun A,Bodenreider O.Mapping the UMLS Semantic Network into General Ontologies [C]. In: Proceedings of Annual Symposium. 2001: 81-85.   
[8]Keselman A, Smith C A,Divita G, et al. Consumer Health Concepts that do not Map to the UMLS:Where do They Fit? [J]. Journal of the American Medical Informatics Association, 2008,15(4): 496-505.   
[9]Yang ZH,Lin HF,LiYP,et al. TREC 2005 Genomics Track Experiments at DUTAI [C].In: Proceedings of the 14th Text REtrieval Conference. 2005: 1-9.   
[10] Yang Z H,Lin HF,Li Y P,et al. DUTIR at TREC 2006 Genomics and Enterprise Tracks [C]. In: Proceedings of the 15th Text REtrieval Conference.2006:1-10.   
[11]Jiang Q,Wang Y,Hao Y,et al.miR2Disease:A Manually Curated Database for microRNA Deregulation in Human Disease [J]．Nucleic Acids Research，2009,37(Database issue): D98-104.   
[12]Yang H, Yang C C.Using Health Consumer Contributed Data to Detect Adverse Drug Reactions by Association Mining with Temporal Analysis [J].ACM Transactions on Intelligent Systems & Technology,2015,6(4): Article No.55.   
[13] Chen A T. Exploring Online Support Spaces: Using Cluster AnalysistoExamineBreastCancer,Diabetesand Fibromyalgia Support Groups [J]. Patient Education and Counseling,2012,87(2): 250-257.   
[14]刘红霞，张进，陈璟浩．WHO 英文网站健康主题语义链接 关系社会网络分析[J]．图书情报工作,2014,58(13):75-82. (Liu Hongxia,Zhang Jin,Chen Jinghao．Social Network Analysis of Semantic Links Relationships Among Health Topics in WHO English Website[J].Library and Information Service,2014,58(13):75-82.)   
[15]Bengio Y,Schwenk H,Senécal J-S，et al．A Neural Probabilistic Language Model [J].Journal of Machine Learning Research,2003,3(6): 1137-1155.   
[16]Mikolov T,Chen K,Corrado G,et al.Efficient Estimation of Word Representations in Vector Space [OL]. [2016-05-13]. http://arxiv.org/pdf/1301.3781v3.pdf.   
[17]Mikolov T,Sutskever I,Chen K，et al．Distributed RepresentationsofWordsandPhrasesandTheir Compositionality [A].//Advances in Neural Information Processing Systems [M].2013:3111-3119.   
[18]Handler A.An Empirical Study of Semantic Similarity in WordNet and Word2Vec [D].Columbia University,2014.   
[19]Amunategui M,Markwell T,Rozenfeld Y.Prediction Using Note Text: Synthetic Feature Creation with Word2Vec [J]. Computer Science,2015(3):1-6.   
[20] Ju R,Zhou P,Li C H,et al．An Efficient Method for Document Categorization Based on Word2Vec and Latent Semantic Analysis [C].In: Proceedings of the 2015 IEEE International Conference on Computer and Information Technology； Ubiquitous Computing and Communications; Dependable,Autonomic and Secure Computing；Pervasive Intelligenceand Computing(CIT/IUCC/DASC/PICOM). IEEE,2015:2276-2283.   
[21]Su Z,Xu H,Zhang D,et al. Chinese Sentiment Classification

Usinga Neural Network Tool—Word2Vec [C].In: Proceedings of the 2O14 International Conference on Multisensor Fusion and Information Integration for Intelligent Systems (MFI). IEEE, 2014:1-6.

# 作者贡献声明：

陈：提出研究思路，设计研究方案，论文修订;  
罗文馨：进行实验，采集、清洗和分析数据，论文起草;  
邓思艺：参与文献调研。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储，E-mail:luowenxinl994@foxmail.comchenchong@bnu.edu.cn。  
[1]罗文馨.Word2Vec 疾病相似性结果.xlsx．本文中与专家评分结果相关度最高的(Pearson 0.635)Word2Vec 结果(即W2V)得到的疾病关联度.  
[2]罗文馨.Word2Vec词向量训练结果.txt.W2V结果对应的词向量，用于计算疾病的语义相似性.  
[3] 陈.30 种疾病新闻网页.html.抓取的Medical News Today 网站上的9000个新闻网页.

收稿日期:2016-05-16   
收修改稿日期:2016-05-22

# Detecting Disease Associations with Word2Vec from Consumer Health Information

Luo WenxinChen Chong Deng Siyi (School of Government, Beijing Normal University, Beijing 10o875, China)

Abstract: [Objective] Average people usually do not know the complex associations among diseases,which poses negative effects to their health information seeking experience.This study tries to detect the associations among diseases using popular medical information with the help ofdeep learning technology(Word2Vec),aiming to improve personalized information services.[Methods]First,we identified 30common disease topics withthe helpof medical professionals,and then colected related reports from Medical News Today.Second,we built word vector for each document with Word2Vec technology to calculate the semantic similarities among them.Finally，we compared the machine training results with experts’scores to evaluate the performance of the proposed methd. We also investigated the impacts of different models,optimization methods,data sizes and important parameters to the results.[Results] The corelation coeficient between the Word2Vec results and the experts’scores reached 0.635 in optimal condition. We found that Skip-Gram model with less than 2O negative samples on large scale dataset yielded the best results. [Limitations] The precision of the Word2Vec judgment was afected by the numberof disease topics.The granularity of disease topic needed to be improved.[Conclusions] The Word2Vec technology could be used to identify diseases association from consumer health information sources.It could also be used to improve the personalized health information services.

Keywords: Word2VecDisease association Non-professional medical information Health informaiton Personalization

# EBSCO进一步资助Koha

EBSCO 宣布继续倡导开源和开放获取，进一步资助 Koha。Koha 是世界上第一个功能丰富、免费开源的集成图书馆系统，全世界有15000多家各种类型的图书馆使用Koha作为其集成图书馆系统。

EBSCO于2015年2月起开始为Koha提供资金资助，本次对Koha的最新资助，将帮助Koha进行下一阶段的功能改进，如额外的系统互操作性，以及采购和电子资源管理功能，具体来说，包括：

(1）开发一个采购的 API;(2）全面实施订购和发票系统;(3）改进Koha 和CORAL的互操作性，为传统的集成图书馆系统工作流和 ERM功能的结合提供一个开源的解决方案。Koha将坚持开源的传统，这些Koha的增强功能也将是开源的，可供他人使用、修改和重新部署。这些增强的功能可望于 2017 年第一季度完成。(编译自:htps://botereeasbfatisoituoug

(本刊讯)