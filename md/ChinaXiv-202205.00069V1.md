# 贪心非对称深度有监督哈希图像检索方法

赵昕昕，李阳，苗壮，王家宝，张睿(陆军工程大学 指挥控制工程学院，南京 210007)

摘要：近年来，深度有监督哈希检索方法已成功应用于众多图像检索系统中。但现有方法仍然存在一些不足：一是大部分深度哈希学习方法都采用对称策略来训练网络，但该策略训练通常比较耗时，难以用于大规模哈希学习过程；二是哈希学习过程中存在离散优化问题，现有方法将该问题进行松弛，但难以保证得到最优解。为解决上述问题，提出了一种贪心非对称深度有监督哈希图像检索方法，该方法将贪心算法和非对称策略的优势充分结合，进一步提高了哈希检索性能。在两个常用数据集上与17种先进方法进行比较。在CIFAR-10数据集上48比特条件下，与性能最好的方法相比mAP提高 $1 . 3 \%$ ；在NUS-WIDE数据集上所有比特下，mAP平均提高 $2 . 3 \%$ 。在两个数据集上的实验结果表明，所提方法可以进一步提高哈希检索性能。

关键词：非对称策略；贪心算法；有监督哈希；图像检索 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.03.0076

Greedy-asymmetric deep supervised hashing for image retrieval

Zhao Xinxin, Li Yang, Miao Zhuang†, Wang Jiabao, Zhang Rui (Command & Control Engineering Collge,Army Engineering Universityof PLA,Nanjing 210007,China)

Abstract: Inrecent years,thedeepsupervised hash retrieval method have been successfullyapplied to many imageretrieval systems.However,theexisting methods stillhave some shortcomings:First,mostof the deep hash learning methods use symmetricstrategiestotrainthe network,butthetrainngofthisstrategyisusualltime-consumingand dificult tobeused inthelarge-scalehashlearingproces;Second,thereisadiscreteoptimizatioprobleminthehashlearningprocess.Existing methods relaxthis problemanditisdificultguaranteetheoptimalsolution.Inorder tosolvetheaboveproblems,this paper proposes a greedy-symmetric dep supervised hashing method for image retrieval,which fullycombines the advantagesof the greedyalgorithmand asymmetric strategyto further improve the hash retrieval performance.Thisarticlecompares 17 state-of-the-art methodsontwocommonlyused datasets.Compared withthe state-of-the-art methods,the propoed method increases the mAP in 48-bits setting by $1 . 3 \%$ on CIFAR-10 dataset.And on NUS-WIDE dataset,increases the mAP in all-bits setting by increased $2 . 3 \%$ on average.The experimental results show thatthe propoed method can further improve the performance of hash retrieval.

Key words: asymmetric strategy; greedy algorithm; supervised hashing; image retrieval

# 0 引言

随着图像数据的爆炸性增长，如何从海量数据中寻找所需要的信息已经成为一个至关重要的问题。在大规模图像检索中，由于哈希检索方法[1]在计算和存储方面具有高效性[2]，因此基于哈希特征的近似最近邻搜索方法[3]受到了广泛关注。

近年来，许多哈希检索方法已经被提出，它们可以分为数据无关[4]和数据相关方法[5]。数据无关方法主要是依靠随机映射来构造哈希函数，而哈希函数构造过程通常不依赖于训练数据，因此该类方法的检索精度较低[。数据相关方法利用各种机器学习技术来学习哈希函数。与数据无关方法相比，数据相关方法能够利用更短的哈希码达到更高的精度[7]因此，数据相关方法比数据无关方法得到了更加广泛的应用。

由于深度神经网络在图像分类[8]、目标检测[9]、人脸识别[10]等众多任务[1]中的成功应用，研究人员试图通过深度学习来解决哈希问题，并提出了深度有监督哈希学习方法。深度有监督哈希学习方法是通过深度神经网络提取出图像特征，并同时进行哈希学习的一类方法[12,13]。该类方法将特征提取和哈希学习集成到同一个端到端框架中[14]，使得哈希编码的检索性能相对于传统方法得到了大幅提升。

尽管深度有监督哈希学习方法已经取得了巨大的进步，但依然存在许多不足[15,16]。现有的深度有监督哈希学习方法大部分在训练过程中采用对称策略，例如，CNNH[17](Convolutional Neural Networks Hashing)、 $\mathrm { \Delta D P S H ^ { [ 1 8 ] } }$ (DeepPairwise Supervised Hashing)、DHN[19](Deep Hashing Network)等。对称策略是指使用相同的深度神经网络对查询样本点和数据集合样本点进行深度特征提取，再使用相同的深度哈希函数为查询样本点和数据集合样本点生成哈希码。采用对称策略的哈希学习方法的训练通常比较耗时，这使得它们很难有效地利用监督信息来处理大规模数据集合。例如，DPSH方法[18]的存储和计算成本是 $O ( n ^ { 2 } )$ ，其中 $n$ 是数据集合样本点的数量；DTSH[20]方法(Deep Supervised Hashing with Triplet)的训练成本甚至更高。由于采用对称策略训练网络比较耗时，所以为了使训练切实可行，大多数现有的方法只从整个数据集合中抽取一个子集来构建哈希函数学习的训练集，而其余数据集合样本点则被丢弃。采用以上策略虽然能够加速网络训练，但是会出现监督信息利用不充分问题[21]。

在早期关于非对称哈希[22,23]的研究工作中，它们使用非对称距离度量来保持图像之间的相似度，其中训练集和查询集的二进制哈希码是由需要学习的相同的哈希函数生成的。受上述非对称思想启发，后续工作中又提出了一些深度非对称哈希方法，如 Deep Asymmetric Pairwise Hashing[24]、Nonlinear Asymmetric Multi-valued Hashing[25]、Collaborativelearning for extremely low bit Asymmetric Hashing[26]、DeepAsymmetric Hashing with Dual Semantic Regression and ClassStructureQuantization[27]和基于非对称监督深度离散哈希的图像检索[28]等。其中ADSH[21]方法采用非对称方式进行深度哈希学习。非对称方式是指特征提取仅仅只对查询样本点执行，而不对数据集合样本点执行。在深度哈希函数学习过程中只学习查询样本点的哈希码，而数据集合样本点的哈希码则是直接学习得到。该方法所提的非对称方式能够有效解决上述监督信息利用不充分问题。

虽然ADSH方法通过非对称方式能够充分利用监督信息并实现高效地训练网络，但由于该方法在哈希码学习过程中，需要使用sign 函数(sign 函数不可导)将深度特征映射为二值化哈希码，进而使得该优化问题变成NP难问题。ADSH方法在训练阶段使用tanh 函数替换sign 函数进行松弛[29]，并在损失函数中添加一个惩罚项来生成尽可能离散的特征[18,30]，然后在测试阶段再使用sign 函数来获得真正的二进制哈希码。虽然这样能够训练网络，但该方法会引入量化误差。为了更好求解离散优化问题，GreedyHash[31]方法利用贪心原理在正向传播中严格使用sign函数保持对网络输出的离散约束，而在反向传播中，哈希层梯度被完整地传送到前层，进一步避免了梯度消失。

在ADSH和GreedyHash方法的启发下，本文提出一种贪心非对称深度有监督哈希图像检索方法。该方法将贪心算法和非对称策略同时应用到哈希函数的学习过程中，使得该学习过程即可充分利用监督信息又能更好求解离散优化问题具体地，本文的主要贡献包括以下3个方面：

a)提出了一种贪心非对称深度有监督哈希图像检索方法，该方法将贪心算法和非对称策略的优势充分结合，进一步提高了哈希检索性能。

