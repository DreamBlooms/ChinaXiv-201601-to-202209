# 基于差异性采样的流数据聚类算法\*

邱云飞，孙梦冉

(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：针对传统聚类算法对流数据进行聚类时面临时间复杂度高，存储空间需求大以及准确度较低的问题，提出一种基于差异性采样的流数据聚类算法。首先利用差异性采样法对流数据进行采样并用样本点构造核矩阵，然后利用核模糊C均值聚类算法对核矩阵中的点进行聚类得到一个带有标记的样本核矩阵，最后利用带有标记的样本核矩阵对流数据中的点进行划分。同时利用衰退聚类机制，实时更新样本核矩阵。实验结果表明，相比于传统聚类算法，该算法实现了更低的时间复杂度，同时实时聚类，得到较为理想的聚类结果。

关键词：差异性采样；衰退聚类机制；核模糊C均值；流数据；时间复杂度 中图分类号：TP391.9 doi:10.3969/j.issn.1001-3695.2017.12.0808

# Stream data clustering algorithm based on differential sampling

Qiu Yunfei, Sun Mengran† (College of Software Liaoning Technical University,HuLudao Liaoningl25105,China)

Abstract: Concerningthe problems ofhightimecomplexity,largestoragespacerequirementsandlowaccuracywhentraditional clusteringalgorithmclusterstream data,thispaper proposedakindof stream data clusteringalgorithmbasedondifferential sampling.First,itusedthdiferentialsamplingmethodsampledstreamdata,andusedsamplepointstoconstructkerelmatrix. Then itused kernel fuzzyC-means clustering algorithm clustered thedata pointsin the kernel matrix,obtained amarked sample kernel matrix.Finally,using themarked kernelmatrix divided thestreamdata.Meanwhile,this paperadoptedthefadingcluster mechanism toupdate kernel matrix inreal time.Experimental results show thatcompared with the traditional clustering algorithm,theproposedalgorithmachieves lowertimecomplexityreal-timeclusteringatthesam time,gettheidealclustering result.

Key words: differential sampling; fading cluster mechanism; kernel fuzzy C-means; stream data; time complexity

# 0 引言

近年来，对流数据进行聚类分析成为数据挖掘领域中的热点问题。但由于流数据到达的实时性、数据结构的不稳定性、数据量的无限性，利用传统聚类算法很难进行有效的聚类。为了解决以上问题，Aggarwal等人[1]提出一种流聚类算法（CluStream算法）。该算法通过在线维护 $( 2 \mathrm { d } \substack { + 3 } )$ 维的微簇产生高质量的簇提升流数据聚类的准确性及效率，但对高维数据处理效率不高。文献[2]提出一种自适应非线性流聚类算法，应用核异常检测方法按照时间的局部性将流数据分成若干部分，并对每一部分进行聚类，自适应选取具有代表性的部分作为初始的类对流数据中的其他点进行聚类。该算法虽然减小了时间复杂度及对存储空间的利用，但没有考虑数据点本身的数据信息在流数据中的影响程度，因此聚类效果并不理想。文献[3]提出一种基于密度与网格的流聚类算法，将数据映射到网格空间中对应的网格之中，根据密度在网格空间中进行聚类。该算法利用数据本身的特性对流数据进行聚类，但是由于流数据数量的无限性，导致该算法的时间复杂度较高。文献[4]提出一种基于采样的流聚类算法（approximate kernel fuzzy C-means,AKFCM），对流数据进行随机采样并聚类。该算法大大降低了时间复杂度，但准确率较低。与此同时，也出现了针对不同需求的流聚类算法[5,6]。例如文献[5]针对数据流中流速的变化，在基于在线和离线聚类框架的基础上提出了基于动态滑动窗口的流聚类算法DSC，使得滑动窗口大小可随数据流流速动态改变，同时设定了窗口改变阈值避免窗口的频繁变化。该算法对流数据的处理效率较高，但未考虑到流数据本身数据信息对聚类结果的影响，因此聚类准确度并不高。文献[6]对经典流数据聚类算法CluStream 与经典密度聚类算法DBSCAN7进行总结与改进，提出了适用于入侵检测环境的流数据聚类算法。该算法能够实现对流数据的实时聚类，但不能准确反映新流入数据的特征，

因此聚类性能较低。

针对以上问题，本文提出一种基于差异性采样的流数据聚类算法。首先采用统计杠杆分数(statistical leverage scores）[8]对流数据中的点进行采样，其次用样本点构造核矩阵，然后应用核模糊C均值聚类算法对样本核矩阵中的点进行聚类得到一个带有类别标记的核矩阵，然后用带标记的样本核矩阵对流数据中的点进行实时划分，最后利用衰退聚类机制(fadingclustermechanism)2删除不再具有代表性的类别，实时更新数据模型。

# 1 基础理论

# 1.1模糊C均值聚类算法

模糊聚类算法是一种根据隶属度值最大原则来划分类别的数学方法，每个样本点以不同隶属度值同时属于多个类，最终将该点聚到对应隶属度值最大的类中，使得被聚到同一类中的数据对象之间相似度最大，不同类数据对象之间相似度最小。模糊C均值聚类算法(fuzzy C-means,FCM)[9]步骤为：首先随机初始化每个数据与各个类的隶属度得到初始隶属度矩阵；然后根据隶属度计算每一个类的聚类中心，接着更新隶属度矩阵。如此迭代，直到各个类的聚类中心不再发生变化或者隶属度值变化的绝对值低于设定阈值，算法结束。模糊C均值聚类算法的目标函数为

$$
J _ { _ { F C M } } = \sum _ { j = 1 } ^ { C } \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } \left\| x _ { i } - \nu _ { j } \right\| ^ { 2 }
$$

$$
\sum _ { j = 1 } ^ { C } u _ { i j } = 1 , u _ { i j } \in [ 0 , 1 ]
$$

其中：给定数据集 $X = \left\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { i } , \cdots , x _ { N } \right\} $ $C$ 为聚类个数； $N$ 为样本个数； $U = \left[ u _ { i j } \right] _ { C \times N }$ 为隶属度矩阵； $u _ { i j }$ 为数据点； $x _ { i }$ 隶属于第 $j$ 类的隶属度值； $\boldsymbol { \nu } _ { j }$ 为第 $j$ 类的聚类中心； $\mathbf { \nabla } m$ 为加权指数，也称平滑因子，控制模式在模糊类间的分享程度，关于它的最佳取值尚未有理论指导，大多数情况下取值为2。令 $J _ { { } _ { F C M } }$ 对 $\boldsymbol { \nu } _ { \scriptscriptstyle j }$ （20和 $u _ { i j }$ 求偏导，并令偏导为0，得到聚类中心和隶属度值的更新函数:

$$
\nu _ { j } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } x _ { i } } { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } }
$$

$$
u _ { i j } = \frac { \displaystyle \left( \left\| x _ { i } - \nu _ { j } \right\| \right) ^ { - 2 / ( m - 1 ) } } { \displaystyle \sum _ { g = 1 } ^ { C } \left( \left\| x _ { i } - \nu _ { g } \right\| \right) ^ { - 2 / ( m - 1 ) } }
$$

# 1.2核模糊C均值聚类算法

在原始空间下,数据点之间并非都是线性可分的，尤其对于流数据来说，数据的形式多样，即使应用较优的聚类算法，也难以得到较好的聚类效果。基于此，可利用核方法来解决这一问题，基于核方法的聚类算法[10\~12]对数据的处理更加灵活，同时便于操作。核方法的核心思想是：首先通过某种非线性映射$\phi$ ,将原始数据嵌入到高维特征空间，使得原始空间下不能线性可分的点变得线性可分；然后利用通用的线性学习器在这个高维特征空间中对数据进行分析和处理。定义非线性映射$\phi : X \to F$ ,将低维输入空间 $X$ 映射到高维特征空间 $F$ 。核模糊$C$ 均值聚类算法(kernel fuzzy C-means,KFCM)的目标函数为

$$
J _ { _ { K F C M } } = 2 \underset { j = 1 } { \overset { C } { \sum } } \underset { i = 1 } { \overset { N } { \sum } } u _ { i j } ^ { m } \left( 1 - k \left( x _ { i } , \nu _ { j } \right) \right)
$$

$$
\sum _ { j = 1 } ^ { C } u _ { i j } = 1 , u _ { i j } \in [ 0 , 1 ]
$$

$K ( x _ { \mathrm { i } } , \nu _ { \mathrm { j } } )$ 为核函数，定义了特征空间中两点之间的欧氏离。令 $J _ { _ { K F C M } }$ 对 $\boldsymbol { \nu } _ { j }$ 和 $u _ { i j }$ 求偏导，并令偏导为0，得到聚类中心和隶属度值的更新函数：

$$
\nu _ { j } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } k \left( x _ { i } , \nu _ { j } \right) x _ { i } } { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } k \left( x _ { i } , \nu _ { j } \right) }
$$

$$
u _ { i j } = { \frac { \displaystyle \left( 1 - k \left( x _ { i } , \nu _ { j } \right) \right) ^ { - 1 / ( m - 1 ) } } { \displaystyle \sum _ { g = 1 } ^ { C } \left( 1 - k \left( x _ { i } , \nu _ { g } \right) \right) ^ { - 1 / \left( m - 1 \right) } } }
$$

其中： $k ( x _ { i } , \nu _ { j } )$ 因选取的核函数而异。本文采用高斯径向基核函数（Gaussian radial bases kernels,GRBF）[13],形式如下：

$$
k \left( x _ { i } , \nu _ { j } \right) = \exp \left( - \frac { \left\| x _ { i } - \nu _ { j } \right\| ^ { 2 } } { 2 \sigma ^ { 2 } } \right)
$$

其中： $\sigma$ 为函数的宽度参数，控制函数的径向作用范围。

# 1.3 统计杠杆分数

统计杠杆分数是用来衡量行向量与矩阵的一致性或相关性的标准，从而判断该向量与矩阵的相似性。统计杠杆值越高，则该行向量与矩阵中点的差异性越大，相关性越小。统计杠杆分数的应用较为广泛，在异常值检测领域[14]，用来判断外来数据是否为异常数据；在随机矩阵分析算法[15]领域，用来分析数据与随机矩阵的相关性；在矩阵一致性研究领域，如矩阵填充[16]，用于对矩阵缺失部分进行估计。

统计杠杆分数计算如下：

设矩阵 $A \in n \times d$ ， $A ^ { ( i ) } \in 1 \times d$ 为矩阵 $A$ 的第 $i$ 行，矩阵 $A$ 的第 $i$ 行的统计杠杆分数 $I$ 为

$$
I = \left\| A ^ { ( i ) } \right\| _ { 2 } ^ { 2 } , i \in \left\{ 1 , 2 , \cdots , n \right\}
$$

# 1.4衰退聚类机制

由于流数据的动态性，随着新数据点的到达，数据模型也会发生变化。本文采用衰退聚类机制来动态更新样本核矩阵中的数据。设每一个类 $j \in \left[ 1 , C \right]$ ,都被赋予一个变量值 $t _ { j }$ ，代表被划入到第 $j$ 类中的最后一个点的时刻， $t$ 为新的数据点 $x _ { t }$ 到达的时间，在每一个数据点即将被划分到第 $j$ 类时，本文算法采用一个单调函数 $f _ { j } \left( t \right)$ 来计算该类的近因值[17]（近因值的概念来源于心理学的近因效应[18]，是指当人们识记一系列事物时对末尾部分项目的记忆效果优于中间部分项目的现象），近因值越大，越能代表最新点的数据特征，受到之前数据点特征影响的程度越小。近因函数表示如下：

