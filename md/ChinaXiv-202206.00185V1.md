# 一个面向原始数据搜寻的快速射电暴数据集

徐志骏1,2\*，安涛1,2，郭绍光1,2，劳保强1,2，吕唯佳1,2，伍筱聪1,2

1.中国科学院上海天文台SKA区域中心联合实验室，上海2000302.鹏城实验室SKA区域中心联合实验室，深圳518066\* 联系人,E-mail: xuthus@shao.ac.cn

收稿日期：；接受日期：；  
国家自然科学基金资助项目（批准号：12041301）、国家重点研发计划大科学装置前沿研究专项（2018YFA0404603)、国家自然科学基金资助项目（批准号：11873079）和中国科学院青年创新促进会项目（编号：2021258）资助项目。

摘要快速射电暴是目前国际天文学新兴前沿热点，随着海量观测数据带来的处理和分析的挑战，亟需开展快速射电暴信号智能搜寻和甄别的研究。为了加速快速射电暴搜寻研究，我们开发了一套基于机器学习的快速射电暴数据集，它可以训练机器学习算法以搜寻原始数据中的快速射电暴。目前数据集有 8020个快速射电暴仿真图像、4010个非快速射电暴和4010个射频干扰仿真图像，这些图像是根据开放的快速射电暴观测结果构建的，并可根据需要扩展数量。本研究旨在为最先进的人工智能算法提供开源数据集，以测试和比较快速射电暴识别算法。该数据集为卷积神经网络和经典机器学习算法提供图像和 numpy 格式的文件。数据集可以实现快速射电暴和非快速射电暴分类，或快速射电暴、射频干扰和背景噪声分类。在本例中，我们使用预先训练过的31种经典卷积神经网络(CNN)。在快速射电暴/非快速射电暴分类中，在第一个历元训练中达到 $9 0 \mathrm { - } 9 2 \%$ 的准确率，在真实数据测试中达到 $9 9 . 8 \%$ 的最大准确率。

关键词 快速射电暴，机器学习，数据集

PACS: 47.27.-i, 47.27.Eq, 47.27.Nz, 47.40.Ki, 47.85.Gj

# 1介绍

找候选体[7,8]。

快速射电暴（FRB）是持续时间为毫秒或更短的明亮射电辐射脉冲[1,2]。自 2007 被发现以来，以ASKAP、CHIME和FAST为代表的国内外众多射电望远镜取得了系列观测进展和突破，推动了这一领域成为国际天文学新兴前沿热点。传统的快速射电暴搜寻使用消色散方法，首先从望远镜观测原始文件中读取"filterbank"[3] 或者“Fits”[4] 文件,并去除射频干扰（RFI）[5,6]，然后需要搜索100 到2600 pc $\mathrm { c m } ^ { - 3 }$ 范围内的大量色散度量（DM）来寻

几乎所有的快速射电暴搜寻管线[9-12]都采用传统的消色散算法进行盲搜索。尽管已经研发了很多优化算法[13-16]，然而此类算法仍然有一些缺点：大量的DM步骤会消耗大量的计算能力；太多的候选体需要人工确认；需要小心地去除射频干扰信号，否则会有太多假或者伪的结果。

我们生成了一套快速射电暴搜寻的机器学习数据集，用于在观测原始数据文件中检测快速射电暴。与在候选体中搜寻[17,18] 的方法不同，直接在观测的原始数据中搜索可以节省大量消色散的计算需求和消除干扰信号的时间，以及检测弱快速射电暴信号[19]的可能性。此外，通过训练提高机器学习方法的准确度，也可以大幅减少最终候选体的数量。

为了开展机器学习搜寻快速射电暴，我们研发了STEP软件系统1，机器学习的准确率与训练集有很大关系，而目前尚无快速射电暴的大型数据集，本文介绍了利用ASKAP开放数据创建数据集的方法。生成该数据集的主要目的是改进和优化在原始数据中搜寻快速射电暴的模型。数据集已有上万幅快速射电暴图像，由STEP在澳大利亚平方公里阵列探路者（ASKAP）[20]公开的数据中检测到的39个FRB信号模拟产生。图1显示了2次FRB观测中检测到的4个FRB信号(在不同光束中)。该数据集将公开发布，供FRB科学界使用。

已知快速射电暴信号，处理36波束、3295秒数据的观测，使用单个GPU卡只需要2743 秒。

# 2.2 模拟仿真快速射电暴信号

目前快速射电暴信号的特性还在不断发现和解析，所以模拟仿真快速射电暴信号最佳的方法是基于已有的真实快速射电暴信号。因此我们使用STEP搜寻并提取消色散后的快速射电暴信号，然后通过下述方法和参数仿真快速射电暴信号，最后将模拟仿真的快速射电暴信号注入真实的观测背景数据就可以生成数据集样本。

以下是影响数据集的几个因素及创建数据集的方法。

# 2 数据集构建