b)设计了一种贪心非对称成对损失，该损失函数包括贪心损失和非对称成对损失两部分。贪心损失通过在前传过程中保持对网络输出的离散约束，在反传过程中将哈希层的梯度完全传送到网络输出层，进一步解决离散优化问题。非对称成对损失通过采用非对称策略对查询样本点和数据集合样本点使用不同策略进行学习，进一步提高了哈希码学习效率。

c)在两个数据集上的实验结果表明，贪心非对称深度有监督哈希图像检索方法可以进一步提高哈希检索性能。

# 1 特征提取

图1展示了贪心非对称深度有监督哈希图像检索方法的模型结构。该模型结构主要包括两部分：特征提取部分和损失函数部分。特征提取部分的主要作用是通过一个骨干网提取出图像的深度特征。损失函数部分主要作用是通过哈希学习将图像深度特征映射成哈希码。如图1所示，训练图像首先在特征提取阶段得到图像的深度特征，其次通过哈希层得到图像的二进制哈希码，最后通过所设计的损失函数指导网络训练生成能够保留图像相似性的哈希码。该方法将两部分融入到同一个端到端的结构中，使得模型在训练过程中各部分可实现相互反馈，实现了更加鲁棒的哈希编码。

![](images/a4b870216912b0beb46507d183c5de2b5ec40330f90e1ce99c3a172c8323a6dd.jpg)  
图1本文方法总体架构  
Fig.1The overall framework of the proposed method

值得注意的是，本文设计的损失函数包括两部分：贪心损失和非对称成对损失。如图1中贪心损失 $L _ { \mathrm { 1 } }$ 所示，得到图像的哈希特征后直接使用sign函数将哈希特征映射成二进制哈希码，再通过贪心原理解决离散优化问题，具体实现过程如2.1节所示。如图1中非对称成对损失 $L _ { 2 }$ 所示，该部分同时使用查询图像与数据集合图像的监督信息对网络进行训练，并在训练过程中能够学习得到数据集合图像的二进制哈希码。该部分具体实现过程如2.2节所示。

如图1中特征提取阶段所示，为了提取图像的深度特征，本文采用AlexNet[8]作为骨干网进行特征提取。AlexNet骨干网包括5个卷积层和3个全连接层(结构如表1所示)。为了得到图像的哈希特征，本文在AlexNet骨干网的FC3层后添加一个哈希编码层，它可以将深度特征映射到 $\pmb { R } ^ { c }$ 空间中， $\mathbf { \Psi } _ { c }$

为哈希码长度。

表1AlexNet 神经网络结构  
Tab.1The network structure of alexnet   

<html><body><table><tr><td>Type</td><td>Filter size/stride</td><td>Output size</td></tr><tr><td>Conv1</td><td>11 × 11/4</td><td>55×55×96</td></tr><tr><td>Conv2</td><td>5×5/1</td><td>27× 27×256</td></tr><tr><td>Conv3</td><td>3×3/1</td><td>13×13×384</td></tr><tr><td>Conv4</td><td>3×3/1</td><td>13×13×384</td></tr><tr><td>Conv5</td><td>3×3/1</td><td>13 ×13×256</td></tr><tr><td>FC1</td><td>4096</td><td>4096</td></tr><tr><td>FC2</td><td>4096</td><td>4096</td></tr><tr><td>FC3</td><td>1000</td><td>1000</td></tr></table></body></html>

