# 基于多尺度残差网络的单应估计方法

唐云1，帅鹏飞1，蒋沛凡¹，邓 飞1，杨强1,2(1.成都理工大学 计算机与网络安全学院(牛津布鲁克斯学院)，成都 610059;2.成都信息工程大学 控制工程学院.成都 610225)

摘要：单应估计是许多计算机视觉任务中的一个基础且重要的步骤。传统单应估计方法基于特征点匹配，难以在弱纹理图像中工作。深度学习已经应用于单应估计以提高其鲁棒性，但现有方法均未考虑到由于物体尺度差异导致的多尺度问题，因此精度受限。针对上述问题，提出了一种用于单应估计的多尺度残差网络。该网络能够提取图像的多尺度特征信息，并使用多尺度特征融合模块对特征进行有效融合，此外还通过估计四角点归一化偏移进一步降低了网络优化难度。实验表明，在MS-COCO数据集上，该方法平均角点误差仅为0.788个像素，达到了亚像素级的精度，并且在 $9 9 \%$ 情况下能够保持较高的精度。由于综合利用了多尺度特征信息且更容易优化，该方法精度显著提高，并具有更强的鲁棒性。

关键词：单应估计；多尺度残差网络；特征融合；四角点归一化偏移；平均角点误差中图分类号：TP183;TP751 doi: 10.19734/j.issn.1001-3695.2022.03.0124

Homography estimation method based on multi-scale residual network

Tang Yun1, Shuai Pengfeilt,Jiang Peifanl,Deng Feil, Yang Qiang1,2 (1.CollegeofComputer&NetworkSecurity(OxfordBrookesColege),ChengduUniversityofTechnology,Chengdu60059, China;2.CollgeofControlEngineering,Chengdu Universityof Information Technology,Chengdu610225,China)

Abstract: Homography estimation is a basic and important step in many computer vision tasks.Traditional homography estimation methods are based on feature point matching,whichare dificult to work in weak texture images.Deep learning has beenappliedtohomography estimationtoimprove itsrobustess,buttheexisting methods do notconsiderthe multi-scale problemcaused byobject scalediferences,resulting in limited acuracy.To solvethe above problems,this paper proposesa multi-scaleresidual network forhomography estimation.The network can extractthe multi-scale featureof the image,and used the Multi-ScaleFeatureFusion Moduletoeffectivelyfusethefeatures.Inaddition,itfurtherreduced thedifficultyof network optimizationby estimating the four-corer normalized offset.Experiments on MS-COCOdataset showed that the averagecorner errorofthis methodwas only0.788 pixels,whichachievedsub-pixelaccuracy,andcan maintainhighaccuracy in $9 9 \%$ of cases.Due to the comprehensive utilization of multi-scale features and easier to optimize,this method had significantly improved accuracy and stronger robustness.

Keywords: homographyestimation; multi-scale residual network; feature fusion; four-corner normalized ofset;average corner error

# 0 引言

单应(homography)指从一个平面到另一个平面的可逆映射，这种映射关系可以使用一个 $3 \times 3$ 的非奇异矩阵来表示，其中包含了平移、缩放、旋转与透视，称为单应矩阵[I]。给定两幅图像，从中估计这两幅图像之间的单应变换是计算机视觉中常见的需求。单应估计具有广泛的应用场景，是图像配准[2]、图像拼接[3]、图像矫正[4]、三维重建[5]以及SLAM[6]等任务中的基础性工作，单应估计的精度对于这些任务有十分重要的影响。

传统的单应估计方法通常是基于特征点匹配的。它使用SIFT[7]、SURF[8]或ORB[9]等算法提取图像中的特征点，通过暴力匹配或 FLANN[10]等匹配方法获得两组特征点的对应关系，最后利用RANSAC[I]算法剔除错误匹配后求解得到单应矩阵。然而这种方法的效果很大程度上依赖于特征点的数量与分布，难以应用于弱纹理图像中，并且步骤比较繁琐许多超参数都需要人工指定[2]。

随着深度学习的兴起，基于深度学习的单应估计方法被相继提出。2016年DeTone等人[2]首次提出了一种基于VGG架构的网络用于单应估计，显示了深度学习方法在单应估计中的潜力；2017年 Nowruzi 等人[13]使用一种分层堆叠的网络，通过堆叠多个相同网络模块来逐步细化估计结果；Nguyen等人[14]提出了单应估计的无监督学习方法；2020 年Zhang等人[15]以残差网络为主干，并使用内容掩码来选择可靠的区域进行单应估计。这些方法均取得了一定的效果，但都忽略了单应估计的多尺度性。在单应估计中，两次拍摄的照片由于相机的位置、距离和角度的不同，导致两张图像中的同一物体可能具有不同的尺度，而上述网络模型均未考虑到这一点，采用了单一尺度的特征进行单应估计，因此具有一定的局限性。

为了解决单应估计中存在的多尺度问题，同时也受到SKNet[16在多尺度特征融合方式上的启发，本文提出了一种多尺度残差单应估计网络(Multi-scale ResidualHomographyEstimationNetwork，MRHENet)来进行单应估计。该网络主要创新点有：a)使用不同感受野的卷积层提取多尺度特征进行单应估计；b)提出多尺度特征融合模块(Multi-ScaleFeatureFusionModule，MFFModule)来有效融合多尺度特征；c)不直接估计四角点绝对像素偏移[12]，而是估计四角点归一化偏移。在MS-COCO 数据集[17]与 Apolloscape 数据集[18]上的实验结果表明本文方法优于现有方法。其中，在MS-COCO数据集上，本文方法平均角点误差[12]仅为0.788个像素，与文献[12]和[15]相比，误差分别降低了 $8 5 . 0 \%$ 和 $5 9 . 4 \%$ 因此该方法精度显著提高，并且具有更强的鲁棒性。

# 1 基本原理

# 1.1传统单应估计方法原理

假设通过针孔相机模型对同一平面上的物体进行两次拍摄获得一对图像A和B，那么图像A和B存在单应变换的关系。使用 $3 \times 3$ 的非奇异单应矩阵 ${ \pmb H }$ 来表示这种关系，那么根据单应矩阵的定义[I]，可得单应变换式(1)：

