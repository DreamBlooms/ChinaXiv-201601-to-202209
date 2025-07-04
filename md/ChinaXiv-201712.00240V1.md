# 多SoftMax卷积神经网络及其在行星齿轮箱复杂故障诊断中的应用

单建华 吕钦 张神林 孟瑞 王孝义(安徽工业大学 机械工程学院 马鞍山 243002)

摘要：现有行星齿轮箱故障诊断方法存在不足：一是传统方法复杂，且不能有效诊断行星齿轮故障类型。二是基于卷积神经网络的方法主要用于诊断齿轮箱故障，很少用来诊断行星齿轮箱。为有效诊断复杂的故障类型和变工况，本文首次提出了故障树形结构、工况并列结构和多 SoftMax 卷积神经网络。故障树形结构能统一处理各种复杂故障类型，还能查看各个节点的诊断效果。工况并列结构能处理变工况，预测转速和载荷。采用实验室行星齿轮箱的振动数据，进行了一系列测试，表明了本方法能够准确诊断行星齿轮箱复杂故障和变工况，准确率达 $9 7 \%$ ，验证了多SoftMax卷积神经网络强的泛化能力，以及故障树形结构的优势。

关键词：故障诊断；行星齿轮箱；深度学习；卷积神经网络

中图分类号：TH156

# Multi-SoftMax Convolution Neural Network and Its Application in the Diagnosis of Planetary Gearbox Complicated Faults

SHAN Jianhua LVQin ZHANG ShenlinMENG RuiWANG Xiaoyi (School of Mechanical Engineering,Anhui University of Technology, Maanshan 243002)

Abstract:Therearesomeshortcomingsintheexisting methodsoffaultdiagnosisofplanetarygearbox:First,thetraditionalethods arecomplex andcannotefectivelydiagnosethe planetary gearbox faults.Second,the methods basedonconvolution neuralnetwork mostlydiagnosegearboxfaultsandrarelyareusedtodiagnoseplanetarygearbox.Inordertoefectivelydiagnosecomplexfaultsand variable workingconditions,faulttreestructure,workingconditionparalelstructureandmulti-SftMaxconvolutioneuraletwork are proposedforthefirsttime.Fault treestructurecanhandleavarietyofcomplex faultsandseethediagnosis efectofeachnode. The paralle structurecan handle variableconditions,and predict speedandload.Aseriesof experiments arecariedoutusing the vibrationdataofourslboratoryplanetarygearbox,whichindicatedthatthemethodcanaccuratelydiagnosethecomplexfaultsnd variable working conditions of the planetary gearbox,and the accuracy is $9 7 \%$ . It is verified that the multi-SoftMax convolution neural network has strong generalization ability,and the advantages of the fault tree structure.

Key words:Fault diagnosis; Planetary gearbox; Deep learning; Convolution neural network

# 0 前言

行星齿轮箱具有传动比大，体积小，承载能力大等优点，因此广泛运用于风力发电、治金、船舶和起重运输等。一旦发生故障，会造成严重的安全事故，因此行星齿轮箱故障诊断显得尤其重要[1-2]。行星齿轮箱中齿轮运动是典型的复合运动，其振动响应比轴承和定轴传动齿轮箱更为复杂，相应的故障诊断问题具有自身的特点和难点[3]。为此，国内外学者对此进行了大量研究。

