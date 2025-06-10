# 基于组反馈融合机制的视频超分辨率模型

张庆武」，迟小羽²，朱鉴1，陈炳丰1，蔡瑞初1(1．广东工业大学 计算机学院，广州 510006;2.北京航空航天大学 青岛研究院，山东 青岛 266000)

摘要：视频超分辨率(video super-resolution，VSR)，其目的是利用多个相邻帧的信息来生成参考帧的高分辨率版本。现有的许多VSR工作都集中在如何有效地对齐相邻帧以更好地融合相邻帧信息，而很少在相邻帧信息融合这一重要步骤上进行研究。针对该问题，提出了基于组反馈融合机制的视频超分辩模型(GFFMVSR)。具体来说，在相邻帧对齐后，把对齐视频序列输入第一重时间注意力模块，然后，把序列分成几个小组，各小组依次通过组内融合模块实现初步融合。接着，不同小组的融合结果经过第二重时间注意力模块。然后，各小组逐组输入反馈融合模块，利用反馈机制反馈融合不同组别的信息，最后，把融合结果输出重建。经验证，该模型具有较强的信息融合能力，在客观评价指标和主观视觉效果上都优于现有的模型。

关键词：视频超分辨率；时间注意力；反馈机制；分组融合 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2022.03.0112

Video super-resolution model based on group feedback fusion mechanism

Zhang Qingwu1, Chi Xiaoyu², Zhu Jian1, Chen Bingfengl†, Cai Ruichu1 (1.SchoolofComputers,GuangdongUniversityoftechnologyGuangzhou5o6,China;2.QingdaoResearchIstituteof Beihang University,Shandong Qingdao 266oo0,China)

Abstract: Video super-resolution(VSR),whichaims to exploitinformation frommultipleadjacent frames to generateahighresolutionversionofareference frame.Many existing VSR works focus onhowto effectively align adjacent frames tobetter fuse adjacentframeinformation,andlitleresearchhasbeendoneonthe important stepofadjacentframeinformation fusion. To solve this problem,This paper propose a video super-resolution model based on group fedback fusion mechanism (GFFMVSR).Specifically,afteradjacentframesarealigned,thealignedvideosequencesarefed into the firsttemporal atention module.Then,the sequence is divided intoseveral groups,and each group achieves preliminary fusion through the intra-group fusion module inturn.Next,thefusion resultsofdiferent groups gothroughasecond temporalattntion module. Then,each group inputs the fedback fusion module group by group,anduses the feedback mechanismto feedback and fuse theinformationofdiferent groups.Finaly,the fusionresultoutput isreconstructed.Ithasbeenverifiedthatthe modelhas stronginformationfusionabilityandissuperiortotheexisting models inbothobjectiveevaluationindicatorsandsubjective visual effects.

Key words: video super-resolution; temporal attention; feedback mechanism; group fusion

# 0 引言

超分辨率(super-resolution，SR)是指将相应的低分辨率(low-resolution,LR)图像重建为高分辨率(high-resolution,HR)图像的过程。根据输入帧的数量，SR任务可以可分为两类：单图像超分辨率(single-image super-resolution，SISR)和视频超分辨率(video super-resolution，VSR)。本文是关于视频超分辨率(VSR)任务的研究。VSR 在计算机视觉和图像处理研究领域引起了广泛的关注，具有广泛的应用前景。例如，当监控录像被放大以识别人或车牌时，或者当视频被投影到高清晰度显示器上以获得视觉上的愉悦时，就需要它。

