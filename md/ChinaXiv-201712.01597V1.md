# 基于多特征多分类器集成的专利自动分类研究

贾杉杉」刘　畅²　孙连英³刘小安」　彭　涛²(北京联合大学智慧城市学院 北京 100101)2(北京联合大学机器人学院 北京 100101)3(北京联合大学城市轨道交通与物流学院北京 100101)

摘要：【目的】为了准确地给专利申请书分配IPC分类号，本文提出一种基于多特征多分类器集成的专利自动分类方法。【方法】使用从专利申请书中提取的全词典TFIDF特征、信息增益词典TFIDF 特征、段落向量特征、主题模型向量特征，分别训练朴素贝叶斯、支持向量机、AdaBoost分类器，以此构建特征-类别矩阵，并结合F1权重矩阵集成，获得最终IPC预测分类号。【结果】对2014年-2016年"发动机或泵"领域的10个小类进行分类，使用 Top Prediction、All Categories 和 Two Guesses 三种评估方法得到准确率分别为: $78 . 9 \%$ 、 $80 . 1 \%$ 、 $91 . 2 \%$ 。

【局限】训练仅仅使用了2014年-2016年共三年的专利数据，数据规模有限。【结论】在"发动机或泵"领域，本文方法能够有效地提高专利文本分类的准确率。

关键词：专利分类段落向量主题向量分类器集成 分类号：G250

# 1引言

中国知识产权局研究发现[1]，知识资源和信息资源是最主要的智力资源，尤其是专利信息这样基于创新、体现技术的资源。为了尽快找到和利用相关的专利信息，需要对每一件专利按照其技术内容分配相应的专利分类号[2]。专利分类方法有很多，其中使用最广泛的是国际专利分类(International Patent Classification,IPC)体系[3]，其几乎包括了与发明创造有关的全部知识领域，中国、美国以及其他50多个国家和地区都在使用。

使用IPC分类体系进行专利分类难点众多，主要有：

