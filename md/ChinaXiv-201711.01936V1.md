# 基于改进 CFSFDP算法的文本聚类方法及其应用

詹春霞 王荣波 黄孝喜 谌志群(杭州电子科技大学计算机学院杭州 310018)

摘要：【目的】针对 CFSFDP(Clustering byFast Search and Findof Density Peaks)算法利用局部密度和距离的乘积选择聚类中心而导致聚类结果不理想的问题进行改进。【方法】提出一种基于粒子群算法的CFSFDP算法，通过粒子群算法寻找 CFSFDP 算法中的最佳局部密度和距离阈值，得到相对较高的局部密度和距离的聚类中心，减少离散点对数据中心选取的影响，并在某高考咨询平台提供的考生问题库中随机选取数据集进行试验。【结果】实验结果表明，在不同的数据集中，本文算法相对于基本的CFSFDP算法在准确率、召回率、F值上均有明显提高。【局限】文本处理时没有考虑语义关系。【结论】本文方法有很好的聚类效果，应用在高考咨询库中能够有效地减轻被咨询方的工作量并且帮助快速回答考生的问题。

关键词：CFSDFP 聚类中心粒子优化群算法分类号：TP391

# 1引言

随着信息时代的到来，互联网中的数据以爆炸式增长，如何从这些海量的数据中获取有用的信息并对数据进行有效的处理分析是当前研究的热点。数据挖掘[1]中的一个热门分支就是聚类[2]，它是一种无监督学习方法，无需任何先验知识，按照某种相似性度量方式，找到数据之间的共性，将数据集划分成若干个不同的类。划分到同一个类中的数据相似度高、差异小，而不同类之间的数据相似性较低。迄今为止，对聚类方法的研究已经长达几十年，它在医学、模式识别、图像处理、用户兴趣推荐等方面具有广泛的应用，推动了社会的发展，改善了人们的生活。

