# 一种改进K-means 聚类的FCMM算法\*

杨明极，马池，王娅，张竹(哈尔滨理工大学 测控技术与通信工程学院，哈尔滨 150080)

摘要：针对 K-means 算法易受初始聚类中心影响而陷入局部最优的问题，提出一种基于萤火虫智能优化和混沌理论的 FCMM算法。首先利用最大最小距离算法确定聚类类别值K和初始聚类中心位置；然后以各聚类中心为基准点，利用Tent映射构建混沌空间，通过混沌搜索更新聚类中心，以降低初始聚类中心过于临近的影响，并改善算法易陷入局部最优的问题。仿真结果表明，FCMM算法的平均聚类精度相较于经典K-means 算法和FA算法分别提高了 $7 . 5 1 \%$ 和 $2 . 2 \%$ ，成功避免算法陷入局部最优解，提高了划分初始数据集的效率和寻优精度。

关键词：K-means 聚类；萤火虫；最大最小距离；Tent映射；混沌搜索 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.12.0851

# Algorithm named FCMM to improve K-means clustering algorithm

Yang Mingji, Ma Chi, Wang Ya, Zhang Zhu (SchoolofMeasure-controlTechnology&CommunicationEnginering,Harbin UniversityofScience&Technology,Harbin 150080, China)

Abstract: Inordertosolvetheproblemthatthe K-meansalgorithmgetsafectedbythe initialclustercenters easily,this paper proposesFCMMalgorithm basedofrefly inteligence optimizationand chaos theory.Ituses the max-min distance clustering algorithm tocalculate the numberKof cluster center and determine the locationof initial clustercenters.Toovercome the problemthat initialclusteringcentersaretooclosetoeachotherandtraditionalalgorithmfalsintolocaloptimaeasilyituses Tent mapping to construct a chaotic space with each clustercenter as the datum point,and thenupdates cluster centers through chaotic search.The experimentalresults show that theaverage clustering accuracyof theFCMM algorithm thanthatof the classical K-means algorithm and the FA algorithm is respectively $7 . 5 1 \%$ and $2 . 2 \%$ higher, the FCMM algorithm avoids falling into the local optimal solution successfully,and improves the efciency and precision of the initial data set.

Key words: K-means clustering; firefly; maximum and minimum distance; Tent mapping; chaotic search

# 0 引言

