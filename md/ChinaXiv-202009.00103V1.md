# 带模糊需求的开放式选址路径问题的混合离散蘑菇繁殖算法

刘凡，张惠珍，周迅(上海理工大学 管理学院，上海 200093)

摘要：针对带限制的开放性选址路径问题的研究，考虑模糊需求的条件下，以仓库选址成本、车辆行驶距离成本、机会损失成本、额外距离等目标之和最小化的要求下建立数学模型。通过对蘑菇繁殖算法的改造，使用部分映射交叉和路径重连算法代替原算法中父代更新方式；在邻域搜索部分使用概率法进行邻域选择；使用随机模拟程序对设计好的路径进行模拟，计算因服务失败而产生的额外行驶距离与机会损失成本。在保留算法原有特性的情况下，使其成功应用于组合优化问题。最后，通过一系列算例测试与对比，验证了模型的正确性与有效性以及混合离散蘑菇繁殖算法的计算效率和优化能力。

关键词：开放性选址路径问题；模糊需求；蘑菇繁殖算法；路径重连算法；随机模拟程序 中图分类号：TP doi:10.19734/j.issn.1001-3695.2020.02.0023

Hybrid discrete mushroom reproduction algorithm for solving open location-routing problem with fuzzy demands

LiuFan, ZhangHuizhen†,Zhou Xun (Business School,University ofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract:Thispaperproposedthe mathematicalmodel whichbasedon theopenlocationrouting problemwith fuzzydemands considering with thesumoflocationcost,routingcost,lostopportunityandadditional distances.Forsolvingthe mathematical model,this paper proposed anew swarm intellgence algorithm named hybrid discrete mushroom algorithm.The artificial windreplaced bypartly mapping crossoverand pathrelinking algorithm; Andthe localsearchstrategyreplaced bythe method ofselectingdifferent neighborhoods withacertain probability;Stochastic simulationsimulatedthedesignedroutes tocompute additional distances and lost opportunity resulting from serving failure.Thealgorithm successfully applied to the combinatorial optimization problems under theconditionofretaining theoriginal characteristicsof the algorithm.Finaly, verifythe validityof the mode and the performanceofhybrid discrete mushroomreproduction algorithm througha series of tested instances and comparisons.

Key words:open location routing problem; fuzzy demand; mushroom reproduction algorithm; path relinking algorithm; stochastic simulation

# 0 引言

快速、精确的车辆路径规划与合理的仓库选址对现代物流管理有着重要影响，其不仅可以节约配送成本，而且可以提高客户满意度及企业的竞争力。很多学者研究指出：将车辆路径问题(vehicle routingproblem，VRP)与设施选址问题(facilitylocationproblem，FLP)分开考虑时，不免会因为所考虑的影响因素不足而导致管理者无法作出最优决策。现如今，两者的综合问题—一选址路径问题(location-routingproblem，LRP)已成为物流管理、供应链管理及运筹优化领域的研究热点。

根据实际需求，在标准LRP问题中加入不同的约束条件即可形成不同的LRP扩展问题。如：根据物流配送中存在客户需求、服务时间等的不确定性，在LRP模型中加入各种模糊限制条件，形成带模糊需求的选址路径模型[7]，不确定性条件下带时间窗的选址路径模型[12]，多元联运网络下带模糊需求的选址路径模型[8]，应急物流系统中多目标模糊选址路径问题模型[4]，多车型并考虑震后路网变化情况的应急物资动态选址路径问题模型[16,17]。此外，由于近年来第三方物流的兴起，许多企业进行战略重组，为了提高企业核心竞争力，将更多精力专注于核心业务，而将物流服务外包给第三方公司。在此情况下，提出了由第三方物流配送的选址路径问题——开放式选址路径问题(Open location-routingproblem,OLRP)。虽然实际配送中，OLRP也会面临各种模糊限制条件，但由于OLRP是近年来提出的新问题，国内外现有文献中对带模糊限制条件的OLRP问题研究尚少，仅在文献[15]中，王海军等人建立了关于OLRP的多目标混合整数规划模型，利用概率进行选择更加安全可靠的路径进行配送，使用NSGA-II(基于非支配解排序的遗传算法)和 NSDE(基于非支配解排序的差分进化算法)求解了关于汶川地震中救援物资配送的实例。

LRP属于NP难问题。使用精确算法(如分支定界法、列生成法等)仅可以求解小规模的LRP问题，然而，从实际物流配送中抽象出来的LRP问题往往规模较大，精确算法难以在可接受的计算时间内给出问题的解决方案。为此，在有限计算时间内能给出近似最优解的智能优化算法已成为LRP问题的主要求解方法，如：蚁群算法[10\~13],遗传算法[4,8,15,17\~19]和模拟退火算法[5,12]在求解LRP问题中均取得了较为满意的结果。

本文将模糊需求与OLRP相结合，提出了带模糊需求的开放式选址路径问题(Open location-routing problem withfuzzydemand,OLRP-FD)，其能够很好解决目前第三方物流配送中所面临的客户需求的不确定性问题，对节约企业配送成本具有重要意义。此外，本文在基本蘑菇繁殖算法[14]中引入新的邻域搜索方法，设计求解OLRP-FD问题的离散蘑菇繁殖算法，这不仅为OLRP问题的求解提供了一种新的解决方案，而且拓宽了蘑菇繁殖算法的应用领域。算法中的邻域搜索在评估搜索父代蘑菇邻近区域的基础上，生成子代孢子来细化这些区域以搜索更优的解，数值实验表明该算法在有限的计算时间内可为OLRP-FD提供较优的解。

# 1模型

OLRP-FD相较于标准OLRP的不同之处在于客户的需求是模糊的，而非确定的，只有配送车辆在抵达客户时，才能知道客户的具体需求。因此，在OLRP-FD中，当配送车辆在抵达客户时，可能会发现因为车辆的剩余容量不足而无法服务当前客户，此时，车辆需要返回仓库重新装载，之后再回到未被服务的客户进行服务。OLRP-FD中模糊的客户需求不仅会导致配送车辆返回仓库重新装载带来额外的行驶距离而且会因配送车辆预先配备不足而无法服务部分客户，产生一定的机会损失成本。

本文使用可信度测量理论来构建OLRP-FD的数学模型，模型在满足车辆容量、最大行驶距离等条件下，要求不仅最小化总配送成本(包括车辆固定启用成本、车辆计划行驶总距离成本、未服务客户的机会损失成本)，而且最小化车辆由于服务‘失败’而额外行驶的总距离。

# 1.1 可信度理论

模糊集理论最先由Zadeh[21通过隶属度函数提出，之后，由Kafumann[23]和 Zadeh[22]完善了测量模糊事件的模糊变量可能性测量理论，但其缺乏自对偶性。Liu[9]为定义其自对偶性，提出了关于模糊变量的可信度测量理论。

假设 ${ \bf \Pi } ( \Theta , P ( \Theta ) , P o s { \bf \Theta } )$ 为可能性空间， $A$ 是 $P ( \Theta )$ 中的一个事件,$P o s \{ A \}$ 表示事件 $A$ 发生的可能性，那么 $A$ 的必要性(也就是事件 $A$ 发生的必要性)则为 $N e c \{ A \} { = } 1 - P o s \{ A ^ { c } \}$ 。记 $A ^ { c }$ 为事件 $A$ 的补集，进而可得事件 $A$ 的可信度 $C r \{ A \} = 1 / 2 ( N e c \{ A \} + P o s \{ A ^ { c } \} )$ 。

本文中将客户需求使用三角模糊变量进行表示为$d = ( d \iota , d \iota , d \iota )$ ，其中， $d _ { I }$ 和 $d _ { 3 }$ 分别是客户需求的上下界，客户的需求一定在这个范围之内； $d _ { 2 }$ 表示隶属度函数值为1的时候所对应的客户需求。这三个参数一般由相关数据或者经验主观估计得到。假设一个客户的实际需求为 $\boldsymbol { r }$ ，隶属度函数如图1所示，其可能性，必要性，可信度可分别由公式(1)-(3)计算所得。

![](images/edc4e67b80521a52d9cb21095e1c25454d7d6a4613359660e05836b2269bda69.jpg)  
图1三角模糊变量隶属度函数

Fig.1Membership function of triangular fuzzy variable

$$
\begin{array} { r l } &  \begin{array} { l l } { \displaystyle 1 } & { i f ~ r \leq d _ { 3 } } \\ { \displaystyle } & { } \\ { P o s ( \tilde { d } \geq r ) = \left\{ \begin{array} { l l } { 1 } & { i f ~ d _ { 2 } \leq r \leq d _ { 3 } } \\ { \displaystyle \frac { d _ { 3 } - r } { d _ { 3 } - d _ { 2 } } } & { i f ~ d _ { 2 } \leq r \leq d _ { 3 } } \\ { 0 } & { i f ~ r \geq d _ { 3 } } \end{array} \right. } \\ & { \begin{array} { r l } & { 0 } \\ { N e c ( \tilde { d } \geq r ) = \left\{ \begin{array} { l l } { 1 } & { i f ~ r \leq d _ { 1 } } \\ { \displaystyle \frac { d _ { 2 } - r } { d _ { 2 } - d _ { 1 } } } & { i f ~ d _ { 1 } \leq r \leq d _ { 2 } } \\ { 0 } & { i f ~ r \geq d _ { 2 } } \end{array} \right. } \end{array} } \end{array} \end{array}
$$

# 1.2问题描述

本文在可信度理论的基础上，构建带模糊需求的开放式选址路径问题的数学模型，由选中的仓库派出车辆为客户提供配送服务，并假设：a)每辆车只能服务最多一条线路；b)仓库和车辆有固定的容量限制；(3)配送车辆有最大行驶距离限制；c车辆服务完最后一个客户后，并不会返回仓库，而是返回第三方物流企业车辆集散中心；d由于每个客户需求的模糊性，可能会存在因为车辆数不足而有客户无法被服务的情况，此时会产生相应的机会损失成本。

对于客户需求是模糊的这一情况，文章利用可信度理论来判断当前车辆以及仓库是否能服务下一个新的客户。假设车辆与仓库的容量分别为 $\varrho$ 和 $P$ ，当车辆或仓库服务完计划线路中的第 $e$ 个客户时，当前车辆的剩余容量为$Q _ { e } = ( Q - \sum _ { j = 1 } ^ { e } d _ { 3 j } , Q - \sum _ { j = 1 } ^ { e } d _ { 2 j } , Q - \sum _ { j = 1 } ^ { e } d _ { 1 j } ) = ( q _ { 1 , e , } , q _ { 2 , e , } , q _ { 3 , e } )$ ；当前仓库的剩余容量为 $P _ { e } = ( P - \sum _ { j = 1 } ^ { e } d _ { 3 j } , P - \sum _ { j = 1 } ^ { e } d _ { 2 j } , P - \sum _ { j = 1 } ^ { e } d _ { 1 j } ) = ( p _ { 1 , e } , p _ { 2 , e } , p _ { 3 , e } )$ 。那么，下一个客户需求不超过车辆容量和仓库容量的可信度可分别表示为式(4)和(5)：

$$
C r \{ \tilde { d } _ { { e + 1 } } \leq Q _ { { e } } \} = C r \{ ( \tilde { d } _ { { 1 } , { \ e + 1 } } - q 3 , { e } , \tilde { d } _ { { 2 } , { \ e + 1 } } - q 2 , { e } , \tilde { d } _ { { 3 } , { \ e + 1 } } - q 1 , e ) \leq 0 \}
$$

$$
C r \{ \tilde { d } _ { { e + 1 } } { \le } P _ { e } \} = C r \{ ( \tilde { d } _ { { 1 } , { \ { e + 1 } } } - p 3 , { e } , \tilde { d } _ { { 2 } , { \ e + 1 } } - p 2 , { e } , \tilde { d } 3 , { \ e + 1 } - p 1 , { e } ) { \le } 0 \}
$$

进而，由式(3)可将 $C r \{ \tilde { d } _ { e } { _ + } 1 \le Q _ { e } \}$ 和 $C r \{ \tilde { d } _ { e } { _ + } 1 \le P _ { e } \}$ 分别表示为下式(6)和(7):

$$
\begin{array} { r l } & { \displaystyle { C r ( \tilde { d } _ { { e } + 1 } \leq Q _ { e } ) } = } \\ { \displaystyle { \left[ \begin{array} { c c } { 0 } & { d _ { 1 , e + 1 } \geq q _ { 3 , e } } \\ { \frac { q _ { 3 , e } - d _ { 1 , e + 1 } } { 2 * \left( q _ { 3 , e } - d _ { 1 , e + 1 } + d _ { 2 , e + 1 } - q _ { 2 , e } \right) } } & { d _ { 1 , e + 1 } \leq q _ { 3 , e } , d _ { 2 , e + 1 } \geq q _ { 2 , e } } \\ { \frac { d _ { { s , e } - 1 - q _ { 1 , e } - 2 * } ( d _ { 2 , e + 1 } - q _ { 2 , e } ) } { 2 * \left( q _ { 2 , e } - d _ { 2 , e + 1 } + d _ { 3 , e + 1 } - q _ { 1 , e } \right) } } & { d _ { 2 , e + 1 } \leq q _ { 2 , e } , d _ { 3 , e + 1 } \geq q _ { 1 , e } } \\ { 1 } & { d _ { 3 , e + 1 } \leq q _ { 1 , e } } \end{array} \right] } } \end{array}
$$

$$
\begin{array} { r } { \left[ \begin{array} { c c } { C r ( \widetilde { d } _ { { e } + 1 } \leq P _ { e } ) = } \\ { 0 } \\ { 0 } \\ { \frac { p _ { 3 , e } - d _ { 1 , e + 1 } } { 2 * \left( p _ { 3 , e } - d _ { 1 , e + 1 } + d _ { 2 , e + 1 } - p _ { 2 , e } \right) } } & { d _ { 1 , e + 1 } \leq p _ { 3 , e } } \\ { \frac { d _ { 3 , e + 1 } - p _ { 1 , e } - 2 * \left( d _ { 2 , e + 1 } - p _ { 2 , e } \right) } { 2 * \left( p _ { 2 , e } - d _ { 2 , e + 1 } + d _ { 3 , e + 1 } - p _ { 1 , e } \right) } } & { d _ { 2 , e + 1 } \leq p _ { 2 , e } , d _ { 3 , e + 1 } \geq p _ { 1 , e } } \\ { \frac { d _ { 3 , e + 1 } - p _ { 1 , e } - 2 * \left( d _ { 3 , e + 1 } - p _ { 2 , e } \right) } { 2 * \left( p _ { 2 , e } - d _ { 2 , e + 1 } + d _ { 3 , e + 1 } - p _ { 1 , e } \right) } } & { d _ { 2 , e + 1 } \leq p _ { 2 , e } , d _ { 3 , e + 1 } \geq p _ { 1 , e } } \\ { 1 } & { d _ { 3 , e + 1 } \leq p _ { 1 , e } } \end{array} \right. } \end{array}
$$

$C r$ 为评估配送车辆或仓库是否为某个客户提供服务的参数，当 $C r$ 为0时，这个客户必定不会被当前车辆或仓库服务；当 $C r$ 为1时，该客户肯定会被当前车辆或仓库服务。文章设置了两个阈值 $D P I$ 和A $P I ( D P I \in [ 0 , 1 ] ,$ $A P I \in [ 0 , 1 ]$ )分别与车辆和仓库的可信度进行比较，当 $C r$ 大于所设置的阈值时，客户会被当前车辆或仓库服务；而小于所设置的阈值时，则不被当前车辆或仓库服务。显然，DPI和 $A P I$ 的取值大小对车辆计划行驶距离和额外行驶距离有着重要影响。当DPI取值较低时，车辆的容量会被尽可能使用，此时，路线中靠后的客户就极有可能服务失败，从而导致车辆要返回仓库重新装载，产生额外的行驶距离；当 $D P I$ 取值较高时，意味着仓库派出的车辆数较多，那么计划行驶距离就会增加，而服务失败的客户就会减少，产生的额外距离也随之减少。当API取值较低时，表明仓库会尽可能的消耗自己的容量去服务客户，不仅有可能导致其容量溢出，而且有可能导致仓库预留的配送车辆不足，部分被安排给此仓库服务的客户无法被提供服务，从而产生较大的机会损失成本；当API取值较高时，仓库的容量对客户的需求安排更加谨慎，因而出现容量溢出的情况比较少。本文通过随机模拟程序求解相应的额外行驶距离，并且会对DPI进行灵敏度分析，求得最优参数设置。

# 1.3模型

模型主要参数设置如下：

I：仓库集合；  
$J$ ：客户集合；  
$J K$ ：第三方物流公司车辆集散中心点；  
V: $I \cup J$ ：  
（204 $S$ ： $J K \cup J$ ;  
$K$ ：车辆集合；  
$d _ { j }$ ：第 $j$ 个客户的需求， $j \in J$ ;  
$\varrho _ { k }$ ：第 $k$ 辆车的容量， $k \in K$ ：  
$P _ { i }$ ：第 $i$ 个仓库的容量， $i \in I$ ：  
$O _ { i }$ ：第 $i$ 个仓库的开放成本， $i \in I$ ：  
$F _ { k }$ ：第 $k$ 辆车的启用成本， $k \in K$ ;  
$A D _ { k }$ ：第 $k$ 辆车行驶的额外距离， $k \in K$ ：  
$C _ { i j }$ ：由点 $i$ 到点 $j$ 的单位距离行驶费用， $i \in V , j \in V$ ：$T D _ { k }$ ：车辆 $k$ 的最大行驶距离， $k \in K$ ：  
$D _ { i j }$ ：点 $i$ 到点 $j$ 的欧氏距离， $i \in V , j \in V$ ：  
$B _ { j }$ ：未服务客户 $j$ 时的损失成本， $j \in J$ 。

决策变量设置如下：

$$
X _ { i j k } = \left\{ \begin{array} { l l } { 1 } & { \begin{array} { r l } & { \ddag \ddag \# \underline { { \# } } k \ j k \ k \ i \ \xrightarrow { r } \acute { \mathcal { T } } \ddag \underline { { \hat { \mathcal { T } } } } \ \underline { { \hat { \mathcal { T } } } } { \hat { \mathcal { R } } } \ll \underline { { \hat { \mathcal { T } } } } { \hat { \mathcal { T } } } { i } \in V , \forall j \in V , \forall j \in V , \forall k \in K } } \\ { 0 } & { \qquad \quad \vdots \ddagger / \mathrm { i } \underline { { \mathbb { L } } } } \end{array}  \end{array} \right.
$$

$$
Y _ { i j } = \left\{ { \begin{array} { r l r } { 1 } & { } & { { \big \Updownarrow } \overleftrightarrow { \ddagger } i { \mathrm { ~ } } \mathbb { H } \mathbb { X } \overleftrightarrow { \mathcal { Y } } \overleftrightarrow { \mathcal { Y } } } \end{array} } j , \forall i \in I , \forall j \in J \right.
$$

$$
Z _ { i } = \left\{ { \begin{array} { r l } { 1 } & { \quad { \widehat { \mathbb { G } } } | { \widehat { \mathbb { G } } } i \ { \mathcal { F } } { \dot { \mathfrak { H } } } { \mathcal { U } } , \forall i \in I } \\ { 0 } & { \quad { \widehat { \mathbb { H } } } { \mathcal { A } } \not \\\\\mu . } \end{array} } \right.
$$

在上述假设条件及模型参数和决策变量设置的基础上，OLRP-FD的数学模型可构建如下：

$$
\operatorname* { m i n } \sum _ { i \in I } O _ { i } Z _ { i } + \sum _ { i \in I } \sum _ { j \in J } \sum _ { k \in K } F _ { k } X _ { i j k } + \sum _ { i \in V } \sum _ { j \in J } \sum _ { k \in K } C _ { i j } D _ { i j } X _ { i j k }
$$

$$
\displaystyle \operatorname* { m i n } _ { k \in K } { A D _ { k } } + \sum _ { j \in J } ( 1 - \sum _ { i \in V } \sum _ { k \in K } X _ { i j k } ) B _ { j }
$$

$$
C r ( \sum _ { i \in V } \sum _ { j \in J } d _ { j } X _ { i j k } \leq Q _ { k } ) \geq D P I \quad \forall k \in K
$$

s.t.

$$
C r ( \sum _ { j \in J } d _ { j } Y _ { i j } \le P _ { i } Z _ { i } ) \ge A P I \quad \forall i \in I
$$

$$
\sum _ { i \in V } \sum _ { k \in K } X _ { i j k } \leq 1 \quad \forall j \in J
$$

$$
W _ { i k } - W _ { j k } + N X _ { i j k } \leq N - 1 \quad \forall i , j \in J ; \forall k \in K
$$

$$
\sum _ { i \in I } \sum _ { j \in J } X _ { i j k } \leq 1 \quad \forall k \in K
$$

$$
\sum _ { i \in V } X _ { i j k } - \sum _ { i \in S } X _ { j i k } = 0 \quad \forall j \in J ; \forall k \in K
$$

$$
\sum _ { l \in J } X _ { i l k } + \sum _ { l \in \{ V \backslash j \} } X _ { l j k } \leq 1 + Y _ { i j } \quad \forall i \in I ; \forall j \in J ; \forall k \in K
$$

$$
\sum _ { i \in I } Y _ { i j } = 1 \forall j \in J
$$

$$
\sum _ { i \in V } \sum _ { j \in J } D _ { i j } X _ { i j k + A } D _ { k } \leq T D _ { k } , \forall k \in K
$$

$$
\sum _ { j \in J } X _ { i j k } - Z _ { i } \le 0 ~ \forall i \in I , \forall k \in K
$$

$$
\sum _ { j \in J } \sum _ { k \in K } Z i - X _ { i j k } \leq 0 \quad \forall i \in I
$$

$$
X _ { i j k } \in \{ 0 , 1 \} \quad \forall i \in V ; \forall j \in S ; \forall k \in K
$$

$$
Y _ { i j } \in \{ 0 , 1 \} \quad \forall i \in I ; \forall j \in J
$$

$$
Z _ { i } \in \{ 0 , 1 \} \quad \forall i \in I
$$

$$
W _ { i k } \in \{ 0 \cup N \} \quad i \in J ; k \in K
$$

其中，目标函数(8)表示最小化总成本，包括仓库和车辆的固定启用成本、车辆计划行驶总距离成本；目标函数(9)表示最小化由服务‘失败’而导致的车辆行驶的额外距离之和以及未被服务客户的机会损失成本；模糊机会约束(10)保证配送车辆对所有客户进行访问时，车辆容量与客户需求满足所设置的可信度水平；模糊机会约束(11)表示仓库为客户提供服务时，其容量与客户需求满足所设置的可信度水平；约束(12)表示一个客户最多被一辆车服务；约束(13)用于消除子路径;约束(14)表示任意车辆最多被启用一次；约束(15)保证路径的连续性，进出每个点的流量相同；约束(16)和(17)表示客户被某个仓库服务时，必定有路线将两者相连；约束(18)表示车辆的最大行驶距离限制；约束(19)和(20)表示两个决策变量之间的关系；约束(21-23)表示3组不同的0-1决策变量；约束(24)为消除子路径所用的辅助变量。

# 2 求解OLRP-FD的混合离散蘑菇繁殖算法

蘑菇繁殖算法[14](mushroom reproduction optimization,MRO)是基于蘑菇生长繁殖特性而提出的一种新型群智能优化算法，已在连续优化问题的求解中取得了较好的效果。为了进一步拓宽MRO算法的应用领域，本文将其与贪心聚类算法、路径重连算法及邻域搜索等相结合，设计求解OLRP-FD的混合离散蘑菇繁殖算法(hybriddiscrete mushroomreproduction optimization,HDMRO)。

HDMRO由三部分组成：a)初始化：使用贪心聚类算法生成一组高质量的初始解，以便算法能够更好地寻优迭代；b)离散蘑菇繁殖算法：在基本MRO 算法的基础上，结合OLRP-FD问题的具体特征，与部分映射交叉和路径重连算法，以及邻域搜索相融合，逐步使问题的解得到优化；c随机模拟程序：通过模拟客户的实际需求，计算车辆服务时产生的额外距离。

# 2.1基本蘑菇繁殖算法

蘑菇繁殖算法[14]通过模拟蘑菇繁殖和生长的机制，父代蘑菇通过风的力量来传播自己的孢子，让其探索各个繁殖区域，并细化搜索空间，找到更优秀的繁殖区域来进行生长繁殖搜索活动。基本蘑菇繁殖算法最初是用来解决连续优化问题的，其关键步骤为：在进行局部搜索之前，根据每个菌落的平均适应度值 $( A \nu g ( i ) )$ 和所有菌落的平均适应度值 $T _ { a v g }$ ，判断 $A \nu g ( i ) + T _ { a \nu g } / c$ 与 $T _ { a \nu g }$ 的大小关系 ${ } ^ { \prime } c$ 为一个固定的阈值，$c \in [ 1 , 1 0 ]$ )，决定是否需要删除一些菌落。若是前者大于后者，则不进行父代蘑菇的删除，若小于，则对父代蘑菇进行更新，选取更加优秀的父代细化搜索空间，以便于搜索到优秀的解。对父代蘑菇进行更新时，通过构造人工风来进行孢子之间信息交换更新。第 $j$ 个子代蘑菇人工风的初始计算公式为(25):

$$
M o v _ { j } ^ { w i n d } = ( X _ { i } ^ { * } - X _ { k } ^ { * } ) \times ( \xrightarrow { A \nu g ( i ) } ) ^ { - \beta } \times r a n d ( \overrightarrow { - \delta , \delta } ) \times r s + r a n d ( \overrightarrow { - s , s } )
$$

其中， $X _ { i } ^ { * }$ 和 $\boldsymbol { X } _ { k } ^ { * }$ 分别为第 $i$ 和第 $k$ 个菌落的父代； $\beta \left( \beta \in \left[ 1 , + \infty \right) \right.$ ）为风的密度，； $\mathcal { S } \left( \mathcal { S } \in \left( 0 , 1 \right) \right.$ )为调整风的方向参数； $r s \big ( r s \in ( 0 , 1 ) \big )$ （20为控制风的步长的参数； $s$ 为搜索半径，其通常根据具体问题定义。

除上述步骤外，MRO算法中通常采用下述式(26)进行邻域搜索：

$$
X _ { i j } = X _ { i } ^ { * } + r a n d ( \overline { { - s , s } } )
$$

其中， $X _ { i j }$ 为第 $i$ 个父代蘑菇生成的第 $j$ 个孢子。

基本MRO算法主要通过式(25)和(26)进行迭代搜索，具体迭代优化步骤参见文献[14]。

# 2.2 初始化

# 2.2.1解的表示

本文采用自然数编码。假设 $\mid m$ 个仓库的编号分别为1，2，...， $m$ ； $n$ 个客户的编号分别为 $m { + } 1$ ， $m + 2$ ，.， $m + n$ ，则3个仓库，15个客户的OLRP-FD的算例的可行解可编码为图2所示的形式。若某一仓库编号之后无客户编号，则表示该仓库不开放；若某一仓库编号之后为客户编号，则表示该仓库开放，而且仓库编号出现的次数即为从该仓库出发的配送路线数。一辆车从对应编号的仓库出发，从左到右依次对相应客户进行服务，直到下一编号为仓库时，该车辆完成配送任务。如图2所示，仓库1关闭，仓库2和3开放；从仓库2出发的2条配送路线分别为 $2 {  } 5 {  } 7 {  } 4 {  } 1 0$ 和 $2 {  } 6$ $ 1 2  1 4  1 3  1 8$ ；从仓库3出发的配送路线为 $3 \to 1 7 \to 1 6$ $ 9  1 5  1 6  8$ 。这样的编码方式简单直观，能很好地解读出仓库所要服务的客户，每辆车所行驶的路线。

![](images/3b1a5d2181b50642146763db5fae624e1b73ca2afb1a580496b9b39fb809be98.jpg)  
Fig.2The representation of solution

2.2.2初始化

初始可行解的优劣不仅会影响解的质量，而且会影响算法的收敛速度。为了得到较优的初始可行解，本文使用贪心聚类算法进行初始化，其具体步骤如下：

# 1）聚类客户

利用贪心思想，根据车辆的容量，客户的模糊需求，以及客户之间的距离对客户聚类。一次聚类过程可简要描述为：a)生成一个空聚类(聚类的容量等于车辆的容量)，并从未被聚类的客户中随机挑选一个客户加入该聚类；b)从未被聚类的客户中，选择距新加入该聚类的客户最近的客户，并计算此客户的模糊需求与车辆剩余容量的可信度，若其值大于所给定的DPI，则将该客户加入当前聚类；否则，当前聚类不考虑此客户；c）重复步驟b），继续选择离最后一个被加入聚类的客户最近的客户，并判断其是否可以加入当前聚类，直到当前聚类的剩余容量不足以服务其他新客户时，一次聚类完成。重复步驟a) $\mathrm { \Pi \sim } \mathrm { c }$ 继续生成新的聚类，直到所有客户都被聚类为止。

# 2）选择开放仓库及分配客户聚类

首先，根据每个聚类中客户的坐标，由式(27)计算聚类重心。然后，由式(28)和(29)分别计算每个仓库到客户聚类重心的距离之和 $U _ { i }$ 和排序指标 $W _ { i }$ 。最后，按 $W _ { i }$ 值从大到小的顺序对仓库进行排序，开放 $W _ { i }$ 值最大的仓库，并将离它最近的客户聚类分配给它，接着分配离它次近的聚类，依此类推，当仓库剩余容量不足以服务任意未被分配的聚类时，开启排序序列中下一个仓库，直到所有聚类都被分配给仓库为止。将某一客户聚类分配给某一仓库时，需要考虑该聚类的总需求量与仓库剩余容量之间的可信度值是否大于给定的API值，若大于，则将聚类分配给该仓库；否则，检验下一未必分配的聚类是否满足该条件，直到仓库容量不足以服务任意聚类为止。

$$
( X _ { c } , Y _ { c } ) = ( \frac { \displaystyle \sum _ { j \in c } X _ { j } } { \displaystyle n _ { c } } , \frac { \displaystyle \sum _ { j \in c } Y _ { j } } { \displaystyle n _ { c } } ) , c \mathcal { H } _ { \mathcal { H } \ R } ^ { \# \times } \mathcal { H } _ { \mathsf { S } } ^ { \ * }
$$

$$
U _ { i } = \sum _ { c \in J } ( ( X _ { i } - X _ { c } ) ^ { 2 } + ( Y _ { i } - Y _ { c } ) ^ { 2 } ) ^ { 1 / 2 } , i \in I
$$

$$
W _ { i } = \frac { P _ { i } } { O _ { i } { ^ * } U _ { i } }
$$

3）构建配送线路

对每一客户聚类及为其分配的仓库，按照先仓库，后聚

类客户的顺序，随机构造一条配送路线。

# 2.3改进蘑菇繁殖算法

# 2.3.1部分映射交叉和路径重连算法

为了将蘑菇繁殖算法很好地应用于LRP问题的求解，提高其求解性能，本文利用部分映射交叉[24]和路径重连算法[20]替换基本蘑菇繁殖算法中对父代蘑菇利用风的力量进行全局搜索的处理方式(25)。具体方法为：首先，将第 $i$ 个菌落的父代蘑菇与全局最优解或第 $k$ 个菌落的父代蘑菇进行部分映射交叉，得到新解；然后使用路径重连算法对当前迭代菌落i的父代与部分映射交叉所产生的解进行连接，搜索两者之间更优的解。

部分映射交叉：产生随机数 $r \in [ 0 , 1 ]$ ，若 $r \leq 0 . 5$ ，选择全局最优解与第i个菌落的父代蘑菇进行交叉；若 $r > 0 . 5$ ，选择第 $k$ 个菌落的父代蘑菇与第 $i$ 个菌落的父代蘑菇进行交叉。实验证明本文所采用的部分映射交叉算法可以有效加快算法收敛速度。

图3给出仓库数和客户数分别为2和6的OLRP-FD实例的部分映射交叉过程。如图3所示：首先，随机选择父代P1和P2中的两个位置4和7，将父代个体第4到第7位中所有信息复制到其相应的子代个体Child1和Child2中(子代个体Child1 和 Child2 中其余位置用\*表示)，得到 Child1(\*)和 Child2(\*)，以及一组映射 $( 4  9 , ~ 1  6 , ~ 5  2 , ~ 7  4 )$ ；其次，从左到右依次扫描个体P1和P2，若父代P1(P2)中第 $i$ 个位置上的编码未在子代Child2(Child1)中，则将其复制于子代Child2的相应位置上，得子代Child1(\*)和Child2(\*)；再次，利用所得映射填充子代Child1' $( ^ { * } )$ 和Child2(\*)中的剩余空位，如：子代Child1 $( ^ { * } )$ 中的空缺位置1，2和3本应填入父代P2中相应位置的编码1，7和5，但由于Child1(\*)中已存在这些编码，则根据映射规则 $( 1 \to 6 , 7 \to 4 \to 9 , 5 \to 2 )$ 将1,7和5分别调整为6,9和2，得Child1'，同理，可得Child2'；最后，检查Child1'和Child2'第1个位置的编码，若Child1和Child2'第1个位置的编码为客户编码(如图3所示，Child1和Child2'第1个位置的编码分别为6和5)，则随机选取任意一个仓库(如图3所示，选取仓库1)与其交换，得最终解Child1和Child2。

![](images/8ddcde118ecb4650b5c8010bafaf29d400ac4231ee9b0f412bb7e31a75dc71bb.jpg)  
图2解的表示  
图3部分映射交叉  
Fig.3Partly mapping crossover

路径重连算法：路径重连算法主要是对两个解(作为当前种群父代孢子的当前解 $X ^ { i }$ 和部分映射交叉得到的目标解 $X ^ { t }$ 门信息的交换。算法具体过程可被描述如下：

a)计算初始解 $X ^ { i }$ 与引导解 $X ^ { t }$ 之间的汉明距离 HD，并令 目标解 $\boldsymbol { X } ^ { * } { = } \boldsymbol { X } ^ { t }$

b）若 $\mathrm { H D } { > } 0$ 且 HD为奇数，依次从左到右比较 $X ^ { i }$ 与 $X ^ { t }$ 相同位置的编码，并对不同的编码进行交换；若 $\mathrm { H D } { > } 0$ 且HD为偶数，依次从右到左比较 $X ^ { i }$ 与 $X ^ { t }$ 相同位置的编码，并对不同的编码进行交换；若 $\mathrm { H D = } 0$ ，则输出目标解 $\boldsymbol { { X } ^ { * } }$ 。交换过程可概述为：假设 $X ^ { i }$ 与 $X ^ { t }$ 第 $\mathbf { \Delta } _ { a }$ 个位置的编码不同，在 $X ^ { i }$ 中找到与 $X ^ { t } ( a )$ 的编码相同的位置 $b$ ，令 $X ^ { i } ( b ) { = } X ^ { i } ( a )$ ， $X ^ { i } ( a ) { = } X ^ { \prime } ( a )$

c）更新 HD： $= \mathrm { H D - 1 }$ ，并交换当前解 $X ^ { i }$ 与引导解 $X ^ { t }$ （ $X ^ { i }  X ^ { t }$ )，然后转步驟b)。

路径重连算法可以免去大多数连续优化的算法在求解离散问题时，解的信息从离散到连续，再从连续到离散的转换过程，有效防止了信息的丢失。

# 2.3.2邻域搜索

为了进一步提高蘑菇繁殖算法在离散优化问题中的寻优能力，本文在基本蘑菇繁殖算法的基础上，结合OLRP-FD问题的特点，选择了单点交换、插入和逆转3种邻域搜索机制，3种邻域以相同概率对解进行搜索。

交换位置2574102612141318 31716915168B0421243 3616915168

图4单点交换

单点交换：随机选择两个位置i和 $j$ ，将其相应位置的编码进行交换。如图4所示，位置7和14的编码分别为6和17，将其交换后，得到新的个体。需要注意的是：为了保证解的可行性，只能进行客户与客户之间的交换和仓库与仓库之间的交换，而客户与仓库之间不能进行交换。

单点插入：随机选择两个位置i和 $j$ ，将位置 $i$ 的编码插入到位置 $j$ 的编码之前。如图5所示，将位置7的编码17插入到位置14的编码6之前，得到新的个体。

![](images/6a20310dd80a29e67ba4fa3af07129103b8660e65de5b04fbc1cacccd6f9c222.jpg)  
Fig.4Exchange single point

逆转：随机选择两个位置 $i$ 和j，将位置i和 $j$ 之间(包括位置 $i$ 和 $j$ )的所有编码反向排序。如图6所示，将位置11和14之间的编码逆转排序后，得到新的个体。

![](images/2921a0301f430c77900b986405bc78b18998e5b4819ec47c088954d77cad6832.jpg)  
Fig.5Insert single point   
Fig.6 Inverse

# 2.4随机模拟程序

如前文所述，由于在OLRP-FD 模型中每个顾客的需求都是由三角模糊变量表示，所以，当HDMRO优化好仓库选址位置和车辆行驶路线之后，本文使用随机模拟[12]的方法模拟每个客户的实际需求，进而计算机会损失成本(由于仓库车辆数不足以服务所有客户时产生的机会损失成本)和车辆行驶的额外距离(由于车辆按照规划路线行驶至某个客户时，车辆剩余货物量无法满足当前服务客户的需求，从而车辆需要返回仓库重新装载货物来服务当前客户，此时车辆就会产生额外行驶距离，距离为往返当前客户与仓库之间的距离；或是由于车辆在抵达当前客户之后，发现剩余货物量不足以服务当前客户，则车辆需要返回仓库进行装载，然而车辆从当前客户返回仓库的距离与之前已经行驶的距离之和超过最大距离约束，那么仓库就只需要重新派出一辆车为当前客户服务，而此时的额外距离则为当前客户到仓库之间的距离)。随机模拟程序的具体步骤如下：

a）生成每个客户的实际需求。对 $\forall j \in J$ ，(a)在区间 $[ d _ { 1 } , d _ { 3 } ]$ 内产生随机数 $r$ ，并计算其相应的隶属度 $\mu$ ；(b)随机生成一个实数 $\mathfrak { a }$ 在区间[0,1]，如果 $\alpha { \leq } \mu$ ，采用客户的实际需求为 $\boldsymbol { r }$ 。否则，重新随机生成 $\boldsymbol { r }$ 和 $\mu$ ，直到满足上述关系。此程序将模拟所有客户的实际需求。

b）沿着HDMRO 生成的每条配送路线移动，根据实际需求计算由于车辆服务‘失败’而产生的额外距离以及机会损失成本。

c）重复上述两个步骤400次，取平均额外距离和平均损失成本为最终的额外距离与损失成本。

# 2.5HDMRO 算法流程

HDMRO算法的具体步骤如下：

a)初始化参数。父代蘑菇数量(种群数量 $M )$ ，每个父代产生孢子个数 $N$ ，算法最大迭代次数 $G ( g = 1 )$ ，阈值c。

b)调用贪心聚类算法生成初始可行解。每个父代蘑菇通过邻域搜索生成 $N$ 个孢子，计算每个个体的适应度值，选取每个父代蘑菇和其产生的孢子中的最优适应度值的个体作为新的父代，更新每个父代蘑菇。

c）正式开始迭代。若 $A \nu g ( i ) + T _ { a \nu g } / c > T _ { a \nu g }$ ，转步骤d)；否则，转步骤e）。

