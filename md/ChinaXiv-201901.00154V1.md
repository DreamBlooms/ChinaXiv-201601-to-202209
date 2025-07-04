# 三维重建网格模型的缺陷孔洞识别与修复方法

温佩芝ab，雷永庆 $^ { \mathrm { a , b ^ { \dagger } } }$ ，孙梦龙ab

(桂林电子科技大学 a.计算机与信息安全学院;b.广西图像图形智能处理重点实验室，广西 桂林 541004)

摘要：针对三维重建网格模型经常出现异常缺失孔洞的问题，提出一种缺陷孔洞自动识别与孔洞区域细节特征保持的曲面修复方法。首先对缺失区域的上下文及轮廓曲线进行异常检测以判断是否为缺陷孔洞，确认为缺陷孔洞后对孔洞周边的特征线进行检测与匹配构造孔洞区域的基曲面；之后引进一个无约束的三角剖分对基曲面进行三角化；最后利用网格的各向异性进行细化及形态调整，改善网格的拓扑结构和几何性质。实验结果表明，该方法能够有效地识别三角网格模型的缺陷孔洞区域并还原其细节特征。

关键词：三维重建；孔洞识别；孔洞修复；细节保持；特征线；各向异性 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.09.0773

Defective hole identification and hole-filling for 3d reconstruction mesh models

Wen Peizhia,b, Lei Yongqinga, bt, Sun Menglonga, b (a.SchoolofComputer Science&Information Security,b.Guangxi KeyLaboratoryof Intelligent Processingof Images& Graphics,Guilin University of Electronic Technology,Guilin Guangxi 541oo4,China)

Abstract: Aiming to solve the problem of abnormal holes occur in 3D reconstruction mesh models frequently,this paper proposed a novel method that hole-defect identification automatically and detail-preserving surface repair around he hole. Firstly,inorder to determine whether theholeisareal defectivehole,itdetected thecontext irregularityand contour iregularityof the missing region.Afterthat,itdetectedand matched the feature linesaroundthe hole,which were to form thefundamental surfaceoftheholearea,andthen it introducedunconstrained triangulation for basal surface.Finally,it madeuse of the anisotropyof mesh to refine and adjust morphologicall,which were to improve the topological and geometric propertiesof the mesh.The experimental results show that the proposed method can identifythe defective hole and restore the hole area's detail features of triangular mesh models effectively.

Key words: 3D reconstruction; hole identification; hole-filing; detail-preserving; feature lines; anisotropy

# 0 引言

在数字几何应用领域，三角多边形网格模型因其良好的可视化、简单灵活的表现能力，被越来越多的用在计算机视觉与图形学中表示物体的几何形态。由于现实物体形态及材质的复杂性，对目标物体进行三维网格重建生成时会造成孔洞、自相交、噪声、边冗余等方面的瑕疵，这对后续的几何模型展示及应用带来了极大的障碍。网格模型中的孔洞区域通常是模型缺失了几何信息且未经剖分的缺陷区域，待修补模型的孔洞区域处没有任何已知信息，使得构造一个连续、合理的几何结构来填充孔洞区域并得到令人信服的修复结果是一个具有挑战的课题。根据修复方法的不同，Perez 等人[1]将孔洞修复的方法主要分为两大类：一种是基于体素的方法，另一种是基于曲面定向的方法。

基于体素的方法主要思想是将待修补的网格模型转换成体的形式表达，在体的基础上进行修补操作，再利用等值面抽取技术转换表达成多边形网格。Kumar[2]利用体扩散方程沿着体的表面扩散到数据缺失区域；吴晓军等人[3]提出了可见外壳与多视图三维点云融合的多视图立体修复算法；Paulsen等人[4]建立符号距离场对初始点集能量最小化，后引入马尔可夫随机场（MRF）进行规则化； $\mathrm { J u } ^ { [ 5 ] }$ 通过建立一个八叉树网格结构，提出了等值面曲面重建的方法，但只能适用处理小的孔洞。这种基于体的方法虽然在效率上有良好的表现，但是在模型转换之间会丢失一些原有的细节特征信息，修复后的模型往往会比原有的模型出现多余的多边形面片，这对后续的网格简化等操作会造成输出网格质量的降低。

