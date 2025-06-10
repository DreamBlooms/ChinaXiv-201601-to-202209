# 基于语义参数的三维复杂模型变形方法研究

孙霞，何坤金

(河海大学 物联网工程学院，江苏 常州 213022)

摘要：针对含有自由曲面的三维模型不易变形的问题，提出一种基于语义参数的三维复杂模型变形方法，旨在实现三维模型的快速设计。该方法利用变形控制点作为模型变形的基本元素，通过设置语义参数实现层次化变形：以变形控制点带动分组部件变形，以分组部件促进三维模型整体变形。首先，采用 Hausdorff 测距法和均值聚类法，将已分组的电动车的自由曲面替换成二次曲面；然后，根据变形控制点间及与部件顶点的关系，计算各分组部件内部和外部的约束条件；最后，编辑修改定义在变形控制点上的语义参数，实现模型自定义变形。以电动车三维模型验证实验，结果表明，本方法支持用户通过修改少量语义参数对模型变形，有效提升三维模型个性化设计的效率。

关键词：聚类分析；二次曲面；部件约束；语义参数 中图分类号：TP391.72 doi:10.3969/j.issn.1001-3695.2018.03.0233

# 3D complex models deformation based on semantic parameters

Sun Xia, He Kunjin† (College ofIOT Engineering,Hohai University,Changzhou Jiangsu 213022,China)

Abstract: This paper developed a method about 3D complex models deformation based on semantic parameters to quickly design the 3Dcomplex models,which could solve the problem that 3D models including fre-form surfaces havedificult in deformation.This methodregarded deformation handlesas basicelements,then,byseting the semantic parameters realized thehierarchicaldeformation:the deformationof components byconfiguringthe deformation handlecan makethe 3Dmodels redesigned.First,thequadric surfaces replaced the freform surfaces of each component with Hausdorffdistance and the clusteranalysis method.Then,therelationship between deformation handlesandvertices of each component helped to calculate theconstraintsoftheinteraland extealcomponents.Finally,editingand modifing thesemanticparametersofthe deformation handles deformed 3Dmodels.Experimental results whichuse3Delectrombileas an example show thattheabove method support users achieve the deformation of3D models witha few parameters and keep beter eficiencyof personalized design.

Key words: cluster analysis; quadric surface; component constraint; semantic parameter

# 0 引言

自从1985年第一辆电动车的诞生至今，中国成为轻型电动车最重要的市场。目前，为满足大众的需求和追求电动车销量的稳定，设计者只根据大部分人的审美倾向，选择需求设计电动车。伴随着产品同质化日益增长的趋势，消费者不再满足于接受企业已有的产品，更希望将自己的想法融入到产品设计中。但产品设计要求设计者不仅熟悉底层的曲面造型技术，而且要具有熟练的几何操作技能。因此，鉴于现存的电动车三维模型，研究电动车自由曲面的替换方法和分组部件间的制约关系，使用户通过修改少量的语义参数，实现模型直观快速的变形，使产品的概念化设计面向大众化。

近年来，国内外学者对三维模型变形技术展开了相关研究，并取得了一定成果。Yumer等人错误!未找到引用源。通过设定变形handles，使用户自由选择三维模型变形方向，但不适用于由复杂多边形构成的模型；朱丹墨等人错误!未找到引用源。提出了一种基于特征语义的汽车原型快速生成的方法，但特征语义参数有限，不能涵盖体量特征语义的各个方法面；何坤金等人错误!未找到引用源。提出一种自由曲面特征参数分层实现框架，用户能从特征语义层直观地编辑修改自由曲面特征，但未能健全框架层次间的约束关系，随后在此基础上，提出一种基于特征线的曲面模型局部区域重构与特征化方法错误!未找到引用源。，虽能编辑修改局部曲面区域，但无法自动添加约束线；Yumer 等人错误未找到引用源。提出使用一组语义属性来创建几何变形的方法，但种类过多的语义属性可能导致变形模式失效；Demisse 等人错误!未找到引用源。提 提出基于n维曲面形状空间的变形方法，对局部形状的移位、重叠有较好的鲁棒性，但计算代价较高；Liu 等人错误:未找到引用源。提出基于地标深度估计和形状变形的模型重建方法，能得到较为真实的三维模型，但三维地标估计的精度会影响细节丰富的区域；蒋波等人错误!未找到引用源。提出基于 Delaunay 背景图改进的网格变形方法，提高网格变形的质量与效率。

