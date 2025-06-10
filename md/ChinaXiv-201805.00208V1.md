# 一种自动分类的网页搜索排序算法

刘铭瑀，刘学亮，胡骏(合肥工业大学 计算机与信息学院，合肥 230009)

摘要：针对传统网页排序算法OkapiBM25 通常会出现网页与查询关键词领域无关的领域漂移现象，以及改进算法需要人工建立领域向量的问题，提出了一种基于 BM25和 Softmax 回归分类模型的网页搜索排序算法。该方法首先对网页文本进行数据预处理并利用词袋模型进行网页文本的向量表示，之后通过少量的网页数据来训练Softmax 回归分类模型，来预测测试网页数据的类别分数，并与BM25信息检索的分数结合在一起，得到最终的网页排序结果。实验结果显示该检索算法无须人工建立领域向量，即可达到很好的网页排序结果。

关键词：领域向量；BM25；Softmax回归分类；网页排序 中图分类号：TP391.1 doi:10.3969/j.issn.1001-3695.2017.07.0700

# Web page search ranking algorithm using automatic classification

Liu Mingyu,Liu Xueliang, Hu Jun (School ofComputer&Information,Hefei UniversityofTechnology,Hefei23ooo9,China)

Abstract:In the traditional Web pagerankingalgorithm Okapi BM25,thereexists aproblem that theretrievalresults are independenttothedomain keywords,ndtheimprovedalgorithmneeds tobuildthedomainvector manuall.Toaddressthis isue,weproposea webpageranking algorithm based on BM25and softmax regresion classification model.Inthis method, wefirst encode thewebpage text withthebag-of-words model,andthentrainthesoftmaxregressionclassificationmodelbya small amountof webdatato predict thecategory scores ofthe test webdata.Finallwecombinethecategory scores and the BM25informationretrieval scores to get thefialranking of web page results.Experimentresults showthatour method can meet the user's information need better without even manually creating the domain vector.

Key Words: domain vector; BM25; softmax regression classification; Web page ranking

# 0 引言

随着互联网爆炸式的发展，Web信息在每个人的生活中变得越来越重要，然而当面对大量的信息时，用户从中找到有用的信息就严重依赖于搜索引擎的功能了，所以网页排序算法一直是搜索引擎的研究热点。但是，用户检索的关键字往往是很简短且不精确的[1]，导致了搜索引擎中高排名的网页可能与用户搜索意图并不相关[2]。例如，用户搜索关键词"微博”，有的可能是想搜索到“微博"的登录界面，有的则是想得到“微博"这家公司的新闻、股票等相关信息。互联网上的内容涵盖了多个主题，在现实生活中，人们想要得到的网页返回信息往往是某一主题内的，这就是所谓的领域问题。实际影响搜索排序的因子有很多，信息检索是最主要的因素之一。多年以来，许多研究学者在信息检索领域做了大量的工作，提出了布尔模型[3]、向量空间模型[4和概率模型[5]等许多有代表性的信息检索模型，布尔模型和向量空间模型都将文档表示词条视为相互独立的项忽略了表示词条间的关联性，概率模型则考虑了词条、文档间的内在联系，利用词条之间以及词条与文档间的概率相依性进行信息的检索，而OkapiBM25 算法[作为概率模型的典型排序算法，已经在搜索引擎的网页排序[7'8]、自然语言处理的文本加权[9,10]等领域得到广泛使用。

