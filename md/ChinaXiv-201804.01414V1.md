# 一种改进的深度残差网络行人检测方法\*

郝旭政，柴争义

(天津工业大学 计算机科学与软件学院，天津 300387)

摘要：为了提高行人检测方法的准确率，针对行人图像特征，提出一种基于深度残差网络和YOLO(You Only LookOnce)方法的行人检测方法。以加强行人特征表达为目的，通过分析行人在图像中的表达和分布特征，提出一种不影响实时性的矩形输入深度残差网络分类模型以改进YOLO检测方法，使模型能够更好的表征行人；为了进一步提高模型的准确率和泛化能力，采用了混合行人数据集训练的方式，提取VOC数据集的行人数据与INRIA数据集组成混合数据集进行训练，明显降低了漏检率；并且利用聚类分析预测框的方法重新设计了初始预测框，提高行人定位能力并加快收敛。经公开的INRIA数据集的测试实验证明，本方法较主流的行人检测方法每张图片误检率有明显改善，降低至$1 3 . 8 6 \%$ ，有 $1 . 5 1 \%$ 至 $5 8 . 6 2 \%$ 不同程度的提升，并且本方法拥有良好的实时性和泛化能力，实用性强。

关键词：行人识别；深度残差网络；YOLOv2；卷积神经网络；深度学习 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.12.0836

# Improved pedestrian detection method based on depth residual network

Hao Xuzheng, Chai Zhengyi (School ofComputer Science &Software Engineering,Tianjin Polytechnic University,Tianjin 300387,China)

Abstract:To improve theaccuracyof the pedestrian detection method,a rectangular input ofconvolution neural network enhance the new pedestrian detection method based on the depth residual network and YOLOobject detection method.The rectangular input helpedthe model gain the pedestrian characteristics expresion byanalyzingthe expressionand distribution characteristics ofpedestriansinthe images.Thedepthresidualnetwork with pre-activationforYOLOobjectdetectionimproved thefeatureextractionabilitythrough more layersofconvolution neural networks.Hybrid dataset trainingand clusteranchor boxes could also improve thepedestriandetectionperformance.ThetestresultsofINRIAdatasethave provedthatthe method has beterdetectionperformane than thepopularpedestriandetectionmethods,the indexofFalsePositive perImagecanreduce to $1 3 . 8 6 \%$ ,improving ranging from $1 . 5 1 \%$ to $5 8 . 6 2 \%$ in varying degrees.

Key Words: pedestrian detection; deep residual network; YOLOv2; convolutional neural network; deep learning

# 0 引言

行人检测是计算机视觉领域的重要研究课题之一。行人检测通常通过图像处理、计算机视觉相关算法以及机器学习等技术对行人进行检测和识别[1]。行人检测和识别技术在无人驾驶汽车、智能视觉监控、服务型智能机器人等领域中均有重要应用。

