# 面向无监督分割的双分支上采样域自适应网络

韩宗桓1，刘名果1，李坤²，陈立家1，田敏1，兰天翔1，梁倩1(1．河南大学 物理与电子学院，河南 开封 475004;2.开封平煤新型炭材料科技有限公司，河南 开封 475004)

摘要：工业应用中，表面压印字符图像全监督语义分割将会给企业带来高昂的数据集标注成本。针对该问题，提出了双支路特征融合的域适应分割方法(Dual-branch Feature Fusion Domain Adaptation，DbFFDA)。首先，借鉴U-Net的跨层连接设计思路，提出了双分支上采样结构的残差域适应分割网络(Residual Adaptation Network，Res-Adp)。同时，提出了融合特征输入用于提升网络分割性能，克服了字符缺失的问题。此外，提出了分割连续性损失函数$L _ { c o n }$ ，抑制了分割图像中噪点的产生。在石墨电极表面压印字符无监督分割实验中，所提方法MIoU值可达 $6 9 . 6 0 \%$ 。实际分割效果已基本满足字符识别需求，有望在特定工业场景中投入实际应用，为企业节省巨大的数据集标注成本。

关键词：表面压印字符；域适应；语义分割；无监督训练 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2022.02.0062

Double branch upsampling domain adaptive network for unsupervised segmentation

Han Zonghuan1,Liu Mingguol†,Li Shen², Chen Lijia1, Tian Min1,Lan Tianxiang], Liang Qian1 (1.SchoolofPhysics&Electronics,HenanUniversity,Kaifeng Henan47504,China;2.KaifengPingmeiNewCarbon Materials Technology Co,Ltd,Kaifeng Henan 475004, China)

Abstract:In industrialapplications,fullsupervisedsemanticsegmentationofsurface-imprintedcharacterimages wilring highdataset annotationcosts to enterprises.To solvethis problem,this paper proposes adual-branch feature fusiondomain adaptation (DbFFDA)method.First,themethod draws onthe design ideaof U-Net'scross-layerconnection,and proposes a residual adaptation network (Res-Adp)with a dual-branch upsampling structure.At the same time,this method proposes fusion feature input to improve network segmentation performance and overcome the problemof missing characters. Furthermore, this method proposes a segmentation continuity loss function $L _ { { C o n } }$ ,which suppresses the generation of noise in segmented images.In the unsupervisedsegmentation experimentofimprinted characters onthesurfaceofgraphiteelectrodes, the MIoU value of the proposed method can reach $6 9 . 6 0 \%$ .The actual segmentation effect has basically met the needs of characterrecognitionnditisexpectedtobeputintopracticalapplications inspecificindustrialsenarios,svingeterpises huge dataset labeling costs.

Key words: surface imprint characters; domain adaptation; semantic segmentation; unsupervised training

# 0 引言

图像语义分割是计算机视觉领域重要的研究方向，在自动驾驶、字符识别等领域具有广泛的应用前景，其任务目标是将图像中各像素点归纳解析为具有特定语义信息的类别。在工业应用中，因受光线、打印机质量影响，表面压印字符图像的分割难度较大，传统算法很难对其进行精确的分割。自深度学习技术问世以来，众多研究者在图像语义分割领域进行了一系列探索，分割效果及精度不断提升。2014 年Long等人[1]提出的(FullyConvolutionalNetworks，FCN)网络完全由卷积层构成，不包含全连接结构，为语义分割网络的设计提供了新思路。2015年提出的U-Net[2]设计了一个编码与解码部分完全对称的U型网络结构，并引入了跨层连接融合网络各层级间的信息，在医学影像分割领域取得了巨大成功。2018年，Chen等人[3\~]提出了DeepLab 系列网络，其最重要的贡献是提出了空洞空间池化金字塔(AtrousSpatialPoolingPyramid,ASPP)模块。卷积神经网络(ConvolutionalNeuralNetworks，CNN)的出现，极大的提升了复杂场景图像语义分割的效果，具有传统语义分割方法无可比拟的优点。

