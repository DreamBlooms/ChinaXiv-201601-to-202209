# 基于改进SimRank的产品特征聚类研究

刘臣，段俊(上海理工大学 管理学院，上海 200093)

摘要：针对在线用户评论中产品特征的提取和聚类问题进行了研究，提出一种改进的 SimRank算法，将情感词-特征对放入二分网中，在二分网中使用改进后的SimRank算法计算特征词之间的相似度；再通过谱聚类算法对特征相似度进行聚类，提取网络产品的特征集合。以某电脑评论为例，从中提取情感词-特征对进行研究，实验结果显示，改进后的算法准确率更高。改进后的特征相似度检测方法可以作为检测特征相似度的有效方法。实验采用在线产品的评论语料，实验结果表明使用改进后的 SinRank相似度对特征词进行聚类提取出特征更加准确。

关键词：SimRank算法；特征聚类；二分网；特征相似度中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.01.0027

# Product feature clustering based on improved SimRank

Liu Chen, Duan Jun† (Business School,University ofShanghai for Science&Technology,Shanghai 20o093,China)

Abstract:This paper studies the extraction and clustering of product features inonlineuserreviews.It proposed an improved SimRankalgorithmtoput theaffective word-featurepairintothebinarynetwork.AndtheimprovedSimRankalgorithmisused tocomputethesimilaritybetweenthecharacteristic words.Thenthespectralclusteringalgorithmisadoptedtoclusterthefeature similarity.Extracts feature sets fornetwork products.Takingacomputercommentaryasan example,thepaper extractsaffective word-feature pairs,and the experimentalresults showthatthe improved algorithm has higher accuracy.Theimproved feature similaritydetection methodcanbeusedasanefective method fordetecting feature similarity.Theexperimentalresults show that using the improved Sinrank similarity to extract the feature words is more accurate.

ey words: SimRank algorithm; feature clustering; binary network; feature similarit

# 0 引言

随着电子商务的迅速发展，消费者更多的选择网上购物。同时，消费者在购买产品后会发表产品评论。互联网上涌现出大量的产品评论信息，这些评论对在线产品的各个性能进行了描述。研究表明，消费者会根据产品评论做出是否购买的决策。所以，产品评论对消费者和商家都至关重要。但是，消费者阅读在线评论存在很多阻碍。例如：a)评论信息过载,由于某些产品评论量过大，消费者无法一一阅读来获取自己所需信息，而大部分消费者往往只需要根据自己的需求了解产品的部分特征；b)用户评论中存在产品特征表达多样性问题，如“外观”，“外表”，“外形”和“颜值”等描述同一类特征，消费者很难通过读完所有评论了解到该产品的全部特征。商家也无法客观的提供产品的全部特征，尤其是由消费者进行产品体验后的特征;c)几乎每个消费者对产品特征的关注点都不同,消费者很难从大量的评论中快速找到自己所需的特征等。基于众多问题，目前的研究热点之一即为如何将有价值的信息从海量的评论中挖掘出来。产品特征的有效提取"是解决上述诸多问题的关键方法。通过对网上产品评论信息的挖掘与分析[，用户能清晰的认识产品的特征，从而做出购买决策，商家也能掌握消费者对产品的评价，从而对产品的某些方面进行改进。

目前，已有一些学者在产品评论的特征提取方面做出了研究。Hu和Liu2最开始使用关联规则实现对产品特征的提取。Kamal3等人设计出的相关规则对评论中产品“特征-情感对”进行抽取则是通过对评论的语义和语言学分析。在商品特征自动提取方面，Hu等人4利用词性标注在评论中提取名词或名词性短语从而生成事务集，根据Apriori算法提取候选特征集，最后使用邻近规则和独立支持度规则过滤商品特征。李实等人[5]参考Hu等人的研究方法，结合中文评论的语言特点，对Hu等人的方法进行改进，将改进后的方法应用于提取中文评论中的产品特征。刘鸿宇等人利用产品特征词与评价词之间的依存句法关系，同时结合频率、点互信息、名词剪枝三种过滤技术，从在线评论中提取产品特征。Jin等人则直接从利弊型评论中提取出名词和名词短语，去除低频词及停止词后，利用WordNet词典进行同义词聚类，聚类后的集合作为产品特征列表。张珠等人8衡量商品特征之间关联程度是运用了语素和评价词，用K-means方法实现商品特征归类，但K-means聚类方法具有一些缺陷，如数据离群点、输入次序等会影响聚类质量。

