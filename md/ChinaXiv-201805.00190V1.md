# 基于熵准则遗传算法的点云配准算法

陈杰a，蔡勇a,b，张建生a

(西南科技大学 a.制造科学与工程学院;b.制造过程测试技术省部共建教育部重点实验室，四川 绵阳 621010)

摘要：迭代最近点(ICP)算法由于其配准精度很高，通常运用于点云的精配准，但其配准精度和迭代收敛性取决于待配准点云的初始位置。提出一种将遗传算法和空间分布熵相融合的空间最优变换矩阵求解算法，以一种新的点云空间位置评价方法——空间分布熵作为遗传算法的目标函数，采用遗传算子指导解的搜索方向，通过新种群的不断迭代达到空间分布熵最小，结束后对最优个体解码实现点云的粗配准。实验表明，该算法有效可行，克服了传统方法在有点云缺陷和噪声点时不能提供很好的初始拼接位置的问题，在误差允许的范围内，可以直接实现点云拼接。

关键词：迭代最近点算法；遗传算法；空间分布熵；配准 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.03.0642

# Point cloud registration based on entropy criterion genetic algorithm

Chen Jiea, Cai Yonga,b, Zhang Jianshenga (a.SchoolofManufacturingScience&Engineering,b.KeyLaboratoryofTesting TechnologyforManufacturingProces, Southwest University of Science& Technology,Mianyang Sichuan 62101o, China)

Abstract: The iterativeclosest point (ICP)algorithm is usuallyused in thefineregistrationof pointcloud becauseofits high registration acuracy,but itsregistration acuracyanditeration convergence dependontheinitialregistrationpositionof the point cloud toberegistered.This paper proposed analgorithmofspatial optimizationtransformation matrix combining genetic algorithm with spatialdistributionentropy,in which usedanew pointcloud spatial position evaluationmethodas theobjective functionof genetic algorithm,used and genetic operator to guide the solution ofsearch direction.The algorithm achievs the minimumspatialdistributionentropythroughthenewpopulationofiterations,afterwhichthecoarseregistrationofpointcloud is achievedbydecoding theoptimal individuals.Theexperimentalresultsshowthatthealgorithmiseffectiveandfeasible,and itcanovercomethe problemthat traditional methodcan'tprovideagood initial position whenthedefectsand noiseexist inthe point cloud. The algorithm can directly realize point cloud registration within the acceptable error range.

Key Words: iterative closest point algorithm (ICP); genetic algorithm; spatial distribution entropy; registration

# 0 引言

随着三维扫描仪不断的向高精度、高质量发展并且越来越普及，三维扫描的点云配准技术是非常重要的技术，已经在许多行业有大量的应用。如逆向工程、产品检测、机器人姿态调整、文物保护、计算机视觉、计算机图形学和模式识别等领域有广泛的应用，是一个非常重要的研究领域。操纵各类扫描仪器对物体的轮廓来准确采样，得到三维空间一些分散的的点，所有点的集合称为点云。利用获取的模型轮廓的采样点来表示模型，在计算机上通过点云信息进行三维重建。对于体积庞大和表面复杂的物体，每次只能扫描物体一部分，如果要形成一个完整的模型往往需要多次扫描完成。获取的点云是相互没有联系的，要完整、真实的来表示物体的轮廓，需要将多个角度扫描的点云经过坐标变换放在同一个坐标系下，这个操作就是点云配准。

点云配准本质上是计算旋转平移矩阵，目的是使物体表面同一个部位的点云重合在一起。一般在粗配准后再进行精配准是点云配准中比较常见并且有效的方法。粗配准就是把初始位置任意的两片点云放在大体正确的位置上，以便为精配准提供良好的初始位置，使配准收敛到全局最小，提高配准的效率和精度；精配准是使物体表面同一个部位的点云到达完全重合的状况。