$$
f _ { j } \left( t \right) = \exp \left( - \gamma \left( t - t _ { j } \right) \right)
$$

$$
\eta = \exp \left( - \gamma \tau \right) , \tau \in \left\{ 1 , 2 , 3 , 4 , 5 \right\}
$$

其中： $\gamma$ 代表一个类的衰退率[18]；参数 $\tau \in \{ 1 , 2 , 3 , 4 , 5 \}$ 。本文算法将近因值小于一定阈值的类实时删除，同时用新到达的点代替该类。

# 2 基于差异性采样的流数据聚类算法

本文算法基于流数据的特性，采用核模糊C均值聚类算法为基础算法，利用差异性采样法对数据进行采样，随着流数据的流入，利用衰退聚类机制实时更新数据模型。该算法主要分为采样、聚类和更新三个阶段。

# 2.1差异性采样

本文算法在对流数据进行聚类时，由于流数据的无限性，首先利用统计杠杆分数对流数据进行采样，由于聚类的类别是在核矩阵中产生，所以应使核矩阵中的采样数据之间的差异较大，从而囊括更多的数据信息，才更能代表流数据中数据的的分布情况。统计杠杆分数越高，表明数据点与原核矩阵中数据点的平均水平相差越大，同时数据在核矩阵中的影响程度越高，因此需要采集统计杠杆分数值较高的数据以保证样本核矩阵中数据点的差异性。

设样本集 $s$ ，样本中数据点的个数为 $s \left( r \leq s \leq R \right) , r$ 和 $R$ 为自定义参数， $\boldsymbol { K } _ { t - 1 }$ 代表 $\left( t - 1 \right)$ 时刻的核矩阵, $K _ { 1 } = 1$ （将 $( \mathrm { X } _ { 1 } , \mathrm { X } _ { 1 } )$ 带入高斯核函数公式可得）。当数据点 $x _ { t }$ 在 $t$ 时刻到达时,先将其划入到样本集中得到 $K _ { t }$ ，对其进行奇异值分解[19-20]，采用奇异值分解的原因是，在采集样本点时，需要计算核矩阵的每个行向量的统计杠杆值，计算量大，奇异值分解是提取矩阵特征的重要手段，特征值越大，说明矩阵在对应的特征向量上的方差越大，功率越大，包含的信息量也越多，同时也越能够代表数据的分布情况。因此利用奇异值分解得到核矩阵中具有代表性的C个向量，每次只需计算这C个向量和新到达点的统计杠杆值即可。以下为分解过程：

$$
\begin{array} { r } { K _ { t } = V _ { c } \sum _ { c } V _ { c } ^ { T } } \end{array}
$$

$$
\begin{array} { r } { \sum _ { c } = d i a g ( \lambda _ { 1 } , \cdots , \lambda _ { 2 } ) } \end{array}
$$

$$
V _ { C } = ( \nu _ { 1 } , \cdots , \nu _ { C } )
$$

$C$ 为聚类个数， $\textstyle \sum _ { C }$ 是由 $K _ { t }$ 的最大的 $C$ 个特征值组成的对角矩阵， $\left( V _ { c } \right) _ { s \times C }$ 是由对应的 $C$ 个特征向量组成的矩阵。利用 $V _ { c }$ 来计算统计杠杆分数，目的是利用有价值的信息来挑选同样或者更加有用的信息，增加了筛选的准确率，提高了核矩阵的整体差异度。 $V _ { C } ^ { ( i ) }$ 为 $V _ { c }$ 的第 $i$ 行，更新核矩阵( $\mathbf { \bar { \rho } } _ { h }$ 为自定义参数)：

$$
K _ { t } = \left\{ { \begin{array} { c c } { K _ { t - 1 } } & { \varphi ^ { T } } \\ { \varphi } & { k \left( x _ { t } , x _ { t } \right) } \\ { K _ { t - 1 } } & { p _ { t } \geq h } \end{array} } \right. \quad p _ { t } < h
$$

$p _ { t }$ 为将数据点 $x _ { t }$ 划入到S中的可能性，定义为 $( t - 1 )$ 时刻与t时刻矩阵 $V _ { c }$ 的统计杠杆分数的比值，定义如下：

$$
p _ { t } = \frac { \displaystyle \sum _ { i = 1 } ^ { s } \left\| V _ { c } ^ { ( i ) } \right\| _ { 2 ( t - 1 ) } ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { s } \left\| V _ { c } ^ { ( i ) } \right\| _ { 2 ( t ) } ^ { 2 } }
$$

统计杠杆值越大，说明新到达的点与原矩阵中的点的差异性越大，分母越大， $\boldsymbol { p } _ { t }$ 越小；当 $\boldsymbol { p } _ { t }$ 小于阈值 $\mathbf { h }$ 时，则将t时刻到达的点 $x _ { t }$ 划入到样本核矩阵中。其中阈值 $h \in ( 0 , 1 ]$ ，且 $h$ 的取值越接近于0，说明新数据点的到达使得统计杠杆分数越大，表明数据点与原核矩阵中数据的差异性越大，从而使得核矩阵中的点的分布范围变大，数据包含的信息越丰富，可以更有效的对流数据中的点进行聚类；但 $h$ 的值越接近于0，会使得满足条件的数据点变少从而需要不断筛选导致较大的计算复杂度，而且所选实验数据集的大小也会影响的选取，本文算法在不同数据集上选取了不同的 $h$ 值，详见第3章。本文算法的采样方法,能够减小时间复杂度和对存储空间的占用，又可以采集到相对能代表所有流数据分布的点。

# 2.2 聚类

利用核模糊 $C$ 均值聚类算法将核矩阵 $K _ { t }$ 中的点聚成 $C$ 个类，本文算法目标函数 $J _ { { } _ { M } }$ 如下：

$$
{ \cal J } _ { M } = 2 \sum _ { j = 1 } ^ { C } \sum _ { i = 1 } ^ { s } u _ { i j } ^ { m } \Big ( 1 - k \Big ( x _ { i } , \nu _ { j } \Big ) \Big )
$$

令 $J _ { { } _ { M } }$ 对 $\boldsymbol { \nu } _ { \boldsymbol { j } }$ 和 $u _ { i j }$ 求偏导，并令偏导为0，得到聚类中心和隶属度值的更新函数：

$$
\nu _ { j } = \frac { \displaystyle \sum _ { i = 1 } ^ { s } u _ { i j } ^ { m } k \left( x _ { i } , \nu _ { j } \right) x _ { i } } { \displaystyle \sum _ { i = 1 } ^ { s } u _ { i j } ^ { m } k \left( x _ { i } , \nu _ { j } \right) }
$$

$$
u _ { i j } = { \frac { \displaystyle \left( 1 - k \left( x _ { i } , \nu _ { j } \right) \right) ^ { - 1 / \left( m - 1 \right) } } { \displaystyle \sum _ { g = 1 } ^ { C } \left( 1 - k \left( x _ { i } , \nu _ { g } \right) \right) ^ { - 1 / \left( m - 1 \right) } } }
$$

具体聚类步骤如下：

a)给定聚类类别数 $C$ ，设定迭代收敛阈值，初始化各个聚类中心以及隶属度矩阵。

