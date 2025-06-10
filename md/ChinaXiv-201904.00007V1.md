# 基于原型与正交投影学习的图像集分类算法

任珍文1²，吴明娜1

(1．西南科技大学 国防科技学院，四川 绵阳 621010;2.南京理工大学 计算机科学与技术学院，南京 210094)

摘要：为了利用图像集中的集合信息来提高图像识别精度以及对图像变化的鲁棒性，从而大幅降低诸如姿态、光照、遮挡和未对齐等因素对识别精度的影响,提出了一种用于图像集分类的图像集原型与投影学习算法(LPSOP)。该算法针对每个图像集学习有代表性的点(原型)以及一个正交的全局投影矩阵，使得在目标子空间的每个图像集可以被最优地分类到同类的最近原型集中。用学习到的原型来代表该图像集，既能降低冗余图像干扰，又能减少存储和计算开销，学习到的投影矩阵则能够大幅提高分类精度与噪声鲁棒性。在 UCSD/Honda、CMU Mobo和YouTubeCelebrities 这三个数据集上的实验结果表明，LPSOP比目前流行的图像集分类算法具有更高的识别精度和更好的鲁棒性。

关键词：图像集分类；原型学习；尺度学习；人脸识别；目标识别；模式识别中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.10.0843

Learning of prototype set and orthogonal projection for image set classification

Ren Zhenwen1,²,Wu Mingnal (1.Schoolof NationalDefenceScience&Technology,SouthwestUniversityofScience&Technology6210lo,China;2. Dept. of Computer Science,Nanjing University of Science & Technology, Nanjing 210o94, China)

Abstract: Inorder to improve the identificationaccuracyand the robustness by using colection information of the image set,hence greatlyreduces the influenceof posture,light,misalignment and soon.This paper developed a novel method, called learning prototype setand orthogonal projection for image set classification (LPSOP)，which simultaneouslylearns therepresentatives (prototypes)andalinear discriminative projectionforeach imageset,making anyimage set in the target subspacecan be clasified into its nearest neighbor prototype optimally.Inaddition,the leared representatives notonly reduceredundant image noise but also reduce the consumption of ime and memory.At the same time,the projection matrix greatly mproves the clasification accuracy and noise robustness.Experimental results on UCSD/Honda、CMU Mobo and YouTube databases prove that compared to state-of-the-art learing methods,LPSOP has higher recognition acuracyand better robustness.

Key words:image setclassification； prototype learning；scale learning；face recognition；target recognition；pattrm recognition

# 0 引言

随着计算机芯片技术的发展与图像获得途径越来越多样，基于单幅图像识别的传统方法暴露出精度不高、鲁棒性差的问题，不能满足自然环境下图像的变化。与基于单幅图像的识别技术相比，图像集分类则研究一段时间的视频帧序列或者在不同时间、场景、光照下采集的多幅图像。通过对图像集进行建模来选择合适的分类标准，这样易于消除不利因素的影响（如光照、姿态、遮挡等)，从而更有效的增强判别能力，提高识别率。因此，基于图像集的分类算法越来越广泛应用在人脸识别、目标识别以及安全监控等机器学习领域。

根据集合本身的特点，图像集分类面临的主要问题有两个，一个是集合的表示方法（建模)，一个是集合间相似度的度量。根据对图像集的建模方法进行划分，相关方法主要分为四类：基于统计模型的方法，比如ProNN[1]、Stiefel andGrassmannManifolds[2]；基于线性子空间的方法，比如DCC[3];基于非线性流形的方法，比如 $\mathrm { M M D } ^ { [ 4 , 1 8 ] }$ ；基于仿射子空间的方法，比如ProNN[1]（统计模型 $+$ 仿射子空间）、RNP[5]、AHISD与CHISD[7]。基于仿射包模型的图像集分类方法[1,5-8]，将图像集建模为仿射包，图像集之间的相似度被定义为两个仿射包中最近点之间的距离。这是一种几何方法，分类结果依赖于高维仿射空间中点的位置，图像集中的离群值将会大大降低分类精度。为了降低图像集仿射包模型松散导致的几何区域太大的问题，基于稀疏表示最近点的图像集分类方法[9,10]通过对字典稀疏线性表示来表示图像集，以稀疏重建残差来对图像集进行分类。正则化最近点方法[将每个图像集建模为一个正则化的仿射包。这些基于最近点的方法高度依赖图像集中每个样本的位置，同时离群值和噪声对模型的结果影响较大。为了降低这些影响，文献[11]利用协方差矩阵和黎曼核函数来表示图像集，利用图像集从黎曼流形到欧几里德空间的映射来测量图像集之间的相似性。考虑到图库集之间的相关性，文献[12\~14]提出基于图像集的协同表示方法进一步提高了识别精度。值得注意的是中科院王雯提出一种有效的图像集分类算法PDL[I5],PDL学习一个投影矩阵将样本从原始空间投影到目标子空间，接着在目标子空间内将图像集建模成仿射包，通过更新仿射系数来更新原型位置，学习得到的投影矩阵与原型联合优化分类性能。上述方法虽然取得了较好的分类效果，但仍然存在一些不足：a）需要样本满足某种概率统计分布;b)处理数据样本量大，计算、存储成本高;c)存在噪声或离群值时，算法的鲁棒性与分类精度低。近些年来，深度学习的出现，虽然在一些任务中取得了显著的成功，但它在图像集分类中的应用还很少。

