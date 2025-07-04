# 无线传感器网络中基于虚拟力的覆盖算法

张淳

(南京邮电大学 计算机学院、软件学院、网络空间安全学院，南京 210023)

摘要：在无线传感器网络的很多应用场景中，大量的传感器节点被任意播撒在被监测区域内，形成很多覆盖空洞，对无线传感网络的感知、监测和数据采集能力造成很大影响。为了解决无线传感器网络中的覆盖问题，提出了一种基于虚拟引力的覆盖算法。首先，根据虚拟引力产生的约束条件和引力大小，一种扩大网络覆盖范围的算法被提出，算法分析证明这种算法能够减少覆盖空洞；第二，提出了维持邻居节点的连通性的方法；第三，提出一种覆盖感兴趣区域的算法。仿真结果表明，这种算法既能提高网络的覆盖能力，又能减少传感器节点的移动距离。

关键词：无线传感器网络；覆盖算法；连通性 中图分类号：TP393.06 doi: 10.3969/j.issn.1001-3695.2018.01.0008

# Coverage algorithm based on virtual forces in wireless sensor networks

Zhang Chun (School ofComputer Science,Nanjing University ofPosts &Telecommunications,Nanjing 210023,China)

Abstract: Inmanyapplications,alarge numberofsensor nodes are randomlydeployed in themonitoredarea.There exits many coverageholes,whichafectthe sensing,detectinganddatacollectingcapabilityofwirelesssensornetworks.Iordertosolve thecoverageproblem,acoveragealgorithmbasedonthevirtualforceswasproposedinthispaper.First,basedonthecostraints and strengthof thevirtualforces,an enhanced coverage algorithm was proposed.Algorithmanalysis proves thatthealgorithm can decreasecoverage holes.Second,a connectivitypreserved method forthe neighboring nodes was proposed.Third,a coverage algorithm forthe interestedarea was proposed.Simulationresults showsthat,theproposed algorithmcan extend the coverage of wireless sensor networks,and decrease the moving distance of the sensor nodes.

Key words:wireless sensor network;coverage algorithm; connectivity

# 0 引言

无线传感器网络包括大量的传感器节点，这些节点集成了感知模块、通信模块、数据处理模块和电源模块[1,2]。随着传感器技术和计算机网络通信技术的发展，移动无线传感器网络广泛地应用于各个领域，例如交通管理、智能工业制造、农业生产等等，传感器节点具有自主移动和自组织的能力[3.4]。当传感器网络对环境进行感知监测时，必须首先对被监测领域进行覆盖，因此，网络的覆盖算法是一个很重要的研究问题[5.6]。

文献[7,8]致力于研究“K覆盖”问题，研究目标是激活一部分传感器，使得被监测领域内的每个位置至少被K个传感器覆盖。文献[9]提出一种带有障碍物的长条形区域的覆盖方法，当穿过该区域的所有路径是“K覆盖”时，该区域被称为被全方位的传感器网络“K障碍性覆盖”。因为“障碍性覆盖”问题致力于研究所有穿过长条形区域的路径的覆盖问题，很多已提出的覆盖方法不能直接用于解决该问题。文献[10]提出了一种分布式的优化覆盖算法。文献[11]要解决的问题是确保覆盖区域所需的传感器数量，覆盖问题被建模成了一种决策问题。基于虚拟力的算法是广泛应用在覆盖问题中的一种算法，这种算法的原理是，当两个节点之间的距离较近时，它们之间将产生斥力，当两个节点之间的距离较远时，它们之间将产生引力。文献[12,13]中通过斥力扩大网络的覆盖范围，文献[13]指出距离最近的节点互相影响最大。文献[14]提出了一种基于分簇的覆盖算法，分别考虑了一种二进制感知模型和一种基于概率的感知模型，节点的位置根据其他节点和障碍物施加的斥力来计算。

本文提出了一种基于引力的全局覆盖算法，在扩大网络覆盖范围的同时保持网络的连通性，并将这种覆盖算法推广到对感兴趣区域的覆盖场景中，仿真实验证明，这种算法在不同的网络参数下，能有效提高网络的覆盖率。

# 1基于虚拟力的算法基本原理