$$
{ \left[ \begin{array} { l } { x ^ { \prime } } \\ { y ^ { \prime } } \\ { 1 } \end{array} \right] } = \pmb { H } \cdot { \left[ \begin{array} { l } { x } \\ { y } \\ { 1 } \end{array} \right] } = { \left[ \begin{array} { l l l } { h _ { 1 1 } } & { h _ { 1 2 } } & { h _ { 1 3 } } \\ { h _ { 2 1 } } & { h _ { 2 2 } } & { h _ { 2 3 } } \\ { h _ { 3 1 } } & { h _ { 3 2 } } & { h _ { 3 3 } } \end{array} \right] } \cdot { \left[ \begin{array} { l } { x } \\ { y } \\ { 1 } \end{array} \right] }
$$

式(1)中单应矩阵 $\pmb { H }$ 将图像A上的点 $( x , y )$ 映射到另一图像B上的 $( x ^ { ' } , y ^ { ' } )$ 。将式(1)变换后，可得2个线性方程：

$$
\mathrm { x } ^ { \prime } = \frac { h _ { I I } x + h _ { I 2 } y + h _ { I 3 } } { h _ { 3 I } x + h _ { 3 2 } y + h _ { 3 3 } } \ ; \mathrm { y } ^ { \prime } = \frac { h _ { 2 I } x + h _ { 2 2 } y + h _ { 2 3 } } { h _ { 3 I } x + h _ { 3 2 } y + h _ { 3 3 } }
$$

在单应矩阵 $\pmb { H }$ 中， $h _ { 3 3 }$ 为非零的缩放系数，一般为1,因此只有8个自由度。根据式(2)，1组匹配点对可得2个线性方程，因此最少只需要4组匹配点对即可求解单应矩阵，唯一的限制是这4组匹配点对中来自同一图像的点需要满足任意3点不共线[1]。

$$
H = \left\{ \begin{array} { l l } { \mathcal { D } \mathrm { \ddot { t } } 2 \mathrm { \neq } \frac { \mathrm { \neq } 4 } { \mathrm { \neq } 4 } \quad } & { , n < 4 } \\ { f _ { D L T } ( C o r n e r s _ { \mathrm { A } } , C o r n e r s _ { B } ) } & { , n = 4 } \\ { f _ { L S } \mathrm { \ ( } C o r n e r s _ { \mathrm { A } } , C o r n e r s _ { B } ) } & { , n > 4 } \end{array} \right.
$$

单应矩阵求解方法如式(3)所示，其中CornerSA、CornersB分别表示对两图提取的匹配特征点坐标， $n$ 表示匹配点对的数量。匹配点对若少于4组，则无法求解；若只有4组，则可以使用直接线性变换法(DirectLinearTransformation，DLT)求解单应矩阵；若多于4 组，则可以使用最小二乘法(LeastSquares，LS)求解。

传统单应估计方法步骤如下：a)通过特征点检测算法从待估计的两图中获取特征点。b)使用特征点匹配算法以建立两组特征点之间的对应关系。c根据对应关系来求解单应矩阵。针对特征点检测算法，目前已有大量研究：文献[7]提出SIFT算法，匹配精度高，但算法复杂度较高，运算时间长；文献[8]对 SIFT 算法运算速度进行了改进，提出 SURF算法；文献[9]提出了ORB 算法，计算效率较高但质量不如SIFT算法。特征点匹配可使用暴力匹配或FLANN[I0]等方法。由于可能存在误匹配的特征点对，在求解单应矩阵时，还需要使用RANSAC[1]算法排除误匹配的离群值。

传统单应估计方法依赖于特征点检测质量与分布。实际中，为了达到理想精度而选择的特征点检测算法速度通常较慢，并且对于弱纹理图像，往往难以找到足够多的匹配点对来求解单应矩阵，导致误差很大甚至无法求解。因此，传统单应估计方法鲁棒性较弱，在实际使用时有诸多限制。

# 1.2深度学习单应估计方法原理

基于深度学习的单应估计是指通过深度学习方法从输入的两张图像中估计出对应的单应变换，其基本原理如图1所示。假设有一对待估计图像A和B，其中A为源图像，B为目标图像，图像B是由图像A经过单应变换而来，单应矩阵为 $\pmb { H }$ 。基于深度学习的单应估计方法的基本步骤为：首先对图像A和B预处理，然后将处理后的图像输入网络，由网络估计出某种形式表示的单应变换，最后计算得到单应矩阵 $\boldsymbol { H } ^ { * } ( \boldsymbol { H } ^ { * }$ 表示对 $\pmb { H }$ 的估计值，下文均使用上标“\*”表示估计值)。

![](images/6c56554052ea1061cf60867688d8f0234cb07a6759e6f5b153716bac157e70ee.jpg)  
图1深度学习单应估计方法原理示意图 Fig.1Schematic diagram of homography estimation method based on deep learning

单应变换具有多种表示方式，可以直接采用单应矩阵来表示，也可以采用四角点绝对像素偏移[12]或者其他形式来表示。由于单应矩阵中的各个元素的意义与取值范围各不相同，例如式(1)中 $\mathbf { h } _ { 1 1 }$ 、h12、h2i和h22表示旋转，hi3、h23表示平移，而平移元素一般会远远大于旋转元素，且又无法对矩阵中的元素进行归一化处理，因此直接使用深度网络估计单应矩阵十分困难。为此，文献[12]不直接估计单应矩阵，而是把单应矩阵参数化为四角点绝对像素偏移，通过网络估计四角点绝对像素偏移从而得到4组匹配点对，再使用式(3)中的直接线性法求解以获取单应矩阵。

与传统单应估计方法相比，深度学习单应估计方法在速度和鲁棒性上具有诸多优势。传统方法由于需要检测和匹配特征点，速度通常较慢，并且在弱纹理图像中难以获得稳定有效的匹配点对，导致不能工作。而深度学习方法不需要检测与匹配特征点，因此速度较快。对于传统方法不能处理的弱纹理图像，深度学习同样能根据大量训练数据学习到的规律来估计出较合理的单应矩阵。因此深度学习单应估计方法在实际使用中限制较小，鲁棒性更强，具有较大的应用价值，

