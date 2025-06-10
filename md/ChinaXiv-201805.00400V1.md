# 多类型分类器融合的文本分类方法研究

李惠富，陆光†

(东北林业大学 信息与计算机工程学院，哈尔滨 150040)

摘要：传统的文本分类方法大多数使用单一的分类器，而不同的分类器对分类任务的侧重点不同，就使得单一的分类方法有一定的局限性，同时每个特征提取方法对特征词的考虑角度不同。针对以上问题，提出了多类型分类器融合的文本分类方法。该模型使用了word2vec、主成分分析、潜在语义索引以及TFIDF 特征提取方法作为多类型分类器融合的特征提取方法。并在多类型分类器加权投票方法中忽略了类别信息的问题，提出了类别加权的分类器权重计算方法。通过实验结果表明，多类型分类器融合方法在二元语料库、多元语料库以及特定语料库上都取得了很好的性能，类别加权的分类器权重计算方法比多类型分类器融合方法在分类性能方面提高了 $1 . 1 9 \%$ 。

关键词：文本分类；分类器融合；主成分分析；潜在语义索引 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.09.0908

# Research on text classification method of multi-class classifier fusion

Li Huifu, Lu Guang† (Collegeof Computer& Engineering,Northeast Forestry University,Harbin150o40,China)

Abstract: Mostofthe traditional textclasification methodsuseasingleclassfier,anddiferentclassfers havediferent emphasisonclasification tasks,which makes the single classfication method have some limitations.At thesame time,each feature extraction method has diferentanglesofconsidering the feature words.Aiming at the above problems,this paper proposes atextclasification method based on multi type clasifier fusion,which combines Word2ve,Principal Component Analysis,Latent Semantic IndexingandTFIDF featureextraction as feature extraction methods forthe multi type classifier fusion.The weighted voting method ofmultitype classfier ignores thecategory information.This paper proposes a weighted clasifier weightcalculation method.Theexperimentalresults showthatthe multiclasifierfusionmethodhasachieved good performance both in two dimensional,multiple corporaand corpus specificcorpus,the classification weighting methodof classifier weighting improves the classification performance by $1 . 1 9 \%$ compared with the multi type classifier fusion method.

Key Words: text classification; classifier fusion; principal component analysis; potential semantic index

# 0 引言

随着互联网的逐渐成熟和微博等社交网络的发展，以信息技术的革命极大了改变了人们的生活方式，越来越多的用户通过网络发布信息和评价实时信息，这些信息的主题类别包括色情、邪教、毒品在内的各种有害信息[1]。因此，如何有效的管理信息对互联网的发展是有重要意义的。