骨干网的输入为图像 $x _ { i } \in X$ ， $X = \{ x _ { i } \} _ { i = 1 } ^ { m }$ 表示查询图像集合，

该数据集中共包含 $m$ 个样本。图像经过骨干网提取得到哈希特征 $\pmb { h } _ { i }$ ：

$$
\pmb { h } _ { i } = f ( x _ { i } , \theta )
$$

其中 $f$ 表示骨干网函数， $\theta$ 表示骨干网的参数。

# 2 损失函数

如图1中损失函数阶段所示，为学习得到更优的哈希码，设计了一个损失函数，可表示为： $\begin{array} { r } { L = L _ { 1 } + \lambda L _ { 2 } } \end{array}$ ，其中 $L _ { 1 }$ 为贪心损失， $L _ { 2 }$ 为非对称成对损失， $\lambda$ 为超参数。贪心损失 $L _ { 1 }$ 能够解决优化过程中梯度消失问题[30]；非对称成对损失能够充分利用数据集合标签信息，并高效训练网络[21]。

# 2.1贪心损失

为了得到图像的哈希编码，通常会在哈希编码层后面使用sign函数将深度特征映射为二值化哈希码。但由于sign函数不可导，会使优化过程变为NP难问题。传统方法使用tanh或sigmoid 函数进行松弛[29]，这样虽然能够训练网络，但会产生次优解。为更好解决这个问题，本文提出利用贪心算法，在正向传播中严格使用sign函数保持对网络输出的离散约束；而在反向传播中，哈希层梯度被完整地传送到前层，避免了梯度消失，有效地解决了离散优化问题。

贪心损失的核心问题是如何利用贪心算法来解决离散优化问题。因此，该损失关注离散优化问题 $\operatorname* { m i n } L _ { 1 } ( \pmb { b } _ { i } )$ ，其中$\pmb { b } _ { i } = s i g n ( \pmb { h } _ { i } ) \in \{ - 1 , 1 \} ^ { 1 \times c }$ 表示 $x _ { i }$ 的哈希码。具体地，本文的贪心损失采用交叉熵损失形式。

在离散优化过程中，如果完全忽略离散约束 ${ \pmb b } _ { i } \in \{ - 1 , 1 \} ^ { 1 \times c }$ ，利用梯度下降算法可以得到第 $\left( t { + } 1 \right)$ 次迭代的 $b _ { i }$ ，即

$$
{ \pmb b } _ { i } ^ { t + 1 } = { \pmb b } _ { i } ^ { t } - l _ { r } ^ { \ast } \frac { \hat { \sigma } L _ { 1 } } { \hat { \sigma } { \pmb b } _ { i } ^ { t } }
$$

其中 $l _ { r }$ 代表学习率。然而，使用式(2)得到的解不满足${ \pmb b } _ { i } ^ { t + 1 } \in \{ - 1 , 1 \} ^ { 1 \times c }$ 。若不考虑离散约束，则由式(2)所得到的解为连续最优解。贪心原理认为离连续最优解最近的离散点如式(3)，就是所希望得到的离散最优解。

$$
{ \pmb b } _ { i } ^ { t + 1 } = s i g n ( { \pmb b } _ { i } ^ { t } - l _ { r } * \frac { \partial L _ { 1 } } { \partial { \pmb b } _ { i } ^ { t } } )
$$

式(3)可拆分为前向传播和反向传播两步来实现。前向传播过程如式(4)所示，它通过新的哈希层在正向传播中使用sign函数实现：

$$
{ \pmb { b } } _ { i } ^ { t + 1 } = s i g n ( { \pmb { h } } _ { i } ^ { t + 1 } )
$$

反向传播过程中，本文在贪心损失中添加一个惩罚项$\| h _ { i } - s i g n ( h _ { i } ) \| _ { \mathrm { p } } ^ { \mathrm { p } }$ ，并且使得该惩罚项尽可能地接近零。再由${ \pmb b } _ { i } ^ { t } = s i g n ( { \pmb h } _ { i } ^ { t } )$ 可以得到：

$$
{ \pmb h } _ { i } ^ { t + 1 } = { \pmb h } _ { i } ^ { t } - l _ { r } * \frac { \hat { \partial } L _ { 1 } } { \hat { \partial } { \pmb h } _ { i } ^ { t } } = ( { \pmb h } _ { i } ^ { t } - { \pmb b } _ { i } ^ { t } ) + { \pmb b } _ { i } ^ { t } - l _ { r } * \frac { \hat { \partial } L _ { 1 } } { \hat { \partial } { \pmb h } _ { i } ^ { t } } =
$$

$$
( { \pmb h } _ { i } ^ { \prime } - s i g n ( { \pmb h } _ { i } ^ { \prime } ) ) + { \pmb b } _ { i } ^ { \prime } - l _ { r } * \frac { \hat { \partial } L _ { 1 } } { \hat { \partial } { \pmb h } _ { i } ^ { \prime } } \approx { \pmb b } _ { i } ^ { \prime } - l _ { r } * \frac { \hat { \partial } L _ { 1 } } { \hat { \partial } { \pmb h } _ { i } ^ { \prime } }
$$

今

$$
\frac { \partial L _ { 1 } } { \partial \pmb { h } _ { i } ^ { \prime } } = \frac { \partial L _ { 1 } } { \partial \pmb { b } _ { i } ^ { \prime } }
$$

即可得到：

