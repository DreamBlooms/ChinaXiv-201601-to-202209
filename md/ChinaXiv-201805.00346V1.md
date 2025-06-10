# MBDH:一种多尺度平衡深度哈希图像检索方法

张艺超1，黄樟灿1，陈亚雄2,3

(1．武汉理工大学 理学院 数学系，武汉 430070;2.中国科学院西安光学精密仪器研究所，西安 710048;3．中国科学院大学，北京 100049)

摘要：哈希由于其在存储和检索效率方面的优势已经被广泛用于大规模多媒体检索。通过利用数据的语义相似度来提高哈希编码质量的监督哈希近来受到更广泛关注。传统监督哈希方法将图像学习的手工特征或机器学习特征和二进制码的单独量化步骤分开，并未很好地控制量化误差，并且不能保证生成哈希码的平衡性。为了解决这个问题，提出了新的多尺度平衡深度哈希的方法。该方法采用多尺度输入，这样做有效地提升了网络对图像特征的学习效果。并且提出了新的损失函数，在很好地保留语义相似性的前提下，考虑了量化误差以及哈希码平衡性，以生成更优质的哈希码。该方法在CIFAR-10以及Flickr数据集上的最佳检索结果较当今先进方法分别提高了 $5 . 5 \%$ 和 $3 . 1 \%$ 检索精度。

关键词：多尺度；平衡性；深度哈希；卷积神经网络；图像检索中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.10.0962

# MBDH: a multi-scale balanced deep hashing method for image retrieval

Zhang Yichao1, Huang Zhangcan1, Chen Yaxiong² (1.DeptofMathematics,hoolofiene,WuhnUniversityofchnlogyWuhan4300hna;2.XianIstituteOtic &Precision Mechanics,ChineseAcademyofSciences,Xian71o48,China;3.UniversityofChineseAcademyofSciences, Beijing 100049, China)

Abstract: Hashing hasbeen widelyusedforlarge-scale multimedia retrievalbecauseofitsadvantagesofstorageandretrieval efciency.The useof the semantic similarity improving the hash coding quality has recently been more widely concerned. Traditional supervised hash methods for image retrieval represent an image as a manual feature vector or a machine learning feature vector,and then perform a separatequantization step to generate a binarycode.Such methods do notcontrol the quantization errorefectively,andcannotguarante thebalanceofhashcode.Tothis end,this paperpresentsanemulti-scale balanced dep hash method.The method uses multi-scale input,which efectively improves the abilityof leaming the image features fromthe network.Moreover,anew lossfunction is proposed.Under the premiseofpreserving thesemantic similarity, thequantization error and the balance ofhash code are taken intoaccounttogenerate the high quality hash code.After experimenting on two benchmark databases: CIFAR-10 and Flickr,this method has been improved by $5 . 5 \%$ and $3 . 1 \%$ of the search accuracy compared with today's advanced image retrieval methods.

Key Words: multi-scale; balance; deep hashing; convolutional neural network; image retrieval

# 0 引言

最近邻搜索（nearest neighbor search，NNS）[1]已经成为许多机器学习、数据挖掘、图像检索问题的基础。假设给定查询点 $n$ ，尝试找到最接近数据库中给定查询点 $n$ 的点，这便是NNS的主要思想。NNS在大数据领域的潜在应用前景受到学术界和行业的高度重视。维度灾难、存储成本和查询速度是NNS在处理大数据问题时所遇到的主要挑战。

哈希是 NNS 中重要而且有效的方法。可以通过构建哈希码获得非常好的效果以及实现理想的时间复杂度。哈希方法可以分为数据独立哈希及数据依赖哈希。两种方法的区别是生成哈希函数的具体方式。偏移不变核函数哈希（shiftinvariantkernel hashing,SIKH)[2]和最小损失哈希（minimal loss hashing,MLH）[3]是具有代表性的数据独立哈希方法，其哈希函数是人工或随机投影构建的。数据独立哈希方法的缺陷是显而易见的。理论上，过多的人工干预可能导致适应性以及准确性的缺失。

因此，从给定数据库学习哈希函数的数据依赖哈希方法被提出。这种哈希函数的构造方法可以生成更紧凑的二进制哈希码。数据依赖的哈希方法根据给定的训练数据集是否具有标签分为监督和无监督的方法。无监督哈希函数基于一定概率理论，可以实现局部敏感效应。无监督哈希方法通过使用未标记的数据来学习哈希函数。现如今有许多无监督的哈希方法，如局部敏感哈希（locality-sensitive hashing,LSH)[2],迭代量化（iterativequantization,ITQ）[4]和谱哈希（spectral hashing,SH）[5]。无监督的哈希算法是快速的，但是图片所含有的丰富语义没有得到很好地利用。为了避免宝贵的语义信息的丢失，监督哈希方法被提出。在某些情况下，与速度相比，精度更加被人们所重视。在这种情况下，监督哈希方法便更适用。如半监督哈希（semi-supervised hashing,SSH)[6],最小损失哈希（minimal loss hashing,MLH)[3]，基于线性判别分析的哈希（lineardiscriminant analysisbased hashing,LDAhash）[7]，基于内核的监督哈希（kernelbasedsupervisedhashing,KSH）[8]，基于潜在因子模型的监督哈希（latent factor models for supervised hashing,LFH）[9]。

