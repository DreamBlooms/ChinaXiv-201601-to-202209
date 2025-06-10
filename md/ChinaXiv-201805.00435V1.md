# 一种面向表情识别的ROI区域二级投票机制

文元美，欧阳文，凌永权(广东工业大学 信息工程学院，广州 510006)

摘要：针对如何更有效地使用卷积神经网络从训练图像中学习到的分布式特征进行研究，提出了一种面向人脸表情识别的ROI区域二级投票机制。首先将图像划分成一系列感兴趣区域（ROI）图像输入到卷积神经网络中进行训练；然后将测试图像的ROI图像输入到卷积神经网络中，统计所有ROI图像的判别结果；最后采用二级投票机制确定测试图像的最终类别，得到最终判别结果。此外，针对卷积神经网络不能从人脸图像中学习到旋转等空间位置信息，引入了STN(spatial transformer network)网络，提高算法在解决复杂情况下的表情识别问题的能力。实验表明，ROI 区域二级投票机制能够更有效地使用卷积神经网络从训练图像中学习到的分布式特征，比直接使用ROI图像进行投票的方法准确率提升了 $1 . 1 \%$ ，引入 STN 网络能够有效提升卷积神经网络的鲁棒性，比未引入 STN 网络的方法准确率提升了$1 . 5 \%$ 。

关键词：卷积神经网络；表情识别；STN网络；二级投票机制中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.03.0189

# Expression-oriented ROI region secondary voting mechanism

Wen Yuanmei, Ouyang Wen, Ling Yongquan (School of Information Engineering Guangdong University ofTechnology,Guangzhou 510o06,China)

