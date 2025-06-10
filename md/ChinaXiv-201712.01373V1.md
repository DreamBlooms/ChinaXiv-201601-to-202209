# 什么样的评论更容易获得有用性投票以亚马逊网站研究为例

# 吴江 刘弯弯

(武汉大学信息管理学院武汉 430079)(武汉大学电子商务研究与发展中心武汉 430079)

摘要：【目的】购物网站评论系统中的投票机制有利于帮助消费者筛选出高质量评论。本文以评论有用性投票数为研究对象，探讨什么样的评论更容易获得有用性投票。【方法】以信息采纳理论和负面偏差理论为基础，基于亚马逊购物网站中的12393条手机评论数据，结合文本分析与零膨胀负二项回归分析方法，从评论者信度、评论信息质量、评论极性三个方面探究评论有用性投票影响因素。【结果】研究结果表明，评论者有用性、评论信息量、评论回复数、极端评分、评论文本消极倾向对评论有用性投票数具有积极正向影响。评论者发表评论数、评论者是否确认购买对评论有用性投票数有负向影响。【局限】仅以手机这一搜索型产品为研究对象，研究结果欠缺普适性。【结论】本文研究成果对于改善电子商务评论排序系统具有借鉴意义。

关键词：在线评论 评论有用性评论投票分类号：G203

# 1引言

用户生成内容(User Generated Content,UGC)是Web2.0时代的一个重要产物，并随着微博、微信、论坛等社交平台的出现而逐渐扩大了影响力。购物网站中的在线评论是UGC 中的一个重要内容，对于消费者购买决策过程具有辅助作用。然而，购物网站中的在线评论存在数量庞大且质量参差不齐等问题[1]。为了帮助消费者对评论质量进行评估并筛选出高质量评论，亚马逊、淘宝、京东等购物网站推出了评论有用性投票机制。例如，亚马逊在每一条评论后向消费者提问“该条评论是否对你有用？”。消费者回答“是”，则评论有用投票数加1，消费者回答“否”，有用投票数不增加，总投票数加1。每一条评论后都有一个有用性评估指标，例如"10人中有9人认为此评论有用”。许多研究者以评论有用性投票数除以评论总投票数的值为评论有用性衡量指标，进一步探究什么样的评论才是消费者认为有用的评论，即评论有用性影响因素[2-8]。例如，Liu等以IMDB上的影评数据为例，采用回归分析方法，以评论有用性为因变量，探究了评论者的专业程度、评论书写的模式、评论发表时间对评论有用性的影响。Mudambi等4以亚马逊上6种商品(包括搜索品和体验品两种)的评论投票数大于2的评论数据为研究对象，利用tobit回归模型，研究评论评分、评论长度对评论有用性的影响，并进一步探究了商品类型对这种影响的调节作用，从信息诊断性这一角度对结果进行解释。

这些研究在探讨什么样的评论对于消费者来说有用这一问题上做出了许多贡献。但是这些研究存在两个问题。首先，多数研究以亚马逊中的评论有用性为因变量研究评论的质量[4-5.7]。这种衡量模式忽略了投票基数带来的影响力。例如，评论有用性为1的投票，可以是"1人中有1人觉得该评论有用”，也可以是"10人中有10人觉得该评论有用”。这两种计算方式的结果虽然一样，但是显然后者的质量和影响力高于前者，而许多前人研究忽略了这一点。其次，这些研究在探讨评论有用性时，所采用的评论都是有投票的评论，对于没有投票的评论因为无法计算评论有用性而排除在样本之外。然而有的商品评论集中，超过 $50 \%$ 的评论并没有投票[1]。本研究采用的12393 条评论数据集中，也有高达 $69 \%$ 的评论没有投票，这些没有投票的评论并不都是没有用的。只包含有投票评论的样本将是一个非随机样本，采用该样本进行回归会产生误差[9]。

为避免这两个问题，同时体现评论对于消费者的有用性价值，本文以评论有用性投票为研究对象。评论有用性投票一方面体现了消费者对评论的认可度,另一方面体现了评论的高影响力。因为评论投票数越高，代表赞成这一观点的消费者越多，那么该观点所影响的消费者数越多。因而，评论有用性投票这一指标相对评论有用性增加了对投票人数的考量。那么，什么样的评论更容易获得有用性投票呢？研究这样一个问题，将有助于理解消费者的投票行为，帮助改善购物网站评论投票系统。本文以此为出发点，以亚马逊中的手机评论数据为研究对象，将有投票和没有投票的评论都纳入样本中，以评论的有用性投票数为因变量，采用零膨胀负二项回归模型对评论有用性投票影响因素进行探究。

# 2理论基础与假设

# 2.1 理论基础

# (1）信息采纳理论