b)用当前的聚类中心根据式（20）更新隶属度矩阵，用当前隶属度矩阵根据式（19）更新各个聚类中心。

c)循环b)，直到各个类的聚类中心不再发生变化或者隶属度矩阵的变化值小于一定的阈值，终止迭代。

# 2.3动态更新数据模型

在核空间下将样本集S中的点聚成 $C$ 个类后，将 $C$ 个类映射到原空间，用来对数据流中的点进行划分，将各个点划分到距离它最近的类中。根据式（21）计算距离 $t$ 时刻到达的点 $x _ { t }$ 最近的类 $j ( j \in [ 1 , C ] )$ 类。

$$
j = \underset { j \in \left[ 1 , C \right] } { \arg \operatorname* { m i n } } \left\| \nu _ { j } - x _ { t } \right\| ^ { 2 }
$$

当得到类 $j$ 时，计算第 $j$ 类的近因值。若近因值小于等于自定义阈值 $\eta$ （代表一个类持续活跃的生命周期），则将该类以及类中的点从 $s$ 中删除，并用 $x _ { t }$ 代替该类并作为该类的初始点；若近因值大于 $\eta$ ，则将 $x _ { t }$ 划分到该类中。因此将 $x _ { t }$ 划分到类中的条件为

$$
\left\{ \begin{array} { l l } { \displaystyle j = \arg \operatorname* { m i n } _ { j \in [ 1 , C ] } \Big \| \nu _ { j } - x _ { t } \Big \| ^ { 2 } } \\ { \qquad f _ { j } \big ( t \big ) > \eta } \end{array} \right.
$$

# 2.4本文算法过程概述

本文算法的具体步骤描述如下，算法过程图示和算法流程如图1和2所示。

a)输入数据集 $X = \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { i } , \cdots , x _ { N } \}$ ，聚类个数：C，核函数： $k ( x _ { i } , \nu _ { j } )$ ，样本集中点的个数的最大最小值：R、r,参数： $\boldsymbol { \tau }$ 、h。

b)初始化U, $K _ { 1 } = 1 \ : , \ : V _ { c } = 1 \ : , \ : \sum _ { c } = k \big ( x _ { 1 } , x _ { 1 } \big )$ ，初始聚类中心。

c)采样：利用差异性采样方法进行采样，并利用样本集中的数据构造核矩阵。

d)聚类：采用核模糊C均值聚类算法对核矩阵中的数据进行聚类，得到一个带有类别标记的核矩阵。

e)划分以及动态更新数据模型：利用步骤4得到的标记核矩阵对流数据进行划分，同时不断更新隶属度矩阵U。

f)输出隶属度矩阵，聚类结果。

![](images/70d22dbbb8deb9eae98778a354a3b9838febf0b7c89d0b6f2fcf7264ca020e88.jpg)  
图1算法过程图示

![](images/63aa609c6a811fd9468ff6aa75d794d184c451db1611f40e180e0ea1de8c822e.jpg)  
图2算法流程

# 2.5实时动态处理概述

a)按条读取数据。为了验证本文算法的准确率，本文采用已经分类的数据集进行实验，将数据集以矩阵的形式存入，按行读取数据。

b)对数据进行采样分析，利用 MATLAB 中的功能函数 $t i c$ 函数计算每条数据的处理时间 $\mathbf { \Phi } _ { t }$ ，并以 $t + t _ { 0 }$ 作为下一条数据的初始处理时间。假设第一条数据的处理时间为 $t _ { \mathrm { { l } } }$ ，第二条数据的处理时间为 $t _ { 2 }$ ，第三条数据的处理时间为 $t _ { 3 }$ …，则第二条数据的初始处理时间为 $t _ { \mathrm { 1 } } + t _ { \mathrm { 0 } }$ ，第三条数据的初始处理时间为t+t+t…以此类推。（由于不同数据集的种类和属性的差异，因此本文算法的动态更新过程没有固定的更新频率和时间窗口）。

c)对样本核矩阵进行动态更新，每当一条数据 $x _ { t }$ 在 $\mathbf { \Phi } _ { t }$ 时刻被划入到相应的类 $j$ 中，都要利用 $\mathbf { \Phi } _ { t }$ 和之前最后一个划入到该类中的数据到达的时刻 $t _ { j }$ 进行近因值计算，实时删除不再具有代表性的类。

# 2.6 时间复杂度分析

