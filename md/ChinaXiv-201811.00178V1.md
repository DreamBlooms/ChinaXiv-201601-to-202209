# 基于CNN和DLTL的步态虚拟样本生成方法

支双双1，赵庆会²，金大海1，唐珙²(1．西安工程大学 工程训练中心，西安 710048;2．中南大学 信息科学与工程学院，长沙 410083)

摘要：针对步态识别在反恐、安防领域亟待解决的小样本问题,提出了一种基于深度卷积神经网络CNN(convolutionaland neural network)和DLTL(dual learning and transfer learning)的步态虚拟样本生成方法。首先用基于VGG19的深度卷积神经网络模型低层响应提取步态风格特征图，然后利用基于对抗网络的对偶学习 DL(dual leaming)对风格特征图进行风格训练，得到风格特征模型；其次利用VGG19 模型的高层响应提取步态内容特征图，然后让步态内容特征图对风格特征模型中的风格特征进行学习；最后使用迁移学习TL(transferleaming)获得步态虚拟偏移样本。实验结果表明，经过DLTL风格学习生成的步态虚拟样本虽然整体风格发生改变,但人体步态特征没有改变,可有效扩充小样本容量；当虚拟样本数量增加到一定数量，步态识别率有所提升。该方法与现有步态虚拟样本生成方法进行对比实验，结果表明该算法优于现有方法，能够大量生成虚拟样本且稳定提高步态识别的识别率。

关键词：步态识别；卷积神经网络；DLTL；虚拟样本；步态识别率 中图分类号：TP391.4 doi: 10.19734/j.issn.1001-3695.2018.05.0504

# Gait virtual sample generation method based on CNN and DLTL

Zhi Shuangshuang1, Zhao Qinghui², Jin Dahai', Tang Jin2† (1.EngineeringTainingCenter,Xi'anPolytechnicUniversity,Xiananni7048,China;2.SchoolofInformationScience &Engineering,Center South University,Changsha 41oo83,China)

Abstract:Tosolve the problemofsmallsmpleof gaitrecognition in the fieldofcounterterorismand securityissues,this paper proposed a novel gait virtual sample generation method based on deep CNN(Convolutional and Neural Network)and DLTL(Dual Learning and TransferLearning).Firstly,low-level ofCNNmodel VGG19 extracted gait style feature map,and thenitused theDL(DualLearning)tocarryonthestyle featuretraining.Thus it madestyle featuremodel.Moreover,igh-level ofVGG19 extracted gait context feature map,and then itused theTL(TransferLearning)to make context feature mapcarryon thestylecharacteristiclearing.Finalyitobtainedthevirtualmigrationsmples.Experimentalresultsdemonstratethatthese virtual samples remained individual gait feature but style feature.So this method can effectively expand smallsample size.At thesam time,when thenumberofvirtualsamples increase toacertain number,gait recognitionrate has improved.The method was compared withthe existing virtual sample generation method.The result shows thatthe method has abeter performance, which can generate virtual samples in large numbers and improve the recognition rate of gait recognition steadily.

Key words: gait recognition; CNN; DLTL; virtual sample; gait recognition rate

# 0 引言

步态识别是依据行人步行的图像序列来提取生物特征的一种方法。与DNA、指纹、虹膜、2D与3D人脸等生物特征识别方法相比，步态识别具有不需被观察者配合、可在较远距离进行、可在较低图像质量下进行，且难以伪装和掩藏[1等优点。因此,基于步态特征的身份识别方法成为近年来的研究热点[2.3],在安防和反恐等领域的应用研究得到了国内外学者的重视[4]。

步态识别在特征提取过程中，按照是否需要使用相关人体姿态参数，分为模型无关（形体统计方法)和构建模型的方法。模型无关的步态识别方法将步态外形轮廓直接进行特征提取和匹配(无须构建人体模型结构数据)，按轮廓数据又可细分为2D，2.5D或3D步态外形轮廓的识别方法。另一类通过使用人体模型进行步态识别，人体的模型可分为2D模型（棍棒模型，铰链模型等)和3D人体模型(3D椭圆模型，3D关节骨架模型)。模型无关的步态识别方法，其特点是可以直接使用步态轮廓数据。基于模型的方法，对图像像素和清晰度的要求略高，由于需要构建人体模型，特别是三维人体模型时，其运算复杂度会高于模型无关的方法。

