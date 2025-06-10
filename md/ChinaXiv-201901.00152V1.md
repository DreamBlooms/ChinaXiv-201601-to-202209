# 基于改进的U-Net眼底视网膜血管分割

梁礼明，盛校棋，郭凯，邓广宏(江西理工大学 电气与自动化学院，江西 赣州 341000)

摘要：针对视网膜血管图像特征信息复杂程度高，现有的算法存在微血管分割较低和病理信息误分割等问题，提出一种融合DenseNet和U-Net 网络的血管分割模型。首先，通过限制对比度直方图均衡化和 filter滤波对图像进行血管增强处理；其次利用局部自适应Gamma 提升图像亮度信息并降低伪影的干扰；再次，由多尺度形态学滤波局部增强微血管特征信息；最后，利用U型密集连接模块进行分割。该算法在 DRIVE数据集上实验，其平均准确率、灵敏度和特异性分别高达 $9 6 . 7 4 \%$ 、 $8 1 . 5 0 \%$ 和 $9 8 . 2 0 \%$ 。

关键词：U型网络；视网膜；血管分割；形态学滤波 中图分类号：TP391.41 doi: 10.19734/j.issn.1001-3695.2018.09.0775

ImprovedU-Net fundusretinal vessels segmentation

Liang Liming†, Sheng Xiaoqi, Guo Kai, Deng Guanghong (SchoolofInformationEngineering Jiangxi UniversityofScience&Technology,GanzhouJiangxi341ooo,China)

Abstract: Inviewofcomplexing feature information inretinal vessls,andthe existing algorithmshavelow microvascular segmentationand pathological information mis-segmentation.Thus,avessels segmentation model basedon DenseNet and U-Net networks is proposed.First,image enhancementisperformedbyrestrictingcontrast histogramequalizationandfilter filtering.Secondly，using local adaptivegamma to improve retinal image brightness informationandreduce artifact interference.Then,multi-scalemorphologicalfltering locallyenhancesmicrovascular feature information.Finally,the optimized vessl image is segmented using a U-shaped dense connection module.The algorithm has an average accuracy, sensitivity and specificity of $9 6 . 7 4 \%$ $8 1 . 5 0 \%$ and $9 8 . 2 0 \%$ by experimenting on the DRIVE dataset Key words: U-Net; retinal; blood vessels segmentation; morphological filtering

# 0 引言

人的视网膜是一个具有极其丰富血管信息的光敏组织，且是唯一具有非入侵和非创伤可视化性质[]。通过对视网膜血管的数量、角度、分支、曲度等分析[2]，能够辅助医生诊断患者疾病。因此，视网膜血管系统的自动分析成为医学成像领域的热点话题。

