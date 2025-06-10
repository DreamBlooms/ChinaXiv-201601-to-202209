# 基于KNE-BPNN的电务设备故障预测

李晨光¹，乔帅1，杨晓杰1，解伟凡²，李川子』，李俊红1(1．河北师范大学 数学与信息科学学院，石家庄 050024;2．东南大学 信息科学与工程学院，南京 211189)

摘要：针对铁路电务设备故障频发、运行效率低且无有效故障预测方法等现实问题，提出一种基于K-均值一邻域近似条件熵与BP神经网络（KNE-BPNN）的电务设备故障预测模型。首先，采用基于K-均值聚类的样例约简算法约简设备故障决策表中的冗余样例；其次，运用邻域近似条件熵属性约简方法对样例约简后故障决策表中的非必要属性进行约简；最后，使用经过样例和属性约简后的样本集训练BP神经网络并进行模型预测，直到模型输出结果满足预设条件为止。实验结果表明KNE-BPNN故障预测模型的预测精度和泛化性能均满足电务设备管理的实际需求。

关键词：BP神经网络；邻域粗糙集；近似条件熵；属性约简；故障预测；K-均值聚类算法 中图分类号：TP183 doi:10.3969/j.issn.1001-3695.2018.03.0201

# Fault prediction for communication andsignal equipment based on KNE-BPNN

Li Chenguang1, Qiao Shuail, Yang Xiaojie1, Xie Weifan²,Li Chuanzi1, Qiao Shuai1†,Li Junhong1† (1.Collgeof Mathematics& Information ScienceHebei Normal UniversityShijiazhuang O5024，China;2.Schoolof Information science& Engineering,Southeast University,Nanjing 21l189,China)

Abstract:Basedonthe practical problems,suchas frequentfailures,lowoperating efficiencyandlackingof efective fault prediction methods forrailway communication and signal (C&S)equipment,afault prediction model forC&S equipment based on K-means-neighborhoodapproximateconditional entropyandBPneuralnetwork (KNE-BPNN)is proposed.Firstly,a sample reduction algorithm based on K-means clustering is used to reduce the redundant samples in the equipment failure decision table.Secondly，using neighborhoodapproximate conditional entropyatribute reduction theory to reduce the non-esentialatributes inthefaultdecisiontableaftersamplereduction.Finally,teBPneuralnetworkis trainedbyusingthe reduced sampleset,andthe model is trained until itsoutput meets the expected requirement.The experimentalresults show thatthe prediction precision and generalizationperformance of the KNE-BPNN fault prediction model can mettheactual requirements.

Key words: neural network; neighborhoodrough set;approximateconditional entropy;reductionatributes;fault prediction; K-means method

# 0 引言

电务设备作为铁路运输系统的主要设备之一，在铁路运输安全体系中发挥着重要的保障作用错误!未找到引用源。。近年来，我国铁路建设逐步完善，铁路固定资产投资逐年增加，铁路科技也在不断创新。现如今，我国铁路建设已经步入高速发展的道路。与此同时，对电务设备的稳定性和可靠性也提出了更高的要求。由于电务设备内部结构复杂，极易发生故障。为了减少故障的发生，确保铁路系统安全稳定地运行，研究在设备运行过程中的设备故障预测方法，预测设备故障的发生，从而及时对设备进行维修和维护，减少由于设备故障带来的人员伤害和经济损失是一个重要且现实的问题。

鉴于故障设备预测存在较高的研究价值，许多专家学者对这类问题进行了深入、广泛的研究，也产生了很多重要的研究成果。比如，利用支持向量机（SVM)、神经网络、灰色系统、模糊系统、时间序列、实时专家系统，等进行故障设备预测方面的研究错误!未找到引用源。。其中，人工神经网络具有自学习、自组织和非线性的能力，并且能够克服早期人工智能在模式识别和

非结构化处理等方面的不足，展示出其良好的智能特性错误!未找到  
引用源。0

在实际应用中，进行预测的样本数据往往会出现维度高，数据量大，关系复杂等不利于加工处理的情况。这样的数据输入神经网路预测模型容易造成模型收敛速度慢、拟合程度低、泛化能力不强等现象，而基于粗糙集理论的属性约简能够从复杂的数据中提取出潜在的、精度高的、分类性能好的数据错误!\*找到引用源。。虽然粗糙集属性约简能够消除冗余数据，提高模型训练速度，但是在样本集中依然存在无效的、冗余的样例，使预测模型呈现过学习、过拟合等现象，而采用基于 $K$ 均值聚类[5.6]的样例约简算法能够有效地约简冗余样例，加快模型的学习速度。

现阶段铁路电务部门对于电务设备的管理主要依赖人工方式进行，该方式存在管理工作繁琐，管理效率低下，不适合多用户共享等弊端。同时，铁路电务设备结构复杂，设备组成部件容易老化，极易造成设备故障。如何专业化地管理电务设备，提高电务设备的安全性和可靠性，已成为铁路电务部门急需解决的重要课题。

针对上述问题，给出基于样例和属性的设备故障数据约简方法，并在此基础上构建模型对电务设备故障进行预测。首先采用K-均值聚类对决策表进行样例约简；其次，使用基于邻域近似条件熵错误!未找到引用源。对约简后的决策表进行属性约简；最后构建基于KNE-BPNN（KNE-BPNN即K-均值和邻域近似决策熵的BP神经网络）的电务设备故障预测模型。实验结果表明，该模型在设备故障预测方面表现出良好的性能，可为后续电务设备智能管理提供有效思路和方法。

# 1 K-均值样例约简

真实的样本数据集往往存在很多无关样例，这类数据会使模型出现过学习、过拟合等情况，导致模型泛化能力降低。据此，采用基于K-均值聚类的样例约简算法对样本集进行约简，消除样本集中的无关、冗余样例，提高训练后的模型的泛化能力。

# 1.1K-均值聚类算法

K-均值聚类是一种传统的聚类算法，主要目标是将 $n$ 个观测样本划分成 $K$ 个类别，使得每个观测值与其所在聚类的均值之间的距离最小。该算法首先随机选择 $K$ 个观测值作为初始聚类中心，并根据每个观测样本到各个聚类中心之间的距离将样本划分到距离最小的簇。然后计算每个簇的均值并将其更新成簇的聚类中心，迭代调整观测值的类别划分，直到各个簇的聚类中心不再发生改变。通常 $K$ 均值聚类采用平方误差准则函数，该准则函数可以使 $K$ 个聚类尽可能地聚集和收敛[5.6]。K-均值聚类算法流程如图1所示。

K-均值聚类算法的执行步骤如下：

输入：观测样本集 $X$ 和聚类数目 $K$ ，其中$X = \{ x _ { 1 } , x _ { 2 } , . . . , x _ { n } \}$ 。

输出： $K$ 个聚类，每个聚类的平方误差最小。

a）令迭代次数 $i = 1$ ，随机选择 $K$ 个观测样本分别作为第j个类别的聚类中心 $C _ { j }$ [i], $j = 1 , 2 , . . . , K$ 。

