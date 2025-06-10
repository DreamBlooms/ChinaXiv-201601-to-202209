# 基于大批量训练和正交正则化的跨模态哈希方法\*

张学旺1,2†，周印1

(1．重庆邮电大学 软件工程学院，重庆 400065;2.重庆大学 微电子与通信工程学院，重庆 400044)

摘要：基于深度学习的跨模态哈希方法都使用小批量训练方式来训练模型，然而小批量方式在每次更新参数时获取样本数量有限，不能得到很好的梯度，影响最终训练的模型的检索性能。针对此问题，提出了一个新的跨模态哈希方法，该方法使用大批量方式进行训练，并引入正交正则化来增加大批量训练的稳定性，同时考虑了哈希码的离散性，将哈希码与特征之间的距离加入到目标函数中，使得哈希码能够更加真实的表示数据。在两个广泛使用的跨模态检索数据集上的实验表明该方法比现有的几种哈希方法具有更好的性能。

关键词：跨模态哈希；大批量训练；正交正则化；哈希码和特征之间的距离 中图分类号：TP391.3 doi:10.19734/j.issn.1001-3695.2020.02.0040

Cross-modal hashing method based on large batch training and orthogonal regularization

Zhang Xuewang1, 2†, Zhou Yin1 (1.SchoolofSoftware Engineing,Chongqing UniversityofPosts&Telecommunications,Chongqing 40o65,China;2. School of Microelectronics & Communication Engineering, Chongqing University,Chongqing 40oo44, China)

Abstract:The cross-modal hashing methods basedondeep learming use thesmallbatch training method to train their model. However,itcannot geta good gradientusing this training methoddue tothe limited number ofsamples ineach parameter update,which affcts theretrievalperformanceof the final rained model.To solve the problem,this paper proposed anew cros-modal hashing,whichusedlargebatchtrainingandintroducedorthogonalregularization to increasethe stabiltyofthis kindoftraining.Andtoconsider thediscreteness ofhashcodes,theobjectivefunctionadded thedistance between hashcodes andfeatures which made hash codes to represent data more realistically.Extensive experimentsontwo widely used public datasets in cross-modal hashing show thatthis method achieves beter performance than several existing hashing methods.

Keywords:cross-modal hashing;large batch training;orthogonalregularization；the distance between hash codesanc features

# 0 引言

随着互联网和多媒体技术的快速发展，产生了大量不同模态的多媒体数据，比如图像、文本、视频等。不同模态的数据可以用于描述同一个事物，多视角地展现信息，可以帮助用户获得该事物的综合理解。随着不同模态的多媒体数据快速增长，跨模态检索成为了研究热点。跨模态检索的关键在于对不同模态的多媒体数据的关系进行建模，难点主要是不同模态的多媒体数据存在异构性鸿沟，无法进行直接比较[1]。跨模态哈希方法可以有效地为不同模态的数据建立比较关系，将不同模态的数据映射到共同的汉明空间中，每个数据都被转换成一个固定长度的二进制哈希码，通过将哈希码按位异或运算，可以得到数据间的汉明距离，进而得到数据间的相似性。

随着深度学习的发展，越来越多的基于深度学习的跨模态哈希方法被提出。Jiang 等人提出深度跨模态哈希(deepcross-modalhashing,DCMH)[2]，使用深度神经网络的端到端学习框架进行特征学习，直接学习离散的二进制码。Zhang 等人提出无监督生成对抗跨模态哈希(unsupervised generativeadversarialcross-modalhashing,UGACH)[3]，利用生成对抗网络(generativeadversarialnets,GAN)的无监督表示学习能力，学习跨模态数据的底层流形结构，通过生成模型和判别模型的对抗训练来提高判别模型的判别能力。Deng等人提出基于三元组深度哈希(triplet-based deep hashing,TDH)[4]，采用三元组(查询样本，正样本，负样本)的形式输入训练数据，三元组形式能够更加灵活地捕捉所有可能的语义相似性，并且还考虑了模态间和模态内的相似性。Zhang等人提出半监督生成对抗跨模态 哈希(semi-supervised cross-modal hashing bygenerative adversarial network，SCH-GAN)[5]，利用生成对抗网络GAN进行对抗训练。

大多基于深度学习的跨模态哈希方法都采用小批量训练方式训练模型，比如文献[3,5]训练批量大小为64，文献[4]训练批量大小为128，这会使得在训练过程中每次更新参数时获取样本数量有限，不能得到很好的梯度，影响最终训练的模型的检索性能。