虚拟力包括引力和斥力。利用虚拟作用力的方法扩大无线传感器网络对被监控区域的覆盖范围，可以理解为节点之间互相施加虚拟的引力或斥力。在引力作用下，当节点之间距离较远时，它们会向着对方移动，从而减少了被监测范围内的覆盖空洞，达到扩大覆盖率的目的。在虚拟引力的作用下，节点受到来自相邻一个或多个节点的引力作用，下面对节点受力的计算方法进行描述。如图1（a)所示，圆圈代表节点的感知区域，当满足条件 $d ( i , j ) > d _ { t h }$ 时（ $d _ { t h }$ 为一个距离门限)，节点的感知区域之间有可能存在未被覆盖的领域，所以这些节点之间才存在引力，该引力作用于 $S _ { i }$ 和 $S _ { j }$ 上，是一对作用力与反作用力，分别用 $\vec { f } _ { i j }$ 和 $\vec { f } _ { j i }$ 表示，它们大小相同，方向相反。

当节点分布密集时，在斥力的作用下，节点会向着远离对方的方向移动，节点的感知区域之间的重叠部分会减少，这种方法同样可以扩大无线传感器网络对被监测区域的覆盖范围，最终达到被覆盖区域最大化的目的。一个节点可能受到来自一个或多个节点的斥力作用，图1(b)给出了节点受力的示意图，$S _ { i }$ 和 $S _ { j }$ 之间存在斥力的作用，该斥力作用于 $S _ { i }$ 和 $S _ { j }$ 上，是一对作用力和反作用力，分别用 $\vec { f } _ { i j }$ 和 $\vec { f } _ { j i }$ 表示，它们大小相同，方向相反。

![](images/fc54bf5736e1d89ef58b34e02cc97c62e3901bb3dae088e1697ffbbebc08a403.jpg)  
图1引力和斥力的示意图

# 2 基于虚拟引力的网络覆盖算法

# 2.1全局覆盖策略

a）初始阶段，当可移动的传感器节点被播撒在被监控区域后，无线传感器网络的拓扑是连通的；

b)所有节点都有相同的感知半径 $r _ { s }$ 和通信半径 $r _ { c }$ ，节点的感知区域和通信区域的模型分别为以节点为圆心， $r _ { s }$ 和 $r _ { c }$ 为半径的圆，距离一个节点的欧式距离小于 $\boldsymbol { r _ { c } }$ 的节点被称为该节点的一跳邻居节点；

c）节点已知自己的位置和邻居节点的位置，位置信息可以通过节点内置的硬件设备如GPS或节点定位算法获得；

d)算法执行过程由若干时间段构成，每个时间段是一段固定的时间，每个时间段计算得到的节点需要移动的距离不一定相同，在每个时间段末，节点沿着直线移动到要到达的目标点。

由于节点的感知区域为一个圆，当节点被布设在被监测区域时，如果节点的感知区域彼此都不重叠，如图2(a)所示，这种方法虽然能减少覆盖被监测区域所需要的节点的数目，但是采用这种方法，会形成覆盖空洞；因此，为了扩大传感器网络的覆盖范围，减少覆盖空洞，在布设节点的时候，就要让节点的感知区域互相重叠，但是如果重叠范围过大，又会造成传感器资源的浪费，因此为了扩大传感器网络的覆盖范围，同时减少覆盖一个区域所需的节点数量，节点之间的距离门限被设置为 $\sqrt { 3 } r _ { s }$ ，如图2(b)所示。

假设在被监测区域内有一个坐标点 $g _ { \scriptscriptstyle { k } }$ ，坐标值为 $( x , y )$ ，使用感知模型将物理信号转换为节点对区域的探测度的表达，则节点 $S _ { i }$ 对 $g _ { \scriptscriptstyle k }$ 的覆盖率可以被表达为 $S _ { i }$ 对位于 $g _ { \scriptscriptstyle { k } }$ 处的目标的探测概率 $c _ { i } ^ { k }$ 。设 $S _ { i }$ 的坐标值为 $( x _ { i } , y _ { i } )$ ， $S _ { i }$ 和 $g _ { \scriptscriptstyle k }$ 之间的欧式距离用 $d ( i , k )$ 表示， $d ( i , k ) = \sqrt { \left( x _ { k } - x \right) ^ { 2 } + \left( y _ { k } - y \right) ^ { 2 } }$ 。传感器节点的感知模型可用式（1）表示，为二进制模型。

