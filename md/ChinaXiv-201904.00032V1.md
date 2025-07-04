# 基于堆稀疏自编码的二叉树集成入侵检测方法

柳毅1，阴梓然1，洪洲²

(1．广东工业大学 计算机学院，广州 510006;2．广州城市职业学院 科研处，广州 510405)

摘要：至今已经有许多不同的机器学习方法被提出来，而传统的机器学习方法无法有效解决大规模入侵数据的分类问题，为了解决大规模入侵数据的分类问题，提出的堆稀疏自编码的lightGBM（light gridient boosting model）二叉树算法。首先将类别标签分为五类，构造成二叉树结构，然后通过上采样方法解决数据分布的不平衡问题，以上处理可以将大规模的数据分解开来以便之后分开训练，再采用稀疏自编码器网络进行特征降维，采用该种降维方法可以保证在原始数据中抽取出更深层特征的基础上节省降维时间。最后通过 lightGBM集成算法进行分类，而采用lightGBM模型相比其他模型可以在保证分类性能的情况下节省训练时间。实验利用NSL-KDD数据集测量了所提方法的准确率（accuracy）、精确率（precision）、召回率（recall）以及综合评价指标 $F _ { 1 }$ 在五类分类上平均分别达到了$8 7 . 4 2 \%$ ， $9 8 . 2 0 \%$ ， $91 . 3 1 \%$ ，优于对比算法，且明显节省了运算时间。

关键词：入侵检测；堆稀疏自编码网络；lightGBM算法；不平衡数据；NSL-KDD数据集 中图分类号：TP393.08 doi: 10.19734/j.issn.1001-3695.2018.11.0827

Binary tree ensemble intrusion detection method based on stacked sparse autoencoder

Liu $\mathrm { Y i ^ { 1 } }$ , Yin Ziranl,Hong Zhou² (1.SchoolofComputer Science&Technology,Guangdong UniversityofTechnology,Guangzhou510o06,China;2.Ofce ofAcademic Research,Guangzhou City Polytechnic,Guangzhou 510405,China)

Abstract:Sofar,manydifferent machine learning methods have ben proposed,and traditional machine learning methods cannoteffectivelysolve theclasificationproblemof large-scaleintrusiondata.Inordertosolve theproblemof classification oflarge-scale intrusion dataThis paper proposed lightGBM binarytreealgorithm basedon stacked sparse autoencoder.Firstly,thecategory labels were divided into fivecategoriesandconstructed into binarytree structures,then the imbalance of data distribution was solved by the upper sampling method,the above processing could separate the large-scaledata,sothattheycould be trained separately,and then,the sparse autoencoder network was used toreduce the feature dimension.Using this method could ensure thattimeof dimensionreduction could be savedon the basisof extracting deper features from the original data.Finall,the lightGBMensemblealgorithm wasused toclassify.And compared to other models,using the lightGBM model could save training time while ensuring clasification performance. The NSL-KDD dataset was used to measure the accuracy,accuracy,recal,and comprehensive evaluation index F1of the proposed method,which reached an average of $8 7 . 4 2 \ \%$ ， $9 8 . 2 0 ~ \%$ ，and $91 . 3 1 \ \%$ in five classification,respectively. It is superior to the comparison algorithm and obviously saves the calculation time.

Keywords:intrusiondetection；stacked sparse AutoEncoder network；lightgbmalgorithm;imbalanced data;nsl-kdc dataset.

# 0 引言

入侵检测是信息安全的重要组成部分，只有正确检测入侵，才能实现后续反应和恢复。入侵检测分为误用检测和异常检测,误用检测通过建模并利用攻击的鲜明特征来检测入侵.误用检测对于已知的入侵具有较高的检测率，但无法检测到新的入侵。异常检测是基于正常行为的模型，任何偏离所构造的正常行为模型的行为都被认为是异常[1]。由于很难对所有正常行为进行精确建模，异常检测很容易将正常行为错误地归类为攻击。

随着移动互联网和物联网的不断发展，网络攻击日益智能化和复杂化，使得恶意入侵的检测更加困难。为了应对这些挑战，机器学习方法在入侵检测中得到了广泛的应用，包括决策树、朴素贝叶斯、随机森林、K-均值聚类算法、支持向量机。传统的浅层结构的机器学习方法大多表达复杂函数的能力有限，泛化能力较弱，因此不能很好地处理复杂的分类问题。

