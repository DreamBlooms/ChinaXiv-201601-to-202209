# 基于文本聚类与兴趣衰减的微博用户兴趣挖掘方法

秦永彬a,b，孙玉洁a，魏笑a

(贵州大学a.计算机科学与技术学院;b.贵州省公共大数据重点实验室，贵阳 550025)

摘要：微博平台隐含潜在的用户信息，通过微博数据挖掘用户兴趣具有重要的社会意义。结合用户兴趣与微博信息的特点，提出了一种文本聚类与兴趣衰减的微博用户兴趣挖掘（TCID-MUIM）方法。首先，通过基于词林的同义词合并策略弥补建模时词频信息不足的弊端；其次，利用二次 Single-Pass 不完全聚类算法将用户微博划分为多个簇，将簇合并为同一文档以弥补微博文本短小难以挖掘主题信息的问题；最后，通过LDA模型建模，并考虑用户兴趣随时间变化的问题，引入时间因子，将微博一主题矩阵压缩为用户一主题矩阵，获取用户兴趣。实验表明，较之传统建模方法与合并用户历史微博为同一文档的建模方法，TCID-MUIM方法挖掘的用户兴趣主题具有更好的主题区分度，且更贴合用户的真实兴趣偏好。

关键词：微博；Single-Pass 聚类；LDA模型；用户兴趣挖掘；兴趣衰减 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.11.0743

# Microblog user interest mining based on text clustering and interest decay

Qin Yongbin a, bt, Sun Yujiea, Wei Xiaoa (a.Colege ofComputer Science&Technology,b.Guizhou KeyLaboratoryofPublicBig Data Guizhou UniversityGuiyang 550025,China)

Abstract: Microblog platformcontains potentialuser'sinformation,through microblogdata mining microbloguserinteresthas importantsocialsignificance.Onaccountofthecharacteristicsofuserinterestand microbloginformation,thispaperputforward a method of microblog user interest mining based on text clustering and interest decay(TCID-MUIM).Firstly,it used the synonymscombined strategy basedon Tongyici Cilin to make up for the process of modeling the lack of word frequency information.Secondly,itusedthedoublesingle-passincomplete clusteringalgorithmtomakeuptheproblemthat themicroblog text wasshortersothatdifcult todigthetopic information.Finaly,itusedtheLDAmodelmodeling,aswellasconsidering the user'sinterestchanges with time,byintroductionoftiefactorcompresses the microblog-topic matrix intotheuser-topic matrix to gain user interest.Experimentalresultsshow thatcomparedto traditional modeling methodsandthe modelingmethods of merger user's allhistory microblog as the same document,te TCID-MUIM method presented which modeling results have a higher topic's differences and closer to the user's real interest preferences.

Key Words: microblog; Single-Pass clustering; LDA model; user interest mining; interest decay

# 0 引言

信息技术的飞速发展与互联网的广泛应用，促使了微博、微信等具有强大交互性的网络社交平台的深入应用并使其融入了人们的社会化生活。微博，作为一个以用户为主体进行信息分享的广播式社交网络平台，由于信息发布便捷、内容形式多样、名人效应等特点聚集了2.71亿用户[1]，微博已成为人们获取信息、交流信息的重要工具。调查显示，微博用户关注的内容倾向于基于兴趣的垂直细分领域[1]，且微博平台上 $6 1 . 9 \%$ 的用户只浏览、点赞、评论或转发，基本不发原创微博[2]，这意味着用户使用微博的主要目的是在微博平台上获取自己感兴趣的内容。然而微博平台存在“信息过载”问题，用户很难在海量微博信息中获取感兴趣的信息。个性化推荐通过对用户信息的挖掘有针对性地为用户推荐有效的微博信息，是解决上述问题的有效方法.在此过程中，用户兴趣挖掘是为用户进行个性化信息推荐的前提。因此，本文以微博平台的用户兴趣挖掘为研究内容。

