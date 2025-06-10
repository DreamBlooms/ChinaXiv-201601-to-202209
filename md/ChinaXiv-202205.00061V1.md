# 基于时空信息和任务流行度分析的移动群智感知任务推荐

杨桂松‘a，王静茹la，李俊²，何杏宇b

(1.上海理工大学a.光电信息与计算机工程学院;b.出版印刷与艺术设计学院，上海 200093;2.国家工业信息安全发展研究中心，北京 100040)

摘要：现有移动群智感知任务推荐的共同缺点是：一方面，未充分考虑时空信息对工人偏好的影响，导致推荐准确性低；另一方面，忽略任务流行度对推荐的影响，导致推荐覆盖率差。为解决这些问题，本文提出一种基于时空信息和任务流行度分析的移动群智感知任务推荐方法。首先，充分利用工人执行记录中的相关信息(如工人执行任务的时间、位置)，准确预测工人对任务的偏好。其次，基于工人声誉和任务执行情况分析任务流行度并设计任务流行度惩罚因子，提升推荐效果的覆盖率。然后，结合工人偏好和流行度惩罚因子生成任务推荐列表。实验结果表明，与现有基线方法相比，所提出方法在推荐准确率上平均提升了 $3 . 5 \%$ ，推荐覆盖率上平均提高了 $2 5 \%$ 。

关键词：移动群智感知；任务推荐；时空信息；流行度偏差；任务流行度 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2022.01.0046

# Task recommendation based on spatial-temporal information and task popularity analysis in mobile crowd sensing

Yang Guisongla, Wang Jingrula, Li $\mathrm { J u n } ^ { 2 }$ ,He Xingyulbt (1.a.SchoolofOptical-Electrical& Computer Engineering,b.ColegeofCommunication&Art Design,Universityof Shanghai for Science&Technologyhanghai2Oo93,China;2.National Industrial Information Security evelopment Research Center,Beijing 100040, China)

Abstract:The drawbacks of existingtask recommendation in mobile crowdsensing were as follows:ontheone hand,not fully considering the influence ofspatial-temporal information on worker preference ledtolowaccuracyofrecommendation; Onthe otherhand,ignoringthe impactoftask popularityonrecommendationledtopoorrecommendationcoverage.To solve thesedrawbacks,this paper proposedanoveltask recommendationapproach based on spatial-temporal informationand task popularityanalysis in mobile crowd sensing.Firstly,this approach made fulluseoftherelevant information contained in the worker execution record (e.g.，the time and location of worker performing tasks）to accurately predict the preference of worker forperforming tasks.Secondly,inorder toreduce theimpactofpopular asks onrecommendationcoverage,this paper analyzed task popularity based on worker reputation and task execution record,and designed appropriate task popularity penalty factor.Then,combining worker preferenceand task popularitypenaltyfactor,this paper providedanappropriate task recommendation listforeach worker.Finall,the experimentalresultsshowthatcompared withthe existingbaseline methods, the proposed method improves the recommendation accuracy by $3 . 5 \%$ and the recommendation coverage by $2 5 \%$ ：

Key words: mobile crowd sensing; task recommendation; spatial-temporal information; popularitybias; task popularity

# 0 引言

移动群智感知(Mobile crowd sensing,MCS)[1]是一种具有广阔前景的感知模式，已广泛应用于很多领域，例如环境监测[2]、健康数据收集[3]、工业控制管理[4]、地质勘测[5]和交通规划[等。典型的移动群智感知系统由任务发布方、任务完成方(工人)和MCS平台三部分组成。其工作流程如下：任务发布方将任务请求发布在MCS平台，MCS平台根据接收到的任务请求为工人建立任务列表，工人从列表中选择任务去执行，并将感知数据上传至MCS平台，MCS平台最终将感知数据反馈给任务发布方。在这个过程中，工人选择任务的可能性受工人偏好的影响。因此，如何挖掘工人偏好，向工人推荐最有可能执行的任务列表尤为重要。任务推荐的效率和质量不仅会影响工人的执行意愿，也会影响任务的感知质量。

现有研究倾向于使用单一模型来学习工人偏好[7]，进而实现任务推荐。例如，基于工人相似性或者任务相似性[8-10]的任务推荐方法、基于逻辑回归模型的方法[11,12]。这些方法都需要提前制定影响工人偏好的因素，但是在移动群智感知中，影响工人偏好的因素众多，很难提前制定所有因素。为解决这个问题，一些研究开始将推荐系统[13]应用到移动群智感知领域的任务推荐，从工人的历史执行记录中预测工人偏好。例如，文献[14,15]利用矩阵分解模型预测工人偏好，并依据偏好为工人生成任务推荐列表。文献[16]提出一种基于特征的贝叶斯任务推荐方法，通过任务类别来学习任务的潜在特征，解决新任务冷启动情况下的任务推荐问题。文献[17]综合考虑每个工人的偏好和可靠性实现任务推荐。

上述方法未充分考虑工人偏好的时空变化，这会影响推荐准确度。一方面，工人的偏好随着时间动态变化，工人近期的任务选择更能代表工人目前的偏好，另一方面，移动群智感知中的任务分布在不同的感知区域，工人需要移动到感知区域地点去执行任务，出于自身成本角度考虑，工人更倾向于执行距离自己较近位置的任务。尽管文献[18]利用张量分解模型实现基于工人位置的任务推荐，但是受到工人流动性的影响[19]，该模型需要频繁更新来适应工人的位置变化，导致不能及时捕捉工人新的偏好。因此，如何结合工人时空信息来准确预测工人偏好是一大挑战。

另外，现有移动群智感知任务推荐研究忽略了任务流行度对推荐效果的影响，这会产生流行度偏差问题[20]，造成任务推荐覆盖率下降。例如，市区的交通流量监测等流行任务可能会因为其执行简单而受到大量工人喜欢，如果平台为这些工人都推荐该任务，会产生感知数据冗余，而诸如山区地质水平测量等冷门任务则可能因为没得到足够的推广而收集不到充足的样本导致任务失败。一般情况下，推荐系统领域中任务的流行程度由执行该任务的工人比例决定，比例越高，则任务流行度越高[21]。在移动群智感知系统中，工人具有从众心理，容易受到其他工人的影响而去执行某个任务，导致任务的流行度发生变化。因此，任务流行度和工人声誉关系密切，声誉越高的工人对其他工人的影响更大，进而对任务流行度的影响也就更大。因此，基于工人声誉和任务执行情况分析任务的流行度，设计合理的流行度惩罚因子，提高任务推荐覆盖率，是另一个挑战。

针对上述挑战，本文提出基于时空信息和流行度分析的移动群智感知任务推荐方法(TimeMatrixFactorization andBidirectionalLong Short-TermMemory,TimeMF-BiLSTM)，该方法综合考虑工人偏好和任务流行度惩罚因子为工人推荐任务列表，保证任务推荐的准确度和覆盖率。本文的主要贡献如下：

a）使用融合时间因素的矩阵分解模型从工人历史执行数据中学习工人和任务的隐含关系，再利用双向长短期记忆网络模型从工人的轨迹信息中提取工人的位置偏好信息，将两个模型得到的偏好融合得到精确度更高的任务推荐。

b)引入社交网络计算工人声誉，提出一种基于工人声誉信息的任务流行度计算方法，实现对任务流行度更精确分析，并设计合理的任务流行度惩罚因子，保证任务推荐的覆盖率。

# 1 系统模型

图1展示了TimeMF-BiLSTM任务推荐方法的整体架构。该方法先使用融合时间因素的矩阵分解模型(TimeMatrixFactorization，TimeMF)从工人执行记录中学习工人和任务的隐含关系(即工人潜在特征向量和任务潜在特征)，得出工人对任务的偏好(记为TimeMF偏好评分)，解决工人偏好随时间动态改变的问题；再使用双向长短期记忆网络(BidirectionalLongShort-TermMemory,BiLSTM)从工人 GPS轨迹序列中学习其下一时刻可能到达的位置，并基于任务与该位置之间的距离得到工人偏好(记为BiLSTM偏好评分)，解决工人偏好随着工人位置动态改变的问题；然后，将TimeMF 模型学习到的工人偏好和BiLSTM模型学习到的工人偏好使用逻辑回归方法融合在一起，综合得到工人的偏好评分，保证任务推荐的准确性；此外，引入社交网络计算工人声誉，并根据任务执行情况分析工人之间的影响因子，结合工人声誉和工人影响因子计算任务流行度，构造与任务流行度负相关的惩罚因子；使用流行度惩罚因子和工人偏好相乘得到工人对任务的最终评分，解决由于任务流行度偏差造成的感知数据覆盖不平衡问题。在此基础上，将工人对任务的最终评分从高到低进行排序，为每一个工人生成TopN任务推荐列表。

本文使用的主要参数描述如下： $m$ 个工人的集合表示为$\mathbb { U } = \{ u _ { 1 } , u _ { 2 } , . . . , u _ { m } \}$ ， $n$ 个任务的集合表示为 $\mathbb { V } = \left\{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { n } \right\}$ ，每个工人的执行记录表示为 $\mathbb { H } _ { u _ { i } }$ ， $\mathbb { H } _ { u _ { i } }$ 包含工人 $u _ { i }$ 执行的所有任务，每个任务的执行情况表示为 $\mathbb { F } _ { \nu _ { j } }$ ， $\mathbb { F } _ { \nu _ { j } }$ 包括执行任务 $\nu _ { j }$ 的所有工人ID 编号， $\mathbb { L } _ { u _ { i } } = \{ ( t _ { 1 } , l _ { 1 } ) , ( t _ { 2 } , l _ { 2 } ) , . . . , ( t _ { s } , l _ { s } ) , . . . \}$ 表示工人 $u _ { i }$ 的GPS轨迹序列， $l _ { s }$ 是由经度和纬度组成的二元组，代表工人 $u _ { i }$ 在时刻 $t _ { s }$ 时的位置。本文提出一种有效的方法来精确计算工人和任务之间的评分矩阵 $\boldsymbol { \mathsf { Y } }$ ，为每个工人生成TopN任务推荐列表，目标是最大化任务推荐的准确率和覆盖率，任务推荐列表的长度 $N$ 由平台根据实际情况设置。

人偏好预测  
1 工人执 计算 初始工人任 TimeMF模 工人潜在特 任务潜在 评分 TimeMF偏  
1 行记录 务评分矩阵 型学习 征矩阵 特征矩阵 生成 好评分  
二二工人GPS 轨迹 完整工人GPS 轨迹 工人下一 任务相似 BiLSTM 偏好 工人轨迹序列 填充 轨迹序列 预测 时刻位置 性计算 偏好评分 融合 偏好任务流行度惩罚因子设计 7工人相似性计算 I I任务核行系 工人餐子 计算 任流 设计 任流行度工人声誉信息统计 二二11任务推荐列表生成二二工人偏好 计算 工人任务最 降序 有序工人任务最 提取每一行 工人任务推 1任务流行度 终评分矩阵 排列 终评分矩阵 前N个评分 荐列表 ====二

Fig.1Task recommendationbasedonspatial-temporal informationand popularityanalysis in mobile crowd sensing

# 2 工人偏好预测

# 2.1融入时间因素的矩阵分解

为解决工人偏好随时间动态改变的问题，使用TimeMF模型学习工人偏好。TimeMF模型通过不断迭代学习工人潜在特征向量 $\boldsymbol { \mathbf { \mathit { v } } }$ 和任务潜在特征向量 $V$ ，并利用两者乘积预测工人任务评分矩阵 $M P$ ，即将原始工人任务评分矩阵 $M P$ 中的零值补全。TimeMF模型主要包含三个部分：a)初始工人任务评分矩阵构建。根据工人执行记录构建原始工人任务评分矩阵，并考虑时间因素对工人偏好的影响；b)TimeMF 模型学习。根据原始工人任务评分矩阵，采用合适的算法对任务潜在特征进行迭代更新，并最终达到一个最优解，使得工人潜在特征向量和任务潜在特征向量的乘积逼近原始工人任务评分矩阵；c)

