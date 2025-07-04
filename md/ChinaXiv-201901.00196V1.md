# 基于曲率信息的人工蜂群点云配准算法

付鲲1，陈雷1,2

(1．天津大学 电气自动化与信息工程学院，天津 300072;2.天津商业大学 信息工程学院，天津 300134)

摘要：针对仅使用群智能优化算法及点云空间信息进行点云配准时，优化过程寻找两片点云对应点耗时较长，收敛速度较慢的缺点，提出一种基于曲率信息的人工蜂群点云配准算法。算法根据曲率信息提取特征点，通过改进人工蜂群算法优化目标函数得到可以使两片点云重合的最佳变换矩阵。在种群优化过程中根据曲率信息约束对应点寻找范围，缩小参与计算点云的规模。对比实验表明，与仅采用随机选点方法和使用点云空间坐标信息的配准算法等相比，所提出算法可以在不降低配准精度的同时，有效加快配准收敛速度，显著缩短点云配准所用时间。

关键词：点云；曲率信息；特征点选取；对应点寻找；人工蜂群算法 中图分类号：TP751.1 doi: 10.19734/j.issn.1001-3695.2018.10.0732

Point cloud registration based on artificial bee colony algorithm and curvature information

Fu Kun1, Chen Lei1,2 (1.SchoolofElectrical&Information Engineering,Tianjin UniversityTanjin3o72,China;2.SchoolofInformation Engineering,Tianjin UniversityofCommerce,Tianjin 30o134,China)

Abstract: Some methods forpoints cloud registrationonlyuse theswarm intellgenceoptimizationalgorithmandthe points spatialinformation.Those methods have such shortcomings as slow convergence speed and long time consuming.To overcome these weaknes,this paper proposed a registration algorithmbased on the curvature information of points cloud. The algorithm extracted feature pointsaccording tothecurvature information.And itobtained the best transformation matrix to makethetwo pointcloud coincide bythe improvedartificial beecolonyalgorithm.Inthe process of population optimization,thecoresponding points were searchedaccording to thecurvature information,and the scaleof point cloud was reduced.The experimental results show that compared with the registrationalgorithmonly using random point selection method and point cloud spatialcoordinate information,the proposed algorithmcan efectively acelerate the convergence speed and significantly shorten the registration time without reducing the registration accuracy.

Key words: pointcloud;informationof points’curvature;seletionoffeaturepoints;search forthecorrsponding points; artificial bee colony

# 0 引言

三维成像是针对某一实际物体，用三维扫描设备从不同角度采集该物体三维点云数据，并形成被测物体的三维完整形貌。在三维成像领域，三维点云的配准技术是至关重要的，它的任务是找到一个最优欧式变换，使同一物体从不同角度得到的有部分重叠的点云变换到同一坐标系下，最终恢复出被测物体的完整形貌。

三维点云的配准过程实质上是一个最优化过程。在求解该最优化问题时，传统的配准方法容易受到量化误差、点云噪声和点云初始位置的影响。比如经典的点云配准算法迭代最近点（iterativeclosestpoints，ICP）算法[1]在待配准点云初始位置不佳时往往会陷入局部极值而导致配准失败。尽管已经有一些学者提出了改进的ICP算法。如，Chen 等人[2]在ICP算法基础上，选取了点到对应点切平面的距离中值而不是对应点之间的距离中值作为配准的目标函数进行配准。文献[3]采用主成分分析法先进行粗配准，再采用一种基于曲率特征点的改进ICP算法进行细配准。然而这些改进算法依然存在配准易陷入局部收敛的缺点。