利用传统核模糊C均值聚类算法对流数据进行聚类，在构造核矩阵时，矩阵规模为 $N \times N$ ，因此算法的时间复杂度为$O ( N ^ { 2 } )$ .在本文算法中，样本核矩阵中的数据量为 $s$ ，且 $s \ll N$ ，所以本文算法的时间复杂度为 $O ( N s )$ ，本文算法的时间复杂度远远低于传统核模糊C均值聚类算法。同时，在进行采样分析时，需要计算核矩阵中每行的统计杠杆分数，时间复杂度为$O ( s )$ ，在采用奇异值分解后，只需利用C个特征向量的值进行计算，且 $C < s$ ，时间复杂度为 $O ( C )$ ，进一步降低了本文算法的时间复杂度。

# 3 实验分析

本实验的实现平台为MATLAB2014a。为了验证本文算法的聚类效果，与AKFCM/KFCM和FCM算法分别进行实验对比，通过AKFCM算法对流数据聚类时采用的随机采样法与本文差异性采样法进行对比，验证本文算法的聚类效果；通过与非采样的KFCM算法对比，验证本文算法的时间复杂度以及聚类效果；通过与FCM算法进行对比，验证本文算法的聚类效果优于传统聚类算法。由于KFCM算法是用数据集中所有数据构造核矩阵，因此选取的数据集不宜过大，避免存储空间不足。本文选用Movement-Libras整个数据集，MFCC数据集中20类中的部分数据，CIFAR-10数据集中20类中的部分数据，ForestCoverType 数据集中7类中的部分数据来模拟流数据。表1为实验数据集。四个数据集的长度依次变大，目的是为了验证随着流数据规模的增加，本文算法的聚类效果不会受到影响，证明本文算法对于数据量大的流数据更具有优势。本文采用归一化互信息（NMI）[2I]、运行时间、准确率（A)[22]及误差平方和（SSE）作为聚类效果的评价标准。为减少偶然误差，每次实验进行50次取平均值。

表1实验数据集  

<html><body><table><tr><td>数据集</td><td>属性数</td><td>类别数</td><td>数据个数</td></tr><tr><td>Movement-Libras</td><td>90</td><td>15</td><td>360</td></tr><tr><td>MFCC</td><td>22</td><td>20</td><td>3121</td></tr><tr><td>CIFAR-10</td><td>3072</td><td>20</td><td>10000</td></tr><tr><td>Forest Cover Type</td><td>4</td><td>7</td><td>20000</td></tr></table></body></html>

# 3.1聚类性能指标分析

归一化互信息（NMI）在聚类中，常被用来度量某聚类算法的聚类结果与数据实际分类的相近程度，其值的范围为[0,1],NMI值越高，说明该聚类算法与数据的实际分类越相近，效果越好，反之效果越差。计算公式为

$$
N M I = \frac { H ( A ) + H ( B ) } { H ( A , B ) }
$$

$$
H ( A ) = - \sum _ { a } P _ { A } ( a ) \log P _ { A } ( a )
$$

$$
H ( B ) = - \sum _ { b } P _ { _ B } ( b ) \log P _ { _ B } ( b )
$$

$$
H ( A , B ) = - \sum _ { a , b } P _ { A B } ( a , b ) \log P _ { A B } ( a , b )
$$

其中： $H ( A )$ 表示 $A$ 向量的信息熵[23]； $H ( B )$ 表示 $B$ 向量的信息熵； $H ( A , B )$ 表示 $A$ 和 $B$ 的联合信息熵[23]； $a \cdot b$ 分别表示 $A$ 和 $B$ 的概率； $P _ { A } ( a ) \setminus P _ { B } ( b )$ 分别表示 $A$ 和 $B$ 的概率分布[24];$P _ { _ { A , B } } ( a , b )$ 表示 $A$ 和 $B$ 的联合概率分布[24]。

准确率（A）是评价聚类结果性能最常用的准则，其计算公式如下:

$$
A = \frac { \displaystyle \sum _ { j = 1 } ^ { C } a _ { j } } { N }
$$

其中： $N$ 表示实验样本数据总数； $c$ 表示类的数目； $a _ { j }$ 表示聚类结果中的第 $j$ 个聚类和实际聚类相一致的样本个数, $a _ { { } _ { j } }$ 越大，表示正确分类的样本数越多； $A$ 越大，则聚类结果的准率越高，聚类质量越好。

误差平方和（SSE）是用来评价类间差异性的函数，公式如下：

$$
S S E = \sum _ { j = 1 } ^ { C } \sum _ { i = 1 } ^ { d } { \left\| { \boldsymbol { x } } _ { i j } - { \boldsymbol { m } } _ { j } \right\| } ^ { 2 }
$$

其中： $c$ 表示类的数目； $d$ 表示第 $j$ 类中样本的个数； $x _ { i j }$ 表示第 $j$ 类中的第 $i$ 个数据； $m _ { j }$ 表示第 $j$ 类的聚类中心； $S S E$ 的值越小，说明数据都被聚到相对较近的类中，聚类效果越好

# 3.2参数取值分析

1）参数 $\tau$ 的取值分析

由 $\eta = \exp \left( - \gamma \tau \right)$ ， $\tau \in \{ 1 , 2 , 3 , 4 , 5 \}$ 可知， $\boldsymbol { \tau }$ 越大， $\eta$ 越小，反之$\eta$ 越大。当近因值大于 $\eta$ 时，将数据点划入到相应的类中，为了严格筛选核矩阵中的数据点，应尽量使 $\eta$ 的值较大，但同时又会增加算法运行的时间，因此需要权衡时间复杂度与聚类效果之间的关系。表2\~4分别为t的取值对运行时间、NMI以及A的影响。Movement-Libras 数据集的采样样本大小为100，MFCC数据集的采样样本大小为500，CIFAR-10数据集的采样样本大小为2000，ForestCoverType 数据集的采样样本大小为$4 0 0 0$ 。由表2可知，对于每个数据集，随着τ的增大，运行时间呈现不断增大的趋势，因此从运行时间上 $\boldsymbol { \tau }$ 的值设为1较好；由表3可知，当 $\scriptstyle \tau = 1$ 时，四个数据集的NMI值都为最大，且随着 $\boldsymbol { \tau }$ 值的增大，每个数据集NMI值降低较快；由表4可以看出，当 $\scriptstyle \tau = 1$ 时，四个数据集的A值都是最大的。因此实验中将 $\boldsymbol { \tau }$ 值设为1。

