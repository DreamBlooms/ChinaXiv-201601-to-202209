# 压缩感知和相似性约束的图像超分辨率重构算法\*

吴科永‘，陈 东²，辛宁²，曹桂兴²

(1．西安电子科技大学 综合业务网理论及关键技术国家重点实验室，西安710071;2.中国空间技术研究院 通信卫星事业部，北京 100094)

摘要：针对通过外部学习进行超分辨率存在图像质量不佳、细节不真实的问题提出一种压缩感知和相似性约束的单帧图像超分辨率算法。算法首先利用压缩感知中测量域与频域的线性关系对训练库图像在测量域分类，对不同类别图像块训练对应类别的字典，提高字典的表示能力；然后在重构时利用图像的非局部相似性，将图像在分类字典下的稀疏性和相似块信息同时作为先验信息联合约束重构过程，最后恢复出高分辨率图像。实验结果表明算法重构出的高分辨率图像具有丰富的细节以及清晰的边缘，重构图像主观质量良好。

关键词：超分辨率；压缩感知；测量域字典分类；非局部相似；联合重构 中图分类号：TP391.4 doi: 10.3969/j.issn.1001-3695.2017.12.0833

# Compressed Sensing and Similarity constraint Image Super-Resolution

Wu Keyong1, Chen Dong², Xin Ning², Cao Guixing² (1.State Key Laboratory of Integrated Services Networks，Xidian University，Xi'an 1071，China;2.Instituteof Telecommunication Satellite,China Academy of Space Technology,Beijing 10oo94, China)

Abstract: Aimingat theproblemofpoor qualityandcontrived details in super-resolutionreconstruction byexternal learning, this paper proposesasingleimage super-resolutionbasedoncompressedsensingandsimilarityconstraint.Firstly,aclassified dictionary basedon measurement domain is proposedbyusing thelinearrelationship between the measurement domain andthe frequencydomainincompressed sensing,which improves therepresentationofdictionaries,then,thenon-local similarityis usedinthereconstructionprocess,the sparsityunderthefeaturedictionaryandsimilarblock informationarecombinedaspriori information toregularize super-resolutionreconstruction,and finallthe highresolution image isrecovered.Experimental results show that the reconstructed image has rich details and defined edges,and the subjective quality is good.

Key words:super-resolution;compressed sensing;dictioaryclassificationinmeasurementdomain;non-localsimilarity;joint reconstruction

# 0 引言

随着信息技术的飞速发展，图像已经成为人类获取信息的重要途径之一，人们对图像质量的要求也越来越高，具有丰富细节的高清图像在一些特定领域如视频监控、卫星图像、医疗数字影像等具有重要的应用价值[。然而由于技术或者硬件成本的限制，目前获取的很多图像质量较差，不能满足实际的应用需求。超分辨率算法作为一种基于软件的处理方式，在不需要改变现有成像系统的条件下就可以提高图像的分辨率，在近年来发展十分迅速。

多帧图像超分辨率算法要求输入的低分辨率图像存在多幅并且只有亚像素的位移，单帧图像超分辨率摆脱了这个限制，成为近几年研究的热点。Yang等人[2提出一种基于稀疏表示的超分辨率算法，利用图像的稀疏性，通过外部训练库学习具有对应关系的高、低分辨率字典对，取得了很好的效果，很多在此基础上改进的算法也相继被提出。He 等人[3]针对耦合特征空间学习超完备词典的问题，使用Beta过程作为先验的贝叶斯方法应用来学习超完备字典，相比其他算法，该针对每个特征空间提供定相应的字典，同时增加了两个特征空间之间更一致和准确的映射，而Beta 过程模型的独特性质在于稀疏表示可以被分解为值和字典原子指标，从而在耦合特征空间之间实现一致且精确的映射，该算法的另一个优点可以非参数地推断字典原子的数目及其相对重要性。Yeganli等人[4提出一种基于选择性稀疏表示的单幅图像超分辨率算法的扩展，该算法在一组耦合的低分辨率和高分辨率的字典对上进行，相比其他算法，扩展算法为高清晰度值的块保留稀疏表示框架，而双三次插值则用于超清晰非尖锐块如果一个块属于一个低清晰度的簇，则使用双三次插值进行超分辨，否则，这个块在群集的低分辨率字典上进行了稀疏编码；然后，利用低分辨率块的稀疏编码系数和簇的高分辨率块来估计相应的高分辨率块。Li等人[15]提出了一种基于自适应稀疏表示的超分辨率算法，将高分辨率图像与具有迭代反投影算法的重建图像之间的差异作为图像的高频特征，进一步用于高分辨率的字典训练。在边缘检测之后，改进的算法分别自适应地将稀疏表示和迭代反投影应用于边缘斑块和光滑斑块进行重建。相比其他算法，该算法重建的图像边缘强，几乎可以和原图像的高分辨图像媲美。尽管上述改进算法均存在各自的优点，但这种基于外部学习的方法存在两个问题：a)重构图像的效果与外部训练集的选取是否合适有着很大的关系，如果待重构的图像与外部训练库的特征差异性较大，则重构出图像质量较差；b)所有先验信息都是通过外部图像库学习得到，重构出的高分辨率图像存在不真实的细节。

为了解决上述问题，本文提出一种基于压缩感知和相似性约束的单帧图像超分辨率重构算法，主要包括两部分：在字典训练时利用压缩感知理论中测量域和频域的相关性[5]，提出一种基于测量域的字典分类方法，提高字典表示能力；在重构时将图像的自相似信息作为先验信息加入重构过程，提出一种联合学习的超分辨率重构算法。实验结果表明，该算法恢复出的高分辨率图像细节丰富且真实，边缘清晰，主观质量良好。

# 1基于压缩感知和相似性约束的图像超分辨率算法

本文算法的原理框图如图1所示，主要包括字典学习和重构两个过程。将文献[2使用的训练图像库在测量域进行分类，分别训练对应类别的特征字典，在重构时使用与输入图像块最接近的字典进行重构，同时将输入图像块的自相似块也作为约束条件加入重构过程中，联合图像块的稀疏性和自相似性恢复出具有细节丰富、纹理真实的高分辨率图像。

![](images/c017bc0e6f0aac13b5b3fda17e34d5cda5a26be72eec5b1654797c79ec6ba925.jpg)  
图1算法原理图

# 1.1测量域分类字典

针对只训练一个通用字典导致对不同类型图像表示性能较差的问题，本文提出一种基于测量域的字典分类方法。常用的图像分类方法通常都是在像素域进行的，而训练集一般包含很多幅图像，这使得分类处理的数据量很大。在压缩感知理论中，信号经过测量后，数据被压缩，文献[5表明，测量值与相应频域信号的相关性呈近似线性关系，而频域信号与像素域信号具有密切的关系，这使得在测量域对图像块分类的做法具有一定的可行性。

将训练库中的图像分块，大小为 $8 \times 8$ ，块与块之间没有重叠区域。将每个图像块拉成一维列向量使用高斯矩阵进行测量，得到的测量值为一维列向量。为了构建每个图像块的测量值矩阵，本文在图像块测量之前，对它进行二次分块，对这些子块使用相同高斯矩阵进行测量，使用这些子块的测量值向量构建它们所在的大图像块的测量值矩阵，如图2所示，然后利用测量值矩阵计算互协方差矩阵的方差对图像块进行分类。具体算法步骤如下：

a)对整幅图像分块，对于每个大图像块以 $\boldsymbol { x } _ { b }$ 为例子，将它进行二次分块，分成大小一致的四个子块 $x _ { b I } , x _ { b 2 } , x _ { b 3 } , x _ { b 4 }$ ，子块对应的频域信号为 $\theta _ { I } , \theta _ { 2 } , \theta _ { 3 } , \theta _ { 4 }$ ，对每个子块使用同一高斯矩阵测量，将得到的测量值向量 ${ \bf y } _ { I } , { \bf y } _ { 2 } , { \bf y } _ { 3 } , { \bf y } _ { 4 }$ 构建大图像块 $\boldsymbol { x } _ { b }$ 的测量值矩阵 $\mathbf { y } = [ { \boldsymbol { y } } _ { I } , { \boldsymbol { y } } _ { 2 } , { \boldsymbol { y } } _ { 3 } , { \boldsymbol { y } } _ { 4 } ] ^ { T }$ ，令 $\pmb { y } _ { i } = [ \pmb { y } _ { i I } , \pmb { y } _ { i 2 } , \cdots , \pmb { y } _ { i m } ] ^ { T }$ （204号$( i = 1 , 2 , \cdots , m )$ ，那么 $y$ 可进一步表示为

$$
\mathbf { y } = [ \mathbf { y } _ { I } , \mathbf { y } _ { 2 } , \mathbf { y } _ { 3 } , \mathbf { y } _ { 4 } ] ^ { T }
$$

$$
\begin{array} { r l } & { \left[ \begin{array} { l l l l } { y _ { 1 1 } } & { y _ { 2 1 } } & { y _ { 3 1 } } & { y _ { 4 1 } } \\ { y _ { 2 2 } } & { y _ { 2 2 } } & { y _ { 3 2 } } & { y _ { 4 2 } } \\ { \vdots } & { \vdots } & { \vdots } & \\ { y _ { m } } & { y _ { 2 m } } & { y _ { 3 m } } & { y _ { 4 m } } \end{array} \right] ^ { u } } \\ & { = \left[ \begin{array} { l l l } { y _ { 1 1 } } & { y _ { 1 2 } } & { \cdots } & { y _ { 1 m } } \\ { y _ { 2 1 } } & { y _ { 2 2 } } & { \cdots } & { y _ { 2 m } } \\ { \vdots } & { \vdots } & { \vdots } \\ { y _ { 4 1 } } & { y _ { 4 2 } } & { \cdots } & { y _ { 4 m } } \end{array} \right] ^ { u } } \end{array}
$$

b)将 ${ \bf y } _ { I } , { \bf y } _ { 2 } , { \bf y } _ { 3 } , { \bf y } _ { 4 }$ 视为一组随机变量且 $y _ { i 1 } , y _ { i 2 } , \cdots , y _ { i m }$ 作为随机变量 $\boldsymbol { y } _ { i }$ 的样本，利用公式$C _ { i j } = C o \nu ( y _ { i } , y _ { j } ) = E \{ [ y _ { i } - E ( y _ { i } ) ] [ y _ { j } - E ( y _ { j } ) ] \}$ 计算 $y$ 的互协方差矩阵 $C _ { y }$ ：

$$
\pmb { C } _ { y } = \left[ \begin{array} { l l l l } { C _ { 1 1 } } & { C _ { 1 2 } } & { C _ { 1 3 } } & { C _ { 1 4 } } \\ { C _ { 2 1 } } & { C _ { 2 2 } } & { C _ { 2 3 } } & { C _ { 2 4 } } \\ { C _ { 3 1 } } & { C _ { 3 2 } } & { C _ { 3 3 } } & { C _ { 3 4 } } \\ { C _ { 4 1 } } & { C _ { 4 2 } } & { C _ { 4 3 } } & { C _ { 4 4 } } \end{array} \right]
$$

在互协方差矩阵中， $C _ { y } ( i , j ) ( i = j )$ 能够衡量相应的频域信号 $\theta _ { i }$ 的方差， $C _ { y } ( i , j ) ( i \neq j )$ 能够衡量相应的频域子块 $\theta _ { i }$ 和 $\theta _ { j }$ 之间的相关性。

c)对测量域协方差矩阵的各个元素求方差，由文献[5]可推出， $\operatorname { v a r } ( { C _ { y } } ) = ( { \frac { n } { m } } ) ^ { 2 } \cdot \operatorname { v a r } ( { C _ { \theta } } )$ ，式中 $m \ 、 n$ 分别为测量域和频域信号随机向量的样本数量，这表明它们互协方差矩阵元素的方差也具有对应的线性关系，方差值的大小可以衡量大图像块内各个子块的相似程度，值越大反映出子块之间的差异性越大，反之则越小，因此可以将上述矩阵的方差值作为特征块的分类依据，将 $\mathrm { v a r } ( C _ { y } ) < T$ 的图像块作为纹理训练集训练纹理字典对$( D _ { t } ^ { l } , D _ { t } ^ { h } )$ ， $\operatorname { v a r } ( C _ { y } ) \geq T$ 的图像块作为边缘训练集训练边缘字典$( D _ { e } ^ { l } , D _ { e } ^ { h } )$ ，依据实验经验值本文取 $T = 1 0 ^ { 7 }$ 。

![](images/ffba78d7443be9f22cd089f63364db83ff5c1a28d762541bd32952dee256d192.jpg)  
图2测量域二次分块构造测量矩阵

使用文献[2]方法训练字典得到纹理字典对 $( D _ { t } ^ { l } , D _ { t } ^ { h } )$ 和边缘字典对 $( D _ { e } ^ { l } , D _ { e } ^ { h } )$ 后，在对输入的低分辨率图像进行超分辨率重构时，对每一个图像块 $y$ ，根据上述步骤求出图像块 $y$ 的方差 $\mathbf { v a r } ( \mathbf { y } )$ ，若 $\mathrm { v a r } ( y ) < T$ ，则当前待重构的图像块为纹理块，选取纹理字典对 $( D _ { t } ^ { l } , D _ { t } ^ { h } )$ 进行重构，否则当前重构图像块为边缘块，选取边缘字典对 $( D _ { e } ^ { l } , D _ { e } ^ { h } )$ 进行超分辨率重构。该分类方法既考虑了图像块的全局统计特性，也在一定程度上考虑了图像块的局部分布特性，输入图像根据自身特征选取最适合的字典对进行重构，能够提高字典的稀疏表示能力。

# 1.2联合重构

通常重构过程是分块进行的，并且块与块之间加入重叠部分避免结果图像出现明显的块效应。将输入低分图像块在低分字典表示下的稀疏系数 $\pmb { \alpha }$ 直接作为待重构高分图像在高分字典下的稀疏系数，求解的优化过程可表示为

$$
\operatorname* { m i n } \lambda \left\| \pmb { \alpha } \right\| _ { 1 } + \frac { 1 } { 2 } \left\| \tilde { D } \pmb { \alpha } - \tilde { y } \right\| _ { 2 } ^ { 2 }
$$

其中：D= $\tilde { D } = \left[ \begin{array} { c } { F D _ { \scriptscriptstyle L } } \\ { \beta P D _ { h } } \end{array} \right]$ ， $\widetilde { y } = \overline { { F y } } \overline { { } }$ ， $F$ 为特征提取算子， $P$ 表示重叠因子， ${ \pmb w }$ 为前一图像块在重叠区域恢复的高分辨率像素值，参数 $\lambda$ 用来平衡解的稀疏性和对图像块 $y$ 的近似程度， $\beta$ 用来控制当前重构方块与前一方块的相关性与稳定性。将公式(3)得到的系数 $a ^ { * }$ 通过 $\pmb { x } = \pmb { D } _ { h } \pmb { a } ^ { * }$ 得到图像块 $y$ 对应的高分辨率图像块 $x$ 。

上述的求解过程只利用了图像的稀疏性来约束解的唯一性，重构出的的结果图会出现虽然PSNR值很高但是与原图差异较大、细节不真实等问题[6][7]。所以仅利用图像的稀疏性作为先验信息还不够，本文需要加入图像的自相似信息[8来引导解趋于原始图像结构更一致的方向进行调整，提高重构图像的质量。本文所提的自相似信息指的是在一张自然图像中会出现一样或者相似的信息，在实际应用中一般从统计学的角度用协方差矩阵来衡量，本文使用接下来将提到的块匹配方法来度量。

对一幅低分辨率图像的任一图像块 $y$ 进行超分辨率重构时，根据 $y$ 的方差选取最合适的特征字典对 $( D ^ { l } , D ^ { h } )$ ，并且使用块匹配方法[9在局部区域找到它的相似块，用集合$S = \{ \mathbf { y } ^ { \prime } , \mathbf { y } ^ { 2 } , \cdots \mathbf { y } ^ { n } \}$ 表示，重构时在公式(3)的基础上，加入图像的自相似性，要求得到的系数 $\pmb { a }$ 不仅具有很高的稀疏度，而且用它表示的高分辨率图像块与其相似块 $s$ 具有一定的相似度。具体利用相似块集合 $s$ 以及外部训练的字典对 $( D ^ { l } , D ^ { h } )$ 联合求解的过程可以用式(4)表示。

$$
\begin{array} { r l } { \underset { i , \alpha ^ { i } } { \operatorname* { m i n } } \| F y - F D ^ { l } \alpha \| _ { 2 } ^ { 2 } + \underset { y ^ { i } \in S } { \sum } \| F y ^ { i } - F D ^ { l } \alpha ^ { i } \| _ { 2 } ^ { 2 } } & { } \\ { +  \lambda ( \| \pmb { \alpha } \| _ { 1 } + \underset { i = 1 } { \overset { n } { \sum } } \| \pmb { \alpha } ^ { i } \| _ { 1 } ) + \underset { i = 1 } { \overset { n } { \sum } } \gamma _ { i } \| \pmb { D } ^ { h } \alpha - \pmb { D } ^ { h } \alpha ^ { i } \| _ { 2 } ^ { 2 } } & { } \end{array}
$$

其中： $\pmb { a }$ 为当前处理图像块 $y$ 的稀疏系数， $\pmb { a } ^ { i }$ 为相似块 $\mathbf { y } ^ { i }$ 在低分字典 $\pmb { D } ^ { l }$ 表示下的稀疏系数，上式中前两项用来保证低分辨率图像的保真度，中间两项 $l _ { 1 }$ 正则化用来保证低分辨率图像块用

低分字典 $\smash { \mathbf { \delta D } _ { \perp } ^ { l } }$ 表示的稀疏度，最后一项用来保证用相似块重构出的高分图像块与当前处理的图像块 $y$ 对应的高分图像块的相似度，相似度用参数 $\gamma _ { i }$ 控制，取值为

$$
\gamma _ { i } = \frac { 1 } { Z } \mathrm { e x p } \{ - \frac { \left\| y - y ^ { i } \right\| ^ { 2 } } { h ^ { 2 } } \}
$$

$Z$ 为归一化参数。式(4)中的第二、四、五项为新加入的图像块的自相似信息，在求解系数 $\pmb { a }$ 时用来约束其与相似块的一致性。将图像块 $y$ 的稀疏性以及相似性同时作为约束条件来解重构的优化问题，可以保证重构出的图像不仅有丰富的细节，同时纹理真实边缘清晰，与原图更为接近。

通过求解式(4)，得到图像块 $y$ 的稀疏解 $\pmb { a }$ 。由于训练字典时已经保证了低分辨率字典和高分辨率字典原子之间的一一对应关系，所以通过求得下式得到图像块 $y$ 对应的高分辨率图像x:

$$
\mathbf { \Delta } _ { x } = D ^ { h } \mathbf { \delta } _ { a }
$$

如此依次对所有的低分辨率图像小块处理便可以得到最终的高分辨率图像 $X$ 。然后使用反向迭代投影[10]对 $X$ 进行图像后处理，使得最终得到的重建高分图像与输入的低分图像基于图像降质模型保持一致。方向迭代投影算法收敛的，同时算法简单、直观。

反向迭代投影算法示意图如图3所示，引导 $X$ 沿着与降质模型更接近的方向进行调整，即

$$
X _ { t + 1 } = X _ { t } + ( ( Y - D H X _ { t } ) \uparrow s ) * p
$$

其中： $X _ { t }$ 为 $t$ 次迭代后的高分辨率图像， $p$ 为反向投影滤波器，↑ $s$ 为上采样因子，将上式改进的 $X ^ { ^ { * } }$ 作为最终结果图像，它不仅能很好地近似由稀疏先验恢复的图像 $X$ ，同时也符合重建约束条件。

![](images/672a4760a02b87c0cbe9994211d0695cc46fa2362cd49196f220e63e9a714445.jpg)  
图3反向迭代算法示意图

# 2 实验结果与分析

为了验证本文提出的字典分类算法的有效性，使用不同类别的图像块训练对应类别的字典，对foreman序列的前50帧图像使用分类字典进行SR重构，并与传统单字典算法进行比较，结果如图4所示。

![](images/31b4789fec1a732cdec4d15f5578d4073490d57798f083fb55fef5f2ee12b436.jpg)  
图4前 50 帧重构PSNR值(foreman)

由图4可以看出，使用测量域分类字典重构出HR结果图像相比于单字典方法PSNR值平均提高了 $0 . 1 8 ~ \mathrm { d B }$ 。

图5给出foreman序列第五帧图像分别使用单字典以及分类字典进行SR重构的结果图像。

![](images/e6c5f2ad4438c6ca57ab2a8f248a89d348f19f6ca4c1210a2c0a9ab8b6eb49b3.jpg)  
图5使用单字典和测量域分类字典重构结果图

由主观结果图可以看出，用分类字典重构出的HR图像在边缘轮廓要比单特征字典更加清晰，墙面纹理更丰富，这是因为不同特征的图像块分别使用了对应类别的字典，字典的表示能力得到了提高。

为了验证本文算法的有效性，本文从超分辨率算法常用的测试集 set5[11]、set14[12]中选取5幅有代表性的测试图像进行2倍和4倍超分辨率重建，并与文献[2，3，13，14]的其他四种方法进行对比，为了方便表述，将这四种方法分别命名为Bicubic、SCSR、FDSR、JDLSR。评价指标除了主观视觉评价外，还采用峰值信噪比（PSNR）和结构相似度（SSIM）两个客观指标。所有仿真实验均在一台配置为AMDA8-5600KAPUwithRadeon(tm) HD Graphics 3600Mhz CPU 和 4GB 内存的PC上进行。

考虑到人眼视觉系统对于亮度分量相比色度更为敏感，本文对彩色图像仅在亮度Y通道进行超分辨率重建，而色度 $C _ { b }$ 和$C _ { r }$ 通道则通过Bicubic 插值直接上采样。表1到表5列出各算法进行 $2 \times$ 重构的PSNR和SSIM值。

表1lena放大2倍超分辨率结果数据  

<html><body><table><tr><td></td><td>PSNR/dB</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>32.79</td><td>0.887</td></tr><tr><td>SCSR</td><td>35.01</td><td>0.923</td></tr><tr><td>FDSR</td><td>35.03</td><td>0.912</td></tr><tr><td>JDLSR</td><td>35.23</td><td>0.935</td></tr><tr><td>Proposed</td><td>35.32</td><td>0.936</td></tr></table></body></html>

表2pepper 放大2倍超分辨率结果数据  

<html><body><table><tr><td></td><td>PSNR/dB</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>33.05</td><td>0.983</td></tr><tr><td>SCSR</td><td>34.17</td><td>0.989</td></tr><tr><td>FDSR</td><td>34.19</td><td>0.988</td></tr><tr><td>JDLSR</td><td>34.33</td><td>0.989</td></tr><tr><td>Proposed</td><td>34.75</td><td>0.991</td></tr></table></body></html>

表3bird 放大2倍超分辨率结果数据  

<html><body><table><tr><td></td><td>PSNR/dB</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>36.68</td><td>0.969</td></tr><tr><td>SCSR</td><td>38.38</td><td>0.982</td></tr><tr><td>FDSR</td><td>38.33</td><td>0.981</td></tr><tr><td>JDLSR</td><td>39.92</td><td>0.981</td></tr><tr><td>Proposed</td><td>40.69</td><td>0.985</td></tr></table></body></html>

表4child放大2倍超分辨率结果数据  

<html><body><table><tr><td></td><td>PSNR/dB</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>37.05</td><td>0.992</td></tr><tr><td>SCSR</td><td>38.38</td><td>0.996</td></tr><tr><td>FDSR</td><td>38.33</td><td>0.995</td></tr><tr><td>JDLSR</td><td>38.40</td><td>0.995</td></tr><tr><td>Proposed</td><td>38.46</td><td>0.998</td></tr></table></body></html>

表5Butterfly放大2倍超分辨率结果数据  

<html><body><table><tr><td></td><td>PSNR/dB</td><td>SSIM</td></tr><tr><td>Bicubic</td><td>27.46</td><td>0.909</td></tr><tr><td>SCSR</td><td>31.10</td><td>0.953</td></tr><tr><td>FDSR</td><td>31.23</td><td>0.954</td></tr><tr><td>JDLSR</td><td>31.33</td><td>0.954</td></tr><tr><td>Proposed</td><td>31.72</td><td>0.959</td></tr></table></body></html>

由表1\~5中数据可以看出，本文提出的算法相比于其他算法重构出的高分辨率图像有更好的客观质量。本文算法在PSNR 和 SSIM两方面均有明显的提升，其中PSNR 值有0.006\~0.77dB的提升，SSIM值有 $0 . 0 0 9 { \sim } 0 . 1 0 8$ 的提升。

为了进一步说明本文算法结果同时具有良好的主观视觉效果，列出bird、child 放大2倍以及butterfly、lena 放大4倍的高分辨率结果图像，因为bird的鸟嘴、bufferfly的翅膀纹络以及lena的帽沿有着锐利的边缘，bird的羽毛、child的眼睛和帽子有着丰富的纹理区域，本文通过对比这些区域的主观视觉效果来较全面的衡量本文算法的性能。

![](images/fc6cae7c774b1c88acc7e095914488ad4684a770821541d02a9022686de0e4ac.jpg)  
图6bird 放大2倍结果图

![](images/246fa0e8fc6036128aa7691bb21127d87c11c6ce37e13662ee33c0aace652022.jpg)  
图7child 放大2倍结果图  
图8lena放大4倍结果图

Ty 原图 Bicubic SCSR FDSR JDLSR Proposed

![](images/b82ca56c2fd9a0d5aa3bc717f6f89079cde4d2019e48716913769e3a810401cd.jpg)  
图9butterfly放大4倍结果图

从上面结果图像中可以看出，图6中本文算法重构出的鸟嘴嘴尖最下面的三角形处更加锐利，嘴角轮廓更加自然，图7小孩的眼眶轮廓更加清楚，瞳孔更加明亮自然。当放大倍数较大时，原图像经过降质得到的低分辨率图像所缺失的高频细节信息就越多，重构时恢复细节信息的过程也就越困难，因为本文方法在重构时引入图像的非局部自相似信息，所以可以有效的保持重构图像的边缘细节，由图8结果可以看出，其他方法结果图在lena帽沿处锯齿效应比较明显，而利用本文方法得到的高分辨率图像帽子边缘更加清晰，图9中butterfly翅膀有很多相似的纹络，这些相似块在重构过程中可以提供额外信息，由对比图可以看出本文方法得到的翅膀纹络更平滑真实，更加接近原图像。为了提高算法效率，本文采用的图像块的思想可能导致重构的图像具有块效应以及增加压缩感知本身的重构误差，从实验室结果表明，本文方法使用字典分类思想以及重构时引入图像的非局部自相似信息，避免了因图像块的思想带来的有效信息损失。

# 3 结束语

本文提出了一种压缩感知和相似性约束的图像超分辨率算法，该算法同时利用了图像的稀疏性和自相似性作为先验知识正则化重构过程。在利用外部图像库训练字典的过程中，提出一种基于测量域的特征字典分类方法，对外部图像库在测量域分别训练边缘特征字典和纹理特征字典，增强外部训练集与待重构图像之间的相似度；在重构时将图像块的稀疏性和自相似性同时作为重构过程的约束条件恢复出高分辨率图像。实验结果表明该算法重构出的图像细节真实丰富、边缘清晰，且主观效果良好。不过目前都是对单幅图像进行超分辨率重建，今后的进一步工作重心会将算法应用在视频超分辨率上，充分利用视频的空时相关性进行视频超分辨率算法研究，算法研究中需要降低外部光照对图像的影响、考虑视频序列帧间冗余信息的提取，以及如何对多帧视频序列进行配准，实现多帧图像的融合，最后得到重构图像主观质量和客观质量方面都有较好的效果。

# 参考文献：

[1]Yue Linwei, Shen Huanfeng,Li Jie,et al. Image super-resolution: The techniques,applications,and future [J]. Signal Processing,2016,128:389-

408.   
[2]Yang Jianchao,John Wright,Thomas S.Huang,et al.Image superresolution via sparse representation [J]. IEEE Trans on image processing, 2010,19 (11): 2861-2873.   
[3]He L,Qi H, Zaretzki R.Beta process joint dictionary learning for coupled feature spaces with application to single image super-resolution [C]// Procs of IEEE Conference on Computer Vision and Pattern Recognition. 2013: 345-352.   
[4]Yeganli F,Nazzal M, Ozkaramanli H. Selective super-resolution via sparse representations of sharp image patches using multiple dictionaries and bicubic interpolation [C]// Proc of Signal Processing and Communications Applications Conference.2015: 1957-1960.   
[5]尹东芹．压缩视频感知系统中测量域与频域信号的相关性研究[D]. 西安：西安电子科技大学,2013.   
[6] Gao Z, Xiong C, Zhou C,et al. Compressive sampling with coefficients random permutations for Image compression [C]// Proc of International Conference on Multimedia and Signal Processing.2011: 321-324.   
[7]Zhang Kaibing,Gao Xinbo,Tao,Dacheng,et al. Multi-scale dictionary for single image super-resolution [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2012:1114-1121.   
[8]Huang J B,Singh A,Ahuja N. Single image super-resolution from transformed self-exemplars [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2015: 5197-5206.   
[9]Anagin Y, Seke E,Adar N. Video super-resolution based on block motion estimation and gradient magnitude [C]//Proc of International Symposium on Innovations in Intelligent Systems and Applications.2015:1-6.   
[10] Pejman R, Demirel H, Anbarjafari G. Image resolution enhancement by using interpolation followed by iterative back projection [C]//Proc of Signal Processing and Communications Applications Conference.2013: 1-4.   
[11] Bevilacqua M,Roumy A, Guillemot C,et al. Low-complexity single-image super-resolution based on nonnegative neighbor embedding [J].British Machine Vision Conference,2012: 135-1.   
[12] Zeyde R,Elad M, Protter M. On single image scale-up using sparserepresentations [Cl//.Proc of International conference on curves and surfaces.2010:711-730.   
[13] Wang Huipeng，Zhou Lili,Zhang Jie.Region-based bicubic image interpolation algorithm[J]. Computer Engineering,2010,19:216-218.   
[14] Yang C Y, Yang MH. Fast direct super-resolution by simple functions [C]// Proc of IEEE International Conference on Computer Vision.20l3:561-568.   
[15] Li Xin,Zhu Min,Cui Ziguan,et al.A super-resolution algorithm based on adaptive sparse representation [C]/ Fuzzy Systemsand Knowledge Discovery.2015:1834-1838.