b)计算每个观测样本与所有聚类的类别中心之间的距离$D I S ( x _ { k } , C _ { j } [ i ] ) , k = 1 , 2 , . . . , n ,$ 当$D I S ( x _ { k } , c _ { j } [ i ] ) = \operatorname* { m i n } \{ D I S ( x _ { h } , c _ { j } [ i ] ) , h = 1 , 2 , . . . , n \} ,$ 则将 $x _ { k }$ 划分到第j个聚类。

c）令 ${ \dot { \mathbf { i } } } = { \dot { \mathbf { i } } } + 1 ;$ ，更新聚类中心的值，$c _ { j } [ i ] = \frac { 1 } { n _ { j } } \sum _ { k = 1 } ^ { n _ { j } } x _ { k } ^ { [ j ] } , j = 1 , 2 , . . . , K$ ∑x,j=1,2,.,K，计算误差平方准则函数J的值 $\begin{array} { r } { J _ { e } [ i ] = \sum _ { j = 1 } ^ { K } \sum _ { k = 1 } ^ { n _ { j } } \bigl \| \ x _ { k } ^ { [ j ] } - C _ { j } [ i ] \bigr \| _ { \circ } ^ { 2 } } \end{array}$

d)如果 $\mid J _ { e } [ i + 1 ] - J _ { e } [ i ] \mid < \varepsilon ( \varepsilon$ 为极小值，一般为 $1 0 ^ { - 4 }$ ）则算法终止，否则转第b)步。

![](images/2836d6ce0d491d3189696fa895904a7a5a728eb6d9ba4c4fa686730ffe999891.jpg)  
图1K-均值聚类算法流程图

# 1.2样例约简算法

样例约简是基于K-均值聚类算法进行约简的。首先根据样例集中的数据关系构建设备故障二维决策表MDS（如表1所示， $\boldsymbol { x } _ { j }$ 表示样例，propi为条件属性， $D$ 代表决策属性，其中0表示代表未发生故障，1表示发生故障)。其次，指定决策类别数为聚类数目 $K$ ，并根据决策类别划分数据子集(不包括决策属性) $M D S _ { k }$ ， $( k = 1 , 2 , . . . , K )$ ，计算每个数据子集的均值，分别作为 $K$ 个聚类的聚类中心。然后采用 $K$ 均值聚类算法调整聚类和聚类中心，并输出 $K$ 个聚簇。最后计算每个簇中的不同决策类别样例所占的比例，约简比例较少的样例。采用基于

K-均值聚类的样例约简算法能够有效地约简样本集中的无关、冗余样例，减少冗余样例对模型预测的影响，提升模型的泛化能力。

表1决策表  

<html><body><table><tr><td></td><td>prop1</td><td>prop2</td><td>prop3</td><td>prop4</td><td>D</td></tr><tr><td>X1</td><td>1</td><td>2</td><td>1</td><td>1</td><td>0</td></tr><tr><td>X2</td><td>2</td><td>3</td><td>0</td><td>2</td><td>1</td></tr><tr><td>X</td><td>3</td><td>3</td><td>1</td><td>1</td><td>1</td></tr><tr><td>X4</td><td>2</td><td>4</td><td>1</td><td>2</td><td>0</td></tr></table></body></html>

基于K-均值聚类的样例约简算法的具体实现如下：a)构建二维决策表，将决策表中的决策类别数设为聚类个数K；b)按照决策类别划分数据子集且分别计算各数据子集的均值，并将均值指定为各个簇的聚类中心 $C _ { k }$ ，其中数据子集不包括决策属性；c)按照K-均值聚类算法调整各个聚类，最终得到 $K$ 个簇；d)根据各个簇中不同决策类别所占的比例，约简比例较小的样本。样例约简的算法流程如图2所示。

![](images/6d09452f8db4bfe245da92f124187a48725976f02a6aeef6fca71079a2ea34db.jpg)  
图错误！文档中没有指定样式的文字。基于 $K$ 均值聚类的样例约简算

# 2 基于邻域近似条件熵的粗糙集属性约简

# 2.1粗糙集

粗糙集理论是波兰数学家Z.Pawlak于1982年提出的一种处理非确定性和不完整性知识的数学工具错误!未找到引用源。。采用规则提取方式进行属性约简是粗糙集理论的重要研究内容之一。现有的属性约简方法主要有基于保正域的决策粗糙集属性约简方法错误!未找到引用源。，基于差别矩阵的属性约简方法错误!未找到引用源。，以及信息观下的属性约简方法错误!未找到引用源。，等。但是，经典粗糙集理论仅适用于处理离散型数据，如果要对数值型数据进行约简，需要事先对其进行数据离散化操作，而离散化操作可能会导致重要信息的损失，影响后续约简操作的效果错误!未找到引用源。。邻域粗糙集约简模型建立在邻域等价关系基础上，不需要离散化操作就能有效处理数值型数据，最大程度地保持样本集的分类性能错误!未找到引用源。

# 2.2邻域粗糙集

用于分类学习的数据集可以定义为一个五元决策系统$N D S = ( U , C , D , V , f ) _ { \circ }$ 其中 $U = \{ u _ { 1 } , u _ { 2 } , . . . , u _ { n } \}$ 是一个论域，为非空有限集， $C = \{ c _ { 1 } , c _ { 2 } , . . . , c _ { n } \}$ 表示对象的条件属性，为非空有限集， $D = \{ d _ { 1 } , d _ { 2 } , . . . , d _ { n } \}$ 表示对象的决策属性集合， $C \cap D = \phi$ 。$\textstyle V = \bigcup _ { a \in A } V _ { a }$ ，其中 $A = C \cup D , V _ { a }$ 是属性 $a$ 的值域。$f : U \times ( C \bigcup D ) \to V$ 是一个信息函数，它为每个对象的每一个属性均设置一个信息值，即 $\forall a \in A , x \in U , f ( x , a ) \in V _ { a ^ { \circ } }$

定义 $\mathbf { 1 } ^ { [ 1 3 ] }$ 对于任意一个对象 $u _ { i } \in U , B \subseteq C , u _ { i }$ 在属性集$B$ 上的邻域为

$$
\mathcal { S } _ { { B } } ( u _ { i } ) = \{ u _ { j } , u _ { j } \in U , \Delta _ { { B } } ( \mathbf { u _ { i } } , \mathbf { u _ { j } } ) \leq \delta \} , \delta \geq 0
$$

式中 $\Delta$ 表示两个对象之间的距离，通常用来衡量对象之间的相似度。

若 $A = C \cup D$ ,则在 $\mathbf { N }$ 维空间 $A = \{ { \mathrm { a } } _ { 1 } , { \mathrm { a } } _ { 2 } , . . . , { \mathrm { a } } _ { \mathrm { n } } \}$ 中，样本 $u _ { i }$ 和 $u _ { j }$ 之间的Minkowsky 距离为

$$
{ \boldsymbol { \Delta } } _ { M } ( u _ { i } , u _ { j } ) = [ \sum _ { K } ^ { N } \bigl | \ \mathbf { f } ( \mathbf { u } _ { \mathrm { i } } , \mathbf { a } _ { \mathrm { k } } ) - \mathbf { f } ( \mathbf { u } _ { j } , \mathbf { a } _ { \mathrm { k } } ) \ \bigr | ^ { M } ] ^ { \frac { 1 } { M } }
$$

