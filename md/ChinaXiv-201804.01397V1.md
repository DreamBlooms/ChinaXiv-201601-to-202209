# 复杂非均质地层的等值线生成算法研究\*

孙歧峰，赵琰，段友祥，刘培刚(中国石油大学(华东）计算机与通信工程学院，山东青岛 266580)

摘要：等值线图是复杂油气藏地质研究中的一类重要表示形式。针对地层数据特点，研究和分析了复杂非均质地层数据等值线绘制方法的不足，提出一种新的分区方法，实现了带断层的数据集合划分。基于Delaunay三角剖分算法，并以几何多边形为雏形，建立了带约束的三角网格模型。采用约束Delaunay三角网的拓扑结构，选用改进的反距离加权插值算法，有效地解决了断层两侧高程值问题，并结合实际应用要求在 $\mathrm { V C } + +$ 与OpenSceneGraph的开发环境下，实现了非均质带断层的地层等值线的绘制。通过对国内某采油厂的实际油气储集地层数据等值线图的绘制和可视化，证明了方法的可行性和准确性。

关键词：非均质；Delaunay三角剖分；约束三角网；反距离加权 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.12.0834

# Research of contour generation algorithm for complex heterogeneous reservoir. computer engineering and applications

Sun Qifeng, Zhao Yan, Duan Youxiang, Liu Peigang (CollegeofComputer&CommunicationEngineering,China UniversityofPetroleum,Qingdao Shandong266580,China)

Abstract: Contour map isanimportanttypeofrepresentation inthe studyofcomplex reservoirs.Aimed atthe characteristics offormationdata,this paper firstly analyzed the shortcomings ofthecontour drawing method and proposed anew partition method,whichrealizes thepartitionofdata sets with faults.Thenitestablishedatriangular mesh modelbasedontheDelaunay triangulationalgorithmandgeometricpolygons.UsingthetopologyofconstrainedDelaunaytriangulationandimproved inverse distance weighted interpolation algorithm,this paper solvedthe problemof elevation values onboth sidesofthefaults.In the development environment of ${ \mathrm { V C } } + +$ and OpenSceneGraph,this paper realized the contour drawing of the stratum with heterogeneityfault.Throughthe drawingandvisualizationofthecontourmapoftheactualoilandgasreservoirdata,it proves the feasibility and accuracy of the method.

Key words: heterogeneous; delaunaytriangulation; constrained delaunaytriangulation; inverse distance weighting

# 0 引言

等值线图是地质研究工作中的一种重要的表示方法[1,2]，为确定石油富集区的位置、形态、石油的储量以及钻井作业等提供了重要依据，因此地层等值线图的绘制与可视化具有非常重要的价值。由于地壳运动过程中产生的作用力，使地层发生断裂，沿着断裂面两侧发生相对位移，即断层。断层使其两侧数据不再连续，给地层等值线的绘制及地层构造可视化带来困难。但矿物、油气等资源又往往分布在断层附近，准确的等值线图可以清晰地反映复杂地质构造，使专业人员能够对地层构造作出正确的分析，从而带来重大的经济效益[34]。在TIN

（triangulated irregular network）生成算法中，Delaunay三角剖分算法在地形拟合方面较普遍，常被用于TIN的生成。当断层参与TIN的生成时，应将断层视为约束条件，则应考虑带限定约束条件的Delaunay 三角网，即约束Delaunay 三角网（constrained delaunay triangulation, CDT）[5-6]。

目前，生成约束Delaunay三角网的算法有很多，大致上分为两步：首先，生成无约束的Delaunay三角网，其次，将断层约束线段嵌入到无约束的三角网中，并对三角网进行调整。有关约束线段嵌入的算法比较多[7\~12]，文献[7]中，将除断层之外的数据先进行剖分，随后再把断层嵌入，这样，断层线段跟三角网的位置情况会有多种，对每种情况分别进行不同的嵌入方法，算法较复杂，不易操作；黄晶晶[8提出的“插入-交换”算法适合于任意区域的约束剖分，但在断层影响域内三角形，每共边的两个三角形，就要判断一次是否为凹凸多边形，执行起来比较耗时；刘少兵9提到的复连通区域三角剖分算法，该方法首先要找到与约束线段相交或靠近约束线段的三角形，并把这些三角形合并成一个单连通区域，然后求取该区域的外边界，将单连通区域与外边界组成复连通区域，这样就转换成了简单多边形的三角剖分，该方法解决了约束线段嵌入问题，但效率不高；张坤[12]，付金华[3]提出的等值线生成算法，解决了单条断层线的嵌入问题，但并没有对断层多边形进行处理；孙劲光[13]提出当约束条件为折线约束或者曲线约束时，可以将约束转换为线性单元集合，然后对这些线性单元集合进行Delaunay剖分，但在转换过程中，要保证转换后的线性单元集合与原来约束条件拟合，在剖分过程中，若线段不在Delaunay三角网格中，许多文献[14-16]是通过局部变换边或者边界细分算法在直线上取点进行加点细分，以恢复约束线段在网格中的存在。这种算法加入的是线性单元上的点而不是原来约束条件中的点，这种方法不利于逼近线性单元集合对原来约束条件的逼近。

针对上述问题，本文以采油厂地层离散数据为基础，结合地层三维可视化的应用特点，提出一种针对非均质带断层的地层等值线生成算法。该方法首先将原始地层数据进行分区，并将分区后的数据分别进行无约束的三角剖分，然后通过文献[17]中提到的约束线段嵌入方法，将断层多边形嵌入到三角网中；通过判断断层多边形的内外边界类型，对构成的三角网进行适当的裁剪与优化，最后进行等值线追踪。该方法不仅实现了带断层的等值线的绘制，而且满足了实际应用需求。

# 1 带断层约束的层面建模

# 1.1 地层数据分区

对于给定的油藏地层不规则离散点集合 $\boldsymbol { \mathbf { \mathit { V } } }$ 以及断层数据集合 $F$ ， $V = \{ X _ { \scriptscriptstyle , } Y _ { \scriptscriptstyle , } Z _ { \scriptscriptstyle , } \} , i = 1 , 2 , 3 . . . n$ ，其中 $X _ { _ { i } , Y _ { _ { i } } }$ 为离散点的坐标， $Z _ { _ i }$ 为离散点的高程值， $F = \{ X _ { _ j } , Y _ { _ j } \} , j = 1 , 2 , 3 . . . m$ ，其中 $X _ { _ { j } } , Y _ { _ { j } }$ 为断层点的坐标。其分区思想如下：

a)以离散点数据集合为例。设定分区号 $n u m \mathrm { ~ , ~ } n u m$ 从 $_ 1$ 开始，任取离散点集合中的一点为 $p 1$ ，将其分区号设为 $_ 1$ ，从剩下的离散点数据集合中取出任意一点为 $p 2$ ，假定一条以点 $p 1$ 与点$p 2$ 为端点的线段，如果该线段与所有的断层数据线都不相交，那么点 $p 2$ 跟点 $p 1$ 同属于一个分区，将点 $p 2$ 分区号设为 $p 1$ 的分区号，并将 $p 2$ 从原始离散数据集合中删除。如果点 $p 2$ 与该分区号下的 $p 1$ 存在相交的情况，需分情况进行判断：

(a)将点 $p 2$ 先不做处理，依次遍历离散点数据集合中剩下的点，若剩下的点中至少存在一点 $p 3$ ，且以点 $p 3$ 、点 $p 1$ 为端点的线段与所有断层数据线都不相交，那么将 $p 3$ 的分区号设为 $p 1$ 的分区号，修改分区号完成后，判断以点 $p 2$ 、点 $p 3$ 为端点的线段与所有断层线是否相交，如果不相交，就将 $p 2$ 的分区号设为与 $p 1$ 相同的分区号，并将 $p 2$ 从原始离散数据集合中删除，否则， $p 2$ 跟 $p 1$ 不属于同一个分区；

(b)若遍历完所有的离散数据集合，不存在点 $p 3$ ，使得以点$p 3$ 、点 $p 1$ 为端点的线段与所有断层数据线都不相交，那么分区号 $n u m + 1$ ；

b）依次循环遍历，直到取遍所有的离散数据点。

c）以断层数据为例。任取断层数据集合中的一点 $f 1$ ，从$n u m = 1$ 开始，若该分区内至少存在一点 $p 4$ ，使得以点 $p 4$ 、点 $f 1$ 为端点的线段与所有的断层线都不相交，那么将点 $f 1$ 加入到这一分区内，并将其从原始数组中删除。

d）依次循环遍历，直到取遍所有的断层数据点。

如图1、2所示，黑色圆点代表离散数据点，红色代表断层数据点，图1为分区示意图，图2为分区完成图。

![](images/520af42c0eef34e23636097da4eb4bae5f94639459237a061923e8e217951440.jpg)  
图1离散点示意图

![](images/2ecae271efafcbbce01581afdafad69f40d37ab194bf5ccfd5cca17d27576e6e.jpg)  
图2分区完成图

# 1.2构造带断层约束的CDT网格

# 1.2.1构建无约束的DT网格

本文采用逐点插入法按照上述分区，构建每个分区内的离散数据点与断层点组成的无约束DT网格，其具体思想步骤可参考文献[18,19]。

# 1.2.2断层约束线段入网

选取断层上相邻两点组成的线段，假设要嵌入的线段为$f 1 f 2$ ， $f 1$ 、 $f 2$ 在原始三角网中位置如图3（a)所示，与f1f2相交的三角形组成的区域为 $f 1 f 2$ 的影响区域。给定两个数组right、left用来存放三角形顶点。断层入网的详细实现过程如下：

