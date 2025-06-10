# 基于 $\boldsymbol { L } _ { 1 }$ 范数的形状快速匹配算法

王江辉，吴小俊

(江南大学 物联网工程学院，江苏 无锡 214122)

摘要：针对内距离形状上下文 IDSC（inner-distance shape context）和轮廓点分布直方图 CPDH（contours pointsdistribution histogram）在形状相似性度量中直方图匹配耗时长，工程应用性不佳的问题，提出了一种用 EMD $. L _ { 1 }$ 测量轮廓特征直方图的距离的方法。EMD $. L _ { 1 }$ 在原始EMD(earth mover'sdistance)的基础上融合了 $L _ { 1 }$ 范数，通过替换地面距离计算方法，减少了目标函数的变量，加快了直方图匹配的速度，能够快速实现形状匹配并保持较好的检索性能。对形状数据集进行仿真实验的结果证明，该方法能够有效地进行数据集的形状识别和检索，并且在MNIST 数据集下的匹配速度优于其他算法。

关键词：内距离形状上下文；轮廓点分布直方图；地球移动距离 (EMD)； $L _ { 1 }$ 范数；形状检索 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.08.0893

# Fast shape retrieval based on $L _ { 1 }$ norm

Wang Jianghui,Wu Xiaojun (SchoolofIoT Engineering,Jiangnan University,Wuxi Jiangsu214122,China)

Abstract; Inorder tosolve the problem that thehistogram matching time islongand theenginering application is poor.This paper proposed to use EMD- $. L _ { 1 }$ to measure the distance between two feature histograms. EMD- $. L _ { 1 }$ fusion of the $L _ { 1 }$ norm and the originalEarth Mover'sDistance(EMD)andreplacethecalculationof the ground distance.The algorithmreduce the numberof unknownvariables,couldachieveshapematchingquicklyandhasagoodretrievalperformance.Withagreatdealofexperiments in several shape databases,theresults show that the performanceof novel method are superior tooriginal algorithm.And the matching speed is better than other algorithms under the MNIST data set.

Key Words: inner-distance shapecontext(IDSC);contour pointsdistribution histogram(CPDH);earth mover’s distane(EMD); $L _ { 1 }$ norm; shape retrieval

# 0 引言

形状是物体的一项重要特征，相比纹理、灰度等外观特征，形状具有更深层次的视觉信息[1-2]。形状的匹配应用于计算机视觉的许多领域，如目标识别，图像检索等都可以利用形状作为分类与识别的一项依据。其中形状检索又可以分为2D形状与3D形状检索，因为最近几年深度学习发展迅速得到了众多学者的青睐。提出了大量基于深度学习的3D形状检索算法[3,4]。但是2D形状检索依旧是计算机视觉中的代表性问题。二维形状匹配的过程主要可以分为两部分：首先设计一种形状描述子，即通过某种方式来描述和表示形状；然后计算不同形状的描述子间的距离来衡量形状间的差异完成匹配。该方法主要分为基于形状组成点集、形状边界轮廓和形状内部骨架3类来描述形状特征。轮廓相比点集增加了点的顺序信息，骨架则包含了形状的几何特征和拓扑结构[5]。基于轮廓的方法有多尺度法，如多尺度三角形面积（triangle-arearepresentation,TAR）[6]、多尺度凹凸性（multiscaleconvexity，MCC）[7]、多尺度积分不变量[8]等。这类方法通过构建多个尺度下的形状特征来拓展特征信息。形状上下文[9]（shapecontext，SC）是基于轮廓点相对位置关系的经典方法，该算法注重轮廓中某个点与其他所有点的空间分布关系，但是其方法抗噪能力差，采用薄板样条函数（TPS）计算直方图距离耗时长。

Ling在SC的基础上用轮廓点的内部距离代替欧氏距离来衡量轮廓点的差异，提出了内距离形状上下文（inner-distanceshape context,IDSC）[10]方法。该方法对非刚性物体轮廓的形状描述具有良好的表示，并采用动态规划算法度量目标形状之间的距离。但是其计算复杂度高，实用性不佳。

Shu 和 $\mathrm { { W u } ^ { [ 1 1 ] } }$ 提出了一种2维形状描述符—一轮廓点分布直方图（contours points distribution histogram，CPDH）。CPDH以目标形状的最小外接圆为特征提取区域，以轮廓特征点分布为统计对象，以外接圆圆心为原点建立极坐标下的轮廓点分布直方图。CPDH用地球移动距离(EarthMover'sDistance,EMD)度量直方图之间的距离。但是CPDH侧重于轮廓局部特征描述导致其在形变较大的形状数据集下性能不佳，检索不稳定且EMD算法时间复杂度高，在形状匹配时速度过慢。

本文提出用EMD- $\cdot \mathrm { L } _ { 1 }$ 度量[12]由轮廓描述子生成的两幅形状轮廓特征直方图的相似度，EMD-Li在原始EMD[9]基础上利用Li范数（曼哈顿距离)作为一种新的地面距离。改进后的EMD-Li通过减少函数的变量和约束条件，降低了计算复杂度，加快了形状匹配速度，而且并没有弱化形状描述子的鉴别能力。除此之外Li范数在特征提取中也有去噪，减少异常值的优点，可使形状描述子更具鲁棒性通过在各数据集下检索效果的实验分析，该改进算法有效地保持了IDSC和CPDH在良好的检索性能，提高了匹配速度，增强了工程应用型。

# 1 CPDH与IDSC算法基本原理

轮廓特征是图像最本质的特征，CPDH是基于轮廓点分布的基础上提出的一种目标特征描述符。IDSC 是基于采样点之间的空间分布关系且在内距离的基础上提出的一种具有良好表示的形状描述符。

# 1.1构建CPDH描述符

首先采用标准的Canny算子对图像目标轮廓进行提取,但由于目标形状轮廓的点数过多，为了减少计算量满足实时性的要求,采用等间隔距离方法对轮廓点进行采样,得到轮廓的部分点集。 $P = \{ p _ { 1 } , p _ { 2 } , p _ { 3 } , . . . , p _ { n } \} , p \in I R ^ { 2 }$ 式中， $n$ 表示点的数量，来描述物体的形状,如图1所示。图中，(a)为初始图像;(c)提取的采样点轮廓图像;(d)为目标形状的最小外接圆图像。

![](images/27d44eb2caf72e524534f02f4e524d14a259c356882181e6346ebfabc4542953.jpg)  
图1轮廓提取效果图

以轮廓点集 $P$ 为目标区域建立其最小外接圆 $C ,$ 以圆心 $( C x$ $C y )$ 为原点建立极坐标系统,在该最小外接圆内以同心圆方式建立如图2所示扇形网格模型来统计轮廓点的分布特征。对每一个扇形区域 $R _ { i }$ ，得到三元组 $H _ { i } = \{ \rho _ { i } , \theta _ { i } , n _ { i } \}$ 其中: $\rho i$ 为第 $i$ 个同心圆的半径, $\theta _ { i }$ 为区域 $R _ { i }$ 的一条扇形边与水平方向(顺时针旋转)所成夹角， $n _ { i }$ 为落在区域 $R _ { i }$ 中的点的个数。这样一幅图像 $I$ 就可以描述成 $R$ 个三元组所构成的直方图 $H _ { \circ }$ CPDH具体描述细节参考文献[7].

![](images/bb94c774e28c9c2f48fcf22838e9647cc8cb68d4305faa2d9068d554d4dfede6.jpg)  
图2极坐标下轮廓点分布

# 1.2IDSC形状描述符

首先利用二阶梯度Canny算子提取目标形状的部分轮廓点集 $Q = \{ q _ { 1 } , q _ { 2 } , q _ { 3 } , . . . , q _ { n } \} , q \in I R ^ { 2 }$ ， $n$ 表示采样点数量。对于任意采样点都可以用其余 $^ { n - 1 }$ 个点和该点构造的向量表示。因此整个目标形状就可以用 $n ^ { * } n { - } 1$ 个向量表示。这些向量包含了轮廓点在整个形状中的距离信息和方向信息。方向参数表示把一个圆周等分份数；距离参数是等分半径数。然后用形状统计直方图表示得到的向量集。

内距离定义为形状A内部连接两点 $m , n$ 的最短路径长度，用 $d \big ( \mathrm { m , n ; A } \big )$ 来表示。最短路径一般存在两种情况：若点 $m$ ，n之间的线段完全位于目标形状之间，则内距离等价于欧氏距离；否则应用Floyed-Warshall最短路径算法来计算每一对采样点之间的距离。结合上述部分，可得到目标形状的IDSC。如图3所示，图3.(a)表示提取的蝙蝠形状轮廓并标记了4个轮廓点，图3.(b)分别表示相应的内距离形状上下文特征。

![](images/d857872d4027ffa4fa836643ba60e2a2a85dc0c468b40186d59e04a7817bf1e2.jpg)

图3形状轮廓和统计直方图

# 2 EMD算法

相似性度量是直接影响检索效果的重要环节，人们一直致力于研究如何用数值来有效地表示图像在特征上的相似程度。Rubner等人[13]提出的EMD算法广泛应用于线性规划中的运输问题。直觉地，本文将两幅进行比较的图像看做是图像特征在空域的两个不同分布，一个看做是空间散布的土堆，另一个看做是土坑，EMD算法就是找一个最佳路径来完成土堆的运输问题，在该最佳路径下所做的功可看做是两个分布间的距离。该算法可详细地形式化如下的线性规划问题：

设空间S分布着 $\mathbf { m }$ 个土堆 $P = \{ ( p _ { 1 } , w _ { p 1 } ) , \cdots , ( p _ { m } , w _ { p m } ) \}$ ，第pi个土堆的质量为 $w _ { p _ { i } }$ ，同时分布着 $\mathfrak { n }$ 个土坑$Q = \{ ( q _ { 1 } , w _ { q _ { 1 } } ) , \cdots , ( q _ { n } , w _ { q _ { n } } ) \}$ ，第 $\mathbf { q } _ { \mathrm { i } }$ 个土坑能容纳土的质量为 $w _ { q _ { i } }$ ，$D = [ d _ { i j } ^ { \phantom { } } ]$ 表示地面距离矩阵。需要找到最佳运输方案 $F = [ f _ { i j } ]$ ，这里fij表示从土堆 $\mathfrak { p } \mathrm { i }$ 运输到土坑 $\mathbf { q } \mathrm { i }$ 的土的质量。运土的最小功可定义为

$$
W o r k \left( P , Q , F \right) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } d _ { i j } f _ { i j }
$$