因此，本文从复杂网络的角度对产品特征进行聚类分析，将提取出的特征词、情感词分别看作二分网络的顶点，情感词-特征对之间的关系看作二分网络的边。在SimRank 算法的基础上考虑二分网络边的权重，分别使用原相似度计算方法和改进后的方法对样本数据进行相似度检测,并对比准确率验证改进后方法的有效性。最后利用谱聚类分别对得到的相似性矩阵及加权的相似度矩阵进行聚类。实验表明改进的SimRank算法计算特征词之间的相似性更加准确，聚类效果更好。

# 1 实验方法

# 1.1数据抓取及分词标注

本文使用Python 编写爬虫程序，在京东网上抓取产品评论[9]，抓取的评论保存到数据库中。从京东商城上抓取了某电脑的全部评论，共11543条。

首先对爬取到的评论进行预处理[10]，使用哈工大社会计算与信息检索研究中心研发的“语言技术平台（LTP)"。LTP中的中文自然语言处理[]云服务高效精准。LTP 进行分析的前两步是将评论语句分词及词性标注，基于此，我们使用Python 对存放在数据库中某电脑全部评论进行分词和标注。分词标注后的词性有名词n，形容词a，动词v，副词d，连词c，标点符号wp 等。然后通过分析分词标注后的各成分之间的依存语法关系揭示评论的句法结构。依存句法分析通过识别评论语句中的“主谓宾”、“定状补”这些语法成分来分析它们之间的关系。主要语法关系有主谓关系（SBV)，动宾关系（VOB)，定中关系（ATT)，状中结构（ADV)，并列关系（COO）等。如图1所示。

![](images/61626adc271f4d82788b2307c1b15288f858dda07e1aacdbea709e514b79a1df.jpg)  
图1依存句法分析

# 1.2提取情感词-特征对

将京东的产品评论爬取出来，根据LTP中的依存句法分析，找出特征词和情感词之间的依赖关系。通过大量的训练发现情

感词和特征词之间主要语法关系主要有：多数的主谓关系（SBV)，少数的动宾关系（VOB）、定中关系（ATT）以及并列关系（COO）。

因此，基于大量训练得出的特征词和情感词之间的关系，将预处理后的评论进行情感词-特征对提取[12]。提取出的情感词-特征对作为候选情感词-特征对。部分如表1所示。

表1依赖关系提取情感词-特征对  

<html><body><table><tr><td>特征词</td><td>情感词</td><td>依赖关系</td></tr><tr><td>配置</td><td>不错</td><td>SBV</td></tr><tr><td>外观</td><td>漂亮</td><td>ATT</td></tr><tr><td>价格</td><td>合理</td><td>SBV</td></tr><tr><td>速度</td><td>很快</td><td>SBV</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

# 1.3特征词相似度计算

本文将特征词与情感词之间的联系抽象为一个二分网络。由不同性质的两类节点以及这两类节点之间的连边组成二分网络，其中同类节点之间没有连线。在这个网络中，将情感词看作一类节点，特征词看做另一类节点，而用依存句法分析出的情感词与特征词之间的语法关系看成情感词节点与特征词节点之间的连边。在情感词-特征对的提取过程中，情感词和特征词之间的关系就呈现出这样的网络特征。如图2所示。

![](images/80266da3fb52804cc2ade5beca8b152282b02eea8d0046fb0abeccebb15ae494.jpg)  
图2二分网络图

基于情感词-特征对二分网络，本文使用SimRank相似度算法计算特征词之间的相似度[13]。SimRank 相似度算法的核心思想为：如果两个对象和被其相似的对象所引用（即它们有相似的入邻边结构)，那么这两个对象也相似。近年来已在信息检索领域引起广泛关注，成功应用于网页排名、网络图聚类、协同过滤、孤立点检测、近似查询处理等。SimRank基本公式：

$$
\mathsf { S } ( a , b ) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 , a = b } { | I ( a ) | | I ( b ) | } \sum _ { i } ^ { | I ( a ) | } \sum _ { j } ^ { | I ( b ) | } s \left( I _ { i } ( a ) , I _ { j } ( b ) \right) , a \neq \mathsf { b } | I ( a ) | , | I ( b ) | \neq \emptyset } \\ { \displaystyle 0 , o t h e r w i s e } \end{array} \right.
$$

