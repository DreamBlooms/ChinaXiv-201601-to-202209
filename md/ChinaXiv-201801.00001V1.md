# 多属性卷积神经网络及其在轴承故障诊断中的应用

单建华 吕钦 张神林 郑近德 王孝义(安徽工业大学 机械工程学院 马鞍山 243002)

摘要：现有轴承故障诊断方法存在不足：传统方法数学计算复杂，诊断效果不佳，且一般只诊断故障位置，难以诊断载荷及故障大小。现有的利用卷积神经网络的方法，使用传统卷积神经网络，一个网络只能输出一个属性，不能同时诊断多个属性，为了同时诊断故障位置、故障大小及载荷，首次提出了一种多属性卷积神经网络，并应用于轴承故障诊断，直接利用一维振动信号对多属性卷积神经网络进行训练。优势在于克服了传统方法的缺点：能获得故障属性任意组合的诊断结果，网络参数更少，方法简洁，泛化能力强，准确率高。采用西储大学的轴承数据，进行了一系列测试，表明本文方法能准确地诊断轴承故障的多个属性，准确率高，同时有很好的泛化能力。

关键词：卷积神经网络；故障诊断；轴承；多属性

中图分类号：TH156

# Multi-attributes Convolution Neural Network and its Application to Bearing Quantitative Fault Diagnosis

SHAN Jianhua LVQin ZHANG Shenlin ZHENG JindeWANG Xiaoyi (School of Mechanical Engineering,Anhui University of Technology, Maanshan 243002)

Abstract:The existing methodsofbearing diagnosis havesome disadvantages:Theconventional methodhascomplex mathematical calculationandpoordiagnosisefect.Itgenerallyonlydiagnosesthefaultlocationandirespectiveofteloadandthefaultie.The existingconvolutional neural networkmethodusethetraditionalconvolution neural network.Anetworkcanonlyoutput aproperty andcannotsimultaneouslydiagnosemultipleproperties.Inordertosimultaneouslydagnosethefaultlocation,faultsizeadload, forthefirst timeputforwardamulti-atributesconvolutionneuralnetwork (MACNN)andappliedtothebearingfaultdiagnosis.The multi-atributeconvolutionneural network istrainedusingone-dimensionalvibrationsignaltraining.Theadvantagesliesin overcoming thesortcomingsofthetraditionalmethod:thediagnosisresultofanycombinationofthefaultatributescanbebtaied, thenetwork parametersareles,themethod issimple,thegeneralizationabilityisstrongandtheaccuracyrateishigh.Aseriesof tests havebeecarredoutusing the bearingdataofCase WesternReserve University.Theresults show thattheproposed methodcan accurately diagnose several properties of bearing faults with high accuracy and good generalization ability.

Key Words: Convolution neural network; Fault Quantitative diagnosis; Bearing; Multi-attributes

# 0 前言

