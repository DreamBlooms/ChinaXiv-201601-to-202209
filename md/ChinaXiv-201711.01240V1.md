# 商品检索中的多任务识别与分析

张鹏翼周 翔 王军(北京大学信息管理系北京 100871)

摘要：【目的】对商品检索中的购物任务进行识别，并对多任务会话行为特征进行分析。【方法】利用淘宝商品分类体系以及自建的商品词表，根据商品检索的检索式进行购物任务识别，数据集为2754个用户的19704个检索会话。【结果】影响每个购物任务所用检索式数的因素包括商品分面、数量的多少以及描述难易程度；有主要任务和次要任务之分的多任务会话中，任务之间的关系更为紧密。局限购物任务识别方法有待完善，只以检索式作为研究对象无法全面反映用户行为特征。【结论】本研究可以帮助理解购物中的商品检索行为，并为设计更好的商品推荐算法、预测用户购物过程、行为等提供依据。

关键词:商品检索购物任务识别购物任务分析多任务会话 分类号：G358

# 1引言

近年来，网络购物由于其便捷、高效，不受时空地域限制的特点，越来越受到用户青睐。借助互联网高度的互动性、便利性、透明性和个性化，网络购物得以提升服务质量，并且可以通过数据挖掘、机器学习等技术来实施实时营销和精准营销[1]。基于以上优点,网络购物成为了人们生活中越来越重要的一种购物方式。

据中国互联网络信息中心(CNNIC)发布的《2014年中国网络购物市场研究报告》2显示，2014年网络零售交易额达到2.79万亿元，同比增长 $49 . 7 \%$ 。在网络购物发展势头迅猛的当下，如何分析网络购物用户行为，得出行为特征，并以此为基础对电商系统进行优化和改进，就成为一个值得关注的问题。在网络购物行为中，同时开展多个购物任务的现象很常见，但对于网络购物任务的识别以及多任务情况下搜索特征的分析很少。一般网络搜索也具有多任务的特性，例如Spink等3的研究指出，多任务信息检索是一种很常见的用户行为，他们在检索系统随机抽取的1000个会话中,有 $1 1 . 4 \%$ 的会话涉及多任务检索；Spink 等4的研究也发现，含有三个或以上检索式的会话中，多任务会话占比超过九成。但对网络购物用户信息行为的分析中，针对用户使用的检索式进行分析，识别用户任务的研究较少。本研究旨在补充此领域研究的不足，通过分析用户在网络购物时使用的检索式，对用户的购物任务进行识别，并根据所识别的结果展开多购物任务间关系以及搜索特征的研究。