偏好评分生成。根据上一阶段最终得到的工人潜在特征向量和任务潜在特征向量，实现工人对任务的评分预测。

# 2.1.1初始工人任务评分矩阵构建

工人对任务的评分表示工人对该任务的偏好，由于MCS平台中很少要求工人对任务有显式的评分，因此本文使用工人执行任务的次数来代替工人对任务的评分，工人 $u _ { i }$ 执行任务 $\nu _ { j }$ 以用三元组 $\left\{ u _ { i } , \nu _ { j } , t _ { i j } \right\}$ 来表示， $t _ { i j }$ 是工人 $u _ { i }$ 执行任务 $\nu _ { j }$ 的时刻。若工人 $u _ { i }$ 时刻 $t _ { i j }$ 执行任务 $\nu _ { j }$ ，则表示工人 $u _ { i }$ 对任务 $\nu _ { j }$ 感兴趣， $\left\{ u _ { i } , \nu _ { j } , t _ { i j } \right\} = 1$ ，反之，则表明该时刻工人 $\mathbf { \chi } _ { u _ { i } }$ 对任务 $\nu _ { j }$ 不感兴趣， $\left\{ u _ { i } , \nu _ { j } , t _ { i j } \right\} = 0$ 0

考虑到工人偏好的时间动态特性，工人最近一段时间执行的任务更能代表工人的偏好，因此，引入牛顿冷却定律的思想，通过指数衰减函数 $e ^ { - \lambda \left( t - t _ { i j } \right) }$ 使评分信息的权重随时间呈指数衰减。其中， $t$ 是当前时刻， $t _ { i j }$ 是工人 $\mathbf { \chi } _ { u _ { i } }$ 执行任务 $\nu _ { j }$ 的时刻， $\lambda$ 是时间衰减因子， $\lambda > 0$ ，且 $\lambda$ 越大，历史偏好的重要程度越低。在此基础上，建立工人任务原始评分矩阵 $M P$ $M P$ 中的每一个子元素 $m p _ { i j }$ 通过下式计算：

