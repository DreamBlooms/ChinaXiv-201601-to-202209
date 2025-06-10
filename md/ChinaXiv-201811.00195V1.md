# 基于深度双向模型和特征融合的视频转文字研究

宁培阳，史景伦，张荣锋，邱威(华南理工大学 电子与信息学院，广州 510640)

摘要：自动生成视频的自然语言描述，是一个非常具有挑战性的研究热点。基于深度BLSTM模型和CNNs 特征的方法，能够学习到视频序列的全局时空关联信息。针对视频转文字时面临的准确率低以及计算复杂度高的问题，提出了深度BMGU模型，从而在保持深度 BLSTM模型结构优势的同时提高计算效率；还将原始视频帧的CNN特征，与经过Haar 特征预处理后的视频的CNNs特征进行后期融合，从而增加了训练特征的多样性，进而提升了视频转自然语言的实验效果。在 M-VAD和MPII-MD数据集中，相对原 S2VT模型，所提方法分别将 METEOR分数从6.7及7.1提高到8.0和8.3。结果表明所提方法有效地改善了原S2VT模型的准确率和语言描述效果。

关键词：视频转文字；深度双向模型；哈尔特征；特征融合；卷积神经网络 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.03.0488

# Research on video description based on deep bidirectional model and feature fusion

Ning Peiyang, Shi Jinglun, Zhang Rongfeng, Qiu Wei (School of Electronic & Information Engineering,South China University ofTechnology,Guangzhou 510641,China)

Abstract: Automatically generating a natural languagedescriptionof avideo is achallenging work for computer vision.The method basedon dep bidirectional long-short term memory(DBLSTM)and CNN feature,hadtheability to lear global spatiotemporalcorelationinformationof videos.Focusingonthelowaccuracyand high computational complexityof video to text,this paperproposedanewmethod,whichbasedonthedepbidirectional minimal gatedunit (BMGU) inordertoimprove the computational eficiency while maintaining the advantages in structureof the deep BLSTM model.In the same time,by merging the CNNs feature ofthe original frames andthe CNNs featureof the frames with Haar feature increasedthe diversity oftraining features and improved the efect of the video totext.Byusing thedatasets ofM-VADand MPI-MD,comparing to theoriginalS2VTmodel,theproposed methodisabletoincrease thescores from6.7to8.0andfrom7.1to8.3inMETEOR. The results show thatthe proposed methodcan efectively improve theaccuracyandthe descriptionofthevideos oftheoriginal S2VT model.

Key words: video to text; deep bidirectional model; haar feature; feature fusion;convolutional neural networks

# 0 引言