基于曲面定向的方法一般是在待修补的网格模型上对孔洞进行定位检测和修复。Liepa[通过最小化相邻曲率的能量函数直接在待修复模型的孔洞区域进行Delaunay三角剖分；Wang等人[7先对孔洞顶点进行特征分类与匹配，之后用波前法（AdvancingFrontMethod）进行细化填充，；另外还有基于Bezier 曲面[8]、径向基函数插值[9]、Laplacian 滤波[10]、变分水平集[1等方法。这些方法在一定程度上能修复三维模型的破损区域，但计算复杂度高且在过渡区域不能自然衔接，无法很好的恢复孔洞原始的曲面细节特征。刘震等人[12]将修复工作分为两步，首先利用动态规划的方法三角剖分构造基曲面，然后在基曲面的基础上通过基于特征线优先级的分层收缩策略不断迭代添加曲面细节，直到剖分孔洞形成的三角形的边长小于边界边的边长为止。所述方法步骤繁多，且实现的每一步算法复杂度高，仅基于动态规划进行三角剖分的时间复杂度就为 $o ( n ^ { 3 } )$ ；且现有的大多数方法中，修复的过程需要人工参与判断该孔洞是否是三维重建中形成的缺陷孔洞还是原本模型的自然所属，无法满足自动化的需求。

本文针对上述缺点，提出一种三角网格模型缺陷孔洞自动识别与曲面细节保持的修复方法，通过对孔洞的缺陷检测，解决了修复过程中需要人工判断的过程；而在孔洞填充部分先构造基于特征线的基曲面，之后仅使用一个时间复杂度为$\mathrm { { O } } ( \log n )$ 的三角剖分函数，不需满足任何最优化的约束条件，后续也仅需较少次数的迭代进行细化，避免了高代价的孔洞多边形最优三角化的求解过程。本文方法中首先利用孔洞轮廓周边的点集聚类和轮廓曲线切向量的变化对孔洞进行检测，确认是否为需要被填充的单连通区域缺陷孔洞；判断为缺陷孔洞后，对缺陷孔洞区域周边的特征线进行检测与匹配以恢复缺陷孔洞区域的特征线，实现缺陷孔洞区域基曲面的构造；最后对基曲面填充时先进行无约束的一般三角化，再利用三角网格模型的各向异性特性进行细化及形态调整，之后能输出更高质量、几何性质鲁棒的三角网格模型。实验结果表明，与文献[6]相比，本文方法很好的保持了曲面原有的细节特征信息，修复的孔洞区域能与周边自然地过渡衔接。

# 1 缺陷孔洞的检测

三维重建的过程中由于算法精度及周边环境高光会对重建后的三维模型产生孔洞的影响，在自动修复孔洞过程中需要辨别该孔洞是需要被修复的缺陷孔洞还是模型自身所属的非缺陷孔洞。如图1所示，是缺陷孔洞与非缺陷孔洞的区别。自动修复孔洞前首先要搜索孔洞的位置，而搜索孔洞最简单有效的方式就是检查一系列边界边的连续性，所谓边界边就是三角网格模型中不与别的三角形共用同一条边。文献[6]中的方法首先是在网格上进行一般搜索，找到一个初始的边界三角形，接着对邻域三角形进行搜索以寻找下一个边界边，直到初始三角形被检索，一个闭环的孔洞路径被检测出来。可是该方法的局限性在于当被检测的三维网格模型是一个非完全封闭的表面时，不能判断此闭合路径是否是真实的缺陷孔洞，所以自动修复孔洞首先要解决的问题在于区分一个表面不连续是否属于目标模型的自然表面。基于上述问题，在填充孔洞之前，本文首先判断网格模型上孔洞的真实性，提出一种验证缺陷孔洞与非缺陷孔洞的方法，从孔洞最重要的几何特性包括周边表面不规则性和轮廓曲线不规则性这两个方面描述缺陷孔洞。

![](images/76ffdffbb96fbfa3c04cbc15f8f0f3eb51552ba5eb13ae1552e871eb48b0cc93.jpg)  
图1孔洞的分类

# 1.1孔洞上下文的异常检测

上下文不规则测量通过孔洞周围区域的差异量化进行聚类环境的分析。对每一个聚类来说，质心的几何拓扑特性用来表示一个形状特征，因此这一步通过区域生长完成了一般性的聚类生成。文献[6]计算了模型表面每一点所在位置的先验曲率估计，先查找当前点 $p _ { i } ( x , y , z )$ 最邻近的 $n$ 个点，构成$\scriptstyle n \times 3$ 的矩阵，之后计算协方差矩阵得到特征值，使每一个类的方差都不超过一个固定的阈值 $\beta$ ，小于阈值 $\beta$ 的部分即为选取的主成分，近似于求解协方差矩阵进行主成分分析(PCA)，如下：

$$
m c = { \frac { 1 } { n - 1 } } \sum _ { i = 1 } ^ { n } ( p _ { i } - { \overline { { p } } } ) ( p _ { i } - { \overline { { p } } } ) ^ { T }
$$

其中： $n$ 是 $p$ 的邻域大小， ${ \overline { { p } } } = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } p _ { i }$ 是每个类的质心。曲率估计如文献[13]计算如下：

$$
c = \frac { \lambda _ { 0 } } { \lambda _ { 0 } + \lambda _ { 2 } + \lambda _ { 3 } }
$$

其中： $\lambda _ { 0 } \leq \lambda _ { 2 } \leq \lambda _ { 3 }$ ，而与 $\lambda _ { 0 }$ 有关的特征向量表示数据的低变化方向，因此，计算表面 $p$ 点的法向量，便于参数 $\mid c \mid$ 能表示表面切线的变化，这也是表面区域变化的一种度量方式。只要计算得到了曲线的近似值，那下一步就是计算表面的聚类。以上表述的算法流程如下所示：

a)选取一个随机种子点，且生成一个新的类 $\mathrm { { C _ { i } } }$ 。

b)增加一个顶点 $\mathrm { V _ { k } \in N _ { C _ { i } } }$ ，使 $\mathrm { V } _ { \mathrm { C } _ { \mathrm { i } } } < \beta$ 。这里 $\mathrm { N } _ { \mathrm { c } _ { \mathrm { i } } }$ 是类 $\mathrm { { C _ { i } } }$ 的径向邻域，且 $\mathrm { V } _ { \mathrm { C } _ { \mathrm { i } } }$ 是类 $\mathrm { { C _ { i } } }$ 的方差估计。