轴承是工业中应用最广泛的机械零件之一，同时也是故障频发零件[1-2]，过去大部分方法都只诊断轴承故障发生位置（正常、外圈故障、内圈故障和滚珠体故障）[3-5]。对故障大小和轴承载荷等属性的诊断具有重大的现实意义，可以改变传统的事后维修或预先维修得维修制度，减少经济损失和零件浪费。同时诊断故障位置、故障大小及载荷等属性难度很大，采用传统模式识别方法，难于取得好效果，故此方面进展很小。大部分学者虽然考虑了故障位置和故障大小两个因素，其做法是把不同故障位置和故障大小的组合作为一个整体，不能查看轴承故障的单个属性诊断结果[6-7]；有的学者只考虑了某一种故障位置下的故障大小的诊断，且数学方法复杂难懂。现有的轴承故障大小的诊断分为回归方法和分类方法；对于回归算法，鞠华[8提出了基于SVR的轴承故障定量诊断，通过提取特征，利用训练集训练SVR模型，然后诊断测试的轴承故障大小，其故障大小为 $0 . 2 { \sim } 0 . 7 \mathrm { m m }$ 的均匀分布，但其只包含外圈故障，故障位置单一。崔玲丽[提出了基于动力学仿真的轴承大小诊断方法，通过动力学仿真获得不同故障大小的振动信号，然后依据振动信号中双冲击的时间间隔来确定故障大小，验证时采用相同的故障大小下仿真信号与真实振动信号双冲击的时间差别小表明了方法的有效性。对于分类方法，因大部分论文中，故障大小数据种类少，文章一般对故障大小进行分类，将不同的故障大小看成不同的类，同时与故障位置进行组合形成多个类别进行分类诊断。

近几年，深度学习作为机器学习的一个最新最热领域，发展迅速，在语音识别、图像处理等领域取得了巨大成功，以其强大的特征学习能力著称。卷积神经网络[10]作为深度学习的重要一员，主要运用于二维图像识别中，具有如下优点：（1）可以从大量的样本中自动学习数据的特征，省去了传统方法复杂繁琐的特征提取过程，减少了对专家知识的依赖。（2）结构采用局部连接、权值共享等手段，极大减小了网络参数规模，降低了训练难度，提高了训练速度、使得网络泛化能力增强。因此国内外学者开始尝试将卷积神经网络运用于旋转机械故障诊断中，但是仅仅是诊断故障位置，没有同时诊断故障大小和载荷。同时使用的都是传统的卷积神经网络，无法同时诊断多个属性。2016年中国石油大学WangJinjiang[11]采用卷积神经网络进行旋转机械故障诊断，卷积神经网络的输入直接采用截取的一维振动数据；2017年北京航天航空大学的Chen$\mathrm { L u } ^ { [ 1 2 ] }$ 及西安交通大学的LiuRuonan[13]等都采用通过将一维振动信号拼接成二维信号，再作为卷积神经网络输入进行故障诊断；2017年加拿大英属哥伦比亚大学的MinXia[14]提出了基于多传感器融合的卷积神经网络的旋转机械故障诊断。

针对传统方法和现有基于卷积神经网络的轴承故障诊断方法存在的不足，根据多标签卷积神经网络[15-16]的思想，本文首次提出一种多属性卷积神经网络，将多属性卷积神经网络运用于轴承故障诊断中，具有如下优点：能同时诊断故障位置、故障大小以及载荷等多种属性，网络结构简洁，参数少，网络训练难度低；自动提取特征，准确率高；不需人工参与，方法简单易懂，便于工程推广；诊断方法泛化能力强，能在实际故障诊断中取得良好效果。通过西储大学轴承数据证明了本方法对轴承故障诊

断的有效性。

# 1多属性卷积神经网络

# 1.1 卷积神经网路的发展

1998年，YannLecun等[17]提出了LeNet-5，采用基于梯度下降法的反向传播算法对网络进行训练，并在手写数字数据库MNIST上取得了成功。因此卷积神经网络引起了学术界的关注，也逐渐应用在语音识别、人脸识别、物体识别等领域。

2012年，Hinton及其学生 AlexKrizhevsky 等人提出了AlexNet[18]网络模型，并在大型图像数据库ImageNet[19]的竞赛中，以比第二名高出 $1 1 \%$ 的巨大优势取得了胜利。一时间卷积神经网络成为了学术界的焦点。之后，牛津大学提出了VGGNet，谷歌提出了GoogLeNet，微软提出了ResNet。这些网络不断刷新了AlexNet创下的记录。

# 1.2 卷积神经网路的优点

卷积神经网络在图像识别中，利用局部区域的卷积和池化，提取局部区域的相关性，而轴承故障诊断也是考虑振动信号的局部特征，因此可以利用卷积神经网络进行故障诊断。通过卷积操作，并通过反向传播理论对卷积核进行修正，可以得到类似于小波变换的特征，还可以自动提取振动信号的平均值、均方差、频谱关系等其他传统类似的特征，此外卷积神经网络除了能得到类似于传统方法的特征，同时能自动得到有别于传统方法的其他特征，再将各种特征综合考虑进行故障诊断，因此卷积神经网络的效果比传统方法更好。

# 1.3 卷积神经网路的结构

传统的卷积神经网络一般由输入层、卷积层、非线性激活层、池化层、全连接层、softmax输出层组成。在本文中将其称为单属性卷积神经网络。其中核心为卷积层，非线性激活层，池化层。如图1所示是卷积神经网络的典型模型。

![](images/5ec73e8a9555da174b6993041d20dcc84fb0a4923f16cd7ce9395ff7143c8dd2.jpg)  
图1卷积神经网络的典型结构

卷积层运用卷积核完成从上一层到下一层的特征提取。 $X _ { i }$ 表示第 $i$ 层的特征图，卷积神经网络的输入层一般是图像，用 $X _ { 0 }$ 表示。卷积层的操作表示为

$$
X _ { i } = X _ { i - 1 } \otimes W _ { i } + b _ { i }
$$

其中： $\boldsymbol { W } _ { i }$ 为第 $i$ 层的卷积核的权值矩阵， $\otimes$ 表示卷积运算， $b _ { i }$ 为第 $i$ 层的偏移向量。

非线性激活层通过非线性函数，完成从上一层到下一层的特征映射，表示为

$$
X _ { i } = F \big ( X _ { i - 1 } \big )
$$

其中： $F$ 为非线性函数，常用的非线性函数有ReLU函数及其变体LeakyReLU,RandomReLU,Parametric ReLU, Shifted ReLU, Exponential LU[20]。

池化层：对特征图进行降采样，一方面可以对特征图进行降维，另一方面又可以减少卷积神经网络参数。其中最常见的是最大值池化，表示为

$$
X _ { i } \displaystyle \left( a \ b \right) = \operatorname* { m a x } _ { ( 0 < p , q < s ) } \left( X _ { i - 1 } \displaystyle \left( a * s + p \ b * s + p \right) \right)
$$

其中： $s * s$ 是池化层窗口尺寸，a和b是像素坐标。

卷积神经网络的目标是使损失最小，损失包括经验风险和结构风险，经验风险常用的是交叉熵损失，结构风险通常是权重的二范数。

# 1.4多属性卷积神经网路的结构

轴承运行时，不同工况具有不同转速，不同载荷等，故障属性包括故障位置、故障大小等，而为了在轴承故障诊断时同时诊断上述属性，现有做法分为属性组合方法和多网络方法。属性组合方法：将不同的属性值进行组合，得到不同类，然后进行诊断，此时网络的输出维数是各个属性的属性值个数的乘积，网络输出过大，网络参数过多，难以训练，同时不能单独查看网络对某一个属性的诊断效果；多网络方法：根据属性个数，创建多个诊断网络，一个网络诊断一种属性，此时网络个数多，诊断时间长，网络参数多。为此本文首次提出多属性卷积神经网络。

多属性卷积神经网络创新在于克服了上面两种方法的缺点，采用一个网络同时识别故障的多个属性，且输出维数是各个属性种类个数的和，远远小于属性组合方法的各个属性属性值种类个数的乘积。多属性卷积神经网络通过输出层之前的网络共用，只是增加输出层维数，有效地减少了网络参数和测试时间。因此多属性卷积神经网络在轴承故障诊断里运用，能同时诊断故障位置、故障大小、载荷以及转速等各个属性。

在多属性卷积神经网络结构中，SoftMax输出层以前的网络结构与单属性卷积神经网络相似，可以参考LeNet、AlexNet、ZFNet、VGGNet、GoogLeNet、ResNet等经典单属性卷积神经网络的基础上设计，或自行设计。

多属性卷积神经网络结构包含输入层、卷积层、最大池化层、平均池化层、SoftMax输出层，每层卷积层后接一个激活层；输入层为 $\mathrm { H } ^ { * } \mathrm { l } ^ { * } \mathrm { l }$ ，其中H为样本点数据长度。单属性卷积神经网络的SoftMax输出层是由一个得分向量（scorevector）组成的，多属性卷积神经网络的SoftMax输出层则由M个得分向量组成。轴承的每个故障属性用一个得分向量表示，每个得分向量的维数等于对应故障属性下属性种类数目。以凯西西储大学的轴承故障数据为例，如图2所示，可以看出轴承故障共有三种属性，分别是故障位置、故障大小和轴承载荷，因此SoftMax 输出层有三个得分向量，每种属性对应一个得分向量，每个得分向量的不同位置对应该属性下的属性类别。在测试时，每个得分向量中最大值位置对应的属性类别预测为该故障属性的类别。由此可以看出，每个故障属性是独立诊断的，故能给出故障属性任意组合的诊断结果。

外圈故障 28- 3  
滚动体故障 21- 2  
内圈故障- 14 1  
无故障 7 00S1 S2 S3 S4 s1 S2 S3 S4 S5 S1 S2 S3 S4第1种故障属性： 第2种故障属性： 第3种故障属性：故障位置 故障大小 轴承载荷共有4类属性种 共有5类属性种 共有4类属性种类，S（Score）向 类，S（Score）向 类，S（Score）向量元素最大值所 量元素最大值所 量元素最大值所在位置的序号预 在位置的序号预 在位置的序号预测为属性种类的 测为属性种类的 测为属性种类的序号 序号 序号

单属性卷积神经网络的风险损失是单个交叉熵函数，多属性卷积神经网络的风险损失是M个交叉熵函数的加权平均值。

单属性卷积神经网络的样本点 $i$ 的风险损失为：

$$
L _ { i } = - \log \left( \frac { e ^ { s _ { y _ { i } } } } { \sum _ { j } e ^ { s _ { j } } } \right)
$$

式中向量 $s$ 是得分向量， $y i$ 为样本点 $i$ 的标签。多属性卷积神经网络的样本点i的风险损失为：

$$
L _ { i } = \sum _ { k = 1 } ^ { M } L _ { i k }
$$

其中 $L _ { i k }$ 为：

$$
L _ { i k } ~ { = } ~ - ~ \mathrm { l o g } \left( \frac { e ^ { s k _ { y _ { i k } } } } { \displaystyle \sum _ { j = 1 } ^ { n k } e ^ { s k _ { j } } } \right)
$$

式中： $\mathbf { M }$ 是故障属性数目， $L _ { i k }$ 是故障属性 $k$ 的风险损失，向量 $s k$ 是故障属性 $k$ 的得分向量， $n k$ 是故障属性 $k$ 的属性种类数目，向量 $y i$ 是多属性标签，$y _ { i k }$ 为故障属性 $k$ 的多属性标签的序号。

# 2轴承故障诊断方法流程

卷积神经网络进行轴承故障诊断时，分为四个步骤：创建训练数据库、创建卷积神经网络、训练卷积神经网络以及诊断轴承故障。

（1）创建训练数据库：在多属性卷积神经网络中，训练数据库的创建分为样本点数据的创建和样本点多属性标签的创建。对于每种工况下采样数据，采用随机方式创建，即在随机位置处截取振动数据中大于一个数据周期长度（即轴承旋转一周，采样数据点的个数)的连续数据点作为一个样本点数据，优先选择 $k * 2 ^ { n }$ 个数据点作为一个样本点数据，其中 $k = 1$ 或3， $n$ 为正整数；随机创建方式的优点是模型泛化能力强。重复上述样本点数据创建过程，创建足够多的样本点数据作为训练数据库。再对每个样本点数据创建多属性标签，轴承故障属性的数目为 $\mathbf { \delta M }$ ，则样本点多属性标签有M维，每维数值对应该故障属性下的属性种类的序号。

（2）创建多属性卷积神经网络：创建多属性卷积神经网络卷积时，SoftMax输出层以前的网络结构可以在参考LeNet、AlexNet、ZFNet、VGGNet、GoogLeNet、ResNet等经典卷积神经网络的基础上设计，或自行设计。SoftMax输出层由M个得分向量组成。轴承的每个故障属性用一个得分向量表示，每个得分向量的维数等于对应故障属性下属性种类数目。

（3）训练卷积神经网络：利用训练数据库训练多属性卷积神经网络，调试超参数，获得较好的卷积神经网络参数，提高网络泛化性能。

（4）诊断轴承故障：将待诊断轴承的样本点数据输入训练好的多属性卷积神经网络中，SoftMax输出层输出M个得分向量，每个得分向量中最大值所在位置序号诊断为该属性种类的序号，这M个属性种类的最大值序号组成的向量为一个多属性标签，每个样本点诊断出一个多属性标签，则多个样本点诊断出多个多属性标签，采用出现次数最多的多属性标签作为轴承故障诊断结果。

# 3轴承故障诊断实例

本实例采用美国凯斯西储大学（CaseWesternReserveUniversity）的轴承故障数据库，实验装置如图3所示。

![](images/931ba579750619480790641fde9f327ff970ec2bde73800318b9ddcd0e7c628a.jpg)  
图3西储大学轴承故障信号采集装置

# 3.1 创建数据库

选用驱动端以采样频率 $1 2 k H z$ 采集的 48 种工况加速度数据。其中，包含正常、内圈故障、滚动体故障和外圈故障四种故障位置;包含1730rpm、1750rpm、1772rpm和1797rpm四种转速;包含0mils、7mils、14mils、21mils和28mils（ $1 m i l s { = } 0 . 0 0 1 i n c h )$ （204号五种故障大小以及0hp、1hp、2hp 和3hp（hp为马力）四种载荷，因此轴承共有四种属性，但由于 $0 h p$ 对应着1797rpm，1hp 对应着1772rpm，2hp 对应着1750rpm，3hp对应着1730rpm。在诊断时诊断故障位置，故障大小和载荷三种属性即可。由于故障大小和载荷只有几种情况，故本文对这两种属性进行分类识别，而不是回归。

