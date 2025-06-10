# 基于改进最小分类误差准则算法的深度学习研究 以台风卫星云图为例

郑宗生，侯倩，邹国良，卢奇(上海海洋大学 信息学院，上海 201306)

摘要：针对传统基于最小分类误差准则(MCE)建立的目标函数存在样本错分类时网络出现的梯度反向问题，引入最小分类误差准则，定义带修正项的FMCE目标函数。以较高精度的交叉熵作为基函数，将FMCE作为修正函数，提出改进交叉熵目标函数CE-FMCE，使得网络在反向传播过程中提升标签类输出的概率。CE-FMCE不仅克服了传统MCE目标函数的梯度反向问题，还弥补了交叉熵函数对非标签集梯度不作区分处理的不足。分别在自建台风云图数据集和通用数据集MNIST上对CE-FMCE和MSE、交叉熵、MCE、M3CE 进行对比实验，实验结果表明CE-FMCE 优于其他目标函数。

关键词：深度学习；卷积神经网络；交叉熵；最小分类误差准则；台风等级 中图分类号：TP3 doi: 10.3969/j.issn.1001-3695.2018.04.0335

# Research on deep learning based on improved minimal classification error criterion algorithm: take typhoon satellite image as example

Zheng Zongsheng, Hou Qian, Zou Guoliang†, Lu Qi (CollegeofInformation,Shanghai Ocean University,Shanghai201306,China)

Abstract:Forthe traditionalobjective functionbasedontheminimumclasification errorcriterion (MCE),there existedthe problem of gradient inversion in the network when the sample was misclasified.This paper introduces the minimum classification errorcriterion and defines the FMCE objective function with corection term.This paper used the higher precisioncross entropyas a basis function and FMCE as acorrection function,and proposes animproved cross-entropy objective function CE-FMCE,which makes thenetwork increase the probabilityof label classoutput in the reverse propagation proces.CE-FMCE notonlyovercomes the gradient inversion problem ofthe traditional MCEobjective function, butalsocompensates forthe lackof diferentiationof the cross-entropy function for non-label set gradients.This paper compared CE-FMCEand MSE,cros-entropy,MCE,and M3CEonself-built typhoon image dataset and general dataset MNIST.The experimental results showed that CE-FMCE was superior to other objective functions.

Keywords:deep learning；convolutional neural network;cross-entropy； minimum clasification eror criterion；typhoon rating

# 0 引言

深度学习是当前流行的机器学习算法[I]，针对浅层神经网络对复杂分类问题泛化能力弱的缺点，其通过模拟人脑进行逐层学习，提取自然信息的深层抽象特征来提高泛化能力[2]。目前，深度学习在模式识别、智能视频、机器视觉等研究领域取得了一系列成果[3-6]。卷积神经网络（convolutional neuralnetworks,CNN）作为深度学习算法成功应用的模型之一，由LeCun[7]在1989 年提出。直到 2012 年在ImageNet评测问题中将错误率降低了 $9 \%$ ，CNN才在图像识别应用方面获得重大进展[8]。目前国内外研究学者对CNN的权值优化方法主要集中在选择合适的网络参数（如变尺寸卷积核[9]、参数池化[10]、Dropout置零率[I]等)；使用具有更好稀疏特性的激活函数(如 Relu、LeakyRelu、PRelu 等)。其中权值优化方法中，目标函数至关重要，目标函数作为CNN模型中重要的组成部分，其值越小表示模型的鲁棒性越好[12]。在网络的训练过程中它不仅能表示当前网络的状态，还在反向传播的梯度下降算法中提供参数的梯度。如果输出层的梯度太小，梯度经过深层网络衰减后，低层基本接受不到有效的训练信号。如何使网络权值达到最优从而提高泛化能力，其中构建目标函数成为研究的热点。