近些年，群智能优化算法作为新兴的最优化方法，被广泛应用于解决各种工程优化问题。文献[4\~7]将粒子群优化算法用于工业系统永磁同步电机的参数估计中，有效提高了系统性能。文献[8在语音识别算法中引入了粒子群优化算法，提高了语音识别算法的成功率。文献[9]在数字图像处理算法中使用了蜂群优化算法，解决了数字图像水印技术中存在的误报问题。文献[10]将蚁群优化算法应用到嵌入式系统设计中，成功实现了软硬件的双路规划。

在三维成像领域，由于群智能优化算法优异的全局优化能力，基于群智能优化的点云配准技术也开始逐渐成为研究热点，并已表现出优于传统方法的明显优势。例如Cordon等人[11]提出了基于细菌算法的图像配准算法；Santamaria[12]提出了基于CHC算法的图像配准算法；Agrawal等人[13]提出了基于进化刚体对接算法的图像配准算法等。

虽然这些基于群智能优化的三维点云配准算法比较好地弥补了传统基于梯度优化的配准算法的缺点，有效提升了点云配准过程的适应性和配准精度。但该类算法需要经过多次迭代进化得到精准的配准结果，而每一次迭代进化过程中，需针对种群个体计算目标函数值，计算量较大。因此，在保证点云配准精度的同时，减少迭代进化过程计算量，缩短配准时间，就成了众多学者关注的重点。

为此，本文提出一种基于曲率信息的人工蜂群（artificialbee colonyalgorithm,ABC）[14]点云配准算法。首先，算法通过随机采样和根据点云曲率信息采样两种方式提取部分点云，之后，在寻找对应点阶段根据点云曲率范围的不同，排除待配准点云中曲率范围相差较大的部分点云，从而缩小了对应点的寻找范围，减少算法计算量；最后，通过人工蜂群算法优化求解目标函数得到待配准点云之间的空间最优变换。对比实验可以有效证明，本算法利用点云曲率信息限制了种群迭代进化过程中寻找对应点的范围，在保证配准精度的前提下，有效缩短了配准时间，提高了配准成功率。

# 1 点云配准模型

点云配准的目的是将通过传感器扫描得到的不同视角的点云合并到同一三维坐标系下，得到物体的完整几何模型。在空间坐标系中，物体模型的刚性变换可以用一个旋转平移矩阵表示，本文称这个矩阵为 $T$ 。对于待配准的动态点云$P = \{ p , \} , i = 1 , 2 , \cdots , N _ { p }$ 和静态点云 $\mathcal { Q } = \{ q , \} , j = 1 , 2 , \cdots , N _ { q }$ ，就是要获得两片点云间的最优欧式变换矩阵 $T$ ，使两点云重合部分的对应点在空间坐标系中完全重合。该变换矩阵包含6个待定参数，分别为沿三个坐标轴的平移量 $T _ { \ast } , T _ { \ast } , T _ { \ast }$ 以及绕3个坐标轴的旋转角 $\alpha , \beta , \gamma$ 。在不考虑模型大小伸缩的情况下，变换矩阵 $T$ 的表达式为

$$
T = R _ { x } R _ { y } R _ { z } S
$$

其中：

$$
R _ { x } = { \left[ \begin{array} { l l l l } { 1 } & { \quad 0 } & { \quad 0 } & { \quad 0 } \\ { \quad } & { \quad } & { \quad } & { \quad } \\ { \quad 0 } & { \quad \cos \alpha } & { \quad \sin \alpha } & { \quad 0 } \\ { \quad } & { \quad } & { \quad } & { \quad } \\ { \quad 0 } & { \quad - \sin \alpha } & { \quad \cos \alpha } & { \quad 1 } \\ { \quad } & { \quad } & { \quad } & { \quad 0 } & { \quad 1 } \end{array} \right] }
$$

$$
R _ { \gamma } = \left[ \begin{array} { c c c c } { \cos \beta } & { 0 } & { - \sin \beta } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \cos \beta } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } \end{array} \right]
$$

$$
\begin{array} { r } { R _ { z } = \left[ \begin{array} { c c c c } { \cos \gamma } & { \sin \gamma } & { 0 } & { 0 } \\ { - \sin \gamma } & { \cos \gamma } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 1 } \end{array} \right] } \end{array}
$$

$$
S = { \left[ \begin{array} { l l l l } { 1 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } \\ { T _ { x } } & { T _ { r } } & { T _ { z } } & { 1 } \end{array} \right] }
$$

在理想状态下， $P$ 中一点 $p _ { i }$ 经过 $T$ 变换后得到的点 $T ( p _ { i } )$ 与其在 $\varrho$ 中的对应点 $q _ { j }$ 之间的距离应当为0。实际上，它们的距离可以表示为

$$
\boldsymbol { d } _ { \iota } = \left\| \boldsymbol { T } ( \boldsymbol { P } _ { \iota } ) - \boldsymbol { \mathcal { Q } } _ { \iota } \right\| _ { \iota }
$$

但是由于测量误差以及噪声等因素的影响，对应点之间的距离无法达到理想值0，所以点云配准问题就转换为了优化问题：寻求一个最优的变换矩阵 $T$ 使得所有对应点对 $T ( p _ { i } )$ 与 $q _ { j }$ 之间的欧氏距离最小，即

$$
E _ { i } ( T ) = \operatorname* { m i n } _ { \tau } \big [ \big | T ( P _ { i } ) - Q _ { \mathbf { \varepsilon } } \big | \big ]
$$

结合人工蜂群优化算法，将对应点距离中值作为目标函数 $F ( T )$ ：

$$
F ( T ) = M e d S E \left\| d _ { \cdot } \right\| ^ { 2 }
$$

其中： $M e d S E$ 表示两片待配准点云中每一对对应点距离平方 $d _ { \cdot } ^ { \cdot }$ 的中值。

# 2 改进的人工蜂群算法

人工蜂群算法是Karaboga 等人模仿蜜蜂采蜜过程提出的，已被广泛应用于寻找多维优化问题中的最优解[15\~17]。该算法将优化问题中的每一个解看做是一个食物源。每一个食物源有优劣之分，其优劣由各种因素决定，包括食物源的地理位置、食物的多少和获取的难易程度等。对于每一个优化问题，都有一个目标函数来评价每一个解的优劣。

整个蜂群有三种蜜蜂，分别是采蜜蜂、观察蜂和侦查蜂。采蜜蜂各自寻找到一个食物源，即多维优化问题的一组解，每次优化迭代都改变这组解的部分信息得到新的解，通过比较目标函数值的优劣，保留两者中最优的一个。然后采蜜蜂将这个食物源的信息带回蜂巢，以蜜蜂间特有的方式以一定概率将它所携带的食物源信息传达给观察蜂，观察蜂同样对接收到的信息作出部分改变得到新的解并择优保留。此后经过一定次数的循环，如果经过规定优化次数，观察蜂没有得到更好的食物源，则放弃所携带的信息，转变为侦查蜂，并寻找一个新的食物源。

