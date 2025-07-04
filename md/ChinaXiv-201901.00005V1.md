# 基于深度时空卷积神经网络的人群异常行为检测和定位

胡学敏，陈钦，杨 丽，余进，童秀迟(湖北大学计算机与信息工程学院，武汉 430062)

摘要：针对公共场合人群异常行为检测准确率不高和训练样本缺乏的问题，提出一种基于深度时空卷积神经网络的人群异常行为检测和定位的方法。首先针对监控视频中人群行为的特点，综合利用静态图像的空间特征和前后帧的时间特征，将二维卷积扩展到三维空间，设计面向人群异常行为检测和定位的深度时空卷积神经网络；为了定位人群异常行为，将视频分成若干子区域，获取视频的子区域时空数据样本，然后将数据样本输入设计的深度时空卷积神经网络进行训练和分类，实现人群异常行为的检测与定位。同时，为了解决深度时空卷积神经网络训练时样本数量不足的问题，设计一种迁移学习的方法，利用样本数量多的数据集预训练网络，然后在待测试的数据集中进行微调和优化网络模型。实验结果表明,该方法在UCSD和Subway 公开数据集上的检测准确率分别达到了 $9 9 \%$ 和 $9 3 \%$ 以上。

关键词：人群异常行为检测；深度时空卷积神经网络；迁移学习；数据扩充 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.09.0671

# Abnormal crowd behavior detection and localization based on deep spatial-temporal convolutional neural networks