其中： $S ( a , b )$ 指节点 $a$ ，节点b之间的相似度，取值范围是[0,1];$\boldsymbol { I } ( \boldsymbol { a } )$ 为所有指向结点 $a$ 的节点集合，即入邻点集合； $I _ { i } ( a )$ 为第i个指向 $a$ 的节点，即 $a$ 的第i个入邻点; $s \left( I _ { i } ( a ) , I _ { j } ( b ) \right)$ 为相连的二部图另一个子集节点之间的相似度，即相连的情感词之间的相似度。参数c是阻尼系数， $0 < \mathsf { c } < 1$ ，一般取 $c = 0 . 8$ 。所以，节点 $a$ 与节点 $b$ 之间的相似度就等于所有同时指向节点 $a$ ， $b$ 的节点相似度之间的平均值。

由于SimRank算法认为只要有边相连，即为相似。如图3所示，相似的特征词都和相同的情感词相连接，而非相似的特征词也会和同一情感词连接，但是没有考虑到两个节点共同相连的边越多，则意味着节点相似度越高。实验数据也证明直接使用SimRank算法计算的特征词之间的相似度无太大差别，所以仅通过SimRank求出的相似度，对这些数据进行聚类效果不好。所以，这里使用改进的SimRank算法，本文考虑加入权重的思想，即在算法中加入二分网边的权重。

![](images/78acdd212f7435bf32bf75ef1b38735f792e2fb9db4e5e014544044e61966247.jpg)  
图3情感词-特征对二分网络图

# 1.4情感词-特征对边权重计算

基于二分网的特征计算情感词-特征对边权重。首先统计出二分网边的频次 $f$ ，即情感词-特征对出现的频次，进而计算每条边的两个端点出现的概率：

$$
\begin{array} { c } { p _ { 1 } = \frac { f _ { 1 } } { \sum _ { i = 1 } ^ { n } f _ { i } } } \\ { p _ { 2 } = \frac { f _ { 2 } } { \sum _ { j = 1 } ^ { n } f _ { j } } } \end{array}
$$

其中： $f _ { i }$ 表示该边连接的特征词出现的频次， $f _ { j }$ 表示该边连接的情感词出现的频次， $p _ { 1 }$ ， $p _ { 2 }$ 分别表示特征词和情感词出现的概率。

$$
I ( p _ { 1 } ) = - p _ { 1 } l o g _ { 2 } p _ { 1 }
$$

$$
I ( p _ { 2 } ) = - p _ { 2 } l o g _ { 2 } p _ { 2 }
$$

为了计算的更加准确，我们用下式作为边的权重，即

$$
w = ( - p _ { 1 } l o g _ { 2 } p _ { 1 } - p _ { 2 } l o g _ { 2 } p _ { 2 } ) l o g _ { 2 } f
$$

# 1.5加权特征词相似度计算

SimRank相似度算法中，由于两节点共同相连的边越多意味着节点相似度越高，本文在二分

网中加入权重来计算特征词之间的相似度。即改进的SinRank相似度算法。加权的SimRank迭代算法：

$$
R _ { 0 } = ( a , b ) = { \binom { 0 , a \neq b } { 1 , a = b } }
$$

