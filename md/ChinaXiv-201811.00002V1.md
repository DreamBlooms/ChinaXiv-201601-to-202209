# 基于卷积神经网络的全天空地基云图分类研究

崔顺12许允飞2苏丽颖1崔辰州²樊东卫²韩军²王川中12张磊23(1 北京工业大学机械工程与应用电子技术学院北京 100124)(2 中国科学院国家天文台北京 100012)（3中国科学院大学北京100049）

# 摘要：全天相机拍摄的全天空地基云图能够实时反应当地的云量信息，而云量是天文选

址时需要首先考虑的因素之一。在云量检测工作前对全天空地基云图根据图像质量，应用背景等因素进行自动化分类，实现鲁棒性高、适应性强的自动化分类算法，将减少图像分类过程中的人工成本，为天文选址提供重要帮助。本文实现了一种基于卷积神经网络分类模型的全天空地基云图自动化分类方法，采用雪龙号科考船搭载的全天相机数据进行了分类模型训练，并使用中科院云南天文台丽江观测站全天相机数据进行了验证，均取得了较好的分类效果，并证明该方法具有良好的可迁移性。

关键词：天文选址；云图分类；模式识别；卷积神经网络

# 1．研究背景与意义

对于天文选址，云量是首先需要考虑的因素之一。天文观测目标发射出的光线到达地基望远镜的终端时，会受到大气中云的散射和吸收，大气中云量的多少，决定了观测数据质量的好坏，从而决定了天文可用时间和天文观测可视域。然而，现在对云的观测还是以人工观测为主，观测结果受人为主观因素影响较大1，因此，实现云量的自动检测尤为重要。

全天相机是实现云量自动检测的主要仪器。全天相机主要由电荷耦合元件(ChargeCoupled Device，CCD)和鱼眼镜头组成，通过全天相机拍摄的全天空地基云图具有很高的空间和时间分辨率，其分析结果能够准确反映当地的云量覆盖与变化特征，适合用于全天云量信息监测[2]。

全天相机在拍摄地基云图时，难免会受到时间、天气、光照等因素的影响，导致获取图像的内容质量有所差异，此外针对不同时段（如白天与黑夜)的图像，云量检测方法也不同。

因此在进行云量检测之前，去除不可靠图像（雨露雪、过曝光），区分图像场景（夜晚或者白天），以自动化统计晴天数与晴夜数，是云量自动分析工作的基础。

根据上述需求，本文根据图像质量、应用场景等因素对全天空地基云图做了详细的类别划分，并基于部署在雪龙号上的全天相机获取的地基云图数据集，进行了基于卷积神经网络（Convolutional Neural Network，CNN）[3]的分类模型训练，提出了全天空地基云图的自动化分类处理方法。并使用中国科学院云南天文台丽江观测站全天空地基云图数据集对模型进行了验证，同样取得了较好的分类效果，证明了模型拥有较强的泛化性能，适用于天文选址时全天空地基云图的分类。

本文首先阐述了全天空地基云图分类的背景与意义；第二部分介绍了模型训练所采用的数据集及分类标准；第三部分对现有的卷积神经网络模型以及文中使用的分类模型进行了详细描述；第四部分主要介绍了模型的训练过程；第五部分描述了丽江数据在模型上的验证效果并做了详细的分析；第六部分总结与展望，分析了模型的优点与不足，并提出了改进方向。

# 2．数据集以及分类标准

全天相机拍摄的全天空地基云图种类复杂多样，质量也不尽相同。使用大量不同且具有代表性的训练数据能够提高分类模型的泛化能力，使模型在新数据集上拥有较好的适应性，从而实现任意地区全天空地基云图的自动化分类，为云检测自动化系统的实现和天文选址提供支撑。

# 2.1雪龙号极地科考船全天相机数据

雪龙号是我国的极地综合科学考察专用船。2017年7月20日雪龙号从上海出发，7月31日进入北极圈，10月9日返回上海长江口水域，共航行20590 海里，成功完成了第8次北极科学考察任务。搭载在雪龙号上的全天相机每五分钟采集一次数据，航行期间共获得数据 89.8GB，共13484张，图像单张分辨率为 $1 0 0 0 ^ { * } 6 2 5$ 。

