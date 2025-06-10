# 基于大规模古文语料库的词典构建及分词技术研究

邢付贵1.2 朱廷劭2\*

1（中国科学院大学 北京 10049)

2 （中国科学院心理研究所，北京100101）

摘要：古文献的研究有助于传统文化的继承与发扬，而古文分词则是利用自然语言处理技术对古文献进行分析的重要环节，但由于缺少规范的数据资料而没有像现代汉语分词取得突破性进展。当前互联网拥有大量古汉语文本和词典方面的数据资料，但是这些数据分散，没有得到有效地整合。本文提出采集互联网非结构化古汉语数据，经过数据清洗和预处理抽取出一个古汉语基础词典，然后再利用互信息、信息熵、位置成词概率相结合的新词发现方法从大规模古籍文本中抽取古汉语候补词典，最终将基础词典与候补词典融合，利用正向最大匹配实现对古文的分词。与开源的分词器甲言在基于词典的分词方面比较后F值提高了 $1 4 \%$ ，取得了良好的效果，结果证明本文构建的分词器可以应用在古汉语文本分词上。

关键词：古汉语分词；大数据；语料库；Apache Spark

分类号：B849

# Segmentation Dictionary construction and research of word segmentation based on large-scale ancient Chinese Corpus

Fugui Xing1,2 Tingshao Zhu2\*

1（University of Chinese Academy of Sciences, Beijing 10049) (Institute of Psychology， Chinese Academy of Sciences Beijing 100101)

Abstract: The corpus The study of ancient documents is helpful for the inheritance and development of traditional culture,and ancient Chinese word segmentation is an important part of the analysis of ancient documents by using natural language processng technology, but due to the lack of standard data, it has not made a breakthrough like modern Chinese word segmentation. At present, there are a large number of ancient Chinese text and dictionary data on the Internet, but these data are scattered and not effectively integrated. This paper proposes to collect unstructured ancient Chinese data on the Internet and extract a basic dictionary of ancient Chinese through Big Data processing, then extract the candidate Dictionary of ancient Chinese from large-scale ancient Chinese texts by using the new word discovery method combining mutual information, information entropy and position word probability. Finally, we integrated the basic dictionary and the addition dictionary and used the forward maximum matching to tokenize ancient Chinese text. Compared with the open-source ancient Chinese tokenizer "Jiayan", the F value which segment based on the dictionary was improved by $14 \%$ and good results were achieved. The result showed that this tokenizer constructed in this paper can be applied to ancient Chinese text word segmentation.

Key words: ancient Chinese word segmentation; Big Data; corpus; Apache Spark

# 1引言

中国古代文献是一个宝藏，从古汉语文本中挖掘有价值的信息在考古中有很重要的意义[1]。通过对古文献的分析研究，有助于进一步弘扬传统文化，而古文分词则是利用自然语言处理技术对古文献进行分析的重要环节。由于古文和现代汉语无论是在词汇还是在语法上都有很大的不同，探索古文的有效分词是亟待解决的问题。

相关学者在古文分词方面做了大量研究。严顺［2」提出了基于条件随机场(CRF)的古汉语分词模型；王晓玉等［3」将CRFs模型和词典相结合用于古汉语的分词；钱智勇等［4」使用隐马尔科夫模型对《楚辞》进行了自动分词标注的研究实验，取得了较好的效果；李筱瑜等［5」将互信息，信息熵相结合进行新词发现，并与词典信息结合用于古籍文本分词研究，但是准确度并不高。

本文利用大规模网络古文语料库，通过对海量古文资料的分析[6]，构建古文词典。首先，通过爬虫从互联网采集古汉语相关的数据集，经过数据清洗和转换得到一个古汉语基础词典，这个基础词典是由互联网的非结构化数据转换所得，囊括了大部分古汉语字词，但是并不能保证古汉语词汇的全面性，所以本文进一步采用互信息、信息熵[8]和位置成词概率[7]相结合的新词发现方法，从大规模古籍文本中抽取古汉语词汇并得到候补词典，以此来弥补基础词典的不足。在融合得到的新词典的基础上，本文利用正向最大匹配实现对古文的分词，并与开源古汉语分词器甲言[9]进行分词性能比较。

# 2研究方法

# 2.1基础词典的构建

在互联网发达的今天，互联网上有很多古汉语相关的数据，例如收录词典的网站，汉文学网［25]，词典网[26]，汉典［27]，在线汉语字典［28]，国学大师［29]等，Github上也有很多开放的古汉语数据集，百科上也有古汉语相关的文本资料。

本文统一将数据抽取到 Hadoop,存储在hdfs上。Hive 用于数据的统计，在分布式数据索引方面选择 Apache Elasticsearch[11]用于筛选古汉语数据集，Spark 用于数据处理。

总体流程如图1所示。

![](images/37c07d017aeb9628a0c3b562271d72371365dbb54272e1c27f5afcca1d0469ec.jpg)  
图1古文词典构建的处理流程

