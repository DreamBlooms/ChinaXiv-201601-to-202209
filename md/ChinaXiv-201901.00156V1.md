# 基于 $L _ { 2 } .$ -范数重构样本约束的稀疏表示人脸识别方法

米建勋a,b，林志凯a,b

(重庆邮电大学a.计算机科学与技术学院;b.计算智能重庆市重点实验室，重庆 400065)

摘要：稀疏表示分类方法在训练样本空间较大的情况下具有良好的分类效果，但是计算的时间成本较高。针对稀疏表示方法的此问题，考虑构造对重构样本的 $L _ { 2 }$ -范数约束，使得重构样本中各类别分量之间的竞争加强，以起到组稀疏的效果，最后提高分类正确率。由于该方法可以直接得到闭式解，使得求解的计算成本大大的减小，并且得到的系数稀疏程度与传统方法类似。在公开的人脸和物体图像数据集上和同类型方法的对比实验结果表明该方法在复杂的条件下具有优秀的图像识别效果。

关键词：稀疏表示；人脸识别；联合表示；重构样本中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.10.0771

# Sparse representation classification via $L _ { 2 }$ -norm based reconstruction sample constraint for face recognition

Mi Jianxuna,bt,Lin Zhikaia, b (a.Schoolof Computer Science & Technology,b.Chongqing Key Laboratoryof Computational Intelligence,Chongqing University of Posts & Telecommunications,Chongqing 40o065,China)

Abstract: Sparse representation classification (SRC) has a good performance of clasification when the feature space spanned by training samples is sufcient,butthecomputationalcost is expensive.To solvethis problemofSRC,this work considered the constraint of reconstruction samples.It introduced a group sparsity efect to enhance the competitions between different subjects in reconstruction procedure，and improves the accuracy of classfication finall.Since the proposed method hasa closed solution,thecomputational costisvery low.Moreover,the sparsityof thecoefficient producedbythe new approach is the same as thatobtained by SRC.The experiment results on public face and object image datasets demonstrate that the proposed method has a good performance comparing with other same kind approaches.

Key words: sparse representation; face recognition; collaborative representation; reconstruction sample

# 0 引言

人脸识别是计算机视觉和模式识别等领域的热门研究方向。作为生物特征识别的重要方法，人脸识别在现在生活中的很多场景都起到了至关重要的作用，比如机场安检系统、手机刷脸解锁和刷脸支付等场景。人脸识别技术主要有以下三类：基于几何特征的方法；基于模板的方法；基于数学统计模型的方法[1]。随着人脸识别技术在日常生活中应用的深入，识别算法需要处理的场景变得更加复杂，光照、表情、姿态和伪装对人脸识别的效果有很大影响，提升算法的鲁棒性和速度成了亟待解决的问题。