$$
c _ { i } ^ { k } = \left\{ \begin{array} { l l } { 1 } & { i f \quad d ( i , k ) \leq r _ { s } } \\ { ~ 0 } & { o t h e r w i s e } \end{array} \right.
$$

![](images/79de6ae6083cf369475f0250fce374f49e6c1fc0bc6806a4dad56036eb631204.jpg)  
图2无重叠和有重叠的节点分布方式

网络的初始拓扑结构用 $\mathbb { Z } = ( V , \varepsilon )$ 表示，其中 $\boldsymbol { V }$ 表示拓扑图的顶点，每个顶点代表一个传感器节点， $\boldsymbol { \varepsilon }$ 表示拓扑图的边界，用式（2）表示，由 $\varepsilon$ 得到的节点的一跳邻居节点用式（3）表示。

$$
\varepsilon = \left\{ ( i , j ) \in V ^ { 2 } \left| i \neq j \land d ( i , j ) \leq r c \right. \right\}
$$

$$
N ( i ) = \left\{ j \in V { \big | } ( i , j ) \in \varepsilon \right\}
$$

其中： $i$ 和 $j$ 为节点 $S _ { i }$ 和 $S _ { j }$ 的标志号， $d ( . )$ 表示节点 $S _ { i }$ 和 $S _ { j }$ 之间的欧氏距离。

当且仅当 $S _ { i }$ 和 $S _ { j }$ 满足式(4)时，它们之间的距离可能满足式（5)，也可能满足式(6)，当 $S _ { i }$ 和 $S _ { j }$ 同时满足式(4）和（6)时，它们之间产生引力，用式（7）表示，其中 $j \in N ( i )$ ， $\gamma$ 为系数， $\theta _ { i j }$ 为作用力的方向。

$$
r _ { c } \ge \sqrt { 3 } r _ { s }
$$

$$
d ( i , j ) \leq \sqrt { 3 } r _ { s }
$$

$$
d ( i , j ) > \sqrt { 3 } r _ { s }
$$

$$
\vec { \pmb { f } } _ { i j } = ( \gamma ( d ( i , j ) - \sqrt { 3 } r _ { s } ) , \theta _ { i j } )
$$

# 2.2维持连通性

根据2.1节中的假设，网络中的节点在初始状态是连通的。需要注意的是，当执行2.2节的全局覆盖算法后，节点并不移动，而是根据执行算法后得到的结果得到一个新的拓扑结构，用 $\mathbb { Z } _ { \ell } = ( V ,  { \varepsilon } _ { \ell } )$ 表示，其中 $\varepsilon _ { \ell } = \left\{ ( c , g ) \in V ^ { 2 } \Big | c \neq g \land D ( c , g ) \leq r _ { c } \right\} .$ （根据节点的新坐标得到的节点之间的欧式距离用 $D ( . )$ 表示。式(8)为由 $\boldsymbol { \varepsilon } _ { \iota }$ 得到的节点的一跳邻居节点的表达式。接下来节点执行本节提出的维持连通性的算法，然后节点再移动到新位置。

$$
N _ { \ell } ( c ) = \left\{ g \in V { \big | } ( c , g ) \in \varepsilon _ { \ell } \right\}
$$

由于 $\mathbb { Z } _ { \ell }$ 拓扑结构不一定连通，为了维持 $\mathbb { Z } _ { \varepsilon }$ 的连通性，网络中的任一节点 $S _ { i }$ 都要维持和 $N ( i )$ 的连通性，当 $S _ { i } \setminus S _ { n }$ 满足式（9）时， $S _ { i }$ 和 $S _ { n }$ 之间会产生一个虚拟引力，引力用式（10)表示。

$$
D ( \mathbf { \chi } _ { i \in V } , \mathbf { \chi } _ { n \in N ( i ) } ) > r _ { c }
$$

