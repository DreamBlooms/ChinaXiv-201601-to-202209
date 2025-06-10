# 基于距离限定优化的人脸识别

周胜阳，邹华，肖春霞(武汉大学 计算机学院，武汉 430072)

摘要：针对现有人脸识别方法对人脸角度、表情、姿态等因素较为敏感且准确率低的问题，提出了一种基于距离限定优化算法的人脸识别模型。该模型对人脸识别方法的改进有两点：a)利用LBP算子提取人脸图像纹理谱特征图，然后与原始人脸图像的R、G、B通道进行融合，将融合后的图像矩阵作为神经网络的输入，丰富了人脸的纹理特征；b)对误差函数进行改进，使用阈值和边界值约束特征向量的距离，对模型构建新的优化目标，使得相同对象的人脸图像在特征空间中具有较小的欧氏距离，不同对象的人脸图像在特征空间中具有较大的欧氏距离。通过在非限制场景下的LFW人脸库上进行实验，表明该模型准确率分别达到 $9 9 . 1 5 \%$ ，能有效地提高人脸识别准确率，具有很好的鲁棒性。

关键词：人脸识别；特征提取；局部二值模式；二元误差函数；残差神经网络 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.10.1016

# Face recognition based on limit distance optimization

Zhou Shengyang, Zou Hua, Xiao Chunxia (SchoolofComputer,Wuhan University,Wuhan430072,China)

Abstract: Giventhesensitivityofhumanfaceangle,expressionandatitudeas wellas thelowrecognition precision,thispaper presented anew face recognition algorithm based on distance optimization method.There were two revised points in the proposed method: a)The algorithm used the LBPoperator to extract the texture mapof the face imageand then converged it withtheR,GandBchannelsoftheoriginal image,thenthe neuralnetworkcouldtakethefused image matrix asinput,which enrichedthe human face texture features;b)Inthe procesingof training,itreconstructed thelossfunctionto improve the performance,made useofthe thresoldand margin toconstrain thedistanceofthe feature vector,andbuiltanewoptimization target forthe model,whichcouldlimitthefacesoftesamepersonhavesmalleuclideandistancesandfacesofdistinctpeople hav largedistances.Experiments ontheunconstrained scenesoftheLFWface databaseshowthattheaccuracyofthemodelis $9 9 . 1 5 \%$ respectively,indict the model can improve the accuracy of face recognition with strong robustness.

Key Words: face recognition; feature extraction; local binary pattern; binary lossfunction; residual network

# 0 引言

随着社会的发展，已经进入数字和网络时代，信息的安全性和保密性越来越受到人们的重视，传统的身份认证方法难以满足人们的要求。21世纪以来，大量新型的生物特征识别技术涌现，包括指纹识别、虹膜识别、DNA识别等。人脸识别技术由于具有非接触性、易采集和可靠性高的特点，在司法、安保等领域得到了广泛的应用。如何提高人脸识别的效率和准确率成为一个重要的研究课题。

近年来，深度学习为许多计算机视觉问题带来了突破性的进展，伴随着大数据时代的到来，卷积神经网络(CNN)也为人脸识别提供了新思路。在实际应用中，人脸识别系统要求能对不同表情、角度、光照等非限制场景下的人脸图像进行正确识别，判断是否为相同个体。传统人脸识别方法在适用性和准确率上存在局限性，而基于深度学习的方法由于其强大的特征学习能力得到了广泛的应用，在很多人脸数据库上的识别率甚至超过了人眼识别水平。

代表性的深度学习人脸识别方法有ConvNet-RBM[1]、DeepFace[2]等，其主要思想是使用大量的具有个体标签的人脸图像样本对神经网络模型进行softmax训练，然后手工选取神经网络中间层的特征作为代表人脸图像的特征向量，最后度量特征向量的关系来进行人脸识别。虽然这些方法在精度上有了很大的提高，但是该类方法具有三个明显的缺陷：a)中间层特征不具有直接性[3]，训练过程没有显式地对中间层特征进行调整，因此新图像提取的特征向量可能不具有代表性，因而限制了算法的准确性；b)特征向量的度量方法需要人为进行选择，具有不确定性；c当在大型数据库上训练神经网络模型时，softmax类别会相应增加，为了保持特征的完整性，中间层神经单元个数也要随之增加，导致最后提取的特征向量维度很高，增加了计算成本。

