# 基于局部感受野扩张D-MobileNet模型的图像分类方法

王威，邹婷，王新(长沙理工大学 计算机与通信工程学院，长沙 410114)

摘要：针对轻量级的深度神经网络 MobileNet 会减少分类准确率的问题，将空洞卷积核引入MobileNet 模型中的某一卷积层中，提出一种基于局部感受野扩张的D-MobileNet模型。模型根据空洞卷积核所在位置的不同分为三种结构，在不增加参数数量的同时能够扩大该层卷积核的局部感受野，提高分类精度。实验在Caltech-101数据集、Caltech-256数据集以及图宾根大学动物分类数据库上进行，结果表明，D-MobileNet模型可获得比 MobileNet 更好的分类准确率，最多可以提高 $2 \%$ 。

关键词：图像分类；深度神经网络；MobileNet；空洞卷积；D-MobileNet 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.10.0781

# Image classification method based onD-MobileNet model

Wang Wei, Zou Ting, Wang Xin† (SchoolofComputer&CommunicationEngineering,Changsha UniversityofScience&Technology,Changsha 410114, China)

Abstract: Aiming at the problem that lightweight deep neural network MobileNet can reduce clasification acuracy,this paper proposed an D-MobileNet(dilatedconvolution MobileNet）model based on local receptive field expansion by introducing dilated convolution kernel intoaconvolution layerof MobileNet model.The modelsconsistedof three structures acording tothelocationofthe dilated convolution kernel. Without increasing the number of parameters,itcould expand the localreceptive fieldof the layer convolution kerneland improve theclasification acuracy.This papercarried out the experiments on Caltech-1O1 database,Caltech-256 database and Uebingen animals with atributes database.The results show thatthe D-MobileNet model canachieve beterclasification accuracy thanthatof MobileNet,andcanimprove the classification accuracy by up to $2 \%$ ：

Key words: image classification; dep neural networks; MobileNet; dilated convolution; D-MobileNet

# 0 引言

计算机图像分类利用计算机对图像进行分析，把图像归为若干类别中的某一类别，来代替人的视觉判读，是计算机视觉领域的研究热点之一。大多数图像分类的研究主要集中在图像特征提取和分类算法上面，特征的好坏对分类非常关键，而传统的图像特征如SIFT、HOG等特征都是经过手工设计的，因此有时难以满足要求。卷积神经网络具有自学习、自适应和自组织能力，能利用已知类别的图像样本集的先验知识，自动提取特征，可避免传统图像分类方法中复杂的特征提取的过程，提取到的特征表达能力强，分类效率高。

深度卷积神经网络在计算机视觉领域，如图像分类[]目标追踪[2]、目标检测[3]，以及图像分割[4]等方面都取得了很好的效果。如Krizhevsky等人在2012年ImageNet大规模视觉识别挑战分类任务使用约有6000万参数8层的AlexNet[1]模型取得了冠军，Simonyan 等人使用的16 层的VGG[5]、以Inception 为基本结构的GoogleNet[6]、为改善梯度消失问题引入残差结构的ResNet[7]等也都取得了成功。但由于深度卷积神经网络模型本身是一种结构密集型和计算密集型的模型，庞大的参数数量和计算量、大量的内存访问和CPU/GPU 资源计算导致的巨大的耗电量使得模型难以应用到硬件资源有

限的便携式移动设备上。

针对上述问题的一种可行的解决方案是对深度神经网络进行压缩与加速。在尽量不影响精度的前提下，减少网络参数和计算量，减少耗电，使完整的深度神经网络能应用到一些有实时性要求和低内存的便携式设备中。Denil等人[8]证明了深度神经网络中的参数存在大量的冗余，且这些冗余的参数对分类精度并没有很大的影响。Denton等人[9]通过SVD 奇异值矩阵分解找到一个合适的低秩矩阵来估计深层CNNs的信息参数，该方法需要较多的计算成本，也需要大量的重新训练来达到收敛。Han等人[10]通过参数剪枝将训练好的网络中不重要的连接删除，对剩下的参数再进行训练和量化，然后对量化后的参数进行霍夫曼编码，进一步降低压缩率，该方法需手动调超参数。Hinton 等人[I]采用知识精馏的方法对网络模型进行压缩，将一个性能好但存在较多冗余的复杂网络中有用信息提取出来迁移到一个更小更简单的网络上，使简单网络与复杂网络有相近的性能。除此之外，很多相关研究通过改进网络模型来压缩网络。SqueezeNet[12]是以 firemodule 为基础结构的网络模型、MobileNets[13]是以深度可分离卷积核（depthwise separable filters）为基本结构的网络模型、ShuffleNet[4]的基本结构是在残差结构的基础上进行改进，引入了分组逐点卷积（group pointwise convolution）和通道重排（channel shuffle）操作。

轻量级网络虽然参数或计算量减少了，但是分类准确率也有相应的下降。为了减少计算量同时又兼顾分类精度，本文提出一种基于局部感受野扩张的D-MobileNet 网络结构，将空洞卷积核引入到MobileNet网络中，利用空洞卷积核在不增加参数的前提下可增大卷积核感受野这一优点，获取更大的局部感受野，提高MobileNet的分类精度。

# 1 卷积神经网络基本理论

# 1.1 卷积神经网络

作为一种自动化特征提取的机器学习模型，卷积神经网络是最早应用于各个领域的深度学习网络模型。卷积神经网络通过局部感受野和权值共享减少权值的数量，降低网络模型的复杂度，从而避免一般深度学习模型中由于参数过多而引起的过拟合问题。与此同时，卷积神经网络可将图像直接作为网络的输入，避免传统图像分类方法中复杂的特征提取过程，并且对图像平移、比例缩放等具有高度不变性。

卷积神经网络一般由卷积层、池化层和全连接层组成，如图1所示。图像经一层或多层卷积层和池化层进行特征提取，将最后一层卷积层输出的所有特征图转换成一维向量进行全连接，最后利用分类器进行分类。网络通过反向传播调节权重参数，并利用分类的结果与期望输出的结果之间的平方差达到最小这一目标进行优化。卷积神经网络每层的神经元按宽度、高度以及深度三维排列，其中宽度和高度指神经元尺寸的大小，而深度指输入图片的通道数或输入特征图的数量。

![](images/000e00d27614f8e696ffceac2de7e1db98b815d72fa88202a2053557b2eb25f4.jpg)  
图1 卷积神经网络基本结构示意图

卷积层通过卷积运算来提取图像中不同的特征，该层包含若干组可学习的参数(卷积核)，是整个卷积网络的核心。当前层的卷积核对输入的特征图像进行卷积运算，可提取局部特征，得到特征图，再经过激活函数进行非线性操作，可得到非线性的特征映射图像。卷积神经网络的局部感受野和权值共享思想在卷积层中体现，网络中大部分的计算量也集中在卷积层。

卷积层之后为池化层，也叫下采样层。该层通过下采样操作，在一定大小的区域内，用一个特定的值作为输出，并通过去掉特征映射图中不重要的样本点来降低下一层输入维度，进一步减少运算量，增加网络对图像平移、旋转等变化的适应性。常见的池化操作有最大池化和平均池化。

卷积层 $^ +$ 池化层的结构可提高网络的鲁棒性，卷积神经网络通过多层卷积层可得到更深层次特征图。随着层数增加，学到的特征也越全局化。最后学习到的全局特征映射转换成向量连接全连接层，再连接分类层。网络中大部分的参数量在全连接层。

# 1.2MobileNet模型

MobileNet是一种流线型的架构，它使用深度可分离的卷积来构建轻量级的深度神经网络，为移动和嵌入式视觉应用提供的一种高效模型[13]。MobileNet的基本结构为深度可分离卷积核（Depthwise SeparableFilters），如图2所示。

![](images/7929a659c617c2f8f0624df7b1157e47455a831f5e4dd926c7b399017d09233f.jpg)  
图2 MobileNet 网络结构图

Fig.2Architecture of mobilrnet

深度可分离卷积核由深度卷积核(depthwise convolutionfilter)和点卷积核(pointconvolution filter)组成，其中深度卷积核在每个输入通道上进行单个卷积，点卷积核用一个 $^ { 1 \times I }$ 的卷积将深度卷积的输出值进行线性组合。这样， $N$ 个$D _ { K } \times D _ { K } \times M$ 的标准卷积核（图3(a)）可以由M个 $D _ { K } \times D _ { K } \times I$ 的深度卷积核（图3(b)）和N个 $\pmb { I } { \times } \pmb { I } { \times } \pmb { M }$ 的点卷积核（图3(c))替代。一个标准的卷积滤波器是将输入组合成一组新的输出，而深度可分离卷积将输入分为两层，一层用于过滤，另一层用于合并。

