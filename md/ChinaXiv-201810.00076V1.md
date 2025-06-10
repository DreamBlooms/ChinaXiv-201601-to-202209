# 基于深度置信网络的实木板材缺陷及纹理识别研究

胡忠康，刘英，周晓林，赵乾，沈鹭翔(南京林业大学机械电子工程学院，南京 210037)

摘要：针对在现代木材加工企业中，实木板材以缺陷及纹理为主要品质分级要素的需求，提出利用基于局部二值模式、自学习的深度置信网络与 Softmax 分类器组合的深度学习算法，实现对实木板材缺陷及纹理的分类。首先提取实木板材的缺陷及纹理特征，在此基础上利用深度置信网络对经过局部二值化处理的特征进行训练学习，并采用可自学习的学习率算法优化收敛速度、减少训练时间，最后使用 Softmax分类器获取常见缺陷及直纹、花纹的分类结果。通过与BP神经网络、支持向量机、极限学习机等几种经典算法的比较，采用深度置信网络得到的实木板材缺陷及纹理识别的误差率在 $3 . 5 9 \%$ 左右，在实木板材缺陷和纹理上取得了更好的识别效果。

关键词：缺陷识别；纹理识别；深度置信网络；自学习；局部二值模式 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.07.0438

# Research on defects and textures recognition of solid wood lumbers based on deep belief network

Hu Zhongkang, Liu Ying†, Zhou Xiaolin, Zhao Qian, Shen Luxiang (NanjingForestry University,CollgeofMechanical&Electronic Engineering,Nanjing210037,China)

Abstract:In modern wood procesing enterprises,themainqualityclassification factors ofsolid wood lumbers aredefects and textures.This research proposes adeep learning algorithm basedona mixtureoflocal binary pattern,self-learning deep belief networksandSoftmax classificationtoclasifysolid woodlumbers withdefectsandtextures.Firstlyit extracts thedefectsand textures featuresofsolidwoodumbers,onwhichtobebased,uses thedeepbeliefnetworks totrainandlear thecharacteristics of thelocalbinarized processng.Afterwards,itadopts theself-learninglearingrate algorithm tooptimizetheconvergence speed andreduce the tainingtime.Finally,tealgorithmobtainthecommon defects,straighttexturesandconfusedtextures by usingaSoftmax clasification.Comparedwithclasscal algorithms e.g.BP neuralnetwork,supportvector machineand extreme learming machine,theerorrateofsolidwooddefectsand texturesrecognitionobtainedbythedeep belief networks designed is about $3 . 5 9 \%$ ,and this algorithm works efficiently in recognition the defects and textures of solid wood lumbers.

Key words: defect recognition; texture recognition; deep belief network; self-learning; local binary pattern

# 0 引言

深度学习自Hinton2006年提出以来，以其强大的功能在语音[1]、图像[2]、视频[3]、文本[4]等领域取得了巨大的突破。深度学习的概念是相对于传统的浅层学习算法提出来的，它模拟人脑分析问题的过程，通过组合、学习低层数据形成更抽象的高层特征表示（类别、属性等)，以提高特征识别和分类的准确性。传统的浅层学习结构，如支持向量机、最大熵模型、隐马尔可夫模型等，仅仅是将原始的输入数据转换到特定问题空间内，形成易于处理的某种简单的特征结构[5]。这些浅层学习结构在有限的样本和计算资源情况下，对复杂问题的表示能力也很有限，泛化性较差。相比较而言，深度学习可以实现复杂函数的非线性逼近，表征输入数据的分布式表示，展现出强大的从海量数据样本中集中学习数据集本质特征的能力[]。

在图像识别方面，深度学习最典型的应用是在手写字数据集MINST的识别上，将错误率降低至 $1 . 2 \% _ { \circ } 2 0 1 2$ 年,Krizhevsky在ImageNet大规模视觉识别挑战赛中将深度学习和卷积神经网络结合，设计出的深度网络模型AlexNet可以将识别错误率降至 $1 5 . 3 2 \%$ ，远低于第二名使用传统方法得出的识别错误率$2 6 . 2 \%$ 。至2014年，参赛选手更是在Krizhevsky设计的网络结构基础上进行优化改良，设计出GoogLeNet，识别错误率已成功降至 $6 . 6 6 \% \text{ textperthousand}$ 年，ResNet网络结构识别错误率为 $3 . 5 7 \%$ 已经超过人类的识别错误率 $5 . 0 0 \%$ 。2017年，错误率已低至$2 . 2 5 \%$ 。2010至2017年ImageNet竞赛的识别错误率如图1所示。

