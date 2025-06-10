# 基于粒子群算法的三维CAD模型相似性计算

高雪瑶‘，陈育南‘，张春祥b(哈尔滨理工大学 a.计算机科学与技术学院;b.软件学院，哈尔滨 150080)

摘要：为了更加准确地度量两个模型之间的形状差异，提出了一种基于粒子群的模型相似性计算方法。利用面的组成边数来构造面相似度矩阵，通过粒子群算法对该矩阵进行搜索，得到了两个模型之间的最优面匹配序列。根据这个最优面匹配序列，从面相似度矩阵中提取对应的面相似性值。通过累积面之间的相似性来计算模型之间的整体相似性。以此为基础来度量模型之间的差异。实验结果表明：该方法能够准确地度量两个模型之间的相似程度。

关键词：形状差异；模型相似性；粒子群算法；匹配序列 中图分类号：TP391.7 doi:10.3969/j.issn.1001-3695.2017.09.0961

# Similarity calculation of 3D CAD model based on particle swarm algorithm

Gao Xueyaoa, Chen Yunana, Zhang Chunxiangb (a.SchoolofComputer Science&Technology,b.SchoolofSoftware,Harbin UniversityofScience&Technology,Harbin 150080, China)

Abstract: Inorder tomeasure shape diffrenceof twomodelsaccurately,this paper proposeda method forcalculating model similarity basedon particle swarm.Itused edge numberoffaceto construct face similarity matrix,andused particle swarm algorithmto search this matrix to getanoptimal face matching sequencebetween two models. It extracted corrspondent face similarityvaluesacording tothis face matching sequencefromfacesimilarity matrix.This paperaccumulatedfacesimilarities to calculate two models'smilarityand measured shape diferenceoftwo models.Experimentalresults showthatthis method can evaluate similarity between two models accurately.

Key Words: shape difference; model similarity; particle swarm algorithm; matching sequence

# 0 引言