a）确定影响区域。从三角形链表中查找与约束线段 $f 1 f 2$ 相交的三角形，保留三角形的顶点，在三角形链表中删除该三角形；

b）判断a）中存储的顶点与 $f 1 f 2$ 线段的位置关系。这里采用点与直线的位置关系判定法。若点在 $f 1 f 2$ 的右侧，把该点存储到 $r i g h t$ 数组中，若在 $f 1 f 2$ 的左侧，把点存放在 $l e f t$ 数组中，若点在 $f 1 f 2$ 上，把该点同时存放到right、left数组中；

c）循环遍历三角形链表，执行a)b)，直到不存在与 $f 1 f 2$ 相交的三角形；

d）删除数组right、left中的重复元素，按顺序排列，并在数组末尾添加头元素，组成 $P L$ 、 $P R$ 两个多边形，如图3（b)所示，红线代表约束线段。

![](images/5f7132b23197f4549e03c5eafce24de47a6a0b63568da506a1be652071b2de7a.jpg)  
图3约束线段入网过程

# 1.3影响多边形的三角剖分

因内外边界约束的三角剖分在有限元分析、曲面重建等领域具有广泛的应用且效率较高，故而本文使用内外边界约束的算法，对多边形进行剖分[20]。当断层约束嵌入完成后，对 $P L$ 、$P R$ 分别进行三角剖分，若 ${ P L } \setminus \ P R$ 为凸多边形，不做处理，若为凹多边形，要将 $P L$ 、 $P R$ 外部多余三角形删除，并进行优化调整。因此处讨论断层多边形的约束算法，当完成上述断层线段嵌入，影响多边形的三角剖分后，若断层多边形内还存在多余的三角形，需将断层多边形视为边界，判断断层多边形的边界类型，若为内边界，将断层多边形内部的三角形删除；若为外边界，需将断层多边形外部多余的三角形删除。删除多余三角形的算法步骤如下：