其中 $f ( u , a _ { k } )$ 表示 $u$ 在属性 $a _ { k }$ 上的取值。

常见的Minkowsky距离函数主要有三种，当 $M = 1$ 时，此距离函数称为Manhattan 距离；当 $M = 2$ 时，称为Euclidean 距离；当 $M = \infty$ 时，称为Chebychev 距离，文中主要采用 Euclidean距离。

定义 $\pmb { 2 } ^ { [ 1 4 , 1 5 ] }$ 在领域决策系统 $N D S = ( U , C , D , V , f )$ 中，决策属性 $D$ 决定的一个不可分辨关系为$I N D ( D ) = \{ ( \mathbf { x } , \mathbf { y } ) \subset \mathbf { U } { \times } \mathbf { U } | \forall \mathbf { a } \in \mathbf { S } , \mathbf { f } ( \mathbf { x } , \mathbf { a } ) = \mathbf { f } ( \mathbf { y } , \mathbf { a } ) \}$ (3)那么， $U / I N D ( D ) = \{ \mathrm { Y } _ { 1 } , \mathrm { Y } _ { 2 } , . . . , \mathrm { Y } _ { \mathrm { m } } \}$ 表示决策属性 $D$ 对论域 $U$ 的划分， $B \subseteq C$ 在论域 $U$ 上的一个邻域关系为 $N _ { _ B }$ ， $\delta _ { B } ( u )$ 为样本$u$ 在属性 $B$ 上的邻域，则决策属性集 $D$ 相对于 $B$ 上的邻域上近似为

$$
\overline { { N _ { B } } } D = \cup _ { i = 1 } ^ { m } \overline { { N _ { B } } } Y _ { i }
$$

D 关于B的邻域下近似为

${ \underline { { N _ { B } D = } } } \cup _ { i = 1 } ^ { m } { \underline { { N _ { B } Y _ { i } } } }$ 其中： $\overline { { N _ { B } } } Y = \{ \mathbf { u } _ { \mathrm { i } } | \delta _ { \mathrm { B } } ( \mathbf { u } _ { \mathrm { i } } ) \bigcap \mathbf { Y } \neq \phi , \mathbf { u } _ { \mathrm { i } } \in U \}$ $\underline { { N _ { B } } } Y = \{ \mathbf { u } _ { \mathrm { i } } | \delta _ { \mathrm { B } } ( \mathbf { u } _ { \mathrm { i } } ) \in \mathrm { Y } , \mathbf { u } _ { \mathrm { i } } \in U \}$

定义 $\mathbf { 3 } ^ { [ 7 ] }$ 在邻域决策系统 $N D S = ( U , C , D , V , f )$ 中，$\forall B \subseteq C , X \subseteq U$ ， $X$ 在 $N _ { _ B }$ 关系下的邻域近似精度为：

$$
\gamma _ { B } ( X ) = \frac { \vert N _ { B } X \vert } { \vert \overline { { N _ { B } } } X \vert }
$$

其中： $X \neq \phi$ ， $\left| \mathrm { X } \right|$ 表示集合的势（或称基数，cardinal),$0 \leq Y _ { _ { B } } ( X ) \leq 1$ 。

# 2.3基于邻域近似条件熵的粗糙集理论

定义 $\mathbf { 4 } ^ { [ 7 ] }$ 对于一个邻域决策系统$N D S = ( U , C , D , V , f )$ ， $\forall B \subseteq C$ ，属性集 $B$ 的邻域为 $\delta _ { B } ( u )$ ，决策属性 $D$ 在论域 $U$ 的划分为 $I N D ( D ) = \{ \Upsilon _ { 1 } , \Upsilon _ { 2 } , . . . , \Upsilon _ { \mathrm { m } } \}$ ，则属性 $B$ 相对于决策属性 $D$ 的邻域条件熵为

$$
N C H = - \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } [ \frac { | \delta _ { \mathrm { { B } } } ( \mathbf { u } _ { \mathrm { j } } ) \bigcap \Upsilon _ { \mathrm { i } } | } { | U | } \times \log _ { 2 } \frac { \delta _ { _ B } ( u _ { j } ) \bigcap \Upsilon _ { \mathrm { i } } } { | \delta _ { _ B } ( u _ { j } ) | } ]
$$

定义 $\pmb { 5 } ^ { [ 7 ] }$ 对于一个邻域决策系统

$N D S = ( U , C , D , V , f )$ ，由定义1可知 $\forall B \subseteq C$ ，属性集 $B$ 的邻域为 $\delta _ { \scriptscriptstyle B } ( u _ { i } )$ ，决策属性 $D$ 在论域 $U$ 的划分为$I N D ( D ) { = } \{ \Upsilon _ { 1 } , \Upsilon _ { 2 } , { \ldots } , \Upsilon _ { \mathrm { m } } \}$ 。由定义3可知 $\gamma _ { _ B } ( Y )$ 是 $Y$ 在邻域条件关系 $N _ { _ B }$ 下的邻域近似精度，那么决策属性 $D$ 相对于属性 $B$ 的邻域近似条件熵为

$$
\begin{array} { r l } & { { \cal N } A C H ( D \vert B ) = - { \displaystyle { \sum _ { i = 1 } ^ { m } } } \{ ( 1 - \gamma _ { B } ( Y _ { i } ) ) \times } \\ & { { \displaystyle { \sum _ { j = 1 } ^ { n } } } [ \frac { \vert \delta _ { \mathrm { B } } ( \mathbf { u } _ { \mathrm { j } } ) \bigcap { \displaystyle \Upsilon _ { \mathrm { i } } \vert } } { \vert U \vert } \times \log _ { 2 } \frac { \delta _ { B } ( u _ { j } ) \bigcap { \displaystyle { \Upsilon _ { \mathrm { i } } } } } { \vert \delta _ { B } ( u _ { j } ) \vert } ] \} } \end{array}
$$

性质1错误!未找到引用源。 给定一个邻域决策系统$N D S = ( U , C , D , V , f )$ ，由定义1可知 $\forall B \subseteq C$ ，属性集 $B$ 的邻域为 $\delta _ { B } ( u _ { i } )$ ，决策属性 $D$ 在论域 $U$ 的划分为$I N D ( D ) { = } \{ \Upsilon _ { 1 } , \Upsilon _ { 2 } , { = } , \Upsilon _ { \mathrm { m } } \}$ ，那么邻域近似条件熵满足$0 \leq N A C H ( D | B ) \leq n \log _ { 2 } n , ( n = | U | ) \colon$ （204号

a）当且仅当$\begin{array} { r } { \forall Y _ { j } \in U / I N D ( D ) , | Y _ { j } | = 1 , \forall u _ { i } \in U , \delta _ { B } ( u _ { i } ) = \mathbf { U } \mathbb { \ : } \mathbb { H } \ : } \\ { N A C H ( D | B ) = M A X \{ \mathbf { N A C H } \} = \mathbf { n l o g } _ { 2 } \mathbf { n } } \end{array}$ F

