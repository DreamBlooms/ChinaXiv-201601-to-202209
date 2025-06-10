# 基于图注意力网络的开源社区问题解决参与者推荐

赵海燕1,2,3，夏文宗1,2,3†，曹健4，陈庆奎1,2,3(1.上海市现代光学系统重点实验室，上海 20093;2.光学仪器与系统教育部工程研究中心，上海 200093;3．上海理工大学光电信息与计算机工程学院，上海 200093;4.上海交通大学 计算机科学与技术系，上海 200030)

摘要：在开源社区中，开发者提出的问题能否得到快速与高质量的答复和解决决定着社区的活跃程度。因此，为新提交的问题寻找和推荐合适的问题解决参与者有助于社区的发展。根据开发者之间的协作关系记录与开发者参与问题的记录构建了双层图注意力网络的问题解决参与者推荐模型(GAT-UCG)。首先获取问题参与者的信息和开发者的互动信息，分别构建开发者问题参与图和开发者协作关系图，通过注意力机制对于边重新分配权重，最后根据输出层得到的问题节点嵌入表示进行问题参与者的Top-N推荐。选取了Github流行仓库中的7352个问题进行了实验，实验结果表明，所提出的GAT-UCG模型在推荐准确率、召回率、F-Score三个指标上均优于基线方法。

关键词：推荐系统；问题跟踪；图注意力网络；参与者推荐；评论网络中图分类号：TP183 doi:10.19734/j.issn.1001-3695.2022.01.0028

# Graph attention network based participant recommendation for issue resolution in open source community

Zhao Haiyan1,2,3, Xia Wenzong1,2,3t, Cao Jian4, Chen Qingkui1,2, 3 (1.Shanghai Key Labof Modern Optical System,Shanghai 200093,China;2.Engineering Research CenterofOptical Instrument& System，Ministryof Education,Shanghai 20093,China;3.Scholof Optical-Electrical&Computer Engineering,UniversityofShanghaiforScience&Technologyhanghai2oo93,China;4.Dept.ofComputerScience& Technology,Shanghai Jiao Tong University,Shanghai 20o030,China)

Abstract: IntheOpen SourceCommunity,it's essential tofindandrecommendsuitableparticipants fornewlyinitiatedissues in order to solved the isses and develop the community.This paper proposed to construct a two-layer Graph Atention Network Participant Recommendation Model (GAT-UCG) based on the cooperative relationship records and the historical participated issues records of the developers.The methodused to construct the model is obtaining the informationof the problemparticipantsandthe interactioninformationof thedevelopers first,and building thedeveloperproblemparticipation graphandthedevelopercolaborationrelationshipgraphrespectively,thenredistributingthe weights totheedgesthroughthe atention mechanism,finally,figuring theTop-Nrecommendationofthe problem participantsaccording tothe Issue node embeddng representation obtained by theoutput layer.There are 7，352 issues from popular Github repositories for experiments.The results showedthatthe GAT-UCG model outperforms the baseline method inthree indicators: recommendation accuracy,recall,and F-Score.

Key words: recommendation system;issue tracking;graphatentionnetwork; participantrecommendation; commentnetwork

# 0 引言

在现代开源软件开发过程中，开源社区为开源软件的开发者们提供了一个高效的合作平台，例如，Github作为全球最大的开源社区平台，吸引了世界各地的开发者参与开发。

为了让开发者更便捷的进行开源项目的交流，每个人都可以在开源社区中创建问题，而问题的参与者包括项目开发团队的核心成员或是对该问题感兴趣的外部贡献者。在开源社区中，经常会有大量的问题等待开发者进行回复和解决[]。将推荐技术应用到开源社区的问题解决过程中，为每个问题推荐问题解决过程的参与者，能有助于提高问题解决的速度与质量，进而促进社区的协作与发展[2.3]。

近年来，许多学者提出了不同的方法，这些方法从开发者画像、开发者过去解决问题的特征，待解决问题的特征[4,5]等方面进行问题参与者的推荐。

Zhou等人采用结构方程模型(SEM)分析发现，在开源社区中社会认同是决定开源社区用户知识贡献的主要因素[6]；Morris等人研究发现许多问题都是被联系紧密的朋友解决的，并且联系的紧密程度影响着开发者参与问题的积极性[7,8]。所以将开发者之间的协作关系纳入推荐模型，其结果有助于提升开发者知识贡献的意愿，从而更好、更快的解决问题[9,10]，目前的推荐模型大多根据开发者的专业技能等信息进行推荐，部分工作中虽然考虑了问题提出者与开发者之间的关系，但是这些模型中考虑的是直接社交关系的影响[11,12]，没有能够反映社交关系对开发者参与积极性产生的潜在的、复杂的作用，所以本文设计了一个基于图注意力网络的问题参与者推荐模型，引入用户协作关系图以提升推荐的效果。

本文的主要工作如下：根据开源社区开发者协作的特点，将开发者协作关系信息和开发者问题参与信息与图注意力网络相结合，构造了一个双层图注意力网络模型，其中包括开发者协作关系图和开发者问题参与图。本文在Github上的流行仓库[13]中选取了7352个问题进行了实验。实验结果表明，本文提出的GAT-UCG 模型在推荐准确率、召回率、F-Score三个指标上均优于基线方法。

# 1 相关工作

