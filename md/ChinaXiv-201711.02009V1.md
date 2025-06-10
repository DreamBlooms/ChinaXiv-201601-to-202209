# 基于语义相似度的文本聚类研究

毕强刘健1 鲍玉来1,21(吉林大学管理学院 长春 130022)2(内蒙古大学图书馆 呼和浩特 010021)

摘要：【目的】为解决传统的文本聚类无法充分挖掘文本资源语义信息以及相似度矩阵高维性、稀疏性等问题，并进一步改善文本聚类质量，提出基于语义相似度的文本聚类方法。【方法】通过《同义词词林扩展版》计算词语的语义相似度并得到文本语义相似度矩阵，根据文本语义相似度矩阵进行谱聚类，将文本聚集为文本簇。【结果】利用复旦大学文本语料库与搜狗文本语料库中的文本资源作为数据来源分别对传统聚类算法与本文提出的算法进行实验，结果表明，当聚类个数为10时，本文算法的准确率最高，并且Purity值高于传统聚类算法的Purity值。【局限】《同义词词林扩展版》中包含的领域术语不完整，部分相似度计算结果需要手工进行调整。【结论】该方法考虑了词语间语义关系，充分挖掘文本主体潜在信息，并且改善了聚类质量，为文本聚类和推荐提供了一条新途径。

关键词：同义词词林扩展版 语义相似度 谱聚类 文本挖掘

分类号：G250.7

# 1引言

Web2.0时代，文本数据呈现爆炸式增长[1]。文本聚类作为一种无监督的机器学习方法，可以对文本信息进行有效的组织、分类和导航[2]，从而保证用户对知识进行有效、便捷的获取。然而，文本聚类过程中，采用向量空间模型计算文本间相似度的方法受共现特征词影响较大[3]，易造成描述概念信号弱、噪音数据多及特征矩阵稀疏等问题[4]；基于领域本体计算概念相似度的方法需要人工或半人工构建本体，构建过程复杂,借助领域专家和知识工作人员协作完成，并且本体结构中包含信息较为复杂，不能充分体现和揭示概念之间的语义关系，相似度计算结果精度不高[5]。另外，在文本聚类中也存在着对初始聚类中心选值的敏感性问题、容易陷入局部最优值等问题，影响了文本聚类效果。

《同义词词林扩展版》编码简单，层次结构清晰具有丰富的语义知识并且可以解决中文文本多义词分歧的问题[]，因此本文利用同义词词林扩展的语义相似度计算方法改进谱聚类算法：通过同义词词林计算语义相似度并形成语义相似度矩阵，对语义相似度矩阵进行拉普拉斯变换以降低矩阵维度，将变换后的向量矩阵进行聚类，从而完成对语义相近文本簇的划分，以此提高文本聚类效果。

# 2相关研究

# 2.1 语义相似度计算