b）当 $\gamma _ { _ B } ( X ) = \frac { \mid N _ { _ B } \ X \mid } { \mid \overline { { N _ { _ B } } } \ X \mid } = 1$ 即所有对象都是正域中的元素时，$N A C H ( D | B ) = M I N \{ \mathrm { N A C H } \} = 0 \ _ { \circ }$

性质2错误!未找到引用源。 在邻域决策表系统$N D S = ( U , C , D , V , f )$ 中，若 $M , N \subseteq C$ 且 $M \subseteq N$ ，那么

$$
N A C H ( D | M ) \geq N A C H ( D | N ) .
$$

性质3预该!不我到引用源。 在邻域决策表系统$N D S = ( U , C , D , V , f )$ 中，若 $M \subseteq C$ 且 $a \in M$ ,当$N A C H ( D | M ) \ge N A C H ( D | \mathrm { M - \{ a \} ) }$ 时，认为属性 $a$ 相对于 $B$ 来说是不必要的。

定义6错误！未找到引用源。 在邻域决策表系统$N D S = ( U , C , D , V , f )$ 中，若 $M \subseteq C$ ，当

$N A C H ( D | M ) = N A C H ( D | C )$ ，并且  
$\forall m \in M , N A C H ( D | M - \{ \mathbf { m } \} ) > N A C H ( D | C )$ 时，称 $M$ 是 $C$ 相对于 $D$ 的一个约简。

定义7错误！未找到引用源。 给定邻域决策系统$N D S = ( U , C , D , V , f )$ ， $\forall m \in C$ ， $m$ 相对于 $C$ 关于 $D$ 的内部属性重要度为

$$
I M P ( m , C , D ) = N A C H ( D | C ) - \{ m \} ) - N A C H ( D | C )
$$

定义8错误!未找到引用源。 对于一个邻域决策系统

$N D S = ( U , C , D , V , f ) _ { \circ }$ ，当 $\forall a \in C$ ，如果  
$N A C H ( D | C ) - \{ a \} ) > N A C H ( D | C )$ ，即 $I M P ( a , C , D ) > 0$ ，则称 $a$ 是 $C$ 相对于 $D$ 的一个核属性。

定义9错误!未找到引用源。 给定邻域决策系统

$N D S = ( U , C , D , V , f )$ ，若 $N \subseteq C$ ，当 $\forall n \in C - N$ 时， $n$ 关于$D$ 的外部属性重要度为：

$$
I M P ( n , N , D ) = N A C H ( D | N ) - N A C H ( D | N \bigcup \{ n \} )
$$

# 2.4基于邻域近似条件熵属性约简算法

通过邻域粗糙集相关理论获得所有条件属性集合的最小约简是一个NP问题，目前解决此类问题的一个有效方式是采用启发式的方法进行约简。启发式添加策略首先获取条件属性的核属性，然后循环比较各个核属性的属性重要性，将属性重要性 $I M P ( a , C , D )$ 最大的元素添加到约简集 $B$ 中，即$B = B \cup \{ a \}$ ，直到 $N A C H ( D | B ) = N A C H ( D | C )$ 为止。下面是基于邻域近似条件熵的粗糙集属性约简算法的基本步骤：

输入：邻域决策系统 $N D S = ( U , C , D , V , f )$ 和阈值 $\delta \geq 0$ 。

输出：邻域决策系统最小约简集 $B$ □a)初始化约简集 $B$ ，令 $B = \phi$ 。

b) $\forall u _ { i } \in U$ ，采用Euclidean 距离计算 $u _ { i }$ 在条件属性集C下的邻域 $\delta _ { C } ( u _ { i } )$ 。

c)计算决策属性 $\mathrm { ~ D ~ }$ 关于 $\mathrm { ~  ~ { ~ C ~ } ~ }$ 的邻域近似条件熵$N A C H ( D | C )$ 。

d) $\forall a _ { i } \in C$ ，计算 $I M P ( a _ { i } , C , D )$ ，若 $I M P ( a _ { i } , C , D ) > 0$ ，则将 $a _ { i }$ 添加到约简集 $B$ 中，即 $B = B \cup \{ \mathrm { a } _ { \mathrm { i } } \}$ 。

e)如果 $B \neq \phi$ ，计算 $N A C H ( D | B )$ ，若$N A C H ( D | B ) = N A C H ( D | C )$ ，则执行第 $\mathrm { \bf { g } } )$ 步，否则转到第6步执行。若 $B \neq \phi$ ，则直接执行第f)步。

$\mathrm { f } ) \forall a _ { i } \in C - B$ ，计算 $a _ { i }$ 的外部属性重要度 $I M P ( a _ { i } , B , D )$ ，若 $a _ { k }$ 满足 $I M P ( a _ { k } , B , D ) = \operatorname* { m a x } \{ \mathrm { I M P } ( a _ { i } , B , D ) , a _ { i } \in \mathbf { C } - \mathbf { B } \}$ (如果有多个属性满足该条件，则随机选择其中一个属性)，则令$B = B \cup \{ { \mathbf { a } } _ { k } \}$ ，并跳转到第e)步。

g)输出属性约简集 $B$ ，结束算法。

基于邻域近似条件熵的粗糙集属性约简算法流程如图3所示

# 3 基于KNE-BPNN的故障预测模型

基于KNE-BPNN故障预测模型的具体步骤如下：a)利用设备历史故障监测数据构造初始故障决策表；

b)采用K-均值聚类方法将决策表中的样例聚成两类（样本数据决策结果仅为发生故障和未发生故障两种)，计算每个簇中不同决策类别样例的比例，约简比例较小的样例；

c)使用邻域近似条件熵约简算法对样例约简后的决策表进行属性约简，去除决策表的冗余属性；

d)经过b)c)后产生一个新的约简决策表。并将其中的数据输入BP神经网络，经过反复训练和参数调优，确定神经网路每层的设置以及每层神经元节点的个数，最后利用调试好的神经网络对设备实施故障预测。

![](images/c7db5587de0185c5991bc9fe5f48aeee2825a129be43f6af84f391715a844906.jpg)  
图3基于邻域近似条件熵的粗糙集属性约简算法流程图

基于KNE-BPNN的故障预测模型采用K-均值样例约简和基于邻域近似条件熵属性约简算法对故障决策表进行约简操作，能够有效地约简冗余数据，确保样本数据保留更好的分类性能。而约简后的样本集输入神经网络后，能够提升神经网络的训练效率，避免模型出现过学习、过拟合状况。图4为基于KNE-BPNN故障预测模型工作流程，具体步骤如下：

a)故障数据决策表构建。将收集到的电务设备故障监测数据通过添加缺失值，替换一些异常值，最终初始化成一个二维的故障决策表。

b)样例约简。采用K-均值聚类方法对初始故障决策表按照决策表中样例的决策类别数N将样例聚类成N个簇，然后依次计算每个簇中不同决策类别的样例集所占的比例，并将比例较小的样本剔除，从而完成故障决策表的样例约简。