为了解决以上问题，本文提出一种基于距离限定优化的人脸识别模型。该模型不使用softmax中间层结构，而是直接使用残差神经网络模型将人脸图像映射为128维特征向量，计算特征向量间的欧式距离，进而比较人脸图像的相似度。如果两个特征向量的欧式距离小于给定的阈值，则判断两幅人脸图像为相同对象，反之则为不同对象。与上述深度学习人脸识别方法相比，该方法的网络结构不受数据集影响，也不需要人为地统计选择适合的中间层和特征度量方法。除此之外，本文根据LBP人脸识别方法，结合神经网络的特点，提出了将LBP人脸特征图和原始人脸图像融合训练的方法。LBP人脸特征图具有光照不变性的优点，且可以丰富人脸图像的几何和纹理特征。使用融合后的图像作为神经网络的输入能增强网络模型泛化能力，加快网络的训练速度，尤其在数据量相对较小的情况下更能体现。实验结果也表明，本文方法可以进一步提高人脸识别的准确率，对于非限制场景下的人脸图像也具有很好的鲁棒性。

# 1 相关工作

最早的可投入使用的人脸识别算法是主成份分析法(principlecomponent analysis，PCA)[4]，也叫特征脸方法。该方法首先利用若干幅样本图片构造一个低维的特征空间，并将测试图片投影到该空间中，计算其特征向量，最后使用距离度量函数进行分类。梯度直方图方法(histrogramoforiented gradient,HOG)[56]计算图像在水平方向和竖直方向的梯度，并将二维的梯度信息转换为若干无向的直方图通道信息，统计每个像素点在各个方向的直方图特征，参数化并级联获得整幅图像的HOG特征向量，最后进行人脸比对。文献[7]提出一种基于二维核主成分分析的拉普拉斯特征映射算法，极大地提高了人脸识别准确率。类似方法还有局部二值模式分类方法(localbinarypatternLBP)[8]、线性判别分析法(linear discriminant analysis，LDA)[9]以及多特征融合分类的方法[10]。这些方法存在共同的缺点，即都需要人工设计特征提取方法，在设计参数时往往需要进行反复的实验，并且难以获取到人脸图像高度非线性的特征，对人脸表情、姿态等信息较为敏感，识别的准确率会受到限制。一般来说，传统的人脸识别算法需要一些图像预处理方法，如阴影消除[11,12]和纹理上采样[13]，以增强人脸的特征提取效果。

近年来，深度学习在图像分类和特征提取方面取得了很好的发展，研究者将深度学习的方法引入到人脸识别上，取得了很好的效果。DeepFace[2]是由FaceBook公司设计的人脸识别模型，该模型使用softmax分类方法按照对象将人脸图像分为4030个不同类，然后取神经网络模型倒数第二个全连接层的特征(4096维)作为人脸的特征向量，主要的优势在于使用了3D模型和局部卷积层进行人脸矫正以及局部特征提取，网络模型训练完成后，计算特征向量间的加权平方距离或欧氏距离作为人脸识别的判断依据，该方法在LFW人脸库上达到 $9 7 . 3 5 \%$ 的准确率。

DeepID[14]模型将人脸图像切分为25个区域块，然后提取多尺度的人脸特征向量，最后使用级联贝叶斯分类器进行人脸识别。DeepID $2 ^ { [ 1 5 ] }$ 对 DeepID进行拓展，使用识别信号和验证信号联合的方式训练网络模型。其中，识别信号为普通的softmax分类信号，用来学习不同对象间的特征，增加其特征向量间的距离；验证信号为图像对分类信号，用来学习相同对象间的特征，缩小其特征向量间的距离。然后训练一个联合贝叶斯分类器对特征向量进行分类。DeepID2在LFW人脸库上达到了 $9 9 . 1 5 \%$ 的准确率。

