# 基于深度学习的人体动作识别方法

李玉鹏，刘婷婷，张良

(中国民航大学天津市智能信号与图像处理重点实验室，天津 300300)

摘要：针对人体动作深度视频的四维信息映射到二维空间后，动作分类容易发生混淆的问题，提出一种基于深度学习的人体动作识别方法。首先构建空间结构动态深度图，将深度视频的四维信息映射到二维空间，进行信息降维处理；然后提出基于联合代价函数的深度卷积神经网络，结合交叉熵损失函数与中心损失函数作为联合代价函数，指导卷积层学习到更具分辨力的深度特征，以进行更精确的分类。在MSRDailyActivity3D和 SYSU3DHOI两个数据集的实验结果表明，与现有方法相比，该方法识别率得到了较明显地提升，验证了该方法的有效性和鲁棒性。该方法较好地解决了动作分类容易发生混淆的问题。

关键词：深度信息；人体动作识别；深度学习；空间结构动态深度图；深度卷积神经网络 中图分类号：TP391.41 doi: 10.19734/j.issn.1001-3695.2018.05.0499

# Human action recognition based on deep learning

Li Yupeng, Liu Tingting, Zhang Liang (TianjinKeyLaboratoryofAdvancedSignal&ImageProcessng,CivilAvitionUniversityofhna,TanjinCina)

Abstract:Inorder to solves the problemofactionclasification prone toconfusionaftermappingthe four-dimensionaldepth information to two-dimensional space,this paper proposed amethod for human actionrecognition basedon deep learning. Firstly,the methodconstructed spatiallstructured dynamicdepth images fordimensionreduction.Then,itproposedthe dep convolutionneuralnetwork with jointcostfunction,whichcombinedthecross entropylossfunctionandthecentrallossfunction ascost function,toguidetheconvolutionlayertolearnmore discriminativedeep features.Theexperimentalresults evaluated on the public MSRDailyActivity3D dataset and SYSU 3DHOIdataset.It showthatthe method obtaina better performance compare withother existing method,which validate the efectiveness androbustess ofthe method.Themethod efectively solves the problem of action classification prone to confusion.

Key words:depth information; humanaction recognition; dep learning; spatially structured dynamic depth images;deep convolution neural network

# 0 引言

人体动作识别在智能监控、人机交互、视频检索、虚拟现实等方面具有广泛的应用，因此其一直是计算机视觉领域一个活跃的研究方向。在以前的研究中，很多关于人体动作识别的研究方法都集中在传统的RGB视频[1-4]，但基于RGB视频数据的处理有很多难点，比如：不具有视角不变性，对光照和背景的变化敏感，对噪声不鲁棒等，虽然近几年通过研究者的努力，取得了一些很有意义的成果，但人体动作识别的研究仍然非常具有挑战性。

近年来，微软Kinect的发布为这一领域带来了新的机遇，Kinect设备可以实时地采集深度图，与传统彩色图像相比，深度图有许多优点，例如，深度图序列实质上是四维空间可以包含更丰富的动作信息，对光照条件的变化不敏感，可以更可靠地估计人体轮廓和骨骼等[5]。文献[6\~11]利用深度图的这些特性设计出专门的特征描述子，一定程度上对动作识别领域产生了深远的影响。Liu等人[12]提出增强的骨骼点形象化方法利用骨骼点的时空序列对人体动作进行视角不变的识别，具有更广泛的实用性，但仍受限于利用骨骼数据构造特定的特征。因此，上述方法都是基于手工制作的特征，这些特征是对局部或全局时空信息的浅层次描述，无法同时捕获动作中重要的时空和结构信息。

随着深度卷积神经网络（deepconvolutionalneuralnetwork,DCNN）在ImageNet图像分类竞赛中获得巨大的成功[13]，许多研究者将ImageNet 上训练好的模型应用到诸如属性分类[14]、图像表示[15]和语义分割[16]等任务中，取得了良好的效果。然而，上述研究均是针对彩色图像的图像理解任务，人体动作识别不同于一般的图像理解任务，特别是基于深度信息的人体动作识别问题，其以深度视频这种四维空间的形式表示，因此无法效仿上述任务直接使用DCNN进行识别。