根据分类方法，行人检测通常被分为形变部件模型变体、基于决策森林的行人检测方法和基于深度神经网络的行人检测方法三种[2]。近年来，行人检测在这三个研究方向均有不同程度的发展，在公开的行人数据集上可以取得相似的性能表现。但类似方向梯度直方图(HOG)[3]、局部二值模式(LPB)[4等手工特征的传统行人检测方法存在特征维度高、手工设计特征、泛化能力差等缺点，在实际应用中效果较差[5]。基于深度神经网络的行人检测方法能够自动学习行人特征，具有较好的泛化能力，随着卷积神经网络在目标检测领域的成功应用，引起了研究者的广泛关注，成为计算机视觉领域的研究热点之一[6]。

基于卷积神经网络的目标检测方法主要有区域提名和端到端两个方向。基于区域提名方向的研究主要是R-CNN(region-basedconvolutionalneuralnetworks，基于区域的卷积神经网络)[7\~9]、SPP-net (spatial pyramid pooling networks，金字塔池化层网络)[10]和 R-FCN(Region-based Fully Convolutional Network,基于区域的全卷积网络)[1]。FasterR-CNN[9]使用了区域提名网络(region proposal networks，RPN)，提出预测框(anchor box)机制。端到端方向的研究主要有 YOLO[12,13]和 SSD(single shotmulti-box detector)[14]。YOLOv2[13]方法去掉YOLO全链接层引入FasterR-CNN提出的区域提名网络，加入聚类分析，多尺度训练、多层次特征融合层等改进，并在此基础上加入词汇向量树和联合训练算法，提出可以检测超过9000种物体YOLO9000[13]方法。

本文基于端到端目标检测的研究成果，针对行人特征提出了一种融合深度残差网络[15,16]和YOLO方法的行人检测和识别方法。本方法通过分析行人在图像中的表达和分布特征，提出一种9:19矩形输入的卷积神经网络分类模型，加强了行人特征表达；为了提高模型的特征提取能力，本文提出了基于50层的预激活深度残差网络的YOLO行人检测方法，使模型能够更好的表征行人；为了提高模型的准确率和泛化能力，本文提出了混合行人数据集训练方式，手工提取了VOC数据集的行人数据与INRIA数据集组成混合数据集进行训练，明显降低网络漏检率；最后，本文针对提出的网络模型和增强的数据集通过聚类分析方法设计了初选预测框，提高行人定位能力，加快收敛。实验证明，本算法拥有良好的实时性和泛化能力，在公开的行人数据集下，本方法较主流的行人检测方法每张图片误检率有明显提升，并且本方法拥有良好的实时性和泛化能力。

# 1 相关知识

# 1.1YOLOv2目标检测方法

YOLOv2目标检测方法是目前最先进的目标检测方法之一，在检测速度和检测精度均有出色表现。YOLOv2方法使用的是基于GoogLeNet的定制网络，结构如图1。其分类网络是Darknet-19[13]网络模型，拥有19 个卷积层和4 个池化层，把$1 \times 1$ 的卷积核置于 $3 { \times } 3$ 的卷积核之间来压缩特征，每次池化后将特征图维度加倍。分类网络还采用了批规范化、预训练和多尺度训练等方法提高网络分类准确率。

YOLOv2的检测网络借鉴了FasterR-CNN，使用了带有Anchor预测框的卷积层，并优化了先验预测框的选取；YOLOv2还设计了多层次特征融合层，把 $2 6 { \times } 2 6 { \times } 5 1 2$ 的浅层特征图拆分并组成 $1 3 \times 1 3 \times 2 0 4 8$ 的特征图，并连接到深层组成 $1 3 \times 1 3 \times 3 0 7 2$ 特征图，从而使YOLOv2能够获得更好的细粒度特征。

![](images/57df9e2482163c50ed486fc3aafada0a1bc7b311eb546134f034ec73d3e01026.jpg)  
图120分类的YOLOv2 结构图

# 1.2 深度残差网络

深度残差网络（DeepResidualNetwork,Resnet）是何恺明等人在文献[15]中提出的极深卷积神经网络模型，可以避免简单堆叠的卷积神经网络梯度消失或爆炸以及精度退化问题，模型更容易优化，性能提升明显[15]。

![](images/eb41b26ca09c9de8105ef5e77598f96a867055ce5f19934b2ca1979e73f0f522.jpg)  
图2深度残差网络基本结构

假设 $H ( X ) = X$ 来表示最优解映射，一般的卷积神经网络是直接拟合 $H ( X ) = X$ ，而深度残差网络期望网络拟合残差映射，即

$$
F ( X ) = H ( X ) - X
$$

此时原最优解映射被表示为

$$
H ( X ) = F ( X ) + X
$$

深度残差网络自动提取特征时，只要 $F ( X ) = 0$ ，即完成了一个恒等映射 $H ( X ) = X$ ，显然，使网络去拟合确定的函数$F ( X ) = 0$ 比逼近某个函数 $H ( X )$ 容易。

在深度残差网络中， $F ( X ) + X$ 通过快捷连接来实现，结构如图2(a)所示。快捷连接跳过2或3个卷积层，自身映射到叠加层相加作为输出。文献[16]进一步提出了预激活机制的深度残差网络Resnetv2，在卷积操作前进行批规范化和激活操作，如图2(b)所示，采用预激活方式使深度残差网络加强对模型的正则化，并加快网络收敛。

# 2 针对图像特征的行人检测方法

# 2.1基于图像的行人特征分析

人类通过双眼观察事物，视像设备记录人类眼中的事物，这些事物都是“真实”的，这是针对行人图像特征的行人检测方法设计的灵感来源。计算机视觉是机器模拟生物视觉的方法，如果给机器更贴近原生的输入，则更有利于机器“理解”世界。

通过对行人图像进行分析，如图3所示，可归纳以下特点：

a）行人个体的横向(X)特征表达比纵向(Y)特征表达少，如图3(d)所示。行人身高和身宽比约为3:1，横向特征表达较少，增加横向特征表达有助于行人识别。b)行人群体在没有标注的图像上无法体现深度信息，因此如图3(a)人群可以看做行人特征的横向堆叠，增加图像宽度，有利于行人群体特表达。