相比于DeepFace 和FaceId模型，FaceNet[3]并没有使用传统的softmax方式进行学习，而是使用一种三元组损失误差函数(tripletloss)来实现从图像到特征向量的编码，然后基于编码计算图像对之间的误差。该模型使用图像对来训练网络参数，规定同一个人的两幅图像为正样本，不同人的两幅图像为负样本，FaceNet的训练目标是使得任意正样本的图像对之间的欧氏距离与阈值之和小于负样本图像对之间的欧式距离。训练目标表示为

$$
\begin{array} { r } { \left\| x _ { a } - x _ { p } \right\| _ { 2 } ^ { 2 } + \alpha < \left\| x _ { a } - x _ { n } \right\| _ { 2 } ^ { 2 } } \end{array}
$$

其中： $a$ 和 $p$ 表示两幅图像属于同一个人，为正样本； $a$ 和 $n$ 表示两幅图像属于不同人，为负样本， $\alpha$ 代表阈值； $x _ { a }$ 和 $\boldsymbol { x } _ { p }$ 表示两个正样本图像的特征向量， $x _ { a }$ 和 $x _ { n }$ 表示两个负样本图像的特征向量。神经网络的训练过程为：取任意一幅人脸图像，随机选择一幅对应的正样本图像和负样本图像，如果提取的特征向量之间满足训练目标，则不计算误差；反之，计算误差并使用反向梯度传播算法更新神经网络参数，直到满足所有的训练样本。模型训练完成后，选取适当的阈值 $\tau$ 。对任意两幅图像，使用FaceNet模型分别提取特征向量并比较之间欧氏距离与 $\tau$ 的关系，如果大于 $\tau$ ，表示两幅图像为不同对象；反之，则为相同对象。FaceNet模型的网络结构独立于数据集，且训练过程直接对特征向量进行优化，具有较好的解释性和直观性；缺点在于三元组训练方式对坏样本敏感，且训练完成后需要人为统计选择合适的阈值，具有不确定性。

# 2 本文算法

为了进一步提高人脸识别模型的准确率，本文提出了一种距离限定优化的人脸识别模型，并对图像预处理和训练算法进行改进，主要有LBP特征图融合算法和二元误差优化算法两个方面。

# 2.1LBP特征图融合算法

LBP特征是一种在灰度范围内非常有效的纹理谱描述符，具有分类能力强、光照不变性的特点，能较好地描述图像的整体和局部特征。因此，LBP特征被广泛应用在模式识别领域，

Ahonen等人[8]成功地将其应用在人脸识别。

LBP算子是一种基于局部模式的纹理算子，基本思想是在半径为 $R$ 的圆形邻域内，选取与中心像素点距离相等的 $P$ 个采样点 $g _ { i } ( i = 0 , 1 , \cdots , P - 1 )$ ，并与中心像素点 $g _ { c }$ 的像素值进行比较，用布尔函数来表示结果。纹理特征的LBP值计算公式为