虽然已经设计出了很多监督哈希方法，但是仍然存在以下缺陷：a）这些方法总是采用GIST全局特性，可能会造成语义信息丢失;b）大多数图像检索方法只能学习浅层特征，使图像信息之间的相关结构被忽略;c）一般来说，之前的方法普遍没有考虑到量化误差。

为了解决上述问题，本文提出了一种多尺度平衡深度哈希方法：a）使用多尺度特征作为输入，这样可以得到更鲁棒的语义信息，与局部特征描述符不同，分成多尺度输入后，从深层卷积网络提取的特征向量是对整体信息进行编码的全局描述符；b）将卷积神经网络（ConvolutionalNeuralNetwork，CNN）作为深度映射引入，更多地考虑了图像信息之间的相关结构；c)提出了一种由交叉熵、L2范数以及平衡项构成的新的损失函数。它不仅可以保留语义信息，还使得量化误差的问题得到了很好地解决，从而生成平衡且紧凑的哈希码

# 1 卷积神经网络哈希

卷积神经网络出现后，便快速引起了计算机视觉界的广泛关注。机器与人类在视觉感知能力方面的差距得到进一步缩小，其在物体识别，检测，图像解析和以及视频分类等各种任务中取得的显著成就推动了人工智能领域的前进。

CNN[0]是一个约束多层神经网络，其输入位于二维平面上。受人类视觉系统启发，CNN隐藏层的神经元从上一层的局部区域获取输入，并相对于其输入区域平铺在二维特征图中。典型的CNN由三种类型的结构构成，即卷积层，池化层以及全连接层。卷积特征图中的神经元彼此共享权重。池化层被放置在卷积层之后，可以根据所采用的操作为最大池化还是平均池化进行分类。通过调整步幅和输入滤波器大小，卷积层和池化层都可以重叠。

CNNH[I]以及后来的改进CNNH\*[12]均为以原始图像数据为输入的两阶段框架。在第一阶段，相似度矩阵 $s$ 被分解为一

个乘积的形式:

$$
S = \frac { 1 } { q } H H ^ { T }
$$

其中: $\mathbf { H } \in \{ - 1 , 1 \} ^ { n \times q }$ 表示每行是一个 $q$ 维哈希码的近似哈希码矩阵。

在第二阶段，原始图像像素以及预生成的二进制码H（CNNH\*及其二进制标签 $\mathbf { Y }$ ）被馈送到CNN，CNN的目标是使输出之间的误差最小化，并将目标二进制矢量连接到 $\mathbf { H }$ 和 $\mathbf { Y }$ 。

在哈希函数学习阶段，CNNH利用深度网络学习图像特征表示以及哈希函数。具体来说，CNNH采用常用的深层框架作为其基本网络，并设计具有softmax激活的输出层以生成 $q$ 维哈希码。CNNH以监督的方式训练设计好的深度网络。在哈希编码学习阶段学习到哈希码被用作地面校正。另外，如果训练图像的离散类标签可用，则CNNH还合并这些图像标签以学习哈希函数。基于深度网络，CNNH同时学习深层特征和哈希函数。然而，CNNH是一个具有两个阶段的框架，其中第二阶段中的学习的深层特征不能帮助改进第一阶段中的近似哈希码学习，这极大限制了哈希学习的性能。

通常，使用具有负对数似然的逻辑回归作为损失函数用于单标签分类。也经常使用其他种类的损失函数如欧氏距离和交叉熵。本文提出了由交叉熵、L2范数以及平衡项构成的新损失函数，会在本文后面详细介绍。

最近有很多这样利用卷积神经网络学习更有效的图像表示的方法，获得了比常规哈希方法性能更好的图像表示。然而，这些方法仍存在诸多挑战。例如：图像信息没有获得更多元化的学习；在学习深层哈希算法的过程中存在不可控的量化误差，这不能最佳地兼容连续哈希码转换成离散的二进制代码，最终影响二进制代码的质量等。

# 2 多尺度平衡深度哈希

在相似度检索中，给出了 $N$ 点 $\{ \pmb { x } _ { i } \} _ { i = 1 } ^ { N }$ 的训练集，每一个表示为 $D$ 维特征向量 $\boldsymbol { x } \in \mathbb { R } ^ { D }$ 。一些点与相似性标签 $s _ { i j }$ 相关联，其中$s _ { i j } = 1$ 表示 $x _ { i }$ 和 $x _ { j }$ 相似，若 ${ s } _ { i j } = - 1$ 则表示 $x _ { i }$ 和 $x _ { j }$ 不相似。目标是学习非线性哈希函数 $f : x \mapsto H \in \{ - 1 , 1 \} ^ { K }$ 来对紧凑的 $\boldsymbol { K }$ 位哈希码$H = f ( x )$ 中的每个点 $x$ 进行编码，从而保留给定对之间的相似性。

本文提出了一种新的多尺度平衡深度哈希图像检索方法。该方法通过多个尺度接受输入图像，并利用卷积神经网络哈希通道对其进行处理：a）将图片多尺度化作为输入；b）全连接哈希层，用于生成紧凑的哈希码；c）利用交叉熵函数构成的损失层来保留语义相似信息；d）利用由L2范数构成的量化损失层来控制生成哈希码的质量。

# 2.1多尺度平衡深度哈希方法