加拿大多伦多大学的YU[4提出了基于小波变换和时域平均的行星齿轮箱故障诊断方法，2017年湖南大学的程军圣[5]提出了基于ASTFA和SDEO调节的行星齿轮箱故障诊断方法；2016 年哈尔滨工业大学的黄文涛[6提出了基于自适应优化品质因子的共振稀疏分解方法的行星齿轮箱故障诊断方法。上述方法只适用于稳态工况、数学方法复杂以及诊断效果不佳。为克服这些方法存在的不足，需提出一种创新的方法来解决行星齿轮箱的故障诊断问题。

近几年，深度学习作为机器学习的一个最新最热领域，发展迅速，在自然语言处理、图像识别等领域取得了巨大成功，以其强大的特征学习能力著称。卷积神经网络[7作为深度学习的重要一员，主要运用于二维图像识别中，具有如下优点：（1）可以从大量的样本中自动学习数据的特征，省去了传统方法复杂繁琐的特征提取过程，减少了对专家知识的依赖。（2）结构采用局部连接、权值共享等手段，极大减小了网络参数规模，降低了训练难度，提高了训练速度、使得网络泛化能力增强。

近年国内外学者开始尝试将卷积神经网络运用于旋转机械故障诊断中，主要应用于轴承故障诊断。2016年中国石油大学WangJinjiang[8]采用卷积神经网络进行旋转机械故障诊断，卷积神经网络的输入直接采用截取的一维振动数据；2017年北京航天航空大学的 Chen Lu[9]、哈尔滨工业大学的 ZhangWei[lo]以及西安交通大学的LiuRuonan[11]等都采用通过将一维振动信号拼接成二维信号，再作为卷积神经网络输入进行故障诊断；2017年加拿大英属哥伦比亚大学的MinXia[l2提出了基于多传感器融合的卷积神经网络的旋转机械故障诊断。上述的论文中存在某些不足：

(1)卷积神经网络的输入样本长度是人为随  
意给定的固定数值，难以推广到不同采样频率，不  
同转速的工况。(2)主要用于诊断轴承，故障比较明显，振动  
波形差别大，而在行星齿轮箱的故障诊断中，振动  
波形差别很小，诊断难度远大于轴承。(3)工况较为简单，转速固定或者变化范围很  
小，没有研究变工况的诊断问题。(4)对于复合故障，采用的方法是将复合故障  
设置一个独立的类，不能查看单个故障诊断的效果。

针对上述利用卷积神经网络进行旋转机械故障诊断存在的不足，本文提出了改进方案，有效地解决了行星齿轮箱的故障诊断问题，本文的创新点包括：

（1)给出样本数据长度的计算公式，能适应不同转速、不同采样频率的工况。同时采用随机截取方式创建样本，使得网络泛化能力更强，测试时也更加方便。

(2)提出故障树形结构，能统一处理单一和复合故障，并能查看各个节点诊断的效果。

(3)为了实现故障树形结构的诊断问题，提出了多SoftMax的网络结构。

(4)本文采用大的卷积窗口、大的池化步长和最新的卷积神经网络DenseNet[13]结构，简化了网络结构，解决了变工况下行星齿轮箱的复杂故障诊断问题。

# 1故障树形结构及多SoftMax卷积神

# 经网络

# 1.1卷积神经网路的发展

1998年，YannLecun等[14]提出了LeNet-5，采用基于梯度下降法的反向传播算法对网络进行训练，并在手写数字数据库MNIST上取得了成功。因此卷积神经网络引起了学术界的关注，也逐渐应用在语音识别、人脸识别、物体识别等领域。

2012年，Hinton及其学生AlexKrizhevsky 等人提出了AlexNet[15]网络模型，并在大型图像数据库ImageNet[16]的竞赛中，以比第二名高出 $1 1 \%$ 的巨大优势取得了胜利。一时间卷积神经网络成为了学术界的焦点。之后，牛津大学提出了VGGNet[17],谷歌提出了GoogLeNet[18]，微软提出了ResNet[19],这些网络不断刷新了AlexNet创下的记录。2016年12月康奈尔大学、清华大学和FaceBook提出了DenseNet，进一步减少了网络规模，降低了训练难度，提高了网络的泛化能力，被评为2017CVPR国际会议最优论文，成为卷积神经网络的最优结构。

# 1.2 卷积神经网路的结构

传统的卷积神经网络一般由输入层、卷积层、非线性激活层、池化层、全连接层、SoftMax输出层组成。核心为卷积层，非线性激活层，池化层。如图1所示是卷积神经网络的典型结构。

![](images/1269b57cb0d008c684f87517aa73dcb8ce4561e9188e65550136c478db8a7967.jpg)  
图1卷积神经网络典型结构

卷积层运用卷积核完成从上一层到下一层的特征提取。 $X _ { i }$ 表示第 $i$ 层的特征图，卷积神经网络的输入层一般是图像，用 $X _ { 0 }$ 表示。卷积层的操作表示为

$$
X _ { i } = X _ { i - 1 } \otimes W _ { i } + b _ { i }
$$

其中： $W _ { i }$ 为第 $i$ 层的卷积核的权值矩阵， $\otimes$ 表示卷积运算， $b _ { i }$ 为第 $i$ 层的偏移向量。

非线性激活层通过非线性函数，完成从上一层

到下一层的特征映射，表示为

$$
X _ { i } = F \big ( X _ { i - 1 } \big )
$$

其中： $F$ 为非线性函数，常用的非线性函数有ReLU 函数及其变体LeakyReLU,RandomReLU,Parametric ReLU, Shifted ReLU,Exponential LU[20]。

池化层：对特征图进行降采样，一方面可以对特征图进行降维，另一方面又可以减少卷积神经网络参数。最常见的是最大值池化，表示为

$$
X _ { i } \displaystyle \left( a \ b \right) = \operatorname* { m a x } _ { \left( 0 \leq p , q < s \right) } \left( X _ { i - 1 } \displaystyle \left( a * s + p \ b * s + p \right) \right)
$$

其中： $s * s$ 是池化层窗口尺寸，a和 $\boldsymbol { \mathbf { b } }$ 是像素坐标。

卷积神经网络的目标是使损失最小，损失包括经验风险和结构风险，经验风险常用的是交叉熵损失，结构风险通常是权重的二范数。

# 1.3 故障树形结构

实际情况下，故障类型可能特别复杂，有单一故障、复合故障，各种故障的程度不一等等，为了能统一处理各种故障情况，设计了故障树形结构，具体如图2所示。

SoftMax1 正常 有故障 SoftMax2 1 单一故障 复合故障 SoftMax3 ↓ SoftMax4 太阳轮 轴承 太阳轮+轴承 行星轮+轴承 SoftMaxs SoftMax6 SoftMax7 SoftMax8 断齿 裂纹 磨 缺 内圈 滚动体 外 断 裂 磨 缺齿 损 齿 圈 齿 纹 损 1 一 SoftMax9 轻微 中等 较重 严 轻微 中等 较 严 轻微 中等 较 严 轻微 中 较 严 重 重 重 重 重 等 重 重

故障树形结构中，正常（无故障）和有故障为故障树的根节点，往下分叉出节点，直到叶节点。正常为叶节点，有故障分为单一故障和复合故障。单一故障分为太阳轮、轴承、行星轮和行星架等不同零部件故障；对于太阳轮故障分为断齿、裂纹、磨损、缺齿等不同故障类型；太阳轮裂纹故障等根据故障程度分为轻微、中等、较重等故障程度。同理可得到其他零部件故障结构。复合故障是多个零部件出现故障，不限于两个零部件。通过每个零部件故障的组合，可得到复合故障。

对于其他机械的故障类型，可同样设计相应的故障树形结构。

# 1.4 工况并列结构

行星齿轮箱除了有不同的故障类型，还存在变工况，即转速和载荷会发生变化。设计工况并列结

构，如图3所示，根据实际工况，确定几个典型的转速和载荷。如果有其他工况属性也可以加到工况并列结构中。

![](images/d3224444a1ebad508dd41629f77bbbe55e9988ee39cc6c09e391b12a45e0b245.jpg)  
图3工况并列结构

# 1.5多SoftMax卷积神经网络的结构

多SoftMax卷积神经网络结构包含输入层、卷积层、最大池化层、平均池化层、多SoftMax输出层，多SoftMax输出层是输出层有多个SoftMax得分向量，得分向量集合为 $S = \bigl \{ S o f t M a x _ { i } \big | i = 1 , . . . , m \bigr \}$ ，如图4所示，每个 $S o f t M a x _ { i }$ 与最后一层特征层是全连接。1.2节介绍的传统的卷积神经网络是多SoftMax卷积神经网络的特例，即输出层只有一个SoftMax得分向量。

![](images/2d74536b8cf05ad7598be93872705e9430e309912daa83515695f3f9c75763cd.jpg)  
图2行星齿轮箱故障树形结构  
图4多SoftMax卷积神经网络结构

多SoftMax卷积神经网络的经验风险损失与传统的卷积神经网络差别很大。以图2为例，某个行星齿轮箱的故障类型是太阳轮出现故障，但不知道太阳轮具体哪个位置出故障，则对应SoftMax得分向量下标集为：{123}，某个行星齿轮箱的故障类型是太阳轮出现裂纹故障，且是中等程度，则对应SoftMax得分向量下标集为： $\{ 1 2 3 5 9 \}$ 。可见，样本对应多个SoftMax得分向量，而且SoftMax得分向量的数目是不定的。

样本包含的SoftMax得分向量除了故障树形结构中的SoftMax得分向量，也包含工况并列结构中的SoftMax得分向量。如图3，如果是转速2和载荷3，则工况并列结构的SoftMax得分向量下标集为： $\{ 1 0 1 1 \}$ 。故障树形结构和工况并列结构同时存在时，样本包括两者的SoftMax得分向量。结合图2和图3，单一故障下的轴承外圈故障，工况为转速

1，载荷2，则对应SoftMax 得分向量下标集为：{1  
2 3 610 11}。

多SoftMax卷积神经网络的经验风险损失是样本包含的多个SoftMax得分向量的交叉熵函数的平均值。单个 $S o f t M a x _ { i }$ 得分向量的经验风险损失为：

$$
L _ { i } = - \log \left( \frac { e ^ { s m _ { \ y i } } } { \displaystyle \sum _ { j = 1 } ^ { n } e ^ { s m _ { \ j } } } \right)
$$

式中 $s m$ 是 $S o f t M a x _ { i }$ 得分向量， $n$ 是 $S o f t M a x _ { i }$ 维数，$y _ { i }$ 为 $S o f t M a x _ { i }$ 得分向量对应的标签值。

样本的风险损失为：

$$
L = \frac { 1 } { | \boldsymbol { S } \mathrm { i } | } \sum _ { \mathrm { i } \in \boldsymbol { S } \mathrm { i } } L _ { i }
$$

式中，Si( $\mathrm { | } \mathrm { S i } \in \mathrm { S } \mathrm { | }$ ）为样本的SoftMax得分向量集合，Si为集合Si元素数目。

根据式（5），此时在经验风险损失反向梯度传递时，只需传递Si集合中SoftMax得分向量的梯度，S-Si中SoftMax得分向量的梯度不要反向传递。

确定样本标签的方法为：样本每个SoftMaxi得分向量对应标签的一个元素，元素取值为该SoftMaxi得分向量中相应属性的序号（序号从1开始）。如SoftMax3是轴承故障，则标签该元素值为2；某个行星齿轮箱的故障类型是太阳轮出现裂纹故障，且是中等程度，则标签为[2112 2]。

# 2行星齿轮箱故障诊断方法流程

多SoftMax卷积神经网络进行行星齿轮箱故障诊断时，分为四个步骤：创建训练数据库、创建多SoftMax卷积神经网络、训练多SoftMax卷积神经网络以及诊断行星齿轮箱故障。

(1)创建训练数据库：训练数据库的创建分为样本数据的创建和样本标签的创建。对于每种工况下采样数据，采用随机方式创建，即在随机位置处截取振动数据中大于一个最大数据周期长度（即最低转速下，行星齿轮箱旋转一周，采样数据点的个数）的连续数据点作为一个样本数据，优先选择$k * 2 ^ { n }$ 个数据点作为一个样本数据，其中 $k$ ， $n$ 为正整数；随机创建方式的优点是模型泛化能力强。重复上述样本数据创建过程，创建足够多的样本数据作为训练数据库；接着根据故障树形结构和工况并列结构创建样本的标签。

（2）创建多SoftMax卷积神经网络：创建多SoftMax卷积神经网络卷积时，多SoftMax输出层以前的网络结构在DenseNet基础上设计。输入层为$\mathrm { H } ^ { * } \mathrm { l } ^ { * } \mathrm { K }$ ，其中H为样本数据长度，1是数据宽度，K为数据维度即传感器数目。采用多个传感器采集信号，同时利用多个传感器采集的信号进行故障诊断可以提高诊断的准确率，相当于在数据层进行了多传感器融合。

（3）训练卷积神经网络：利用训练数据库训练多SoftMax卷积神经网络，每次mini-batch（批量数）训练网络，每次mini-batch包含的样本均不同，直到训练结束，这样每个样本只参与一次训练。所有这些mini-batch样本构成了训练集。调试超参数，获得较好的卷积神经网络参数，提高网络泛化性能。

（4）诊断行星齿轮箱故障：将待诊断行星齿轮箱的样本数据输入训练好的多SoftMax卷积神经网络中，得到多SoftMax得分向量。

对于故障树形结构的SoftMax得分向量，首先从根节点的SoftMax得分向量开始，根据最大值位置往下判断，直到叶节点退出。以图2为例，首先从根节点SoftMax1得分向量即有无故障开始判断，判断方法为：得分向量中最大值所在位置如果在1，则判断正常，由于正常是叶节点，所以直接退出。如果位置在2，则判断为有故障，继续往SoftMax2判断。其他SoftMax判断方式与SoftMax1一样，SoftMax2得分向量如果判断为单一故障，则复合故障不需判断。

工况并列结构直接判断即可。最后得到样本诊断结果。

为了提高诊断可靠性，可采集多个样本，对每个样本都得到相应标签，采用出现次数最多的标签作为最终标签，获得行星齿轮箱的故障类型和工况。

# 3行星齿轮箱故障诊断实例

本实例采用实验室行星齿轮箱实验装置自测故障数据，实验装置如图5所示，运用两个传感器采集振动数据。

![](images/b30451cee00594e55e4c43cc77f9bbe9b621ec587d341240e9b46f8b1db8d6c7.jpg)  
图5本实验室装置

行星齿轮箱参数如表1所示。

表1实验行星齿轮箱参数  

<html><body><table><tr><td>部件</td><td></td><td>太阳轮</td><td>行星轮</td><td>外齿圈</td><td>行星架</td></tr><tr><td colspan="2">参数 齿数</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="2">模数（mm）</td><td>28</td><td>36</td><td>100</td><td></td></tr><tr><td colspan="2">压力角（deg)</td><td>1</td><td>1 20</td><td>1 20</td><td></td></tr><tr><td colspan="2">齿宽（mm）</td><td>20 10</td><td>10</td><td>10</td><td></td></tr><tr><td colspan="2">质量（kg)</td><td>0.069</td><td>0.057</td><td>0.422</td><td>0.709</td></tr><tr><td colspan="2">节圆直径（mm)</td><td>28</td><td>36</td><td>100</td><td></td></tr></table></body></html>

实验中有四种太阳轮转速： $1 0 \mathrm { H z }$ 、15Hz、 $2 0 \mathrm { { H z } }$ 和 $2 5 \mathrm { H z }$ 。由于实验限制，相对于图2的故障树形结构，故障类型做得较为简单。太阳轮单一故障有断齿、裂纹、磨损和缺齿，转频为 $1 0 \mathrm { H z } \cdot 2 0 \mathrm { H z }$ 和 $2 5 \mathrm { H z }$ 复合故障包含太阳轮故障和轴承外圈故障，太阳轮故障为断齿、裂纹、磨损和缺齿，转频为 $1 5 \mathrm { H z }$ 和$2 0 \mathrm { { H z } }$ 。载荷分为有载荷和无载荷两种。

下，磨损振动模式与其他故障类型差别较大，但磨损振动模式与其他工况下其他故障类型的振动模式较为相似，如（1）中磨损与（2）中断齿。缺齿振动模式很明显，容易识别。

# 3.1 创建数据库

![](images/1babe427009ae985d25e53f20c868801df6cbdb28facb200b5023011d5e269b4.jpg)  
图6不同工况下振动波形图

振动数据的采样频率为 $8 1 9 2 \mathrm { H z }$ ，最小转频为$\boldsymbol { 1 0 \mathrm { H z } }$ ，此时太阳轮旋转一圈，采样的数据点数为820，820为数据周期。1280是超过数据周期820且是符合 $\mathrm { k } { * } 2 ^ { \mathrm { n } }$ 的整数，其中 $k { = } 5$ ， $\mathrm { n } { = } 8$ 。每种工况下的振动数据，在随机位置处截取1280个连续数据点作为一个的样本数据，如图7所示，这样选取的样本数据长度相对较短，有利于降低多SoftMax卷积神经网络结构的复杂度和训练难度，同时能加快训练速度。采用随机方式创建样本数据，在实际测试时，无需从特定点截取测试数据，使得测试更为简便。而且由于是位置是随机的，理论上可以创建足够多的样本数量。

![](images/0bc3edf06500bb760708bfbfd899d034dcaea3f80f42bafc9fcffbb0331591e5.jpg)  
图7样本数据创建

![](images/df3932b008a63d0fb9c90ed32b4d056a6e2f629009459508254ae77235c52d77.jpg)  
图8本实例故障树形结构，工况并列结构及多SoftMax 输出层形式

不同工况下振动波形图如图6所示，可以发现，同种工况下正常、断齿、裂纹振动波形很接近，说明行星齿轮箱的故障诊断难度比较大。在相同工况

本实验对应的故障树形结构和工况并列结构如图8所示，对应图2和图3的SoftMax得分向量下标集为[123457810]，由于图2中的SoftMax得分向量下标集[348]只有一个属性值，因此这三个 SoftMax 得分向量可以省略。最终故障树形结构和工况并列结构只需SoftMax得分向量下标集为［125710]。标签创建方式如1.5节，例如：对于转速 $2 0 \mathrm { { H z } }$ ，故障为单一故障下的磨损故障的工况，则标签为[2133]。