$$
\begin{array} { l } { { \displaystyle { \bf L B P } _ { P , R } = \sum _ { i = 0 } ^ { P - 1 } s ( g _ { i } - g _ { c } ) 2 ^ { i } , } } \\ { { \displaystyle s ( x ) = \left\{ \begin{array} { l l } { { 1 , } } & { { x \geq 0 } } \\ { { 0 , } } & { { \mathrm { o t h e r w i s e } } } \end{array} \right. ; } } \end{array}
$$

用半径为 $R$ 、采样点为 $P$ 来表示采样方式，不同邻域的结果如图1所示。

![](images/b73c1014cc245bc63addcb07d9c8b50579f830707137eebcf033b0a3d9beb10d.jpg)  
图1几种LBP算子

本文采用 $R = 2$ $P = 8$ 的LBP算子提取图像的纹理特征，LBP算子提取图像邻域特征的运算过程为如图2所示。

融合后的图像具有更直观的纹理信息，因而神经网络模型会具有更快的收敛速度和更高的准确率。人脸图像的LBP特征图和融合过程如图3所示。

![](images/30a6898e6e6cd2adb8af365dc148415de7a9ab7ddccb889b22466733b55c4faf.jpg)  
图3LBP特征提取与融合

# 2.2Resnet网络模型结构

本文使用残差神经网络(residualneuralnetwork，Resnet)作为人脸的特征提取器，将人脸图像映射为特征向量。残差神经网络是一种改进的卷积神经网络，最初由He等人[17]提出，并应用在ImageNet分类问题上，获得了当时最高分类准确率。Resnet的优点在于对神经网络中间层使用跨层连接的方式，强化了特征信号，降低了深层网络训练过程中出现梯度爆炸或梯度消失的风险，从而提高了模型分类的准确率。类似于Resnet-34结构模型，综合考虑准确率和效率等因素，本文设计的Resnet神经网络模型一共有20层网络结构，详细参数如表1所示。

![](images/13df221c9b458f6194a8eb5969f542d3a3d4b10a1f73cc38ecead66f81ab1022.jpg)  
图2基本LBP算子运算过程

表1本文ResNet 结构参数  

<html><body><table><tr><td>网络层</td><td>参数</td></tr><tr><td>C1</td><td>32×7×7×2×2</td></tr><tr><td>P2</td><td>3×3×2×2</td></tr><tr><td>RB3</td><td>3×[32×3×3×1×1]</td></tr><tr><td>P4</td><td>2×2×2×2</td></tr><tr><td>RB5</td><td>3×[64×3×3×1×1]</td></tr><tr><td>P6</td><td>2×2×2×2</td></tr><tr><td>RB7</td><td>3×[128×3×3×1×1]</td></tr><tr><td>P8</td><td>2×2×2×2</td></tr><tr><td>RB9</td><td>3×[256×3×3×1×1]</td></tr><tr><td>P10</td><td>2×2×2×2</td></tr><tr><td>F11</td><td>NumX128</td></tr></table></body></html>

LBP特征图包含了原始人脸图像丰富的纹理信息，传统的LBP人脸识别方法一般将图像局部的LBP特征串联起来使用直方图来表示，本文不使用该类方法，而是直接将LBP特征图与原始人脸图像作通道融合。Xi等人[16证明了将LBP特征图作为神经网络的输入可以很好地获取人脸的特征表达，将LBP特征转换为更稀疏有效的特征。LBP特征图具有简单直观的特征表示方式，而原始人脸图像具有更丰富的特征信息。本文借鉴文献[16]的思想，使用LBP特征图为人脸图像构建条件约束，其中，C表示卷积层；P表示池化层；RB表示残差连接块，每个残差块由3个卷积层和1个池化层连接组成；F表示全连接层。整个神经网络模型结构如图4所示。

![](images/1aebcee3813ce1d66655fe72386e18075d99bd50e08d9095b026d165b4016e0c.jpg)  
图4本文模型结构

# 2.3Resnet模型误差函数与训练过程

Resnet神经网络模型可以作为一种黑盒子来使用，其主要作用是提取人脸图像具有代表性的特征向量，将人脸图像映射到特征空间中。在训练的初始阶段，每个特征向量表示为一个特征点，所有的特征点以高斯分布的形式存在于特征空间中。本节的重点在于设计一种训练规则，使得在训练的过程中，同类的特征点能够逐渐聚合，而不同类的特征点能够逐渐分离，从而对特征点进行分类识别。

本文提出一种改进的二元组误差优化算法的方法对Resnet神经网络进行训练。先对人脸图像作如下定义：选取两幅人脸图像，当两幅图像代表同一个对象时，图像对为正样本；当两幅图像代表不同对象时，图像对为负样本。训练的目标是：对于所有正样本，其特征向量应该具有较小的欧氏距离；对于所有负样本，其特征向量应该具有较大的欧氏距离。

根据训练目标构造Resnet模型的目标函数，设定一个阈值$\tau$ 和边界值 $m ( \tau > m )$ ，则对于所有正样本的图像对，其特征向量的欧氏距离应该满足

$$
\left\| x _ { a } - x _ { p } \right\| _ { 2 } ^ { 2 } < \tau - m
$$

其中： $x _ { a }$ 和 $\boldsymbol { x } _ { p }$ 表示正样本的两幅图像的特征向量。对于所有负样本的图像对，其特征向量的欧氏距离应该满足

$$
\left\| x _ { a } - x _ { n } \right\| _ { 2 } ^ { 2 } > \tau + m
$$

其中： $x _ { a }$ 和 $x _ { n }$ 表示负样本的两幅图像的特征向量。由此一来，图像对可以根据特征向量欧氏距离和阈值 $\tau$ 的关系来进行分类，如果小于 $\tau$ ，则表示样本为正样本；反之，则为负样本。另外，边界值 $m$ 的作用主要是为了在训练阶段更直观地划分正样本和负样本，如图5所示，使用边界值m可以进一步缩小正样本的距离，扩大负样本的距离，避免样本的距离与阈值 $\tau$ 太过接近，从而出现危险样本。

![](images/35bde2b8e9a623b916a6cfb152969bbc654d1bb355b5f923d473b5b7d63d1389.jpg)  
图5边界值 $m$ 对样本分类的影响

对于正样本，一些方法直接最小化其欧氏距离，如MSE人脸识别模型，其目标函数为

$$
\mathrm { a r g } \operatorname* { m i n } \{ \left\| x _ { a } - x _ { p } \right\| _ { 2 } ^ { 2 } \}
$$

该方法的目标是最小化正样本的L2距离，在训练过程中正样本代表的特征点会越来越接近。本文不使用这种方法，主要是考虑下面两个原因：

a)对于非限制场景下的正样本，图像在光照、表情、背景等方面有明显的差异，表现为较大的类内差距，因此提取的特征向量也应该有少量的差异性，而不是简单地将其距离优化为零。

b)在大型数据库中经常出现将负样本标记为正样本的情况，使用最小化特征向量距离的方法容易受不好数据的主导。