在三维CAD模型检索中，模型相似性计算起着重要的作用。它关系到模型检索的效率和可靠性。刘志通过获取三维模型较优视点集，来渲染三维模型的混合轮廓线视图。利用提取的Gabor边缘响应特征，去构建特征库。从特征库中，使用视觉词袋方法来检索相似的模型[1。范菁采用多层次局部视图对树木模型进行组合描述，根据视图所对应的树木语义信息，来实现视图特征的转换，从而完成由粗略到精细的多阶段检索[2]。庄廷建立了距离一余弦二维网格，通过获取网格中的随机点数量，来构建三维模型的距离-余弦联合形状分布矩阵。利用分布矩阵之间的 $\mathrm { L } _ { 2 }$ 距离来表示模型之间的相似度，并采用二进制粒子群优化算法来计算模型之间的相似性[3]。张开兴将两个自由曲面的相似性评价问题转换为两个曲面局部特征之间的相似性评价问题。利用自由曲面参数域内生成的曲率云图来提取类Sift 算子，通过比较局部特征的相似程度来评价自由曲面之间的相似性[4]。白静将各类非线性特征统一表示为属性图，利用非线性凝聚层次聚类算法来实现属性图聚类。同时，引入增量模型的动态归类方法，来实现三维CAD模型可重用区域的有效聚类[5]。Qin利用分层特征本体和本体映射，来生成语义描述符。以语义描述符为基础进行本体推理，使检索系统获得更好的性能[。Kim 给出了一种基于自由草图的建模方法。利用形状分布来比较多分辨率模型，使用简单的形状查询模型来提高检索精度[7]。Chen 给出了三个组合特征描述符和一个基于类的特征描述符，并将其应用于模型检索过程中[8]。Tao把面邻接图分割为凸、凹和平面区域，利用区域属性编码来表示面区域，通过比较区域属性编码来度量模型之间的相似性[9]。Jin通过推导拉伸形变能量的三维版本，结合固定边界条件，将表面参数化扩展到体积参数化，使其具有拉伸最小化的优点[10]。皇甫中民从模型的B-Rep表示中提取几何拓扑属性。利用属性邻接图来表示三维CAD模型，使用图谱来描述局部特征。同时，采用两层搜索机制来实现模型检索[11]。陈龙利用单元之间的拓扑信息，生成多个零亏格四边子域，并使用边界插值算法和内点优化算法来实现子域参数化[12]。潘万彬以区域之间的对应面和三维尺寸约束图为基础，将简单局部区域的形状和定位信息传播到可重用区域[13]。

本文利用面组成边数差异，来构建源模型与目标模型之间的面相似度矩阵。以面相似度矩阵为基础，使用粒子群算法来搜索源模型与目标模型之间的最优面匹配序列。以此为基础，计算源模型和目标模型之间的相似性。

# 1 源模型与目标模型之间的面相似性计算

模型是由多个面组成的。组成面的形状差异，造成了模型形状之间千差万别。在计算源模型与目标模型之间的相似性时，需要累积这两个模型面之间的相似性。如果模型之间面的组成边数差距很小，那么这两个模型的相似度就会很高；如果模型之间面的组成边数差异很大，那么这两个模型之间的相似度就很低。源模型A和目标模型B如图1所示。

![](images/a55935a4aaa5fc60160220311e430dd493d6c7170c22a892bd065c58221b0621.jpg)  
图1源模型A和目标模型B

源模型A包括七个面：面 $u _ { 1 }$ 、u2、 $u _ { 3 }$ 、u4、 $u _ { 5 }$ 、 $u _ { 6 }$ 和 $u _ { 7 }$ 。面$u _ { 1 }$ 与面 $u _ { 2 }$ 、 $u _ { 5 }$ 、 $u _ { 6 }$ 和 $u _ { 7 }$ 相邻接；面 $u _ { 2 }$ 与面 $u _ { 1 }$ 、 $u _ { 3 }$ 、 $u _ { 6 }$ 和 $u _ { 7 }$ 相邻接；面 $u 3$ 与面 $u _ { 2 }$ 、u4、 $u _ { 6 }$ 和 $u \ i$ 相邻接；面 $u _ { 4 }$ 与面 $u 3$ 、u5、u6和 $u _ { 7 }$ 相邻接；面 $u _ { 5 }$ 与面 $u _ { 1 } , u _ { 4 } , u _ { 6 }$ 和 $u _ { 7 }$ 相邻接；面 $u _ { 6 }$ 与面 $u _ { 1 }$ 、$u 2 、 u 3 、 u _ { 4 }$ 和 $u _ { 5 }$ 相邻接；面 $u _ { 7 }$ 与面 $u _ { 1 } \setminus u _ { 2 } \setminus u _ { 3 } \setminus u _ { 4 }$ 和 $u _ { 5 }$ 相邻接。面 $u _ { 1 }$ 有四个相邻面，因此，面 $u _ { 1 }$ 的边数为4。同理，可以计算出其他面的边数。面 $u _ { 2 }$ 、u3、 $u _ { 4 }$ 和 $u s$ 分别有四条边，面 $u 6$ 和 $u \ i$ 分别有五条边。

目标模型B包括七个面：面 $\nu _ { 1 }$ 、 $\nu _ { 2 }$ 、V3、V4、V5、 $\nu _ { 6 }$ 和 $\nu \tau$ 。其中，面 $\nu _ { 1 }$ 、V2、V3、 $\mathbf { \nu } _ { \nu 4 }$ 和 $\mathbf { \sigma } _ { \nu 5 }$ 是四边形，分别有四条边；面 $\nu _ { 6 }$ 和 $\nu _ { 7 }$ 是五边形，分别有五条边。

利用式(1)来计算源模型面 $u _ { i }$ 和目标模型面 $\nu _ { j }$ 之间的相似度 $S ( u _ { i } , \nu _ { j } )$ 。

$$
S ( u _ { i } , \nu _ { j } ) = 1 - \frac { \mid n u m ( u _ { i } ) - n u m ( \nu _ { j } ) \mid } { \operatorname* { m a x } ( n u m ( u _ { i } ) , n u m ( \nu _ { j } ) ) }
$$

其中： $n u m ( f )$ 表示模型面 $f$ 所包含的边数； $m a x ( x , y )$ 表示 $x$ 与 $y$ 之间的最大值。由公式(1)可以看出：若两个模型面所含的边数差异越小，则这两个面的形状就越相似。使用 $S ( u \mathrm { i } , \nu \mathrm { j } )$ 来构造源模型A与目标模型B之间的面相似度矩阵 ${ \pmb S } _ { \mathrm { A B } }$ ，其中： $m$ 表示源模型面数， $n$ 表示目标模型面数。如果 $\mid m \mid$ 大于 $n$ ，则将源模型与目标模型互换。即始终保持面相似度矩阵的行数要小于等于列数。

$$
S _ { A B } = \left[ \begin{array} { c c c c c c c } { { \nu _ { 1 } } } & { { \ldots } } & { { \nu _ { j } } } & { { \ldots } } & { { \nu _ { n } } } \\ { { } } & { { S ( u _ { 1 } , \nu _ { 1 } ) } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { S ( u _ { 1 } , \nu _ { n } ) } } \\ { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } \\ { { u ( \phantom { \mu } } } & { { \ldots } } & { { \ldots } } & { { S ( u _ { i } , \nu _ { j } ) } } & { { \ldots } } & { { \ldots } } \\ { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } \\ { { u ( \phantom { \mu } } } & { { S ( u _ { m } , \nu _ { 1 } ) } } & { { \ldots } } & { { \ldots } } & { { \ldots } } & { { S ( u _ { m } , \nu _ { n } ) } } \end{array} \right]
$$

其中：源模型的面序列号 $\boldsymbol { u } _ { 1 }$ 、 $u _ { 2 }$ 、、 $u _ { \mathrm { m } }$ ，作为面相似度矩阵的行标；目标模型的面序列号 $\nu _ { 1 } , \ \nu _ { 2 } , \ \dots \ \nu _ { \mathrm { n } }$ ，作为面相似度矩阵的列标。在面相似度矩阵 ${ \pmb S } _ { \mathrm { A B } }$ 中，源模型面 $u _ { \mathrm { i } }$ 和目标模型面vj之间的相似度值为 $S ( u \mathrm { i } , \nu \mathrm { j } )$ 。

源模型面与目标模型面之间的相似程度影响着两个模型之间的相似性。对于两个模型而言，如果它们的组成面越相似，那么这两个模型之间的相似度也就越高。如果它们的组成面差异越大，则这两个模型之间的相似度也就越低。

根据式(1)，构造源模型A与目标模型B之间的面相似度矩阵。在面相似度矩阵中，用源模型 A的面序号 $u _ { 1 }$ 、 $u _ { 2 }$ 、·$u \ i$ 表示行号，用目标模型B的面序号 $\nu 1 \setminus \nu 2 \setminus \dots \nu 7$ 表示列号。源模型A和目标模型B的面相似度矩阵如下所示：

在源模型A中，面 $u \mathrm { 1 }$ 与面 $u _ { 2 }$ 、u5、u6和 $u \ i$ 相邻接；在目标模型B中，面 $\nu _ { 1 }$ 与面 $\nu _ { 2 }$ 、V5、 $\nu _ { 6 }$ 和 $\nu \tau$ 相邻接。由式(1)可知，在源模型A和目标模型B的面相似度矩阵中，第 $u _ { 1 }$ 行第 $\nu _ { 1 }$ 列的值为1。在目标模型B中，面 $\mathbf { \sigma } _ { \nu 7 }$ 与面v1、V2、V3、 $\nu _ { 4 }$ 和 $\vert \nu \boldsymbol { 5 } ^ { }$ 相邻接。由式(1)可知，在源模型A和目标模型B的面相似度矩阵中，第 $u _ { 1 }$ 行第 $\mathbf { \Psi } _ { \nu _ { 7 } }$ 列的值为0.8。

# 2 基于粒子群算法的模型面匹配

如果两个模型的组成面越相似，则这两个模型之间的相似度也就越高。对于两个模型而言，其组成面之间存在着多种对应方案。本文以面相似度矩阵为基础，使用粒子群算法来搜索源模型面与目标模型面之间的最优匹配序列。根据最优面匹配序列，来计算两个模型之间的相似性。

在使用粒子群算法搜索面相似度矩阵的过程中，设定一个$d$ 维的搜索空间。种群的大小为 $p$ ： $x _ { t }$ 表示第 $t$ 个粒子的位置，即在面相似度矩阵中搜索到的列序号组成的向量; $\nu _ { t }$ 表示第 $\mathbf { \chi } _ { t }$ 个粒子的飞行速度；在第 $k$ 次迭代过程中，使用 $x _ { P b e s t , t } ^ { k }$ 表示第 $t$ 个粒子的个体最优位置，对应的适应度函数值为 fpbestt；利用$x _ { G b e s t } ^ { k }$ 表示全局最优位置，对应的适应度函数值为fGbest。利用$x _ { P b e s t , t } ^ { k }$ 和 $x _ { G b e s t } ^ { k }$ 来更新 $\boldsymbol { x } _ { t } ^ { k + 1 }$ 和速度 $\nu _ { t } ^ { k + 1 }$ ，其计算过程如式(2)和(3)所示。

$$
\boldsymbol { \nu } _ { t } ^ { k + 1 } = \boldsymbol { w } ^ { * } \boldsymbol { \nu } _ { t } ^ { k } + c _ { 1 } \boldsymbol { r } _ { 1 } ( \boldsymbol { x } _ { P b e s t , t } ^ { k } - \boldsymbol { x } _ { t } ^ { k } ) + c _ { 2 } \boldsymbol { r } _ { 2 } ( \boldsymbol { x } _ { G b e s t } ^ { k } - \boldsymbol { x } _ { t } ^ { k } )
$$

$$
\boldsymbol { x } _ { t } ^ { k + 1 } = \boldsymbol { x } _ { t } ^ { k } + \boldsymbol { \nu } _ { t } ^ { k + 1 }
$$

其中： $k$ 表示当前的迭代次数； $w$ 表示惯性权重； $c _ { 1 } , \ c _ { 2 }$ 为学习因子； $\boldsymbol { r } _ { 1 }$ 、 $r _ { 2 }$ 表示取值在[0,1]内的随机数。

在每次迭代过程中，为了使粒子向最好的位置进行偏移，为每个粒子设定了对应的适应度值。第 $\mathbf { \xi } _ { t }$ 个粒子在面相似度矩阵 $S _ { \mathrm { A B } }$ 中搜索到的位置向量 $\scriptstyle x _ { t } = ( j ( 1 ) , j ( 2 ) , \ldots , j ( m ) ) ,$ 。其中， $j ( i )$ 表示与源模型A的第 $i$ 个面所匹配的目标面号 $( i { = } 1 , 2 , . . . , m )$ 。第 $t$ 个粒子的适应度函数的计算过程如式(4)所示。

$$
f ( t ) = \sum _ { i = 1 } ^ { m } S [ i , j ( i ) ]
$$

基于粒子群算法的面匹配过程如下所示：

a)根据式(1)构造源模型A和目标模型B之间的面相似度矩阵 ${ \pmb S } _ { \mathrm { A B } }$ 。

b)初始化种群大小 $p$ ，惯性权重 $w$ ，迭代次数 $s$ ，学习因子C1、 $c _ { 2 }$ ；初始化粒子的位置 $x _ { t }$ 和速度 $\nu _ { t } ( t { = } 1 , 2 , . . . , n )$ ；初始化当前迭代次数 $k { = } 0$ 。

c)根据式(4)计算第 $t$ 个粒子的适应度函数值 $f ( t ) ( t { = } 1 , 2 , . . . ,$ n)。

d)判断 $k { > } s$ ，如果为真则算法结束，输出 $x _ { G b e s t } ^ { k }$ ；否则执行步骤e)。