Besl等人[1在1992年首次提出了迭代最近点（iterativeclosetestpoint，ICP）算法，该算法在配准正确的情况下有很高的精度，是现在最成熟最优良的精配准算法。原始ICP算法的基本思想是：在两点集中一一寻找对应点，并计算所有相对应点欧氏距离平方的平均值，并同时更新点云之间的相对位置，再重复以上的过程直至算法收敛，算法收敛即平均值最小，两片点云达到最佳的位置，至此点云配准完成。

Besl提出的经典ICP算法的缺点和局限有很多：第一，原始ICP收敛速度和是否收敛于正确的位置在很大程度上依赖于初始位置；第二，每一次迭代都需要为每个点寻找最近点，产生对应点，那么当点云数量比较大将会非常耗时；第三，由于两片点云是部分重合且存在噪声点，有些点云并没有相对应的点，而原始ICP假设的是这些点是不存在的，而当存在这些点时又没有被剔除，将会严重影响算法的运行效果。针对以上缺点和局限性，国内外许多学者对该算法进行了改进，并以此形成了许多变种的ICP 算法[2\~3]。

为了解决文章提到的ICP依赖初始位置的缺陷学者提出一系列粗配准方法，文献[2]使用PCA（principal component analysis）主成分分析法，能快速的进行点云配准，但是针对有大量噪声和只有部分重合的点云不能很好地提供优良的初始位置；文献[3]通过提取点云边界特征点，在匹配边界点以实现粗配准，但是该方法精度不高,并且特征提取比较耗时；文献[4]通过迭代最小空间分布熵法为点云实现粗配准，但该方法精度不高，且比较耗费时间。

近些年来也提出一些随机算法[5\~II]，文献[5]采取优化算法中遗传算法结合均值平方误差(MSE)度量准则来实现点云粗配准，虽然精度较高但效率很低；文献[6]提出一种将优化算法中遗传算法结合O'Rourke算法求解最小包围盒的算法；Chen等人[8]在1999年首次运用RANSAC算法进行三维点云配准，该方法有较高的鲁棒性，不需要模型的几何特征，也不需要提供初始位置，对小部分重合的点云处理非常有效，但是时间复杂度非常大；文献[9]提出了4PCS（4pointcongruent set）技术结合RANSAC 算法，对以前随机抽样三个点改用四点集充分利用图形的几何关系，加快对应点集搜索速度，虽然4PCS技术极大的提高了 RANSAC 方法的效率，但是 $\mathrm { O } { \left( N ^ { 2 } \right) }$ 算法复杂度针对庞大的数据耗费的时间也是比较多的；文献[10]运用采样球配准方法，加快了寻找与“基”重合的三点基，同时在噪声点和异常值点的抵抗能力比以前的RANSAC配准更强；文献[12]针对局部大变形模型进行处理，利用遗传算法提供初始位置在利用ICP算法进一步配准得出某一偏差值，设定该偏差值为阈值去除偏差大的点云，剔除了局部大变形的点云在运用最小二乘法进行配准；文献[13]改进遗传算法目标函数为测量点到三角面片的距离平方和，并利用参考球加快了距离计算速度，大大节省时间。基于以上分析，提出一种基于熵准则遗传算法的点云粗配准方法，使用空间分布熵做为遗传算法的目标函数，能快速将未知任何信息的两片点云放在大体的位置上，为精配准提供良好的初始值。空间分布熵能准确的度量空间点云贴合程度，使算法具有优良的鲁棒性。

# 1 算法简介

该算法首先运用八叉树对待配准的点云P和点云Q建立三维立方栅格，然后统计在每一个立方栅格内的点云的点数，最后求取点云空间分布熵。点云配准分两步：粗配准和精配准。粗配准运用空间分布熵准则为目标函数，遗传算法求解空间最优变换矩阵；精配准使用改进ICP算法求解满足精度的空间变换。

# 1.1 空间立体栅格

本算法利用八叉树[14]建立空间立方栅格，采用分割结束的条件为节点栅格对角线长度的平方，即：

$$
l = \left( x _ { _ { m a x } } - x _ { _ { m i n } } \right) ^ { 2 } + \left( y _ { _ { m a x } } - y _ { _ { m i n } } \right) ^ { 2 } + \left( z _ { _ { m a x } } - z _ { _ { m i n } } \right) ^ { 2 }
$$

其中 $x _ { m a x }$ $, \mathrm { ~ \it ~ y ~ } _ { m a x } , \mathrm { ~ \it ~ z ~ } _ { m a x }$ 为节点栅格每个坐标轴方向上的最大值，$x _ { m i n }$ ， $y _ { m i n }$ ， $z _ { m i n }$ 为最小值。

每个栅格大小是相同的，由于点云数据通常不是均匀的，进行栅格化后每个栅格中的点数是不同的。点云重合的部分相对于其他部分的点云要密集一点，点云的疏密程度通过栅格中点数的多少能很好的描述，即点云分布越密集该区域的栅格点数越多，反之越稀疏。

# 1.2 空间分布熵

本文的空间分布熵[4]是描述的点云的位置信息与信息熵[15]有许多相似之处。不同视角扫描的点云空间位置通常是任意的，处于不同的坐标下位置相差很大，因此不确定性也非常大。当两点云实现了配准，相对位置是最小的，也是唯一确定的。点云的空间分布熵能准确的描述点云配准时的位置关系。点云空间分布熵求解流程如下：

（1）点云 $D$ 包含 $N$ 个数据点，将其利用八叉树进行均匀三维栅格化。

（2）点云被栅格划分，记录每个立方栅格分配的点记为$n { \big ( } i , j , k { \big ) }$ ，并计算点云落在每个立方栅格内的概率 $p { \big ( } i , j , k { \big ) }$ ，计算式为

$$
p { \left( i , j , k \right) } = \frac { n { \left( i , j , k \right) } } { N }
$$

其中： $i = 1 , 2 , 3 \Lambda$ ， $n _ { x }$ ; $j = 1 , 2 , 3 \Lambda$ K $n _ { y }$ ; $k = 1 , 2 , 3 \Lambda$ ； $n _ { x }$ ， $n _ { y }$ ， $n _ { z }$ 分别表示每个坐标轴方向的栅格数目。

（3）计算点云D的空间分布熵（SDE)，计算式为