近年来，深度学习已成为机器学习中的一个热门话题，深度学习方法在人脸识别、语音识别、图像识别等领域得到了广泛的应用。同时，在入侵检测中也采用了深度学习方法。文献[2]提出了基于PCA降维KNN作为分类器的入侵检测方法，实验表明，在应对多分类问题时，对于少数类的检测率明显不高，由此可以看出在应对大规模数据时，对于少数类的处理尤为重要。文献[3]提出了一个半监督约束玻尔兹曼机器（DRBM）模型，它可以检测未知的入侵事件，他们在网络异常检测中的准确率达到了 $96 \%$ ，但应对大规模数据时，噪声对其模型的影响较大，因此此方法缺乏去噪策略。文献[4]提出了DBN和 SVM的组合，DBN用于降低输入数据集的维度，SVM用于分类。这一组合取得了良好的效果，然而，他们没有考虑类别不平衡问题，这对于大规模且种类繁多的入侵数据的侦测性能是致命的。文献[5]表明，堆去噪自编码网络能够很好地区分恶意和非恶意软件，作者构建了三个隐藏的深层神经网络，这个模型只使用了在SDN环境中容易获得的六个基本特征，对于特征的考虑过少，容易丢失信息，不适用于入侵检测在数据规模大而繁杂的情况下使用。文献[6]使用一个隐藏层的RBM来进行无监督的特征降维。权重被传递给另一个RBM产生一个DBN。预先训练的权重被传递到一个精细的调节层，由一个逻辑回归分类器（用10个迭代来训练）与softmax层组成。使用KDDCUP99组数据对所提出的解决方案进行了评估。作者声称检测率 $9 7 . 9 0 \%$ ，假阴性率为 $2 . 4 7 \%$ 。这比类似论文作者声称的结果有所改进，其权重优化使用的随机梯度下降法，在优化时间上会随着数据的规模增大而增加，因此权重优化算法需进一步更新以应对较大的数据规模。文献[7]提出了一种基于深度学习的方法来建立一个有效而灵活的NIDS。他们的方法被称为自学（STL)，它结合了稀疏的自动编码器和 softmax 回归。他们已经实现了他们的解决方案，并根据基准NSL-KDD数据集对其进行了评估。在2类和5类分类中，分类精度都有一定的提高。然而同样在其权重优化算法上可进一步改善。文献[8]提出堆稀疏自编码网络(SSAE)和 XGBoost 集成算法的组合，SSAE用来降维输入数据，XGBoost集成算法用来分类。实验结果表示他们在5类分类中的平均F1值达到了 $9 1 . 9 7 \%$ 然而他们采用的5层稀疏自编码网络的降维效果和在训练时间上可以进一步改善以应对大规模入侵数据。基于以上工作存在的一些欠缺，有必要提出进一步的方法来解决入侵检测在面对大规模数据时的问题，旨在进一步优化入侵检测算法的运算时间，和弥补类别数据不平衡的缺陷，从而改善分类性能。