本文通过调查并选取了与古汉语词汇相关的网站，通过分析它们的robots 协议和许可限制，最终确定可以用于爬虫采集数据的网站。经过数据的采集，转换，抽取了22203 个字，364761个词语。但是这些字和词语并不完全是古汉语，还包括一些现代字和词。这就需要对数据进行进一步处理，将现代字和词过滤掉。但是人工对这些字词进行筛选的工作量是巨大的，并且存在人为的误差，本文通过搜索古文语料库实现对古汉语字词的筛选。为了判断某一个字或者某一个词是否为古汉语字词，在古汉语语料库中进行查找，如果在语料库中存在，就被认定为古汉语字或者古汉语词语，否则不是。

Github 上有很多开源的古汉语语料库，其中，汉语古典文本资料库[12]有13000 种文本，10 万卷，近13亿字，大小为3.14GB，基本上涵盖了所有朝代的古籍文献，本文选定这个数据集作为筛选古汉语字词的依据。为了达到良好的搜索性能，首先在 ApacheElasticsearch7.4.2中将3.14 GB 的古汉语语料库建立索引，然后通过 Elasticsearch提供的检索 API 对词典中的字和词进行筛选。如果某个字或者词语能在 Elasticsearch 索引库中检索到，就将这个词标记为文言词汇，最终形成一个只有古汉语字词的候选词表。

对于Elasticsearch 中索引和检索所用的分词组件，本文使用了IK 分析插件[31]，将上文得到的字和词转换成字典文件，并替换IK 中原有的字典文件，analyzer 配置为 IK 的优点是能够精确地按照中文词典分词，Mapping 设置如下，