e)如果 $f ( t ) < f _ { s s , t , t }$ ，则 $f _ { _ { P S , i } } = f ( t )$ ， $\boldsymbol { x } _ { P b e s t , t } ^ { k } = \boldsymbol { x } _ { t } ^ { k }$ （204号f)如果 $f _ { _ { N a s t } } { < } f _ { _ { a s s } }$ ，则 $f _ { _ { o s s t } } { = } f _ { _ { p s s t } }$ ， $\boldsymbol { x } _ { G b e s t } ^ { k } = \boldsymbol { x } _ { P b e s t , t } ^ { k }$ 。

g)根据式(2)(3)来更新第 $\mathbf { \Psi } _ { t }$ 个粒子的速度 $\nu _ { t } ^ { k + 1 }$ 和位置 $\boldsymbol { x } _ { t } ^ { k + 1 }$ $\mathrm { h } ) k { = } k { + } 1$ ，执行步骤d)。

在模型面相似度矩阵 ${ \pmb S } _ { \mathrm { A B } }$ 中，利用粒子群算法来搜索两个模型之间的最优面匹配序列。最优位置解向量为 $( j ( 1 ) , j ( 2 ) , . . . ,$ $j ( m ) )$ 。可以知道：源模型A与目标模型B的最优面匹配序列为$( 1 , j ( 1 ) ) \cdot ~ ( 2 , j ( 2 ) ) \cdot ~ \ldots ~ ( m , j ( m ) ) \circ$