在基本ABC算法中，采蜜蜂和观察蜂共用同一个搜索方程来对所携带信息作出改变，搜索方程如下：

$$
V _ { i , j } = X _ { i , j } + \phi _ { i , j } ( X _ { i , j } - X _ { k , j } )
$$

其中： $\phi _ { i , j }$ 是 $[ - 1 , 1 ]$ 之间的随机数.

对于解决复杂度高的多维非线性优化问题，人工蜂群算法作为群智能优化算法的一种，具有控制参数少、全局收敛性好、易于实现等优势，通过不同工种蜜蜂之间的合作，能快速准确的获得全局最优解，具有比传统遗传算法、粒子群算法等群智能优化算法更好的优化性能。

然而基本人工蜂群算法在局部区域内的开发能力不足，往往导致优化过程难以快速收敛。针对此问题，同时受差分进化算法（DE）[18]的启发，高卫峰提出了一种 EABC算法（enhancing artificial bee colony algorithm,EABC）[19]。该算法采用以下两个公式分别作为采蜜蜂和观察蜂的搜索方程：

$$
\begin{array} { r l } & { V _ { i , j } = X _ { , 1 , j } + \alpha ( X _ { _ { k e n , j } } - X _ { _ { r 1 , j } } ) + } \\ & { \beta ( X _ { _ { r 1 , j } } - X _ { _ { k e n , j } } ) } \\ & { V _ { i , j } = X _ { _ { r 1 , j } } + \alpha ( X _ { _ { k e n , j } } - X _ { _ { r 1 , j } } ) + } \\ & { \beta ( X _ { _ { r 1 , j } } - X _ { _ { r 2 , j } } ) } \end{array}
$$

其中： $X _ { _ { b e w , f } }$ 为当前群体的最优个体； $r 1 \neq r 2 \neq i$ 是从集合 $\{ 1 , 2 , \cdots , N P \}$ 中随机选择的整数； $\mathrm { j }$ 是一个随机选择的整数， $j \in \left\{ 1 , 2 , \cdots , D \right\}$ 。 $\alpha$ 是[0.A]之间的一个随机数， $\beta$ 为 $r a n d * B$ ，这里 $\mathbf { B }$ 是一个均值为 $\mu$ ，标准差为 $\sigma$ 的高斯分布数。采蜜蜂和观察蜂分别对应的两个搜索方程由于既有当前群体的最优个体 $X _ { _ { b a r } }$ 的引导又有 $X _ { r 1 } - X _ { r 2 }$ 的扰动，在一定程度上保持了种群的多样性，可以为搜索过程带来更多有用的信息，所以可以产生一个更有前途的候选解以此来提高算法的性能，且该搜索方程在一定程度上平衡了算法的探索和开发能力。

# 3 基于点云曲率信息的人工蜂群配准算法

点云配准过程一般存在计算量大、时间复杂度高以及对应点寻找不准确等问题。针对以上问题，近年来有许多学者在点云的粗配准过程中使用了点云的特征点信息，如局部曲率特征信息[20]、FPFH特征信息[21]、LSP特征信息[22]等。点云特征信息的使用，在有效减小参与计算点云规模的同时，为对应点的匹配提供了独特的特征信息。例如点云的不同位置曲率大小一般差别较大，利用点云的局部曲率信息，可以有效减小对应点误匹配的概率。

由于点云的特征点信息目前还主要运用在点云粗配准过程中，应进一步考虑将特征点信息和群智能优化算法相结合解决配准问题。因此，本文提出一种基于曲率信息的人工蜂群点云配准算法。

该算法在初始点云中提取采样点时，采用随机提取和根据点云曲率信息分段提取的方法相结合，从而减小样本规模。提取出的点云既包含点云曲率信息，又可以保证较均匀地分布在待配准动态点云整体范围内。

在蜂群优化过程中不断得到变换矩阵T。采样点中的每一个点经过 $T$ 变换后，仅在相近曲率范围内的静态点云中寻找对应点。然后再计算所有对应点的距离中值平方作为蜂群优化算法的目标函数，寻找最优变换。以达到减少计算量，提高收敛速度的效果。

# 3.1基于点云曲率信息的特征点采样

针对点云 $\boldsymbol { \mathsf { \Sigma } } _ { P }$ 和 $\varrho$ 中的每一个点，采用基于 MLS 表面（moving least squares surfaces,MLS）[23]的方法计算得到各自的高斯曲率 $k _ { G a u s s i a n }$ 和平均曲率 $k _ { M e a n }$ 。并由此得到主曲率：

$$
k _ { 1 } = k _ { M e a n } - \sqrt { k _ { M e a n } ^ { 2 } - k _ { G a u s s i a n } }
$$

$$
k _ { 2 } = k _ { M e a n } + \sqrt { k _ { M e a n } ^ { 2 } - k _ { G a u s s i a n } }
$$

其中： $k _ { \ast } \setminus k _ { \ast }$ 是最小、最大主曲率。根据Chen等人的定义，本文用以下公式表示每一点的曲率信息[24]