大批量训练在每次更新参数时是基于更多的样本，会得到更好的梯度，同时也使得每轮训练时间更少。基于以上特点，越来越多学者在不同研究领域探索大批量训练。Goyal等人[在ImageNet数据集上采用大批量方式训练ResNet-50 网络模型，批量大小为8192，使训练时间缩小到一小时，训练的模型精度可以和小批量训练方式训练的模型精度媲美。You 等人[7将大批量训练扩展到了自然语言处理领域，收到了很好的效果。Brock等人[8将大批量训练应用到图像生成领域，批量大小设为2048，也获得了很好的性能。但是，仅仅增加批量大小会导致训练极其不稳定[9]，还容易导致网络的泛化性能下降，出现"GeneralizationGap"问题[10]。

正交正则化能够保持矩阵的范数不变，使梯度忠实传播，防止梯度消失[1I]。在图像生成研究领域，Brock等人[11]引入正交正则化，提高了网络泛化能力；在文献[8]中，Brock等人引入正交正则化的变体，使得截断更平滑，实现了更好的性能。在多模态检索领域，Wang等人[2]引入正交正则化，采用小批量训练模型解决了生成哈希码的冗余问题。

由于哈希码是离散的，大部分跨模态哈希方法将哈希码的离散学习问题松弛为连续学习问题。但是数据的连续实值特征在转换为哈希码的过程中，会出现信息损失，这使得哈希码不能够很好地表示数据，影响检索性能[2]。DCMH[2]采用小批量训练模型，将哈希码加入到目标函数中，直接学习哈希码，而不进行松弛。

综合上述应用于不同领域的研究方法，本文提出了基于大批量训练和正交正则化的跨模态哈希方法。该方法包含三个主要特征：a）模型采用三元组的方式输入数据，使用大批量训练方式进行训练，以获得更好的梯度；b)引入正交正则化用于增加大批量训练模型的稳定性；c）在目标函数中加入哈希码与数据特征之间的距离，通过优化目标函数，数据特征在转换成哈希码时所产生的信息损失将减小，使得哈希码能够更加真实的表示数据。

# 1基于大批量训练和正交正则化的跨模态哈希

在本节中将详细描述本文所提出的方法。为了阐述更简洁，本文只考虑图像和文本两种模态的数据，其他的模态数据可以进行相应扩展。简化后有两种检索任务：a）文本检索图像；b）图像检索文本。假定有 $k$ 个训练数据， $I = \{ I _ { i } \} _ { i = 1 } ^ { k }$ 表示图像数据， $T = \{ T _ { i } \} _ { i = 1 } ^ { k }$ 表示文本数据。 $F = \{ F _ { I _ { i } } , F _ { T _ { i } } \} _ { i = 1 } ^ { k }$ 为数据的低维特征， $q = \{ q _ { I _ { i } } , q _ { T _ { i } } \} _ { i = 1 } ^ { k }$ 表示查询数据， $H = \{ H _ { I _ { i } } , H _ { T _ { i } } \} _ { i = 1 } ^ { k }$ 为数据的哈希码，而 $\left\| \bullet \right\| _ { F r o }$ 表示矩阵的Frobenius 范数。

# 1.1模型结构

本模型分为图像网络和文本网络两部分。对于图像部分，很多基于深度学习的跨模态哈希方法使用卷积神经网络(CNN)来提取图像的特征以此作为模型的图像输入值，比如文献[3，5]，使用VGG-19来提取图像特征。本文也将使用VGG-19来提取图像特征作为图像的输入值，然后经过两层全连接层得到哈希码。而对于文本，则使用词袋模型(BoW)将其表示成向量，作为文本网络的输入值，同样经过两层全连接层得到哈希码。整个模型的框架结构如图1所示。

![](images/26ce5f76bfb95b554bdab30e74c9840cb8b140db2313c69db71d6c9b6f4fc5d0.jpg)  
图1模型框架图  
Fig.1The framework of proposed model

# 1.2 特征学习部分

如图1所示，首先将图像或者文本的特征经过第一层全连接层映射到一个共同空间，然后再经过第二层全连接层得到数据的低维特征。第一层全连接层的激活函数是tanh函数，而第二层全连接层的激活函数是sigmoid函数。整个过程可以表示如下：

$$
F = s i g m o i d ( W _ { c _ { 2 } } ( \operatorname { t a n h } ( W _ { c _ { 1 } } f + B _ { c _ { 1 } } ) + B _ { c _ { 2 } } ) )
$$

其中 $W$ 为权重， $B$ 为偏置项， $c _ { 1 }$ 表示第一层全连接层， $c _ { 2 }$ 表示第二层全连接层。 $f$ 表示图像的VGG-19特征或者文本的BoW向量。图像的低维特征 $F _ { I }$ 和文本的低维特征 $F _ { T }$ 维度相同，便于度量它们之间的相似性。将低维特征 $F$ 通过阈值函数映射为哈希码 $H$ ，阈值函数如下：

$$
H = \left\{ { \begin{array} { l l } { 1 , } & { i f { \ F } \geq 0 . 5 } \\ { 0 , } & { i f { \ F } < 0 . 5 } \end{array} } \right.
$$

# 1.3目标函数

由于图像检索文本任务和文本检索图像任务是对称的，所以在接下来部分仅介绍文本检索图像任务的目标函数。目标函数主要分成三部分：a）文本特征 $F _ { q _ { T } }$ 和图像特征$F _ { I } = \{ F _ { I ^ { + } } , F _ { I ^ { - } } \}$ 之间的距离；b）哈希码 $H$ 和特征 $F$ 之间的距离;c） $W$ 和 $B$ 的正则化项。

a）文本特征 $F _ { _ { q _ { T } } }$ 和图像特征 $F _ { \scriptscriptstyle I } = \{ F _ { \scriptscriptstyle I ^ { + } } , F _ { \scriptscriptstyle I ^ { - } } \}$ 之间的距离：

$$
D _ { q _ { T _ { i } } I _ { i } ^ { + } } = \left. F _ { q _ { T _ { i } } } - F _ { I _ { i } ^ { + } } \right. _ { 2 } ^ { 2 }
$$

$$
D _ { q _ { T _ { i } } I _ { i } ^ { - } } = \left. F _ { q _ { T _ { i } } } - F _ { I _ { i } ^ { - } } \right. _ { 2 } ^ { 2 }
$$

其中 $I _ { i } ^ { + }$ 和 $I _ { i } ^ { - }$ 分别表示与查询文本 $q _ { T _ { i } }$ 同语义和不同语义的图像。 $D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ 表示 $I _ { i } ^ { + }$ 与 $q _ { T _ { i } }$ 之间的距离。 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 表示 $I _ { i } ^ { - }$ 与 $q _ { T _ { i } }$ 之间的距离。本文使用一个基于边界的合页损失函数(amargin-basedhingelossfunction)来度量，如下式所示。

$$
L _ { 1 } = \frac { 1 } { n } \sum _ { i } ^ { n } \operatorname* { m a x } ( 0 , \beta + D _ { q _ { T _ { i } } I _ { i } ^ { + } } - D _ { q _ { T _ { i } } I _ { i } ^ { - } } )
$$

其中 $\beta$ 是 $D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ 和 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 的边界值，是一个可调节的超参数。 $n$ 表示三元组 $( q _ { T _ { i } } , I _ { i } ^ { + } , I _ { i } ^ { - } )$ 个数。当减少损失函数 $L _ { 1 }$ 时， $D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ 将会减小，而 $D _ { q _ { \bar { r } _ { i } } I _ { i } ^ { - } }$ 会增大。这符合语义相似数据之间距离小，语义不同数据之间距离大的原则。在训练优化过程中，希望降低$D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ 的值，增大 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 的值，即 $D _ { q _ { T _ { i } } I _ { i } ^ { * } }$ 越小， $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 越大越好。因此，可以将该过程转换为二分类问题，可以使用sigmoid交叉熵函数来作为损失函数。二分类问题的sigmoid交叉熵公式如下：

$$
\begin{array} { c c } { { l o s s = - [ z \ln ( s i g m o i d ( x ) + ( 1 - z ) \ln ( 1 - s i g m o i d ( x ) ) ) ] } } \\ { { s . t . } } & { { z \in \{ 0 , 1 \} } } \end{array}
$$

其中 $x$ 表示输入值，在这里为 $D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ 或者 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 。 $z$ 表示目标值。对于 $D _ { q _ { T _ { i } } I _ { i } ^ { + } }$ ，希望 $D _ { q _ { \bar { r } _ { i } } I _ { i } ^ { + } }$ 尽可能的小，即让 $z = 0$ ，将其带入式(6),可以得到如下公式：

$$
l o s s _ { 1 } = - \ln ( 1 - s i g m o i d ( D _ { q _ { T _ { i } } I _ { i } ^ { + } } ) ) = \ln ( 1 + e ^ { D _ { q _ { i } } \prime } ) ~
$$

对于 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ ，希望 $D _ { q _ { T _ { i } } I _ { i } ^ { - } }$ 尽可能的大，即让 $z = 1$ ，将其带入式(6)，可以得到如下公式：

$$
l o s s _ { 2 } = - \mathrm { l n } ( s i g m o i d ( D _ { q _ { T _ { i } } I _ { i } ^ { - } } ) ) = \mathrm { l n } ( 1 + e ^ { - D _ { q _ { T _ { i } } I _ { i } ^ { - } } } )
$$

将式(7)和(8)结合，就得到了第二个损失项：

$$
L _ { 2 } = \frac { 1 } { n } \sum _ { i } ^ { n } ( l o s s _ { 1 } + l o s s _ { 2 } )
$$

损失项 $L _ { 2 }$ 和损失项 $L _ { 1 }$ 具有相似的效果，将两者结合可以更好地度量图像和文本间的相似性。

b）哈希码 $H$ 和特征 $F$ 之间的距离

哈希码是离散的，当数据的实值特征 $F$ 在被转换为哈希码 $H$ 时，会发生信息损失：

$$
D _ { H _ { q _ { i } } F _ { q _ { i } } } = \left\| H _ { q _ { \tau _ { i } } } - F _ { q _ { \tau _ { i } } } \right\| _ { 1 }
$$

$$
D _ { H _ { l _ { i } } F _ { l _ { i } } } = \left\| H _ { l _ { i } } - F _ { l _ { i } } \right\| = \left\| H _ { l _ { i } ^ { + } } - F _ { l _ { i } ^ { + } } \right\| _ { 1 } + \left\| H _ { l _ { i } ^ { - } } - F _ { l _ { i } ^ { - } } \right\| _ { 1 }
$$

其中 $D _ { H _ { q _ { i } } F _ { q _ { i } } }$ 表示查询文本 $q _ { T _ { i } }$ 的低维特征 $F _ { q _ { T _ { i } } }$ 与其对应的哈希码 $H _ { \boldsymbol { q } _ { T _ { i } } }$ 之间的距离。 $D _ { H _ { I _ { i } } F _ { I _ { i } } }$ 表示图像 $I _ { i } = \{ I _ { i } ^ { + } , I _ { i } ^ { - } \}$ 的低维特征$F _ { I _ { i } } = \{ F _ { I _ { i } ^ { + } } , F _ { I _ { i } ^ { - } } \}$ 与其对应的哈希码 $H _ { I _ { i } } = \{ H _ { I _ { i } ^ { + } } , H _ { I _ { i } ^ { - } } \}$ 之间的距离。可以得到以下损失项：

$$
L _ { 3 } = \frac { 1 } { n } \sum _ { i } ^ { n } ( D _ { H _ { q _ { i } } F _ { q _ { i } } } + D _ { H _ { I _ { i } } F _ { I _ { i } } } )
$$

对该损失项进行优化过程中，会使得哈希码与数据的特征越来越接近，将会减少数据特征向哈希码转换过程中的信息损失，使得哈希码更好的表达数据特征。

# c） $W$ 和 $B$ 的正则化项

大批量训练在训练模型时不稳定，为了降低其负面影响，本文引入了正交正则化来作为权重 $W$ 的惩罚项。对于偏置项$B$ ，仍然使用L2正则化项作为惩罚项，可以得到损失项如下：

$$
\begin{array} { r l } & { L _ { 4 } = \theta \big \| \boldsymbol { W ^ { t r a } } \boldsymbol { W } - \boldsymbol { I _ { i d e } } \big \| _ { F r o } ^ { 2 } + \omega \big \| \boldsymbol { B } \big \| _ { F r o } ^ { 2 } } \\ & { = \theta ( \big \| \boldsymbol { W _ { T } ^ { t r a } } \boldsymbol { W _ { T } } - \boldsymbol { I _ { i d e } } \big \| _ { F r o } ^ { 2 } + \big \| \boldsymbol { W _ { I } ^ { t r a } } \boldsymbol { W _ { I } } - \boldsymbol { I _ { i d e } } \big \| _ { F r o } ^ { 2 } ) } \\ & { + \omega ( \big \| \boldsymbol { B _ { T } } \big \| _ { F r o } ^ { 2 } + \big \| \boldsymbol { B _ { I } } \big \| _ { F r o } ^ { 2 } ) } \end{array}
$$

其中 $W ^ { t r a }$ 是权重矩阵W的转置， $I _ { i d e }$ 表示单位矩阵， $B$ 表示偏置项。 $W _ { T }$ 表示文本网络的权重， $B _ { T }$ 表示文本网络的偏置项，$W _ { I }$ 表示图像网络的权重， $B _ { I }$ 表示图像网络的偏置项。而 $\theta$ 和$\omega$ 是超参数。

将 $L _ { 1 } , L _ { 2 } , L _ { 3 }$ 和 $L _ { 4 }$ 结合在一起，就可以得到总目标函数：

$$
\begin{array} { l } { \operatorname* { m i n } L = L _ { 1 } + \lambda L _ { 2 } + \gamma L _ { 3 } + L _ { 4 } } \\ { = \displaystyle \frac { 1 } { n } \sum _ { i } ^ { n } \big ( \operatorname* { m a x } ( 0 , \beta + \left\| F _ { q _ { i } } - F _ { I _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } - \left\| F _ { q _ { i } } - F _ { I _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } ) + } \\ { \big ) \big ( 1 \mathrm { e } ( 1 + e ^ { \left\| F _ { q _ { i } } - F _ { I _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } } ) + \mathrm { i n } ( 1 + e ^ { - \left\| F _ { q _ { i } } - F _ { I _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } } ) \big ) + } \\ { \gamma \big ( \left\| H _ { q _ { i } } - F _ { q _ { i } } \right\| _ { 1 } + \left\| H _ { I _ { i } ^ { * } } - F _ { I _ { i } ^ { * } } \right\| _ { 1 } + \left\| H _ { I _ { i } ^ { * } } - F _ { I _ { i } ^ { * } } \right\| _ { 1 } ) \big ) + } \\ { \theta ( \left\| W _ { I } ^ { \scriptscriptstyle \prime \prime } W _ { I } - I _ { i \mathrm { e } } \right\| _ { I _ { i } ^ { \mathrm { e } } } ^ { 2 } + \left\| W _ { I } ^ { \scriptscriptstyle \prime \prime } W _ { I } - I _ { i \mathrm { e } } \right\| _ { I _ { i } ^ { \mathrm { e } } } ^ { 2 } ) } \\ { + \omega ( \left\| B _ { I } \right\| _ { F ^ { \mathrm { e } } } ^ { 2 } + \left\| B _ { I } \right\| _ { F ^ { \mathrm { e } } } ^ { 2 } ) } \end{array}
$$

其中 $\lambda$ 和是超参数。

同理，图像检索文本任务的目标函数为

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } L = \frac { 1 } { n } \sum _ { i } ^ { n } \big ( \operatorname* { m a x } ( 0 , \beta + \left\| F _ { q _ { i } } - F _ { T _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } - \left\| F _ { q _ { i } } - F _ { T _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } ) + } \\ { \big ) \big ( \lfloor \mathfrak { n } ( 1 + e ^ { \left\| F _ { q _ { i } } - F _ { T _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } } ) + \ln ( 1 + e ^ { - \left\| F _ { q _ { i } } - F _ { T _ { i } ^ { * } } \right\| _ { 2 } ^ { 2 } } ) ) + } \\ { \big ) \gamma ( \left\| H _ { q _ { i } } - F _ { q _ { i } } \right\| _ { 1 } + \left\| H _ { T _ { i } ^ { * } } - F _ { T _ { i } ^ { * } } \right\| _ { 1 } + \left\| H _ { T _ { i } ^ { - } } - F _ { T _ { i } ^ { * } } \right\| _ { 1 } ) \big ) + } \\ { \theta ( \left\| W _ { T } ^ { r r \alpha } W _ { T } - I _ { i d } \right\| _ { F ^ { n p } } ^ { 2 } + \left\| W _ { I } ^ { r r \alpha } W _ { I } - I _ { i d } \right\| _ { F ^ { n p } } ^ { 2 } ) } \\ { \displaystyle + \omega ( \left\| B _ { T } \right\| _ { F ^ { n p } } ^ { 2 } + \left\| B _ { T } \right\| _ { F ^ { n p } } ^ { 2 } ) } \end{array}
$$