大多数现有的无监督与有监督视网膜图像分割方法都依赖于手工制作的特征来表征血管和非血管像素之间的差异。如基于多尺度匹配滤波的眼底分割方法[3]，该方法利用分段线性近似呈高斯状强度分布的视网膜血管，在阈值化之前增强血管，虽然增强了大部分微小血管，但仍存在血管交叉处分割不足、病灶误分割等现象。Soares[4利用不同尺度2D-Gabor滤波是训练分类器实现血管像素检测的有效代替方案，但此法仍存在微血管分割断裂的问题。其他的特征还包括脊特征[5]、矩不变特征[6、局部相位特征[7]、COSFIRE滤波[8]等，可以较好地提取大部分血管特征，但抗噪性较差，异造成微血管分割断裂的现象。现有视网膜微血管通常具有较低的对比度，并且与宽血管的强度差异往往大于背景的变化。此外，还存在视盘、黄斑、病理和伪影等噪声的影响。虽然上述方法都取得了较好的分割效果，但是这些人为选择的特征在解决这两个问题时，仍然不能较鲁棒地解决血管变化趋势和血管信息的不变性，造成微血管分割不足、病灶与视盘误分割等问题。

近年来，基于深度学习的特征学习方法被广泛地应用于眼底视网膜血管分割，该类方法区别于人为的特征提取方法，需另选较优的分类器完成最后的血管分割。其中深度学习的卷积神经网络(convolutional neural network,CNN)将特征提取与分类器相结合，具有更好的泛化能力和鲁棒性[9]。Orlando[10]成功地将密集型条件随机场(conditionalrandomfield,CRF)模型与CNN相结合应用于视网膜血管分割，该模型在图像内部建立远程链接，因此较好解决了“收缩偏差"的问题，但存在病灶误分割的现象。Zhou[1]利用CNN提取血管特征和一组滤波器提升微小血管，最后利用密集型CRF进行血管分割，较好地解决了微血管分割不足的问题，但仍存在部分微血管断裂、血管易链结等现象。

针对上述算法存在的不足与经验，本文提出一种在U-Net[12]框架下的DenseNet[13]的分割模型，充分利用输出层的特征信息，并在网络中加入空洞卷积提高网络提取血管特征信息的能力，从而能更多的分割出微小血管。该方法融合限制对比度直方图均衡化(CLAHE)、filter滤波和多尺度形态学滤波增强主血管与微血管信息。通过局部自适应Gamma矫正，纠正视网膜伪影区域。最终将以上处理结果利用DenseNet-U-Net模型进行分割，较好解决了微小血管分割不足、视盘与病灶误分割的难题。本文算法总体流程图如图1所示。

![](images/ea8336637434eb8d5d3eaf968fea5f1ba0546c21613d23296bc2ae6a281fbf43.jpg)  
图1总体流程图  
Fig.1Overall flow chart

# 1 视网膜图像分割原理

# 1.1图像预处理

考虑到经过采集的视网膜图像存在光照不均匀、血管中心线反射等现象，从而造成微血管与背景对比度较低，进而使得算法鲁棒性不高，造成血管分割断裂和微血管分割不足等问题，故需对眼底视网膜图像进行预处理，才能获取较优异的血管特征，以便进一步处理。具体步骤如下：

a)提取彩色眼底图像血管与背景对比度较高的绿色通道，并利用双边滤波对其降噪。

b)对经过滤波去噪的绿色通道图像采取限制对比度直方图均衡化(CLAHE)，在抑制噪声的同时提升血管与背景的对比度，然后经filter滤波对图像进行全局锐化，抑制CLAHE增强后图像的伪影与黄斑等噪声影响，突显血管信息。

c)利用局部自适应Gamma矫正[14]，根据血管与背景的不同像素特征进行Gamma值匹配，将视网膜图像分区域进行矫正，使得光照不均匀因素与中心线反射现象加以抑制。

d)将经过自适应Gamma矫正的图像，通过多尺度形态学Top-Hot变换[15],进一步提升视网膜图像微血管信息。通过选取4个尺度，控制图像边缘梯度信息控制因子 $w _ { i }$ ，调整相邻血管像素尺度的差值，降低病灶与视盘等特征信息的干扰，提取微小血管的多尺度亮、暗细节特征。该模型定义如下：

$$
f _ { T } = I _ { r } + k \times \sum _ { i } ^ { n } w _ { i } ( D o p _ { i } - D c l _ { i } )
$$

其中： $k$ 是视网膜血管图像细节增强因子; $I _ { r }$ 为输入图像； $f _ { T }$ 为输出图像； $D o p _ { i }$ 与 $D c l _ { i }$ 分别为视网膜图像亮细节与暗细节特征。预处理结果如图2所示。

# 1.2 DenseNet-U-Net模型

本文针对现有U-Net网络易对微血管分割产生断裂与视网膜眼底图像特征复杂性，引入DenseNet网络，增加网络信息重复利用率，使U-Net网络分割模型能分割出更多的血管信息。为了解决U-Net网络编码与解码过程中不能较好保留图像细节特征而造成的微血管分割断裂的现象，引入新的卷积层，利用空洞卷积代替U-Net网络中的卷积层，从而使视网膜图像训练在较少样本情况下得到最优分割。

![](images/226795cae4dc25b1a8207a9251efb3c765dd6660171213435102117dc67a0758.jpg)  
图2预处理各阶段结果图  
Fig.2Preprocessing results for each stage

1.2.1U-Net模型