$$
S ( p ) = { \frac { 1 } { 2 } } - { \frac { 1 } { \pi } } \arctan { \frac { k _ { \scriptscriptstyle { 1 } } ( p ) + k _ { \scriptscriptstyle { 2 } } ( p ) } { k _ { \scriptscriptstyle { 1 } } ( p ) - k _ { \scriptscriptstyle { 2 } } ( p ) } }
$$

其中：点 $\boldsymbol { p }$ 代表点云中的任意一点； $k _ { \ u { r } _ { 1 } } ( \ u _ { p } )$ 、 $k _ { \mathrm { } _ { z } } ( p )$ 和 $0 < S ( p ) < 1$ 分别代表点 $\boldsymbol { p }$ 的最小主曲率、最大主曲率和该点的曲率信息。此时点云可以表示为 $P = \{ p _ { i } , S _ { \ast } \} , i = 1 , 2 , \cdots , N _ { \ast }$ ， $\mathcal { Q } = \{ q _ { n } , S _ { n } \} , j = 1 , 2 , \cdots , N _ { \ast }$ 。

由于点云模型的不同，可能有些模型的点会大量聚集在某个曲率范围内。如果仅仅依靠曲率信息提取采样点，可能造成采样点云不能均匀地分布在初始点云的整体范围内，进而有可能导致点云配准陷入局部收敛而失败。

本文采用随机采样和根据曲率信息采样相结合的方式提取点云。点云中的每个点都有自己的曲率信息 $s$ ，把 $s$ 从0到1平均分为 $\mathbf { n }$ 段，这样每个点的曲率信息就属于其中的一段。依

据曲率信息所属范围不同，动态点云 $\textbf { \textit { P } }$ 可分为 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个点云子集 $P _ { k }$ ， $k = 1 , 2 , \cdots , n$ 。点云子集 $P _ { k }$ 中仅包含曲率信息 $s$ 满足式（15）的点：

$$
\frac { k - 1 } { n } = < S < \frac { k } { n }
$$

静态点云 $\varrho$ 可以分为 $\mathfrak { n }$ 个点云子集 $\mathcal { Q } _ { * }$ ， $w = 1 , 2 , \cdots , n$ 。点云子集 $\smash { \mathcal { Q } _ { \nu } ^ { \mathrm { ~ ~ } } }$ 中仅包含曲率信息 $s$ 满足式（16）的点。

$$
{ \frac { w - 1 . 5 } { n } } = < S < { \frac { w + 0 . 5 } { n } }
$$

如图1所示，这是 $\scriptstyle \mathtt { n } = 3$ 时，根据曲率信息 $s$ 划分点云的简单情况。

![](images/5dec256f72f0a57700627eba430ed9152cc79f41de37cbc997351844d76b370c.jpg)  
图1点云区域划分  
Fig.1Region division of point cloud

使用曲率信息对点云进行采样时，从1到 $\mathfrak { n }$ 中随机选取一个数字 $\mathbf { k }$ ，如果动态点云 $P$ 的子集 $P _ { \nu }$ 不为空，且在静态点云@中对应的子集 $\boldsymbol { \mathscr { Q } } _ { \ast }$ 也不为空，则从 $P _ { \nu }$ 中随机选取一点作为提取的特征点。循环此步骤，直到得到固定个数的曲率特征点为止。假设要根据点云曲率信息提取 $N _ { _ { \mathrm { \it { f r a t u r e } } } }$ 个特征点，则点云提取过程如图2所示， $P _ { \mathrm { a w v } / \omega d }$ 表示根据曲率信息提取的点云集合。

为了避免配准过程中局部拟合等因素导致的配准失败，再用随机采样的方式在点云 $P$ 中提取 $N _ { \mathrm { \it { n a i s e u } } }$ 个采样点，两部分点云结合起来构成最终用于配准的子点云。通过反复实验证明，在实际点云配准中， $n = 1 2$ ， $N _ { _ { f r e n e e } } : N _ { _ { r a n d o e } } = 2 : 1$ 时配准效果最佳。

# 3.2受曲率信息限制的目标函数

使用种群优化算法寻找最优变换矩阵时，要在优化过程中不断地寻找动态点云 $\boldsymbol { \mathsf { \Pi } } _ { P }$ 中的每一点在静态点云 $\varrho$ 中相对应的点，再由对应点对欧氏距离平方中值的大小来评价配准效果的优劣。点云配准的大部分时间都用在了寻找对应点上。为了减少寻找对应点所花费的时间，提出一种由点云曲率信息限制的目标函数 $\psi ( T )$ 0

对应点之间的曲率范围相差较小，所以在寻找动态点云$P$ 中一点 $\boldsymbol { p } _ { i }$ ，在静态点云 $\boldsymbol { \mathscr { Q } }$ 中的对应点时，无须在 $\boldsymbol { \mathscr { Q } }$ 的整体范围内寻找，只需要在曲率信息相差较小的范围内寻找即可。寻找到对应点之后，再计算对应点距离平方中值，所得结果作为优化算法的目标函数值。

![](images/a4f735c6bd56a61b0dc347007c771424425a28376906537be8a5a5ad720a90cc.jpg)  
图2样点采集示意图  
Fig.2Sample collection schematic diagram

这种寻找对应点的方法可以有效减少函数曲线局部极值点的个数，更易于搜索。此外，因为只需要在曲率信息相近的范围内寻找对应点，所以极大地缩小了查找范围，从而减少了查找对应点的时间。