# 2 多尺度残差单应估计网络

# 2.1网络结构

2016年文献[12]首次将一种VGG架构的网络用于单应估计，但由于网络结构简单且深度较浅，效果与传统方法相比提升有限。传统的卷积神经网络随着深度不断加深，网络可能会出现退化，训练也会更加困难。因此，2016年He 等人[19]提出残差网络(ResNet)，通过恒等映射来降低深度网络训练难度。2020 年文献[15]使用ResNet34作为主干，并使用内容掩码来进行单应估计，效果相比于前人有一定提高。但是以上方法均忽略了单应估计中存在的多尺度问题，因此具有一定的局限性。

在单应估计中，两次拍摄的照片由于相机位置、距离和角度的不同，两张图像之间会存在扭曲与缩放，导致图像中的同一物体尺度可能会发生变化，因此单应估计面临多尺度的挑战。为了解决这一问题，本文综合多尺度特征信息来估计四角点归一化偏移，提出了一种多尺度残差单应估计网络来进行单应估计。该网络相比于前人提出的单应估计网络具有明显的创新：首先，网络具有三个多尺度分支，能够提取图像的多尺度特征信息；其次，提出了多尺度特征融合模块(MFFModule)来逐步融合多尺度特征；最后，网络并不直接估计四角点绝对像素偏移，而是估计四角点归一化偏移。网络结构如图2所示。

