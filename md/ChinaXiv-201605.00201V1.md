# 多航天器协同探测星簇构型探测效能的评价方法

杨震²，孟新’，牛文龙'²，李明涛’，张艺腾’，郑伟（1．中国科学院空间科学与应用研究中心，北京100190;2．中国科学院大学，北京100049)

摘要：为定量评估不同星簇构型设计的探测效能以进行各航天器的轨道设计基于空间四面体构型的体张量定义分析现有空间四面体构型的评价参量，并采用将空间五航天器构型分解为“五个四面体"和“主四面体加第五点问题"这两种方法定量评价空间五点协同探测星簇构型的探测效能。最后利用项目组已有的五个航天器在一个轨道周期内的模拟轨道数据对所提出的方法进行仿真，结果表明所提出的方法可以较好地评价空间五点构型的探测效能。

关键词：多点协同；四面体；探测效能；评价参量  
中图分类号：V529 文献标识码：A 文章编号：1000-328(2015)09-0981-07  
DOI: 10.3873/j.issn.1000-1328.2015.09.001

# A Evaluation Method for Multi-Spacecraft Formation Detection Efficiency

YANG Zhen1²,MENG Xin,NIU Wen-longl²,LI Ming-tao’,ZHANG Yi-teng¹,ZHENG Wei' (1.National Space Science Center Chinese Academy of Sciences ,Beijing 1Oo190 ,China; 2.University of Chinese Academy of Sciences ,Beijing 10o049,China)

Abstract:Inordertochoosethe bestdetectionefficiencyof diferentformations，quantitativeevaluationof different formations shallbeemployed.In thispaper,theexisting evaluation parametersof four-pointcooperative detectionare analyzedandsummarizedandthenbasedonthedefinitionofvolumetrictensor,thefive-point formation isdividedinto five tetrahedronsandone main tetrahedronplusafifth pointtoevaluatethedetectioneficiencyFinall,orbitdataof fivespacecraft inone orbit period isused to simulateand analyzethetwo methods,andresult showsthatthe method works well in evaluating five-point formation.

Key Words:Multi-point cooperative detection；Tetrahedron；Detection eficiency；Evaluation parameters

# 0引言

空间物理场中粒子群、电场和磁场参数均随空间和时间不断变化，依靠单一航天器无法对其空间结构及动力学现象在时域和空域的演变进行充分观测和分析。中欧“双星”计划与欧空局ClusterII计划配合在人类历史上第一次实现了对地球空间的“六点立体探测”,对地球磁层进行多时空、多尺度探测研究[1]。目前 若干已经实施或处于计划中的空间物理测量任务多采用四面体航天器编队以满足三维数据采集要求，尤其是最低阶物理场梯度的测量要求。例如NASA 的Magnetospheric MultiScale（MMS)[2]、日本的 SCOPE等编队中,四个航天器分别位于四面体的四个顶点，航天器间距的大小决定于被采样的场或动力学现象的规模，形状接近正四面体。但是在实际轨道设计中，无法实现四个航天器时刻保持正四面体构型，这时就需要定量评估不同构型设计结果的优劣以进行不同构型设计方案的选择并且需要根据探测目标设计相应的探测性能评价方法。

对于空间四面体构型的探测性能评价方法国内外研究学者提出了多种评价指标[3-57-9,2] ,包括Glassmeier 参量、Robert/Roux 参量[3]、体积比、体积边长比等;在ClusterII任务中ESOC飞行力学部门的 Harvey[4]提出了体张量的概念,较好地描述了空间四面体的几何特性;Robert等[5]在空间四面体体张量概念的基础上提出了凸度-扁度二维评价参量。这些评价参量均是基于空间四面体的理想构型是正四面体构型这一基本原则，能够较好地解决空间四面体构型的几何特性分析和探测性能评价问题但是当空间探测点的数量大于4时，上述评价参量便不再完全适用了。

本文在分析归纳已有的空间四点协同探测构型性能评价方法的基础上，尝试将其推广应用至空间五点协同探测星簇构型性能评价中，并对所提出的评价参量进行了仿真校验。

# 1空间四面体构型的评价参量

# 1.1 与正四面体构型的比较参量

对于基于空间四点立体探测的空间物理场探测任务而言 其理想构型是正四面体构型。通过将空间四面体构型的几何特性与正四面体的几何特性进行比较，评估其构型与理想构型的近似程度在一定意义上可以作为空间四面体构型优劣的评价依据。这一类的评价参量包括下述三个。

