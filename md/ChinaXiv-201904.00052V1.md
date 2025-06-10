# 基于PageRank的多维度微博用户影响力度量‘

罗芳¹，徐 阳¹，蒲秋梅²，邱奇志1

(1．武汉理工大学 计算机科学与技术学院，武汉 430063;2．中央民族大学 信息工程学院，北京 100081)

摘要：近年来社交网络的发展推动了多个领域的研究，如舆情监控、广告推荐、意见领袖识别等，而社交网络用户的影响力度量则是以上研究的基础。以新浪微博为研究对象，旨在提出一种适用性更广、考虑因素更全面的微博用户影响力度量算法，将用户基本属性、用户交互行为和用户博文内容三个维度因素融入传统 PageRank 算法中，提出了一种多维度微博用户影响力度量算法——MDIR(multi-dimension influence rank)。实验结果表明，MDIR 算法相较于其他常用的五种影响力度量算法，能更加全面、真实地反映微博用户的实际影响力。

关键词：微博；用户影响力；PageRank；用户行为 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.10.0798

Multi-dimensional measure of Microblog user influence based on PageRank

Luo Fang1, Xu Yang1, Pu Qiumei², Qiu Qizhi1 (1.SchoolofComputerScience&Technology，WuhanUniversityofTechnology，WuHan430063，China;2.Schoolof Information Engineering,Minzu University ofChina,Beijinglooo81,China)

Abstract: Inrecent years,thedevelopmentofsocial networks had promoted research inmanyfields,such aspublicopinion monitoring,advertisingrecommendationandopinion leaderidentificationetc.Theinfluence measurementofsocialnetwork users is thebasisoftheabove research.This paper integrated the basicatributesofuser,interaction behaviorof userand user'smicroblog content intothePageRank algorithm,therefore，it proposeda multi-dimensionaluser influence measurement algorithm:MDIR(multi-dimension influence rank).The experiment shows that,the MDIR can reflect the actual influenceof microblog users more comprehensivelyand realistically than other five commonlyused influence measurement algorithms.

Keywords:Microblog;user influence;PageRank;user behavior

# 0 引言

随着互联网技术的迅速发展，以博客技术为代表，围绕用户互动与个性体验的互联网应用技术进一步推动了以开放共享为特征的Web2.0时代向具有信息融合特征的Web3.0时代过渡。微博是微型博客的简称，是一种基于关注机制分享简短实时信息的广播式的社交网络平台。据CNNIC发布的第41次《中国互联网络发展状况统计报告》中的数据显示[1]，截至2017年12月，我国微博用户规模为3.76亿，推动用户使用率持续增长达到 $40 . 9 \%$ ，较2016年12月上升3.8个百分点。微博平台中每个用户除了发布自己原创的微博信息外，还可以随意的转发、评论、点赞其他用户的微博信息，不同用户之间的相互转发、评论、点赞等行为促成了微博信息传播网络的形成。另外，微博平台还具有用户使用门槛较低、微博内容短小精悍、可阅读性强的特点，这些特点使得微博信息的传播速度更快以及影响范围更广。

微博用户的影响力可以理解成是某用户发布微博后引起其他用户行为改变的能力。在微博信息传播的过程中，不同影响力的用户对微博信息的操作（如转发、评论等）和态度（如支持、反对等)，会对微博信息的传播范围与传播深度产生不同的影响。用户影响力的度量在网络舆情监控、广告投放、用户推荐等领域有着重要的应用。对于舆情监控而言，监控过程中需要对某些高影响力的用户采取特别措施，以免舆情泛滥；对于广告投放而言，选取高影响力的用户作为初始的广告传播的中心可以使得传播效果最大化；对于用户推荐而言，用户感兴趣领域的"意见领袖"[2]常常都是默认推荐的对象。综上所述，用户影响力的度量在当前的热点研究中扮演着不可忽视的角色。

为了合理地度量微博用户的影响力，本文在PageRank算法的基础上进行改进，并提出了MDIR（multi-dimensioninfluencerank）算法，相比较于其他影响力度量算法而言，MDIR算法考虑的影响因素更为全面、合理，其得到的用户影响力排名也更为客观。

# 1 相关工作

目前，国内外学者对于社交网络用户影响力度量的研究一般基于用户的基本属性、交互行为以及发布的博文内容三个方面：

a）基于用户基本属性的影响力度量方法。

用户的基本属性是用户影响力最原始的体现，常见的基本属性如粉丝数、发博数等，这些大多都是当前流行的影响力度量算法所考虑的特征因素。Cha等人[3]选取Twitter中用户的粉丝数、转发数、评论次数三个属性，按节点度计算用户的影响力并对比所得结果的相关性，其实验结果表明用户粉丝数的多少与用户微博被转发数、被评论数并不成正比例关系。Mao等人[4对微博用户的活跃度进行了分析，但是其仅仅只通过评论数进行分析，并没有分析其他因素，也没有排除微博平台中“僵尸粉"对用户影响力的干扰。

b)基于用户交互行为的影响力度量方法。