根据最优面匹配序列，从源模型A与目标模型B的面相似度矩阵 ${ \pmb S } _ { \mathrm { A B } }$ 中提取对应的元素。通过累积源模型面和目标模型面之间的相似性，就可以得到A、B 两个模型的整体相似性$S _ { m o d \left( \mathrm { A } , \mathrm { B } \right) }$ 。模型相似性 $S _ { m o d \left( \mathrm { A } , \mathrm { B } \right) }$ 的计算过程如式(5)所示。

$$
\displaystyle S _ { \mathrm { \ m o d } ( A , B ) } = \frac { \displaystyle \sum _ { i = 1 } ^ { m } S [ i , j ( i ) ] } { \displaystyle \operatorname* { m i n } ( m , n ) }
$$

其中 $( i , \ \mathrm { j } ( i ) )$ 表示最优面匹配序列中的第 $i$ 个值； $S [ i , j ( i ) ]$ 为面相

似度矩阵 $S _ { \mathrm { A B } }$ 的第 $i$ 行第j(i)列的数值； $m i n ( m , n )$ 为 $m , n$ 的最小值。

# 3 实验

本文在处理器为i5的Windows7操作系统下，使用Matlab来编写粒子群算法，实现对面相似度矩阵的搜索。在实验中，共选取三个CAD模型。目标模型和源模型如图2所示。目标模型是四棱锥；源模型A是四棱锥；源模型B是三棱柱；源模型C是带有通孔的圆台。