本文中用曲率估计的方法对孔洞轮廓周边的点集进行聚类，然而高斯曲率和平均曲率这些经典的曲面曲率表示方法并不能很好的表示局部形态。在这里，采用一种独立于表面大小的测量方式，以至于能够描述表面的局部形态：形状索引(shapeindex)[14]就是描述曲面上任意点在表面邻域二级结构的一种方法，估计方法如下所示：

$$
s = \frac { 2 } { \pi } \arctan \frac { k _ { 2 } + k _ { 1 } } { k _ { 2 } - k _ { 1 } }
$$

其中： $k _ { 1 } \geq k _ { 2 }$ 是主曲率，除了平坦区域是一个不确定的形状索引外，其余表面区域中 $s \in [ - 1 , 1 ]$ 。为了描述一个完整的全局孔洞轮廓，就要计算类间的平均形状索引，而又由于形状索引是一个点方法，所以每一个类 $i$ 的质心形状索引为

$$
\overline { { S } } I = \frac { 1 } { N } \sum _ { i = 1 } ^ { k } p _ { i } s _ { i }
$$

$c _ { i }$ 是 $K$ 个类中的一个子集， $s _ { i }$ 是类 $c _ { i }$ 的形状索引，点集的大小 $\ N { = } p _ { 1 } + \cdots + p _ { k }$ ， $p _ { i }$ 表示每一类的点集数。如图2所示，反映了孔洞周边点集聚类分布的情况。

![](images/a390a2fadccfbeb936959ee05732f4f82996a461daaceafb265bc9c04c8c61fc.jpg)  
Fig.1 Classification of holes   
图2轮廓周边的点集分布 Fig.2Points'distribution around hole

# 1.2孔洞轮廓的异常检测

孔洞轮廓的异常检测即是检测计算轮廓曲线的曲率与扭力这两个几何特性的变化，具体参数的计算是使用条件熵测量的方法得到。然而基于曲线扭力的方法，不能很好地处理当孔洞轮廓处于平坦区域时的情况，所以在这一步中，本文采用文献[15]中对轮廓曲线曲率测量的方法，即通过测量孔洞轮廓切向量的变化，判断该孔洞是否属于缺陷孔洞。对缺陷孔洞来说，孔洞轮廓上切线的变化方向是杂乱无章的，反映在具体数学参数上表现为条件熵值过高；而非缺陷孔洞在切线角度上的变化是平滑过渡的。

![](images/d6f1c911a581b268f4d70c98fa582127fed7ec367d2021802e727bdeab842115.jpg)  
图3孔洞轮廓的法向分布

