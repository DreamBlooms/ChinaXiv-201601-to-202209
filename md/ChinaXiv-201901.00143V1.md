# 基于改进卷积神经网络的图像超分辨率算法研究

胡晓辉，张建国

(兰州交通大学 电子与信息工程学院，兰州 730070)

摘要：针对现有卷积神经网络图像超分辨率复原算法中的映射函数容易出现过学习、损失函数的收敛性不足等问题,通过结合现有的视觉识别算法和深度学习理论对其提出改进。首先将原有 SRCNN网络层数从3层提高到13层，并提出一种自门控激活函数形式 Swish，代替以往网络模型常用的 Sigmoid、ReLU等激活函数，充分利用 Swish函数的优势，有效避免了过拟合问题，更好地去学习利用低分辨率到高分辨率图像之间的映射关系指导图像重建；然后在传统的网络损失函数中引入 Newton-Raphson 迭代法的理论，进一步加快了收敛速度。最后通过实验证明了改进的卷积神经网络模型能够有效改善图像的清晰度，并在主观的视觉效果和客观的参数评价指标上有了进一步提高。

关键词：低分辨率；超分辨率；卷积神经网络；图像处理；复原 中图分类号：TP751 doi:10.19734/j.issn.1001-3695.2018.10.0785

Research on image super-resolution algorithm based on improved convolutional neural network

Hu Xiaohui, Zhang Jianguo (School ofElectronics &Information Engineering,Lanzhou Jiaotong University,Lanzhou 73o070,China)

Abstract:Aimed at the problems of over-fitingof mapping functionand insuffcient convergenceof lossfunction in convolution neural network image super-resolution algorithm,combined existing visionrecognition algorithmand depth learning theory,this paper proposed animprovementon it.Firstly,the original SRCNN network increased layer number from3to13layers,and proposedaformofself- gatedactivation functionSwish to replace theusual network model Sigmoi, ReLUand other activation functions,and fullutilized the advantages of Swish function to effectivelyavoid Over-fiting problems,better to learn and use the mapping relationship between low-resolution and high-resolution images to guide imag reconstruction.Then introduced the Newton-Raphson methodinto the traditional network lossfunction,which further accelerates theconvergencespeed.Finallyexperiments show that theimproved network modelcan effectivelyimprove the image definition,and improve the visual effect and objective parameter evaluation index.

Key words: slow resolution; Super-Resolution; convolution neural network; image processing; recovery

# 0 引言