在所有工况中，最低转速是1730rpm，12kHz采样频率时，此时数据周期为416。如图4所示，样本点数据采用随机方式创建，即在随机位置处截取连续的512个数据点，512为大于数据周期416且满足 $k * 2 ^ { n }$ 的最小整数，样本点数据选取的数据点少，有利于降低卷积神经网络结构的复杂度和训练难度，同时能加快训练速度和减少测试时间。

创建样本点多属性标签时，轴承故障属性有三种，多属性标签用3维向量表示，向量元素表示属性种类的序号。故障位置下属性种类有4类分别用序号（1、2、3、4）表示，故障大小和载荷属性与故障位置类似。举例说明，如轴承是内圈故障且故障大小为0.014inch时，载荷为 $0 h p$ 时，多属性标签为[231]；如轴承无故障则故障大小为0，载荷为1hp 时，多属性标签为[112]。

![](images/ab85e73a2df1cb4473892d69176749970b6fff7ed74e1fa42f2c226d14051620.jpg)  
图4随机方式创建样本点数据，A是随机位置点，AF之间是512个数据点

对48种工况数据，每个工况创建600个样本点，由于外圈一个工况有三种安装位置，故每个工况创建1800个样本点，总共38400个样本点，并对每个样本点设置对应的多属性标签，完成数据库创建。

