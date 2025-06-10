# 基于椭球拟合的人体一服装碰撞检测方法

龚随，侯进，钟李涛，张娟，唐源皓(西南交通大学 信息科学与技术学院，成都 611756)

摘要：为了实现服装仿真中服装与人体的快速碰撞检测，提出了一种基于椭球拟合的碰撞检测方法。首先，以测地距离等值线为基础数据，结合人体尺寸与身高的线性关系和人体结构特征提取模型特征点，实现模型语义分割；然后，以径向距离的平均值作为椭球与模型之间的拟合误差，采用剪枝优化的二分K均值聚类算法逐步增加聚类中心个数，实现对人体模型的快速聚类并生成一系列逼近模型的最小体积包围椭球；最后，使用生成的包围椭球代替人体模型与布料进行碰撞检测。实验结果表明，该方法不仅能快速实现对三维人体模型的高度拟合，而且有效提高了碰撞检测的计算效率。

关键词：碰撞检测；测地距离；模型分割；最小体积包围椭球；二分K均值聚类 中图分类号：TP391.4 doi: 10.3969/j.issn.1001-3695.2017.08.0894

# Cloth-body collision detection method based on ellipsoid fitting

Gong Sui, Hou Jin†, Zhong Litao, Zhang Juan, Tang Yuanhao (School ofInformation Science&Technology,Southwest Jiaotong University,Chengdu 611756,China)

Abstract:Torealizetherapidcollsiondetectionbetweenclothandhumanbodyinclothsimulation,acolisiondetectionmethod based onelipsoid fiting is proposed.Firstly,thegeometricdistance isoline wasusedas thebasicdata.Andthe modelfeature points was extracted bycombining thelinearrelationshipbetween bodysizeandheight withthe structuralfeatures ofthe human body,whichrealizedthesemanticsegmentationofthe model.Secondly,teaverageoftheradial distance wasusedtoepresent thefiting errorbetweenan ellpsoidand the model.And thenumberofclustercenters was graduallyincreased by bisecting Kmeans clustering algorithm based on pruning optimization.Itcouldrealize therapid clustering of human model and generate a seriesof minimum ellpsoids.Finaly,cloth grid points was detected withthe elipsoids insteadof the model.Simulation experimentsshow that this method notonlyrealizes the fast fiting of the humanmodel,butalso efectively improves the computational efficiency of collision detection.

KeyWords:colisiondetection;geometric distance； model segmentation； minimum volume elipsoid;bisecting K-meansclustering

# 0 引言

在虚拟服装仿真系统中，碰撞检测是决定仿真中视觉效果逼真度的关键因素，同时也是最为耗时的部分，如何快速检测出服装与人体模型之间的碰撞并作出响应是影响试衣实时性的一个关键问题。为此，大量研究人员进行了深入研究，并取得了较好的研究成果[1-3]。