近些年来，有许多学者对于问题参与者推荐进行了研究Jiang等人提出了一种基于多属性的推荐评论者方法，将开发者的活跃度与文本相似度等因素纳入考虑，发现开发者的活跃度是问题参与者推荐最重要的属性[14]。Chen 等人设计了一个回答者推荐系统，有针对性的将问题推荐给有专业知识、能够回答该问题的开发者，并且他们发现，对问题进行及时的处理可以促进问题提问者与回答者之间的互动，使问题的回答者更积极地改进他的回答[15]。Davoodi 等人提出的基于混合方法的专家推荐系统，使用基于社交网络的协同过滤方法来提升参与者预测的准确率[16]。Xu 提出一种基于社交网络并使用矩阵分解技术的新推荐方法，以缓解推荐系统稀疏性的问题并提高模型在复杂内容下的准确率和多样性[17]。刘晔晖等人提出一种基于信息索引、评论网络及熵值法的混合推荐算法，其混合方法相比其独立的方法有着更好的性能[]。

由于传统的推荐系统存在泛化能力差、表达能力不足并且难以处理非欧几里德空间数据等问题[18\~20]。近些年来，能够处理非欧几里德空间数据的图神经网络在挖掘复杂网络的隐藏特征等任务上取得了巨大的成功[2I]。针对基于图神经网络(GNN)的推荐算法，Kipf等人提出了一种半监督图卷积算法(GCN)，利用图的拓扑结构和节点的信息进行标签分类[22]。Zhang等人提出一种基于图神经网络的启发式链路预测方法，从局部子图中学习启发式，并保持着很好的泛化性能[23]。Zhang等人提出了基于图卷积神经网络(GCN)的用户表示学习推荐方法，通过多层的图卷积层进行用户的表示学习[24]。虽然图卷积神经网络(GCN)能够很好的表示节点的特征，但GCN内推式(Transductive)的性质并不适合开源软件快速迭代的特点。为了提升GCN扩展性，Hamilton等人提出了GraphSAGE模型，有效的提升了模型的灵活性和泛化能力[25]但在实际情况中，不同的开发者对于问题的贡献程度是不同的，需要对于开发者节点之间的边给予重要性的表示。Velickovic等人提出基于注意力模型的图神经网络(GAT)，通过引入注意力机制来使模型能够根据邻居节点特征的不同来为其分配不同的权值[26]。针对图神经网络模型的改进方法，Tao等人提出了一种基于多模型的图注意力推荐算法，使用GNNs从不同的模型中获取用户的偏好[27]。Fan 等人提出一种用于社交推荐的图神经网络架构(GraphRec)，使用注意力机制区分社交关系的重要性[28]。Guo 等人提出一种基于深度图神经网络的社交推荐框架(GNN-SoR),将用户与项目的特征抽象为两个图，通过图神经网络进行编码并将编码嵌入至矩阵分解的两个潜在因子中，以完成用户-项目评分矩阵中缺失的评分值[29]。Wang等人使用不同的聚类函数来处理用户的邻居并使用注意力机制生成用户项目的表示[30]。

在本文的模型中，首先利用开源社区问题解决过程中的用户评论数据，来构建开发者的特征，之后利用图注意力机制学习开发者邻居节点的权重并进行节点特征的传播。问题的标签可以直接的体现提问者的主题和疑问所对应的模块，所以将问题标签的One-Hot编码作为问题节点的特征进行问题参与者的推荐。与目前的其他模型相比，本文的模型对协作关系进行了更为全面的融合。

# 2 基于图注意力网络的问题参与者推荐

本文首先对于开源社区中评论数据进行分析，验证了开发者之间的协作关系在问题解决的过程中起着重要的作用。为了充分的挖掘开发者协作网络，本文根据开发者之间的评论信息与开发者参与问题的记录，设计了一个双层图注意力模型(GAT-UCG)，模型的整体结构如图1所示。

![](images/eec4035aacb40916690d66acbba961aa380d90a6e4242a0dbadf642438fa924f.jpg)  
图1 GAT-UCG整体结构图  
Fig.1Overall Architecture of GAT-UCG

# 2.1社交关系对于开发者参与问题解决的重要性

为了验证开源社区中历史合作过的关系在新问题讨论中出现的比例，本文在Github上选取了两个流行仓库tensorflow和kubernetes 的数据进行分析。

首先在仓库中选取特定时间段内的Issue作为源数据，并根据月份划定每月用户社交数据并以第一个月的数据为用户社交的基准数据，将后面月份的互动数据与基准互动数据对比，获得当前时间段里用户互动列表中历史上曾互动过的关系的比例，其中本文将曾互动过的行为定义为用户双方曾在同一个Issue中进行过评论行为，分析结果如表1所示。

表1tensorflow、Kubernetes 仓库中社交关系统计表

Tab.1Statistics of social relationships of tensorflow and Kubernetes   

<html><body><table><tr><td>Repo</td><td>time bucket</td><td>interaction</td><td>interaction in historical</td><td>historical proportion</td></tr><tr><td rowspan="4">tensorflow</td><td>3/22/2020-4/30/2020</td><td>5354</td><td></td><td></td></tr><tr><td>4/30/2020-5/31/2020</td><td>2434</td><td>526</td><td>21.61%</td></tr><tr><td>5/31/2020-6/30/2020</td><td>1576</td><td>402</td><td>25.50%</td></tr><tr><td>6/30/2020-7/31/2020</td><td>1474</td><td>438</td><td>29.71%</td></tr><tr><td rowspan="8">kubernetes</td><td>12/28/2020-1/31/2021</td><td>4724</td><td></td><td></td></tr><tr><td>1/31/2021-2/28/2021</td><td>3812</td><td>1902</td><td>49.89%</td></tr><tr><td>2/28/2021-3/31/2021</td><td>4756</td><td>2744</td><td>57.69%</td></tr><tr><td>3/31/2021-4/30/2021</td><td>2968</td><td>1824</td><td>62.06%</td></tr><tr><td>4/30/2021-5/31/2021</td><td>2482</td><td>1592</td><td>64.14%</td></tr><tr><td>5/31/2021-6/30/2021</td><td>2044</td><td>1420</td><td>69.47%</td></tr><tr><td>6/30/2021-7/30/2021</td><td>1278</td><td>864</td><td>67.60%</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