目前基于非模型的研究是步态识别研究的一个重要方向。模型无关的步态识别方法，提取周期内步态轮廓统计信息，对反映形体和运动特征的轮廓数据直接进行匹配。最基础的匹配方法，就是先将步态轮廓按不同时序和姿态进行同步，然后将相同姿态的不同人体步态轮廓直接进行相似性比较，可以使用欧氏距离、余弦距离等。其他的一种通用方法，即是计算步态轮廓序列的均值，构成步态能量图GEI(gait energy image)[5]，再进行匹配。以步态能量图为基础，衍生了许多相关特征的能量图，比如，运动步态轮廓图 MSI(motion silhouete image)[6]，步态光流图GFI(gait flow image)[7]，彩色步态图 CGI(color gaitimage)[8],帧间差分能量图FDEI(frame difference energy image)[9].步态能量体GEV(gait energy volume)[o]，梯度直方能量图DGHEI(depth gradient histogram energy image)[1l],基于曲率的步态彩色能量图 CGCEI(curve-based gait color energy image)[12]等。步态能量图的特点相当明显，计算复杂度小，同时由于采用了轮廓平均，对图像分布噪声有较好的抑制作用。

模型无关的步态识别方法虽然已取得了很大进展，但仍存在多协变量引起的轮廓缺失与人体阴影、步态识别的视角差、小样本等难点问题。步态识别由于步态周期长和拍摄艰难等因素，很难采集到大量的步态样本。当前步态识别的公开步态库也只有数量有限的样本，而且每个人的步态样本数目较少，这就是步态识别数据量问题的集中表现。

对于图像识别的小样本问题，有学者提出了一种基于先验知识从给定小规模真实样本产生虚拟训练样本的方法[13]。目前的研究有利用BPNN 和巨型趋势分散技术[14]、利用原始样本分布函数[15]等。文献[16]提出用分散神经网络（decentralized neuralnetworks,DNN）产生虚拟样本，表明DNN比BPNN具有更强的预测性能；文献[17\~19]提出基于遗传算法（GA)、粒子群优化（particle swarmoptimization,PSO）算法以及蒙特卡洛与PSO相结合的虚拟样本生成算法。为了解决步态识别过程中的小样本问题，目前基于能量图的步态虚拟样本生成方法主要包括：合成步态模板[20]和基于对抗网络[21]的虚拟样本生成方法。基于合成步态模板的虚拟样本生成方法会破坏能量图轮廓的完整度，导致该方法不能大量生成虚拟样本。而基于对抗网络的虚拟样本生成方法由于随机噪声引起的不确定性，导致生产的步态虚拟样本鲁棒性差且不稳定。

为了更好的解决步态识别小样本问题，本文提出一种基于深度CNN和DLTL风格学习的虚拟样本生成方法。首先用基于深度卷积神经网络模型低层响应提取步态风格特征图,然后利用基于对抗网络的对偶学习对风格特征图进行风格训练，得到风格特征模型。接着利用VGG19模型的高层响应提取步态内容特征图，然后让步态内容特征图对风格特征模型中的风格特征进行学习。最后使用迁移学习获得步态虚拟偏移样本。该

方法可有效扩充步态样本。

# 1基于 CNN 和 DLTL 风格学习的虚拟样本生成方法

该方法的提出源自实际应用中步态人体轮廓分割不能达到$100 \%$ 的分割正确率，而环境协变量的变化会引起步态人体轮廓分割位置和分割效果的变化。正是基于这样的原因，本文才提出通过基于CNN和DLTL风格学习的步态虚拟样本生成方法来改变步态识别样本的风格背景与气候，以此达到大量生成步态虚拟样本的目的。该方法主要思路是首先用基于VGG19的深度卷积神经网络模型低层响应提取步态风格特征图,然后利用基于对抗网络的对偶学习DL(DualLearning)对风格特征图进行风格训练，得到风格特征模型。然后利用VGG19模型的高层响应提取步态内容特征图，然后让步态内容特征图进行学习风格特征模型中的风格特征学习。该方法的结构图如图1所示。

低层响应提 基于对偶学  
大数据原 风格特库 →取风格特征 习的凤特 风络特征型?  
小数据目 集态样本 肉 行 步本1

# 1.1VGG19模型网络图

深度CNN 通过多次卷积变换和降采样，将图像映射到一个较低维空间，提取图像的稀疏特征；同时由于其使用权值共享，使得神经元和参数个数更少，更加易于训练。当前大数据环境下，具有足够深度的CNN模型已经成为解决计算机视觉领域众多问题的重要工具[22]。

Karen 等提出的VGGnet采用 $3 { \times } 3$ 的卷积核，同时在若干卷积层后加入池化层。网络层数增加有利于提高图像分类的准确度，但过多的层数会产生网络退化问题[23]。VGG19 包含 16个卷积层（Convl_1-Conv5_4）、5个池化层(pooll-pool5)、3个全连接层(Fc6-Fc8)，VGG19的激活函数使用矫正线性单元（rectification linearuint,Relu）。VGG19的结构如图2所示。