在这个目标函数 $\psi ( T )$ 中，如图1所示，认为动态点云子集 $P _ { \varepsilon }$ 中点的曲率信息只和静态点云子集 $\scriptstyle Q _ { k }$ 中点的曲率信息是相近的。对于 $P _ { \ k }$ 中的点只需在 $\varrho _ { \star }$ 中寻找对应点。此外 $\scriptstyle Q _ { \varepsilon }$ 中点的曲率信息范围是包含 $P _ { \nu }$ 中点的曲率信息范围的，这样就避免了在用曲率信息分段边缘的点不能准确找到对应点。曲率信息为 $s$ 的点，其所属点云子集的序号 $\mathbf { k }$ 可以用式（17）所示。

$$
k = \Biggl \lfloor S / ( \frac { 1 } { n } ) \Biggr \rfloor + 1
$$

其中：」」表示向下取整。为了加快搜索速度，可以对静态点云的每一个子集 $\varrho _ { \star }$ 建立kd-tree 数据结构进行索引。

以下列出了优化算法目标函数 $\psi ( T )$ 的求解流程：

for $i = 1 , 2 , \cdots , N _ { \rho }$

a)使用优化过程得到的变换矩阵 $\boldsymbol { \tau }$ 对 $p _ { i }$ 进行旋转平移，得到点 $T ( \boldsymbol { p } _ { i } )$ ：b)根据式17计算得到 $p _ { \cdot }$ 的 $\boldsymbol { \mathsf { k } }$ 值；  
c)在 $\varrho _ { \star }$ 中寻找 $p _ { \cdot }$ 的对应点 $q _ { \iota }$ ：  
d)计算 $T ( P _ { \iota } )$ 与 $q _ { \cdot }$ 的欧式距离 $d _ { \ast } = \Vert T ( p _ { \ast } ) - q _ { \ast } \Vert _ { \ast }$ ：  
End  
e)由公式 $\psi ( T ) = M e d S E \left\| d _ { \cdot } \right\| ^ { 2 }$ 计算得到目标函数值。

# 4 实验结果及分析

# 4.1三维点云数据

配准实验所用三维点云模型分别为SAMPL点云库中的Tele、Bird、Angel以及frog点云模型。四种点云模型都选取0度视角和40度视角的两片点云。各模型0度视角所含点的个数分别为6841、9115、14089和9640，40度视角所含点的数量分别为5612、5872、13190和7650。配准时一片点云静正不动，另一片点云通过随机旋转平移变换后作为动态点云进行配准

# 4.2 配准实验设计

为了分析比较本文算法的配准性能，进行两组实验。

实验1：把使用了点云曲率信息的改进人工蜂群配准算法（以下简称本文算法）和仅使用点云空间坐标信息的改进人工蜂群配准算法（以下简称空间算法）作对比。表1所示为实验1中两种算法所用策略对比。

实验2：把本文算法和其他两种较为新颖的基于群智能优化算法的点云配准方法进行对比。

表1实验1算法策略对比  
Table 1Algorithm strategy comparison of experiment 1   

<html><body><table><tr><td>算法</td><td>优化算法</td><td>样点采集</td><td>目标函数</td></tr><tr><td rowspan="2">本文算法</td><td rowspan="2">EABC</td><td>曲率特征点+</td><td>曲率约束+</td></tr><tr><td>随机采样</td><td>距离中值</td></tr><tr><td>空间算法</td><td>EABC</td><td>随机采样</td><td>距离中值</td></tr></table></body></html>

# 4.3参数设置

实验用计算机硬件配置为IntelCore（TM）i7-4790处理器，主频 $3 . 6 \ \mathrm { G H z }$ ，内存 $1 6 ~ \mathrm { G B }$ 。操作系统为Windows8,所有算法均在matlabR2014a软件下编程实现。

本文使用的蜂群优化算法种群数目过多会降低点云配准效率，而种群数目过少则会导致配准可能无法成功。由预实验得到一组本文算法的控制参数。EABC中种群数量取20为宜，其中采蜜蜂和观察蜂各占一半。最大尝试次数 $\mathrm { l i m i t } { = } 5 0$ 高斯分布均值 $\mu = 0 . 3$ ，标准差 $\delta = 0 . 3$ ， $A = 1$ 。配准过程中选取各模型0度视角的点云作为动态点云 $\textbf { \textit { P } }$ ，从 $P$ 中选取300个点作为采样点用于配准过程。各模型动态点云 $P$ 在用于配准前，其空间坐标在 $[ - 4 0 \mathrm { m m } , 4 0 \mathrm { m m } ]$ 间随机平移，在(0.2)的角度范围内分别绕 $X$ ，Y， $Z$ 轴随机旋转。表2为EABC优化算法主要参数。

Table 2Parameter selection of EABC algorithm   

<html><body><table><tr><td>参数类别</td><td>参数值</td></tr><tr><td>种群数量</td><td>20</td></tr><tr><td>limit</td><td>50</td></tr><tr><td>采蜜蜂（观察蜂）数量</td><td>10</td></tr><tr><td>旋转角度范围</td><td>[0,360]</td></tr><tr><td>平移范围/mm</td><td>[-40mm,40mm]</td></tr><tr><td>高斯分布均值"</td><td>0.3</td></tr><tr><td>标准差δ</td><td>0.3</td></tr><tr><td>A</td><td>1</td></tr></table></body></html>

