# 一种双流CNN的太阳黑子群磁类型分类方法

杨五谷，田卫新\*，曾曙光，黄瑶(三峡大学 计算机与信息学院，湖北 宜昌 443000)

摘要：太阳耀斑大多数发生在磁极复杂的黑子群上空，因此黑子群磁类型可作为预测太阳耀斑的重要依据。针对同时具有白光图和磁图数据的太阳黑子分类，提出了一种双流CNN 的黑子群磁类型分类方法。该方法通过两个网络分支同时提取白光图和磁图特征，在全连接层对二类特征进行融合，最后用于训练和分类。实验表明该方法能较好避免单通道网络模型的信息损失以及使用双通道图像合成出现的白光图和磁图的相互影响，加权F1分数可达 $8 4 . 8 7 \%$ ，平均准确率可达 $8 4 . 9 3 \%$ 。

关键字：太阳黑子；威尔逊山；双流CNN；ResNet

# 0引言

太阳耀斑是太阳突然释放的磁场能量造成的，长期观测发现，大多数耀斑发生在黑子群的上空，且黑子群的磁场极性越复杂，发生大耀斑的几率越高。因此黑子群的磁类型可以作为预测太阳耀斑的重要依据。典型的黑子群分类方法可以分为基于图像学的边缘检测法、数学形态法和小波分析法，以及基于数据驱动的机器学习方法。近年来随着观测条件的进步，与太阳活动有关的数据增长迅速，基于机器学习方法的优势越来越显著[3]。