U-Net卷积神经网络的核心思想是利用较少的训练集进行端对端的训练，并且能有较好的输出结果。这种结构首先去掉了传统的全连接卷积神经网络(fully connected neuralnetwork,FCN)[16]冗余的全连接层，只保留有效的卷积层，进而可以大幅度降低训练时间。然后，将网络中部分层的上采样层利用池化层代替，提高图片输出分辨率。最后，利用远程连接方式同时结合底层和高层信息，底层信息有助于提高训练精度，高层信息用来提取复杂特征，使得较浅层的网络可以完成深层网络的效果，得到更多的视网膜血管分割的细节。但该网络不能很好的恢复经池化层之后的图像细节结构信息，易造成微血管分割断裂的现象。

# 1.2.2DenseNet模型

DenseNet的密集连接模块能将训练阶段视网膜血管图像的前层与本层的特征信息相结合作为下一层的输出，缩短前后层之间的距离，跨层连接时采用Concatenate代替Elewise-wise操作，从而加强的特征传播的能力，使得网络特征重用，有利于减少网络参数和层数，降低算法整体复杂度。设DenseNet的密集连接模块能将训练阶段视网膜血管图像的前层与本层的特征信息相结合作为下一层的输出，缩短前后层之间的距离，跨层连接时采用Concatenate代替Elewise-wise操作，从而加强的特征传播的能力，使得网络特征重用，有利于减少网络参数和层数，降低算法整体复杂度。设 $l$ 层的输出为 $x _ { l }$ ，则该模型第 $\mathbf { \xi } _ { l }$ 层的输出定义为

$$
x _ { l } = H _ { l } ( [ x _ { 0 } , x _ { 1 } , ^ { \ldots } , x _ { l - 1 } ] )
$$

其中: $[ x _ { 0 } , x _ { 1 } , \cdots , x _ { l - 1 } ]$ 表示 $_ { 0 , 1 , \cdots , l - 1 }$ 层输出的特征层合并， $H _ { l } ( \bullet )$ 表示第 $\mathbf { \xi } _ { l }$ 层的非线性映射，是多种操作的组合 $B N  R e L U  C o n \nu$ u该模型可以较好地缓解梯度消失的问题，能够充分利用网络中所有输出特征图的信息。

# 1.2.3空洞卷积

传统卷积神经网络的池化层有利于降低图像尺寸、增加特征图步长，但存在视网膜图像细节信息丢失，从而导致微血管分割不全和易发生断裂等问题[17]。U-Net 网络通过上采样过程解决此问题，但网络层数越多其特征图也会越多，因此此法并不能较好的恢复原图像的细节信息。故本文采用文献[18]提出的空洞卷积代替传统的卷积层，使本文算法能保留更多的图像细节信息，提升算法的泛化能力。

空洞卷积能以不增加算法参数复杂度的情况下使池化层拥有更大的感受野信息，并将图像全局信息都可以加以利用。其基本原理是在传统卷积核的每个像素之间插入值为0的像素，即增加网络的扩张率r。如图3所示，设一个卷积核为 $3 { \times } 3$ ，当 $\scriptstyle \mathbf { r } = 1$ 时的空洞卷积核，当 $\scriptstyle \mathbf { r } = 2$ 时为一个 $5 { \times } 5$ 的空洞卷积核。

![](images/e0cf8f648f623f46692dfb430bae0104452a980c0650071ff9dcae819f004948.jpg)  
Fig.3Sketch map of dilated convolution

1.2.4DenseNet-U-Net模型

针对现有卷积神经学习网络存在储存开销大、计算效率低小等不足，本为提出将U-Net与DenseNet相结合，设计了一个U型密集链接模块(U-Netdense block,UDB)。该模型结合二者的优势，提高了网络的泛化性能，在减少训练时间的同时使得网络中每一层的血管特征都能得到充分利用，较好地解决了眼底视网膜图像存在病变与伪影的干扰，从而能更多的保留血管特征信息，获取更多微小血管，而且在训练集较少的视网膜图像中不易发生过拟合现象，提高了测试集的分割精度，具有较强的鲁棒性。本文算法网络模块如图4所示。

![](images/21d9b6ee6effe525352bdbf073172b7a6c50ece0f0f8041814369bfa3ffa6c11.jpg)  
图3空洞卷积示意图  
Fig.4U type dense module (UDB)