Data Convl Relul_1 Conv1_2 Relu1_2 Pooll Conv2_ Relu2_1 Conv2_2 Relu2_2 Pool2 Conv3_ Relu3_1 Conv3_2 Cony323 Relu3_3 Conv3_4 Relu3_4 Pool3 Conv4_1 Relu4_1 Conv4_2 Relu4_2 Conv4_3 Relu4_3 Conv4_4 Relu4_4 Pool4 Conv5_1 Relu5_1 Conv5_2 Relu5_2 Conv5_3 Relu5_3 Conv5_4 Relu5_4 Pool5 Fc6 Relu6 Drop6 Fc7 Fc8 Prob

# 1.2图像内容特征与风格特征提取

图像特征可分为内容和风格，它们可以运用深度CNN 模型中卷积层的响应进行表征。在深度CNN模型中低层次响应

描述的特征是图像风格，而高层次响应描述的则是图像的内容[24]。

# 1.2.1图像内容特征图提取

采用随机噪声生成一张与目标图像 $\overline { { { \boldsymbol X } ^ { 0 } } }$ 尺寸一样的图像$X ^ { 0 }$ ,并将图像输入到CNN模型中。在该网络模型第I个卷积层响应可标为 $X ^ { l }$ ，其尺寸大小为 $H ^ { l } \times W ^ { l } \times N ^ { l }$ ,其中 $H$ 表示图像高度， $W$ 表示图像宽度， $N$ 表示图像像素点数。类似地，可将目标图像 $\overline { { { X } ^ { 0 } } }$ 也输入到该网络模型中，可得到该层的特征响应 $\overline { { { X } ^ { l } } }$ v由于期望 $\overline { { { X } ^ { 0 } } }$ 与 $X ^ { 0 }$ 的图像内容一致，所以目标函数为最小化二范数误差：

$$
E _ { c } ^ { l } = \frac { 1 } { 2 } { \left\| { X ^ { l } - \overline { { { X ^ { l } } } } } \right\| } ^ { 2 }
$$

可以使用该误差函数对本层各响应的元素进行求导运算：

$$
\frac { \partial E _ { c } ^ { l } } { \partial x _ { h w k } ^ { l } } = x _ { h w k } ^ { l } - \overline { { x _ { h w k } ^ { l } } }
$$

其中： $h = 1 , 2 , 3 , . . . , H , w = 1 , 2 , 3 , . . . W , k = 1 , 2 , 3 , . . . , N$ 。采用链式法则，对输入的图像元素进行误差求导，可得 $\hat { c } E _ { c } ^ { l } \big / \hat { c } x _ { h w k } ^ { l }$ ，这就是经典的反向传播算法。采用 $\hat { o } E _ { c } ^ { l } \big / \hat { o } x _ { h w k } ^ { 0 }$ 来对 $X ^ { \dag }$ 进行更新，以获得新的更接近目标图像响应 $\overline { { { X } ^ { 0 } } }$ 的第 $l$ 层响应 $X ^ { l }$ ，即为提取到目标图像的内容特征图。

# 1.2.2图像风格特征图提取

为了提取图像风格特征图，先构建一个 $N ^ { l } \times N ^ { l }$ 的特征矩阵$\boldsymbol { G } ^ { l }$ ：

$$
\begin{array} { r } { G ^ { l } = \sum x _ { h w x } ^ { l } \cdot x _ { h w y } ^ { l } } \end{array}
$$

其中： $\boldsymbol { x } = 1 , 2 , 3 , . . . , N$ ， $y = 1 , 2 , 3 , . . . , N$ 。 $\boldsymbol { G } ^ { l }$ 是通过计算消除了位置信息的第l层响应得到的，即为风格描述。 $x y$ 位置的元素表示第$\mathbf { x }$ 个与第y个通道响应的相关性。对于目标图像在每一层的风格 $\overline { { G ^ { l } } }$ ，其目标函数可以通过最小化下面的误差函数获得。

$$
E _ { S } ^ { l } = \frac { 1 } { 2 } \bigg \| G ^ { l } - \overline { { G ^ { l } } } \bigg \| ^ { 2 }
$$

可以推导出该误差函数在各层响应的导数：

$$
\frac { \partial E _ { s } ^ { l } } { \partial x _ { h w k } ^ { l } } = \left( x ^ { l } \right) ^ { T } \left( G ^ { l } - \overline { { G ^ { l } } } \right) _ { y x }
$$

类似地可以通过反向传播算法推导出 $\partial E _ { s } ^ { l } \big / { \hat { o } } X ^ { 0 }$ ，以此更新$X ^ { 0 }$ ，使得它更接近 $\overline { { { X } ^ { 0 } } }$ 的风格，即为图像风格特征提取图。

本文的分类网络模型选用的是VGG19深度卷积神经网络模型。从该模型的convl_1,conv2_1,conv3_1,conv4_1,conv5_1层提取大数据原始集的风格特征图，从该模型的conv4_2层提取小数据目标集的步态内容特征图。

# 1.3基于对偶学习DL的风格训练