![](images/cec07cc3fb5c39a6c65a3c9056b13121649187bef3c9280d1b95e3e814d8f664.jpg)  
图3卷积神经网络的图像预处理比例

另外，视像设备多采用16:9长宽比例采集数据，视像数据多为图3(a)(d)形式，特别是图3(a)画幅是视频采集常用画幅。而目标检测方法通常输入处理后的正方形图像，这种处理加大了行人横向和纵向特征差异，从图3(b)(c)(e)(f)可知横幅图像的失真比竖幅图像的失真程度更高。Overett 等人在Haar[17]特征行人识别研究中也有类似工作，认为对于Haar特征方法增加样本宽度的性能好于增加样本高度的性能。综上，本文采用了改变卷积神经网络输入的长宽比例，利用矩形输入网络提取更丰富的横向特征，经实验验证，本文选择了 $2 8 8 \times 6 0 8$ 分辨率图像作为输入，这个分辨率的图像与 $4 1 6 \times 4 1 6$ 图像有相近像素数，不影响实时性。

# 2.2基于维度聚类的预测框选取

在基于区域提名网络的目标检测方法中，先验预测框的设置往往是手工设计而成，虽然网络在迭代过程中也能拟合随机性较大，使网络拟合缓慢，而且更容易使模型收敛到局部最优，文献[13]针对这个问题提出了维度聚类的方法选取先验预测框。本文采用了K-means聚类方法对数据集进行分析，确定先验框个数和大小。

在实现K-means聚类时，没有采用闵可夫斯基距离变式作为评价指标，而是通过交并比衡量，这样可以避免框的尺寸对K-means损失的影响。并且计算交并比时没有采用直接的框的的长宽计算，而是通过单位网格将其标准化。最终，相异度计算公式为

$$
d ( b o x , c e n t r d ) = 1 - I o U ( b o x , c e n t r d )
$$

其中：centrd 表示簇中心，box 表示样本。 $I o U ( b o x , c e n t r d )$ 表示簇中心框和聚类框的交并比。交并比 $I o U$ 表示预测框的准确程度，公式表示为

$$
I o U ( b b _ { _ { g t } } , b b _ { _ { d t } } ) = \frac { b b _ { _ { g t } } \cap b b _ { _ { d t } } } { b b _ { _ { g t } } \cup b b _ { _ { d t } } }
$$

其中： $b b _ { _ { g t } }$ 表示真实框， $b b _ { _ { d t } }$ 表示预测框。

本文通过实验对比了 $\scriptstyle 1 = [ 2 \sim 9 ]$ 八组预测框对模型定位能力的影响，见图4，均衡网络性能和检测实时性，最终选择预测框个数为5个。

![](images/8bace742cf9e115104a06afad5efb2a36f7686297d0e7d64f8daf3d9fc7a1847.jpg)  
图4预测框个数与交并比关系

# 2.3 Res-P-YOLO 网络设计