该模型以U-Net网络为主要框架，DenseNet为辅。其中BN表示批量归一化(batchnormalization,BN)用来降低模型训练中的协变转移，防止由于视网膜图像存在病理性噪声造成梯度消失，并且很好地保持原有模型的表达能力；MaxPool表示池化层用来压缩特征图，降低复杂度；Up-convz表示上采样卷积，在每一个上采样后跟一个卷积，降低特征通道数。Conv表示卷积层，每一个卷积层利用线性修正单元(rectifiedlinearunit,ReLU)进行特征提取，ReLU能有效减少反向传播过程的梯度消失，降低网络计算复杂度，使得训练数据获得一定的稀疏性，其定义如下：

$$
R e L U ( x ) = m a x ( x , 0 )
$$

由式(3)可知当 $x < 0$ 时数据出现硬饱和状态，当 $x { > } 0$ 导数值恒为1，从而可以缓解在训练过程中梯度消失的问题。

该网络结构每个小块内均采用DenseNet的密集链接网络以确保最大的信息流，使得整个网络信息传播路径变得更短，因此可以减少输出层的特征数目，降低的训练时间复杂度。每个函数 $H _ { l } ( \bullet )$ 会产生 $k$ 个特征图则 $\mathbf { \xi } _ { l }$ 层会具有 $k _ { 0 } + k ( l - 1 )$ 特征图映射，DenseNet 网络可以设定一个固定增长率 ${ \mathrm { K } } ^ { [ 1 3 ] }$ 来防止网络变得过宽，进一步提高网络的性能，从而可以提高小数据集训练的抗过拟合性。而U-Net的远程链接网路将编码部分和解码部分链接，确保低级信息加以利用。其中，在U-Net模型中卷积层利用空洞卷积增加数据的感受野，但多个相同空洞卷积层叠加存在数据连续性差的特点，故本文使用多种扩张率的组合，如在第一个U型密集连接网络使用扩张率为1，2组合的空洞卷积。

# 1.2.5训练与分割

本文视网膜血管分割模型的可大致分为编码器与解码器两大部分，主要目的是分类血管相邻的每一个像素将血管与背景分割。设经预处理的输入图像为 $I _ { p }$ ，将该图片进行归一化处理，公式定义下：

$$
I { = } \frac { I _ { p } - { \upsilon } } { \sigma }
$$

其中： $\upsilon$ 和 $\sigma$ 分别表示数据的平均值与标准差。

然后，将归一化后的图像输入编码器部分。先经过带有7个UDB结构的网络层，设每次输出层的增长率 $K { = } 1 2$ 。每一结构包含两个空洞卷积层和一个 $2 \times 2$ 池化层进行下采样将特征图降维到原来的 $\%$ ，再将其输出加一个密集连接模块以便将训练所得血管特征重复利用。其次，由核大小为 $3 { \times } 3$ 上采样层进行图像解码，为防止上采样解码部分恢复原图像时信息丢失，使用一个DenseNet结构模型连接编码输出部分使得与上采样层相同深度的特征层进行求和（如图5所示)。最后，由softmax 激活函数将血管与背景分类。

![](images/6f1159f46d2a77fbb632b8ccc4b1932e95aae354bdbf1f8623fd1d55e96f82e0.jpg)  
图4U型密集模块(UDB)  
图5上采样合并特征过程图  
Fig.5Upsampling merge feature process diagram

# 2 实验结果与分析

本实验的仿真平台为PyCharm,使用keras及其TensorFlow端口，计算机配置为Intel(R)CoreTMi7-7700CPU@3.6GHz，16 GB内存，Nvidia GeForceGTX1080 GPU,采用64bitWin10。

# 2.1 数据集

本文在 DRIVE[19](digital retinal images for vesselextraction)数据集上选取专家第一专家手动分割的眼底血管图像作为训练标签，第二专家手工分割的眼底图像作为最终分割结果参考标准进行实验。

DRIVE于2004年由Niemeijer团队建立，分别包括20幅训练集图片和20幅测试集图片，其分辨率均为 $5 6 5 \times 5 8 4$ 。每幅图像对应两位专家的手动分割结果（金标准）。

由于视网膜图像数据集过少，本文将图像以45为旋转角度，将训练集扩充原来的5倍，以进一步降低训练过程过拟

合现象。

# 2.2网络参数