其中 $T _ { i } ^ { + }$ 和 $T _ { i } ^ { - }$ 分别表示与查询图像 $q _ { I _ { i } }$ 同语义和不同语义的文本。

# 1.4优化过程

由于有图像检索文本和文本检索图像两种检索任务，因此将分别对模型进行训练，具体如下过程：

a）首先初始化权重 $W$ 和偏置项 $B$ ，设定批量大小为 $n$ 和训练轮次为 $\boldsymbol { \mathscr { e } }$ ：

b）为每个查询文本 $q _ { T _ { i } }$ 随机取出 $m$ 个同语义的图像 $I _ { i } ^ { + }$ 和不同语义的图像 $I _ { i } ^ { - }$ 组成三元组 $( q _ { T _ { i } } , I _ { i } ^ { + } , I _ { i } ^ { - } )$ ，作为训练数据，对文本网络进行训练。固定 $W _ { I }$ 和 $B _ { \scriptscriptstyle I }$ ，通过式(14)分别对 $W _ { T }$ 和 $B _ { T }$ 求偏导。对 $W _ { T }$ 求偏导为

$$
\begin{array}{c} \begin{array} { r l } & { \mathrm { 3 6 0 a : } } \\ & { \mathrm { 4 8 0 a b : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 4 8 0 a : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 4 8 0 a : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 6 8 0 a : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 4 8 0 a : } } \end{array} \begin{array} { r } { \mathrm { 1 6 0 0 a : } } \\ { \mathrm { 3 6 1 4 a : } } \\ { \mathrm { 4 8 0 a : } } \\ { \mathrm { 5 6 0 a : } } \\ { \mathrm { 5 6 0 a : } } \end{array} \begin{array} { r } { \mathrm { 1 6 0 0 a : } } \\ { \mathrm { 3 6 1 4 a : } } \\ { \mathrm { 6 8 0 a : } } \\ { \mathrm { 8 6 0 a : } } \end{array}  \\ & { } \\ & { \mathrm { 4 8 0 a : } } \\ & { \mathrm { 5 6 0 a : } } \\ & { \mathrm { 4 8 0 a : } } \end{array}
$$