针对以上问题，本文提出一种基于原型减少与正交投影的图像集分类算法（LPSOP)。对于每个图像集，首先通过稀疏表示和线性判别分析学习一组有代表性的样本作为初始化的基础原型，接着提出一种基于最小化分类误差概率的目标函数来同时学习最优化的原型和一个线性投影矩阵。最终学习到的代表点（原型）不仅能够最佳的描述图像集，而且还能降低计算时间、空间开销，学习到的正交投影矩阵，大幅度提高了原型集的判别能力。此外，为了进一步增强目标子空间中的稳定性和鲁棒性，投影矩阵约束为标准正交矩阵。为了同时开展优化原型和投影学习，本文发展了梯度下降算法，对原型集和投影矩阵进行交替迭代优化。与PDL不同，本文先利用Fisher判别准则学习基础原型而不是利用仿射包建模图像集，接着在更新原型位置的同时学习全局投影矩阵。通过在UCSD/Honda、CMUMobo和YouTubeCelebrities这三种数据集上与近年来八种流行图像集分类算法对比，证实了LPSOP具有更高的识别精度和鲁棒性。

# 1 方法

# 1.1基础原型学习

针对具有 $c$ 个图像集 $T = \{ T _ { 1 } , T _ { 2 } , . . . , T _ { c } \}$ （其中 $c = 1 , 2 , . . . , C$ ，$T _ { c } = \{ x _ { c , i } \} _ { i = 1 } ^ { n _ { c } }$ ， $x _ { c , i }$ 为第 $\mid c \mid$ 个类中的第 $i$ 张图像向量化得到的 $\textit { d }$ 维列向量）的分类场景，基于文献[16]，通过学习稀疏系数矩阵 $M = \{ M _ { 1 } , M _ { 2 } , . . . , M _ { c } \}$ （ $M _ { c }$ 是 $T _ { c }$ 对应的稀疏系数子矩阵)，得到 $T$ 的代表点子集 $P = \{ P _ { 1 } , P _ { 2 } , . . . , P _ { C } \}$ ? $( P \subseteq \mathrm { T } )$ ，其学习模型为

$$
\operatorname* { m i n } _ { M } \ \left\| T - T M \right\| _ { F } ^ { 2 } + \alpha \big \| M \big \| _ { 2 , 1 } + \beta f ( M )
$$

其中: $\Vert T - T M \Vert _ { F } ^ { 2 }$ 为重建误差项， $\| M \| _ { 2 , 1 }$ 表示 $\mathbf { \Omega } _ { M }$ 的混合 $l _ { 1 }$ 与 $l _ { 2 }$ 范数，$f ( M )$ 是一个关于系数矩阵 $M$ 的判别函数， $\alpha$ 和 $\beta$ 为标量化的平衡参数。

为了让类与类之间具有良好的判别能力，采用Fisher判别准则使类内离散度 $S _ { w } ( M )$ 最小化，类间离散度 $S _ { B } ( M )$ 最大化。其离散度计算公式如下：

$$
S _ { \boldsymbol { w } } ( M ) = \sum _ { c = 1 } ^ { C } \sum _ { m _ { k } \in M _ { c } } ( m _ { k } - \mu _ { c } ) ( m _ { k } - \mu _ { c } ) ^ { T }
$$

$$
S _ { B } ( M ) = \sum _ { c = 1 } ^ { C } n _ { c } ( \mu _ { c } - \mu ) ( \mu _ { c } - \mu ) ^ { T }
$$

其中： $m _ { k }$ 为 $\mathbf { \Omega } _ { M }$ 的第 $k$ 列， $\mu _ { c }$ 和 $\mu$ 分别为 $M _ { c }$ 和 $M$ 的均值向量，$n _ { c }$ 表示第 $\mid c \mid$ 类的样本个数。结合式（2）（3)，判别项 $f ( M )$ 定义为