构建的快速射电暴数据集基于ASKAP开放的已知快速射电暴样本[21]。构建步骤是首先使用传统的消色散管线检测原始数据中的所有已知快速射电暴。将这些消色散后的快速射电暴信号提取后，用以模拟快速射电暴信号集。最后通过随机选择原始背景数据、快速射电暴信号集和下面介绍的方法和参数选择，就可以构建面向原始数据的快速射电暴数据集 (参见图2)。

# 2.1 快速射电暴观测和搜寻

ASKAP的开放快速射电暴数据随附于论文[21]。它发布了19 次快速射电暴观测，每个都包含36 波束的“filterbank”文件。数据为8比特，336个1MHz 通道，采样时间为1.26 毫秒，按下边带排序，最高频率为 $1 4 8 8 ~ \mathrm { M H z ^ { 2 } } )$ ：

我们使用STEP来搜寻快速射电暴信号。这是我们团队自研的一个基于GPU的开源工具包，用于快速射电暴搜寻和分析。它在中国SKA区域中心原型机（CSKA-P）[22]上进行了开发和测试，并从ASKAP公开的快速射电暴数据中搜寻出了所有

# 2.2.1 色散量

色散量是快速射电暴的主要特性，它决定了最高和最低频率之间的色散延迟时间。目前已知快速射电暴的色散量的范围是100 到 $2 6 0 0 \mathrm { p c } \ \mathrm { c m } ^ { - 3 } \ [ 7 , 8 ]$ .但是为了搜寻更远的奇异快速射电暴，搜寻的色散量范围越大越好，所以最大值可以超出2600pc$\mathrm { c m } ^ { - 3 }$ ；最小值 $1 0 0 \mathrm { p c } \ \mathrm { c m } ^ { - 3 }$ 一般认为是脉冲星或者射频干扰信号的色散范围所以维持不变。在我们的模拟仿真中，选择的快速射电暴色散量是从100pc$\mathrm { c m } ^ { - 3 }$ 到由数据带宽、频率、采样时间和图像像素确定的最大值之间随机选择的，请参见下面的4.1节。色散量对延迟时间是线性关系，所以对于超过图像最大值对应的色散量，可以通过对原始数据进行指定色散量的预处理来扩展对更大色散量的支持。比如图像最高支持色散量400，超过400的色散量需要对数据进行DM为300的消色散的预处理，这里100色散量的差值是因为色散量小于100不在搜寻范围内。预处理后支持的最大色散量提高到700。以此类推，对于更高色散量，只需对该数据继续做DM 为300 的消色散处理。基于这种方法，可以根据本地算力和具体需求自定义最小和最大色散量范围。应当注意的是，这种消色散预处理的方法只适

徐志骏等.

![](images/6bf83395b67010cf82258b3721e129a337155b0b739076c346aee33da5c0b016.jpg)  
图1使用 STEP 搜寻到的快速射电暴的样本图像。图中（a)、（b)、（c）分别是FRB170416 的第15、16、21波束。右下(d）为FRB170721的第 16 波束。在每个子图中，下方是原始数据图形，中上方是消色散后图像，顶部是去消色散数据按频率相加后的幅度分布。

Figure1SampleimagesofFRBs detectedbySTEP.Panel (a),(b),(c)areFRB170416beam15,16,21.Panel(d)isFRB170721 beam16.Ineverypanel,belowisrawdata,themiddleisddispersiondataandthetopisthesumof thededispersiondataby frequency.

![](images/8d6efeede3b9755ac83a0fa97ab0081879f190bc27aa862fdea9734768534395.jpg)  
图2构建面向原始数据的快速射电暴机器学习数据集的流程图。首先从观测数据中检测 FRB，然后提取FRB 信号来构 建 FRB 数据集，最后采用随机DM、流量和位置偏移的随机FRB 信号注入原始背景数据中。 Figure 2Flowchart explainingthe processes tobuild MADFRB.Wefirstdetected theFRBsfromobservationdata,and then extracttheFRBsignalstobuildtheFRBdataset.TheFRBsignalsthenarerandomlyselected withrandomDM,fuence,and offset to inject to the raw data.

用于推理阶段，快速射电暴数据集和训练阶段是不需要的，这里涉及主要是解释如何在实际观测数据处理时如何扩展色散量范围。

# 2.2.2 射频干扰信号

仿真的快速射电暴信号最后被注入原始数据中，原始数据背景的射频干扰信号仍然会保留。ASKAP的台址条件非常好，在大多数情况下，数据中射频干扰信号很少见，因此需要手动注入的方式模拟一些射频干扰信号。在我们的模拟仿真中，射频干扰信号被设置为色散量为零或者负数信号，这使得机器学习算法只能识别色散量为正且大于 $1 0 0 \mathrm { p c }$ $\mathrm { c m } ^ { - 3 }$ 的信号，这个限制符合实际观测。

# 2.2.3 流量强度

观测发现快速射电暴的能量或流量变化很大，即使同一个快速射电暴比如重复的快速射电暴，不同脉冲的流量也不相同，甚至同一快速射电暴的同一脉冲，不同波束中的流量也不一样 （见图1)，这表明在适当范围内调整模拟仿真信号的流量强度不仅可以扩充样本数，还可以更接近真实情况。同时为了增强弱快速射电暴信号的搜寻能力，在我们的模拟仿真中，随机增强或者减弱信号流量，流量范围从接近检测上限到真实快速射电暴的信号流量。

