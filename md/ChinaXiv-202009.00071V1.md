# 基于卷积神经网络的语义分割算法研究\*

熊炜1,2†，童磊1，金靖熠1，王传胜'，王娟1，曾春艳1(1.湖北工业大学电气与电子工程学院，武汉 430068;2.美国南卡罗来纳大学计算机科学与工程系，南卡 哥伦比亚29201)

摘要：针对语义分割中残差网络并不能完好地提取图像信息和分割效果差的问题，提出一种联合特征金字塔模型(JFP)用来融合残差网络的输出特征，并结合暗黑空间金字塔池化模型(ASPP)进一步提取特征，在解码部分，应用简单的解码结构，恢复图像尺寸完成语义分割，同时引入注意力模型作为辅助语义分割网络，辅助神经网络进行训练。该方法分别在Pascal VOC 2012数据集和增强的PascalVOC 2012数据集对网络进行训练，并在Pascal VOC 2012的验证集上进行测试，其平均交并集之比(mIoU)分别达到了 $78 . 5 5 \%$ 和 $8 0 . 1 4 \%$ ，表明所提方法具有良好的语义分割性能。

关键词：图像语义分割；联合特征金字塔模型(JFP)；暗黑空间金字塔模型(ASPP)；注意力模型 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2019.12.0705

Research on semantic segmentation algorithm based on convolutional neural network

Xiong Wei1,2†, Tong Lei1, Jin Jingyi, Wang Chuansheng1,Wang Juan1, Zeng Chunyan1 (1.SchoolofElectrical&ElectronicEngineering,HubeiUniversityofTechnologyWuhan43068,China;2.Dept.of Computer Science & Engineering,University of South Carolina, Columbia,SC 29201, USA)

Abstract: Inorder tosolvetheproblemthattheresidualnetworkcannot extract imageinformationwellandthesegmentation effectis poorinsemanticsegmentation,tis paperproposedajointfeaturepyramidmodel(JFP)to integrate theoutput features oftheresidual network,and then further extractthe features incombination with theatrous spatialpyramid poling module (ASPP).Inthedecodingpart,thispaperappliedasimple decoding structuretorecovertheimagesize tocompletethesemantic segmentation This paper also used atention moduleas the auxiliary semantic segmentation network toasist the training of theneural network.This method trains thenetwork in thePascal VOC20l2 data setand theenhanced Pascal VOC2012data setrespectively,andtestsitonthe verificationsetofPascal VOC2012.TheaverageratioofintersectionandUnion (Miou) is $78 . 5 5 \%$ and $8 0 . 1 4 \%$ respectively, which shows that proposed method has good semantic segmentation performance.

Key words: image semantic segmentation; joint feature pyramid module (JFP);atrous spatial pyramid pooling module (ASPP); attention module

# 0 引言

图像的语义分割是对图像进行像素级别的分割，需要对图像的每一个像素从语义上进行分类[1,2]，同一类别的像素分成同一类别标签，体现在分割结果上就是同一类别的物体属于同一个颜色标签，而不同颜色就是不同类别的物体。

卷积神经网络(CNN)的应用使得图像语义分割快速得到发展，各种基于卷积神经网络的语义分割网络结构被提出。加州大学伯克利分校的Long 等人[3]提出的完全卷积网络(FCN)，去掉了CNN末端使用的全连接层[4]，使得网络最后生成的不是固定的特征向量，而是可以变换尺寸的特征图像，最后进行逐像素的分类以达到语义分割的目的，类似FCN[5]的思路贯穿在语义分割的研究当中。