与本研究相关的一些定义如下：会话是一个客户与服务器之间的不中断的请求响应序列，用户的一次会话代表了用户的一次网购过程[5]。本研究中,如果用户在完成一个动作之后连续45分钟没有进行任何动作，则视为一个会话的结束，并将这之后用户第一个动作作为下一个会话的开始[。购物任务是指用户为了购买某一种商品所做出的一系列行为的集合，基于研究目的，本研究主要在单个会话中进行购物任务的识别，多任务会话则是指含有多个购物任务的会话。

# 2 文献综述

# 2.1检索系统中的任务识别

检索任务识别的主要思路有：比较检索式之间的相关度；Glance[7提出比较网络搜索引擎中进行检索所返回的URL；Raghavan 等[8提出比较检索所得的文档等。根据用户两次检索在上述指标上的相似程度，判断两次检索是否属于同一个检索任务。

比较两个检索式相关度的方法主要有以下两种：对比检索式之间的字符相似程度，提取两个检索式中的检索词集合，可用的指标有Järvelin 等的Jaccard指标，以两个集合的交集与两个集合的并集的比值作为相似度的判断指标，以及Jones等[1o]提到的Levenstein 距离；对比检索式之间的语义关联程度[],采用向量空间的思想，分别利用外部知识资源如Wiktionary和Wikipedia所提供的语义关系，计算每个检索词与语义网中每个资源的相似度并生成向量(如检索词t，共有W个资源， $\mathrm { { C _ { i } } }$ 为检索词t与第i个资源的相关度，则生成的向量为 $\mathrm { C ( t ) } { = } ( \mathrm { C } _ { 1 } , \mathrm { C } _ { 2 } , \cdots , \mathrm { C } _ { \mathrm { w } } )$ ，每个检索式对应的向量为检索式中包含的检索词对应的向量之和，然后通过计算两个检索式所对应向量的夹角作为计算两个检索式相关度的指标。

Lucchese等[12]的研究在具体的检索任务识别中采取了以下方法：首先对检索日志进行一定的处理，步骤包括：去除空记录和无意义记录、去除停用词、用算法去除检索词形态上的变化、去除持续时间较长而且含有过多检索式的会话记录(这些记录可能由机器产生，与对用户研究的目的不符)。然后根据上文所提到的方法，计算检索式之间的字符相似程度和语义关联程度。最后综合两个评价指标，他们提出两种方法：其一是做简单的加权处理，对两个指标进行加权平均，得到一个统一的指标；其二是当词形相似度高于一定阈值的时候取词形相似度作为最终指标，而当词形相似度低于阈值的时候取词形相似度和语义相似度的较大值作为指标。

从已有研究来看，目前任务识别的主流方式是分析检索式之间的字符相似程度或语义关联程度，建立相应的评价指标，进而识别出同属于一个任务的多个检索式。

# 2.2多任务检索会话研究

Spink 等[13]认为，关于多任务检索会话产生的原因主要有两种：检索用户在一开始就有多个需要检索的主题；检索用户一开始只有一个检索主题，但在检索的过程中衍生出其他的检索主题。

关于多任务检索会话的特征，Ozmutlu 等[14]发现多任务会话在检索式的长度和会话所花时间上都多于单任务会话。他们的另一项研究[15也验证了多任务会话所花时间更多的结论。Lin等[16发现多任务会话中检索式数量较之单任务会话更多。

Lucchese 等[12]、Spink 等[13]、Wang 等[17]都采用日志分析的方法对多任务会话进行研究，相关的研究结果如表1所示：

表1相关研究结果对比  

<html><body><table><tr><td>比较项</td><td>Lucchese等</td><td>Spink 等</td><td>Wang等</td></tr><tr><td>日志来源</td><td>AOL</td><td>AltaVista</td><td>Bing.com</td></tr><tr><td>日志时间</td><td>3个月</td><td>1天</td><td>5天</td></tr><tr><td>会话数</td><td>307</td><td>254</td><td>37 547</td></tr><tr><td>检索式数</td><td>1 424</td><td>655</td><td>114 723</td></tr><tr><td>每个会话平 均检索式数</td><td>4.49</td><td>2.58</td><td>3.1</td></tr><tr><td>每个任务平 均检索式数</td><td>2.57</td><td></td><td>6.6</td></tr><tr><td>每个会话平 均任务数</td><td>1.8</td><td></td><td></td></tr><tr><td>多任务会话 比例</td><td>74%</td><td>81.2%</td><td></td></tr><tr><td>其他</td><td>会话的平均 持续时间为 15分钟</td><td>多任务会话平均时间和 检索式长度约为普通会 话的2倍</td><td></td></tr></table></body></html>

如表1所示，网页检索中每个会话所含的检索式平均在2-5个左右，多任务会话的比例高达 $70 \% 8 0 \%$ 以上。

目前对多任务会话的研究主要集中在会话及任务的数值特征(如时间、检索式长度、每个会话平均任务数、每个任务平均检索式数等)。而进一步的研究，如分析任务类型对相关数值特征的影响，以及分析会话中任务间的联系等还比较缺乏。

本研究通过对商品检索日志进行处理，采取以商品类型为特征对检索式进行标引进而对任务进行识别的新方式，分析商品检索中多任务会话的基本情况，并进一步挖掘商品类型与检索行为之间的关系，以及多任务会话中任务关系与任务主次之间的关联，填补目前该领域对这一方面研究的空白。

# 3 研究方法

# 3.1 数据描述及预处理

采用的日志数据是由第三方市场调查机构采集自用户客户端2013年5月在淘宝网上的访问数据。可用日志数据表中总共有记录1409160条，涉及到81759个访问会话，4285个用户。

数据预处理的步骤如下：

(1）对商家数据进行筛选和剔除。由于本研究主要是针对网络购物中的消费者进行研究，因此筛去了会话数大于100的用户(很可能是商家)的数据。(2）去除用户其他行为类型如登录、浏览、翻页、筛选等产生的记录。由于本研究侧重用户搜索时产生的日志，其他行为的日志与本研究无关，也一并进行筛选和剔除。

经过预处理得到的数据集合包括53091个含有原始检索式的记录，共涉及到2754个用户，占用户总数的 $6 4 . 2 7 \%$ ；共涉及19704个会话，占用户会话总数的$2 4 . 1 0 \%$ 。

# 3.2任务识别方法及评估

对已有的商品检索记录进行任务识别，流程如图1所示：

![](images/dd8499da1b4f2d332f51ab4b71b270672318b5acd491c8237a30717567d47d31.jpg)  
图1任务识别流程

(1）通过淘宝 $\mathrm { \ A P I ^ { \mathrm { ( p ) } } }$ 获取所有的商品类目数据信息-共14000余商品类目，类目层级4-5级。以这一商品分类目录为基础，并对类目设置进行增补、修改和删减，建立一套改进的商品类目等级分类目录。

(2）对原有的商品检索记录进行切词处理，对53091条商品检索记录进行切词，共得到163617个词语。对所得词语的词频进行统计，并选取其中出现频次大于等于10次的词语，共2376个。对所得词语进行筛选，选取其中能代表商品类型的词语，作为词表的组成部分。再将所筛选出的词语，与建立好的商品类目分类体系进行匹配。同时选取商品类目分类体系中的商品类目名称，也作为词表的组成部分纳入。将两部分进行合并，得到一个较为完整的词表，包含了绝大多数直接指向商品类目的词语以及一些检索中使用频率较高的品牌名称。

对购物任务进行识别时，将商品检索记录与词表和商品类目映射关系进行匹配，若一条检索记录匹配到词表中的某个词语，则将该条检索记录所对应的购物任务用该词语所对应的商品类目进行标识。原始商品检索记录共有53091条，匹配成功的记录有41486条，匹配成功记录占总记录的 $78 . 1 4 \%$ 。如果某一用户一个会话中的两条或多条检索记录被标识为同一商品细类，则认为这两条检索记录属于同一购物任务。

为考察该购物任务识别方法的准确度，从匹配成功的商品检索记录中随机抽取了200条进行人工的任务识别。在200条记录中，有164条记录的购物任务识别准确或基本准确，准确率为 $82 \%$ 。

# 4结果分析

# 4.1会话及任务分布情况

检索日志共包含19074个会话，进行购物任务识别之后会话内包含被识别的购物任务的会话16050个，占会话总数的 $8 4 . 1 5 \%$ ，共对应购物任务26182个。平均每个会话对应的购物任务为1.63个，每个购物任务对应的检索记录为1.585条。为比较各商品大类之间每个任务的平均检索式数，列出检索式数/任务数比值较高和较低的5个大类，如表2所示。可见，检索式数/任务数比例最高的类目是服装、箱包皮具、五金/工具、手表等，而比例最低的类目主要是传统滋补营养品、药品/医疗器械、个人护理/保健/按摩器材、珠宝/钻石/翡翠/金银等，经分析，影响任务平均检索式的因素主要有以下两点：

表2部分商品类目检索式数与任务数  

<html><body><table><tr><td>商品类目</td><td>类目 ID</td><td>检索 式数</td><td>任务数</td><td>任务平均 检索式数</td></tr><tr><td>服装</td><td>161</td><td>7 770</td><td>19 358</td><td>2.49</td></tr><tr><td>箱包皮具</td><td>146</td><td>1 406</td><td>3 047</td><td>2.17</td></tr><tr><td>五金/工具</td><td>126</td><td>116</td><td>233</td><td>2.01</td></tr><tr><td>手表</td><td>159</td><td>129</td><td>256</td><td>1.98</td></tr><tr><td>网游</td><td>155</td><td>73</td><td>142</td><td>1.95</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>网络设备/ 网络相关</td><td>116</td><td>51</td><td>72</td><td>1.41</td></tr><tr><td>珠宝/钻石/ 翡翠/金银</td><td>147</td><td>176</td><td>246</td><td>1.40</td></tr><tr><td>个人护理/ 保健/按摩器材</td><td>123</td><td>160</td><td>220</td><td>1.38</td></tr><tr><td>药品/医疗器械</td><td>156</td><td>68</td><td>92</td><td>1.35</td></tr><tr><td>传统滋补营养品</td><td>134</td><td>135</td><td>176</td><td>1.30</td></tr></table></body></html>

(1）检索商品分面较多，检索条件的涉及面也比较广泛的商品类型时，往往会在一个任务中使用更多的检索式进行检索。如某用户(UID：9242120128831377467；SID:99456)先以"雪纺衫"作为检索词，但检索结果数量较多，所以用户为了进一步筛选，减少挑选范围，加入限制条件，使用"雪纺衫短袖"进一步检索，而后使用"雪纺衫 短袖 花色"进一步检索。相比之下，任务平均检索式数较低的商品如传统滋补营养品、药品/医疗器械等类目下的商品专指程度较高，用于进一步检索的条件也比较少，进行一次检索之后所得的商品列表可以由用户在其中进行直接选择。比如某用户(UID:10071878660749185838；SID:624)购买保婴丹(属于药品/医疗器械)，只检索"余仁生 $^ +$ 保婴丹"就得到较小的商品范围，不需要更多的检索式缩小检索范围。

(2)任务平均检索式数较高的商品类型所对应的词语在日常生活中使用频率不高，较难描述，用户需要不断修正检索式来检索自己想要的商品。比如五金/工具类的某一个任务中，某用户(UID：17461349388365160511；SID：48488)在检索时使用了“移动门门锁”、“移动门锁”、“移门锁”、“趟门门锁”、“门锁"等词汇来检索商品。

# 4.2 双任务会话分析

(1）主次任务的区分

在同时开展两项购物任务的会话中，购物任务可能存在主次之分。用户可能会更为关注主要任务，进行更为详细的检索和筛选，因此用户在主要任务中使用的检索式会更多，反之亦然，因此将每个任务所含的检索式数量作为判断任务是否有主次之分的依据。当会话中的两个任务所含检索式数量有显著差异时，认为这两个任务有主次之分，所含检索式较多的为主要任务，较少的为次要任务。当会话中的两个任务所含检索式数量没有显著差异时，笔者认为这两个任务没有主次之分。

具体的分析步骤为：首先抽取出双任务会话及其所含的两个任务及对应的检索式数量，然后基于以下标准进行判断：检索式数相差0或1的；检索式数相差2且两任务所含检索式数不为1和3的。满足以上两个标准的其中一个则标识为没有主要任务和次要任务之分，两个标准都不满足的则为有主要任务和次要任务之分。

在总共3133个双任务会话中，2591个会话的两个任务间没有主次关系，占比 $82 . 7 0 \%$ ，而有主要、次要任务之分的会话有542个，占比 $1 7 . 3 0 \%$ 。

# (2）任务间关系

本研究将两个任务之间的关系分为三类：强关联任务，两个任务之间有比较紧密的联系，比如某一用户的两个任务分别对应"沙发"和"住宅家具"两个商品类目(上下位类)；弱关联任务，两个任务之间有所联系，但并不紧密，如某一用户的两个任务分别对应"长裤"和“牛仔裤"两个商品类目(具有共同的上位类"裤子")；无关联任务，两个任务之间没有联系，如用户的两个任务分别对应“牛仔裤"和"面膜/面膜粉"两个商品类目。

根据这一区分标准，对3133个双任务会话进行任务关系的标识。标识结果如表3所示：

表3双任务会话关联类型分析  

<html><body><table><tr><td>会话类型</td><td>强关联</td><td>比例</td><td>弱关联</td><td>比例</td><td>无关联</td><td>比例</td></tr><tr><td>无主要任务</td><td>309</td><td>11.93%</td><td>305</td><td>11.77%</td><td>1977</td><td>76.30%</td></tr><tr><td>有主要任务</td><td>83</td><td>15.31%</td><td>48</td><td>8.86%</td><td>411</td><td>75.83%</td></tr><tr><td>总计</td><td>392</td><td>12.51%</td><td>353</td><td>11.27%</td><td>2388</td><td>76.22%</td></tr></table></body></html>

其中无关联任务的比例最多，占 $76 . 3 0 \%$ 。有主要任务的会话中，强关联和弱关联任务有比较显著的差别。考察在所有两任务相关的情况，运用SAS软件进行独立性检验，得到其 $\chi ^ { 2 }$ 为7.3558,P值为0.0067，在$\scriptstyle { \mathfrak { a } } = 0 . 0 5$ 水平下可以否定假设，即会话类型和任务类型相关。

双任务会话中，有主次任务的会话，其两个任务之间的联系会更为紧密，而无主次任务之分的会话，任务之间的联系不如前者。

# 4.3 三任务会话分析

# (1）主要任务区分

三任务会话中，如果有一个任务的检索式数量大于其他两个任务检索式数量之和，则认为该任务是会话中的主要任务；另外如果有一个任务的检索式数量等于其他两个任务检索式数量，且检索式数量较少的两个任务所含检索式数量均大于一个，也认为检索式数量最多的任务是该会话中的主要任务。1230个三任务会话中，有291个会话含有主要任务，占总数的$23 . 6 6 \%$ 。

相关度更高)，值接近-1表示负关联(即没有主要任务的会话中任务相关度更低)。在这一分析中，KendallTau-b的 $9 5 \%$ 置信区间为(-0.3404，-0.0056)，该区间在零点左边，故可以认为会话类型和任务之间的关系有负关联，没有主要任务的会话中任务之间的相关度更低，而有主要任务的会话中任务之间的相关度更高。

“maintask\*relation”表的统计量  
统计量 值渐近标准误差  
Gamma -0.3492 0.1563  
Kendall_Tau-b -0.1730 0. 0837  
Stuart Tau-c -0.1633 0.0801  
Somers DCR -0.2178 0. 1044  
Somers D RC -0.1375 0.0680  
Pearson 相关系数 -0.1626 0. 0877  
Spearman 相关系数 -0.1800 0.0870  
Lambda非对称CR 0. 1270 0. 0756  
Lambda 非对称RC 0.0000 0.0000  
Lambda 对称 0.0860 0.0512  
不确定系数CR 0.0224 0. 0193  
不确定系数RC 0. 0387 0.0330  
不确定系数对称 0.0284 0.0243  
样本大小=120

# (2）任务间关系

对于会话中存在三个任务的关系分析，采用两两比较的方式，判断两个任务为相关/不相关，这样三任务会话中任务之间的关系有三种：三个任务都有关联;两个任务有关联，另一个任务与它们无关联；三个任务两两都不关联。

随机抽取120个会话，其中90个不含主要任务的会话，30个含主要任务的会话，进行会话中三个任务之间关系的判定。结果如表4所示：

表4三任务会话中是否有主要任务和有关联任务之间关系  

<html><body><table><tr><td>会话 类型</td><td>三任务 都关联</td><td>比例</td><td>两任务 关联</td><td>比例</td><td>无关联</td><td>比例</td></tr><tr><td>无主要 任务</td><td>10</td><td>11.11%</td><td>32</td><td>35.56%</td><td>48</td><td>53.33%</td></tr><tr><td>有主要 任务</td><td>4</td><td>13.33%</td><td>17</td><td>56.67%</td><td>9</td><td>30.00%</td></tr><tr><td>总计</td><td>14</td><td>11.67%</td><td>49</td><td>40.83%</td><td>57</td><td>47.50%</td></tr></table></body></html>

运用SAS软件对任务类型和关系类型做属性变量关联度计算，结果如图2所示。使用KendallTau-b统计量进行判断，该统计量取值在-1到1之间，值接近1表示正关联(即没有主要任务的会话中任务之间

# 4.4多任务会话关系

综合双任务会话中任务关系和三任务会话中关于任务关系的研究，可以得到如下结论：有主要任务(即使用检索式较多的任务)的会话中，会话中所含任务之间的关系较之无主要任务的会话更紧密一些。

无主要任务的会话情境对应用户预设的多个购物任务，这些任务重要程度相当且未必有直接联系。例如某用户(UID:10987349518420796011；SID:6367)欲购买两种商品：手机壳和连衣裙，用户在同一会话中分别对这两种商品进行检索，使用的检索式数量也会大体相当。如上文提到的用户，在会话中关于手机壳和连衣裙的检索式均为5条。

有主要任务的会话，用户在进行主要任务的检索时会衍生出一些有关系的次要任务，主要任务和次要任务之间联系会比较紧密；或者是用户先检索一种商品，然后在检索过程中受到影响意识到自己真正需要的商品，从而转到主要任务的检索当中。比如某用户(UID:15691965703667985508；SID:37988)想购买拖鞋，在检索拖鞋的时候使用了三条检索式，在检索过程中可能商品结果页面推荐了商品“果冻鞋”，因而衍生出“果冻鞋"的检索式一条。在这样的情境下，两个任务之间检索式数量会存在差别，存在主要任务和次要任务之分，同时主要任务和次要任务之间在商品类型上会有比较紧密的联系。

# 5结论和讨论

本研究旨在对商品检索中的检索式进行任务识别并分析其特征，得出的主要结果如下：

(1）影响不同种类商品平均每个购物任务所用检索式数的因素主要有两个：其一是商品分面多少及数量多少，分面多、数量多的商品，需要用更多检索式来缩小检索结果范围，反之亦然；其二是商品描述的难易程度，需要专业术语描述的商品较难进行检索，需要不断改变检索词，提交不同的检索式以得到比较准确的检索结果范围。

(2）在多任务会话中，以检索式的多少来定义主要任务和次要任务，得到结论：有主要任务和次要任务之分的会话中，任务之间的联系要比无主要任务和次要任务之分的会话更为紧密。

本研究也存在一些不足，在购物任务的识别中，商品分类体系、词表构建、匹配规则等都有可以进一步完善的空间。以商品检索式作为购物任务识别的依据存在一定局限，因为检索式只反映用户的检索行为，而没有对其他购物行为特征如商品浏览、比较、购物决策等进行考虑，因而对用户的分析可能不够全面;而其他用户行为特征，如点击行为、页面之间的跳转等，也可以为购物任务识别提供依据。今后可以结合其他数据，对用户多购物任务的信息行为特征展开进一步研究。此外，随着移动购物的发展和普及，考察移动端用户行为，并与PC端用户行为进行比较，也是一个值得研究的课题。

# 参考文献：

[1] 冯炜．消费者网络购物信任影响因素的实证研究[D]．杭 州：浙江大学,2010.(Feng Wei.Empirical Study on Factors Influencing Trust of Consumers in Online Shopping [D]. Hangzhou: Zhejiang University,2010.)   
[2] 中国互联网络信息中心.2014年中国网络购物市场研究报 告[EB/OL].[2015-06-30].http://www.cnnic.cn/gywm/xwzx/ rdxw/2015/201509/W020150908609566580083.pdf.(CNNIC. The Research Report of Online Shopping Market in China, 2014 [EB/OL].[2015-06-30]. htp://www.cnnic.cn/gywm/xwzx/ rdxw/2015/201509/W020150908609566580083.pdf.)   
[3]Spink A, Ozmutlu H C,Ozmutlu S. Multitasking Information Seeking and Searching Processes [J]. Journal of the American Society for Information Science and Technology,20o2,53(8): 639-652.   
[4]Spink A,Park M, Jansen B J. Information Task Switching and Multitasking Web Search[J].Proceedings of the American Society for Information Science and Technology, 2004, 41(1): 213-217.   
[5]张文君，王军，徐山川．电商用户需求状态的聚类分析- 以淘宝网女装为例[J].现代图书情报技术，2015(3):67-74. (Zhang Wenjun,Wang Jun,Xu Shanchuan. The Probing of E-commerce User Need States by Page Cluster AnalysisAn Empirical Study on Women's Clothes from Taobao.com [J].New Technology of Library and Information Service, 2015(3):67-74.)   
[6]袁兴福，张鹏翼，刘洪莲,等．基于点击流的电商用户会话 建模[J]．图书情报工作，2015，59(1):119-126.(Yuan Xingfu，Zhang Pengyi，Liu Honglian，et al.Modeling E-commerce User Session Behaviors Based on Click-through Sequences [J]. Library and Information Service,2015,59(1): 119-126.)   
[7]Glance N S. Community Search Assistant [C]. In: Proceedings of the 6th International Conference on Intelligent User Interfaces. New York: ACM,2001: 91-96.   
[8]Raghavan V V, Sever H. On the Reuse of Past Optimal Queries[C].In: Proceedings of the 18th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACM,1995:344-350.   
[9]Järvelin A， Järvelin A, Järvelin K. S-grams:Defining Generalized N-grams for Information Retrieval [J]. Information Processing & Management, 2007,43(4):1005-1019.   
[10] Jones R，Klinkner K L.Beyond the Session Timeout: Automatic Hierarchical Segmentation of Search Topics in Query Logs [C]. In: Proceedings of the 17th ACM Conference on Information and Knowledge Management. New York: ACM,2008: 699-708.   
[11] Salton G, McGill M J.Introduction to Modern Information Retrieval [M]. McGraw-Hill Book Company, 1983.   
[12] Lucchese C，Orlando S,Perego R,et al. Identifying Task-based Sessions in Search Engine Query Logs[C]. In: Proceedings of the 4th ACM International Conference on Web Search and Data Mining.New York:ACM,2011:277-286.   
[13]Spink A,Park M,Jansen BJ,et al.Multitasking During Web Search Sessions [J].Information Processing & Management, 2006,42(1): 264-275.   
[14]Ozmutlu S,Ozmutlu H C，Spink A.Multitasking Web Searching and Implications for Design [J].Proceedings of the American Society for Information Science and Technology, 2003,40(1):416-421.   
[15] Ozmutlu S,Ozmutlu H C,Spink A.A Study of Multitasking Web Search [C].In:Proceedings of International Conference on Information Technology:Coding and Computing (ITCC 2003).Washington DC:IEEE,2003:145-148.   
[16]Lin S,Belkin N.Validation of a Model of Information Seeking over Multiple Search Sessions [J].Journal of the American Society for Information Science and Technology, 2005,56(4): 393-415.   
[17]Wang H,Song Y,Chang M W,et al. Learning to Extract Cross-session Search Tasks [C].In:Proceedings of the 22nd International Conference on World Wide Web．Geneva: InternationalWorldWide Web ConferencesSteering Committee,2013:1353-1364.

# 作者贡献声明：

张鹏翼：研究设计，论文撰写、修改;  
周翔：实验开展，数据分析，论文撰写、修改;  
王军：研究设计，论文修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

支撑数据由作者自存储,E-mail: zhouxiang.im@pku.edu.cn。[1]张鹏翼，周翔，王军.query_by_product_category.csv.查询词按商品类目分布.  
[2]张鹏翼，周翔，王军．task_analysis.csv.双任务及多任务关系分析.  
[3]张鹏翼，周翔，王军．first_class_product_category.csv.商品大类相关数值特征.

收稿日期:2015-10-19   
收修改稿日期:2015-11-09

# Multi-task Session Identification and Analysis in Product Search

Zhang PengyiZhou XiangWang Jun (Department of Information Management, Peking University, Beijing 10o871, China)

Abstract:[Objective] This research aims to identify shopping tasks from product search,and then analyze the characteristic of multi-task sessions.[Methods] Using the product classfication of Taobao,and a list of manually selected product terms,we identified online shopping tasks based on query terms from 19 704 search sessions by 2 754 users.[Results]First,factors influence the number of queries per shopping task: productcharacteristics,the amountof available products,andthe dificulty indescribing productcategory with query terms.Second,we found that inssions witha major task,the relationshipamong the shopping tasks is closer.[Limitations]The task identification method based n query terms cannot completely describe thecomplex consumer shopping behaviors.[Conclusions]This study provides an exploratory understanding of the relationships among various shopping tasks,and may be used to improve product recommendation algorithm, as well as predict shopping behaviors.

Keywords: Product searchShopping task identificationShopping task analysisMulti-task session