用户间的交互行为是用户影响力的直接体现，常见的用户交互行为有转发、评论、提及、点赞等。张昊等人[5]基于用户的基本属性与交互行为提出了UI算法，其首先引出了“用户影响力”与“用户被影响力”的概念，“用户影响力是基于用户的粉丝数、发博数、微博被转发数等属性计算得来，而“用户被影响力”则是基于粉丝用户与关注用户之间的交互情况，如粉丝用户对某关注用户的微博进行转发、评论的次数占该粉丝用户对其所有关注用户的微博进行转发、评论的总数的百分比，但是作者对用户各种交互行为采取的量化手段是归一化，这并不符合实际微博传播情况；王顶等人[在张昊等人研究的基础上考虑了不同行为的权重值，其实验部分也从数据出发对排序结果作出了详细的论证，但是其只基于用户间的关注关系构建网络拓扑，没有考虑到微博中存在大量的“僵尸粉”，即关注了某用户之后并不对其产生交互行为，这类粉丝在微博的传播中起不到作用；孙红等人[7综合考虑用户的实际微博活动行为以及微博网络的拓扑结构，进而提出了MBUI-Rank算法，其实验结果表明该算法计算出的用户影响力较为准确与客观；齐超等人[8]在PageRank算法的基础上加以改进提出了BWPR算法，分别对转发、评论、提及三种行为构建拓扑网络，虽然该算法在实验中得到了很好的效果，但是其只考虑了用户交互行为这种显性特征，没有考虑隐性的用户兴趣偏好。

c）基于博文内容的影响力度量方法。

用户所发布的微博携带着大量信息，通过对博文内容进行分析可以获取用户所感兴趣的话题或者用户的情感属性，这些特征也被广泛地应用在影响力度量的领域中。Weng 等人[9]基于Twitter数据提出了TwitterRank 算法，其不仅考虑网络结构，而且基于推文内容分析了每个用户所发推文的话题相似性，最后将用户在每个主题中的影响力值求和得到用户在整个网络中的影响力值。虽然此方法在实验中得到了不错的效果，但是其也只考虑了推文数目和话题相似度，忽略了用户之间的交互行为特征。师亚凯等人[0]通过引入网络拓扑结构中用户行为与基于博文内容的用户兴趣相似度来衡量用户间的影响力，但是没有考虑用户的粉丝数、认证情况等用户基本属性。

鉴于当前研究的不足之处，本文在PageRank 算法的基  
础上进行改进，提出了一种融合用户基本属性、用户交互行  
为、用户博文内容的多维度微博用户影响力度量算法-MDIR（multi-dimensionin fluence rank）。

# 2 MDIR算法基本原理

# 2.1PageRank 算法

PageRank算法是互联网中广泛用于网页排名的经典算法[1]，其核心思想是研究网络的拓扑结构并计算页面中的入链数（即页面链接的次数)，从而确定该页面的排名顺序。PageRank 算法的相关公式如式（1）所示。其中： $P R ( p _ { i } )$ 为页面 $p _ { i }$ 的PageRank值； $I ( p _ { i } )$ 为页面 $p _ { i }$ 的入链集合； $\left| O ( p _ { j } ) \right|$ 为页面 ${ \boldsymbol { p } } _ { j }$ 的出链集合中网页的数量；d是阻尼系数，通常采用$\mathbf { d } = 0 . 8 5 ^ { [ 1 2 ] }$ 。

$$
P R ( p _ { i } ) = ( 1 - d ) + d \sum _ { p _ { j } \in I ( p _ { i } ) } { \frac { P R ( p _ { j } ) } { \left| O ( p _ { j } ) \right| } }
$$

传统的PageRank算法用于微博用户的影响力度量时，将微博平台中的用户类比为Web网络中的网页，仅仅考虑了用户与用户之间的关注与被关注关系。若直接采用PageRank算法度量用户影响力会存在以下问题：

a)初始PR值的确定不够客观。

PageRank算法对于网页的初始PR值采取的计算方法是取平均数，这样的方法并不适用于微博用户影响力度量。由于每个用户间的差异（具体表现在用户的粉丝数、发博数、是否认证等)，若直接采用取平均数的方式得到用户的初始PR值，则会忽略用户自身属性对微博传播所带来的影响，从而导致最后计算出的用户影响力排名不够客观。

b)PR值的分配方式不够合理。

网页将自身PageRank值均匀地分给它所链出的网页，这样的计算方式对于微博用户显然不合理。因为不是所有用户都能做到对他们关注的所有用户一视同仁，大多数用户只对其中的一部分表现出兴趣从而愿意为其投入更多的注意力。

c）网络结构的考虑不够全面。

PageRank算法在微博中的应用是基于用户的关注关系，由此算法很大程度上依赖于粉丝数。但由于粉丝中可能包含很多无效的僵尸粉与沉默粉，所以粉丝数并不能真实地反映用户的影响力。此外，微博用户是动态的，他们之间存在着各种各样的行为，如转发微博、评论微博等。这些行为对用户微博的传播有着明显的推动作用，而且这些行为不仅仅发生在有关注关系的用户之间，如新浪微博推出的“微吧”和“微话题”功能，用户不需关注即可获取微吧或微话题内其他用户所发的消息并且可以对其进行转发、评论等操作。

# 2.2MDIR影响力度量因素

针对上文分析的PageRank算法在度量用户影响力时存在的问题，本文提出的MDIR算法综合考虑了以下三个维度的因素：

a)基于用户基本属性的影响因素。

用户自身的基本属性如用户的粉丝数、发博数、认证情况。用户的粉丝数、发博数对于用户的影响力而言是一个比较直观的影响因素。通常来讲，用户的粉丝数越多，意味着能看到该用户发布的微博信息的用户也越多，从而导致该用户所能影响到的人数也越多；如果说用户的粉丝数决定了该用户影响力的范围，那么用户的发博数则决定了该用户影响力的深度。对于相同规模的粉丝群体，用户的发博数越多，则每个粉丝被该用户微博信息所影响到的次数也会随之增多即该用户影响力的深度越深；用户的认证情况对用户的影响力而言是一个潜在的影响因素，如果用户通过新浪微博认证，则其微博的可信度越高，从而使得该微博被评论和被转发的可能性越大，因此用户影响力越大。

b)基于用户间交互行为的影响因素。