概念语义相似度是指两个概念间的相似程度[8],已经被应用于词义消歧[9]、自动检索[10]、图像分类及标注[11]、信息抽取[12]、信息检索[13]等领域。目前，语义相似度计算方法主要包括基于本体的概念语义相似度计算与基于语义词典的概念相似度计算。基于本体的语义相似度计算按照计算方法的不同可分为：基于距离的方法、基于内容的方法和基于属性的方法等。基于距离的计算方法是在层次网络中使用路径长度来量化两个概念之间的语义距离[14]。基于属性的方法[15]是利用事物之间不同的属性特征区别事物。两个事物的公共属性越多，相似度越高。基于内容的方法[16认为两个概念共享的信息会影响二者的语义相似度。然而由于本体结构中包含信息较为复杂，不能充分体现和揭示概念之间的语义关系，导致相似度计算的精度不高。另一方面，利用语义词典WordNetFrameNet、MindNet等来计算英文词语相似度，以及利用《知网》(HowNet)、同义词词林等计算中文相似度[17]，也是较为常用的方法。基于语义词典的方法通常依赖于比较完备的大型语义词典。词典中的关系和层次结构，如概念之间的上下位关系和同位关系可以用来计算词语的相似度。由于基于同义词词林比基于《知网》的词汇语义相似度计算方法更符合人们的理解[18]，因此本文利用其作为计算语义相似度的方法。

# 2.2 文本聚类分析

文本聚类分析是利用文本之间的相似性对无结构或半结构化的文本对象进行自动分组的过程[19]。同组内文本相似性较高，不同组的文本相似性较低。通常将文本表示成向量的模式，利用特征词来计算各文本之间的相似度。常用的文本聚类分析的方法包括K-means聚类[20]、层次聚类[21]、基于密度的聚类[22]以及基于网格的聚类[23]等。文本聚类的过程包括提取文本特征词、计算文本相似度以及文本聚类算法等方面。文本聚类技术在文档整理、组织以及信息检索中得到广泛应用，例如对网页自动归类、新闻报道自动分类、电子邮件分组等，还可以对搜索引擎返回的结果进行聚类，使用户迅速查询到所需要的信息。

传统的聚类算法都是建立在凸球形的样本空间上。当样本空间不为凸时，算法会陷人“局部"最优。另外，许多文档之间没有公共词语存在，导致文档矩阵具有高维性和稀疏性，而且聚簇中心也没有提供可以理解的聚簇描述。为了能在任意形状的样本空间上聚类，收敛于全局最优解，克服文档矩阵的高维性和稀疏性等缺点，相关学者开始利用谱方法来聚类。谱聚类方法建立在谱图理论的基础上，通过计算数据相似关系建立相似度矩阵，以该矩阵的前k个特征向量来对不同的数据点聚类。与其他聚类方法不同，谱聚类不容易陷入局部最优解，而且可以有效识别非凸分布的聚类，已经成功应用于在线学习分类[24]、图像分割[25]、词义消歧[26]、网页划分[27和文本挖掘[28]等领域。因此，本文选用谱聚类作为文档聚类的分析方法。

# 3计算方法及过程

文本聚类过程中首先要对文本文档数据进行预处理，完成从文本形式到数学表示的转换。常见的文本表示方法采用向量空间模型，利用单词或词语共现次数表征文档内容，忽略了文档资源之间存在的语义关联。基于距离的相异度可以用来度量文档对象之间相似度，例如余弦距离、欧几里德距离、曼哈坦距离等。但由于文档之间的特征词交集过少导致文档向量矩阵的高维性和稀疏性，距离度量往往不能准确有效地表达文档之间潜在的语义关联信息。因此，在文本聚类过程中应充分挖掘隐藏在文档中的语义信息，寻找文本对象之间特有的语义关联。本文利用改进的语义相似度矩阵代替空间向量模型，并利用谱聚类方法对相似度矩阵进行分解，从而降低矩阵的高维度，提高聚类结果的准确性。

# 3.1概念语义相似度计算

文献[18]根据同义词词林结构及其编排的特点，利用词语在词林树状结构中的编号，提出基于同义词词林的概念语义相似度计算方法。本文参考文献[18]的计算方法计算概念的语义相似度。具体描述如下：首先判断两个概念在同义词林中不同编号的起始位置，例如:Aa01A01与Aa01B01，在第四层不同。对于不同的层，分别乘以不同的系数。同义词词林的结构深度共五层，从第二层开始，对于不同层的词语分别乘以不同的参数a、b、c、d。然后再乘以调节参数0 $\mathrm { { z o s } } { \Bigg ( } \mathrm { n } \times { \frac { \pi } { 1 8 0 } } { \Bigg ) }$ 利用该调节参数将词语相似度控制在[0,1]区间，其中 $\mathfrak { n }$ 是分支层的节点总数。

概念所在词林位置的密度会影响概念语义的相似度计算：密度越大，概念语义相似度的值越精确；相反，密度越小，概念语义相似度值误差越大。一般的计算方式是统计两个概念在词典间隔单词的数量，即计算词林中公共祖先的数量来计算概念语义相似度，这种方法并没有考虑概念所在分支的密度信息。通过统计两个概念 $\mathbf { c } _ { 1 } , \mathbf { c } _ { 2 }$ 在同义词词林中分支间的距离，即统计这两个概念所在分支包含的概念数量来计算密度信息[29]，密度信息公式如下。

$$
\mathrm { d i s } = - \mathrm { l o g } \left( \frac { \mathrm { f r e q ( c ) } } { \mathrm { N } } \right)
$$

其中，freq(c)=∑count(c)，c为从概念 $\mathbf { c } _ { 1 }$ 所在分支到概念 $\mathbf { c } _ { 2 }$ 所在分支之间所包含的概念，∑count(c)为这些概念数量的总合， $\mathrm { ~ N ~ }$ 为 $\mathbf { c } _ { 1 }$ 和 $\mathbf { c } _ { 2 }$ 所在分支的所有概念的总和。利用公式(1)对计算的语义相似度结果进行细化，以此保证计算结果更加精确。由以上得出概念的语义相似度公式，用Sim表示。

若两个概念不在同一棵树上：

$$
\mathrm { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = \mathbf { f }
$$

若两个概念在同一棵树上，并且位于在第二层分支，则系数为a，计算公式如下：

$$
\operatorname { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = 1 \times \mathbf { a } \times \mathbf { c o s } \left( \mathbf { n } \times { \frac { \pi } { 1 8 0 } } \right) \times \mathrm { d i s }
$$

若两个概念在同一棵树上，并且位于第三层分支，则系数为 $\boldsymbol { \mathbf { b } }$ ，计算公式如下：

$$
\operatorname { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = 1 \times \mathbf { b } \times \cos \left( \mathbf { n } \times { \frac { \pi } { 1 8 0 } } \right) \times \mathrm { d i s }
$$

若两个概念在同一棵树上，并且位于第四层分支，则系数为c，计算公式如下：

$$
\operatorname { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = 1 \times \mathbf { c } \times \cos \left( \mathbf { n } \times { \frac { \pi } { 1 8 0 } } \right) \times \mathrm { d i s }
$$

若两个概念在同一棵树上，并且位于第五层分支，则系数为 $\mathrm { ~ d ~ }$ ，计算公式如下：

$$
\operatorname { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = 1 \times \mathbf { d } \times \mathbf { c o s } \left( \mathbf { n } \times { \frac { \pi } { 1 8 0 } } \right) \times \mathbf { d i s }
$$

当编号相同且末尾号为 $\cdot = \overrightarrow { \mathbf { \Gamma } }$ 时，相似度为1；当编号相同而只有末尾号为"#"时，直接将定义的系数e赋给结果。即: $\mathrm { S i m } ( \mathbf { c } _ { 1 } , \mathbf { c } _ { 2 } ) = \mathbf { e }$ 。通过对概念相似度测试及根据文献[18]的参考，本文将层数初始值设置为 $\mathbf { a } =$ 0.532, ${ \sf b } = 0 . 7 8$ 5 $\mathrm { c } = 0 . 8 4$ ， ${ \mathrm { d } } = 0 . 8 8$ + $\mathbf { e } = 0 . 4 2$ 5 $\mathrm { f } = 0 . 0 0 1$ 。

# 3.2 文本相似度计算

文本相似度是指文本间主题或内容的相似程度，与Quillian的联合概念相似，可以通过计算文本特征词或概念的相似度计算文本相似度[30]。当计算文本的语义相似度时，首先要计算文本的语义距离，如公式$( 7 ) ^ { [ 3 0 ] }$ 所示。

$$
\mathrm { D i s t ( d _ { x } , d _ { y } ) = D i s t ( \hat { \omega } _ { i = 1 } ^ { n } K _ { x i } , \hat { \omega } _ { j = 1 } ^ { m } K _ { y j } \omega ) = \frac { 1 } { d } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } f _ { i } \times f _ { j } \times D i s t ( K _ { i } , K _ { j } ) }
$$

其中， $\mathrm { d } _ { \mathrm { x } }$ ，dy为两个不同文本， $\mathbf { X } _ { \mathrm { i } }$ ，yj分别为文本$\mathbf { d } _ { \mathrm { x } }$ ， ${ \bf d } _ { \mathrm { y } }$ 所包含的特征词或概念; $\mathrm { f _ { i } }$ 为概念 $\mathbf { X _ { i } }$ 在文本dx中出现的次数；fj为概念 $\mathsf { y } _ { \mathrm { j } }$ 在文本 ${ \bf d } _ { \mathrm { y } }$ 中出现的次数;n, $\mathrm { ~ m ~ }$ 分别为两个文本所包含的概念个数。为了避免语义距离的计算结果过大，利用d 进行归一化，公式如下[30]

$$
\mathrm { { d } = \left( \sum _ { i = 1 } ^ { n } f _ { x i } \right) \times \left( \sum _ { j = 1 } ^ { m } f _ { y j } \right) }
$$

d所代表的意义为两个文本中概念或者特征词语义距离的数量，同时也考虑到特征词或概念在文本中出现的次数，对语义距离进行归一化可以避免文本包含的特征词或概念过多，导致文本语义距离过大。综上，本文将文本语义相似度定义如下[30]

$$
\mathrm { S i m } ( \mathrm { d } _ { \mathrm { x } } , \mathrm { d } _ { \mathrm { y } } ) { = } \frac { 1 } { 1 + \mathrm { D i s t } ( \mathrm { d } _ { \mathrm { x } } , \mathrm { d } _ { \mathrm { y } } ) }
$$

可以看出，语义距离越大，文本的相似度越小。

# 3.3基于语义相似度的谱聚类算法

基于 NJW 算法[31],本文提出基于语义相似度矩阵的谱聚类算法(SCBSS)。SCBSS算法采用概念列表表示文本，以文本间的语义相似度作为文本间相关程度的度量。相似度矩阵是一个对称矩阵，而且相似度值是非零的。在进行文本预处理的基础上，以中文词语为单位，利用《同义词词林扩展版》计算词语之间的语义相似度，将其作为衡量概念距离的指标。其次，将文本表示成概念的集合，两个文本的相似度可以通过它们包含概念的语义相似度计算。最后，构建文本间相似度矩阵，并应用文本谱聚类方法进行分析。改进SCBSS算法的描述如下：

输入：n个数据点，聚类的个数K  
输出：K个聚类  
方法：  
Begin$\textcircled{1}$ 构造相似性矩阵 $\mathbf { W } \in \mathbf { R } ^ { \mathrm { n \times n } }$ ：  
$\textcircled{2}$ 构造矩阵 $\mathrm { P } = \mathrm { D } ^ { - 1 / 2 } \mathrm { W D } ^ { 1 / 2 }$ ;  
$\textcircled{3}$ 求P的 $\mathbf { k }$ 个最大特征值所对应的特征向量 $\mathbf { v } _ { 1 } , \mathbf { v } _ { 2 } , \mathbf { \cdots } , \mathbf { v } _ { \mathrm { n } } .$ 构造矩阵 $\mathbf { V } = [ \mathbf { v } _ { 1 } \mathbf { v } _ { 2 } \cdots \mathbf { v } _ { \mathrm { n } } ] \in \mathbb { R } ^ { \mathrm { n } \times \mathrm { k } }$ ，其中 $\mathbf { \sigma } _ { \mathbf { V } _ { i } }$ 为列向量, $\mathrm { i } { = } 1 , \ \cdots , \mathrm { n }$ ：（204号 $\textcircled{4}$ 规范化 $\mathrm { \Delta V }$ 的行向量，得到矩阵Y,其中 $\mathrm { y _ { i j } = v _ { i j } / ( \sum _ { j } v _ { i j } ^ { 2 } ) ^ { l / 2 } }$ ：$\textcircled{5}$ 将 $\mathrm { \Delta Y }$ 的每一行看成是 $\mathbb { R } ^ { \mathrm { k } }$ 空间中的一点，使用 $\mathrm { ~ K ~ }$ -means聚类。End

如上所示，谱聚类将文档的相似度放到一个带权无向图中，采用"图划分"的方法进行聚类。谱聚类算

# 法分为三步：

(1）构造一个 $\boldsymbol { \mathrm { n } } \times \boldsymbol { \mathrm { n } }$ 的权值矩阵W，利用同义词词林计算词语的相似度 $\mathbf { W _ { i j } } \circ \mathbf { \Sigma } \mathbf { W _ { i j } }$ 表示词语i和词语j的相似度，显然W是对称矩阵。(2）构造一个对角矩阵D, $\mathrm { d } _ { \mathrm { i i } }$ 为W第i列元素之和。对矩阵 $\mathrm { ~ \bf ~ P ~ }$ 进行规范化，即 $\mathrm { P } = \mathrm { D } ^ { - 1 / 2 } \mathrm { W D } ^ { 1 / 2 }$ 。可以证明P是个半正定和对称矩阵，求得 $\mathrm { ~ \bf ~ P ~ }$ 的前 $\mathfrak { n }$ 大特征值所对应的特征向量。(3）将 $\mathbf { n }$ 个特征向量放在一起构造一个 $\mathbf { n } \times \mathbf { k }$ 的矩阵V，将V的每一行当成一个新的样本点，对新的样本点进行K-means聚类。传统的聚类方法要求数据必须是N维欧氏空间中的向量，而利用谱方法聚类只需要计算文本的相似度矩阵，这降低了数据矩阵的维度，并且缓解了数据矩阵的稀疏性。

# 4实验过程及结果

# 4.1 语义相似度计算

选取10组概念进行语义相似度计算，为了对比实验效果，采用咨询的方式获得人工对于语义相似度的判断。咨询对象包括计算机专业、情报专业、经济专业的硕士生和博士生，共有20人。通过对该组概念语义评价问题进行语义相似度判定。语义相似度的评判范围是[0,1],0表示两个概念完全不同，1表示两个概念语义相同。对受测者各进行两次实验，并对同一概念语义相似度的评测结果取平均值。计算结果如表1所示。

表1概念语义相似度部分计算结果  

<html><body><table><tr><td colspan="2">词语</td><td>语义相似度</td><td>相似度范围</td></tr><tr><td>经济</td><td>产业</td><td>0.693</td><td>0.7-0.8</td></tr><tr><td>货币</td><td>银行</td><td>0.540</td><td>0.6-0.7</td></tr><tr><td>企业</td><td>公司</td><td>1.000</td><td>0.9-1.0</td></tr><tr><td>资源</td><td>工业</td><td>0.362</td><td>0.3-0.4</td></tr><tr><td>软件</td><td>计算机</td><td>0.717</td><td>0.7-0.8</td></tr><tr><td>服务器</td><td>路由器</td><td>0.500</td><td>0.5-0.6</td></tr><tr><td>历史</td><td>二战</td><td>0.431</td><td>0.4-0.5</td></tr><tr><td>地理</td><td>地理学</td><td>1.000</td><td>0.9-1.0</td></tr><tr><td>电路</td><td>电子</td><td>0.832</td><td>0.8-0.9</td></tr><tr><td>设备</td><td>产品</td><td>0.727</td><td>0.7-0.8</td></tr></table></body></html>

该方法根据概念在同义词词林的位置进行编码，计算得出概念相似度。从表1可以看出，利用同义词词林进行语义相似度计算结果具有较高的准确性，并且符合目标用户对于语义相似度的主观判断，说明该算法可以客观准确地反映概念之间的语义关系，并为有效度量概念的语义相似度提供一种新的方法和途径。

# 4.2文本相似度计算结果

搜狗文本挖掘数据集是比较全面的语料库，该数据集包含汽车、财经、IT、健康、体育、旅游、教育、招聘、文化、军事等10个类别，每个类别大约有2000篇文档。本文从这10个类别中各选择100篇文档共计1000 篇，利用 NLPIR 大数据搜索与挖掘共享平台①对其进行分词处理和词频统计。从中选出10个词频较高并能代表文档内容的关键词，将其作为表征文档特征的关键词，并记录其词频，如图1所示。

<html><body><table><tr><td>文章名</td><td>关键词</td><td>词频 关键词</td><td>词频</td><td>关键词 词频</td><td>关键词</td><td>词频 关键词</td><td>词频 关键词</td><td>词频</td><td>关键词 词频</td><td>关键词 词频</td><td>关键词</td><td>词频 关键词</td><td>词频</td><td>关键词</td><td>词频</td></tr><tr><td>文章1</td><td>流通</td><td>166经济学</td><td>101理论</td><td></td><td>72商业</td><td>31经济</td><td>42资源</td><td>8马克思</td><td></td><td>23国家</td><td>7变革</td><td>6政府</td><td>5要素</td><td></td><td>12</td></tr><tr><td>文章2</td><td>企业</td><td>77经济</td><td></td><td>25商业</td><td>33竞争性</td><td>10市场</td><td>21结构</td><td></td><td>10行业</td><td>27资产</td><td>10机制</td><td>9产业</td><td></td><td>5资本</td><td>4</td></tr><tr><td>文章3</td><td>价格</td><td>7市场</td><td></td><td>18消费者</td><td>10企业</td><td>8购买力</td><td>3居民</td><td>10制度</td><td></td><td>6体制</td><td>3资金</td><td>3指数</td><td></td><td>5医疗</td><td></td></tr><tr><td>文章4</td><td>农村</td><td>86农民</td><td></td><td>79农产品</td><td>62消费</td><td>47市场</td><td>40收入</td><td>40城镇</td><td></td><td>37支出</td><td>20价格</td><td>18投资</td><td></td><td>13资源</td><td>4</td></tr><tr><td>文章5</td><td>消费</td><td>56储蓄</td><td>42居民</td><td></td><td>29经济</td><td>20存款</td><td>17投资</td><td>10市场</td><td></td><td>7改革</td><td>6银行</td><td>6消费品</td><td></td><td>4余额</td><td>4</td></tr><tr><td>文章6</td><td>消费</td><td>118经济</td><td>58增长</td><td></td><td>41投资</td><td>37储蓄</td><td>27需求</td><td>17收入</td><td></td><td>17政策</td><td>13财政</td><td>7产业</td><td></td><td>7信贷</td><td>5</td></tr><tr><td>文章7</td><td>消费</td><td>72发展</td><td>36经济</td><td></td><td>29生产力</td><td>17生产关系</td><td>7社会</td><td></td><td>5消费者</td><td>5福利</td><td>5政策</td><td>4社会</td><td></td><td>5管理</td><td>4</td></tr><tr><td>文章8</td><td>经济</td><td>28市场</td><td>23消费</td><td></td><td>23商家</td><td>14行业</td><td>10服务</td><td>9发展</td><td></td><td>7产业</td><td>6需求</td><td>6政府</td><td></td><td>6内需</td><td>3</td></tr><tr><td>文章9</td><td>企业</td><td>72信息</td><td>65网络</td><td></td><td>63外贸</td><td>30经济</td><td>25管理</td><td>22市场</td><td></td><td>19资源</td><td>12成本</td><td>9技术</td><td></td><td>9服务</td><td>8</td></tr><tr><td>文章10</td><td>俄罗斯</td><td>53经济</td><td>25出口</td><td></td><td>23经贸</td><td>18经济危机</td><td>13政策</td><td>13市场</td><td></td><td>11贸易</td><td>10财政</td><td>6工业</td><td>6投资</td><td></td><td>6</td></tr><tr><td>文章11</td><td>投资</td><td>35财政</td><td>28经济</td><td></td><td>18需求</td><td>17贴息</td><td>12企业</td><td>11财政</td><td></td><td>8消费</td><td>7投资</td><td>14产业</td><td></td><td>6债券</td><td>5</td></tr><tr><td>文章12</td><td>储蓄</td><td>225政府</td><td>194支出</td><td></td><td>79收入</td><td>47税收</td><td>47投资</td><td>32经济</td><td></td><td>30资金</td><td>25政策</td><td>24财政</td><td></td><td>22财政赤字</td><td>16</td></tr><tr><td>文章13</td><td>财政</td><td>88政策</td><td>55国债</td><td></td><td>30经济</td><td>23预算</td><td>22政府</td><td>20投资</td><td></td><td>19货币</td><td>16银行</td><td>16企业</td><td></td><td>12市场</td><td>9</td></tr><tr><td>文章14</td><td>财政</td><td>56经济</td><td>26支出</td><td></td><td>19预算</td><td>15资金</td><td>15社会</td><td>11收入</td><td></td><td>8投资</td><td>8企业</td><td>6国民经济</td><td></td><td>4政治</td><td>5</td></tr><tr><td>文章15 文章16</td><td>税收</td><td>9征管</td><td>5制度</td><td></td><td>5电子商务</td><td>3交易</td><td>3经济</td><td></td><td>3经济体制</td><td>3市场</td><td>3保障</td><td>2改革</td><td></td><td>2贸易</td><td>26</td></tr><tr><td></td><td>资本市场</td><td>42政策</td><td>24货币</td><td></td><td>21经济</td><td>17市场</td><td>15投资</td><td>14金融</td><td></td><td>13产业</td><td>11企业</td><td>9股市</td><td></td><td>6银行</td><td></td></tr><tr><td>文章17 文章18</td><td>税收 金融</td><td>29协定</td><td>12经济</td><td></td><td>8技术</td><td>7金融</td><td>7资本</td><td>6税务</td><td></td><td>5电子商务</td><td>4纳税人</td><td>4劳动力</td><td></td><td>3税基</td><td>3</td></tr><tr><td>文章19</td><td>银行</td><td>64经济</td><td>28知识</td><td></td><td>19货币</td><td>16市场</td><td>12金融业</td><td>7产业</td><td></td><td>6企业</td><td>5资本市场</td><td>5经济体制</td><td></td><td>4商业</td><td>4</td></tr><tr><td>文章20</td><td>银行</td><td>73金融 38金融</td><td>15经营</td><td></td><td>11利润</td><td>8企业</td><td>7服务</td><td></td><td>6农业</td><td>5贷款</td><td>4金融业</td><td>4商业</td><td></td><td>4货币</td><td>33</td></tr><tr><td>文章21</td><td>金融</td><td></td><td></td><td>30信息化</td><td>14科技</td><td>12经济</td><td>9银行业</td><td></td><td>7计算机</td><td>4信息</td><td>4货币</td><td>4电子商务</td><td></td><td>3外资</td><td></td></tr><tr><td>文章22</td><td>保险</td><td>273银行</td><td>77贷款</td><td></td><td>60资产</td><td>43企业</td><td>30经济</td><td>26商业</td><td></td><td>21制度</td><td>18资金</td><td>13金融市场</td><td></td><td>12金融业</td><td>8</td></tr><tr><td>文章23</td><td>企业</td><td>93失业 78技术</td><td>88企业</td><td></td><td>45基金</td><td>22经济</td><td>11创新</td><td>10改革</td><td></td><td>10服务</td><td>9财政</td><td>5市场经济</td><td></td><td>5公有制</td><td>4</td></tr><tr><td>文章24</td><td>经济</td><td>67法律</td><td></td><td>53经济 29经济法</td><td>34产业 24立法</td><td>28知识经济</td><td>28信息 17利益</td><td></td><td>28信息化</td><td>25市场</td><td>17公司</td><td>13资本</td><td></td><td>13工业</td><td>8</td></tr><tr><td>文章25</td><td>经济</td><td>105社会主义</td><td></td><td>45生产力</td><td>18现代化</td><td>17社会</td><td>14改革</td><td></td><td>12行政</td><td>9私法</td><td>7改革</td><td>6产品 7国有经济</td><td></td><td>5服务</td><td>5</td></tr><tr><td>文章26</td><td>利益</td><td>73集体主义</td><td></td><td>47社会主义</td><td>46市场经济</td><td>16政治</td><td>35道德</td><td>13核心</td><td></td><td>13阶级斗争</td><td>12改革开放</td><td></td><td></td><td>7国民经济</td><td>5</td></tr><tr><td>文章27</td><td>经济</td><td>85市场</td><td></td><td>57市场经济</td><td>55企业</td><td>39个人主义 54伦理</td><td>53社会主义</td><td></td><td>29观念 45道德</td><td>12经济</td><td>12资产阶级 29竞争</td><td>12政治 25权利</td><td></td><td>9历史 19民主</td><td>5 17 7</td></tr><tr><td>文章28</td><td>经济 道德</td><td>59知识 109建设</td><td>31观念</td><td>41生产力</td><td>33社会 21社会主义</td><td>25资源</td><td>16工业 20市场经济 13政策</td><td>12经济</td><td>14产业</td><td>42自由 11农业 6思想</td><td>9资本 5市场</td><td>8技术 4需求</td></table></body></html>

义相似度及文本相似度。部分计算结果如图2所示。

利用Java语言对公式(7)-公式(9)进行编程计算语  

<html><body><table><tr><td></td><td>文章1</td><td>文章2</td><td>文章3</td><td>文章4</td><td>文章5</td><td>文章6</td><td>文章7</td><td>文章8</td></tr><tr><td>文章1</td><td>1.00000000</td><td>0.563974568901669</td><td>0.327679511725551</td><td>0.94941099423074</td><td>0.1005755767596925</td><td>0.9728397634991666</td><td>0.969634158229821</td><td>0.666262179435328</td></tr><tr><td>文章2</td><td>0.563974568901669</td><td>1.00000000000000</td><td>O.766954062882087</td><td>0.6751060957294674</td><td>O.163081826396616</td><td>0.4019696407249738</td><td>0.829608338463549</td><td>0.165699911380247</td></tr><tr><td>文章3</td><td>0.3276795117255515</td><td>T0.766954062882087</td><td>100000000</td><td></td><td>0.90425783123187</td><td></td><td>0.175794923419562</td><td>0.6359152355969346</td></tr><tr><td>文章4</td><td></td><td>0.675106095729467</td><td></td><td>O.026369012590481</td><td>0.420746187724109</td><td>0.918461274220261 0.6387285229573507</td><td></td><td></td></tr><tr><td></td><td>0.9494109942307407</td><td>0.163081826396616</td><td>O.026369012590482</td><td>1.000000000000000</td><td></td><td></td><td>0.017402323041681</td><td>0.4130173790115754</td></tr><tr><td>文章5 文6</td><td>0.100575576759693</td><td></td><td>0.904257831231872</td><td>0.42074618772411</td><td>1.000000000000000</td><td>0.594445989739732</td><td>0.594000170522666</td><td>0.8515256634203805</td></tr><tr><td></td><td>0.972839763499167</td><td>0.401969640724974</td><td>0.9184612742202605</td><td>0.6387285229573503</td><td>0.594445989739732</td><td>1.000000000000000</td><td>0.71068311265961</td><td>0.428263053220396</td></tr><tr><td>文章7 文章8</td><td>0.9696341582298214</td><td>0.82960833846355</td><td>0.175794923419562</td><td>0.017402323041681</td><td>0.594000170522666</td><td>0.71068311265961</td><td>1.0000000000000000</td><td>0.4354999400392616</td></tr><tr><td>文章9</td><td>0.6662621794353285</td><td>0.1656999113802464</td><td></td><td></td><td>0.8515256634203796</td><td>0.4282630532203955</td><td></td><td>1.000000000000000</td></tr><tr><td></td><td>0.055181703157101</td><td>0.856106829731903</td><td></td><td></td><td>0.470549414597219</td><td>6677065017</td><td>3341869498</td><td>0.416412334885247</td></tr><tr><td>文章10</td><td>0.310603435121219</td><td>0.2612428331351793</td><td>0.369832290345109</td><td>.2367970011278646</td><td>0.7924533845516057</td><td>0.971914982838976</td><td>1.366547439196948</td><td>0.7936447365840604</td></tr><tr><td>文章11 文章12</td><td>0.438117547541325</td><td>0.823865464416473</td><td>0.519229085912907</td><td>0.104859881506144</td><td>0.102005203451274</td><td>0.124725826624569</td><td>263593179253916</td><td>0.6897209873570302</td></tr><tr><td>文章13</td><td>0.279399821825014</td><td>0.6057667862248026 0.672217918962981</td><td>192426142122578</td><td>111364329026387</td><td></td><td>0.8017474051834266</td><td>5996449874</td><td>0.666745668415216</td></tr><tr><td>文章14</td><td>0.49028001555837 0.37548598939755</td><td></td><td></td><td></td><td></td><td>0.9685143918589274</td><td></td><td>0.684369100937615</td></tr><tr><td>文章15</td><td>0.361509827348179</td><td>0.328644826509014</td><td>.1340 63839688</td><td>6428259</td><td>0.527434572676645</td><td></td><td></td><td>0.538429440587028</td></tr><tr><td>文章16</td><td>0.985339344546746</td><td>0.994287926160746</td><td>0.84254223138336</td><td>62037701017</td><td>0.3190870346828705</td><td>0.847792529417909 .425320867189221</td><td>813 0677271 0.426701550674164</td><td>0.138275549760936</td></tr><tr><td>文章17</td><td>0.044912769652934</td><td>0.7949372982548635</td><td></td><td>433933</td><td>5411675933829345</td><td>0.8219995783201957</td><td></td><td>0.0023055906289375 0.547719869515687</td></tr><tr><td>文章18</td><td>0.060415667541866</td><td></td><td></td><td></td><td></td><td></td><td>981793927895194</td><td></td></tr><tr><td>文章19</td><td>0.147779629408661</td><td>9443532778</td><td></td><td></td><td></td><td>7642055</td><td>３６２8５</td><td>0.050689166371367</td></tr><tr><td>文章20</td><td>0.7783298361351823</td><td>0.345390713589556</td><td>65128205140301</td><td>194359</td><td>125158518524769</td><td>4233416049016587</td><td>354267691677</td><td>0.0505777926001265</td></tr><tr><td>文章22</td><td>0.402738381718552</td><td>0.138404523698873</td><td>237652</td><td>143303767417171</td><td>.080275315952335</td><td>1715648900044044</td><td>43475433875</td><td>0.26378988255054 0.8032132851294214</td></tr><tr><td>文章22</td><td>0.10483724127857</td><td>0.5780178080372598</td><td></td><td>1918455</td><td>743499629038064</td><td>.9008811990118084</td><td>3022233</td><td>0.3453715985749812</td></tr><tr><td>文章23</td><td>0.7110146136680027</td><td>0.393788514277369</td><td></td><td></td><td></td><td></td><td></td><td>0.7862874616627886</td></tr><tr><td>文章24</td><td>0.852558624950651</td><td>0.868 2452292448</td><td></td><td>20705</td><td>50</td><td>0.406 Ｂ8０２３</td><td></td><td>0.9324470406782908</td></tr><tr><td>文章25</td><td>0.4838700311251856</td><td>0.9023832838666332</td><td>.345528483590705</td><td>11003 8349717243</td><td>0.671893442927284</td><td>1206465875359752</td><td>140607096</td><td>0.9716173605719427</td></tr><tr><td>文26</td><td>0.8385271683015687</td><td>0.445333670840423</td><td>0.7883641667853447</td><td>0.6015054623906217</td><td>0.269920483401144</td><td>.451679716214165</td><td>7197404083241876</td><td>0.270232890868706</td></tr><tr><td>文章27</td><td>0.056551202951806</td><td>0.393540011663058</td><td>.008005874011931</td><td>585764152008852</td><td>0.713331270454713</td><td>698449684405485</td><td></td><td>0.9673682921536115</td></tr><tr><td>文章28</td><td>0.448030401984392</td><td>O.002832992183949</td><td></td><td></td><td>423912</td><td></td><td></td><td>0.9633271849773037</td></tr><tr><td>文章29</td><td>0.602312025010499</td><td>0.207572351849996</td><td>0.63953391182852</td><td>0.151952 532920807</td><td>0.389387454231344</td><td>0.253845526997306</td><td>97939726</td><td>0.9379319034155484</td></tr><tr><td>文章30</td><td>0.010089965720908</td><td>0.255517342110042</td><td>0.8670937216539683</td><td>0.590271889861161</td><td>0.549722995873713</td><td>0.771690193392097</td><td>0.576826431770618</td><td>0.318361222785512</td></tr><tr><td>文章31</td><td>0.253213354239287</td><td>0.405561566226373</td><td>O.3722728725263376</td><td>0.359119957039426</td><td>0.727446294215676</td><td>0.026305175466306</td><td>0.5044707218883255</td><td>0.805644349331044</td></tr><tr><td>文章32</td><td>0.544157812908578</td><td>0.709817986907104</td><td>0.27898522136654</td><td>0.217660147899522</td><td>0.920681087249042</td><td>0.8541084609723018</td><td>O.096874772727638</td><td>0.5251280427283183</td></tr><tr><td>文章33</td><td>0.410493040486498</td><td>0.604007500171299</td><td>0.352302557400517</td><td>0.9363983206959867</td><td>0.949085761487553</td><td>0.025088237336723</td><td>0.9823815271374827</td><td>0.5589581019354415</td></tr></table></body></html>

# 4.3文本聚类实验及结果

得到文本相似度矩阵后，利用谱聚类方法对文档矩阵进行聚类划分。本文聚类结果的衡量指标选用聚类结果的纯度(Purity)进行分析，此方法是一种简单有效的聚类结果的评价指标，计算公式如下。

$$
\mathrm { P u r i t y } = \sum _ { \mathrm { i } = 1 } ^ { \mathrm { K } } \frac { \mathrm { m } _ { \mathrm { i } } } { \mathrm { m } } \mathrm { p } _ { \mathrm { i } }
$$

其中， $\bf \ p _ { \mathrm { i } } = \mathrm { m a x ( p _ { \mathrm { i j } } ) , \nabla \ p _ { \mathrm { i j } } = \frac { m _ { \mathrm { i j } } } { m _ { \mathrm { i } } } }$ ， $\mathbf { m } _ { \mathrm { i } }$ 是在聚类i中所有成员的个数， $\mathbf { m } _ { \mathrm { i j } }$ 是既属于聚类i又属于聚类j的成员个数。对于该算法，分别考虑当聚类个数 $\scriptstyle 1 = 4$ 、10这两种情况，对每个取值均随机选择初始簇中心，得到聚类结果。当 $\scriptstyle 1 = 4$ 时，聚类的结果如表2所示。

表2 $\scriptstyle 1 = 4$ 时聚类结果  

<html><body><table><tr><td>类别</td><td>C1</td><td>C2</td><td>C3</td><td>C4</td></tr><tr><td>汽车</td><td>82</td><td>4</td><td>5</td><td>9</td></tr><tr><td>财经</td><td>10</td><td>64</td><td>12</td><td>14</td></tr><tr><td>IT</td><td>40</td><td>17</td><td>24</td><td>19</td></tr><tr><td>健康</td><td>19</td><td>17</td><td>33</td><td>31</td></tr><tr><td>体育</td><td>37</td><td>15</td><td>10</td><td>38</td></tr><tr><td>旅游</td><td>23</td><td>35</td><td>18</td><td>24</td></tr><tr><td>教育</td><td>8</td><td>3</td><td>84</td><td>5</td></tr><tr><td>招聘</td><td>46</td><td>39</td><td>9</td><td>7</td></tr><tr><td>文化</td><td>2</td><td>13</td><td>8</td><td>77</td></tr><tr><td>军事</td><td>28</td><td>24</td><td>30</td><td>28</td></tr></table></body></html>

图2文档相似度计算结果  

<html><body><table><tr><td>类别</td><td>C1</td><td>C2</td><td>C3</td><td>C4</td><td>C5</td><td>C6</td><td>C7</td><td>C8</td><td>C9</td><td>C10</td></tr><tr><td>汽车</td><td>67</td><td>8</td><td>4</td><td>3</td><td>0</td><td>2</td><td>2</td><td>6</td><td>1</td><td>7</td></tr><tr><td>财经</td><td>2</td><td>73</td><td>5</td><td>3</td><td>3</td><td>4</td><td>1</td><td>2</td><td>5</td><td>2</td></tr><tr><td>IT</td><td>5</td><td>4</td><td>69</td><td>2</td><td>3</td><td>8</td><td>1</td><td>3</td><td>2</td><td>3</td></tr><tr><td>健康</td><td>7</td><td>4</td><td>3</td><td>57</td><td>10</td><td>4</td><td>2</td><td>5</td><td>3</td><td>5</td></tr><tr><td>体育</td><td>0</td><td>2</td><td>2</td><td>0</td><td>92</td><td>1</td><td>1</td><td>0</td><td>2</td><td>0</td></tr><tr><td>旅游</td><td>1</td><td>4</td><td>2</td><td>1</td><td>6</td><td>78</td><td>3</td><td>1</td><td>2</td><td>2</td></tr><tr><td>教育</td><td>2</td><td>6</td><td>1</td><td>9</td><td>2</td><td>1</td><td>62</td><td>5</td><td>6</td><td>4</td></tr><tr><td>招聘</td><td>3</td><td>3</td><td>3</td><td>1</td><td>2</td><td>1</td><td>1</td><td>84</td><td>1</td><td>1</td></tr><tr><td>文化</td><td>2</td><td>4</td><td>5</td><td>5</td><td>8</td><td>7</td><td>11</td><td>4</td><td>55</td><td>9</td></tr><tr><td>军事</td><td>1</td><td>2</td><td>1</td><td>1</td><td>2</td><td>2</td><td>1</td><td>1</td><td>1</td><td>88</td></tr></table></body></html>

由表2所示，通过算法聚类后，得到Purity=0.307。当 $\mathrm { K } { = } 1 0$ 时，聚类的结果如表3所示。

可以看出，聚类个数 $\mathrm { K } { = } 1 0$ 时Purity=0.725。这说 明随着聚类个数的增多，聚类的结果越来越准确。

选取K-means $\mathrm { \cdot } \mathrm { \mathrm { T C U S S ^ { [ 1 6 ] } } }$ 以及本文提出的SCBSS三种方法进行实验，并将聚类个数设置为4、5、6、7、8、10，对于不同的聚类数量各重复实验10次，然后取Purity值的平均数集 $\scriptstyle \mathrm { C ( P ) = \sum f / 1 0 }$ ，计算结果如表4所示。

表3 $\mathrm { K } { = } 1 0$ 时聚类结果  
表4三种聚类算法的Purity 值对比  

<html><body><table><tr><td>聚类数量</td><td>K-means</td><td>TCUSS</td><td>SCBSS</td></tr><tr><td>4</td><td>0.296</td><td>0.303</td><td>0.307</td></tr><tr><td>5</td><td>0.272</td><td>0.411</td><td>0.439</td></tr><tr><td>6</td><td>0.371</td><td>0.506</td><td>0.565</td></tr><tr><td>7</td><td>0.433</td><td>0.517</td><td>0.688</td></tr><tr><td>8</td><td>0.466</td><td>0.513</td><td>0.706</td></tr><tr><td>10</td><td>0.483</td><td>0.504</td><td>0.725</td></tr></table></body></html>

如表4所示,SCBSS算法为本文的算法，TCUSS、K-means为人工方式构建。结果表明，SCBSS算法的纯度有明显提高。并且当聚类数量较少时，算法的Purity值并不高，但是随着聚类数量的增多，Purity值有显著提升。由于 SCBSS 算法采用概念列表示文本,并基于《同义词词林》语义相似度计算方法对文本进行相似度计算，解决了基于向量空间模型的文本聚类算法中数据维数过高和相似度矩阵稀疏等问题，也解决了文本中包含的近义词和多义词问题，从而提高了聚类的效果和质量。但是，在对表征本文关键词的选取过程中由于个人主观因素的差异导致关键词选取不准确，聚类结果的精确度计算出现偏差；另外，《同义词词林扩展版》作为一种语义资源，存在未登录词的问题，互联网语料库中很多新词需要人工标示其相似度，由此也会影响聚类结果。以上问题也是今后研究的重点。

# 5结语

本文提出基于语义相似度的文本聚类方法SCBSS。首先，对文本进行预处理，提取出文本的特征词，利用《同义词词林扩展版》进行词语间的语义相似度计算，以此作为计算文本间相似度的依据，并构造文本相似度矩阵。其次，对相似度矩阵进行规范化，求得最大特征值以及对应的特征向量，并构造特征向量矩阵。最后，使用谱聚类方法对新的特征向量构成的矩阵进行聚类，完成文本的划分。相对于基于本体的方法计算语义相似度，本文提出的基于《同义词词林扩展版》的语义相似度计算方法的计算结果更加准确。利用本文提出的谱聚类方法，解决了传统聚类算法数据维数过高和矩阵稀疏等问题。实验结果表明，SCBSS可以充分挖掘聚类中文本之间的语义相似度，同时提高了聚类结果的质量。

# 参考文献：

[1]王鹏，高铖，陈晓美．基于LDA 模型的文本聚类研究[J]. 情报科学，2015，33(1):63-68.(Wang Peng，Gao Cheng, Chen Xiaomei.Research on LDA ModelBased on Text Clustering[J]. Information Science,2015,33(1):63-68.)   
[2] 顾晓雪，章成志．结合内容和标签的Web 文本聚类研究[J] 现代图书情报技术，2014(11):45-52.(Gu Xiaoxue,Zhang Chengzhi.Using Content and Tags for Web Text Clustering [J].New Technology of Library and Information Service, 2014(11): 45-52.)   
[3]赵辉，刘怀亮．面向用户生成内容的短文本聚类算法研究 [J]．现代图书情报技术，2013(9):88-92.(Zhao Hui,Liu Huailiang.Research on Short Text Clustering Algorithm for User Generated Content [J]. New Technology of Library and Information Service,2013(9): 88-92.)   
[4]柴春梅．互联网短文本信息分类关键技术研究[D]．上海: 上海交通大学,2009.(Chai Chunmei.The Key Technology Research on Internet Short Text Information Classification [D]. Shanghai: Shanghai Jiaotong University,2009.)   
[5]张文秀，朱庆华．领域本体的构建方法研究[J]．图书与情 报，2011(1):16-19，40.(Zhang Wenxiu，Zhu Qinghua. Research on Construction Methods of Domain Ontology [J]. Library and Information,201l(1): 16-19,40.)   
[6]行小帅，潘进，焦李成．基于免疫规划的 K-means 聚类算 法[J]．计算机学报,2003,26(5):605-610.(Xing Xiaoshuai, Pan Jin, Jiao Licheng.A Novel K-means Clustering Based on the Immune Programming Algorithm [J]. Chinese Journal of Computers,2003,26(5): 605-610.)   
[7]刘端阳，王良芳.基于语义词典和词汇链的关键词提取算法 [J]．浙江工业大学学报，2013，41(5):545-551．(Liu Duanyang,Wang Liangfang.Keywords Extraction Algorithm Based on Semantic Dictionary and Lexical Chain [J]. Journal of Zhengjiang University of Technology，2013，41(5): 545-551.)   
[8]刘宏哲，须德.基于本体的语义相似度和相关度计算研究 综述[J]．计算机科学,2012,39(2):8-13.(Liu Hongzhe,Xu De. Ontology Based Semantic Similarity and Relatedness Measures Review [J]. Computer Science,2012,39(2): 8-13.)   
[9]Fernandez-Amoros D,Heradio R.Understanding the Role of Conceptual Relations in Word Sense Disambiguation [J]. Expert Systems with Applications,2011,38(8): 9506-9516.   
[10] Alonso I,Contreras D.Evaluation of Semantic Similarity Metrics Applied to the Automatic Retrieval of Medical Documents: An UMLS Approach [J]. Expert Systems with Applications,2016,44 (C): 386-399.   
[11] Chang JY, Lee K M.Large Margin Learning of Hierarchical Semantic Similarity for Image Classification [J]. Computer Vision and Image Understanding,2015,132: 3-11.   
[12] Hassan H,Hassan A,Emam O.Unsupervised Information Extraction Approach Using Graph Mutual Reinforcement [C]. In: Proceedings of the 20o6 Conference on Empirical Methods in Natural Language Processing.2006: 501-508.   
[13] Bae M,Kang S,Oh S.Semantic Similarity Method for Keyword Query System on RDF [J]. Neurocomputing, 2014, 146(C): 264-275.   
[14] Rada R，Mili H,Bicknell E,et al．Development and Application of a Metric on Semantic Nets [J].IEEE Transactions on Systems,Man,and Cybernetics,1989,19(1): 17-30.   
[15] Tversky A. Feature of Similarity [J]. Psychological Review, 1977, 84(4): 327-352.   
[16] Lord P W, Stevens R D, Brass A, et al. Investigating Semantic Similarity MeasuresAcross the Gene Ontology: The RelationshipBetweenSequenceand Annotation[J]. Bioinformatics,2003,19(10):1275-1283.   
[17]焦芬芬.基于概念和语义相似度的文本聚类算法[J]．计算 机工程与应用，2012，48(18):136-141．(Jiao Fenfen. Clustering Method Based on Concept and Semantic Similarity [J].Computer Engineering and Applications,2012,48(18): 136-141.)   
[18]田久乐，赵蔚．基于同义词词林的词语相似度计算方法[J]. 吉林大学学报：信息科学版，2010，28(6):602-608.(Tian Jiule,Zhao Wei. Words Similarity Algorithm Based on Tongyici Cilin in Semantic Web Adaptive Learning System [J]. Journal of Jilin University: Information Science Edition, 2010,28(6):602-608.)   
[19]王刚，邱玉辉．基于本体及相似度的文本聚类研究[J]．计 算机应用研究，2010，27(7):2494-2497.(Wang Gang，Qiu Yuhui. Study on Text Clustering Based on Ontology Similarity [J]．Application Research of Computers，2010, 27(7): 2494-2497.)   
[20] Xiong S,Ji D.Exploiting Flexible-constrained K-means Clustering with Word Embedding for Aspect-phrase Grouping [J]. Information Sciences,2016,367-368: 689-699.   
[21] Zhuo Z,Zhang X,Niu W,et al. Improving Data Field Hierarchical Clustering Using Barnes-Hut Algorithm [J]. Pattern Recognition Letters,2016,80(1): 113-120.   
[22] Kumar K M,Reddy A R M. A Fast DBSCAN Clustering Algorithm by Accelerating Neighbor Searching Using Groups Method [J].Pattern Recognition,2016,58:39-48.   
[23]YildirimA A,Ozdogan C.Parallel WaveCluster:A Linear Scaling Parallel Clustering Algorithm Implementation with Application to Very Large Datasets [J]. Journal of Parallel and Distributed Computing,2011,71(7): 955-962.   
[24] Langone R,Agudelo O M,De Moor B,et al. Incremental Kernel Spectral Clustering for Online Learning of Nonstationary Data [J]. Neurocomputing,2014,139(2): 246-260.   
[25] Yang Y,Wang Y, Xue X.A Novel Spectral Clustering Method with Superpixels for Image Segmentation [J]. International Journal for Light and Electron Optics,2016,127(1): 161-167.   
[26]Chifu A-G,Hristea F,Mothe J,et al.Word Sense Discrimination in Information Retrieval:A Spectral Clustering-based Approach [J]. Information Processing & Management,2015,52(2): 16-31.   
[27]NgAY,ZhengAX,Jordan MI.Stable Algorithms forLink Analysis[C].In: Proceedings of the 24th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval, 20o1:258-266.   
[28]Singh K,Shakya H K,Biswas B.Clustering of People in Social Network Based on Textual Similarity [J].Perspectives in Science,2016,8:570-573.   
[29]吕立辉，梁维薇，冉蜀阳．基于词林的词语相似度的度量 [J]．现代计算机,2013(1):3-6,9.(Lv Lihui,Liang Weiwei, Ran Shuyang.A Method for Measuring Word Similarity Based on Cilin [J].Modern Computer,2013(1):3-6,9.)   
[30]孙爽，章勇．一种基于语义相似度的文本聚类算法[J]．南 京航空航天大学学报，2006,38(6):712-716.(Sun Shuang, Zhang Yong. Clustering Method Based on Semantic Similarity [J].Journal of Nanjing University of Aeronautics & Astronautics,2006,38(6):712-716.)   
[31] Ng A Y,Jordan M L，Weiss Y. On Spectral Clustering: Analysis and an Algorithm[A]. // Advances in Neural Information Processing Systems[M]. Cambridge,MA:MIT Press,2002.

# 作者贡献声明：

毕强：提出研究命题及研究思路;  
刘健：论文撰写及最终版本修订，数据处理及实证研究;  
鲍玉来：论文修改。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: tomosliu9999@126.com。  
[1]刘健，毕强.Resoures.csv.文章分词统计表.  
[2]刘健，毕强.Similarity.csv.文章相似度计算结果.  
[3]刘健，毕强.SimilarityQuestionnaire.doc．相似度调查表.  
[4]刘健，毕强.Result.csv.文章聚类结果统计表.  
[5]刘健，毕强.PurityResult.csv.文章聚类Purity 值统计表.

收稿日期:2016-09-12  
收修改稿日期:2016-10-24

# A New Text Clustering Method Based on Semantic Similarity

Bi QianglLiu Jian'Bao Yulai1,2 1(School of Management, Jilin University, Changchun 130022, China) 2 (Inner Mongolia University Library, Hohhot 010021, China)

Abstract: [Objective]This paper proposes an algorithm based on semantic similarity to extract more information from the textualresources.[Methods]First, we calculated thesemantic similarityof words with the Extended Dictionaryof Synonyms,and then created a semantic similarity matrix.Second,we clustered the texts based on the new semantic similarity matrix.[Results]The proposed algorithm was examined with text corpus from Fudan University and the search engine Sogou. Compared to the traditional methods,the proposed algorithmachieved the highest precision rates and purity values (cluster numbei $\scriptstyle 1 = 1 0 ^ { \cdot }$ ). [Limitations] Some partial similarity calculation results were manually adjusted due to the incomplete coverage of the Tongyici Cilin Extened Edition.[Conclusions] The proposed algorithm could extract more latent information from the texts，which is an effctive method to cluster and recommend textual documents.

Keywords:Tongyici Cilin Extended Edition Semantic similaritySpectrum clustering Text mining

# ClarivateAnalytics发布2016年高被引研究人员

2016年11月中旬，曾经是Thomson Reuters 的知识产权与科学业务的Clarivate Analytics 公司发布了年度高引用研究人员列表。该列表是引用分析的结果，给出了一些科学家名单，这些科学家的研究在他们各自的研究领域在全球有着重大的影响。

本次引用分析根据 2004年1月至2014年12月这11年期间的高被引文献，选择了21个自然科学和社会科学领域的共3000 多名研究人员。由来自Clarivate Analytics的文献计量专家根据数据进行分析得出结果。该引用分析使用世界领先的基于网络的研究分析平台InCitesTM Essential Science IndicatorsSM，基于科学绩效指标、来自 Web of ScienceTM的学术论文发表数量和引用数据这些趋势数据。

Clarivate Analytics 出品的高被引研究人员数据是世界大学学术排名(htp://www.sanghairanking.com/index.html)的关键组成部分，是全球顶尖大学中历史最悠久且最有影响力的年度调查之一。德国马克斯普朗克学会科学和创新研究部门文献计量学和社会学家Lutz Bommann 认为,“在定量研究评估领域，几乎没有另一个免费访问的数据库，可以像Clarivate Analytics 出品的高被引研究人员列表那样为研究人员带来如此高的声誉。”

Clarivate 负责人Jessica Turmer表示:“我们的高引用研究人员名单在学术和科学界赢得了全球尊重，我们感到很自豪。”访问http://hcr.stateofinnovation.thomsonreuters.com 可以查看 2016 年高被引研究人员名单。

(编译自:https://librarytechnology.org/news/pr.pl?id=22031)

(本刊讯)