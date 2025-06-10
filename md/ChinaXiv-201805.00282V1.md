# 一种结合空间特征的图像注意力标注算法改进研究

徐守坤¹′，周佳¹，李宁1,²，石林1

(1．常州大学 信息科学与工程学院 数理学院，江苏 常州 213164;2.福建省信息处理与智能控制重点实验室(闽江学院)，福州 350108)

摘要：针对图像标注和Attention机制结合过程中特征选择不充分和预测过程中对空间特征权重比例不足问题，提出了一种结合空间特征的注意力图像标注方法。首先通过卷积神经网络得到图像特征，特征区域与文本标注序列匹配；然后通过Atention 机制给标注词汇加权，结合空间特征提取损失函数得到基于空间特征注意力的图像标注；最后分别在 Flickr30k和COCO两个数据集上进行验证，通过可视化显示该模型如何自动学习显著区域并生成相应的词汇输出序列。实验结果表明，该方法能较好地提取注意力区域并给出标注，与其他模型对比能够得到更好的标注结果。

关键词：视觉注意力；图像标注；空间特征 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.08.0869

# Improved algorithm for image attention annotation combined with spatial features

Xu Shoukunl†, Zhou Jial,Li Ning1,², Shi Lin1 (1.SchoolofMathematics&Physics,choolofformationScience&Engineeing,ChangzhouUniversity,ChangzhouJangsu 213164,China;2.Fujian Provincial Key Laboratoryof Information Processingand Intellgent Control (Minjiang Colge), Fuzhou 350108,China)

Abstract: Aiming atthe problem ofisufficient feature selection and lackof spatial feature weight in the processof image annotationand Atentionmechanism,this paper proposedamethodofatentionimage annotationcombined with spatial feature. Firstly,itobtainedtheimagefeaturebyconvolutionneuralnetworkandmatchedthefeatureregionwiththetextlabelsequence. Then,itusedtheAtentionmechanismtoweightthannotationvocabularyandcombiningthespatialfeaturetoextractheloss function,theimageannotationbasedonthespatialfeatureatention.Finally,theFlickr3OkandCOCOvalidatedonthedataset to showhow the modelautomaticallylearns the salientregionsand generates thecorresponding vocabularyoutput sequences. The experimentalresults show that the methodcan extract theatentionareaand givethe annotation,andcompare withother models can get better labeling results.

Key Words:Visual attention; image annotation; spatial feature

# 0 引言

机器翻译中序列到序列、编码器解码器框架的成功应用[1]为图像标注领域提供更好的实现和使用。Kiros等人[2]提出一种多模态对数双线性模型前馈神经网络预测下一个标注词汇。Vinyals等人[3]使用LSTM代替RNN作为解码器，最后使用CNN全连接层输出图像标注。Karpathy等人[4]将物体检测结果从R-CNN和双向RNN 输出，得到标注排序和联合嵌入空间。近些年注意力机制被引入编码器解码器神经框架得到了更好的图像标注效果，注意力机制由机器翻译发展而来，将人类神经注意力因素考虑到对图像的标注中使得图像中的信息更好的被提取和标注。Xu等人[5]将注意力机制用于生成相应的图像对齐词汇，提出了基于LSTM模型的隐状态结合视觉注意力的模型。该模型也是目前发展比较成熟的基于注意力的图像标注模型。Yang等人[扩展当前注意力编码器解码器框架，加入验证网络，用向量捕捉全局属性加入解码器机制。You[7]和Wu等人[8]使用LSTM的输入或输出来处理语义几何图像视觉注意力属性的问题，也得到了不错的效果[9,10]。

本文方法主要通过卷积神经网络训练提取且对网络中的空间特征因子权重增加提取，使用Attention机制的LSTM模型作为编码器解码器，以注意力加权结合空间特征进行图像标注，得到基于空间特征注意力的图像标注结果，最后通过可视化展示注意力权重与图像标注结果及其分析。

# 1 相关概念

# 1.1Attention 编码器解码器

Attentionmodel（注意力模型）是一种模拟人脑注意力的模型，其核心为Encoder-Decoder 过程。Encoder-Decoder 模型是一种经典的自然语言处理模型，主要是通过Encoder模块对于输入序列进行编码得到编码之后的code，然后将code输入到Decoder模块进行解码，最后输出特定的序列。图1给出了Encoder-Decoder模型的一般框架。

![](images/888f9533d2c43b62addee7bb6324a1ccd248e70f587f4589f1873053561845a7.jpg)  
图1编码器解码器模型框架

Input一般是序列 $X = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . x _ { n } \}$ ，output是序列$Y = \{ y _ { 1 } , y _ { 2 } , y _ { 3 } , . . . y _ { _ m } \}$ 。在 Encoder 模块对输入序列进行编码，用$c$ 表示编码之后的code，表达公式为： $C = F ( x _ { _ 1 } , x _ { _ 2 } , x _ { _ 3 } , . . . x _ { _ n } )$ 。在Decoder模块对 $c$ 解码，计算输出 $y _ { _ i }$ 要用到 $c$ 和之前生成的$y _ { 1 } , y _ { 2 } , y _ { 3 } , . . . . y _ { i - 1 }$ ，计算公式为： $y _ { i } = G ( C , y _ { 1 } , y _ { 2 } , y _ { 3 } , . . . y _ { i - 1 } )$ 。由此可以看出在Decoder模块中计算输出 $y _ { i }$ 时，用到的语义信息都是一样的，对于较长序列的输入，由于语义编码code向量的维度限制，部分有效信息被丢失。