其中 $\left\| F _ { q _ { T _ { i } } } - F _ { I _ { i } ^ { + } } \right\| _ { 2 } ^ { 2 } - \left\| F _ { q _ { T _ { i } } } - F _ { I _ { i } ^ { - } } \right\| _ { 2 } ^ { 2 } > - \beta$ 时 $g$ 为1，否则 $g$ 为0。 $H _ { q _ { T _ { i j } } }$ 只有0，1两种值，而 $F _ { q _ { T _ { i j } } } \in ( 0 , 1 )$ ，所以当 $H _ { q _ { T _ { i j } } }$ 为0时，∑lHm-Fr|/aFar=1；当H为1时，其值为-1。因此将Ha为0的值变为-1，为1的值保持不变，得到一个变体 $H _ { q _ { T _ { i j } } } ^ { \nu a r i a n t }$ （204号$h$ 表示特征的维度，也就是哈希码的长度。对于任意矩阵A，有 $\left\| A \right\| _ { F r o } ^ { 2 } = t r ( A ^ { T } A ) = t r ( A A ^ { T } )$ ，因此由式(16)得到：

$$
\begin{array} { c }  { \displaystyle { \frac { \hat { \sigma } \operatorname* { m i n } { \cal L } } { \hat { \sigma } W _ { T } } = \frac { 1 } { n } \sum _ { i } ^ { n } \sum _ { j } ^ { h } \Bigl ( 2 ( { \cal F } _ { I _ { i j } ^ { - } } - { \cal F } _ { I _ { i j } ^ { + } } ) g + 2 \lambda ( \frac { { \cal F } _ { q _ { T _ { i j } } } - { \cal F } _ { I _ { i j } ^ { + } } } { 1 + e ^ { - \sum _ { j } ^ { h } ( { \cal F } _ { q _ { T _ { i j } } } - { \cal F } _ { I _ { i j } ^ { + } } ) ^ { 2 } } } } } \\ { { + \frac { { \cal F } _ { I _ { i j } ^ { - } } - { \cal F } _ { q _ { T _ { i j } } } } { 1 + e ^ { \sum _ { j } ^ { h } ( { \cal F } _ { q _ { T _ { i } } } - { \cal F } _ { I _ { i j } ^ { + } } ) ^ { 2 } } } ) - \gamma H _ { q _ { T _ { i j } } } ^ { \nu a r i o n t } { } ) \frac { \hat { \sigma } { \cal F } _ { q _ { T _ { i j } } } } { \hat { \sigma } W _ { T } } + 4 \theta ( W _ { T } W _ { T } ^ { t r a } - I _ { i d e } ) W _ { T } } } \end{array}
$$