切向量定义为 $T ( t ) = N ( s ) \times B ( s ) = r ^ { \prime } ( t ) / \| r ^ { \prime } ( t ) \|$ ，其中$N ( s ) = r ^ { \prime \prime } ( t ) / \| r ^ { \prime \prime } ( t ) \|$ 为法向量， $s ( t _ { 1 } ) = \int _ { t _ { 0 } } ^ { t _ { 1 } } \| r ^ { \prime } ( u ) \| d u$ 为参数曲线 $\boldsymbol { r }$ 上的弧长，B(s)=(s）N(s)=- 为轮廓曲线上的扭力，采用最小二乘法和局部弧长估计的方法来计算其切向量，根据条件熵[16]的概念，切线变化的条件熵为

$$
S _ { T } = - { \sum _ { i } ^ { n } p } ( \varphi _ { i } , \psi _ { i } ) \log ( p ( \varphi _ { i } | \psi _ { i } ) )
$$

综上所述，孔洞轮廓异常测量（全局熵）的计算方式为

$$
i r r e g u l a r i t y = \| \overline { { S } } I \| \cdot S _ { T }
$$

![](images/5f6d54f2ae6dde75368f59341b1bd78efa9727a765b0f3cc57bbdddc63c04d52.jpg)  
Fig.3Normal distribution of hole boundary   
图4曲线上切线与法线的分布  
Fig.4Tangent,normal distribution of curve

图3所示是缺陷孔洞与非缺陷孔洞关于切向量方向的变化情况，图4所示是曲线上切向量与法向量的分布。实验中设置一对参照实验各10个孔洞轮廓，一组是缺陷孔洞，另一组是非缺陷孔洞。经计算得到使缺陷孔洞与非缺陷孔洞分离的熵值确定为3.1，高于3.1的熵值确定为缺陷孔洞，反之为非缺陷孔洞。

# 2 细节特征保持的修复方法

细节特征的保持在本文中指的是恢复模型原有的特征线，所谓三维模型表面特征线是曲面上能够表示显著几何特征的脊线和谷线，在数学计算上的定义是对模型表面沿着相应主方向曲率拟合极值的描述。对于具有丰富细节特征的三维模型，特征线及其附近区域经常具有曲面的显著几何特征[17]，所以特征线的检测与匹配连接对于保持原孔洞区域的细节信息具有重要的作用。本文提出的基于特征线的曲面细节恢复方法中，先进行特征线的检测[18]与最优化匹配形成基曲面的构造，这一步完成了孔洞缺失部位基本信息的恢复；之后对形成的基曲面进行一般的三角剖分[19]，仅使用一个算法复杂度为 $O ( \log n )$ 的递归函数就能实现，在形成的基曲面基础上进行三角面片的剖分；最后利用孔洞网格的各向异性进行细化及形态调整，改善网格的拓扑结构和几何性质，使之与周边网格完美过渡并保持密度一致。

# 2.1特征线的检测

特征线表征模型表面的几何特征，对带有单连通区域孔洞的三维模型，先检测孔洞周边区域的特征线，这是本文细节特征保持修复方法的第一步。利用离散微分算子对分段线性网格进行操作，避免了高阶表面拟合技术或隐士曲面流程这样预处理操作步骤。对于绝大部分几何模型来说，曲面噪声造成了大量奇异三角形的出现，在进行特征线的检测之前，可先对三维表面进行平滑处理操作，之后再计算离散极值。

假设M是三维空间中的光滑曲面， $\vec { K } _ { i }$ 是沿着M中曲率线上的单位切向量， $e _ { i } = \left. \nabla K _ { i } , \vec { K } _ { i } \right.$ 被称为是极值系数。其中 $e _ { i }$ 是曲面上的隐函数， $\vec { K } _ { i }$ 的符号选择决定了 $e _ { i }$ 的符号。对于 $\mathbf { \delta M }$ 上所有点集来说，特征线表现了曲面几何有用的特征信息，函数 $e _ { i }$ 的值为0即为曲面 $\mathbf { \delta M }$ 上的一条特征线，分为两种情况 $e _ { \mathrm { m a x } }$ 和 $e _ { \mathrm { m i n } }$ ：

$$
e _ { \mathrm { m a x } } = 0 : \Big < \nabla e _ { \mathrm { m a x } } , \vec { K } _ { \mathrm { m a x } } \Big > < 0 , \big | K _ { \mathrm { m a x } } \big | > \big | K _ { \mathrm { m i n } } \big |
$$

$$
e _ { \mathrm { m i n } } = 0 : \big < \nabla e _ { \mathrm { m i n } } , \vec { K } _ { \mathrm { m i n } } \big > > 0 , \big | K _ { \mathrm { m i n } } \big | > \big | K _ { \mathrm { m a x } } \big |
$$

对于规则三角形 $T = ( p _ { 1 } , p _ { 2 } , p _ { 3 } )$ ，依次对三角形的顶点计算$\vec { \mathrm { K } } _ { \mathrm { m a x } } ( \boldsymbol { p } _ { i } )$ 和 $e _ { \mathrm { m a x } } ( { p } _ { i } )$ ， $\scriptstyle { i = ( 1 , 2 , 3 ) }$ 。由于 $e _ { \mathrm { m a x } }$ 对于三角形 $T$ 是一个线性函数，计算 $e _ { \mathrm { m a x } }$ 的梯度。

$$
\begin{array} { r } { \left. \nabla e _ { \mathrm { m a x } } , \sum _ { p _ { i } \in T } \vec { K } _ { \mathrm { m a x } } ( p _ { i } ) \right. < 0 } \end{array}
$$

$$
\begin{array} { r } { \left| \sum _ { p _ { i } \in T } \vec { K } _ { \operatorname* { m a x } } ( p _ { i } ) \right| > \left| \sum _ { p _ { i } \in T } \vec { K } _ { \operatorname* { m a x } } ( p _ { i } ) \right| } \end{array}
$$

如果 $e _ { \mathrm { m a x } } = 0$ 为非空且满足式(9)(10)的条件，与 $e _ { \mathrm { m a x } }$ 对应的特征线段就被检测出来。对式(8)采取上述类似的处理方式，则对应 $e _ { \mathrm { m i n } }$ 的特征线段也被检测出来。在所有的特征线被提取之后，用阈值方案处理所提取的特征线，槟弃一些小线段和弯曲的波浪线，余下的即为本文方法所采用的特征线。

# 2.2特征线的匹配

对三维网格模型孔洞周边的特征线进行了检测，接下来就是进行特征线的匹配[20]以恢复孔洞中的特征线，构造三角剖分的基曲面，以提高孔洞区域上的细节恢复效果。

假设 $S = \{ s _ { i } \} , i = 1 , 2 , 3 , \cdots N$ 是孔洞区域周边提取的特征线集合，对于特征线 $s _ { i } \in S$ ，待匹配特征线集合为$C _ { i } =  s _ { j } \in S | \vec { s } _ { i } \cdot \vec { s } _ { j } < \delta $ ，其中 $s _ { i }$ 是以孔洞边界顶点 $\nu _ { i , 0 }$ 为起点且有（20 $m$ 个采样点 $\nu _ { i , 0 } , \nu _ { i , 1 } , \cdots , \nu _ { i , m }$ 的特征线， $\vec { s } _ { i } = \sum _ { k = 0 } ^ { m - 1 } \bigl ( \nu _ { i , k } - \nu _ { i , k + 1 } \bigr )$ 为特征线平均单位方向，阈值参数 $\delta \in [ - \sqrt { 2 } / 2 , 0 ]$ ，匹配集合中元素的数目决定于阈值 $\delta$ 的大小， $\delta$ 越小则集合中元素的数目就越多，实际中本文选取 $\delta$ 的值为 $- { \sqrt { 2 } } / 2$ 。给出了特征线 $s _ { i }$ 与集合 $C _ { i }$ 中的待匹配特征线，通过匹配概率（matching possibility，MP）衡量标准选取最优匹配：

$$
M P ( s _ { i } , s _ { j } ) = \frac { 1 } { m + 1 } \sum _ { k = 0 } ^ { m } \exp \left( - \frac { \left| \nu _ { j , k } - a _ { j , k } \right| ^ { 2 } } { \sigma ^ { 2 } } \right)
$$

其中： $s _ { j } \in C _ { i }$ ， $a _ { j , k }$ 为 $s _ { j }$ 的第 $k$ 个采样点 $\nu _ { j , k }$ 在特征线 $s _ { i }$ 拟合曲线上的投影，高斯函数中参数 $\sigma$ 取0.5，如图5所示为特征线检测与匹配的示意图。

对于特征线 $s _ { i }$ ，使 $M P \big ( s _ { i } , s _ { j } \big )$ 最大的 $s _ { j } \in C _ { i }$ 即为 $s _ { i }$ 的最优匹配。如果 $s _ { j }$ 的最优匹配也是 $s _ { i }$ ，则称 $( s _ { i } , s _ { j } )$ 为最优匹配对，选取最优匹配对 $( s _ { i } , s _ { j } )$ ，使用球面线性插值方法将特征线匹配对连接起来，即

$$
\vec { u } \left( t \right) = \frac { \sin \left( \left( 1 - t \right) \varphi \right) } { \sin \varphi } \vec { u } _ { 0 } + \frac { \sin ( t \varphi ) } { \sin \varphi } \vec { u } _ { 1 } , t \in [ 0 , 1 ]
$$

其中： $\vec { u } _ { o } = \left( \nu _ { i , 0 } - o \right)$ ， $\vec { u } _ { 1 } = \left( \boldsymbol { \nu } _ { j , 0 } - o \right)$ ，其中 $\textit { o }$ 是由 $\nu _ { i , 0 } , \nu _ { i , 1 } , \nu _ { j , 0 }$ 三点所确定圆的圆心， $\varphi$ 为向量 ${ \vec { u } } _ { 0 }$ 和 $\vec { u } _ { 1 }$ 之间的夹角，连接起来的这条线称为匹配对 $( s _ { i } , s _ { j } )$ 的桥线。

![](images/217fb5de67e787df11c46348d18b8b7859c8b23d897efd207fc248cb580fa31e.jpg)  
图5特征线的检测与匹配

# 2.3三角剖分及细化调整

上述部分进行特征线的匹配与桥接之后，表征细节特征信息的脊线与谷线被恢复，原孔洞部分被划分为了几个简单的多边形子洞，基曲面构造完成。由于形成的基曲面只是特征线的连接，并没有形成表示网格模型的三角面片，之后需对每一个多边形子洞进行三角化。现有的许多方法中，孔洞区域的三角剖分是整个算法的关键步骤，其本质是一个非线性的优化问题，为获得最优的三角化结果，其时间复杂度通常很高。为了解决最优化三角剖分时间复杂度高的问题，在本方法之前步骤中形成的基曲面的基础上使用平均时间复杂度为 $o ( \log n )$ 的递归函数 $F i n d ( i , j )$ 进行无约束的三角化(i， $j$ 为多边形子洞的顶点标号)，步骤所示如下：

a)如果 $j = i + 2$ ，则将 $\Delta \nu _ { i } \nu _ { i + 1 } \nu _ { j }$ 加入到三角形集合s中。b)否则令 $m _ { i j }$ 为 $i$ ， $j$ 之间的任一数。c)在步骤 b)的条件下，如果 $m _ { i j }$ 不等于 $i + 1$ ，递归调用$F i n d ( i , m _ { i j } )$ ，将 $\Delta \nu _ { i } \nu _ { m _ { i j } } \nu _ { j }$ 加入到三角形集合s中。