网络输入待估计的两张 $1 2 8 \times 1 2 8$ 的归一化灰度图像，输出表示四角点归一化偏移的 $4 \times 2$ 矩阵 $\pmb { H } _ { 4 p t \_ n o r m } ^ { * }$ 。具体计算过程如下：首先，将待估计的两图像归一化后堆叠成双通道，同时输入到三个特征提取分支中，分别提取大尺度、中尺度和小尺度的特征。其中，中尺度和小尺度分支具有额外的步长为2的卷积层用来减小特征图。三个分支经过ReLU激活函数后，大尺度特征图输入到ResNet34[19]的 stage1块，stage1块输出与中尺度特征图通过一个MFF 模块(缩放系数$\scriptstyle \mathbf { r } = 2$ 融合后作为 stage2块的输入，stage2 块输出与小尺度特征图再通过一个MFF 模块 $( \mathrm { r } { = } 4 )$ 融合后依次通过stage3块和stage4块；最后，特征图通过平均池化后形状变为 $1 \times 1 \times$ 512，再经过全连接层输出 $4 \times 2$ 的矩阵 $\pmb { H } _ { 4 p t \_ n o r m } ^ { * }$ 。为了加速训练，在每个卷积层后均使用了BatchNorm层[20]。

![](images/3f9304356800ad1268cf629a7664be0daed422e4b0b0068dd51cab5f849382cd.jpg)  
Fig.2Multi-scale residual homography estimation network structure diagram

# 2.2 多尺度特征提取

在单应估计中，两次拍摄的照片由于相机位置、距离和角度的不同，两张图像之间会存在扭曲与缩放，导致图像中的同一物体尺度可能会发生变化，因此单应估计面临多尺度的挑战。而文献[12\~15]均忽略了这个问题，将两图视为相同尺度对待，使用单一大小的卷积层来提取图像的原始特征，单一的卷积核感受野是固定不变的，导致提取到的特征是在单一空间尺度下的，虽然特征会在后续的卷积层和激活函数后被不断聚合成深层语义特征，感受野逐渐变大，但此时已经丢失了图像原始的空间、几何等细节特征[2I]。因此，使用单一尺度的特征来进行单应估计具有一定的局限性，尤其在两张图像具有较大尺度差异时效果不佳。因此，多尺度特征信息对于单应估计是十分重要的。本文把多尺度特征信息引入网络，利用多尺度特征信息来解决单应估计中尺度不一致的问题，从而提高单应估计的精度，使得即使在图像尺度差异较大的情况下该方法也达到理想的效果。

图2所示的网络具有大、中、小三个尺度的提取分支，每个分支能够提取对应尺度的特征，因此网络能够利用多尺度特征信息来估计单应变换。具体来说，在三个多尺度分支中，分别使用了感受野为 $7 \times 7$ 、 $5 \times 5$ 和 $3 \times 3$ 空洞卷积层[22]来提取图像的不同尺度上的特征。图3显示了空洞卷积层的原理，与标准卷积相比，空洞卷积可以保证感受野大小不变的同时降低参数量和计算量，能够提高计算效率。

![](images/540b20d846350b52759225e64daf6607d345d2800fe3fbb238df0071bd932d39.jpg)  
图2多尺度残差单应估计网络结构图  
图3空洞卷积示意图  
Fig.3Schematic diagram of dilated convolution

在原始的ResNet34[19]中，使用了最大池化来对特征图下采样。但是最大池化下采样过程中只保留最大值，导致其余特征信息丢失，因此本文在这里没有使用最大池化，而是将 stage1块中第一层卷积步长设置为2(原始步长为1)，在避免特征信息丢失的同时也减少了计算量。由于后续的MFF模块需要输入两个相同形状的特征图，所以在中尺度和小尺度特征提取分支中分别使用了1层和2层卷积核为 $2 \times 2$ 、步长为2的卷积层，用于对特征图下采样以匹配后续的MFF模块，同时也可以加强特征信息在通道上的交流。

# 2.3 多尺度特征融合

在基于卷积的单应估计网络中，图像特征通过卷积层逐渐由浅层特征变为深层特征。浅层特征分辨率更高，包含更多位置、几何等细节信息，但是由于经过的卷积层较少，其语义性更低；而深层特征具有更强的语义信息，但是对细节感知能力较差。有效利用浅层特征与深层特征的优势是提高单应估计精度的关键之一。

因此，网络并没有在刚开始就将三种尺度的特征融合，而是在stage1块和stage2块后分别将中尺度和小尺度的特征融合到网络的主干中。采用了逐步融合的方式，能够利用浅层特征包含的细节信息对深层特征进行补充，实现浅层特征与深层特征优势互补。多尺度分支提取的特征由于尺度不同，如果直接通过相加来融合会导致不同尺度特征混合而难以充分利用多尺度特征的优势；如果将特征在通道上连接，多尺度特征能得到保留，但是通道数就会加倍，计算效率会大幅降低。考虑到特征虽然尺度不同，但均来自于同一输入，所以特征之间会存在冗余。为了充分利用多尺度特征并减少冗余提高计算效率，同时也受到文献[16在多尺度特征融合方式上的启发，本文提出了使用多尺度特征融合模块MFFModule来融合不同尺度的特征。

MFF模块结构如图4所示。输入2个不同尺度的特征图$\pmb { x } _ { 1 } , \pmb { x } _ { 2 } \in \mathbb { R } ^ { H \times W \times C }$ ，MFF 模块输出融合后的特征图 $\pmb { x } _ { o u t } \in \mathbb { R } ^ { H \times W \times C }$ 。文献[16]中为了融合不同尺度的特征，先将 $\mathbf { \lambda } _ { x _ { I } }$ 与 $\mathbf { x } _ { 2 }$ 直接相加，再使用 $1 \times 1$ 的平均池化来提取通道上的信息。而本文与文献[16]有两处不同之处：第一，本文先将 $x _ { I }$ 与 $\mathbf { x } _ { 2 }$ 在通道上连接，这样可以保持 $\mathbf { \lambda } _ { \pmb { x } _ { I } }$ 与 $\mathbf { x } _ { 2 }$ 各自的特征，便于后续提取通道上的特征；第二，本文同时使用了 $1 \times 1$ 平均池化与 $1 \times$ 1最大池化来提取通道上的信息。原因是平均池化只能提取到全局的平均信息不能提取到局部信息，而最大池化只能提取局部信息而不能提取到全局信息，因此同时使用平均池化与最大池化能够综合全局与局部的信息。MFF模块具体计算过程如下：

a）将 $\ x _ { I } , \ x _ { 2 }$ 在通道上连接，得到 $\mathbf { \Psi } _ { X _ { c a t } \in \mathbb { R } ^ { H ^ { X } W ^ { X } 2 C } }$ ，对 $x _ { c a t }$ 分别使用 $1 \times 1$ 平均池化和 $1 \times 1$ 最大池化分别提取通道上的信息并将结果相加，得到 $\boldsymbol { x } _ { g } \in \mathbb { R } ^ { I ^ { \boldsymbol { x } } I ^ { \boldsymbol { x } } 2 C }$ .

$$
\pmb { x } _ { g } = A \nu g P o o l ( \pmb { x } _ { c a t } ) + M a x P o o l ( \pmb { x } _ { c a t } )
$$

b）使用节点数为 $\operatorname { C } / \operatorname { r }$ 的全连接层 $f c _ { 0 } ( \mathbf { r }$ 表示缩放系数)缩短 $x _ { g }$ 的长度以提高计算效率，随后通过 $R e L U$ 函数，得到 $z _ { r }$ $\in \mathbb { R } ^ { I \times _ { I } \times _ { C / r } }$ 。 $_ { z r }$ 分别通过2个节点数为C的全连接层 $f c _ { 1 } , \ f c _ { 2 }$ ，得到 $_ { z _ { I } }$ 、 $\boldsymbol { z } _ { 2 } \in \mathbb { R } ^ { I \times I ^ { \times } C }$

$$
z _ { r } = \mathrm { R e L U } ( f c _ { 0 } ( x _ { g } ) )
$$

$$
z _ { I } = \mathrm { f c } _ { 1 } ( z _ { r } ) ; z _ { 2 } = \mathrm { f c } _ { 2 } ( z _ { r } )
$$

c）将 $_ { z _ { I } , \ { z 2 } }$ 在通道上堆叠，并在通道上使用SoftMax 函数，得到输入的两特征图在通道上的权重 ${ { \ w } _ { I } }$ 、 ${ w _ { 2 } } \in \mathbb { R } ^ { I \times } I ^ { \times } C$

$$
w _ { I } [ i ] = \frac { e ^ { z _ { I } [ i ] } } { e ^ { z _ { I } [ i ] } + e ^ { z _ { 2 } [ i ] } } ~ ; w _ { 2 } [ i ] = \frac { e ^ { z _ { 2 } [ i ] } } { e ^ { z _ { I } [ i ] } + e ^ { z _ { 2 } [ i ] } }
$$

d）最后，使用广播乘法将 $\mathbf { \psi } _ { x _ { I } , \mathbf { \psi } _ { \mathbf { \lambda } } , \mathbf { \psi } _ { x _ { 2 } } }$ 分别与 $\boldsymbol { w } _ { I } , ~ \boldsymbol { w } _ { 2 }$ 相乘，再将其结果相加，得到融合后的特征图。

$$
\pmb { x } _ { o u t } = \pmb { x } _ { I } * \pmb { w } _ { I } + \pmb { x } _ { 2 } * \pmb { w } _ { 2 }
$$

不同于将特征图直接简单地相加，MFF模块能够综合通道上的全局信息为不同尺度的特征图分配相应权重，使得网络具有根据输入的图像选择合适尺度的特征进行单应估计的能力。不同尺度的特征信息经过MFF模块融合后能够保留有效特征，减少冗余与无效的特征，有利于网络充分利用多尺度特征信息，从而提高单应估计的精度。

![](images/28aa74ac6142a7acb293284f1b3fd920a12d5f22121720dd0cf75a441bf7199c.jpg)  
图4MFF 模块结构图  
Fig.4Structure diagram of MFF module

# 2.4四角点归一化偏移

文献[12]为了解决直接估计单应矩阵而导致网络难以优化的问题，将单应矩阵参数化为四角点绝对像素偏移 $\pmb { H } _ { 4 p t }$ 通过估计四角点绝对像素偏移来间接估计单应矩阵，在一定程度上降低了网络优化的难度。但是，实际上四角点绝对像素偏移在数值上差异仍然较大，这会使得网络优化过程中梯度差异较大，不利于网络优化。同时也考虑到深度网络中的权重一般会初始化为- $\cdot 1 . 0 { \sim } 1 . 0$ 之间，而四角点绝对像素偏移在大部分情况下会远大于1像素，为了学习到这种绝对像素偏移的分布规律，网络权重相对于初始值会发生较大改变，因此使用网络直接估计四角点绝对像素偏移不利于网络收敛，为了进一步降低网络优化难度，本文用网络估计四角点归一化偏移 $H _ { 4 p t \_ n o r m }$ ，计算方法如式(8)所示。

$$
H _ { \mathit { d p t \_ n o r m } } = \left[ \begin{array} { c c } { \Delta x _ { 1 } } & { \Delta y _ { 1 } } \\ { \Delta x _ { 2 } } & { \Delta y _ { 2 } } \\ { \Delta x _ { 3 } } & { \Delta y _ { 3 } } \\ { \Delta x _ { 4 } } & { \Delta y _ { 4 } } \end{array} \right] = H _ { \mathit { 4 p t } } \cdot \left[ \begin{array} { c c } { Y } & { 0 } \\ { W } & { \gamma _ { H } } \end{array} \right]
$$

式(8)中的 $\Delta x _ { i }$ 与 $\Delta y _ { i } ( i = 1 , ~ 2 , ~ 3 , ~ 4 )$ 表示从图像原点开始顺时针第 $i$ 个点在图像宽度与高度方向上的归一化偏移量，$W$ 与 $H$ 分别表示图像的宽度与高度。由网络估计的四角点归一化偏移 $\smash { \boldsymbol { H } _ { 4 p t , n o r m } ^ { * } }$ 到单应矩阵 $\boldsymbol { H } ^ { * }$ 的计算方法如式(9)\~(11)所示。

$$
C o r n e r s _ { A } = \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { H } \\ { W } & { H } \\ { W } & { 0 } \end{array} \right]
$$

$$
C o r n e r s _ { _ B } ^ { * } = C o r n e r s _ { _ A } + H _ { \mathcal { I } p t \_ n o r m } ^ { * } \cdot \left[ \begin{array} { c c } { W } & { 0 } \\ { 0 } & { H } \end{array} \right]
$$

$$
\pmb { H } ^ { * } = f _ { _ { D L T } } ( C o r n e r s _ { _ A } , C o r n e r s _ { _ B } ^ { * } )
$$

# 3 实验与分析

# 3.1网络训练

本文使用MS-COCO 数据集[17]与 Apolloscape 数据集[18],按照文献[12]的方法生成实验所需数据集，不同的是本文并没有将图像缩放到 $3 2 0 \times 2 4 0$ ，这会使网络从更少的特征中学习单应估计，有利于增强网络鲁棒性。除此以外，本文还通过将像素值除以255的方式来对图像做归一化。总共生成了22万对图像，图像尺寸为 $1 2 8 \times 1 2 8$ ，最大角点偏移 $\scriptstyle \mathbf { \rho } \mathbf { = } 3 2$ 像素(图像的四分之一)，其中18万对用于训练网络，4万对用于验证网络。

损失函数使用平均角点误差(AverageCornerError,ACE)[12]，表示预测的四角点偏移与真实值的平均欧式距离，单位为像素(pixel，px)，计算方法如式(12)所示。

$$
\mathrm { A C E } = \frac { 1 } { 4 } \sum _ { i = 1 } ^ { 4 } \sqrt { ( \Delta x _ { i } - \Delta x _ { i } ^ { * } ) ^ { 2 } + ( \Delta y _ { i } - \Delta y _ { i } ^ { * } ) ^ { 2 } } \times 1 2 8
$$

本文基于Pytorch 深度学习框架来完成实验。训练过程中，使用了概率为0.5的随机翻转用于增强数据，采用Adam优化器，L2正则化权重衰减系数设置为0.003，每次迭代训练256对图像，初始学习率为0.0002，每迭代20K次学习率乘以0.7，总共迭代200K次。

# 3.2实验测试

为了验证本文方法的实际效果，使用3.1节中的方法分别在最大角点偏移 $\scriptstyle \mathsf { p } = 8 \mathsf { p x }$ 、 $1 6 \mathrm { p x }$ 、 $2 4 \mathrm { p x }$ 和 $3 2 \mathrm { p x }$ 时各生成了4万对图像，总共生成了16万对图像作为测试集。其中$\scriptstyle \mathsf { p } = 8 \mathsf { p x }$ 表示最大偏移距离较小， $\scriptstyle \mathsf { p } = 3 2 \mathsf { p x }$ 表示最大偏移距离较大，因此测试集中包含了不同程度偏移的图像对。

在测试过程中，平均角点误差ACE可能偶尔会出现极端大的情况，导致整个测试集上的平均 ACE(mean averagecornererror,Mean-ACE)偏高，同时传统方法可能会由于特征点较少而失败。因此本文对ACE作出限制，对于$\mathrm { A C E } { > } 3 2 \mathrm { p x }$ 或者传统方法失败的情况，均视为 $\mathrm { A C E } { = } 3 2 \mathrm { p x }$ 。对于 $1 2 8 \times 1 2 8$ 的图像，如果 $\mathrm { A C E } { > } 3 2 \mathrm { p x }$ 意味结果几乎没有任何价值，所以选择用32px作为阈值。由于Mean-ACE误差只能反映误差在测试集上的平均情况，不能反映误差分布情况，因此本文引入了中值ACE(median average corner error,Median-ACE)作为评价指标之一。对于 $\mathrm { A C E } { > } 3 2 \mathrm { p x }$ 或者传统方法失败这两种情况，意味着这次估计是无效的，所以本文还引入了无效率(InvalidRate，IR)作为评价指标之一，表示无效的情况在测试集中的比例。实验中所有方法均经过多次测试，以避免偶然情况。

为了分别验证本文提出的三个改进点效果，首先进行了消融实验。所有模型均使用相同的方法进行训练与测试，在MS-COCO数据集[17]上的消融实验结果如表1所示，其中“MFE”表示使用多尺度特征提取，“MFF”表示使用MFF模块来融合多尺度特征，“Norm”表示使用了四角点归一化偏移。由表1可知，单独使用多尺度特征提取或者四角点归一化偏移均能提升模型效果，并且使用MFF模块融合多尺度特征后模型效果有一定提升。当同时使用多尺度特征融合、MFF模块与四角点归一化偏移时，模型效果能够进一步提升。

在进行了消融实验后，本文使用最终模型与其他方法进行对比实验。参与实验的方法包括了传统方法中的SIFT[7]+RANSAC[1]法和 ORB[9]+RANSAC[11]法，以及基于深度学习的文献[12,14,15]的方法。在MS-COCO数据集[17]与Apolloscape数据集[18]上的对比实验结果如表2\~3所示。

由于Apolloscape 数据集[18]中的图像纹理弱于 MS-

COCO 数据集[17]，因此各种方法在Apolloscape 数据集上的误差均有一定升高。比较表2与表3，可以明显看出传统方法在较弱纹理图像上误差与无效率大幅增加，这使得传统方法在实际中几乎难以应用。而基于深度学习的方法误差与无效率虽然也有一定升高，但是幅度却较小，这也印证了基于深度学习的方法在弱纹理图像中鲁棒性更强。

表1消融实验结果  

<html><body><table><tr><td colspan="2">P</td><td colspan="3">8px</td><td colspan="3">16px</td><td colspan="3">24px</td><td colspan="3">32px</td></tr><tr><td>MFE MFF Norm</td><td></td><td>Mean-ACE</td><td>Median-ACE</td><td>IR</td><td>Mean-ACE</td><td>Median-ACE</td><td>IR</td><td>Mean-ACE</td><td>Median-ACE</td><td>IR</td><td>Mean-ACE</td><td>Median-ACE</td><td>IR</td></tr><tr><td></td><td></td><td>0.654</td><td>0.605</td><td>0.00%</td><td>0.758</td><td>0.688</td><td>0.00%</td><td>0.978</td><td>0.859</td><td>0.00%</td><td>1.431</td><td>1.149</td><td>0.06%</td></tr><tr><td></td><td>√</td><td>0.601</td><td>0.564</td><td>0.00%</td><td>0.688</td><td>0.622</td><td>0.00%</td><td>0.860</td><td>0.758</td><td>0.00%</td><td>1.236</td><td>0.981</td><td>0.05%</td></tr><tr><td>√</td><td></td><td>0.417</td><td>0.373</td><td>0.00%</td><td>0.510</td><td>0.454</td><td>0.00%</td><td>0.687</td><td>0.590</td><td>0.00%</td><td>1.077</td><td>0.823</td><td>0.02%</td></tr><tr><td>√</td><td>√</td><td>0.352</td><td>0.312</td><td>0.00%</td><td>0.430</td><td>0.392</td><td>0.00%</td><td>0.570</td><td>0.519</td><td>0.00%</td><td>0.881</td><td>0.702</td><td>0.01%</td></tr><tr><td>√ √</td><td>√</td><td>0.324</td><td>0.288</td><td>0.00%</td><td>0.395</td><td>0.352</td><td>0.00%</td><td>0.515</td><td>0.452</td><td>0.00%</td><td>0.788</td><td>0.616</td><td>0.00%</td></tr></table></body></html>

表2在MS-COCO数据集上的对比实验结果

Tab.2Results of comparative experiments on MS-COCO dataset   

<html><body><table><tr><td>P</td><td colspan="3">8px</td><td colspan="3">16px</td><td colspan="3">24px</td><td colspan="3">32px</td></tr><tr><td>评价指标</td><td>Mean-ACE Median-ACE</td><td></td><td>IR</td><td>Mean-ACE</td><td>Median-ACE</td><td>IR</td><td></td><td>Mean-ACE Median-ACE</td><td>IR</td><td></td><td>Mean-ACE Median-ACE</td><td>IR</td></tr><tr><td>SIFT[7]+RANSAC[11]</td><td>5.339</td><td>0.343</td><td>13.82%</td><td>6.020</td><td>0.519</td><td>15.18%</td><td>6.977</td><td>0.764</td><td>17.41%</td><td>8.179</td><td>1.135</td><td>20.10%</td></tr><tr><td>ORB[9]+RANSAC[11]</td><td>12.778</td><td>4.960</td><td>29.08%</td><td>14.262</td><td>7.002</td><td>31.82%</td><td>16.860</td><td>11.751</td><td>37.88%</td><td>20.601</td><td>29.483</td><td>49.32%</td></tr><tr><td>DeTone[12]</td><td>2.072</td><td>1.779</td><td>0.00%</td><td>2.575</td><td>2.189</td><td>0.00%</td><td>3.489</td><td>2.885</td><td>0.03%</td><td>5.252</td><td>4.251</td><td>0.47%</td></tr><tr><td>Nguyen[14]</td><td>3.487</td><td>2.959</td><td>0.00%</td><td>4.126</td><td>3.480</td><td>0.00%</td><td>5.050</td><td>4.212</td><td>0.00%</td><td>6.556</td><td>5.464</td><td>0.12%</td></tr><tr><td>Zhang[15]</td><td>0.873</td><td>0.752</td><td>0.00%</td><td>1.083</td><td>0.894</td><td>0.00%</td><td>1.488</td><td>1.118</td><td>0.00%</td><td>1.942</td><td>1.476</td><td>0.05%</td></tr><tr><td>Ours</td><td>0.324</td><td>0.288</td><td>0.00%</td><td>0.395</td><td>0.352</td><td>0.00%</td><td>0.515</td><td>0.452</td><td>0.00%</td><td>0.788</td><td>0.616</td><td>0.00%</td></tr></table></body></html>

表3在ApolloScape 数据集上的对比实验结果

Tab.1Result of ablation experiment   
Tab.3Results of comparative experiments on apolloscape dataset   

<html><body><table><tr><td>P</td><td colspan="3">8px</td><td colspan="3">16px</td><td colspan="3">24px</td><td colspan="3">32px</td></tr><tr><td>评价指标</td><td>Mean-ACE Median-ACE</td><td></td><td>IR</td><td>Mean-ACE Median-ACE</td><td></td><td>IR</td><td></td><td>Mean-ACE Median-ACE</td><td>IR</td><td>Mean-ACE Median-ACE</td><td></td><td>IR</td></tr><tr><td>SIFT[7]+RANSAC[11]</td><td>15.981</td><td>7.392</td><td>47.68%</td><td>16.696</td><td>16.493</td><td>49.03%</td><td>18.001</td><td>32.000</td><td>52.984%</td><td>18.695</td><td>32.000</td><td>54.73%</td></tr><tr><td>ORB[9]+RANSAC[11]</td><td>25.559</td><td>32.000</td><td>74.18%</td><td>26.545</td><td>32.000</td><td>77.05%</td><td>27.423</td><td>32.000</td><td>79.86%</td><td>28.845</td><td>32.000</td><td>85.21%</td></tr><tr><td>DeTone[12]</td><td>2.265</td><td>1.836</td><td>0.00%</td><td>3.050</td><td>2.518</td><td>0.00%</td><td>4.114</td><td>3.407</td><td>0.24%</td><td>6.123</td><td>4.813</td><td>0.62%</td></tr><tr><td>Nguyen[14]</td><td>3.693</td><td>3.010</td><td>0.00%</td><td>4.404</td><td>3.769</td><td>0.00%</td><td>5.693</td><td>4.693</td><td>0.19%</td><td>7.596</td><td>6.105</td><td>0.46%</td></tr><tr><td>Zhang[15]</td><td>0.967</td><td>0.822</td><td>0.00%</td><td>1.177</td><td>0.968</td><td>0.00%</td><td>1.623</td><td>1.213</td><td>0.00%</td><td>2.315</td><td>1.687</td><td>0.22%</td></tr><tr><td>Ours</td><td>0.348</td><td>0.298</td><td>0.00%</td><td>0.424</td><td>0.376</td><td>0.00%</td><td>0.549</td><td>0.484</td><td>0.00%</td><td>0.922</td><td>0.664</td><td>0.01%</td></tr></table></body></html>

由于基于深度学习的方法在两个数据集上具有相似的趋势，因此本文以MS-COCO数据集[17]上的实验结果为例进行分析。图5和图6分别显示了MS-COCO数据集上不同程度偏移下各种方法的Mean-ACE误差和Median-ACE误差。

![](images/5cf94e5e8a84ed9b4f93420ce44971b3a435569b1d4aee6e15da56e3ebe49702.jpg)  
图5在MS-COCO 数据集上不同程度偏移下的Mean-ACEFig.5Mean-ACE under different scale offsets on MS-COCO dataset

![](images/9275e1c579fc0bd587c9cf415f85827209512ddf017b041a796ab6099f1591b7.jpg)  
图6在MS-COCO 数据集上不同程度偏移下的Median-ACEFig.6Median-ACE under different scale offsets on MS-COCO dataset从表2\~3和图5\~6中可以看出：在传统方法中，SIFT[7]+RANSAC[11]法在精度上明显优于ORB[9]+RANSAC[1]法。所有方法随着图像最大偏移距离 $\rho$ 由小变大(从 8px 增加到32px)，Mean-ACE与 Median-ACE 误差均有不同程度

地增加。其中，本文误差变化则相对平缓，是唯一能够始终保持亚像素级精度的方法，而其他方法误差增加地比较明显。基于深度学习文献[12,14,15]的方法在MS-COCO数据集[17]上虽然Mean-ACE误差小于SIFT+RANSAC法，但是Median-ACE误差却比SIFT $^ +$ RANSAC法大，而本文方法则在Mean-ACE与Median-ACE误差上均领先于SIFT+RANSAC法。

图7显示了在较大偏移 $\scriptstyle ( \rho = 3 2 \mathrm { p x } )$ 时MS-COCO数据集[17]上各种方法的ACE累积分布曲线。从中可以看出：传统方法中ORB[9]+RANSAC[11]法表现较差，在大部分情况下都具有相对较高的误差，无效率高达 $4 9 . 3 2 \%$ ； $\mathrm { S I F T ^ { [ 7 ] } + }$ RANSAC[I]法表现较好一些，能够在大约 $70 \%$ 的情况下保持较低的误差( $\mathrm { A C E } { < } 4 \mathrm { p x } )$ ，而在另外 $30 \%$ 的情况下误差会急剧升高，表现变得非常糟糕，无效率为 $20 . 1 \%$ 。基于深度学习的方法整体上都能在 $9 9 \%$ 以上的情况下正常工作1 $\mathrm { \ A C E { < } } 3 2 \mathrm { p x }$ )，但文献[12,14,15]的方法 $60 \%$ 以上的情况误差高于SIFT $^ { \ast } +$ RANSAC法，仅能在另外少部分情况下获得比SIFT $+$ RANSAC法更好的结果；而本文方法能够在绝大部分情况下具有比SIFT $^ +$ RANSAC法更低的误差，并且能够在$9 9 \%$ 情况下保持较高的精度 $( \mathsf { A C E } { < } 4 \mathsf { p x } )$ ，具有最好的鲁棒性