Wang等人[17]尝试通过设计加权的深度运动映射图作为DCNN的输入，使人体动作识别问题转换为图像分类问题,首次使用DCNN对基于深度图的人体动作进行识别，但实验结果表明该方法的鲁棒性欠佳。受 Fernando 等人[18\~20]提出的顺序池化法（rankpooling，RP）在基于彩色图像的人体动作识别方向上取得较大成功的激励，Wang 等人[21]在RP 的基础上提出空间结构动态深度图（spatially structured dynamic depth images，SSDDI)，克服了RP操作抑制深度图空间局部细粒度运动信息的缺点，达到了较高的识别率。

以上分析可知，目前的研究工作集中在寻求设计某种有效的特征表示方式，期望在动作的四维信息映射二维空间后，尽量将动作的重要特征在二维空间中得到表征，从而提高动作识别的准确率。然而，笔者在研究中发现，动作的深度信息被映射到二维空间表征后，动作在分类过程中很容易产生混淆，从而限制该类方法的识别率上限。

针对现有方法所存在的问题，通过对文献[22]的研究和实践，受Wen等解决人脸识别领域类似问题所采用方法的启发，笔者从神经网络提取特征与分类的机制考虑问题，结合基于深度图的人体动作识别的特点，提出基于联合代价函数的深度卷积神经网络（joint cost function based deep convolution neuralnetwork,JCF-DCNN）用于人体动作识别，尝试提高动作分类的准确性和鲁棒性，该方法在网络训练过程中增加训练样本的特征空间与类中心的距离约束，以兼顾动作特征的类内聚合与类间分离，指导深度卷积神经网络学习到具有较强分辨力的特征，以促使后续进行较精确的分类。图1是该方法的整体流程示意图，在MSRDailyActivity3D和SYSU3DHOI两个数据集的实验结果表明，使用本文提出的方法，人体动作识别的准确率和鲁棒性得到了明显的提升。

# 1 动作表征方法

# 1.1RP与BRP的工作原理

将帧的图像序列表示成X=<x,x.,x,.x>,φ(x,)∈Rd表示从每一帧x中映射而来的特征向量，特征向量$\varphi ( x _ { t } )$ 前 $t$ 帧的平均值用 $V _ { t } = \frac { 1 } { t } \Sigma _ { \tau = 1 } ^ { t } \varphi ( x _ { t } )$ 表示，对任意时序 $\mathbf { \Phi } _ { t }$ 指定 $r _ { t } = w ^ { T } \bullet V _ { t }$ 表示其得分，一般来说，时序越靠后，对应的得分会越大，因此得分函数 $r _ { t }$ 满足约束： $r _ { i } > r _ { j } \Leftrightarrow i > j$ 。顺序池化过程的目的是找到满足目标函数式（1）的 $w ^ { * }$ ，

$$
a r g m i n \frac 1 2 \| w \| ^ { 2 } + \lambda \sum _ { i ~ > j } \varepsilon _ { i j }
$$

$$
{ \mathit { s } } . { \mathit { t } } . ~ w ^ { T } { \bullet } ( V _ { i } - V _ { j } ) { \geq } 1 - \varepsilon _ { i j } , \varepsilon _ { i j } \geq 0
$$

其中： $\varepsilon _ { i j }$ 是一个较小非负值，参数 $\boldsymbol { w } ^ { * }$ 可以表征在 $\nu _ { { } _ { t } }$ 刚开始但$\nu _ { { t + 1 } }$ 尚未进行之时对应的图像序列的信息，其可作为图像序列的特征描述子。

由上述分析可知，RP是无监督学习过程，可以将图像序列描述为新的特征，其是与输入图像等尺度的二维空间。由于其包含整个动作过程时空变化的信息，因此称之为动态图(dynamicimage,DI)，基于深度信息的动态图则称为动态深度图（dynamic depth images，DDI）。

![](images/c94ece8aa0245b7b1c977acb2e581f0f0906300d84b3f3b6d6553e34fcc4792b.jpg)  
图1整体流程示意图Fig.1Overall method flow  
图2 SSDDI组件分布  
Fig.2SSDDI Component distribution