机器学习中的文本分类方法是处理和管理文档数据的关键技术[2]。研究者对文本分类方法进行了广泛的研究。例如，利用K最近邻（KNN）方法的简单、无参数等优点对文本垃圾短信分类[3]。Goudjil等人[4]通过使用SVM分类器提供的后验概率来选择样本，利用选择的样本进行分类。在文献[5中，使用训练数据中深度计算特征加权频率来估计贝叶斯的条件概率，提高

了分类的性能。

上述研究方法都取得了很好的分类效果。但是，KNN方法中的 $K$ 值是人工设置的，具有很大的客观性。SVM中如何确定高维空间的核函数是目前难点之一。贝叶斯分类中，特征计算时假设特征之间相互独立，而现实中的特征之间是有联系的。上述方法都是采用单一的分类器对文本进行分类，而文本数据涉及的领域非常广，这使得单一分类器不能很好的覆盖更多的领域。因此，本文引进了多分类器融合的文本分类方法。

文本分类是将文本内容相似的文档分配到一个或多个预定义的类别中，而特征提取方法在提高分类器的性能方面有重要的作用[6]。如，文献[7]中，利用动能定理和TFIDF 特征提取方法来解决微博主题检测问题。文献[8]中，利用word2vec作为自动特征提取工具，然后利用句子向量来完成分类。Santosh等人[9]利于特征本体树和LDA 作为在线产品评论文本的特征提取方法，能更好的识别意见词。Uysal等人[10]使用遗传算法和LSI相结合的方法能更好的获取文档的特征向量，能更好的完成分类任务。

上述特征提取方法研究中，都在各自的分类任务中取得了良好的效果。但是，TFIDF方法只考虑了词语的的统计指标，没有考虑到特征词的语义知识。LSI方法只考虑了特征词之间的语义关系。word2vec 没有考虑特征词的统计特征。LDA没有将类别信息加入到主题模型中。上述方法都是单一的特征提取方法并且每个特征提取方法的侧重特征词不同，所以上述方法有一定的局限性。因此，为了能更好的表示文本的特征，本文使用融合的特征提取方法。

综上所述，针对文本分类器和特征提取方法比较单一的问题，本文提出了多类型分类器融合的文本分类方法。并针对分类器加权投票决策方法中没有考虑到分类器对每个类别的贡献度不同的问题，提出了一个类别加权的分类器权重计算方法。

# 1 多类型分类器融合的文本分类

多类型分类融合的方法是通过融合不同的特征提取方法使得特征空间向量中的特征词更加丰富，通过融合多特征提取方法使文本的表现形式更加丰富，然后通过使用分类器进行文本分类。本文多类型分类融合的方法包含了以下特征提取方法：word2vec；TF-IDF(词频-逆文档频率)；主题模型(latentDirichletallocation,LDA)；潜在语义索引(latent semantic indexing,LSI);

# 1.1特征提取方法

# 1.1.1 word2vec 词向量

在2013年，Mikolov 等人提出了一种word2vec 的开源软件[11]。Word2vec(word to vector)方法通过神经网络方法将单词转换为词向量。在训练词向量的过程中，首先提取出训练数据集中的词语生成词语表，通过使用CBOW或者Skip-Gram模型来得出每个词语的词向量，模型示意图如图1所示。

![](images/df1d563a3afe48fd8368de36704c34baf6d3811c8a1b2d9f4aad0810fc98f05b.jpg)  
图1CBOW 和 Skip-Gram 模型

在图1中显示，CBOW和Skip-Gram 模型是一个反向的过程。CBOW模型是利用待预测词前后各 $t$ 个词去预测当前词，而 Skip-Gram 模型是利用当前预测词去预测前后各t个词。由于本文使用了CBOW模型，所以本文详细介绍了CBOW模型。

CBOW模型是一种利用上下文的信息来预测当前词语出现概率的模型。该模型是一个三层的神经网络，分别为输入层、隐藏层和输出层。输入层是输入词向量，

该词向量为随机值，通过训练数据不断更新词向量。隐藏层是对词向量进行累加。输出层输出词语的概率。

1.1.2 TF-IDF

TF-IDF 是经典的特征权值计算方法，TF-IDF由TF(词频)和 $I D F$ (逆文档频率)构成的，公式如下：

$$
{ t f i d f } \left( \boldsymbol { w } \right) = { t f } \left( \boldsymbol { w } \right) \times i d f \left( \boldsymbol { w } \right)
$$

其中： $t f ( w )$ 为单词 $w$ 在文本中出现的次数， $i d f ( w )$ 为单词 $w$ 的逆文档频率， $i d f ( w )$ 的计算方法如式（2）所示。

$$
i d f \left( w \right) = \log { \frac { A } { B \left( w \right) } }
$$

其中： $A$ 代表训练集中文本总的数量， $B ( w )$ 代表包含该词语 $w$ 的文件数量。

1.1.3LDA

LDA是一种主题模型，是词-文档-主题的三层贝叶斯模型。主题模型通过训练集训练得出主题的Dirichlet分布和主题与词之间的多项式分布函数。该方法首先确定一个主题，然后在主题中选择一个单词直到遍历所有的单词，LDA模型如图2所示。

![](images/4020b098ba6b50d44c6a7f8e5f99b79e24caa08d2ecd490c942c03fbd7ea2ce7.jpg)  
图2LDA模型

图中， $W$ 代表文本中的单词； $N$ 代表文本中的单词； $M$ 代表文本的数量；L代表参数值 $D$ 的多项分布； $P 2$ 代表Dirichlet分布的先验参数，表示词 $W$ 的概率; $D$ 代表以 $P 1$ 参数的Dirichlet主题分布； $P 1$ 是 $D$ 的参数;

# 1.1.4 LSI

LSI是一种无监督的数据挖掘技术，针对一词多义等语义问题有很好的效果。在潜在语义索引方法中，使用奇异值分解方法分解特征向量空间来达到降维的目的，算法模型如图3所示。

![](images/526c7b40ae77d787ae09467a38aa2154aa3fa4cda0357ba213af544ea36c18a0.jpg)  
图3潜在语义索引模型示意图

# 1.2多类型分类器融合

通过1.1节的特征提取方法计算使得产生了4组不同的特征向量空间。第一个是由CBOW方法产生的word2vec的向量空间，第二个是利用TFIDF产生的向量空间，第三个是LSI产生的语义向量空间，最后一个是利用主题模型产生的LDA 向量空间。多类型分类器融合的方法是利用特征提取方法产生向量空间之间的互补性。多类型分类器方法模型如图4所示，三角形中的数字为分类器的权重。

![](images/92ff97a87a46a4a8beb053ace040841dfaeef34f20e68ff87a522ae15c999766.jpg)  
图4多类型分类器融合示意图

# 1.3类别加权多类型分类器融合

多分类器融合可以利用不同分类器来完成不同的任务，从而避免考虑不全面的问题，不同分类器对同一样本的分类能力不同，因此，每个分类器对每个样本都有不同的贡献能力，分类器加权投票方法是作为组合分类器投票决策的方法之一[12]。分类性能(训练完的样本对训练样本的正确识别率)作为分类器加权投票方法有如下优点：不同分类器对同一样本的识别率是不同的，当组合分类器进行分类决策时，分类结果倾向与分类性能好的分类器，使得决策的性能最好。因此，本文使用分类性能作为分类器的权重。分类性能公式如式（3）（4）所示。

$$
\varepsilon = \frac { e r r o r N u m } { t e x t N u m }
$$

$$
\alpha = \ln \left( \frac { 1 - \varepsilon } { \varepsilon } \right)
$$

其中：errorNum为分类器未正确分类的样本数目；textNum为样本数据集中样本的总数量； $\scriptstyle a$ 为分类器对数据集的权重。

图5为传统的二元分类样本示意图，图中一共有100个数据点，每个类别有40个训练数据点，每个类别有10个测试数据点，其中·代表训练数据类别1， $\times$ 代表训练数据类别2，△代表测试数据类别2中的测试数据，<为测试数据类别1中的测试数据。本部分用KNN和多项式贝叶斯作为分类算法，分类性能作为分类器权重。通过KNN方法得到了ε为0.0375， $\alpha$ 等于3.2452，多项式贝叶斯方法得到了ε为0.9625， $\alpha$ 等于2.5123。因此可知，KNN分类器权重为3.2452，多项式贝叶斯分类器权重是2.5123。KNN方法的错误样本个数为12个，多项式贝叶斯方法的错误样本个数为10个，当测试样本点输入组合分类中时，根据投票原则可得该组合方法的错误测试样本个数为12个，即是KNN方法的错误率。这种方法只是将整个分类器的分类性能作为分类器的权重，忽略了类别对分类器的影响。因此，本文提出了类别加权的分类器权重计算方法。

![](images/e2453ecf37878c5ff5b7eb1f15b113e1a9c9260ff926141d8096c0dc3e882667.jpg)  
图5二元分类样本示意图

类别加权分类器是考虑类别信息对分类器权重的影响。在上述组合分类器中，KNN分类性能中包含了1个负类样本和2个正类样本。多项式贝叶斯分类性能中包含了6个负类样本。通过上述分析得到，多项式贝叶斯分类器对正类样本有好的识别率，所以想增加多项式贝叶斯正类样本的权重，减少负类样本的分类器权重。因此，本文以不同样本的类别赋予不同的分类器权重。类别加权分类器公式如式(5)所示。通过式(5)计算可以得出，KNN的正类的 $\boldsymbol { \varepsilon }$ 为0.05，负类的 $\boldsymbol { \varepsilon }$ 为0.025，正类的$\scriptstyle a$ 是2.9444，负类的 $\scriptstyle a$ 是3.6636。多项式贝叶斯的正类 $\boldsymbol { \varepsilon }$ 为0,负类的ε为0.15，正类的 $\scriptstyle a$ 是10(表示无穷大)，负类的 $\scriptstyle a$ 是1.7346。KNN和多项式贝叶斯组合方法当测试样本为正类的时候，多项式贝叶斯起到很好的作用，当测试样本为负样本时，KNN方法对组合分类器的影响较大，根据投票原则得出了该组合方法的错误样本个数为9个，相比以前的分类器权重计算方法分类效果得到了提升。

$$
w _ { l i } = { \left\{ \begin{array} { l l } { \alpha , x _ { i } \in L _ { l } } \\ { 0 , x _ { i } \notin L _ { l } } \end{array} \right. }
$$

$$
\varepsilon = \frac { e r r o r l N u m } { t e x t N u m }
$$

其中： $x _ { i }$ 表示测试样本， $L _ { l }$ 表示在类别 $l$ 下测试样本的分类器权重。errorlNum为类别 $l$ 下的分类错误率。 $A$ 如式(4)所示。

因此，通过上述数据的分析，得出了类别加权分类器权重方法能更好的表示出分类器权重。将类别加权分类器权重方法融入到多类型分类器方法模型中，得出了改进的多类型分类器模型，模型如图6所示。

![](images/6d22251652a08f0eb3973fad29a961f8f600074c5593d393826cdf2c2a366849.jpg)  
图6多类型二元分类器融合示意图

# 1.4多类型分类器的算法步骤

输入：样本训练集x_train，样本测试集x_test，样本训练集标签y_train，样本测试集标签  
y_test，分类器数目cLassNum  
输出：预测结果矩阵predicted

1) calculate word2vec for $\mathbf { x _ { - } }$ train as class1   
2) calculate tfidf for X_train as class2   
3) calculate lsi for X_train as class3   
4) calculate lda for X_train as class4   
5) train classifier according to ×_train   
6) for $\mathrm { i } \in \{ 1 , 2 , \cdots , \mathrm { l e n } ( \mathsf { x \_ t r a i n } ) \}$ do   
7) calculate errorword2vecNum、errortfidfnum、errorlsiNum、errorldaNum for   
each class according to y_train   
8) end   
9) for $\mathbf { i } \in \{ 1 , 2 , \cdots , \mathrm { l e n ( x \_ t e s t ) \} }$ do   
10) calculate wli for errorword2vecNum、errortfidfnum、errorlsiNum、errorldaNum   
according to equation (4)、(5)and(6)   
11) for $\mathbf { i } \in \{ 1 , 2 , \cdots , \operatorname { l e n } ( { \mathsf { x \_ t e s t } } ) \}$ do   
12) for $\mathfrak { j } \in \{ 1 , 2 , \cdots$ ,classNum} do   
13) s[j] $+ =$ class[j]\*w[j][i]   
14) end   
15) predicted[i] $\mathbf { \sigma } = \mathbf { \sigma }$ maximum number index for s is class   
16) end   
17) return predicted