Abstract: Aimingat the problemofhow to moreefficientlyuse thedistributedfeatures thatconvolutional neural network have learmed from training images,this paper proposed a ROI(regions of interest）region secondary voting mechanism for facial expresionrecognition.Firstlyitdivided intotheimageaseriesofROIimages,and input itintotheconvolutional neural network for training.Then,itinput intotheROIimagesofthetestimagetheconvolutional neural network,getingallROI images'results.Lastly,itusedthesecondaryvotingmechanismtodeterminethefinalcategoryoftestimage.Inaddition,ming at theproblemofconvolutionalneural networkcannot learn spatialpositioninformationsuchas rotation,this paper introduced theSTN(spatialtransformer network)to makeconvolutional neuralnetwork useful incomplexcondition.Experiments show the ROIregionsecondaryvoting mechanismcan more efectivelyusethedistrbuted features which learned byconvolutional neural network,compared with the method of voting directly using ROI images,the accuracy is increased by $1 . 1 \%$ .The introductionof STNcan effectivelyimprove therobustness ofconvolutional neural network,compared with non-introduced STN networks, the accuracy is increased by $1 . 5 \%$ ：

Key Words: convolutional neural network; expression recognition; STN network; secondary voting mechanism

# 0 引言

人脸表情是由人眼晴、鼻子、嘴巴、眉毛等处的肌肉形变产生的，是人类情感交流最有力、最自然、最直接的手段之一，能够正确反映人当前所处的状态。人脸表情识别能让计算机识别人的表情，并根据表情所反映的信息为人类提供更人性化的服务，在安全驾驶、人机交互、测谎等诸多方面有广泛的应用，因此成为计算机视觉的研究热点之一[1\~3]。

自从Krizhevsky等人[4]利用卷积神经网络在ILSVRC-2012图像识别竞赛取得比手工特征更好的效果，卷积神经网络引起了广泛的关注，学者们对基于卷积神经网络的表情识别进行了一系列的探索与分析[5,6],比如Hamester等人[7提出了一种由标准CNN通道与CAE通道构成的双通道卷积神经网络用于表情识别;Liu等人[8将卷积神经网络提取的特征与手工提取的CBP特征(centralized binarypatterns）相结合，使用SVM分类器进行分类；Meng等人[9在卷积神经网络中提取的表情特征中融合了人身份特征，提升了表情识别地准确率。但在这些方法中，卷积神经网络都是直接学习表情图像的全局特征，没有充分挖掘局部表情的分布式特征，引导卷积神经网络关注表情变化的重点区域。

ROI区域即感兴趣区域。对于不同的计算机视觉任务，重点关注的区域也会不同。设定ROI区域，可以主动引导算法关注重点区域，从而达到提升识别精度、加快处理速度的功能。表情识别中，引入ROI区域，可以引导卷积神经网络关注表情相关的重点区域，从而提高表情识别的精度。已有研究者在基于卷积神经网络的表情识别中引入了ROI区域，比如Vo等人[10]分别使用全局图像与局部图像训练卷积神经网络，分别学习图像的全局信息和局部信息，在测试时利用局部图像测试的结果对全局图像的概率分布进行调整；孙晓等人[1提出将人脸划分为一系列ROI(regionsof interest)区域输入到卷积神经网络中进行训练，在测试时利用ROI图像进行投票，选取票数最多的类别作为结果。上述方法在训练与测试中使用了ROI图像，同时也证明了在测试阶段使用ROI图像进行辅助判别有利于提升卷积神经网络的识别精度。

文献[11]中采用ROI投票进行辅助判别，较传统的基于卷积神经网络的表情识别方法取得了更好的效果。但是由于局部ROI图像包含的信息较少，导致ROI区域容易产生误判。为了充分使用卷积神经网络在训练阶段学习到分布式表达特征，同时降低由于ROI区域图像包含信息量太少对判别结果的影响，本文提出了面向表情识别的ROI区域二级投票机制，通过对全局图像赋予更大的影响因子，降低局部ROI图像对判别结果的影响。另外，为了解决文献[11]中提出的表情识别中卷积神经网络不具有旋转不变性问题，本文将STN网络(spatialtransformernetwork)[12]引入了表情识别中，使卷积神经网络能够学习到表情图像的空间位置信息，提升系统的鲁棒性。

# 1 模型改进方法

本文在文献[11]模型的基础上对ROI图像的辅助判别方法以及模型的旋转不变性进行了研究。接下来，对上述两个方面的研究分别进行介绍。

# 1.1ROI辅助判别方法研究

在卷积神经网络的训练阶段引入ROI图像，不仅可以扩充数据集，防止网络过拟合，又可以使卷积神经网络学习到表情图像的分布式表达特征。为了充分使用卷积神经网络训练阶段学习到的分布式表达特征，同时减少由于局部ROI图像包含信息过少而导致的判别时容易产生误判的问题，本文在文献[11]的基础上提出了ROI区域二级投票机制，提升表情识别的精度。

本文参考文献[11]，根据人脸结构，通过分割、遮挡、翻转、中心聚焦处理，设置9个不同的ROI区域。分割处理时重点关注眼睛、鼻子、嘴巴区域的变化，提取眼睛、鼻子、嘴巴区域图像，得到四幅ROI图像，分别记为ROI0、ROI1、ROI2、ROI3;遮挡处理时分别遮挡脸的上半部分与下半部分，得到两幅ROI图像，分别记为ROI4、ROI5；翻转处理考虑了拍摄的角度不同，将图像进行水平翻转，得到一幅ROI图像，记为ROI6；中心聚焦去除头发等噪声对表情的影响，聚焦人脸表情的重点区域，得到一幅ROI图像，记为ROI7。处理得到的8幅ROI图像加上初始图像(记为ROI8)一共得到9幅ROI图像，9幅ROI图像如图1所示。

![](images/1bf5542e12c32d110b74bb1c821f33691426b94648b1bf78a007eeef0f74396a.jpg)  
图1ROI区域图像

通常，中性表情的眼睛、嘴巴、鼻子等部位没有特别变化;高兴表情具有的特征为嘴角张大或者上扬、眼睛变细、鼻翼上翘；悲伤表情具有的特征为眉毛眼角向下倾、嘴巴张大或者嘴角向下；愤怒表情具有的特征为眉毛上竖、嘴角下扣、眉头紧锁、鼻孔上翘，有时伴随着嘴巴张开；惊讶表情具有的特征为张大嘴、瞪大眼，同时眉毛上扬。但是每种表情都具有一定幅值，不同幅值表情的表达形式也会不一样。例如有时表达高兴情感时嘴巴张开幅度比较大，若将嘴巴部分的ROI图像提取出来，此部分ROI图像与惊讶表情的在嘴巴处的ROI图像相似度比较高，因此若直接对此ROI图像进行判别，容易将此处的ROI图像误判为惊讶。因此，在投票判决时，应适当减少包含局部信息的ROI图像对最终结果的影响，提升具有全局信息的ROI图像对最终判别结果的影响。

本文受决策树多级决策思想的启发，提出了二级投票机制。对于决策树来说，通常采用信息增益来进行划分属性的选择，信息增益计算方法为

$$
E n t ( D ) = - { \sum _ { k = 1 } ^ { | y | } } p _ { k } \log _ { 2 } { p _ { k } }
$$

$$
G a i n ( D , a ) = E n t ( D ) - \sum _ { \nu = 1 } ^ { V } \frac { \left| D ^ { \nu } \right| } { \left| D \right| } E n t ( D ^ { \nu } )
$$

其中：D为样本集； $\mathrm { \Delta V }$ 表示样本具有的某一属性。信息增益越大，该属性的影响越大，则优先采用该属性设置节点。因此，本文为了提升具有全局信息的ROI图像在判别时的影响力，优先采用具有全局信息的ROI图像设置了判别节点。假设 $V _ { i }$ 为表情类别，其中 $i \in [ 0 , 4 ] , W _ { j }$ 为 $W$ 中第 $j$ 幅ROI图像， $j \in [ 0 , 8 ]$ ，$W _ { j 1 }$ 、 $W _ { j 2 }$ 为 $W$ 中具有全局信息的ROI图像，卷积神经网络对$W _ { j 1 }$ 、 $W _ { j 2 }$ 的判别结果为 $V _ { i 1 }$ 、 $V _ { i 2 }$ ，卷积神经网络对 $W$ 中所有图像的判别结果为 $I$ ，经本文提出方法辅助判别后输出的结果为$o$ ，因此，本文提出的方法为：

$$
\textit { O } < - \ : V _ { i 1 }
$$

$$
t < - \operatorname* { m a x } \left( C \right)
$$

在划分的9个ROI区域图像中，ROI6与ROI8包含了完整的表情信息，因此，在利用ROI图像进行投票时，提高ROI6与ROI8对判别结果的影响力，同时降低其他ROI图像对判别结果的影响。因此，本文提出的二级辅助判别的具体步骤如下：

a)将测试图像划分为一系列ROI区域图像。

b)将划分得到的ROI图像输入到训练好的卷积神经网络中，统计每一个ROI图像的判别结果。

c)比较判断ROI6与ROI8的判别结果是否一致。若一致，则将ROI6与ROI8的判别结果归并为测试图像的判别结果；若不一致，则利用ROI-KNN方法进行投票，选取票数最多的结果在线归并为测试图像结果。

# 1.2旋转不变性研究

在实际应用中，人脸图像通常会有一定旋转角度，且拍摄的人脸图像也会有拍摄角度的远近之分。因此，提高系统对旋转、缩放图像的处理能力，可以进一步提升系统的实用性。

针对卷积神经网络不能学习图像的空间信息如旋转、缩放等问题。本文在原卷积神经网络结构的基础上，引入了STN网络用来解决模型不具有旋转不变性的问题。

STN网络由谷歌Jaderberg 等人[12于2015年提出。STN网络由Localisation Network、Grid generator、Sampler3 个模块组成，STN网络结构如图2所示：

![](images/e2706f022aa90337807bd3cbfc91f98a0da0c25d7b85ecaefeb3a3b9c572b018.jpg)  
图2 STN网络结构

本文使用STN 网络学习表情图像的位置信息的过程包含前向传播与反向调整两个阶段。

前向传播过程为：

a)将表情图像输入LocalisationNetwork中，经过全连接层输出变换参数 $\theta$ ，假设得到的 $\theta$ 为

$$
\boldsymbol { \theta } \mathbf { = } \left[ \begin{array} { l l l } { \theta _ { _ { 1 1 } } } & { \theta _ { _ { 1 2 } } } & { \theta _ { _ { 1 3 } } } \\ { \theta _ { _ { 2 1 } } } & { \theta _ { _ { 2 2 } } } & { \theta _ { _ { 2 3 } } } \end{array} \right]
$$

b)将得到的变换参数 $\theta$ 输入到Grid generator模块中，在此模块中得到生成图像与原图像坐标对应关系 $T _ { \theta }$ 。此过程如下所示：

$$
\begin{array} { r }  \bigg [ \mathbf { X } _ { i } ^ { s } \bigg ] = \stackrel { \vartriangle } { \left[ \begin{array} { l l l } { \theta _ { 1 1 } } & { \theta _ { 1 2 } } & { \theta _ { 1 3 } } \\ { \theta _ { 2 1 } } & { \theta _ { 2 2 } } & { \theta _ { 2 3 } } \end{array} \right] } \bigg [ \begin{array} { l } { \boldsymbol { x } _ { i } ^ { t } \bigg ] } \\ { \boldsymbol { y } _ { i } ^ { t } \bigg ] = \boldsymbol { T } _ { \theta } ( G _ { i } ) } \end{array} \end{array}
$$

其中： $( \boldsymbol { X } _ { i } ^ { t } , \boldsymbol { y } _ { i } ^ { t } )$ 为生成网格的坐标； $( \boldsymbol { X } _ { i } ^ { s } , \boldsymbol { y } _ { i } ^ { s } )$ 原图像的坐标。c)利用得到的坐标对应关系进行插值，将原图像坐标中的