# 4.4实验1结果分析

经过多次实验对比得出，实验1中的两种算法大约在160s左右都可以收敛，因此约束实验运行时间为 $2 0 0 \ \mathrm { s } .$ 。在相同的时间内，每隔10s记录下蜂群中的最优变换向量 $\rho$ 。用向量 $\rho$ 对完整动态点云中的点 $p ,$ ， $i = 1 , 2 , \cdots , N _ { _ { p } }$ 做旋转平移变换，得到点云 $T ( p _ { _ i } )$ 。

计算 $T ( p _ { , } )$ 与静态点云 $\varrho$ 中对应点的距离平方中值 $\mid { \cal L } _ { , }$ ，$r = 1 , 2 , \cdots , 2 0$ 。其中， $\mathrm { ~ \bf ~ r ~ }$ 代表从迭代优化开始每隔10s记录一次 $\mathrm { ~  ~ \mathcal ~ { ~ L ~ } ~ }$ 的值，共记录20次。 $\iota ,$ 表示算法运行 $1 0 \times r$ s时，所有对应点的距离平方中值。最后用 $\iota ,$ ， $r = 1 , 2 , \cdots , 2 0$ 构造算法的收敛曲线，观察算法收敛对比效果。此外，针对各点云数据模型，分别设定判定配准是否成功的目标函数限定阈值：。目标函数值小于 $\{ \tau \}$ 则判定配准成功，否则视为失败。表3为针对各模型的阈值’。

表2EABC 算法参数选取  
表3判定各模型配准是否成功的阈值  
Table 3Threshold value to determine whether registration of each model is successful or not   

<html><body><table><tr><td>模型</td><td>τ(mm)</td></tr><tr><td>Bird</td><td>0.60</td></tr><tr><td>Tele</td><td>0.40</td></tr><tr><td>Angle</td><td>0.70</td></tr><tr><td>Frog</td><td>0.60</td></tr></table></body></html>

因为使用群智能优化算法进行点云配准存在随机性，存在较小概率会发生算法局部收敛的情况，失败的点云配准数据对平均数据影响较大，所以两种算法各自运行30次，舍弃配准失败时的数据，仅取配准成功时的平均数据对算法进行分析。

由于点云初始位置不确定，实验运行开始阶段，用于绘制收敛曲线的 $\boldsymbol { L } _ { \prime }$ 的值可能与最终收敛时的值相差较大，绘制的收敛曲线不便于观察收敛效果，所以使用50s之后的 $\boldsymbol { L } _ { \prime }$ 值来绘制收敛曲线。图3为各点云模型的收敛曲线。

将实验所得各点云模型的目标函数值与限定阈值：作比较可以得出，两种算法都可以达到收敛。观察图3可以看出，本文算法一般在100s之内可以达到收敛，而空间算法则收敛速度较慢，一般在150s左右才可以收敛。相同时间内，本文算法收敛速度更快。这是因为在本文算法的目标函数中引入了点云曲率信息，通过曲率的限制降低了函数复杂度，从而大大加快算法收敛速度。

表4记录了两种对比算法30次运行中的成功次数，在成功的次数中求取目标函数的平均值以及200s内迭代次数的平均值。可以看出本文算法与空间算法相比，本文算法运行30次仅仅在angel模型实验中有一次失败，成功率更高，而最终达到的精度较之空间算法并没有降低。同时，在相同时间内，本文算法迭代次数明显多于空间算法的迭代次数。这说明本文算法降低了每一次迭代的过程计算量。相同时间内，本文算法的迭代次数更多，从而使算法更快地达到收敛。

![](images/2fe308cf740c4277bc7a116c15b349b6296733adf1b3be323eb1418625a8fc53.jpg)  
图3实验1中各模型收敛曲线

Table 4Comparison of results in experiment 1   

<html><body><table><tr><td></td><td>点云模型 配准算法 成功次数</td><td>平均目标函数值（mm)</td><td>迭代次数</td></tr><tr><td rowspan="2">Bird</td><td>本文算法</td><td>30</td><td>0.2784 6614</td></tr><tr><td>空间算法</td><td>29</td><td>0.3057 3891</td></tr><tr><td rowspan="2">Tele</td><td>本文算法</td><td>30 0.2854</td><td>6974</td></tr><tr><td>空间算法</td><td>29</td><td>0.2698 4227</td></tr><tr><td rowspan="2">Angel</td><td>本文算法</td><td>30 0.4236</td><td>6283</td></tr><tr><td>空间算法</td><td>26 0.4508</td><td>3653</td></tr><tr><td rowspan="2">Frog</td><td>本文算法</td><td>29 0.3804</td><td>5766</td></tr><tr><td>空间算法</td><td>24 0.4065</td><td>3627</td></tr></table></body></html>

对于四种模型，采用本文算法在200s内迭代次数分别为6614次、6974次、6283次、5766次，采用空间算法的迭代次数分别为3891次、4227次、3653次、3627次。可以看出本文算法与空间算法相比，在相同时间内，迭代次数更多。这说明采用本文算法可以有效减少每一次迭代进化过程的计算量，因而相同时间内可以有更多的迭代次数，进而证明在达到相同配准精度标准时，本文算法计算量大大减少。