$$
\begin{array} { r } { R _ { k + 1 } ( a , b ) = \left\{ \frac { c } { | I ( a ) | | I ( b ) | } \sum _ { i = 1 } ^ { | I ( a ) | } \sum _ { j = 1 } ^ { | I ( b ) | } R _ { k } \left( I _ { i } ( a ) , I _ { j } ( b ) \right) w ( I _ { i } ( a ) \to a ) w ( I _ { i } ( b ) \to b ) , a \ne b \right. } \\ { \left. 1 , a = b \right. \qquad } \end{array}
$$

在此基础上计算每条边的特征词和情感词两端点所携带的信息熵：

其中： $w ( I _ { i } ( a ) \to a )$ 表示与 $a$ 相连的第 $i$ 个入邻点之间边的权重。二分网络中加权的SimRank 公式：

$$
\begin{array} { r } { \mathrm { S } ( A , B ) = \frac { C _ { 1 } } { \vert \sigma ( A ) \vert \vert \sigma ( B ) \vert } \sum _ { i = 1 } ^ { \vert \sigma ( A ) \vert } \sum _ { j = 1 } ^ { \vert \sigma ( B ) \vert } S \left( O _ { i } ( A ) , O _ { j } ( B ) \right) w ( O _ { i } ( A ) \to A ) w \big ( O _ { j } ( B ) \to B \big ) , A \ne B } \end{array}
$$

其中： $w$ 为情感词-特征对边的权重；节点A和 $B$ 之间的相似度即为A， $B$ 的所有出度间加权相似度的平均值。同理，在情感词-特征对的二分网中A， $B$ 代表特征词，特征词A， $B$ 之间的相似度等于指向A， $B$ 的所有情感词之间加权相似度的平均值。

# 2 数据分析

本文在Python中编写爬虫程序，从京东商城中抓取某电脑的全部在线评论。LTP语言云对每条评论分词标注，提取情感词-特征对，首先根据SimRank相似度计算各特征词之间的相似度。部分结果如表2所示。

表2未加权的特征词相似度  

<html><body><table><tr><td>SimRank</td><td>卡</td><td>电脑</td><td>屏幕</td><td>本本</td><td>外观</td><td>外形</td><td></td><td>笔记本</td><td>快递</td><td>物流</td><td>显卡</td></tr><tr><td>卡</td><td></td><td>0.003</td><td>0.0046</td><td>0.005</td><td>0.016</td><td>0.04</td><td></td><td>0.04</td><td>0.0133</td><td>0.0067</td><td>0.005</td></tr><tr><td>电脑</td><td>0.003</td><td></td><td>0.0027</td><td>0.003</td><td>0.0036</td><td>0.003</td><td></td><td>0.0059</td><td>0.004</td><td>0.0049</td><td>0.003</td></tr><tr><td>屏幕</td><td>0.0046</td><td>0.0027</td><td></td><td>0.0015</td><td>0.0049</td><td>0.002</td><td>：</td><td>0.0062</td><td>0.0041</td><td>0.0031</td><td>0.0038</td></tr><tr><td>本本</td><td>0.005</td><td>0.003</td><td>0.0015</td><td>-</td><td>0.012</td><td>0.0267</td><td>：</td><td>0.002</td><td>0.0067</td><td>0.0033</td><td>0.005</td></tr><tr><td>外观</td><td>0.016</td><td>0.0036</td><td>0.0049</td><td>0.012</td><td></td><td>0.0091</td><td></td><td>0.032</td><td>0.0107</td><td>0.0107</td><td>0.008</td></tr><tr><td>外形</td><td>0.04</td><td>0.003</td><td>0.002</td><td>0.0267</td><td>0.0091</td><td></td><td></td><td>0.023</td><td>0.008</td><td>0.008</td><td>0.003</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>…</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>笔记本</td><td>0.04</td><td>0.0059</td><td>0.0062</td><td>0.002</td><td>0.032</td><td>0.023</td><td>：</td><td></td><td>0.0533</td><td>0.0267</td><td>0.02</td></tr><tr><td>快递</td><td>0.0133</td><td>0.004</td><td>0.0041</td><td>0.0067</td><td>0.0107</td><td>0.008</td><td></td><td>0.0533</td><td></td><td>0.0267</td><td>0.0133</td></tr><tr><td>物流</td><td>0.0067</td><td>0.0049</td><td>0.0031</td><td>0.0033</td><td>0.0107</td><td>0.008</td><td>：</td><td>0.0267</td><td>0.0267</td><td></td><td>0.002</td></tr><tr><td>显卡</td><td>0.005</td><td>0.003</td><td>0.0038</td><td>0.005</td><td>0.008</td><td>0.003</td><td></td><td>0.02</td><td>0.0133</td><td>0.002</td><td></td></tr></table></body></html>

从实验后的相似度数据可以看出，由于表中数据的鉴别指数 $\mathsf { D } = P _ { h } - P _ { d }$ ，即最大值与最小的差为0.0513。并且衡量数据离散程度的方差为0.00014，都非常小，所以未加权的特征词之间的相似度区分度不高。同类特征词之间的相似度与不同类特征词之间的相似度差别不大。

对表2中的数据加权后得到表3中的数据，鉴别指数为

0.8871，方差为0.06718。相比较表2中的数据，表3中的数据有了很大的区分度。如表3中加黑部分的相似度值，同类特征词的相似度明显高于不同类的特征词，实验数据便于做后续的聚类分析。

表3加权的特征词相似度  

<html><body><table><tr><td>WSimRank</td><td>卡</td><td>电脑</td><td>屏幕</td><td>本本</td><td>外观</td><td>外形</td><td></td><td>笔记本</td><td>快递</td><td>物流</td><td>显卡</td></tr><tr><td>卡</td><td>-</td><td>0.1012</td><td>0.0582</td><td>0. 2754</td><td>0.1937</td><td>0.0110</td><td></td><td>0.0173</td><td>0.3337</td><td>0.0115</td><td>0.8046</td></tr><tr><td>电脑</td><td>0.1012</td><td></td><td>0.1363</td><td>0.7059</td><td>0.0655</td><td>0.0353</td><td></td><td>0. 7934</td><td>0.3234</td><td>0.0324</td><td>0.0555</td></tr><tr><td>屏幕</td><td>0.0582</td><td>0.1363</td><td></td><td>0.0071</td><td>0.1170</td><td>0.0544</td><td>：</td><td>0.4755</td><td>0.0112</td><td>0.0261</td><td>0.0390</td></tr><tr><td>本本</td><td>0.2754</td><td>0.7059</td><td>0.0071</td><td>-</td><td>0.0675</td><td>0.0204</td><td></td><td>0.6784</td><td>0.3131</td><td>0.0279</td><td>0.0085</td></tr><tr><td>外观</td><td>0.1937</td><td>0.0655</td><td>0. 1170</td><td>0.0675</td><td></td><td>0.8250</td><td></td><td>0.5080</td><td>0.2761</td><td>0.0617</td><td>0.0241</td></tr><tr><td>外形</td><td>0.0110</td><td>0.0353</td><td>0.0544</td><td>0.0204</td><td>0.8250</td><td>-</td><td></td><td>0.2335</td><td>0.0878</td><td>0.0322</td><td>0.0243</td></tr><tr><td></td><td>：</td><td>：</td><td></td><td>：</td><td></td><td></td><td></td><td>：</td><td>：</td><td></td><td>：</td></tr><tr><td>笔记本</td><td>0.0173</td><td>0.7934</td><td>0.4755</td><td>0.6748</td><td>0.5080</td><td>0.2335</td><td></td><td>-</td><td>0.2845</td><td>0.0077</td><td>0. 1847</td></tr><tr><td>快递</td><td>0.3337</td><td>0.3234</td><td>0.0112</td><td>0.3131</td><td>0.2761</td><td>0.0878</td><td>：</td><td>0.2845</td><td></td><td>0.8942</td><td>0.0402</td></tr><tr><td>物流</td><td>0.0115</td><td>0.0324</td><td>0.0261</td><td>0.0279</td><td>0.0617</td><td>0.0322</td><td>：</td><td>0.0077</td><td>0.8942</td><td>-</td><td>0.0335</td></tr><tr><td>显卡</td><td>0.8046</td><td>0.0555</td><td>0.0390</td><td>0.0085</td><td>0.0241</td><td>0.0243</td><td></td><td>0.1847</td><td>0.0402</td><td>0.0335</td><td></td></tr></table></body></html>

# 3 基于相似度聚类

本文给出了情感词-特征对边的相似度以后，特征词种类的划分就可以转化为聚类问题，基于相似度矩阵的聚类算法进行划分。在复杂网络的网络簇结构中存在着同族节点之间连接密集，不同节点之间连接稀疏的特征。根据这样的特征对网络节点进行聚类，使得同类节点之间连接密集，不同类节点之间连接稀疏。

这里使用谱聚类算法[4对网络节点中的特征词进行聚类[15]。这里谱聚类是根据特征词之间的相似度，将它们分成不同组。根据谱聚类的思想，将特征词看作顶点V，特征词之间的相似度看作带权的边 $E$ ，得到一个基于相似度的无向加权图$\mathsf { G } ( V , E )$ ，两点之间有边相连权重大于零，无边相连权重等于零，从而将聚类问题转为图分割问题。如图4所示。谱聚类能找到一种最优的图分割的方法，该方法使分割后的子图内部有最大的相似度，子图之间有最小的相似度。也就是不同组之间相连的边权重尽可能低，即组间相似度尽可能低，各个组内部相连的边权重尽可能高，即组内相似度尽可能高。

![](images/201cac918507fd30cd3d3fb09991233abdb0b8e257679431120505af150443e7.jpg)  
图4聚类原理图

实现方法的总体框架可以归纳为三个主要步骤：

a)构建表示对象集的无向加权图，即相似度矩阵W，同时指定需要聚类的簇数k。根据前面加权的SimRank 算法得到特征词之间的相似度矩阵。所以该聚类中无需再计算相似度矩阵，直接进行后半部分的步骤即可。且该相似度矩阵W具有如下性质：矩阵 $N \cdot N$ ，为特征词总数；矩阵对角线的值为0；矩阵为对称矩阵，即相似度是无向的。此时，谱聚类的任务就是根据这个相似度矩阵W，将这 $N$ 个特征词分成不同的组，小组内部的特征词彼此都很像，小组之间则不像。通过这个相似度矩阵得到对应的图分割方案。

b)计算对角矩阵 $D ( N \cdot N )$ ：