本文使用了NSL-KDD 数据集9]，并采用Adam 函数作为优化器的稀疏自编码网络进行降维，通过大量的实验，选择了适当数量的前训练迭代数和隐藏层。最后通过lightGBM算法(lgb)[0构造的二叉树结构方法进行分类。贡献在于：采用Adam函数作为训练优化器的3层堆稀疏自编码来进行降维，不仅提高了少数类的分类精度，而且减少了网络训练的时间，与此同时采用lightGBM算法作为分类器进一步减少了训练时间和提高了分类效果。之后采用二叉树的结构并通过1：1比例的上采样方法解决了大部分算法对于少数类侦测率低的缺陷。

# 1 堆稀疏自编码网络

# 1.1单层稀疏自编码（SAE）

如图1所示，单层的SAE具有输入层、隐藏层和输出层，并且能够给出输入向量的压缩表示，因为隐藏节点的数目小于输入向量的长度。训练过程保证输出向量足够接近输入向量 $X = \{ x _ { 1 } , x _ { 2 } , . . . , x _ { n } \} , x _ { i } \in R ^ { n }$ ， $\mathbb { R } ^ { \mathrm { n } }$ 表示输入向量的集合，如此隐藏节点能够表征数据集的有效特征表示。给定一个输入向量X，所有隐藏节点 $H _ { j } , j = 1 , 2 , . . . s$ 的激励函数计算如下：

$$
a ( x ) = f ( W ( 1 ) x + b _ { x } )
$$

其中： $f ( z ) = 1 / \left( 1 + \exp ( - z ) \right)$ 是 sigmoid 激励函数， $W ( 1 )$ 是关

联输入层和隐藏层的权重矩阵， $b _ { x }$ 是输入层的偏置向量， $\mathbf { a } ( \mathbf { x } )$ 是包含有s个隐藏节点的隐层的激励函数。输出向量 $\hat { x }$ ，其计算如下：

$$
\hat { x } = f ( W ( 1 ) ^ { T } a ( x ) + b _ { h } )
$$

其中： $W ( 1 ) ^ { \mathrm { T } }$ 是关联隐藏层和输出层的权重矩阵， $ { \mathbf { b } } _ { \mathrm { h } } ( 1 )$ 是隐藏层的偏置向量。成本函数 $J _ { _ { S A E } }$ 包括所有输入数据和输出数据之间的误差，权重衰减项和稀疏惩罚项。具体来说，成本函数的定义如下：

$$
J _ { _ { S A E } } = J _ { _ { A E } } + \beta \sum _ { j = 1 } ^ { n _ { h } } K L ( \rho | | \tilde { \rho } _ { j } )
$$

其中： $J _ { _ { A E } }$ 是不考虑稀疏性时的成本函数，第二项是稀疏惩罚项。具体地说， $\beta$ 是控制稀疏惩罚项的权重的系数，$K L ( \rho | | \tilde { \rho } _ { j } )$ 是 $\tilde { \rho } _ { j }$ （隐藏节点 $\mathrm { H _ { j } }$ 相对于所有输入数据的平均激励值)，和 $\rho$ （设定的稀疏参数）之间的Kullback-Leibler 散度，其中 $\mathrm { n } _ { \mathrm { k } }$ 为编号为 $\mathbf { k }$ 的隐藏层的节点数，KL散度其计算为 $\rho \log ( \rho / \tilde { \rho } _ { j } ) + ( 1 - \rho ) \log ( ( 1 - \rho ) / ( 1 - \tilde { \rho } _ { j } ) )$ 。值得注意的是隐藏节点的大多数激励结果都限制在接近0的值上。第一项 $J _ { _ { A E } }$ 计算如下：

$$
{ { J } _ { _ { A E } } } = \frac { 1 } { 2 n } \sum _ { i = 1 } ^ { n } { \left\| { { { \hat { x } } _ { i } } - x _ { i } } \right\| ^ { 2 } } + \frac { \lambda } { 2 } \sum _ { l = 1 } ^ { { { n } _ { l } } } \sum _ { i = 1 } ^ { { { s } _ { l } } } \sum _ { j = 1 } ^ { { { s } _ { l + 1 } } } ( { { W } _ { i j } } ( l ) ) ^ { 2 }
$$

其中，第一项测量输入和输出数据之间的总误差，其中 $\mathfrak { n }$ 是输入数据的维数；第二项是权重衰减项，它控制权重的数量，以防止自编码器过拟合。其中 $\lambda$ 是规范化参数， $n _ { l }$ 是层数，1是当前层的编号， $s _ { l }$ 和 $s _ { l + 1 }$ 是相邻两个层之间各自隐藏层的节点数量， $W _ { i j } ( l )$ 是关联相邻两层之间的权重矩阵。