Lazebnik等人提出了使用基于特征包(bagoffeature,BoF)的方法对空间信息进行编码的空间金字塔匹配（spatialpyramidmatching,SPM）方法[13]。它们代表使用几个级别或尺度的金字塔的图像。来自不同尺度的特征被组合以形成图像表示，使特征越粗糙获得的权重越小，而特征越精细获得的权重越大。此文认为在较粗糙的层面上发现的匹配可能涉及越来越多的不同的图像特征。在本文中同样使用卷积特征图作为局部描述符，以同样思路探索多尺度情况。实验后发现卷积特征图的深层特征与传统的描述符不同：不同级别的特征的加权和不比其简单的总结表现出优越的性能。Kaiming等人设计了一种称为空间金字塔池化（spatial pyramid pooling,SPP）[14]的方法。在 SPP中，最后一个卷积层的特征图被划分成3或4个尺度的金字塔。首先，每个尺度的区域特征被级联，然后将比例级别特征级联到固定长度向量以被转发到下一个全连接层。在文献[15]中证明，这种策略对于无监督检索并不会取得什么好的效果，导致与其他简单组合方法相比的性能较差。

当用于图像检索时，这种特征仍然缺乏准确匹配两个图像所需的详细和本地信息。受到文献[13-15]的启发，本文更加深入地研究了应用此强大方法来获得辨别图像特征的可行性。图像由 $L$ 级金字塔表示，并且在每个级别，图像被均匀地划分成几个重叠或非重叠区域。计算这些小区域的向量表示，然后组合区域向量以形成图像特征向量。图像的单一尺度表示仅仅是等级数 $L = 1$ 的多尺度方法的特殊情况。

将小区域重新投入网络计算区域向量的时间成本将是巨大的，对于快速图像检索来说，这是不可接受的。受Girshick和Tolias 等人的工作的启发[16,17]，在某一层的特征图中，原始图像区域和区域之间的线性投影。然后可以有效地计算区域特征向量，而无须重新反馈相应的图像区域。

本文提出的多尺度平衡深度哈希方法的流程图如图1所示。

![](images/cc0dcd68aae920d49028f4d4e80ccd2526c8f621fc2bc1aa01b6933c3d31f29c.jpg)  
图1多尺度平衡深度哈希流程图

该网络在接受多尺度输入后，首先进入子卷积神经网络部分，该部分由卷积层、池化层及全连接层组成。在本文中，采用三个卷积层，第一个卷积层32个卷积核，大小为 $3 \times 3$ ；第二及第三层各64个卷积核，大小均为 $3 \times 3$ 。卷积层中间为两个池化层，两个最大池化的大小均为 $2 \times 2$ 。而后连接两个全连接层，其中第二个全连接层作为哈希层。最后，进入损失函数模块，该模块由三部分组成，包括softmax损失部分、量化损失部分以及平衡项部分组成。

假设 $X = [ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { N } ] \in \mathbb { R } ^ { d \times N }$ 为一个具有 $N$ 个样本的训练集，并且 $\boldsymbol { x } _ { n } \in \mathbb { R } ^ { d } \left( 1 < n < N \right)$ 是第 $n$ 个样本。哈希的最终目的是将其映射并量化为二进制编码。本文将训练样本 $x _ { n }$ 作为输入放入多层神经网络进行非线性变换，最终得到输出为二进制编码 ${ \mathbf b } _ { H }$ 。假设文中的网络是一个 $\scriptstyle { L + 1 }$ 层网络，分为 $m$ 个尺度输入，其中在第 $i \in ( 1 , 2 , . . . , m )$ 尺度下在第 $l \in ( 1 , 2 , . . . , L )$ 层的输出可以表述为如下公式：

$$
\mathbf { h } _ { i l } = \mathbf { W } _ { i l } ^ { \textit { T } } \cdot \mathbf { h } _ { i ( l - 1 ) } + \mathbf { c } _ { l }
$$

其中: ${ \bf h } _ { i l }$ 在第 $i$ 尺度下在第 $\mathbf { \xi } _ { l }$ 层的输出， $\mathbf { W } _ { i l } \in \mathbb { R } ^ { l \times K }$ 为第 $i$ 尺度下在第 $\mathbf { \xi } _ { l }$ 层的权重， $\mathbf { c } _ { \scriptscriptstyle { l } }$ 为该层的偏置。

各尺度在最高层的融合输出可通过如下公式求得：

$$
\mathbf { H } _ { L } = \phi \sum _ { i = 1 } ^ { m } \mathbf { h } _ { i L } = \phi \sum _ { i = 1 } ^ { m } ( \mathbf { W _ { \it i L } } ^ { T } \cdot \mathbf { h } _ { i ( L - 1 ) } + \mathbf { c } _ { L } )
$$

其中: $\mathbf { H } _ { \mathit { L } }$ 为最高层的融合输出，形式为一组 $K$ 位哈希码， $\phi$ 为

tanh 函数， $\mathbf { W } _ { L } \in \mathbb { R } ^ { L \times K }$ 、 ${ \bf c } _ { \scriptscriptstyle L } \in \mathbb { R } ^ { \scriptscriptstyle K }$ 分别为最高层的权重及偏置。

本文提出来的方法将卷积特征映射到 $[ - 1 , 1 ] ^ { \kappa }$ ，哈希码$\mathbf { H } _ { \mathit { L } } \in [ - 1 , 1 ] ^ { \mathit { K } }$ 是连续的实值。为了获得二进制哈希码 ${ \mathbf b } _ { H }$ ，阈值函数为

$$
{ \bf b } _ { { \scriptscriptstyle H } } = \mathrm { s g n } ( { \bf H } _ { { \scriptscriptstyle L } } )
$$

