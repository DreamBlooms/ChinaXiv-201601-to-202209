# 深度学习在遥感影像分类中的研究进展

付伟锋，邹维宝

(长安大学 地质工程与测绘学院，西安 710054)

摘要：随着遥感技术和计算机技术的不断发展，传统的遥感影像分类方法已不能满足如今遥感影像分类的需求。近年来，随着深度学习方面研究成果的不断涌现，它给遥感影像的分类提供了一种新的思路和方法。首先概述了遥感影像分类的发展和深度学习的基本概念，然后重点介绍了基于深度置信网、卷积神经网络和栈式自动编码器等深度学习模型在遥感影像分类中的研究进展，最后提出了目前研究中存在的问题及遥感影像分类的发展趋势。

关键词：深度置信网；卷积神经网络；栈式自动编码器；遥感影像分类；深度学习 中图分类号：TP751 doi: 10.3969/j.issn.1001-3695.2017.10.000C

# Review of remote sensing image classification based on deep learning

Fu Weifeng, Zou Weibao (College of Geology Engineering & Geomatics,Chang'an University,Xi'an 710o54, China)

Abstract:With thecontinuous developmentofremote sensing technologyandcomputer technology,the traditionalremote sensing image classification method can not met the needs of remote sensing image clasification.Inrecent years,with the continuous emergenceofresearchresults indeep learing,itprovidesanewwayfortheclassficationofremotesensing mages. This paper first outlines the development ofremote sensing image classification and thebasicconcepts ofdeep learning,and then focuses onthe research progressin the clasification ofremote sensing images based on the deep learning model such as deepbeliefnetwork,convolutionalneuralnetworkandstackeduto-encoder.Finalltheexistingisuesandthefuturedirections of remote sensing image classification based on deep learning are summarized.

Key Words:deepbeliefnetwork; convolutionneuralnetwork;tackedauto-encoder;Remote sensing imageclasification;dep learning

# 0 引言

遥感技术作为一种重要的对地观测技术，能够从人造卫星、飞机或其他飞行器上收集地物目标的电磁辐射信息，进而判定地球上的环境和资源。随着遥感影像技术的不断进步，遥感影像逐渐呈现出高光谱、高空间、高时间分辨率的特点[1]。目前，随着遥感影像不断被应用于矿产勘探、精准农业、城市规划、林业测量、军事目标识别和灾害评估中，对影像的分类精度和效率要求不断被提高。但是遥感影像的分类受到多种因素影响，如遥感影像的波段选择、复杂的地表信息等使得影像分类比较困难。在遥感影像的应用中一般要对影像进行分类，而遥感影像目标特征的有效提取和表达则是影像分类中的重点。