同理可以得到 $B _ { T }$ 的偏导数，然后采用后向传播算法更新权重 $W _ { T }$ 和偏置项 $B _ { T }$ 。

c）为每个查询图像 $q _ { I _ { i } }$ 随机取出 $m$ 个同语义的文本 $T _ { i } ^ { + }$ 和不同语义的文本 $T _ { i } ^ { - }$ 组成三元组 $( q _ { I _ { i } } , T _ { i } ^ { + } , T _ { i } ^ { - } )$ ，作为训练数据，对图像网络进行训练。固定 $W _ { T }$ 和 $B _ { \scriptscriptstyle T }$ ，与求 $W _ { T }$ 和 $B _ { T }$ 的偏导数类似，通过式(15)求偏导，采用后向传播算法更新权重 $W _ { \iota }$ 和偏置项 $B _ { I }$ 。

整个方法如算法1所示。算法1算法描述输入：训练数据 $I \ , \ T$ ：输出：权重 $W$ 和偏置项 $B$ ：1 随机初始化权重 $W$ 和 $B$ ，训练批量大小设为 $b$ ，训练轮次设为 $\boldsymbol { \mathscr { e } }$ ·2for epoch $\mathtt { \Omega } = \mathtt { \partial } \mathtt { \partial }$ ,1,2.,，..,e-1do3 if epoch $\% 3 0 = = 0$ do4 for $q _ { T _ { i } } = T _ { 1 } , T _ { 2 } , \cdots , T _ { k }$ do5 随机取出 $m$ 个与查询文本 $q _ { 7 _ { i } }$ 相关的正例图像 $I _ { i } ^ { + }$ 和与查询文本 $q _ { T _ { i } }$ 不相关的负例图像 $I _ { i } ^ { - }$ 组成 $m$ 个三元组 $( q _ { T _ { i } } , I _ { i } ^ { + } , I _ { i } ^ { - } )$ ，作为训练数据。6 end for7 end if8 for ste $\mathfrak { p } { = } 1 , 2 { \cdots } , \lceil k ^ { * } m / b \rceil \mathbf { d } \mathbf { c }$ 9 固定 $W _ { I }$ 和 $B _ { \iota }$ ，通过式(14)求偏导，采用后向传播算法更新权重 $W _ { T }$ 和偏置项 $B _ { \scriptscriptstyle T }$ 。10 end for11 if epoch% $3 0 = = 8$ do12 for $q _ { I _ { i } } = I _ { 1 } , I _ { 2 } , \cdots , I _ { k }$ do13 随机取出 $m$ 个与查询图像 $q _ { I _ { i } }$ 相关的正例文本 $T _ { i } ^ { + }$ 和与查询图像 $q _ { l _ { i } }$ 不相关的负例文本 $T _ { i } ^ { - }$ 组成 $m$ 个三元组 $( q _ { I _ { i } } , T _ { i } ^ { + } , T _ { i } ^ { - } )$ ，作为训练数据。14 end for15 end if16 for step= $1 , 2 \cdots , \lceil k ^ { * } m / b \rceil$ do17 固定 $W _ { T }$ 和 $B _ { T }$ ，通过式(15)求偏导，采用后向传播算法更新权重 $W _ { \iota }$ 和偏置项 $B _ { \iota }$ （204号18 end for19 end for

# 2 实验

在本章中，将在两个广泛用于跨模态哈希的数据集上评估本文方法的性能，并与几个比较先进的方法进行对比。

# 2.1 数据集

本文分别在Wikipedia[13]和MIRFlickr[14]数据集上开展实验。Wikipedia数据集是一个流行的数据集，它由10个类别共2866个文本/图像数据对组成。本文将其中2173个数据对作为训练数据集和检索数据集，剩余的693个数据对作为测试数据集。每个图像由深度学习框架Keras应用程序中的19层VGGNet的fc2层提取的4096维特征表示，而每个文本由1000维的BoW的向量表示。

MIRFlickr数据集从Flickr网站上收集得到，包含25000个文本/图像数据对，分为24个类别。但是其为人工标注，有些图像没有文本描述，有些图像没有类别，需要对其进行筛选。首先预处理文本，移除标点符号和停用词，然后统计各个单词的次数，取出现20次以上的单词组成BoW的词汇表，移除不包含在词汇表中单词的文本/图像数据对，同时也移除没有文本描述的图像或者没有类别的文本/图像数据对。经过这些处理后还剩余20819个文本/图像数据对。随机取出其中的 $5 \%$ 的数据对作为测试数据集，剩余数据对作为检索数据集，并随机取出5000个数据对作为训练数据集。每个图像都由Keras应用程序中的19层VGGNet的fc2层提取的4096维特征表示，而每个文本由1386维的BoW的向量表示。相关统计信息见表1。

Tab.1Statistics of two benchmark datasets   

<html><body><table><tr><td></td><td>Wikipedia</td><td>MIRFlickr</td></tr><tr><td>数据集大小</td><td>2866</td><td>20819</td></tr><tr><td>训练集</td><td>2173</td><td>5000</td></tr><tr><td>测试集</td><td>693</td><td>1041</td></tr><tr><td>检索集</td><td>2173</td><td>19778</td></tr><tr><td>类别</td><td>10</td><td>24</td></tr></table></body></html>