其中: $\mathbf b _ { H } \in \{ - 1 , 1 \} ^ { K }$ 为一组 $K$ 位二进制哈希码， $\mathrm { s g n } ( \cdot )$ 为符号函数，如果 $x > 0$ ，则 $\mathrm { s g n } ( \cdot ) = 1$ ，否则 $\mathrm { s g n } ( \cdot ) = - 1$ 。

# 2.2损失函数

由于将隐层状态值转换成二进制码的离散优化是非常具有挑战性的，为了便于优化，连续松弛被应用于二进制约束，被现有的哈希方法广泛采用[18]。然而，连续松弛将产生哈希函数学习工作所广泛忽视的两个重要问题：将连续松弛代替二进制约束会带来不可控的量化误差；采用连续松弛之间的内积作为二进制代码之间的汉明距离的替代所产生的近似误差。为了控制量化误差并缩小汉明距离与其替代之间的距离，学习高质量哈希码，本文设计了一种新的损失函数，由交叉熵控制和 $L 2$ 范数以及平衡项构成。它不仅可以保留语义信息，还能很好地解决量化误差的问题。

假设一张图片 $\boldsymbol { \mathcal { T } } ^ { ( n ) }$ 的二进制码 $\mathbf { b } _ { H } ^ { \quad ( n ) }$ 被用作 softmax 层的输入，则预测标签 $y ^ { ( n ) }$ 的概率为

$$
p ( { \boldsymbol y } ^ { ( n ) } = m \bigm | { \bf b } ^ { ( n ) } ) = \frac { e x p ( z _ { m } ) } { \displaystyle \sum _ { j = 1 } ^ { M } e x p ( z _ { j } ) } , m = 1 , 2 , . . . , M
$$

其中: ${ \boldsymbol { z } _ { m } } = { \bf w } _ { m } ^ { T } { \bf b } ^ { ( n ) } + { \boldsymbol { c } _ { m } }$ ， $\mathbf { w } _ { m } \in \mathbb { R } ^ { K \times 1 }$ 为 softmax 层的第 $m$ 个权重参数，$c _ { m }$ 为 softmax 层的第 $m$ 个偏置参数， $M$ 为训练图像的种类数，$\mathbf { b } ^ { ( n ) } \in \left\{ - 1 , 1 \right\} ^ { K }$ 。

通过考虑标签 $\mathbf { Y }$ 的负对数似然，则可以获得以下优化问题：

$$
\begin{array} { l } { { \displaystyle \underset { \{ \mathbf { B } \} } { m i n } \mathfrak { I } _ { 1 } = - \log p ( \mathbf { Y } \mid \mathbf { B } ) = - \sum _ { n = 1 } ^ { N } \log p ( { y } ^ { ( n ) } \mid \mathbf { B } ) } } \\ { { \displaystyle \quad = - \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } I \{ y ^ { ( n ) } = m \} \log \frac { e x p ( z _ { m } ) } { \displaystyle \sum _ { j = 1 } ^ { M } e x p ( z _ { j } ) } } , } \end{array}
$$

其中: $I \{ . \}$ 为示性函数，如果 ${ \boldsymbol { y } } ^ { ( n ) } = m$ ,则为1;否则为 $0 _ { \circ } \ \mathbf { B } = \{ b ^ { ( n ) } \} _ { n = 1 } ^ { N }$ 为所有图片的二进制码。上述优化问题利用标签信息去保存哈希码语义相似度。

设 $b ^ { ( n _ { 1 } ) }$ 为一张图片 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 1 } ) }$ 的二进制码， $b ^ { ( n _ { 2 } ) }$ 为另一张图片 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 2 } ) }$ 的二进制码， $b ^ { ( n _ { 3 } ) }$ 是图片 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 3 } ) }$ 的二进制码。其中图片 $\underline { { \boldsymbol { \mathcal { T } } } } ^ { ( n _ { 2 } ) }$ 与图片$\boldsymbol { \mathcal { T } } ^ { ( n _ { 1 } ) }$ 是相似的，图片 $\underline { { \boldsymbol { \mathcal { T } } } } ^ { ( n _ { 3 } ) }$ 与图片 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 1 } ) }$ 是不相似的。 $d i s t _ { H } ( b ^ { ( x ) } , b ^ { ( y ) } )$ 为二进制码 $b ^ { ( x ) }$ 和 $b ^ { ( y ) }$ 之间的汉明距离。优化式（8）问题可以使两张相似的图片 $\mathbf { \nabla } \mathcal { T } ^ { ( n _ { 2 } ) }$ 与 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 1 } ) }$ 的汉明距离 $d i s t _ { { \scriptscriptstyle H } } ( b ^ { ( n _ { 1 } ) } , b ^ { ( n _ { 2 } ) } )$ 尽可能小，同时使两张不相似的图片 $\boldsymbol { \mathcal { T } } ^ { ( n _ { 1 } ) }$ 与 $\underline { { \boldsymbol { \mathcal { T } } } } ^ { ( n _ { 3 } ) }$ 的汉明距离 $d i s t _ { { \scriptscriptstyle H } } ( b ^ { ( n _ { 1 } ) } , b ^ { ( n _ { 3 } ) } )$ 尽可能大[19]。