在卷积神经网络算法中，通常使用的目标函数有最小均方误差(mean square error,MSE)、交叉熵(cross entropy)等，其中MSE更适用于解决回归问题。Papoulis等人[13]认为在分类问题中MSE 估计的是后验概率，当网络的输出函数为sigmoid 时网络存在梯度消失的问题。随着CNN的发展，研究证明交叉熵损失函数较MSE平坦区域更少，使得网络更容易跳出局部最佳值[14,15]，所以对于多分类问题使用交叉熵作为目标函数能够取得更好的效果。因此，目前对于目标函数的研究，大多是针对特定的问题，在交叉熵函数的基础上引入与之相关的参数项。例如归喆针对人脸识别问题，增加个体内差异的损失函数作为正则项，使得网络学习到属于同一个人的特征向量在空间内尽可能相似[12]。但是交叉熵函数在梯度下降算法中并不对非标签维的梯度作区分处理，而是对它们作相同的训练。这就导致分类器不能很好的将标签类和最容易混淆的类区分，从而降低模型的正确率。

如果一个分类器在训练的过程中，能将标签类与最容易混淆的类别区分，那势必会降低误差率。Juang等人[6最先将最小分类误差方法(minimumclassification error,MCE)引入到浅层神经网络的训练过程中，他们提出的目标函数考虑非标签集中混淆程度最大的一个类别来降低分类的错误率但是基于最小分类误差构造的logistic目标函数存在梯度消失的问题。当深层卷积神经网络通过反向传播算法调整网络权值时，处于最顶层的目标函数一旦出现梯度饱和，将会影响网络的训练，因此传统的logistic函数并不适合直接应用到深度卷积神经网络中。为了克服梯度饱和的问题，Feng等人[17提出基于最大间隔最小分类误差（ $\mathbf { \nabla } cdot \mathbf { M } ^ { 3 } \mathbf { C E }$ ）建立目标函数，但当样本被错分类时， $\mathbf { M } ^ { 3 } \mathrm { C E }$ 出现部分非标签维所对应的梯度方向与交叉熵梯度方向相反，这将导致网络在反向传播的过程中信息不能充分训练且收敛速度降低，因此限制了其推广使用。

为了克服传统的MCE目标函数存在的梯度方向问题，本文引入最小分类误差准则，定义带修正项的目标函数FMCE，提出基于最小分类误差准则的修正交叉熵目标函数（CE-FMCE）。CE-FMCE不仅克服了传统MCE目标函数的梯度方向问题，而且弥补了交叉熵函数对非标签维的梯度不做区分处理的不足。并且将此目标函数应用于台风卫星云图自建数据集和手写字体库MNIST数据集，通过在卷积神经网络框架下进行对比实验，证明本文提出的目标函数CE-FMCE的有效性。

# 1 传统卷积神经网络

卷积神经网络是由卷积层和采样层交替组成的网络拓扑结构，在网络训练过程中包括前向传播和反向传播两个过程。对于前向传播，卷积层利用本层的卷积核与输入图像进行卷积运算，实现对输入图像隐式的特征提取；采样层则对当前输入的特征图做下采样降低图像的分辨率，减少运算量从而提高网络的收敛速度。网络在反向传播中运用残差 $\delta$ 反向传播规则[18]由输出层向输入层逐层传递，使得模型目标函数不断降低，对每个神经元的权值进行更新，从而得到网络的最佳权值。两个过程循环进行，直到目标函数达到规定阈值或达到最大迭代次数为止。残差表征网络实际输出 $y _ { t r u e }$ 与期望输出 $y _ { { p r e d } }$ 之间的误差信号，深度为 $H$ 层的网络的输出层残差可表示为

$$
\delta = \frac { \partial L ( w , b ) } { \partial z _ { H } } = \nabla _ { y _ { t r u e } } L \bullet \sigma ^ { ' } ( z )
$$

其中： $\sigma ^ { ' } ( z )$ 表示输出层函数的导数； $z _ { H }$ 表示第 $H$ 层的输入。

卷积神经网络通常采用softmax层作为网络的输出层函数。设 $z _ { j }$ 为 softmax 函数的输入，那么网络的输出层中第 $j$ 个神经元的值表示为

$$
p _ { j } = \frac { \exp { z _ { j } } } { \sum _ { i = 1 } ^ { m } \exp { z _ { i } } }
$$

其中： $m$ 表示样本类别数。

对于一个含有 $\mathrm { ~ N ~ }$ 个样本的训练集，其交叉熵函数表示为

$$
L _ { c } = - \frac { 1 } { N } \sum _ { n = 1 } ^ { N } \boldsymbol { y } _ { n } ^ { T } \log p _ { n }
$$

由于网络在训练过程中的误差是所有样本误差的总和，所以为了方便分析，这里只考虑单个样本。那么输出层残差 $\delta _ { c }$ 表示为

$$
\delta _ { c } { = } \frac { \hat { \partial } L } { \hat { \partial } z _ { j } } { = } \left\{ { p _ { j } - 1 , \begin{array} { l } { j = k } \\ { p _ { j } , \ } \end{array} } \right.
$$

其中： $j$ 表示 $p$ 中的任意一维(即输出层中第 $j$ 个神经元的值)； $k$ 表示样本标签维。根据式（4）可以看出，当所求的维度是样本标签维时，即 $j = k$ ，此时 $\delta _ { c } < 0$ ,其余维度 $\delta _ { c } > 0$ 。通过分析得知，当 $j \neq k$ 时 $\delta _ { c } = p _ { j }$ ，那么交叉熵函数在反向传播过程中对所有非标签维梯度不作区分处理，而是采用相同的方式对其进行训练。这将降低网络的收敛速度且训练精度不高。

# 2 改进MCE目标函数算法及证明

# 2.1改进MCE目标函数算法

针对传统卷积神经网络中交叉熵函数存在的问题，可以在交叉熵函数的基础上利用最小误差准则建立目标函数来优化CNN。通过定义错分类度量，将不同的非标签维采用不同的方式进行训练，从而弥补交叉熵的不足。

基于最小分类误差定义的目标函数一般为以下三个步骤：

a)对某个类别 $k$ ，定义一个判别函数 $g _ { k } ( z )$ 。

b)对类别 $k$ 中每个样本特征给定一个错分类度量 $d _ { k } ( z )$ 。

c)为 $d _ { k } ( z )$ 构建一个目标函数 $l _ { k } ( d _ { k } ( z ) )$ 。最终的目标函数定义如下：

$$
L _ { _ { M C E } } = \frac { 1 } { N } \sum _ { n = 1 } ^ { N } l _ { _ n } ( d _ { _ n } ( z _ { n } ) )
$$

传统方法在建立 $l _ { k }$ 时仅考虑 $d _ { k }$ 的影响，例如采用logistic目标函数，随着网络深度增加会出现梯度消失问题； $\mathbf { M } ^ { 3 } \mathbf { C E }$ 定义 $l _ { k } = ( 1 + d _ { k } ) ^ { 3 }$ ，当样本被错分类时只有错分类维梯度为正数，对比(4)式发现，这与交叉熵方向相反，这样不仅会造成收敛速度下降，而且使得信息不能充分训练。为了防止错误的信号传播到网络底层引起不可预测的错误，因此本文对MCE进行改进，提出目标函数FMCE。其定义过程如下：

a)对于多分类问题网络采用softmax作为输出层，所以本文采用 softmax 函数作为判别函数 $g _ { k } ( z )$ 。

b)如果一个分类器能将正确的类别与最容易错分的类别分开，那么对网络的识别率必定有所提高。所以对错分类度量$\boldsymbol { d } _ { k } ( z )$ 的定义如式(6)所示。