$$
m p _ { i j } = \sum _ { \nu _ { j } \in \mathbb { H } _ { m } } e ^ { - \lambda ( t - t _ { i j } ) } \left( u _ { i } , \nu _ { j } \right)
$$

# 2.1.2TimeMF模型学习

工人潜在特征向量和任务潜在特征向量用两个 $k$ 维的低秩特征矩阵 $\boldsymbol { \mathbf { \mathit { v } } }$ 和 $\nu$ 表示， $U \in \mathbb { R } ^ { m \times k }$ 的每一行代表一个工人 $u _ { i }$ 的潜在特征向量 $U _ { i }$ ， $V \in \mathbb { R } ^ { n \times k }$ 的每一行代表一个任务 $\nu _ { j }$ 的潜在特征向量 $V _ { j }$ 。 $\pmb { U }$ 和 $V$ 中的值随机初始化。TimeMF模型的训练目标是保证 $M P$ 和原始工人任务评分矩阵 $M P$ 的误差最小。目标函数如式(2)所示。

$$
\begin{array} { l } { { \displaystyle \ a r g m i n d ( U , V ) = \frac 1 2 \sum _ { i , j } c _ { i , j } \left( m p _ { i j } - U _ { i } T _ { j } ^ { T } \right) ^ { 2 } + } } \\ { { \displaystyle \ \left( \frac { \lambda _ { U } } 2 \sum _ { i = 1 } ^ { m } \lVert U _ { i } \rVert _ { F r o } ^ { 2 } + \frac { \lambda _ { V } } 2 \sum _ { j = 1 } ^ { n } \lVert V _ { j } \rVert _ { F r o } ^ { 2 } \right) } } \end{array}
$$

其中, $c _ { i , j }$ 用于指示工人 $u _ { i }$ 对任务 $\nu _ { j }$ 感兴趣的程度， $c _ { i , j } = 1 + \alpha m p _ { i , j }$ ，$\alpha$ 是衰减参数。 $\| \cdot \| _ { F r o } ^ { 2 }$ 表示Frobenius 范数， $\lambda _ { U }$ 和 $\lambda _ { v }$ 是正则化项。式(2)可通过梯度下降方法找到最优解。

# 2.1.3TimeMF偏好评分生成

利用上一阶段最终学习到的工人潜在特征向量 $\pmb { U }$ 和任务潜在特征向量 $V$ ，生成工人对任务的偏好 $M P$ 。偏好生成的公式如下：

$$
\scriptstyle m p _ { i j } = U _ { i } V _ { j } ^ { T }
$$

# 2.2融入空间因素的双向长短期记忆网络

为了克服工人偏好随工人位置动态改变的问题，使用双向长短期记忆网络(Bidirectional Long Short-Term Memory,BiLSTM)学习工人偏好，模型主要包括三个部分：a)轨迹数据处理。即对轨迹序列中的缺失值填充；b)BiLSTM预测。通过工人的GPS轨迹序列预测工人下一时刻可能会到达的位置；c)BiLSTM偏好评分生成。基于上一阶段学习到的工人下一时刻可能到达的位置和平台内任务的距离生成工人任务偏好，

# 2.2.1轨迹数据处理

对于工人轨迹数据中的缺失值，首先依据工人自身轨迹的时空相关性进行填充，例如，工人 $u _ { i }$ 在 $t _ { s }$ 时刻的轨迹信息缺失，则依次检索该时刻的前5个时刻和后5个时刻的轨迹信息，若查找到轨迹信息值，则利用该值填充工人 $\mathbf { \chi } _ { u _ { i } }$ 在 $t _ { s }$ 时刻的轨迹信息 $l _ { s }$ 。

然后，对于工人 $u _ { i }$ 的GPS轨迹序列仍然存在缺失值的每个时刻，比较工人 $u _ { i }$ 与其他工人之间的轨迹相似性，根据其相似工人在该时刻的轨迹信息来填充轨迹，需要注意的是，如果只有一名相似工人在该时刻有轨迹信息，则直接使用该相似工人的轨迹信息填充，如果有多名工人在该时刻都有轨迹信息，则选择相似性最大的工人所在的轨迹信息填充该时刻。

工人 $u _ { i }$ 和工人 $\boldsymbol { u _ { w } }$ 的轨迹相似性通过下式计算：

$$
L S _ { i w } = \sum _ { t _ { s } \subseteq \mathbb { L } _ { u _ { i } } } \xi _ { t _ { s } } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right)
$$

其中， $\xi _ { s } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right)$ 表示 $t _ { s }$ 时刻工人 $u _ { i }$ 和工人 $\boldsymbol { u } _ { \boldsymbol { w } }$ 轨迹位置的相似性，由下式得到：

$$
\xi _ { t _ { s } } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right) = \left\{ { 1 \atop 0 } \right. , \ : d \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right) \leq \varepsilon
$$

$d \big ( l _ { s } ^ { i } , l _ { s } ^ { w } \big )$ 表示 $t _ { s }$ 时刻工人 $u _ { i }$ 和工人 $\boldsymbol { u } _ { \boldsymbol { w } }$ 的距离，若两个工人之间的位置距离小于等于 $\varepsilon$ ，认为这两个位置相似，记$\xi _ { t _ { s } } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right) = 1$ ，否则， $\xi _ { t _ { s } } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right) = 0$ 。 $\varepsilon$ 的值由平台设定。

# 2.2.2BiLSTM预测

由于BiLSTM模型中输入序列长度必须相同，因此在BiLSTM模型中引入了滑动窗口方法，时间窗口的大小通过实验指定。工人的轨迹序列首先被转换成固定长度的输入和输出

样本集，然后用这些固定长度的样本集来训练BiLSTM模型。

BiLSTM模型总共5层：a)输入层；b)嵌入层；c)BiLSTM层；d)Dropout层；e)输出层。

a）输入层：工人任务轨迹序列 $\mathbb { L } _ { u _ { i } } = \{ ( t _ { I } , l _ { I } ) , ( t _ { 2 } , l _ { 2 } ) , . . . , ( t _ { s } , l _ { s } ) , . . . \}$ v

b）嵌入层：通过WordEmbedding的思想对工人的GPS序列信息进行嵌入，得到序列嵌入向量 $x _ { I D }$ 。

c)BiLSTM层：包含前向LSTM 和后向LSTM两个隐层。将嵌入向量 $x _ { I D }$ 分别输入到两个隐层，得到向量 $h _ { t } = h _ { t } ^ { I } \oplus h _ { \tau } ^ { 2 }$ ，其中， $h _ { \tau } ^ { I }$ 为前向LSTM的输出， $h _ { t } ^ { 2 }$ 为后向LSTM的输出。

d)Dropout层：以预先设定的概率停止神经元的输出，防止模型出现过拟合的问题。

e）输出层：输出工人下一时刻可能到达的位置 $\boldsymbol { l _ { n e x t } }$ 。

# 2.2.3BiLSTM偏好评分生成