a）判定断层多边形的边界类型。

b)计算三角形的内心。因三角形内心始终存在于三角形内部，故而，判断三角形的内心与断层多边形的位置关系，若断层多边形为内边界，那么删除三角形内心在断层多边形内的三角形；若断层多边形为外边界，那么删除三角形内心在断层多边形外的三角形；

(a)三角形内心的计算公式为：假定三角形的三个顶点的坐标为 $\textit { I A } ( x 1 , y 1 ) \quad \mathrm { ~ , ~ } \quad B ( x 2 , y 2 ) \mathrm { ~ , ~ } \quad C ( x 3 , y 3 ) \mathrm { ~ , ~ } \quad B C = \textit { a } , \quad C A = b \mathrm { ~ , ~ } \quad A B = c \mathrm { ~ , ~ }$ （204内心为 $M ( x , y )$ 。则内心点 $M ( x , y )$ 的坐标公式由式 $( 1 ) { \sim } ( 3 ) \$ ）计算得到：

$$
a = { \sqrt { \left( x 2 - x 3 \right) ^ { 2 } + \left( y 2 - y 3 \right) ^ { 2 } } }
$$

由式(3)，类似可以推出 $\textit { b , c }$ 的值。

$$
x = ( a ^ { * } x 1 + b ^ { * } x 2 + c ^ { * } x 3 ) / \left( a + b + c \right)
$$