另一方面，在三维模型变形的同时也考虑到保持其原有的几何细节。许斌等人错误!未找到引用源-提出一种基于 Laplacian 坐标的网格模型全局优化算法，网格质量和模型几何细节有较好的保证，但本算法仅适用于STL文件的模型，随后，一种基于局部刚性约束的变形算法被提出错误!未找到引用源。，解决了大规模角色模型变形过程中关节部位出现失真的问题，但算法复杂度会随着骨架嵌套模型的复杂度增加；张湘玉等人错误:未找到引用源·提出基于细分的骨架驱动网格模型变形方法，适用于几何信息丰富的复杂模型，但构建的控制网格不能很好贴合模型表面形状；Dai等人错误!未找到引用源。通过提取一个数据驱动的形状描述符，解决了三维模型在结构变形时产生的变化和噪声，其鲁棒性在变形程度较大时也较好。

虽然定制产品已面向市场，但无论是产品的大批量定制或私人定制，在设计过程中或存在耗时费力且定制价格昂贵错误!未找到引用源。，或存在缺乏高层语义参数且产品外观不能实时显示等缺陷。因此，本系统基于模型的各分组部件，设定功能不同的变形控制点和分组部件内部、外部的约束条件，并为用户提供了自定义变形的操作接口，便于用户通过高层语义参数直观地编辑修改变形控制点的三维信息，实现模型层次化的变形。以电动车为变形模型对本系统所提方法进行验证，主要包括基于电动车各分组部件的自由曲面的替换、三种类型变形控制点的设定以及变形过程中约束条件的计算。

# 1 电动车参数化变形框架

基于语义参数的三维复杂模型变形过程一般包括替换模型的自由曲面、设定变形控制点、计算分组部件内部和外部约束以及参数化控制点等，其流程如图1所示。

![](images/5fd7bb1a85829e55008d3ae6cd6f56d4a4efd245b8f9da392edbd66dd1bb14ee.jpg)  
图1电动车参数化变形

根据上述设计流程，电动车参数化变形步骤如下：

a)导入已有电动车模型，对模型曲面简化和分组;

b)对各分组部件曲面聚类，替换构成电动车的自由曲面为二次曲面；

c)建立约束条件，包括设定变形控制点及分组部件的内部和外部约束；

d）参数化变形控制点实现电动车变形。

其中，b)和c为本文研究的主要内容。通过以上流程生成简化电动车模型（由二次曲面构成)，将不同类型的变形控制点置于相应的分组部件上，并在各分组部件内部、外部建立约束关系，有效规范电动车变形的结构，通过编辑修改语义参数，实现电动车模型的自定义变形。

# 2 简化电动车模型生成

对电动车三维模型精简和分组后，将电动车分为车头、车座、车身、前车轮及后车轮五个部分。首先，分别对构成每个分组部件的子曲面聚类，再对子曲面类进行二次聚类，便于将几何信息相似的曲面归为一类；然后，判别曲面类中的自由曲面属于平面、球面、圆柱面等二次曲面的可能性，并将自由曲面替换为二次曲面。

# 2.1基于自由曲面的聚类

每个分组部件都由多个自由曲面构成，为收集自由曲面的特征信息需要对曲面的类别进行判别。通过子曲面聚类将具有较高相似性的曲面归为一类，并在此基础上通过均值漂移聚类将几何特征信息相符的曲面重新聚类。

# 2.1.1子曲面聚类

本文利用 Hausdorff 测距法错误!未找到引用源。判别每个分组部件中子曲面的两两相似性。Hausdorff距离是描述两组点集之间相似程度的一种量度，指某一集合中离另一集合最近点的所有距离最大值。本文利用Hausdorff 测距方法分别对车头、车座、车身、前车轮、后车轮五个分组部件包含的曲面进行相似性比较。选择一个分组部件中任意两个曲面 $A , \ B$ ，计算两曲面的Hausdorff 距离 $H ( A , B )$ ，并与设定阈值 $D$ 比较。当 $H ( A , B ) < D$ 时，则认为曲面 $A$ 、 $B$ 相似，可以归为一类。Hausdorff 距离的数学描述定义为

$$
H ( A , B ) = \operatorname* { m a x } ( h ( A , B ) , h ( B , A ) )
$$

$$
h ( A , B ) = \operatorname* { m a x } _ { a \in A } \operatorname* { m i n } _ { b \in B } \left\| a - b \right\|
$$