然而，上述各网络均采用全监督的方式进行训练，即需要手工标注的标签作为训练数据，带来了巨大的手工标注成本。随着域自适应无监督语义分割网络的研究逐渐兴起，这一问题有望得到解决。域适应任务的重点是优化对齐两域数据的特征分布，提取两域数据的共有特征对目标域数据进行预测。研究者们提出了各种域适应方法，其中大多数域适应方法均使用生成对抗网络(GenerativeAdversarialNetworks,GAN)[7对抗学习进行域适应训练。将分割网络作为生成器，源域和目标域图像送入分割网络(生成器)得到的分割预测交替送入判别器中，分割网络与判别器对抗训练以对齐两域特征的分布，实现域适应分割。Ganin等人提出的(Domain-AdversarialNeuralNetwork，DANN)[8]由特征提取模块、分类模块和域判别模块组成。该网络同时构造了图像分类损失和域分类损失等两个损失函数，在训练过程中既提升了网络性能又对齐了两域数据的分布，提升了对目标域图像的分类能力。因使用单域判别器的对抗性域适应方法无法利用复杂的多模结构，Pei等人[9提出的(Multi-AdversarialDomain

Adaptation，MADA)构造了多个判别器进行域适应训练。多个域判别器可从各个维度对齐两域数据的分布，提升域适应效果。Luo 等人[10]提出的(Category-Level AdversarialNetwork,CLAN)构造了类别级别的对抗网络，旨在整体对齐一致性中强化局部语义一致性。Wang 等人[11]提出的(Patch-based Output Space Adversarial Learning, pOSAL)设计了一个轻量且高效的分割网络。并提出一种新的形态感知分割损失来指导网络生成准确和平滑的分割预测。Wang 等人[12]提出了边界和熵驱动的对抗学习(BoundaryandEntropy-drivenAdversarialLearning，BEAL)域适应框架，以改进模糊边界区域上的分割性能。BEAL 通过鼓励目标域的边界预测与源域相似，以生成更准确的边界。Zhu等人[13]提出的循环式生成对抗网络(Cycle-Consistent Generative AdversarialNetworks,CycleGAN)将两个GAN 网络级联在一起，并引入了循环一致性损失函数，构造了一个源域图像与目标域图像的双向风格迁移网络，因此可生成接近目标域数据分布的模拟样本协助训练。Chen 等人[14]对CycleGAN 结构进行改进。在目标域到源域的生成器上添加了分割分支，从图像和特征等两个角度对齐源域图像和目标域图像的分布，在医学MRI图像和 CT 图像之间的域适应分割上取得了巨大成功。张勋晖等人[15提出的域适应分割方法在分割网络中引入了空洞空间池化金字塔(ASPP)提取各尺度的图像特征以提升分割性能，并将分割预测的信息熵作用于对抗损失，以减小域偏移。Liu 等人提出的(Source-Free Domain Adaptation，SFDA)[16]网络提供了一个在源域数据集无法公开的应用场景中进行域适应训练的方法。通过从源域模型中恢复和筛选源域数据，仅使用训练完成的源域模型和目标域数据集即可实现域适应。Araslanov 等人[17]提出的轻量化域适应分割方法针对现有网络模型较为复杂、资源消耗大的缺点，槟弃了对抗训练和风格迁移等常用的域适应方法。采用加噪、翻转和缩放等数据增强技术确保跨域的图像语义分割的一致性。Wang 等人提出的(Correlation-Aware Domain Adaptation，CorDA)[18]使用两域通用的自监督深度估计的指导来弥合领域差距。该方法在目标深度估计的帮助下显式学习任务特征相关性以改善预测效果。Saha 等人[19]提出了一种编码视觉任务关系的方法，用于提升无监督域适应网络的性能。提出的跨任务关系层(Cross-TaskRelationLayer，CTRL)编码了语义和深度预测之间的任务依赖关系。刘少鹏等人[20]提出了一种两阶段分割网络一一CDR-GANs。各分割阶段都包含语义分割网络、生成器和判别器等三部分，训练过程中，判别器指导语义分割网络和生成器学习原图和分割预测的联合概率分布。Li 等人[21针对现有域适应算法使用共享的源域网络学习跨域的特征表示限制了对未标记的目标域对象的泛化能力的问题。提出了一种可转 移语义增强(TransferableSemanticAugmentation，TSA)方法，通过隐式生成关于目标域对象的源域特征来增强网络的适应能力。本文所提双支路特征融合的域适应分割方法DbFFDA在网络结构、图像预处理和损失函数等方面对U-Net进行改进，在石墨电极压印字符数据集上取得了较为理想的分割效果，基本满足工业应用需求。DbFFDA创新之处包含以下3个方面：

a）提出一种双分支上采样结构的无监督语义分割网络Res-Adp。在U-Net的跨层连接中加入了残差模块，以搭建残差支路用于两域特征对齐。网络上采样过程中的各级特征分别通过残差支路与卷积支路进行上采样。残差支路负责特征对齐，以使用域不变特征对图像进行分割，卷积支路负责保留本域特征，以使用本域独有的图像特征对分割细节进行补充。

b)融合特征输入。针对表面压印字符图像噪点多、字符边缘极为重要的特点，将表面压印字符灰度图像、中值滤波图像和边缘检测图像作为网络输入的3个通道，融合送入网络进行训练。

c）构造分割连续性损失函数 $L _ { c o n }$ 约束分割网络的训练。根据分割图像中各类对象内部连续的先验知识提出了分割连续性损失函数 $L _ { c o n }$ ，通过约束源域分割图像的生成间接提升目标域分割效果，抑制了字符中的空洞与背景中噪点的产生。

# 1 双支路特征融合的域适应分割方法DbFFDA

# 1.1域适应分割框架

域适应分割框架如图1所示。分割网络为本文所提双分支上采样网络Res-Adp，为两域数据所共享。Is为源域(模拟)数据，其标签极易获取，监督信息丰富，具有完备的标签集Ls。Ir为目标域(真实)数据，无监督信息。

![](images/b158e76d9c5a9b64364bfa2cdf9a090fa6c6ff306f706ad244097ef37282e6e7.jpg)  
图1域适应分割框架  
Fig.1Domain adaptive segmentation framework

源域数据为计算机生成的模拟图像，标签无须手工标注，目标域数据为摄像机采集到的真实图像，训练数据无标注信息。

a)源域数据的全监督训练。

(a)源域(模拟)图像Is输入分割网络后得到源域预测 $\mathbf { P } _ { \mathrm { S } }$ Ps可与其标签Ls构造交叉熵损失函数，以全监督的方式训练分割网络Res-Adp。交叉熵损失函数公式为

$$
L _ { C E } = - \frac { 1 } { N } { \sum _ { i = 1 } ^ { N } } \big [ y ^ { ( i ) } \log \big ( p ^ { ( i ) } \big ) + \big ( 1 - y ^ { ( i ) } \big ) \log \big ( 1 - p ^ { ( i ) } \big ) \big ]
$$

其中， $p ^ { ( i ) }$ 为源域预测中的像素点， $y ^ { ( i ) }$ 为源域标签中的像素点。

(b）目标域(真实)图像 $\mathrm { I r }$ 输入分割网络后得到目标域预测 $\mathbf { P } _ { \mathrm { T } }$ ，因目标域图像 $\mathrm { I _ { T } }$ 无标签，故不可构造交叉熵损失函数进行分割训练。

b)分割网络(生成器)与判别器的对抗训练。

为了使得使用源域图像训练的分割网络对目标域图像也能进行精准的分割，需要对齐两域数据的分布，进行域适应训练。将源域预测 $\mathbf { P } _ { \mathrm { S } }$ 与目标域预测 $\mathbf { P } _ { \mathrm { T } }$ 分别送入判别器，与分割网络(生成器)进行对抗训练。对抗性损失函数 ${ { L } _ { G a n } }$ 如下

$L _ { G a n } = E _ { x _ { S } \sim P _ { d a n a } \left( x _ { S } \right) } \left[ \log D \big ( S \left( x _ { S } \right) \big ) \right] + E _ { x _ { T } \sim P _ { d a u a } \left( x _ { T } \right) } \left[ \log \left( 1 - D \big ( S \left( x _ { T } \right) \big ) \right) \right]$ (2其中， $x _ { s }$ 及 $x _ { T }$ 分别为源域与目标域图像， $s$ 为分割网络,$D$ 为判别器。

网络整体损失函数 $\boldsymbol { L }$ 由三部分构成：

$$
{ \cal L } = { \cal L } _ { { G a n } } + { \cal L } _ { { C E } } + { \cal L } _ { { C o n } }
$$

其中， ${ \cal L } _ { G a n }$ 为对抗性损失函数， $L _ { C E }$ 为交叉熵损失函数。 $\scriptstyle L _ { c o n }$ 为本文所提分割连续性损失函数，将在本文第2.4节中详细阐述。

判别器的优化目标是鉴别出输入的分割预测是源域预测Ps还是目标域预测 $\mathbf { P } _ { \mathrm { T } }$ 。而分割网络(生成器)的优化目标是使得判别器难以甄别分割预测的来源。训练时，判别器训练方向是对源域预测输出全1矩阵，对目标域预测输出全0矩阵，确定分割预测的类别。判别器对目标域预测的判别结果与同形的全0矩阵构造L2范数，对源域预测的判别结果与同形的全1矩阵构造L2范数，判别器优化减小两损失函数之和。

分割网络优化目标是使得目标域预测送入判别器后输出全1矩阵，输出接近源域预测的分割结果。判别器对目标域预测的判别结果与同形的全1矩阵构造L2范数，源域输入图像与其标签构造非对抗性损失函数，分割网络优化减小两损失函数之和。

非对抗性损失函数 $L _ { C E }$ 和 $L _ { c o n }$ 负责训练分割网络的分割性能，对抗性损失函数 ${ \cal L } _ { G a n }$ 负责训练分割网络的域适应能力，在两者的共同约束下，分割网络在提升对源域(模拟)图像分割性能的同时又对齐了两域数据的分布，进而提升了对目标域(真实)图像的分割性能。达到了对目标域(真实)图像无监督分割的目标。

# 1.2双分支上采样分割网络Res-Adp

2015年提出的U-Net设计了一个编码与解码部分完全对称的U形网络结构，并引入了跨层连接融合网络各层级间的信息，在医学影像分割领域取得了巨大成功。U-Net结构如图2所示。U-Net最大的创新点是网络对称位置的跨层连接结构，由于上下采样会不可避免的引起特征丢失，而该网络可以同时利用各个层级的特征进行分割，提升网络性能。残差网络(ResNet)[22]于2015年提出，解决了网络深度过深时性能不再提升的问题。网络某层特征图通过两层卷积层提取特征后与该层特图直接相加并激活即得残差块输出。胡扬涛等人提出的AR-Unet[23]将残差模块引入U-Net中，避免了U-Net中的梯度消失以及图像结构信息丢失等问题。

U-Net对于全监督分割任务可以达到较好的分割效果。对于域适应分割任务，源域图像进行全监督训练，分割网络与判别器共同进行对抗训练。U-Net由于结构过于简单，特征之间直接拼接，无法很好的对齐两域特征。

Res-Adp网络在U-Net编码阶段与解码阶段的跨层连接中引入了残差块对齐两域特征。为了避免因对齐两域特征而丢失本域特征的问题，设计了双分支结构改善该问题。网络上采样过程中的各级特征分别通过残差支路与卷积支路进行上采样。残差支路负责特征对齐，以使用域不变特征对图像进行分割，卷积支路负责保留本域特征，以使用本域独有的图像特征对分割细节进行补充。

![](images/4d4f4a3a45d3a50e3fb212e3ee3c33b02df76e6b77dd5ce7cecb4b6bedde93d3.jpg)  
图2 U-Net 网络结构  
Fig.2Network structure ofU-Net   
图3分割网络Res-Adp 结构  
Fig.3Structure of segmentation network Res-Adp

Res-Adp结构如图3所示，给出了图例，并在连接线上列出了操作的简称。特别的，图中连接线上的C表示先执行连接线对应操作再与其他特征图进行拼接。Ri-C表示先通过i个残差块再与其他特征图进行拼接，US-C表示先上采样再与其他特征图进行拼接。特征图旁的数字，逗号左边的数值表示该特征图边长与网络输入图像边长的比值，逗号右边的数值表示该层特征图的通道数。如1/2，128表示该特征图边长为网络输入图像的1/2，包含128个通道。

010502 0.50.20.8 0.90.40.8 0.10.20.3 0.40.50.6 0.60.50.4 0.90.80.7 $\ c =$ 0.90.80.7 0.60.50.4 Convolution (Cv) Desidua block (Ds) 0.60.40.5 0.20.00.9 0.10.30.1 ① 0.60.71.0 0.70.80.9 0.30.20.1 0.30.20.1 Upsat (ing (us) 基本残差单元 1/2,256 拼接操作 图例 R4-C F2-F 1/8,1024 F4-F ↑us-c PC 111.1114 阿口 C FrR 1/4,768 1/4.256R2C R C R1 Cvx2↑ 小e F1-A B F2-A F3-A S F4-A sa F5-A Foe 915355 FeFa s+s8 F2-B 1/8 F2-2 5t6/ t9T/I F1-0 源域预测Ps 1/8,5121/166 R21/8,1536 3 图像 1/2,128 1/8,1536 Ftus-.C P-3C 1/2,384R4 目标域预测P R3-C F3-F US-C PPC 1/4,512 F1-F R5-C 1/1,128

输入图像使用2层卷积扩充通道数后进行4次下采样到达网络最深层级，按照下采样过程中特征图的尺度将网络划分为1-5层，分别记为 $\operatorname { F } _ { \mathrm { i - A } }$ 。1层为输入图像所在层，5层为网络最深层。

下采样到网络最深层的特征图Fs-A卷积2次后记为Fs-B。从F5-A和 $\mathrm { F } _ { 5 - \mathrm { B } }$ 分别引出一条支路，支路一经1个残差块对齐特征后上采样到第4层级。与此同时，下采样到第4层的特征图 $\mathrm { F _ { 4 - A } }$ 通过2个残差块后与支路一拼接，得到融合特征 $\mathrm { F } _ { 4 - \mathrm { F } }$ 。

支路二经2层卷积后上采样到第4层级，与F4-F通过2个残差块后的特征图拼接得到F4-B。

此后特征图逐步上采样，对于上采样过程中的各层级特征图，均从Fi-B引出两条支路。第一支路为残差支路，用于对齐两域特征。第二支路为上采样支路，用于保留本域独有特征。

从 $\mathrm { F } _ { 4 - \mathrm { B } }$ 引出两条支路。支路一经2个残差块对齐特征后上采样到第3层级。与此同时，下采样到第3层的特征图 $\mathrm { F } _ { 3 }$ A通过3个残差块后与支路一拼接，得到融合特征 $\mathrm { F } _ { 3 - \mathrm { F } }$ 。

支路二经过2层卷积后上采样到第3层级，与 $\mathrm { F } _ { 3 - \mathrm { F } }$ 通过3 个残差块后的特征图拼接得到F3-B。

同理，重复上述操作，依次得到 $\operatorname { F } _ { 2 - \mathrm { B } }$ 、F1-B。随着上采样过程中网络深度逐步变浅，对齐两域特征所需残差块数量逐步增加，从第5层的1个残差块依次增加到第1层的5个残差块。

第1层中，Fi-B通过2层卷积调整通道数量后映射为概率分布图再求最大值索引即得网络分割预测。

# 1.3 马尔可夫判别器

DbFFDA的判别器为马尔可夫判别器[24]。如图4所示，分割预测输入判别器进行4次下采样后再进行1次卷积操作，即可输出通道数为1的特征图。马尔可夫判别器也称为PatchGAN，输出特征图上的一点表征了分割预测上一块区域的真实性。判别器的优化方向是鉴别出输入判别器的分割预测属于源域预测还是目标域预测。分割网络的优化方向是生成判别器无法分辨的分割预测。两者相互博弈，不断提升自身性能，以达到对齐两域数据分布的目的。

![](images/5ab76f948a19e5e35cf30de22b48f41fbf7487d77239dd03ed74e039827543ad.jpg)  
图4马尔可夫判别器结构

# 1.4融合特征输入

在复杂多变的自然光线条件下，受打印机打印质量及图像采集设备性能限制，表面压印字符图像具有明暗不均、噪点较多的特点。因此直接将原图像送入网络训练会给分割图像带来大量二值噪点，严重影响分割图像的纯净度。

将摄像机采集到的表面压印字符彩色图像转换为灰度图像作为网络输入数据的第1通道。

选用中值滤波的方法去除原图中的噪点，前景信息也最大程度地得到了保留。将中值滤波图像作为网络输入数据的第2通道。

表面压印字符图像中字符的边缘是前景的关键信息，对字符的分割具有重要意义。使用索贝尔(Sobel)算子对中值滤波图像进行边缘提取，所得图像作为网络输入数据的第3通道。

图5为网络输入的3通道数据示例图，将3通道图像拼接后送入网络进行训练。  

<html><body><table><tr><td></td><td>源域</td><td>目标域</td></tr><tr><td>通道1: 灰度图像</td><td>SDK0123</td><td>0A04768</td></tr><tr><td>通道2： 中值滤波</td><td>SDK0123</td><td>0A04768</td></tr><tr><td>通道子</td><td>SDK0123</td><td>0A04768</td></tr></table></body></html>

![](images/afb59e993fca43d3a5af944dd1ee52899b92200b45b616f82009ad65efa5d355.jpg)  
Fig.4Markov discriminator structure   
图5融合特征输入  
Fig.5Fusion feature input   
图7石墨电极实拍图像 Fig.7Real image of graphite electrode

# 1.5分割连续性损失函数 $L _ { c o n }$

因表面压印字符图像噪点较多，部分字符扭曲变形，故仅使用交叉熵函数作为非对抗性损失函数对分割网络进行训练，目标域分割图像上出现了字符空洞与二值噪点。

为解决该问题，受传统计算机图像处理算法启发，提出分割连续性损失函数 $L _ { C o n }$ 。二值标签图中单个字符内部是连续的，背景亦连续，无二值噪点相互穿插，即前景与背景相对独立。因此 $\mathrm { \Delta N }$ 通道标签中各通道上值为1的点与值为0的点均应当是连续的，即某类与其他类相互独立且内部连续。如图6所示，除边界点外，某点与其邻域的点的值应当相同。

![](images/0cf300ec2a741ba23fc9de66501a558f1d72449d866a20039ae410b942d23547.jpg)  
图6N通道标签某通道中的某点及其四邻域 Fig.6Point of a channel in an n-channel label and its four neigh-borhoods

因网络分割图像由 $\mathrm { \Delta N }$ 通道特征图映射为概率分布图再求最大值索引得到，故网络输出的N通道特征图也应当具有与标签相同的性质，即各点的激活值连续。 $\mathrm { ~  ~ N ~ }$ 通道特征图某通道上的某点 $A _ { ( i , j , k ) }$ 应具有与其邻域相近的激活值，故可构造分割连续性损失函数 $L _ { c o n }$ ：

$$
L _ { C o n } = \frac { 1 } { N } \sum _ { k = 1 } ^ { c } \sum _ { j = 1 } ^ { m - 1 } \sum _ { i = 1 } ^ { n - 1 } \{ | A _ { ( i , j , k ) } - A _ { ( i - 1 , j , k ) } | + | A _ { ( i , j , k ) } - A _ { ( i + 1 , j , k ) } |  \}
$$

其中， $A _ { ( i , j , k ) }$ 代表第 $k$ 通道上位于 $( i , j )$ 处的点， $A _ { ( i - 1 , j , k ) }$ 、 $A _ { ( i + 1 , j , k ) }$ 、$A _ { ( i , j - 1 , k ) }$ 、 $A _ { ( i , j + 1 , k ) }$ 分别为该点的左、右、上、下邻域。该函数的引入有效抑制了字符中空洞的产生。

# 2 实验验证

# 2.1实验数据

域适应分割有效解决了语义分割数据集手工标注成本高昂的问题，具有广阔的应用前景。在工业应用中，众多应用场景需要使用语义分割算法对采集得到的图像进行分割以进行后续处理。

在石墨电极生产这一工业场景中，为方便对生产过程中的石墨电极进行统计与管理，需要对石墨电极表面压印字符进行识别。语义分割是识别前的重要步骤，而语义分割数据集像素级的标注将会给企业带来巨大的生产成本。本文使用计算机生成源域数据，摄像机采集目标域数据，采用域适应分割方法有效地解决了这一问题，为企业节省了标注成本。

实验数据集包含源域数据和目标域数据两部分。源域(模拟)数据由计算机字库字符截图构成，无须手工标注，具有计算机生成的完备的标签集。图像中字符的字体、大小和空间位置均是随机的。目标域数据由手机摄像头采集某碳材料生产企业的石墨电极表面压印字符图像构成，如图7所示。

实验数据集示例图像如图8所示。源域数据(计算机字库字符)包含600张图像，目标域数据(石墨电极表面压印字符)包含550张图像，其中440张图像为训练数据，110张图像为测试数据。数据集所有图像的尺寸均为 $5 1 2 \times 1 2 8$ 。

# 2.2评价指标

使用像素精度(PixelAccuracy，PA)、平均像素精度(MeanPixelAccuracy，MPA)、精准率(Precision)、召回率(Recall)和平均交并比(Mean Intersection OverUnion，MIoU)等五种评价指标对网络性能进行评估。

PA为分类正确的像素点数与总像素点数之比。MPA为各类目标分类正确的像素点数与该类总像素点数之比的均值。Precision为预测为正例的像素点中实际为正例的比例。Recau为正确预测的正例的比例。交并比 $I o U$ 为预测图像与标签图像中某一类物体交集所含像素点数与并集所含像素点数之比，平均交并比MIoU指各类交并比的均值。五种评价指标公式如下：

$$
P A = { \frac { T P + T N } { T P + F N + T N + F P } }
$$

$$
M P A = m e a n \Biggl ( \frac { T P + T N } { T P + F N + T N + F P } \Biggr )
$$

$$
P r e c i s i o n = \frac { T P } { T P + F P }
$$

$$
R e c a l l = \frac { T P } { T P + F N }
$$

$$
M I o U = m e a n \Biggl ( \frac { A \mathrm { ~ I ~ } \ : B } { A \mathrm { ~ U ~ } B } \Biggr )
$$

其中，真正例 $T P$ 为实际为正，预测为正的像素点。真负例TN 为实际为负，预测为负的像素点。假正例 $F P$ 为实际为

负，预测为正的像素点。假负例FN为实际为正，预测为负的像素点。

# 2.3实验参数设置

实验依托TensorFlow平台构建神经网络，版本为1.15，Python版本为3.6.5。实验平台配置如下：CPU为IntelE7-$4 8 3 0 { \mathrm { v } } 4$ ，内存容量为48G，GPU为Tesla K40c。

训练策略如下：在每一轮次训练中，从源域600张计算机字库字符图像中随机抽取440张图像及对应标签与目标域训练集440张石墨电极表面压印字符图像构成当前轮次训练数据。训练过程中对于每1个批次的源域数据，使用随机放缩及加噪的方法增加样本多样性，提升分割效果。生成器学习率设为1e-5，判别器学习率设为4e-6，使用Adam优化器进行优化。每迭代1轮保存1次网络模型，共迭代100轮。使用保存的网络模型对测试集进行测试，记录各轮模型测试结果。

# 2.4实验结果与分析

# 2.4.1对比实验结果与分析

实验分为CLAN[10]、pOSAL[11]、BEAL[12]、DbFFDA等4组。对比了DbFFDA与现有算法的性能表现。

MIoU是语义分割领域使用最广泛的性能评价指标。选用MIoU作为主评价指标，找出各实验组的MIoU最大值对应训练轮次，将该轮评价指标数据作为实验结果。分割效果对比如图9所示，分割细节对比如图10所示。DbFFDA与现有算法定量评价对比如表1。

根据图9、10和表1数据可以看出：

a)CLAN组分割所得图像中字符缺失严重，且存在大量块状噪点。无法进行后续识别，MIoU仅为 $56 . 2 2 \%$ 。

b)pOSAL组分割所得图像中字符较为完整，但仍存在大量块状噪点，MIoU可达 $6 6 . 8 3 \%$ 。

c)BEAL组块状噪点较pOSAL组具有一定程度的减少，但字符仍存在一定程度的缺失，MIoU可达 $6 8 . 4 6 \%$ 。

d)DbFFDA组分割所得图像中字符基本无缺失，边缘光滑无毛刺，块状噪点最少。MIoU可达 $6 9 . 6 0 \%$ ，基本满足工业应用中表面压印字符后续识别需求。