遥感影像分类是一个复杂的数据处理过程，传统的目视解译方法虽然简单易操作、灵活性强，但是需要解译人员具有丰富的经验、专业的知识，而且花费时间长、解译精度差，已经不适合当今的海量遥感影像分类。后来，人们利用遥感影像的光谱、纹理等特征，通过统计模式识别方法实现遥感影像的解译，如最大似然法、最小距离法、K-均值聚类法等。但是针对高分辨遥感影像中大量的细节信息和地物光谱的复杂化问题分类准确率下降。因此，新的方法如人工神经网络[2]、支持向量机[3]、遗传算法[4]、面向对象[5]等被用于遥感影像的解译中，虽然取得了很好的分类效果，但是自动化程度不高。近年来，深度学习的出现[为遥感影像的解译提供了一种新的方法，它是一种深层次结构的神经网络，比人工神经网络、支持向量机等浅层结构的模型能够更好的提取遥感影像的特征，实现对高光谱遥感影像的降维，并在影像分类中取得了比以往更高的精度，能够更好的推动遥感影像自动化、智能化解译的发展。深度学习的优点是能够更好的进行特征选择与特征提取，遥感影像的应用基础是要有好的分类精度，而分类精度主要和影像的特征提取和特征选择有关，运用深度学习技术能够很好的提取遥感影像的特征，进而提升影像的分类精度，使其在实际运用中发挥更好的效果。

典型的深度学习模型主要有深度置信网（deepbeliefnetwork，DBN）[6]、栈式自动编码器网络（stacked auto-encodernetwork，SAE）[7]和卷积神经网络（convolutional neural network,CNN）[8]，本文将分别介绍这三个模型在遥感影像分类中的应用以及研究进展，最后对这三个模型在遥感影像分类领域中的应用情况进行比较分析，指出目前存在的问题，并展望了遥感影像分类的未来发展方向。

# 1 基于DBN的遥感影像分类

# 1.1DBN 模型简介

DBN是由多个RBM堆叠而成的概率生成模型，具有三个隐藏层的典型DBN模型如图1所示。DBN的底层接收数据训练集，第一个RBM模型是高斯-伯努利RBM，其余的RBM模型是伯努利-伯努利RBM。DBN的学习过程主要包括预训练和微调两个阶段，预训练时采用逐层训练的方式对各层中的RBM进行单独训练，并且层之间的权重和偏差被固定和保存用于进一步的分析。在微调阶段，DBN模型的权重和偏差将通过使用标记的输入数据的反向传播算法进行更新，具体的细节可以参考[9]。

![](images/fcc5835497406b3fe48fa0e3d83ff591701b30f183d5b4621de956748f8e389e.jpg)  
图1DBN网络结构图

# 1.2基于DBN模型的遥感影像分类研究进展

随着近年来深度学习的不断发展，DBN模型不断被应用于语音、图像数据集的处理上面并取得不错的成果[10,I1]。2010 年,Mnih和Hinton将首次将DBN模型应用于对机载遥感影像中的道路检测，证实了DBN 模型能够很好的提取出影像的特征并取得很好的分类效果[12]。但是随着高光谱、高分辨率遥感影像以及合成孔径雷达（synthetic aperture radar，SAR）影像的数据越来越多，遥感影像的分类也出现了新的问题。下面将分别介绍基于深度学习中的DBN 模型在高光谱遥感影像和高分辨遥感影像中的应用和研究进展。

# 1.2.1DBN模型在高光谱遥感影像中的应用

高光谱遥感影像的分类方法一般是基于混合像元分解、特征空间的分类和光谱匹配的影像分类。但是由于Hudge现象、有限的训练样本和光谱特征的空间变异性使得影像的分类比较困难。2014年，Li等人将DBN引入高光谱遥感影像中用来提取影像特征和图像分类，而且也可以用于空谱分类，但是学习率和分类的精度之间需要进一步平衡[13]。之后，Chen等根据高光谱数据在光谱和空间变化下的数据特性，提出基于DBN 的一种新的特征提取和影像分类方法用于高光谱数据的特征学习和分类问题，有效地解决了由于数据复杂和样本数目有限而引起的问题[14]。Zhou 等人[15]提出的分组置信网络在高光谱遥感影像的空谱分类中能够取得了更好的结果，分组置信网络是结合了高光谱特征的分组知识和深度神经网络，能够减少与神经网络连接的多余特征分组之间的权重，进而为空谱分类去除大量多余的光谱波段。最新研究表明，Zhong等人提出多元化DBN模型，先用非监督学习预训练未标记的样本，再用监督学习微调解决样本少的问题，然后引入多元化处理运用DBN时隐藏单元参数持续反映和无应答的情况，取得了比最初的DBN 模型以及其他的方法用于高光谱遥感影像分类时更好的精度[16]。1.2.2DBN模型在高分辨率遥感影像中的应用

高分辨率遥感影像虽然为人们理解世界提供了准确的信息，但是也为遥感影像领域的智能解译带来了挑战。以前的像素级影像分类方法随着遥感影像分辨率的提高已经不在适用，因为单个像素可能存在有不同类型的地物。2013年，Chen 等人用DBN模型提取高分辨率遥感影像中的飞机，利用DBN能够学习特征和利用BP调整参数的特点证实了比传统特征分类器的提取方法更好[17]。2014年，Zou等人提出将影像的特征选择问题转换为DBN中的重构问题用于高分辨率遥感影像的分类，并在RSSCN7数据集上验证总体分类精度达到了 $7 7 \%$ ，但是运行时间相比直接使用DBN进行影像分类较长[18]。2016年,Diao等人结合DBN的无监督特征学习和视觉显著性的优点，有效的避免了在图像上进行穷举搜索并产生少量的边界框，从而可以快速准确地定位目标，但是这种方法不能很好的检测多尺度物体[19]。

由于SAR影像具有全天候、全天时、不受大气传播和气候影响、穿透力强的特点，越来越多的SAR影像被用于土地利用和土地覆盖的监测、军事侦察卫星等领域。但是影像分类时特征选择比较困难，Dou 等人于2014年首次将DBN 模型用于SAR 影像中的城市地图的制作[20]。之后，Radu 等提出一个卷积DBN模型用于极化SAR影像的特征提取，DBN模型可以逐层的提取更高层次的特征，然后利用卷积的特征不变形将其扩展到极化SAR影像，能够有效的提取出极化SAR影像的特征，在通过对德国Kaufbeuren机场的全极化多视F-SAR图像的分类验证中取得了 $8 8 . 7 \%$ 的精度[21]。

近年来，由于DBN 模型具有无监督学习的特征和能够更好的提取影像中的特征，越来越多的基于DBN 模型的方法不断被提出用于高光谱影像和高分辨率遥感影像的分类，高光谱影像的数据复杂和样本数有限问题、高分影像的精细分类和目标检测以及SAR 影像的特征提取问题都将随着深度学习模型的不断改进以及与空间信息（纹理、大小、形状、位置等）的结合而取得更好的效果。

# 2 基于CNN的遥感影像分类

# 2.1 CNN模型介绍

卷积神经网络是一种前馈神经网络，它是受生物学上感受野（respective field）的机制而提出的。20世纪60 年代，Hubel等人通过对猫视觉皮层细胞的研究，提出了感受野这个概念[22]。1980年，Fukushima基于感受野概念提出了第一个卷积神经网络神经认知机[23]。1998年，LeCun 等成功地训练基于反向传播算法的CNN架构，首次成功应用于图像分类[24]。CNN本质上是一个多层感知机，但是由于它的局部连接、权重共享以及空间或时间上的次采样特性使得卷积神经网络在处理二维图形上具有一定程度上的平移、缩放和扭曲不变性。

典型的CNN结构是由输入层、卷积层、池化层、全连接层构成，每一层有多个特征图，每个特征图通过一种卷积滤波器提取输入的一种特征，如图2所示。

CNN的训练是通过反向传播和随机梯度下降进行的，逐层更新卷积神经网络的权重和偏置，详细过程可参考文献[25]。

![](images/a08508a0dd557d051ec5d326b970c750fffb5156a757fc79f10351b548cb222d.jpg)  
图2卷积神经网络结构图

# 2.2基于CNN模型的遥感影像分类研究进展

虽然CNN模型已经提出许多年，但是一直没有受到重视，直到2012年Krizhevsky等人提出训练CNN模型运用于图像的分类在InageNet比赛中取得了很好的分类结果比第二名高约10 个百分点[26]，此后CNN模型被广泛运用于图像分类、人脸识别、目标检测中[27-30]。CNN 的权值共享特性可以减少网络的参数训练数量，对高维数据的处理具有明显的优势，而且不用手动选取特征，只需训练好权重，就可以很好的提取特征。但是CNN也有许多缺点，易于过拟合需要大量的已知类别的训练样本来提高模型的泛化能力，而且神经网络本身就是一种"黑箱模型"物理含义不明确，计算量大等。

# 2.2.1CNN模型在高光谱遥感影像中的应用

高光谱遥感图像中包含了丰富的光谱和空间信息，由于CNN具有局部连接、权值共享等特性，近年来部分学者尝试使用CNN模型对高光谱影像进行分类并取得了一定的效果。2015年，Adriana提出非监督的神经网络用于遥感影像的分析，这种方法用贪婪逐层非监督预训练来形成一个深度CNN 模型，它通过获取每个像元的光谱矢量，再利用CNN卷积层提取光谱矢量上的局部光谱信息，并将卷积操作生成的特征图作为全连接层的输入，最后完成高光谱遥感图像的分类，避免了用有监督方法训练时高光谱影像的Hudge现象和小样本造成的过拟合问题，但是相比监督分类不能有效的提取影像的特征[31]。之后，

Chen 等人提出一种有监督的3D-CNN 模型能够同时提取影像的光谱和空间特征，并结合正则化方法和dropout 策略防止过拟合和提高模型的泛化能力，使得分类精度进一步提升[32]。

# 2.2.2CNN模型在高分辨率遥感影像中的应用

虽然深度学习中的CNN模型在许多领域都取得了很好的表现，尤其在高光谱影像的研究中，但是由于SAR影像复杂的散射机制和随机噪声使得SAR影像的分类比较困难。Chen 等提出用全卷积网络即不包括全连接层只有稀疏连接层对SAR影像进行自动目标识别和分类，有效地缓解了由有限的样本造成的的过拟合问题，并在MSTAR数据集中达到了 $9 9 \%$ 的准确率，明显优于传统的分类方法[33]。之后，Zhou 等人研究了使用深层CNN模型在极化SAR影像的监督分类中的可适性，他们将极化SAR影像转换为6维的特征矢量输入CNN模型中进行特征提取和分类，并在SanFrancisco 和Flevoland两个区域的机载SAR影像上进行验证取得了较好的分类准确度，为以后极化 SAR 影像的分类提供了一种新的途径[34]。最近Hu等人把高光谱数据和极化SAR数据结合起来用于市影像的分类，并提出一个双流的卷积神经网络用来处理它们，这样既可以利用高光谱数据的光谱信息又可以利用极化SAR数据的散射机制能够更好的分辨城市中的地物[35]。

最近研究表明，Grant等人提出用迁移学习和数据增强方法来结合深度CNN能够很好的克服遥感影像中样本有限的问题[36]。Weng等人结合CNN学习特征的能力和极限学习机[37]的泛化性能用于高空间分辨率影像的土地利用分类，相比传统的方法能够降低计算量并取得好的分类精度[38]。随着深度学习的发展，CNN也不断的被应用于遥感影像的应用中，例如道路和建筑物的提取、目标物的检测和土地利用的分类等[39-42]。

# 3 基于SAE的遥感影像分类

# 3.1 SAE模型介绍

堆栈式自编码器是由若干稀疏自编码器结构单元组成的深度神经网，网络结构如图3所示。栈式自动编码器是典型的深层神经网络被广泛用于特征学习和表示，通过贪婪学习逐层确定参数，再从顶层反向传播来调整整个网络的参数。网络的最顶层没有标签信息，则学习过程是无监督的学习过程，如果将样本的标签信息添加到最顶层，以反向调整网络范围的参数，则学习过程将成为监督学习过程，详细细节可参考文献[43]。

# 3.2基于SAE模型的遥感影像分类研究进展

# 3.2.1SAE模型在高光谱遥感影像的应用

高光谱遥感影像具有特征空间维数高，数据相关性强，冗余度高的特点，这给影像的分类带来了巨大困难，一般需要对影像进行降维去除多余的波段信息才能进行影像的特征提取。传统的高光谱遥感图像的降维主要采用主成分分析、独立成分分析、或最小噪声分离变换等降维算法从原始数据中提取具有代表性的波段进行分类。尽管这些算法有效避免了“Hughes现象”，提升了分类效率，但是却在一定程度上丢失了原数据中所蕴涵的丰富信息，导致分类精度的下降。

近年来，越来越多的研究者采用基于深度学习的方法对高光谱遥感图像进行分类。2014 年，Chen 针对高光谱遥感影像非线性特性的特征提取，将栈式自编码网络应用到高光谱遥感影像分类中，虽然该方法较传统方法取得了较大突破，但SAE网络的各层都是全连接，会产生较多参数，因而需要较多样本用于训练[44]。之后，Tao 等人基于此用堆栈稀疏编码器模型改进了学习机制，并且利用深度学习可以同时处理大量的数据和学习可以共用于多个影像的特征表示特点，验证了从一个影像学习的光谱空间特征可以转移到其他相关的影像中[45]。Lv 等人提出把极限学习机和SAE结合起来可以处理高光谱影像分类中的数据复杂和样本有限的问题[46]。同时，基于栈式自动编码器的遥感影像也逐渐用于土地利用的分类方面[47,48]。

![](images/9d130fb7821419f2e47d3fd9d1991f82754588222cb565b322b6bd7f184c012e.jpg)  
图3自动编码器结构图

# 3.2.2SAE模型在高分辨率遥感影像的应用

随着高分辨率遥感影像在实际应用中越来越多，新的分类方法也不断被提出，Ding 等人提出了一种基于SAE的遥感图像土地利用分类新方法，并通过GF-1遥感数据验证。实验结果表明，与支持向量机和BP神经网络相比，基于SAE的遥感图像土地利用分类方法可以取得较好的分类效果，影像的总体分类精度达到 $9 5 . 5 \% [ 4 9 ]$ 。但是自动编码器不能有效解决图像数据中的池化问题，并且大量冗余参数被强迫参与计算使得运算效率较低，因此卷积自动编码器被提出用于高分辨遥感的特征提取。卷积自编码器利用了传统自编码器的无监督的学习方式，结合了卷积神经网络的卷积和池化操作，从而实现特征提取，最后通过堆叠实现一个深层的神经网络。2015年，Geng等人提出卷积自动编码器用于高空间分辨率的SAR影像的分类，能够有效地解决 SAR 影像缺少有效的特征表示和斑点噪声的存在问题，但是模型的参数选择是一个制约精度的因素[50]。最近Gong 等人提出把稀疏自动编码器，CNN 和无监督分类结合起来，综合利用三者的优点解决SAR影像的三元变化检测问题。SAE用于将不同的图像转换成合适的特征空间来抑制噪声，提取关键变化信息，并将SAE学习到的特征映射作为CNN的输入。然后对SAE学习的特征表示进行无监督聚类，为训练CNN作为变化特征分类提供可靠的伪标记，并且实验验证了提出的框架的有效性和优越性[51]。

# 4深度学习模型在遥感影像分类的比较分析

自从深度学习提出以来，大量国内外学者对深度学习中的模型进行了不断改进，并在语音识别、图像分类、人脸识别等领域取得了巨大的成功。随着深度学习在各个领域的应用取得了突破进展，部分学者把深度学习也运用到了遥感领域，本文通过对深度学习中的三个主要模型在遥感影像中的应用进行了概述，分析了各个模型在影像的分类中的研究情况，现对深度置信网、卷积神经网络、栈式自动编码器网络在遥感影像分类中的运用情况进行比较分析，总结为以下两点：

a）虽然CNN模型可以用于影像的分类，但是在高光谱遥感影像的分类中，由于图谱合一、高维度和数据中非线性成分的存在使得高光谱影像不能直接分类，一般需要对影像进行降维处理，才能使用CNN进行分类。而SAE可以对高维影像进行降维，并且可以结合极限学习机的方法解决由于数据复杂和样本数目有限的问题。由于DBN模型可以更好的提取影像的深层特征，在高光谱遥感影像中也会引入DBN用来提取影像特征和图像分类，提升分类的精度。

b)高分辨率遥感影像的精度较高，能够更准确的识别地物信息。在实际应用中，高分影像一般用于目标识别、土地覆盖的变化等，而CNN可以很好的获取影像纹理信息，捕捉像素与像素之间的空间特征，因此，一个训练好的CNN 模型在地物提取中具有很大的优势，图像识别大多用卷积神经网络。另外卷积自编码器由于能够改善 SAR 影像特征表示较少和存在斑点噪声问题，在SAR影像的特征提取和影像分类方面具有潜在的优势。