# 2 实验与结果分析

实验平台基于anaconda平台，编程语言为python语言，4GB 内存和1TB硬盘的电脑上进行实验。

# 2.1实验数据

为了验证多类型分类融合方法的性能，本文利用nItk中的movie_reviews的特定场景的语料库[l3]和普通文本分类搜狗语料库以及20news语料库进行实验验证[14]。其中：搜狗语料库以及20news语料库是最常用的文本分类语料库，可用于测试算法的不同性能。而20news的数据是相对平衡的数据集。movie_reviews是关于电影评论的情感分析语料库，用于情感分析等分类工作，通过使用movie_reviews能更好的验证本文算法。数据集的分布如表1所示。

表1数据集分布  

<html><body><table><tr><td>数据集名称</td><td>类别名</td><td>训练集/个</td><td>测试集/个</td></tr><tr><td rowspan="2">Movie_reviews</td><td>pos</td><td>1600</td><td>400</td></tr><tr><td>neg</td><td>1600</td><td>400</td></tr><tr><td rowspan="4">20news</td><td>atheism</td><td>640</td><td>160</td></tr><tr><td>med</td><td>792</td><td>198</td></tr><tr><td>crypt</td><td>794</td><td>198</td></tr><tr><td>graphics</td><td>800</td><td>200</td></tr><tr><td rowspan="2">搜狗语料库</td><td>社会</td><td>1460</td><td>365</td></tr><tr><td>娱乐</td><td>1460</td><td>365</td></tr></table></body></html>