自从2009年Wright等人[2]提出基于稀疏表示 SRC(sparserepresentationbasedclassification）的人脸识别方法以来，其受到了领域内研究者广泛的关注。稀疏表示方法通过在训练样本组成的字典上对测试人脸进行稀疏的线性回归拟合得到重构人脸，然后比较重构人脸在不同类别上的分量与测试样本相似程度，选择最相似的分量作为测试样本所属类别。SRC对表示系数施加 $L _ { 1 }$ -范数正则，以期望得到稀疏的系数。Wright认为只要测试样本数量足够多同时系数足够稀疏，SRC就可以完全拟合测试样本。SRC通过迭代优化的方法求解基于 $L _ { 1 }$ -范数正则的最小化问题，在文献[3]中综述相关求解算法。实验证明，当测试样本较多时，SRC方法在人脸识别场景中可以有很好的分类结果。此后，许多学者在稀疏表示方向的应用和研究[4\~9证明了其在图像处理和人脸识别方面的良好表现。然而，Zhang等人认为SRC之所以能够取得好的实验效果，其本质原因是联合表示的机制起主要作用，并提出 CRC_RLS(collaboratively representation classificationwith regularized least square)[lo]。CRC_RLS 通过 $L _ { 2 }$ -范数正则替代 $\boldsymbol { L } _ { 1 }$ -范数正则，以起到相似的稀疏约束的效果。由于CRCRLS存在闭式的解，其求解速度相对SRC得到了很大的提升，但系数的稀疏程度并不是很高。为了达到相似的稀疏程度，同时提高方法的求解速度， $\mathrm { \Delta X u }$ 等人提出一系列的有监督的稀疏表示方法[1l\~15]。其中 TPTSR[11]（two-phase testsamplerepresentation）方法通过两个步骤对样本进行拟合，在首次表示之后剔除贡献较小的一些训练样本，然后用剩余的样本再对测试样本作一次拟合，最后得到的系数可以达到与SRC类似的稀疏程度。由于TPTSR在两次拟合中对系数施加 $L _ { 2 }$ -范数约束，因此求解的时间代价很小。CRCRLS和TPTSR都属于期望用较快的求解速度得到类似于SRC稀疏效果的模型，此外加权方法也属于该类模型的研究方向。AWCRC（adaptive and weighted collaborative representationclassification）[16]是其中的一个典型的加权联合表示的方法，根据测试样本和训练样本的距离对表示系数进行相应的加权约束，最后得到稀疏的系数。ProCRC[I7]通过对重构样本的 $l _ { 2 }$ -范数约束得到快速的稀疏系数，同样DSRC[18]也是在样本重构空间构造约束得到类似效果，它们的良好表现证明了对于重构样本进行合理的约束同样可以起到 $L _ { 1 }$ -范数系数正则效果。

为了能够得到更加快速且鲁棒的人脸识别算法，本文提出基于对重构样本的 $L _ { 2 }$ -范数约束的稀疏表示分类方法。通过约束重构样本中每两类分量的联合模长的方式，起到既能约束不同类别重构样本的模长又能约束它们之间的角度的效果，进而提高测试样本被单类样本表示的概率，最后提升整体的分类效果。通过在主流人脸及物体图像数据库中的实验比较，证明本文提出的方法在图像识别中具有良好的表现。

# 1 稀疏表示分类方法

稀疏表示的分类方法通过在测试样本组成的字典上对测试样本进行线性的回归拟合，然后根据不同类别分量得到的重构样本效果判别测试样本所属类别。假设 $\boldsymbol { \cal X }$ 表示测试样本组成的字典，其中 $\boldsymbol { X } = [ \boldsymbol { X } _ { 1 } \cdots \boldsymbol { X } _ { i } \cdots \boldsymbol { X } _ { c } ]$ 表示字典由‘个类别的样本组成， $X _ { i }$ 表示第 $i$ 类样本。 $\mathrm { \Delta y }$ 表示测试样本,通过线性拟合$\mathbf { y } = X a + \varepsilon$ 求得系数 $\hat { a }$ ，而用 $\hat { y } _ { i } = X _ { i } \hat { a } _ { i }$ 表示不同类别在重构样本所占表示分量，而 $\widehat { \mathbf { y } } = X \widehat { \boldsymbol { a } }$ 表示整体的重构样本，其中$\widehat { \boldsymbol { a } } = [ \widehat { \boldsymbol { a } } _ { 1 } , \cdots , \widehat { \boldsymbol { a } } _ { i } , \cdots , \widehat { \boldsymbol { a } } _ { c } ]$ 。有别于直接的线性回归即最小二乘法，SRC对系数施加一个 $L _ { 1 }$ -范数约束，具体的目标函数如下：

$$
\operatorname* { m i n } _ { a } \| y - X a \| _ { 2 } ^ { 2 } + \lambda \| a \| _ { 1 }
$$

其中：第一项称为保真项，第二项称为正则项。传统的最小二乘法只有保真项，而式(1)可以看做是回归问题中的Lasso[19]起到回归和变量选择两个作用。

虽然 $L _ { 1 } .$ -范数在回归中对训练样本有隐式选择的作用，但是迭代求解的计算成本很高。CRC_RLS则将正则项的范数替换为 $L _ { 2 }$ -范数，具体如下：

$$
\operatorname* { m i n } _ { a } \left\| y - X a \right\| _ { 2 } ^ { 2 } + \lambda \left\| a \right\| _ { 2 } ^ { 2 }
$$

CRCRLS可以看做是回归问题中的岭回归，引入松弛稀疏约束使得在字典元素不足时可以较大限度的回归拟合出测试样本。

然而当字典元素足够的时候， $L _ { 2 }$ -范数的约束会导致得到的系数稀疏程度较低，不利于后面的分类，针对此问题最近又有研究者提出通过对重构样本的约束以起到稀疏的效果[17,18,20,21]。其中 DSRC 在原有保真项的基础上增加了新的正则项约束重构样本的模长，具体如下：

$$
\operatorname* { m i n } _ { a } \| y - X a \| _ { 2 } ^ { 2 } + \lambda \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { c } \big \| X _ { i } a _ { i } + X _ { j } a _ { j } \big \| _ { 2 } ^ { 2 }
$$

此外，ProCRC在CRCRLS基础上添加对多个类别组成的重构样本模长的约束，具体如下：

$$
\operatorname* { m i n } _ { a } \| y - X a \| + \lambda \| a \| _ { 2 } ^ { 2 } + { \frac { \gamma } { c } } \sum _ { i = 1 } ^ { c } \| X a - X _ { i } a _ { i } \| _ { 2 } ^ { 2 }
$$

实验证明，对重构样本模长的约束可以有效的提升系数的稀疏程度，进而提高分类的正确率。

# 2 本文算法

本文研究的是在传统的稀疏表示方法的基础之上拓展得到计算速度较快且系数稀疏程度充分的方法。实验和理论证明[2]稀疏表示方法在人脸识别场景下具有优势，然而稀疏约束在字典元素数量足够多的时候才能起到良好的分类效果。

由于 $L _ { 1 }$ -范数约束特殊的性能，导致大部分与测试样本弱相关的训练样本失去表示的机会，当训练样本较少时，则测试样本因为失去正确类别弱相关训练样本的表示而被误分类至其他类别。然而 $L _ { 2 }$ -范数倾向于让更多训练样本去表示测试样本理想的状态重构的样本将处于训练样本的中心，也就是每个训练样本都有表示测试样本的机会。 $L _ { 1 }$ -范数和 $L _ { 2 }$ -范数存在一个共同的问题，分类效果特别依赖于训练样本的分布，当测试样本依据正则项最小化的原则在可行空间中寻找最优的表示时，由于训练样本没有携带标签信息，所以每个样本在相同的条件下都是等概率的被组合到一起。当类别之间的差异较小时，测试样本有很大可能性会被多个类别的样本表示，在进行分类判别时误分类的风险增大。因此让训练样本携带标签信息将有利于提高表示结果的一致性，提升分类效果。在回归问题中，GroupLasso[22]通过对系数给予不同的约束，即类内施加 $L _ { 2 }$ -范数约束，类间施加 $L _ { 1 }$ -范数约束，达到提高同类样本结合的可能性。

本文通过增强不同类别重构样本的竞争，以增大同类样本组合的几率，以达到GroupLasso 的稀疏效果。本方法在CRC_RLS的基础上添加新的正则项，通过对不同类别分量两两之间的模长之和进行约束使得表现能力较弱的类别整体的失去表现机会，同时增大表现能力较强的类别在整体重构样本中的占比，以提高算法的识别能力。

# 2.1算法描述

假设 $\boldsymbol { X } = [ \boldsymbol { X } _ { 1 } \cdots \boldsymbol { X } _ { i } \cdots \boldsymbol { X } _ { c } ]$ 表示包含c个类别训练样本的字典，y表示测试样本， $a = [ a _ { 1 } , \cdots , a _ { i } , \cdots , a _ { c } ]$ 表示由不同样本系数组成的整体表示系数。本文提出基于 $l _ { 2 }$ -范数的重构样本约束稀疏表示分类方法 RCSRC (Reconstruction constraint sparserepresentationclassification)，在CRC_RLS的基础之上添加关于重构样本中不同类别分量的约束项，具体的目标函数如下：

$$
\operatorname* { m i n } _ { a } \left\| y - \sum _ { i = 1 } ^ { c } y _ { i } \right\| _ { 2 } ^ { 2 } + \lambda \left\| a \right\| _ { 2 } ^ { 2 } + \frac { \gamma } { 2 } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 , j \neq i } ^ { c } \left\| y _ { i } + y _ { j } \right\| _ { 2 } ^ { 2 }
$$

其中： $y _ { i } = X _ { i } a _ { i }$ 表示不同类别组成的重构样本， $\lambda$ 和 $\gamma$ 是调节参数平衡保真项和正则项。直接对式（5）求导等于0可以得到闭式解如下：

$$
\hat { a } = [ ( 1 + \gamma ) X ^ { \mathrm { T } } X + \gamma ( c - 1 ) \Phi + \lambda I ] ^ { - 1 } X ^ { \mathrm { T } } y
$$

其中 $I$ 是单位矩阵， $\boldsymbol { \Phi } \mathbf { - } \left[ \begin{array} { c c c } { \boldsymbol { X } _ { 1 } ^ { \mathrm { ~ T ~ } } \boldsymbol { X } _ { 1 } } & { \cdots } & { \boldsymbol { 0 } } \\ { \vdots } & { \ddots } & { \vdots } \\ { \boldsymbol { 0 } } & { \cdots } & { \boldsymbol { X } _ { c } ^ { \mathrm { ~ T ~ } } \boldsymbol { X } _ { c } } \end{array} \right] \mathrm { ~ o ~ }$

通过计算不同类别分量所组成的重构样本与测试样本的距离作出类别的预测，具体如下：

$$
l a b e l ( \boldsymbol { y } ) = \arg \operatorname* { m i n } _ { i } \left\| \boldsymbol { y } - \boldsymbol { X } _ { i } \boldsymbol { \hat { a } _ { i } } \right\| _ { 2 } ^ { 2 }
$$

整体的算法流程如下：

算法1

输入：训练样本集 $X$ ，测试样本 $y$ ，参数 $\lambda$ ，参数 $\gamma$ ，训练样本集类别总数 $\mid c \mid$ 。

输出：label(y)测试样本类别标签

预处理：对训练集 $X$ 中的列向量进行归一化处理。

算法步骤：

1：根据式(6)计算得到 $\hat { a }$ 。  
2：根据式(7)计算得到测试样本标签 $l a b e l ( y )$ 。

# 2.2算法分析

RCSRC的目标函数式(5)由三个部分组成，分别是保真项、正则项和重构样本模长约束项。保真项保证了重构样本在测试样本合理的范围内变化，对系数的 $L _ { 2 }$ -范数正则项保证了系数在合理的范围内变化，第三项则保证了重构样本不同类别分量之间的合理竞争，起到了组合同类样本和抑制弱表达类别的作用。对第三项进行展开可以得到：

$$
\left\| y _ { i } \right\| _ { 2 } ^ { 2 } + 2 { y _ { i } } ^ { T } y _ { j } + \left\| y _ { j } \right\| _ { 2 } ^ { 2 }
$$

其中： $\begin{array} { r } { \left\| y _ { i } \right\| _ { 2 } ^ { 2 } } \end{array}$ 表示重构样本在类别i的分量的模长，而 ${ y _ { i } ^ { \textit { T } } } y _ { j }$ 表示第i类分量和第j类分量的相关性。由于对重构样本类别分量模长的约束，使得某些与测试样本相关性较弱的分量被压制到较小的值。而由于对不同分量之间的相关性有约束，使得不同类别之间的相关性尽量的减小，这有利于在训练样本类别较多的情况下，最后形成的重构样本仅有少数几个类别分量占优势，去除弱相关类别样本对于分类的影响。SRC和CRCRLS因为对训练样本标签是未知的，所以只能按照相关性盲目地选择样本，随着训练样本类别的增多，不同类别样本分布空间之间的重合程度会加剧，当测试样本所处的位置刚好处在多个类别分布空间重合区间之内，则被选择的测试样本必定是跨越多个空间的样本。然而，RCSRC由于对类别信息是已知的，整体的去除某些相关性较弱的类别样本，所以可以构造跨越少数空间的重构样本。

为了说明RCSRC计算得到系数稀疏程度，本文在ExtendYaleB[23]人脸数据库上进行实验，31个类别每类20张人脸，计算来自第1类的测试人脸图片得到的系数，如图1\~3所示分别是通过RCSRC，CRC_RLS和SRC三个算法计算得到的表示系数分布图。为了具体比较不同方法系数的稀疏程度，本文根据文献[2]中定义的 SCI (sparsity concentration index)计算不同系数的稀疏集中指标，SCI具体的定义如下：

$$
\operatorname { S C I } ( a ) { = } \frac { c ^ { \frac { \operatorname* { m a x } \lvert \delta _ { i } ( a ) \rvert _ { \lvert } } { \lvert \boldsymbol { a } \rvert \rvert _ { \lvert } } } - 1 } { c - 1 } \in [ 0 , 1 ]
$$

其中： $\delta _ { i } ( a )$ 表示取系数中属于第i类的那部分，SCI值越大意味着系数的集中程度越高，当SCI值为1时意味着系数集中在单独的一个类别中，其他类别的系数都为零，而当 SCI值为0时则意味着所有类别的系数绝对值和都相等。通过计算本文得到RCSRC，CRC_RLS 和 SRC 的 SCI值分别为：0.2045，0.1393和0.9308，而三个方法的计算时间分别是：RCSRC 为 0.040482 s；CRC_RLS为 $0 . 0 1 4 7 6 9 \mathrm { ~ s ~ }$ ；SRC为0.294314s（实验环境:Inteli9-7980XECPU 和16GB内存，MATLAB2018a)。本文的方法计算得到的系数稀疏程度介于SRC和CRC_RLS之间，然而对比SRC的计算时间成本，RCSRC在求解速度上具有优势。