$$
\pmb { h } _ { i } ^ { t + 1 } = \pmb { b } _ { i } ^ { t } - l _ { r } ^ { \ast } \frac { \hat { \sigma } L _ { 1 } } { \hat { \sigma } \pmb { b } _ { i } ^ { t } }
$$

式(6)表示，在反向传播过程中，贪心原理能够将哈希层梯度完全传送到网络输出层。通过分别实现正向传播和反向传播过程，本文的贪心损失有效地解决了离散优化问题，且获得精确的哈希码。

# 2.2 非对称成对损失

非对称成对损失 $L _ { 2 }$ 的作用是：在训练过程中，采用非对称策略训练网络。这样不仅能够充分利用数据集合的监督信息，而且也可以高效训练网络。所谓非对称策略是指，采用不同的方式来处理查询图像和数据集合图像。对于查询图像，通过骨干网进行深度特征提取，再使用深度哈希函数生成查询图像的哈希码；而对于数据集合图像，它的哈希码则是直接学习得到。

为得到能够保留查询图像与数据集合图像之间相似性的哈希码，一种常见的方法[29]是最小化训练图像与数据集合图像的监督信息相似性和哈希码内积之间的相似性：

$$
\operatorname* { m i n } _ { { \pmb { B } } , { \pmb V } } L _ { 2 } ( { \pmb B } , { \pmb V } ) = \sum _ { i = I } ^ { m } \sum _ { j = 1 } ^ { n } [ { \pmb b } _ { i } ^ { T } { \pmb \nu } _ { j } - c { \pmb S } _ { i j } ] ^ { 2 }
$$

其中 $\pmb { { \cal B } } = \{ \pmb { b } _ { i } \} _ { i = 1 } ^ { m } \in \{ - 1 , 1 \} ^ { m \times c }$ ，表示训练图像集合通过哈希函数所学习到的哈希码集合。 $V = \{ \pmb { \nu } _ { j } \} _ { j = 1 } ^ { n } \in \{ - 1 , 1 \} ^ { n \times c }$ 表示直接学习得到的数据集合图像对应的哈希码集合，该集合中包含 $n$ 个样本点。$S _ { i j }$ 表示相似矩阵，如果两张图像相似， ${ \boldsymbol { S } } _ { i j } = 1$ ，否则 $S _ { i j } = - 1$ 。

由 $\pmb { h } _ { i } = f ( x _ { i } , \theta )$ 和 $\pmb { b } _ { i } = s i g n ( \pmb { h } _ { i } )$ ，式(8)可变换为

$$
\operatorname* { m i n } _ { \theta , V } L _ { 2 } ( \theta , V ) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } [ s i g n ( f ( x _ { i } , \theta ) ) ^ { T } \nu _ { j } - c S _ { i j } ] ^ { 2 }
$$

但由于式(9)中存在sign函数(sign 函数不可导)，因此参数 $\theta$ 的梯度不能直接进行反向传播。本文使用tanh函数替代sign函数进行松弛，式(9)表示如下：

$$
\operatorname* { m i n } _ { \theta , V } L _ { 2 } ( \theta , V ) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } [ t a n h ( f ( x _ { i } , \theta ) ) ^ { T } \nu _ { j } - c S _ { i j } ] ^ { 2 }
$$

在实际应用中，如果只给定一个数据集合 $z$ 而没有指明查询集 $X$ ，那么可以从 $z$ 中随机采样 $m$ 个数据作为查询集。即 $X = Z ^ { a }$ ，其中 ${ \pmb Z } ^ { a } = \{ z _ { 1 } , z _ { 2 } , \cdots , z _ { m } \}$ 表示从数据集合中随机采样的数据集合， $\pmb { \varOmega } = \{ i _ { 1 } , i _ { 2 } , \cdots , i _ { m } \}$ 表示采样得到数据的索引集。本文令 $\boldsymbol { { \cal T } }$ 表示数据集合的所有索引值，则 $\pmb { \mathcal {  }$ 。同样可以得到采样数据集对应的相似矩阵 $S ^ { a }$ ，令 $S = S ^ { a }$ 。则式(10)可重写为

$$
\operatorname* { m i n } _ { \theta , V } L _ { 2 } ( \theta , V ) = \sum _ { i \in \Omega } \sum _ { j \in I } [ t a n h (  { f } ( z _ { i } , \theta ) ) ^ { T } \nu _ { j } - c S _ { i j } ] ^ { 2 }
$$

为保持 $\pmb { \nu } _ { i }$ 和 $t a n h ( f ( z _ { i } , \theta ) )$ 尽可能接近，在式(11)中添加一个额外约束是合理的。由于 $t a n h ( f ( z _ { i } , \theta ) )$ 是 $z _ { i }$ 的哈希码的近似值，因此式(11)可重写为

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } _ { \theta , V } L _ { 2 } ( \theta , V ) = \sum _ { i \in \pmb { \Omega } } \sum _ { j \in T } [ t a n h ( \ b { f } ( \triangledown _ { i } , \theta ) ) ^ { T } \pmb { \nu } _ { j } - c \pmb { S } _ { i j } ] ^ { 2 } + } \\ { \displaystyle \gamma \sum _ { i \in \pmb { \Omega } } [ \pmb { \nu } _ { i } - t a n h ( \pmb { f } ( \triangledown _ { i } , \theta ) ) ] ^ { 2 } } \end{array}
$$

其中为超参数。