表4显示了不同方法之间的性能对比。在模型大小方面，本文模型比文献[12,14]更小；在处理速度方面，本文方法速度与传统方法相比具有显著提升，与文献[15]速度相当。

# 3.3效果展示

图8显示了使用不同方法进行单应估计上的可视化效果。其中最左侧表示被估计的两张图像；右侧图像中的蓝色框与红色框分别表示被估计两图在原图中的位置；绿色框表示使用不同方法估计的结果。红色框与绿色框四角点的平均距离即为3.1节中的ACE误差，两者越接近则表示误差越低，该方法越好。估计误差显示在对应图像下方，“fail”则表示该方法失败。可以看出SIFT[7]+RANSAC[11]法与 $\mathrm { O R B ^ { [ 9 ] } + }$

RANSAC[1]法在弱纹理图像中几乎不能工作，而本文方法则始终保持较低的误差。

表4不同方法的性能对比  
Tab.4Performance comparison of different methods   

<html><body><table><tr><td>方法</td><td>模型大小</td><td>PPS</td></tr><tr><td>SIFT[7]+RANSAC[11]</td><td></td><td>75</td></tr><tr><td>ORB[9]+RANSAC[11]</td><td></td><td>100</td></tr><tr><td>DeTone[12]</td><td>32.61M</td><td>10200</td></tr><tr><td>Nguyen[14]</td><td>31.54M</td><td>9800</td></tr><tr><td>Zhang[15]</td><td>20.31M</td><td>5950</td></tr><tr><td>Ours</td><td>20.46M</td><td>5900</td></tr></table></body></html>