1）Glassmeier 参量 $Q _ { \mathrm { G M } }$

$$
Q _ { \mathrm { G M } } = \frac { V _ { T } } { V _ { I } } + \frac { S _ { T } } { S _ { I } } + 1
$$

式中： $V _ { I }$ 是指以空间四个探测点之间6条边的平均值为边长所构成的正四面体的体积， $S _ { I }$ 为该正四面体的表面积， $V _ { T }$ 为空间四点构成的实际四面体的体积， $S _ { T }$ 为实际四面体的表面积。该参量的最大值为3（当四面体为正四面体构型时）最小值为1（当空间四点共线时），可以用来表征空间四面体的空间维数。

2）Robert/Roux 参量 $Q _ { \mathrm { R R } }$

$$
Q _ { \mathrm { R R } } \ = \ \bigg ( \frac { 9 \pi } { 2 \sqrt { 3 } } \frac { V _ { T } } { V _ { s } } \bigg ) ^ { \frac { 1 } { 3 } }
$$

式中： $V _ { s }$ 定义为以空间四个探测点的质心为球心、空间四个探测点均处于球面上的球体体积。该参量最小值为0最大值为1（当四面体为正四面体构型

时），该参量对于评价磁场的空间梯度估计误差非常有用。

3）参量 $Q _ { \mathrm { { R 8 } } }$

$$
Q _ { \mathrm { R 8 } } \ = \frac { V _ { T } } { V _ { I } }
$$

该参量最小值为0最大值为1（当四面体为正四面体构型时）。

# 1.2 基于体张量的评价参量

# 1.2.1 体张量的引入

Harvey[4]通过对空间磁场多点立体探测的数据处理方法进行研究分析，推导出利用多点协同探测实现空间场的分界面、空间梯度等探测目标的数据处理精度依赖于由多个探测点相对位置所决定的一种张量的逆，这种张量描述了多个探测点构成的空间构型的基本几何特性：包括三个正交方向的尺度特征、三维构型的空间指向性。下面以空间三维场的分界面探测数据处理过程为例说明其推导过程。