$$
\left\{ \begin{array} { l l } { \displaystyle { \vec { f } } _ { i n } = ( \frac { 1 } { 2 } ( D ( i , n ) - r _ { c } ) , \theta _ { i n } ) } \\ { \displaystyle { \vec { f } } _ { n i } = ( \frac { 1 } { 2 } ( D ( n , i ) - r _ { c } ) , \theta _ { n i } ) } \end{array} \right.
$$

Z=(V,ε)是由z得到的执行全局覆盖算法后的网络拓扑结构图。当 $S _ { i }$ 和 $S _ { n }$ 为了维持网络连通性而产生虚拟力时， $S _ { i }$ 和 $S _ { g }$ 之间的欧式距离将发生改变（其中 $g \in N _ { \ell } ( i )$ 且 $g \not \in N ( i ) ^ { \ ) }$ ，为了兼顾网络连通性和网络覆盖增强，在维持网络连通的过程中，任一节点 $S _ { i }$ 要保持和节点 $S _ { g }$ 之间的欧式距离等于 $D ( i , g )$ ，（204 $S _ { i }$ 要对 $S _ { g }$ 产生一个虚拟引力 $\vec { f } _ { g i }$ ， $\vec { f } _ { g i }$ 的表达式为 ${ \vec { f } } _ { g i } = { \vec { f } } _ { i n }$ 。

综上所述，为了扩大对被监测区域的覆盖率，同时维持网络的连通性，节点 $S _ { i }$ 受到的合力用式（11）表示，其中 $S _ { j }$ 和 $S _ { n }$ 分别满足式（6）和（9)。

$$
{ \vec { F } } _ { i } = \sum { \vec { f } } _ { i j } + \sum { \vec { f } } _ { i n }
$$

当算法经过若干次的迭代后，假如节点在每个时间段移动的距离小于门限值 $\Delta d$ ，则认为节点的移动是来回振荡式的移动，这种移动方式会导致算法不能收敛。为了保证算法的收敛性，当传感器网络对被监测范围的覆盖率满足式（12）时，算法终止，其中 $C _ { A }$ 表示在当前的时间段末，传感器网络对被监测区域 $A$ 的覆盖范围， $C _ { t h }$ 为覆盖率的期望值， $\Delta C$ 为覆盖率的阈值。

$$
\left. C _ { A } - C _ { t h } \right. < \Delta C
$$

图3显示的是全局覆盖算法的伪码。对于任一节点来说，执行算法共包括三个步骤，首先是判断和邻居节点之间是否存在覆盖空洞，其次是通过虚拟引力减少覆盖空洞，最后要根据新坐标判断网络的连通性是否得到保持，如果没有，要通过虚拟引力的作用维持和原邻居节点之间的连通性。

定理对于任一节点 $S _ { i }$ ，当执行完全局覆盖算法之后，它和邻居节点之间的距离小于3r。

证明：a）r≤rs

在这种情况下，可以得到式（13）。

$$
d ( i , j ) \leq r _ { s } < \sqrt { 3 } r _ { s }
$$

b） $r _ { s } < r _ { c } < \sqrt { 3 } r _ { s }$

在这种情况下，同样可以得到式（13）。

$$
r _ { c } \ge \sqrt { 3 } r _ { s }
$$

在这种情况下，当 $\boldsymbol { d } ( i , j )$ 满足式(5)时，可以得到式（13);当 $d ( i , j )$ 满足式（6）时，在式（7）所示引力的作用下， $\boldsymbol { d } ( i , j )$ （20满足式（14)。当式（7）所示的引力导致 $S _ { i }$ 无法保持和邻居节点的连通性时， $S _ { i }$ 会受到式（10）所示的引力，同时 $S _ { i }$ 会给 $S _ { j }$ 一个引力，这两个力大小相同，因此 $\boldsymbol { d } ( i , j )$ 仍旧能够满足式(14)

$$
d ( i , j ) < \sqrt { 3 } r _ { s }
$$

综上所述，通过执行全局覆盖算法，任意一个节点和邻居节点之间的距离满足距离门限√3r。

# $/ \ast$ 覆盖评估\*/

