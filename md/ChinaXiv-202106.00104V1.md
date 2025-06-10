# 自对偶地图上的伊辛模型及相变临界点

张孝伍  
(青岛理工大学理学院，山东 青岛 266520)  
E-mail:zxwaa@qut.edu.cn

摘要：给定连通地图 $M = ( V , E , F )$ ，在每个节点 $\nu$ 处赋于一个自旋，每条边上的两个节点有相互作用，得到地图 $M$ 上的伊辛模型.由伊辛模型的对偶变换，给出了自对偶地图上伊辛模型相变临界点 $\boldsymbol { K } ^ { * }$ 的上下界： $0 . 2 4 0 6 \leq K ^ { * } \leq 0 . 7 2 1 8$ ，并且得到三维自对偶伊辛模型的相变临界点: $\boldsymbol { K } ^ { * } = 0 . 5 2 6 9$ ：

关键词：连通地图;伊辛模型;对偶变换;相变临界点

Ising model and critical point of phase transition on self dual map ZHANGXiao-Wu

Abstract: Given connected map ${ \bf M } { = } ( \mathrm { V } , \mathrm { E } , \mathrm { F } )$ ,each node $\mathrm { \Delta V }$ is assigned a spin, two nodes on each edge interact, the Ising model on map m is obtained.Dual transformation from Ising model, The upper and lower bounds of the critical point $\kappa ^ { * }$ of the phase transition of Ising model on the self dual map are given: $0 . 2 4 0 6 \leqslant \mathrm { K } ^ { * } \leqslant 0 . 7 2 1 8$ ，the critical point of phase transition of the three-dimensional self dual Ising model is obtained: $\mathrm { K ^ { * } } \mathrm { = } 0 . 5 2 6 9$ ：

Key words: Connected map; Ising model; Dual transformation; Critical point of phase transition

# 1引言

设有连通地图 $^ { [ 1 ] } M = ( V , E , F )$ ，对每一个节点 $\nu \in V$ 处赋于自旋 $\sigma _ { \nu }$ ,每条边$\boldsymbol { e } = ( u , \nu )$ 的两个节点之间有相互作用量 $J _ { ( u , \nu ) }$ ，如此得到地图 $M$ 上的伊辛模型[2].

