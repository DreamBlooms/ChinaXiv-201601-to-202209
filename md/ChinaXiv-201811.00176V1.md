# 基于权值分布的多模型分类算法研究\*

蒋梦莹1²，林小竹1，柯岩1²，魏战红1(1．北京石油化工学院 信息工程学院，北京 102617;2.北京化工大学 信息科学与技术学院，北京 100029)

摘要：为了提高卷积神经网络对图像分类的正确率，对网络结构进行研究，提出了多模型融合卷积神经网络。通过提取单个模型的输出特征向量，进行融合后得到新的输出特征向量，再搭建单层分类器进行图像分类，提高分类准确率。将单个模型与多模型融合的分类准确率进行比较，多模型融合卷积神经网络的分类准确率有所提高。并分析了卷积神经网络最后一层全连接层的权值分布，发现同一模型在不同数据集上权值分布曲线相似，分类效果好的网络模型其权值分布曲线更平缓。

关键词：卷积神经网络；多模型融合；特征向量；特征提取；权值分布 中图分类号：TP391.4 doi:10.19734/j.issn.1001-3695.2018.05.0506

# Research on multi-model classification algorithm based on weight distribution

Jiang Mengying1,², Lin Xiaozhu1, Ke Yan1, ², Wei Zhanhongl (1.CollegeofInformationEngineeing,BeingIstituteofPetrochemicalTechnology,Beijing2617,China;2.Cllef Information Science&Technology,Beijing University ofChemical Technology,Beijing 10oo29,China)

Abstract:To improve thecorrectrateof imageclassification byconvolutional neural network,a multi-model fusion convolutional neural networkis proposed afterresearch on thenetwork structure.By extracting theoutput feature vectorsofa single modelandthenfusionthem,thenewoutputfeature vectorsareobtained,andthenasingleclasifierissetuptoclassify theimages,andtheaccuracyoftheclassification is improved.Teclasificationaccuracyofsingle model compare withmultimodel fusion,the acuracyofclasificationof multi-model fusion convolutionalneural network isimproved.The weight distributionofthelastlayeroftheconvolutionalneuralnetwork isanalyzed,anditisfoundthattheweightdistributioncurve of the same modelon diferent datasets is similar and the weight distribution curveof the network model with beter classification effect is more gentle.

Key words:convolutional neural network; multi-model fusion; feature vector; feature extraction; weight distribution

# 0 引言

图像的特征提取和分类一直以来都是计算机视觉领域一个基础且重要的研究方向。深度学习是近十余年来人工智能领域取得的重要突破，其卷积神经网络在图像分类上具有显著效果。卷积神经网络（convolutionalneuralnetwork，CNN）能从原始输入图片中挖掘抽象的特征信息，得到的特征表示具有良好的泛化能力。1998年LeCun提出了LeNet-5网络结构[1]标志着CNN的真正面世，但此时的CNN只适用于小图片的识别，对于大规模的数据输入，识别效果较差。直至2012年，krizhevsky等人[2]设计的 AlexNet 卷积神经网络结构在 ImageNet 图像竞赛（ImageNet Large Scale Visual Recognition Challenge,LSVRC）中取得冠军，使CNN得到越来越多的研究者们的重视。2014年，

