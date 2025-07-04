# 基于降噪自动编码器的中文新闻文本分类方法研究

刘红光 马双刚 刘桂锋(江苏大学科技信息研究所 镇江 212013)

摘要：【目的】借助深度学习理论，解决传统特征选择方法容易导致特征项不明确、分类精度下降的问题。【方法】对中文新闻文本进行分类时，使用降噪自动编码器构建一个深层网络来学习对文本的压缩及分布式的表示，并在网络最后一层采用 SVM 算法将其分类到具体的类别中去。【结果】随着样本数目的增大，分类准确率、召回率和F值都在上升，且比KNN算法、BP算法和SVM算法取得了更优的分类效果，平均分类准确率达到 $9 5 \%$ 以上。【局限】数据量依然较小，且并没有完全发挥深度学习并行处理大容量数据的优势。【结论】该方法能提高特征项提取的准确性，并能提高分类效果。

关键词:降噪自动编码器支持向量机特征提取文本分类分类号：G350

# 1引言

信息技术的飞速发展，使得海量的信息数据以指数级的模式不断增长，标志着大数据时代的来临。在此背景下，对海量文本信息的有效组织与利用显得尤为重要。文本分类技术以其对海量信息高效、准确地管理和定位的优势被广泛应用在社会生活的各个领域，并取得了长足的发展。