考虑由 $N$ （ $N \geqslant 4$ )颗航天器构成的一个多点协同探测星簇定义质心 $o$ 使得所有卫星相对于质心 $o$ 的位置坐标 $\pmb { r } _ { \alpha }$ ( $1 \leqslant \alpha \leqslant N$ ），满足

$$
\sum _ { \alpha = 1 } ^ { N } \pmb { r } _ { \alpha } = 0
$$

假设在三维场中存在一个边界面，该边界面的法向矢量为 $\textbf { \em n }$ 移动速度大小为 $V$ （法线方向）卫星 $\alpha$ 在 $t _ { \alpha }$ 时刻观测到该分界面此时卫星 $\alpha$ 所处位置为 $\pmb { r } _ { \alpha }$ ( $1 \leqslant \alpha \leqslant N$ ）在考虑测量误差的情况下采用最小二乘法 当 $s$ 取最小值时可得到边界面的法向矢量 $\pmb { n }$ 和移动速度 $V$ 的最佳估计值。

$$
S ~ = ~ \sum _ { \alpha = 1 } ^ { N } ~ [ { \pmb n } \cdot { \pmb r } _ { \alpha } ~ - ~ V ( ~ t _ { \alpha } ~ - ~ t _ { 0 } ) ~ ] ^ { 2 }
$$

式中： $t _ { 0 }$ 为参考时刻。

使用矢量 ${ \pmb m } = \frac { \pmb n } { V }$ 则式(5)可写成:

$$
\begin{array} { c } { { { \cal S } ~ = ~ V ^ { 2 } \displaystyle \sum _ { \alpha = 1 } ^ { N } ~ [ m \cdot r _ { \alpha } - ( ~ t _ { \alpha } - t _ { 0 } ) ] ^ { 2 } ~ = } } \\ { { { \cal V } ^ { 2 } \displaystyle \sum _ { \alpha = 1 } ^ { N } ~ \left[ ~ \displaystyle \sum _ { k = 1 } ^ { 3 } m _ { k } r _ { \alpha k } ~ - ~ ( ~ t _ { \alpha } - t _ { 0 } ) ~ \right] ^ { 2 } } } \end{array}
$$

式(6)不确定的量只有 $t _ { 0 }$ 和矢量 $\textbf { \em m }$ 的三个分量$m _ { k }$ 为使得 $s$ 最小取 ${ \frac { \mathrm { d } s } { \mathrm { d } t _ { 0 } } } = 0$ 和 ${ \frac { \mathrm { d } s } { \mathrm { d } m _ { k } } } = 0$ 得到

$$
\begin{array} { c } { { { \displaystyle \sum _ { \alpha = 1 } ^ { N } } \left[ m _ { j } r _ { \alpha j } - \left( \begin{array} { c } { { { \tau } _ { \alpha } - t _ { 0 } } } \end{array} \right) \ \right] \ = \ 0 } } \\ { { { \displaystyle \sum _ { \alpha = 1 } ^ { N } } \left[ m _ { j } r _ { \alpha j } - \left( \begin{array} { c } { { { t } _ { \alpha } - t _ { 0 } } } \end{array} \right) \ \right] r _ { \alpha k } \ = \ 0 } } \end{array}
$$

利用多面体质心的定义由方程(4)可得到:

$$
t _ { 0 } ~ = ~ { \frac { 1 } { N } } \sum _ { \alpha = 1 } ^ { N } t _ { \alpha }
$$

即多面体的质心穿越边界面的时刻。

式(8)可表达为：

$$
m _ { j } R _ { j k } \ = \frac { 1 } { N } \sum _ { \alpha = 1 } ^ { N } t _ { \alpha } r _ { \alpha k }
$$

其中:

$$
R _ { j k } \ = \ \frac 1 { N } \sum _ { \alpha = 1 } ^ { N } r _ { \alpha j } r _ { \alpha k }
$$

此处的 $R$ 称为张量，用符号 $X$ 表示，将在第1.2.2节进行具体描述。

# 1.2.2 空间四面体体张量的定义

$X$ 这一张量对于采用 $N$ （ $N \geqslant 4$ ）颗航天器构成的一个多点协同探测星簇实现空间三维体场探测的过程具有非常重要的基础性意义，我们称这一张量为多点协同探测星簇空间构型的体张量X[4]：

$$
X = { \frac { 1 } { N } } \sum _ { \alpha = 1 } ^ { N } \left( \pmb { r } _ { \alpha } - \pmb { r } _ { b } \right) \left( \pmb { r } _ { \alpha } - \pmb { r } _ { b } \right) ^ { \textrm { T } } =
$$

$$
\frac { 1 } { N } \sum _ { \alpha = 1 } ^ { N } { \boldsymbol { r } } _ { \alpha } { \boldsymbol { r } } _ { \alpha } ^ { \mathrm { T } } - { \boldsymbol { r } } _ { b } { \boldsymbol { r } } _ { b } ^ { \mathrm { T } }
$$

式中： $\pmb { r } _ { \alpha }$ 为卫星 $\alpha$ 的三维空间坐标( $1 \leqslant \alpha \leqslant N$ ），$r _ { b } ~ = ~ { \frac { 1 } { N } } \sum _ { \alpha = 1 } ^ { N } r _ { \alpha }$ 是任意坐标系统下多点协同探测星簇空间构型的质心。

张量 $X$ 由多点协同探测星簇中所有航天器在轨道上的空间位置唯一确定，由于这一张量与多点协同探测星簇的几何形状和体积密切相关，因此张量 $X$ 称为空间四面体的体张量。

# 1.2.3 空间四面体体张量的物理含义

对于空间四面体而言，设 $a ^ { 2 } \cdot b ^ { 2 } \cdot c ^ { 2 }$ 分别为其体张量 $X$ 的三个特征值三个特征值的平方根（ $\mathbf { \Omega } _ { a }$ 、$\textit { b } , \textit { c } )$ 体现了该四面体构型在由体张量 $X$ 的三个特征向量所对应的三个正交方向上的尺度特性，并可推导出下述特性。

1)由四颗航天器所构成的空间四面体构型的体积为 $V$ 则 $V = { \frac { 8 } { 3 } } a b c = { \frac { 8 } { 3 } } \ \sqrt { | X | }$ 。与最小的特征值 $R ^ { ( { \bf \Phi } ) }$ 对应的特征向量 $\pmb { R } ^ { c }$ 是空间四面体构型最为扁平的方向，也是空间梯度探测精度最差的方向。

2)如果四颗航天器共面则体张量 $X$ 最小的特征值 $c ^ { 2 } ~ = ~ R ^ { ( { \it c } ) } ~ = ~ 0$ 此时共面的四颗航天器所构成的四边形面积 $A$ 满足下式:

$$
\frac { 1 } { \sqrt { 2 } } \leqslant \frac { A } { 4 a b } \leqslant 1
$$

其中，上限对应于四颗航天器分别位于一个平行四边形四角的情况；下限对应于任意两颗航天器重叠构成三角形的情况。

零特征值所对应的特征向量 $\pmb { R } ^ { c }$ 是四颗航天器构成的平面的法线方向。

3)如果四颗航天器共线则意味着 $\textit { b } = \textit { c } = 0$ ，于是四颗航天器构成的线段长度 $L$ 满足下式：

$$
1 \leqslant \frac { L } { 2 a } \leqslant \sqrt { 2 }
$$

其中，上限对应于四颗航天器中的两颗位置重合并位于其它两颗航天器中点的情况；下限对应于四颗航天器两两重合的情况。非零特征值所对应的特征向量 $\pmb { R } ^ { a }$ 是四颗航天器构成的直线方向。

# 1.2.4基于体张量的空间四面体构型评价参量

由于空间四面体的体张量囊括了采用最小二乘法进行分界面探测和空间梯度测量所需要的所有空间特征参数因此可以利用体张量作为空间四面体构型优劣的评价依据。这一类的评价参量包括下述两个。

1)参量QsR

$$
Q _ { s R } \ = \ \frac { 1 } { 2 } \Big ( \frac { a \ : + \ : b \ : + \ : c } { a } \Big ) - 1
$$

该参量用到了体张量的特征值，其中 $a ^ { 2 } \cdot b ^ { 2 }$ 、$c ^ { 2 }$ 分别为按照从大到小顺序排列的该四面体构型体张量的三个特征值。

2)E-P-L

利用空间四面体体张量 $X$ 的三个特征值能很好地描述四面体构型的形状、尺度和方向性。当体张量 $X$ 的三个特征值相等时，意味着空间四面体具有各向同性；当该四面体被拉伸时，体张量 $X$ 最大的特征值 $a ^ { 2 }$ 与其他两个特征值比较将增大，直到另外两个特征值 $b ^ { 2 } \ = c ^ { 2 } \ = \ 0$ 时空间四个探测点将形成一条直线;当该四面体被挤压时，体张量 $X$ 最小的特征值 $c ^ { 2 }$ 与其他两个特征值比较将减小，直到$c ^ { 2 } \ = 0$ 时 空间四个探测点将共面。

Robert等[5]引入了如下评估因子:

（1）凸度： $E = 1 - \left( { \frac { b } { a } } \right)$ 体张量 $X$ 的最大特征值 $a ^ { 2 }$ 所对应的特征向量 $\pmb { R } ^ { a }$ 是空间四面体的凸方向；

