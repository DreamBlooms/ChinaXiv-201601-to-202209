# 基于直线型反 $\lambda$ 基本图的交通流分配模型及算法

何胜学

(上海理工大学 管理学院，上海 200093)

摘要：针对现有交通流分配理论难以处理路段拥挤状态的问题，以直线型反 $\lambda$ 交通流量、密度和速度基本关系图为基础，提出了给定路段交通状态下的静态交通流分配新方法。首先通过分析基本关系图，得到两阶段的路段行程时间函数；其次，通过引入路段交通状态指标量，构建节点流量守恒方程，建立了系统最优和用户均衡交通流分配模型；最后，针对非凸的用户均衡模型，通过线性化目标函数中的非凸项，设计了一种有效的分支定界求解算法。数值算例验证了新模型和算法的有效性；新理论扩展了现有路段行程时间函数过于片面的单调递增特征假设，可有效处理路段拥挤状态，提高现有理论的实用性。

关键词：交通规划；交通流分配；拥堵；非凸规划中图分类号：U491 doi:10.3969/j.issn.1001-3695.2017.09.0923

# Traffic assignment model and algorithm based on straight line inverse $\lambda$ fundamental diagram

He Shengxue (Business School, University ofShanghai for Science &Technology,Shanghai 2Ooo93,China)

Abstract:Theexisting traffcasignment theorem hardlydealt with thecongested traffc stateoflink.Tosolve the above problem,based on the classic straight line inverse $\lambda$ fundamental diagram, a static traffic assignment method with given states oflinks was presented.Firstly,throughanalyzingthefundamentaldiagram,thetraveltimefunctionoflink withtwostages was obtained.Secondly,byintroducingtheindicatinglabelof traficstateoflinkandconstructing thflowconservationequations at nodes,thesystem optimalanduser equilibriumtraffic asignment models were formulated.Atlast,tosolvethe non-convex user equilibrium model,abranchandboundalgorithmwithrelaxedpartialobjectivefunctionwas proposed.Numericalxamples were used todemonstrate theefectivenessof te new modelandalgorithm.Byextending theone-sidedasumptionofmonotone increasingoflinktravel timefunction,thenew theorycandealwiththecongested traffc stateoflink effectivelyand mprove the practicality of existing theories.

Key Words: transportation planning; trafic assignment; congestion; non-convex programming

# 0 引言

现有静态交通流分配理论假设路段行程时间函数为流量的单调增函数，因此无法有效处理路段的拥挤交通状态。根据基本的交通流量、密度和速度基本关系图，当路段处于拥挤状态时，路段的行程时间将随着路段流量的增大而减少。因此，拥挤状态的路段行程时间函数应该为路段流量的单调减函数。为了解决上述问题，本文以经典的直线型反流量、密度和速度基本关系图为基础，给出对应的两阶段路段行程时间函数。利用两阶段行程时间构建新的交通流分配模型，并设计有效求解算法。

静态交通流分配理论始于1952年Wardrop提出有名的出行路径选择两原则，即Wardrop 第一原则(用户均衡)和Wardrop第二原则(系统最优)[1]。1956 年 Beckman 给出了对应Wardrop第一原则的用户均衡交通流分配数学模型，即有名的Beckman变换[2]。1975年，Leblanc 首次给出了求解上述模型的实用有效Frank-Wolfe 算法[2]。Dafermos 和Sparrow 探讨了如何利用变分不等式构建交通流分配模型[3]；Daganzo 和 Sheffi 最早提出了随机交通流分配的理念[4]。2002年Bar-Gera 提出的基于起点的交通流分配算法大大提高了求解静态模型的效率[5]。近年来研究者更多地关注于动态交通流分配和一些拟动态交通流分配的理论研究，例如应用投影动态理论对交通流分配问题进行建模分析[67]。为了克服经典理论中路段流量可超出路段通行能力的缺陷，研究者提出了一系列基于变分不等式理论的带有边约束的交通流分配模型[8,9]。静态交通流分配理论中一般假设路段行程时间函数具有对于路段流量的单调递增特征，而该假设与实际路段处于拥挤状态下的相矛盾。最近的基于静态交通流分配理论的研究也没有改变上述假设，例如文献[10]假设路段行程时间函数为一般的连续可微单调增凸函数，文献[11]则利用了经典BPR单调增函数，而文献[12]则简单利用了线性单调增函数。流量、密度和速度的基本关系图是交通流理论的基础理论之一，广泛应用于交通研究的各个领域，例如经典的CTM 模型即基于该理论建立[13\~15]。

本研究的主要创新包括：a)基于直线型反 $\lambda$ 基本图构建了考虑两阶段路段行程时间的交通流分配模型；b)针对非凸的用户均衡模型设计了一种有效的线性松弛分支定界求解算法。

# 1 路段行程时间函数

与常见的三角形流-密-速基本关系相比，图1给出的反 $\lambda$ 型流-密-速基本关系体现了交通状态从自由流状态转为拥挤状态时的通行能力失效特征，即图中交通状态从C到B的突变。随着交通流密度 $d$ 的增大，路段上的交通状态首先维持自由流状态，然后当达到自由流临界密度 $d _ { c r }$ 后，会出现流量的突降，即由 $q _ { c r }$ 变为 $q _ { \operatorname* { m a x } }$ ，随后转入拥挤状态。显然，自由流状态下的车速保持为 $\nu _ { f r e e }$ 不变。而任意拥挤状态D下的车速，为原点与D 点连线的斜率VD。