![](images/63eebb9ee7271876262a5e795c2e7d00ae8e299066e59ac65699fc77eb78bb9f.jpg)  
Fig.1Basic structure of convolution neural network   
图3 标准卷积核和深度可分离卷积核  
Fig.3 Standard convolutional filters and depthwise separable filters

# 2 D-MobileNet模型

标准的MobileNet模型一直都采用 $3 { \times } 3$ 的小尺寸卷积核。这样虽然可以减少计算量，但是在前几层特征图分辨率较高的情况下，小尺寸的卷积核的局部感受野太小，捕捉不到好的特征。若换成较大的卷积核，则又会增加参数数量和计算量。因此，可以考虑在前面几层卷积层中，用扩张率为2的空洞卷积代替标准卷积。这个模型称为扩张卷积MobileNet模型，即D-MobileNet模型。

# 2.1空洞卷积

空洞卷积核 [15] （dilatedconvlution）又叫做带孔卷积核，是在上采样滤波器非零值中间插入零值的一种卷积核。空洞卷积最先应用在图像分割中。图像分割需要得到与原输入图片相同尺寸的图片，而传统的深度神经网络中池化层会减少特征图的空间分辨率。为了生成有效的密集特征图，Chen 等人将全卷积神经网络去掉后面几层最大池化层，同时，为了取得相同大小的感受野而引入空洞卷积。这样既能避免池化层减少特征映射图空间分辨率，还能与池化层一样增加感受野[]

