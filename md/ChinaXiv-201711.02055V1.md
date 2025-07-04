# 面向微博话题的“主题+观点"词条抽取算法研究

# 姚兆旭 马静

(南京航空航天大学经济与管理学院南京 211106)

摘要：【目的】自动抽取微博话题信息，从主题及观点两个维度整合揭示微博话题内容与观点。【方法】将主题模型应用于微博话题中，结合改进的 TF-IDF 算法，构建主题特征词向量；基于特征词向量中特征词之间的相关度，自动抽取主题词汇链；引入情感词典，抽取主题观点，无监督构建"主题 $\cdot +$ 观点"词条。【结果】使用爬虫工具抽取2014年6月-2015年6月期间4个特定热门微博话题事件的微博共24598条，抽取"主题 $\cdot +$ 观点"词条，平均准确率达到 $80 . 3 \%$ ，召回率为 $7 6 . 7 \%$ 。【局限】数据量依旧较小，主题模型对于微博短文本的特征抽取效果仍需提高。【结论】本文算法可以准确且有效地描述话题事件内容及其相应观点。

关键词：文本挖掘 词条抽取 主题模型微博话题分类号：TP391 G350

# 1引言

随着互联网的普及与发展，博客、微博和社交网络等网络平台成为网民获取信息的重要来源。截至2015 年6月，中国网民规模达6.68亿[1]，微博用户规模为2.49亿，其中有 $6 4 . 6 \%$ 的用户参与过热门话题讨论[2]。由此可见，微博社区已成为重要的舆情传播平台，其中微博话题已成为用户针对话题事件获取信息、表达观点的重要渠道。但是由于微博话题中信息鱼龙混杂以及微博自身短文本、结构松散的特性，因此迫切需要一种合适的组织模式或框架，帮助用户在信息过载时迅速抽取与表达微博话题信息，多维度展现舆情内容。