$$
y = \left( a ^ { * } y 1 + b ^ { * } y 2 + c ^ { * } y 3 \right) / \left( a + b + c \right)
$$

(b)点与多边形位置关系判定方法。判断点与多边形的位置关系，常用的方法为射线法。即从要判定的点引出一条射线，统计该射线与多边形的交点个数。若有奇数个交点，说明点在多边形中，否则，点在多边形外。需注意的是，当检测的点是多边形的顶点或者是多边形边上的点时，在此处算作点在多边形内。如图4为点与多边形的位置关系示意图（红色代表要判定的点， $p 1$ 代表判定点与多边形点重合)。

![](images/d6d9c062138109b2f522779ddcad62e17384d02f98c8ce68fb8456e618e3d1f6.jpg)  
图4点与多边形位置关系示意图

c）循环遍历a）b)，直到所有的断层多边形处理完毕。

以上述数据为例，图5为断层线段嵌入完成后，形成的CDT网格，图6为删除多余三角形后形成的CDT网格（红色代表断层数据点，黑色为离散数据点）。

![](images/6e815fa619321bc7da4f83a72916b0399b02343e9c41e84fc9db6eea16fc804f.jpg)  
图5嵌入断层后的CDT网格

![](images/b8ffb916d28c5915cef5f697a94a105105232d27b02fadab9de30ed973000bd4.jpg)  
图6删除多余三角形后的CDT网格

# 2 带断层的等值线生成算法

# 2.1反距离加权插值算法

目前，经野外勘探获得的断层数据信息都是不完整的，大部分断层缺失或者没有高程值信息，所以在绘制带断层的等值线图时，需计算断层两侧的高程值。用于等值线绘制时网格插值的方法有很多，如：反距离加权法、克里金插值法、最邻近点法等。本文采用反距离加权插值算法，该方法比较简单、容易实现，且有效地解决了计算断层高程值的问题。

反距离加权插值（InverseDistanceWeighting）又叫最小二乘距离加权插值，它的插值点的值只是周围邻近点距离倒数的函数[21]。对于插值点 $x$ 的估计值为 $z$ ，其一般形式的公式为

$$
z ( x ) = { \sum } _ { i = 0 } ^ { N } w _ { i } ( x ) ^ { * } z _ { i } / \sum _ { i = 0 } ^ { N } w _ { i } ( x )
$$

其中：

$$
w _ { i } ( x ) = 1 / d ( x , x _ { i } ) ^ { m }
$$