伴随大数据时代的到来，数据挖掘领域得到日新月异的发展。聚类分析作为数据挖掘和数据分析的经典方法[I，在模式识别，室内定位，统计学等领域拥有良好的发展前景。随着社会发展对数据精度要求的不断提高，如何提高算法的聚类精度是广大学者一直以来的研究热点[2]。

鉴于传统K-means聚类算法存在易受初始聚类中心和异常数据影响的缺陷[3]，算法开始研究集中于利用特征关联度对传统K-means 算法的初始聚类中心进行优化[4]和基于自适应权重的聚类算法[5]。随着智能优化算法的提出和发展，萤火虫算法FA(FireflyAlgorithm)作为一种源于生物界的随机优化算法，因其具有操作简单、易于并行处理、鲁棒性强等特点[6]，可以有效解决各种优化问题，并能够成功应用到聚类问题中提高算法的准确性,受到了很多学者的关注和研究。针对K-means算法存在过度依赖初始聚类中心而陷入局部最优的问题，潘晓英等人提出了基于自适应步长的萤火虫划分聚类算法，采用了自适应步长代替原有的固定步长[7]。王冲等人提出一种新的小生境萤火虫划分聚类算法以增加种群多样性[8]。陈小雪等人利用萤火虫优化算法全局搜索能力强、易于实现的优势，通过引用一种加权的欧氏距离对 K-means 算法的初始聚类中心进行优化[9]。上述基于萤火虫优化的K-means 算法在给定聚类中心后的优化过程方面改善了聚类效果，但是都没有明确给出确定聚类中心数值K的方法，同时，基于自适应步长的改进算法在寻优后期设置的步长较小，易导致收敛速度较慢，且数据集局限于某个聚类中心无法跳出，从而陷入局部最优解，降低聚类精度。

针对以上问题，本文提出一种基于混沌理论和最大最小距离算法的动态种群萤火虫算法(dynamic Firefly algorithm basedon Chaos theory and Max-Min distance algorithm,FCMM)。该算法首先利用最大最小距离算法确定聚类中心数值 $K$ 的大小和初始聚类中心位置,再用遍历性均匀、迭代速度快的Tent 混沌映射构建以初始聚类中心为基准点的混沌搜索空间，并通过Tent混沌搜索的形式优化初始聚类中心，促使算法跳出局部最优，且可以获得较快收敛速度，最后利用智能萤火虫优化算法的位置更新公式划分非聚类中心样本点所属的聚类类别，完成聚类过程。

# 1 基本算法

# 1.1K-means 聚类算法

K-means 的核心功能是将给定的数据集 $X = \{ X _ { 1 } , X _ { 2 } , . . . , X _ { n } \}$ （20划分成 $K$ 个子集 $\{ C _ { 1 } , C _ { 2 } , . . . , C _ { k } \}$ ,经典K-means 聚类算法思想：从数据集X中随机选择K个对象，分别作为K个类别的初始聚类中心 $C _ { j } ( j = 1 , 2 , . . . , k )$ ；计算剩余每个对象 $X _ { i } ( i = 1 , 2 , . . . , n )$ 与各个聚类中心的欧氏距离，并将其划分到距离最近的子类 $C _ { j }$ 中；然后重新计算每个子类中所有对象的平均值，将其作为新的聚类中心[10]。重复上述过程，直到聚类中心不再改变。

定义1欧氏距离(Euclideandistance）是欧氏空间中两点之间的直线距离[11]。样本 $X _ { i }$ 与 $X _ { j }$ 在 $\mathbf { \Sigma } _ { m }$ 维空间中的欧式距离为

$$
\operatorname { d } \left( X _ { \mathrm { i } } , X _ { \mathrm { j } } \right) = { \sqrt { \sum _ { \mathrm { k } = 1 } ^ { \mathrm { m } } \left( X _ { \mathrm { i k } } - X _ { \mathrm { j k } } \right) ^ { 2 } } }
$$

K-means算法根据欧式距离确定样本的相似程度。

# 1.2萤火虫算法

该算法模拟萤火虫的移动过程，根据各萤火虫的位置和荧光亮度赋予其目标函数值并计算相对吸引度。荧光较强的个体吸引荧光较弱的个体按照位置更新公式向其移动，移动距离由吸引度的大小决定。优化过程基于以下三个原则：

a)萤火虫的性别因素忽略，任何两只萤火虫个体均可以互相吸引。b)萤火虫个体的吸引度与距离成反比，与亮度成正比，亮度强的萤火虫吸引亮度弱的萤火虫向其移动，亮度最强的个体随机移动；。

c）萤火虫个体的亮度由其所在位置的目标函数值决定。

定义2荧光亮度为

$$
I \propto - f ( x _ { i } ) , 1 \leq i \leq n
$$

$$
I = I _ { \mathrm { o } } \exp \left( - \gamma ^ { \ast } r _ { i j } \right)
$$

其中I表示荧光亮度， $f \left( x _ { i } \right)$ 表示目标函数， $x _ { i }$ 为萤火虫i的空间位置； $I _ { 0 }$ 表示最大荧光亮度； $\gamma$ 为常量，表示光强吸收因子；$r _ { i j }$ 表示 $x _ { i }$ 与 $\boldsymbol { x } _ { j }$ 之间的欧式距离。

定义3 吸引度为

$$
\beta = \beta _ { \mathrm { 0 } } \exp \left( - \gamma ^ { \ast } r _ { i j } ^ { 2 } \right)
$$

其中， $\beta _ { 0 }$ 为最大吸引度。

定义4位置更新公式为

$$
x _ { i } \left( t + 1 \right) = x _ { i } \left( t \right) + \beta \big ( x _ { j } \left( t \right) - x _ { i } \left( t \right) \big ) + \alpha \varepsilon _ { i }
$$