接下来，建立工人对平台内所有任务的偏好矩阵 $L P , L P$ 中的每一个子元素 $l p _ { i j }$ 使用欧氏距离得到。

$$
l p _ { i j } = \parallel l _ { v _ { j } } - l _ { n e x t }
$$

其中， $l _ { \nu _ { j } }$ 表示任务 $\nu _ { j }$ 要求的感知位置， $\boldsymbol { l } _ { n e x t }$ 是工人下一时刻可能到达的位置。如果工人下一时刻可能到达的位置 $l _ { n e x t }$ 与任务 $\nu _ { j }$ 距离很近，则工人很有可能执行该任务。

# 2.3偏好融合

将前两个部分的得到的偏好评分 $M P$ 和 $L P$ 使用逻辑回归方法融合，得到工人最终的偏好评分 $P$ ， $P$ 中的每一个子元素 $p _ { i j }$ 通过下式得到：

$$
p _ { i j } = \frac { 1 } { 1 + \exp \left( - \left( m p _ { i j } + l p _ { i j } \right) \right) }
$$

# 3 任务流行度惩罚因子设计

以往计算任务流行度[2I通过下式计算：

$$
p o p _ { j } = \frac { \mathbb { F } _ { \nu _ { j } } } { m }
$$

$\mathbb { F } _ { \nu _ { j } }$ 是 MCS平台内执行任务vj的工人集合， $\mathbf { m }$ 为MCS平台总的工人数量。popj是任务vj的流行度值。

然而，这种方法视不同工人对任务流行度的影响是同质的，其结果存在误差。在移动群智感知平台中，任务的流行度与工人声誉有很大关系。一方面，MCS平台中的工人具有从众心理，工人执行任务的意愿容易收到其他工人的影响，并且，声誉较高的工人在某一时刻执行某个任务的话，则下一时刻容易吸引更多的工人去执行该任务，导致该任务下一时刻的流行度激增。显然，按照以往的做法，即出于覆盖率保证的角度考虑，根据时刻 $t$ 的流行度情况，在 $t { + } l$ 时刻提升任务的评分，是不合理的。因此，本文引入工人声誉的计算，帮助更好地衡量下一时刻的任务流行情况。

首先，计算工人之间的影响因子 $I N$ 矩阵，即不同工人之间相互影响的难易程度，以工人 $u _ { i }$ 和工人 $\boldsymbol { u } _ { \boldsymbol { w } }$ 为例，二者之间的影响因子 $i n _ { i w }$

$$
i n _ { i w } = \frac { \left| \mathbb { H } _ { u _ { i } } \cap \mathbb { H } _ { u _ { w } } \right| } { \left| \mathbb { H } _ { u _ { i } } \cap \mathbb { H } _ { u _ { w } } \right| }
$$

其中， $\mathbb { H } _ { u _ { i } }$ 和 $\mathbb { H } _ { u _ { w } }$ 分别表示工人 $u _ { i }$ 和工人 $u _ { w }$ 执行过的任务集合，若两个工人所做的共同任务数量越多，则表明两个工人的亲密程度越高，两个工人之间也就更容易互相影响。

然后，引入社交网络来计算工人在移动群智感知平台的声誉，建立工人声誉矩阵 $\pmb { W P }$ 。工人声誉可以通过其他工人的点赞数、评论数量以及工人之间的朋友关系等多种社会关系来度量。

工人 $u _ { i }$ 的声誉对任务 $\nu _ { j }$ 的流行度影响可以表示为

$$
p c _ { i j } = w p _ { i } * \sum _ { u _ { w } \subseteq \mathbb { U } _ { - i } } i n _ { i w }
$$

其中， $\mathbb { U } _ { - i } = \left\{ u _ { 1 } , u _ { 2 } , . . . u _ { i - 1 } , u _ { i + 1 } , . . . u _ { m } \right\}$ 。因此，任务的流行度重新定

义为

$$
p o p _ { j } = \frac { \mathbb { F } _ { \nu _ { j } } + \sum _ { u _ { i } \subseteq \mathbb { F } _ { \nu _ { j } } } p c _ { i j } } { m }
$$

接下来，对候选任务集合中的任务流行度进行归一化，使 $p o p _ { j }$ 的取值在0-1之间。

$$
p o p _ { j } = \frac { p o p _ { j } - p o p _ { m i n } } { p o p _ { m a x } - p o p _ { m i n } }
$$

其中， $p o p _ { m a x }$ 表示任务集合中所有任务流行度的最大值，$p o p _ { m i n }$ 表示任务集合中所有任务流行度的最小值。

接下来，对MCS平台中每个任务添加流行度惩罚因子，该流行度惩罚因子可以调节任务的推荐权重，以此保证任务推荐的覆盖率，任务 $\nu _ { j }$ 的流行度惩罚因子 $m _ { j }$ 由下式计算：

$$
m _ { j } =
$$

$$
\left\{ \begin{array} { c c l } { 1 } & { , } & { p o p _ { j } < \phi a n d s a m p l e _ { j } < s a s m p l e _ { j } } \\ { 1 - p o p _ { j } } & { , } & { p o p _ { j } \geq \phi a n d s a m p l e _ { j } < s a s m p l e _ { j } } \end{array} \right.
$$

其中，samplej为任务 $\nu _ { j }$ 现在收集到的任务样本数量，sample 为任务 $\nu _ { j }$ 总共所需的样本数量，由任务请求方在发布任务请求时自定义确定。 $\phi$ 的取值为平台内所有任务执行次数的中位数。

# 4 任务推荐列表生成

在任务流行度惩罚因子的基础上，进一步改进工人对任务的预测评分，生成任务推荐列表。工人对任务最终预测评分为

$$
{ \bf y } _ { i j } = p _ { i j } * m _ { j }
$$

$p _ { i j }$ 为融合时空信息计算出的工人偏好， $m _ { j }$ 为任务 $\nu _ { j }$ 的流行度惩罚因子。当 $s a m p l e _ { j } < s a m p l e _ { j }$ 时，表明该任务还没有被执行成功，针对每一个工人，依据预测出来的其对任务的评分矩阵Y，将任务按照降序排列，从中选择前 $N$ 个任务组成任务列表推荐给工人， $N$ 的个数由平台自定义设定。若samplej≥samplej，表示该任务需要的样本数量已经收集完成，则不再向工人推荐该任务，并将该任务从候选任务集合中删除。

基于时空信息和流行度分析的移动群智感知任务推荐方法的具体实现步骤如下：

# 算法1 TimeMF-BiLSTM

输入：工人集合U，任务集合V，每个工人的执行记录 H、任务的执行记录F、每个工人的轨迹记录L、任务所需样本数量 samplej。

输出：工人的任务推荐列表。

a）工人潜在特征向量 $\pmb { \upsilon }$ 和任务潜在特征向量 $\pmb { v }$ 随机初始化。  
b）依据式(1)构建原始工人评分矩阵 $M P$ 。  
c）构建式(2)的损失函数，通过梯度下降训练TimeMF模型；如果损失函数小于阈值，则完成训练，跳到步骤d)；否则跳到步骤 $\mathsf { \Lambda } _ { \mathsf { c } }$ 。d）依据式(3)构建工人的TimeMF 偏好评分矩阵 $M P \ , \ M P$ 中的每一个子元素 $m p _ { i j }$ 表示工人 $u _ { i }$ 对任务 $\boldsymbol { v } _ { j }$ 的TimeMF 偏好。  
e）依据式(5)计算工人 $u _ { i }$ 和工人 $u _ { w }$ 之间的轨迹相似性 $\xi _ { t _ { s } } \left( l _ { s } ^ { i } , l _ { s } ^ { w } \right)$ 。f）遍历工人 $u _ { i }$ 的轨迹记录L，如果 $l _ { s } ^ { i } = 0$ ，使用与工人 $u _ { i }$ 轨迹相似性最大的工人在该时隙的位置填充该时隙；否则跳过该时隙，继续遍历轨迹记录L；  
g）训练BiLSTM 模型，输出工人 $u _ { i }$ 下一时刻可能到达的位置 $\boldsymbol { L _ { n e x t } }$ 。h）依据式(6)计算 $\boldsymbol { L _ { n e x t } }$ 和任务 $\boldsymbol { v } _ { j }$ 的相似性 $\iota _ { P i j }$ ，构建BiLSTM偏好评分矩阵 $\pmb { L P }$ ， $\angle P$ 中的每一个子元素 $\iota _ { P i j }$ 表示工人 $u _ { i }$ 对任务 $\boldsymbol { v } _ { j }$ 的BiLSTM 偏好。  
i）依据式(7)构建工人偏好评分 $\pmb { P } _ { \circ } \pmb { P }$ 中的每一个子元素表示工人 $u _ { i }$ 对任务 $\boldsymbol { v } _ { j }$ 的偏好评分。  
j）依据式(13)构建任务流行度惩罚因子矩阵 $\pmb { M }$ 的每一个子元素 $m _ { j }$ 表示任务 $\boldsymbol { v } _ { j }$ 的流行度惩罚因子。  
k）计算工人最终预测评分矩阵 $\pmb { \gamma }$ ， $\pmb { \gamma }$ 中的每一个子元素 $y _ { i j }$ 依据式(14)计算。  
1）对于每个工人 $u _ { i }$ ，将预测评分矩阵 $\pmb { \gamma }$ 第i行按照 $y _ { i j }$ 大小降序排列，取前 $N$ 个作为给工人 $u _ { i }$ 的任务推荐列表输出；如果任务 $\boldsymbol { v } _ { j }$ 收集

到的样本数量大于sample，则将 $\boldsymbol { v } _ { j }$ 从任务集合V中剔除，转到步骤a)。