# 3.2多SoftMax卷积神经网络结构

卷积层采用大的卷积核和大步长，池化层同样采用大的池化窗口和步长，可以减少网络层数。激活层的激活函数为 $\operatorname { M a x } ( - 1 , \mathrm { X } )$ 。为解决网络层数太深导致难以训练以及网络太浅导致特征提取不够好的问题，参考了DenseNet，在网络中加入了双路径，网络具体结构如图9所示。

![](images/9e804dd1888124ba30e8845e00bb86c396f939a5494249244ab7a1983bfe6abf.jpg)  
图9实验采用的多SoftMax卷积神经网络各层的具体参数如下表：

表2多SoftMax卷积神经网络各层参数  

<html><body><table><tr><td>层编号</td><td>层运算</td><td>算子尺寸</td><td>步长</td><td>特征图大小</td></tr><tr><td>I</td><td>输入</td><td>1</td><td>1</td><td>1280*1*2</td></tr><tr><td>C1</td><td>卷积</td><td>15*1</td><td>1*1</td><td>1280*1*48</td></tr><tr><td>P1</td><td>最大池化</td><td>6*1</td><td>4*1</td><td>321*1*48</td></tr><tr><td>C2</td><td>卷积</td><td>7*1</td><td>1*1</td><td>321*1*96</td></tr><tr><td>P2</td><td>最大池化</td><td>6*1</td><td>4*1</td><td>80*1*96</td></tr><tr><td>C3</td><td>卷积</td><td>5*1</td><td>1*1</td><td>80*1*192</td></tr><tr><td>P3</td><td>最大池化</td><td>2*1</td><td>2*1</td><td>40*1*192</td></tr><tr><td>C4</td><td>卷积</td><td>5*1</td><td>1*1</td><td>40*1*192</td></tr><tr><td>AP2</td><td>平均池化</td><td></td><td></td><td>1*1*192</td></tr><tr><td>AP1</td><td>平均池化</td><td></td><td></td><td>1*1*192</td></tr><tr><td>FC</td><td>全连接</td><td></td><td></td><td>1*1*384</td></tr><tr><td>S</td><td>多 SoftMax 输出</td><td></td><td></td><td>1*1*16</td></tr><tr><td>0</td><td>输出标签</td><td></td><td></td><td>1*1*5</td></tr></table></body></html>

