# 基于卷积神经网络的轴承故障定性诊断

单建华 吕钦 张神林 郑近德 王孝义(安徽工业大学 机械工程学院 马鞍山 243002)

摘要：轴承定性诊断的传统方法需要复杂难懂的数学知识和高深的领域知识；基于深度置信网络的方法虽然克服了传统方法的缺点，但网络参数规模巨大，训练困难；基于时频图的卷积神经网络方法需用小波变换得到时频图。由于卷积神经网络具有强大的特征学习能力和泛化能力，提出了一种基于卷积神经网络的轴承故障定性诊断方法，直接利用一维振动信号对卷积神经网络进行训练。优势在于克服了传统方法的缺点；相比深度置信网络，网络参数少很多，训练高效；也无需小波变换得到时频图。采用西储大学和本实验室轴承数据，进行了一系列全面测试，表明本文方法能准确地定性诊断轴承故障，准确率高于其他所有方法；首次通过利用西储大学的轴承数据训练的卷积神经网络准确诊断了本实验室待测轴承的故障类型，这表明该方法能实际工程运用。

关键词：故障诊断； 卷积神经网络； 轴承中图分类号：TH156

# Bearing Qualitative Fault Diagnosis based on Convolution Neural Network

SHAN Jianhua LVQin ZHANG Shenlin ZHENG JindeWANG Xiaoyi (School of Mechanical Engineering,Anhui University of Technology, Maanshan 243002)

Abstract：Thetraditional methodsofqualitativediagnosisofbearingrequirecomplexanddificultknowledgeofmathematicsand deepdomainknowledge.The method basedondeep belief networkovercomes theshortcomingsof traditionalmethods,butthe amountof networkparametersarehuge,thus thenetwordis dificulttotrain.Convolution neural network time-frequencyimage method uses wavelet packet transform toobtaintime-frequency image.Asthestrong feature learningabilityand generalization abilityofconvolution neural network，aqualitative faultdiagnosismethodofbearing basedonconvolution neural network is proposed.Convolutionneural network istraineddirectlyonone-dimensional vibrationsignal.Theadvantagesofthis methodareto overcometheshortcomingsofthetraditionalmethods,theamount ofparametersaremuchlessandtrainingis efectivecompared to thedp belefntwork,don’tnedusewaveletpacket transfortoobtaintime-frequencyimage.Aseriesofcomprehensivetestsare caried out byusing thedataofCase Wester ReserveUniversityandourown laboratory.Theyshowthatthe methodcandiagnose thebearigfaultacuratelyandtheaccuracyishigherthanthatofallother methods.Forthefirsttime,theconvolution neural networdtrainedon Case Wester Reserve University'sdata,accuratelydiagnoses thefault typeofourown laboratory's bearing, which indicates that the method can be used in practical.

Key words:Fault diagnosis； CNN；Bearing

# 0 前言

轴承是旋转机械中重要的承载元件之一，也是机械设备中故障高发元件，所以轴承故障诊断显得尤其重要[1-2]，为此，国内外学者对此进行了大量研究。传统方法是人工提取特征，然后进行特征选择和降维及分类器设计。特征提取是最为重要的步骤，大量的方法被提出，例如小波分析，统计分析、经验模式分解、奇异值分解和自回归模型等[3-5]。然而，上述方法运算复杂和难以掌握，同时诊断效果不佳，难以实际运用。