话题信息的抽取与表达可以追溯到话题识别与跟踪(Topic Detection and Tracking，TDT)的话题检测阶段，话题检测的主要任务[3是检测和组织话题，通常用于应对信息过载问题。近年来国内外关于话题信息抽取方法的研究主要从数据挖掘方法与NLP文本挖掘方法两方面切入。数据挖掘方法主要从结构化、半结构化数据中抽取信息。Becker等[4]利用Twitter一段时间内的历史数据，通过聚类算法获得事件簇，提取事件簇特征，并利用支持向量机模型在线识别新文本。Popescu等[5针对某一类特定产品的评论信息，通过计算评论中的名词与该类产品表征词间的点互信息(PMI)，使用贝叶斯分类来提取产品特征。NLP文本挖掘方法从非结构化的开放文本中发现新知识，并将其转换为可理解的有用信息。Rttier等[针对Twitter自身特性，提出开放领域事件抽取方法，利用潜在变分模型发现重要的事件类别。然而，由于微博话题文本相较于传统文本内容简短、结构松散、数据稀疏性严重，因此传统的文本抽取方法并不适用于微博话题文本。

随着主题模型的提出，为了解决上述方法存在的问题，越来越多的学者将LDA模型引人到话题抽取与表达的研究中。LDA模型是三层贝叶斯分布的概率模型，将话题中隐含主题信息通过特征词概率分布来表示。为进一步提升模型适用性与话题抽取效果，有学者在传统LDA模型基础上引入情感因素[8]、话题热度[9]、作者信息[10]、微博间用户关系[11]等外部因素，进行微博短文本研究，并取得良好效果。目前基于主题模型的话题信息抽取与表达主要从话题标签抽取[12]、话题线索化[13]、话题演化[14]等方面进行研究。寇宛秋等[12]提出一种基于种子词的话题标签抽取方法，对话题特征词权重重排序，抽取种子词，采用 Bootstrapping思想，生成关键短语集合，最后泛化选择话题标签，表述话题内容。Ramage 等[15]针对 Twitter 中博文的内容特征，利用标签 LDA(Labeled LDA)模型将博文内容映射到4个维度，抽取标签，反映话题信息。Darling等[提出 PoSLDA 模型，在LDA 模型和HMMLDA模型的基础上进一步扩展，将文档中的词汇分为三个类别(形容词、动词和名词)表示话题涉及的事物、动作和描述信息。闫泽华[17]在LDA模型基础上，调整单词权重，考虑背景词与N元短语的因素，抽取新闻线索标签。这些研究都是从话题内容方面抽取话题信息,并没有考虑引入观点维度改善微博话题信息抽取与表达，更加全面展现话题信息。

为了进一步提升话题信息抽取与表达效果，本文设计面向微博话题的“主题 $+$ 观点"表达模型，并提出一种无监督的“主题 $+$ 观点"词条抽取算法。实验结果表明本文算法在不同微博话题中均取得较好的效果，从多维度反映微博话题中各主题信息及主题观点。

# 2面向微博话题的"主题 $+$ 观点"词条模型

微博话题的微博语义信息可以分为两类：话题事件的客观描述信息与主观观点信息。本文综合微博话题自身特性，提出面向微博话题的“主题 $^ +$ 观点"词条的话题表达模型，“主题 $\cdot +$ 观点"词条由主题词汇链与主题观点两部分组成，主题词汇链以词汇链的形式表征微博话题中各主题事件内容信息，主题观点反映用户对主题事件的观点倾向。

定义1主题词汇链Lexicalchain $\{ \boldsymbol { \mathrm { k } } _ { \mathrm { n } } \}$ 由一组具有代表性的单词或者短语组成，根据特征词集合中词汇的相关性 $\mathrm { c o r } ( \mathrm { w } _ { \mathrm { i } } , \mathrm { w } _ { \mathrm { j } } )$ 自动构建生成，用以表征微博话题中主题事件的内容信息

定义2主题观点Viewpoint $\{ \boldsymbol { \mathrm { j _ { n } } } \}$ 是代表主题 $z _ { \mathrm { i } }$ 观点信息的观点词，反映网民对主题事件的观点意见。

定义3“主题 $^ +$ 观点"词条Entry(n)表示从主题内容与主题观点两个维度揭示话题信息，由主题词汇链Lexicalchain $\{ \boldsymbol { \mathrm { k } } _ { \mathrm { n } } \}$ 与主题观点Viewpoint $\{ \boldsymbol { \mathrm { j _ { n } } } \}$ 构成，模型结构如下所示：

$$
\mathrm { E n t r y ( n ) } = \mathrm { L e x i c a l c h a i n \{ k _ { n } \} } + \mathrm { V i e w p o i n t \{ j _ { n } \} } \quad \mathrm { n = 1 , 2 , \cdots , K }
$$

其中，主题词汇链Lexicalchain $\{ \boldsymbol { \mathbf { k } } _ { \mathrm { n } } \}$ 表示第 $\mathfrak { n }$ 个主题 $z _ { \mathrm { n } }$ 的主题词汇链，主题观点Viewpoint{jn}表示对应主题信息的观点信息，K表示主题数目。

# 3无监督的"主题 $^ +$ 观点"词条抽取算法

当前针对话题信息抽取的普遍解决思路是有监督、半监督或无监督的文本挖掘方法。有监督方法仅具理论价值，因为实际应用中难以拟出合适的训练集构建分类器。本体作为一种有效的形式语义模型和知识表示形式，近年来在话题抽取方面也有一定应用，但构建话题相关本体往往采用半监督方式，需要引入大量领域信息，准确度不高，多为原型系统，未能走向应用[18]。然而无监督探测算法则兼具较少先验需求与较强泛化能力，更符合话题抽取的实际情境。

本文提出一种无监督的微博话题信息抽取算法，主要分为以下三步:

(1）根据主题特征词在话题中不同主题间代表度的差异，调整特征词权重，构建主题特征词向量;(2）在特征词向量的基础上，依照特征词之间相关度，无监督生成主题词汇链表征主题内容信息;(3）引入情感词典，构建观点词集合，结合步骤(2)中主题词汇链与观点词的观点强度，自动抽取主题观点，用以描摹主题事件观点倾向。最终主题词汇链与主题观点构成“主题 $\cdot +$ 观点"词条，将微博话题信息从文本维度降维表示，从主题事件内容与观点的维度描述话题信息。

# 3.1基于改进TF-IDF算法的主题特征词向量构建

在LDA主题模型中，通过降维将话题信息从海量文本空间变换到主题空间，将一组词汇的概率分布表示话题中一个主题(Topic)，即通过一组特征词描述话题中一个主题事件。假设话题文本集合$\mathbf { D } = \{ \mathbf { d } _ { 1 } , \mathbf { d } _ { 2 } , \cdots \mathbf { d } _ { \mathrm { n } } \}$ ，其中 $\mathbf { V } = \{ \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \cdots \mathbf { w } _ { \mathrm { n } } \}$ 为词汇集合，潜在主题事件集合为 $Z = \{ \mathbf { z } _ { 1 } , \mathbf { z } _ { 2 } , \cdots \mathbf { z } _ { \mathrm { n } } \}$ ，主题建模后得到主题-词概率分布θ与文档主题概率分布 $\boldsymbol { \Phi }$ ，其中 $\mathsf { p } ( \mathrm { w } _ { \mathrm { j } } \vert \mathrm { z } _ { \mathrm { k } } )$ 表示在主题 $z _ { \mathrm { k } }$ 下词汇 $\mathbf { w _ { j } }$ 对主题的贡献度，即 $\mathbf { w _ { j } }$ 属于主题 $z _ { \mathrm { k } }$ 的概率。

LDA模型假设每个词汇权重相同，但实际上每个词汇在各个主题中代表度并不相同。传统词汇代表度的计算通常使用TF-IDF算法，但TF-IDF存在无法有效识别高频关键词与无法筛选均匀分布的关键词的问题，本文借鉴文献[12]的思想，在传统TF-IDF 算法基础上引入覆盖度与特征度，使主题特征词与背景词区分出来。

覆盖度coverage $_ { \mathrm { i , j } }$ 表示词汇在文档集合上的覆盖程度，覆盖度高的词语在语料中更具有代表性，覆盖度用包含词语的全部文档数 $\mathrm { N _ { i } }$ 除以总文档数 $\mathrm { \Delta N }$ 来表示，计算公式如下：

$$
\mathrm { c o v e r a g e _ { i , j } = \frac { N _ { i } } { N } }
$$

特征度characteristic $\mathbf { \dot { \rho } _ { i } }$ 反映词汇所在文本在某个主题中代表程度。 $\mathsf { p } ( z _ { \mathrm { i } } \mid \mathsf { d } _ { \mathrm { n } } )$ 为主题-文本概率分布，代表词汇 $\mathbf { w _ { i } }$ 所在的文本属于主题 $z _ { \mathrm { i } }$ 的概率，为包含词汇 $\mathbf { w _ { i } }$ 的微博 ${ \bf d } _ { \mathrm { n } }$ 代表主题 $z _ { \mathrm { i } }$ 的概率，计算公式如下:

$$
\mathrm { { c h a r a c t e r i s t i c } _ { i } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } { p ( z _ { i } | \mathbf { d } _ { n } ) } } { N } }
$$

结合改进TF-IDF算法，其表达式如下：

$$
\mathrm { \ w e i g h t _ { i , j } = p ( w _ { i } \mid z _ { j } ) \times l o { \underline { { | \Psi _ { \mathrm { n u m } } | } } } \times \mathrm { c o v e r a g e _ { i , j } \times \mathrm { c h a r a c t e r i s t i c _ { i } } } } 
$$

其中， $\mathrm { w } _ { \mathrm { n u m } }$ 表示文档词汇总数， $\mathrm { \Delta W _ { n u m } ^ { i } }$ 表示 $\mathbf { w _ { i } }$ 的词频数量。可见，词汇在文档中出现次数越多，包含词汇文档数目越少，代表度越高，同一主题中覆盖度越大，特征度越高的特征词更能代表主题语义。本文通过改进的 TF-IDF算法计算词汇权重后，按权重weighti;数值从大到小排序，选取前 $\mathfrak { n }$ 个特征词，组成主题特征词向量，则调整后主题 $z _ { \mathrm { n } }$ 的特征词向量表示如下:

$$
\begin{array} { c } { \overline { { \mathbf { z } _ { \mathrm { n } } } } = \{ ( \mathrm { w } _ { 1 } , \mathrm { w e i g h t } _ { 1 , \mathrm { j } } ) , ( \mathrm { w } _ { 2 } , \mathrm { w e i g h t } _ { 2 , \mathrm { j } } ) , \cdots , ( \mathrm { w } _ { \mathrm { n } } , \mathrm { w e i g h t } _ { \mathrm { n } , \mathrm { j } } ) \} } \\ { \mathrm { w } _ { 1 } \cdots \mathrm { w } _ { \mathrm { n } } \in \mathrm { V } } \end{array}
$$

基础LDA模型与权重计算结果对比如图1所示，上方为LDA主题建模结果，下方为权重计算后的主题

特征向量。

Topic 1 Topic 2 Topic 3  
男司机 中国 \*\*...\*\*·\*\*.\*.\*....·\*.\*\*...·\*\*...\*\*··....\*\*··\*·..\*\*··... 李娜  
女司机 地震 姜山  
暴打 尼泊尔 [鼓掌]  
惨遭 游客 中国  
成都 愿 妈妈  
分析 嫦 曝光  
[笑cry] 暖 恭喜冠军成为想 升级  
To司机 惨遭 Topi2 游客 \*\*\*\*.\*\*\*·...\*\*·\*\*.\*\*\*\*....\*\*\*.\*\*.\*\*\*\*...·\*\*·\*\*.\*\*\*\*·... Top娜 恭喜  
暴打 回国 成为  
分析 尼泊尔 妈妈骂 地震 中国  
成都 [心] [鼓掌]  
[笑cry] 嫦爱想愿 曝光  
男司机 姜山  
评论 冠军事 升级

# 3.2基于特征词向量的主题词汇链生成

词语常常围绕特定主题描述话题信息，这些围绕某个主题，在语义上相互联系的词语集合，称为词汇链。本文用特征词之间相关度的大小反映不同词汇间语义关联的强弱。常用的词汇间相关度计算公式如下：

$$
\mathrm { c o r ( w _ { i } , w _ { j } ) } = \frac { \mathrm { c ( w _ { i } , w _ { j } ) } } { \mathrm { c ( w _ { i } ) } + \mathrm { c ( w _ { j } ) } - \mathrm { c ( w _ { i } , w _ { j } ) } } - \frac { \mathrm { c ( w _ { i } ) } \times \mathrm { c ( w _ { j } ) } } { \mathrm { N } \times \mathrm { N } }
$$

其中， ${ \mathsf { c } } ( { \mathsf { w } } _ { \mathrm { i } } , { \mathsf { w } } _ { \mathrm { j } } )$ 为 $\mathbf { w _ { i } }$ 与 $\mathbf { w _ { j } }$ 在同一窗体中出现的频率, $\mathsf { c } ( \mathrm { w } _ { \mathrm { i } } ) , \mathsf { c } ( \mathrm { w } _ { \mathrm { j } } )$ 为各自的词频，N为全部文档数目。由于在计算中可能得到词汇为负相关，考虑到$\mathsf { c } ( \mathrm { w } _ { \mathrm { i } } ) , \mathsf { c } ( \mathrm { w } _ { \mathrm { j } } )$ 相比于 $\mathrm { ~  ~ N ~ }$ 通常较小，因此公式(6)中后半部分可以忽略。传统相关度计算中忽视了 $\mathbf { w } _ { \mathrm { i } }$ 与 $\mathbf { w _ { j } }$ 自身权重的影响，当权重较高的特征词间相关度高时，其组成短语更易于反映主题信息。由此本文相关度计算公式改进为如公式(7)所示，在原相关度计算公式基础上引人特征词权重weighti,j

$$
\mathrm { c o r ( w _ { i } , w _ { j } ) } = \sum \mathrm { w e i g h t _ { i , j } } ( \frac { \mathrm { c ( w _ { i } , w _ { j } ) } } { \mathrm { c ( w _ { i } ) } + \mathrm { c ( w _ { j } ) } - \mathrm { c ( w _ { i } , w _ { j } ) } } )
$$

其中， ${ \mathsf { c } } ( { \mathsf { w } } _ { \mathrm { i } } , { \mathsf { w } } _ { \mathrm { j } } )$ 在本文中取词汇在同一微博中共现次数， $\mathsf { c } ( \mathbf { w } _ { \mathrm { i } } )$ ， ${ \mathsf { c } } ( { \mathsf { w } } _ { \mathrm { j } } )$ 为 $\mathbf { w _ { i } }$ 与 $\mathbf { w _ { j } }$ 在语料文本中出现次数。可见，若相关性为正值，则说明两词相关，正值越大，则相关度越高。当两个权重高的特征词的共现概率高时，则词汇间相关度变大，其组成短语更能准确反映话题语义信息。

文献[19]认为，新闻领域通常使用新闻六要素来描述一个事件，即：内容(What)、人物(Who)、地点(Where)、时间(When)、原因(Why)及如何(How)。文献[20]认为评论中的观点持有者一般是由命名实体,提出借助于命名实体识别技术来获取观点持有者。本文借鉴上述思想，认为描述话题事件的文本通常包含名词词性的词汇，由此选择特征词集合中的名词词性的特征词 $\mathbf { w _ { i } ^ { n } }$ 作为种子词，用以自动生成主题词汇链。主题词汇链Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$ 依据种子词 $\mathbf { w _ { i } ^ { n } }$ 与特征词向量中其他特征词的相关度和特征词的权重等因素生成。当种子词 ${ \bf w } _ { \mathrm { i } } ^ { \mathrm { n } }$ 与特征词的相关度 ${ \mathrm { c o r } } ( \mathrm { w } _ { \mathrm { i } } ^ { \mathrm { n } } , \mathrm { w } _ { \mathrm { j } } )$ 大于阈值后，将种子词与特征词组成短语 $\mathrm { { \bf P } ^ { t } }$ 加入词汇链候选集合 $\mathrm { \mathbf { P } _ { i } }$ 中，短语的权重更新为词汇的权重之和。迭代计算后，从中选取权重最大的短语 $\mathrm { { \bf P } } ^ { \mathrm { t } }$ 作为主题词汇链，即Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \} = \arg \operatorname* { m a x } _ { 0 < \mathrm { k } < \mathrm { K } } \mathrm { P } ^ { \mathrm { t } } ( \mathrm { w e i g h t } _ { \mathrm { i , j } } \mid z = \mathrm { i } ) ,$ ，主题词汇链生成算法如下：

Input:特征词集合 $\mathrm { V _ { i } }$ ，特征词短语集合 $\mathrm { \mathrm { P _ { i } } }$   
Output:主题词汇链Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$   
$\mathrm { \textcircled {1 } S e t P _ { i } = V _ { i } }$   
$\textcircled{2}$ For each wj in $\mathrm { \Delta V _ { i } }$ Calculate weighti.j Add all $\mathbf { w _ { i } ^ { n } }$ in list; End for;   
$\textcircled{3}$ Foreach $\mathbf { w _ { i } ^ { n } }$ in list For each $\mathrm { { { P } ^ { t } } }$ in $\mathrm { \mathbf { P } _ { i } }$ Calculate ${ \cos ( \mathrm { w _ { i } ^ { n } , \mathrm { w _ { j } ) } } }$ （204号 If $\mathrm { c o r } ( \mathrm { w _ { i } ^ { n } , w _ { j } ) \geq }$ 阈值 Set $( \mathbf { w } _ { \mathrm { i } } ^ { \mathrm { n } } , \mathbf { w } _ { \mathrm { j } } )$ as a phrase into $\mathrm { \mathbf { P } _ { i } }$ （204号 End for End for   
$\textcircled{4}$ Foreach $\mathrm { { { P } ^ { t } } }$ m $\mathrm { \mathbf { P } _ { i } }$ Set maximum weight $\mathrm { { { P } ^ { t } } }$ as Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$ End for

# 3.3基于情感词典的主题观点抽取

观点抽取指利用计算机技术自动分析网络中带有观点信息的句子或文档，从中提取出用户所表达的观点或态度。话题文本中的观点倾向主要通过观点词传

递，观点词多为情感词，其中观点词体现为观点倾向(褒义、贬义和中立)与观点强度两个维度。

本文借鉴大连理工情感词本体[21]结果，构建情感词典，大连理工情感词本体通过三元组来描述，具体如下:

$$
\mathrm { L e x i c o n } = \left( \mathrm { B } , \mathrm { R } , \mathrm { E } \right)
$$

其中，B表示词汇基本信息,R表示词汇之间同义关系，E代表词汇情感信息，分别从情感分类、极性、强度三个维度描述。通过候选情感词与基准情感词在大规模语料中点互信息(PMI)判定情感强度，强度分为1,3,5,7,9这5个等级。在微博文本中，越来越多的用户使用微博表情代替文字信息，表达个人观点，在本文的实验语料中，含有微博表情的文本占 $4 6 . 7 \%$ 。由此在大连理工情感词本体的基础上，对情感词典进行扩充，加入微博常用表情。将微博表情以[表情内容]的形式表示，如"[鼓掌]"[爱你]"，存入情感词典，以其文本内容代表表情语义。经过处理，情感词典共有单词共28466个，褒义词16074个，贬义词12392个，情感强度参考情感词本体，也分为1,3,5,7,9这5个等级。

参照情感词典，假设在主题特征词向量中标记出$\mathbf { m }$ 个观点词，当前主题观点词向量表示为 $\mathrm { \Delta S W = }$ $\{ ( \mathrm { s w } _ { 1 } , \mathrm { s w e i g h t } _ { \mathrm { s w } _ { 1 } } ) , ( \mathrm { s w } _ { 2 } , \mathrm { s w e i g h t } _ { \mathrm { s w } _ { 2 } } ) \cdots ( \mathrm { s w } _ { \mathrm { m } } , \mathrm { s w e i g h t } _ { \mathrm { s w } _ { \mathrm { m } } } ) \} \ ,$ （20$\boldsymbol { \mathrm { s w } } _ { \mathrm { m } }$ 表示观点词，sweight $\operatorname { s w } _ { \mathrm { ~ m ~ } }$ 为对应观点强度。然而主题观点的表达不仅与观点强度相关还与观点次和主题内容的紧密程度有关。本文采用主题词汇链Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$ 表示主题事件的语义信息。因此，将观点抽取过程转化为观点词与主题词汇链的相关度的计算过程。本文定义主题观点的观点值 $\mathrm { \Delta Q _ { i } }$ ，其计算公式如下:

$$
\mathrm { Q _ { i } = s w e i g h t _ { s w _ { i } } \times \sum _ { i } ^ { n } c o r ( s w _ { i } , w _ { j } ) \lvert \ s w _ { i } \in S W , w _ { j } \in L e x i c a l c h a i n \{ k _ { i } \} }
$$

可见，当观点词观点强度越大，同时该观点词与主题内容相关度越高，则观点词更能代表主题观点。对所有被标注出的观点词sW，满足以下两种情况之一，则自动抽取为主题观点View $\{ \mathrm { j } _ { \mathrm { n } } \}$ ：

(1)对于 $\forall \mathbf { s w } _ { \mathrm { i } } \in$ Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$ ，Viewpoint $\{ \mathrm { j _ { n } } \} =$ argmax{weight $_ \mathrm { s w _ { i } } \}$ ， $\mathrm { i } \in \{ 1 , 2 , \cdots \mathrm { n } \}$ ·，

(2)如果 $\exists \mathrm { s w } _ { \mathrm { i } } \in \mathrm { S W }$ 且sw；Lexicalchain $\{ \mathbf { k } _ { \mathrm { i } } \}$ ，使得 $\mathrm { V i e w p o i n t \{ j _ { n } \} } = \mathrm { a r g m a x \{ Q _ { i } \} } , \ \mathrm { i } \in \{ 1 , 2 , \cdots n \} \ \mathrm { o }$ （20

即，在条件(1)中，如果主题词汇链中存在情感词，选取权重最大的特征词作为主题观点；在条件(2)中，选取在观点词集合中观点值最大的观点词作为主题观点。

# 4实验设计

# 4.1 实验设置

本文使用爬虫工具抽取2014年6月到2015年6月热门微博话题事件微博共24598条，其中关于“成都女司机被打"话题微博共9 230 条，关于"尼泊尔地震"微博共6932条，关于“长江客轮沉没"话题共4367条，“李娜产女"话题共4069条。预处理阶段，使用中国科学院计算技术研究所汉语分词系统 ${ \mathrm { N L P I R } } 2 0 1 5 ^ { \mathrm { \textregistered } }$ 对微博正文文本分词并进行词性标注。根据哈工大停用词表去除停用词，同时去掉微博短链以及低频词，保留名词、动词、形容词作为候选词。

# 4.2 实验结果

实验设置参数 $\alpha = 5 0 / \mathrm { K }$ ， $\beta = 0 . 0 1$ ，吉布斯采样的迭代次数为1000次，其中K为设置的话题数量。为了分析话题数量的设置对于LDA话题建模的影响，采用Perplexity 指标对实验结果进行衡量。Perplexity是度量话题模型性能的常用指标和衡量方法，表示预测数据时的不确定度，取值越小表示性能越好，计算公式如下：

$$
\mathrm { P e r p l e x i t y ( W ) } = \mathrm { e x p } \left\{ \mathrm { - \frac { \displaystyle \sum _ { m } \ln p ( \mathrm { w _ { m } ) } } { \displaystyle \sum _ { m } \mathrm { N _ { m } } } } \right\}
$$

其中，W 为测试集, $\mathbf { w _ { \mathrm { m } } }$ 是测试集中可观测到的词语， $\Nu _ { \mathrm { { m } } }$ 为词语数。逐步递增话题数K进行实验，按照公式(10)计算不同话题值下LDA话题的混杂度。随着话题数逐渐增加,Perplexity值不断降低，如图2所示：

![](images/cb6e2b399abcd96df945c6305840977f07731df39e535d68fabdbfb55c424b7f.jpg)  
图2Perplexity 分布图

本文最终选取 $\mathrm { K } { = } 5 0$ ，实验结果如表1所示：

表1“主题 $^ +$ 观点"词条抽取结果  

<html><body><table><tr><td>事件名称</td><td>权重计算结果</td><td>主题词汇链</td><td>主题观点</td><td>“主题+观点"词条</td></tr><tr><td rowspan="3">李娜产女</td><td>李娜公布顺利 英文名小脚Alisa 喜讯孩子发布 英文</td><td>李娜公布</td><td>喜讯</td><td>李娜公布+喜讯</td></tr><tr><td>李娜产女祝福人生哈哈 祝 满贯快乐手成长</td><td>李娜产女</td><td>祝福</td><td>李娜产女+祝福</td></tr><tr><td>李娜 恭喜 成为 妈妈 中国[鼓掌]曝光 姜山 冠军 升级</td><td>李娜成为妈妈</td><td>恭喜</td><td>李娜成为妈妈+恭喜</td></tr><tr><td rowspan="3"></td><td>女司机变道成都 视频 记录 车行车殴打遭曝光</td><td>女司机变道</td><td>殴打</td><td>女司机变道+殴打</td></tr><tr><td>成都司机被打女司机 惨遭 暴打 分析 骂 成都[笑cry]男司机 评论 事</td><td>女司机暴打</td><td>暴打</td><td>女司机暴打+骂</td></tr><tr><td>女司机 慈善 做 母亲 视频 机构[笑cry]事 女儿搞</td><td>女司机慈善</td><td>[笑cry]</td><td>女司机慈善+[笑cry]</td></tr><tr><td rowspan="3">尼泊尔地震</td><td>中国游客回国尼泊尔地震[心]嫦爱 想愿</td><td>中国游客回国</td><td>[心]</td><td>中国游客回国+[心]</td></tr><tr><td>尼泊尔 地震[祈祷]中国国际[心]汶川加油 力量[位置]</td><td>尼泊尔地震</td><td>[祈祷]</td><td>尼泊尔地震+[祈祷]</td></tr><tr><td>西藏 受灾自治区捐赠 救灾 影响 受 波及房屋 前往</td><td>西藏受灾</td><td>捐赠</td><td>西藏受灾+捐赠</td></tr><tr><td rowspan="2">长江客船沉没</td><td>救援队 救援 搜救 队员中国 国际 应急 帐篷小时废墟</td><td>救援队搜救</td><td>救援</td><td>救援队搜救+救援</td></tr><tr><td>长江愿平安客船沉没 乘客入公司星沉 长江 倾覆 客轮 安息 生命 加油 珍惜 生长 爱</td><td>长江客轮 长江客轮</td><td>平安 倾覆</td><td>长江客船+平安 长江客轮+倾覆</td></tr></table></body></html>

对于某一微博话题内容，往往含有多个不同主题内容即子话题。由实验结果可以看出LDA模型在主题挖掘领域中具有良好的效果，主题间具有较高独立性，主题特征词具有较高的概括性，充分反映出不同主题间的文本内容，有效去除垃圾微博对话题事件的影响。例如“尼泊尔地震"事件中，分别反映出“中国旅客回国”、“西藏地区受灾”、“救援队救援"等主题信息，将围绕微博话题的不同主题信息有效区分开来。

在特征词集合构建中，根据改进的 TF-IDF 算法提升话题特征词的权重，降低无关的背景词的权重,突出主题特征。例如，在"李娜产女"的话题中“中国”“冠军"是与话题相关性较低词汇，经过计算，本文方法减少了无关词汇影响，同时提升了“李娜”、“女儿"等词汇的权重，更好地反映话题内容。

观点词抽取反映出用户对话题内容的观点意见，展示事件发展过程中对话题中不同主题的态度。例如在"成都女司机被打"事件中，事件开始女司机被打的观点为“骂”，表达对打人事件的遣责，经过事件发展，女司机借口去做慈善而违章变道，则该主题事件中的观点是"[笑cry]"，表达反讽与不相信。

本文的"主题 $\cdot +$ 观点"词条能够较好地反映话题信息，基本覆盖话题中各主题事件内容，从主题内容信息与主题观点两个维度表征话题。例如“长江沉船沉没"事件中，自动抽取词条"长江客船 $^ { \cdot _ { + } }$ 平安”、“长江客轮 $^ +$ 倾覆”，虽然主题词汇链相同，但属于微博话题中不同讨论的内容，前者为客船祈福，后者是话题事件的描述报道。

# 4.3 对比实验

对本文方法同新浪微博话题标签与文献[12]提出的方法进行比较。新浪微博话题标签一般由人工编辑，作为对微博话题事件的概述。文献[12]抽取每个主题的种子词，迭代产生关键短语集合，最后泛化选择话题标签，描述话题信息。结果如表2所示：

表2对比实验结果  

<html><body><table><tr><td>事件名称</td><td>新浪微博话题标签</td><td>文献[12]话题标签</td><td>“主题+观点"词条</td></tr><tr><td>尼泊尔地震</td><td>尼泊尔8.1级地震</td><td>尼泊尔地震 中国救援队</td><td>尼泊尔地震+[祈祷] 西藏受灾+捐赠</td></tr><tr><td></td><td></td><td>西藏地震</td><td>救援队搜救+救援 中国游客回国+[心] 李娜产女+祝福</td></tr><tr><td>李娜产女</td><td>李娜产女 成都女司机</td><td>李娜公布孩子 女司机成都狂殴</td><td>李娜成为妈妈+恭喜 女司机变道+殴打</td></tr><tr><td>成都司机被打 长江客轮</td><td>变道遭殴打 长江客轮沉没</td><td>女司机驾驶 全国人民</td><td>女司机惨遭+暴打 长江客船+平安</td></tr></table></body></html>

从对比结果可以看出本文方法能够准确抽取表达出话题内容及观点。例如"尼泊尔地震"话题中，由于话题事件爆发突然，事件讨论相对集中，用户观点基本一致。新浪微博简单表述为“尼泊尔8.1级地震"，缺少对话题中各主题事件的多维度表达，文献[12]的话题标签只是单纯描述出话题事件内容，如"尼泊尔地震”、“西藏地震”，而本文对话题语料抽取出“中国游客回国 $+$ [心]”、“西藏受灾 $+$ 捐赠"等，在表述主题信息同时，反映用户相应主题观点。

与文献[12]话题标签抽取方法相比，本文在反映主题内容信息同时，也反映出事件相应观点倾向，以便于用户了解话题全貌。例如，尼泊尔地震事件中，虽然两种方法都抽取出“尼泊尔地震”，但本文方法在表述话题事件的同时也反映出提及地震事件的微博大部分是为地震灾区祈祷，展现用户表达的观点。同时在“尼泊尔地震"事件中，本文方法还抽取出在被困中国游客回国的事件，而文献[12]方法并没有挖掘出相关主题。

在部分话题语义表达中，本文方法不如新浪微博话题标签，例如新浪微博话题标签为“成都女司机变道遭殴打”，本文抽取的词条为"女司机变道 $+$ 殴打”,与之相比信息完整性与语义通顺性都有所欠缺。同时，由于用户在发表的微博中，越来越多使用表情图标代替文本以表达观点，但包含微博表情的微博往往无明显句法结构，因此包含微博表情的词条在对话题信息解释性方面受到影响。

本文采用准确率P、召回率R和F1对比文献[12与本文方法抽取的效果，计算公式如下：

$$
\mathrm { P } { = } \frac { \mathrm { C } _ { \mathrm { c o r r e c t } } } { \mathrm { C } _ { \mathrm { e x t r a c t } } }
$$

$$
\mathrm { R } = \frac { \mathrm { C _ { c o r r e c t } } } { \mathrm { C _ { s t a n d a r d } } }
$$

$$
\mathrm { F 1 } = \frac { 2 \mathrm { P R } } { \mathrm { P } + \mathrm { R } }
$$

其中， $\mathbf { C } _ { \mathrm { c o r r e c t } }$ 为正确抽取结果数目, $\mathrm { \Delta C _ { \mathrm { e x t r a c t } } }$ 为所有抽取结果，而 $\mathrm { C _ { \mathrm { { s t a n d a r d } } } }$ 为所有人工标注词条数目，结果如表3所示：

表3实验精度评测结果  

<html><body><table><tr><td rowspan="2">事件名称</td><td colspan="2">准确率P</td><td colspan="2">召回率R</td><td colspan="2">F1</td></tr><tr><td>本文 方法</td><td>话题 标签</td><td>本文 方法</td><td>话题 标签</td><td>本文 方法</td><td>话题 标签</td></tr><tr><td>李娜产女</td><td>78.7%</td><td>74.6%</td><td>73.3%</td><td>69.6%</td><td>75.9%</td><td>72.1%</td></tr><tr><td>成都司机被打</td><td>75.3%</td><td>68.7%</td><td>71.7%</td><td>66.2%</td><td>73.4%</td><td>67.4%</td></tr><tr><td>尼泊尔地震</td><td>85.1%</td><td>84.1%</td><td>78.3%</td><td>76.4%</td><td>81.6%</td><td>80.1%</td></tr><tr><td>长江客轮沉没</td><td>80.3%</td><td>78.9%</td><td>76.7%</td><td>77.8%</td><td>78.4%</td><td>78.3%</td></tr></table></body></html>

从表3中可以看出，本文方法精度高于文献[12]方法，在“成都司机被打"的事件中，话题讨论多为网民自发参与，事件持续时间较长，伴随着事件的演化与发展，用户在不同阶段情感发生转变，文献[12]话题标签由于缺少观点维度表达，仅描述话题内容，因此准确率、召回率低于本文方法。在"李娜产女"的微博中存在大量"大满贯"中国网球"等无关背景词，在一定程度上干扰话题信息，本文方法有效降低了背景词对事件抽取的影响，因此准确率更高。同时在"尼泊尔地震"与“长江客轮沉没"的事件中由于话题中微博多为新闻报道类微博，具有通用格式，微博内容具有较高语义相似性，因此两种方法精度相近。

本文与文献[12]方法均采用LDA 模型主题建模,但模型建模结果中存在部分主题语义表达不明确和掺杂大量垃圾微博信息的问题，如大量简单动词如“走”、“吃”、“去”、“爱"在同一个话题结果中，并不具备表达话题语义的能力，影响反映话题事件主要信息。

# 5总结与展望

本文提出一种面向微博话题的"主题 $\cdot +$ 观点"词条模型及其无监督抽取算法，该算法采用LDA建模，对词汇权重计算后，构建特征词集合；根据特征词间相关性，自动抽取出主题词汇链，表述主题内容信息;引入情感词典，得到主题观点，将主题词汇链与主题观点构建成“主题 $^ +$ 观点"词条，从内容与观点两个维度表征微博话题信息。最后通过实验数据验证“主题 $^ +$ 观点"词条在话题信息抽取与表达方面的实用性以及其无监督抽取算法的有效性。后续工作包括进一步准确抽取话题观点以及改进主题模型，提升主题抽取效果。

# 参考文献：

[1]中国互联网络信息中心．第36次中国互联网络发展状况统 计报告[R/OL]. http://www.cnnic.net.cn/hlwfzyj/hlwxzbg/hlwtjbg/ 201507/P020150723549500667087.pdf.(China Internet Network Information Center. The 36th Statistical Report on the Network Development of China Internet [R/OL]. http://www. cnnic.net.cn/hlwfzyj/hlwxzbg/hlwtjbg/201507/P02015072354 9500667087.pdf.)   
[2]艾瑞咨询．2014 年中国微博用户行为研究报告[R/OL]. http://www.iresearch.com.cn/report/2183.html. (iResearch．The 2014 Research on China Weibo User Behavioral Report [R/OL].http://www.iresearch.com.cn/report/2183.html.)   
[3]洪宇，张宇，刘挺，等．话题检测与跟踪的评测及研究综 述[J]．中文信息学报,2007,21(6):71-87.(Hong Yu,Zhang Yu,Liu Ting,et al. Topic Detection and Tracking Review [J]. Journal of Chinese Information Processing，2007,21(6): 71-87.)   
[4] Becker H, Naaman M, Gravano L.Beyond Trending Topics: Real-WorldEventIdentificationonTwitter[C].In: Proceedings of the 5th International Conference on Weblogs and Social Media,Barcelona, Catalonia, Spain. AAAI Press, 2011.   
[5]Popescu A M,Etzioni O.Extracting Product Features and Opinions from Reviews[A]. // Natural Language Processing and Text Mining[M]. Springer London,2007.   
[6] Ritter A，Mausam，Etzioni O,et al.Open Domain Event Extraction from Twitter[C].In: Proceedings of the 18th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.ACM,2012.   
[7] Blei D M,Ng A Y,Jordan MI,et al.Latent Dirichlet Allocation [J]. Journal of Machine Learning Research, 2003, 3:993-1022.   
[8]Lin C H,He Y L. Joint Sentiment/Topic Model for Sentiment Analysis [C].In: Proceeding of the 18th ACM Conference on Information and Knowledge Management. New York: ACM, 2009: 375-384.   
[9]唐晓波，向坤．基于 LDA 模型和微博热度的热点挖掘[J]. 图书情报工作，2014,58(5):58-63.(Tang Xiaobo，Xiang Kun.Topic Mining Based on LDA Model and Popularity of Weibo[J]. Library and Information Service,2014,58(5): 58-63.)   
[10] Rosen-Zvi M,Grifiths T,Steyvers M,et al.The AuthorTopic Model for Authors and Documents [C]. In: Proceedings of the 2Oth Conference on Uncertainty in Artificial Intelligence. 2012.   
[11] 张晨逸，孙建伶，丁轶群．基于 MB-LDA 模型的微博主题 挖掘[J]．计算机研究与发展，2011，48(10):1795-1802. (Zhang Chenyi,Sun Jianling,Ding Yiqun.Topic Mining for Microblog Based on MB-LDA Model[J]. Journal of Computer Research and Development, 2011,48(10): 1795-1802.)   
[12]寇宛秋，李芳．基于种子词汇的话题标签抽取研究[J]．中 文信息学报,2013,27(5):114-121.(Kou Wanqiu,Li Fang. Topic Label Extraction Based on Seed Word[J]. Journal of Chinese Information Processing,2013,27(5): 114-121.)   
[13]钱哲怡，李芳．基于关键词和命名实体识别的新闻话题线 索抽取[J]．计算机应用与软件，2011，28(12)：168-171. (Qian Zheyi,Li Fang. Keyword andNameEntity Identification Based News Topic Thread Extraction[J]. Computer Applications and Software,2011,28(12):168-171.)   
[14] Hoffman M D,Blei D M,Bach F R.Online Learning for Latent Dirichlet Allocation[C]. In:Proceedings of the 24th Annual Conference on Neural Information Processing Systems.2010.   
[15] Ramage D,Hall D,Nallapati R,et al.Labeled LDA: A Supervised TopicModel for Credit Attributionin Multi-labeled Corpora [C]. In: Proceedings of the 2009 Conference on Empirical Methods in Natural Language Processing, Singapore.2009.   
[16]Darling W, Song F．Probabilistic Topic and Syntax Modeling with Part-of-Speech LDA[OL].arXiv:1303.2826.   
[17] 闫泽华．基于LDA的新闻线索抽取研究[D]．上海：上海交 通大学,2012.(Yan Zehua.News Threading Based on LDA Model[D]. Shanghai: Shanghai Jiaotong University,2012.)   
[18]王宇阳．基于本体进化的自适应中文话题跟踪算法研究 [D]．南京：南京航空航天大学，2013．(Wang Yuyang. Research on Algorithm of Adaptive Chinese Topic Tracking Based on Ontology Evolution [D]. Nanjing: Nanjing University of Aeronautics and Astronautics,2013.)   
[19]郭秀，吕学强，李卓．基于突发词聚类的微博突发事件 检测方法[J]．计算机应用，2014，34(2)：486-490.（Guo Yixiu，Lv Xueqiang，Li Zhuo.Burstyn Topics Detection Approach on Chinese Microblog Based on Burst Words Clustering [J]. Journal of Computer Applications,2014, 34(2):486-490.)   
[20]Kim S M,Hovy E.Determining the Sentiment of Opinions [C].In:Proceedings of the 2Oth International Conference on ComputationalLinguistics.2004.   
[21]陈建美．中文情感词汇本体的构建及其应用[D].大连：大 连理工大学，20o8.(Chen Jianmei.The Construction and Application of Chinese Emotion Word Ontology [D].Dalian: Dalian University of Technology,2008.)

# 作者贡献声明：

姚兆旭：提出研究思路和研究方案，进行实验，论文撰写与修订;  
马静：数据采集，扩展研究思路，论文审阅与修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版 http://www.infotech.ac.cn。  
[1]姚兆旭，马静.lda.zip.LDA 建模JAVA程序.  
[2]姚兆旭，马静.corpus.txt.分词后的数据集.  
[3]姚兆旭，马静.ldaresult.towords.LDA结果数据.  
[4]姚兆旭，马静.tfidfresult.xls.特征词向量结果数据.  
[5]姚兆旭，马静.sentimentdictionary.sql.情感词典.  
[6]姚兆旭，马静.finalresult.xls.结果数据.

收稿日期:2016-01-28   
收修改稿日期:2016-05-23

# Extracting Topic and Opinion from Microblog Posts with New Algorithm

Yao ZhaoxuMa Jing (College of Economic and Management,Nanjing UniversityofAeronautics and Astronautics,Nanjing 211106,China)

Abstract: [Objective] This paper proposes an algorithm to extract topic and opinion information from the microblog posts automatically.[Methods]First,we used the improved TF-IDFalgorithm to build the topic characteristic word vector.Second,we generatedlexicalchain for the topics based onthe relevance among words ofthe vector.Finally, we extracted the topic and opinion information with the sentiment dictionary,and then generated the“topic+opinion” entries.[Results] We analyzed 24,598 Sina microblog posts offour trending events from June 2014 to June 2015 retrieved by a specially designed crawler.The precision and recal rates of the proposed method were $80 . 3 \%$ and $7 6 . 6 7 \%$ ,respectively.[Limitations] The data size was small the eect that the topic model extracted the feature about Weibo still required tobe improved.[Conclusions]The proposed algorithm could effectively extract the“topic and opinion” information from micoblog posts.

Keywords: Text miningKeyword extractionTopic modelMicroblog topic

# NISO推出新项目，为图书馆电子内容创建灵活的API框架

国家信息标准组织(NISO)经过投票已经批准了一个新的项目，该项目的目标是增强现代化图书馆厂商技术的互操作性,以改善数字内容和电子书的访问。NISO 工作小组将基于Queens Library 所开发的一套 API需求，建立一个基础的供图书馆使用的 API组。这个API组将实现用户和图书馆目前的需求，例如：更快的响应时间、灵活的发现和交付选项、更高的资源可利用性，以及电子资源和物理资源更加无缝的集成。

图书馆服务于读者时，应该给读者以优秀的用户体验，以及必要的便利性。NISO 的这一新项目试图将读者的图书馆体验和现代化工具，以及读者在生活中习惯使用的技术，特别是移动技术进行接轨。当今的图书馆使用了多种技术，其中的一些技术甚至依赖过时的、缓慢的通信协议来服务读者。通过建立RESTful Web Services API标准，以及移动扩展标准，图书馆行业将能够摒弃很多陈旧的、难以使用的工具，帮助图书馆在满足用户需求时能够有更强的灵活性。

志愿者工作组成员将以NISO推荐做法的形式提供一个基础框架，讨论图书馆如何提供和获取数据。这些图书馆相关的通讯和功能可能包括：定制的馆藏浏览、搜索和发现，用户认证，账户信息的传输，条形码管理，图书的借阅和归还，在线资源的流媒体化，以及其他利益相关者的需求。此外，工作组的工作还包括，创建一些使用推荐做法的服务案例，构建一个注册机制，帮助支持数据提供方和系统供应商沟通他们对基础框架的支持。完整的工作说明可在 NISO 官网(htp://www.niso.org.)获取。

(编译自:http://www.niso.org/news/pr/view?item_key $\scriptstyle \overbrace { \mathbf { \Gamma } } = \mathbf { \Lambda }$ e18a9742103bc945868a51a1e196e62b68879df6)

(本刊讯)