$$
f ( M ) = t r ( S _ { \scriptscriptstyle W } ( M ) ) - t r ( S _ { \scriptscriptstyle B } ( M ) ) + \eta \| M \| _ { \scriptscriptstyle F } ^ { 2 }
$$

将式（4）代入式（1）中得到

$$
\operatorname* { m i n } _ { M } \ \left\| T - T M \right\| _ { F } ^ { 2 } + \alpha \big \| M \big \| _ { 2 , 1 } + \beta ( t r ( S _ { W } ( M ) ) - t r ( S _ { B } ( M ) ) + \eta \left\| M \right\| _ { F } ^ { 2 } )
$$

优化目标函数式（5）得到一个原型减少的代表性原型集$P = \{ P _ { 1 } , P _ { 2 } , . . . , P _ { C } \}$ ，代表性原型集 $P$ 不仅能够最佳地描述训练图像集集 $T$ ，还使得类之间具有很好的判别能力。针对实际应用场景中存在噪声或者离群点导致图像集分类精度和稳定性下降的问题，本文提出了一种同时学习原型和投影矩阵的算法，以进一步增强分类精度和鲁棒性。

# 1.2 目标函数的设计

通过1.1节的原型学习算法学习得到原始图像集 $T$ 对应的原型集 $P = \{ P _ { 1 } , P _ { 2 } , . . . , P _ { C } \}$ 后，LPSOP不仅优化 $P$ 中每个原型点的位置，还同时学习一个线性投影矩阵 $W$ 将原始空间中样本投影到低维的目标空间中，减少冗余特征，提高分类判别能力，图1所示为本文算法的原理框图。对于任意一张样本图像 $\boldsymbol { x } \in { T } _ { c }$ ，通过 $W$ 投影映射表示为

$$
y = W ^ { T } x \in \mathbb { R } ^ { m } ( m < d )
$$

本文设计基于近邻（NN）分类误差估计的目标函数$J ( W , P )$ 来同时学习得到一个优化的原型集 $P$ 和线性投影矩阵 $W$ 。目标函数定义如下：

$$
J ( W , P ) = { \sum _ { c = 1 } ^ { C } } { \sum _ { x \in T _ { c } } } S _ { \beta } ( Q _ { x } )
$$

其中： $S _ { \beta } ( z )$ 为step 函数，当 $z \leq 1$ 时， $s t e p ( z ) = 0$ ，否则 $s t e p ( z ) = 1$ 。从分类角度看， $J$ 可以看做是分类误差和，因此本文求解优化问题 $\operatorname* { m i n } J ( W , P )$ 。但是此函数不可微，为了保证能使用梯度下降法来同时学习得到最优的原型集 $P ^ { * }$ 和线性投影矩阵 $\boldsymbol { W } ^ { * }$ ，本文使用斜率为 $\beta$ ，中心 $z = 1$ 的 Sigmoid函数来近似替代 step函数，其定义如下：

$$
S _ { \beta } ( z ) = \frac { 1 } { 1 + e ^ { \beta ( 1 - z ) } }
$$

当 $\beta$ 很大时， $S _ { \beta } ( z ) \approx s t e p ( z )$ 。 $S _ { \beta } ( z )$ 的导数 ${ S _ { \beta } } ^ { \prime } ( z )$ 如下：