本文采用 $4 8 \times 4 8$ 的滑动窗口，步长为15，迭代100次即可达到理想训练精度。通过交叉验证来最小化像素分割错误率，采用Adam 算法[20]优化损失函数，其学习率为0.001。其中交叉验证定义如下：

$$
{ \cal J } _ { _ { C E } } \left( y , \overline { { y } } \right) = - \sum y _ { i } \log \overline { { y } } _ { i } + ( 1 - y _ { i } ) \log ( 1 - \overline { { y } } _ { i } )
$$

其中: $i$ 表示分类个数， $y$ 为金标准， $\mathit { \Pi } _ { y } ^ { - }$ 预测数据。

# 2.3性能评价指标

为了系统定量的分析本文算法分割结果的性能，本文采取以下三个指标作为衡量标准：

$$
S e n s i t i \nu i t y = \frac { T _ { P } } { T _ { P } + F _ { N } }
$$

$$
S p e c i f i c i t y = \frac { T _ { N } } { T _ { N } + F _ { P } }
$$

$$
A c c u r a c y = { \frac { T _ { p } + T _ { N } } { T _ { p } + T _ { N } + F _ { p } + F _ { N } } }
$$

其中: $T _ { p } , T _ { N } , F _ { p } , F _ { N }$ 分别表示真阳性、真阴性、假阳性、假阴性。敏感度(sensitivity),又称真阳性率表示正确分类血管像素占真实血管像素的百分比；特异性(specificity)表示正确分类的非血管像素占真实非血管像素的百分比；准确率(accuracy)表示正确分类血管和非血管像素占整个图像总像素的百分率，

ROC(receiver operatingcharacteristic)曲线是一种重要衡量血管分割结果综合性能的标准，其横轴以假阳性率(falsepositive rate,FPR),纵轴以真阳性率(true positive rate,TPR),反映不同阈值下二者的变化趋势，其值越大说明算法的分割性能鲁棒性越优异。

# 2.4主观分析

图6展示了本文算法与文献[21]在DRIVE数据集上的部分图像的分割效果图。其中图6第一行与第三行图片为DRIVE数据集第二与第四张健康视网膜图像，第二行与第四行图片为DRIVE数据集第三与第八张病变视网膜图片。图6中，(a)为原始图像， (b)为第二专家金标准图像， (c)为文献[21]利用全连接CRFs算法进行血管分割图，(d)为本文算法分割图像。

观察图6第一行与第三行健康视网膜图像可知，本文算法与文献[21]均取得较理想的分割结果，但文献[21]出现部分微血管断裂和视盘被误分割的现象，然而本文算法在微血管处分割数目较多且很好地解决了血管断裂的问题，基本避免了视盘被误分为血管的可能。本文算法对比图6(b)标准图像，可以看出本文算法的微血管分割结果的粗细相当，不会出现文献[21]微血管分割偏粗的现象，并且在微血管部分能分割出比金标准给更多的细节结构。

由图6第二行与第三行病变视网膜图像可观察到此类视网膜图像存在一定量的硬性渗出物且总体图片较暗，尤其第四行的图片视盘与病灶的干扰因素较为严重。文献[21]的分割结果存在大量的病灶，尤其在第四行病变图像鲁棒性较差，实盘区域基本分割失效，而本文算法分割结果基本解决了视盘中心与硬性渗出物的影响，较好地还原了视网膜图像的血管结构。

为了更进一步清晰地展现出本算法的优势，给出与第一专家分割为基准，在不同颜色下的血管对比图。其中绿色为分割正确的血管，红色为分割错误的血管，蓝色为多分割或误分割的血管。对比效果图如图7所示。

由图7可以看出本文算法相比文献[21]CRFs算法与文献[22]传统U-Net 算法能更多的分割出微小血管且微小血管不易断裂，误分割率较低。CRFs算法在视盘处蓝色区域明显，而且多分割出的部分均为误分割，造成假阳性过高。

![](images/53d4730ae570f46bba8e5dc2eb49f33d94dc0108825f8b0e400ec61ae5d19d18.jpg)  
图6不同算法分解结果比较