$$
d _ { k } ( z ) = - p _ { k } + p _ { r } = - \frac { z _ { k } } { \sum _ { i = 1 } ^ { m } \exp z _ { i } } + \frac { z _ { r } } { \sum _ { i = 1 } ^ { m } \exp z _ { i } }
$$

其中： $k$ 是样本标签类； $r$ 表示softmax函数输出中针对样本标签类最容易错判的一类。

c)当 $0 < d _ { k } < 1$ 时即模型出现错误分类，传统的MCE目标函数会增加错误信息对网络的影响，从而降低模型鲁棒性。因此本文在 $0 < d _ { k } < 1$ 时增加修正项 $\ln \sum _ { i = 1 } ^ { m } \exp z _ { i }$ 。所以对于单一样本 $l _ { n }$ 的表达式为

$$
l _ { n } = \left\{ \begin{array} { l l } { { d _ { k } + \ln \sum _ { i = 1 } ^ { m } \exp z _ { i } } } & { { 0 < d _ { k } < 1 } } \\ { { d _ { k } } } & { { - 1 < d _ { k } \leq 0 } } \end{array} \right.
$$

其中： $m$ 表示样本类别数。

那么改进后的目标函数FMCE可以表示为

$$
L _ { _ { F M } } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { N } \sum _ { n = 1 } ^ { N } ( d _ { _ k } + \ln \sum _ { i = 1 } ^ { m } \exp z _ { i } ) } & { 0 < d _ { _ k } < 1 } \\ { \displaystyle \frac { 1 } { N } \sum _ { n = 1 } ^ { N } d _ { _ k } } & { - 1 < d _ { _ k } \leq 0 } \end{array} \right.
$$