近年来，随着深度学习的发展，基于深度学习的超分辨率算法在性能上有了极大的提高。第一个基于深度学习的SISR 算法是由Dong 等人[1]提出的SRCNN。它由三个卷积层组成，通过端到端的方式学习LR图像到HR图像的非线性映射，并展示了令人印象深刻的潜力。此后，许多深度学习方法被应用到SISR领域。例如，Kim等人[3]受到VGG[2]的启发而提出的VDSR，采用更深层次的卷积网络架构。Li等人[4提出了一个通过反馈连接使用更多的上下文信息来纠正低级特征学习的网络架SRFBN。盘等人[5]提出了一个应用残差中的残差(RIR)和结合使用空间、坐标注意力充分提取和复用特征的网络架构FFAMSR。尽管这些网络实现了最先进的性能，但高计算成本和内存占用限制了它们在移动设备上的应用。为了解决这个问题，一些轻量级网络被提出来，例如FALSR-A[6]、SMSR[7]。

在VSR领域，Huang等人[8]提出了一种名为BRCN的双向循环卷积网络，可以对跨多帧的长期时间信息进行建模，从而提升了VSR的质量。Caballero等人[提出了VESCPN，该网络通过端到端的方式联合训练光流估计和时空网络，从而实现了高效的VSR。Tao 等人[I0]提出了SPMC，该网络通过设计的亚像素运动补偿模块同时实现了运动补偿和上采样，Kim 等人[I受3DCNN固有的时空学习能力启发提出了3DSRNet，该网络通过堆叠多个3D卷积层进行VSR并避免了直接的运动对齐。Jo等人[I2]提出的DUF利用3DCNN来挖掘时空信息，并预测一个动态上采样滤波器[13]进行隐式运动补偿和上采样，从而代替在像素层面进行的光流估计和对齐。Haris等人[14]提出的RBPN通过使用循环编解码模块来利用空间和时间信息。TDAN[15]和EDVR[16]把可变形卷积应用于VSR领域并提出了一种时间可变形对齐模块，它们利用该模块在特征层面实现运动对齐。

Hupé[17]和Gilbert[18]等人发现，在人类认知理论中，连接皮层视觉区域的反馈连接可以将反映信号从高阶区传递到低阶区，从而被加以利用。Zamir等人[19]更是在前人的基础上提出了一个适用于计算机视觉领域的反馈机制网络。近年来，它已被应用到各种视觉任务[4,20,21]的网络架构中，并表现出了不错的结果。据笔者调查，反馈机制还没有在VSR的研究领域中得到应用。得益于前人的启发[4,18]，笔者思考：既然反馈机制[19]允许网络携带历史信息来影响新输入信息的学习，那么融合了部分相邻帧信息的结果对其余相邻帧的融合是否同样具有影响？为此，本文提出了一个基于组反馈融合机制的视频超分辨率模型(video super-resolution model basedongroupfeedbackfusionmechanism，GFFMVSR)，本文反馈方案的原理是，具有部分相邻帧信息的结果可以促进其余相

邻帧信息的更好融合。

其主要贡献点包括：

a)提出了基于分组和反馈机制思想的视频超分辨率模型，该模型能有效地融合对齐帧中的高层信息，提高了视频重建的能力。

b）在视频超分领域内引入了组反馈机制，提供了一种新的相邻帧信息融合方法以提高时空信息融合的性能。

c）在模型内引入了双重时间注意力，时间注意力模块能捕捉隐藏在相邻帧内的重要信息，使得网络能恢复更清晰，细节更丰富的视频帧。

# 1 方法论

# 1.1 网络框架

如图1所示，基于组反馈融合机制的视频超分辨率模型主要由五个部分组成：特征提取与对齐模块(feature extractionand alignment module，FEAM)，组内融合模块(intra-groupfusion module，IGFM)，双重时间注意力模块(dual temporalattentionmodule，DTAM)，反馈融合模块(feedbackfusionmodule，FFM)，重建模块(rebuildmodule，RM)。图中蓝色箭头表示反馈融合，绿色箭头表示全局残差跳连接。该网络模型的任务是根据输入的 $2 N { + } 1$ 帧视频序列重建参考帧的高分辨率版本。把输入视频序列定义为 $\{ I _ { r - N } ^ { L R } , \cdots , I _ { r } ^ { L R } , \cdots , I _ { r + N } ^ { L R } \}$ ，输出的参考帧超分辨率版本定义为 $I _ { r } ^ { S R }$ ，参考帧的真实高分辨率版本定义为 $I _ { r } ^ { H R }$ ，卷积操作定义为 $C o n \nu ( s , n )$ ，反卷积操作定义为$D e c o n \nu ( s , n )$ ，其中 $s$ 是滤波器的大小， $n$ 是滤波器的数量。

![](images/2f53c869f6a615c77d5df2040874728b97d1d649d72e06f13d0ded7a18d419ce.jpg)  
图1基于组反馈融合机制的视频超分辨率模型

Fig.1Video super-resolution model based on group feedback fusion mechanism

特征提取与对齐模块用于相邻帧特征的提取和对齐，其操作如式(1)所示。

$$
\{ F _ { r - N } ^ { a } , \cdot \cdot \cdot , F _ { r } ^ { a } , \cdot \cdot \cdot , F _ { r + N } ^ { a } \} = f _ { F E A M } ( \{ I _ { r - N } ^ { L R } , \cdot \cdot \cdot , I _ { r } ^ { L R } , \cdot \cdot \cdot , I _ { r + N } ^ { L R } \} )
$$

其中 $f _ { F E A M } \left( \cdot \right)$ 代表特征提取与对齐操作。 $\left\{ F _ { r - N } ^ { a } , \cdots , F _ { r } ^ { a } , \cdots , F _ { r + N } ^ { a } \right\}$ 代表经过对齐后的相邻帧特征序列。在FEAM，特征提取简单地通过具有步进卷积运算的下采样来实现，而对齐操作参考EDVR[22]中提出的基于多尺度可变形卷积的方法(即 PCD 对齐模块)来实现，该部分建议读者参考EDVR[22]的PCD对齐模块的详细信息。

经过对齐的相邻帧随后输入时间注意力模块一( $T A M _ { \mathrm { 1 } }$ 从而计算相邻帧与参考帧的相似性，这将有利于组内信息的融合。其操作如式(2)所示。

$$
\{ F _ { r - N } ^ { a ^ { \prime } } , \cdots , F _ { r } ^ { a ^ { \prime } } , \cdots , F _ { r + N } ^ { a ^ { \prime } } \} = f _ { T A M _ { 1 } } ( \{ F _ { r - N } ^ { a } , \cdots , F _ { r } ^ { a } , \cdots , F _ { r + N } ^ { a } \} )
$$

其中 $f _ { T A M _ { 1 } } ( \cdot )$ 代表时间注意力模块一的操作。 $\{ F _ { r - N } ^ { a ^ { \prime } } , \cdots , F _ { r } ^ { a ^ { \prime } } , \cdots , F _ { r + N } ^ { a ^ { \prime } } \}$   
代表经过时间注意力计算的相邻帧特征序列。

随后对 $\{ F _ { r - N } ^ { a ^ { \prime } } , \cdots , F _ { r } ^ { a ^ { \prime } } , \cdots , F _ { r + N } ^ { a ^ { \prime } } \}$ 分成 $N$ 组，每组代表一种特定的帧速率。把各小组序列输入一个参数共享的IGFM实现小组内的初步融合，得到融合后的特征序列，定义为$\left\{ F _ { 1 } ^ { g } , F _ { 2 } ^ { g } , \cdots , F _ { N } ^ { g } \right\}$ (IGFM模块将在1.2节中详细阐述)。

融合后的不同组别所蕴涵的信息不一样。为了突出对重建结果有用的信息，在IGFM后插入了一个和时间注意力模块一结构相同的时间注意模块二( $T A M _ { 2 }$ )，构成了双重时间注意力模块(DTAM)，该时间注意力模块将在1.3节中详细阐述。经过 $T A M _ { 2 }$ 后的特征序列定义为 $\left\{ F _ { 1 } ^ { g ^ { \prime } } , F _ { 2 } ^ { g ^ { \prime } } , \cdots , F _ { N } ^ { g ^ { \prime } } \right\}$ ，其操作如式(3)所示。

$$
\left\{ F _ { 1 } ^ { g ^ { \prime } } , F _ { 2 } ^ { g ^ { \prime } } , \cdots , F _ { N } ^ { g ^ { \prime } } \right\} = f _ { T A M _ { 2 } } ( \left\{ F _ { 1 } ^ { g } , F _ { 2 } ^ { g } , \cdots , F _ { N } ^ { g } \right\} )
$$

其中， $f _ { T A M _ { 2 } } ( \cdot )$ 代表时间注意力模块二的操作。

跨组别信息通过基于反馈机制的反馈融合模块进一步整合。如图2所示，图1中红色虚线框可以展开成 $T$ 次迭代0 $\scriptstyle \left( T = N \right)$ ， $\textit { t }$ 代表1到 $T$ 中的某一次迭代。为了使FFM中的隐藏状态携带输出的概念，联系每次迭代的损失。损失函数将在1.5节中详细阐述。把序列 $\left\{ F _ { 1 } ^ { g ^ { \prime } } , F _ { 2 } ^ { g ^ { \prime } } , \cdots , F _ { N } ^ { g ^ { \prime } } \right\}$ 中的元素逐一输入FFM模块实现反馈融合。此外 $F _ { 1 } ^ { g ^ { \prime } }$ 被视为初始隐藏状态 $F _ { 0 } ^ { g ^ { \prime } }$ 。

FFM的第 $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { t }$ 次迭代输入包括第 $t$ 组特征 $F _ { t } ^ { g ^ { \prime } }$ 和来自前一次迭代的隐藏状态 $F _ { t - 1 } ^ { o u t }$ 。 $F _ { t } ^ { o u t }$ 代表FFM的第 $t$ 次输出。其操作如式(4)所示。

$$
F _ { t } ^ { o u t } = f _ { F F M } ( F _ { t - 1 } ^ { o u t } , F _ { t } ^ { g ^ { \prime } } )
$$

其中 $f _ { F F M } \left( \cdot \right)$ 代表FFM的操作，并且反馈的真实过程如图2所示。FFM模块将在1.4节中详细阐述。

把反馈融合的结果输入重建模块生成残差图像。如图1

所示，重建模块使用 $D e c o n \nu ( k , m )$ 将融合后的LR特征放大到HR特征，并使用 $C o n \nu ( 3 , c _ { o u t } )$ 生成网络的残差图像。重建模块的操作如式(5)所示。

$$
I _ { r , t } ^ { \mathrm { R e } s } = f _ { R M } \left( F _ { t } ^ { o u t } \right)
$$

![](images/512a13813bbcda77361066c2ff87825cc87462e9ba043d6289c6ff4f90f78565.jpg)  
图2反馈融合过程展开

最后，通过添加网络产生的残差图和输入参考帧的双三次上采样来生成参考帧的高分辨率版本 $I _ { r , t } ^ { S R }$ 。其操作如式(6)所示。

$$
\begin{array} { r } { I _ { r , t } ^ { s R } = I _ { r , t } ^ { \mathrm { R e } s } + f _ { u p } ( I _ { r } ^ { L R } ) } \end{array}
$$

其中 $f _ { u p } ( \cdot )$ 代表上采样核的操作。上采样核的选择是任意的，这里使用的是双三次上采样核。在 $T$ 次迭代之后，总共将得到参考帧的 $T$ 个SR版本 $( I _ { r , 1 } ^ { S R } , I _ { r , 2 } ^ { S R } , \cdots , I _ { r , T } ^ { S R } )$ 。值得注意的是，随着迭代次数的增加，重建的参考帧携带了越来越多的相邻帧信息，同时也更接近真实的HR版本，因此选择最后一次的重建结果作为最终的重建结果。

# 1.2组内融合模块(IGFM)

距离较远的相邻帧所隐含的有用信息可能较少。为了充分利用有用信息、剔除过多的无关特征，并提高随后的反馈效率，需要在反馈融合前进行初步的非反馈组内融合。对特征序列 $\{ F _ { r - N } ^ { a ^ { \prime } } , \cdots , F _ { r } ^ { a ^ { \prime } } , \cdots , F _ { r + N } ^ { a ^ { \prime } } \}$ 进行分组。与之前的工作不一样，基于到参考帧的时间距离，相邻的2N帧被分成 $N$ 组。原始序列被重新排列为 $\left\{ G _ { 1 } , . . . , G _ { n } \right\} , n \in \left[ 1 \colon N \right]$ ，其中 $G _ { n } = \{ F _ { r - n } ^ { a ^ { \prime } } , F _ { r } ^ { a ^ { \prime } } , F _ { r + n } ^ { a ^ { \prime } } \}$ 是由前一帧 $F _ { r - n } ^ { a ^ { \prime } }$ ，参考帧 $F _ { r } ^ { a ^ { \prime } }$ 和后一帧 $F _ { r + n } ^ { a ^ { \prime } }$ 组成的子序列，需要提醒的是，参考帧出现在每一组中(具体原因参考第2.2节)。不同时间距离的相邻帧的贡献是不相等的，通过分组的方式可以根据参考帧的引导对不同时间距离的相邻帧进行高效的信息提取和融合。值得注意的是，本文的方法可以很容易地推广到任意帧作为输入。

对于每个组，组内融合模块被部署用于每个组内的特征融合。如图3所示，该模块的前部分使用具有卷积核的3D卷积层来实现每个小组的时空特征融合。然后，通过在2D 稠密块中应用15个2D单元(unit)来深度整合每个组内的信息，最后产生分组特征序列 $\left\{ F _ { 1 } ^ { g } , F _ { 2 } ^ { g } , \cdots , F _ { N } ^ { g } \right\}$ 。稠密块的每一单元依次由批量归一化[23](batch normalization，BN)、ReLU[24]、 $1 \times 1$ 卷积、BN、ReLU、 $3 { \times } 3$ 卷积组成。如在文献[25]中所做的，每个2D单元将所有先前的特征图级联在一起作为输入。最后通过一个 $1 \times 1$ 卷积层减少通道数。2D 稠密块的设计受到DUF[12]的启发。为了提升效率，组内融合模块的权重由每个组共享，并对本文的数据流通道进行了有效的修改。该模块的操作如式(7)所示。

$$
\left\{ F _ { 1 } ^ { g } , F _ { 2 } ^ { g } , \cdots , F _ { N } ^ { g } \right\} { = } f _ { I G F M } \left( \left\{ G _ { 1 } , G _ { 2 } , \cdots , G _ { N } \right\} \right)
$$

其中 $f _ { I G F M } ( \cdot )$ 表示卷积操作。代表组内融合模块操作。第2.2节验证了建议的时间分组的有效性。

# 1.3双重时间注意力模块(DTAM)

帧间时间关系在VSR相邻帧融合中是至关重要的(由于遮挡、模糊区域和视差问题，不同的相邻帧的信息量不同)。

时间注意力可以更加聚焦于有利于后续重建的特征上，而非一视同仁。DTAM由两个一样的，结构如图4所示的时间注意力模块构成，分别命名为 $T A M _ { 1 }$ 和 $T A M _ { 2 }$ 。它们分别聚焦于分组融合前后特征序列时间信息的捕获和权重计算，从而提高信息融合效果。

![](images/93632a7d3ff4b046cc29fb55db229feb2fbe4b9f9ec7b54c55a088e08d7d70f5.jpg)  
Fig.2Feedback fusion process unfolds   
图3组内融合模块

时间注意力的目标是在一个嵌入空间中计算特征序列的相似性。直观地说，在一个嵌入空间中，应该更多地关注与参考特征更相似的特征信息。在 $T A M _ { 1 }$ 中，对于每一帧特征，相似性距离 $h$ (即时间注意力图 $M _ { i }$ )可以计算为

$$
M _ { i } = h ( F _ { i } ^ { a } , F _ { r } ^ { a } ) = s i g m o i d ( \theta ( F _ { i } ^ { a } ) ^ { T } \phi ( F _ { r } ^ { a } ) )
$$

这里， $F _ { r } ^ { a }$ 被视为参考特征。 $i \in [ r - N , r + N ]$ 。 $\theta ( F _ { i } ^ { a } )$ 和 $\phi ( F _ { r } ^ { a } )$ 是两个嵌入运算，可通过简单的卷积滤波器来实现。sigmoid激活函数用于限制输出在[0，1]之间，稳定梯度反向传播。请注意，时间注意力图大小和特征图 $M _ { i }$ 的尺寸是相同的。每帧相邻帧的注意力加权特征计算如下：

$$
F _ { i } ^ { a ^ { \prime } } = F _ { i } ^ { a } \odot M _ { i }
$$

这里， $\odot$ 代表按位置元素的乘法。

同理，对于 $T A M _ { 2 }$ 也是如此。值得注意的是，在 $T A M _ { 2 }$ 中参考特征为 $F _ { 1 } ^ { g }$ 。其时间注意力图 $M _ { i }$ 和注意力加权特征的计算如式(10)(11)所示(此时 $i \in [ 1 , N ]$ )：

$$
M _ { i } = h ( F _ { i } ^ { g } , F _ { 1 } ^ { g } ) = s i g m o i d ( \theta ( F _ { i } ^ { g } ) ^ { T } \phi ( F _ { 1 } ^ { g } ) )
$$

$$
F _ { i } ^ { g ^ { \prime } } = F _ { i } ^ { g } \odot M _ { i }
$$

![](images/af3579707ee628f0baddfd2d2e2e06fa75043c02b5e031e6ecd8d04490142818.jpg)  
Fig.3Intra-group fusion module   
图4时间注意力模块  
Fig.4Temporal attention module

# 1.4反馈融合模块(FFM)

FFM模块如图5所示。第 $t \left( t \in \left[ 1 : T \right] \right)$ 次迭代的FFM接收反馈信息 $F _ { t - 1 } ^ { o u t }$ 以指导融合第 $t$ 组特征图 $F _ { t } ^ { g ^ { \prime } }$ ，然后将融合了更多信息的表示 $F _ { t } ^ { o u t }$ 传递给下一次迭代和重构模块，从而形成一个完整的反馈过程。为了实现FFM模块的反馈融合功能，该模块依次包含3个投影组，其中的信息通过密集的跳跃连接有效地跨层级流动。每个投影组主要包括上采样和下采样操作，该操作可将HR特征投影到一个LR特征上，从而达到不断细化融合特征的效果。通过迭代执行FFM来有效地逐个融合特征序列 $\left\{ F _ { 1 } ^ { g ^ { \prime } } , F _ { 2 } ^ { g ^ { \prime } } , \cdots , F _ { N } ^ { g ^ { \prime } } \right\}$ 。迭代过程如图2展开所示。

在FFM的前端，用 $C o n \nu ( 1 , m )$ 对 $F _ { t } ^ { g ^ { \prime } }$ 和 $F _ { t - 1 } ^ { o u t }$ 进行级联和压缩，以通过反馈信息 $F _ { t - 1 } ^ { o u t }$ 来指导融合输入特征 $F _ { t } ^ { g ^ { \prime } }$ ，产生特征细化组的输入特征 $L R _ { t } ^ { 0 }$ ：

$$
L R _ { t } ^ { 0 } = C _ { 0 } ( [ F _ { t - 1 } ^ { o u t } , F _ { t } ^ { g ^ { \prime } } ] )
$$

其中 $C _ { 0 } ( \cdot )$ 代表初始通道压缩操作， $[ F _ { t - 1 } ^ { o u t } , F _ { t } ^ { g ^ { \prime } } ]$ 代表对 $F _ { t - 1 } ^ { o u t }$ 和 $F _ { t } ^ { g ^ { \prime } }$ 的级联。定义 $H _ { t } ^ { g }$ 和 $L _ { \eta } ^ { g }$ 为第 $t$ 次迭代时FFM中第g ${ \left( \begin{array} { l } { g \in \left[ 1 : 3 \right] } \end{array} \right) }$ 个投影组产生的HR和LR特征图。 $H _ { t } ^ { g }$ 可以通过以下方式获得：

$$
H _ { t } ^ { g } = D e c _ { g } ( [ L _ { t } ^ { 0 } , L _ { i } ^ { 1 } , \cdots , L _ { i } ^ { g - 1 } ] )
$$

其中， $D e c _ { g } ( \cdot )$ 表示在第 $g$ 个投影组使用 $D e c o n \nu _ { g } ( k , m )$ 进行上采样操作。相应地， $L _ { t } ^ { g }$ 可由下式获得：

$$
{ \cal L } _ { t } ^ { g } = C o n \nu _ { g } ( [ H _ { t } ^ { 1 } , H _ { t } ^ { 2 } , \cdots , H _ { t } ^ { g } ] )
$$

其中， $C o n \nu _ { g } \left( \cdot \right)$ 表示在第 $g$ 个投影组使用 $C o n \nu _ { g } ( k , m )$ 进行下采样操作。为降低参数量和提高计算效率，本文在除了第一个投影组外的 $D e c o n \nu _ { g } ( k , m )$ 和 $C o n \nu _ { g } ( k , m )$ 之前添加了 $C o n \nu ( 1 , m )$ 进行通道压缩操作。

FTZnoEn 1D T:ToTTN cuoa LR Y1Ion F r\*%% HR --- P

为了充分利用来自每个投影组的有用信息，本文对投影组产生的 LR 特征进行特征融合(图5 中的红色箭头所示)，以产生FFM模块的的输出：

$$
F _ { t } ^ { o u t } = C _ { F F } ( [ L _ { t } ^ { 1 } , L _ { t } ^ { 2 } , L _ { t } ^ { 3 } ] )
$$

其中， $C _ { F F } ( \cdot )$ 代表 $C o n \nu ( 1 , m )$ 的函数。

# 1.5损失函数

在本工作中，选择L1损失来优化所提出的网络。虽然只使用重建序列 $( I _ { r , 1 } ^ { S R } , I _ { r , 2 } ^ { S R } , \cdots , I _ { r , T } ^ { S R } )$ 中最后一次的结果当做最终结果，但在训练时，仍需要把中间结果与损失函数联系起来，确保每次迭代FFM模块都能最大限度融合当前输入特征图的有用信息。网络中的损失函数可以表示为

$$
L o s s ( \theta ) = \frac { 1 } { T } \sum _ { t = 1 } ^ { T } W ^ { t } \left\| I _ { r } ^ { H R } - I _ { r , t } ^ { S R } \right\| _ { 1 }
$$

其中， $\theta$ 表示网络的参数。 $W ^ { t }$ 是一个常数因子，代表了每次迭代时SR结果的贡献值。将所有迭代的 $W ^ { \prime }$ 设置为1，这意味着每次重建的SR结果都有相同的贡献，从而使得每次迭代都能尽可能地去融合高级信息。

# 2 实验结果和分析

# 2.1实验设置

a）数据集。采用Vimeo-90k[26]作为训练集，这是一个广泛用于视频超分辨率的训练集。它包含约90k份7帧的视频剪辑。从高分辨率的视频剪辑中裁剪出空间分辨率为$2 5 6 \times 4 4 8$ 的区域。与文献[26,27]相似，通过应用标准差 $\sigma { = } 1 . 6$ 的高斯模糊核和4倍下采样生成 $6 4 \times 1 1 2$ 的低分辨率视频剪辑。在两个流行的基准数据集上评估了所提出的方法:Vid4[28]和Vimeo90K-T[26]。这两个基准数据集都具有各种运动和遮挡的场景，因此适用于评估本文方法的信息融合和高分辨率重建能力。

b)实现细节：除非另有说明，否则像大多数VSR方法[29,16,30]一样，本文网络以7个视频帧作为输入，即 $N = 3$ 0使用PReLU[3I作为每个子网络中除最后一层之外的所有卷积和反卷积层之后的激活函数。将 $C o n \nu ( k , m )$ 和 $D e c o n \nu ( k , m )$ 中的 $k$ 设为6，以及4个步伐和2个填充， $m$ 设为64。使用Adam[32]优化器进行优化，其中 $\beta _ { \mathrm { { l } } } = 0 . 9$ ， $\beta _ { 2 } = 0 . 9 9 9$ 。在训练中不使用权重衰减。学习率最初设置为 $2 \times 1 0 ^ { - 4 }$ ，然后每8个epoches降低0.5倍，直到60个epoches结束。小批量的大小设置为2训练数据通过0.5的概率进行翻转，旋转进行增强。

所有实验都是在配备Python $_ { 1 = 3 . 8 }$ 、PyTorch $_ { 1 } { = } 1 . 1$ 和Nvidia2080TI的GPU服务器上进行。

# 2.2消融实验

分组实验。首先用不同的方法来组织输入的序列，一种Base方法(记作Base1)是简单地沿着时间轴堆叠输入序列，并一次性输入IGFM和FFM模块(中间不具有时间注意力模块),此处的FFM 模块只执行一次，不具有反馈机制。另外，除了文中建议的分组方式{345，246，147}，还尝试了其他方法的分组：{123，345，567}和{345，142，647}。如表1中所示{345，246，147}的分组方法所获得的PSNR最高，这暗示了在每组中添加参考帧将有助于模型提取参考帧中缺失的信息。{345，142，647}表现次优则可以归因于距离参考帧不同时间步长的相邻帧信息差异较大，这将不利于信息的分组学习。

Tab.1Ablation experiment with grouping methor   

<html><body><table><tr><td>模型</td><td>Base1</td><td>{123,345,567}</td><td>{345,142,647}</td><td>{345,246,147}</td></tr><tr><td>Vid4</td><td>27.09</td><td>27.12</td><td>27.17</td><td>27.20</td></tr><tr><td>Vimeo-90K-T 37.06</td><td></td><td>37.12</td><td>37.16</td><td>37.19</td></tr></table></body></html>

各模块实验。为了验证各模块的作用，实验中把分组实验提到的{345,246,147}分组方式作为Base 模型(记作Base2)分别在Base2 模型上引入时间注意力模块一(time attentionmodule1， $T A M _ { \mathrm { 1 } }$ )，时间注意力模块二(time attention module 2，$T A M _ { 2 }$ )，反馈融合机制(feedback fusion mechanism，FFM'）。值得注意的是，分组后反馈融合机制的关闭是通过在时间维度级联相邻组别特征，然后只执行一次FFM模块实现。此外，整合了 $T A M _ { \mathrm { 1 } }$ 、 $T A M _ { 2 }$ 、FFM'的完整模型记为GFFMVSR(Ours)。设置放大的倍数为4，按照实验设置进行实验后，在vid4 测试集上的PSNR值如表2所示。

表1分组方法的消融实验(PSNR)  
表2在vid4(4x)测试集上的组件消融实验  
Tab.2Component ablation experiments on the vid4 (4x) test set   

<html><body><table><tr><td>模型</td><td>时间注意力模块一时间注意力模块二反馈机制PSNR</td><td></td></tr><tr><td>Base2</td><td></td><td>27.20</td></tr><tr><td>TAM1</td><td>√</td><td>27.29</td></tr><tr><td>TAM2</td><td>√</td><td>27.28</td></tr><tr><td>TAM1+TAM2</td><td>√</td><td>√ 27.33</td></tr><tr><td>FFM'</td><td></td><td>27.38</td></tr><tr><td>GFFMVSR (Ours)</td><td>√ √</td><td>√ 27.47</td></tr></table></body></html>

由表2第1、2、3、4行可见，引入时间注意力模块一和时间注意力模块二，对Base2模型在PSNR值上分别有 $0 . 0 9 \mathrm { d B }$ 和0.08dB的提升，同时引入两个时间注意力构成双重时间注意力模块后，PSNR有0.13dB的提升。由第1、5行可见，引入反馈融合机制，PSNR值有0.18dB的提升。由最后一行可见，整合了双重时间注意力和反馈机制的完整模型性能达到最大值，相比Base2模型高出了 $0 . 2 7 \mathrm { d B }$ ，这证实了本文提出的模型合理性。

# 2.3对比现有先进模型

在本节中，将本文方法与几种最先进的VSR方法进行了比较，包括TOFlow[26]、DUF[12]、RBPN[14]、EDVR[16]、MuCAN[33]、Liu[34]、PFNL[35]和VSR-Transformer[36]。TOFlow和RBPN都使用光流在像素层面进行显式运动估计。EDVR则采用对噪声处理能力更强的隐式运动估计。DUF、MuCAN和PFNL则跳过了运动估计过程。最后一种专门使用最新的视觉transformer(ViT)[37]网络来完成VSR任务。通过运行公开的代码或者自己仔细复现了大多数方法，并试图重现原始论文中报告的结果。

Vid4数据集。表3显示了关于Vid4的定量结果，其中的数据或者由笔者计算，或者来自于原始论文。其中Y 和

RGB分别表示亮度和RGB通道，“-”意味着该数值无法取得。作为GFFMVSR的降级版本，GFFMVSR-S(只使用时间注意力模块一)在Y通道中实现了27.43/0.8373的平均PSNR/SSIM值，在RGB通道中实现了25.93/0.8186，这可以说是优于所有其他方法。采用双重时间注意力后，GFFMVSR-S 变为GFFMVSR，在Y和RGB 通道都获得了更高的性能。定性结果如图6所示。可以看到GFFMVSR比其他方法产生的边缘更锐利，纹理更精细，这也验证了本文方法的优越性。

此外，为了比较时间一致性的性能，从Vid4数据集中的日历序列中提取并可视化时间分布图(见图7)。通过在多个连续的帧中相同位置取水平行的像素(图7中的红线)并垂直堆叠它们来获得时间轮廓。可以看出，GFFMVSR产生了最一致的结果，与其他方法相比，它具有更少的闪烁伪像，并且包含更均匀的线条细节。

表3在Vid4上的 $4 \times$ 视频超分辨率定量比较  
Tab.3Quantitative comparison of $4 \times$ video super-resolution on Vid4   

<html><body><table><tr><td rowspan="2">模型</td><td>Frames</td><td colspan="2">Calendar(Y)</td><td colspan="2">City(Y)</td><td colspan="2">Foliage(Y)</td><td colspan="2">Walk(Y)</td><td colspan="2">Average(Y)</td><td colspan="2">Average(RGB)</td></tr><tr><td></td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>1</td><td>18.83</td><td>0.4936</td><td>23.84</td><td>0.5234</td><td>21.52</td><td>0.4438</td><td>23.01</td><td>0.7096</td><td>21.80</td><td>0.5426</td><td>20.37</td><td>0.5106</td></tr><tr><td>TOFlow[26]</td><td>7</td><td>22.29</td><td>0.7273</td><td>26.79</td><td>0.7446</td><td>25.31</td><td>0.7118</td><td>29.02</td><td>0.8799</td><td>25.85</td><td>0.7659</td><td>24.39</td><td>0.7438</td></tr><tr><td>DUF-52L[12]</td><td>7</td><td>24.17</td><td>0.8161</td><td>28.05</td><td>0.8235</td><td>26.42</td><td>0.7758</td><td>30.91</td><td>0.9165</td><td>27.38</td><td>0.8329</td><td>25.91</td><td>0.8166</td></tr><tr><td>RBPN[14]</td><td>7</td><td>24.02</td><td>0.8088</td><td>27.83</td><td>0.8045</td><td>26.21</td><td>0.7579</td><td>30.62</td><td>0.9111</td><td>27.17</td><td>0.8205</td><td>25.65</td><td>0.7997</td></tr><tr><td>EDVR-L[16]</td><td>7</td><td>24.05</td><td>0.8147</td><td>28.00</td><td>0.8122</td><td>26.34</td><td>0.7635</td><td>31.02</td><td>0.9152</td><td>27.35</td><td>0.8264</td><td>25.83</td><td>0.8077</td></tr><tr><td>Liu[34]</td><td>5</td><td>21.61</td><td></td><td>26.29</td><td>-</td><td>24.99</td><td></td><td>28.06</td><td></td><td>25.23</td><td>-</td><td></td><td></td></tr><tr><td>PFNL[35]</td><td>7</td><td>24.37</td><td>0.8246</td><td>28.08</td><td>0.8385</td><td>26.51</td><td>0.7768</td><td>30.65</td><td>0.9135</td><td>27.40</td><td>0.8384</td><td>-</td><td></td></tr><tr><td>VSR-Transformer [36]</td><td>5</td><td>24.08</td><td>0.8125</td><td>27.94</td><td>0.8107</td><td>26.33</td><td>0.7635</td><td>31.10</td><td>0.9163</td><td>27.36</td><td>0.8258</td><td>-</td><td>-</td></tr><tr><td>GFFMVSR-S</td><td>7</td><td>24.32</td><td>0.8253</td><td>28.09</td><td>0.8312</td><td>26.48</td><td>0.7771</td><td>30.80</td><td>0.9158</td><td>27.43</td><td>0.8373</td><td>25.93</td><td>0.8186</td></tr><tr><td>GFFMVSR</td><td>7</td><td>24.39</td><td>0.8282</td><td>28.11</td><td>0.8337</td><td>26.54</td><td>0.7784</td><td>30.85</td><td>0.9166</td><td>27.47</td><td>0.8392</td><td>25.95</td><td>0.8206</td></tr></table></body></html>

![](images/874d79d60268e7b7eca6df009caeebf1576b3a8f1bdea9e65ef5c9e484a4e5e4.jpg)  
图6在Vid4数据集上 $4 \times \mathrm { V S R }$ 的定性比较

![](images/40433b3b34fab06931853350417bd531b85d6867fd3cffc5d3a057d49e0a566b.jpg)  
Fig.6 Qualitative comparison of $4 { \times } \mathrm { V S R }$ on the Vid4 dataset   
图7日历序列上红线的时间轮廓可视化，用于显示时间一致性  
Fig.7Temporal profile visualization forthered line on the calendar,sequence to show the temporalconsistency

Vimeo-90K-T数据集.Vimeo-90K-T包含了从Vimeo-90K中选取的大约7K个视频片段作为测试集，涵盖了大量的场景和大运动。PSNR/SSIM的定量结果见表4，其中也包括了大多数方法的参数数量，“-"意味着该数值无法取得。在PSNR和 SSIM，本文方法远远超过了大多数最先进的方法，如TOFlow、DUF、RBPN和MuCAN。唯一的例外是EDVR-L,它的模型大小大约是本文方法的四倍，且EDVR涉及到一个需要大量数据和训练时间的预训练过程。尽管如此，本文方法在PSNR还是相当不错的，在SSIM略胜一筹。

此外，Vimeo-90K-T的定性结果如图8所示。可以看到，GFFMVSR也可以在这个具有挑战性的数据集上产生视觉上令人信服的 SR图像。

表4在Vimeo-90K-T上的 $4 \times$ 视频超分辨率定量比较

Tab.4Quantitative comparison of $4 \times$ video super-resolution on Vimeo-90K  

<html><body><table><tr><td rowspan="2">模型</td><td></td><td>Frames Param</td><td>Y Channel</td><td>RGB Channel</td><td></td></tr><tr><td></td><td></td><td>PSNR SSIM</td><td>PSNR</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>1</td><td></td><td>31.30 0.8687</td><td>29.77</td><td>0.8490</td></tr><tr><td>TOFlow[26]</td><td>7</td><td>1.4M</td><td>34.62 0.9212</td><td>32.78</td><td>0.9040</td></tr><tr><td>DUF-52L[12]</td><td>7</td><td>5.8M</td><td>36.87 0.9447</td><td>34.96</td><td>0.9313</td></tr><tr><td>RBPN[14]</td><td>7</td><td>12.1M</td><td>37.20 0.9458</td><td>35.39</td><td>0.9340</td></tr><tr><td>EDVR-L[16]</td><td>7</td><td>20.6M 37.61</td><td>0.9489</td><td>35.79</td><td>0.9374</td></tr><tr><td>MuCAN[33]</td><td>7</td><td>1</td><td>37.32 0.9465</td><td>35.49</td><td>0.9344</td></tr><tr><td>GFFMVSR-S(ours)</td><td>7</td><td>4.7M</td><td>37.43</td><td>0.9481 35.62</td><td>0.9373</td></tr><tr><td>GFFMVSR(ours)</td><td>7</td><td>4.95M</td><td>37.47</td><td>0.9493 35.68</td><td>0.9385</td></tr></table></body></html>

# 3 结束语

本文针对存在于人类视觉系统中的反馈机制仍未在现有视频超分辨率模型中得到充分应用的问题，提出了一种新的端到端可训练的视频超分辨率网络，称为GFFMVSR。通过将分组思想和反馈机制结合在一起应用到VSR任务中，有效地提高了相邻帧信息的融合效果和目标帧重建质量。输入序列被重组为具有不同帧速率的几组子序列。分组允许以分层方式提取时空信息，之后是组内融合模块对小组特征进行初步融合。而反馈融合机制通过模仿人类的认知学习过程，通过反馈信息高效学习并融合新输入的内容。通过在模型的恰当位置应用时间注意力构成的双重时间注意力模型更进一步促使模型专注于有用信息的融合。在几个基准数据集上的大量实验表明，本文提出的模型在定量和定性两方面都优于现有的VSR方法。

![](images/13c77ca620dfa40e061250dec879162a40a16181ff2efa50bb3903e3abb71b9d.jpg)  
图8在Vimeo-90K-T数据集上 $4 \times \mathrm { V S R }$ 的定性比较  
Fig.8Qualitative comparison of $4 { \times } \mathrm { V S R }$ on the Vimeo-90K-T dataset

# 参考文献：

[1]Dong Chao,Loy Chen Change,He Kaiming,et al. Learning a deep convolutional network for image super-resolution [C]// European Conference on Computer Vision. Springer, Cham,2014:184-199.   
[2]Simonyan K, Zisserman A.Very deep convolutional networks for largescale image recognition [J].arXiv preprint arXiv:1409.1556,2014.   
[3]Kim J,Lee JK,Lee K M. Accurate image super-resolution using very deep convolutional networks [C]//Proceedings of The IEEE Conference on Computer Vision and Pattern Recognition.2016:1646-1654.   
[4]Li Zhen,Yang Jinglei,Liu Zheng,et al.Feedback network for image super-resolution [C]// Proceedings of The IEEE/CVF Conference on Computer Vision and Pattern Recognition.2019:3867-3876.   
[5] 盘展鸿，朱鉴，迟小羽，等．基于特征融合和注意力机制的图像超分 辨率模型[J].计算机应用研究,2022,39(3):5.(Pan Zhanhong,Zhu Jian,Chi Xiaoyu,et al. Image super-resolution model based on feature fusion and attention mechanism [J].Application Research of Computers. 2022,39 (3): 5.)   
[6]Chu Xiangxiang,Zhang Bo,Ma Hailong,et al.Fast,accurate and lightweight super-resolution with neural architecture search [C]// 25th International Conference on Pattern Recognition (ICPR).IEEE,2021: 59-64.   
[7]Wang Longguang，Dong Xiaoyu，Wang Yingqian．et al.Exploring sparsity in imagesuper-resolution for effcient inference [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2021: 4917-4926.   
[8]Huang Yan，WangWei,WangLiang.Bidirectional recurrent convolutional networks for multi-frame super-resolution [J].Advances in Neural Information Processing Systems,2015,28.   
[9]Caballero J,Ledig C,Aitken A,et al.Real-time video super-resolution withspatio-temporal networks and motion compensation [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2017: 4778-4787.   
[10] Tao Xin,Gao Hongyun,Liao Renjie,et al.Detail-revealing deep video super-resolution [C]//Proceedings of the IEEE International Conference on Computer Vision.2017: 4472-4480.   
[11] Kim S Y,Lim J,Na T,et al. 3dsrnet:Video super-resolution using 3d convolutional neural networks [J].arXiv preprint arXiv:1812.09079, 2018.   
[12] Jo Y, Oh S W,Kang J,et al. Deep video super-resolution network using dynamic upsampling filters without explicit motion compensation [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2018:3224-3232.   
[13] Jia X,De Brabandere B,Tuytelaars T,et al.Dynamic filter networks for predicting unobserved views [C]//Proceedings ECCV 2016 workshops. 2016:1-2.   
[14]Haris M, Shakhnarovich G,Ukita N.Recurrent back-projection network forvideo super-resolution [Cl//Proceedingsof the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2019:3897- 3906.   
[15] Tian Yapeng,Zhang Yulun,Fu Yun,et al.Tdan: Temporally-deformable alignment network for video super-resolution [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Patern Recognition. 2020:3360-3369.   
[16] Wang Xintao,Chan K CK,Yu Ke,et al.Edvr: Video restoration with enhanced deformable convolutional networks [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops.2019:0-0.   
[17] Hupé JM, James AC,Payne B R,et al. Cortical feedback improves discrimination between figure and background by V1，V2 and V3 neurons [J].Nature,1998,394 (6695): 784-787.   
[18] Gilbert C D,Sigman M. Brain states: top-down influences in sensory processing [J]. Neuron,2007,54 (5): 677-696.   
[19] Zamir AR,Wu TL, Sun L,et al. Feedback networks [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2017: 1308-1317.   
[20] CarreiraJ,AgrawalP,Fragkiadaki K,et al.Human pose estimation with iterative error feedback [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2016:4733-4742.   
[21] Sam D B，Babu R V. Top-down feedback for crowd counting convolutional neural network [C]// Thirty-second AAAI Conference on Artificial Intelligence.2018.   
[22]Wang Xintao,Chan K CK,Yu Ke,et al.Edvr:Video restoration with enhanced deformable convolutional networks [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops.2019:0-0.   
[23] Ioffe S,Szegedy C.Batch normalization: Accelerating deep network training by reducing internal covariate shift [C]// International Conference on Machine Learning.PMLR,2015: 448-456.   
[24] Glorot X,Bordes A,Bengio Y. Deep sparse rectifier neural networks [C]// Proceedings of the Fourteenth International Conference on Artificial Intelligence and Statistics.JMLR Workshop and Conference Proceedings,201l: 315-323.   
[25]Huang Gao,Liu Zhuang,Van Der Maaten L,et al.Densely connected convolutional networks [C]//Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2017: 4700-4708.   
[26] Xue Tianfan,Chen Baian,Wu Jiajun,et al.Video enhancement with taskoriented flow [J].International Journal of Computer Vision,2O19,127 (8):1106-1125.   
[27] Jo Y, Oh S W, Kang J,et al. Deep video super-resolution network using dynamic upsampling filters without explicit motion compensation [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2018:3224-3232.   
[28] Liu Ce, Sun Deqing. On Bayesian adaptive video super resolution [J]. IEEE Transactions on Pattern Analysis and Machine Intelligence,2013, 36 (2): 346-360.   
[29]Haris M, Shakhnarovich G, Ukita N.Recurrent back-projection network forvideo super-resolution [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2019:3897- 3906.   
[30] Yi Peng,Wang Zhongyuan,Jiang Kui,et al.Progressive fusion video super-resolution network via exploiting non-local spatio-temporal correlations[C]//Proceedingsof theIEEE/CVFInternational Conference on Computer Vision.2019:3106-3115.   
[31] He Kaiming,Zhang Xiangyu,Ren Shaoqing,et al. Delving deep into rectifiers:Surpassinghuman-levelperformanceonimagenet classification [C]//Proceedings of the IEEE International Conference on Computer Vision.2015:1026-1034.   
[32]Kingma DP,Ba J.Adam: A method for stochastic optimization [J].arXiv preprint arXiv:1412.6980,2014.   
[33]Li Wenbo,Tao Xin,Guo Taian,et al.Mucan:Multi-correspondence aggregation network for videosuper-resolution [Cl//European Conference on Computer Vision. Springer, Cham,2020:335-351.   
[34]Liu Ding，Wang Zhaowen，Fan Yuchen，et al.Learning temporal dynamics for video super-resolution: A deep learning approach [J].IEEE Transactions on Image Processing,2018,27(7): 3432-3445.   
[35]Yi Peng,Wang Zhongyuan,Jiang Kui,et al. Progressive fusion video super-resolution network via exploiting non-local spatio-temporal correlations[C]//ProceedingsoftheIEEE/CVFInternational Conference on Computer Vision.2019:3106-3115.   
[36] Cao Jiezhang，Li Yawei,Zhang Kai，et al.Video super-resolution transformer[J].arXiv preprint arXiv:2106.06847,2021.   
[37]Dosovitskiy A,BeyerL,Kolesnikov A,et al.An image is worth 16x16 Words:Transformers for image recognition at scale [J].arXiv preprint arXiv:2010.11929,2020.