![](images/b093bed3fb5c3a4a1e8f90907ed0a054e43b5305b168f21efb4aa007455285bb.jpg)  
图1RCSRC计算得到的测试样本系数分布

![](images/b691f54a9cf9f4bd5002230bc879f834481223d396e506efeb136473771a5f33.jpg)  
Fig.1Distribution of coefficients of the test sample computing by   
图2CRC_RLS计算得到的测试样本系数分布  
Fig.2Distribution of coefficients of the test sample computing by CRC_RLS

![](images/d6eccf9e510807a894f486a2f1b0435acd7c6dc8969349737737c8d58ed0817e.jpg)  
图3SRC计算得到的测试样本系数分布

SRC

# 3 实验分析

为了验证RCSRC在不同人脸识别和图像识别场景中的性能，本文在主流的人脸和物体图像库Georgia Tech(GT)[24],Extend YaleB[23]，LFW[25]和COIL-20[26]进行实验。对比的同类型识别算法有 SRC[2]，CRC[10]，ProCRC[17]和DSRC[18],其中 SRC 通过 L1LS 算法求解。所有的实验在安装有MATLAB2018a，配置为Inteli9-7980XECPU 和16GB内存的PC上运行。

a)GeorgiaTech人脸数据库。GT数据库包含50个个体的750张人脸图片，每个个体有15张图片。这些人脸存在包括表情，光照和尺度等变化。所有测试和训练的人脸图片经过灰度化以后通过手动裁剪和缩放至 $2 5 ^ { * } 2 0$ 的尺寸，每张图片原始像