# 2.2改进MCE目标函数证明

对目标函数进行输出层残差的理论推导，证明FMCE的可行性。为了便于分析只考虑单一样本，即式(8)被简化为

$$
L _ { _ { F M } } = \left\{ \begin{array} { l l } { { d _ { _ k } + \ln \sum _ { i = 1 } ^ { m } \exp z _ { _ i } } } & { { 0 < d _ { _ k } < 1 } } \\ { { d _ { _ k } } } & { { - 1 < d _ { _ k } \leq 0 } } \end{array} \right.
$$

在梯度下降法中输出层残差 $\delta _ { { } _ { F M } }$ 为

$$
\delta _ { _ { F M } } = \frac { \hat { \mathcal { O } } L _ { M } \left( w , b \right) } { \hat { \mathcal { O } } z _ { j } } = \left\{ \begin{array} { l l } { \delta _ { 2 } + \delta _ { 3 } } & { 0 < d _ { \scriptscriptstyle k } < 1 } \\ { \delta _ { 2 } } & { - 1 < d _ { \scriptscriptstyle k } \leq 0 } \end{array} \right.
$$

其中：

$$
\delta _ { 2 } \mathrm { = } \frac { \hat { \partial } d _ { \mathbf { \varphi } _ { k } } ( \boldsymbol { z } ) } { \hat { \partial } z _ { j } } \mathrm { = } \left\{ \begin{array} { l l } { p _ { j } \left( - d _ { \mathbf { \varphi } _ { k } } - 1 \right) , } & { j = k } \\ { - p _ { j } d _ { \mathbf { \varphi } _ { k } } , } & { j \neq k \boxplus j \neq r } \\ { p _ { j } \left( - d _ { \mathbf { \varphi } _ { k } } + 1 \right) , } & { j = r } \end{array} \right.
$$

$$
\delta _ { 3 } \mathrm { = } \frac { \displaystyle \partial ( \ln \sum _ { i = 1 } ^ { m } \exp z _ { i } ) } { \displaystyle \partial z _ { j } } \mathrm { = } \frac { \exp z _ { j } } { \displaystyle \sum _ { i = 1 } ^ { m } \exp z _ { j } } \mathrm { = } p _ { j }
$$

因为残差 $\delta _ { { } _ { F M } }$ 与 $d _ { k }$ 的大小有关，所以进行分开讨论。

当 $0 < d _ { k } < 1$ 时

$$
\begin{array} { l } { \displaystyle \delta _ { F M } = \delta _ { 2 } + \delta _ { 3 } = \frac { \partial d _ { k } \left( z \right) } { \partial z _ { j } } + \frac { \hat { \mathcal { O } } ( \ln \sum _ { i = 1 } ^ { m } \exp z _ { i } ) } { \hat { \mathcal { O } } z _ { j } } } \\ { = \left\{ \begin{array} { l l } { \displaystyle - p _ { j } d _ { k } , } & { j = k } \\ { \displaystyle p _ { j } ( - d _ { k } + 1 ) , } & { j \neq k \boxplus j \neq r } \\ { \displaystyle p _ { j } ( - d _ { k } + 2 ) , } & { j = r } \end{array} \right. } \end{array}
$$

当 $- 1 < d _ { k } \le 0$ 时

$$
\delta _ { _ { F M } } = \delta _ { _ 2 } = \frac { \hat { \mathcal { O } } d _ { _ k } \left( z \right) } { \hat { \mathcal { O } } z _ { j } } = \left\{ \begin{array} { l l } { p _ { j } \left( - d _ { _ k } - 1 \right) , } & { j = k } \\ { - p _ { j } d _ { _ k } , } & { j \neq k \boxplus j \neq r } \\ { p _ { j } \left( - d _ { _ k } + 1 \right) , } & { j = r } \end{array} \right.
$$

式(11)\~(12) $\delta _ { { } _ { F M } }$ 的方向与 $d _ { k }$ 的关系可以归纳总结为表1所示。

表1目标函数梯度分析  

<html><body><table><tr><td>SFM</td><td>0<dk <1</td><td>-1<dk ≤0</td></tr><tr><td>j=k</td><td></td><td></td></tr><tr><td>j≠k且j≠r</td><td>+</td><td>+</td></tr><tr><td>j=r</td><td>+</td><td>+</td></tr></table></body></html>

因为softmax的输出可以表示后验概率，所以$p _ { k } \in [ 0 , 1 ] , p _ { r } \in [ 0 , 1 ]$ ，那么 $d _ { k } \in [ - 1 , 1 ]$ ，即当一个样本从错分类变为正确分类时， $d _ { k }$ 从1变为-1。分析表1、式（11)（12)和(4)，发现当 $0 < d _ { k } < 1$ 即样本被错分类时，本文实现了对非标签维梯度作区分处理，并且保证 $\delta _ { F M }$ 梯度方向与 $\delta _ { c }$ 一致；当 $- 1 < d _ { k } \le 0$ 即样本被正确分类时， $\delta _ { F M }$ 梯度的方向也与交叉熵一致。因此本文方法保证提升正确类输出的同时对非标签类作不同的训练，从而证明了本文提出的方法在理论层面的可行性。综上所述， $\delta _ { { } _ { F M } }$ 可以作为 $\delta _ { c }$ 的补充项，即 FMCE 可以作为交叉熵的补充来优化卷积神经网络。

因此在交叉熵的基础上引入FMCE构成目标函数CE-FMCE，最终表达式为

其中： $\scriptstyle \alpha = 1 / T , T$ 表示一个批次中样本的数量，根据实验过程中样本的大小进行取值； $L _ { c } = - \frac { 1 } { N } \sum _ { n = 1 } ^ { N } \log p _ { y n }$ 。因此CE-FMCE可以表示为

$$
L = - \frac { 1 } { N } \sum _ { n = 1 } ^ { N } y _ { n } ^ { T } \log p _ { n } + \alpha \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { N } \sum _ { n = 1 } ^ { N } ( d _ { k } + \ln \sum _ { i = 1 } ^ { m } \exp z _ { i } ) \quad 0 < d _ { k } < 1 } \\ { \displaystyle \frac { 1 } { N } \sum _ { n = 1 } ^ { N } d _ { k } \quad } & { - 1 < d _ { k } \leq 0 } \end{array} \right.
$$

# 2.3 网络结构

本文构建的卷积神经网络如图1所示。采用多层卷积层代替传统的卷积层，增强模型特征提取能力的同时降低卷积过程的计算量。通过权值共享和网络结构重组对6层神经网络进行特征学习，同时使得整个网络可以通过反向传播算法得以很好地训练并用于分类。构建模型时采用三个卷积层(C1-C3)、一个采样层(S1)和两个全连接层（F4-F5)，其中C1和C2采用32个 $5 ^ { * } 5$ 大小的卷积滤波器，步长为1；C3采用32个 $2 ^ { * } 2$ 大小的卷积核，步长同样设为1；采样层则采用大小为 $2 ^ { * } 2$ 的核对卷积后的特征图进行最大下采样，降低图像的分辨率从而提高网络的收敛速度。优化模型时选择使用Relu函数作为激活函数；在卷积层加入批归一化层来加速网络的训练，此外在全连接层使用Dropout方法来抑制模型过拟合；采用本文提出的CE-FMCE目标函数，根据样本数据集大小采用合适的参数 $\alpha$ ，在反向传播过程中使目标函数最小化从而优化网络参数。

![](images/f4add722f0c206aa68f9f07c97d5bca8869db3547d54583c9f89d9487ff633ae.jpg)  
图1模型结构

# 3 实验结果及分析

本文所有对比实验均是基于Windows 10CPUIntel Core$\mathrm { i } 5 { - } 6 5 0 0 \mathrm { M } ~ 3 { . } 2 ~ \mathrm { G H z }$ 内存为4GB，使用基于Tensorflow 的keras深度学习框架。实验部分分为两组：为了证明提出的目标函数CE-FMCE对台风等级分类的可行性，第一组实验使用自建的台风卫星云图数据集，其中批尺寸为40,则 $\scriptstyle { \alpha = 0 . 0 2 5 }$ ；为了验证CE-FMCE的普适性，第二组实验数据集采用通用数据集手写字体库 MNIST，此时 $\scriptstyle { \alpha = 0 . 0 1 }$ ，框架则与第一组实验相同都采用2.3节中的网络模型。此外，本文的两组对比实验中都采用CE-FMCE和目前被广泛使用的目标函数作对比，实验结果取得了预期的效果。

模型的精确度通过正确率检验，假设在N个样本中第 $\mathfrak { n }$ 个 样本的真实类标签为 $y _ { t r u e }$ ，预测类标签为 $y _ { { p r e d } }$ ，则模型分类

的正确率为

$$
A C C ( y _ { t r u e } , y _ { p r e d } ) = \frac { 1 } { N } \sum _ { n = 1 } ^ { N } 1 ( y _ { t r u e } = y _ { p r e d } )
$$

预测得到的类标签与真正的标签集越吻合，模型分类的正确率越大。

# 3.1基于CE-FMCE的台风等级分类

# 3.1.1数据集构建

实验数据采用日本国立情报学研究所（NationalInstituteofInformatics，NI）提供的西北太平洋 $1 9 7 8 - 2 0 1 6$ 年"Himawari1-8"卫星观测到的高时间分辨率卫星云图资料及对应的台风强度信息。数据集包含近1000多个台风过程。为了获取全天候的数据，实验采用了红外云图作为数据样本，依据日本气象台提供的台风等级标准制定4类台风等级标签，如表2所示。

表2台风等级标准  

<html><body><table><tr><td>台风等级</td><td>最大风速/kt</td><td>最大风速/m/s</td></tr><tr><td>热带低气压</td><td><34</td><td><17</td></tr><tr><td>台风</td><td>≥34~<64</td><td>≥ 17~<33</td></tr><tr><td>强台风</td><td>≥64~<85</td><td>≥ 33~<44</td></tr><tr><td>超强台风</td><td>≥ 85<105</td><td>≥ 44~<54</td></tr></table></body></html>

本文将采集到的红外云图首先采用中值滤波器去除云图斑块中的噪声，有效保留图像中的边缘信息；其次采用插值缩放将云图分辨率转为 $2 4 ^ { * } 2 4$ ；最后根据表2制定数据集标签，并且将台风云图转换为 $2 4 ^ { * } 2 4 ^ { * } 1$ 的格式作为模型的输入。最终构建了4000训练样本、800 测试样本的数据集，热带低气压、台风、强台风、超强台风训练集各1000个、测试集各200个，部分卫星云图样本如图2所示。

![](images/e0897809386c07d0c2283c756d3fa18ba7b535a63a022f01a83af27fd9d6edda.jpg)  
图2部分气象卫星云图样本（a、b、c、d分别代表热带低气压、台风、强台风、超强台风)