其中: $\alpha$ 表示初始化的步长因子； $\varepsilon _ { i }$ 表示服从高斯分布的随机因子。

# 2 K-means聚类算法的优化

对于传统K-means算法，给定初始聚类中心后，可以利用萤火虫算法的随机性和全局搜索能力对除去聚类中心以外的数据集进行较为精确的划分，进而提高算法的收敛速度，实现对K-means算法的优化。但是基于萤火虫优化的K-means算法存在以下缺陷：

a)聚类中心数值K的选取尚没有指定算法，若选取的K值不合理，会严重影响聚类精度和计算复杂度。

b)最佳聚类结果对应于目标函数的极值点，聚类中心落在某个局部极小点附近，易导致算法陷入局部最优[10]。

在利用萤火虫个体的相互吸引模拟K-means 聚类过程，提高全局搜索收敛速度的基础上，针对现有算法在全局寻优搜索中易陷入局部极值区域的缺陷，本文根据混沌映射对初值具有敏感性和遍历性的特点[12]，提出一种基于混沌理论的动态种群萤火虫算法(简称FCMM算法)，对K-means聚类进行改进。

# 2.1最大最小距离算法确定聚类中心数值K

最大最小距离(Max-Mindistance)聚类算法，本文简称MM算法。MM算法与传统K-means相似，都是通过计算欧氏距离，根据最近邻原则划分归属于各聚类中心的样本点。不同之处在于，MM算法并不是直接给定聚类类别数值K，而是从样本点中任选一个对象 $X _ { i }$ ，作为第一个聚类中心，通过式(1)计算各点到 $X _ { i }$ 的欧式距离，将距离 $X _ { i }$ 最远的点作为新的聚类中心。重复以上划分步骤，直到不再产生新的聚类中心，最后确定聚类中心总数K。

算法步骤如下：

a)给定 $\theta , 0 < \theta < 1$ ,选取初始聚类中心 $Z _ { 1 } = x _ { 1 }$ 。

b)产生新的聚类中心

通过计算各点到 $Z _ { \scriptscriptstyle 1 }$ 的欧氏距离 $D _ { i 1 }$ ，选取 $D _ { k 1 } = \operatorname* { m a x } \{ D _ { i 1 } \}$ 对应的 $x _ { k }$ 为下一个聚类中心 $Z _ { _ 2 }$ ；

计算各点到聚类中心 $Z _ { \scriptscriptstyle 1 }$ 和 $Z _ { _ 2 }$ 的距离 $D _ { i 1 } , D _ { i 2 }$ ，若$D _ { l } = \operatorname* { m a x } \{ \operatorname* { m i n } ( D _ { i 1 } , D _ { i 2 } ) \} , i = 1 , 2 , . . . n ,$ 并且 $D _ { l } > \theta ^ { * } D _ { 1 2 }$ ，，则取 $x _ { l }$ 为第三个聚类中心Z。

$$
D _ { i 1 } = \parallel x _ { i } - Z _ { 1 } \parallel = \sqrt { \sum _ { i = 1 } ^ { d } \lvert x _ { i } - Z _ { 1 } \rvert ^ { 2 } } , D _ { i 2 } = \parallel x _ { i } - Z _ { 2 } \parallel
$$

注： $D _ { 1 2 }$ 表示 $Z _ { \scriptscriptstyle 1 }$ 和 $Z _ { _ 2 }$ 之间的距离

若 $Z _ { 3 }$ 存在，判断是否有 $D _ { j } = \operatorname* { m a x } \{ \operatorname* { m i n } ( D _ { i 1 } , D _ { i 2 } , D _ { i 3 } ) \}$ $i = 1 , 2 , . . . n .$ ，若满足以上条件并且 $D _ { l } > \theta ^ { * } D _ { 1 2 }$ ,则确定第四个聚类中心。依次类推，如果出现 $D _ { l } \leq \theta ^ { * } D _ { 1 2 }$ ，，停止寻找新的聚类中心。