\*PPS(Pairs Per Second)表示每秒处理的图像对数量。SIFT+RANSAC与ORB $+$ RANSAC运行于CPU(R55600X)，而其他方法运行于GPU(RTX3080Ti)。

![](images/a1ea40058b34c3469cdb9221a235f9da8d548cd1773dd88a1479c75349ca4ea2.jpg)  
图7在MS-COCO数据集上的ACE累计分布曲线

![](images/24b1bf578b8a763bd819078e11a49b1be3ab1c97e030d7c7b573872e70128238.jpg)  
Fig.7ACE cumulative distribution function on MS-COCO datasel   
Fig.8Effect diagram of homography estimation

# 4 结束语

单应估计是图像拼接、图像矫正等许多计算机视觉任务中的一个基础且重要的步骤，具有广泛的应用场景，提高单应估计的精度对这些任务具有重大意义。基于特征点匹配的传统单应估计方法难以在弱纹理图像中工作。然而现有的深度学习方法未考虑到单应估计的多尺度性，使用单一尺度的特征来估计四角点绝对像素偏移，导致图像具有较大偏移时表现不佳。本文提出了一种基于多尺度残差单应估计网络来进行单应估计的方法，通过提取图像的多尺度特征信息并使用MFF模块来融合多尺度特性信息，有效利用了多尺度特征信息同时结合了浅层特征与深层特征的优势，并且通过估计四角点归一化偏移来进一步降低了网络优化的难度。在多个数据集上的实验证明了该方法相比于前人提出的传统方法以及深度学习方法精度显著提高，鲁棒性也更强，因此在实际中具有较大的应用价值。