# 3.1.2结果对比

第一组实验中，将本文提出的目标函数与均方差、交叉熵函数进行对比，对模型迭代200次网络的正确率如图3所示。

![](images/3c91e5034c63fec7fc9f859b66e50993aa3f376db074ee1143c127ad1f6b3e52.jpg)  
图3不同目标函数训练结果

对比图3可以发现，在现有样本的基础上，交叉熵目标函数对网络的优化效果较均方差有一定的提高，在迭代200次网络的正确率为 $9 6 . 2 5 \%$ 。CE-FMCE较其他的目标函数能取得更好的效果，网络正确率达到 $9 8 . 0 \%$ ，并且CE-FMCE收敛速度最快，均方差和交叉熵的收敛效果表现都不理想。

将本文提出的目标函数CE-FMCE与目前被广泛使用的多分类目标函数在训练集和测试集做对比实验，结果如表3所示。

表3不同目标函数的模型正确率  

<html><body><table><tr><td>目标函数</td><td>训练集/%</td><td>测试集/%</td></tr><tr><td>MCE</td><td>92</td><td>78.12</td></tr><tr><td>均方差</td><td>95.4</td><td>82.0</td></tr><tr><td>交叉熵</td><td>96.25</td><td>83.38</td></tr><tr><td>M³CE[17]</td><td>97.0</td><td>84.59</td></tr><tr><td>CE-FMCE</td><td>98.0</td><td>86.78</td></tr></table></body></html>