本文基于YOLOv2目标检测模型，把Resnetv2-50分类网络与YOLOv2的检测方法结合。首先去掉50层预激活深度残差网络最后的一个平均池化层和一个全链接层，此时最后的卷积层输出维度为2048，为了避免高维度带来的计算量，在此后串联一个 $1 \times 1 \times 1 0 2 4$ 卷积层,用来降低维度以减少运算量；其次有针对性的将深度残差网络的输入设计为 $2 8 8 \times 6 0 8$ ，保留图像更多横向特征；然后接入YOLOv2的检测网络，并将分类网络中 $1 8 \times 3 8 \times 5 1 2$ 特征图作为细粒度特征与检测网络的特征图重组，提高网络小物体识别能力；最后根据识别目标数目和预测框设置调整模型，完成Res-P-YOLO行人识别方法的设计，结构图如图5所示。

![](images/2a8cfa1e5931feec7c47d6c36c9e7f6c2a367c575499c527b952c91eb5106a08.jpg)  
图5Res-P-YOLO网络

在训练过程中，Res-P-YOLO 端到端回归行人位置坐标的同时，也进行了预测框中行人的置信度Conf(Person)计算，置信度包含了预测框的准确程度和框内存在行人的可能性Pr(Person)为

$$
C o n f ( P e r s o n ) = \mathrm { P r } ( P e r s o n ) \times I o U _ { d t } ^ { g t }
$$

因此，在训练过程中Res-P-YOLO在计算损失时需要衡量行人位置、预测框准确度和行人可能性三方面，故模型的损失函数表示为