此处优化方法主要通过利用Adam算法[11优化成本函数$J _ { _ { S A E } }$ 的权重和偏置值来完成SAE 的训练过程。Adam 算法的基本原理是将Momentum 和 RMSprop 结合在一起。经过一定次数的迭代后， $J _ { s A E }$ 会被减少到相当小的值，因此实现了SAE的自动特征提取。

使用Adam算法更新W和各层偏置值b，其具体步骤是首先计算momentum指数加权平均数，公式如下：

$$
V _ { \hat { \sigma } w } = \beta _ { 1 } V _ { \hat { \sigma } w } + ( 1 - \beta _ { 1 } ) \hat { \sigma } w
$$

$$
V _ { \hat { c } b } = \beta _ { 1 } V _ { \hat { c } b } + ( 1 - \beta _ { 1 } ) \hat { c } b
$$

使用RMSprop 算法进行更新，公式如下：

$$
S _ { \hat { \sigma } w } = \beta _ { 2 } S _ { \hat { \sigma } w } + ( 1 - \beta _ { 2 } ) { ( \hat { \sigma } w ) } ^ { 2 }
$$

$$
S _ { \hat { c } b } = \beta _ { 2 } S _ { \hat { c } b } + ( 1 - \beta _ { 2 } ) ( \hat { c } b ) ^ { 2 }
$$

此时将式（5）～（8）皆考虑修正偏差，公式如下：

$$
V _ { \hat { \sigma } w } ^ { c } = \frac { V _ { \hat { \sigma } w } } { ( 1 - \beta _ { 1 } ^ { t } ) }
$$

$$
S _ { \hat { \sigma } w } ^ { c } = \frac { S _ { \hat { \sigma } w } } { ( 1 - \beta _ { 2 } ^ { t } ) }
$$

$$
V _ { \hat { o } b } ^ { c } = \frac { V _ { \hat { o } b } } { ( 1 - \beta _ { 1 } ^ { t } ) }
$$

$$
S _ { \hat { o } b } ^ { c } = \frac { S _ { \hat { o } b } } { ( 1 - \beta _ { 2 } ^ { t } ) }
$$

最终参数的更新函数如下：

$$
W _ { i j } ( l ) = W _ { i j } ( l ) - \alpha \frac { V _ { \widehat { o w } } ^ { c } } { \sqrt { S _ { \widehat { o w } } ^ { c } + \varepsilon } }
$$

$$
b _ { i } ( l ) = b _ { i } ( l ) - \alpha \frac { V _ { \widehat { c b } } ^ { c } } { \sqrt { S _ { \widehat { c b } } ^ { c } + \varepsilon } }
$$

其中： $\alpha$ 为学习率， $\mathrm { \Delta V }$ 表示移动均值，S表示平方梯度， $\beta _ { \mathfrak { l } }$ 、$\beta _ { 2 }$ 是指数衰减率， $\varepsilon$ 是设定的步长，t表示某个时刻，而 $\beta _ { 1 } ^ { t }$ 和$\beta _ { 2 } ^ { t }$ 表示在t时刻的相应值。

![](images/72a0fa96866f97ed81e78148d45b5673efb7071cc7eeded93c9a4a6f6a4dee41.jpg)  
图1稀疏自编码结构Fig.1Architecture of SAE

# 1.2堆稀疏自编码 (SSAE)

顾名思义，SSAE是一种分层编码结构，单层SAE被堆积起来。每个隐藏层都希望从上一层学习到更抽象的特征表示[12]。SSAE中每层的训练过程与SAE的训练过程是相同的，即最大限度地降低成本函数，并在每次获得一层最优权值和偏置值。在所有的层经过适当的训练后，SSAE能够从训练数据集的输入数据中学习到更复杂和抽象的特征表示。

图2是堆稀疏自编码的训练结构图，因堆稀疏自编码的构建方式为先单独训练各个SAE，每一层的输入皆是其上一层的隐层，最后有序的将各级隐层连接起来构建成整体的SSAE。第一层由 $\textbf { \em x }$ 、h2、X组成再使用式(4)来无监督的学习特征表示，之后使用式(13)(14)得到权重和偏置W1、b1，第二层由 hi，h2， $\mathrm { H } _ { 2 }$ 组成，由训练过层与第一层相同并得到W2、b2，重复以上步骤最终得到整个网络的参数。

![](images/1d16a4face481b4e29552e22b77d265052bb25de0932321a970e803f87a0b5e5.jpg)  
图2堆稀疏自编码的训练结构图 Fig.2Training architecture of SSAE

# 2 基于堆稀疏自编码的二叉树集成算法

# 2.1数据处理流程

如图3所示，首先导入NSL-KDD数据集；其次，将数据作为神经网络的输入，因此需要对数据进行预处理。对于连续特征，需要规范化来平衡每一维特征的影响，而对于类别特征则需要独热编码。然后，标准化数据被用作SSAE-lightGBM二叉树的输入。最后，利用该模型对实验数据进行了预测，并对实验结果进行了对比分析。

![](images/ed63d329bd19ceb95dd1a5c34f192caab17dbf46b4c9e20794bef333790983f9.jpg)  
图3数据处理流程  
Fig.3Process of data processing

# 2.2堆稀疏自编码的lightGBM二叉树结构算法(SSAE-Igb-BT)框架

在入侵检测中，数据类别的不平衡问题频繁发生，造成了对数据量少的类别预测性能不佳的效果。解决类别数据量不平衡问题的方法一般包括上采样、下采样、代价敏感学习算法。通过参考决策树的分类过程和对入侵数据集分布的分析，引入了二叉树来解决入侵检测问题。通过使用二叉树，将多重分类简化为二元分类，使原来的多分类中类别数据的失衡问题变得相对平衡，减少了接下来集成方法计算的次数。

二分类可能还存在数据不平衡问题。在数据层面，过采样和欠采样是最具代表性的方法。过采样法为数据量少的类别创造合成的样本，并将其添加到训练集中，这将需要相当长的时间来进行训练。通过减少数据量多的类别样本的数量，欠采样方法通过平衡不同类别的比例，但这可能会丢失一些重要的信息。基于以上分析，提出了一种将EUS[13]和SMOTE[14]混合的方法EUS-SMOTE。EUS-SMOTE方法先使用EUS方法将多数类与存在多个类别的少数类的样本集分开，然后使用SMOTE方法对少数类进行采样，最后将多数类样本与过采样后的样本结合作为训练集，之后再重复将存在多个类别的少数类采用相同的EUS-SMOTE方法。关于不平衡类别数据的过采样比例使用1：1进行数据的过采样。最后在每层分开的数据集上使用SSAE-lightGBM集成算法进行训练并进行分类，其算法结构框架如图4所示。

![](images/213dfbb9d2aaa716e5dc02b16d7ab90e59261de816bf445ee91df8438c9d595d.jpg)  
图4算法框架

SSAE-lightGBM集成算法的训练过程如图5所示，图中(a)\~(d)训练的最终分类器依次对应图4中A、B、C、D四个分类器。图5(a)中，首先将NSL-KDD训练集分为两大类，分别为Nomal类以及(Dos，Probe，U2R，R2L)类，其标签分别标记为0、1，之后使用EUS-SMOTE处理0、1两类的类别平衡问题，之后利用SSAE抽取数据的深层特征T，最后将T放入lightGBM模型训练，训练过程使用bagging 投票式的5折交叉验证法融合预测结果，并最终得到分类器A。同样通过以上相同步骤得到分类器B、C、D。

![](images/aa6d48f65b1050185a71ca6909981e3ed96ae3857424d8bf624abcafe71a4d3f.jpg)  
Fig.4Structure of algorithm   
图5各分类器的训练流程  
Fig.5Training process of various classifier

图4所示为预测阶段，入侵数据首先进入第一层分类器A，通过SSAE-lightGBM集成模型后将会被分为0类或1类，若被判为0类则输出分类结果，并转换为真实的标签，若被分为1类则会将原始的侵入数据输入到第二层分类器B处分类，之后重复以上操作直到结束。

图6是使用SSAE-lightGBM模型预测入侵数据时的详细过程。其前半段是由3层训练好的隐层组成的编码器（训练过程如图2所示)，当数据依次通过一\~三层时，原始特征维数将会由下一层的神经元数所确定，直至到达最后一层，编码器将从高维特征中自动抽取出有意义的特征。之后将特征作为lightGBM分类器的输入从而得到预测结果。关于图6前半部分的编码器一共有4个，分别是在图5训练过程中产生，此4个编码器分别是从不同是数据集中无监督学习产生。