近年来，大多数基于BM25的相关性排序算法主要利用词频，例如TF、IDF信息等来计算查询与网页之间的相关性，TF指的是词条在文档中出现的次数，IDF通过统计包含词条的文档数量来衡量词条的重要性。Buttcher 等人[1]在BM25 的基础上加入了临近信息模型，该模型计算了词条在文档中的距离信息来改善BM25的评分。Roi-Blanco等人[12]同样改进了BM25算法并应用到网页检索当中，该模型通过考虑词条的不同来源来计算文档的词条的重要性，并通过在“虚拟区域”上定义运算符来计算词条与文档的相似度。上述方法都将BM25算法或其改进算法应用到了网页的检索排序之中，并取得了不错的效果，但是这些方法并没有有效的解决领域漂移。针对这个问题，文献[13]提出了基于领域模型的网页排序算法(topic sensitivere-ranking,TSRR)，该算法设计了一种独立于网页排序的模型，模型能够选取领域关键词组成的向量来表示领域，然后建立网页信息模型，在用户检索过程中结合领域向量模型和网页信息模型对网页搜索结果进行重排序。该算法效果的好坏取决于领域关键词选择的多少以及关键词建立的准确性。然而领域关键词的建立比较费时费力，而且严重依赖专业知识和直觉。

本文针对上述方法存在的问题，提出了一种自动分类的网页搜索排序算法。所提算法与前述算法不同点在于无须人工建立领域向量，而是采用分类器自动获得网页的类别概率。在信息检索方面，本文使用BM25算法来计算检索关键词与网页的相关性。领域方面，用少量的网页训练Softmax回归分类模型，得到网页数据的领域概率分数。将BM25分数和领域概率分数线性相加，对网页进行排序。该方法无须经验和人工技巧，即可以达到一个很好的网页排序效果。

# 1 本文方法

本文方法如图1所示，首先用爬虫程序爬取网页文本，之后进行分词、去停用词和词袋模型向量化等预处理，形成了本实验的数据集。接着训练Softmax回归分类模型得到每个网页的类别概率。根据用户提供的搜索关键词，通过BM25算法检索相关网页，将网页的BM25分数和Softmax的类别分数进行融合，得到最终的网页分数，以此排序来将相关网页返回给用户。

![](images/30ed5a9059075d04f96f3592a8735a89ea015853bb08e65fbaea383fc5aea92a.jpg)  
图1本文算法流程图

# 1.1数据预处理

首先，通过爬虫程序对不同领域的网站进行爬取，并根据网页的标签提取出文本内容，然后采用结巴分词中的精确模式进行中文分词，并去掉停用词。

在数据预处理后得到了已分词后的网页文本数据集，对通过中文分词切分成词语的文本进行计算，得到每个词语在每个网页文本中的权重，此处用到了自然语言处理中的词袋模型(bag-of-words)。如果某个词语在网页文本中出现n次的话，则在网页文本向量中对应的权重值为n，否则为0。网页文本向量的大小为 $m * | v |$ ，其中 $m$ 为网页文本的个数， $| v |$ 表示每一个文本向量的长度，具体大小为词典中词的个数。

# 1.2Okapi BM25 算法

OkapiBM25是一个经典概率模型计算公式，它根据给定搜索查询词与匹配文档的相关性对文档进行排名。给定一个索引向量 $\varrho$ ，包含关键词 $q _ { 1 } , q _ { 2 } , \ldots , q _ { n }$ ，对于一个文档 $D$ ，BM25的分数公式为：

$$
s c o r e _ { _ { B M 2 5 } } = \sum _ { i = 1 } ^ { n } I D F \left( q _ { i } \right) \cdot \frac { f \left( q _ { i } , D \right) \left( k + 1 \right) } { f \left( q _ { i } , D \right) + k \left( 1 - b + b \cdot \frac { \left| D \right| } { a \nu g d l } \right) }
$$

其中： $f ( q _ { i } , D )$ 是关键词 $q _ { i }$ 在文档 $D$ 中的词频， $| D |$ 是文档 $D$ 的长度，avgdl是平均文档长度， $k$ 和b是两个可调节的参数，一个决定了词频的比重，一个决定了文档长度的比重。实验验证[14]，通常将 $k$ 设置为[1.2,2.0]，本文为 1.2， $b$ 设置为0.75。$I D F ( q _ { i } )$ 是检索词 $q _ { i }$ 的逆文档频率，公式为

$$
\mathrm { I D F } \big ( q _ { i } \big ) = \log \frac { N - n \big ( q _ { i } \big ) + 0 . 5 } { n \big ( q _ { i } \big ) + 0 . 5 }
$$