从表1可以看出，在kubernetes仓库中，在以一个月为间隔的时间段内，平均曾互动过的比例占该月总互动数目的$6 1 . 8 0 \%$ ，在tensorflow社区中也存在一定比例的历史互动。分析结果表明，开发者与曾互动过的人一起参与新问题的讨论这一现象十分普遍，并且随着时间的推进，这一比例稳步升高，体现出开发者之间的协作网络逐渐扩大，所以将开发者之间的历史合作信息纳入考虑有助于提升问题参与者推荐模型的性能。

# 2.2多注意力头的图注意力层

多注意力头的图注意力层作为GAT-UCG模型的基本单元，其基本结构如图2所示。该层的输入数据为一组节点特征， $\pmb { P } = \left\{ \overrightarrow { p _ { 1 } } , \overrightarrow { p _ { 2 } } , \overrightarrow { p _ { 3 } } , . . . , \overrightarrow { p _ { N } } \right\} , \overrightarrow { p _ { i } } \in \mathbb { R } ^ { F }$ ,其中 $N$ 代表节点的数量， $F$ 代表每个节点特征的数目。每一层模型的输出为一组节点的新特征，$\pmb { P } ^ { \prime } = \{ \overrightarrow { p _ { 1 } } ^ { \prime } , \overrightarrow { p _ { 2 } } ^ { \prime } , \overrightarrow { p _ { 3 } } ^ { \prime } , . . . , \overrightarrow { p _ { N } } ^ { \prime } \} , \overrightarrow { p _ { i } } ^ { \prime } \in \mathbb { R } ^ { F ^ { \prime } }$ 。为了充分的将输入特征转换为高阶的嵌入表示，在每个图注意力层中，在节点的计算中引入自注意力(self-attention)机制，输入特征的计算如式(1)(2)所示。

$$
\begin{array} { r } { e _ { i j } = L e a k y R e L U \left( a ^ { T } \left[ W _ { P _ { i } } \left. W _ { P _ { j } } \right. \right] \right) } \end{array}
$$

$$
\alpha _ { i j } = s o f t m a x _ { j } \left( e _ { i j } \right) = \frac { \exp \left( e _ { i j } \right) } { \sum _ { k \in \mathcal { N } _ { i } } \exp \left( e _ { i k } \right) }
$$

其中， $\textbf { \em P }$ 为输入的嵌入表示， $\pmb { W } \in \mathbb { R } ^ { F ^ { \prime } \times F }$ 为权重矩阵， $\mathcal { N } _ { i }$ 为图$G$ 中节点 $i$ 的一阶邻居。

所以，注意力层输出的嵌入表示 ${ \pmb P } ^ { \prime } \in \mathbb { R } ^ { N ^ { \ast } F ^ { \prime } }$ 计算公式如式(3)所示。

$$
\overrightarrow { p _ { i } } = \sigma \Bigg ( \sum _ { j \in N _ { i } } \alpha _ { i j } W \vec { p } _ { j } \Bigg )
$$

其中i,j属于图 $\sigma$ ，图 $G$ 为输入图， $\sigma$ 为非线性的激活函数。

为了能够获得稳定的自注意力(self-attention)结果，采用$K$ 个独立的注意力头进行计算，之后将它们的计算结果进行串联，其中在最后一层，为了减少输出特征向量的维度，将拼接操作替换为平均操作，如式(4)(5)所示。

$$
\overrightarrow { p _ { i } } = \Bigr | \Bigr | _ { k = 1 } ^ { K } \sigma \biggl ( \sum _ { j \in N _ { i } } \alpha _ { i j } ^ { k } W ^ { k } \vec { p } _ { j } \biggr )
$$

$$
\overrightarrow { p _ { i } } = \sigma \Bigg ( \frac { 1 } { K } \sum _ { k = 1 } ^ { K } \sum _ { j \in N _ { i } } \alpha _ { i j } ^ { k } W ^ { k } \vec { p } _ { j } \Bigg )
$$

其中， $\parallel$ 表示将特征进行串联操作， $\kappa$ 代表多注意力头的数目， $\alpha _ { i j } ^ { k }$ 代表由第 $k$ 个注意力头计算的注意力系数， $\mathbf { \Delta } _ { W ^ { k } }$ 代表对应输入的线性变换权重矩阵。使用多注意力机制可将注意力分配到中心节点与邻居节点之间的相关特征上，可使模型的学习能力更强。

![](images/f392a38766950771f52c7a770e6920bf7c99b183e751f5f672985073b1a5a2af.jpg)  
Fig.2Graph attention network architecture

# 2.3开发者协作图的权重传播