像素值依照得到的坐标对应关系在生成网格中进行双线性插值，得到生成图像。公式表达如下：

$$
V _ { i } ^ { C } = \sum _ { n } ^ { H } \sum _ { m } ^ { \nu } U _ { _ { \it m a x } } ^ { C } \operatorname * { m a x } \left( 0 , 1 - \left| X _ { i } ^ { s } - \frac { } { } m \right| \right) \operatorname * { m a x } \left( 0 , 1 - \left| y _ { i } ^ { s } - n \right| \right)
$$

d)将插值得到的生成图像输入到卷积神经网络中进行特征学习。

反向传播过程为

e)计算 $\frac { \hat { \sigma } V _ { i } ^ { C } } { \hat { \sigma } U _ { n m } ^ { C } }$ 播。计算公式如下：

$$
\frac { \partial V _ { i } ^ { c } } { \partial U _ { n m } ^ { c } } = \sum _ { n } ^ { H } \sum _ { m } ^ { W } \operatorname* { m a x } \Big ( 0 , 1 - \Big | x _ { i } ^ { s } - m \Big | \Big ) \operatorname* { m a x } \Big ( 0 , 1 - \Big | y _ { i } ^ { s } - n \Big | \Big )
$$

假设卷积神经网络第一层输出的误差为loss，经STN层输出误差为previous，因此STN中误差反向传播的过程为