![](images/d690c6ac18542c9c19d0b5d5106eecb48758685bb69c6f6916cd418443828845.jpg)  
图6模型预测过程  
Fig.6Predicting process of model

# 3 实验与结果

为了证明所提算法的有效性，本文使用NSL-KDD公用数据集将所提出的SSAE-lightGBM二叉树结构算法与SSAE-XGBoost二叉树结构算法、PCA-XGBoost-二叉树结构算法的分类效果进行比较。以上几种方法在Intel(R）CoreTMi5-3210M CPU $\textcircled { a } ~ 2 . 5 \mathrm { { H z } }$ 处理器、4GB内存、Windows764位操作系统和Pycharm2017的环境中运行。

# 3.1数据及描述

对所有的NSL-KDD 数据集进行了实验。NSL-KDD 数据集由KDDcup99数据集生成。它解决了KDDcup99数据集中的数据冗余问题，更具实用性。NSL-KDD数据集包含125973训练样本和22544测试样本，它包括四类攻击：拒绝服务攻击（DoS)，远程到本地攻击（R2L)，用户根目录攻击（U2R）和攻击者试图获取有关目标主机信息的嗅探攻击（Probe）。图7显示了训练数据和测试数据的分布情况，数据在不同类别中的分布是不平衡的。DoS类别的数目比U2R类别的数目多得多。