$$
d = \sqrt { \left( x - x _ { i } \right) ^ { 2 } + \left( y - y _ { i } \right) ^ { 2 } }
$$

在式 $\left( 4 \right) \sim \left( 6 \right)$ 中， $x _ { i }$ 为临近点的横坐标， $z _ { i }$ 为临近点的高程值， $N$ 为用于插值的样本点的个数，（此处 $N = 6$ ）， $d$ 为临近点 $x _ { i }$ 到插值点 $x$ 的距离， $m$ 为正整数幂次（一般0.5到3的值可获得最合理的结果，此处 $m = 2$ ）， $w _ { i }$ 为权重，距离插值点越近，邻近点的权重就越大。邻近点的选取，通过计算离散数据点到插值点的距离，通过设定距离长度，查找距离插值点最近的6个点，从而得到邻近的离散点。

# 2.2等值线追踪

进行等值线追踪时，需注意等值线是否到达断层线，若已经追踪到断层线，应立即停止，而不是穿越断层线。为避免出现穿越断层的情况，在进行等值线追踪之前，需对约束剖分完成后的CDT网格进行结构化处理，将断层线所在的三角形视为边界三角形，当等值线追踪到边界三角形时，停止追踪。追踪算法如下：

a)遍历所有的三角形集合，查找边界三角形及断层三角形，并将该三角形中的边界边及断层边存储在边界边链表中；b)以某等值线数据为例，从边界边链表中选取一条等值边作为起始边。查找以该边为边的三角形及其相邻三角形，并记录穿过的所有三角形，直到查找到的等值边的最后一条是边界边，非闭合的等值线追踪完成。c）闭合的追踪与非闭合类似，但需注意的是，其追踪结束条件为查找到的等值边的最后一条为起始边。

# 3 算法实现实例

本文以油藏地层离散数据为基础，实验环境为VisualStudio $2 0 1 3 +$ OpenSceneGraph，实现了非均质带断层的等值线绘制功能。图7为无约束DT网格，图8为带断层约束的CDT网格；图9为无约束的等值线图，图10为带断层的等值线图。实验证明该方法效果良好。

![](images/4a5b3c51477fdb50b5f63b0cb597e4de177e31b5ad1837d4a94c9b48af9441bd.jpg)  
图7无约束DT 网格

![](images/b050ea633b27cb30b0d8cbda14971a76261591fafa7168799f31a0fe5e3f4147.jpg)  
图8带断层约束的CDT网格

![](images/548d041fb2eb4b35eaf5b553cc073f0d56bed095452bf1a1c32d382603c46832.jpg)  
图9无约束等值线图

![](images/b28ec1a404ef17bca4a191fdeafaa17cf525bd210020667da84f91e4d749fcc9.jpg)  
图10带断层的等值线图

在断层线条数为6，等值线为11的情况下，对不同数据级别的数据进行测试，时间对比结果如表1、表2所示。

表1数据集合约束剖分耗时  

<html><body><table><tr><td>实验组别</td><td>1组</td><td>2组</td><td>3组</td><td>4组</td></tr><tr><td>离散点数</td><td>200</td><td>1000</td><td>5000</td><td>10000</td></tr><tr><td>本文算法耗时/ms</td><td>18</td><td>120</td><td>482</td><td>921</td></tr></table></body></html>

表2传统等值线生成与本文等值线生成算法耗时对比  

<html><body><table><tr><td>实验组别</td><td>1组</td><td>2组</td><td>3组</td><td>4组</td></tr><tr><td>离散点数</td><td>200</td><td>1000</td><td>5000</td><td>10000</td></tr><tr><td>传统算法耗时/ms</td><td>25</td><td>116</td><td>580</td><td>1160</td></tr><tr><td>本文算法耗时/ms</td><td>15</td><td>89</td><td>445</td><td>890</td></tr></table></body></html>

# 4 结束语