为了更直观地展示TimeMF-BiLSTM的任务推荐过程，算法1的流程图如图2所示。该方法首先训练TimeMF模型，得出工人TimeMF偏好评分矩阵 $M P$ ；再对工人轨迹的缺失值填充，输入到BiLSTM模型中，预测工人下一时刻可能到达的位置，基于任务与该位置之间的距离得到工人BiLSTM偏好评分 $_ { L P }$ ；然后，将 $_ { L P }$ 和 $M P$ 的对应元素使用逻辑回归方法融合到一起，综合得到工人的偏好评分 $P$ ；接下来，构造与任务流行度惩罚因子矩阵 $\pmb { M }$ ，并将流行度惩罚因子 $\pmb { M }$ 和工人偏好矩阵 $P$ 相乘得到工人对任务的最终评分Y；最后，对应系统中的每个工人 $u _ { i }$ ，降序排列工人评分矩阵 $\boldsymbol { { \cal Y } }$ 的第 $i$ 行，取评分最大的前 $N$ 个任务作为工人 $u _ { i }$ 的任务推荐列表输出；当任务 $\nu _ { j }$ 收集到的样本数量sample；所需的样本满足要求之后，将该任务从任务集合V中移除，并重新开始模型的训练

开始输入U,V,H,F,L,sample，工人社交网络工人潜在特征向量U和任务潜在特征向量V随机初始化损失小于阈值否是 更新工人潜在特征向量U和任务潜在特征向量V构建TimeMF偏好评分矩阵MP对于每一个工人u∈U，计算工人 $u _ { i }$ 和其他工人 $\boldsymbol { u } _ { \boldsymbol { w } }$ 的轨迹相似性 $\dot { \xi } _ { t _ { S } } \left( \dot { l } _ { s } ^ { i } , \dot { l } _ { s } ^ { w } \right)$ 1香 跳过该对于每一个工人，=0时隙是使用与 $u _ { i }$ 相似性最高的工人 $\boldsymbol { u } _ { \scriptscriptstyle \mathrm { W } }$ 在该时隙的位置填充训练BiLSTM模型，输出 $u _ { i }$ 下一时刻可能到达的位置 $\underline l { l } _ { n e x t } .$ 计算l与 $\nu _ { j }$ 的相似性,构建BiLSTM偏好评分矩阵LP构建任务流行度惩罚构建工人偏好评分P因子矩阵M?计算工人任务最终sample $>$ sample 预测评分矩阵Y香是1对于工人u,∈U，降序排从任务集合V中 列评分矩阵Y第i行，取移除任务 $\boldsymbol { \nu } _ { j }$ （204 其前N个输出结束

# 5 实验分析

# 5.1 数据集

在两个真实数据集Gowalla[23]和 Foursquare[24]上验证所提方法的有效性。所使用数据集的详细信息如下：

a)Gowalla数据集：该数据集包含了196591个用户从2009年8月至2010年9月的签到记录。通过处理，比如删除签到记录低于20次的工人以及任务地点等，最终提取了216245条数据，包括78个工人、117个任务和371个位置。

b)Foursquare 数据集：该数据集包含2153471个用户，1143092个场所，1021970个签到，27098490个社交关系以及用户分配给场所的2809581评分；所有这些都是通过公共API从Foursquare应用程序中提取的。在这个数据集中，首先对数据集做预处理操作，比如删除签到记录低于20次的工人以及任务地点等。最终剩余622841条数据，包括285名工人、105个任务和168个地点。

# 5.2参数设置

实验运行在一台拥有IntelCorei5-10210U处理器，8GBRAM的戴尔笔记本电脑上。操作系统是windows10，编程语言是Python3.6。所使用的主要参数通过表1给出。

Tab.1 Parameter settings   

<html><body><table><tr><td>参数</td><td>取值范围</td><td>参数</td><td>取值范围</td></tr><tr><td>时段T划分</td><td>30min</td><td>学习率α</td><td>[0.001,0.05]</td></tr><tr><td>任务数n</td><td>[20,100]</td><td>正则化参数β</td><td>[0.01,0.9]</td></tr><tr><td>工人数m</td><td>15</td><td>时间窗口t</td><td>20</td></tr><tr><td>潜在特征维度k</td><td>[10,25]</td><td>dropout</td><td>0.2</td></tr></table></body></html>

# 5.3评价准则

a）准确度(Precision)