由于在进行 RP 时，截止到时间 $t$ 的平均特征 $\nu _ { { } _ { t } }$ 被用于对帧 $t$ 进行分类，所以经池化后的特征偏向于图像序列的起始帧，导致起始帧对于 $\boldsymbol { w } ^ { * }$ 的影响更大。然而，这在动作识别中显然是不合理的，因为并没有先验知识可以得知哪一帧对该任务更重要。

双向顺序池化法(bidirectional rank pooling,BRP)可以大幅度的降低上述偏差。如果将上文所提及的过程称为正向DDI(ForwardDDI,DDIF)的生成过程，则将图像序列反向排序后再进行RP即为反向DDI(backwardDDI,DDIB)的生成过程，同时产生DDIF和DDIB的方法即为BRP，由此，每个动作的深度图像序列经BRP后最终将生成DDIF和DDIB一对图像。

C1 C2 C3 C1 C2 C3 C4   
C5 C6 C7 C8   
C4 C5 C6   
C9 C10 C11 C12   
C7 C8 C9 C13 C14 C15 C16

# 1.2 SSDDI

文献[18,21]的研究表明，BRP不仅受限于动作长期的动态过程，而且也受限于空间域。由于非监督的学习方式，BRP在时域中主要对突出的全局特征进行编码，却没有同时在时空域发掘出具有分辨力的运动模式。因此，若直接使用BRP对动作进行处理，将导致空间中颗粒度较小，但却对动作识别具有较高区分度的运动信息被颗粒度较大的运动信息所抑制，特别是对细粒度的动作来说，在整个动作过程中，其局部的时空子空间运动信息相比于全局的运动信息来说更重要。SSDDI将深度图像序列在空间域中按不同的颗粒度分解为多个部分，再对各部分分别进行BRP操作，最后其组合起来作为新的表征，可以有效的解决上述问题。