# 2.2评价指标

本文在每个数据集上执行两种检索任务：图像检索文本和文本检索图像，分别用image $$ text和text $$ image表示。本文使用两个广泛使用的评价标准来评价跨模态哈希的检索性能，如下所示。

a)mean average precision (MAP)：表示所有查询数据的average precisions(AP)的均值。其中AP表示查询的平均准确率，定义如下：

$$
A P = \frac { 1 } { R } { \sum _ { t = 1 } ^ { s } } \frac { R _ { t } } { t } \times r e l _ { t }
$$

其中 $\boldsymbol { R }$ 表示检索数据集中所有的相关数据的数量， $s$ 表示检索数据集中所有的数据的数量， $R _ { \mathfrak { r } }$ 表示检索出的前 $\prime$ 个数据中的相关数据的数量， $r e l _ { t }$ 表示第 $\prime$ 个数据是否是相关数据，如果为1，则相关，如果为0，则不相关。

b)Precision-recall曲线 (PR-曲线)：表示准确率召回率曲线，在不同召回率下的检索准确率，常常用于评价检索性能。

# 2.3对比方法和实现细节

本文与两个非深度学习方法 SePH[15]和GSPH[16]进行了对比，SePH和GSPH都是基于核的，使用核逻辑回归(KLR)学习哈希函数来取得最好的结果，都分别采用了k-均值算法和随机抽样法。因此，在对比这两种方法时，用 $\mathbf { k l r } { + } \mathbf { k }$ 表示使用 $\mathbf { k }$ -均值算法的核逻辑回归，而用 $\mathbf { k l r } { + \mathbf { r } }$ 表示使用随机抽样的核逻辑回归。另外还与现有三个基于深度学习的跨模态哈希方法DCMH[2]，UGACH[3]和 SCH-GAN[5] 进行了对比,DCMH采用端到端网络结构，直接学习哈希码，UGACH和SCH-GAN都基于生成对抗网络GAN，采用三元组方式输入数据。在本文实验中要用到图像和文本两种模态数据，对比时在将一种模态的数据作为查询数据集的时候，将另一种模态的数据作为检索数据集。为了公平对比，所有方法都采用3.1节中描述的图像和文本的表示形式作为输入值，即图像值是4096维特征，文本是BoW向量。DCMH作为一种端到端的方法，可以直接输入图像，本文用 $\mathrm { D C M H } _ { \nu g g 1 9 }$ 表示前述对比形式，另外用 $\mathrm { D C M H } _ { o r i g i n a l }$ 表示直接将图像作为输入值进行训练。对比的五个方法的代码都由相应的作者提供。对于本文的方法，参考文献[5]将超参数设置为： $\lambda { = } 0 . 0 1$ ， $\gamma = 0 . 0 1$ 和 $\omega = 0 . 0 1$ ；参考文献[8]，令 $\scriptstyle \theta = 0 . 0 0 0 1$ ；对于 $\beta$ ，哈希码位数不同，在汉明空间中的维度就不同，位数越大，维度越大，边界值越大才能更好的在汉明空间中将正例数据和负例数据分开。哈希码位数分别为16、32和64位(bits)， $\beta$ 分别为6、8和10.在Wikipedia数据集上的学习率为0.08，在MIRFlickr数据集的学习率为0.016。与文献[3,5]类似，对于每一个数据挑选出相应的数据组成4个三元组用于训练，即将 $m$ 设为4,因此对于Wikipedia数据集总共有 $2 1 7 3 ^ { * } 4 = 8 6 9 2$ 个三元组，对于MIRFlickr数据集总共有 $5 0 0 0 ^ { * } 4 { = } 2 0 0 0 0$ 个三元组。批量大小 $b$ 设为8192。本文使用tensorflow深度学习框架来实现代码，具体的软件版本是python3.5.2 和 tensorflow1.11.0。所有的实验都是在NVIDIAGTX1080Ti 图形卡，Intel(R)Xeon(R)E5-2620v42.10GHzCPU,128GB内存的机器上运行得到。

# 2.4实验结果

表2和3分别展示了各个方法在MIRFlickr和Wikipedia数据集上的MAP的实验结果。从结果可以看出，对于32位和64位的哈希码，本文的方法在两个数据集上都取得了最好的结果。总体来看，与第二好的方法SCH-GAN相比，在图像检索文本的任务中，本文的方法在MIRFlickr和Wikipedia数据集上分别比其大约高出了 $1 . 8 \%$ 和 $8 . 2 \%$ ；而在文本检索图像的任务中，则分别大约提高了 $1 . 3 \%$ 和 $2 \%$ 。这主要是因为本文使用大批量训练模型，可以得到更好的梯度，并使用正交正则化使训练更加稳定。还因为将哈希码与数据特征之间的距离添加到损失函数中，使得哈希码更真实地表示数据的特征。对于16位的哈希码，由于其长度不能充分表示数据特征，尽管本文的方法在Wikipedia数据集上取得了最好的成绩，但在MIRFlickr数据集上只是第二好，说明哈希码长度对MAP具有一定的影响。

表1两个基准数据集的统计信息  
表2在MIRFlickr数据集上的MAP  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">image→text</td><td colspan="3">text→image</td></tr><tr><td>16</td><td>32</td><td>64</td><td>16</td><td>32</td><td>64</td></tr><tr><td>SePHkr+ [5]</td><td>0.7364</td><td>0.7367</td><td>0.7451</td><td>0.7486</td><td>0.7514</td><td>0.7573</td></tr><tr><td>SePHkr+k[15]</td><td>0.7377</td><td>0.7459</td><td>0.7467</td><td>0.7522</td><td>0.7595</td><td>0.7599</td></tr><tr><td>GSPHklr+r [16]</td><td>0.7279</td><td>0.7425</td><td>0.7541</td><td>0.7579</td><td>0.7693</td><td>0.7760</td></tr><tr><td>GSPHklr+k [16]</td><td>0.7374</td><td>0.7485</td><td>0.7584</td><td>0.7614</td><td>0.7729</td><td>0.7798</td></tr><tr><td>UGACH [3]</td><td>0.6100</td><td>0.6045</td><td>0.5848</td><td>0.6278</td><td>0.6029</td><td>0.6101</td></tr><tr><td>DCMHoriginat [2]</td><td>0.7296</td><td>0.7363</td><td>0.7386</td><td>0.7639</td><td>0.7650</td><td>0.7703</td></tr><tr><td>DCMHvgg19 [2]</td><td>0.7433</td><td>0.7527</td><td>0.7592</td><td>0.7669</td><td>0.7792</td><td>0.7837</td></tr><tr><td>SCH-GAN [5]</td><td>0.7203</td><td>0.7481</td><td>0.7609</td><td>0.7661</td><td>0.7851</td><td>0.7884</td></tr><tr><td>本文算法</td><td>0.7410</td><td>0.7571</td><td>0.7718</td><td>0.7822</td><td>0.7915</td><td>0.7953</td></tr></table></body></html>