$$
P r e c i s i o n { } = { } \frac { \sum _ { 1 } ^ { m } \displaystyle \frac { h i t c o u n t _ { i } } { t o t a l r e c o m m e d a t i o n ~ n u m b e r _ { i } } } { m }
$$

其中，hitcounti是工人从任务推荐列表中执行的任务数量，total recommendation numberi代表推荐给工人 $\mathbf { u } _ { \mathrm { i } }$ 的任务数量。

b）归一化折损累计增益(NDCG)

$$
N D C G = { \frac { D C G } { I D C G } }
$$

IDCG是理想条件下的最大 $D C G$ 值。NDCG的值介于(0,1)之间，用来衡量任务推荐列表中的任务顺序是否与工人偏好一致。在MCS平台中，工人最终选择的任务在任务推荐列表中的位置越高，该任务对折损增益的贡献越大，NDCG的值越大，排名结果越好。

$D C G$ 是折损累计增益，由下式得到：

$$
D C G = \sum _ { i = 1 } ^ { b } \frac { 2 ^ { r e l _ { i } } - 1 } { l o g _ { 2 } i + 1 }
$$

其中， $b$ 是任务推荐列表中的任务数量。 ${ r e l } _ { i }$ 代表该列表中第 $i$ 项的相关度，如果工人执行该项任务，则设置为1，否则设置为 $0 _ { \circ }$

c）覆盖率(Coverage)

$$
C o \nu e r a g e = \frac { 1 } { n } \sum _ { j = 1 } ^ { n } ( 2 c - n - 1 ) p o p ( \nu _ { c } )
$$

覆盖率用来描述能够推荐出来得任务占总任务的比例。$p o p ( \nu _ { c } )$ 是按照任务流行度 $p o p$ 从大到小排序的任务集合中的第 $\mathbf { \Psi } _ { c }$ 个任务。

# 5.4对比方法

为了验证TimeMF-BiLSTM方法的有效性，本文将其与6 个基线方法进行比较，用以证明所提出的模型优于其他方法。具体如下所示。

TR-UMCR[8]：该方法使用基于混合用户模型与列表级排序学习算法相结合的协同排序任务推荐方法。

FLTE[11]：该方法利用逻辑回归算法进行任务推荐。

RTRA[14]：该方法仅利用矩阵分解模型学习工人和任务的隐含关系。

PRTR[18]：该方法将工人位置信息和工人偏好结合起来，利用张量分解模型学习工人和任务的关系，忽略工人偏好随时间动态变化的影响。

TCTR[22]：该方法仅融入时间因素考虑工人偏好，忽略工人偏好随位置动态变化的影响。

RLIN：与本文所提出方法TimeMF-BiLSTM不同之处是，将两种模型得到的评分以线性加权的形式融合，比较线性加权

和逻辑回归偏好融合的不同。

# 5.5性能评价

这一节，本文展示与其他基线方法在评估指标上的结果对比。

表2和表3分别给出了TimeMF-BiLSTM任务推荐方法在两个数据集上的精确度效果。从表中可以看出，TimeMF-BiLSTM的精确度远远高于FLTE，这是由于FLTE不考虑工人和任务的隐含关系，导致学习到的工人偏好的准确性很差，说明本文模型更符合MCS任务推荐的实际应用。当推荐列表长度 $N$ 大于15时，能够看到TimeMF-BiLSTM的精度大于TR-UMCR、PRTR以及TCTR算法，说明TimeMF-BiLSTM融合时空因素进行偏好融合，可以更加准确地捕捉工人的偏好。可以发现，TR-UMCR和PRTR算法的效果大致相同，这是由于这两个算法均是采用基本的矩阵分解模型，并且均融入了工人的位置信息来提高推荐效果，这个现象也从侧面反映出，在MCS领域，工人执行任务的意愿与工人位置有很大关系。此外，与RLIN相比，TimeMF-BiLSTM的精确度略高，这是由于本文使用工人的历史执行情况作为工人对任务的评分，即评分数据都是整数，线性回归方法预测出来的分值必须要通过取整操作，这会造成部分误差。随着推荐列表长度$N$ 的上升，TimeMF-BiLSTM的精确度不断上升，在Gowalla数据集上，当推荐列表长度 $L$ 为20时，TimeMF-BiLSTM方法的精确度最终收敛到 $9 4 . 3 \%$ 左右。综上所述，依据TimeMF-BiLSTM方法向工人推荐任务在精确度方面更具有优势。

表2不同推荐长度 $N$ 在Gowalla数据集的推荐精确度

表1参数设置  

<html><body><table><tr><td colspan="5">Gowalla dataset</td></tr><tr><td>方法</td><td>5</td><td>10</td><td>15</td><td>20</td></tr><tr><td>TimeMF-BiLSTM</td><td>32.2%</td><td>59.6%</td><td>88.4%</td><td>94.3%</td></tr><tr><td>TR-UMCR</td><td>36.8%</td><td>58.4%</td><td>82.9%</td><td>90.2%</td></tr><tr><td>FLTE</td><td>21.9%</td><td>30.7%</td><td>64.1%</td><td>70.5%</td></tr><tr><td>RTRA</td><td>25.2%</td><td>38.1%</td><td>73.8%</td><td>82.4%</td></tr><tr><td>TCTR</td><td>39.6%</td><td>59.9%</td><td>78.3%</td><td>88.9%</td></tr><tr><td>PRTR</td><td>37.7%</td><td>60.3%</td><td>80.8%</td><td>87.6%</td></tr><tr><td>RLIN</td><td>30.2%</td><td>58.5%</td><td>82.1%</td><td>91.6%</td></tr></table></body></html>

表3不同推荐长度 $N$ 在Foursquare 数据集上的推荐精确度指标

Tab.2Accuracy of different recommended length N on   
Tab.3Accuracy of different recommended length $N$ on   

<html><body><table><tr><td colspan="5">Foursquare dataset</td></tr><tr><td>方法</td><td>5</td><td>10</td><td>15</td><td>20</td></tr><tr><td>TimeMF-BiLSTM</td><td>33.9%</td><td>57.5%</td><td>78.9%</td><td>92.1%</td></tr><tr><td>TR-UMCR</td><td>27.7%</td><td>57.1%</td><td>77.5%</td><td>89.2%</td></tr><tr><td>FLTE</td><td>21.0%</td><td>25.1%</td><td>57.1%</td><td>63.3%</td></tr><tr><td>RTRA</td><td>25.2%</td><td>33.9%</td><td>70.1%</td><td>78.5%</td></tr><tr><td>TCTR</td><td>20.7%</td><td>43.5%</td><td>77.4%</td><td>89.2%</td></tr><tr><td>PRTR</td><td>37.7%</td><td>60.3%</td><td>84.8%</td><td>85.1%</td></tr><tr><td>RLIN</td><td>31.6%</td><td>53.4%</td><td>81.8%</td><td>89.5%</td></tr></table></body></html>