d)如果 $m _ { i j }$ 不等于 $j - 1$ ，递归调用 $F i n d ( m _ { i j } , j )$

在递归函数 $F i n d ( i , j )$ 中， $\Delta { \nu } _ { i } { \nu } _ { m _ { i j } } { \nu } _ { j }$ 是本次递归分割出的三角形，依次递归，多个多边形子洞被三角剖分而得以填充。

但此时填充的网格质量较差，与周围网格的采样率及顶点密度相差较大，所以需要对填充后的孔洞网格进行细化。本文采用边记分函数为每条边赋予一个影响因子[19]，实现网格的各向异性的细化。

影响因子由边的长度和密度两个元素构成，反映的是最终的孔洞网格的疏密程度，边 $e _ { i j } = \nu _ { j } - \nu _ { i }$ ，则边的长度为$l ( e _ { i j } ) = \left\| e _ { i j } \right\| = \left\| \nu _ { j } - \nu _ { i } \right\|$ 。对于另一个元素边的密度，先定义顶点 $\nu$ 的密度 $\rho ( \nu ) = \mu \big | K ( \nu ) \big | + ( 1 - \mu ) H ^ { 2 } ( \nu )$ ， $\mu \in ( 0 , 1 )$ ，而 $K ( \nu )$ 和 $H ( \nu )$ 分别为该点的高斯曲率和平均曲率。如下图6所示，对于顶点$\nu _ { 0 }$ ， $e _ { 0 1 } , e _ { 0 2 } , \cdots , e _ { 0 n }$ 为其顶点 $\nu _ { 0 }$ 对相邻顶点 $\nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { n }$ 形成的边；相邻两条边 $\boldsymbol { e } _ { 0 i }$ 和 $e _ { o ( i + 1 ) }$ 之间的夹角为 $\alpha _ { i } = a n g ( e _ { 0 i } , e _ { 0 ( i + 1 ) } )$ ;（204号 $\Delta \nu _ { 0 } \nu _ { 0 i } \nu _ { 0 ( i + 1 ) }$ 所在平面的法向量为 $n _ { i } = \frac { e _ { 0 i } \times e _ { 0 ( i + 1 ) } } { \left\| e _ { 0 i } \times e _ { 0 ( i + 1 ) } \right\| }$ ；相邻三角形所在平面的夹角为 $\beta _ { i } = a n g ( n _ { i } , n _ { i + 1 } )$ 。

