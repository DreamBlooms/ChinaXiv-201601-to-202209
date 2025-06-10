# 基于非鲁棒特征的图卷积神经网络对抗训练方法

承琪，朱洪亮，辛阳(北京邮电大学 网络空间安全学院，北京 100876)

摘要：图卷积神经网络可以通过图卷积提取图数据的有效信息，但容易受到对抗攻击的影响导致模型性能下降。对抗训练能够用于提升神经网络鲁棒性，但由于图的结构及节点特征通常是离散的，无法直接基于梯度构造对抗扰动，而在模型的嵌入空间中提取图数据的特征作为对抗训练的样本，能够降低构造复杂度。借鉴集成学习思想，提出一种基于非鲁棒特征的图卷积神经网络对抗训练方法 VDERG，分别针对拓扑结构和节点属性两类特征，构建两个图卷积神经网络子模型，通过嵌入空间提取非鲁棒特征，并基于非鲁棒特征完成对抗训练，最后集成两个子模型输出的嵌入向量作为模型节点表示。实验结果表明，提出的对抗训练方法在干净数据上的准确率平均提升了 $0 . 8 \%$ ，在对抗攻击下最多提升了 $6 . 9 1 \%$ 的准确率。

关键词：图卷积神经网络；集成学习；非鲁棒特征；对抗训练 中图分类号：TP183 doi:10.19734/j.issn.1001-3695.2022.01.0012

Graph neural networks adversarial training with non-robust features

Cheng Qi, Zhu Hongliang†, Xin Yang (Cyber Security,Beijing UniversityofPosts&Telecommunications,Beijing lOo876,China)

Abstract: Graph convolutionalneuralnetworkscandistilltheefectiveinformationof graphdata through graphconvolution. However,the graphconvolutionalneural network showvulnerabilitytoadversarialatack,which leads tothedegradationof model performance.Adversarial training can be used to improve therobustness of neural networks.However,since the structureandnodefeaturesof graphsareusuallydiscrete,itisimpossble todirectlyconstructadversarial examplesbasedon gradients.Therefore,distilling featureofgraphdataintheembedding spaceofmodels asadversarial examples canreduce the complexity of adversarial training.Byusing the idea of the idea of ensemble learning,this paper innovatively proposes an adversarial training method based on non-robust features distilation for graph convolution network,VDERG.The method constructed two graph convolution neural networks assub models from the two types of features of topology and node atributesrespectively.Sub models distilled non-robust features through embeding spaceand used these features to implementadversarialtraining.Finaly,themethod combined the embedding given bythe two sub models as the nodes vectors.Experimentalresults show that theadversarial training strategy improves the accuracyof graph convolution neural networks in clean data by $0 . 8 \%$ on average,and improves the accuracy by $6 . 9 1 \%$ at most under adversarial attack.

Key words: graph convolutional neural network; ensemble learning; non-robust features; adversarial training

# 0 引言

图作为一种具有普遍性的数据结构，可以广泛用于表示不同领域中的系统，例如经济领域(交易网络)、社会科学领域(社交网络和引文网络)、自然科学领域(分子结构)和知识图等，近年来图神经网络(graphneuralnetwork,GNN)在学习图表示方面取得了令人瞩目的成果。其中，图卷积神经网络(graphconvolutionalneuralnetwork,GCN)通过利用边的信息对节点信息进行聚合生成节点表示，在图信息的提取方面效果显著。从图中提取出的特征可以用于节点分类、链路预测、图分类等任务，在数据挖掘、推荐系统等领域有着广泛的应用。

已有研究证明缺乏鲁棒性的神经网络容易受到对抗攻击的影响，即加入了微小扰动的对抗样本，会大大降低神经网络的模型表现[1]。Dai等人[2]发现随机丢弃节点间的边就能对图神经网络造成较好的攻击效果。GCN的脆弱性可能在其应用领域导致安全问题，例如在信用检测系统中，欺诈者可以通过与几个高信用用户伪装多个交易，从而在模型检测中获得"高信用用户"的虚假结果[2]。因此开始有大量研究针对提

升GCN鲁棒性展开。

对抗训练[3]被广泛用于提升神经网络的鲁棒性：通过在模型训练过程中加入对抗样本，使神经网络适应对抗扰动，从而提升对抗攻击下的模型表现。现有针对GCN的对抗训练方法研究主要集中于针对单个模型构造扰动正则项或修改图结构，少有研究从集成的角度借助多个分类器的学习能力提升模型的鲁棒性。

对抗攻击的特征之一是在神经网络间具有泛化性，而通过集成多个神经网络模型分别进行对抗训练，能够使总体模型学习到更全面的特征信息，从而提升模型鲁棒性。文献[4,5]指出，基于集成学习的防御算法效果依赖于子模型的多样化。只有使子模型分别学习到不同的特征，才能避免对抗扰动在子模型间迁移，有效提升总体模型的防御能力。考虑到图数据的特征，Wu等人[构造了包含两个子模型的集成模型，分别针对拓扑结构信息和节点属性信息进行模型训练，以此提升GNN鲁棒性。但仅仅通过在结构信息和属性信息上分开训练子模型，没有考虑对抗攻击的攻击特点，在结构信息和属性信息都受到攻击的情况下仍可能产生较大的预测偏差。

对神经网络进行模型训练本质上是从图数据中学习特征的过程，而学习到的有利于提升模型表现的特征会对对抗扰动表现出不一样的敏感度，基于不同的对抗扰动敏感度，可以将这些特征分为鲁棒特征和非鲁棒特征两类。数据中的鲁棒特征即使在对抗攻击下，仍能保持稳定性，帮助模型学习正确的有效信息，而非鲁棒特征则会被对抗扰动窜改，使模型在训练过程中学习错误的信息，进而导致模型表现降低。模型学习到的非鲁棒特征导致了模型的脆弱性，但目前基于非鲁棒特征进行对抗训练的研究都针对图像数据展开，鲜有研究利用图数据上的非鲁棒特征提升模型鲁棒性。

基于上述问题，本文旨在探索图数据中的非鲁棒特征对于提升GCN模型鲁棒性的作用，并结合图数据中的结构信息和节点属性信息，给出非鲁棒特征定义及提取方法。并且，基于GCN从图数据中学习到的非鲁棒特征以及集成学习方法，提出一套基于非鲁棒特征的鲁棒图卷积神经网络集成模型(vulnerabilities distillation of ensembles for robust graphneuralnetworks,VDERG)。VDERG利用图卷积层后的嵌入向量，分别从结构信息和属性信息中提取非鲁棒特征，并以此对两个子模型分别进行对抗训练，使两个子模型分别适应节点关系和节点属性上的对抗扰动，然后集成两个子模型的节点嵌入向量，输入映射函数作为最终预测结果。实验证明本文提出的防御算法能够有效提高图卷积神经网络模型的鲁棒性。

本文的主要贡献如下：a)定义了图数据上的非鲁棒特征，并结合图数据特点，从结构信息和属性信息两方面给出非鲁棒特征提取方法；b)提出一种基于集成学习的鲁棒性图卷积神经网络算法，通过非鲁棒特征对子模型进行对抗训练，并使不同子模型分别从结构信息和属性信息中学习图信息，集成节点向量表征，有效抵御对抗攻击影响。