$$
h ( B , A ) = \operatorname* { m a x } _ { b \in B } \operatorname* { m i n } _ { a \in A } \left\| b - a \right\|
$$

其中： $a , b$ 分别为曲面 $A$ 和 $B$ 的顶点位置信息。本文定义阈值 $D$ 的计算方法为

$$
D = ( h ( A , B ) + h 1 ( A , B ) + h ( B , A ) + h 1 ( B , A ) ) / 4
$$

$$
h 1 ( A , B ) = \operatorname* { m i n } _ { a \in A } \operatorname* { m i n } _ { b \in B } \left\| a - b \right\|
$$

$$
h 1 ( B , A ) = \operatorname* { m i n } _ { b \in B } \operatorname* { m i n } _ { a \in A } \left\| b - a \right\|
$$

电动车每个分组部件（如车身）在子曲面初次聚类后，得到几个不同的子曲面类 $c { = } \{ c _ { l } , \ c _ { 2 } , \ c _ { 3 } . . . c _ { m } \}$ ，计算 $c _ { m }$ 类中描述每个子曲面的特征信息 $\scriptstyle x = \left. e _ { I } , e _ { 2 } , e _ { 3 } , { \pmb { n } } , k \right.$ 。其中 $e _ { I } , e _ { 2 } , e _ { 3 }$ 为描述某一子曲面顶点分布信息的主成分向量； $\textbf { \em n }$ 为描述某一子曲面的法向量; $k { = } \{ k _ { I } , k _ { 2 } , k _ { 3 } , k _ { I } > k _ { 2 } > k _ { 3 } \}$ 为描述某一顶点 $j$ 的高斯曲率，其

根据Gauss-Bonnet定理计算：

$$
\iint _ { A } k d A r = 2 \pi - \sum _ { j } \theta _ { j }
$$

其中： $A r \mathrm { ~ , ~ } \theta _ { j }$ 分别为与顶点 $j$ 相关的所有三角面片的面积和及其所在夹角的角度和。将某一子曲面所有顶点的高斯曲率作为统计数据，组数为10，统计分布情况， $k _ { I }$ 、 $k _ { 2 }$ 、 $k _ { 3 }$ 为直方图中对应频数最高的组距内的高斯曲率的平均值。以含有15个自由曲面的车头部件为例，根据Hausdorff 测距法得到3个不同的子曲面类 $c { = } \{ c _ { I } , \ c _ { 2 } , \ c _ { 3 } \}$ ，其中 $\boldsymbol { c } _ { I }$ 、 $c _ { 2 }$ ， $\mathbf { \sigma } _ { c _ { 3 } }$ 分别包含3、4、8个自由曲面。表1所示为子曲面类 $c _ { I }$ 中各自由曲面的特征信息，其中，文中所有概率均保留小数点后二位。

$$
C _ { i } ^ { c } = \frac { 2 ( \sigma _ { 2 } - \sigma _ { 3 } ) } { \sigma _ { 1 } + \sigma _ { 2 } + \sigma _ { 3 } }
$$

表1c1中各自由曲面的特征信息  

<html><body><table><tr><td>e1,e,e3</td><td>n</td><td>k1,k,k</td></tr><tr><td>-0.52.0.17,0.84</td><td></td><td></td></tr><tr><td>0.80,0.27,0.54</td><td>0.90,0.50,0.00</td><td>-0.90,-0.10,-0.30</td></tr><tr><td>0.31,-0.94,0.00</td><td></td><td></td></tr><tr><td>0.00,-1.00.0.00</td><td></td><td></td></tr><tr><td>1,00,0.00,0.00</td><td>-0.10,-0.10.0.00</td><td>-0.30,-0.90,-0.10</td></tr><tr><td>0.00,0.00,-1.00</td><td></td><td></td></tr><tr><td>0.28,-0.40,-0.87</td><td></td><td></td></tr><tr><td>-0.96,-0.13,-0.25</td><td>0.30,-1.00,0.00</td><td>-0.50,-0.80,-0.20</td></tr><tr><td>-0.18,0.90,-0.42</td><td></td><td></td></tr></table></body></html>