# 2.3 数据集统计信息

ASKAP的FRB观测数据有36个波束数据，有FRB信号的波束都是已知的，这样没有FRB信号的波束数据就可以作为噪声背景来生成无FRB的背景图像，同时通过注入RFI信号和FRB信号就可以生成RFI和FRB图像。目前数据集总共有16040个图像，包括4010个原始数据（无FRB）、RFI、FRB 和弱 FRB 图像（参见图3)。我们用于模拟的真实FRB信号来自FRB170906的4个波束（见图fig:FRB170906)，我们使用的原始数据来自该观测[21]的其他没有快速射电暴信号的波束数据，这些数据也用于注入信号以模拟FRB或RFI。

数据集的数据格式包括图像和NumPy文件。图像文件可以是“ps”、“pdf”、“svg”，默认情况下也可以是卷积神经网络（CNN）算法支持的“png”格式。STEP支持Numpy“npy”格式，或将其转换为其他FRB搜索管道支持的过滤器库文件。它还支持经典机器学习算法（如向量机、随机森林等）。因此，我们将有机会使用相同的数据集比较CNN、经典ML算法和传统FRB 管线的性能。

# 3 试验

试验在中国 SKA 区域中心原型机上进行[23]。目前中国SKA区域中心原型机具备完善的软件平台[24]，通过高速网络传输 SKA 先导设备数据[25,26]，并开展了射电天文管线的优化研究[27,28]。硬件设备拥有 4个GPU节点，共包括 16 块英伟达v100显卡和4块A40显卡。本次试验通过3个GPU 节点的16 块英伟达V100 显卡训练完成。

# 3.1 模型架构

我们使用 PyTorch3)[29] 及其自带的 torchvi-sion 软件包一起开发用于测试快速射电暴数据集的模型。torchvision软件包包括最新的可访问数据集、流行的模型架构和标准图像转换。在PyTorch1.6.0版本中，模型软件包包含以下图像分类算法以及预训练模型：

· VGG (vgg11, vgg13, vgg16, vgg19, vgg11_bn,   
vgg13__bn,vgg16__bn,vgg19_bn)[30] · DenseNet (densenet121, densenet169,   
densenet201, densenet161) [31] · ResNet(resnet18, resnet34, resnet50,   
resnet101, resnet152) [32] · ResNeXt (resnext50_32x4d, resnext101_32x8d) [33] · Wide ResNet (wide_resnet50_2,wide_resnet101_2) [34] · AlexNet [35] ·inception_v3 [36] · GoogLeNet [37] · mobilenet_v2 [38]

徐志骏等.

![](images/bd806a0e5b42aa8e2358b9af6424ab9a90ab008d847b6e441b6d254e06f7895a.jpg)  
图3快速射电暴数据集中的图像。（a）是没有FRB信号的原始数据，（b）是真实搜寻到的FRB信号，（c）是射频干扰信号，（d）是具有错误弱信号的弱流量FRB 信号，（e）是改正后正常的弱流量FRB 信号Figure3 Images inthe dataset.(a)theraw data without FRB,(b)FRB with natural energy,(c)RFI,(d)weak FRB withwrongly weak signals,and (d) corrected weak FRB.

![](images/0675fe726c600b912c938891f334a54554a322ad303f2ef38bbd7dcfe8adcff2.jpg)  
图4用于模拟的真实FRB信号来自FRB170906的4个波束 Figure 4 The real FRB signal used for simulation which come from four beams of FRB170906

· ShuffleNet v2(shufflenet_v2_x0_5, shufflenet_v2_x1_0)[39]

· SqueezeNet (squeezenet1_O, squeezenet1_1) [40] · MNASNet (mnasnet0_5,mnasnet1_0) [41]

# 3.2 预训练模型

常规的模型训练是用随机初始化来训练整个网络，这种方式耗时长，训练效果也很不稳定。本研究采用了使用预训练模型的方法。预训练模型是在一个巨大的数据集[42]上训练一个网络，然后将其用作初始化。由于我们的数据集可能与原始数据集非常不同，而且我们的数据集也可能很大，因此使用预训练模型后还需要通过训练对整个网络进行微调。

快速射电暴信号的图像，其他图像作为非快速射电暴图像。该数据截取了包含快速射电暴信号的约10秒原始数据，符合真实观测时的连续处理或者处理暂现源终端记录的候选体的缓存数据段。从表2中可以看到大多数网络的准确率可以达到 $9 9 \%$ ，而且层数更深的网络一般有更高的分类准确率。在实际应用中，为了尽可能减少错过正样本也就是快速射电暴信号，需要召回率尽量高。从表2中可以看到有3个模型的召回率都达到了 $1 0 0 \%$ ，表示所有的快速射电暴信号都找到了。召回率 $1 0 0 \%$ 的原因是正样本的快速射电暴信号在真实数据中占比非常小，所以在正样本有限情况下召回率结果不一定精确，这也说明了真实场景下提高召回率的重要性。表2中，召回率 $1 0 0 \%$ 情况下，精确率最高只有 $9 9 . 3 2 1 \%$ ，说明有一定几率出现假阳性候选体，需要一定的后续人工审查。