引入的AttentionModel机制原理在Decoder 阶段计算出输入序列 $x _ { _ 1 } , x _ { _ 2 } , x _ { _ 3 } , . . . . , x _ { _ n }$ 对于当前输出的 $y _ { i }$ 的注意力概率分布，对应唯一的语义编码信息，这种编码信息融合了输入对当前输出的注意力概率分布，可以优化当前的输出。加入AttentionModel的Encoder-Decoder模型的框架示意图如图2所示。

![](images/a9542e6e1f50284832cbab221e385e0956ee9d5d77854aa2bf003c4fb67db658.jpg)  
图2AM框架

从图2中可以看出，每个输出元素都有对应输入序列概率分布的语义编码 $c$ 。因此对于输出 $y _ { i }$ ，可以得到这样的计算公式； $y _ { i } = F ( C _ { i } , y _ { 1 } , y _ { 2 } , y _ { 3 } , \ldots y _ { i - 1 } )$ 。其中： $C _ { _ i }$ 是对输入序列$x _ { _ 1 } , x _ { _ 2 } , x _ { _ 3 } , . . . , x _ { _ n }$ 在编码阶段进行非线性函数转换得到；对于输入$x _ { i } , S ( { \boldsymbol { x _ { i } } } )$ 表示在编码阶段经过函数处理之后的值。编码阶段得到输入序列对应状态值，然后计算出状态值对于输出 $y _ { i }$ 的注意力概率分布。再根据注意力概率分布计算出对应 $C _ { _ i }$ 。计算公式为： $C _ { i } = \sum _ { j = 1 } ^ { T } \alpha _ { i j } S ( x _ { j } )$ 。其中： $\alpha _ { _ { i j } }$ 是输入 $\boldsymbol { x } _ { j }$ 对输出 $y _ { i }$ 的注意力概率； $T$ 为输入序列的元素的数目。这样设计的原理是计算出$x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . x _ { _ T }$ 对总体的影响力权重，可以突出关键词的作用，减少非关键词对于整体语义的影响。

将Attention机制加入Encoder-Decoder有两个计算过程分别为计算注意力概率分布下的语义编码及特征向量。具体计算步骤如下：

a)计算注意力分布概率的语义编码，主要思想是计算历史节点和最后输入节点的关系分数，然后计算占总体分数的比重，通过以下公式得到了每一个输入对于最后输入的注意力概率。计算公式如下：

$$
a _ { _ { k i } } = { \frac { \exp ( e _ { _ { k i } } ^ { } ) } { \sum _ { j = 1 } ^ { T } e x p ( e _ { _ { k j } } ^ { } ) } }
$$

$$
e _ { _ { k i } } = \nu \operatorname { t a n h } ( W h _ { _ { k } } + U h _ { _ { i } } + b )
$$

其中： $a _ { \scriptscriptstyle { k i } }$ 表示节点 $i$ 对于节点 $K$ 的注意力概率权重； ${ \mathbf { \Omega } } _ { \nu , W , U }$ 为权重矩阵； $h _ { \scriptscriptstyle k }$ 为最后输入对应的隐藏层状态； $h _ { _ i }$ 表示输入序列第 $i$ 个元素对应的隐藏层的状态值。

b)计算注意力分布概率的语义编码和特征向量。其中语义编码 $c$ 主要是通过注意力概率权重与历史输入节点的隐藏层状态乘积的累加得到。最终的语义编码是将含有历史节点的注意力概率分布的语义编码和文章总体向量作为传统LSTM模块的输入，最后节点的隐藏层状态值 $H _ { \nu ^ { \prime } }$ 就是最终的特征向量。该特征向量，包含了历史输入节点的权重信息，突出了关键词的语义信息[]表。计算公式如下:

$$
C = \sum _ { i = 1 } ^ { r } a _ { { \scriptscriptstyle k i } } h _ { { \scriptscriptstyle i } }
$$

$$
H _ { \mathrm { \Omega } _ { k ^ { \prime } } } = H ( C , h _ { \mathrm { \Omega } _ { k } } , X ^ { \prime } )
$$

# 1.2 空间特征

一般地，用卷积神经网络来抽取图像特征，通过多个串行的卷积层(convolutionlayer)和池化层(poolinglayer)间隔排列的方式逐层学习图像数据特征。采用卷积操作方式利用小于图像尺寸卷积核扫描整个图像并计算卷积核与图像局部位置权重之和。每个卷积都对应一个特征映射，随后被输入到池化层进行空域上子抽样(subsample)，使得卷积神经网络具有一定抗畸变能力。网络最顶层将所有得到的特征映射重新拉成一维向量并结合多分类回归分类器反向传播错误信号来调整网络参数。

空间特征是静态图像中物体目标的空间判断能力的重要部分。图像数据的重要特性即数据在空域(两维)和时域(一维)上都存在着明显的统计相关性。在图像标注领域中大多是使用全特征提取，目前全特征提取存在明显缺陷即数据进入网络拉成一维向量形式。这破坏了空域和时域上的相对位置关系，可能会引起相关信息丢失，会产生图像中目标空间方位判断失误，抽取的特征可能引入了其他无关信息。

通过计算两帧之间的逐元素乘积来抽取时域特征，使用多个并行卷积层抽取特征，再计算这些特征的两两逐元素乘。这种神经元间的乘法交互(multiplicative interactions)模型可以显性地学习到时域动态空间特征，同时保留了卷积神经网络在处理空域特征上的优势[12]。

# 2 模型构建

# 2.1基于Attention 的编码器解码器整体架构

图3所示基于注意力机制的循环网络编码解码整体架构。首先分析和表示图像提取视觉特征的多个视觉区域，然后采用视觉特征经AttenionLSTM结构即加入了Attention机制编码器解码器的LSTM网络来预测不同区域的序列，最后得到基于视觉注意力的标注词语生成序列。该模型可以看成是对高维原始输入数据编码之后再解码成低维抽象特征的过程，通过编码器一解码器框架处理各模块之间的关联[16]。

![](images/172cca443c1cc28caab03a56a74e19c8db9341e5263da7c4e29645038dd24e3c.jpg)  
图3模型架构

# 2.2编码器：卷积特征

模型获取单个原始图像并生成标注编码为 $1 { \sim } K$ 的编码单词序列。

$$
y = \left\{ y _ { 1 } , . . . , y _ { C } \right\} , y _ { i } \in \mathbb { R } ^ { K }
$$

其中： $K$ 是词汇表大小， $c$ 是标签长度。使用CNN提取作为特征向量的注释向量 $a$ ，提取器产生 $L$ 个向量，对应图像的不同空间位置特征用 $D$ 维向量来表示。

$$
a = \left\{ a _ { 1 } , . . . , a _ { \scriptscriptstyle L } \right\} , a _ { \scriptscriptstyle i } \in \mathbb { R } ^ { D }
$$

为了获得特征向量和部分图像对应关系，将逐层卷积得到的特征图直接通过全连接层输入到包含512个神经单元的下一隐藏层。这使得解码器选择性地聚焦于图像的某些部分，并且加权所有特征向量子集[17,18]。

# 2.3 解码器：AttentionLSTM网络

将视觉注意力机制引入到网络中，使得每个时刻可以自适应地将注意力集中于当前画面中面积相对较小但具有丰富信息的图像区域，从而加快模型解码速度。使用LSTM网络做解码器：

$$
i _ { \iota } = \sigma ( W _ { i } E y _ { \iota - 1 } + U _ { i } h _ { \iota - 1 } + Z _ { i } \mathcal { Z } _ { t } + b _ { i } )
$$

$$
f _ { \scriptscriptstyle t } = \sigma ( W _ { \scriptscriptstyle f } E y _ { { } _ { t - 1 } } + U _ { \scriptscriptstyle f } h _ { { } _ { t - 1 } } + Z _ { \scriptscriptstyle f } \ z _ { { } _ { t } } + b _ { \scriptscriptstyle f } )
$$