其中：某一曲面类 $C _ { n }$ 中包含曲面个数为 $n$ ； $C _ { n }$ 中任意曲面 $i$ 点集的标准偏差为 $\sigma _ { 1 } , \sigma _ { 2 } , \sigma _ { 3 } , \sigma _ { 1 } > \sigma _ { 2 } > \sigma _ { 3 }$ 。如果 $P _ { p } > = 0 . 9$ 或 ${ \cal P } _ { s } { \displaystyle > } = 0 . 9$ 或 $P _ { c } > = 0 . 9$ ，则该曲面类 $C _ { n }$ 中所有曲面以计算所得最高概率的二次曲面特征呈现；如果 $P _ { p } { < } 0 . 9$ ， $P _ { s } { < } 0 . 9$ ， $P _ { c } { < } 0 . 9$ ，则该曲面类 $C _ { n }$ 中的所有曲面维持其原有自由曲面特征。以车头部件为例，计算曲面类 $C { = } / C _ { I } , \ C _ { 2 } .$ ， $C _ { 3 } \}$ 包含自由曲面的点集的标准偏差。例如，曲面类 $C _ { I }$ 中包含三个自由曲面点集的标准偏差为$\sigma _ { 1 } = \{ 0 . 1 3 , 0 . 0 9 , 0 . 1 3 \}$ （204 ， $\sigma _ { 2 } = \{ 0 . 1 0 , 0 . 0 0 , 0 . 6 0 \}$ $\sigma _ { 3 } = \{ 0 . 0 9 , 0 . 0 0 , 0 . 0 5 \}$ ，根据 $P _ { p } { = } 0 . 9 9$ ， $\scriptstyle P _ { s } = 0 . 4 8$ ， ${ P _ { c } } \mathrm { = } 0 . 6 6$ ，确定曲面类 $C _ { I }$ 中的自由曲面以平面代替。图2表示电动车各分组部件的自由曲面被替换成二次曲面后，形成的简化电动车模型。

2.1.2均值漂移聚类

分别对电动车五个分组部件二次聚类。首先，将某一分组部件的子曲面类 $c { = } \{ c _ { I } , c _ { 2 } , c _ { 3 } { \ldots } c _ { m } \}$ 作为待聚类的类别；其次，根据均值偏移算法错误!未找到引用源；计算子曲面类二次聚类的类别$\scriptstyle  C = \{ C _ { I }$ ， $C _ { 2 }$ ， $\displaystyle C _ { 3 \ldots } C _ { n } \}$ 。均值偏移向量的数学描述定义为

$$
m ( x ) = { \frac { \displaystyle \sum _ { x _ { i } \in N ( x ) } e ^ { - \| x _ { i } - x \| } \cdot x _ { i } } { \displaystyle \sum _ { x _ { i } \in N ( x ) } e ^ { - \| x _ { i } - x \| } } }
$$

其中： $m ( x )$ 为均值漂移向量； $x$ 为某一子曲面的15 维特征量;$N ( x )$ 为 $x$ 的邻域； $x _ { i }$ 为 $N ( x )$ 中任意向量。当 $m ( x )$ 收敛到足够小时，如果当前 $N ( x )$ 的中心值与已存在的另一个类的中心值的距离足够小，则将两者归为一类；反之， $N ( x )$ 作为新的聚类。基于子曲面类 $\boldsymbol { c }$ 的均值漂移算法，得到曲面类 $C { = } { \{ } C _ { I } ,  \subset { _ { 2 } , } \subset { _ { 3 } } { \quad }$ 其中 $C _ { I }$ 、 $C _ { 2 }$ 、 $C _ { 3 }$ 分别包含3、4、8个自由曲面。

# 2.2基于二次曲面的替换

电动车某一分组部件（如车身）在曲面聚类后生成曲面类$C { = } { \{ } C _ { I } , ~ C _ { 2 } , ~ C _ { 3 } { \ldots } C _ { n } { \} }$ ，将曲面类中包含的自由曲面替换为二次曲面，有利于根据二次曲面特征设定带语义参数的变形控制点。计算某一曲面类 $C _ { n }$ 属于平面概率 $P _ { p }$ 、球面概率 $P _ { s }$ 、圆柱面概率 $P _ { c }$ 等二次曲面的可能性，根据判别公式：

$$
P _ { p } = \sum _ { i } ^ { n } \frac { C _ { i } ^ { p } } { n } , P _ { s } = \sum _ { i } ^ { n } \frac { C _ { i } ^ { s } } { n } , P _ { c } = \sum _ { i } ^ { n } \frac { C _ { i } ^ { c } } { n }
$$

$$
C _ { i } ^ { p } = \frac { 2 ( \sigma _ { 1 } - \sigma _ { 3 } ) } { \sigma _ { 1 } + \sigma _ { 2 } + \sigma _ { 3 } } , C _ { i } ^ { s } = \frac { 3 \sigma _ { 3 } } { \sigma _ { 1 } + \sigma _ { 2 } + \sigma _ { 3 } } ,
$$

LO

# 3 基于点云模型的约束生成

根据待变形的分组部件，定义三种类型的变形控制点于各分组部件的二次曲面上。计算各分组部件内部、外部的约束条件，提高电动车变形的合理性。

# 3.1变形控制点的分类

在简化电动车模型的各分组部件上设定不同类型的变形控制点。图3为位于五个分组部件的变形控制点。各分组部件的变形控制点用不同的形状表示（如用圆点表示位于车身上变形控制点)。本文根据变形控制点在电动车模型变形时发挥的不同作用将其分为三类：