带孔卷积核就是通过在卷积核中非零数值中间插入零值扩大该卷积核的感受野，如图4所示。其中，(a)表示标准的$3 { \times } 3$ 卷积核的感受野，(b)表示扩张率为2时不加填充时 $3 { \times } 3$ 卷积核的感受野为 $5 { \times } 5$ ，(c)表示扩张率为3时不加填充时 $3 { \times } 3$ 卷积核的感受野为 $7 { \times } 7$ 。由此可见，空洞卷积可扩大卷积核的感受野，且不会增加卷积核的参数数量。

![](images/b105c4472ae335d5c73b0381598b809d7d0cb012b2544e18accdd0993ec58c60.jpg)  
Fig.4Schematic diagram of dilated convolutional filter

# 2.2 D-MobileNet模型

感受野是指卷积神经网络每一层输出的特征图中每个元素在输入图像上映射的区域大小。层数越往后，感受野区域越大，越接近全局感受野。本文通过扩张局部感受野来提高MobileNet的分类精度，所以增加感受野的层数应靠近输入层。根据空洞卷积核所在位置的不同，提出了三种改进的网络模型，分别为D1-MobileNet、D2-MobileNet以及D3-MobileNet。

![](images/fdac4cf0624183ab0a2748e8aef656befb47f8ff761bfbe62051a9e0c2e25670.jpg)  
图4 空洞卷积核示意图

a）D1-MobileNet。D1-MobileNe 将MobileNet 的第一层卷积层步长设置为1，并使用扩张率为2的空洞卷积核代替标准的卷积核。同时，为了增加最少的计算量，将第二层深度可分离卷积层中的深度卷积层步长设置为2，其他层不变。这样，与MobileNet相比较，由于第一层的卷积步长设置为了1，第一层卷积层输出的特征图大小由 $1 1 2 \times 1 1 2$ 变为$2 2 4 \times 2 2 4$ ，如图5所示。