$$
S _ { \beta } ^ { ' } ( z ) = \frac { d ( S _ { \beta } ( z ) ) } { d z } = \frac { \beta e ^ { \beta ( 1 - z ) } } { ( 1 + e ^ { \beta ( 1 - z ) } ) ^ { 2 } }
$$

${ S _ { \beta } } ^ { \prime } ( z )$ 是一个“窗口”函数,当 $z = 1$ 时达到最大值。 $\left| z - 1 \right| \gg 0$ 时消失。如果 $\beta$ 的值较大， $\varphi _ { \beta } ^ { \prime } ( z )$ 则近似于狄拉克 $\delta$ 函数，而如果 $\beta$ 较小， $\varphi _ { \beta } ^ { \prime } ( z )$ 在 $z$ 的可取值范围内近似为常数。此外，本文定义如下判别函数 $Q _ { x }$ ：

$$
Q _ { x } = \frac { \left\| y - n n _ { w } ^ { c } ( y ) \right\| _ { 2 } } { \left\| y - n n _ { b } ^ { c } ( y ) \right\| _ { 2 } }
$$

其中： $n n _ { w } ^ { c } ( y )$ ， $n n _ { b } ^ { c } ( y )$ 分别为在投影目标子空间中与 $y$ 属于同一个类和不同类的最近邻原型。他们分别定义为

$$
\begin{array} { r l } { n n _ { w } ^ { c } ( y ) = W ^ { T } a , } & { a = \underset { a \in P ^ { \backslash } P _ { c } } { \arg \operatorname* { m i n } } \left\| y - W ^ { T } a \right\| _ { 2 } } \\ & { } \end{array}
$$

![](images/4147d0415a9b6f6376b516ba868e05800d591ee08b46ac190bd84133991462f2.jpg)  
图1LPSOP 原理框图  
Fig.1Block diagram of LPSOP

在原始空间中，与 $y$ 属于同一类的样本和不属于同一类的样本通过投影矩阵 $W$ 投影到目标子空间后得到两个集合，从这两类集合中各自选择一个最近邻原型点，得到原型点$n n _ { w } ^ { c } ( y )$ 与 $n n _ { b } ^ { c } ( y )$ 。 $\mathbf { \Delta } _ { a }$ 与 $b$ 分别为最近邻原型点 $n n _ { w } ^ { c } ( y )$ ， $n n _ { b } ^ { c } ( y )$ 在原始空间中对应的样本。此外，对于所有的 $x$ ,若 $Q _ { x } > 1$ ，目标函数的函数值则近似为零，此时认为 $x$ 被正确分类；反之， $x$ 被认为错误分类。为了进一步增强目标子空间的稳定性和鲁棒性，本文在投影W上施加正交约束，即 $W ^ { T } W = I$ （ $I$ 为单位矩阵)。

# 1.3算法优化

为了得到最优的原型集 $P ^ { * }$ 和线性投影矩阵 $\boldsymbol { W } ^ { * }$ ，本文发展了一种交替梯度下降法来最小化目标函数 $J$ ，即：分别求出 $J$ 关于 $W$ 和 $P$ 的偏导数，并进行交替迭代更新。考虑到对$Q _ { x }$ 的定义中涉及到 $W$ 和 $P$ ，此外，对于一些 $x \in T _ { c }$ ，当 $W$ 和 $P$ 的位置发生变化时， $n n _ { w } ^ { c } ( y )$ 和 $n n _ { b } ^ { c } ( y )$ 也会改变。不难发现，对最近邻原型的搜索过程依赖 $W$ 和 $P$ 。由于当 $W$ 和 $P$ 的位置发生变化时,尽管 $n n _ { w } ^ { c } ( y )$ 和 $n n _ { b } ^ { c } ( y )$ 也会改变。其中还存在不连续、依赖关系隐晦的问题，因此本文假设当投影和原型位置其中一个发生很小的变化时，另外一个保持不变，即在求解优化问题时，可以固定 $W$ 后求解 $P$ ，也可以在固定 $P$ 之后求解 $W$ 。在上述近似下，可得到 $J$ 关于 $W$ 的偏导数:

$$
\begin{array} { r l r } {  { \frac { \hat { \sigma } J } { \hat { \sigma } W _ { k } } \approx \sum _ { c = 1 } ^ { C } \sum _ { x \in T _ { c } } \frac { S _ { \beta } ^ { \prime } ( Q _ { x } ) Q _ { x } } { \| y - n n _ { w } ^ { c } ( y ) \| _ { 2 } ^ { 2 } } ( x - a ) ( y _ { k } - n n _ { w } ^ { c } ( y ) _ { k } ) } } \\ & { } & { - \sum _ { c = 1 } ^ { C } \sum _ { x \in T _ { c } } \frac { S _ { \beta } ^ { \prime } ( Q _ { x } ) Q _ { x } } { \| y - n n _ { b } ^ { c } ( y ) \| _ { 2 } ^ { 2 } } ( x - b ) ( y _ { k } - n n _ { b } ^ { c } ( y ) _ { k } ) } \end{array}
$$

式（12）中 $W _ { k } \in R ^ { d }$ 为 $W$ 的第 $k$ 列， $y _ { k }$ 为向量 $y$ 的第 $k$ 个元素。对于第 $k$ 类图像集 $T _ { k }$ ，最优原型集 $P _ { k } = \{ p _ { k , i } \}$ ，则 $J$ 关于 $p _ { k , i }$ 的偏导数如下：

$$
\begin{array} { c } { { \displaystyle { \frac { \partial J } { \partial p _ { k , i } } \approx \sum _ { c = 1 } ^ { c } \sum _ { \displaystyle x \in T _ { c } } \frac { S _ { \beta } ^ { \prime } ( Q _ { x } ) Q _ { x } } { \| y - n n _ { w } ^ { c } ( y ) \| _ { 2 } ^ { 2 } } W W ^ { T } ( a - x ) } } } \\ { { - \displaystyle { \sum _ { c = 1 } ^ { c } \sum _ { \displaystyle x \in T _ { c } } \frac { S _ { \beta } ^ { \prime } ( Q _ { x } ) Q _ { x } } { \| y - n n _ { b } ^ { c } ( y ) \| _ { 2 } ^ { 2 } } } } } \end{array}
$$