素在标准化之后直接被拉伸为列向量形式组成字典。图4展示了GT人脸数据库中剪裁以后的人脸图片。本文随机在每类样本中选择8和10张作为训练图片，剩余图片作为测试图片，随机实验分别进行10次，最后得到如表1所示的平均分类准确率和方差。

![](images/769515fe9e53d6a74c1a0009cf2a8e85df723cc7fd2b47cb8faebbe2e0c182d9.jpg)  
Fig.3Distribution of coefficients of the test sample computing by   
图4GT人脸数据库中人脸图像Fig.4Face images from GT face database表1GT数据库人脸识别实验结果 $( \% )$

Table 1Experiment results on GT database(%)   

<html><body><table><tr><td>算法</td><td>8/15</td><td>10/15</td></tr><tr><td>RCSRC</td><td>79.03±0.03</td><td>83.28±0.04</td></tr><tr><td>CRC_RLS</td><td>71.49±0.04</td><td>74.12±0.02</td></tr><tr><td>SRC</td><td>68.37±0.03</td><td>72.88±0.06</td></tr><tr><td>ProCRC</td><td>71.63 ±0.05</td><td>74.6±0.02</td></tr><tr><td>DSRC</td><td>78.49±0.02</td><td>82.2±0.05</td></tr></table></body></html>