<html><body><table><tr><td>原图</td><td>0A05982</td><td>0A04815</td><td>OA</td><td>0A05979</td><td>0A 04873</td></tr><tr><td>CLAN</td><td>0A0 6900</td><td></td><td></td><td></td><td></td></tr><tr><td>pOSAL</td><td>0A05:9:82</td><td>0A0.4815</td><td>DA 485</td><td>0A:0:5979</td><td>OA' 0 4873</td></tr><tr><td>BEAL</td><td>0A0 59:32</td><td>0A0 4815</td><td>□A 485</td><td>0A05979</td><td>OA 0 4873</td></tr><tr><td>DbFFDA</td><td>0A0: 5.9:82</td><td>QA04815</td><td>DA 0 4851</td><td>0A0 5979</td><td>0A 0 4873</td></tr><tr><td>标签</td><td>0AO 5982</td><td>0A04815</td><td>0A 0 4851</td><td>OAO 5979</td><td>0A 0 4873</td></tr></table></body></html>

AAAAA 4444 O 1000 0 原图 CLAN pOSAL BEAL DbFFDA 标签

![](images/88ece06c2adfd3e088861e0ff87c0da1cef9eaca32c6db37f3a738361336b0fe.jpg)  
图8数据集图像示例Fig.8Examples of dataset  
图9分割效果对比  
图10 分割细节对比  
Fig.10 Segmentation detail comparison chart   
Fig.9Comparison of segmentation effect