![](images/4b4d7418ef322221c6273e443ff4f0cf018ee1f740f811c7d7238a8a58c84f23.jpg)  
图1直线型反 $\lambda$ 流-密-速基本关系图

![](images/2f5631f61a76bc70f0c6856e77fc69e6d7ffe90d7521c78ad3872f1e35dd2fce.jpg)  
图2对应反 $\lambda$ 型流密速关系的两阶段路段行程时间

图2给出了对应反“λ”型流-密-速基本关系的路段行程时间函数。假设路段的长度为 $\mathcal { L }$ ，则显然存在如下关系：$t _ { \mathit { f r e e } } = \mathcal { L } / \nu _ { \mathit { f r e e } }$ ，因此自由流状态下路段行程时间为常数 $t _ { f r e e }$ 。假设拥挤状态下路段行程时间函数为 $t = \alpha + \beta q ^ { - 1 }$ ，其中 $\alpha$ 和$\beta > 0$ 是待定常数。简单的推算可知，上述拥挤状态下路段行程时间函数与直线型的路段拥挤阶段流量和密度的关系相对应，且有 $\beta = \mathcal { L } d _ { j a m }$ 和 $\alpha = \mathcal { L } ( d _ { \operatorname* { m a x } } - d _ { j a m } ) \big / q _ { \operatorname* { m a x } }$ 成立。由图2可知，关系式 $q _ { \mathrm { m a x } } / d _ { \mathrm { m a x } } = \nu _ { f r e e }$ 成立。

# 2 交通流分配模型

与给定路段交通流状态的交通流分配模型相关的参变量简介如下：

$a \in A$ = 指代有向路段 $a , _ { A }$ 为所有的有向路段集合;  
$n \in N$ 1 指代节点 $n \mathrm { ~ , ~ } N$ 为所有节点集合;

$\boldsymbol { A } _ { n } ^ { + }$ ——所有进入节点 $n$ 的路段集合,即如果 $a \in A _ { n } ^ { + }$ ,则节点$n$ 为有向路段 $\mathbf { \Phi } _ { a }$ 的首节点;

$\boldsymbol { A } _ { n _ { n } } ^ { - }$ ——所有离开节点 $n$ 的路段集合,即如果 $a \in A _ { n } ^ { - }$ ,则节点$n$ 为有向路段 $\mathbf { \Phi } _ { a }$ 的尾节点;

$b \in B$ —一指代OD 对 $b , B$ 为所有OD 对的集合;

（20 $n _ { b } ^ { + } \in N _ { B } ^ { + }$ OD 对 $b$ 的起点， $N _ { B } ^ { + } \equiv \{ n _ { b } ^ { + } \in N \left| b \in B \right. \}$ 为所有OD 对起点的集合;

（20 $n _ { b } ^ { - } \in N _ { B } ^ { - }$ —OD 对 $b$ 的终点, $N _ { B } ^ { - } \equiv \{ n _ { b } ^ { - } \in N \left| b \in B \right. \}$ 为所有OD 对终点的集合;

$q _ { b }$ 1 OD对 $b$ 的交通需求流量;  
$x _ { a }$ 1 路段 $\mathbf { \Phi } _ { a }$ 上的流量;  
$x _ { a } ^ { b }$ OD对 $b$ 的交通需求流量经由路段 $a$ 的流量;  
$t _ { a } ^ { 1 }$ 一 自由流状态下路段 $a$ 的行程时间,为给定常数;

$t _ { a } ^ { 0 } ( x _ { a } )$ —一当路段 $a$ 的交通状态为拥挤状态且其上的流量为 $x _ { a }$ 时,路段 $\mathbf { \Psi } _ { a }$ 的行程时间;

$\mathcal { S } _ { a } \in \{ 0 , 1 \}$ 路段 $\mathbf { \Psi } _ { a }$ 的交通状态指示量;当 $\delta _ { a } = 1$ 时,路段$a$ 的交通状态为自由流状态;

否则，路段 $\mathbf { \Omega } _ { a }$ 的交通状态为拥挤状态；  
qmax 拥挤状态下路段 $a$ 的最大通行流量;  
$\boldsymbol { q } _ { a } ^ { c r }$ ——自由流状态下路段 $\mathbf { \Psi } _ { a }$ 的最大通行流量;  
$\Delta > 0$ 1 为给定的一个拥挤状态下的最小通行流量。

相关的约束包括：

$$
\textstyle \sum _ { a \in A _ { n } ^ { + } } x _ { a } ^ { b } - \sum _ { a \in A _ { n } ^ { - } } x _ { a } ^ { b } = 0 , \forall n \in N / \{ n _ { b } ^ { + } , \boldsymbol { \mathrm { n } } _ { b } ^ { - } \} , b \in B
$$

$$
{ \sum } _ { a \in A _ { n } ^ { + } } x _ { a } ^ { b } - { \sum } _ { a \in A _ { n } ^ { - } } x _ { a } ^ { b } + q _ { b } = 0 , \forall n = n _ { b } ^ { + } , b \in B
$$