![](images/deb3e4a3a810b122c0768564227b1a1f52b440dafe6f9a4971a0896c6cd8a462.jpg)  
图12010 年至2017年ImageNet竞赛的识别错误率

在木材加工生产中，木材缺陷会对木材的品质产生很大的影响，而木材的品质又决定了木材及其制品的商品价值和使用价值。国内木材原材料综合使用率非常低，只有 $6 3 \%$ ，远不及发达国家平均 $8 0 \%$ 以上的利用率，而木材缺陷检测效率较低是其中主要原因之一[7]。近年来，众多学者为了提高木材原料综合使用率，研究并提出了木材缺陷的检测方法[8：如基于3D扫描技术的木材缺陷定量化分析[9]、钻入阻抗法检测木材缺陷[10]、基于快速 $l _ { I }$ 算法和LBP 算法的木材缺陷识别[I等。这些方法或多或少存在着因检测设备成本高、对实际检测的工作环境要求苛刻等问题，无法大规模产业化推广应用。而基于机器视觉的木材缺陷检测技术既可以降低识别过程中的主观因素影响，又可以摆脱对特定检测设备的依赖，对环境的要求也比较低，因此成为首选检测技术。

传统的机器视觉技术大多是基于浅层学习算法的，这些浅层学习算法在识别木材缺陷时，往往需要经过繁琐的处理过程，如图像预处理、阈值分割、特征提取、模式识别、边缘检测等等一系列过程，识别精度却很难令人满意[12]，这对于复杂的木材的纹理信息检测带来很大困难。基于此，本文将深度学习中的深度置信网络用于木材缺陷及纹理识别，并加入LBP特征提取和一种自学习步长大小方法，以优化算法的特征学习过程，降低算法训练时间。

# 1 深度置信网络

GeoffreyHinton 在 2006 年提出的深度学习模型为深度置信网络（deepbeliefnetworks,DBN)，其快速贪心逐层无监督训练算法在多层神经网络中具有降维作用[13]。DBN是结合了无监督学习和监督学习的深度学习模型，它是由若干层受限玻尔兹曼机和反向微调算法组成的，可以用于提取训练数据中深层结构的特征信息。

# 1.1受限玻尔兹曼机

玻尔兹曼机（Boltzmannmachine,BM）是一种生成式随机全连接神经网络，且对称连接，无自反馈，属于自编码网络的范畴，具有强大的无监督学习能力，能够学习数据集中复杂的规则。但其训练时间较长，很难获取它的概率分布情况。为了克服这一缺陷，Smolensky引入了受限玻尔兹曼机（restrictedBoltzmannmachine,RBM），该网络由一些可见单元(对应可见变量，visible unit)和一些隐藏单元(对应隐藏变量，hidden unit)构成，可见单元 $\mathbf { \Phi } _ { \nu }$ 和隐藏单元 $h$ 都是二元变量，亦即其状态取0或1。整个网络是一个二分图，只有可见单元和隐藏单元之间才会存在边，而可见单元之间和隐藏单元之间都不会有边相连接。如图2所示BM和RBM的网络结构。

![](images/fca8521639c281959f2583609a2d85afc457ef9f1033532121c5cffb50f0bcd5.jpg)  
图2玻尔兹曼机与受限玻尔兹曼机的网络结构

RBM是一种基于能量的模型（EnergyBasedModel,EBM)。根据EBM对于一个随机系统的描述，系统的能量波动和系统的有序程度相关，越有序的系统其能量波动越小，系统愈趋于平衡状态。反之越无序的系统其能量波动越大，系统愈趋于不平衡状态。对于一组给定的状态（v，h)，其可见单元 $\mathbf { v }$ 和隐藏单元h的联合配置能量函数为： $E ( v , h | \theta ) =$ $\begin{array} { r } { - \sum _ { i = 1 } ^ { n } b _ { i } v _ { i } - \sum _ { j = 1 } ^ { m } c _ { j } h _ { j } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } v _ { i } W _ { i j } h _ { j } } \end{array}$ (1)