近几年，深度学习作为机器学习的一个最新最热领域，发展迅速，在语音识别、图像处理等领域取得了巨大成功，以其强大的特征学习能力著称。所以，近年来有学者利用深度学习进行轴承故障定性诊断。赵光权[、雷亚国[7]等提出了基于深度信念网络DBN的轴承故障诊断方法，省去了人工提取特征的步骤，但是网络参数多，网络参数需要预训练且训练难度高，网络的泛化能力较弱，识别效果不够理想。何清波[8]、曾雪琼[9]提出基于卷积神经网络的轴承故障定性诊断，但是网络输入层是时频图，需要用小波变换将一维振动数据转化成二维时频图，运算复杂，且转化过程中会丢失信息，识别效果不佳。

卷积神经网络[10]作为深度学习的重要一员，主要运用于二维图像识别中，具有如下优点：（1）可以从大量的样本中自动学习数据的特征，省去了传统方法复杂繁琐的特征提取过程，减少了对专家知识的依赖。（2）结构采用局部连接、权值共享等手段，极大减小了网络参数规模，降低了训练难度，提高了训练速度、使得网络泛化能力增强。

卷积神经网络在图像识别方面已经广泛运用，但在故障诊断方面的运用却鲜有人尝试。卷积神经网络主要用于图像识别，图像尺寸是二维的，但卷积神经网络也可以用于一维信号。本质上只要信号具有平移不变性，就能通过卷积神经网络进行学习，不管信号是一维还是二维。图像具有平移不变性，轴承故障数据也具有平移不变性，本文实验结果验证了这一点。一维信号可以看成二维信号的特例，只需把一维信号的宽度认为是1。

据作者所知，本文提出了采用一维振动信号的基于卷积神经网络的轴承故障定性诊断方法。该方法具有如下优点：卷积神经网络能自动提取特征，不需人工参与，方法简单易懂，便于工程推广；网络训练难度低；诊断方法效果好，准确率高；诊断方法泛化能力强，能在实际故障定性诊断中取得良好效果。通过西储大学和本实验室轴承数据证明了本方法对轴承故障定性诊断的有效性。

# 1卷积神经网络简介

# 1.1 卷积神经网路的发展

1998年，YannLecun等[1]提出了LeNet-5，采用基于梯度下降法的反向传播算法对网络进行训练，并在手写数字数据库MNIST上取得了成功。因此卷积神经网络引起了学术界的关注，也逐渐应用在语音识别、人脸识别、物体识别等领域。

2012年，Hinton及其学生 AlexKrizhevsky 等人提出了AlexNet[l2]网络模型，并在大型图像数据库ImageNet[13]的竞赛中，以比第二名高出 $1 1 \%$ 的巨大优势取得了胜利。一时间卷积神经网络成为了学术界的焦点。之后，牛津大学提出了VGGNet[14],

谷歌提出了GoogLeNet[15]，微软提出了ResNet[16]。  
这些网络不断刷新了AlexNet创下的记录。

# 1.2 卷积神经网路的结构

卷积神经网络一般由输入层、卷积层、非线性激活层、池化层、全连接层、softmax输出层组成。其中核心为卷积层，非线性激活层，池化层。如图1所示是卷积神经网络的典型模型。

![](images/6268a5f6c1cb5efaedd951b71f88d82e08076006e1b1e42facb7968c858b9793.jpg)  
图1卷积神经网络的典型模型

卷积层运用卷积核完成从上一层到下一层的特征提取。 $X _ { i }$ 表示第 $i$ 层的特征图，卷积神经网络的输入层一般是图像，用 $X _ { 0 }$ 表示。卷积层的操作表示为

$$
X _ { i } = X _ { i - 1 } \otimes W _ { i } + b _ { i }
$$

其中： $W _ { i }$ 为第 $i$ 层的卷积核的权值矩阵， $\otimes$ 表示卷积运算， $b _ { i }$ 为第 $i$ 层的偏移向量。

非线性激活层通过非线性函数，完成从上一层到下一层的特征映射，表示为

$$
X _ { i } = F \big ( X _ { i - 1 } \big )
$$

其中： $F$ 为非线性函数，常用的非线性函数有ReLU 函数及其变体LeakyReLU,RandomReLU,Parametric ReLU, Shifted ReLU, Exponential LU[17]。

池化层：对特征图进行降采样，一方面可以对特征图进行降维，另一方面又可以减少卷积神经网络参数。其中最常见的是最大值池化，表示为$X _ { i } \displaystyle \left( a \ b \right) = \operatorname* { m a x } _ { ( 0 < p , q < s ) } \left( X _ { i - 1 } \displaystyle \left( a * s + p \ b * s + p \right) \right)$ (3）

其中： $s * s$ 是池化层窗口尺寸。

卷积神经网络的目标是使损失最小，损失包括经验风险和结构风险，经验风险常用的是交叉熵损失，结构风险通常是权重的二范数。

# 2轴承故障定性诊断方法流程

卷积神经网络进行轴承故障定性诊断时，分为四个步骤：创建训练数据库、创建卷积神经网络、训练卷积神经网络以及定性诊断轴承故障。

(1)创建训练数据库：对于每种工况下采样数据，优先采用随机方式创建，即在随机位置处截取振动数据中大于一个数据周期长度（即轴承旋转一周，采样数据点的个数）的连续数据点作为一个样本点，优先选择 $k * 2 ^ { n }$ 个数据点作为一个样本点，其中 $k$ 、 $n$ 为正整数。一般建议选取满足条件的最小数作为样本点长度数值，这样样本点长度较短，使得卷积神经网络训练更快，网络设置层数也可以减少。但有时为了提高诊断准确率，也可以适当增加样本点长度。

对于样本点的创建方式，MiaoHe[18]在提出了将原始信号进行短时傅里叶变换或者快速傅里叶变换，然后从中提取部分图谱作为样本点数据；何清波[8也是将原始信号通过小波包变换成时频图，然后利用时频图进行诊断；MinXia[19]提出了以原始信号为卷积神经网络作为输入，但多传感器时时构建二维图形式。还有其他的一些论文中，也并没有详细说明样本点的长度以及如何从很长的原始信号中提取样本点。而本文详细给出样本点长度计算公式，同时采用随机截取的方式，使得在测试时更加简便，无需寻找特定的截取位置，使得运用更加简便，随机截取样本点的方式还有一个优点就是使得样本点多样性增强，这样训练出来的卷积神经网络泛化能力更强。

重复上述样本点创建过程，创建足够多的样本点作为训练数据库。

（2）创建卷积神经网络：在创建卷积神经网络卷积时，可以在参考LeNet、AlexNet、ZFNet、VGGNet、GoogLeNet、ResNet 等经典卷积神经网络的基础上设计，或自行设计可行的卷积神经网络。

（3）训练卷积神经网络：利用训练数据库训练卷积神经网络，调试超参数，获得较好的卷积神经网络参数，提高网络泛化性能。

（4）定性诊断轴承故障：从待诊断的轴承振动数据中创建多个样本点，输入到训练好的卷积神经网络中，得到每个样本点的故障类型，采用出现次数最多的故障类型作为轴承的故障类型。

# 3轴承故障定性诊断实例

本实验采用美国凯斯西储大学（CaseWesternReserveUniversity）的轴承故障数据库，实验装置如图2所示。

![](images/954562770bac106b8fec14cc05b3e0d2b6b7cf8a72d7b74d42f16baf6448cc13.jpg)  
图2西储大学轴承故障信号采集装置

# 3.1 创建数据库

选用驱动端以采样频率 $1 2 k H z$ 采集的加速度数据，其中包括了正常、内圈故障、滚动体故障和外圈故障4种类型所有工况即48种工况的原始数据，其中包含的转速有1730rpm、1750rpm、1772rpm 和1797rpm四种，包含的故障程度有7mils、14mils、21mils和28mils（1mils=0.001inch）四种，包含的载荷有Ohp、1hp、2hp 和3hp 四种，hp 是马力。值得注意的是，0hp对应着1797rpm，1hp对应着1772rpm,2hp对应着1750rpm，3hp对应着1730rpm。对于外圈故障数据包含了三种不同的安装位置，分别是3、6和12点钟方向。

在所有工况中，最低转速是1730rpm， $1 2 k H z$ 采样频率时，此时数据周期为416。如图3所示，样本点采用随机方式创建，即每个样本点在随机位置处截取连续的512个数据点，512为大于数据周期416且满足 $k * 2 ^ { n }$ 的最小整数，样本点选取的数据点少，有利于降低卷积神经网络结构的复杂度和训练难度，同时能加快训练速度和减少测试时间。

![](images/d12fcd98bb77e98ce15026ab25296047d3d7a77bd1866b1b419296f5863c56bc.jpg)  
图3随机方式创建样本点，A是随机位置点，AB之间是512个数据点

对48种工况数据，每个工况创建600个样本点，由于外圈一个工况有三种安装位置，故每个工况创建1800个样本点，总共38400个样本点，并对每个样本点设置对应的故障类型标签，完成数据库

创建，如表1所示。

表1西储大学轴承故障数据库  

<html><body><table><tr><td>轴承故障 类型</td><td>故障程度（mils）</td><td>载荷类别（hp) 电机转速（rpm)</td><td>样本点个数</td><td>故障标签</td></tr><tr><td colspan="2">正常</td><td>0—1797 1—1772</td><td rowspan="4">2400</td><td rowspan="4">0</td></tr><tr><td colspan="2"></td><td>2—1750 3—1730</td></tr><tr><td colspan="2">7</td><td>0—1797</td></tr><tr><td rowspan="3">内圈故障</td><td>14</td><td>1—1772</td><td rowspan="3">9600</td><td rowspan="3">1</td></tr><tr><td>21</td><td>2—1750</td></tr><tr><td>28</td><td>3—1730</td></tr><tr><td rowspan="3">滚珠体 故障</td><td>7</td><td>0—1797</td><td rowspan="3">9600</td><td rowspan="3">2</td></tr><tr><td>14</td><td>1—1772</td></tr><tr><td>21 28</td><td>2—1750</td></tr><tr><td colspan="2"></td><td>3—1730</td><td></td><td></td></tr><tr><td rowspan="4">外圈故障</td><td></td><td>0—1797</td><td rowspan="4">16800</td><td rowspan="4">3</td></tr><tr><td>7</td><td>1—1772</td></tr><tr><td>14</td><td>2—1750</td></tr><tr><td>21</td><td>3-1730</td></tr></table></body></html>

# 3.2 创建卷积神经网络

直接采用一维振动信号作为网络输入层，即3.1节创建的样本点作为输入层。创建卷积神经网络时，参考了VGGNet的结构，网络包含输入层（inputlayer），卷积层（convolutionallayer）、最大池化层（max-pooling layer）、平均池化层（average-poolinglayer），SoftMax输出层。采用平均池化层代替全连接层，可极大减小网络权重数量，降低训练难度，同时也能提高网络预测精度[20]。每两个连续的卷积层后跟一个最大池化层，卷积层不改变特征图尺寸，池化层减小特征图尺寸到二分之一。每个卷积层后接一个非线性激活层，激活函数采用偏移修正线性函数(ShiftedReLU)，具体表达式为 $\mathrm { { m a x } ( - 1 , x ) }$ 。网络层数设为19层，其中1层输入层、11层卷积层，5层最大池化层以、1层平均池化层和1层SoftMax输出层。前10层卷积层的卷积模板尺寸均为 $3 ^ { * } 1$ 最后1层卷积层卷积模板尺寸为 $1 ^ { * } 1$ ，卷积层步长均取 $^ { 1 ^ { * } 1 }$ 。最大池化层的池化窗口尺寸均为 $2 ^ { * } 1$ ，步长均为 $2 ^ { * } 1$ 。输入层为 $5 1 2 ^ { * } 1 ^ { * } 1$ （样本点），SoftMax输出层有4维，对应4种故障类型。为了保证每次卷积运算后，特征图（feturemaps）尺寸不变，在对特征图进行 $3 ^ { * } 1$ 卷积运算之前，需对特征图进行填充（Padding），即在特征图首尾对称补一个零。网络各层的特征图数量依次为：1、12、12、12、24、24、24、48、48、48、96、96、96、128、128、128、4、4、4。网络结构如图4所示。

![](images/7e0c5b2267fe8ae4caa1f6e5a1aef443f623ed0c771ab35aa31e7965867c053c.jpg)  
图4卷积神经网络模型

# 3.2 设置网络超参数

训练卷积神经网络时所采用的超参数为：Nesterov动量随机梯度下降法，提前终止法，学习速率为0.003，正则化系数为0.0005，mini-batch（批量数）为32，动量系数为0.9；权重初始化为高斯分布的随机数，均值为零，方差为0.1，偏置初始化为零。

# 3.3 测试1

采用3.1节所创建的数据库，每种工况所创建的600个样本点按照6:2:2的比例随机分为训练集、验证集和测试集，如表2所示。

表2测试1中数据库分类情况  

<html><body><table><tr><td>轴承故障 故障程度（mils） （训练、验证 类型 /测试)</td><td>载荷类别（hp) （训练、验证 /测试)</td><td>样本点个数 （训练、验证 /测试)</td><td>故障标 签</td></tr><tr><td>正常</td><td>(0~3）/(0~3)</td><td>2400 （1440、480 /480)</td><td>0</td></tr><tr><td>内圈故障 (7~28）/(7~28)</td><td>(0~3）/(0~3)</td><td>9600 (5760、1920 /1920)</td><td>1</td></tr></table></body></html>

<html><body><table><tr><td colspan="3"></td></tr><tr><td>滚珠体 故障</td><td>(7~28）/(7~28）(0~3）/(0~3)</td><td>9600 (5760、1920 2 /1920）</td></tr><tr><td colspan="3"></td></tr><tr><td colspan="3">外圈故障 (7~21）/(7~21）(0~3）/(0~3)</td></tr></table></body></html>

采用提前终止法，在1900次停止训练，测试集的准确率，结果如表3所示。

表3测试1中测试集准确率  

<html><body><table><tr><td>轴承故障类型</td><td>正常</td><td>内圈故障</td><td>滚珠体 故障</td><td>外圈故障</td><td>全部</td></tr><tr><td>准确率(%)</td><td>100</td><td>100</td><td>99.24</td><td>100</td><td>99.79</td></tr></table></body></html>

这里特别强调下，测试集准确率 $9 9 . 7 9 \%$ 虽然没有达到 $100 \%$ 。但 $9 9 . 7 9 \%$ 是任一样本点的准确率，实际测试时，可以创建多个如100个样本点，得到每个样本点的故障类型，采用出现次数最多的故障类型作为轴承的故障类型，这时出现误判的概率接近零。

测试1采用混合工况，测试样本点所在工况在训练工况中都出现过，这与其他论文的做法相似，传统方法的准确率一般都在 $9 5 \%$ 左右，个别方法能达到 $98 \%$ 。深度学习DBN方法7准确率与样本点长度有很大的关系，当样本点长度为2048时，准确率为 $9 8 . 8 \%$ ；利用时频图的卷积神经网络诊断方法为$9 9 . 5 \%$ ，该文献只是使用了少数工况数据，不像本文使用了全部的48个工况，本文方法的准确率为$9 9 . 7 9 \%$ 。

测试1中，测试集所在的工况包含于训练集工况中，传统的人工提取特征方法所采用的测试方式基本都是这种方式，准确率比本文方法低，且很少对混合工况进行研究。测试集所在的工况包含于训练集工况中，即测试用的工况在训练卷积神经网络时，被卷积神经网络见过，在实际测试中，这种情况不可能存在的。因为实际测试时，测试轴承所在工况的数据是不可能在训练时得到的。为了避免测试集所在的工况包含于训练集工况中，使测试样本点被卷积神经网络见过的情况，设计了测试2。

# 3.4 测试2

测试2中，对于正常轴承采用 $0 h p$ 载荷的工况作为测试集。内圈故障的轴承采用四种故障程度下1hp 载荷的四种工况作为测试集。滚动体故障的轴承采用四种故障程度下2hp载荷的四种工况作为测试集。外圈故障的轴承采用三种故障程度下 $3 h p$ 载荷的三种工况下传感器相应安装位置下采集的七组数据作为测试集。

剩下的所有工况，每种工况所创建的600个样本点按照8:2的比例随机分为训练集和验证集，数据集分类如表4所示。

同测试1一样采用提前终止法，在1900 次停止训练，四个测试集的准确率，结果如表5所示。

表4测试2中数据库分类情况  

<html><body><table><tr><td>轴承故障 类型</td><td>故障程度（mils） 载荷类别（hp） （训练、验证 （训练、验证 /测试) /测试)</td><td>样本点个数 （训练、验证 /测试)</td><td>故障标签</td></tr><tr><td>正常</td><td>(1、2、3) /0</td><td>2400 (1440、360 /600)</td><td>0</td></tr><tr><td>内圈故障 (7~28）/(7~28)</td><td>(0、2、3) /1</td><td>9600 （5760、1440 /2400)</td><td>1</td></tr><tr><td>滚珠体 (7~28）/(7~28) 故障</td><td>(0、1、3) /2</td><td>9600 (5760、1440 /2400)</td><td>2</td></tr><tr><td>外圈故障 (7~21）/(7~21)</td><td>(0、1、2) /3</td><td>16800 （10080、2520 /4200)</td><td>3</td></tr></table></body></html>

表5测试2中测试集准确率  

<html><body><table><tr><td>轴承故障类型</td><td>正常</td><td>内圈故障</td><td>滚珠体 故障</td><td>外圈故障</td><td>全部</td></tr><tr><td>准确率(%)</td><td>100</td><td>96.5</td><td>99.6</td><td>95</td><td>97</td></tr></table></body></html>

与测试1不同的是，测试2的测试工况，没有出现在训练工况中，即卷积神经网络没有学习过这类工况，但本文定性诊断方法还能取得如此好的效果，进一步说明了该方法具有非常强的泛化能力。测试工况的故障大小在训练工况中出现过，载荷大小未出现过，这在实际测试中是合理的，因为实际工作中，载荷是变化的，故障大小是逐渐增大的，故障大小不同的工况可以提前采集进行训练。

西储大学采集的轴承数据库，目前国内很多研究故障定性诊断方法的学者们认为有几组工况下数据的特征不明显，分类准确率不高，如：B0071、B021_2； $\mathrm { O R 0 1 4 @ 6 \_ 0 }$ 、OR014@6_2，B007_1意思为滚动体故障类型，故障程度为7mils，载荷为1hp的工况，其他类似。针对这四种工况，我们做了同样的测试，即把这四种工况作为测试集，其他所有工况作为训练集和验证集。最终四种工况准确率分别为： $9 9 . 5 \%$ 、 $9 7 . 1 7 \%$ 、 $7 2 . 7 \%$ 、 $9 4 . 3 3 \%$ ，其中三种工况准确率和表5的准确率差别不大，只有一种工况准确率明显偏低。具体原因需进一步研究，目前猜测有两种可能：一种是准确率低的工况可能数据采集出现问题；一种是需进一步改进网络结构和训练方法，使之能正确识别该工况。

测试2中，测试工况没有在训练工况中出现。这种测试方法，据作者所知，像本文做得如此全面系统，是第一次，本文方法的准确率达到 $9 7 \%$ 。

测试2中，轴承数据都是来自同一型号，同一测试装置，在实际诊断轴承故障时，轴承型号可能不同、工况不同。为了验证卷积神经网络能诊断实际工作状态中的轴承，设计了测试3。

# 3.5测试3：实验轴承故障定性诊断

# 3.5.1 实验轴承数据来源

实验轴承故障定性诊断时，利用本实验室的测试装置采集数据，并利用测试1训练好的卷积神经网络模型对实验轴承故障定性诊断。

西储大学轴承数据采集实验装置中，加速度传感器采集振动信号，使用磁性底座将传感器安放在电机壳体上。加速度传感器分别安装在电机壳体的驱动端和输出端12点钟的位置。有些工况中，传感器安放在电机支承底盘上。

本实验室的测试装置如图5所示，2号传感器采集轴向振动信号，信号较为微弱；3号传感器采集径向振动信号，信号较强。

西储大学装置与本实验室装置的一些重要参数对比如表6所示。本实验室所用轴承型号、采样频率、轴承转速与西储大学不同，本实验室轴承故障大小、载荷模拟实际工作情况，与西储大学不同。

![](images/6d2dc548966f37a76c4474cb71468ad50a495d57d583067014afc8bd01233cbf.jpg)  
图5实验轴承实验装置

表6实验装置重要参数对比表  

<html><body><table><tr><td>数据来源</td><td>轴承型号</td><td>故障大小 (mils）</td><td>转速 （rpm）</td><td>采样频率 (Hz)</td></tr><tr><td rowspan="4">凯西西储 大学</td><td rowspan="4">6205</td><td></td><td>1797</td><td rowspan="4">12000</td></tr><tr><td>7 14</td><td>1772</td></tr><tr><td>21</td><td>1750</td></tr><tr><td>28</td><td>1730</td></tr></table></body></html>

<html><body><table><tr><td>本实验室 6210</td><td colspan="3">5120 1800</td></tr><tr><td></td><td></td><td></td><td>10240</td></tr><tr><td></td><td>电机载荷 （hp）</td><td>轴向载荷 径向载荷 (N) (N)</td><td></td></tr><tr><td>凯西西储</td><td>0</td><td></td><td></td></tr><tr><td>大学</td><td>１2</td><td></td><td></td></tr><tr><td></td><td>3</td><td></td><td></td></tr><tr><td colspan="3">0</td><td rowspan="3"></td></tr><tr><td colspan="3">本实验室</td></tr><tr><td colspan="3">100 300 200</td></tr></table></body></html>

# 3.5.2 实验轴承测试集创建

依据不同的采样频率，采用不同的数据点个数创建样本点。 $5 1 2 0 H z$ 采样频率，转速 $1 8 0 0 r p m$ ，数据周期为170.7，根据 $k * 2 ^ { n }$ 原则，样本点长度为256。 $1 0 2 4 0 H z$ 采样频率，数据周期为341.3，依据$k * 2 ^ { n }$ 原则，样本点长度为384。

$5 1 2 0 H z$ 采用频率，轴承有正常、内圈故障、外圈故障三种状态，载荷有三种，共7种工况，有两个传感器，每个工况下每个传感器采集的数据创建600个样本点，共8400个样本点。

$1 0 2 4 0 H z$ 采样时，轴承有内圈故障和外圈故障两种状态，载荷有三种，共6种工况，有两个传感器，每个工况下每个传感器采集的数据创建600个样本点，共7200个样本点。

表7实验轴承数据库  

<html><body><table><tr><td colspan="4">轴承故障 载荷 (N)</td><td rowspan="2">样本点 个数</td><td rowspan="2">故障标 签</td></tr><tr><td>采样频率 (Hz)</td><td>类型</td><td></td><td>传感器 编号</td></tr><tr><td rowspan="3">5120</td><td>正常</td><td></td><td></td><td>1200</td><td>0</td></tr><tr><td>内圈故障</td><td>0、100</td><td></td><td>3600</td><td>1</td></tr><tr><td>外圈故障</td><td>、200</td><td>2、3</td><td>3600</td><td>3</td></tr><tr><td rowspan="2">10240</td><td>内圈故障</td><td></td><td></td><td>3600</td><td>1</td></tr><tr><td>外圈故障</td><td></td><td></td><td>3600</td><td>3</td></tr></table></body></html>

# 3.5.3 实验数据轴承故障定性诊断结果

用测试1训练好的卷积神经网络对表7的样本点进行测试，测试结果如表8。

从表中可以看出，准确率大部分是 $100 \%$ ，最低也达到 $8 6 . 9 4 \%$ ，完全达到实际诊断轴承故障类型的要求。

3号传感器采集的数据准确率高于2号准确率，因为3号传感器采集的是径向振动信号，信号较强，2号传感器采集的是轴向振动信号，信号较弱。

![](images/b0550c0ad408a18c64caaa4c0e39d7afce55a2f87d03589c0fa8704bd1c535a3.jpg)  
图6西储大学和本实验室轴承不同故障类型下的波形图

图6可看出，本实验内圈故障振动振幅与西储大学内圈最小故障振幅相当，远大于无故障时的振幅。本实验外圈故障振动振幅远小于西储大学外圈最小故障振幅，且与无故障时的振幅相当。本实验无故障振幅与西储大学无故障振幅相当。

结合诊断效果，无故障和内圈基本诊断正确，外圈全部诊断错误为无故障类型，作者猜测波形振幅大小对诊断性能有重大影响，实验轴承振幅大小与训练轴承振幅大小相当，能诊断正确；差别巨大，诊断错误。本实验外圈振幅与西储大学无故障振幅相当，导致全部识别为无故障类型。如果训练轴承外圈振幅与本实验外圈振幅相当，那外圈故障还会识别错误吗？本实验中外圈故障的振幅与无故障振幅相当，卷积神经网络能区分开这两个类型吗？

# 3.6测试4：实验轴承故障训练及诊断

表9实验轴承样本点分类  

<html><body><table><tr><td></td><td></td><td>载荷 (N)</td><td>样本点个数</td><td>故</td></tr><tr><td>采样频率</td><td>轴承故障</td><td>训练、验证</td><td>训练、验证</td><td>障</td></tr><tr><td>(Hz)</td><td>类型</td><td>/测试</td><td>/测试</td><td>标</td></tr><tr><td></td><td></td><td></td><td></td><td>签</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">正常</td><td>(720、240) /240</td><td>0</td></tr><tr><td rowspan="2">5120</td><td>内圈故障</td><td>(2160、720) /720</td><td>1</td></tr><tr><td>外圈故障 /(0、100、200）)</td><td>(2160、720)</td><td>3</td></tr><tr><td rowspan="2">10240</td><td>内圈故障</td><td>(2160、720) /720</td><td>1</td></tr><tr><td>外圈故障</td><td>(2160、720) /720</td><td>3</td></tr></table></body></html>

为了验证3.5节的猜想，进行了测试4。采用测试1的方式，利用实验轴承数据，进行故障定性诊断。实验轴承数据中每种工况的样本点按照6:2:2比例随机分成训练集、验证集和测试集，样本点分类如表9所示。

值得注意的是， $5 1 2 0 H z$ 和 $1 0 2 4 0 H z$ 的样本点长度不一致，需要分开训练和测试。对 $5 1 2 0 H z$ ，只需将3.2节中的卷积神经网络输入层改为 $2 5 6 ^ { * } 1 ^ { * } 1$ ；对于 $1 0 2 4 0 H z$ ，只需将3.2节中的卷积神经网络输入层改为 $3 8 4 ^ { * } 1 ^ { * } 1$ 。网络结构和训练超参数不变。

分别对 $5 1 2 0 H z$ 和 $1 0 2 4 0 H z$ 的数据进行训练和测试，测试结果如表10所示。

表10测试4中测试集准确率  

<html><body><table><tr><td colspan="3">采样频率 5120 (Hz)</td><td colspan="2">10240</td></tr><tr><td>轴承故障 类型</td><td>正常</td><td>内圈故障</td><td>外圈故障内圈故障</td><td>外圈故障</td></tr><tr><td>准确率 (%)</td><td>99.29</td><td>100</td><td>98.75</td><td>100 100</td></tr><tr><td>总准确率 (%)</td><td></td><td>99.17</td><td></td><td>100</td></tr></table></body></html>

从表10看出，各种故障类型基本全部诊断正确，外圈故障振幅虽然与无故障振幅相当，也基本完全识别正确。这表明卷积神经网络能学习到振动模式，不仅仅是振幅大小。

结合3.5节的分析可以发现，卷积神经网络具有很强的泛化能力，只要待诊断轴承的故障大小与训练轴承同类型故障的任一故障大小相当，不论轴承型号，轴承品牌以及轴承载荷是否相同，都能正确诊断轴承故障类型。

为了达到实际使用目的，可以采集各种故障类型下，故障面积从小到大一系列故障程度的数据，训练卷积神经网络，通过训练好的卷积神经网络定性诊断实际轴承故障类型。

# 4结论

(1）本文首次提出直接采用一维振动信号作为输入层的卷积神经网络的轴承故障定性诊断方法。卷积神经网络可以自动提取轴承故障数据的特征，识别效果很好。(2）与传统方法比较，提出的方法省去了人工提取特征的复杂过程，准确率更高；与DBN相比，网络参数更少，无需预训练网络参数；与利用时频图的卷积神经网络相比，无需利用小波变换生成时频图，直接利用一维振动信号，提高诊断准确率。(3）本文首次进行了利用西储大学数据训练出的卷积神经网络来实际测试本实验室的轴承故障类型，识别效果很好。(4）本文方法泛化能力强；只要训练时，采集故障面积从小到大一系列振动信号，训练卷积神经网络，就可以运用训练好的卷积神经网络定性诊断轴承实际故障类型，达到工程实用化。

# 参考文献

[1]彭宇，刘大同．.数据驱动故障预测和健康管理综述[J].仪器仪表学报,2014,35(3)：481-495.PENG Y,LIU D T. Data-driven prognostics and health

management: A review of recent advances[J]. Chinese Journal of Scientific Instrument, 2014,35(3) : 481-495.   
[2] RANDALL R B，ANTONI J.element bearing diagnostics-A tutorial[J]. Mechanical Systems and Signal Processing,2011, 25: 485-520.   
[3] 闫鹏程,孙华刚,毛向东，等．基于EMD 与 SVD 的 齿轮箱分形诊断方法研究[J]．电子测量与仪器学报, 2012,26(5): 404-412. YAN P CH, SUN H G, MAO X D, et al. Research of fractal diagnosis method for gearbox based on EMD and SVD[J].Journal of ElectronicMeasurementand Instrument,2012,26(5) : 404-412.   
[4] WANG H, CHEN J, DONG G. Feature extraction of bearing’s early weak fault based on EEMD and tunable Q-factor wavelet transform[J].Mechanical Systems & Signal Processing,2014,48 (1-2): 103 - 119.   
[5] 王太勇，何慧龙，王国峰，等．基于经验模式分解和最 小二乘支持矢量机的轴承故障诊断[J]．机械工程学报, 2007, 43(4) : 88-92. WANG T Y, HE H L,WANG G F, et al. The fault diagnosisofbearingsbased on empirical mode decompositionandleastsquaresupportvector machine[J]. Journal of Mechanical Engineering,2007, 43(4) : 88-92.   
[6]赵光权，葛强强，刘小勇，等．基于DBN 的故障特征 提取及诊断方法研究[J]．仪器仪表学报,2016,37（9)： 1946-1953. ZHAO G Q,GE Q Q,LIU X Y,et al. The research of fault feature extraction and diagnosis method based on DBN [J]. Chinese Journal of Scientific Instrument, 2016, 37(9): 1946-1953.   
[7]雷亚国，贾峰，周昕，等．基于深度学习理论的机械装 备大数据健康监测方法[J]．机械工程学报,2015, 51(21) : 49-56. LEI Y G, JIAF, ZHOU X,et al.A deep learning-based method for machinery health monitoring with big data[J]. Journal of Mechanical Engineering,2015,51(21) :49-56.   
[8] DING X X,HE Q B. Energy-Fluctuated Multiscale Feature Learning With Deep ConvNet for Intelligent Spindle Bearing Fault Diagnosis[J]. IEEE Transactions onInstrumentationandMeasurement,17March 2017:1-10.   
[9]曾雪琼，黎杰．基于卷积神经网络的时频图像研究 [J]．机械与电子,2016,34(5):25-29. ZENG X Q,LI J. The research of time frequency image based on convolution neural network[]. Machinery & Electronics,2016,34(5): 25-29.   
[10] 李彦东，郝宗波，雷航．卷积神经网络综述[J].计算机 应用,2016,36(9) : 2508-2515,2565. LI Y D, HAO Z B,LEI H. Summary of the convolutional neural network[J]. Journal of Computer Applications, 2016, 37(9) : 1946-1953.   
[11] LECUNY，BOTTOUL，BENGIO Y，et al. Gradient-based learning applied to document recognition[J]. Proceedings of the IEEE ，1998,86(11) : 2278 - 2324.   
[12]KRIZHEVSKY A，SUTSKEVER I， HINTON G E. ImageNet classification with deep convolutional neural networks[C].Proceedingsof Advancesin Neural Information Processing Systems． Cambridge,MA: MIT Press， 2012:1106-1114.   
[13]DENG J,DONG W,SOCHER R,et al. ImageNet:a large-scale hierarchical image database [C].Proceedings of the 2Oo9 IEEE,Conference on Computer Vision and Pattern Recognition．Washington，DC:IEEE Computer Society,2009:248-255.   
[14] SIMONYANK， ZISSERMANA， Verydeep convolutional networks for large-scale image recognition [EB/OL]．arXiv:1409.1556v6 [cs.CV] 10 Apr 2015.   
[15] SZEGEDYC，LIUW，JIAY，et al．Going deeper with convolutions [EB/OL].arXiv:1409.4842v1 [cs.CV] 17 Sep 2014.   
[16] HE K， ZHANG X,REN S,et al． Deep residual learning forimagerecognition[EB/OL]. arXiv:1512.03385v1 [cs.CV]10 Dec 2015.   
[17]CLEVERT D，UNTERTHINER T,HOCHREITER S. Fast and accurate deep network learning by exponential linearunits(ELUS)[EB/OL]. arXiv:1511.07289v5 [cs.LG] 22 Feb 2016.   
[18]HE M,HE D.Deep Learning Based Approach for Bearing Fault Diagnosis[J].IEEE Transactionson Industry Applications.2017,53(3):3057-3065   
[19]XIA M,LIT,XUL,LIUL Z, rt al.FaultDiagnosis for RotatingMachinery UsingMultipleSensorsand Convolutional Neural Networks [EB/OL].IEEE/ASME Transactions on Mechatronics.2017   
[20] LIN M,CHEN Q，YAN S CH. Network in network [EB/OL].arXiv:1312.4400v3[cs.NE]4Mar2014.