![](images/a7516590fd272da09d6f7ec54f2718887840c7f04743c2bef32ae185ec9b3c35.jpg)  
图2目标模型和源模型

在度量源模型与目标模型之间的相似性时，一般都采用贪心策略来寻找这两个模型之间的最优面匹配序列。为了验证本文所提出方法的有效性，共进行了两组对比实验。

在实验中，利用式(1)来构造源模型与目标模型的面相似度矩阵 $S _ { \mathrm { A B } }$ 。分别使用贪心算法和粒子群算法来搜索这两个模型之间的最优面匹配序列。根据最优面匹配序列，从矩阵 $\pmb { S } _ { \mathrm { A B } }$ 中提取源模型面与目标模型面之间的相似性，并使用式(5)来计算模型之间的相似性。

目标模型包括五个面：面 $\nu _ { 1 }$ 、V2、 $\nu _ { 3 }$ 、 $\nu _ { 4 }$ 和 $\vert \nu _ { 5 }$ 。面 $\nu _ { 1 }$ 与面$\nu _ { 2 }$ 、 $\nu _ { 4 }$ 和 $\mathbf { \sigma } _ { \nu \varsigma }$ 相邻接；面 $\nu _ { 2 }$ 与面 $\nu _ { 1 }$ 、 $\nu _ { 3 }$ 和 $\mathbf { \sigma } _ { \nu _ { 5 } }$ 相邻接；面 $\nu _ { 3 }$ 与面$\nu _ { 2 }$ 、 $\nu _ { 4 }$ 和 $\mathbf { \sigma } _ { \nu 5 }$ 相邻接；面 $\nu _ { 4 }$ 与面 $\mathbf { \Psi } _ { \nu _ { 1 } }$ 、 $\mathbf { \sigma } _ { \nu 3 }$ 和 $\mathbf { \sigma } _ { \nu 5 }$ 相邻接；面 $\nu { } _ { 5 }$ 与面$\nu _ { 1 }$ 、 $\nu _ { 2 }$ 、 $\nu _ { 3 }$ 和 $\nu _ { 4 }$ 相邻接。面 $\nu _ { 1 }$ 有三个相邻面，因此，面 $\nu _ { 1 }$ 的边数为3。同理，可以计算出其他面的边数。面 $\nu _ { 2 }$ 、 $\nu _ { 3 }$ 和 $\nu _ { 4 }$ 分别有三条边，面 $\vert \nu _ { 5 }$ 有四条边。