# 3.3 训练

我们以8:2的比例将数据集分成12832个图像训练集和3208个验证集。如上所述，本研究选取了含预训练模型的31种经典CNN算法对数据集进行试验。由于使用了预训练模型，在训练的第一个历元，大多数网络的准确率可以达到 $9 0 \%$ ，训练经过几次历元后，多数网络的准确率都超过了 $9 9 . 7 \%$ 。这说明经典CNN算法可以有效提取快速射电暴仿真数据集的图像特征，并通过多次迭代训练提高准确率。为了更好的研究不同CNN模型的分类效果，我们还计算了召回率(Recall)、精确率（Precision)和F1，其中召回率反应了模型识别正样本的能力，精确率反应了出现假阳性的概率，而F1反应了召回率和精确率在综合数值。从表2中可以看到有大多数模型的召回率、精确率和F1都在 $9 9 \%$ 以上，表明我们的快速射电暴仿真数据集非常适合经典CNN类的算法。

# 3.4 测试数据集

为了验证基于快速射电暴仿真数据集训练后的CNN 模型对于真实数据的分类效果，我们生成了16544张所有ASKAP公开的快速射电暴观测的真实FRB信号图像作为测试数据集，包括35张包含

# 4讨论

# 4.1 真实数据的图像大小和信号位置

快速射电暴数据集的首要限制就是图像的大小。卷积神经网络算法通常先将图像统一为固定大小，通常为等长的正方形图像。但在真实快速射电暴数据中，图像的高度由数据的通道数来定义，宽度由样本时间长度定义。观测中的通道数通常是固定的，因此对于真实数据我们需要选择与通道数等长的时间样本来获得等长图像。

目前数据集的生成算法中，我们默认快速射电暴的所有频段信号都在同一张图内。在处理真实快速射电暴数据时，为了保证这一点，需要对信号位置和色散量都有限制。对于未知的快速射电暴信号，为满足信号的位置限制，我们使用了设置重叠区域的方法。目前我们对ASKAP数据设置了 $5 0 \%$ 重叠，比如单张图片包括时间长度为1的话，每个图片每经过0.5就自动生成一张图片。通过计算，这样可以保证在一定色散范围内所有频段信号都在单张图片内。

对于色散量限制，正如我们在2.2.1节中提到的，色散量与延迟成正比，因此色散量的最大值也

徐志骏等.

表131种经典CNN 模型的验证集结果 Table1 31 classic CNN models with their respective validation result (Val Acc)   

<html><body><table><tr><td>模型</td><td>验证集准确率(%)</td><td>精确率 (%)</td><td>召回率 (%)</td><td>F1</td></tr><tr><td>resnet18</td><td>99.87</td><td>99.913</td><td>99.957</td><td>99.935</td></tr><tr><td>resnet34</td><td>99.731</td><td>99.896</td><td>99.835</td><td>99.865</td></tr><tr><td>resnet50</td><td>99.835</td><td>99.896</td><td>99.939</td><td>99.918</td></tr><tr><td>resnet101</td><td>98.986</td><td>99.904</td><td>99.079</td><td>99.49</td></tr><tr><td>resnet152</td><td>96.75</td><td>99.901</td><td>96.838</td><td>98.346</td></tr><tr><td>vgg11</td><td>99.818</td><td>99.913</td><td>99.904</td><td>99.909</td></tr><tr><td>vgg13</td><td>99.766</td><td>99.93</td><td>99.835</td><td>99.883</td></tr><tr><td>vgg16</td><td>99.783</td><td>99.904</td><td>99.878</td><td>99.891</td></tr><tr><td>vgg19</td><td>99.887</td><td>99.905</td><td>99.983</td><td>99.944</td></tr><tr><td>vggl1_bn</td><td>99.61</td><td>99.904</td><td>99.705</td><td>99.804</td></tr><tr><td>vgg13_bn</td><td>99.853</td><td>99.887</td><td>99.965</td><td>99.926</td></tr><tr><td>vgg16_bn</td><td>99.558</td><td>99.904</td><td>99.653</td><td>99.778</td></tr><tr><td>vgg19_bn</td><td>99.801</td><td>99.922</td><td>99.878</td><td>99.9</td></tr><tr><td>inception_v3</td><td>99.861</td><td>99.939</td><td>99.922</td><td>99.931</td></tr><tr><td>densenet121</td><td>99.827</td><td>99.948</td><td>99.878</td><td>99.913</td></tr><tr><td>densenet161</td><td>99.783</td><td>99.904</td><td>99.878</td><td>99.891</td></tr><tr><td>densenet169</td><td>99.879</td><td>99.939</td><td>99.939</td><td>99.939</td></tr><tr><td>densenet201</td><td>99.775</td><td>99.957</td><td>99.818</td><td>99.887</td></tr><tr><td>resnext50_32x4d</td><td>99.792</td><td>99.93</td><td>99.861</td><td>99.896</td></tr><tr><td>resnext101_32x8d</td><td>98.726</td><td>99.93</td><td>98.793</td><td>99.358</td></tr><tr><td>wide_resnet50__2</td><td>98.891</td><td>99.895</td><td>98.992</td><td>99.441</td></tr><tr><td>wide_resnet101_2</td><td>99.827</td><td>99.939</td><td>99.887</td><td>99.913</td></tr><tr><td>googlenet</td><td>99.818</td><td>99.93</td><td>99.887</td><td>99.909</td></tr><tr><td>mobilenet_v2</td><td>99.792</td><td>99.913</td><td>99.878</td><td>99.896</td></tr><tr><td>alexnet</td><td>99.827</td><td>99.922</td><td>99.904</td><td>99.913</td></tr><tr><td>_0 squeezenet1_</td><td>99.567</td><td>99.913</td><td>99.653</td><td>99.783</td></tr><tr><td>squeezenet1_1</td><td>98.977</td><td>99.93</td><td>99.045</td><td>99.485</td></tr><tr><td>mnasnet1_0</td><td>99.879</td><td>99.887</td><td>99.991</td><td>99.939</td></tr><tr><td>mnasnet0_5</td><td>99.307</td><td>99.774</td><td>99.531</td><td>99.652</td></tr><tr><td>shufflenet_v2_x0_5</td><td>99.766</td><td>99.904</td><td>99.861</td><td>99.883</td></tr><tr><td>shufflenet_v2_x1_0</td><td>99.567</td><td>99.913</td><td>99.653</td><td>99.783</td></tr></table></body></html>