$$
\begin{array} { l l } { { l o s s ( p e r s o n ) = \lambda _ { \mathrm { c o e n t } } \displaystyle \sum _ { i = 0 } ^ { \mu \nu + l } \sum _ { j = 0 } ^ { \mu } \sum _ { i } ^ { \nu } \Delta _ { j i } ^ { \mu \nu \prime \prime } ( ( x _ { i } - \widehat { x } _ { i } ) ^ { 2 } } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { { } } \\ { } \\ { { } } \\ { } \\ { { } } \\ { } \\ { { } } \\ { } \\ { } { } \\ { } \\ { }  \\ { { } \\ { } } \\ { } \\ { } \\ { { } } \\ { } \\ { } \\ { }  \\ { { } } \\ { } \\ { } \\ { } \\ { } { } \\ \end{array}
$$

其中： $W , H$ 表示网络最终特征图网格尺寸， $B$ 表示每个网格的预测框个数， $\mathbf { \Phi } _ { x , y , w , h }$ 表示框的中心和宽高； $C _ { _ i }$ 表示预测框定位到行人的置信度， $\hat { C } _ { i }$ 表示框内真实存在行人的置信度， ${ \boldsymbol { p } } _ { i }$ 表示预测行人置信度， $\widehat { \boldsymbol { p } } _ { i }$ 真实存在行人置信度。 $\lambda _ { _ { c o o r d } } , \lambda _ { _ { n o p e r s } }$ 分别表示位置预测和行人预测正则化惩罚系数， $\Delta _ { i j } ^ { p e r s }$ 表示第i个网格的第」个预测框存在行人的可能性， $\Delta _ { i } ^ { p e r s }$ 表示判定第i个网格存在行人的概率。

# 3 方法验证与实验对比

# 3.1实验环境

本文的实验环境如下，CPU：IntelCore i7-6800K；内存：16GDDR4；GPU：NvidiaGeforceGTX1070；操作系统：64位Ubuntul6.04LTS；实验框架为Darknet开源框架。数据集选用了INRIA行人数据集和提取自PASCALVOC数据集的行人数据。在该实验环境下，Res-P-YOLO在1080p 的 $\mathrm { m p 4 }$ 视频上的检测速度可达31.2帧/秒。

# 3.2行人检测模型评价方法

本文使用每张图片误检率(false positive per image，FPPI)和漏检率(MissRate，MR)指标评价行人检测方法，使用ROC曲线直观表示。该指标通过整张图像评估反映整个行人检测系统的性能，FPPI-MR指标越低表明行人检测方法性能越好。漏检率和每张图片误检率计算方法分别如下

$$
M R = { \frac { F N } { F N + T P } }
$$

$$
F P P I = \frac { F P } { N _ { t e s t \_ d a t a } }
$$

其中： $F N$ 表示实际为行人，被判定非行人的个数； $T P$ 表示实际为行人，被判定行人的个数； $F P$ 表示实际非行人，被判定行人的个数； $N _ { _ { t e s t \_ d a t a } }$ 表示测试集图片张数。

# 3.3混合数据集训练效果验证

INRIA行人数据集是目前被应用最多的公开数据集，训练集标注准确，场景丰富，分为测试集和训练集两部分。训练集包含行人样本2416个，分布在614张图片上；测试集包含行人样本1126个，分布在288 张图片上。PASCALVOC 数据集是知名的20分类的公开多目标数据集，本文根据标注信息，从混合的数据集中手工提取出8102张行人图片以及对应标注信息。

深度学习方法需要大量数据训练，少量数据容易造成过拟合，虽然在该数据集上有较好表现，但实际应用时泛化能力较差。针对这个问题，本文提取了PASCALVOC数据集的全部行人数据用来辅助训练，提高本方法的泛化能力。本文使用INRIA和VOC混合训练模型与仅使用INRIA训练模型进行实验对比，如图6所示，实验表明使用混合训练的方法能使行人检测的每张图片漏检率降低 $5 \%$ 。因此，本文综合了INRIA行人数据集和PASCALVOC数据集行人图片部分，共有样本图片8716张，本文选取PASCALVOC训练集全部行人图片和INRIA训练集作为实验的训练集；选取PASCALVOC测试集全部行人图片作为实验的验证集；采用INRIA测试集作为实验的测试集。

![](images/1362647c41e9fe7bad447b4c8d59eff5c692295499ca751f1970e1d42d8b24a3.jpg)  
图6混合数据集训练和单一数据集训练模型性能对比

# 3.4矩形输入性能对比

在设计矩形输入时有两种思路：一是在原始输入 $4 1 6 \times 4 1 6$ 基础上进行横向扩展，但会导致分辨率骤增，无法验证矩形输入对网络的影响，并会影响实时性；二是自行设计新的矩形尺寸使像素数尽量与 $4 1 6 \times 4 1 6$ 相近，在保证实时性的同时可以验证矩形输入对网络的影响。

本文验证采用方法二，矩形输入的设计见表1。

表1网络矩形输入设计  

<html><body><table><tr><td>分辨率</td><td>长宽比</td><td>像素数</td></tr><tr><td>416×416</td><td>13:13</td><td>173056</td></tr><tr><td>352×480</td><td>11:15</td><td>168960</td></tr><tr><td>352 × 544</td><td>11:17</td><td>191488</td></tr><tr><td>288 ×544</td><td>9:17</td><td>156672</td></tr><tr><td>288×608</td><td>9:19</td><td>175104</td></tr></table></body></html>

显然 $2 8 8 \times 6 0 8$ 像素数与 $4 1 6 \times 4 1 6$ 最为相近，故采用288$\times 6 0 8$ 和 $4 1 6 \times 4 1 6$ 两种输入尺寸进行实验比对。为了加快验证速度，采用了yolov2精简方法 tiny-yolo[18]在上述训练集上进行行人检测定量分析实验，实验均采用默认设置，仅修改输入分辨率设置，从图7可以看出，采用 $2 8 8 \times 6 0 8$ 输入的行人检测方法有明显提升，召回率提高 $6 . 3 7 \%$ ，平均交并比提升 $2 . 2 2 \%$ 。

![](images/6697a5bda3d7270abecc9f7b20b3c9e90820db5ebb1391c7178bcf020464ee3b.jpg)  
图7不同输入尺寸对网络性能的影响

# 3.5 实验结果与对比

Res-P-YOLO 网络的构建和实现基于开源的深度学习框架Darknet[18]。训练时学习率采用均匀分布策略(polynomialdecay),初始学习率为0.001，在40000和60000次迭代后分别在乘以0.1,动量系数为0.9，权值衰减系数为0.0005，并采用了随机调整曝光、饱和度、色调数据增强的方法。实验以64张图片/批进行迭代，迭代80000次，如图8所示，经验证集确认第73800次迭代结果作为最终权重模型。

![](images/b0604bd87190c8da8bdbf6001fbcdd13040b91f9c5ea4f5198acc1cfe54727ff.jpg)  
图8网络迭代损失值变化图

为了综合评价本文算法有效性，本节对综合上述工作，在INRIA行人测试集上对本文方法与主流的LatSVM[19]、ACF[20]、RandForest[21]、ConvNet[22]等行人检测方法以及YOLOv2方法的检测性能指标进行评估，得出FPPI-MR关系的ROC曲线，ROC曲线下的面积越小，说明行人检测方法检测性能越好。实验结果如图9和表2所示。

![](images/973ed1652ce1c8d12deb3eab61f5dc6e29fc804bbff6f9b2cfe74319c458eb1b.jpg)  
图9本算法和主流行人算法的ROC 曲线图

从图9本方法和YOLOv2的ROC曲线可以看出，本方法与YOLOv2相比，当 $\mathrm { { F P P I } < 1 0 ^ { - 1 } }$ 时本方法明显优于YOLOv2方法。从曲线总体来看，本方法的FPPI指标较YOLOv2低约 $1 \%$ 因为YOLOv2采用了ImageNet预训练模型训练，而本方法自行设计的网络没有相应预训练模型，ImageNet预训练模型对调参影响巨大，因此 $1 \%$ 的差距在理论上是合理的。

从表2可以看出，本方法在INRIA数据集上取得了较好的性能表现，每张图片误检率仅 $1 3 . 8 6 \%$ ，不同程度上优于图表中其他传统算法，特别是在 $\mathrm { { F P P I } < 1 0 ^ { - 1 } }$ 时，本算法的行人检测性能明显优于其他算法。其原因在于大多数手工设计特征的行人检测方法对行人的表征能力较差，而本算法针对图片行人特征设计了有助于图像中行人特征表达的网络输入和能够更好提取行人图像特征的深度残差网络，并通过混合数据集、聚类初选预测框方法加强训练，使本方法能够自主学习到更有效的行人特征，进而进一步降低每张图片误检率。

表2主流行人算法检测率对比  

<html><body><table><tr><td>行人检测方法</td><td>FPPI(%)</td></tr><tr><td>VJ</td><td>72.4810</td></tr><tr><td>HOG</td><td>45.9788</td></tr><tr><td>HikSvm</td><td>42.8188</td></tr><tr><td>HogLbp</td><td>39.0968</td></tr><tr><td>LatSvm-V2</td><td>19.9641</td></tr><tr><td>VeryFast</td><td>15.9591</td></tr><tr><td>ConvNet</td><td>19.8934</td></tr><tr><td>ACF</td><td>17.2809</td></tr><tr><td>RandForest</td><td>15.3714</td></tr><tr><td>WordChannels</td><td>15.9511</td></tr><tr><td>本方法</td><td>13.8589</td></tr></table></body></html>

# 4 结束语

本文针对行人自身形状特征和在图像中的分布特征提出了一种基于深度残差网络的行人检测方法。针对行人形状和分布特点，提出了一种矩形输入的卷积神经网络分类模型，加强了行人特征表达；为了提高模型特征提取能力，提出了一种基于预激活深度残差网络的行人检测方法。在方法设计时，为了提高模型准确率和泛化能力，提出了混合行人数据集训练的方式降低每张图片误检率，并且通过聚类分析预测框的方法重新为模型设计了初始预测框，提高行人定位能力并加快收敛。实验结果表明，本算法拥有良好的实时性和泛化能力的同时，在公开的行人数据集下本方法较主流行人检测方法的准确率有显著提升。本文仅是对基于卷积神经网络的行人检测方法的初步探索，如何在保证实时性的进一步提高准确率和泛化能力是下一步探索的方向。

# 参考文献：

[1]苏松志，李绍滋，陈淑媛，等．行人检测技术综述[J]．电子学报,2012, 40 (4): 814-820.   
[2]Benenson R,Omran M,Hosang J,et al. Ten years of pedestrian detection, what have we learned?[C]// Proc of European Conference on Computer Vision. Springer,2014: 613-627.   
[3]Dalal N,Triggs B.Histograms of oriented gradients for human detection [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition. 2005: 886-893.   
[4]Ojala T,Pietikainen M, Maenpaa T.Multiresolution gray-scale and rotation invariant texture classification with local binary patterns [J],IEEE Trans on Patterm Analysis and Machine Intelligence,2002,24(7): 971-987.   
[5]张慧，王坤峰，王飞跃．深度学习在目标视觉检测中的应用进展与展望 [J]．自动化学报,2017,43(8):1289-1305.   
[6]周飞燕，金林鹏，董军．卷积神经网络研究综述[J].计算机学报,2017, 40 (6): 1229-1251.   
[7]Girshick R,Donahue J,Darrell T,et al. Region-Based Convolutional Networks for Accurate Object Detection and Segmentation [J].IEEE Transs on Pattern Analysis & Machine Intelligence,2016,38 (1): 142.   
[8]Girshick R.Fast R-CNN[C]// Proc of IEEE International Conference on Computer Vision.2015: 1440-1448.   
[9]Ren SQ,He KM,Girshick R,et al.FasterR-CNN: towards real-time object detection with region proposal networks [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2017,39 (6): 1137-1149.   
[10] He K, Zhang X,Ren S,et al. Spatial pyramid pooling in deep convolutional networks for visual recognition.[J].IEEE Trans on Pattern Analysis & Machine Intelligence,2015,37(9): 1904-16.   
[11] Dai J,LiY,He K,etal.R-FCN: object detection via region-based fully convolutional networks [C]//Neural Information Processing Systems.2016: 379-387.   
[12] Redmon J,Divvala S,Girshick R,et al. You only look once: unified,realtime object detection [C]//Computer Vision and Pattern Recognition.2016: 779-788.   
[13] Redmon J,Farhadi A.YOLO90o0: better,faster, stronger[J].arXiv preprint arXiv: 1612.08242,2016.   
[14] Liu W,Anguelov D,Erhan D,et al. SSD: single shot multibox detector [C]// Proc of European Conference on Computer Vision. Springer, 2016:21-37.   
[15] He K, Zhang X,Ren S,et al. Deep residual learning for image recognition [C]//Computer Vision and Pattrn Recognition. 2016:770-778.   
[16] He K, Zhang X,Ren S,et al. Identity mappings in deep residual networks [C]/ Proc of European Conference on Computer Vision. Springer International Publishing,2016: 630-645.   
[17] Overett G,Petersson L,Brewer N,et al.A new pedestrian dataset for supervised learning [C]//Proc of Intelligent Vehicles Symposium.2011: 373-378.   
[18] Redmon J. Darknet: Open Source Neural Networks in C [DB/OL].[2017- 10-25]. http://pjreddie.com/darknet/.   
[19]Felzenszwalb P,McAllester D,Ramanan D.A Discriminatively Trained, Multiscale,Deformable Part Model [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2008:1-8.   
[20] Dollar P,Appel R,Belongie S,et al.Fast Feature Pyramids for Object Detection[J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2014, 36 (8): 1532.   
[21] Marin J,Vazquez D,Lopez AM,et al. Random Forests of Local Experts for Pedestrian Detection [C]// Proc of IEEE International Conference on Computer Vision.2014: 2592-2599.   
[22] Sermanet P,Kavukcuoglu K, Chintala S,et al.Pedestrian detection with unsupervised multi-stage feature learning [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2013:3626-3633.