其中： $N$ 是采集的文档总数， $n ( q _ { i } )$ 为包含关键词的文档个数。观察该公式可以看出，如果一个词 $q _ { j }$ 在一半以上的文档里都出现，那么 $I D F ( q _ { j } )$ 为负值，所以本文在数据预处理阶段，就把停用词都去掉。

为了提高查询效率，减少响应时间，本文采用倒排索引机制(inverted index)[15]，在全局搜索下，倒排索引可以建立并存储词条(term)与文档(doc)之间的关系映射。通过倒排索引，可以根据词条快速获取包含这个词条的文档列表。在经过数据预处理过程之后，每篇文档都转换成一个词条列表<term,doc>，对所有文档按照其中出现的词条来建立倒排索引，索引中包括一部词典，和一个全体倒排记录表。如图2所示。

![](images/67b426301fb7bfb4b0374e7ca7fe5ce6b07d2de24fe936369691ff3af9e84b47.jpg)  
图2倒排索引

# 1.3 网页文本分类

网页信息是包含多个领域数据的，因此，网页分类是一个多分类问题。本文采用Softmax回归分类模型对网页进行分类。Softmax回归分类模型有很多优点，例如它是直接对分类可能性进行建模，无须事先假设数据分布，这样就避免了假身份不准确所带来的问题，而且它不仅可以预测出类别，还可以得到近似的概率预测，这就对本文的任务很有帮助。该模型数学定义如下：

$$
p \left( y ^ { i } = j | x ^ { i } \right) = \frac { e ^ { W _ { j } x ^ { i } } } { \sum _ { l = 1 } ^ { k } e ^ { W _ { l } x ^ { i } } }
$$

其中：W 是模型参数， $x ^ { i }$ 为第 $\mathrm { ~ i ~ }$ 个网页文本向量， $p { \big ( } y ^ { i } = j { \big | } x ^ { i } { \big ) }$ 表示Softmax回归将 $\textbf { x }$ 分类为类别 $\mathrm { j }$ 的概率。对于给定的输入实例 $\textbf { x }$ ，按照上述的条件概率分布求得各类别的概率，取概率最大者，选为其类别。

对于爬取到的五个类别的网页，本文首先将全部的网页加上类别标签，为了近似达到线上模型的效果，随机抽取1500篇的数据来训练网络，余下的13500篇数据作为测试数据来测试分类准确率，测试数据与训练数据不交叉。经过调参，当准确率达到最优时，固定好网络的参数，将13500篇测试数据再次输入到网络中，得到Softmax回归分类模型预测的类别概率输出 $\pmb { p }$ 。

领域分类方面，采用余弦相似度来计算Softmax回归分类模型的类别概率输出 $\pmb { p }$ 与类别向量 $\iota$ 的相似度，来得到类别分数。Softmax回归分类模型的类别概率输出 $\pmb { p }$ 与类别向量 $\iota$ 可以表示为如下形式：

$$
\pmb { p } = ( p _ { 1 } , p _ { 2 } , \cdots , p _ { n } )
$$

$$
\pmb { l } = ( l _ { 1 } , l _ { 2 } , \cdots , l _ { n } )
$$

其中： $\mathfrak { n }$ 为类别个数，类别向量 $\iota$ 中只有一个元素的值$l _ { i } { \left( i = 1 , 2 , \ \cdots , \ n \right) }$ 为1，其余元素为0。余弦相似度的计算公式如下：

$$
\mathrm { s c o r e } _ { p } = { \frac { \sum _ { i = 1 } ^ { n } p _ { i } \ : ^ { * } l _ { i } } { \sqrt { \sum _ { i = 1 } ^ { n } p _ { i } ^ { 2 } } \ : ^ { * } \sqrt { \sum _ { i = 1 } ^ { n } l _ { i } ^ { 2 } } } }
$$

# 1.4算法整体描述

自动分类网页排序算法的具体步骤如下：

a)利用式(1)(2)计算用户搜索关键字和每个网页的相似度，得到分数scoreBM25°