表1对比实验定量评价  
Tab.1 Quantitative evaluation of comparative experiments /%   

<html><body><table><tr><td>Approachs</td><td>PA</td><td>MPA</td><td>Precision</td><td>Recall</td><td>MIoU</td></tr><tr><td>CLAN[10]]</td><td>93.99</td><td>60.44</td><td>45.81</td><td>22.49</td><td>56.22</td></tr><tr><td>pOSAL[11</td><td>93.51</td><td>82.39</td><td>45.43</td><td>64.14</td><td>66.83</td></tr><tr><td>BEAL[12]</td><td>95.59</td><td>82.07</td><td>46.91</td><td>61.34</td><td>68.46</td></tr><tr><td>DbFFDA</td><td>96.12</td><td>80.90</td><td>59.60</td><td>64.29</td><td>69.60</td></tr></table></body></html>

2.4.2消融实验结果与分析

消融实验分为U-Net(全监督)[2]、U-Net(无监督)[2]、Res-Adp(创新点1)、Res-Adp+融合特征输入(创新点 $1 { + } 2$ )、Res-Adp+融合特征输入 $+ L _ { c o n }$ (DbFFDA，创新点 $1 + 2 + 3 )$ 等5组。对比了

DbFFDA与全监督U-Net网络的性能差距，并实验证实了提出的各创新点的效果。找出各实验组的MoU最大值对应训练轮次，将该轮评价指标数据作为实验结果。分割效果对比如图11所示，分割细节对比如图12所示。消融实验定量评价对比如表2。

<html><body><table><tr><td>原图</td><td>0A05982</td><td>0A04815</td><td>0A0485</td><td>0A05979</td><td>0A04873</td></tr><tr><td>U-Net (全监督)</td><td>0A0 5982</td><td>0A04815</td><td>0A 0 485</td><td>0A05979</td><td>0A 0 4873</td></tr><tr><td>U-Net (无监督)</td><td>0A059.82</td><td>0A0.4815</td><td>A 0 485</td><td>0A05979</td><td>0A 0 4873</td></tr><tr><td>Res点</td><td>0A059.82</td><td>QA04815</td><td>DA 0 485</td><td>0A05979</td><td>0A 0 4873</td></tr><tr><td>融特输入 (创新点1+2)</td><td>0A059.82</td><td>0A04815</td><td>DA 0 485</td><td>0A0 5979</td><td>0A 0 4873</td></tr><tr><td>+融合特征输入 +Lccn(创新点1+2+3)</td><td>0A0. 59.82</td><td>QA04815</td><td>DA 0 485</td><td>0A0 5979</td><td>0A 0 4873</td></tr><tr><td>标签</td><td>0A0 5982</td><td>0A04815</td><td>0A 0 485</td><td>0A0 5979</td><td>0A 0 4873</td></tr></table></body></html>

AAAAAAA444444  
0 00000 0Res-Adp Res-Adp  
原图 U-Net（全监U-Net（无监 Res-Adp +融合特征 融合特征输入 标签督） 督) （创新点1） 输入（创新 + Lcon（创新点1+2) 点1+2+3)