NSL-KDD 数据集包含41个特性和1个类标签。这 41个特征包含38个连续特征和3个类别特征。

# 3.2评估方法

采用精确度、召回率和F1值计量方法。用这些方法来比较不同模型的结果。评估措施的计算公式如下：

$$
{ \mathrm { R e } } c a l l = { \frac { T P } { T P + F N } } { \times } 1 0 0 \%
$$

$$
\mathrm { P r } e c i s i o n = \frac { T P } { T P + F P } { \times } 1 0 0 \%
$$

$$
F 1 = \frac { 2 T P } { 2 T P + F P + F N } { \times } 1 0 0 \%
$$

其中：TP（真阳率）表示正常类型数据被正确归类的情况，TN（真阴率)表示攻击类型数据被正确归为攻击类别的情况，FN（假阴性）表示将正常类型归为攻击类型的情况，而FP（假阳性）指的是攻击类型被归类为正常类型的情况。精确度指出返回的正常类别有多少是正确的，而召回率则指出模型返回的攻击有多少是被分错的。 $F _ { 1 }$ 测度是精确度和召回率的调和平均值。

![](images/eb92b4b40c3399b701b124e19f8ad7ff8bd98532716ed37390e465fdf62a1d8e.jpg)  
图7训练数据集与测试数据集的分布Fig. 7 Distribution of dataof trainandtest

# 3.3稀疏自编码的迭代数及隐藏层数的选择

对于SSAE-lightGBM的构成要素来说，预训练迭代的数量和隐藏层的数量非常重要。预训练迭代次数太少则无法减少损失，而太多则浪费机器资源。过多的隐藏层会导致过度拟合，过少的隐藏层无法达到良好的检测性能。因此，对预训过程中的迭代次数和隐藏层数进行了实验，该实验选取的batch_size大小为64，epochs为80，隐藏层选取100-80-60的三层结构。

在不同隐藏层的情况下，损失与预训练迭代次数的关系如图8所示。从图8可以看出，随着迭代的增加,不同隐藏层的损失呈不同的下降趋势。随着迭代的增加，第1、2和第3层的损失下降在40迭代次数后都趋于稳定。通过以上分析本文选择了含3个隐藏层和40个预训练迭代数的网络结构。

![](images/79f42aa91c9c317ee559d957fae75402bace65be57d580f8edb9cad4852b2a84.jpg)  
图8预训练迭代数、隐藏层数与损失的关系  
Fig.8Relationship between pre-training,hidden number and loss

# 3.4实验性能评估

表1展示了堆稀疏自编码的lightGBM二叉树结构算法

（SSAE-lgb-BTensemble）、堆稀疏自编码的极限梯度提升集成二叉树结构算法(SSAE-xgb-BT ensemble)、主成分分析的lightGBM二叉树结构算法（PCA-lgb-BT）分别在NSL-KDD数据集上的性能表现,将三种算法分别依次用SLB、SXB、PLB表示。 $F _ { 1 }$ 值反映了模型的检测效果。在 $F _ { 1 }$ 值方面，表中显示SSAE-xgb-BT算法优于不进行深度特征提取PCA-xgb-BT算法,并且从运行时间上，也只花费了后者1/4的时间，从这可以看出堆稀疏自编码在提取特征方面要优于主成分分析法。从SSAE-lgb-BT和SSAE-xgb-BT算法的性能可以看出，在Probe类上 $F _ { 1 }$ 值达到了 $9 7 . 0 9 \%$ ，高出后者9个百分点。虽然在少数类R2L上精确度偏低，但与SSAE-xgb-BT算法相比，对于少数类U2R，在召回率上有明显提升，并且在计算时间上，SSAE-lgb-BT集成算法只用了SSAE-xgb-BT集成算法的将近1/5的时间，从而在整体性能表现上，本文提出的混合分类器的性能优于SSAE-xgb-BT等其他分类算法。