另外，从表2和表3可以发现，当推荐列表长度低于10时，TimeMF-BiLSTM的精度略小于PRTR，这是因为本文的算法考虑了任务的流行度惩罚，导致推荐的精度稍有降低。为进一步验证该现象，本文从Foursquare 数据集随机抽取特定用户以及其历史执行任务的记录等相关信息作为测试样本。具体来说，本文选择的工人ID号为9号，取任务集合中ID从1至20号任务作为训练集，工人9对这20个任务的真实偏好评分值以及依据本文所提方法对这些任务的预测评分情况如表4所示。从表4可以看出，理论上来讲，依据工人对不同任务的评分高低来生成任务列表，工人9真实最优的任务ID列表应该为[3,4,8,2,6,7,1,5,9,10]。

然后，依据本文所提方法预测工人9对这10项任务的评分，结果显示，所提方法对工人9的预测偏好评分 $P$ 结果在表4展示，可以发现预测偏好评分 $P$ 与工人9的真实评分的均方误差为0.414152，与工人9的真实偏好非常接近，证明本文所提方法在预测工人偏好方面的准确性。但是，如果仅以此作为推荐结果的话，任务2、3、4、8由于较高的评分，工人9下一次的推荐列表前5个位置将全是任务区域 $C _ { 3 }$ 和$C _ { 4 }$ 的任务，这会导致工人9越来越偏爱于任务区域 $C _ { 3 }$ 和 $C _ { 4 }$ 的任务，那么任务区域 $C _ { 3 }$ 和 $C _ { 4 }$ 的任务流行度就会越来越高，而工人9执行任务的总次数是一定的，那么相应地，任务区域 $C _ { I }$ 和 $C _ { 2 }$ 则会由于缺乏足够的推荐而收集不到充分的样本。因此，本文使用流行度惩罚因子，调整流行度过高的任务权重，得到最终的工人任务预测评分矩阵Y，结果在表4展示，可以发现调整之后工人9的最终预测评分 $Y$ 与工人9的真实评分的均方误差稍有提升，但是任务2、3、4、8的推荐权重明显降低，任务区域 $C _ { I }$ 和 $C _ { 2 }$ 区域处于工人下一时刻的任务列表中靠前位置，这对于提升任务推荐的覆盖率是非常有帮助的，这一现象与本文的初衷，也就是适当降低推荐精度，促进推荐效果覆盖率，是非常一致的。而随着推荐列表长度不断增加，也就是说一次性推荐给工人的任务数量不断增加，那么每一次推荐的任务列表所能覆盖的范围就会越来越来，即推荐效果的覆盖率越来越大，此时，为满足覆盖率要求而设置的流行任务的惩罚因子就会越来越小，那么推荐效果的精确度也就会逐渐增加了。

表4样本实例  
Tab.4Sample instance   

<html><body><table><tr><td>任务ID</td><td>真实评分 任务所属区域</td><td>预测偏好评分P</td><td>最终预测评分Y</td></tr><tr><td>1</td><td>2 C1</td><td>2.78933511</td><td>2.78933511</td></tr><tr><td>2</td><td>3 C4</td><td>3.56075737</td><td>1.61037869</td></tr><tr><td>3</td><td>6 C</td><td>5.54626787</td><td>0.00000000</td></tr><tr><td>4</td><td>5 C4</td><td>4.39667412</td><td>0.92437798</td></tr><tr><td>5</td><td>2 C2</td><td>3.09950478</td><td>3.09950478</td></tr><tr><td>6</td><td>3 C4</td><td>3.09983137</td><td>3.09983137</td></tr><tr><td>7</td><td>3 C2</td><td>2.95584221</td><td>2.95584221</td></tr><tr><td>8</td><td>5 C</td><td>4.54064423</td><td>0.75677404</td></tr><tr><td>9</td><td>1 C1</td><td>1.60706052</td><td>1.60706052</td></tr><tr><td>10</td><td>0 C1</td><td>0.63975154</td><td>1.63975154</td></tr></table></body></html>

接下来，将推荐长度 $N$ 设置为20，图3展示TimeMF-BiLSTM与其他基线方法在NGDD指标的性能对比。本文将计算折损累计增益时的参数 $b$ 设置为 $n$ ， $n$ 是MCS平台中的任务数量，由平台当前的候选任务数量决定。可以发现，TimeMF-BiLSTM的NDCG明显高于其他基线方法，并且比逻辑回归方法的NDCG高了将近一倍左右，证明本文的模型评价排序的准确性。

![](images/18fcf7885491f9e908c379c6392388e8733971a5ef2382a36b395476e3d786ad.jpg)  
图3NDCG 的性能对比图Fig.3Comparison ofNDCG

图4和图5显示不同方法在两个数据集上的覆盖率指标情况，本文将TimeMF-BiLSTM方法及其他基线算法重复运行50次，取其平均值作为不同算法的覆盖率值。从图中可以看出，覆盖率与推荐列表的长度 $N$ 呈现正相关关系，并且相较于其他基线方法，本文算法具有更高的覆盖率。其原因是，以往的算法没有考虑任务的流行度偏差，造成过度推荐流行性任务。本文利用任务流行度设立惩罚因子，进而降低流行性过高的任务权重，提高冷门任务选择的概率，因此当任务数量不断增加时，TimeMF-BiLSTM任务推荐方法也能保证工人有更多的机会选择其他任务。

![](images/4155878cdbd84d40b104936ca68079d4227a7d976644600c408d9640cfb385d6.jpg)  
图4覆盖率性能对比(Gowalla数据集)

![](images/8a227320279619d7af3f7ba3900ad389d0a17c37e930af70380f9dc1cc35f6e2.jpg)  
Fig.4Comparison of coverage (Gowalla dataset)   
图5覆盖率性能对比(Foursquare 数据集)  
Fig.5Comparison of coverage (Foursquare dataset)

最后，在两个数据集上进行实验，以验证工人声誉关系对任务覆盖率的影响，如图6和图7所示。推荐列表长度为20，图5中的不同线条表明本文计算工人声誉时引入的社交网络信息条数，横坐标表示移动群智感知平台中工人和任务的比率，理论上来说，当平台内工人和任务的比率不断增加时，推荐的覆盖率会成比例下降。从图中可以看出，工人声誉的引入，可以保证任务推荐覆盖率的下降速度变缓慢，这是由于工人声誉可以让本文更准确的分析任务流行度，对流行任务的惩罚也就更加准确，因此当工人和任务的比率不断增加时，TimeMF-BiLSTM方法也能保证任务推荐的覆盖率下降速度最慢。从图中可以看出，当任务和工人的比率为10时，平台的覆盖率仍可以超过 $71 \%$ 。并且从图中可以发现，随着工人社会关系引入条数的不断增加，覆盖率下降速度越来越慢，因此在保证任推荐的覆盖率时有必要引入工人之间的社会关系。这些实验结果表明，TimeMF-BiLSTM在MCS实际应用中具有更全面的性能。

# 6 结束语