1.For $P _ { k } ( x _ { k } , y _ { k } ) \in I$   
2. For $S _ { a } \in \left\{ S _ { 1 , } S _ { 2 , . . . , S _ { n } } \right\}$ （20   
3. Calculate $c _ { _ a } ^ { k }$ using $( d ( a , k ) , r _ { s } )$ （20   
4. End   
5.End   
6.If coverage probability is met: $\left| C _ { _ { I } } - C _ { _ { t h } } \right| < \Delta C$   
7．Break from While loop;   
8.End   
$9 . / ^ { * }$ 虚拟力计算\*/   
10.For $S _ { i } \in \left\{ S _ { 1 } , S _ { 2 } , . . . , S _ { n } \right\}$ （204号   
11. Calculat $\mathrm { ~ e ~ } _ { f _ { i j } } \mathrm { ~ u s i n g ~ } \gamma \mathrm { ~ } , d ( i , j ) \mathrm { ~ } , r _ { s } , \theta _ { i j } , r _ { c }$   
12. $\vec { F _ { i } } = \sum \vec { f _ { i j } } , j \in N ( i ) \ , d ( i , j ) > \sqrt { 3 } r _ { s }$   
13.End   
14./\*维持连通性\*/   
15.For $S _ { i } \in \left\{ S _ { 1 } , S _ { 2 } , . . . , S _ { n } \right\}$   
16. 旺 $D ( \mathbf { \chi } _ { i \in V } , \mathbf { \chi } _ { n \in N ( i ) } ) > r _ { c }$ （204   
17. fn=(²(D(i，n)-r），θn)   
2   
18. F=F+Fm   
19. End   
20.End

# 2.3覆盖感兴趣的目标区域

2.1节中论述了节点全局覆盖算法的基本思想，在现实的很多应用领域中，只需要监控一个感兴趣的区域，而不需要对整个区域进行监控。在这种情况下，令无线传感器网络进行全局覆盖会造成资源的严重浪费。因此，本节提出了一种对感兴趣区域进行覆盖的算法。

这种算法的思想是，通过感兴趣的区域对节点产生的虚拟引力，促使节点向着该区域移动。

考虑到 $n$ 个节点被布设在被监测区域 $A$ 内， $A$ 内有一个感兴趣的长方形区域 $I$ ，用 $P _ { k } ( x _ { k } , y _ { k } )$ 表示 $\boldsymbol { { \mathbf { \mathit { I } } } }$ 内的任一点，其中$\boldsymbol { x } _ { k } \in \left[ 0 , x _ { I } \right]$ ， $y _ { k } \in \left[ 0 , y _ { I } \right]$ 。 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 3 }$ ， $P _ { 4 }$ ， $P _ { 5 }$ 分别是 $I$ 内的五个点，它们的坐标分别是 $[ 0 , 0 ]$ $, 0 ] ~ , ~ [ 0 , y _ { I } ^ { } ] ~ , ~ [ x _ { I } ^ { } , 0 ] ~ , ~ [ \frac { x _ { I } ^ { } } { 2 } , \frac { y _ { I } ^ { } } { 2 } ] ~ $ $[ x _ { I } , y _ { I } ]$ 。对于任一节点 $S _ { i }$ ，它收到的来自 $I$ 的虚拟引力 $\vec { F _ { i I } }$ 用式（14）表示，其中 $d ( i , k )$ 为 $P _ { \boldsymbol { k } }$ 和 $S _ { i }$ 之间的距离， $\alpha$ 为系数， $\theta _ { i k }$

为作用力方向。

在扩大对 $\boldsymbol { \mathbf { \ell } } _ { I }$ 的覆盖率阶段，任一节点 $S _ { i }$ 受到的作用力用式（17）表示，其中 $S _ { j }$ 满足式（4）和（6)，且 $j \in N ( i )$ 。

$$
\vec { \boldsymbol { f } } _ { i k } = ( \alpha d ( i , k ) , \boldsymbol { \theta } _ { i k } )
$$

$$
\vec { F _ { i I } } = \sum _ { k = 0 } ^ { 5 } \vec { f _ { i k } }
$$

$$
\stackrel {  } { F _ { i } } = \stackrel {  } { F _ { i I } } + \sum \stackrel {  } { f _ { i j } }
$$

节点 $S _ { i }$ 根据式(17)计算出新坐标后，并不移动到新坐标，而是应用1.3节中提出的维持连通性的算法，从而得到 $S _ { i }$ 受到的合力如式（18）所示。在每个时间段末，节点根据所受合力，计算移动的方向和距离，其中 $S _ { n }$ 满足式（9）， $\vec { f } _ { i n }$ 用式（10）表示。