通过式（12）（13）得到梯度下降更新方程为（其中／，$\nu$ 分别为学习步长因子)

$$
W _ { k } ^ { ( t + 1 ) } \ = \ W _ { k } ^ { ( t ) } - \gamma \frac { \hat { \sigma } J } { \hat { \sigma } W _ { k } }
$$

$$
P _ { c } ^ { ( t + 1 ) } = P _ { c } ^ { ( t ) } - \nu \frac { \hat { \sigma } J } { \hat { \sigma } P _ { c } }
$$

# 1.4分类

首先利用1.3节的优化方法，以图库集作为输入，学习得到最优的原型集 $\boldsymbol { P } ^ { * }$ 和线性投影矩阵 $\boldsymbol { W } ^ { * }$ ，接着将测试集与原型集 $\boldsymbol { P } ^ { * }$ 利用线性投影矩阵 $\boldsymbol { W } ^ { * }$ 转换到目标空间，然后计算目标空间中测试图像集和原型集之间的距离，即测试集样本与图库集中相应原型之间的最短欧式距离，最后将测试集划分到最近原型所在的图像集所属的类中，完成图像集的分类。

# 2 实验

为了验证本文提出的图像集分类算法LPSOP的有效性，本文在三种公开数据库上对比分析了近年来八种流行的图像集分类算法，并记录各自的分类精度与标准差。

# 2.1图像集以及样本设置

本文使用UCSD/Honda[17]、CMU Mobo[18]和 YouTubecelebrities(YTC)[19]这三个数据集来开展算法评估。

UCSD/Honda数据集包含20名对象共59个视频，视频中的每个图像均发生了姿态、光照和表情的变化。数据集中每幅人脸图像被重新调整为 $2 0 \times 2 0$ 的灰度图像，并用直方图均衡化处理[20]，所有的视频序列被分成两组，随机选取20个视频序列作为训练集，剩下的39个序列为测试集。

CMUMobo数据集包含了来自24名对象的96个视频序列，每名对象包含4个视频序列,每个序列分别对应着一种行走模式。首先使用Viola-Jonesfacedetector框架提取人脸，然后将人脸重新调整为 $3 0 \times 3 0$ 的灰度图像，最后从每个对象的视频中随机选取一个图像集作为训练集，剩下的作为测试集。

![](images/033841a7efd38627f578fef2e8136e82bf2f96ebe82ba93b7bf38d1a8ba3b44b.jpg)  
图2YTC 数据集部分样本 (每一行属于同一个图像集)  
rig.∠rart sainpies ol r iC(eacn row beiongs to tne saine iage set)

YTC数据集由47位名人的1910个视频组成，其中视频序列中的每个对象均发生较大姿态、光照和表情变化。由于数据集中的视频大多分辨率低、姿态变化大、光照强度各异，因此这个数据集与前面两个相比更具有挑战性。对于该数据集，本文将提取的脸部区域调整为 $2 0 \times 2 0$ 灰度的图像。在每一段视频中随机选取3个图片集合作为训练集，随机挑选6个图片集合作为测试集，如图2所示为YTC样本图像，其中每一行的人脸照片来自同一个图像集（YTC数据集为自然条件下采集的图像，图像质量不高，含有噪声，因此可以利用该数据库测试识别精度与鲁棒性）。

# 2.2对比算法和参数设置

为了证实LPSOP方法的有效性，本文与多种流行的图像集分类算法比较进行比较，这些算法包括DCC[3]、 $\mathbf { M M D } ^ { [ 2 1 ] }$ 、AHISD[7]、CHISD[7]、SANP[6]、RNP[5]、SSDML[22]、PDL[15],这些算法的源代码可以在各个作者的主页上下载得到。为了实验结果公平，各个算法相关参数按照各自参考文献中推荐的实验参数进行配置。在本文的实验中，每个图像集都由随机选择的50、100或200张人脸图片组成集合，所有实验结果的分类精度与标准差均为进行10次实验后求均值得到。此外，本文设置 $\scriptstyle \alpha = 0 . 1$ ， $\beta { = } 0 . 1$ ， $\scriptstyle \eta = 1$ 以及将线性投影矩阵 $\boldsymbol { \mathcal { W } }$ 的投影维度设置为100维。

# 2.3 实验结果与分析