对比表3发现均方差目标函数在训练集和测试集的正确率分别为 $9 5 . 4 \%$ 和 $8 2 . 0 \%$ ；交叉熵目标函数在测试集的准确达到$8 3 . 3 8 \%$ ；文献[17]设计的 $\mathbf { M } ^ { 3 } \mathbf { C E }$ 目标函数在训练集和测试集的正确率都有一定的提升，训练集正确率为 $9 7 . 0 \%$ ，测试集正确率达到 $84 . 5 9 \%$ ，比交叉熵目标函数提升 $1 . 2 1 \%$ 。本文设计的目标函数CE-FMCE，在模型迭代200次后训练集正确率为 $9 8 . 0 \%$ 测试集正确率达到 $8 6 . 7 8 \%$ ，比交叉熵函数在训练集高出 $1 . 7 5 \%$ 测试集高出 $3 . 4 \%$ 。CE-FMCE在理论上修正了文献[17]提出的$\mathbf { M } ^ { 3 } \mathbf { C E }$ 在错分类时出现梯度反向的问题，表3也很好地验证了本文的改进，相比于 $\mathbf { M } ^ { 3 } \mathbf { C E }$ 测试集的正确率提高了 $2 . 1 9 \%$ ，这也充分证明了CE-FMCE的可行性。