因此，本文使用距离限制的方法，所有的正样本只需要小于一个距离阈值即可，而不需要无限接近，从而提高了系统的鲁棒性。另外，将本文改进的二元组优化目标函数和FaceNet[3]模型的优化目标函数进行对比，改变本文二元组优化的目标函数形式，可以推导出以下关系：

$$
\begin{array} { r } { \left\| x _ { a } - x _ { p } \right\| _ { 2 } ^ { 2 } + \tau + m < \left\| x _ { a } - x _ { n } \right\| _ { 2 } ^ { 2 } + \tau - m } \end{array}
$$

$$
\left\| x _ { a } - x _ { p } \right\| _ { 2 } ^ { 2 } + 2 m < \left\| x _ { a } - x _ { n } \right\| _ { 2 } ^ { 2 }
$$

与FaceNet的目标函数(式(1))做比较，可以发现，当设置$2 m = \alpha$ 时，两个目标函数一致，表示本文的二元组的优化目标函数可以推导出FaceNet三元组优化目标函数，也就是说，本文二元组优化自标隐式包含FaceNet三元组优化目标。另外，FaceNet模型训练完成之后，需要对测试样本进行统计并设置距离阈值，从而对新的样本进行分类，而本文并不需要重新设置新的阈值，直接使用训练过程中的阈值即可，具有更直观的特点。

根据优化目标，可以对Resnet模型构建误差函数，设定Y作为图像对的样本标签， $Y { = } 1$ 表示图像为正样本， $Y { = } { \mathrm { - } } 1$ 表示图像为负样本，则本模型的误差函数表示为

$$
\ell = \operatorname* { m a x } \{ 0 , Y ( \left\| x _ { 1 } - x _ { 2 } \right\| _ { 2 } ^ { 2 } - \tau ) + m \}
$$

$$
\big \| x _ { 1 } - x _ { 2 } \big \| _ { 2 } ^ { 2 } = s q r t \sum _ { i = 1 } ^ { D } \{ x _ { 1 } ( i ) - x _ { 2 } ( i ) \} ^ { 2 }
$$

误差函数表示，本模型的训练数据为图像对，当两个图像的特征向量之间的欧氏距离满足给定的优化目标时，则不计算误差(误差为0)，否则将按照SGD优化方法更新模型参数。图6所示为误差函数为特征点的训练结果。

![](images/8b0f9313d211b5fe3d6934b17215d677e988ffb7b25fb43bea5d95d323d7ecc5.jpg)  
图6特征点的优化结果