# 3.2创建多属性卷积神经网络

直接采用一维振动信号作为网络输入层，即3.1节创建的样本点数据作为输入层。SoftMax输出层以前的网络结构参照VGGNet的网络构型，网络包含输入层，卷积层、最大池化层、平均池化层、SoftMax输出层。采用平均池化层代替全连接层，可极大减小网络权重数量，降低训练难度，同时也能提高网络诊断精度[26]。每两个连续的卷积层后跟一个最大池化层，卷积层不改变特征图尺寸，池化层减小特征图尺寸到二分之一。每层卷积层后都接一个激活层，激活函数采用ShiftedReLU（偏移修正线性单元），具体表达式为 $\mathrm { \ m a x } ( - 1 , \ \mathrm { \ x } )$ 。

网络层数设为19层，卷积层有11层，最大池化层有5层以及1层平均池化层，前10层卷积层的卷积模板尺寸均为 $3 ^ { * } 1$ ，最后1层卷积层卷积模板尺寸为 $^ { 1 ^ { * } 1 }$ ，卷积层步长均为 $^ { 1 ^ { * } 1 }$ ；最大池化层的池化窗口尺寸均为 $2 ^ { * } 1$ ，步长均为 $2 ^ { * } 1$ ；输入层大小为$5 1 2 ^ { * } 1 ^ { * } 1$ （样本点），最后以SoftMax层输出，网络结构如图5所示。由于轴承故障属性有3个：故障位置、故障大小和轴承载荷，则SoftMax 输出层由三个得分向量组成，故障位置下属性种类有4种，故第1个得分向量是4维向量；故障大小下属性种类有5种，故第2个得分向量是5维向量；轴承载荷下属性种类有4种，故第3个得分向量是4维向量；则最终 SoftMax 输出层有 $1 3 ( = 4 + 5 + 4 )$ 维。为了保证每次卷积运算后，特征图（Feturemaps）尺寸不变，进行 $3 ^ { * } 1$ 卷积运算之前，需对特征图进行填充（Padding），即在样本点首尾各补一个零。网络各层的特征图大小依次为：1、12、12、12、24、24、