图像的超分辨率复原技术于20世纪60年代（super-resolution，SR）被提出，且当时被称为频谱外推法，但并未得到一致的认可。直到1984年，Tsai等人[1提出了将图像从低分辨率复原到单帧高分辨率，即可以通过信号处理的方法来处理低分辨率图像，以重建成像系统的截止频率之外的高频信息，这样可以恢复成像过程中的高频信息，实现图像的高分辨率重建，之后该研究方向开始被大量研究人员重视，现已成为一个研究热点[18\~21]。

在目前的研究领域中主要有重建，插值，学习三种方法[2]被用于图像超分辨率重建技术。基于重建方法的图像超分辨率技术使用单个或多个低分辨率（lowresolution，LR）图像来重建高分辨率（highresolution,HR）图像，该方法实质是建立观测模型之后再逆向求解最终实现重组，但该方法是一个不可逆问题且重组结果不唯一[2]，因为对于任何给定的低分辨率图像都可能存在不止一种解。插值是一种相对基本的方法，最经典的方法有双线性内插法和三次内插法，它们都是直接利用图像的先验信息，再通过建立数学模型的方式产生预知的效果，但由于图像种类繁多，该方法只对少部分图像重建效果明显，对于大多数图像的实验表明，随着所需图像放大倍率的增加，超分辨率重建效果不太理想。由于重建法和插值法存在的不足，研究人员逐渐开始关注基于学习的方法。近几年来，随着深度学习的迅猛发展，深度学习中的各类智能算法及神经网络模型被广泛应用到了图像超分辨率重组中，这些方法可以通过使用图像数据库或图像本身建立模型，设计学习策略和培训模型学习能力，主动学习或查找高分辨率图像和低分辨率图像之间的相关信息，最后，由特定功能层生成高分辨率图像。Chan等人[3]引入流形学习中局部线性嵌入法来求得重建图像加权平均值。假设HR信息和相应的LR信息具有几何相似性，先由LLE算法计算一组最优线性组合系数，再通过对样本库中的 $K$ 个最近邻样本LR块和输入LR图像块进行加权平均而获得的图像块之间的误差被最小化，该系数组直接应用于K个样本中的HR图像块，以获得高频信息。Yang 等人[4]引入稀疏编码理论[5,17]来建立LR到HR图像的完备字典，再使先验约束条件进一步稀疏，最后重建并得到SR图像。Chang等人[6提出基于稀疏编码网络的超分辨率重建方法，提出了一种基于稀疏编码网络的超分辨率重建方法，该方法将稀疏表示、映射和稀疏重构三个独立模块集成到稀疏网络中，然后通过训练该网络使得三个模块被协同优化后再重建SR图像。Wang等人[7提出了一种基于稀疏编码网络的 SR方法，该方法首先通过特征提取层获得图像的稀疏先验信息。然后，通过基于学习的迭代收缩和阈值算法建立前馈神经网络SCN，实现图像稀疏编码和解码，最后通过级联网络完成图像放大。该方法能够在更高放大倍数下提高PSNR，且算法运行速度进一步提升。Gu等人[8将卷积稀疏编码用于图像SR重建，该方法表明LR和HR滤波器学习对深度学习网络滤波器组的设计具有重要的指导意义，有助于保持图像的空间信息，提高重建效果。Dong等人[9]首次提出将卷积神经网络（convolutionalneuralnetwork，CNN）引入到超分辨率重建问题中，SRCNN包含的3个卷积层分别是图像块提取与表征、非线性映射和最后的重建，根据稀疏编码和特征学习理论，实现由LR到HR图像之间的端到端学习过程，但是研究人员发现SRCNN很难训练，它对超参数的变化非常敏感，并且只有3个卷积层，还有很多地方有待改善。Yang等人[10]提出深度边缘指导反馈残差网络的方法(DEGREE)，该方法将图像信号分解成不同的频带并重建，然后再进行组合，这样可以保留图像的重要细节信息，初步解决了SRCNN没有完全开发图像的先验信息，并且存在丢失细节信息的现象的问题。研究人员对基于卷积神经网络的图像超分辨率改进算法[12]已经有了不小的提升，但随着研究的深入仍能作出进一步的改进。本文基于Dong 等人[8提出的理论，并在原有SRCNN网络基础上进行改进。

# 1 方法与理论

# 1.1模型建立

本文采用了一个13层卷积神经网络[]并用Swish作为激活函数，首先第一层对输入图像使用

双立方插值进行预处理，使其能达到所要求的LR图像，其次由于Swish适应于局部响应归一化，在第二到第十一层充分结合Swish的优势，对LR图像进行特征提取得到LR图像块，然后第十二到十三层通过学习LR与HR图像块之间的特征映射关系来得到HR图像块，最后通过重叠和平均方法获得重建的HR图像。网络结构如图1所示。

![](images/ab30b7f4574bb08f8ff0b0650afbfd46214987b601abfe681d0ec4d0a7582972.jpg)  
Fig.1Improved SRCNN algorithm framework

# 1.2特征提取与卷积操作

经典神经网络模型中使用的激活函数是Sigmoid函数，该函数来自于神经科学理论，主要是模拟了神经元在受到刺激时接收到的电信号达到某一阈值就会产生兴奋，它有着强大的解释能力。然而，在实践中研究者们很少使用到Sigmoid函数，因为使用Sigmoid会导致网络状态出现过饱和以及梯度丢失。一旦网络神经元的活跃度在0和1处达到饱和状态，那么它在该处的梯度就会消失，这导致几乎没有信号通过该神经元或者间接通过神经元的所有信号都不能被激活。而且，从Sigmoid函数的输出图像可知其并不是以零作为中心点，这种特殊的性质导致了不以零为中心的对称信息输被送到后面的神经网络高层处理，从而在梯度下降过程中出现晃动。近年来，在深度学习中。ReLU[13]代替 Sigmoid 函数，变的越来越受欢迎，研究中常使用ReLU作为激活函数（函数表达式如式(1)所示)，因为从计算机的层面上来说，调制符号更加便于实践，而且ReLU函数的梯度只有0和1两种可能，十分简单。无论网络模型的层如何变化，其梯度都可以稳定在一个数量级上，该函数图像如图2所示。

$$
f ( x ) = \operatorname* { m a x } ( 0 , x )
$$

在实验中发现，与 sigmoid函数相比，使用ReLU作为激活函数获得的 SGD 的收敛速度比 Sigmoid 函数快得多。ReLU只需要一个阈值来获取激活值，而不需要经过大量复杂的操作。但是当一个非常大的梯度流过ReLU神经元时，在更新参数后，它将导致神经元不激活任何数据。那么这个神经元的梯度就永远都会是0，而且经过此神经元的梯度将永不被激活，数据流在不可逆的训练期间会发生关闭现象。

$$
F _ { 1 } ( x ) = ( W _ { 1 } * X + B _ { 1 } ) \times \frac { 1 } { 1 + e ^ { - \beta ( W _ { 1 } * X + B _ { 1 } ) } }
$$

![](images/09525494d32d2b2cebb9e0409a27fa1a058d350bcdfb0176a28e4f1799e6ea1b.jpg)  
图1改进 SRCNN 算法框架  
图2 ReLU函数Fig.2Relu function

于是针对ReLU函数的缺点，本文提出了一种自门控激活函数形式Swish 作为激活函数，如图3所示，在式(2)中$W _ { I }$ 是卷积核， $B _ { I }$ 是偏置向量，“\*"表示卷积操作， $W _ { l }$ 的尺寸大小为 $c \times f _ { I } \times f _ { I }$ ， $\boldsymbol { \mathscr { c } }$ 是输入图像的通道数， $\beta$ 是可训练的参数。

由于ReLU在 $\mathbf { x } < 0$ 时梯度为0，这样就导致负的梯度在这个ReLU被置零，本文改进的激活函数将大于零与小于零的数值均用Swish表示，与ReLU不同，Swish激活函数同时具备了稀疏、非单调和平滑的特性，减少了大梯度流经过时可能出现神经元不被激活的现象。当Swish函数处于 $\mathbf { x } < 0$ 时，随着 $\textbf { \em x }$ 的值不断减小，梯度无限接近零，但它不会等于0，故而不会出现神经元坏死的情况。此外，Swish是一种自动门控激活函数形式。自门控激活函数有着特殊的优势，与正常的门控需要多个标量作为输入相比，它只需要把单个的标量作为输入。该特性足以让以单个标量作为输入的激活函数ReLU轻松被自门控激活函数Swish代替，而无须再去调整参数的隐藏容量或数量。实验结果表明，当增大到一定数值后，运行结果达到了预期的效果，证实了Swish函数的实用性。

![](images/b7fbc323bba7b62383d6c2177b2461cadb81580bcab4b21dc88ea70578d85a66.jpg)  
图3Swish函数Fig.3Relu function

# 1.3非线性映射

在整个模型[14]中，第一层在网络中的作用是对每块 LR图像进行特征提取操作。第二到第十一层的作用是对提取的特征图进行非线性映射，其数学表达式由式(3)表示， $W _ { 2 }$ 是卷积核， $B _ { 2 }$ 是偏置向量。如果有 $n _ { I }$ 维向量通过了非线性映射，则就会得到 $n _ { 2 }$ 维向量，即LR特征图像块通过端到端学习理论得到了HR图像块。如果存在 $\mathrm { ~  ~ N ~ }$ 个卷积核，则在卷积之后就会产生 $\mathrm { ~ N ~ }$ 个用于重建的高分辨率图像块。

$$
F _ { 2 } ( x ) = ( W _ { 2 } * X + B _ { 2 } ) \times \frac { 1 } { 1 + e ^ { - \beta ( W _ { 2 } * X + B _ { 2 } ) } }
$$

# 1.4图像重建

式(4)中 $W _ { 3 }$ 可视为一个均值滤波器， $B _ { 3 }$ 为一个维数为 $\mathbf { \Psi } _ { c }$ 的偏置向量。在进行非线性特征映射后，可以获得HR图像块。本文通过预测重叠HR图像块，而后使用平均的方法来得到最终完整的高清图。在此过程中可以设计了一个卷积层生成最终的高分辨率图像，然而平均的方法可以看做是一个在特征图上预先定义的滤波器。

$$
F _ { 3 } \left( x \right) = W _ { 3 } \ast F _ { 2 } \left( X \right) + B _ { 3 }
$$

# 1.5 训练与优化

传统的神经网络均采用了全连接的方式，即输入层到隐藏层的神经元都是连通的，这将会产生巨大的参数量。另外，这也使得网络的训练及其耗时甚至是难以训练，而且CNN学习算法必须通过训练多层网络结构来实现最优化的网络模型。而CNN的主要思想就是通过把局部感受野，权值共享以及时间或空间亚采样这三种思想结合在一起，以获得了某种程度的位移、尺度、形变不变性来避免这一困难。一个典型的CNN 结构看起来是这样的：输入→卷积→激活函数→卷积 $$ 激活函数→池化 $$ 激活函数 $$ 卷积 $$ 激活函数→池化→全连接。

CNN学习算法需要重构误差，并不断校正前向传播与反向传播过程中的连接权值和偏置，更新网络参数，从而使得整个网络参数最优化。前向传播本质上就是特征信息的传递，这与普通神经网络的前向传播过程没有差异。当前层用 $\mathbf { \xi } _ { l }$ 表示，当前层的输出 $x ^ { l }$ 表示，当前层的权值和偏置分别用 $w ^ { l }$ 和$b ^ { l }$ 表示，则前向传播可以表示为

$$
x ^ { l } = f ( u ^ { l } ) , u ^ { l } = W ^ { l } x ^ { l - 1 } + b ^ { l }
$$

其中函数 $f ( )$ 为激活函数，本文选择Swish函数。

反向传播则是通过误差信息校正模型参数。在反向传播的过程中，要从缩小后区域的误差，还原前一层较大区域的误差，这个过程叫做upsample。CNN中损失函数有较多形式，例如均方误差损失函数和交叉熵损失函数，这些都比较常用。其目标就是求得每个单元的残差，并且每个子函数又可以分别求得其相应输出单元的残差，本文用均方误差函数作为损失函数，如式(6)所示。

$$
L o s s ( y , y ^ { \prime } ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( y _ { i } - y _ { i } ^ { \prime } ) ^ { 2 }
$$

以上的公式描述了样本 $\mathfrak { n }$ 的训练误差，其中 $y _ { i }$ 为一批样本数据中第i个数据的准确值，而 $y _ { i } ^ { \prime }$ 为CNN网络中所给出的预测值。均方误差损失函数是一种较为简单有效的用来度量平均误差的方法，均方误差损失函数能够用作评估数据的变动程度，当均方误差损失函数的值越小时，就说明该预测模型在描述训练样本时拥有更好的准确度。实验结果表明当使用Swish作为激活函数时使用均方误差损失函数具有较好预测效果。均方误差损失函数如图4所示。

![](images/c0d459d272ab5defd9f8a969d26427082cc7d60c2c22db5f8fa5b5f3f031e406.jpg)  
图4均方误差损失函数图像  
Fig.4Mean square error loss function image

最小化误差平方和问题通常通过梯度下降法来解决，梯度下降法是通过找到梯度下降最快的方向而获得训练的网络参数，梯度下降法有两种方法被广泛应用，一种是是批量梯度下降法[15]，其数学表达式如式（7）（8）所示，其中 $\alpha$ 表示步长，给定图像样本 $X$ 的样本数据集是 $X { = } \{ x _ { I } , x _ { 2 } , { \ldots } , x _ { n } \}$ ， $x ^ { i }$ 表示第i类图像的样本集，共有 $\mathrm { ~ m ~ }$ 个样本。该方法需要在更新参数时使用所有样本数据更新计算，计算精度相对提高。

$$
W _ { i } = W _ { i } - \alpha \frac { \hat { o } } { \hat { \sigma } W _ { i } } J \left( W , b \right)
$$

$$
W _ { i } = W _ { i j } - \alpha \frac { 1 } { m } \sum _ { \mathrm { i = 1 } } ^ { \mathrm { m } } \bigl [ G _ { \nu , b } \left( x ^ { i } \right) - y ^ { i } \bigr ] x ^ { i }
$$

另一种方法是随机梯度下降法[16]，其数学表达式如式(9)所示，该方法的特点是在求解梯度时只选择一个样本来求梯度，这样做可以减少训练时间。

$$
W _ { i } = W _ { i } - \alpha { \frac { 1 } { m } } { \big [ } G _ { w , b } \left( x ^ { i } \right) - y ^ { i } { \big ] } x ^ { i }
$$

本文经过多次实验发现梯度下降法在计算过程中往往会遇到局部最优解问题[15]。批量梯度下降法采用所有样本来达到梯度下降的目的，这样会导致在样本量很大的情况下使训练速度变慢，而随机梯度下降法由于每次仅采用一个样本进行迭代，训练速度较快，但因为随机梯度下降法仅抽取一个样本来决定梯度方向，这样做会造成所得到的解可能不是全局最优解。从收敛速度来考虑，随机梯度下降法一次只迭代一个样本，迭代方向变化很大，不能快速收敛到局部最优解。如何合理选择梯度计算方法是提高网络学习速率的关键所在[16]。针对批量梯度下降法和随机梯度下降法等梯度下降法的不足，最终本文另辟思路引入Newton-Raphson迭代法的概念。Newton-Raphson迭代法是二阶收敛，梯度下降是一阶收敛，所以Newton-Raphson迭代法就更快，几何上说，Newton-Raphson迭代法就是用一个二次曲面去拟合当前所处位置的局部曲面，梯度下降法使用平面来拟合当前的局部表面，通常情况下二次曲面的拟合会比平面效果更优，所以Newton-Raphson 迭代法选择的下降路径会更符合真实的最优下降路径。如图5所示。其中A表示Newton-Raphson 迭代法的迭代路径，B表示梯度下降法的迭代路径。

![](images/d9a8e0f7e3a893c656da8433e320cc6d4a363f038f31586a1958ee292b257a62.jpg)  
图5Newton-Raphson 迭代法与梯度下降法对比 Fig.5Comparison between Newton-Raphson iteration method and gradient descent method

Newton-Raphson 迭代法要比梯度下降法具有更多的全局判断能力，梯度下降法从初始点的区域开始预判，并在局部进行下降，之后步步向极值逼近，通常走的是之字型。在二阶导数的作用下，Newton-Raphson 迭代法直接搜索如何从函数的凸性到达极值点。也就是说，在选择方向时，不仅考虑当前斜率是否足够大，而且还会考虑在走了一步之后，斜率是否会变得更大。从收敛速度来看，梯度下降是线性收敛，Newton-Raphson迭代法是超线性的，至少是二阶收敛。Newton-Raphson 迭代法可以解决批梯度下降法训练速度慢，以及随机梯度下降法准确性不足问题，但对于不同的卷积神经网络还是有一定的局限性，只能通过实验结果来进行超参数调整。不过针对于以往的梯度下降法已经有了很大改进（如图6所示，原SRCNN模型采用随机梯度下降法)，它的引入使得原SRCNN网络收敛速度变快，减小了采用以往梯度下降方法时产生的较大的振荡，且学习速率得到了提高，训练时间变短。

![](images/32393ebc7b3506214f94f9b9462453a3c794ea5d44b919506443197990287921.jpg)  
图6在set6测试集上，随着迭代系数的增加,不同方法的TestLoss 曲线图

# 2 实验结果与分析

本文的评估实验在 Intel CoreTM i7-8500YCPU $@ 4 . 2 0$ GHz，GPU为NVIDIAGTX1070Ti[15]，内存为 $1 2 \mathrm { G B }$ 。实验平台搭载的操作系统为64位Ubuntu18.04.1LTS、MATLABR2016b、CUDA10.0和OpenCV3.2.0。本文选用经典双三次插值方法（BI）、深度边缘指导反馈残差网络方法(DEGREE)[10]、SRCNN 算法，改进的 SRCNN 算法进行对比测试。采用ImageNet数据库中的90幅图像进行训练，该数据集被广泛用于众多的单幅图像超分辨率方法的测试中。

为验证本文所提算法的效果，本文采用峰值信噪比（PSNR）和结构化相似度（SSIM)来评估改进的网络。PSNR是对已处理图像与原始图像之间的误差进行定量计算，PSNR的数值越大，说明失真越小。SIMM的数值越逼近于1，说明处理后的图像结构与原始图结构极为近似，表明生成的结果图像越好。

PSNR表达式计算如下：

$$
M S E = \frac { 1 } { H \times W } \sum _ { i = 1 } ^ { H } \sum _ { j = 1 } ^ { W } ( X ( i , j ) - Y ( i , j ) ) ^ { 2 }
$$

$$
P S N R = 1 0 \log _ { 1 0 } \left( \frac { ( 2 ^ { n } - 1 ) ^ { 2 } } { M S E } \right)
$$

其中： $H$ 与 $W$ 分别表示图像的高度和宽度， $n$ 为每个像素的比特值，一般取值为8。

SSIM表达式如下：

$$
S S I M ( x , y ) = \frac { ( 2 \mu _ { x } \mu _ { y } + c _ { 1 } ) ( 2 \sigma _ { x y } + c _ { 2 } ) } { ( \mu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } + c _ { 1 } ) ( \sigma _ { x } ^ { 2 } + \sigma _ { y } ^ { 2 } + c _ { 2 } ) }
$$

其中： $\mu _ { x }$ 为 $x$ 的平均值， $\mu _ { y }$ 为 $y$ 的平均值， $\sigma _ { x } ^ { 2 }$ 为 $x$ 的方差，$\sigma _ { y } ^ { 2 }$ 为 $y$ 的方差， $\sigma _ { x , y }$ 为 $x$ 与 $y$ 的协方差， $c _ { 1 } = ( k _ { 1 } L ) ^ { 2 }$ 、 $c _ { 2 } = ( k _ { 2 } L ) ^ { 2 }$ 两个变量用来维持稳定， $\textbf { \em L }$ 为像素的动态范围， $k _ { 1 } = 0 . 0 1$ 与$k _ { 2 } = 0 . 0 3$ 为默认值。

在实验中本文使用Swish 函数以及基于Newton-Raphson迭代法的误差函数与批量梯度下降法在set14测试集进行比较，将重建的高分辨率图像的平均PSNR值绘制成曲线图，其实验结果充分说明本文对SRCNN网络的改进有明显效果，如图7所示。

![](images/9e21a4e8dbf5c21e30e3a41946c67a6907a61ada7e15f2304fd6aa88d2d4b9ab.jpg)  
图7在 setl4 上不同算法的 PSNR(dB)平均值Fig.7PSNR(dB) averages of different algorithms on set14

为了更加充分地说明本文中所使用的Swish函数和基于Newton-Raphson迭代法的误差函数分别对网络有多大的改进程度，本文又分别将改进算法使用Swish函数单独与对比算法在set14测试集中进行比较以及再使用基于Newton-Raphson迭代法的误差函数单独与对比算法在set14测试集中进行比较，实验结果表明本文算法使用Swish函数和 Newton-Raphson 迭代法均使改进算法效果有所提升，如果图8、9所示，但比较图7会发现同时使用Swish函数和Newton-Raphson迭代法效果最好。

![](images/ced0ecace894718ac57048ceddbc4b1bd65dd01a16ea992053d6590c140af3ed.jpg)  
Fig.6Test set 6,the Test Loss curves of different methods are increased with the increase of iteration coefficients   
图8在 setl4上改进算法仅使用 Swish与其他算法对比的PSNR(dB)平均值  
Fig.8Improved algorithm on setl4 uses the PSNR(db) mean value of Swish compared with other algorithms

![](images/4afd73aa8a691642e4c62fa4176852916235985aaf1be99c2c4cdbafa3c01a56.jpg)  
图9在 setl4上改进算法仅使用Newton-Raphson 迭代法与其他算法对比的 PSNR(dB)平均值Fig.9Improved algorithm on setl4 uses only the Newton-Raphsoniterative method to compare the PSNR(dB) average with otheralgorithms

以上实验结果已经从PSNR平均值说明了改进算法的良好效果，为了再一次更好的说明改进后的网络相对于SRCNN网络、DEGREE网络的有效提高，本文在set5和set14测试集进行测试实验，其结果同样得到了有效提升，结果如表1所示。

表1不同图像的SSIM值  

<html><body><table><tr><td colspan="5">Table 1 SSIM values of different images</td></tr><tr><td>Image</td><td>BI</td><td>SRCNN</td><td>DEGREE</td><td>本文算法</td></tr><tr><td>Butterfly</td><td>0.8216</td><td>0.8715</td><td>0.8872</td><td>0.9052</td></tr><tr><td>Baboon</td><td>0.9256</td><td>0.9388</td><td>0.9491</td><td>0.9579</td></tr><tr><td>Baby</td><td>0.9226</td><td>0.9406</td><td>0.9497</td><td>0.9543</td></tr><tr><td>Bird</td><td>0.8896</td><td>0.9142</td><td>0.9239</td><td>0.9316</td></tr><tr><td>Pepper</td><td>0.8978</td><td>0.9102</td><td>0.9186</td><td>0.9235</td></tr><tr><td>Lenna</td><td>0.8993</td><td>0.9137</td><td>0.9205</td><td>0.9311</td></tr></table></body></html>

图10\~13使用四种算法对4幅测试图像分别进行处理，从结果中可以看出DEGREE、SRCNN和本文算法均优于传统的插值算法，说明了基于学习的重组算法有着显著优势，但本文所提出的改进算法在图像边缘有着更好更明显的效果。在图中本文分别对狒狒、辣椒、莱纳、鸟的局部进行放大，BI算法处理效果较模糊，边缘也不清晰，图11和13的辣椒局部和鸟眼晴周围效果十分不理想。SRCNN算法、DEGREE算法的实验结果相比BI算法有了提升，略微能看清细节的边缘，但与本文提出的改进算法相比较，本文算法在细节处理的地方更加清晰，边缘保持方面更加完整，图像锐度明显更强。因为改进后的算法相对于原有的SRCNN算法学习到了更加细微的高频信息，从而提高了图像的重建质量。

![](images/127bb7c2239ec040410baa609b0512f2acd1c02db79aa1fbaed6aad25c596250.jpg)  
图10不同算法对baboon 的处理结果  
Fig.l0Processing results of different algorithms for baboon

![](images/9e613bf98dd99bd50d2c1d4e7f4d1c1eea3a3531150efa17fc75e705dfe8451f.jpg)  
图11不同算法对 pepper 的处理结果

![](images/8952e2d0d4909aeda1737ac93673538a6d07e69d77a89f35a93cd8731e1dee24.jpg)  
图12不同算法对lenna 的处理结果

![](images/e554a6a4f3b02ea72104fe94c3551c26901b0d2dcd0b16040b8e5dc9c34b36e0.jpg)  
Fig.11Processing results of different algorithms for pepper   
Fig.12Processing results of different algorithms for lenna   
图13不同算法对bird 的处理结果Fig.13Processing results of different algorithms for bird

# 3 结束语

本文通过理论分析了CNN网络的学习和训练过程，并在原有网络的基础上对其使用的映射函数（ReLU）和梯度下降法来重建图像的局限性进行了解析，通过实践研究提出了新的映射函数(Swish)和损失函数，最终利用实验在标准测试集Set5和Set14上的进行验证，实验结果证明了本文改进的算法相对于其他算法有显著提升，并在主观视觉评价和客观参数量化上取得了优秀表现。

# 参考文献：

[1]孙旭，李晓光，李嘉锋，等．基于深度学习的图像超分辨率复原研究 进展[J].自动化学报,2017,43(5):697-709.(Sun Xu,Li Xiaoguang, Li Jiafeng,et al. Advances in image super-resolution restoration based onin-depth learning [J]. Journal of Automation，2017，43 (5): 697-709.)   
[2]苏衡，周杰，张志浩．超分辨率图像重建方法综述[J]．自动化学报， 2013,39(8):1201-1213.(Su Heng,Zhou Jie,Zhang Zhihao.Overview of super-resolution image reconstruction methods [J]．Journal of Automation,2013,39(8):1201-1213.)   
[3]Chan Takming,Zhang Junping,Pu Jian,et al.Neighbor embedding based super-resolution algorithm through edge detection and feature selection [J].Pattern Recognition Letters,2009,30 (5): 494-502.   
[4]Yang Jianchao,Wright J,Huang T S,et al. Image super-resolution via sparse representation [C].IEEE Trans on Image Processing,2O10,19 (11): 2861-2873.   
[5] 潘宗序，禹晶，胡少兴,等．基于多尺度结构自相似性的单幅图像超 分辨率算法[J]．自动化学报，2014,40(4):594-603.(Pan Zongxu, Yu Jing,Hu Shaoxing et al. Single image super-resolution algorithm based on self-similarity of multi-scale structure [J].Journal of Automation,2014,40(4):594_603.)   
[6]Chang Hong，Yeung D Y,Xiong Yimin. Super-resolution through neighbor embedding [C]//Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2004: 275-282.   
[7]Wang Zhaowen,Liu Ding,Yang Jianchao,et al.Deep networks for image super-resolution with sparse prior[C]//Proc of IEEE International Conference on Computer Vision．Washington DC:IEEE Computer Society,2015:370-378.   
[8]Gu Shuhang,Zuo Wangmeng,Xie Qi,et al.Convolutional sparse coding for image super-resolution[C]//Proc of IEEE International Conferenceon Computer Vision. Washington DC:IEEE Computer Society,2015:1823-1831.   
[9] Dong Chao, Chen CL, He Kaiming,et al. Image super-resolution using deep convolutional networks [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2016,38 (2): 295-307.   
[10] Yang Wenhan,Feng Jiashi,Yang Jianchao,et al.Deep edge guided recurrentresiduallearningforimagesuper-resolution[EB/OL]. (2016-07-18). https://arxiv.org/pdf/1604.08671.pdf.   
[11] Karen Simonyan，Andrew Zisserman.Very deep convolutional networksfor large-scale image recognition[EB/OL].(2015-04-10). https://arxiv.org/abs/1409.1556.   
[12]王晓明，黄凤，刘少鹏，等．改进的单幅图像的自学习超分辨率重建 方法[J/OL].计算机应用研究，2019，36（9）．htp://www.arocmag. com/article/02-2019-09-052.html.(Wang Xiaoming,Huang Feng,Liu Shaopeng,et al. Improved self-learning super-resolution reconstruction method for single image [J/OL].Applicatipn Research of Computers, 2019,36(9). htp://www.arocmag.com/article/02-2019-09-052.html.)   
[13] Xu Bing,Wang Naiyan,Chen Tianqi,et al. Empirical evaluation of rectified activations in convolutional network[EB/OL].(2015-11-27). https://arxiv.0rg/abs/1505.00853.   
[14] Nair V,Hinton G E..Rectified linear units improve restricted Boltzmann machines [C]//Proc of the 27th International Conference on International Conference on Machine Learning.201o:807-814.   
[15]刘村，李元祥，周拥军，等．基于卷积神经网络的视频图像超分辨率 重建方法[J/OL].计算机应用研究，2019，36（4). http://www.arocmag.com/article/02-2019-04-057.html .(Liu Cun，Li Yuanxiang，Zhou Yongjun,et al.Video image super-resolution reconstruction method based on convolution neural network [J/OL]. Applicatipn Research of Computers,2019,36(4). htp://www.arocmag. com/article/02-2019-04-057.html.)   
[16]肖进胜，刘恩雨，朱力,等．改进的基于卷积神经网络的图像超分辨 率算法[J]．光电学报，2017,37(3):0318011.(Xiao Jinsheng,Liu Enyu,Zhu Li,et al. Improved image super-resolution algorithm based on convolution neural network [J]. Journal of Optoelectronics,2017,37 (3): 0318011.)   
[17]李民，程建，乐翔,等．稀疏字典编码的超辨率重建[J].软件学报, 2012,23 (5):1315-1324.(Li Min,Cheng Jian,Le Xiang,et al. Super-resolution reconstruction of sparse dictionary coding [J]. Journal of Software,2012,23 (5):1315-1324.)   
[18] He Kaiming,Zhang Xiangyu,Ren Shaoqing,et al. Delving deep into rectifiers:Surpassinghuman-levelperformanceonimagenet classification [C]/Proc of IEEE Intermational Conference on Computer Vision.Washington DC:IEEE Computer Society,2015:1026-1034.   
[19] Timofte R,Agustsson E,Van Gool L,et al. Ntire 2017 challenge on single image super-resolution: Methods and results [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society, 2017: 1110-1121.   
[20] Liao Renjie,Tao Xin,Li Ruiyu,et al. Video super-resolution via deep draft-ensemble learning [C]//Proc of IEEE International Conference on Computer Vision. Washington DC:IEEE Computer Society， 2015: 531-539.   
[21] Du Bo,Xiong Wei,Wu Jia,et al.Stacked convolutional denoising auto-encoders for feature representation [J].IEEE Trans on Cybernetics, 2017,47 (4): 1017-1027.