$$
\stackrel {  } { F _ { i } } = \stackrel {  } { F _ { i I } } + \sum \stackrel {  } { f _ { i j } } + \sum \stackrel {  } { f _ { i n } }
$$

算法的伪码如图4所示。

$/ *$ 覆盖评估 $^ { * } / ^ { }$

1.For $P _ { k } ( x _ { k } , y _ { k } ) \in I$ （204号   
2. For $S _ { a } \in \left\{ S _ { 1 , } S _ { 2 , . . . , S _ { n } } \right\}$   
3. Calculate $c _ { i } ^ { k }$ using $( d ( i , k ) , r _ { s } )$ （20   
4. End   
5.End   
6.If coverage probability is met: $\left. C _ { _ { I } } - C _ { _ { t h } } \right. < \Delta C$   
7．Break from While loop;   
8.End   
$9 . / { ^ { * } }$ 虚拟力计算 $^ { * } I$   
10.For $S _ { a } \in \left\{ S _ { 1 } , S _ { 2 } , . . . , S _ { n } \right\}$   
11. F=F+∑f+∑f   
12. Calculate Fu using α,d(i,k),0i   
13. E=   
k=0   
14.End

# 3 仿真结果

本节中，对上节提出的覆盖算法的性能进行仿真分析。仿真中，被监测区域的尺寸为 $4 0 0 \times 4 0 0$ ， $\alpha$ 、γ和 $\Delta C$ 分别被设置为0.5、0.5和0.1。

首先对上节提出的维持连通性的全局覆盖策略进行分析，这种算法被简称为FBDA，本文将文献[13]中提出的CPCM算法与FBDA算法进行比较。CPCM算法的基本思想是，通过节点间产生的斥力推动节点不断向外移动，从而实现扩大网络的覆盖率的目标。

为了验证算法的性能，本文通过改变算法的各种参数来观察其对算法产生的影响。图5考察了当节点的数量改变时，对被监测区域的覆盖率产生的影响。从图中可以看出，随着节点的数量由10增加到90，网络的覆盖率不断增加，且应用FBDA算法，传感器网络对被监测区域的覆盖率要高于CPCM算法。这是因为，应用CPCM算法，节点在斥力的作用下，不断向外移动，使得传感器网络的覆盖范围不断扩大，而应用FBDA算法，在虚拟引力的作用下，覆盖空洞周围的节点会向着覆盖空洞移动，从而提高了对被监测范围的覆盖率，节点的移动以减少覆盖空洞为目的，避免了盲目移动造成的冗余运动，另外，提出的算法终止条件避免了节点来回振荡式的运动。从图中还可以看出，随着感知半径和通信半径的增加，网络的覆盖率得到提高。

![](images/ebb14b6d4c2bf53f6f28d7f07dc07716d988598617f8ace346d9f148e8835b34.jpg)  
图4感兴趣区域覆盖算法伪码

图6显示的是传感器节点移动的平均距离和节点数量的关系图。从图中可以看出，应用FBDA算法，节点移动的平均距离要小于CPCM算法，且随着传感器数量的增加，节点移动的距离不断增加。在算法执行的每个时间段，节点在执行扩大覆盖率和维持连通性的算法后，才根据所受到的合力计算移动的距离和方向，且节点的移动方向根据覆盖空洞的位置得到，避免在移动的过程中扩大节点感知区域的重叠范围，从而减少了节点不断调整位置以兼顾覆盖率和连通性的次数。

![](images/90920bd77dd369dd3f19eb7d2a8d70e7b6997bccaa339e80b8727f56e3bb8ab3.jpg)  
图5覆盖率和传感器数量的关系图

![](images/edf462fe7b04f4b63ba7009c952367fc4aad4bbf6f1b76dd50ef15e1d469dce1.jpg)  
图6节点移动的平均距离和传感器数量的关系图  
图7覆盖率和算法迭代次数的关系图

![](images/1547a882aed26b36ad944de6a0d9205dac2346f825aa2ca0b082f1b5b96c2e71.jpg)  
图8对 $I$ 覆盖率和传感器数量的关系图

为了进一步强调节点的数量对覆盖率的影响，图7分析了覆盖率和算法迭代次数的关系。图中的三条曲线分别代表应用FBDA算法，节点数量取20、40和60的情况，从图中可以看出，随着迭代次数的增加，网络的覆盖率不断增加，当迭代次数增加到一定程度时，网络的覆盖率不再继续增大；且随着被监测区域中节点数量的不断增加，传感器网络对节点的覆盖率也在不断增加。