# 3.3 测试一

训练时超参数设置为：当迭代次数 $\mathrm { i } { < } 7 0 0 0$ 时，学习速率为0.001，正则化系数为0.00001，mini-batch（批量数）为32，动量系数为0.9；当i$\geqslant 7 0 0 0$ 时，学习速率为0.0005，正则化系数为0.00001，mini-batch（批量数）为32，动量系数为0.9；权重初始化为高斯分布的随机数，均值为零，方差为0.1，偏置初始化为零。振动波形数据乘以10，作为输入数据。训练采用提前终止法，在21400次停止训练，训练结束并测试测试集的准确率。

每个工况采集了100个样本作为测试数据集，诊断效果采用两个指标，第一个指标是所有样本的准确率，诊断结果与给定标签完全一致，才算诊断正确，准确率为 $9 7 . 5 5 \%$ 。可见，本方法能准确诊断行星齿轮箱的复杂故障类型。

![](images/169b35684c16013d7affd31a9888204249db91ebdf1ec6e4b31cb6a17f7af02d.jpg)  
图10 测试一各节点查全率

另一种是查看树形结构图和工况并列结构中各个节点的查全率，如图10。查全率也叫召回率，其定义为某类样本中被诊断正确的比例。举例如下：对于单一故障的查全率为 $9 9 . 9 6 \%$ ，意义是符合单一故障的样本被诊断为单一故障的比例。