本文采用交替优化策略来学习式(12)中的参数 $\theta$ 和 $\boldsymbol { V }$ ，该方法也可适用于式(10)。具体地，在每次迭代中只学习一个参数而其他参数固定，这个过程重复多次迭代。交替优化策略更新参数的具体过程可参考 $\mathrm { \ A D S H ^ { [ 2 1 ] } }$ 方法中学习算法部分。

# 3 实验

为验证所提出方法的有效性，本文在两个常用公开数据集上进行了测试，并同17种方法进行了比较。

# 3.1 数据集

a)CIFAR-10 数据集。CIFAR-10 数据集[32]共包含10 个类，每类包含6000个样本，总共有60000张彩色图像，图像大小为 $3 2 \times 3 2$ 。对于CIFAR-10数据集，如果两幅图像标签相同，那么将两张图像视为相似对。

b)NUS-WIDE 数据集。NUS-WIDE 数据集[33]由 269648张带标签的网络图像组成。它是一个多标签数据集，其中每个图像都包含多张标签。本文只选择了10个最常见的类的图像。对于NUS-WIDE 数据集，如果两张图像至少共享一个公共标签，它们将被定义为相似对。

# 3.2实验设置

本实验的模型是在PyTorch框架下实现的。min-batch的大小设置为128，并使用Adam[34]作为优化器，权重衰减设置为0.0005，最大迭代次数设置为50。在数据划分上，对于CIFAR-10数据集，随机从每类中抽取200张，总共抽取2000张图像作为训练集；从数据集合中每类抽取100张，总共1000张图像作为查询集。除去1000 张查询集之外的59000张图像作为数据集合。

对于NUS-WIDE数据集，每次从数据集合中随机抽取2000张作为训练集，随机抽取1000张作为查询集，除去查询集之外的所有图像作为数据集合。在评价指标中，本文选取图像检索中最常用的评价指标：mAP(meanAveragePrecision)和 PR(Precision-Recall)。

在深度哈希方法中，由于不同深度神经网络具有不同的特征提取能力，在选取不同深度神经网络作为骨干网时检索性能会有较大变化。为便于比较，本实验采用在ImageNet数据集[35]上预训练的AlexNet模型作为骨干网。

# 3.3实验结果与分析

# 3.3.1检索结果对比

本实验在图像数据集CIFAR-10和NUS-WIDE上进行，为评估本文贪心非对称深度有监督哈希的性能，本文选取17种方法进行比较，其中包括7种传统哈希学习方法和10 种深度哈希学习方法。传统哈希学习方法中包括无监督哈希学习方法： $\mathrm { I T Q } ^ { [ 2 ] }$ ，有监督哈希学习方法：Lin:Lin[35]、LFH[37]、FastH[38]、SDH[39]、COSDISH[40]、KADGH[41]。深度哈希学习方法包括： $\mathrm { \Delta D S H ^ { [ 1 ] } }$ 、DSDH[15]、DHN[19]、DPSH[18]、DTSH[20]、Greedy Hash[31]、ADSH[21]、SDNMSH[42]、ASDDH[27]和TransHash[43]。

在CIFAR-10和NUS-WIDE上的图像检索mAP精度如表2所示，加粗字体表示最优值，下划线表示次优值，\*表示本文复现结果。从表2中可以看出，在大多数情况下，有监督哈希学习方法性能都要优于无监督哈希学习方法，而深度哈希学习方法优于传统哈希学习方法。同时，本文方法在所有长度哈希码上的检索性能均显著优于其他方法。这是因为所提出的贪心非对称损失能够更好地保留图像特征信息，从而提高哈希检索性能。在CIFAR-10数据集上，本文方法在48比特条件下的性能比ADSH方法提高了 $3 . 0 \%$ ，与TransHash方法相比提高了 $1 . 4 \%$ 。在NUS-WIDE 数据集上，所提方法在不同比特下检索性能平均提高了 $2 . 3 \%$ 。从实验结果可以看出，本文方法在这两个常用数据集上的性能均较好，尤其是在单标签数据集CIFAR-10上检索性能提升更加明显。

表2CIFAR-10 和NUS-WIDE上图像检索mAP精度对比

Tab.2Comparison of map accuracy on CIFAR-10 and NUS-WIDE   