$$
\begin{array} { r } { D _ { i , i } = \sum _ { j } ^ { N } w _ { i , j } } \end{array}
$$

对角矩阵 $D$ 对角线上的值为矩阵W中对应行或列的和，指的是度矩阵，即和点i相连的所有边的权重之和， $w _ { i , j }$ 指得是第i行对应第j点的度数。为了有利于后面子图内部的极大化，利用相似度矩阵构造拉普拉斯矩阵 $L$ ： $L = D - L$ 。再将拉普拉斯矩阵标准化，即归一化 $L$ 矩阵：

为了将 $L$ 降维，计算 $L$ 矩阵的 $K$ 个最小特征值以及对应的特征向量，并将 $K$ 个特征向量按列排放，形成 $N \cdot K$ 的特征矩阵。

c)对这里的特征矩阵进行 $\mathrm { \bf K }$ -means聚类，得到的 $N$ 维向量分别对应相似度矩阵W中每一行所代表的特征词所属类别，也即最终聚类结果。

# 4 实验结果与分析

如图5所示，横轴表示聚类的个数，纵轴表示每个聚类包含的个数，即每个聚类包含的节点数量。第一张图为聚类簇数$k$ 取15时未加权SimRank相似度矩阵聚类出的结果，第二张图是用传统的K-means聚类后的结果，最后一张图是本文中改进的加权相似度矩阵聚类出的结果。由图可以看出，未加权的相似度矩阵几乎无法进行聚类。相比之下，最后一张图的聚类效果要更加明显。且和传统的K-means聚类相比较聚类效果也更好。