Szegedy[3]等人增加了CNN的深度，提出了超出20层的CNN结构GoogLeNet模型。Simonyan等人[4]对CNN的深度进行研究，提出了VGGNet模型，通过不断增加 $3 { \times } 3$ 卷积核的卷积层来增加网络的深度。2015年，He等人[5]提出深度为152层的残差网络在LSVRC-15的图像分类竞赛中获得了第一名。随着卷积神经网络结构的不断加深，模型需要海量的数据输入。由于数据集数量有限，训练网络存在梯度弥散和过拟合[6等问题，导致图片分类的准确率下降。对此，研究者们提出了许多解决办法。在网络结构方面，通过改变网络的激活函数[7]、引入dropout 层[8]、迁移学习、并行交叉CNN模型[9]和本文前期工作—跨连接[10]等方法来提高模型对特征的表达能力，进而提高图片分类的准确率。本文首先提出一种多模型融合的卷积神经网络来进行图像分类，将数据集采用迁移学习[1在几个现有的卷积神经网络模型中进行训练，并分别提取训练后模型的最后一层全连接层输出特征向量。将几个模型提取出的特征向量进行融合，使用融合后的特征向量进行Softmax分类，提高分类准确率，并通过实验验证了方法的可行性。然后对单模型和多模型的最后一层全连接层的权值分布曲线进行分析。

# 1多模型融合卷积神经网络

卷积神经网络可以直接输入原始图像，避免了图片复杂的前期预处理，不需要人为地进行特征提取，具有良好的特征表达能力[12]。卷积神经网络主要包括卷积层、下采样层、局部响应归一化（local response normalization，LRN）层[l3]、全连接层和Softmax分类层，其中卷积层和池化层是卷积神经网络的重要组成部分。卷积神经网络的训练过程主要包括前向传播和反向传播两个过程[14]，主要是学习卷积层的卷积核参数和层间连接权重等网络参数。

# 1.1AlexNet模型和VGG 模型

# 1.1.1 AlexNet模型

AlexNet模型解决了之前卷积神经网络只能满足小尺寸图片输入的问题，并证明了CNN在复杂模型下的有效性。相较于传统的卷积神经网络，AlexNet模型在网络模型结构、激活函数以及引入Dropout 层等方面进行了改进。AlexNet 模型增加了网络模型层数，更深的模型结构使其具有更好的特征提取和特征表达能力。局部响应归一化是对特征图相邻区域或者相邻特征图的响应进行归一化操作，起到相邻响应相互抑制的作用。在激活函数方面，摒弃了传统的sigmoid激活函数和tanh激活函数，采用ReLU分段线性激活函数，使得网络能够快速收敛，提供了神经网络的稀疏表达能力并且有效缓解了梯度消失的问题。在全连接层采用Dropout，即在训练过程中，按照一定的概率将部分神经网络单元随机暂时的从网络中丢弃，增强了模型的泛化能力，改善模型过拟合的问题。

# 1.1.2VGGNet模型

VGGNet模型是AlexNet模型发展而来的网络模型，主要展示出网络的深度是算法优良性能的关键部分。VGGNet主要在两方面提出了改进：所有的卷积核大小都使用 $3 { \times } 3$ 尺寸大小;在整个图片和multi-scale上训练和测试图片。VGGNet根据网络层数不同有多种模型，常使用的为VGG-16模型，其结构图如图1所示。

# 1.2多模型融合卷积神经网络

训练卷积神经网络模型时常出现模型过拟合的问题，导致网络模型对图像分类的正确率降低。由于输入图片的数量有限，而网络结构参数多，特征向量在进行分类时全连接层参数容易出现冗余。

对网络模型的全连接层分析发现，改善模型过拟合现象提高分类正确率方法主要分为减少全连接层权值参数和增加输出特征向量两方面。在这基础上，提出一种多模型融合的卷积神经网络模型，对同一训练数据集，提取不同网络模型经过迁移学习后的最后一层全连接层输出特征向量，然后将得到的不同模型的输出特征向量进行融合后，再搭建新的单层分类器进行分类，其模型结构如图2所示。

![](images/b0431f06da6c07755c6727aa7e675d2d9d1283446a25441b86bbe7304db455f3.jpg)  
图1VGG-16 模型结构图

![](images/329d46402741f4c525481012dc4160122258ac786d8c7d2aae283e2e6c397838.jpg)  
Fig.16model   
图2多模型融合结构图  
Fig.2Multi-model fusion structure diagram

将不同网络模型的输出特征向量进行融合后，增加的输出特征向量参与最后分类器的分类，对分类正确率有一定的提高。同时，在获取不同模型的输出特征向量时，仅采用预训练模型微调网络参数后来得到最后一层全连接层网络的输出特征向量融合不同模型的输出特征向量后，只需要进行单层分类器训练分类，一定程度的减少了计算量，对训练时的硬件要求降低。

# 2 CNN最后一层权值分布

通过对卷积神经网络的结构分析，可以发现卷积神经网络的卷积层和池化层的作用旨在提取图像特征，卷积神经网络后几层全连接层的作用则是将提取的特征变换得到一维的输出特征向量。最后一层全连接的输出特征向量的每个单元可以看做训练样本中含有的特征，经过最后一层全连接层后得到一个一维向量（ $( \boldsymbol { 1 } ^ { * } \boldsymbol { n } )$ ，其中 $n$ 为样本数据集的类别数。网络的最后一层全连接层的作用实际是对特征向量进行分类。对最后一层全连接层进行研究，获取网络模型的最后一层权值参数，并对其权值参数分布进行分析。假设输出特征向量单元数为4096个单元，最后一层全连接层过程如图3所示。

图中，全连接层的输入为 $\{ X _ { I } , X _ { 2 } , X _ { 3 } , . . . , X _ { 4 0 9 6 } \}$ ，输出为$\{ a _ { I } , a _ { 2 } , . . . , a _ { n } \}$ ， $n$ 表示分类任务的类别数，w为全连接层的权值参数。那么，全连接层也可以用一个多维方程组表示，如下式所示：

$$
\begin{array} { r l } & { \mathrm { a _ { 1 } } = w _ { 1 1 } * x _ { 1 } + { w _ { 1 2 } } ^ { * } x _ { 2 } + \ldots + w _ { 1 , 4 0 9 6 } * x _ { 4 0 9 6 } + b _ { 1 } } \\ & { \mathrm { a _ { 2 } } = w _ { 2 1 } * x _ { 1 } + w _ { 2 2 } * x _ { 2 } + \ldots + w _ { 2 , 4 0 9 6 } * x _ { 4 0 9 6 } + b _ { 2 } } \\ & { \mathrm { a _ { 3 } } = w _ { 3 1 } * x _ { 1 } + w _ { 3 2 } * x _ { 2 } + \ldots + w _ { 3 , 4 0 9 6 } * x _ { 4 0 9 6 } + b _ { 3 } } \\ & { \cdots } \\ & { \mathrm { a _ { \rho } } = w _ { \mathrm { { _ { - } 1 } } } * x _ { 1 } + w _ { \mathrm { { _ { - } 2 } } } * x _ { \mathrm { { + } } \mathrm { { + } } \ldots } + w _ { \mathrm { { _ { - } 4 0 0 6 } } } * x _ { \mathrm { { 4 0 0 6 } } } + b . } \end{array}
$$

通过公式可知，每一种分类类别都是由4096个特征按照一定的权值比重组成的。在进行分类时，通过分析可知，全连接层输入与权值相乘得到的净激活再经过ReLU激活函数，净激活小于等于零的值经过ReLU激活函数后被置零，只保留大于零的净激活值。那么实际上，在最后一层全连接层进行分类时，只有部分的输出特征决定着分类类别。所以，最后一层全连接层的权值分布情况很大程度上决定着模型分类的效果。

![](images/b618d237c1be55fedc126cda2518ba036745ad8263cd8d5b1cddccc38a77e61d.jpg)  
图3全连接层结构图

# 3 实验分析

# 3.1实验数据集

本实验分别采用Caltech-101数据集[15]和2017年百度图像竞赛数据集进行实验。Caltech-101数据集是由李飞飞等人于2003年在加州理工学院创建的数字图像集。Caltech-101数据集共 9146张图片，包括101类前景图片和一个背景类。每类有30\~800 张图片，大部分图片有50张。图4为Caltech-101数据集的一部分示例图片。

![](images/b77b58bf06c08858caa05bb7eaec70a7fd85f2968342dd2e71709690e88274a7.jpg)  
Fig.3Full connect layer structure diagram   
图4Caltech-101数据集的部分图片  
Fig.4Partial pictures of Caltech-1O1 dataset

2017百度图像竞赛数据集为100类不同品种的狗狗图片，数据集如图5所示。其中，训练集数量为8153张，测试集数量为10624张，每类有30\~200张。

![](images/f3032432ff037211d6ad58831bc3d84607a3c95b847e9046193793a993cb82c9.jpg)  
图52017百度图像竞赛数据集部分图片  
Fig.5Partial pictures of 2O17 Baidu image competition dataset

# 3.2 实验结果及分析

# 3.2.1多模型融合

本文将Caltech-101数据集中每类随机选取出30幅图像作为训练样本，剩余部分作为测试样本。将2017百度图像竞赛数据集训练集8153张图片进行训练，测试集10624张图片进行测试。首先对图像进行预处理，将数据集所有图片缩放为$2 5 6 ^ { * } 2 5 6$ 像素大小的图像块。由于从ImageNet数据集上学习得到的底层滤波器往往描述了各种不同的局部边缘和纹理信息，这些滤波器对一般的图像有较好的普适性。在不同模型提取最后一层全连接层输出向量时，均采用各个模型在ImageNet数据集训练过后的参数作为初始权值参数，然后使用输入数据集对网络模型进行微调。使用CaffeNet模型进行微调提取输出特征向量时，对输入图像进行处理得到 $2 2 7 ^ { * } 2 2 7$ 像素的图像，然后对所有图像进行减均值处理。CaffeNet模型与AlexNet结构模型基本相似，区别在于LRN层的位置不同。AlexNet 结构中，LRN层是在池化层之前，而CaffeNet结构中，LRN层则在池化层之后。使用VGG-16网络模型进行微调提取输出向量时，则截取 $2 2 4 ^ { * } 2 2 4$ 像素的图像输入。初始学习率为0.0001，每迭代1000次学习率减少10倍，训练过程总迭代次数为8000次。将两个网络模型融合后，得到输出向量为8192个单元，再进行单层的Softmax分类器分类。

使用Caltech-101数据集在CaffeNet网络模型提取输出特征向量进行单层分类器训练、在VGG-16网络模型提取输出特征向量进行单层分类器训练、将两个模型的输出特征向量融合后进行单层分类器训练，其测试集结果如表1所示。

表1不同模型在Caltech-101数据集上的分类正确率  

<html><body><table><tr><td>网络模型</td><td>正确率(%)</td></tr><tr><td>CaffeNet模型</td><td>79.02</td></tr><tr><td>VGGNet 模型</td><td>82.25</td></tr><tr><td>多模型融合</td><td>83.89</td></tr></table></body></html>

将2017百度图像竞赛数据集在CaffeNet 模型提取输出特征向量进行单层分类器训练、在VGG-16网络模型提取输出特征向量进行单层分类器训练以及将两个模型的输出特征向量融合后进行单层分类器训练，其测试集结果如表2所示。

表2不同模型在2017百度图像竞赛数据集上的分类正确率  

<html><body><table><tr><td>网络模型</td><td>正确率(%)</td></tr><tr><td>CaffeNet模型</td><td>39.05</td></tr><tr><td>VGGNet模型</td><td>42.88</td></tr><tr><td>多模型融合</td><td>45.67</td></tr></table></body></html>

对两个数据集分别进行多个模型训练后，测试结果表明：同一训练样本数据集，VGG-16模型训练后分类正确率高于CaffeNet模型，多模型融合后，分类正确率均高于单个模型训练的分类准确率。

# 3.2.2最后一层全连接层权值分析

通过上一节实验可以得到已经训练好的不同卷积神经网络模型，分别提取其最后一层全连接层的权值，将它们按照大小顺序绘制出来。其中，CaffeNet 模型在Caltech-101数据集与2017百度图像竞赛数据集上训练后最后一层全连接层权值分布如图6所示。

图6中，横坐标为最后一层全连接层特征向量的维度，一般情况下输出向量的单元数为4096，横坐标范围为（0，4500)。纵坐标为最后一层全连接层的权值参数值，其范围为（-0.06，0.08)。对比同一模型在不同数据集上的最后一层权值分布曲线，可以得到，同一模型在不同数据集上的权值分布曲线相似。

