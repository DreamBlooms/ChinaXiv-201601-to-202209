# 数字文本自动分类中特征语义关联及加权策略研究综述与展望

李湘东1,²巴志超1,高凡¹1(武汉大学信息管理学院武汉 430072)2(武汉大学信息资源研究中心 武汉 430072)3(山东省科学院情报研究所济南 250014)

摘要：【目的】探讨目前针对书目、题录信息以及新闻网页、博客等新兴媒体开展的数字文本自动分类研究中存在的主要问题和可能的解决方向。【文献范围】基于机器学习方法的自动分类研究领域中，关于特征语义转换、特征扩展和加权策略等方面的主要研究成果及相关文献。【方法】按照主要研究、关键技术、现有成果水平和今后发展方向等方面进行分析归纳。【结果】针对特征语义转换、特征扩展和加权策略等研究领域，分析问题的现象和原因，指出当前研究在文本语义表示、各种知识库的利用等方面存在的不足。【局限】没有涉及分类过程中分类算法等其他比较成熟的研究领域。【结论】今后可以从向量空间模型与概率主题模型相结合、利用各种外部知识库并提高概念相似度计算能力、结合多种加权策略构建复合加权表示模型等方向开展分类研究，以提高数字文本自动分类的性能。

关键词：自动分类特征语义关联特征语义转换特征扩展加权策略

分类号：TP391 G35

# 1基于机器学习文本自动分类概述

基于机器学习文本自动分类的基本原理是通过对现有分类体系及其已分类文本(称为样本、训练文本、训练集文本或训练集)的内容进行统计学习，以掌握各个类别的知识或模式，形成分类模型或分类器，然后将其作用于待分类文本(也称为测试集文本或测试集，与训练集共同构成语料库)，根据待分类文本的内容与从训练集获得的模式进行比较来确定其类别。目前，基于机器学习自动分类的主要对象是图书书目信息或期刊论文题录信息(简称书目信息)，新闻网页、博客、微博等新兴媒体的各种数字文本资源。

基于机器学习的分类过程主要包括语料库整理、分词、预处理、特征相关处理、文本表示、分类器构建等基本环节。其中，分词、预处理和文本表示是信息检索、主题分析、聚类以及分类等以文本为主要研究对象的相关研究中都需要事先解决的问题，已有学者专门对其进行研究，且取得比较成熟的研究成果。特征相关处理环节中，主要是针对特征选择方法的研究，其和分类算法的研究在分类研究中都比较成熟。然而，随着对书目信息、新兴媒体等分类对象的文本特性认识的深入，以及基于向量空间模型(VectorSpace Model,VSM)、LDA(LatentDirichletAllocation)概率主题模型等文本表示模型等相关分类环节的进一步研究，发现单纯地依靠传统的词频统计且忽略特征之间的语义关系，不能很好地提高最终的分类性能，而考虑文本以及特征之间的同义、冗余和蕴涵等语义关系，借助外部知识库、语义词典等对特征进行关联扩充、语义建模等，能有效改善文本分类性能。同时，在通过特征选择方法进行特征选取时也暴露出一些影响分类性能的问题。特征选择方法从语料库的分词结果中选取能够代表各个类别的词或特征，但却不考虑词或特征的语义信息，因此，这些问题不是特征选择方法所能解决的，针对特征的选取，仅限于特征选择方法的改进已经不能满足对分类性能进一步提高的需求。随着研究的深人和细化发展，除特征选择之外，特征相关处理环节需要增加特征语义转换、特征扩展、加权策略等研究内容，如表1所示。这些也是目前分类研究中比较活跃的研究领域。本文着重总结这些研究领域所取得的主要成果。

表1特征处理的相关问题  

<html><body><table><tr><td>现象</td><td>原因</td><td>后果</td><td>解决办法</td></tr><tr><td rowspan="2">特征之间缺乏 语义关联</td><td>VSM模型以词作为维度，并假定文本中的词与词之间相互 独立。以VSM模型表示的文本中，词与词之间在语义上的 同义、近义、多义以及词之间上下位等多重语义关系未能 得到反映。</td><td>特征之间缺乏语义关联，意味着待分类文 本中的特征不管重要性如何，都可能会因 为在训练集形成的特征空间中匹配不到同 一个词而无法参人到分类中，即测试集的特征语 不同作者、不同文献类型的文本之间，如新闻网页、博客、特征空间与训练集的特征空间之间存在一义转换</td><td></td></tr><tr><td>微博等新兴媒体内的体例结构特点，与书目或题录信息之 间在写作格型的叉爆等可有在汇进行这达，存间上学习到的识或模式不能很好地应用 在同义、多义以及近义等问题。 书目信息通常以几十或几百字为主，其文本长度与微博、</td><td>部分差异，使得分类器在训练集的特征空 特征稀疏，意味着训练集形成的特征空间与 测试集的特征空间各自只能提供少数的词参</td><td>特征扩展</td></tr><tr><td></td><td>博客等新兴媒体的文本特性相似，属于短文本类型，存在 特征稀疏、噪声大、主题特征不明显等不足。 TF、IDF是常用的最基本的统计量，是构建文本表示模型 的基本元素。在基于VSM或LDA等模型进行文本表示时,</td><td>入匹配，这既使分类器难以从训练集形成较 好的模式，也会降低两者匹配的可能性。 对文本中来自标题、摘要、正文、作者关键</td><td></td></tr><tr><td>特征重要程度 反映不足</td><td>TF、IDF 都是以文本或文本集合为单位进行统计，未考虑 不同文本的结构化特性，即未对标题、摘要、正文等不同 位置或词性的词在分类上的重要程度加以区分。</td><td>词等不同位置的词在重要程度上不加以区 分，意味着对书目信息、新兴媒体等文本的 结构化特性没有加以有效利用。</td><td>加权策略</td></tr></table></body></html>

# 2特征语义关联研究

特征语义关联主要包括特征扩展和特征语义转换两个方面，研究内容虽然不尽相同，但使用的关键技术比较相似。

# 2.1 主要研究