该式需满足以下四个限制条件：

$$
f _ { i j } > 0 1 \le i \le m , 1 \le j \le n
$$

$$
\sum _ { j = 1 } ^ { n } f _ { i j } \leq w _ { p _ { i } } \qquad 1 \leq i \leq m
$$

$$
\sum _ { i = 1 } ^ { n } f _ { i j } \leq w _ { q _ { i } } \qquad 1 \leq j \leq n
$$

$$
\sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } f _ { i j } = \operatorname* { m i n } \Biggl ( \sum _ { i = 1 } ^ { m } w _ { p _ { i } } , \sum _ { j = 1 } ^ { n } w _ { q _ { i } } \Biggr )
$$

条件1限定只能把土从土堆集P运倒土坑集Q，反之不然；条件2限定土堆 $\mathfrak { p } \mathrm { i }$ 最多所能运输的图的质量不超过 $w _ { p _ { i } }$ ；条件3限定土坑 ${ \mathfrak { q } } { \mathfrak { j } }$ 最多所能承载的土地质量不超过 $w _ { q _ { i } }$ ;条件4表示尽可能多的运输土。只要该运输问题得到解决，就找到了最佳运输方案F，EMD 距离可采用最终归一化的形式：

$$
E M D \big ( P , Q \big ) = \frac { \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } d _ { i j } f _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } f _ { i j } }
$$