开发者协作图层主要负责进行开发者之间权重传播。本文将用户协作图定义为一个带权重的有向图$G _ { D C } = \langle V _ { D } , E _ { D } , W _ { D } \rangle$ ，其中节点 $\boldsymbol { V } _ { D }$ 表示开发者集合，节点之间的关系集合用边 $E _ { D }$ 表示，如果开发者 $V _ { D i }$ 至少评论或引用了开发者 $V _ { D j }$ 提交的一个问题或回复，那么从开发者 $V _ { D i }$ 到开发者$V _ { D j }$ 之间就会有一条边 $\boldsymbol { e } _ { i j }$ 。本文通过正则表达式来提取文本中的 $@$ 行为、引用他人评论等行为，获得开发者之间的协作关系。权重集合 $W$ 反映了边的重要程度，本文通过图注意力机制来进行边的权重进行学习，使用 $\alpha _ { i j }$ 表示 $V _ { D i } , V _ { D j }$ 之间边的权重。开发者节点的嵌入表示通过该开发者历史参与问题的标签进行Multi-hot编码得到。开发者协作图注意力机制的输出如式(6)所示。

$$
\overrightarrow { p _ { D i } } = \sigma \Bigg ( \sum _ { j \in \mathcal { N } _ { D i } } \frac { \exp ( L e a k y R e L U ( a ^ { T } [ W _ { p _ { D i } }  W _ { p _ { D j } } ] ) ) } { \sum _ { k \in \mathcal { N } _ { D i } } \exp ( L e a k y R e L U ( a ^ { T } [ W _ { p _ { D i } }  W _ { p _ { D k } } ] ) ) } W \vec { p } _ { D j } \Bigg )
$$

其中， $\pmb { p } _ { D i } , \pmb { p } _ { D j }$ 分别表示开发者节点 $i , j$ 的嵌入表示， $\mathcal { N } _ { D i }$ 为开发者节点 $i$ 的一阶邻居节点。

图3显示了开发者协作图中的一部分示例，如开发者 $p _ { D 4 }$ 与开发者 $p _ { D 5 }$ 存在协作关系，因此 $p _ { D 4 }$ 到 $p _ { D 5 }$ 有一条边,其权重为α45。

# 2.4开发者-问题参与图的权重传播

本文将开发者-问题参与图定义为 $G _ { I D } = \langle V _ { I } , V _ { D } , E _ { I - D } , W _ { I - D } \rangle$ ，该图为二分图。其中顶点 $V _ { I }$ 表示问题集合，顶点 $V _ { D }$ 表示开发者集合，问题节点与开发者节点之间的关系集合用边 $E _ { \scriptscriptstyle { I - D } }$ 表示，如果开发者 $V _ { D i }$ 至少评论了问题 $V _ { I j }$ 一次，那么从 $V _ { D i }$ 到 $V _ { I j }$ 就会有一条边 $e _ { i j }$ 。权重集合 $W$ 反映了边的重要程度，本文通过注意力机制来对开发者与问题之间边的权重进行学习，使用 $\alpha _ { i j }$ 表示 $V _ { D i } , V _ { I j }$ 之间边的权重大小。开发者-问题参与图注意力机制的输出如式(7)所示。

$$
\overrightarrow { p _ { I } } = \sigma \Bigg ( \sum _ { D \in \cal N _ { d } } \frac { \exp \bigl ( L e a k y R e L U ( a ^ { T } [ W _ { p _ { i } }  W _ { p _ { D } } ] ) ) } { \sum _ { k \ll N _ { d } } \exp \bigl ( L e a k y R e L U ( a ^ { T } [ W _ { p _ { i } }  W _ { p _ { k } } ] ) \bigr ) } W \vec { p } _ { D } \Bigg )
$$

其中， $\pmb { p } _ { b }$ 为开发者节点的嵌入表示， $\pmb { p } _ { i }$ 为问题节点的嵌入表示， $\mathcal { N } _ { d }$ 为问题节点的一阶邻居节点。

图4显示了开发者-问题参与图中的一部分示例，如开发者 $p _ { D 1 } , p _ { D 2 } , p _ { D 3 }$ ，参与了问题 $p _ { I 1 }$ 的讨论，因此 $p _ { D 1 } , p _ { D 2 } , p _ { D 3 }$ 到 $p _ { I 1 }$ 分别有一条边，其分别为 $\alpha _ { 1 1 } , \alpha _ { 2 1 } , \alpha _ { 3 1 }$ 。

![](images/5e3c1f031170fd4b4f29f5e56d5641849a2272215ff367ce5ebbeb02c21ae37b.jpg)  
图2图注意力网络结构  
图3开发者协作关系图示例

![](images/7c5e80fab62423e7b383a8c2955b01f082dcb79f8b9085f728968b34b777c449.jpg)  
Fig.3An example of developer cooperation graph   
图4开发者-问题参与图示例  
Fig.4An example of Developer-Issue participation graph

# 2.5模型预测和优化

为了学习模型参数，使模型可以更好的建模问题与开发者之间的特征。本文采用LogSoftmax进行问题解决参与者的预测，预测层输出如式(8)所示。

$$
p _ { i } = \log \left( \frac { \exp ( a _ { i } ) } { \sum _ { k = 1 } ^ { C } \exp ( a _ { k } ) } \right)
$$

其中， $\pmb { a } _ { 1 } , \pmb { a } _ { 2 } , \pmb { a } _ { 3 } , . . . , \pmb { a } _ { C }$ 是问题节点I的特征， $p _ { i }$ 为该问题节点I应该被分配给开发者 $i$ 的概率，通过上式可以获得该问题节点I分配给每个开发者的概率，根据概率的高低进行排序，推荐Top-N的问题解决参与者。使用LogSoftmax 能够加快模型运算的速度，提高数据的稳定性。模型采用梯度下降法训练更新模型参数。