$$
E _ { S D } = - { \sum _ { i = 1 } ^ { n _ { x } } } \sum _ { j = 1 } ^ { n _ { y } } \sum _ { k = 1 } ^ { n _ { z } } p \left( i , j , k \right) \mathrm { l n } { \left[ p \left( i , j , k \right) \right] }
$$

由算法可知，点云空间分布熵（SDE）只需要建立三维栅格统计落在每个栅格中点数，算法的时间复杂度是很低的，而均值平方误差(MSE)[4]需要为一片点云的每一个点，到另外一片寻找最近点形成一一对应点，每次都需要全局遍历，因此算法的时间复杂度很高。

已知给出完全重合的两片bunny 模型点云 $P$ 和 $\varrho$ ，现对 $\varrho$ 进行如下操作：将其绕 $Z$ 轴顺时针旋转角度 $\theta$ ， $\theta$ 在 $- \pi \sim \pi$ 之间以0.0314rad 等间隔取值，旋转后的 $\varrho$ 记为 $Q ( \theta )$ 。点云$D ( \theta )$ 由 $P$ 和 $Q ( \theta )$ 组成，计算 $D ( \theta )$ 的 MSE 和 SDE，图1(a)所示的为MSE 的值，图1(b)所示的为 SDE 的值。表1给出了采用 MSE 和 SDE 评估整个 $Q ( \theta )$ 点云空间位置所需时间的比较。

![](images/5d8e7df5bb1399408982d875e3707830e9f05cc02a5abb964f10102849edd8ab.jpg)  
图1不同空间位置的评估值

表1MSE和SDE评估点云空间位置的时间比较  

<html><body><table><tr><td>点云评估</td><td>MSE</td><td>SDE</td></tr><tr><td>Times/s</td><td>93.159261</td><td>3.135315</td></tr></table></body></html>

由图1可知，MSE 和SDE 都满足空间位置的估计，当点云完全配准时MSE和SDE 都是全局最小。由表1可知，SDE估计点云空间位置运行效率比MSE高很多，可以用于频繁的调用。

由于空间分布熵是基于点云落在每个立方栅格内的概率$p { \big ( } i , j , k { \big ) }$ ，在相同空间范围内建立的立方栅格越多对点云的空间位置表示的越精确，但是随着立方栅格的增长计算的时间也相应的增加，所以合理选择分割结束条件对算法性能改善很大。考虑到空间分布熵对空间位置估计的有效性和快速性，本文bunny模型选用节点栅格对角线长度的平方l为0.003。表2对选用bunny模型对空间分布熵估计点云位置有效性和快速性的验证。

表2节点栅格的长度对运行时间的比较  

<html><body><table><tr><td>长度</td><td>0.001</td><td>0.003</td><td>0.005</td><td>0.007</td></tr><tr><td>Times/s</td><td>3.568808</td><td>2.876564</td><td>2.814571</td><td>2.794607</td></tr></table></body></html>