2008年Colak等[4采用McIntosh分类方案，提出了一种混合系统，该系统使用从SOHO /MDI磁图图像中提取的活动区域数据，对SOHO/MDI白光图像上的黑子群进行自动检测。从MDI白光图像中检测到黑子后，使用MDI磁图图像对它们进行分组/聚类。通过集成图像处理和神经网络，自动对检测到的黑子组分类。但系统存在分组错误和小型黑子漏检的缺陷。

2010年Mehmmood A．Abd等[5]，采用改良后的七类Zurich分类方案，使用sVM(SupportVectorMachine,支持向量机)来实现对太阳全日面白光图像上黑子群的自动分类。在数据预处理阶段，使用了边缘检测、噪声去除以及二值化来分割黑子群和日面，之后对黑子群的进行无监督分割，将属于同一组的黑子进行合并，然后对每个黑子组的属性提取，最后使用SVM来进行分类。该方法精度对图片质量和失真程度有所要求，且分割过程对结果输出的速率有较大影响。

2019年Yuanhui Fang等[6]，使用CNN(Convolutional Neural Network，卷积神经网络)对黑子群的磁类型进行分类，在数据预处理阶段图像被分为三类，白光图、磁图以及白光图和磁图的合成图像。采用CNN对三类图像进行分类，结果显示单独使用白光图的分类效果最佳。该方法作者认为磁图结构相对白光较为复杂，使用CNN不能很好地提取特征，是造成使用磁图分类不佳的主要原因之一。

双流CNN可以融合对象不同维度的特征，为分类任务提供更多的特征信息。在动作识别领域，双流CNN一个分支用于提取RGB图的空间信息，另一个分支用于提取光流图的时间信息，融合之后进行动作识别。采用该方法识别打斗行为，平均识别率可达到 $8 9 . 3 \%$ ，高于单一分支情况[]。

MountWilson方案判断黑子群磁类型需用到不同维度的特征信息，首先通过白光图观察黑子群结构，然后查看对应磁图的磁极分布，最后将二者结合起来确定黑子群的磁类型。鉴于MountWilson方案的特点，本文将双流CNN用于对黑子群磁类型分类，一个分支用于提取白光图特征，另一个分支用于提取磁图特征，不同类型的特征在全连接层前进行融合。分类结果显示，双流CNN对黑子群磁类型的分类准确率高于用CNN对单一白光图或磁图进行的分类。本文内容安排如下：第1节介绍数据集与预处理；第2节介绍实验方案；第3节是实验

结果与分析；第4节是本文结论。

# 1 数据集与预处理

本文使用的数据集为SOLAR-STORM1[8]，它由空间环境人工智能预警创新工坊整理提供，可在天池实验室(https://tianchi.aliyun.com/dataset/)公开下载。该数据集基于Mount Wilson黑子群磁类型分类方案，分为白光图和磁图两部分，由于同一时刻的同一观测对象有白光图和磁图两类图像，所以二者是一一对应的，每个白光图部分或磁图部分含Alpha、Beta、Betax三个类型。

我们将Alpha、Beta、Betax中6205号、6207号、6206号之后的划归至测试集，其余作训练集使用，具体分布情况如表1所示。

表1数据集分布情况  
Tab.1 Data set distribution   

<html><body><table><tr><td></td><td>Alpha</td><td>Beta</td><td>Betax</td><td>Sum</td></tr><tr><td>Trainset</td><td>4709</td><td>7353</td><td>2407</td><td>14469</td></tr><tr><td>Testset</td><td>567</td><td>496</td><td>109</td><td>1172</td></tr><tr><td>Sum</td><td>5276</td><td>7849</td><td>2516</td><td>15641</td></tr></table></body></html>

原始数据集是FIT格式，其中白光图像素值范围为[200,74000],磁图像素值范围为[-5000,5000],我们将白光图值域压缩至[0,255]转为JPG格式，将磁图[-800,800]范围内的压缩至[0,255]以加强其特征。图1分别为Alpha、Beta、Betax的白光图和磁图。可以看出Alpha类为单极黑子群，Beta类极性相反双极黑子群，Betax类为复杂的多极黑子群。

![](images/d1c94b1fdc4518e948769dbb2dae2ab3d3d349b972adef5c9f654c3983eb58fb.jpg)  
图1Alpha、Beta、Betax 的白光图和磁图  
Fig.1 Continuum and magnetogram of Alpha,Beta and Betax

由于太阳黑子拍摄时间间隔为96分钟，短时间内黑子群演化并不明显，导致一定时间段内，观测对象的照片之间相似度很高。如图2，Beta类中26号对象在一天内不同时刻所拍摄的白光图和磁图几乎看不出变化。

为避免数据切分时训练集和验证集有相似图像造成准确率虚高，我们将数据按对象进行子类归集，之后按对象划分训练集和验证集并以十折交叉验证方式训练和测试。

![](images/b4f614f6d23039d9a6a1e5bd3e9407e2f77e067e06cfb0885a48cf450b04b480.jpg)  
图226号对象不同时刻的白光图与磁图

# 2 实验方案

# 2.1双流CNN分类方法

首先建立两条不同的CNN 网络，以 $\mathrm { R e s N e t } 5 0 ^ { \mathrm { [ 9 } }$ 错误!未找到引用源。(ResidualNetwork,残差网络)为Backbone，接着将白光图和磁图分别输入，由于图像进入的是不同的分支，所以CNN的权重不存在共享。两类图经过网络提取特征后形成特征向量，然后将特征向量进行拼接，之后进入全连接层，以Softmax进行分类，采用的网络结构如图3所示。

![](images/d4471d5aebd1aeb42ae8ca3cfa3569833c55f62202f4ae7906955b078b72f11d.jpg)  
Fig.2 Continuum and magnetogram of object 26 at different times   
图3采用的双流CNN结构图  
Fig.3 Structure diagram of dual-stream CNN

# 2.1.1 ResNet50

ResNet是KaimingHe 等为解决深层网络的退化现象提出的，其基本思想是在ResNet单元内设置跳跃链接，这样原始信息能够直接传递至后面的层。常见的ResNet网络层数有18,34,50 和101等。ResNet基本结构如图4(a)，其中 $x$ 为输入， $\operatorname { f } ( x )$ 为映射函数， $\mathrm { H } ( x )$ 为输出。

![](images/0dd0bfadf79c42af313e93c060f5c093c99c9fcf3ec5b552bd81dd05d3b41599.jpg)  
图4ResNet模块和CNN模块   
Fig.4ResNet module and CNN module

由ResNet模块可知 $\mathrm { f } ( x ) { = } \mathrm { H } ( x ) { - } x .$ 即ResNet模块学习的是输入和输出之间的差值。当网络到达某层为最优状态时，CNN需要进一步更新权重，而ResNet模块只需做恒等映射，继而避免了网络退化的发生。

# 2.1.2 防止过拟合的措施

为避免模型过拟合，实验中进行了数据增强，添加了Dropout、L2 和 Label smoothing三种正则化方法。

数据增强使用旋转、水平镜像、放缩来丰富数据分布，以提高模型泛化能力。

Dropout值设为0.5，即随机设定特征向量中一半为0，其本质是在该层引入噪声，以避免因为某些不显著的偶然性获得正确的结果。

L2 正则化可强制使权重参数取较小的值以防止过拟合，实现方法是在损失函数中添加权重系数的平方。使用的交叉熵损失函数公式如下：

$$
\mathrm { { L o s s = - \sum _ { i = 0 } ^ { n - 1 } q _ { i } l o g ( p _ { i } ) } }
$$

其中 $n$ 为样本总量， $i$ 为类别序数， $q$ 为样本实际标签， $p$ 为样本预测标签。

添加L2正则化后：

$$
\mathrm { L o s s } = - \sum _ { \mathrm { i = 0 } } ^ { \mathrm { n - 1 } } \mathrm { q } _ { \mathrm { i } } \mathrm { l o g } ( \mathrm { p } _ { i } ) + \frac { \lambda } { 2 n } \sum _ { w } w ^ { 2 }
$$

其中 $\lambda$ 为正则化参数，设为0.001， $w$ 为权重。

由公式(2)可知，如果权重值变大，Loss 值就会增大，所以为了降低Loss 值模型会逐步调低 $w$ 的值，这样即使输入值差异很大，模型的预测变化也不会很大。

Label smoothing 是对公式(1)的 $q$ 做调整，当样本标签转换为One-hot形式后，真值为1,其他为0，而由Softmax计算得来的 $p$ 在训练过程中需逐步逼近 $\boldsymbol { q }$ ，Softmax计算公式如下：

$$
S _ { \mathrm { i } } = { \frac { \mathrm { e ^ { i } } } { \sum _ { \mathrm { j } } \mathrm { e ^ { j } } } }
$$

其中 $i$ 为类别序数， $j$ 为类别总数。

通过公式(3)的计算，模型的输出变为了概率分布，再结合公式(2)可知，由于样本标签非0即1的表示，会使得分类正确时的Loss值趋近0，分类错误时的Loss值趋近- $\scriptstyle . \infty$ ，而这种激励惩罚机制过于极端，只适用于数据集能够覆盖所有可能性或数据集标注完全正确的情况，为缓和这种极端的激励惩罚机制，对标签的One-hot形式做以下改动：

$$
\mathbf { q } _ { \mathrm { i } } = { \left\{ \begin{array} { l l } { 1 - \varepsilon } & { { \mathrm { ~ k = y ~ } } } \\ { \varepsilon / ( n - 1 ) } & { { \mathrm { ~ k \neq y ~ } } } \end{array} \right. }
$$

其中 $\varepsilon$ 为设置的超参数，设为0.1， $k$ 为类别标签， $y$ 为样本真实标签。

由公式(4)可知，由于拉近了类间距离，减少类内距离，使得模型的泛化能力得以进一步提高。

# 2.2实验对比组方法

为形成实验对比，另设ResNet50 和文献[6]使用的CNN 模型，所有模型除网络结构外数据划分、超参数、防过拟合措施等均采用相同配置，采用的CNN模型结构如图5所示。该结构具有三个卷积层，卷积核尺寸均为（5.5），每一层的卷积核数量均为上一层的两倍，以达到提取图像特征的目的，特征提取后形成特征向量输入全连接层，随后以Softmax 分类器进行分类。输入层方面，将白光图、磁图、白光图和磁图构成的双通道图片分别输入到网络中，进行训练，最终获得7组数据。

![](images/0b92f5574df370477308140e0df2c39a10d77caa210817b0ccf176c0f56ce8dd.jpg)  
图5对比组采用的CNN结构图  
Fig.5 CNN structure diagram used by the comparison group

# 2.3模型评价指标

本实验以各模型的准确率（Accuracy）、精确率（Precision）、召回率（Recall）、F1-score（F1分数）、混淆矩阵来评估模型的分类性能。以Alpha为例上述指标计算公式如下：

$$
{ \mathrm { A c c u r a c y } } = { \frac { \mathrm { T A } + \mathrm { T B } + \mathrm { T X } } { \mathrm { T A } + \mathrm { T B } + \mathrm { T X } + \mathrm { A B } + \mathrm { A X } + \mathrm { B A } + \mathrm { B X } + \mathrm { X A } + \mathrm { X B } } }
$$

$$
\mathrm { P r e c i s i o n } = { \frac { \mathrm { T A } } { \mathrm { T A } + \mathrm { B A } + \mathrm { X A } } }
$$

$$
{ \mathrm { R e c a l l } } = { \frac { \mathrm { T A } } { \mathrm { T A } + { \mathrm { A } } { \mathrm { B } } + { \mathrm { A } } { \mathrm { X } } } }
$$

$$
{ \mathrm { F 1 - s c o r e } } = { \frac { \angle \mathbf { 1 } \mathbf { \uparrow } \mathbf { A } } { 2 \mathbf { T A } + \mathbf { A B } + \mathbf { A X } + \mathbf { B A } + \mathbf { B X } } }
$$

三类别的混淆矩阵如表2所示，其中TA是正确将Alpha类识别为Alpha类，TB 是正确将 Beta 类识别为Beta 类，TX是正确将 Betax 类识别为Betax类，AB是错误将Alpha类识别为Beta 类，AX是错误将 Alpha类识别为Betax 类，BA是错误将 Beta 类识别为Alpha类，BX是错误将 Beta类识别为Betax 类，XA是错误将Betax 类识别为Alpha类，XB 是错误将Betax类识别为Beta类。

表2三种类别的混淆矩阵Tab.2 Confusion matrix of three classes  

<html><body><table><tr><td></td><td>预测为Alpha</td><td>预测为Beta</td><td>预测为Betax</td></tr><tr><td>实际为Alpha</td><td>TA</td><td>AB</td><td>AX</td></tr><tr><td>实际为Beta</td><td>BA</td><td>TB</td><td>BX</td></tr><tr><td>实际为Betax</td><td>XA</td><td>XB</td><td>TX</td></tr></table></body></html>

# 3 实验结果与分析

由于实验采用十折交叉验证，实验中用 StratifiedKFold对训练集切分为10份，每次选1份作验证集，其余作训练集，最后统计模型在测试集上的分类情况。评价指标取加权均值，混淆矩阵按模型对应的混淆矩阵的和来计算。实验数据如表3所示：

表3各模型实验结果  
Tab.3Experimental results of each model   

<html><body><table><tr><td>Model 模型</td><td>Data 数据源</td><td>Average accuracy 平均准确率</td><td>Weighted Precision 加权精确率</td><td>Weighted Recall 加权召回率</td><td>Weighted F1-score</td></tr><tr><td>CNN</td><td>白光图</td><td>75.00%</td><td>76.58%</td><td>75.00%</td><td>加权F1分数 75.28%</td></tr><tr><td>CNN</td><td>磁图</td><td>74.69%</td><td>76.96%</td><td>74.69%</td><td>74.68%</td></tr><tr><td>CNN</td><td>白光图+磁图的 双通道</td><td>75.38%</td><td>76.53%</td><td>74.82%</td><td>75.07%</td></tr><tr><td>ResNet50</td><td>白光图</td><td>81.48%</td><td>82.96%</td><td>81.48%</td><td>81.69%</td></tr><tr><td>ResNet50</td><td>磁图</td><td>83.98%</td><td>84.63%</td><td>83.98%</td><td>84.09%</td></tr><tr><td>ResNet50</td><td>白光图+磁图的 双通道</td><td>83.09%</td><td>83.89%</td><td>83.09%</td><td>83.04%</td></tr><tr><td>双流 ResNet50</td><td>白光图+磁图</td><td>84.93%</td><td>85.27%</td><td>84.93%</td><td>84.87%</td></tr></table></body></html>

从表3可以看出，双流ResNet50的各项指标都是最高,即使有映射寻优能力的ResNet50,在缺失部分数据的情况下也不及双流ResNet50，这表明在面对同一测试集的情况下，双流ResNet50有更好的分类能力。

由于本实验测试集类别不平衡，模型指标以加权F1-score为主要参考，其他指标为辅助参考，通过对比相同数据源、不同模型之间的实验结果可知ResNet50 的F1分数相比CNN有较大提高，当数据为白光图、磁图、双通道图时，加权F1-score 提高了 $6 . 4 1 \%$ 、 $9 . 4 1 \%$ 、$7 . 9 7 \%$ ，当数据为白光图、磁图、双通道图时提高了 $6 . 4 8 \%$ 、 $9 . 2 9 \%$ 、 $7 . 7 1 \%$ ，这表明ResNet50这种深层网络的特征提取能力比CNN这种浅层网络要强，更能够提取到有用的特征。

通过对比相同模型、不同数据源之间的实验结果可知当模型使用CNN时，使用白光图时F1分数最高、双通道图次之、磁图最低。当模型使用ResNet50时，使用磁图时F1分数最高、双通道图次之、白光图最低。在不同模型下白光图和磁图显现出不同的分类优势，可能的原因是CNN架构简单，深度较浅，ResNet50架构复杂，深度较深，而白光图结构简单、磁图结构复杂，所以当磁图进入CNN后，不能被CNN提取到有利于分类的特征，当白光图进入CNN后，所提取的特征相较于磁图的提取的特征对分类更有利。而ResNet50 的分类能力较CNN更强，所以当磁图进入ResNet50后，其复杂的结构得以提供更多有利于分类的信息，当白光图进入ResNet50后，由于其结构简单，提供给分类的信息相对于磁图较少。

由于ResNet50 分类较强，再比较ResNet50 和双流ResNet50 的实验结果，由结果可知，使用双通道图的模型的分类能力相比使用磁图模型有所下降，这说明白光图和磁图形成的双通道图输入进模型后，互相之间有影响，该影响对形成分类所需的特征向量有负面作用。最后以使用磁图的ResNet50为基线，对比双通道图的ResNet50和双流ResNet50的实验结果，可以发现两者都有白光图的加入，但使用双通道图的模型F1分数下降，双流ResNet50的F1分数上升，这说明双流ResNet50在数据的总和使用和数据特征提取方面相对其他模型更有优势。

据文献[6]结果可知,模型使用白光图、磁图、双通道图的F1分数分别为 $9 4 . 2 0 \% . 8 7 . 2 2 \%$ ，$8 8 . 6 1 \%$ ，结果均优于双流ResNet50，造成该情况的可能原因如下：1、数据质量有差异，文献[6]采用数据集是在太阳盘中心 $\pm 7 5$ 度的经度以内且背景噪声较小的黑子群图像，而SOLAR-STORM1数据集中存在部分临边的黑子群和噪声大的图像；2、数据集的切分方式不同，文献[6]采用随机切分方式，同一黑子群在短时间内演化不明显时，这可能导致训练集和测试集中存在相似度较高的图像。本文按照黑子群对象切分，同一黑子群的图像不会在训练集和测试集同时出现；3、训练方式不同，文献[6]对数据集做一次切分，本文采用十折交叉验证，计算平均值。

表4双流ResNet50的混淆矩阵  
Tab.4Confusionmatrix ofdual-streamresnet50   

<html><body><table><tr><td></td><td>预测为 Alpha</td><td>预测为 Beta</td><td>预测为Betax</td></tr><tr><td>实际为Alpha</td><td>5092(89.8%)</td><td>575(10.1%)</td><td>3(0.1%)</td></tr><tr><td>实际为 Beta</td><td>639(12.9%)</td><td>4007(80.8%)</td><td>314(6.3%)</td></tr><tr><td>实际为 Betax</td><td>24(2.2%)</td><td>211(19.4%)</td><td>855(78.4%)</td></tr></table></body></html>

从表4可以看出，Alpha 和 Betax 被误判为 Beta 的几率较高，Beta被误判为Alpha 的几率相比被误判为Betax的几率高出一倍。

以 Alpha类7169号对象为例，如图6，该对象在10月27日和29日显示为一个单极黑子群，此时模型分类正确，而在28日黑子群右上方，出现了另一个黑子，该黑子特征被模型提取后，致使整张图片分类为Beta。所以演化过程中短暂性出现的黑子可能是模型误判的原因之一。

以Beta类6242号对象为例，如图7。初期黑子群双极清晰，但在演化过程中右方黑子逐渐消散，而左方黑子依旧存在，所以当末期黑子群的图像进入模型后容易被判为Alpha,这种由于演化形成了模糊的类型特征可能是模型分类精度不佳的主要原因之一。

另以Betax类6975号对象为例，如图8。该对象末期逐渐向日面边缘靠近，由于投影效应和临边昏暗效应，导致了黑子群白光图特征模糊，以及磁场测量的精度下降。所以当黑子群接近日面边缘时，图片质量降低可能也是模型分类精度不佳的原因。

![](images/0032977e2c09d241b0740e660495c0fc5ecc13523d5c5f1a9a92606dd29af97b.jpg)

(a)10月27日磁图 (b)10月28日磁图 (c)10月29日磁图

![](images/4ba60037f5cf4686367c1d11c37f7a201a94b9e63a9b8953d0c78d14a158adf3.jpg)  
Fig.6 Continuum and magnetogram of object 7169 in October 2017   
图76242号对象初期和末期的白光图和磁图

Fig.7 Continuum and magnetogram of the early and late stages of object 6242

![](images/bf13000c3f74be1e7062fb7dde52b0a2e83a43f2d3cecebbefa8aeab8ee41d6b.jpg)  
图67169号对象于2017年10月份的白光图和磁图  
图86975号对象末期的白光图和磁图

Fig.8 Continuum and magnetogram of the late stages of object 6975

SOLAR-STORM1数据集为FITS格式，文件为7GB,体积较大，读取速度较慢，转为JPG格式后，文件为 $6 0 0 \mathbf { M }$ ，读取速度较快，并且黑子群的特征依旧得到了保留，所以在实验中采用转换为JPG格式的数据集。

# 4结论

观测条件的进步为太阳观测提供了海量数据。本文针对SOLAR-STORM1数据集的特点，采用双流CNN方法开展黑子群磁类型分类研究，并与其他方法进行了对比实验。实验结果表明，双流CNN对黑子群磁类型分类效果更好，与使用单通道的方法相比，双流CNN避免了仅使用一种图像造成的数据缺失，实现了数据的最大化利用，与使用双通道的方法相比双流CNN避免了图像特征提取过程中，白光图和磁图的互相影响。在相同数据源情况下，深层模型的特征提取能力比浅层模型要强；在算法特征提取能力强的情况下，仅使用磁图比仅使用白光图的分类精度要高，而使用双通道图像的精度介于两者之间。

尽管双流CNN表现出了较好的分类性能，但由于部分对象在演化过程中特征逐渐消散和部分图像有临边昏暗现象，使得双流CNN 出现了误判情况。接下来的工作将针对这两方面的原因对双流CNN做进一步的优化。

# A magnetic classification method of sunspot group

# based on dual-stream CNN

Yang Wugu, Tian Weixin \*, Zeng Shuguang，Huang Yao (School of computer and information, Three Gorges University, Yichang, Hubei 443000)

Absrtact: Most solar flares occur over sunspot groups with complex magnetic polarities, so the magnetic type of sunspot groups can be used as an important basis for predicting solar flares. A sunspot group magnetic classfication method, dual-stream CNN is proposed for sunspot classification with both continuum and magnetogram.The method simultaneously extracts the continuum and the magnetogram features through two network branches, then fuses the two types of features in the fully connected layer,and finally uses them for training and classification. Experimental results show that the method can avoid the information loss of single-channel network model and the interaction of continuum and magnetogram in the dual-channel image, and the weighted F1 score was $8 4 . 8 7 \%$ , and the average accuracy was $8 4 . 9 3 \%$ ：

Keywords: sunspot; Mount Wilson; dual-stream CNN; ResNet

# 参考文献：

[1]梁波,林语琦,戴伟,冯松,杨云飞.基于多变量LSTM 网络的太阳黑子活动预测分析[J].天文研究与技术,2020,17(03):322-333. LiangBoLinYuq,Dai Wei,etalPredictioandAnalysisofSunspotActivityBasedonMultivariableLSTNetwork[J]Astrooical Research& Technology,2020,17(03):322-333.   
[2]朱健,杨云飞,苏江涛,刘海燕,李小洁,梁波,冯松.基于深度学习的太阳活动区检测与跟踪方法研究[J].天文研究与技 术,2020,17(02):191-200.   
ZhuJian,YangYunfeiSuJiangtao,etalADetectionandTrackingMthodforActiveRegions BasedonDeepLearing[JAstroomical Research & Technology,2020,17(02):191-200.   
[3]刘辉,季凯帆,金振宇.机器学习在太阳物理中的应用[J].中国科学:物理学力学 天文学,2019,49(10):105-117.   
Liu Hui,JiKaifan,inZeu.apationofmacheleainginolarpsics(ininese).SciSi-sechtron19,49: 109601   
[4]T.ColakandR.Qahwaji,"Automatedmcintoshbasedclasificationofsusot groupsusingDimages”SolarPhysics,ol.48, no.2,pp.277-296,2008.   
[5]M.A.Abd,S.F.Majed,andV.Zharkova,“Automatedclasificationofsunspotgroupswith supportvectormachines,”in Proceedings of the Technological Developments in Networking,Education and Automation,pp.321-325,2010.   
[6]FangY,CuiY,AoX.DepLearingfor AutomaticRecognitionof MagneticType inSunspot Groups[J].AdvancesinAstronomy 2019,2019(123):1-10.   
[7]高阳.基于双流卷积神经网络的监控视频中打斗行为识别研究[D].西安理工大学,2018. GaoYang.FightingBehaviorDetectionInSurveilancevideoByTwo-Stream ConvolutionalNetworks[D].Xi'anUniversityof technology, 2018   
[8]Thedatasetofsunspot group magnetictypeprovidedbySpaceEnvironment WarningandAITechnologyInterdisciplinaryIovation Working Group[FANG Y,et al.,2019].   
[9]He K,ZhangX,RenS,etal.DepResidualLearingforIageRecognition[C/IEEEConferenceonComputerVisio&ater Recognition. IEEE Computer Society,2016.