徐志骏等.

表231种经典CNN模型的测试集结果 Table 2 31 classic CNN models with their respective test set result   

<html><body><table><tr><td>模型</td><td>测试集准确率(%)</td><td>精确率 (%)</td><td>召回率 (%)</td><td>F1</td></tr><tr><td>resnet18</td><td>99.127</td><td>98.344</td><td>99.938</td><td>99.134</td></tr><tr><td>resnet34</td><td>99.608</td><td>99.226</td><td>99.991</td><td>99.607</td></tr><tr><td>resnet50</td><td>98.896</td><td>97.862</td><td>99.982</td><td>98.911</td></tr><tr><td>resnet101</td><td>99.791</td><td>99.618</td><td>99.964</td><td>99.791</td></tr><tr><td>resnet152</td><td>99.194</td><td>98.901</td><td>99.492</td><td>99.196</td></tr><tr><td>vgg11</td><td>99.506</td><td>99.123</td><td>99.893</td><td>99.506</td></tr><tr><td>vgg13</td><td>99.581</td><td>99.247</td><td>99.92</td><td>99.582</td></tr><tr><td>vgg16</td><td>99.43</td><td>98.88</td><td>99.991</td><td>99.432</td></tr><tr><td>vgg19</td><td>97.885</td><td>95.952</td><td>100</td><td>97.934</td></tr><tr><td>vggl1_bn</td><td>99.657</td><td>99.321</td><td>100</td><td>99.659</td></tr><tr><td>vgg13_bn</td><td>98.642</td><td>97.398</td><td>99.946</td><td>98.656</td></tr><tr><td>vgg16_bn</td><td>99.657</td><td>99.317</td><td>100</td><td>99.657</td></tr><tr><td>vgg19_bn</td><td>99.069</td><td>98.206</td><td>99.982</td><td>99.086</td></tr><tr><td>inception_v3</td><td>97.217</td><td>94.951</td><td>99.761</td><td>97.297</td></tr><tr><td>densenet121</td><td>99.884</td><td>99.857</td><td>99.911</td><td>99.884</td></tr><tr><td>densenet161</td><td>99.813</td><td>99.665</td><td>99.965</td><td>99.814</td></tr><tr><td>densenet169</td><td>99.884</td><td>99.839</td><td>99.929</td><td>99.884</td></tr><tr><td>densenet201</td><td>99.817</td><td>99.731</td><td>99.901</td><td>99.816</td></tr><tr><td>resnext50_32x4d</td><td>99.532</td><td>99.133</td><td>99.938</td><td>99.534</td></tr><tr><td>resnext101_32x8d</td><td>98.753</td><td>99.403</td><td>98.091</td><td>98.743</td></tr><tr><td>wide_resnet50_2</td><td>99.1</td><td>98.3</td><td>99.919</td><td>99.103</td></tr><tr><td>wide_resnet101_2</td><td>99.706</td><td>99.45</td><td>99.964</td><td>99.707</td></tr><tr><td>googlenet</td><td>99.181</td><td>98.476</td><td>99.902</td><td>99.184</td></tr><tr><td>mobilenet_v2</td><td>99.693</td><td>99.441</td><td>99.946</td><td>99.693</td></tr><tr><td>alexnet</td><td>93.886</td><td>89.437</td><td>99.519</td><td>94.209</td></tr><tr><td>squeezenet1_0</td><td>99.212</td><td>98.814</td><td>99.616</td><td>99.213</td></tr><tr><td>squeezenet1_1</td><td>99.221</td><td>98.769</td><td>99.689</td><td>99.227</td></tr><tr><td>mnasnet1_0</td><td>96.277</td><td>93.201</td><td>99.876</td><td>96.423</td></tr><tr><td>mnasnet0_5</td><td>50.109</td><td>50.076</td><td>99.822</td><td>66.694</td></tr><tr><td>shufflenet_v2_x0_5</td><td>92.95</td><td>88.43</td><td>98.891</td><td>93.369</td></tr><tr><td>shufflenet_v2_x1_0</td><td>95.827</td><td>93.56</td><td>98.39</td><td>95.914</td></tr></table></body></html>

