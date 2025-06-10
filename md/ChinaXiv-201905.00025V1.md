# 基于核密度估计的基本概率指派生成方法

黄杰1,²，尉永清³′，伊静1,4，刘孟迪1,2(1.山东师范大学 信息科学与工程学院，济南 250358;2.山东省分布式计算机软件新技术重点实验室，济南250014;3．山东警察学院 公共基础部，济南 250014;4.山东建筑大学 计算机科学与技术学院，济南 250014)

摘要：D-S证据理论是一种有效处理不确定信息的方法，被广泛应用于各领域中，而D-S合成方法作用的对象是基本概率指派(basic probability assign,BPA)，如何生成BPA仍是D-S理论应用中重要且有待解决的首要步骤。针对生成 BPA提出一种基于核密度估计KDE（kermeldensity estimation）的BPA生成方法：训练数据用于构建基于最优化窗宽的核密度估计的数据属性模型；然后利用训练数据的核密度模型计算测试数据的密度一距离一分布值Tri-D(density-distance-distribution)，通过嵌套式的方法分配Tri-D 值获取测试数据对应的 BPA；最后D-S 合成 BPA得到最终判断，通过分类准确率来判断 BPA生成方法的有效性。实验通过在UCI数据集上的与其他方法的分类准确率对比验证了提出方法的有效性。

关键词：基本概率指派BPA；核密度估计；Tri-D；窗宽 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.11.0882

New method to determine basic probability assign based on kernel density estimation

Huang Jie1,2, Wei Yongqing³ †, Yi Jing1,4, Liu Mengdi, 2 (1.School of Information Science& Engineering，Shandong Normal University,Jinan250358,China;2.Shandong Provincial KeyLaboratoryforDistributedComputerSoftwareNovelTechnology,Jinan25ool4,China;3.BasicEducation Dept,Shandong PoliceColege,Jinan250o14,China;4.SchoolofComputer Science&TechnologyShandongJianzhu University, Jinan 250014, China)

Abstract:D-S evidence theory isa method that processesuncertain information effectively and iswidely used in information fusion.However,the determinationofBPA(Basic Probability Asign)orthe action objectofD-S fusion method is stillan open problem in processof D-S theory appication.This paper proposed aBPA determination method based on kerneldensityestimation(kde).The methoduses trainingdata toconstructadataatribute model withoptimizedbandwidth basedontheoptimized kerneldensityestimation;thencalculate thedensity-distance-distribution(Tri-D)valueof testdata byusingthe kernel density modeloftraining data.The next step is obtaining BPAoftestdata byusing the nested method to assign Tri-D.Finaly,fusing BPAbyD-Smethod togetthe finalresult,and judging thevalidityof theBPA generation methodby the classification accuracy rate.Anillustrativecase regarding the clasification accuracy compared with other methods on UCI data sets shows the effectiveness of the method.

Key Words:basic probability assign(BPA); kernel density estimation; Tri-D; bandwidth

# 0 引言

D-S证据理论是由Dempster[1]提出，并由Shafer[2]发展的一种有效处理不确定信息和组合多元信息的方法。它和经典的贝叶斯理论是数据融合中两个主流框架，但相比于贝叶斯理论，D-S理论具有将概率同时分配给单子集和复合子集的优点。D-S理论在数据融合[3]、综合评估[4,5]、分类[6,7]、进化博弈论[8\~10]等诸多领域实现了很好地应用。在应用D-S 框架的过程中，BPA的生成是关键又核心的第一步，会对最终的结果产生很大的影响。但如何生成BPA到现在依旧没有通用的解决办法，不少学者就此进行了研究，并提出了不同的解决方法。较早的Yager[11]引进了与D-S信念结构相关的一整类模糊测度，并讨论了模糊测度的熵；蒋雯等人[12\~14]提出了基于广义模糊数生成BPA的方法；Liu等人[15]将模糊朴素贝叶斯与最近邻均值分类进行加权结合提出了WFDSF算法；文献[16]提出了一种利用训练数据核心样例获得BPA的方法;文献[17]提出了基于分类器含混矩阵的方法；此外，还有基于聚类确定BPA的方法[18,19]。