![](images/5a7105a59900a7128243d343dee6933da2d397d85db0c6d9484b43924cb1088c.jpg)  
图5相似度聚类图

这里从每一行聚类分布的结果中得到聚类分布情况，电脑特征聚类部分结果如表4所示，第一列表示该簇的簇中心，第二列是该簇的簇内成员。从表中可看出，谱聚类效果较好且不受离群点的影响，如第二簇中的“做工”可单独作为一个簇。实验结果显示，本文所用方法准确率较高，更加适合特征词聚类。

表4特征词列表样例  

<html><body><table><tr><td>簇中心</td><td>簇内成员</td></tr><tr><td>卡</td><td>显卡</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">做工</td></tr><tr><td>笔记本</td><td>本本，本子，电脑</td></tr><tr><td>外形</td><td>颜值，外观，外型，外壳…</td></tr><tr><td>音质</td><td>音效，音，音色，音响效果，声音…</td></tr><tr><td>物流</td><td>快递，发货，送货…</td></tr><tr><td>价格</td><td>价位，秒价，价钱，特价</td></tr><tr><td>字</td><td>字体，文字，字号…</td></tr><tr><td>手感</td><td>质感，触感，塑料感，印刷感，体验感，动</td></tr><tr><td>感</td><td></td></tr><tr><td>性能</td><td>流畅性，扩展性，便携性，兼容性</td></tr><tr><td>配置</td><td>配件，适配器，配器</td></tr><tr><td>内存</td><td>容量，大小，内存条…</td></tr><tr><td>音响</td><td>音箱</td></tr><tr><td>插□</td><td>□，接口</td></tr><tr><td>机器</td><td>机，一款机，机子，机身，真机，新机子，主</td></tr><tr><td></td><td>机</td></tr><tr><td></td><td>：</td></tr></table></body></html>