# 5 基于深度学习的遥感影像分类中存在的问题及研究展望

在遥感应用中，通过遥感影像解译识别各种地物是遥感影像处理的重要目的，而分类问题是遥感影像信息提取中最基本的问题之一，虽然深度学习的新理论和新方法在遥感影像分类研究方面取得了一定的成果，但是也存在着如下的一些突出问题：

a）DBN 模型虽然可以很好的提取影像的特征，但是不能  
直接提取高维数据影像的特征，而且模型的网络结构以及参数  
选择需要依据经验或实验方法来选取最优，运算时间长。b）由于遥感影像的样本有限，在用CNN模型进行影像的  
分类时易于出现过拟合问题，而且样本的数量少也限制了CNN  
模型的泛化能力。c）虽然SAE模型可以实现对在高维影像的降维，但是逐  
层训练法的方式使得现有的预训练算法和系统参数优化策略对  
类标数据集有较强依赖性，不是真正意义上的“无监督分类”。

而且随着隐藏层个数和神经元数量的增加，梯度稀疏越严重，仍然会陷入局部最优。

从目前基于深度学习的遥感影像分类中存在的问题，可以发现未来将深度学习用于遥感影像分类时，有以下几个方向值得进一步研究：a)如何更加快速准确确定最佳的深度学习模型的结构以及神经单元的数量使遥感影像的分类精度更高，同时避免深度模型中的过拟合和局部最优问题。b)针对遥感数据样本有限的问题，可以结合其他方法如迁移学习、极限学习机和数据增强等方法对样本数量进行扩容，可以有效地解决样本容量有限的造成的过拟合问题。c)可以把深度学习中的模型进行结合用于遥感影像的分类，如卷积DBN、卷积自动编码器等模型可以充分发挥各自的优势，弥补它们的不足。