在微博平台中，用户所发布、转发的微博都以潜移默化的方式影响着他们的粉丝，而粉丝的评论、转发、提及等行为则又反过来推动微博信息的传播。微博信息被转发的次数越多，意味着该微博信息被传播得越广；微博信息被评论的次数越多，意味着该微博信息受关注度越高；用户被提及次数越多，说明该名用户在其粉丝群体中建立的威信度越高。

c）基于用户博文内容的影响因素。

用户发布与转发的微博信息可以看做是用户个人兴趣的体现，通过对博文内容的挖掘可以得到每条微博的主题分布向量，而综合一个用户所有微博的主题分布向量，可以得到代表一个用户兴趣的主题分布向量，本文简称为兴趣分布向量。Weng等人[9]指出，在Twitter中用户感兴趣的话题越相似，则他们相互关注的可能性越大。虽然其在Twitter平台下做的实验，但由于Twitter与微博的结构具有相似性，其结果也可以被用于微博平台。李志宏等人[13]指出微博用户间具有“同好性”,即用户更倾向于与自己有相同兴趣爱好的用户建立关系（转发关系、评论关系等）。

综上所述，本文提出的MDIR算法基于用户的基本属性，计算出用户的初始影响力值，解决了传统PageRank算法的不够客观的缺点；基于用户间的交互行为与用户博文内容，计算用户间的传播意愿，从而改进了传统PageRank 的影响力均值分配的问题；基于用户的交互行为，构建用户微博信息的传播网络，有效地排除了大量“僵尸粉”“沉默粉”对用户影响力的干扰。

# 3 MDIR算法具体实现

# 3.1微博传播网络的构建

根据2.2节所述，本文通过用户的转发、评论、提及行为构建一个微博信息的传播网络简称微博传播网络，其定义如下：

定义1微博传播网络。设微博传播网络为 $G = ( V , ~ E , ~ B )$ ，其中 $V = \Re \nu _ { i } | \mathcal { \bar { \ell } } = 1 , 2 , 3 , . . . , n \}$ 为微博传播网络中节点的集合， $\nu _ { i }$ 代表有涉及到转发、评论、提及三种行为中一种或多种的微博用户； $E = \{ ( \nu _ { i } , \nu _ { j } ) | \mathbb { V } _ { i } , \nu _ { j } \in V , i \not = j , \nu _ { i } R \nu _ { j } \vee \nu _ { i } C \nu _ { j } \vee \nu _ { i } M \nu _ { j } \}$ 为微博传播网络中边的集合， $\nu _ { i } R \nu _ { j }$ 代表用户 $\nu _ { i }$ 转发过用户 $\nu _ { j }$ 的微博， $\nu _ { i } C \nu _ { j }$ 代表用户 $\nu _ { i }$ 评论过用户 $\nu _ { j }$ 的微博， $\nu _ { i } M \nu _ { j }$ 代表用户 $\nu _ { i }$ 在微博中提及过用户 $\nu _ { j }$ ； $B = \{ B _ { i , j } \mid ( \nu _ { i } , \nu _ { j } ) \in E \}$ 为微博传播网络中边权集合，$B _ { i , j }$ 代表用户 $\nu _ { i }$ 对用户 $\boldsymbol { \nu } _ { j }$ 的转发、评论、提及次数的带权之和。

三种行为对微博的传播有着不同的贡献比例，所以 $B _ { i , j }$ 应该综合考虑每种行为的贡献比例。本文用 $\alpha , \beta , \gamma$ 分别表示转发、评论、提及三种行为的贡献比例，其公式如式（2）所示。

$$
B _ { i , j } = { \ a } R _ { i , j } + \beta C _ { i , j } + \gamma M _ { i , j }
$$

其中： ${ \bf R } _ { \mathrm { i , j } }$ 、 $C _ { i , j }$ 、 $M _ { i , j }$ 为用户 $\nu _ { i }$ 对用户 $\nu _ { j }$ 的转发、评论、提及次数。对于 $\alpha , \beta , \gamma$ 的取值本文根据序关系法确定，首先将各个变量的重要程度做成对比较，然后将比较的结果按一定的方式聚合起来，最终经过计算得到 $\alpha , \beta , \gamma$ 的值。对 $\alpha , \beta , \gamma$ 构建一个判断矩阵 $\mathbf { \mathcal { A } }$ ，如式（3）所示。