$$
{ \sum } _ { a \in A _ { n } ^ { + } } x _ { a } ^ { b } - { \sum } _ { a \in A _ { n } ^ { - } } x _ { a } ^ { b } - q _ { b } = 0 , \forall n = n _ { b } ^ { - } , b \in B
$$

$$
\sum _ { b \in B } x _ { a } ^ { b } = x _ { a } , \forall a \in A
$$

$$
x _ { a } \leq \delta _ { a } q _ { a } ^ { c r } + ( 1 - \delta _ { a } ) q _ { a } ^ { \operatorname * { m a x } } ,
$$

$$
x _ { a } \geq ( 1 - \delta _ { a } ) \Delta \ , \forall a \in A
$$

$$
\delta _ { a } \in \{ 0 , 1 \} , \forall a \in A
$$

其中：约束式(1)\~(3)分别为一般节点、OD对起点和OD对终点的交通流守恒方程。约束式(4)表示总的路段流量等于各分OD对的路段流量之和。约束式(5)和(6)是路段流量和的上下界限约

束。约束式(7)限定路段交通状态指示参数为0-1变量。

与出行者的择路行为对应，可以给出两个不同的目标函数。式(8)对应系统最优(Systemoptimization)，式(9)则对应用户均衡(User equilibrium)。

$$
\displaystyle \operatorname* { m i n } Z ^ { \mathrm { s o } } = \sum _ { \boldsymbol { a } \in A } x _ { \boldsymbol { a } } ( \delta _ { \boldsymbol { a } } t _ { \boldsymbol { a } } ^ { 1 } + ( 1 - \delta _ { \boldsymbol { a } } ) t _ { \boldsymbol { a } } ^ { 0 } ( x _ { \boldsymbol { a } } ) )
$$

$$
\mathrm { m i n } Z ^ { \mathrm { U E } } = \sum _ { a \in A } \int _ { ( 1 - \delta _ { a } ) \Delta } ^ { x _ { a } } ( \delta _ { a } t _ { a } ^ { 1 } + ( 1 - \delta _ { a } ) t _ { a } ^ { 0 } ( w ) ) \mathrm { d } w
$$

为了方便表述，将以式(8)为目标函数的交通分配模型称为两阶段系统最优模型，而将以式(9)为目标函数的交通分配模型称为两阶段用户均衡模型。

定理1如果任意路段 $\mathbf { \Phi } _ { a }$ 在自由流阶段的行程时间函数为常数 $t _ { a } ^ { 1 } = t _ { f r e e } ^ { a }$ ，而在拥挤状态的行程时间函数形式为$t _ { a } ^ { 0 } = \alpha _ { a } + \beta _ { a } { x _ { a } } ^ { - 1 }$ ，且路段交通状态 $\delta _ { a }$ ， $\forall a \in A$ 给定，那么系统最优的交通流分配模型为线性规划。

证明当路段交通状态 $\delta _ { a }$ ， $\forall a \in A$ 给定时，约束集为线性单纯形。对应自由流状态的目标函数部分为变量的线性函数，而对应拥挤状态的目标函数部分也为变量的线性函数。综上结论可证。

定理2如果任意路段 $a$ 在自由流阶段的行程时间函数为常数 $t _ { a } ^ { 1 } = t _ { f r e e } ^ { a }$ ，在拥挤状态的行程时间函数形式为$t _ { a } ^ { 0 } = \alpha _ { a } + \beta _ { a } { x _ { a } } ^ { - 1 }$ 且 $ { { \beta } } _ { a } > 0$ ，所有 $\delta _ { a }$ ， $\forall a \in A$ 给定，且至少有交通状态 $\delta _ { c } = 0$ ， $\exists c \in A$ ，那么用户均衡的交通流分配模型为非凸规划。

证明 对应 $\delta _ { c } = 0$ 的目标函数加和项为$\int _ { \Delta } ^ { x _ { c } } t _ { c } ^ { 0 } ( w ) ) \mathrm { d } w = \int _ { \Delta } ^ { x _ { c } } ( \alpha _ { c } + \beta _ { c } w ^ { - 1 } ) \mathrm { d } w$ ，而该项为变量 $x _ { c }$ 的凹函数。易知结论成立。

由定理1可知系统最优模型为线性规划模型，因此可以有效求解。由定理2可知用户均衡模型为非凸规划，下一节将给出一个对应的线性松弛分支定界算法。

# 3线性化松弛分支定界算法