表2消融实验定量评价  
Tab.2Quantitative evaluation of ablation experiment $\%$   

<html><body><table><tr><td>Approachs</td><td>PA</td><td></td><td>MPA Precision Recall MIoU</td></tr><tr><td>U-Net(全监督)[2]</td><td>98.3190.67</td><td>79.01</td><td>82.30 83.08</td></tr><tr><td>U-Net(无监督)[2]</td><td>96.38 60.44</td><td>54.71</td><td>56.79 67.48</td></tr><tr><td>Res-Adp</td><td>95.75 84.78</td><td>51.87</td><td>72.85 69.00</td></tr><tr><td>Res-Adp+融合特征输入</td><td>96.7379.20</td><td>60.65</td><td>60.11 69.43</td></tr><tr><td>Res-Adp+融合特征输入+ Lcon</td><td>96.12 80.90</td><td>59.60</td><td>64.29 69.60</td></tr></table></body></html>

Fig.12 Segmentation detail comparison of ablation experiments

根据图11、12及表2数据可以看出：a）无监督U-Net组分割所得图像存在字符缺失、噪点较多等问题。Res-Adp组(创新点1)由于采用了双分支上采样结构，在对齐两域特征的同时又较为完整的保留了本域特征，极大程度地改善了这一问题，分割得到的字符连续无缺失，MIoU较U-Net(无监督)组提升了 $1 . 5 2 \%$ 。b)Res-Adp+融合特征输入组(创新点$_ { 1 + 2 ) }$ 由于输入网络的数据中增加了中值滤波图像与 Sobel 算子边缘检测图像，抑制了原图中的噪点，增强了字符的边缘信息。分割所得字符边缘较为光滑，抑制了毛刺现象的产生，且噪点较 Res-Adp 组(创新点1)也有一定程度的减少，使得MIoU较Res-Adp组提升了 $0 . 4 3 \%$ 。c)Res-Adp+融合特征输$\lambda + L _ { c o n }$ 组(DbFFDA，创新点 $1 + 2 + 3 )$ 分割所得图像中字符连续无缺失，边缘光滑无毛刺，且背景中噪点最少。由于分割连续性损失函数 $L _ { C o n }$ 的引入，进一步抑制了背景中的噪点与字符中空洞的产生，分割效果最佳，MIoU可达 $6 9 . 6 0 \%$ 。

DbFFDA与全监督U-Net网络在客观评价指标方面仍存在一定差距，但实际分割效果已基本满足字符识别需要，有望投入实际的工业应用中。

# 3 结束语

针对工业应用中表面压印字符图像对应标签获取困难，手工标注成本高昂的问题，本文提出一种双支路特征融合的域适应分割方法DbFFDA。首先，借鉴U-Net的跨层连接设计思路，提出一种双分支上采样分割网络Res-Adp。同时，将灰度图像、中值滤波图像与边缘检测图像融合作为网络输入数据，抑制了原图中的噪点，增强了字符的边缘信息。此外，因标签中各类对象内部连续，故分割网络输出特征图应当具有相同的性质，本文据此提出分割连续性损失函数 $L _ { c o n }$ 该函数通过约束源域分割图像的生成间接提升目标域图像的分割效果，进一步抑制了字符中空洞与背景噪点的产生。DbFFDA分割所得图像中字符完整、边缘光滑、噪点较少，MIoU可达 $6 9 . 6 0 \%$ ，基本满足工业应用中表面压印字符后续识别需求。

针对部分图像因光照不均引起的分割预测中噪点过多的问题，作者将在后续工作中尝试对判别器结构进行改进，使其更好的约束生成器的优化，抑制分割预测中噪点的产生，提升分割效果。