# 3.4 测试二

在测试1中，训练样本的工况和测试样本的工况是相同的，但在实际中，行星齿轮箱的工况复杂多变，训练样本中难以包含所有工况，所以为了检验多SoftMax卷积神经网络对载荷的泛化能力，在测试二中，将行星齿轮箱无载荷工况的振动数据作为训练样本，有载荷工况的振动数据作为测试样本。

测试二中样本标签与测试一相同，多SoftMax卷积神经网络与测试一相同。

训练时超参数设置与测试一基本相同，只是迭代次数不同而已。迭代次数到4000次，改变学习率，6000次停止训练。迭代次数明显小于测试一，说明训练难度降低。

对有载荷的每种工况提取100个测试样本，样本准确率为 $8 8 . 8 3 \%$ ，再计算各个节点的查全率，如

![](images/a6c71569171bc764e89bdb0b7058b7d0dc1aa77ff413eb59b6fbf64dfa0fa20b.jpg)  
图11所示。

测试二中，训练样本和测试样本的载荷存在差别，准确率 $8 8 . 8 3 \%$ 明显低于测试一的 $9 7 . 5 5 \%$ 。但每种工况下可以截取多个样本，例如取100个，这些样本出现次数最多的故障类型代表行星齿轮箱最终故障类型。即使单个样本是 $8 8 . 8 3 \%$ 的准确率，但行星齿轮箱故障类型出现误判的的概率也很低。