表2 $\boldsymbol { \tau }$ 的不同取值下的运行时间/ms  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="5">T</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>Movement_Libras</td><td>338.21</td><td>355.48</td><td>346.09</td><td>375.42</td><td>390.72</td></tr><tr><td>MFCC</td><td>652.73</td><td>684.63</td><td>697.25</td><td>698.70</td><td>757.26</td></tr><tr><td>CIFAR-10</td><td>8975.6</td><td>8973.2</td><td>9301.4</td><td>9432.9</td><td>9804.3</td></tr><tr><td>Forest Cover Type</td><td>2981.7</td><td>3025.6</td><td>2911.0</td><td>3214.8</td><td>3410.5</td></tr></table></body></html>

表3τ的不同取值下的NMI值  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="5">T</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>Movement_Libras</td><td>0.8624</td><td>0.8432</td><td>0.8458</td><td>0.8063</td><td>0.8146</td></tr><tr><td>MFCC</td><td>0.8943</td><td>0.8656</td><td>0.8124</td><td>0.7596</td><td>0.7758</td></tr><tr><td>CIFAR-10</td><td>0.8793</td><td>0.8562</td><td>0.8746</td><td>0.8043</td><td>0.7859</td></tr><tr><td>Forest Cover Type</td><td>0.9025</td><td>0.8925</td><td>0.8856</td><td>0.8293</td><td>0.7894</td></tr></table></body></html>

表4 $\boldsymbol { \tau }$ 的不同取值下的A值  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="5">T</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>Movement_Libras</td><td>0.9073</td><td>0.8825</td><td>0.8401</td><td>0.8190</td><td>0.7911</td></tr><tr><td>MFCC</td><td>0.9174</td><td>0.8941</td><td>0.8631</td><td>0.8854</td><td>0.8126</td></tr><tr><td>CIFAR-10</td><td>0.8992</td><td>0.8829</td><td>0.8944</td><td>0.8788</td><td>0.8635</td></tr><tr><td>Forest Cover Type</td><td>0.9130</td><td>0.8799</td><td>0.8991</td><td>0.8432</td><td>0.8673</td></tr></table></body></html>

# 2）参数 $h$ 的取值分析

参数 $h \in ( 0 , 1 ] \ , \ h$ 的取值越小，说明新数据点的到达使得统计杠杆分数越大，表明数据点与核矩阵中原数据点的差异性越大，从而使得核矩阵中的点的分布范围变大，数据包含的信息越丰富，但 $h$ 的值越小，会使得满足条件的数据点变少从而需要不断筛选造成较大的时间复杂度，因此需要根据不同的数据集，通过实验验证，权衡时间复杂度与聚类效果之间的关系来确定 $h$ 的值。由表5，NMI和A的值随着 $h$ 的增大而变小，运行时间也变小，且变化值较小，又由于Movement_Libras数据集规模较小，运行时间较短，因此采用聚类结果最准确的值$h = 0 . 1$ 。由表6，NMI和A的值在 $h = 0 . 4$ 时降低幅度较大，且在 $h = 0 . 1 \mathord { \mathrm { . 0 . 2 } } \mathord { \mathrm { . 0 . 3 } }$ 时的值相差较小；运行时间上，当 $h = 0 . 3$ 时，运行时间明显降低，并且之后趋于平缓，因此在MFCC数据集上， $\boldsymbol { h }$ 值设为0.3。由表7，当NMI最大时 $h = 0 . 4$ ，且之后NMI值逐渐降低，且降幅较大；运行时间上呈现逐渐减小的趋势，且当 $h = 0 . 1 \AA 0 . 2 \AA . 0 . 3$ 时，运行时间很大， $h = 0 . 4$ 时降幅较大，且之后趋于平缓，同时 $h = 0 . 4$ 时的A值与最大值相差不多，因此在 CIFAR-10 数据集上，将 $h$ 设为0.4。由表8，运行时间在$h = 0 . 2$ 时降低幅度较大且之后趋于平缓；同时 NMI和A的值逐渐降低，且在 $h = 0 . 2$ 时,NMI和A值相对较大，因此在ForestCover Type 数据集上，将 $h$ 设为0.2。

表5Movement_Libras 数据集h取值分析  

<html><body><table><tr><td>h</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td></tr><tr><td>NMI</td><td>0.8624</td><td>0.8502</td><td>0.8594</td><td>0.8006</td><td>0.8399</td><td>0.8458</td><td>0.8303</td><td>0.8242</td><td>0.8112</td></tr><tr><td>A</td><td>0.9073</td><td>0.8992</td><td>0.8801</td><td>0.8688</td><td>0.8597</td><td>0.8525</td><td>0.8457</td><td>0.8391</td><td>0.8361</td></tr><tr><td>运行时间/ms</td><td>338.21</td><td>336.12</td><td>331.25</td><td>321.92</td><td>318.60</td><td>309.19</td><td>311.32</td><td>299.30</td><td>290.56</td></tr></table></body></html>

表6MFCC数据集h取值分析  

<html><body><table><tr><td>h</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td></tr><tr><td>NMI</td><td></td><td>0.90320.8982</td><td></td><td>0.8943 0.7206 0.7299 0.6958 0.68030.6542</td><td></td><td></td><td></td><td></td><td>0.6212</td></tr><tr><td>A</td><td></td><td></td><td></td><td>0.9198 0.9183 0.9174 0.8233 0.7980 0.7815 0.7570 0.7499 0.7161</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>运行时间/ms</td><td></td><td></td><td></td><td>1176.9 976.61 652.73 654.90 643.52 662.15 619.04 629.18 600.79</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