# 1.3遗传算法

遗传算法[16,17]是一种进化学习的优化算法。由于遗传算法进化学习不断保留优良个体同时又产生新的个体特点，所以不仅具有极强的鲁棒性，也可以利用设计变量在设计空间进行多点搜索，具有较强的全局搜索能力，同时该方法还具有全局收敛性及对初始值要求不严格的特点。遗传算法过程描述如下：

a)编码。将求解的问题转换为遗传算法的基因型串结构数据。

b)初始群体的生成。随机生成一个种群的基因型数据。

c)适应度值评价检测。根据目标确定合适的适应度函数评价个体的适应性。

d)选择与遗传。种群中优良的个体被选择遗传到下一代，子代由父代交叉变异产生更优的个体。

e)迭代终止。满足迭代终止条件，算法停止选择与遗传，在进化过程中最优的个体就是最优解。

# 2 基于熵准则遗传算法配准

本文利用基于熵准则的遗传算法进行粗配准。首先确定目标函数，空间分布熵度量两片重合部分重合程度确定位置关系；然后根据遗传算法的操作选择、复制、交叉、变异不断迭代；最后找出最优的旋转和平移矩阵。

# 2.1 目标函数的建立

配准的目标是把不同角度扫描的点云转换在同一视角下，点云空间分布熵能快速、准确地计算转换的结果，将空间分布熵作为遗传算法的目标函数，即将遗传算法的目标设定为解决点云空间分布熵的最小值求解问题。设空间分布熵函数为$E _ { s D } \big ( P , ~ Q _ { i } \big )$ ，其中 $P$ 为参考点云， $Q _ { i }$ 为变换后的目标点云。基于该函数可精确获得局部最优解，遗传算法中每个个体都需要计算目标函数，因此需要频繁的调用，将其作为目标函数能够保证求解精度，有效缩小搜索范围，有助于提高遗传算法的运行效率。

# 2.2遗传算法的选择

2.2.1染色体实数编码

三维空间的物体具有六个自由度即三个转动和三平移$\left[ \alpha , \beta , \gamma , T _ { x } , T _ { y } , T _ { z } \right]$ ，变换矩阵可由六个自变量组成旋转自变量$\alpha , \beta , \gamma$ 的变化范围为 $\left[ - \pi , ~ \pi \right]$ ,平移自变量的变化范围由参考点云 $\mathrm { ~ \bf ~ P ~ }$ 得到,每个坐标轴方向的变化范围 $\left[ - x , x \right] , \left[ - y , y \right] , \left[ - z , z \right]$ 可表示为

$$
\begin{array} { r } { x = \left( x _ { _ { m a x } } - x _ { _ { m i n } } \right) / \ : 2 } \\ { y = \left( y _ { _ { m a x } } - y _ { _ { m i n } } \right) / \ : 2 } \\ { \mathbf { z } = \left( \mathbf { z } _ { _ { \operatorname* { m a x } } } - \mathbf { z } _ { _ { \operatorname* { m i n } } } \right) / \ : 2 } \end{array}
$$

其中： $x _ { m a x }$ ， $x _ { m i n }$ ， $y _ { m a x }$ ， $y _ { m i n }$ ， $z _ { m a x }$ ， $z _ { m i n }$ 分别为点云 $P$ 在 $X$ ，Y、 $Z$ 坐标轴方向上的最大值与最下值。

# 2.2.2适应度函数

在遗传算法中实现“自然选择”最重要的依据是适应度函数。本文的目标函数是空间分布熵(SDE)， $S D E$ 小的个体是优良个体被选择概率越大。本算法采用基于排序的适应度分配。根据个体 $S D E$ 值按照由小到大顺序排序，并通过适应度函数计算出对应个体的适应度值 $F i t n V _ { \circ }$ 有适应度函数可知 $F i t n V$ 越大个体越优良。

适应度函数为

$$
F i t n V ( P o s ) = 2 - s p + 2 \times ( s p - 1 ) \times \frac { P o s - 1 } { N i n d - 1 }
$$

其中： $s p$ 为个体的 $S D E$ 值； $P o s$ 该种群排序后在种群中的位置；  
Nind为种群个体的数量。

# 2.2.3选择与遗传