分别绘制CaffeNet模型和VGG-16模型在Caltech-101数据集上最后一层全连接层权值分布曲线，如图7所示。通过分析不同模型在同一数据集上的最后一层权值分布，可以得到，VGG-16模型相较于CaffeNet模型，其最后一层全连接层的权值参数分布更平缓。

![](images/77e3a1e39349b9577cc0da0a50a16a248083cf4cbcdd7208a1005713db1b8f01.jpg)  
图6CaffeNet模型在不同数据集上的最后一层全连接层权值分布图

![](images/3493d5bb63bfc980f9fbc76769c52b27f41fadb2858cba2c7fe3bccdd2ac87eb.jpg)  
Fig.6The last layer full connected weight distribution on diferent data sets on CaffeNet model   
图7不同模型在Caltech-101数据集上的最后一层全连接层权值分布曲线图  
3.7The last layer full connect layer weight distribution of different models on Caltech-1Ol datas

对于多模型融合卷积神经网络模型则同样提取其分别在Caltech-101数据集和2017百度数据集上训练后的最后一层权值分布曲线，如图8所示。图中横坐标为最后一层全连接层特征向量的维度，由于多模型融合了两个单模型的输出向量，所以其多模型的特征向量维度为8192，横坐标范围为(0，10000)。纵坐标为最后一层全连接层的权值参数值，其取值范围为（-0.2，