本文首先在UCSD/Honda数据库上进行实验，设置图像集大小分别为50、100和200，测试LPSOP的识别精度与标准差。表1为对比LPSOP与其他流行的八种算法在UCSD/Honda数据集上的实验结果。从表1可知，LPSOP比其他相关算法具有更高的识别精度与更低的标准差，证明了本文算法的有效性。值得注意的是RNP、PDL以及LPSOP在图像集大小为200时识别率均为 $100 \%$ 。

表1在UCSD/Honda上的分类精度与标准差数据对比 $( \% )$ 0

Table 1 Classification accuracy and standard deviation data on   

<html><body><table><tr><td colspan="3">UCSD/Honda (%)</td><td></td></tr><tr><td>算法</td><td>50</td><td>100</td><td>200</td></tr><tr><td>DCC</td><td>77.1±3.5</td><td>83.8±2.5</td><td>92.2±2.2</td></tr><tr><td>MMD</td><td>68.9±4.4</td><td>86.3±2.0</td><td>92.2±2.1</td></tr><tr><td>AHISD</td><td>87.4±2.6</td><td>84.6±3.6</td><td>88.9±1.9</td></tr><tr><td>CHISD</td><td>82.2±2.4</td><td>84.4±1.9</td><td>91.8±1.8</td></tr><tr><td>SANP</td><td>84.3±2.9</td><td>91.8±3.2</td><td>94.5±3.0</td></tr><tr><td>SSDML</td><td>83.8±2.0</td><td>84.3±2.0</td><td>81.4±3.3</td></tr><tr><td>RNP</td><td>87.2±3.1</td><td>95.1±3.0</td><td>100.0±0.0</td></tr><tr><td>PDL</td><td>90.1±2.1</td><td>95.9±2.3</td><td>100.0±0.0</td></tr><tr><td>LPSOP</td><td>91.8±1.9</td><td>96.1±1.3</td><td>100.0±0.0</td></tr></table></body></html>

# 表2在CMUMobo上的分类精度与标准差数据对比（ $( \%$ ）

Table 2 Classification accuracy and   

<html><body><table><tr><td>算法</td><td>50</td><td>100</td><td>200</td></tr><tr><td>DCC</td><td>81.7±3.2</td><td>83.5±2.7</td><td>90.4±2.3</td></tr><tr><td>MMD</td><td>91.1±2.5</td><td>93.5±2.2</td><td>95.5±0.9</td></tr><tr><td>AHISD</td><td>90.8±2.7</td><td>93.9±2.1</td><td>91.7±2.6</td></tr><tr><td>CHISD</td><td>91.5±3.4</td><td>93.1±2.5</td><td>97.4±2.2</td></tr><tr><td>SANP</td><td>91.8±3.0</td><td>94.8±1.6</td><td>97.2±1.5</td></tr><tr><td>SSDML</td><td>91.2±3.1</td><td>95.1±2.3</td><td>97.4±2.7</td></tr><tr><td>RNP</td><td>91.7±2.8</td><td>94.6±1.2</td><td>97.6±1.5</td></tr><tr><td>PDL</td><td>94.4±2.0</td><td>95.4±1.7</td><td>96.4±1.6</td></tr><tr><td>LPSOP</td><td>94.7±1.6</td><td>97.2±0.9</td><td>98.3±0.9</td></tr></table></body></html>

接着，本文在CMUMobo数据库上进行实验，同样测试LPSOP在图像集大小分别为50、100和200时的识别精度与标准差。表2为LPSOP与其他算法的对比数据，从数据中可以看出LPSOP仍旧具有最好的分类性能。相比于UCSD/Honda,CMUMobo数据库更具有挑战性，但是LPSOP的识别率仍旧可以高达 $96 . 7 3 \%$ ，比同类型的方法PDL平均精度高出 $1 . 3 3 \%$ 。

最后，本文在更具挑战性的YTC数据库上进行实验，图像集大小设置与上面的实验一致，即分别为50、100和200。表3展示了最终的实验结果。从表中可以得出LPSOP比其他流行算法具有更好的性能，当图像集大小为50、100和200时，分类精度分别比次好的算法高出 $0 . 5 \%$ 、 $1 \%$ 和 $0 . 5 \%$ 。特别时当图像集大小较小时（50与100)，LPSOP更具优势。