# 5 结束语

大数据时代海量的文本信息需要进行有效的处理，而特征词挖掘是文本信息处理的基础。针对产品评论挖掘产品特征进行了研究。本文首先通过依存句法实验训练出特征词与情感词之间的语法关系，并通过语法关系提取出某在线产品评论的全部情感词-特征对；然后将情感词-特征对放入二分网中，基于二分网使用SimRank算法计算特征相似度；为实验结果更加准确，提出基于改进的SimRank相似度出发，即加权特征相似度。基于商品特征相似度的聚类算法有效地对相近的商品特征进行聚类，成功降低了商品特征维度，为评论挖掘的进一步研究奠定基础。实验表明，本文所提出的改进后的特征词相似度计算方法能有效提高聚类准确度。同时也存在一些不足，如通过LTP提取出的情感词-特征对并非完全准确，这给后续的相关研究工作带来不便。针对存在的不足之处，将做进一步研究。

# 参考文献：

[1]Liu Bing.Sentiment analysis and opinion mining [M].Morgan:Claypool Publishers,2012: 67-77.   
[2]Hu Minqing,Liu Bing.Mining and summarizing customer reviews [C]// Proc of the 1Oth ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York: ACMPress,2004:168-177.   
[3]Kamal A,Abulaish M,Anwar T.Mining feature-opinion pairs and their reliability scores from web opinion sources [C]// Proc of the 2nd International Conference on Web Intelligence,Mining and Semantics.2012: 1-7.   
[4]Hu Minqing,Liu Bing.Mining opinion features in customer reviews [C]/ Proc of the 19th International Conference on Artifical Intelligence.San Jose: AAAIPress 2004: 755-760.   
[5]李实，叶强，李一军，等.挖掘中文网络客户评论的产品特征及情感倾 向[J].计算机应用研究,2010,27(8):3016-3019.(Li Shi,Ye Qiang,Li Yijun,et al.Mining Product Features and Sentiment Orientation from Chinese Customer Reviews [J].Application Research of Computers,2010, 27(8):3016-3019.)   
[6]刘鸿宇，赵妍妍，秦兵，等．评价对象抽取及其倾向性分析[J].中文 信息学报,2010,24(1):84-88.   
[7]Jin J,Liu Y,JiP,et al.Understanding big consumer opinion data for marketdriven product design [J]. International Journal of Production Research, 2016,54 (10): 3019-3041.   
[8]张珠，贾文杰，夏迎炬，等．商品属性归类技术研究[C]//第六届全国 信息检索学术会议论文集.2010.   
[9]Shi B,Chang K.Mining Chinese Reviews [C]//Proc of the 6th IEEE International Conference on Data Mining.Washington DC: IEEE Computer Society,2006: 585-589.   
[10]Xu H, ZhangF,WangW.Implicit feature identification in Chinese reviews using explicit topic mining model [J].Knowledge-based systems,2015,76 (5): 166-175.   
[11] YiJ,Nasukawa,Bunescu R,etal. Sentiment analyzer: extracting sentiments about a given topic using natural language processing techniques [C]// Proc of the 3rd IEEE International Conference on Data Mining.Washington D C: IEEE Computer Society,2003:427.   
[12] Zhang S,Jia W,Xia Y,et al.Product features extraction and categorization in Chinese reviews [C]//Proc of the 6th IEEE International Conference on Advanced Information Management and Service.2010:324-329.   
[13] Glen J,Widom J. SimRank: a measure of structural-context similarity [C]// Proc of the 8th ACM SIGKDD International Conference on Knowledge DiscoveryandData Mining.New York:ACMPress,2002:538-543   
[14] Li S,Hao J. Spectral clustering-based semi-supervised sentiment classification [C]// Advanced Data Mining and Applications.Berlin: Springer,2012:271-283.   
[15] Pang B,Lee L. Opinion mining and sentiment analysis [J]. Foundations and Trends in Information Retrieval,2008,2(1//2):1-135.