b）首先用Softmax回归分类模型对网页进行概率预测，其次利用式(4)计算Softmax 模型的类别概率输出 $\pmb { p }$ 与类别向量 $\iota$ 的余弦相似度，得到类别分数 $s c o r e _ { p }$ 。

c)对两个分数进行加权求和，得到网页排序的最终分数公式：

$$
s c o r e = \alpha \cdot s c o r e _ { B M 2 5 } + \beta \cdot s c o r e _ { p }
$$

其中 $\alpha + \beta = 1$ ， $\alpha$ ， $\beta \in \left[ 0 , 1 \right]$ ，根据 score 对网页进行排序，得到最终的网页排序结果。自动分类网页排序算法的具体步骤如下：

Input:query, page,l

Output:result

1: for each page in pagelist{   
2: scoreBM25=BM25(query, page)   
3: p=SOFTMAX(page)   
4: scorep=cosine-relative(l, p)   
5: （20 ${ \mathrm { s c o r e } } { = } \alpha \cdot s c o r e _ { B M 2 5 } + \beta \cdot s c o r e _ { p }$   
6: result.add(score, page)   
7: result.sorted(score)   
8:}   
9: return result

# 2 实验结果及分析

# 2.1实验设置

本文实验所使用的机器配置为Intel(RXeon(RCPUE5-2620@2.10GHz，RAM64GB，Ubuntu14.04 操作系统，算法采

用 Python2.7实现。

# 2.2实验检索关键词及语料

本文使用网络爬虫从腾讯、新浪、IT时代网等常用网站爬取了IT、创业、学术、时政、娱乐等五大类新闻语料。总共15000篇，每一类3000篇。检索关键词挑选自2016互联网各领域热词，每个领域选取三个检索词。实验数据具体选择如表1所示。

表1语料来源及检索关键词  

<html><body><table><tr><td>领域</td><td>语料来源</td><td>检索关键词</td></tr><tr><td>IT</td><td>IT时代网</td><td>虚拟现实、比特币、 无人机</td></tr><tr><td>创业</td><td>IT时代网、科技讯</td><td>云计算、直播、共享 单车</td></tr><tr><td>学术</td><td>合肥工业大学新闻网、中国</td><td>基因、生物、人工智</td></tr><tr><td></td><td>科学技术大学新闻网</td><td>能</td></tr><tr><td>时政</td><td>腾讯、新浪、搜狐</td><td>一带一路、互联网+、 文化自信</td></tr><tr><td>娱乐</td><td>八卦来了</td><td>王宝强、杨洋、粉丝</td></tr></table></body></html>

# 2.3评价标准

为了验证本文排序方法的有效性，实验采用了如下两个评价指标：

a)用户满意度。用户对排名前十的每个网页进行打分，采用五分制，分数为1\~5，分别表示很不满意、不满意、一般、满意、十分满意。最后计算前十网页的打分均值。公式如下：

$$
S a t i s f i c a t i o n = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } S _ { i }
$$

其中： $\mathfrak { n }$ 是用户数量， $S _ { i }$ 表示用户对排名前十的网页打分的均值。

b)Precision at $\operatorname { K } \circ \operatorname { P } \mathcal { Q } \operatorname { K }$ 是信息检索领域一个最直观的指标，它反映了检索回的前K个结果中被认为是相关的文档的比例。所以该指标衡量的是用户对整体检索结果的满意度。根据文献[16]的评价标准，本文选择在用户满意度指标中网页评分3分以上的，即满意和十分满意的网页作为相关的网页检索结果。$\mathrm { P } @ \mathrm { K }$ 的公式如下：

$$
\mathrm { P } @ K = \frac { K _ { s } } { K }
$$