# 3 EMD-L1度量

CPDH采用原始EMD度量轮廓特征直方图相似度，但它存在计算复杂度高，对微小形变鲁棒性较弱的缺点。IDSC采用卡方检验计算形状直方图的相似度得到代价矩阵，再用动态规划算法(dynamic programming algorithm，DP)得出代价矩阵中最优匹配。虽然上述两种度量算法匹配精度高但是计算时间太长不利于工程应用。针对这一不足，本文采用EMD-Li作为度量准则。EMD- $\cdot \mathrm { L } _ { 1 }$ 算法核心在于用 $\mathrm { L } _ { 1 }$ 范数（曼哈顿距离）替代了原始EMD 的地面距离。 $\mathrm { L } _ { 1 }$ 范数（曼哈顿距离）是指向量中各个元素的绝对值之和，因此新定义的地面距离如式(7)所示。通过利用 $\mathrm { L } _ { 1 }$ 范数取代原始地面距离的计算方式降低了目标函数的变量个数，加快了直方图的匹配速度，由于 $\mathrm { L } _ { 1 }$ 范数对噪声，异常值的鲁棒性优于 $\mathbf { L } _ { 2 }$ 范数所以选取 $\mathrm { L } _ { 1 }$ 范数。

$$
{ d _ { i , j ; k , l } } = \left| i - k \right| + \left| j - l \right|
$$