b)D2-MobileNet。在MobileNet的第二层深度可分离卷积层的深度卷积层中，用扩张率为2的空洞卷积核代替标准的卷积核，其他层不变。该方法不增加任何计算量和参数数量，也不改变任何一层的输出特征图大小，如图6所示。

![](images/0ae3dc4098ef5692c075c11bb16455420c303f35ec103da39cb8bead65089fe0.jpg)  
Fig.5Architecture of D1-mobilenet   
图6 D2-MobileNet网络结构图  
Fig.6Architecture of D2-mobilenet

c)D3-MobileNet将MobileNet的第一层卷积层步长设置为1，用扩张率为2的空洞卷积核代替标准的卷积核，并在第一层的批次规范化层[16](Batch Normalization)后加入步长为2的池化层，其他层不变，如图7所示。

![](images/c94289c5f927ecd39ceeeb8e3f8ede3e24133875bf7f079c37c27930bddcbcf2.jpg)  
图5 D1-MobileNet 网络结构图  
图7 D3-MobileNet网络结构图  
Fig.7Architecture of D3-mobilenet

# 2.3 D-MobileNet性能分析

对于一个标准的卷积层，假设输入 $R ^ { h \times w \times m }$ 的特征图 $\boldsymbol { { \cal I } }$ ，其中 $h , \ w , \ m$ 分别代表特征图的高、宽和输入特征图的通道数。$\boldsymbol { { I } }$ 与 $R ^ { s \times s \times m \times n }$ （ $\mathbf { \sigma } _ { s }$ 代表卷积核的尺寸， $\textbf { \em n }$ 代表输出特征图的通道数）的卷积核 $\pmb { K }$ 进行无填充的卷积操作，可得到 $R ^ { ( h - s + 1 ) \times ( w - s + 1 ) \times n }$ 的输出特征图 $o$ ， $\scriptstyle O = K ^ { * } I$ 。

$$
O ( y , x , j ) = \sum _ { i = 1 } ^ { m } \sum _ { u , \nu = 1 } ^ { s } K ( u , \nu , i , j ) I ( y + u - 1 , x + \nu - 1 , i )
$$

其中： $O ( y , x , j )$ 代表第 $j$ 个特征图中点 $( y , x )$ 的值， $K ( u , \nu , i , j )$ 代表第 $j$ 个卷积核中第 $i$ 个通道上点 $( u , \nu )$ 上的值， $I ( y , x , i )$ 代表第 $i$ 个输入通道上点 $( y , x )$ 的值。由式 $( 1 )$ 可知，得到一个输出需要 $s \times s \times m$ 次乘法运算，则总计算量为$s \times s \times m \times ( h - s + 1 ) \times ( w - s + 1 ) \times n$ ，总的参数数量为 $s \times s \times m \times n$ 。

D-MobileNet在标准卷积层引入空洞卷积核，输入同样的特征图 $\boldsymbol { { \cal I } }$ ，用扩张率为 $\textbf { \em r }$ 同尺寸大小的卷积核 $\pmb { K }$ 进行的无填充的空洞卷积操作，可得到 $R ^ { ( h - s - ( s - 1 ) ( r - 1 ) + 1 ) \times ( w - s - ( s - 1 ) ( r - 1 ) + 1 ) \times n }$ 的输出特征图 $O _ { d }$ 。

$$
\begin{array} { l } { { \displaystyle O _ { d } ( y , x , j ) = \sum _ { i = 1 } ^ { m } \sum _ { u , \nu = 1 } ^ { s } K ( u , \nu , i , j ) \nonumber } } \\ { { \displaystyle I ( y + u + ( u - 1 ) ( r - 1 ) - 1 , x + \nu + ( \nu - 1 ) ( r - 1 ) - 1 , i ) } } \end{array}
$$