其中， $K _ { s }$ 指的是前 $K$ 个查询结果中相关网页的个数。对于检索系统而言，用户想要的结果排名越靠前，那么这个检索系统越是成功的，为了将排序位置信息也加入到评测指标中，本文分别选择 $\scriptstyle \mathrm { P } \ @ 2$ 、 $\scriptstyle \mathbf { P } ( { \widehat { \boldsymbol { a } } } , 4$ 、 $\mathrm { P } \ @suit 6$ 、 $\scriptstyle \mathrm { P } \ @ 8$ 、 $\mathbf { P } \ @ 1 0$ 来判断检索结果的好坏。

# 2.4参数调优

式(5)决定网页排序的最终得分，对于两个参数 $\alpha$ ， $\beta$ 需要根据实验结果来权衡哪一部分的比重更大，实验的方法是找五个志愿者，每个领域选取出一个关键词，利用用户满意度公式，对不同的参数计算出来的排序结果进行评分，并确定参数的最优值。每个关键词进行九次实验，参数分别从第一次的(0.1,0.9)到第九次的{0.9,0.1)。图4是实验结果。

![](images/52f8ddaccf5b6d205483b3ac1a971b83adf26716c3bdb2f87b5649c79f2ccd0c.jpg)  
图4参数调优结果  
图5各领域用户满意度实验结果

根据实验结果，IT、学术、娱乐三个领域在(0.4,0.6)时用户满意度分数最高，同时创业、时政也达到了第二高评分，五类的平均分也是在(0.4,0.6)时达到最高，因此本文选择 $\alpha = 0 . 4$ $\beta = 0 . 6$ 作为最优参数值。

Softmax回归分类器的迭代次数为50次，步长设置为 $1 0 ^ { - 4 }$ ，当分类准确率达到最高约为 $9 4 . 6 \%$ 时，获得分类器的最优参数，将测试数据输入网络中计算得到类别概率。

# 2.5对比实验结果

本文选择的对比方法同样是为了解决领域漂移问题的TSRR算法，由于数据集不同，该算法同样按照本文参数调优的方法确定参数最优值为 $\alpha = 0 . 3$ ， $\beta = 0 . 7$ 。在事先不告知两种排序结果分别属于哪种算法的前提下，找五名志愿者，对所给各领域检索关键词，按照对某个关键词在对应领域想要得到的检索结果对每个关键词所检索回的网页结果进行用户满意度打分。图5是实验结果对比。由图5可知，一些关键词本身包含一定领域信息，例如：IT领域的"虚拟现实”、“比特币”，创业领域的"云计算""直播"共享单车”、学术领域的"基因""生物”，时政领域的“一带一路"文化自信”，娱乐领域的"王宝强"杨洋"粉丝"等。这些关键词的结果TSRR的用户满意度平均分为3.53，本文算法获得了3.87，比TSRR高 $9 . 6 \%$ 。但是像"无人机"既可以是IT领域，也可以是创业领域。“人工智能"既可以是IT领域，也可以是创业领域或者学术领域。“互联网 $+ ^ { , , , }$ 也是如此。这些关键词在检索的时候就可能存在严重的领域漂移现象，这三个词TSRR平均分为2.83，本文算法平均分为3.73，比TSRR 提高了 $3 1 . 8 \%$ 。有效的解决了领域漂移的问题。

创业领域 IT领域  
5 5  
43 2 三 43 2 三  
1 1  
0 0云计算直播共享单车 虚拟现实 比特币无人机TSRR ■本文算法 TSRR·本文算法时政领域 学术领域  
5 5  
4 山 4 三  
3 3  
2  
1  
0 0一带一路互联网+文化自信 基因 生物人工智能TSRR■本文算法 TSRR■本文算法娱乐领域543 三210王宝强 杨洋 粉丝TSRR ■本文算法

表2P@K实验结果  

<html><body><table><tr><td rowspan="2" colspan="2">算法</td><td colspan="5">TSRR</td><td colspan="5">本文算法</td></tr><tr><td>P@</td><td>P@4</td><td>P@6</td><td>P@8</td><td>P@10</td><td>P@2</td><td>P@4</td><td>P@6</td><td>P@8</td><td>P@10</td></tr><tr><td rowspan="3">IT</td><td>虚拟现实</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.8</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0.8</td></tr><tr><td>比特币</td><td>1</td><td>0.5</td><td>0.5</td><td>0.5</td><td>0.4</td><td>1</td><td>0.75</td><td>0.5</td><td>0.5</td><td>0.5</td></tr><tr><td>无人机</td><td>0.5</td><td>0.5</td><td>0.33</td><td>0.38</td><td>0.4</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.8</td></tr><tr><td rowspan="3">创业</td><td>云计算</td><td>0</td><td>0.25</td><td>0.17</td><td>0.25</td><td>0.4</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.7</td></tr><tr><td>直播</td><td>0.5</td><td>0.5</td><td>0.33</td><td>0.38</td><td>0.5</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.9</td></tr><tr><td>共享单车</td><td>0</td><td>0.25</td><td>0.33</td><td>0.25</td><td>0.4</td><td>0.5</td><td>0.5</td><td>0.33</td><td>0.25</td><td>0.4</td></tr><tr><td rowspan="3">学术</td><td>基因</td><td>0.5</td><td>0.75</td><td>0.7</td><td>0.63</td><td>0.6</td><td>1</td><td>0.75</td><td>0.5</td><td>0.63</td><td>0.7</td></tr><tr><td>生物</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.7</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.9</td></tr><tr><td>人工智能</td><td>0</td><td>0.25</td><td>0.17</td><td>0.13</td><td>0.2</td><td>1</td><td>0.75</td><td>0.83</td><td>0.75</td><td>0.8</td></tr><tr><td rowspan="3">时政</td><td>一带一路</td><td>1</td><td>1</td><td>0.83</td><td>0.75</td><td>0.7</td><td>1</td><td>1</td><td>0.83</td><td>0.88</td><td>0.9</td></tr><tr><td>互联网+</td><td>0</td><td>0.25</td><td>0.17</td><td>0.13</td><td>0.1</td><td>1</td><td>0.75</td><td>0.67</td><td>0.63</td><td>0.6</td></tr><tr><td>文化自信</td><td>0.5</td><td>0.25</td><td>0.5</td><td>0.63</td><td>0.7</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td rowspan="3">娱乐</td><td>王宝强</td><td>1</td><td>0.75</td><td>0.67</td><td>0.63</td><td>0.6</td><td>1</td><td>1</td><td>0.83</td><td>0.75</td><td>0.7</td></tr><tr><td>杨洋</td><td>1</td><td>1</td><td>0.83</td><td>0.75</td><td>0.6</td><td>1</td><td>1</td><td>0.83</td><td>0.75</td><td>0.6</td></tr><tr><td>粉丝</td><td>0</td><td>0.25</td><td>0.33</td><td>0.5</td><td>0.6</td><td>1</td><td>1</td><td>1</td><td>0.88</td><td>0.9</td></tr></table></body></html>

本文选择 $\mathrm { P } @ \mathrm { k }$ 来衡量算法对检索结果位置的好坏。结果如表2所示， $\scriptstyle \mathrm { P } \ @ 2$ 提升了 $81 . 3 \%$ ， $\scriptstyle \mathrm { P } \ @ 4$ 提升了 $5 8 . 8 \%$ ， $\scriptstyle \mathrm { { P } } \ @ 6$ 提升了 $54 . 8 \%$ ， $\scriptstyle \mathrm { P } \ @ 8$ 提升了 $5 0 . 5 \%$ ， $\mathbf { P } \ @ 1 0$ 提升了 $45 . 5 \%$ 。本文算法的 $\scriptstyle \mathrm { P } \ @ 2$ 等指标有较大提高，确保了用户想要得到的结果返回在较靠前的位置。综上所述，Softmax回归分类模型与BM25结合的网页排序算法即有效的解决了网页排序中领域漂移问题，也使得相关网页的排序更加靠前。

# 3 结束语

本文提出了一种结合BM25和Softmax回归分类模型的网页排序算法，算法采用少量的网页数据训练分类器，获得类别分数，与BM25检索分数相结合，得到网页排序的最终分数。该方法无须人工建立领域向量，有效的解决了领域漂移的问题，同时能够保证了相关的网页排名更加靠前。在后续的研究中，将用户的历史搜索、行为倾向[17\~19]等加入到该算法当中，使得网页排序算法得到更好的效果。

# 参考文献：

[1]Fonseca B M,Golgher PB,Moura E S D,et al.Using association rules to discover search engines related queries [C]//Proc ofLA-WEB.2003:66- 71.   
[2]Zhuang Ziming,Cucerzan S.Re-ranking search results using query logs [C]//Proc of the 15th ACM International Conference on Information and Knowledge Management.2006: 860-861.   
[3] Cooper W S.Getting beyond boole [J]. Information Processing and Management,1998,24 (3): 243-248.   
[4]Salton G, Yang C S,Yu C T.A theory of term importance in automatic text analysis [J].Journal of the American Society for Information Science and Technology,2010,26(1): 33-44.   
[5]Robertson, Stephen E, Jones S,et al. Relevance weighting of search terms [J].Journal of the Association for Information Science and Technology, 2014,27 (3): 129-146.   
[6]Robertson S,Zaragoza H. The probabilistic relevance framework:BM25 and beyond [J].Foundations and Trends? in Information Retrieval,2009,3 (4): 333-389.   
[7]Niu Jianwei, Zhao Qingjuan,Wang Lei,et al. OnSeS:a novel online short text summarization based on bm25 and neural network [C]//Proc of IEEE Global Communications Conference.2016:1-6.   
[8]Li Ying, Sha Fei,Wang Shujuan,et al. The improvement of page sorting algorithm for music users in Nutch [C]// Proc of the 15th IEEE//ACIS International Conference on Computer and Information Science.2O16:1-4.   
[9]Bestgen Y. Improving the character n-gram model for the DSL task with BM25 weighting and less frequently used feature sets [C]//Proc of the 4th Workshop on NLP for Similar Languages, Varieties and Dialects.2017: 115- 123   
[10] Kazemian S, Zhao Shunan,Penn G.Evaluating sentiment analysis in the context of securities trading [Cl// Proc of the 54th Annual Meeting of the Association for Computational Linguistics.Association for Computational Linguistics.2016: 2094-2103.   
[11] Bütcher S,Clarke C L,Lushman B.Term proximity scoring for Ad hoc retrieval on very large text collections [C]//Proc of the 29th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval. 2006: 621-622.   
[12] Blanco R,Boldi P. Extending BM25 with multiple query operators [C]// Proc of the 35th International ACM SIGIR Conference on Research and Development in Information Retrieval.2012: 921-930.   
[13]潘澄，吴共庆，李磊，等．基于领域模型的网页搜索排序算法[J].计 算机系统应用,2015,24(11):107-114.   
[14] Jones K S,Walker S,Robertson SE.A probabilistic model of information retrieval: development and comparative experiments [J]. Information processing and management, 20oo,36 (6): 809-840.   
[15] Manning C D,Raghavan P, Schitze H.An Introduction to Information Retrieval [M]. Cambridge: Cambridge University Press,2008:1-18.   
[16] Agichtein E,Brill E,Dumais S.Improving Web search ranking by incorporating user behavior information [C]// Proc of the 29th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval. 2006: 19-26.   
[17] Wu Yao,DuBois C,Zheng AX,etal. Collaborative denoising auto-encoders for top-n recommender systems [C]// Proc of the 9th ACM International Conference on Web Search and Data Mining. 2016: 153-162.   
[18] Wu Chaoyuan,Ahmed A,Beutel A,etal. Recurrent recommender networks [C]// Proc of the 1Oth ACM International Conference on Web Search and Data Mining. 2017: 495-503.   
[19] Zhuang Fuzhen,Luo Dan, Yuan N J,et al.Representation Learning with Pair-wise Constraints for Collaborative Ranking [C]//Proc of the 1Oth ACM International Conference on Web Search and Data Mining.2017: 567-575.