目前已经形成了两类比较经典的算法：层次包围盒法[4-8]和空间分解法。其中前者被广泛应用于复杂环境中空间几何模型之间的碰撞检测。Salazar等人[4]通过使用轴向包围盒(axisalignedboundingbox,AABB)层次结构和GPU多线程实现了对高分辨率布料的动态实时仿真。Du等人[5]同样采用AABB包围盒处理多层服装间的穿透，但当服装粒度过大时依然存在渗透问题。针对AABB包围盒紧密性差的问题，Shen 等人[使用有向包围盒（orientedboundingbox,OBB）和包围球来构成双重包围盒层次结构，首先通过包围球剔除不会相交的对象，再通过紧密性较好的OBB包围盒进行精确碰撞计算，该方法综合了OBB的紧密性和包围球的简易性，相比单一的OBB算法更高效，但这种方法并不适用于近距离接触物体之间的碰撞。Guo等人[7]则将AABB包围盒和离散方向包围盒(Discreteorientationpoly-topes,K-DOP)混合用于加速虚拟手术中器官形变产生的碰撞检测，在不影响精度的前提下提高了碰撞检测效率。唐等人[8利用多核CPU的并行性，结合SIMD指令进一步优化k-DOP模型，有效提升了多核体系架构下柔性织物的碰撞检测效率，但在核心数目较大时，会造成SIMD指令获得的加速比下降等问题。Zhang等人[9通过使用多核CPU和多核GPU进行并行碰撞检测，该方法简化了计算的工作量。Du等人[10提出一种针对分布式存储GPU 集群的并行连续碰撞检测加速算法。Ye等人[1采用基于离散交叉检测的方法处理模型之间的渗透现象，对于复杂模型表面的变形，该方法相比于传统连续碰撞检测方法具有较好地性能，但该方法并不能有效处理表面相交的模型。

对于服装-人体之间的冲突检测而言，服装与人体之间较为紧密，其运动复杂且极易变形，采用层次包围盒的方式在运动过程中需要实时更新层次结构，计算带来的时间消耗成为此类方法效率的瓶颈之一。鉴于球体包围盒的方向无关性和碰撞响应的简易性，Wang 等人[12]提出一种通过球体近似固体模型的近似方法。王等人[13提出一种三维模型球体逼近方法，在三维模型体素化的基础上构建内部球逼近，但该方法构建的内部球数量较多，不适用于实时性较高的碰撞检测。Li等人[14]基于人体着装时服装质点与相连三角面片的关系，提出一种相干碰撞检测方法，其性能相比于传统层次包围盒方法提升两倍多。

与此同时，针对人体网格模型缺少足够语义信息及平面包围体紧密性差、层次结构复杂的问题。杜等人[15]采用SDF进行高斯混合模型聚类分割。王等人[16提出一种基于凹凸型号的最小值边界检测的三角网格模型分割算法，该方法有较高的鲁棒性，但在不同场合下需人工适当调整阈值。Liu 等人[17使用椭球体作为基元采用自顶向下的方式对给定模型构建层次包围盒，该方法能有效逼近但计算成本较大。Meng 等人[18]根据人体骨骼结构对人体模型进行初始化分，之后针对初始化分的部位实现椭球体拟合并细分，但该方法依赖于骨骼结构。唐等人[19]基于改进的K均值聚类算法构建自适应椭球包围盒，然后根据表面误差分为两类分别进行碰撞响应，该方法由于反复回溯，计算较为耗时。本文方法基于椭球体对曲面物体良好的表面拟合特性，在模型语义分割的基础上进行椭球体初始拟合；针对躯干和四肢采用不同的初始聚类中心和 $k$ 值，并结合剪枝优化的二分K-均值聚类算法实现人体模型的快速椭球拟合及布料碰撞检测，得到了较好的仿真结果。

# 1 算法框架

本文算法分为预处理和动态模拟两个阶段，在预处理阶段，提取模型特征点，采用测地距离算法实现复杂模型的语义分割。动态模拟阶段主要分为模型拟合和碰撞响应两个方面，首先对分割好的模型数据采用最小体积包围椭球进行初始拟合，然后针对拟合误差较大的椭球体进行细分优化，最后使用优化后的椭球体代替原始模型与布料进行碰撞检测处理得到最终的仿真

结果。算法框架如图1所示。

![](images/1b495f6b03e994a7b48832862c3c4d8244b1de96568d36cdf41ef884d856c503.jpg)  
图1算法框架

# 2 模型预处理

由于单一椭球体难以实现对复杂三维模型的有效拟合，通常需要对复杂三维模型进行简化分割，使其分解为一系列具有相对较高拟合度的子区域，从而改善整体拟合的效果。在人体模型中，椭球体对模型四肢具有较好的拟合性，为此，本文基于人体结构特征，以测地距离作为基础数据，结合人体部位尺寸与身高H之间的线性关系，实现快速有效的模型语义分割。

# 2.1特征点提取

本文采用于等人[20]提出的方法自动提取人体模型末端特征点，即四肢末端和头顶5个部位的特征点。此外，由于人体比例具有一定的稳定性，不会随着身高的改变而快速变化，本文对GB/T10000-88《中国成年人人体尺寸》[21]和GB/T13547-92《工作空间人体尺寸》[22]进行研究分析，将人体模型分为末端特征点、中层特征点和内层特征点三类，计算出人体部位尺寸与身高H之间的线性关系，如表1所示。并以此为基础，结合迪科斯彻(Dijkstra)近似测地距离算法快速定位中层特征点（肘点、膝点和颈点)。

表1人体部分尺寸与身高H之间的线性关系  

<html><body><table><tr><td>项目f(H)</td><td>成年男性（18-60岁）</td><td>成年女性(19-60 岁)</td></tr><tr><td>头部长L1</td><td>0.0836H+168.9137</td><td>0.0994H+142.6445</td></tr><tr><td>前臂长L7</td><td>0.5510H-283.1964</td><td>0.5672H-307.5205</td></tr><tr><td>小腿长L4</td><td>0.7447H-257.6398</td><td>0.7134H-207.8311</td></tr><tr><td>腰高 L3</td><td>0.8044H-243.0916</td><td>0.7683H-170.2316</td></tr><tr><td>胸高 L2</td><td>0.9630H-311.3857</td><td>0.9309H-245.0959</td></tr></table></body></html>

由于本文采用的模型沿y轴正方向站立，故只需对所有坐标点按照其 $y$ 坐标值查找出最大值 $y _ { m a x }$ 和最小值 $y _ { m i n }$ ，即可求出人体身高： $H = \left| y _ { m a x } - y _ { m i n } \right|$ 。之后分别以末端特征点为基准点，求解模型上任意一点 $\nu _ { n }$ 与各末端特征点 $p _ { i }$ 之间的测地距离。

$$
G ( x ) = g e o d ( \nu _ { n } , p _ { i } ) , n \in ( 0 , N )
$$

其中： $\nu _ { n }$ 为模型的第 $n$ 个顶点， $p _ { i }$ 为某一末端特征点， $G ( x )$ 为两点之间的测地距离， $N$ 表示模型的总顶点个数。

鉴于人体模型是由不同疏密程度的三角网格构成，所在截面与模型相交时必然与边相交，为了保证计算精度，需要求解截面与三角网格的交点；检测模型上所有三角形，求解$G ( x ) = f ( H )$ 的点， $f ( H )$ 表示人体部分尺寸与身高 $H$ 之间的线性关系。如图2中 $\Delta A B C$ ，设 $G ( A ) > f ( H ) , G ( B ) < f ( H )$ ，根据式（2)可以计算出点 $d _ { \mathrm { { \scriptscriptstyle 1 } } }$ 坐标。同理，点 $d _ { 2 }$ 坐标也可以得到。

$$
d _ { 1 } = \frac { f ( H ) - G ( A ) } { G ( B ) - G ( A ) } ( B - A ) + A
$$

![](images/75b3eaaa5f15e1a4999011a2448adca228646258b06fc8ae4b6acd81758346b1.jpg)  
图2测地距离等值点

通过上面的计算，可以获得肘点、膝点和颈点所在的测地距离等值线。会阴点即为两脚尖特征点之间测地距离长度一半所对应的 $\nu _ { { } _ { 4 } }$ 点，模型的腿长 $L 5$ 则用会阴点到脚尖点的测地距离 $G _ { l e g } ( x )$ 代替，即 $L 5 = G _ { l e g } \left( x \right)$ 。为了准确的划分模型手臂，结合人体模型结构特征，可通过点到直线的距离准确提取，如图3所示， $\nu _ { 3 }$ 为手肘对应测地距离等值面上一点到会阴点的最小欧式距离点； $\nu _ { 2 }$ 为以右脚尖末端特征点为基准点， $f ( H ) = L 3$ 计算的等值线上距离会阴点欧式距离最大值点。依次比较 $\nu _ { 2 }$ 到 $\nu _ { 3 }$ 之间测地线经过的所有顶点中点 $\nu _ { i }$ 到直线 $\nu _ { 2 } \nu _ { 3 }$ 的投影距离 $d _ { i }$ ，则投影距离最大的 $\nu _ { 1 }$ 点即为腋下点， $\nu _ { 1 }$ 到对应指尖特征点的测地距离即为模型手臂长L6=Ghand(x)。

# 2.2模型分割

得到人体语义特征点以后，可以通过测地距离完成三维人体模型的层次分割。为了描述方便，设三维模型所构成的顶点集合为 $S { = } \{ \nu _ { 1 } , \nu _ { 2 } , \cdot \cdot \cdot , \nu _ { i } , \cdot \cdot \cdot , \nu _ { N } \}$ ，其中 $\nu _ { i }$ 为模型第 $i$ 个顶点， $N$ 为三角片总数；模型分割的最终目的是将三维模型所有顶点 $s$ 按照其结构特性进行划分，以手臂分割为例，对于末端特征点 $p _ { i }$ ，以及相邻内层特征点 $\nu ^ { \prime }$ ，可知属于手臂部分的顶点为

$$
g e o d ( \nu _ { i } , p _ { i } ) < g e o d ( \nu ^ { \prime } , p _ { i } )
$$

类似地，在特征点的约束下，可以得到腿部、头部的分割结果，余下顶点构成人体模型的躯干部分，之后依据腰高、胸高和左右腋下点连线中垂面把躯干部位划分为6个部分。最后针对已经分割好的模型四肢，找到相应的中层特征点，形成一个需要二次分割的子部分集合，根据式(3)再次分割为两部分，完成模型的语义分割，由图4可以看出，男士模型和女士模型的分割结果都能能较好的反映人体结构特征。

# 3 椭球体拟合及优化

# 3.1最小体积包围椭球

鉴于AABB包围盒对曲面模型拟合度较低和OBB包围盒碰撞检测相交测试较多的特性，本文采用对弧度表面更具拟合性的椭球体作为模型的基元包围体。采用文献[19]中的方法对

三维模型点集 $s$ 生成一系列最小体积包围椭球（minimumvolume enclosingellipsoids,MVEE)，并在其基础上进行改进，即 $M V E E ( S )$ ，具有如下性质：

$$
M V E E { \left( { \boldsymbol { S } } \right) } = \varepsilon _ { \boldsymbol { Q } , c } = \left\{ \boldsymbol { x } \in \boldsymbol { R } ^ { 3 } : \left( \boldsymbol { x } - \boldsymbol { c } \right) ^ { T } \boldsymbol { Q } \left( \boldsymbol { x } - \boldsymbol { c } \right) \leq 1 \right\}
$$

$$
M V E E ( S ) / d \subseteq c o n \nu ( S ) \subseteq M V E E ( S )
$$

式(4)中： $\varepsilon _ { Q , c }$ 表示椭球，由 $3 \times 3$ 维的正定矩阵 $\boldsymbol { \mathscr { Q } }$ 和中心 $\mathbf { \Psi } _ { c }$ 来表示，其中 $\boldsymbol { \mathrm { \ell } }$ 的特征向量和特征值分别为椭球的半长轴方向和半长轴长度。式(5)中： $M V E E ( S ) / d$ 表示围绕 $M V E E ( S )$ 的中心对其缩放 $1 / d \ , \quad c o n \nu ( S )$ 是 $s$ 的凸包。

经过预处理的人体模型被按照语义分为多个不同的区域$P S { = } \big \{ S _ { 1 } , S _ { 2 } , \cdot \cdot \cdot , S _ { j } , \cdot \cdot \cdot , S _ { k } \big \}$ ，保证了分割结果和人体拓扑结构的一致性。

![](images/72d18907d600d19d3edc4c7cbb5dbcfc565ecb41094188dad75247a98955ed39.jpg)  
图3人体尺寸及会阴点、腋下点示意图

![](images/ae516ec7e3ef3ffcc4e6e3a3751a2097389e157d5ef27c0100e1d084f2cace8d.jpg)  
图4模型语义分割及会阴点、腋下点提取结果

# 3.2 椭球体拟合误差

在对子区域 $\boldsymbol { S } _ { j }$ 的椭球体拟合过程中，为了有效评估生成椭球体的拟合情况，需要对拟合椭球与子区域之间的近似误差进行数值化表示。Simari等人[23]通过使用欧式径向距离、表面法线和曲率的加权平均值作为拟合情况的判断标准，通过控制相对应的权重，实现了较好的拟合效果。Lu等人[24]基于原始模型与椭球体体积之间的误差作为自适应划分三维模型，生成紧密包围的椭球，但计算模型的体积较为复杂，计算消耗太大。由于本文中已经对人体模型语义分割处理，椭球体已具备良好的拟合特性，仅对局部区域椭球进行细化处理，无须准确地求解误差值。如式(6)所示，拟合误差可通过计算人体模型子区域表面点与近似表面之间径向距离的平均值来近似：

$$
E _ { S _ { j } } = \frac { 1 } { K } \sum _ { k = 1 } ^ { K } \left\| \nu _ { i } - \varphi _ { S _ { j } } ( \nu _ { i } ) \right\|
$$

其中： $E _ { s _ { j } }$ 表示模型子区域 $S _ { j }$ 的椭球体拟合误差， $\nu _ { i }$ 为子区域表面点中第 $i$ 个顶点， $K$ 为子区域中包含的顶点总数， $\varphi _ { S _ { j } } ( \nu _ { i } )$ 表示顶点 $\nu _ { i }$ 在椭球体表面上的径向投影点， $\left\| \bullet \right\|$ 表示欧氏距离。

# 3.3 椭球体细分优化

人体模型经过语义分割和初始拟合之后，得到了一系列符合表面特征的椭球，但是在模型躯干部位依然存在拟合误差较大的椭球体，这主要是由于在模型躯干部位细分级数不够所致，可以通过增加全局迭代次数来减小拟合误差，但同时也会造成模型的过度划分而引入大量的拟合椭球体，同时不能保证拟合的精确性，大大降低了碰撞检测的效率。为了实现躯干全局最优化拟合，本文依据腰高、胸高和左右腋下点连线中垂面把躯干部位划分为6个部分，K均值聚类的初始 $k$ 值设为6，相应6个子区域中包含的顶点的均值坐标作为初始质心，然后基于剪枝优化的K均值聚类算法进行二次划分，得到逼近效果较好的椭球体结构。剪枝优化算法思想如下：由于K均值在收敛状态下，所有的点都不会从一个簇转移到另一个簇，质心不再发生改变，即：K均值最明显的收敛过程会发生在算法运行的前期阶段，故在某些情况下为了增加算法的执行效率，可以改变原始算法的结束条件，采用 $k$ 个聚类中心的均值变化量小于特定值为止。

![](images/75a0c1df2f5600c478e45ad038c58632fac080549d8da824262c66c0679578fa.jpg)  
图5聚类终止条件示意图

如图 5所示，假设K均值聚类的初始k 值等于3，νp.\`$\nu _ { p , 2 }$ 和 $\nu _ { p , 3 }$ 分别为子区域中各特征点域的均值坐标， $\nu _ { p , 1 } ^ { \prime } \setminus \nu _ { p , 2 } ^ { \prime }$ 和$\nu _ { p , 3 } ^ { \prime }$ 分别为下一步对应的聚类中心，则聚类的限定条件为

$$
\left\| \overline { { \nu } } _ { p } - \overline { { \nu } } _ { p } ^ { \prime } \right\| \leq \sigma
$$

其中： $\overline { { \nu } } _ { p } \ 、 \ \overline { { \nu } } _ { p } ^ { \prime }$ 分别为 $\Delta \nu _ { p , 1 } \nu _ { p , 2 } \nu _ { p , 3 }$ 和 $\Delta \nu _ { p , 1 } ^ { \prime } \nu _ { p , 2 } ^ { \prime } \nu _ { p , 3 } ^ { \prime }$ 的重心坐标， $\sigma$ 为预设阈值。

为了保证二次划分后的结果和效率，本文采用欧式距离作为聚类准则，在剪枝优化的同时逐个增加 $k$ 值和中心，并判断椭球体的拟合误差 $E _ { s _ { j } } \leq \mu$ 是否满足， $\mu$ 为预设阈值，满足条件则停止细分。

算法的具体步骤如下：

a)判断是否为躯干，若为躯干，则初始化 $k$ 值为6，否则 $k$ 等于1，进行剪枝优化K均值聚类，对聚类形成的所有簇包含顶点计算最小体积包围椭球。

b)找出拟合误差最大的包围椭球，使用最长轴的两个端点作为新的中心点将包围椭球对应的点集进行划分，同时摒弃该点集的原有中心点， $k$ 值增加1。

c)根据新的 $k$ 值和新的中心点对子区域中所有点进行剪枝优化K-均值聚类。

d)对聚类生成的 $\mathbf { k }$ 个点集重新计算得到新的最小体积包围椭球。

e)比较所有椭球包围盒的拟合误差 $E _ { P _ { j } }$ 与预设域值 $\mu$ 的大小，若 $E _ { s _ { j } } > \mu$ 则转到b)，反之停止细分。

在上述过程中，为了使拟合误差 $E _ { s _ { j } }$ 收敛，在聚类过程中对点进行重新归类时需添加限定条件：

$$
E _ { s _ { i } } > E _ { s _ { j } }
$$

其中： $E _ { s _ { i } }$ 、 $E _ { s _ { j } }$ 分别为椭球 $i ,$ （20 $j ( i \neq j )$ 的拟合误差。椭球 $i$ 为该点当前所在椭球，椭球 $j$ 为其他的椭球包围盒。

# 4 碰撞检测与处理

服装布料作为一种高度可变形体，具有轻柔灵活的材质特性，并紧密覆盖在人体模型表面，因此与模型的碰撞需要精准地检测才能得到真实的效果。另一方面，考虑到服装类型的不同，在人体模型的不同部位所需的精准程度定然也不一样。因此，为了提高碰撞检测的效率，保证计算速度和视觉效果，本文采用双重拟合误差标准，针对模型的躯干和四肢采用不同的拟合误差，即设置不同的阈值 $\mu$ 。基于以上方法，人体模型被划分为一系列高度拟合的椭球体，使用这些椭球体取代原始模型与服装进行碰撞，能够有效提高碰撞检测的效率，同时也能保证仿真的逼真度。

每隔一段时间间隔检测碰撞是否发生，一旦检测到碰撞，则改变相应质点的速度和位置来避免穿透。对于服装模型上的一点 $\nu$ 带入式(9)计算 $\zeta$ ，式中 $\boldsymbol { \mathscr { Q } }$ 为椭球的正定矩阵， $\mathbf { \Psi } _ { c }$ 为椭球中心，当 $\zeta > 1$ 表示没有碰撞发生， $\zeta \leq 1$ 表示发生碰撞，点 $p$ 处于椭球内部，需要将其移动至距离顶点当前位置最近距离的椭球体表面，通常比较简单的处理方法是直接沿着椭球体中心和顶点当前位置连线移动至椭球体表面。

$$
\zeta = \left( x - c \right) ^ { T } Q \left( x - c \right)
$$

但上面的方法只针对一个椭球体包围盒成立，当处理多个相交椭球体的碰撞检测时，相应顶点可能被移动到错误位置。如图6a所示，当服装模型上一点 $p _ { 0 }$ 与两相交椭球进行碰撞检测响应时发生三种错误情况：

情况1顶点从 $p _ { \mathrm { 0 } }$ 到 $p _ { 1 }$ 时， $p _ { 1 }$ 处于多个椭球相交处，由于每个椭球都检测到碰撞响应，不同的响应顺序将导致不同的响应结果，易造成系统不稳定。

情况2顶点从 $p _ { \mathrm { 0 } }$ 到 $p _ { 2 }$ 时， $p _ { 2 }$ 被移动到椭球 $O _ { 1 }$ 的表面，但是仍然处于椭球 $O _ { 0 }$ 的内部，于是该点又被移动到椭球 $O _ { 0 }$ 的表面，然而因为 $O _ { 0 }$ 部分存在于 $O _ { 1 }$ 内部，最后该点依然处于椭球 $O _ { 1 }$ 内部。

情况3顶点从 $p _ { \mathrm { 0 } }$ 到 $p _ { 3 }$ 时，顶点被移动到椭球错误的一侧。

![](images/a3c21d5475a8fdfd9a9c231be2c58309a6539e0835b1aebf44f859d547eda82b.jpg)  
图6碰撞检测处理

针对上面可能出现的问题，本文将碰撞处理分为两个阶段，首先找出所有与该点发生碰撞的椭球，计算出每一个碰撞相交点位置；然后计算这些相交点与该点初始位置之间的距离，碰撞点与该点初始位置距离最小的椭球意味着最早发生碰撞的椭球，所以可以把与距离最小椭球的碰撞相交点作为响应位置。如图6（b）所示，若质点 $p _ { 0 }$ 移动到 $p _ { 1 }$ 过程中与椭球 $O _ { 0 }$ 和 $O _ { \scriptscriptstyle 1 }$ 发生碰撞，分别相交于 $P _ { c }$ 和 $P _ { e }$ ，根据 $\left| P _ { e } P _ { 0 } \right| > \left| P _ { c } P _ { 0 } \right|$ 可以确定 $P _ { c }$ 为修正后的位置，其速度计算如式(9)所示。

$$
\nu _ { c } = \nu - 2 \cdot ( \nu \cdot n _ { c } ) \cdot \frac { n _ { c } } { \left| n _ { c } \right| }
$$

其中： $\nu _ { c }$ 表示修正后的速度， $\boldsymbol { \nu }$ 是修正前的原始速度， $n _ { c }$ 表示球心 $O _ { 0 }$ 到 $P _ { c }$ 的向量。

# 5 实验结果及分析

本文实验是在Window7，Intel(R)Core(TM)i3-2350MCPU$\textcircled { a } 2 . 3 \mathrm { G H z } , 4 \mathrm { G B }$ 内存笔记本电脑环境下，以 $\mathrm { C } { + } { + }$ 语言编写代码，编译环境为VisualStudio2010，运用OpenGL图形库对所有模型进行渲染。本文使用的人体模型均从Marvelous Designer3 服装仿真软件导出，服装布料的动力学模型采用文献[25]中方法构建，然后在重力和风力[26]的作用下进行动态仿真。

本文方法采用人体部分尺寸与身高H的线性关系提取中层特征点，结合人体结构特征提取腋下点和会阴点，最后使用测地距离进行模型分割，尽管逼近人体尺寸有计算误差，但是基本上符合人体拓扑结构；为进一步验证分割方法的有效性和拟合效果的优越性，将本文算法与文献[19]的拟合结果进行实验比较，采用不同性别、体型和姿势的模型分别进行实验，如图7所示，可以看出，两种方法均能实现对不同姿势的人体模型的高度拟合，但是本文方法无论是对正常体型还是肥胖体型，分割结果均能较好地反映人体层次结构特征，均能以较快的速度完成拟合，且拟合效果更佳，提高了仿真效率；而文献[19]方法由于采用反复迭代的方式，对于不同姿势的模型拟合耗时差异较大，效率相对较低。

表 2所示为本文方法与文献[19]两种方法的数据对比。可以看出对于同一模型，拟合椭球数相近的情况下，本文方法耗时较少，椭球拟合更接近人体模型。图9和图10展示的是椭球体代替角色模型完成与服装网格之间的碰撞处理，服装在重力和风力的作用下紧密依附于人体模型，有效避免了服装与角色模型之间的相互穿透，相比于传统包围盒响应效果更为真实。

表2本文方法和文献[19]两种方法对比  

<html><body><table><tr><td rowspan="2">模型</td><td rowspan="2">顶点数</td><td rowspan="2">椭球数</td><td colspan="2">耗时/s</td></tr><tr><td>文献[19]</td><td>本文(分割+拟合)</td></tr><tr><td>男士1</td><td>4065</td><td>60</td><td>7.6</td><td>0.8 + 1.4</td></tr><tr><td>男士2</td><td>3160</td><td>56</td><td>5.1</td><td>0.5 + 1.3</td></tr><tr><td>肥胖男</td><td>4210</td><td>90</td><td>14.2</td><td>0.8 + 2.3</td></tr><tr><td>女士1</td><td>5000</td><td>50</td><td>6.7</td><td>1.1 + 1.8</td></tr><tr><td>女士2</td><td>8055</td><td>59</td><td>11.8</td><td>2.4 + 2.5</td></tr><tr><td>女士3</td><td>7133</td><td>50</td><td>10.1</td><td>1.7 + 2.5</td></tr><tr><td>肥胖女</td><td>5000</td><td>70</td><td>10.0</td><td>1.1 + 2.6</td></tr></table></body></html>

本文算法中将人体模型分为躯干和四肢两大部分，分别使用不同的初始K值和拟合误差阈值，并把躯干各子区域中包含的顶点均值坐标作为初始质心，对所有分割区域采用剪枝优化的K均值聚类算法进行模型椭球体的优化细分。该方法有效改善了人体模型躯干部位椭球拟合误差较大的问题，同时减少了K均值聚类过程的迭代次数，有效提高了仿真速度。实验中针对不同姿势的模型，设置相同的拟合误差阈值和聚类截止阈值，通过控制参数的大小，分别得到图8中a、b、c、d、e、f所示拟合效果，其中a、b、c为男士2 模型，d、e、f为女士1模型，由左至右分别对应单一椭球初始拟合效果，躯干和四肢设置相同拟合阈值效果，躯干和四肢设置不同拟合阈值效果。可以明显的看到，在没有考虑拟合阈值的初始拟合效果中，模型驱干的拟合效果较差，细分优化后的椭球拟合效果较好，但是由于使用同一拟合误差阈值，导致椭球数较多，针对不同部位设置不同拟合误差阈值后不但能保证拟合的精度，同时降低了椭球体的数量，有效改善了碰撞检测的效率。

为了达到精确碰撞检测的要求，通过针对不同的部位设置恰当的拟合误差阈值，可以有效改善不同区域的精度，实现多阈值拟合效果，满足不同服装碰撞检测精度的需求，例如图9中宽松裙装仿真时，腿部区域可以设置较大的拟合误差阈值，相反图10中紧身服装试衣时可设置较小拟合误差阈值。如图8所示，通过对各部位设置不同阈值标准，模型不同部位的拟合效果明显改善，得到合理的划分和高度拟合的椭球。

在完成了人体模型的椭球体拟合之后，本文使用高度拟合的椭球体代替原始模型与服装在风力作用下的动态碰撞检测进行了实验。分别对两种姿势的人体模型着装衣裙进行仿真，仿真结果如图9所示，在重力和风力作用下，均无穿透现象，仿真效果逼真。图10所示为身着紧身衣服的女士模型和男士模 型的仿真结果。

a.文献[19]方法：

b.本文方法：

![](images/dd05e213649c3f9237d676b4e71d9d7b40bd0d0e5e6e1c96ad7b7f77fd4f55d9.jpg)  
图7不同方法椭球体拟合效果

![](images/8ad79b9592df9152ba76126476baa31841bb339e287a0e8de695cdc4ccacc106.jpg)  
图8不同模型初始拟合及细分优化效果对比

为了验证本文方法在碰撞检测处理上的优越性，将本文算法和文献[27]中算法进行实验比较，为了比较的公平性，针对相同的实验模型女士2，分别采用增加人体模型顶点数和增加服装模型顶点数的方式逐步增加整个实验着装模型的总顶点数，并将不同顶点数及三角面片数的人体着装模型应用于文献[27]方法和本文方法，通过比较平均每帧的碰撞检测处理时间得到图11和图12所示曲线对比图，单位为秒。从图11可以看出在仅增加人体模型顶点数时，随着着装模型顶点总数的增加，本文方法每帧碰撞检测处理的时间基本保持不变，相反文献[27]的方法呈现线性递增的趋势逐渐增加，原因在于碰撞检测处理阶段本文方法仅仅只需判断服装顶点与拟合椭球的位置关系，并更新服装顶点位置，省去了动态更新包围盒的时间。此外，本文方法对相同模型的顶点数不敏感，随着模型顶点数的增加，拟合椭球数变化较小，从而每帧碰撞检测处理时间并不随顶点数增加而增加；而文献[27]将非邻接三角对的基本图元标记放到了碰撞检测计算的过程中，虽然减少了存储该标记所用的内存空间，但是也增加了碰撞检测计算的复杂度。从图12可以看出在仅增加服装模型顶点数时，随着着装模型顶点总数的增加，两种方法在每帧碰撞检测处理的时间都稳定增长，但本文方法耗时较文献[27]降低了10倍。综合之，本文方法在处理碰撞检测的平均用时要优于文献[27]方法。

# 6 结束语

本文针对服装仿真中人体模型包围盒的紧密性和碰撞检测效率问题，提出一种基于椭球体的人体服装碰撞检测方法，与传统包围盒相比，本文方法在不需要精确分割的前提下，通过人体部分尺寸与身高H的线性关系，有效改善了模型分割速率，采用剪枝优化二分K均值迭代的方式生成系列紧密椭球，提高了拟合效率及碰撞检测处理效率，但针对不同模型，拟合误差的阈值大小 $\mu$ 需人为设定。除此之外，本文方法目前只适用于静态模型的服装碰撞检测，对于动态模型的服装碰撞检测可将椭球与皮肤同时绑定骨骼，仅对关节区域动态更新椭球包围盒，

这将是下一步研究的重点。

![](images/a4950f7229d4698213cc287e278ba9996ae677c2580ec967020f14bcdd6ea787.jpg)  
图9宽松裙装在重力和风力作用下效果(左:女士2,右:女士3)

![](images/3a1edee69738f4ede480937e859cb9d306f1f3ce081108c1ae9562f46ecf2cfd.jpg)  
图10紧身服装试衣效果

![](images/4e2ef9c6c740feffe0cbb22620df98d7363778027b5fb51a8ceec65e5e7ccccf.jpg)  
图11增加人体模型顶点数时每帧碰撞检测处理耗时对比

![](images/733ea6361fe6b540ec617c2aecbcfcfe334bbcccfe2ddb6823025eb386be89ab.jpg)  
图12增加服装模型顶点数时每帧碰撞检测处理耗时对比

# 参考文献：

[1]Tang Min,Manocha D,Tong Ruofeng,Fast continuous collision detection using deforming non-penetration filters [C]//Proc of the ACM SIGGRAPH Symposium on Ineractive 3D Graphics and Games.2010: 7-13   
[2]Narain R,Samii A,O'Brien JF.Adaptive anisotropic remeshing for cloth simulation [J].ACM Trans on Graphics,2012,31(6):Article No. 152   
[3]Yao Junfeng,Lan Lei,Lin Wenlin,et al.Realistic and stable animation of cloth [J]. Computer Animation and Virtual Worlds,2015,26 (3-4):281-289   
[4]Salazar FAS R, Machado B B, Mamani AVO,et al. Cloth simulation using AABB hierarchies and GPU parallelism [Cl//Proc of Brazilian Symposium on Games and Digital Entertainment. 2010: 97-107   
[5]Du H, Huang Kunchao,Wang Rromei, Research and implementation of penetration resolving for multi-layered virtual garment dressing [C]//Proc of the 4th International Conference on Digital Home.2012: 326-330   
[6]Shen Yanchun,Sun Xingyi,Research and improvement of colision detection based on oriented bounding box in physics engine [C]//Proc of the 3rd International Conference on Communication Software and Networks. 2011: 73-76   
[7]Guo Xinlu,Zhang Yakun,Liu Rong,et al. Eficient colision detection with a deformable model of an abdominal aorta [Cl//Proc of IEEE International Conference on Information and Automation.2016: 927-932   
[8]唐敏，Manoch D，童若锋．基于 SIMD 指令的柔性物体并行碰撞检测 [J]．计算机学报,2009,32(10):2042-2051   
[9]Zhang Xinyu,Kim Y J. Scalable collision detection using p-partition fronts on many-core processors [J]. IEEE Trans on Visualization and Computer Graphics,2014,20 (3): 447-456   
[10] Du P,Liu E S,Suzumura T.Parallel continuous collision detection for highperformance GPU cluster [C]/ Proc ofACM SIGGRAPH Symposium on Interactive 3d Graphics and Games.2017: 4   
[11] Ye J,Nyberg TR,Xiong G.Fast Discrete Intersection Detection for Cloth Penetration Resolution [C]// Proc of IEEE International Conference on Multimedia Big Data.2015: 352-357.   
[12] Wang Rui, Zhou Kun, Snyder J,et al. Variational sphere set approximation for solidobjects [J]. The Visual Computer,2006,22(9-11): 612-621   
[13]王君良，李重，金小刚，等．基于内部球的三维模型逼近与聚类[J]. 计算机辅助设计与图形学学报,2013,25(10):1446-1453   
[14] Li Hanwen,Wan Yi.Coherent hierarchical collision detection for clothing animation [Cl//Proc of IEEE International Workshop on Haptic Audio VisualEnvironments and Games.2011:129-134   
[15]杜顺，詹永照，王新宇．基于形状直径函数的三维网格模型零水印算法 [J]．计算机辅助设计与图形学学报,2013,25(5):653-658   
[16]王泽昊，黄常标，林忠威．三角网格模型的最小值边界分割[J].计算 机辅助设计与图形学学报,2017,29(1):62-71   
[17] Liu Shengjun,Wang CCL,Hui KC,etal. Approximating solid objects by ellipsoid-tree [C]//Proc of the 1lth IEEE International Conference on Computer-Aided Design and Computer Graphics.20o9:134-139   
[18] Meng Y,Mok PY,JinX. Interactive virtual try-onclothing design systems [J].Computer-Aided Design,2010,42 (4): 310-321   
[19]唐勇，杨偶傯，吕梦雅，等．自适应椭球包围盒改进织物碰撞检测方法 [J]．计算机辅助设计与图形学学报,2013,25(10):1589-1596   
[20]于勇，王兆其，夏时洪，等．一种姿态无关的人体模型骨骼提取方法 [J]．计算机研究与发展,2008,45(7):1249-1258.   
[21]GB//T10000-88．中国成人人体尺寸[S].北京：中国标准出版社,1988   
[22]GB//T13547-92.工作空间人体尺寸[S].北京：中国标准出版社,1992   
[23] Simari PD,Singh K.Extraction and remeshing of ellipsoidal representations from mesh data [C]//Proc of Graphics Interface.2005:161-168   
[24]LuL,ChoiYK,WangWP,etal.Variational 3D shape segmentation for bounding volume computation [J]. Computer Graphics Forum,20o7,26 (3): 329-338   
[25]孙守迁，徐爱国，黄琦，等．基于角色几何碰撞体估计的实时服装仿真 [J]．软件学报,2007,18(11):2921-2931   
[26]赖秋凤，侯进．基于噪声函数的随机风场作用的动态布料研究[J].计 算机仿真,2015,32(12):192-196   
[27] Tang Min,Curtis S,Yoon S C,et al. Interactive continuous collision detection between deformable models using connectivity-based culling [J]. IEEE Trans on Visualization and Computer Graphics,2009,15(4):544-557