$$
\mathbf { A } = { \left[ \begin{array} { l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { a _ { 1 3 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { a _ { 2 3 } } \\ { a _ { 3 1 } } & { a _ { 3 2 } } & { a _ { 3 3 } } \end{array} \right] } = { \left[ \begin{array} { l l l } { \alpha / \alpha } & { \alpha / \beta } & { \alpha / \gamma } \\ { \beta / \alpha } & { \beta / \beta } & { \beta / \gamma } \\ { \gamma / \alpha } & { \gamma / \beta } & { \gamma / \gamma } \end{array} \right] }
$$

矩阵 $\textbf {  { A } }$ 中的元素 $a _ { i j }$ 代表第i个变量对第 $\mathrm { j }$ 个变量的相对重要性，在矩阵 $\textbf {  { A } }$ 中元素的性质有 $a _ { i j } = 1 / a _ { j i }$ ， $a _ { i j } = a _ { i k } ^ { \mathrm { ~ * ~ } } a _ { k j }$ ， $a _ { i i } = 1$ u接着根据Saaty 等人总结出的变量间相对重要性等级表[14]（表1）结合三种行为的相对重要关系可以对矩阵 $\textbf {  { A } }$ 中的元素赋值。其中，转发行为与评论行为相比处于略微重要到相当重要之间，故取 $a _ { 1 2 } = 4$ 。转发行为同提及行为相比，处于明显重要与绝对重要之间，故取 $a _ { 1 3 } = 8$ 。评论关系和提及关系相比，处于同等重要与略微重要之间，故取 $a _ { 2 3 } = 2$ 。将${ a } _ { 1 2 } \mathrm { . }$ $. a _ { 1 3 } . a _ { 2 3 }$ 代入到式(3)中，得到的最终矩阵如式(4)所示。

$$
\pmb { A } = \left[ \begin{array} { c c c } { 1 } & { 4 } & { 8 } \\ { 0 . 2 5 } & { 1 } & { 2 } \\ { 0 . 1 2 5 } & { 0 . 5 } & { 1 } \end{array} \right]
$$

联立方程组，最后 $\alpha , \beta , \gamma$ 的值如式（5）所示。

$$
\left\{ { \begin{array} { l } { \alpha = 0 . 7 2 7 } \\ { \beta = 0 . 1 8 2 } \\ { \gamma = 0 . 0 9 1 } \end{array} } \right.
$$

表1变量之间的相对重要性  
Table1 Relative Importance between variables   

<html><body><table><tr><td>相对重要程度</td><td>定义</td><td>说明</td></tr><tr><td>1</td><td>同等重要</td><td>两个变量同样重要</td></tr><tr><td>3</td><td>略微重要</td><td>一个变量比另一个变量稍微重要</td></tr><tr><td>5</td><td>相当重要</td><td>一个变量比另一个变量更为重要</td></tr><tr><td>7</td><td>明显重要</td><td>一个变量比另一个变量更为重要，</td></tr><tr><td></td><td></td><td>且已有实践证明</td></tr><tr><td>9</td><td>绝对重要</td><td>重要程度可以肯定</td></tr><tr><td>2，4，6，8</td><td colspan="2">两个相邻判断的中间值需要折中时采用</td></tr></table></body></html>

# 3.2 初始影响力计算

本文从用户的粉丝数、发博数、认证情况三个基本属性入手计算用户的初始影响力值。由于不同用户之间的粉丝数、发博数差异巨大，本文采用一种对数归一化的方法对用户的粉丝数、微博数进行处理，降低数据的跨度。计算公式如式（6）所示。

$$
I n i t I n f l ( \nu _ { i } ) { = } \frac { l g \left( N F ( \nu _ { i } ) \right) } { l g \left( N F _ { m a x } \right) } { + } \frac { l g \left( N W ( \nu _ { i } ) \right) } { l g \left( N W _ { m a x } \right) } { + } V e r i f y ( \nu _ { i } )
$$

其中： $N F ( \nu _ { i } )$ 代表用户 $\nu _ { i }$ 的真实粉丝数，即用户 $\nu _ { i }$ 在微博传播网络中的入度； $N F _ { m a x }$ 代表真实粉丝数最多的用户的真实粉丝数； $N W \left( \nu _ { i } \right)$ 代表用户 $\nu _ { i }$ 的发博数； $N W _ { m a x }$ 代表发博数最多的用户的发博数；Verify $\left( \nu _ { i } \right)$ 代表用户 $\nu _ { i }$ 的认证情况，Lappas T等人[15]指出，当用户 $\nu _ { i }$ 得到了微博认证时 $V e r i f y ( \nu _ { i } ) { = } 0 . 5$ ，否则 $V e r i f y ( \nu _ { i } ) { = } 0$ 的取值最为合适。

# 3.3 MDIR算法

MDIR算法通过合理的策略重新计算了目标用户的影响力，其计算公式如式（7）所示。

$$
M D I R ( \nu _ { i } ) = ( 1 - d ) + d \sum _ { \nu _ { j } \in i n ( \nu _ { i } ) } r a t i o { \left( \nu _ { j } , \nu _ { i } \right) } ^ { * } M D I R ( \nu _ { j } )
$$

其中： $i n ( \nu _ { i } )$ 代表用户 $\nu _ { i }$ 在微博传播网络中的入度集合；d是阻尼系数，取值一般为0.85； $r a t i o ( \nu _ { j } , \nu _ { i } )$ 代表用户 $\boldsymbol { \nu } _ { j }$ 对用户 $\nu _ { i }$ 的影响力贡献比例，其计算公式如式（8）所示。

$$
r a t i o \left( \nu _ { j } , \nu _ { i } \right) { = } \frac { W \left( \nu _ { j } , \nu _ { i } \right) } { \sum _ { { \nu _ { k } } \in o u t \left( \nu _ { j } \right) } W \left( \nu _ { j } , \nu _ { k } \right) } 
$$

其中： $\mathrm { o u t } ( \nu _ { j } )$ 为用户 $\nu _ { j }$ 在微博传播网络中的出度集合；$W ( \nu _ { j } , \nu _ { k } )$ 代表用户 $\nu _ { j }$ 对用户 $\nu _ { k }$ 的微博的传播意愿，由 $\boldsymbol { \nu } _ { j }$ 对 $\nu _ { k }$ 的交互频率 $\mathrm { B F } ( \nu _ { j } , \nu _ { k } )$ 与兴趣相似度 $\mathrm { S I M } ( \nu _ { j } , \nu _ { k }$ )的乘积表示。

对于用户间的交互频率，可以由微博传播网络 $G$ 的边权集合 $B$ 计算得出，如式（9）所示。

$$
B F \big ( \nu _ { i } , \nu _ { j } \big ) = \frac { B _ { i , j } } { \sum _ { \nu _ { k } \in o u t ( \nu _ { j } ) } B _ { i , k } }
$$

对于用户间兴趣相似度，本文采用LDA模型抽取用户的主题分布向量，而后再基于微博传播网络计算相邻用户间的相似度。首先将用户发布、转发、评论过的历史微博信息聚合成一篇文档，再将“文档一用户”集合作为模型的输入，最后利用LDA模型输出每一个用户所对应的主题分布向量。所有用户的主题分布向量集合记做矩阵 ${ \pmb D } { \pmb T }$ ，其中D、T分别对应用户数和主题数，矩阵元素 $D T _ { i , j }$ 代表用户 $\nu _ { i }$ 在话题 $t _ { j }$ 上的概率。

基于“用户一主题”矩阵 ${ \pmb D } { \pmb T }$ ，本文采用KL距离计算用户间相似性，KL距离是描述两个概率分布 $\mathrm { ~ \bf ~ P ~ }$ 、Q差异的一种方法，其计算公式如式（10）所示。

$$
K L ( P | | Q ) = \sum _ { x } P ( x ) \mathrm { l n } { \frac { P ( x ) } { Q ( x ) } }
$$

根据式（10）可以看出，两概率分布之间越相似则它们的 KL离散度越小，且KL离散度不具有对称性，即$\operatorname { K L } ( P \| Q ) \neq \operatorname { K L } ( Q \| P )$ 。由此，为了更适当地表示微博用户间的相似度，本文先对KL距离取平均而后再取倒数，如式（11)所示。

$$
S I M ( \nu _ { j } , \nu _ { i } ) = \frac { 2 } { K L ( D T _ { i } | | D T _ { j }  ) + K L ( D T _ { j } | | D T _ { i }  | ) }
$$

其中： $D T _ { i }$ 与 $D T _ { j }$ 分别为矩阵 $_ { D T }$ 的第i行与第j行，表示用户 $\nu _ { i }$ 与用户 $\nu _ { j }$ 的话题分布向量。

以下是MDIR算法的主要处理过程：

输入：微博传播网网络 $G = \left( V , E , B \right)$ ，阻尼系数 ${ \mathsf { d } }$ ，阈值ε。输出：所有用户的影响力集合S。  
1//微博传播网络边权值初始化  
2 for $B _ { i , j } \epsilon B$ （203 $B _ { i , j } = \alpha R _ { i , j } + \beta C _ { i , j } + \gamma M _ { i , j }$ （204号4 end for5//用户 $\nu _ { i }$ 的影响力值初始化  
6for $\nu _ { i } \epsilon V$ （204号  
7 $\mathbf { \nabla } \cdot \mathbf { \mathrm { M D I R } } \left( \nu _ { i } \right) = \frac { l g \left( N F ( \nu _ { i } ) \right) } { l g \left( N F _ { m a x } \right) } + \frac { l g \left( N W ( \nu _ { i } ) \right) } { l g \left( N W _ { m a x } \right) } + \mathbf { \mathcal { V } } e r i f y ( \nu _ { i } )$ （208 end for9 S.Init(）//初始化集合S10//用户影响力计算，当所有用户的影响力值都收敛时，迭代结束11 while $\vert s \vert < \vert V \vert$ 12 while $( \mathbf { \nabla } \nu _ { j } , \mathbf { \nabla } \nu _ { i }$ ） $\epsilon E$ 13 $P _ { 0 } = M D I R \left( \nu _ { i } \right) / \$ /用户 $\nu _ { i }$ 上一轮计算的影响力值  
14 $B F \big ( \nu _ { j } , \nu _ { i } \big ) = \frac { B _ { i , j } } { \sum _ { \nu _ { k } \in o u t ( \nu _ { j } ) } B _ { i , k } }$   
15 $S I M ( \nu _ { j } , \nu _ { i } ) = \frac { 2 } { K L ( D T _ { i } | | D T _ { j }  ) | | D T _ { j }  | | D T _ { j }  | | D T _ { i }  ) | }$   
16 $r a t i o \left( \nu _ { j } , \nu _ { i } \right) { = } \frac { W \left( \nu _ { j } , \nu _ { i } \right) } { \sum _ { \nu _ { k } \in o u t \left( \nu _ { j } \right) } W \left( \nu _ { j } , \nu _ { k } \right) }$   
1 $\_ M D I R ( \nu _ { i } ) = ( 1 - d ) + d \sum _ { \nu _ { j } \in i n ( \nu _ { i } ) } r a t i o ( \nu _ { j } , \nu _ { i } ) ^ { * } M D I R ( \nu _ { j } )$ 18 $P = M D I R ( \nu _ { i } )$ //用户 $\nu _ { i }$ 当前轮次计算的影响力值19if $P - P _ { 0 } \mid \mathrm { ~  ~ \leq ~ } \varepsilon$   
20 S.add $\{ \ \nu _ { i } , P $ ） //保存用户 $\nu _ { i }$ 的影响力21 end if22 end while23 end while24 return S

根据式（8）可以构造概率转移矩阵 $M$ ，从而MDIR算法的求解过程可以转换成一个Markov过程。Markov过程的收敛条件有：a）矩阵 $\pmb { M }$ 为随机矩阵；b）矩阵 $A$ 为不可约矩阵；c）矩阵 $\pmb { M }$ 为非周期矩阵。根据式（8）的表述，矩阵 $\pmb { M }$ 可直接满足收敛条件a)和b)；对于收敛条件c)，本文在实验开始前会对用户进行筛选，使得构建的微博传播网络是一个强连通图，可以保证矩阵 $\pmb { M }$ 的不可约性。综上所述，本文所提出的MDIR算法是可收敛的。

# 4 实验结果与分析

# 4.1数据集与实验环境

# 4.1.1数据集选取

本文以新浪微博为作为数据源，爬取了2014年5月份新浪微博一个月内12个热门话题下的部分用户微博信息作为研究数据。由于爬取到的用户信息繁杂、冗余信息过多，本

文过滤掉发博数少于10、关注用户数少于10的用户，由筛选后的数据所构建的微博传播网络的相关数据如表2所示。

Table 2Related data of microblog propagation network   

<html><body><table><tr><td>信息</td><td>数据</td></tr><tr><td>总节点数</td><td>81346</td></tr><tr><td>总边数</td><td>2712345</td></tr><tr><td>平均出度数</td><td>18.37</td></tr><tr><td>平均入度数</td><td>17.12</td></tr><tr><td>总微博数</td><td>1091461</td></tr></table></body></html>

# 4.1.2实验环境

由于在构建微博传播网络与MDIR算法迭代计算时所耗费的时间开销较大，本文对这两个过程进行了基于MapReduce 的并行化设计。实验使用四台PC 机搭建Hadoop集群，每台机器的操作系统均为64位CentOS-7。具体集群概况如表3所示。

表2微博传播网络相关数据  
表3实验集群概况  
Table 3Overview of experimental clusters   

<html><body><table><tr><td>IP地址</td><td>主机名</td><td>集群角色</td></tr><tr><td rowspan="2">172.168.21.5</td><td></td><td>NameNode</td></tr><tr><td>Master</td><td>SecondNameNode</td></tr><tr><td>172.168.21.6</td><td>Slave01</td><td>ResourceManager</td></tr><tr><td>172.168.21.7</td><td>Slave02</td><td>DataNode DataNode</td></tr><tr><td>172.168.21.8</td><td>Slave03</td><td>NodeManager</td></tr></table></body></html>

# 4.2对比实验与评价标准

# 4.2.1对比实验

为了让实验结果更有说服力，本文选取了目前较为流行或经典的用户影响力度量算法作为对比实验。首先选取的是PageRank算法，由于MDIR算法是基于PageRank的改进算法，用原始的PageRank算法做对比更会凸显该算法的优点；其次选取的是BWPR 算法，齐超等人[8]基于PageRank 算法提出了一种BWPR算法计算用户影响力，其主要改进是基于用户间交互行为来确定粉丝用户影响力的分配因子；然后是TwitterRank算法，Weng 等人[9]提出了针对Twitter平台的TwitterRank 算法，该算法主要是在PageRank 算法的基础上融合了用户的兴趣相似度，虽然该算法是基于Twitter平台的但是Twitter平台与新浪微博平台在结构上是一脉相承的，所以将TwitterRank算法推广在微博平台也具有一定意义；最后两种分别是基于用户粉丝数与发博数的排名算法。

# 4.2.2评价标准

在实际环境中微博用户影响力的衡量标准众多，难以给定一个统一标准。本文采用丁兆云等人[16提出的M折交叉验证的方法，分别验证了算法的准确率、召回率和F值。首先求出实验中的五种排序算法与本文提出的MDIR算法各自所计算出的Top-K影响力用户集合 $I _ { x }$ ，然后构造标准排序集合 ${ \mathbf { } } I _ { M }$ 为任意M $( 1 { < } \mathbf { M } \leq 6$ )种算法都投票为正确的结果。集合${ \mathbf { } } I _ { M }$ 的算术描述如式（12）所示。

$$
I _ { M } = \bigcup _ { x \in C o m b i n e ( 6 , M ) } \Biggl ( \bigcap _ { i = 1 } ^ { M } J _ { x _ { i } } \Biggr )
$$

其中：Combine(6,M)是从六种算法中选取 $M$ 种算法的组合数。例如，给定四种算法A、B、C、D得到的Top-K个影响力用户集合为 $I _ { A }$ ， $I _ { B }$ ， $I _ { C }$ ， $I _ { D }$ ，假设 $\scriptstyle { M = 2 }$ ，则标准集合 $J _ { M }$ 的构成如式（13）所示。

$$
\begin{array} { r l r } & { } & { I _ { M } = ( I _ { A } \bigcap I _ { B } ) \bigcup ( I _ { A } \bigcap I _ { C } ) \bigcup ( I _ { A } \bigcap I _ { D } ) \bigcup } \\ & { } & { \big ( I _ { B } \bigcap I _ { C } \big ) \bigcup ( I _ { B } \bigcap I _ { D } ) \bigcup ( I _ { C } \bigcap I _ { D } ) } \end{array}
$$

其中：算法A的准确率 $P _ { A }$ 的计算公式如式（14）所示。

$$
P _ { \mathrm { { A } } } = { \frac { \left| I _ { \mathrm { { A } } } \cap I _ { \mathrm { { M } } } \right| } { \left| I _ { \mathrm { { A } } } \right| } }
$$

算法A的召回率 $R _ { A }$ 的计算公式如式（15）所示。

$$
R _ { \scriptscriptstyle A } = \frac { \left| I _ { \scriptscriptstyle A } \cap I _ { \scriptscriptstyle M } \right| } { \left| I _ { \scriptscriptstyle M } \right| }
$$

算法A的 $F _ { A }$ 值的计算公式如式（16）所示。

$$
F _ { A } = 2 * \frac { P _ { A } * R _ { A } } { P _ { A } + R _ { A } }
$$

# 4.3算法有效性验证

同时对六种算法在 $\scriptstyle M = \{ 2 , 3 , 4 \}$ 的情况下进行交叉验证。由于 $M \geq 5$ 时，标准集合内的元素较少，各算法的准确率与召回率比较相似，故予以忽略。针对 $\scriptstyle \mathbf { M } = 2$ 、3、4的三种情况对六种算法所得的 Top-K（K分别值取100、200、..、1000)影响力用户的准确率、召回率及F值进行比较，实验结果表明MDIR算法在三种衡量指标下都有不错效果。

# 4.3.1准确率验证

在用户规模为Top-K的情况下，准确率表示目标算法正确计算出的Top-K用户的个数与用户数K的比值。由图1所示的三组实验结果表明，MDIR算法在不同的用户规模K与交叉折数M下的准确率都优于其他对比算法。其中当 $\mathbf { M } { = } 3$ 、4时，集合 $I _ { M }$ 中的用户较少，从而使得任意算法的结果集与标准集的相交的元素也较少，故整体的准确率相较于 $\scriptstyle \mathbf { M } = 2$ 的时候要低一些。

# 4.3.2召回率验证

在规模为Top-K影响力用户中，召回率为目标算法“正确”计算出的Top-K用户的个数与标准集中影响力用户个数的比值，反映了微博中影响力用户被发现的程度。六种算法分别在 $\scriptstyle \mathbf { M } = 2$ 、3、4的情况下Top-K 影响力用户的召回率分布如图2所示。实验表明，MDIR算法在M的三种取值下均有不错的表现，在 $\mathbf { M } { = } 3$ 的情况下MDIR算法区分度尤为明显。因为召回率由 $\left| I _ { A } \cap I _ { M } \right|$ 和 $\big | I _ { M } \big |$ 共同决定，所以当M增加时两者都随之增加，召回率变化不明显。

![](images/ea33bdb2a47eedcb07e6bf5aee7f89b40b897b48789f80c32e487a63f6361583.jpg)  
图1各算法在交叉验证中的准确率

![](images/dac4d69281c63be6b102681467b7322736b08f198e91518be82ad5fa2df809ba.jpg)  
Fig.1Precision of algorithms in cross-validation   
图2各算法在交叉验证中的召回率  
Fig.2Recall of algorithms in cross-validation

# 4.3.3F值验证

F 值综合考虑召回率与准确率，反映算法整体召回率与准确率的程度。各算法在交叉验证中的F值如图3所示。由图3可知，本文提出的MDIR算法在三组实验中有着明显的优势；同时可以看出只基于用户交互行为的BWPR算法在统计规模增加的情况下效率有所下降，这是因为用户的影响力还与用户的基本属性与博文内容有关；基于用户博文相似度的TwitterRank算法效率虽然会随着统计规模的增加出现上升的趋势，但是其没有结合用户的交互行为，所以效率一直不佳；PageRank算法和用户粉丝数排名的变化趋势很相近，足以说明PageRank很大程度依赖于用户的粉丝数，这也是原始PageRank算法的局限所在；用户发博数的排名与用户粉丝数排名由于考虑因素的单一，致使整体性能很差；而本文提出的MDIR算法则综合考虑了用户自身基本属性、用户间的交互行为以及博文内容三个维度的因素，并且有针对性地将其融入原始的PageRank 算法，使得其最终计算的结果在准确率、召回率、F值上均优于其他对比算法。

![](images/1667e1d0192d78ccdc2cc6b3d6ac46b5832aa8be95ab2d8e56ea3f30755499b8.jpg)  
图3各算法在交叉验证中的F值

# 4.3.4收敛性验证

SF-UIR算法是王顶[等人于2018年提出的微博用户影响力度量算法，该算法在PageRank的基础上加入了用户自身行为的特征与网络拓扑结构中的粉丝用户特征，解决了传统PageRank算法客观性差、影响力传递比例分配均匀的缺点，并且通过实验验证了该算法计算出的影响力排序结果的全面性与真实性。为了进一步说明本文提出的MDIR算法的适用性，本文将对比两个算法收敛速度。

本文仍用表2中介绍的数据集，分别对两种算法进行并行化，在相同收敛阈值的情况下计算用户影响力值，并且跟踪记录计算过程中的迭代次数。结果发现，MDIR算法使影响力值收敛的迭代次数为58次，用时 $3 4 ~ \mathrm { m i n }$ 。对于SF-UIR算法而言，其迭代次数为65次，用时 $3 9 \mathrm { \ m i n }$ 。实验结果说明了本文提出的MDIR算法有较好的收敛性。

# 4.4算法时间效率验证

根据3.3节中MDIR算法的相关介绍可以看出，由于要计算用户间的影响力贡献比例 $r a t i o ( \nu _ { j } , \nu _ { i } )$ ，所以本文提出的MDIR算法相较于PageRank算法的时间复杂度有所增加。但$r a t i o ( \nu _ { j } , \nu _ { i } )$ 的计算简单，仅涉及微博文本内容与用户交互关系，这些因素都可以在实验之前的预处理步骤中提取得到。另外，MDIR算法可以达到高影响力用户的影响力值更快累计，低影响力用户的影响力值更快趋于收敛的效果。为了验证并行化之后的MDIR算法的时间效率，本文比较了单机串行的MDIR算法与基于MapReduce的并行化MDIR算法在处理相同规模数据时，从读入数据到最后收敛所消耗的时间。根据不同的用户规模设计了八次对比测试，其结果如图4所示。从图中不难看出，基于并行化的MDIR算法在处理规模较小的1万条用户数据时，所花时间为 $1 0 ~ \mathrm { { m i n } }$ ，略低于串行MDIR算法所消耗的 $7 ~ \mathrm { m i n }$ 。然而从3万条用户数据开始，并行化MDIR算法的执行时间的变化较为平稳，但是串行MDIR算法几乎呈指数型增长。当达到的8万用户的数据规模时，并行化算法所需的时间几乎为串行算法的一半。如果数据量持续增大，那么串行算法会因为消耗的内存过多，引起程序的异常退出，而经过并行化后的MDIR算法依然会保持不错的性能。

![](images/4f3cd8a016450e7b9d9896c8b28703ce81712431d75a1e07ab0915dcca9357ea.jpg)  
Fig.3F-Measure of algorithms in cross-validation   
图4串、并行MDIR 算法时间效率对比 Fig.4Time efficiency comparison of algorithm between serial MDIR and parallelMDIR

# 5 结束语

本文通过分析传统PageRank 算法度量用户影响力存在的问题，从三个维度进行了有针对性的特征选取，进而提出了MDIR 算法。相比当前的相关研究，MDIR 算法融入了更多的影响因素，其考虑用户自身的基本属性使计算结果更为客观，考虑用户间的交互行为与博文内容使计算结果更为合理，考虑网络拓扑结构规避了不必要的计算并且获得更有效的结果。通过实验也可以看出，本文提出的MDIR算法在多种影响力评价指标上取得了良好的效果。

在下一步的研究中，将会首先考虑用户在不同话题中的影响力，挖掘在多个话题中都具有高影响力的意见领袖。其次，微博中大量的“水军”会对计算结果产生一定的干扰，需要在度量算法中加入对微博"水军"的识别技术，使得最终的计算结果更客观。

# 参考文献：

[1]CNNIC．第41次《中国互联网络发展状况统计报告》[R]．北京：中 国互联网络信息中心.2018.(CNNIC.The 41st Statistical report on the development of China's Internet network [R].Beijing:China Internet Network Information Center, 2018.)   
[2]王晨旭，管晓宏，秦涛，等.微博消息传播中意见领袖影响力建模研 究[J]．软件学报，2015，26(6):1473-1485.(Wang Chenxu,Guan Xiaohong,Qin Tao,et al.Modeling on opinion leader’s influence in microblog message propagation and its application [J].Journal of Software,2015,26(6):1473-1485.)   
[3]Cha M,Haddadi H,Benevenuto F,et al.Measuring user influence in Twitter: the million follower fallacy [C]//Proc of International Conference on Weblogs and Social Media. Carlifornia:AAAI Press, 2010: 14.   
[4]Mao Guojun,Zhang Jie.A PageRank-based mining algorithm for user influences on micro-blogs [C]// Proc of Pacific Asia Conference on Information Systems .Berlin: Springer,2016.   
[5]张昊，刘功申，苏波．一种微博用户影响力的计算方法[J].计算机 应用与软件,2015,32 (3):41-44.(Zhang Hao,Liu Gongshen,Subo.A computer method for microblog ging users influence [J].Computer Applications and Software,2015,32 (3): 41-44.)   
[6]王顶，徐军，段存玉，等．基于PageRank 的用户影响力评价改进算 法[J].哈尔滨工业大学学报,2018,50(5):60-67.(Wang Ding,Xu Jun,Duan Cunyu,et al. Improved user influence ecaluation algorithm based on PageRank [J]. Journal of Harbin insititude of Technology: Social Sciences Edition,2018,50 (5):60-67.)   
[7]孙红，左腾．基于PageRank 的微博用户影响力算法研究[J].计算 机应用研究,2018,35(4):1028-1032.(Sun Hong,Zuo Teng.Research OI aigoriun Ol cro-viog user uence Daseu on rageKaIk [J]. Application Research of Computers,2018,35(4):1028-1032.）   
[8]齐超，陈鸿昶，于洪涛．基于用户行为综合分析的微博用户影响力 评价方法 [J].计算机应用研究,2014,31（7):2004-2007.(Qi Chao, Chen Hongxu,Yu Hongtao.Method of evaluating micro-blog users' influence based on comprehensive analysis of user behavior [J]. Application Research of Computers,2014,31(7):2004-2007.)   
[9]Weng Jianshu,Lim E P,Jiang Jing，et al.TwitterRank:finding topic-sensitive influential twitterers [C]// Proc of ACM International Conference on Web Search and Data Mining. New York: ACM Press, 2010:261-27.   
[10]师亚凯，马慧芳，张迪，等．融合用户行为和内容的微博用户影响力 方法[J].计算机应用研究,2016,33(10):2906-2909.(Shi Yakai,Ma Huifang,Zhang D,et al.Microblog user influence algorithm based on user behavior and content [J].Application Research of Computers,2016, 33 (10): 2906-2909.)   
[11] Brin S,Page L. Repeint of: The anatomy of a large-scale hypertextual Web search engine [J].Computer Networks,2012,56 (18):3825-3833.   
[12] Wang Chi，Chen Wei，Wang Yajun，et al. Scalable influence maximization for independent cascade model in large-scale social networks [J].Data Mining and Knowledge Discovery,2012,25 (3): 545-576.   
[13]李志宏，庄云蓓．基于PageRank 算法的双维度微博用户影响力实时 度量模型[J]．系统工程，2016，34(2):128-137.(Li Zhihong, Zhuang.Yunbei. Rela-time measurement model of the influence of micro-blog users with double dimensions based on PageRank algorithm [J].System Engineering,2016,34 (2): 128-137.)   
[14] Saaty T. Fundamentals of the analytic network process-multiple networks with benefits [J]. Journal of System Science and System Engineering,2004,13 (3): 348-379.   
[15] Lappas T,Terzi E,Gunopulos D,et al. Finding effectors in social networks [C]// Proc of the 16th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM Press,2010: 1059-1068.   
[16]丁兆云，周斌，贾焰，等．微博中基于多关系网络的话题层次影响力 分析[J]．计算机研究与发展，2013，50(10):2155-2175.(Ding Zhaoyun, Zhou Bin,Jia Yan,et al. Topical influence analysis based on the multi-relational network in microblogs [J].Journal of Computer Research and Development, 2013,50 (10): 2155-2175.）