顶点 $\nu _ { 0 }$ 的高斯曲率 $K$ 和平均曲率 $H ^ { \ [ 2 1 ] }$ 的定义为

$$
K ( \nu _ { 0 } ) = \frac { 2 \pi - \sum _ { i = 1 } ^ { n } \alpha _ { i } } { 3 a r e a ( S ) }
$$

$$
H ( \nu _ { 0 } ) = \frac { \displaystyle \sum _ { i = 1 } ^ { n } \lVert e _ { i } \rVert \lVert \beta _ { i } \rVert } { 4 a r e a ( S ) }
$$

其中： $s$ 是与顶点 $\nu _ { 0 }$ 相邻的所有三角形的面积之和。

![](images/83cc037f9d118b4b3504ee732a25e2cd8bf98629d91a0124075d43dd28a1631e.jpg)  
Fig.5Detection and matching of feature lines   
图6与顶点 $\nu _ { 0 }$ 相关的几何量定义  
Fig.6Geometric definition about $\nu _ { 0 }$

本文假设边的密度从一个顶点 $\nu _ { i }$ 到另一个顶点 $\nu _ { j }$ 之间是线性变化，则边密度 $\rho ( e _ { i j } )$ 可由两个顶点密度的均值表示为

$$
\rho ( e _ { i j } ) = \frac { \left| \rho ( \nu _ { i } ) + \rho ( \nu _ { j } ) \right| } { 2 }
$$

定义了边的长度和密度之后，边 $e _ { i j }$ 的记分函数由准高斯核函数给出，即

$$
M _ { i j } = \frac { 1 } { \sqrt { 2 \pi } \sigma } \Biggl ( 1 - \exp ( - \frac { \rho _ { i j } ^ { 2 } + l _ { i j } ^ { 2 } } { 2 \sigma ^ { 2 } } ) \Biggr )
$$

通过该记分函数，先计算孔洞周围区域网格的每条边的记分，并求其平均值 $\bar { M }$ 。孔洞网格填充后的每条边的一个记分为 $M _ { i j }$ ，若 ${ M } _ { i j } > \overline { { M } }$ ，则对该边进行边分裂操作，即在该边的中点处插入一个新的顶点，并将这个新顶点与该边所在三角形的两个对顶点分别相连，如图7所示。

对孔洞网格填充细化之后，需要对修复后的网格进行几何形态调整，这种调整在局部是按各向异性进行的。本文通过边置换来保证孔洞网格的Delaunay性质。对于相邻的两个三角形ABC和 $\Delta A B D$ ，当ABC确定一个外接圆时，对顶点 $D$ 进行判断： $D$ 到该圆上的投影点 $D ^ { \prime }$ 在外接圆外时，边 $\mathbf { \nabla } _ { A B } $ 具有局部Delaunay 性质，无须进行操作；否则需要将边 $\mathbf { \nabla } _ { A B } $ 置换为边 $\boldsymbol { c D }$ ，如图8所示。

![](images/1b97cd27fa8dee784a1d6d7a3660f460525309e645846d60559298e2a17d0af5.jpg)  
图7边的拓扑分裂

![](images/ca65bb573eca9facaac8f667ca5aa3007aaf8c383d1932ea3a0ca674ccf34a28.jpg)  
Fig.7Edge's topology split   
图8边的拓扑置换

上述过程在孔洞区域一般三角化后进行迭代操作，直到无边分裂即完成了孔洞网格的细化。这种后续的规整步骤只需要较少次数的简单迭代，就能获得几何性质良好的三角网格，且能够与孔洞周边实现自然过渡。

# 3 实验结果与分析

本文实验电脑配置为：CPU3.70 GHzIntelR）CoreTMi3-6100、RAM12.0GB、Windows1064位，编程采用MATLAB、Python，OpenCV、MeshLab。为验证本文提出的算法的有效性与正确性，实验对象选择图形库Geometry++中最具代表的三维网格结构，修复后的结果也均以网格模型的结构展示，实验结果与Liepa方法进行对比。