本文采用杰出策略方法进行选择操作算子，即当前最优给提直接传给下一代，采用随机遍历抽样选择法来对其他的染色

体进行选择，随机遍历抽样选择法是依据随机产生的种群，产生一个随机数就产生一个染色体，而它被选中的概率与其适应度函数成正比：

$$
F ( x _ { i } ) = { \frac { f ( x _ { i } ) } { \displaystyle \sum _ { i = 1 } ^ { N \operatorname* { i n } d } f ( x _ { i } ) } }
$$

其中： $f \left( x _ { i } \right)$ 是个体 $x _ { i }$ 的适应度， $F \left( x _ { i } \right)$ 是这个个体被选择的概率。

由于染色体采用实数编码的范式，交叉算子也同样采用实数交叉算子中的离散重组。变异算子采用实值种群的变异。一个变量的变异是由以下计算得到的：

$$
X ^ { ' } = X + M u t M x \times r a n g e \times \beta \times d e l t a
$$

其中：MutMx控制是否变异，数值在1、0、-1中随机取数；range $= 0 . 5 \times$ 变量的域(见2.2.1)； $\beta$ 是压缩变异的范围，数值是[0,1]之间的一个数；delta 是变异步长的大小。

# 2.3算法步骤

本文遗传算法实现使用现存比较流行、较为完善MATLAB遗传算法工具箱[18]。目标函数和选择遗传操作如前面所述，则算法的流程如下：

（1）在最大变量域初始化种群 $P$ 。（2）种群 $P$ 分别运用于目标点云，求取每次初始变换的空间 $x$ 、y、 $z$ 最大最小值，求取整个空间的 $\ x , \ y , \ z$ 最大最小值，确定最大变换空间位置。（3）计算其目标函数和适应值。(4)选取种群中最优个体得到其空间分布熵 $S D E$ ，令全局最小空间分布熵 $S D E _ { m i n } { = } S D E$ ，并设定最大代数 $G$ 。（5）根据适应度值进行优良个体选择，对选择的种群进行交叉和变异操作，产生新一代进化种群。（6）求解新一代种群所有个体的适应值 $F i t n V$ ，比较该代最优个体的空间分布熵 $S D E$ 和全局最小空间分布熵 $S D E _ { m i n }$ ，如果 $S D E { < } S D E _ { m i n }$ 则 $S D E _ { m i n } = S D E$ 。(7)检查当前代数是否达到最大代数 $G$ 和 $S D E$ 是否收敛，若没有达到，则转到步骤(5)，继续求解；否则，输出全局最优个体，解码得到空间最优旋转、平移矩阵，算法结束。

（8）更新点云位置，输出配准点云。

基于熵准则遗传算法流程如图2所示。

![](images/0bbbb2bb1742965f4fffd8ff6f276b79491e94e2cd1da221006982356d3a0e25.jpg)  
图2基于熵准则遗传算法流程

# 3 实验结果与分析

为了验证算法的可行性、鲁棒性和有效性，在IntelCore-i5，2GB内存的Windows7操作系统上，熵准则的遗传算法基于MATLAB平台进行粗配准实验，精配准ICP 算法基于Visual$\mathrm { C } { + } { + }$ 平台进行精配准实验，主要从有缺陷的点云和有大量噪声点两方面来进行验证。以 Stanford 的bunny、cow、man 模型为例，两个不同视点下的成像数据 $P$ 和 $\varrho$ 为例，如图所示。图3\~6分别给出了粗配准前后参考点云和目标点云的相对位置，其中（a）两片点云位置相错 $9 0 ^ { \mathrm { o } }$ ，（b）为使用本文算法粗配准后的结果。

a）精简后的bunny 模型b)有大量噪声点的模型c）有点云缺失的点云模型

![](images/ad59ca931f31f8f9a1f24e42136d733b146ea2e6824a62679fc9519b2d884188.jpg)  
图3精简bunny点云粗配准前后相对位置

![](images/731c9172a2d07ffc7a9c0030240146ef1048a64077f2b7eb81caea8413538e09.jpg)  
图4存在噪点点云粗配准前后相对位置

![](images/af4c7af3052cf34c8e1dcdfd23dea16579e1a6cfd270465296eaf25a5a06f139.jpg)  
图5精简1/2点云粗配准前后相对位置

