# 面向WSI的乳腺病理亚型分类研究

陈金令，李洁，赵成明，刘鑫(西南石油大学 电气信息学院，成都 610599)

摘要：为实现乳腺病理WSI图像的精准分类，提出了一种基于混合连接的门控卷积神经网络分类方法。搭建了局部残差连接和全局稠密连接的混合模块，将压缩激活门控单元嵌入混合模块，建立了混合模块与过渡层交替连接的骨干网络。结合基于四叉树分割的图像数据增强方法训练模型，基于 BreastSet 临床数据集的实验结果得出，该方法的图像级、患者级和病理级准确率分别达到 $9 2 . 2 4 \%$ 、 $9 2 . 8 3 \%$ 和 $9 2 . 1 8 \%$ ，相较其他方法，准确率提高，参数量和计算量降低，更具有临床应用价值。

关键词：全切片图像；乳腺病理亚型分类；计算机辅助诊断；门控卷积网络；混合连接 中图分类号：TP391.5 doi:10.19734/j.issn.1001-3695.2022.03.0087

# Research of breast pathological subtype classification on WSI

Chen Jinling†,Li Jie, Zhao Chengming, Liu Xin (School ofElectrical Information,Southwest Petroleum University,Chengdu 610599,China

Abstract: For precise clasification of pathological breast WSI images,the study proposed the gatedconvolution network based on hybridconnection (HC-GCN),setupahybridblock of local residual connectionand global denseconnection,and through embedingthe Squeeze-Excitation-and-Gated (SEG) module intothehybrid block,establishedabackbone network for alternateconnection between the hybrid blockand the transition layer.Incombination with atraining model for image data enhancement based on quad-tre image segmentation method,the experimental results based on the BreastSetclinical data set showed $9 2 . 2 4 \%$ $9 2 . 8 3 \%$ and $9 2 . 1 8 \%$ of accuracy at the image level, patient level and pathology level respectively. Therefore,compared withothermethods,this method isofgreat clinical applicationvalueforimproved acuracyas wellas reduced number of parameters and amount of computation.

Keywords:WSI;breast pathological subtype clasification；computer auxiliarydiagnosis；gated convolutional network; hybrid connection

# 0 引言

乳腺癌是中国女性第一高发恶性肿瘤，发病率逐年升高，严重威胁中国女性的生命健康[1]。早期乳腺癌是可治愈性疾病，精准地诊断乳腺癌可以最大程度地提高患者的生存概率和生活质量。随着智能算法的发展、医学数据的积累和医疗水平的进步，各种智能算法也逐渐被运用到了医疗领域。传统的图像分类算法由特征提取、特征编码、分类器设计三个步骤组成[2]，人工提取病理特征的过程通常需要占用大量的计算资源，难以实用。卷积神经网络(convolutionalneuralnetworks,CNN)具有良好的自动特征建模能力[3]。目前，乳腺病理图像分类领域广泛使用 CNN 构建深度学习(deeplearning,DL)模型[4]。

乳腺组织病理图像在临床诊断时发挥着重大作用，乳腺癌病理学图像数据集(breast cancer histopathological database.BreakHis)是已做切分处理的大型公共数据集，目前已有许多研究者围绕其进行病理分类研究。例如，Han[5]等人利用深度学习模型基础层构建CSDCNN模型，在多分类任务中获得的平均分类准确率达到 $9 3 . 3 \%$ 。Bardou[等人采用基于袋模型(Bagofwords)、局部约束线性编码器(Localityconstrainedlinearcoding)和支持向量机(SupportVectorMachine,SVM)分类器的手工特征提取方法，在进行二分类和多分类任务时获得的准确率分别达到 $9 6 . 1 5 \%$ 和 $9 3 . 3 1 \%$

第二种是基于数据增强和卷积神经网络设计的深度学习分类方法，二分类和多分类任务获得的准确率分别达到 $9 8 . 3 3 \%$ 和 $8 8 . 2 3 \%$ 。程年[7]等人运用VGG16和InceptionV3两个深度学习模型，结合迁移学习和数据增强等方法，进行良恶性二分类获得的准确率分别为 $9 4 . 4 3 \%$ 和 $8 2 . 6 4 \%$ ，进行病理亚型八分类获得的准确率分别为 $8 2 . 9 7 \%$ 和 $5 8 . 7 8 \%$ 。Nguyen[8]等人结合调整大小的原始图像等方法建立CNN模型，对多种乳腺癌类型进行自动分类，获得的准确率可达 $7 3 . 6 8 \%$ 。 $\mathbf { M } \mathbf { t } ^ { \left[ 9 \right] }$ 等人利用图像增强技术处理每个图像数据，通过注意模块对图像的重要关键区域进行选择和处理，建立BreastNet了模型，实验显示良恶性二分类准确率最高达到 $9 8 . 8 0 \%$ 。李雨倩[10]使用深度学习方法作为特征提取器，根据乳腺图像特征构建随机森林模型，该模型进行多分类的准确率达到$9 2 . 5 \%$ 。Jiang[]等人建立了基于小型SE-ResNet 模块的卷积神经网络模型，实验显示良恶性二分类和病理亚型八分类的准确率分别为 $9 8 . 8 7 \% { \sim } 9 9 . 3 4 \%$ 和 $9 0 . 6 6 \% { \sim } 9 3 . 8 1 \%$ 。刘巧利[12]等人提出了基于DenseNet网络的乳腺癌分类模型，在二分类任务中得出的识别准确率平均值达到了 $9 9 . 2 \%$ 。刘靖雯[13]等人提出了基于Inception-ResNet-V2的乳腺癌病理图像识别方法，获得的八分类准确率达到 $7 9 . 7 \%$ 。明涛[14]等人结合注意力机制算法，提出基于深度学习的多尺度通道重校准模型该模型在良恶二分类实验中展示的准确率达到 $8 8 . 8 7 \%$ 。于凌涛[15]等人提出了一种基于卷积神经网络的多任务模型，模型在二分类任务上达到了 $9 8 . 5 5 \% \sim 9 9 . 5 2 \%$ 的分类准确率，在多分类上达到了 $9 2 . 2 6 \% \sim 9 4 . 8 5 \%$ 的分类准确率。赵晓平[16]等人基于稠密卷积神经网络、注意力机制和焦点损失函数提出了乳腺癌组织病理图像的多分类模型，在BreakHis数据集上进行验证性实验，得出良恶性二分类识别准确率达到$9 9 . 1 \%$ ，乳腺病理亚型八分类的识别准确率达到了 $9 5 . 5 \%$ 。

在对乳腺病理类型进行临床诊断过程中，大多是直接对乳腺病理WSI(whole slide image,WSI)图像进行直接观察分析，因此，对乳腺病理WSI图像数据进行研究更有实用价值。Cruz-Roa[17等人提出了对于全切片乳腺病理图像中浸润性导管癌组织区的自动检测和视觉分析的深度学习方法，在 49 张WSI图像上获得了 $8 4 . 2 3 \%$ 的均衡准确度。Wang[18]等人设计了转移乳腺癌检测器对哨落淋巴结的WSI图像进行自动检测，获得的图像分类AUC达到0.995，肿瘤定位得分达到0.733。Gecer[19]等人建立四个全卷积网络组成的深度学习模型对乳腺WSI图像进行五分类，得出的预测效果与45位病理学家诊断结果有 $5 5 \%$ 的相似度。

为实现对乳腺全切片图像病理亚型的精准高效分类，本文利用来自绵阳市中心医院的乳腺病理WSI图像，建立BreastSet数据集，并提出了基于混合连接的门控卷积网络模型(gated convolution network based onhybrid connection，HC-GCN)对其进行分类研究。模型采用混合连接的组织架构，通过跨层的“短路连接”(shortcuts，skip connection)加速向前传播信息，降低稠密连接导致的庞大冗余性；利用结合了注意力机制的门控结构对特征信息进行有效融合，使得病理类别判别的准确率提高，分类模型的计算复杂度减小。此外本文针对混合模块特性使用Tanh'函数作为激活函数，避免了ReLU函数引起的神经元“坏死”后无法训练问题，从网络结构和激活函数的角度提升了模型性能。

# 1 基于混合连接的门控卷积网络

# 1.1混合连接

$\mathrm { H e } ^ { [ 2 0 ] }$ 等人提出的残差连接为深度学习突破了发展瓶颈，通过跨层的数据通道结构训练出有效的深层神经网络，建立ResNet模型。但实际操作中，ResNet的网络层数通常较多，所以尽管其模型内部具有参数共享机制，但参数量和计算量仍然较大。另外，残差模块堆叠过程中，早期的特征信息被自然地丢失，太多的残差聚合会导致特征信息损失过多，最终造成无法弥补的误差。DenseNet[21]是由HuangG等人提出的以稠密连接为基础结构的网络模型，与ResNet同样采用跨层连接的模式，不同的是残差块的输出是输出和输入相加，稠密块的输出是输出和输入在通道维上相联结。DenseNet减轻了梯度消失问题，促进了特征信息的有效传递和利用，保留了更多的特征信息，对网络深度的要求较低，且每层网络的通道数明显较少，减小了模型的参数量，但稠密连接网络内每一层的特征信息都是前面所有层的聚合，这种做法虽然保护了特征信息的利用，但也导致了模型重复提取冗余信息，使得模型的冗余性极高，计算量居高不下。

为了提高乳腺癌的检测准确率，同时减小算法复杂度和运算时间，本文提出局部的残差连接与全局的稠密连接相聚合的混合连接。混合连接模块的基础结构如图1所示。

0n SEG1 SEG2

图1表示由两个SEG块进行混合连接组成的混合模块，每一个混合模块都由2个或以上的 SEG 块组成。其中，实弧线表示稠密连接，虚弧线表示残差连接，“ $^ +$ ”表示两个输入的相加，“[,]”表示通道维上的联结， $\textcircled{1}$ 和 $\textcircled{2}$ 分别表示SEG块中的压缩单元与激活单元。

混合模块的最终目的是代替原本DenseNet 网络中的稠密块，实现网络模型的混合连接，提高乳腺病理图像病理分类模型的特征提取能力。

# 1.2压缩激活门控单元

图1中的SEG1和SEG2表示专为混合模块搭建的特殊结构，功能和原理与瓶颈层(bottlenecklayer)类似，称为SEG块。SEG块的具体结构如图2所示。

图2中， ${ } _ { H , W , C }$ 分别表示特征图的高、宽和通道数。

如图2所示，在SEG模块中，首先，利用卷积和组卷积结构对输入特征图像进行压缩，控制特征维度、减小模型的通道数，进而减小模型所需的参数量和计算量。

![](images/0fdb8ad3917f5ccd0f40c03bf6802c6dfb716826a817fc99d01462b54b5081a9.jpg)  
图1混合模块Fig.1Hybrid block  
图2压缩激活门控单元  
Fig.2Squeeze -Excitation-and-Gated module (SEG)

其次，运用引入了注意力机制的遗忘门和更新门结构对特征信息进行有效处理，遗忘门使用一个全局上下文模型(globalcontextmodel)用于计算每个位置的空间注意力特征权重，又加入了Sigmoid函数对每个通道进行加权衰减，有效地减小模型所需的计算量；更新门使用Softmax 函数起到相互比较的作用，选出了最应被注意的特征信息与原信息叠加，促进模型对新特征的挖掘和应用，能够在一定程度上提高模型的分类准确率。同时，更新门和遗忘门的结构既能够像自注意力机制模型一样有效地对全局上下文进行建模，又能够有效地节省计算资源。下面将针对 SEG 块中的压缩与激活、遗忘门和更新门三种结构逐一进行介绍。

# 1.2.1压缩与激活

压缩单元的操作步骤主要分为两步：首先，利用 $1 \times 1$ 的标准卷积对输入特征图进行压缩，目的是减小通道数，处理后的通道数将由 $\tilde { c }$ 减小为 $\alpha c$ ，其中， $\alpha$ 表示通道的宽度乘数，且 $\scriptstyle 0 < \alpha < 1$ ；然后使用组数为 $g$ ，卷积内核为 $3 \times 3$ 的组卷积对特征图进一步压缩，通过设置步长(stride)来实现模型的降采样操作，以减小特征图的高、宽和通道数。两个压缩操作的根本目的都是降低模型的参数量和计算量。

特征信息经过压缩后进入激活单元，运用 $3 \times 3$ 的深度可分离卷积(dethwiseconvolution)进行激活和数据填充。乳腺病理图像中隐藏的信息相较于常见的分类图像(例如猫狗、鲜花等)隐藏的信息要多，要提取更多的信息，在卷积层需要更多的卷积核，而卷积核的增大会带来计算规模的增大。在输入输出的特征图维度相同情况下，深度可分离卷积所需的输入通道很少、参数和计算的成本极低，参数量和计算量相比与标准卷积显著较少，用深度可分离卷积进行激活和数据填充可以在不影响效率的情况下提升模型性能。

1.2.2遗忘门

图2中的最左边的连接线和图1中的虚线同样表示为SEG块中的残差连接，与普通残差连接不同的是，原来的残差连接是通道信息与残差连接信息的简单相加，此处由于同时使用了残差连接和稠密连接，所以为了高效利用在通道中重复传递的特征信息，在残差连接上嵌入了一个引入了注意力机制的遗忘门对重复利用的特征信息进行衰减过滤。

遗忘门为了满足对重用特征的衰减，不仅要保证特征信息的有效流通，而且需将每个通道权重的最终输出映射控制在(0,1)之间。所以，遗忘门在引用了空间注意力和通道注意力机制的同时，使用了Sigmoid函数进行最后的衰减工作。

遗忘门的结构如图3所示，操作步骤主要分为以下五步：

IX':HxWxC1×1卷积S' : HxW x1Softmax函数$S ^ { \prime } : H \times W \times 1$ （20  
全局注意力池化$z ^ { f } : 1 \times 1 \times C$ （20全连接层一 $\mathbf { l } \times \mathbf { l } \times { C } / r ^ { f }$   
标准化+激活函数1x1xC/rf全连接层1x1xCSigmoid函数J:1x1xC

Stepl：将特征图 $X ^ { \prime } \in \mathbb { R } ^ { H \times W \times C }$ 输入 $1 \times 1$ 的标准卷积，输出通道维数减小的空间注意力特征 $\tilde { S } ^ { \prime } \in \mathbb { R } ^ { H \times W \times 1 }$ ：

Step2：利用Softmax函数对空间注意力特征图进行归一化得到新的空间注意力特征 $S ^ { \prime } \in \mathbb { R } ^ { H \times W \times 1 }$ ，其中每个元素可用如下公式表示：

$$
S _ { i , j , 1 } ^ { \prime } = e ^ { \wedge } \tilde { S } _ { i , j , 1 } ^ { \prime } \Big / { \sum _ { x = 1 } ^ { H } \sum _ { y = 1 } ^ { w } e ^ { \wedge } \tilde { S } _ { i , j , 1 } ^ { \prime } }
$$

其中， $i = 1 , . . . , H$ ， $j = 1 , . . . , W$ 。

Step3：特征图 $\boldsymbol { S ^ { \prime } }$ 经过全局注意力池化层(globalattentionpooling)，生成缩小的全局特征图 $z ^ { f } \in \mathbb { R } ^ { \mathrm { | x l \times C } }$ ，第 $\mid c \mid$ 通道全局特征图的表示公式如下：

$$
\begin{array} { r } { z _ { c } ^ { f } = \sum _ { x = 1 } ^ { H } \sum _ { y = 1 } ^ { W } X _ { x , y , c } ^ { \prime } { ^ { * } S _ { x , y , c } ^ { \prime } } } \end{array}
$$

其中， $*$ 表示元素乘法。

Step4：全局注意力特征图 $z ^ { f }$ 经过两个连续的全连接层。因为网络在训练过程中，上一层训练参数的更新会使后一层输入数据分布也发生变化，两个全连接层之间加入了一个标准化 $+$ 激活函数层(BN+Tanh)进行缓冲，作用是在两个全连接层中进行一次批量归一化处理操作。

Step5：利用Sigmoid函数进行最后的衰减操作。

遗忘门最终的输出特征图表示公式如下：

$$
f = \sigma ( W _ { 2 } ^ { f } ( \mathrm { T a n h } ^ { \prime } ( B N ( W _ { 1 } ^ { f } z ^ { f } | b _ { 1 } ^ { f } ) ) ) \vert b _ { 2 } ^ { f } )
$$

其中， $f$ 表示遗忘门的最终输出特征图， $W _ { i } ^ { f } , b _ { i } ^ { f }$ 分别表示遗忘门中第 $i$ 个全连接层的权重和偏置值； $\sigma$ 表示 Sigmoid 函数； $r ^ { f }$ 表示遗忘门设置的瓶颈比率数；并且 $f \in \mathbb { R } ^ { \mathrm { { 1 \times 1 \times C } } }$ ，$W _ { 1 } ^ { f } \in \mathbb { R } ^ { C \times C / r ^ { f } }$ ， $W _ { 2 } ^ { f } \in \mathbb { R } ^ { C / r ^ { f } \times C }$ ， $b _ { 1 } ^ { f } \in \mathbb { R } ^ { C / r ^ { f } }$ ， $b _ { 2 } ^ { f } \in \mathbb { R } ^ { C }$ 。

1.2.3更新门

更新门的设立是为了更有效地处理 $3 \times 3$ 深度可分离卷积得到的新特征，具体结构如图4所示。

更新门与遗忘门的差别在于遗忘门的目的是对信息进行衰减，而更新门的目的是促进特征信息的挖掘和使用。二者在结构上也有明显的差异，更新门中没有使用Sigmoid函数对特征信息衰减，并且它的最终输出和全局注意力池化层之间有一个简单相加操作。

X:HxWxC1×1卷积S3 : H xW x1Softmax函数S : H xW x1全局注意力池化2z3x :1x1xC全连接层z³ :1x1x Ch':1x1xC|r"标准化+激活函数h:1x1xC/r"3 :1x1xC 全连接层v:1x1xC

![](images/7f1a504d41ed487ac002c0c753a3890e46b49cc57cf3b16d0e5fe7a2804bf05d.jpg)  
图3遗忘门  
Fig.3Forget gate   
图4更新门  
Fig.4Update gate   
图5ReLU、Sigmoid 和Tanh三种常用激活函数的函数图像Fig.5The function images of relu,Sigmoid and Tanh

令 $h$ 表示标准化 $\cdot ^ { + }$ 激活函数层后输出的隐藏特征图，其中 $h \in \mathbb { R } ^ { 1 \times 1 \times C / r ^ { f } }$ ， $r ^ { u }$ 表示更新门设置的瓶颈比率数。隐藏特征图的具体公式表示如下：

$$
h = \mathrm { T a n h ^ { \prime } } ( B N ( W ( z ^ { 3 \times 3 } ) ) + b )
$$

其中， $W , b$ 分别表示第一个全连接层的权重和偏置值，且$W \in \mathbb { R } ^ { C \times C / r ^ { u } } , b \in \mathbb { R } ^ { C / r ^ { u } }$

隐藏特征图 $\boldsymbol { h }$ 在经过第二个全连接层后生成通道注意力特征图 $\tilde { u } ^ { 3 \times 3 }$ ，公式为

$$
\tilde { u } ^ { 3 \times 3 } = W ^ { 3 \times 3 } h + b ^ { 3 \times 3 }
$$

其中， $W ^ { 3 \times 3 } , b ^ { 3 \times 3 }$ 分别表示第二个全连接层的权重和偏置值，且 $W ^ { 3 \times 3 } \in \mathbb { R } ^ { C / r ^ { u } \times C } , b ^ { 3 \times 3 } \in \mathbb { R } ^ { C }$ 。

第二个全连接层的输出 $\tilde { u } ^ { 3 \times 3 }$ 与全局注意力池化层的输出$z ^ { 3 \times 3 }$ 相加得到更新门的最终输出 $\nu$ ， $\nu \in \mathbb { R } ^ { \mathrm { { \mathrm { { k l } } \times \mathrm { { l } } \times C } } }$ 口

本质上，更新门和遗忘门的作用是将压缩单元形成的紧凑特征图 $X ^ { \prime }$ 看做是重用的旧特征，将 $3 \times 3$ 的深度可分离卷积形成的输出 $X ^ { 3 \times 3 }$ 看做是提取的新特征，最后巧妙地提取和聚合新旧特征构成最终的输出 ${ \cal O } \in \mathbb { R } ^ { H \times W \times C }$ 。这种处理方法不仅能够在节省参数量和计算量的同时促进特征的有效重用，而且能够增强对更多特征信息的挖掘能力。

# 1.2.4激活函数的选择

激活函数能够为神经网络训练过程加入非线性因素，提高模型的特征表达能力。

图5展示了ReLU、Sigmoid和Tanh三种常用激活函数的函数图像。

ReLU函数具有符合神经网络编码特点、克服梯度下降问题、提高计算效率等优点。但从图5中的ReLU函数曲线可以看出，ReLU函数有两个致命的缺点。一是当输入神经元 $x < 0$ 时，ReLU的梯度被置零，这很有可能导致 $x < 0$ 时神经元“坏死”，输入数据无法激活。二是ReLU函数的输出恒为正值，没有负值。因此，ReLU会在很大程度上破坏模型的特征表示能力，导致模型无法训练出有效的特征信息。

另外，ReLU函数不会控制数值的幅度，在深层网络中数值幅度变化过大可能导致模型无法训练。Sigmoid函数和Tanh函数能够有效解决神经元“坏死”的问题，保护 $x < 0$ 时的特征信息，并且控制数值的幅度。

由图5可以看出，采用Sigmoid函数作为激活函数时，如果当前输入参数 $( \omega _ { \mathrm { 0 } } , \omega _ { \mathrm { i } } )$ 的最佳优化方向是 $( + d _ { 0 } , - d _ { 1 } )$ ，那么因为Sigmoid函数不以0为中心，并且输出值恒为正，所以模型将无法实现最快的参数更新，而是走z字形逼近最优解。因此，使用以0为中心，取值范围为[-1,1]的Tanh函数可以让模型的收敛速度更快。

另外，Tanh 函数的梯度消失问题比 Sigmoid 函数要轻。但Tanh在[-1,1]区间上的取值近似线性，这可能会导致提取的图像特征有一定的误差，降低特征学习的准确度。

为了解决 Tanh 函数导致的梯度消失问题和分类误差提高的问题，本文选择Tanh'作为HC-GCN的激活函数，Tanh的具体公式如下：

$$
\mathrm { T a n h ^ { \prime } = T a n h } ( x ) \cdot \mathrm { s i g m o i d } ( x )
$$

选用Tanh'函数作为激活函数，既可以有效解决“神经元”坏死问题、保护特征信息、控制数值幅度，还能够消除近似线性处理导致的分类误差，获得更好的模型性能和分类结果。另外，混合连接显著加强了梯度的反向传播，可以极大程度地弥补激活函数可能导致的梯度消失的问题。

# 1.3模型整体架构

HC-GCN的整体架构与DenseNet 相似，不同的是DenseNet 的主要构建模块是稠密块(dense block)[22]，而HC-GCN 的主要构建模块是混合模块(hybrid block)。混合模块和稠密块的作用都是定义模型内部瓶颈块的输入输出联结模式

HC-GCN模型将需要进行病理类别分类的乳腺病理图像作为网络的输入。首先，输入图像经过一个由 $3 \times 3$ 卷积层、批量标准化(BatchNorm，BN)和ReLU 函数组成的特征块做标准化处理。然后，传入混合模块与过渡层交互连接的骨干网络提取特征信息，过渡层的主要作用是控制通道数。最后，提取到的特征信息进入全局平均池化(global averagePooling，GAP)层、全连接层(fullyconnectedlayer)和Softmax分类器，完成最后的分类操作。图6中展示的HC-GCN的骨干网络是由3个混合模块与2个过渡层交互连接构成的，其中每个混合模块内部均有多个压缩激活门控单元(Squeeze-Excitation-Gatedmodule，SEG)以稠密连接的模式构成。

Input Stem Transition1 Transition2 GAP FC特征块 过渡层 过渡层 平均池化 全连接层 Softmax混合模块1 混合模块2 混合模块3

在实际应用中，为了获得更好的乳腺病理图像的病理类别分类效果，可以通过改变网络中的混合模块、SEG块的数量和调试超参数等方法来构建不同结构的HC-GCN。

# 2 数据集来源及处理

# 2.1数据集来源

本文采用的图像数据是由绵阳市中心医院提供的乳腺病理WSI图像，源文件为KFB格式，可利用K-Viewer软件对其进行查看和处理。图7展示了BreastSet数据集中的部分样本。

将原始数据导出格式为png 的RGB三通道图像后可形成分类数据集，数据集包含了来自患不同乳腺癌病症患者的3498张的WSI病理图像，分类标签共有八种：伴有髓样特征乳腺癌(medullary breast carinoma，MBC)、非特殊类型浸润性癌(non-special type invasive breast carcinoma，NST)、浸润性大汗腺癌(apocrine carinoma，AC)、浸润性微乳头状癌(invasive micropapillarycarinoma，IMPC)、浸润性小叶癌(invasive lobular carcinoma，ILC)、黏液癌(mucoid carinoma,MC)、实性乳头状乳腺癌伴浸润(solid papillary caricoma,SPC)、小管癌(tubular carcinoma，TC)。在此将该数据集命名为乳腺病理图像分类数据集(breastpathological imageclassification data set，BreastSet)。表1介绍了BreastSet数据集的数据结构。

![](images/1b50dfff29ad3980e19b8ed8f7ab8f1177c7fa3c2429e0132c472b6c43cfbb31.jpg)  
图7 BreastSet 样本数据Fig. 7 BreastSet sample data表1BreastSet 的数据结构Tab.1Breastset data structure

<html><body><table><tr><td>病理类别</td><td>总计</td><td>训练集</td><td>验证集</td><td>测试集</td></tr><tr><td>MBC</td><td>407</td><td>325</td><td>41</td><td>41</td></tr><tr><td>NST</td><td>519</td><td>415</td><td>152</td><td>152</td></tr><tr><td>AC</td><td>133</td><td>107</td><td>13</td><td>13</td></tr><tr><td>IMPC</td><td>597</td><td>477</td><td>60</td><td>60</td></tr><tr><td>ILC</td><td>757</td><td>607</td><td>75</td><td>75</td></tr><tr><td>MC</td><td>464</td><td>372</td><td>46</td><td>46</td></tr><tr><td>SPC</td><td>496</td><td>398</td><td>49</td><td>49</td></tr><tr><td>TC</td><td>125</td><td>101</td><td>12</td><td>12</td></tr><tr><td>总计</td><td>3498</td><td>2802</td><td>348</td><td>348</td></tr></table></body></html>

# 2.2数据增强

WSI图像的尺寸和内存占用较大，因此BreastSet数据集中的图像数据难以被计算机直接识别与应用。为了保证图像数据的精准读取，提高模型的特征表达能力，可对数据集中的数据做数据增强处理。除改变尺寸等基础的数据增强方法以外，还可使用如图8所示的基于四叉树分割的图像数据增强方法[23]。

![](images/b776b325d2403678503e15ed5362a7786c850d8ee2d386bd3f97ba6df534fb5a.jpg)  
图6 HC-GCN整体架构示意图  
Fig.6Overall architecture schematic of HC-GCN   
图8 四叉树图像分割方法  
Fig.8Quad-tree image segmentation method

四叉树是一种树状数据结构，在每一个节点上会有四个子区块，常应用于二维空间数据的分析与分类。它将数据区分成为四个象限。数据范围可以是方形或矩形或其他任意形状。四叉树有一个连续的结构组成，在每一层，将上一层的输入图像均等分成4个部分。在分割之后，每块子图像都被认为与原始图像具有相同的类标签。

# 2.3融合算法

由于采用了基于四叉树的图像分割方法，一张图片被分割成多个子图像块，每个图像块在经过模型计算可能产生不同的分类结果，故需要融合算法将每个图像块的分类结果有效地整合起来，常用的融合算法有和规则、乘积规则、最大值规则、多数投票规则等。和规则、乘积规则和最大值规则算法的具体计算公式[24]如下：

和规则： （204号 $\phi = \arg \operatorname* { m a x } _ { k = 1 } \sum _ { i = 1 } ^ { N } p _ { i } ( k )$

乘积规则： $\phi = \arg \operatorname* { m a x } _ { k = 1 } \prod _ { i = 1 } ^ { K } p _ { i } ( k )$

最大值规则： $\phi = \arg \operatorname* { m a x } _ { k = 1 } \operatorname* { m a x } _ { i = 1 } ^ { K } p _ { i } ( k )$

其中， $p _ { i } ( k )$ 表示为1张图片的第 $i$ 个子图像块被模型分为类的概率值； $K$ 表示病理类别总数； $N$ 表示1张图片的切分块总数。本文采用的是多种融合算法相结合的整合方法。图9展示了1张病例图片的完整融合分类结果过程，最后输出的分类结果由三种融合规则得出的分类结果投票决定。

![](images/34bfec333e609c5237274dd26d2f7cfe6a0528090e9bde12cea591653ba9d993.jpg)  
图9 融合分类结果示意图  
Fig.9Schematic diagram of fusion classification results

# 2.4评价标准

记录模型训练和测试的结果，是进一步完善模型和评价模型质量的依据[25]。为了评价模型在面向WSI的乳腺病理亚型分类任务上的适用性，本文计算了分类准确率(accuracy)、模型参数(params)、计算浮点数(FLOPs)、精确率(查准率，precision，P)、召回率(查全率recall,R)和F1评分(F1scores,F1)等参数进行评估。

在医学领域，计算机辅助诊断模型的分类准确率包含图像级、患者级和病理级三种。图像级的准确率(image-levelaccuracy，IA)指的是被正确分类的图像数量占样本总数量的比率，患者级的准确率(patient-level accuracy，PA)指的是每位患者对应的乳腺病理图像分类准确率平均值，病理级的准确率(pathological-levelaccuracy，PLA)指的是多分类情况下的每种病理类型对应的乳腺病理图像分类准确率平均值。

精确率、召回率、F1评分是衡量模型性能的重要指标。精确率是被诊断为阳性的患者是真阳性的概率，召回率是真阳性患者被诊断为阳性的概率。模型具有较高的精准率可以减少误诊率，防止正常人被错误治疗和医疗资源的浪费；模型具有较高的查全率可以减少漏诊率，防止患者错过最佳治疗时间。

F1分数(F1Score)是统计学中用来衡量模型精确度的重要指标[25]，也是模型精准率和召回率的一种调和平均。具体计算公式见式(5)\~(7)。

$$
\mathrm { p r e c i s i o n } = { \frac { T P } { T P + F P } }
$$

$$
\mathrm { r e c a l l } = { \frac { T P } { T P + F N } }
$$

$$
F 1 = 2 \times \frac { \mathrm { p r e c i s i o n \times r e c a l l } } { \mathrm { p r e c i s i o n + r e c a l l } }
$$

其中，TP 表示真阳性数量，FP 表示假阳性数量，FN 表示假阴性数量。

在对病理进行多分类的情况下，计算模型的精确率、召回率和F1评分时需要计算相应的宏平均值(Macro)和微平均值(Micro)。宏平均值是指分别计算每个病理类别的精确率、召回率和F1评分的平均值，平等地对待每个类别，因此容易受到样本数量较少的类别的影响。微平均值是指不区分类别，整体计算精确率、召回率和F1评分，平等的对待每个样本，因此容易受到样本数量较多的类别的影响。根据计算原理，Micro-P，Micro-R和Micro-F1在数值上与IA相等。

# 3 实验

# 3.1实验环境

实验用的硬件配置和运行环境如表2所示。

Tab.2Lab environment   

<html><body><table><tr><td>环境</td><td>名称及对应版本</td></tr><tr><td>操作系统</td><td>Ubuntu 18.04.2</td></tr><tr><td>编程语言</td><td>Python 3.6.13</td></tr><tr><td>CPU</td><td>Intel Core i7-10870H(2.20GHz)</td></tr><tr><td>GPU</td><td>NVDIAGeForceGTX1660Ti</td></tr><tr><td>框架</td><td>PyTorch1.6,Torchvision0.7.0</td></tr></table></body></html>

# 3.2模型架构与超参数设置

为了获得更好的模型分类效果，经过多轮的测试和调整混合模块中的 SEG 块的数量和增长率(growth rate)等结构和参数设置，构建了一个由3个混合模块，每个混合模块包含 8个SEG块的HC-GCN模型。表3展示了模型的具体结构设置。

表2实验环境  
表3HC-GCN架构配置  
Tab.3HC-GCNArchitecture for breasthis Classification   

<html><body><table><tr><td>Stage</td><td>HC-GCN2</td><td>IR</td></tr><tr><td>Stem</td><td>[3×3 Conv-BN-ReLU]×3</td><td>224×224</td></tr><tr><td></td><td>3×3 max pool</td><td>112×112</td></tr><tr><td>HybridBlock1</td><td>SEG×8，k=24</td><td>56×56</td></tr><tr><td>transition1</td><td>SEG×1</td><td>56×56</td></tr><tr><td>Hybrid Block2</td><td>SEG×8，k=36</td><td>28×28</td></tr><tr><td>transition2</td><td>SEG×1</td><td>28×28</td></tr><tr><td>Hybrid Block3</td><td>SEG×8，k=64</td><td>14×14</td></tr><tr><td>Classification</td><td>global average pool FC，Softmax</td><td>1×1 1</td></tr></table></body></html>

另外，模型中几个比较重要的超参数设定如下：批样本大小(batchsize)为16,epoch为10o，学习率(learningrate)为0.1，过渡层和混合模块之间的压缩因子 $\theta$ 为0.5；SEG 块中$3 \times 3$ 组卷积的组数 $g$ 为，宽度乘数 $\alpha$ 为4，更新门和遗忘门的缩减比( $r ^ { u } = r ^ { f }$ )为2，步长 $s$ 为1；过渡层中设置 $g$ 为1,$r ^ { u } = r ^ { f }$ 为2， $\alpha$ 为1.5，步长 $s$ 为2；深度可分离卷积核大小(kernel size)为2。

# 3.3 训练与测试

如表1所示，实验前按照8：1：1的比例分配训练集、验证集和测试集。本文对乳腺病理图像数据增强的第0层和第1层进行了训练，即训练时分为直接使用原始数据进行训练和对图像进行四切分后训练两种模式，四切分时每张原始图像被切割成4块进行训练和投票融合。

图10是HC-GCN基于BreastSet数据集得出的训练集损失曲线和验证集图像级准确率曲线，图中向上弯曲的实线曲线表示对原数据分类的验证集图像级准确率曲线(Acc0)，向下弯曲的实线曲线表示对原数据分类的训练集损失曲线(LossO)；向上弯曲的点状曲线表示四切分训练模式下得出的验证集图像级准确率曲线(Acc1)，向下弯曲的点状曲线表示四切分训练模式下得出的训练集损失曲线(Loss1)。

![](images/066ef043611c61cd301876192df8c8dc16bc501925a38cc9d69295b9edfb6a26.jpg)  
图10训练集损失曲线和验证集图像级准确率曲线 Fig.l0Image-level Accuracy of Verification and Loss of Trainin{

由图10可知，HC-GCN在原数据集和四切分模式上进行训练时都能获得较好的准确率结果和较少的损失，说明本文建立的模型具有一定的准确性和科学性；模型的训练集和验证集损失曲线显示在BreastSet数据集上的训练过程较平稳，说明模型具有稳定性；当epoch大于等于40时，准确率和损失的数值就已经较高并逐渐收敛，说明模型具有收敛性。

对比图10中两种训练模式的验证图像级准确率曲线，可以看出两种训练模式下HC-GCN的训练准确率曲线平滑，获得的准确率数值较高，说明HC-GCN 模型适用于对当前乳腺病理数据集进行亚型分类研究。

# 3.4实验结果分析

表4展示了本文所提方法和其他较经典的深度学习方法基于BreastSet数据集的分类实验结果。

从表4中各种模型在原始数据训练模式和四切分训练模式下对应得出的数据可以看出，四切分训练模式得出的准确率、F1评分等准确率性能数据均优于原始数据训练模式。同时，从图10可以看出，四切分训练模式相比原始数据训练模式，验证集图像准确率曲线数值普遍更高，训练集损失曲线数值普遍更低，证明使用基于四叉树分割的图像数据增强方法有助于提高模型对于乳腺病理WSI图像的分类性能

HC-GCN只需要用到很少的参数量和计算量就可以达到较好的病理类型识别精度，有助于降低模型对计算资源的依赖、增加模型的扩展性和可移植性。

# 3.5 与其他方法比较

本文还选用了多种经典热门的图像分类模型与HC-GCN进行对比，每个模型均基于BreastSet 数据集进行了病理亚型分类，实验结果如表4所列。

从表4可以看出，许多优秀模型均能够在乳腺病理图像分类任务上获得较高的分类准确率。与各级别准确率最高的网络模型DenseNet121相比，HC-GCN在原始数据训练模式下获得的图像级、患者级和病理级准确率分别提高了 $1 . 1 4 \%$ ，$0 . 2 3 \%$ 和 $0 . 6 5 \%$ ；在四切分训练模式下获得的图像级、患者级、病理级准确率分别提高了 $0 . 3 7 \%$ ， $0 . 4 0 \%$ 和 $0 . 6 5 \%$ ，说明HC-GCN相比DenseNet模型能够获得更高的分类准确率；并且HC-GCN所需的参数量和计算浮点数大约分别只占DenseNet121网络模型的3/8和 $1 / 6$ ，有效地减轻了特征重用机制导致的冗余度过大问题，节省了计算资源。与具有较小参数量的模型ShuffleNetv2相比，HC-GCN在使用更小的参数量和计算量的情况下，原始数据训练模式下的图像级、患者级和病理级准确率分别提高了 $9 . 7 7 \%$ 、 $9 . 5 3 \%$ 和 $9 . 4 5 \%$ ，四切分训练模式下的图像级、患者级和病理级准确率分别提高了 $5 . 5 7 \%$ ， $3 . 5 3 \%$ 和 $1 7 . 6 1 \%$ 与其他具有更小的计算量的模型AlexNet、MobileNetv2和MobileNetv3相比，尽管HC-GCN多使用了 $0 . 1 9 \mathrm { G B } \mathrm { \sim } 0 . 2 8 \mathrm { G B }$ 的计算量，但原始数据训练模式下的图像级、患者级和病理级别准确率分别提高了 $5 . 4 6 \% { \sim } 1 9 . 5 4 \%$ ， $5 . 8 4 \% { \sim } 1 6 . 8 9 \%$ 和 $6 . 6 6 \% { \sim } 2 9 . 3 2 \%$ 四切分训练模式下的图像级、患者级和病理级准确率分别提高了$6 . 2 4 \% \sim 1 2 . 3 3 \%$ 、 $5 . 9 3 \% \mathrm { \sim } 1 2 . 3 7$ 和 $5 . 2 4 \% \sim 1 1 . 7 5 \%$ 0

表4实验结果 Tab.4Accuracy, Params,Flops,Precision,Recall and F1 Scores of Classification   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="7">L=0</td><td colspan="5">L=1</td><td rowspan="2">Params /MB</td><td rowspan="2">Flops /GB</td></tr><tr><td>IA</td><td>PA</td><td>PLA</td><td>Macro-P</td><td>Macro-R</td><td>Macro-F1</td><td>IA</td><td>PA</td><td>PLA</td><td>Macro-P</td><td>Macro-R</td><td>Macro-F1</td></tr><tr><td>AlexNet</td><td>78.74</td><td>77.64</td><td>77.68</td><td>85.05</td><td>77.68</td><td>81.53</td><td>85.14</td><td>84.25</td><td>83.44</td><td>83.55</td><td>83.44</td><td>83.49</td><td>16.63</td><td>0.30</td></tr><tr><td>VGG11</td><td>84.48</td><td>86.19</td><td>85.75</td><td>87.52</td><td>85.75</td><td>87.03</td><td>86.73</td><td>87.21</td><td>85.00</td><td>85.20</td><td>85.00</td><td>85.01</td><td>132.86</td><td>7.62</td></tr><tr><td>VGG13</td><td>85.06</td><td>87.10</td><td>86.33</td><td>88.20</td><td>86.33</td><td>87.71</td><td>85.26</td><td>85.59</td><td>81.53</td><td>84.07</td><td>81.53</td><td>82.49</td><td>133.05</td><td>11.32</td></tr><tr><td>VGG16</td><td>81.61</td><td>82.72</td><td>82.51</td><td>82.84</td><td>82.51</td><td>82.65</td><td>84.28</td><td>84.10</td><td>81.30</td><td>82.71</td><td>81.41</td><td>81.52</td><td>138.36</td><td>15.48</td></tr><tr><td>VGG19</td><td></td><td>81.90 83.91</td><td>83.65</td><td>87.38</td><td>83.65</td><td>85.25</td><td></td><td>82.94 83.49</td><td>79.47</td><td>81.82</td><td>79.47</td><td>80.18</td><td>133.05</td><td>19.65</td></tr><tr><td>GoogLeNet</td><td></td><td>84.77 86.78</td><td>85.90</td><td>88.68</td><td>85.90</td><td>87.86</td><td>88.93</td><td>86.80</td><td>87.18</td><td>88.20</td><td>87.17</td><td>87.58</td><td>7.00</td><td>1.59</td></tr><tr><td>ResNet34</td><td>62.93</td><td>65.51</td><td>48.45</td><td>59.2</td><td>48.45</td><td>51.96</td><td>68.49</td><td>69.37</td><td>69.74</td><td>69.58</td><td>70.07</td><td>69.82</td><td>21.99</td><td>6.67</td></tr><tr><td>ResNet50</td><td></td><td>69.8371.75</td><td>59.07</td><td>65.13</td><td>59.07</td><td>61.71</td><td>71.78</td><td>72.83</td><td>71.95</td><td>73.12</td><td>78.90</td><td>75.91</td><td>25.56</td><td>4.11</td></tr><tr><td>ResNet101</td><td>72.13</td><td>74.38 61.61</td><td></td><td>72.71</td><td>61.61</td><td>65.08</td><td>78.41</td><td>79.46</td><td>79.18</td><td>80.29</td><td>79.31</td><td>79.80</td><td>44.55</td><td>7.83</td></tr><tr><td>ResNet152</td><td>67.53</td><td>68.36</td><td>59.04</td><td>67.18</td><td>59.04</td><td>62.24</td><td>78.30</td><td>78.55</td><td>78.35</td><td>77.72</td><td>78.56</td><td>78.34</td><td>57.67</td><td>9.18</td></tr><tr><td>ResNext50</td><td>68.39</td><td>69.59</td><td>54.84</td><td>65.87</td><td>54.84</td><td>58.29</td><td></td><td>75.76 76.55</td><td>75.52</td><td>78.04</td><td>77.39</td><td>77.72</td><td>25.03</td><td>4.26</td></tr><tr><td>ResNext101</td><td>71.55</td><td>71.83</td><td>62.42</td><td>70.18</td><td>62.42</td><td>65.66</td><td>78.67</td><td>79.71</td><td>79.03</td><td>80.56</td><td>79.57</td><td>80.06</td><td>88.89</td><td>16.48</td></tr><tr><td>MobileNetv2</td><td>71.26</td><td>73.95</td><td>61.51</td><td>70.99</td><td>61.51</td><td>64.90</td><td>79.91</td><td>80.46</td><td>80.43</td><td>80.40</td><td>86.89</td><td>83.52</td><td>3.51</td><td>0.31</td></tr><tr><td>MobileNetv3</td><td>85.34</td><td>85</td><td>84.17</td><td>83.96</td><td>84.17</td><td>83.82</td><td>86.00</td><td>86.90</td><td>86.94</td><td>87.29</td><td>88.73</td><td>88.00</td><td>5.48</td><td>0.22</td></tr><tr><td>DenseNet121</td><td>89.66</td><td>90.61</td><td>90.18</td><td>90.73</td><td>90.18</td><td>90.53</td><td></td><td>91.87 92.43</td><td>91.53</td><td>91.46</td><td>91.53</td><td>91.47</td><td>7.98</td><td>2.87</td></tr><tr><td>DenseNet169</td><td>85.87</td><td>86.09</td><td>84.50</td><td>83.86</td><td>84.50</td><td>84.11</td><td></td><td>88.79 90.31</td><td>89.45</td><td>90.23</td><td>89.45</td><td>90.15</td><td>14.15</td><td>3.40</td></tr><tr><td>DenseNet201</td><td>89.37</td><td>90.16</td><td>89.36</td><td>90.57</td><td>89.36</td><td>90.39</td><td></td><td>91.26 91.79</td><td>91.01</td><td>90.93</td><td>91.01</td><td>90.98</td><td>20.01</td><td>4.34</td></tr><tr><td>DenseNet264</td><td></td><td>87.08 87.42</td><td>87.74</td><td>84.88</td><td>86.53</td><td>85.66</td><td></td><td>89.08 90.16</td><td>89.76</td><td>90.57</td><td>89.76</td><td>90.40</td><td>28.68</td><td>7.79</td></tr><tr><td>EfficientNetbo</td><td>87.93</td><td>89.04 88.17</td><td></td><td>89.40</td><td>88.17</td><td>88.57</td><td>88.20</td><td>88.78</td><td>86.44</td><td>87.79</td><td>86.44</td><td>86.93</td><td>5.29</td><td>0.65</td></tr><tr><td>ShuffleNetv2</td><td></td><td>81.03 81.31</td><td>81.38</td><td>79.54</td><td>81.38</td><td>80.88</td><td></td><td></td><td>86.67 89.30 74.57</td><td>87.09</td><td>74.57</td><td>78.69</td><td>2.28</td><td>1.08</td></tr><tr><td>RegNetx1.2gf</td><td></td><td>87.36 89.47</td><td>89.28</td><td>89.08</td><td>89.28</td><td>89.18</td><td>90.53</td><td>91.61</td><td>89.94</td><td>89.88</td><td>89.94</td><td>89.89</td><td>46.11</td><td>13.61</td></tr><tr><td>HC-GCN</td><td></td><td>90.8090.84</td><td>90.83</td><td>90.90</td><td>90.83</td><td>90.89</td><td></td><td>92.2492.83</td><td>92.18</td><td>91.97</td><td>92.18</td><td>92.07</td><td>3.06</td><td>0.50</td></tr></table></body></html>

注：其中，加粗的数值表示在同家族模型中的同指标最优值，灰色底纹的数值表示其他模型的同指标最优值。

与表4列出的其他模型相比，HC-GCN在使用更小的参数量和计算量的同时获得了更优的准确率、精确率、召回率和F1评分数值。实验结果说明HC-GCN显著提升了对WSI乳腺病理图像的亚型分类性能。

综上所述，与其他方法相比，HC-GCN不仅能够提高乳腺病理图像的病理类别分类准确率，而且可以减少模型所需的参数量和计算量，节省计算资源。

# 3.6消融实验

为了测试和验证本文所提方法和模块的有效性，设计了四组互为对照的消融实验。表5展示了消融实验中依次添加改进结构模块的情况。

表5中，RC表示残差连接，FG表示遗忘门，UG表示更新门。第一组消融实验中每个瓶颈块包含标准正则化层(Batchnormalization)、ReLU激活函数层、 $1 \times 1$ 卷积、 $3 \times 3$ 组卷积、 $3 \times 3$ 深度可分离卷积和Dropout层各一个，设计第一组实验的目的是将其与添加各种模块结构后的模型形成对比，验证各结构是否能够有效提升模型的分类性能。第二组至第四组消融实验中，删除了瓶颈模块中的标准正则化层、ReLU层和Dropout层，依次在瓶颈块中添加残差连接、遗忘门和更新门结构，即逐渐形成本文设计的SEG块，这样设计的目的是观察各结构对模型性能的影响。

观察表5中对应的准确率数值可知，第二组较第一组、第四组较第三组的准确率数值增幅较大，说明残差连接和更新门结构有利于提高模型的分类准确率。观察第二组和第三组实验数据可知，添加遗忘门的操作不会对模型的分类准确率和参数量产生较大影响，同时遗忘门的衰减操作有效地降低了模型的计算量。观察第三组和第四组实验数据可知，更新门只需要占用较少的参数量和计算量就能够使模型的分类准确率获得较大的提升。综上所述，本文所提的混合连接模式和SEG块结构均能有效地提升模型性能。

表5消融实验  
Tab.5Ablation experiment   

<html><body><table><tr><td>模型</td><td>RC</td><td>FG</td><td>UG</td><td>IA</td><td>PA</td><td>PLA</td><td>Params/MB</td><td>Flops/GB</td></tr><tr><td>1</td><td></td><td></td><td></td><td>84.77</td><td>84.96</td><td>84.22</td><td>2.38</td><td>2.07</td></tr><tr><td>2</td><td>√</td><td></td><td></td><td>88.51</td><td>89.47</td><td>89.29</td><td>2.38</td><td>0.89</td></tr><tr><td>3</td><td>√</td><td>√</td><td></td><td>88.79</td><td>88.98</td><td>88.62</td><td>2.72</td><td>0.43</td></tr><tr><td>4</td><td>√</td><td>√</td><td>√</td><td>92.24</td><td>92.83</td><td>92.18</td><td>3.06</td><td>0.50</td></tr></table></body></html>

# 3.7与其他文献中方法比较

为了证明HC-GCN模型的优越性和通用性，本文还将其得出的实验结果与其他文献中使用的乳腺病理图像分类方法进行了对比。

图11展示了HC-GCN与其他乳腺病理图像分类方法的图像级准确率对比情况，其中的实验数据结果均是基于大型公开的BreakHis 数据集得出的，[5]\~[16]分别表示文献[5]\~[16]中所提方法，当文献中所提方法或训练方法不唯一时，图11中取文献中展示的图像级准确率最高数值。

二分类IA(%)  
山l[5] [6] [7] [9] [11] [12] [14] [16] HC-GCN八分类IA(%)  
10095.5 95.69  
95 93.3 92.5 90.66\~93.81 92.26\~94.85  
90 88.23 山  
85 I  
80  
75 73.68  
70[5] [6] [8] [10] [11] [13] [15] [16]HC-GCN

由图11可知，在基于BreakHis数据集的乳腺病理图像分类实验中，本文提出的HC-GCN 模型进行良恶性二分类的图像级准确率达到了 $9 9 . 7 5 \%$ ，进行病理亚型八分类的图像级准确率达到了 $9 5 . 6 9 \%$ ，与对比方法相比准确率有所提高。实验结果表明HC-GCN 模型的分类准确率高于其他文献中的乳腺病理图像分类方法。

另外，图11显示本文所提的HC-GCN模型在BreakHis数据集上也能获得较好的分类效果，说明模型具有良好的通用性和泛化能力。

# 4 结束语

本文提出基于混合连接的门控卷积网络模型对乳腺病理图像进行业型分类，运用来自绵阳市中心医院的乳腺病理WSI 图像建立BreastSet 数据集，使用基于四叉树的图像分割增强方法进行数据增强，采用融合算法和投票制规则决定每张WSI的最终分类。实验结果表明，本文所提的 HC-GCN模型在乳腺病理WSI图像分类问题上能够获得较好的结果，所提的混合连接、更新门和遗忘门结构均能够有效提升模型性能。同时，HC-GCN模型还具有良好的通用性和泛化能力。

本文方法也适用于其他WSI病理图像(例如宫颈癌组织切片图像等)的视觉分类和辅助诊断，能够在一定程度上满足临床需求。在后续的实验中，可考虑对原始WSI乳腺病理图像数据进行定位标注，对BreastSet数据集进行图像分割和病灶定位，对多种病理类别中难以分类的特征加入自适应调整模块等方面进一步展开研究。

# 参考文献：

[1]黄育北，佟仲生，陈可欣，等．《中国女性乳腺癌筛查指南》解读 (精简版）[J].中国肿瘤临床，2019,46(09):432-440.(Huang Yubei, Tong Zhongsheng,Chen Kexin,et al. Interpretation of guideline for breast cancer screening in Chinese women [J].Chinese Journal of Clinical Oncology,2019,46 (09): 432-440.)   
[2]魏溪含，涂铭，张修鹏.深度学习与图像识别[M]．北京：机械工业 出版社，2019:26-28.(Wei Xihan,Tu Ming,Zhang Xiupeng.Deep learning and image recognition [M].BeiJing: Machinery Industry Press, 2019:26-28.)   
[3]马技，李晶皎，李珍妮．基于视觉注意机制深度强化学习的行人检 测方法[J]．中国科技论文，2017,12(14):1570-1577.(Ma Ji,Li Jingjiao,Li Zhenni.Deep reinforcement learning with visual attention forpedestrian detection [J].China Sciencepaper,2017,12 (14):1570- 1577.)   
[4]赵凯，安卫超，张晓宇，等．共享浅层参数多任务学习的脑出血图像 分割与分类[J]．计算机科学:2022,49(04):203-208.(Zhao Kai,An Weichao，Zhang Xiaoyu，et al. Intracerebral Hemorrhage Image Segmentation and Classification Based on Multi-task Learning of Shared Shallow Parameters [J].Computer Science,2022,49 (04):203-208.)   
[5]Han Z,Wei B,Zheng Y,et al.Breast Cancer Multi-classification from Histopathological Images with Structured Deep Learning Model [J]. Scientific Reports,2017,7(1): 4172.   
[6]Bardou D, Zhang K, Ahmad S M. Classification of Breast Cancer Based on Histology Images Using Convolutional Neural Networks [J]. IEEE Access,2018:1-1.   
[7]程年，俞晨，宁静艳．基于深度学习网络的乳腺癌图片分类研究[J]. 软件导刊,2019,18(8):26-28.(Cheng Nian,Yu Cheng,Ning Jinyan. Classification of Breast Couldcer Images Based on Deep Learning Network [J]. Software Guide,2019,18 (8): 26-28.)   
[8]NguyenPT,Nguyen TT,Nguyen NC,et al. Multiclass Breast Cancer Classification Using Convolutional Neural Network [C]// Proc of 4th Interational Symposiumon Electrical and Electronics Engineering (ISEE).New York: IEEE,2019:130-134.   
[9]Mt A,Kbz B,Be C,et al. BreastNet:A novel convolutional neural network model through histopathological images for the diagnosis of breast cancer[J].Physica A: Statistical Mechanics and its Applications. 2020: 123592.   
[10]李雨倩．基于深度学习的乳腺组织病理类型的多分类方法研究[D]. 安徽合肥：中国科学技术大学,2019.(Li Yuqian,Research on Multiclassification of Breast Histopathological Pattrns based on Deep Learning [D]. Hefei, Anhui: University of Science and Technology of China,2019.)   
[11] Jiang Y,Chen L,Zhang H,et al. Breast cancer histopathological image classification using convolutional neural networks with smallSE-ResNet module [J]. PloS one,2019,14 (3): e0214587.   
[12] 刘巧利，闫航，贺鹏飞，杨信志，李彦杰．基于改进DenseNet网络的 乳腺癌自动诊断[J].计算机与数字工程，2019,47(10):2496-2502. (Liu Qiaoli,Yan Hang,He Pengfei, Yang Xinzhi,Li Yanjie.Automatic Diagnosis of Breast Cancer Based on Improved DenseNet Network [J]. Computer & Digital Engineering,2019,47(10): 2496-2502.)   
[13]刘靖雯，黄理灿．基于 Inception-ResNet-V2 的乳腺癌病理图像识别 研究[J].软件导刊,2020,19(5):225-229.(Liu Jingwen, Huang Lican. Pathological Image Recognition of Breast Cancer Based on InceptionResNet-V2[J]. Software Guide,2020,19 (5): 225-229)   
[14]明涛，王丹，郭继昌，等．基于多尺度通道重校准的乳腺癌病理图像 分类[J].浙江大学学报（工学版),2020,54(07):1289-1297.(Ming Tao,Wang Dan,Guo Jichang,et al.Breast cancer histopathological image classification using multi-scale channel squeeze-and-excitation 54 (07): 1289-1297.)   
[15]于凌涛，夏永强，王鹏程，等．基于多任务模型的乳腺癌病理图像分 类[J].华中科技大学学报（自然科学版），2021,49(08): $5 3 - 5 7 + 6 9$ ： (Yu Lingtao,Xia Yongqiang，Wang Pengcheng，et al.Breast cancer pathological image classification based on multi-task model [J].J. Huazhong Univ.of Sci.& Tech.(Natural Science Edition).2021,49 (08): （20 $5 3 - 5 7 + 6 9 .$ ）   
[16]赵晓平，王荣发，孙中波，等．改进 DenseNet 的乳腺癌病理图像八 分类研究[J]．计算机工程与应用，2022,03(09):1-10.(Zhao Xiaoping，Wang Rongfa，Sun Zhongbo，et al.Research on Eight Classifications of Breast Cancer Pathological Images Based on Improved DenseNet [J].Computer Engineering and Applications,2022,03 (09):1- 10.)   
[17] Cruz-Roa A,Basavanhally A,Gonzalez F,et al.Automatic detection of invasive ductal carcinoma in whole slide images with convolutional neural networks [C]// Medical Imaging 2014: Digital Pathology. San Diego: SPIE,2014: 904103.   
[18] Wang D,Khosla A, Gargeya R,et al. Deep learning for identifying metastatic breast cancer[J].arXiv preprint arXiv:1606.05718,2016.   
[19] Gecer B,Aksoy S,Mercan E,et al. Detection and clasification of cancer in whole slide breast histopathology images using deep convolutional networks [J].Patern recognition,2018,84: 345-356.   
[20] He K, Zhang X,Ren S,et al.Deep residual learning for image recognition [C]//Proceedings of the IEEE conference on computer vision and pattern recognition.New York: IEEE,2016:770-778.   
[21] Huang G,Liu Z, Weinberger K Q,et al. Densely connected convolutional networks [C]// Proceedings of the IEEE conference on computer vision and pattern recognition.New York: IEEE,2017,4700-4708.   
[22]阿斯顿·张，李沐，扎卡里·C．立顿，等．动手学深度学习[M]. 北京：中国工信出版集团，人民邮电出版社，2019:147-149.(Aston Zhang,MuLi, Zachary C.Lipton,et al.DIVE INTO DEEPLEARNING [M].BeiJing: China Industry and Information Technology Publishing Group,Posts & Telecom Press,2019:147-149.)   
[23] Gu J,Wang Z,Kuen J,et al. Recent advances in convolutional neural networks [J].Patterm Recognition,2018,77: 354-377.   
[24] Yosinski J, Clune J,Bengio Y,et al. How transferable are features in deep neural networks? [Cl// Advances in Neural Information Processing Systems.Cambridge,MA:MIT Press,2014:1-9.   
[25] Sokolova M,Japkowicz N,Szpakowicz S.Beyond accuracy,F-score and ROC:a family of discriminant measures for performance evaluation [C]// Australasian joint conference on artificial intelligence. Springer,Berlin: Heidelberg,2006:1015-1021.