![](images/ae01878bc8e4370f0c6a5f5b18086222227109022ec0cc8a615683d94ad73007.jpg)  
Fig.6Comparison of decomposition results by different algorithms   
图7其他算法与本文算法彩色对比图  
Fig.7Color comparison of other algorithms with this algorithm

综上所述，可见本文算法不仅在健康视网膜图像上有较好的分割性能，在病变视网膜能理想的分辨出病灶与血管特征，具有较强的鲁棒性和泛化能力。对于主血管末端的微小血管能较好的连通性与完整性，且分割结果不会出现过粗的现象，进一步说明本文算法在保持较高精度与灵敏度的情况下，能分割出较多的血管，拥有一定的临床应用价值。

# 2.5 客观分析

本文算法与其他文献的敏感度、特异性和准确率对比如表1所示，其中加粗的数据为本文算法。

表1不同文献之间性能数据对比  
Table 1 Comparison of performance data between different documents   

<html><body><table><tr><td>Method</td><td>Acc</td><td>Sen</td><td>Spe</td><td>Auc</td></tr><tr><td>文献[9]</td><td>0.9556</td><td>0.8036</td><td>0.9778</td><td>0.9800</td></tr><tr><td>文献[11]</td><td>0.9469</td><td>0.8078</td><td>0.9674</td><td>------</td></tr><tr><td>文献[22]</td><td>0.9636</td><td>0.7802</td><td>0.9876</td><td>0.9772</td></tr><tr><td>文献[23]</td><td>0.9467</td><td>0.7731</td><td>0.9724</td><td>0.9588</td></tr><tr><td>文献[24]</td><td>0.9502</td><td>0.7410</td><td>0.9894</td><td>-----</td></tr><tr><td>文献[25]</td><td>0.9382</td><td>0.5686</td><td>0.9926</td><td>------</td></tr><tr><td>本文算法</td><td>0.9674</td><td>0.8150</td><td>0.9820</td><td>0.9808</td></tr></table></body></html>

由表1可知现有的算法在DRIVE 数据集上的血管分割准确率、灵敏度和AUC值均低于本文算法，说明本文算法

在该数据集上有较强的鲁棒性。文献[9]将残差学习和密集连接网络相结合的方法其 AUC 值基本与本文算法持平，但本文算法在灵敏度与准确率方面远高于此文献。文献[22]利用基本的U-Net网络结构，得到的分割精度与本文算法差距较小，其特异性高于本文约0.0056左右，几乎达到可以忽略的优势，但本文算法AUC值与灵敏度远高于传统U-Net网络结构的血管分割结果，说明本文算法加入DenseNet与空洞卷积的必要性。文献[24，25]采用机器学习算法得到的特异性微高于本文算法，但本文的灵敏度远高于文献[24，25]，说明UDB模型能分割出更多的微小血管，鲁棒性较强。

为了更直观地表现出本文算法的优势，给出图8所示ROC曲线走势图。由ROC曲线可以看出本文算法总体性能优越，假阳性率低，真阳性率较高，存在血管误分割可能小。

![](images/585d353467439ee60da3a982eeee638126b7730b62be7a2567a379527d1cbf04.jpg)  
图8DRIVE 数据集ROC 曲线图Fig.8ROC chart of DRIVE dataset

图9给出本文算法与其他视网膜分割算法的ROC性能曲线对比图。其中UDB为本文算法,DRIU（deep retinal imageunderstanding）、HED(Holistical-nestednetwork)为深度学习算法，wavelets为机器学习小波变换算法。从总体来看深度学习算法远优于传统机器学习算法，但存在训练时间过长的特点。但本文UDB算法能在保证合理训练时间的情况下得到最优分割结果，100张图训练仅用6h，测试阶段平均每张图为22s左右。

![](images/8a77a65f936209e672d839b2da533dccb3dc13032b28c05d9cb4ae58a5e8b8aa.jpg)  
图9其他算法ROC 曲线比较图Fig.9Comparison of ROC curves for other algorithms

# 2.6客观分析

本文通过改变网络结构对本文算法进一步评估。由于仅使用U-Net 网络结构通过文献[22]已经得出了分割结果，故本文在UDB 结构中去掉空洞卷积换成传统卷积层得到分割结果ROC曲线，如图10所示。