由于二元约束优化问题难以解决。在本文中，为了解决离散优化问题，提出了一种新的策略，利用连续松弛以取代二进制约束。本文采用连续哈希码代替离散二进制码。式(8）的优化问题在可以重新定义如下：

$$
\begin{array} { c } { { \displaystyle { m i n } \ n _ { 1 } \ \eta _ { 1 } = - { \displaystyle \sum _ { n = 1 } ^ { N } } { \displaystyle { \sum _ { m = 1 } ^ { M } } } I \{ y ^ { ( n ) } = m \} \log \displaystyle { \frac { e x p ( \hat { z } _ { m } ) } { \displaystyle { \sum _ { j = 1 } ^ { M } } e x p ( \hat { z } _ { j } ) } } } \\ { { s . t . \quad \mathbf { H } _ { \mathbf { L } } ^ { { ( n ) } } = \mathbf { b } _ { \mathbf { H } } ^ { { ( n ) } } , \qquad n = 1 , 2 , 3 . . . , N } } \\ { { \mathbf { H } _ { \mathbf { L } } ^ { { ( n ) } } \in \mathbb { R } ^ { K \times 1 } , \qquad n = 1 , 2 , 3 . . . , N } } \\ { { \displaystyle H _ { \mathbf { \Sigma } } ^ { { ( n ) } } \in [ - 1 , 1 ] } , \quad k = 1 , 2 , 3 . . . , K } } \end{array}
$$

其中: $\eta _ { \mathrm { 1 } }$ 为交叉熵损失函数， $\hat { \mathcal { Z } } _ { m } = \mathbf { W } _ { m } ^ { T } \mathbf { H } _ { L } ^ { ( n ) } + c _ { m }$ ，和 $\mathbf { H } _ { \mathbf { L } } = \{ H ^ { ( n ) } \} _ { n = 1 } ^ { N }$ ，$\mathbf { H _ { L } } ^ { ( n ) } = \{ H _ { 1 } ^ { ( n ) } , H _ { 2 } ^ { ( n ) } , . . . , H _ { K } ^ { ( n ) } \} \ ,$ 0

然而，连续松弛导致不可控的量化误差 $[ 2 0 ]$ 。本文中，正则化项 $\mathcal { L }$ 被引入去控制的量化误差。使用连续哈希码和离散的二进制码之间的 $L 2$ 范数作为正则化项 $\mathcal { L }$ 。然而，仅仅优化正则化项 $\mathcal { L }$ 就可能导致二进制码全由1组成。这是因为优化L2范数项会影响哈希码的平衡性。为了维持哈希码的平衡性，利用哈希码平均值的平方作为平衡准则。这个平衡的标准鼓励哈希码每一位被映射成-1或1尽可能均匀[21]。为了产生好的二进制代码，优化问题为

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } _ { \{ { \bf b } _ { \mu } , { \bf R } _ { 1 } \} } \eta _ { 2 } = \eta _ { 1 } + \gamma \mathcal { L } + \lambda Q } \\ { \displaystyle \quad \quad = - \sum _ { n = 1 } ^ { N } \{ { y ( { \bf b } ^ { ( n ) } = m ) \log \frac { e x p ( \hat { z } _ { n } ) } { \displaystyle \sum _ { j = 1 } ^ { M } e x p ( \hat { z } _ { j } ) } } } \\ { \displaystyle \quad \quad + \gamma \sum _ { n = 1 } ^ { N } \| { \bf \cal { H } } _ { \bf L } ^ { ( n ) } | - | { \bf b } _ { \mu } ^ { ( n ) } | \| _ { 2 } } \\ { \displaystyle \quad \quad + \lambda \sum _ { n = 1 } ^ { N } ( \rho ( { \bf H } _ { \bf L } ^ { ( n ) } ) ) ^ { 2 } , } \end{array}
$$

其中：为控制正则化强度的权重参数， $\lambda$ 为控制平衡标准的相对重要性的参数， $\rho ( \cdot )$ 为平均算子，为L2范数，为绝对值。正则化项 $\mathcal { L }$ 控制将连续松弛代替二进制约束产生的不可控制的

量化误差。平衡的标准 $\boldsymbol { \mathscr { Q } }$ 保证哈希码的每一位比特具有相同的概率为1或-1，这样使得在二进制哈希码中0和1出现的几率尽可能相等。

# 3 实验设计及结果分析

# 3.1实验算法流程

算法1多尺度平衡深度哈希算法  
输入：训练样本 $\scriptstyle \mathbf { I } = \{ { \mathcal { T } } ^ { ( n ) } \} _ { n = 1 } ^ { N }$ 和它们对应的标签向量 $Y = \{ \boldsymbol { y } ^ { ( n ) } \} ^ { N }$ 。输出：所有权重参数 $W$ ；所有偏置参数 $b$ 。  
初始化：权重采用高斯分布初始化

循环：

1：通过前向传播计算 $h _ { i l }$ ·  
2：根据式(2)(3)计算哈希码 $H _ { L } ( x _ { i } )$ ：  
3：根据式(4)计算预测输出 $\hat { z } _ { i }$ ·  
4：根据式(8)利用 $W , H _ { L } ( x _ { i } ) , \mathbf { Z } _ { i } , \hat { z } _ { i }$ 来计算 $\eta _ { 2 }$ ：  
5：利用来随机梯度下降法（SGD）更新参数 $W , b$ ·

直到：达到固定迭代次数返回：W,b

# 3.2实验数据集

根据本文所提出的方法，利用两个基准数据集CIFAR-10，Flickr对本方法进行评估。

a)CIFAR-10 图像数据库。这个数据集是8000万张Tiny图像数据集的子集，其中分为10类（每类6000张图像）的对象的彩色图像。每个图像的大小是 $3 2 \times 3 2$ 。这些类包含飞机、汽车、鸟、猫、鹿、狗、青蛙、马、船和卡车。对于CIFAR-10数据集，从每个类别中随机选择1000张图像以形成测试查询集，并且剩余的50000张图像用作训练集。根本文使用512维GIST特征作为传统特征表示和4096维CNN特征作为深度语义特征表示。