具体来说，将深度动作序列提取前景后，根据骨骼点数据作为引导，在空间域分别按照全身区域(body）、部分区域(part)、骨骼区域(joint)三个层次分解；其中body层次是将包含20 个骨骼点的整个人体，由于只有一个组件，所以其进行BRP后形成的DDI即为SSDDI；part层次的组件构成如表1所示，每个组件的区域由3个骨骼点之间的最大距离确定，共分成9个部分，作为9个组件，可以覆盖全身，将每个组件分别BRP后生成对应的DDI，按照图2左侧所示构造成SSDDI；joint层次的每个组件包含1个骨骼点，从表2可以看到，该层次的SSDDI共有16个组件，每个组件的区域由骨骼点所在位置对外拓展一定的距离而成，用于组件的骨骼点是从全部20个骨骼点中选取的噪声较低的16个，组件的分布见图2右侧。

表1Part层次各个组件包含的骨骼点  

<html><body><table><tr><td>Table1 Components of part level</td></tr><tr><td>C1 head,shoulder center, shoulder left</td></tr><tr><td>C2 head, shoulder center, shoulder right</td></tr><tr><td>C3 elbow left,wrist left,hand left</td></tr><tr><td>C4 elbow right,wrist right,hand right</td></tr><tr><td>C5 spine,hip center,hip right</td></tr><tr><td>C6 spine,hip center, hip left</td></tr><tr><td>C7 knee left,ankle left, foot left</td></tr><tr><td>C8 knee right,ankle right,foot right</td></tr><tr><td>C9 shoulder left,shoulder center,shoulder right</td></tr></table></body></html>

图1中展示了同一动作对应的三个层次的SSDDI，从中可以看出，相比于body层次的 SSDDI,part 和 joint层次的SSDDI对颗粒度较小的动作表征更具有分辨力，可以更有效的实现对动作进行从全局到局部运动以及结构信息的表征，将上述三个层次的SSDDI分别训练JCF-DCNN后进行决策层融合，有利于提高动作识别的准确率。

表2joint层次各个组件包含的骨骼点  

<html><body><table><tr><td>hip center</td><td>spine</td><td>shoulder center</td><td>head</td></tr><tr><td>shoulder left</td><td>elbow left</td><td>hand left</td><td>shoulder right</td></tr><tr><td>elbow right</td><td>hand right</td><td>hand left</td><td>knee left</td></tr><tr><td>foot left</td><td>hip right</td><td>knee right</td><td>foot right</td></tr></table></body></html>

# 2 JCF-DCNN

# 2.1JCF-DCNN的网络结构及超参数设置

JCF-DCNN的意义在于其具有较强的特征学习和分类能力，可以提高对SSDDI这类图像样本的分类准确率，换句话说，JCF-DCNN可以将两个相似度较高但属于不同类别的样本区分开来，以对其进行正确归类，降低动作分类的混淆程度。

其主要的特点在于联合交叉熵损失函数及中心损失函数作为网络分类层的代价函数，也即在网络训练过程中增加样本特征空间与类中心的距离约束，这样可以指导JCF-DCNN的卷积层在训练时可以学习到更具分辨力的特征。

![](images/9a685eb7e0e6320b65ea65ab971f5a63696ea25009a30be0f045de85a2364f7d.jpg)  
图3JCF-DCNN网络结构Fig.3JCF_DCNN structure

如图3所示是所提出网络的具体结构图，可以看出，JCF-DCNN具有12层，主要包含5个卷积层和3个全连接层以及后端的分类层，该网络分类层的联合代价函数由交叉熵损失函数与中心损失函数组成，表3记录了该网络架构卷积层和前2个全连接层的相关超参数设置，第3个全连接层网络的神经元数量与相应数据库的样本类别数一致。由于目前基于深度图的动作识别数据集规模普遍都比较小，若用其从头训练具有百万级训练参数的深度卷积神经网络，会出现过拟合现象，因此，本文采用迁移学习的方法，将已在大规模数据集ImageNet上预训练完成的参数，用于对本网络的全部卷积层和前2个全连接层进行参数初始化。

训练时，按上述方法初始化相应的网络层，但最后一个全连接层使用均值为0、标准差为0.01的高斯分布随机初始化。经过多次实验分析比较，将前3k次迭代学习率设置为0.001，后续的3k次迭代学习率设为0.0001，共迭代训练6000次后能够达到良好效果。动量和权重衰减因子使用经验值0.9和0.0005。为进一步避免过拟合，在图像样本进入深度卷积神经网络前，先对其尺度变换至 $2 5 6 \times 2 5 6$ ，然后以中心和四角为坐标原点，剪裁出 $2 2 4 \times 2 2 4$ 的区域，再进行镜像操作，使实际的训练样本达到输入样本量的10倍。但测试时只截取测试图像样本的中心区域，且不进行镜像操作，同时由于测试阶段只进行前馈操作，因此并不涉及中心损失函数，只需将交叉熵损失函数的输出值进行均值融合。

Table 2Components of joint level   
表3JCF-DCNN网络结构超参数设置  
Table 3Super parameter setting for JCF-DCNN   

<html><body><table><tr><td>Layer</td><td>C1</td><td>C2</td><td>C3</td><td>C4</td><td>C5</td><td>FC1</td><td>FC2</td></tr><tr><td>numb</td><td>96</td><td>256</td><td>384</td><td>384</td><td>256</td><td>4096</td><td>4096</td></tr><tr><td>filter</td><td>11²</td><td>52</td><td>3²</td><td>3²</td><td>3²</td><td></td><td></td></tr><tr><td>stride</td><td>4</td><td>1</td><td>1</td><td>1</td><td>1</td><td></td><td></td></tr><tr><td>pad</td><td>0</td><td>2</td><td>1</td><td>1</td><td>1</td><td></td><td></td></tr></table></body></html>

# 2.2 交叉熵损失函数

深度网络中的代价函数是整个网络模型的“指挥棒”，通过样本的预测结果与真实标记产生的误差反向传播指导网络参数学习与表示学习。交叉熵损失函数是目前深度卷积神经网络中

最常用的分类损失函数，其形式为

$$
L _ { S } = - \sum _ { i = 1 } ^ { m } \log \frac { \mathrm { e } ^ { W _ { y _ { i } } ^ { T } x _ { i } + b _ { y _ { i } } } } { \sum _ { j = 1 } ^ { n } \mathrm { e } ^ { W _ { j } ^ { T } x _ { i } + b _ { j } } }
$$

其中: $x _ { i } \in R ^ { d }$ 表示属于 $y _ { i }$ 类的第 $i$ 个深度特征， $d$ 是深度特征的维数， $W \in R ^ { d \times n }$ 是最后一个全连接层的权值矩阵， $b \in { \cal R } ^ { n }$ 是偏置项， $W _ { j } \in R ^ { d }$ 表示权值矩阵 $W$ 的第 $j$ 列， $\mathbf { \Sigma } _ { m }$ 和 $n$ 分别是每批训练样本的数量以及相应的类别数，由于偏差项对性能的影响极其微小，因此为了简化分析，往往可以被忽略。

由式（2）可知，交叉熵损失函数具有结构简单，计算量小的优点，因而得到了广泛的应用，然而从实际应用角度来说，该损失函数仅仅关注了待识别图像应该属于哪个类别的问题，即类间分离问题，但没有考虑同样重要的一个问题，即最终的分类器决策面区域内的空间是否均应属于该类别。实际上，同一类别下两个图像样本的距离有可能比不同类的距离还大，若在这种情况下使用交叉熵损失函数作为神经网络的代价函数，极易出现由于待分类的图像样本太相似而被误判的情况。值得注意的是，交叉熵损失函数在测试阶段不再进行梯度的计算，也不进行梯度的反向传播，仅作为计算相应类别概率值的一个函数使用。

# 2.3中心损失函数及联合代价函数

为弥补交叉熵损失函数存在问题，中心损失函数给每一类数据定义一个中心点，这个中心点和聚类问题中的中心点十分相似，目的是为了使同一类数据计算出来的特征都能靠近自身类别的中心点，聚合类内特征，特征离中心点越远，则对其惩罚越大。式（3）中对中心损失函数作了形式化的表征。

$$
L _ { C } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { m } { \left\| x _ { i } - c _ { y _ { i } } \right\| } _ { 2 } ^ { 2 }
$$

$$
\frac { \hat { \partial } L _ { C } } { \hat { \partial } x _ { i } } = x _ { i } - c _ { y _ { i } }
$$

$$
{ \Delta c _ { y _ { i } } = \frac { \alpha } { 2 } \sum _ { i = 1 } ^ { m } ( c _ { y _ { i } } - x _ { i } ) }
$$

其中： $c _ { y _ { i } } \in \mathbf { R } ^ { d }$ 可由式（4）（5）计算得出，表示 $y _ { i }$ 类深度特征$x _ { i }$ 的类中心，其随着深度特征 $x _ { i }$ 的变化而更新，参数 $\alpha$ 是范围在[0.1的缩放因子，通过调节此参数，可以对神经网络进行进一步的优化，因此其是一个超参数，变量 $\mathbf { \lambda } _ { m }$ 与 $x _ { i }$ 含义与交叉熵损失函数中介绍的一致。

为整合交叉熵损失函数和中心损失函数的优点，同时使深度特征类内聚合与类间分离，所提出的JCF-DCNN采用联合交叉熵损失函数与中心损失函数作为该网络分类层的代价函数：

$$
\begin{array} { l } { { \displaystyle { \cal L } = { \cal L } _ { s } + \lambda { \cal L } _ { c } } } \\ { { \displaystyle ~ = - \sum _ { i = 1 } ^ { m } \log \frac { \mathrm { e } ^ { W _ { y _ { i } } ^ { T } x _ { i } + b _ { y _ { i } } } } { \sum _ { j = 1 } ^ { n } \mathrm { e } ^ { W _ { j } ^ { T } x _ { i } + b _ { j } } } + \frac { \lambda } { 2 } \sum _ { i = 1 } ^ { m } \left\| x _ { i } - c _ { y _ { i } } \right\| _ { 2 } ^ { 2 } } } \end{array}
$$

$\lambda$ 是为了控制两个损失函数的比例而引入的超参数，当$\lambda = 0$ 时，联合代价函数将退化成交叉熵损失函数，图3虚线部分指示了联合代价函数在JCF-DCNN中所处的具体位置。

Table 4Comparison of recognition rates in MSRDailyActivity3D   

<html><body><table><tr><td>方法</td><td>识别率</td></tr><tr><td>IPM[24]</td><td>83.30%</td></tr><tr><td>WHDMMs+ConvNets [17]</td><td>85.00%</td></tr><tr><td>SNV [9]</td><td>86.25%</td></tr><tr><td>DS+DCP+DDP+JOULE-SVM[23]</td><td>95.00%</td></tr><tr><td>Range Sample[10]</td><td>95.63%</td></tr><tr><td>MFSK+BoVW [25]</td><td>95.70%</td></tr><tr><td>SSDD[21]</td><td>97.50%</td></tr><tr><td>本文方法</td><td>99.38%</td></tr></table></body></html>

# 3 实验与结果分析

# 3.1实验环境与方法

实验环境所用GPU为NVIDIAQuadroP2000，操作系统为Ubuntul4.04，配置并 编 译caffe-HAR(https://github.com/liyupeng-ing/caffe-HAR)，caffe-HAR是考虑到便于读者复现和验证本文所提出的方法而上传至开源网站的文件夹，其包含按照2.2节所叙述的JCF-DCNN网络模型文件以及相关的应用程序，其是在深度学习框架caffe[27]的基础上，通过设计具有联合代价函数的分类层模块拓展而来。联合代价函数的超参数均按照经验值，将 $\alpha$ 设置为0.5， $\lambda$ 设置为0.003。采用的MSRDailyActivity3D和SYSU3DHOI数据集中绝大部分动作都涉及人与物的交互过程，具有较大的挑战性，上述数据集均包含彩色视频和深度视频，以及对应的骨骼点数据，本文只使用了深度图像和骨骼点数据，并没有用到数据集中的彩色图像。

实验过程包含训练阶段和测试阶段。训练阶段，使用训练样本的 body、part 和 joint 这三个层次的 SSDDI分别训练3个网络模型；测试阶段，用三个层次测试样本的SSDDI分别输入上述对应的网络模型，对每个网络模型的分类层的输出结果进行融合，取融合后得分最大值对应的标签为识别结果，实验中使用的融合方法为均值融合，测试阶段分类层中仅有交叉熵损失函数进行工作，并不涉及中心损失函数，即此时的 $\lambda$ 将自动设置为零，此时分类层的联合代价函数退化为交叉熵损失函数。需要注意的是，每个 SSDDI 都对应有DDIF 和DDIB一对图像，因此需要先进行各个层次内的融合，再进行层次间的融合。具体来说，body层次的SSDDI对应的DDIF 和DDIB 输入网络模型后会输出2个相对应的结果，需将这两个结果进行均值融合作为该层次内的输出结果，part与joint同理，最后将三个层次的输出结果再次进行均值融合，作为最终结果。

表4MSRDailyActivity3D数据集中的识别率对比  
表5联合代价函数对网络性能的影响  

<html><body><table><tr><td colspan="5">Table5 Influence of joint cost function on network performance</td></tr><tr><td>方法</td><td>BodyDDI</td><td>Part DDI</td><td>Joint DDI</td><td>fusion</td></tr><tr><td>JCF-DCNN*</td><td>62.50%</td><td>92.50%</td><td>93.13%</td><td>96.88%</td></tr><tr><td>JCF-DCNN</td><td>65.63%</td><td>90.63%</td><td>93.75%</td><td>99.38%</td></tr></table></body></html>

# 3.2 识别结果与分析

MSRDailyActivity3D数据集由Kinect深度摄像机采集，包含16种动作，由10人完成，每人分别做2次动作，其中一个站立完成，另一个坐着完成，共有320个文件。为公平起见，训练样本和测试样本的选取均遵从文献[7]，将2，4，6，8，10号表演者的动作用于训练，1，3，5，7，9号表演者的动作用于测试。表4是各种方法的比较结果，可以看出，基于JCF-DCNN的人体动作识别方法的准确率达到了 $9 9 . 3 8 \%$ ，比SSDDI提高了 $1 . 8 8 \%$ 。

为体现JCF-DCNN中采用的联合代价函数在该网络中所起的作用，本文设置了去除中心损失函数的JCF-DCNN\*实验，如表5所示，除part层次的融合结果较低外，JCF-DCNN的其他层次以及最终结果均高于JCF-DCNN\*，而导致part层次中融合结果较低的原因可能是由于part层次的样本间相似度较低，不符合JCF-DCNN类内聚合的特性所致；值得注意的是，JCF-DCNN整体的识别率相对于JCF-DCNN\*来说，有大幅度的提升，提升幅度达到了惊人的 $2 . 8 \%$ ，说明了联合代价函数在网络性能的提升中起到了明显的效果。

SYSU3DHOI数据集共包含480个动作文件，由40个人每人演示12种动作通过深度摄像机采集而来。在SYSU3DHOI数据集上，训练和测试样本的选取与文献[23]保持一致，如表6所示，本文提出的方法在该数据集的识别率到比SSDDI要高出$1 . 6 6 \%$ ，达了 $9 7 . 0 8 \%$ 。

本文提出的方法在2个数据集的表现均优于现有方法，验证了该方法的有效性和鲁棒性，这主要是由于所提出的方法具有更强的特征学习能力以及分辨力，可以提高对SSDDI方法产生的类间差异比较小且类内差异比较大的图像样本的分类准确率。同时，这也说明了深度卷积神经网络结合传统的动作识别方法，可以优势互补，对解决人体动作识别问题具有积极意义。

表6SYSU3DHOI数据集中的识别率对比  
Table 6Comparison of recognition rates in SYSU 3D HOI   

<html><body><table><tr><td>方法</td><td>识别率</td></tr><tr><td>HON4D [8]</td><td>79.22%</td></tr><tr><td>DS+DCP+DDP+MTDA [26]</td><td>84.21%</td></tr><tr><td>DS+DCP+DDP+JOULE-SVM[23]</td><td>84.89%</td></tr><tr><td>SSDD[21]</td><td>95.42%</td></tr><tr><td>本文方法</td><td>97.08%</td></tr></table></body></html>

# 4 结束语

本文对目前人体动作识别存在的问题进行了讨论，针对SSDDI存在的不足，提出了基于JCF-DCNN的人体动作识别方法，该方法主要特点是结合交叉上损失函数与中心损失函数作为联合代价函数，具有较强的特征学习和分类能力，能够兼顾深度特征类内聚合与类间分离，有效的降低了动作分类的混淆程度。实验结果表明，与现有方法相比，采用本方法，人体动作识别的准确率和鲁棒性均得到了明显提高。在今后的工作中，将面向包含动作种类更多的大规模数据集进行研究，同时尝试设计其他深度学习模型，尝试进一步提高人体动作识别的准确率和鲁棒性。

# 参考文献：

[1]Aggarwal JK,Ryoo M S.Human activity analysis: a review [J].ACM Computing Surveys,2011,43 (3): 1-43.   
[2] 张良，鲁梦梦，姜华．局部分布信息增强的视觉单词描述与动作识别 [J].电子与信息学报,2016,38(3):549-556.(Zhang Liang,Lu Mengmeng, Jiang Hua.An improved scheme of visual words description and action recognition using local enhanced distribution information [J]. Journal of Electronics & Information Technology,2016,38 (3): 549-556.)   
[3] 王满一，宋亚玲，李玉，等．结合区域光流特征的时序模板行为识别 [J].系统仿真学报,2015,27(05):1146-1151.(Wang Manyi,Song Yaling, Li Yu,et al. Behavior recognition combining regional optical flow features and temporal templates [J].Journal of System Simulation,2015,27(05): 1146-1151. )   
[4] 秦华标，张亚宁，蔡静静．基于复合时空特征的人体行为识别方法 [J]. 计算机辅助设计与图形学学报,2014,26(8):1320-1325.(Qin Huabiao, Zhang Yaning, Cai Jingjing. Human action recognition based on composite spatio-temporal feature[J].Journal ofComputer-AidedDesign& Computer Graphics,2014,26 (8): 1320-1325.)   
[5]Shotton J, Sharp T, Kipman AA,et al. Real-time human pose recognition in parts from single depth images [J]. Communications ofACM,2013,56 (1): 116-124.   
[6]Li Wanqing, Zhang Zhengyou,Liu Zicheng. Action recognition based on a bag of 3D points [C]/ Proc of Computer Vision and Patterm Recognition. Piscataway, NJ: IEEE Press,2010: 9-14.   
[7]Wang Jiang,Liu Zicheng,Wu Ying,et al.Mining actionlet ensemble for action recognition with depth cameras [C]// Proc of IEEE Conference on Computer Vision and Patern Recognition. Piscataway,NJ: IEEE Press, 2012: 1290-1297.   
[8]Oreifej O,Liu Zicheng.HON4D: histogram of oriented 4D normals for activity recognition from depth sequences [C]// Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2013: 716-723.   
[9]Yang Xiaodong,Tian Yingli. Super normal vector for activity recognition using depth sequences [Cl// Computer Vision and Pattern Recognition. Piscataway, NJ: IEEE Press,2014: 804-811.   
[10]Lu Cewu, Jia Jiaya, Tang Chikeung. Range-sample depth feature for action recognition [Cl//Computer Vision and Pattern Recognition. Piscataway,NJ: IEEE Press,2014: 772-779.   
[11]Presti LL, Cascia ML.3D skeleton-based human action classification: A survey[J].Pattern Recognition,2016,53(C): 130-147.   
[12] Liu Mengyuan,Liu Hong,Chen Chen. Enhanced skeleton visualization for view invariant human action recognition [J].Pattern Recognition,2O17,68 (8): 346-362.   
[13] Krizhevsky A,SutskeverI,Hinton G E.ImageNet classification with deep convolutional neural networks [C]// Proc of International Conference on Neural Information Processing Systems.Cambridge,MA: MIT Press,2012: 1097-1105.   
[14] Zhang Ning,Paluri M,Ranzato M,et al.PANDA:Pose aligned networks for deep attribute modeling [C]// Computer Vision and Pattern Recognition. Piscataway,NJ: IEEE Press,2014: 1637-1644.   
[15] Oquab M,Bottou L,Laptev I,et al.Learning and transferring mid-level image representations using convolutional neural networks [Cl// Proc of IEEE Conference on Computer Vision and Pattrn Recognition. Piscataway, NJ:IEEE Press,2014:1717-1724.   
[16] Girshick R B,Donahue J,Darrell T,et al.Rich feature hierarchies for accurate object detection and semantic segmentation [C]// Computer Vision and Pattern Recognition.Piscataway, NJ:IEEE Press,2014: 580-587.   
[17] Wang Pichao,Li Wanqing,Gao Zhimin,et al.Action recognition from depth maps using deep convolutional neural networks [J]. IEEE Trans on HumanMachine Systems.Piscataway,NJ: IEEE Press,2016,46 (4):498-509.   
[18] Fernando B,Gavves E,Oramas MJ,et al.Modeling video evolution for action recognition [C]// Computer Vision and Pattern Recognition. Piscataway,NJ:IEEE Press,2015:5378-5387.   
[19] Bilen H,Fernando B,Gavves E,et al.Dynamic image networks for action recognition [C]// Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2016:3034-3042.   
[20] Fernando B,Anderson P,Hutter M,et al.Discriminative hierarchical rank pooling for activity recognition [C]// Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE Press,2016:1924-1932.   
[21] Wang Pichao,Wang Shuang,Gao Zhimin,et al. Structured images for RGBD action recognition [C]// Proc of IEEE International Conference on Computer Vision.Piscataway,NJ: IEEE Press,2017:1005-1014.   
[22] Wen Yandong,Zhang Kaipeng,Li Zhifeng,et al.A discriminative feature learning approach for deep face recognition [M]// Computer Vision.Berlin: Springer International Publishing,2016: 499-515.   
[23] Hu Jianfang，Zheng Weishi，Lai Jianhuang，et al.Jointly learning heterogeneous features for RGB-D activity recognition [Cl// Computer Vision and Pattern Recognition. Piscataway, NJ: IEEE Press,2015: 5344- 5352.   
[24] Zhou Yang,Ni Bingbing,Hong Richang,et al. Interaction part mining: A mid-level approach for fine-grained action recognition [C]// Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2016: 3323- 3331.   
[25] Wan Jun,Guo Guodong,Li S Z.Explore efficient local features from RGBD data for one-shot learning gesture recognition [J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2016,38(8):1626-1639.   
[26] Zhang Yu, Yeung D Y.Multi-task learning in heterogeneous feature spaces [C]// National Conference on Artificial Intelligence.Palo Alto,SF:AAAI Press,2011: 574-579.   
[27] Jia Yangqing，Shelhamer E,Donahue J,et al.Caffe:Convolutional Architecture for fast feature embedding [C]// Proc of the 22nd ACM International Conference on Multimedia.New York: ACMPress,2014: 675- 678.