表3在Wikipedia数据集上的MAP

Tab.2The MAP scores on mirflickr dataset   
Tab.3The MAP scores on Wikipedia dataset   

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">image→text</td><td colspan="3">text→image</td></tr><tr><td>16</td><td>32</td><td>64</td><td>16</td><td>32</td><td>64</td></tr><tr><td>SePHk/r+r[15]</td><td>0.5009</td><td>0.5287</td><td>0.5393</td><td>0.5508</td><td>0.5955</td><td>0.6190</td></tr><tr><td>SePHkr+ [15]</td><td>0.4997</td><td>0.5252</td><td>0.5413</td><td>0.5584</td><td>0.6009</td><td>0.6122</td></tr><tr><td>GSPHklr+ [16]</td><td>0.5064</td><td>0.5289</td><td>0.5320</td><td>0.5701</td><td>0.6001</td><td>0.6237</td></tr><tr><td>GSPHklr+k [16]</td><td>0.5117</td><td>0.5318</td><td>0.5390</td><td>0.5801</td><td>0.6036</td><td>0.6207</td></tr><tr><td>UGACH[3]</td><td>0.3332</td><td>0.3605</td><td>0.3688</td><td>0.3222</td><td>0.3323</td><td>0.3471</td></tr><tr><td>DCMHoriginal [2]</td><td>0.4503</td><td>0.4506</td><td>0.4120</td><td>0.7419</td><td>0.7238</td><td>0.6940</td></tr><tr><td>DCMHvg19 [2]</td><td>0.4387</td><td>0.4698</td><td>0.4809</td><td>0.8279</td><td>0.8457</td><td>0.7927</td></tr><tr><td>SCH-GAN [5]</td><td>0.5207</td><td>0.5370</td><td>0.5076</td><td>0.8352</td><td>0.8351</td><td>0.8288</td></tr><tr><td>本文算法</td><td>0.5528</td><td>0.5712</td><td>0.5688</td><td>0.8426</td><td>0.8502</td><td>0.8572</td></tr></table></body></html>

图2和3分别给出了各个方法在Wikipedia和MIRFlickr数据集上的32位和64位哈希码所对应的PR-曲线。从图中可以看出，本文的方法比其他方法都要好。

→SePHr+6ePHr+kGSPHkir+GSPHkr+kUGACH→DCMHoriginalDCMHvgp19SCH-GANOurs image→text 32bits image→text 64bits   
88838 0.3 0.2 0.2 0.1 0.1 0.0 0.2 0.4 0.6 0.8 1.0 0.0 0.2 0.4 0.6 0.8 1.0 recall recall text→image 32bits text→image 64bits 1.0 1.0 0.9 0.8 二 0.9 号   
1 0.4 0.3 0.2 0.2 0.1 0.1 0.0 0.2 0.4 0.6 0.8 1.0 0.0 0.2 0.4 0.6 0.8 1.0 recall recall

![](images/5a699b74ec5e0970ef904560b419522eeccb6e2ff4e9175b06bef3a268b71c4c.jpg)  
图2在Wikipedia数据集上的PR曲线图  
Fig.2The PR-curves on Wikipedia dataset   
图3在MIRFlickr 数据集上的PR曲线图Fig.3The PR-curves on mirflickr dataset

此外，本文还在Wikipedia 数据集上比较了不同批量大小和正交正则化对模型训练的影响。批量大小分别设置为512，2048和8192。提高批量大小需要增加学习率，才能保证收敛速度，因此学习率分别为0.02、0.04和0.08。N表示不使用正交正则化，Y表示使用正交正则化。当不使用正交正则化时，用L2正则化来代替。即式(13)被替换为

$$
L _ { 4 } = \theta ( \left\| \boldsymbol { W } _ { T } \right\| _ { F r o } ^ { 2 } + \left\| \boldsymbol { W } _ { I } \right\| _ { F r o } ^ { 2 } ) + \omega ( \left\| \boldsymbol { B } _ { T } \right\| _ { F r o } ^ { 2 } + \left\| \boldsymbol { B } _ { I } \right\| _ { F r o } ^ { 2 } )
$$

其余参数配置都一样，所有的实验结果如表4所示。在评价性能好坏时，不仅需要看图像检索文本任务的MAP，也需要考虑文本检索图像任务的MAP，因此表4也给出了两个任务总的MAP。从表中可以看出，仅仅增大批量效果并不好，甚至还有所降低，这主要因为批量增大后，模型训练不稳定，网络泛化能力下降；而在使用同一个批量大小进行训练时，如果使用了正交正则化，会得到更好的果，但是每轮训练时间会增加。而增大批量可以加快训练速度，降低每轮训练的时间。总体上来看，当批量大小为8192，使用了正交正则化，本文方法得到了最好的结果。

# 3 结束语

在目前广泛应用的跨模态检索的研究领域，本文提出了一个新的跨模态哈希方法一一基于大批量训练和正交正则化的跨模态哈希方法。该方法采用三元组的方式输入数据，使用大批量训练方式进行训练，引入正交正则化使得模型训练更加稳定，并且还度量了哈希码和数据特征之间的距离，使得哈希码能够更好地表示数据。在两个广泛使用的Wikipedia和MIRFlickr数据集上的实验结果证明了该方法的有效性，相比现有的几种哈希方法具有更好的性能。

表4在Wikipedia 数据集上的不同批量大小训练

Tab.4The different batch size training on Wikipedia dataset   