![](images/90ed3b0ea05013417b5241a84febb68ef8b6190ed72381d8092d682144564418.jpg)  
图10传统卷积层的UDB网络结构ROC曲线图 Fig.10ROC curve diagram of UDB network structure with traditional volume layer

由图8与10相比较可知在网络中使用空洞卷积层增加感受野比传统卷积层能得到更好的血管分割效果，由表1中文献[22]与图10可知仅加入DenseNet网络结构就远优于传统U-Net模型的分割结果，因此更能体现出本文总体算法的优越性。

# 3 结束语

眼底视网膜血管分割是医学领域人工分析走向自动诊断的重要过程。本文针对现在视网膜血管自动分割算法存在微血管分割不足、病灶与视盘易被误分割为血管的假阳性现象，提出一种基于DenseNet和U-Net网络的视网膜血管分割算法首先利用限制对比度直方图均衡化(CLAHE)、fiIter滤波增强整体视网膜图像对比度；然后利用局部自适应Gamma矫正视网膜图像的伪影；再后利用多尺度形态学滤波局部增加血管与背景的对比度，进一步增加后续算法微血管处分割的鲁棒性；最后采用本文改进的U-Net网络进行血管分割，得到最终分割结果。本文分割算法将密集型连接网络引入到U-Net模型中，增加了特征信息的重复利用率，提高了分割结果的准确率，且极大的降低网络参数的复杂度。并且利用空洞卷积代替传统卷积层增加池化层的感受野，能更好的提高算法的灵敏度，防止微血管分割断裂。该算法分割结果不需进行额外的后处理过程，说明算法对DRIVE数据集具有很好的鲁棒性和有效性。但对于带有病灶图片仍会出现血管分割断裂的现象，如何进行提取病灶并修复病灶处血管断裂问题仍是以后视网膜血管分割研究需进一步解决的问题。

# 参考文献：

[1]Zheng Yalin,KwongMT,MacCormickIJC,etal.A comprehensive texturesegmentation framework for segmentation of capillary non-perfusion regions in fundus fluorescein angiograms[J].Plos One, 2014,9 (4): e93624.   
[2]梁礼明，黄朝林，石霏，等．融合形状先验的水平集眼底图像血管分 割[J].计算机学报,2018，41(7):1678-1692.(Liang Liming,Huang Chaolin,Shilin,et al.Fusion of shape priori level set for fundus image vascular segmentation [J]. Journal of Computer Science,2018，41(7): 1678-1692.)   
[3]Rawi M,Qutaishat M,Arrar M.An improved matched filter for blood vessel detection of digital retinal images [J].Computers in Biology & Medicine,2007,37(2):262-267.   
[4]Soares JV B,Leandro JJG,Cesar R M,et al.Retinal vessel segmentation using 2-D Gabor wavelet and supervised classification [J].

IEEE Trans on Biomedical Engineering,2012,59 (9):1214-1222.