c)属性约简。首先计算故障决策表中所有条件属性集的邻域近似条件熵，初始化属性约简集B为空，并将所有内部重要度大于0的属性添加到约简集中。然后迭代计算属性约简集B的邻域近似条件熵，判断其是否与所有属性的近似条件熵相等。若相等，则输出；否则，计算除属性约简集以外所有条件属性的外部重要度，并将外部重要度最大的属性添加至属性约简集中，并再次进行迭代，直到属性约简集和条件属性集近似条件熵相等为止。

d)神经网络预测模型构建（图5为神经网络的结构图）。首先根据样本的维度和样本的类别数分别确定输入层节点数和输出层节点数。其次根据样本数据量和维度两个因素确定隐含层层数，然后为隐含层神经元设置节点数范围(例如设置隐含层的神经元个数 $N \in ( 5 0 ]$ 且 $N$ 为正整数)，从该范围内均匀取数，设置为该隐含层的神经元节点数。通过反复实验确定最终的隐含层神经元个数。

e)输出结果分析。将样本测试集输入训练好的神经网络模型中，最终得到样本故障情况的预测结果。对输出结果进行分析，若达不到预测目标，则继续调整模型中的超参数或增加训练的次数，直到输出结果符合预设条件为止。

![](images/2cec303b0ec0936ea785fc7f6cd0eee31f234d9ff65782a42a185d94efb38d04.jpg)  
图4基于KNE-BPNN的故障预测模型

![](images/2bd241a7ce0e13a34987a2cb3e38681ab63f6a3311162b928ad3f98940b07cf7.jpg)  
图5神经网络的结构图

# 4基于KNE-BPNN故障预测实例分析

# 4.1初始化决策表

文中使用铁路道岔设备电路的监测数据作为KNE-BPNN故障预测系统的样本集，如表2所示。将表2中的数据初始化成一个决策表 $N D S = ( U , C , D , V , f )$ ，其中条件属性 $C = \{$ 温度，供电电压，发送电压，发送频率，接收1.1电压，接收1.2电压，干扰电压，故障情况}，决策属性 ${ \bf D } { = } \{$ 故障情况}（发生设备故障为1，设备运转正常为0)。并非所有初始决策表中的因素都会对道岔设备故障产生影响，而通过K-均值样例约简以及邻域近似条件熵属性约简能够最大限度地保留决策系统中对道岔故障具有较大影响的样本。使用约简后的样本进行设备故障预测能够提高模型的预测精度和泛化能力。

表2铁路道岔设备故障决策表(部分数据)  

<html><body><table><tr><td>编号</td><td>温度</td><td>供电 电压</td><td>发送 电压</td><td>发送 频率</td><td>电压</td><td>接收1.1接收1.2 电压</td><td>干扰 电压</td><td>故障 情况</td></tr><tr><td>1</td><td>28</td><td>201.5</td><td>58.67</td><td>9.85</td><td>5.07</td><td>8.55</td><td>0.63</td><td>1</td></tr><tr><td>2</td><td>25.5</td><td>205.23</td><td>55.72</td><td>9.75</td><td>8.92</td><td>6.95</td><td>0.76</td><td>1</td></tr><tr><td>3</td><td>25.8</td><td>192.92</td><td>59.94</td><td>9.66</td><td>8.76</td><td>8.16</td><td>0.72</td><td>1</td></tr><tr><td>4</td><td>29.9</td><td>225.37</td><td>56.14</td><td>9.69</td><td>5.01</td><td>8.91</td><td>0.59</td><td>0</td></tr><tr><td>5</td><td>29.7</td><td>221.47</td><td>56.45</td><td>9.58</td><td>4.89</td><td>4.6</td><td>0.47</td><td>1</td></tr><tr><td>6</td><td>27.2</td><td>212.87</td><td>58.16</td><td>9.56</td><td>8.54</td><td>5.07</td><td>0.68</td><td>1</td></tr><tr><td>7</td><td>29.4</td><td>217.7</td><td>56.19</td><td>9.81</td><td>6.33</td><td>7.06</td><td>0.87</td><td>1</td></tr><tr><td>8</td><td>26.3</td><td>208.33</td><td>50.86</td><td>9.58</td><td>5.94</td><td>8.27</td><td>0.86</td><td>0</td></tr><tr><td>9</td><td>25</td><td>214.34</td><td>57.99</td><td>9.31</td><td>8.22</td><td>8.5</td><td>0.5</td><td>1</td></tr><tr><td>10</td><td>24.1</td><td>207.77</td><td>50.42</td><td>9.45</td><td>5.96</td><td>8.62</td><td>0.78</td><td>0</td></tr><tr><td>11</td><td>28.6</td><td>238.51</td><td>51.7</td><td>9.79</td><td>6</td><td>8.34</td><td>0.74</td><td>0</td></tr><tr><td>12</td><td>20.5</td><td>190.59</td><td>56.48</td><td>9.11</td><td>4.88</td><td>8.42</td><td>0.48</td><td>1</td></tr><tr><td>13</td><td>29.5</td><td>216.3</td><td>59.09</td><td>9.08</td><td>6.57</td><td>6.33</td><td>0.71</td><td>0</td></tr><tr><td>14</td><td>23.7</td><td>216.8</td><td>54.19</td><td>9.16</td><td>8.76</td><td>6.45</td><td>0.66</td><td>0</td></tr><tr><td>15</td><td>20.9</td><td>227.7</td><td>57.83</td><td>9.55</td><td>7.53</td><td>6.1</td><td>0.6</td><td>0</td></tr></table></body></html>

# 4.2K-均值样例约简

在采用K-均值样例约简算法约简样例之前，应事先确定好聚类的个数 $K$ 以及每个簇的聚类中心 $C _ { k }$ 。由K-均值样例约简算法可知，聚类个数 $K$ 应设置为决策表决策属性的类别数。而为了使大多数样本能够聚类到样本本身所属的类别，先对样本集进行标准化处理，也就是对每个样本按照去均值和方差进行缩放操作，即

$$
\stackrel { \wedge } { x } = \frac { x - x \_ m e a n } { x \_ s t d }
$$

其中: $x _ { - } m e a n$ 为均值， $x _ { - } s t d$ 为标准差。

其次，将样例集按照决策类别划分子集，然后计算每个子集的均值，并将这些均值作为各个簇的聚类中心 $C _ { k }$ 。即