# 2.2实验分析

该部分的实验分为三个实验来进行的，第一个实验主要验证了算法的有效性，第二个实验主要关注特征维数对本文算法的影响，第三个实验验证类别加权分类器权重计算方法的有效性。分类方法采用python语言中sklearm库中的KNeighborsClassifier方法作为分类方法(k值为10)，特征提取方法有 word2vec、LSI、LDA 和 TFIDF方法，过滤掉小于30的特征词，使用样本识别率作为分类的评价标准，并采用6折交叉验证方法验证算法的有效性[15]。本文实验将多类型融合方法以及其他下属混合方法进行实验，以验证本文算法的性能。

# 2.2.1多类型分类器融合方法的实验对比

该部分使用了20news和movie_reviews 数据集来进行实验的，20news为相对平衡数据集侧重于多元分类，movie_reviews为平衡数据集侧重于二元分类和特定场景的分类，特征维数采用的是300维特征，实验结果如表2所示。

表220news 和 movie_reviews分类结果  

<html><body><table><tr><td colspan="2">Movie_reviews(%) 20news(%)</td></tr><tr><td>LDA</td><td>57.58 92.06</td></tr><tr><td>TFIDF</td><td>70.13 93.25</td></tr><tr><td>LSI</td><td>69.46 93.85</td></tr><tr><td>word2vec</td><td>62.71 79.89</td></tr><tr><td>LDA+TFIDF</td><td>65.33 93.72</td></tr><tr><td>LSI+TFIDF</td><td>71.21 94.44</td></tr><tr><td>LSI+LDA</td><td>65.75 93.32</td></tr><tr><td>word2vec+TFIDF</td><td>69.58 89.15</td></tr><tr><td>word2vec+LDA</td><td>61.54 87.37</td></tr><tr><td>word2vec+LSI</td><td>69.21 88.49</td></tr><tr><td>LSI+LDA+TFIDF</td><td>70.75 95.44</td></tr><tr><td>word2vec+TFIDF+LDA</td><td>69.38 95.11</td></tr><tr><td>word2vec+LSI+TFIDF</td><td>70.75 94.58</td></tr><tr><td>word2vec+LSI+LDA</td><td>69.38 95.30</td></tr><tr><td>word2vec+LSI+TFIDF+LDA</td><td>73.34 96.49</td></tr><tr><td>平均值</td><td>67.74 92.16</td></tr><tr><td>本文算法的最小识别率</td><td>2.13 1.06</td></tr></table></body></html>