模型训练完成后，可以使用ResNet模型对新的图像进行特征提取和分类，判断图像对为正样本或负样本。在对新的图像进行验证时，舍弃边界值 $m$ ，保留阈值 $\tau$ 作为欧氏距离的度量标准，表达式如下：

$$
Y = \left\{ { \begin{array} { l l } { 1 } & { \left\| x _ { 1 } - x _ { 2 } \right\| _ { 2 } ^ { 2 } < \tau } \\ { - 1 } & { \left\| x _ { 1 } - x _ { 2 } \right\| _ { 2 } ^ { 2 } > \tau } \end{array} } \right.
$$

# 3 实验结果与分析

为了验证本文人脸识别模型的有效性，以及研究模型参数对识别率的影响，将本文模型和传统 PCA+LDA、CS-LBP[16]、Fisher-Vector 模型以及基于深度学习的ConvNet-RBM[1]、DeepId[14]、FaceNet[]模型进行对比。实验环境为硬件Inteli52.4GHz CPU, $2 . 4 ~ \mathrm { G H z }$ ，4GB内存，软件环境为64位Ubuntu 操作系统。算法主要用 $\mathrm { C } { + } { + }$ 编程实现，实验过程在Facescrube[19]和 LFW[20]人脸图像库上进行，其中 Facescrube 人脸库用于对模型进行调参，LFW人脸库用于与其他模型进行对比。

# 3.1FaceScrube 实验结果与分析

FaceScrube[19]人脸库包含530个对象的106863幅人脸图像，所有图像均为非限制场景下采集的包括光照、表情、方向、尺寸大小等变化。Facescrube人脸库主要用于验证模型的有效性，保持训练集和测试集不交叉的原则，选择450个对象的图像作为训练集，50个对象的图像作为验证集，30个对象的图像作为测试集，则有约90000个训练图像、10000幅验证图像和$6 0 0 0$ 幅测试图像。使用2.3节所述的神经网络训练方法优化人脸识别模型，将图像组合成图像对进行训练和测试，则各类样本数量远大于实际图像数量，其中训练集约有 $1 \times 1 0 ^ { 7 }$ 对正样本和 $4 \times 1 0 ^ { 9 }$ 对负样本。

# 3.1.1超参数的选择

本文人脸识别模型有两个超参数，分别是用于限制距离的阈值 $\tau$ 和边界值 $m$ 。其中，边界值 $m$ 主要用于训练阶段，阈值 $\tau$ 用于训练和测试的全过程。阈值 $\tau$ 和边界值 $m$ 的选取将决定人脸识别模型的准确率，对于任意正样本，需要使得特征向量之间的欧氏距离小于阈值 $\tau$ 与边界值 $m$ 之差；对于任意负样本，需要使得特征向量之间的欧氏距离大于阈值 $\tau$ 与边界值m之和。一方面，人脸特征具有一定的稀疏性（较小的类间差距)，因此合理的阈值 $\tau$ 不应该过大；另一方面，边界值 $m$ 的作用是为了进一步减小正样本的距离和增加负样本的距离，如果 $m$ 值与 $\tau$ 值大小接近，会使得所有正样本之间的距离过小，这与人脸的特性（较大的类内差距）是不符合的，因此也会降低模型的准确率。综合考虑以上两种因素，本文设置不同的阈值 $\tau$ 和边界值 $m$ 组合，其中 $0 . 4 \leq \tau \leq 2 . 0$ ， $0 . 0 5 \leq m < \tau$ ，并在Facescrube人脸库上进行训练测试，最后对准确率进行排序。实验发现，当选择阈值 $\tau$ 在（0.7，1.0）之间时，模型具有较高的准确率。准确率随阈值和边界值变化的关系如图7所示。

从图中可以看出，随着阈值 $\tau$ 的增加，模型的准确率呈现先增加后减小的趋势，并在 $\scriptstyle \tau = 0 . 8$ 时达到最高。对于固定的阈值，边界值过小或过大都会降低模型的准确率，当边界值过大时，会将正样本的特征向量压缩在很小的距离内，违背了人脸较大类内差距的特性；当边界值过小时，无法进一步的分离正样本和负样本，可能导致两个不同对象的特征向量在特征空间中具有较小的距离（危险样本)。数据表明，当选取 $\scriptstyle \tau = 0 . 8$ ，$m = 0 . 2$ 时，模型具有最高的准确率，达到 $9 6 . 6 8 \%$ ，表明本文模型在FaceScrube数据库有很好的表现。