表2展示了DNN(1)[7]、DNN(2)[15]两种算法与SSAE-lgb-BT集成算法的比较，上述两种算法的数据都出自于论文中所给实验结果。从结果比对可以看出，SSAE-lgb-BT集成算法作为一种混合算法要优于DNN 算法的，由此可以进一步说明使用堆稀疏自编码进行特征降维可以从高维特征中学习到更深层次的特征。根据F1值，与所提算法进行比较，可以看出SSAE-lgb-BT算法可以更好的处理数据不平衡问题，从而有更好的分类效果。

Table 1 Comparison of different model   

<html><body><table><tr><td>模型</td><td>类别</td><td>精确度(%)</td><td>召回率(%)</td><td>F1(%)</td><td>time(s)</td></tr><tr><td rowspan="5">SLB</td><td>Normal</td><td>98.64</td><td>98.82</td><td>98.73</td><td>673</td></tr><tr><td>Dos</td><td>99.01</td><td>99.15</td><td>99.08</td><td></td></tr><tr><td>Probe</td><td>97.54</td><td>96.64</td><td>97.09</td><td></td></tr><tr><td>R2L</td><td>73.77</td><td>96.42</td><td>83.59</td><td></td></tr><tr><td>U2R</td><td>68.18</td><td>100.00</td><td>78.09</td><td></td></tr><tr><td rowspan="5">SXB</td><td>Normal</td><td>97.96</td><td>99.96</td><td>98.94</td><td>3232</td></tr><tr><td>Dos</td><td>98.57</td><td>99.17</td><td>98.86</td><td></td></tr><tr><td>Probe</td><td>75.75</td><td>99.50</td><td>86.02</td><td></td></tr><tr><td>R2L</td><td>99.18</td><td>97.13</td><td>98.14</td><td></td></tr><tr><td>U2R</td><td>69.26</td><td>89.00</td><td>77.89</td><td></td></tr><tr><td rowspan="5">PLB</td><td>Normal</td><td>90.31</td><td>92.99</td><td>91.63</td><td>14987</td></tr><tr><td>Dos</td><td>98.75</td><td>22.85</td><td>37.11</td><td></td></tr><tr><td>Probe</td><td>20.07</td><td>80.51</td><td>32.13</td><td></td></tr><tr><td>R2L</td><td>13.73</td><td>3.83</td><td>2.99</td><td></td></tr><tr><td>U2R</td><td>25.00</td><td>18.18</td><td>21.05</td><td></td></tr></table></body></html>

表2与其他模型比较

表1不同模型的结果比较  
Table 2Comparison with other models   

<html><body><table><tr><td>模型</td><td>精确度(%)</td><td>召回率(%)</td><td>F1(%)</td></tr><tr><td>SSAE-lgb-BT</td><td>87.42</td><td>98.20</td><td>91.31</td></tr><tr><td>ensemble DNN(1)</td><td>83.00</td><td>69.00</td><td>75.35</td></tr><tr><td>DNN(2)</td><td>83.00</td><td>75.00</td><td>74.00</td></tr></table></body></html>

# 4 结束语