为了更好地解释消费者判断评论是否有用的行为过程，笔者引人 Sussman 和 Siegal[10提出的信息采纳模型，这也是前人关于评论有用性研究中最常用的理论模型[11-13]。因为消费者在对评论进行投票的过程实际上是评估评论信息是否有用，进而决定是否采纳的过程。该模型认为消费者决定对一条信息是否采纳的过程中，通常会从两个角度考虑，一是信息源的可信度，二是信息的质量[9]。即消费者从信息质量和信息源可信度两个角度对信息进行权衡以后，则会判断该条信息是否对自己有用，进一步地确定是否采纳该信息，从而做出态度或行为的改变。

信息源的可信度是指由于信息源具有和用户信息需求主题相关的知识或经验而使用户相信信息源能提供与需求和预期相关的客观性信息或意见的程度。信息源的可信性具体表现为专业性和真实性[14]。

而关于信息质量的定义及度量就要复杂得多，不同的学者给出了不同的答案[15-16]。对于信息质量的度量,Gorla等[17认为信息质量涉及完整性、准确性和及时性三个维度。Filieri 等[18]在对用户对旅游评论信息的采纳研究中，在Gorla等的基础上进一步加上相关性、可理解性和增值性三个维度探讨在线评论的信息质量。在本文中，由于研究的情境是电子商务购物网站中的在线商品评论，用户浏览评论的目的是为了减少信息不对称性从而做出购物决策，因此将信息质量定义为信息能够满足用户进行购物决策所达到的要求。

在消费者对评论进行投票的情境中，消费者对信息源的评估指的是对评论者信息的评估，而信息质量的评估主要是指评论内容的评估。

# (2）负面偏差理论

Kanouse和Hansonn在1972年提出的负面偏差理论[19]指出，相同强度的负面事情(例如，不开心的想法、情绪、事件等)相对于中立或者积极的事情，对一个人的心理状态有着更强烈的影响[20]。也就是说，对于同等情感强度的正面信息和负面信息，负面信息对于消费者的行为和认知的影响强于正面信息。进一步地，负面偏差对于消费者的决策具有影响[21]。因为当个体在获得和损失之间进行决策时，个体更多地会考虑损失。因而，相比于正面评论对于商品的肯定，消费者更看重负面评论中的内容。因为负面评论会传递这样一个信息：我付钱购买该商品将会产生哪些效用损失。因此，除了信息源和信息的质量以外，信息所包含的情感极性也会影响消费者对信息的采纳。

因此，本文从评论者信度、评论信息质量、评论极性三个角度考察评论有用性投票影响因素。

# 2.2 评论者信度

许多研究发现，评论者信息对消费者对评论有用性的评估具有显著影响。前文指出，评论者信息与评论有用性之间的关系主要是从信息源的可信度这一视角考虑的。关于信息源可信度的度量角度包括评论者声誉、评论者等级、评论者排名、评论者专业性、评论者历史评论信息等[5-6,22-23]。这些角度可归纳为两个方面：评论者的专业性和真实性。本文结合亚马逊网站的数据特点，对评论者信度的衡量也从这两个方面展开。

亚马逊网站上提供的评论者信息包括评论是否为排名前1000名的评论者、评论者历史发表评论的有用性即评论者有用性(评论者发表的所有评论获得的有用性投票数除以总投票数)、评论者发表的评论数、评论者是否确认在亚马逊上购买过商品。对于评论排名前1000名的评论者，亚马逊都会在评论页上提示。而本文不采用此种衡量方式，因为亚马逊上的评论者数量庞大，有一些商品的评论中可能不包含排名在前1000 名的评论者。在本文采集的12393条样本数据中，也只有 40 条评论的评论者是前1000 名评论者，采用该指标并不合适。

除评论者排名外，有学者研究发现评论者的历史评论信息可以预测评论的有用性[5,23]。Ghose和Ipeirotisl研究发现，对于DVD产品和数码相机，评论者的历史信息对其评论有用性存在显著影响。评论者的历史信息反映了评论者的评论撰写经验，是对评论者可信度中专业性的度量。本研究认为评论者有用性是对评论者所发表的历史评论质量的度量，评论者有用性越高，评论所获得有用性投票数越高。评论者所发表的评论数是对评论者的评论经验的考察，评论者所发表的历史评论数越多，其当前评论所获得评论有用性投票数将越高。因此本文提出如下假设:

Hla：评论者有用性对评论有用性投票数有显著的正向影响。

H1b：评论者发表评论数对评论有用性投票数有显著的正向影响。

而对于评论者信息真实度的衡量，本文采用“评论者是否确认购买"这一指标。确认已经在亚马逊上购买商品的用户其评论通常是真实的，而那些没有确认购买的用户其发表的评论可能是虚假的，其信服力更低。因此本文提出如下假设：

Hlc：评论者的购买真实性对评论有用性投票数有显著的正向影响。

# 2.3 评论信息质量

评论信息质量的好坏体现在为消费者购物决策提供信息支持的评论内容上。许多学者在对评论有用性的研究中将评论内容纳为影响因素。其中评论可读性[5,7,24]和评论长度[4,7,25]是研究最多的两个变量。评论可读性是指评论是否容易阅读，这一指标会影响消费者对评论内容的理解[5]。英文中有FRES[24]、FOG[7]等较成熟的文本可读性测量方法，可以方便地做文本可读性计算。然而，中文中并没有成熟的可读性测量方法，因此本文不考虑这一影响因素。评论长度代表评论中的信息总量，越长的评论，信息量越大，评论越有用[4]。但另一部分学者研究发现，评论长度与评论有用性并不成正比，中等长度的评论比过短或过长的评论更有用[15]。过短的评论无法提供足量有效信息,过长的评论可能使消费者失去阅读耐心，因而这两种评论对消费者而言都没有用[26]。另有学者质疑以在线评论长度代表评论信息量的方式[27]。因为有些评论虽然很长，但是包含许多无用信息。那么什么才是有效的信息，什么样的信息对于消费者而言有用？如果评论中所包含的内容能够集中代表其他用户所反映的观点，那么可以认为该条评论所包含的信息是有效的，该评论对消费者而言也越有用。

本研究认为，当一条评论所包含的内容越能够代表其他评论的内容时，该评论所包含的信息量越高。评论所包含的信息量越多，评论有用性越高。本文采用一种自动文本摘要算法，对每个产品的评论集中每条评论文本所包含的信息量进行评估。因而本文提出如下假设:

H2a：评论信息量对评论有用性投票数有显著的正向影响。

亚马逊网站允许所有浏览评论的浏览者对评论进行回复。这些回复包括浏览者和评论者之间的回复互动及亚马逊商家对评论者在评论中提出的问题的官方解答。这些回复是对评论文本内容的补充，能够帮助其他消费者进一步加深对商品和服务的了解，对其十分有用。因而，本文认为评论的回复数越多，评论获得的有用性投票数将越高。因而本文提出如下假设：

H2b：评论回复数对评论有用性投票数有显著的正向影响。

# 2.4 评论极性

前文指出，信息的情感极性对信息采纳也具有影响。在以往评论研究中，对于评论极性的衡量从两个角度出发：评论评分极性、评论文本极性。评论评分的极性认为评分过高或过低的评论为极性高的极端评论，中间评分的评论为极性低的温和评论[4]。这种评分的变化实际上反映了评论者态度极性的变化。关于评论极性和评论有用性之间的关系，不同的学者的研究结果有所差异。一方面，中间评分的评论由于能够更客观地表述产品的优点和缺点，因而更令人信服，通常会被消费者认为更有用。例如,Mudambi等4发现对于经验型产品，中间评分比极端评分更有用。另一方面，也有学者研究发现，相比于中间评分，消费者更容易受极端评分的影响[28]。本研究认为，在不考虑评论内容的前提下，极端评分相对于中间评分更能够吸引消费者的注意，因而能够获得更多的有用性投票。因而提出如下假设：

H3a:评分极性对评论有用性投票数有显著的正向影响。

评论评分仅仅是对评分极性的衡量，并没有涉及到评论内容的情感极性。因而有学者利用文本分析方法，进一步探究了评论文本中的积极和消极[24,29-31]、焦虑和生气[8]、主客观[5]等情感因素对评论有用性的影响，即评论文本极性。本文将探讨评论中的积极情感和消极情感对评论有用性投票的影响。负面偏差理论指出，相对于中立和积极信息，消极信息对消费者影响更大[19]。因而本文提出如下假设:

H3b:评论消极情感倾向对评论有用性投票数有正向影响。  
H3c：评论积极情感倾向对评论有用性投票数有负向影响。  
本文的研究模型如图1所示。

![](images/3182ad6224df9657dbe2c0cedf028de37b03e617012075643f397e2a2a359606.jpg)  
图1评论有用性投票实证研究模型

# 3研究设计

# 3.1 数据收集

在线评论的相关研究多以英文亚马逊网站为研究对象。为和国外研究结果进行对比，本文以亚马逊中国网站中的评论数据为研究对象。有学者研究发现产品类型对消费者感知评论有用性具有调节作用[4]。因而选取以往研究[4.32]中常用的搜索品—手机为研究对象进行数据爬取，排除了产品类型对评论有用性的影响。利用GooSeeker爬取亚马逊2016年1月8日这一天销量排名前100的100部手机评论数据。为保证研究的准确性，按照评论ID对重复数据进行删除；同时，删除总评论数小于100的样本。最后共得19部手机的12393条评论数据。其中每条评论数据包括以下内容：评论评分；评论时间；评论文本；评论回复数;评论者排名；评论者有用性；评论者发表评论数；评论者是否确认购买该商品；手机总评论数；手机销量排名；评论有用性投票数。

# 3.2 变量设计

为了验证本文假设，设计了如表1所示的变量。其中因变量为评论有用性投票数，即认为该条评论有用的投票的总数。自变量包括评论者信度、评论信息质量、评论极性三个部分。

表1变量设计  

<html><body><table><tr><td>变量类型</td><td>变量名</td><td>变量</td><td>变量解释</td></tr><tr><td rowspan="7">自变量</td><td>评论者有用性</td><td>reUse</td><td>评论者获得有用性投票数/ 评论者获得的总投票数</td></tr><tr><td>评论者发表 评论数</td><td>reNum</td><td>评论者已经发布的评论的 总数</td></tr><tr><td>是否确认购买</td><td>buyornot</td><td>评论者是否确认在亚马逊 上购买商品(0表示未确 认购买;1表示确认购买)</td></tr><tr><td>评论信息量 评论回复数</td><td>reInfo comment</td><td>评论文本所包含信息量 评论下的回复总数</td></tr><tr><td>评分极性</td><td>rateGap</td><td>评分与平均评分差值的绝 对值</td></tr><tr><td>评论积极倾向</td><td>pos</td><td>积极词汇总数/评论长度</td></tr><tr><td>评论消极倾向</td><td>neg</td><td>消极词汇总数/评论长度</td></tr><tr><td>因变量</td><td>评论有用 性投票数</td><td>usefulNum</td><td>评论获得的有用性投票 总数</td></tr></table></body></html>

# (1）评论者信度

评论者信度信息包括评论者有用性(reuse)、评论者发表评论数(reNum)、是否确认购买(buyornot)三个变量。其中评论者有用性指评论者发表的所有评论所获得总有用投票数与总投票数的比值，是一个值域在[0，1]的数值变量；该值越大表示该评论者所发表的评论受到其他消费者认可度越高，是对消费者已发表评论的质量的衡量。评论者发表评论数是消费者在亚马逊网站上发表的所有评论的数目。评论者是否确认购买，是一个二元变量，0表示评论者未确认在亚马逊上购买该商品,1表示评论者已确认在亚马逊上购买该商品。

# (2）评论信息质量

评论信息质量衡量指标包括评论信息量(reInfo)、评论回复数(comment)两个变量。对于评论信息量的计算，采用基于文本相似性思想的LexRank[33]算法。该算法是一种文本自动摘要算法，能够对文档中每个句子所包含的信息量进行评估，从中抽取出信息含量最多的一个句子[34]。算法的基本思想是：将每一个句子视作无向图 $\scriptstyle { \mathrm { G = } } ( \mathrm { S } , \mathrm { ~ E } )$ 中的节点，当句子间的相似度大于某一阈值时，则认为这两个句子语义相关并将它们连接起来；节点s的度d代表与节点s相连的边的数目;当节点的度d越大时，代表与其关联的句子越多，那么该节点就越重要，同时与重要节点相连的节点也很重要，而节点的特征向量中心性可以表征这一关系;通过计算节点的特征向量中心性，来表示节点对于整个网络的重要程度，节点的特征向量中心性越大，该节点就越重要，即该句子所包含的信息量越大。因此可以利用LexRank算法计算每一个商品评论集中所包含的评论的信息量。采用LexRank算法计算评论信息量之前，需要计算评论之间的文本相似度。对于评论文本之间的相似度，采用经典的基于TF-IDF的余弦相似度算法[35]。本研究中的具体做法如下:

$\textcircled{1}$ 构建用户词典与停用词词表。其中用户词典来源是搜狗语料库中的手机、网购词库及第三方手机评测网站中关村在线上关于本研究所涉及的手机产品零部件的描述，一共234个。

$\textcircled{2}$ 利用ICTCLAS分词系统[36对每一个商品中所有评论进行分词处理，去掉停用词及低频词，形成基于不同商品的评论词袋。

$\textcircled{3}$ 计算某一商品每一条评论中词语的 TF-IDF值，从而对商品的评论集进行VSM建模。所形成的矩阵的每一行表示商品中的每一条评论，而每一行中的值是每一条评论中每一个词的TF-IDF值。

$\textcircled{4}$ 计算矩阵中每一行的值与其余行的余弦夹角值，以其作为每一条评论与商品评论集中其余评论的余弦相似性值，从而形成评论余弦相似性矩阵。

$\textcircled{5}$ 利用LexRank 算法对余弦相似性矩阵进行处理，获得每一条评论的信息量，用变量reInfo表示。

评论回复数(comment)为每一条评论下其他消费者对该评论的回复总数。这些回复能够进一步揭露消费者所关心的问题，有助于丰富评论信息内容，提高消费者对该条评论有用程度的感知。

# (3）评论极性

评论极性包括评分极性(rateGap)、评论积极倾向(pos)、评论消极倾向(neg)。评分极性(rateGap)采用评论评分和商品平均评分的差值的绝对值。该值越大，表示该评论持有不一样的观点，可能会吸引更多的消费者进行有用性投票[28]。评论文本的积极和消极情感倾向的计算，采用评论文本中积极或消极词汇的数量除以评论长度的方式[24,27]。本文利用台湾大学的NTUSD 情感极性词典[37识别评论文本中的积极和消极词汇。考虑到评论文本中包含一些表达情感的网络用语(例如"赞”、“坑爹"等)，以及关于手机的情感词汇(例如"瑕疵品”、“推荐”、“值得购买"等)，而NTUSD中不包含这些词汇，因此需要补充加入。关于这一部分词汇的补充，利用ICTCLAS系统对所有样本数据进行分词[36]，统计高频词汇，从词频大于10的词汇中筛选高频情感词汇；两位实验室人员分别阅读1000条长度最长评论，选出情感词，而后对比情感词选择结果，对情感词典进一步补充；最后重组成基于手机网购评论的NTUSD情感词典。通过ICTCLAS分词器及NTUSD情感词典，可以有效地对样本数据中的评论文本进行情感词汇识别与情感计算。

# 3.3 分析方法

为验证本模型中假设，采用零膨胀负二项回归模型。采用该模型的原因主要有三个：

(1）因变量评论有用性投票数是一个计数变量，并不是一个连续变量，且不呈正态分布，不满足普通最小二乘回归模型的基本要求，因而采用泊松回归和负二项回归等计数模型更合适;(2）因变量均值为1.7、方差为189，方差远大于均值，数据较为分散，此种情况下采用泊松回归模型拟合效果不理想[38]，因而采用负二项回归模型;(3）因变量零值比例高达 $69 \%$ ，而零膨胀负二项回归模型能够在数据分散、零值多的情况下进行更好的拟合[39]

零膨胀负二项模型通常由两部分组成：决定因变量是否发生的逻辑回归模型，该模型对因变量中的零值进行解释；负二项回归模型，该模型对因变量的值的大小进行解释。消费者对评论进行投票时，并没有阅读所有的评论。因此有的评论的有用性投票数为0,并不是因为该评论没有用，而可能是该评论并没有被消费者所阅读。如果直接采用负二项回归模型会产生偏差，因此需要对因变量中的零值进行解释。

本研究将评论发表时间(time)、商品总评论数(comNum)、商品排名(rank)作为解释变量，纳入零膨胀模型中。评论投票数是否为零值受两方面因素影响,一是消费者的投票习惯，如果消费者的投票习惯越为成熟，那么评论被投票的几率越高；二是评论的被阅读量，如果评论的被阅读量越少，那么评论投票数为零值的可能性越大。时间有助于评论投票习惯养成,消费者参与网上互动的行为将随着时间推移越来越强烈，因此将评论已经发表的时间(time)作为零膨胀因子。同时商品总评论数越多，平均每条评论被阅读的几率越小，被投票的几率都会减少；商品排名越靠前，代表商品热门程度越高，那么单位时间内相对于其他商品，其评论的浏览量更高，因而平均每条评论被投票的可能性越高。

本研究中的零膨胀负二项模型如下所示：

逻辑回归模型：

usefulNum $_ { 1 = \beta }$ 1time+β2comNum+β3rank+β4keyNums+ε, usefulNum $_ { = 0 }$

负二项回归模型:

usefulNum $_ { 1 = \beta }$ lreUse+β2reNum+β3buyornot+β4reInfo $1 + \beta 5$ comment+β6rateGap+β7pos+β8neg+ε,usefulNum $^ { = 1 }$ ,2,3·

其中逻辑回归模型是对因变量有用性投票数为0进行解释；负二项回归模型是本文的主要研究对象，其解释因子由评论者信度、评论信息质量、评论极性三大部分组成。

# 4数据分析与结果

# 4.1 描述性统计分析

各变量的描述性统计分析结果如表2所示。其中评论有用性投票数最小为0，最大为755，有用性投票数分布较离散。对有用性投票数进行频数统计，发现其呈现左偏分布。约 $69 \%$ 的评论有用性投票数为0，约$28 \%$ 的评论有用性投票数为1到10之间，仅有 $2 \%$ 的评论有用性投票数大于10。同有用性投票数一样，评论者发表的评论数也呈现较大的离散现象。虽然评论者发表评论数的均值达到10，但是约有 $51 \%$ 的评论者只在亚马逊发表过1到2次评论，这表明大部分评论者在亚马逊的评论经验不丰富。

表2描述性统计分析结果  

<html><body><table><tr><td>类别</td><td>变量名</td><td>平均值 标准差</td><td>最大值</td><td>最小值</td></tr><tr><td rowspan="4">评论者信度</td><td>usefulNum</td><td>1.70</td><td>13.77</td><td>755.00 0.00</td></tr><tr><td>reUse</td><td>0.37</td><td>0.38 1.00</td><td>0.00</td></tr><tr><td>reNum</td><td>9.91</td><td>27.73 781.00</td><td>1.00</td></tr><tr><td>buyornot</td><td>0.97</td><td>0.17 1.00</td><td>0.00</td></tr><tr><td rowspan="2">评论信息质量</td><td>reInfo</td><td>0.29</td><td>0.25</td><td>1.00 0.00</td></tr><tr><td>comment</td><td>0.19</td><td>0.81</td><td>44.00 0.00</td></tr><tr><td rowspan="3">评论极性</td><td>rateGap</td><td>1.01</td><td>0.81</td><td>3.41 0.03</td></tr><tr><td>pos</td><td>0.02</td><td>0.03</td><td>0.31 0.00</td></tr><tr><td>neg</td><td>0.01</td><td>0.02</td><td>0.18 0.00</td></tr><tr><td rowspan="3">零膨胀因子</td><td>time</td><td>417.72</td><td>265.92</td><td>973.00 0.00</td></tr><tr><td>rank</td><td>34.20</td><td>20.01</td><td>97.00 1.00</td></tr><tr><td>comNum</td><td>652.26</td><td>2495.11</td><td>6011.00 100.00</td></tr></table></body></html>

各变量之间的相关系数如表3所示，变量time 和comNum相关系数达到0.78，表明两者呈现正相关，根据变量对模型拟合优度贡献程度舍弃变量comNum，而选择变量time；其余自变量之间的相关系数均小于0.3，表明自变量之间不存在共线性问题。

# 4.2 回归分析结果与讨论

为更好地体现评论者信度、评论信息质量、评论极性三个部分的自变量对模型的解释作用。除包含全部变量的模型外，另加入两个模型进行对比。其中模型1是只包含有关评论者信度一类自变量的零膨胀负二项模型，模型2是包含有关评论者信度和评论信息质量两类自变量的零膨胀负二项模型，模型3是包含评论者信度、评论信息质量、评论极性三类自变量的零膨胀负二项模型。模型回归结果如表4所示，发现模型3的对数似然值的绝对值比模型1和模型2都要小，表明加入评论信息质量和评论极性两类变量能够提高模型的拟合优度。因此，本文以模型3的结果进行分析。同时，将模型3中的零膨胀负二项模型与包含模型3中所有变量的负二项模型进行Vuong检验。检验结果表明本研究采用零膨胀负二项模型比负二项模型拟合效果更好。

表3变量相关系数  

<html><body><table><tr><td></td><td>reUse</td><td> reNum</td><td> buyornot</td><td>reInfo</td><td>comment</td><td>rateGap</td><td>pos</td><td>neg</td><td>comNum</td><td> time</td><td>rank</td></tr><tr><td>reUse</td><td>1.00</td><td>0.22</td><td>-0.06</td><td>0.01</td><td>0.08</td><td>0.07</td><td>0.00</td><td>0.02</td><td>-0.06</td><td>-0.01</td><td>-0.05</td></tr><tr><td>reNum</td><td>0.22</td><td>1.00</td><td>-0.05</td><td>0.00</td><td>0.00</td><td>-0.06</td><td>0.00</td><td>-0.01</td><td>0.02</td><td>0.00</td><td>0.02</td></tr><tr><td>buyornot</td><td>-0.06</td><td>-0.05</td><td>1.00</td><td>0.02</td><td>-0.07</td><td>-0.10</td><td>0.02</td><td>-0.05</td><td>0.07</td><td>0.01</td><td>-0.06</td></tr><tr><td>reInfo</td><td>0.01</td><td>0.00</td><td>0.02</td><td>1.00</td><td>0.04</td><td>-0.06</td><td>-0.05</td><td>-0.04</td><td>-0.05</td><td>-0.02</td><td>0.01</td></tr><tr><td>comment</td><td>0.08</td><td>0.00</td><td>-0.07</td><td>0.04</td><td>1.00</td><td>0.08</td><td>-0.03</td><td>0.01</td><td>-0.13</td><td>-0.13</td><td>-0.07</td></tr><tr><td>rateGap</td><td>0.07</td><td>-0.06</td><td>-0.10</td><td>-0.06</td><td>0.08</td><td>1.00</td><td>-0.13</td><td>0.19</td><td>0.04</td><td>-0.01</td><td>0.08</td></tr><tr><td>pos</td><td>0.00</td><td>0.00</td><td>0.02</td><td>-0.05</td><td>-0.03</td><td>-0.13</td><td>1.00</td><td>-0.13</td><td>-0.08</td><td>-0.07</td><td>0.00</td></tr><tr><td>neg</td><td>0.02</td><td>-0.01</td><td>-0.05</td><td>-0.04</td><td>0.01</td><td>0.19</td><td>-0.13</td><td>1.00</td><td>0.00</td><td>0.00</td><td>0.02</td></tr><tr><td>comNum</td><td>-0.06</td><td>0.02</td><td>0.07</td><td>-0.05</td><td>-0.13</td><td>0.04</td><td>-0.08</td><td>0.00</td><td>1.00</td><td>0.78</td><td>0.26</td></tr><tr><td>time</td><td>-0.01</td><td>0.00</td><td>0.01</td><td>-0.02</td><td>-0.13</td><td>-0.01</td><td>-0.07</td><td>0.00</td><td>0.78</td><td>1.00</td><td>0.17</td></tr><tr><td>rank</td><td>-0.05</td><td>0.02</td><td>-0.06</td><td>0.01</td><td>-0.07</td><td>0.08</td><td>0.00</td><td>0.02</td><td>0.26</td><td>0.17</td><td>1.00</td></tr></table></body></html>

表4回归分析结果  

<html><body><table><tr><td rowspan="2"></td><td colspan="2">模型1</td><td colspan="2">模型2</td><td colspan="2">模型3</td></tr><tr><td>系数</td><td>P值</td><td>系数</td><td>P值</td><td>系数</td><td>P值</td></tr><tr><td>(Intercept)</td><td>-1.598</td><td>0.000</td><td>-1.576</td><td>0.000</td><td>-2.081</td><td>0.000</td></tr><tr><td>reUse</td><td>5.836</td><td>0.000</td><td>4.841</td><td>0.000</td><td>4.651</td><td>0.000</td></tr><tr><td>reNum</td><td>-0.006</td><td>0.000</td><td>-0.005</td><td>0.000</td><td>-0.004</td><td>0.000</td></tr><tr><td>buyornot</td><td>-1.445</td><td>0.000</td><td>-1.334</td><td>0.000</td><td>-1.152</td><td>0.000</td></tr><tr><td>reInfo</td><td></td><td></td><td>0.451</td><td>0.000</td><td>0.630</td><td>0.000</td></tr><tr><td>comment</td><td></td><td></td><td>0.476</td><td>0.000</td><td>0.441</td><td>0.000</td></tr><tr><td>rateGap</td><td></td><td></td><td></td><td></td><td>0.324</td><td>0.000</td></tr><tr><td>pos</td><td></td><td></td><td></td><td></td><td>-2.136</td><td>0.001</td></tr><tr><td>neg</td><td></td><td></td><td></td><td></td><td>2.418</td><td>0.034</td></tr><tr><td>Log(theta)</td><td>-0.961</td><td>0.000</td><td>-0.721</td><td>0.000</td><td>-0.640</td><td>0.000</td></tr><tr><td>零膨胀模型</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(Intercept)</td><td>-30.124</td><td>0.000</td><td>-30.445</td><td>0.000</td><td>-30.500</td><td>0.000</td></tr><tr><td>rank</td><td>0.043</td><td>0.000</td><td>0.0435</td><td>0.000</td><td>0.044</td><td>0.000</td></tr><tr><td>Log(time)</td><td>4.230</td><td>0.000</td><td>4.272</td><td>0.000</td><td>4.277</td><td>0.000</td></tr><tr><td>LogLike</td><td>-12940</td><td></td><td>-12530</td><td></td><td>-12380</td><td></td></tr></table></body></html>

本文的膨胀因子系数均显著，说明添加的膨胀因子有效。这表明，评论发表时间和商品排名会影响评论是否被投票。

# (1）评论者信度

评论者有用性(reuse)的系数为正且P值显著$\scriptstyle ( \mathrm { P < } 0 . 0 0 1 )$ ，表明评论者有用性对评论有用性投票数有正向影响,H1a得到支持。评论者发表的评论数reNum的系数P值虽然显著，但是系数为负，表明评论者发表的评论数对评论有用性投票数有负向影响，与假设H1b相悖，因此假设H1b没有得到支持。评论者发表的评论数与评论有用性投票呈现负向关系，如表5所示，样本中约 $3 7 \%$ 的评论者是第一次评论，在其他变量相同的情况下，这些评论者的平均评分极性差 rateGap 值为1.13，大于其他评论者的 rateGap值0.93；前者平均评分(3.87)小于后者(4.24)。表明第一次发表评论的评论者的评论通常负面偏激，负面情绪促使用户参与第一次评论，而多次参与评论的评论者所发表的评论更为客观，评论更为温和；负面评论相对于正面评论能够获得更多有用性投票，因此评论有用性投票数与评论者发表的评论数呈现负面关系。若将评论者有用性看作评论者发表评论质量，H1a得到支持而H1b没有得到支持的结果表明，评论者历史发表的评论数越多，其当前所发表的评论获得有用性投票数不一定越高；而评论者历史发表的评论质量越高，则其当前所发表的评论获得有用性投票数将越高。

表5评论者发表评论数与有用性投票数关系  

<html><body><table><tr><td>已发表评论数</td><td>比率</td><td>平均有用性投票数</td><td>评分差值(评分)</td></tr><tr><td>>1</td><td>63%</td><td>1.64</td><td>0.93(4.24)</td></tr><tr><td>1</td><td>37%</td><td>1.80</td><td>1.13(3.87)</td></tr></table></body></html>

评论者是否确认购买(buyornot)系数为负且P值显著 $( \mathrm { P } { < } 0 . 0 0 1 )$ ，表明那些没有确认在亚马逊上购买商品的评论者的评论相对于确认在亚马逊上购买商品的评论者的评论能够获得更多投票，与假设H1c相悖，假设H1c没有得到支持。如表6所示，样本中约 $3 \%$ 的评论者属于没有确认在亚马逊上购买商品的评论者，另外 $9 7 \%$ 的评论者属于已经确认在亚马逊上购买商品的群体。前者的有用性投票数的均值为7.73，而后者的均值为1.51。这表明没有在亚马逊上确认购买商品的评论相比于确认购买的评论能够获得更多消费者的关注和认可。同时也表明，亚马逊的“是否确认购买"功能对于用户感知评论真实性方面没有影响。因为所选商品为亚马逊自营商品，不会出现商家操纵评论的现象即恶意差评与好评现象，保证了评论的真实性。因而亚马逊的"是否确认购买"这一功能仅能确认评论者的购买渠道是否是亚马逊。这些"没有确认在亚马逊购买"的评论者，极有可能是在线下门店等其他渠道购买商品后，再前往亚马逊撰写评论。而这样的行为需要更强的主动性，因此在撰写评论时会更认真。同时由表6可知，这一部分评论者的评论表现为负面偏激，因而根据负面偏差理论及下文有关评论极性与评论有用性投票数的关系可知，负面评论相对于正面评论更易获得有用性投票。

表6评论者是否确认购买与有用性投票数关系  

<html><body><table><tr><td>是否真实购买</td><td>比率</td><td>平均有用性投票数</td><td>评分差值(评分)</td></tr><tr><td>1</td><td>97%</td><td>1.51</td><td>1.00(4.16)</td></tr><tr><td>0</td><td>3%</td><td>7.73</td><td>1.46(3.33)</td></tr></table></body></html>

# (2）评论信息质量

评论信息量(reInfo)系数为正且 $\mathrm { ~ \bf ~ P ~ }$ 值显著 $( \mathrm { P } { < } 0 . 0 0 1 )$ ，表明评论信息量与评论有用性投票数成正比，评论信息量越多，评论有用性投票数将越高，假设H2a得到支持。根据本研究对评论信息含量的计算，那些与其他评论相似度越高的评论，其信息量越丰富，即这些评论是对该产品评论集中观点的概括。因而假设H2a成立的结果表明那些具有代表性的观点，其受到消费者的认可度越高，其获得的有用性投票数将越多。

评论回复数(comment)系数为正且P值显著，表明评论回复数对评论有用性投票具有正向影响，假设H2b得到支持。评论回复数越多，能够披露更多消费者所关心的问题，进而提高评论信息的诊断性。那么，该条评论获得有用性投票的可能性越高。评论回复数越多，表明该条评论的消费者关注度越高，因而获得的评论投票数越多。

# (3）评论极性

评分极性(rateGap)系数为正且P值显著，表明评分极性对评论投票有正向影响，假设H3a得到支持。当消费者所发表的评分偏离平均评分越多时，即消费者观点越极端时，该条评论就越能够吸引消费者进行有用性投票。

评论文本消极倾向(neg)对评论有用性投票数具有正向影响，假设H3b成立。评论文本积极情感倾向(pos)的P值显著且系数为负，假设H3c成立。这一结果表明，消极评论相对积极评论更容易获得有用性投票；积极词汇比例越高的评论，其投票数越少，表明积极描述并不能吸引用户投票。本文的研究结果也与负面偏差理论一致，即消极评论相对于积极评论对消费者的影响更大。电子商务卖家在对商品进行宣传的时候，会尽可能阐述商品的优点而不谈商品的缺点。事实上消费者在商品的详情页，已经对于商品的优点有所了解。因此消费者在阅读评论时更想知道：商家阐述的这些优点是否真实以及该商品还有何缺点。因而负面评论相对于正面评论能够为消费者提供更多有价值的信息。同时，有学者研究表明，大部分在线评论都是积极的[40-41]，那么消极评论在众多评论中能够吸引更多消费者的注意，从而可能获得更多投票。

假设验证结果如表7所示。

表7假设结果  

<html><body><table><tr><td>类别</td><td>假设</td><td>结果</td></tr><tr><td rowspan="2">评论者 信度</td><td>Hla：评论者有用性对评论有用投票数有显著 的正向影响。 H1b：评论者发表的评论数对评论有用性投票</td><td>支持</td></tr><tr><td>数有显著的正向影响 H1c：评论者的购买的真实性对评论有用性投</td><td>不支持</td></tr><tr><td>评论 信息 质量</td><td>票数有显著的正向影响。 H2a：评论信息量对评论有用性投票数有显著 的正向影响。 H2b：评论回复数对评论有用性投票数有显著</td><td>支持 支持</td></tr><tr><td rowspan="2">评论 极性</td><td>的正向影响。 H3a：评分极性对评论有用性投票数有显著的 正向影响。</td><td>支持</td></tr><tr><td>H3b：评论文本消极情感倾向对评论有用性投 票数有正向影响。 H3c：评论文本积极情感倾向对评论有用性投</td><td>支持</td></tr></table></body></html>

# 5结论与展望

# 5.1 研究结论与启示

本文探究了一个以往在线评论研究中较少涉及的问题：什么样的评论更容易获得有用性投票。只有当评论获得投票后，评论投票系统才能有效运作。因此，研究这个问题是必要的。以信息采纳理论和负面偏差理论为基础，将有可能会影响评论有用性投票数的因素分成评论者信度、评论信息质量、评论极性三个大类。从这三个角度探讨了什么样的评论更容易获得有用性投票，并以亚马逊网站中的12393条手机评论为研究对象，利用零膨胀负二项回归模型进行分析。

研究结果显示，在评论者信度信息方面，历史发表评论质量越高的用户，越容易获得有用性投票；同时，第一次发表评论的评论者及未通过亚马逊渠道购买商品的评论者，其评论通常负面偏激，容易引起其他用户共鸣，更容易获得更多有用性投票。在评论信息质量方面，回复数较多的评论更能够吸引消费者进行有用性投票；评论中包含的信息量越高，对消费者而言越有用。在评论极性方面，评分越极端的评论，越有可能获得有用性投票；负面评论相对于正面评论更能够吸引消费者进行有用性投票。

基于这些研究结论，对于电子商务评论系统的管理者提出如下建议：

(1）改善评论排序机制。本文的研究结果表明评论者有用性及评论回复数这些指标对影响消费者感知评论有用性具有正向影响。因此，除了传统的以时间、有用性、综合排序外，在线评论系统的评论排序逻辑可以将评论者有用性、评论回复数等因素也纳入其中。

(2）重视负面评论。本研究结论表明消费者容易受负面评论影响。因此亚马逊的商家需要对负面评论进行积极回应，消除其他消费者对商品和服务质量的疑惑。

(3）重视网站首次评论及从其他渠道购买商品的评论者。这部分用户的评论内容通常负面偏激，容易引起其他用户的关注。

# 5.2 研究价值、局限及展望

本文主要贡献如下:

(1）关于评论有用性研究的有益补充。评论的有用性投票有助于其他消费者快速找出有助于决策的评论。前人大多是对评论有用性进行研究，最终达到对没有投票的评论做出有用性预测，从而帮助消费者做出更加明智的购物决策。本研究试图从另外一个角度为消费者的购物决策做出贡献，探究评论有用性投票数的影响因素有哪些。这一研究视角对于帮助消费者快速获得有质量的信息非常有意义，可以帮助人们进一步了解哪些因素影响评论获得有用性投票

(2）利用零膨胀负二项模型对评论有用性投票进行研究，不仅纳入了有投票的评论还纳入了没有投票的评论。采用此种方法避免了因样本选择带来的结果偏差，因而结果更为准确，对后续研究具有借鉴意义。

本研究还存在一些局限：

(1）评论有用性投票影响因素的研究样本选取的是搜索品，而未对体验型产品这一类型进行探究。在今后的研究中，将进一步以体验型产品为样本进行研究并对比结论的差异。

(2）在评论回复数的处理上，仅从数量上分析了评论回复量与评论有用性投票数之间的关系，而未深入分析回复内容及回复对象对消费者感知评论有用性的影响，这也是今后研究的重点方向。

# 参考文献：

[1]Hu N,Bose I,Koh N S,et al.Manipulation of Online Reviews:An Analysis ofRatings,Readability,and Sentiments [J].Decision Support Systems,2012,52(3): 674-684.   
[2] Kim S M,Pantel P,Chklovski T,et al．Automatically Assessing Review Helpfulness[C]//Proceedings of the 2006 Conference on Empirical Methods in Natural Language Processing,Sydney,Australia.2006: 423-430.   
[3]Liu Y, Huang X,An A,et al. Modeling and Predicting the Helpfulness of Online Reviews[C]//Proceedings of the 8th IEEE International Conference on Data Mining. IEEE Computer Society,2008,15:443-452.   
[4]Mudambi S M,Schuff D.What Makes a Helpful Online Review? A Study of Customer Reviews on Amazon.com [J]. MIS Quarterly,2010,34(1): 185-200.   
[5]Ghose A, Ipeirotis P G. Estimating the Helpfulness and Economic Impact of Product Reviews: Mining Text and ReviewerCharacteristics[J].IEEETransactionson Knowledge & Data Engineering,2011,23(10): 1498-1512.   
[6]Baek H,Ahn J,Choi Y. Helpfulness of Online Consumer Reviews: Readers’ Objectivesand Review Cues[J]. International Journal of Electronic Commerce,2012,17(2): 99-126.   
[7]KorfiatisN，Garcia-Bariocanal E, Sanchez-AlonsoS. Evaluating Content Quality and Helpfulness of Online Product Reviews: The Interplay of Review Helpfulness vs. Review Content [J].Electronic Commerce Research & Applications,2012,11(3): 205-217.   
[8]Yin D, Bond S D, Zhang H. Anxious or Angry? Effects of Discrete Emotions on the Perceived Helpfulness of Online Reviews [J]. MIS Quarterly,2014,38(2): 539-560.   
[9]Greene WH.Econometric Analysis [M].北京：清华大学出 版社，2001:182-197.(Greene W H.Econometric Analysis [M].Beijing: Tsinghua University Press,2001: 182-197.)   
[10] Sussman S W,Siegal W S. Informational Influence in Organizations: An Integrated Approach to Knowledge Adoption [J]. Information Systems Research,2003,14(1): 47-65.   
[11]殷国鹏，刘雯雯，祝珊．网络社区在线评论有用性影响模 型研究——基于信息采纳与社会网络视角[J].图书情报

工作,2012,56(16):140-147.(Yin Guopeng,Liu Wenwen, Zhu Shan.What Makes a Helpful Online Review?——The Perspective of Information Adoption and Social Network[J]. Library& Information Service,2012,56(16):140-147.)

[12]黄卫来，潘晓波.在线商品评价信息有用性模型研究-

纳入应用背景因素的信息采纳扩展模型[J].图书情报工 作,2014, 58(S1):141-151.(Huang Weilai,Pan Xiaobo.The Research of the Information Usefulness of Online Product Reviews— -The Extented Information Adoption Model with Background Factor[J].Library & Information Service,2014, 58(S1): 141-151.)   
[13]王军，周淑玲．一致性与矛盾性在线评论对消费者信息采 纳的影响研究——基于感知有用性的中介作用和自我效能 的调节作用[J]．图书情报工作,2016,60(22):94-101.(Wang Jun,Zhou Shuling.Research on How the Consistent and Contradictory Online Reviews Affect Consumer Information Adoption- -Based on the Mediating Effects of Perceived Usefulness and the Moderating Effects of Self-efficacy [J]. Library & Information Service,2016,60(22): 94-101.)   
[14]宋雪雁，王萍．信息采纳行为概念及影响因素研究[J].情 报科学，2010,28(5):760-762，767.(Song Xueyan，Wang Ping. Research on Concept and Efective Factors of Information Adoption Behavior [J]. Information Science, 2010,28(5): 760-762, 767.)   
[15] Taylor R S. Value-added Processes in Information Systems [M]. Norwood, NJ: Ablex,1986.   
[16]Hilligoss B,Rieh S Y.Developing a Unifying Framework of Credibility Assessment: Construct, Heuristics,and Interaction in Context [J]. Information Processing and Management, 2008,44(4): 1467-1484.   
[17]Gorla N,Somers T M,Wong B.Organizational Impact of System Quality, Information Quality,and Service Quality[J]. The Journal of Strategic Information Systems,2010,19(3): 207-228.   
[18] Filieri R，Mcleay F. E-WOM and Accommodation: An Analysis of the Factors that Influence Travelers'Adoption of Information from Online Reviews[J]. Journal of Travel Research,2014,53(1): 44-57.   
[19]Kanouse D,Hansonn L. Negativity in Evaluations [M]. General Learning Press,1972.   
[20] Baumeister R F,Bratslavsky E,Finkenauer C,et al. Bad is Stronger than Good [J]. Review of General Psychology, 2001, 95(3): 477-509.   
[21]Rozin P,Royzman E B. Negativity Bias， Negativity Dominance,and Contagion [J].Personality & Social Psychology Review,2001, 5(4): 296-320.   
[22] Zhu L，Yin G,He W. Is This Opinion Leader's Review Useful? Peripheral Cues for Online Review Helpfulness [J]. Journal of Electronic Commerce Research，2014，15(4): 267-280.   
[23]Levi A,Mokryn O. The Social Aspect of Voting for Useful Reviews [C]/Proceedings of the International Conference on Social Computing， Behavioral-Cultural Modeling,and Prediction.Springer International Publishing,2014:293-300.   
[24] Kuan K K Y,Hui KL,Prasarnphanich P,et al. What Makes a Review Voted? An Empirical Investigation of Review Voting in Online Review Systems [J]. Journal of the Association for Information Systems,2015,16(1): 48-71.   
[25] Lee S,Choeh J Y.Predicting the Helpfulness of Online Reviews Using Multilayer Perceptron Neural Networks [J]. Expert Systems with Applications,2014,41(6): 3041-3046.   
[26] Holmqvist K,Holsanova J,Barthelson M,et al.Chapter 30-Reading or Scanning? A Study of Newspaper and Net Paper Reading [A]// Hyonä J,Radach R,Deubel H.The Mind's Eye: Cognitive and Applied Aspects of Eye Movement Research[M].2003: 657-670.   
[27] Schindler R M,Bickart B.Perceived Helpfulness of Online Consumer Reviews: The Role of Message Content and Style [J]. Journal of Consumer Behaviour, 2012,11(3): 234-343.   
[28] Cao Q,Duan W, Gan Q. Exploring Determinants of Voting for the “Helpfulness”of Online User Reviews: A Text Mining Approach [J]. Decision Support Systems，2011，50(2): 511-521.   
[29] Forman C，Ghose A，Wiesenfeld B. Examining the Relationship Between Reviews and Sales: The Role of Reviewer Identity Disclosure in Electronic Markets [J]. Information Systems Research,2008,19(3): 291-313.   
[30] Zhang JQ,Craciun G,Shin D.When does Electronic Word-of-mouth Matter? A Study of Consumer Product Reviews [J]. Journal of Business Research, 2010,63(12): 1336-1341.   
[31] Cui G, Lui H K,Guo X.The Efect of Online Consumer Reviews on New Product Sales [J]. International Journal of Electronic Commerce,2014,17(1): 39-58.   
[32] Siering M,Muntermann J.What Drives the Helpfulness of Online Product Reviews?From Stars to Facts and Emotions [C]// Proceedings of the 1lth International Conference on Wirtschaftsinformatik.2013:103-118.   
[33] Erkan G, Radev D R. LexRank:Graph-based Lexical Centrality as Salience in Text Summarization [J]. Journal of Artificial Intelligence Research,2004,22(1): 457-479.   
[34] 纪文倩,李舟军，巢文涵，等．一种基于LexRank算法的改 进的自动文摘系统[J]．计算机科学,2010,37(5):151-154. (Ji Wenqian,Li Zhoujun,Chao Wenhan,et al. Automatic Abstracting System Based on Improved LexRank Algorithm [J].Computer Science,2010,37(5): 151-154.)   
[35] Salton G, Buckley C. Term-weighting Approachesin Automatic Text Retrieval [J]. Information Processing& Management,1988,24(5): 513-523.   
[36]ZhangHP,Yu HK,Xiong DY,et al.HHMM-based Chinese Lexical Analyzer ICTCLAS[C]//Proceedings of the 2nd SIGHAN Workshop on Chinese Language Processing. Association for Computational Linguistics,20o3:184-187.   
[37]台湾大学．台湾大学 NTUSD 中文情感词典 [DS/OL]. [2016-03-24].http://www.datatang.com/data/44317.(Taiwan Univeristy.NTUSD:The Chinese Emotion Word Library [DS/OL].[2016-03-24].http://www.datatang.com/data/44317.)   
[38]Dean C,Lawless JF.Tests for Detecting Overdispersion in Poisson Regression Models[J].Journal of the American Statistical Association, 1989,84(406): 467-472.   
[39]Greene W H.Accounting for Excess Zeros and Sample Selection in Poisson and Negative Binomial Regression Models [OL]. New York University Working Paper No. EC-94-10.https://ssrn.com/abstract=1293115.   
[40]ChevalierJA,Mayzlin D.The Effect of Word of Mouth on Sales: Online Book Reviews [J].Journal of Marketing Research,2006,43(3):345-354.   
[41]Hu N,Zhang J,Pavlou P A.Overcoming the J-Shaped Distribution of Product Reviews [J].Communications of the ACM,2009,52(10):144-147.

# 作者贡献声明：

吴江：提出研究思路，设计研究方案，论文最终版本修订;  
刘弯弯：采集、清洗和分析数据，起草论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: jiangw@whu.edu.cn。  
[1]刘弯弯.regression.xls.回归分析所用数据.  
[2]刘弯弯.emotion.xls.计算评论情感得分所用文本及结果数据.  
[3]台湾大学.NTUSD.xls.情感词典.  
[4]刘弯弯.reviewInfo.xls.评论文本及评论信息量计算结果.  
[5]刘弯弯.review.xsl.基础数据.  
[6]刘弯弯.method.txt.研究方法详细描述.  
[7]刘弯弯.emotionAnalysis.R.情感计算程序.  
[8]刘弯弯.lexRank.R.评论信息量计算程序.

收稿日期:2017-05-23   
收修改稿日期:2017-07-05

# Identifying Reviews with More Positive Votes Case Study of Amazon.cn

Wu Jiang Liu Wanwan (School of Information Management, Wuhan University, Wuhan 430072, China) (The Center of E-commerce Research and Development of Wuhan University, Wuhan 430072, China)

Abstract: [Objective] This article examines online reviews atracting more positive votes from consumers,aiming to identify those high quality reviews based onthe information adoption and negative bias theories.[Methods]First, we retrieved12393 reviews on celphones from Amazon.cn.Then，we investigated the impactsof the review's characteristics on the numbers of positive votes with the helpof zero inflated negative binomial regresion and text analysis methods.The characteristics we studied include reviewer'scredibility,review's qualityand extremity.[Results] The usefulness ofthe reviewer's previous posting,the information qualityof the reviews,the number of comments,the extreme ratings,and the negative level of the reviews helped them receive more positive votes.However,the reviewers bought the products or not,and the number of the previously posted reviews had negative influence on the number of Votes.[Limitations]Only investigated cellphones in this study.[Conclusions]This paper helps E-commerce websites improve their review ranking algorithms.

Keywords: Online ReviewOnline Review HelpfulnessReview Vote

# RedLink与ORCID合作，将ORCID集成在最新版Remarq中

近日,RedLink 和ORCID 达成一项合作，计划将 ORCID 集成在最新版的 Remarq中，当用户使用其 ORCID 登录 Remarq时，将在Remarq 中提供无缝的ORCID 作者信息导人。

Remarq 是一个协作工具，提供注释、评论、作者更新、编辑更新、专业联系和文章共享等功能，所有这些都在发布商的网站上进行操作，利用记录的不同版本。Remarq 提供了强大的平稳集成的系列工具，为作者、编辑和用户提供支持，通过支持他们参与记录的不同版本来实现。

ORCID 为参与研究、学术活动和创新活动的个人提供名称标识符。这些标识符使得研究人员、研究人员的学术产出，以及研究人员所属机构之间的关系变得透明和可靠。2017年9月14日,RedLink 首席执行官 Kent Anderson作为发言人参与了ORCID同行评议网络研讨会。

Anderson 评论道：“我们很高兴支持ORCID 成为会员，同时也为ORCID 标识符提供了一个创新而有趣的实用案例。通过ORCID，研究人员将能够快速创建 Remarq的简介，其中包括他们的职业生涯亮点、出版历史以及其他重要的信息。”

除了与ORCID 的集成外，Remarq 的最新升级还包括跟踪文章、作者通知等。未来团队还将进一步增强 Remarq 丰富的合作环境。

(编译自:https://redlink.com/redlink-announces-integration-with-orcid-in-latest-release-of-remarq/)

(本刊讯)