b)Flickr图像数据库。由Flickr收集的25000张图像组成，其中每个图像都标有一个语义概念，共38 种语义概念。在本文中，将该子集的图像调整为 $3 2 \times 3 2$ 。

# 3.3 实验环境配置

本文实验环境为：GeForceGTXTitanXGPU、中央处理器为Intel(RCorei7-5930K3.50GHz、内存为64GB、操作系统为Ubuntu14.04。所提出的模型使用开源库KERAS来实现。模型总体目标函数通过随机梯度下降（SGD）优化。SGD的学习率为10-6，每次更新后的学习率衰减值为10-7，Nesterov动量为0.9。每批次的大小为32。将本文网络的输入层和隐藏层之间的初始权重设置为正态分布。其初始循环权重矩阵设置为单位矩阵，剩余权重采用高斯分布。在本实验中，参数／和λ分别设定为0.001和0.001。本文后面将会进行针对这些参数配置的实验，说明参数选择的原因及其合理性。

# 3.4 实验评价指标

为了评估哈希方法的有效性，考虑了普遍用于定量性能比较的几个指标后，最终采用如下三个度量:

a）平均检索精度 (MAP,Mean Average Precision),它是每个查询样本平均准确率的平均值。

b）以哈希码长度48bits作为参考时，精度 $@$ 前 $n$ 个返回结果(Precision curve w.r.t. top-n $@$ 48 bits)。根据查询样本和数据集之间的汉明距离对数据库中的图像进行排名，并计算排名列表的前 $n$ 个精度。

c)汉明半径2内的精度，计算查询样本和数据集之间的汉明距离小于2的精度。

在实验中，本文应用类标签作为正确的标准。通过检查查询图像和返回的图像是否具有相同的标签来计算所有指标。如果这些指标的值更高，性能更好。

# 3.5 实验结果及分析

# 1）CIFAR-10数据库上的结果

本文利用上述三个指标评估了提出的多尺度卷积神经网络哈希方法的检索质量，并与经典方法以及一些当今前沿方法进行了比较，其中包括三个无监督方法： $\mathrm { L S H } ^ { [ 2 ] }$ 、SH[5]和ITQ[4]方法；以及八个监督方法：DHN[22]、CNNH[1]及其变体CNNH\*[12]、DNNH[12]、KSH[8]、MLH[3]、BRE[23]和ITQ-CCA[24]方法。LSH、SH、ITQ、KSH、MLH、BRE和ITQ-CCA是传统的哈希方法，它们使用512维向量作为输入来学习哈希函数。其他四种哈希方法（即DNH、DNNH、CNNH\*和CNNH)使用4096 维CNN特征作为输入来执行哈希函数。