![](images/1552f7496b8106029c1e169ac8c10493028438bced964c42279eeafbee0b11c3.jpg)  
图7模型准确率变化曲线

# 3.1.2LBP特征图融合

本文在图像预处理阶段使用LBP特征图融合方法为人脸图像构建条件约束，丰富人脸的纹理信息。本节将在Facescrube人脸库上证明LBP特征图融合算法的有效性。

设置ResFace和LBP-ResFace两个模型，其中ResFace模型不使用LBP特征图融合算法，直接将原始人脸图像作为神经网络的输入。模型的阈值 $\tau$ 和边界值m均设置为0.8和0.2。两个模型的准确率随模型的迭代次数变化曲线如图8所示。

![](images/2de831c095353631495bc9894cbf314d07d0cfa30f5d2b6a94cc09b6a758ce3d.jpg)  
图8模型准确率对比

分析图8数据可知，使用LBP特征图融合方法的人脸识别模型准确率更高，在相同的训练样本和超参数下，ResFace 模型最终的准确率为 $9 5 . 5 5 \%$ ，LBP-ResFace 模型最终的准确率为$9 6 . 6 8 \%$ ，准确率提高了 $1 . 1 3 \%$ 。另外，LBP-ResFace 模型在训练的开始阶段（迭代1000次）准确率高出 $2 . 4 8 \%$ ，表明使用LBP特征图融合方法的模型具有更快的优化速度，从而证明了算法的有效性。

使用LBP特征图融合算法可以丰富原始人脸图像的信息，将图像的纹理特征更直观地表达出来，加快神经网络的收敛速度。在人脸的特征提取过程中，不同的人脸区域应该具有不同的卷积权值，使用LBP特征图融合算法可以为原始人脸图像添加这类约束。另外，LBP特征图具有光照不变的特点，可以很好地消除非限制场景下光照和阴影对分类结果的影响，提高模型的准确率。

# 3.2LFW实验结果与分析

LFW[20]人脸库是有美国马萨诸塞大学计算机视觉实验室采集的包括5749个对象的13233幅人脸图像，其中4069个对象只有一幅图像，1680个对象有超过一幅的图像。该人脸库主要是为了研究和比较在非限制场景下人脸识别算法的准确率，已成为学术界和工业界识别性能评价基准。本文模型先在Facescrube[15]和VGG-dataface人脸数据库上进行预训练，然后在LFW提供的标准训练集上作Fine-turning训练，最后在LFW标准测试集上进行测试。为了进一步验证LBP特征图融合算法的有效性，设置Ours-ResFace 和Ours-LBP-ResFace 两个实验模型。前者不使用LBP特征图融合算法。表2所示为LFW人脸库准确率对比结果。

表2LFW人脸识别率对比  

<html><body><table><tr><td>人脸识别模型</td><td>准确率%</td></tr><tr><td>PCA+LDA</td><td>84.98</td></tr><tr><td>CS-LBP[17]</td><td>87.46</td></tr><tr><td>Fisher-Vector Faces</td><td>93.03</td></tr><tr><td>ConvNet-RBM[1]</td><td>91.75</td></tr><tr><td>DeepId[13]</td><td>97.45</td></tr><tr><td>FaceNet[3]</td><td>98.58</td></tr><tr><td>Ours-ResFace</td><td>98.63</td></tr><tr><td>Ours-LBP-ResFace</td><td>99.15</td></tr></table></body></html>

由表2数据分析可得：使用本文改进的二元组误差函数训练神经网络模型的准确率高于其他误差函数训练方法；使用LBP特征图融合算法的模型准确率有较大提高，说明融合纹理特征的图像在神经网络上具有更好的特征表达。本文模型结合LBP特征图融合和优化二元误差的方法训练神经网络，能进一步地限制特征向量的距离，提取更有效的人脸特征向量，也充分体现了本文两种方法在人脸识别上的优势。