![](images/46b814d9c448789cb4a8272597d75e28951828df6f7731d565466887f85ec00b.jpg)  
图6精简1/4点云粗配准前后相对位置

为观察遗传算法各代的数据变化规律，以图3精简后的bunny模型的求解过程为例，如图7所示显示每代个体SDE的最小值和该代所有个体SDE的平均值的变化规律。

![](images/d7207dc17ff84fed1866bf0c781f5e0e053f2cd34963380561355d883fb49a1d.jpg)  
图7优化解的目标函数值及性能跟踪

由图7可知，求解过程中各代的SDE平均值越来越小，种群整体向着最优的方向进行，全局最优解在迭代过程中根据各代局部最优解的情况不断更新，最终迭代到全局最优及SDE最小。图3\~6中(b)都是迭代到全局最优及SDE最小的结果。从配准结果可以表明本文算法能处理重合部分很小的模型，同时能抵抗噪声点和异常值点的干扰。

本文粗配准算法、基于MSE的遗传算法、参考球加速的遗传算法、快速的PCA、4PCS算法进行粗配准效果对比如图8所示。

由图8可以看出，本文算法、MSE、文献[13]、4PCS对完整点云和部分重合的点云都能提供初始位置，PCA的方法针对部分重合的点云粗配准不能提供初始位置。配准结果表明，基于熵准则的遗传算法能够有效地对点云进行粗配准。

骨宵宵宵宵宵(a)配准前点云 (b)MSE (c)文献[13] (d)PCA (e)4PCS (f)本文算法

表3不同模型粗配准时间 /s  

<html><body><table><tr><td>模型</td><td>MSE</td><td>文献[13]</td><td>PCA</td><td>4PCS</td><td>本文</td></tr><tr><td>cow(2904)</td><td>72.98</td><td>50.50</td><td>0.32</td><td>40.35</td><td>36.83</td></tr><tr><td>bunny(35947)</td><td>168.73</td><td>122.35</td><td>1.35</td><td>75.89</td><td>72.63</td></tr><tr><td>man(7492)</td><td>100.62</td><td>70.20</td><td>0.56</td><td>38.26</td><td>42.36</td></tr></table></body></html>

表3展示了粗配准的时间，遗传算法和RANSAC都是随机性算法，算法运行的时间与设置的参数有很大的关系。

![](images/34836e035df7a53b13574d399ec97ba0b9261615592412834bca5bc15b9b4618.jpg)  
图8点云的粗配准后相对位置关系  
图9点云点数与时间的变化曲线

图9所示是本文算法(SDE)、MSE、文献[10]在点云点数不同情况下配准所用的时间。遗传算法的初始种群和遗传代数对算法运行时间有很大的联系，三种算法都设置初始种群为80，遗传代数为40。从图9可以看出，文献[13]和MSE配准的时间随着点数增多上升迅速，而SDE方法上升很平缓，说明基于熵准则的遗传算法可以进行大规模的点云配准。MSE 和文献[13]求解目标函数都要全局搜索对应点求解距离，随着点数增大，搜索时间急剧增加。

运用基于熵准则的遗传算法进行粗配准的提供的初始位置，在利用KDtree 寻找最近点的改进ICP算法进行精配准，并与传统ICP[算法和文献[3]进行比较，如表4所示。由表4可看出，本文的在运行效率上由于其他两种方法，都能达到精度要求。

配准精度的评判，采用文献[3]使用的标准，计算公式如下：

$$
\varepsilon = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } F a i l { \Big ( } p _ { 1 _ { i } } , p _ { 2 _ { i } } { \Big ) } } { N } }
$$