目前，聚类算法主要分为5大类[2-3]：基于层次的方法、基于划分的方法、基于密度的方法、基于模型的方法和基于网络的方法。每一类聚类方法都有一些经典算法[3]，在文本处理方面有着广泛的应用。但是鉴于数据的多样性和复杂性，没有任何一种聚类算法可以普遍适用于各种数据集，每一类方法都有各自的优点和缺陷，不同的聚类算法会得到不同的聚类结果。本文对比实验中，Agglomerative Clustering 算法和DBSCAN算法分别是基于层次和基于密度的方法，基本的 CFSFDP 算法是由Rodriguez 和Laio 提出的一种新的密度聚类算法[4]，该算法具有能够发现任意形状的数据集且快速简单的优点。张文开进行了基于密度的层次聚类算法研究[5]，Mehmood 等进行了基于CFSFDP算法的模糊聚类研究[，马春来等提出一种基于簇中心点自动选择策略的密度峰值聚类算法[7]。由于CFSFDP算法聚类中心的选取取决于数据点密度和距离乘积的大小，乘积越大越有可能是聚类中心，而数据集中密度大距离小或距离大密度小的数据点之间的乘积也可能很大而被误认为是聚类中心。因此本文通过引入粒子群算法找到一对密度距离阈值，数据集中密度和距离均大于这对阈值的数据点为数据中心，减少了离散点对聚类中心选取的影响，实现了聚类中心的自动选择，减少了人工干预的过程。

本文的实验数据来自于某高考咨询平台自动问答APP，其中的数据都是学生对于所报考大学的录取情况、学校基本信息等方面的问题，对其中文本的聚类有利于完善机器人知识库，提高对学生问答的准确率。将该算法应用于从中抽取的数据集中，证明了本文聚类算法的有效性。

# 2相关工作

# 2.1 CFSFDP算法

CFSFDP[4聚类算法的基本思想是：首先计算数据点的密度及距离，其次选取聚类中心，最后对非聚类中心点进行归类操作。其中，对聚类中心的选取是该算法的关键。聚类中心点具有两个重要的特征：聚类中心本身密度比较大，它是由一些密度比它小的数据点包围；与其他比其密度高的数据点之间的距离都比较大。基本的CFSFDP算法选取聚类中心的方法具有很大的缺点：数据集中密度大距离小或密度小距离大的数据点乘积也可能很大而被误认为是聚类中心;聚类中心的个数无法自动确定，需要一个人工干预的过程。

# (1）局部密度和距离

设有数据集 ${ \boldsymbol { s } } = \{ x _ { i } \} _ { i = 1 } ^ { N }$ ， $I _ { s } = \{ 1 , 2 , \cdots , N \}$ ， $d _ { i , j }$ 表示数据点 $x _ { i }$ 和数据点 $x _ { j }$ 之间的距离。对于数据集 $s$ 中的每一个数据点 $x _ { i } ,$ 可以用两个变量进行刻画：局部密度和距离。计算局部密度 $\rho _ { i }$ ，如公式(1)所示[4]

$$
\rho _ { i } = \sum _ { j \in I _ { s } \{ i \} } \varphi ( d _ { i , j } - d _ { c } )
$$

其中， $\varphi ( x ) = { \left\{ \begin{array} { l l } { 1 , x < 0 } \\ { 0 , x \geq 0 } \end{array} \right. }$ 参数 $d _ { c } { > } 0$ 为截断距离。，由公式(1)可知，每个数据点的密度是在数据集 $s$ 中与该数据点的距离小于 $d _ { c }$ 的数据点个数(不包括本身)。

当数据点 $x _ { i }$ 具有最大的局部密度时，其距离为 $s$ 与 $x _ { i }$ 距离最大的数据点与 $x _ { i }$ 之间的距离。除此之外，对于其他不具有最大密度的数据点，距离表示在所有局部密度大于 $x _ { i }$ 的数据点当中，与 $x _ { i }$ 的距离最小的数据点与 $x _ { i }$ 之间的距离。其计算如公式(2)所示[4]

$$
\delta _ { q i } = \left\{ \begin{array} { l l } { \underset { j < i } { \operatorname* { m i n } } \{ d _ { q i , q j } \} } & { i \geqslant 2 } \\ { \underset { j \geqslant 2 } { \operatorname* { m a x } } \{ d _ { q 1 , q j } \} } & { i = 1 } \end{array} \right.
$$

其中， $\rho _ { q 1 } \geqslant \rho _ { q 2 } \geqslant \ldots \geqslant \rho _ { q N } .$

(2)决策图

以局部密度 $\rho$ 为横轴，距离 $\delta$ 为纵轴，对数据点的局部密度和距离刻画出相应的决策图。图1是由28个数据点包含的散点图，相应的决策图如图 $2 ^ { [ 4 ] }$ 所示。

![](images/2cc71c4a97b2689e8584ba71c9f7393e283951ba00b27e14cf03454322744c47.jpg)  
图1散点图[4]

![](images/7862bcac2bb8a72cb84f4584a82dcb24010de8ed1ff0084627f3c6e78862d109.jpg)  
图2决策图[4]

# 2.2 粒子群算法

粒子群算法[8-9]中，种群中的粒子都有决定自身方向和位置的速度和由适应度函数决定的适应度值，每个粒子通过向自身和群体曾达到的最优位置靠拢来动态调节自身位置，通过迭代得到最优解。

假设粒子群的种群规模为N，种群中个体维度为D，每一个粒子都有两个属性：当前的位置 $x _ { i }$ 和飞行的速度Vi，,可表示为xi=(xi,1,xi,2,,xi,D），Vi=$( \nu _ { i , 1 } , \nu _ { i , 2 } , \cdots , \nu _ { i , D } )$ ，其中 $\mathsf { i } { = } 1 , 2 , { \cdots } \mathsf { N } _ { \circ } \ P _ { i }$ 为粒子 $x _ { i }$ 在搜索解的过程中适应度值最高的位置； $P _ { g }$ 为整个粒子群中粒子所达到的最优位置，即 $P _ { g }$ 是所有 $P _ { i }$ 当中的适应度最大的值。在每一次迭代的过程中，每个粒子通过这两个极值来调整自身的位置和飞行速度。位置和速度的更新如公式(3)和公式(4)所示[9]。

$$
x _ { i } = x _ { i } + \nu _ { i }
$$

$$
\nu _ { i } = w \times \nu _ { i } + c _ { 1 } \times r _ { 1 } \times ( P _ { i } - x _ { i } ) + c _ { 2 } \times r _ { 2 } ( P _ { g } - x _ { i } )
$$

其中, $c _ { 1 } \setminus c _ { 2 }$ 为正数，称之为加速因子; $r _ { 1 } , r _ { 2 }$ 为[0,1]中均匀分布的随机数; $w$ 是惯性权重因子。 $\nu _ { m a x }$ 是粒子的最大速率, $\nu _ { i } \in [ - \nu _ { \operatorname* { m a x } } , \nu _ { \operatorname* { m a x } } ]$ ，当粒子的飞行速度超过 $\nu _ { m a x }$ 时，粒子的飞行速度即为 $\nu _ { m a x }$ 。

# 3基于改进CFSFDP算法进行文本聚类

由于基本的CFSFDP 算法存在上述缺陷，本文引入了粒子群算法。改进CFSFDP 算法的主要思想为:利用粒子群算法调节CFSFDP算法中聚类中心的选取。即通过粒子群算法得到一个密度和距离的阈值，在CFSFDP算法中密度值和距离均大于这个阈值的数据点为聚类中心，根据选取出来的聚类中心进行聚类，根据聚类结果计算适应度值，将其作为粒子群算法更新的判断依据。将其运用到文本聚类中，通过计算文本之间的相似性，计算出每条文本的密度和局部距离，实现文本聚类。算法的流程如图3所示。

![](images/f98375596df14f75f0a6f0d68a4165cc3e85b3270b7ff71aea236edd10d95694.jpg)  
图3算法流程

对于全部的文本数据集，采用目前最广泛的文本处理方法，基于 TF-IDF(Term Frequency-InverseDocument Frequency)[10-12]的向量空间模型 VSM(VectorSpace Model)[12来表示文本，向量的每一维为对应的特征词在该文本中的权重。文本相似度的度量方式是依据余弦距离[13-14]，值越大，两条文本之间越相似，距离越近。

粒子群算法在迭代过程中以适应度函数为依据适应度值越高说明该粒子的适应能力越好，则会对下一代粒子的进化产生影响，从而产生最优解。本文采用Rand系数[15]的倒数作为粒子群算法的适应度函数,以此来评价聚类结果的好坏。

算法的具体过程如下：

$\textcircled{1}$ 对文本集S进行预处理，计算每条文本特征词的权重，得到每条文本的向量化表示并且计算文本之间的相似度。

$\textcircled{2}$ 将 $\textcircled{1}$ 中得到的每个向量作为一个数据点，根据公式(1)和公式(2)计算每个数据点的局部密度和距离。

$\textcircled{3}$ 初始化粒子群算法的参数，主要包括种群规模 $m$ 、惯性权重 $w$ 、学习因子 $\scriptstyle { c _ { 1 } }$ 和 $c _ { 2 }$ 、最大迭代次数 $t$ 等。随机生成种群的初始速度和初始位置，将粒子的初始位置赋值给粒子的初始最优位置 $P _ { i }$ ，根据各个粒子的最优位置找到全局最优位置 $P _ { g } ,$ 位置由密度和距离确定。

$\textcircled{4}$ 计算每个粒子对应的聚类结果。将每个粒子的位置传递给CFSFDP算法，数据集中局部密度和距离均大于此粒子位置的数据点记为聚类中心，并使用数据点归属方法对非聚类中心点进行归属，完成聚类操作。

$\textcircled{5}$ 对于每个粒子对应的聚类结果计算适应度值，更新当前每个粒子的最优位置。并且根据每个粒子的最优位置更新种群全局最优位置，更新每个粒子的位置和速度。

$\textcircled{6}$ 判断是否满足收敛条件或是否达到最大迭代次数，若是，返回 $\textcircled{7}$ ；否则，迭代次数加1后执行 $\textcircled{4}$ ○

$\textcircled{7}$ 根据种群的全局最优位置选取聚类中心，通过数据点的归属方法完成聚类，得到最终文本集的聚类结果，算法结束。

# 4实验结果及分析

# 4.1 数据集

实验中的数据来自于从高考咨询平台APP中考生向学校招生办提出的问题，从问题库中随机选取7个类别：询问学校代码和专业代码类、军训有关事项、高考加分情况、分数极差情况、询问招生办电话、省控线有关信息、是否有退档情况。从每一类中随机选取构造包含7类数据的数据集，共构造出data1050、data3100、data5000三个数据集，分别包含1050、

3100、5000条数据，其中每个数据集中包含的各个类数如表1所示。利用"结巴分词”、停用词处理等对数据集进行预处理，并且对不同的数据集进行实验分析比较。本文通过纯度(Accuracy)、精度(Precision)、召回率(Recall)和F度量值(F-Measure)[16-17]4个评价指标衡量聚类效果。

表1文本数据集  

<html><body><table><tr><td>类 数据集</td><td>代码</td><td>军训</td><td>加分</td><td>极差</td><td>电话</td><td>省控线</td><td>退档</td></tr><tr><td>data1050</td><td>200</td><td>100</td><td>200</td><td>100</td><td>150</td><td>200</td><td>100</td></tr><tr><td>data3100</td><td>600</td><td>300</td><td>600</td><td>300</td><td>500</td><td>500</td><td>300</td></tr><tr><td>data5000</td><td>1000</td><td>400</td><td>1000</td><td>400</td><td>900</td><td>900</td><td>400</td></tr></table></body></html>

# 4.2 实验结果分析

分别用层次聚类算法（AgglomerativeCluster)[18-19]、DBSCAN 算法[20]、基本的 CFSFDP算法、以及本文算法对抽取的三个数据集进行聚类比较。其中AgglomerativeClustering 算法因其可以适用于任意形状和任意属性的数据集在文本聚类方面也有广泛的应用。AgglomerativeClustering 算法采用在三个数据集中设定的类别数目实验效果最佳的7。粒子群算法中种群数量设定为50，最大迭代次数为30,加速因子为2，惯性权重因子为0.5。DBSCAN 算法是基于密度的聚类算法中的一种经典算法，具有较强的代表性。针对 DBSCAN 算法进行多次实验，在数据集data1050中选取参数eps $\scriptstyle \operatorname { \tt : = } 0 . 8$ 、 $\mathrm { m i n P t s } { = } 3 0$ ，数据集data3100 中参数 eps $\scriptstyle \operatorname { \tt \ s u p }$ 、minPts $\scriptstyle \left. = 7 0 \right.$ ，数据集data5000中选取参数 $\mathrm { \tt e p s { = } } 0 . 8$ 、minPts $\scriptstyle \left. = 1 1 0 \right.$ 效果相对最佳的实验结果。层次聚类算法、DBSCAN算法、基本的CFSFDP算法、本文算法总体F值比较如图4所示。

![](images/ce5697cc0a6863c4c959f061bd45d9c1f515b23c8d64674af5ab7d06a76d4f91.jpg)  
图4聚类效果的比较

可见本文算法相对于其他三个算法在不同的数据集中聚类效果都较好。实验结果如表2所示，可以看出本文算法在高考问询文本库中相比其他三个算法都有较好的效果。其中基本的CFSFDP算法由于噪声点的影响造成同一个类中两个及以上的数据点成为数据中心导致聚类算法的不准确性。DBSCAN算法由于对参数 eps(被认为是同一个类的文本之间的最大距离)和minPts(一条文本与其他文本的距离小于eps的个数大于等于minPts视为聚类中心)特别敏感，在类中的数据发布密度不均匀的时候，eps 较小时，密度小的类会被划分成多个相似的类，eps 较大时，会使得距离较近且密度较大的类被合并成一个较大的类，导致聚类效果不理想。层次算法比DBSCAN算法具有更好的效果，但是Agglomerative Clustering 算法的计算复杂度太高。

表24 种算法的 Accuracy、Precision、Recall、F-Measure 值比较  

<html><body><table><tr><td>算法</td><td>数据集</td><td>Accuracy</td><td>Precision</td><td>Recall</td><td>F-Measure</td></tr><tr><td rowspan="3"></td><td>data1050</td><td>0.7305</td><td>0.7743</td><td>0.7969</td><td>0.7854</td></tr><tr><td>Agglomerative data3100</td><td>0.7077</td><td>0.6976</td><td>0.7811</td><td>0.7370</td></tr><tr><td>data5000</td><td>0.6808</td><td>0.6598</td><td>0.6627</td><td>0.6612</td></tr><tr><td rowspan="3">DBSCAN</td><td>data1050</td><td>0.6486</td><td>0.6795</td><td>0.7332</td><td>0.7052</td></tr><tr><td>data3100</td><td>0.6797</td><td>0.6761</td><td>0.7880</td><td>0.7278</td></tr><tr><td>data5000</td><td>0.6006</td><td>0.6270</td><td>0.6500</td><td>0.6643</td></tr><tr><td rowspan="3">CFSFDP</td><td>data1050</td><td>0.8171</td><td>0.8050</td><td>0.8090</td><td>0.8070</td></tr><tr><td>data3100</td><td>0.750</td><td>0.7375</td><td>0.6617</td><td>0.6975</td></tr><tr><td>data5000</td><td>0.7425</td><td>0.7438</td><td>0.6189</td><td>0.6756</td></tr><tr><td rowspan="3">本文算法</td><td>data1050</td><td>0.8333</td><td>0.7171</td><td>0.9098</td><td>0.8609</td></tr><tr><td>data3100</td><td>0.7574</td><td>0.7421</td><td>0.7676</td><td>0.7546</td></tr><tr><td>data5000</td><td>0.7712</td><td>0.7340</td><td>0.7450</td><td>0.7395</td></tr></table></body></html>

# 5结语

本文针对CFSFDP算法聚类中心选取的武断性的问题，提出一种基于粒子群算法的CFSFDP 算法。引入粒子群算法找到一对阈值，将大于这对阈值的数据点作为聚类中心，减少离散点对聚类结果的影响，提高了聚类准确性。将此算法应用在从某高考咨询平台问题库中随机提取的问题中，验证了本文算法的有效性和准确性，能够帮助考生更准确高效地获得答案并且减轻了被咨询方的咨询量，大大节省了双方的时间。但是该算法也存在局限性，由于粒子群本身算法的特性，在计算高纬度的问题时，粒子群优化算法需要的粒子数较多，导致计算复杂度通常很高。

# 参考文献：

[1]Tan P N, Steinbach M, Kuma V. Introduce to Data Mining [M].Addison-Wesley Professional,1988.   
[2]孙吉贵，刘杰，赵连宇．聚类算法研究[J]．软件学报，2008, 19(1):48-61.(Sun Jigui,Liu Jie,Zhao Lianyu.Clustering Algorithms Research[J].Journal of Software,20o8,19(1): 48-61.)   
[3]史梦洁．文本聚类算法综述[J]．现代计算机，2014(2):3-6. (Shi Mengjie. Summary of Text Clustering Algorithms[J]. Modern Computer, 2014(2): 3-6.)   
[4]Rodriguez A,Laio A. Clustering by Fast Search and Find of Density Peaks[J]. Science,2014,344(6191):1492-1496.   
[5]张文开．基于密度的层次聚类算法研究[D].合肥：中国科 学技术大学，2015.(Zhang Wenkai．Research on DensitybasedHierarchicalClusteringAlgorithm[D].Hefei: University of Science and Technology of China,2015.)   
[6]Mehmood R,Bie R,Dawood H,et al. Fuzzy Clustering by Fast Search and Find of Density Peaks[C]//Proceedings of the 2015 International Conference on Identification,Information, and Knowledge in the Internet of Things.2015.   
[7]马春来,单洪,马涛．一种基于簇中心点自动选择策略的密 度峰值聚类算法[J]．计算机科学,2016,43(7):255-258.(Ma Chunlai, Shan Hong,Ma Tao.Improved Density Peaks Based Clustering Algorithm with Strategy Choosing Cluster Center Automatically[J]. Computer Science,2016,43(7):255-258.)   
[8]Kennedy J，Eberhart R.Partical Swarm Optimization[C]// Proceeding of the 1995 IEEE International Conference on Neural Networks.1995.   
[9]刘建华．粒子群算法的基本理论及其改进研究[D]．长沙: 中南大学,2009.(Liu Jianhua.The Basic Theory of Partical Swarm Optimization and Its Improvement[D]. Changsha: Central South University,2009.)   
[10]黄承慧，印鉴，侯昉．一种结合词项语义信息和 TF-IDF 方 法的文本相似度量方法[J]．计算机学报，2011，34(5): 856-864.(Huang Chenghui,Yin Jian,Hou Fang.A Text SimilarityMeasurementCombiningWordSemantic Information with TF-IDF Method [J].Chinese Journal of Computer,2011,34(5): 856-864.)   
[11]Aizawa A.An Information-treoretic Perspective of TF-IDF Measures[J]. Information Processing and Management, 2003, 39(1): 45-65.   
[12]Salton G, Buckley C. Term Weight Approaches in Automatic Text Retrieval [J]. Information Processing and Management, 1988,24(5):513-523.   
[13]谭静．基于向量空间模型的文本相似度算法研究[D]．成 都：西南石油大学，2015.（Tan Jing.Research on Text Similarity Algorithm Based on Vector Space Modal[D]. Chengdu: Southwest Petroleum University,2015.)   
[14]赵俊杰，胡学钢．基于文本分类的文档相似度计算[J].微型 电脑应用,2008,24(12):46-47.(Zhao Junjie,Hu Xuegang. Simility Calculation Based on Text Classification [J]. Microcomputer Application,2008,24(12): 46-47.)   
[15] Halkidi M，Batistakis Y,Vazirgiannis M. On Clustering Validation Techniques[J]. Journal of Intelligent Information Systems,2015,17(2-3): 107-145.   
[16]Liang J,Bai L,Dang C,et al. The K-Means-Type Algorithms Versus Imbalanced Data Distributions[J]. IEEE Transactions on Fuzzy Systems,2012,20(4): 728-745.   
[17]张鸣．符号数据聚类评价指标研究[D]．太原：山西大学, 2013.(Zhang Ming. Study on the Evaluation Index Symbol of Data Clustering[D]. Taiyuan: University of Shanxi,2013.)   
[18]Franti P, Virmajoki O,Hautamaki V. Fast Agglomerative Clustering Using a K-nearest Neighbor Graph [J].IEEE Transactions on Pattern Analysis & Machine Intelligence, 2006,28(11): 1875-1881.   
[19]段明秀．层次聚类算法的研究及应用[D].长沙:中南大学, 2009.(DuanMingxiu.ResearchandApplicationof Hierarchical Clustering Algorithm[J]. Changsha: Central South University,2009.)   
[20]冯少荣，肖文俊.DBSCAN 聚类算法的研究与改进[J].中国 矿业大学学报,2008,37(1):106-111.(Feng Shaorong,Xiao Wenjun.An Improved DBSCAN Clustering Algorithm[J]. Journal of China University of Mining & Technology, 2008, 37(1): 106-111.)

# 作者贡献声明：

詹春霞：提出研究思路，采集分析数据;  
詹春霞，王荣波：进行实验，起草并修改论文;  
王荣波，黄孝喜，谌志群：修改论文。

# 利益冲突声明：

本文实验中所用的数据由达言公司提供，实验数据仅限于科学研究，不可在网络传播或用于其他用途。

# 支撑数据：

支撑数据由作者自存储,http://pan.baidu.com/s/1bpLoWcJ。

# Application of Text Clustering Method Based on Improved CFSFDP Algorithm

Zhan ChunxiaWang RongboHuang Xiaoxi Chen Zhiqun (School of Computer Science and Technology, Hangzhou Dianzi University, Hangzhou 3100l8, China)

Abstract:[Objective] This paper aims to improve the un-satisfactory performance of CFSFDP(clustering by fast search and findof density peaks)algorithmwith the helpofbased on particle swarm optimization.[Methods]First, we determined the cluster centers by searching optimal local density and distance thresholds to increase the accuracyof results.These clustering centers have relatively high local densityand distance,which reduced the influence of discrete points.Then,we examined the proposed method on arandomly selected dataset from the question-answer database of a college entrance exam consulting platform.[Results]The modified CFSFDP algorithm had better performance than the original one.[Limitations]We did not include the semantic relations to process the texts.[Conclusions]The proposed algorithm could achieve good clustering results,and improve the eficiency of the consulting personnel .

Keywords: CFSDFPCluster CentersParticle Swarm Optimization Algorithm