<html><body><table><tr><td rowspan="2">方法</td><td colspan="4">CIFAR-10</td><td colspan="4">NUS-WIDE</td></tr><tr><td>12位</td><td>24位</td><td>32位</td><td>48位</td><td>12位</td><td>24位</td><td>32位</td><td>48位</td></tr><tr><td>ITQ[2]</td><td>0.2619</td><td>0.2754</td><td>0.2861</td><td>0.2941</td><td>0.7143</td><td>0.7361</td><td>0.7457</td><td>0.7553</td></tr><tr><td>Lin: Lin[36]</td><td>0.6099</td><td>0.6312</td><td>0.6079</td><td>0.6013</td><td>0.5556</td><td>0.5704</td><td>0.5627</td><td>0.5555</td></tr><tr><td>LFH[37]</td><td>0.4178</td><td>0.5738</td><td>0.6414</td><td>0.6927</td><td>0.7116</td><td>0.7681</td><td>0.7949</td><td>0.8135</td></tr><tr><td>FastH[38]</td><td>0.5971</td><td>0.6632</td><td>0.6847</td><td>0.7020</td><td>0.7267</td><td>0.7692</td><td>0.7817</td><td>0.8037</td></tr><tr><td>SDH[39]</td><td>0.4539</td><td>0.6334</td><td>0.6514</td><td>0.6603</td><td>0.7646</td><td>0.7998</td><td>0.8017</td><td>0.8124</td></tr><tr><td>COSDISH[40]</td><td>0.5831</td><td>0.6614</td><td>0.6802</td><td>0.7016</td><td>0.6425</td><td>0.7406</td><td>0.7843</td><td>0.7964</td></tr><tr><td>KADGH[41]</td><td>0.6134</td><td>0.6607</td><td>0.6701</td><td>0.6829</td><td></td><td></td><td></td><td></td></tr><tr><td>Greedy Hash[31]</td><td>0.7740</td><td>0.7950</td><td>0.8100</td><td>0.8200</td><td></td><td></td><td></td><td></td></tr><tr><td>SDNMSH[42]</td><td></td><td>0.8068</td><td>0.8106</td><td>0.8135</td><td></td><td>0.6169</td><td>0.6234</td><td>0.6289</td></tr><tr><td>DSDH[15]</td><td>0.7400</td><td>0.7860</td><td>0.8010</td><td>0.8200</td><td>0.5930</td><td>0.5930</td><td>0.6200</td><td>0.6350</td></tr><tr><td>DPSH[18]</td><td>0.6818</td><td>0.7204</td><td>0.7341</td><td>0.7464</td><td>0.7941</td><td>0.8249</td><td>0.8351</td><td>0.8442</td></tr><tr><td>DTSH[20]</td><td>0.7100</td><td>0.7500</td><td>0.7650</td><td>0.7740</td><td>0.7730</td><td>0.8080</td><td>0.8120</td><td>0.8240</td></tr><tr><td>DSH[1]</td><td>0.6441</td><td>0.7421</td><td>0.7703</td><td>0.7992</td><td>0.7125</td><td>0.7313</td><td>0.7401</td><td>0.7485</td></tr><tr><td>DHN[19]</td><td>0.6805</td><td>0.7213</td><td>0.7233</td><td>0.7332</td><td>0.7719</td><td>0.8013</td><td>0.8051</td><td>0.8146</td></tr><tr><td>ASDDH[27]</td><td>0.7360</td><td>0.7710</td><td>0.7810</td><td>0.7850</td><td>0.8340</td><td>0.8510</td><td>0.8680</td><td>0.8740</td></tr><tr><td>TransHash[43]</td><td>-</td><td>-</td><td>0.9108</td><td>0.9141</td><td>-</td><td>-</td><td>0.7393</td><td>0.7532</td></tr><tr><td>ADSH*[21]</td><td>0.8950</td><td>0.9010</td><td>0.9030</td><td>0.8970</td><td>0.8690</td><td>0.8990</td><td>0.9050</td><td>0.9110</td></tr><tr><td>本文方法</td><td>0.9130</td><td>0.9150</td><td>0.9160</td><td>0.9270</td><td>0.8940</td><td>0.9180</td><td>0.9350</td><td>0.9300</td></tr></table></body></html>

为了进一步说明所提方法的优越性，本文在CIFAR-10和NUS-WIDE数据集上12比特条件下分别绘制了PR曲线，如图2、3所示。PR曲线与横坐标轴所围面积越大，则表示该方法性能越好。从图2、3各方法的PR曲线与横坐标轴所围面积可以看出，贪心非对称深度有监督哈希图像检索方法的性能明显优于其他所有方法。

# 3.3.2超参数分析

贪心非对称损失为 $\begin{array} { r } { L = L _ { 1 } + \lambda L _ { 2 } } \end{array}$ ，其中 $L _ { 1 }$ 为贪心损失， $L _ { 2 }$ 为非对称成对损失， $\lambda$ 为超参数。为分析 $\lambda$ 对于检索性能的影响，本实验在CIFAR-10和NUS-WIDE 数据集上进行参数分析。图4、5显示了本实验分别在12比特和48比特下λ取不同值(0.1、1、10、100、1000)时的检索精度。从图4、5中可以看出，超参数 $\lambda$ 的取值对两个数据集的检索结果影响并不明显。图4显示：当 $0 . 1 < \lambda < 1$ 时，CIFAR-10 数据集能够达到较好的检索性能。 $\lambda = 1$ 时，CIFAR-10在不同比特下的检索结果均能达到最好；图5显示：当 $0 . 1 < \lambda < 1 0$ 时，NUS-

WIDE数据集能达到较好的检索性能。 $\lambda = 1$ 时，NUS-WIDE在不同比特下的检索结果均能最好。综上所述，本文超参数λ取值为1。

![](images/59475b41c42e264208cd4aa5256d7e2ec9006da9cbc97782d43245ae199ea5d4.jpg)  
图2 CIFAR-10 PR 曲线Fig.2PR curve of CIFAR-10

![](images/1ebed7d5f9d3575a27491a966f5560e7c1b46a07fc4a8b94bd0a35b1c2910ebd.jpg)  
图3 NUS-WIDE PR 曲线 Fig.3PR curve of NUS-WIDE

![](images/e8204d9c9a9dcb0aab79886daf2165705622feae20be68a777ceff8c086e504a.jpg)

![](images/3dcfc4579ed776b578d306d40e52bbaf6326cd53c7aff7782741a0a5c0c8c097.jpg)  
图4λ对CIFAR-10 检索精度的影响 Fig.4The retrieval accuracy with differentλon CIFAR-10   
图5λ对NUS-WIDE 检索精度的影响  
Fig.5The retrieval accuracy with different $\lambda$ on NUS-WIDE

# 3.3.3检索结果可视化