通过表2可知，多元分类20news 的平均识别率为 $9 2 . 1 6 \%$ 比 movie_reviews 的 $67 . 7 4 \%$ 高。这是因为 movie_reviews 是专业情感分析数据集而20news为文本分类数据集，应用的领域不同。本文的多类型分类器方法以及多类型分类器下属方法相比，movie_reviews取得了良好的效果，最低提升了 $2 . 1 3 \%$ ，20news最低提升了 $1 . 0 6 \%$ 。这是因为20news是相对平衡的数据集，所以分类器的识别率倾向于多样本类别。

# 2.2.2特征维数对融合分类器的实验影响

该部分使用movie_reviews来验证不同维数(100、300、500和700)对分类性能的影响，实验结果如表3所示。

从表3可以看出，movie_reviews数据集的特征维数为300时，多类型分类器的性能最好；随着特征维数的不断增加，分类器的平均识别率有所下降，这是因为特征数量不断增加，使得表示文档的特征向量空间中会出现大量的0，导致文本特征空间的稀疏而影响了分类器的效果。

表3movie_reviews 不同特征维数  

<html><body><table><tr><td colspan="2">100</td><td colspan="3">300 500</td></tr><tr><td>LDA</td><td>57.75</td><td>57.58</td><td>57.50</td><td>57.58</td></tr><tr><td>TFIDF</td><td>68.70</td><td>70.13</td><td>68.75</td><td>69.00</td></tr><tr><td>LSI</td><td>68.95</td><td>69.46</td><td>68.75</td><td>69.13</td></tr><tr><td>word2vec</td><td>61.65</td><td>62.71</td><td>61.55</td><td>62.04</td></tr><tr><td>LDA+TFIDF</td><td>64.50</td><td>65.33</td><td>64.45</td><td>64.00</td></tr><tr><td>LSI+TFIDF</td><td>71.00</td><td>71.21</td><td>69.85</td><td>69.92</td></tr><tr><td>LSI+LDA</td><td>64.90</td><td>65.75</td><td>64.30</td><td>64.54</td></tr><tr><td>word2vec+TFIDF</td><td>68.40</td><td>69.58</td><td>68.30</td><td>67.42</td></tr><tr><td>word2vec+LDA</td><td>60.55</td><td>61.54</td><td>60.55</td><td>59.96</td></tr><tr><td>word2vec+LSI</td><td>69.35</td><td>69.21</td><td>68.60</td><td>67.42</td></tr><tr><td>LSI+LDA+TFIDF</td><td>70.20</td><td>70.75</td><td>69.30</td><td>69.63</td></tr><tr><td>word2vec+TFIDF+LDA</td><td>68.55</td><td>69.38</td><td>68.00</td><td>68.68</td></tr><tr><td>word2vec+LSI+TFIDF</td><td>70.45</td><td>70.75</td><td>69.85</td><td>69.58</td></tr><tr><td>word2vec+LSI+LDA</td><td>68.60</td><td>68.75</td><td>68.05</td><td>67.92</td></tr><tr><td>word2vec+LSI+TFIDF+LDA</td><td>72.15</td><td>73.00</td><td>70.60</td><td>70.75</td></tr><tr><td>平均值</td><td>67.05</td><td>67.65</td><td>66.56</td><td>66.48</td></tr><tr><td>本文算法的最小识别率</td><td>1.15</td><td>2.13</td><td>0.75</td><td>0.83</td></tr></table></body></html>