0.1)。由于2017年百度图像竞赛数据集相较于Caltech-101数据集来说，其数据未经过清洗，图片质量不好，所以分类正确率低。通过对比多模型融合卷积神经网络模型在两个数据集上的权值分布曲线，可以发现多模型融合后权值分布取决于数据集的质量，曲线总体相似，当数据集质量越好，分类曲线越平缓。

![](images/44d664cb4a49f774072e444a215ba737a54a768095905a3d2017b7a42f5fae66.jpg)  
图8融合模型在不同数据集上的最后一层全连接层权值分布曲线图  
Fig.8The last layer full link layer weight distribution of fusion models on different datasets

# 4 结束语

卷积神经网络的特点是能够自动地、隐式地学习特征，不需要人为地定义特征。当有足够多的样本进行训练时，网络可以学习到很好的特征来进行分类。由于网络权值参数过多，训练样本少，网络模型易出现过拟合问题，分类正确率降低。网络模型结构复杂，计算量大，硬件设施要求较高。本文首先提出多模型融合的卷积神经网络模型，其分类准确率较于单个模型有一定的提高。由于多模型融合后，只需进行单层网络训练，对于硬件设施要求也降低，计算速度也得到提高。然后对卷积神经网络的最后一层全连接层进行分析，发现同一模型在不同数据集上最后一层全连接层权值分布曲线相似，不同模型在相同数据集上的最后一层全连接层权值分布曲线有差异。多模型融合后权值分布则与数据集的质量有关，质量越好分类曲线越平缓，而且一致性较好。