Hu Xuemin, Chen Qin, Yang $\mathbf { L i } ^ { \dagger }$ , Yu Jin,Tong Xiuchi (SchoolofComputer Science&Information Engineering,Hubei University,Wuhan 43oo62,Chinc

Abstract:To handle the issues of low accuracyand lacking training samples in abnormal crowd behaviordetection in public places,this paper proposesamethod basedondeep spatial-temporalconvolutional neural ntworks in this paper.In viewofthecharacteristicsofcrowd behaviorin monitoring videos,adeep spatial-temporal convolution neural network for detectingabnormal crowd behavior is first designed by extending 2Dconvolution to the 3D space according to spatial features ofstatic images and temporal features between the framesbeforeand after thecurrentframe.Tolocating abnormal crowd,this paper divides video frames intoanumberof subregions thatobtain spatial-temporal samples.Then,thesamples areinputintothedesigned dep spatial-temporal convolutional neural network for trainingand clasification,whoseesults are usedto detect and locate abnormal crowd.In the meanwhile,this paper utilizesa transferlearning method to deal with theissue oflacking training samples when training the deep spatial-temporalconvolutional neural network,where datasets with more training samples are used to pre-train the network which is fine-tuned and optimized on testing datasets with fewer samples.Experimental results show thatthe detection accuracies on UCSDand Subway open datasets are greater than $9 9 \%$ and $9 3 \%$ ,respectively.

Key words: crowd abnormal behavior detection;deepspatial-temporalconvolutional neural network;transferlearning;data augmentation

# 0 引言

近年来，随着城市人群安全问题日益突出，视频监控显得尤为重要。传统视频监控通过工作人员观察监控画面获知异常情况，这种方法不仅主观性强，而且浪费人力、效率低下。因此，关于人群异常行为检测与定位的智能视频监控系统具有重要研究意义和商业价值。

目前，国内外研究人员已经在人群异常检测方面做了不少研究工作，并取得了一定成果。相关方法主要分为两大类。第一类是基于局部目标检测的方法，该方法通常利用动态模型对人群行为进行建模。Chaudhry等人[1]利用面向对象的光学直方图并结合分类器来识别人群行为；Colque等人[2.3]利用基于方向、速度和熵的直方图描述人群的异常；Li等人[4则提出一种动态混合纹理模型来实现人群异常的检测。这类方法能够有效检测并定位异常人群行为，但是模型构建复杂并且检测率不高。第二类则是基于全局统计的方法，从整体提取某些特征，如角点、梯度、光流等，然后通过特征分类的方法来实现人群异常行为检测。王乔等人[5提出一种基于整体能量模型表示的方法来较辨识正常行为中的异常行为；任晓芳等人[6对输入的视频使用梯度方向直方图特征和光流直方图特征识别人体动作,最后结合基于能量的最小二乘双分界面支持向量机完成人体动作的识别；姬丽娜等人[7提出一种基于混合高斯模型和尺度不变特征变换特征的人群数量统计分析方法。这类算法的缺点是受环境中光线影响比较大，

准确率不高。

![](images/56dd85a7c9bb17f5491a35e44dbf3a506df909c16d4b6f8e3ead1d132afa8996.jpg)  
图1基于DSTCNN的人群异常行为识别与定位流程图 Fig.1Flow chart of abnormal crowd behavior detection and localization based on DSTCNN

近年来，卷积神经网络(convolutionneural network,CNN)凭借其优良的特征提取能力在计算机视觉领域得到广泛关注。传统卷积神经网络能够对二维图像进行有效的特征提取，从而实现目标检测与分类。Chen等人[8借助卷积神经网络实现在夜景中识别汽车转向灯；文献[9]则利用卷积神经网络对人的年龄和性别进行判断。传统卷积神经网络仅能够在二维图像上提取特征，但是无法应用于三维的视频数据。文献[10]提出了基于传统CNN的人群异常行为检测，但是只使用了运动方向、速度和加速度三者的运动显著图，丢失了大量信息，导致能够检测的异常行为有限。针对这种问题，有学者提出能够应用于视频中时空特征提取的时空卷积神经网络，并应于与人体行为的识别[1。此外，训练一个深度网络需要大规模、多样化的训练样本，而实际的人群异常行为检测中往往难以获取足够的样本，从而导致检测效果不理想。

针对现有的人群异常检测方法检测率不高、传统CNN无法提取时间相关特征、以及训练样本缺乏的问题，本文提出一种基于深度时空卷积神经网络(Deep Spatial-temporalConvolution Neural Network,DSTCNN)的人群异常行为检测与定位的方法，如图1所示。首先，基于传统CNN，结合时间特征，设计DSTCNN 的结构；然后基于DSTCNN，设计人群异常行为检测和定位的方法；针对数据不足问题，提出基于迁移学习的DSTCNN训练方法。在数据量较多的数据集上训练得到检测率较高的DSTCNN模型，将此模型通过迁移学习(transferlearning,TF)的方法迁移到其他数据集对应模型上并训练。实验结果表明本文的方法与现有方法相比，具有更高的检测率。

![](images/fa4c0548d8961156aa70e6e3572248949a7a2ff7858233ed5fa8417754defd1a.jpg)  
图2二维卷积与三维卷积  
Fig.22D convolution and 3D convolution

# 1 时空卷积神经网络

传统卷积神经网络使用二维卷积核对图像进行特征提取，卷积神经网络中每个卷积层都包含多个不同的卷积核，每个卷积核提取不同的特征。通常一个完整的卷积神经网络包含多层卷积层，低层卷积层提取低级特征，如边缘、线条、角落；高层卷积层提取高级特征，如目标对象各部分的轮廓。卷积层提取的特征最后通过全连接层组合成完整的目标对象。传统卷积神经网络可以有效地对图像进行特征提取和目标分类，但是仅限于静态图像，无法对视频中连续视频帧之间的时间特征进行提取。时空卷积神经网络和传统卷积神经网络的本质区别在于网络所使用卷积核的不同，如图2所示。传统卷积神经网络中所使用的二维卷积核提取特征时，只在图像上进行行和列的卷积。而连续视频帧中，除了每一帧的图像特征，连续帧之间还存在时间关联性。基于视频分析的人群异常行为检测中，人群的行为特征在视频中表现为空间和时间的关联性。因此时空卷积神经网络采用三维卷积核，其卷积计算的内容除了包含每一帧图像的行和列像素点以外，还包含前后帧对应位置的像素点，即时空卷积神经网络除了能够提取单个视频帧的图像特征，还能提取连续帧之间的时间特征。时空卷积神经网络的每一层从输入到输出的计算方式如式(1)所示。

$$
y = \sigma \Biggl ( \sum _ { k } \sum _ { j } \sum _ { i } \left( { \vec { x } } _ { i j k } * { \vec { w } } + b \right) \Biggr )
$$

其中： $y$ 表示某一层的输出； $\sigma$ 表示激活函数； $i , j , k$ 表示样本上对应位置的坐标； $\vec { x } _ { i j k }$ 表示每一层输入上对应于 $( i \mathbf { \nabla } , j$ k)处与对应卷积核尺寸大小相等的局部区域，如图2右边立方体中阴影部分所示； $\vec { w }$ 表示卷积核的权重矩阵； $b$ 表示对应卷积核的偏置值。

# 2人群异常行为检测与定位算法

为实现人群异常的定位，本文首先将完整的视频画面分成若干子区域并编号，对每个子区域使用DSTCNN进行人群异常行为检测，若某个子区域检测为异常，则可根据编号找到对应的视频区域，实现人群异常行为的检测与定位。

# 2.1深度时空卷积神经网络结构设计

本文设计的面向人群异常行为检测和定位的深度时空卷积神经网络结构，如图3所示，其中包含8个卷积层、5个池化层和2个全连接层以及1个输出层。为提取人群行为信息，以连续若干帧一定大小视频子区域作为输入。由于本文设计深度时空卷积神经网络主要目的在于检测异常，因此输出为两类，正常与异常。

实验证明 $3 \times 3 \times 3$ 的卷积核尺寸对于视频处理是一种合适的尺寸[12]，因此本文中的深度时空卷积神经网络的卷积核尺寸统一固定为 $3 \times 3 \times 3$ ；卷积步长统一设定为 $1 \times 1 \times 1 _ { \circ }$ 除第一层池化核大小设定为 $1 \times 2 \times 2$ ，步长设定为 $1 \times 2 \times 2$ 以外，其他层的池化核大小统一设定为 $2 \times 2 \times 2$ ，步长设定为2$\times 2 \times 2$ 。池化方式统一采用最大池化，并将池化层间隔一层或两层置于卷积层中间，对卷积层信息降采样，用以在保留重要信息和减少相关度相对较低信息、降低计算复杂度的同时，提升卷积神经网络的泛化能力。而第一层池化层 $1 \times 2 \times$ 2 池化核与池化步长的设计可以避免视频中时序信息被过早地降采样。第1\~4层卷积层用于提取低级特征，第5\~8层卷积层用于提取高级特征，低级特征较为通用，种类较少，高级特征更为具体，种类较多，因此第1层卷积层设置64个卷积核，第2层卷积层设置128个卷积核，第3\~5层卷积层设置256个卷积核，第6\~8层卷积层设置512个卷积核。通过卷积与池化得到的特征与两层全连接层连接组成具体目标对象，最后通过输出层得到卷积神经网络对输入视频的分类概率。

![](images/4e6ab5103a0cbe581ea998b983aa984137ad0d2fb37c111c9b502023bd58078f.jpg)  
图3面向人群异常行为检测和定位的深度时空卷积神经网络结构

Fig.3Structureofdeepspatial-temporalconvolutionaleuralnetworkforcrowdabnormalbehaviordetectionandlocalizatior

在每一层卷积层以及全连接层之后，本文使用ReLu(Rectifiedlinearunit,修正线性单元)激活函数，提升神经网络模型的线性表达能力。为输出视频的分类概率，输出层采用Softmax函数。最后结合交叉熵[13]函数与L2正则化构造损失函数，并利用Adam优化算法更新优化神经网络模型。交叉熵函数如式(2)所示。

$$
C { = } { - } \frac { 1 } { n } { \sum _ { x } } [ y \ln a + ( 1 - y ) \ln ( 1 - a ) ]
$$

其中： $c$ 表示损失值； $n$ 表示样本总量； $x$ 表示样本； $y$ 表示期望的输出(即标签); $a$ 表示实际的输出，具体表达式如式(3)所示。

$$
a = \sigma \Bigg [ \sum _ { k } \sum _ { j } \sum _ { i } ( \vec { x } _ { i j k } * \vec { w } + b ) \Bigg ]
$$

![](images/78d64627d8b02da72b797d81054616d99e23a523c0760d50a15ac50a6278bae9.jpg)  
图4异常检测与定位  
Fig.4Anomaly detection and location

# 2.2异常行为的检测与定位

为实现人群异常行为的定位，本文将完整视频画面划分为若干个大小相同的局部子区域，相邻子区域互不重叠。每个子区域设置一个唯一编号，每个编号对应不同的子区域，如图4所示。为实现对每个子区域进行人群异常行为检测，本文将每个子区域的连续视频帧作为输入，训练得DSTCNN模型；在检测人群异常行为时，同样将完整视频划分为局部子区域，再将每个局部子区域输入已训练好的DSTCNN 模型。若某个子区域被识别为异常，则根据编号确定其在视频画面中的位置，实现人群异常行为的定位。

# 3 深度时空卷积神经网络的训练方法

深度神经网络的训练和优化需要大规模、多样化的数据样本，而对于人群异常行为分析，异常情况通常以小概率发生，因此难以获取足够的训练样本，特别是异常行为的样本。现有的公开数据集中，同样存在异常行为样本数量较少、正常和异常样本数量相差较大的问题，导致难以训练实用的深度神经网络。针对这种情况，本文设计一种基于数据扩充和迁移学习的深度神经网络训练方法，在训练DSTCNN之前首先将训练样本数据进行数据扩充，使用扩充后的训练样本训练得到优化后的DSTCNN模型，然后使用迁移学习的方法，将此模型迁移到其他DSTCNN模型上，实现少量样本的训练和优化。

# 3.1数据扩充

图像的亮度、对比度、噪声等属于图像的二维特征，且这些特征对于人群的行为没有影响，因此本文针对训练样本数据不足及正常样本和异常样本数量相差较大问题，通过增加对比度、降低对比度、增加亮度、降低亮度、添加椒盐噪声、进行高斯模糊等6种方式，对训练样本进行数据扩充(dataaugmentation,DA)使其数量增加为原来的7倍，如图5所示。同时，通过保留数量较少的异常样本并随机去除数量相对较多的正常样本，使正常样本与异常样本比例为2：1。利用以上方式，可以改变视频中每一帧的图像信息，增加样本多样性，同时保留人群原有的行为特征，并减小正常样本与异常样本数量差异。从图5中可以看出，本文的数据扩充方法能够在一定程度上有效增加训练数据的数量。

# 3.2基于迁移学习的DSTCNN训练方法

对于一些人群异常行为检测的场景或者公开数据集，其中异常样本数据过于稀少，即使在经过数据扩充后样本数据仍然不足。另外，如果只是通过数据扩充来实现正负样本的平衡，容易引起过拟合的问题。因此，本文提出一种基于迁移学习的训练方法，实现DSTCNN的训练和优化。

当源域数据与目标域数据存在部分共享模型参数时，即两个数据集之间存在部分相似的基础特征，而该部分特征可利用相同卷积神经网络进行提取的时候，可基于模型进行迁移学习[14]。Long 等人[15]提出一种DAN 结构，通过迁移并固定卷积神经网络低层卷积层网络参数，在特定数据集上微调高层卷积层及全连接层的方法，在Office-31、Office- $1 0 ~ +$ Caltech-10数据集上取得较高识别率。由于不同的人群行为数据集中，人群行为也存在部分相似的特征，因此本文在数据量相对较多的UCSD数据集上训练得到DSTCNN模型，再将此模型通过迁移学习迁移到Subway数据集上的DSTCNN模型，如图6所示。

在进行迁移学习过程中，本文将UCSD数据集作为源域$D _ { s }$ ，将Subway数据集作为目标域 $D _ { t }$ ，其中：

$$
D _ { s } = \left\{ x _ { i } , y _ { i } \right\} _ { i = 1 } ^ { n } , D _ { t } = \left\{ x _ { j } , y _ { j } \right\} _ { j = 1 } ^ { n } , X _ { s } = X _ { t } , Y _ { s } = Y _ { t }
$$

$x _ { i }$ 、 $x _ { j }$ 分别表示第 $i , j$ 个样本， $y _ { i } , \ y _ { j }$ 表示对应的标签。$X _ { \mathrm { s } }$ 、 $X _ { \mathrm { { t } } }$ 分别表示源域及目标域的特征空间， $\mathrm { Y _ { s } }$ 、 $\mathrm { Y _ { t } }$ 分别表示源域及目标域的标签空间。

首先利用 $D _ { s }$ 学习得到分类器：fi: $x _ { s }  y _ { s }$ 来预测 $D _ { s }$ 的标签$y _ { s }$ ，其中 $x _ { s }$ 表示源域样本，fi表示 $D _ { s }$ 对应的目标函数，且$\mathbf { \boldsymbol { x } } _ { s } \in D _ { s }$ ；为得到：f2: $x _ { t } \to y _ { t }$ 即用来预测 $D _ { t }$ 对应标签 $y _ { t }$ 的分类器，其中 f表示 $D _ { t }$ 对应的目标函数， $x _ { t }$ 表示目标域样本，且 $x _ { t }$ $\scriptstyle \in D _ { t }$ ，本文将fi: $x _ { s } \to y _ { s }$ 在一定条件下利用 $D _ { t }$ 重新学习，完成如下过程：

![](images/668590b5a5ad8be83bde8bca8020a83d459d134f9492de7c25a32dac3413e377.jpg)  
图5数据扩充样例  
Fig.5Data augmentation samples

f2: $x _ { t } \to y _ { t } =$ retrain(f1: $\boldsymbol { x } _ { s } \to \boldsymbol { y } _ { s } \mathrm { , }$ s.t.Neti[1\~ $l ] = \mathsf { N e t } _ { 2 } [ 1 { - } l ] = K$ ，$( \mathbf { x } \ , \mathbf { y } ) { \in } \mathbf { D } \mathrm { t }$

其中：retrain表示重新训练过程， $\mathrm { N e t } _ { 1 } [ 1 { \sim } l ]$ 、 $\mathrm { N e t } _ { 2 } [ 1 { \sim } l ]$ 分别表示 $D _ { s , } D _ { t }$ 对应的神经网络的第1层到第 $\mathbf { \xi } _ { l }$ 层参数， $K$ 表示常数矩阵，重新训练过程中 $K$ 不变。为确定 $\mathbf { \xi } _ { l }$ 值，本文分别对$\mathbf { \xi } _ { l }$ 取不同值并在UCSD数据集上进行对比实验，最终确定最优值 $\scriptstyle { l = 4 }$ 。

训练网络时，在数据扩充的基础上，本文将两个数据集划分局部子区域，首先在UCSD数据集上训练DSTCNN，取连续N(本文中 ${ \bf N } = 1 0 \$ 帧UCSD数据集局部子区域视频作为输入，初始化DSTCNN模型参数后进行训练，再利用UCSD数据集测试集对DSTCNN模型进行评测，得到优化后的DSTCNN模型；由于在UCSD数据集与 Subway 数据集中，

DSTCNN的前4层提取的特征是两个数据集所共有的特征，因此可利用相同结构神经网络进行特征提取，即将在UCSD数据集上训练得到的DSTCNN模型前4层卷积层直接迁移到Subway 数据集的DSTCNN上，固定该4层网络参数，取连续 $N$ 帧Subway数据集的局部子区域视频作为输入，更新除前4层卷积层之外的参数，得到适合 Subway 数据集人群异常行为检测和定位的DSTCNN模型。

![](images/37f80c900a706bc00499ebdcd33ff74c78f75cff855f343dde5e645e53f27c62.jpg)  
图6UCSD数据集到Subway数据集的DSTCNN模型迁移学习（ $\mathrm { \bf C } _ { 1 } { \sim } \mathrm { \bf C } _ { 8 }$ 第1\~8个卷积层 $\mathrm { F C } _ { 1 } { \sim } \mathrm { F C } _ { 2 } { : } 2$ 个全连接层)  
Fig.6TransferLearning ofDSTCNN model fromUCSD dataset t Subway dataset

# 4 实验结果与分析

本文进行实验的硬件环境：CPU为Corei7-7700K(Quad-core $4 . 2 ~ \mathrm { G H z } ,$ ）、显卡为NVIDAGTX1080ti、内存为32GB。软件环境：计算机操作系统为Windows10 pro、DSTCNN训练测试平台为TensorFlow1.2、Python3.5。

本文利用UCSD以及Subway 这两个开源的数据集。其中UCSD数据集由美国加利福尼亚州统计学习视觉计算实验室提供[16]。该数据集包含场景一和场景二两个人群行走视频，其视频像素分辨率分别为 $2 3 8 \times 1 5 8$ 、 $3 6 0 \times 2 4 0$ 。视频中正常行为是正常行走的人群，而异常的行为包括骑自行车、驾驶汽车、踩滑板、坐轮椅的老人等行为；Subway 数据集源自于Adam等人，包含地铁入口以及出口的两个监控视频，像素分辨率均为 $5 1 2 \times 3 8 4 ^ { [ 1 7 ] }$ 。对于入口视频，正常行为是正常刷卡进入入口，异常行为表现为从入口出来、不刷卡强行翻越进入入口等；对于出口视频，正常行为则是正常从出口走出来，异常行为则是强行从出口翻越进入。

本文将UCSD及Subway数据集分为训练数据以及测试数据两部分，为保证训练时异常样本的数量，本文选取异常行为相对较多的视频作为训练数据，其余的作为测试数据。为了在尺寸上能够将人群中的个体、人群与障碍物分离，并且最大限度包含人体行为信息，UCSD数据集划分的子区域大小为 $3 0 \times 3 0$ 像素，Subway 数据集划分的子区域大小为$6 0 \times 6 0$ 像素，同一子区域取连续10帧作为一个样本。当视频中出现异常情况时，所有包含人体的子区域标注为异常样本，其余情况子区域均标注为正常样本。对训练数据按照3.1节中的方法进行预处理，得到训练数据，数据扩充前后样本数量、正常与异常样本比例如表1所示。可以看出，Subway数据集中包含的人群异常行为的样本，远远无法达到训练一个深度神经网络的要求。

为证明扩充数据以及迁移学习的有效性，本文在UCSD以及Subway两个数据集的每一个场景上都进行了4组实验：不进行数据扩充直接训练DSTCNN、进行数据扩充后训练DSTCNN、不进行数据扩充并结合迁移学习训练DSTCNN、进行数据扩充后结合迁移学习训练DSTCNN。其中，对UCSD数据集，其场景一和场景二样本相似度较大，因此训练时合并两个场景一起训练，但测试时分场景一和场景二两个场景单独测试。UCSD数据集实验结果如图7(a)-(d)所示，图中黑色方框区域即为异常区域；对Subway数据集，其出口和入□两个场景样本差异较大，因此分开训练及测试。Subway数据集的实验结果如图8(a)-(d)所示。为定量描述实验结果，本文基于每个测试数据集绘制受试者工作特性曲线(ReceiverOperatingCurve，ROC)，并计算出ROC曲线下的面积(AreaUnder theCurve,AUC)，UCSD数据集的场景一、场景二以及Subway数据集的入口、出口场景ROC曲线分别如图7(e)(f)、图8(e)(f)，其AUC的值如表2所示。另外，为验证本文方法的有效性，本文将实验结果与几种经典算法HOOFI、HOFM[2]、HOFME[3]、MDT-temporal[4]、MDT-spatial[4]进行对比，结果如表3所示。根据实验结果，可以得出以下结论：

a）本文设计的DSTCNN模型能够有效检测和定位多种人群异常行为。DSTCNN通过提取二维图像特征和视频序列特征，表达复杂的人群行为，因此本文方法能够检测和定位多种不同的人群异常行为。如图7(a)中检测出的汽车、图8(a)中检测出的翻越地铁入口的人群。

b）本文提出的数据扩充和基于迁移学习的训练方法，能够有效提高人群异常行为检测的准确率。本文通过数据扩充增加了训练样本的数量以及多样性，同时结合迁移学习优化DSTCNN模型，使其即使在训练样本数量很少的情况下，也能够准确提取人群行为特征并分类，从而提高了人群异常行为检测的准确率。例如表3中UCSD数据集的场景一通过数据扩充以及迁移学习的方法将AUC值提升了0.1663；表3中Subway 数据集的入口场景AUC 值通过相同方法提升了0.0539。

c）本文基于DSTCNN，结合数据扩充与迁移学习的方法，比现有经典方法在公开数据集中的检测率更高。本文分别通过数据扩充与迁移学习在数据层面及模型层面对DSTCNN进行优化，最终在UCSD数据集与Subway数据集上得到的测试结果AUC均高于对比的几种经典方法，其中UCSD数据集场景二的AUC更是达到了0.9994，相比对比方法中最好的AUC为0.899高出0.1004。此外，在正常和异常人群样本数量悬殊的情况下，只进行数据扩充训练神经网络模型比只进行迁移学习效果好。迁移学习能够解决因数据量较少导致的深度神经网络性能不高的问题，但是无法有效处理数据正负样本数量悬殊的问题。本文对数据进行扩充后对正常和异常人群的样本比例进行了调整，因此数据扩充后训练得到的模型性能优于仅使用迁移学习训练得到的深度神经网络模型。

表1不同数据集的样本数量  
Tab.1 Samplenumbers ofdifferentdatasets   

<html><body><table><tr><td rowspan="2">数据集场景</td><td rowspan="2"></td><td rowspan="2">有无扩充</td><td colspan="2">训练</td><td colspan="2">测试 正常样本 异常样本 正常样本 异常样本</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td rowspan="5">UCSD</td><td rowspan="5">场景一</td><td>无</td><td>1332</td><td>666</td><td>1388</td><td>12</td></tr><tr><td>有</td><td>9324</td><td>4662</td><td>1</td><td></td></tr><tr><td>无 场景二</td><td>1332</td><td>666</td><td>3398</td><td>58</td></tr><tr><td>有</td><td>9324</td><td>4662</td><td>1</td><td></td></tr><tr><td>无</td><td>164</td><td>82</td><td>2796</td><td>36</td></tr><tr><td rowspan="4">入口 Subway</td><td></td><td>有</td><td>1148</td><td>574</td><td>1</td><td></td></tr><tr><td>出口</td><td>无</td><td>108</td><td>54</td><td>2396</td><td>6</td></tr><tr><td></td><td>有</td><td>756</td><td>378</td><td>一</td><td>一</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/777db21d4cb8ff762ac73404226364af67dfc9162d534fd5a05c8691dd2aff5a.jpg)  
图7UCSD数据集测试结果 Fig.7Experimental results in UCSD dataset

![](images/7a3d5bf53879071be0e5c3ff2684ce4434e9ad29edbb10432a9aa71ab37a8897.jpg)  
图8Subway数据集测试结果  
Fig.8Experimental results in Subway dataset

d）在8层卷积层的深度时空卷积神经网络中，固定前4层时空卷积层进行迁移学习的能取得最优检测效果。表4为将在UCSD 数据集上训练的网络，迁移到 Subway入口数据集上训练，固定前1\~l层测试的AUC值。由于第4层之前的时空卷积层主要提取的为行人的边缘、形状等人群通用特征，后4层的时空卷积层主要提取为行人的行为特征，因此固定前4层的检测效果较好。随着固定层数的减少，由于Subway上的数据量较少，少量的数据难以训练所有网络层的权重，故AUC值会减小；随着固定层数的增加，由于两个数据集的人群异常行为的专用特征不一样，因此只微调个别高层网络的权重，无法拟合新的数据集的人群行为特征数据，因此AUC值也会减小。

表2有无数据扩充和迁移学习的对比测试  
表3与其他经典方法的对比测试  

<html><body><table><tr><td colspan="5">experiments withoutDA or TF</td></tr><tr><td>方法</td><td>UCSD 数据集 场景一</td><td>场景二</td><td>Subway数据集 入口</td><td>出口</td></tr><tr><td>DSTCNN</td><td>0.8311</td><td>0.9227</td><td>0.8792</td><td>0.5000</td></tr><tr><td>DSTCNN+DA</td><td>0.9960</td><td>0.9993</td><td>0.8112</td><td>0.8984</td></tr><tr><td>DSTCNN+TF</td><td>0.9919</td><td>0.9877</td><td>0.8974</td><td>0.9820</td></tr><tr><td>DSTCNN+DA+TF</td><td>0.9974</td><td>0.9994</td><td>0.9331</td><td>0.9829</td></tr></table></body></html>

Tab.2 Comparative results between experiments with DA or TF and   
Tab.3 Comparative results with other classical methods   

<html><body><table><tr><td rowspan="2">方法</td><td colspan="2">UCSD数据集</td><td colspan="2">Subway数据集</td></tr><tr><td>场景一</td><td>场景二</td><td>入口</td><td>出口</td></tr><tr><td>HOOF</td><td>0.6900</td><td>0.8200</td><td>0.7740</td><td>0.8000</td></tr><tr><td>HOFM</td><td>0.7150</td><td>0.8990</td><td>0.8150</td><td>0.8450</td></tr><tr><td>HOFME</td><td>0.8490</td><td>0.8160</td><td>0.8160</td><td>0.8490</td></tr><tr><td>MDT-temporal</td><td>0.8250</td><td>0.7650</td><td>0.8890</td><td>0.8750</td></tr><tr><td>MDT-spatial</td><td>0.6000</td><td>0.7500</td><td>0.6820</td><td>0.6700</td></tr><tr><td>DSTCNN+DA+TF</td><td>0.9974</td><td>0.9994</td><td>0.9331</td><td>0.9829</td></tr></table></body></html>

表4不同迁移层数在Subway入口数据集上测试AUC 值 Tab.4AUC values of testing results for different transfer layers on the Subway dataset of the entrance   

<html><body><table><tr><td>迁移层数1~l的l取值</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td></tr><tr><td>AUC</td><td>0.8227</td><td>0.8883</td><td>0.9331</td><td>0.9068</td><td>0.8734</td></tr></table></body></html>

# 5 结束语

本文提出一种利用深度时空卷积神经网络，并结合迁移学习实现人群异常检测与定位的方法。该方法中，首先根据应用场景设计DSTCNN结构，该结构主要包含用于特征提取的卷积层与特征分类的全连接层及输出层，然后设计基于数据扩充和迁移学习的训练方法，实现DSTCNN的训练和优化，提高检测率。在UCSD数据集和 Subway 数据集上的测试结果表明，本文的方法能够有效进行人群异常行为检测与定位，其检测准确率高于几种经典方法。

同时，本文方法也存在一定局限性。由于DSTCNN计算量较大，本文的方法实时性难以满足实时性要求高的多路监控系统；此外，本文方法只能检测并定位异常，无法识别出具体是何种异常。因此未来的工作将致力于优化算法，提高实时性以及实现异常行为的分类识别。

# 参考文献：

[1]Chaudhry R,Ravichandran A,Hager G,et al.Histograms of oriented optical flow and Binet-Cauchy kernels on nonlinear dynamical systems for the recognition of human actions [C]/Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2009:1932-1939.   
[2]Colque RVHM,Junior CAC,Schwartz WR.Histograms of Optical Flow Orientation and Magnitude to Detect Anomalous Events in videos [C]//Proc of the 28th SIBGRAPI Conference on Graphics,Patterns and Images.Washington DC:IEEE Computer Society,2015:126-133.   
[3]ColqueRVHM,Junior C AC,Schwartz WR.Histograms of optical flow orientation and magnitude to detect anomalous events in videos [J]. IEEE Trans on Circuits & Systems for Video Technology,2017,27(3): 673-682.   
[4]Li Weixin，Mahadevan V,Vasconcelos N.Anomaly detection and localization in crowded scenes [J].IEEE Trans on Pattern Analysis& Machine Intelligence,2014,36(1):18-32.   
[5]王乔，雷航，郝宗波．基于整体能量模型的异常行为检测[J].计算 机应用研究，2012,29(12):4782-4785.(Wang Qiao,Lei Hang，Hao Zongbo.Abnormal behavior detection based on globe energy model [J]. Application Research of Computers,2014,29(12):4782-4785.)   
[6] 任晓芳，秦健勇，杨杰，等．基于能量模型的 LS-TSVM 在人体动作 识别中的应用[J].计算机应用研究，2016，33(2)：598-601.(Ren Xiaofang,Qin Jianyong,Yang Jie,etal.Energy model based LS-TSVM for action recognition [J].Application Research of Computers,2016,33 (2):598-601.)   
[7]姬丽娜，陈庆奎，陈圆金，等．基于GPU的视频流人群实时计数 [J]. 计算机应用，2017,37(1):145-152.(Ji Lina,Chen Qingkui,Chen Yuanjin,et al. Real-time crowd counting method from video stream based on GPU [J].Journal of Computer Applications,2017,37(1): 145-152.)   
[8] Chen Long,Hu Xuemin, Xu Tong,et al. Turn Signal Detection During Nighttime by CNNDetector and Perceptual Hashing Tracking[J].IEEE Trans on Intelligent Transportation Systems,2017,18(12):3303-3314.   
[9]Levi G, Hassner T.Age and gender classification using convolutional neural networks [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition Workshops.Washington DC:IEEE Computer Society,2015: 34-42.   
[10]胡学敏，易重辉，陈钦，等．基于运动显著图的人群异常行为检测 [J]．计算机应用,2018,38(4):1164-1169.(Hu Xuemin,Yi Chonghui, Chen Qin,et al.Abnormal crowd behavior detection based on motion saliency map [J].Journal of Computer Applications,2018,38 (4): 1164-1169.)   
[11] Ji Shuiwang，Yang Ming，Yu Kai，et al.3D convolutional neural networks for human action recognition [J].IEEE Trans on Pattern Analysis& Machine Intelligence,2013,35(1):221-231.   
[12] Tran D,Bourdev L,Fergus R,et al.Learning Spatiotemporal Features with 3D Convolutional Networks [C]//Proc of IEEE International Conference on Computer Vision．Washington DC:IEEE Computer Society,2015: 4489-4497.   
[13] Kline M,Berardi L.Revisiting squared-error and cross-entropy functions fortraining neural network classifiers[M].Berlin: Springer-Verlag,2005:310-318.   
[14] Pan Jialin, Yang Qiang.A survey on transfer learning [J]. IEEE Trans on Knowledge and Data Engineering,2010,22(10):1345-1359.   
[15] Long Mingsheng,Cao Yue,Wang Jianmin,et al.Learning transferable features with deep adaptation networks [C]//Proc of International Conference on Machine Learning.2015: 97-105.   
[16] S.V.C.Lab,“UCSD anomaly data set”[EB/OL]. (2014)[2018-10-22]. http://www. svcl.ucsd. edu/projects/anomaly/;http://www. svcl. ucsd. edu/projects/anomaly/.   
[17] Adam A,Rivlin E,Shimshoni I,et al.Robust Real-Time Unusual Event Detection using Multiple Fixed-Location Monitors [J].IEEE Trans on Pattern Analysis& Machine Intelligence,20o8,30(3):555-560.