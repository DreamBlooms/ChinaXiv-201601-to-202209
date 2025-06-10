# 基于3D卷积神经网络的视频哈希算法\*

刘玉莹」，刘宏哲1+，袁家政²，李兵

(1．北京联合大学 北京市信息服务工程重点实验室，北京 100101；2.北京开放大学，北京 10081；3．中国科学院自动化研究所模式识别国家重点实验室，北京100190)

摘要：随着视频分享应用和平台的蓬勃发展，视频数据正处于指数上升阶段，针对目前相似性视频检索方法中快速性和准确性仍无法满足用户要求等问题，提出了一种基于3D卷积神经网络的视频快速检索方法。该算法将3D卷积神经网络与哈希学习方法结合应用于视频数据，既能快速学习视频时空特征表示，又能极大地缩短视频检索时间。在常用视频数据集上的实验结果表明，利用所提出的方法对视频进行相似性检索性能优于当前主流方法。

关键词：深度学习；哈希算法；视频检索 中图分类号：TP doi:10.19734/j.issn.1001-3695.2018.07.0664

# Video hash algorithm based on 3D convolutional neural network

Liu Yuying1, Liu Hongzhel+, Yuan Jiazheng²,Li Bing³ (1. BeijingKeyLaboratoryof Information Service EngineringBeijing,Beijing Union UniversityBeijinglOolo1,China; 2. Beijing Open UniversityBeijingOo081,China;3.StateKeyLaboratoryofPatern Recognition,InstituteofAutomation, Chinese AcademyofScienceBeijing 10o19o,China)

Abstract: With the vigorous development of video sharing applications and platforms,video data is inan exponentially rising phase.Inorderto solve this thorny problemthat the speedand accuracyof thecurrent similarity video retrieval methods stillcannot meet the requirements of users,this paper proposes a new similarity video quick retrieval method, whichcombines the three-dimensionalconvolutional neural network with the hash learing methodandapply to video data. It notonlycan quicklylearnthevideo spatiotemporal feature representation but alsocan greatly shorten the video retrieval time.The experimental resultson theset show thatthe similarityretrieval performanceof thevideo using the proposed method is superior to the current mainstream methods.

Key words:deep learning;hashing method;video retrieval

# 0 引言