图8分析的是FBDA算法在对感兴趣的区域】进行覆盖时的性能表现。仿真中，感兴趣的区域中心是被监测区域的中心，区域的尺寸为 $2 0 0 \times 1 8 0$ 。随着传感器的数量从10增加到 50,应用FBDA算法得到的覆盖率逐渐增加，且FBDA算法的性能要优于CPCM算法。这是因为，应用FBDA算法，节点受到的来自 $\boldsymbol { \mathbf { \ell } } _ { I }$ 的虚拟引力促使它们向着 $I$ 移动，然后节点再通过相互作用的引力填补对 $I$ 的覆盖空洞，因此节点的运动能够有效提高对 $I$ 的覆盖率。随着节点感知半径和通信半径的增加，覆盖相同尺寸的区域所需的节点数量降低，因此在节点的数量不足够多的情况下，节点对 $I$ 的覆盖率得到提高。

# 4 结束语

无线传感器网络的覆盖策略直接影响到网络的性能和服务质量，有效的覆盖方法不仅能优化网络的资源，还能提高网络的监测性能。本文首先提出了一种基于虚拟引力的维持连通性的全局覆盖算法，然后将这种算法扩展到监测感兴趣区域的场景。仿真分析证明，在不同的网络性能指标下，这种算法能提高网络覆盖率，并减少节点的移动距离。

# 参考文献：

[1]Yang Changlin,Chin K.Novel algorithm for complete targets coverage in

energy harvesting wireless sensor networks [J]. IEEE Communications Letters,2014,18(1): 89-94.   
[2]Xing Xiaofei,Wang Guojun,Li Jie.Polytype target coverage scheme for heterogeneous wireless sensor networks using linear programming [J]. Wireless Communications and Mobile Computing,2014,14(8): 1397-1408.   
[3]Song Jing,Cong Li,Ge Jianhua,et al.A dynamic resource allocation approach using cooperative game theory for two-tie networks [J].Journal of Xi'an Jiaotong University,2012,46 (10): 89-94.   
[4]Erdelj M,Loscri V,Natalizio E,et al.Multiple point of interest discovery and coverage with mobile wireless sensor [J].Ad Hoc Networks,2013,11 (8): 2288-2300.   
[5]Vempaty A, Ozdemir O,Agrawal K,et al. Localization in wireless sensor networks: Byzantines and mitigation techniques [J]. IEEE Trans on Signal Processing,2013,61(6): 1495-1580.   
[6]李建坡，穆宝春．基于协同预测的无线传感器网络全移动节点定位算 法[J].计算机应用研究,2017,34(1):186-201.   
[7]Huang C F, Tseng Y C.The coverage problem in a wireless sensor network [J]. Mobile Networks and Applications,2005,10 (4): 519-528.   
[8]Simon G, Molnar M, Gonczy L,Cousin B.Robust K-coverage algorithms for sensor networks [J]. IEEE Trans on Instrumentation and Measurement, 2008,57 (8): 1741-1748.   
[9]Kumar S,Lai T H,Arora A. Barrier coverage with wirelesssensors [J]. Wireless Networks,2007,13 (6): 817-834.   
[10]LiM, WanPJ,FriederO. Coverage inwirelessad hoc sensor networks[J]. IEEE Trans on Computers,2003,52(6): 753-763.   
[11] Huang C F, Tseng Y C.The coverage problem in a wireless sensor network [J].Mobile Networks and Applications,2005,10 (4): 519-528.   
[12] Heo N,Varshney PK.Energy-efficient deployment of intelligent mobile sensor networks [J]. IEEE Trans on Systems, Man,and Cybernetics-Part A, 2005,35 (1): 78-92.   
[13] Thhiry R,David SR.Connectivity preservation and coverage schemes for wireless sensor networks [J]. IEEE Trans on Automatic Control, 2011,56 (10): 2418-2428.   
[14] Zou Y, Chakrabarty K.A distributed coverage and connectivity centric technique for selecting active nodes in wireless sensor networks [J]. IEEE Trans on Computers,2005,54(8): 978-991.