24、48、48、48、96、96、96、128、128、128、13、13、13。最后三层的特征图大小为13等于三个得分向量的维数之和。风险损失是3个得分向量风险损失的平均值。

![](images/5cdf5ec2a5bf181bf69468fbc62e5d7d9aeda68480d475d392b300b51fc84434.jpg)  
图5多属性卷积神经网络结构

样本点 $i$ 的风险损失公式：

$$
L _ { i } = -  \int _ { 3 } { * \log ( \frac { e ^ { s 1 _ { y i 1 } } } { \displaystyle \sum _ { j = 1 } ^ { 4 } e ^ { s 1 _ { j } } } ) } -  \int _ { 3 } { * \log ( \frac { e ^ { s 2 _ { y _ { i 2 } } } } { \displaystyle \sum _ { j = 1 } ^ { 5 } e ^ { s 2 _ { j } } } ) }
$$

$$
- \not \langle \gamma _ { 3 } * \log \left( \frac { e ^ { s 3 _ { y _ { 3 } } } } { \sum _ { j = 1 } ^ { 4 } e ^ { s 2 _ { j } } } \right)
$$

式中：向量s1是故障位置的得分向量，向量s2 是故障大小的得分向量，向量s3是载荷的得分向量，[yilyi2yi3]是多属性标签。