(2）扁度: $P = 1 - \left( { \frac { c } { b } } \right)$ 体张量 $X$ 的最小特征 $c ^ { 2 }$ 所对应的特征向量 $\pmb { R } ^ { c }$ 是空间四面体的扁方向;

（3）空间尺度： $L \ = 2 a$ ,表征空间四面体构型的尺度特征。

当四面体为正四面体时 $\mathbf { \nabla } { \mathcal { L } } = P = 0 $ 当四面体四个顶点共线时 $\mathbf { \nabla } { \mathcal { L } } = 1 \mathbf { \nabla }$ ；当四面体四个顶点共面时 $\mathbf { \Omega } , P _ { \mathbf { \Omega } }$ $= 1$ 。图1列出了文献[5]中四面体形状与 $E , P$ 的对应关系。

![](images/022931affe64f03972260826787e0b2ebf026430bbaa903c6b4031982ad9866f.jpg)  
图1 四面体形状与 $E \setminus P$ 的对应关系  
Fig.1The shape of the polyhedron as a function of $E$ and $P$

# 2空间五点探测构型的评价参量

在多颗航天器的编队飞行中，如需满足三维结构的探测需求至少需要4个航天器进行四面体布局编队。通常近地圆轨道的四面体编队在一个轨道周期中存在两个探测性能劣化时间段而通过增加第5颗航天器，可以弥补其探测性能的下降图2是一种空间五点探测的构型设计示意。

在空间探测点数量增加到五的情况下原来针对空间四面体构型的覆盖效能评价方法是否仍然适用？首先要面临的一个问题就是在三维空间不存在顶点数为五的正多面体[1]。既然不存在一个顶点数为五的正多面体考虑将空间五点进行分解：从五点中任取四点可以组成五个四面体；将五点分解为主四面体加空间第五点。本节利用项目组已有的五颗航天器在一个轨道周期内的模拟轨道数据对上述两种分解方式星簇构型的探测效能进行评价和分析。

![](images/f32b03c8f281fb26551807ffeba7f1765e72fcf4a16fc0b69e63bf18543b255c.jpg)  
图2空间五点探测构型 Fig.2Five-point formation

在编队设计中引入虚拟中心 $R$ 作为参考星 $\mathbf { \Omega } , \mathbf { \Omega } ,$ 表示主控载荷 ${ \mathbf { \nabla } } , { S _ { i } }$ 表示第 $i$ 个分离载荷。主控载荷$M$ 与虚拟中心 $R$ 之间存在相对轨道倾角差和相对升交点赤经差相对虚拟中心做并行运动;分离载荷$S _ { 1 } { \setminus } S _ { 2 } { \setminus } S _ { 3 }$ 与虚拟中心 $R$ 存在相对偏心率、相对近地点幅角和相对平近点角差，相对虚拟中心做绕飞运动绕飞中心在虚拟中心上;分离载荷 $S _ { 4 }$ 与虚拟中心 $R$ 存在相对升交点赤经差、相对近地点幅角和相对平近点角差相对虚拟中心做钟摆运动。

在任意时刻 $\mathbf { \varLambda } _ { S _ { 1 } \setminus S _ { 2 } \setminus S _ { 3 } }$ 都在一个平面上，可以分别与 $M$ 和 $S _ { 4 }$ 构成空间四面体，并且两个四面体在地理覆盖上是互补的。 $S _ { 1 } \setminus S _ { 2 } \setminus S _ { 3 } \setminus M$ 构成的空间四面体在极区形成良好的探测覆盖; ${ \cal S } _ { 1 } \setminus { \cal S } _ { 2 } \setminus { \cal S } _ { 3 } \setminus { \cal S } _ { 4 }$ 构成的空间四面体在赤道形成良好的极区覆盖。

编队飞行的相对位姿描述的基本内容可以参考文献 $[ 1 3 ] _ { \circ }$ 下面给出编队中虚拟中心 $R$ 的平均轨道根数。半长轴为 $7 3 7 8 . 0 7 1 6 { \mathrm { ~ k m } }$ ，偏心率为0.06775，轨道倾角为 $8 9 . 9 9 8 8 ^ { \circ }$ ，升交点赤经为$1 0 9 . 9 9 7 8 ^ { \circ }$ 近地点俯角为 $2 8 5 . 7 8 4 7 ^ { \circ }$ ,平近点角为$3 5 9 . 8 8 2 7 ^ { \circ }$ 。

# 2.1 空间五点构型分解为五个四面体

对于空间五点， $( ~ V _ { 1 } ~ , ~ V _ { 2 } ~ , ~ V _ { 3 } ~ , ~ V _ { 4 } ~ , ~ V _ { 5 } ~ )$ 可以构成五个空间四面体分别为 $( \ T _ { _ 1 } ) \ = \ V _ { _ 1 } V _ { _ 2 } V _ { _ 3 } V _ { 4 }$ 、 $\textbf { ( } T _ { 2 } \textbf { ) }$ $= V _ { 2 } V _ { 3 } V _ { 4 } V _ { 5 } \ . \ ( \ T _ { 3 } ) \ = V _ { 1 } V _ { 3 } V _ { 4 } V _ { 5 } \ . \ ( \ T _ { 4 } ) \ = V _ { 1 } V _ { 2 } V _ { 4 } V _ { 5 }$ 、$( \ { \cal T } _ { 5 } ) \ = \ { \cal V } _ { 1 } { \cal V } _ { 2 } { \cal V } _ { 3 } { \cal V } _ { 5 }$ 。下面几组图是将图2所示空间五点探测构型分解为五个四面体 按照 $\scriptstyle { E - P - L }$ 参量法在一个轨道周期内分别进行分析得到的计算结果其中横轴为轨道周期纵轴为 $E \setminus P$ 和 $L$ 。

![](images/53283a70b632b190888d0e56cf5af8565021e742a672c67bf23d0b8f1c921c21.jpg)  
图3（ ${ \cal T } _ { 1 } )$ 的 $\scriptstyle { E - P - L }$ 曲线Fig.3 $\scriptstyle { E - P - L }$ curve of $\textbf { ( } T _ { 1 } )$ （204号