由式(2)可知，空洞卷积层的总计算量为$s \times s \times m \times ( h - s - ( s - 1 ) ( r - 1 ) + 1 ) \times ( w - s - ( s - 1 ) ( r - 1 ) + 1 ) \times n$ ，参数数量为 $s \times s \times m \times n$ 。在无填充的卷积操作条件下，扩张率 $r > 1$ 的空洞卷积的计算量要小于标准的卷积，参数数量一样，但空洞卷积的感受野比标准卷积大；在有填充的卷积操作条件下，输出特征图尺寸均为 $R ^ { h \times w \times n }$ ，两者的计算量和参数数量都一样。

D-MobileNet在深度可分离卷积层引入空洞卷积核，输入特征图经过深度卷积层得到 $\scriptstyle O _ { d c }$ ，再经过点卷积层，最后可得到 $R ^ { ( h - s - ( s - 1 ) ( r - 1 ) + 1 ) \times ( w - s - ( s - 1 ) ( r - 1 ) + 1 ) \times n }$ 的输出特征图 $o$ 。

$$
\begin{array} { l } { \displaystyle { \cal O } _ { d c } ( y , x , j ) = \sum _ { u , v = 1 } ^ { s } K ( u , \nu , j ) } \\ { \displaystyle ~ * I ( y + u + ( u - 1 ) ( r - 1 ) - 1 , x + \nu + ( \nu - 1 ) ( r - 1 ) - 1 , j ) } \end{array}
$$

其中： $O _ { d c } ( y , x , j )$ 代表第 $j$ 个特征图中点 $( y , x )$ 的值， $K ( u , \nu , j )$ 代表第 $j$ 个卷积核上点 $( u , \nu )$ 的值， $I ( y , x , j )$ 代表第 $j$ 个输入通道上点(y,x)的值。深度可分离卷积的总计算量为$( s \times s + n ) \times ( h - s - ( s - 1 ) ( r - 1 ) + 1 ) \times ( w - s - ( s - 1 ) ( r - 1 ) + 1 ) \times m$ ，总的参数数量为 $s \times s \times m + m \times n$ 。由此可见，深度可分离卷积层相对于标准卷积层，参数减少量为

$$
\frac { s \times s \times m + m \times n } { s \times s \times m \times n } = \frac { 1 } { n } + \frac { 1 } { s ^ { 2 } }
$$

计算量减少为

$$
\frac { ( s \times s + n ) \times ( h - s - ( s - 1 ) ( r - 1 ) + 1 ) \times ( w - s - ( s - 1 ) ( r - 1 ) + 1 ) } { s \times s \times n \times ( h - s + 1 ) \times ( w - s + 1 ) }
$$

同理，在进行有填充的深度可分离空洞卷积时，计算量减少为

$$
\frac { ( s \times s + n ) \times m \times h \times w } { s \times s \times m \times n \times h \times w } = \frac { 1 } { n } + \frac { 1 } { s ^ { 2 } }
$$

由式(2)和 (3)的输出特征图尺寸可知，扩张率为 $\textbf { \textit { r } }$ 卷积核大小为 $s { \times } s$ 的深度卷积核 $\pmb { K }$ 的感受野相当于卷积核$( r \times s - r + 1 ) \times ( w \times s - r + 1 )$ 的感受野，可达到扩大感受野的目的，而且不会增加参数量和计算量

# 3 实验及结果分析

实验采用 TensorFlow 框架下的Python 语言，模型在配有 NVIDIATITANGPU的服务器上实现。实验采用RMSprop优化算法进行优化。RMSprop 是一种自适应学习率方法，可调整学习率，初始学习率为0.1。根据数据集训练样本数量的不同，本文设置不同的epoch 数来降低学习率。权重初始化采用Xavier初始化方法，该方法可根据每层输入个数和输出个数来决定参数随机初始化分布范围，是一种均匀分布，偏差初始值全为零。实验共训练5万批次，每批样本数为64，均采用ReLU作为激活函数。为了证明D-MobileNet模型的有效性，实验将D-MobileNet模型与MobileNet模型在Caltech-101[22]、图宾根大学动物分类数据库和Caltech-256[23]数据集上的分类结果进行比较。