$$
c _ { { t } } = f _ { { t } } c _ { { t } - 1 } + i \operatorname { t a n h } ( W _ { { c } } E y _ { { t } - 1 } + U _ { { c } } h _ { { t } - 1 } + Z _ { { c } } z _ { { t } } + b _ { { c } } )
$$

$$
o _ { t } = \sigma ( W _ { o } E y _ { t - 1 } + U _ { o } h _ { t - 1 } + Z _ { o } \zeta _ { t } + b _ { o } )
$$

$$
h _ { \mathrm { { } } _ { t } } = o _ { \mathrm { { } } _ { t } } { \operatorname { t a n h } } ( c _ { \mathrm { { } } _ { t } } )
$$

其中 $i _ { \scriptscriptstyle t } , f _ { \scriptscriptstyle t } , c _ { \scriptscriptstyle t } , o _ { \scriptscriptstyle t } , h _ { \scriptscriptstyle t }$ 分别是LSTM的输入门、遗忘门、记忆单元、输出门和隐层状态表示； $W , \boldsymbol { U } , \boldsymbol { Z } , \boldsymbol { b }$ 是权重矩阵和偏差；$\mathbf { E } \in \Re ^ { m \times K }$ 是嵌入矩阵； $\sigma$ 是 sigmoid 函数；上下文向量$z _ { \ i } = \sum _ { i = 1 } ^ { L } \alpha _ { \ i i } a _ { \ i }$ 是一个动态向量表示在 $t$ 时刻相关部分图像的特征， $\alpha _ { _ { u i } }$ 表示在时刻 $t$ 中视觉向量 $a _ { _ i }$ 加权，定义如式(8)所示[20]。LSTM通过平均注释向量来初始化存储状态和隐藏状态，通过两个分类的MLPs得到，如(9)所示。

$$
\alpha _ { _ i i } = \frac { \exp ( e _ { _ i i } ^ { } ) } { \sum _ { \scriptscriptstyle k = 1 } ^ { \scriptscriptstyle L } \exp ( e _ { _ { t k } } ^ { } ) } \qquad e _ { _ i i } ^ { _ { a } } = f _ { _ { a t m } } ( a _ { _ i } , h _ { _ { t - 1 } } ^ { } )
$$

$$
c _ { \scriptscriptstyle 0 } = f _ { { \scriptscriptstyle i n i t } , c } ( \frac { 1 } { L } \sum _ { i } ^ { L } a _ { \scriptscriptstyle i } ) ~ h _ { \scriptscriptstyle 0 } = f _ { { \scriptscriptstyle i n i t } , h } ( \frac { 1 } { L } \sum _ { i } ^ { L } a _ { \scriptscriptstyle i } )
$$

$f _ { a m } ( a _ { i } , h _ { r - 1 } )$ 是注意力函数，在隐层状态 $h _ { { \scriptscriptstyle t - 1 } }$ 下决定分配给图像特征 $a _ { _ i }$ 的注意力数量，其中 $\textstyle \sum _ { i = 1 } ^ { L } { \alpha _ { _ { t i } } } = 1$ 。输出词汇的概率由图像上下文向量 $\boldsymbol { z } _ { t }$ 、前一时刻的词汇 $y _ { { } _ { t - 1 } }$ 和隐层状态 $h _ { \scriptscriptstyle t }$ 共同决定，如式(10)所示， $G$ 是学习参数。除此对应有损失函数 $L$ ，对词汇 $w = \left\{ w _ { _ 1 } , . . . , w _ { _ C } \right\}$ 的负采样对数概率，如式(11)所示。

$$
p ( y _ { \iota } \vert a , y _ { \iota - 1 } ) \propto \exp ( G _ { o } ( E y _ { \iota - 1 } + G _ { h } h _ { \iota } + G _ { z } z _ { \iota } ) )
$$

$$
L _ { _ { t , c a p } } = - \log p ( w _ { _ t } | a , y _ { _ { t - 1 } } )
$$

兴趣注意力通过模型 $\alpha _ { _ t } = \left\{ \alpha _ { _ { t i } } \right\} _ { _ { i = 1 , . . , L } }$ 生成。具体来说，正例验证标注的注意力图 $\beta _ { \mathrm { r } } = \{ \beta _ { \mathrm { r } i } \} _ { i = 1 , \dots , L }$ 由正例验证标注给出且$\sum _ { i = 1 } ^ { L } \beta _ { i i } = 1$ 。一旦 $\sum _ { i = 1 } ^ { L } \beta _ { _ i i } = \sum _ { i = 1 } ^ { L } \alpha _ { _ i i } = 1$ ，可以认为是两个注意力概率分布，一般被用在交叉损失熵中验证。对于那些没有与图像区域对齐的单词（如“of”，“is”），设置 $L _ { \phantom { t r a t t { n } } }$ 为0：