[5]Staal J,M. D. Abramoff,Niemeijer M,et al. Ridge-based vessel segmentation in color images of the retina [J].IEEE Trans on Medical Imaging,2004,23 (4):501-509.   
[6] Marin D,Aquino A,Gegundez-Arias M E,et al.A new supervised method for blood vessel segmentation in retinal images by using gray-level and moment invariants-based features [J]. IEEE Trans on Medical Imaging,2011,30(1): 146.   
[7]Gunnar N,Jonasson J,Borga M.Blood vessel segmentation using multi-scale quadrature filtering [J]. Pattrn Recognition Letters,2010, 31 (8): 762-767.   
[8]Azzopardi G,Strisciuglio N, Vento M,et al. Trainable COSFIRE filters for vessel delineation with application to retinal images [J].Medical Image Analysis,2015,19 (1): 46-57.   
[9]吴晨玥，易本顺，章云港，等．基于改进卷积神经网络的视网膜血管 图像分割[J]．光学学报，2018,38(11):1111004.(Wu Chenyu,Yi Benshun, Zhang Yungang,et al.Retinal vascular image segmentation based on improved convolution neural network [J]. Journal of Optics, 2018,38 (11): 1111004.)   
[10] Orlando JI, Prokofyeva E,Blaschko M B.A discriminatively trained fully connected conditional random field model for blood vessel segmentation in fundus images [J].IEEE Trans on Bio-medical Engineering,2016,64 (1): 16-27.   
[11] Zhou Lei,Yu Qi,Xu Xu,et al. Improving dense conditional random field for retinal vessel segmentation by discriminative feature learning and thin-vessel enhancement.[J].Computer Methods & Programs in Biomedicine,2017,148:13-15.   
[12] Ronneberger O,Fischer P,Brox T.U-Net: convolutional networks for biomedical image segmentation [C]//Proc of International Conference on Medical Image Computing and Computer-Assisted Intervention. Cham: Springer,2015:234-241.   
[13] Huang Gao,Liu Zhuang,Van Der Maaten L,et al.Densely Connected Convolutional Networks [C]/Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC: IEEE Computer Society,2017:2261-2269..   
[14]储清翠，王华彬，陶亮．图像的局部自适应Gamma校正[J].计算机 工程与应用,2015,51(7):189-193.(Chu Qingcui,Wang Huabin,Tao Liang.Local adaptive Gamma correction of images [J].Computer Engineering and Applications,2015,51(7): 189-193.）   
[15] 刘艳莉，桂志国．多尺度 top-hat 变换提取细节的对比度增强算法 [J]．计算机工程与设计，2014，35(4): $1 3 3 2 - 1 3 3 5 + 1 3 4 0$ .(Liu Yanli, Gui Zhiguo.Contrast enhancement algorithms for extracting details by multiscale top-hat transform [J]. Computer Engineering and Design, atry via deep learning network and fully-connected conditional random fields [C]// Proc of the 13th IEEE International Symposium on Biomedical Imaging. Piscataway,NJ: IEEE Press,2016: 698-701.   
[17] Shelhamer E,Long J,Trevor D.Fully convolutional networks for semantic segmentation [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition．Washington DC:IEEE Computer Society,2015: 3431-3440.   
[18] Chen L C,Papandreou G,Kokkinos I,et al. DeepLab: semantic image segmentation with deep convolutional nets,atrous convolution，and fully connected CRFs [J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2018,40 (4): 834-848.   
[19] Staal J，Abramoff M D,Niemeijer M,et al.Ridge-based vessel segmentation in color images of the retina [J].IEEE Trans on Medical Imaging,2004,23 (4): 501-509.   
[20] Kingma D P,Ba J.Adam: a method for stochastic optimization [C]//Procof the3rd International Conferenceon Learning Representations.2015: 1-15.   
[21] Orlando JI,Blaschko M.Learning fully-connected CRFs for blood vessel segmentation in retinal images.[C]//Proc ofInternational Conference on Medical Image Computing and Computer-Assisted Intervention.Springer International Publishing,2014: 634-641.   
[22] Gao Xurong,Cai Yiheng,Qiu Changyan,et al. Retinal blood vessel segmentation based on the Gaussian matched filter and U-net [C]//Proc of the 10th International Congress on Image and Signal Processing, Biomedical Engineering and Informatics .IEEE,2018.   
[23] Strisciuglio N,Azzopardi G，Vento M,et al.Supervised vessel delineation in retinal fundus images with the automatic selection of B-COSFIRE filters [J]. Machine Vision & Applications,2016,27 (8): 1137-1149.   
[24]蔡震震，唐鹏，胡建斌，等．基于PST 和多尺度高斯滤波的视网膜 血管的分割[J/OL].计算机应用研究，2019，36（7）．http://www. arocmag.com/article/02-2019-07-059.html.(Cai Zhenzhen,Tang Peng, Hu Jianbin,et al. Segmentation of retinal vessels based on PST and multi-scale Gauss filtering [J/OL]. Application Research of Computers, 2019,36(7).htp://www.arocmag.com/article/02-2019-07-059. html)   
[25]汪维华，张景中，吴文渊．改进的形态学与Otsu 相结合的视网膜 血管分割[J/OL].计算机应用研究，2019，36（8）．htp://www. arocmag.com/article/02-2019-08-061．html.(Wang Weihua,Zhang Jingzhong,Wu Wenyuan.Improved morphology combined with Otsu for retinal vascular segmentation [J/OL].Application Research of Computers, 2019,36（8） http://www. arocmag. com/article/02-2019-08-061.html..)