# 1 相关工作

# 1.1对抗训练

图卷积神经网络可以看做卷积神经网络在图数据上的迁移变种，由于二者相似的卷积机制，图卷积神经网络同样容易受到对抗攻击干扰。对于图 $\mathcal { G } = ( A , X )$ 上节点水平的对抗攻击，攻击者的目标是找到一个图结构 $\hat { \mathcal { G } } = \left( \hat { A } , \hat { X } \right)$ ，能够最大化目标节点 $V _ { t }$ 在图神经网络模型 $f _ { \theta }$ 上的损失值 $\mathcal { L } _ { a t k } \Big ( f _ { \theta } \big ( \hat { \mathcal { G } } \big ) \Big )$ ,其中需要约束对抗扰动不易被察觉，即 $\left. \hat { A } - A \right. _ { 0 } + \left. \hat { X } - X \right. _ { 0 } \leqslant \Delta$ 。由于图数据上的任务特性，目前大多数的对抗攻击为投毒攻击，即攻击者在训练数据集中加入对抗样本实施攻击[7]。

近年来由于图卷积神经网络在节点表征上的强大表达能力，有许多研究开始关注如何提升GCN模型的鲁棒性。对抗训练已经在提升卷积神经网络等模型的鲁棒性上取得了显著成果，也被众多学者借鉴用于提升GCN模型的鲁棒性。对抗训练在模型训练过程中生成对抗样本，并同时最小化模型在对抗样本上的损失值，即 $\operatorname* { m i n } _ { \theta } \mathcal { L } _ { t r a i n } \big ( f _ { \theta } \big ( \hat { \mathcal { G } } \big ) \big )$ 。Dai 等人[2]通过在模型训练过程中随机丢弃图中的边从而对扰动邻接矩阵，但这种训练方法只降低了 $1 \%$ 的攻击成功率。Dai等人[8]基于DeepWalk[9]，提出在嵌入空间中加入噪声以进行针对投毒攻击情境下的对抗训练，提升了DeepWalk在节点分类任务上的泛化能力。这种对抗训练方法可以扩展到一系列节点嵌入的模型，但实验缺少对模型鲁棒性的对比验证。Feng等人[10]认为图的平滑性会导致对抗扰动在节点间传播，并针对这个问题通过添加一个对抗正则项，降低目标样本及其相连样本与预测值间的差异，结果表明添加了正则项的GCN-GAD对对抗扰动的敏感度下降，但实验中没有明确使用的对抗攻击方法。Wang等人[1]提出忽略图的离散性而直接对邻接矩阵、特征矩阵加入扰动，针对随机丢弃边一种攻击方法，实验验证提出的GraphDefense方法能够保证对抗攻击后模型准确率提升0.2左右。图数据的离散性给GCN上的对抗训练带来了挑战，在邻接矩阵或特征矩阵上直接加入扰动的方法能够降低对抗训练方法的复杂度。

# 1.2集成学习

集成学习被广泛研究用于提高模型的性能，通过结合多个单学习器，提升整体模型的泛化性。由于神经网络模型总会倾向于从数据集中提取类似的特征进行学习，对抗攻击在不同的图神经网络间也具有泛化性[12]。基于集成学习的对抗攻击防御方法，可以通过使不同子模型间具有不同的对抗子空间(adversarialspace,Adv-SS)[13]，防止对抗攻击造成的影响在子模型间转移[14]。Kariyappa 等人[5]提出多样性训练降低子模型间损失函数的相关性。Pang等人[4]提出了一种自适应的正则项，鼓励不同子模型的非极大预测值具有多样化。Yang等人[15]基于数据中非鲁棒特征分布更普遍的发现，通过让子模型提取不同非鲁棒特征并集成模型学习能力，提升了模型在干净数据和攻击数据上的表现。上述基于集成学习的方法在图像领域取得了显著成果。