# 3.2 设置网络超参数

训练卷积神经网络时所采用的超参数可以在训练时依据训练效果调试，本实例中网络的超参数为：Nesterov动量随机梯度下降法，提前终止法，学习速率为0.003，正则化系数为0.0005，mini-batch（批量数）为32，动量系数为0.9；权重初始化为高斯分布的随机数，均值为零，方差为0.1，偏置初始化为零。

# 3.3 测试1

采用3.1节所创建的数据库，每种工况所创建的600个样本点（部分工况为1800个样本点）按照6:2:2的比例随机分为训练集、验证集和测试集。

利用训练集训练卷积神经网络，采用提前终止法，在12000次停止训练，测试集的平均准确率为$8 9 . 7 4 \%$ ，结果如表1所示。由于同时诊断三种属性（故障位置，故障大小，载荷大小），样本点只有三种属性同时诊断正确才认为诊断正确。

表1轴承故障诊断准确率  

<html><body><table><tr><td>准确率 载荷 故障位置和 大小(mils)</td><td>（hp） 0</td><td>1</td><td>2</td><td>3</td></tr><tr><td>正常 0</td><td>100</td><td>99.2</td><td>86.3</td><td>75</td></tr><tr><td rowspan="4">内圈 故障</td><td>7</td><td>100</td><td>99.6 99.5</td><td>100</td></tr><tr><td>14 99.2</td><td>98.2</td><td>94</td><td>96.4</td></tr><tr><td>21</td><td>99.6</td><td>97.2 98.6</td><td>98.7</td></tr><tr><td>28</td><td>81.5 57.9</td><td>56.5</td><td>90.8</td></tr><tr><td rowspan="4">滚动体 故障</td><td>7</td><td>95</td><td>94.4</td><td>90.6 98.2</td></tr><tr><td>14</td><td>96.1 98.8</td><td>98.47</td><td>99.6</td></tr><tr><td>21</td><td>97.2 95.3</td><td>98.6</td><td>100</td></tr><tr><td>28</td><td>46 25</td><td>21</td><td>28.5</td></tr><tr><td rowspan="3">外圈 故障</td><td>7</td><td>93.5</td><td>94.7</td><td>97.5 98.6</td></tr><tr><td>14</td><td>100</td><td>83.1 96.8</td><td>98.5</td></tr><tr><td>21</td><td>94.2 92.8</td><td>84.6</td><td>93.2</td></tr></table></body></html>

从表1可以看出，大部分工况下准确率达到99.6以上，这说明本文方法能准确同时诊断三种故障属性。但是最低的只有 $21 \%$ ，通过对轴承振动波形的分析发现准确率低的工况中，载荷对振动波形的影响很小，难以区分，主要是载荷属性识别错误。由于本文采用多属性卷积神经网络，能获得故障属性任意组合的诊断结果，测试1中如果只考虑轴承故障位置和故障大小两种属性的准确率如表2，轴承故障位置和大小两种属性的平均准确率 $9 8 . 9 6 \%$ 比三种属性的准确率 $8 9 . 7 4 \%$ 有明显提高，这说明主要是轴承载荷没有诊断正确。特别的，对于故障大小为28miles的滚动体故障，三种属性都对，准确率只有 $30 . 1 \%$ ；故障位置和故障大小两种属性，准确率则为 $100 \%$ ，明确地显示这些工况下，轴承载荷诊断错误。仔细观察这些工况下的振动波形，发现不同载荷下的波形几乎一致。总而言之，本文提出的方法能同时准确诊断故障三个属性，而且能查看不同属性组合的诊断效果，这是传统属性组合方法做不到的。

表2故障位置和故障大小诊断准确率  

<html><body><table><tr><td>准确率 故障大 小 故障位 置</td><td>0</td><td>7</td><td>14</td><td>21</td><td>28</td></tr><tr><td>正常</td><td>100</td><td></td><td></td><td></td><td></td></tr><tr><td>内圈故障</td><td></td><td>100</td><td>97.37</td><td>100</td><td>100</td></tr><tr><td>滚珠体故障</td><td></td><td>100</td><td>100</td><td>93.18</td><td>100</td></tr><tr><td>外圈故障</td><td></td><td>99.32</td><td>100</td><td>97.95</td><td></td></tr></table></body></html>