c)统计聚类中心总数 $\mathrm { ~ K ~ }$ 。

该算法的聚类结果与参数和起始点的选取关系重大。为得到良好的聚类效果，在无先验样本分布知识的情况下需要进行反复实验，故此算法在本文仅用于确定聚类中心数值K的大小。

# 2.2混沌理论优化聚类中心

为避免基于萤火虫优化的K-means 算法的聚类中心落在某个局部极小点附近，改善算法的全局搜索能力，尽快跳出局部最优解，本文引入具有随机性、遍历性、规律性特征的混沌变量，对基于萤火虫算法的K-means聚类进行优化处理。

由于Logistic 混沌映射在0,1边界范围分布集中，存在明显的遍历不均匀的问题，导致算法效率较低。单梁[10]等通过严谨的推理证明，验证了Tent映射产生的混沌序列更有助于算法优化[13]，并指出Tent映射的收敛速度和遍历均匀性等性能相较于logistic 映射更优。

# 2.2.1Tent混沌序列

Tent映射表达式为

$$
\boldsymbol { x } _ { t + 1 } = \left\{ \begin{array} { l l } { 2 \boldsymbol { x } _ { t } , 0 \leq \boldsymbol { x } _ { t } \leq \displaystyle \frac { 1 } { 2 } } \\ { 2 ( 1 - \boldsymbol { x } _ { t } ) , \displaystyle \frac { 1 } { 2 } \leq \boldsymbol { x } _ { t } \leq 1 } \end{array} \right.
$$

Tent 映射经伯努利移位变换后表示为

$$
x _ { t + 1 } = \big ( 2 x _ { t } \big ) \mathrm { m o d } 1
$$

Tent混沌序列的产生步骤如下：

a)随机产生一个不在(0.20,0.40,0.60,0.80）范围内的初值 $x _ { 0 }$ ，记作 $z , z ( 1 ) = x _ { 0 } , i = j = 1$ ：

b)按式(7)进行迭代，产生序列 $x$ 。

c）如果 $x ( i ) = [ 0 , 0 . 2 5 , 0 . 5 , 0 . 7 5 ]$ 或 $x ( i ) = x ( i - k ) .$ $k = [ 0 , 1 , 2 , 3 , 4 ]$ ,执行步骤b)。

d)按式 $x ( i ) = z ( j + 1 )$ 改变迭代初值，jj $+ 1$ ，执行步骤2。

e)如果达到最大迭代次数，终止运行，保存产生的 $x$ 序列。

# 2.2.2混沌搜索

本文提出的FCMM算法以当前搜索到的局部最优解为基准点产生Tent混沌序列，通过Tent搜索跳出局部最优，从而获得全局最优解。

具体方案如下：将各个聚类中心 $C _ { i } ( i = 1 , 2 , . . . k )$ 与当前聚类中心 $C _ { x }$ 的距离 $D _ { { } _ { i x } }$ 从大到小依次排列，取距离较小的前面 $\mathbf { n }$ 个（占聚类中心总数的 $30 \%$ 类 $C _ { i 1 } , C _ { i 2 } , . . . , C _ { i n }$ 与 $C _ { x }$ ，并分别求出当前 $\mathtt { n } { + } 1$ 个类中第j维的最大值 $X _ { \mathrm { \ m a x } } ^ { j }$ ，最小值 $X _ { \mathrm { \ m i n } } ^ { j }$ ，共同构成新的混沌搜索空间。以 $C _ { x }$ 的聚类中心 $X _ { x }$ 为基准点产生混沌序列，进行混沌搜索，搜索结束得到的最优解作为新的聚类中心。

假设聚类中心是Cx，Xk={xk1,k2..Xkd},

$$
\boldsymbol { x } _ { k j } \in [ X _ { \operatorname* { m i n } } , X _ { \operatorname* { m a x } } ] \ : _ { \circ }
$$

Tent混沌搜索主要步骤：