式中， $\theta = \{ W _ { i j } , \ b _ { i } , \ c _ { j } \}$ 为 RBM的参数， $W _ { i j }$ 为可见单元v和隐藏单元 $\mathbf { h }$ 之间边的权重， $b _ { i }$ 为可见单元 $\mathbf { v }$ 的偏置， $c _ { j }$ 为隐藏单元 $\mathbf { h }$ 的偏置。基于该能量配置函数得到 $( \boldsymbol { \mathbf { \rho } } _ { \boldsymbol { \mathbf { V } } , \boldsymbol { \mathbf { h } } } )$ 的联合概率：

$$
\begin{array} { r } { P _ { \theta } ( v , h ) = \frac { 1 } { Z ( \theta ) } \mathrm { e x p } ( - \mathrm { E } ( \mathrm { v } , \mathrm { h } | \theta ) ) } \end{array}
$$

其中： $\begin{array} { r } { Z ( \theta ) = \sum _ { v , h } \exp ( { - E ( v , \mathrm { h } \mid \theta ) } } \end{array}$ 是归一化因子，也称为分配函数。

由于可见单元 $\mathbf { v }$ 和隐藏单元 $\mathbf { h }$ 条件独立，且RBM模型的对称结构，当给定可见单元 $\boldsymbol { v } _ { i }$ 的状态时，第 $j$ 个隐藏单元的激活概率为

$$
\begin{array} { r } { \mathrm { P } \big ( h _ { j } = 1 \big | \boldsymbol { v } \big ) = \sigma ( c _ { j } + \sum _ { i } W _ { i j } v _ { i } ) } \end{array}
$$

其中：σ(x)=（1+exp(-x)°。

同理，当给定隐藏单元 $h _ { j }$ 的状态时，第i个可见单元的激活概率为：

$$
\begin{array} { r } { \mathrm { P } ( v _ { i } = 1 | h ) = \sigma ( b _ { i } + \sum _ { j } W _ { i j } h _ { j } ) } \end{array}
$$

由可见单元 $\mathbf { v }$ 的对数似然概率对 $W _ { i j }$ 求偏导，得到RBM权重更新准则为

$$
\Delta W _ { i j } = \varepsilon ( < v _ { i } h _ { j } > _ { d a t a } - < v _ { i } h _ { j } > _ { m o d e l } ) ~
$$

其中： $\varepsilon$ 为权重学习速率， $< v _ { i } h _ { j } > _ { d a t a }$ 为数据分布的期望，$< v _ { i } h _ { j } > _ { m o d e l }$ 为 RBM 模型定义的期望。利用对比散度算法（contrastive divergence,CD)，借助Gibbs 采样得到近似的概率分布，以此概率分布来估计所需的概率分布，得到 $< v _ { i } h _ { j } > _ { m o d e l }$

的近似值，完成权值更新。

Gibbs采样是一种基于马尔可夫链蒙特卡洛方法（MarkovchainMonteCarlomethods,MCMCM）的采样，它的处理过程是：

对于一个长度为K的随机向量 $\mathbf { X } = ( X _ { 1 } , X _ { 2 } , \ldots , X _ { K } )$ ，假设我们无法求得关于X的联合分布 $\mathrm { P } \mathrm { ( X ) }$ ，当给定X的其他分量时，第K个分量 $X _ { K }$ 的条件分布 $\mathrm { P } ( X _ { K } | X _ { K - } )$ ，其中 ${ \cal X } _ { K - } =$ $( X _ { 1 } , X _ { 2 } , \ldots , X _ { K - 1 } , X _ { K + 1 } , \ldots , X _ { K } )$ ，对于X的一个任意状态开始，利用分量的条件分布，迭代的对其分量依次采样，随着采样次数的增加，随机变量 $\mathrm { X } ( n ) = ( X _ { 1 } ( n ) , X _ { 2 } ( n ) , \ldots , X _ { K } ( n ) )$ 的概率分布将以 $\mathfrak { n }$ 的几何级数收敛于 $\mathrm { \Delta } \mathrm { X }$ 的联合概率分布 $\mathrm { P } \mathrm { ( X ) }$ 0

# 1.2深度置信网络结构和学习过程