# 2.2.3类别加权分类权重的实验结果比较

该部分使用搜狗数据集来验证类别加权分类器权重的有效性，实验结果如表4所示。

表4搜狗语料库结果  

<html><body><table><tr><td colspan="2">分类性能加权</td><td>类别加权</td></tr><tr><td>LDA</td><td>95.11</td><td>96.21</td></tr><tr><td>TFIDF</td><td>95.07</td><td>95.57</td></tr><tr><td>LSI</td><td>95.80</td><td>95.98</td></tr><tr><td>word2vec</td><td>89.59</td><td>91.74</td></tr><tr><td>LDA+TFIDF</td><td>89.59</td><td>91.74</td></tr><tr><td>LSI+TFIDF</td><td>94.75</td><td>95.57</td></tr><tr><td>LSI+LDA</td><td>89.59</td><td>91.78</td></tr><tr><td>word2vec+TFIDF</td><td>95.98</td><td>95.48</td></tr><tr><td>word2vec+LDA</td><td>89.73</td><td>91.78</td></tr><tr><td>word2vec+LSI</td><td>95.80</td><td>95.57</td></tr><tr><td>LSI+LDA+TFIDF</td><td>94.75</td><td>94.16</td></tr><tr><td>word2vec+TFIDF+LDA</td><td>89.59</td><td>95.11</td></tr><tr><td>word2vec+LSI+TFIDF</td><td>96.07</td><td>96.94</td></tr><tr><td>word2vec+LSI+LDA</td><td>96.07</td><td>96.85</td></tr><tr><td>word2vec+LSI+TFIDF+LDA</td><td>97.40</td><td>98.22</td></tr><tr><td>平均值</td><td>93.66</td><td>94.85</td></tr><tr><td>本文最小识别率</td><td>1.32</td><td>1.28</td></tr></table></body></html>

