# 基于Transformer的图像分类网络MultiFormer

胡杰a.b.c†，昌敏杰a,bc，熊宗权a,bc，徐博远abc，谢礼浩abc，郭迪a,b.c(a.现代汽车零部件技术湖北省重点实验室;b.汽车零部件技术湖北省协同创新中心;c.湖北省新能源与智能网联车工程技术研究中心 武汉理工大学，武汉 430070)

摘要：为解决目前 ViT 模型无法改变输入补丁大小且输入补丁都是单一尺度信息的缺点，提出了一种基于Transformer 的图像分类网络称为 MultiFormer。MultiFormer 通过AWS(Atention With Scale)模块，将每阶段不同尺度输入小补丁嵌入为具有丰富语义信息的大补丁；通过GLA-P(Global-Local Atention With Patch)模块交替捕获局部和全局注意力，在嵌入时同时保留了细粒度和粗粒度特征。设计了MultiFormer-Tiny、-Small和-Base三种不同变体的MultiFormer模型网络，在ImageNet图像分类实验中Top-1精度分别达到 $81 . 1 \%$ 、 $8 2 . 2 \%$ 和 $8 3 . 2 \%$ ，后两个模型对比同体量的卷积神经网络ResNet-50 和ResNet-101提升 $3 . 1 \%$ 和 $3 . 4 \%$ ；对比同样基于Transformer分类模型ViT，MultiFormer-Base 在参数和计算量远小于ViT-Base/16模型且不需要大量数据预训练前提下提升 $2 . 1 \%$ 。

关键词：机器视觉；深度学习；图像分类；自注意力；Transformer 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2022.03.0133

MultiFormer: image classification network based on Transformer

Hu Jiea,b.ct, Chang Minjiea,b.c, Xiong Zongquana,b.c, Xu Boyuana,b,c, Xie Lihaoab.c, Guo Dia,b,c (a.Hubei KeyLaboratoryofAdvanced TechnologyforAutomotive Components,b.Hubei Collaborative InnovationCenter forAutomotiveComponents Technology,c.HubeiResearchCenterforNewEnergy&IntellgentConnected VehicleWuhan University of Technology,Wuhan 430070, China)

Abstract: Inorder tosolve thedisadvantage thatthe ViTcannotchange theinput patch sizeandtheinput patches are all single-scale information,this paper proposed an image classficationnetwork based on Transformer caled MultiFormer. MultiFormer embeds smallpatches with diferent scales of input at each stage into large patches with rich semantic information through theAWS (Atention With Scale) module;andcaptures local and globalatention alternatelythrough the GLA-P(Global-Local Atention With Patch） module,preserving both fine-grained andcoarse-grained features during embedding.This paperdesigned MultiFormer-Tiny,-Smalland-Base networksofthree diffrent sizes toachieve $8 1 . 1 \%$ $8 2 . 2 \%$ and $8 3 . 2 \%$ Top-l accuracy respectively in ImageNet image classification experiments, the later two models improve by $3 . 1 \%$ （20 and $3 . 4 \%$ compared to the same volume of convolutional neural networks ResNet-50 and ResNet-101;MultiFormer-Base offers a $2 . 1 \%$ improvement with far fewer parameters and computational effort than the ViT-Base/16 model,and without the need for extensive data pre-training.

Key words:machine vision; deep learning; image classification; self-attention; Transformer

# 0 引言

一方面，图像分类[11、目标检测[2]和语义分割[3]等计算机视觉任务由卷积神经网络主导，自AlexNet[4]在ImageNet图像分类挑战中获得冠军之后，卷积神经网络架构通过一系列设计变得更深、更密集且卷积形式更复杂[5\~7]，ResNet[5]提出了残差网络在加深网络层数时解决了梯度消失问题；DenceNet6引入了密集连接的拓扑结构将每个卷积块与前一个卷积块连接起来；VGG[8通过叠加卷积核扩大感受野的方法加深网络；GoogLeNet[9]通过构建密集的块结构来近似最优的稀疏结构在提高性能时不增加计算量；EfficientNet[10]证明了可以利用复合系数统一缩放模型所有维度从而提高模型性能。另一方面，Transformer由于自注意力模块具有捕捉长距离依赖[1的能力而被用于自然语言处理任务，许多研究人员受此启发，尝试探索Transformer结构在计算机视觉任务中的应用。文献[12\~15]已将自注意力模块纳入卷积神经网络并用于图像分类、目标检测和语义分割等计算机视觉任务。

Vision Transformer(ViT)[16]由于不使用卷积神经网络而通过图像序列化将Transformer应用于图像分类，因此迅速引入改进[17\~20]并用于各种下游任务[21\~24]。由于 Transformer 的自注意力模块对整个输入序列进行操作，处理自然图像时把每一个像素点都看做一个标记，其长度会远远长于单词序列，因此会比卷积操作产生更多的内存和计算成本。ViT采用折中策略将多个像素点嵌入图像补丁(Patch)作为一个标记(Token)输入自注意力模块进行计算，但是计算复杂度仍然过高且要求输入图片只能是固定大小。对ViT的改进可以分为三类:

a)改进ViT设计本身，DeiT[9]引入了合适的训练策略来摆脱大规模的预训练并采用蒸馏的方式引导模型进行更好的学习；T2T-ViT[20]采用渐进式方式将图像结构化为图片补丁并保留了局部结构信息，克服了ViT中简单标记化的局限性；Dynamicvit[23]利用Transformer标记是非结构化序列的特点，设计了一种标记稀疏化剪枝的方法，通过删除信息量不大的标记降低计算量。

b)将卷积操作引入到ViT 设计中，利用卷积进行位置编码[17]或者使用卷积来替换Transformer中的线性投影层[25]；CoAtNet[26]通过引入卷积神经网络捕获局部注意力来弥补局部特征。

c)设计新的主干网络和自注意力模块，PVT[21设计了一个金字塔结构的主干网络逐层对特征图进行下采样并使用了空间缩减注意力模块来权衡模型效率和准确率；CAT[24]设计了一个跨块自注意块将序列补丁内的注意力和序列补丁间的注意力结合起来从而使得局部信息和全局信息交互；Swin[22]提出将输入特征图划分到不同固定大小的局部窗口中，通过在每个窗口内计算自注意力来降低计算成本；DPT[27]自适应地将图像分割成不同位置和大小的像素块，可以避免对语义信息的破坏从而捕捉到完整且与对象相关的局部结构；FPT[28能够对特征图跨空间和跨尺度的非局部特征进行编码且能整合到其他主干网络用于其他下游任务。

这些工作仍然具有一些局限性，它们将单一尺度的图片补丁输入自注意力模块时会丢失许多语义信息，此时需要跨尺度注意力机制来建立它们之间的联系，同时图像分类任务需要粗粒度特征和细粒度特征之间的交互来捕获目标信息。基于上述，本文主要工作如下：a)针对ViT模型输入特征图存在尺度单一的问题，提出多尺度嵌入模块AWS(AttentionWithScale)，AWS模块使用不同尺度的卷积核对图片进行采样，融合成具有人类视觉感受野的跨尺度注意力补丁输入到下一个阶段，使每一个阶段的输入都是多尺度图片补丁；b)针对其他Transformer模型无法对像素块长距离建模导致粗粒度特征丢失的问题，设计新的自注意力模块GLA-P(Global-LocalAttentionWithPatch)，通过交替捕获全局补丁和局部补丁聚合粗粒度和细粒度特征来弥补图片补丁语义信息的不足利用注意力打包操作，在不影响网络性能的前提下减少计算量；c)设计了三个不同大小的模型称为 MultiFormer-Tiny、-Small 和-Base，在公开数据集ImageNet、CIFAR10和CIFAR100上进行图像分类实验，结果表明MultiFormer在图像分类实验中优于其他同量级的对比网络，并通过消融实验验证了各个模块的有效性。

# 1 模型框架

MultiFormer图像分类网络整体框架如图1(a)所示，主干网络参考PVT[2I]设计为4阶段金字塔结构，每个阶段由AWS多尺度嵌入模块和多个MultiFormerBlock顺序组合而成；如图1(b)所示，每个MultiFormer模块由一个GLA-P自注意力模块和一个多层感知机MLP组成，MLP使输入数据非线性化并改变数据维度。

/418 20 MLP MLPStage 1 Stage 2 Stuge 3 Stuge 4  
I×IF ×3 Trr gertt eaete Mr reat rshereetrsesa LN L  
Images H SMV Y SMV + SMV + 中 SMV X 中 GAP LAPLN LN↑ f(a)MultiFormer分类网络整体架构 (b)MulliFormer决内部结构

首先，输入图片通过AWS模块生成多尺度特征图并划分为具有多尺度信息的图片补丁，对除了Stage1之外的输出进行下采样将补丁数量减少为四分之一并把输出维度扩大为两倍形成金字塔结构。然后，把生成的多尺度补丁接入MultiFormerBlock中的GLA-P自注意力模块，GAP(GlobalAttentionwithPatch)和LAP(LocalAttentionwithPatch)即打包过的全局注意力和局部注意力交替出现形成GLA-P自注意力模块能够同时聚合输入图像的全局特征和局部特征。最后，接一个单独的视觉任务头如图像分类头(Classification Head)用于图像分类任务，下面详细介绍各个模块原理及作用。

# 1.1AWS 多尺度嵌入模块

将图像输入自注意力模块计算之前，需要将图片的像素块划分为等大小的图片补丁并序列化为二维矩阵形式来满足输入要求。如图2中补丁Patch划分方式对比所示，ViT简单地将图片中相邻的像素块划分为固定大小的补丁使每个阶段的补丁数量固定，从而方便嵌入绝对位置编码输入自注意力模块计算。这种划分方式会导致每个阶段的自注意力计算量呈平方倍增长，并需要大量数据集进行预训练而且难以训练到收敛。与ViT不同，AWS模块先将图片划分成大小为4$\times 4$ 的小补丁，然后利用下采样将小补丁合并为 $8 \times 8$ 和16$\times 1 6$ 的大补丁并将维度升为2倍，通过减少补丁数量，扩大补丁维度和大小形成金字塔结构，不仅降低了计算复杂度，而且不必限制每个阶段的补丁数量，解决了ViT必须输入固定大小图片的劣势。

![](images/df3d573fbbf882d7a3b7db8fe27652af32ec33893d5c63b883288cf6d53c1ff5.jpg)  
图1算法框架  
Fig.1Algorithm framework   
图2AWS模块  
Fig.2Module diagramofAWS

PVT[21]和 Swin[22]在将输入图片划分为等大小的补丁并序列化为二维矩阵时，由于忽视了输入特征图尺度对图片补丁尺度的影响，使得划分的补丁尺度单一并会丢失目标的多尺度语义信息，导致模型性能降低。本文设计的AWS模块在生成图片补丁之前会利用不同大小的卷积核对输入图片进行卷积操作，生成语义信息丰富的多尺度特征图用于增强嵌入补丁的语义信息。如图2所示，首先，AWS模块接收一个$H \times W \times 3$ 的RGB图像作为输入，使用三个不同大小的卷积核进行采样，将采样框的步幅保持一致，让每个采样框都有相同的中心和不同的尺度，其中 Stage1的AWS 卷积核大小设置为 $2 \times 2$ 、 $4 \times 4$ 和 $8 \times 8$ ，后三个 Stage 设置为 $2 \times 2$ 和 $4 \times$ 4，步幅都设置为 $4 \times 4$ ，为了便于特征图的融合将通道数都设置为 $\mathrm { ~ D ~ }$ 。然后，将通过不同尺度卷积核采样得到的多尺度特征图参考人眼视觉特征[29]融合成语义信息丰富的特征嵌入图。最后，将 Stage1中划分的 $4 \times 4$ 大小的补丁下采样为$8 \times 8$ 和 $1 6 \times 1 6$ 大小的补丁，并将维度扩大为两倍形成金字塔结构。与其他Transformer 网络划分的Patch尺度对比如图2右侧所示，PVT和Swin将输入图片进行划分时，粗糙地将原始特征图划分为图片补丁，此时的补丁受特征图尺度的限制只能关注到 $4 { \times } 4$ 像素块里的特征信息，如果目标尺度不局限于 $4 \times$ 4 大小的像素块之内，则模型会因为无法关注到图片目标其他尺度内的语义信息而造成目标特征信息缺失；本文提出的AWS模块通过多尺度卷积操作使得划分的补丁能够聚合特征图中 2$\times 2$ ， $4 { \times } 4$ 和 $8 \times 8$ 多个尺度中像素块的语义信息从而生成特征信息丰富的补丁，在输入后续模块时能够弥补Swin和PVT由于补丁多尺度特征信息不足而提升模型性能。

# 1.2GLA-P自注意力模块

通过AWS 模块生成多尺度补丁之后，需要将图片补丁输入图1(a)MultiFormer模块中的GLA-P自注意力模块计算。如图1(b)所示，由于在图像分类任务中，网络需要同时捕获目标的细粒度和粗粒度特征，因此在MultiFormer模块中设计了GAP和LAP交替形成新的自注意力模块GLA-P，从而能够捕获全局注意力和局部注意力来保留目标的粗粒度和细粒度特征。如图3所示，输入LAP和GAP的是经过AWS模块嵌入的多尺度特征图 $H _ { o } \times W _ { o } \times D$ ，对于LAP，每 $4 \times 4$ 的相邻像素块被分组在一起形成LocalAttention；对于GAP，同样 $4 \times 4$ 数量但间隔为4的像素块被分为一组形成GlobalAttention，不相邻的像素块由于广泛分布为生成的补丁提供了足够的上下文信息，使得全局注意力变得更加有效。

![](images/ddbf5cd9e5dff8b5cb1fe48966f997150400094f02552c4d3c5908411fcc6850.jpg)  
图3Global-Local Attention WithPatch 模块

与 CoAtNet[26]中的GLA(Global-Local Attention)通过卷积神经网络捕获局部特征，自注意力模块捕获全局特征不同，本文提出的GLA-P模块通过对相邻和相间隔的像素块分别进行短距离和长距离建模而不依赖于卷积神经网络来交替捕获全局注意力和局部注意力。为了更直观地观察GLA-P自注意力模块的作用方式，以MultiFormer-Base为例，将训练好的模型最后一层特征图输出的各个像素得分经过激活函数后，映射回原图得到Global-LocalAttention自注意力可视化表述，如图4所示，明亮部分为自注意力所关注的部位，说明本文自注意力模块能有效捕获图像全局信息。

与其他Transformer模型的自注意力模块对比如图3所示，Swin将特征图划分为几个不重叠的窗口并限制在每一个窗口内独立执行自注意力操作，此外为了补偿缺失的全局信息，提出了一种滑动窗口策略在不同窗口之间交换信息，不过Swin依然将自注意力计算局限在相邻的像素块之间，无法对生成的补丁进行长距离建模。本文提出的自注意力模块通过GlobalAttention对广泛分布的像素块进行建模而生成具有上下文信息的补丁，与通过LocalAttention对相邻像素块建模生成的补丁相结合，经过GLA-P形成的补丁同时保留输入图片的全局信息和局部信息，在自注意力计算后能够同时关注目标的粗粒度和细粒度特征从而能够在图像分类任务中表现出色。

![](images/50f6dcf1a2bf9f3e96483772733acdd083e41898ee458e9f148bfb961f70f048.jpg)  
Fig.3Module diagram ofGLA-P   
图4自注意力可视化  
Fig.4Self-attention visualization

实际上，为了尽可能保留原特征图的语义信息，本文大补丁的分辨率会比较大(如Stage1中经过GLA-P处理后的补丁大小为 $2 8 \times 2 8 )$ ，在序列化为二维数组时计算量依然会很大，因此本文设置了一个卷积打包方式来替代传统编码器中的多头注意力(Multi-headattention)[ll]，与MHA类似，接收查询(Query)、键(Key)和值(Value)并输出一个改进的加强特征。细节表述如下：

$$
P a t c h ( q , k , \nu , P = 2 , B ) = A t t e n t i o n ( Q , K ^ { \prime } , V , B )
$$

$$
\begin{array} { l } { \left\{ \begin{array} { l l } { Q = x q } \\ { K ^ { ' } = N o r m ( r e s h a p e ( C o n \nu ( x k ) ) ) } \end{array} \right. } \\ { V ^ { ' } = N o r m ( r e s h a p e ( C o n \nu ( x \nu ) ) ) } \end{array}
$$

其中， $x$ 为输入特征图， $q , k , \nu \in \mathbb { R } ^ { ( H W ) \times D }$ 为生成的对应维度的矩阵，本文在注意力每个头部都添加一个可学习的相对位置偏差[30\~32] $B \in \mathbb { R } ^ { d _ { h e a d } \times ( W H ) \times ( W H / d _ { h e a d } / P ) }$ ，Conv为对应的卷积操作，与$P a t c h ( q , k , \nu , P = 2 )$ 中 $P$ 的大小有关，例如 $P = 2$ ，则卷积核大小为4， $K ^ { \prime }$ 和 $\boldsymbol { V }$ 的维度为 $\boldsymbol { \mathcal { Q } }$ 的四分之一，Norm()为层归一化[33],Attention()为自注意力操作，计算如下：

$$
A t t e n t i o n ( q , k , \nu ) = S o f t M a x ( \frac { q k ^ { \mathord { \mathbb { T } } } } { \sqrt { d _ { h e a d } } } + B ) \nu
$$

与Swin同时处理Query、Key和Value不同，本文对键值对进行下采样后能在不影响精度的情况下减少 $\mathrm { ~ \bf ~ P ~ }$ 倍计算量，经过AttentionPatch打包操作后参数减少情况如表1所示。

表1模型参数及计算量示意  
Table 1Model parameters and calculation quantity  

<html><body><table><tr><td colspan="2">Model</td><td>MultiFormer-Tiny</td><td>MultiFormer-Small MultiFormer-Base</td><td></td></tr><tr><td>Before</td><td>Params(M)</td><td>32.7</td><td>39.8</td><td>54.7</td></tr><tr><td>Patch</td><td>Flops(G)</td><td>3.2</td><td>5.4</td><td>7.4</td></tr><tr><td>After</td><td>Params(M)</td><td>22.8</td><td>30.5</td><td>45.7</td></tr><tr><td>Patch</td><td>Flops(G)</td><td>2.4</td><td>4.8</td><td>6.9</td></tr></table></body></html>

同时由图2可将MultiFormer计算细节描述如下：

$$
\left\{ \begin{array} { l } { z _ { o } ^ { l } = G A P ( L N ( z ^ { l - 1 } ) ) + z ^ { l - 1 } } \\ { z ^ { l } = M L P ( L N ( z _ { o } ^ { l } ) ) + z _ { o } ^ { l } } \\ { z _ { o } ^ { l + 1 } = L A P ( L N ( z ^ { l } ) ) + z ^ { l } } \\ { z ^ { l + 1 } = M L P ( L N ( z _ { o } ^ { l + 1 } ) ) + z _ { o } ^ { l + 1 } } \end{array} \right.
$$

其中， $z _ { O } ^ { l }$ 和 $z ^ { l }$ 表示MultiFormer 块中GAP模块和 MLP模块的输出特征， $z _ { O } ^ { l + 1 }$ 和 $z ^ { l }$ 表示LAP 模块和MLP模块的输出特征。

# 1.3模型变体

遵循残差网络结构ResNet[5]的设计规则，本文构建了三个不同尺度大小的模型，分别称为MultiFormer-Tiny，-Small，和-Base，它们的模型大小和计算复杂度为1:1.5:3的关系，其中MultiFormer-Tiny、-Small 和-Base 的计算量和计算参数分别与ResNet-18、ResNet-50及ResNet-101相似，主要超参数设置如下：

MultiFormer-Tiny: $D = 6 4 , D e p t h = \{ 1 , 1 , 8 , 6 \} , H e a d s = \{ 2 , 4 , 8 , 1 6 \}$

MultiFormer-Small: $D = 9 6 , D e p t h = \{ 2 , 2 , 6 , 2 \} , H e a d s = \{ 3 , 6 , 1 2 , 2 4 \}$

MultiFormer-Base: $D = 9 6 , D e p t h = \{ 2 , 2 , 1 2 , 2 \} , H e a d s = \{ 3 , 6 , 1 2 , 2 4 \}$ 一其中， $D$ 为第一阶段隐藏层的通道数，Depth为每个 stage 包含的MultiFormer块数，Heads为多头注意力的维度。且在GLA-P模块中将小补丁嵌入为大补丁时的大小为Group_size $\mathbf { \bar { \rho } } = \mathbf { \rho }$ {28,14,14,7}，利用卷积将注意力打包时将Patch设置为 $P = \{ 4 , 2 , 2 , 1 \}$ ，模型设计及详细超参数设置如表2所示。

# 2 实验

用本文设计的MultiFormer 图像分类网络在ImageNet-1K、CIFAR10和CIFAR100数据集上进行图像分类实验并与同量级且具代表性的卷积神经主干网络ResNet[5]以及其他基于Transformer的主流模型进行对比，随后进行充分的消融实验验证各个模块的有效性。

# 2.1图像分类实验

ImageNet-1K 数据集[34]包含来自1000个类别的128万张训练图片和5万张验证图片，本文在训练集上训练模型，并用验证集测试输出Top-1精确度(排名第一的类别与实际结果相符的准确率)。本文将图像大小随机裁剪为 $2 2 4 \times 2 2 4$ ，优化器选择动量为0.9且衰减权重为0.05余弦衰减的AdamW优化器，批次(batch_size)设为128，初始学习率为0.001，所有模型都在4张2080Ti显卡上从头开始训练300个epoch，实验结果如表3所示。

Tab.2Model variants of backbone networks of multiformer   
表3分类实验Top-1精度对比  

<html><body><table><tr><td>Output Size</td><td>Layer Name</td><td>MultiFormer-T</td><td>MultiFormer-S</td><td>MultiFormer-B</td></tr><tr><td></td><td>AWS</td><td colspan="3">Kernel size:4×4,8×8,16×16,Stride =4</td></tr><tr><td>56x-1</td><td>GLAP</td><td>[=2.=2]x</td><td>-</td><td>[G=28.=3]x</td></tr><tr><td></td><td>AWS</td><td></td><td>Kernel size:2×2,4×4,Stride=2</td><td></td></tr><tr><td>Stage-2 28×28</td><td>GLA-P</td><td colspan="3">[D =128,H =4] [D=192,H=6x2</td></tr><tr><td></td><td>MLP</td><td>[G =14,𝑃 =2 X</td><td>[G =14,P =2</td><td>[D =192,H1=6] [G =14,P =2]</td></tr><tr><td>Stage-3</td><td>AWS</td><td></td><td>Kernel size:2×2,4×4,Stride=2</td><td></td></tr><tr><td>14×14</td><td>GLA-P MLP</td><td>[G =14,𝑃 =2 [D=256.=88</td><td>[G =14,𝑃 =2 [D=384H=127x6</td><td>[G =14,𝑃 =2 [D=384,H=12x12</td></tr><tr><td></td><td>AWS</td><td colspan="3">Kernel size: 2×2,4×4,Stride =4</td></tr><tr><td>Stage-4 7×7</td><td>GAP</td><td>[G =7,P =1 [D =512H=147x6</td><td>D-=768H1=2472</td><td>[0=768=1=24]x</td></tr><tr><td></td><td></td><td></td><td>[G1 =7,P =1</td><td></td></tr><tr><td>Head</td><td>Avg Pooling</td><td></td><td>Kernel size: 7×7</td><td></td></tr><tr><td>1x1</td><td>Linear</td><td></td><td>Classes:1000</td><td></td></tr></table></body></html>

表2MultiFormer主干网络模型变体  
Tab.3Comparison of top-1 accuracy of classification experiment   

<html><body><table><tr><td>Method</td><td>Param/M</td><td>FLOPs/G</td><td>Top-1/%</td></tr><tr><td>R18*[5]</td><td>11.7</td><td>1.8</td><td>69.8</td></tr><tr><td>R18[5]</td><td>11.7</td><td>1.8</td><td>68.5</td></tr><tr><td>DeiT-T[19]</td><td>5.7</td><td>1.3</td><td>72.2</td></tr><tr><td>PVT-S[21]</td><td>24.5</td><td>3.8</td><td>79.8</td></tr><tr><td>MultiFormer-Tiny</td><td>22.8</td><td>2.4</td><td>81.1</td></tr><tr><td>R50*[5]</td><td>25.6</td><td>4.1</td><td>76.1</td></tr><tr><td>R50[5]</td><td>25.6</td><td>4.1</td><td>78.5</td></tr><tr><td>DeiT-S[19]</td><td>22.1</td><td>4.6</td><td>79.9</td></tr><tr><td>T2T-ViT[20]</td><td>21.5</td><td>5.2</td><td>80.7</td></tr><tr><td>Swin-T[22]</td><td>29.0</td><td>4.5</td><td>81.3</td></tr><tr><td>CAT-S[24]</td><td>37.0</td><td>5.9</td><td>81.8</td></tr><tr><td>PVT-M[21]</td><td>44.2</td><td>6.7</td><td>81.2</td></tr><tr><td>MultiFormer-Small</td><td>30.5</td><td>4.8</td><td>82.2</td></tr><tr><td>R101*[5]</td><td>44.7</td><td>7.9</td><td>77.4</td></tr><tr><td>R101[5]</td><td>44.7</td><td>7.9</td><td>79.8</td></tr><tr><td>Swin-S[22]</td><td>50.0</td><td>8.7</td><td>83.0</td></tr><tr><td>CAT-B[24]</td><td>52.0</td><td>8.9</td><td>82.8</td></tr><tr><td>PVT-L[21]</td><td>61.4</td><td>9.8</td><td>81.7</td></tr><tr><td>DeiT-B[19]</td><td>86.0</td><td>17.5</td><td>81.1</td></tr><tr><td>ViT-Base/16[16]</td><td>86.6</td><td>17.6</td><td>81.1</td></tr><tr><td>MultiFormer-Base</td><td>45.7</td><td>6.9</td><td>83.2</td></tr></table></body></html>

从表3结果可以看出本文所设计的MultiFormer网络模型在参数量和计算量相当的情况下明显优于基于卷积神经网络的模型ResNet系列，MultiFormer-Tiny，-Small和-Base 模型较ResNet-18，ResNet-50 和ResNet-101 模型分别提升$12 . 6 \%$ ， $3 . 1 \%$ 和 $3 . 4 \%$ ；对比同样基于Transformer的主流模型ViT和Swin，在参数和计算量远小于ViT-Base/16模型且不需要大量数据预训练前提下，MultiFormer-Base提升 $2 . 1 \%$ 同时在参数量较Swin-S降低了 $10 \%$ 的前提下提升 $0 . 2 \%$ ，验证了所设计模型的有效性。

图5为本文所设计的MultiFormer网络模型与卷积神经网络ResNet以及其他基于Transformer工作的网络模型对比，图5(a)和(b)分别为模型参数和模型计算量与分类数据集 Top1准确率的关系，可以看出本文所设计的MultiFormer网络模型在参数量和计算量相当的情况下全面优于其他模型。

随机从ImageNet数据集中抽取图片，输入已加载训练权重的MultiFormer、PVT和Swin 网络中进行推理，将4个阶段所得到的特征图相加并映射回原图得到图像分类实验热力图如图6所示。相较于PVT和Swin网络，MultiFormer在处理单一尺度图片时，由于自注意力模块GAL-P能对上下文关系建模，因此能更加聚焦于目标的有效特征；在处理多尺度图片时，由于AWS多尺度嵌入模块能生成语义信息丰富的多尺度补丁，因此能有效关注目标的不同尺度信息及其轮廓信息。

![](images/585806498e6f78249b4ee11f4ea3075e9a512e9593e58bfd72dea7b6aebeee83.jpg)  
图5实验结果折线对比

![](images/8505aeed2eee64228bb890751f7da6bfba8956d78e7c4c20054cb20493c5a90d.jpg)  
Fig.5Broken line comparison diagram of experimental results   
图6图像分类热力图对比图  
Fig.6Thermodynamic diagram comparison of Image classification

使用CIFAR10和CIFAR100图像分类数据集对所设计的MultiFormer网络作进一步验证，CIFAR10和CIFAR100分别包含10个和100个类别，两个数据集都分别有5万张训练集和1万张测试集，在训练集上训练模型，并用验证集测试输出Top-1精确度。为了避免由于数据集较小而出现过拟合的情况，与ViT微调策略保持一致，将ImageNet分类实验获得的训练权重分别加载到 MultiFormer-Tiny、-Small 和-Base中并替换掉分类检测头，使用动量为0.9的SGD优化器进行模型微调，训练批次和轮数设置为64和300轮，实验结果如表4所示。

Tab.4Experimental results ofCIFAR   

<html><body><table><tr><td>Model</td><td>Param/M</td><td>CIFAR10</td><td>CIFAR100</td></tr><tr><td>EfficientNetV2-S[10]</td><td>24</td><td>98.7</td><td>91.5</td></tr><tr><td>EfficientNetV2-M[10]</td><td>55</td><td>99.0</td><td>92.2</td></tr><tr><td>EfficientNetV2-L[10]</td><td>121</td><td>99.1</td><td>92.3</td></tr><tr><td>LeViT-256[35]</td><td>18.9</td><td>98.0</td><td>1</td></tr><tr><td>LeViT-384[35]</td><td>39.1</td><td>98.1</td><td>1</td></tr><tr><td>ViT-B/16[16]</td><td>86</td><td>98.9</td><td>91.6</td></tr><tr><td>ViT-L/16[16]</td><td>307</td><td>99.1</td><td>93.4</td></tr><tr><td>ViT-H/16[16]</td><td>632</td><td>99.2</td><td>93.8</td></tr><tr><td>MultiFormer-Tiny</td><td>22.8</td><td>99.0</td><td>92.2</td></tr><tr><td>MultiFormer-Small</td><td>30.5</td><td>99.4</td><td>93.8</td></tr><tr><td>MultiFormer-Base</td><td>45.7</td><td>99.5</td><td>94.1</td></tr></table></body></html>

由表4可知，MultiFomer-Base在参数量较EfficientNetV2-L 降 低了 $50 \%$ 的前提下，CIFAR10和CIFAR100的Top-1精度分别提高 $0 . 4 \%$ 和 $1 . 7 \%$ ，在参数量为ViT-H/16的十分之一时，CIFAR10 和CIFAR100 的 Top-1精度仍能分别提高 $0 . 3 \%$ 和 $0 . 3 \%$ ；MultiFormer-Tiny 和-Small对比同体量模型LeViT-256和-384在CIFAR10上Top-1精度分别提高 $1 . 0 \%$ 和 $1 . 3 \%$ ，进一步验证了本文所提模型MultiFormer的有效性。

# 2.2消融实验

为了验证所设计的AWS和GLA-P模块的有效性，本文基于MultiFormer-Tiny模型在ImageNet图像分类数据集上设计了如下对比实验。

a)取消AWS多尺度嵌入模块，改为单尺度嵌入，将Stage-1中卷积核设为单个大小为 $4 \times 4$ 的卷积核，其他阶段的下采样设为单个大小为 $2 \times 2$ 的卷积核，结果如表5所示，AWS模块帮助模型取得了很大的性能提升，Top-1准确率相较于单尺度嵌入提升了 $0 . 6 \%$ 。

b)用GLA-P 模块替换为 Swin[22]、 $\mathrm { P V T } ^ { [ 2 1 ] }$ 和CoAtNet[26]模型中的自注意力模块，结果显示精度分别提升 $0 . 3 \%$ 、 $0 . 5 \%$ 和 $0 . 8 \%$ ，具体分析是因为Swin采用了滑动窗口的方式将自注意力限制在了局部范围而忽略掉了全局注意力之间的联系；PVT在处理自注意力特征时，对生成的键值对简单下采样而舍弃掉了细粒度语义信息；CoAtNet在主干网络前两个阶段过度依赖卷积神经网络提取特征会丢失部分全局信息，导致输入图片粗粒度特征的缺失而精度降低。以上实验结果表明交替捕获局部注意力和全局注意力能有效提升模型性能。

表4CIFAR 实验结果表  
表5消融实验  
Tab.5Ablation experiment   

<html><body><table><tr><td></td><td>AWS GLA-P</td><td>Swin-Attention</td><td>PVT-Attention</td><td></td><td>CoAtNet Top-1/%</td></tr><tr><td></td><td>√</td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td>80.5</td></tr><tr><td>√</td><td>√</td><td>80.8</td></tr><tr><td></td><td></td><td>80.6</td></tr><tr><td></td><td></td><td>80.3</td></tr><tr><td></td><td>√</td><td>81.1</td></tr></table></body></html>

实验条件和超参数均与之前保持一致，训练设备均为4张2080Ti显卡，训练轮数为300轮。

# 3 结束语

本文提出了一种基于Transformer的图像分类网络MultiFormer，核心组成为(AWS)AttentionWithScale多尺度嵌入模块和(GLA-P)Global-LocalAttention With Patch 自注意力模块，实验结果表明在参数和计算量相当的情况下相对于卷积神经网络和其他基于Transformer的工作有较大提升，证明了多尺度嵌入和交替捕获局部注意力及全局注意力能明显增强Transformer网络中自注意力学习特征图语义信息的能力，同时本文所设计的主干网络能较好提取特征图的语义信息，有望成为计算机视觉任务通用主干网络并用于其他下游任务。目前Transformer正在计算机视觉领域飞速发展并成为了一种趋势，希望本文能对后续基于Transformer模型所进行的工作能够起到启迪作用。

# 参考文献：

[1]黄凯奇，任伟强，谭铁牛．图像物体分类与检测算法综述[J].计算 机学报,2014,378 (06):1225-1240.(Huang Kaiqi,Ren Weiqiang,Tan Tieniu.Areview on image object classification and detection [J]. Chinese Jourmal of Computers,2014,378 (06): 1225-1240.)   
[2]李旭冬，叶茂，李涛．基于卷积神经网络的目标检测研究综述[J]. 计算机应用研究,2017,312(10):2881-2886,2891.(Li Xudong,Ye Mao,Li Tao.Review of object detection based on convolutional neural networks [J].Application Research of Computers,2017,312 (10): 2881- 2886,2891.)   
[3]田萱，王亮，丁琪．基于深度学习的图像语义分割方法综述[J]．软 件学报,2019,30 (02):440-468.(Tian Xuan,Wang Liang,Ding Lei. Review of image semantic segmentation based on deep learning [J]. Journal of Software,2019,30 (02): 440-468.)   
[4]Krizhevsky A,Sutskever I,Hinton G E.Imagenet classification with deep convolutional neural networks [C]// Advancesin Neural Information Processing Systems.2012: 1097-1105.   
[5]He Kaiming,Zhang Xiangyu,Ren Shaoqing,et al.Deep residual learning for image recognition [C]//Proc of the IEEE Conference on Computer Vision and Pattern Recognition.2016: 770-778.   
[6]Huang Gao,Liu Zhuang,Van Der Maaten L,et al. Densely connected convolutional networks [C]//Proc of the IEEE Conference on Computer Vision and Pattern Recognition.2017: 4700-4708.   
[7]Xie Saining，Girshick R,Dollar P,et al.Aggregated residual transformations for deep neural networks [C]// Proc of the IEEE Conference on Computer Vision and Pattern Recognition.2017:1492- 1500.   
[8]Simonyan K, Zisserman A. Very deep convolutional networks for largescaleimage recognition [EB/OL]. (2015-04-10） [2022-03-28]. https://arxiv.org/pdf/1409.1556.   
[9]Szegedy C,Liu Wei, Jia Yangqing,et al. Going deeper with convolutions [C]//Proc of the IEEE conference on Computer Vision and Pattern Recognition. 2015: 1-9.   
[10] Tan Mingxing，Le Q.Eficientnet: Rethinking model scaling for convolutional neural networks [C]// Proc of International Conference on Machine Learning. 2019: 6105-6114.   
[11] Vaswani A,Shazeer N,Parmar N,et al.Attention is all you need [C]// Advances in Neural Information Processing Systems.2017: 5998-6008.   
[12] Wang Xiaolong,Girshick R,Gupta A,et al.Non-local neural networks [C]// Proc of the IEEE Conference on Computer Vision and Patern Recognition. 2018: 7794-7803.   
[13] Zhao Hengshuang,Jia Jiaya,Koltun V.Exploring self-attention for image recognition [C]//Proc of the IEEE Conference on Computer Vision and Pattern Recognition.2020:10076-10085.   
[14] Ramachandran P,Parmar N, Vaswani A,et al. Studying standalone selfattention in vision models [EB/OL]. (2019-06-13）[2022-03-28]. https://arxiv.org/pdf/1906.05909.   
[15] Carion N,Massa F, Synnaeve G,et al.End-to-End object detection with transformers [C]// Proc of European Conference on Computer Vision. 2020:213-229.   
[16] Dosovitskiy A,Beyer L,Kolesnikov A,et al.An image is Worth 16x16 words: Transformers for image recognition at scale [EB/OL].(2021-01- 03)[2022-03-28]. https://rxiv.org/pdf/2010.11929.   
[17] Chu Xiangxiang,Tian Zhi,Zhang Bo,et al. Conditional positional encodings for vision transformers [EB/OL].(2021-05-18)[2022-03-28]. https://arxiv. org/pdf/2102.10882.   
[18] Han Kai,Xiao An,Wu Enhua,et al.Transformer in Transformer [EB/OL].(2021-10-26)[2022-03-28]. https:/arxiv.org/pdf/2103.00112.   
[19] Touvron H,Cord M,Douze M,et al.Training data-efficient image transformers & distillation through attention [C]//Proc of International Conference on Machine Learning.2021,139:10347-10357.   
[20] Yuan Li, Chen Yunpeng,Wang Tao,et al. Tokens-to-token vit: Training vision transformers from scratch on imagenet [C]// Proc of the IEEE/CVF International Conference on Computer Vision.2021:558-567.   
[21]WangWenhai,Xie Enze,Li Xiang,etal.Pyramid vision Transformer:A versatile backbone for dense prediction without convolutions [C]//Proc of the IEEE/CVF International Conference on Computer Vision.2021: 568-578.   
[22]Liu Ze,Lin Yutong,Cao Yue,et al.Swin Transformer:Hierarchical vision Transformer using shifted windows [Cl//Proc of the IEEE/CVF International Conference on Computer Vision.2021:10012-10022.   
[23] Rao Yongming,Zhao Wenliang,Liu Benlin,et al.Dynamicvit:Efficient vision transformers with dynamic token sparsification [EB/OL].(2021- 10-26)[2022-03-28]. https://arxiv.org/pdf/2106.02034.   
[24]Lin Hezheng,Cheng Xing,Wu Xiangyu,et al.CAT:Cross attention in vision Transformer [EB/OL].(2021-06-10) [2022-03-28].https://arxiv. org/pdf/2106.05786.   
[25] Wu Haiping,Xiao Bin,Codella N,et al.Cvt: Introducing convolutions to vision transformers [C]// Proc of the IEEE/CVF International Conference on Computer Vision.2021:22-31.   
[26]Dai Zihang,Liu Hanxiao,Le QV,et al. Coatnet:Marrying convolution and attention for all data sizes [C]//Advances in Neural Information Processing Systems.2021,34: 3965-3977   
[27] Chen Zhiyang,Zhu Yousong,Zhao Chaoyang,et al. Dpt: Deformable patch-based Transformer for visual recognition [Cl//Proc of the 29th ACMInternational Conference on Multimedia.2021:2899-2907.   
[28] Zhang Dong,Zhang Hanwang,Tang Jinhui,et al. Feature pyramid Transformer [C]/ Proc of the European Conference on Computer Vision. 2020:323-339.   
[29] Liu Songtao,Huang Di,Wang Yunhong.Receptive field block net for accurate and fast object detection [C]//Proc of the European Conference on Computer Vision.2018:385-400.   
[30] Bao Hangbo,Li Dong，Wei Furu,et al.Unilmv2:Pseudo-masked language models for unified language model pre-training [C]// Proc of International Conference on Machine Learning.2020: 642-652.   
[31] Hu Han,Gu Jiayuan,Zhang Zheng,et al.Relation networks for object detection [C]//Proc of the IEEE Conference on Computer Vision and Pattern Recognition.2018:3588-3597.   
[32] Raffel C,Shazeer N,Roberts A,et al.Exploring the limits of transfer learning with a unified text-to-text Transformer [J]. Journal of Machine Learning Research,2020,21(140): 1-67.   
[33] BaJL,Kiros JR,Hinton G E.Layer normalization [EB/OL].(2016-07- 21) [2022-03-28]. https://arxiv.org/pdf/1607.06450.   
[34]Deng Jia,Dong Wei,SocherR,et al. Imagenet:A large-scale hierarchical image database [Cl//Proc of the IEEE Conference on Computer Vision and Pattern Recognition. 2009: 248-255.   
[35] Graham B,El-Nouby A,Touvron H,et al.LeViT: A vision Transformer in ConvNet's clothing for faster inference [C]//Proc of the IEEE/CVF International Conference on Computer Vision.2021:12259-12269.