限制在给定时间长度的样本中。这个问题可以通过对数据在时域进行下采样来解决，但会带来灵敏度降低的风险。为了解决这个问题，我们采用了对高色散量信号进行预先消色散的解决方法。

目前ASKAP数据中我们设置了 $4 0 0 \mathrm { p c } \ \mathrm { c m } ^ { - 3 }$ （204的预消色散步骤，比如对于搜索范围 $2 0 0 0 \mathrm { p c } \mathrm { c m } ^ { - 3 }$ ，需要设置5个并行搜寻管线，分别对应不进行预消色散和预消色散 400、800、1200、1600pccm-。这样对于每个搜寻管线，只需要搜寻 $4 0 0 \mathrm { p c } \ \mathrm { c m } ^ { - 3 }$ 以内，所有信号都在单张图片的情况，有效提高搜索准确率。当然为了彻底解决限制问题，有必要解除快速射电暴所有信号都在单张图像中的限制，但这将带来其他问题，需要在后续研究中解决。

# 4.2 弱快速射电暴信号

该问题来源于本研究初期在进行随机流量强度变换时的错误。为了注入随机流量强度的快速射电暴信号，我们初期通过随机选择的流量强度因子对信号的所有频率流量同时进行增强或削弱。。检查生成的图像后，我们发现一些在真实数据中不会出现的“奇异的弱线” (参见图3)。这个问题的原因是快速射电暴信号在不同频率上流量强度表现不同，对信号进行随机流量强度变换时，原先流量强度较低的频率就可能发生信号比背景的流量强度还弱的现象，造成了“奇异的弱线”。为了解决这个问题，我们在仿真中对注入的快速射电暴信号进行检查，并将信号中的低于同频率背景强度的部分替换为背景噪声，这样仿真图像就更符合真实数据的情况。

# 4.3 快速射电暴宽度

快速射电暴信号的宽度决定了需要从观测数据中提取多少真实FRB 信号样本。FRB 的最大和最小宽度仍不确定，因此必须手动提取真实的FRB信号。类似地，尽管FRB的宽度可以设置为随机选择，但在我们的模拟中，它默认设置为不变。

# 5未来工作

数据集只是快速射电暴搜寻的第一步，未来还有很多工作需要继续。比如引入不同望远镜的观测和射频干扰数据以提高适应性。针对平方公里阵列第一期的快速射电暴研究，可以利用在SKA低频站址的SKA先导设备MWA数据，进行SKA低频快速射电暴仿真数据集研究。同样可以利用MeerKAT数据，研究SKA中频快速射电暴仿真数据集。另外快速射电暴的能量强度在不同频率会有一定随机性，不同数据格式的量化效果等还需要根据不同观测数据进行具体研究。目前快速射电暴搜寻管线研发的主要困难之一就是缺乏统一的比较手段。基于已有快速射电暴仿真数据集，进一步可以开展快速射电暴搜寻管线的比较和优化。可以有效量化管线性能，为快速射电暴搜寻管线研发、测试和优化提供统一标准。

# 6结论

为了加速快速射电暴搜寻管线研究，我们开发了一套基于机器学习的快速射电暴数据集，它可以训练机器学习算法以搜寻原始数据中的快速射电暴。同时数据集也可以作为传统快速射电暴管线的性能量化标准。数据集目前已有8020个快速射电暴、4010 个非快速射电暴和 4010 个射频干扰图像，这些图像是根据公开的快速射电暴观测结果构建的。我们为最先进的人工智能算法提供开源数据集，以比较快速射电暴识别算法。该数据集为卷积神经网络和经典机器学习算法提供图像和numpy格式的文件。数据集可以实现快速射电暴/非快速射电暴分类，或快速射电暴/射频干扰/背景噪声分类。目前图像结果已经开源，下一步测试完成后，仿真的工具包也会开源，满足特定望远镜观测数据搜寻的需求。

# 致谢

本研究使用了中国SKA区域中心原型机的资源。

# 参考文献