表3在YouTube上的分类精度与标准差数据对比 $( \%$ ）

Table 3Classification accuracy and standard deviation data on   

<html><body><table><tr><td colspan="4">YouTube(%)</td></tr><tr><td>算法</td><td>50</td><td>100</td><td>200</td></tr><tr><td>DCC</td><td>68.8±3.0</td><td>73.5±4.4</td><td>75.7±2.3</td></tr><tr><td>MMD</td><td>70.0±3.5</td><td>71.7±4.5</td><td>76.2±4.4</td></tr><tr><td>AHISD</td><td>73.5±5.6</td><td>72.8±7.6</td><td>68.9±4.4</td></tr><tr><td>CHISD</td><td>72.6±5.7</td><td>73.3±5.3</td><td>74.6±4.9</td></tr><tr><td>SANP</td><td>73.4±4.1</td><td>74.9±6.0</td><td>78.4±4.3</td></tr><tr><td>SSDML</td><td>68.4±5.6</td><td>68.1±5.3</td><td>72.5±4.2</td></tr><tr><td>RNP</td><td>75.3±5.4</td><td>75.3±5.0</td><td>77.7±5.2</td></tr><tr><td>PDL</td><td>74.3±3.4</td><td>75.2±3.8</td><td>77.4±3.3</td></tr><tr><td>LPSOP</td><td>75.8±2.6</td><td>76.3±3.6</td><td>78.9±2.5</td></tr></table></body></html>

本文提出的原型减少与正交投影学习方法同时学习最优化原型和一个线性投影矩阵。学习到的原型集合能够很好的描述图像集中的样本结构与特征，线性投影矩阵则可以看做是一种全局尺度，能够很好的提高算法精度与鲁棒性。为了展示本文算法学习的结果，以YTC数据库为例，图3给出了部分学习到的原型对应的图像，其中每一行属于同一个原型集，从图中可以看出，学习到的原型具有人脸的重要的轮廓与标志信息。图4给出了投影矩阵W（ $4 0 0 \times 1 0 0 )$ ，通过该矩阵对应的图像能够看出，矩阵的元素值不尽相同，说明该线性投影矩阵作为一种全局尺度贡献了权重。

![](images/e9b190c48fa153798758ebdc9a65c27414478d378ef939fb49bed9f745e7e239.jpg)  
图3学习到的部分原型(每一行来自同一个原型集) Fig.3Part of the prototypes learned (each row comes from the same prototype set)

![](images/e472dcc2855793420ff8d6986d7359922a06d8a54650a0dbbd07f6c63320771c.jpg)  
图4学习到的全局线性投影矩阵W Fig.4Learned global linear projection matrix W

# 2.4算法收敛性

本文没有直接证明LPSOP算法的收敛性质，但是通过实验分析，该算法具有快速和平滑的收敛特性。在YTC数据库上测试时收敛曲线如图5所示，随着迭代的进行，大约30次后损失函数的值就趋于稳定，说明该算法具有较好的收敛特性。

![](images/66096706987f5c3759c8d1cbd0cf18e5f8350ec1f6ef69b44f665f766f396831.jpg)  
图5收敛曲线Fig.5Convergence curve

# 2.5 问题与改进方向

由表1\~3可知，与其他八种图像集分类方法相比，LPSOP在这三个数据集上具有最高的识别精度与最低的标准差。这主要归功于本文在以下两个方面的创新：a）通过稀疏表示和线性判别分析学习一组有代表性的原型点；b)同时学习最优的原型集和一个全局的线性投影矩阵提高了图像集的判别能力。但是LPSOP可能存在过拟合的问题，后续拟增加正则项来改进LPSOP，比如引入 $l _ { 2 }$ 正则、 $l _ { 1 }$ 稀疏正则、 $l _ { 2 1 }$ 结构化稀疏正则。

# 3 结束语

本文提出了一种用于图像集分类的图像集原型与尺度学习算法（LPSOP)。该算法同时学习图像集的原型集合和一个线性投影矩阵，最终学习到的原型（代表点）集合能够最佳的描述图像集，学习到的正交投影矩阵则大幅度提高原型集的判别能力。此外，为了进一步增强目标子空间中的稳定性和鲁棒性，投影矩阵约束为标准正交矩阵。为了同时开展优化原型和投影学习，本文发展了梯度下降算法，对原型集和投影矩阵进行交替迭代优化。该算法在三种公开数据集上进行了实验，实验结果表明与其他目前比较先进的算法相比，LPSOP在图像集分类上有更高的识别精度和更好的鲁棒性。但是本文并没有考虑到图库集本身包含的隐藏的可利用特征下一步可以采用相关低秩算法捕获隐藏的特征进一步提高算法的识别精度。

# 参考文献：

[1]Wang Wen,Wang Ruiping,Shan Shiguang,et al.Probabilistic nearest

