# 非对称周期推理循环渐进的人脸修复算法研究

李雅倩，张旭曜，李岐龙(燕山大学 电气工程学院，河北 秦皇岛 066004)

摘要：针对生成对抗网络中修复网络无法兼顾图像的全局一致性和局部一致性，且计算负载较大的问题，在非对称U-Net网络架构的基础上引入渐进修复的思想。首先，提出了非对称周期特征推理模块，增加图像修复内容与周围已知像素之间的关联性，提高了修复图像的全局一致性表现。其次，提出新型的U-Net结构生成器网络，避免了编码器中的未知像素进入解码器，从而破坏解码器中特征的问题。最后，引入了感知损失和风格损失，进而提高了网络在主观评价下的修复效果。在人脸图像数据集上的实验表明，该文算法在主观视觉效果和客观指标上都有显著的提高。

关键词：生成对抗网络；渐进式修复；非对称周期特征推理；图像修复 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.01.0009

Asymmetric periodic inference cyclic progressive face completion algorithm research

Li Yaqian, Zhang Xuyao†,Li Qilong (Yanshan University,School of Electrical Engineering,Qinhuangdao Hebei O66004,China)

Abstract:Toaddress theproblem thatthe inpainting network ingenerativeadversarialnetworkscannottakeintoaccountthe global consistencyand local consistencyof images and has alarge computational load,this paper introduces the idea of incremental inpainting based on the asymmetric U-Net network architecture.Firstly,this paper proposed an asymmetric periodic feature inference module to increase thecorrlationbetween image ipainting contentandsurrounding known pixels, which improves the global consistency performance of restored images.Secondly,this paper presented a novel U-Net structured generator network to avoid theproblem ofunknown pixels inthe encoder entering the decoderand thus corrupting thefeatures in the decoder.Finaly,it introduced perceptual loss and style loss,which in turn improve theinpainting effectivenessof the network under subjective evaluation.Experiments on the face image dataset show that the algorithm in this paper shows significant improvements in both subjective visual effects and objective metrics.

Key words: generative adversarialnetwork; gradual inpainting; asymmetric periodic feature inference; image inpainting

# 0 引言

图像作为人们日常生活中一个重要的信息载体，当其产生破损、老化或者部分信息丢失的时候很容易使人们对信息产生误解。由于现实中的图像是在非约束条件下获得的，所以获得的图像可能会出现遮挡、污渍、破损等情况，当图像中出现上述情况的时候会明显对图像的识别、检测与分割产生负面影响。因此图像修复技术是一种被现实迫切需要的技术，特别是在如今图像识别、分割等任务已经进入日常使用环境下的今天。