这里特别强调下，测试集平均准确率为 $8 9 . 7 4 \%$ 或 $9 8 . 9 6 \%$ ，虽然没有达到 $100 \%$ 。但 $8 9 . 7 4 \%$ 或$9 8 . 9 6 \%$ 是任一样本点的准确率，实际测试时，可以对一个故障轴承创建多个如100个样本点，得到每个样本点的故障多属性标签，采用出现次数最多的多属性标签作为轴承的诊断结果，这时出现误判的概率接近零。

故障诊断的目的是对实际工作时的轴承进行诊断，而不是对训练轴承进行诊断，所以对网络的泛化性能要求高。实际工作时的轴承所在工况是很难都在训练时得到，为了验证本文提出的方法具有良好的诊断效果，留下部分轴承工况不用于训练，模拟实际工作的轴承，测试时只诊断这些留下的轴承，为此设计了测试2。

# 3.4 测试2

轴承工作时可能是变工况，主要是载荷发生变化，这时就要考虑不同载荷下能不能准确诊断故障位置和故障大小，此时载荷是未知的。故本测试中，样本点的属性只包含故障位置和故障大小，样本点的多属性标签是2维。相同故障位置和故障大小情况下，留下一个载荷的工况模拟实际工作轴承，来诊断其故障位置和故障大小，剩下的三种载荷用于训练。实际工作轴承具体工况如下：正常轴承的载荷为0，内圈故障载荷为1，滚动体故障为2，外圈故障载荷为3。

各种工况的样本点个数均取600个，其中训练工况的样本点按照8:2的比例随机分为训练集和验证集。

表3测试2中测试集准确率  

<html><body><table><tr><td>准确率 故障大 小 故障位 置/载荷</td><td>0</td><td>7 14</td><td>21</td><td>28</td></tr><tr><td>正常 /0</td><td>100</td><td></td><td></td><td></td></tr><tr><td>内圈故障 /1</td><td>100</td><td>85.17</td><td>100</td><td>100</td></tr><tr><td>滚珠体 故障 /2</td><td>88.33</td><td>100</td><td>70</td><td>100</td></tr><tr><td>外圈故障 /3</td><td>99.62</td><td>99</td><td>100</td><td></td></tr></table></body></html>

采用提前终止法，在10000次停止训练，并测试12个模拟实际工作轴承的准确率，结果如表3所示，平均准确率达到 $9 6 . 3 \%$ ，说明了该方法具有非常强的泛化能力。

据作者所了解的文献，都没有给出如本文这样全面的准确率数据，因此难以进行公平客观的比较。作为一个粗糙的比较，其他基于深度学习的轴承故障诊断方法准确率基本在 $98 \%$ 左右 $\cdot [ 1 1 \cdot 1 3 \cdot 1 4 ]$ ，与本文测试1接近，但实验包含的工况较少，而且样本点的数据个数比本文多，没有测试1全面；且其诊断时是将不同故障属性进行组合在进行诊断，容易使网络输出层维数呈指数增长导致网络难以训练。同时未进行本文测试2的实验，没有验证其方法在实际工作轴承的诊断效果及卷积神经网络的泛化能力。综合比较，本文方法优于其他方法。

# 4结论

(1)本文首次提出了多属性卷积神经网络并应用于轴承故障诊断，诊断效果好。(2)与传统诊断方法相比，多属性卷积神经网络直接采用原始振动数据进行训练和测试，方法简洁，自动提取轴承故障数据特征，识别效果好。(3)与现有的神经网络诊断方法比，利用一个网络可以输出多个属性，便于查看各个属性的诊断效果，网络参数更少，测试时间更短。同时验证了网络的泛化能力强。

# 参考文献