# 3.2基于CE-FMCE的MNIST数据集对比实验

为了验证本文提出的目标函数CE-FMCE的普适性，第二组实验数据采用通用数据集手写字体库 MNIST。MNIST 数据集包含0\~9共10类手写数字，如图4所示。其中包含42000个训练样本，10000个测试样本，图像分辨率为 $2 8 ^ { * } 2 8$ ，部分样本数据如图4所示。

![](images/6942fde88e77edc35845fa2ebbc81ed4a872d4149421f9d91a6b80e7e26b2a4c.jpg)  
图4MNIST数据集部分样本

第二组实验将CE-FMCE与其他的目标函数在MNIST数据集进行验证。网络采用与第一组实验相同的模型，将MNIST数据集中的样本转换为 $2 8 ^ { * } 2 8 ^ { * } 1$ 的格式作为网络的输入，对模型设置迭代次数100次，实验结果如表4所示。

表4不同目标函数的模型正确率  

<html><body><table><tr><td>目标函数</td><td>训练集/%</td><td>测试集/%</td></tr><tr><td>MCE</td><td>99.69</td><td>98.90</td></tr><tr><td>均方差</td><td>99.25</td><td>98.35</td></tr><tr><td>交叉熵</td><td>99.79</td><td>98.99</td></tr><tr><td>M3CE[17]</td><td>99.86</td><td>99.06</td></tr><tr><td>CE-FMCE</td><td>99.92</td><td>99.11</td></tr></table></body></html>

从表4可以看出，CE-FMCE的训练集正确率为 $9 9 . 9 2 \%$ 测试集正确率达到 $9 9 . 1 1 \%$ ，较 $\mathbf { M } ^ { 3 } \mathbf { C E }$ 测试集正确率提升了$0 . 0 5 \%$ ，且表现能力优于其他目标函数，但是相对于其他的多分类目标函数，模型的正确率的提升并不大。分析原因在于MNIST数据集的数字噪声干扰少、识别难度低，所以基准正确率比较高，提升不太明显。

对比表3和4发现，CE-FMCE对特征复杂的图像样本，模型正确率提升效果明显。

# 4 结束语

深度学习通过构建深层非线性网络实现复杂函数的逼近来表达自然图像的深层抽象特征，克服传统浅层神经网络对复杂分类问题泛化能力弱的问题。目前针对深度学习网络的研究大多集中在优化网络参数，目标函数作为深度学习算法的重要组成部分不仅表征当前网络的状态，还在网络的梯度下降法中提供参数梯度。因此，本文对目标函数展开研究，针对传统基于MCE建立的目标函数在网络中存在的梯度问题，提出基于MCE的修正交叉熵目标函数CE-FMCE；并且在自建台风云图数据集和通用数据集手写字体库MNIST，将CE-FMCE与目前被广泛应用于多分类问题的目标函数MSE、交叉熵、MCE和$\mathbf { M } ^ { 3 } \mathbf { C E }$ 进行对比实验，达到了预期的效果，充分证明本文方法的可行性，为今后的研究提供一种新的思路。