其中：（i,j）;(k,I)分别是目标形状对应轮廓特征直方图下的块。

给定两个由CPDH生成的 $\mathbf { m }$ 行 $\mathfrak { n }$ 列二维直方图 $\mathrm { ~ \bf ~ P ~ }$ ，Q，分别有N个块， $N = m \times n$ ，作如下的定义：

a)定义直方图块的索引集：

$\eta = \{ ( i , j ) : 1 \leq i \leq m , 1 \leq j \leq n \}$ ,(ij)表示直方图中的一个块

b)定义块之间流的集合： $\nu = \{ ( i , j , k , l ) : ( i , j ) \in \upsilon , ( { \bf k } , { \bf l } ) \in \nu \}$

c)由a）可得，直方图 $\mathrm { ~ \bf ~ P ~ }$ ，Q的定义： $P = \{ p _ { i j } : ( i , j ) \in \eta \}$ ，$Q = \{ q _ { i j } : ( i , j ) \in \eta \}$

根据上述三个定义，重新定义直方图 $\mathrm { ~ \bf ~ P ~ }$ 和Q间的EMD ：

$$
E M D \big ( P , Q \big ) = \operatorname* { m i n } _ { { F = \{ f _ { i , j ; k , l } : ( i , j , k , l ) \in \nu \} } } \sum _ { \eta } f _ { i , j ; k , l } d _ { i , j ; k , l }
$$