从实验结果中可以看到RCSRC在所有对比的方法中具有最好的结果。SRC由于训练样本数量的限制表现最差。

b）ExtendYaleB人脸数据库。ExtendYaleB 数据库由2414张人脸图片组成，包含31个人的人脸图像。这些图像在实验室控制的不同条件光线下采集得到。本文在每个人中选择64张图片用于实验，每张图片通过手工裁剪和缩放至$2 0 ^ { * } 2 0$ 大小，图5展示了裁剪得到的人脸图像。本文在每个类别中随机选择10、15、20、25和30张图片作为训练样本，剩余的作为测试样本，分别进行10次实验。实验结果如表2所示。

![](images/8288ae4d6189413d629ec906d6b31ab89a47ff2ab036cc2c7bada93ca33ac060.jpg)  
图5ExtendYaleB人脸数据库中人脸图像Fig.5Face images from Extend Yaleb face database

由表中的数据可以发现RCSRC相较于其他方法准确率高了 $1 \% { \sim } 2 \%$ 。此外还可以看到当每类训练样本数量在小于20 的情况下分类准确率在递增，然而在大于20的情况下结果趋于稳定，甚至有下降趋势，这是由于训练样本组成的线性空间达到饱和状态，即字典的列数大于行数，意味着测试样本可以被完全的线性表示出来。此外某些比较相似的类别由于表示样本的增加使其表示空间也相应的增大，这会使得不同类别之间误分类风险增加，所以导致最后分类准确率的下降趋势。