![](images/7daf3ebef7bf58b3a17c8e1112f3520bfdf5f58d782bd73c178d3ab859288742.jpg)  
图4（ ${ \cal T } _ { 2 } )$ 的 $\scriptstyle { E - P - L }$ 曲线Fig.4 $\scriptstyle { E - P - L }$ curve of $\left( \begin{array} { l } { T _ { 2 } } \end{array} \right.$ ）

![](images/82b99371e8cf845de17879abb8e43ab961e9139f1b939f3ebedb57eee19dc052.jpg)  
图5 $\left( \begin{array} { l } { T _ { 3 } } \end{array} \right)$ 的 $\scriptstyle { E - P - L }$ 曲线Fig.5 $\scriptstyle { E - P - L }$ curve of ( $T _ { 3 }$ ）

根据第1.2.4节中对 $\scriptstyle { E - P - L }$ 物理含义的分析，由图 $3 \sim$ 图7可以看出，单独考察从空间五点任选四点组成的每个四面体，其在一个轨道周期内均会有多个劣化时间段。图8所示的是各个四面体在一个轨道周期内( $\textit { \textbf { E } } ,$ 散点图横轴为 $E$ 值纵轴为 $P$ 值。综合图3\~图8可以看出， $\begin{array} { r } { T _ { 2 } . } \end{array}$ ）在整个轨道周期内综合指标最优。在一个轨道周期内，为了使组合体尽可能维持在接近正四面体的构型以满足三维空间结构的探测，不同时段可以选取不同的四面体以保持整个轨道周期的综合探测性能最优。在四面体构型的劣化时段，虽然对三维空间结构的综合探测性能低但是由于组合体在某一方向进行拉伸因此可以针对该方向进行高精度探测。

![](images/578c8336bace3faf430983d097b6b73edc68b9bef54656701ec5c93f7eadcdbe.jpg)  
图6 $\left( \begin{array} { l } { T _ { 4 } } \end{array} \right)$ 的 $\scriptstyle { E - P - L }$ 曲线Fig.6 $\scriptstyle { E - P - L }$ curve of $( \mathrm { \Delta } T _ { 4 } )$ （204号

![](images/de85f62b76645d20131ca16bdd71e37e417031196fb58383528dd04c58eb1493.jpg)  
图7 $\mathit { \Pi } _ { \left[ T _ { 5 } \right] }$ 的 $\scriptstyle { E - P - L }$ 曲线Fig.7 $\scriptstyle { E - P - L }$ curve of $( \mathit { T } _ { 5 } )$ （204号

![](images/ae44c91e400882708bd5532d1f5c30fbef9a4e59121260c6d84d33c9fc6b2a6a.jpg)  
图8各个四面体的( $\textit { \textbf { E } } ,$ 散点图Fig.8 $\ , \ E \ , P )$ Point of each tetrahedron

# 2.2 空间五点构型分解为主四面体加第五点问题

通过将空间五点构型分解为五个四面体的方式虽然可以分析评价出每个时间点上构型最优的那个四面体但是实际进行编队构型设计的过程中由于五个四面体的构型变化是相互关联的，很难平衡多个四面体之间的优化关系，另外也没有充分考虑最优四面体之外空间第五点的位置优劣对探测自标的贡献。为进一步改进评价方法我们将空间五点构成的多面体分解为主四面体加第五点问题。首先通过将空间五点构型分解为五个四面体的评价方法，遴选出其中在整个轨道周期内综合指标最优的一个四面体 称为主四面体 $( \ T _ { _ m } ) \ = \ V _ { 1 } V _ { _ 2 } V _ { _ 3 } V _ { 4 }$ 其余一个点作为空间第五点 $M$ 。

对于空间第五点相对于一个空间四面体的位置关系表达已有多种坐标系形式在有限元分析中经常采用空间四面体重心坐标系但是该坐标系不能表达空间第五点位于四面体外的情况所以我们选取一种拓展的空间四面体重心坐标系。该坐标系采用点M与空间四面体 $( \mathit { T } )$ 的四个面的距离来表达如图9所示 其中 $F _ { i }$ 为空间四面体（T）的顶点 $V _ { i }$ 所对的面。

![](images/e76cd76aa1fb41d15e2c387f379dac81311dbd907c557ab750513868dfbf7d13.jpg)  
图9 四面体的点和面

首先定义点到平面的有向距离： $D ( \boldsymbol { p } \_ { \ u { F } } )$ 对于点 $M$ 来说，其在空间四面体重心坐标系下的坐标为： $\pmb { \mu } = [ \mu _ { 1 } \mu _ { 2 } \mu _ { 3 } \mu _ { 4 } ] ^ { \mathrm { T } }$ （20

$$
\mu _ { i } \ = \frac { D ( \ M \ , F _ { i } ) } { D ( \ V _ { i } \ , F _ { i } ) }
$$

式中： $\mu _ { 1 } \cdot \mu _ { 2 } \cdot \mu _ { 3 } \cdot \mu _ { 4 }$ 分别是 $M$ 点相对于空间四面体（T）的四个顶点 $V _ { 1 } \setminus V _ { 2 } \setminus V _ { 3 } \setminus V _ { 4 }$ 的权重并且有 $\mu _ { \mathrm { 1 } } \mathrm { ~ + ~ }$ $\mu _ { 2 } + \mu _ { 3 } + \mu _ { 4 } = 1$

当 $M$ 点位于空间四面体 $( \mathit { T } )$ 的内部时有 $0 \leqslant$ $\mu _ { 1 } ~ \mu _ { 2 } ~ \mu _ { 3 } ~ \mu _ { 4 } \leqslant 1$ ；当 $M$ 点位于空间四面体（T）的外部时如果 $M$ 点和 $V _ { i }$ 点位于 $F _ { i }$ 的同一侧则 $\mu _ { i }$ 为正；如果 $M$ 点和 $V _ { i }$ 点分别位于 $F _ { i }$ 的两侧则 $\mu _ { i }$ 为负;特别的，如果 $\mu _ { i }$ 为0,则点 $M$ 位于空间四面体$( \mathit { T } )$ 的第 $i$ 个面（与顶点 $V _ { i }$ 相对的面）上。

以第2.1节中的 $( \ T _ { _ 2 } ) \ = \ V _ { _ 2 } V _ { _ 3 } V _ { _ 4 } V _ { 5 }$ 作为主四面体， $V _ { 1 }$ 为第五点得到的4个 $\mu$ 值如图10所示。

![](images/1c509e05f3fa89d05f521992779faca3c45a8b6fbbca955f7fd6a2db98ccba9b.jpg)  
图10 $\mu$ 值曲线Fig.10Curve of $\mu$ （204号

![](images/b9245a464f3b35fe2b38b95626c24c96bf341c5c0218806b8b8e22ffed03c28d.jpg)  
Fig.9Vertices and faces of tetrahedron   
图11改进的 $P \mathcal { L }$ 曲线 Fig.11Improved $P \mathcal { L }$ curve

由图10可以判断空间第五点相对于主四面体的位置关系同时能够看出随着主四面体的扁度增加 ${ } _ { , \mu }$ 值将出现极值当 $\mu \geqslant 1 0$ 时我们认定四面体为近共面状态。

当主四面体共面时我们从中选取构成三角形面积最大的三个点，与空间第五点共同组成新的四面体并称为辅四面体图11中曲线 $P 2$ 是主四面体的扁度曲线 $P 4$ 是辅四面体的扁度。对比图10和图11可以看出在主四面体构型劣化的两个时间段（虚线之间）， $P 4$ 曲线可以有效弥补 $P 2$ 数值过大的状态因此空间第五点加入后构成的辅四面体可以有效提高整体探测效能。图11中同时给出了主辅四面体的空间尺度 $L 2$ 和 $L 4$ 的曲线。

由上述评估结果知，可以通过调整空间第五颗航天器的轨道参数来优化辅四面体的性能，使得其在主四面体指标劣化时能够提供更好的测量贡献。完成上述优化设计后，可以重新采用将空间五点构型分解为五个四面体的方法进行主四面体的确定，有可能主四面体所包含的四个顶点会发生变化；此时再次使用第二种方法对新的第五点航天器轨道参数进行优化如此迭代可以将寻找最优设计方案的过程变得简化。

# 3结论

本文总结归纳了已有的空间物理场四点协同探测构型性能评价方法，并通过“将空间五点构型分解为五个四面体”和“将空间五点构型分解为主四面体加第五点问题”两种方法将其推广应用到空间五点协同探测星簇构型探测效能评价中，并对所提出的评价参量进行了仿真校验。在实际任务方案设计过程中,采用该方法不仅能够较好地定量评价空间五点构型的性能优劣，还可以通过两种评估方法迭代使用快速寻找最优的空间五点协同探测星簇构型设计方案实现整个轨道周期内较好的探测性能。

# 参考文献

[1］张永维，袁仕耿．地球空间双星探测计划[J]．中国航天， 2008(5):12-17．[Zhang Yong-wei,Yuan Shi-geng.Geospace double star exploration program [J]．Aerospace China，2008 (5):12-17.]   
[2] Curtis S A. The Magnetospheric multiscale mission .resolving fundamental processes in space plasmas [R].Maryland,USA: NASAGoddard Space Flight Center，Greenbelt，December 1999.   
[3] Guzman J，Schiff C．A preliminary study for a tetrahedron formation quality factors and visualization [C].AIAA/AAS Astrodynamics Specialist Conference and Exhibit，Califorinia， USA,August5 -8,2002.   
[4] Harvey C.Spatial gradients and the volumetric tensor [R]. Noordwijk,Noordwijk:ISSI Report SR-OO1,ESA Publications Division,1998.   
[5] Robert P，Roux A，HarveyC，et al.Tetrahedron geometric factors[R].Noordwijk,Noordwijk:ISSI Report SR-OO1,ESA Publications Division,1998.   
[6]Edery A,Schiff C.The double lunar swingby of the MMS mission

[C]．The 16th International Symposium on Space Flight

Dynamics,Pasadena,California,December 2001. [7］印桂生，李艳波，张菁等．四面体模型质量度量准则及其 之间的关系［J]．计算力学学报 $, 2 0 1 2 , 9 ( 1 ) : 5 5 - 6 0$ [Yin Gui-sheng,Li Yan-bo,Zhang Jing,et al.Relationship between quality measures criterion of tetrahedral mesh [J].Chinese Journal of Computational Mechanics,2012,9(1):55-60.] [8]Liu A,Joe B.Relationship between tetrahedron shape measures [J].Numerical Mathematics, $1 9 9 4 ( 3 4 ) \div 2 6 8 - 2 8 7$ [9]Lo S H.Optimization of tetrahedral meshes based on element shape measures [J].Computers & Structures,1997,63(5):   
951 -961. [10]Yang Z,Niu W L,Gao C.Research on the payload coverage analysis of space science exploration [C],The 64th International Astronautical Congress，Beijing，China，September 23- 27，   
2013. [11]明建国．关于正多面体只有五种的证明[J]．数学通报，   
1994(11):37-38．[Ming Jian-guo.Proof of existing only five regular polyhedra [J]．Math Bulletin,1994(11):37-38.] [12]安雪滢，郗晓宁，张为华等．大椭圆轨道航天器四面体编队 运动分析设计[J]．国防科技大学学报,2007,29(5)：21-   
24．[An Xue-ying，Xi Xiao-ning，ZhangWei-hua，et al. Analysisand optimization design of tetrahedron formation spacecrafts in highly elliptic orbits[J]．Journal of National University of Defense Technology $, 2 0 0 7 , 2 9 ( 5 ) : 2 1 - 2 4 . ]$ （20 [13]马可锌，王惠南，付世勇．基于对偶四元数的编队飞行卫星 相对位姿描述及算法研究[J]．宇航学报,2011,32（9)：   
1871-1877．[Ma Ke-xin，Wang Hui-nan，Fu Shi-yong. Research on relative position and attitude representation and algorithm for formation flying satellites based on dual-quaternion [J].Journal of Astronautics ,2011 ,32(9):1871-1877.]

# 作者简介：

杨震(1972-）男博士研究员主要从事复杂系统仿真、半实物仿真、仿真评估、空间任务协同设计、地面应用系统、空间信息应用等方面的研究。  
通信地址：北京市海淀区中关村南二条1号B座0368(100190)电话：(010)62630420  
E-mail: Yangzhen $@$ nssc. ac.cn

(编辑:牛苗苗)