1 LorimerDR,Bailes M,McLaughlin,MA,etal.A Bright Milisecond Radio Burstof ExtragalacticOrigin.Science,0, 318(5851): 777-780   
2 Petroff E, Hessels JW T, Lorimer D R.Fast radio bursts,Astron Astrophys Rev, 27(1):1-75   
3 Lorimer D R.SIGPROC: pulsar signal processing programs.Astrophysics Source Code Library, 2011,ascl:1107.016   
4 Hotan A W,Van Straten W,Manchester R N.PSRCHIVEand PSRFITS: an open appoach to radio pulsar data storage and analysis. Publ Astron Soc Aust, 2004,21(3):302-309   
5 PetroffE,KeaneEF,BarrED,etal.Identifying the sourceofPerytonsattheparkes radio telescope.MonNotices Royal Astron Soc,2015,451(4):3933-3940   
6 Nita G M,Gary DE.The generalized spectral kurtosis estimator.Mon Notices Royal Astron Soc,2010,406(1):L60-L64   
7 Bhandari S,KeaneEF,BarrED,etal. TheSUrveyforPulsars and Extragalactic Radio Bursts-II NewFRBdiscoveries and their follow-up.Mon Notices Royal Astron Soc,2018,475(2):1427-1446   
8 Caleb M,KeaneEF,Van Straten W,etal.TheSUrveyforPulsarsandExtragalacticRadio Bursts-I.Polarizationproperties of FRBs 160102 and 151230. Mon Notices Royal Astron Soc,2018,478(2): 2046-2055   
9 Ransom S.PRESTO: PulsaR Exploration and Search TOolkit.Astrophysics source code library,2011,ascl:1107.017   
10 ChampionDJ,PetroffE,Kramer M,etal.Fivenewfastradioburstsfromthe HTRUhigh-latitude surveyatParkes:frst evidence for two-component bursts. Mon Notices Royal Astron Soc, 2016,460(1): L30-L34   
11 Banister KW,ShannonRM,Macquart JP,etal.The detectionofan extremelybright fastradio burstina phasedaray feed survey. Astrophys J Lett, 2017, 84l(1): L12   
12MikhailovK,Sclocco A.The Apertif Monitor for Bursts Encountered in Real-time(AMBER)auto-tuning optimization with genetic algorithms.Astronomy and computing,2018,25:139-148.   
13BarsdellBR,BailesM,BarnsDG,etal.Acceleratingincoheretddispersion.MonNoticesRoyalAstroSoc,,4(): 379-392   
14 Sclocco A,van Leuwen J，Bal HE,etal.Real-time dedispersion for fastradio transient surveys,using auto tuningon many-core accelerators.Astronomy and Computing, 2016,14:1-7   
15Zackay B,Ofek EO.Anaccurate and eficient algorithm fordetectionofradio bursts with anunknown dispersion measure, for single-dish telescopes and interferometers.Astrophys J, 2017,835(1):11   
16 Amiri M,Bandura K,BergerP,et al.TheCHMEfastradioburst project:systemoverview.Astrophys J,2018,863(1):48   
17 Connor L,van Leeuwen J.Applying deep learning to fast radio burst classification.Astron J,2018,156(6): 256   
18AgarwalD,AggarwalK,Burke-SpolaorS,etal.FETCH:Adeep-learningbasedclasiferforfasttransientclasifcation. Mon Notices Royal Astron Soc,2020,497(2):1661-1674   
19 Zhang YG,GajarV,Foster G,etal.Fastradio burst11102 pulse detection and periodicity:amachine learning approach. Astrophys J, 2018,866(2): 149   
20McConell D,AllsonJR,BannisterK,etal.The Australian Square Kilometre Array Pathfinder:Performanceof the Boolardy Engineering Test Array.Publ Astron Soc Aust,2016,33   
21ShannonRM,MacquartJP,BaisterKWetal.Thedispersion-brightnessrelationforfastradioburstsfromawide-feld survey. Nature,2018,562(7727):386-390.   
22 An T,Wu X P, Hong X. SKA data take centre stage in China.Nat Astron, 2019,3(11): 1030-1030   
23An T, Wu X C,Lao B Q,et al. Status and progress of China SKA Regional Centre prototype.arxiv:2206.13022   
24Lao B Q，Zhang Y K，An T,et al.Software Platform on China SKA Regional Center Prototype System(in Chinese).ChinaXiv:202206.00173.[劳保强,张迎康,安涛,等.(2022).中国SKA区域中心原型系统－软件平台.ChinaXiv:202206.00173]   
25GuoSG,AnT,Xu ZJ,etalProgress and Prospectof transcontinental high-speed data transmissonat SKARegional Center in China(in Chinese).ChinaXiv:xxx 郭绍光,安涛，徐志骏，等.(2022).中国 SKA 区域中心跨洲际高速数据传输进展及 展望.ChinaXiv:xxxx ]   
26GuoSG,LuY,AnTetal.ScientifcdatafowandaraysimulationanalysisfortheSKA-era(iChinese).ChiaXiv:x. [郭绍光,安涛，徐志骏,等.(2022).面向 SKA-1 时代的科学数据流及阵列模拟分析.ChinaXiv:xxxx]   
27Wei JW,Zhang CF,Zhang ZL,et al.Paraleloptimizationof the pulsar search pipelineon China SKA Regional Centre Prototype(in Chinese)．ChinaXiv:T202206.00297[韦建文，张晨飞，张仲莉，等.(2022)．低频射电脉冲星搜索的性能优化方法. ChinaXiv:T202206.00297]   
28Wei JW,Zhang CF,Lao BQ,etal.Optimization of paralel procesing of Square Kilometre Array low frequency imaging pipeline (in Chinese)．ChinaXiv:T202206.00292.[韦建文，张晨飞，劳保强，等.(2022).SKA 低频成像管线并行优化 化.ChinaXiv:T202206.00292]   
29 Paszke A,Gross S,MassaF,etal.Pytorch:Animperative style,high-performancedeeplearning library.Advancesinneural information processng systems,2019,32:8026-8037   
30 RussakovskyO,DengJ,SuH,etal.Imagenet large scalevisualrecognitionchallenge.IntJComputVis2015,15(3): 211-252.   
31 Huang G,LiuZ,VanDerMatenL,etal.Denselyconnectedconvolutionalnetworks.In:ProceedingsoftheIEEEconference on computer vision and pattern recognition.2017:4700-4708.   
32 He K,Zhang X,Ren S,etal.Deepresiduallearning forimagerecognition.In:Proceedingsof the IEEEconferenceon computer vision and pattern recognition. 2016:770-778   
33XieS,GirshickRDollrP,etal.AggregatedesidualtrasformatiosfordepeuralnetworksIn:ProcedingsofteIEE conference on computer vision and pattern recognition.2017:1492-1500   
34 Zagoruyko S,Komodakis N.Wide residual networks.arXiv preprint,20l6,arXiv:1605.07146   
35KrizhevskyA,SutskeverI,HintonGE.Imagenetclasifcationwithdeepconvolutionalneuralnetworks.Advancesinneural information processing systems, 2012,25:1097-1105   
36 SzegedyC,VanhouckeV,Ioffe S,etal.Rethinking theinceptionarchitectureforcomputer vision.In:Proceedingsof the IEEE conference on computer vision and pattern recognition. 2016: 2818-2826   
37 SzegedyC,LiuW,JiaY,etal.Going deper withconvolutions.In:Proceedingsof theIEEEconferenceoncomputerision and pattern recognition.2015:1-9.   
38 HowardAG,Zhu M,Chen B,etal.Mobilenets:Eficientconvolutional neural networks for mobile visionapplications[J]. arXiv preprint,2017,arXiv:1704.04861   
39 Zhang X,ZhouX,Lin M,etal.Shufenet:Anextremelyeffcientconvolutional neuralnetwork formobiledevices.In: Proceedings of the IEEE conference on computer vision and pattern recognition. 2018: 6848-6856   
40 Iandola F N, Han S,Moskewicz M W, et al. SqueezeNet: AlexNet-level accuracy with $5 0 \mathrm { x }$ fewer parameters and $< 0 . 5$ MB model size.arXiv preprint,2016,arXiv:1602.07360   
41Tan M,ChenB,PangR,etal.Mnasnet:Platform-awareneuralarchitecture search formobile.In:Proceedingsof the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2019: 2820-2828   
42Simonyan K,Zisserman A.Verydeepconvolutional networks for large-scale image recognition.arXiv preprint，2014, arXiv:1409.1556