DBNs是一个包含多隐藏层的深层神经网络模型，本文采用的DBNs如图3所示，这是一个由四个RBM构成的DBNs。输入数据作为第一层RBM的可见层进行无监督预训练，然后第一层获取的输入表征作为第二层RBM可见层数据，，在经过四层RBM后，可以加入额外的学习算法（如BP神经网络等）把学习得到的表征转换为有监督的预测，同时比较期望输出类标和预测输出类标对权重进行微调。Hinton教授2006年设计的DBNs网络结构，采用一种无监督贪婪逐层训练方法以训练生成模型，在每一阶段训练当中寻求最优解。由于贪婪算法寻求的是局部最优解，因此必须要经过一个全局学习算法对网络参数微调，从而得到全局最优解。

![](images/ad5cd5f9da5b5e0bf40c07518bde0a571d3ebe4a32ce902f397149deae57b9a6.jpg)  
图3 DBN网络结构

# 2 基于DBNs 的木材缺陷识别

本文拟采用四层RBM构建的DBNs对木材缺陷进行识别，利用一层的BP神经网络对其参数进行微调。为了DBNs能够更好地处理图像信息，本文加入了局部二值模式（local binarypatterm,LBP）进行特征提取；采用自学习的学习率优化训练过程，并在DBN最后一层加入Softmax分类器实现特征分类。

# 2.1LBP对木材图像的处理

LBP能够提取缺陷特征信息，在提取纹理特征时更是表现良好[14]，故本文选用LBP 提取木材图形的特征信息。LBP 算子限定在 $3 ^ { * } 3$ 个像素点范围内，以正方形中心点的像素大小为标准，对该正方形外围的像素点进行比较。若外围像素点的值比中心值大，则当前位置的值置为1；否则当前位置的值置为0;通过这种规则将原本局部区域的像素值二值化，简化数据以方便后续图像处理。为了使提取的特征具有旋转不变性[15]，旋转LBP 选定的局部区域，得到多个不同模式的二值化数列，从这些数列中选取数值最小的值来表示其特征值。另外，一种均匀LBP模式，即要求二进制序列从0到1或者从1到0的变换不超过2次（二进制序列是首尾相连的)，可以起到降维作用，而且能克服旋转LBP模式中一幅图像里分布出现的频率差异较大的问题，本文正是利用这种均匀LBP模式确保图像的旋转不变性。图4所示的是LBP算子局部二值化过程，图5显示的是木材图像LBP处理后的效果，可以很好地提取木材图像的特征信息。图6显示木材图像灰度化及LBP处理后的统计的直方图。根据图图4中的LBP特征矩阵，可以得到一个从左上角开始按顺时针方向的二进制串11100111，将二进制串转换成十进制的LBP值，计算出该像素点的LBP值为$1 + 2 + 4 + 3 2 + 6 4 + 1 2 8 = 2 3 1$ 。同理，可以统计出木材图像的LBP特征直方图。

![](images/a89459052825eff82ef3287ba6700d93e1de8a31d2836d65ba3c057e992dc6ea.jpg)  
图4局部二值化过程

![](images/3bd615fc986739603ce7c45698ab7eb1f6e99c15748dbc129f106ca546d9b99c.jpg)  
图5原始图像、经过灰度化和LBP处理后的木材图像

![](images/784fb501b2d67094bf5e3c141898ce5557527e225abe7b2afabf301de8069460.jpg)  
图6灰度化和LBP处理后图像的直方图

# 2.2自学习的深度置信网络算法

DBNs网络是在RBM模块上逐层训练得到相应的空间参数并构建整个网络层次架构，而RBM基于CD的快速学习算法中通常采用一个全局的学习率来对网络进行训练。然而，如果学习率过大，将导致重构误差急剧增加，权重也会变得异常大；学习率过小，则可避免上述情况出现，但收敛速度较慢，训练时间过长。为克服这一矛盾，在传统的DBNs算法基础上，将自学习步长大小这一概念引入，提出了在CD快速算法的迭代过程中，对于每一个连接权重 $W _ { i j }$ ，使用一个独立的步长大小(学习率)参数 $\cdot \gamma _ { i j }$ ，来替代原DBNs网络中的全局学习率，而步长的具体大小则根据因子的改变做出相应的调整 $\dot { \gamma } _ { i j }$ ，这里涉及的因子包括增量因子 $\mathbf { \Omega } _ { u }$ ( $u { > } 1$ ）和减量因子 $d ( 0 < d < 1 )$ 。若连接权重更新 $\Delta W _ { i j } > 0$ ，用 ${ u \gamma _ { i j } }$ 更新步长；若连接权重更新 $\Delta W _ { i j } < 0$ 用 $d \gamma _ { i j }$ 更新步长。在学习过程中为了避免由于过大的步长而产生冲突，如果某一权重更新方向连续两次相同，则步长增加，反之则步长减小。

# 2.3基于LBP与自学习DBNs 的木材缺陷识别

利用LBP进行特征提取并利用自学习DBNs 进行分类的木材缺陷识别具体过程如图7所示：

a)数据预处理。首先根据木材图像数据库的特点进行图像分块；之后对每一块当中的每一个像素采用均值LBP进行处理，得到每个像素点的LBP值；然后统计得到每个块的直方图，并进行归一化；最后将每个块得到的直方图表示为特征向量的形式，便于自学习DBNs 进行处理。