表2ExtendYaleB人脸数据库实验结果 $( \% )$   

<html><body><table><tr><td>算法</td><td>10/64</td><td>15/64</td><td>20/64</td><td>25/64</td><td>30/64</td></tr><tr><td>RCSRC</td><td>93.36±0.04</td><td>96.12±0.02</td><td>98.26±0.01</td><td>97.68±0.02</td><td>97.46±0.02</td></tr><tr><td>CRC_RLS</td><td>87.79±0.21</td><td>93.22±0.12</td><td>97.14±0.04</td><td>96.05±0.09</td><td>95.94±0.05</td></tr><tr><td>SRC</td><td>89.24±0.07</td><td>93.29±0.05</td><td>95.92±0.05</td><td>96.68±0.03</td><td>96.82±0.02</td></tr><tr><td>ProCRC</td><td>87.93±0.21</td><td>93.36±0.11</td><td>97.32±0.04</td><td>96.29±0.09</td><td>96.29±0.04</td></tr><tr><td>DSRC</td><td>91.77±0.04</td><td>94.9±0.03</td><td>98.02±0.01</td><td>97.37±0.02</td><td>96.78±0.03</td></tr></table></body></html>

c)LFW人脸数据库。LFW数据库包含超过13000张在网页中采集的人脸图片。这些图片存在姿态，光照，表情，遮挡等变化，图6给出了LFW人脸数据库矫正裁剪以后的示例图片。所有用于实验的人脸图片经过矫正，裁剪和缩放至 $5 0 ^ { * } 4 0$ 大小。在本文的实验中采用两种方案：方案一是挑选出每类样本数量大于16的类别组成子集，在子集中的每个类别随机挑选15张作为训练样本，剩余的作为测试样本；方案二是挑选出每类样本数量大于11的类别组成子集，在子集中的类别随机挑选10张作为训练样本，剩余的作为测试样本，实验结果如表3所示。由于在LFW的人脸图片是在不受控制的情况下采集得到，所以在该数据库上进行实验具有很大的挑战性，主要原因是同类样本之间的差异性较大，在不同类别的训练样本组成的空间分布会出现很大的重合空间，不同空间之间的界限变得模糊，RCSRC利用标签信息使得训练样本空间界限清晰所以得到较好的分类结果。

d)COIL-20物体图像数据库。COIL-20包含20个类别的物体，每个类别有72张不同角度的图片。所有用于实验的图片均缩放至 $1 5 ^ { * } 1 5$ ，图7给出了部分类别的示例。本文随机地在每类的72张图片中抽取10、15和20张图片作为训练样本，分别随机进行10次实验，实验结果如表4所示。物体识别相比人脸识别，不同个体之间差异较大，所以所有方法的表现差异不大，本文方法只比其他方法高出 $1 \% { \sim } 3 \%$ 。

![](images/01bd778c7648da36ab5cbb23aa8924199dc727008012ff66cda378b0ce8af90e.jpg)  
图6LFW人脸数据库中人脸图像Fig.6Face images from LFW face database表3 LFW数据库人脸识别实验结果 $( \% )$

