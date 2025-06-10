# 基于流形学习的新闻主题关系构建和演化研究

徐月梅」李　杨2,梁　野」蔡连侨」1(北京外国语大学计算机系 北京 100089)2(中国科学院信息工程研究所北京 100093)3(中国科学院大学北京 100049)

摘要：【目的】通过对以互联网为媒介的新闻报道的主题演化研究，分析新闻主题的产生、发展和演变过程，把握媒体舆论方向。【方法】引入流形学习构建全局时间跨度的新闻主题关联关系，挖掘由LDA主题模型识别得到的各个时间窗口的高维主题向量间的关系，在低维平面上实现主题聚类和相互关联的可视化，提出利用社会网络理论指标分析主题的演化结果。【结果】利用2015年美国有线电视新闻网对中国的新闻报道进行主题关系构建和演化，结果表明该方法能够发现主题在全局时间跨度的演化趋势。【局限】时间窗口长度对主题演化的效果和可变时间窗口长度机制没有涉及。【结论】新闻主题演化分析方法能够在低维可视平面上描绘主题在全局时间跨度的演化，避免主题由于相邻时间窗口关联失效而导致全局演化路径的断裂。

关键词：潜在狄利克雷分配模型 流形学习 主题关联主题演化

分类号：TP393 G354

# 1引言

随着信息技术的发展，互联网已成为信息传播的重要渠道，被公认为是继报纸、广播、电视之后的"第四媒体"1]。研究以互联网为媒介的西方主流媒体对中国的新闻报道，有助于了解西方媒体中的中国形象，把握国外舆论的发展方向。新闻报道的主题演化是指新闻报道的主题内容与强度在研究过程中变化的现象，一般经历从提出、发展、衰亡到最后结束的过程。例如天津塘沽大爆炸事件，美国主流媒体有线电视新闻网(Cable News Network,CNN)2015 年8月13 号第一次进行报导，随后在14-21号每天都有相关新闻追踪，而27号是最后一次报导，意味着该事件主题的结束。可见，随着时间的变化，西方媒体对中国的新闻报道主题也随着变迁，如何描述新闻主题的演变过程是目前研究的难点[2]。