本文针对移动群智感知领域在挖掘工人偏好时忽略时空信息和任务流行度影响，导致任务推荐的准确性和覆盖率低的问题，设计了融合时空信息和任务流行度分析的任务推荐方法。融合时空信息可以准确地挖掘工人偏好，而任务流行度分析可以有效地缓解现有研究任务覆盖率低的问题，所提方法将时间因素、空间因素两个方面对推荐的影响分开计算，可以有效地缓解现有方法需要频繁更新的缺点。本文所提方法适用于所有具有时空背景的项目推荐问题，同时由于不同模型相互独立，未来更多影响工人意愿的因素可以轻松嵌入，并且所提方法将推荐的精度和覆盖率两个指标分开优化求解支持其他多种优化目标组合，具有良好的可扩展性。在两个真实数据集上实验本文方法的有效性，实验结果表明，与现有的基线方法相比，本文所提方法在准确率和覆盖率具有良好的效果，证明了该方法在处理移动群智感知任务推荐领域实际应用方面具有出色的性能。在今后的工作中，本文将考虑更多可能影响MCS平台任务推荐效果的因素，并进一步研究如何用更短的训练时长来及时捕捉工人偏好，为工人提供更好的服务体验。

![](images/68062121823494d3e63f6bd965669652b327a6fde6d1bbc4381e16f5283ccbbf.jpg)

![](images/1495362647fad228dff71eab72bc0e65b82d5b9a37f9fed254128fc78b7706ea.jpg)  
图6工人声誉对两个数据集覆盖率的影响(Gowalla数据集) Fig.6Influence of worker reputation on accuracy (Gowalla dataset)   
图7工人声誉对两个数据集覆盖率的影响(Foursquare 数据集) Fig.7Influence of worker reputation on accuracy (Foursquare dataset)

# 参考文献：

[1]Ganti RK,Ye F,Lei H.Mobile crowdsensing:current state and future challenges [J].IEEE Communication Magazine,2011,49(11): 32-39.   
[2]Montori F,Bedogni L,Bononi L.A collaborative internet of things architecture for smart cities and environmental monitoring [J].IEEE Internet of Things Journal,2018,5 (2): 592-605.   
[3]Jovanovic S,Jovanovic M,Skoric T,et al.A mobile crowd sensing application for hypertensive patients [J]. Sensors.2019,19 (2): 400-416.   
[4]Huang Junqin,Kong Linghe,Dai Hongning,et al.Blockchain based mobile crowd sensing in industrial systems [J].IEEE Trans on Industrial Informatics,2019,16(10): 6553-6563.   
[5]Kim K,Zabihi H,Kim H,et al. TrailSense:a crowdsensing system for detecting risky mountain trail segments with walking pattern analysis [J]. Proceedings of the Acm on Interactive Mobile Wearable&Ubiquitous Technologies,2017,1(3): 1-31.   
[6]Wan Jiafu,Liu Jianqi,Shao Zehui,et al.Mobile crowd sensing for traffic prediction in internet of vehicles [J]. Sensors,2016,16 (1): 88-102.   
[7]Yucel F,Yuksel M,Bulut E.QoS-based budget constrained stable task assignment in mobile crowdsensing [J].IEEE Trans on Mobile Computing,2021,20 (11): 3194-3210.   
[8]王健，刘嘉欣，赵国生，等．移动群智感知中基于协同排序的任务推 荐方法[J]．电子学报，2021,49(10):2012-2019.(Wang Jian,Liu Jiaxin,Zhao Guosheng,et at. Task recommendation method based on collaborative ranking in mobile crowd sensing [J].Acta Electronica Sinica,2021,49 (10): 2012-2019.)   
[9]Zhao Zhongnan,Wang Yanli,Wang Huiqiang. SDN-based cross-domain cooperative method for trusted nodes recommendation in Mobile crowd sensing [J]. Per-to-Peer Networking and Applications,2021,14 (5): 3793-3805.   
[10] Tang Wenjuan,Zhang Kuan,Ren Ju,et al.Privacy-preserving task recommendation with win-win incentives for mobile crowdsourcing [J]. Information Sciences,2020,527: 477-492.   
[11] Karaliopoulos M,Koutsopoulos I, Titsias M.First learn then earn: optimizing mobile crowdsensing campaigns through data-driven user profiling [C]// Proc the 17th ACM International Symposium on Mobile Ad Hoc Networking and Computing.New York: ACM Press,2016: 271- 280.   
[12] Wang Zhibo,Zhao Jing,Hu Jiahui,et al. Towards personalized taskoriented worker recruitment in mobile crowdsensing [J]. IEEE Trans on Mobile Computing,2021,20 (5): 2080-2093.   
[13] Kumar P,Thakur R S. Recommendation system techniques and related issues:asurvey[J].InterationalJounalof Information Techology 2018,10 (4): 495-501.   
[14] Yuen M C,King I,Leung K S.Taskrec:a task recommendation framework in crowdsourcing systems [J]. Neural Processing Letters, 2015,41 (2): 223-238.   
[15] Wang Jian, Liu Jiaxin, Zhao Zhongnan,et al.A task recommendation framework for heterogeneous mobile crowdsensing [J]. The Journal of Supercomputing,2021,2021 (48): 12121-12142.   
[16] Dai Wei, Wang Yufeng,Ma Jianhua,et al. BTR: a feature-based bayesian task recommendation scheme for crowdsourcing system [J].IEEE Trans on Computational Social Systems,2020,7 (3): 780-789.   
[17] Yang Shuo,Zheng Zhenzhe,Tang Shaojie,et al.Fine-grained user profiling for personalized task matching in mobilecrowdsensing[J]. IEEE Trans on Mobile Computing,2021,20 (10): 2961-2976.   
[18] Yang Guisong,Li Yanting,He Xingyu,et al. Profile-free and real-time task recommendation in mobile crowdsensing [J]. IEEE Trans on Computational Social Systems,2021,8 (6): 1311-1322.   
[19] Noulas A, Scellato S,Lathia N,et al. Mining user mobility features for next place prediction in location-based services [C/ IEEE International Conference on Data Mining.Piscataway,NJ: IEEE Press,2012:1038- 1043.   
[20] Song Shiwei,Liu Zhidan,Li Zhenjiang,et at. Coverage-oriented task assignment for mobile crowdsensing[J]. IEEE Internet of Things Journal, 2020, 7 (8): 7407-7418.   
[21]王宁，张巍，苏湛，等．推荐系统中考虑流行程度差异的评分预测算 法 [J].软件导刊,2021,20(11):18-21.(Wang Ning,Zhang Wei,Su Zhan，et at.Rating prediction algorithm considering popularity differences in recommender systems [J]. Software Guide,2021,20 (11): 18-21.)   
[22] Mcy A,Ik B,Ksl B. Temporal context-aware task recommendation in crowdsourcing systems [J]. Knowledge-Based Systems,2021,219 (1): 106770.   
[23] Scellato S,Noulas A,Lambiotte R,et al. Socio-spatial properties of online location-based social networks [Cl//Proc of the 5th International Conference on Weblogs and Social Media.Barcelona: [s.n.],2011: 329- 336.   
[24] Vasconcelos MA, Ricc S,Almeida J, et al. Tips,dones and todos: uncovering user profiles in foursquare [C]// Proc of the 5th ACM International Conference on Web Search and Data Mining.New York: ACM Press,2012: 653-662.