目前，将集成学习用于图领域以提升模型表现和模型鲁棒性的研究很少。张嘉杰等人[14]基于节点间的特征相似度重构了一个属性图，并分别基于结构信息和属性图进行预测，最后聚合二者的预测值作为返回结果。这种集成算法基于特征相似的节点以及相邻节点间通常具有相似标签的假设，对于属性信息进行了预处理，一定程度提升了模型表现，但在图结构受到扰动的情况下无法消除攻击影响，存在一定的局限性。Wu等人[选取两个子模型分别从图的结构信息和属性信息进行学习并在每轮迭代中平均两个子模型的置信度，将集成模型最有信心的预测值作为该节点的伪标签，并将该节点加入到训练集中，以此提升模型鲁棒性。该方法主要用于解决半监督学习下缺少标签的问题，没有考虑对抗攻击下图结构和节点属性上的变化。

# 1.3非鲁棒特征研究

监督学习下，神经网络通过提取学习数据集中的特征提升模型能力，神经网络学习到的特征将直接决定其模型预测能力，Ilyas等人[12]认为模型学习到的泛化性良好的特征是对抗攻击的基础，并通过在图像数据集上构建“鲁棒版数据集"和"非鲁棒版数据集”，证明了数据集中的非鲁棒特征会导致神经网络容易受到对抗攻击影响，因此非鲁棒特征在提升神经网络鲁棒性上具有研究价值。Yang等人[15]通过模型卷积层后的嵌入向量提取图像数据中的非鲁棒特征，在提升模型鲁棒性的同时保证了干净数据集上的模型表现。

目前针对非鲁棒特征的研究大都集中在图像领域，但Garg等人[16]发现不受对抗攻击影响的鲁棒特征与图像数据的谱特征有关，说明图数据的拉普拉斯矩阵同样可能存在非鲁棒特征从而导致GCN的脆弱性。Jin 等人[17的实验证明，去除对抗攻击的边和正常的边会对邻接矩阵的秩和奇异值产生不同的影响，说明对抗攻击生成过程所利用的特征具有特殊性，侧面印证了GCN学习到的特征中对于对抗攻击的易感性不同。由于GCN同时基于结构信息和节点属性信息进行模型训练，图数据上的非鲁棒特征研究应针对这两方面展开。文献[17]通过对比现实世界中的图和metattack[18]攻击后的图，发现现实图中的相连节点大多倾向于拥有相似的属性特征，而对抗攻击会改变图的平滑度。文献[10]通过提升图的平滑度构造正则项提升了模型表现。上述研究说明图数据集中的非鲁棒特征可能与图的平滑度有关。

# 2 基于非鲁棒特征的集成对抗训练方法

受图像领域的非鲁棒特征提取方法启发，本文提出基于非鲁棒特征的集成对抗训练方法VDERG，考虑图数据的拓扑结构信息和节点属性信息，在模型的嵌入向量空间，分别通过与随机图的矩阵差异和特征平滑度差异获得梯度，对应在邻接矩阵和属性矩阵上进行迭代从而得到图数据中的非鲁棒特征。将非鲁棒特征作为对抗样本，让两个子模型分别在得到的结构非鲁棒特征和属性非鲁棒特征上进行对抗训练，最后对两个子模型的嵌入向量求和取平均，通过softmax函数得到节点预测标签。方法整体流程如图1所示。

![](images/829b1219fc845b2c363df83a9dd565e2382a150b301849229e451fdd6fcad194.jpg)  
图1VDERG方法流程图  
Fig.1Flow chart of VDERG

# 2.1问题描述

定义一个图为 $\mathscr { G } = ( \nu , \mathcal { E } )$ ，其中 $\nu$ 为节点集合，包含N 个节点 $\{ v _ { 1 } , v _ { 2 } , \cdots , v _ { N } \}$ ， $\varepsilon$ 为边的集合。节点间的关系可以通过邻接矩阵 $A \in \mathbb { R } ^ { N \times N }$ 进行表示，其中 $A _ { i j }$ 表示节点 $\boldsymbol { v } _ { i }$ 和节点 $\boldsymbol { v } _ { j }$ 间的关系。 $X = [ x _ { 1 } , x _ { 2 } , . . . , x _ { N } ] \in \mathbb { R } ^ { N \times N }$ 表示节点特征矩阵， $\boldsymbol { x } _ { i }$ 表示节点$\boldsymbol { v } _ { i }$ 的特征向量。则一个图也可以用 $\mathcal { G } = ( A , X )$ 来表示。根据常见的节点分类任务设定，本文假定数据集中只有部分节点 $\mathcal { V } _ { L } = \{ v _ { 1 } , v _ { 2 } , \cdots , v _ { L } \}$ 带有标签 $\mathcal { V } _ { L } = \{ y _ { 1 } , y _ { 2 } , \cdots , y _ { L } \}$ ，其中节点$\boldsymbol { v } _ { i }$ 的标签对应为 $y _ { i }$ 。则对于节点分类任务，给定图 $\mathcal { G } = ( A , X )$ 以及部分节点标签 $\mathcal { V } _ { L }$ ，GCN的目标是学习一个能够将节点映射到一组标签的函数 $f _ { \theta } \colon \mathcal { V } _ { L } \to \mathcal { V } _ { L }$ ，并利用函数 $f _ { \theta }$ 对无标签的节点进行分类预测，学习过程可以由以下公式进行描述：

$$
\operatorname* { m i n } _ { \theta } \mathcal { L } _ { G C N } ( \theta , A , X , \mathcal { V } _ { L } ) = \sum _ { v _ { i } \in \mathcal { V } _ { L } } \ell ( f _ { \theta } \left( X , A \right) _ { i } , y _ { i } )
$$

其中， $\theta$ 为需要学习的 $f _ { \theta }$ 的参数， $f _ { \theta } ( X , A ) _ { i }$ 表示节点 $\boldsymbol { v } _ { i }$ 的预测值， $\ell ( \cdot , \cdot )$ 表示预测值和标签之间的差异，通常用交叉熵函数计算。目前最常用的GCN结构为两层GCN[19]，即模型参数$\theta = \left( W _ { 1 } , W _ { 2 } \right)$ ，则函数 $f _ { \theta }$ 可以进一步细化为

$$
f _ { \theta } \left( X , A \right) { = } \mathrm { s o f t m a x } \left( \hat { A } \sigma \big ( \hat { A } X W _ { 1 } \big ) W _ { 2 } \right)
$$

其中， $\hat { A } = \tilde { D } ^ { - 1 / 2 } \left( A + I \right) \tilde { D } ^ { - 1 / 2 }$ 表示对邻接矩阵进行标准化， $\tilde { D }$ 表示 $A + I$ 对角矩阵, $\tilde { D } _ { i i } { = } 1 + \sum _ { j } A _ { i j }$ $\sigma$ 表示激励函数，常用ReLU 函数。

基于上述定义，给定图 $\mathcal { G } = ( A , X )$ 和标签 $\mathcal { V } _ { L }$ ，本文提出的VDERG算法将针对投毒攻击，在邻接矩阵 $A$ 和特征矩阵 $X$ 可能被投毒的前提下，学习GCN模型参数 $\theta$ ，通过对抗训练得到一个具有鲁棒性的GCN模型，提升对抗攻击下无标签节点上的预测分类表现。

# 2.2非鲁棒特征提取

GCN通过提取图数据中的特征学习节点的嵌入表示，提取过程中所利用的图数据特征中，一部分特征具有鲁棒性，即不易受到对抗攻击扰动的影响，反之则为非鲁棒特征，受到攻击后会使模型的表现下降。

设想最理想的非鲁棒特征提取情况：提取得到的扰动图中蕴涵所有可能干扰GCN的非鲁棒特征，且原图数据和扰动图数据间的差异巨大，但通过GCN模型后得到了相同的嵌入向量，如图2所示，则扰动图中包含的非鲁棒特征将对GCN生成节点嵌入表示产生致命影响。基于以上理论，本文对GCN在图数据上提取的非鲁棒特征作出如下定义：$\mathcal { G } = ( A , X )$ 为原图数据的邻接矩阵及属性矩阵， $\mathcal { G } ^ { \prime } = ( A ^ { \prime } , X ^ { \prime } )$ 为随机生成的、与原图具有相同节点数但节点关系、属性特征不同的图数据。GCN模型 $f$ 的第 $l$ 层从图 $\mathcal { G } ^ { \prime }$ 中提取出的、对应图 $\mathcal { G }$ 的非鲁棒特征 $\mathscr { R } = ( S , T )$ 可以由下式定义：

$$
\begin{array} { r l } & { d i s \left( \mathcal { G } , \mathcal { G } ^ { \prime } \right) = \underset { ( S , T ) } { \arg \operatorname* { m i n } } \left[ \alpha L \left( f ^ { \iota } ( S ) , f ^ { \iota } ( A ) \right) + \beta R \left( f ^ { \iota } ( T ) , f ^ { \iota } ( X ) \right) \right] , } \\ & { \left\| S - A ^ { \prime } \right\| _ { \infty } \leq \epsilon , \ \left\| T - X ^ { \prime } \right\| _ { \infty } \leq \zeta } \end{array}
$$

其中， $f ^ { l } \left( \cdot \right)$ 表示GCN模型第 $l$ 个隐藏层在激励函数(如ReLU)前的输出。考虑到对抗攻击可以通过修改节点间关系或节点属性对GCN模型产生干扰，式(3)代表的特征提取过程分别从邻接矩阵和属性矩阵两方面进行约束优化，目标是从图 $\mathcal { G } ^ { \prime }$ 中提取出可能让GCN模型混淆识别为图 $\mathcal { G }$ 的特征，即图 $\mathcal { G }$ 中的非鲁棒特征。

式(3)的第一项 $L ( f ^ { l } ( S ) , f ^ { l } ( A ) )$ 通过最小化原图邻接矩阵 $A$ 和提取邻接特征 $\boldsymbol { s }$ 在嵌入空间的差异，使从节点关系中提取的特征接近GCN学习到的节点关系信息。可以通过约束 $f ^ { l } ( S )$ 和 $f ^ { l } ( A )$ 的 $\mathrm { ~ F ~ }$ 范数实现上述目标，即可以将第一项重写为

$$
L ( f ^ { \iota } ( S ) , f ^ { \iota } ( A ) ) = \parallel f ^ { \iota } ( S ) - f ^ { \iota } ( A ) \parallel _ { F } ^ { 2 }
$$

而第二项 $R \left( f ^ { l } ( T ) , f ^ { l } ( X ) \right)$ 则考虑从节点的属性信息中提取特征。对抗攻击在连接属性差异大的节点或删除相似节点间链接时，会降低图的平滑度，因此本文考虑通过最小化原图属性矩阵 $X$ 和提取属性特征 $T$ 间的特征平滑度差异，使从节点属性中提取的特征接近GCN学习的节点属性信息，即式(3)的第二项可以被重写为

$$
\begin{array} { r l } {  { R \bigl ( f ^ { \iota } ( T ) , f ^ { \iota } ( X ) \bigr ) = \frac { 1 } { 2 } \parallel \sum _ { n , m = 1 } ^ { N } S _ { n m } ( f ^ { \iota } ( t _ { n } ) - f ^ { \iota } ( t _ { m } ) ) ^ { 2 } - } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \sum _ { n , m = 1 } ^ { N } A _ { n m } ( f ^ { \iota } ( x _ { n } ) - f ^ { \iota } ( x _ { m } ) ) ^ { 2 } \parallel } \end{array}
$$

其中， $A$ 表示图数据的邻接矩阵， $A _ { n m }$ 表示节点 $\boldsymbol { v } _ { n }$ 和 $v _ { m }$ 相连，$( x _ { n } - x _ { n } ) ^ { 2 }$ 衡量了节点 ${ \boldsymbol { v } } _ { n }$ 和 $v _ { m }$ 通过 GCN 模型得到的嵌入向量间的差异。 $\frac { 1 } { 2 } \sum _ { n , m = 1 } ^ { N } A _ { n m } ( x _ { n } - x _ { m } ) ^ { 2 }$ 衡量了图 $( A , X )$ 的特征平滑度差异，$\frac { 1 } { 2 } \sum _ { n , m = 1 } ^ { N } S _ { n m } ( t _ { n } - t _ { m } ) ^ { 2 }$ 同理。通过约束特征平滑度差异进行属性特征提取，充分考虑了现实中攻击者常常将差异较大的节点相连以降低模型预测能力的攻击特点。

隐藏层 隐藏层(A,X) 西品西 品品西 embedding1ReLU ReLU  
好相似的嵌入向量  
非鲁棒特征(S,E) 乐 宏品 embedding2  
小 ReLU ReLU心 /子

# 2.3基于非鲁棒特征的集成对抗训练

集成学习作为一种训练思路能够用于提升模型鲁棒性，通过让集成学习中的子模型分别学习到不同的特征，能够在保持简单模型结构的前提下提升模型表现。而若能让不同子模型学习到不同的非鲁棒特征，则能避免对抗攻击的泛化性影响到所有子模型，提升集成后的模型表现。基于上述理论，本文采用集成学习思想，采用两个子模型分别从节点关系和节点属性两个方面提取图数据中的非鲁棒特征，并利用提取的非鲁棒特征对模型进行对抗训练。对抗训练常通过在样本中加入微小扰动，使神经网络适应扰动从而提升对抗样本上的模型鲁棒性。但图数据作为非欧几里德数据结构，无法通过梯度相关方法构造对抗样本。因此，通过提取的特征对模型进行对抗训练，避开了构造对抗样本过程中需要考虑的数据离散问题，更加简单且具有可解释性。

# 2.3.1基于节点关系的非鲁棒特征学习方法

参考式(1)和(2)，第一个子模型从邻接矩阵中提取节点关系所含非鲁棒特征 $( S , X )$ 的过程可以用下式表示：

$$
\underset { s } { \arg \operatorname* { m i n } } \mathcal { L } _ { a } = \Vert f _ { 1 } { ^ { 2 } } ( S ) - f _ { 1 } { ^ { 2 } } ( A ) \Vert _ { F } ^ { 2 } ,
$$

$$
\| S - A ^ { \prime } \| _ { \infty } \leq \epsilon
$$

其中， $f _ { 1 } { } ^ { 2 }$ 表示第一个子模型的第二层卷积层后、激励函数前的嵌入向量。通过约束特征 $\boldsymbol { s }$ 和随机图邻接矩阵 $A ^ { \prime }$ 间的差异小于e，最小化 $\boldsymbol { S }$ 和原图邻接矩阵 $A$ 在嵌入空间中的差异距离，从随机图 $\boldsymbol { \mathcal { G } ^ { \prime } }$ 的邻接矩阵中提取出与随机图 $\mathcal { G } ^ { \prime }$ 相似，但会错使GCN模型预测为图 $\mathcal { G }$ 的非鲁棒特征。则第一个子模型进行对抗训练时的目标损失函数为

$$
\begin{array} { r l } & { \underset { \boldsymbol { s } } { \arg \operatorname* { m i n } } \mathcal { L } _ { 1 } = \mathcal { L } _ { f _ { 1 } } = \mathcal { L } _ { G C N } ( \boldsymbol { \theta } _ { 1 } , \boldsymbol { S } , \boldsymbol { X } , \mathcal { V } _ { L } ) , } \\ & { \left\| \boldsymbol { S } - \boldsymbol { A } ^ { \prime } \right\| _ { \infty } \leq \epsilon } \end{array}
$$

其中， $\mathcal { L } _ { G C N } ( \theta _ { 1 } , S , X , \mathcal { V } _ { L } )$ 是第一个 GCN 子模型在输入特征$( S , X )$ 上的损失函数。通过最小化式(7)，能够训练第一个模型学习到节点关系中包含的非鲁棒特征，提升模型的鲁棒性。

# 2.3.2基于节点属性的非鲁棒特征学习方法

参考式(1)和(3)，同样基于GCN第二层卷积层后的嵌入向量，第二个子模型从属性矩阵中提取节点属性所含非鲁棒特征 $( A , T )$ 的过程可以用下式表示：

$$
\begin{array} { l } { \displaystyle \arg \operatorname* { m i n } _ { T } \mathcal { L } _ { f } = \frac { 1 } { 2 } \parallel \sum _ { n , m = 1 } ^ { N } S _ { n m } ( { f _ { 2 } } ^ { 2 } ( t _ { n } ) - { f _ { 2 } } ^ { 2 } ( t _ { m } ) ) ^ { 2 } - } \\ { \displaystyle \sum _ { n , m = 1 } ^ { N } A _ { n m } ( { f _ { 2 } } ^ { 2 } ( x _ { n } ) - { f _ { 2 } } ^ { 2 } ( x _ { m } ) ) ^ { 2 } \parallel , } \\ { \parallel T - X ^ { \prime } \parallel _ { \infty } \le \zeta } \end{array}
$$

其中， $f _ { 2 } { } ^ { 2 }$ 表示第二个子模型的第二层卷积层后、激励函数前的嵌入向量。类似地，约束特征 $T$ 和随机图属性矩阵的差异小于 $\zeta$ ，并最小化 $T$ 和原图属性矩阵 $X$ 在嵌入空间中的特征平滑度差异，以此从随机图 $\boldsymbol { \mathcal { G } ^ { \prime } }$ 的属性矩阵中提取出对应图 $\mathcal { G }$ 的非鲁棒特征。则第二个子模型进行对抗训练时的目标损失函数为

$$
\underset { T } { \arg \operatorname* { m i n } } \mathcal { L } _ { 2 } = \mathcal { L } _ { f _ { 2 } } = \mathcal { L } _ { G C N } ( \theta _ { 2 } , A , T , \mathcal { V } _ { L } ) ,
$$

$$
\parallel T - X ^ { \prime } \parallel _ { \infty } \leq \zeta
$$

其中， $\mathcal { L } _ { G C N } ( \theta _ { 2 } , A , T , \mathcal { y } _ { L } )$ 是第二个 GCN 子模型在输入特征$( A , T )$ 上的损失函数。式(9)能够训练第二个子模型从节点属性的角度学习非鲁棒特征，降低对抗攻击的影响效果。

# 2.3.3基于集成学习的对抗训练策略

基于上述非鲁棒特征学习方法，本文提出的VDERG 的对抗训练过程如下：首先随机生成两个GCN子模型，在每轮迭代中根据输入图生成节点数相同的随机图，通过随机梯度下降优化式(6)和(8)，借助随机图分别从邻接矩阵和属性矩阵中提取输入图的非鲁棒特征。然后基于节点关系和节点属性中的非鲁棒特征分别对两个子模型进行对抗训练，利用式(7)和(9)的交叉熵损失函数优化子模型参数，通过Adam对网络参数进行优化，最后对两个子模型得到的节点嵌入向量求和取均值，经过softmax函数得到最终模型的预测结果。伪代码如算法1所示。

算法1VDERG 的训练策略输入：邻接矩阵 $A$ ，属性矩阵 $X$ ，标签 $\mathcal { V } _ { L }$ ，特征提取过程轮数 $N _ { 1 } , N _ { 2 }$ ，步长 $\alpha$ 、 $\beta$ ，学习率 $\eta$ 。

输出：集成GCN 模型的参数 $\theta _ { 1 }$ 、 $\theta _ { 2 }$ ，节点预测结果。

Randomly initialize $\theta _ { 1 }$ ， $\theta _ { 2 }$ //初始化2个GCN子模型的参数;for $\boldsymbol { \mathscr { e } }$ in range $( E )$ ：

$( A ^ { \prime } , X ^ { \prime } ) {  } r a n d o m { \_ } a t t a c k ( ( A , X ) , p t b \_ r a t e = 1 )$ /\*通过在输入图数据上实施扰动率1.0的随机攻击生成随机图 $^ { * } /$

Initialize $\vert s {  } A ^ { \prime }$ //利用随机图的邻接矩阵初始化特征 $s$

for $\mathbf { \chi } _ { i }$ in $N _ { 1 }$ ：

通过式(6)以步长 $\alpha$ 更新 $\boldsymbol { S }$ 得到 $( S , X )$ //基于嵌入空间从邻接矩阵提取非鲁棒特征

end

$$
g _ { 1 } {  } \frac { { \mathcal { L } _ { G C N } } ( \theta _ { 1 } , S , X , \mathcal { V } _ { L } ) } { \mathcal { \vartheta } \theta _ { 1 } }
$$

$\theta _ { 1 } {  } \theta _ { 1 } - \eta g _ { 1 }$ //更新第一个子模型参数

Initialize $\boldsymbol { T } {  } \boldsymbol { X } ^ { \prime }$ //利用随机图的属性矩阵初始化特征 $T$ for $j$ in $N _ { 2 }$ ：

通过式(8)以步长 $\beta$ 更新 $T$ 得到 $( A , T )$ /\*基于嵌入空间的特征平滑度差异提取非鲁棒特征\*/

$$
g _ { 2 } {  } \frac { { \mathcal { L } _ { G C N } } ( \theta _ { 2 } , A , T , \mathcal { V } _ { L } ) } { \mathcal { V } \theta _ { 2 } }
$$

$$
p r e d = \mathrm { s o f t m a x } ( \frac { e m b e d d i n g _ { 1 } + e m b e d d i n g _ { 2 } } { 2 } )
$$

end

# 3 实验结果与分析

# 3.1数据集描述

本文选取了图领域常见的三种引文网络数据集作为数据集进行节点分类任务实验，数据集的详细信息如表1所示。实验中，参考著名攻击算法Metattack的数据集划分方法，本文将所有数据集按照 $10 \%$ 和 $90 \%$ 的比例随机分割为有标签集和无标签集，再进一步把有标签集按照 $50 \%$ 和 $50 \%$ 的比例分

为训练集和验证集。

Tab.1Data description   

<html><body><table><tr><td>数据集</td><td>节点数</td><td>特征</td><td>类别</td><td>边</td></tr><tr><td>Cora</td><td>2708</td><td>1433</td><td>7</td><td>5278</td></tr><tr><td>Citeseer</td><td>3327</td><td>3703</td><td>6</td><td>4552</td></tr><tr><td>PubMed</td><td>19717</td><td>500</td><td>3</td><td>44324</td></tr></table></body></html>

# 3.2 模型效果对比

为了验证本文所提出的VDERG的对抗攻击防御能力，本文基于对抗攻击算法Metattack，将VDERG与目前效果最好的几种GCN防御算法在节点分类准确率上进行对比评估。Metattack有五个变种，在数据集Cora和Citeseer上本文采用攻击效果最好的Meta-Self变种进行实验；在数据集Pubmed数据集上，出于节省时间的内存的考虑，本文采用和Meta-Self变种相似的A-Meta-Self变种进行实验。实验针对从0到 $20 \%$ 的扰动率进行了实验，每次提升 $5 \%$ 扰动率，参考实验结果如表2 所示，其中GCN、GAT、GCN-Jaccard、Pro-GNN的实验结果来自文献[17]，SimP-GCN的实验结果来自原论文。为了使模型结果更加客观、消除深度学习训练过程中的随机性，所有实验均重复了10次。

表1数据集描述  
表2全局攻击(metattack)下节点分类任务表现对比  

<html><body><table><tr><td>数据集</td><td>扰动率/%</td><td>GCN[19]</td><td>GAT[20]</td><td>Pro-GNN[17]</td><td>SimP-GCN [21]</td><td>VDERG</td></tr><tr><td rowspan="5">Cora</td><td>0</td><td>83.50±0.44</td><td>83.97±0.65</td><td>83.42±0.52</td><td>81.81±0.62</td><td>84.26±0.43</td></tr><tr><td>5</td><td>76.55±0.79</td><td>80.44±0.74</td><td>82.78±0.39</td><td>76.43±1.98</td><td>83.98±0.63</td></tr><tr><td>10</td><td>70.39±1.28</td><td>75.61±0.59</td><td>79.03±0.59</td><td>73.27±1.93</td><td>82.72±1.38</td></tr><tr><td>15</td><td>65.10±0.71</td><td>65.10±0.71</td><td>76.40±1.27</td><td>70.75±3.98</td><td>81.70±0.71</td></tr><tr><td>20</td><td>59.56±2.72</td><td>59.94±0.92</td><td>73.32±1.56</td><td>66.63±6.87</td><td>80.23±1.21</td></tr><tr><td rowspan="5">Citeseer</td><td>0</td><td>71.96±0.55</td><td>73.26±0.83</td><td>73.28±0.69</td><td>73.76.±0.78</td><td>75.01±1.09</td></tr><tr><td>5</td><td>70.88±0.62</td><td>72.89±0.83</td><td>73.09±0.34</td><td>73.12±0.85</td><td>74.16±0.66</td></tr><tr><td>10</td><td>67.55±0.89</td><td>70.63±0.48</td><td>72.51±0.75</td><td>72.38±0.67</td><td>73.76±0.38</td></tr><tr><td>15</td><td>64.52±1.11</td><td>69.02±1.09</td><td>72.03±1.11</td><td>71.75±1.54</td><td>73.52±0.81</td></tr><tr><td>20</td><td>62.03±3.49</td><td>61.04±1.52</td><td>70.02±2.28</td><td>69.37±1.50</td><td>73.41±1.23</td></tr><tr><td rowspan="5">PubMed</td><td>0</td><td>87.19±0.09</td><td>83.73±0.40</td><td>87.33±0.18</td><td>87.59.±0.10</td><td>87.91±0.23</td></tr><tr><td>5</td><td>83.09±0.13</td><td>78.00±0.44</td><td>87.25±0.09</td><td>86.79±0.12</td><td>87.87±0.14</td></tr><tr><td>10</td><td>81.21±0.09</td><td>74.93±0.38</td><td>87.25±0.09</td><td>86.01±0.10</td><td>87.76±0.13</td></tr><tr><td>15</td><td>78.66±0.12</td><td>71.13±0.51</td><td>87.20±0.09</td><td>85.49±0.11</td><td>87.55±0.11</td></tr><tr><td>20</td><td>77.35±0.19</td><td>68.21±0.96</td><td>87.15±0.15</td><td>85.37±0.12</td><td>87.41±0.15</td></tr></table></body></html>

从表2的结果可以看出，在扰动率为0时，VDERG在Cora、Citeseer和PubMed数据集上的模型准确率分别在目前最优模型的基础上提升了 $0 . 8 4 \%$ 、 $1 . 2 5 \%$ 和 $0 . 3 2 \%$ ，说明VDERGE通过集成节点属性特征和结构特征能够更全面地学习到图数据蕴涵的信息，并且通过非鲁棒特征进行对抗训练不仅能够提升模型鲁棒性，还能提升模型在干净数据集上的表现。

针对扰动率为 $5 \%$ 至 $20 \%$ 的情况，VDERG在三个数据集上都比现有最优模型取得了更高的准确率，扰动率的提升并没有使VDERG像原始GCN那样在准确率上产生明显的下降。在扰动率提升的过程中，相较其他方法，VDERG的模型准确率下降更为缓慢，表现出了更强的鲁棒性。同现其他分类器相比，VDERG在Cora数据集上的表现提升最为明显，当扰动率为 $20 \%$ 时，VDERG的准确率比现有最优模型高了 $6 . 9 1 \%$ 。

# 3.3集成与单一特征学习对比

为了研究集成方法在替身模型表现过程中的有效性，本小节对比在集成过程中仅考虑结构信息或属性信息的模型表现，实验结果如表3所示，图中分别展示了只从结构信息提取非鲁棒特征的VDERG-structure 和只从属性信息提取非鲁棒特征的VDERG-features在数据集Cora和Citeseer上的结果。从表中可以看出，虽然在Cora数据集的原始数据上VDERG的效果略逊于单独考虑结构信息，但在Citeseer数据集上以及受到对抗攻击时，综合考虑了结构信息和属性信息的VDERG都取得了最好的分类效果，说明本文提出的集成策略能够有效提升模型鲁棒性，提高对抗攻击下的图信息表征能力。同时，实验结果表明，仅仅基于结构信息中的非鲁棒特征进行对抗训练比仅基于属性信息的方法效果更好，这是因为基于特征平滑度差异提取非鲁棒特征时可能造成孤立节点的过平滑，而VDERG综合考虑结构信息能够有效弥补这一缺陷。

Tab.2Node classification performance under non-targeted attack (metattack)   
表3结构和属性消融实验对比  
Tab.3The comparison of structure and features ablation   

<html><body><table><tr><td>数据集扰动率/%</td><td>VDERG-structure</td><td>VDERG-features</td><td>VDERG</td></tr><tr><td rowspan="5">0 Cora</td><td>85.51±0.30</td><td>84.48±0.53</td><td>84.26±0.43</td></tr><tr><td>5 83.82±0.75</td><td>83.65±1.21</td><td>83.98±0.63</td></tr><tr><td>10 82.10±0.85</td><td>81.50±1.40</td><td>82.72±1.38</td></tr><tr><td>15 81.69±1.36</td><td>81.37±1.18</td><td>81.70±0.71</td></tr><tr><td>20</td><td>80.19±1.31 80.12±1.02</td><td>80.23±1.21</td></tr><tr><td rowspan="5">0 Citeseer</td><td>74.46±1.06</td><td>74.75±0.71</td><td>75.01±1.09</td></tr><tr><td>5</td><td>73.31±1.04</td><td>73.69±1.84 74.16±0.66</td></tr><tr><td>10</td><td>73.02±0.62 73.02±0.50</td><td>73.76±0.38</td></tr><tr><td>15</td><td>73.34±0.47 72.71±1.57</td><td>73.52±0.81</td></tr><tr><td>20 72.18±0.80</td><td>72.86±0.95</td><td>73.41±1.23</td></tr></table></body></html>

# 3.4模型不同参数对比

对于本文提出的VDERG策略，非鲁棒特征的提取效率至关重要。因此，本小节在 $10 \%$ 扰动率的Metattack攻击下的Cora数据集上，研究分析了结构非鲁棒特征提取过程中的步长 $\alpha$ 和轮数 $N _ { 1 }$ ，以及属性非鲁棒特征提取过程中的步长 $\beta$ 和轮数 $N _ { 2 }$ 对VDERG效果的影响，实验结果如图3所示。本文设定步长 $\alpha$ 和步长 $\beta$ 的变化范围为5e-5到1，轮数 $N _ { 1 }$ 和 $N _ { 2 }$ 的变化范围为1到12。从图3中可以看出，在两种非鲁棒特征提取过程中，模型的性能随着迭代轮数的变化呈现先上升后下降的趋势，对于结构信息的特征提取，最佳轮数为7；在迭代轮数为8至11时，属性信息特征提取随迭代轮数变化的曲线波动更明显，同样在轮数为7时取得最好模型效果，迭代轮数达到11后模型性能开始显著下降。此外，图中还可以看出模型在两种非鲁棒特征提取过程中随步长的改变有着相似的变化趋势，都呈现先上升后下降的形势，结构非鲁棒特征提取的最佳迭代步长为5e-5，属性非鲁棒特征提取的最佳迭代步长为5e-4。

![](images/b887be9359cca4ae2e8df1c03edffb8b4bd8d422dfa598ab747c1a343b9260f2.jpg)  
图3Cora数据集上的参数分析结果图  
Fig.3Results of parameter analysis on Cora dataset

# 4 结束语

本文针对图卷积神经网络提出了一种基于非鲁棒特征的集成对抗训练策略。通过从图卷积层后的嵌入向量中提取非鲁棒特征进行对抗训练，能够绕开直接构造对抗样本时面临的数据离散等问题。为了充分利用图数据信息，本文提出的策略分别从拓扑结构和节点属性两方面的信息出发，借助随机图分别提取输入图中蕴涵的非鲁棒特征，利用非鲁棒特征对两个子模型分别进行对抗训练，并最终集成两个子模型得到的嵌入向量，得到节点预测分类。在引文网络上的实验证明，在Cora、Citeseer、PubMed原始数据集上，该策略较目前最优模型分别提升了 $0 . 8 4 \% , 1 . 2 5 \%$ 和 $0 . 3 2 \%$ 的准确率；Cora数据集上，面对 $20 \%$ 扰动率的对抗攻击时，能够比现有最优模型提升 $6 . 9 1 \%$ 的准确率，以上实验结果充分证明了本文提出的策略能够提升模型在干净数据和攻击图上的节点分类任务表现。

通过对比集成模型与单一特征学习模型的实验结果可以看出，不论是在原始数据集上还是在攻击情景下，集成结构拓扑和节点属性的策略都比单从一个方面进行对抗训练的模型效果更好。

在接下来的工作中，本文计划针对包含较多孤立节点的数据集提升非鲁棒特征的提取效果，研究其他图神经网络模型结构对非鲁棒特征的敏感度以及学习表现，更深入探索图数据中的非鲁棒特征与对抗攻击间的关系。

# 参考文献：

[1]Zügner D,Akbarnejad A,Ginnemann S.Adversarial attacks on neural networks for graph data [C]// Proc of the 24th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York:ACMPress,2018:2847-2856.   
[2]Dai Hanjun,Li Hui,Tian Tian,et al.Adversarial attack on graph structured data [C]// Proc of the 35th International Conference on Machine Learning.[S.1.]:PMLR Press,2018:1115-1124.   
[3]Goodfellow I J,Shlens J，Szegedy C.Explaining and harnessing

adversarial examples [C]//Proc of the 6th ICLR,2015.

4979.   
[5] Kariyappa S,Qureshi M K. Improving adversarial robustness of ensembles with diversity training [EB/OL].(2019-01-28)[2022-01-04]. https://arxiv. org/pdf/1901. 09981.   
[6]Wu Xuguang,Wu Huijun, Zhou Xu,et al. CoG: a two-view co-training framework for defending adversarial attacks on graph [EB/OL]. (2021- 9-12) [2022-01-04]. https://arxiv. org/pdf/2109.05558.   
[7]Sun Lichao,Dou Yingtong,Yang C,et al.Adversarial attack and defense ongraph data:A survey [EB/OL]. (2020-07-12） [2022-01-04]. https://arxiv. org/pdf/1812.10528.   
[8]Dai Quanyu, Shen Xiao,Zhang Liang，et al.Adversarial training methods for network embedding [C]//Proc of WWW Conference.New York: ACM Press,2019: 329-339.   
[9]Perozzi B,Al-Rfou R, Skiena S. Deepwalk: Online learning of social representations [C]// Proc of the 20th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York:ACM Press,2014: 701-710.   
[10]Feng Fuli,He Xiangnan,Tang Jie,et al. Graph adversarial training: Dynamically regularizing based on graph structure [J]. IEEE Trans on Knowledge and Data Engineering,2019,33 (6): 2493-2504   
[11] Wang Xiaoyun,Liu Xuanqing, Hsieh CJ. GraphDefense: Towards robust graph convolutional networks [EB/OL]. (2019-11-11） [2022-01-04]. https://arxiv.org/pdf/1911.04429.   
[12] Ilyas A, Santurkar S,Tsipras D,et al. Adversarial examples are not bugs, they are features [J].Advances in Neural Information Processing Systems,2019,32: 125-136.   
[13] Tramer F,Papernot N,Goodfellow I,et al.The space of transferable adversarial examples [EB/OL].(2017-05-23)[2022-01-04]. htps://arxiv. org/pdf/1704. 03453.   
[14]张嘉杰，过弋，王家辉，等．基于特征和结构信息增强的图神经网络 集成学习框架[J/OL].计算机应用研究,2021,39(3).(2021-12-07) [2022-01-04].https://www.arocmag.com/article/02-2022-03-033.html. (Zhang Jiajie,Guo Yi,Wang Jiahui,et al.Ensemble learning framework for graph neural netword with feature and structure enhancement [J/OL]. Application Reasearch ofComputers,2021,39 (3).(2021-12-07)[2022- 01-04l.https://ww.aromag.cm/article/2-0-030.html.)   
[15] Yang Huanrui, Zhang Jingyang,Dong Hongliang,et al.DVERGE: diversifying vulnerabilities for enhanced robust generation of ensembles [J].Advances in Neural Information Processing Systems, 2020,33: 5505-5515.   
[16] Garg S,Sharan V, Zhang B H,et al.A spectral view of adversarially robust features [J].Advances in Neural Information Processing Systems, 2018,31: 10159-10169.   
[17] Jin Wei, Ma Yao,Liu Xiaorui,etal. Graph structure learning for robust graph neural networks[C]// Proc of the 26th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM Press,2020: 66-74.   
[18] Zügner D, Ginemann S. Adversarial attacks on graph neural networks via meta learning [EB/OL]. (2019-02-22)[2022-01-04]. htps://arxiv. org/pdf/1902. 08412.   
[19] Kipf T N,Weling M. Semi-supervised classification with graph convolutionalnetworks[EB/OL].(2017-02-22）[2022-01-04]. https://arxiv.org/pdf/1609.02907.   
[20] Velickovic P, Cucurull G,Casanova A,et al. Graph attention networks

[C]//Proc of the 6th ICLR,2018. [21] Jin Wei,Derr T,Wang Yiqi,et al.Node similarity preserving graph convolutional networks [C]// Proc of the 14th ACM International

Conference on Web Search and Data Mining.New York:ACM Press, 2021:148-156.