为了进一步说明本文方法的检索效果，图6中给出了对CIFAR-10数据集每类图像查询结果(TOP10检索结果)的可视化。从图6可以看出，CIFAR-10数据集的TOP10平均检索精度可以达到 $9 8 \%$ 。进一步验证了本文方法在单标签数据集上优异的检索性能。

![](images/f7304a7ee4c03a865153390c0220673606eeb32cb8a06b1fee20dfc1256e65de.jpg)  
图6CIFAR-10的 TOP10 检索结果Fig.6Top 10 retrieval results on CIFAR-10

# 4 结束语

针对哈希函数学习过程中的离散优化问题和监督信息利用不充分问题，提出了贪心非对称深度有监督哈希图像检索方法。该方法将贪心算法和非对称策略同时应用到哈希学习过程中，这样不仅能够将哈希层梯度完全传送到网络输出层来解决离散优化问题，而且能够充分利用监督信息高效地训练网络。所提方法与17种方法在两个公开数据集上进行对比实验，验证了该方法的有效性。虽然贪心非对称深度有监督哈希图像检索方法的检索性能已经取得显著进步，但在多标签检索任务上仍有一定的提升空间。因此在下一步工作中，本文将考虑进一步提高本文方法对多标签数据的适应能力。

# 参考文献：