$$
\mathrm { s . t . } \{ \sum _ { ( i , j ) \in \eta } f _ { i , j ; k , l } = 0  \quad \forall \bigl ( i , j , k , l \bigr ) \in \nu 
$$

F表示直方图P到Q的流； $f _ { i , j ; k , l }$ 表示块（i,j）到 $( \mathbf { k } , \mathbf { l } )$ 的流；地面距离 $d _ { i , j ; k , l }$ 用式(7)计算即可。

为了进一步优化目标函数，将 $\nu$ 划分成三个子集$\nu { = } \nu _ { 0 } \cup \nu _ { 1 } \cup \nu _ { 2 }$ ，每一个子集对应一种情形下的流：

$\nu _ { \scriptscriptstyle 0 } = \{ \left( i , j , i , j \right) : \left( i , j \right) \in \nu \}$ 表示在直方图同一位置块的流,命

名为s-flows

$\nu _ { { \scriptscriptstyle 1 } } = \left\{ \left( i , j , k , l \right) : \left( i , j , k , l \right) \in \nu , d _ { i , j , k , l } = 1 \right\}$ 表示直方图中相邻两

个块的流,命名为 $\mathfrak { n }$ -flows

$\nu _ { { _ 2 } } = \left\{ \left( i , j , k , l \right) : \left( i , j , k , l \right) \in \nu , d _ { i , j , k , 1 } > 1 \right\}$ 是除上述两种情况剩

下的流,命名为f-flows

根据以上定义，可以将f-flow划分成若干个n-flow。这是因为在整数直方图块上 $\mathrm { L } _ { 1 }$ 距离可以形成一个最短路径系统。例如，给定一个 f-flow $f _ { i , j ; k , l } , i \le k , j \le l$ ， $\mathrm { L } _ { 1 }$ 地面距离可以有如下分解：

$$
d _ { i , j ; k , l } = d _ { i , { \mathrm { j } } ; i , l } + d _ { i , { \mathrm { l } } ; k , { \mathrm { l } } } = \sum _ { j \leq x < l } d _ { i , x ; i , x + 1 } + \sum _ { i \leq y < k } d _ { { \mathrm { y } } , { \mathrm { l } } ; y + 1 , l }
$$

综上所述，目标形状 $\mathrm { ~ \bf ~ P ~ }$ 与查询形状Q对应CPDH下的轮廓直方图EMD- $\mathrm { . L } _ { 1 }$ 距离为：

$$
E M D - L _ { 1 } \big ( P , Q \big ) = \operatorname* { m i n } _ { \substack { G = \{ g _ { i , j ; k , l } : ( i , j , k , l ) \in \nu _ { 1 } \} } } \sum _ { \nu _ { 1 } } g _ { i , j ; k , l }
$$

$$
s . t . \left\{ \begin{array} { c c } { g _ { i , j ; k , l } \geq 0 } & { \forall \left( i , j , k , l \right) \in \nu _ { 1 } } \\ { \sum k , l : \left( i , j , k , l \right) \in \nu _ { 1 } \left( g _ { i , j ; k , l } - g _ { k , l ; i , j } \right) = b _ { i j } } & { \forall \left( i , j \right) \in \eta } \end{array} \right.
$$

其中： $b _ { i j } = p _ { i j } - q _ { i j }$ 表示两个直方图在块(i,j)的轮廓点数差异。目标函数11和约束条件12与原始EMD相比，变量数与约束条件减少。另外根据 $\mathrm { L } _ { 1 }$ 距离的特性也不用再计算块与块之间的地面距离，很大程度降低了算法的计算复杂度。

# 4 算法时间复杂度分析

改进算法中的优化问题将目标函数的变量数由O(N)减到O(N),N表示外接圆划分的块数。EMD-L1利用L1范数计算地面距离，大大地提升了直方图匹配速度。原始的 EMD 算法复杂度为O(NlogN),而优化后的算法复杂度为O(N),通过实验验证改进算法的形状匹配速度得到了有效提高。

# 5 实验结果与分析

为验证本文所提方法的有效性，在不同数据集下进行实验分析。实验过程中，分别将数据集中每一样本视为查询形状，余下样本视为目标形状，将得到的形状距离结果按照升序排列。如果匹配结果显示查询形状与目标形状属于相同类别,则匹配结果正确;否则,匹配错误。

# 5.1Kimia-25与Kimia-99形状数据集

Kimia-25数据库[14]中包含6个类别共25个样本，样本示例如图4(a)所示。Kimia-99数据库[15]包含9个类别各11个样本，样本实例如图4.(b)所示。

在本文的所有实验中，为确保与其他方法比较时的公平性，设置各形状轮廓的采样点数目均为 $\mathrm { \Delta N } = 1 0 0$ 。在Kimia-25数据库和Kimia-99数据库的测试过程中，目标形状最小外接圆圆周12 等分，圆心角半径5等分，即 $5 \mathrm { p } { \times } 1 2 6 { = } 6 0$ 个区域块。

在Kimia-25数据库进行仿真实验的结果见表1，表1列出了不同方法在Kimia-25数据集下的检索结果，给出了与查询形状最相似的1\~3组目标形状中分类正确的具体数目。从表1的结果中可以看出，本文所改进的IDSC与CPDH效果略优于经典方法SC，主要原因在于SC在构建每个轮廓点的局部直方图时，若半径过短，则局部直方图不具备良好的鉴别能力；若半径过长，则局部直方图会包含较多的噪声。但是所提算法检索效果弱于 $\mathrm { C P D H + E M D }$ ，与 $\mathrm { I D S C + D P }$ 。经分析Li距离替代原始EMD地面距离时忽略了轮廓点之间的空间信息，导致检索效果略有下降。

在Kimia-99数据库进行仿真实验的结果见表2，表2分别给出了与查询形状最相似的1\~10 组目标形状分类正确的具体数目及合计结果。从表中可以发现，本文算法检索性能优于SC，改进的CPDH算法弱于 $\mathrm { C P D H + E M D }$ 。但是检索到数据集第8类至第10类时，本文算法比另外两种算法更加稳定，返回有效的形状数目更多。原因在于采取 $\mathrm { L } _ { 1 }$ 距离对微小形变的鲁棒性更好。另外改进后的IDSC算法检索性能明显优于SC，CPDH+EMD。证明EMD-L1能很好的保持IDSC对形状的描述能力。

表1Kimia-25数据库在不同方法下的检索结果比较  

<html><body><table><tr><td>方法</td><td>1st</td><td>2nd</td><td>3rd</td></tr><tr><td>SC[9]</td><td>23</td><td>21</td><td>20</td></tr><tr><td>CPDH+EMD[11]</td><td>25</td><td>24</td><td>22</td></tr><tr><td>Sharvit et. al[14]</td><td>23</td><td>21</td><td>20</td></tr><tr><td>IDSC+Dp[12]</td><td>25</td><td>24</td><td>25</td></tr><tr><td>CPDH+EMD-L1</td><td>25</td><td>22</td><td>20</td></tr><tr><td>IDSC+EMD-L1</td><td>25</td><td>24</td><td>24</td></tr></table></body></html>

![](images/4fa6e6ee5864d6d41c4ed320acc635984622f5a64e9bb4e3ab64b2d0673ff2f8.jpg)  
图4两组形状数据集剪影

表2Kimia-99 数据库在不同方法下的检索结果比较  

<html><body><table><tr><td>方法</td><td>1st 2nd</td><td></td><td>3rd</td><td>4th</td><td>5th</td><td>6th</td><td>7th</td><td>8th</td><td>9th</td><td>10th</td><td>全部</td></tr><tr><td>SC[9]</td><td>97</td><td>91</td><td>88</td><td>85</td><td>84</td><td>77</td><td>75</td><td>66</td><td>56</td><td>37</td><td>756</td></tr><tr><td>CPDH+EMD[11]</td><td>96</td><td>94</td><td>94</td><td>87</td><td>88</td><td>82</td><td>80</td><td>70</td><td>65</td><td>22</td><td>808</td></tr><tr><td>IDSC+EMD-L1</td><td>99</td><td>99</td><td>98</td><td>98</td><td>96</td><td>90</td><td>85</td><td>82</td><td>76</td><td>67</td><td>893</td></tr><tr><td>CPDH+EMD-L1</td><td>99</td><td>91</td><td>85</td><td>85</td><td>79</td><td>80</td><td>73</td><td>78</td><td>68</td><td>53</td><td>791</td></tr></table></body></html>

# 5.2Articulated 形状数据集

Articulated数据集[10]包含8个类，总共40 张图片。每个类的5张图片都有不同程度的形变，如图6所示。该数据集被用于测试形状的铰接，这是形变中一个较为特殊的情况。同时也可以检验算法对形变的鲁棒性。该实验采用交叉验证，分别用卡方检验 $\chi ^ { 2 }$ ，EMD-Li度量同一形状描述子生成的直方图之间的相似度。将返回与查询形状最相似的1\~4组目标形状且分类正确的具体数目作为评价算法检索性能的标准。分析表3的实验数据，第一组与第二组实验结果相比，说明 EMD $\cdot \mathrm { L } _ { 1 }$ 比 $\chi ^ { 2 }$ 在形变较明显的数据集下的检索效果更好，鲁棒性更加；分析第二组与第三组的实验结果，IDSC对形状的鉴别能力优于SC，分析第一组和第五组实验，可以看出CPDH对形状形变的描述能力更优于SC因为IDSC对形状的描述中包含了轮廓点的相对位置关系且SC算法抗噪性能差。

# 5.3 MPEG-7数据集

根据本文提出的算法，选用MPEG- $\cdot 7 ^ { [ 1 6 ] }$ 数据集进行仿真实验，该数据集共有1400个形状剪影，均分为70个类别，每个类别中共有20个样本。

# 5.3.1CPDH+EMD与CPDH $\cdot +$ EMD-L1的比较

表4给出了CPDH+EMD,CPDH+EMD-Li算法的比较，本次实验在MPEG-7SetB的子图像库中进行，该子库包括216幅形状图像，分为18个类别，每类12幅。从表4的实验结果可以看出，虽然CPDH+EMD返回的有效形状总数多于CPDH+EMD-Li，但是分析第8类到第11类的检索结果，尤其是第10类至第11类EMD返回的形状数量下降较快而EMD-$\mathrm { L } _ { 1 }$ 则平稳减少且第11类的返回数目远多于原始算法，说明基于EMD-Li的CPDH在类数较多的情况下对形变的鲁棒性更优，但是由于L范数的特性忽略了轮廓点之间的空间信息导致总体效果不如原算法。

![](images/457e77d8e308e00311d5834a39bf1fa252a8d9b94a27ab149ab7221756e8c9a0.jpg)  
图5Articulated 形状数据集

表3Articulated形状数据集在不同方法下的检索结果比较  

<html><body><table><tr><td>方法</td><td>Top1</td><td>Top2</td><td>Top3</td><td>Top4</td></tr><tr><td>SC+EMD-L1</td><td>36/40</td><td>19/40</td><td>10/40</td><td>8/40</td></tr><tr><td>SC+x2[9]</td><td>20/40</td><td>10/40</td><td>11/40</td><td>5/40</td></tr><tr><td>IDSC+x²</td><td>40/40</td><td>34/40</td><td>35/40</td><td>27/40</td></tr><tr><td>IDSC+EMD-L1</td><td>39/40</td><td>3940</td><td>34/40</td><td>32/40</td></tr><tr><td>CPDH+EMD-Li</td><td>40/40</td><td>12/40</td><td>14/40</td><td>10/40</td></tr></table></body></html>

表4MPEG-7子库中的检索结果比较  
表6IDSC+EMD-L1旋转不变性测试结果  

<html><body><table><tr><td>方法</td><td>1st</td><td>2nd</td><td>3rd</td><td>4th</td><td>5th</td><td>6th</td><td>7th</td><td>8th</td><td>9th</td><td>10th</td><td>11th</td><td>总数</td></tr><tr><td>CPDH+EMD[1]</td><td>214</td><td>215</td><td>209</td><td>204</td><td>200</td><td>193</td><td>187</td><td>180</td><td>168</td><td>146</td><td>114</td><td>2030</td></tr><tr><td>CPDH+EMD-L1</td><td>216</td><td>206</td><td>199</td><td>185</td><td>186</td><td>178</td><td>176</td><td>167</td><td>154</td><td>144</td><td>135</td><td>1946</td></tr></table></body></html>

# 5.3.2IDSC $^ +$ EMD-L1与其他方法的比较

本实验采用MPEG-7数据集并使用Bull-eye[17]方法确定检索精度：每个待检索形状都要与数据集中所有形状比较，取实验结果中与每个待检索形状最相似的40个形状，统计这40个形状中与待检索形状同类别的数目，并计算对应的查全率。从表5可以看出EMD-L1提升了IDSC的检索性能且超过了大多数形状检索算法。证明了本文算法的有效性。

表5各算法检索性能比较  

<html><body><table><tr><td>方法</td><td>检索精度(Bullseye)</td></tr><tr><td>CSS[18]</td><td>75.44%</td></tr><tr><td>Visual Parts[17]</td><td>76.45%</td></tr><tr><td>SC+TPS(x2)[9]</td><td>76.51%</td></tr><tr><td>Curve Edit[19]</td><td>78.17%</td></tr><tr><td>Distance Set[20]</td><td>78.38%</td></tr><tr><td>Gen.Model[21]</td><td>80.03%</td></tr><tr><td>IDSC(x²)</td><td>85.40%</td></tr><tr><td>IDSC+EMD-L1</td><td>86.56%</td></tr></table></body></html>

# 6 旋转不变性测试

为了验证IDSC+EMD-L1的旋转不变性。本次实验从MPEG-7数据集中随机选取10幅图像作为基准图像，然后将这每一幅图像幅分别沿着顺时针和逆时针方向依次旋转 $5 ^ { \circ }$ ? $1 5 ^ { \circ }$ ，$3 0 ^ { \circ }$ ： $. 4 5 ^ { \circ }$ ， $6 0 ^ { \circ }$ ? $. 7 5 ^ { \circ }$ 得到12幅新的图像。包括10幅基准图像，整个旋转数据集有130幅图像。表6列出了将10基准幅图像作为查询图像的检索结果，若有检索错误的图像将其表格背景颜色设置为灰色。从表6可以看出检索返回结果只有两幅图像检索错误，其余118图像检索正确，说明改进后的算法仍然保持良好的旋转不变性。

![](images/eab81052f302c47527a6c587e23f1025c9a7e86bc24a5515af04ebaab15298fa.jpg)

# 7算法运算速度测试

本实验采用两组算法进行对比。第一组实验：CPDH+EMD-L1，CPDH+EMD，SC；第二组实验：IDSC+DP，IDSC+EMD-L1，SC。采用的数据集是 MNIST[22]手写数字图像库的训练图像库，共有10000 幅图像，包含0到9共10种数字。从中随机选取1000 幅进行实验(数字形状复杂度从低到高，由此计算出的识别速度更具有一般性)。实验结果如图6、7所示。实验证明改进后算法的运行时间显著优于原算法与SC，更适合于工程应用。

![](images/f4ada9ced5a9cb4ec0f64677cf8621d5878f487861510b3f02edd134dbc8ef3b.jpg)  
图6第一组算法时间测试

![](images/2ef8c642247ea657ae076c813bc616d7921a59fe7ccf6efcf5c3b064113a173a.jpg)  
图7第二组算法时间测试

# 8 结束语

本文基于CPDH和IDSC分别用EMD-Li替换EMD和DP算法作为轮廓点直方图的度量准则，其主要优点在于L范数（曼哈顿距离）对于形变有较好的鲁棒性，而且通过减少目标函数的变量数降低了算法的计算复杂度。从实验结果来看，所改进算法有良好的检索能力，加快了形状匹配速度。由于最近几年深度学习大热，以神经网络为基础做3D形状检索将是作者下一步研究的方向。

# 参考文献：

[1]Zhang D,Lu G.Review of shape representation and description techniques

[J]. Pattern Recognition,2004,37(1):1-19.   
[2] Yang M, Kpalma K,Ronsin J. A survey of shape feature extraction techniques [J].DOI: 10.5772//6237,2008.   
[3]Bai S,Bai X, Zhou Z,et al. Gift: Areal-time and scalable 3d shape search engine [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.2016: 5023-5032.   
[4]Zhu Z, Wang X,Bai S,etal. Deep learning representation using autoencoder for 3D shape retrieval[J]. Neurocomputing,2016,204: 41-50.   
[5]周瑜，刘俊涛，白翔．形状匹配方法研究与展望[J]．自动化学报,2012, 38 (6): 889-910.   
[6] Alajlan N,EI Rube,Kamelb M S,Freeman G H. Shape retrieval using triangle-area representation and dynamic space warping，[J] Pattern Recognition 2007 40(7) 1911-1920.   
[7]Adamek T, O'Connor N E.A multiscale representation method for nonrigid shapes with a single closed contour[J]. IEEE Trans on Circuits and Systems for Video Technology,2004,14(5): 742-753.   
[8]Hong B W,Soatto S.Shape Matching using Multiscale Integral Invariants [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2015,37(1): 151-160.   
[9]Belongie S,Malik J,Puzicha J. Shape matching and object recognition using shapecontexts [J]. IEEE Trans on Pattern Analysis and Machine Intelligence, 2002,24 (4): 509-522.   
[10]Ling H,Jacobs DW.Shape classification using the inner-distance[J].IEEE Trans on Pattern Analysis and Machine Intelligence,2007,29 (2): 286-99.   
[11] Shu Xin, Wu Xiaojun. A novel contour descriptor for 2D shape matching and its application to image retrieval[J]. Image and Vision Computing,2011, 29 (4): 286-294.   
[12] Ling,Haibin,and Kazunori Okada.An efficient earth mover's distance algorithm for robust histogram comparison.IEEE Trans on Pattern Analysis and Machine Intellgence,2007,29 (5): 840-853.   
[13] Yossi R,GuibasL J,Tomasi C.The earth mover's distance multidimensional scaling and color-based image retrieval [C]// Proc.of ARPA Image Understanding Workshop.1997: 661-668   
[14] Sharvit D,Chan J, Tek H,et al. Symmetry-based indexingof image databases [C]// Proc of IEEE Workshop on Content-Based Access of Image and Video Libraries.1998: 56-62.   
[15] Sebastian TB,KleinPN, KimiaBB.Recognition of shapes by editing their shock graphs [J]. IEEE Trans on Pattern Analysis and Machine Intelligence, 2004, 26 (5): 550-571.   
[16]Atalla E,Siy P.Robust shape similarity retrieval based on contour segmentation polygonal multiresolution and elastic matching [J].Pattern Recognition,2005,38 (12): 2229-2241.   
[17] LateckiLJ,Lakamper R,Eckhardt T.Shape descriptors fornon-rigid shapes with a single closed contour [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.20oo: 424-429   
[18]MokhtarianF,Abbasi S,Kittler J.Robust and efficient shape indexing through curvature scale space $[ \mathrm { C } ] / \AA$ Proc of British Machine and Vision Conference.1996,96:53-62   
[19] Sebastian TB,Klein PN,Kimia BB.On aligning curves [J].IEEE Trans on pattern analysis and machine intelligence,20o3,25(1): 116-125.   
[20] Grigorescu C,Petkov N.Distance sets for shape filters and shape recognition [J].IEEE Trans on Image Processing,2003,12(10):1274-1286.   
[21] Tu Zhuowen, Yuille AL. Shape matching and recognition-using generative models and informative features [C]// Proc of European Conference on Computer Vision. Berlin: Springer,2004:195-209.   
[22]Deng Li.The MNIST database of handwrittendigit images for machine learning research [best of the web] [J].IEEE Signal Processing Magazine, 2012,29 (6): 141-142