d)调用部分映射交叉生成一个路径重连算法所需的引导解，再调用路径重连算法连接当前迭代次数的第 $i$ 个种群的父代解与部分映射交叉生成的引导解，搜索两个解之间的区域。更新每个菌落的父代蘑菇和全局最优值。

e)邻域搜索。利用概率法对三种邻域进行选择，父代蘑菇根据选择出的邻域进行繁殖，产生孢子，搜索解空间。更新每个菌落的父代蘑菇和全局最优值。

D $g = g + 1$ ，若 $g { < } G$ ，转步驟c)，并继续迭代；否则，输出当前最优解，并转步骤g）。

g）将优化好的路线使用随机模拟程序进行模拟，求解出相应的额外行驶距离和未被服务客户带来的机会损失成本。

![](images/29915b841d42cacfe012aa6e0647700eb8e9f4bc6acb5d41e92f6a3b5afb0dad.jpg)  
图5单点插入  
图7HDMRO 算法流程图Fig.7The flow chart of HDMRO

# 3 算例测试与结果分析

为了验证混合蘑菇算法在解决OLRP-FD模型的有效性，本文仿照文献[11随机生成两组规模不同的算例。其中，客户的需求 $\tilde { d } = ( \tilde { d } _ { 1 } , \tilde { d } _ { 2 } , \tilde { d } _ { 3 } )$ 分别从[1,35]，[36,60]，[61,110]，三个区间内随机生成，其他相关数据见表1。本文实验环境是在Windows10系统下的MATLABR2017a实现混合蘑菇算法的编码以及相关算例的实验。相关参数：父代种群大小 $N { = } 4 0$ 子代个数 $\scriptstyle { M = 8 }$ ；最大迭代次数 $G { = } 6 0 0$ ；阈值 $c = 1 0$ 。

表1测试算例相关信息  
Tab.1The relative data of tested instances   

<html><body><table><tr><td>客户 数量</td><td>候选仓库数量/ 仓库车辆数</td><td>容量容量</td><td></td><td>车辆 仓库 仓库的启 用成本</td><td>用成本</td><td>车辆的启 车辆最大距 离限制</td></tr><tr><td>30</td><td>5/5</td><td>300</td><td>1200</td><td>100</td><td>20</td><td>300</td></tr><tr><td>50</td><td>5/8</td><td>500</td><td>2000</td><td>100</td><td>20</td><td>300</td></tr></table></body></html>

# 3.1DPI的灵敏度分析

此部分将DPI值设置以步长0.1的长度，在区间0-1内变化，并且，为了方便测试，节约计算时间，将API值固定为1(保证仓库一定能服务归属于它的所有客户)。测试数据如表2、3所示。

图7和8分别对应表2和3的内容，如图7和8所示，随着DPI值的增加，启用的车辆数增加，同时导致计划行驶路线距离长度的增加，那么，此时车辆服务客户失败的可能性降低，车辆的额外行驶距离就会减少；而仓库的开放成本保持不变，机会损失成本为0是由于每个仓库的可用车辆数足够，而额外行驶距离并未使车辆数超过可用数量，所以这两个算例中的机会损失成本为零，也表明算例中每个客户都会被服务。从图7和8可观察到，随着DPI值的变化，当API值一定时，DPI取0.6左右时，目标总成本达到最小值。

表230个客户算例测试结果

Tab.2The computational results when the number of customer is 30   
表350客户算例测试结果  

<html><body><table><tr><td>DPI</td><td>计划路线距离</td><td>额外行驶距离</td><td>总行驶距离</td><td>机会损失成本</td><td>仓库开放费用</td><td>车辆费用</td><td>总成本</td><td>计算时间/s</td></tr><tr><td>0.1</td><td>410.72</td><td>156.20</td><td>566.92</td><td>0.00</td><td>300</td><td>62</td><td>928.92</td><td>134.22</td></tr><tr><td>0.2</td><td>419.90</td><td>134.22</td><td>554.12</td><td>0.00</td><td>300</td><td>86</td><td>940.12</td><td>140.08</td></tr><tr><td>0.3</td><td>428.33</td><td>132.70</td><td>561.03</td><td>0.00</td><td>300</td><td>100</td><td>961.03</td><td>130.46</td></tr><tr><td>0.4</td><td>439.02</td><td>123.74</td><td>562.76</td><td>0.00</td><td>300</td><td>100</td><td>962.76</td><td>127.71</td></tr><tr><td>0.5</td><td>440.85</td><td>123.11</td><td>563.96</td><td>0.00</td><td>300</td><td>100</td><td>963.96</td><td>132.99</td></tr><tr><td>0.6</td><td>449.28</td><td>39.91</td><td>489.19</td><td>0.00</td><td>300</td><td>122</td><td>911.19</td><td>128.25</td></tr><tr><td>0.7</td><td>459.14</td><td>16.69</td><td>475.83</td><td>0.00</td><td>300</td><td>144</td><td>919.83</td><td>129.12</td></tr><tr><td>0.8</td><td>462.39</td><td>0.99</td><td>463.38</td><td>0.00</td><td>300</td><td>160</td><td>923.38</td><td>130.44</td></tr><tr><td>0.9</td><td>468.02</td><td>0.07</td><td>468.09</td><td>0.00</td><td>300</td><td>160</td><td>928.09</td><td>132.26</td></tr><tr><td>1</td><td>495.48</td><td>0.00</td><td>495.48</td><td>0.00</td><td>300</td><td>190</td><td>985.48</td><td>133.42</td></tr></table></body></html>

Tab.3The computational results when the number of customer is 50   

<html><body><table><tr><td>DPI</td><td>计划路线距离</td><td>额外行驶距离</td><td>总行驶距离</td><td>机会损失成本</td><td>仓库开放费用</td><td>车辆费用</td><td>总成本</td><td>计算时间/s</td></tr><tr><td>0.1</td><td>534.79</td><td>219.5</td><td>754.29</td><td>0.00</td><td>300</td><td>62</td><td>1116.29</td><td>195.22</td></tr><tr><td>0.2</td><td>538.04</td><td>182.28</td><td>720.32</td><td>0.00</td><td>300</td><td>86</td><td>1106.32</td><td>174.30</td></tr><tr><td>0.3</td><td>540.73</td><td>111.28</td><td>652.01</td><td>0.00</td><td>300</td><td>92</td><td>1044.01</td><td>228.01</td></tr><tr><td>0.4</td><td>542.27</td><td>104.56</td><td>646.83</td><td>0.00</td><td>300</td><td>100</td><td>1046.83</td><td>210.21</td></tr><tr><td>0.5</td><td>551.04</td><td>89.76</td><td>640.80</td><td>0.00</td><td>300</td><td>104</td><td>1044.80</td><td>199.77</td></tr><tr><td>0.6</td><td>556.31</td><td>52.32</td><td>608.63</td><td>0.00</td><td>300</td><td>124</td><td>1032.63</td><td>223.90</td></tr><tr><td>0.7</td><td>559.45</td><td>35.29</td><td>594.74</td><td>0.00</td><td>300</td><td>150</td><td>1044.74</td><td>222.50</td></tr><tr><td>0.8</td><td>570.43</td><td>0.61</td><td>571.04</td><td>0.00</td><td>300</td><td>162</td><td>1033.04</td><td>230.61</td></tr><tr><td>0.9</td><td>585.09</td><td>0</td><td>585.09</td><td>0.00</td><td>300</td><td>180</td><td>1065.09</td><td>243.60</td></tr><tr><td>1</td><td>599.46</td><td>0</td><td>599.46</td><td>0.00</td><td>300</td><td>184</td><td>1083.46</td><td>174.60</td></tr></table></body></html>

![](images/ed47be4aff3440c8fe975ba6025dc45ca3453deef2caee2f078c39c9a6d27b8c.jpg)

![](images/e31c0659d7a3e3507f515562e2417e6084fea24c893e47e2d50a5dacbd07a7cc.jpg)  
图830个客户时DPI变化时各类费用变化曲线 Fig.8The curves of varied costs changed with DPI when the number of customer is 30   
图950个客户时DPI变化时各类费用变化曲线 Fig.9The curves of varied costs changed with DPI when the number of customer is 50

# 3.2算例测试

由于研究中客户的需求是模糊的，所有客户和仓库的位置都是随机产生的，同时，带模糊需求的开放性选址路径问题模型的研究在国内外很少，所以无法将表2、3所示的HDMRO结果与之前研究的工作进行对比。因此，为了评价HDMRO的效率，本文选择将式(10)和(11)松弛，使其模糊需求的限制条件变为确定性需求，与松弛后的下界进行比较，同时，式(12)的不等式限制要变为等式限制，松弛后的公式如(30)和(31)所示。

$$
\sum _ { i \in V } \sum _ { j \in J } d _ { j } X _ { i j k } \leq Q _ { k } \quad \forall k \in K
$$

$$
\sum _ { j \in J } d _ { j } Y _ { i j } \leq P _ { i } Z _ { i } \quad \forall i \in I
$$

显然，当模糊需求的左边界为客户的确定性需求时，客户的总需求相较于需求模糊时会下降，同时，仓库和车辆的利用率也会降低。因此，可以得到确定性需求下的总成本是相对应的模糊需求下总成本的一个下界的结论。表4中，第一列为算例规模，接下来三列为解的质量对比，最后三列为运行时间对比，其中， $G a p =$ _HDMRO的解-CPLEX求解下界 $\times 1 0 0 \%$ 0CPLEX求解下界  
如表4所示，CPLEX求解的两个测试实例的下界分别是503.08和677.31，第一个算例所用时间为4011.34秒，第二个算例在3小时限制内未得到最优答案。而HDMRO求解两个算例的时间分别为128.25秒和223.90秒，因此，与CPLEX这种使用精确算法的求解器相比，该算法在计算时间上具有更高的效率，可以在较短的计算机运行时间内求得满意的解。

Tab.4The results of tested instances   

<html><body><table><tr><td>算例规模</td><td colspan="2">解的质量</td><td colspan="5">运行时间/s</td></tr><tr><td></td><td>HDMRO(DPI=0.6 和 API=1)</td><td>CPLEX求解下界</td><td>Gap(%)</td><td>HDMRO</td><td>CPLEX 12.8</td><td></td><td>Gap(%)</td></tr><tr><td>30-5</td><td>911.19</td><td>503.08</td><td>81.12%</td><td>128.25</td><td></td><td>4011.34</td><td>3027.75</td></tr><tr><td>50-5</td><td>1032.63</td><td>677.31</td><td>52.46%</td><td>223.90</td><td></td><td>10800</td><td>4723.58</td></tr></table></body></html>

除此之外，为了进一步验证HDMRO和OLRP-FD 模型的有效性，本文选取了标准 CLRP 算例库(http:/prodhonc.free.fr/Instances/instancesus.htm)中的7组标准算例进行相应改造来进行实验。改造步骤如下：

a）标准算例的默认需求为模糊需求的左界 $( d _ { I } )$ ，右界 $( d _ { 3 } )$ 为左界的3倍，而 $d _ { 2 }$ 为 $[ 1 . 5 ~ d _ { I } , 2 . 5 { d _ { I } } ]$ 中随机生成一个整数。

b）比较车辆容量 $\varrho$ 与所有客户中最大的 $d _ { 3 }$ ，若 $\varrho$ 大于$d _ { 3 }$ ，则默认车辆容量不变，否则，将最大的 $d _ { 3 }$ 设置为车辆容量。仓库容量 $P$ 设置为默认值的三倍。其余参数使用数据库默认参数，不做改变。

表5中给出了7组改造后的OLRP实例在CPLEX优化软件下3小时内求解出的下界，相对于本文使用HDMRO求解带模糊需求的OLRP 结果来说，HDMRO在求解此类复杂问题上有着较好的效果，除此之外，Gap值在7组算例中至少大于 $1 9 . 4 8 \%$ ，这说明了总成本会因为不确定的决策情况会导致巨大的差异，所以，当决策者所拥有的用于决策的信息不足时，利用科学的手段进行合理的预测和谨慎的决策能在一定程度上避免企业损失(此组算例中客户的机会损失成本为所对应客户实际需求的20倍)。

为了更进一步验证HDMRO 的求解效率，本文选择了CLRP标准数据库中的16组算例进行比较，使用HDMRO运行每组算例10次后取其中最优值的比较结果如表6所示。

表4测试算例结果  
表5HDMRO在7组标准OLRP实例上的计算结果  

<html><body><table><tr><td rowspan="2">算例</td><td rowspan="2">OLRP</td><td colspan="5">HDMRO 的解 (DPI= 0.6 and API= 1)</td><td rowspan="2">Gap(%)</td></tr><tr><td>计划行驶距离</td><td>额外行驶距离</td><td>仓库开放费用</td><td>车辆费用</td><td>总费用</td></tr><tr><td>20-5-1a</td><td>43958</td><td>20700</td><td>6626</td><td>25549</td><td>12000</td><td>64875</td><td>47.58</td></tr><tr><td>20-5-1b</td><td>34497</td><td>17900</td><td>5403</td><td>15497</td><td>5000</td><td>43800</td><td>26.97</td></tr><tr><td>20-5-2a</td><td>41125</td><td>19100</td><td>6431.5</td><td>22769</td><td>12000</td><td>60300.5</td><td>46.63</td></tr><tr><td>20-5-2b</td><td>32520</td><td>19100</td><td>563</td><td>13911</td><td>6000</td><td>39574</td><td>21.69</td></tr><tr><td>50-5-1a</td><td>78562</td><td>61400</td><td>10825</td><td>15385</td><td>24000</td><td>128772</td><td>63.91</td></tr><tr><td>50-5-1b</td><td>63099</td><td>42000</td><td>11680</td><td>15385</td><td>12000</td><td>85454</td><td>35.43</td></tr><tr><td>50-5-2a</td><td>73242</td><td>51600</td><td>6324</td><td>29319</td><td>29000</td><td>133065</td><td>81.67</td></tr></table></body></html>

表6HDMRO与其他三种算法比较结果

Tab.5The computational results of HDMRO in7 standard instances   
Tab.6The comparative results of HDMRO and other three algorithms   

<html><body><table><tr><td></td><td>GRASP</td><td>运行时间/s</td><td>MAPM</td><td>运行时间/s</td><td>LRGTS</td><td>运行时间/s</td><td>2-phase HGTS</td><td>运行时间/s</td><td>HDMRO</td><td>运行时间/s</td></tr><tr><td>Gaskell67-21x5</td><td>429.6</td><td>0.2</td><td>424.9</td><td>0.3</td><td>424.9</td><td>0.2</td><td>424.9</td><td>6</td><td>424.9</td><td>13.7</td></tr><tr><td>Gaskell67-22x5</td><td>585.1</td><td>0.2</td><td>611.8</td><td>0.3</td><td>587.4</td><td>0.2</td><td>585.1</td><td>9</td><td>585.1</td><td>20.5</td></tr><tr><td>Gaskell67-29x5</td><td>515.1</td><td>0.4</td><td>512.1</td><td>0.8</td><td>512.1</td><td>0.4</td><td>512.1</td><td>11</td><td>512.1</td><td>22.3</td></tr><tr><td>Gaskell67-32x5</td><td>571.9</td><td>0.6</td><td>571.9</td><td>0.8</td><td>584.6</td><td>0.6</td><td>562.2</td><td>40</td><td>568.5</td><td>19.8</td></tr><tr><td>Gaskell67-32x5</td><td>504.3</td><td>0.5</td><td>534.7</td><td>1.0</td><td>504.8</td><td>0.5</td><td>504.3</td><td>22</td><td>504.3</td><td>20.5</td></tr><tr><td>Gaskell67-36x5</td><td>460.4</td><td>0.8</td><td>485.4</td><td>1.4</td><td>476.5</td><td>0.7</td><td>460.4</td><td>39</td><td>479.5</td><td>18.3</td></tr><tr><td>Min92-27x5</td><td>3062.0</td><td>0.4</td><td>3062.0</td><td>1.0</td><td>3065.2</td><td>0.3</td><td>3062.0</td><td>11</td><td>3082.0</td><td>20.2</td></tr><tr><td>Christofides69-50x5</td><td>599.1</td><td>2.3</td><td>565.6</td><td>3.8</td><td>586.4</td><td>2.4</td><td>580.4</td><td>45</td><td>565.6</td><td>30.8</td></tr><tr><td>20-5-1a</td><td>55021</td><td>0.2</td><td>54793</td><td>0.3</td><td>55131</td><td>0.4</td><td>54793</td><td>3</td><td>54793</td><td>15.7</td></tr><tr><td>20-5-1b</td><td>39104</td><td>0.2</td><td>39104</td><td>0.3</td><td>39104</td><td>0.2</td><td>39104</td><td>4</td><td>39104</td><td>12.8</td></tr><tr><td>20-5-2a</td><td>48908</td><td>0.1</td><td>48908</td><td>0.4</td><td>48908</td><td>0.5</td><td>48945</td><td>3</td><td>48908</td><td>13.2</td></tr><tr><td>20-5-2b</td><td>37542</td><td>0.2</td><td>37542</td><td>0.3</td><td>37542</td><td>0.1</td><td>37542</td><td>4</td><td>37542</td><td>12.9</td></tr><tr><td>50-5-1</td><td>90632</td><td>1.8</td><td>90160</td><td>2.6</td><td>90160</td><td>0.3</td><td>90402</td><td>27</td><td>90160</td><td>30.7</td></tr><tr><td>50-5-1b</td><td>64761</td><td>1.8</td><td>63242</td><td>3.2</td><td>63256</td><td>1.0</td><td>64073</td><td>27</td><td>66468</td><td>35.2</td></tr><tr><td>50-5-2</td><td>88786</td><td>2.4</td><td>88298</td><td>3.4</td><td>88715</td><td>1.8</td><td>89342</td><td>23</td><td>89809</td><td>31.2</td></tr><tr><td>50-5-2b</td><td>68042</td><td>2.5</td><td>67893</td><td>2.9</td><td>67698</td><td>2.0</td><td>68479</td><td>21</td><td>67340</td><td>36.7</td></tr><tr><td>取得最优值次数</td><td>7</td><td></td><td>10</td><td></td><td>6</td><td></td><td>10</td><td></td><td>11</td><td></td></tr></table></body></html>

表6的16 组测试算例中，GRASP[25](贪心随机自适应搜索算法)能够求得7组最优解，MAPM[26](基于人群管理的文化基因算法)能够求得10 组最优解,LRGTS[27](基于拉格朗日松弛的禁忌搜索算法)能够求得6组最优解，2-phaseHGTS[28](两阶段启发式散点禁忌搜索)能够求得10 组最优解，而 HDMRO能够求得11组最优解，相比于另外四种算法，HDMRO 能够求解出更多的最优解，在求解质量上具有更大的优势。此外，在求解时间这一方面，由于计算机硬件与编译软件的不同(文章中所引用的前三种算法都是由 $\scriptstyle { \mathrm { C } } + +$ 进行编码，在DellPCOptiplexGX260 装载2.4GHzPentium4的CPU和512MBRAM以及WindowsXP系统下进行测试，2-phaseHGTS算法是Linux11.04下2GBRAM以及 intel coreDuo(2.0GHz)的配置下用 $\mathrm { C } { + } { + }$ 编写的)，无法进行直观的比较，但可以肯定的是，HDMRO 能够在可接受的时间内求解出质量令人满意的解，所以，根据以上数据可以得到HDMRO算法在此类问题的求解具有良好的效果。

# 3.3OLRP与 CLRP对比

此部分选择改造后的7组算例进行比较，分析开放式选

址路径问题与普通选址路径问题以及两者在需求模糊时的区别，判断企业是否选择配送服务外包。此部分所有算例使用HDMRO进行求解。相关参数：需求模糊时 $D P I = 0 . 6 \$ ， $A P I$ $= 1$ ，车辆启用费用为1000，单位距离费用为100，其余参数设置与3.2中的数据相同。求解结果如表7所示。$G a p 1 { = } \frac { \mathrm { C L R P - O L R P } } { \mathrm { O L R P } } { \times } 1 0 0 \%$ ，在需求是确定的情形下，OLRP与CLRP之间的Gap1至少为 $1 5 . 4 4 \%$ ，这说明在不考虑最后一段运输距离，假设企业的任何其他与此物流运输相关的费用和第三方物流公司的费用一致的情形下，决策者需要考虑的是承包给第三方物流公司的服务费用与此段距离所节省费用的差值的大小，由此来决定是否将物流配送服务外包。而在需求是不确定的情形下时，OLRP-FD与CLRP-FD之间的（ $\mathrm { \Delta } \mathrm { \ i } a p 2 \mathrm { ( \it \ G a p 2 = \frac { C L R P \mathrm { - } F D \mathrm { - } O L R P \mathrm { - } F D } { O L R P \mathrm { - } F D } \times 1 0 0 \% }$ )至少为 $1 9 . 6 6 \%$ ，这说明在需求是不确定的时候，CLRP-FD的总费用会比OLRP-FD更大，那么说明考虑模糊需求时，虽然车辆额外行驶距离与机会损失成本会让总费用增加，但OLRP-FD相对于CLRP-FD 增加的更少，因此，企业就有更多费用空间去考虑物流服务是否承包给第三方物流服务企业。其次，当客户规模为20时，Gap2值大于Gap1值的原因，主要是因为此组算例中客户较少，车辆服务所分配的客户时并未达到最大行驶距离限制，能够顺利的服务完所有客户，仓库无须启用更多车辆，从而没有产生机会损失成本，同时，在考虑额外行驶距离的情况下，CLRP-FD的产生的额外距离高于OLRP-FD产生的额外距离，所以Gap2值会大于Gap1值。而在客户规模为50时，Gap2值小于Gap1值，是由于最大距离限制以及HDMRO对路线规划的原因，仓库启用的车辆数有限，从而导致没有足够的车辆服务完归属于该仓库的客户，此时会产生较大的机会损失成本，虽然在总成本中占主要部分的还是计划行驶路线成本，但OLRP-FD的机会损失成本高于CLRP-FD的机会损失成本导致Gap 值有一定的减小，从而导致Gap2 值小于Gap1值。

表7OLRP与CLRP 结果对比  
Tab.7The comparative results of OLRP and CLRP   

<html><body><table><tr><td>算例</td><td>OLRP</td><td>CLRP</td><td>Gap1(%)</td><td>OLRP-FD</td><td>CLRP-FD</td><td>Gap2(%)</td></tr><tr><td>20-5-1a</td><td>43849</td><td>54793</td><td>24.96</td><td>64875</td><td>104242</td><td>60.68</td></tr><tr><td>20-5-1b</td><td>33564</td><td>39104</td><td>16.51</td><td>43800</td><td>52413</td><td>19.66</td></tr><tr><td>20-5-2a</td><td>41125</td><td>48908</td><td>18.93</td><td>60300.5</td><td>102347</td><td>69.73</td></tr><tr><td>20-5-2b</td><td>32520</td><td>37542</td><td>15.44</td><td>39574</td><td>52605</td><td>32.93</td></tr><tr><td>50-5-1a</td><td>63985</td><td>90160</td><td>40.91</td><td>128772</td><td>176215</td><td>36.84</td></tr><tr><td>50-5-1b</td><td>51485</td><td>66468</td><td>29.10</td><td>85454</td><td>106676</td><td>24.83</td></tr><tr><td>50-5-2a</td><td>67519</td><td>89809</td><td>33.01</td><td>133066</td><td>176310</td><td>32.50</td></tr></table></body></html>

# 4 结束语

本文对带模糊需求的开放式选址路径问题建立以仓库开放、使用车辆、车辆行驶距离、未服务的客户机会损失、额外行驶距离等成本之和最小为目标建立数学模型。同时，提出了求解离散问题的混合蘑菇繁殖算法，使用部分映射交叉和路径重连算法组合代替算法优秀父代蘑菇细化搜索空间与删除种群的操作，合理的避免信息在离散和连续空间转换时的丢失，并且能够更好的探索解的空间，提高算法的迭代效率。除此之外，邻域搜索时使用概率法对多种邻域选择，加强局部搜索能力。最后，通过对DPI的灵敏度分析，HDMRO与CPLEX求解改造算例结果之间的比较，以及OLRP与CLRP、OLRP-FD与CLRP-FD求解结果之间的对比分析，分析了企业选择第三方物流企业服务的可能性，验证了算法及模型的有效性。

# 参考文献：

[1]Clerc M,Kennedy J.The particle swarm-explosion，stability,and convergence inamultidimensional complex space[J].IEEE transactions on Evolutionary Computation,2002,6(1): 58-73.   
[2]张晓楠，范厚明，李剑锋．变动补偿的多模糊选址-路径机会约束模 型及算法[J]．系统工程理论与实践,2016,36(02):442-453.(Zhang Xiaonan,Fan Houming,Li Jianfeng.Chance-constrained model and algorithm forLRP with multiple fuzzy variablesunderchange-reward [J]. System Engineering-Theory& Practice,2016,36 (02):442-453.)   
[3]刘长石，彭怡，寇纲．震后应急物资配送的模糊定位-路径问题研究 [J]．中国管理科学,2016,24 (05):111-118.(Liu Changshi,Peng Yi, Kou Gang.Study of location-routing problem of emergency goods distribution in post-earthquake [J].Chinese Journal of Management Science,2016,24 (05): 111-118.)   
[4]郑斌，马祖军，方涛．应急物流系统中的模糊多目标定位-路径问题 [J]．系统工程,2009,27(08):21-25.(Zheng Bin,Ma Zujun,Fang Tao. Fuzzy multi-objective location-routing problem of emergency logistics system [J]. System Engineering,2009,27 (08): 21-25.)   
[5]Vincent F Y,Lin S Y.A simulated annealing heuristic for the open location-routing problem [J].Computers & Operations Research,2015, 62:184-196.   
[6]Pichka K,Bajgiran AH,Petering MEH,et al.The two echelon open location routing problem: Mathematical model and hybrid heuristic [J]. Computers & Industrial Engineering,2018,121: 97-112.   
[7]Ghaffari-Nasab N,Ahari S G,Ghazanfari M.A hybrid simulated annealing based heuristic for solving the location-routing problem with fuzzy demands [J]. Scientia Iranica,2013,20 (3): 919-930.   
[8]Fazayeli S,Eydi A,Kamalabadi I N.Location-routing problem in multimodal transportation network with time windows and fuzzy demands:Presenting a two-part genetic algorithm [J]. Computers & Industrial Engineering,2018,119:233-246.   
[9]B.Liu.Uncertainty Theory:An Introduction to its Axiomatic Foundations [M]. Springer,Berlin,2004.   
[10] Mehrjerdi Y Z,Nadizadeh A.Using greedy clustering method to solve capacitated location-routing problem with fuzzy demands [J].European Journal of Operational Research,2013,229 (1): 75-84.   
[11] Nadizadeh A,Nasab H H. Solving the dynamic capacitated locationrouting problem with fuzzy demands by hybrid heuristic algorithm [J]. European Journal of Operational Research,2014,238 (2): 458-470.   
[12] Zarandi MHF,Hemmati A,Davari S,et al. Capacitated location-routing problem with time windows under uncertainty [J]. Knowledge-Based Systems,2013,37:480-489.   
[13] Zhang H,Zhang Q,Ma L,et al.A hybrid ant colony optimization algorithm for a multi-objective vehicle routing problem with flexible time windows [J].Information Sciences,2019,490:166-190.   
[14] Bidar M,Kanan H R,Mouhoub M,et al.Mushroom Reproduction Optimization (MRO):a novel nature-inspired evolutionary algorithm [C]//2018 IEEE Congress on Evolutionary Computation (CEC).IEEE, 2018:1-10.   
[15]Wang H,Du L,Ma S.Multi-objective open location-routing model with split delivery for optimized relief distribution in post-earthquake [J]. Transportation Research Part E:Logistics and Transportation Review, 2014,69:160-179.   
[16]代颖，马祖军，朱道立．震后应急物资配送的模糊动态定位一路径 问题[J]．管理科学学报,2012(07):64-74.(Dai Ying,Ma Zujun,Zhu Daoli.Fuzzy dynamic location-routing problem of emergency goods distribution in post-earthquake [J]. Journal of Management Sciences in China,2012 (07): 64-74.)   
[17]马祖军，代颖，李双琳．带限制期的震后应急物资配送模糊多目标 开式定位-路径问题[J].系统管理学报，2014,23(5):658-667.(Ma Zujun,Dai Ying,Li Shuanglin.Fuzzy multi-objective open locationrouting problem with deadlines in post-earthquake relief deliveries [J]. Journal of Systems &Management,2014,23 (5): 658-667)   
[18]王海军，杜丽敬，马士华．震后应急物流系统中双目标开放式选址： 路径问题模型与算法研究[J].管理工程学报,2016,30(02):108-115. (Wang Haijun,Du Lijing,Ma Shihua.Dual-objective open location routing problem in the post-earthquake emergency logistics system: model and algorithm study [J].Journal of Industrial Engineering and Engineering Management,2016,30 (02):108-115.)   
[19]YuX,Zhou Y,Liu XF.A novel hybrid geneticalgorithm for the location routing problem with tight capacity constraints [J].Applied Soft Computing,2019,85:105760.   
[20]MAURICIOGCRR,CELSOC.OPTIMIZATIONBYGRASP:Greedy Randomized Adaptive Search Procedures [M].SPRINGER,2018.   
[21] Zadeh LA.Fuzzy sets as a basis for a theory of possibility [J].Fuzzy sets and systems,1978,1(1): 3-28.   
[22] ZadehLA.The concept of a linguistic variable and its application to approximate reasoning—I[J].Information sciences,1975,8(3):199-249.   
[23] A．Kaufmann.Introduction to the Theory of Fuzzy Subsets [M]. Academic Press,New York,1975.   
[24]Puljic K,Manger R.Comparison of eight evolutionary crossover operatorsfor thevehicle routingproblem[J].Mathematical Communications,2013,18 (2):359-375.   
[25] Christian Prins,Caroline Prodhon,Roberto Wolfler Calvo.Solving the capacitated location-routing problem by a GRASP complemented by a learning process and a path relinking [J].4orA Quarterly Journal of Operations Research,4(3):221-238.   
[26]Prins C,ProdhonC,Calvo RW.AMemetic AlgorithmwithPopulation Management (MA|PM) for the Capacitated Location-Routing Problem [J]. 2006.   
[27] Prins C,Prodhon C,Ruiz A,et al. Solving the Capacitated LocationRouting Problem by a Cooperative Lagrangean Relaxation-Granular Tabu Search Heuristic [J]. Transportation Science,2007,41(4):p.470- 483.   
[28] John Willmer Escobar,Rodrigo Linfati,Paolo Toth.A two-phase hybrid heuristic algorithm for the capacitated location-routing problem [J]. Computers & operations research,2013,40(1):70-79.