图4为使用本文算法得到的配准效果。从图中可以看出本文算法配准效果良好。

![](images/9e68c82a5f4b475ed9ef88bdf3a2d4eb6a56d4caccb6d9cf58322febcd13d6ce.jpg)  
图4本文算法配准效果 Fig.4Registration effected map of presented algorithm

# 4.5实验2结果分析

实验2中，将本文算法与2016年提出的基于改进ISS特征点与人工蜂群算法的点云配准方法（ABC2016）[25]和2014年提出的基于侵略模型的自适应分布式差分进化点云配准算法（DE2014）[26]作对比。实验2中本文算法采用和实验1中相同的实验参数、实验平台、点云数据模型、目标评价函数和相同的实验设计。其余两种算法所需主要优化过程参数见表5。

表4实验1结果对比  
表5实验2中各算法相关参数  

<html><body><table><tr><td>算法名称</td><td>优化过程参数</td></tr><tr><td>ABC2016</td><td>种群数量20，limit=100</td></tr><tr><td>DE2014</td><td>种群数量16，种群规模10, τ =30</td></tr></table></body></html>

同实验1，每种算法运行30次，每隔10s记录用当前最 优解所对应的目标函数值，并以此绘制各算法的收敛曲线。 各模型收敛曲线见图5

![](images/c68c5f5adefcf84f0b7b00cc7a6af19468deda456e35ad8fb2a90114e3dda972.jpg)  
Fig.3Convergence curves of models in Experiment 1   
图5实验2中各模型收敛曲线   
Fig.5 Convergence curves of models in Experiment 2

表5记录三种算法30次运行中的成功次数，最终的平均目标评价函数精度。

Table.5Parameters of each algorithm in experiment 2   
表5实验2结果对比  
Table 5Comparison of results in experiment 2   

<html><body><table><tr><td>点云模型</td><td>配准算法</td><td>成功次数</td><td>平均目标函数值</td></tr><tr><td rowspan="3">Bird</td><td>本文算法</td><td>30</td><td>0.2637</td></tr><tr><td>ABC2016</td><td>25</td><td>0.5094</td></tr><tr><td>DE2014</td><td>26</td><td>0.2936</td></tr><tr><td rowspan="3">Tele</td><td>本文算法</td><td>30</td><td>0.2865</td></tr><tr><td>ABC2016</td><td>29</td><td>0.3952</td></tr><tr><td>DE2014</td><td>28</td><td>0.2391</td></tr><tr><td rowspan="3">Angel</td><td>本文算法</td><td>30</td><td>0.4359</td></tr><tr><td>ABC2016</td><td>28</td><td>0.5903</td></tr><tr><td>DE2014</td><td>26</td><td>0.6248</td></tr><tr><td rowspan="3">Frog</td><td>本文算法</td><td>29</td><td>0.3710</td></tr><tr><td>ABC2016</td><td>26</td><td>0.5739</td></tr><tr><td>DE2014</td><td>24</td><td>0.3262</td></tr></table></body></html>

与实验1不同的是，实验2未统计相同时间内各算法迭代次数。这是因为各配准算法所用优化方法不同，种群粒子数目不同，导致无法比较同一时间内各种群的迭代进化次数。

观察图5可知，使用了点云曲率信息的本文算法与另外两种算法相比较，可以更快地达到收敛。同时由表5可以看出，与另两种算法相比，本文算法并未降低配准精度。此外其他两种算法的失败次数要多于本文算法，证明了本文算法拥有更好的稳定性。

# 5 结束语

本文通过对选取采样点以及寻找对应点过程的改进，提出了一种基于曲率信息的点云配准方法。首先，在提取点云预处理阶段，根据点云曲率信息采样与随机采样相结合的方式各提取一部分点。优化过程中根据点云曲率信息所属范围的不同减小寻找对应点的范围，从而减少寻找对应点的计算量。最后用改进的人工蜂群EABC算法找到点运之间的最佳变换向量。通过实验对比证明，本文算法可以达到良好的配准效果。此外与仅使用点云空间信息的蜂群优化配准算法，以及其他两种算法相比，本文算法可以在保证配准精度的同时更快达到收敛。同时在相同运行次数中，本文算法配准成功率更高。与传统群智能优化配准算法相比，本文算法有较强的竞争力。

# 参考文献：