[1]Liu HM,Wang RP,Shan SG,et al.Deep supervised hashing for fast image retrieval [C]//Proc of the 2016 IEEE Conference on Computer Visi-on and Pattern Recognition. Washington: IEEE Computer Society, 2016:2064-2072.   
[2]Gong Y Cand Lazebnik S.Iterative quantization: a procrustean approach to learning binary codes [C]// Proc of the 2011 IEEE Conference on Computer Vision and Pattern Recognition. Washington: IEEE Computer Society,2011: 817-824.   
[3]Andoni A and Razenshteyn I.Optimal data dependent hashing for approximate near neighbors [C]// Proc of the 47th Annual ACM Symposium on the Theory of Computing. New York: ACM Press, 2015: 793-801.   
[4]Andoni Aand Indyk P.Near-optimal hashing algorithms for approximate nearest neighbor in high dimensions [C]//Proc of the 2Oo6 Annual IEEE Symposium on Foundations of Computer Science.Piscataway,NJ: IEEE Press, 2006: 459-468.   
[5]Kong W Hand LiWJ. Isotropic hashing[C]/ Proc of the 2012 Neural Information Processing Systems. Cambridge,MA:MIT Press,2012: 1655-1663.   
[6]Atkinson MP,Orlowska ME, Valduriez P,et al. Similarity search in high dimensions via hashing [Cl// Proc of 25th International Conference on Very Large Data Bases. San Francisco: Morgan Kaufmann,1999: 518- 529.   
[7]Liu W,Wang J,JiRR,et al. Supervised hashing with kernels [C]//Proc of the 2O12 IEEE Conference on Computer Vision and Pattern Recognition. Washington: IEEE Computer Society,2012: 2074-2081.   
[8]Krizhevsky A, Sutskever I and Hinton G. ImageNet classification with deep convolutional neural networks [C]// Proc of the 2O12 Neural Information Processing Systems.Cambridge,MA:MIT Press,2012: 1106-1114.   
[9]Szegedy C,Liu W,Jia YQ,et al. Going deeper with convolutions [C]// Proc of the 2O15 IEEE Conference on Computer Vision and Pattern Recognition. Washington: IEEE Computer Society,2015:7-12.   
[10] Sun Y,Chen YH,Wang XG,et al.Deep learning face representation by joint identification-verification [C]// Proc of the 2014 Neural Information Processing Systems. Cambridge,MA:MIT Press,2014: 1988-1996.   
[11] Taigman Y, Yang M, Ranzato M, et al. DeepFace: closing the gap to human-level performance in face verification [C]//Proc of the 2014 IEEE Conference on Computer Vision and Pattern Recognition. Washington: IEEE Computer Society,2014: 1701-1708.   
[12] Zhao F, Huang Y Z, Wang L,et al. Deep semantic ranking based hashing for multi-label image retrieval [C]// Proc of the 2015 IEEE Conference on Computer Vision and Pattern Recognition．Washington: IEEE Computer Society,2015:1556-1664.   
[13] Zhang R M,Lin L,Zhang R,et al.Bit-Scalable deep hashing with regularized similarity learning for image retrieval and person reidentification [J].IEEE Trans on Image Processing,2015,24 (12): 4766- 4779.   
[14] Lai H J,Pan Y, Liu Y,et al. Simultaneous feature learning and hash coding with deep neural networks [C]// Proc of the 2015 IEEE Conference on Computer Vision and Pattern Recognition.Washington: IEEE Computer Society,2015: 3270-3278.   
[15] Li Q, Sun Z N, He R,et al. Deep supervised discrete hashing[J]. IEEE Trans on Image Processing,2018: 27 (12): 5996-6009.   
[16] Luo X, Chen C, Zhang H S,et al. A Survey on Deep Hashing Methods [J].Arxiv,2020,abs/2003.03369.   
[17] XiaHK,Pan Y,Lai HJ,et al. Supervised hashing for image retrieval via image representation learning [Cl//Proc of the 28th AAAI Conference on Artificial Intelligence. New York: AAAI Press,2014: 2156-2162.   
[18] Li W J, Wang S and Kang W C. Feature learning based deep supervised hashing with pairwise Labels [C]//Proc of the 25th International Joint Conference on Artificial Intelligence.New York:AAAI Press,2016: 1711-1717.   
[19] Zhu H,Long MS,Wang JM,et al.Deep hashing network for efficient similarity retrieval [C]//Proc of the 3Oth AAAI Conference on Artificial Intelligence.New York: AAAI Press,2016:2415-421.   
[20] Wang XF, Shi Yand Kitani K M. Deep supervised hashing with triplet labels [C]// Proceedings of the 13th Asian Conference on Computer Vision. Taipei,Taiwan: Springer,2016: 70-84.   
[21] Jiang QY and Li W J.Asymmetric deep supervised hashing [C]// Proc of the 32th AAAI Conference on Artificial Intelligence.New York: AAAI Press,2018:3342-3349.   
[22] Dong W,Charikar M,Li K,Asymmetric distance estimation with sketches for similarity search in high-dimensional spaces [C].Proc of the Annual International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACM Press, 2008: 123-130.   
[23] Gordo A,Perronnin F, Gong YC,et al. Asymmetric distances for binary embeddings [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2014,36 (1): 33-47.   
[24] Shen F M, Gao X,Liu L,et al. Deep asymmetric pairwise hashing [C]. /Proc of the 2017 ACM on Multimedia Conference.New York: ACM Press,2017:1522-1530.   
[25] Da C,Meng G F, Xiang S M,et al. Nonlinear asymmetric multi-valued hashing [J].IEEE Trans on Pattern Analysis and Machine Intellgence, 2019,44 (11): 2660-2676.   
[26] Luo YD,Huang Z,Li Y, et al. Collaborative learning for extremely low bit asymmetric hashing [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2021,33 (12): 3675-3685.   
[27] Lu JL,Wang HL, Zhou J,et al. Deep Asymmetric Hashing with Dual Semantic Regression and Class Structure Quantization [J]. Information Sciences,2022,589: 235-249.   
[28]顾广华，霍文华，苏明月，等．基于非对称监督深度离散哈希的图像 检索[J].电子与信息学报,2021,43(12):3530-3537.(Gu Guanghua, Huo Wenhua, Su Mingyue,et al. Asymmetric Supervised Deep Discrete Innh Technology,2021,43 (12):3530-3537.)   
[29] Zhu H and Gao S H.Locality constrained deep supervised hashing for image retrieval [C]// Proc of the 26th International Joint Conference on Artificial Intelligence. San Francisco: Morgan Kaufmann,2017: 3567- 3573.   
[30] Yang H F, Lin K and Chen C S. Supervised learning of semanticspreserving hashing via deep convolutional neural networks for largescale image search [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2017,40 (2): 437-451.   
[31] Su SP, Zhang C,Han K,et al.Greedy Hash: towards fast optimization for accurate hash coding in CNN [C]// Proc of the 2018 Neural Information Processing Systems. Cambridge,MA:MIT Press,2018: 806-815.   
[32] Krizhevsky A and Hinton G.Learning multiple layers of features from tiny images [D].Technical Report TR-20o9.University ofToronto,2009.   
[33] Chua T S,Tang JH,HongRC,et al.NUS-WIDE:a real-world web image database from national university of singapore [C]// Proc of the 8th ACM International Conference on Image and Video Retrieval. New York: ACM Press, 2009: 1-9.   
[34] Kingma D Pand Ba J.2014.Adam: a method for stochastic optimization. [EB/OL]. (2020-02-25). htps://arxiv.org/pdf/1412. 6980.pdf.   
[35] Russakovsky O,Deng J,Su H,et al.ImageNet large scale visual recognition challenge [J]. International Journal of Computer Vision, 2015,115 (3): 211-252.   
[36] Neyshabur B,Srebro N,Salakhutdinov R,et al.The power of asymmetry in binary hashing [C]//Proc of the 2013 Neural Information Processing Systems. Cambridge,MA: MIT Press,2013: 2823-2831.   
[37] Zhang PC,Zhang W,Li WJ,et al. Supervised hashing with latent factor models [C]// Proc of the 37th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACM Press,2014:173-182.   
[38] Lin G S,Shen CH, Shi QF,et al. Fast supervised hashing with decision trees for high-dimensional data[C]// Proc of the 2014 IEEE Conference on Computer Vision and Pattern Recognition．Washington: IEEE Computer Society,2014: 1971-1978.   
[39] Shen FM,Shen CH,Liu W,et al. Supervised discrete hashing [C]// Proc of the 2015 IEEE Conference on Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE,2015: 37-45.   
[40] Kang W C, Li W Jand Zhou Z H. Column sampling based discrete supervised hashing [C]//Proc of the 30th AAAI Conference on Artificial Intelligence.New York: AAAI Press,2016: 1230-1236.   
[41] Shi X S, Xing FY, Xu K D,et al. Asymmetric discrete graph hashing [C]/ Proceedings of the 31th AAAI Conference on Artificial Intelligence. New York: AAAI Press,2017: 2541-2547.   
[42]张志升，曲怀敬，徐佳，等．稀疏差分网络和多监督哈希用于高效图 像检索[J].计算机应用研究,2021,39(6):1-8.(Zhang Zhisheng,Qu Huaijing,Xu Jia,et al. Sparse differential network and multi-supervised hashing for eficient image retrieval [J].Application Research of Computers,2021,39 (6): 1-8.)   
[43] Chen Y B,Zhang S,Liu F X,et al. TransHash: Transformer-based Hamming Hashing for Efficient Image Retrieval [J].Arxiv,2021, abs/2105.01823.