# 3 数据及实验

# 3.1问题及用户评论数据

本文在Github上选择了两个流行仓库(tensorflow、kubernetes)作为实验数据。通过GithubAPI获得了仓库特定时间段内的Issue信息，包含Issue的标签以及所有参与该问题的用户信息，共获取了7352条Issue以及58814条评论行为，数据集见表2。

表2tensorflow、kubernetes 数据集  
Tab.2Datasets of tensorflow and kubernetes   

<html><body><table><tr><td>Repo</td><td colspan="4">issue comment developer label attributes</td><td>time bucket</td></tr><tr><td>tensorflow 2459</td><td></td><td>13067</td><td>497</td><td>79</td><td>3/22/2020-7/28/2020</td></tr><tr><td>kubernetes 4893</td><td></td><td>45747</td><td>896</td><td>121</td><td>12/28/2020-7/30/2021</td></tr></table></body></html>

# 3.2评测指标

为了验证算法的性能，采用召回率、精确率和F-Score作为评价的指标，推荐结果的召回率计算方式如式(9)所示。

$$
R e c a l l = \frac { \sum _ { i = 1 } ^ { | I s s u e _ { s } | } | R ( i ) \bigcap T ( i ) | } { \sum _ { i = 1 } ^ { | I s s u e _ { s } | } | T ( i ) | }
$$

推荐结果的精确率计算方式如式(10)所示。

$$
P r e c i s i o n { = } \frac { \sum _ { i = 1 } ^ { | I s s u e _ { s } | } \lvert R ( i ) \bigcap T ( i ) \rvert } { \sum _ { i = 1 } ^ { | I s s u e _ { s } | } \lvert R ( i ) \rvert }
$$

推荐结果的F-score值计算方式如式(11)所示。

$$
F - s c o r e = 2 * \frac { p r e c i s i o n * r e c a l l } { p r e c i s i o n + r e c a l l }
$$

其中 $I s s u e _ { s }$ 表示问题的测试集, $\boldsymbol { R } ( i )$ 表示根据开发者在训练集上的行为作出的Top-N推荐列表, $\begin{array} { r } { T ( i ) } \end{array}$ 表示实际参与问题的用户列表。

# 3.3实验设置

本文在Python3.8，Pytorch1.9.0，Cuda11.4，RTX3090 环境下完成GAT-UCG与基线算法的对比实验。在实验中，按照8:1:1的比例划分数据集来构造训练集、验证集和测试集；GAT-UCG模型超参数的设置如表3所示。将模型默认的训练轮次(epochs)设置为2000，并且当验证集上的评测指标在100轮内没有变化时提前结束训练。基线方法GAT和GCN中的嵌入维度、学习率、批处理大小和注意力头数目与GATUCG模型相同，其他超参数默认与原始论文或代码一致。实验目标是为测试集中的每个问题推荐排名靠前的N个开发者，并使用Recall@N、Precision $\mathbf { \Delta } _ { \mathcal { Q } \mathrm { N } }$ 、F-Score@N 三个指标来衡量各模型的性能。

表3模型的超参数设置  
Tab.3Hyperparameter setting of model   

<html><body><table><tr><td>超参数名称</td><td>参数值</td></tr><tr><td></td><td>问题、开发者嵌入维度237(tensorflow 社区)/363(kubernetes 社区)</td></tr><tr><td>学习率</td><td>0.005</td></tr><tr><td>隐藏层数目</td><td>8</td></tr><tr><td>注意力头数目</td><td>8</td></tr><tr><td>Drop out Rate</td><td>0.6</td></tr><tr><td>L2正则项系数</td><td>5e-4</td></tr></table></body></html>

# 3.4消融实验

为了评估图注意力层中多注意力头的有效性以及贡献，本节进行了消融实验分析了单注意力头与多注意力头。根据统计，在本文选取的两个流行仓库中， $9 9 . 7 9 \%$ 的问题参与人数在10位及以下，所以将推荐的列表长度限制在10人以内进行 Top-N的问题参与者推荐的召回率评估，结果如表4所示。

为了更加清晰的显示性能的差别，将表4转换成图5的形式。消融实验结果显示，基于多注意力头的图注意力网络模型相比基于单注意力头的图注意力网络模型在tensorflow和kubernetes两个仓库的问题参与者Top-N的推荐召回率平均提高 $8 . 5 7 \%$ ，表明基于多注意力头的图注意力模型相比基于单注意力头的图注意力网络模型能稳定传播邻居节点信息并且提升模型的推荐性能。

withdifferent numbersofheads   

<html><body><table><tr><td>Repo</td><td>attention head</td><td>2</td><td>4</td><td>6</td><td>8</td><td>10</td></tr><tr><td rowspan="2">tensorflow</td><td>Multi</td><td></td><td>39.67% 48.29% 52.85% 55.59% 58.89%</td><td></td><td></td><td></td></tr><tr><td>Single</td><td></td><td>27.66% 39.07% 44.43% 46.82% 51.78%</td><td></td><td></td><td></td></tr><tr><td rowspan="2">kubernetes</td><td>Multi</td><td></td><td>45.01% 56.16% 61.18% 64.05% 66.04%</td><td></td><td></td><td></td></tr><tr><td>Single</td><td></td><td>34.55% 46.35% 53.29% 57.29% 60.77%</td><td></td><td></td><td></td></tr></table></body></html>