b）数据处理。将得到的特征向量输入到自学习DBNs的网络当中。自下而上地抽取特征向量中的深层信息，利用式（3)～（5）和自学习学习率的更新设计，初步确定网络结构中的空间参数 $\{ b _ { i }$ ， $c _ { j }$ ， $W _ { i j } \}$ 后，利用 BP 算法对其进行参数微调和优化。

c）网络逐层建立好之后，在输出层设置一个Softmax分类器，对输出数据进行分类。

![](images/5d773cace859c2094cf1ae66b7cabf14546f66ada52ef61a286719957635e553.jpg)  
图7基于深度置信网络的木材缺陷识别过程

# 3基于自学习DBNs 的木材缺陷及纹理的识别结果和分析

利用LBP处理原始的实木板材图片提取特征生成特征直方图，同时对数据归一化处理，并将数据以特征向量的形式输入到自学习的DBNs的网络中，借助DBNs逐层学习能力对数据进行训练和学习，最后通过Softmax分类器进行分类。

为了验证本方法对木材缺陷及纹理的识别效果，基于MATLAB2017b 的Deep Learning Toolbox，构建本网络模型。DBNs 由四层RBM和一个Softmax 构成主体网络框架，其中，输入层的随机单元数和第一层的可见层的随机单元数相等，大小为 $1 4 4 ^ { * } 9 6 { = } 1 3 8 2 4$ 维，四个隐藏层的维度分别设计为1500,500,250,30，最后经过Softmax分类器输出的维数是8，为分类器的数目。

# 3.1木材缺陷及纹理识别

训练样本共500 张，大小是 $1 4 4 ^ { * } 9 6$ ，其中400 张作为训练样本，100张作为测试样本。部分样本图像如图8所示。样本中杉木缺陷主要有节子、裂缝、孔洞等三种缺陷，以及直纹和花纹两种主要纹理。故将缺陷和纹理排列组合得到节子 $^ +$ 直纹、节子 $^ +$ 花纹、裂纹 $\cdot +$ 直纹、裂纹 $\cdot +$ 花纹、孔洞 $^ +$ 直纹、孔洞 $+$ 花纹、无缺陷 $^ +$ 直纹、无缺陷 $^ +$ 花纹等八种分类结果，用 $\mathbf { k } 0 { \sim } \mathbf { k } 7$ 表示。

![](images/ac90da5528677efe7566a1a476d8fc4618f69b8e2a3a9419afb2a7544c7fdfac.jpg)  
图8训练样本示例

另外，基于本文设计的自学习的DBNs 网络模型中，其增量因子和减量因子分别取1.2和0.8。而在初始化时，将每一层DBN的学习率均置为0.1。随着迭代次数的增加自学习的DBNs网络相较固定学习率DBNs网络的优势愈来愈明显，如下图9所示，分别在自学习率、固定学习率为0.1、固定学习率为0.4和固定学习率为0.7情况下DBNs网络的收敛情况。从图中可以看出，自学习率DBNs网络的性能要优于固定学习率DBNs网络。DBNs网络的学习率不应过大，也不应过小。学习率增加会使网络收敛速度越来越快，过大会导致网络不稳定；学习率减小会使网络愈加趋于稳定，过小会导致收敛速度过慢，易陷入局部最优解[16]。

![](images/e1581dfa885e5dbe920b33722477a09a056e503e3e29ddb1a65b5b7d96cd3381.jpg)  
图9不同学习率的误差率和迭代次数的关系

# 3.2几种算法识别率的比较和分析