从表4中可以看出，类别加权相对分类性能加权方法具有一定的效果。本章算法平均正确率上比分类性能加权方法高

$1 . 1 9 \%$ ，分类器融合方法比下属方法也高出 $0 . 8 2 \%$ ，在单独特征提取方法中分类性能均得到了提高了，只有在word2vec+TFIDF和word2vec+LSI以及LSI+LDA+TFIDF方法效果没有提高，这是因为语料库的数据规模使得word2vec方法的词向量得分类效果不是很好，同时LDA、LSI以及word2vec所取得的识别率几乎相同，使得word2vec+LSI+TFIDF的融合方法和word2vec+LSI+TFIDF+LDA的融合方法效果相差无几，从而影响了融合分类器整体的分类性能。

# 3 结束语

本文针对单一的分类器以及单一的特征提取方法没有很好的扩展性问题，提出了多类型分类器融合的文本分类方法。本文以四个不同类型的特征提取方法融合起来组成了多类型的文本分类方法。并对分类器权重没有考虑类别信息的问题，提出了类别加权的分类器权重计算方法。通过二元分类和多元分类实验来验证本文算法的有效性。下一步工作是将该方法如何并行计算，减少模型的计算时间。

# 参考文献：

[1]何力，丁兆云，贾焰，等．大规模层次分类中的候选类别搜索[J]．计 算机学报,2014,37(1):41-49.   
[2] 李荣陆，王建会，陈晓云，等．使用最大熵模型进行中文文本分类[J]. 计算机研究与发展,2005,42(1):94-101.   
[3]黄文明，莫阳．基于文本加权KNN算法的中文垃圾短信过滤[J].计算 机工程,2017,43(3):193-199.   
[4]Goudjil M,Koudil M,Bedda M,et al. A novel active learning method using SVM for text classification [J]. International Journal of Automation and Computing,2016:1-9.   
[5]Jiang L,Li C,Wang S,et al. Deep feature weighting for naive Bayes and its application to text classification [J].Engineering Applications of Artificial Intelligence,2016,52(C): 26-39.   
[6]Sangodiah A,Ahmad R, Wan FWA.Areview in feature extraction approach in question classification using Support Vector Machine [C]//Proc of IEEE International Conference on Control System, Computing and Engineering. 2015.   
[7]Chen S,Jin Z.Weibo topic detection based on improved TF-IDF algorithm [J].Science and Technology Review,2016,34(2): 282-286.   
[8]Wang Z,Ma L, Zhang Y.A hybrid document feature extraction method using latent dirichlet allocation and word2vec [C]//Proc of IEEE International Conference on Data Science in Cyberspace.2016.   
[9]Santosh D T,Babu K S,Prasad S D V,et al.Opinion mining of online product reviews from traditional lda topic clusters using feature ontology tree and Sentiwordnet [C]// Proc of International Conference on Social Computing and Social Media.2016: 34-44.   
[10] Uysal A K,Gunal S.Text classification using genetic algorithm oriented latent semantic features [J].Expert Systems with Applications,2014,41 (13):

5938-5947.

[11] Mikolov T,Chen K,Corrado G,et al.Efficient estimation of wordrepresentations in vector space [C]// Proc of International Conference onLearning Representations.2013.  
[12]王晓丹，李睿，薛爱军，等．基于熵的自适应加权投票HRRP 融合识别方法[J].系统工程与电子技术,2017,39(4):707-713.  
[13] Jongeling R,Sarkar P,Datta S,et al.On negative results when usingsentiment analysis tools for software engineering research [J].EmpiricalSoftware Engineering,.2017,22 (5): 2543-2584.  
[14]魏勇，胡丹露，郝晨光，等．基于分类关键词词频模型的地缘政治主题爬虫设计[J].计算机工程，2016,42(2)：45-50  
[15]段宏湘，张秋余，张墨逸．基于归一化互信息的FCBF特征选择算法[J].华中科技大学学报：自然科学版,2017,45(1):52-56.