a)利用 $z _ { k j } ^ { 0 } = ( x _ { k j } - X _ { \operatorname* { m i n } } ^ { j } ) / \left( X _ { \operatorname* { m a x } } ^ { j } - X _ { \operatorname* { m i n } } ^ { j } \right)$ ,将 $X _ { x }$ 映射到(0,1)，其中 $k = 1 , 2 , . . . , n , j = 1 , 2 , . . . , D \ s$

b)将上式代入式(7)进行Tent映射，迭代产生混沌变量序列z(m=1,2..,C.max）。C.ax 是混沌搜索的最大迭代次数[11]。

c)利用式(8)将 $z _ { k j } ^ { m }$ 还原到原解空间的邻域内，产生新解 $V _ { _ k }$ 。

$$
\nu _ { _ { k j } } = x _ { _ { k j } } + \left( X _ { _ { \operatorname* { m a x } } } ^ { j } - X _ { _ { \operatorname* { m i n } } } ^ { j } \right) \ast \left( 2 z _ { _ { k j } } ^ { m } - 1 \right) / 2
$$

d)计算 $\nu _ { \scriptscriptstyle k }$ 的荧光亮度值 $F ( \nu _ { k } )$ ，并与局部最优解的荧光亮度值 $F ( x _ { k } )$ 比较，保留最好的解。

e)若搜索次数达到 $C _ { \mathrm { m a x } }$ ，停止搜索；否则，转向步骤2。

# 2.3FCMM算法基本步骤

a)初始化参数：聚类对象总数N,吸收系数 $\gamma$ ,步长因子 $\alpha$ ，混沌搜索的最大迭代次数 $C _ { \mathrm { m a x } }$ ，最大荧光亮度 $I$ ，最大吸引度$\beta _ { 0 }$ 。

b)通过最大最小距离算法确定聚类中心数K，记录最大最小距离算法获得的初始聚类中心位置。

c)依次通过Tent映射构建以各个聚类中心为基准点的混沌搜索空间。

d)利用Tent混沌搜索更新初始聚类中心的位置，直到聚类中心不再变化。

e)将聚类中心对应于目标萤火虫，赋予最高荧光亮度。计算剩余的样本点相对于各聚类中心的欧氏距离，并按照式(3)赋予不同的荧光亮度。

f)如果 $I _ { i } > I _ { j }$ ,表示萤火虫j比i的目标函数值小，即j比i的位置好，萤火虫j将吸引i向它移动，移动方式由式(4)决定，并通过式(5)更新萤火虫位置。

g)重复步骤f)，直到所有萤火虫都被划分到所属的聚类中心。

h)输出结果。

# 3 实验结果与分析

# 3.1实验环境

为了验证算法的有效性，本文进行了三组实验。实验一通过对比不同算法的聚类效果图，验证本文算法聚类中心选取的有效性；实验二通过UCI数据集测试不同聚类算法的聚类精度和收敛速度，验证本文算法收敛速度较快、聚类精度有一定提高。实验三将本文算法与引言中介绍的基于自适应步长的萤火虫划分聚类算法（以下简称文献[7]算法）和加权的欧氏距离对K-means改进算法（以下简称文献[9]算法）的聚类效果进行对比分析。实验的运行环境为Windows7操作系统，4GB物理内存，CPU速度 $3 . 1 0 \mathrm { G H z }$ ，matlab2014b。

# 3.2 实验结果与分析

实验1聚类效果对比。随机选取200 个样本数据散布在解空间，经过最大最小距离算法得到聚类类别数 $\scriptstyle 1 = 4$ 。鉴于萤火虫算法的参数设定对实验结果有很大影响，本文采用水平实验得到最优解出现次数最多的组合，对步长因子 $\alpha$ 和光强吸收系数 $\gamma$ 采用枚举法得到一系列最优值组合，最后对结果进行分析得到了FA算法的参数取值情况。经30组实验结果分析对比，参数设置如下都会取得比较好的效果：最大吸引度 $\beta _ { 0 } ^ { \mathrm { ~ } } = 1 0 0$ ，吸收系数 $\gamma = 1$ ，步长因子 $\alpha = 0 . 0 6$ ，最大迭代次数 $C _ { \mathrm { m a x } } { = } 5 0$ ，最大荧光亮度 $\scriptstyle { \boldsymbol { I } } ^ { = 1 0 0 }$ ， $\theta = 0 . 4$ 。测试结果如图1所示。