交通状态处于拥挤状态的路段集合为Ac={a∈Alδ=0}。集合 $A _ { C }$ 包含的元素个数为 $n _ { c }$ 。由式(9)可知，用户均衡的目标函数中包含的非凸函数部分为 $\textstyle \sum _ { a \in A _ { C } } \beta _ { a } \ln x _ { a }$ 。拥挤状态下变量$x _ { a }$ 的取值范围为 $[ \Delta , q _ { a } ^ { \operatorname* { m a x } } ]$ 。为了简化后续的公式表述，对集合$A _ { c }$ 中的元素加以标序，对应路段的流量按序排列，构成向量$\widehat { \boldsymbol { x } } = ( x _ { 1 } , x _ { 2 } , \cdots , x _ { n _ { c } } ) ^ { \mathrm { T } }$ 。上标“T”表示转置运算。$Z ^ { \mathrm { U E C } } = Z ^ { \mathrm { U E } } - \sum _ { a \in A _ { C } } \beta _ { a } \ln x _ { a }$ 为用户均衡的目标函数中除去非凸函数后的线性函数部分。令集合S={𝑥∈R"c|≤x≤u}，（20 $l = ( l _ { 1 } , \cdots , l _ { n _ { c } } ) ^ { \mathrm { \scriptscriptstyle T } } = ( \Delta , \cdots , \Delta ) ^ { \mathrm { \scriptscriptstyle T } } ~ , ~ u = ( u _ { 1 } , \cdots , u _ { n _ { c } } ) ^ { \mathrm { \scriptscriptstyle T } } = ( q _ { 1 } ^ { \mathrm { \scriptscriptstyle m a x } } , \cdots , q _ { n _ { c } } ^ { \mathrm { \scriptscriptstyle m a x } } ) ^ { \mathrm { \scriptscriptstyle T } } ~ \circ$ （20假设 $S ^ { k }$ 是 $s$ 的任意子长方体且 $S ^ { k } = \{ \hat { x } \in R ^ { n _ { c } } \left| l ^ { k } \leq \hat { x } \leq u ^ { k } \right. \}$ ，其中 $\boldsymbol { l } ^ { k } = ( l _ { 1 } ^ { k } , \cdots l _ { n _ { c } } ^ { k } ) ^ { \mathrm { T } }$ ， $\boldsymbol { u } ^ { k } = ( u _ { 1 } ^ { k } , \cdots u _ { n _ { c } } ^ { k } ) ^ { \top }$ 。易知凹函数 $\beta _ { j } \ln x _ { j }$ 在（20 $[ l _ { j } ^ { k } , u _ { j } ^ { k } ]$ 上的凸包络为线性函数$\overline { { y } } _ { j } = \frac { \beta _ { j } ( \ln u _ { j } ^ { k } - \ln l _ { j } ^ { k } ) } { u _ { j } ^ { k } - l _ { j } ^ { k } } ( x _ { j } - l _ { j } ^ { k } ) + \beta _ { j } \ln l _ { j } ^ { k }$ ，且满足 $\beta _ { j } \ln x _ { j } \geq \overline { { y } } _ { j }$ ，$\forall x _ { j } \in [ l _ { j } ^ { k } , u _ { j } ^ { k } ] , j = 1 , \cdots , n _ { c }$ 。将用户均衡目标函数中的非凸函数部分 $\sum _ { a \in A _ { c } } \beta _ { a } \ln x _ { a } = \sum _ { j = 1 } ^ { n _ { c } } \beta _ { j } \ln x _ { j }$ 替代为 $\sum _ { j = 1 } ^ { n _ { C } } \overline { { y } } _ { j }$ ，则原用户均衡的非凸规划问题(NCP)转化为一个线性规划问题(RLP)，且该线性规划问题提供了原问题的最优值下界。显然对于自由流状态的路段，其对应的目标函数部分保持不变，因此上面的线性松弛为部分变量的松弛。

下面给出的分支定界法通过求解一系列松弛线性规划RLP，逐步改进NCP最优值的上界和下界，最终确定NCP的全局最优解。假定在算法的第 $k$ 次迭代中， $L _ { k }$ 表示由可能存在全局最优解的子长方体构成的集合。对任意 $\hat { S } \in L _ { k }$ ， $\mathrm { R L P } ( \hat { \boldsymbol { S } } ^ { } )$ 的最优值记为 $\mu ( \hat { S } )$ ，令 $\mu _ { k } = \operatorname* { m i n } \{ \mu ( { \hat { S } } ) { \big | } { \hat { S } } \in L _ { k } \}$ ，则 $\mu _ { k }$ 是问题(NCP）最优值的一个下界。若 $\mathrm { R L P } ( \hat { \boldsymbol { S } } )$ 的最优解是问题(NCP)的可行解，则更新 NCP 最优值的上界 $\nu _ { \scriptscriptstyle k }$ ，选定一子长方体 $S ^ { k }$ 使得$\mu ( S ^ { k } ) = \mu _ { k }$ ，然后沿垂直 $S ^ { k }$ 的最长边方向将 $S ^ { k }$ 平分为两部分，对每一部分求其相应的解，重复这一过程直到满足收敛条件。需要指出的是下面出现的 $x _ { k }$ 指代由分OD对的路段流量构成的向量，显然 $x _ { k }$ 暗含了 $\hat { x }$ 。

具体算法如下：

a)初始化。给定收敛参数ε>0，令k=1,L={S}，S=S，$\nu _ { _ { k } } = \infty$ 。求解 $\mathrm { R L P } ( \mathbf { \Phi } _ { S ^ { k } } \mathbf { \Phi } )$ ，得其最优解和最优值分别为 $x _ { k }$ 和$\mu ( \boldsymbol { S } ^ { k } )$ ，令 $\mu _ { k } = \mu ( \boldsymbol { S } ^ { k } )$ ；若 $x _ { k }$ 对(NCP）可行，则令 $\nu _ { \scriptscriptstyle k } = Z ^ { \mathrm { U E } } ( x _ { \scriptscriptstyle k } )$ 。若 $\nu _ { \scriptscriptstyle k } - \mu _ { \scriptscriptstyle k } \leq \varepsilon$ ，则算法停止，且(NCP）的最优解和最优值分别为 $x _ { k }$ 和 $\nu _ { \scriptscriptstyle k }$ ；否则执行步b)。

b)分支步。沿垂直于 $S ^ { k }$ 最长边方向将 $S ^ { k }$ 平分为两部分 $S ^ { k _ { r } }$ 0 $\cdot r = 1 , 2$ 。令 $L _ { k } = L _ { k } - \{ S ^ { k } \}$ 。

${ \mathsf { c } } )$ 定界步。对任意 $r \in \{ 1 , 2 \}$ ，求 $\mathrm { R L P } (  _ { S ^ { k _ { r } } }$ ）得最优解和值分别为 $x _ { k _ { r } }$ 和 $\mu ( S ^ { k _ { r } } )$ ；若 $\mu ( S ^ { k _ { r } } ) > \nu _ { k }$ ，删除 $S ^ { k _ { r } }$ ，否则 $L _ { k } = L _ { k } \cup \{ S ^ { k _ { r } } \}$ 若 xk对(NCP）可行，Vk =min{νk,ZUE(x,）}。

选 $x _ { k }$ 使 $\nu _ { \boldsymbol { k } } = Z ^ { \mathrm { U E } } ( x _ { \boldsymbol { k } } )$ 。

${ \mathsf { d } } )$ 判断步。令 $L _ { k + 1 } = L _ { k } - \{ \hat { S } \in L _ { k } \mid \nu _ { k } - \mu ( \hat { S } ) \leq \varepsilon \}$ 。若 $L _ {  { \boldsymbol { k } } + 1 } = \emptyset$ ，算法停止，且(NCP）的最优解和值分别为 $x _ { k }$ 和 $\nu _ { \scriptscriptstyle k }$ ；否则（20 $k : = k + 1$ ; $\mu _ { k } = \operatorname* { m i n } \{ \mu ( \hat { S } ) | \hat { S } \in L _ { k } \}$ 。选取 $S ^ { k }$ ,使得 $\mu ( S ^ { k } ) = \mu _ { k }$ ，返回步b)。

定理3假定用户均衡非凸规划问题(NCP)的全局最优解存在，则算法或者经有限步迭代求得问题的全局最优解，或者算法产生的迭代序列 $\{ x _ { k } \}$ 的极限点必为问题的全局最优解。

证明若算法经有限步迭代终止，则结论是显然的。由函数 $\ln x$ 的图形可知， $\beta _ { j } \ln x _ { j } - \overline { { y } } _ { j } \leq \beta _ { j } ( \ln u _ { j } ^ { k } - \ln l _ { j } ^ { k } ) \leq \beta _ { j } ( u _ { j } ^ { k } - l _ { j } ^ { k } )$ 。由凹函数的凸包特征可知，原问题目标函数与松弛后的线性规划目标函数间存在关系 $Z ^ { \mathrm { U E } } ( S ^ { k } ) \ge ( Z ^ { \mathrm { U E } C } ( S ^ { k } ) + \sum _ { j = 1 } ^ { n _ { C } } \overline { { y } } _ { j } )$ 。且两者满足 $\begin{array} { r l } & { \displaystyle Z ^ { \mathrm { U E } } ( S ^ { k } ) - ( Z ^ { \mathrm { U E } C } ( S ^ { k } ) + \sum _ { j = 1 } ^ { n _ { c } } \overline { { y } } _ { j } ) = } \\ & { \displaystyle \sum _ { j = 1 } ^ { n _ { c } } ( \beta _ { j } \ln x _ { j } - \overline { { y } } _ { j } ) \le n _ { c } \operatorname* { m a x } _ { j } \beta _ { j } ( u _ { j } ^ { k } - l _ { j } ^ { k } ) } \end{array}$ 。当算法产生一个无限迭代序列时，由算法中矩形二分法的穷举特征可知$\operatorname* { l i m } _ { k \to \infty } ( u _ { j } ^ { k } - l _ { j } ^ { k } ) = 0$ 。综上可得

尽管定理3证明算法可求得模型的全局最优解，但是注意到部分线性松弛后得到的线性模型可能出现解不唯一的情况，因此最终的全局最优解可能不唯一。例如网络只有两条连接唯一OD对的路径，且两条路径间没有共用路段。假设自由流状态下两路径的行程时间相同，唯一OD对间的交通需求量较小。因此该需求量可以被任意分配到两条路径，而两路径可保持自由流状态，既行程时间不变。这种情况下，我们得到不同的路径流量(对应不同的路段流量)，而对应的目标函数值不变。上例对应的流量分配模型为线性模型，可解释全局最优解可能不唯一的情况。

# 4 算例分析

由于系统最优模型属于线性规划，目前存在许多有效求解方法，因此本节仅考虑非凸的用户均衡模型。本节中均以小时(hr)作为时间单位，公里 $( \mathrm { k m } )$ 作为距离单位。流量的单位均为pcu/hr,速度的单位均为 $\mathrm { k m / h r }$ 。这里pcu表示标准小汽车单位。上节的算法利用Lingo语言实现，其中的松弛线性规划子模型(RLP)的求解直接利用Lingo软件的自带程序实现。因此计算的效率与软件本身的算法密切相关，对于随后给出的算例，得到最终结果需要的时间大约为9s；而利用Lingo软件直接求解非凸模型得到最终结果需要的时间大约为4秒。

![](images/6588341a265790aa29a0828035c51eb080e7f0da35558771ece3ac98818e858f.jpg)  
图3给出了一个有10个节点的交通网络。  
图3有10个节点交通网络

图3中水平方向路段长度均为 $2 \mathrm { k m }$ ，竖直方向的上层路段长度均为 $1 \mathrm { k m }$ ，竖直方向下层路段的长度均为 $2 \mathrm { k m }$ ，斜向路段长度已经标示在图中相应路段旁。假设所有的节点均既可作为OD 对的起点，也可作为OD对的终点。因此有效的OD对有

90对，相应的OD交通需求量在表1中给出。从表1可知总的出行需求为16860pcu/hr。假设所有路段的自由流速度均为$8 0 \mathrm { k m / h r }$ 。

表1交通OD需求信息 $\mathrm { ( p c u / h r ) }$ （204  

<html><body><table><tr><td rowspan="2">OD 起点</td><td colspan="10">OD终点</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>1</td><td>0</td><td>20</td><td>50</td><td>430</td><td>190</td><td>400</td><td>250</td><td>230</td><td>80</td><td>50</td></tr><tr><td>2</td><td>20</td><td>0</td><td>20</td><td>50</td><td>400</td><td>200</td><td>250</td><td>120</td><td>150</td><td>130</td></tr><tr><td>3</td><td>50</td><td>20</td><td>0</td><td>160</td><td>360</td><td>150</td><td>220</td><td>140</td><td>200</td><td>90</td></tr><tr><td>4</td><td>430</td><td>50</td><td>160</td><td>0</td><td>430</td><td>100</td><td>360</td><td>130</td><td>30</td><td>50</td></tr><tr><td>5</td><td>190</td><td>400</td><td>360</td><td>430</td><td>0</td><td>200</td><td>400</td><td>340</td><td>330</td><td>360</td></tr><tr><td>6</td><td>400</td><td>200</td><td>150</td><td>100</td><td>200</td><td>0</td><td>140</td><td>220</td><td>120</td><td>70</td></tr><tr><td>7</td><td>250</td><td>250</td><td>220</td><td>360</td><td>400</td><td>140</td><td>0</td><td>320</td><td>230</td><td>60</td></tr><tr><td>8</td><td>230</td><td>120</td><td>140</td><td>130</td><td>340</td><td>220</td><td>320</td><td>0</td><td>40</td><td>80</td></tr><tr><td>9</td><td>80</td><td>150</td><td>200</td><td>30</td><td>330</td><td>120</td><td>230</td><td>40</td><td>0</td><td>80</td></tr><tr><td>10</td><td>50</td><td>130</td><td>90</td><td>50</td><td>360</td><td>70</td><td>60</td><td>80</td><td>80</td><td>0</td></tr></table></body></html>

表2给出了对应图3中交通网络的路段相关参数值和计算得到的路段流量。其中， $x _ { a } \left( 1 \right)$ 列给出了利用本文给出的分支定界算法计算得到的路段流量值； $x _ { a } \left( 2 \right)$ 列给出了利用Lingo 软件直接求解非凸模型得到的路段流量值。 $x _ { a } \left( 0 \right)$ 列给出了当不考虑路段拥挤状态(即假设各路段均为自由流状态)条件下利用现有考虑边约束的交通流分配模型计算得到的路段流量值。 $x _ { a } \left( 0 \right)$ 列的数值与本文模型在假设各路段均为自由流状态条件下的计算结果相同。上述结果表明，与现有考虑边约束的分配模型相比，本文模型具有更广泛的适应性，既可以描述路段的自由流状态，也可描述拥挤状态下“随流量增大，路段行程时间降低”的特征。

表3给出了求解算例的 $x _ { a } \left( 1 \right)$ 列路段流量过程中目标函数上下界随迭代次数增加的变化情况。算法在迭代10次（21次求解RLP子模型）后得到全局最优解，此时的目标函数为16464.88。而利用Lingo软件直接求解非凸模型得到的目标函数也为16585.31。但是注意两者计算所得的路段流量值并不相同，见表2中的 $x _ { a } \left( 1 \right)$ 列和 $x _ { a } \left( 2 \right)$ 列数值。表4给出了21次求解RLP子模型的目标函数值(OLP)和对应的原用户均衡模型目标函数值(OUE)。上述计算结果表明本文给出的算法优于Lingo 软件内嵌的非凸模型求解算法。

# 5 结束语

通过分析直线型反lamda基本图，建立了路段行程时间分两阶段的静态交通流分配模型。针对非凸的用户均衡模型，设计了部分线性化松弛的分支定界求解算法。数值分析验证了模型与算法的有效性。研究可进一步深化的方向包括：a)考虑更加复杂的交通流、密度和速度基本图，如曲线型反lamda基本图；b)分时段更新路段状态的拟动态交通流分配研究；c)多方式联合的分配模型扩展。