$$
\begin{array}{c} L _ { _ { t , a t t n } } = \{ { \displaystyle - \sum _ { 0 } } ^ { \cal L _ { _ { i = 1 } } ^ { \cal L } \beta _ { _ { i i } } \log \alpha _ { _ { i i } } } \quad \beta _ { _ { t } } \exists w _ { _ { t } }  \\ { 0 \qquad \quad \quad \quad \quad o t h e r w i s e } \end{array}
$$

故而总损失变成两个损失项的加权和：

$$
L = \sum _ { t = 1 } ^ { c } L _ { _ { t , c a p } } + \lambda \sum _ { t = 1 } ^ { c } L _ { _ { t , a m } }
$$

# 2.4 空间驱动注意力

空间因素[]是图像注意力中比较重要的因素，如本文1.2节所阐述之原因，故本文将空间特征因素加入注意力模型，从而更好的得到图像标注与生成。CNN最后一层ResNet尺寸为$2 0 4 8 \times 7 \times 7$ ， $A = \left\{ a _ { 1 } , . . . , a _ { \scriptscriptstyle k } \right\}$ ， $a _ { i } \in R ^ { 2 0 4 8 }$ 代表全连接层空间卷积特征， $k$ 表示其每个栅格位置，故全局图像特征表示为

$$
a ^ { g } = \frac { 1 } { k } \sum _ { i = 1 } ^ { k } a _ { i }
$$

其中： $a ^ { \mathrm { { } ^ { g } } }$ 表示全局图像特征。使用单层感知机和激活函数调整图像特征向量， $W _ { a }$ 和 $W _ { _ b }$ 是权重参数，得到新的特征向量：

$$
\begin{array} { l } { { \nu _ { i } \ = \mathrm { R e } L U ( W _ { a } a _ { i } ) } } \\ { { \nu ^ { g } = \mathrm { R e } L U ( W _ { b } a ^ { g } ) } } \end{array}
$$

图像空间特征最终为 $V = \left[ \nu _ { 1 } , . . . , \nu _ { k } \right] \nu _ { i } \in \Re ^ { d }$ ，每个都用 $d$ 维表示其对应图像部分，故空间注意模型计算LSTM的上下文向量 $\boldsymbol { c } _ { t }$ 公式为

$$
c _ { \scriptscriptstyle t } = f ( V , h _ { \scriptscriptstyle t } )
$$

其中： $f$ 是注意力函数，空间图像特征 $V \in \Re ^ { d \times k }$ 和LSTM隐层状态 $h _ { { \mathrm { { \ell } } } _ { t } } \in \Re ^ { d }$ ，经过单层神经网络由softmax 函数在图像上得到

包含注意力分布的 $k$ 个区域的空间特征图像：

$$
\boldsymbol { z } _ { t } = \boldsymbol { w } _ { h } ^ { T } \operatorname { t a n h } ( \boldsymbol { W } _ { \nu } \boldsymbol { V } + ( \boldsymbol { W } _ { g } \boldsymbol { h } _ { t } ) \boldsymbol { 1 } ^ { r } )
$$

$$
\alpha _ { \iota } = s o f t \operatorname* { m a x } ( z _ { \iota } )
$$

$1 \in \Re ^ { k }$ 是所有元素置为1的向量， $W _ { \nu } , W _ { g } \in \mathfrak { R } ^ { k \times d } w _ { h } \in \mathfrak { R } ^ { k }$ 是学习参数， $\alpha \in \Re ^ { k }$ 是在 $V$ 中特征注意力权重。基于注意力分布，上下文向量 $c _ { _ { t } }$ 可以如下表示：

$$
c _ { _ t } = \sum _ { i = 1 } ^ { k } \alpha _ { _ n } \nu _ { _ { t i } } a _ { _ n }
$$

$c _ { _ t }$ 和 $h _ { _ t }$ 的组合被用来预测下一个词汇 $y _ { { t + 1 } }$ 。用当前的隐藏状态 $h _ { \scriptscriptstyle t }$ 分析注意哪里，结合两种信息源预测下一个词汇。生成上下文向量 $\boldsymbol { c } _ { t }$ 可作为当前隐层状态 $h _ { \scriptscriptstyle t }$ 的视觉残差信息，从而减少当前隐层状态预测下一词汇的不确定性。

# 3 实验及结果分析

# 3.1实验设置及评价指标

使用Flickr30k和COCO两大开源数据集来进行本文实验。Flickr30k包含Flickr收集的31783张图片，图像大多描述了人类日常活动都已被人工标注，每个图像对应五句标注描述。COCO是目前使用最多的图像标注数据集，包含82783、40504、40 775幅图像，分别用于训练、验证、测试。因全部图像训练时间过长，所以随机抽取其中一部分融合起来作为实验数据集。将数据集分为三部分：4000幅的训练图像、500幅的验证图像以及500幅测试图像，同样每个图像对应有五句人工标注。验证图像主要用于确定模型参数，待参数确定后，验证集里所有图像放入训练集中[21,22]。实验平台为 HP 台式机，硬件配置为$3 . 2 \mathrm { G H z }$ 的Inteli5CPU、4.0GB内存，操作系统为Ubuntu14.0，软件环境为MATLAB2014a及python2.7。图像标注生成常用的评价指标为BLEU[25]值，本实验依此进行评价，除BLEU之外，另一种常见评价指标METEOR[23]和CIDEr[24]。评估Flickr30k 和 COCO，与现有的 MSM[26]，Hard-Attention[5]以及DeepVS[4]进行部分比较。

# 3.2 实验结果分析

所有实验情况参数设置等细节严格遵守 $\mathrm { \Delta X u }$ 等人[5]的模型。本文调整图像的大小短边为256像素，中心区域裁剪成 $2 2 4 \times$ 224像素。预训练ImageNet之后提取VGG19 网络中conv5_4特征，顶层卷积层尺寸为 $1 4 \times 1 4 .$ 。为了可视化注意力模型权重，上采样权重因子为 $2 ^ { 4 } { = } 1 6$ ，使用高斯滤波器模拟感受野大小。设置CNN卷积迭代次数为15000次，训练文本向量矩阵迭代次数为15000 次；为了避免过度拟合，设置CNN的权重下降速率为 $1 0 ^ { - 3 }$ 。LSTM语言模型的学习率为 $4 \times 1 0 ^ { - 4 }$ ；设置更新权重参数为 $\alpha = 0 . 8$ 、 ${ \beta = } 0 . 9 9 9$ 。进行随机梯度下降非正则化训练，为数据源Flickr30k设置1300个LSTM单元，COCO数据集为1800个。

在Caffe 框架下使用Zhang等人[26]提供的开源代码训练程序得到的效果如图4所示。基于注意力模型的图像语义生成标注正样例，在图中重点注意力在于三个人的特征注意，颜色越深的地方表示注意力权重越深，故而“man”和“boy”等词汇权重较其他来说略高一些。两两人物关系因加入空间特征，故而在同时注意区域推测可能为夫妻关系；男性注意力在男孩身上，故而推测为父亲，推测的标注词汇来源于训练集中的现有语句词汇逻辑预测成果。

![](images/1de94ff354232823920e27dfb8a1a6b01321e70b91344eb8368b3d81955f2909.jpg)  
图4实验正例

图5为实验结果对比。加入了空间因素，可以看出对于注意力权重和空间判断有了矫正。图5展示在同一个交通标志在三种现有模型下的注意力对比。对于STOP标志的注意力权重比HardAttention模型范围测距小，因加入的空间特征对无关特征去除及加深相关特征权重的缘故，所以比起DeepVS 是全特征识别更为典型的代表，对于颜色空间过度识别。

![](images/9654ca57019acfffe0f1902b2cc885e67c214ec609658f6c308c1320e6e75ddf.jpg)  
图5实验比较

进一步将标注生成对应空间注意力关系可视化对应如图6所示。非注意力词汇例如“of”对其进行注意力关注提升，因为冠词之后很有可能给出重点名词，如同“riding”“elephant”之类词汇分配注意概率占重比非注意力词汇大。上下文场景环境不同时，同词汇分配的视觉注意概率度也是不同的。例如词汇“a”通常在文章的开始具有较高标注概率，因无背景上下文需要LSTM保存信息再判断。

![](images/f02a13147dd36644a92a9edc128458bcdd739d02641043adf913b9fac94db7ca.jpg)  
图6词汇生成过程

表1注意力模型比较/%  

<html><body><table><tr><td rowspan="2">模型</td><td colspan="6">Flickr30k</td><td colspan="6">MS-COCO</td><td colspan="3">平均正确率</td></tr><tr><td>B-1</td><td>B-2</td><td>B-3</td><td>B-4</td><td>M</td><td>C</td><td>B-1</td><td>B-2</td><td>B-3</td><td>B-4</td><td>M</td><td>C</td><td>Flickr30k</td><td></td><td>MS-COCO</td></tr><tr><td>DeepVS</td><td>0.572</td><td>0.367</td><td>0.241</td><td>0.158</td><td>0.154</td><td>0.248</td><td>0.628</td><td>0.451</td><td></td><td>0.322</td><td>0.231</td><td>0.198</td><td>0.678</td><td>0.627</td><td>0.911</td></tr><tr><td>Hard- Attention</td><td>0.668</td><td>0.438</td><td>0.286</td><td>0.189</td><td>0.187</td><td></td><td>0.185</td><td>0.719</td><td>0.547</td><td>0.358</td><td>0.251</td><td>0.231</td><td></td><td>0.643</td><td>0.906</td></tr><tr><td>MSM</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td><td></td><td></td><td>0.725</td><td>0.561</td><td>0.423</td><td>0.326</td><td>0.250</td><td>0.987</td><td>0.551</td><td>0.923</td></tr><tr><td>Ours</td><td>0.671</td><td>0.442</td><td>0.257</td><td>0.190</td><td>0.194</td><td>0.255</td><td></td><td>0.731</td><td>0.570</td><td>0.334</td><td>0.331</td><td>0.257</td><td>0.990</td><td>0.657</td><td>0.925</td></tr></table></body></html>

如表1所示的结果，对Flickr30k和COCO的数据集，使用M表示METEOR指标，用C表示CIDEr指标，使用Ours代表本文实验。与没有加入空间特征注意力模型的算法进行比较，本文融入空间注意力模型局部性能上稍优于其他注意模型。在Flickr30k 数据集上，CIDEr得分值从0.248 提高至0.255；在COCO数据集上为从0.987提升至0.990。在COCO数据集中，本文方法BLEU-4得分从0.326提高到0.331，METEOR从0.250到0.257。标注模型所BLEU指标相比基线有所提升。模型在Flickr30kBLEU-1 评分提升 $( 0 . 6 7 1 { - } 0 . 6 6 8 ) / 0 . 6 6 8 \approx 0 . 4 \%$ COCOBLEU-2评分提升 $( 0 . 5 7 0 { - } 0 . 5 4 7 ) / 0 . 5 4 7 \approx 4 . 2 \%$ ，从表1可以看出，在准确率方面本文方法有较好的标注效果，在Flickr30k数据集下，经过训练和随机局部结果抽样比对提升了$1 9 . 2 \%$ ；MS-COCO数据集下提升有 $2 . 1 \%$ 。

对上述模型计算复杂度比较，本文将各模型在两大数据集中随机抽样测试1000张，长度为20个字符以内的单张图像对平均标注时间进行比较，结果如表2所示。在表2中，本文算法运行所需时间相比其他模型运行时间增加的幅度在$0 . 0 3 9 { \sim } 0 . 3 2 0 \mathrm { ~ s ~ }$ ，在Flickr30k数据上相对增量为 $0 . 1 1 \%$ ，在MS-COCO上为 $0 . 0 2 \%$ ，整体平均增量为 $0 . 0 7 \%$ ，尚未达到 $1 \%$ ，可见本文算法复杂度的增加在可承受的范围内。综合评分指标，模型的整体基于空间注意力融合标注局部性能上较优，它具备一定实用价值。

表2数据集上平均运行时间/s/张  

<html><body><table><tr><td>模型</td><td>DeepVS</td><td>Hard-Attention</td><td>MSM</td><td>Ours</td></tr><tr><td>Flickr30k</td><td>2.039</td><td>2.217</td><td>2.864</td><td>2.359</td></tr><tr><td>MS-COCO</td><td>4.483</td><td>4.334</td><td>5.847</td><td>4.522</td></tr></table></body></html>

# 4 结束语

本文在以前工作的基础上提出了一种有效针对图像的视觉融入空间特征注意力模型，能够很好地描述图像中吸引注意力区域的情况。首先通过卷积神经网络得到图像特征，特征图像区域标注匹配，使用Attention机制的LSTM模型作为编码器解码器，以注意力加权结合空间特征进行图像标注，最终得到基于空间特征注意力的图像标注生成结果。实验结果表明，与相关方法相比，本文所提出的算法在标注性能上取得了一定的效果，但是从整体评估和独创性方面来看还需要很多的改进工作。

# 参考文献：

[1]Bahdanau D,Cho K,Bengio Y.Neural machine translation by jointly learning to align and translate [J]. Computer Science,2014,40 (12): 4751- 4759.   
[2]Kiros R, Salakhutdinov R, Zemel R. Multimodal neural language models [C]// Proc of International Conference on Learning Representations. 2014: II-595.   
[3]Vinyals O,ToshevA,Bengio S,et al. Show and tell a neural image caption generator[J].Computer Science,2015,36(7):3156-3164.   
[4]Karpathy A, LiFF. Deep visual-semantic alignments for generating image descriptions [J]. IEEE Trans on Pattrn Analysis & Machine Intelligence, 2014, 39 (4): 664-676.   
[5]Xu K,Ba J,Kiros R,et al. Show,attend and tell neural image caption generation with visual attention[J]. Computer Science,2015,58 (12):2048- 2057.   
[6]Yang Z, Yuan Y,Wu Y, et al. Review networks for caption generation [C]// Advances in Neural Information Processing Systems.2016: 2361-2369.   
[7]You Q, Jin H,Wang Z,et al. Image captioning with semantic attention [J]. Computer Science,2016,42 (13): 4651-4659.   
[8]Wu Q, Shen C,Liu L,et al. What value do explicit high level concepts have in vision to language problems?[J]. Computer Science,2016,12 (01): 1640- 1649.   
[9]Lu J, Xiong C,Parikh D,et al. Knowing when to look: adaptive attention via a visual sentinel for image captioning [J]. International Journal of Computer Vision,2016,115 (3): 211-252.   
[10] Zhou L,Xu C, Koch P, et al. Watch what you just said: image captioning with text-conditional attention [J]. IEEE Trans on Image Processing,2016, 25 (8): 3919-3930.   
[11]张冲．基于Attention-BasedLSTM模型的文本分类技术的研究[D]．南 京：南京大学,2016.   
[12]杨格兰，邓晓军，刘琮．基于深度时空域卷积神经网络的表情识别模型 [J]．中南大学学报：自然科学版,2016,47(7):2311-2319.   
[13]李静．基于多特征的图像标注研究[D].武汉：武汉理工大学,2013.   
[14]滕飞，郑超美，李文．基于长短期记忆多维主题情感倾向性分析模型 [J]．计算机应用,2016,36(8):2252-2256.   
[15] 刘杰.ISTM神经网络在 Android 平台上的实现.[Dl.天津：南开大学.

2015.   
[16]Fu Kun,Jin Junqi,Cui Renpeng,et al.Aligning where to see and what to tell:image captioning with region-based Attention and scene-specific contexts[J].IEEE Trans on Pattern Analysis&Machine Intelligence,2015, 39 (12): 2321-2334.   
[17] Cho K,Merrienboer B V, Gulcehre C,et al.Learning phrase representations using RNN encoder-decoder for statistical machine translation [J]. Computer Science,2014,45 (18):4913-4921.   
[18] Sutskever I, Vinyals O,Le QV. Sequence to sequence learning with neural networks [J].Advances in Neural Information Processing Systems,2014,4 (3):3104-3112.   
[19] Mao J,Xu W, Yang Y,et al.Deep Captioning with multimodal recurrent neural networks (m-RNN) [C]// Proc of International Conference on Learning Representations.2015: I1-301.   
[20] Liu C,Mao J, Sha F,et al.Attention correctness in neural image captioning [C]// Proc of AAAI -the Association for the Advance of Artificial Intelligence.2017: 4176-4182.   
[21]柯逍，李绍滋，曹冬林．基于相关视觉关键词的图像自动标注方法研究 [J]．计算机研究与发展,2012,49(4):846-855.   
[22]Denkowski M,Lavie A.Meteor universal: language specific translation evaluation for any target language [C]//Proc of Workshop on Statistical Machine Translation.2014:376-380.   
[23] Vedantam R,Zitnick C L,Parikh D.CIDEr:consensus-based image description evaluation [J]. Computer Science,2014,9(4): 4566-4575.   
[24] Papineni K,Roukos S,Ward T,et al.BLEU:a method for automatic evaluation of machine translation[C]//Proc ofMeeting on Association for Computational Linguistics.2002:311-318.   
[25] Yao T,PanY,LiY,etal.Boosting image captioning with attributes[J].ACM Trans on Graphics,2016,27(3):1423-1436.   
[26] Zhang J,Lin Z,Brandt J,et al.Top-down neural attention by excitation backprop [C]//Proc of European Conference on Computer Vision.[S.1.] : Springer International Publishing,2016: 543-559.