<html><body><table><tr><td>{</td></tr><tr><td>"properties":{</td></tr><tr><td>"content":{</td></tr><tr><td>"type": "text",</td></tr><tr><td>"analyzer": "ik_smart",</td></tr><tr><td>'search_analyzer": "ik_smart"</td></tr><tr><td>}</td></tr><tr><td>了</td></tr><tr><td>}</td></tr></table></body></html>

Elasticsearch 有三种搜索方式，term，match 和 match_phrase，其中 match 和match_phrase都会对搜索关键词进行拆分，然后对子关键词再进行检索，这样就无法满足本实验的要求，而 term 搜索方式能够做到整词匹配，虽然 term 搜素方式会将字典中不存在的词语进行单字拆分，但是这不影响本实验的结果，因为本实验针对的是字典中的词进行检测，没有字典之外的词语。接下来经过去重处理和繁体字转换，得到了一个包含331516 个字词的词典，本文称之为基础词典，其中词语有 66712个。由于字对分词的准确度的影响并不高，所以本文重点统计了基础词典中的两个字以上的词语的一些分布特征，横坐标代表词语在3.14GB 语料中出现的次数，纵坐标代表这个频率的词有多少个，如图2所示。

![](images/45af5d86d428d0429fe10fa119ff1da5473e72f2874a76d3b11e8bac6c943221.jpg)  
图2基础词典不同词频的词分布

由上图可以看出，频率在10左右的词汇占了大约4万个，词频在10以上的词汇的数量比较少。

# 2.2 新词发现

新词发现是自然语言处理的重要的一项技术，用于抽取字典中没有的新词[13」。在获取古文基础词典后，仍然难以确保基础词典收录了全面的古汉语字词。为了弥补基础词典的不足，在这一步骤中，本文提出了多特征融合的方法实现新词发现，综合采用N-Gram 词频、互信息、信息熵、位置成词概率相结合的方式在大规模语料库中抽取新词，语料库采用上文提到的开源的3.14GB 的汉语古典文本资料库。在既往演剧中也有采用新词发现的方式抽取古汉语词汇［5]，但是这些方法均在少量的语料库上进行实验，效果并不理想，而在本实验中采用大规模语料，并使用分布式计算平台 Apache Spark 进行新词发现。

N-Gram 是一个统计语言模型[14]，它的假设是，第N个词的出现只与前面 N-1个词相关，而与其它的词都不相关。本文首先对古汉语文本进行切分，切分后的每个单元被认为是一个 gram,进而统计出每个 gram 的频率。根据设定的阈值，过滤掉不符合词长要求的词语。使用N-Gram 的优点是语言无关性，不需要对古汉语文本进行语言学处理。

互信息和信息熵都是信息论中的概念[15]，互信息可以计算两个对象的关联程度，如果X和Y互相独立，那么X和Y之间互相不提供任何信息，他们的互信息就为0。N-Gram获取高频率的文本片段，但是一个文本片段出现的频率高并不能代表这个文本片段是一个真正的词语，它可能是多个词语结合在一起的词组。本文采用互信息度量不同文本片段的凝固程度。互信息的计算公式如下，

$$
M I ( w _ { 1 } \cdots w _ { n } ) = \log _ { 2 } \frac { p ( w _ { 1 } \cdots w _ { n } ) } { a v g ( w _ { 1 } \cdots w _ { n } ) }
$$

$$
p ( w _ { 1 } \cdots w _ { n } ) = { \frac { f ( w _ { 1 } \cdots w _ { n } ) } { n u m } }
$$

$$
\operatorname { a v g } ( w _ { 1 } \cdots w _ { n } ) = { \frac { 1 } { n - 1 } } \sum _ { i = 1 } ^ { n - 1 } \quad p ( w _ { 1 } \cdots w _ { i } ) p ( w _ { i } \cdots w _ { n } )
$$

其中， $w _ { 1 } \cdots w _ { n }$ 代表由多个字构成的词语， $p ( w _ { 1 } \cdots w _ { n } )$ 代表词语 $w _ { 1 } \cdots w _ { n }$ 在语料库中出现的概率， $f ( w _ { 1 } \cdots w _ { n } )$ 代表词语 $w _ { 1 } \cdots w _ { n }$ 在语料中出现次数，num 表示语料库的字数，avg(wlwn）表示词语中的字不同组合的平均概率。

信息熵也被称为自由度，用于判断古汉语文本左右相邻字符的相互关系的稳定性，熵越大，稳定性越小，越有可能称为独立的词。信息熵分为左信息熵和右信息熵。左信息熵代表一个文本片段与左边的字符相结合的稳定程度，右信息熵代表一个文本片段与右边的字符相结合的稳定程度，计算公式如下，

$$
H _ { l e f t } ( W ) = - \sum _ { w _ { l e f t } c _ { l e f t } } \quad p \big ( w _ { l e f t } \big | w \big ) \log _ { 2 } p \big ( w _ { l e f l } \big | w \big )
$$

其中， ${ \cal H } _ { l e f t } ( W )$ 是候选词语w左信息熵， $c _ { l e f t }$ 是候选词 $W$ 左边相邻的字符集合， $p \big ( w _ { l e f t } | w \big )$ 是出现候选词w时，其左边相邻字符 $w _ { l e f t }$ 的条件概率。 $p ( w _ { \mathrm { l e f t } } | w )$ 的计算公式见式（5)，

$$
p ( w _ { \mathrm { l e f t } } | w ) = \frac { N ( w _ { \mathrm { l e f t } } ) } { N ( w ) }
$$

其中， $N ( w _ { \mathrm { l e f t } } )$ 是左边相邻字符 $w _ { \mathrm { l e f t } }$ 及候选词 $w$ 共同出现的概率， $N ( w )$ 是候选词 $w$ 单独出现的概率，同理，右信息熵可判断词语右边界，候选词右信息熵计算方法如公式（6）所示，

$$
H _ { r i g \dot { s } t } ( W ) = - \sum _ { w _ { r i g h t } c _ { r i g h t } } \quad p \big ( w _ { r i g h t } \big | w \big ) \log _ { 2 } p \big ( w _ { r i g h t } \big | w \big )
$$

其中， $H _ { r i g \it / t } ( W )$ 是候选词语 $W$ 右信息熵， $c _ { r i g h t }$ 是候选词 $\boldsymbol { \mathit { \Delta } } _ { W }$ 右边相邻的字符集合，$p \big ( w _ { r i g h t } \big | w \big )$ 是出现候选词 $w$ 时，其右边相邻字符 $w _ { r i g h t }$ 的条件概率。 $p \big ( w _ { \mathrm { r i g h t } } \big | w \big )$ 的计算公式见式（7），

$$
p \big ( w _ { \mathrm { r i g h t } } \big | w \big ) = \frac { N \big ( w _ { \mathrm { r i g h t } } \big ) } { N ( w ) }
$$

其中， $N \big ( w _ { \mathrm { r i g h t } } \big )$ 是右边相邻字符 $w _ { \mathrm { r i g h t } }$ 及候选词w共同出现的概率， $N ( w )$ 是候选词 $w$ 单独出现的概率。

由于新词发现需要将在整个语料库加载到内存上进行计算，只有在整个语料库上重复出现过的字符串才可能是候选词，因此语料库越大，所需要的内存也越多，时间复杂度也越大。本文基于 Spark 实现了并行处理[16]，在效率上有了很大提升，算法基本流程如表1所示，

# 算法基本流程

输入：原始语料 $\overline { { \mathrm { D } = \{ \mathrm { ~ S ~ 1 ~ } , \mathrm { ~ S ~ 2 ~ } , \mathrm { ~ } \cdots , \mathrm { ~ S ~ n ~ } \} } }$   
输出：候选词的集合  
$\textcircled{1}$ 将原始语料文件以RDD变量的形式读入内存，假设该RDD变量为corpus_rdd。$\textcircled{2}$ 对corpus_rdd的每一行，把出现的每一个字符存到数组中，并将每个字符映射到频率（也就是1）。最后用Reduce操作把相同字符的频率相加，得到每个元素是（字符，频率）的RDD量nGram_RDD。  
$\textcircled{3}$ 对RDD变量nGram_RDD做filter操作，将频率大于阈值的词保留，得到新的RDD变量nGram_filter_RDD。  
$\textcircled{4}$ 使用map操作对RDD变量nGram_filter_RDD中的每个词计算信息熵。  
$\textcircled{5}$ 使用map操作计算好词频和信息熵的RDD，建立Trie树。  
$\textcircled{6}$ 使用broadcast操作将建好的Trie树广播到其他节点，减少计算中的通信开销。$\textcircled{7}$ 使用map操作计算互信息，并过滤掉低于互信息和信息熵阈值的词语，返回最终的字典集合。

Trie 树是一个树形的结构，也是哈希树的变种[23]。Trie 树利用前缀来缩短检索时间，能够最大限度地减少字符串的比较，尤其在动态地增加或者修改数据的场景下性能表现更好。本文通过 Spark RDD 实现了分布式的Trie 树，在效率上有了提升[17]。

RDD 是弹性分布式数据集[18]，是 Spark 实现分布式处理的基石，RDD 能将数据分布在多台机器上，提高了计算性能。本文采用的 Spark 集群采用1个 master 主控节点，3 个slave从节点组成，节点配置如表2所示，

表2节点配置  

<html><body><table><tr><td>项目名词</td><td>说明</td></tr><tr><td>CPU</td><td>8 Core，Interl Xeon</td></tr><tr><td>Memory</td><td>64GB</td></tr><tr><td>Disk</td><td>1TB</td></tr><tr><td>0S</td><td>Ubuntu 18.04.3 LTS</td></tr><tr><td>Java Version</td><td>JDK 1.8</td></tr><tr><td>Hadoop Version</td><td>3.2.0</td></tr><tr><td>Spark Version</td><td>2.4.4</td></tr></table></body></html>

在算法中涉及了算法的超参数配置，本文选取的参数阈值如表3所示，通过运算，以表4所示的样式输出，

表3参数配置  

<html><body><table><tr><td>参数</td><td>参数值</td></tr><tr><td>最小词频</td><td>10</td></tr><tr><td>最大词长</td><td>2</td></tr><tr><td>最小词长</td><td>8</td></tr><tr><td>互信息阈值</td><td>0.2</td></tr><tr><td>信息熵阈值</td><td>0.2</td></tr></table></body></html>

表4算法输出结果  

<html><body><table><tr><td>信息熵</td><td>互信息</td><td>词频</td><td>词语</td></tr><tr><td>5.125501</td><td>200.1129</td><td>61</td><td></td></tr><tr><td>4.775116</td><td>97.83365</td><td>104</td><td>涅槃</td></tr><tr><td>4.569175</td><td>167.3033</td><td>63</td><td>徘徊</td></tr><tr><td>3.947703</td><td>653</td><td>18</td><td>邂逅</td></tr><tr><td>4.36353</td><td>240.5139</td><td>41</td><td>邯郸</td></tr><tr><td>3.459432</td><td>1127.909</td><td>11</td><td></td></tr><tr><td>3.563074</td><td>477.1923</td><td>25</td><td>琵琶</td></tr><tr><td>3.721612</td><td>589.3325</td><td>19</td><td>窀穸</td></tr><tr><td>3.25</td><td>775.4375</td><td>16</td><td>袈裟</td></tr><tr><td>4.682079</td><td>194.9931</td><td>43</td><td>匍匐</td></tr><tr><td>3.560935</td><td>275.7111</td><td>38</td><td>鹪鸪</td></tr><tr><td>4.026244</td><td>180.8911</td><td>51</td><td>糟粕</td></tr><tr><td>3.640224</td><td>653</td><td>15</td><td>鹦鹉</td></tr><tr><td>2.867634</td><td>563.9545</td><td>22</td><td>婕妤</td></tr><tr><td>3.418296</td><td>827.1333</td><td>12</td><td>澳涩</td></tr><tr><td>3.558519</td><td>438.6313</td><td>21</td><td>玲珑</td></tr><tr><td>3.741446</td><td></td><td></td><td>鸳鸯</td></tr><tr><td>3.471354</td><td>437.6367 496.28</td><td>20 19</td><td>整屋</td></tr><tr><td>3.886842</td><td>347.049</td><td>24</td><td>图圖</td></tr></table></body></html>

至此，通过词频统计并搭配互信息，信息熵得到的词典已经涵盖了足够多的候补词语，但是仍然存在一些非古汉语词语，这些词语有些是完整词语的部分片段，例如，“氏家世”并不是一个完整的词语，一般用法为“刘氏家世”，“家世”，为了进一步提高成词的准确度，本文通过位置成词概率[7」对上一步得到的词典进行过滤。在古汉语中，每个字或者词语都有自己的构词规律，某个字会出现在合成词的固定的位置，例如“才”一般出现在某个词的结尾，“秀才”“王进才”，所以在结尾这个位置的概率比较高。位置成词概率公式为，

$$
\mathrm { P W P } ( w , \mathrm { \ p o s \ } ) = \frac { N ( w , \mathrm { \ p o s \ } ) } { N ( w ) }
$$

其中，pos表示古汉字w在该词中出现的位置，位置包括词首，词中，词尾，N(w，pos）表示w 出现在词语中的位置 pos 的所有词语的频次；N(w，pos )则表示w 在基础词典的词语中出现的总次数，根据这个公式，本文基于上文得到的基础词典计算出位置成词概率表，如表5所示，

表5位置成词概率表  

<html><body><table><tr><td>古汉字</td><td>词首概率</td><td>词中概率</td><td>词尾概率</td></tr><tr><td>耀</td><td>0.234848</td><td>0.037879</td><td>0.727273</td></tr><tr><td>老</td><td>0.547358</td><td>0.188435</td><td>0.264207</td></tr><tr><td>考</td><td>0.494881</td><td>0.051195</td><td>0.453925</td></tr><tr><td>耄</td><td>0.526316</td><td>0</td><td>0.473684</td></tr><tr><td>者</td><td>0.052805</td><td>0.29703</td><td>0.650165</td></tr><tr><td>耆</td><td>0.694118</td><td>0.070588</td><td>0.235294</td></tr><tr><td>者</td><td>0</td><td>0</td><td>1</td></tr><tr><td>者</td><td>0</td><td>0</td><td>1</td></tr><tr><td></td><td>0.411765</td><td>0</td><td>0.588235</td></tr><tr><td>而</td><td>0.031208</td><td>0.913161</td><td>0.055631</td></tr><tr><td>耍</td><td>0.642857</td><td>0.042857</td><td>0.314286</td></tr><tr><td>奠</td><td>0.416667</td><td>0</td><td>0.583333</td></tr><tr><td>耐</td><td>0.5</td><td>0</td><td>0.5</td></tr><tr><td>耐</td><td>0.606061</td><td>0.090909</td><td>0.30303</td></tr><tr><td>耒</td><td>0.333333</td><td>0</td><td>0.666667</td></tr></table></body></html>

假设一个词语词首含有某个古汉字，这个古汉字在词首的位置的概率越小，表明这个词语成为古汉语词语的可能性越小，同理，如果一个古汉字在词尾的位置的概率越小，表明这个词语成为古汉语词语的可能性也越小。

最终，本文在基于互信息和信息熵得到的词典中通过计算首字和尾字的位置概率，将不合理的词再次过滤，得到最终的词典，本文称之为候补词典。在候补词典中，本文统计了不同长度的词语的数量分布，如图3所示，

![](images/e208c68e851b8ad07f35225f8ea4e430c5de3723b0ae36f8d45aeba493570d06.jpg)  
图3候补词典中不同长度的词语的数量比较

由此可见，在候补词典中，二字词和三字词占比最多，并且二字词和三字词数量接近。

# 2.3分词器的构建

中文的分词算法[19」有很多，根据它们的原理，可以分为三种，基于词典的分词，基于统计的分词，基于理解的分词，其中基于词典的分词的算法的分词速度是最快的。基于词典的分词算法主要有正向最大匹配，逆向最大匹配，双向最大匹配。

甲言是github上开源的古汉语分词器，是一个完整的分词系统，主要分词方式有两种，一种是正向最大匹配分词，另一种是使用训练好的HMM[4]模型来分词。在获取基础词典和候补词典后，我们将两个词典整合在一起，其中有一部分会有相同的词语，这一部分词语通过冗余处理合并，最终形成词典并作为分词器的分词词典。本文使用正向最大匹配作为分词算法[24]。

# 3结果与分析

# 3.1测试数据集

为了测试古文分词的准确性，就需要一个已标注好的语料库作为测试依据。宾夕法尼亚州语言数据联盟大学网站［20]提供了人工标注的文言语料库(LDC2017T14)，该语料库是对左传的分词和词性的标注，共包含了180,000 个中文字符，由两部分构成，训练数据（166138字）和测试数据（28131字)，数据格式为纯文本文件，如表6所示。

# 表6左传语料库样例

<html><body><table><tr><td>左传语料库样例</td></tr><tr><td>元年/t，/w春/n，/w王/n正月/t 辛已/t，/w晉/ns魏舒/nr合/v諸侯/n 之/u 大夫/n 于/p 狄泉/ns，/w 將/d 以/c 城/n 成周/ns。/w</td></tr><tr><td>魏子/nr蔽政/v。/w</td></tr><tr><td>衛/ns 彪傒/nr 曰/v：/w“/w 將/d 建/v 天子/n，/w 而/c 易位/v以/c 令 /v，/w非/d義/v也/y。/w 大事/n奸/v義/n，/w必/d有/v 大咎/n。/w</td></tr><tr><td>晉/ns 不/d 失/v 諸侯/n，/w 魏子/nr 其/u 不免/v 乎/y！/w”/w</td></tr></table></body></html>

然而该数据只包含左传的数据，数据的多样性略显不足。我们扩展了一些数据集，首先选取一些代表性的，不同朝代的文言语料，其中包括春秋，战国，秦朝，汉朝，魏晋南北朝，隋唐，宋朝，辽金元，明朝，清朝，然后组织了古汉语专业学生进行人工标注，最终与左传的数据集进行合并，作为测试集。选取的古籍文本出处如表7所示，

表7标注的文本的出处  

<html><body><table><tr><td>朝代</td><td>节选出处</td></tr><tr><td>春秋</td><td>《史记·田敬仲完世家》《史记·晋文称霸》《论语·学而篇》《邓 析子·无厚》《史记·项羽本纪》</td></tr><tr><td>战国</td><td>《史记·孟尝君列传》《全上古·上书说秦昭王》《楚辞·离骚》 《孟子·梁惠王、公孙丑》》</td></tr><tr><td>秦朝</td><td>《史记·秦始皇本纪》《韩非子·存韩·上书韩王》《史记·李斯 传·上书对二世》</td></tr><tr><td>汉朝</td><td>《论衡》《汉书·董仲舒传》《贾谊传》《史记·仓公传》 《傅子》《抱朴子》《三国志·魏书·武文世王公传》《陆景》《典</td></tr><tr><td>魏晋南北朝</td><td>语》</td></tr><tr><td>隋唐</td><td>《史通·自叙》《长乐老自叙》《与文徵明书》《先侍御史府君神道 表》</td></tr><tr><td>宋朝</td><td>《金石录后序》《指南录后序》《训俭示康》《九议》</td></tr><tr><td>辽金元</td><td>《辽史》《归潜堂记》《金史》《元史·本纪第一》</td></tr></table></body></html>

<html><body><table><tr><td>明朝</td><td>《御制皇陵碑》《前历试卷自序》《白牛生传》《立命之学》</td></tr><tr><td>清朝</td><td>《三十自述》《三侬赘人广自序》《强园老民自传》《与弟文韶书》</td></tr></table></body></html>

标注方法是将原始文本中的字，词，标点符号使用空格分开，标注样例如表8所示，

# 表8人工标注样例

<html><body><table><tr><td>人工标注样例</td></tr><tr><td>元年王充 者，会稽 上虞人也，字 仲任。其先 本 魏郡 元城一姓。孙一</td></tr><tr><td>几世尝从军有功，封会稽阳亭。一岁仓卒国绝，因家焉。以农 桑 为业。世祖 勇任气，卒咸 不揆 於人。岁凶，横道伤杀，怨仇</td></tr><tr><td>众多。会世扰乱，恐为怨仇所擒，祖父泛举家檐载，就安会</td></tr></table></body></html>

由于左传的标注格式区分了词性，所以这里还需要将左传的标注格式转换成空格标注的格式，如表9所示，

表9左传语料库标注格式转换后的格式  

<html><body><table><tr><td>左传语料库标注格式转换后的格式</td></tr><tr><td></td></tr><tr><td>元年，春，王正月辛巳，晋魏舒合诸侯之大夫于狄泉，将以城</td></tr><tr><td>成周。</td></tr><tr><td>魏子莅政。</td></tr><tr><td>卫彪傒曰：“将建天子，而易位以令，非义也。大事奸义，</td></tr><tr><td>必有大咎。晋不失诸侯，魏子其不免乎！”</td></tr></table></body></html>

# 3.2词典扩展前后的效果比较

由于古汉语和现代汉语在验证准确度的方法上是一样的，所以本文使用了Bakeoff2005 数据集［21]包含的 perl 脚本，Bakeoff 是国际计算语言学会（ACL）中文语言处理小组SIGHAN 所主办的国际中文语言处理竞赛，而 Bakeoff 2005 是 SIGHAN 于 2005 年在韩国济州岛举行的第二届竞赛的数据集，该数据集是完全免费和公开的，但是使用的前提是非商业使用。在该数据集中 scripts 文件夹下包含了一个用于测评的脚本文件 score,该文件是一个Perl 程序，为了能让程序运行，需要有一个 Perl 编译器，而 Ubuntu 18.04.3 LTS自带了Perl 编译器和运行环境，所以本文将在ubuntu下进行分词的评估。该脚本需要输入三个参数，分别为标准词表，标准切分，待评测的切分［22]。

本文采用准确率（Precision）、召回率（Recall）和F值（F-measure）作为分词的评价指标，其计算公式为：

$P = \frac { N \cap M } { N } \times 1 0 0 \%$ (9) $R = \frac { N \cap M } { M } \times 1 0 0 \%$ (10) $\mathrm { F } = \frac { 2 \mathrm { P R } } { P \ + \ R } \times 1 0 0 \%$ （204号 (11)

其中，N表示实验获得的新词总个数，M表示语料中存在的新词总个数

接下来，本文基于 Bakeoff 提供的脚本分别对基础词典，候补词典，合并词典进行评估。评价过程如表10所示，

# 表10评价过程

# 评价过程

# 输入：

待切分的语料库ancient_original_data.txt，标准切分文件ancient_gold_data.txt, 基础词典ancient_basic_dict.txt，候补词典ancient_addtion_dict.txt，合并词典 ancient_dict.txt

输出:评价指标，准确率（Precision）、召回率（Recall）和F值（F-measure）

$\textcircled{1}$ 准备待切分的语料ancient_original_data.txt，该语料由上文提到的测试数据集转换而来，将测试数据集中的分词标记删除得到原始语料。  
$\textcircled{2}$ 使用上文编写的Python分词器对待切分语料进行分词，分词器使用基础词典ancient_basic_dict.txt，分词算法使用正向最大匹配。  
$\textcircled{3}$ 输出已分词的古汉语文本ancient_segmentation_data.txt  
$\textcircled{4}$ 将已分词的古汉语文本ancient_segmentation_data.txt，标准切分文本ancient_gold_data.txt，标准词典ancient_dict.txt输入Perl评测脚本并在Ubuntu上运行脚本。  
$\textcircled{5}$ 输出使用基础词典分词的评价指标，准确率、召回率和F值。  
$\textcircled{6}$ 从 $\textcircled{2}$ 重新开始，并使用候补词典ancient_addition_dict.txt，得到候补词典分词的评价指标。  
$\textcircled{7}$ 从 $\textcircled{2}$ 重新开始，并使用合并词典ancient_dict.txt，得到合并词典分词的评价指标。

在使用正向最大匹配分词算法的条件下，基础词典，候补词典和合并后的词典的分词结果比较如表11所示，

表11三个词典的分词结果比较  

<html><body><table><tr><td>指标</td><td>基础词典</td><td>候补词典</td><td>合并词典</td></tr><tr><td>P</td><td>0.801</td><td>0.630</td><td>0.821</td></tr><tr><td>R</td><td>0.838</td><td>0. 778</td><td>0.859</td></tr><tr><td>F</td><td>0.819</td><td>0.696</td><td>0.839</td></tr></table></body></html>

从上面的比较可以看出，将基础词典和候补词典合并之后，分词器的准确性得到了很大的提升。

# 3.3与古汉语开源分词器比较

甲言是一个开源的古汉语分词器，为了验证本文提出的分词器是否能够达到开源分词器的分词效果，本实验将本文的古汉语分词器与甲言分词器进行比较，甲言分词器中包含了两种分词算法，一种是基于词典的分词，一种是基于 HMM 模型的分词。因此，我们分别与这两种方式进行比较。评价方式与上文提到的评价过程类似，将待切分的文本ancient_original_data.txt分别输入两个分词器，然后分词，并输出各自的评价指标，准确率、召回率和F值，结果如表12所示，

表12三个词典的分词结果比较  

<html><body><table><tr><td>分词器</td><td>P</td><td>R</td><td>F</td></tr><tr><td>本文的分词器</td><td>0.821</td><td>0.859</td><td>0.839</td></tr><tr><td>甲言的词典分词</td><td>0.651</td><td>0.751</td><td>0. 698</td></tr><tr><td>甲言的HMM分词</td><td>0.750</td><td>0.798</td><td>0. 773</td></tr></table></body></html>

由此可以看出，本文设计的分词器与甲言的两种分词模式相比，在准确度，召回率，F值这些指标上均有明显地提升，本文提出的分词器的F 值比甲言的词典分词模式高出了$1 4 \%$ ，总体上取得了良好的效果。由此表明，基于互联网大规模语料库的词典构建在古汉语分词上是可行的。

# 4.总结

本文利用大规模古文语料库，通过整合了互联网上的古汉语数据资源，生成了一个古汉语分词基础词典，并使用N-Gram、互信息、信息熵、位置成词概率相结合的新词发现的方式在大规模语料库上抽取古汉语词汇，弥补了基础词典的不足。在词典的基础上，本文利用正向最大匹配实现古文的分词，通过与甲言进行比较，在人工标注的分词语料库上取得了良好的效果。

本研究也存在一定的局限。例如本文采集古汉语数据所用的数据源比较少，在以后的研究中可以进一步扩大数据源，收集更全面的古汉语数据；在新词发现中的超参数的设置还有待优化，以致于进一步提升分词的准确度；在本文中没有考虑歧义词处理，然而在歧义词处理方面，刘风成[30]提出 AdaBoost.MH算法进行语义消歧，并引入了语义范畴,提高了排歧的正确率。

中国古代文献是一个宝藏，从古汉语文本中挖掘有价值的信息在考古中有很重要的意义。本文利用在线大规模古文语料库，经过数据处理，构建古汉语词典，利用正向最大匹配实现对古文的分词。通过与甲言分词系统进行比较，分词准确率有了较大的提高。通过对古文献的分析研究，有助于深入了解中国文化的变迁，开展数字心理考古研究，为进一步弘扬传统文化提供技术支撑。

# 参考文献：

[1]Amrani，A.，V. Abajian，Y. Kodratoff，and O. Matte-Tailliez. "A Chain ofText-MiningtoExtractInformationinArchaeology."20083rdInternational Conference on Information and Communication Technologies:From Theory to Applications， 7-11 April 2008 2008.  
[2]严顺．基于CRF 的古汉语分词标注模型研究[J]．江苏科技信息，2016(8):10-12.  
[3］王晓玉，李斌．基于 CRFs 和词典信息的中古汉语自动分词[J]．数据分析与知识发现，2017，1(5).  
［4］钱智勇，周建忠，童国平，et al．基于 HMM 的楚辞自动分词标注研究［J]．图书情报工作，2014(04) :107-112.  
[5］李筱瑜．基于新词发现与词典信息的古籍文本分词研究［J]．软件导刊，2019,18 (04) :66-69.  
[6］刘永楠，李建中，高宏．海量不完整数据的核心数据选择问题的研究［J]．计算机学报，2018.  
[7］林自芳，蒋秀凤．基于改进位置成词概率的新词识别［J]．福州大学学报（自然科学版)，2011(01) :48-53.  
[8］夭荣朋，许国艳，宋健．基于改进互信息和邻接熵的微博新词发现方法[J]．计算机应用，2016，36(10):2772-2776.  
[9］古汉语分词器，甲言，https://github.com/jiaeyan/Jiayan  
[10]Prabhu C.， Chivukula A.， Mogadala A.， Ghosh R.，Livingston L. (2019)Big Data Tools-Hadoop Ecosystem， Spark and NoSQL Databases. In: Big DataAnalytics: Systems, Algorithms， Applications. Springer， Singapore  
[11] Olsson， J. (2019)． Using Elasticsearch for full-text searches onunstructured data (Dissertation). Retrieved fromhttp://urn.kb.se/resolve?urn=urn:nbn: se:uu:diva-395654  
[12]汉语古典文本数据库 https://github.com/mahavivo/scripta-sinica  
[13］王思丽,祝忠明,刘巍,杨恒.领域本体学习语料的自动获取与预处理方法研究［J].图书馆学研究,2019(20):54-64.  
[14]H. Wang，B. Wang，M. Zou and J. Duan，"New Cyber Word Discovery UsingChinese Word Segmentation,"2019IEEE3rdInformation Technology,Networking， Electronic and Automation Control Conference (ITNEC)， Chengdu,China，2019，pp.970-975.  
[15] Cheng，& Lee， W. (2018)． Combining Mutual Information and Entropy forUnknown Word Extraction from Multilingual Code-Switching Sentences.  
[16]Junjie Hou， Yongxin Zhu, Sen Du, Shijin Song， Design and implementationofreconfigurable acceleration for in-memory distributed bigdatacomputing,Future Generation Computer Systems.  
[17］刘鹏，滕家雨，丁恩杰，et al．基于 Spark 的大规模文本 $\mathrm { \ k }$ means 并行聚类算法[J]．中文信息学报，2017(04):150-158.  
[18]Aziz K.， Zaidouni D.， Bellafkih M. (2018) Big Data Optimisation AmongRDDs Persistence in Apache Spark. In: Tabii Y.，Lazaar M.，Al Achhab M.,Enneya N.(eds） BigData， CloudandApplications.BDCA2018.Comunications in Computer and Information Science， vol 872. Springer,Cham  
[19］张梅山，邓知龙，车万翔，et al．统计与词典相结合的领域自适应中文分词[J].中文信息学报，2012(2):8-12.  
[20］古汉语语料库，https://catalog.ldc.upenn.edu/LDC2017T14  
[21]中文分词大赛数据集，http://sighan.cs.uchicago.edu/bakeoff2005/  
[22］黄翼彪．开源中文分词器的比较研究[D]．郑州大学，2013.  
[23］王思力，张华平，王斌．双数组 Trie 树算法优化及其应用研究[J]．中文信息学报，2006，20(5):26-32.  
[24］熊志斌，朱剑锋．基于改进 Trie 树结构的正向最大匹配算法[J]．计算机应用与软件，2014(05):282-284.  
[25]汉文学网，https://www.hwxnet.com/  
[26]汉典网，https://www.cidianwang.com/[27] 汉典，https://www.zdic.net/  
[28］在线汉语字典，http://xh.5156edu.com/  
[29]国学大师，http://www.guoxuedashi.com/  
[30］刘风成，黄德根，姜鹏．基于 AdaBoost.MH 算法的汉语多义词消歧[J]．中文信息学报，2006(03):8-15.  
[31]IK 插件，https://github.com/medcl/elasticsearch-analysis-ik