航行沿途经过区域广，环境因素复杂，获取的全天影像数据类型丰富，覆盖性强，很适合作为模型的训练数据。

# 2.2分类标准

根据应用场景，将云图划分为夜晚（dark），雨露雪（rain_snow），过曝光（overlight），晴空（bluesky），少云（cloudimage），多云（overcast）6类。

昼夜会给图像带来不同的特性，研究的内容和方法也往往不同。云点识别时，对于白天拍摄的全天空地基云图，往往通过图像可见光波段的性质来确定有云点[4]；夜间则将测得的星场图像与计算的星象图作比较，确定哪些已知的明亮恒星被云遮盖，从而识别云[5]。因此，昼夜图像分类将便于之后的科学研究，我们将夜晚拍摄图像划分为一类，如图所示。

![](images/6825fd7aad917e2ea7abe3e8629098740b9dbcf71ce490e0d9c0e8ab4bada74f.jpg)  
图1夜晚类典型图像

对于白天图像我们做了更为细致的划分。拍摄过程中，镜头往往会受到恶劣天气的影响，如雨露雪对镜头的覆盖，严重影响成像质量，使得这部分图像很难应用于之后的云量检测工作。为此将受雨露雪影响的图像划分为单独一类。雨露雪类图像如图2。

![](images/15d8ce5cebabdf1164f0b36b04f3c43397e64ccc3860a40858890faa8481a08f.jpg)  
Fig1 Typical image of dark   
图2雨露雪类典型图像

Fig2 Typical image of rain_snow

正午光线充足，在强光照射下拍摄图片容易发生过曝光的现象，将这类数据划分为单独一类,可区分出更有研究价值的全天空云图数据。当曝光面积大于全天图像面积三分之一时，认为该图片属于过曝光类。过曝光类典型图像如图3所示。

![](images/c2dec6987cf4bfbbcfbe4927be3b7ff9fafda7daa6ed94a926299a67f5ff9f1d.jpg)  
图3过曝光类典型图像

Fig3Typical image of overlight

69   
70   
71   
72   
73   
74   
75   
76

在去除掉质量较差的图像后，根据云量的多少将剩余图像划分为三类，晴空类、多云类和少云类。晴空不含云，整个天空几乎完全被云覆盖定义为多云，其他则均认为是少云。一些数据在太阳所在位置会出现过曝，出现的白色区域较难与云区分，此时根据数据拍摄时间与区域形状确定该区域是太阳过曝还是云。各类别典型代表图像如下，图4为晴空类，图5为多云类，图6为少云类。

![](images/0fa465724c5b88b28267e59cc2a35383f430e8a49a9270bef30429e0e5207a3a.jpg)  
图4 晴空类典型图像

77   
78   
79

![](images/1d61291aba1ad0151f853cf8ff51131eea7282cb72a37aabaa4fbf08cbecd89b.jpg)  
Fig4 Typical image of bluesky   
图5多云类典型图像

![](images/bd3ae84909353eea09538aa28d671c046126ea417e8fdfe7de41c801e6660c49.jpg)  
Fig5Typical image of overcast   
图6少云类典型图像

Fig6 Typical image of cloudimage