# 6 结束语

目前，遥感影像分类中使用较多的仍然是传统的分类方法。近年来，随着深度学习的提出并不断发展，这种方法不断被应用于遥感影像的分类中，虽然影像的分类精度有明显提高，但是也存在一些不足。为了进一步提高分类，综合利用各种信息进行遥感影像的分类是非常必要的。本文主要介绍了深度学习的三个主要模型和它们在遥感影像分类中的具体应用，总结了限制遥感影像分类精度的原因和各个模型的优点。同时也介绍了大量国内外学者在深度学习和遥感影像分类方面中的一些研究以及存在的问题，未来随着遥感技术和计算机技术的不断发展，影像的智能化解译将是一个重要的发展趋势。

# 参考文献：

[1] 李德仁，童庆禧，李荣兴，等．高分辨率对地观测的若干前沿科学问题 [J]．中国科学：地球科学,2012,42(6):805-813.   
[2]Canty M J.Boosting a fast neural network for supervised land cover classification.[M].[S.1.] :Pergamon Press,Inc.2009.   
[3]Huang C,Davis L S,Townshend JRG.An assessment of support vector machines for land cover classification [J]. International Journal of Remote Sensing,2002,23 (4): 725-749.   
[4]Tseng MH, Chen S J,Hwang G H, et al.A genetic algorithm rule-based approach for land-cover classification [J]. Isprs Journal of Photogrammetry and Remote Sensing,2008,63 (2):202-212.   
[5]Huan Y U, Zhang SQ,Kong B,et al. Optimal segmentation scale selection for object-oriented remote sensing image classification [J].Journal of Image and Graphics,2010,15 (2): 352-360.   
[6]Hinton G E,Osindero S,Teh YW.A fast learning algorithm for deep belief nets.[J].Neural Computation,2006,18(7):1527.   
[7]Hinton G E, Salakhutdinov RR.Reducing the dimensionality of data with neural networks[J]. Science,2006,313 (5786):504.   
[8]Lecun Y,Bottou L,Bengio Y,et al. Gradient-based learning applied to document recognition [J].Proceedings of the IEEE,1998,86 (11):2278- 2324.   
[9]Bengio Y,Lamblin P,Dan P,et al. Greedy layer-wise trainingof deep networks [Cl// Proc of International Conference on Neural Information Processing Systems. Cambridge: MIT Press,2006: 153-160.   
[10] Mohamed A,Dahl G,Hinton G.Deep belief networks for phone recognition [Cl// Proc ofNIPS Workshop on Deep Learning for Speech Recognition and Related Applications. 2009,1(9): 39.   
[11]Farabet C, Couprie C, Najman L,et al. Learning Hierarchical features for scene labeling[J].IEEE TransonPattern Analysisand Machine Intelligence, 2013,35 (8): 1915-1929.   
[12] Mnih V,Hinton G E.Learning to detect roads in high-resolution aerial images [C]//Proc of European Conference on Computer Vision.2010: 210- 223.   
[13] Li T, Zhang J, Zhang Y. Clasification of hyperspectral image based on deep belief networks [Cl//Proc of IEEE International Conference on Image Processing.2015:5132-5136.   
[14] Chen Y,Zhao X,Jia X.Spectral-spatialclassificationofhyperspectraldata based on deep beliefnetwork[J]. IEEE Journal ofSelected Topics in Applied Earth Observations and Remote Sensing,2015,8(6): 2381-2392.   
[15] Zhou X,Li S,Tang F,etal. Deep learning with grouped features for spatial spectral classification of hyperspectral images [J].IEEE Geoscience and Remote Sensing Letters,2016,14 (1): 97-101.   
[16] Zhong P,Gong Z,Li S,etal. Learning to diversify deep belief networks for hyperspectral image classification [J].IEEE Trans on Geoscience and Remote Sensing,2017,55 (6): 3516-3530.   
[17] Chen X, Xiang S,Liu CL,etal. Aircraft detectionby deep belief nets [C]/ Proc of the 2nd IAPR Asian Conference on Pattern Recognition.2013:54- 58.   
[18] Zou Q,NiL, Zhang T,et al. Deep learning based feature selection forremote sensing scene classfication [J]. IEEE Geoscience and Remote Sensing Letters,2015,12(11): 2321-2325.   
[19] Diao W,Sun X,Zheng X,et al.Efficient saliency-based object detection in remote sensing images using deep belief networks [J]. IEEE Geoscience and Remote Sensing Letters,2016,13 (2):137-141.   
[20] Lv Q,Dou Y,NiuX,etal. Classification of land cover basedon deep belief networksusingpolarimetric RADARSAT-2 data[C]//Proc ofGeoscience and Remote Sensing Symposium.2014: 4679-4682.   
[21]Tanase R,Datcu M,Dan R.A convolutional deep belief network for polarimetric SAR data feature extraction [C]//Proc of Geoscience and Remote Sensing Symposium. 2016: 7545-7548.   
[22] Hubel D H,Wiesel T N.Receptive fields，binocular interaction and functional architecture in the cat's visual cortex [J].Journal of Physiology 1962,160 (1): 106.   
[23]Fukushima K.Neocognitron: A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position [J]. Biological Cybernetics,1980,36(4):193-202.   
[24] Lecun Y,Bottu L,Bengio Y,et al Gradient-based learming applied to document recognition [J]. Proceedings of the IEEE,1998,86 (11): 2278- 2324.   
[25]RumelhartDE,Hinton GE, Wiliams RJ.Learning representations bybackpropagating errors [J]. Nature,1986,323 (6088): 533-536.   
[26] KrizhevskyA,Sutskever I,Hinton GE.ImageNet classification with deep convolutional neural networks [C]// Proc of International Conference on Neural Information Processing Systems.2012: 1097-1105.   
[27] Lawrence S, Giles C L,Tsoi A C,et al. Face recognition: a convolutional neural-network approach [J]. IEEE Trans on Neural Networks,1997,8 (1): 98-113.   
[28] Taigman Y, Yang M, Ranzato M,et al.DeepFace: closing the gap to humanlevel performance in face verification [C]/ Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC: IEEE Computer Society,2014: 1701-1708.   
[29] Girshick R,Donahue J,DarrellT,etal.Rich feature hierarchies foraccurate object detection and semantic segmentation [Cl// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2014: 580-587.   
[30] XuW,Xu W,YangM,etal.3D Convolutional neural networks for human action recognition [J]. IEEE Trans on Patern Analysis and Machine Intelligence,2013,35(1): 221-231.   
[31] RomeroA, Gatta C, Camps-Vals G. Unsupervised deep feature extraction for remote sensing image classification [J]. IEEE Trans on Geoscience and Remote Sensing,2016,54 (3): 1349-1362.   
[32] Chen Y,Jiang H,Li C,et al. Deep feature extraction and classification of hyperspectral images based on convolutional neural networks [J]. IEEE Trans on Geoscience and Remote Sensing,2016,54 (10): 6232-6251.   
[33] Chen S,Wang H,Xu F,et al. Target classification using the deep convolutional networks for SAR images [J]. IEEE Trans on Geoscience and Remote Sensing,2016,54 (8): 4806-4817.   
[34] Zhou Y, Wang H, Xu F,et al. Polarimetric SAR image clasification using deep convolutional neural networks [J]. IEEE Geoscience and Remote Sensing Letters,2016,13 (12): 1935-1939.   
[35] HuJ,Mou L,Schmitt A,etal.FusioNet: a two-stream convolutional neural network for urban scene classification using PolSAR and hyperspectral data [C]// Urban Remote Sensing Event.2017.   
[36] Scott GJ,England MR,Starms WA,et al. Training deep convolutional neural networks for land-cover classification ofhigh-resolution imagery [J] IEEE Geoscience and Remote Sensing Letters,2017,14(4): 549-553.   
[37] Huang GB,Zhu QY,Siew C K.Extreme learning machine: Theory and applications [J]. Neurocomputing,2006,70 (1-3): 489-501.   
[38] Weng Q,Mao Z,Lin J,et al.Land-use classification via extreme learning classifier based on deep convolutional features [J]. IEEE Geoscience and Remote Sensing Letters,2017,14 (5): 704-708.   
[39] Alshehhi R,Marpu PR, Wei L W,et al. Simultaneous extractionof roads and buildings in remote sensing imagery with convolutional neural networks [J].Isprs Journal of Photogrammetry and Remote Sensing,2017,130:139 149.   
[40] Chen X,Xiang S,Liu CL,etal. Vehicle detection in satelite images by hybrid deep convolutional neural networks [J]. IEEE Geoscience and Remote Sensing Lettrs,2017,11(10): 1797-1801.   
[41]张义德，胡长雨，胡春育．基于卷积神经网络的遥感图像飞机检测[J]. 光电子技术,2017,37(1):66-71.   
[42] Castelluccio M,Poggi G,Sansone C,etal.Land use classification in remote sensing images byconvolutional neural networks [J]. Acta Ecologica Sinica, 2015,28 (2): 627-635.   
[43] Bengio Y.Learning Deep Architectures for AI [M].[S.1.] : Now Publishers, 2009.   
[44] Chen Y,Lin Z,Zhao X,et al. Deep learning-based classification of hyperspectral data[J]. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2014,7(6): 2094-2107.   
[45] Tao C,Pan H,Li Y,et al. Unsupervised spectral-spatial feature learning with stacked sparse autoencoder for hyperspectral imagery clasification [J]. IEEE Geoscience and Remote Sensing Leters,2015,12 (12): 2438-244.   
[46] LvF, Han M, Qiu T. Remote sensing image classification based on ensemble extreme learning machine with stacked autoencoder [J]. IEEE Access,2017, 5: 9021-9031.   
[47] Ding A,Zhou X. Land-Use Classification with Remote Sensing Image Based on Stacked Autoencoder [C]// Proc of International Conference on Industrial Informatics-ComputingTechnology，IntellgentTechnology, Industrial Information Integration.2017: 145-149.   
[48] Li W,FuH,YuL,etal. Stacked autoencoder-based deep learning for remotesensingimagecassicai: acasestudyofficanlandcovemapping[J]. International Journal of Remote Sensing,2016,37 (23): 5632-5646.   
[49] Ding A, Zhou X.Land-use classification with remote sensing image based on stacked autoencoder [C]/ Proc of International Conference on Industrial Informatics-Computing Technology，Intelligent Technology， Industrial Information Integration. 2017: 145-149.   
[50] Geng J,Fan J, Wang H,et al. High-Resolution SAR image clasification via deep convolutional autoencoders [J]. IEEE Geoscience and Remote Sensing Letters,2015,12(1): 2351-2355.   
[51] Gong M,Yang H,Zhang P. Feature learning and change feature classification based on deep learning for ternary change detection in SAR images [J]. Isprs JournalofPhotogrammetry and Remote Sensing,2017,129: 212-225.