通过图11可以发现，复合故障的查全率远高于其下节点的查全率，这说明复合故障的样本基本都诊断为复合故障，但是很大一部分样本的具体故障类型诊断错了，例如诊断错误的断齿样本有很大比例诊断为磨损。这点体现了故障树形结构的优点，如果不考虑故障类型，只考虑故障有无或单一还是复合故障，查全率是很高的，最低的达到 $9 6 . 9 2 \%$ 。

# 3.5测试三

行星齿轮箱很多情况下工作在变工况下，转速会发生很大波动，所以训练工况难以包括所有转速，故需验证多SoftMax卷积神经网络对转速的泛化能力。在测试三中， $1 0 \mathrm { H z }$ 、 $1 5 \mathrm { H z }$ 和 $2 5 \mathrm { H z }$ 转频工况下的振动数据作为训练数据， $2 0 \mathrm { { H z } }$ 的振动数据作为测试数据。测试三不再包括转速得分向量。多SoftMax输出层前的网络结构和测试一相同。

训练时超参数设置与测试一基本相同，只是迭代次数不同而已。迭代次数到1500次，改变学习率，5500次停止训练。迭代次数明显小于测试一，说明训练难度降低。

训练停止后，对每种工况创建100个样本作为测试样本，测试样本准确率为 $7 6 . 3 7 \%$ ，以及测试样本的各个节点查全率如图12所示。