# 4 结束语

本文为了提高人脸识别算法的准确性和鲁棒性，提出一种基于距离优化限定的人脸识别模型。首先在图像预处理阶段将LBP特征图与原始图像融合，为图像添加纹理信息；然后设计一个残差网络模型，将人脸图像编码为128维特征向量，并提出新的二元误差函数训练神经网络。实验结果表明，该算法更可行、更有效，使用距离优化限定的人脸识别算法，增强了表示图像特征的能力，且显著提高了人脸识别率。

# 参考文献：

[1]Sun Y,Wang XG,Tang X O.Hybrid deep learning for face verification [C]

Proc of IEEE International Conference on Computer Vision.2013:1489-

1496.   
[2] Taigman Y, Yang M, Ranzato M A,et al. Deepface: closing the gap to human-level performance in face verification [C]//Proc ofIEEE Conference on Computer Vision and Pattern Recognition. 2014: 1701-1708.   
[3]SchroffF,Kalenichenko D,Philbin J. Facenet: aunified embedding for face recognition and clustering $[ \mathrm { C } ] / \AA$ Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2015: 815-823.   
[4]Bartlett M S, Movellan JR,Sejnowski TJ.Face recognition by independent component analysis [J].IEEE Trans on neural networks,2002,13(6): 1450- 1464.   
[5]Albiol A,Monzo D,Martin A,et al.Face recognition using HOG-EBGM [J].Pattern Recognition Letters,2008,29 (10): 1537-1543.   
[6] 万源，李欢欢，吴克风，等.LBP 和 HOG 的分层特征融合的人脸识别 [J]．计算机辅助设计与图形学学报,2015,27(4):640-650.   
[7]徐梦珂，许道云，魏明俊．基于 2D-KPCA 的拉普拉斯特征映射人脸 识别[J].计算机应用研究,2017,34(7):2212-2215,2220.   
[8]Ahonen T,Hadid A,Pietikainen M.Face recognition with local binary paterns [C]/ Proc of European Conference on Computer Vision. Springer. 2004: 469-481.   
[9]Simonyan K, Vedaldi A, Zisserman A.Learning local feature descriptors using convex optimisation [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2014,36 (8): 1573-1585.   
[10]杨赛，赵春霞，刘凡，等．一种基于多种特征融合的人脸识别算法[J]. 计算机辅助设计与图形学学报,2017,29(9):1667-1672.   
[11] Zhang L, Zhang Q, Xiao C. Shadow remover: image shadow removal based onillumination recovering optimization [J]. IEEE Trans on Image Processing,2015,24 (11): 4623-4636.   
[12] Xiao C,Gan J. Fast image dehazing using guided joint bilateral filter [J]. The Visual Computer,2012,28 (6-8): 713-721.   
[13] Xiao C,Nie Y,Hua W,et al.Fast multi-scale joint bilateral texture upsampling [J]. The Visual Computer,2010,26 (4): 263-275.   
[14] Sun Y,Wang X, Tang X O. Deep learning face representation from predicting 10,O00 classes [Cl//Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2014: 1891-1898.   
[15] Sun Y, Chen Y,Wang X,et al. Deep learning face representation by joint identification-verification[C]//Advances in Neural Information Processing Systems. 2014: 1988-1996.   
[16] Xi Meng,Chen Liang,Polajnar D,et al.Local binary pattern network: a dep learning approach for face recognition [C]//Proc of IEEE International Conference on Image Processing.2016:3224-3228.   
[17] He K, Zhang X,Ren S,et al. Deep residual learning for image recognition [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2016: 770-778.   
[18] Heikkila M,Pietikainen M, Schmid C.Description of interest regions with local binarypatterns [J].Pattern Recognition,2009,42 (3): 425-436.

[19] $\mathrm { N g \ H }$ W,Winkler S.Adata-driven approach to cleaning large face datasets [C]//Proc of IEEE International Conference on Image Processing.2014: 343-347.

[20] Labeled faces in the wild:a database for studying face recognition in unconstrained environments [R].Amherst:University of Massachusetts, 2007.