利用堆稀疏自编码网络，以无监督的方式学习入侵检测数据的深层特征。稀疏性约束增强了堆稀疏自编码网络的泛化能力。实验结果表明，本文提出的SSAE-lgb方法能够从高维入侵数据中提取出深层的稀疏特征。与线性降维法主要成分分析法（PCA）相比，SSAE-lgb-BT集成算法显著提高了检测效果，与运用随机梯度提升法作为优化器的5层堆稀疏自编码网络SSAE-xgb-BT集成算法相比，SSAE-lgb-BT集成算法进一步提升了准确率，并节约了更多的计算时间,虽然在少数类R2L上精确度偏低，但与SSAE-xgb-BT 算法相比，对于少数类U2R，在召回率上有明显提升，从而在整体性能表现上。所以本文提出的混合分类器的性能优于其他分类算法， $F _ { 1 }$ 值达到了平均 $91 . 3 1 \%$ 。并且，本文的方法能够很好地处理类别失衡问题，提高少数类别的 $F _ { 1 }$ 值。因此本文为网络入侵检测提供了一种新的研究方法。在接下来的工作中将进一步提升算法的性能，本文通过将训练集数据进行聚类（聚类中心为5)，再将测试集对5个聚类中心进行分类（可采用KNN)，如此可以进一步提高SSAE-lgb二叉树集成算法的准确率和计算时间。

# 参考文献：

[1]Sarasamma S T, Zhu Qiuming A,Huff J.Hierarchical Kohonenen net for anomaly detection in network security [J].IEEE Trans on Systems Man& Cybernetics PartB Cybernetics,2005,35(2):302.   
[2]Khalid C,Zyad E,Mohammed B.Network intrusion detection system using Ll-norm PCA[C]//Proc of the 11th International Conference on Information Assurance & Security.2016.   
[3]Fiore U,Palmieri F,Castiglione A,et al.Network anomaly detection with the restricted Boltzmann machine.[J].Neurocomputing,2O13,122: 13-23.   
[4]Salama MA,Eid HF,Ramadan RA,et al.Hybrid Intelligent Intrusion Detection Scheme [M]//Soft Computing in Industrial Applications, Volume 96 of the Advances in Intelligent and Soft Computing Book Series.Berlin: Springer-Verlag,2011:293-303.   
[5]Wang Yao,Cai Wandong,Wei Pengcheng.A deep learning approach for detecting malicious JavaScript code [J].Security & Communication Networks,2016,9(11):1520-1534.   
[6]Alrawashdeh K,Purdy C.Toward an online anomaly intrusion detection system based on deep learning[C]//Proc of thel5th IEEE International Conference on Machine Learning& Applications.Piscataway,NJ:IEEE Press,∠01/.   
[7]Javaid A Y,Niyaz Q, Sun Weqing,et al.A deep learning approach for network intrusion detection system [C]// Proc of the 9th EAI InternationalConferenceonBio-inspiredInformationand Communications Technologies.New York:ACMPress,2015:21-26.   
[8]Zhang Baoan,Yu Yanhua,Li Jie.Network intrusion detection based on stacked sparse autoencoder and binary tree ensemble method [C]//Proc of IEEE International Conference on Communications Workshops. Piscataway,NJ:IEEE Press,2018:20-2.   
[9]Tavallaee M,Bagheri E,Lu Wei,et al.A detailed analysis of the KDD CUP 99 data set [C]/ Proc of the 2nd IEEE International Conference on Computational Intelligence for Security & Defense Applications. Piscataway,NJ:IEEE Press,2009:53-58.   
[10]Ke Guolin,Meng Qi,Thomas F,LightGBM:a highly efficient gradient boosting decision tree [Cl// Proc of the 31st Conference on Neural Information Processing Systems.Long Beach,CA: NIPS Press,2017.   
[11] Kingma D P,Ba J.Adam: a method for stochastic optimization [C]// Proc of the 3rd International Conference for Learning Representations. 2015.   
[12]Lee H,Grosse R,Ranganath R,et al.Convolutional deep belief networksforscalableunsupervisedlearningofhierarchical representations [C]// Proc of the 26th Annual International Conference on Machine Learning.New York: ACMPress,2009: 609-616.   
[13] Chawla N V,Bowyer K W,HallL O,et al. SMOTE: synthetic minority over-sampling technique [J]. Journal of Artificial Intelligence Research, 2002,16(1):321-357.   
[14] Garcia S,Herrera F.Evolutionary undersampling for classification with imbalanced datasets:proposalsand taxonomy [J].Evolutionary Computation,2014,17(3): 275-306.   
[15] Tang TA,Mhamdi L,McLernon D,et al.Deep learning approach for network intrusion detection in software defined networking[C]//Proc of InternationalConferenceonWirelessNetworks&Mobile Communications.Piscataway,NJ:IEEE Press,2016.