近年来，随着移动互联网技术的快速发展，图像、视频等多媒体数据呈爆炸式增长。对于互联网用户来说，从海量的视频数据中快速的检索到对自己有用或者喜欢的视频非常重要；对互联网平台来说，为用户进行个性化的视频推荐或者相关视频广告的投放能够有效地提高用户体验以及产品的销量；对视频原创者来说，能够充分对其视频进行版权保护。因此，对相似视频检索技术的研究成为基于内容的视频检索、视频个性化推荐和原创视频版权保护等应用的关键点。相似视频检索的基本思想是将查询视频与视频数据库中的视频进行近似最近邻搜索，返回与之内容相似的视频。传统的方法是先提取视频特征，然后计算查询视频特征与视频数据库中视频特征的欧氏距离，并根据距离从小到大的顺序来返回相似的视频。但是随着互联网上的视频数据的井喷式增长，传统的线性搜索方法需要的存储空间消耗大、计算复杂度高、检索速度慢。为了解决传统方法对存储空间和检索时间的上的局限，近来近似最近邻搜索技术发展迅猛，其中哈希技术作为一种代表性方法受到了广泛关注，这种方法能够将视频数据的高维特征映射到低维空间，产生简洁的二值码表示，通过计算查询视频与数据库视频二值码之间的汉明距离来进行相似度检索，能够显著降低计算开销并且提升检索性能。近几年，在许多关于计算机视觉的课题研究上运用深度学习技术都显著提升了性能，如目标检测、分类、分割等，这些任务性能的提升都归功于深度卷积神经网络在特征表示学习上的强大，但这些任务主要是针对图像作为输入进行的，因此 2D卷积[9能很好地对图像进行特征表示学习。而在视频作为输入的视觉任务中，2D卷积不能及时捕获视频数据的时序信息，因此针对视频时序信息的表示，研究者们提出了3D卷积[10]来同时提取视频数据的时间特征和空间特征，从而保证视频特征表示的连续性。本文基于深度学习和哈希技术，提出了一种新的相似性视频快速检索方法，运用3D卷积神经网络[10]同时对视频进行时间特征和空间特征的提取与融合，利用哈希方法对融合后的视频时空特征进行量化编码，得到视频的哈希二值码，计算查询视频与大规模视频数据集的汉明距离，实现快速有效的视频检索。

# 1 相关研究

# 1.1哈希学习

为了实现高效的近似最近邻搜索，哈希方法旨在将数据时相似性。仕数据层面可分为数据独立型"""和数据依赖型[16-33]哈希方法。数据独立型哈希方法主要采用随机投影方法将数据映射为二值码，但是这种不依赖数据的哈希方法需要较多位数的二值码才能得到比较高的精度。为了解决数据独立型哈希的码长问题，数据依赖型哈希方法利用数据的属性或者数据所具有的标签信息来监督训练来生成紧凑的二值码。现有的数据依赖型哈希算法又可分为有监督哈希方法[2-5,7,8,21-311和无监督哈希方法[1,6.16-20.32]。在无监督方法中哈希学习过程是在没有标签信息的情况下完成的。利用离散优化技术对数据的二值码进行学习，保持原始高维特征之间的相似性关系，比较典型的算法有Yair 等人[7]提出的谱哈希(SpectralHashing,SH)、Gong 等人[18]所提的迭代量化哈希方法(iterative quantization,ITQ)以及等人 Irie[20]提出的局部线性哈希方法(locality linear hashing,LLH)。虽然无监督哈希方法相比数据独立哈希方法的检索精度高了不少，但是缺少数据标签信息，总体的检索精度还是很难提升，因此有监督哈希方法的出现一定程度上解决了这一局限性，利用带有标签信息的数据进行哈希学习，该类哈希学习模型的目标是最小化二值码之间的距离并对增大数据之间的相似度差异，即使得相似的数据尽量靠近，不相似的数据尽量远离。在过去的几年里，由于深度卷积神经网络在各种视觉任务展现出其优越的性能，研究者们将深度学习与哈希方法结合提出了许多深度哈希方法。通过训练端到端的(convolutional neuralnetwork,CNN)[9]模型，现有的深度哈希方法能够同时学习图像表示以及在监督或者非监督的方法得到二值码。虽然现有的深度哈希方法已经取得了显著的性能，但它们大多是为图像检索设计的。相比之下，专门为视频检索设计的深度哈希方法[4-8相对较少，因为学习视频特征表示比图像特征表示更具挑战性。由于视频提供的信息比图像提供的更加多样和复杂，在视频哈希算法设计中，研究者们主要集中在学习视频的空间特征。例如，文献[4]利用视觉注意力模型提取视频特征视觉特征，并通过深信念网络(deep belief network，DBN)融合视觉外观和视觉特征生成视频哈希，获得具有代表性的视频特征；为了融合视频的空间特征和时间特征，文献[5]提出了二值长短时记忆(binary long short-term memory,BLSTM)网络，利用LSTM捕获视频中的时间信息，采用二值化的LSTM单元在每个时间步长上输出二进制码，在处理传统的序列数据(如文本和语音)时，LSTM具有优异的性能。然而，由于视频内容的高度多样性和复杂性，该方法在处理视频数据的泛化能力不高。现有的视频哈希方法主要集中在学习视频的感知特征，再将学习到的特征应用于图像哈希方法中去得到二值码表示，这两部分不能相互反馈，即产生的哈希码的质量在很大程度上取决于所获得的特征的质量，而哈希码没有被用来指导特征的学习。由于3D 卷积神经网络在学习视频时空特征上的优越性，本文将视频时空特征学习与能够融入深度卷积神经网络的哈希学习相结合，提出了一种端到端的视频哈希算法，并能够快速有效地应用于相似视频检索中。

# 1.23D Convolutional Neural Networks

利用二维卷积网络对视频进行特征提取一般是对视频的每一帧图像分别利用CNN来进行特征学习，这种方式不会考虑时间维度的帧间运动信息，而使用3D卷积神经网络能更好的捕获视频中的时间和空间的特征信息。图1是3DCNN对图像序列（视频）采用3D卷积核进行卷积操作。

图1中进行卷积操作的时间维度为3，即对连续的三帧图像进行卷积操作，3D卷积是通过堆叠多个连续的帧组成一个立方体，然后在立方体中运用3D卷积核。在这个结构中，卷积层中每一个 feature map 都会与上一层中多个邻近的连续帧相连，以此来捕捉运动信息。例如图1左边，一个卷积map 的某一位置的值是通过卷积上一层的三个连续的帧的同一个位置的局部感受野得到的。3D卷积核只能从cube 中提取一种类型的特征，因为在整个cube中卷积核的权值都是一样的，也就是共享权值，都是同一个卷积核（图中同一个颜色的连接线表示相同的权值）。因此本文可以采用多种卷积核，以提取多种特征。

![](images/d768fdcd5cec509434d7a4adc4c9990163c1cf9daaf8c4a215a3f42e023f60c8.jpg)  
图13D卷积计算过程  
Fig.13D convolution alculation process

# 2 基于3DCNN的视频哈希算法

在本章中将具体介绍所提出的基于3D卷积神经网络的视频哈希方法模型及学习算法。

# 2.1符号定义

本文使用 $m$ 表示向量， $\mathbf { \Omega } _ { M }$ 表示矩阵， $M ^ { \scriptscriptstyle T }$ 表示矩阵的转置。用来表示向量的欧氏范数，符号函数 $\mathrm { s g n } ( \bullet )$ 表示如果元素为正，则返回1，否则返回-1。假设数据集中有 $\mathfrak { n }$ 个数据点（视频片段） $V = \{ \nu _ { i } \} _ { i = 1 } ^ { n }$ ，其中 $\boldsymbol { \nu } _ { i } , \boldsymbol { \nu } \in \mathbb { R } ^ { D }$ 表示第i个视频数据的D-维特征向量；除此之外，本文还使用使用相似度矩阵$S _ { i j }$ 表示视频数据之间的相似性，其中 $S _ { i j } = 1$ 表示 $\nu _ { i }$ 与 $\boldsymbol { \nu } _ { j }$ 相似，$S _ { i j } = 0$ 表示 $\nu _ { i }$ 与 $\boldsymbol { \nu } _ { j }$ 不相似。在视频检索系统中，相似度矩阵 $S _ { i j }$ 通常是用视频语义标签来构造的。本文的目标是利用深度哈希方法将具有语义标签信息的视频数据映射成哈希二值码表示，即 $b _ { i } \in \{ - 1 , 1 \} ^ { c }$ ，其中 $\vert c \vert$ 表示二值码的长度，并且保证学到的哈希二值码能够保留视频之间的相似性 $B = \{ b _ { i } \} _ { i = 1 } ^ { n }$ ，即相似视频所对应二值码之间的汉明距离尽量小，不相似视频所对应二值码之间的汉明距离尽量大，且相似视频之间的汉明距离比不相似视频之间的汉明距离更小。本文使用 $h ( \nu _ { i } )$ 来表示要学习的哈希函数，其中 $b _ { i } = h ( \nu _ { i } ) = [ h _ { 1 } ( \nu _ { i } ) , h _ { 2 } ( \nu _ { i } ) , . . . , h _ { c } ( \nu _ { i } ) ] ^ { T }$ 0

# 2.2方法模型

本方法的模型框架如图2所示。它是一个端到端的学习框架，主要由视频特征学习部分和哈希二值码学习部分组成，在训练过程中，各部分会相互反馈。

# 2.2.1视频特征学习部分

本文的模型在文献[11]所提出的3DCNN 模型的基础上做了一些改进，在模型的第一层卷积和第三层卷积之后增加了归一化操作，以及最后一层添加了一个哈希码学习层。请注意，图2中有两个3DCNN网络结构，这两个3DCNN网络具有相同的结构和相同的权重。也就是说，输入和损失函数都是基于成对对视频数据的。模型每一层的详细配置如表1所示。

![](images/37049a9fefebc9a5ed4194cf4c8aae4dce02a06b191ce60543a58cb8ae2f8080.jpg)  
图2深度视频哈希算法框架  
Fig.2Deep video hash algorithm framework

表1深度视频哈希方法框架参数设置  
Table1Parameter settings for deep video hash algorithm   

<html><body><table><tr><td>Layer</td><td>Configuration</td></tr><tr><td>Conv1</td><td>f. 64*3*3*3;st.1*1*1;pad. SAME;BN</td></tr><tr><td>Pooll</td><td>ksize:1*2*2;st.1*2*2;pad.SAME</td></tr><tr><td>Conv2</td><td>f.128*3*3*3;st.1*1*1;pad. SAME</td></tr><tr><td>Pool2</td><td>ksize:2*2*2;st.2*2*2;pad. SAME</td></tr><tr><td>Conv3_1</td><td>f.256*3*3*3;st.1*1*1;pad. SAME;BN</td></tr><tr><td>Conv3_2</td><td>f.256*3*3*3;st.1*1*1;pad. SAME</td></tr><tr><td>Pool3</td><td>ksize:2*2*2;st.2*2*2;pad. SAME</td></tr><tr><td>Conv4_1</td><td>f.512*3*3*3;st.1*1*1;pad. SAME</td></tr><tr><td>Conv4_2</td><td>f.512*3*3*3;st.1*1*1;pad.SAME</td></tr><tr><td>Pool4</td><td>ksize:2*2*2;st.2*2*2;pad. SAME</td></tr><tr><td>Conv5_1</td><td>f.512*3*3*3;st.1*1*1;pad. SAME</td></tr><tr><td>Conv5_2</td><td>f.512*3*3*3;st.1*1*1;pad. SAME</td></tr><tr><td>Pool5</td><td>ksize:2*2*2;st. 2*2*2;pad. SAME</td></tr><tr><td>Full6</td><td>4096</td></tr><tr><td>Full7</td><td>4096</td></tr><tr><td>Full8</td><td>Video hash code length c</td></tr></table></body></html>

更具体地，它包含8个卷积层(其中包含5次池化操作)和3个全连接层。每个卷积层描述在几个方面：f.表示卷积核的数量及其大小；st.表示卷积步长；pad.表示要添加到输入的像素数；BN 表示是否应用批量归一化操作。其中卷积核的大小均为 $3 ^ { * } 3 ^ { * } 3$ ，步长为 $1 ^ { * } 1 ^ { * } 1$ 。池化操作核的设置：除了第一层大小和步长均为 $1 ^ { * } 2 ^ { * } 2$ ，之后的大小和步长均为$2 ^ { * } 2 ^ { * } 2$ ，这样设置是为了不过早缩减时序上的长度。除哈希码学习层外，所有层的激活函数均为ReLU[9]，其收敛速度快且可以避免出现梯度消失问题，最后一层本文选择恒等函数作为激活函数。

# 2.2.2视频哈希码学习部分

本文使用 $f ( \nu _ { i , j } ; \theta ) \in \mathbb { R } ^ { c \times 1 }$ 表示学习到的视频特征，对应模型的输出，其中 $\theta$ 为网络模型的参数。基于3D卷积神经网络的视频哈希方法的目标函数定义如下：

$$
\begin{array} { l } { { \displaystyle \operatorname* { m i n } _ { B ^ { \nu _ { i } } , B ^ { \nu _ { j } } , \theta } J = - \sum _ { s _ { i j } \in S } ( S _ { i j } \Theta _ { i j } - \log ( 1 + e ^ { \Theta _ { i j } } ) ) } } \\ { { \displaystyle \quad \quad + \alpha ( \left\| B ^ { \nu _ { i } } - F _ { i } \right\| _ { F } ^ { 2 } + \left\| B ^ { \nu _ { j } } - F _ { j } \right\| _ { F } ^ { 2 } ) } } \\ { { \displaystyle \quad s . t . \quad B ^ { \nu _ { i } } } , B ^ { \nu _ { j } } \in \{ - 1 , + 1 \} ^ { c } }  \end{array}
$$

其中： $F _ { i , j } = f ( \nu _ { i , j } ; \theta ) , \Theta _ { i , j } = 0 . 5 ^ { * } F _ { i } ^ { T } { } ^ { * } F _ { j }$ ; $B ^ { \nu _ { i } } , B ^ { \nu _ { j } }$ 分别表示第ij个视频所对应的哈希码； $B ^ { \nu _ { i } } = s i g n ( F _ { i } )$ ； $B ^ { \nu _ { j } } = s i g n ( F _ { j } )$ ； $\alpha$ 为超参数。

目标函数的第一部分 $- \sum _ { i , j } ^ { n } ( S _ { i j } \Theta _ { i j } - \log ( 1 + e ^ { \Theta _ { i j } } ) )$ 是具有如下定义的相似性的负对数似然函数：

$$
p ( S _ { i j } \mid { F } _ { i } , { F } _ { j } ) = \left\{ \begin{array} { c c } { { \sigma ( \Theta _ { i j } ) } } & { { S _ { i j } = 1 } } \\ { { 1 - \sigma ( \Theta _ { i j } ) } } & { { S _ { i j } = 0 } } \end{array} \right.
$$

其中： $\sigma ( \Theta _ { i j } ) = \frac { 1 } { 1 + e ^ { - \Theta _ { i j } } }$ ，这一部分是用来保证视频特征与哈希码之间的相似性，即相似视频的哈希码尽量相似，不相似视频的哈希码尽量不同。

优化目标函数的第二部分 $\alpha ( \left\| B ^ { \nu _ { i } } - F _ { i } \right\| _ { F } ^ { 2 } + \left\| B ^ { \nu _ { j } } - F _ { j } \right\| _ { F } ^ { 2 } )$ ，因为 $F _ { i }$ 和 $F _ { j }$ 是视频离散哈希码的连续替代项，保持 $F _ { i }$ 和 $F _ { j }$ 的相似性即可以保持输入视频对的相似性。

# 2.3模型学习

本算法采用交替学习策略来学习 $B ^ { \nu _ { i } } , B ^ { \nu _ { j } } , \theta$ 。每次先学习一个参数，其他参数固定。算法1简要介绍了本方法模型的整个交替学习算法，并在本节的以下内容中详细介绍该算法的推导过程。

# 1）学习 $\theta$ ， $B ^ { \nu _ { i } } , B ^ { \nu _ { j } }$ 固定

当 $B ^ { \nu _ { i } } , B ^ { \nu _ { j } }$ 固定时，本文使用反向传播算法来学习网络模型的参数 $\theta$ 。根据现有的深度学习方法[9],本文利用随机梯度下降法反向传播梯度来学习 $\theta$ 。更具体地，在每次迭代中，本文从训练集采样一小部分的视频数据，然后基于采样数据执行本文的学习算法。特别地，对于每个采样点组，本文首先计算以下梯度：

$$
\begin{array} { c } { { { \displaystyle { \frac { \partial J } { \partial F _ { i } } } = 0 . 5 ^ { * } \sum _ { j = 1 } ^ { n } ( \sigma ( \Theta _ { i j } ) F _ { j } - S _ { i j } F _ { j } ) + 2 \alpha ( F _ { i } - B ^ { \nu _ { i } } ) } } } \\ { { { \displaystyle { \frac { \partial J } { \partial F _ { j } } } = 0 . 5 ^ { * } \sum _ { i = 1 } ^ { n } ( \sigma ( \Theta _ { i j } ) F _ { i } - S _ { i j } F _ { i } ) + 2 \alpha ( F _ { j } - B ^ { \nu _ { j } } ) } } } \end{array}
$$

$\frac { \partial J } { \partial F _ { i } } , \frac { \partial J } { \partial F _ { j } }$ $\frac { \hat { \sigma } J } { \hat { \sigma } \theta }$ 后利用反向传播算法即可更新参数 $\theta$ 。

# 2）学习 $B ^ { \nu _ { i } } , B ^ { \nu _ { j } }$ ， $\theta$ 固定

当参数 $\theta$ 固定时，式（1）将重新定义如下：

$$
\operatorname* { m a x } _ { B ^ { \nu _ { i } } , B ^ { \nu _ { j } } } t r [ \alpha ( ( B ^ { \nu _ { i } } ) ^ { T } F _ { i } + ( B ^ { \nu _ { j } } ) ^ { T } F _ { j } ) ]
$$

则哈希码的更新依赖于其连续替代项：

$$
B ^ { \nu _ { i } } = s i g n ( \alpha ( B ^ { \nu _ { i } } ) ^ { T } F _ { i } ) , B ^ { \nu _ { j } } = s i g n ( \alpha ( B ^ { \nu _ { j } } ) ^ { T } F _ { j } )
$$

算法1基于3D卷积神经网络的视频哈希算法输入：视频数据集 $\mathsf { v }$ 以及相似度矩阵S。

输出：模型的网络参数 $\theta$ ，以及输入的视频所对应的哈希二值码B。初始化：初始化模型网络参数 $\theta$ ，mini-batch s $\therefore z e = 1 0$ ，迭代iteration $\scriptstyle = 5 0 0 0$ 0

Repeat

for iteratio $\mathfrak { n } = 1 , 2 , 3 , \dotsc , 5 \theta \theta \theta$ do

从 $\mathsf { v }$ 中随机取样视频数据来构造一个mini-batch

for 每个在mini-batch 的采样视频组( $\cdot \ \nu _ { i } , \nu _ { j }$ )，

根据前向传播算法计算 $F _ { i , j } = f ( \nu _ { i , j } ; \theta )$ ，并根据式（2）计算对应的梯度并根据反向传播算法更新模型网络参数 $\theta$ 。

end for

根据式（4）得到输入视频所对应哈希二值码Until iteration $\scriptstyle = 5 0 0 0$

# 3 实验

在这一部分中，本文在常用的视频数据集上与其他最先进的方法进行了比较，验证了所提方法的有效性。本实验是在NvidiaTitanXGPU服务器上使用开源的深度学习框架Tensorflow 实现的。

# 3.1数据集和评价指标

UCF101数据集包括101个动作类别，13320个实际动作视频片段，UCF101中大多数视频的剪辑持续时间小于10s，在实际实验中本文选择了其中的9537个视频片段作为训练集，剩余3783个片段作为测试集。

对于基于哈希的检索方法，汉明距离排序和哈希查找是两种广泛使用的检索性能评估方法。在本实验对比中也采用这两种性能来评估本文方法和其他的baselines。汉明距离排序[34检索评估方法是将数据库中的视频与给定查询视频的汉明距离按从小到大的顺序进行排列，平均均值精度(meanaverage precision，mAP)[33]是衡量汉明距离排序准确性的常用指标。哈希查找是返回数据库中离查询视频在某个汉明半径以内的所有视频，而精确一召回率曲线是用来衡量哈希查找方法准确性的通用指标。

# 3.2实验参数设置

根据数据集中视频语义级标签来构建相似度矩阵。在训练阶段，网络的输入是由两个输入视频的帧集组成的帧内对；而在检索阶段，输入是单个视频的帧集。每个帧集包含从视频中随机选择的帧数k，在实验中，本文将k设为16，帧集中的每个帧被调整为 $1 1 2 \times 1 1 2$ 。为了评估不同长度的哈希码的性能，本文将二进制码的长度分别设为16、32和64。目标参数中 $\alpha$ 值设置为1。

# 3.3Baseline

本文将所提出的方法与目前最先进的视频检索baselines进行了比较，包括三种传统哈希方法：(fromimagehashing tovideo hashing,FIHTV)[1]、(video hashing via structure learning,VHSL)[3]和(submodular video hashing,SVH)[2]，以及三种深度哈希方法：(deep video hashing,DVH)[7]、(video hashingbased on appearance and attention featuresfusionviaDBN,DBNVH)[4]和(unsupervised deep video hashing withbalanced rotation,BRVH)[6]。在视频检索性能对比实验中，尽量按照对比论文中作者提出的参数设置复现方法。对于与传统视频哈希方法进行比较侧重于哈希学习方法上，而针对深度视频哈希学习的算法，性能比较的侧重点在视频特征学习部分。本文还将提出的方法与图像深度哈希方法进行对比：(deep supervised hashing for fast image retrieval,DSH) [31],(deep learning of binary hash codes for fast image retrieval,DLBHC)[30]等。这一部分实验中，将图像哈希码学习部分的方法实验代码合理改编并能够应用于视频的哈希码学习，主要用于对比所提出哈希码学习方法。

# 3.4实验结果与分析

# 3.4.1汉明排序

表2本文方法及其他方法在汉明排序上的最佳mAP

lable 2Best map of this method and other methods in Hamming   

<html><body><table><tr><td colspan="5">ranking</td></tr><tr><td colspan="2">任务</td><td colspan="3">UCF101</td></tr><tr><td rowspan="10">V->V</td><td>方法</td><td>16 bits</td><td>32 bits</td><td>64bits</td></tr><tr><td>FIHTV</td><td>0.3651</td><td>0.3725</td><td>0.4213</td></tr><tr><td>VHSL</td><td>0.3985</td><td>0.4202</td><td>0.4758</td></tr><tr><td>SVH</td><td>0.4564</td><td>0.4787</td><td>0.4886</td></tr><tr><td>UVH</td><td>0.5041</td><td>0.5472</td><td>0.5830</td></tr><tr><td>DBNVH</td><td>0.5612</td><td>0.6253</td><td>0.6441</td></tr><tr><td>BRVH</td><td>0.6525</td><td>0.6826</td><td>0.7189</td></tr><tr><td>DSH*</td><td>0.7274</td><td>0.7458</td><td>0.7963</td></tr><tr><td>DLBHC*</td><td>0.7141</td><td>0.7199</td><td>0.7418</td></tr><tr><td>本方法</td><td>0.7832</td><td>0.7914</td><td>0.8256</td></tr></table></body></html>

在表 2中展示了本文方法及其他方法在汉明排序上的mAP，“ $\mathrm { v { \mathrm { - } } \mathrm { > v } }$ 表示查询视频对数据库视频的检索。从表2中可知，相比于传统视频哈希方法，本文所采用的哈希码学习方法更为高效，检索性能提升明显。为了进一步验证基于3D CNN的视频哈希算法的有效性，本文利用在Sport-1M数据集上预先训练的深层网络来提取视频时空特征，与其他深度视频哈希算法学习视频特征的方式相比，3D卷积神经网络学习到视频特征更能有效地表示视频内容，融入到哈希学习的部分进行相互反馈能保持视频特征的相似性，因此能得到更高的检索精度。

![](images/7b243b9a0718713b8ca758b7ca9c615d555d1049f01ed33df87725094bf30148.jpg)  
图3查询结果(32 bit) Fig.3Query results (32 bit)

为了验证所提方法中目标函数的有效性，本文将所求得的深度视频哈希模型与其他视频哈希方法进行性能比较，如图3所示，将查询视频输入到模型中产生32bit的哈希二值码，并利用汉明距离对数据库中可能的相似视频进行排序。由于空间限制，本文只返回结果中前五个最相似的视频结果，其中，绿色对勾表示返回的结果与查询视频相似，反之红色叉号表示返回的结果与查询视频并不相似。可以观察到，本文所提出的方法得到了最好的效果，从而验证了所提的深度

视频哈希学习方法的高效性。

# 3.4.2哈希查找

在哈希查找协议中，本文可以计算出给定任何汉明半径的返回点的精确率和召回率，通过将汉明半径从0变到 $d$ 步长为1，就可以得到精确一召回率曲线。图4显示了本文方法和其他baselines方法在UCF101数据集上哈希码长度为16的精确一召回曲线。可以发现本文提出的方法获得最佳的性能。

![](images/2e350a01df5a229294d3897a0647b48e4695e93976f83d9c9b8b4f8ecb36eae7.jpg)  
图4精确一召回率曲线(16 bit) Fig.4Precision-recall rate curve (l6 bit)

# 4 结束语

本文通过3D卷积神经网络学习视频的时空特征，并将学习到的特征融入到哈希算法中，根据为视频相似度保持任务所设计的目标函数进行大量的训练能够得到紧凑并保持视频时空特征相似性的二值码，摆脱了传统视频特征手工设计的局限，大幅降低了大规模视频数据集特征存储的空间，因此在视频检索应用中，该方法既能够加快对相似视频的检索速度，又能提高检索精度。

# 参考文献：

[1]Li Weng,BartP.From image hashing to video hashing[C]//Proc of International Conference on Advances in Multimedia Modeling. [S.l.]:Springer-Verlag,2010: 662-668.   
[2]Cao Liangliang,Li Zhenguo,Mu Yadong,et al. Submodular video hashing:a unified framework towards video pooling and indexing [C]// Proc of ACM International Conference on Multimedia.2012:299-308.   
[3]Ye Guangnan,Liu Dong,Wang Jun,et al.Video Hashing via Structure Learning [C]// Proc of IEEE International Conference on Computer Vision.2014:2272-2279.   
[4]Sun Jiande,Liu Xiaocui,Wan Wenbo,et al.Video hashing based on appearance and attention features fusion via DBN [J]. Neurocomputing, 2016,213: 84-94.   
[5]Zhang Hanwang,Wang Meng,Hong Richang,et al.Play and rewind: optimizing binary representations of videos by self-supervised temporal hashing [C]//Proc of ACM on Multimedia Conference.2016:781-790.   
[6]Wu Gengshen,Liu Li,Guo Yuchen,et al. Unsupervised deep video hashing with balanced rotation [C]//Proc of the 26th International Joint Conference on Artificial Intelligence.2017: 3076-3082.   
[7]Liong $\mathrm { ~ v ~ E ~ }$ ，Lu Jiwen,Tan YP,et al.Deep video hashing[J].IEEE Trans on Multimedia,2017,19 (6):1209-1219.   
[8]Wang Wulin,Sun Jiande,Liu Ju.A memorability based method for video hashing [C]// Proc of IEEE International Conferenceon Communication Technology.2016:309-313.   
[9] Alex K,Ilya S,Hinton H G E. ImageNet classification with deep convolutional neural networks [Cl// Proc of International Conference on Neural Information Processing Systems.[S.1.]:Curran Associates Inc, 2012:1097-1105.   
[10] Tran D, Bourdev L,Fergus R,et al. Learning spatiotemporal features with 3d convolutional networks [C]// Proc of IEEE International Conference on Computer Vision. Piscataway,NJ: IEEE Press, 2015: 4489-4497.   
[11] Ji Shuiwang，Xu Wei,Yang Ming，et al.3D convolutional neural networks for human action recognition [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35(1): 221-231.   
[12] Li Ping, Shrivastava A,Moore J. Hashing algorithms for large-scale learning [J]. Nips,2011: 2672-2680.   
[13] ShrivastavaA,LiPing.Densifying onepermutation hashing via rotation for fast near neighbor search [C]// Proc of International Conference on International Conference on Machine Learning. 2014: I-557.   
[14] Shrivastava A,Li Ping.Asymmetric LSH(ALSH) for sublinear time Maximum Inner Product Search(MIPS）[C]// Proc of International Conference on Neural Information Processing Systems.[S.1.J:MIT Press,2014: 2321-2329.   
[15] Alexandr A,Piotr I,Thijs L,et al.Practical and optimal LSH for angular distance [J].Computer Science,2015.   
[16] Liu Wei, Wang Jun,Kumar S,et al. Hashing with Graphs [C]//Proc of International Conference on, Machine Learning. 2011:1-8.   
[17] Yair W,Antonio T,Rob F. Spectral hashing [C]// Proc of International Conference on Neural Information Processing Systems.[S.l.]:Curran Associates Inc,2008:1753-1760.   
[18] Gong Yunchao,Lazebnik S,Gordo A,et al. Iterative quantization: a Procrustean approach to learning binary codes for large-scale image retrieval.[J]. IEEE Trans on Pattern Analysis & Machine Intelligence, 2013,35 (12):2916-2929.   
[19]Jiang Qingyuan，Li Wujun.Scalable graph hashing with feature transformation [C]// Proc of International Conference on Artificial Intelligence.[S.l.]:AAAI Press,2015: 2248-2254.   
[20] Irie G,Li Zhengguo,Wu Xiaoming,et al.Locally linear hashing for extracting non-linear manifolds [C]// Proc of IEEE Conference on Computer Visionand Pattern Recognition.[S.l.]:IEEE Computer Society,2014:2123-2130.   
[21] Liu Wei, Wang Jun,Ji Rongrong,etal. Supervised hashing with kernels [C]// Proc of IEEE Computer Vision and Pattern Recognition. 2012: 2074-2081.   
[22] Karen S,Andrew Z. Very deep convolutional networks for large-scale image recognition [J]. Computer Science,2014.   
[23] Wang Jun, Kumar S, Chang SF. Semi-supervised hashing for scalable image retrieval [Cl//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2010: 3424-3431.   
[24] Jiang Qingyuan,Li Wujun. Deep cross-modal hashing [C]/ Proc of IEEE Computer Vision and Pattern Recognition.2017: 3270-3278.   
[25] Liong VE,Lu Jiwen,Tan YP,et al. Cross-modal deep variational hashing [Cl// Proc of IEEE International Conference on Computer Vision. 2017: 4097-4105.   
[26] Xia Rongkai,Pan Yan,Lai Hanjiang,et al. Supervised hashing for image retrieval via image representation learning [Cl// Proc of AAAI International Conference on Artificial Intelligence.2014.   
[27l Lai Haniiang.Pan Yan.Liu Ye.et al. Simultaneous feature learning and hash coding with deep neural networks [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Piscataway,NJ:IEEE Press,2015:3270-3278.   
[28] Liong VE,Lu Jiwen,Wang Gang,et al.Deep hashing for compact binary codes learning[C]//Proc of IEEE Computer Vision and Pattern Recognition. 2015:2475-2483.   
[29] Li Wujun,Wang Sheng, Kang Wangcheng.Feature learning based deep supervised hashing with pairwise labels [C]//Proc of International Joint Conference on Artificial Intelligence.[S.l.]:AAAI Press,2016: 1711-1717.   
[30]LinK,YangHF,Hsiao JH,etal.Deep learning ofbinary hash codes forfast image retrieval [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition Workshops．[S.l.]:IEEE Computer Society,2015: 27-35.   
[31]Liu Haomiao,Wang Ruiping,Shan Shiguang,et al.Deep supervised hashing for fast image retrieval [C]//Proc of IEEE Computer Vision and Pattern Recognition. 2016: 2064-2072.   
[32] Lin K,Lu Jiwen,Chen Chusong，et al.Learning compact binary descriptors with unsupervised deep neural networks [C]//Proc of IEEE Computer Vision and Pattern Recognition.2016:1183-1192.   
[33] Liu Wei,Mu Cun,Kumar S,et al.Discrete graph hashing[C]//Proc of International Conference on Neural Information Processing Systems. [S.l.]:MIT Press,2014:3419-3427.   
[34] Mohammad N,David JF, Salakhutdinov R.Hamming distance metric learning [C]//Advances in Neural Information Processing Systems. 2012:1061-1069.