![](images/cf7c8b8def61f9f3cad8152c382c8812cdfb88dad904d894c7f354633dd7a810.jpg)  
图5单、多注意力头模型Top-N推荐的召回率 Fig.5Recall rate ofTop-N recommendations of single and multi-head attention models

# 3.5实验结果

根据消融实验的结果，本文将多注意力头的机制应用到GAT-UCG 模型中，本文比较了不同的方法在推荐Top-2、Top4、Top-6、Top-8、Top-10个参与者时的推荐性能，实验结果如表5\~7所示。

在表5\~7中，第一行是本文所提出的基于开发者协作图和问题参与图的双层图注意力网络(GAT-UCG)模型。第二行是图注意力网络(GAT)模型[26]。第三行是图卷积神经网络(GCN)模型[22]。第四行是基于开发者社交网络的用户画像模型(SN)[I]。第五行是基于矩阵分解的协同过滤模型(MF)[17]。

表4不同注意力头数Top-N推荐的召回率Tab.4Recall rate of Top-N recommendations  
表5不同算法Top-N推荐的召回率  
Tab.5Recall rate of Top-N recommendations of different methods   

<html><body><table><tr><td>Repo</td><td>baseline</td><td>2</td><td>4</td><td>6</td><td>8</td><td>10</td></tr><tr><td rowspan="5">tensorflow</td><td>GAT-UCG</td><td>39.67%</td><td>48.29%</td><td>52.85%</td><td>55.59%</td><td>58.89%</td></tr><tr><td>GAT</td><td>16.14%</td><td>28.32%</td><td>36.80%</td><td>43.65%</td><td>45.92%</td></tr><tr><td>GCN</td><td>11.63%</td><td>20.68%</td><td>28.28%</td><td>33.36%</td><td>36.68%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>22.69%</td><td>26.10%</td><td>28.93%</td><td>30.54%</td><td>31.39%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>5.11%</td><td>14.82%</td><td>21.45%</td><td>24.82%</td><td>25.52%</td></tr><tr><td rowspan="5">kubernetes</td><td>GAT-UCG</td><td>45.01%</td><td>56.16%</td><td>61.18%</td><td>64.05%</td><td>66.04%</td></tr><tr><td>GAT</td><td>28.70%</td><td>39.59%</td><td>45.27%</td><td>49.10%</td><td>51.27%</td></tr><tr><td>GCN</td><td>12.18%</td><td>22.17%</td><td>29.11%</td><td>35.21%</td><td>37.27%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>18.04%</td><td>21.08%</td><td>23.41%</td><td>25.58%</td><td>26.22%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>4.22%</td><td>8.31%</td><td>12.08%</td><td>14.98%</td><td>17.13%</td></tr></table></body></html>

Tab.6Precision rate of Top-N recommendations of different methods   

<html><body><table><tr><td>Repo</td><td>baseline</td><td>2</td><td>4</td><td>6</td><td>8</td><td>10</td></tr><tr><td rowspan="5">tensorflow</td><td>GAT-UCG</td><td>39.80%</td><td>24.22%</td><td>17.62%</td><td>13.94%</td><td>11.42%</td></tr><tr><td>GAT</td><td>16.20%</td><td>14.23%</td><td>12.30%</td><td>10.95%</td><td>9.21%</td></tr><tr><td>GCN</td><td>11.67%</td><td>10.37%</td><td>9.45%</td><td>8.36%</td><td>7.36%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>25.39%</td><td>14.07%</td><td>9.90%</td><td>7.57%</td><td>6.10%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>12.84%</td><td>12.56%</td><td>10.78%</td><td>8.93%</td><td>8.87%</td></tr><tr><td rowspan="5">kubernetes</td><td>GAT-UCG</td><td>53.05%</td><td>33.10%</td><td>23.86%</td><td>18.71%</td><td>15.42%</td></tr><tr><td>GAT</td><td>33.30%</td><td>22.97%</td><td>17.51%</td><td>14.24%</td><td>11.90%</td></tr><tr><td>GCN</td><td>14.13%</td><td>12.86%</td><td>11.26%</td><td>10.21%</td><td>8.65%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>18.92%</td><td>12.30%</td><td>8.61%</td><td>6.74%</td><td>4.74%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>8.41%</td><td>8.21%</td><td>7.95%</td><td>7.42%</td><td>6.64%</td></tr></table></body></html>

表7不同算法Top-N 推荐的F-score

表6不同算法 Top-N推荐的精确率  
Tab.7F-scores of Top-N recommendations of different methods   

<html><body><table><tr><td>Repo</td><td>baseline</td><td>2</td><td>4</td><td>6</td><td>8</td><td>10</td></tr><tr><td rowspan="5">tensorflow</td><td>GAT-UCG</td><td>39.73%</td><td>32.26%</td><td>26.43%</td><td>22.30%</td><td>19.02%</td></tr><tr><td>GAT</td><td>16.17%</td><td>18.94%</td><td>18.43%</td><td>17.51%</td><td>15.34%</td></tr><tr><td>GCN</td><td>11.64%</td><td>13.81%</td><td>14.16%</td><td>13.36%</td><td>12.26%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>23.96%</td><td>18.28%</td><td>14.75%</td><td>12.13%</td><td>10.22%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>7.31%</td><td>13.59%</td><td>14.34%</td><td>13.13%</td><td>13.16%</td></tr><tr><td rowspan="5">kubernetes</td><td>GAT-UCG</td><td>48.70%</td><td>41.65%</td><td>34.33%</td><td>28.96%</td><td>25.01%</td></tr><tr><td>GAT</td><td>30.82%</td><td>29.25%</td><td>25.25%</td><td>22.08%</td><td>19.32%</td></tr><tr><td>GCN</td><td>13.08%</td><td>16.27%</td><td>16.24%</td><td>15.82%</td><td>14.04%</td></tr><tr><td>基于社交网络的用户画像(SN)</td><td>18.47%</td><td>15.54%</td><td>12.59%</td><td>10.67%</td><td>8.03%</td></tr><tr><td>基于矩阵分解的协同过滤算法(MF)</td><td>5.62%</td><td>8.26%</td><td>9.59%</td><td>9.92%</td><td>9.57%</td></tr></table></body></html>