# A machine learning dataset for FRB detection in raw data

XU ZhiJun $^ { 1 , 2 }$ \*，AN Tao $^ { 1 , 2 }$ , GUO ShaoGuang $^ { 1 , 2 }$ , LAO BaoQiang $^ { 1 , 2 }$ , LU WeiJia $^ { 1 , 2 }$ & WU Xiaocong $^ { 1 , 2 }$

1.SKARegionalCentreJointLab,Shanghai AstronomicalObservatoryChineseAcademyofSciences,Shanghai230, China; 2.SKA Regional Centre Joint Lab,Peng Cheng Lab,Shenzhen,518066,China

We introduce a machine learning FRB dataset that can train the ML algorithms to reach the FRBs in raw data.It has 8020 FRB simulation images,4010 non-FRBand 4010 RFI simulation images built from the public FRB observations,and can be expanded in any number as needed. This work provides an open-source dataset for state of art AI to the comparison of FRB event recognition algorithms. The dataset provides image and NumPy format files for both convolutional neural networks and clasic machine learning algorithms.The dataset can implement FRB/non-FRB classification,or FRB/RFI/Blank classification. In the example,we used 31 pre-trained classic CNNs.In FRB/non-FRB classification, it achieves the accuracy of 90-92% in the first training epoch and max accuracy of 99.8% in real FRB dataset testing.

FRB,Machine Learning,Dataset

PACS:47.27.-i, 47.27.Eq,47.27.Nz,47.40.Ki, 47.85.Gj doi: