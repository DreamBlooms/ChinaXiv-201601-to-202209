# 基于增强特征融合网络的行人再识别

邓滔，杨娟，汪荣贵，薛丽霞(合肥工业大学 计算机与信息学院，合肥 230601)

摘要：行人再识别主要是判断不同摄像机捕捉到的行人图像是否属于同一个人。现实生活中，由于人的姿势变化，摄像头的视角变化和背景干扰等因素，导致相同的行人在不同的摄像头产生巨大的差别，这是一项艰巨的任务。近几年，基于深度学习的方法在解决行人再识别问题都取得了显著的效果。然而目前多数方法仅将行人的局部或全局特征分开考虑，从而忽略了行人整体之间的关系，即行人全局特征和局部特征之间的联系。因此，该算法提出了一种增强特征融合网络(EnhancedFeature Convergent Network，EFCN)。在全局分支中，提出适用于获取全局特征的注意力网络作为嵌入特征，嵌入在基础网络模型中以提取行人的全局特征；在局部分支中，提出循环门单元变换网络(GatedRecurrent Unit Change Network，GRU-CN)得到代表性的局部特征，再使用特征融合方法将全局特征和局部特征融合成最终的行人特征，最后借助损失函数训练网络。通过大量的对比实验，该算法网络模型在标准的Re-ID数据集上可以获得较好的实验结果。提出的增强特征融合网络能提取辩别性较强的行人特征，该模型能够应用于大场景非重叠多摄像机下的行人再识别问题，具有较高的识别能力和识别精度，且对背景变化的行人图像能提取具有较强的鲁棒性特征。

关键词：行人再识别；全局特征；局部特征；特征融合 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2020.02.0078

Enhanced feature convergent network for person re-identification

Deng Tao†, Yang Juan, Wang Ronggui, Xue Lixia (Dept.of computer& information,Hefei University of Technology,Hefei230601,China)

Abstract:Personre-identificationis to judge whether the pedestrianacrossdiferentcamerasbelongs to thesame personor not.Whileitischalenging taskduetothelarge variations inpersonpose,occusion,backgroundcluter,etc.Andseveral deep learning based person re-identification have been proposed and achieved remarkable performance.However,these methodsareonlyconsideredseparatelyfromthe localorglobalfeaturesof thepedestrian,ignoring therelationship between the features.So this paper proposed theenhanced feature convergent network (EFCN).Inthe global branch,the paper used to employ thenewatentiontopaycloseattntion totheglobalfeatureof pedestrians.Inthelocalbranch,itproposed the gated recurrentunit change network(GRU-CN)to obtain more robustlocal features,andthen this paperused feature fusion to connect theextracted global and local features.Extensivecomparative experiments show thatEFCNcanachievebetter experimentalresults onthreestandard person Re-IDdatasets.The proposed enhanced feature convergent network can extract highly discriminative pedestrian features.This modelcanbeapplied tothe problemofRe-IDunder non-overlapping multicameras inlarge scenes.Ithas highrecognition abilityand accuracy.The method can extract robust features for pedestrian images with changing background.

Key words: person re-identification; global features; local features; feature convergent

# 0 引言

行人再识别(personRe-ID)通常是行人检索的子问题，是指在无重叠视域多摄像机监控系统中，辨别两个不同摄像机捕捉到的行人图像是否属于同一个人。personRe-ID 技术可以运用在自动跟踪和检索视频监视网络中的犯罪嫌疑人，能够提高视频监视系统的性能和增加案件处理效率。考虑到行人再识别在视频监控和公共安全中的重要作用，越来越多的研究人员对此问题展开了深入研究。行人再识别主要核心是行人特征表达[1和特征距离度量。由于监控系统中行人姿势变化，摄像机角度和图片质量问题等因素变化，同一行人在不同的监控摄像头中差异很大，这些问题给行人再识别带来了巨大挑战。具体表现主要如下三个方面：

首先，被捕捉的行人图像在不同的相机中不能对齐，如图1(a)所示，对于同一个人，在不同图像的相同位置，左侧的红色方框是行人的头部，而右侧的蓝色方框是图像背景。显然，通过卷积神经网络提取的两个区域的特征图存在巨大的差距，无法直接进行比较。为了行人图像解决未对齐问题，文献[2]提出一种基于多特征子空间与核学习的方法，能够有效的识别行人身份信息；文献[3]将关键点直接用于生成感兴趣区域，然后学习行人的局部特征来实现行人的对齐，而这种方法需要训练一个可以达到实际水平的模型，其代价是非常昂贵的。因此本文通过引入注意力嵌入网络去提取行人的全局特征；再使用水平切片方法将提取的全局特征转换为三个相同的局部特征，使得行人特征可以间接对齐，实验效果得到了显著的改善。

其次，如图1(b)所示，在现实生活中，许多相机拍摄到的行人图像模糊不清，导致图片质量过低，增加了Re-ID的难度。为了解决该问题，文献[4]使用注意力机制关注局部感兴趣区域；文献[5]使用注意力机制从上到下关注局部特征，使用局部特征比较相似性，但是却忽略了全局特征的影响。此外，文献[6]提出了一种多方向显著性学习权值的行人再识别方法,学习到的特征对行人图像具有更好的表述能力，但由于必须将输入图片配对，导致计算效率较低。针对此问题，本文使用注意力机制提取全局特征，并使用水平切片获取局部特征，通过提出的循环门单元变换网络(GRU-CN)，可以着重提取行人的局部重点特征，更好地解决图像模糊问题，还可以减少背景干扰因素。

此外，如图1(c)所示，当需要区分非常相似的行人图像时，行人细节之间的差异尤为重要。文献[7]通过提取行人的全局和局部特征来捕获行人的细节，但却忽略全局特征与局部特征之间的相关性；文献[8提出了一种多级相似性度量，通过计算不同级别的相似性得分来识别行人身份，相似性得分的计算量很大。因此，本文在局部分支中提出了循环门单元变换网络(GRU-CN)，该网络可以提取更辨别性的局部特征。同时设计了一种特征融合的方法，将全局特征和局部特征更加紧密地联系在一起，得到了更具代表性的行人特征。本文方法可以更好地提取行人的细节信息，因此对细微差别行人图像的识别效果有明显提高。

![](images/929c3364f2aca131a1f5bd60d0098ee32d49a4722b1a89ef5e030642eaa8fd17.jpg)  
图1行人再识别的挑战

根据以上分析，在特征学习阶段，提出了一种增强特征融合网络(EFCN)，它具有三个分支：学习全局特征、学习局部特征和特征融合。在全局分中，本文把空间注意力和通道注意力相结合作为注意力嵌入式网络SC-Net，嵌入到ResNet50[9网络中；在局部分支中，提出了循环门单元变换网络(GRU-CN)，并使用GRU-CN来变换行人局部特征；在特征融合中，利用特征融合操作将全局特征和局部特征融合成新的特征向量。最后把三组特征向量送入损失函数去训练网络参数。

# 1 模型方法

对于一个给定的查询图像 $I _ { p }$ ，行人再识别的目标就是在候选集 $\textbf { \em G }$ 中去找出与查询图像 $I _ { p }$ 相同身份的其他图像。设候选集 $G = \{ I _ { i } \} , i \in [ 1 , . . . , c ]$ 其中 $\mathbf { \Psi } _ { c }$ 为行人图像的总数量。让训练集通过网络模型去学习到行人辨识性的特征向量 $M$ 是解决行人再识别的一种方法。在本节中，重点介绍本文提出的增强特征网络模型，如图2所示，模型主要分为三个部分，第一部分是全局特征分支，第二部分是局部特征分支，第三部分是特征融合。接下来章节，详细介绍模型的各个部分。

![](images/94e758ef730b5f7c091a550e5f3f4cfd172914166896d3a4f2afe2acbb5d270e.jpg)  
图2增强特征融合网络模型的体系结构  
Fig.2Architecture of the enhanced feature converged network

# 1.1 全局分支网络

近年来，如何利用深度学习来提取判别特征已受到研究人员越来越多的关注。本文的目的是通过网络模型学习行人的特征图，然后识别行人的身份信息。对于全局分支，利用ResNet50作为基础网络。但是由于行人再识别所面临的挑战如果仅使用基本的ResNet50网络来学习全局特征，则提取的全局特征不够代表性，同时引起干扰因素。因此，提出了一种注意力嵌入网络，称为空间和通道注意力嵌入网络(SC-Net)。既是将SC-Net与ResNet50模型结合起来，其效果能提取出更具代表性的行人全局特征，并稍微修改了ResNet50网络，在网络的第四层，删除下采样操作，以获得更大的特征图，其大小为 $2 0 4 8 ^ { * } 2 4 ^ { * } 8$ 。

接下来介绍嵌入注意力网络的组成，SC-Net目标是通过注意力机制来增强特征表现力：关注重要的特征，抑制不必要的特征。嵌入注意力网络SC-Net主要是由空间注意机制和通道注意力机制组成。由于卷积运算是将跨信道信息和空间信息混合在一起来提取特征的，因此采用该模块来强调通道和空间这两个主要维度的有意义特征。给定行人图像大小为 $3 ^ { * } 3 8 4 ^ { * } 1 2 8$ ，图像通过ResNet50网络得到相应的特征向量。假定特征向量 $\pmb { F } \in \mathbb { R } ^ { \mathrm { C } ^ { \ast } \mathrm { H } ^ { \ast } \mathrm { W } }$ ，行人图像通过 ResNet50 第一层得到浅层特征向量 $_ F$ ,其中C是通道数， $\mathrm { H ^ { * } W }$ 表示特征向量的长和宽。接下来把特征向量 $_ F$ 输到SC-Net注意力嵌入网络得到特征向量 $f \in \mathbb { R } ^ { \mathrm { C ^ { * } H ^ { * } W } }$ 。其具体结构如图3所示。

![](images/eb1fbfd9e187ebd8acbeb0eb543325cefab565b7aa2ede5a7e04f4ce9ef059fe.jpg)  
Fig.1Re-ID has some challenges   
图3SC-Net注意力嵌入网络  
Fig.3Spatial and Channel attention network

特征向量 $\pmb { F } \in R ^ { C ^ { * } H ^ { * } W }$ 直接地计算通道特征图 $M \in R ^ { C ^ { * } C }$ ，首先，改变特征向量 $F$ 的尺寸大小为 $F _ { i } \in R ^ { C ^ { * } N }$ ,其中 $N = H ^ { * } W$ ， $\boldsymbol { F } _ { i }$ 的转置定义为 $F _ { j } \in R ^ { N ^ { \ast } C }$ ，把 $F _ { i }$ 和 $F _ { j }$ 相乘，最后，利用 softmax 层提取通道注意力特征图 $M \in R ^ { C ^ { * } C }$ ：

$$
M _ { j , i } = \frac { e ^ { ( F _ { i } . F _ { j } ) } } { et { } { ' } \sum _ { i = 1 } ^ { C } e ^ { ( F _ { i } . F _ { j } ) } }
$$

其中， $\boldsymbol { M } _ { j , i }$ 是测量第 $i$ 个通道对第 $j$ 个通道的影响。接下来通道注意机制作用后的特征向量 $\boldsymbol { F ^ { \prime } }$ 为

$$
F ^ { \prime } = \alpha \sum _ { i = 1 } ^ { c } \left( M _ { j , i } F _ { i } \right)
$$

其中 $\alpha$ 为权重，是从0开始学习的，对 $\textbf { \em M }$ 和 $F$ 的转置进行矩阵相乘。其中 ${ M } _ { j , i } \in { \cal R } ^ { \scriptscriptstyle { 1 } * c }$ ， $F _ { i } \in R ^ { c * N }$ 。二者矩阵相乘得到单一通道上的值其大小 $R ^ { * N }$ ，最后把每个通道值叠加求和得到${ \pmb F } ^ { \prime } \in { \pmb R } ^ { C ^ { * } N }$ ，并将其结果重新定义为 $R ^ { C ^ { * } H ^ { * } W }$ 。它有助于提高特征的辨别性。接下来利用通道注意力提取的特征向量 $\boldsymbol { F ^ { \prime } }$ ，分别采用平均池化和最大池化两种操作得到两组特征向量，接下来将两组特征整合成一个有效的特征描述符。沿着通道方向可以有效地突出重要信息区域。然后，利用一个卷积层作用在特征描述符上，从而得到一个空间注意特征图$M _ { s } \left( F ^ { \prime } \right) \in R ^ { H ^ { * } W }$ ，式(3)给出计算过程：

$$
M _ { s } \left( F ^ { \prime } \right) = \sigma \big ( f \left( \left[ F _ { a v g } ^ { \prime } ; F _ { m a x } ^ { \prime } \right] \right) \big )
$$

其中: $\sigma$ 为sigmoid函数， $f$ 表示为卷积核为 $7 ^ { * } 7$ 的卷积操作，

$F _ { a \nu g } ^ { ' }$ 是平均池化得到大小为 $1 ^ { * } H ^ { * } W$ 的特征向量， $F _ { m a x } ^ { * }$ 是最大池化得到大小为 $1 ^ { * } H ^ { * } W$ 的特征向量。综上所述，对于特征向量 $F \in R ^ { C ^ { * } H ^ { * } W }$ ，嵌入注意力网络 SC-Net 是一个通道注意力和空间注意力的组合，其运算过程如下所示。

$$
f = M _ { s } \left( F ^ { \prime } \right) \circledast F ^ { \prime }
$$

其中: $\circledast$ 表示为特征向量的乘积运算; $F ^ { \prime }$ 为通过通道注意力优化得到的特征向量，由于嵌入注意力网络 SC-Net 是嵌入学习在ResNet50网络的前三个残差块(residualblock)后。因此，（204号 $f \in R ^ { C ^ { * } H ^ { * } W }$ 为嵌入网络层 SC-Net优化后的输出特征。接下来通过ResNet50的第四层后，获得的特征图为 $2 0 4 8 ^ { * } 2 4 ^ { * } 8$ 。然后利用平均池化获取一个2048 维特征向量，接下来通过 $^ { 1 ^ { * } 1 }$ 卷积层，批归一化和ReLU层获得512维特征向量。最后，利用三重损失函数和softmax损失函数训练了全局分支网络。

# 1.2 局部分支网络

许多方法主要研究行人的全局特征，会忽略一些行人细节信息，从而加大行人再识别的难度，于是越来越多的研究者考虑行人的局部特征。因此，本文另一个分支是局部分支网络。但是不同于其他方法，本文是利用全局分支提取到的特征向量作为基础。假定在ResNet50 的第三层中得到一个特征向量 $\pmb { F }$ ；然后利用bottleneck[9]把特征向量F映射为T，其尺寸为 $2 0 4 8 ^ { * } 2 4 ^ { * } 8$ ；然后利用简单的分块操作，把T划分成三块大小为 $2 0 4 8 ^ { * } 8 ^ { * } 8$ 相同的特征向量 $\pmb { t } _ { 1 } , \pmb { t } _ { 2 } , \pmb { t } _ { 3 }$ ；最后提出的循环门单元变换网络(gated recurrent unit change network,GRU-CN)变换得到三块局部特征。

对于本文GRU-CN网络，其主要结构是在空间转换网络(STN)[o的基础上作出相关的改进。STN已经被证明在只有一个前景目标的情况下，可以很好地关注到图像中最重要的部位，还可以自行定位到若干个不同的重要区域。但是通过实验发现STN中的归一化网络Localizationnet仅采用简单的卷积操作，不能够满足分块后的局部特征，导致不同小块的局部特征关联性不够强。另外调查研究发现循环门单元(gated recurrentunit，GRU)[1]继承了长短时记忆网络的特点，可以使得局部特征之间更具空间依赖性，同时又提高了计算能力。因此，设计将GRU网络放入归一化网络中，并且在其后加入两个全连接层，形成全新的Localizationnet。本文提出了循环门单元变换网络GRU-CN，即能获得更为重要的局部特征信息，又能保持各个局部特征之间的联系性。因此，采用GRU-CN可以在局部特征上可以得到行人的重要的区域，然后自动进行特征的对齐，从而得到更好的特征图来提高行人再识别的性能。GRU-CN网络结构具体见图4。

![](images/0ae708a6762efc8356d438aae4ae70f77a723d15c00bf2f8fe3a52bb2953a5e7.jpg)  
图4循环门单元变换网络GRU-CN 结构 Fig.4Gated recurrent unit change network

定位网络的输入是特征图 $\pmb { U } \in R ^ { C ^ { * } H ^ { * } W }$ ，其中 $c$ 为通道数，$H$ 和 $W$ 分别表示高和宽，输出是一个6维的仿射变化参数 $\theta$ ，$\theta$ 可以描述为

$$
A _ { \mathfrak { d } } = { \left[ \begin{array} { l l l } { \mathfrak { \theta } _ { 1 } } & { \ \theta _ { 2 } } & { \ \theta _ { 3 } } \\ { \ \theta _ { 4 } } & { \ \theta _ { 5 } } & { \ \theta _ { 6 } } \end{array} \right] }
$$

仿射变换允许输入的缩放、旋转和倾斜。使用定位网络预测转换参数。在网络中，定位网络Localizationnet是循环门单元和两个全连接层的组合，因此

$$
\left( { { C _ { t } } , h _ { t } } \right) = f _ { G R U } \left( U , { C _ { t - 1 } } , h _ { t - 1 } \right)
$$

$$
A _ { \ u \ u _ { \ u \ u _ { \theta } } } = \mathrm { F C } \left( h _ { \ u \tau } \right)
$$

其中: $f _ { G R U } \left( . \right)$ 为循环门单元， $U$ 是输入特征。 $F C ( . )$ 为两个全连接层。通过以上的研究，利用6维参数 $A _ { \theta }$ 来计算图像的仿射变化：

$$
{ \binom { x ^ { s } } { y ^ { s } } } = T _ { \oplus } \left( G \right) = { \left[ \begin{array} { l l l } { \theta _ { 1 } } & { \theta _ { 2 } } & { \theta _ { 3 } } \\ { \theta _ { 4 } } & { \theta _ { 5 } } & { \theta _ { 6 } } \end{array} \right] } { \left( \begin{array} { l } { x ^ { t } } \\ { y ^ { t } } \\ { 1 } \end{array} \right) }
$$

其中 $\theta _ { 1 } , \theta _ { 2 } , \theta _ { 4 } , \theta _ { 5 }$ 是尺寸和旋转参数，而 $\theta _ { 3 } , \theta _ { 6 }$ 是转变参数。式(7)中 $\left( x ^ { t } , y ^ { t } \right)$ 为输出图像的目标坐标， $\left( x ^ { s } , y ^ { s } \right)$ 为输入图像的源坐标。通过 $T _ { \theta } \left( G \right)$ 的计算，可以用如下公式得到变化后的特征图$V \in R ^ { C ^ { * } H ^ { * } W }$ ，其尺寸不变。

$$
V _ { c } = \sum _ { n } ^ { H } \sum _ { m } ^ { W } U _ { n m } ^ { c } \mathrm { ~ } ^ { * } \operatorname* { m a x } \left( 0 , 1 - \left| x ^ { s } - m \right| \right) { } ^ { * } \operatorname* { m a x } \left( 0 , 1 - \left| y ^ { s } - n \right| \right)
$$

其中 $V _ { c }$ 表示输出特征图在通道 $\mathrm { ~  ~ c ~ }$ 位置上的 $( m , n )$ 上的像素， $U _ { c }$ 表示输入特征图在通道c位置上的 $( m , n )$ 上的像素。最后需要导出 $U , x ^ { s } , y ^ { s }$ ，然后利用损失函数进行反向传播。综上所述，通过利用GRU-CN网络的变换，得到更鲁棒性的行人局部信息特征。在局部分支中，同样的通过 $1 ^ { * } 1$ 卷积层，批归一化和Relu层得到512维特征向量。最后，利用三重损失函数和softmax损失函数训练局部分支网络。

# 1.3特征融合分支

为了更加准确提高行人再识别的识别率，利用特征融合技术把提取到的局部特征和全局特征结合起来以生成更健壮的特征表示是很有必要的。研究发现，将局部特征与全局特征简单地利用concat或者add操作可能会引入特征噪声干扰在文献[12]中进行了调查研究，使用向量的外积将使提取的特征图更具表现力。因此，本文使用特征描述符融合操作(featuredescriptorfusion,FDF)来融合全局特征和局部特征。为了验证特征描述子融合操作的效果，使用了几组数据进行比较实验，详细的实验在4.4节中。假设全局分支提取到的行人特征是 $F _ { g }$ ，其中 $F _ { g } \in R ^ { C ^ { * } H ^ { * } W }$ ，局部分支提取的特征表示为$t _ { 1 } , t _ { 2 } , t _ { 3 }$ ,则将三个局部特征利用concat得到局部特征向量 $F _ { l }$ ，其中 $F _ { l }$ 的大小与全局特征 $F _ { g }$ 相同。现做以下说明， $\alpha _ { x y }$ 表示为全局特征 $F _ { g }$ 中的点 $( \mathbf { x } , \mathbf { y } )$ 的特征描述符，而 $\beta _ { x y }$ 被表示为局部特征 $F _ { l }$ 中的点 $( \mathbf { x } , \mathbf { y } )$ 的特征描述符。特征描述符融合操作主要使用外部乘积来组合提取的全局特征 $F _ { g }$ 和局部特征 $F _ { l }$ 。因此，在 $F _ { g }$ 和 $F _ { l }$ 上融合的到融合特征向量 $\mathbf { M }$ 。具体操作如下：

$$
M _ { x y } = T ( \alpha _ { x y } \odot \beta _ { x y } )
$$

$$
\tilde { \mathbf { M } } = \frac { 1 } { S } \sum _ { x y } M _ { x y }
$$

$$
\mathbf { M } = \frac { \tilde { M } } { \tilde { M } _ { \mathrm { \Omega } } }
$$

其中: $\odot$ 表示向量的外积， $T ( . )$ 是把矩阵转换成向量，S是空间大小，其大小即 $H ^ { * } W$ 。最终，利用式(11)归一化得到融合特征向量 $\mathbf { M }$ 。特征描述符融合操作把局部特征和全局特征融合为2048维特征向量。接下来使用softmax损失函数来优化特征融合阶段的学习网络参数。在本文网络中，仅在GRU-CN 网络使用了dropout[13]策略。最后，将从三个分支提取的特征向量相融合形成行人图像的特征向量。

# 1.4损失函数

对于全局分支和局部分支来说，二者共用同一个损失函数。总损失函数是改进的三重损失函数和分类损失函数之和。即

$$
\mathrm { L o s s } = L _ { s } + l o s s _ { s m b }
$$

对于 $L _ { s }$ 是分类损失函数，其具体表示为

$$
L _ { s } \left( x _ { i } \right) = \sum _ { i = 1 } ^ { T } - y _ { i } l n f \left( x _ { i } \right)
$$

其中 $y _ { i }$ 为预测标签， $T$ 为行人的类别， $f \left( . \right)$ 为分类函数。而$l o s s _ { s m b }$ 是改进的三元组损失函数[9]，其具体表达式为

$$
l o s s _ { s m b } \left( \mu ; X \right) = \sum _ { i = 1 } ^ { M } \sum _ { a = 1 } ^ { N } \ln \left( 1 + e ^ { \left( d _ { m , a , n } ^ { i , a , p } \right) } \right)
$$

$$
d _ { m , a , n } ^ { i , a , p } = \operatorname* { m a x } _ { p = 1 , . . . N } D i s \left( y _ { \mu } \left( x _ { a } ^ { i } \right) , y _ { \mu } \left( x _ { p } ^ { i } \right) \right) - \operatorname* { m i n } _ { \stackrel { m = 1 . . . M } { m = 1 . . . N } } D i s \left( y _ { \mu } \left( x _ { a } ^ { i } \right) , y _ { \mu } \left( x _ { n } ^ { m } \right) \right)
$$

其中: $M$ 表示行人的类别， $N$ 表示为每个行人的图像数量，那么 $M ^ { * } N$ 就表示在一个批次中有 $M ^ { * } N$ 个三元组。对于 $d _ { m , a , n } ^ { i , a , p }$ 表示为批次中最难三元组损失函数，其中 $\operatorname* { m a x } _ { p = 1 , . . . N } D i s ( . )$ 是挑选出正样本中最难的样本； $\operatorname* { m i n } _ { p  \dots N } D i s ( . )$ 则是挑选出负样本对中最难的样本，其中 $D i s ( . )$ 是欧式距离函数，也就是说，对于每个样本 $x _ { a } ^ { i }$ ，其中 $\boldsymbol { x } _ { p } ^ { i }$ 是相同行人中对于 $x _ { a } ^ { i }$ 的最大距离的图像， $x _ { n } ^ { m }$ 是不同行人中最小距离的图像。因此，一个三元组包括 $\boldsymbol { x } _ { a } ^ { i } , \boldsymbol { x } _ { p } ^ { i } , \boldsymbol { x } _ { n } ^ { m }$ ，$l o s s ( \mu ; X )$ 是一个批次中所有三元组图像的损失函数之和。对于特征融合分支，把融合后的特征向量送入softmax分类损失函数中，该损失函数就是式(13)所示。

# 2 实验结果

在本文实验中，验证模型在行人再识别数据集：Market1501、CUHK03和DukeMTMC-reID上测试。为了使实验简单快捷，所有的实验都是在单查询图像中进行的。本文的网络模型利用pytorch 深度学习框架，用NVIDIAGeForceGTX1080iGPU，Inteli7CPU和内存32GB训练网络模型。本文采用adam[14]优化算法来优化模型，adam是随机梯度下降算法的扩展式。本文随机地把样本分为若干个批次，每批的训练样本的数量为16张，每批的测试样本为16张。在预处理阶段，对图像进行初始化处理，使得输入图像大小变为 $3 8 4 ^ { * } 1 2 8$ ，然后利用数据增强方法。本文利用随机水平翻转和标准化对样本进行增强。在训练阶段，开始先把学习率初始化为1e-3，然后在100个周期后衰减到1e-4，在300个周期后进一步衰减到1e-5。整个训练过程共达到400个周期，共消耗了8-10小时使得模型达到拟合状态。

在Market1501数据集上评估：在表1中展示了Market1501数据集的实验结果。将其与近年来最先进的方法进行比较，例如度量学习方法：LOMO $^ +$ XQDA[15], ${ \mathrm { B o W } } +$ KISSME[16]；属性识别学习方法APR[17]；深度学习方法：GLOB-TO-LOCAL[7]，PCB[18]和PCB-RPP[18]；使用注意力机制的学习方法：MSCAN[19]，HA-CNN[20]；与当前最新的主力DMA-CN[21]、Pose[22]算法。从表1可以看出，本文方法明显优于度量学习方法。与深度学习方法相比，不需要先验知识，Rank-1的准确率可以达到 $94 . 4 \%$ 。与PCB-RPP 相比，相同的使用注意模型用于辅助学习功能，相比该方法本文的mAP增加了 $2 . 2 \%$ 。本文同样设置一个基本网络模型 baseline,它是以ResNest-50网络模型，其mAP和rank-1达到分别达到 $71 . 5 9 \%$ 和 $8 8 . 8 4 \%$ 。从表中可以明显看出，本文方法分别比MSCAN和HA-CNN的rank-1精度高 $14 . 1 \%$ 和 $3 . 2 \%$ 。同样，将重排序方法RK与本文方法结合使用，可以使rank-1达到 $9 5 . 2 \%$ ，mAP达到 $93 . 1 \%$ 。

在CUHK03数据集上评估：CUHK03数据集是一个具有挑战性的数据集，因为其数据集中存在许多障碍，许多方法均未达到预期的结果。将对实验的结果呈现在表2中，并与两组方法进行比较。一方面是低级特征提取方法，另一方面是深度学习方法。在比较方法中，可以清楚地发现，本文方法比低级特征提取方法有显着改进。本文方法在CUHK03-detected数据集上的两个评估指标分别为 $61 . 9 \%$ 和 $65 . 3 \%$ 。与 $\mathrm { P C B } + \mathrm { R P P }$ 方法相比，Rank-1增加了 $2 . 5 \%$ ，mAP增加了$5. 2 \%$ 。在以CUHK03-labe1数据集中，实验准确性分别达到$6 5 . 0 \%$ 和 $67 . 6 \%$ 。重新排序也与本文方法相结合，实验结果见表2。

表1在Market1501数据集上的实验结果Tab.1Experimental results on the Marketl501 dataset  

<html><body><table><tr><td>网络模型</td><td>rank-1</td><td>rank-5</td><td>rank-10</td><td>mAP</td></tr><tr><td>LOMO+XQDA</td><td>43.7</td><td>-</td><td></td><td>22.2</td></tr><tr><td>BoW+KISSME</td><td>44.4</td><td>63.9</td><td>72.2</td><td>20.8</td></tr><tr><td>APR</td><td>87.04</td><td>95.10</td><td>96.42</td><td>66.89</td></tr><tr><td>GLOB-TO-LOCAL</td><td>89.9</td><td>-</td><td>-</td><td>73.9</td></tr><tr><td>PCB</td><td>92.3</td><td>97.2</td><td>98.2</td><td>77.4</td></tr><tr><td>PCB+RPP</td><td>93.3</td><td>97.4</td><td>98.2</td><td>80.9</td></tr><tr><td>MSCAN</td><td>80.3</td><td>-</td><td>-</td><td>57.5</td></tr><tr><td>HA-CNN</td><td>91.2</td><td>-</td><td></td><td>75.7</td></tr><tr><td>DMA-CN</td><td>88.93</td><td></td><td></td><td>70.48</td></tr><tr><td>Pose</td><td>84.3</td><td></td><td></td><td>63.2</td></tr><tr><td>baseline(ResNet50)</td><td>88.84</td><td>-</td><td>-</td><td>71.59</td></tr><tr><td>本文</td><td>94.4</td><td>98.0</td><td>98.6</td><td>83.1</td></tr><tr><td>本文+RK</td><td>95.2</td><td></td><td></td><td>93.1</td></tr></table></body></html>

表2在CUHK03数据集上的实验结果

Tab.2Experimental results on the CUHKo3 dataset   

<html><body><table><tr><td>CUHK03-detected</td><td>mAP</td><td>rank-1</td><td>CUH03- label</td><td>mAP</td><td>rank-1</td></tr><tr><td>LOMO+XQDA</td><td>11.5</td><td>12.8</td><td></td><td>13.6</td><td>14.8</td></tr><tr><td>BoW+KISSME</td><td>11.7</td><td>14.4</td><td></td><td>12.3</td><td>14.2</td></tr><tr><td>IDE</td><td>19.7</td><td>21.3</td><td></td><td>21.0</td><td>22.2</td></tr><tr><td>PCB</td><td>54.2</td><td>61.3</td><td></td><td></td><td>1</td></tr><tr><td>PCB+RPP</td><td>56.7</td><td>62.8</td><td></td><td>1</td><td>-</td></tr><tr><td>HA-CNN</td><td>38.6</td><td>41.7-</td><td></td><td>41.0</td><td>44.4</td></tr><tr><td>baseline(ResNet50)</td><td>59.3</td><td>62.1</td><td></td><td>62.3</td><td>64.8</td></tr><tr><td>本文</td><td>61.9</td><td>65.3</td><td></td><td>65.0</td><td>67.6</td></tr><tr><td>本文+RK</td><td>72.6</td><td>73.3</td><td></td><td>75.4</td><td>76.7</td></tr></table></body></html>

在DukeMTMC-reID数据集上评估：将本文方法与DukeMTMC-reID数据集上已经获得的一些成果的方法进行比较，例如：IDE[1]，ARP，HA-CNN, $\mathrm { P C B } + \mathrm { R P P }$ ，DMA-CN,Pose。实验结果列于表3。本文实验效果mAP可达到 $72 . 9 \%$ ，Rank-1为 $86 . 8 \%$ 。与更好的GP-ReID[23]方法相比，尽管mAP并没有得到改善，但这可能是由于错误造成的，但是本文的Rank-1增加了 $1 . 6 \%$ 。在此数据集中，本文的方法超越了一些更经典的方法。采用RK法，mAP的实验效果达到 $86 . 8 \%$ ，Rank-1达到 $89 . 7 \%$ 。

表3在DukeMTMC-reID数据集上的实验结果  
Tab.3Experimental results on the dukemtmc-reid dataset   

<html><body><table><tr><td>网络模型</td><td>mAP</td><td>rank-1</td><td>网络模型</td><td>mAP</td><td>rank-1</td></tr><tr><td>IDE</td><td>47.1</td><td>67.7</td><td>DMA-CN</td><td>61.73</td><td>78.57</td></tr><tr><td>ARP</td><td>55.56</td><td>73.92</td><td>Pose</td><td>60.5</td><td>78.4</td></tr><tr><td>PCB+RPP</td><td>69.2</td><td>83.3</td><td>baseline(ResNet50)</td><td>65.1</td><td>79.4</td></tr><tr><td>HA-CNN</td><td>63.8</td><td>80.5</td><td>本文</td><td>72.8</td><td>86.8</td></tr><tr><td>GP-ReID</td><td>72.8</td><td>85.2</td><td>本文+RK</td><td>86.8</td><td>89.7</td></tr></table></body></html>

# 3 实验分析

为了验证本文提出来的各种方法的有效性，接下来在Market1501数据集上做了相关的消融实验，利用baseline 模型去验证各个网络部分的正确性。

# 3.1注意力机制网络对实验的影响

对于注意力网络，本文利用四组实验对比证明SC-Net的有效性，如表4所示.可以明显的发现单独的通道注意力和空间注意力都可以提高实验结果。因为注意力机制被证明能够很好的关注行人的重要信息，减少背景干扰。但是单独的使用通道注意力和空间注意力可能会导致部分行人信息的丢失，从而降低了识别率。而本文提出的SC-Net，是从空间和通道两个方面入手，既保持了特征的空间不变性又重点考虑了图像的通道信息，因此，二者结合的注意力机制不仅可以关注重要信息，而且也不会过多的丢失行人图像的信息。综上所述，合并后的嵌入注意力网络SC-Net可以有助于提取行人的全局特征，提高识别准确率。

[ab.4Experimental results of the attention mechanism network   

<html><body><table><tr><td>网络模型</td><td>mAP</td><td>rank-1</td></tr><tr><td>baseline(ResNet50)</td><td>71.59</td><td>88.84</td></tr><tr><td>baseline+spatial</td><td>74.61</td><td>89.31</td></tr><tr><td>baseline+channel</td><td>73.85</td><td>89.10</td></tr><tr><td>baseline+SC-Net</td><td>78.65</td><td>91.34</td></tr></table></body></html>

# 3.2局部特征变换网络对实验的影响

通过实验数据表5来证明本文的循环门单元变换网络GRU-CN的优越性，通过三组对比实验，明显地得出结论，LSTM-STN或者STN网络作用在局部分支上，都可以提高实验的效果；但是本文提出的GRU-CN，相比较STN网络mAP提高了 $2 . 1 2 \%$ ,Rank-1提高了 $0 . 5 2 \%$ 对比LSTM-STN，本文的GRU-CN实验结果有微弱的提高。因为相比LSTM，本文的GRU提高了模型的计算能力,如果只是对GRU和LSTM来说的话，一方面GRU的参数更少，因而训练稍快或需要更少的数据来泛化。另一方面，如果你有足够的数据，LSTM的强大表达能力可能会产生更好的结果。但是行人再识别的数据集的一个缺点就是样本数据的缺少，因此本文的GRU-CN比LSTM-STN有轻微的提高。通过实验不难发现，STN网络可以不需要关键点的标定，能够根据分类或者其他任务自适应地将数据进行空间变换和对齐，在输入数据在空间差异较大的情况下，这个网络可以加在现有的卷积网络中，提高分类的准确性。而本文的GRU-CN网络一方面保持了STN网络的特征对齐性，另一方面使得分块的局部特征产生了联系，更符合行人的整体性信息。因此，GRU-CN网络作用于局部分支可以提高实验的效果。

表5不同变换网络的测试结果  
Tab.5Experimental results of different transformer network   
Tab.6Experimental results of number of patches   

<html><body><table><tr><td>网络模型</td><td>mAP</td><td>rank-1</td></tr><tr><td>baseline(ResNet50)</td><td>71.59</td><td>88.84</td></tr><tr><td>baseline+STN</td><td>73.14</td><td>89.66</td></tr><tr><td>baseline+LSTM-STN</td><td>75.26</td><td>90.18</td></tr><tr><td>baseline+GRU-CN</td><td>75.98</td><td>91.69</td></tr></table></body></html>

# 3.3分块对实验的影响

本文在局部分支利用水平切分的方法，把提取到的全局特征分为三块局部特征，为了简单的验证本文采用分块数量的有效性，同样地使用几组对比实验来验证分块个数对实验的影响，其实验结果见表6，从表格中可以明显的得出以下结论。利用分块技术提取行人的局部特征可以提高baseline的识别率。但是不同分块数量带来不一样的结果，本文采用的切分成三块的局部特征效果最好。对于切分成两块的局部特征虽然有所提高，但是有可能提取不到行人的细节信息；而采用四块的局部特征会导致行人图像分割过细，引入了背景干扰因素，从而降低了实验结果。因此，利用水平切分成三块的局部特征使得实验能呈现较好的结果。

# 3.4特征融合技术对实验的影响

对比基础网络Baseline,使用全局分支和局部分支的结合，会使得实验结果有明显的提高，实验结果如表7所示。同样地为了验证特征描述符融合技术的准确性，本文在表7中展示了多组对比实验。表7通过与三种融合方法对比：concat操作、fisher vector(FV)[24]、bilinear[25]。相比简单的 concat 操作，本文方法FDF的mAP和Rank-1分别提高了 $2 . 9 4 \%$ 和$3 . 1 3 \%$ ，对比当前主流的融合特征方法 fishervector(FV)和bilinear,本文方法FDF的实验结果都有轻微的提高。本文的FDF方法是从图像的基本点出发，其融合手段保留了特征向量的原始信息，不会像其他融合方法降低了特征的信息。因此，可以得出结论：使用特征描述符融合方法FDF有利于提高特征融合后的结果，并且FDF方法能够提取更有区分度的行人特征向量。

表4注意力机制网络的测试结果  
表6分块数量的实验结果  

<html><body><table><tr><td>网络模型</td><td>mAP</td><td>rank-1</td></tr><tr><td>baseline(ResNet50)</td><td>71.59</td><td>88.84</td></tr><tr><td>baseline+2 patches</td><td>76.37</td><td>89.55</td></tr><tr><td>baseline+3 patches</td><td>78.34</td><td>92.41</td></tr><tr><td>baseline+4 patches</td><td>78.21</td><td>91.07</td></tr></table></body></html>

表7特征融合技术的实验结果

Tab.7Experimental results of feature fusion   

<html><body><table><tr><td>网络模型</td><td>mAP</td><td>rank-1</td></tr><tr><td>baseline(ResNet50)</td><td>71.59</td><td>88.84</td></tr><tr><td>global+local</td><td>78.1</td><td>90.4</td></tr><tr><td>global+local+concat</td><td>80.06</td><td>90.87</td></tr><tr><td>global+local+FV</td><td>80.98</td><td>91.5</td></tr><tr><td>global+local+bilinear</td><td>81.46</td><td>92.43</td></tr><tr><td>global+local+本文(FDF)</td><td>83.1</td><td>94.4</td></tr></table></body></html>

最后，利用三组实验图片，在图5中，展示了本文在三个Re-ID数据集上的可视化结果，第一列中是待查询图像。根据相似度分数从左到右依次对检索到的图像进行排序。蓝色矩形表示正确匹配的行人，红色矩形表示错误匹配的行人。排序列表的图像是通过本文网络模型获取的。其中Market1501和DukeMTMC-reID 数据集上的识别率都很高;在Cuhk03数据集中，在第一组中，查询图像只有五个图像，因此第六个图像不匹配。第二组与行人图片太相似。本文方法产生错误识别，但是在误差范围之内。因此，本文增强特征网络可以较好的识别出行人身份信息。

![](images/c0531929c2e4e678a4f57092b13a9c8846acb0edf28e588da2a1de05a938dcaf.jpg)  
图5在三个数据集上的检索样例Fig.5Sample retrieval results on the three datasets

# 4 结束语

在本文中，提出了一种增强特征融合网络(EFCN)实现行人再识别。该网络模型可以有效的解决行人再识别行人姿态变化，模糊图像和相似图片等问题。本文将ResNet50网络作为基本模型，总体网络模型主要分成三个分支：全局分支，局部分支和特征融合分支。在全局分支中利用注意力网络SC-Net作为嵌入网络，作用在ResNet50网络的前三层后，该嵌入网络SC-Net与基础网络结合起来能提取到更具表示性的行人全局特征；在局部分支中，主要利用循环门单元变换网络 GRU-CN(gated recurrent unit change network)提取行人重要的局部信息；在特征融合分支，把提取到的全局特征和局部特征利用特征融合方法融合得到鲁棒性和代表性的行人特征，最后利用损失函数训练网络模型。为了验证实验效果，网络模型在三个行人再识别数据集上进行结果评估。通过和不同主流方法相比，其实验效果在三个数据集上都有明显的提高。

# 参考文献：

[1]贵睨烨，徐森，王俊．行人步态的特征表达及识别[J].模式识别与 人工智能,2012,25(1):000071-81.(Ben Xianye,Xu Sen,Wang Jun. Review on pedestrian gait feature expression and recognition [J].Pattern Recognition and Artificial Intelligence,2012,25 (1): 000071-81.)   
[2] 齐美彬，颤胜顺，王运侠，等．基于多特征子空间与核学习的行人再 识别[J]．自动化学报，2016,42(2):299-308.(QiMeibin，Tan Shengshun,Wang Yunxia,et al. Multi-feature Subspace and Kernel Learning for Person Re-identification [J]．ACTA AUTOMATICA SINICA,2016,42 (2): 299-308.)   
[3] Zhao Haiyu, Tian Maoqing,Sun Shuyang,et al. Spindle net: person reidentification with human body region guided feature decomposition and fusion [C]// Proc of IEEE the European Conference on Computer Vision (ECCV).2017: 907-915.   
[4] Zhao Rui,Wanli Ouyang,Wang Xiaogang.Person re-identification by salience matching [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition(CVPR) .2013:2528-2535.   
[5]Liu Hao,Feng Jiashi,Qi Meibin,et al.End-to-End comparative attention networks for person re-identification [C]// Proc of IEEE the 26th Transactions on Image Processing.2017: 3492-3506.   
[6]陈莹，霍中花．多方向显著性权值学习的行人再识别[J]．中国图像 图形学报，2015,20(12):1674-1683.(Chen Ying,Huo Zhonghua. Person re-identification based on multi-directional saliency metric learning [J].Journal of Image and Graphics,2015,20 (12):1674-1683.)   
[7]Wei Longhui, Zhang Shiliang,Yao Hantao,et al. GLAD:Global-localalignment descriptor for pedestrian retrieval [C]//Proc of the 25th ACM International Conference on Multimedia.2017: 420-428.   
[8] Guo Yiluan，Ngai-Man Cheung.Efficient and deep person reidentification using multi-level similarity [C]// Proc of IEEE on Computer Vision and Pattern Recognition (CVPR) .2018: 2335-2344.   
[9]He Kaiming，Zhang Xiangyu,Ren Shaoqing,et al.Deep residual learning for image recognition [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition(CVPR) .2016: 770-778.   
[10] Jaderberg M,Simonyan K,and Zisserman A,et al. Spatial transformer networks [Cl// Proc of the 28th International Conference on Neural Information Processing Systems.2015:2017-2025.   
[11] Cho K,Van Merrienboer B,Gulcehre C,et al.Learning phrase representations using RNN encoder-decoder for statistical machine translation [C]//Proc ofthe Conference on Empirical Methods in Natural Language Processing (EMNLP).2014: 1724-1734.   
[12] Gao Yang,Oscar B, Zhang Ning,et al. Compact Bilinear Pooling [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition (CVPR).2016: 317-326.   
[13] Srivastava N., Hinton G. Krizhevsky E,et al. Dropout: a simple way to prevent neural networks from overfitting [J]. Journal of Machine Learming Research.2014,15 (1): 1929-1958.   
[14] Zheng Liang, Yang Yi, Hauptmann A G. Person re-identification: past, present and future [J].2016,arXiv preprint: 1610. 02984.https://rxiv. org/abs/1610.02984.   
[15] Liao Shengcai; Hu Yang; Zhu Xiangyu,et al.Person re-identification by local maximal occurrence representation and metric learning [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition (CVPR).2015: 2197-2206.   
[16] Zheng Liang，Shen Liyue,Lu Tian，et al.Scalable person reidentification: a benchmark [C]//Proc of IEEE International Conference on Computer Vision (ICCV) .2015: 1116-1124.   
[17] Lin Yutian, Zheng Liang, Zheng Zhedong,et al. Improving person reidentification by attribute and identity learning [J]. pattern recognition 95. 2019: 151-161.   
[18] Sun Yifan,Zheng Liang,Yang Yi,et al.Beyond part models:Person retrieval with refined partpooling [C]//Proc of the International Conference on European Conference on Computer Vision (ECCV) .2018: 501-518.   
[19]Li Dangwei, Chen Xiaotang,Zhang Zhang,et al. Learning deep contextaware features over body and latent parts for person re-identification [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition (CVPR).2017: 7398-7407.   
[20] Li Wei, Zhu Xiatian, Gong Shaogang.Harmonious attention network for person re-identification [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition (CVPR) .2018:2285-2294.   
[21] 刘畅，邱卫根，张立臣．基于可变形掩膜对齐卷积模型的行人再识 别[J].计算机工程与应用,2020(03）.htp://dx.doi.org/10.3778. (Liu Chang,Qiu Weigen, Zhang Lichen.Person re-identification based on deformable mask alignment convolution model [J]. Computer Engineering and Applications,2020 (03). htp://dx.doi.org/10.3778.)   
[22]裴嘉震，徐曾春，胡平．融合视点机制与姿态估计的行人再识别方 法[J]．计算机科学，2020（02）．http://x.doi.org/10. 11896/2019/500013.(Pei Jiazhen, Xu Zengchun,Hu Ping.Person reidentification fusing viewpoint mechanism and pose estimation [J]. Computer Science，2020（02) http://dx.doi.org/10. 11896/2019/500013.)   
[23] Ahmed E,Jones M, Marks TK.An improved deep learning architecture for person re-Identification [C]// Proc of IEEE Conference on Computer Vision and Paterm Recognition (CVPR) .2015: 3908-3916.   
[24] Sanchez J,Perronnin F,Mensink T,et al. Image classification with the fisher vector: theory and practice [J]. International Journal of Computer Vision. 2013,105 (3): 222-245.   
[25] Lin T,Roychowdhury A,Maji S,et al.Bilinear CNN Models for FineGrained Visual Recognition [C]//Proc of the international conference on computer vision (ICCV) .2015: 1449-1457.