# 参考文献：

[1]Lécun Y,Bottou L,Bengio Y,et al.Gradient-based learning applied to document recognition [J].Proceedings of the IEEE,1998,86 (11): 2278- 2324.   
[2]Krizhevsky A, Sutskever I, Hinton G E.ImageNet classification with deep convolutional neural networks [C]//Proc of International Conference on Neural Information Processing Systems.Curran Associates Inc.2O12:1097- 1105.   
[3]Szegedy C,Liu Wei, Jia Yangqing,et al. Going deper with convolutions [C]// Computer Vision and Pattern Recognition.2015:1-9.   
[4]Simonyan K, Zisserman A.Very deep convolutional networks for large-scale image recognition [J].Computer Science,2014.   
[5]He Kaiming, Zhang Xiangyu,Ren Shaoqing,et al. Deep Residual Learning for Image Recognition [C]// Computer Vision and Pattern Recognition.2016:

770-778.

[6]Sermanet P,Eigen D,Zhang Xiang,et al. OverFeat: Integrated recognition, localization and detection using convolutional networks [J].Eprint Arxiv, 2013.   
[7]Goodfellow IJ,Wardefarley D,Mirza M,et al.Maxout networks [J]. Computer Science,2013: 1319-1327.   
[8]Srivastava N, Hinton G,Krizhevsky A,et al.Dropout: a simple way to prevent neural networks from overfitting [J]. Journal of Machine Learning Research,2014,15(1):1929-1958.   
[9]汤鹏杰，王瀚漓，左凌轩．并行交叉的深度卷积神经网络模型[J].中 国图象图形学报,2016,21(3):339-347.(Tang Pengji,Wang Hanli, Zuo Lingxuan．Parallel cross deep convolution neural networks model [J]. Journal of Image and Graphics,2016,21(3): 339-347.)   
[10]李勇，林小竹，蒋梦莹．基于跨连接 LeNet-5 网络的面部表情识别[J]. 自动化学报,2018,44(1):176-182.(LiYong,Lin Xiaozhu,Jiang Mengying. Facial expression recognition with cross-connect LeNet-5 network [J].Acta Automatica Sinica,2018,44 (1): 176-182)   
[11] Pan Sinno Jalin,Yang Qiang.A Survey on Transfer Learning[J]. IEEE Trans on Knowledge & Data Engineering,2010,22(10):1345-1359.   
[12]常亮，邓小明，周明全，等．图像理解中的卷积神经网络[J]．自动化 学报，2016,42 (9):1300-1312.(Chang Liang,Deng Xiaoming,Zhou Mingquan,et al. Convolutional neural networks in image understanding [J]. Acta Automatica Sinica, 2016,42 (9): 1300-1312)   
[13] Fleming A D,Philip S,Goatman K A,et al. Automated microaneurysm detection using local contrast normalization and local vessel detection [J]. IEEE Trans Med Imaging,2006,25 (9): 1223-32.   
[14] Bouvrie J.Notes on Convolutional Neural Networks [J].Neural Nets,2006.   
[15] Borji A,Sihite D N, Itti L. Salient Object Detection: A Benchmark [M]// Computer Vision. Berlin: Springer,2012: 414-429.