传统的工匠修复照片通常首先对图像的线条或者物体轮廓进行修补，之后再对图像的颜色和纹理进行修复。Li等人[1]首次将GAN应用在人脸修复领域，借鉴工匠修复图片先轮廓后纹理的思路，在鉴别器中同时引入全局和局部损失函数，生成的图片不仅在语义上有效，视觉上也比较和谐。由此图像修复技术发展出了一类将修复任务分级的修复方法。Nazeri等人[2]提出了一种线条-颜色两步修复算法，先用一个PatchGAN[3]进行图像的线条修复，再用另一个PatchGAN进行颜色修复，这样两个GAN串联的方式可以将修复网络分级，得到精细度更好的修复图像。Xiong等人[4提出应明确区分结构推断和内容修复。所提出的模型通过精确的预测边界来指导图像修复，边界修复模块能够在待修复区域推断出合理的结构，图像修复模块再根据预测边界来生成图像内容，同时将粗网络-细网络修复[5]的方法融合到了每一个GAN 中还有一种类似的方法是基于分层VQ-VAE的multiple-solution图像修复方法[，这种方法的模型将结构和纹理分开提出为结构特征的分布学习一个条件自回归网络，对于纹理生成,提出一个结构注意力模块，用来捕捉结构特征的远距离相关性，改善了结构的一致性和纹理的真实性[7]。Li等人设计了一种线条修复模块将线条修复过程简化，从而可以使用一个GAN进行线条-颜色修复的方法。通过设计可视化结构重构(visual structurereconstruction,VSR)模块l8可在生成器的初始层中进行线条修复，在生成器的主干通道中进行颜色修复。将线条修复作为一个模块嵌入到网络中可以有效的避免分级修复中多个GAN串联造成的计算负载大和不易收敛的问题。随后Li等人[9]认为线条-颜色分级不是图像修复的最优解，因此设计了周期特征推理(recurrentfeaturereasoning,RFR)模块。它采取修复区域分级的方法，逐步向内修复。RFR模块可以控制每一步修复的区域，然后控制下一步修复采用上次修复区域的内容作为推理依据进行下一步的填充，通过在各层推理特征图中设计知识一致性注意力(knowledgeconsistentattention,KCA)[9]机制来增强各层推理的相关性。

上述工作中，大部分模型虽然获得了更好的图像修复效果，但也随之增加了计算负担，并且没有解决多个GAN 串联不易收敛的问题。如何在不增加训练难度的同时引入分级修复的思想，针对修复任务设计出一种即插即用的特征推理模块是一种简单有效的解决思路。RFR模块为渐进修复方法提供了一种模块化设计网络的新思路，受启发于RFR的设计理念，本文将RFR模块进行重构并结合非对称U-Net框架，设计了非对称周期特征推理模块，从而进一步提升模块的特征推理能力。本文的主要贡献如下：

(1)本文针对图像修复网络无法兼顾图像的全局一致性和局部一致性，且需要的计算负载较大的问题。比较现有方法后发现RFR模块在降低编码器部分的未知像素，提高网络的解码有良好表现。将RFR模块进行重构改进成非对称周期特征模块应用U-Net结构之中，提出了非对称周期特征推理模块。

(2)本文提出了一种渐进修复[10]的人脸修复网络。引入PatchGAN训练修复网络，使用门控卷积层作为U-Net结构的生成器的编码器中的卷积函数，U-Net底层改为双通道空洞卷积的方式，结合感知损失和风格损失，获得了良好的人脸修复效果。

(3)实验在CelebA人脸数据集上采用了随机mask作为训练和测试数据，并且与Edge-Connection[2]，PConv[11],GatedConv[12]，GFP-GAN[13]和LaMa[14]现有先进的修复模型进行对比，结果表明本文算法在提升主观效果和客观指标上的有效性。

# 1 算法原理

# 1.1循环修复网络框架

周期特征推理模块启发于渐进修复思想以及部分卷积中的修复区域定位机制，通过对mask通道的更新进行每一步修复区域的定位。周期推理模块分为四个部分：区域定位(area identification)[15]特征推理(feature reasoning)[16]特征融合(featuremerging)知识一致性注意力(knowledgeconsistentattention)，模块结构如图1所示。

![](images/acc7f490853d5641e646b3d80be2766b890ab4e56b09ab6253c4e8364f2720e2.jpg)  
图1周期推理模块

和现在流行的图像修复方法不同的是，RFR模型中并没有使用GAN，网络总体上是一个CNN结构。在本文设计非对称周期特征推理模块中，将GAN优良的无监督学习能力引入，设计PatchGAN结构，采用基于Wasserstein距离[17]设计的马尔可夫判别器训练嵌入了RFR模块的U-Net生成器。区域定位采用部分卷积的mask[18]更新机制定位每一个循环体中修复区域的大小和位置。由于基于普通卷积的卷积方式不适合用于图像空洞填充，因为空间共享的卷积过滤器将所有输入像素或特征视为相同的有效特征；会导致诸如颜色差异、模糊和孔周围明显的边缘反映等视觉假象，所以本文采用门控卷积[12]作为特征推理模块的卷积核使之提高对修复内容的特征推理能力，构建一个非对称的结构。本文提出的非对称周期特征推理模块框架如图2所示。

采用上述非对称特征推理模块结合U-Net网络结构的跳跃连接[19]机制提高解码器的图像生成能力，从而提高图像的视觉表现，采用在人脸数据集上预训练的VGG-Net构建感知损失和风格损失可以提升生成图在图像视觉感知和风格上的表现。设计的非对称周期推理循环渐进的人脸修复网络框架如图3所示。其中循环渐进修复网络首先将RFR模块嵌入在输入层后面使得进入修复网络的编码器的时候图像已经没有未知区域，随后将不含未知区域的特征图送入U-Net网络中，此网络类似RNN，特征图第一次输入到RFR模块里输出的结果又会第二次重新输入到RFR模块里。第二次则在第一次填充的特征图的基础上进一步填充或预测出更合理的值。这样反复几个循环后才会进入到下一步的特征融合环节。这种循环机制带来的好处是能反复利用RFR模块中的特征，使模型达到轻便化的同时预测出更合理的特征参数，进一步提升模块特征推理能力。为了提高图像在高层特征图中提取语义的能力，将U-Net的底层设计为并联空洞卷积结构。该算法使用门控卷积层作为U-Net结构生成器中编码器的卷积函数U-Net底层改为双通道空洞卷积的方式以防止图像空间结构在生成器的底层被破坏。

![](images/c8053d2601bfdb2f57cd108593d93d79f82f87f88fbff34e14338f9e22cb8090.jpg)  
  
图2非对称周期特征推理

![](images/7243b50df1c311f20c7fd0c490fc2085aca490edfaca44d262a93fbcfa035d0f.jpg)  
Fig.1Periodic reasoning module   
Fig.2Asymmetric periodic feature inference   
图3非对称周期推理循环渐进的人脸修复模型 Fig.3Asymmetric cycle inference for cyclic progressive face restoration model

# 1.2 马尔可夫判别器

普通的GAN 思想是采用一个判别器来判定输入是来自真实数据分布 $p _ { r }$ 还是生成数据分布 $p _ { g }$ 。与普通GAN的判别器不同，马尔可夫判别器设计为全卷积结构，输出为一个$N { \times } N$ 的矩阵 $\boldsymbol { \cal X }$ ,其中矩阵 $\boldsymbol { \cal X }$ 的元素 $X _ { i , j }$ 代表在位置 $( i , j )$ 处对应到原图一个 $M \times M$ 大小的感受野内图像块的真实度，最后将矩阵所有的值取平均得到图像的真实度。网络训练采用基于Wasserstein距离的衡量指标，保证可以收敛。

采用马尔可夫判别器相对于普通判别器来说有以下优点：

(1)马尔可夫判别器可以关注图像块的修复结果，能够显著提升图像的细节表现。

(2)通过关注输入的不同区域，可以通过学习考虑到图中不同区域对于识别该图是否属于真实图像的贡献度，从而可以有针对性的考虑贡献大的区域。例如在针对人脸进行修复的时候，判别器重点关注人脸区域，减少对背景区域的关注。

为了提高PatchGAN的收敛速度，同时提高修复的多样性，参考了Miyato等人的研究，在PatchGAN中引入谱范数正则化。WGAN能够收敛所需要的条件是网络满足Lipschitz约束[20]。为了满足这个条件，原始WGAN采用了梯度裁剪的方式人为的将所有卷积层的权重约束到一个范围内，最后造成了梯度分布不均匀的问题。随后提出的WGAN-G[2I采用梯度惩罚的正则化方式缓解了这个问题。后来Miyato等人提出了采用谱范数正则化的方式，进而在不对梯度加以干扰的条件下使得网络满足1-Lipschitz约束。本文所采用的马尔可夫判别器中采用谱范数正则化进行训练，从而提高判别器的效果。

# 1.3感知损失与风格损失

针对人脸修复任务，本文引进了感知损失与风格损失[22]。本文算法采用在人脸数据集上预训练的人脸识别网络作为监督，对修复图和原图进行感知差别的计算和风格保持的计算。其中修复网络的输出和原图的尺寸为 $2 5 6 \times 2 5 6$ ，而VGG16网络的输入为 $2 2 4 \times 2 2 4$ 的图像，因此在训练时将修复网络的输出图与原图在计算损失时尺寸变为 $2 2 4 \times 2 2 4$ 。所用的VGG16网络结构如图4所示。

![](images/a1d9716775d0c00d19f9eebccec5c13ad2ceba845d1c585f06b31df6ae5eb62b.jpg)  
图4感知损失与风格损失计算  
Fig.4Perceived loss and style loss calculation

感知损失的计算在VGG16网络的relu3_3层计算，计算方式如式(1)所示。

$$
{ l } _ { \mathrm { p e r c e p t u a l } } ^ { \phi , j } = \frac { 1 } { C _ { j } H _ { j } W _ { j } } \bigl \| \phi _ { j } \left( 0 \right) - \phi _ { j } \left( g \right) \bigr \| _ { 2 } ^ { 2 } ,
$$

其中， $\phi$ 代表VGG网络， $j$ 代表使用VGG网络的第 $j$ 层的特征图作为输出， $C _ { j }$ ， $\boldsymbol { H } _ { j }$ ， $W _ { j }$ 分别代表VGG网络的第 $j$ 层输出的特征图的通道数、高度和宽度。

采用VGG16作为监督网络，识别输入两个图在特征图层面的像素级差别。与直接在图像上进行像素级差别计算相比，特征图可以表示图像的高层语义特征，因此在特征图上进行像素级的计算可以表示两张图之间的感知差别。

风格损失计算方式如式(2)及(3)所示。

$$
G _ { j } ^ { \phi } \left( x \right) _ { c , c ^ { \prime } } = \frac { 1 } { C _ { j } H _ { j } W _ { j } } \sum _ { h = 1 } ^ { H _ { j } } \sum _ { w = 1 } ^ { W _ { j } } \phi _ { j } \left( x \right) _ { h , w , c } \phi _ { j } \left( x \right) _ { h , w , c ^ { \prime } } ,
$$

$$
l _ { \mathrm { s t y l e } } ^ { \phi , j } \left( o , g \right) = \left\| G _ { j } ^ { \phi } \left( o \right) - G _ { j } ^ { \phi } \left( g \right) \right\| _ { F } ^ { 2 } ,
$$

其中， $\phi$ 代表VGG 网络， $j$ 代表使用VGG网络的第 $j$ 层的特征图作为输出， $C _ { j }$ ， $\boldsymbol { H } _ { j }$ ， $W _ { j }$ 分别代表VGG 网络的第 $j$ 层输出的特征图的通道数、高度和宽度， $G$ 代表计算格拉姆矩阵。

# 1.4总体损失

训练网络总共包含四部分的损失，即PatchGAN损失、感知损失、风格损失及L1重构损失。定义网络的输入图片为 $I _ { \mathrm { i n } } = I _ { \mathrm { g l } } \odot M$ ，式中 $M$ 是掩码图像，在 $M$ 中像素点为0的区域为未知区域，像素点为1的区域为已知区域，输入的破损图像是由原始图像和掩码图像进行逐像素的叠加得到。输入图像经过循环渐进人脸修复网络的修复，输出为 $O = I _ { \mathrm { g t } } \odot M + G \left( I , M \right) \odot \left( 1 - M \right)$ ，式中 $\sigma$ 为网络的生成器，输入图片未被遮挡的原图为 $I _ { \mathrm { g l } }$ ，网络的总损失函数如下式(4)所示。

$$
\begin{array} { r } { L = \lambda _ { \mathrm { a d v } } L _ { \mathrm { a d v } } + \lambda _ { \mathrm { p e r } } L _ { \mathrm { p e r } } + \lambda _ { \mathrm { s t y l e } } L _ { \mathrm { s t y l e } } + \lambda _ { 1 1 } L _ { 1 1 } , } \end{array}
$$

其中， $L _ { \mathrm { a d v } }$ 代表生成对抗网络损失[23]， $\boldsymbol { L } _ { \mathrm { p e r } }$ 代表感知损失， $L _ { \mathrm { s t y l e } }$ 代表风格损失， $L _ { \mathrm { 1 1 } }$ 代表L1重构损失。

本文网络的优化方法使用Adam优化器，针对总体损失进行优化。首先对网络进行前向计算，得到输出的修复图像，随后根据式(4)计算网络的损失，采用Adam对损失进行优化。所计算的权重如下所示。

$$
w = w - \frac { \eta m _ { t } } { \sqrt { n _ { t } + \varepsilon } } ,
$$

上式中的一阶动量 $m _ { \iota }$ 和二阶动量 $n _ { t }$ 计算由式(6)和(7)给出：

$$
m _ { t } = \frac { m _ { t } } { 1 - \gamma _ { 1 } ^ { t } } = \frac { \gamma _ { 1 } ^ { t } m _ { t - 1 } + \left( 1 - \gamma _ { 1 } ^ { t } \right) } { 1 - \gamma _ { 1 } ^ { t } } \frac { \partial L } { \partial w } ,
$$

$$
n _ { t } = \frac { n _ { t } } { 1 - \gamma _ { 2 } ^ { t } } = \frac { \gamma _ { 2 } ^ { t } m _ { t - 1 } + \left( 1 - \gamma _ { 2 } ^ { t } \right) } { 1 - \gamma _ { 2 } ^ { t } } \frac { \partial L } { \partial w } ,
$$

其中，γ、和 $\varepsilon$ 都是优化算法的参数， $\textbf { \em L }$ 是网络的总体损失。梯度反传过程首先通过网络的损失对权重的梯度计算出一阶动量和二阶动量的无偏估计，代入式(5)即可更新权重。

# 2 修复实验结果

# 2.1深度学习环境配置

本算法的实验代码采用PyTorch 框架实现。Pytorch 是Facebook公司开发的动态计算流图的深度学习框架。PyTorch框架提供了根据计算图求各节点导数的功能，可以动态的建立计算流图，能够更加方便的实现梯度的反向传播。同时集成了大量的深度学习常用函数，方便网络搭建和实验。

本文算法的实验平台的操作系统是64位的Linux 内核系统，版本是Ubuntu18.04LTS，PyTorch 版本为1.2.0,OpenCV为4.4.0.46，numpy为1.16.5，scipy为1.1.0，scikit-image为0.13.1。显卡型号为Nvidia1080Ti8G。

# 2.2数据集介绍与超参数配置

CelebA[24]是香港中文大学收集制作的大尺度人脸数据集，数据集中一共包含202599张人脸图片。由于未处理的数据集中图像尺寸不一，人脸位置不一，不方便进行学习，因此首先采用作者给出的人脸bbox回归框标注文件进行预处理，得到202599张对齐后的图片，随后进行尺寸变换为 $2 5 6 \times$ 256的图片，然后在图片中随机抽取1000张作为测试集，其余图片均为训练集。

本文的实验使用Adam优化器，训练时学习率为 $1 \times 1 0 ^ { - 4 }$ ，模型调整优化阶段(fine-tuning)学习率为 $1 \times 1 0 ^ { - 5 }$ ，模型的输入批次为6,训练450000 次循环。超参数设置为 $\lambda _ { a d \nu } = \lambda _ { p e r } = 0 . 0 5$ ，$\lambda _ { s t y l e } = 1 2 0$ ， $\lambda _ { l _ { 1 } } = 1$ 。

# 2.3实验结果与评价指标

本文算法选取的对比模型都是在人脸数据上有优秀表现的模型。横向对比的模型有Edge-Connection[2]，PConv[1l],GatedConv[12]，GFP-GAN[13]和LaMa[14]。本文采用PConv中所提出的不规则遮挡(irregularmask)数据集作为训练和测试的mask，该数据集提供了不同遮挡比例和不同形状的随机遮挡，可以模拟现实世界中遮挡的随机性，采用该数据集作为测试mask对于横向对比而言更有客观性，不同比率的mask遮挡如图5所示，待修复图片如图6所示。

各算法在人脸数据集上的主观表现如图7所示。观察可知，PConv、GatedConv、Edge-Connection、GFP-GAN、LaMa和本文算法均对还原图像的全局语义有较好的效果，但本文算法在还原图像的细节结构有更加突出的表现，前五种算法无法准确的全部还原图像中的一些细节结构。

![](images/142ddf148478f7684af14f272be3248285830fa36eac650730767b5adb179944.jpg)  
图5不同mask比率示意图

![](images/a9acf06e97ebdac51f60f25d5c737f4f0f782e1db5c1448584bcf7e19ac7d7d6.jpg)  
Fig.5Diagram of different mask ratios   
图6不同比例随机遮挡下的待修复图像

![](images/38828b46de36e91efeaa559affe60cfc409ae91d531ddc80fe30cab6abfc6b5a.jpg)  
Fig.6Images to be restored at different scales with random masking   
图7不同模型主观修复对比  
Fig.7Comparison of subjective inpainting of different models

为了探索本文算法所提出的非对称周期特征推理模块和采用PatchGAN训练的网络框架的有效性，设计了与RFR进行对比的实验，对比结果如表1所示。

表1mask 在(0.1,0.2]时与RFR对比结果  
Tab.1Mask compared the results with the original paper at (O.1,0.2]   
表4mask在(0.5.0.6]时不同模型的指标  

<html><body><table><tr><td>模型</td><td>PSNR</td><td>SSIM</td><td>L1</td></tr><tr><td>RFR-Net</td><td>33.56</td><td>0.981</td><td>0.0075</td></tr><tr><td>本文算法</td><td>33.61</td><td>0.983</td><td>0.0071</td></tr></table></body></html>

不规则遮挡数据集将不同比例的 mask 进行了分类，其中每一个比例含有2000 张随机mask图像，为了测试模拟本文算法在不同 mask 比例下的修复效果，选取(0.1,0.2]、(0.3.0.4]以及(0.5.0.6]的三个不同比例的mask数据集作为测试。不同的mask比例下本文算法与其他算法的客观指标横向对比结果如表2\~4所示。在mask比率为(0.1,0.2]时不同模型的修复效果对比如表2所示。

Tab.2Mask at (O.1,O.2] different model indicators   

<html><body><table><tr><td>模型</td><td>PSNR</td><td>SSIM</td><td>L1</td></tr><tr><td>PConv</td><td>32.77</td><td>0.977</td><td>0.0083</td></tr><tr><td>GatedConv</td><td>32.56</td><td>0.973</td><td>0.0088</td></tr><tr><td>Edge-Connection</td><td>32.48</td><td>0.975</td><td>0.0088</td></tr><tr><td>GFP-GAN</td><td>32.86</td><td>0.979</td><td>0.0082</td></tr><tr><td>LaMa</td><td>33.17</td><td>0.980</td><td>0.0078</td></tr><tr><td>本文算法</td><td>33.61</td><td>0.983</td><td>0.0071</td></tr></table></body></html>

在mask比率为(0.3,0.4]时不同模型的修复效果对比如表3所示。

Tab.3Mask at (O.3,0.4] different model indicators   

<html><body><table><tr><td>模型</td><td>PSNR</td><td>SSIM</td><td>L1</td></tr><tr><td>PConv</td><td>26.94</td><td>0.922</td><td>0.0236</td></tr><tr><td>GatedConv</td><td>26.72</td><td>0.914</td><td>0.0245</td></tr><tr><td>Edge-Connection</td><td>26.62</td><td>0.915</td><td>0.0247</td></tr><tr><td>GFP-GAN</td><td>27.04</td><td>0.920</td><td>0.0235</td></tr><tr><td>LaMa</td><td>27.15</td><td>0.926</td><td>0.0231</td></tr><tr><td>本文算法</td><td>27.78</td><td>0.935</td><td>0.0211</td></tr></table></body></html>

在mask比率为(0.5,0.6]时不同模型的修复效果对比如表4所示。

表3mask在(0.3,0.4]时不同模型的指标  

<html><body><table><tr><td>模型</td><td>PSNR</td><td>SSIM</td><td>L1</td></tr><tr><td>PConv</td><td>22.14</td><td>0.791</td><td>0.0524</td></tr><tr><td>GatedConv</td><td>21.47</td><td>0.767</td><td>0.0561</td></tr><tr><td>Edge-Connection</td><td>21.49</td><td>0.759</td><td>0.0572</td></tr><tr><td>GFP-GAN</td><td>21.62</td><td>0.792</td><td>0.0506</td></tr><tr><td>LaMa</td><td>22.14</td><td>0.797</td><td>0.0498</td></tr><tr><td>本文算法</td><td>22.91</td><td>0.823</td><td>0.0468</td></tr></table></body></html>

表2\~4展现了在不同mask遮挡比例下本文算法的客观有效性。客观指标对比采用三种不同的指标，分别是峰值信噪比(PSNR)、结构相似性(SSIM)以及L1误差。其中PSNR与SSIM指标是越大越好，L1误差是越小越好，L1误差是修复图像与原图之间的L1范数。在上述三种客观指标的对比中，本文算法在不同数据集上的实验结果显示出了本文算法的优越性。

实验表明本章算法相比原算法有一定程度的提高。在实验中发现非周期特征推理的迭代次数对修复结果有影响作用，通过设计不同迭代次数的实验得到在迭代次数为6次的时候网络的修复性能表现最好。实验如表5所示。

Tab.4Mask at(O.5,0.6] different model indicators   
表5周期推理模块迭代次数的影响  
Tab.5Influence of iteration number of periodic reasoning module   

<html><body><table><tr><td>迭代次数</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>PSNR</td><td>27.32</td><td>27.70</td><td>27.78</td><td>27.72</td><td>27.56</td></tr><tr><td>SSIM</td><td>0.914</td><td>0.928</td><td>0.935</td><td>0.931</td><td>0.917</td></tr></table></body></html>

上述的实验证明了本文创新的有效性，图8展示了本文算法在不同比例遮挡下的修复表现，图9展示了本文算法在同一图像上不同比例遮挡下的表现。从主观效果上来看，本文算法在较大范围的任意遮挡上获得了比较好的修复效果。

# 3 结束语

针对修复网络无法兼顾图像的全局一致性和局部一致性，且需要的计算负载较大的问题，本文提出了非对称周期特征推理模块，提高了图像修复内容与周围已知像素之间的关联性。首先引入渐进修复的思想，将一种渐进修复模块(RFR)结合非对称网络的构架，对渐进修复模块进行重构；其次采用加入了非对称RFR模块的U-Net框架，引入PatchGAN训练修复网络，使用门控卷积层作为U-Net结构的生成器的编码器中的卷积函数，U-Net底层改为双通道空洞卷积的方式防止图像空间结构在生成器的底层被破坏；最后结合感知损失和风格损失，获得了良好的人脸修复效果。实验结果表明，本文算法分别相比于现有一些算法，在信噪比(PSRN)、结构相似性(SSIM)和L1 误差各项客观指标以及主观视觉上都有显著的提高。

![](images/77b7cb1e9752900e5974a9b7e29fc637f2d0d4ae9b33d38b26262949f6276509.jpg)  
图8不同mask 比例下的修复效果

![](images/b2ede42620c7eabbe35ea35e626e10efa9725fca9a5ce34fcfb25a9e0af6e0e0.jpg)  
Fig.8Repair effect under different mask ratio   
图9同一图像不同mask 比例下的修复效果Fig.9The repair effect of the same image withdifferent mask proportions

# 参考文献：

[1]Li Yijun,Liu Sifei, Yang Jimei,et al. Generative face completion [C]/ Proceedings of the IEEE conference on computer vision and pattern recognition.IEEE,2017:3911-3919.   
[2] Nazeri K,Ng E,Joseph T,et al.Edgeconnect:Generative image inpainting with adversarial edge learning[J].arXiv preprint arXiv:1901. 00212,2019.   
[3]杜雪梅.基于GAN的图像补全算法研究[D].成都：电子科技大学, 2021.(Du Xuemei.Research on image completion algorithm based on GAN [D].ChengDu: University of Electronic Science and Technology of China,2021.)   
[4]Xiong Wei,Yu Jiahui,Lin Zhe,et al.Foreground-aware image inpainting [C]//Proceedings of the IEEE/CVF Conference on Computer Vision and

[5]Moskalenko A,Erofeev M, Vatolin D.Deep Two-Stage High-Resolution Image Inpainting[J].CEUR Workshop Proceedings,2020,2744.

[6]Peng Jialun,Liu Dong,Xu Songcen,et al. Generating Diverse Structure for Image Inpainting With Hierarchical VQ-VAE[C]/ Proceedings ofthe IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021: 10775-10784.   
[7]Liao Liang,Xiao Jing,Wang Zheng,et al. Image Inpainting Guided by Coherence Priors of Semantics and Textures [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021: 6539-6548.   
[8]Li Jingyuan，He Fengxiang，Zhang Lefei,et al.Progressive reconstruction of visual structure for image inpainting [C]// Proceedings of the IEEE/CVF International Conference on Computer Vision. 2019: 5962-5971.   
[9]Li Jingyuan，Wang Ning，Zhang Lefei，et al.Recurrent Feature Reasoning for Image Inpainting [Cl// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattrn Recognition. 2020: 7760- 7768.   
[10] Wang Tengfei， Ouyang Hao,Chen Qifeng. Image Inpainting with External-internalLearningandMonochromicBottleneck[C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021: 5120-5129.   
[11] Liu Guilin,RedaFA,Shih KJ,et al. Image inpainting forirrgularoles using partial convolutions [C]// Proceedings of the European Conference on Computer Vision (ECCV).Springer,2018: 85-100.   
[12] Yu Jiahui,Lin Zhe, Yang Jimei,etal. Free-form image inpainting with gated convolution [C]// Proceedings of the IEEE/CVF International Conference on Computer Vision. 2019: 4471-4480.   
[13] Wang Xintao,Li Yu,Zhang Honglun,etal. Towards real-world blind face restoration with generative facial prior [Cl// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021: 9168-9178.   
[14] Suvorov R,Logacheva E,Mashikhin A,et al. Resolution-robust Large Mask Inpainting with Fourier Convolutions [C]// Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision. 2022: 2149-2159.   
[15] Gong Yunpeng. A general multi-modal data learning method for Person Re-identification [J].arXiv preprint arXiv: 2101.08533,2021.   
[16] Ai Mingxi,Xie Yongfang,Tang Zhaohui,et al. Deep learning featurebased setpoint generation and optimal control for flotation processes [J]. Information Sciences,2021,578: 644-658.   
[17] Jam J,Kendrick C,Drouard V,et al. Symmetric Skip Connection Wasserstein GAN for High-resolution Facial Image Inpainting [Cl//16th International Conference on Computer Vision Theory and Applications. 2021.   
[18] 曾文雯，杨阳，钟小品．基于改进 Mask R-CNN 的在架图书书脊图 像实例分割方法[J].计算机应用研究，2021，38(11):3456- $3 4 5 9 + 3 5 0 5$ .(Zeng Wenwen, Yang Yang, Zong Xiaopin. An improved Mask R-CNN based method for segmentation of on-shelf book spine image instances [J]. Computer Applications Research,2021,38(11): $3 4 5 6 - 3 4 5 9 + 3 5 0 5 .$ ）   
[19]李大海，王榆锋，王振东．面向遥感图像云分割问题的新型U-Net模 型[J].计算机应用研究,2021,38(11): $3 5 0 6 { - } 3 5 0 9 { + } 3 5 1 6$ (Li Dahai, Wang Yufeng, Wang Zhendong. A novel U-Net model for remote sensing image cloud segmentation problem [J]. Computer Application Research, 2021, 38 (11): $3 5 0 6 { - } 3 5 0 9 { + } 3 5 1 6 .$ ）   
[20] He Zhiyu,He Jianping,Chen Cailian,et al. CPCA: A chebyshev proxy and consensus based algorithm for general distributed optimization [C]// 2020 American Control Conference (ACC) .IEEE,2020:94-99.   
[21]Wei Xiang,Gong Boqing,Liu Zixia,et al.Improving the improved training of wasserstein gans:A consistency term and its dual effect [J]. arXiv preprint arXiv:1803.01541,2018.   
[22] Cai Shaoyu,Zhu Kening,Ban Y,et al.Visual-Tactile Cross-Modal Data Generation using Residue-Fusion GAN with Feature-Matching and Perceptual Losses [J].IEEE Robotics and Automation Letters,2021,6 (4): 7525-7532.   
[23] Goodfellow I,Pouget-Abadie J,Mirza M,et al.Generative adversarial networks [J]. Communications of the ACM,2020,63 (11):139-144.   
[24]Liu Ziwei,Luo Ping,WangXiaogong,et al.Deep learning face attributes in the wild [C]// Proceedings of the IEEE international conference on computer vision.IEEE,2015:3730-3738.