可以清楚地发现：a)比较利用手工特征和利用4096维CNN特征的相同的方法，可以看出CNN特征可以提高传统方法的检索精度;b)与其他深度哈希方法CNNH、CNNH\*、DNNH、DHN相比，提出的MBDH将检索平均MAP从 $. 4 2 . 9 \% ( \mathrm { C N N H } ) . 4 8 . 4 \%$ $\mathrm { ( C N N H ^ { * } }$ ）、 $5 5 . 2 \%$ (DNNH)、 $5 5 . 5 \%$ (DHN)至 $67 . 6 \%$ 。这是因为所提出的方法运用了多尺度的图片输入，并且设计了新的损失函数，其保持了哈希码的语义相似性和平衡性，并且同时考虑了连续编码转换为离散二进制码产生的量化误差，从而可以提高检索精度。

表1CIFAR-10数据库上MAP的图像检索结果  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="4">CIFAR-10 (MAP)</td></tr><tr><td>12bits</td><td>24 bits</td><td>32 bits</td><td>48 bits</td></tr><tr><td>MBDH</td><td>0.654</td><td>0.663</td><td>0.671</td><td>0.676</td></tr><tr><td>DNH</td><td>0.555</td><td>0.594</td><td>0.603</td><td>0.621</td></tr><tr><td>DNNH</td><td>0.552</td><td>0.566</td><td>0.558</td><td>0.581</td></tr><tr><td>CNNH*</td><td>0.484</td><td>0.476</td><td>0.472</td><td>0.489</td></tr><tr><td>CNNH</td><td>0.429</td><td>0.511</td><td>0.509</td><td>0.522</td></tr><tr><td>KSH</td><td>0.303</td><td>0.337</td><td>0.346</td><td>0.356</td></tr><tr><td>ITQ-CCA</td><td>0.264</td><td>0.282</td><td>0.288</td><td>0.295</td></tr><tr><td>MLH</td><td>0.182</td><td>0.195</td><td>0.207</td><td>0.211</td></tr><tr><td>BRE</td><td>0.159</td><td>0.181</td><td>0.193</td><td>0.196</td></tr><tr><td>SH</td><td>0.131</td><td>0.135</td><td>0.133</td><td>0.130</td></tr><tr><td>ITQ</td><td>0.162</td><td>0.169</td><td>0.172</td><td>0.175</td></tr><tr><td>LSH</td><td>0.121</td><td>0.126</td><td>0.120</td><td>0.120</td></tr></table></body></html>

![](images/b688758860e366707ba35bf46682003596aa54fead365b5450ec93f51bb1b27a.jpg)  
图2CIFAR-10 数据集的结果图

图2左边显示了在CIFAR-10数据集上的不同比特情况下汉明距离小于等于2的精度曲线，可以看出，所提出的MBDH在所有比特的汉明距离小于等于2实现了最佳的检索精度。图2中间展示了所提出的MBDH与其他方法在所有比特情况下前的MAP。图2右边显示了在CIFAR-10数据集上48bit情况下前1000张返回图片的精度曲线，所提出的MBDH仍然实现了最佳的检索精度。

MBDH在本数据集上查询10个类返回的前10个结果如图3所示。其中，左侧为查询图片，右侧有红色方框标记的为错误结果。

# 2）Flickr数据库上的结果

在该实验中采用的实验设置与上文相同。表2表示在Flickr数据集上不同长度的哈希码的检索MAP结果。

![](images/00f5f66420e6f7d6d95f201bf50fd5bf955057de48be920f0e9cf662c2cd4857.jpg)  
图3MBDH在CIFAR-10数据集查询返回前10个结果

表2Flickr数据库上MAP 的图像检索结果  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="4">Flickr (MAP)</td></tr><tr><td>12bits</td><td>24 bits</td><td>32 bits</td><td>48 bits</td></tr><tr><td>MBDH</td><td>0.853</td><td>0.859</td><td>0.863</td><td>0.872</td></tr><tr><td>DHN</td><td>0.810</td><td>0.828</td><td>0.829</td><td>0.841</td></tr><tr><td>DNNH</td><td>0.783</td><td>0.789</td><td>0.791</td><td>0.802</td></tr><tr><td>CNNH*</td><td>0.749</td><td>0.761</td><td>0.768</td><td>0.776</td></tr><tr><td>CNNH</td><td>0.732</td><td>0.734</td><td>0.741</td><td>0.740</td></tr><tr><td>KSH</td><td>0.690</td><td>0.702</td><td>0.702</td><td>0.706</td></tr><tr><td>ITQ-CCA</td><td>0.513</td><td>0.531</td><td>0.540</td><td>0.555</td></tr><tr><td>MLH</td><td>0.610</td><td>0.618</td><td>0.629</td><td>0.634</td></tr><tr><td>BRE</td><td>0.571</td><td>0.592</td><td>0.599</td><td>0.604</td></tr><tr><td>SH</td><td>0.531</td><td>0.533</td><td>0.531</td><td>0.529</td></tr><tr><td>ITQ</td><td>0.544</td><td>0.555</td><td>0.560</td><td>0.570</td></tr><tr><td>LSH</td><td>0.499</td><td>0.513</td><td>0.521</td><td>0.548</td></tr></table></body></html>

可以清楚地看到：

a）利用4096维CNN特征的传统哈希方法比使用手工特征的相同方法具有更好的性能，可以发现CNN特征可以提高传统方法的检索精度。b）所提出的MBDH实现了优于其他比较的现有哈希技术方法的性能。并且所提出的MBDH 将平均MAP从DHN 的$84 . 1 \%$ 改进到 $87 . 2 \%$ 。c）所提出的MBDH可以实现优于其他8种监督哈希方法(即DNH、DNNH、CNNH、CNNH\*、KSH、MLH、BRE 和ITQ-CCA方法)的性能，因为其使用多尺度输入，并使用了新的损失函数。

# 3.6关于参数配置影响的实验分析

将两个参数／和 $\lambda$ 设置为从 $1 0 ^ { - 5 }$ 到1的不同值，为了方便记录，此处和λ取相同的值。并计算长度为48位的哈希码在CIFAR-10数据集上的MAP。结果如表3所示。

表3参数配置影响实验结果  

<html><body><table><tr><td rowspan="2">评价度量</td><td colspan="6">不同参数／和λ取值下的实验结果(48bits)</td></tr><tr><td>10-5</td><td>10-4</td><td>10-3</td><td>10-2</td><td>10-1</td><td>1</td></tr><tr><td>MAP</td><td>0.632</td><td>0.658</td><td>0.676</td><td>0.665</td><td>0.643</td><td>0.60</td></tr></table></body></html>

从表3可以明显观察到当参数和λ取 $1 0 ^ { - 3 }$ 时，MAP达到最高值为0.676。解释了本文参数选择的原因及合理性。

# 3.7多尺度有效性的实验分析

为了进一步验证本文所提出的多尺度平衡深度哈希方法的有效性，本文还对相同网络结构的单尺度以及双尺度方法进行了实验，计算三种方法在哈希码长度为48位的情况下三个评价指标的值。结果如表4所示。

从表4中可以明显看出，本文提出的方法的三个度量指标值都明显高于单尺度及双尺度方法。尤其较单尺度方法，MAP提高了 $4 . 4 \%$ 。通过上述实验，可以进一步证明本文提出的

MBDH的有效性。

表4多尺度输入有效性实验结果  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">评价度量</td></tr><tr><td>MAP</td><td>Precision @500</td><td>Hamm dist<=2</td></tr><tr><td>单尺度</td><td>0.632</td><td>0.6092</td><td>0.6174</td></tr><tr><td>双尺度</td><td>0.661</td><td>0.6423</td><td>0.6521</td></tr><tr><td>多尺度</td><td>0.676</td><td>0.6538</td><td>0.6624</td></tr></table></body></html>

# 4 结束语

本文提出一个简单而有效的多尺度平衡深度哈希模型MBDH来学习二进制哈希码，用于快速图像检索。该方法不依赖于数据的对称相似性，提出的深度哈希网络架构将单一尺度输入换为多尺度输入，并同时优化了语义相似性的交叉熵损失以及生成紧凑哈希码时产生的量化损失，并考虑到了哈希码的平衡性。本文进行了广泛的实验，并提供了MBDH在两个基准数据库上的实验结果以及与多种当今先进哈希方法的比较评估。实验结果表明，通过采用多尺度输入，并对损失函数进行优化后，MBDH分别对CIFAR-10以及Flickr数据集的最佳检索结果较当今先进方法分别提高了 $5 . 5 \%$ 和 $3 . 1 \%$ 检索精度。进一步展示了所提出的方法对数据量在100万以上的大规模数据集的可扩展性和有效性。

# 参考文献：

[1]易唐唐，黄立宏.CBIR中一种基于最近邻的改进相关反馈算法[J//OL]. 计算机应用研究,2015,32(08):2326-2330.   
[2]Raginsky M,Lazebnik S. Locality-sensitive binary codes from shiftinvariant kernels [C]//Advances in Neural Information Processing Systems. 2009:1509-1517.   
[3]Norouzi M,Blei D M.Minimal loss hashing for compact binary codes [C]// Proc of International Conference on Machine Learning.2011:353-360.   
[4]Gong Y,Lazebnik S,Gordo A,et al. Iterative quantization: a procrustean approach to learning binary codes for large-scale image retrieval[J].IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35(12):2916- 2929.   
[5]Weiss Y,TorralbaA,Fergus R.Spectral hashing [C]//Advances in Neural Information Processing Systems.2009:1753-1760.   
[6]Wang J, Kumar S, Chang SF. Semi-supervised hashing for scalable image retrieval[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2010:3424-3431.   
[7]Strecha C,Bronstein A, Bronstein M,et al.LDAHash: improved matching with smaller descriptors [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2012,34 (1): 66-78.   
[8]Liu W,Wang J,JiR,et al.Supervised hashing with kernels [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.2012:2074- 2081.   
[9]Zhang P,Zhang W,Li WJ,etal. Supervised hashing with latent factor models [C]// Proc of the 37th International ACM SIGIR Conference on Research& Development in Information Retrieval.2014:173-182.   
[10] Krizhevsky A, Sutskever I, Hinton G E. Imagenet classification with deep convolutional neural networks [C]// Advances in Neural Information Processing Systems.2012:1097-1105.   
[11] Xia R,Pan Y,Lai H,etal. Supervised hashing for image retrieval via image representation learning [C]//Proc of the 28th AAAIConference on Artificial Intelligence.2014: 2156-2162.   
[12] Lai H,Pan Y,Liu Y,et al. Simultaneous feature learning and hash coding with deep neural networks [C]// Proc of International Conference on Computer Vision and Pattern Recognition.2015:3270-3278.   
[13] Lazebnik S,Schmid C,Ponce J.Beyond bags of features: Spatial pyramid matching for recognizing natural scene categories [C]//Proc of International Conference on Computer Vision and Pattern Recognition.2006:2169-2178.   
[14] He K, Zhang X,Ren S,et al. Spatial pyramid pooling in deep convolutional networks for visual recognition [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2015,37(9): 1904-1916.   
[15]Hao J,Dong J,WangW,etal.What Is the BestPractice for CNNsApplied to Visual Instance Retrieval?[J].arXiv preprint arXiv:1611.O1640,2016.   
[16] Girshick R.Fast r-CNN[C]//Proc of International Conference on Computer Vision and Pattern Recognition.2015:1440-1448.   
[17] Tolias G,Sicre R,Jégou H.Particular object retrieval with integral maxpooling of CNN activations [J].arXiv preprint arXiv: 1511.05879,2015.   
[18] Wang J, Shen HT, Song J,et al.Hashing for similarity search: Asurvey [J]. arXiv preprint arXiv:1408.2927,2014.   
[19] Li WJ, Wang S, Kang W C.Feature learning based deep supervised hashing with pairwise labels [J].arXiv preprint arXiv:1511.03855,2015.   
[20] Kang WC,LiWJ, Zhou ZH.Column Sampling Based Discrete Supervised Hashing[C]//Proc of the 3Oth AAAI Conference on Artificial Intelligence. 2016:1230-1236.   
[21] Do TT,DoanA Z,Cheung NM.Discrete hashing with deep neural network [J].arXiv preprint arXiv: 1508.07148,2015.   
[22] Zhu H,Long M,Wang J,et al.Deep Hashing Network for Efficient Similarity Retrieval [Cl//Proc of the 3Oth AAAI Conference on Artificial Intelligence.2016: 2415-2421.   
[23] Kulis B,Darrell T.Learning to hash with binary reconstructive embeddings [C]//Advances in Neural Information Processing Systems.20o9:1042-1050.   
[24] Gong Y,Lazebnik S,Gordo A,et al. Iterative quantization: a procrustean approach to learning binary codes for large-scale image retrieval [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35 (12): 2916- 292