表2路段相关参数和流量  

<html><body><table><tr><td>a</td><td>a</td><td>β</td><td>qmax</td><td>qcr</td><td>Sa</td><td>xa (1)</td><td>𝑥 (2)</td><td> xa (0)</td></tr><tr><td>(1,2)</td><td>-0.12651</td><td>273.228</td><td>1803.32</td><td>1913.221</td><td>1</td><td>1913.221</td><td>1913.221</td><td>720</td></tr><tr><td>(1,4)</td><td>-0.05112</td><td>127.8856</td><td>2010.131</td><td>2154.679</td><td>0</td><td>1140.923</td><td>60</td><td>1140</td></tr><tr><td>(2,1)</td><td>-0.12083</td><td>247.6413</td><td>1698.196</td><td>1801.691</td><td>1</td><td>1228.429</td><td>319.4563</td><td>1070</td></tr><tr><td>(2,3)</td><td>-0.10767</td><td>230.1844</td><td>1735.07</td><td>1859.839</td><td>1</td><td>1859.839</td><td>1637.344</td><td>1220</td></tr><tr><td>(2.5)</td><td>-0.05771</td><td>141.3638</td><td>2013.544</td><td>2159.52</td><td>0</td><td>793.3825</td><td>1924.85</td><td>1680</td></tr><tr><td>(3,2)</td><td>-0.10352</td><td>228.8147</td><td>1780.4</td><td>1908.429</td><td>1</td><td>1908.429</td><td>1908.429</td><td>1908.429</td></tr><tr><td>(3.6)</td><td>-0.05943</td><td>119.842</td><td>1666.077</td><td>1755.15</td><td>1</td><td>1755.15</td><td>1755.15</td><td>490</td></tr><tr><td>(3,7)</td><td>-0.16299</td><td>361.0587</td><td>1858.79</td><td>1996.239</td><td>1</td><td>1544.942</td><td>1469.736</td><td>940</td></tr><tr><td>(4,1)</td><td>-0.06638</td><td>136.614</td><td>1731.882</td><td>1856.421</td><td>1</td><td>1825.716</td><td>1653.765</td><td>790</td></tr><tr><td>(4,5)</td><td>-0.11383</td><td>284.0972</td><td>2046.412</td><td>2155.818</td><td>0</td><td>1066.779</td><td>1008.216</td><td>1290</td></tr><tr><td>(4,8)</td><td>-0.15125</td><td>405.0306</td><td>2145.904</td><td>2305.844</td><td>0</td><td>60</td><td>60</td><td>570</td></tr><tr><td>(5,2)</td><td>-0.05112</td><td>115.0922</td><td>1809.042</td><td>1940.192</td><td>0</td><td>60</td><td>60</td><td>1341.571</td></tr><tr><td>(5,4)</td><td>-0.12059</td><td>282.7275</td><td>1941.923</td><td>2045.743</td><td>1</td><td>1751.571</td><td>1176.574</td><td>940</td></tr><tr><td>(5,6)</td><td>-0.1304</td><td>265.2706</td><td>1707.072</td><td>1799.338</td><td>0</td><td>1107.018</td><td>1707.072</td><td>1660</td></tr><tr><td>(5.8)</td><td>-0.10476</td><td>223.5967</td><td>1723.143</td><td>1835.174</td><td>0</td><td>1723.143</td><td>1654.146</td><td>1520</td></tr><tr><td>(6,3)</td><td>-0.05771</td><td>128.5704</td><td>1831.319</td><td>1929.226</td><td>1</td><td>1929.226</td><td>1929.226</td><td>1178.429</td></tr><tr><td>(6,5)</td><td>-0.12436</td><td>239.6839</td><td>1604.725</td><td>1691.46</td><td>0</td><td>694.0262</td><td>1604.725</td><td>1691.46</td></tr><tr><td>(6,7)</td><td>-0.10083</td><td>222.227</td><td>1766.081</td><td>1880.904</td><td>0</td><td>60</td><td>60</td><td>1450</td></tr><tr><td>(6.9)</td><td>-0.11863</td><td>274.7702</td><td>1912.986</td><td>2058.336</td><td>1</td><td>1089.46</td><td>1770.982</td><td>1080</td></tr><tr><td>(7,3)</td><td>-0.15074</td><td>293.6677</td><td>1613.653</td><td>1732.975</td><td>1</td><td>1419.456</td><td>1566.745</td><td>940</td></tr><tr><td>(7,6)</td><td>-0.1061</td><td>266.6403</td><td>2033.826</td><td>2166.056</td><td>0</td><td>60</td><td>60</td><td>1531.46</td></tr><tr><td>(7,10)</td><td>-0.12228</td><td>231.7266</td><td>1573.366</td><td>1693.836</td><td>1</td><td>1340</td><td>1240.544</td><td>280</td></tr><tr><td>(8,4)</td><td>-0.18654</td><td>392.8358</td><td>1753.403</td><td>1884.088</td><td>0</td><td>60</td><td>1485.408</td><td>570</td></tr><tr><td>(8.5)</td><td>-0.10207</td><td>265.2706</td><td>2087.545</td><td>2223.268</td><td>0</td><td>2087.545</td><td>60</td><td>800.1109</td></tr><tr><td>(8.9)</td><td>-0.11696</td><td>276.1399</td><td>1945.206</td><td>2094.146</td><td>1</td><td>1763.143</td><td>2094.146</td><td>1850</td></tr><tr><td>(9,6)</td><td>-0.10476</td><td>222.227</td><td>1712.587</td><td>1842.712</td><td>1</td><td>850.5437</td><td>1842.712</td><td>1718.429</td></tr><tr><td>(9,8)</td><td>-0.11208</td><td>274.7702</td><td>2004.429</td><td>2157.904</td><td>1</td><td>2127.545</td><td>1925.408</td><td>1130.111</td></tr><tr><td>(9,10)</td><td>-0.10067</td><td>233.0963</td><td>1854.87</td><td>1961.588</td><td>1</td><td>1475.058</td><td>1697.552</td><td>690</td></tr><tr><td>(10,7)</td><td>-0.11863</td><td>249.1835</td><td>1734.848</td><td>1867.682</td><td>1</td><td>1214.514</td><td>1337.552</td><td>361.4603</td></tr><tr><td>(10.9)</td><td>-0.12811</td><td>231.7266</td><td>1513.468</td><td>1600.544</td><td>1</td><td>1600.544</td><td>1600.544</td><td>608.5397</td></tr></table></body></html>