视频转自然语言（video captioning,又称自动生成视频的自然语言描述)，其主要任务是对视频进行理解和分析，并进一步获取有用的语义信息，然后，将这些视频帧中的语义信息与应用的语义环境进行关联，从而将视频帧序列转换为自然语言描述[1。视频转自然语言可用于智能安防、人机交互、视频检索等诸多领域，具有较高的应用价值和现实意义。

随着深度学习在计算机视觉的诸多领域的逐步延伸，以S2VT[2]（sequence to sequence-video to text）为代表的视频转文字方法，在性能上显著地超越了以往的非深度学习方法，但也仍存在若干方面需要改进。例如，为了获取视频帧中所包含的语义信息，一般先使用CNN模型来提取视频帧的卷积特征[3]，卷积特征中包含视频帧的空间信息。然而，视频描述数据集中的视频帧常常存在背景繁杂（存在多种对象）的情况，某些CNNs模型提取这类视频帧的特征时性能会降低，导致视频转文字方法不能输出较为准确的自然语言描述。另外，LSTM是S2VT方法的核心模型，它通过将RNN(recurrentneuralnetworks)无门的结构改进为具有三个门结构和两个隐藏状态的结构，较好地克服了梯度弥散或梯度爆炸的问题，从而具有对长序列信息进行较好地学习和建模的能力[4,5]。然而LSTM增加了大量的参数，降低了方法的计算效率，不利于将其应用于实时性要求高、计算条件严苛的场合。并且，近年来Chung 等人[通过实验发现，门结构的数量越多并不意味着最终的实验效果会更好，一些较为简单的RNN 模型在降低了计算复杂度的同时，甚至还能够收到比LSTM更好的效果。

针对 S2VT方法中存在的描述准确率低、计算复杂等问题，本文提出了基于深度双向循环神经网络[7]和哈尔特征[8]（Haarfeature）的视频转文字方法，具体如下：首先，针对S2VT模型（其编码层基于单向LSTM）不能充分学习视频序列中前后帧的时序信息的问题，提出基于深度双向LSTM的视频转文字方法以学习到全局的时间关联信息。其次，针对视频帧具有背景繁杂的特点，而影响对主体对象的特征提取的问题，提出基于Haar特征预处理的视频帧增强方法，即在使用VGG等卷积神经网络提取视频帧的隐式特征前，通过提取Haar特征对视频帧进行预处理，以达到抑制繁杂背景信息和强化主体对象信息的目的；再次，针对深度BLSTM计算复杂度高的问题，提出基于深度BMGU的视频转文字方法。实验表明，这种基于简化模型的方法，不仅能够有效地提高计算效率，而且自然语言描述的效果也与深度BLSTM模型相当。

# 1 视频转自然语言原理与S2VT模型

视频转自然语言的任务，在数学上可以表述为：给定视频的帧序列 $\mathbf { X } ( x _ { I } , x _ { 2 } , . . . , x _ { t } , . . . \ : x _ { n } )$ ，给出关于概括视频语意信息的词序列 $\mathbf { Y } ( y _ { I } , y _ { 2 } , . . . , y _ { t } , . . . y _ { m } )$ 的条件概率，即

$$
p ( \mathbf { Y } / \mathbf { X } ) = p \big ( y _ { 1 } , . . . , y _ { m } \big | x _ { 1 } , . . . , x _ { n } \big )
$$

其中：帧序列长度 $n$ 和词序列长度 $m$ 是可变的。一般地， $\scriptstyle n \neq m$ 且 $n > m$ 。基于循环神经网络的视频转文字方法，通过构造"编码器-解码器（encoder-decoder）"模型，从而使用隐式特征来实现帧序列和词序列的联合建模。相应地，可把式(1)改写为

$$
p ( \mathbf { Y } / \mathbf { X } ) = p \left( y _ { 1 } , . . . , y _ { m } | x _ { 1 } , . . . , x _ { n } \right) { = } \prod _ { t = 1 } ^ { m } p \left( y _ { t } \mid h _ { n + t - 1 } , y _ { t - 1 } \right)
$$

S2VT[2]具有理解和描述视频内容的功能，它是一个经典的、基于LSTM的视频转文字模型，能够生成自然语言的句子来描述视频中所发生的相应事件。

![](images/b04c49f123694fe686fc268fc9d444b57502063c3d24cb25658322befc708605.jpg)  
图1S2VT模型原理图

如图1所示，S2VT模型通过VGG-16[9网络获取输入视频序列的卷积特征（CNNs特征)，再将特征序列按时序地输入第一层LSTM进行特征建模；在第二层LSTM中，通过LSTM网络学习帧序列与词序列之间的映射关系，完成特征和语言的关联建模。另外，图中"<Pad>"表示用全零向量作为输入来填充相应的位信息，输入 $\mathrm { \mathop {  } { s o s } } \mathrm {  { > } { } } ^ { \mathrm { , } }$ ”则表明帧序列已输入完毕，用于指示模型从编码阶段切换到解码阶段（即开始预测词序列）。： $\mathrm { \check { \cdot } \mathrm { < E O S > } } ^ { \mathrm { , } }$ 表示 S2VT模型预测的词序列已输出完毕。

LSTM是S2VT模型实现式(2)功能的核心算法，具体计算上，假设在时刻 $t$ 输入的变量是 $x _ { t }$ ，对应的隐藏层状态参数是$h _ { t }$ ，而记忆单元的状态是 $c _ { t }$ ，则在 $t$ 时刻LSTM单元中的公式如下[5]：

$$
\begin{array} { r l } & { \boldsymbol { i } _ { t } = \mathbb { C } ( W _ { x } \boldsymbol { x } _ { t } + W _ { h } \boldsymbol { h } _ { t - 1 } + b _ { t } ) } \\ & { \boldsymbol { f } _ { t } = \mathbb { C } ( W _ { \boldsymbol { x } ^ { T } } \boldsymbol { x } _ { t } + W _ { h } \boldsymbol { h } _ { t - 1 } + b _ { f } ) } \\ & { \mathbf { o } _ { t } = \mathbb { C } ( W _ { w } \boldsymbol { x } _ { t } + W _ { b _ { t } } \boldsymbol { h } _ { t - 1 } + b _ { o } ) } \\ & { \mathbf { g } _ { t } = \varphi ( W _ { \mathbf { x } } \boldsymbol { x } _ { t } + W _ { h } \boldsymbol { h } _ { t - 1 } + b _ { t } ) } \\ & { \boldsymbol { c } _ { t } = \boldsymbol { f } _ { t } \odot \boldsymbol { c } _ { t - 1 } + \boldsymbol { i } _ { t } \odot \boldsymbol { g } _ { t } } \\ & { \boldsymbol { h } _ { t } = \boldsymbol { f } _ { t } \odot \boldsymbol { \phi } ( \boldsymbol { c } _ { t } ) } \end{array}
$$

在式 $( 3 ) \sim ( 8 )$ 中， $i , f , o , g$ 分别表示LSTM的输入门、遗忘门、输出门、输入调制栅,对应的各门偏置向量为 $b _ { i }$ 、bf、$b _ { c }$ 、 $b _ { g }$ 。 $h _ { t } \in R ^ { n }$ 表示 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个隐藏状态参数。 $\boldsymbol { W _ { a b } }$ ( $a \in \{ x , h \}$ ， $b \in$ $\{ i , h , o , g \}$ ）表示输入或隐藏层状态参数 $a$ 到门 $b$ 的权重矩阵。$\sigma ( x )$ 是sigmoid 函数， $\varphi ( x )$ 是双曲正切函数，而 $\odot$ 是逐元素点积（element-wise product）运算。通过式 $( 3 ) \sim ( 8 )$ ，S2VT模型依次迭代求出各时刻的隐藏层参数 $h _ { I } , h _ { 2 } , . . . h _ { t } , . . . h _ { n }$ ，并进一步求出隐藏层参数关于词 $y _ { t }$ （ $\mathbf { \Phi } _ { t = 1 , 2 , \dots , m }$ ）的条件概率 $p ( y _ { t } | h _ { n + t } )$ ，从而得到预测的词序列。

# 2 改进方法的提出

# 2.1基于DBLSTM与Haar特征预处理的视频转文字方法

首先，针对S2VT模型的基于单向LSTM编码层对视频帧特征利用不充分的问题，采用深度双向LSTM（DBLSTM）网络对方法进行改进。基于深度双向LSTM的视频转文字方法原理图如图2所示。

![](images/1dce3b419bb40d0a1399a47a5f12d64aaf6fdf58e034866a2be2567090710c5f.jpg)  
Fig.1Schematic diagram of S2VT model   
图2基于深度双向LSTM的视频转文字方法原理图  
Fig.2Schematic diagram of video-to-text based on depth bidirectional

其中，一个正向传输信息的 LSTM 和一个反向传输信息的LSTM组成了BLSTM，2个BLSTM再按图3中的连接组成DBLSTM。关于两层LSTM隐藏层状态参数的融合，一般使用如下的方法[];

$$
\begin{array} { c } { { { \vec { h } } _ { t } = H \left( W _ { _ { x \vec { h } } } x _ { t } + W _ { _ { \vec { h } \vec { h } } } { \vec { h } } _ { t - 1 } + b _ { \vec { h } } \right) } } \\ { { { \vec { h } } _ { t } = H \left( W _ { _ { x \vec { h } } } x _ { t } + W _ { _ { \vec { h } \vec { h } } } { \vec { h } } _ { t + 1 } + b _ { \vec { h } } \right) } } \\ { { y _ { t } = W _ { _ { \vec { h } \vec { y } } } { \vec { h } } _ { t } + W _ { _ { \vec { h } \vec { y } } } { \vec { h } } _ { t } + b _ { h } } } \end{array}
$$

其中： $\vec { h } _ { \iota }$ 、 $\ddot { h } _ { { t } }$ 分别是正向传输层、反向传输层中LSTM在 $\mathbf { \chi } _ { t }$ 时刻的隐藏层状态参数， $\mathrm { H } ( x )$ 为LSTM的激活函数， $y _ { t }$ 是融合后的输出。其余参数的含义与式(3)\~(8)的参数含义类似。

通过将两个BLSTM网络的堆叠而构成深度BLSTM网络，来作为深度RNN网络的一种改进方法。这使得新网络结构具有下面的优点：首先，BLSTM除了能够学习到前面帧的相关信息（informationinpreviousframes），还能够学习到未来帧的相关信息（informationinfutureframes），通过前后帧的关联学习以及上下文的关联学习，因而可利用视频中的全局时间信息以增强视频-句子对的学习效果，从而提高了视频转自然语言的准确率。这样就可以有效克服单向LSTM只能利用前面帧的相关信息的局限性。其次，在深度神经网络（deepneuralnetwork）中，通过拓宽网络的宽度（widerandwider）和增加网络的深度（deeperanddeeper）是优化并提高模型性能的两个主要方向：相对应于CNNs网络在空间上的深度，LSTM则是时间上的深度网络，双向LSTM（BLSTM）相对单向LSTM是在时间维度上更深(deeper in time)的网络，因此，BLSTM相比LSTM增强了网络在时间上的依赖性，而深度BLSTM则进一步强化了其时间上的依赖性。增加时间深度的方式，增加了网络的参数，也使得训练时可以增强视频和自然语言的关联学习，从而进一步提高了视频转文字的训练和学习效果，进而提高了视频转文字的实验效果（在实验结果上的直观表现为METEOR分数的提高)。当然，更深的网络就包含了更多的参数，因而也增加了计算复杂度。

其次，针对视频繁杂的背景可能影响CNN对主体特征的提取的情况，对视频帧按RGB三个通道进行分离，并逐通道进行一阶Haar小波滤波，滤除细节信息，最后重组，从而得到包含了Haar特征的视频帧。流程如图3所示。

![](images/0af5ea8f10b5dcdf6005af6350a7097bf0b0b4e70ff8889c5213137e0275be79.jpg)  
图3视频帧提取Harr特征的流程图

由对比图3中处理前后的图片可知，经过提取Haar特征后的视频帧中，视频帧的主体信息得到了保留和增强，而较为繁杂的背景信息则相对被削弱了一些，从而提供了帧序列的语

义信息。

# 2.2基于DBMGU与 Haar 特征预处理的视频转文字方法

将DBLSTM模型应用于视频转文字，在获得效果提升的同时，还应注意到：如前文述及，由于模型参数的明显增多，计算复杂度增大，往往增加了训练时间，不利于将其应用于实时性要求高的场景。针对这些问题,利用 MGU[10](minimal gatedunit）模型的精简性以简化计算参数，从而减少训练时间。而针对视频帧提取Haar特征，往往能够提供较好的语义信息，因此，提出基于DBMGU模型与特征融合的视频转自然语言方法。

最少门单元 MGU[10]作为RNNs 模型的一种简化模型，其主要特点是仅具有1个门结构，因而被命名为"最少门单元”。在 $t$ 时刻MGU单元的计算公式如下(计算符号含义与式(3)\~(8)一致):

$$
f _ { t } = \sigma ( W _ { h f } h _ { t - 1 } + W _ { x f } x _ { t } + b _ { f } )
$$

$$
\tilde { h } _ { t } = \varphi ( W _ { h h } \left( f _ { t } \odot h _ { t - 1 } \right) + W _ { x h } x _ { t } + b _ { h } )
$$

$$
h _ { t } = ( 1 - f _ { t } ) \odot h _ { t - 1 } + f _ { t } \odot \tilde { h _ { t } }
$$

MGU模型的参数远远比LSTM要少（相同条件下约为LSTM模型的二分之一)，理论上其计算复杂度明显低于LSTM,从而MGU模型有效地降低了计算开销，进而提高了训练速度。其次，Chung等人的研究表明，拥有门结构的RNNs类网络，相对于简单地使用双曲正切函数且没有门结构的RNNs网络，一般来说，在实验效果上有较显著的提升[6]。MGU模型遵循了这个结论，保留了必要的一个门结构，使得序列数据的学习效果可以得到保证。为了直观表现LSTM、MGU一个时间步内计算复杂度的差异，参考周国兵等人[10]的研究工作，绘出两者的单元结构如图4所示。

![](images/9338216242c944cafb2ccaaf6e8038a15b2bd2e25775505c874a39989a38114a.jpg)  
Fig.3Flowchart of extractingHarr features fron video frames   
图4一个时间步内LSTM与MGU的计算流程  
Fig.4Calculating process of LSTM and MGU within a time step

DBMGU的构造方法与DBLSTM的构造方法相同。基于DBMGU模型和特征融合的视频转文字方法，是将DBLSTM模型替换为DBMGU模型，同时为了便于对比，也采用经Haar 特征预处理后的特征来提高模型的效果。

# 3 模型实验与分析

# 3.1实验方法

如图3所示,经过Haar特征预处理后，视频中的主体目标得到了增强，而其他次要目标则相对地被削弱了，从而提供了一定的语义信息，再对这些视频帧提取CNNs 特征，因而获得包含了Haar特征的CNNs特征，这是与原视频帧的CNNs 特征不同的新特征。同时，鉴于有效的特征融合往往能够提高视频转自然语言描述的准确率和语言效果[I]，本文也将原始视频帧的CNNs特征与包含Haar特征的CNNs特征进行融合，从而增加了训练特征的种类，进而增强了视频特征学习的丰富性，优化学习的效果。如图5所示，本文将原始视频帧的CNNs特征与包含了Haar特征的CNNs 特征进行融合，以提高视频转自然语言描述的实验效果。

![](images/d724c8475b9ff5a3dd481f2c204bac5c0a7b48e9bcd4f0d9cd9fa26ad512c23f.jpg)  
图5视频转自然语言实验的模型框架  
Fig.5Model framework of video-to-natural language   
图6两种方法的METEOR评测分数与迭代次数的关系  
Fig.6Relationship between METEOR evaluation scores and iterations of two methods

在基于小波与DBLSTM的视频转自然语言方法中，图中“深度双向RNN"具体为DBLSTM模型。在DBMGU与特征融合的视频转自然语言方法中，图中"深度双向RNN"则具体为DBMGU 模型。为了便于描述，在以下实验结果图表中，将基于DBLSTM和特征融合的视频转自然语言方法简称为"DBLSTM_VGG&Wavelet_Fusion"，将基于DBMGU与特征融合的视频转自然语言方法简称为“DBMGUVGG&Wavelet_Fusion”。

本文使用 Caffe[12]（convolutional architecture for fast featureembedding)深度学习框架实现实验模型。使用M-VAD和MPII-MD 两种主流视频标注数据集独立地对模型进行训练和测试。为了充分利用样本的信息，在训练时综合考虑每个样本的帧序列和词序列的长度，自适应地抽取数量合适的视频帧；在测试时则仅考虑每个样本的帧序列长度对视频帧进行采样。另外，关于视频标注句子与本文方法所生成句子的对比及评价，则使用METEOR评测指标作为本文方法输出语句的客观评价指标。METEOR[13]是Lavir等人发现在评价指标中召回率的意义后于

2004年提出的评价指标。他们的研究表明，在考虑了召回率的指标相比于单纯基于准确率的指标，其结果和人工判断的结果有较高相关性。因而METEOR评测指标常作为机器翻译、图像转自然语言、视频转自然语言等领域的评价参考，例如Rohrbach等人[14]在他们的视频转文字研究中就以METEOR作为客观评价指标。模型训练的主要超参数（HyperParameter）见表1。另外，采用的初始学习率为0.01，学习率调整方法为：每2万次迭代将学习率降低为原来的二分之一；训练优化方法为Mini-Batch下的SGD，momentum设定为0.9；正则化方法为 Dropout。

表1模型训练的主要超参数  
Table 1Hyper parameter of model training   

<html><body><table><tr><td>超参数</td><td>值</td></tr><tr><td>RNN 模型的 time step</td><td>80</td></tr><tr><td>RNN 模型的输出向量长度</td><td>1000</td></tr><tr><td>batch size</td><td>16</td></tr><tr><td>迭代次数</td><td>60000</td></tr><tr><td>视频特征降维的全连接层尺寸</td><td>4096*500</td></tr><tr><td>词向量降维的全连接层尺寸</td><td>46168*500</td></tr><tr><td>生成词向量的全连接层尺寸</td><td>1000*46168</td></tr></table></body></html>

# 3.2 实验结果分析

参考Rohrbach等人[15]的实验分析方法，通过METEOR指标评测，以及对标注句子与两种方法生成的句子进行分析比较两个角度，对模型效果进行评估。

首先，在4万\~6万次迭代之间，取偶数千次迭代下的模型进行评测，整理得到两种方法的 METEOR 评测分数与迭代次数的关系如图6所示。

-DBLSTM_VGG&Wavelet_Fusion 一DBMGU_VGG&Wavelet_Fusion 8.2 %T 8.0 7.8 7.6 7.4 7.2 40 42 44 4648505254565860 迭代次数/千次 (a)M-VAD数据集 (a) M-VAD dataset -DBLSTM_VGG&Wavelet_Fusion ←DBMGU_VGG&Wavelet_Fusion MP 8.1 7.9 7.7 7.5 40 42 44 46 48 505254 56 5860 迭代次数/千次 (b)MPII-MD 数据集 (b)MPII-MD dataset

分析图6可知，两种方法的METEOR评测分数均较为稳定，可以说明它们在不同的数据集下均能较好地收敛。将图6中两种方法的METEOR评测分数的峰值整理，并与其他视频转文字方法的 METEOR评测分数的峰值比较，结果如表2所示。METEOR单位为 $0 \%$ ，越高效果越佳。

表2M-VAD与MPII-MD数据集的METEOR评测  
Table2METEOR Evaluation of M-VAD andMPII-MD datasets   

<html><body><table><tr><td>方法</td><td>M-VAD</td><td>MPII-MD</td></tr><tr><td>Visual-Labels[15]</td><td>6.3</td><td>7.0</td></tr><tr><td>Mean pool(VGG)[16]</td><td>6.1</td><td>6.7</td></tr><tr><td>S2VT:RGB(VGG)[2]</td><td>6.7</td><td>7.1</td></tr><tr><td>DBLSTM_VGG&Wavelet_Fusion</td><td>7.9</td><td>8.1</td></tr><tr><td>DBMGU_VGG&Wavelet_Fusion</td><td>8.0</td><td>8.3</td></tr></table></body></html>

分析表2可知，对于M-VAD数据集而言，文中提出的2种方法在METEOR分数上将原S2VT模型的 $6 . 7 \%$ ，分别提高到了 $7 . 9 \%$ 和 $8 . 0 \%$ ；同样地，在MPII-MD 数据集上，文中的2个方法，将原S2VT模型的 $7 . 1 \%$ ，分别提高到了 $8 . 1 \%$ 和 $8 . 3 \%$ 。一方面，两种方法的METEOR评测分数均高于之前的视频转文字方法的 METEOR 分数，这说明深度双向模与特征融合的有机结合，可以提升视频转文字的准确率和语言效果。另一方面，本文提出的两种方法，在视频特征建模部分分别使用的是DBLSTM 模型和DBMGU 模型。使用DBMGU 模型，相对DBLSTM模型，METEOR分数不仅没有降低甚至还略有提高，这说明DBMGU模型虽然比DBLSTM模型少了近一半的参数，但是所生成的句子与DBLSTM所生成的句子在语言效果上相近。更为重要的是，DBMGU模型可以有效的降低计算复杂度，降低计算开销从而提高视频转文字的速度。

本文对标注句子与两种方法生成的句子进行分析比较。因篇幅限制，每个数据集挑选三个例子作为示例，如图7所示。可知，两种方法生成的句子，不仅描述准确，而且相对标注句子包含了更多的细节信息，增加了语言的丰富性。验证了本文所提方法，可以有效提升视频转文字的准确率和语言效果。

手工标注句子：They tour the campus.   
DBLSTM_VGG&Wavelet_Fusion：Someone and someone walk up to the sidewalk.   
DBMGU_VGG&Wavelet_Fusion：Someone and someone watch as someone and someone walk up to the front lawn. (a)M-VAD 实例1 (a) M-VAD examplel

![](images/0384623d384a7c78770fd93326a20b850e075a21f5f81185de99edcff6a79b8a.jpg)

手工标注句子：Nowalunchdate. DBLSTM_VGG&Wavelet_Fusion：Someone glances at someone who smiles and nods. DBMGU_VGG&Wavelet_Fusion：Someone glances at someone who sits on the couch

and smiles at someone. (b)M-VAD实例2 (b)M-VAD example2

![](images/89518b63276ca8bb8e377ee4811eb35ff6acd61614a4eb7992914c33fbd50fe0.jpg)

手工标注句子：Aboyenters. DBLSTM_VGG&Wavelet_Fusion：Someone turns away and someone follows him to the door. DBMGU_VGG& Wavelet_Fusion：Someone steps into the living room and finds someone staring at the door then faces someone. (c)M-VAD 实例3 (c)M-VAD example3

![](images/26067aa54bf80055ba2335ebcc6c62954bca3ca66175cf287c9f3259841af0d6.jpg)  
图7来自M-VAD和MPII-MD数据集的视频描述实例

![](images/a87bb13cb478d5efa271795c296e5c5953cff052da4750f584ceec39a7418b6c.jpg)

手工标注句子：She nods sleepily. DBLSTM_VGG&Wavelet_Fusion：Someone is lying on the bed. DBMGU_VGG&Wavelet_Fusion：Someone sits on the bed and looks at her. (d)MPII-MD 实例1 (d) MPII-MD examplel

![](images/bdbe178ef3316b4e8844380c3e247e1535839dbb2d8d97dafb253a1f1c18e75d.jpg)

手工标注句子：He sits up. DBLSTM_VGG&Wavelet_Fusion:Someone is sitting on the bed. DBMGU_VGG&Wavelet_Fusion：Someone sits on the bed and looks at the ceiling. (e)MPII-MD 实例2 (e)MPII-MD example2

![](images/fc7d443c23f0ba2de58f7a1382350f65d4b1f9f6e4db174512ae35dea3aca0a0.jpg)

手工标注句子：They turn and walk away together. DBLSTM_VGG&Wavelet_Fusion：Someone is walking along the sidewalk. DBMGU_VGG&Wavelet_Fusion：Someone walks up to the front of the house and looks at someone. (f)MPII-MD 实例 3 (f)MPII-MD example3

Fig.7Video description examples from M-VAD andMPI-MD datasets

# 4 结束语

本文针对S2VT方法中存在的描述准确率不高的问题，在

DBLSTM与特征融合的视频转自然语言方法的基础上，提出基于DBMGU与特征融合的视频转自然语言方法。所提方法有效地改善了原 S2VT模型的准确率和语言效果。其中，DBMGU模型的参数数量仅约为DBLSTM模型一半，减少了计算开销，提高了计算速度，却取得了与DBLSTM 模型相近的语言描述效果，使得所提方法具有广泛的应用场景。当然，当前的工作还存在一些不足，在后期的研究工作中，将针对S2VT方法的解码模型、语言模型等方面，做进一步的改进工作。

# 参考文献：

[1]Kojima A，Izumi M,Tamura T,et al.Generating natural language description of human behavior from video images [C]//Proc of the 15th International Conference on Pattern Recognition.Washington DC:IEEE Computer Science,2000:728-731.   
[2]Venugopalan S,Rohrbach M,Donahue J,et al. Sequence to sequence-video to text [C]//Proc of IEEE International Conference on Computer Vision. Piscataway,NJ: IEEE Press,2015: 4534-4542.   
[3]Donahue J,Hendricks L A,Rohrbach M,et al.Long-term recurrent convolutional networks for visual recognition and description [J]. IEEE Trans on Pattern Analysis and Machine Intelligence.2017,39 (4): 677-691.   
[4] Jozefowicz R, Zaremba W, Sutskever I. An empirical exploration of recurrent network architectures [C]// Proc of the 32nd International Conference on Machine Learning.New York:ACMPress,2015:2342-2350.   
[5]Hochreiter S,Schmidhuber J.Long short-term memory [J].Neural Computation.1997,9(8): 1735-1780.   
[6]Chung J,Gulcehre C,Cho KH,et al.Empirical evaluation of gated recurrent neural networks on sequence modeling [EB/OL].(2015) [2018-06-01]. https://arxiv.org/abs/1412.3555.   
[7]Graves A, Jaitly N,Mohamed AR.Hybrid speech recognition with Deep Bidirectional LSTM[Cl//Proc of IEEE Workshop on Automatic Speech Recognition and Understanding.Piscataway,NJ: IEEE Press,2013:273-278.   
[8]Papageorgiou C P,Oren M,Poggio T.A general framework for object detection [C]//Proc of IEEE International Conference on Computer Vision. Piscataway,NJ,IEEE Press,2002:555-562.   
[9]Simonyan K, Zisserman A. Very deep convolutional networks for largeScale image recognition [EB/OL]. (2014) [2018-06-01]. https://arxiv. org/abs/1409.1556.   
[10] Zhou Guobing,Wu Jianxin,Zhang Chenlin,et al.Minimal gated unit for recurrent neural networks [J]. International Journal of Automation and Computing.2016,13 (3): 226-234.   
[11]梁锐，朱清新，廖淑娇，等．基于多特征融合的深度视频自然语言描述 方法[J].计算机应用.2017,37(4):1179-1184.(Liang Rui,Zhu Qingxin, Liao Shujiao,et al. Deep natural language description method for video based on multi-feature fusion [J]. Journal of Computer Applications.2017, 37 (4): 1179-1184.)   
[12] Jia Yangqing，Shelhamer E,Donahue J，et al.Caffe:convolutional architecture for fast feature embedding [C]// Proc of the 22nd ACM International Conference on Multimedia.New York:ACMPress,2014:675- 678.   
[13] Denkowski M,Lavie A. Meteor universal: language specific translation evaluation for any target language [C]// Proc of the 9th Workshop on Statistical Machine Translation.Cambridge,MA: MITPress,2014: 376-380.   
[14] Rohrbach A,Rohrbach M,Schiele B.The long-short story of movie description [C]//Proc of German Conference on Pattern Recognition.Berlin: Springer,2015: 209-221.   
[15]Rohrbach A,Rohrbach M,Tandon N,et al.A dataset for movie description [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. New York: IEEE Press,2015: 3202-3212.   
[16] Venugopalan S,Xu Huijuan,Donahue J,et al. Translating videos to natural language using deep recurrent neural networks [C]// Proc of Annual Conference of the North American Chapter of the ACL.Cambridge,MA: MIT Press,2015:1494-1504.