当地图 $M = ( V , E , F )$ 是一个环形图时，伊辛模型[34是一维的， $M$ 是连通度大于3的平面图时，伊辛模型是二维的． $M$ 的亏格不等于1时，伊辛模型是三维以上的.

伊辛模型是统计力学的一个多体相互作用模型，可以用来描述非常广泛的物理现象.如晶体的磁性，合金中的有序无序转变和相变临界现象等.一维、二维伊辛模型都有精确解，目前为止，三维伊辛模型还没有得到精确解5.用低温展开、高温展开、重整化群和MonteCarlo模拟等方法，能够得到三维伊辛模型的一些近似解[6,7,8].

参考文献中［5」介绍了三维伊辛模型的数学结构与精确解猜想，从拓扑、代数和几何角度对三维伊辛模型的数学结构进行了评述.分析了三维伊辛模型的转移矩阵、拓扑理论中的纽结变换、Yang-Baxter方程和四面体方程之间的关系

文献[9]中给出了自对偶地图和无手征性纽结的构造方法，在文献中[10」，也给出了可逆纽结的构造方法．纽结的无手征性就是对应于伊辛模型上的自对偶变换性，纽结的可逆性就是对应于伊辛模型格点之间相互作用的对称性

文中利用地图 $M$ 上伊辛模型的对偶变换，给出了自对偶地图上伊辛模型相变临界点的上下界，并且得到三维自对偶伊辛模型的精确相变临界点.

# 2地图上伊辛模型的配分函数展开

设有连通地图 $M = ( V , E , F )$ ，其上伊辛模型的Hamiltonian 量[2是:

$$
H \{ \sigma _ { \nu } \} = - \sum _ { ( u , \nu ) \in E } \beta J _ { ( u , \nu ) } \sigma _ { u } \sigma _ { \nu } - \mu \beta B \sum _ { \nu \in V } \sigma _ { \nu }
$$

其中 $B$ 是外加磁场,地图的每个节点 $\nu$ 是一个晶格，自旋 $\sigma _ { \nu } = \pm 1$ ,每条边 $\boldsymbol { e } = ( u , \nu )$ 上两个节点之间的相互作用量是 $J _ { ( u , \nu ) }$ ， $\mu = 2 \mu _ { \scriptscriptstyle B } \sqrt { s ( s + 1 ) }$ 是磁矩, $s$ 是磁量子数， $\beta = \frac { 1 } { k _ { \scriptscriptstyle B } T }$ ，这里 $k _ { B }$ 是玻尔兹曼常数， $T$ 是晶格系统的温度.

设每条边上两个节点之间的相互作用量都是 $J$ ，伊辛模型的配分函数是：

$$
Q _ { N } ( B , T ) = \sum _ { \nu \in V } \sum _ { \sigma _ { \nu } } \exp [ - H \{ \sigma _ { \nu } \} ] = \sum _ { \sigma _ { u } } \sum _ { \sigma _ { \nu } } \prod _ { ( u , v ) \in E } \exp [ \beta J \sigma _ { u } \sigma _ { \nu } ] \prod _ { \nu \in V } \exp [ \beta \mu B \sigma _ { \nu } ]
$$

其中 $\exp [ x ] = e ^ { x }$

假设外加磁场强度 $B = 0$ ， $K = \frac { J } { k _ { B } T }$ ，则 Hamiltonian量是$H \{ \sigma _ { \nu } \} = - K \sum _ { ( u , \nu ) \in E } \sigma _ { u } \sigma _ { \nu }$ ，

由于 $( \ \sigma _ { u } \sigma _ { \nu } ) ^ { 2 } = 1 \mathrm { ~ , ~ } \ \exp [ K \sigma _ { u } \sigma _ { \nu } ] = e ^ { K \sigma _ { u } \sigma _ { \nu } } = c h K + \sigma _ { u } \sigma _ { \nu } s h K = c h K ( 1 + \sigma _ { u } \sigma _ { \nu } t h K )$ ，配分函数为：

$$
\mathcal { Q } ( | V | , T ) = \sum _ { \nu \in V } \sum _ { \sigma _ { \nu } } \exp [ - H \{ \sigma _ { \nu } \} ] = \sum _ { \sigma _ { u } } \sum _ { \sigma _ { \nu } } \prod _ { ( u , \nu ) \in E } [ c h K ( 1 + \sigma _ { u } \sigma _ { \nu } t h K ) ]
$$

$$
= ( c h K ) ^ { \vert E \vert } \sum _ { \sigma _ { u } } \sum _ { \sigma _ { \nu } } \prod _ { ( u , \nu ) \in E } ( 1 + \sigma _ { u } \sigma _ { \nu } w ) \quad ( \ w = t h K ) .
$$

将配分函数的乘积项展开得：

$$
Q ( | V | , T ) = ( c h K ) ^ { | E | } \sum _ { \sigma _ { 1 } = \pm 1 } \cdots \sum _ { \sigma _ { | v | } = \pm 1 } ( 1 + w \sum _ { ( i , j ) \in E } \sigma _ { i } \sigma _ { j } + w ^ { 2 } \sum _ { ( i , j ) \in E } \sum _ { ( k , l ) \in E } \sigma _ { i } \sigma _ { j } \sigma _ { k } \sigma _ { l } + \cdots ) .
$$

设 $n ( r )$ 是在给定晶格上使用 $\boldsymbol { r }$ 个键所能画出的图形数，且这些图形要求每个节点都是由偶数个键连接，则配分函数的高温展开是：

$$
Q ( | V | , T ) = 2 ^ { | V | } ( c h K ) ^ { | E | } \sum _ { r = 0 } ^ { \infty } n ( r ) w ^ { r } \ , \ ( n ( 0 ) = 1 ) .
$$

在基态下系统所包含的所有自旋都指向同一方向，对应总能量 ${ \cal E } _ { 0 } = - J \vert E \vert$ 反转一个节点 $\nu$ 的自旋，会减少 $d _ { \nu }$ 个同向最近邻对,同时产生了 $d _ { \nu }$ 反向最近邻对，系统的总能量增加了 $2 d _ { \nu } J$ ，这里 $d _ { \nu }$ 是节点 $\nu$ 的度数.设 $\left| V \right| _ { + + }$ 表示两个自旋上-上最近邻对的总数目， $\left| V \right| _ { -- }$ 表示两个自旋下-下最近邻对的总数目， $\left| V \right| _ { + - }$ 表示两个自旋上-下最近邻对的总数目，并且 $\left| V \right| _ { + + } + \left| V \right| _ { -- } + \left| V \right| _ { + - } = \left| E \right|$ ，系统的 Hamiltonia量为

$$
H ( \left| V \right| _ { + - } ) = - J \left( \left| V \right| _ { + + } + \left| V \right| _ { -- } - \left| V \right| _ { + - } \right) = - J \left( \left| E \right| - 2 \left| V \right| _ { + - } \right) ~ .
$$

配分函数的低温展开式是： $Q ( \left| V \right| , T ) = e ^ { K \left| E \right| } \sum _ { r = 0 } ^ { \infty } m ( r ) e ^ { - 2 K r } \ , \ ( m ( 0 ) = 1 ) .$

其中 $m ( r )$ 表示这样的数目：设置晶格中 $| V |$ 个自旋方向，使之有 $\boldsymbol { r }$ 个反向最近邻对， $m ( r )$ 表示的就是满足如此条件之设置的数目， $r = 0 , \ d _ { \nu } \cdot \cdot \cdot$ ：

# 3伊辛模型配分函数的对偶变换

设有连通地图 $M = ( V , E , F )$ ，对偶地图 $\boldsymbol { M } ^ { * } = ( \boldsymbol { V } ^ { * } , \boldsymbol { E } , \boldsymbol { F } ^ { * } )$ ，且$\left| \boldsymbol { V } ^ { * } \right| = \left| \boldsymbol { F } \right| , \left| \boldsymbol { F } ^ { * } \right| = \left| \boldsymbol { V } \right| .$ （20$\left| V \right| - \left| E \right| + \left| F \right| = \chi _ { M } = \left\{ 2 - 2 \xi _ { M } , M \right.$ 可定向M\*上的晶格是M上的对偶晶格，|V|-|E|+|F|=χm=不可定向其中 $\chi _ { \scriptscriptstyle M }$ 是 $M$ 的欧拉示性数， $\xi _ { { \scriptscriptstyle M } }$ 为 $M$ 的亏格数.

从给定的晶格 $M$ 出发，在这个晶格上有一个键数为 $r$ 的闭圈图形， $\boldsymbol { r }$ 个键对应有 $n _ { \scriptscriptstyle M } ( { \boldsymbol { r } } )$ 个闭圈,构建它的对偶晶格 $M ^ { * }$ ，然后在闭圈内部的节点上给定某一方向的自旋，外部节点给定反方向的自旋.这样所得的图形是对偶晶格上具有 $\boldsymbol { r }$ 个反方向最近邻对的闭圈图形， $\boldsymbol { r }$ 个反方向键对应有 $m _ { { _ M ^ { * } } } ( r )$ 个闭圈.相反地，晶格

M上某图形具有 $r$ 个反方向最近邻对，用路径长度为 $r$ 的闭圈图形来表示， $\boldsymbol { r }$ 个  
反方向最近邻对对应有 $m _ { { \scriptscriptstyle M } } ( r )$ 个闭圈图形，构建它的对偶晶格 $\boldsymbol { M } ^ { * }$ ,这个闭圈图  
形就是对偶晶格上的键数为 $r$ 个的闭圈图形， $\boldsymbol { r }$ 个键对应有 $n _ { { } _ { M ^ { * } } } ( r )$ 个闭圈,由地图  
的对偶性得： $n _ { { \scriptscriptstyle M } } ( r ) = m _ { { \scriptscriptstyle M } ^ { * } } ( r ) , m _ { { \scriptscriptstyle M } } ( r ) = n _ { { \scriptscriptstyle M } ^ { * } } ( r ) .$ （20设 $\boldsymbol { K } ^ { * } = \frac { \boldsymbol { J } } { k _ { B } T ^ { * } }$ ，以使得 $t h K ^ { * } = e ^ { - 2 K }$ ，即: $s h ( 2 K ) s h ( 2 K ^ { * } ) = 1$ ：$Q _ { \scriptscriptstyle M } ( \left. V \right. , T ) = e ^ { \kappa \vert E \vert } \sum _ { r = 0 } ^ { \infty } m _ { \scriptscriptstyle M } ( r ) e ^ { - 2 K r } = e ^ { \kappa \vert E \vert } \sum _ { r = 0 } ^ { \infty } n _ { { \scriptscriptstyle M ^ { * } } } ( r ) ( \nu ^ { * } ) ^ { r } , \nu ^ { * } = t h K ^ { * } .$ （204号$Q _ { _ M ^ { * } } ( | F | , T ^ { ^ * } ) = 2 ^ { | F | } ( c h K ^ { ^ * } ) ^ { | E | } { \sum _ { r = 0 } ^ { \infty } } n _ { _ M ^ { * } } ( r ) ( \nu ^ { ^ * } ) ^ { r } \ .$ 所以得到配分函数的对偶变换为： $Q _ { M } ( \left| V \right| , T ) = 2 ^ { - \left| F \right| } ( s h K ^ { ^ { \ast } } c h K ^ { ^ { \ast } } ) ^ { - { \frac { \left| E \right| } { 2 } } } Q _ { _ M ^ { \ast } } ( \left| F \right| , T ^ { ^ { \ast } } ) .$

# 4自对偶伊辛模型的相变临界点

若 $\boldsymbol { M } ^ { * } = \boldsymbol { M }$ ，则 $M$ 是自对偶的地图，其上的晶格模型是自对偶的伊辛模型，这时有：

$\begin{array} { r } { \big \vert \boldsymbol { V } ^ { * } \big \vert = \big \vert \boldsymbol { F } \big \vert = \big \vert \boldsymbol { V } \big \vert , \big \vert \boldsymbol { V } \big \vert - \big \vert \boldsymbol { E } \big \vert + \big \vert \boldsymbol { V } \big \vert = \chi _ { \scriptscriptstyle M } , \big \vert \boldsymbol { E } \big \vert = 2 \big \vert \boldsymbol { V } \big \vert - \chi _ { \scriptscriptstyle M } . } \end{array}$   
在临界状态时， ${ \boldsymbol { T } } = { \boldsymbol { T } } ^ { * }$ $T ^ { * } , \ Q _ { \boldsymbol { M } } ( \lvert \boldsymbol { V } \rvert , \boldsymbol { T } ) = Q _ { \boldsymbol { M } ^ { * } } ( \lvert \boldsymbol { V } \rvert , \boldsymbol { T } ^ { * } ) , 2 ^ { - \lvert \boldsymbol { F } \rvert } ( s h \boldsymbol { K } ^ { * } c h \boldsymbol { K } ^ { * } ) ^ { \frac { \lvert \boldsymbol { E } \rvert } { 2 } } = 1 .$ （20$2 ^ { - | V | } ( s h K ^ { ' } c h K ^ { ' } ) ^ { \frac { | E | } { 2 } } = 1 , ( s h ( 2 K ^ { ' } ) ) ^ { - \frac { | E | } { 2 } } = 2 ^ { \frac { 2 | V | - | E | } { 2 } } , s h ( 2 K ^ { ' } ) = 2 ^ { 1 - 2 ^ { \frac { | V | } { | E | } } } = 2 ^ { - \frac { \chi _ { M } } { | E | } } ,$ 记： $k _ { \scriptscriptstyle M } = - \frac { \chi _ { \scriptscriptstyle M } } { \vert E \vert } = 1 - 2 \frac { \vert V \vert } { \vert E \vert }$ 则相变临界点 $K ^ { ' } = \frac { 1 } { 2 } \mathrm { l n } ( 2 ^ { k _ { M } } + \sqrt { 2 ^ { 2 k _ { M } } + 1 } ) .$ 对于连通地图 $M \ : \ : , \ : \ : \ : | V | - 1 \leq \lvert E \rvert \leq \frac { 1 } { 2 } \lvert V \rvert ( \lvert V \rvert - 1 ) , \frac { 2 } { \lvert V \rvert - 1 } \leq \frac { | V \rvert } { \lvert E \rvert } \leq \frac { \lvert V \rvert } { \lvert V \rvert - 1 } .$   
$- 1 \leq 1 - \frac { 2 \big | V \big | } { \big | V \big | - 1 } \leq 1 - 2 \frac { \big | V \big | } { \big | E \big | } \leq 1 - \frac { 4 } { \big | V \big | - 1 } \leq 1 ,$ ，所有： $\frac 1 2 \ln ( \frac 1 2 + \sqrt { \frac 5 4 } ) \leq K ^ { * } \leq \frac 1 2 \ln ( 2 + \sqrt { 5 } ) .$ （204号  
自对偶地图 $M$ 上伊辛模型的相变临界点 $\boldsymbol { K } ^ { * }$ 满足： $0 . 2 4 0 6 \leq K ^ { * } \leq 0 . 7 2 1 8$ ：

对于三维伊辛模型，节点数 $\left. V \right. = m n l$ ，度数 $d _ { \nu } = 6$ ，边数 $\left. E \right. = 3 m n l$ ，设 $M$ 在曲面上的嵌入是自对偶的地图，面数 $\vert F \vert = m n l , \chi _ { \scriptscriptstyle M } = - m n l , M$ 是六正则地图. $M$ 可定向时，亏格数 $\xi _ { \scriptscriptstyle M } = \frac 1 2 ( 2 + n m l ) = 1 + \frac { n m l } 2$ 其中nml为偶数. $M$ 不可定向时， $\xi _ { { \scriptscriptstyle M } } = 2 + n m l$ ：

$$
k _ { \scriptscriptstyle M } = = 1 - 2 \frac { \left| V \right| } { \left| E \right| } = \frac { 1 } { 3 } , \quad K ^ { \ast } = \frac { 1 } { 2 } \ln ( \sqrt [ 3 ] { 2 } + \sqrt [ 3 ] { \sqrt [ 4 ] { 4 } + 1 } ) = 0 . 5 2 6 9 .
$$

根据现有文献[5-8]，由MonteCarlo模拟和重整化群等近似方法得到相变临界点的近似值是：

$$
\boldsymbol { K } ^ { * } = \frac { \boldsymbol { J } } { k _ { B } \boldsymbol { T } _ { c } ^ { * } } = 0 . 2 1 7 4 , 0 . 2 2 2 0 0 , 0 . 2 2 1 6 5 4 4 , 0 . 2 2 1 7 , 0 . 3 0 7 4
$$

三维自对偶伊辛模型有较高的对称性和稳定性，其相变临界点 $\boldsymbol { K } ^ { * } = \boldsymbol { 0 } . 5 2 6 9$ 比模拟得到的临界点都要大，文献[5]中由二个猜想得的的Curie 温度相变临界点，精确地存在于黄金点 $\exp ( - 2 K _ { c } ^ { * } ) = \frac { \sqrt { 5 } - 1 } { 2 } = 0 . 6 1 8 0 0 3 3 9 8 8 7 ,$ 所得到的$\boldsymbol { K } _ { c } ^ { * } = 0 . 2 4 0 6 0 5 9$ 与文中的临界点下界精确值 $\frac { 1 } { 2 } \ln ( \frac { 1 } { 2 } + \sqrt { \frac { 5 } { 4 } } ) = 0 . 2 4 0 6 0 5 9$ 近似相等,两个临界点的误差很小.

# 5结论

根据地图上伊辛模型的对偶变换和地图是自对偶的充要条件,本文得到了自对偶地图的上伊辛模型相变临界点 $\boldsymbol { K } ^ { * }$ 的上下界： $0 . 2 4 0 6 \leq K ^ { * } \leq 0 . 7 2 1 8$ ，并且给出三维自对偶伊辛模型的相变临界点： $\boldsymbol { K } ^ { * } = \boldsymbol { 0 } . 5 2 6 9$ ：

# 参考文献

[1]刘彦佩.地图的代数原理[M].北京：高等教育出版社,2006:1-108.  
[2]R.K.Pathria,Paul D.Beale.统计力学(第三版)[M],方锦清，戴越 译．北京:高等教育出版社，2017:445-500.  
[3]易中.统计力学基础[M].北京：冶金工业出版社，2008:153-297.  
[4]沈惠川.统计力学[M].合肥：中国科学技术大学出版社,2011:268-356.  
[5]张志东.三维Ising 模型的数学结构与精确解探索[J].金属学报,2016,52(10):1311-1325.[6]黄纯青,邓绍军.三维Ising 模型的蒙特卡罗模拟[J].计算物理,2009,26(6):937-941.[7]陈小余.三维Ising 模型矩阵解法的简化与近似解[J].物理学报,1995,44(9):1484-1488.[8]邵元智,蓝图,林光明.三维动态Ising 模型中的非平衡相变:三临界点的存在[J].物理学报，2001,50(5):942-947.  
[9]张孝伍.纽结的新伙伴:平图[J].淮南工业学院学报,2002,22(4),70-73．  
[10]张孝伍.有向纽结的可逆性[J]．青岛理工大学学报,2018,39(1):107-110.