本文在前人研究的基础之上，对带断层的复杂地层等值线绘制问题提出了一个新的方法。该方法首先将地层离散数据点及断层数据点划分在不同区块中，简化了数据集，通过断层约束线段的嵌入、影响多边形的三角剖分以及断层数据插值等操作，完整的实现了非均质带断层的等值线的可视化。该方法为有效地进行地层建模分析与应用奠定了坚实的基础。

# 参考文献：

[1]郭鹏，董兰芳，夏泽举．地质数据的等值线绘制方法研究[J].计算机仿真,2009,26 (9):168-171.  
[2]Laier T,Jensen JB. Shallow gas depth-contour map of the Skagerrak-western Baltic Sea region [J].Geo-Marine Letters,2007,27(2-4):127-141.  
[3]陈学工，付金华，马金金，等．约束TIN生成带断层等值线图的方法[J].计算机工程与应用,2011,47(33):198-201+206.  
[4]Bradley D,Heidrich W,Popa T,et al.High reolution passive facialperformance capture [J].ACM Trans on Graphics,2010,29 (4):1-10.  
[5]俞亚磊，罗永龙，郭良敏，等.Delaunay三角网中任意约束线段嵌入算法研究[J]．测绘科学,2013,38(4):61-62+33.  
[6]Boissonnat J D.Shape reconstruction from planar cross sections [J].Computer Vision Graphics & Image Processing,1988,43(1): 112-112.  
[7]刘少华，程朋根，史文中．约束Delaunay 三角网生成算法研究[J].测绘通报,2004(3):4-7.  
[8]陈学工，黄晶晶.Delaunay 三角网剖分中的约束边嵌入算法[J].计算机工程,2007,33 (16):56-58.  
[9]刘少兵．带断层地震数据的Delaunay三角剖分算法[J].煤田地质与勘探,2008,36 (06): 70-72.  
[10]俞亚磊，罗永龙，郭良敏，等.Delaunay三角网中任意约束线段嵌入算法研究[J].测绘科学,2013,38(4): $6 1 - 6 2 + 3 3$   
[11]张群会，解子毅．带断层约束的Delaunay三角剖分混合算法[J]．西安科技大学学报,2014,34(01):52-56.  
[12]陈学工，张坤．带断层线的等值线生成方法[J].计算机应用研究,2010,27 (8):3144-3146.  
[13]孙劲光，周勃．曲线约束Delaunay三角剖分及在地形构建中的应用[J].计算机应用与软件,2015,32(12): $2 5 - 2 8 + 4 1$   
[14] CerqueiraAMLG,LisboaAC,MesquitaRC.Boundary recovery forconforming Delaunay triangulation of curved complexes [J]. IET ScienceMeasurement Technology,2011,6(5):324-330.  
[15]Isenburg M,Liu Y, Shewchuk J,et al.Ilustrating the streaming constructionof 2D delaunay triangulations $[ \mathrm { C } ] / \AA$ Proc of Symposium on ComputationalGeometry.2006: 481-482.  
[16] Chernikov A N,Chrisochoides N P.Three-dimensional semi-generalizedpoint placement method for Delaunay mesh refinement [C]//Proc of the 16thInternational Meshing Roundtable.20o8: 25-44.  
[17]王中辉，闫浩文．带约束折线的平面散点集Delaunay三角剖分[J].测绘与空间地理信息,2011,34(1):46-47,52.  
[18]王龙浩，王解先．基于逐点插入法的Delaunay三角网快速生成算法[J].工程勘察,2013,41(10):75-79.  
[19]余代俊，蒲朝旭，朱逍贤．一种Delaunay三角剖分的改进算法[J].测绘通报,2014(6):51-54.  
[20]闫浩文，王明孝，王中辉．计算几何：空间数据处理算法[M].北京：科学出版社,2012.  
[21]荆永滨，杜学胜，张瑞林，等．复杂地质构造煤层三维模型自动构建技术[J].辽宁工程技术大学学报：自然科学版,2016,35(03):243-247.