潜在狄利克雷分配(Latent Dirichlet Allocation,LDA)模型[3是模拟文档生成过程的主题模型，其参数空间的规模与文档数量无关，适合处理大规模语料，因此近年来成为主题演化研究的重要途径之一。常见的思路是利用LDA模型获取不同时间段的主题及其关键词，将相邻时间窗口的主题根据关键词的近似程度采取阈值法[4或最大相似度法[5]进行关联，再从相邻时间窗口建立的主题关联关系观察多个时间窗口的主题演变。

然而，基于相邻时间窗口的主题演化分析方法不能直接应用于新闻报道的主题演化，原因有两点。首先，基于相邻时间窗口的主题演变关系建立容易因为某个相邻窗口的主题关联出错而导致整个主题链的演变失效。例如，某个主题的演变经过时间窗口[t1,t2,t3,t4]，但由于在[t2,t3]相邻时间窗口内该主题的关联出错(可能由于阈值设置过大或者相似度计算有误)使得该主题的全局演变过程断裂。其次，新闻报道的主题具有突发性和时间间隔性，使得新闻主题的演化规律并不一定遵循相邻时间窗口跨度。例如 2015年6月CNN网站针对中国南海问题进行相关报道，在间隔7月、8月之后，9月和10月又有中国南海问题的相关报道，可见新闻报道主题的演化时间跨度具有不确定性。

针对上述两个问题，本文提出将流形学习(ManifoldLearning)引入到新闻主题的关系构建和演化研究，定义新闻主题的演化关系并不局限于传统的相邻时间间隔的主题演化，而是从全局时间跨度分析两个主题的关联关系。通过从整体上对各个时间窗口内的主题进行关联分析，以期获得主题在全局时间上的演变关系。经过LDA模型抽取得到的主题表现为高维度的特征词向量，采用现有的相似度计算方法进行全局时间上的主题关联因为"高维数灾难"7而变得十分困难。例如有5个时间窗口，每个时间窗口有10个主题，每个主题的向量维度为1000维，利用相似度方法进行全局时间上的主题关联需要 $\boldsymbol { 4 \times 1 0 } ^ { 7 }$ 时间复杂度1 $( 5 - 1 ) \times 1 0 \times 1 0 ^ { 3 } \times 1 0 ^ { 3 } \ \mathrm { { ; } }$ 。而流形学习技术可以挖掘高维主题向量之间隐藏的关联关系，找到高维空间中的低维流形，并求出主题在相应的低维空间的嵌人映射，实现维数约简和可视化，使得进一步利用社会网络分析相关指标分析主题演变规律变为可能。本文的创新点与贡献总结如下：

(1）借鉴图像处理和机器学习领域中的非线性降维思想，引入流形学习方法挖掘由LDA模型抽取得到的各个时间窗口的高维主题向量，一方面在低维平面上可视化高维主题向量间的关系，另一方面将非线性降维的结果与余弦相似度结合，重新定义低维平面上主题之间的距离，实现全局时间窗口的主题关联。

(2）高维主题向量经非线性降维后表现为一个小型的社会网络：主题表征为低维平面上的节点，节点的远近反映主题之间的距离，节点的边为主题的关联边。因此利用社会网络理论的4种度量指标来分析主题的演化，识别主题演化过程中影响力大的主题、活跃的主题以及主题演化网络的整体属性等。

(3）以美国CNN网站对中国的相关新闻报道为例验证了所提方法的有效性和准确性

# 2相关研究工作

早期对主题演化的研究主要是将文档的时间信息引人到LDA模型或其变形模型中，并利用连续的时间信息指导文档集中主题的分布，如连续时间模型TOT[8]、动态主题模型DTM[9]。但该方法无法对新文档进行扩展，新文档加入后必须重新建模。

近年来对主题演化研究主要有两种思路：一种是先对整个文档集合运用LDA获取主题，再从时间上将主题划分为各个子集，分析主题在各个子集上的分布从而得到主题的演化规律[10]。另一种是先对整个文档集合按照时间信息离散到各个时间窗口，再利用LDA获取各个时间窗口内的主题，最后将相邻时间窗口的主题关联，得到主题演化过程[2.4-5,11]。这两种方法各有其局限性。前一种方法依赖于时间粒度的选取，时间粒度的取值直接影响演化的准确性。后一种方法中，相邻时间窗口的主题关联是分析主题演化的重要步骤，不同的关联方法将得到不同的演化结果。例如，楚克明等[2通过计算相邻时间段中任意两个主题的特征向量相似度实现主题关联度分析，该方法对阈值大小比较敏感并且阈值的确定需要较强的专业知识。崔凯等[11]使用KullbackLeibler 相对熵来计算主题的相似性从而建立关联，但得到的主题演化都是一对一的，与科学研究中主题的融合、交叉等现象不完全吻合。

此外，为了提高阈值法或相似度法的主题关联准确性，相关文献提出了特征词过滤[12]和主题关联过滤的方法[13]。由阈值法或相似度法建立主题关联后，定义过滤规则去除无效的关联来提高主题关联的准确性，但其效果的提高过度依赖于过滤规则的定义，过滤规则对于不同领域的主题不具有普适性。

总体而言，不管是先获取主题再从时间上划分子集分析主题演化，还是先划分时间窗口再获取主题从而得到主题演化，现有研究都是从相邻时间窗口构建主题的演化关系。一方面容易因为相邻窗口内的主题关联出错使得全局演化过程断裂；另一方面新闻报道主题演化的时间跨度具有随机性，不一定遵循相邻时间窗口的跨度。

为了解决上述两个问题，本文从一个全新的角度，首次引人流形学习方法从全局时间跨度、而非相邻时间窗口跨度构建新闻的主题关系，并利用社会网络相关分析指标衡量主题演化的结果。流形学习近年来被广泛应用在数据挖掘、机器学习、模式识别等领域，其作为解决非线性降维问题的方法，在挖掘高维数据集的固有特征分布和结构特点方面具有优势[6]。经过LDA抽取的主题表征为非线性、高维度的特征词向量，若采用现有的相似度计算方法将由于“高维数灾难"难以进行全局时间跨度的主题关联，而流形学习能够挖掘高维度主题向量之间蕴含的关联关系，将其映射到低维空间，使得全局时间跨度的新闻主题关系构建和主题演化分析变为可能。

# 3基于流形学习的新闻主题关系构建和演化分析

# 3.1 基本思路

本文提出的基于流形学习的新闻主题演化关系构建和演化方法的基本流程如图1所示：

![](images/14c3eb37f74fa4d789b00ffcfbb5fa50f66682b92aadae9ddc00cc180917d134.jpg)  
图1基于流形学习的新闻主题演化方法流程图

(1）将时间序列划分为若干个长度固定的时间窗□，根据时间将文本划入到相应的时间窗口，利用LDA模型抽取每个时间窗口的主题，并将主题表示为高维特征词向量的形式。

(2）将得到的多个高维主题向量利用流形学习算法进行非线性降维，获得每个主题向量的低维度嵌入变量以及主题关联边。

(3）为主题关联边赋予权重，确定主题间的关联  
关系。(4）利用社会网络指标分析主题关联关系，分析  
主题的演化特征。(5）得到新闻主题演化结果。

# 3.2 新闻主题的定义和识别

新闻报道的主题表现为媒体对某一特定事件及其所有相关事件的集合(简称主题)。给定D个新闻报道文本，用集合 $\mathbf { C } = \{ \mathrm { d } _ { 1 } , \mathrm { d } _ { 2 } , \cdots , \mathrm { d } _ { \mathrm { D } } \}$ 表示。 $\mathrm { \Delta V }$ 为所有文本不相同单词构成的词汇集合。将主题定义为一组语义上相关的词及词语主题相关的权重的向量表示[13]:

$$
\mathrm { { T } = \{ ( v _ { 1 } , p _ { 1 } ) , ( v _ { 2 } , p _ { 2 } ) , \cdots , ( v _ { k } , p _ { k } ) , \cdots , ( v _ { | V | } , p _ { | V | } ) \} }
$$

其中， $\mathbf { v } _ { \mathbf { k } } \in \mathbf { V }$ 是与主题 $\mathrm { \Delta T }$ 相关的词, $\mathsf { p } _ { \mathrm { k } }$ 是主题T在该词上的分布概率。

将时间序列划分为 $\mathfrak { n }$ 个长度为L的时间窗口，依据时间将集合C中新闻报道划分到相应的时间窗口,$\mathrm { C } _ { \mathrm { t } }$ 表示时间窗口t的新闻报道集合。采用LDA模型对 $\mathrm { C } _ { \mathrm { t } }$ ， $\mathfrak { t } \in [ 1 , \mathfrak { n } ]$ 抽取主题。LDA模型是一个三层贝叶斯文本主题生成模型，可以发现任何离散数据中潜在的主题结构。其基本思想是：假设文档由若干个潜在主题的混合组成，而每个主题由若干个词的分布刻画。

LDA设立参数 $\alpha$ 作为文本集合的主题先验超参数，β为主题集合的词汇先验超参数，使得每篇文本服从参数为 $\alpha$ 的Dirichlet分布，每个主题服从参数为β的Dirichlet分布。给定文本集合，根据Gibbs采样[14]计算出文本-主题概率分布θ和主题-词分布 $\boldsymbol { \Phi }$ 如下:

$$
\theta _ { \mathrm { m i } } = \frac { \displaystyle \mathsf { n } _ { \mathrm { m } } ^ { ( \mathrm { i } ) } + \alpha } { \displaystyle \sum _ { \mathrm { j } = 1 } ^ { | \mathrm { S } | } \mathsf { n } _ { \mathrm { m } } ^ { ( \mathrm { j } ) } + | \mathrm { S } | \alpha } \quad \mathrm { m } \in [ 1 , \mathrm { D } ] , \mathrm { i } \in [ 1 , | \mathrm { S } | ]
$$

$$
\displaystyle \Psi _ { \mathrm { i k } } = \frac { \displaystyle \mathrm { n } _ { \mathrm { i } } ^ { ( \mathrm { k } ) } + \alpha } { \displaystyle \sum _ { \mathrm { j = 1 } } ^ { | \mathrm { V } | } \mathrm { n } _ { \mathrm { i } } ^ { ( \mathrm { j } ) } + | \mathrm { V } | \alpha } \quad \mathrm { i } \in [ 1 , | \mathrm { S } | ] , \mathrm { k } \in [ 1 , | \mathrm { V } | ]
$$

其中， $\Theta _ { \mathrm { m i } }$ 为文本 ${ \bf d } _ { \mathrm { m } }$ 属于主题 $\mathrm { T _ { i } }$ 的概率， $ { \mathtt { n } } _ { \mathrm { m } } ^ { \mathrm { ( i ) } }$ 表示文本 ${ \bf d } _ { \mathrm { m } }$ 中赋予主题 $\mathrm { T _ { i } }$ 的词的总数。 $\varphi _ { \mathrm { i k } }$ 为主题 $\mathrm { T _ { i } }$ 出现单词 $\mathbf { v _ { k } }$ 的概率， ${ \mathfrak { n } } _ { \mathrm { i } } ^ { ( \mathrm { k } ) }$ 表示词 $\mathbf { v } _ { \mathrm { k } }$ 被赋予主题 $\mathrm { T _ { i } }$ 的总次数。S为LDA抽取的主题集合。

结合公式(1)的定义和 LDA 模型，笔者将时间窗□ $\mathrm { ~  ~ \Omega ~ } _ { \mathrm { ~ t ~ } }$ 内文档集合 $\mathrm { C } _ { \mathrm { t } }$ 的主题表示为：

$$
\mathrm { T _ { t i } = \{ ( v _ { l } , \Phi _ { t i l } ) , ( v _ { 2 } , \Phi _ { t i 2 } ) , \cdots , ( v _ { k } , \Phi _ { t i k } ) , \cdots , ( v _ { | V | } , \Phi _ { \Phi _ { t i | V | } } ) \} }
$$

其中, $1 \leqslant \mathrm { i } \leqslant \mathrm { S } _ { \mathrm { t } }$ ， $\mathbf { S } _ { \mathrm { t } }$ 为时间窗口t内的主题数目,$\mathrm { T _ { t i } }$ 的向量维度为 $\mid \mathrm { V } \mid$ 维。 $\mathbf { v } _ { \mathrm { k } } \in \mathrm { V }$ ， $\Phi _ { \mathrm { t i k } }$ 由LDA 模型计算得到，为主题 $\mathrm { T _ { t i } }$ 出现单词 $\mathbf { v _ { k } }$ 的概率。

每个时间窗口内的新闻报道数不同，相应的主题数也随之动态变化。 $\mathbf { S } _ { \mathrm { t } }$ 的最佳值采用统计语言模型中常用的评价标准—困惑度(Perplexity)[15]进行选取,计算如下:

$$
\mathrm { P e r p l e x i t y } ( \mathbf { C } _ { \mathrm { t } } ) = \exp \{ - \frac { \displaystyle \sum _ { m = 1 } ^ { | C _ { \mathrm { t } } | } \ln \mathrm { P } ( \mathbf { d } _ { \mathrm { m } } ) } { \displaystyle \sum _ { m = 1 } ^ { | C _ { \mathrm { t } } | } \mathrm { N } _ { \mathrm { m } } } \}
$$

其中， $\Nu _ { \mathrm { { m } } }$ 表示第 $\mathrm { ~ m ~ }$ 篇新闻报道的长度， $\mathrm { P ( d _ { m } ) }$ 表示模型产生第 $\mathbf { m }$ 篇新闻报道的概率。困惑度的值越小，性能越好。在其他参数确定的情况下，通过对 $\mathbf { S } _ { \mathrm { t } }$ 取不同值进行困惑度的计算和分析，选取得到最优主题数目的 $\mathbf { S } _ { \mathrm { t } }$ 值。

对 $\mathfrak { n }$ 个时间窗口分别抽取主题，笔者将总的主题集合TopicSet以及总主题数S定义为：

$$
\mathsf { p i c S e t } = ( \mathrm { T } _ { 1 1 } , \mathrm { T } _ { 1 2 } \cdots ; \cdots ; \mathrm { T } _ { \mathrm { t } 1 } , \mathrm { T } _ { \mathrm { t } 2 } \cdots ; \mathrm { T } _ { \mathrm { n } 1 } , \mathrm { T } _ { \mathrm { n } 2 } \cdots )
$$

$$
\mathrm { \bf S } = \sum _ { \mathrm { { t } = 1 } } ^ { \mathrm { n } } \mathrm { \bf S } _ { \mathrm { t } }
$$

# 3.3基于流形学习的主题演化关系构建

主题演化反映了主题变化的过程，主题的演化在时间上存在延续性。对 $\mathfrak { n }$ 个时间窗口的文本经LDA识别，得到的主题表现为S个 $\mid \mathrm { V } \mid$ 维的特征词向量，当$\mid \mathrm { V } \mid$ 较大时使得挖掘主题间的演化关系变得困难。本文利用流形学习对高维度的主题向量进行降维，并构建主题演化关系。

流形学习是一种非线性降维方法，可用于处理高维数据，通过对高维空间的特征数据学习以获得低维的隐变量模型，即找到高维空间中的低维流形，以实现维数约简和可视化。图2展示了高维流形与低维映射的关系，在三维空间中的"瑞士蛋卷"数据分布模型，经过降维后在二维平面上显示各个数据点的关系[16]

![](images/7df2ed6f3325ae7494c519c7ad7c35edacc897dba0907d618c6e877eb7d446e5.jpg)  
图2高维流形向低维空间的映射

流形学习的典型实现方法包括等距特征映射(Isometric Feature Mapping,ISOMAP)[17|和局部线性嵌入(Locally Linear Embedding，LLE)[18]等。本文采用

ISOMAP算法，该算法主要思想是利用局部邻域的欧氏距离近似计算数据点之间的全局流形测地线距离，通过建立原数据之间的测地线距离与降维数据间的空间距离的对等关系从而实现降维。ISOMAP在降维过程中通过计算点与点之间的测地距离，并采用多维标度法(Multi-Dimensional Scaling，MDS)[17来获取全局最优的几何结构，从而准确发现数据流形潜在的参数空间。

为了得到高维主题向量 $\mathrm { T _ { t i } }$ 的特征，需要在欧式空间 $\operatorname { R } ^ { \mathrm { d } }$ 找到一个低维度区域 $\mathrm { Y _ { t i } }$ 反映 $\mathrm { T } _ { \mathrm { t i } } \in \mathbf { R } ^ { | \mathrm { V } | }$ 的特征,通常 $\mathrm { \Delta } \mathrm { d } < < | \mathrm { \Delta } \mathrm { V } |$ 。笔者将主题 $\mathrm { T _ { t i } }$ 在欧式空间 $\operatorname { R } ^ { \mathrm { d } }$ 的低维度嵌人变量 $\mathrm { Y _ { t i } }$ 定义为：

$$
\mathrm { Y _ { t i } } = \{ \mathrm { y _ { t i } } ( 1 ) , \mathrm { y _ { t i } } ( 2 ) , \cdots , \mathrm { y _ { t i } } ( \mathrm { d } ) \} | \mathrm { Y _ { t i } } \in \mathrm { R ^ { d } }
$$

其中，d是 $\mathrm { Y _ { t i } }$ 的维度。算法1将上述S个 $\mid \mathrm { V } \mid$ 维（2 $( | \mathrm { \Delta V } | \mathrm { > } > 1$ )的主题向量集合TopicSet进行基于ISOMAP的高维主题向量降维。取维度空间d为2，笔者将TopicSet在二维平面的嵌入变量定义为：

$$
( \mathrm { Y } _ { 1 1 } , \mathrm { Y } _ { 1 2 } \cdots ; \cdots ; \mathrm { Y } _ { \mathrm { t 1 } } , \mathrm { Y } _ { \mathrm { t 2 } } \cdots ; \mathrm { Y } _ { \mathrm { n 1 } } , \mathrm { Y } _ { \mathrm { n 2 } } \cdots )
$$

其中， $\mathrm { Y _ { t i } }$ 为 $\mathrm { T _ { t i } }$ 的低维嵌入变量，可在二维平面显示，有利于直接观察主题之间的演化关系。

算法1 基于ISOMAP的高维主题降维算法

输入：TopicSet;

输出：每个主题向量 $\mathrm { T _ { t i } }$ 的低维度嵌入变量 $\mathrm { Y _ { t i } }$ 和 $\mathrm { Y _ { t i } }$ 的 邻域图邻接矩阵E;

执行：

$\textcircled{1}$ 建立每个主题 $\mathrm { T _ { t i } }$ 的邻域图。

根据主题向量之间的距离，确定主题集合中哪些主题为邻居主题。计算所有主题之间的欧氏距离 ${ \bf d } _ { \mathrm { T } } ( \mathrm { i } , \mathrm { j } )$ ，确定每个主题的K个最近主题,K为可输入变量。这些主题的邻居关系被描述在一个覆盖采样点的带权图G中，主题之间的关系以链路权重 ${ \bf d } _ { \mathrm { T } } ( \mathrm { i } , \mathrm { j } )$ 表示。

$\textcircled{2}$ 计算图G中主题之间的测地线距离。

根据步骤 $\textcircled{1}$ 确定的图G和两两主题之间的链路权重${ \bf d } _ { \mathrm { T } } ( \mathrm { i } , \mathrm { j } )$ ，计算所有主题之间的最短路径 $\mathrm { d } _ { \mathrm { G } } ( \mathrm { i } , \mathrm { j } )$ ，并以此来估算流形内所有主题之间的测地线距离。

$\textcircled{3}$ 构建低维度的嵌入变量 $\mathrm { Y _ { t i } }$ 和 $\mathrm { Y _ { t i } }$ 的邻域图邻接矩阵E。

对于步骤 $\textcircled{2}$ 得到的所有主题之间的最短路径距离矩阵$\mathrm { D } _ { \mathrm { G } } = \{ \mathrm { d } _ { \mathrm { G } } ( \mathrm { i } , \mathrm { j } ) \}$ ，应用多维标度法进行降维，创建位于d-维欧氏空间内的低维嵌入变量 ${ \mathrm { Y } } _ { \mathrm { t i } }$ 和 $\mathrm { Y _ { t i } }$ 的邻域图邻接矩阵E。

降维后得到每个主题的低维度嵌入变量 $\mathrm { Y _ { t i } }$ 和低维度嵌入变量的邻接矩阵E。其中， $\mathrm { Y _ { t i } = ( x _ { t i } , y _ { t i } ) }$ ，${ \bf { X } } _ { \mathrm { { t i } } }$ 和 $\mathrm { \Delta y _ { t i } }$ 为主题 $\mathrm { Y _ { t i } }$ 在二维平面的横坐标和纵坐标值,

E为0-1矩阵。每个主题 $\mathrm { T _ { t i } }$ 表征为二维平面上的一个点，节点在二维平面上的分布由高维主题向量的测地线距离决定，反映了主题之间的相似程度。节点越密集表示具有演化关系的相似主题越多，反之则越少。为了建立全局时间跨度的主题关联，笔者基于余弦相似度[19]，在二维平面上重新定义任意两个时间窗口内的主题距离为：

$$
\begin{array} { r l } & { \mathrm { S i m } ( \mathrm { Y } _ { \mathrm { t i } } , \mathrm { Y } _ { ( \mathrm { t + k } ) { \mathrm { j } } } ) = } \\ & { \left\{ \frac { { \mathrm {  ~ { \cal ~ x } _ { \mathrm { t i } } } } { \mathrm {  ~ { \cal ~ x } _ { \mathrm { \ell } } ~ } } _ { \mathrm { f } } + { \mathrm {  ~ { \cal ~ y } _ { \mathrm { t i } } } } \mathrm {  ~ { \cal ~ y } _ { ( \mathrm { t + k } ) { \mathrm { j } } } } } { \sqrt { { \mathrm {  ~ { \cal ~ x } _ { \mathrm { t i } } } } ^ { 2 } + { \mathrm {  ~ { \cal ~ y } _ { \mathrm { t i } } } } ^ { 2 } } \times \sqrt { { \mathrm {  ~ { \cal ~ x } _ { \mathrm { \ell } } ~ } } _ { \mathrm { f } } + { \mathrm {  ~ { \cal ~ y } _ { ( \mathrm { t + k } ) { \mathrm { j } } } } } ^ { 2 } } } \quad \mathrm { E } ( \mathrm { I } _ { \mathrm { t i } } , \mathrm { I } _ { ( \mathrm { t + k } ) { \mathrm { j } } } ) = 1 \right. } \\ & { \left. 0 \mathrm {  ~ { \cal ~ E } ( \mathrm { I } _ { t i } , \mathrm { I } _ { ( \mathrm { t + k } ) { \mathrm { j } } } ) } = 0 \right. } \end{array}
$$

其中, $\mathrm { Y _ { t i } }$ 和 $\Upsilon _ { \left( \mathrm { t + k } \right) \mathrm { j } }$ 分别为时间窗口t和 $\mathbf { t } + \mathbf { k }$ 内的主题低维度嵌入变量， $\mathrm { i } \in \mathrm { S } _ { \mathrm { t } } , \mathrm { j } \in \mathrm { S } _ { \mathrm { t + k } }$ ， $\mathfrak { t } \in [ 1 , \mathfrak { n } - 1 ]$ $\mathrm { k } \geqslant 1 \circ \mathrm { E } ( \mathrm { I } _ { \mathrm { t i } } , \mathrm { I } _ { ( \mathrm { t + k } ) \mathrm { j } } ) = 1$ 表示主题向量 $\mathrm { Y _ { t i } }$ 和 $\Upsilon _ { \mathrm { ( t + k ) j } }$ 在低维嵌入平面上有关联边，反之则表示主题向量 $\mathrm { Y _ { t i } }$ 和$\Upsilon _ { \mathrm { ( t + k ) j } }$ 关联程度低，将其相似度赋值为 $0$ 。

# 3.4社会网络指标的主题演化分析

一个社会网络由多个点和各点之间的连线组成，“点"是各个社会行动者，“边"是行动者之间的各种社会关系。高维的主题特征向量经过ISOMAP降维表现为一个小型的社会网络：由主题节点之间的相互作用关系形成的二维平面图。其中，二维平面上节点之间的距离表征主题之间的关系和相互作用程度。因此,可借鉴社会网络理论的4种度量指标[20]来分析主题的演化，识别演化过程中影响力大的主题、活跃主题和主题演化网络的整体属性等：

(1）度(Degree)，以连接到节点的边的数目作为度量节点重要性的依据。在有向图中，节点的度包括点入度和点出度。在主题构成的有向图中，如果一个主题拥有更高的度数值，则该主题与很多其他主题存在演变关系。其中，人度值越高，则在演变过程中有越多主题指向到该主题；出度值越高，则该主题有越多延续主题。度数仅仅描述主题所产生的局部影响力，无法反映主题的全局演变情况。

(2）介数中心度(Betweeness Centrality)，以网络中经过该节点的所有点与点的最短路径的数目作为度量依据。介数中心度反映节点的信息交互能力，可用来衡量一个主题作为媒介者的能力，即占据在其他两个主题演变路径之间的交互能力。在主题的演变分析中，通过介数中心度，可以确定比较活跃的主题。

(3）密度(Density)，是一个网络图中实际存在的边数与可能存在的最多边数的比值，一般用来衡量网络图的全局凝聚力水平。在主题构成的网络图中，密度越大则主题的演变关系越复杂，演化关系越多；密度越小则主题的演变关系越简单，演化关系越少。

(4）直径(Diameter)，将网络中最长测地线的长度作为度量依据，测地线是给定两点之间最短的路径。在主题演变图中，存在多条测地线，而直径表征主题演变关系上最长的演变距离跳数。

# 4实验

为了验证基于流形学习的新闻主题关系构建和演化分析方法的有效性，实验基于GooSeeker数据爬取平台[21]从CNN网站抓取了2015年与中国相关的新闻报道作为文本集，共464篇新闻报道。对文本集的每一篇文档进行数据预处理，包括分词、剔除停用词、词形还原、词干提取、提取关键词等。

将时间序列划分为12个长度为1个月的时间窗口，根据新闻的报导时间将其划入到相应的窗口。表1列举了各时间窗口的新闻报道数以及利用公式(5)确定各个时间窗口的最优主题数。

表1数据集各时间窗口所含新闻报道数和最优主题数  

<html><body><table><tr><td>新闻报道集</td><td>文档数</td><td>最优主题数</td></tr><tr><td>2015年1月</td><td>27</td><td>5</td></tr><tr><td>2015年2月</td><td>16</td><td>5</td></tr><tr><td>2015年3月</td><td>21</td><td>4</td></tr><tr><td>2015年4月</td><td>25</td><td>6</td></tr><tr><td>2015年5月</td><td>41</td><td>5</td></tr><tr><td>2015年6月</td><td>38</td><td>6</td></tr><tr><td>2015年7月</td><td>71</td><td>7</td></tr><tr><td>2015年8月</td><td>72</td><td>6</td></tr><tr><td>2015年9月</td><td>66</td><td>6</td></tr><tr><td>2015年10月</td><td>24</td><td>6</td></tr><tr><td>2015年11月</td><td>34</td><td>5</td></tr><tr><td>2015年12月</td><td>29</td><td>5</td></tr><tr><td>总计</td><td>464</td><td>66</td></tr></table></body></html>

# 4.1 主题识别结果

利用LDA模型抽取每个时间窗口的主题，设置两个超参数为 $\mathrm { \Delta a } = 5 0 / \mathrm { L }$ ， $\beta = 0 . 0 1 ^ { [ 3 ] }$ 。选取每个主题中分布概率Top20的单词作为主题内容的特征词。表2列举了抽取的部分主题(并给出了人工总结后的主题内容)及其特征词(仅列举前10 个)。

表22015年CNN与中国相关的部分主题  

<html><body><table><tr><td>主题</td><td>主题内容</td><td>主题特征词(前10个)</td></tr><tr><td>T53</td><td>南海 军事</td><td>sea,south,island,military,navy,aircraft,flight,state,surveillance,warn</td></tr><tr><td>T64</td><td>南海 袭击</td><td>government,attack,state,sea,island,official,hack,federal, information,south</td></tr><tr><td>T104</td><td>南海 领土</td><td>island,sea,operation,reef, south,water,freedom,beijing,dispute,territorial</td></tr><tr><td>T114</td><td>习近平与马英九会面</td><td>taiwan,ma,xi,meeting,beijing,president,relation, state,Singapore,mainland</td></tr><tr><td>T23</td><td>希腊 经济</td><td>Greece,bank,currency,russia,internet,growth,financial,government,economist,money</td></tr><tr><td>T31</td><td>柴静 空气污染</td><td>state,video,chai,government,xi,president,air, pollution,authority, documentary</td></tr><tr><td>T42</td><td>市场股票</td><td>state,investor, government,market, stock,growth,global, charge,unite,economic</td></tr><tr><td>T71</td><td>股票崩盘</td><td>market, stock,economy, share,shanghai, financial, investor,trade,government,crash</td></tr></table></body></html>

从表2可看出：LDA模型能够识别每个时间窗口内的新闻报道主题，主题的类别包括军事( $\mathrm { \Delta T } _ { 5 3 }$ 、 $\mathrm { T } _ { 6 4 }$ 、$\mathrm { T } _ { 1 0 4 } )$ 、政治 $\left( \mathrm { T } _ { 1 1 4 } \right)$ 、经济 $( \mathrm { T } _ { 2 3 } , \mathrm { T } _ { 4 2 } , \mathrm { T } _ { 7 1 } ) .$ 和社会民生 $\left( \mathrm { T } _ { 3 1 } \right)$ （204号等方面。各主题中分布概率较高的主题特征词能够涵盖该主题的内容。以5月份的第3个主题为例 $( \mathrm { T } _ { 5 3 } )$ ，该主题与中国南海军事主权有关，Top10的特征词为：sea(海洋)，south(南方)，island(岛屿)，military(军事),navy(海军),aircraft(航空器),flight(飞行)，state(声明)

surveillance(监督),warn(警告)。

# 4.2基于ISOMAP流形学习的主题关联结果

根据3.3节中叙述的方法，进行基于ISOMAP 流形学习的主题关联分析。每个主题选取分布概率最高的Top20特征词，64个主题得到不重复的特征词表包括657个特征词。因此，每个主题表示为657维的特征词向量。基于算法1的流形学习步骤，将64个657维的主题向量映射在二维平面上。图3为64个主题的

ISOMAP嵌入变量输出，每一个点代表一个主题，每一条边为 ISOMAP 构建的主题邻域图中主题间的连接边。

![](images/63ad07d35cf8ea201d4411e9733e9b7cc61104b3777b71a385d40469462861f2.jpg)  
图3高维主题向量的二维ISOMAP嵌入变量 输出和关联

通过分析发现主题在二维平面上的位置与该主题的特征词和内容相关。主题在二维平面上被聚类为6大类，分别为：黄色(军事)、青色(政治)、橘色(经济)红色(科技)、蓝色(家庭/孩子)和绿色(生活)。例如，黄色节点标识的军事类主题，主要与南海领土问题、新疆恐怖主义、藏独、抗日战争胜利70周年大阅兵新闻报道相关；青色节点标识的政治类主题，主要与习主席与彭丽媛夫人出访、李克强总理访问、习主席与奥巴马总统会面、习主席访美等相关；橘色节点标识的经济类主题，主要与市场投资、中国股市泡沫、希腊债务相关；红色标识的社会科技类主题，主要与谷歌和小米等互联网公司、工业污染、波音飞机相关；蓝色节点标识的家庭/孩子类主题，主要与中国计划生育政策、二孩放开、孩子教育、张国立儿子吸毒等事件相关；绿色节点标识的生活类主题，与空气污染、柴静《穹顶之下》视频、优衣库试衣间视频等2015年引起媒体广泛讨论的民生事件相关。还有一些节点用灰色标注，这些节点较为分散，与上述6大节点簇距离较远。

可见，基于ISOMAP的非线性降维算法能够在低维嵌入平面正确表示主题之间的关联和相互作用关系；能够挖掘隐藏在高维向量间的规律、对相似的主题进行无监督学习聚类。即：基于ISOMAP的非线性降维算法对主题的聚类个数决定于主题向量之间的测地线距离，不需要根据先验知识事先确定，优于现有的依赖于算法初始值(如聚类个数和节点位置等)的聚类算法(如K-means[22])

# 4.3 主题演化结果分析

基于3.4节的方法，利用社会网络理论的度数(包括出度数和入度数)、介数中心度、密度和直径指标分析由ISOMAP算法得到的二维平面主题关联图。首先根据公式(10)为图3的每条边赋予权重，借鉴文献[4]的方法过滤权重值小于阈值的边(取阈值为0.9)，并利用Pajek软件[23]描绘主题之间的演化关系如图4所示。其中，每一个节点代表一个主题，有线弧代表主题的演化方向。如经济类主题 $\mathrm { T } _ { 2 3 }$ 和 $\mathrm { T } _ { 4 2 }$ 之间有一条弧，表示从 $\mathrm { T } _ { 2 3 }$ 演变到 $\mathrm { T } _ { 4 2 }$ 。

![](images/c879195fb1aba34405b0fe63d0042201fe15794f40681ab8519b0034297ba31e.jpg)  
图42015年CNN对中国新闻报道的主题演化关系图

节点和有向弧构成了主题的演化路径，例如从图 4的经济类主题中抽取一条路径为 $( \mathrm { T } _ { 2 3 } , \mathrm { T } _ { 4 2 } , \mathrm { T } _ { 6 3 } , \mathrm { T } _ { 7 1 } )$ 其Top3主题特征词分别为 $\mathrm { T } _ { 2 3 }$ (希腊、银行、债务） $\mathrm { T } _ { 4 2 } ( \$ 投资、市场、增长)、 $\mathrm { T } _ { 6 3 }$ (市场、股票、投资)和 $\mathrm { T } _ { 7 1 }$ (股票、经济危机、泡沫)。该路径的演变过程为：CNN在2015年2月份对经济类主题的报道与中国和俄罗斯是否干预希腊债务有关，3月份没有对经济类主题的报道，4月、6月和7月的经济类主题都与中国股票市场相关。由此可见，新闻主题的演变并不一定遵循相邻时间窗口的跨度，如 $\mathrm { T } _ { 2 3 }$ 和 $\mathrm { T } _ { 4 2 }$ 之间、 $\mathrm { T } _ { 4 2 }$ 和 $\mathrm { T } _ { 6 3 }$ 之间。

注意到5月份有涉及经济类主题的报道 $( \mathrm { T } _ { 5 2 } )$ ，但并不在 $( \mathrm { T } _ { 2 3 } , \mathrm { T } _ { 4 2 } , \mathrm { T } _ { 6 3 } , \mathrm { T } _ { 7 1 } )$ 演化路径中，而是在另一个经济类主题的演化分支 $( \mathrm { T } _ { 2 3 } , \mathrm { T } _ { 5 2 } )$ 上，这是因为 $\mathrm { T } _ { 5 2 }$ 除了涉及少量的中国股票市场泡沫的相关报道，主要涉及中俄经济、中国百万富翁增长等相关报道(参见表3列举的5月份CNN对中国经济所有相关报道的新闻标题)。若采用在相邻时间段中计算任意两个主题的特征向量相似度的方法，将会导致 $\mathrm { T } _ { 4 2 }$ 和 $\mathrm { T } _ { 6 3 }$ 之间关联出错，使得演化路径 $( \mathrm { T } _ { 2 3 } , \mathrm { T } _ { 4 2 } , \mathrm { T } _ { 6 3 } , \mathrm { T } _ { 7 1 } )$ 断裂。

根据图4的主题演化图计算每个主题的度数。表4为度数值最高和最低的4个主题。可以看出，度数值最高的4个主题是 $\mathrm { T } _ { 4 2 \setminus } \mathrm { T } _ { 6 4 \setminus } \mathrm { T } _ { 9 1 \setminus } \mathrm { T } _ { 1 2 3 } ,$ ，主题的内容(见表4加黑标注的关键词)分别为股票增长/泡沫、南海军事安全、南海恐怖主义袭击、南海防御；这些主题在主题演化关系中局部影响力较高。而 $\mathrm { T } _ { 1 2 }$ 、 $\mathrm { T } _ { 9 5 }$ 、 $\mathrm { T } _ { 5 1 }$ 和 $\mathrm { T } _ { 6 2 }$ 为度数值最低(等于0)的 4个主题,此外还有$\mathrm { T } _ { 7 4 }$ 、 $\mathrm { T } _ { 1 3 }$ 由于篇幅关系不一一列举。这些主题表现为孤立主题，大多为主题含义不明确(如 $\mathrm { T } _ { 1 2 }$ 和 $\mathrm { T } _ { 9 5 } \mathrm { \dot { } }$ 或某个事件的突发报道(如 $\mathrm { T } _ { 5 1 }$ ，神州飞船发射)。

表32015年5月CNN与中国经济相关的所有新闻标题  

<html><body><table><tr><td>新闻内容</td><td>时间</td><td>新闻标题</td></tr><tr><td>中俄经济</td><td>5月4号</td><td>Russia and China have had enough of western banking.</td></tr><tr><td>中俄经济</td><td>5月11号</td><td>China isn'tRussia'sanswerto crisis with the West.</td></tr><tr><td></td><td></td><td>中国央行 5月19 号 China's central bank is just getting started.</td></tr><tr><td>中国首富5月21号</td><td></td><td>China's richest man lost $15 billion in one hour.</td></tr><tr><td>中国首富5月22号</td><td></td><td>China's richest man bet his company's</td></tr><tr><td>中国百万</td><td></td><td>shares would fall. 5月 27号 China has more than 1 million millionaires.</td></tr><tr><td>富翁</td><td></td><td></td></tr><tr><td>中国经济 泡沫</td><td></td><td>5 月31 号 The next big bubble: Bonds,startups,China?</td></tr></table></body></html>

表4度数值最高和最低的4个主题  

<html><body><table><tr><td>主题</td><td>关键词(Top20)</td><td>入度</td><td>出度</td><td>度数</td></tr><tr><td>T42</td><td>state,investor,government, market,stock,growth,power, global, charge,unite,economic,trade, company,washington, suspect, bubble, bank,money, president, department</td><td>9</td><td>1</td><td>10</td></tr><tr><td>T64</td><td>government,attack,state,sea,island,oficial,hack,federal,information,south,unite,security, office,freedom,law,target,cybersecurity,military,personnel, international</td><td>6</td><td>3</td><td>9</td></tr><tr><td>T91</td><td>sea,official,obama,issue,island,cyber,visit,south,military,xi,state,dispute,espionage,beijing, step,attack, tension, security,unite, territorial</td><td>3</td><td>3</td><td>6</td></tr><tr><td>T123</td><td>state,statement,unite,military,pu,island,defense,complain,sea,job,freedom,south,economic, dispute,death,rule,criticize,fly, flight, post</td><td>0</td><td>6</td><td>6</td></tr><tr><td>T12</td><td>musical,price,market,sun,sell,child,san,bao,baby,family,father,boy,bin,son,broadway,xiaomi, industry, police,production, man</td><td>0</td><td>0</td><td>0</td></tr><tr><td>T95</td><td>panda,police,clip,bomb,glass,suspect,sprout,bridge,stock,sell,giant,trend,man, wednesday,kill, xinhua, money, thai,attack,Thursday</td><td>0</td><td>0</td><td>0</td></tr><tr><td>T51</td><td>space,mission, shenzhou,astronaut,yang,kung,fu,opportunity,crewed,star,fei,wang,station, launch,man,war, center,return, zhang, nie</td><td>0</td><td>0</td><td>0</td></tr><tr><td>T62</td><td>ship,yangtze,eastern,river,sink,star,cruise,state,capsize,rescue,water,passenger, june,authority, body, storm,board, tornado,monday,survivor</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

(注：加黑标注的关键词能够清楚地反映主题的含义，因此重点标出。)

对于图4的主题演化图，计算每个主题的介数中心度。表5按照从高到低的顺序列举了介数中心度不为0的主题及其人工总结的主题内容。主题的介数中心度值越大，则在主题演化和关联关系中越活跃，媒介能力越强。可以看出，最活跃的主题为南海军事主题，其次为经济主题。而7月的优衣库主题 $\left( \mathrm { T } _ { 7 2 } \right)$ 、9月的纪念抗日战争胜利70周年的阅兵主题 $( \mathrm { T } _ { 9 3 } )$ 、9月习主席出访美国华盛顿白宫主题 $\left( \mathrm { T } _ { 9 6 } \right)$ 、中国放开二孩政策主题 $\mathrm { ~ T ~ } _ { 3 2 } \mathrm { ~ , ~ } \mathrm { ~ T _ { 8 6 } ) ~ }$ 和污染问题 $\left( \mathrm { T } _ { 2 1 } \right)$ 都是2015年度受到广泛关注、引起媒体热议的主题。由此可见，通过介数中心度指标能够找到主题演化关系中的活跃主题。

表5介数中心度值不为0的主题  

<html><body><table><tr><td>主题</td><td>介数中心度</td><td>主题内容</td></tr><tr><td>T64</td><td>0.00461</td><td>袭击 南海 安全</td></tr><tr><td>T91</td><td>0.00307</td><td>南海 争议</td></tr><tr><td>T42</td><td>0.00282</td><td>投资 市场 增长</td></tr><tr><td>T55</td><td>0.00205</td><td>印度 交易 穆迪</td></tr><tr><td>T93</td><td>0.00179</td><td>北京 阅兵 战争 习主席 军事</td></tr><tr><td>T96</td><td>0.00166</td><td>习近平 美国 奥巴马 华盛顿 白宫</td></tr><tr><td>T72</td><td>0.00154</td><td>优衣库 性 视频</td></tr><tr><td>T61</td><td>0.00154</td><td>运动 伦敦 英国 足球 间谍 亚洲</td></tr><tr><td>T82</td><td>0.00090</td><td>美国 习主席 奥巴马 货币贬值</td></tr><tr><td>T102</td><td>0.00034</td><td>艺术 建筑师 比赛 网球 联赛</td></tr><tr><td>T21</td><td>0.00026</td><td>工业 污染</td></tr><tr><td>T105</td><td>0.00026</td><td>小米 手机 市场 科技 非洲</td></tr><tr><td>T113</td><td>0.00026</td><td>北京 温度 冷 北韩 烟雾 零度以下</td></tr><tr><td>T84</td><td>0.00026</td><td>弹道导弹 军事 检阅 军官 防御</td></tr><tr><td>T32</td><td>0.00021</td><td>孩子 政策人口数量</td></tr><tr><td>T86</td><td>0.00021</td><td>孩子 家庭 父母 政策</td></tr><tr><td>T85</td><td>0.00013</td><td>市场 股票 台湾 经济增长 金融风暴</td></tr><tr><td>T71</td><td>0.00013</td><td>市场 股票 经济危机</td></tr></table></body></html>

对于图4的主题演化图，计算其网络拓扑图的密度为0.02197266。密度值较小，网络的演变关系较为简单，与实际情况相符。

图5描绘了图4的主题演化图中最长的主题演化路径，长度为5，为 $( \mathrm { T } _ { 3 4 } / \mathrm { T } _ { 4 5 } / \mathrm { T } _ { 5 3 }$ $\mathrm { T } _ { 6 4 }$ $\mathrm { T _ { 8 1 } }$ 5 $\mathrm { T } _ { 9 1 }$ 5 $\mathrm { T } _ { 9 3 }$ $\mathrm { T } _ { 1 1 4 }$ ）这条路径描绘了2015年CNN媒体对我国军事和政治主题报道的演化过程，从3月、4月份的徐才厚、周永康事件，到5月、6月份的南海事件，到8月份中美讨论网络安全事件，再到9月份的纪念抗日战争胜利70周年阅兵事件，最后到12月份习主席和马英九在新加坡会面事件。

综合上述分析可得，实验结果与实际情况较为相符，可见基于流形学习的主题关系构建和演化分析方法能够在全局时间跨度建立主题的关联关系，挖掘主题关联关系间隐藏的规律并表征主题演化关系。该方法一方面克服高维主题特征向量之间的相似度计算带来的维数灾难问题，能够在低维平面输出主题的关联关系图，实现无监督的主题聚类和关联；另一方面避免了相邻时间窗口的主题关联失效而导致的全局主题演化链断裂，实验结果也表明新闻报道的演化并不遵循传统主题演化研究设定的相邻时间窗口跨度，而是具有不确定性和突发性；最后，基于社会网络相关指标能够较好地对新闻报道的主题演化结果进行分析和评价，找到主题演化过程中局部影响力较高的、较为活跃的主题。

![](images/8dc701210cae212141c5e0cdf5fcf829550eb6cecc441f7807a0eeca2deabf4c.jpg)  
图5最长距离的主题演化路径示意图

# 5结语

本文提出一种基于流形学习的新闻主题关系构建和演化研究方法，利用流形学习在全局时间窗口对新闻领域的主题演化进行探索，通过对高维主题向量进行非线性降维并在低维空间重新定义话题间的距离以实现话题的关联，并借鉴社会网络理论的度数、介数中心度、密度和直径指标分析主题的演化结果。

以2015年美国CNN网站对中国相关的新闻报道为例对该方法的有效性进行验证，得出以下结论：非线性降维处理能够在低维嵌入平面正确表示主题之间的关联，并且能够挖掘隐藏在高维向量间的规律、实现对高维主题向量的约简和可视化；通过社会网络的度数和介数中心度指标能够找到话题演化关系中局部影响力较大和较活跃的话题，通过密度和直径指标描绘整体的话题演化关系，并得到每一条主题演化路径。下一步工作是研究不同时间窗口长度对主题演化结果的影响以及基于可变时间窗口的主题演化分析。

# 参考文献：

[1]Samovar L A，Porter R E，McDaniel E R，et al. Communication Between Cultures [M].Wadsworth,2015.   
[2]楚克明,李芳．基于 LDA 模型的新闻主题的演化[J]．计算 机应用与软件,20l1,28(4):4-7,26.(Chu Keming,Li Fang. LDA Model-based News Topic Evolution [J].Computer Applications and Software,2011,28(4): 4-7,26.)   
[3]BleiD M, $\mathrm { N g }$ A Y, Jordan M I. Latent Dirichlet Allocation[J]. The Journal of Machine Learning Research，2003，3: 993-1022.   
[4]楚克明．基于LDA的新闻话题演化研究[D]．上海：上海交 通大学，2010.(Chu Keming．The Reaearch on Topic Evolution for News Based on LDA Model [D]. Shanghai: Shanghai Jiaotong University,2010.)   
[5]胡艳丽，白亮，张维明．一种话题演化建模与分析方法[J]. 自动化学报,2012,38(10): 1690-1697.(Hu Yanli,Bai Liang, Zhang Weiming.Modeling and Analyzing Topic Evolution [J].Acta Automatic Sinica,2012,38(10): l690-1697.)   
[6]Seung H S,Lee D D.Cognition-The Manifold Ways of Perception [J]. Science,2000,290(5500): 2268-2269.   
[7]Donoho D L. High-Dimensional Data Analysis: The Curses and Blessings of Dimensionality [C]. In: Proceedings of International Conference of Mathematicians,Paris,France. 2000: 6-11.   
[8]Wang X,McCallum A.Topics over Time:A Non-Markov Continuous-TimeModel of Topical Trends[C]. In: Proceedings of the 12th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. 2006: 424-433.   
[9]Blei D M,Laferty JD.Dynamic Topic Models [C]. In: Proceedings of the 23rd International Conference on Machine Learning.2006:113-120.   
[10] Hall D,Jurafsky D,Manning C D. Studying the History of Ideas Using Topic Models [C]. In: Proceedings of the Conference on Empirical Methods in Natural Language Processing. 2008: 363-371.   
[11]崔凯，周斌,贾焰，等．一种基于 LDA 的在线主题演化挖 掘模型[J]．计算机科学，2010,37(11):156-159，193.(Cui Kai,Zhou Bin,Jia Yan,et al.LDA-based Model for Online Topic Evolution Mining[J]. Computer Science,2010,37(11): 156-159,193.)   
[12]李保利，杨星．基于LDA 模型和话题过滤的研究主题演化 分析[J]．小型微型计算机系统，2012，33(12):2738-2743. (Li Baoli, Yang Xing.Analyzing Research Topic Evolution with LDA and Topic Filtering [J].Journal of Chinese Computer Systems,2012,33 (12): 2738-2743.)   
[13] 秦晓慧，乐小虬．基于LDA主题关联过滤的领域主题演化 研究[J]．现代图书情报技术,2015(3):18-25.(Qin Xiaohui, Le Xiaoqiu.Topic Evolution Research on a Certain Field Based on LDA Topic Association Filter [J]. New Technology of Library and Information Service,2015(3): 18-25.)   
[14]Griffiths T L，Steyvers M.Finding Scientific Topics [J]. Proceedings of the National Academy Sciences of the United States of America,2004,101(1): 5228-5235.   
[15] Cao J, Xia T,Li J.A Density-based Method for Adaptive LDA Model Selection [J]. Neurocomputing,2009,72(7-9): 1775-1781.   
[16] Law MH C,Jain A K. Incremental Nonlinear Dimensionality Reduction by Manifold Learning [J]. IEEE Transactions on Pattern Analysis and Machine Intelligence,2006,28(3): 377-391.   
[17] Tenenbaum J B，De Silva V,Langford JC.A Global Geometric Framework for Nonlinear Dimensionality Reduction [J].Science,2000,290(5500): 2319-2323.   
[18]Roweis S T,Saul L K.Nonlinear Dimensionality Reduction by Locally Linear Embedding [J]. Science,2000,290(5500): 2323-2326.   
[19] ManingC D,Schutze H,Raghavan P. 信息检索导论[M]．王 斌译．北京：人民邮电出版社，2011.(Manning C D, Schiitze H,Raghavan P.Introduction to Information Retrieval [M]. Translated by Wang Bin. Beijing: Post &Telecom Press, 2011.)   
[20] Costa L,Da F,Rodrigues F A,et al.Characterization of Complex Networks: A Survey of Measurements [J].Advances in Physics,2007,56(1): 167-242.   
[21]GooSeeker [EB/OL]. http://www.gooseeker.com.   
[22] Hartigan J A，Wong M A.Algorithm AS:A K-means Clustering Algorithm [J].Journal of the Royal Statistical Society: Series C (Applied Statistics),1979,28(1): 100-108.   
[23] Pajek: Analysis and Visualization of Large Networks [EB/OL]. http://mrvar.fdv.uni-lj.si/pajek/.

# 作者贡献声明：

徐月梅：提出研究思路，设计研究方案，撰写论文;  
李杨：设计研究方案，全文修改定稿;梁野：采集、清洗和分析数据;  
蔡连侨：提出部分修改意见。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:xuyuemei@bfsu.edu.cn。  
[1]徐月梅，李杨，梁野，蔡连侨.ISOMAP.mat.ISOMAP主题降维算法Matlab 程序.  
[2]徐月梅，李杨，梁野，蔡连侨.Cnn_China_2015.xlsx.2015年美国有线电视新闻网与中国相关的新闻.  
[3]徐月梅，李杨，梁野，蔡连侨.data.txt.预处理后的数据集.[4] 徐月梅,李杨，梁野，蔡连侨.LDA.mat.LDA主题抽取算法的Matlab 程序.  
[5]徐月梅，李杨，梁野，蔡连侨.LDAresult.xlsx.LDA抽取得到的主题和主题关键词.  
[6]徐月梅，李杨，梁野，蔡连侨.modelresult.xlsx．主题降维后各主题在低维平面的坐标和关联边.  
[7]徐月梅，李杨，梁野，蔡连侨．Similar.mat.低维平面关联边的权重计算算法.  
[8]徐月梅,李杨，梁野，蔡连侨.Pajekinput.net.Pajek 软件生成主题演化图的数据.

收稿日期:2016-05-13   
收修改稿日期:2016-08-23

# Analyzing Evolution of News Topics with Manifold Learning

Xu YuemeilLi Yang2,³Liang $\mathrm { Y e ^ { 1 } }$ Cai Lianqiao1   
1(Department of Computer Science, Beijing Foreign Studies University, Beijing 10o089, China)   
(Institute of Information Engineering, Chinese Academy of Sciences, Beijing 1Ooo93, China) 3(University of Chinese Academy of Sciences, Beijing 10o049, China)

Abstract:[Objective] This study aims to examine the creationand development of online news topics,and then to gauge the public opinion.[Methods]First, we introduced the manifold learning technology to analyze the news topics. Second,we explored the relations among the high dimensional topics from each time window,which were identified by the LDAmodel.Third, we clustered these topics and visualized the relations among them in the low-dimensional space. Finally,we analyzed the topic evolution with the helpof social network theorem.[Results]The proposed method could effctively identify the topic evolution trends of news reportson China from CNN in 2015.[Limitations]We did not fully explore the impacts of ime windows.[Conclusions]This study provides a new method to visualize the evolution of news report topics over a period of time,which avoids inaccurate description due to the changing of adjacent time windows.

Keywords: Latent Dirichlet AllocationManifold learning Topic relevanceTopic evolution