由图1可以看出，传统K-means算法的部分聚类中心分布较为集中，明显存在局部最优问题；FA算法获得的聚类中心分布均匀性稍有改善，但聚类效果仍有待提高；本文算法相较于K-means和FA算法，聚类中心分布更均匀，明显改善了易陷入局部最优的问题，聚类效果更佳。

实验2选用标准数据集进行仿真，参数设置同实验一。为了验证本文算法的有效性，K-means、FA算法与FCMM算法分别在6种不同的数据集上进行独立实验，不同算法的平均聚类精度如表1所收敛曲线如图2所示。

![](images/536ba3efcdc473b1635095b75d7eaeefe65d629581a91818e833e625ad775f12.jpg)  
图1不同算法的聚类效果对比图

![](images/96a1d4c75ab77789d1e2fa93550192e11649abcc7f08ffa4772f4bac28fb09bc.jpg)  
图2三种算法在6种数据集上的收敛曲线

表1算法的平均聚类精度 $( \% )$   

<html><body><table><tr><td>数据集</td><td>K-means</td><td>FA 算法</td><td>本文算法</td></tr><tr><td>Iris</td><td>87.93</td><td>91.13</td><td>92.16</td></tr><tr><td>Wine</td><td>56.85</td><td>70.23</td><td>72.15</td></tr><tr><td>Seed</td><td>86.97</td><td>88.07</td><td>90.46</td></tr><tr><td>Glass</td><td>54.05</td><td>57.18</td><td>63.12</td></tr><tr><td>Hayes-Roth</td><td>77.32</td><td>81.06</td><td>82.35</td></tr><tr><td>New-thyroid</td><td>72.34</td><td>79.63</td><td>80.28</td></tr></table></body></html>

由表1可以看出，本文算法首先通过最大最小距离算法确定聚类中心数值K并引入混沌理论对聚类中心进行优化后，平均聚类精度相较于经典 K-means 算法和 FA 算法分别提高了$7 . 5 1 \%$ 和 $2 . 2 \%$ 。由图2看出，本文算法在保证较高聚类精度的前提下，相比于经典K-means和FA算法有较快的收敛速度。

实验3不同算法聚类效果对比分析。该实验将本文算法与引言中的基于萤火虫优化的K-means算法在聚类准确率和处

理时间等方面进行对比分析。

由表2可知，相对于文献[7]与文献[9]的算法，本文算法由于采用了最大最小距离算法进行初始聚类中心数值的分析，时间复杂度相对较高，处理时间略长；但是聚类精度明显较高。

# 4 结束语

本文针对K-means 算法易受初始聚类中心影响而陷入局部最优的问题，提出了新的FCMM聚类算法，分别在初始聚类中心的个数和聚类中心的位置分布两个方面对K-means算法进行了改进。本文提出的确定聚类中心数值K的方式，可以有效降低算法受初始聚类中心个数的影响。同时，在基于萤火虫优化K-means聚类算法的基础上，提出了通过混沌搜索的方式更新聚类中心位置的方法，由于混沌映射可以降低初始聚类位置对结果的影响，同时充分利用了萤火虫算法的寻优能力和收敛速度，成功解决了聚类过程易陷入局部最优解和收敛速度过慢的问题。

表2不同算法的仿真结果比较  