以图2中的源模型A为例，使用粒子群算法来搜寻源模型A和目标模型之间的最优面匹配序列。源模型A包括五个面：面 $u _ { 1 }$ 、u2、 $u _ { 3 }$ 、 $u _ { 4 }$ 和 $u _ { 5 }$ 。其中，面 $u _ { 1 }$ 、 $u _ { 2 }$ 、 $u _ { 3 }$ 和 $u _ { 4 }$ 为三角形,分别有3条边；面 $u s$ 是四边形，含有四条边。

使用式(1)计算源模型面与目标模型面之间的相似性，并构造源模型A与目标模型之间的面相似度矩阵，如下所示：

$$
\left[ \begin{array} { c c c c c c c } & { \nu _ { 1 } } & { \nu _ { 2 } } & { \nu _ { 3 } } & { \nu _ { 4 } } & { \nu _ { 5 } } \\ { u \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 0 . 7 5 } } \\ { u \boldsymbol { 2 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 0 . 7 5 } } \\ { u \boldsymbol { 3 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 0 . 7 5 } } \\ { u \boldsymbol { 4 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 1 } } & { \boldsymbol { 0 . 7 5 } } \\ { u \boldsymbol { s } } & { \boldsymbol { 0 . 7 5 } } & { \boldsymbol { 0 . 7 5 } } & { \boldsymbol { 0 . 7 5 } } & { \boldsymbol { 0 . 7 5 } } & { \boldsymbol { 1 } } \end{array} \right]
$$

在源模型A中，面 $u \mathrm { 1 }$ 与面 $u _ { 2 }$ 、 $u _ { 4 }$ 和 $u s$ 相邻接；在目标模型中，面 $\nu _ { 1 }$ 与面 $\nu _ { 2 }$ 、 $\nu _ { 4 }$ 和 $\nu { } _ { 5 }$ 相邻接。由式(1)可知,在源模型A和目标模型的面相似度矩阵中，第 $u _ { 1 }$ 行第 $\nu _ { 1 }$ 列的值为1。在目标模型中，面 $\mathbf { \sigma } _ { \nu 5 }$ 与面 $\nu _ { 1 }$ 、V2、V3和 $\mathbf { \sigma } _ { \nu 4 }$ 相邻接。由式(1)可知,在源模型A和目标模型的面相似度矩阵中，第 $\boldsymbol { u } _ { 1 }$ 行第 $\vert \nu _ { 5 }$ 列的值为

# 0.75。

以源模型A和目标模型的面相似度矩阵为基础，使用粒子群算法来搜索源模型A与目标模型之间的最优面匹配序列。得到最优面匹配序列为：(1,3)、(2,2)、(3,1)、(4,4)、(5,5)。同时，使用式(5)来计算源模型A与目标模型之间的整体相似性，其数值为1。

源模型A、源模型B和源模型C与目标模型之间的相似性计算结果如表1所示。

表1源模型与目标模型之间的相似性  

<html><body><table><tr><td>源模型</td><td>面数</td><td>边数</td><td>顶点数</td><td>贪心算法</td><td>粒子群算法</td></tr><tr><td>A</td><td>5</td><td>8</td><td>5</td><td>1</td><td>1</td></tr><tr><td>B</td><td>5</td><td>9</td><td>6</td><td>0.9</td><td>0.9</td></tr><tr><td>C</td><td>4</td><td>8</td><td>0</td><td>0.75</td><td>0.8125</td></tr></table></body></html>