![](images/8feaa915f0bc5abc99de2f0c36ccdd9beab0eb89379ae931a810cb52cbbbdd7a.jpg)  
图12测试三各节点查全率

测试三的准确率明显低于测试一和测试二的准确率，说明测试三的难度很大，这表明转速对振动波形的影响远大于载荷。通过正常行星齿轮箱在不同转速下的振动波形图可以验证这点，如图13所示。计算了波形图各点幅值绝对值的平均值，结果如下：10到 $2 5 \mathrm { H z }$ 分别为0.0032,0.0056,0.0075，$0 . 0 1 2 \mathrm { m } / \mathrm { s } ^ { 2 }$ ，最大差别达到4倍。

虽然测试样本准确率为 $7 6 . 3 7 \%$ 偏低，但是在判断有无故障，及单一还是复合故障时，查全率很高，基本是 $100 \%$ 。准确率低主要是由于部分故障类型判断错误所致，如复合故障下的断齿基本识别错了，及裂纹大部分识别错了。

![](images/7283a783ee65453047a1fc1d8b00727a2d99d13314abdad424da4a6c2137a8d8.jpg)  
图11测试二各节点查全率  
图13不同转频下无故障时振动波形图

# 4结论

(1)首次提出了故障树形结构和工况并列结构，能统一处理各种复杂的故障类型和变工况，同时能查看各个节点的诊断效果。

(2)首次提出了多SoftMax卷积神经网络，能处理故障树形结构和工况并列结构。并借鉴了DenseNet网络结构，使得训练更加容易。同时激活函数采用Max(-1,X)。

(3)采用上述方法成功的诊断了实验室的行星齿轮箱各种故障类型，测试一的准确率达到$9 7 . 5 5 \%$ 。

# 参考文献

[1]雷亚国，何正嘉，等．行星齿轮箱故障诊断技术的研 究进展[J]．机械工程学报,2011,47(19):59-67. LEI Y G,HE Z J,et al.Research advances of fault diagnosis technique for planetary gearboxes[J]. Journal of Mechanical Engineering,2011,47(19) :59-67.