基于改进最小分类误差准则的深度学习算法，将非标签集中的梯度作区分处理导致批运行时间长，同时对特征简单的样本集的识别精度提高并不明显。因此，下一步研究并行化提高效率和进一步优化。

# 参考文献：

[1]LeCun Y,Bengio Y,Hinton G.Deep learning [J].Nature,2015,521 (7553): 436-444.   
[2]Zeiler M D,Fergus R.Visualizing and understanding convolutional networks [C]//Proc of European Conference on Computer Vision. Cham: Springer,2014: 818-833.   
[3]LeCun Y,Bottou L,Bengio Y,et al. Gradient-based learning applied to document recognition [J].Proceedings of the IEEE，1998,86 (11): 2278-2324.   
[4]Xiao Jianxiong,Hays J,Ehinger K A,et al. SUN database:large-scale scene recognition from abbey to zoo [C]// Proc of IEEE Computer Vision and Pattern Recognition.2010: 3485-3492.   
[5]黄凯奇，任伟强，谭铁牛，等 图像物体分类与检测算法综述[J].计算 机学报,2014,37(6):1225-1240.(Huang Kaiqi,Ren Weiqiang,Tan Tieniu. Areview on image object classification and detection [J].Chinese Journal of Computers,2014,37(6): 1225-1240.)   
[6] 何希平，张琼华，刘波．基于 HOG 的目标分类特征深度学习模型[J]. 计算机工程,2016,42 (12):176-180.(He Xiping,Zhang Qionghua, Liu Bo.Deep learning model of target classification features based on HOG [J].

Computer Engineering,2016,42(12):176-80.)

[7]LeCun Y. Generalization and network design strategies [C]// Proc of Connectionism in Perspective.1989.   
[8]Krizhevsky A,Sutskever I,Hinton G E. ImageNet classification with deep convolutional neural networks $[ \mathrm { C } ] / \hbar$ Proc of International Conference on Neural Information Processng Systems.[S.1.]:Curran Associates Inc, 2012:1097-1105.   
[9]余礼杨，范春晓．一种改进的多尺度核卷积目标跟踪算法[J].计算机 应用，2015,(Xu Liyang,Fan Chun xiao.Multi-scale tracker based on improved kernel correlation filter [J].Journal of Computer Application. 2015.)   
[10]贾涛，周利莉，陈健，等.基于卷积神经网络的PCBCT图像中的过孔 和焊盘检测算法 [J]．计算机应用研究,2018,35(2):637-640.(Jia Tao, ZhouLili,Chen Jian,et al.Via and pad detection inPCB CT imagesbased on convolutional neural network [J].Application Research of Computer, 2018,35 (2): 637-640.).   
[11] Finn C,Hendricks L A,Darrell T.Learning compact convolutional neural networks with nested dropout [J].Eprint Arxiv,2015,

[12]归喆．基于深度学习的人脸特征提取与匹配[D]；成都：电子科技大

学,2016.(Gui Zhe.Facial feature extraction and matching based on deep learning [D].Chengdu:University of Electronic Science and Technology of China, 2016.)   
[13] Papoulis A,Saunders H.Probability,random variables and stochastic processes (2nd edition) [J].A Papoulis,1989,33(6):1637-1637.   
[14] Krizhevsky A, Sutskever I, Hinton G E. ImageNet classification with deep convolutional neural networks [C]//Proc of International Conference on Neural Information Processing Systems.[S.1.] :Curran Associates Inc, 2012:1097-1105.   
[15] Szegedy C,Wei Liu,Jia Yangqing,et al.Going deeper with convolutions [C]//Proc of IEEE Computer Vision and Pattern Recognition.2015: 1-9.   
[16] Juang B H,Katagiri S.Discriminative learning for minimum error classification [patern recognition] [J].IEEE Trans on Signal Processing, 1992,40 (12): 3043-54.   
[17]Feng Ziyong,Sun Zenghui, Jin Lianwen.Learning deep neural network using max-margin minimum classification error [C]// Proc of IEEE International Conference on Acoustics，Speech and Signal Processing., 2016.   
[18]Bouvrie J.Notes on convolutional neural networks [J].Neural Nets,2006.