a)用户编辑控制点，即用户操作电动车变形的点，包含定义的语义参数，其根据用户对电动车外观变形的需求自动选择。b)系统固定控制点，即自动保持模型固定的点，其与用户编辑控制点具有全局对称性，用于减少用户标记固定点的次数。c)系统操纵控制点，即系统自动实现分组部件变形的点，由用户编辑控制和系统控制点共同决定。其位置更新的最优化方程为

$$
{ \mathrm { m i n i m i z e } } \sum _ { i } ^ { N } { \frac { 1 } { \nu _ { j } } } { \Big | } m _ { j } - s _ { j } { \Big | } , { \mathrm { s u b j e c t ~ t o } } t _ { j } = u _ { j } , \forall t _ { j } \in T
$$

其中： $s _ { i }$ 为方程求解的数值，即系统操纵控制点的更新位置； $N$ 为系统操纵控制点的个数； $T$ 为某一分组部件能够发生变形( $X$ ，

Y、Z轴上平移、旋转、缩放）的类型； $t _ { j }$ 为任一种变形类别;$u _ { j }$ 为用户指定部件发生变形的类别； $m _ { i }$ 、 $\mathbf { \sigma } _ { \nu _ { i } }$ 分别为系统操纵控制点所操纵区域顶点信息的均值和方差。

马

# 3.2基于待变形分组部件约束的设定

由局部（如车身部件）到整体（电动车）的变形设计，涉及到单个分组部件内部的约束限定和不同分组部件间的约束限定，以此保证电动车有序变形。当某个分组部件 $M$ 发生变形时，本文中定义部件内部约束条件限定该分组部件 $M$ 内部的变化范围，部件外部约束条件为其他分组部件内部的约束条件及 $M$ 对其他分组部件 $\scriptstyle M M = \{ M _ { I }$ ， $M _ { 2 }$ ， $M _ { 3 } . . . M _ { n } { \rangle }$ 的影响。假设车身为待变形的分组部件 $M$ ，则 $\scriptstyle M M = \{ M I$ ， $M _ { 2 }$ ， $M _ { 3 }$ ， $M _ { 4 } { \it ) }$ 分别对应于车头、车座、前车轮和后车轮部件。图4表示车身部件变形内部和外部约束条件，其中图4(a1)为电动车点云模型，4(a2)为电动车点云与曲面相结合模型。为便于变量在图上的标记，示例图以曲面模型展示。

# 3.2.1待变形部件内部约束

图4(b)为车身部件内部约束。以车身部件的重心分别划分用户编辑控制点 $e$ 、系统固定控制点 $a$ 的影响域为Areal、Area2，根据 $D _ { ( e , \ p i ) } { = } \parallel e - p _ { i } \parallel$ 计算点 $\mathbf { \Psi } _ { e }$ 对影响域 Area 中某顶点 $p _ { i }$ 的影响因子 $k$ ，从而得到 $p _ { i }$ 的新位置 $p _ { n e w }$ 。其中， $D _ { ( e }$ ， $p i )$ 为点 $e$ 和 $p _ { i }$ 间的距离。本文定义用户编辑控制点 $\boldsymbol { \mathscr { e } }$ 对某顶点 $p _ { i }$ 的约束条件 $F _ { ( e , p i ) }$ 分为三种类型：a)当 $D _ { ( e }$ ， $_ { p i ) } { < } 0 . 1$ 时，则 $k { = } 1$ ， $p _ { n e w } { = } p _ { i }$ b)当 $0 . 1 { < } D _ { ( e }$ ， $_ { p i ) } < 1$ 时，找出 $D _ { ( e }$ ， $p i )$ 在此范围内的最小距离 $D _ { m i n }$ 和最大距离 $D _ { m a x }$ ，则 $k { = } 1 / \left( D _ { m i n } { + } D _ { m a x } \right)$ ， $p _ { n e w } { = } p _ { i } { + } t e m p { \cdot } k ;$ ：c）当$D _ { ( e }$ ， $_ { p i ) } { > } 1$ 时， $k { = } 1 /$ D(e, $p i )$ ， $p _ { n e w } { = } p _ { i } { + } t e m p { \cdot } k$ 。同理，可得点 $\mathbf { \Delta } _ { a }$ 对 $A r e a _ { 2 }$ 中某顶点 $p _ { i }$ 影响后的位置 $p _ { n e w }$ 。