# 3.6结果分析

为了直观地表示结果，分别将表5\~7转换成图6\~8的形式。实验结果显示，本文所提出的GAT-UCG推荐模型在实验的两个仓库上的推荐效果都比对比的四个算法的效果要好。其中，在tensorflow仓库上，本文所提出的方法召回率最多提升了 $3 9 . 6 1 \%$ ，在kubernetes仓库上，召回率最多提升了 $54 . 6 1 \%$ 。

![](images/3c77492333b8282877aa2107bb908b3d5c228cd533379c7d9858ad56abcf2a07.jpg)  
图6不同方法下参与者推荐召回率比较  
Fig.6Comparisons of recall rate of different methods for participant recommendation

![](images/442678f5c368bf792ac87f3ad1a84a6111562d828c0b22a842d9bc8ffa311020.jpg)  
图7不同方法下参与者推荐精确率比较 Fig.7Comparisons of precision rate of different methods for participant recommendation

比较所提出的模型和数据集的不同结果，有以下的观察和结论：

(1)基于图神经网络的模型在大部分实验结果上要优于基于矩阵分解和基于社交网络的传统模型。这说明图神经网络模型能够很好的挖掘开发者协作关系和兴趣偏好的特征。

(2)在基于图神经网络的模型中，将开发者协作信息与开发者-Issue 参与信息进行综合考虑相比于只利用开发者-Issue参与信息的模型可以获得更好的问题参与者推荐性能。

(3)比较两个实验数据集上的实验效果，图神经网络模型在kubernetes仓库的数据上收到了最优的效果，kubernetes仓库有更多的用户数目、互动数和标签特征数，这表明图的内容越丰富，嵌入向量的信息越多，实验效果越好。因此，当将所提出的模型应用于更大的数据集时，其效果更加明显。(4)基于社交网络的用户画像模型在tensorflow仓库上Top-2的推荐效果相比于基于图注意力网络的推荐效果更好：是由于tensorflow仓库参与人员更为固定并且标签类型更少导致基于社交网络能在推荐人数较少的情况下效果更好。此情况在参与人数更多、标签更丰富的kubermetes仓库中并不明显。实验结果显示，在 tensorflow 仓库中，从Top-4开始，图注意力网络模型的推荐性能开始超过基于社交网络的用户画像模型，说明图神经网络模型能更好的适应复杂的情况。

![](images/b307117e757f74ca3844bb7d50bc3cc98725ff3e42c82a455069b19d0eaa8a6f.jpg)  
图8不同方法下参与者推荐F-score 比较Fig.8Comparisons ofF-scores of different methods forparticipant recommendation

# 4结束语

本文通过深入分析已有的问题参与者推荐方法，提出了一种基于图注意力网络的问题解决参与者推荐模型并详细描述了设计的模型。本文选取了Github上流行仓库的数据进行实验，使用Precision、Recall和F-Score 作为模型的评估指标，将本文所提出的推荐模型与GAT、GCN、SN和MF 进行对比，实验结果表明本文提出的推荐模型在数据集上的指标均优于基线算法，可以有效的推荐问题参与者。同时，本文的模型引入了开发者之间的协作关系，可以更好的根据开发者的社交关系进行推荐。

本文的工作还有不少可拓展的地方，例如在本文中选取问题的标签作为问题的描述特征，然而，在实际中还有许多问题来不及打标签或者标签不全等问题。在未来的工作中，可以考虑将更多的问题特征纳入考虑，以提高问题参与者推荐模型的性能。

# 奓考乂：