图9所示为Eight 模型的修复效果对比，图中，(d)(e)(f)分别为图(a)(b)(c)孔洞局部区域放大并向右旋转60度后的观察角度，(a)(d)为原始破损模型，(b)(e)为Liepa方法的结果，(c)(f)为本文方法修复后的效果图。从图中可以看出，Liepa方法只是在孔洞区域原始顶点的基础上进行三角剖分，破坏了原始模型的几何结构；而本文方法恢复了孔洞区域的几何特征结构并且延续了孔洞周边区域的特征线，对其模型的脊线特征得到了很好的保持。图10所示为Squirrel模型的修复结果对比，图中，(d)(e)(f)分别为图(a)(b)(c)的局部放大图，(b)(e)为Liepa方法的结果图。可以明显看出修复后的三角网格密度与周边三角网格密度不一致且没有很好的延续原有孔洞周边网格的特征线；(c)(f)为本文算法修复后的效果，不仅修复后的三角网格密度与原始孔洞周边三角网格密度保持一致，而且很好的延续了孔洞周边的特征线，捕获了孔洞的全局特征，使孔洞区域的显著性几何特征得到了很好的恢复。图11所示为Diana模型的修复效果比较，(a)为带孔洞的原始模型，该模型的后脑顶部有大部分缺失区域；Liepa方法只能沿着孔洞轮廓顶点进行三角剖分，根本不能还原原始模型后脑顶部凸起特征，修复效果极差，难以反映其原始模型的原始特征信息；本文方法修复后的效果可以明显看出对后脑顶部的孔洞区域原始特征信息进行了很好的还原，三角网格密度也与原始网格模型保持一致。由实验的修复效果可以看出，本文方法的修复结果不仅能捕获孔洞区域的全局特征，且局部的显著几何特征也得到了很好的恢复，对不同尺度的孔洞区域都给出了较好的填充效果。图12中为Bunny 模型的修复效果比较，(a)为带两个单连通区域的孔洞模型，其中大腿和背部都有明显的区域缺失；经过Liepa方法后，其修复效果跟图11所示相同，只能沿着孔洞轮廓顶点进行三角剖分，且没有考虑到采样密度与周边三角网格一致，修复效果极差，难以反映模型原表面的细节特征信息，如图12(b)所示；图12(c)为本文的修复方法，不仅还原了颈部凹陷的特征，并且在Bunny 背部及其大腿上很好的修复了原有的凸起特征，细节特征保持良好。

![](images/817ec71c16f6eb9688342c1e04ff4ae77aaa6cf2351fccb477446f78751a51fd.jpg)  
Fig.8Edge's topology substitution   
图9Eight模型修复效果比较 Fig.9Comparison of Eight model

![](images/9e56134993e7be92a7200db4055bfc762d8a4c6e7482559cafcac7647b6952d4.jpg)

![](images/37589da070c522d82c32d756b9950f51b8aafce18517d07326a042e0f3b3cb62.jpg)  
图12Bunny 模型修复效果比较Fig.12Comparison of Bunny model

表1和2分别列出了原始模型、Liepa方法和本文方法所修复后的模型顶点个数与三角面片的数量比较，可以看出Liepa方法后的顶点数量与原始破损模型的顶点数量一样，即 Liepa 方法只在原始破损模型的孔洞轮廓上进行三角剖分，不会考虑到原始特征信息的保持，而本文方法修复后的模型不管是在顶点数量还是在三角面片的数量上都高于Liepa方法，且对于大孔洞区域的面片数大大增加，极大的丰富了孔洞区域的细节特征信息。

Table 1Vertexes comparison of models   

<html><body><table><tr><td></td><td>原始模型</td><td>Liepa方法</td><td>本文方法</td></tr><tr><td>Eight</td><td>766</td><td>766</td><td>768</td></tr><tr><td>Squirrel</td><td>10745</td><td>10745</td><td>10850</td></tr><tr><td>Diana</td><td>9762</td><td>9762</td><td>10040</td></tr><tr><td>Bunny</td><td>33144</td><td>33144</td><td>35292</td></tr></table></body></html>

表2模型的面片数比较

表1模型的顶点数比较  
Table 2Patches comparison of models   

<html><body><table><tr><td></td><td>原始模型</td><td>Liepa方法</td><td>本文方法</td></tr><tr><td>Eight</td><td>1516</td><td>1532</td><td>1543</td></tr><tr><td>Squirrel</td><td>21454</td><td>21465</td><td>21477</td></tr><tr><td>Diana</td><td>19379</td><td>19520</td><td>20074</td></tr><tr><td>Bunny</td><td>65922</td><td>66280</td><td>70580</td></tr></table></body></html>

# 4 结束语

针对任意三角网格模型，本文提出了一种自动识别真实缺陷孔洞与保持细节特征的修复方法，解决了现阶段大多数孔洞填充算法都需要人工参与判断的问题，利用无约束的三角化代替求解非线性的最优化三角剖分极大地降低了算法的时间复杂度。首先利用孔洞上下文异常检测及轮廓异常检测对三角网格模型的孔洞进行检测，判断该缺失区域是否属于真实缺陷孔洞；然后利用孔洞周边特征线的信息进行检测与匹配以实现对破损区域基曲面的构造，再在基曲面的基础上进行三角剖分，采用边记分函数为每条边赋予一个影响因子，进而实现网格的各向异性的细化及形态调整。通过与其他方法相比，本文能很好地还原原始模型的细节特征，并且在模型修复质量和计算效率方面取得了很好的平衡，为三维模型的后续处理提供更精确的模型结构。但本文解决的问题仅适用于单连通区域的缺陷孔洞修复，忽略了复杂缺失区域的拓扑结构，算法的时间复杂度也较高，后期会进一步研究复杂缺失区域的情况，并考虑使用GPU并行加速处理，以实现复杂破损模型的快速修复。