在图像中选取6160张，对其进行了人工分类及标注。标注数据具体数量为:overlight(1124张）、overcast（1128 张）、rain_snow（1117 张）、cloudimage（1115 张）、dark（1119张）、bluesky（557张）。

# 2.3丽江天文观测站全天相机数据

中国科学院云南天文台丽江观测站是我国南方重要的天文观测基地。目前台站里拥有多台望远镜：2.4 米望远镜、1.8 米望远镜、BOOTES-4 和 TAT等，丽江天文观测站全天相机为这些望远镜的夜晚观测提供实时的云量信息，在天文观测中起着必不可少的辅助作用。本研究中采用丽江天文观测站全天相机数据进行分类模型的验证。

数据集选取2016年11月26日到2016年12月26日期间丽江观测站全天相机拍摄的全天空云图数据，共5208张，单张图像分辨率为 $7 2 0 ^ { * } 4 8 0$ 。按照2.2节中描述的分类标准对丽江数据进行了人工分类，用于验证模型在其他全天空地基云图数据集上的泛化能力。

# 3．分类模型介绍

卷积神经网络在图像识别领域拥有着巨大的优势，它可以直接使用图像的像素点作为输入，通过训练来提取最有效的特征，并且对缩放、平移、旋转等畸变具有不变性，有着很好的泛化效果。而卷积的权值共享结构，可以大幅减少神经网络的参数量，在防止过拟合的同时又降低了神经网络模型的复杂度。为此本研究对卷积神经网络中经典模型LeNet5 和AlexNet进行了改进，将其应用至全天相机数据的分类中。

# 3.1LeNet5与AlexNet

LeNet5[是Yann LeCun 在1998 年设计的用于手写数字识别的卷积神经网络模型，是最早的卷积神经网络模型之一。LeNet5 拥有如下特点：每个卷积层包含三个部分，分别为卷积、池化和非线性激活函数。模型使用卷积提取空间特征，并使用平均池化层进行降采样。使用双曲正切或S型激活函数，并以多层感知机（MLP）作为最后的分类器，且模型各层之间采用稀疏连接以减少计算的复杂度。该模型的许多特性至今仍在当前主流的卷积神经网络中被使用。

AlexNet[则是由Hinton 和他的学生Alex Krizhevsky 设计,它将LeNet的思想发扬光大，并把CNN的基本原理应用到了更深更宽的网络中。在2012年的ImageNet图像分类竞赛中AlexNet以显著优势获得冠军。

AlexNet成功的将ReLU作为激活函数，其效果在较深的网络中超过了常用的 Sigmoid 函数。模型训练时Dropout方法的使用减轻了模型过拟合的现象，结合使用重叠的最大池化避免了平均池化的模糊化效果。并提出将训练步长小于池化核的尺寸以提升特征的丰富性。同时随机地从 $2 5 6 ^ { * } 2 5 6$ 的原始图像中截取 $2 2 4 ^ { * } 2 2 4$ 大小的区域，最大限度扩大了数据量，减轻模型过拟合现象，提升模型的泛化能力。

# 3.2模型介绍及训练

本文对LeNet5和AlexNet模型的结构进行了组合优化，并在其基础上进行了模型参数的修改，其结构如图7所示。将卷积层层数设定为2，卷积核大小设为 $5 ^ { * } 5$ 。每个卷积层后连接一个核大小为 $3 ^ { * } 3$ 、步长为2的最大池化层,最后连接两个全连接层,并通过一个Softmax[8]层来确定最终分类结果。在全连接层使用Dropout方法随机忽略了一部分神经元以降低模型过拟合现象，在卷积层后使用ReLU作为激活函数。

![](images/1a0e3e57f974ebca24f5ec95fa23448480b7ce7ac6be6d7883efc73037b5f9d5.jpg)  
Fig7The structure of a convolutional neural network

# 4．分类模型训练

分类模型训练主要目标是通过对训练数据集的拟合获得神经网络的各项参数权重，以实现未来数据的分类预测，主要包括训练数据的预处理、拟合计算以及对模型效果的评价。

# 4.1数据预处理

在将训练数据输入至分类网络前，需首先对数据进行合适的预处理操作，使其符合模型输入要求，并最大限度的包含有效信息。预处理主要包括数据划分、兴趣区提取、数据增强、标准化四个部分。

# 4.1.1划分训练集与测试集

在人工标注好的6160 张图像中，bluesky类为 557张，其余类均在1000 张以上，由于较大数量的训练集是防止模型过拟合的关键因素之一，因此选取 bluesky 类别的图像 500 张，其余每类图像1000张作为训练集，余下图像作为测试集。训练集和测试集没有交叉图像，测试集数据不用于对模型的训练，仅用于测试模型对未知图像的分类准确度。

4.1.2获取感兴趣区域（region of interest，ROI)

将所有分辨率为 $1 0 0 0 ^ { * } 6 2 5$ 的原始图像(如图8左)做中心裁剪，去掉两端无关信息，裁剪后图像分辨率为 $8 0 0 ^ { * } 6 2 5$ （如图8右）。

![](images/3c900fef278e7ef14cdafdd20133d431f84410931258d25b821a92e4d2903235.jpg)  
图7卷积神经网络的结构  
图8对全天图像进行ROI裁剪，左图为裁剪前，右图为裁剪后

Fig8 Cropal-skyimages toget theROI.The image onthe leftis beforecropping.Theimageon therightiscropped

# 4.1.3数据增强

模型训练过程中，为了防止过拟合现象的发生，通常需要输入充足的数据量。在数据量较小的情况下，可以通过数据增强的方法，在保证数据特征不变的基础上对图像数据进行几何变换，以增加数据量。主要数据增强操作包含翻转变换、缩放变换、平移变换、尺度变换、对比度变换、噪声扰动、颜色变换等。

结合数据特征，本研究对训练集采取如下数据增强的方法：首先对训练集图像做偏移处理，分别以右下，右上，中心，左下，左上为坐标端点，裁剪大小为 $7 0 0 ^ { * } 5 5 0$ 的区域。再通过左右翻转操作，将数据扩充10倍(如图9)。对数量较少的无云晴空，增加上下翻转过程。最终得到每类10000张图像，从而实现训练数据各类样本数量均衡。

![](images/3ebef3fcb46cce56bafff491ee429c17cfc6f22370b00eb747e69f697059a34a.jpg)  
图9数据增强操作的部分示例

第一行分别是以右下，右上，中心，左下，左上为坐标端点裁剪后的图像第二行是对第一行图像进行左右翻转操作后图像

Fig9Data augmentation example

The first line is the image cropped at the lower right,upper right,center,lower left,and upper left.

The second line is the image after the left and right flip operations of the first line.

将经过上述操作的图像分辨率压缩至 $1 2 8 ^ { * } 1 2 8$ ，减小图像尺度，减轻模型训练负担。之后对图像进行随机截取，大小为 $1 0 0 ^ { * } 1 0 0$ ，相当于将数据量扩大了（128-100） $^ { 2 } { = } 7 8 4$ 倍。最后进行随机上下翻转，并随机改变图像对比度、亮度、饱和度、色调等特征，进一步扩大数据量。实验证明，使用上述数据增强手段将大大减轻过拟合现象，提升模型的泛化能力。此外，全天相机中拍摄到的雪龙号上固定景物翻转平移后将作为噪声存在，有利于提高模型的泛化能力。

对测试集数据的处理则是以图像中心为坐标端点，裁剪大小为 $7 0 0 ^ { * } 5 5 0$ 区域，再压缩至$1 2 8 ^ { * } 1 2 8$ ，最后做中心裁剪，得到分辨率为 $1 0 0 ^ { * } 1 0 0$ 的图像，以保证测试集图像中保留足够多的有效信息，并和训练集图像具有相同的输入尺度。

# 4.1.4标准化

在图像输入到网络前进行标准化处理，将会降低输入图像的冗余性，使得网络对图片的动态范围变化不敏感。主要有如公式（1）操作：

$$
i m g _ { _ { o u t } } = \frac { i m g _ { i n } - m e a n } { a d j u s t e d _ { s t d d e v } } \# ( 1 )
$$

179 其中 $i m g _ { i n }$ 为图片的RGB 三通道像素值，mean 分别为三通道像素的均值，adjustedstddev  
180 如公式（2）所示

$$
a d j u s t e d _ { s t d d e v } = \operatorname* { m a x } \left( s t d d e v , \ : \ : \frac { 1 . 0 } { \mathrm { s q r t } \big ( N u m E l e m e n t s \big ) } \right) \# \ : \ : \ : \frac { 1 . 0 } { 1 . 0 7 6 \times 1 . 0 7 5 } \ : \exp \left( - \frac { 1 . 0 } { 2 . 0 7 6 \times 1 . 0 7 5 } \right) .
$$

其中stddev为三通道像素的标准差，NumElements是三通道各自的像素个数。

训练集以及测试集数据经过标准化处理后，输入到模型网络中进行训练与测试。

# 4.2实验结果与分析

网络训练过程中，随着训练批次的增加，损失值（loss）逐渐下降，准确率（accuracy）不断上升（如图10）。

![](images/ef9291d5d72b96f90580aae06d71917f2d9f878d8f8d868d7af969f9e55ae6bc.jpg)  
图10 训练过程中的准确率与损失值变化曲线，横轴为训练迭代数，纵轴为损失值和准确率

Figl0LossadacuracyureoftrainingThezontalaxisisteumberoftrainingepohsandtheerticalisistelosalue and accuracy.

在选取合适训练批次大小以及学习率的情况下，模型loss值下降平稳，在训练迭代次数（epoch）达到50之后，下降速度明显放缓，模型逐渐收敛；当epoch达到100时，loss 逐渐趋近于0.15，并不再有明显下降。训练集以及验证集的 accuracy 整体趋势较为相像。在epoch 达到50之后，验证集accuracy逐渐趋于平稳，训练集accuracy在 $9 5 \%$ 与 $100 \%$ 之间不断波动，这是由于训练集图像在输入模型前进行随机的对比度，亮度变换等操作，导致在当前迭代次数下，模型并没有完全拟合所有可能出现的图像数据。训练在epoch达到220之后，验证集accuary 稳定为 $9 5 . 5 \%$ ，不再发生变化，表示模型已经收敛。

由于样本种类较多，并且存在数量不均衡的特点，因此，我们采用精确率（Precision）、召回率（Recall）以及F1-Score来进行分类效果的评判。精确率表示预测为正的样本里有多少是真正的正样本，即预测为正样本有两种可能，一种是将正类预测为正类（TP），另一

201 种是将负类预测为正类 $( F P )$ ），则精确率 $P$ 由公式（3）表示：

$$
P = { \frac { T P } { T P + F P } }
$$

召回率是针对原有样本而言的，它表示的是样本中的正例有多少被正确预测了，同样也有两种可能，一种是把原来的正类预测成正类（ $T P$ ），另一种就是把原来的正类预测为负类（FN），即召回率 $R$ 由公式（4）表示：

$$
R = { \frac { T P } { T P + F N } }
$$

F1-Score $( F I )$ 是精确率和召回率的调和均值，相当于精确率和召回率的综合评价指标，可由公式（5）推导：

$$
{ \frac { 2 } { F _ { 1 } } } = { \frac { 1 } { P } } + { \frac { 1 } { R } }
$$

变换后 $F l$ 可由公式（6）表示：

$$
F _ { 1 } = \frac { 2 T P } { 2 T P + F P + F N }
$$

各项类别的精确率、召回率和F1-Score如图11所示：

![](images/9ac12125b6e45c6522f634c7a281aa54016ba195bd47ba13520c190ce4f1e5b9.jpg)  
图11各项类别的精确率，召回率和F1-Score  
Figl1Precision,Recalland F1-Score for each category.

由图11可见,分类模型在各个类别都取得了非常好的效果,其分类精度、召回率、F1-score均达到了 $90 \%$ 以上，绝大多数类别均在 $9 5 \%$ 以上。

# 5．基于丽江观测站全天相机数据集的模型验证

# 5.1验证过程

为了验证模型的泛化能力，本研究采用了丽江观测站全天相机数据集对模型的分类能力进行了验证。在验证数据进入分类网络前，同样需要对数据进行预处理，全天空地基云图拍摄过程中，由于拍摄设备，相机参数的不同，图像尺度也会有所差异。对图像进行预处理操作，使得验证数据集在输入模型前尺度信息尽可能与训练数据一致，可以提高模型对数据的

分类准确率。

本研究对丽江观测站的 5208 张全天云图数据进行了人工标注，其中dark类别4257张、bluesky 类别 549张、overlight类别 519张、cloudimage 类别 321张、overcast类别115张、rain_snow类别46张。

原始图像（如图12左）分辨率为 $7 2 0 ^ { * } 4 8 0$ ，以图像中心为基准，截取 $4 0 0 ^ { * } 3 2 0$ 大小图像（如图12右），获取与训练数据近似长宽比的有效信息。之后再压缩至 $1 2 8 ^ { * } 1 2 8$ ，最后做中心裁剪，得到分辨率为 $1 0 0 ^ { * } 1 0 0$ 的图像，保持输入尺度与训练集图像一致。经过4.1.4中的标准化处理后，输入到模型中进行分类。

![](images/c8dddd1833327efa73b9bf8965341c88aa80f7ebca4f8a3e060ae064564bc32b.jpg)  
图12丽江站全天相机数据预处理样例，左图为原始图像，右图为裁剪后的图像

FiglAl-syimagesclassificationexampleofLjiang station,thelftistheoriginalpictureandtherightisthecropped image.

# 5.2预测结果及分析

模型对验证集各项类别分类结果的精确率、召回率、和F1-Score如图13。

![](images/a271686abc819e230d0d175776433a7908a2de2b0c3a8a31b85ec6aae573e3f5.jpg)  
图13验证集数据各项类别的精确率，召回率和F1-Score  
Fig13 Precision,Recall and F1-Score for each category of validationset.

结果显示，模型在全新数据集上有着不错的表现，对数量最多的dark类判定精准，并且在cloudimage，bluesky，overlight，overcast之间也有较好的区分能力。但对 rain_snow 类划分结果较差，并且bluesky 的召回率、overcast 的召回率、cloudimage 的准确率相对较低。

![](images/4e7ef7be04c1c8a238e28c68a12e48ea03f1c37b4b562c3667980b1c4859a645.jpg)  
图14测试集数据分类的混淆矩阵

从分类结果的混淆矩阵（图14）中可以看出，rain_snow大部分预测为overlight，误判图像如图15所示，雨滴数量较少且存在着严重的过曝光现象。模型更加关注到过曝光的特征，可能是误判的主要原因。此外，测试集中rain_snow类雨滴数量相较训练集明显减少，也可能是导致rain_snow类分类准确度整体较低的主要原因。

![](images/fda4739fb6eb7c148fd2c417db09ed615502469acbf1f05eb283cb2c672895ad.jpg)  
Fig14 Confusionmatrix for test set data   
Fig15Rain_snowmisjudged as overlight

由图14可知，bluesky 召回率，cloudimage 准确率较低的主要原因是一部分bluesky 被预测为cloudimage，典型误判图像如图16，根据对图像的观察，这些图像与训练集中的 bluesky有较大差异，图像整体偏暗，并且存在较明显三个污点，可能是导致误判的原因。

![](images/fcc116c995e17abc46507851f3a40a70fdee50980b5617836d64f0b534e69558.jpg)  
图15误判为overlight类的rain_snow类图像  
图16误判为cloudimage 类的bluesky类图像

此外overcast 的召回率较低。由图14 可知，overcast 主要误判为 overlight，典型误判图像如图17所示，误判图像亮度较高，整体特征与训练集中overlight类较为相近。区别主要是由于相机拍摄时的参数设置不同所致。

![](images/48359c3c612bb3e29df07fa4eea84dc88f914380158170f32b6ee5fa0377dd2a.jpg)  
图17误判为overlight类的overcast类图像 Fig17overcast misjudged as overlight

# 6.总结与展望

本文提出了可用于天文选址的基于卷积神经网络的全天空地基云图分类处理方法，使用雪龙号全天空地基云图数据集进行了分类模型的训练，并使用丽江天文观测站全天空地基云图数据对模型的泛化能力进行了验证，证明了模型在不同采集设备、不同采集地区及不同尺度的全天空地基云图数据集上，均能够具有较好分类效果，即模型具有较强的泛化能力以及良好的可移植性。该方法实现了任意地区地基云图的自动化分类，将极大的减少云量自动化处理的前期工作，降低天文选址过程中图像分类的人工成本。

全天相机拍摄过程中，由于硬件设备，拍摄参数，气象条件，外部环境等因素的影响，图像质量差异巨大，虽然雪龙号数据类型丰富，覆盖性强，但是从验证结果可以看出，训练集没有完全包含所有可能出现的数据类型，导致部分数据种类误判，如误判为overlight 类的 rain_snow 图像，误判为cloudimage 的 bluesky 类。

针对以上问题，可行的方法是使用迁移学习技术基于更多样化的数据进行分类模型的训练，可以有效提高分类精度，使得本分类方法在其它全天空地基云图数据集上有更好的表现。

致谢：本论文得到中国虚拟天文台和中国天文数据中心提供的数据资源和技术支持。中国天文数据中心得到国家科技部国家科技基础条件平台项目"地球系统科学数据共享服务平台"和"国家基础科学数据共享服务平台”（DKA2017-12-02-07）的资助。感谢国家天文台-阿里云天文大数据联合研究中心对本项工作的支持。感谢中国科学院云南天文台丽江观测站提供的数据资源。

# 284 参考文献

[1]施洋，姚永强，刘立勇．天文选址数字云量白天观测处理方法[J].天文研究与技术,2008,5(4):415-419.   
ShiY,YaoYQ,LiuLY.AMethodforObservingandCounting Day-time CloudAmounts inanAstronomical Site Survey[J]. Astronomical Research & Technology,2008.   
[2]彭焕文，辛玉新，寿圣，等．丽江天文观测站全天相机介绍[J].天文研究与技术,2015,12(1):000089-95.   
PengH,XinY,HeS,etlAnItrouctiotoeAl-kyCamraatteLijgstrooicalStatioJ]Astrooileach & Technology,2015.   
[3]Lecun Y,Bengio Y,Hinton G.Deep learning[J].Nature,2015,521(7553):436.   
[4]杨俊，吕伟涛，马颖，等.基于局部阈值插值的地基云自动检测方法[J].气象学报,2010,68(6):1007-1017.   
YANGJun,LUWeitao,MAingetal.Automaticgoundbasedoudetectiomethodbsedonthelocalresholdinteolatio]. ActaMeteorologicaSinica,2010,68(6):1007-1017.   
[5]漆随平，刘涛，胡桐，等．地基云观测技术及装备研究进展[J].山东科学,2014,27(6):1-9   
Sui-PingQI,Liu,TongHU,etal.Groundcloudobservationtechnologyaditsistrumentresearchadvances[J].ShandongSience, 2014.   
[6]LecunY,oouLioYtlGdtsedagdttcgio[J]ocngfe, 86(11):2278-2324.   
[7]KrizhevskyA,SutskeverI,HntonGE.ImageNetclasification withdeeconvolutionalneuralnetworks[C/ Inteational Conference on Neural Information Processing Systems.Curran Associates Inc.2O12:1097-1105.   
[8]Bishop C.Bishop,C.M.: Patern Recognition and Machine Learning.Springer[M]/ Stat Sci.2O06:140-155.

# Classification of all-sky camera data based on convolutional neural network

Cui Shun1², Xu Yunfei²³,Su Liying',Cui Chenzhou²,Fan Dongwei², Han Jun²,WangChuanzhong1², Zhang Lei23 (1CollegofMechanicalEngieringandAplicationElectronicTechnology,Beijing UniversityofTechnology,Beijg0024) (2 National Astronomical Observatories,Chinese Academy of Sciences,Beijing 100012) （3 University of Chinese Academy of Sciences 100049）

Abstract:Cloud volume is one of the first factors to consider in astronomical site selection. Ful-sky cloud images, which are captured by the al-sky camera, reflect local cloud information in real time.Therefore,it is one of the main data source for automatic classification of cloud volume. Automatic classification of all-sky cloud map is based on image quality,application background and other factors. It will reduce the labor cost in the data filtering process,and improve the accuracy of cloud volume detection. This paper implements an automatic classification method based on convolutional neural network classification model for full-sky cloud images,to provide an important aid for astronomical site selection. The clasification model training is carried out by using the all-sky camera data of the XueLong polar research vessel,and the model are also tested by using the data of Lijiang Observatory, CAS. Preferable classification results are obtained, and it is proved that the method has good transferability in different data sets.

Key words:astronomical site selection; cloud image classification; pattern recognition; convolutional neural network