表7CIFAR-10数据集h取值分析  

<html><body><table><tr><td>h</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td></tr><tr><td>NMI</td><td></td><td>0.8724 0.8602</td><td></td><td>0.8794 0.8793 0.7499 0.7158 0.6803 0.6842 0.6512</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A</td><td>0.8669</td><td></td><td></td><td>0.8640 0.8571 0.8992 0.7350 0.7375 0.7216 0.6991 0.6761</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>运行时间/ms</td><td>14562</td><td>12729</td><td>12382</td><td></td><td></td><td></td><td>8975.6 8709.4 8577.0 8548.1 8762.3 8434.6</td><td></td><td></td></tr></table></body></html>

表8ForestCoverType数据集h取值分析  

<html><body><table><tr><td>h</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td></tr><tr><td>NMI</td><td></td><td></td><td></td><td>0.9094 0.9025 0.9000 0.8606 0.8432 0.8400 0.8207 0.8233 0.8142</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A</td><td></td><td></td><td></td><td>0.9109 0.9130 0.8873 0.8988 0.8596 0.8432 0.8592 0.8348 0.8293</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>运行时间/ms</td><td></td><td></td><td></td><td></td><td></td><td></td><td>4019.2 2981.7 2810.5 2699.0 2579.1 2600.7 2583.6 2401.9 2481.6</td><td></td><td></td></tr></table></body></html>

# 3.3 聚类性能分析

# 1） NMI值分析

图3\~6分别为四种算法在不同数据集上的NMI值。由于本文算法和AKFCM算法需要进行采样，样本大小不同，聚类效果也不同，所以此NMI值是变化的，而KFCM和FCM算法为非采样算法，因此为固定值。通过分析图3\~6可知：a）本文算法的值始终大于AKFCM算法的值，且随着数据规模的不断扩大，两者差值逐渐增大，证明本文算法采用的采样方法优于AKFCM算法采用的随机采样法；b）在四个数据集上，本文算法的NMI值都高于KFCM和FCM算法的值，且远远高于FCM算法的值，同时随着采样数目的增加，本文算法NMI值逐渐增大，证明在对流数据进行聚类上，本文算法优于传统聚类算法。

![](images/ceba65f71fe1ae1d41fe8d9ce736a453ae07db81d1c03e87fc7c6d67c2215147.jpg)  
图3Movement_Libras 数据集对比实验NMI值

![](images/ae22455fd89595202176e009dbcdc618dfd7159ea43e1330cae400224187d59e.jpg)  
图4MFCC数据集对比实验NMI值

![](images/4f2ccb07031213aa163511fd9cb8faa53e169a1130bce79678d995bd4fd34b6e.jpg)  
图5CIFAR-10数据集对比实验NMI值

![](images/9c485cf00e41e2d70e26344c01bcf3c68f168025cca7d51918bcbc845ef28edc.jpg)  
图6ForestCoverType 数据集对比实验NMI值

# 2）其他性能比较分析

下面主要从运行时间（time/ms）、误差平方和（SSE）和准确率（A）三个方面进行对比分析。四组数据集样本数量分别为100、500、2000、4000。从表 $9 { \sim } 1 2$ 可以看出，在运行时间（time/ms）、误差平方和（SSE）以及准确率（A）三个方面本文算法都要优于AKFCM和KFCM，且随着数据集规模的扩大，

AKFCM与KFCM算法的准确率逐渐降低，本文提出的算法仍然具备较高的准确率。证明本文算法的聚类效果优于利用随机采样法对流数据进行聚类的算法。虽然在运行时间上本文算法要高于FCM算法，但在误差平方和以及准确率上本文算法要远优于FCM算法。

表9Movement_Libras数据集运行时间、SSE和A  

<html><body><table><tr><td></td><td>核矩阵样本数</td><td>Time/ms</td><td>SSE</td><td>A</td></tr><tr><td>本文算法</td><td>100</td><td>338.21</td><td>12985</td><td>0.9073</td></tr><tr><td>AKFCM</td><td>100</td><td>349.00</td><td>14260</td><td>0.7659</td></tr><tr><td>KFCM</td><td>全部</td><td>565.75</td><td>14098</td><td>0.8509</td></tr><tr><td>FCM</td><td>0</td><td>187.17</td><td>15780</td><td>0.6134</td></tr></table></body></html>

表10MFCC 数据集运行时间、SSE 和A  

<html><body><table><tr><td colspan="2">核矩阵样本数</td><td>Time/ms</td><td>SSE</td><td>A</td></tr><tr><td>本文算法</td><td>500</td><td>652.73</td><td>151750</td><td>0.9174</td></tr><tr><td>AKFCM</td><td>500</td><td>786.79</td><td>186400</td><td>0.7284</td></tr><tr><td>KFCM</td><td>全部</td><td>1054.3</td><td>174208</td><td>0.8273</td></tr><tr><td>FCM</td><td>0</td><td>287.9</td><td>245780</td><td>0.5934</td></tr></table></body></html>

表11CIFAR-10数据集运行时间、SSE 和A  

<html><body><table><tr><td colspan="2">核矩阵样本数</td><td>Time/ms</td><td>SSE</td><td>A</td></tr><tr><td>本文算法</td><td>2000</td><td>8975.6</td><td>484679</td><td>0.8992</td></tr><tr><td>AKFCM</td><td>2000</td><td>9478.1</td><td>683679</td><td>0.6734</td></tr><tr><td>KFCM</td><td>全部</td><td>16445</td><td>637863</td><td>0.7348</td></tr><tr><td>FCM</td><td>0</td><td>2480.0</td><td>977894</td><td>0.4122</td></tr></table></body></html>

表12ForestCoverType 数据集运行时间、SSE和A  