从形状上看，源模型A与目标模型完全一致，其相似性数值为1；源模型B与目标模型的相似度较大，其相似性数值为0.9；源模型C与目标模型有一定的相似性，其相似性数值为0.8125。

从表1可知,源模型A和目标模型是同一个模型，贪心算法和粒子群算法获得的数据是一致的。对于源模型B，贪心算法和粒子群算法获得的数据也是一致的。对于源模型C，它是一个关键性模型。使用粒子群算法所获得的相似性数值比贪心算法要高，其结果提高了 $8 . 3 3 \%$ 。从形状上看，源模型C与目标模型有一定的相似性。相对于贪心算法而言，本文所提出的方法更能准确地度量两个模型之间的相似性。

在实验中，使用贪心算法搜索面相似度矩阵，其时间复杂度为 $O ( m n )$ 。使用粒子群算法搜索面相似度矩阵，其时间复杂度为 $O ( p s m n )$ 。尽管粒子群的时间复杂度要高于贪心算法，但是粒子群算法在度量模型之间的相似性时，效果要好于贪心算法。

# 4 结束语

本文利用面的边数差异来构建面相似度矩阵。通过粒子群算法来搜索源模型与目标模型之间的最优面匹配序列。以最优面匹配序列为基础，通过累积源模型面与目标模型面之间的相似性来度量两个模型的整体相似度。实验结果表明：粒子群算法可以有效地实现源模型面与目标模型面的匹配，进而准确地度量模型之间的形状差异。

# 参考文献：

[1]刘志，尹世超，潘翔，等．基于特征线条的三维模型检索方法[J].计 算机辅助设计与图形学学报,2016,28(9):1512-1520.   
[2] 范菁，李然，董天阳．基于局部视图的三维树木模型递进检索方法[J]. 计算机辅助设计与图形学学报,2016,28(1):162-171.   
[3] 庄廷，张旭堂，侯珍秀．多特征结合相似度优化的三维工程模型检索算 法[J].哈尔滨工程大学学报,2015,36(5):720-724.   
[4] 张开兴，白晓亮，张树生．基于局部形状特征的自由曲面相似性评价方 法[J].计算机集成制造系统,2014,20(3):530-536.   
[5]白静，罗皓楠，秦飞巍．面向非线性特征的三维CAD 模型聚类[J].计 算机辅助设计与图形学学报,2015,27(8):1578-1586.   
[6] Qin Feiwei,Gao Shuming，Yang Xiaoling，et al.An ontology-based semantic retrieval approach for heterogeneous 3D CAD models[J]. Advanced Engineering Informatics,2016,30 (4):751-768.   
[7]Kim Hyungki,Cha Moohyun,Mun Duhwan.Shape distribution based retrieval of 3D CAD models at different levels of detail[J].Multimedia Tools and Applications,2017,76 (14): 15867-15884.   
[8]Chen Qiang,Fang Bin, Yu Yongmei, et al.3D CAD model retrieval based on the combination of features [J]. Multimedia Tools and Applications, 2015, 74 (13): 4907-4925.   
[9]Tao Songqiao,Wang Shuting,Chen Anhui.3D CAD solid model retrieval based on region segmentation[J]. Multimedia Tools and Applications,2017, 76 (1): 103-121.   
[10] Jin Yao,Qian Gui Ping,Zhao Jie Yi, et al. Stretch-minimizing volumetric parameterization [J]. Journal of Computer Science and Technology,2015, 30 (3): 553-564.   
[11]皇甫中民，张树生，闫雒恒．基于层次特征描述子的三维CAD 模型检 索[J].计算机集成制造系统,2015,21(12):3095-3106.   
[12]陈龙，樊兴旺，王猛，等．有限元四边单元网格模型的参数化重建[J]. 计算机辅助设计与图形学学报,2017,29(4):680-688.   
[13]潘万彬，高曙明，陈翔．参数化模型的局部自动适应重用方法[J].计 算机辅助设计与图形学学报.2016.28(2):314-327.