$$
\frac { \partial l o s s } { \partial p r e { \nu } i o u s } = \frac { \partial l o s s } { \partial V _ { i } ^ { C } } \bullet \frac { \hat { \sigma } V _ { i } ^ { C } } { \hat { \sigma } U _ { m n } ^ { C } } \bullet \frac { \hat { \sigma } U _ { m n } ^ { C } } { \hat { \sigma } p r e { \nu } i o u s }
$$

f)计算 $\frac { \partial V _ { i } ^ { c } } { \partial { X _ { i } ^ { s } } }$ $\frac { \partial V _ { i } ^ { C } } { \partial y _ { i } ^ { s } }$ 使得能够通过 $V _ { _ { i } } ^ { C }$ 反向调整变换变换参数 $\theta$ 。 $\frac { { \hat { \sigma } } V _ { i } ^ { c } } { { \hat { \sigma } } X _ { i } ^ { s } }$ 计算公式如下, $\frac { { \hat { \partial } } V _ { i } ^ { c } } { { \hat { \partial } } y _ { i } ^ { s } }$ $\frac { { \hat { \sigma } } V _ { i } ^ { c } } { { \hat { \sigma } } X _ { i } ^ { s } }$ 计算过程相似。$\frac { \partial V _ { i } ^ { c } } { \partial x _ { i } ^ { s } } = \sum _ { n } ^ { H } \sum _ { n } ^ { \mu } U _ { a n } ^ { c } \operatorname* { m a x } \Big ( 0 , 1 - \Big | x _ { i } ^ { s } - m \Big | \Big ) \operatorname* { m a x } \Big ( 0 , 1 - \Big | y _ { i } ^ { s } - m \Big | \Big ) \left\{ 1 , \ : \operatorname* { m } \ge \ : x _ { i } ^ { s } \right. \ge 1 \Big .$

因此，STN中网络中参数 $\theta$ 反向调整过程为

$$
\frac { \partial V _ { i } ^ { c } } { \partial \theta } = \left( \frac { \widehat { \frac { \partial V _ { i } ^ { c } } { \partial X _ { i } ^ { s } } } \bullet \frac { \widehat { \frac { \partial X _ { i } ^ { s } } { \partial \theta } } } { \partial \theta } } { \frac { \partial V _ { i } ^ { c } } { \partial y _ { i } ^ { s } } \bullet \frac { \widehat { \frac { \partial Y _ { i } ^ { s } } { \partial \theta } } } { \partial \theta } } \right)
$$

# 2 实验

为了验证本文提出的ROI区域二级投票机制的有效性以及引入STN 是否能够使模型具有旋转不变性，本文就采用本文提出的方法(记为Ours+CNN)与ROI-KNN方法(记为ROI-$\mathrm { K N N + C N N } )$ 以及直接对图像分类的方法(记为 $\mathsf { R O I + C N N } )$ 进行了对比实验。同时在具有旋转的样本情况下，对在卷积神经网络中引入STN网络与未引入STN网络进行了对比实验。

# 2.1实验样本选取及评价指标

本文使用的数据集是孙晓等人[1]采集的混合CK数据集与互联网采集的Wild面部表情数据形成的新的数据集，该数据集包含 $\mathrm { C K ^ { + } }$ (ExtendedCohnKanade）3数据集中的高兴、悲伤、惊讶、愤怒各700张混合互联网下载的上述各种表情的200 张Wild图像，以及900张实验室状态下的中性图像。共5类，每类900 张，一共有4500 张图像。测试集由互联网采集除中性外其他类别的各300张混合300张实验室状态的中性图像，共5类1500张图像，称为数据集I。在数据集I的基础上，孙晓等人对数据集I中的每张图像通过切割、翻转、遮盖、中心聚焦处理后得到9张ROI图像，如图1所示，共5类，每类4500 张图像，测试图像不做变化，称为数据集ⅡI。为了研究注入旋转样本能否使系统具有旋转不变性，孙晓等人[11]对数据集I包含的正规数据进行旋转生成采样，与数据集II相混合，得到5类共83500张图片，称为数据集I。本文采用了数据集ⅡI与数据集III进行实验。

本文实验采用准确率（accuracy）作为评价指标，准确率计算公式如下：

$$
\mathrm { A c c u r a c y } = \left( 1 - { \frac { \hbar \sharp \sharp \bigstar \mathcal { A } _ { f f } \sharp \sharp \sharp _ { \sf c f f } \sharp _ { \sf c o s s } \sharp _ { \sf c o s s } ^ { \prime } \sharp \xi \langle \boldsymbol { \mathcal { A } } _ { \sf c o s s } \rangle _ { \sf c o s s } } { \sharp \sharp \mathcal { A } _ { \sf c o s s } \sharp \langle \boldsymbol { \mathcal { A } } _ { \sf c o s s } \rangle _ { \sf c o s s } } } \right) \times 1 0 0 \%
$$

# 2.2卷积神经网络结构及参数设置

本文采用的卷积神经网络结构参考文献[11]，采用9层卷积神经网络，包括了3个卷积层、3个最大池化层、1个全连接层、1个dropout[4层、1个 softmax 层。网络结构如表1所示。

表1本文采用的卷积神经网络结构  

<html><body><table><tr><td>层数</td><td>类型</td><td>输出特征图</td><td>卷积核尺寸</td><td>池化核尺寸</td></tr><tr><td>0</td><td>Input</td><td>32*32*1</td><td></td><td></td></tr><tr><td>1</td><td>Conv1</td><td>30*30*64</td><td>3*3</td><td></td></tr><tr><td>2</td><td>Pooll</td><td>15*15*64</td><td></td><td>2*2</td></tr><tr><td>3</td><td>Conv2</td><td>12*12*64</td><td>4*4</td><td></td></tr><tr><td>4</td><td>Pool2</td><td>6*6*64</td><td></td><td>2*2</td></tr><tr><td>5</td><td>Conv3</td><td>2*2*128</td><td>5*5</td><td></td></tr><tr><td>6</td><td>Pool3</td><td>1*1*128</td><td></td><td></td></tr><tr><td>7</td><td>Full</td><td>1*1*300</td><td></td><td></td></tr><tr><td>8</td><td>Droput</td><td>1*1*300</td><td></td><td></td></tr><tr><td>9</td><td>Softmax</td><td>1*1*5</td><td></td><td></td></tr></table></body></html>

网络的第一层为卷积层，卷积核大小为 $3 ^ { * } 3$ ，输出64个$3 0 ^ { * } 3 0$ 的特征图；第二层为池化层，池化核大小为 $2 ^ { * } 2$ ，输出64个 $1 5 ^ { * } 1 5$ 的特征图；第三层为卷积层，卷积核大小为 $4 ^ { * } 4$ 输出64个 $1 2 ^ { * } 1 2$ 的特征图；第四层为池化层，池化核大小为$2 ^ { * } 2$ ，输出64个 $6 ^ { * } 6$ 的特征图；第五层为卷积层，卷积核大小为 $5 ^ { * } 5$ ，输出128个 $2 ^ { * } 2$ 的特征图；第六层为池化层，池化核大小为 $2 ^ { * } 2$ ，输出128个 $1 ^ { * } 1$ 的特征图；第七层为全连接层，输出 300 个特征值；第八层为概率为0.5的dropout 层；第九层为 softmax层。卷积层的激活函数采用ReLu[15]函数。

本文的权值与偏置的初始值服从均值为0、标准差为0.1的标准正态分布。训练过程中，每次随机从样本中选取100个样本，共进行 50000 次随机采样。初始学习率为0.01，动量为0.09，每采样5000次验证一次，验证过程中发现准确率不变或下降时，学习率下降一个数量级继续训练，学习率下降到0.0001时不再变化。

# 2.3实验步骤

# 2.3.1ROI辅助判别实验步骤

本文采用数据集II验证本文提出的ROI辅助判别方法，实验主要由卷积神经网络训练、ROI图像测试以及ROI区域辅

助判别三个环节组成。

在卷积神经网络的训练阶段，首先将划分好的ROI图像按照下式进行归一化，将归一化之后的图像输入到卷积神经网络中进行训练，得到训练好的卷积神经网络模型。式中：train_image是归一化之后的图像；image是原始图像。

$$
t r a i n \_ i m a g e = ( i m a g e - ( 2 5 5 / 2 . 0 ) ) / 2 5 5
$$

在ROI图像测试阶段，首先测试图像的ROI图像进行归一化，然后将归一化之后的图像输入到训练好的卷积神经网络当中，统计测试图像的ROI图像的判别结果。

在最终判别阶段，利用本文提出的方法对ROI图像测试阶段统计得到的结果进行处理，得到最终的判别结果。

# 2.3.2旋转不变性研究实验步骤

本文采用数据集II进行旋转不变性的研究。首先将数据集III输入到卷积神经网络当中进行训练，训练完成之后将测试数据集输入到训练好的网络当中，记录测试的准确率。

接下来在卷积神经网络的第一层中引入STN网络，同样将数据集III输入到引入了STN的卷积神经网络当中进行训练，训练完成之后将测试图像输入到训练好的网络当中，记录测试的准确率。

# 3 实验结果与分析

# 3.1ROI辅助判别实验结果与分析

为验证本文方法的有效性，将本文提出的方法与ROI-KNN方法以及利用ROI图像进行数据增强的方法进行对比实验，实验结果如表2所示。

表2不同辅助判别方法准确率对比  

<html><body><table><tr><td>方法</td><td>准确率</td></tr><tr><td>Ours+CNN</td><td>78%</td></tr><tr><td>ROI-KNN+CNN</td><td>76.9%</td></tr><tr><td>ROI+CNN</td><td>73.2%</td></tr></table></body></html>

由表2可知，在整体准确率上，采用本文提出的方法进行人脸表情识别准确率达到 $78 \%$ ，比 ${ \mathrm { R O I - K N N + C N N } }$ 方法准确率提高了 $1 . 1 \%$ ，比 $\mathrm { R O I + C N N }$ 方法识别准确率提高了 $4 . 8 \%$ 。由此可见，本文提出的方法取得了最好的效果。

为了分析本文方法取得最好效果的原因，本文在实验中引入了混淆矩阵观察每个类别的分类情况。Ours+CNN方法实验结果的混淆矩阵如图3所示，ROI-KNN+CNN方法实验结果的混淆矩阵如图4所示， $\mathrm { R O I + C N N }$ 方法实验结果的混淆矩阵如图5所示。

混淆矩阵横轴为预测的类别，纵轴为实际类别。矩阵中从左到右依次是中性、高兴、悲伤、惊讶、愤怒。对角线中的数值表示每个类别的分类的准确率。

由混淆矩阵可知，本文提出的方法在自然、高兴、悲伤、惊讶、愤怒表情中的识别准确率分别为0.98、0.71、0.56、0.89、0.76；ROI-KNN+CNN方法在上述表情的识别准确率分别为0.98、0.69、0.54、0.88、0.75；ROI+CNN法在上述表情的识别准确率分别为0.96、0.66、0.49、0.83、0.68。

![](images/468ab3e578dfa533edca8c41b7a57c0da8c814e6690d1af5eab2cdf9cb676b42.jpg)  
图3Ours+CNN

![](images/54740007f8ca07f6f6b826bd519adc382b6dc0ee7c4289c3e48aa3660da7ba5d.jpg)  
图4 ROI-KNN+CNN

![](images/af3fac428f8b9a48d00d844c25839ba562eb9fa04c2e46178febdc317fb75a01.jpg)  
图5ROI+CNN

由此可见，本文提出的方法与ROI-KNN方法在各个表情都能取得比 $\mathrm { R O I + C N N }$ 更高的准确率，说明在测试阶段引入ROI图像进行辅助判别，充分使用网络从ROI图像中学习到的信息，能有效地提升系统对表情地判别能力。对于本文提出的方法与ROI-KNN方法，由混淆矩阵可知，本文提出的方法与ROI-KNN方法在各表情类别中准确率相接近甚至更高，在整体准确率上，本文提出的方法要比ROI-KNN方法准确率更高。

为了分析本文提出方法能够取得比ROI-KNN卷积神经网络取得更好效果的原因，本文挑选出本文分类正确、ROI-KNN方法分类错误的样本，如图6所示，并对这些样本的ROI图像的类别概率分布进行可视化，如表3所示。由于情况相同，本文以图6以及图6对应的类别概率分布进行分析。

![](images/b9a0172b3b0418d22283caa9065bf2e75e8d6781c35bc1324a3a234b27cad04a.jpg)  
图6ROI-KNN 错分样本

表3ROI-KNN 错分样本类别概率分布  

<html><body><table><tr><td rowspan="2">ROI</td><td colspan="5">类别概率分布</td></tr><tr><td>中性</td><td>高兴</td><td>悲伤</td><td>惊讶</td><td>愤怒</td></tr><tr><td>图像 0</td><td>0.000</td><td>0.000</td><td>0.100</td><td>0.900</td><td>0.000</td></tr><tr><td>1</td><td>0.749</td><td>0.245</td><td>0.005</td><td>0.002</td><td>0.000</td></tr><tr><td>2</td><td>0.000</td><td>0.002</td><td>0.118</td><td>0.855</td><td>0.024</td></tr><tr><td>3</td><td>0.002</td><td>0.561</td><td>0.131</td><td>0.307</td><td>0.000</td></tr><tr><td>4</td><td>0.000</td><td>0.017</td><td>0.139</td><td>0.844</td><td>0.000</td></tr><tr><td>5</td><td>0.000</td><td>0.629</td><td>0.357</td><td>0.013</td><td>0.000</td></tr><tr><td>6</td><td>0.000</td><td>0.001</td><td>0.994</td><td>0.005</td><td>0.000</td></tr><tr><td>7</td><td>0.839</td><td>0.149</td><td>0.009</td><td>0.000</td><td>0.002</td></tr><tr><td>8</td><td>0.000</td><td>0.992</td><td>0.003</td><td>0.005</td><td>0.000</td></tr></table></body></html>

表3中的ROI图像分别对应于图6中从左到右的图像。对于每幅图像，通常都是选取类别概率分布中最大概率值对应的类别作为此ROI图像的类别。

表3中，ROI0、ROI2、ROI4都在惊讶的表情中拥有最大概率值0.900、0.855、0.844，因此有3幅ROI图像被判别为惊讶。同理，ROI3、ROI5、ROI8在高兴表情的概率分别为0561、0.629、0.992，在各类别概率分布中拥有最大值，因此这3幅ROI图像被判别为高兴，出现了多幅局部ROI图像产生误判的情况，此时导致ROI-KNN产生误判。将图像划分成ROI图像后，局部ROI图像包含的信息较少，这些包含局部信息的ROI图像与其他表情的ROI图像比较相似，容易将ROI图像判断为具有相似ROI图像的其他表情。当某测试图像中多个ROI图像被误判为具有相似ROI图像的其他表情时，容易出现误判的ROI图像与正确判断的ROI图像相等甚至超过正确判断的ROI图像的情况，使得ROI-KNN方法产生误判。而本文提出的ROI区域二级投票机制，首先将两幅具有完整信息的ROI图像的判断结果进行比较，当结果不一致时，再采用投票机制，确定最终的判决结果，此时可以在一定程度上降低包含局部信息的ROI图像对最终判决结果的影响，因此取得了更好的效果。

另外，由于 $\mathrm { R O I + C N N }$ 对图像进行判别时只需要对测试图像进行一次判别，而本文与ROI-KNN 方法都需要对测试图像的所有ROI图像进行判别，所以需要进行9次判别。因此本文还针对引入辅助判别是否会增加判别时间进行实验。经实验得，判别1500张图像， $\mathrm { R O I + C N N }$ 方法用了 $0 . 1 2 5 \mathrm { ~ s ~ }$ ，引入辅助判别方法用了 $0 . 6 8 0 \mathrm { s }$ 。可见，引入了辅助判别仅比未引入辅助判别方法多了 $0 . 5 5 5 \mathrm { s }$ ，但是准确率确提升了 $4 . 8 \%$ 。因此，本文提出方法能够在略微增加判决时间的前提下，取得更好的判别结果。

# 3.2旋转不变性研究实验结果与分析

本文利用数据集II设置了6组实验，其中3组实验引入了STN，3组未引入STN。实验结果如表4所示。

表4引入STN实验结果对比  

<html><body><table><tr><td>未引入STN</td><td>准确率</td><td>引入STN</td><td>准确率</td></tr><tr><td>ROI+CNN</td><td>73.5%</td><td>ROI+ CNN</td><td>75%</td></tr><tr><td>Ours+CNN</td><td>76.7%</td><td>Ours+ CNN</td><td>78.4%</td></tr><tr><td>ROI-KNN+CNN</td><td>74.8%</td><td>ROI-KNN+CNN</td><td>76.9%</td></tr></table></body></html>

由表4可知，在 $\mathrm { R O I + C N N }$ 实验中，引入STN 网络进行表情识别准确率达 $7 5 \%$ ，比未引入STN 网络的识别准确率提高了 $1 . 5 \%$ ；在Ours+CNN实验中，引入STN网络识别准确率达 $78 . 4 \%$ ，比未引入STN网络的识别准确率提高了 $1 . 7 \%$ 。在ROI-KNN+CNN实验中，引入STN网络识别准确率为 $76 . 9 \%$ ，比未引入STN 网络准确率提升了 $2 . 1 \%$ 。因此，在训练样本中注入了旋转样本的情况下，引入STN网络能够提升表情识别的准确率。同时，由在未引入STN网络以及引入STN情况下，本文提出的二级投票机制的识别准确率都高于ROI-KNN方法，进一步证明了本文提出的二级投票机制的有效性。

为了进一步观察在表情识别任务中引入STN网络的效果，本文引入了混淆矩阵进行观察。由于 $\mathrm { R O I + C N N }$ 中未使用辅助判别方法，所以以 $\mathrm { R O I + C N N }$ 中引入 STN 网络与未引入 STN网络生成的混淆矩阵为例进行分析。 $\mathrm { R O I + C N N }$ 中未引入STN网络实验结果的混淆矩阵如图7所示，引入STN网络实验结果的混淆矩阵如图8所示。

![](images/9395658653e323c96b5644214cbb4d88d0429aef12be98e694e9562cf2a8220f.jpg)  
图7未引入STN网络

![](images/d59ae16a0911f6dfc8f35df78f9b46582b7e9f9041ae068c4fec2133a8b08c58.jpg)  
图8引入STN网络

由混淆矩阵可知，卷积神经网络中引入STN网络后，在自然、高兴、悲伤、惊喜、愤怒五种情感中的准确率分别为0.98、0.73、0.43、0.84、0.77，而卷积神经网络中未引入STN时在上述表情的识别准确率分别为0.96、0.73、0.45、0.82、0.71。由此表明，在注入旋转样本的前提下，引入STN网络在大部分表情中都能比未引入STN网络获得更高的准确率，说明在卷积神经网络中引入STN网络，能够使卷积神经网络学习到图像的空间信息，使得卷积神经网络能够获得更高的识别准确率。同时，由于中性表情是处于实验室状态下的图像，而在中性表情中引入STN网络后并未出现准确率降低的情况，所以说明引入STN网络之后不会对不具有旋转角度的图像产生不良影响。

另外，由于本文在卷积神经网络的第一层引入了STN网络，相较于未引入STN网络的卷积神经网络增加了 $3 2 \times 3 2 \times$ $6 { = } 6 1 4 4$ 个连接，所以本文还针对引入STN网络之后所需要的训练时间进行实验。经实验得，引入STN网络所需训练时间为$\mathrm { ~ 1 ~ } 3 8 3 \mathrm { ~ s ~ }$ ，测试时间为 $0 . 2 2 9 \mathrm { ~ s ~ }$ ，而未引入STN所需训练时间为$9 2 8 \mathrm { ~ s ~ }$ ，测试时间为 $0 . 1 4 8 \mathrm { ~ s ~ }$ ，由此可见，引入STN网络比未引入STN网络训练时间多了 $4 5 5 \mathrm { ~ s ~ }$ ，测试时间多了0.081s。由此可见，引入STN网络虽然增加了一定的训练时间，但是测试时间未明显增加，因此，引入STN网络能够在几乎未增加判决时间的基础上有效解决表情识别任务中的旋转不变性问题，从而满足实时处理的需要。

# 4 结束语

在人脸表情识别任务中，为了充分使用卷积神经网络在训练阶段学习到的分布式特征，并且降低由于局部ROI图像包含信息量较少导致的误判对最终判别结果的影响，本文提出了一种二级投票机制对表情图像进行辅助判别方法，并将本文提出的方法与ROI-KNN方法以及仅在训练采用ROI图像进行数据增强的方法进行比较。实验结果表明，本文提出的二级投票机制能够获得更好的效果。另外，本文还对如何让卷积神经网络学习到表情图像的空间位置信息进行研究，将STN网络引入到表情识别任务中，使卷积神经网络具有旋转不变性，提升了系统的鲁棒性。本文提出的方法虽然提升了表情识别的准确率，但是对不同光照、不同角度等复杂情况下的表情图像处理能力还不够强，因此建立一个能在复杂情况下准确识别表情的表情识别系统将是下一步的研究重点。

# 参考文献：

[1]Hernandez-Matamoros A,BonariniA,Escamilla-Hernandez E,et al.Facial expression recognition with automatic segmentation of face regions using a fuzzy based classification approach [J].Knowledge-Base Systems,2016, 110: 1-14.   
[2]Shan Caifeng,Gong Shaogang,McOwan PW.Facial expression recognition based on Local Binary Patterns:A comprehensive study [J]. Image and Vision Computing,2009,6 (27): 803-816.   
[3]罗源，张灵，陈云华，等．基于层次结构化字典学习的人脸表情识别 [J].计算机应用研究,2017,34(11):3514-3517.(Luo Yuan,Zhang Ling, Chen Yunhua,et al. Facial expression recognition based on hierarchy structured dictionary learning [J].Application Research of Computer, 2017, 34 (11): 3514-3517.)   
[4]KrizhevskyA, Sutskever I, Hinton G E.ImageNet classification with deep convolutional neural networks $[ \mathrm { C } ] / \hbar$ Proc of International Conference on Neural Information Processing Systems.2012:1097-1105.   
[5]Shin M,Kim M,Kwon D S.Baseline CNN structure analysis for facial expression recognition[C]//Proc of the 25th IEEE International Symposium on Robot and Human Interactive Communication.2016:724-729.   
[6]Perveen N,Singh D,Mohan CK. Spontaneous facial expression recognition: a part based approach [C]// Proc of IEEE International Conference on Machine Learning and Applications.2017: 819-824.   
[7]Hamester D,Barros P,Wermter S.Face expression recognition with a 2- channel convolutional neural network [C]//Proc of International Joint Conference on Neural Networks.2O15:1-8.   
[8]Liu Yize,Chen Yixiang.Recognition of facial expression based on CNNCBP features [C]// Proc of the 29th Chinese Control And Decision Conference.2017: 2139-2145.   
[9]Meng Zibo,Liu Ping,Cai Jie,et al.Identity-aware convolutional neural network for facial expression recognition [C]//Proc of the 12th International Conference on Automatic Face & Gesture Recognition.2017:558-565.   
[10] Vo D M,Sugimoto A,Le TH. Facial expression recognition by re-ranking with global and local generic features [C]//Proc of the 23rd International Conference on Pattern Recognition.2017:4118-4123.   
[11]孙晓，潘汀，任福继．基于ROI-KNN卷积神经网络的面部表情识别[J]. 自动化学报,2016,42(6):883-890.(Sun Xiao,Pan Ting,Ren Fuji.Facial expression recognition using ROI-KNN deep convolutional neural networks [J].Acta Automatica Sinica,2016,42(6): 883-890.)   
[12] Jaderberg M, Simonyan K,Zisserman A,et al. Spatial transformer networks [C]/Proc of IEEE Conference on Computer Vision and Pattern Recognition 2015:665-673.   
[13] LuceyP,Cohn JF,Kanade T,et al. The extended cohn-kanade dataset $\mathrm { ( C K + ) }$ ： a complete dataset for action unit and emotion-specied expression [C]//Proc of Computer Vision and Pattern Recognition Workshops.2010: 94-101.   
[14]Hinton G E,Srivastava N,Krizhevsky A,et all.Improving neural networks by preventing coadaptation of feature detectors [J].Computer Science,2012, 3 (4):212-223.   
[15] Glorot X,Bordes A,Bengio Y.Deep sparse rectifier neural networks [C]// Proc of the International Conference on Artificial Intelligence and Statistics. 2012:315-323.