$$
\left\{ \begin{array} { l l } { C _ { k } = ( \mathbf { c } _ { _ { 1 k } } , \mathbf { c } _ { _ { 2 k } } , . . . , \mathbf { c } _ { _ { \mathrm { n k } } } ) } \\ { \displaystyle \mathbf { c } _ { \mathrm { i k } } = \frac { 1 } { M _ { _ { k } } } \sum _ { m = 1 } ^ { M _ { _ k } } x _ { _ { m i } } , \mathbf { x } _ { \mathrm { m } } \in \{ \mathbf { x } \in U \left| x _ { d } = D _ { k } \right. \} } \end{array} \right.
$$

其中 $k = 0 , 1 , . . . , K - 1 , K \geq 2$ ， $n$ 为条件属性个数， $\boldsymbol { M } _ { \boldsymbol { k } }$ 为决策类别为 $D _ { k }$ 的样例集的个数， $x _ { m }$ 属于由决策类别为 $D _ { k }$ 的样例组成的样例集。

表3标准化故障决策表   

<html><body><table><tr><td rowspan="2">编号</td><td rowspan="2">温度</td><td>供电</td><td>发送</td><td>发送</td><td>接收</td><td>接收</td><td>干扰</td><td>故障</td></tr><tr><td>电压</td><td>电压</td><td>频率</td><td>1.1 电压1.2 电压</td><td></td><td>电压</td><td>情况</td></tr><tr><td>1</td><td>-0.25</td><td>2.35</td><td>0.21</td><td>-0.52</td><td>-0.59</td><td>-0.54</td><td>-0.66</td><td>1</td></tr><tr><td>2</td><td>-0.28</td><td>2.37</td><td>0.16</td><td>-0.52</td><td>-0.53</td><td>-0.56</td><td>-0.65</td><td>1</td></tr><tr><td>3</td><td>-0.28</td><td>2.35</td><td>0.26</td><td>-0.54</td><td>-0.55</td><td>-0.56</td><td>-0.68</td><td>1</td></tr><tr><td>4</td><td>-0.24</td><td>2.38</td><td>0.11</td><td>-0.51</td><td>-0.58</td><td>-0.52</td><td>-0.63</td><td></td></tr><tr><td>5</td><td>-0.23</td><td>2.37</td><td>0.13</td><td>-0.50</td><td>-0.57</td><td>-0.57</td><td>-0.63</td><td>1</td></tr><tr><td>6</td><td>-0.27</td><td>2.37</td><td>0.17</td><td>-0.52</td><td>-0.53</td><td>-0.58</td><td>-0.64</td><td>1</td></tr><tr><td>7</td><td>-0.24</td><td>2.37</td><td>0.13</td><td>-0.51</td><td>-0.56</td><td>-0.55</td><td>-0.64</td><td>1</td></tr><tr><td>8</td><td>-0.26</td><td>2.38</td><td>0.10</td><td>-0.50</td><td>-0.56</td><td>-0.52</td><td>-0.63</td><td>0</td></tr><tr><td>9</td><td>-0.30</td><td>2.37</td><td>0.17</td><td>-0.52</td><td>-0.54</td><td>-0.53</td><td>-0.65</td><td>1</td></tr><tr><td>10</td><td>-0.29</td><td>2.39</td><td>0.10</td><td>-0.50</td><td>-0.55</td><td>-0.51</td><td>-0.63</td><td>0</td></tr><tr><td>11</td><td>-0.26</td><td>2.40</td><td>0.03</td><td>-0.50</td><td>-0.55</td><td>-0.52</td><td>-0.61</td><td>0</td></tr><tr><td>12</td><td>-0.33</td><td>2.35</td><td>0.24</td><td>-0.51</td><td>-0.58</td><td>-0.52</td><td>-0.65</td><td>1</td></tr><tr><td>13</td><td>-0.24</td><td>2.36</td><td>0.17</td><td>-0.53</td><td>-0.56</td><td>-0.56</td><td>-0.64</td><td>0</td></tr><tr><td>14</td><td>-0.31</td><td>2.38</td><td>0.12</td><td>-0.51</td><td>-0.51</td><td>-0.55</td><td>-0.63</td><td>0</td></tr><tr><td>15</td><td>-0.35</td><td>2.38</td><td>0.14</td><td>-0.50</td><td>-0.52</td><td>-0.54</td><td>-0.61</td><td>0</td></tr></table></body></html>

通过分析故障决策表的决策属性D，可以明显观察到决策属性D有发生设备故障和设备运转正常两种情况，分别用1和0来表示，因此聚类个数 $K = 2$ ；接着对样本集进行标准化处理（样本标准化处理结果如表3所示，样本数据均保留两位小数)，数据标准化既能保证各个属性之间的差别依然存在，又平衡了各个属性之间的量级。然后按照决策类别划分子集，计算各个子集的均值，将其作为每个簇的聚类中心。计算可得

$$
C _ { 0 } = ( - 0 . 2 8 , 2 . 3 8 , 0 . 1 1 , - 0 . 5 1 , - 0 . 5 5 , - 0 . 5 3 , - 0 . 6 3 )
$$

$$
C _ { 1 } = ( - 0 . 2 7 , 2 . 3 6 , 0 . 1 8 , - 0 . 5 2 , - 0 . 5 6 , - 0 . 5 5 , - 0 . 6 5 ) \ : _ { \circ }
$$

确定聚类中心后，对样例进行聚类操作，直到聚类中心不再发生变化为止。由图6和表4可知，在15个样例中，样例编号为5，7和13的样本被错误划分，因此为了避免模型出现过学习，过拟合现象，应将这3个样例去除。

![](images/ce920ed6bb44d09da427de9caa4420fabcfcfb7e23b252c8e70a3a21c6f3f1da.jpg)  
图6聚类结果示意图

样例的聚类结果如表4所示。

表4样例聚类分析结果  

<html><body><table><tr><td>编号</td><td>实际类别</td><td>聚类类别</td><td>编号</td><td>实际类别</td><td>聚类类别</td></tr><tr><td>1</td><td>1</td><td>1</td><td>11</td><td>0</td><td>0</td></tr><tr><td>2</td><td>1</td><td>1</td><td>12</td><td>1</td><td>1</td></tr><tr><td>3</td><td>1</td><td>1</td><td>13</td><td>0</td><td>1</td></tr><tr><td>4</td><td>0</td><td>0</td><td>14</td><td>0</td><td>0</td></tr><tr><td>5</td><td>1</td><td>0</td><td>15</td><td>0</td><td>0</td></tr><tr><td>6</td><td>1</td><td>1</td><td></td><td></td><td></td></tr><tr><td>7</td><td>1</td><td>0</td><td></td><td></td><td></td></tr><tr><td>8</td><td>0</td><td>0</td><td></td><td></td><td></td></tr><tr><td>9</td><td>1</td><td>1</td><td></td><td></td><td></td></tr><tr><td>10</td><td>0</td><td>0</td><td></td><td></td><td></td></tr></table></body></html>

# 4.3邻域近似条件熵属性约简