# 参考文献：

[1]Hartley R, Zisserman A.Multiple view geometryin computer vision [M]. 2nd ed.Cambridge University Press.2004:25-48.   
[2]夏丹，周睿．视差图像配准技术研究综述[J].计算机工程与应用, 2021,57 (O2):18-27.(Xia Dan,Zhou Rui. Survey of Parallax lmage Registration Technology [J].Computer Engineering and Applications, 2021,57 (02): 18-27.)   
[3]Brown M,Lowe D G.Recognising panoramas [C]//Proc of IEEE International Conference on Computer Vision.Piscataway,NJ:IEEE Press,2003:1218.   
[4]Yang Xieliu,Yin Chenyu,Tian Dake,et al.Rule-based perspective rectification for Chinese text in natural scene images [J].Multimedia Tools and Applications,2021,80 (12):18243-18262.   
[5]Zhang Zhongfei,Hanson AR.3D reconstruction based on homography mapping[J].Proc.ARPA96,1996:1007-1012.   
[6]Davison AJ,Reid ID,Molton ND,et al. MonoSLAM: Real-time single camera SLAM [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2007,29 (6):1052-1067.   
[7]Lowe DG.Distinctive image features from scale-invariant keypoints [J]. International Journal of Computer Vision,20o4,60 (2):91-110.   
[8]Bay H,Tuytelaars T,Van GoolL.SURF: Speeded up robust features [C]// Proc of European Conference on Computer Vision.Berlin: Springer, 2006: 404-417.   
[9]Rublee E,Rabaud V,Konolige K,et al. ORB:An efficient alternative to SIFTor SURF[C]//Proc of IEEE International Conference on Computer Vision.Piscataway,NJ:IEEE Press,2011:2564-2571.   
[10] Muja M,Lowe D G.Fast approximate nearest neighbors with automatic algorithm configuration [J]. VISAPP (1),2009,2 (31-340): 2.   
[11] Fischler MA,Bolles R C.Random sample consensus:a paradigm for model fitting with applications to image analysis and automated cartography [J]. Communications of the ACM,1981,24 (6): 381-395.   
[12] DeTone D,Malisiewicz T,Rabinovich A. Deep image homography estimation [EB/OL].(2016)[2022-03-13].https://arxiv.org/abs/1606. 03798.   
[13] Nowruzi FE,Laganiere R, Japkowicz N.Homography estimation from image pairs with hierarchical convolutional networks [C]//Proc of IEEE International Conference on Computer Vision.Piscataway,NJ:IEEE Press. 2017: 913-920.   
[14] Nguyen T,Chen S W, Shivakumar S S,et al. Unsupervised deep homography:A fast and robust homography estimation model[J].IEEE Robotics and Automation Letters,2018,3 (3): 2346-2353.   
[15] Zhang Jirong，Wang Chuan,Liu Shuaicheng，et al. Content-aware unsupervised deep homography estimation [Cl// Proc of European Conference on Computer Vision.Cham: Springer,2020:653-669.   
[16]Li Xiang,Wang Wenhai,Hu Xiaolin,et al.Selective kernel networks [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Piscataway, NJ: IEEE Press,2019: 510-519.   
[17] Lin TY, Maire M,Belongie S,et al. Microsoft COCO: Common objects in context [C]//Proc of European Conference on Computer Vision.Cham: Springer,2014: 740-755.   
[18] Huang Xinyu, Wang Peng,Cheng Xinjing,et al. The ApolloScape Open Dataset for Autonomous Driving and its Application [C]// Proc of IEEE Transactions on Pattern Analysis and Machine Intellgence.Piscataway, NJ: IEEE,2020:2702-2719.   
[19] He Kaiming,Zhang Xiangyu,Ren Shaoqing，et al.Deep residual learning for image recognition [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Piscataway,NJ:IEEE Press, 2016: 770-778.   
[20] Ioffe S,Szegedy C.Batch normalization:Accelerating deep network training by reducing internal covariate shift [C]// Proc of International Conference on Machine Learning. New York: ACM Press,2015: 448- 456.   
[21]姚铭，邓红卫，付文丽，等．一种改进的 MaskR-CNN的图像实例分 割算法[J]．软件,2021,42(09):78-82.(Yao Ming,Deng Hongwei,Fu Wenli,et al.An Improved Mask R-CNN Image Instance Segmentation Algorithm[J].Computer Engineering& Software,2021,42 (09): 78-82.)   
[22] Yu F,Koltun V.Multi-scale context aggregation by dilated convolutions [EB/OL]. (2015)[2022-03-13]. htps://rxiv.org/abs/1511.07122.