# 3.1 Clatech-101数据集

Caltech-101数据集总共有9145张图像，共102类。其中包含101个物体类别和一个背景类，每类图像的数量在40\~800个，图8为Caltech-101数据集中的图片事例。在网络训练时，首先将数据集中的图片进行标签，然后充分打乱，随机选取其中的1500张图片作为测试集，剩余的图片作为训练集训练网络。

![](images/60a178af82d8fd1fc2ca080bd1e516d126f364ea9a44a9c466f756d241710149.jpg)  
Fig.8Picture instances in the Caltech-1O1 dataset

# 3.2Clatech-256 数据集

Caltech-256数据集在Caltech-101数据集的基础上增加了图像类别和每类图像的数量，总共30607张图像，共257类。其中包含256个物体类别和一个背景类，每类图片最少80张，最多827张（背景类），图9为Caltech-256数据集中的图片事例。在训练网络时，将数据集中每张图片进行标签，然后打乱，随机抽取其中的3060张图片作为测试集，剩余的图片作为训练集训练网络。

![](images/5440d7d4a58c34a8f623a8e1ce32f606176fa1250983a07cb2d711b436b3fe34.jpg)

# 3.3图宾根大学动物分类数据库

图宾根大学动物分类数据库(Uebingen animalswithattributes)总共有50种动物类别，共30475张图片。由于类别中的图片量差别大，实验选取其中最多的并且类别数目差别不大的21种动物类别作为数据集，共有22742张图片，每类图片数量在850\~1600，图10为图宾根大学动物数据集中的图片事例。在训练网络前，对数据集中的图片进行标注并随机抽取2000张图片作为测试集，其余图片作为训练集训练网络。

![](images/a3d90a944ea30b52e66e3ca61d70769f894add0b52782d7340254ca02962dcfe.jpg)  
图10Uebingen animals(21类)数据集图片事例 Fig.10Picture instances in the Uebingen animals(21) dataset

# 3.4实验结果分析

为了验证改进的有效性，将实验分成4组在相同运行环境和超参数数值的前提下进行结果分析和比较。第一组用标准的MobileNet神经网络结构进行图像分类，第二组用改进的D1-Mobilenet神经网络结构进行图像分类，第三组用改进的D2-MobileNet神经网络结构进行图像分类，第四组用改进的D3-Mobilenet神经网络结构进行图像分类。图11是四种分类方法在Caltech-101 数据集上取得的分类正确率，表1为相应的分类正确率数值。

<html><body><table><tr><td>Table 1</td><td colspan="3">Accuracy rate on Caltech-101101</td><td colspan="2">dataset (%)</td></tr><tr><td>迭代次数</td><td>30000</td><td>35000</td><td>40000</td><td>45000</td><td>50000</td></tr><tr><td>MobileNet</td><td>76.73</td><td>76.6</td><td>76.6</td><td>76.8</td><td>76.6</td></tr><tr><td>D1_MobileNet</td><td>77.4</td><td>77.47</td><td>77.53</td><td>77.4</td><td>77.47</td></tr><tr><td>D2_MobileNet</td><td>77.67</td><td>77.8</td><td>77.73</td><td>77.67</td><td>77.73</td></tr><tr><td>D3_MobileNet</td><td>78.6</td><td>78.6</td><td>78.53</td><td>78.53</td><td>78.73</td></tr></table></body></html>

![](images/ba757eb59a1a1d77f0c5103ab371fe0de613b841eecf31987a2d2475bd30bd2f.jpg)  
图11 Caltech-101数据集上的准确率  
Fig.11 Accuracy rate on Caltech-1O1 dataset

由图11和表1可知，四种分类模型在迭代30000次以后，其准确率均已达到平衡，且改进的三种模型其准确率均比MobileNet模型提高 $0 . 8 \% { \sim } 2 \%$ 左右。其中，D1_MobileNet模型可以提高 $0 . 8 7 \%$ ，D2_MobileNet模型可以提高 $1 . 1 3 \%$ ，D3_MobileNet模型精度提高最多，可以提高 $2 . 1 3 \%$ ，最终分类精度为 $7 8 . 7 3 \%$ 。