# 3.2.2待变形部件外部约束

![](images/263bb06372c8b4d72fc8edeee4c7925c491035a42a3c7fe4265fe8c578f762c7.jpg)  
图3简化电动车模型的变形控制点

以增长车身长度为例，计算电动车变形控制点 $\scriptstyle p = \{ e , a , E \}$ $E { = } { \{ E _ { I } , ~ E _ { 2 } , ~ E _ { 3 } , ~ E _ { 4 } \} }$ 间的约束，即其他分组部件内部约束条件。如图4(c)所示的不同分组部件上的变形控制点，其中，位于车身部件的点 $\mathbf { \Psi } _ { e }$ 为用户编辑控制点，点 $\mathbf { \Delta } _ { a }$ 为系统固定控制点， $E$ 为系统操纵控制点的集合，位于车头、车座、前车轮、后车轮部件上的系统操纵控制点分别对应于 $\scriptstyle { E _ { I } = { \big / } e _ { I I } }$ ， $e _ { I 2 }  \big \}$ ， $\boldsymbol { E _ { 2 } } \mathrm { = } \{ \boldsymbol { e _ { 2 I } }$ $e _ { 2 2 } \boldsymbol { \jmath }$ ， $\boldsymbol { E _ { 3 } } \mathrm { = } \{ \boldsymbol { e _ { 3 } } \}$ ， $\scriptstyle { E _ { 4 } = { \big / } e _ { 4 } } \rangle$ 。根据式(5)得到 $\scriptstyle { E = } ( e _ { I I }$ ， $e _ { I 2 }$ ， $\boldsymbol { e } _ { 2 I }$ ， $e _ { 2 2 }$ ，$\scriptstyle { e _ { 3 } }$ ， $\boldsymbol { e } _ { 4 } \boldsymbol { \jmath }$ 的变化值。以车座部件 $M _ { 2 }$ 为例，按其重心划分 $\boldsymbol { e } _ { 2 I }$ ， $e _ { 2 2 }$ 的影响域分别为Area21、Area22，位于不同影响域中的顶点随着对应系统操纵点的变化，按相同约束带动车座部件变形。同理，其他分组部件将会根据各自约束变形。

在相邻分组部件间建立制约能有效降低变形过程中发生重叠、悬空等现象。设定相邻分组部件间约束步骤包括：a）计算$M$ 对相邻分组部件的影响区域 $E A = \{ E A _ { l } , ~ E A _ { 2 } , ~ E A _ { 3 } . . . E A _ { n } ~ \}$ ，其中 $M$ 对 $M _ { I }$ ， $M _ { 2 }$ ， $M _ { 3 } . . . M _ { n }$ 的影响区域分别对应于 $E A _ { I }$ ， $E A _ { 2 }$ .$E A _ { 3 }$ ，： $. . E A _ { n }$ ；b）计算影响区域 $E A _ { n }$ 中的任意顶点 $p _ { i }$ 与位于 $M$ 上的变形控制点间的约束条件；c）根据步骤b）约束条件，得到影响区域 $E A _ { n }$ 中 $p _ { i }$ 点变形后的新位置。

以车身部件 $M$ 对车座部件 $M _ { 2 }$ 的影响为例。首先根据 $M$ 与$M _ { 2 }$ 的三维重叠空间得到影响域 $E A _ { 2 }$ ；其次根据用户编辑控制点对某顶点 $p _ { i }$ 的约束条件 $F _ { ( e , \ p i ) }$ ，分别得到点 $\textit { e , a }$ 与位于影响域$E A _ { 2 }$ 上的点 $p _ { i }$ 的约束条件。同理，可得车身部件 $M$ 与车头 $M _ { I }$ 、前车轮 $M _ { 3 }$ 、后车轮 $M _ { 4 }$ 部件间的约束条件。图4(d)所示车身部件增长temp距离，得到的变形后的电动车模型。

A

![](images/836b6ff358cd21c85d1a8c46acb8dbb69fee5fde8149ab4ad5877ac8cfb327c2.jpg)  
(a1）电动车点云模型  
(a2）点云与曲面模型结合  
(b）车身部件内部约束

![](images/f1da30a4d60c7737077e5fd49382cabd0db0aa5178b883ade9789be3895c17de.jpg)

(d）车身部件增长temp后的电动车模型

# 4 实例

本文所提出的方法在VS2010 和Unity5.5.3平台上进行了实例测试。下面以对前车轮部件和车座部件变形为例，说明自定义参数的电动车变形。

图5为电动车模型的前车轮部件参数化。首先，通过曲面替换得到五个分组部件的简化模型，设定用户编辑控制点e于待变形的前车轮部件，如图5(a)所示，其中 $p _ { i }$ 为车轮部件上任一点， $\textbf {  { D } }$ 为点 $\boldsymbol { \mathscr { e } }$ 到 $p _ { i }$ 的向量，R为车轮部件初始半径；其次，根据前车轮的二次曲面的特殊性，通过 $p _ { n e w } { = } p _ { i } + D ^ { * } R I$ 得到半径增加R1后的车轮部件，如图5(c)所示；然后，根据式(5)，得到位于其他分组部件上系统操纵控制点的更新位置，实现其他分组部件的变形。同时，根据前车轮部件的三维空间，得到图5(b)所示的对车身部件的影响区域，以黑色方框圈出，将前车轮部件内部约束关系应用到其对影响域中的车身局部部件的制约，计算此影响域中车身部件变形时的约束，避免两者发生穿透或错位的情况；最后，编辑修改定义在点 $\boldsymbol { \mathscr { e } }$ 上的语义参数，使车轮部件增大的同时带动其他分组部件的改变，实现电动车层次化变形，如图5(d)所示。

![](images/ef5e99a8f1b556f3c57f64df863fdbb5ed047da4d94bf991a42034385133fa91.jpg)  
图4车身部件变形的内部和外部约束条件

![](images/a5a1598d296e75b16fe0617e34529f0f333d118d89a46a64565933d76503c7fa.jpg)

图5电动车模型的前车轮部件参数化

图6为电动车模型的车座部件参数化。根据文中方法得到电动车简化模型并设定不同功能的变形控制点于各分组部件上，即设定用户编辑控制点 $e$ 、系统固定控制点 $\mathbf { \Delta } _ { a }$ 于车座部件,如图6(a)所示， $D _ { ( e , p i ) }$ 为点 $\boldsymbol { \mathscr { e } }$ 到 $p _ { i }$ 的距离， $L$ 为车座部件初始长度。首先，以车座部件重心划分点 $\textit { e , a }$ 的影响域，分别根据点$\boldsymbol { \mathscr { e } }$ 及点a对各自影响域中点 $p _ { i }$ 的约束条件得到长度增加 $L I$ 的车座部件，如图6(c)所示；其次，根据式(5)，计算位于其余分组部件上的系统操纵控制点的更新位置，实现车头、车身、前车轮和后车轮部件的变形；然后，用文中所提计算外部约束的方法，得到位于影响域中车身部件变形的约束条件，确保两者变形过程中的紧密贴合，影响域以车座部件的三维空间划分，以黑色方框圈出，如图6(b)所示；最后，修改带有语义参数的用户编辑点的信息，使车座部件的增长的同时实现电动车整体变形，如图6(d)所示。

![](images/39e70e9301bc668ce5dfb9fcd59dca45e5d379296e68da9eb6f3dcd61734f122.jpg)  
(d)改变前车轮部件半径后的电动车模型   
(c）改变车座部件长度

山

在电动车参数化变形过程中，用户通过修改定义在用户编辑控制点的语义参数，以分组部件的变形带动电动车整体变形，简化了复杂电动车模型变形设计的过程。

# 5 结束语

在现有电动车三维模型的基础上，本文提出了一种基于语义参数的三维复杂模型变形方法。该方法将构成电动车的自由曲面替换成规则的二次曲面，有效地解决了由自由曲面构成的复杂模型不易变形的问题。通过建立原模型到目标模型的约束关系，包括变形控制点间的约束、待变形分组部件内部、外部的约束，实现电动车模型有序化、层次化的变形。但是在电动车的分组过程中还难以做到自动分组，且本文定义的约束条件有限，难以满足在电动车每个零件间建立制约条件，因而电动车细节部分的变形存在不足，这将在今后的工作中有待进一步研究和完善。

# 参考文献：

[1]Yumer ME,Kara L B.Co-constrained handles for deformation in shape collections [J].Association for Computing Machinery Transactions on Graphics,2014,33 (6): 1-11.   
[2]朱丹墨，陆洋，徐鑫，等．基于特征语义的汽车原型快速生成方法 [J]. 系统仿真学报,2013,25(9):1990-1995.(Zhu Danmo,Lu Yang,Xu Xin, et al,Rapid car-body prototype generation method based on feature semantics [J]. Journal of System Simulation.2013,25 (09): 1990-1995.)   
[3]何坤金，赵宗星，耿维忠，等．层次参数化的自由曲面特征表示与实现 [J]．计算机辅助设计与图形学学报，2014,26(5):826-834.(He Kunjin, Zhao Zongxing,Geng Weizhong，et al.Parametric representation and implementation of freeform surface feature based onlayered parameters [J] Journal of Computer-Aided Design and Computer Graphics.2014,26 (5): 826-834.)

[4] 何坤金，王淋，陈正鸣，等．基于CAD 曲面模型的局部区域重构与特 征化[J]．计算机集成制造系统，2014,20(10):2360-2368.(He Kunjin, Wang Lin,Chen Zhengming,et al.Reconstruction and featurization of local region based on CAD surface models [J].Computer Integrated Manufacturing System.2014,20 (10): 2360-236.)

[5]Yumer ME, Chaudhuri S, Hodgins JK,et al. Semantic shape editing using deformation handles[J].Association for Computing Machinery Transactions on Graphics,2015,34 (4): 86.   
[6]Demisse G G,Aouada D,Ottersten B.Deformation based curved shape representation[J]. IEEE Trans onPattrn Analysis & Machine Intellgence, 2017, PP (99): 1-1.   
[7]Liu P, Hong M,Wang M,et al.3D face reconstruction via landmark depth estimation and shape deformation [J].Multimedia Tools & Applications, 2017,76 (2): 2749-2767.   
[8]蒋波，朱目成，曾磊，等．一种基于Delaunay 背景图改进的网格变形方 法[J/OL].计算机应用研究，2018，35(4).(2017-03-31)[2017-03-31]. http://www.arocmag.com/article/02-2018-04-005. html. (Jiang Bo, Zhu Mu cheng, Zeng lei,et al. Improved mesh deformation method based on Delaunay background map [J/OL].Application Research of Comtuters. 2018，35(4）．(2017-03-31） [2017-03-31].http://www.arocmag. com/article/02-2018-04-005. html. )   
[9]许斌，李虑科．基于STL文件的Laplacian 网格优化算法[J].计算机应 用研究，2013,30(5):245-248.(Xu bin,Li1u ke.Laplacian mesh optimization algorithm based on STL file[J].Application Research of Computers,2013,30 (5): 245-248)   
[10]许斌，于勇，谭营．基于局部刚性约束的微分网格变形算法[J].计算 机应用研究，2015，32(5):1580-1585.(Xubin，Yu Yong，Tan Ying. Differential mesh deformation algorithm based on local rigidity constraint [J].Application Research of Computers.2015 (5): 1580-1585.)   
[11]张湘玉，李明，马希青．基于细分的网格模型骨架驱动变形技术[J]. 计算机应用,2015,35(3):811-815.(Zhang Xiangyu,Li ming,Ma Xiqing. Skeleton-driven mesh deformation technologybased on subdivision[J], Journal of Computer Applications.2015,35 (3): 811-815.)   
[12]Dai G, Xie J, Zhu F,et al.Learning a discriminative deformation-invariant 3Dshape descriptor via many-to-one encoder☆ [J].Pattern Recognition Letters,2016,83: 330-338.   
[13]田保珍，余隋怀，王淑侠，等．多约束条件下定制产品模块划分方法 [J].计算机工程与应用，2016，52(19):234-240.(Tian Baozhen，Yu Suihuai, Wang Shuxia,et al. Module partition method of multi-constrained for customized products [J]. Computer Engineering and Applications,2016, 52 (19): 234-240.)   
[14] Kim YJ,Oh Y T,Yoon SH,et al.Efficient Hausdorff distance computation for freeform geometricmodelsin closeproximity[J]. Computer-Aided Design,2013,45(2): 270-276.   
[15] Carreira-Perpi?an Miguel A.A review of mean-shift algorithms for clustering [J].arXiv: 1503.00687,2015.