为了进一步对分类算法的有效性进行验证，将本文 $\mathbf { L B P + }$ 自学习DBNs+Softmax组合的分类算法同其他四种有代表性的算法进行了对比，即极限学习机（extreme learningmachine,ELM)[17]、支持向量机（support vector machine,SVM）[18]、反馈传播算法（back propagation,BP）[19]、卷积神经网络（convolutionalneural network,CNN）[20]。其中，ELM和 SVM是浅层学习算法中使用比较广泛的两种算法。这里的ELM选取为单隐层的网络，隐层节点数为1000，并结合使用AdaBoost算法克服ELM输出不稳定现象。SVM算法则选用高斯核函数，而BP算法的隐藏层数只有一层，隐层节点数也为1000。CNN具备5层网络结构，包括两个卷积层、两个最大池化层、两个全连接层，同时结合使用了Softmax分类器。各算法具体分类识别率对比如表1所示。通过比较LBP+DBNs+Softmax组合算法性能优于浅层学习算法，也比其他深度学习算法在实木板材缺陷及纹理的识别表现地更好。

表1几种不同图像分类方法误差率比较  

<html><body><table><tr><td>算法名称</td><td>误差率</td></tr><tr><td>Adaboost+ELM</td><td>7.31%</td></tr><tr><td>SVM</td><td>8.77%</td></tr><tr><td>BP</td><td>10.60%</td></tr><tr><td>CNN+Softmax</td><td>5.42%</td></tr><tr><td>LBP+DBNs + Softmax</td><td>3.59%</td></tr></table></body></html>

# 4 结束语

实木板材的缺陷和纹理无损检测方法的不断完善是为了满足现代化木材加工企业提高产品品质、降低经济成本的需求，本文研究深度置信网络在实木板材缺陷和纹理检测中的具体应用，利用LBP对采集的实木板材图像进行处理，得到木材缺陷和纹理信息，并转换成特征直方图导入DBNs模型中，同时引用自学习的学习率方法至DBNs的逐层RBM学习训练，最后利用Softmax分类器实现缺陷及纹理特征的多分类。在实木板材图像数据集上，以400张杉木图像作为算法的训练集，100 张图像作为算法的测试集，借助Matlab 的Deep Learning Tool Box和GTX1080TiGPU，优化算法训练时间，验证算法的有效性。本算法能在迭代400次左右收敛，而且收敛时间也在 ${ 5 0 0 } \mathrm { m s }$ 以内，算法识别误差率达到了 $3 . 5 9 \%$ ，相较于ELM、SVM、BP、CNN等算法无法准确地识别木材纹理特征，本算法能取得很好的分类效果。当然，本算法在处理几百万及以上像素点的高维图像时，处理时间和检测精度仍需改进；将本文中实木板材缺陷和纹理检测方法迁移到完整实木板材图像的缺陷和纹理检测中。在今后的学习和研究中，进一步从这两个方面优化算法。

# 参考文献：

[1]侯一民，周慧琼，王政一．深度学习在语音识别中的研究进展综述[J]. 计算机应用研究,2017,34(8):2241-2246.(Hou Yimin,Zhou Huiqiong, Wang Zhengyi. Overview of speech recognition based on deep learning [J]. Application Research of Computers,2017,34(8):2241-2246.)   
[2]刘栋，李素，曹志冬.深度学习及其在图像物体分类与检测中的应用综 述[J].计算机科学,2016,43(12):13-23.(Liu Dong,Li Su,Cao Zhidong. State-of-the-art on deep learning and its application in image object classification and detection [J].Computer Science,2016,43(12): 13 -23.)

[3]Yeh CW,Pan TY,Hu MC.A sensor-based official basketball referee signals recognition system using deep belief networks [M]//Multimedia Modeling. Springer International Publishing,2017: 565-575.

[4]陆军建，林家骏．基于CUDA和深度置信网络的手写字符识别[J]．华 东理工大学学报：自然科学版,2015,41(02):210-215.(LuJunjian,Lin Jiajun.Handwritten character recognition based on CUDA and deep belief networks [J]. Journal of East China University of Science and Technology: Natural Science Edition,2015,41 (02): 210-215.)

[5]尹宝才，王文通，王立春.深度学习研究综述[J].北京工业大学学报, 2015(1): 48-59.(Yin Baocai, Wang Wentong,Wang Lichun.Review of deep learning [J].Journal ofBeijing University ofTechnology,2015(1): 48-59.)