表3目标函数上下界变化  

<html><body><table><tr><td>k</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>μk</td><td>15211.77</td><td>15617.21</td><td>15617.21</td><td>15680.48</td><td>16067.05</td><td>16067.05</td><td>16067.05</td><td>16067.05</td><td>16396.26</td><td>16396.26</td></tr><tr><td>Vk</td><td>16832.24</td><td>16573.36</td><td>16573.36</td><td>16464.88</td><td>16464.88</td><td>16464.88</td><td>16464.88</td><td>16464.88</td><td>16464.88</td><td>16464.88</td></tr></table></body></html>

表4序列线性子模型目标值和对应的原模型的目标值  

<html><body><table><tr><td>序号</td><td>OLP</td><td>OUE</td><td>序号</td><td>OLP</td><td>OUE</td><td>序号</td><td>OLP</td><td>OUE</td></tr><tr><td>1</td><td>15211.77</td><td>16832.24</td><td>8</td><td>15450.44</td><td>17055.41</td><td>15</td><td>15914.67</td><td>16848.45</td></tr><tr><td>2</td><td>15263.66</td><td>16580.75</td><td>9</td><td>16067.05</td><td>17558.35</td><td>16</td><td>15914.67</td><td>16848.45</td></tr><tr><td>3</td><td>15617.21</td><td>16573.36</td><td>10</td><td>15738.92</td><td>17178.54</td><td>17</td><td>16396.26</td><td>17327.44</td></tr><tr><td>4</td><td>15549.04</td><td>17207.67</td><td>11</td><td>15514.04</td><td>17003.02</td><td>18</td><td>15914.67</td><td>16848.45</td></tr><tr><td>5</td><td>15286.61</td><td>16574.02</td><td>12</td><td>15573.01</td><td>17003.02</td><td>19</td><td>16720.5</td><td>17666.53</td></tr><tr><td>6</td><td>15450.44</td><td>17055.41</td><td>13</td><td>15733.04</td><td>16811.41</td><td>20</td><td>16932.93</td><td>17631.02</td></tr><tr><td>7</td><td>15680.48</td><td>16464.88</td><td>14</td><td>15799.49</td><td>16812.38</td><td>21</td><td>16724.77</td><td>17928.88</td></tr></table></body></html>