Table 3Experiment results on LFW database $( \% )$   

<html><body><table><tr><td>算法</td><td>LFW11</td><td>LFW16</td></tr><tr><td>RCSRC</td><td>54.83±0.01</td><td>63.55±0.04</td></tr><tr><td>CRC_RLS</td><td>51.13 ±0.03</td><td>57.48±0.05</td></tr><tr><td>SRC</td><td>43.92±0.03</td><td>50.33±0.02</td></tr><tr><td>ProCRC</td><td>52.33±0.03</td><td>58.55±0.05</td></tr><tr><td>DSRC</td><td>52.66±0.01</td><td>61.47±0.02</td></tr></table></body></html>

![](images/96703566e93d36b842b32414eee3b101192788e92ad7660612f087722dc1591b.jpg)  
图7COIL-20 物体图像数据库 Fig.7Object images from COIL-20 database 表4COIL-20 物体图像识别结果 $( \% )$

Table 2Experiment results on Extend yaleb face database $( \% )$   
Table 4Experiment results on COIL-20 database $( \% )$   

<html><body><table><tr><td>算法</td><td>10/72</td><td>15/72</td><td>20/72</td></tr><tr><td>RCSRC</td><td>95±0.07</td><td>97.83±0.02</td><td>98.27±0.02</td></tr><tr><td>CRC_RLS</td><td>90.56±0.09</td><td>92.18±0.03</td><td>93.13±0.04</td></tr><tr><td>SRC</td><td>90.4±0.05</td><td>95.48±0.02</td><td>97.25 ±0.005</td></tr><tr><td>ProCRC</td><td>91.26±0.09</td><td>92.85±0.03</td><td>93.89±0.04</td></tr><tr><td>DSRC</td><td>94.31±0.05</td><td>97.32±0.02</td><td>97.9±0.03</td></tr></table></body></html>

# 4 结束语

传统的稀疏表示方法SRC在稀疏约束的条件下能够得到良好的分类表现，但是由于SRC计算代价较高，而松弛约束下的CRCRLS虽然计算代价降低，但稀疏性不够。针对传统稀疏表示方法不足，本文提出基于 $L _ { 2 }$ -范数的重构样本约束方法RCSRC，通过构造对重构样本模长和不同类别分量相关性的约束以较快的速度得到稀疏的系数。通过在主流人脸和物体图像数据库上和同类算法的对比实验证明了本文提出的方法在复杂情况下的人脸识别具有良好的表现。

# 参考文献：