(1）特征扩展

特征扩展的目的是从有限的文本内容中寻获更多的语义表达，以扩大训练集或待分类文本各自的特征空间，使两者之间具备有更多共同特征的可能。

依据是否使用外部的第三方资源，特征扩展的方法主要有基于语料库内部语义关联的特征扩展方法和借助第三方资源的特征扩展方法，表2列举了所使用的资源以及该种方法下目前使用的主要技术。

基于语料库内部语义关联的特征扩展方法是直接通过建立训练集与待分类短文本之间的关联性，对待分类的短文本进行特征扩展。王细薇等[1-2]利用FP2Growth算法挖掘训练集特征项与测试集特征项之间的共现关系，将得到的关联规则对待分类的短文本中的特征项进行特征扩展；胡勇军等[3利用高频词建立训练集的特征空间，利用LDA模型将概率大于某一阈值的隐含主题对应的高频词扩展到待分类的短文本，以降低短文本的稀疏性影响。Vo等4将LDA建模所产生的隐含主题中的一部分分配给短文本，将这些隐含主题中的词扩展进短文本中。基于内部语义关联的特征扩展方法的关键是在不借助外部第三方资源的情况下如何挖掘训练集与待分类短文本之间隐含的内部语义关联，其中以共现为核心思想的关联规则实质上是通过两个词的共现来关联或限定语义，与LDA模型中由多个词形成的一个隐含主题来关联或限定语义在目的上相同，但后者关联或限定语义的程度更高。

表2特征扩展的基本方式  

<html><body><table><tr><td>特征扩展方法</td><td>使用的资源</td><td>主要技术</td></tr><tr><td rowspan="2">基于语料库内部语义关联 的特征扩展方法</td><td rowspan="2">训练集和测试集内部语义关联</td><td>关联规则</td></tr><tr><td>使用多元回归方法填补缺失值 LDA建模</td></tr><tr><td>借助第三方资源的特征 扩展方法</td><td>训练集和测试集并借助第三方资源，如维基百科、 《知网》、MEDLINE 数据库等</td><td>基于维基百科的概念相似度计算方法 基于《知网》的概念相似度计算方法 LDA建模</td></tr></table></body></html>

基于外部第三方资源的特征扩展是借助语义词典、维基百科等知识库或者互联网知识等第三方资源，对待分类的短文本进行特征扩展。宁亚辉等[5以领域高频词为特征词，借助《知网》及其词语之间的语义相似度计算方法将与高频词相似度较高的词也扩展成为特征；赵辉等%以维基百科词语相关概念集合为对象，通过计算并选取与语料库中特征在语义上高度相关的词作为特征扩展词集，对短文本进行特征扩展;

Phan 等利用LDA 概率主题模型，通过维基百科、MEDLINE医学数据库等第三方资源及其所反映的包括专业术语在内的词语相关概念对短文本进行扩展。基于第三方资源的特征扩展的关键是寻找合适的第三方资源，从中获得词语之间相似程度。

此外，在内部特征扩展的基础上，结合使用外部第三方资源也可以有效开展特征扩展。王盛等[8利用《知网》确定训练集中词语对的上下位关系，再将其用于扩展待分类文本的特征词，实验证明上下位关系能够改善短文本的分类性能。Fan等运用《知网》中的语义树挖掘语料库内的施事-受事(Agent-Patient)关系，从而提取词语对进行短文本的特征扩展。

# (2）特征语义转换

特征语义转换的目的是使训练集与测试集之间形成更多的共同特征空间。为实现这个目的，在人工智能领域开展了跨领域分类的研究，在信息管理领域，通过使用本体自建知识库等方式也开展了类似研究。各种代表性共同特征空间的类型、产生方式、特点、映射方式以及该种类型下目前使用的主要技术等如表3所示：

表3各种共同特征空间  

<html><body><table><tr><td rowspan="2">共同特征 空间的 种类</td><td colspan="2">共同特征空间的建立方式</td><td rowspan="2">映射的 方式</td><td rowspan="2">主要技术</td></tr><tr><td>途径</td><td>共同特征空间的特点</td></tr><tr><td rowspan="3">外部共同 特征空间</td><td>自建</td><td>利用训练集和测试集的各自特有特征、共有特征及其语义 关联新建一个特征空间作为共同特征空间 对训练集和测试集的特征首先进行扩展，利用扩展后的特 征及其语义关联新建一个特征空间作为共同特征空间</td><td></td><td>聚类技术(谱聚类) 聚类技术(协同聚类) 奇异值分解</td></tr><tr><td></td><td>自建基于本体的知识库，并将其中的概念及其概念空间看 作是共同特征空间 直接将维基百科等公开知识库中的概念及其概念空间看作</td><td>训练集和测试集 都转换、映射到概念相似度计算 此共同特征空间</td><td></td></tr><tr><td>特征空间 寻找并直接使用 是共同特征空间</td><td>合适的外部共同 直接将 SUMO等公开的本体知识库中的概念及其概念空间 看作是共同特征空间</td><td>进行文本表示</td><td>LDA建模 概念相似度计算</td></tr><tr><td>内部共同 特征空间</td><td>将训练集的特征 空间作为共同特 征空间</td><td>公开本体知识库并辅以WordNet等其他资源 利用隐含主题或借助第三方资源将测试集的特征转换为训 转换、映射到共PLSA、LDA 建模、 练集上的特征</td><td>将测试集的特征 同特征空间进行概念相似度计算 文本表示</td><td></td></tr></table></body></html>

大多数研究试图建立或直接使用一个语料库之外的外部共同特征空间、供训练集和测试集同时映射至此空间下，表示文本及实施分类。

在建立外部共同特征空间的相关研究中，Pan 等[10]提出直接在训练集和测试集之间进行特征映射的谱特征对齐(Spectral Feature Alignment, SFA)算法。该算法核心思想是从两个集合之间找到一些共有的特征(称为领域无关特征)，利用这些领域无关特征将两个集合中各自特有的特征(称为领域相关特征)映射起来。SFA通过对领域无关特征以及领域独有特征之间的共现性进行跨领域联合建模得到两类特征的共现矩阵，然后对该共现矩阵实施谱聚类的聚类技术，使相似的特征聚为一组，形成众多组的谱聚类特征。SFA 将训练集和测试集映射到由这多组聚类特征定义的共同特征空间中，从而使得传统分类算法可以直接用于分类器的学习和预测。在类似核心思想的研究中，Soundarya[11]将该方法应用于对分别属于训练集和测试集的两个意思相反的领域无关特征进行语义关联;Wang等[12]的研究特点在于，在从训练集和测试集之间寻找共有的特征之前，先使用特征扩展方法、通过维基百科将两个集合的现有特征加以扩大，另外，使用协同聚类的聚类技术构建共同特征空间；Xie 等[13]则是利用训练集的领域相关特征以及训练集与测试集之间的领域无关特征，使用多元回归方法填补测试集中缺失的特征，对测试集的特征加以扩展，得到两个集合的较大、较高维的共有特征空间，使用奇异值分解方法将此高维的共有特征空间映射到一组低维空间，其中的一个低维空间就将待分类文本与相似的训练集文本集合在一起。在此基础上，使用相似度加权计算的传统分类器方法决定待分类文本的所属类别。在信息管理领域，建立外部共同特征空间则不是使用语料库，而是将《中图法》学科分类体系或《农业科学叙词表》主题体系分别与本体相结合，构建综合性或专业性学科领域本体知识库[14-15]作为共同特征空间，将训练集和测试集的特征同时转换、映射到该共同特征空间，构建基于该本体知识库中的概念为维度的文本表示模型下的分类器。

在寻找并直接使用外部共同特征空间的相关研究中，Xiang 等[16将维基百科概念页面的文本集合进行LDA建模，得到词-隐含主题矩阵构成的外部共有特征空间，利用该矩阵将训练集和测试集的特征都转换、映射至隐含主题，使训练集和测试集可以利用隐含主题向量计算相似度，利用SVM分类算法构建分类器。在信息管理领域，马芳[17则直接使用SUMO公开本体知识库作为共同特征空间，采取与文献[14-15]类似的特征转换、映射以及分类过程；胡泽文等[18]与马芳[17的做法类似，但将WordNet同义词集与SUMO 本体概念相结合、进一步提高了特征语义关联的可能性。

也有一部分研究希望仅依靠语料库内部提供的数据就能构建训练集与测试集之间的内部共同特征空间。

Xue 等[19]基于概率隐含语义索引(ProbabilisticLatentSemanticIndexing，PLSI)提出将训练集和测试集统一到一个概率模型中来，以不同集合的共同隐含主题为桥梁建立训练集和测试集间的关系的思想；通过将两个集合同时分解到相同隐含主题及由此构建的共有特征空间上，就可以将所有的文本表达为以一组相同隐含主题为特征的特征向量，在此基础上，使用传统的分类算法构建分类器。在信息资源管理领域李湘东等[20]采用与Xue 等[19]类似的思想，不同之处在于使用更容易实现的LDA模型，并应用于多种文献类型的文本；刘怀亮等[21则是在向量空间模型下将训练集的特征空间作为内部共同特征空间，借助《知网》将测试集中的特征转换到训练集中的特征，构建基于训练集的特征为维度的文本表示模型下的分类器

# 2.2 关键技术

特征语义关联以及特征扩展等特征语义转换相关研究主要涉及以下关键技术：

(1）决定领域相关特征和领域无关特征的相关技术。比较简单的方法是共现频次，即将在训练集和测试集中同时出现过一定次数以上的特征作为领域相关特征，剩余的作为领域无关特征。比较复杂的是借鉴特征选取方法，例如，将互信息方法改造为判断一个特征与文本集合是否相关[10]，公式如下:

$$
\mathrm { I ( X ^ { i } ; D ) = \sum _ { d \in D } \sum _ { \mathrm { \bf ~ x } \in X ^ { i } , \mathrm { \bf ~ x } \neq 0 } \mathrm { p } ( \mathrm { x } , d ) l o g } _ { 2 } \Bigg ( \frac { \mathrm { p } ( \mathrm { \bf ~ x } , \mathrm { d } ) } { \mathrm { p } ( \mathrm { \bf ~ x } ) \mathrm { p } ( \mathrm { d } ) } \Bigg )
$$

其中，D是训练集或测试集文本集合， $\operatorname { I } ( \mathrm { X } ^ { \mathrm { i } } ; \mathrm { D } )$ 越小，则特征 $\boldsymbol { \mathrm { X } } ^ { \mathrm { i } }$ 与领域越无关；规定一个阈值，由此区分领域相关特征和领域无关特征。具体的次数或阈值取决于实验和经验。Bollegala等[22发现，规范化点互信息方法(NPMI)[23]能较好地判断一个特征 $\mathbf { x }$ 与文本集合是否相关，公式如下：

$$
\operatorname { s c o r e } ( \mathbf { x } ) = \operatorname* { m i n } ( \mathbf { N P M I } ( \mathbf { x } , \mathbf { S } ) , \mathbf { N P M I } ( \mathbf { x } , \mathbf { T } ) )
$$

$$
\mathrm { { N P M I } ( x , y ) = \log \left( { \frac { p ( x , y ) } { p ( x ) p ( y ) } } \right) \frac { 1 } { - \log ( p ( x , y ) ) } }
$$

其中， $\mathbf { x }$ 和y是两个文本集合S和 $\mathrm { \Delta T }$ 中的两个特征，依据特征积分scoreO的高低分别为训练集和测试集选取领域相关特征和领域无关特征。

(2）将相似特征聚为一组的相关技术。向量空间模型下开展特征语义转换研究，主要是解决领域无关特征和领域相关特征所形成的高维词-词共现矩阵下相似特征发现的问题。为此，聚类技术和矩阵降维是关键技术，例如谱聚类、协同聚类等聚类技术，以及矩阵的奇异值分解等方法。 $\mathrm { N g }$ 等[24介绍了一个标准的谱聚类算法,Dai等[25]提出了被广泛引用的CoCC协同聚类算法。

(3）利用知识库进行词或概念之间相似度计算方法。维基百科是一种结构化的语义知识库，概念页面既包含了对概念的解释内容，也包含了丰富的链接距离和类别等结构信息，如何利用这两种结构信息是基于维基百科的语义相似度计算的关键。WLM 算法[26]是目前被普遍用作计算维基百科概念间链接距离的方法。赵辉等[27提出基于最短路径值作为两个维基百科概念之间的类别距离计算公式，并综合链接距离和类别距离提出计算两个维基百科概念之间语义距离，即语义相似度的计算方法。

在《知网》知识库中，词语由义项表示，即一个词语可以表示为多个义项，而一个义项又由义原来表示。因此，两个词语之间的相似度可以转化为义原间的相似度计算。为此，吴健等[28]提出综合考虑义原之间的最短路径距离及义原层次深度的义原相似度计算方法，刘群等[29]提出将义项的相似度计算转化为义原间的相似度计算方法，孙建旺等[30]采用最大匹配的方法，将两个词语之间的相似度定义为各个义项组合中相似度的最大值，并提出计算公式。

利用自建基于本体的知识库进行概念相似度计算，比较简单的是直接通过分散在属性或实例中的同义词或近义词完成特征词与本体概念的映射，比较复杂的是需要进一步考虑特征、本体概念、本体属性以及训练集文本之间的共现关系，公式如下：

$$
{ \mathrm { W } } ( \mathrm { t , c } ) { = } \frac { \mathrm { t f } ( \mathrm { t , c } ) { \times } \mathrm { N } _ { \mathrm { a } } ( \mathrm { t , c } ) { \times } \mathrm { N } _ { \mathrm { b } } ( \mathrm { t , c } ) } { \sqrt { \mathrm { t f } ( \mathrm { t , c } ) { } ^ { 2 } \times \mathrm { N } _ { \mathrm { a } } ( \mathrm { t , c } ) { } ^ { 2 } \times \mathrm { N } _ { \mathrm { b } } ( \mathrm { t , c } ) { } ^ { 2 } } }
$$

其中， $\mathrm { W } ( \mathrm { t } , \mathrm { c } )$ 表示词向量空间中词语 $\mathfrak { t }$ 与本体概念c的相似度，tf(t,c)表示词语t与本体概念c在特征集合中共现的频次， $ { \mathrm { N _ { a } } } ( \mathrm { t , c ) }$ 表示词语t与本体概念c共现的文本数， $\mathrm { N _ { b } ( t , c ) }$ 表示词语 $\mathrm { \Delta t }$ 与本体概念c共现的概念实例数，分母为归一化因子。

(4)使用概率主题模型代替向量空间模型，从文本表示模型的层次或环节解决特征之间的语义问题。LDA是目前最具代表性且被广泛使用的概率主题模型。构建LDA模型的关键是隐含变量分布的推断，即获得目标文本的隐含主题分布0和特征-隐含主题分布$\phi$ ，以构建隐含主题-文本矩阵和特征-隐含主题矩阵。计算两个分布通常使用Griffiths 等31] 提出的Gibbs 抽样方法对相关参数进行推断，但张志飞等[32]简明易懂地描述了后验估计值的计算公式，孙世杰等[33]较好地解释了LDA模型中使用困惑度计算主题数的方法。

# 2.3 现有成果的水平及今后的发展方向

从文本表示模型、《知网》等公开知识库以及基于本体自建知识库三个方面概括现有成果的水平和今后的发展方向，如表4所示：

表4现有成果的水平和今后的发展方向  

<html><body><table><tr><td>现有成果</td><td>现有成果的水平</td><td>发展方向</td></tr><tr><td>文本表示 模型</td><td>目前的大多数研究仍然使用向量空间模型，使用LDA等进一步普及使用LDA 等概率主题模型，将VSM 模型 概率主题模型的研究、从文本表示环节解决特征语义关联的细粒度特征与LDA模型的粗粒度特征相结合来表示 问题的研究尚未普及；已用于特征语义转换及特征扩展。</td><td>文本。</td></tr><tr><td>《知网》维 基百科等公 开知识库</td><td>在同义词、近义词以及上下位关系等概念相似度计算方面 已有相当成果，但歧义词的计算尚不多见；使用单个知识 库较多，缺乏比较知识库之间的优劣，也缺乏联合使用; 已用于特征语义转换及特征扩展。</td><td>进一步应用并提高歧义词的区分能力，可以帮助转换或 扩展到更正确的特征；多个公开知识库在特征语义转换 中的功能或性能比较以及联合使用。</td></tr><tr><td>基于本体自 建知识库</td><td>相较于公开知识库，基于本体自建知识库的中文概念相似构建这种知识库并将其用于基于机器学习方法的自动分 度计算比较粗略；自建本体的知识库目前仅用于特征语义类，是信息资源领域开展书目信息自动分类研究的一个 转换。</td><td>关注本体构建自动化等相关研究领域的成果，应用相关 成果构建基于《中图法》等学科分类体系的本体知识库; 重要方向；与公开知识库结合使用，改进中文的概念或词 之间相似度计算；可以考虑将其用于特征扩展，特别是与 学科专业领域有关的书目信息的标题甚至摘要的扩展。</td></tr></table></body></html>

# 3加权策略研究

# 3.1 主要研究

在向量空间模型下，经过互信息、卡方或信息增益等特征选择方法选取的特征能够有效提高分类性能。但是无论哪一种特征选择方法，都是以文本或文本集合为单位选取特征，没有进一步细化考虑结构化文本中在标题、摘要、作者关键词等不同位置出现的词对分类的作用会有所不同等问题。在LDA模型下,Bischof等[34针对隐含主题下哪些词更能代表该主题开展研究并给出排序，说明不同的词对表达隐含主题的作用有所不同，因此，不同的词通过隐含主题对分类的作用也需要区别对待。为此，在两种模型下分类时，都开展了加权策略研究。

目前的加权策略主要有利用文本体例结构进行加权或者利用特征项分布特性进行加权。各种代表性加权方式、文本表示模型及其该模型的基本技术、该种加权方式下使用的主要技术等如表5所示：

表5加权策略的主要方式及相关技术  

<html><body><table><tr><td>加权方式</td><td>文本表示 模型</td><td>基本技术</td><td>主要技术</td></tr><tr><td>文本体 例结构</td><td>VSM</td><td>TF-IDF</td><td>同一个词在结构化文本中 的不同位置，赋予不同权重</td></tr><tr><td>特征项</td><td>LDA VSM</td><td>Gibbs 抽样 TF-IDF</td><td>类别内及类别间的分布赋予</td></tr><tr><td>分布特性</td><td></td><td></td><td>不同权重</td></tr><tr><td></td><td>LDA</td><td>Gibbs抽样</td><td>尚无研究成果</td></tr></table></body></html>

(1）利用文本体例结构进行加权的方法认为，针对新闻、书目信息等特定类型的语料，处于标题、摘要、作者关键词或正文等不同位置的特征词对文章具有不同的贡献度，因此，需要根据位置信息赋予特征词不同权值。王昊等[35选取期刊题录信息作为实验材料，在向量空间模型下，为处于标题、摘要和关键词等不同位置的特征词设置不同权值，实验结果表明考虑了特征来源的方法具有更好的分类效果。李湘东等[36]将基于文本体例结构的加权策略运用于书目信息的文本分类，在点互信息的基础上，结合词性、位置等要素修正特征词的权重并扩展至LDA的模型中。

(2)利用特征项分布特性进行加权主要考虑的是特征项的分布特性。Lertantree 等[7通过改进 TF-IDF模型，根据在类别中单词的分布区别，提出多种不同的特征词权重表示方法；蒋健[38在此基础上，提出类间集中度、类内分散度等考虑在各个类别间的分布情况赋予权重的加权策略，

# 3.2 关键技术

加权策略研究主要涉及对TF-IDF公式的重复利用或改造、Gibbs抽样公式的改造等关键技术。

针对向量空间模型下利用文本体例结构进行加权时，书目信息中所包含的题名、作者关键词以及摘要等三项内容，分别形成三个语料库，在各自语料库内计算每一个特征词的权重，其利用的都是经典的TF-IDF作为权重计算方法[39]，公式如下：

$$
\mathrm { W T } ( \mathbf { w _ { i j } } ) = \mathrm { T F } ( \mathbf { w _ { i } } ) \times \mathrm { I D F } ( \mathbf { w _ { i } } ) = \mathrm { t f _ { i j } } \times \log \left( { \frac { \mathbf { n } } { \mathbf { n _ { i } } + \mathbf { \alpha } \alpha } } \right)
$$

其中， $\mathrm { { T F } ( w _ { i } ) }$ 表示特征 $\mathbf { w } _ { \mathrm { i } }$ 在文档 $\mathrm { ~ j ~ }$ 中出现的次数，用 $\mathrm { t f _ { i j } }$ 计算； $\mathrm { { I D F } ( w _ { i } ) }$ 表示特征 $\mathbf { w } _ { \mathrm { i } }$ 的逆文档频率,用 $\log \left( { \frac { \mathfrak { n } } { \mathfrak { n } _ { \mathrm { i } } + \mathfrak { a } } } \right)$ 计算。 $\mathfrak { n }$ 为文档总数, $\mathbf { n } _ { \mathrm { i } }$ 为包含特征 $\mathbf { t } _ { \mathrm { i } }$ 的文档数， $\alpha$ 为调节因子。

因此，书目信息中的一个特征可能最多在上述三个语料库中重复利用公式(5)分别计算出三个权值，这三个权值在将包含有题名、作者关键词以及摘要的书目信息作为一个完整的文本形成的语料库中，用来计算该特征的最终权值。计算的关键是如何在最终权值中按比例分配这三个权值。王昊等[35根据实验结果将特征比例确定为3:5:2，即将上述三个权值分别乘以系数0.3、0.5和0.2后相加。

针对LDA模型下利用文本体例结构进行加权时，在 Griffiths 等[31]提出的 Gibbs 抽样公式的基础上，可以利用特征词与文本的点互信息 $\mathrm { P M I } ^ { [ 4 0 ] }$ 对其公式进行修正如下：

$$
\mathrm { p ( z _ { i } = k | z _ { - i } , w , \alpha , \beta ) \propto \mathrm { p ( z _ { i } = k , w _ { i } = t | z _ { - i } , w _ { - i } , \alpha , \alpha , \beta ) } }
$$

$$
\propto \frac { \mathrm { w e i g h t ( t , d ) n _ { k , - i } ^ { ( t ) } } + \beta _ { t } } { \sum _ { \mathrm { t = 1 } } ^ { \mathrm { V } } ( \mathrm { w e i g h t ( t , d ) n _ { k , - i } ^ { ( t ) } } + \beta _ { t } ) } \cdot \frac { \mathrm { w e i g h t ( t , d ) n _ { m , - i } ^ { ( k ) } } + \alpha _ { k } } { \sum _ { \mathrm { k = 1 } } ^ { \mathrm { K } } ( \mathrm { w e i g h t ( t , d ) n _ { m , - i } ^ { ( k ) } } + \alpha _ { k } ) } \binom { k } { m } ,
$$

$$
\mathrm { w e i g h t } ( \mathrm { t } = \mathrm { w } _ { \mathrm { i } } , \mathrm { d } ) = \mathrm { P M I } ( \mathrm { w } _ { \mathrm { i } } , \mathrm { d } ) = \sum _ { \mathrm { j } = 1 } ^ { 3 } { \boldsymbol { \lambda } } \cdot \mathbf { \mu } _ { \mathrm { j } } \cdot \mathrm { P M I } ( \mathrm { w } _ { \mathrm { i } } ) _ { \mathrm { j } }
$$

其中， $\mu _ { \mathrm { j } }$ 和 $\lambda$ 为特征词权重的调节因子， $\mu _ { \mathrm { j } } ( \mathrm { j } { = } 1$ 2,3)为特征词的位置权重，且满足条件μ >μ>μ,$\sum \limits _ { j = 1 } ^ { 3 } \mu _ { \mathrm { j } } = 1$ 。考虑特征词的位置因素进行权重调整，使得处于文本不同位置的特征词在文本表示能力上的差异得以体现，也提高了PMI模型的特征选择效率。另外，实词相对于虚词对文本具有更强的描述能力，因此文本中的特征词若为实词时，设定 $\lambda { = } 1$ ；若为虚词时，设定 $\lambda { = } 0 . 7$ ，以区分不同词性特征词对文本表示能力上的差异。

针对向量空间模型下利用特征项分布特性进行加权时，蒋健[38提出改进的TF-IDF计算公式如下：

$$
\mathrm { W T _ { T F - I D F - C D _ { \mathrm { m a x } } } ( w ) = T F ( w _ { i } ) \times I D F ( w _ { i } ) \times m a x _ { i = 1 } \left\{ C D ( C _ { i } , w ) D D ( C _ { i } , w ) \right\} }
$$

$$
\mathrm { C D } ( \mathrm { C } _ { \mathrm { i } } , \mathrm { w } ) { = } \frac { \mathrm { d f } _ { \mathrm { i } } ( \mathrm { w } ) } { \sum _ { \mathrm { i } = 1 } ^ { \mathrm { m } } \mathrm { d f } _ { \mathrm { i } } ( \mathrm { w } ) }
$$

$$
\mathrm { D D } ( \mathrm { C } _ { \mathrm { i } } , \mathrm { w } ) = \frac { \mathrm { d f } _ { \mathrm { i } } ( \mathrm { w } ) } { \left| \mathrm { C } _ { \mathrm { i } } \right| }
$$

其中， $\mathrm { d f _ { i } }$ (w)表示特征 $\mathbf { w }$ 在 $\mathrm { C _ { i } }$ 类内出现的文档频次， $\textstyle \sum _ { \mathrm { i = 1 } } ^ { \mathrm { m } } \mathrm { d f _ { i } } ( \mathbf { w } )$ 表示特征w在所有类内出现的总文档数， $\left| \mathrm { C _ { i } } \right|$ 表示文档集中 $\mathrm { { C _ { i } } }$ 类的总文档数。公式(9)表示特征 $\mathbf { w }$ 对于类 $\mathrm { C _ { i } }$ 的集中度，若其值越大表示该特征越集中地出现在该类中；公式(10)表示特征w 对于类 $\mathrm { { C _ { i } } }$ 的分散度，若其值越大表示该特征在 $\mathrm { { C _ { i } } }$ 中分布得越均匀。 $\mathrm { \ m a x _ { i = 1 } \left\{ C D ( C _ { i } , w ) D D ( C _ { i } , w ) \right\} }$ 表示 $\mathrm { T F - I D F - C D } _ { \operatorname* { m a x } }$ （204号方法所有的CD值中，取特征 $\mathbf { w }$ 在各个类的CD值中最大的一个。

# 3.3 现有成果的水平及今后的发展方向

不管是利用文本体例结构进行加权还是利用特征项分布特性进行加权，加权策略主要是对VSM、LDA模型中的基本公式进行改造。改造的主要途径包括：特征的位置、词性，特征与文本、特征与类别的相关关系，改造的主要方式是将改造途径中所反映的特征重要程度以系数的形式加入到模型的基本公式中。

目前，运用于文本分类的加权策略研究大多基于向量空间模型，而且一般只考虑利用文本体例结构进行加权和利用特征项分布特性进行加权等两种方式中的某一种加权策略，结合两种加权策略的研究是一个重要的努力方向。

在LDA模型下已经开始有利用文本体例结构进行加权的研究，但数量不多、有待加强；在LDA模型下利用特征项分布特性进行加权则是一个有待开拓研究方向。

# 4结语

本文在特征语义转换和特征扩展等特征语义关联方面，或者在加权策略方面对文本自动分类进行了比较深入和细致的研究，提出了属于特征选择方法研究范围之外，但影响书目信息、新兴媒体等文本的分类性能的相关问题和有效的解决办法。由于使用的语料库、结果的评价方式各不相同，难以对这些研究进行横向比较。但是，这些研究在各自研究的范围内，均与改进前的方法在分类结果上做出比较，验证了其在分类性能上的改进或提高程度，说明了这些研究对文本自动分类研究的有效性及其贡献。针对现有研究中概率主题模型使用不多、基于本体和学科分类体系自建知识库的自动化构建及概念相似度计算方法不足、加权策略单一等问题，今后的研究可以从向量空间模型与概率主题模型结合使用、利用各种知识库提高概念相似度计算能力、结合多种加权策略构建复合加权策略等方向展开。

# 参考文献：

[1] 王细薇，樊兴华，赵军．一种基于特征扩展的中文短文本 分类方法[J]．计算机应用，2009，29(3):843-845.（Wang Xiwei,Fan Xinghua,Zhao Jun.Method for Chinese Short Text Classification Based on Feature Extension [J]. Journal of Computer Applications,2009,29(3):843-845.) [2] 王细薇，张凯．一种改进的基于共现关系的短文本特征扩 展算法研究[J]．河南城建学院学报，2012，21(4)：48-50. (Wang Xiwei,Zhang Kai.Improved Expansion Algorithm Based on Co-occurrence Relationship Between Short Text Feature[J].Journal of Henan University of Urban Construction,2012,21(4):48-50.) [3] 胡勇军，江嘉欣，常会友．基于LDA 高频词扩展的中文短 文本分类[J]．现代图书情报技术，2013(6)：42-48.(Hu Yongjun,Jiang Jiaxin,Chang Huiyou．A New Method of Keywords Extraction for Chinese Short-Text Classification [J].New Technology of Library and Information Service,   
2013(6):42-48.) [4] Vo D T,Ock C Y. Learning to Classify Short Text from Scientific Documents Using Topic Models with Various Types of Knowledge [J]. Expert Systems with Applications,2015,   
42(3): 1684-1698. [5]宁亚辉，樊兴华，吴渝．基于领域词语本体的短文本分类 [J]．计算机科学，2009,36(3):142-145.(Ning Yahui,Fan Xinghua,Wu Yu.Short Text Classification Based on Domain Word Ontology [J]. Computer Science，2009，36(3): 142- 145.)   
[6]赵辉，刘怀亮．一种基于维基百科的中文短文本分类算法 [J]．图书情报工作,2013,57(11):120-124.(Zhao Hui,Liu Huailiang.Classification Algorithm of Chinese Short Texts Based on Wikipedia [J].Library and Information Service, 2013,57(11): 120-124.)   
[7]Phan X H,Nguyen L M,Horiguchi S. Learning to Classify Short and Sparse Text & Web with Hidden Topics from Large-scale Data Collections[C]. In: Proceedings of the 17th International Conference on World Wide Web.ACM,2008.   
[8]王盛，樊兴华，陈现麟.利用上下位关系的中文短文本分类 [J]．计算机应用,2010,30(3):603-607.(Wang Sheng,Fan Xinghua,Chen Xianlin.Chinese Short Text Classification Based on Hyponymy Relation [J].Journal of Computer Applications,2010,30(3): 603-607.)   
[9]Fan X,Wei D.A Method of Agent and Patient Relation Acquisition for Short-Text Classification [A].// Advanced Research on Computer Science and Information Engineering [M]. Springer Berlin Heidelberg,2011.   
[10] Pan S J,Ni X,Sun J T,et al.Cross-domain Sentiment Classification via Spectral Feature Alignment [C].In: Proceedings of the 19th International Conference on World Wide Web.ACM,2010.   
[11]SoundaryaR. Sentiment ClassificationforDomain Adaptation Using Cross Domains [C]. In: Proceedings of the 2015 International Conference on Futuristic Trendsin Computing and Communication,Chennai, Tamilnadu, India. 2015.   
[12]Wang P, Domeniconi C，Hu J. Cross-DomainText Classification Using Wikipedia [J].IEEE Intelligent Informatics Bulletin,2008,9(1): 5-17.   
[13] Xie S,Fan W,Peng J,et al.Latent Space Domain Transfer Between High Dimensional Overlapping Distributions[C]. In: Proceedings of the 18th International Conference on World Wide Web,NewYork,NY,USA.ACM,2009.   
[14]马范玲，胡泽文．基于 SUMO 本体的图书自动分类模型研 究[J]．情报杂志，2011，30(1):168-173.(Ma Fanling，Hu Zewen.The Research on Automatic Library Classification Model Based on SUMO Ontology[J]. Journal of Intelligence, 2011, 30(1): 168-173.)   
[15] 朱平，范少辉,岳永德．一种集成本体和 SVM的文本分类 方法[J]．江西理工大学学报,2012,33(1):68-72.(Zhu Ping, Fan Shaohui,Yue Yongde.A Text ClassificationMethod IntegratingOntology and SVM [J]. Journal of Jiangxi University of Science and Technology,2012,33(1): 68-72.)   
[16] Xiang E W, Cao B,Hu D H,et al. Bridging Domains Using World Wide Knowledge for Transfer Learning [J].IEEE Transactions on Knowledge and Data Engineering, 2010, 22(6): 770-783.   
[17]马芳．基于 SUMO 本体的中文文本自动分类研究[J]．情报 科学,2015,33(6):43-47.(Ma Fang.Research on Chinese Text Automatic Classification Based on SUMO Ontology [J]. Information Science,2015,33(6): 43-47.)   
[18] 胡泽文，王效岳，白如江．基于 SUMO 和 WordNet 本体集 成的文本分类模型研究[J]．现代图书情报技术，2011(1): 31-38.(Hu Zewen,Wang Xiaoyue, Bai Rujiang. Study on Text Classification Model Based on SUMO and WordNet Ontology Integration [J]. New Technology of Library and Information Service, 2011(1): 31-38.)   
[19] Xue G, Dai W, Yang Q，et al. Topic-bridged PLSA for Cross-domain Text Classification[C]. In: Proceedings of the 31st Annual International ACM SIGIR Conference on Research and Development in Information Retrieval.ACM, 627-634.   
[20] 李湘东，胡逸泉，黄莉．采用 LDA 主题模型的多种类型文 献混合自动分类研究[J]．图书馆论坛，2015，35(1):74-80. (Li Xiangdong,Hu Yiquan,Huang Li.A Study of Mixed Automatic Categorization of Multi-type Document Adopting LDA Model [J].Library Tribune,2015,35(1): 74-80.)   
[21] 刘怀亮，杜坤，秦春秀．基于知网语义相似度的中文文本 分类研究[J]．现代图书情报技术，2015(2)：39-45.(Liu Huailiang,Du Kun,Qin Chunxiu.Research on Chinese Text Categorization Based on Semantic Similarity of HowNet[J]. New Technology of Library and Information Service, 2015(2): 39-45.)   
[22]Bollegala D,Maehara T,Kawarabayashi K.Unsupervised Cross-Domain Word Representation Learning [C]. In: Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing, Beijing, China. 2015.   
[23] Bouma G. Normalized (Pointwsie） Mutual Information in Collocation Extraction [C].In: Proceedings of the Bi-Annual Conference of the German Society for Computational Linguistics and Language Technology.2009.   
[24] Ng A Y, Jordan M,Weiss Y.On Spectral Clustering: Analysis and an Algorithm [C].In: Proceedings of the 2011 Annual Conference on Neural Information Processing Systems, Vancouver, British Columbia,Canada.2001.   
[25] Dai W，Xue G R，Yang Q，et al. Co-clustering Based Classification for Out-of-Domain Documents[C]. In: Proceedings of the 13th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. 2007.   
[26] Milne D,Witten I H.An Effective,Low-Cost Measure of Semantic Relatedness Obtained from Wikipedia Links[C]. In: Proceeding of AAAI Workshop on Wikipedia and Artificial Intelligence: An Evolving Synergy. AAAI Press,2008.   
[27］赵辉，刘怀亮．面向社区问答的中文短文本分类算法研究 [J]．现代情报，2013，33(10):70-74.(ZhaoHui,Liu Huailiang.Research on Chinese Short Text Classification Algorithm for Community-Based Q&A [J]. Journal of Modern Information,2013,33(10): 70-74.)   
[28] 吴健，吴朝晖，李莹，等．基于本体论和词汇语义相似度 的 Web 服务发现[J]．计算机学报，2005，28(4)：595-602. (Wu Jian, Wu Zhaohui,Li Ying,etal. Web Service Discovery Based on Ontology and Similarity of Words [J].Chinese Journal of Computers,2005,28(4): 595-602.)   
[29] 刘群,李素建．基于《知网》的词汇语义相似度计算[J]．计 算语言学及中文语言处理,2002,7(2):59-76.(Liu Qun,Li Sujian. Word Similarity Computating Based on How-Net [J]. Computational Linguistics and Chinese Language Processing, 2002, 7(2): 59-76.)   
[30]孙建旺，吕学强，张雷瀚．基于语义与最大匹配度的短文 本分类研究[J]．计算机工程与设计，2013，34(10): 3613-3618.(Sun Jianwang,Lv Xueqiang， Zhang Leihan. Short Text Classification Based on Semantics and Maximum Matching Degree [J]. Computer Enginering and Design, 2013,34(10): 3613-3618.)   
[31]Griffiths T L，Steyvers M.Finding Scientific Topics[J]. Proceedings of the National Academy of Sciences of the United States of America,2004,101(S1): 5228-5235.   
[32] 张志飞，苗夺谦，高灿.基于 LDA 主题模型的短文本分类 方法[J]．计算机应用，2013，33(6):1587-1590.（Zhang Zhifei,Miao Duoqian,Gao Can.Short Text Clasification Using Latent Dirichlet Allocation [J]. Journal of Computer Applications,2013,33(6):1587-1590.)   
[33]孙世杰，濮建忠.基于LDA 模型的 Twitter中文微博热点主 题词组发现[J]．洛阳师范学院学报，2012,31(11)：60-64. (Sun Shijie,Pu Jianzhong.A Hot Topic Phrase Selection Based on LDA for Chinese Tweets [J]. Journal of Luoyang Normal University,2012,31(11): 60-64.)   
[34]Bischof JM,Airoldi E M. Summarizing Topical Content with Word Frequency and Exclusivity[C].In: Proceedings of the 29th International Conference on Machine Learning.2012.   
[35]王昊，叶鹏，邓三鸿.机器学习在中文期刊论文自动分类研 究中的应用[J].现代图书情报技术，2014(3)：80-87.(Wang Hao,Ye Peng,Deng Sanhong.Machine Learning Application in Chinese Journal Articles Automatic Classification[J].New Technology of Library and Information Service,2014(3): 80-87.)   
[36]李湘东，巴志超，黄莉.一种基于加权 LDA 模型和多粒度 的文本特征选择方法[J].现代图书情报技术，2015(5): 42-48.(Li Xiangdong,Ba Zhichao,Huang Li.A Text Feature Selection Method Based on Weighted Latent Dirichlet Allocation and Multi-granularity [J]. New Technology of Library and Information Service,2015(5):42-48.)   
[37]Lertantree V,Theeramunkong T.Effect of Term Distributions on Centroid-based Text Categorization [J]. Information Sciences,2004,158(1): 89-115.   
[38] 蒋健．文本分类中特征提取和特征加权方法研究[D]．重 庆：重庆大学,2010.(Jiang Jian.Text Classification in the Feature Extraction and Feature Weighting Method Research [D]. Chongqing: Chongqing University, 2010.)   
[39]Salton G,Yang C S.On the Specification of Term Values in Automatic Indexing [J].Journal of Documentation,1973,29 (4): 351-372.   
[40]Peter A C,Brett WB,Stephen H,et al．An InformationTheoretic,Vector-Space-Model Approach to Cross-Language Information Retrieval [J]. Journal of Natural Language Engineering,2011,17(1):37-70.

# 作者贡献声明：

李湘东：提出研究课题和思路，阅读整理文献，论文最终版修订;  
巴志超：阅读整理文献，起草论文;  
高凡：文献调研、阅读和整理。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。  
[1]李湘东，巴志超，高凡．原始数据-参考文献全文链接.xlsx.  
本文参考文献.

收稿日期:2016-01-22   
收修改稿日期:2016-06-19

# Review of Digital Documents Automatic Classification Research

Li Xiangdong1,²Ba Zhichao1,3Gao Fan' 1(School of Information Management, Wuhan University, Wuhan 430072, China)   
2(Center for the Studies of Information Resources,Wuhan University, Wuhan 430072, China)   
3(Information Research Institute of Shandong Academy of Sciences Ji'nan 25o014, China)

Abstract: [Objective]This paper discusss the existing issues and possible solutions to the automatic classification of digital documents (i.e.library bibliographies,news pages and social media posts).[Coverage] We reviewed literature onthe feature semantics conversion，feature expansion and weighting strategy from the field of Automatic Classification basedon machine learing.[Methods] We analyzed the leading studies,key technologies，current achievements,and future directions from the published articles.[Results] Our research found the limits of previous studies onsemantic representation of texts and utilization of knowledge bases.[Limitations] We did not discuss the classification algorithms.[Conclusions]To improve the efectiveness of automatic classfication of digital documents, future research could try to combine Vector Space Model with Probabilistic Topic Model,use the knowledge base to improve the concept similarity computing, as wellas construct composite weighted strategy.

Keywords: Automatic classificationFeature semantic asociation Feature semantic conversionFeature expansion Weighting strategy

# EBSCO有声读物的新功能为图书馆带来更好的用户体验

EBSCO 信息服务改进了其有声读物的用户体验，添加了新设计和新功能，为图书馆读者提供了更好的聆听体验。此外，EBSCO 有声读物还提供了一个新的 APP,为用户提供更多的读物选择、改进的交付系统，以及一个新的、易于使用的设计界面。

通过和全球数字内容交付领头羊Findaway的合作,EBSCO有声读物提供了从移动设备直接访问有声读物的功能。凭借简化的工作流和一个有趣的、直观的设计,EBSCO有声读物快速简易的搜索功能，配合其新的APP,使得在线聆听变得更加容易。APP 允许图书馆用户从他们的图书馆馆藏中直接下载有声读物到他们的设备上并开始试听。和Findaway的合作还将EBSCO 有声读物的范围扩大至 5000多个条目，这将吸引广大的图书馆读者，包括休闲读者、研究人员、语言学习者、中小学生、视障读者和极客。EBSCO 的馆藏建设者和馆员们为学术界、公共图书馆、中小学校和企业图书馆创建了几个新的有声读物资源库，包括获奖读物库、流行小说库和畅销书库。

通过EBSCO新的简易采购模型来采购一本 EBSCO有声读物是非常简单的。所有的有声读物都可以在 EBSCOhost馆藏管理平台上通过单用户永久访问模型进行购买。EBSCO 有声读物的身份验证方法包括个人用户身份验证和 SSO身份验证。从而提供对有声读物的安全访问。

(编译自:htps://ww.ebsco.com/news-center/press-releases/ebsc-audiobooks-ne-design-and-features-create-an-enhanceduser-experience)

(本刊讯)