<html><body><table><tr><td colspan="2">核矩阵样本数</td><td>Time/ms</td><td>SSE</td><td>A</td></tr><tr><td>本文算法</td><td>4000</td><td>2981.7</td><td>64846</td><td>0.9130</td></tr><tr><td>AKFCM</td><td>4000</td><td>3975.6</td><td>82370</td><td>0.6734</td></tr><tr><td>KFCM</td><td>全部</td><td>5776.0</td><td>84579</td><td>0.7763</td></tr><tr><td>FCM</td><td>0</td><td>923.0</td><td>107894</td><td>0.4950</td></tr></table></body></html>

# 4 结束语

本文提出了一种基于差异性采样的流数据聚类算法，在采样阶段，利用统计杠杆分数衡量数据点与原样本集中点的差异性，得到一个数据点之间差异性较大的样本核矩阵，使样本中的点更能代表流数据中点的分布特征；在数据更新阶段，本文采用衰退聚类机制，随着新数据点的到达，实时删除无法反映新数据点特征的类，并用新数据点代替该类，以保证实时分析得到更能代表所有数据分布的数据模型。实验结果表明，本文算法在保证聚类效果的前提下，大大降低了对流数据聚类的时间复杂度；同时随着数据集规模的扩大，本文算法的聚类效果并未受到影响，证明本文算法对于数据量大的流数据更具有优势。

参考文献：   
[1]Aggarwal C C,Han Jiawei,Wang Jianyong，et al.A framework for clustering evolving data streams [C]// Proc of the 29th International Conference on Very Large Data Bases.Berlin:Morgan Kaufmann Publishers,2003:81-92.   
[2]Jain A,Zhang Z,Chang EY,Adaptive non-linear clustering indata streams [C]//Proc of International Conference on Information and Knowledge Management.2006:122-131.   
[3]Chen Yixin,Li Tu.Density-based clustering forreal-time stream data [C]// Proc of the 13th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. 2007: 133-142.   
[4]Havens TC, Chitta R,Jain A K, et al. Speedup of fuzzy and possibilistic kernel C-means for large-scale clustering [C]//Proc of IEEE International Conference on Fuzzy Systems.2011: 463-470   
[5] 张中平，王浩，薛伟，等．动态滑动串口的数据流聚类方法[J].计算 机工程与应用,2011,47(7):135-138.   
[6] 黄红艳，安素芳．数据流聚类算法在入侵检测中的应用[J].计算机工 程与应用,2012,48 (20): 112-116.   
[7]Ester M,Kriegel HP, Sander J,et al.A density-based algorithm for discovering clusters in large spatial databases with noise [C]//Proc of KDD. 1996:226-231.   
[8]P.Drineas,M.Magdon-Ismail,M.W.Mahoney,et al. Fast approximation ofmatrix coherenceand statistical leverage [C]/ ProcofJournal ofMachine Learning Research.2012: 3475-3506.   
[9] Goyal L M, Mittal Mamta,Sethi JK.Fuzzy model generation using subtractive and fuzzy C-means clustering [J]. CSI Trans on ICT,2016,4(2 4),129-133.   
[10]范子静，罗泽，马永征．一种基于模糊核聚类的谱聚类算法[J].计算 机工程,2017,43(11):161-165,172.   
[11]张腾达，吕晓琪，任晓颖，等．基于空间模糊核聚类的脑肿瘤图像分割 方法[J].控制工程,2017,24(10):2107-2111.   
[12]王书文，皮炳坤，张弘强，等．一种基于模糊核聚类算法的图像分类方 法[J]．西北师范大学学报：自然科学版,2016,52(5):42-45.   
[13] Yin Yong,Hao Yinfeng,Bai Yu,etal.A Gaussian-based kernel Fisher discriminant analysis for electronic nose data and applications in spirit and vinegarclassification[J].JournalofFoodMeasurementand Characterization,2017,11(1): 24-32.   
[14] Hoaglin DC,Welsch RE.The hat matrix in regression and ANOVA[J]. The American Statistician,1978,32(1): 17-22.   
[15] BoutsidisC,Mahoney MW,DrineasP.An improved approximation algorithm for the column subset selection problem [C]// Proc of the 20th Annual ACM-SIAM Symposium on Discrete Algorithms.2009: 968-977.   
[16] Recht B.Exact matrix completion via convex optimization [J].ACM,2012, 55 (6): 111-119.   
[17] Aggarwal C C. Data streams: models and algorithms. Springer Science

[EB/OL].(2007).http://www.stat.wvu.edu/\~jharner/courses/stat624/docs/

streambook. pdf.   
[18]张军．近因效应的认知影响及教学应用[J].化学学,2017,36(9):24-28.   
[19]Wang Shuli,Wang Guanxiang.Texture classification by bit-plane multifractal spectrum and bit-plane barycentric coordinates of wavelet coefficients based on SVD [EB/OL].(2017）.htp://dpi-proceedings. com/index.php/dtcse/article/download/8875/8444.   
[20]邱志伟，岳顺，岳建平，等．基于奇异值分解(SVD)的桥梁监测数据 去噪方法[J].工程勘察,2017,45(12):36-39.   
[21] Rand W M. Objective criteria for the evaluation of clustering methods [J]. Journal of the American Statistical Association,1971,66(1): 846-850.   
[22] Sun Y, Zhu QM, Chen ZX.An iterative initial points refinement algorithm for categorical data clustering [J].Pattern Recognition Letrs,20o2,23 (7): 875-884.   
[23]王天志，吴仕勇，陈恳，等．基于联合信息熵和粗糙集理论的关联知识 发现[J].云南民族大学学报：自然科学版,2010,19(3):224-227.   
[24] Zhang Jinping, Zhao Yong,Ding Zhihong.Research on the joint probability distribution of rainfall and reference crop evapotranspiration [J]. Paddy and Water Environment,2017,15(1),193-200.