[1] 刘晔晖，赵海燕，曹健，陈庆奎．开源社区中 Issue 解决过程的参与 者推荐方法[J].小型微型计算机系统，2020,41(09):1930-1934. (Liu Ye-hui, Zhao Hai-yan,Cao Jian,et al.Participants recommendation approaches for issue solving process in open source community [J]. Journal of Chinese Computer Systems,2020,41(9):1930-1934.)   
[2] MARLOW J, DABBISH L,HERBSLEB J. Impression formation in online peer production: Activity traces and personal profiles in github [C]//Proceedings of the 20l3 Conference on Computer Supported Cooperative Work (CSCW'13).New York,NY,USA,2013:117-128.   
[3]TSAY J,DABBISH L,HERBSLEB J. Influence of social andtechnical factors for evaluating contribution in github[C]//Proceedings ofthe 36th International Conference on Software Engineering (ICSE 2014). New York,NY,USA,2014: 356-366.   
[4] Yeh R T,Ramamoorthy C V. Proceedings of the 2nd international conference on softw are engineering [J]. Scientific American,1976,172 (4): 297-301.   
[5]MontandonJE,Silva LL, Valente MT.Identifying experts in softw are libraries and framew orks among Git Hub users [C]//Proceedings of the 16th International Conference on M ining Softw are Repositories,IEEE Press, 2019: 276-287.   
[6]周涛，王超．开源软件社区用户知识贡献行为研究[J].科研管理， 2020，41 (02):202-209.(Zhou Tao，Wang Chao.A research on knowledge contribution behaviors of open source software community users [J]. Science Research Management, 2020,41 (02): 202-209.)   
[7]Morris MR,Teevan J,Panovich K.A comparison of information seeking using search engines and social networks [Cl// Fourth International AAAI Conference on Weblogs and Social Media. 2010.   
[8]White R W, Richardson M,Liu Y.Effects of community size and contact rate in synchronous social Q&A [Cl// Proceedings of the SIGCHI Conference on Human Factors in Computing Systems. 2011: 2837-2846.   
[9]Alami A,Dittrich Y, WasowskiA. Influencers of quality assurance in an open source community [C]// 2018 IEEE/ACM 11th International Workshop on Cooperative and Human Aspects of Software Engineering (CHASE).IEEE,2018:61-68.   
[10] SOWE S K, STAMELOS I,ANGELIS L. Understandin g know-ledge sharing activities in free/open source software projects: An empirical study[J]. Journal of Systems and Software,2008,3 (81): 431-446.   
[11] Wang H,Wang T,Yin G,et al.Linking issue tracker with Q&Asites for know ledge sharing across communities [J]. IEEE Transactions on Services Computing,2015,11 (5): 782-795.   
[12] Guo L,Chen Q,Han W,et al. Collaborative topic prediction model for user interest recommendation in online social netw orks [J]. International Journal of Digital Content Technology&its Applic,2012,6 (23): 62-73.   
[13]王伟，周添一，赵生宇，范家宽．全球开源生态发展现状研究[J]. 信息通信技术与政策,2020(05):38-44.(Wang Wei,Zhou Tianyi,Zhao Shengyu,Fan Jiakuan. Research on the development of global open source ecology[J].Science Research Management, 2020,41 (02): 202- 209.)   
[14] Jiang J，Yang Y,He J，et al.Who should comment on this pull request?analyzingattributesformoreaccuratecommenter recommendation in pul-based development [J]. Information and Software Technology,2017,84: 48-62.   
[15] Chen T,Cai J,Wang H,et al. Instant expert hunting: building an answerer recommender system for a large scale Q&A website [C]/ Proceedings of the 29th Annual ACM Symposium on Applied Computing. 2014: 260-265.   
[16] Davoodi E,Afsharchi M, Kianmehr K.Asocial network-based approach to expert recommendation system $[ \mathrm { C } ] / \hbar$ International conference on hybrid artificial intelligence systems.Springer,Berlin,Heidelberg,2012: 91-102.   
[17] Xu C.A novel recommendation method based on social network using matrixfactorizationtechnique[J].Informationprocessing& management,2018,54(3):463-474.   
[18]程龙，李涵．基于矩阵分解的推荐算法研究综述[J]．北京信息科技 大学学报（自然科学版），2021,36(02):38-45+51.(ChengLong,Li Han.A review of recommendation algorithms based on matrix factorization [J]. Journal of Beijing Information Science & Technology University,2021,36 (02): 38-45+51.)   
[19]秦川，祝恒书，庄福振，等．基于知识图谱的推荐系统研究综述[J]. 中国科学：信息科学，2020，50(07):937-956.(QinChuan，Zhu Hengshu,Zhuang Fuzhen，et.A survey on knowledge graph-based recommender systems [J]. Scientia Sinica (Informationis),2020,50 (07): 937-956.)   
[20]周万珍，曹迪，许云峰，刘滨．推荐系统研究综述[J].河北科技大 学学报,2020,41(01):76-87.(Zhou Wanzhen,Cao Di,Xu Yunfeng,Liu Bin.A survey of recommendation systems [J].Journal of Hebei University of Science and Technology,2020,41 (01): 76-87.s)   
[21] Wu Z,Pan S,Chen F,et al.A comprehensive survey on graph neural networks [J].IEEE transactions on neural networks and learning systems, 2020,32 (1): 4-24.   
[22] Kipf T N,Welling M.Semi-supervised classification with graph convolutional networks [J].arXiv preprint arXiv:1609.02907,2016.   
[23] Zhang M, Chen Y.Link prediction based on graph neural networks [J]. Advances in Neural Information Processing Systems,2018,31:5165- 5175.   
[24] Zhang S,Yin H, Chen T,et al. Gcn-based user representation learning for unifying robust recommendation and fraudster detection [C]// Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval.2020: 689-698.   
[25] Hamilton WL,Ying R,Leskovec J. Inductive representation learning on large graphs [C]//Proceedings of the 31st International Conference on Neural Information Processing Systems.2017:1025-1035.   
[26] Velickovic P,Cucurull G,Casanova A,et al.Graph attention networks [J].arXiv preprint arXiv:1710.10903,2017.   
[27] Tao Z,WeiY,WangX,et al.MGAT: multimodal graph attention network for recommendation [J]. Information Processing & Management,2020, 57 (5): 102277.   
[28] Fan W,Ma Y,Li Q，et al.Graph neural networks for social recommendation [C]//The World Wide Web Conference.2019: 417-426.   
[29] Guo Z,Wang H.A deep graph neural network-based mechanism for social recommendations [J].IEEE Transactions on Industrial Informatics, 2020,17(4):2776-2783.   
[30]Wang J,Xie H,WangFL,et al.Top-N personalized recommendation with graph neural networks in MOOCs[J].Computers and Education: Artificial Intelligence,2021,2:10001