# 参考文献：

[1]Pérez E,Salamanca S,Merchan P,et al.A comparison of hole-filling methods in 3D[J]. International Journal of Applied Mathematics and Computer Science,2016,26(4): 885-903.   
[2]Kumar A,Shih A M.Hybrid approach for repair of geometry with complex topology [C]//Proc of the 20th International Meshing Roundtable.Springer,Berlin,Heidelberg,2011:387-403.   
[3]吴晓军，文飞，温佩芝．多视图立体三维重建中的孔洞修复算法[J]. 计算机辅助设计与图形学学报，2012，24(12):1606-1613.(Wu Xiaojun,Wen Fei,Wen Peizhi.Hole-filling algorithm in multi-view stereo reconstruction [J].Journal of Computer-Aided Design & Computer Graphics,2012,24(12):1606-1613.)   
[4]Paulsen RR,Baerentzen JA,Larsen R.Markov Random Field Surface Reconstruction [J].IEEE Trans on Visualization& Computer Graphics, 2010,16 (4): 636-646.   
[5]Ju Tao. Robust repair of polygonal models [J].ACM Trans on Graphics. 2004,23 (3): 888-895.   
[6] Liepa P.Filing holes in meshes [C]/Proc of Eurographics/ACM SIGGRAPH Symposium on Geometry Processng. 2003: 200-205.   
[7]Wang Xiaochao,Liu Xiuping,Lu Linfa,et al.Automatic hole-filling of CAD models with feature-preserving [J]. Computers & Graphics, 2012, 36 (2): 101-110.   
[8] Li Zhong,Meek D S,Walton D J. Polynomial blending in a mesh hole-filingapplication[J].Computer-AidedDesign，2010，42(4): 340-349.   
[9]Liu Shengjun，Wang C C L. Quasi-interpolation forsurface reconstruction from scatered data with radial basis function [J]. Computer Aided Geometric Design,2012,29(7): 435-447.   
[10] Wei Mingqiang，Wu Jianhuang，Pang Mingyong.An integrated approach to fillig holes in meshes [C]// Proc of International Conferenceon Artificial IntellgnceandComputationalIntellice. 2010: 306-310.   
[11]张婧，周明全，耿国华.基于变分水平集的三维模型复杂孔洞修复 [J].计算机应用研究，2018，35(4):1254-1257.(Zhang Jing，Zhou Mingquan，Geng Guohua. Repair methods for complex hole of thre-imensionalmodelbasedonvariational levelset method[J]. Application Research of Computers,2018,35(4):1254-1257.)   
[12]刘震，王艳宾，白丽丽，等．曲面细节特征保持的三维模型孔洞修复 方法[J].计算机辅助设计与图形学学报，2016,28(12):2052-2059. (Liu Zhen,Wang Yanbin,BaiLili,etal.Detail-preserving hole-filling for complex 3D models [J]. Journal of Computer-Aided Design & Computer Graphics,2016,28(12): 2052-2059.)   
[13] Pauly M，GrossM,Kobbelt L P. Efficient simplification of point-sampled surfaces [C]/Proc of Conference on Visualization. Washington DC:IEEE Computer Society,2002: 163-170.   
[14] Koenderink JJ, Van Doorn AJ. Surface shape and curvature scales [J]. Image and vision computing,1992,10(8): 557-564.   
[15] Sanchez G, Branch J W,Atencio P.A metric for automatic hole characterization [C]/Proc of the 19th International Meshing Roundtable. Berlin:Springer,2010: 195-208.   
[16] Caticha A.Lectures on probability,entropy，and statistical physics [C]//Proc of International Workshop on Bayesian Inference& Maximum Entropy Methods in Science & Engineering.2008.   
[17] Ohtake Y, Belyaev A, Seidel H P. Ridge-valey lines on meshes via implicit surface fiting [J].ACM Transon Graphics,2004，23(3): 609-612.   
[18] Hildebrandt K,Polthier K，Wardetzky M. Smooth feature lines on surface meshes [C]/Proc of Symposium on Geometry Processing. 2005: 85-90.   
[19]张洁，岳玮宁，王楠，等．三角网格模型的各向异性孔洞修补算法 [J].计算机辅助设计与图形学学报,2007,19(7):892-897.(Zhang Jie, Yue Weining,Wang Nan,et al. Anisotropic hole filing algorithm for triangle mesh models [J]. Journal of Computer-Aided Design& Computer Graphics,2007,19(7): 892-897.)   
[20] Huang Hui, Yin Kangxue,Gong Minglun,et al. "Mind thegap": tele-registration for structure-driven image completion [J].ACM Trans on Graphics,2013,32(6): 174:1-174: 10.   
[21] Hormann K. Theory and applications of parameterizing triangulations [D].Erlangen: University of Erlangen,2001.