图12是四种分类方法在Caltech-256数据集上取得的分类正确率的比较，表2为相应的分类正确率数值。

表1 Caltech-101数据集上的准确率%  
表2 Caltech-256数据集上的准确率 $\%$   

<html><body><table><tr><td>Table 2</td><td colspan="3">Accuracy rate on Caltech-256</td><td colspan="2">dataset (%)</td></tr><tr><td>迭代次数</td><td>30000</td><td>35000</td><td>40000</td><td>45000</td><td>50000</td></tr><tr><td>MobileNet</td><td>64.48</td><td>64.58</td><td>64.55</td><td>64.67</td><td>64.52</td></tr><tr><td>D1_MobileNet</td><td>65.77</td><td>65.74</td><td>65.87</td><td>65.9</td><td>65.87</td></tr><tr><td>D2_MobileNet</td><td>66.1</td><td>66.06</td><td>65.94</td><td>65.84</td><td>65.94</td></tr><tr><td>D3_MobileNet</td><td>64.97</td><td>64.9</td><td>64.87</td><td>65.19</td><td>65.16</td></tr></table></body></html>

![](images/3eb0a2672e7b5123462dd61268dfb563d3f9a252e4e8c03624e023a56d57ae8c.jpg)  
Fig.9Picture instances in the Caltech-256 dataset   
图12 Caltech-256数据集上的准确率  
Fig.12Accuracy rate on Caltech-256 dataset

由图12和表2可知，四种分类模型在迭代30000次以后，其准确率均已达到平衡，且改进的三种模型其准确率均比MobileNet 模型提高 $0 . 5 \% { \sim } 1 . 5 \%$ 左右。其中，D1_MobileNet模型可以提高 $1 . 3 5 \%$ ,D3_MobileNet模型可以提高 $0 . 6 4 \%$ ，D2_MobileNet模型精度提高最多，可以提高$1 . 4 2 \%$ ，最终分类精度为 $6 5 . 9 4 \%$ 。

图13是五种分类方法在UebingenAnimals数据集上取得的分类正确率的比较，表3为相应的分类正确率数值。

表3 UebingenAnimals(21类)数据集上的准确率 $\%$

Table 3.Accuracyrate on Uebingen animals(21) dataset   

<html><body><table><tr><td>迭代次数</td><td>30000</td><td>35000</td><td>40000</td><td>45000</td><td>50000</td></tr><tr><td>MobileNet</td><td>91.6</td><td>91.6</td><td>91.6</td><td>91.55</td><td>91.6</td></tr><tr><td>D1_MobileNet</td><td>92.45</td><td>92.45</td><td>92.5</td><td>92.35</td><td>92.4</td></tr><tr><td>D2_MobileNet</td><td>92.0</td><td>92.05</td><td>92.05</td><td>92.0</td><td>92.0</td></tr><tr><td>D3_MobileNet</td><td>92.85</td><td>92.75</td><td>92.8</td><td>92.7</td><td>92.8</td></tr></table></body></html>

![](images/f25e3481d815a7dc975544638126105ca62c959743522dba9942986b215a14c5.jpg)  
图13 UebingenAnimals(21类)数据集上的准确率  
Fig.13Accuracy rate on Uebingen animals(21) dataset

由图13和表3可知，四种模型在迭代30000次时均达到平衡，准确率变化不大，且改进的D-MobileNet准确率比MobileNet高 $0 . 5 \% { \sim } 1 . 2 \%$ 左右。其中D1_MobileNet模型最终提高 $0 . 8 \%$ ,D2_MobileNet模型最终提高 $0 . 4 \%$ ,D3_MobileNet模型的准确率提高最多，达到 $1 . 2 \%$ ，最终的分类精度为$9 2 . 8 \%$ 。

# 4 结束语