# 参考文献：

[1]Long J,Shelhamer E,Darrell T.Fully convolutional networks for semantic segmentation [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Boston:IEEE Press,2015:3431-3440.   
[2]Ronneberger O,Fischer P,Brox T.U-net: convolutional networks for biomedical image segmentation [J].Medical Image Computing and Computer-Assisted Intervention,2015:1520-1528.   
[3] Chen L C,Papandreou G，Kokkinos I,et al.Semantic image segmentation with deep convolutional nets and fully connected crfs [C]// International Conference in Learning Representations,2015.   
[4]Chen L C,Papandreou G,Kokkinos I,et al.Deeplab: Semantic image segmentation with deep convolutional nets,atrous convolution,and fully connected crfs [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2018,40(4):834-848.   
[5]Chen L C,Papandreou G,SchroffF,et al. Rethinking atrous convolution for semantic image segmentation [J].arXiv preprint arXiv:1706.05587, 2017.   
[6]Chen L C,Zhu Yukun,Papandreou G,et al. Encoder-decoder with atrous separableconvolutionforsemanticimagesegmentation[C]// Proceedings of the European Conference on Computer Vision (ECCV) . 2018:801-818.   
[7]GoodfellowIJ,Pouget AJ,Mirza M,et al.Generative adversarial networks [C]//Proceedings of Annual Conference on Neural Information Processing Systems.Montreal,Quebec,Canada:ACM.2014.2672-2680.   
[8]Ganin Y,Lempitsky V S.Unsupervised domain adaptation by backpropagation [C]//Proceedings of the 32nd International Conference on Machine Learning.Lille,France: JMLR,2015.1180-1189.   
[9]Pei Zhongyi,Cao Zhangjie,Long Mingsheng,et al.Multi-adversarial domain adaptation [C]//Proceedings of the 32nd Conference on Artificial Intelligence,New Orleans,Louisiana,USA: AAAI,2018.3934-3941.   
[10]Luo Yawei,Zheng Liang,Guan Tao,et al. Takinga closer look at domain shift:Category-level adversaries for semantics consistent domain adaptation [C]//Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2019:2507-2516.   
[11] Wang Shujun,Yu Lequan,Yang Xin,et al.Patch-based output space adversarial learning for joint optic disc and cup segmentation [J].IEEE Trans on Medical Imaging,2019,38 (11): 2485-2495.   
[12] Wang Shujun,Yu Lequan,Li Kang,et al. Boundary and entropy-driven adversarial learning for fundus image segmentation [C]// International Conference on Medical Image Computing and Computer-Assisted Intervention. Springer, Cham,2019:102-110.   
[13] Zhu Junyan,Park T,Isola P,et al.Unpaired image-to-image translation usingcycle-consistent adversarial networks[C]//2017IEEE International Conference on Computer Vision (ICCV).2017:2242-2251.   
[14] Chen Cheng,Dou Qi, Chen Hao,et al.Unsupervised bidirectional crossmodality adaptation via deeply synergistic image and feature alignment for medical image segmentation [J]. IEEE Trans on Medical Imaging, 2020,39 (7): 2494-2505.   
[15]张勋晖，周勇，赵佳琦，等．基于熵增强的无监督域适应遥感图像语 义分割[J]．计算机应用研究，2021,38(09):2852-2856.(Zhang Xunhui, Zhou Yong,Zhao Jiaqi,et al. Entropy enhanced unsupervised domain adaptive remote sensing image semantic segmentation [J]. Application Research ofComputers,2021,38 (09):2852-2856.)   
[16] Liu Yuang,Zhang Wei,Wang Jun. Source-free domain adaptation for semantic segmentation [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2021:1215-1224.   
[17] Araslanov N,Roth S.Self-supervised augmentation consistency for adapting semantic segmentation [C]// Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2O21:15384- 15394.   
[18] Wang Qin,Dai Dengxin,Hoyer L,et al. Domain adaptive semantic segmentation with self-supervised depth estimation [C]// Proceedings of the IEEE/CVF International Conference on Computer Vision.2021: 8515-8525.   
[19] Saha S,Obukhov A,Paudel D P,et al.Learning to relate depth and semantics for unsupervised domain adaptation [C]//Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2021:8197-8207.   
[20]刘少鹏，洪佳明，梁杰鹏，等．面向医学图像分割的半监督条件生成 对抗网[J].软件学报,2020,31(8):2588-2602.(Liu Shaopeng,Hong Jiaming,Liang Jiepeng,et al. Medical image seg-mentation using semisupervised conditional generative adversarial nets [J].Journal of Software,2020,31(8):2588-2602.)   
[21] Li Shuang,Xie Mixue,Gong Kaixiong,et al. Transferable semantic augmentation for domain adaptation [C]//Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2021:11516- 11525.   
[22] He Kaiming,Zhang Xiangyu,Ren Shaoqing，et al.Deep residual learning for image recognition [C]// Proceedings of Conference on Computer Vision and Pattern Recognition. Las Vegas,NV, USA: IEEE, 2016: 770-778.   
[23]胡扬涛，裴洋，林川，等．空洞残差U型网络用于视网膜血管分割 [J].计算机工程与应用,2021,57(07):185-191.(Hu Yangtao,Pei Yang, Lin Chuan,et al. Atrous residual u-net for retinal vessel segmentation [J]. Computer Engineering and Applications,2021,57(07):185-191.)   
[24] IsolaP,Zhu Junyan,Zhou Tinghui,et al. Image-to-image translation with conditional adversarial networks [C]// Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.2017:1125- 1134.