(1）类别众多，层次复杂，最新的IPC分类体系有 7万多个类别,5个层级;

(2）一件专利可被赋予不止一个分类号;(3）为了扩大专利受保护范围，专利申请人对于专利申请的用词过于夸大;(4）类别之间相似度高，对特征的表达能力要求高;(5）各个类别的专利数量严重不均衡，给分类带来巨大压力。

目前，专利审查员主要使用手工分类，少量借助机器对专利进行分类。对于手工分类，专利审查员需要逐篇阅读专利文献以确定分类号，这样做效率低、费用高，另外不同的人主观判断存在差别，导致分类效果一致性较差[2]。近年来，已有许多学者采用基于机器学习的方法对专利文本进行分类研究，主要采用基于词的特征和单一分类器进行分类。然而这种方法并没有很好地解决专利文本分类这样复杂的文本分类任务。因此，机器分类的准确率需要进一步提升，以辅助

专利审查员的分类工作。

本文构建了4种特征：全词典TFIDF特征、信息增益词典TFIDF特征、段落向量特征、主题模型向量特征。使用朴素贝叶斯(或高斯-朴素贝叶斯)、支持向量机、AdaBoost算法对4种特征分别训练得到12个分类器。从每一种特征对应的三个分类器中选取分类效果最好的分类器作为最优分类器。使用4个最优分类器的分类结果构建特征-类别矩阵，借助F1权重矩阵，对分类器进行集成，得到最终分类结果。

# 2相关研究

国内外一直非常重视对专利文本的利用和研究。使用机器学习方法对专利文本按IPC分类号进行分类已经有近20年的历史。IPC分类体系从上到下分为部、类、子类、组和子组5个级别。从1971年发布第一个版本，每5年更新一些子类以下的级别(组和子组)，最新IPC版本包含7万多个类别。

近年专利分类主要从三种角度展开研究工作:

(1）将主题模型应用在特征中，使特征包含主题分布的信息。例如，Venugopalan等4以自然语言处理为基础的分层技术，将太阳能光伏发电领域中10201项专利的主题与现实世界中的类别/主题进行概率映射;廖列法等[5提出使用LDA 主题模型对专利进行分类,实验证明LDA主题模型比KNN方法的准确率高 $10 \%$ 以上。

(2）神经网络和深度学习逐渐展露头角。马芳[2]使用标题和摘要，抽取H部10个相邻的小类1500 篇专利，利用径向基网络分类，准确率达到 $7 2 . 2 \%$ 。马双刚选取计算机领域的发明专利，使用SVM对从自动编码器抽取的特征进行分类，准确率比传统的SVM提高 $3 . 2 5 \%$ ○

(3)随着专利数据量逐年增加，并行化算法的研究得到重视。孔旗提出 M3-SVM算法，在大规模、不均衡数据集进行实验，精确率、召回率和F1测度三个指标都取得了比传统SVM更好的效果。

很多其他研究工作也共同丰富着专利分类方法。

例如：刘桂锋等[3]提出基于概率超图的半监督的方法，在少量标记样本的情况下得到理想的分类效果。缪建明等8借助专利层次结构特点，仅使用摘要进行快速自动分类，大大提高了时效性。

在已有研究的基础上，本文构建4种特征：全部词的词典，以TFIDF为权重，构建代表全体词特征的DICTFIDF特征；通过信息增益算法构建信息增益词典，以 TFIDF为权重，构建代表关键词信息的 $\mathrm { I G } _ { - }$ TFIDF特征；训练段落向量，构建代表语义信息的DocumentVector特征；训练LDA，得到代表专利主题的Topic ModelVector特征。基于以上4组特征，分别训练NB、SVM、AdaBoost分类器。根据分类效果挑选最优分类器，构建特征-类别矩阵，并结合F1权重矩阵实现专利文本自动分类。

# 3基于多特征分类器集成的专利文本分类

系统整体框架如图1所示，分为4个部分：预处理；构建4种分类器；选择最优分类器(框中S、N、A分别表示SVM、NB、AdaBoost分类器)；分类器集成。

# 3.1 预处理

从美国专利及商标局下载的数据是以周为单位的XML 格式文件，解析成TXT格式文本，存入MySQL数据库。抽取发明名称、摘要、权利要求、详细说明、申请人、发明人等信息，对其进行分词、共指消解①、词干还原等预处理

# 3.24组特征的构建

本文构建4组特征，分别如下：

(1）针对预处理后的数据统计词典，每篇专利按照词典顺序构建词频矩阵。根据词频矩阵计算 TFIDF③值，得到代表全局信息的全词典的TFIDF权重的特征向量。

(2)使用信息增益的方法，计算每个词对系统贡献值，从大到小排列。根据对比实验，选择前4351个词。以此构建信息增益词典、词频矩阵，进而计算TFIDF值。根据以上信息得到代表关键词信息的信息增益词典的TFIDF权重特征向量。

![](images/ac59022696ad0276b30f0778b394e273fc31934a7d8a57cd84c04f9bfc58e6ee.jpg)  
图1系统整体设计框架

(3）由于词袋模型有两点主要的缺陷：丢失了词与词之间顺序的特征；忽略了词的语义信息。因此为每篇专利设计了包含语义的段落向量(DocumentVector)。

Le等[使用段落向量的分布式记忆模型(Distributed Memory Model of Paragraph Vector)训练段落向量。段落向量模型在 Word2Vec 模型[10-11]基础上增加一个段落向量，同时将每个段落、每一个词映射为唯一的向量，如图2所示。

![](images/b2fc13fd97ec77f16c34f1afbebda4968811c4d6616ace45124a5352e1c45ad3.jpg)  
图2段落向量算法示意图[9]

例如，训练两个段落"there are many animals inthisroom"和"thecatsatontable"，形成 50 维的段落向量和50维的词向量。训练阶段：首先初始化一个2行50列的D矩阵、12行50列的W矩阵和Softmax的参数。当使用"the”、“cat”、“sat"预测下一个词时，从D中抽取出第二段对应的1个段落向量、W中抽取出“the”、“cat”、“sat"对应的3个词向量，这4个向量求平均(或求和)，使用层次化的Softmax预测下一个词。整体使用随机梯度下降的方法训练，得到D、W、Softmax的参数。推理阶段：模型的W矩阵和Softmax的权重已固定，通过随机梯度下降获得新段落的段落向量。

(4）由于每篇专利的主题不同，为专利文本设计了基于主题模型的主题向量。基于主题模型的LDA算法[12]，使用所有训集语料训练主题模型。由于LDA不仅限于“见过"的数据，可以通过训练好的主题模型得到一篇新文章的主题向量，并且相似主题的专利的主题向量也相似。

# 3.3 分类器集成

使用朴素贝叶斯、支持向量机和AdaBoost算法训练分类器，对4组特征分别训练。训练完成后，对测试集进行预测。在每一组特征所对应的三个分类器中，选择分类效果最好的作为该特征的最优分类器，共计4个。

设训练集有 $N$ 个类别: $\left\{ w _ { 1 } , w _ { 2 } , \cdots , w _ { N } \right\} ,$ $M$ 个最优分类器： $\left\{ C _ { 1 } , C _ { 2 } , \cdots , C _ { M } \right\}$ 。对于任意一个输入样本 $x$ ，令 $P _ { n } ^ { m } ( x )$ 表示使用最优分类器 $C _ { m }$ 计算该篇专利属于$w _ { n }$ 的归一化后的值。全部的 $P _ { n } ^ { m } ( x )$ 组成 $M$ 行 $N$ 列的矩阵：特征-类别概率矩阵 $R ( x )$ 如公式(1)所示，其中$R ( x )$ 的每列都对应一个类别，每行也对应一个特征的最优分类器：

$$
R ( x ) = \left( \begin{array} { c c c c } { { P _ { 1 } ^ { 1 } ( x ) } } & { { P _ { 2 } ^ { 1 } ( x ) } } & { { \cdots } } & { { P _ { N } ^ { 1 } ( x ) } } \\ { { P _ { 1 } ^ { 2 } ( x ) } } & { { P _ { 2 } ^ { 2 } ( x ) } } & { { \cdots } } & { { P _ { N } ^ { 2 } ( x ) } } \\ { { \cdots } } & { { \cdots } } & { { \cdots } } & { { \cdots } } \\ { { P _ { 1 } ^ { M } ( x ) } } & { { P _ { 2 } ^ { M } ( x ) } } & { { \cdots } } & { { P _ { N } ^ { M } ( x ) } } \end{array} \right)
$$

首先，对于确定最优分类器对各类别预测结果的准确性这个问题，使用最优分类器对各类别进行分类的概率值归一化后结果 $P _ { n } ^ { m } ( x )$ 作为准确性的衡量标准。分类器的决策依据是：每个类别计算出相应的概率值越高，则属于该类别的可能性越高。

其次，对于多个分类器如何获得更好的集成效果的问题，不同最优分类器对不同类别的预测倾向不同，使用每个最优分类器对各类别的F1值作为细粒度权重。例如，最优分类器1认为样本 $x$ 属于类别1的可能性为 $P _ { 1 } ^ { 1 } ( x )$ ，类推得到该样本属于每种类别的概率值。记概率最大值对应类别为预测值，统计测试集样本的预测值和真实值，得到每个分类器对每个类别的F1值。由于F1值同时兼顾召回率和精确率两个指标,常用来衡量分类器分类效果，因此使用F1值作为分类器集成的权重。

F1权重矩阵如公式(2)所示。

$$
F 1 = \left( \begin{array} { l l l l } { F _ { 1 } ^ { 1 } } & { F _ { 1 } ^ { 2 } } & { \cdots } & { F _ { 1 } ^ { M } } \\ { F _ { 2 } ^ { 1 } } & { F _ { 2 } ^ { 2 } } & { \cdots } & { F _ { 2 } ^ { M } } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { F _ { N } ^ { 1 } } & { F _ { N } ^ { 2 } } & { \cdots } & { F _ { N } ^ { M } } \end{array} \right)
$$

其中， $F _ { N } ^ { M }$ 表示最优分类器 $M$ 将样本分到第 $N$ 类别的F1值。

使用本文的多特征多分类器集成算法(Multi-Feature Multi-Classifier Integration,MFMCI)，累加每个分类器对其预测结果的概率值( $P _ { n } ^ { m } ( x )$ )与相应F1权重( $\cdot F _ { n } ^ { m }$ )的乘积。 $F _ { n } ^ { m } \times P _ { n } ^ { m } ( x )$ 表示有 $F _ { n } ^ { m }$ 的可能性，认为分类器 $\mathbf { \nabla } _ { m }$ 将样本 $x$ 分到类别 $n$ 是正确的，也是分类器 $m$ 在多分类器集成中的贡献值。则 $S _ { n } ( x )$ 计算如公式(3)所示。

$$
\begin{array} { l } { S _ { n } ( x ) = R ( x ) \cdot F { \mathrm { 1 } } } \\ { \displaystyle \qquad = \sum _ { m = 1 } ^ { M } F _ { n } ^ { m } \times P _ { n } ^ { m } ( x ) , n = 1 , 2 , \cdots , N } \end{array}
$$

其中, $M$ 为最优分类器的个数， $N$ 为训练集中类别总数。

# 4实验设计

# 4.1实验语料和实验环境

专利数据下载自美国专利及商标局①(UnitedStates Patent and Trademark Office)，为 2014 年-2016年"发动机或泵"(Engine andPump)领域的专利申请书。选择子类专利总数超过800 篇的类别，从而得到F01L、F01N、F02B、F02C、F02D、F02M、F03D、F04B、F04C、F04D共10类，总计8000篇专利数据其中5500篇作为训练集，2500篇作为测试集。

实验使用三台CentOS764bit 操作系统、内存16GB的计算机。利用Python 和Java 语言，在PyCharm和Eclipse下编写程序并完成测试。整个实验阶段使用 sklearn、Stanford CoreNLP、gensim、NLTK等依赖库。

# 4.2 评估方法和评价标准

以经典的准确率、召回率、F1值和精确率作为评价标准。由于每篇专利的IPC分类号非唯一，所以使用三种不同的评估方法，如图3 所示。Fall 等[13]也使用了这种评估方法。其中TopPrediction指分类器给出的第一预测值与第一真实值进行匹配;Two Guesses 是分类器前两个预测值与第一真实值进行匹配；AllCategories 表示分类器给出第一预测值，与前三真实的分类号进行匹配。

![](images/b42bf7261c66046ab821de7d04f84a7f85929c7d3487b9a5cacd1f5d0e137e9f.jpg)  
图3评估方法[13]

# 4.34组特征的构建结果

预处理后所有训练语料的词作为词典(45432维)。构建每篇专利的基于全词典的词频向量矩阵，计算TFIDF权重，得到全词典TFIDF特征。

使用Python编写信息增益代码，计算每个词对整个系统的贡献值即信息增益值，得到4351维，部分结果如表1所示。

表1部分词信息增益值  

<html><body><table><tr><td>词(词干还原后)</td><td>信息增益值</td></tr><tr><td>Smoother</td><td>6.64337682087</td></tr><tr><td>vesda</td><td>6.64274815818</td></tr><tr><td>undamp</td><td>6.64274815818</td></tr><tr><td>engin</td><td>6.25488032208</td></tr></table></body></html>

训练段落向量时，分别以50、100、150和200维的段落向量进行实验，使用SVM对语料进行测试，最终选定100作为段落向量的维度。

使用LDA算法训练主题向量，需要根据数据特点确定主题的数量。由于样本共有10个类别，因此分别设计10、12、15、18和20个主题的对比实验，根据实验结果最终选择15作为主题向量的主题个数。

# 4.4选择最优分类器

每个特征训练三个分类器，分别是：朴素贝叶斯(NB)或高斯-朴素贝叶斯(Gaussian-NB)、支持向量机(SVM)和AdaBoost。由于全字典特征维数太高，只得到基于朴素贝叶斯分类器的分类效果。所有分类器表现效果如表2所示。

表2各分类器不同特征下表现效果  

<html><body><table><tr><td>分类算法</td><td>特征</td><td>评估方法</td><td>准确率</td><td>F1值</td><td>召回率</td><td>精确率</td></tr><tr><td>NB</td><td>全字典TFIDF</td><td>Top Prediction</td><td>71.4%</td><td>71.1%</td><td>71.4%</td><td>72.3%</td></tr><tr><td>NB</td><td>信息增益TFIDF</td><td>Top Prediction</td><td>43.9%</td><td>44.7%</td><td>43.9%</td><td>46.1%</td></tr><tr><td>SVM</td><td>信息增益TFIDF</td><td>Top Prediction</td><td>64.6%</td><td>64.4%</td><td>64.6%</td><td>68.0%</td></tr><tr><td>AdaBoost</td><td>信息增益TFIDF</td><td>Top Prediction</td><td>71.7%</td><td>71.9%</td><td>71.7%</td><td>72.9%</td></tr><tr><td>Gaussian-NB</td><td>段落向量</td><td>Top Prediction</td><td>23.3%</td><td>21.4%</td><td>23.3%</td><td>24.3%</td></tr><tr><td>SVM</td><td>段落向量</td><td>Top Prediction</td><td>48.4%</td><td>48.2%</td><td>48.4%</td><td>48.7%</td></tr><tr><td>AdabBoost</td><td>段落向量</td><td>Top Prediction</td><td>23.6%</td><td>23.6%</td><td>23.6%</td><td>24.1%</td></tr><tr><td>Gaussian-NB</td><td>主题向量</td><td>Top Prediction</td><td>39.7%</td><td>38.3%</td><td>39.7%</td><td>39.6%</td></tr><tr><td>SVM</td><td>主题向量</td><td>Top Prediction</td><td>41.7%</td><td>40.4%</td><td>41.7%</td><td>42.2%</td></tr><tr><td>AdaBoost</td><td>主题向量</td><td>Top Prediction</td><td>41.6%</td><td>40.8%</td><td>41.6%</td><td>40.7%</td></tr></table></body></html>

根据实验结果比对，每组选择分类效果最好的分类器作为该特征的最优分类器。全字典TFIDF选择朴素贝叶斯分类器，信息增益TFIDF特征选择AdaBoost分类器，段落向量特征选择SVM分类器，主题向量特征选择SVM分类器

# 5实验结果与分析

# 5.1 实验结果

不同特征组合与分类器集成的实验结果，如表 3所示。

表3不同特征组合与分类器集成的实验结果  

<html><body><table><tr><td>实验</td><td>评估方法</td><td>特征</td><td>算法</td><td>准确率</td><td>F1值</td><td>召回率</td><td>精确率</td></tr><tr><td>1</td><td>All Categories</td><td>I全字典 TFIDF</td><td>NB</td><td>73.6%</td><td>73.5%</td><td>73.6%</td><td>74.6%</td></tr><tr><td>2</td><td>All Categories</td><td>Ⅱ信息增益TFIDF</td><td>AdaBoost</td><td>74.0%</td><td>73.0%</td><td>74.0%</td><td>76.7%</td></tr><tr><td>3</td><td>All Categories</td><td>Ⅲ段落向量</td><td>SVM</td><td>49.4%</td><td>49.1%</td><td>49.4%</td><td>49.6%</td></tr><tr><td>4</td><td>All Categories</td><td>V主题向量</td><td>SVM</td><td>42.0%</td><td>41.3%</td><td>42.0%</td><td>41.6%</td></tr><tr><td>5</td><td>All Categories</td><td>I、II、IV直接拼接</td><td>Gaussian-NB</td><td>31.2%</td><td>30.8%</td><td>31.2%</td><td>31.6%</td></tr><tr><td>6</td><td>All Categories</td><td>II、IV特征直接拼接</td><td>SVM</td><td>34.4%</td><td>33.2%</td><td>34.4%</td><td>34.1%</td></tr><tr><td>7</td><td>All Categories</td><td>I、I、Ⅲ、IⅣ</td><td>投票</td><td>72.2%</td><td>73.5%</td><td>72.2%</td><td>74.0%</td></tr><tr><td>8</td><td>All Categories</td><td>I、ⅢI、IⅣ</td><td>MFMCI</td><td>54.1%</td><td>52.0%</td><td>54.1%</td><td>56.6%</td></tr><tr><td>9</td><td>All Categories</td><td>I、IⅢI、IV</td><td>MFMCI</td><td>79.4%</td><td>78.8%</td><td>79.4%</td><td>81.7%</td></tr><tr><td>10</td><td>All Categories</td><td>I、I、Ⅲ、Ⅳ</td><td>MFMCI</td><td>80.1%</td><td>79.5%</td><td>80.1%</td><td>82.4%</td></tr><tr><td>11</td><td>Top Prediction</td><td>I全字典 TFIDF</td><td>NB</td><td>71.4%</td><td>71.1%</td><td>71.4%</td><td>72.3%</td></tr><tr><td>12</td><td>Top Prediction</td><td>I信息增益TFIDF</td><td>AdaBoost</td><td>71.7%</td><td>71.9%</td><td>71.7%</td><td>72.9%</td></tr><tr><td>13</td><td>Top Prediction</td><td>Ⅲ段落向量</td><td>SVM</td><td>48.4%</td><td>48.2%</td><td>48.4%</td><td>48.7%</td></tr><tr><td>14</td><td>Top Prediction</td><td>V主题向量</td><td>SVM</td><td>41.7%</td><td>40.4%</td><td>41.7%</td><td>42.2%</td></tr><tr><td>15</td><td>Top Prediction</td><td>I、III、IⅣ直接拼接</td><td>Gaussian-NB</td><td>31.2%</td><td>30.8%</td><td>31.2%</td><td>31.6%</td></tr><tr><td>16</td><td>Top Prediction</td><td>I、I、Ⅲ、V</td><td>MFMCI</td><td>78.9%</td><td>78.2%</td><td>78.9%</td><td>81.2%</td></tr><tr><td>17</td><td>Two Guesses</td><td>I全字典 TFIDF</td><td>NB</td><td>88.1%</td><td>88.1%</td><td>88.1%</td><td>88.4%</td></tr><tr><td>18</td><td>Two Guesses</td><td>II信息增益TFIDF</td><td>AdaBoost</td><td>89.4%</td><td>89.2%</td><td>89.4%</td><td>89.8%</td></tr><tr><td>19</td><td>Two Guesses</td><td>Ⅲ段落向量</td><td>SVM</td><td>68.6%</td><td>68.5%</td><td>68.6%</td><td>68.7%</td></tr><tr><td>20</td><td>Two Guesses</td><td>V主题向量</td><td>SVM</td><td>61.8%</td><td>61.4%</td><td>61.8%</td><td>61.9%</td></tr><tr><td>21</td><td>Two Guesses</td><td>I、I、ⅢI、Ⅳ</td><td>MFMCI</td><td>91.2%</td><td>91.0%</td><td>91.2%</td><td>91.7%</td></tr></table></body></html>

# 5.2 实验结果分析

从单特征单分类器的实验结果(1-4、11-14、17-20)得到综合实验效果是：信息增益TFIDF特征最优分类器 $\therefore >$ 全字典 TFIDF 特征最优分类器 $: >$ 段落向量特征最优分类器 $\gtrdot$ 主题向量特征最优分类器。由此可见，对于单个特征而言，信息增益方法选择的特征包含信息量最大，主题向量特征包含的信息量最少。全字典特征总共有45432维，信息增益4351维，段落向量100维，主题向量仅仅15维，特征维数的差距巨大，是造成信息包含量不同的原因之一。然而，并不是特征维数越大，分类效果一定更好，段落向量特征选择100 维时的分类效果比200 维效果好。另外，由于特征维度的不同，不同算法的分类效果也不同。例如，全字典

45432维特征，使用贝叶斯分类效果最好。维度过高对于计算复杂度很高的SVM来说很难达到好的效果。因此设计每种特征分别训练三个不同算法的分类器，从中选择分类效果好的作为最优分类器。

由表3可以看出，采用本文算法在三种评估方法下都取得最好的准确率，All Categories 达到 $80 . 1 \%$ TopPrediction达到 $78 . 9 \%$ ,Two Guesses达到 $91 . 2 \%$ 。由此可以得到4点结论：

(1）4种特征包含的信息量远大于单个特征的信息。4种特征包含全局单词的信息(全词典)、关键词信息(信息增益)、关于语义的信息(段落向量)、篇章主题的信息(主题向量)。多特征使得对专利信息的描述更具全局化和立体化，效果比片面的局部的特征分类效

果好。

(2）信息增益TFIDF特征是从全字典中提取出的关键词特征。从实验1-2、11-12、17-18看到，信息增益TFIDF最优分类器的分类效果比全词典好。但从实验8-10结果分析，全字典特征更能代表全局信息，而信息增益则相对局部。此外，它们对一篇专利的预测概率以及集成时的F1值完全不同，如表4所示。因此在集成过程中，全词典的全局信息是对信息增益的局部信息的补充。所以，两者与其他两种特征的最优分类器的集成效果会远远好于其中一者与其他两种特征最优分类器的集成效果。

表4全词典TFIDF最优分类器和信息增益TFIDF最优分类器的区别  

<html><body><table><tr><td rowspan="2">IPC 分类号</td><td colspan="2">F1值</td><td colspan="2">对某篇专利预测概率值</td></tr><tr><td>全词典 TFIDF 最优分类器</td><td>信息增益 TFIDF 最优分类器</td><td>全词典 TFIDF 最优分类器</td><td>信息增益 TFIDF 最优分类器</td></tr><tr><td>F01L</td><td>86.1%</td><td>83.4%</td><td>66.5%</td><td>11.342%</td></tr><tr><td>F01N</td><td>78.1%</td><td>74.2%</td><td>0.6%</td><td>10.001%</td></tr><tr><td>F02B</td><td>59.8%</td><td>53.8%</td><td>10.9%</td><td>10.019%</td></tr><tr><td>F02C</td><td>76.0%</td><td>87.2%</td><td>0.6%</td><td>9.588%</td></tr><tr><td>F02D</td><td>67.1%</td><td>58.3%</td><td>9.6%</td><td>10.022%</td></tr><tr><td>F02M</td><td>57.7%</td><td>50.6%</td><td>3.2%</td><td>10.006%</td></tr><tr><td>F03D</td><td>94.1%</td><td>96.4%</td><td>0.3%</td><td>9.035%</td></tr><tr><td>F04B</td><td>72.6%</td><td>75.6%</td><td>7.1%</td><td>10.004%</td></tr><tr><td>F04C</td><td>74.7%</td><td>77.2%</td><td>1.0%</td><td>9.992%</td></tr><tr><td>F04D</td><td>69.0%</td><td>62.7%</td><td>0.3%</td><td>9.989%</td></tr></table></body></html>

(3）并不是4 种特征随便结合到一起就可以提高分类效果，从表3中实验5和实验6得到，将特征直接拼接，分类效果急剧下降。这种做法是无效的，只有将特征有机结合才能更好地发挥各自的优势。

(4)本文算法不是对多个特征分类器的简单投票，对比实验7和实验10发现，想要有机结合多个特征分类器，需要抓住各自特征分类的优势，在有优势的地方加大权重，在劣势的地方给予低的权重。结合F1权重矩阵与特征-类别概率矩阵，最终得到更好的分类效果。

马芳[2]使用径向基神经网络对专利自动分类(记为RBFNN)，本文工作与其都是将专利分到小类级别的10 个类，相对具有可比性。本文比马芳的使用径向基神经网络的分类效果好，结果如表5所示。

表5本文与其他工作效果对比  

<html><body><table><tr><td>算法</td><td>标准</td><td>准确率 F1值</td><td>召回率</td></tr><tr><td>RBFNN(径向基网络）Top Prediction</td><td></td><td>72.2% 70.7%</td><td>71.0%</td></tr><tr><td>MFMCI(本文算法)</td><td>Top Prediction</td><td>78.9% 78.2%</td><td>78.9%</td></tr><tr><td>MFMCI(本文算法)</td><td>All Categories</td><td>80.1% 79.5%</td><td>80.1%</td></tr><tr><td>MFMCI(本文算法)</td><td>Two Guesses</td><td>91.2%</td><td>91.0% 91.2%</td></tr></table></body></html>

MFMCI对各个类别的预测效果如表6所示。

表6MFMCI对各个类别的预测效果  

<html><body><table><tr><td>IPC分类号</td><td>F1值</td><td>召回率</td><td>精确率</td></tr><tr><td>F01L</td><td>86.21%</td><td>98.8%</td><td>76.5%</td></tr><tr><td>F01N</td><td>85.60%</td><td>86.8%</td><td>84.4%</td></tr><tr><td>F02B</td><td>66.67%</td><td>53.2%</td><td>89.3%</td></tr><tr><td>F02C</td><td>82.93%</td><td>81.6%</td><td>84.3%</td></tr><tr><td>F02D</td><td>73.31%</td><td>95.6%</td><td>59.5%</td></tr><tr><td>F02M</td><td>64.99%</td><td>51.6%</td><td>87.8%</td></tr><tr><td>F03D</td><td>91.01%</td><td>97.2%</td><td>85.6%</td></tr><tr><td>F04B</td><td>79.29%</td><td>71.2%</td><td>89.5%</td></tr><tr><td>F04C</td><td>84.54%</td><td>90.8%</td><td>79.1%</td></tr><tr><td>F04D</td><td>80.87%</td><td>74.4%</td><td>88.6%</td></tr></table></body></html>

从表6中可以看出,MFMCI对F01L、F01N、F02C、F03D、F04C、F04D等类的分类效果比较好，F1值都超过了 $80 \%$ 。而对F02B、F02D、 $\mathrm { F } 0 2 \mathrm { M }$ 、F04B等类的分类效果不好，究其原因有以下两点：

(1）这10个类别有非常多的交叉和相似之处，例如最新的IPC国际专利分类标准记载：F02B：活塞式内燃机；一般燃烧发动机(其循环操作阀入F01L；内燃机润滑入F01M；其气流消音器或排气装置入F01N;内燃机的冷却入F01P；燃气轮机入F02C；利用燃烧生成物的发动机装置人F02C,F02G)。F02B代表"活塞式内燃机；一般燃烧发动机”。但是如果是燃气轮机就要转入F02C，若专利是利用燃烧生成物的发动机装置也被转入F02C。

(2）部分专利申请人为了扩大自己专利的权利范围，故意在申请书中扩大用词。针对这种情况，机器很难仅仅借助文本对专利进行有效分类，在以后的工作中，可以考虑引入专利申请中的图像的特征来提高效果。

# 6结语

本文提出一种多特征多分类器集成的专利自动分类算法。该方法以全局词特征(全词典 TFIDF 特征)、关键词特征(信息增益TFIDF特征)、语义特征(篇章向量特征)、主题特征(主题向量特征)，分别训练属于每个特征最好的分类器作为最优分类器，构建特征-类别概率矩阵，结合F1权重矩阵，对发动机或泵领域的10个子类进行分类。与单特征、直接串联特征、多特征分类器直接投票、以及马芳的径向基神经网络方法的分类效果进行对比，能够取得较好结果。

本文的不足以及未来工作主要有：对于专利申请人故意扩大用词的情况可以借助专利申请中的图像辅助分类；本文使用了近三年的专利，数量不足以支撑完成组和子组级别的分类。未来研究可以使用2001年至今近17年的专利数据，结合分布式分类算法，对专利进行更深层次的分类，以进一步提高分类准确率。

# 参考文献：

[1] 蔡虹，蒋仁爱，吴凯．知识产权保护对中国技术进步的贡 献研究[J]．系统管理学报,2015,24(3):314-320.(Cai Hong, Jiang Renai,Wu Kai. Contribution of Intellectual Property Protection to the Technological Progresses in China [J].Journal of Systems & Management，2015，24(3): 314-320.)   
[2] 马芳．基于 RBFNN 的专利自动分类研究[J].现代图书情 报技术，2011(12):58-63.(Ma Fang.Research of Patent Automatic Classification Based on RBFNN [J].New Technology of Library and Information Service,2o11(12): 58-63.)   
[3] 刘桂锋，汪满容，刘海军．基于概率超图半监督学习的专 利文本分类方法研究[J]．情报杂志,2016，35(9)：187-191, 173.(Liu Guifeng,Wang Manrong,Liu Haijun.Probabilistic Hypergraph Based Semi-supervised Learning Method for Patent Document Categorization[J].Journal of Intelligence, 2016,35(9): 187-191,173.)   
[4] Venugopalan S,Rai V.Topic Based Classification and Pattern Identification in Patents[J]. Technological Forecasting and Social Change,2015,94:236-250.   
[5] 廖列法，勒孚刚，朱亚兰.LDA 模型在专利文本分类中的 应用[J]．现代情报，2017，37(3):35-39.(Liao Liefa，Le Fugang,Zhu Yalan.The Application of LDA Model in Patent Text Classification[J]. Journal of Modern Information,2017, 37(3): 35-39.)   
[6] 马双刚．基于深度学习理论与方法的中文专利自动分类研 究[D]．镇江：江苏大学,2016.(Ma Shuanggang.The Study of Automatic Chinese Patent Classification Based on Deep Learning Theory and Method [D]. Zhenjiang: Jiangsu University,2016.)   
[7]孔旗．基于并行机器学习的大规模专利分类[D]．上海：上 海交通大学，2011．(Kong Qi．Large-scale Patent Classification Based on Parallel Machine Learning [D]. Shanghai: Shanghai Jiaotong University,2011.)   
[8] 缪建明，贾广威，张运良．基于摘要文本的专利快速自动 分类方法[J]．情报理论与实践，2016,39(8):103-105，91. (Miu Jianming,Jia Guangwei,Zhang Yunliang.The Rapid Automatic Categorization of Patent Based on Abstract Text [J].Information Studies:Theory & Application,2016,39(8): 103-105,91.)   
[9]Le QV,Mikolov T.Distributed Representations of Sentences and Document[OL].arXiv Preprint,arXiv:1405.4053.   
[10]Mikolov T.Statistical Language Models Based on Neural Networks[D].Brno University of Technology,2012.   
[11]Turian J,Ratinov L,Bengio Y.Word Representations:A Simple and General Method for Semi-supervised Learning [C]//Proceedings of the 48th Annual Meeting of the Association for Computational Linguistics.201o:384-394.   
[12]Rosen-Zvi M，Griffiths M，Steyvers M，et al.The Author-topic Model for Authorsand Documents[C]// Proceedings of the 2Oth Conference on Uncertainty in Artificial Intelligence.2012: 487-494.   
[13]Fall C J,Törcsvari A，Benzineb K，et al.Automated Categorization in the International Patent Classification[J]. ACM SIGIR Forum,2003,37(1):10-25.

# 作者贡献声明：

贾杉杉：提出研究思路，设计研究方案，进行实验，起草论文;  
彭涛：采集、清洗和分析数据;  
刘畅，孙连英，刘小安，彭涛：论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: pengtao@buu.edu.cn。  
[1]贾杉杉，刘畅，孙连英，刘小安，彭涛．内在数据详细信息.  
doc.研究方法和工具直接描述、样本数据下载地址.  
[2]贾杉杉，刘畅，孙连英，刘小安，彭涛．附件-表2和表3原始实验结果.txt.直接研究结果数据.

收稿日期:2017-05-31   
收修改稿日期:2017-08-15

# Patent Classification Based on Multi-feature and Multi-classifier Integration

Jia Shanshan'Liu Chang²Sun Lianying³Liu Xiaoan1Peng Tao² 1(College of Intellectualized City, Beijing Union University, Beijing 100101, China) ²(College of Robotics,Beijing Union University,Beijing 100101, China) 3 (College of Urban Rail Transit and Logistics, Beijing Union University, Beijing 100101, China)

Abstract:[Objective]This paper aims to automatically allcate correct IPC to patent applications with the helpof multi-featureand multi-clasifier integrationmethod.[Methods]First，we extracted the TFIDF features of all dictionaries and information gains,as wellas the vector features ofdocument and topic models from patent applications. Then,weused the collected data to train the NB,SVM,and AdaBoost classifiers.Finally，we established the feature-class matrix and predicted the final IPC with the F1 weight matrix.[Results]We examined our new method with 10 patent classs from 2014 to2016 in thefieldof engine and pump.Theaccuracyof top prediction,allcategories, and two guesses were $78 . 9 \%$ ， $80 . 1 \%$ and $91 . 2 \%$ respectively. [Limitations] The size of training corpus is limited, which only includes 3 years patent data.[Conclusions] The proposed method could efectively improve the accracyof patent classification in the field of engine and pump.

Keywords:Patent Classification Document VectorTopic Model Vector Classifier Integration

# 国家纳米科学中心、中国科学院文献情报中心、施普林格·自然联合推出中国纳米科学与技术发展白皮书

北京国际会议中心举办的2017年中国国际纳米科学技术会议上，国家纳米科学中心、中国科学院文献情报中心和施普林格·自然集团(Springer Nature)联合发布了《国之大器始于毫末——中国纳米科学与技术发展状况概览》中英文白皮书。

中国投入进行纳米科研已有数十年时间，已经成为当今世界纳米科学与技术进步重要的贡献者，部分基础研究居国际领先水平，中国纳米科技应用研究与成果转化的成效也已初具规模。这些都与中国在纳米科技领域的持续投入密切相关。中国纳米科技研究正在向原创性突破转变，并更加关注纳米科技的产业化应用。

白皮书分别从原创论文数量、Nano 数据库和专利产出这三个方面，将中国与世界其他主要纳米科研强国进行了对比，揭示了中国纳米科研的优势与发展特点。白皮书还通过业内专家访谈，探讨了中国纳米科学的发展前景和未来面临的挑战。

中国科学院院长、党组书记白春礼指出，从计量学角度在对纳米科技成果分析的基础上，进一步关注纳米专利技术的应用情况，关注纳米研发的投入成效，更深入地揭示和把握纳米科技的发展态势。

(1）中国纳米科技论文：产出数量和质量均有大幅提升;  
(2)Nano数据库彰显中国纳米研究的优势与侧重;  
(3）中国纳米专利：数量全球第一，但多为本国专利。

白皮书指出，科研产出和专利申请数量上的迅速增长，都描绘出中国纳米科学美好的发展前景。不论是传统的强项学科，还是新兴领域，中国纳米科学都表现出巨大的潜力。

(本刊讯)