[2] 周泽坤．风机齿轮箱故障诊断技术研究综述[J].技术 与市场,2016,23(4):25-28. ZHOU Z K. Summary of research on fault diagnosis technology of wind turbine gearbox[J]. Technology and Market,2016,23(4) : 25-28.   
[3]邹今春，沈玉娣.变工况齿轮箱故障诊断方法综述[J]. 机械传动,2012,36(08):124-127(132). ZOU J CH，SHEN Y D. Review of gearbox fault diagnosistechniquesundervariableconditions[J]. Mechanical Drive,2012,36(08) : 124-127(132).   
[4] YU Jing，YIPL，MAKIS V. Wavelet analysis with time-synchronousaveragingofplanetarygearbox vibration data for fault detection， diagnostics，and condition based maintenance[C]/2nd International Conference on Mechanical and Electronics Engineering, August 1-3，2010，Kyoto，Japan.IEEE，2010：132-136.   
[5]程军圣，杨兴凯，等．基于ASTFA 和 SDEO 调节的行星 齿轮箱故障诊断方法[J]．噪声与振动控制，2017, 37(2) : 137-142. CHENG J S, YANG X K, et al. A method of planetary gearboxes fault diagnosis based on ASTFA and SDEO demodulation[J]. Noise and Vibration Control,2017, 37(2) : 137-142.   
[6] 黄文涛，付强，窦宏印．基于自适应优化品质因子的 共振稀疏分解方法及其在行星齿轮箱复合故障诊断中 的应用[J]．机械工程学报,2016,52(15):44-51. HUANG W T, FU Q, DOU H Y. Resonance-based sparse signal decomposition based on the quality factors optimization and itsapplication of composite fault diagnosis to planetary gearbox [J]. Journal of Mechanical Engineering,2016,52(15) : 44-51.   
[7] 李彦东，郝宗波，雷航．卷积神经网络综述[J]．计算机 应用,2016,36(9):2508-2515,2565. LI Y D,HAO Z B,LEI H. Summary of the convolutional neural network[J]. Journal of Computer Applications, 2016,37(9) : 1946-1953.   
[8] WANG J J,ZHUANG J H, DUAN L X,et al. A multi-scale convolutional neural network for featureless fault diagnosis[C]． 2016 International Symposium on Flexible Automation，Cleveland，Ohio，U.S.A.，1-3 August, 2016.   
[9] LU C, WANG ZY, ZHOU B．Intelligent fault diagnosis of rolling bearing using hierarchical convolutional network based health state classification[J].Advanced Engineering Informatics,2017, 32 : 139-151.   
10]ZHANG W, PENG G L, LI C H. Bearings fault diagnosis Daseu on convoiuuonai neurai nelworks Wiu ∠-D representation of vibration signals as input[C]. MATEC Web of Conferences 95,13001(2017).   
[11]LIU R N,MENG G T,et al.Dislocated time series convolutional neural architecture: an intelligent fault diagnosisapproachforelectricmachine[J]. IEEE Transactions on industrial informatics， 2017,13(3）: 1310-1320.   
[12] XIA M,LI T, et al. Fault diagnosis for rotating machinery usingmultiplesensorsandconvolutionalneural networks[C]. IEEE/ASME Transactions on Mechatronics, 1083-4435 (c) 2017, 1-9.   
[13] HUANG G,LIU ZHUANG,et al. Densely connected convolutionalnetworks[EB/OL]. arXiv:1608.06993v3 [cs.CV] 3 Dec 2016   
[14]LECUNY， BOTTOUL， BENGIO Y， etal. Gradient-basedlearningapplied to document recognition[J]. Proceedings of the IEEE ，1998,86(11) : 2278-2324.   
[15] KRIZHEVSKY A，SUTSKEVER I，HINTON G E. ImageNet classification with deep convolutional neural networks [C]. Proceedings of Advances in Neural Information Processing Systems. Cambridge, MA: MIT Press， 2012:1106-1114.   
[16]DENG J,DONG W,SOCHER R,et al.ImageNet:a large-scale hierarchical image database [C]. Proceedings of the 2Oo9 IEEE,Conference on Computer Vision and Pattern Recognition. Washington，DC: IEEE Computer Society, 2009: 248-255.   
[17] SIMONYANK, ZISSERMANA， Verydeep convolutional networks for large-scale image recognition [EB/OL]．arXiv:1409.1556v6 [cs.CV]10 Apr 2015.   
[18]SZEGEDYC，LIUW，JIAY， et al．Going deeper with convolutions [EB/OL].arXiv:1409.4842v1 [cs.CV] 17 Sep 2014.   
[19] HE K， ZHANG X,REN S,et al. Deep residual learning forimagerecognition[EB/OL]. arXiv:1512.03385v1 [cs.CV] 10 Dec 2015.   
[20] CLEVERT D，UNTERTHINER T,HOCHREITER S. Fast and accurate deep network learning by exponential linearunits(ELUS)[EB/OL]. arXiv:1511.07289v5 [cs.LG] 22 Feb 2016.