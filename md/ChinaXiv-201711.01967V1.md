# 基于LDA模型的移动投诉文本热点话题识别

方小飞」黄孝喜」王荣波」 谌志群」 王小华1,21(杭州电子科技大学计算机学院 杭州 310018)2(中国计量大学 杭州 310018)

摘要：【目的】运用中文信息处理和话题识别与追踪的方法，从大量移动投诉文本中找出有价值的信息。【方法】从分析投诉文本的特点入手，使用 $\mathbf { k }$ -means先对文本聚类。利用LDA对每个类进行建模，提取话题，并从词频、词跨度和词长三方面计算每个话题中词的权值，把权重最大的词作为该话题的标签，并计算每个话题的文档分布概率均值。对具有相同标签的话题，先按照均值最大的原则去掉重复标签话题，再对所有话题计算文档支持率，并将文档支持率作为话题的热度，通过热度区分热点话题和一般话题。【结果】对投诉文本进行时间上的建模，通过对比一般话题和热点话题，得出热点话题的支持文档率至少是一般话题的3倍，支持文档率变化趋势也比一般话题高，说明本文算法是有效的。【局限】没有考虑到话题之间的语义关系。【结论】利用LDA模型对移动投诉话题检测初探的方法是比较合理和有效的，对今后此领域的研究具有一定的借鉴意义。

关键词：移动投诉 k-means 话题识别 LDA模型 分类号：TP391

# 1引言

随着互联网的日益普及和通信技术的不断发展，上网人群日益增多，尤其是移动端，通过手机玩游戏、刷微博、逛贴吧、看新闻的人越来越多。各大电信运营商看到了其中的商机，为了满足客户的需求、拓宽自己的业务、抢占市场份额，他们推出了各种优惠政策以吸引用户，随着用户量不断上升，投诉量也日益剧增，因此如何有效地处理投诉文本成为了各界关注的焦点。其实在大量的投诉中有很多大家关注的热点话题，比如"宽带”、“流量”、“扣费"等等，如果可以从中发现话题，并对话题进行追踪，根据话题的变化趋势了解相关业务的受理情况、了解用户的关注点，从而对症下药，就能提高处理投诉的效率。因此对投诉文本进行话题挖掘就显得十分重要。

与新闻报道相比较，移动投诉文本的结构更加复杂且短小，这加大了提取话题的难度。本文针对移动投诉文本，应用"话题识别"的相关知识，从中识别投诉文本中的热点话题。

# 2 相关工作

话题识别和跟踪研究中，LDA[1]主题模型是近年来文本挖掘领域的一个热门研究方向，主题模型具有优秀的降维能力、针对复杂系统的建模能力和良好的扩展性。利用主题建模挖掘出的主题可以帮助人们理解海量文本背后隐藏的语义，也可以作为其他文本分析方法的输人，完成文本分类、话题检测、文本自动摘要和关联判断等多方面的文本挖掘任务。

