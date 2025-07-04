# 基于代价敏感集成极限学习机的文本分类方法\*

李明’2 肖培伦2,3 张矩' 顾心盟41（中国科学院重庆绿色智能技术研究院 高性能计算应用研究中心重庆 400714)² （清华大学信息技术研究院 语音与语言研究中心北京 100084)（爱丁堡大学科学与工程科学学院英国 EH1)4（北京邮电大学北京 100876)

摘要：加权极限学习机对不同类别的样本赋予不同的权值，在一定程度上提高了分类准确率,但加权极限学习机只考虑了不同类别样本之间差异，忽视了样本噪声和同类样本之间的差异。本文提出了一种基于文本类别信息熵的极限学习机集成方法，该方法以Adaboost.M1为算法框架，通过文本的类内分布熵和类间分布熵生成文本类别信息熵，由文本类别信息熵构造代价敏感矩阵，把代价敏感极限学习机集成到Adaboost.M1框架中。实验结果表明，该方法与其他类型的极限学习机相比较有更好的准确性和泛化性。

关键词：极限学习机 集成学习 Adaboost.M1 文本分类代价敏感分类号：TP393

# Ensemble Extreme Learning Machine based on Cost Sensitive for Text Classification

Li Ming1,² Xiao Peilun2³Zhang Ju'Gu Xinmeng4   
1(High performance computing application R&D Center， Chongqing Institute of Green   
and Intelligent Technology， Chinese Academy of Sciences， Chongqing,400714, China ）   
² (Center for Speech and Language Technology,Research Institute of Information Technology，Tsinghua University,Bei jing，100084， China)   
3 (The University of Edinburgh,College of Science & Engineering， Edinburgh EH1, England) (Bei jing University of Posts and Telecommunications, Beijing,100876, China)

Abstract:The weight extreme learning machine improves the classification accuracy, which gives different weight to different samples, but the weight extreme learning machine only takes into account the differences between samples in the different categories and neglects the difference between samples in the same category and noise.In this paper，we propose a novel method about ensemble extreme learning machine based on text information entropy，which takes Adaboost.M1 as the algorithm framework, generates text information entropy through the intra-class entropy and the inter-class distribution entropy of the text， constructs a cost sensitive matrix by using the text information entropy， integrates the cost sensitive ensemble extreme learning machine into the Adaboost.M1 framework.The experimental results show that the proposed method has better accuracy and generalization than other extreme learning machines.

Keywords: extreme learning machine ensemble learningAdaboost.M1 text classification Cost-sensitive

# 1引言

文本分类是指在给定分类体系下，使用计算机自动地标记文本类别的过程。文本分类作为文本挖掘的关键技术之一，广泛应用于信息检索、搜索引擎、问答系统、舆情分析、情感分析等领域。随着网络技术的高速发展，网页的数量成几何速度增长，高效而个性化的信息检索需要发展更精确更有效的文本分类技术。目前比较成熟的文本分类方法有：k近邻（k-nearest neighbor，K-NN）[1-2]、朴素贝叶斯(Naive Bayes）[3]、决策树(Decision tree）[4]、最大熵(maximum entropy）(56]、支持向量机（support vectormachine,SVM)[2）、神经网络（neural networks）[8-9]、模糊理论[10]等。

Huang 等人提出了一种新型的单隐层前馈神经网络--极限学习机（ELM）[1],该算法输入层与隐含层之间的连接权值和阈值均随机产生，而且在模型训练过程中无需对参数进行调整，只需对隐含层神经元个数进行设置，避免了基于梯度下降学习方法的许多问题,如陷入局部极小、收敛速度慢等问题[12]，和传统的神经网络相比，ELM 具有相同的全局逼近能力 准确率高并且模型简单。与其他传统机器学习方法相比极限学习机也具有明显的优势，极限学习机具有更快的学习速度和更好的泛化性能。YingLiu等人对ELM和 SVM在文本分类上的性能进行了对比[13]；Wenbin Zheng 等人使用潜在语义分析对文本进行降维，将正则化极限学习机（RELM）、神经网络和SVM对文本进行分类比较，RELM表现出更快的学习速度和更好的分类性能[14]；此后Wenbin Zheng 等人又提出了基于非负矩阵分解的线性分类器和基于 ELM分类器想结合的文本快速分类框架[15]；Xiang guoZhao 等人提出了一个基于极限学习机的 XML文档分类框架，在该框架中对voting-ELM进行了改进，成功地将REV和RCC方法应用于v-ELM，取得了比voting-ELM 更好的效果[16]；此后，Xiang guo Zhao 继续对该方法进行改进，在RCC方法中引入ε参数提升重投的精确率，对ELM的投票结果进行概率统计，从而进一步提升了分类效果[17；Li juan Duan 采用 KELM 对历史专利文献进行分类，相对 SVM 取得了更好的效果[18]；于海燕等人通过信息增益对文本特征进行降维，引入小波核应用 KELM对中文文本进行情感分类[19]；李永强通过优化搜索策略，提出了CPSO-ELM算法来选择单隐层前馈神经网络中隐藏节点的输入权重和偏置，对 XML文档进行分类[2°；Rajendra Kumar Roul 等人研究了特征提取技术对ELM 分类性能的提升，对单一ELM和多层 ELM在文本分类领域做了大量的实验，结果超过了许多 state-of-the-art 的方法，包括 SVM方法[21；此后，RajendraKumar Roul提出了一种基于K均值聚类的文本分类特征选择算法，结合Wordnet降低文本的维度，应用于单一ELLM 和多层 ELM[2]。

然而，ELM算法也存在着一定的不足，其预测性能仍受连接权值、阈值及隐含层节点数的影响[23]，由于其输入连接权值和隐含层阈值为随机初始化，在对相同训练样本及检验样本下多次执行此算法时的结果可能会有一定出入，即模型稳定性不理想。集成学习相比单个模型可以有效的提高预测性能[24]。Adaboost 是一种重要的集成学习技术，能够将预测精度仅比随机猜度略高的弱学习器增强为预测精度高的强学习器。YunliangJiang 等人通过PCA对人脸特征进行降维，将 ELM嵌入Adaboost 框架中应用于人脸识别[25]。黄海波等人提出基于 Adaboost的 ELM算法，通过小波包分解对减振器异响特征信息进行提取，对减振器异响声品质进行预[26]。Yan Xu等人将基于Adaboost 的 ELM方法应用于交通标志的识别[27]。Kuan Li等人提出了一种boosting 的加权 ELM方法，将加权ELM无缝嵌入到 boosting 的 ELM中，在 Adaboost每次迭代中调整样本的分布权重。但该方法只考虑了数据集的类间不平衡，而没有考虑类内的不平衡，实际上，类内的不平衡对分类性能的影响也很大[28]。

本文在Adaboost.M1的框架下结合代价敏感 ELM提出了一种新的ELM模型并将其应用到文本分类中。首先使用词向量得到高质量低维度的文本特征向量，然后用文本类别信息熵构建代价敏感矩阵，把代价敏感加权ELM作为基分类器，在多分类Adaboost.M1框架中通过代价敏感因子调整样本分布。最后，在三个文本标准数据集 20newsgroups、Reuters52 和 Webkb 上对比了 ELM、Voting-ELM、Adboost-WELM以及本文提出的Adaboost-WELM框架下AE1-WELM、AE2W-ELM和AE3W-ELM三种方法的精度和泛化性能。通过实验验证，AE3-WELM算法相比其他的ELM方法有着更为显著的分类性能、稳定性和泛化性。

# 2基于Adaboost 的加权极限学习机

# 2.1 加权极限学习机

加权极限学习机(weight extreme learningmachine)是在 ELM 的基础上引入加权矩阵W，对每一个样本进行加权，减少样本类间可能存在的不平衡性，从而提高样本总体的识别率。根据 KKT 理论有：

$$
\beta = H ^ { \cdot } T = \left\{ \begin{array} { l } { { \displaystyle \left( \frac { I } { C } + H ^ { T } W H \right) ^ { - 1 } H ^ { T } T , ~ N \ge L } } \\ { { \displaystyle H ^ { T } \left( \frac { I } { C } + W H H ^ { T } \right) ^ { - 1 } T , ~ N < L } } \end{array} \right.
$$

其中W为对角矩阵，对角线上的每一个元素为样本的权重值。W．Zong 等人经验地给出了两种加权方案[28]：

$$
W _ { 1 } = \frac { 1 } { \# t _ { i } }
$$

$$
\begin{array} { r l }  \overrightarrow { t } \overrightarrow { \overrightarrow { x } } \overrightarrow { \Bigg { t } } \Bigg { \Bigg . \Bigg . \Bigg . \Bigg \begin{array} { l } { \displaystyle \boldsymbol { W } _ { 2 } = \int ^ { \frac { 0 . 6 1 8 } { \mathcal { H } _ { t _ { i } } } , \mathrm { \nabla } \mathcal { H } _ { t _ { i } } > A V G \big ( \mathcal { H } t _ { i } \big ) } \\ { \displaystyle \frac { 1 } { \mathcal { H } _ { t _ { i } } } , \mathrm { \nabla } \mathcal { H } _ { i } \leq A V G \big ( \mathcal { H } t _ { i } \big ) } \end{array} } } \end{array}
$$

但加权极限学习机只是简单的用大类的样本数和小类的样本数来赋予样本权值，对少数类样本赋予更大的权重，但是同类样本的分配权重是相等的，这样只是考虑了数据集的类间不平衡，而没有考虑类内的不平衡，实际上，类内的不

平衡对分类性能的影响也很大。KuanLi等人在此基础上进行了改进，对于不同类样本权值采用不同更新方式，但是同样没有考虑同类样本之间的权值差异[28]。

# 2.2基于Adaboost 的加权极限学习机

AdaBoost算法基本思想是将若干个弱分类器按照某种规则组合起来，集成为一个分类能力很强的强分类器。Freund 和 Schapire 改进了原本用于二分类问题的Adaboost，生成Adaboost.M1、AdaboostM2算法用于多分类问题，同时给出了Adaboost.M1的扩展形式，本文使用Adaboost.M1算法的扩展形式[29]，然后将1.1中的加权极限学习机嵌入到Adaboost.M1框架中，生成基于Adaboost 的加权极限学习机算法，算法中采用 $h _ { _ m } \left( x \right)$ 表示第 $m$ 个弱分类器，通过弱分类器权重 $\alpha _ { { \scriptscriptstyle m } }$ 对弱分类器进行组合得到强分类器，算法的主要步骤如下：

步骤1用式（2）初始化样本权值， $D _ { \mathrm { 1 } } \left( x _ { i } \right) = 1 / \# t _ { k }$ ， $i = 1 , 2 , \dots , N$ ;

# $t _ { k }$ 表示样本所在类 $t _ { k }$ 所含样本个数；

步骤2 对样本权值归一化 $D _ { 1 } \left( x _ { i } \right) = D _ { 1 } \left( x _ { i } \right) \Big / { \sum _ { i = 1 } ^ { n } D _ { 1 } \left( x _ { i } \right) }$

步骤3

For $m = 1 : M$ （ （ $M$ 为弱分类器数量）

(1）用弱学习算法训练样本得到弱分类器 $h _ { _ m } \left( x \right)$

(2)计算 $h _ { _ m } \left( x \right)$ 分类错误率

$$
\varepsilon _ { \scriptscriptstyle m } = \sum _ { i = 1 } ^ { \scriptscriptstyle N } D _ { \scriptscriptstyle m } \left( x _ { i } \right) I \left( h _ { \scriptscriptstyle m } \left( x _ { i } \right) \ne y _ { i } \right)
$$

(3）当分类器分类错误率大于0而且小于0.5时，按照式（5）更新样本权值，否则退出循环;

$$
D _ { m + 1 } \left( x _ { i } \right) = \frac { D _ { m } \left( x _ { i } \right) \exp \left( - \alpha _ { m } I \left( h _ { m } \left( x _ { i } \right) \neq y _ { i } \right) \right) } { Z _ { m } }
$$

$Z _ { { _ m } }$ 为归一化因子， $\boldsymbol { Z } _ { \textit { m } } = \sum _ { i = 1 } ^ { N } D _ { \textit { m } + 1 } \left( \boldsymbol { x } _ { i } \right)$

$$
\alpha _ { { \scriptscriptstyle m } } = \log \frac { 1 - \varepsilon _ { { \scriptscriptstyle m } } } { \varepsilon _ { { \scriptscriptstyle m } } } + \log \left( k - 1 \right)
$$

步骤4组合分类器输出为：

$$
\Theta \left( x \right) = \arg \operatorname* { m a x } _ { k } \sum _ { m = 1 } ^ { M } \alpha _ { m } I \left( h _ { m } \left( x \right) = k \right)
$$

# 3基于代价敏感集成极限学习机的文本分类方法

# 3.1基于词向量的文档向量生成

数量巨大的训练样本和过高的向量维度是文本分类的特点。过高维度的特征集会增加极限学习机的计算负担。传统的做法是降低文本向量空间的维数并减少噪音信息对文本分类的干扰，保证文本分类的精度。词向量文本表示比传统的人工提取特征向量的方法具有更好的特征表达效果，词向量通过训练无标注语料将每个词映射成低维实数向量[30],通过低维实数向量之间的距离来描述词语之间的语义相似度，同时又能有效避免特征向量的维度灾难。Mikolov等人提出了两种词向量学习模型： CBOW（Continuous Bag of Words）和 Skip-gram 模型[31]。Skip-gram模型以当前词作为对数线性分类器的输入，预测上下文中的词语。

给定词序列 $w = \left\{ \begin{array} { l } { { w _ { 1 } , w _ { \mathit { \mathrm { ~ 2 ~ } } } , \cdots w _ { \mathit { \mathrm { ~ N ~ } } } } } \end{array} \right\}$ ， $N$ 为序列长度，在skip-gram 的 $N N$ 网络结构中，输入词序列中的第 $i$ 个词 $\boldsymbol { w } _ { i }$ ，使用当前词 $\boldsymbol { w } _ { i }$ 预测窗口大小为 $b$ 的上下文，Skip-gram 模型最大化的目标函数如式（8）所示：

$$
\frac { 1 } { N } \sum _ { i = 1 } ^ { N } \sum _ { - b \leq j \leq b , j \neq 0 } \log p \left( w _ { i + j } \mid w _ { i } \right)
$$

采用 softmax 函数计算 Skip-gram 模型定义的 $p \left( \boldsymbol { w } _ { i + j } \mid \boldsymbol { w } _ { i } \right)$ 如式（9）所示：

$$
p \left( w _ { i + j } \mid w _ { j } \right) = \frac { \exp \left( c _ { { w _ { i + j } } } c _ { { w _ { j } } } \right) } { \sum _ { w } \exp \left( c _ { { w } } c _ { { w _ { j } } } \right) }
$$

其中， $c _ { w _ { i + j } }$ 和 $c _ { { _ w _ { j } } }$ 分别为 $\boldsymbol { w } _ { i + j }$ 和 $\boldsymbol { w } _ { \boldsymbol { \Pi } _ { j } }$ 的词向量。

Skip-gram 模型在文本相似性度量和文本分类任务上都有较好的表现，本文采用的词向量模型为Skip-gram模型。我们首先产生特征词的词向量$\boldsymbol { c } _ { \boldsymbol { w } _ { i } } = \big ( \nu _ { 1 } , \nu _ { 2 } , \cdots \nu _ { m } \big )$ ，表 $m$ 示词向量的维度，我们用 $c _ { i , j }$ 表示第 $i$ 个文档中第 $j$ 个单词的词向量，通过式（10）生成文档向量：

$$
\nu _ { i } = \left( 1 / J _ { i } \right) \sum _ { j = 1 } ^ { J _ { i } } c _ { i , j }
$$

其中 $\boldsymbol { J } _  \boldsymbol { i } _ { \} }$ 表示第 $i$ 个文档中单词的个数。

# 3.2 类别信息熵

通常为了提高文本分类的性能，研究人员主要从两个方面开展研究：一是改善分类算法（或学习模型）；二是改善文本数据表示模型。传统上，我们通过向量空间模型（vector space model，VSM）来表示文本[32]，就是在分类之前把每个文本文档都表示成由一定数量的特征词的权重值所组成的向量。特征词在不同类别的文本中出现具有一定的不确定性，这种不确定性可用熵（entropy）来度量。特征词的权重应当根据它在文本分类中的重要性来分配，而特征词的重要性体现在它的类别区分力的大小，因为类别区分力大的词有助于区分不同类别的文本。我们采用香农的信息熵来度量特征词区分类别的能力，得到特征词的类间信息熵函数的定义。

定义1：若训练集文本有 $m$ 个类别，特征词 $t _ { i }$ 在类别 $\boldsymbol { c } _ { j } \left( \ j = 1 , 2 , \dots , m \right)$ 的文档中出现的频率为 $D F _ { i j }$ ，在所有的文档中出现的频率为 $D F _ { i }$ ，则特征词 $t _ { i }$ 的类间信息熵函数（Entropy with Difference 记为 $E D \left( t _ { i } \right) ~ )$ ，定义为：

$$
E D \left( t _ { i } \right) = \ln \left( \frac { 1 } { E _ { d } \left( t _ { i } \right) + \theta } \right)
$$

其中， $\boldsymbol { E } _ { \textit { d } } \left( \boldsymbol { t } _ { i } \right)$ 为特征词 $t _ { i }$ 的类间信息熵， $E _ { d } \left( t _ { i } \right) = - \sum _ { k = 1 } ^ { m } \left( \frac { D F _ { i j } } { D F _ { i } } \right) \times \ln \left( \frac { D F _ { i j } } { D F _ { i } } \right)$ DF,=ΣDFi。由信息熵的定义以及熵最大值定理可知，特征词t，在各个类别中分布得越均匀，熵值 $\boldsymbol { E } _ { \textit { d } } \left( \boldsymbol { t } _ { i } \right)$ 越大。特征词 $t _ { i }$ 在各个类别中分布得越不均匀，熵值 $\boldsymbol { E } _ { \textit { d } } \left( \boldsymbol { t } _ { i } \right)$ 越小。当且仅当特征词 $t _ { i }$ 在各类别中均匀分布时，熵值 $\boldsymbol { E } _ { \textit { d } } \left( \boldsymbol { t } _ { i } \right)$ 最大。所以，我们对 $\boldsymbol { E } _ { \textit { d } } \left( \boldsymbol { t } _ { i } \right)$ 取倒数，为了防止分母为零，我们加上一个 $\theta$ 参数。通过实验我们发现文档的类间分布熵取完倒数后的数值 $1 \big / \big ( E _ { d } \left( t _ { i } \right) + \theta \big )$ 通常较大，虽然文档之间的类间信息熵差异很大，可以起到刻画文档分布的作用，但是淹没了其后的类内信息熵的数值，使得类内信息熵对文档分布的作用完全不能显现，我们对 $1 \big / \big ( E _ { d } \left( t _ { i } \right) + \theta \big )$ 取对数，最终得到文本的类间信息熵。

定义2：若训练集文本有 $m$ 个类别，特征词 $t _ { i }$ 在类别 $\boldsymbol { c } _ { j } \left( \ j = 1 , 2 , \dots , m \right)$ 的第（204号 $k$ 个文档中出现的频率为 $T F \left( t _ { i } , d _ { j k } \right)$ ，则特征词 $t _ { i }$ 的类内信息熵函数（Entropywith Contribution，记为 $\textit { E C } \left( t _ { i } \right)$ ），定义为：

$$
E C \left( t _ { i } \right) = e ^ { j \in \left[ 1 , m \right] ^ { \left( E _ { c } \left( t _ { i } , c _ { j } \right) \right) } }
$$

其， $E _ { _ c } \left( t _ { i } , c _ { _ j } \right) = - \sum _ { j = 1 } ^ { \left| c _ { j } \right| } \frac { T F \left( t _ { i } , d _ { _ { j k } } \right) } { T F \left( t _ { i } , c _ { _ j } \right) } \mathrm { l n } \left( \frac { T F \left( t _ { i } , d _ { _ { j k } } \right) } { T F \left( t _ { i } , c _ { _ j } \right) } \right) ,$ （20 $\boldsymbol { E } _ { \textit { c } } \left( t _ { i } , \boldsymbol { c } _ { \textit { j } } \right)$ 为特征河 $t _ { i }$ 对类别$\boldsymbol { c } _ { \ j }$ 的类内信息熵， $\left| \boldsymbol c _ { j } \right|$ 表示 $\boldsymbol { c } _ { \boldsymbol { \mathscr { j } } }$ 类中的文本数量， $\textit { d } _ { j k }$ 表示第 $\boldsymbol { c } _ { \ j }$ 类中第 $k$ 个文档;$T F \left( t _ { i } , d _ { j k } \right)$ 表示特征词 $t _ { i }$ 在第 $\boldsymbol { c } _ { \ j }$ 类中第 $k$ 个文档 $\textit { d } _ { j k }$ 出现的频率， $T F \left( t _ { i } , c _ { j } \right)$ 表示特征 $t _ { i }$ 在 $\boldsymbol { c } _ { \ j }$ 类文本中出现的总频率。对于类别 $\boldsymbol { c } _ { j } \left( \ j = 1 , 2 , \dots , m \right)$ ，我们取$\boldsymbol { E } _ { c } \left( t _ { i } , \boldsymbol { c } _ { j } \right)$ 中的最大值作为特征词 $t _ { i }$ 的类内信息熵。

考虑到有些具有较高类别区分能力的特征词是低频词，而低频词的类内信息熵比较低，甚至几乎为0，如果直接用 $\underset { j \in [ 1 , m ] } { M a x } \left( E _ { c } \left( t _ { i } , c _ { j } \right) \right)$ 作为类内信息熵函数，会导致该特征词的类间信息熵和类内信息熵结合之后，得到错误的信息度量结果；而且通过实验我们发现加上 $\mathrm { ~ \tt ~ { ~ e ~ } ~ }$ 作为调节因子后的特征信息熵函数比直接使用$\underset { j \in [ 1 . m ] } { M a x } \left( E _ { c } \left( t _ { i } , c _ { j } \right) \right)$ 的特征信息熵函数有更好更显著的文本区分能力。结合特征词的类间信息熵函数和类内信息熵得到特征词的类别信息熵函数：

$$
E D C \left( t _ { i } \right) = E D \left( t _ { i } \right) \times E C \left( t _ { i } \right)
$$

特征词的类别信息熵值越大，说明该特征词区分类别的作用越明显，对文本分类而言，该特征词具有很高的区分度和重要度，通过特征词的类别信息熵对不仅刻画了不同类别之间的文本分布，同时刻画了同一类别内部的文本分布，对文本的描述具有比较细的粒度。文档类别信息熵生成算法的主要步骤如下：

步骤1 对文本集 $\textit { D } = \left\{ d _ { \mathrm { ~ l ~ } } , d _ { \mathrm { ~ 2 ~ } } , \dots \ , d _ { \mathrm { ~ n ~ } } \right\}$ 中的文本 $d _ { \mathrm { ~ } i } \left( 1 \leq i \leq n \right)$ 进行预处理;

步骤2预处理后，文本集中每篇文本 $\boldsymbol { d } _ { \ i }$ 被表示成特征词的集合$\textit { d } _ { i } = \left\{ { t } _ { i 1 } , { t } _ { i 2 } , \dots , { t } _ { i \mid { d } _ { i } \mid } \right\}$ ;

步骤3计算训练文档中每个特征词的类间信息熵

For $i = 1 : \left| d \mathbf { \Omega } _ { n } \right| \left( \mathbf { \Omega } \left| d \mathbf { \Omega } _ { n } \right| \right.$ 为 $\boldsymbol { d } _ { \ i }$ 文档中特征词的数量)计算文档中特征词 $t _ { i }$ 的 $D F _ { i }$ 值和 $D F _ { i j }$ 值；根据式（12）计算文档中特征词 $t _ { i }$ 的 $E D \left( t _ { i } \right)$ 值；步骤4 计算训练文档中每个特征词的类内信息熵For $j ~ = ~ 1 : m$ For $k ~ = ~ 1 : \left| c ~ _ { j } \right| { \pmod { c ~ _ { j } } }$ 为第 $\textit { \textbf { c } } _ { j }$ 类中文档的数量)计算文档中特征词 $t _ { i }$ 的 $T F \left( t _ { i } , d _ { j k } \right)$ 值、 $T F \left( t _ { i } , c _ { j } \right)$ 值和 $\boldsymbol { E } _ { c } \left( t _ { i } , \boldsymbol { c } _ { j } \right)$ 值；根据式（14）计算文档中特征词 $t _ { i }$ 的 $\boldsymbol { E } _ { c } \left( t _ { i } \right)$ 值；步骤5根据式（13），计算文档中特征词 $t _ { i }$ 的 $E D C \left( t _ { i } \right)$ 值；步骤6对 $E D C \left( t _ { i } \right)$ 值归一化;步骤7计算文本集中每个文档的EDC 值： $E D C \ = \ \sum _ { i = 1 } ^ { \left| { d _ { n } } \right| } \ E D C \left( t _ { i } \right)$ 。

# 3.3基于代价敏感的集成极限学习机

加权极限学习机和Boosting的加权极限学习机都没有考虑同类样本之间的权值差异，为了进一步提高极限学习机的分类性能，我们将代价敏感引入到极限学习机中，为不同的样本赋予不同的权重 $w _ { i } \left( i = 1 , 2 , \dots , n \right)$ ，我们用文本的类别

信息熵构建代价敏感矩阵 $\begin{array} { r l } { W } & { = \left[ \begin{array} { l } { w _ { 1 } } \\ { } \end{array} \right. } \end{array}$ ，其中 $w _ { \textit { i } } = E D C \left( x _ { \textit { i } } \right)$ ，代价敏感W  
加权极限学习机的输出参数 $\beta$ 为： $\beta \ = \ \left( W H \ \right) ^ { + } \ W T$ 0

Adaboost.M1算法是通过对训练样本的自适应采样，调整样本权重来调整样本分布，对于错误分类的样本分配更大的权值，对于正确分类的样本赋予更小的权重，这样的权重分配是从错分率上体现每个样本的重要性，实际上同类别样本集中不同样本之间的重要性也有着很大的差异。我们利用Adaboost.M1算法在迭代中权重分配的思想，把代价敏感因子引入Adaboost.M1框架中，将加权极限学习机无缝集成到代价敏感Adaboost.M1框架中。我们通过文本的类别信息熵来刻画每个样本对于类别区分的重要程度，然后通过文本类别信息熵来构建代价敏感因子，在每次迭代中根据每个样本的重要性来更新样本权重。根据训练样本权重更新方法的不同，分别记为AE1-WELM、AE2-WELM和AE3-WELM，本文将这三种方法统称为AEx-WELM方法，算法的主要步骤为：

步骤1对训练数据集和测试数据集进行预处理，去除停用词、去除特殊符号，文本集中每篇文档 $\boldsymbol { d } _ { \ i }$ 被表示成特征词的集合 $d _ { \mathbf { \Phi } _ { i } } = \left\{ { t } _ { i 1 } , { t } _ { i 2 } , \ldots { \mathbf { \Phi } } , { t } _ { i \left| { d _ { \mathbf { \Phi } _ { i } } } \right| } \right\}$ ；

步骤2利用Word2vec生成特征词的词向量；

步骤3 每篇文档 $\boldsymbol { d } _ { \ i }$ 用文档向量 $\nu _ { _ i } = \left( 1 / J _ { _ i } \right) \sum _ { j = 1 } ^ { J _ { i } } c _ { i , j }$ 表示；

步骤4生成代价敏感矩阵 $\boldsymbol { W } _ { \iota } \ : = \ : d i a g \ : \left( \ : E D C \left( \ : x _ { \iota } \ : \right) \right) , i = 1 , \ldots \ : , N$ 步骤5训练权重为 $\boldsymbol { W } _ { \mathrm { ~ } _ { t } }$ 的加权ELM，并作为弱分类器 $h _ { t } \left( x \right)$ ;

步骤6初始化训练文档权值分布 $D _ { \mathrm { ~ l ~ } } \big ( \boldsymbol { x } _ { i } \big ) = E D C \mathrm { ~ \ l ~ } ( \boldsymbol { x } _ { i } )$ ， $i = 1 , \dots , n$ 步骤7For $t = 1 : T$ （ $T$ 为弱 分类器数量)

(1)计算 $h _ { t } \left( x \right)$ 分类错误率：同式（4）；

(2）当分类器分类错误率大于0而且小于0.5时，按照式（14)更新样本权值，否则退出循环；

$$
D _ { t + 1 } \left( x _ { i } \right) = D _ { t } \left( x _ { i } \right) \times \left\{ \begin{array} { l l } { e ^ { E D C \left( x _ { i } \right) \alpha _ { t } } } \\ { E D C \left( x _ { i } \right) e ^ { \alpha _ { t } } } \\ { E D C \left( x _ { i } \right) e ^ { E D C \left( x _ { i } \right) \alpha _ { t } } } \end{array} \right.
$$

$\boldsymbol { D } _ { t } \left( \boldsymbol { x } _ { i } \right)$ 值的归一化同式（6）， $\alpha _ { \scriptscriptstyle t }$ 值同式（7）；

步骤8给定测试样本 $x$ ，输出测试样本的类别标签

$$
\Theta \left( x \right) = \arg \operatorname* { m a x } _ { k } \sum _ { t = 1 } ^ { T } \alpha _ { { \mathrm { \# } } } \left[ { \mathrm { \# } } _ { t } \left( x \right) = k \right]
$$

AE2-WELM和AE3-WELM算法和AC1-WELM算法基本一致，区别在于样本权值的更新上。用式（14a）更新样本权值的为AE1-WELM算法，用式（14b）

更新样本权值的为AE2-WELM算法，用式（14c）更新样本权值的为AE3-WELM 算法。

# 4实验

# 4.1实验数据集

我们将所有的模型在三个标准文本数据集上进行实验。由Ken Lang 收集的20 Newsgroups 数据集、由CMU项目收集的webkb 数据集、由 DavidDLewis 发布的Reuters52数据集，第一个是平衡数据集，后两个是非平衡数据集。20Newsgroups语料库包含20个不同类别的英文新闻，其中总文档数为18846 个，为了提高实验的可靠性，所有的重复文件被删除，剩下11293个文档被用作训练数据集和7528个文档被用作训练数据集。原始WebKB的语料库包含约8300 个英文网站，分为7类，我们选择最常用的4大类，包括 student、faculty、course和 project 4个文本子集，共有 4199 个文档。同样，为了提高实验的可靠性，重复的文件被删除，剩下2756文档被用作训练数据集和1375个文档被用作测试数据集。Reuters52数据集中90类中最常使用的52类称为R52数据集。R52数据集总共9100个文档，其中6532个文档被用作训练数据集，2568个文档被用作测试数据集。我们对数据集首先进行预处理，包括：删除停用词、去掉单个字符和非字母符号、把大写字母转化成小写字母、词干还原、去除低频词。我们使用google提供的词向量训练工具word2vec进行词向量模型训练4。

# 4.2 评价指标

精确率（Precision）、查全率（Recall）和F1值被广泛应用于分类效果评价。微平均和宏平均是两种对分类结果进行全局评价的方法：微平均（Micro-average）是先计算所有文档的分类结果，然后对所有文档求平均；宏平均（Macro-average）是先计算各个类别的分类结果，再对所有类别求平均。具体定义如下：

其中 $M i c r o P \ = \left( \sum _ { i = 1 } ^ { m } a _ { i } \right) \Biggl / \sum _ { i = 1 } ^ { m } b _ { i } \ ; M i c r o R \ = \left( \sum _ { i = 1 } ^ { m } a _ { i } \right) \Biggl / \sum _ { i = 1 } ^ { m } d _ { i } \ ; M i c r o P$ 和MicroR分别表示微平均的精确率和查全率； $M a c r o P$ 和 $M a c r o R$ 分别表示宏平均的精确率和查全率； $\boldsymbol { b } _ { i }$ 是测试集中 $\boldsymbol { c } _ { i }$ 类的文档数； $\boldsymbol { a } _ { i }$ 是其中被正确判断为 $c _ { i }$ 类的文档数； $\boldsymbol { d } _ { \ i }$ 是属于 $\boldsymbol { c } _ { i }$ 类的文档数。微平均倾向于大类，宏平均倾向于小类。为了对分类的整体性能有一个度量，本文采用 $\boldsymbol { F } \boldsymbol { 1 }$ 的微平均 $M i c r o F 1$ 和宏平均 $M a c r o F 1$ 、训练时间(Training time)和测试时间(Testing Time)对分类结果进行评价。

# 4.3 实验结果分析

# （1）参数设置

所有实验均运行在2.4GHZCPU和4G内存环境下。ELM相关算法由python语言实现，每个实验运行10次，取平均值作为结果。文本输入维数在50维到500 维之间进行取值。极限学习机的激活函数通常有：Sigmoid、RBF 和 tanh 函数，通过对以上激活函数性能的比较，我们选取tanh函数作为隐藏节点的激活函数：极限学习机的超参数c和L采用网格搜索法进行选取， $\left\{ 1 0 ^ { \circ } , 1 0 ^ { - 1 } , . . . , 1 0 ^ { - 8 } \right\}$ 为c值的搜索范围，L的搜索范围{100,200,.1000}。

# （2）性能比较

为了验证AEx-WELM的性能，我们把AEx-WELM和ELM、Voting-ELM和Adaboost-WELM在三个标准数据集上做了比较。为了检测这些方法在文本维数变化情况下的性能，我们选取了不同的文本维数，将微平均mf1、宏平均MF1、训练时间和测试时间的变化情况作比较，具体结果见表1-3，表中数据均是各个方法在最佳（c,L）取值下的最优性能值。从表1-3中可以看出，在所有测试中ELM表现都是最差的。在三个标准数据集上，AE1-WELM和AE3-WELM的 MF1 值高于其他所有ELM方法；在 20newsgroups 数据集和 Reuters52 数据集上，AE1-WELM和AE3-WELM的mf1值明显高于其他ELM方法,比其他所有的ELM方法有更好的性能，说明把代价敏感极限学习机结合到Adaboost框架中是有效的。在非平衡数据集Reuters5252和WEbkb上,AE1-WELM和AE3-WELM的性能明显高于ELM、Adaboost-WELM和AE2-WELM，说明文本提出的方法可以改善不平衡多类分类问题的分类效果；同时在平衡数据集20newsgroups上，AE1-WELM和AE3-WELM性能提升就更为明显,超过了其他所有的ELM方法；而且在三个文本标准数据集上，AE1-WELM和AE3-WELM都表现稳定，说明这两种方法很好的泛化性能。在AEx-WELM三种方法中，AE2-WELM表现最差，几乎和Adaboost-WELM的性能差不多，AE2-WELM分布权重在迭代过程中变化剧烈，这可能导致AE2-WELM分类效果没有另外两种好的原因。AE1-WELM和AE3-WELM两者之间相比，后者随着文本维数的增加展现出更优的分类性能和稳定性，所以AE3-WELM是文本推荐的方法。

表1在 20newsgroups上分类性能对比  

<html><body><table><tr><td rowspan="2">dim</td><td rowspan="2">Evaluation measures</td><td rowspan="2">ELM</td><td rowspan="2">Voting-E LM</td><td rowspan="2">Adaboo st-WEL M</td><td rowspan="2">AE1-WE LM</td><td rowspan="2">AE2-WE LM</td><td rowspan="2">AE3-WE LM</td></tr><tr><td></td></tr><tr><td rowspan="4">50</td><td>mf1</td><td>0.756</td><td>0.768</td><td>0.747</td><td>0.772</td><td>0.749</td><td>0.773</td></tr><tr><td>MF1 Training</td><td>0.743</td><td>0.754</td><td>0.741</td><td>0.764</td><td>0.749</td><td>0.764</td></tr><tr><td>time(s)</td><td>5.744</td><td>114.608</td><td>243.455</td><td>242.735</td><td>261.990</td><td>262.045</td></tr><tr><td>time(s) Testing</td><td>1.336</td><td>27.125</td><td>31.078</td><td>31.750</td><td>31.416</td><td>31.368</td></tr><tr><td rowspan="5">100</td><td>mf1</td><td>0.773</td><td>0.786</td><td>0.771</td><td>0.790</td><td>0.771</td><td>0.791</td></tr><tr><td>MF1</td><td>0.759</td><td>0.772</td><td>0.764</td><td>0.781</td><td>0.763</td><td>0.782</td></tr><tr><td>Training time(s)</td><td>6.639</td><td>140.346</td><td>244.671</td><td>244.628</td><td>244.818</td><td>244.773</td></tr><tr><td>Testing</td><td>1.373</td><td>28.121</td><td>31.702</td><td></td><td></td><td></td></tr><tr><td>time(s) mf1</td><td>0.784</td><td>0.800</td><td>0.792</td><td>31.626 0.804</td><td>31.687 0.791</td><td>31.639 0.806</td></tr><tr><td rowspan="5">200</td><td>MF1</td><td>0.770</td><td>0.786</td><td>0.783</td><td>0.794</td><td>0.783</td><td>0.796</td></tr><tr><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>5.931</td><td>119.746</td><td>247.969</td><td>248.189</td><td>248.280</td><td>248.606</td></tr><tr><td>Testing time(s)</td><td>1.396</td><td>28.462</td><td>33.048</td><td>32.989</td><td>33.051</td><td>32.977</td></tr><tr><td>mf1</td><td>0.785</td><td>0.802</td><td>0.791</td><td>0.804</td><td>0.792</td><td>0.805</td></tr><tr><td rowspan="5">300</td><td>MF1</td><td>0.771</td><td>0.787</td><td>0.782</td><td>0.795</td><td>0.784</td><td>0.796</td></tr><tr><td>Training time(s)</td><td></td><td></td><td></td><td>328.235</td><td></td><td>303.106</td></tr><tr><td>Testing</td><td>6.037</td><td>122.124</td><td>306.810</td><td></td><td>322.786</td><td></td></tr><tr><td>time(s)</td><td>1.446</td><td>29.383</td><td>35.506</td><td>35.652</td><td>35.759</td><td>35.705</td></tr><tr><td>mf1</td><td>0.788</td><td>0.805</td><td>0.795</td><td>0.809</td><td>0.780</td><td>0.808</td></tr></table></body></html>

<html><body><table><tr><td></td><td>MF1</td><td>0.774</td><td>0.790</td><td>0.786</td><td>0.800</td><td>0.772</td><td>0.799</td></tr><tr><td></td><td>Training time(s)</td><td>6.122</td><td>123.236</td><td>254.772</td><td>255.044</td><td>254.767</td><td>254.918</td></tr><tr><td></td><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>time(s)</td><td>1.506</td><td>30.449</td><td>35.167</td><td>35.082</td><td>35.241</td><td>35.090</td></tr><tr><td></td><td>mf1</td><td>0.786</td><td>0.805</td><td>0.797</td><td>0.808</td><td>0.795</td><td>0.809</td></tr><tr><td></td><td>MF1</td><td>0.773</td><td>0.790</td><td>0.788</td><td>0.799</td><td>0.786</td><td>0.800</td></tr><tr><td>500</td><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>time(s)</td><td>7.790</td><td>157.031</td><td>324.748</td><td>311.323</td><td>313.438</td><td>307.131</td></tr><tr><td></td><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>time(s)</td><td>1.631</td><td>33.289</td><td>37.824</td><td>38.742</td><td>38.265</td><td>38.377</td></tr></table></body></html>

表2在Reuters52上分类性能对比  

<html><body><table><tr><td rowspan="2">dim</td><td rowspan="2">Evaluation measures</td><td rowspan="2">ELM</td><td rowspan="2">Voting-E LM</td><td rowspan="2">Adaboo st-WEL M</td><td rowspan="2">AE1-WE LM</td><td rowspan="2"></td><td rowspan="2">AE3-WE LM</td></tr><tr><td>AE2-WE LM</td></tr><tr><td rowspan="4">50</td><td>mf1 MF1</td><td>0.917 0.607</td><td>0.919 0.614</td><td>0.920 0.644</td><td>0.931 0.661</td><td>0.920 0.620</td><td>0.929 0.660</td></tr><tr><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s) Testing</td><td>4.828</td><td>96.317</td><td>110.873</td><td>110.953</td><td>111.173</td><td>111.093</td></tr><tr><td>time(s)</td><td>0.354</td><td>7.240</td><td>8.597</td><td>8.580</td><td>8.593</td><td>8.590</td></tr><tr><td rowspan="4">100</td><td>mf1</td><td>0.918</td><td>0.923</td><td>0.927</td><td>0.938</td><td>0.925</td><td>0.936</td></tr><tr><td>MF1</td><td>0.602</td><td>0.615</td><td>0.661</td><td>0.684</td><td>0.666</td><td>0.671</td></tr><tr><td>Training time(s)</td><td>4.842</td><td>102.547</td><td>111.240</td><td>111.207</td><td>111.303</td><td>111.207</td></tr><tr><td>Testing time(s)</td><td>0.366</td><td>7.900</td><td>9.187</td><td>9.127</td><td>9.023</td><td>9.127</td></tr><tr><td rowspan="5">200</td><td>mf1</td><td>0.922</td><td>0.925</td><td>0.925</td><td>0.938</td><td>0.926</td><td>0.937</td></tr><tr><td>MF1</td><td>0.621</td><td>0.616</td><td>0.650</td><td>0.682</td><td>0.661</td><td>0.679</td></tr><tr><td>Training time(s)</td><td>4.880</td><td>98.303</td><td>114.353</td><td>114.343</td><td>114.290</td><td>114.360</td></tr><tr><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s) mf1</td><td>0.390 0.923</td><td>7.850 0.925</td><td>9.710 0.926</td><td>9.673 0.938</td><td>9.695 0.926</td><td>9.660 0.936</td></tr><tr><td rowspan="4">300</td><td>MF1</td><td>0.618</td><td>0.626</td><td>0.656</td><td>0.674</td><td>0.662</td><td>0.678</td></tr><tr><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s) Testing</td><td>4.990</td><td>100.000</td><td>112.283</td><td>112.460</td><td>112.573</td><td>112.683</td></tr><tr><td>time(s)</td><td>0.410</td><td>8.138</td><td>9.578</td><td>9.578</td><td>9.583</td><td>9.560</td></tr><tr><td rowspan="4">400</td><td>mf1</td><td>0.922</td><td>0.926</td><td>0.925</td><td>0.939</td><td>0.927</td><td>0.939</td></tr><tr><td>MF1</td><td>0.617</td><td>0.618</td><td>0.659</td><td>0.685</td><td>0.653</td><td>0.680</td></tr><tr><td>Training</td><td>5.002</td><td>101.698</td><td>118.338</td><td>118.345</td><td>118.425</td><td>118.410</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td colspan="2">time(s)</td><td colspan="6"></td></tr><tr><td rowspan="9"></td><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>0.422</td><td>8.498</td><td>10.530</td><td>10.483</td><td>10.473</td><td>10.513</td></tr><tr><td>mf1</td><td>0.923</td><td>0.925</td><td>0.928</td><td>0.937</td><td>0.926</td><td>0.937</td></tr><tr><td>MF1</td><td>0.621</td><td>0.625</td><td>0.666</td><td>0.682</td><td>0.665</td><td>0.679</td></tr><tr><td>Training</td><td>5.190</td><td>102.505</td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td></td><td></td><td>118.398</td><td>118.355</td><td>118.428</td><td>118.575</td></tr><tr><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>0.438</td><td>8.883</td><td>10.423</td><td>10.400</td><td>10.423</td><td>10.418</td></tr></table></body></html>

表3在Webkb上分类性能对比  

<html><body><table><tr><td rowspan="2">dim</td><td rowspan="2">Evaluation measures</td><td rowspan="2">ELM</td><td rowspan="2">Voting-E LM</td><td rowspan="2">Adaboo st-WEL</td><td rowspan="2">AE1-WE</td><td rowspan="2">AE2-WE LM</td><td rowspan="2">AE3-WE LM</td></tr><tr><td>LM M</td></tr><tr><td rowspan="4">50</td><td>mf1</td><td>0.850 0.834</td><td>0.873 0.860</td><td>0.864 0.850</td><td>0.876 0.865</td><td>0.867 0.851</td><td>0.874 0.857</td></tr><tr><td>MF1 Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>2.078</td><td>41.602</td><td>69.995</td><td>70.121</td><td>70.059</td><td>70.237</td></tr><tr><td>Testing time(s)</td><td>0.276</td><td>5.616</td><td>6.935</td><td>6.896</td><td>70.059</td><td>6.890</td></tr><tr><td rowspan="4">100</td><td>mf1</td><td>0.863</td><td>0.888</td><td>0.881</td><td>0.886</td><td>0.877</td><td>0.885</td></tr><tr><td>MF1 Training</td><td>0.850</td><td>0.876</td><td>0.867</td><td>0.879</td><td>0.863</td><td>0.874</td></tr><tr><td>time(s) Testing</td><td>2.084</td><td>41.696</td><td>70.215</td><td>70.387</td><td>70.376</td><td>70.409</td></tr><tr><td>time(s)</td><td>0.281</td><td>5.684</td><td>7.041</td><td>6.954</td><td>7.003</td><td>6.951</td></tr><tr><td rowspan="4">200</td><td>mf1</td><td>0.866</td><td>0.896</td><td>0.883</td><td>0.892</td><td>0.881</td><td>0.894</td></tr><tr><td>MF1 Training</td><td>0.853</td><td>0.884</td><td>0.869</td><td>0.884</td><td>0.867</td><td>0.885</td></tr><tr><td>time(s) Testing</td><td>2.129</td><td>42.614</td><td>71.397</td><td>71.572</td><td>71.467</td><td>71.638</td></tr><tr><td>time(s)</td><td>0.288</td><td>5.877</td><td>7.188</td><td>7.149</td><td>7.173</td><td>7.152</td></tr><tr><td rowspan="4">300</td><td>mf1</td><td>0.866</td><td>0.897</td><td>0.884</td><td>0.893</td><td>0.884</td><td>0.893</td></tr><tr><td>MF1</td><td>0.854</td><td>0.886</td><td>0.871</td><td>0.884</td><td>0.871</td><td>0.885</td></tr><tr><td>Training time(s)</td><td>2.165</td><td>43.321</td><td>72.933</td><td>73.062</td><td>73.008</td><td>73.153</td></tr><tr><td>Testing time(s)</td><td>0.322</td><td>6.482</td><td>7.777</td><td>7.726</td><td>7.744</td><td>7.726</td></tr><tr><td rowspan="5">400</td><td>mf1</td><td>0.865</td><td>0.893</td><td>0.884</td><td>0.893</td><td>0.880</td><td>0.893</td></tr><tr><td>MF1</td><td>0.851</td><td>0.882</td><td>0.871</td><td>0.883</td><td>0.865</td><td>0.883</td></tr><tr><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>2.211</td><td>44.316</td><td>73.760</td><td>73.795</td><td>73.799</td><td>74.188</td></tr><tr><td>Testing</td><td>0.306</td><td>6.190</td><td>7.477</td><td>7.449</td><td>7.505</td><td>7.445</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">time(s)</td><td rowspan="2"></td><td rowspan="2"></td><td colspan="3"></td></tr><tr><td>mf1</td><td>0.868</td><td>0.894 0.882</td><td>0.890</td><td>0.881</td></tr><tr><td rowspan="5">500</td><td>MF1</td><td>0.853</td><td>0.881</td><td>0.882</td><td>0.880</td><td>0.867</td><td>0.892 0.882</td></tr><tr><td>Training</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>2.279</td><td>45.458</td><td>74.773</td><td>74.970</td><td>74.876</td><td>75.059</td></tr><tr><td>Testing</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>time(s)</td><td>0.314</td><td>6.399</td><td>7.669</td><td>7.629</td><td>7.663</td><td>7.626</td></tr></table></body></html>

AEx-WELM和ELM相比：从图1-3中可以看到，对于所有的数据集，将极限学习机嵌入Adaboost框架中的四种方法Adaboost-WELM、AE1-WELM、AE2-WELM、AE3-WELM都比ELM方法在分类性能上有显著提高，其中AE1-WELM和AE3-WELM有着更为明显的优势。在三个标准数据集中,AE1-WELM和AE3-WELM的综合指标MF1值都超过了ELM和其他类型的ELM的MF1值，尤其在20newsgroups（平衡数据集）和Reuters52（非平衡数据集）上的MF1值比起其他所有的ELM方法有着更为明显的提高；在Webkb 数据集上（非平衡数据集）上的mfl值要略低于Voting-ELM，但是MF1值仍然高于Voting-ELM方法。

![](images/4c66b01ba6aedd86bbe8a4928aa17d29deb14a18c1e13454cadf578e1334ecac.jpg)  
图120newsgroups 数据集上的分类性能

![](images/91178f4e6b3042a3c2a1d94a7d091b5725ddbc7b05b91d56f228ce697b33efb4.jpg)  
图2Reuters52数据集上的分类性能

![](images/846d04c6186d647edda06f4dc82cdd8540b309dddab4c26f1279b333442088d7.jpg)  
图3Webkb 数据集上的分类性能

AEx-WELM和Voting-ELM比：从图1-3中可以看到，在平衡数据集20newsgroups上AE1-ELM和AE3-WELM比Voting-ELm要略微高一点，在非平衡数集Reuters52上Voting-ELM效果要比AE1-ELM和AE3-WELM差很多。但是在非平衡数据集Webkb上，Voting-ELM却取得了比其他所有ELM都更好的效果，这是由于Webkb数据集较小，而且我们实验中只取了Webkb常用的4类，类的数目也较小，而mf1值是倾向于大类的，所以AE1-ELM和AE3-WELM的 mfl值会比Voting-ELM略低，当然这也和Voting-ELM方法中我们采用的随机采样算法将数据集中文本特征的多样性充分发挥出来有一定的关系，所以在三个文本数据集中Voting-ELM都表现出了不错的性能;尽管如此在Webkb 数据集上，AE1-ELM和AE3-WELM的MF1值还是略微比Voting-ELM高出一点；而且到了像20newsgroups 和Reuters52这类文本数量要远远多于WEbkb 的数据集中，Voting-ELM的性能就明显下降，不能取得像AE1-ELM和AE3-WELM同样显著的分类效果。

基于词向量的文本信息表达也一定程度上丰富了文本的特征表示，不仅有效降低了文本维度，而且在低维空间上（通常100 维）就已经可以取得传统文本VSM特征表达在1000 维（甚至更高维度）上的分类性能；同时我们从图1-3中也观察到，6种的ELM方法在文本维数超过400维之后性能都呈现下降趋势，这说明过高的维数不仅给极限学习机造成了负担而且增加了噪音，而且影响了分类性能。

图4-6显示在三个文本标准数据集上，当文本向量为300 维时，随着隐节点和c值变化的AE3-WELM算法mf1值的变化。从图中我们可以观察到，虽然较多的隐藏节点能够帮助AE3-WELM取得更好的分类结果，但是当隐藏节点数超过 400以后其mf1值较为稳定，过大的隐藏节点数起不到什么太大影响。当隐藏节点达到一定程度后，分类性能会变得不稳定，超过800以后分类性能会性能随着隐藏节点的增加而下降，这种情况应该是由于过拟合造成的。从图4-6中可以看出，正则化参数c是一个很关键的因素，性能随着c值的减少达到一个稳定值。正则化参数c对性能的影响要大于隐藏结点，当c值较小时接近 $1 0 ^ { - 5 }$ 时，AE3-WELM对于隐藏节点参数的选取并不敏感。

![](images/59ea8dab32511c769ab5b4df5f64e7cd8f2e7ec45cb566f7fe787b5ed81c9542.jpg)  
图4随着隐节点和c值变化的AE3-WELMmfl 值的变化（20newsgroups 数据集）

![](images/ec01ad31a3de5b68f76f3e5497c0c547ecb2aea66d6f236284f3d1a1c99d3bb4.jpg)  
图5随着隐节点和c值变化的AE3-WELMmf1值的变化（Reuters52数据集）

图7-9显示了三个文本标准数据集上，当文本向量为300维时，6种ELM方法随着文本向量维度的变化模型训练时间的变化。因为Voting-ELM需要集成多个子分类器，而Adaboost-WELM和AEx-WELM方法都需要经过较多的迭代，所以它们的训练时间消耗要比ELM长很多。AEx-WELM和Adaboost-WELM的训练时间要比ELM长很多，比Voting-ELM也要长出一些。但是我们更观察到这样的细节：Voting-ELM的训练时间是ELM的倍数，这个倍数取决于Voting-ELM当中使用的集成分类器数量，所以这个训练时间的增加是线性的；AEx-WELM和Adaboost-WELM虽然训练时间比ELM用时长很多，训练时间的增长规模是和Adaboost迭代次数相关的，但是我们发现这个迭代次数并不是随着文本向量维度和隐藏节点增加而线性增加的，也就是说训练时间的增加从总体上看是低于线性增长的，所以在Reuters52数据集中会产生基于Adaboost的4种ELM方法和Voting-ELM随着文本向量维度的增加越来越接近的现象。在AEx-WELM的3种方法AE1-WELM、AE2-WELM、AE3-WELM中，在训练时间和测试时间上基本一致，没有太大的差别，没有任何一种方法有明显的优势。

![](images/8fc9210cc3313586fd063f6b6eeccd93f622a22ee1d83e26be21fe98109a5871.jpg)  
图6随着隐节点和c值变化的AE3-WELMmf1值的变化（Webkb数据集）

![](images/0f4824462c324c47399a7fd4307a4deef08814f58fccf353ce180b78497e6968.jpg)  
图720newsgroups数据集上的训练时间对比

![](images/cd837a20b757b838d844eca513ad533ec5d51df56e309f2e4dbbd51530cbd965.jpg)  
图8Reuters52数据集上的训练时间对比

![](images/3c5dcfe001a52359293eeb02009e6025c9a1efba3f248994906765aa01c63e54.jpg)  
图9Webkb数据集上的训练时间对比

# 5结论

传统的VSM文本表达产生高维而稀疏的文本特征给极限学习机的计算增加了负担，本文针对这个问题将词向量模型作为文本表达方法。本文通过文本类别信息熵对样本的重要性进行度量，并且从样本重要性角度生成代价敏感矩阵和代价敏感因子，通过把代价敏感极限学习机集成到Adaboost.M1框架中以期提高文本分类性能。实验表明：在非平衡数据集和平衡数据集，AE1-WELM的AE3-WELM综合分类性能指标均优于其他类型的极限学习机，其中AE3-WELM的整体性能优于AE1-WELM。在将来的工作中，将研究如何在词向量的基础上进一步降低文本特征维度，选取更为合理的代价敏感函数来进一步减少AEx-WELM的计算花销以及如何进一步优化AEx-WELM框架，以获得更好的文本分类性能。

# 参考文献:

[1] Samworth R J. Optimal weighted nearest neighbour classifiers[J]. The Annals of Statistics, 2012，40(5):2733-2763.   
[2] Zhang H, Berg A C, Maire M,et al. SVM-KNN: Discriminative nearest neighbor classification for visual category recognition[C]. Computer Vision and Pattern Recognition, 2006 IEEE Computer Society Conference on，2006:2126-2136.   
[3] Chen J, Huang H, Tian S,et al.Feature selection for text classification with Naive Bayes[J]. Expert Systems with Applications，2009，36(3): 5432-5435.   
[4] Takahashi F， Abe S. Decision-tree-based multiclass support vector machines[C]． Neural Information Processing,2002. ICONIP'02. Proceedings of the 9th International Conference on, 2002: 1418-1422. Science and Technology，2003，18(5):640-647.   
[6] Widyantoro D H, Yen J. A fuzzy similarity approach in text classification task[C]. Fuzzy Systems，2000.FUZZ IEEE 2000.The Ninth IEE International Conference on，2000:653-658. [7] Chang C-C,Lin C-J. LIBSVM:a library for support vector machines[J]. ACM transactions on intelligent systems and technology (TIST)，2011，2(3): 27.   
[8] Ghiassi M, Olschimke M, Moon B, et al. Automated text classification using a dynamic artificial neural network model[J]． Expert Systems with Applications，2012，39(12):10967-10976. [9] Lam H-K, Ekong U,Liu H, et al. A study of neural-network-based classifiers for material classification[J]. Neurocomputing， 2014，144: 367-377.   
[10] Bigi B. Using Kullback-Leibler distance for text categorization[C]. European Conference on Information Retrieval， 2003: 305-319.   
[11] Huang G-B, Zhu Q-Y， Siew C-K. Extreme learning machine: theory and applications[J]. Neurocomputing，2006，70(1):489-501.   
[12] Qin A K, Huang VL, Suganthan PN. Differential evolution algorithm with strategy adaptation for global numerical optimization[J]. IEEE transactions on Evolutionary Computation, 2009,13(2): 398-417.   
[13] Liu Y,Loh H, Tor S. Comparison of extreme learning machine with support vector machine for text classification[J]. Innovations in Applied Artificial Intelligence,2005:390-399. [14] Zheng W, Qian Y,Lu H. Text categorization based on regularization extreme learning machine[J]. Neural Computing and Applications， 2013， 22(3-4): 447-456.   
[15] Zheng W, Tang H, Qian Y. Collaborative work with linear classifier and extreme learning machine for fast text categorization[J].World Wide Web，2015，18(2): 235-252.   
[16] Zhao X-G, Wang G,Bi X,et al. XML document classification based on ELM［J]. Neurocomputing, 2011，74(16): 2444-2451.   
[17] Zhao X, Bi X, Qiao B. Probability based voting extreme learning machine for multiclass XML documents classification[J].World Wide Web，2014，17(5):1217-1231.   
[18] Duan L,Yuan B,Wu C,et al.: Text-image separation and indexing in historic patent document image based on extreme learning machine， Proceedings of ELM-2014 Volume 2: Springer， 2015: 299-307.   
[19] YuH, Chen L, Zheng W. Chinese text sentiment classification based on kernel extreme learning machines[J]． Journal of China University of Metrology，2016,2:020.   
[20］李永强．基于粒子群优化的极限学习机的 XML 文档分类中的研究与应用[D]．东北大学，2013. Li Yongqiang，Research and Application of XML Classification Based on Extreme learning Mchine with Particle Swarm Optimization[D]. Northeastern University，2013   
[21] Roul R K, Nanda A， Patel V，et al. Extreme learning machines in the field of text classification[C].SoftwareEngineering，ArtificialIntelligence，Networkingand Parallel/Distributed Computing (SNPD)，2015 16th IEE/ACIS International Conference on， 2015: 1-7.   
[22] Roul R K, Sahay SK. K-means and Wordnet Based Feature Selection Combined with Extreme Learning Machines for Text Classification[C]. International Conference on Distributed Computing and Internet Technology，2016:103-112.   
[23］陆慧娟，安春霖，马小平,等．基于输出不一致测度的极限学习机集成的基因表达数据分类［J]．计 算机学报．2013，(2)：341-348. LU Hui-Juan，An Chun-Lin,Ma Xiao-Ping，etal. Disagreement measure Based Ensemble of Extreme learning Machine for Gene Expression Data Classification[J]. Chinanese Journal of Computers. 2013, (2):341-348.   
[24] Ditterrich T. Machine learning research: four current direction[J].Artificial Intelligence Magzine，1997，4:97-136.   
[25] Jiang Y, Shen Y,Liu Y,et al. Multiclass AdaBoost ELM and its application in LBP based face recognition[J]. Mathematical Problems in Engineering，2015,2015.   
[26］黄海波，李人宪，黄晓蓉，等．基于样本熵与 ELM-Adaboost 的悬架减振器异响声品质预测[J]．振 动与冲击，2016，(13)：125-133.   
HUANG Hai-bo,LI Ren-xian,HUANG Xiao-rong，et al. Prediction of a suspension shock absorber' s sound metric based on sample entropy and ELM-adaboost[J]． Journal of Vibration and Shock， 2016,(13): 125-133.   
[27] Xu Y,Wang Q，Wei Z,et al. Traffic sign recognition based on weighted ELM and AdaBoost[J]. Electronics Letters，2016,52(24):1988-1990.   
[28] LiK, Kong X,Lu Z,et al. Boosting weighted ELM for imbalanced learning[J]. Neurocomputing, 2014，128:15-21.   
[29] Freund Y, Schapire R E. A desicion-theoretic generalization of on-line learning and an application to boosting[C]. European conference on computational learning theory，1995: 23-37. [30] Turian J，Ratinov L，Bengio Y. Word representations:a simple and general method for semi-supervised learning[C]. Proceedings of the 48th annual meeting of the association for computational linguistics， 2010: 384-394.   
[31] Mikolov T, Chen K, Corrado G,et al. Efficient estimation of word representations in vector space[J].arXiv preprint arXiv:1301.3781，2013.   
[32] Sebastiani F. Machine learning in automated text categorization[J]. ACM computing surveys (CSUR)，2002，34(1):1-47.

(通讯作者：李明E-mail:liming@magicalthink.com)

# 作者贡献声明：

李明：提出研究思路，设计研究方案，进行实验，论文起草；  
肖培伦：数据的获取、提供与分析，进行实验；  
顾心盟：进行实验；  
张矩：论文最终版本修订。