针对微博平台用户兴趣挖掘，许多学者展开了相关研究工作。针对建模文本的选择问题，Chen等人[3]比较了用户历史微博文本及用户粉丝的微博文本用于用户兴趣挖掘的效果，发现基于用户历史微博文本构建的模型更能表达用户兴趣。针对微博文本长度短影响挖掘效果的问题，Abel等人[4通过引入外部语料（网页链接）扩展微博信息，提取能反映用户兴趣的关键字；Hong等人[5提出了三种主题模型训练方法，其实验证明：合并用户所有微博为一个文档用于建模相较于一条微博作为一个文档或合并相同标签的微博为一个文档进行建模，能更有效地训练主题模型。上述方法中，通过网页链接引入外部语料的方法所获取的数据并非全部与微博文本内容高度相关，会影响建模效果；而合并用户历史微博为同一文档的建模方法强行抹去微博文本边界，会使得建模后主题区分度变低。

在微博平台的热点话题与信息检索领域，刘红兵和唐晓波等人[67通过LDA模型与文本聚类相结合的方法，将具有相似话题的微博聚集成簇，分别实现微博平台的热点话题检测及微博信息的有效检索。该方法提供了解决微博文本长度短影响挖掘效果的新思路。

在上述研究的基础上，本文提出了一种基于文本聚类与时间衰减的微博用户兴趣挖掘方法（text clusteringand interestdecay for microbloguser interest mining，TCID-MUIM)。该方法通过同义词合并策略，弥补建模过程中词频信息不足的弊端；通过二次Single-Pass不完全聚类算法，将用户微博划分为多个簇，将簇合并为同一文档，以弥补微博文本短小难以挖掘主题信息的问题。考虑到LDA主题模型具有优秀的降维能力，用于微博等具有稀疏性特征的文本建模具有一定优势[8]，因此选择通过LDA模型对多个微博文本进行建模。同时，考虑到用户兴趣会随时间变化的问题，提出基于时间因子的主题矩阵压缩方法，通过记忆值将微博一主题矩阵压缩为用户一主题矩阵，更准确地表达用户兴趣主题。

吉布斯采样（Gibbs sampling）[10]等参数推导方法进行参数估计。

![](images/570b06970cfbb28ee87c0e701148f7111c8ba80360257fed46a56f26552919b3.jpg)  
图1LDA模型的贝叶斯网络图

通过LDA构建微博用户兴趣模型时，若输入的语料是 $M$ 条表示为词袋模型的微博文本W，事先给定先验参数 $\alpha$ 、 $\beta$ 及需要划分的主题数 $K$ ，可训练得到用于表达用户兴趣的微博一主题矩阵、主题一词汇矩阵 $\Phi$ ，如图2所示。

![](images/ebf29443d607ca1f4df7e28eddd1d3b23456d44b3a6397e2ea593e474bb9f635.jpg)  
图2基于LDA模型的用户兴趣表达

# 1 LDA模型及用户兴趣表达

LDA模型[9是一种包含文档层、词汇层和主题层的三层贝叶斯模型，它也是一种概率生成模型。在LDA模型中，文档的生成前提是词袋模型(bag-of-words)，其把文档看成是一系列词汇的集合，忽略文中的语法和词汇的出现顺序，使得词与词之间独立可交换。LDA模型的基本思想是，一篇文档由一系列描述文档的主题构成，每个主题下是一系列描述主题的词汇，其生成文本的方式可以用LDA模型的贝叶斯网络图表示。

图1描述了文本集中 $M$ 个文档的生成过程。以第 $m$ 个文档的生成为例，其生成步骤如下：a）从参数为 $\beta$ 的Dirichlet先验分布中抽取 $K$ 个主题对应的词汇分布 $\Phi = \{ \varphi _ { k } \} _ { k = 1 } ^ { K }$ ；b）从参数为 $\alpha$ 的 Dirichlet 先验分布中抽取文档的主题分布 $\theta _ { m }$ ；c）根据主题分布概率 $\theta _ { m }$ ，从 $K$ 个主题中抽取一个主题 $z _ { m , \mathrm { n } }$ ；d）从主题 $z _ { m , \mathrm { n } }$ 对应的词汇分布 $\varphi _ { z _ { m , n } }$ 中抽取一个词汇 $w _ { m , \mathrm { n } }$ ；e）重复步骤 $\operatorname { c } ) \mathrm { d } ) { n }$ 次，直到生成文档中全部的 $N _ { { _ m } }$ 个词。

在 LDA 模型中， $w _ { m , \mathrm { n } }$ 是可观测的数据， $\alpha$ 和 $\beta$ 是根据经验给定的先验参数。文档的主题分布 $\Theta$ 及主题下的词汇分布 $\Phi$ 都是需要推断的未知参数，可通过变分贝叶斯期望最大化算法[9]、

# 2基于文本聚类与兴趣衰减的微博用户兴趣挖掘算法

微博平台的用户兴趣挖掘可描述为：假定用户 $u$ 的 $M$ 条历史微博文本集 $D _ { u } = \{ d _ { u 1 } , d _ { u 2 } , \cdots , d _ { u M } \}$ 。对用户 $u$ 的兴趣挖掘首先是对 $D _ { u }$ 中的文本进行有针对性的预处理，把每条微博文本表示为特征词的集合 $W _ { u } = \{ w _ { u 1 } , w _ { u 2 } , \cdots , w _ { u M } \}$ ；然后通过主题建模方法（如LDA）对 $W _ { u }$ 进行兴趣主题建模，获取微博一主题矩阵 $\boldsymbol { \Theta } _ { u }$ 及主题一词汇矩阵 $\Phi _ { \phantom { } u }$ 。其中， $\boldsymbol { \Theta } _ { u }$ 描述了每条微博的主题概率分布，如图3所示。

![](images/31d9bdfb730df66a5050719ef2c583c0fa019857e2360c04976f5dc151447f6e.jpg)  
图3微博-主题矩阵 $\boldsymbol { { \Theta } } _ { u }$

图3中， $\boldsymbol { \Theta } _ { u }$ 表达了每一条用户历史微博的主题概率分布，但很难理解为用户自身的兴趣主题分布。除此之外，LDA虽然在挖掘文本主题方面具有一定优势，但微博本身的一些固有特点还是为用户兴趣挖掘带来了以下问题：

a）针对微博文档集进行LDA建模时，需要预先设定主题数$K \circ K$ 的选取对于兴趣建模效果具有很大影响， $K$ 的过小和过大都会导致主题检测的不准确。针对此问题普遍的解决方法是通过主题差异性确定 $K$ 取值。但微博平台用户量大，对每个用户都通过此办法测定 $K$ 取值会带来算法复杂度大、兴趣挖掘效率低的问题。

b）由于微博文本具有长度较短、内容形式丰富多样、语言不规范、网络流行语多等特点，使得提取特征后用于兴趣建模的用户语料的词频信息及上下文信息严重缺乏，影响微博文本的主题建模效果。

c）没有考虑到用户的兴趣随时间变化的特点。

本文将在LDA模型的基础上提出TCID-MUIM挖掘方法，通过在LDA 建模前后引入同义词合并策略、二次 Single-pass不完全聚类算法、基于时间因子的主题矩阵压缩方法解决上述问题，用于挖掘用户兴趣主题。

# 2.1 同义词合并策略

对于微博平台的用户兴趣挖掘，首要步骤就是对微博文本进行去噪处理、分词处理、停用词处理、去除低频词及单字词等预处理操作，将每条微博文本表示为特征词的集合。然而微博文本较短小且长尾特征明显，去除低频词会使建模过程中词频信息不足的问题进一步加剧。因此，本文通过基于《同义词词林》的同义词合并策略，将用户微博文本中存在的低频词合并到高频词、单字词合并到多字词，对部分低频词及单字词进行合理利用。

《同义词词林》[]是梅家驹先生等人按意义进行编排一部类义词典，包含一个词语的同义词以及其广义的相关词，其扩展版收录词语7万余条。词林以词义为主，兼顾词类，把词语划分为5级结构，不同等级通过不同的编码表示。具体标记如表1所示。

表1词语编码  

<html><body><table><tr><td>编码位</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>符号举例</td><td>D</td><td>4</td><td>1</td><td>5</td><td>B</td><td>0</td><td>2</td><td>=\#\@</td></tr><tr><td>符号性质</td><td>大类</td><td>中类</td><td>小类</td><td></td><td>词群</td><td>原子词群</td><td></td><td></td></tr><tr><td>级别</td><td>第1级</td><td>第2级</td><td colspan="2">第3级</td><td>第4级</td><td colspan="2">第5级</td><td></td></tr></table></body></html>

表中的编码位是按照从左到右的顺序排列。在第五级（6、7位）中，每个分类里词语数量已较少，难以进一步进行分割，称为原子词群或原子节点。而编码位的第8位仅是标记位，具有 ${ } ^ { 6 6 } =$ ”、“#”、“ $@$ ”三种标记，分别代表词行“同义”“同类”“独立”。通过词林中标记为“ $\dot { \bf \Phi } = { \bf \Phi }$ ”的同义词行可以实现对词汇的同义词替换。

基于《同义词词林》的同义词合并策略的具体步骤如算法

1所示。

算法1同义词合并策略

输入：用户 $u$ 的微博文本集 $D _ { u } = \{ d _ { u 1 } , d _ { u 2 } , \cdots , d _ { u M } \}$ 。输出：处理后的微博文本集 $W _ { u } = \{ \mathbf { w } _ { \mathrm { u l } } , \mathbf { w } _ { \mathrm { u 2 } } , \cdots , \mathbf { w } _ { \mathrm { u M } } \} \ ,$ 步骤1对用户微博文本集 $D _ { u }$ 进行预处理，建立用户词库 $V _ { u }$ ，并根据预处理后文本集 $D _ { u }$ 中词汇的出现次数统计用户词库中词汇的词频。

步骤2设定阈值 $\upsilon$ ，将用户词库 $V _ { \boldsymbol { u } }$ 中词汇词频大于等于 $\upsilon$ 的词放入高频词表，低于 $\upsilon$ 的词放入低频词表；并将 $V _ { \boldsymbol { u } }$ 中出现的单字词放入低频词表。

步骤3根据《同义词词林》中的词语编码位，将第8位中符号位为“#”的同类词和符号位为‘ $@$ ”的独立词词行剔除，只保留符号位为“ $\mathbf { \sigma } = \mathbf { \sigma }$ ”的同义词词行。

步骤4根据高频词表中词汇词频从高到低的顺序为词汇进行统一编号 $G = \{ 1 , 2 , \cdots , i , \cdots , n \}$ ，从编号为1的高频词开始，将高频词与《同义词 词林》进行匹配。若高频词 $i$ 与词林匹配成功，则将匹配成功的词行作为 高频词 $i$ 的背景词行；否则，跳到下一个高频词，直到所有高频词与词林 匹配恰好一次。

步骤5从编号为1的高频词开始，将低频词按词汇词频从高到低的编号次序与高频词背景词行中的词汇进行匹配，匹配成功，则赋予低频词与该高频词相同的词汇编号，并在中间词表中加入该词，从低频词表中删除该词，直到所有高频词的背景词行都与低频词表中的词汇匹配恰好一次。

步骤6 将经过步骤5后低频词表中仍存在的词汇加入用户停用词表，使用用户停用词表对经过第一次预处理的用户微博文本集再去一次停用词。步骤7利用高频词表及中间词表中词及编号的对应关系，将经过步骤6处理的用户微博文本集中的词汇变换为编号；再利用高频词表中词及编号的对应关系，通过反变换将编号转换为词汇。实现从低频词到高频词、单字词到多字词的同义词合并。

步骤8输出同义词合并后的微博文本集 $W _ { u }$ 。

# 2.2二次Single-pass不完全聚类算法

Single-pass 聚类算法又称单通道法或单遍法，是一种简单的增量聚类算法。通过数据对象的出现次序依次进行聚类处理，根据相似度值进行匹配。若相似度值大于事先设定的阈值，则将数据对象归入该类簇；否则将该数据对象作为一个新的聚类簇。

Single-pass聚类可随着文本数量的增多而动态地变化，适用于用户微博列表不断增多的微博聚类。但具有明显的次序依赖的问题，可能导致较早完成遍历的微博因为与之前得到的话题的相似度略低于阈值而被重新创建了新的话题，影响聚类效果。因此，本文采用二次 Single-pass 算法对用户微博文本进行聚类。同时，考虑到用户兴趣在一定时间内具有一定的内聚性，在一定时间段内发布或转发的微博文本可能属于同一类别，兴趣方向变化不大，因此第一次Single-pass 聚类时仅通过时间标记将后续输入的文本与前面时间标记最近的 $m$ 个簇进行相似性比较。考虑到用户微博列表中的微博文本主题方向较杂乱，因此第二次Single-pass 聚类时，不对第一次 Single-pass 聚类的微博孤点进行处理，使用不完全聚类[12]的方法进行聚类。

由于微博文本特征词较少，所以选择Jaccard相似系数作为聚类算法中相似度的计算基础。对于给定的词集 $A$ 、 $B$ ，Jaccard相似系数的计算公式为

$$
s i m _ { \ j } \left( A , B \right) = \frac { A \cap B } { A \cup B }
$$

若簇的微博集合为 $c _ { K } = \{ \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \cdots , \mathbf { w } _ { k } \}$ ，其对应词集为$A _ { _ { c _ { K } } } = \{ A _ { \mathrm { w } _ { 1 } } , A _ { \mathrm { w } _ { 2 } } , \cdots , A _ { \mathrm { w } _ { k } } \}$ ， $A _ { \mathrm { w } _ { i } }$ 为 $\mathbf { w } _ { i }$ 对应的词集,其中 $i = 1 , 2 , \cdots , k$ 。目标微博 $\mathbf { W } _ { m }$ 对应的词集为 $B _ { \mathrm { w } _ { m } }$ ，则第一次 Single-pass 聚类时，微博与簇间的相似度计算公式可定义如下：

$$
s i m \left( A _ { { { c } _ { \kappa } } } , B _ { { { \mathrm { w } } _ { m } } } \right) = \frac { 1 } { k } \times \sum _ { 1 \leq i \leq k } \left\{ s i m _ { { { J } } } \left( A _ { { { \mathrm { w } } _ { i } } } , B _ { { { \mathrm { w } } _ { m } } } \right) \right\}
$$

在式（2）中，通过计算 $B _ { \mathrm { w } _ { m } }$ 与微博簇 $A _ { { { \scriptscriptstyle c } _ { { \scriptscriptstyle K } } } }$ 的平均相似度值来衡量目标微博 $\mathbf { W } _ { m }$ 与簇 $c _ { \scriptscriptstyle K }$ 间的相似度。

相同地，簇 $c _ { K } = \{ \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \cdots , \mathbf { w } _ { k } \}$ 与簇 $c _ { L } = \{ \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \cdots , \mathbf { w } _ { l } \}$ 间的相似度计算公式定义如下：

$$
s i m \bigl ( A _ { _ { c _ { K } } } , A _ { _ { c _ { L } } } \bigr ) = \frac { 1 } { k \times l } \times \sum _ { _ { 1 \leq i \leq k } \atop { 1 \leq j \leq l } } \left\{ s i m _ { _ { J } } \Bigl ( A _ { _ { \mathrm { w } _ { i } } } , A _ { _ { \mathrm { w } _ { j } } } \Bigr ) \right\}
$$

二次Single-pass不完全聚类算法的具体步骤如算法2所示。

算法2 二次Single-pass不完全聚类算法

输入：用户 $u$ 的微博文本集 $W _ { u } = \left\{ \mathbf { w } _ { u 1 } , \mathbf { w } _ { u 2 } , . . . , \mathbf { w } _ { u M } \right\}$ ，阈值 $\tau , \ \xi$ ，比较次数 $m$ 。  
输出：簇文本及微博孤点的集合 ${ W } _ { u } ^ { * } = \left\{ \mathbf { w } _ { u 1 } ^ { * } , \mathbf { w } _ { u 2 } ^ { * } , . . . , \mathbf { w } _ { u Q } ^ { * } \right\}$ 和 $K$ 值。步骤 1 将微博文本 $\textbf { W } _ { u i }$ 的发布时间设置为其时间标记 $t _ { u i }$ ，其中$i = 1 , 2 , \cdots , M$ 。按时间标记 $t _ { u 1 } , t _ { u 2 } , . . . , t _ { u M }$ 的顺序输入微博文本$\mathbf { W } _ { u 1 } , \mathbf { W } _ { u 2 } , . . . , \mathbf { W } _ { u M }$ ，其中 $t _ { u M }$ 为最新一条微博的发布时间。针对 $W _ { u }$ 进行处理得到对应的词集 $A _ { \boldsymbol { W _ { u } } } = \{ A _ { \mathrm { w } _ { u 1 } } , A _ { \mathrm { w } _ { u 2 } } , . . . , A _ { \mathrm { w } _ { u M } } \}$ 。  
步骤2当 $i = 1$ ，簇数 $J = 1$ 时，将时间标记为 $t _ { u 1 }$ 的微博文本 $\mathbf { W } _ { u 1 }$ 作为第一个聚类簇 $c _ { 1 }$ ，即 $c _ { 1 } = \{ \mathbf { w } _ { u 1 } \}$ ，执行 $i = i + 1$ ，转到步骤3。  
步骤3当 $i \leq M$ 时，若 $J > m$ ，则根据式（2）计算（20 $a _ { j } = \operatorname* { m a x } _ { J - m \leq j \leq J } \left\{ s i m \Bigl ( A _ { c _ { j } } , A _ { \mathrm { w } _ { u i } } \Bigr ) \right\}$ ；否则根据式（2）计算j=max{sim(A,A）}。若j>τ，则转到步骤3.1；否则转到步骤3.2。  
步骤3.1更新 $c _ { j } = c _ { j } \cup \mathbf { W } _ { u i }$ ，用微博 $\textbf { W } _ { u i }$ 的时间 $t _ { u i }$ 标记更新簇 $c _ { j }$ 的时间标记，执行 $i = i + 1$ ，转到步骤3。  
步骤3.2执行 $J = J + 1$ ，建立新簇 $c _ { J } = \{ \mathrm { w } _ { u i } \}$ ，将时间标记为 $t _ { u i }$ 的微博文本 $\textbf { W } _ { u i }$ 作为新簇 $c _ { J }$ 的时间标记，执行 $i = i + 1$ ，转到步骤3。步骤4执行 $C = \{ c _ { j } : \vert c _ { j } \vert \geq 2 , 1 \leq j \leq J \}$ 以及$C _ { 1 } = \{ c _ { j } : \vert c _ { j } \vert = 1 , 1 \leq j \leq J \}$ ，转到步骤5。  
步骤5将簇族 $C$ 重新标记为 $\boldsymbol { C } ^ { * } = \{ \boldsymbol { c } _ { s } ^ { * } \} _ { s = 1 } ^ { | \boldsymbol { C } | }$ ，按时间标记 $t _ { 1 } , t _ { 2 } , . . . , t _ { | C | }$ 的顺序输入微博簇族 $\boldsymbol { C } ^ { * }$ ，其中 $t _ { \mathrm { l } }$ 为离当前时间最近的时间标记。将 $C ^ { * }$ 对应的词集记为 $A _ { _ { C } ^ { * } } = \{ A _ { _ { c _ { s } ^ { * } } } \} _ { _ { s = 1 } } ^ { | C | }$ ，这里的 $\boldsymbol { A } _ { \boldsymbol { c } _ { s } ^ { * } }$ 为 $c _ { s } ^ { * }$ 对应的词集。步骤6当 $s = 1$ ，簇数 $I = 1$ 时，将时间标记为 $t _ { 1 }$ 的簇 $c _ { 1 } ^ { * }$ 作为第一个聚类簇 $c _ { 1 } ^ { * }$ ，执行 $s = s + 1$ ，转到步骤7。步骤7当 $s \triangleleft { C } ^ { * }$ 时，根据式（3）计算 $b _ { r } = \operatorname* { m a x } _ { 1 \leq r \leq I } \left\{ s i m { \left( A _ { { { c } _ { r } } ^ { * } } , A _ { { { c } _ { s } ^ { * } } } \right) } \right\}$ $b _ { r } > \tau$ ，则转到步骤7.1；否则，转到步骤7.2。否则，转到步骤8。步骤7.1更新 $c _ { r } ^ { * } = c _ { r } ^ { * } \cup c _ { s } ^ { * }$ ，执行 $s = s + 1$ ，转到步骤 $7 .$ （204号步骤7.2 执行 $I = I + 1$ ，更新簇 $c _ { I } ^ { * } { = } c _ { s } ^ { * }$ ，执行 $s = s + 1$ ，转到步骤7。步骤8将步骤7的结果按照簇内微博数的数目从大到小排序，并将排序结果标记为 $\boldsymbol { C } ^ { * * } = \{ c _ { 1 } ^ { * * } , c _ { 2 } ^ { * * } , \cdots , c _ { I } ^ { * * } \}$ ，将 $c ^ { * * }$ 中的 $I$ 个微博簇分别合并为$I$ 个簇文本 $\mathbf { W } _ { 1 } ^ { * } , \mathbf { W } _ { 2 } ^ { * } , . . . , \mathbf { W } _ { I } ^ { * }$ ，簇的时间标记作为该文本的时间标记。步骤9 初始时 $K { = } 1$ ，计算 $\varepsilon _ { 1 } { = } \rvert \operatorname { c } _ { 1 } ^ { * * } \left. / M \right.$ ，若 $\varepsilon _ { 1 } \geq \xi$ ，则输出 $K$ ；否则执行 $K = K + 1$ ，转到步骤10。步骤10当 $K \le I$ 时，计算 $\varepsilon _ { \scriptscriptstyle K } = \sum _ { 1 \leq k \leq K } \vert c _ { k } ^ { * * } \vert / M$ ，若 $\varepsilon _ { K } < \xi$ ，则执行$K = K + 1$ ；否则，输出 $K$ 。步骤11 执行 $\boldsymbol { W } _ { u } ^ { * } = \boldsymbol { C } _ { 1 } \cup \{ \mathbf { w } _ { 1 } ^ { * } , \mathbf { w } _ { 2 } ^ { * } , . . . , \mathbf { w } _ { I } ^ { * } \}$ ，将 $\boldsymbol { W } _ { u } ^ { * }$ 的结果重新标记为$W _ { u } ^ { * } = \left\{ \mathbf { W } _ { u 1 } ^ { * } , \mathbf { W } _ { u 2 } ^ { * } , . . . , \mathbf { W } _ { u Q } ^ { * } \right\} \mathrm { ~ , ~ } \mathbb { H H H } Q = \left| C _ { 1 } \right| + I \mathrm { ~ , ~ }$ 注：在步骤1中， $A _ { W _ { u } }$ 中的 $A _ { \mathrm { w } _ { u i } }$ 为 $\textbf { W } _ { u i }$ 对应的词集，其中  
（204 $i = 1 , 2 , \cdots , M$ 。步骤 $2 { \sim } 3 . 2$ 完成第一次 Single-Pass 聚类。在  
步骤3中， $\boldsymbol { a } _ { j }$ 的下标 $j$ 表示 $\operatorname* { m a x } _ { 1 \leq j \leq J } \left\{ s i m { \left( A _ { c _ { j } } , A _ { \mathrm { w } _ { u i } } \right) } \right\}$ 或  
（204号 $\operatorname* { m a x } _ { J - m \leq j \leq J } \left\{ s i m \left( A _ { c _ { j } } , A _ { \mathrm { w } _ { u i } } \right) \right\}$ 取得最大值的下标。在步骤 4中， $c$ 表示  
微博数大于等于2的微博簇族， $C _ { 1 }$ 表示簇内微博数等于1的孤  
点簇族。步骤 $6 { \sim } 7 . 2$ 完成第二次Single-Pass 聚类。在步骤7  
中， $b _ { { } _ { r } }$ 中的下标 $r$ 表示 $\operatorname* { m a x } _ { 1 \leq r \leq I } \bigg \{ s i m \Big ( A _ { c _ { s } ^ { * } } , A _ { c _ { r } ^ { * } } \Big ) \bigg \}$ 取得最大值的下标。  
$\left| C \right| , \left| C ^ { * } \right| , \left| C _ { 1 } \right|$ 分别表示集合 $c$ 、集合 $c ^ { * }$ 和 $C _ { 1 }$ 中的元素个数。  
在步骤 $9 \mathrm { \sim } 1 0$ 中，按照文献[13]描述的“微博短文本聚类后其  
聚类结果具有长尾分布的特征”的思想，根据长尾分布的一般  
取值原则可将阈值 $\xi$ 设置为0.20；通过 $\xi$ 计算得到的 $K$ 值即为  
$\boldsymbol { W } _ { u } ^ { * }$ 中的大簇数目。  
2.3基于时间因子的主题矩阵压缩方法田户的兴搬可以分为长期兴搬与短期兴搬长期兴搬是华

用户长时间保持的兴趣偏好，它不会随时间的流逝而造成大的变化；而短期兴趣则是指因特定原因导致的用户兴趣短期偏移，其特点是用户在一定时期内会大量关注与该兴趣相关的微博信息，但在一段时间以后，用户对该兴趣相关微博信息的关注会迅速衰减，甚至不再关注。

用户兴趣变化体现在用户发布的历史微博主题随时间的变化中，变化过程与Ebbinghaus 遗忘曲线[13]遵循同样的规律，在已有的兴趣范围内，新的兴趣不断诞生的同时，旧的兴趣也在不断地衰减，甚至遗忘。根据这一特点，本文提出了基于时间因子的主题矩阵压缩方法，根据记忆函数给用户近期微博的主题分布赋予较高的记忆值（memoryvalue)，根据记忆值压缩微博一主题矩阵，获取用户一主题矩阵，得到用户的兴趣主题分布。使得用户微博列表中近期发布的微博对用户兴趣的影响越大，尽可能减少短期兴趣对用户兴趣的影响，使获取的用户兴趣主题分布更贴近用户当前的兴趣偏好，并将微博一主题矩阵$\Theta$ 压缩为易于理解的用户一主题矩阵 $\theta _ { u }$ 。

设用户 $u$ 最近一条微博的发布时间为 $t _ { u r }$ ，若${ W } _ { u } ^ { * } = \{ \mathbf { w } _ { u 1 } ^ { * } , \mathbf { w } _ { u 2 } ^ { * } , \cdots , \mathbf { w } _ { u Q } ^ { * } \}$ 中第 $m$ 个文本 $\textbf { W } _ { u m } ^ { * }$ 的时间标记为 $t _ { u m }$ ，则兴趣建模时其记忆值 $m \nu ( \mathbf { w } _ { u m } ^ { * } , t _ { u r } )$ 定义如下：

$$
\begin{array} { r } { m { \nu } ( \mathbf { w } _ { u m } ^ { * } , t _ { u r } ) = 2 ^ { - \lambda ( t _ { u r } - t _ { u m } ) } } \end{array}
$$

其中： $\lambda > 0$ ， $\lambda$ 越大，历史数据的重要性随时间降低的越快。

根据式(4)，可以利用 $\boldsymbol { W } _ { u } ^ { * }$ 中每个文本对应的时间标记求取微博一主题矩阵 $\Theta _ { u } = \{ \theta _ { m } \} _ { m = 1 } ^ { Q }$ 每一行（微博的主题分布）对应的记忆值。

$$
\begin{array} { c c } { { \begin{array} { c c c c c c c } { { \mathrm { m e m o r y ~ v a l u e } } } & { { } } & { { T _ { u 1 } } } & { { T _ { u 2 } } } & { { . . . } } & { { T _ { u K } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { m \nu ( { \bf w } _ { u 1 } ^ { * } , t _ { u r } ) } } & { { } } & { { \bf w } _ { u 1 } ^ { * } } & { { [ p _ { 1 1 } } } & { { p _ { 1 2 } } } & { { . . . } } & { { p _ { 1 K } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { m \nu ( { \bf w } _ { u 2 } ^ { * } , t _ { u r } ) } } & { { } } & { { \bf w } _ { u 2 } ^ { * } } & { { [ p _ { 2 1 } } } & { { p _ { 2 2 } } } & { { . . . } } & { { p _ { 2 K } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { . . . . } } & { { } } & { { } } & { { . . . . } } & { { } } & { { . . . . } } & { { \ldots } } & { { . . . } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { m \nu ( { \bf w } _ { u 2 } ^ { * } , t _ { u r } ) } } & { { } } & { { \bf w } _ { u Q } ^ { * } } & { { [ p _ { Q 1 } } } & { { p _ { Q 3 } } } & { { . . . } } & { { p _ { Q K } } ] } \end{array} } } \end{array}
$$

根据记忆值以及主题 $T _ { u k }$ 对应的每一条微博维上的概率分布值，可以求得主题 $T _ { u k }$ 在用户一主题分布中的概率值 $P ( T _ { u k } )$ 。计算公式如下：

$$
P ( T _ { u k } ) = \frac { \sum _ { m = 1 } ^ { Q } \Bigl [ m \nu \bigl ( \mathbf { w } _ { u m } ^ { * } , t _ { u r } \bigr ) \times p _ { m k } \Bigr ] } { \sum _ { k = 1 } ^ { K } \sum _ { m = 1 } ^ { Q } \Bigl [ m \nu \bigl ( \mathbf { w } _ { u m } ^ { * } , t _ { u r } \bigr ) \times p _ { m k } \Bigr ] } , k = 1 , 2 , \cdots , K
$$

根据式(5)可以得到用户最终的兴趣主题分布$\theta _ { u } = ( P ( T _ { u 1 } ) , P ( T _ { u 2 } ) , \cdots , P ( T _ { u K } ) )$ 。

# 2.4TCID-MUIM挖掘方法

在中文微博平台，用户历史微博列表主要包括转发微博与原创微博两种类型的微博。转发微博由转发部分和原创部分组成。原创部分是自己对转发内容的附加内容。同时，微博中有一类特殊的功能符号一一话题标签，它是微博同一类话题的标志，同一用户历史微博中具有相同话题标签的微博通常话题相关性加强。针对这一特点，结合LDA模型及上述同义词合并策略、二次Single-pass不完全聚类算法、基于时间因子的主题矩阵压缩方法，将TCID-MUIM挖掘方法的具体步骤如算法3所示。

算法3TCID-MUIM 挖掘算法输入：用户 $u$ 的微博文本集 $D _ { u } = \{ d _ { u 1 } , d _ { u 2 } , \cdots , d _ { u M } \} \ .$

输出：用户一主题分布 $\theta _ { u }$ 、主题-词汇矩阵 $\Phi _ { u }$ 。

步骤1对微博进行第一次初始聚类：将转发微博与转发时发布的原创微博合并；根据提取的话题标签，将含有同一标签的微博文本合并。

步骤2根据算法1同义词合并策略，对步骤1处理后的微博文本进行同义词合并处理。

步骤3 根据算法2二次Single-pass不完全聚类算法，对步骤2处理后的微博文本进行聚类，获取簇文本及微博孤点的集合 $\boldsymbol { W } _ { u } ^ { * }$ 、 $K$ 值。步骤4 将 $\boldsymbol { W } _ { u } ^ { * }$ 作为 LDA 建模的语料， $K$ 值设为 LDA 建模的主题数。通过 LDA 模型获取用户 $u$ 的微博-主题矩阵 $\boldsymbol { { \Theta } } _ { u }$ 、主题-词汇矩阵 $\Phi _ { u }$ 。步骤5根据3.3节中描述的基于时间因子的主题矩阵压缩方法，利用微博文本的时间标记计算记忆值，将微博一主题矩阵 $\boldsymbol { { \Theta } } _ { u }$ 压缩为用户一主题分布 $\theta _ { u }$ 。

步骤6输出用户一主题分布 $\theta _ { u }$ ，主题一词汇矩阵 $\Phi _ { u }$ 。

# 3 实验

# 3.1实验设置

目前，在国内中文微博平台的相关研究领域，还没有用于评测的标准数据集。本文通过firefox浏览器及爬虫插件datascraper、metastudio获取实验数据，采集了新浪微博平台1356位用户，共计91万余条微博数据。根据实验需要，过滤掉其中历史微博数小于150的用户，将保留的623位用户的微博数据按发布时间分为两部分，其中发布时间较近的前50条微博作为测试集，其余部分作为兴趣模型训练集。提取博文内容中的话题标签属性后，对数据进行去噪处理、分词处理（ICTCLAS分词系统[I4])、去停用词处理，将处理后的数据用于实验。

LDA建模参数设置为alpha $_ { : = 0 . 1 }$ ,beta $_ { : = 0 . 1 }$ ,iter_times $\scriptstyle  = 1 0 0$ TCID-MUIM方法中涉及的参数，分别将阈值参数设置为 $\upsilon = 3$ ，$\tau = 0 . 2 5$ ， $\xi = 0 . 2 0$ ，比较次数设置为 $m = 1 0 0$ 。

# 3.2主题有效性

微博主题挖掘的目标是从海量信息中挖掘出能代表用户兴趣的兴趣主题，并匹配相关性高的词汇描述主题，词汇与主题的匹配程度越高，则认为主题有效性越高。为了验证TCID-MUIM挖掘方法的有效性，实验另设置了以下两种方法进行对比：

a）文本合并（textmerge，TM)。将用户的所有历史微博合并为一个文本，使用LDA模型对合并后的文本建模。b）传统方法（conventionalmethod，CM)。不对文档进行同义词合并、聚类处理，直接使用LDA模型对用户微博文本集建模。

三种方法的建模主题数K设定为TCID-MUIM挖掘方法中确定的大簇数目。表2显示了三种方法下用户兴趣挖掘的实验结果。限于篇幅，表中只列出clueid为121365465的用户根据三种方法所获取的3个兴趣主题，每个主题由概率最大的前10个单词表示。通过观察主题所属词汇并比对数据可以看出，这3个主题分别描述的是与医患关系、法治、教育相关的主题；虽然三种方法所挖掘的主题都能在一定程度上表达用户兴趣，但TCID-MUIM挖掘方法挖掘到的主题与其对应的关键词汇匹配准确率较高，主题集中性更强。例如在Topic1st中，TCID-MUIM方法下的关键词都与医患关系有很强的相关性，而TM与CM方法下的关键词中却存在法治、政府等相关性较低的词汇。

表2主题有效性对比  

<html><body><table><tr><td colspan="6">TOPIC 1st</td><td colspan="4">TOPIC 2nd</td><td colspan="3">TOPIC 3rd</td></tr><tr><td colspan="2">TCID-MUIM</td><td colspan="2">TM</td><td colspan="2">CM</td><td colspan="2">TCID-MUIM</td><td>TM</td><td>CM</td><td>TCID-MUIM</td><td>TM</td><td>CM</td></tr><tr><td>医院</td><td>0.0174</td><td>治疗</td><td>0.0058</td><td>医院</td><td>0.0199</td><td>律师</td><td></td><td></td><td></td><td>0.0288 违法0.0048 律师0.0216 学生0.0273教师0.0211学生0.0234</td><td></td><td></td></tr><tr><td>患者</td><td>0.0059</td><td>法治</td><td>0.0048</td><td>北京</td><td>0.0107</td><td></td><td></td><td></td><td></td><td>取保候审0.0087反抗0.0043法院0.0108学校0.0098教授0.0195学校0.0113</td><td></td><td></td></tr><tr><td>医生</td><td>0.0059</td><td>医院</td><td>0.0043</td><td>患者</td><td>0.0080</td><td>法院</td><td></td><td></td><td></td><td>0.0077犯罪0.0043国家0.0089研究0.0091大学0.0120大学0.0106</td><td></td><td></td></tr><tr><td></td><td>百度0.0059</td><td>死亡</td><td>0.0039</td><td>政府</td><td>0.0067</td><td>组织</td><td></td><td></td><td></td><td>0.0053律师0.0037 公开0.0083 教育0.0082学院0.0102 校方0.0082</td><td></td><td></td></tr><tr><td>医疗</td><td></td><td></td><td>0.0056魏则西0.0037</td><td>百度</td><td>0.0062</td><td>人权</td><td></td><td></td><td></td><td>0.0048行政0.0037 国际0.0073 大学0.0078 学生0.0085校长0.0067</td><td></td><td></td></tr><tr><td></td><td>魏则西0.0051</td><td>北京</td><td>0.0037</td><td>莆田</td><td>0.0053</td><td>涉嫌</td><td></td><td></td><td></td><td>0.0048法官0.0037 判决0.0070 同学0.0069 教育0.0082 政府0.0063</td><td></td><td></td></tr><tr><td>莆田</td><td>0.0051</td><td>身体</td><td>0.0032魏则西0.0053</td><td></td><td></td><td>罪名</td><td></td><td></td><td></td><td>0.0044人权0.0037 政府0.0051 小学0.0062 校长0.0079 老师0.0059</td><td></td><td></td></tr><tr><td>良心</td><td>0.0043</td><td>良心</td><td>0.0032</td><td>医疗</td><td>0.0049</td><td>羁押</td><td></td><td></td><td></td><td>0.0044披露0.0037庭审0.0051 老师0.0056政府0.0069教育0.0059</td><td></td><td></td></tr><tr><td>家属</td><td>0.0039</td><td>记者</td><td>0.0032</td><td>医生</td><td>0.0049</td><td>庭审</td><td></td><td></td><td></td><td>0.0039 酒店0.0037要求0.0048文化0.0052北京0.0067 研究0.0051</td><td></td><td></td></tr><tr><td>北京</td><td>0.0034</td><td>医疗</td><td>0.0032</td><td>记者</td><td>0.0045</td><td>判决</td><td></td><td></td><td></td><td>0.0039 仲裁0.0032 案件0.0048 实验0.0049文化0.0061文化0.0043</td><td></td><td></td></tr></table></body></html>

# 3.3主题差异性

主题差异性是指主题模型生成的主题分布间的差异程度。主题模型的思想是，建模后主题间的差异度越大、相似度越小，则认为主题越有代表性，模型的建模效果越好。基于此，本文通过距离测度的方法度量主题模型建模后获取的主题分布间的差异性，以此衡量TCID-MUIM建模方法的性能。具体方法是：首先，通过度量两个概率分布间差异程度的 jensen-shannon(JS)距离计算模型生成的各个主题间的差异度；然后，根据上一步骤的计算结果计算主题平均差异度，并将平均差异度作为衡量模型主题差异性的指标。

JS 距离计算公式如下：

$$
D _ { J S } ( \varphi _ { i } , \varphi _ { j } ) = \frac { 1 } { 2 } \Bigg [ D _ { K L } ( \varphi _ { i } , \frac { \varphi _ { i } + \varphi _ { j } } { 2 } ) + D _ { K L } ( \varphi _ { j } , \frac { \varphi _ { i } + \varphi _ { j } } { 2 } ) \Bigg ]
$$

$$
D _ { K L } ( \varphi _ { i } , \frac { \varphi _ { i } + \varphi _ { j } } { 2 } ) = { \sum } _ { n = 1 } ^ { n } p _ { i n } \ln \frac { 2 p _ { i n } } { p _ { i n } + p _ { j n } }
$$

其中： $\varphi _ { i } = ( p _ { i 1 } , p _ { i 2 } , \cdots , p _ { i n } )$ 与 $\varphi _ { j } = ( p _ { j 1 } , p _ { j 2 } , \cdots , p _ { j n } )$ 分别是两个主题 $T _ { i }$ 与 $T _ { j }$ 的词概率分布。

本实验通过上述方法度量TCID-MUIM、TM和CM三种建模方法的主题差异性。三种建模方法中两两主题之间的JS 平均距离比较如表3所示。可以看出，三种建模方法中TM方法的主题差异性（JS值）相较于其他两种建模方法较低，这可能是由于强行抹去文本边界的原因；而TCID-MUIM方法在三种建模方法中的JS值相对较大，具有更好的主题差异性，说明了对微博进行同义词合并及不完全聚类能够帮助主题模型发现更具代表性的主题。

表3三种建模方法JS 距离比较   

<html><body><table><tr><td>建模方法</td><td>JS距离</td></tr><tr><td>TCID</td><td>0.368191</td></tr><tr><td>TM</td><td>0.297962</td></tr><tr><td>CM</td><td>0.353599</td></tr></table></body></html>

# 3.4兴趣挖掘效果对比

为了判断TCID-MUIM挖掘用户兴趣的准确度，本文将用户最新发布的50条微博作为测量数据，其余部分的微博用作用户兴趣主题建模数据，对比TCID-MUIM、CM、TM三种挖

掘方法的主题建模效果。评价指标选择预测准确率、漏检率以及本文自定义的概率准确率。具体的计算公式如下：

$$
P = \frac { N _ { c } } { N _ { T } }
$$

其中： $P$ 表示预测准确率； $N _ { c }$ 表示测量数据中属于用户兴趣主题的微博数； ${ \cal N } _ { \tau }$ 表示测量数据中的微博总数。

$$
P _ { _ { M I S S } } = \frac { N _ { M } } { N _ { T } }
$$

其中： $P _ { _ { M I S S } }$ 表示漏检率； $N _ { { } _ { M } }$ 表示测量数据中与用户兴趣主题不相关的微博数； ${ { N } _ { \mathrm { { r } } } }$ 表示测量数据中的微博总数。

$$
P _ { _ { A C } } = \sum _ { i = 1 } ^ { k } c _ { i } \times p _ { u , i }
$$

其中： $P _ { \scriptscriptstyle A C }$ 表示概率准确率； $p _ { u , i }$ 是用户兴趣主题分布$\theta _ { \boldsymbol { u } } = ( p _ { u , 1 } , p _ { u , 2 } , \cdots , p _ { u , k } )$ 中第 $i$ 个兴趣主题的分布概率； $c _ { i }$ 是测量数据中属于第 $i$ 个兴趣主题的微博数目。为了在图表中更直观的展示三种方法下的 $P _ { \scriptscriptstyle A C }$ ，选择将三种方法下的 $P _ { \mathrm { } _ { A C } }$ 值归一化处理，并放大一倍。

图4显示了在采用LDA模型进行用户兴趣建模的条件下，TCID-MUIM、CM、TM三种不同用户兴趣挖掘方法进行兴趣主题挖掘的实验对比效果。观察可发现，CM与TM方法相比，TM方法概率准确率高于CM，但预测准确率低于CM，这可能是由于TM方法将所有微博文本合为一个文档，导致主题集中性强，单一主题概率高，但主题区分度较低，不能更大范围地涵盖用户兴趣偏好所致；而TCID-MUIM方法因将文本语料进行了不完全聚类处理，保证了主题的集中性，同时考虑了兴趣衰减问题，保证了主题与用户实时兴趣的贴合性，所以TCID-MUIM与CM、TM方法相比在三种评价指标下都具有明显优势。

# 4 结束语

本文针对直接使用LDA模型挖掘用户兴趣时存在的微博文本长度较短、语义信息缺乏影响主题建模效果以及没有考虑用户兴趣随时间变化的问题，提出了基于文本聚类与兴趣衰减的微博用户兴趣挖掘算法TCID-MUIM，通过同义词合并策略、二次Single-pass不完全聚类算法、LDA模型建模方法以及基于时间因子的主题矩阵压缩方法挖掘用户兴趣主题。在真实微博数据集上对TCID-MUIM相关实验验证进行实验，实验结果表明通过TCID-MUIM方法挖掘的用户兴趣主题与 TM、CM方法相比具有更好的主题区分度，且更贴合用户的真实兴趣偏好。下一步工作需要解决的问题是用户兴趣挖掘中的冷启动问题，考虑是否可以利用用户其他网站上的历史数据信息构建用户兴趣模型。

![](images/30c6b736497419c3b343340b462f8457435fd7523f25117dbb622b9521479fe4.jpg)  
图4用户兴趣挖掘方法效果对比

# 参考文献：

[1]China Internet Network Information Center.The 39th statistical report on Internet development in China [EB/OL].(2017-01-22) .http://www. cnnic. net.cn/hlw fzyj/hlwxzbg/hlwtjbg/201701/t20170122_66437.htm.   
[2]企鹅智酷.2016 微博用户研究报告 [EB/OL].(2016-09-09).http://tech. qq.com/original/archives/al24. html.   
[3]Chen J,Nairn R,Nelson L，et al.Short and tweet:experiments on recommending content from information streams [C]//Proc of International Conference on Human Factors in Computing Systems.2010:1185-1194.   
[4]Abel F, Gao Q,Houben G J,et al.Twitter-based user modeling for news recommendations [C]//Proc of the 23rd International Joint Conference on Artificial Intelligence.[S.1.] : AAAI Press,2013:2962-2966.   
[5]Hong L,Davison B D.Empirical study of topic modeling in twitter [C]// Proc of the 1st Workshop on Social Media Analytics.[S.1.] :ACM Press, 2010: 80-88.   
[6]刘红兵，李文坤，张仰森．基于LDA 模型和多层聚类的微博话题检测 [J].计算机技术与发展,2016,26(6):25-30.   
[7] 唐晓波，房小可．基于文本聚类与LDA 相融合的微博主题检索模型研 究[J]．情报理论与实践,2013,36(8):85-90.   
[8]张培晶，宋蕾．基于LDA的微博文本主题建模方法研究述评[J]．图书 情报工作,2012,56(24):120-126.   
[9]Blei D M,Ng AY, Jordan MI.Latent dirichlet allocation [J]. Journal of Machine Learning Research,2003,3:993-1022.   
[10] Griffiths TL,Steyvers M.Finding scientific topics [J].Proceedings of the National Academy of Sciences of the United States of America,2004,101 (1): 5228.   
[11]梅家驹．同义词词林[M].上海：上海辞书出版社,1983.   
[12]彭泽映，俞晓明，许洪波，等．大规模短文本的不完全聚类[J].中文 信息学报,2011,25(1):54-59.   
[13]于洪，李转运．基于遗忘曲线的协同过滤推荐算法[J].南京大学学报： 自然科学版,2010,46(5):520-527.   
[14] ZhangHP,YuHK,XiongDY,etal.HHMM-based Chinese lexical analyzer ICTCLAS[C]// Proc of the 2nd SIGHAN Workshop on Chinese Language Processing. 2003: 184-187.