深度学习的内存密集型和高度计算密集型特点使其在应用设备上的应用受到限制，而对网络模型进行压缩与加速，会损失分类精度。本文将空洞卷积与特殊的轻量级神经网络模型MobileNet结合，在不增加网络参数的前提下提高分类精度，使该轻量级网络更好的应用于低内存设备中。实验结果表明改进后的D-MobileNet在实验数据集上有更好的分类精度。

# 参考文献：

[1]Krizhevsky A,Sutskever I,Hinton G E.ImageNet classification with deep convolutional neural networks[J].Communications of the ACM, 2017,60(6): 84-90.   
[2]Wang Naiyan，Yeung D Y. Learning a deep compact image representation for visual tracking [C]// Proc of the $2 6 ^ { \mathrm { { u } } }$ International Conference on Neural Information Processing Systems.[S.l.]: Curran Associates Inc,2013:809-817.   
[ə」wan J,wang D,Hol SU I,el ul.Deep iearg ior conen-vaseu image retrieval: A comprehensive study [C]// Proc of the 22nd ACM International Conference on Multimedia.New York:ACM Press,2014: 157-166.   
[4] Chen L C,Papandreou G, Kokkinos I,et al. DeepLab: semantic image segmentation with deep convolutional nets,atrous convolution,and fully connected CRFs [J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2018,40 (4): 834-848.   
[5] Simonyan K,Zisserman A.Very deep convolutional networks for large-scaleimagerecognition[C]//ProcofIEEEInternational Conference on Computer Vision and Pattern Recognition. 2014.   
[6]SzegedyC,Liu W,Jia Y,et al. Going deeper with convolutions [C]/ Proc of the IEEE Conference on Computer Vision and Pattern Recognition. 2015: 1-9.   
[7]He Kaiming,Zhang Xiangyu,Ren Shaoqing,et al. Deep Residual Learning for Image Recognition [C]/ Proc of IEEE Conference on Computer Vision and Patten Recognition. 2016.   
[8] Denil M,Shakibi B,Dinh L,et al.Predicting parameters in deep learning [C]// Proc of the 26th International Conference on Neural Information Processing Systems.[S.l.]: Curran Associates Inc,2013: 2148-2156.   
[9]Denton E,Zaremba W, Bruna J,et al.Exploiting linear structure within convolutional networks for efficient evaluation [C]// Proc of the 27th InternationalConferenceonNeuralInformationProcessing Systems.Cambridge,MA:MIT Press,2014: 1269-1277.   
[10] Han Song,Mao Huizi, Dally WJ.Deep compression: compressing deep neural networks with pruning,trained quantization and huffman coding [EB/OL].(2016-02-15). https://arxiv.org/pdf/1510.00149.pdf.   
[11] Hinton G E,Vinyals O,Dean J.Distilling the knowledge in a neural network [EB/OL].(2015-03-09).https://arxiv.org/abs/1503.02531.   
[12] Iandola FN,Han S,Moskewicz MW,et al. SqueezeNet: AlexNet-level accuracy with 5Ox fewer parameters and $_ { < 0 }$ .5MB model size[EB/OL]. (2016-11-04). htps://arxiv.org/pdf/1602.07360v3.pdf.   
[13]Howard A G, Zhu Menglong,Chen Bo,et al.MobileNets:efficient convolutional neural networks for mobile vision applications[EB/OL]. (2017-04-17). https://arxiv.org/abs/1704.04861.   
[14] Zhang Xiangyu,Zhou Xinyu,Lin Mengxiao,et al.ShuffleNet:an extremely efficient convolutional neural network for mobile devices ]// Proc of IEEE/CVF Conference on Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2O18: 6848-6856.   
[15] Yu F, Koltun V. Multi-scale context aggregation by dilated convolutions. [EB/OL](2016-04-30).https://arxiv.org/abs/1511.07122.   
[16] Ioffe S,Szegedy C. Batch normalization: accelerating deep network training by reducing internal covariate shift [C]// Proc of International Conference on International Conference on Machine Learning.2015: 448-456.