在文本分类过程中，一般采用向量空间模型(VectorSpaceModel,VSM)对文本进行表示。而文本数据结构和语义的复杂性，使得经分词、删除停用词后的特征向量空间维度依然很高，需要对其进一步优化。最常用的方法就是进行降维操作，降维之后文本分类器要处理的文本数据规模大大降低，噪声也大大减少。特征降维的常用方法有：特征选择和特征提取。特征选择一般采用基于统计的方法，得到的特征集是原始特征集中的一个子集，常见的有卡方检验[1(CHI-Square）、互信息[²(Mutual Information,MI)、信息增益[3](Information Gain,IG)等。关于特征选择方法的相关研究4表明：IG方法的性能相对较好。特征提取方法能够从原特征集中构造或者合成新的特征项，从而降低文本特征的空间维度，研究人员先后提出了许多不同的特征提取方法，如互近邻聚类算法[5]、最大熵模型[等。虽然这些传统的特征选择或提取方法能识别出大部分特征，但是也普遍存在着特征识别度较差的问题。如指定类别中很少出现但在其他类别中频繁出现的特征可能会被选择出来，进而导致特征项丢失;而经过提取后的特征可能会出现误差，因而不能准确代表原有数据集，尤其是从数据量较大、维数较多的数据集中提取出的特征项，更容易出现误差，最后导致分类精度下降。

2006年，Hinton等[7介绍自动编码器(Auto Encoder,AE)构建的深度网络在图像和文本的特征降维方面的应用，取得了比传统的特征降维方法更优的效果。因此，学者纷纷将AE应用到特征提取过程中，并不断提出稀疏自动编码器[8(Sparse Auto Encoder, SAE)、降噪自动编码器[9](Denoising Auto Encoder,DAE)和卷积自动编码器[10](Convolutional Auto Encoder,CAE)等不同改进算法。其中，DAE在特征提取中的应用较为广泛，主要应用于对动态视频纹理[1]、音频[12]、图像[13]的特征提取中，在医学诊断[14]中也有所应用。本文只对DAE在文本特征提取中的应用进行深入研究。

文本中存在许多噪声，影响着分类的精度。因此相关学者选择采用DAE进行文本特征的提取，如刘勘等[15]针对短文本的特点，提出一种基于深层DAE的特征提取及聚类算法，有效地解决了短文本空间向量的高维、稀疏问题；秦胜君等[1通过改进DAE，实现了无监督的样本分类，对不平衡率较高的样本具有良好的适应性。虽然这部分研究相对较少，但是可以看到，DAE构建的深度网络能够针对文本数据中噪声较大的特点，提取出更加准确地代表原始文本的特征编码，并有效去除其中的噪声，再结合分类算法进行文本分类时能够大大提高分类准确率。

与文献[15-16]不同，本文将DAE应用到新闻文本的特征提取中，首先使用DAE构建深度网络自动学习得到文本的低维特征；然后在网络的最顶层采用线性分类器支持向量机(SupportVectorMachine,SVM)算法对得到的低维特征编码进行分类输出，根据输出的结果实现分类；最后分别与K近邻(K-NearestNeighbors,KNN)算法、SVM算法和反向传播神经网络(ErrorBackPropagation,BP)算法进行比较，证明此方法的有效性。

# 2相关理论基础

# 2.1基于DAE的特征提取

AE[7,17]构造的是一种无监督的深度网络结构，首先经过无监督的逐层贪心预训练与系统性的参数优化，得到多层非线性网络，然后利用此网络从无类标数据中提取出高维复杂输入数据的分层特征，并得到原始数据的分布式特征表示，能够比较好地复现输入的数据信号。AE主要由两个部分组成：编码器和解码器，结构示意图如图1所示：

![](images/4cfc967e6d01681453cd0a0a09835a765800d6303954d46adbe8781ffabe0b2f.jpg)  
图1 AE结构示意图

但是，AE无法消除数据中的噪声干扰。为了消除噪声干扰，获得更加鲁棒的特征，Vincent 等[18]提出可以用概率分布(通常使用二项分布)随机处理原始输入矩阵 $X _ { \circ }$ ，对原始数据进行破坏处理得到X，然后对X进行编码处理，后续过程即与AE的运算过程相同，此改进后的编码器即为降噪自动编码器，结构示意图如图2所示：

![](images/8a3dc966c63464db7c539595069b712fc9b12f1fc825cc7304f07f565282fb74.jpg)  
图2降噪自动编码器结构模型示意图

编码器 $\mathrm { f } ( \hat { \mathbf { x } } )$ 用于高维数据的降维，首先对输入向量 $\mathbf { x }$ 进行破坏处理得到x，然后输入到编码器 $\mathrm { f } ( \hat { \mathbf { x } } )$ ，经过线性变换和激活函数的作用，最后得到隐含的编码结果y。解码器 $\operatorname { g } ( \operatorname { y } )$ 用于低维编码的重构过程，即将隐含层数据映射回重构 $\mathbf { \dot { z } }$ ，分别表示为如下函数：

$$
\mathbf { y } = \mathbf { f } ( { \hat { \mathbf { x } } } ) = \mathbf { S } _ { \mathbf { f } } ( \mathbf { W } { \hat { \mathbf { x } } } + \mathbf { b } _ { \mathbf { y } } )
$$

$$
\mathbf { \boldsymbol { z } } = \mathbf { \boldsymbol { g } } ( \mathbf { \boldsymbol { y } } ) = \mathbf { \boldsymbol { S } } _ { \mathrm { g } } ( \mathbf { \boldsymbol { W } } ^ { \prime } \mathbf { \boldsymbol { y } } + \mathbf { \boldsymbol { b } } _ { \mathrm { z } } )
$$

其中, $\mathrm { \bf S } _ { \mathrm { f } }$ 是非线性激活函数，其表达式为:

$$
\mathbf { S } _ { \mathrm { f } } = \mathrm { s i g m o i d } ( \mathbf { y } ) = \frac { 1 } { 1 + { \mathrm { e } } ^ { - \mathbf { y } } }
$$

$\mathrm { S _ { g } }$ 是解码器的激活函数，本文也采用 sigmoid 函数， $\mathbf { W } ^ { \prime } = \mathbf { W } ^ { \mathrm { T } }$ ，是 $\mathrm { ~ W ~ }$ 的转置，因此只需要训练W即可,${ \sf b } _ { \mathrm { y } }$ 和 $\boldsymbol { \mathsf { b } } _ { \mathrm { z } }$ 是偏倚向量。

DAE的训练过程即是在训练样本集D上寻找参数 $\boldsymbol { \Theta } = \{ \mathrm { W } , \boldsymbol { \mathrm { b } } _ { \mathrm { y } } , \boldsymbol { \mathrm { b } } _ { \mathrm { z } } \}$ 的最小化重构误差，重构误差的表达式如下:

$$
\mathrm { J _ { A E } = \sum _ { x \in D } L ( x , g ( f ( \hat { x } ) ) ) }
$$

其中，L为重构误差函数，文献[19]表明在实验过程中，交叉熵损失函数一直优于平方差损失函数，因此本文采用交叉熵损失函数，表达式如下：

$$
\mathrm { L ( x , z ) = - \frac { 1 } { n } \sum _ { i = 1 } ^ { d _ { x } } [ x _ { i } l n z _ { i } + ( 1 - x _ { i } ) l n ( l - z _ { i } ) ] }
$$

其中, $\mathbf { \bar { n } }$ 是训练集样本数, $\mathbf { X } _ { \mathrm { i } }$ 是第 $\mathrm { ~ i ~ }$ 个输入, $z _ { \mathrm { i } }$ 为对应的第i个解码重构后的数据，

自动编码器采用经典的随机梯度下降算法进行训练，在每个迭代过程中，利用公式(6)更新权重矩阵:

$$
\mathbf { W } \gets \mathbf { W } - \boldsymbol \Phi \times \frac { \partial \mathrm { L } ( \mathbf { x } , \mathbf { y } ) } { \partial \mathbf { W } }
$$

$$
\mathsf { b } _ { \mathrm { y } } \gets \mathsf { b } _ { \mathrm { y } } - \displaystyle \Phi \times \frac { \hat { \alpha } \mathrm { L } ( \mathbf { x } , \mathbf { y } ) } { \hat { \sigma } \mathsf { b } _ { \mathrm { y } } } \quad \mathsf { b } _ { \mathrm { z } } \gets \mathsf { b } _ { \mathrm { z } } - \displaystyle \Phi \times \frac { \hat { \alpha } \mathrm { L } ( \mathbf { x } , \mathbf { y } ) } { \hat { \sigma } \mathsf { b } _ { \mathrm { z } } }
$$

其中， $\boldsymbol { \Phi }$ 是学习率, ${ \sf b } _ { \mathrm { y } }$ 和 $\boldsymbol { \mathsf { b } } _ { \mathrm { z } }$ 采用与之相同的更新方式。

# 2.2基于SVM的分类

SVM算法[20]的训练过程是要找到一个超平面，使得这个超平面的正反例分别落在两侧，在所有超平面中与正反例的距离最大且到最近的正反例的距离相等，然后对未知类别的样本数据，计算其位于超平面一侧，即为其分属的类别。

在线性可分的情况下，分类线性方程为$( \mathbf { w } \cdot \mathbf { x } ) + \mathbf { b } = 0$ ，对此方程进行正则化，使得每一个线性可分的样本 $( \mathrm { x } _ { \mathrm { i } } , \mathrm { y } _ { \mathrm { i } } ) , \mathrm { i } = 1 , 2 , \cdots , l , \mathrm { x } \in \mathrm { R } ^ { \mathrm { n } } , \mathrm { y } \in \{ - 1 , + 1 \}$ ，均满足:

$$
\mathrm { y _ { i } } [ ( \mathrm { w } \cdot \mathrm { x _ { i } } ) + \mathrm { b } ] - 1 \geq 0 \quad \mathrm { ~ i = 1 , 2 , } { \cdots } , l
$$

其中： $\mathbf { X _ { i } }$ 是输入的第i个样本， $l$ 为样本数, $\mathbf { w }$ 是可调的权值向量,b是偏置。 $\mathbf { y } _ { \mathrm { { i } } } \in \left\{ - 1 , + 1 \right\}$ 表示相应 $\mathbf { X } _ { \mathrm { i } }$ 的期望分类。

为了求得最优分类超平面，需要在满足公式(7)下使得分类间隔 $\mathrm { m a r g i n } = 2 / \left| \left| \mathbf { w } \right| \right|$ 最大，即使得 $\Vert \mathbf { w } \Vert ^ { 2 }$ 最小，这是一个典型的二次规划问题，目标函数为:

$$
\operatorname* { m i n } _ { \mathbf { w } } \mathrm { L } ( \mathbf { w } , \mathbf { b } , \boldsymbol { \alpha } ) = \frac { 1 } { 2 } \| \mathbf { w } \| ^ { 2 } - \sum _ { \mathrm { i } = 1 } ^ { l } \alpha _ { \mathrm { i } } \{ [ ( \mathbf { w } \cdot \mathbf { x _ { i } } ) + \mathbf { b } ] - 1 \}
$$

利用拉格朗日优化方法可以将上述问题转化为其对偶问题，即加入约束条件 $\sum \mathrm { { _ { i = 1 } ^ { \it { l } } } } \mathrm { { a _ { i } } } \mathrm { { y _ { i } } } = 0$ 和$\mathbf { a } _ { \mathrm { i } } \geqslant 0 , \mathrm { i } = 1 , 2 , \cdots l$ ，对 $\mathbf { { a } _ { i } }$ 求解下列函数的极大值:

$$
\operatorname { Q } ( \alpha ) = \sum _ { \mathrm { i = 1 } } ^ { l } \alpha _ { \mathrm { i } } - \frac { 1 } { 2 } \sum _ { \mathrm { i , j = 1 } } ^ { l } \alpha _ { \mathrm { i } } \alpha _ { \mathrm { j } } \cdot \mathrm { y _ { i } } \mathrm { y _ { j } } ( \mathbf { x _ { i } } \cdot \mathbf { y _ { i } } )
$$

$\alpha _ { \mathrm { i } } \geqslant 0$ 为与每个样本相对应的拉格朗日稀疏，即训练样本中仅有少数的拉格朗日系数 $\mathbf { a } _ { \mathrm { i } } ^ { * }$ 不为0，这样的样本定义为支持向量。

在最优分类面中采用适当的核函数就可以实现某一非线性变换后的线性分类，而计算的复杂度却没有增加。此时的目标函数公式(9)变为:

$$
\mathrm { Q } ( \alpha ) = \sum _ { \mathrm { i = 1 } } ^ { l } \alpha _ { \mathrm { i } } - \frac { 1 } { 2 } \sum _ { \mathrm { i , j = 1 } } ^ { l } \alpha _ { \mathrm { i } } \alpha _ { \mathrm { j } } \cdot \mathrm { y } _ { \mathrm { i } } \mathrm { y } _ { \mathrm { j } } \mathrm { K } ( \mathrm { x } _ { \mathrm { i } } , \mathrm { y } _ { \mathrm { i } } )
$$

最后训练后的相应的分类函数为：

# 14 现代图书情报技术

$$
\bf d ( \bf x ) = \sum _ { i = 1 } ^ { / } y _ { i } \bf d _ { i } \bf K ( \bf x _ { i } , \bf x ) + b ^ { * }
$$

即支持向量机，根据d(x)的符号来确定输入样本x 的归属。

# 3DAS文本分类模型

本文设计的结合DAE和SVM算法的中文新闻文本分类模型(简称DAS分类模型)，主要包括6个部分，即NLPIR文本分词、去除停用词、文本表示、DAE特征提取、SVM分类和分类效果评价，如图3所示：

NLPIR 去除停用 文本表示 DAE 分类  
文本 特征 SVM 效果  
分词 提取 分类 评价示词

(1）中文不同于西文，词与词之间没有明显的分割界限，因此需要对中文文本进行特殊的分词操作。本文采用比较成熟的NLPIR汉语分词系统[21]对中文新闻文本进行分词操作。

(2）经过步骤(1)分词后形成的词语有大量的停用词，包括标点符号和一些对分类不起作用的常见词等，本文收集多个停用词表后合并成一个较全面的停用词表，用来剔除这些停用词，得到能代表文本特征的候选特征词。

(3）经过步骤(2)得到的候选特征词依然很多，维数特别大，需要对其进行初步筛选，本文通过信息增益算法对文本特征进行初步筛选后，采用VSM模型进行文本的特征表示。

(4)将经过步骤(3)得到的特征表示输入一个由DAE构建的深度网络中，经过逐层训练后，得到一个维数比较低的特征编码。

(5）在深度网络的最后一层，用SVM算法对经过步骤(4)得到的特征编码进行分类输出，根据输出结果进行分类。

(6）对分类的效果进行评价，并根据评价结果不断地对此文本分类模型进行优化，直至得到满意的分类结果。

其中，文本分类中最基础最重要的工作是步骤(4)特征词的提取，而文本中存在大量的冗余数据和噪声，在提取特征词的时候容易导致误差的产生和识别度较差的问题，进而影响最终的分类效果。要想取得比较好的分类效果，需要将这些冗余数据或噪声的影响尽可能降低到最小。DAE将输入数据进行破坏处理后，利用这些破损数据训练出来的特征系数噪声比较小，并且破损数据在一定程度上能够减轻训练数据与测试数据的代沟。

因此，为了从文本中提取、编码出更加鲁棒的特征并消除噪声的影响，以取得较好的分类效果，本文借鉴相关理论[7,17-20],将 DAE 应用到中文新闻文本特征词的提取中，构建一个深度网络，逐层训练得到一个低维的特征编码，提取出最能代表文本的低维特征，实现高维文本数据的特征降维过程，并利用SVM算法在深度网络的最顶层对输出的低维编码进行分类输出，根据输出的结果实现最终的分类过程。基于DAE和SVM构建的深度网络如图4所示：

![](images/5de2d549adce57c1a04af78fff82bfd9bd4bac1dc608db43bfa906e4971ed077.jpg)  
图4分类训练过程

其中，文本候选词首先经过由多层DAE构成的隐层处理后，得到低维编码，在最顶层由LibSVM对低维编码进行分类输出，根据分类输出的结果进行微调，实现整个文本分类模型的训练过程。

# 4仿真实验

# 4.1 仿真实验步骤

(1）实验1:经典实验

为了测试本文DAS分类模型的优越性，在相同的数据集上，采用信息增益的特征选择方法选择出特征后，采用经典的训练算法，分别为KNN算法、SVM算法和只包含一层隐藏神经元的 BP神经网络算法，进行分类仿真实验，并将其分类召回率、准确率和F值与本文DAS分类模型进行比较。采用经典算法作对比仿真实验的具体步骤如下：

$\textcircled{1}$ 选择仿真实验数据集。仿真实验的新闻文本数据集[22]由复旦大学计算机信息与技术系李荣陆提供，数据集标注比较规范，规模适中，适合中小型的分类仿真实验。

此数据集中answer分组为测试语料，共9833篇文档，train分组为训练语料，共9804篇文档，分为20个类别。随机选取6个类别，每个类别1000篇，分别以200篇、400篇、600篇、800篇设置4组训练集，其中每组都以200篇作为测试集，分别进行训练。具体类别信息及实验分组设计如表1所示：

表1文本分类实验具体类别信息及分组设计  

<html><body><table><tr><td colspan="2">类别</td><td rowspan="2">类别名</td><td rowspan="2">训练集(4 组)</td><td rowspan="2">测试集</td></tr><tr><td>分组</td><td></td></tr><tr><td>C01</td><td>Computer</td><td></td><td>200、400、600、800</td><td>200</td></tr><tr><td>C02</td><td></td><td>Environment</td><td>200、400、600、800</td><td>200</td></tr><tr><td>C03</td><td></td><td>Agriculture</td><td>200、400、600、800</td><td>200</td></tr><tr><td>C04</td><td></td><td>Economy</td><td>200、400、600、800</td><td>200</td></tr><tr><td>C05</td><td>Politics</td><td></td><td>200、400、600、 800</td><td>200</td></tr><tr><td>C06</td><td>Sports</td><td></td><td>200、400、600、800</td><td>200</td></tr></table></body></html>

$\textcircled{2}$ 文本数据集的预处理包括文本分词和去除停用词。文本分词采用的NLPIR 汉语分词系统，其主要功能包括中文分词、词性标注、命名实体识别、用户词典功能、微博分词、新词发现与关键词提取等，是国内比较成熟、用户较多的中文文本分词系统。本文对文本语义特征进行分析，并综合网络上的停用词表，制作了一个比较全面的停用词表，如表 2所示：

表2停用词表  

<html><body><table><tr><td>标点符号</td><td>特殊符号</td><td>无意义词</td><td>数字</td><td>西文字符</td></tr><tr><td>。</td><td><</td><td>的</td><td>1</td><td>A(a)</td></tr><tr><td>、</td><td>></td><td>啊</td><td>2</td><td>B(b)</td></tr><tr><td>：</td><td>/</td><td>一个</td><td>3</td><td>C(c)</td></tr><tr><td>：</td><td>@</td><td>你</td><td>4</td><td>D(d)</td></tr><tr><td>，</td><td>~</td><td>本文</td><td>5</td><td>E(e)</td></tr><tr><td>…</td><td>…</td><td></td><td>…</td><td></td></tr></table></body></html>

$\textcircled{3}$ 文本表示。经过预处理后的文本维数过大，需要对其进行初步的降维处理，计算每个特征词的信息增益值，公式如下：

$$
\begin{array} { c } { { { \displaystyle { \bf I G } _ { \left( \mathrm { t } \right) } = - \sum _ { \mathrm { i = 1 } } ^ { \mathrm { m } } { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \right) } \log { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \right) } } + { \bf P } _ { \left( \mathrm { t } \right) } \sum _ { \mathrm { i = 1 } } ^ { \mathrm { m } } { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \mid \mathrm { t } \right) } \log { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \mid \mathrm { t } \right) } + } }  \\ { { { \displaystyle { \bf P } _ { \left( \overline { { { \mathrm { t } } } } \right) } \sum _ { \mathrm { i = 1 } } ^ { \mathrm { m } } { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \mid \overline { { { \mathrm { t } } } } \right) } \log { \bf P } _ { \left( \mathrm { c } _ { \mathrm { i } } \mid \overline { { { \mathrm { t } } } } \right) } } } } \end{array}
$$

其中， $\mathbf { m }$ 为总类别数, $\mathbf { c _ { i } }$ 代表类别， $\mathrm { P _ { ( c _ { i } ) } }$ 为类别 $\mathbf { c } _ { \mathrm { i } }$ 出现的概率； $\mathrm { { \bf ~ P } _ { ( t ) } }$ 为包含特征词的文档的概率， $\mathrm { P } _ { \mathrm { ( \overline { { \ t } } ) } }$ 为不包含特征词的文档的概率; $\mathrm { P } _ { \left( \mathrm { c } _ { \mathrm { i } } | \mathrm { t } \right) }$ 为包含特征t属于 $\mathbf { c } _ { \mathrm { i } }$ 的概率； $\mathrm { P } _ { ( \mathrm { c } _ { \mathrm { i } } | \overline { { \mathrm { t } } } ) }$ 为包含特征t但属于 $\mathbf { c } _ { \mathrm { { i } } }$ 的概率。

计算出信息增益值后，将其按大小排序并保留前5000个特征词用向量空间模型表示，如表3所示。

表3文本特征集的向量空间模型表示  

<html><body><table><tr><td colspan="2">特征词</td><td rowspan="2">t1</td><td rowspan="2"></td><td rowspan="2">tj</td><td rowspan="2"></td><td rowspan="2">tn</td></tr><tr><td>文本</td><td></td></tr><tr><td>d</td><td></td><td>W11</td><td></td><td>W1j</td><td>…</td><td>W1n</td></tr><tr><td></td><td>：</td><td>：</td><td></td><td></td><td>：</td><td>：</td></tr><tr><td></td><td>di</td><td>Wi1</td><td></td><td>Wij</td><td>：</td><td>Win</td></tr><tr><td></td><td>…</td><td>：</td><td></td><td></td><td>…</td><td>：</td></tr><tr><td></td><td>dm</td><td>Wml</td><td></td><td>Wmj</td><td>…</td><td>Wmn</td></tr></table></body></html>

在该特征词矩阵中，n表示所有文档中的特征词总数，每个特征词对应特征空间中的一维; $\mathrm { ~ m ~ }$ 代表所有待分类的文本数；将每个文档表示成 $\mathrm { ~  ~ N ~ }$ 维空间中的一点，如：$\mathrm { V ( d _ { i } ) } = ( ( \mathrm { t _ { 1 } , w _ { i l } ) , ( t _ { 2 } , w _ { i 2 } ) } , \cdots , ( \mathrm { t _ { k } , w _ { i k } ) } , \cdots , ( \mathrm { t _ { n } , w _ { i n } } ) )$ ，特征权重值 $\mathbf { W _ { i j } }$ 为每个特征词的 TF-IDF值，计算公式如下：

$$
\mathrm { W } _ { ( \mathrm { t } , \mathrm { d } ) } = \frac { \displaystyle \mathrm { t f } _ { ( \mathrm { t } , \mathrm { d } ) } \times \log ( \mathrm { N } / \mathrm { n } _ { \mathrm { t } } + \mathrm { a } ) } { \displaystyle \sqrt { \sum _ { \mathrm { t } \in \mathrm { d } } [ \mathrm { t f } _ { ( \mathrm { t } , \mathrm { d } ) } \times \log ( \mathrm { N } / \mathrm { n } _ { \mathrm { t } } + \mathrm { a } ) ] ^ { 2 } } }
$$

其中， $\mathrm { W } _ { ( \mathrm { t , d } ) }$ 为特征词 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 在文本d中的权重; $\mathrm { t f } _ { ( \mathrm { t , d ) } }$ 表示词条t在文档d中出现的频数; $ { \mathbf { n } } _ { \mathrm { t } }$ 为文本集中含有特征t的文本的数量； $\log ( \mathrm { N } / \mathrm { n } _ { \mathrm { t } } { + } \mathrm { a } )$ 为逆文本频率函数， $ { \mathbf { n } } _ { \mathrm { t } }$ 越大此值越小,a为一个常量，本文取0.01；分母是一个归一化因子。

$\textcircled{4}$ 分类训练。利用分类算法进行有监督的分类训练，得到分类参数，并用测试数据集进行分类测试。本文选择的算法分别为：KNN算法，此算法相对比较简单，用C语言自主设计的KNN算法;SVM算法，采用比较成熟的LibSVM进行分类实验;BP算法,MATLAB自带的成熟的神经网络工具箱。

$\textcircled{5}$ 分类效果评价与比较。采用召回率R(Recall)、准确率P(Precision)和F值对最终的分类结果进行评价。公式如下：

$$
\mathbf { R } = { \frac { \mathbf { M } } { \mathbf { M } + \mathrm { T } } }
$$

$$
\mathbf { P } = { \frac { \mathbf { M } } { \mathbf { M } + \mathbf { N } } }
$$

$$
\mathrm { F } = \frac { 2 \times \mathrm { R } \times \mathrm { P } } { \mathrm { R } + \mathrm { P } }
$$

其中，M为正确分类到该类的文本数，N为错分到该类中的文本数,T为属于该类却错分为别类的文本数。

# (2）实验2：优化实验

本文设计的DAS分类模型用于新闻文本分类的仿真实验的步骤 $\textcircled{1}$ -步骤 $\textcircled{3}$ 和步骤 $\textcircled{5}$ 都与经典实验完全相同，只有步骤 $\textcircled{4}$ 分类训练与经典实验步骤不同。

在本文设计的DAS分类模型中，将训练文本数据集经过步骤 $\textcircled{1}$ -步骤 $\textcircled{3}$ ，得到矩阵表示后，输入一个DAE构建的深度网络，用非监督学习方法对5000维的特征进行逐层的降维操作，并在最后一层采用线性分类器SVM算法对文本进行分类输出，根据输出结果调整训练过程中的各个参数，得到最终分类参数后利用测试数据集进行测试。

$\textcircled{1}$ 特征降维。将文本的向量化矩阵表示X先经过破坏处理得到矩阵X，然后将破坏后的矩阵X输入到编码器得到编码，再经过解码器重构得到一个重构矩阵，将重构矩阵与原始矩阵比较得到重构误差，调整编码器和解码器的参数使得重构误差最小，得到最终的编码。将上层中得到的编码特征作为下层的输入，采用相同的方法得到下层的编码，如此不断进行，得到规定数量层数的编码。

本文设计的深层次网络的节点数分别为5000-2500-1200-600-300-100-50-20，加上最终的线性分类器SVM共9层，先对每层的矩阵表示经过一个随机化置0的过程,再进行训练，每层训练结束后继续训练下一层，直到完成降噪自编码器的降维过程。

$\textcircled{2}$ 有监督微调。将步骤 $\textcircled{1}$ 得到的20 维的特征编码，应用SVM算法对其进行分类输出，然后根据输出的结果分类。再对各层的系数进行微调。此监督训练完成后，即用来对测试集的文本进行分类，以测试这个分类系统的有效性。

本文采用LibSVM算法对每个文本降维后获取到的特征编码进行分类，然后用BP算法从顶层向下进行各层系数的微调，最终取得调整后的系数，即可用来对测试数据集进行测试。

# 4.2 实验结果与分析

在4组训练集下分别进行实验，得出分类召回率、准确率与F值的情况如图5所示：

![](images/c6add9d1d7e76dcdfdcc0e07c6d97f6fbb814005a0f6953989445b87d0313251.jpg)  
图5分类召回率、准确率与F值随数据集变化的曲线图

可以看到，DAS分类模型随着训练集的增大，分类召回率、准确率和F值都在不断增大。这是由于深度网络对数据集的数量要求比较高，过小的数据集会导致产生过拟合现象从而导致分类效果欠佳。因此，针对深度网络，数据集的大小能够决定网络训练的效果，数据集越大，越能训练得到较好的分类效果。

经过与不同分类算法比较的仿真实验，得出4组实验下各算法的分类召回率、准确率和F值如表4至表6所示：

表4不同训练集下各算法的分类召回率 $( \% )$   

<html><body><table><tr><td colspan="2">算法</td><td rowspan="2">KNN</td><td rowspan="2">BP</td><td rowspan="2"> SVM</td><td rowspan="2">DAS</td></tr><tr><td>训练集</td><td></td></tr><tr><td></td><td>200</td><td>83.32</td><td>87.38</td><td>94.18</td><td>91.32</td></tr><tr><td></td><td>400</td><td>84.54</td><td>89.57</td><td>93.73</td><td>92.11</td></tr><tr><td>600</td><td></td><td>83.97</td><td>91.23</td><td>93.66</td><td>94.56</td></tr><tr><td>800</td><td></td><td>84.21</td><td>93.85</td><td>93.89</td><td>95.42</td></tr></table></body></html>

表5不同训练集下各算法的分类准确率 $( \% )$   

<html><body><table><tr><td>算法</td><td rowspan="2">KNN</td><td rowspan="2">BP</td><td rowspan="2"> SVM</td><td rowspan="2">DAS</td></tr><tr><td>训练集</td></tr><tr><td>200</td><td>87.68</td><td>90.32</td><td>93.01</td><td>93.28</td></tr><tr><td>400</td><td>88.72</td><td>90.34</td><td>94.71</td><td>94.21</td></tr><tr><td>600</td><td>86.35</td><td>92.15</td><td>93.78</td><td>95.34</td></tr><tr><td>800</td><td>85.78</td><td>94.24</td><td>94.59</td><td>96.79</td></tr></table></body></html>

表6不同训练集下各算法的分类F值 $( \% )$   

<html><body><table><tr><td>算法 训练集</td><td>KNN</td><td>BP</td><td> SVM</td><td>DAS</td></tr><tr><td>200</td><td>85.44</td><td>88.83</td><td>93.59</td><td>92.29</td></tr><tr><td>400</td><td>86.58</td><td>89.95</td><td>94.22</td><td>93.15</td></tr><tr><td>600</td><td>85.14</td><td>91.69</td><td>93.72</td><td>94.95</td></tr><tr><td>800</td><td>84.99</td><td>94.04</td><td>94.24</td><td>96.10</td></tr></table></body></html>

KNN算法在训练过程中，生成所有训练文本的特征向量，在测试过程中，比较测试文本的特征向量与所有训练文本特征向量的相似度，在中小型的分类实验中能够取得不错的效果。但是可以看到这种方法在很大程度上依赖于选出的特征词，如果选出的特征词代表性不强，分类效果会变得比较差，也可以看到，KNN算法取得的分类效果比其他算法差；BP算法是一种典型的浅层神经网络算法，能够反向传播误差，将误差分摊给各层单元，进而修正各单元的权值系数，完成训练过程。但是BP算法往往只设计三层的网络,在训练集比较少的情况下分类效果较差，随着训练集数目的增加，分类召回率、准确率和F值都有不同程度的增加；SVM算法的训练过程是要找到一个超平面，使得这个超平面的正反例分别落在两侧，在所有超平面中与正反例的距离最大且到最近的正反例的距离相等，然后对未知类别的文本，计算其位于超平面的一侧，即为其分属的类别，在对小规模样本的数据集的处理中颇占优势，但是对大样本数据集的分类效果略差，随着数据集的增大，分类效果并没有明显提升;DAS分类模型利用降噪自动编码器无监督地学习到新闻文本的特征编码，符合人脑以词-句-段-意的逐层分析方式对文本的理解，能够更精确地模拟人脑对文本所表达的意思的理解过程，因此能够取得更好的分类效果，从表4至表6也可以看出，本文的DAS分类模型分类效果更好。

# 5结语

深度学习已经在学术界、工业界掀起了研究热潮并取得了相当大的成果。本文借鉴DAE 和SVM的相关理论，设计DAS分类模型，将DAE构建的深度网络应用于中文新闻文本的特征降维过程中，并在深度网络的最顶层用SVM进行分类，根据分类的结果不断微调各层的系数，最终用测试数据集测试分类效果。结果表明，DAS分类模型降低了新闻文本数据中噪声的影响，分类效果比较好，能够取得比KNN、SVM和BP算法更好的分类效果。但是也看到，虽然设置了4组不同数据集的仿真实验，然而数据量依然比较小，并没有完全发挥深度学习并行处理大容量数据的优势，下一步的研究工作将集中在对大数据集的实验上。

# 参考文献：

[1]裴英博，刘晓霞．文本分类中改进型 CHI 特征选择方法的 研究[J]．计算机工程与应用，2011，47(4):128-130.(Pei Yingbo,Liu Xiaoxia.Study on Improved CHI for Feature Selection in Chinese Text Categorization [J].Computer Engineering and Applications,2011,47(4):128-130.)   
[2] 辛竹，周亚建．文本分类中互信息特征选择方法的研究与 算法改进[J].计算机应用,2013,33(S2):116-118,152.(Xin Zhu，Zhou Yajian. Study and Improvement of Mutual Information for Feature Selection in Text Categorization [J]. Journal of Computer Applications,2013,33(S2):116-118, 152.)   
[3] 郭颂，马飞．文本分类中信息增益特征选择算法的改进[J] 计算机应用与软件，2013，30(8):139-142.(Guo Song，Ma Fei.Improving the Algorithm of Information Gain Feature Selection in Text Classification [J].Computer Applications and Software,2013,30(8):139-142.)   
[4]Peters C,Koster C H.Uncertainty-based Noise Reduction and Term Selection in Text Categorization [C].In: Proceedings of the 24th BCS-IRSG European Colloquium on IR Research, Glasgow, UK. Springer, 2002: 248-267.   
[5]Lewis D D.Representation and Learning in Information Retrieval [D]. University of Massachusetts,1992.   
[6]李学相．改进的最大熵权值算法在文本分类中的应用[J]. 计算机科学,2012,39(6):210-212.(Li Xuexiang.Research of Text Categorization Based on Improved Maximum Entropy Algorithm [J]. Computer Science,2012,39(6): 210-212.)   
[7]Hinton G E, Salakhutdinov R R. Reducing the Dimensionality of Data with Neural Networks [J]. Science,2006,313(5786): 504-507.   
[8]Bengio Y, Lamblin P,Popovici D,et al. Greedy Layer-wise Training of Deep Networks [C]. In: Proceedings of the 20th Annual Conferenceon Neural Information Processing Systems,Vancouver,British Columbia,Canada.2007,19: 153.   
[9]Vincent P, Larochelle H, Bengio Y, et al. Extracting and Composing Robust Features with Denoising Autoencoders [C]. In: Proceedings of the 25th International Conference on Machine Learning. ACM,2008: 1096-1103.   
[10] Masci J,Meier U, Ciresan D,et al. Stacked Convolutional Auto-encoders for Hierarchical Feature Extraction [C]. In: Proceedings of the 2lstInternational Conference on Artificial Neural Networks. Springer Berlin Heidelberg,2011: 52-59.   
[11] 汪彩霞，魏雪云，王彪．基于堆栈降噪自动编码模型的动 态纹理分类方法[J]．现代电子技术，2015，38(6):20-24. (Wang Caixia,Wei Xueyun，Wang Biao.Dynamic Texture Clasification Method Based onStacked Denoising Autoencoding Model [J].Modern Electronics Technique, 2015,38(6): 20-24.)   
[12] Wu Z, Takaki S,Yamagishi J. Deep Denoising Auto-encoder for Statistical Speech Synthesis [OL]. arXiv: 1506.05268, 2015.   
[13] Li J， Struzik Z,Zhang L，et al.Feature Learning from IncompleteEEGwithDenoisingAutoencoder[J]. Neurocomputing,2015,165: 23-31.   
[14]胡帅，袁志勇，肖玲，等．基于改进的多层降噪自编码算 法临床分类诊断研究[J]．计算机应用研究，2015，32(5): 1417-1420.(Hu Shuai，Yuan Zhiyong，Xiao Ling，et al. Stacked Denoising AutoencodersApplied to Clinical Diagnose and Classification [J]. Application Research of Computers,2015,32(5): 1417-1420.)   
[15]刘勘，袁蕴英．基于自动编码器的短文本特征提取及聚类 研究[J]．北京大学学报：自然科学版,2015,51(2):282-288. (Liu Kan,Yuan Yunying. Short Texts Feature Extraction and Clustering Based on Auto-Encoder [J].Acta Scientiarum Naturalium Universitatis Pekinensis,2015,51(2):282-288.)   
[16]秦胜君，卢志平．基于降噪自动编码器的不平衡情感分类 研究[J]．科学技术与工程，2014，14(12):232-235.(Qin Shengjun,Lu Zhiping.Research of Unbalance Sentiment Classification Based on Denoising Autoencoders [J]. Science Technology and Engineering,2014,51(12):232-235.)   
[17]Bengio Y,Delalleau O.On the Expressive Power of Deep Architectures [C]. In: Proceedings of the 22nd International Conference on Algorithmic Learning Theory. Springer Berlin Heidelberg,2011:18-36.   
[18]Vincent P,Larochelle H,Bengio Y,et al.Extracting and Composing Robust Features with Denoising Autoencoders [C].In:Proceedings of the 25th International Conference on Machine Learning.ACM,2008:1096-1103.   
[19]Neural Networks and Deep Learning [EB/OL].[2015-12-23]. http://neuralnetworksanddeeplearning.com/chap3.html.   
[20]Vapnik V N.The Nature of Statistical Learning Theory[J]. IEEE Transactions on Neural Networks,1995，10(5): 988-999.   
[21]NLPIR 汉语分词系统[EB/OL].[2015-09-22].http://ictclas. nlpir.org/. (NLPIR Chinese Word Segmentation System [EB/OL].[2015-09-22]. http://ictclas.nlpir.org/.)   
[22]文本分类语料库(复旦)测试语料[EB/OL].[2015-12-24]. http://www.nlpir.org/?action-viewnews-itemid-1o3.(Text Categorization Corpus(Fudan）Test Corpus [EB/OL].[2015- 12-24].http://www.nlpir.org/?action-viewnews-itemid-103.)

# 作者贡献声明：

刘红光：提出研究思路，设计研究方案;  
马双刚：采集、清洗和分析数据，选择合适的算法进行实验;  
刘桂锋：验证实验可行性，整理实验数据，并对实验进行总结。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版 http://www.infotech.ac.cn。  
[1]刘红光，马双刚，刘桂锋．采用的实验数据集.rar.从文本分类语料库测试语料中选择的6个类别数据集.  
[2]刘红光，马双刚，刘桂锋．InfoGain.txt.由信息增益算法筛选出来的特征词.  
[3]刘红光，马双刚，刘桂锋.TF-IDF值.rar.计算出的各个文本的 TF-IDF 值.

[4]刘红光，马双刚，刘桂锋．分类结果集.xlsx．各个算法计算的分类结果.

# Classifying Chinese News Texts with Denoising Auto Encoder

Liu HongguangMa ShuanggangLiu Guifeng (Institute of Scientific & Technical Information, Jiangsu University, Zhenjiang 212013, China)

Abstract: [Objective]This paper proposes anew method to improve the clasification accuracyof the Chinese news texts with the help of Deep Learning theory.[Methods] We first used the denoising auto encoder to construct a deep network to learn the zipped and distributed representation of the Chinese news texts.Second,we used the SVM algorithm to clasify these news texts.[Results]As the number ofsamples expanding,the precisionrate,the recal rate and the F value of the proposed method increased too.The results are beter than those of the applications using the KNN,BP and SVM algorithms.The average precision rate was higher than $9 5 \%$ . [Limitations] The data size was relativelysmall,tus, te proposed method did not fullyutilize the parallel data processing capacityofthe deep learning technology.[Conclusions]The proposed method improves the performance of applications clasifying Chinese news texts.

Keywords:DAE SVM Feature selection Document classification

# 欢迎订阅2016年《现代图书情报技术》 (月刊)

《现代图书情报技术》杂志是由中国科学院文献情报中心主办的学术性、信息管理技术类专业期刊。1980 年创刊，原名《计算机与图书馆》,1985年更名为《现代图书情报技术》，是国内图书馆学、情报学领域唯一一份技术性刊物，连续多次被授予"中国图书馆学优秀期刊"荣誉称号。

期刊定位面向国内信息技术领域的科研人员，跨图书馆学、情报学、信息科学等几大学科，以报道信息技术的研发与应用为主体，倡导原创性科研论文，同时兼顾应用实践型文章。

月刊：国际通行16开版本  
国内邮发代号：82-421  
地址：北京中关村北四环西路33号(100190)  
E-mail: jishu@mail.las.ac.cn

定价：80元/期，全年定价：960元国外邮发代号：M4345电话/传真:010-82624938网址:http://www.infotech.ac.cn