<html><body><table><tr><td rowspan="2">批量大小</td><td rowspan="2">学习率</td><td rowspan="2">是否使用</td><td colspan="3">MAP (image→text)</td><td colspan="4">MAP (text→image)</td><td colspan="3">总的MAP</td><td colspan="3">每轮训练时间</td></tr><tr><td>正交正则化</td><td>16</td><td>32</td><td>64</td><td>16</td><td>32</td><td>64</td><td>16</td><td>32</td><td>64</td><td>16</td><td>32</td><td>64</td></tr><tr><td>512</td><td>0.02</td><td>N</td><td>0.5406</td><td>0.5506</td><td>0.5612</td><td>0.8280</td><td>0.8524</td><td>0.8432</td><td>1.3686</td><td></td><td>1.4030</td><td>1.4044</td><td>9.3s</td><td>9.6s</td><td>10.2s</td></tr><tr><td>512</td><td>0.02</td><td>Y</td><td>0.5588</td><td>0.5629</td><td>0.5691</td><td>0.8312</td><td>0.8576</td><td></td><td>0.8479</td><td>1.3900</td><td>1.4205</td><td>1.4170</td><td>16.0s</td><td>16.3s</td><td>16.8s</td></tr><tr><td>2048</td><td>0.04</td><td>N</td><td>0.5509</td><td>0.5594</td><td>0.5699</td><td>0.8231</td><td>0.8462</td><td></td><td>0.8326</td><td>1.3740</td><td>1.4056</td><td>1.4025</td><td>8.1s</td><td>8.2s</td><td>8.5s</td></tr><tr><td>2048</td><td>0.04</td><td>Y</td><td>0.5559</td><td>0.5668</td><td>0.5702</td><td>0.8380</td><td>0.8486</td><td></td><td>0.8545</td><td>1.3939</td><td>1.4154</td><td>1.4247</td><td>10.9s</td><td>11.0s</td><td>11.3s</td></tr><tr><td>8192</td><td>0.08</td><td>N</td><td>0.5487</td><td>0.5563</td><td>0.5649</td><td>0.8217</td><td>0.8431</td><td></td><td>0.8327</td><td>1.3704</td><td>1.3994</td><td>1.3976</td><td>7.5s</td><td>7.5s</td><td>7.9s</td></tr><tr><td>8192</td><td>0.08</td><td>Y</td><td>0.5528</td><td>0.5712</td><td>0.5688</td><td>0.8426</td><td>0.8502</td><td></td><td>0.8572</td><td>1.3954</td><td>1.4214</td><td>1.4260</td><td>8.2s</td><td>8.3s</td><td>8.6s</td></tr></table></body></html>

# 参考文献：

[1]Peng Yuxin,Huang Xin and Zhao Yunzhen.An overview of cross-media retrieval: Concepts,methodologies,benchmarks,and challenges [J]. IEEE Trans on Circuits and Systems for Video Technology,2018,28 (9): 2372-2385.   
[2]Jiang Qing Yuan and LiWu Jun.Deep cross-modal hashing[C]//Proc of the 3Oth IEEE Conference on Computer Vision and Pattern Recognition. Piscataway,NJ: IEEE Press,2017:3232-3240.   
[3]Zhang Jian,Peng Yuxin and Yuan Mingkuan.Unsupervised generative adversarial cross-modal hashing [C]// Proc of the 32nd AAAI International Conference on Artificial Intelligence.Palo Alto,CA:AAAI Press,2018:539-546.   
[4]Deng Cheng,Chen Zhaojia,Liu Xianglong,et al. Triplet-Based Deep Hashing Network for Cross-Modal Retrieval[J].IEEE Trans on Image Processing,2018,27(8): 3893-3903.   
[5]Zhang Jian，Peng Yuxin and Yuan Mingkuan.SCH-GAN: Semisupervised cross-modal hashing by generative adversarial network [J].

IEEE Trans on Cybernetics,2020,50 (2):489-502.

[6]Goyal P,Dollar P,Girshick R,et al.Accurate large minibatch SGD: Training imagenet in 1 hour [EB/OL]. (2018-04-30) [2020-02-16]. https://ar xiv.org/abs/1706.02677.   
[7]You Yang,Hseu J,Ying C,et al.Large-batch training forLSTM and beyond [C]// Proc of the 26th International Conference for High Performance Computing,Networking, Storage and Analysis.New York: ACM Press,2019:1-16.   
[8] Brock A,Donahue Jand Simonyan K.Large scale GAN training for high fidelity natural image synthesis [C/OL]/Proc of the 7th International Conference on Learning Representations.2019.(2019-02-26) [2020-02- 16] https://openreview.net/pdf?id=B1xsqj09Fm.   
[9]You Yang,Gitman I and Ginsburg B.Large batch training of convolutionalnetworks[EB/OL].(2017-09-13)[2020-02-16]. https://arxiv.org/abs/1708.03888.   
[10]Keskar N S,Mudigere D,Nocedal J,et al.On large-batch training for deep learning: Generalization gap and sharp minima [C/OL]/Proc of the 5th International Conference on Learning Representations.2017.(2017-   
02-10)[2020-02-16]. htps://openreview. net/pdf?id=H1oyRlYgg. [11]Brock A，Lim T,Ritchie JM,et al.Neural photo editing with introspective adversarial networks [C/OL]/Proc of the 5th International Conference on Learning Representations.2017.(2017-02-23) [2020-02-   
16].https://openre view. net/pdf?id=HkNKFiGex. [12]Wang Daixin,Peng Cui, Ou Mingdong,et al.Deep multimodal hashing with orthogonal regularization [C]//Proc of the 24th AAAI International Conference on Artificial Intelligence.Palo Alto,CA:AAAI Press,2015:   
2291-2297. [13] Pereira JC,Coviello E,Doyle G,etal.On the role of correlation and abstraction in cross-modal multimedia retrieval [J].IEEE Trans on pattern analysis and machine intelligence,2014,36(3): 521-535.   
[14]Huiskes MJand Lew MS.The MIR flickr retrieval evaluation [C]//Proc of the 1st ACM International Conference on Multimedia Information Retrieval.New York:ACMPress,2008:39-43.   
[15]Lin Zijia,Ding Guiguang,Hu Mingqing,et al. Semantics-Preserving Hashing for Cross-View Retrieval [C]// Proc of the 28th IEEE Conference on Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2015:3864-3872.   
[16]Mandal D,Chaudhury K N and Biswas S.Generalized semantic preserving hashing for cross-modal retrieval [J]. IEEE Trans on Image Processing,2019,28(1):102-112.