Fail(P,P）定义如下:

$$
F a i l { \left( p _ { _ { 1 } } , p _ { _ { 2 _ { i } } } \right) } = \left\{ { 1 \atop 0 } \right. \quad d { \left( p _ { _ { 1 } } , p _ { _ { 2 _ { i } } } \right) } > \delta
$$

其中： $\varepsilon$ 代表不能满足精度要求对应点数的比例； $N$ 代表对应

点对数量； $d ( p _ { 1 _ { i } } , p _ { 2 _ { i } } )$ 代表对应点之间的距离； $\delta$ 代表距离阀值;  
$F a i l ( p _ { 1 _ { i } } , p _ { 2 _ { i } } )$ 代表对应点是否满足精度要求。

表4点云数据配准效果比较  

<html><body><table><tr><td>算法</td><td>配准时间</td><td>配准精度</td></tr><tr><td>传统ICP</td><td>42.78</td><td>0.00106324</td></tr><tr><td>文献3</td><td>80.56</td><td>0.00023852</td></tr><tr><td>本文算法</td><td>40.67</td><td>0.00019683</td></tr></table></body></html>

# 4 结束语

点云数据配准是逆向工程的基础，配准的鲁棒性、效率和精度对点云配准非常重要。本文算法对于有异常值和部分重合的原始点云的处理有较好的效果，但是在效率上还有待改进。

本文算法具有以下特点：

a)通过遗传算法避免了对整个变量域的逐一搜索，由于进化的导向性能快速的获得近似最优解，有效提高了最小点云空间分布熵的求解效率；b)空间分布熵是基于空间点云密度求解，当点云有异常值时对空间位置的估计影响不是很大；c）遗传算法能进行并行计算的特点，在此基础上可进一步提高求解效率。

ICP算法精度高的特点成为精配准的通用方法，如何快速、精准地为ICP算法提供良好的初始位置显得很具有挑战性，在后续工作中继续改进本文算法，以进一步提高算法的效率。

# 参考文献：

[1]BeslPJ,MckayHD.A method for registration of 3-D shapes [J].IEEETrans on Pattern Analysis& Machine Intelligence,2002,14(2): 239-256.  
[2]戴静兰，陈志杨，叶修梓.ICP 算法在点云配准中的应用[J]．中国图象图形学报,2007,12(3):517-521.  
[3]王欣，张明明，于晓，等．应用改进迭代最近点方法的点云数据配准[J]．光学精密工程,2012,20(9):2068-2077.  
[4]左超，鲁敏，谭志国，等．一种新的点云拼接算法[J]．中国激光,2012,

39 (12): 211-218.

[5]Silva L, Bellon OR P,Boyer K L.Precision range image registration using a robust surface interpenetration measure and enhanced genetic algorithms [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2005,27(5): 762-76.   
[6] 孙殿柱，史阳，刘华东，等．基于遗传算法的散乱点云最小包围盒求解 [J]．北京航空航天大学学报,2013,39(8):995-998.   
[7]Mavridis P,Andreadis A,Papaioannou G.Efficient sparse ICP[J]. Computer Aided Geometric Design,2015,s35-36(C): 16-26.   
[8] Chen C S, Hung YP, Cheng JB.RANSAC-based DARCES: a new approach to fast automatic registration ofpartially overlappng range images [J]. IEEE Trans on Pattern Analysis& Machine Inteligence,2002,21(11): 1229-1234.   
[9]Aiger D,Mitra N J, Cohen-Or D.4-points congruent sets for robust pairwise surface registration [J].ACM Trans on Graphics,20o8,27(3): 85.   
[10] Meng Y, Zhang H. Registration of point clouds using sample-sphere and adaptive distance restriction [J].Visual Computer,2011,27(6-8): 543-553.   
[11]雷玉珍，李中伟，钟凯，等．基于随机抽样一致算法的误匹配标志点校 正方法[J].光学学报,2013,33(3):205-212.   
[12]武殿梁，黄海量，丁玉成，等．基于遗传算法和最小二乘法的曲面匹配 [J].航空学报,2002,23(3):285-288.   
[13]平雪良，耿鲁，华婷，等．遗传算法在点云配准技术中的应用[J].机 械科学与技术,2010,29(6):809-812.   
[14]郑德炯，卢科青．基于自适应八叉树的三维点云快速拾取方法研究[J] 机电工程,2016,33(4):417-420.   
[15] Lee C Y,Han SK.Evolutionary optimization algorithm by entropic sampling [J].Physical Review E Statistical Physics Plasmas Fluids& Related Interdisciplinary Topics,1998,8753 (3): 3611-3617.   
[16] Goldberg D E.Genetic algorithm in search,optimization,and machine learming [J].1989, xii (7): 2104-2116.   
[17]曲志坚，张先伟，曹雁锋，等．基于自适应机制的遗传算法研究[J]. 计算机应用研究,2015,32(11):3222-3225,3229.   
[18]雷英杰，张善文，李续武，等.MATLAB 遗传算法工具箱及应用[M]. 西安：西安电子科技大学出版社,2005:8-14.