FCN之后，Badrinarayanan等人[提出了SegNet，用于图像语义分割，是一种深度卷积编码解码架构[7]，并跟随着一个像素级别的分类层，编码过程通过池化逐渐减少位置信息并提取图像更深层的特征，这个过程逐渐缩减输入图像的空间维度，而译码过程会逐渐恢复位置信息，并恢复原有空间维度和对图片进行分割，改进编解码模型[8]也是一些研究的方向。

由于语义分割是逐像素的分类过程，卷积操作使得网络的参数量变大，常常需要加入池化层[9]对图像进行降维处理，以减少参数，这又会产生图像信息丢失的问题，而进行语义分割必须要保持与原图像的像素对齐，每个像素的信息都有意义，这是语义分割面临的最大问题。继而Yu等人[10]提出了膨胀卷积，又称空洞卷积[I，通过这个卷积操作聚合更大尺度的信息，同样的卷积核尺寸，空洞卷积有更大的感知域，有效地解决了语义分割中信息丢失的问题。

此外，如何设计一个神经网络模型也是语义分割研究中的主要内容。金字塔池化模型(ASPP)[11,12]通过应用几个不同核心尺寸的空洞卷积层来扩大感知域，得出不同尺度的特征图，结合并转换成固定大小的特征图，有效地提取了图像的空间尺度信息，不过却增加了网络模型的大小，而Li等人[13]引入注意力机制，重新设计了一种注意力金字塔模型(PAN)，进一步提取语义信息，效果进一步提升。Yu等人[14]从网络层次的信息聚合出发，详细介绍并总结了不同网络层的连接方式，再此之上设计了迭代深度聚集(IDA)和分层深度聚集(HAD)模型，通过IDA和HAD的组合连接，可以设计不同深度和不同连接的深层聚集(DLA)模型进行语义分割，同时这种方法可以加入其他模型中，完成不同的任务。

目前这些网络模型绝大部分都采用了深度卷积神经网络(DCNN)作为骨架网络，在此基础上设计针对图像语义分割的特定神经网络模型，但是DCNN也不能完整的提取图像的特征，存在信息丢失的问题，为解决这个问题，本文以ResNet101为骨架网络，设计了联合特征金字塔(JFP)模型，结合文献[11,12]中的ASPP模型作为编码结构，以更加完整的提取图像的特征，建立一个简单的解码结构恢复图像信息，为训练本文的语义分割网络模型，损失函数使用SoftMaxCrossEntropy，激活函数使用ReLu函数，设计了一个注意力模型作为辅助网络，使网络能更快速的收敛，最终组成本文的图像语义分割方法，提高语义分割的性能。

# 1 本文方法介绍

# 1.1总体框架

本文的总体框架如图1所示，首先选择ResNet101作为骨架网络进行特征提取，提出了一个JFP模型将ResNet101输出的后三层进行联合，完善ResNet101对特征的提取，解决图像信息丢失的问题；然后将JFP的输出接入ASPP模型进一步提取图像的空间尺度信息，这部分作为编码结构能够更好的对图像信息进行提取；最后应用简单的解码结构将神经网络的输出图像恢复为原始大小，完成对图像的语义分割;同时，本文设计了一个注意力模型作为辅助语义分割网络，将这个模型的损失函数与语义分割网络的损失函数结合，辅助网络进行训练，提升训练模型的效果。

![](images/87b0be95da618ed4258f6d7d1dad10dab61f6415fb73199adaaae1169c997203.jpg)  
图1本文总体框架Fig.1Overall framework

# 1.2联合特征金字塔模型(JFP)

本文提出的JFP模型如图2所示。首先，ResNet101输出的最后三层分别为block1、block2和block3，这三层的输出尺寸减半而深度增加一倍，将这三层的输出分别通过一个卷积，其中，卷积核尺寸为3，激活函数为ReLu，在图像边界进行1个像素值为0的填充，从而不改变输出图像的尺寸，加入批量归一化处理，采用dropout为0.3以防止过拟合，卷积核的深度为512，使得输出的深度都变成512，然后分别通过空洞卷积率为1、2和4的 $3 { \times } 3$ 卷积，其中像素填充分别与空洞卷积率相同，不采用dropout 处理，其中空洞卷积率为2和4的卷积输出还要在图像边界加入2和4个像素值为0的填充，保持输出尺寸与输出的相同，加入双线性插值，对这两个输出进行调整，使得输出的尺寸与block1相同，由ResNet101的三层输出经过不同的卷积处理得到三个尺寸与深度相同的输出，与block1层的输出尺寸与深度相同，最后将这三个输出与block1的输出相加，因此JFP模型输出的特征图尺寸与block1的输出相同，而深度为2048。本文在JFP模型中使用的空洞卷积率较小，是考虑图片特征能更好的提取，它的感受域提升并不大，模型要比采用大的空洞卷积率的模型要小，但是却十分有效。

# 1.3暗黑空间金字塔模型(ASPP)

本文在JFP模型后使用ASPP模型[I1,I2]进一步对图像特征进行处理，其模型结构如图3所示。模型输出是由五个相同尺寸和深度的特征图相加得来，将JFP模型的输出作为输入，首先，应用 $1 \times 1$ 的卷积，将JFP的输出深度降为256,生成一个尺寸为 $( \mathrm { h , w } )$ 深度为256的特征图；其次，应用空洞卷积率为6，8和10的空洞卷积，在图像边界进行6、8和10 个像素值为0的填充，不改变图像尺寸，输出三个尺寸为$( \mathrm { h , w } )$ 深度为256的特征图；然后，应用全局池化结合 $1 \times 1$ 卷积，然后使用双线性插值法恢复图像尺寸，输出一个尺寸为$( \mathrm { h , w } )$ 深度为256的特征图；最后，由这5个输出特征图相加得到与JFP的输出特征图尺寸相同、深度为1280的输出。其中，卷积的激活函数为ReLu，加入了批量归一化处理。这部分模型应用的空洞卷积率相较于文献[11,12]减小了，目的是为了减小模型结构，相比于本文JFP模型，采用相对大的空洞卷积率，较大的增加了感受域的大小，ASPP在本文JFP的基础上进一步提取图片的空间尺度信息，能更好地提升特征提取的效果。

![](images/be18f9b74be3f21020b46f4ac9d6a8eb572f15fe8a72d2ca1c3e852fa5c38e3d.jpg)  
图2联合特征金字塔模型(JFP)

![](images/9ede703669ffd6d30cd4a39172e87626916454f8952268fc39e29f606905b86e.jpg)  
Fig.2Joint feature pyramid module(JFP)

# 1.4解码结构

本文设计了一个简单的解码结构，如图4所示，采用 $1 \times 1$ 卷积、 $3 { \times } 3$ 卷积和 $1 \times 1$ 卷积的组合，第一个卷积将输入的深度降为256，第二个卷积作进一步特征处理，第三个卷积将深度降为21，与PascalVOC2012数据集的类别数相同(包括背景)，最后通过双线性插值法将图像尺寸变为 $4 0 0 \times 4 0 0$ ，这个尺寸是数据集裁剪的尺寸，与最开始输入神经网络的图像尺寸保持相同。卷积的激活函数为ReLu，加入批量归一化处理，而其中 $3 { \times } 3$ 卷积加入了0.1的dropout，与 JFP 模型中 dropout的值不同，因为设置不同的dropout可以得到更好结果。

![](images/3c4ddf4ae4c525d56291a530d52aedd2f49f3d8562ed13aa675c5c0737e3a69b.jpg)  
图3暗黑空间金字塔模型(ASPP) Fig.3Atrous spatial pyramid module (ASPP)   
图4解码结构  
Fig.4Decoding structure

# 1.5注意力模型

本文设计了一个注意力模型作为语义分割模型的辅助网络，其结构如图5所示，首先将ResNet101的Block2的输出做一个 $1 \times 1$ 卷积处理，将特征图输出深度降为21，然后进行全局池化处理，其中卷积过程的激活函数为ReLu，加入批量归一化处理，最后通过双线性插值法将输出图像尺寸变为$4 0 0 \times 4 0 0$ 。

![](images/f4c03f5dd5140e4d9f998c8d9c240a69188d0fd278fa82eb3185f687f665867c.jpg)  
图5注意力模型  
Fig.5Attention module

这一部分的网络是作为辅助网络的，将这个网络的损失函数作为语义分割模型损失的一部分，辅助本文设计的神经网络进行训练，如图1中所示，语义分割网络的损失为Loss1，辅助网络的损失为Loss2，Loss1和Loss2均为SoftMaxCrossEntropy损失函数所定义，为式(1)所示。

$$
L o s s = \displaystyle { - \sum _ { i = 1 } ^ { j } y _ { i } ^ { \prime } l o g ( y _ { i } ) }
$$

其中， $i , j \in \{ 1 , 2 , 3 \cdots , 2 1 \}$ ， $y _ { i } ^ { \prime }$ 为标签图像中属于第 $i$ 个类的概率值，即真实分布值， $y _ { i }$ 为语义分割模型输出预测属于第 $i$ 个类的概率值，即预测分布值， $y$ 由 SoftMax 函数定义，如式(2)所示。

$$
y _ { i } = s o f t m a x ( x _ { i } \ ) = { \frac { e x p ( x _ { i } \ ) } { \displaystyle { \sum _ { i = 1 } ^ { j } e x p ( x _ { i } \ ) } } }
$$

最终训练网络的损失函数为 $L o s s _ { _ { \perp } }$ ，其关系式如式(3)所示。

$$
L o s s _ { \oplus } = L o s s _ { I } + O . S \times L o s s 2 = \cdot { \sum _ { i = 1 } ^ { j } } y _ { i } l o g ( \frac { e x p ( x _ { i } ^ { I } ) } { \sum _ { i = 1 } ^ { j } e x p ( x _ { i } ^ { I } ) } ) \cdot O . S \times \sum _ { i = 1 } ^ { j } y _ { i } l o g ( \frac { e x p ( x _ { i } ^ { 2 } ) } { \sum _ { i = 1 } ^ { j } e x p ( x _ { i } ^ { 2 } ) } )
$$

其中，0.5为本文设置辅助网络对整个模型损失函数的影响系数。在语义分割网络模型的卷积层中选择ReLU函数作为激活函数，最后层使用SoftMaxCrossEntropy损失函数进行分类，这样简单而且高效。

# 2 实验结果与分析

作者将本文提出的方法与近3年的方法进行了大量对比实验。本文使用的数据集来源于PascalVOC2012数据集，有两种类型，第一种包括1464张训练图像，1446张验证图像和1456张测试图像；第二种增强数据集，加入了Pascal边界检测数据集进行扩充，包括10582张训练图像，1446张验证图像和1456张测试图像。数据集图像分辨率大小300-500不等，在验证集上进行测试，标签图片包括背景类总共有21个不同类别，使用不同的颜色表示不同类别的物体，其中训练集和验证集的标签图像是公布的，因此本文在训练集上进行网络训练，在验证集上进行指标评价，在测试集上比较语义分割结果。

本文使用Pytorch作为深度学习框架，建立语义分割模型，GPU型号为8GGeForceRTX2070，使用平均交并集之比(mIoU)作为性能评估指标，mIoU值越高表示语义分割效果越好。实验中，ResNet101骨架网络使用的是在ImageNet上进行预训练的参数，将输入图片大小调整为 $4 0 0 \times 4 0 0$ ，然后裁剪为 $3 8 4 \times 3 8 4$ (预处理)，设置迭代周期为180，batchsize为8，学习率为0.001，学习率衰减为0.9，权重衰减为0.0001。在上述两种PascalVOC2012数据集上都进行了实验，首先，在PascalVOC2012数据集(1464张训练图片)上对网络进行训练，然后在增强的PascalVOC2012数据集(10582张训练图片)上对网络进行训练，并都在PascalVOC2012数据集的验证集上进行测试，测试结果如表1所示，本文mIoU值分别为 $78 . 5 5 \%$ 和 $80 . 1 4 \%$ ，其他为文献[11\~13,15\~22]中的方法在验证集中的评价结果，这些方法的骨架网络均在ImageNet上进行预训练，可见本文的方法在使用10582张训练图像的时候，mIoU超过了其中的方法，而使用1464张训练图像的时候，mIoU超过其中一些方法或者与其中一些方法接近。

Tab.1Miou results of Pascal VOC 2012 validation set   

<html><body><table><tr><td>方法</td><td>骨架网络</td><td>mIoU/%</td></tr><tr><td>BlitzNet[15]</td><td>ResNet101</td><td>72.40</td></tr><tr><td>LadderDenseNet[17]</td><td>DenseNet</td><td>78.01</td></tr><tr><td>Context+Decoder+CRFs[22]</td><td>ResNet101</td><td>75.26</td></tr><tr><td>MsNet-4[21]</td><td>ResNet101</td><td>75.80</td></tr><tr><td>DFN[20]</td><td>ResNet101</td><td>79.54</td></tr><tr><td>DeeplabV3[11]</td><td>ResNet101</td><td>78.51</td></tr><tr><td>DeeplabV3+[12]</td><td>ResNet101</td><td>78.85</td></tr><tr><td>PAN[13]</td><td>ResNet101</td><td>79.38</td></tr><tr><td>SDN[16]</td><td>DenseNet</td><td>78.60</td></tr><tr><td>Auto-Deeplab[18]</td><td>ResNet101</td><td>75.26</td></tr><tr><td>DUpsamling[19]</td><td>Xception</td><td>79.67</td></tr><tr><td>本文1(1464 张训练图片)</td><td>ResNet101</td><td>78.55</td></tr><tr><td>本文2(10582 张训练图片)</td><td>ResNet101</td><td>80.14</td></tr></table></body></html>

本文方法的速度对比如表2所示，使用1464张训练图像时，本文方法训练时间比Deeplab $\mathrm { V } 3 +$ 多0.69小时，验证速度比DeeplabV3 $+$ 慢1.79个帧率(fps),测试速度慢1.13fps,使用10582张训练图像时，本文方法训练时间比DeeplabV3+多5.01小时，验证速度比DeeplabV3 $+$ 慢1.56 个帧率(fps)，测试速度慢1.37fps，本文方法实现语义分割的速度下降近1.2fps，即本文方法增加了网络模型的计算量，使得语义分割的速度有一定下降，不过却并不，却显著提升了语义分割的效果，在计算量与效果的综和比较上，体现了本文语义分割方法的优越性。

表1PascalVOC 2012 验证集mIoU结果  
表2本文方法速度对比  
Tab.2Speed comparison of our method   

<html><body><table><tr><td>方法</td><td>mIoU/%</td><td>train/h</td><td>val/fps</td><td>test/fps</td></tr><tr><td>DeeplabV3+(1464)</td><td>77.59</td><td>16.16</td><td>22.36</td><td>17.13</td></tr><tr><td>Ours1(1464)</td><td>78.55</td><td>16.85</td><td>20.57</td><td>16.00</td></tr><tr><td>DeeplabV3+(10582)</td><td>78.89</td><td>117.45</td><td>22.29</td><td>17.20</td></tr><tr><td>Ours1(10582)</td><td>80.14</td><td>122.46</td><td>20.73</td><td>15.83</td></tr></table></body></html>

本文复现了DeeplabV3 $+ ^ { [ 1 2 ] }$ 中的方法，并在每个类别的交并集之比(IoU)上与本文的方法进行比较，结果如表3所示，可见在大部分类别的物体分割上，本文的方法具有明显的提升，而在使用较少训练图片的时候，mIoU值接近DeeplabV3+[12]使用10582张训练图片的结果，而在有些物体上，语义分割效果有下降，可能是遮挡、光照和物体细节上的差异导致。

另外分别使用本文方法和DeeplabV3 $+ ^ { [ 1 2 ] }$ 方法在 PascalVOC2012测试集上生成语义分割结果，如图6所示，其中，a为原图，b为DeeplabV3 $+ [ 1 2 ]$ 使用1464张训练图像的语义分割结果，c为本文方法使用使1464张训练图像的语义分割结果，d为DeeplabV3+[12]使用10582张训练图像的语义分割结果，e为本文方法使用10582张训练图像的语义分割结果。可见，对于物体的大部分区域，与DeeplabV3+[12]方法比较分割效果显著，而小的细节上都存在一定的忽视和错误。而本文的方法最终在物体整体语义分割效果上具有一定提升，错误的语义分割也较少，分割出了其他类别的物体，或将其他物体分割为目标类别。

表3PascalVOC2012验证集21类IoU结果  
Tab.321 classes iou results of Pascal VOC 2012 validation se   

<html><body><table><tr><td rowspan="2">类别</td><td colspan="2">1464 training images</td><td colspan="2">0582 training images</td></tr><tr><td>DeeplabV3+</td><td>本文1</td><td>DeeplabV3+</td><td>本文2</td></tr><tr><td>background</td><td>92.38</td><td>93.88</td><td>93.90</td><td>94.26</td></tr><tr><td>aeroplane</td><td>86.26</td><td>89.76</td><td>90.29</td><td>93.51</td></tr><tr><td>bike</td><td>62.27</td><td>62.07</td><td>47.55</td><td>46.15</td></tr><tr><td>bird</td><td>87.14</td><td>88.14</td><td>89.17</td><td>90.68</td></tr><tr><td>boat</td><td>74.27</td><td>75.67</td><td>73.72</td><td>75.71</td></tr><tr><td>bottle</td><td>79.38</td><td>79.18</td><td>79.67</td><td>86.23</td></tr><tr><td>bus</td><td>91.49</td><td>91.37</td><td>93.99</td><td>93.78</td></tr><tr><td>car</td><td>88.31</td><td>88.91</td><td>89.59</td><td>90.02</td></tr><tr><td>cat</td><td>87.11</td><td>89.61</td><td>94.54</td><td>94.94</td></tr><tr><td>chair</td><td>35.15</td><td>36.65</td><td>45.86</td><td>44.60</td></tr><tr><td>cow</td><td>86.04</td><td>89.54</td><td>89.78</td><td>90.18</td></tr><tr><td>table</td><td>60.36</td><td>61.17</td><td>50.42</td><td>53.70</td></tr><tr><td>dog</td><td>86.93</td><td>87.23</td><td>90.21</td><td>91.55</td></tr><tr><td>horse</td><td>86.73</td><td>87.73</td><td>89.04</td><td>89.56</td></tr><tr><td>motorbike</td><td>85.96</td><td>85.26</td><td>88.36</td><td>88.80</td></tr><tr><td>person</td><td>85.27</td><td>86.27</td><td>89.04</td><td>89.00</td></tr><tr><td>plant</td><td>61.23</td><td>61.43</td><td>59.04</td><td>63.89</td></tr><tr><td>sheep</td><td>86.21</td><td>87.21</td><td>87.34</td><td>89.51</td></tr><tr><td>sofa</td><td>47.19</td><td>47.70</td><td>52.38</td><td>49.69</td></tr><tr><td>train</td><td>84.18</td><td>84.38</td><td>87.47</td><td>87.99</td></tr><tr><td>television</td><td>75.47</td><td>76.37</td><td>75.36</td><td>79.29</td></tr><tr><td>mIoU(%)</td><td>77.59</td><td>78.55</td><td>78.89</td><td>80.14</td></tr></table></body></html>

Cntn0 [ 上   
a.原图 b.Deeplab1 c.ours1 d.Deeplab2 e.ours2

# 3 结束语

本文提出一种基于卷积神经网络的语义分割方法，通过本文提出的联合特征金字塔模型(JFP)融合残差网络的三层输出，更加完整地提取图像特征，结合ASPP模型进一步提取图像特征，设计了一个简单的解码结构恢复图像尺寸，在此之外又设计了一个注意力模型作为辅助网络，辅助语义分割网络进行训练，本文的方法解决了特征提取信息丢失和网络训练收敛慢的问题。最后在PascalVOC2012数据集上的对比结果表示，本文提出的方法在mIoU上相比Context+Decoder+CRFs[22]、MsNet- $4 ^ { [ 2 1 ] }$ 和 Auto-Deeplab[18]三种方法提高了将近 $5 \%$ ，相比LadderDenseNet[17]、DeeplabV3[11]、DeeplabV3 $+ ^ { [ 1 2 ] }$ 和 SDN[16]四种方法，本文使用增强数据集时，mIoU有 $1 \% \sim 2 \%$ 的提升，同时也超过DFN[20]、PAN[13]和DUpsamling[19]这三种方法近 $0 . 5 \%$ 。未来对于图像语义分割的工作是寻求更优的方法，设计一个更加优化的模型，提取图像的细节特征，进一步提高语义分割的效果。

# 参考文献：

[1] Gao Hongyang，YuanHao，Wang Zhengyang，et al.Pixel DeconvolutionalNetworks[EB/OL].[2017-11-27]. https://arxiv. org/abs/1705.06820.   
[2] 蒋应锋，张桦，薛彦兵，等．一种新的多尺度深度学习图像语义理解 方法研究[J].光电子·激光,2016,27(02):224-230.(Jiang Yingfeng, Zhang Hua, Xue Yanbing,et al. Research on a new method of multi-scale deep learning image semantic understanding [J]. Optoelectronics laser, 2016,27 (02): 224-230.)   
[3]Long J， Shelhamer E,Darell T.Fully Convolutional Networks for Semantic Segmentation [C/ Proc of the Conference on Computer Vision and Pattern Recognition: IEEE Press,2015:3431-3440.   
[4] 董晓亚，赵晓丽，张嘉祺．一种改进的噪声图像语义分割方法[J]. 光电子·激光,2017,28(12):1372-1377.(Dong Xiaoya, Zhao Xiaoli, Zhang Jiaqi. An improved semantic segmentation method of noise image [J]. Optoelectronics laser,2017,28 (12): 137-1377.)   
[5] Li Jingwei, Yang Hua, Chen Lin,et al. Image semantic segmentation optimization by Conditional Random Field integrated with object clique potential [C]// Proc of the International Symposium on Broadband Multimedia Systems and Broadcasting: IEEE Press,2017.1-6.   
[6] Badrinarayanan V, Kendall A, Cipolla R,et al. SegNet: A Deep Convolutional Encoder-Decoder Architecture for Image Segmentation [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2017,39 (12): 2481-2495.   
[7]Chaurasia A, Culurcielo E.LinkNet: Exploiting encoder representations forefficient semantic segmentation [C]// Proc of the Visual Communications and Image Processing: IEEE Press, 2017.1-4.   
[8] 李琳辉，钱波，连静，等．基于卷积神经网络的交通场景语义分割方 法研究[J].通信学报,2018,39(04):123-130.(Li Linhui, Qian Bo, Lian Jing,et al.Research on trafic scene semantic segmentation based on convolutional neural network [J]. Journal of communications, 2018, 39 (04): 123-130.)   
[9]Lin Guosheng,Shen Chunhua,Hengel AV D,et al. Exploring Context with Deep Structured Models for Semantic Segmentation [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2018,40 (6): 1352-1366.   
[10] Yu F,Koltun V. Multi-Scale Context Aggregation by Dilated Convolutions [J]. arXiv: 151107122,2015.   
[11] Chen L-C,Papandreou G,Murphy K,et al. DeepLab: Semantic Image Segmentation with Deep Convolutional Nets,Atrous Convolution,and Fully Connected CRFs [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2018,40 (4): 834-848.   
[12] Chen L-C,Zhu Y,Papandreou G,et al. Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation [Cl/ Proc of the European Conference on Computer Vision: ECCV Press,2018.801-818.   
[13]Li Hanchao,Xiong Pengfei,An Jie,et al.Pyramid Attention Network for Semantic Segmentation [EB/OL]. [2018-5-25]. https:/arxiv.org/abs/ 1805.10180.   
[14] Yu F,Wang Dequan,Shelhamer E,et al.Deep Layer Aggregation [C]// Proc of the Conference on Computer Vision and Patern Recognition: IEEE Press,2018.2403-2412.   
[15] Dvornik N,ShmelkovK, MairalJ,etal.BlitzNet: AReal-Tme Deep Network for Scene Understanding [C]// Proc of the International Conference on Computer Vision: IEEE Press,2017.4174-4182.   
[16] Fu Jun,Liu Jing,Wang Yuhang,etal. Stacked Deconvolutional Network forSemanticSegmentation [EB/OL].[2017-8-16]. https://arxiv. org/abs/1708.04943.   
[17] Krapac J， Segvic I K S. Ladder-Style DenseNets for Semantic Segmentation of Large Natural Images [C]//Proc of the International Conference on Computer Vision Workshops:IEEE Press,2017.238-245.   
[18]Liu Chenxi,Chen L-C,SchroffF,et al.Auto-DeepLab:Hierarchical Neural Architecture Search for Semantic Image Segmentation [C]// Proc of the Conference on Computer Vision and Pattern Recognition:IEEE Press,2019.82-92.   
[19] Tian Zhi,He Tong,Shen Chunhua,et al.Decoders Matter for Semantic Segmentation:Data-Dependent Decoding Enables Flexible Feature Aggregation [EB/OL].[2019-03-05].https://arxiv.org/abs/1903.02120.   
[20] Yu Changqian,Wang Jingbo,Peng Chao,et al.Learning a Discriminative Feature Network for Semantic Segmentation [C]// Proc of the Conference on Computer Vision and Pattern Recognition:IEEE Press, 2018.1857-1866.   
[21]陈智．基于卷积神经网络的语义分割研究[D].北京交通大学，2018. (Chen Zhi.Research on semantic segmentation based on convolutional neural network [D]. Beijing Jiaotong University,2018.)   
[22]孙海川．基于全卷积网络的图像语义分割算法研究[D].哈尔滨工 业大学,2018.(Sun Haichuan.Research on image semantic segmentation algorithm based on full convolution network [D].Harbin University of technology,2018.)