[1]Besl PJ,Mckay N D.A method for registration of 3-D shapes [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,1992,14 (2): 239-256.   
[2] Chen Y,Medioni G. Object modeling by registration of multiple range images [J].Image and Vision Computing,1992,10 (3):145-155.   
[3]杨现辉，王惠南.ICP算法在3D点云配准中的应用研究[J].计算机 仿真,2010,27(8):235-238.(Yang Xianhui,Wang Huinan.Application research of ICP algorithm in 3D point cloud alignment [J].Computer Simulation,2010,27(8):235-238.)   
[4]Liu Zhaohua,Wei Hualiang,Li Xiaohua,et al.Global identification of electrical and mechanical parameters in PMSM drive based on dynamic self-learning PSO [J].IEEE Trans on Power Electronics,2018,33 (12): 10858-10871.   
[5]Liu Zhaohua,Wei Hualiang，Zhong Qingchang，et al.Parameter estimation for VSI-Fed PMSM based on a dynamic PSO with learning strategies [J].IEEE Transon Power Electronics，2017，32 (4): 3154-3165.   
[6] Liu Zhaohua,Wei Hualiang，Zhong Qingchang，et al.GPU implementation of DPSO-RE algorithm for parameters identification of surface PMSM considering VSI nonlinearity [J].IEEE Journal of Emerging and Selected Topics in Power Electronics,2017,5 (3): 1334-1345.   
[7]Liu Zhaohua, Zhang Jing, Zhou Shaowu,et al. Coevolutionary particle swarm optimization using AIS and its application in multi-parameter estimation of PMSM [J]. IEEE Trans on Cybernetics,2013,43 (6): 1921-1935.   
[8]Yogesh C K,Hariharan M,Ngadiran R,et al.A new hybrid PSO assisted biogeography-based optimization for emotion and stress recognition from speech signal [J]. Expert Systems with Applications, 2017,69:149-158.   
[9] Ansari I A,Pant M,Ahn C W. ABC optimized secured image watermarking scheme to find out the rightful ownership [J]. International Journal for Light and Electron Optics,2016,127 (14): 5711-5721.   
[10]张煜东，吴乐南，韦耿．基于正负反馈机制的蚁群算法用于软硬件 划分[J]．电子测量与仪器学报,2009,23(8):32-38.(Zhang Yudong, Wu Yuenan,Wei Geng.Application of improved ant colony algorithm based on forward/backward feedback in hardware/software partition [J]. Journal of Electronic Measurement and Instrument.2009,23 (8): 32-38.)   
[11] Bermejo E,Cordón O,Damas S,et al.A comparative study on the application of advanced bacterial foraging models to image registration [J]. Information Sciences,2015,295:160-181.   
[12] Cordon O,Damas S, Santamaria J. Feature-based image registration by means of the CHC evolutionary algorithm [J]. Image and Vision Computing,2006,24(5): 525-533.   
[13] Panda R,Agrawal S,Sahoo M,et al.A novel evolutionary rigid body docking algorithm for medical image registration [J].Swarm and Evolutionary Computation,2018,42:138-159.   
[14] Karaboga D.An idea based on honey bee swarm for numerical optimization, Technical Report-TR06,[R].Kayseri， Turkey:Erciyes University,2005.   
[15] Cao Yongcun,Pan Xiuqin,Lu Yong. An improved global best guided artificial bee colony algorithm for continuous optimization problems [J]. Cluster Computer,2018 (1):1-9.   
[16] Zhu Guopu,Kwong S.Gbest-guided artificial bee colony algorithm for numerical function optimization [J].Applied Mathematicsand Computation,2010,217(7): 3166-3173.   
[17] Singh A.An artificial bee colony algorithm for the leaf-constrained minimum spanning tree problem [J]. Applied Soft Computing,2008, 9 (2): 625-631.   
[18] Storn R,Price K.Differential Evolution:a simple and efficient heuristic for global optimization over continuous spaces [J]. Journal of Global Optimization,1997,11 (4): 341-359.   
[19] Gao Weifeng,Liu Sanyang,Huang Lingling. Enhancing artificial bee colony algorithm using more information-based search equations [J]. Information Sciences,2014,270 (1): 112-133.   
[20] Ge Baozhen,Peng Bo,Tian Qingguo.Registration of three-dimensional point-cloud data based on curvature map[J]. Journal of Tianjin University: Science and Technology,2013,46 (2): 174-180.   
[21] Rusu R B,Blodow N,Beetz M. Fast point feature histograms (FPFH) for 3D registration [C]//Proc of IEEE International Conference on Robotics and Automation.2009:3212-3217.   
[22] Chen H,Bhanu B.3D free-form object recognition in range images using local surface patches [J]. Pattern Recognition Letters,2007,28 (10):1252-1262.   
[23] Ding Zhongming,Kawamura T, Sakamoto N,et al.Particle-based multiple irregularvolume rendering on CUDA [J]. Simulation Modelling Practice and Theory,2010,18 (8):1172-1183.   
[24]马忠玲，周明全，耿国华等．一种基于曲率的点云自动配准算法 [J]. 计算机应用研究，2015，32(6):1878-1880.(Ma Zhongling，Zhou Mingquan， Geng Guohua.Automatic registration algorithm for scatered point clouds based on curvature feature [J]. Application Research of Computers,2015,32 (6): 1878-1880.）   
[25]葛宝臻，周天宇，陈雷，等．基于改进ISS 特征点与人工蜂群算法的 点云拼接方法[J]．天津大学学报：自然科学与工程技术版，2016, 49 (12):1296-1302.(Ge Baozhen, Zhou Tianyu,Chen Lei,et al. Point clouds registration algorithm based on improved ISS feature points and artificial bee colonyalgorithm [J].Journal of Tianjin University: Science and Technology,2016,49 (12): 1296-1302.)   
[26]Falco I D,Cioppa A D，Maisto D,et al.Using an adaptive invasion-based model for fast range image registration[C]//Proc of GECCO'14 Conference on Genetic and Evolutionary Computation. New York:ACMPress,2014.