[1]吴巾一，周德龙．人脸识别方法综述[J].计算机应用研究,2009,26 (9):3205-32o9.(Wu Jinyi,Zhou Delong.Survey of face recongnition [J].Application Research of Computers,2009,26 (9):3205-3209.)   
[2]Wright J,YangAY,GaneshA,etal.Robust face recognition via sparse representation [J].IEEE ‘Irans on Pattern Analys1s and Machine Intelligence,2009,31 (2): 210-227.   
[3]Yang A Y,Zhou Zihan，Balasubramanian A G，et al.Fast $l _ { 1 }$ -Minimization Algorithms for Robust Face Recognition [J]. IEEE Trans on Image Processing,2013,22 (8): 3234-3246.   
[4] 张圭，徐斌，周尚波，etal．基于稀疏表示的自适应图像超分辨率重 建算法[J].计算机应用研究,2013,30(3):938-941.(Zhang Yao, Xu Bin, Zhou Shangbo, Zheng Jian. Image super-resolution with adaptive regularization sparse representation [J]. Application Research of Computers,2013,30 (3): 938-941.)   
[5]Liu Tao,Mi Jianxun,Liu Ying,et al.Robust face recognition via sparse boosting representation [J]. Neurocomputing,2016,214: 944-957.   
[6]康利攀，陈方福，范自柱．一种新的拓展稀疏人脸识别算法[J]．计 算机应用研究,2016,33(3):937-939.(Kang Lipan,Chen Fangfu,Fan Zizhu.New extended sparse representation for face recognition [J]. Application Research of Computers,2016,33(3):937-939.)   
[7] 汤镇宇，孟凡荣，王志晓．基于稀疏表示的快速 $\mathrm { l } _ { 2 }$ -范数人脸识别方 法[J].计算机应用研究，2016,33(9):2831-2836.(Tang Zhenyu, Meng Fangrong,Wang Zhixiao.Fast face recognition with regularized least square via sparse representation [J].Application Research of Computers,2016,33 (9): 2831-2836.)   
[8]Mi Jianxun，Fu Qiankun，Li Weisheng.Adaptive class preserving representation for image classification [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2017: 7427-7435.   
[9] 沈韬，李克清，夏瑜．一种鲁棒稀疏表示的单样本人脸识别算法[J]. 计算机应用研究,2018,35(11): 3491-3496.(Shen Tao,Li Keqing, Xia Yu. Single sample face recognition based on robust sparse representation [J].Application Research of Computers,2018,35(11): 3491-3496.)   
[10] Zhang Lei,Yang Meng,Feng Xiangchu.Sparse representation or collaborative representation: Which helps face recognition?[C]/Proc of IEEE International Conference on Computer vision. 2011: 471-478.   
[11] Xu Yong,Zhang David, Yang Jian,et al.A two-phase test sample sparse representation method for use with face recognition [J]. IEEE Trans on Circuits and Systems for Video Technology,2011,21(9):1255-1262.   
[12] Xu Yong, Zuo Wangmeng, Fan Zizhu. Supervised sparse representation method with a heuristic strategy and face recognition experiments [J]. Neurocomputing,2012,79: 125-131.   
[13] Mi Jianxun.Face image recognition via collaborative representation on selected training samples [J]. Optik,2013,124 (18): 3310-3313.   
[14] Xu Yong,Zhu Qi,Fan Zizhu,et al.Using the idea of the sparse representation to perform coarse-to-finefacerecognition[J]. Intormation Sciences,2013,238(/): 138-148.   
[15] Mi Jianxun,Sun Yueru,Lu Jia.Robust face recognition based on supervised sparse representation [C] // Proc of International Conference on Intelligent Computing.Cham: Springer, 2018:253-259..   
[16] Timofte R，Van Gool L.Adaptive and weighted collaborative representations for image classification [J].Pattern Recognition Letters, 2014, 43(7): 127-135.   
[17] Cai Sijia,Zhang Lei，Zuo Wangmeng，et al.A probabilistic collaborative representation based approach for pattern classification [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2016: 2950-2959.   
[18] Xu Yong,Zhong Zuofeng, Yang Jian,et al. A new discriminative sparse representation method for robust face recognition via $\mathrm { L } _ { 2 }$ regularization [J]．IEEE Transon Neural Networksand Learning Systems, 2017,28(10): 2233 - 2242.   
[19] Tibshirani R.Regression shrinkage and selection via the lasso [J]. Journal of the Royal Statistical Society. Series B(Methodological), 1996: 267-288.   
[20] Chi Hongmei,Xia Haifeng,Zhang Lifang,et al. Competitive and collaborative representation for classification [J].Pattern Recognition Letters,2018.https://doi.org/10.1016/j.patrec.2018.06.019.   
[21] YuanHaoliang，Li Xuecong， XuFangyuan，etal. A collaborative-competitive representation based classifier model [J]. Neurocomputing,2018,275(1): 627-635.   
[22] Yuan Ming,Lin Yi. Model selection and estimation in regression with grouped variables [J]. Journal of the Royal Statistical Society: Series B (Statistical Methodology),2006,68 (1): 49-67.   
[23] Georghiades A S,Belhumeur P N,Kriegman D J. From few to many: Illumination cone models for face recognition under variable lighting and pose [J]. IEEE Trans on Pattern Analysis and Machine Intelligence, 2001,23 (6): 643-660.   
[24] Goel N,Bebis G,Nefian A.Face recognition experiments with random projection [C]//Biometric Technology for Human Identification II.2005: 426-438.   
[25] Huang G B,Mattar M,Berg T,et al.Labeled faces in the wild:a database forstudying face recognition in unconstrained environments [C]/Proc of Workshop on Faces in 'Real-Life' Images:Detection, Alignment,and RECOGNItion.2008.   
[26] Nene S A,Nayar S K,Murase H. Columbia object image library (coil-20）[R/OL].1996.https://doc.uments.com $/ \mathrm { g }$ -columbia-objectimage-library-coil-20.pdf.