# 参考文献：

[1]Wardrop JG.Some theoretical aspects of road traffic research [J]. Proceedings of the Institution of Civil Engineers Part I,1952,1(5): 325- 378.   
[2]Sheffi Y. Urban Transportation networks:equilibrium analysiswith mathematical programming methods [M]. Englewood Cliffs:Prentice-Hall, Inc.,1985.   
[3]Dafermos S C,Sparrow FT.The trafic assignment problem for a general network[J].J.Res.Natl.Bureau Stand.,Ser.B,1969,73 (2): 91-118.   
[4]Daganzo C F,Sheffi Y.On stochastic models of trafic assignment [J]. Transportation Science,1977,11 (3): 253-274.   
[5]Bar-Gera H. Origin-based algorithm for the traffic assignment problem [J]. Transportation Science,2002,36 (4): 398-417.   
[6]何胜学，范炳全．多用户动态交通流分配模型及算法研究[J].上海理 工大学学报,2006,28(5):460-464.   
[7]何胜学，董琼，徐福缘．基于网络对偶均衡的交通流分配模型[J]．公 路交通科技,2010,27(9):105-110.   
[8] 何胜学，何建佳，徐福缘．基于网络对偶均衡的有边约束的交通流分配 模型[J].交通运输系统工程与信息,2011,11(2):100-105.   
[9]何胜学，李秋曼．考虑边约束的网络交通流分配及应用[J].计算机应 用研究,2011,28(7):2595-2598.   
[10]Xie J,Xie C.New insights and improvements of using paired alternative segments for traffic assignment [J].Transportation Research Part B,2016, 93 (4): 406-424.   
[11] Ma W,Qian S.On the variance of recurrent trafc flow for statistical traffic assignment[J]. Transportation Research Part C,2017,81(1):57-82.   
[12] Guo R Y,Huang H J.A discrete dynamical system of formulating trafic assignment: Revisiting Smith's model[J].Transportation Research Part C, 2016,71(2): 122-142.   
[13] Daganzo C F.The cell transmission model: a dynamic representation of highway traffic consistent with the hydrodynamic theory. Transportation Research Part B,1994,28(4),269-287.   
[14] Daganzo C F. The cell transmission model,part II:network traffic [J]. Transportation Research Part B,1995,29 (2),79-93.   
[15]He SX.Will a higher free-flow speed lead us toa less congested freeway? [J].Transportation Research Part A,2016,85(1):17-38.