对偶学习(DL)的基本思路是构建一个具有两个对偶任务的闭环反馈系统，该系统能够从未标注数据上得到反馈信息，并以此反馈信息提高对偶任务的训练模型。假设有两种不同风格的图像集X和Y，可从中训练出两种映射 $\mathrm { G } { \cdot } \mathrm { X } {  } \mathrm { Y }$ 和 $\operatorname { F } { \mathrm { : Y } } \to \operatorname X$ ，其中G和F映射关系是可以相互转换的。对偶学习采用同时训练G和F两种映射，并添加循环一致性损失函数，促使

$F { \bigl ( } G ( x ) { \bigr ) } \approx x$ 和 $G { \big ( } F { \big ( } y { \big ) } { \big ) } \approx y$ 。如图3所示，图3(a)表示的是两个映射函数 $\mathrm { G } { : } \mathrm { X } { \to } \mathrm { Y }$ 和 $\operatorname { F } { : \mathrm { Y } \to \mathrm { X } }$ ，以及相应的对抗网络判别器 $\mathrm { \Delta D _ { X } }$ 和$\mathrm { D v }$ 。 $\mathrm { D v }$ 激励G映射将X转换成与真实风格样本无法辨别的虚拟风格，反之亦然。为了进一步规范映射引入loss 损失函数，图3(b)是前向损失函数： $\mathrm { x { \to } G ( x ) { \to } F ( G ( x ) ) } \approx \mathbf { x }$ ，图3(c)则是反向损失函数 $\mathrm { y } \{ \partial \mathrm { F ( y ) } \partial \mathrm { G ( F ( y ) ) } \approx \mathrm { y } \mathrm { , }$

![](images/a8ab8aa3d31a885d2a980ac17f5645f70ce2bbaf994139089e823620de677b3f.jpg)  
图3对偶学习风格转换  
Fig.3Style transformation of dual learning

对于前向和后向损失函数，借鉴了最小二乘对抗网络模型的损失函数描述映射函数G： $\mathrm { X }  {  } \mathrm { Y }$ 及判别器 $\mathrm { D } _ { \mathrm { Y } }$ ，具体定义如下：

$$
\begin{array} { r } { l \big ( G , F , D _ { X } , D _ { Y } \big ) = l _ { G A N \ " \mathbb { H } \left[ \Game \right] } \big ( G , D _ { Y } , X , Y \big ) + l _ { G A N \widetilde { \mathscr { D } } \left[ \Game \right] } \big ( F , D _ { X } , Y , X \big ) + \lambda l _ { \widetilde { \mathscr { P } } \left[ \mathscr { P } \right] } \big ( G , F \big ) \big ( 6 , 7 \big ) \int _ { - \infty } ^ { \infty } \frac { 1 } { 2 \pi l _ { N } ^ { 2 } } \ d \big ( \widetilde { A } \big ) \widetilde { \mathscr { P } } \left[ \mathscr { P } \right] \ d \big ( X , X , X \big ) , } \end{array}
$$

其中整个对偶学习的前向损失函数如下：

$l _ { G A N \sharp \sharp \sharp } ( G , D _ { Y } , X , Y ) = E _ { y \sim P _ { y } } \left[ \log D _ { Y } \big ( y \big ) \right] + E _ { x \sim P _ { x } } \left[ \log \left( 1 - D _ { Y } \big ( G ( x ) \big ) \right) \right] ( 7 )$ （204号其中整个对偶学习的反向损失函数如下:

$$
l _ { \mathit { G A N S } | \mathit { \tilde { \Theta } } } ( G , D _ { x } , Y , X ) = E _ { x \sim P _ { x } } \left[ \log D _ { x } \left( x \right) \right] + E _ { y \sim P _ { y } } \left[ \log \left( 1 - D _ { x } \left( F ( y ) \right) \right) \right] .
$$

其中整个对偶学习的激励调节损失函数如下:

$$
\begin{array} { r } { l _ { \underset { \mathrm { s u r f i f j } } { \rtimes } } ( G , F ) = E _ { x \sim P _ { x } } \| F ( G ( x ) ) - x \| _ { 1 } + E _ { y \sim P _ { y } } \| G ( F ( y ) ) - y \| _ { 1 } } \end{array}
$$

其中： $\mathrm { \bf P _ { x } }$ 是 $\mathbf { x }$ 的真实分布， $\mathrm { P _ { y } }$ 是 $\mathbf { y }$ 的真实分布。式（7）中，当$\mathrm { D v }$ 激励G映射将X转换为和Y无法辨别时，前向损失函数最小；同理，式（8）中，当 $\mathrm { D } _ { \mathrm { x } }$ 激励 $\mathrm { ~ F ~ }$ 映射将 $\mathrm { \Delta Y }$ 转换为和X无法辨别时，反向损失函数最小。

风格训练的思路是通过生成器根据G映射关系将X风格集特征转换为Y风格集特征，并使用判别器 $\mathrm { D } _ { \mathrm { Y } }$ 对生成样本进行反馈激励，以期产生与真实风格 $\mathrm { \Delta Y }$ 相似的样本。同样地，通过生成器根据F映射关系将Y风格集特征转换为X风格集特征，并使用判别器 $\mathrm { \Delta D x }$ 对生成样本进行反馈激励，以期产生与真实风格X相似的样本。若通过 $l \big ( G , F , D _ { X } , D _ { Y } \big )$ 损失函数则可以将二者结合，构建可以相互风格转换的对偶学习模型，以产生多样的风格转换特征模型。在本文中使用对偶学习进行夏天和冬天风格训练，得到冬天和夏天的风格特征模型。

基于迁移学习TL的风格学习

迁移学习(TL)的本质是利用已有的知识学习新的知识，核心是找到已有的知识和新知识的相似性[25]。本文基于迁移学习TL 的风格学习方法采用的是让步态内容特征图对风格特征模型进行风格学习。风格学习算法将随机生成一张白噪声图作为输入，保持分类网络模型VGG19的各层权重不变，计算内容特征图和风格预训练模型在各卷积层的损失值，再使用标准BP算法对学习过程进行权重更新，并调整输入图像使内容和风格损失值达到最小，这样就可以使得步态内容特征图通过调节参数学习到风格预训练模型中的不同的环境风格，生成最终的步态虚拟样本。风格学习损失函数如式(10)所示：

$$
l _ { t o t a l } \left( I _ { 1 } , I _ { s u m } , I _ { 2 } \right) = \alpha * l _ { s t y l e } \left( I _ { 1 } , I _ { s u m } \right) + \beta * l _ { c o n t e n t } \left( I _ { 2 } , \ I _ { s u m } \right)
$$

其中： $l _ { t o t a l }$ 表示风格学习损失函数， $l _ { s t y l e }$ 表示风格特征损失函数，lcontent表示步态内容特征损失函数。 $I _ { 1 }$ 表示风格特征图， $I _ { \mathbf { \Omega } _ { 2 } }$ 表示步态内容特征图， $I _ { s u m }$ 表示最终虚拟样本生成图。 $\lvert \alpha , \beta \rvert$ 是调节参数，分别表示虚拟样本生成图里风格模型和内容特征的加权因子。令 $0 \leq \alpha \leq 1$ ， $0 \leq \beta \leq 1$ ，且 $\mathfrak { a } + \mathfrak { \beta } = 1$ 。 $\mathbf { \alpha } _ { \mathrm { ~ \mathfrak { ~ a ~ } ~ } }$ 从 $1 0 ^ { - 6 }$ 到 $1 0 ^ { - 1 }$ 取值，发现 $\mathbf {  { a } }$ 越大时，最终生成图像更接近风格图像，当 $\textbf { \em a }$ 较小时，最终生成图像更接近内容图像。所以， $\mathfrak { a }$ 取值不宜太多。当取 $\mathbf { a }$ $= 1 0 ^ { - 4 }$ ， $\beta = 1 - 1 0 ^ { - 4 }$ 时，最终生成图像更接近实际真实图像，可以更好地实现预期目标。

图像的步态内容特征损失函数为

$$
l _ { _ { c o n t e n t } } \left( \overrightarrow { I _ { 2 } } , \overrightarrow { I _ { _ { s u m } } } , l \right) = \frac { 1 } { 2 } \sum _ { i , j } \left( F _ { i j } ^ { l } - P _ { i j } ^ { l } \right) ^ { 2 }
$$

其中： $l$ 表示层数， $F$ ， $P$ 分别表示 $I _ { s u m }$ 和 $I _ { 2 }$ 在卷积神经网络中的响应。

风格特征图 $I _ { 1 }$ 在VGG19模型中每一层风格特征损失函数为

$$
E _ { l } \left( \vec { a } , \vec { x } \right) { = } \frac { 1 } { 4 N _ { l } ^ { 2 } M _ { l } ^ { 2 } } \left( G _ { i j } ^ { l } - A _ { i j } ^ { l } \right)
$$

其中： $\vec { a }$ 代表原始图片， $\vec { x }$ 代表最终生成的图片， $A ^ { l }$ 和 $G ^ { l }$ 分别表示原始图片和最终虚拟样本生成图在神经网络 $l$ 层的输出，$\begin{array} { r } { G ^ { l } = \sum _ { k } F _ { i k } ^ { l } * F _ { j k } ^ { l } } \end{array}$ 。

风格特征总损失为

$$
\begin{array} { r } { l _ { s t y l e } ( \overrightarrow { I _ { 1 } } , \overrightarrow { I _ { s u m } } ) = \sum _ { l = 0 } ^ { L } w _ { l } E _ { l } } \end{array}
$$

其中： $w _ { l }$ 为每一层的损失在整体损失中所占的比重。

# 2 本文算法实验结果和分析

实验将对GaitDataBase在0度、45度和90度方向的步态图片进行基于CNN和DLTL风格学习的步态虚拟样本生成方法实验探究。风格特征训练的大数据原始库将采用Yosemite上的1273张夏天图片和854张冬天图片，分类网络模型将采用基于VGG19 的深度卷积神经网络模型。实验的深度学习框架为Torch，编程语言环境为Lua5.1，GPU为GTX1060。

实验目的是训练Yosemite大数据原始集中的夏天与冬天两类风格特征，以此得到夏天和冬天特征模型。夏天与冬天特征训练过程中基于对偶学习的风格训练损失函数如图4所示。图中绿色代表夏天风格训练损失函数，紫色代表夏天真实样本风格函数，白色代表冬天风格训练损失函数。蓝色代表冬天真实样本风格函数。

从训练的损失函数可以看出图像的风格训练过程慢慢趋于稳定，在epoch $\scriptstyle = 4 0$ 时该模型训练过程基本处于收敛状态。同时也可以看出，在开始阶段训练出的风格与真实样本风格差异性较大，随着损失函数的反馈调节，从一个风格训练产生的生成风格样本与另一类真实样本风格越来越相似，最后达到了另一类判别器无法辨认的程度。

summer2winter_yosemite loss over time sso[ 5 thetwuatt 50 epoch

采用夏天、冬天特征模型基于TL风格学习进行环境背景风格的迁移工作。如图5和6所示。

从图5中可以看出原图冬天夏天的DLTL风格学习，步态人体背景环境色调变成冷色调，可以观察到冬天特征，地板人体有雪白的斑点，再使用夏天背景风格进行迁移，也可以观测到色调转成暖色调，地面地板有阳光的斑点。

图6中原图夏天冬天的DLTL风格学习，步态人体背景环境色调变成暖色调，可以观察到夏天特征，可以看到阳光色调；再迁移到冬天背景风格，也可以观测到色调转成冷色调，地面地板有雪白的斑点。

H#园勇昌房

从图7可以看出经过DLTL风格学习生成的步态虚拟样本虽然整体风格都改变了，但是图片中的步态人体的内容并没有改变。也就是说人体步态特征没有改变，行人的步态轮廓信息也没有丢失，只是拍摄步态识别实验的环境改变了，而且使得步态样本在色彩、色调、饱和度等方面在一定程度上都发生了变化。这样就达到了增加同类别样本的目的，扩充了小样本容量，不同的背景环境都给样本带来了多样性，为后续的工作降低了过拟合的概率。

![](images/5ad38a3f9ef108411f1cdfc0657cd9860c9cfa8b22c5db70d3805ad181f3398c.jpg)  
图70度、45度和90度方向不同风格的虚拟样本Fig.7Virtual samples of $0 ^ { \circ } , 4 5 ^ { \circ }$ and $9 0 ^ { \mathrm { { 0 } } }$ in different styles

实验的训练样本是30个人分别在0度方向生成的3张能量图。采用两种经典虚拟样本生成方法一一基于合成模板的虚拟步态样本合成方法和基于对抗网络的步态虚拟样本合成方法，每个人的虚拟能量图样本数量分别增加到1、2、3、4、5、6、7、8、9、10。这样增加虚拟样本个数的原因是步态能量图包含一个周期的图片集合，它的特征相当于二十几张普通图片。特征提取采用常用的基于GEI的步态特征提取法，分类器选用欧氏距离，降维采用PCA降维方法，PCA的贡献率选择 $9 5 \%$ 以上。测试样本采用的是这30个人在0度方向的真实采集到的150个测试样本。通过欧氏距离分类器进行模式匹配，多次测量欧氏距离差值求取平均值，得到图8中的步态识别率。

![](images/1e87f04d70ffdfc4c29fef72f07759cbed38214347af09aba15c251d70cafd65.jpg)  
图8两种虚拟能量图样本生成算法  
Fig.8Two sample generation algorithms for virtual energy maps

![](images/37c61437f40e3ccba582b6a1e79e1790ae67bd20f447a1e839de39825a4edafe.jpg)  
图9基于DLTL风格学习的步态虚拟样本生成方法   
Fig.9Gait virtual sample generation method based on DLTL style

learning

从图8可以看出两种虚拟能量图样本生成算法，当样本数量处在一定范围内能够提高步态识别的识别率。基于合成步态模板的虚拟样本生成方法呈现先增长再下降的趋势，这是因为它通过裁剪脚部的过多会破坏能量图轮廓的完整度。这也导致该方法不能大量生成虚拟样本。而基于对抗网络的虚拟样本生成方法随着虚拟样本数量的增加，识别率也出现了振荡上升的趋势。这说明基于对抗网络的步态虚拟样本鲁棒性差且不稳定，很难将它引入到步态识别系统的实际应用之中。这是因为它的随机噪声引起的不确定性，可能会给步态虚拟样本的构建带来了新的局限性。它虽然可以大量获得同类别步态虚拟样本，但是同时也引入了影响识别率的不确定性问题。

对30个人在0度的训练样本，共1000张原始RGB图片，采用基于CNN 和DLTL风格学习的虚拟样本生成方法，每个人的虚拟样本数量分别增加到5、10、15、20、25、30、35、40、45、50。特征提取采用常用的基于GEI的步态特征提取法，分类器选用欧氏距离。测试样本采用的是这30个人在0度方向的真实采集到的150个测试样本。通过欧氏距离分类器进行模式匹配，多次测量欧氏距离差值求取平均值，得到图9中的步态识别率。

从图9可以看出随着DLTL风格学习虚拟样本数量的增加，识别率有所增加。而且虚拟样本数量增加到一定的数量后，识别率有所提升。从图中趋势可以预测虚拟样本数量达到一定的数量后，识别率可能趋近饱和。通过实验验证DLTL风格学习不仅扩充了同类别的样本数量，还在一定程度上抑制步态识别小样本问题。

表1不同分类器的识别率  
Table 1Recognition rate of different classifiers   

<html><body><table><tr><td>虚拟样本生成</td><td>欧式距离</td><td>SVM</td><td>贝叶斯</td></tr><tr><td>合成步态模板</td><td>86.67%</td><td>86.00%</td><td>84.67%</td></tr><tr><td>对抗网络</td><td>88.67%</td><td>89.33%</td><td>88.00%</td></tr><tr><td>DLTL风格学习</td><td>90.67%</td><td>90.00%</td><td>91.33%</td></tr></table></body></html>

表1所示为利用不同分类器三种虚拟样本生成方法的步态的识别情况，测试样本采用的是30个人在0度方向的真实采集到的150个测试样本。从表1可以看出，DLTL风格学习的

方法优于其他两种方法。

表2三种步态虚拟样本生成算法对比  
Table 2Comparison of three algorithms for gait virtual sample generation   

<html><body><table><tr><td rowspan="2">虚拟样本生成</td><td rowspan="2">稳定性</td><td rowspan="2">是否失真</td><td rowspan="2">大量生成</td><td rowspan="2">提高真实样本 识别率</td></tr><tr><td></td></tr><tr><td>合成步态模板</td><td>香</td><td>是</td><td>否</td><td>先提高后降低</td></tr><tr><td>对抗网络</td><td>否</td><td>香</td><td>是</td><td>提高</td></tr><tr><td>DLTL风格学习</td><td>是</td><td>否</td><td>是</td><td>提高</td></tr></table></body></html>

表2是三种步态虚拟样本生成算法的实验对比，从表中可以看出基于CNN 和DLTL风格学习的步态虚拟样本生成在三种算法中是最优的，该方法不仅稳定提高了真实样本的识别率，还能够在一定程度上解决步态识别的小样本问题。

# 3 结束语

本文提出一种基于深度卷积神经网络和DLTL风格学习的步态虚拟样本生成方法，该方法可较好改善步态识别小样本问题，优于现有的步态虚拟样本生成方法。实验结果表明，该方法能生成大量虚拟样本，且具有良好的鲁棒性。实验发现采用基于CNN 和DLTL风格学习的步态虚拟样本方法能够提高步态识别的识别率。下一步研究将提取更复杂的风格特征模型，提升步态内容特征图对风格特征模型迁移风格学习的效率，高效获得更多风格的步态虚拟样本。

# 参考文献：

[1]Iwama H,Muramatsu D,Makihara Y,et al. Gait-based person-verification system for forensics [C]//Proc of the 5th IEEE International Conference on Biometrics:Theory,Applications and Systems.Washington DC:IEEE Computer Society,2012:113-120.   
[2]Tang Jin,Luo Jian,Tjahjadi T.Robust arbitrary-view gait recognition based on 3d partial similarity matching [J].IEEE Trans on Image Processing,2017, 26 (1): 7-22.   
[3]Luo Jian,Tang Jin,Tjahjadi T,et al.Robust arbitrary view gait recognition based on parametric 3D human body reconstruction and virtual posture synthesis [J].Pattern Recognition,2016 (60): 361-377.   
[4]Bouchrika I, Goffredo M,Carter J,et al. On using gait in forensic biometrics [J].Journal of Forensic Sciences,2011,56 (4): 882-889.   
[5]Han Ju,Bhanu B.Individual recognition using gait energy image[J].IEEE Trans on Pattern Analysis and Machine Intelligence,20o6,28(2):316-322.   
[6]Lam TH.W,Lee R S T.A new representation for human gait recognition: Motion silhouettes image (MSI) [M]//Advances in Biometrics.Berlin: Springer,2006:612-618.   
[7]Lam THW, Cheung KH,Liu JNK.Gait flow image:a silhouette-based gait representation for human identification [J]. Pattern Recognition, 2011, 44 (4): 973-987.   
[8]Wang Chen, Zhang Junping, Wang Liang,et al. Human identification using temporal information preserving gait template [J]. IEEE Trans on Pattern

Analysis& Machine Intelligence,2012,34(11):2164-2176.

[9]Chen Changhong,Liang Jimin, Zhao Heng,et al. Frame difference energy image for gait recognition with incomplete silhouettes [J].Patrn Recognition Letters,2009,30(11): 977-984.

[10] Sivapalan S, Chen D, Denman S,et al. Gait energy volumes and frontal gait recognition using depth images [C]//Proc of International Joint Conference on Biometrics.Piscataway,NJ: IEEE Press,2011: 1-6.   
[11]Hofmann M,Bachmann S,RigollG.2.5Dgait biometrics usingthedepth gradient histogram energy image [C]// Proc of the 5th IEEE International Conference on Biometrics: Theory, Applications and Systems. Washington DC: IEEE Computer Society,2012: 399-403.   
[12] Tang Jin,Luo Jian,Tjahjadi T,etal.2.5Dmulti-view gait recognitionbased on point cloud registration [J].Sensors,2014,14 (4): 6124-6143.   
[13] Du Yong，Wang Yu. Generating virtual training samples for sparse representation of face images and face recognition [J]. Journal of Modern Optics,2016,63(6): 536-544.   
[14] LiD C,Wu C S,TsaiTI,etal. Using mega-trend-diffusionand artificial samples in small data set learning for early flexible manufacturing system scheduling knowledge[J].ComputersandOperationsResearch,207,34 (4): 966-982.   
[15]LiD C,Lin Yaosan.Using virtual sample generation to build up management knowledge in the early manufacturing stages [J]. European Journal of Operational Research,2006,175(1): 413-434.   
[16] Huang Chongfu, Moraga C.A diffusion-neural-network for learning from small samples [J].International Journal of Approximate Reasoning,2004, 35 (2): 137-161.   
[17] Li D C,Wen I H.A genetic algorithm-based virtual sample generation technique to improve small data set learning [J]. Neurocomputing, 2014 (143): 222-230.   
[18] Chen Zhongsheng, Zhu Bao,He Yanlin,et al.A PSO based virtual sample generation method for small sample sets: Applications to regression datasets [J].EngineeringApplicationsofArtificial Intelligence,2017(59):236-243.   
[19] Gong Hongfei, Chen Zhongsheng, Zhu Qunxiong,et al. A Monte Carlo and PSO based virtual sample generation method for enhancing the energy prediction and energy optimization on small data problem: an empirical study of petrochemical industries [J].Applied Energy,2017,197: 405-415.   
[20]HanJu,hanuB.ndividualrecognitionusinggaitenergyimage[J].IEE Trans on Pattern Analysis and Machine Intelligence,20o6,28 (2):316-322.   
[21]王坤峰，苟超，段艳杰，等．生成式对抗网络GAN 的研究进展与展望 [J]．自动化学报,2017,43(3):321-332.(Wang Kunfeng,Gou Chao,Duan Yanjie,et al. Generative adversarial networks:the state ofthe art and beyond [J].Acta Automatica Sinca,2017,43 (3): 321-332.)   
[22] Simonyan K, Zisserman A. Very deep convolutional networks for largeScale image recognition   
[23][EB/OL].(2015-04-10)[2015-07-19].http://arxiv.org/pdf/1409.1556v6 pdf.

[24]周俊宇，赵艳明．卷积神经网络在图像分类和目标检测应用综述[J]. 计算机工程与应用,2017,53(13):34-41.(

[25] Zhou Junyu, Zhao Yanming.Application of convolution neural network in image classification and object detection [J].Computer Engineering and Applications,2017,53(13):34-41.)

[26]王晨琛，王亚琳，葛中芹等．基于神经网络的中国水墨画风格提取[J].图学学报，2017,38(5):754-759.(Wang Chenchen，Wang Yalin,Ge

Zhongqin,et al. Convolutional neural network-based chinese ink-painting artistic style extraction [J].Journal of Graphics,2017,38(5):754-759.)

[27]张博，史忠植，赵晓非，等．一种跨领域典型相关性分析的迁移学习方 法[J].计算机学报,2015,38(7):1326-1336.(Zhao Bo,Shi Zhongzhi, Zhao Xiaofei,et al.A transfer learning based on canonical correlation analysis across different domains [J].Chinese Journal of Computers,2015, 38(7):1326-1336.)