neighbor search for robust classification of face image sets [Cl//Proc of IEEE International Conference and Workshops on Automatic Face and Gesture Recognition.Washington DC:IEEE Computer Society,2015: 1-7.   
[2]Turaga P, Veeraraghavan A,Srivastava A,et al. Statistical computations on Grassmann and stiefel manifolds for image and video-based recognition [J]． IEEE Trans on Pattern Analysis and Machine Intelligence,2011,33(11): 2273-2286.   
[3]Kim TK,Kittler J,Cipolla R.Discriminative learning and recognition of image set classes using canonical correlations [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2007,29(6):1005-1013.   
[4]Du Jixiang, Shao Meiwen,Zhai Chuanmin,et al.Recognition of leaf image set based on manifold-manifold distance [J]. Neurocomputing, 2016,188(5): 131-138.   
[5]Yang Meng,Zhu Pengfei, Van Gool L,et al.Face recognition based on regularized nearest points between image sets [C]/Proc of IEEE International Conference and Workshops on Automatic Face and Gesture Recognition.Washington DC:IEEE Computer Society,2013: 1-7.   
[6] Hu Yiqun，Mian A S,Owens R.Face Recognition using sparse approximated nearest points between image sets [J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2012,34(10):1992-2004.   
[7]Cevikalp H, Triggs B.Face recognition based on image sets [C]//Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition.Washington DC: IEEE Computer Society,2011: 2567-2573.   
[8] Cheng Gong,Zhou Peicheng,Han Junwei. Duplex metric learning for image set classification [J]. IEEE Trans on Image Processing,2018,27 (1): 281-292.   
[9]马建红，张晗，季秋．利用协方差矩阵法表示深度图像集的鲁棒人 脸识别[J]．计算机应用研究,2016,33(12):3847-3851.(Ma Jianhong, Zhang Han,Ji Qiu.Robust face recognition using block based on covariance matrix to represent depth image set [J].Application Research of Computers,2016,33(12):3847-3851.)   
[10] Lu Jiwen,Wang Gang,Deng Weihong,et al. Simultaneous feature and dictionary learning for image set based face recognition [J].IEEE Trans on Image Process,2017,26 (8): 4042-4054.   
[11] Wang Ruiping,Guo Huimin Larry S D,et al. Covariance discriminative learning: a natural and efficient approach to image set classification [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition． Washington DC:IEEE Computer Society，2012: 2496-2503.   
[12] Cai Sijia,Zhang Lei,Zuo Wangmeng，et al.A probabilistic [C]// Proc of IEEE Conference on Computer Vision and Pattrn Recognition. Washington DC:IEEE Computer Society，2016: 2950-2959.   
[13] Li Feng, Zhang Sanyuan. Laplacian sparse coding dictionary for image set based collaborative representation [C]//Proc of the 2nd IEEE International ConferenceonComputerand Communications. Piscataway,NJ: IEEE Press,2016: 245-249.   
[14] Uzair M, Shafait F,Ghanem B,et al.Representation learning with deep extreme learning machines for efficient image set classification [J]. Neural Computing and Applications,2018,30(4):1211-1223.   
[15] Wang Wen，Wang Ruiping， Shan Shiguang，et al. Prototype discriminative learning for face image set classification [C]//Proc of Asian Conference on Computer Vision. Cham:Springer,2016:344-360.   
[16] WangBaoxing，Yin Qiyue,WuShu，et al.Discriminative RepresentativeSelectionviaStructureSparsity[C]//Procof International Conference on Pattern Recognition. Washington DC: IEEE Computer Society,2014: 1401-1406.   
[17] Lee K C,Ho J,Yang MH,et al. Video-based face recognition using probabilistic appearance manifolds [C]/Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2003:313-320.   
[18] Hayat M,Khan S H,Bennamoun M. Empowering simple binary classifiers for image set based face recognition [J]. International Journal of Computer Vision,2017,123(3): 479-498.   
[19] Kim M,Kumar S,Pavlovic V,et al.Face tracking and recognition with visual constraints in real-world videos [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2008:1-8.   
[20]刘雅莉，许鹏飞．一种模糊核聚类的线性滤波多光谱图像增强算法 [J]．计算机应用研究,2015,32(5):1536-1539.(Liu Yali,Xu Pengfei. Linear filtering multispectral image enhancement algorithm with fuzzy kermel clustering [J].Apication Research of Computers,2015,2(5): 1536-1539.)   
[21] Wang Ruiping,Shan Shiguang,Chen Xilin,et al. Manifold-manifold distance with application to face recognition based on image set [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition. Washington DC:IEEE Computer Society,2008: 1-8.   
[22] Zhu Pengfei,Zhang Lei, Zuo Wangmeng,et al. From Point to Set: Extend the Learning of Distance Metrics [C]//Proc of IEEE International Conference on Computer Vision.Washington DC:IEEE Computer Society,2013: 2664-2671.