[1]RANDALL RB， ANTONI J. element bearing diagnostics-A tutorial[J].Mechanical Systems and Signal Processing,2011,25: 485-520.   
[2]彭宇，刘大同．数据驱动故障预测和健康管理综述[J]. 仪器仪表学报,2014,35(3):481-495. Journal of Scientific Instrument,2014,35(3) : 481-495.   
[3] 闫鹏程,孙华刚，毛向东，等．基于 EMD 与 SVD 的 齿轮箱分形诊断方法研究[J].电子测量与仪器学报, 2012, 26(5) : 404-412. YAN P CH, SUN H G, MAO X D,et al. Research of fractal diagnosis method for gearbox based on EMD and SVD[J]. Journal ofElectronic Measurementand Instrument,2012,26(5) : 404-412.   
[4] 王太勇，何慧龙，王国峰，等．基于经验模式分解和最 小二乘支持矢量机的轴承故障诊断[J]．机械工程学报, 2007, 43(4) : 88-92. WANG T Y,HE H L,WANG G F,et al. The fault diagnosisof bearingsbasedonempiricalmode decompositionandleastsquaresupportvector machine[J]. Journal of Mechanical Engineering,2007, 43(4) : 88-92.   
[5]WANG H, CHEN J,DONG G.Feature extraction of bearing’s early weak fault based on EEMD and tunable Q-factor wavelet transform[J].Mechanical Systems & Signal Processing, 2014,48 (1-2): 103-119.   
[6] DING X X,HE Q B. Energy-Fluctuated Multiscale Feature Learning With Deep ConvNet for Intelligent Spindle Bearing Fault Diagnosis[J]. IEEE Transactions onInstrumentation andMeasurement,17March 2017:1-10.   
[7]赵光权，葛强强，刘小勇，等．基于DBN 的故障特征 提取及诊断方法研究[J]．仪器仪表学报,2016,37（9)： 1946-1953. ZHAO G Q, GE Q Q, LIU X Y, et al. The research of fault feature extraction and diagnosis method based on DBN [J].Chinese Journal of Scientific Instrument, 2016, 37(9): 1946-1953.   
[8]鞠华，沈长青，黄国伟，,等．基于支持向量回归的轴承 故障诊断应用[J].振动、测试与诊断,2014,34（4): 767-771. JU H,SHENG C Q, HUANG G W, et al. Quantitative Diagnosis of Bearing Fault Based on Support Vector Regression [J]． Journal of Vibration,Measurement & Diagnosis. 34( 4) : 767-771.   
[9] 崔玲丽，张宇，等．基于振动响应机理的轴承故障诊 断及量化分析[J]．北京工业大学学报,2015,41(11): 1681-1687. CUI L L, ZHANG Y, et al.Vibration Mechanism Based Quantitative Diagnosis and Quantization Analysisof Rolling Bearing Fault[J]. Journal of Beijing University of Technology,2015,41(11) $\because$ 1681-1687.   
10] 李彦东，郝宗波，雷航．卷积神经网络综述[J]．计算机 应用,2016,36(9):2508-2515,2565. LI Y D, HAO Z B,LEI H. Summary of the convolutional neural network[J]. Journal of Computer Applications, 2016,37(9) : 1946-1953.   
[11] WANG J J, ZHUANG J H,DUAN L X,et al. A multi-scale convolutional neural network for featureless fault diagnosis[C]． 2016 International Symposium on Flexible Automation，Cleveland,Ohio，U.S.A.，1-3 August, 2016.   
[12]LUC,WANG ZY,ZHOUB．Intelligent fault diagnosis ofrolling bearing using hierarchical convolutional network based health state classification[J]. Advanced Engineering Informatics,2017,32 :139-151.   
[13]LIU R N,MENG G T,et al.Dislocated time series convolutional neural architecture: an intelligent fault diagnosisapproach forelectricmachine[J].IEEE Transactions on industrial informatics， 2017,13(3） : 1310-1320.   
[14] XIA M,LI T,et al. Fault diagnosis for rotating machinery usingmultiplesensorsandconvolutionalneural networks[C].IEEE/ASME Transactions on Mechatronics, 1083-4435 (c) 2017, 1-9.   
[15]LUBOMIR B，SUBHRANSU M，et al.Describing People:APoselet-Basedapproach toattribute classification[J]. IEEE International Conference on Computer Vision,2011,2(11) :1543-1550.   
[16] ZHU J Q，LIAO S C，LEI Z，et al.Multi-label convolutional neural network based pedestrian attribute classification[J].Image and Vision Computing,2017,58 : 224-229   
[17]LECUNY，BOTTOUL， BENGIO Y,et al. Gradient-based learningapplied to document recognition[J].Proceedings of the IEEE，1998,86(11) : 2278-2324.   
[18] KRIZHEVSKY A，SUTSKEVER I，HINTON G E. ImageNet classification with deep convolutional neural networks[C]. Proceedings of Advances in Neural Information Processing Systems． Cambridge,MA: MIT Press，2012:1106-1114.   
[19]DENG J,DONG W,SOCHER R,et al. ImageNet:a large-scale hierarchical image database [C].Proceedings of the 2Oo9 IEEE,Conference on Computer Vision and Pattern Recognition.Washington，DC:IEEE Computer Society, 2009:248-255.   
[20] LIN M,CHEN Q，YAN S CH.Network in network [EB/OL].arXiv:1312.4400v3 [cs.NE] 4 Mar 2014.