通过对以上文献方法的学习可以发现，BPA的生成本质上是各可能事件发生概率的确定，而核密度估计正是一种完全基于数据本身来进行概率密度估计的有效非参数估计方法，所以本文提出一种基于核密度估计的BPA生成方法，首先利用训练数据构建最优化窗宽（以下简称h）的核密度估计模型；计算测试数据各属性在各模型中核密度取值，并进一步计算Tri-D，通过嵌套式分配[20生成BPA；D-S合成BPA得到判定结果，结合UCI数据集进行本文方法有效性的验证。

# 1 相关工作

# 1.1 D-S证据理论

下面对D-S证据理论的基本概念进行介绍。

a）辨识框架(frame of discernment)。

D-S理论中，将包含所有可能发生假设的集合$\Theta = \{ H _ { 1 } , H _ { 2 } , . . . , H _ { n } \}$ 定义为辨识框架，其中的假设是穷尽且独立的， $\Theta$ 的幂集为 $\Omega = \{ \{ \varphi \} , \{ H _ { 1 } \} , . . . , \{ H _ { n } \} , \{ H _ { 1 } H _ { 2 } \} , . . . , \{ \Theta \} \}$ ，共2"个假设集合。

b）基本概率指派(basic probability assign,BPA)。

设幂集 $\Omega$ 到[0,1]的映射 $m$ 满足式(1)，则称 $m$ 为基本概率指派（下文简称 BPA），又称 mass 函数或证据，其中 $m$ 值非零的子集称为焦元。

$$
\left\{ \sum _ { A \in \Omega } m ( A ) = 1 \atop m ( \varphi ) = 0  \right.
$$

$m$ 值表示对子集的支持程度，值越大表示支持程度越大。

c）组合规则。

对于两条证据，D-S组合规则如下，其中 $B _ { i }$ 和 $C _ { j }$ 为焦元，$k$ 称为冲突系数。

$$
\left\{ \begin{array} { l l } { \displaystyle m ( A ) = \frac { 1 } { 1 - k } \sum _ { B _ { i } \cap C _ { j } = A } m _ { 1 } ( B _ { i } ) m _ { 2 } ( C _ { j } ) , ( A \neq \varphi , A \subset \Theta ) \medskip } \\ { \quad \qquad \quad \qquad \quad m ( \varphi ) = 0 } \end{array} \right.
$$

$$
k = \sum _ { B _ { i } \cap C _ { j } = \varphi } m _ { 1 } ( B _ { i } ) m _ { 2 } ( C _ { j } )
$$

# 1.2Pignistic 概率[21]

在D-S 组合完BPA之后，取最大Pignistic 概率值为最终的结果，计算公式如式（4）所示，其中X表示集合X的基数。

$$
P _ { p i g } \left( A \right) = \sum _ { B \subseteq \Theta } \frac { \left| A \cap B \right| \times m ( B ) } { \left| B \right| }
$$

介绍完D-S证据理论基本内容，对D-S应用与本文工作的关系进行简单说明。本文工作是将有不同特征的数据转换为形如 $\scriptstyle m ( { \mathrm { A } } ) = 0 . 3 , m ( { \mathrm { B } } ) = 0 . 6 , m ( { \mathrm { C } } ) = 0 . 1$ 且满足式(1)的BPA(A,B,C就是中的假设，也就是数据可能的类别或标签)以供D-S按式(3)(4)进行组合，得到最终一条BPA，所以BPA生成是D-S应用过程必不可少的一步。

# 1.3核密度估计(KDE)

求解给定样本集合分布密度的方法包括参数估计和非参数估计两种类型。核密度估计（或称Parzen窗法)属于后者。与参数估计中需要假定所估计数据在各个可能类别中都服从特定分布的“不准确”前提相比，由Rosenblatt[22]和Parzen[23]提出的核密度估计从数据本身出发研究数据的分布特征，在统计和各应用领域均受到了高度重视。对于独立同分布随机变量 $x _ { I } , x _ { 2 } , . . . , x _ { n } ,$ 其真实服从的概率密度函数 $\operatorname { f } ( \mathbf { x } )$ 的核密度估计函数表示如下：

$$
{ \hat { f _ { h } } } ( x ) = { \frac { 1 } { n h } } \sum _ { i = 1 } ^ { n } K ( { \frac { x _ { i } - x } { h } } ) , x \in R
$$

其中： $K ( \bullet )$ 为核函数；h为预先给定的正数，通常称为窗宽或光滑参数。为方便起见，本文记 $K _ { h } ( \mu ) = K ( \mu / h ) / h$ ，则式(5)可以表示为

$$
{ \hat { f } } _ { h } ( x ) = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } K _ { h } ( x _ { i } - x ) , x \in R
$$

从式(6)可以看出，f的密度估计 $\hat { \boldsymbol f }$ 不仅与给定的样本集合有关，还与核函数的选择与带宽参数的选择有关。常见的核函数包括高斯核函数(normal)、三角核函数(triangle)、均匀核函数(uniform)和 Epanechnikov 核函数等,本文在此不再赘述。本文主要考虑窗宽 $h$ 因素， $h$ 的取值决定了密度曲线的光滑程度。图1是一组随机生成的服从正态分布的数据在不同 $h$ 时的核密度估计曲线。

![](images/b0e8c2191f8faa6cd76446e963127aadc0aedba722ad8d837451eb66d7a768a8.jpg)  
图1正态分布数据在不同 $h$ 下的kde 曲线'ig.1KDE curves of random data with different $h$

由图1可以看出，当 $h$ 取值过小时，曲线过于陡峭波折，出现了过拟合现象；而随着 $h$ 的增大，曲线逐渐平缓；当 $h$ 增大到2时，曲线就过于平滑，使数据的特征被掩盖。综上，选择合适的 $h$ 非常重要，本文采用最优化的方法来选择 $h$ 详见2.1节。

# 2 基于核密度估计的基本概率指派生成方法

BPA生成的基本要求是要满足后续组合过程的使用，在此基础上要尽可能多地提取和利用数据信息，不同的属性可以从不同的角度反映数据的特征，因此本文以属性为基本单位进行 $h$ 的优化和kde属性模型的构建，后续的BPA分配也是基于属性模型的（需要说明的是，将一维属性下得到的关于 $\boldsymbol { \nu }$ 个类别的 $\nu$ 个kde子曲线统称为一个属性模型）。

下面将介绍本文的方法，首先给出以下假设：所有可能的假设或最终所有的类别共 $\nu$ 个，即辨识框架表示为$\Theta = \{ \mathrm { c } _ { 1 } , \mathrm { c } _ { 2 } , . . . , \mathrm { c } _ { \mathrm { v } } \}$ ，数据集包含 $n$ 条数据，每条数据有 $p$ 维属性 $\mathbf { \mathcal { A } } _ { t }$ 表示测试数据。

# 2.1基于最优化窗宽的属性kde 模型

现有窗宽的优化方法主要是基于积分均方误差MISE(mean integrated squared error)的优化[24],MISE 的定义如下：

$$
M I S E ( h ) = E [ \int ( \hat { \boldsymbol { f } } _ { h } ( \boldsymbol { x } ) - f ( \boldsymbol { x } ) ) ^ { 2 } d \boldsymbol { x } ] =
$$

$$
\int [ E { \hat { f } } ( x ) - f ( x ) ] ^ { 2 } d x + \int V a r { \hat { f } } ( x ) d x
$$

上式中分解后的第一项表示期望值与真实值间的偏差，第二项表示估计值的方差，对上式求解可以得到偏差及方差的表示式，经过求导、求最小值等一系列过程最终推导出最优窗宽 $h$ 的表达式如下(详细公式推导见文献[24]):

$$
h = ( \frac { 4 \stackrel { \wedge } { \sigma } ^ { 5 } } { 3 n } ) ^ { 0 . 2 } \approx 1 . 0 5 9 \stackrel { \wedge } { \sigma } n ^ { - 0 . 2 }
$$

其中： $\hat { \sigma }$ 和 $n$ 分别代表样本的标准差和数目。根据式(7)可以计算出训练数据属性 $j$ 对应类别 $i$ 的最优窗宽 ${ h _ { i j } } ^ { * }$ ，最终得到训练数据的 $p$ 行 $\nu$ 列的最优化窗宽矩阵 $\mathbf { H } ^ { \ast }$ 。

利用训练数据构建属性核密度估计模型，具体操作为：对训练数据属性 $j$ 按不同类别进行划分，不同属性下不同类

别的优化窗宽 $h$ 在 $\mathbf { H } ^ { * }$ 中已经相应求出，按式(6)进行核密度估计，最终一维属性下共包含 $\nu$ 个子KDE 模型，按照之前第2 章开始的说明，本文称 $p$ 维属性共对应 $p$ 个模型。

# 2.2密度一距离一分布值(Tri-D)

基于训练数据的kde属性模型构建已完成，测试数据的属性在各属性模型下的密度取值可随之得出，数据在某类别下的密度值的大小与数据属于该类别有正相关的关系，但在类间距离较近或密度差距较明显的情况下，仅根据密度值大小来判断所属类别可能会导致较多错误的发生。在区间[4,5]和[5.2.5.6]分别随机生成10个数据记为A类和4个数据记为B类，通过核密度估计得到它们的kde曲线如图2所示。

![](images/90f1c10d33c4608029a9b002d64e0278b6fba221a3b81f8aae0cddb9cb03cd8d.jpg)  
图2A,B两类核密度曲线

由图2可以发现类，别A与B的密度曲线在 $\textbf { x }$ 轴重叠部分较大，可以想象随着A,B类间距离的缩小（在另一方不动的前提下，A曲线往右移动或者B曲线往左移动），这将导致两曲线重叠部分越来越大，这样一来仅靠密度值已经无法正确区分点的类别。

在传统的分类聚类算法中，KNN 通过距离选择样例的 $k$ 近邻进行分类；K-means 算法通过样例与中心点间的距离来进行聚类，所以距离是类别判断中非常重要的因素；另外，同一类别的点之间的距离分布应该相似度更高，所以结合密度值、距离以及分布特征，本文提出了 $T r i - D$ 值的概念，测试点 $x _ { t }$ 的属性 $j$ 在相应 $j$ 属性模型中关于类别 $i$ 的 $T r i - D$ 值定义如下，由此对于有 $\mathbf { \sigma } _ { \nu }$ 个类别的数据来说，在一维属性下共可以得到 $\nu$ 个 $T r i - D$ 值：

$$
T r i - D _ { t i j } = f _ { i j } ( x _ { t } { } ^ { j } ) \cdot ( \mid d _ { t i j } \cdot \overline { { d _ { t j } } } ^ { - 1 } - 1 \mid ) ^ { - 1 }
$$

其中： $f _ { i j } ( x _ { t } ^ { \ j } )$ 代表点 $x _ { t }$ 的属性 $j$ 在对应第 $j$ 维属性模型中 $i$ 类曲线上的密度取值； $d _ { t i j }$ 表示 $x _ { t }$ 属性 $j$ 的值到训练数据属性 $j$ 的第 $i$ 类数据中心点的距离；中心点矩阵 $C e n _ { p \times \nu }$ 由算法k-means $+ + [ 2 5 ]$ 对每维属性的各类别聚类得到； $\overline { { d _ { t j } } }$ 代表训练数据的第 $j$ 维属性下第 $i$ 类数据中任意两点之间距离的均值。

对上述定义进行简单分析：首先第一部分 $f _ { i j } ( x _ { t } ^ { j } )$ ，其取值越大说明在属性 $j$ 的条件下 $x _ { t }$ 属于类别 $i$ 的可能性越大;其次，第二部分由两个距离组成：第一个距离是测试点到训练数据类别中心点的距离，第二个距离选择了训练数据类别i中任意两点之间的平均距离；通过前面的两个距离的比较来实现分布特征的考量，如果两个距离越相近，即 $\vert d _ { i j } \cdot \overline { { d _ { i j } } } ^ { - 1 } - 1 \vert$ 越小，本文就认为 $x _ { t }$ 与该类别所有点的距离分布越相似。所以综合以上分析， $T r i - D _ { t i j }$ 值越大，在属性 $j$ 的条件下 $x _ { t }$ 属于类别 $i$ 的可能性越大；反之，则越小。

# 2.3基本概率指派生成

每个测试数据 $x _ { t }$ 的属性 $j$ 在相应属性模型下可以得到 $\mathbf { \Phi } _ { \nu }$ 个 $T r i - D$ 值，所有 $p$ 个属性共可以得到 $p$ 行 $\mathbf { \sigma } _ { \nu }$ 列的 $T r i - D$ 值矩阵。以 $x _ { t }$ 的任一维属性 $j$ 为例说明本文的嵌套式[20]的分配方法：属性 $j$ 在对应模型中可以得到 $\nu$ 个 $T r i - D$ 值组成向量 $T r i \ – D _ { t j }$ 对 $\it { T r i - D _ { t j } }$ 按降序排序,得到,设相应的 $T r i - D _ { t j }$ '类别向量为 $\bf { C _ { d } }$ 则本文分配方式如下：

$$
m ( C _ { d } [ 1 ] ) = T r i - D _ { t j } ^ { ~ } [ 1 ]
$$

$$
m ( C _ { d } [ 1 ] , C _ { d } [ 2 ] ) = T r i - D _ { t j } ^ { \phantom { ' } } [ 2 ]
$$

$$
m ( C _ { d } [ 1 ] , C _ { d } [ 2 ] , . . . , C _ { d } [ \nu ] ) = T r i - D _ { t j } ^ { \phantom { * } } [ \nu ]
$$

通过这种分配方法可以同时得到单焦元BPA和多焦元复合BPA。为满足式(1)的要求，需要对分配得到的各式进行归一化得到所需的BPA。最终， $x _ { t }$ 的每一维属性都可以得到一条BPA, $p$ 维属性得到 $p$ 条 BPA,通过组合得到最终BPA。

# 2.4算法流程

本文算法的流程给出如图3所示。下面对算法的相关细节进行介绍：将数据分为用来学习和构建属性模型的训练数据和评估方法有效性的测试数据，首先利用训练数据构建kde 模型，将每一维属性都视为一个信息来源：对于每一维属性 $j$ 中的不同类别 $i$ ，通过3.1中式(7)计算得到相应的窗宽${ h _ { i j } } ^ { * }$ ，最终得到最优窗宽矩阵 $\mathbf { H } ^ { \ast }$ ；对各属性对应的各类别数据按照相应的优化窗宽进行核密度估计(本文使用高斯核函数，见4.2节)，得到属性 $j$ 的kde模型。对于测试数据：根据构建的训练数据属性模型，按式(8)计算 $T r i  – D$ 值，最终任一条测试数据 $x _ { t }$ 都对应得到值矩阵 $T r i - D _ { p \times \nu }$ ，依照式(9)进行分配获得 $p$ 条 BPA,D-S 组合得到最终BPA，取最大Pignistic值对应假设为最后的结果。

![](images/9d2794b84434c599465700bf1deb5f47cf922f6f71a94dc3ccafc6bc34f85c32.jpg)  
Fig.2KDE curves ofAand B classes   
图3本文算法流程  
Fig.3Procedures of proposed method

# 3 实验及结果分析

本节共有三组实验在UCI数据集上的实验：3.1节对Iris数据集的数据进行实验流程的示例说明；3.2节确定了核函数的选择，并对本文窗宽的优化效果进行了证明；3.3节通过在UCI数据集上的分类准确率说明了本文方法的有效性。

本文实验中用到的UCI数据集的名称、实例数、类别数、属性数以及是否有缺失值等信息由表5给出。对于缺失值的情况在应用D-S证据理论的过程中可以直接忽略无须做处理，这也是D-S理论的优点之一。

# 3.1本文方法实验示例

本节是通过对Iris一测试数据的分类过程来对本文算法流程进行说明。Iris数据集是分类基准数据集，共有三个类别Setosa(S)、Versicolor(C)、Virginica(V)。每条数据包含SL,SW,PL,PW四维属性，每个类别均有50个样例，共150个样例。本示例实验取 $80 \%$ 为训练数据，给定标签为C的测试样例,其各属性取值如下： $_ { \mathrm { S L } = 6 . 1 \mathrm { c m } }$ 0 $\operatorname { S W } { = } 2 . 9 \operatorname { c m }$ $\mathrm { P L } { = } 4 . 7 \mathrm { c m }$ $\operatorname { P W } { = } 1 . 4 \mathrm { { c m } }$ 。

首先利用训练数据构建属性kde模型：利用式(7)计算训练数据各属性的最优窗宽，得到各属性中不同类别的最优窗宽，如表1所示。图4\~7展示了通过核密度估计构造的各属性模型及模型中不同类别的核密度曲线。其次，计算测试数据的 $T r i - D$ 值：利用K-means $\cdot + + \vert 2 5 \vert$ 聚类得到训练数据各属性不同类别的中心点，如表2所示，按照 $T r i  – D$ 的定义计算得到 $T r i - D$ 矩阵，如表3所示；生成测试数据的BPA：通过嵌套式分配方法得四维属性对应的共计四条BPA，如表4所示，利用式(3)计算任意两 BPA 之间的冲突系数 $k$ ，结果为$k _ { I 2 } = k _ { I 3 } = k _ { I 4 } = k _ { 2 3 } = k _ { 2 4 } = k _ { 3 4 } = 0$ ，BPA之间不存在冲突问题；D-S 组合：组合得最终BPA 为 $m ( \mathrm { S } ) { = } m ( \mathrm { V } ) { = } 0 , m ( \mathrm { C } ) { = } 1$ ，所以判定测试数据属于“最被支持”的C类，与真实类别一致，判定正确。

![](images/2c084d97fc7c48a369f82cd81d1211325911d989d6efb189856921a30268eb3d.jpg)  
图4属性SL模型下三个类别曲线

![](images/5957b85a2c3e7b97eaea6a57117a4c410322a29a98c0e9a6b58b065f31168953.jpg)  
Fig.4Kde curves of three classes for attribute SL   
图5属性SW模型下三个类别曲线

![](images/4ce8611cdb38a87d2602431fdf220bdc6f5d2caf749bb5a57f108d2075e2a37c.jpg)  
Fig.5Kde curves of three classes for attribute SW   
图6属性PL模型下三个类别曲线  
Fig.6Kde curves of three classes for attribute PL   
Fig.7Kde curves of three classes for attribute PW

![](images/33259b405592da1f0721a6b70c95e17bdbbe5a2b900e7a890ba7a4f0b1ad8935.jpg)  
图7属性PW模型下三个类别曲线

Table1 Bandwidth for all classes of each attribute   

<html><body><table><tr><td>属性</td><td>S</td><td>C V</td></tr><tr><td>SL</td><td>0.18</td><td>0.28 0.33</td></tr><tr><td>SW</td><td>0.21</td><td>0.17 0.17</td></tr><tr><td>PL</td><td>0.09</td><td>0.26 0.28</td></tr><tr><td>PW</td><td>0.05</td><td>0.11 0.14</td></tr></table></body></html>

表2各属性下类别的中心点

表1各属性对应类别的窗宽  
表3Tri-D值  

<html><body><table><tr><td>属性</td><td>S</td><td>C V</td><td></td></tr><tr><td>SL</td><td>5.005</td><td>5.988</td><td>6.590</td></tr><tr><td>SW</td><td>3.420</td><td>2.778</td><td>2.980</td></tr><tr><td>PL</td><td>1.447</td><td>4.265</td><td>5.523</td></tr><tr><td>PW</td><td>0.243</td><td>1.335</td><td>2.013</td></tr></table></body></html>

Table2Center for all classes of each attribute   

<html><body><table><tr><td>属性</td><td>S</td><td>C</td><td>V</td></tr><tr><td>SL</td><td>0.014</td><td>0.692</td><td>0.305</td></tr><tr><td>SW</td><td>0.226</td><td>1.555</td><td>0.96</td></tr><tr><td>PL</td><td>0</td><td>2.692</td><td>0.128</td></tr><tr><td>PW</td><td>0</td><td>2.271</td><td>0.078</td></tr></table></body></html>

表4测试样例的四条BPA

Table 3 Tri-D values   
Table 4Four bpas of test sample   

<html><body><table><tr><td>属性</td><td>BPA</td></tr><tr><td>SW</td><td>m({C})=0.684，m({C,V})=0.302，m({C,V,S})=0.014</td></tr><tr><td>SL</td><td>m({C})=0.567，m({C,V})=0.351，m({C,V,S})=0.082</td></tr><tr><td>PW</td><td>m({C})=0.955，m({C,V})=0.045，m({C,V,S})=0</td></tr><tr><td>PL</td><td>m({C})=0.967，m({C,V})=0.033，m({C,V,S})=0</td></tr></table></body></html>

# 3.2核函数和窗宽选择的实验

kde中有两个重要因素窗宽 $h$ 和核函数，每个因素都会对结果产生影响，本节给出这两个因素变化时本文方法在UCI数据集上5折交叉验证的准确率对比。

首先是对采用不同核函数时UCI数据集的准确率对比由图8给出。总体效果来看使用高斯核函数（normal）的效果是最好的，就数据集分别看，在Iris、Heart、Australian三个数据集上使用不同核函数的效果相当，在Zoo和Sonar数据集上略有差距。接着在高斯核函数的条件下验证不同窗宽h对准确率的影响，结果由图9给出。可以看出采用最优化窗宽的准确率明显比使用默认窗宽要高，这是因为优化的窗宽是根据不同属性及不同类别的数据特征进行具体求解的，所以相比所有数据都用一个窗宽来讲可以更加准确地反映数据的特征，进而产生更高的准确率。

![](images/2234fd00fe71d83179c66fbb7e7b0250614b31b69050947cfdab9825b9048175.jpg)  
图8不同核函数下本文方法的准确率对比

![](images/693e94d2f0ec18f69a89b070da2521ce6afb477f02fceab848356a86549abbbc.jpg)  
Fig.8Accuracy of proposed method under different kernel functions   
图9各数据集使用优化h、默认 $h$ 的准确率对比Fig.9Accuracy of optimized $h$ and default $h$ on data sets

# 3.3UCI数据集上的分类实验

本实验通过与七个被大家熟知的分类器及另外三种BPA生成的方法进行对比实验说明本文方法的有效性。由表5可以看出，所采用的数据集在表中给出的样例数、类别数、属性及是否有缺失值四个方面都不尽相同，用于实验可以较全面地展现方法的有效性。5折交叉验证的实验结果如表6所示。

Table 5Basic information of five UCI data sets   

<html><body><table><tr><td>数据集</td><td>样例数</td><td>类别数</td><td>属性</td><td>是否有缺失值</td></tr><tr><td>Iris</td><td>150</td><td>3</td><td>4</td><td>无</td></tr><tr><td>Heart</td><td>270</td><td>2</td><td>13</td><td>无</td></tr><tr><td>Australian</td><td>690</td><td>2</td><td>14</td><td>有</td></tr><tr><td>Z00</td><td>101</td><td>7</td><td>16</td><td>无</td></tr><tr><td>Sonar</td><td>208</td><td>2</td><td>60</td><td>无</td></tr></table></body></html>

表6数据集分类正确率 $\%$

表5UCI数据集的基本信息  
Table 6Classification accuracy of five data sets $\%$   

<html><body><table><tr><td rowspan="2"></td><td colspan="6">分类器</td><td colspan="3">BPA 生成方法</td></tr><tr><td>数据集 NB IB1</td><td></td><td></td><td></td><td>REPTreeSVMSVM-RBF MPRBFN</td><td>方法 1[12]</td><td>方法 2[19]</td><td>方法 3[18]</td><td>本文方 法</td></tr><tr><td>Iris</td><td>94.67</td><td>94</td><td>92</td><td>94.67</td><td>92.7</td><td>93.33 92.67 95.33</td><td>94</td><td>94.67</td><td>96</td></tr><tr><td>Heart</td><td></td><td>82.59 57.78</td><td>70.74</td><td>83.70</td><td>82.96</td><td>75.19 81.85 76.3</td><td>75.1</td><td>81.5</td><td>83.73</td></tr><tr><td>Australian79.56 67.4</td><td></td><td></td><td>80.59</td><td>80.29</td><td>79.86</td><td>82.32 82.61 78.41</td><td>80.6</td><td>80.01</td><td>82.32</td></tr><tr><td>Z0o</td><td>93.1</td><td>94.1</td><td>84.2</td><td>84.1</td><td>72.3</td><td>93.1 93.1 90.5</td><td>84.1</td><td>93.1</td><td>94.2</td></tr><tr><td>Sonar</td><td></td><td>66.28 79.78</td><td>70.70</td><td>66.32</td><td>65.90</td><td>66.86 66.84 65.5</td><td>66.58</td><td>65.57</td><td>67.5</td></tr><tr><td></td><td>Average 83.2478.61</td><td></td><td>79.65</td><td>81.82</td><td>78.74</td><td>82.16 83.41 81.21 80.08</td><td></td><td>82.97</td><td>84.75</td></tr></table></body></html>

通过表6结果本文可以看出，本文方法在各个特征都不尽相同的UCI数据集上的分类准确率整体优于其他几种常见的分类器，同时也优于其他几种BPA 生成方法，其他几种

BPA生成方法与分类器相比表现较平均。本文及对比BPA生成法在Sonar数据集上的表现均偏差，就本文方法初步考虑可能是由于特征较多，在将测试数据对应生成的多条BPA进行融合的过程中融合结果出现偏差导致，但整体来说，本文方法效果还是不错，说明本文方法可以有效地由包含不同特征的数据信息生成BPA即证据供D-S证据理论可以直接融合使用。

# 4 结束语

在D-S证据理论应用的过程中，基本概率指派(BPA)的生成方法仍然是一个开放性的问题，本文提出了一种基于核密度估计的BPA生成方法：首先构建训练数据优化的核密度属性模型；然后根据所提出的Tri-D的概念计算并分配得到测试数据的BPA，通过D-S组合得出最后的结果:本文方法具有主观性弱，BPA之间冲突小的优点。实验结果表明了所提方法的有效性；但在维数较高的数据集上进行BPA生成及后续应用还存在一定不足，下一步将针对此方面考虑结合改进融合方法进行思考和改进。

# 参考文献：

[1]Dempster AP. Upper and lower probabilities induced by a multivalued mapping [J].Annals of Mathematical Statistics,1967,38 (2): 325-339.   
[2] Shafer G.A mathematical theory of evidence [M]. NewJersey: Princeton University Press,1976.   
[3]何晶晶，蔡德胜，介飞，等．利用D-S证据理论进行特征融合的同义 实体识别[J].计算机应用研究，2018，35(5)：1429-1433.(He Jingjing,Cai Desheng,Jie Fei,et al. Synonymous entity recognition based on D-S evidence theory for feature fusion [J].Application Research of Computers,2018,35(5):1429-1433.)   
[4] 门志远，李林宏，张耀辉．基于改进证据理论的齿轮技术状态评估 方法[J]．火力与指挥控制，2018，43(5):65-68.(Men Zhiyuan,Li Linhong, Zhang Yaohui. State evaluation method of gear technology based on improved evidence theory [J].Fire Control & Command Control,2018,43(5): 65-68.)   
[5]余思奇，景博，黄以锋．基于D-S 证据理论的测试性综合评估方法 [J].计算机应用研究，2014，31（7):2071-2073.(Yu Siqi，Jing Bo, Huang Yifeng. Test-based comprehensive evaluation method based on D-S evidence theory [J].Application Research of Computers,2014,31 (7): 2071-2073.)   
[6]Xu Xiaobin,Zheng Jin,Yang Jianbo,et al.Data classification using evidence reasoning rule [J]. Knowledge-Based Systems,2017,116 (1): 144-151.   
[7]李英．基于多分类器 DS 证据理论融合的杂草识别 [J].电脑编程技 巧与维护,2018 (2):145-146,153.(Li Ying.Weed identification based onmulti-classifier DSevidence theory fusion [J]. Computer Programming Skills & Maintenance,2018 (2):145-146,153.)   
[8]Boccaleti S,Bianconi G,Criado R,et al.The structure and dynamics of multilayer networks [J].Physics Reports,2014, 544(1):1-122.   
[9]Burkov A,Chaib-Draa B.Computing equilibria in discounted dynamic games [J].Applied Mathematics & Computation，2015,269(10): 863-884.   
[10] Wang Zhen,Wang Lin,Szolnoki A,et al.Evolutionary games on multilayer networks: a colloquium [J].European Physical Journal B, 2015, 88 (5): 124.   
[11] Yager R R.A class of fuzzy measures generated froma Dempster-Shafer belief structure [J]. International Journal of Intelligent Systems,1999,14(12):1239-1247.   
[12]蒋雯，陈运东，汤潮，等．基于样本差异度的基本概率指派生成方法 [J].控制与决策,2015,30(1):71-75.(Jiang Wen,Chen Yundong,Tang Chao,et al.Basic probability assignment generation method based on sample difference degree [J].Control and Decision，2015,30(1): 71-75.)   
[13]涂世杰，陈航，冯刚．证据理论与模糊函数相结合的弹道目标识别 [J].计算机工程与应用,2017,53(6):169-173.(Tu Shijie,Chen Hang, Feng Gang.Ballistic target recognition based on evidence theory and fuzzy function [J].Computer Engineering and Applications,2017,53 (6): 169-173.)   
[14] Jiang Wen,Yang Yan,Luo Yu,et al.Determining basic probability assignment based on the improved similarity measures of generalized fuzzy numbers [J]. International Journal of Computers Communications & Control,2015,10(3):333-347.   
[15] Liu Yuting,Pal N R，Marathe A R,et al. Weighted fuzzy Dempster-Shafer framework for multimodal information integration [J]. IEEE Trans on Fuzzy Systems,2018,26(1): 338-352.   
[16] Zhang Chenwei,Hu Yong,Chan Felix T.S,et al.A new method to determine basic probability assignment using core samples[J]. Knowledge-Based Systems,2014,69(1):140-149.   
[17] Deng Xinyang,Liu Qi,Deng Yong，et al.An improved method to construct basic probability assignment based on the confusion matrix for classification problem [J].Information Sciences,2016,340-341: 250-261.   
[18]高智勇，董荣光，高建民，等．采用聚类特征的基本概率分配生成方 法及应用[J]．西安交通大学学报,2016,50(10):8-14.(Gao Zhiyong, Dong Rongguang,Gao Jianmin,et al. Basic probability distribution generation method and application using clustering features [J]. Journal of Xi'an Jiaotong University,2016,50(10):8-14.)   
[19]陈亚男，任圣君．大样本条件下证据基本概率指派函数生成方法研 究[J].信息工程大学学报,2017,18(4):118-122.(Chen Yanan,Ren Shengjun.Research on generating probability assignment function of evidence under large sample conditions [J]. Journal of Information Engineering University,2017,18(4):118-122.)   
[20] Mahadevan S,Deng Yong,Xu Peida,etal.A new method to determine basic probability assignment from training data [J]. Knowledge-Based Systems,2013,46(1):69-80.   
[21]李民政，蓝剑平．改进的基于Pignistic 概率距离的证据组合方法 [J]. 桂林电子科技大学学报，2017,37(4):63-67.(Li Minzheng,Lan Jianping.Improved evidence combination method based on Pignistic probability distance [J].Journal of Guilin University of Electronic Technol0gy,2017,37(4): 63-67.)   
[22] Rosenblatt M.Remarks on some nonparametric estimates of a density function [J].Annals ofMathematical Statistics,1956,27 (3): 832-837.   
[23] Parzen E.On estimation of a probability density function and mode [J]. Annals of Mathematical Statistics,1962,33 (3):1065-1076.   
[24] Bolancé C,Guillen M,Nielsen JP.Kernel density estimation of actuarial loss functions [J].Insurance Mathematics & Economics,2009, 32 (1): 19-36.   
[25] Arthur D.K-means+: the advantages of careful seeding [C]//Proc of the 18th Annual ACM-SIAM Symposium on Discrete Algorithms. Philadelphia,PA,USA:Society for Industrial and Applied Mathematics, 2007:1027-1035.