LDA主题模型具有优秀的降维能力和扎实的概率理论基础，使其在短文本主题挖掘中具有很大的潜力。近年来，为了提高LDA模型主题挖掘的效率和准确性，出现很多对LDA模型的改进方法，可归纳为纵向的过程扩展和横向的模型扩展[2]。一方面，针对微博文本篇幅较短的局限，基于操作过程扩展的方法考虑将微博文本进行适当的聚集，这样短文本被聚集成相对适合挖掘的长文本。Weng等[3采用同一微博用户的所有微博文本聚集成一篇长文档的策略，利用LDA模型进行主题挖掘。Hong等[4提出基于训练的用户模式建模和基于术语模式建模。另一方面，为了适应微博短文本的主题挖掘，规避短文本数据噪声大的影响，提出基于模型扩展优化的LDA模型，典型的改进模型包括ATM[5]、Twitter-LDA[、Labeled-LDA[7]、MB-LDA[8]、HLDA[]以及 MA-LDA[10]。Zhao 等[提出Twitter-LDA模型挖掘整个Twitter文本中具有代表性的文本主题。Ramage 等提出 Labeled-LDA，一种基于标签的主题模型。张晨逸等[8提出微博生成模型MB-LDA，该模型综合考虑了微博的文本关联关系和联系人关联关系，这两种关系可以辅助微博的主题挖掘。文献[2,11]对LDA模型的纵向和横向改进方法进行了比较总结，如表1所示。

表1LDA 话题模型建模方法比较[2]  

<html><body><table><tr><td>模型</td><td>扩张方式</td><td>实现方式</td><td>优势</td><td>局限性</td></tr><tr><td>LDA[1]</td><td>无</td><td>直接使用</td><td>无需监督</td><td>主题挖掘不理想</td></tr><tr><td>基于用户聚集LDA[3]</td><td>过程扩展</td><td>文本聚集</td><td>解决短文本问题</td><td>只限微博用户层面建模，需要人工干预</td></tr><tr><td>基于训练USER 模式[4]</td><td>过程扩展</td><td>文本聚集、 分步求解</td><td>解决短文本问题, 简化推导</td><td>需要事先训练和人工干预，若要更新 模型需重新训练基</td></tr><tr><td>ATM[5]</td><td>模型扩展</td><td>文本聚集</td><td>解决短文本问题</td><td>只限微博用户层面主题建模</td></tr><tr><td>ATM扩展模型[12]</td><td>模型扩展</td><td>文本聚集</td><td>解决短文本问题</td><td>帖子层面主题少且不理想</td></tr><tr><td>Twitter-LDA[6, 13]</td><td>模型扩展</td><td>文本聚集, 引入背景模型</td><td>解决短文本问题和高频 词汇问题</td><td>一个帖子只能对应一个主题</td></tr><tr><td>Labeled-LDA[7, 14]</td><td>模型扩展</td><td>引入标签信息</td><td>提高主题可解释性</td><td>要求文本具有足够的标签信息</td></tr><tr><td>MB-LDA[8]</td><td>模型扩展</td><td>引入结构化信息</td><td>解决短文本问题，提高 主题可解释性</td><td>主要针对会话类和转发类中文微博</td></tr><tr><td>HLDA[9]</td><td>模型扩展</td><td>引入微博评论数、 转发数等特征量</td><td>提高主题可解释性</td><td>主要针对具有高评论数和转发数的微博</td></tr><tr><td>MA-LDA[10]</td><td>模型扩展</td><td>引入时间特征</td><td>解决短文本问题，提高 主题可解释性</td><td>主要适应于短时间内被普遍关注的微博</td></tr></table></body></html>

本文鉴于LDA模型本身的优点和在短文话题识别上的优势，又考虑到投诉文本与微博短文本不一样，微博一般围绕一个话题展开，包含评论、转发等额外信息；但投诉文本没有一个明确的话题，仅仅是客户的一条信息反馈，文本结构简短，内容复杂。因此，本文提出一种基于LDA模型的移动投诉文本热点话题识别方法。首先对投诉文本聚类，每一类使用Gibbs抽样方法进行话题的抽取；然后对抽取的话题进行一系列的处理；最后通过计算话题的文档支持率得出热点话题，并在实验部分对本文方法进行了验证。

# 3基于LDA模型的移动投诉文本热点话题识别

# 3.1 文本聚类

由于投诉文本跟新闻报道不一样，它的形式简短，单条文本涵盖内容信息很少。为了更好的提取话题，首先将文本进行聚类，这样每一类中的投诉文本不仅存在着共性，而且内容比较充实，LDA模型抽取话题表达效果就会更好，针对性更强。

本文采用k-means[15]进行聚类，k-means 是经典划分聚类算法。这种方法简单快速，在对文档进行聚类前需要通过k值来确定簇数量。主要过程是从含n个文本的文档集中随机选择k个文本作为初始的聚类中心，并通过计算得到其他文本到每个簇中心点的距离,将文档划分到离它最近的簇中，用迭代的方式不断重复上述过程，直到满足准则函数或划分过程中相邻簇的中心不再发生变化为止。通过不断的迭代过程增加簇内的紧凑性，降低簇间的相似性。图1为本文聚类的流程。

![](images/ebb4b4a7140dc73cb6774a6b3142aed7539be8c650b42b97bb780362ea8b1100.jpg)  
图1聚类流程

使用k-means 聚类好后，将投诉文本按各类分别存于一个Txt 文件中。

# 3.2 LDA模型话题抽取

LDA[模型中对话题的定义为：一组语义上相关的词及这些词在该话题上的分布概率。由于无法对LDA 模型的未知参数进行求解，在这里使用GibbsSampling的方法近似求解,Gibbs Sampling[1通过迭代采样达到逼近真实结果的效果，其关键点在于对当前单词采样概率的求解，如公式(1)[]所示。

$$
P ( z _ { i } ^ { d } ) | z _ { - i } ^ { d } , w ) = \infty \frac { C _ { d j } ^ { D K } + \alpha } { \displaystyle \prod _ { K = 1 } ^ { K } C _ { d k } ^ { D K } + K \alpha } \frac { C _ { i j } ^ { V K } + \beta } { \displaystyle \prod _ { K = 1 } ^ { K } C _ { k i } ^ { V K } + V \beta }
$$

其中， $w$ 为词表个数； $K$ 为话题数目； $C _ { i j } ^ { V K }$ 为计数矩阵 $C ^ { \mathit { t K } }$ 中第 $i j$ 项，表示第 $j$ 个话题中第 $i$ 个词出现的次数； $C _ { d j } ^ { D K }$ 为计数矩阵 $C ^ { D K }$ 中的第 $d j$ 项,表示第 $d$ 篇文档中，第 $j$ 个话题包含的词的数目。通过GibbsSampling方法，可以得到 $\theta$ 、 $\phi$ 的后验值，如公式(2)[1]和公式 $( 3 ) ^ { [ 1 ] }$ 所示。

$$
\theta _ { j } ^ { d } = \frac { C _ { d j } ^ { D K } + \alpha } { \displaystyle \prod _ { k = 1 } ^ { k } C _ { d k } ^ { D K } + K \alpha }
$$

$$
{ { \varphi } _ { j } ^ { i } } = \frac { { { c } _ { i j } ^ { V K } } + \beta } { \displaystyle { \prod _ { k = 1 } ^ { \nu } { { c } _ { k j } ^ { V K } } + \nu \beta } }
$$

在推导参数之前，需要预先将话题的数目K设置好，数值越大则话题越多，话题的颗粒度越小，反之亦然。 $\mathsf { K }$ 的取值对LDA模型文本提取和拟合性能影响较大，其最佳的确定可以通过两种方法：一种是词汇被选中的概率 $p ( w | T ) ^ { [ 1 7 ] }$ ，另一种是困惑度(perplexity)[17]本文用困惑度确定 $K ,$ ，困惑度越小，话题的拟合性就越好。困惑度计算如公式(4)[17]所示。

$$
p e r l e x i t y = \exp ( - \frac { \displaystyle \sum _ { i = 1 } ^ { M } \log ( p ( d _ { i } ) ) } { \displaystyle \sum _ { i = 1 } ^ { M } N _ { i } } )
$$

其中, $M$ 为文本数, $N _ { i }$ 为文本 $d _ { i }$ 的长度(即单词个数), $p ( d _ { i } )$ 为LDA模型产生文本 $d _ { i }$ 的概率。

# 3.3 热点话题识别

使用Gibbs Sampling 抽样可以得到"话题-词语”和"文档-话题"的概率分布。对于“话题-词语"分布，每个话题 $z$ 下分布着词语 $w$ 和它在此话题中的概率$p ( w | z )$ ，话题 $z = \{ ( w _ { 1 } , p ( w _ { 1 } \mid z ) ) , \cdots , ( w _ { i } , p ( w _ { i } \mid z ) ) , \cdots ,$ （204号$( w _ { n } , p ( w _ { n } \mid z ) ) \}$ 对于"文档-话题"分布，每个文档d下分布着 $\mathbf { k }$ 个话题的概率分布，形如 $D = \{ P ( z _ { 1 } | d ) , \cdots$ $P ( z _ { i } \mid d ) \cdots , P ( z _ { k } \mid d ) \}$ 0

使用Gibbs Sampling 抽取的话题数量会比较多,而且有些话题可能表达的意思十分接近，有些话题几乎不能表达文档的意思，所以要进行话题选取。话题的选取就要用到上面的"话题-词语"和"文档-话题"的概率分布。经过话题选取之后，确定了文本的全局话题，然后从全局话题中发现热点话题。

(1）选取话题标签词

文本经过聚类，得到了 $H$ 个类，每个类使用GibbsSampling得到了若干个隐含的话题，每个话题下分布着 $n$ 个话题相关的词，对每个话题中的词计算其在该话题所在类文本中的词频(count)、词跨度(cover)和词的长度(length)，则该词的权值(weight)计算公式如(5)所示。

$$
w e i g h t = c o u n t + l e n g t h + c o \nu e r
$$

为了不让词频、词的长度和词跨度的值相差太大，使三者在权值中的比重相同，分别对其进行了量化，具体计算如公式(6)-公式(8)所示。

$$
c o u n t = \frac { c o u n t ( i ) } { c o u n t ( i ) + 1 }
$$

$$
l e n g t h = \frac { l e n g t h ( i ) } { \operatorname* { m a x } ( l e n g t h ( j ) ) }
$$

$$
c o \nu e r = \frac { l a s t ( i ) - f i r s t ( i ) } { c t o t a l }
$$

其中，count(i)为词在文档出现的次数，length(i)为词的长度， $\operatorname* { m a x } ( l e n g t h ( i ) )$ 为文档中词的最大长度,last $( i )$ 为词在文档中最后一次出现的位置,first(i)为词在文档中第一次出现的位置，ctotal是文档中最后一个词的位置。计算完话题中词的权值后，选出权值最大的词作为该话题的标签词。然后存人数据库，数据表的字段名为标签词(tag)、话题(topic)和话题所表示的类 $( H )$ 。

# (2)计算话题的文档概率分布均值

通过GibbsSampling对每个类抽样后，各自得到一个“文档-话题"概率分布矩阵，矩阵表达式如公式(9)所示。

$$
 \begin{array} { r l } { z _ { 1 } \quad } & { \cdots \quad z _ { i } \quad } \\ { d _ { 1 } { | \begin{array} { l l l l l } { p ( z _ { 1 } | d _ { 1 } ) } & { \cdots } & { p ( z _ { i } | d _ { 1 } ) } & { \cdots } & { p ( z _ { k } | d _ { 1 } ) } \\ { \vdots } & { \cdots } & { \vdots } & { \cdots } & { \vdots } \\ { d _ { i } { | \begin{array} { l l l l l } { p ( z _ { 1 } | d _ { i } ) } & { \cdots } & { p ( z _ { i } | d _ { i } ) } & { \cdots } & { p ( z _ { k } | d _ { i } ) } \\ { \vdots } & { \cdots } & { \vdots } & { \cdots } & { \vdots } \\ { d _ { m } { | \begin{array} { l l l l l l } { p ( z _ { 1 } | d _ { m } ) } & { \cdots } & { p ( z _ { i } | d _ { m } ) } & { \cdots } & { p ( z _ { k } | d _ { m } ) } \end{array} | } } \end{array} }  } } \end{array} } \end{array}
$$

上述矩阵中有 $k$ 个话题和 $m$ 条文档，每行为 $k$ 个话题在一条文档中的分布概率，每列为一个话题在 $m$ 个文档中的分布概率。通过上面的矩阵概率分布就可以得出每个话题的分布概率均值，具体计算如公式(10)所示。

$$
\operatorname { A V G } ( Z _ { i } ) = { \frac { \displaystyle \sum _ { j = 1 } ^ { m } p ( z _ { i } \mid d _ { j } ) } { m } }
$$

(3）话题选取

得到了话题的标签词和话题的文档概率分布均值后，构建话题矩阵如公式(11)所示。

$$
\begin{array} { c c c c c } { t o p i c _ { 1 } : \left[ t o p i c _ { 1 } \phantom { - } t o g } & { \cdots } & { a \nu g ( t o p i c _ { 1 } ) } & { \cdots } & { H _ { I } \right] } \\ { \vdots } & { \vdots } & { \cdots } & { \vdots } & { \cdots } & { \vdots } \\ { t o p i c _ { i } : \left[ t o p i c _ { i } \phantom { - } t a g } & { \cdots } & { a \nu g ( t o p i c _ { i } ) } & { \cdots } & { H _ { J } \right] } \\ { \vdots } & { \cdots } & { \vdots } & { \cdots } & { \vdots } \\ { t o p i c _ { n } : \left[ t o p i c _ { n } \phantom { - } t a g } & { \cdots } & { a \nu g ( t o p i c _ { n } ) } & { \cdots } & { H _ { K } \right] } \end{array}
$$

矩阵中一共有 $n$ 个话题(topic)，topici_tag为 topici的标签词，avg(topici)为 topicj 的文档概率分布均值,$H _ { I \setminus } \ H _ { J }$ 和 $H _ { K }$ 属于文本类集合 $\mathrm { ~ H ~ }$ 。由于话题标签词存在相同的情况，所以先以话题标签词分组。认为同一组中的话题表达的意思相近，如果一组中有多个话题选取其中分布概率均值最大的话题，将其删除。接下来按每个话题的均值排序，去除均值极小的话题，因为均值小的话题不能很好地表达文档的意思，剩下的话题就是文档的全局话题。

# (4）热点话题识别

根据LDA模型的原理，每篇文档都是由数个不同的话题按照一定的比例生成的。这里假设一条经过预处理的投诉文本中有不少于话题 $z$ 中百分之几的词则认为这条投诉文本是话题 $z$ 的支持文档。之后使用徐佳俊等[18]的方法计算文档话题支持率，如公式(12)[18]所示。如果在一个时间段内，话题的支持文档的数量或者文档话题支持率超过一个设定的阈值，那么这个话题就是热点话题。

$$
S ( z , t ) = \frac { \mid D _ { i } ^ { t } \mid } { \mid D ^ { t } \mid }
$$

其中, $z$ 表示话题, $t$ 表示时间段， $\lvert D _ { i } ^ { t } \rvert$ 为时间段 $t$ 内话题 $z$ 的所有支持文档数， $\mid D ^ { t } \mid$ 为时间段 $t$ 内所有文档数量。

通过箱型图分析[21进行话题支持文档数或者文档支持率阈值的设定，箱型图的结构如图2所示。

![](images/2c7bcf418f80434218088eb5af6a0fd13b61e599cbbfca6fad46546e7dc42c19.jpg)  
图2箱型图结构[19]

箱型图用来分析数据的分布情况和识别异常值。从图2中可以看出数据分为4个部分，位于上边缘之上和下边缘之下的值为异常值，本文不作考虑。这里将上四分位数这个值设定为支持文档数的阈值，如果某个话题的支持文档数的值超过这个阈值，该话题为热点话题。一方面，箱形图的绘制依靠实际数据，不需要事先假定数据服从特定的分布形式，没有对数据作任何限制性要求，它只是真实直观地表现数据形状的本来面貌；另一方面，箱形图判断异常值的标准以四分位数和四分位距为基础，四分位数具有一定的耐抗性，多达 $2 5 \%$ 的数据可以变得任意远而不会很大地扰动四分位数，所以异常值不能对这个标准施加影响，箱形图识别异常值的结果比较客观。

# 4实验及结果分析

# 4.1 数据来源

本文所使用的数据是某电信公司投诉业务部提供的，实验部分使用2015年3月-2015年4月的投诉文本，其中,3月份有20000多条,4月份有50000多条,前者用于训练提取话题和识别热点话题，后者用于验证热点话题抽取的效果。分词使用的是结巴分词工具[20],停用词词典为哈尔滨工业大学的停用词词典[21]。

# 4.2 语料预处理

(1）由于现有的词典无法完全识别投诉业务中的专业术语和业务词，为了提高分词效果，在某电信公司业务部员工的协助下手动建立了一个自定义的分词词典，词典一共包含了1600个重点业务关键词，由三元组(词语，词频，词性)组成，其中词性标注集采用的是中国科学院的汉语文本词性标注集。三元组中各个属性以空格分开，每个三元组独占一行，保存在Txt文件中。词典实例如表2所示。

表2词典实例表  

<html><body><table><tr><td>词语</td><td>词频</td><td>词性</td></tr><tr><td>短信费用</td><td>1000</td><td>n(名词)</td></tr><tr><td>欠费停机</td><td>2 000</td><td>n</td></tr><tr><td>上网费用</td><td>2000</td><td>n</td></tr><tr><td>有线宽带</td><td>2 000</td><td>n</td></tr><tr><td>畅玩游戏包</td><td>500</td><td>n</td></tr><tr><td>爱动漫信息费</td><td>3000</td><td>n</td></tr><tr><td>夜间流量</td><td>28 641</td><td>n</td></tr></table></body></html>

(2）使用正则表达式去除投诉文本中特有的短语例如"手机号码”、“工单号"等由字母和数字组成的字符串。

(3）引入自定义词典，使用结巴分词工具进行分词并标注词性，保留名词、动词等重要的词语，并去除停用词。

(4)去除无关的高频词，由于投诉文本是由专业的服务人员使用软件按照模板格式录入的，所以会有很多无法反映语义信息的重复词，例如"诉求”、“用户来电表示”、“客户资产编号”、“请处理”、“谢谢"等，预处理的流程如图3所示。

![](images/086414fc3d7d59e3aa467e0487e4372dbcb05d22fe965b7bda4e8c85a86ef8f9.jpg)  
图3预处理的流程图

处理结果示例如表3所示。

表3语料预处理效果表  

<html><body><table><tr><td>原始 文本</td><td>诉求：用户来电表示自己的手机(18067938538)自己很 少上网，为什么在(2015-03)月份的手机上会超出 (210.38)兆的上网流量，前台解释不使用是不会产生 这个上网流量，前台建议用户手机不使用的时候把数 据流量的开关关闭，用户可以登录网厅查询上网的详 单，前台解释用户不认可，用户表示自己没有使用产 生的流量费用自己也是不予承担，烦请处理谢谢，客</td></tr><tr><td>处理 结果</td><td>手机上网月份 手机 超出上网流量 前台 解释 上 网流量 前台建议手机数据流量 开关关闭登录 网厅 查询上网 详单 前台 解释 用户不认可 流量 费用 不予 承担</td></tr></table></body></html>

# 4.3聚类

通过采用模糊 $\mathbf { k }$ -means聚类，k设置为200，并对聚类结果中每类的文本条数进行了统计，其中条数最少为45条，最多的有362条。具体如表4所示

表4文本类分布表  

<html><body><table><tr><td>类中文本条数区间</td><td>类个数</td></tr><tr><td>[0,50]</td><td>20</td></tr><tr><td>[51,100]</td><td>62</td></tr><tr><td>[101,200]</td><td>88</td></tr><tr><td>[201,+)</td><td>40</td></tr></table></body></html>

# 4.4 全局话题抽取

实验利用Gibbs Sampling方法进行参数推理，使用基于Java 的Gibbs Sampling开源工具包(JGibbLDA-v.1.0)[22]，模型参数 $\scriptstyle a$ 、 $\beta$ 默认值为 $5 0 / k$ 和0.1，每个话题下的词语个数设置为10。

对于话题个数 $k ,$ 这里使用公式(4)进行计算，并对生成的话题进行人工评判。根据每类中文本的条数，最终认定条数在[0，50]区间内的类， $k$ 值设置为5；条数在[51,100]区间内的类, $k$ 值设置为10；条数在[101,200]区间内的类， $k$ 值设置为20；条数在[201,300]区间内的类, $k$ 值设置为30；条数在 $[ 3 0 1 , + \infty ^ { \cdot }$ 区间内的类，$k$ 值设置为40。

参数 $\alpha , \beta$ 和 $k$ 设置好后，对每类进行话题的抽取，得到"话题-词语"和"文档-话题"的概率分布，如表5和图4所示。

表5话题-词语示例表  

<html><body><table><tr><td>话题</td><td colspan="2">词语及词概率</td></tr><tr><td rowspan="2"></td><td>金额0.494</td><td>号码0.056宽带0.042接到0.028</td></tr><tr><td>Topic Oth:核实0.028 显示0.015退订0.015</td><td>收费0.015订单0.0151140.015</td></tr><tr><td rowspan="2"></td><td></td><td>违约金0.228不认可0.122无0.046对此0.046</td></tr><tr><td>费用0.031通知0.031收费0.016</td><td>Topic 1th:滞纳金0.031卡里0.031用户不认可0.031</td></tr><tr><td></td><td>Topic 2th:成功0.031 翼支付加油0.031 支付0.031 收到0.031营业0.031办理0.031</td><td>违约金0.092 返利0.077 翼支付0.062 投诉 0.062</td></tr><tr><td></td><td>滞纳金0.33欠费0.101电话0.044上门0.030 Topic 3th:违约金0.030 加油0.030 平台0.030 前台0.015 怎么回事0.015出票0.015</td><td></td></tr><tr><td></td><td>减免0.248前台0.087解释0.087交易0.062 Topic 4th:强烈要求0.038账户0.025情况0.025 营业厅0.025无效0.013号用0.013</td><td></td></tr></table></body></html>

10：222222222202222222.2778022222220555   
20.169230769230769240.230769230769230780.261538461538461550.16923076923076924 0.16923076923076924   
30.20370370370370370.20370370370370370.185185185185185170.2037037037037037 0.2037037037037037   
40.1864406779661017 0.1694915254237288 0.288135593220339 0.1694915254237288 0.1864406779661017   
50.19642857142857142 0.19642857142857142 0.17857142857142858 0.214285714285714270.21428571428571427   
60.203125 0.1875 0.234375 0.1875 0.1875   
70.21153846153846154 0.192307692307692320.19230769230769232 0.21153846153846154 0.19230769230769232   
80.21311475409836064 0.213114754098360640.18032786885245902 0.196721311475409830.19672131147540983   
90.19298245614035087 0.210526315789473670.17543859649122806 0.192982456140350870.22807017543859648   
100.2 0.2166666666666667 0：.183333333333332 0.216666666666667 0.1833333333333332   
110.18556701030927836 0.1134020618556701 0.20618556701030927 0.206185567010309270.28865979381443296   
120.19642857142857142 0.17857142857142858 0.19642857142857142 0.19642857142857142 0.23214285714285715   
130.2 0.21666666666666667 0.2 0.18333333333333332 0.2   
140.2 0.2 0.18181818181818182 0.21818181818181817 0.2   
150.20370370370370370.20370370370370370.18518518518518517 0.2037037037037037 0.2037037037037037   
160.22807017543859648 0.21052631578947367 0.192982456140350870.17543859649122806 0.19298245614035087   
170.203125 0.203125 0.21875 0.203125 0.171875   
116   
190.211538461538461540.19230769230769232 0.192307692307692320.211538461538461540.19230769230769232   
200.16923076923076924 0.2153846153846154 0.18461538461538463 0.2 0.23076923076923078   
210.196428571428571420.19642857142857142 0.17857142857142858 0.19642857142857142 0.23214285714285715   
220.21818181818181817 0.18181818181818182 0.18181818181818182 0.2 0.21818181818181817   
230.211538461538461540.19230769230769232 0.19230769230769232 0.21153846153846154 0.19230769230769232   
240.1896551724137931 0.1724137931034483 0.1896551724137931 0.20689655172413793 0.2413793103448276   
250.21153846153846154 0.19230769230769232 0.192307692307692320.21153846153846154 0.19230769230769232   
260.2 0.2 0.21818181818181817 0.181818181818181820.2   
270.1935483870967742 0.20967741935483872 0.1935483870967742 0.22580645161290322 0.1774193548387097   
280.206896551724137930.206896551724137930.17241379310344830.1896551724137931 0.22413793103448276   
290.233333333333334 0.2166666666666667 0.20.16666666666 0.1833333333333332   
300.214285714285714270.17857142857142858 0.196428571428571420.21428571428571427 0.19642857142857142   
310.194029850746268660.2089552238805970.223880597014925380.17910447761194030.19402985074626866

表5和图4是某个类的"话题-词语"和"文档-话题"的概率分布，表4中有每个话题的10个话题词及其词语的话题分布概率 $p ( w | z )$ ，图4中每行为5个话题在一条文档中的分布概率，每列为一个话题在31条文档中的分布概率。

通过话题的选取，总共抽取了5130个话题，然后对每个话题提取它的标签词，计算文档概率均值，去除均值极小的话题，保留相同标签词中均值最大的话题，剩下299个全局话题，示例结果如图5所示。

图5话题示例  

<html><body><table><tr><td>t_topic</td><td>topic</td><td>theta</td></tr><tr><td>套餐</td><td>宽带/工作人员/用户不认可/营业厅/工单/固话移机/优惠/套餐/享受/移机0.20845</td><td></td></tr><tr><td>电脑</td><td>电脑/话费/手机/套餐/海信/核实/金蛋/费用/退费/退货</td><td>0.20784</td></tr><tr><td>违约金</td><td>违约金/返利/翼支付/投诉/成功/翼支付加油/支付/收到/营业/办理</td><td>0.20159</td></tr><tr><td>收取</td><td>前台/收取/办理/告知/师傅/外线/后台/移机/号码/</td><td>0.20141</td></tr><tr><td>平板</td><td>平板/办理/杭州/告知/核实/支付/强烈要求/拿到/发现/</td><td>0.20026</td></tr><tr><td>移机</td><td>移机/收取/核实/套餐/减免/投诉/费用不认可/业务/区域/无效</td><td>0.20024</td></tr><tr><td>分组</td><td>分组/公众/广电/频道/改回/节目/高清/机顶盒/后台/故障</td><td>0.20015</td></tr><tr><td>减免</td><td>减免/前台/解释/交易/强烈要求/账户/情况/营业厅/无效/号用</td><td>0.19944</td></tr><tr><td>金额</td><td>金额/号码/宽带/接到/核实/收费/订单//显示/退订</td><td>0.19836</td></tr><tr><td>发短信</td><td>发短信/手机/对此/退费/功能/收到/上网/联系电话/地址/更换</td><td>0.19820</td></tr><tr><td>邮箱</td><td>邮箱/号码/无效/功能/短信/账号/用户不认可/建议/亚洲/公司</td><td>0.19771</td></tr><tr><td>服务质量</td><td>服务质量/办理/对此/监督/管应/工单/导致/前期/游戏/免责</td><td>0.19765</td></tr></table></body></html>

其中,t_topic为话题标签,topic为话题下的分布词语,theta为话题在文档中分布概率均值。

# 4.5热点话题识别实验结果分析

根据第3节的方法，假设一条经过预处理的投诉文本中有不少于话题z中一定比例的词，则认为这条投诉文本是话题 $z$ 的支持文档。这里设置为$30 \%$ ，因为实验中每个话题的词语个数为10，即每条预处理后的投诉文本中词语与话题中词语的交集大于等于3个。通过分析话题支持文档数的箱型图如图6所示。得出结果如表6所示。

![](images/ae24bbdfd864a9a8b8d4579a1128d76d1d9b5c3651fd3c5acc4653455c4a0d53.jpg)  
图4文档-话题示例  
图6支持文档数箱型图

通过上述分析，这里将支持的文档数不低于3000的话题定义为热点话题。由于话题个数有299个，文中分别选取了10个热点话题和10个一般话题进行说明如表7所示。

表6支持文档数的数值分布  

<html><body><table><tr><td>相关内容</td><td>数值</td></tr><tr><td>话题个数</td><td>299</td></tr><tr><td>支持文档数均值</td><td>1760.81</td></tr><tr><td>最大值</td><td>8076</td></tr><tr><td>最小值</td><td>3</td></tr><tr><td>中位数</td><td>1288</td></tr><tr><td>%25分位数</td><td>424</td></tr><tr><td>%50分位数</td><td>1288</td></tr><tr><td>%70分位数</td><td>2628.5</td></tr></table></body></html>

表7话题对比表  

<html><body><table><tr><td>热点话题</td><td>支持文档数</td><td>一般话题</td><td>支持文档数</td></tr><tr><td>账单</td><td>8 070</td><td>维修</td><td>1 643</td></tr><tr><td>用户不认可</td><td>6 797</td><td>包月费</td><td>1058</td></tr><tr><td>副卡</td><td>6733</td><td>违约金</td><td>526</td></tr><tr><td>短号</td><td>6408</td><td>上门移机</td><td>428</td></tr><tr><td>路由器</td><td>6342</td><td>服务质量</td><td>349</td></tr><tr><td>数据流量</td><td>5360</td><td>一号双机</td><td>249</td></tr><tr><td>国内上网</td><td>4848</td><td>翼支付</td><td>240</td></tr><tr><td>线路</td><td>4262</td><td>租用</td><td>205</td></tr><tr><td>补卡</td><td>4 341</td><td>手机信号</td><td>55</td></tr><tr><td>宽带</td><td>3225</td><td>彩铃</td><td>48</td></tr></table></body></html>

从表7中可以看出移动用户对"上网”、“数据流量”、“账单"等比较在意，这与现实中用户的关注基本符合，所以本文的话题抽取和热点识别方法是有效的。

# 4.6话题测试实验结果分析

使用2015年4月的语料进行测试本文算法获取的热点话题效果，先按表7中话题支持文档数，从低至高分别选择三个热点话题和三个一般话题进行实验。计算热点话题和一般话题在2015年4月30天中的支持文档数，其变化趋势如图7和图8所示。

![](images/418ec427e037290812049e4559fb7479bda4cdc960742194d29fa878a426606a.jpg)  
图7热点话支持文档数变化趋势

![](images/87233e95ebb817bbb20a95f5967a6bc5d9727c7974a3dc9dfb8485a92cf2e5eb.jpg)  
图8一般话题支持文档数变化趋势

对比图7和图8可以看出热点话题的每天支持文档数普遍比一般话题高；图8中一般话题的变化趋势大部分时间都比较平稳，有时也会出现急剧的爬升和下落，但支持文档数还是不高，最低点到最高点的变化幅度不是十分明显。从图7可以发现热点话题变化趋势强弱程度比较明显，最低点到最高点的变化幅度基本上都超过100，有一个比较突出的峰值，总体都经历了“开始-高潮-衰落"的过程。

数据出现以上现象，从现实原因来说，是因为热点话题与用户的生活息息相关，都是大部分用户使用非常频繁的业务所出现的问题，所以它的强度变化趋势就比较明显。通过对不同话题进行趋势分析之后，可以发现它们的强度变化趋势与现实的实际情况是比较吻合的，在一定程度上能够反映本文算法获取热点话题的效果。

# 5结语

通过实验说明本文在基于投诉文本的热点话题识别问题研究中取得了一定成果。在预处理阶段，构建了一个移动领域的词典，对于今后该领域的语料处理有一定的帮助；在热点话题发现阶段，使用了聚类技术，使得类中的文本联系更加紧密；再通过LDA模型进行话题抽取，使话题表达更加细粒化，针对性更强;在话题的选取上，考虑了话题对文档表达能力的强弱以及话题与话题之间的相似性。

本文对移动投诉领域话题识别和追踪的初探，还存在一定的不足，没有考虑到话题之间的语义关系，使用的都是统计学的方法。接下将对此方法做出改善，把更多的语义信息融合到话题模型中；并对话题之间的关系进行研究，发掘话题间的联系以及动态获取话题的演化。

# 参考文献：

[1]David M B,John D L.Dynamic Topic Model[C]//Proceedings of the 23rd International Conference on M achine Learning. Pittsburgh.2006:113-120.   
[2]张培晶，宋蕾．基于LDA的微博文本主题建模方法研究述 评[J]．图书情报工作，2012，56(24)：120-126.(Zhang Peijing， Song Lei. Overview on Topic Modeling of Microblogs Text Based on LDA [J]. Library and Information Service,2012,56(24):120-126.)   
[3]Weng J，Lim E P, Jiang J，et al. TwiterRank:Finding Topic-sensitive Influential Twitterers[C]/Proceedings of the 3rd ACM International Conference on Web Search and Data Mining.ACM,2010:261-270.   
[4]Hong L,Davison B D.Empirical Study of Topic Modeling in Twiter [C]//Proceedings of the 1st Workshop on Social Media Analytics.ACM,2010: 80-88.   
[5]Rosen-Zvi M,Griffiths T, Steyvers M,et al. The AuthorTopic Model for Authors and Documents[Cl// Proceedings of the 20th Conference on Uncertainty in Artificial Intelligence. AUAI Press, 2004: 487-494.   
[6]Zhao W X, Jiang J,Weng J, et al. Comparing Twiter and Traditional Media Using Topic Models [C]// Proceedings of the 33rd European Conference on Information Retrieval. Springer Berlin Heidelberg,2011: 338-349.   
[7]Ramage D,Hall D,Nallapati R,et al. Labeled LDA:A Supervised TopicModel for CreditAtributionin Multi-labeledCorpora[C]//Proceedingsofthe2009 Conference on Empirical Methods in Natural Language Processing.2009: 248-256.   
[8]张晨逸，孙建伶，丁轶群．基于 MB-LDA 模型的微博主题 挖掘[J]．计算机研究与发展，2011，48(10):1795-1802. (Zhang Chenyi,Sun Jianling,Ding Yiqun.Topic Mining for Microblog Based on MB-LDA Model [J]． Journal of Computer Research and Development, 2011， 48(10): 1795-1802.)   
[9]唐晓波，向坤.基于 LDA 模型和微博热度的热点挖掘[J]. 图书情报工作，2014，58(5):58-63.(Tang Xiaobo，Xiang Kun.Hotspot Mining Based on LDA Model and Microblog Heat[J].Library and Information Service，2014,58(5): 58-63.)   
[10]朱颖．基于微博的热点话题发现[D]．重庆：西南大学,

2014.(Zhu Ying．Hot Topic Extraction from Microblogs [D].Chongqing: Southwest University,2014.)   
[11] 伍万坤，吴清烈,顾锦江．基于 EM-LDA 综合模型的电商 微博热点话题发现[J]．现代图书情报技术，2015(11): 33-40.(Wu Wankun，Wu Qinglie,Gu Jinjiang.Hot Topic Extraction from E-commerce Microblog Based on EM-LDA Integrated Model[J]. New Technology of Library and Information,2015(11): 33-40.)   
[12] Rosen-Zvi M, Chemudugunta C, Grifiths T,et al. Learning Author-topic Modelsfrom Text Corpora[J].ACM Transactions on Information Systems,2010,28(1):Article No.4.   
[13] Zhao W X,Jiang J,He J,et al. Topical Key Phrase Extraction from Twitter [C]//Proceedings of the 49th Annual Meeting of theAssociation for Computational Linguistics.2011: 379-388.   
[14] Ramage D,Dumais S T,Liebling D J. Characterizing Microblogs with Topic Models [C]//Proceedings of the 4th International Conference on Weblogs and Social Media. 2010.   
[15]吴夙慧，成颖，郑彦宁，等.K-means 算法研究综述[J]．现 代图书情报技术,2011(5):28-35.(Wu Suhui, Cheng Ying, Zheng Yanning, et al. Survey on K-means Algorithm[J]. New Technology of Library and Information Service，2011(5): 28-35.)   
[16] 朱成文，李兵，胡奎.HMM参数估计的 Gibbs 抽样算法[J]. 计算机工程与应用,2012,18(18):57-60.(Zhu Chengwen,Li Bing,Hu Kui.Algorithm of Parameter Estimation of HMM via Gibbs Sampling. Computer Engineering and Applications, 2012,48(18): 57-60.)   
[17]关鹏，王曰芬．科技情报分析中LDA 主题模型最优主题数 的确定方法研究[J]．现代图书情报技术，2016，32(9): 42-50.）(Guan Peng，Wang Yuefen. Identifying Optionan Topic Numbers from Sci-Tech Information with LDA Model[J].New Technology of Library and Information, 2016, 32(9): 42-50.)   
[18] 徐佳俊，杨飚，姚天昉，等．基于 LDA 模型的论坛热点话 题识别和追踪[J]．中文信息学报，2016,30(1):43-50.(Xu Jiajun,Yang Yang,Yao Tianfang， et al.LDA Based Hot Topic Detection and Tracking for the Forum [J]. Journal of Chinese Information Processing,2016,30(1): 43-50.)   
[19]张良均，王路，谭立云，等.Python 数据分析与挖掘实战 [M]．机械工业出版社,2015.(Zhang Liangjun，Wang Lu, Tan Liyun,et al. Python Practice of Data Analysis and Mining [M]. Machinery Industry Press,2015.)

[20]jieba[CP/OL].[2016-11-23].http:/www.oschina.net/p/jieba.

[21]哈尔滨工业大学停用词词典[OL].[2016-11-23].http:// more.datatang.com/data/13281.(Stop Word Dictionary by Harbin Institute of Technology [OL].[2016-11-23].http:// more.datatang.com/data/13281.)

[22]JGibbLDA: A Java Implementation of Latent Dirichlet Allocation (LDA）Using Gibbs Sampling for Parameter Estimation and Inference [CP/OL]. [2016-11-23]. http:/ sourceforge.net/projects/jgibblda.

# 作者贡献声明：

黄孝喜，方小飞，谌志群：提出研究思路，设计研究方案;  
方小飞，黄孝喜，王荣波：分析数据，进行试验，论文起草;

王小华，黄孝喜，谌志群：论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:1484514227@qq.com。  
[1]方小飞.mobiledata.zip．移动投诉文本.  
[2]方小飞.dict.txt.投诉关键词词典.

收稿日期:2016-11-10  
收修改稿日期:2016-12-18

# Identifying Hot Topics from Mobile Complaint Texts

Fang Xiaofei’Huang Xiaoxi1Wang Rongbo'Chen Zhiqun1 Wang Xiaohua 1, 2 1(Department of Computer Science, Hangzhou Dianzi University, Hangzhou 310018, China) ² (China Jiliang University,Hangzhou 310o18, China)

Abstract:[Objective]This paper aims to extract valuable information from large amount of complaint texts with the helpof Chinese message procesing technologies.[Methods] First,we analyzed the characteristics of the complaint texts,and then clustered them byk-means algorithm.Second, we extracted topics fromthe texts ofeach category with the LDA model.In the mean time, we calculated the weight of the word ofeach topic,as wellas the mean of document probability distribution.Third,we analyzed topics with the highest means and used the document supporting rates to identify the trending ones.[Results]The document supporting rates ofthe topics extracted by this study was three times higher than the average ones.[Limitations] We did not investigate the semantic relationship among the topics. [Conclusions]The LDA model is an effective method to detect hot topicsofthe mobile complaints and indicates some future studies.

Keywords: Mobile Complaints $\mathbf { k }$ -means Topic Detection LDA Model