[6]刘建伟，刘媛，罗雄麟．深度学习研究进展[J].计算机应用研究,2014, 31(7):1921-1930.(Liu Jianwei, Liu Yuan,Luo Xionglin.Research and development on deep learning [J].Application Research ofComputers,2014, 31 (7):1921-1930.)

[7]徐姗姗，刘应安，徐昇．基于卷积神经网络的木材缺陷识别[J].山东 大学学报：工学版,2013,43(2):23-28.(Xu Shanshan,Liu Ying’an,Xu Sheng.Wood defects recognition based on the convolutional neural network [J].Journal of Shangdong University (Engineering Science),2013,43 (2): 23-28.)

[8]张厚江，管成，文剑．木质材料无损检测的应用与研究进展[J].林业 工程学报,2016,1(6):1-9.(Zhang Houjiang,Guan Cheng,Wen Jian. Applications and research development of nondestructive testing of wood based materials [J]. Journal of Forestry Engineering,2016,1(6):1-9.)

[9]赵鹏，赵匀，陈广胜．基于3D扫描技术的木材缺陷定量化分析[J].农 业工程学报，2017,33(07):171-176.(Zhao Peng，Zhao Yun,Chen Guangsheng.Quantitative analysis of wood defect based on 3D scanning technique [J]. Trans of the Chinese Society of Agricultural Engineering, 2016, 1 (6): 1-9. )

[10]张富文，许清风，张治宇，等．钻入阻抗法检测木材缺陷[J]．无损检 测,2016,38 (01): 6-9,74.(Zhang Fuwen,Xu Qingfeng,Zhang Zhiyu,et al. Wood defect inspection by drilling resistance method[J].Nondestructive Testing,2016,38 (01):6-9,74.)

[11]熊伟俊，杨绪兵，云挺，等．基于快速I1算法和LBP 算法的木材缺陷 识别[J].数据采集与处理,2017,32(6):1223-1231.(Xiong Weijun,Yang Xubing, Yun Ting, Zhu Zhengli.Automatic Wood defect recognition based on fast ll-Minimization algorithm and LBP algorithm [J].Journal of Data Acquisition and Processing,2017,32(6): 1223-1231.)

[12]汤勃，孔建益，伍世虔．机器视觉表面缺陷检测综述[J].中国图象图 形学报,2017,22(12):1640-1663.(Tang Bo,Kong Jianyi,Wu Shiqian. Review of surface defect detection based on machine vision [J].Journal of Image and Graphics,2017,22 (12): 1640-1663.)

[13] Lecun Y,Bengio Y,Hinton G.Deep learning[J]. Nature,2015,521 (7553): 436.

[14] Tucker JA.Rotation invariant features for color texture classification and retrieval under varying illumination [J].Pattern Analysis & Applications,

2013,16 (1): 69-81.

[15]黄辰，费继友，刘晓东．基于高斯局部二值模式的纹理特征分类方法 [J]．电子技术应用,2018,44(1):121-124.(Huang Chen,Fei Jiyou,Liu Xiaodong. Texture feature method based on Gaussian local binary pattern [J].Computer Technology and Its Applications,2018,44(1): 121-124)

[16]Li Chen,Zhao Shuai,Xiao Ke,et al.Face recognition based on the combination of enhanced local texture feature and DBN under complex illumination conditions [J]. Journal of Information Processing Systems, 2018,14(1):191-204.

[17]Tang Jiexiong,Deng Chenwei, Huang Guangbin.Extreme learning machine for multilayer perceptron [J]. IEEE Trans on Neural Networks & Learning Systems,2017,27 (4): 809-821.

[18] Zhang Ce,Wang Tiejun,Atkinson P M,et al.A novel multi-parameter support vector machine for image classification [J]. International Journal of Remote Sensing,2015,36(7): 1890-1906.

[19]戚大伟，牟洪波．基于Hu 不变矩和 BP 神经网络的木材缺陷检测[J]. 东南大学学报：自然科学版,2013,43(s1):63-66.(QiDawei,Mu hongbo. Detection of wood defects types based on Hu invariant moments and BP neural network [J].Journal of Southeast University: Natural Science Edition, 2013,43 (s1): 63-66.)

[20]常亮，邓小明，周明全，等．图像理解中的卷积神经网络[J]．自动化 学报，2016,42 (9):1300-1312.(Chang Liang,Deng Xiaoming,Zhou Mingquan,et al. Convolutional neural networks in image understanding [J]. Acta Automatica Sinica,2016,42 (9):1300-1312.)