<html><body><table><tr><td>算法</td><td>本文算法</td><td></td><td></td><td></td><td>文献[7]算法</td><td></td><td></td><td>文献[9]算法</td><td></td></tr><tr><td>数据集</td><td>Glass</td><td>Hayes-Roth</td><td>Wine</td><td>Glass</td><td>Hayes-Roth</td><td>Wine</td><td>Glass</td><td>Hayes-Roth</td><td>Wine</td></tr><tr><td>聚类精度/%</td><td>63.12</td><td>82.35</td><td>72.15</td><td>62.45</td><td>81.28</td><td>70.71</td><td>60.70</td><td>81.46</td><td>70.43</td></tr><tr><td>处理时间/s</td><td>19.425</td><td>11.432</td><td>15.725</td><td>17.532</td><td>10.734</td><td>13.832</td><td>18.345</td><td>11.243</td><td>14.432</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>算法 数据集</td><td>Iris</td><td>本文算法 New-thyroid</td><td>Seed</td><td>Iris</td><td>文献[7]算法</td><td></td><td></td><td>文献[9]算法</td><td></td></tr><tr><td>聚类精度/%</td><td></td><td></td><td></td><td></td><td>New-thyroid</td><td>Seed</td><td>Iris</td><td>New-thyroid</td><td>Seed</td></tr><tr><td></td><td>92.16</td><td>80.28</td><td>90.46</td><td>91.22</td><td>79.01</td><td>89.52</td><td>91.49</td><td>79.98</td><td>89.70</td></tr><tr><td>处理时间/s</td><td>10.003</td><td>12.709</td><td>10.782</td><td>9.234</td><td>10.232</td><td>8.342</td><td>8.342</td><td>11.344</td><td>9.232</td></tr></table></body></html>

经过验证不同算法聚类效果的对比和UCI数据集聚类结果的分析，验证了本文算法在对少量数据进行聚类分析的过程中具有收敛速度快，聚类精度高，不易陷入局部最优问题。但是使用本文提出的算法处理较大数据集时，会产生时间复杂度较高的问题，所以需要研究如何更好的使用相似性准则去掉聚类中心候选集，这也是本文算法今后的改进和研究方向。

# 参考文献：

[1]Borgwardt S,Brieden A,Gritzmann P.An LP-based K-means algorithm forbalancing weighted point sets [J].European Journal of Operational Research,2017,263 (2).  
[2]Wangchamhan T,Chiewchanwattana S, Sunat K,et al.Efficient algorithmsbased on the K-means and Chaotic League Championship Algorithm fornumeric,categorical,and mixed-type data clustering[J].Expert Systemswith Applications,2017, 90.  
[3]Patel G K,DabhiVK,Prajapati HB.Clustering using a combination ofparticle swarm optimization and K-means [J]. Journal of Intelligent Systems,2016,26 (3).  
[4] 陈兴蜀，吴小松，王文贤，等．基于特征关联度的K-means 初始聚类中心优化算法 [J]：四川大学学报：工程科学版,2015,47(1):13-19.  
[5]张强，王红卫，陈游，等．基于自适应权重的RFCM聚类算法[J].微电子学与计算机,2016,33(12):80-84.  
[6]赵杰．群智能优化算法在聚类分析中的应用研究[D].西安：陕西师范大学,2015.  
[7] 潘晓英，陈雪静，李昂儒，等．基于自适应步长的萤火虫划分聚类算法[J].计算机应用研究,2017,34(12):3576-3579.  
[8]王冲，雷秀娟．新的小生境萤火虫划分聚类算法[J].计算机工程,2014,40 (5): 173-177.  
[9] 陈小雪，尉永清，任敏，等．基于萤火虫优化的加权K-means 算法 [J].计算机应用研究,2018,35(2).  
[10]陈望，贾振红，覃锡忠，等．基于改进K-means聚类算法的室内WLAN定位研究[J].激光杂志,2014,35(7):11-14.  
[11]徐鹏程，王诚.K-means 算法改进及基于 Spark 计算模型的实现[J]．南京邮电大学学报：自然科学版,2017,37(04):113-118.  
[12]匡芳君，徐蔚鸿，金忠．自适应Tent 混沌搜索的人工蜂群算法[J].控制理论与应用,2014,31(11):1502-1509.  
[13]单梁，强浩，李军，等．基于Tent 映射的混沌优化算法[J].控制与决策,2005,20 (2): 179-182.  
[14]赵杰，雷秀娟，吴振强，等．基于最优类中心扰动的萤火虫聚类算法[J]．计算机工程与科学,2015,37(2):342-347.