样例约简操作完成之后，为防止模型训练速度过慢，学习率低的情况发生，采用邻域近似条件熵属性约简算法对条件属性进行约简。由表3可知在设备故障决策表有7个条件属性，在进行属性约简操作时，通过调整阈值 $\delta$ 能够控制约简属性的个数。一般情况下，约简后的属性子集个数应大于原始属性集的一半，而且属性子集应尽可能的小。所以属性集的个数$M _ { c } \in [ 4 , 5 ]$ ，且 $M _ { c }$ 为整数。经计算满足要求的 $\delta \in [ 0 . 3 8 , 0 . 5 2 ]$ ，将[0.38,0.52]以0.03为间隔分成5份，分别为[0.38,0.41)，[0.41,0.44)，[0.44,0.47），[0.47,0.50），[0.50,0.52]。然后，从每个区间内取一个随机数，最终得到5个阈值，即 $\delta _ { \scriptscriptstyle 1 } = 0 . 3 9$ ， $\delta _ { 2 } = 0 . 4 3$ ， $\mathcal { S } _ { 3 } = 0 . 4 4$ ， $\mathcal { S } _ { 4 } = 0 . 4 9$ ，$\delta _ { 5 } = 0 . 5 1$ 。最后，将各个阈值约简后的样例集，依次输入神经网络，并比较各个阈值所对应的预测精度，选择精度最高的属性约简子集作为最终的约简结果。

表5不同阈值的属性约简结果  

<html><body><table><tr><td>阈值</td><td>属性约简集</td></tr><tr><td>0.39</td><td>{a,a2,a,a7}</td></tr><tr><td>0.43</td><td>{a,a2,a,a,}</td></tr><tr><td>0.44</td><td>{a,a,a3,a4}</td></tr></table></body></html>

![](images/529de9836ccb2458cb18ea9c0349d237307cfef6ed1167fc65b1c807047b27de.jpg)  
图7三种阈值比较情况

令 $\mathbf { a } _ { 1 } - \mathbf { a } _ { 7 }$ 分别代表道岔故障决策表中的7个条件属性，依次为温度，供电电压，发送电压，发送频率，接收1.1电压，接收1.2电压，干扰电压。如表5所示， $\delta _ { 1 }$ 和 $\delta _ { 2 }$ 的约简结果一致， $\delta _ { 4 }$ 和 $\delta _ { 5 }$ 的约简结果也一致，因此应选择 $\delta _ { 1 } , \delta _ { 3 } , \delta _ { 4 }$ 所对应的约简集进行比较。分别将三种约简结果输入到参数设置相同的神经网络中进行训练，每个约简结果进行10次预测，取10次预测结果平均值，选出其中预测结果较好的属性约简集。如图7所示，在经过多次神经网络预测后，阈值 $\delta { = } 0 . 4 4$ 对应的预测精度最高，所以应选择条件属性为 $\{ \mathbf { a } _ { 1 } , \mathbf { a } _ { 2 } , \mathbf { a } _ { 3 } , \mathbf { a } _ { 4 } \}$ (即温度、供电电压、发送电压、发送频率)的约简样本集输入神经网络。

# 4.4两种属性约简算法对比

为进一步验证邻域近似条件熵属性约简算法的有效性，下面分别就差别矩阵属性约简算法错误!未找到引用源。和邻域近似条件熵属性约简算法从属性约简数目和预测精度两个角度进行对比。其中差别矩阵属性约简是在equalfrequency binning(等频分箱）数据离散化操作的基础上完成的，具体实验结果如表6\~8所示：

表6两种算法约简个数比较  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="2">约简后条件属性个数</td></tr><tr><td>文献[10]算法</td><td>本文算法</td></tr><tr><td>故障决策表</td><td>3</td><td>4</td></tr><tr><td></td><td>表7两种算法约简得到的条件属性</td><td></td></tr><tr><td rowspan="2">数据集</td><td>约简后得到的条件属性</td><td></td></tr><tr><td>文献[10]算法</td><td>本文算法</td></tr><tr><td>故障决策表</td><td>{a,a,a}</td><td>{a,a,aa}</td></tr><tr><td></td><td>表8BP神经网络模型下两种约简算法预测准确率对比</td><td></td></tr><tr><td rowspan="2">数据集</td><td>约简后条件属性个数</td><td></td></tr><tr><td>文献[10]算法</td><td>本文算法</td></tr><tr><td>故障决策表</td><td>74%</td><td>92%</td></tr></table></body></html>

通过上述实验结果可知邻域近似条件熵属性约简算法能有效的约简样本集中的冗余属性，同时模型的预测精度也远高于差别矩阵属性约简算法。因此邻域近似条件熵属性约简算法是

一种更加有效的约简方法。

# 4.5BP神经网络预测模型

随着深度学习研究的不断深入，很多学者针对特定问题设计出针对性的深度神经网络，主要包括CNN（卷积神经网络）、RNN（循环神经网络）、LSTM（长短期记忆网络）以及近期研究热点一一GANs（生成对抗网络）等。其中CNN适用于处理图像数据，RNN常用于解决语言识别和机器翻译问题，LSTM适合处理和预测时间序列中间隔和延迟相对较长的事件，而GANs可进行图文转换以及图片降噪等操作。由于目前铁路电务设备监测指标（属性）较少，通过系统监测获取到的数据规模相对较小并且数据复杂度也相对较低，因此应用上述四种网络进行实施故障预测并不能提升预测模型的预测精度，而且还有可能在模型学习阶段耗费大量的时间。而BP神经网络因其自身结构特征，极其适合处理较小规模的预测问题，故本文选用BP神经网络搭建故障预测模型。

考虑到实际应用中电务设备对应的样本数据属性较少，样本理想分类函数复杂性较低，故在设计电务设备故障预测模型时优先选择3层BP神经网络模型。在经过 $K$ 均值样例约简和邻域近似条件熵属性约简后，样例的条件属性集有4个属性，因此神经网络的输入层神经元节点数为4。由于故障预测问题是一个二分类问题，所以输出层神经元节点数为1。经过不断的训练和对比，最终确定隐含层神经元节点数为30时，神经网路的收敛速度和预测精度达到了预期效果。此外，将神经网络隐含层激活函数设置成ReLu来加快故障预测模型的训练速度，通过设置Sigmoid函数为输出层的激活函数，确保模型输出结果保持在[0,1]之间。

当故障预测模型训练结束后，选取50组测试样本输入故障预测模型，评估故障预测模型的性能，最终得到50组测试集的故障预测结果（如表6所示)。由表6数据可知，在50组测试样本中有4个测试样本出现了错分情况，分别是编号为2、10、41和44的样本。

表9测试样本集的预测结果  

<html><body><table><tr><td>编号</td><td>预测结果</td><td>真实类别</td><td>编号</td><td>预测结果</td><td>真实类别</td></tr><tr><td>1</td><td>0.000002</td><td>0</td><td>26</td><td>0.999999</td><td>1</td></tr><tr><td>2</td><td>0.998718</td><td>0</td><td>27</td><td>0.006536</td><td>0</td></tr><tr><td>3</td><td>0.000186</td><td>0</td><td>28</td><td>0.999983</td><td>1</td></tr><tr><td>4</td><td>0.628283</td><td>1</td><td>29</td><td>0.887141</td><td>1</td></tr><tr><td>5</td><td>0</td><td>0</td><td>30</td><td>0.000178</td><td>0</td></tr><tr><td>6</td><td>1</td><td>1</td><td>31</td><td>0.000034</td><td>0</td></tr><tr><td>7</td><td>0.893361</td><td>1</td><td>32</td><td>0.999993</td><td>1</td></tr><tr><td>8</td><td>0.999974</td><td>1</td><td>33</td><td>0</td><td>0</td></tr><tr><td>9</td><td>0.000072</td><td>0</td><td>34</td><td>1</td><td>1</td></tr><tr><td>10</td><td>0.998752</td><td>0</td><td>35</td><td>0.00021</td><td>0</td></tr><tr><td>11</td><td>0</td><td>0</td><td>36</td><td>0.000244</td><td>0</td></tr><tr><td>12</td><td>0.00018</td><td>0</td><td>37</td><td>0.999561</td><td>1</td></tr><tr><td>13</td><td>1</td><td>1</td><td>38</td><td>0.999565</td><td>1</td></tr></table></body></html>

<html><body><table><tr><td>14</td><td>0.8841</td><td>1</td><td>39</td><td>0.000091</td><td>0</td></tr><tr><td>15</td><td>0.99957</td><td>1</td><td>40</td><td>0.999569</td><td>1</td></tr><tr><td>16</td><td>1</td><td>1</td><td>41</td><td>0.99856</td><td>0</td></tr><tr><td>17</td><td>1</td><td>1</td><td>42</td><td>0.87962</td><td>1</td></tr><tr><td>18</td><td>1</td><td>1</td><td>43</td><td>0.60502</td><td>1</td></tr><tr><td>19</td><td>0.99956</td><td>1</td><td>44</td><td>0.99874</td><td>0</td></tr><tr><td>20</td><td>1</td><td>1</td><td>45</td><td>0.00642</td><td>0</td></tr><tr><td>21</td><td>1</td><td>1</td><td>46</td><td>0.88566</td><td>1</td></tr><tr><td>22</td><td>1</td><td>1</td><td>47</td><td>0.64724</td><td>1</td></tr><tr><td>23</td><td>1</td><td>1</td><td>48</td><td>1</td><td>1</td></tr><tr><td>24</td><td>0.580633</td><td>1</td><td>49</td><td>0.90369</td><td>1</td></tr><tr><td>25</td><td>0.999566</td><td>1</td><td>50</td><td>1</td><td>1</td></tr></table></body></html>

# 5 结束语

文中针对铁路电务设备故障频发、运行效率低且无有效故障预测方法等现实问题，提出一种基于K-均值聚类、邻域近似条件熵、以及BP神经网络的电务设备故障预测模型，能够为后续电务设备智能管理提供有效思路和方法。

目前在设备故障预测阶段主要使用设备日常监测数据进行故障的预测。但铁路运输调度的不同，不同设备发生故障后对铁路运输造成的损失不同。所以下一步的研究应额外设置设备故障损失决策表，将设备故障引起的损失和设备故障发生概率集成，最终形成设备维修紧急程度列表，电务维修人员可按照紧急程度列表去检修设备，最大程度地降低由于设备故障所造成的人员和财产损失。

同时，随着铁路智能技术的不断革新，未来的铁路智能系统可以对电务设备实施更全方位的监测，能够获取到维度更多、复杂度更高的数据。同时，随着系统的普及应用，获取的数据量也越来越大。本文所提的BP神经网络技术对多维复杂大量数据的处理效率会不尽如意，需要借助于深度神经网络学习更多的复杂数据所蕴含的特征，从而实现电务设备故障的高精准预测。

# 参考文献：

[1]龚原斌.浅谈铁路电务系统故障应急处置存在问题及对策[J].铁道通 信信号，2012,48 (01):46-47.(Gong Yuanbin.Discussion about the problem and strategy according to emergency fault handling of railway electrical system [J]. Railway Signaling & Communication,2012,48 (01): 46-47. )   
[2]艾红，周东华．动态系统的故障预测方法[J].华中科技大学学报：自 然科学版，2009，37(S1):222-225.(Ai hong，Zhou Donghua.Fault prediction approach for dynamic system [J]. Journal of Huazhong University of Science and Technology: Natural Science Edition,2009,37 (S1): 222-225. )   
[3]朱大奇.人工神经网络原理及应用[M].北京：科学出版社,2006.(Zhu Daqi.Principle and application of artificial neural network [M]. Beijing:

Science Press,2006.)

[4]郭宇，杨育.基于灰色粗糙集与BP神经网络的设备故障预测[J].计算 机应用研究，2017,34(09):2642-2645.(Guo Yu,Yang Yu.Equipment fault prediction based on grey rough set and BP neural network [J]. Application Research of Computes,2017,34(09):2642-2645.)

[5]吴夙慧，成颖，郑彦宁，等.K-means 算法研究综述[J].数据分析与知识发现,2011,27(05):28-35.(Wu Suhui,Cheng Ying,Zheng Yanning,etal.Survey on K-means Algorithm[J].New Technology of Library andInformation Service,2011,27(05): 28-35.)

[6]胡伟．改进的层次K均值聚类算法[J].计算机工程与应用，2013，49 (02):157-159.(Hu Wei.Improved hierarchical K-means clustering algorithm [J].Computer Engineering and Applications,2013,49 (02): 157-159. )

[7]张宁，范年柏．基于邻域近似条件熵的启发式属性约简[J//OL].计算 机应用研究，2018,5(35):1-2.(Zhang ning，Fan Nianbai.Heuristic atribute reduction based on neighborhood approximate conditional entropy [J].Application Research of Computes,2018,5 (35): 1-2.)

[8]黄国顺．保正域的决策粗糙集属性约简[J].计算机工程与应用，2016, 52 (2):165-169.(Huang Guoshun.Positive region preservation reducts in decision-theoretic rough set models [J].Computer Engineering and Applications,2016,52(2):165-169.)

[9]葛浩，李龙澎，杨传健．差别矩阵约简表示及其快速算法实现[J].控 制与决策，2016,31(1):12-20.(Ge Hao,Li Longshu,Yang Chuanjian Discernibility matrix-based reduct representation and quick algorithms [J]. Control and Decision,2016,31(1): 12-20.)

[10]续欣莹，刘海涛，谢珺，等．信息观下基于不一致邻域矩阵的属性约简 [J].控制与决策,2016,31(1):130-136.(Xu Xinying,Liu Haitao,Xie Jun, et al.Attribute reduction based on inconsistent neighborhood matrix under information view [J].Control and Decision,2016,31(1): 130-136.)

[11]胡清华，赵辉，于达仁．基于邻域粗糙集的符号与数值属性快速约简算 法[J]．模式识别与人工智能，2008，21(06):732-738.(HuQinghua, Zhao Hui,Yu Daren.Efficient symbolic and numerical attribute reduction with neighborhood rough sets [J].Patern recognition and artificial intelligence,2008,21 (06): 732-738.)

[12]谢玲玲，雷景生，徐菲菲．基于改进的邻域粗糙集与概率神经网络的水 电机组振动故障诊断[J].上海电力学院学报，2016，32(2)：181-187. (XieLingling,Lei Jingshen,Xu Feifei.Vibrant fault diagnosis for hydro-turbine generating unit based on improved neighborhood rough sets andPNN[J]. Journal of Shanghai University of Electric Power,2O16,32 (2): 181-187.)

[13]徐章艳，刘作鹏，杨炳儒，宋威．一个复杂度为 maX（O（C|U)，O(C|\~2|U//C)的快速属性约简算法[J]．计算机学报，2006，29(03):391-399.(Xu Zhangyan,Liu Zuopeng, Yang Bingru,etal.A quick atributereductionalgorithm with complexity of max (O (ICl|Ul)，O (IC|\~2|U//C)[J].Chinese Journal of Computers,2006,29 (03):391-399.)