# 基于增量最短路径优先算法的高效LFA实现方法

耿海军1，郭小英1，尹霞²

(1．山西大学 软件学院，太原 030006;2.清华大学 计算机科学与技术，北京 100084)

摘要：针对已有LFA实现方式计算开销大和部署难度高的问题，提出了一种基于增量最短路径优先算法的LFA实现方法(LFA implementation method based on incremental shortest path first algorithm，ERPISPF)。首先将快速实现LFA的问题转换为如何在以计算节点为根的最短路径树上高效的计算其所有邻居节点到网络其余所有节点的最小代价问题，然后提出了计算该代价的定理并且证明了它的正确性，最后从理论上分析了算法的时间复杂度。仿真结果表明，ERPISPF不仅计算开销小，并且与LFC的故障保护率是相同的。

关键词：增量最短路径优先；LFA规则；网络故障 中图分类号：TP301.6 doi: 10.19734/j.issn.1001-3695.2018.09.0646

Efficient LFA implementation method based on incremental shortest path first algorithm

Geng Haijun1, Guo Xiaoying1, Yin Xia² (1.SchoolofSoftwareEngineeing,Shanxi UniversityTaiyuanO3o06,China;2.Dept.ofComputerScience&Technology, Tsinghua University,Beijing 10oo84,China)

Abstract: An eficientLFAimplementationmethod whichis basedonIncrementalShortestPath FirstAlgorithm(ERPISPF) was proposed toreducethecomputationaloverhead anddeployment dificultyoftheexisting LFA algorithm.The paper first turns the problemof quick implementationofLFA intohow toeficientlycalculate the minimumcostofallits neighbors to all other nodes ofthe networkon theshortestpath treerootedat thecompute node.Thenatheorem forcalculating the cost is presentedand itscorrectness is proved.Finally，the time complexityof thealgorithm wastheoretically analyzed. Experiments showthatcompared withLFAalgorithm,ERPISPF notonlyhas lesscomputationoverhead,butalsoprovides the same failure protection rate as LFA.

Key words:i-SPF;loop free alternates;network failures

随着互联网的飞速发展，新的应用程序对互联网提出了更加苛刻的要求。如何保证数据的无间断传输成为科研工作们研究的重要课题[1\~3]。从互联网诞生之日开始，学术界和工业界就开始研究如何提高域内路由协议对故障的恢复能力[4-6]。目前，被公认的方法可以分为两种类型，分别是被动恢复方法和主动保护方法。被动恢复方法也称为事后恢复方案，即当网络中出现故障后，路由协议重新收敛，重新计算路由表。针对该方案的研究主要包括，利用增量最短路径优先算法降低计算最短路径树的时间[7.8]；通过调整协议的默认参数来加速故障的检测速度[9]；限制故障的洪泛范围[10]；在数据包的包头中携带故障信息[1I]；修改网络中链路的权值避免路由环路[12]；规定报文更新次序[13]等。然而上述方案容易导致路由不稳定，出现路由震荡等问题。主动保护方法也称为事先预防方案[14]，即提前计算出所有节点对之间的备份路径。当网络出现故障时，利用事先计算出的备份路径转发受故障影响的报文，从而尽可能降低网络的中断时间。在过去的几十年里，大部分的研究主要集中在主动保护方法方面，因此本文也将重点研究这种类型的方案。在主动保护方法中，有一部分研究是基于标签技术的，例如Not-Via[15]、隧道[16]、MPLS[7]和SegmentRouting[18]等。然而这部分研究对网络协议的改动较大，因此不是本文研究的重点。

LFA[19是一种具有较强竞争力的路由保护方案,本文研究如何高效的实现LFA，降低互联网服务提供商部署LFA的开销。

# 0 相关工作

文献[20]中提出首先利用无环路条件计算节点对之间所有符合条件的下一跳，然后使用标签技术选择合适的下一跳转发报文。但是该方案的算法复杂度较高，需要修改报文的头部，所有该方案不适合在实际网络中使用。FIR[2I通过设置时间参数来抑制故障信息的发送，利用本地备份下一跳转发受影响的报文。如果在设定的时间内，网络中的故障依然没有恢复，则洪泛故障信息，重新进行路由收敛。FIR适用于临时故障的恢复，对于长时间故障的效果较差，可以保护网络中的链路故障，无法应对节点故障，并且抑制参数的选取是一个难题。文献[22]对传统FIR进行了调整，使其可以保护节点故障情形。文献[23]对FIR进行了进一步的研究，使其支持链路权值不对称的网络。MRC[24]采用多拓扑的思想配置路由，从而保护网络中的故障。

IETF提出利用LFA方法解决网络中的故障。然而计算节点需要计算多个最短段路径树来实现LFA，大大加剧了路由器的负担。为了降低实现LFA的算法开销，相关人员做了大量的工作，比较典型的研究包括TBFH[25]和DMPA[26]。

# 1 网络模型和问题描述

# 1.1网络模型

图 $G = ( V , E )$ 表示节点集合为 $V$ ，边集合为 $\boldsymbol { \mathbf { \mathit { E } } }$ 的网络拓扑结构。对于网络中任意节点 $\forall \nu \in V$ ，其对应的邻居集合可以表示为 $N ( \nu )$ ，以其为根的最短路径树可以表示为 $s p t ( \nu )$ 0

$D ( \nu , x )$ 为在 $s p t ( \nu )$ 中节点 $x$ 的所有子孙节点（包含节点$^ { \mathrm { ~ \tiny ~ { ~ x ~ } ~ } ) }$ 。对于 $\forall ( i , j ) \in E$ ， $w ( i , j )$ 是该链路代价；对于 $\forall x , y \in V ( x \neq y )$ ，$\_ c o s t ( x , y )$ 是节点 $x$ 到节点 $y$ 的最小代价。 $d n ( x , y )$ 是节点 $x$ 到节点 $y$ 的最优下一跳， $b n ( x , y )$ 是节点 $x$ 到节点 $y$ 的备份下一跳的集合。

图1表示以节点 $\mid c \mid$ 为根的最短路径树 $s p t ( c )$ 。节点 $\mid c \mid$ 的邻居节点可以表示为 $N ( c ) = \{ a , b \}$ 。在 $s p t ( c )$ 中，节点 $b$ 的所有子孙节点可以表示为 $D ( c , b ) = \{ e , f \}$ ，节点 $a$ 的所有子孙节点可以表示为 $D ( c , a ) = \{ h , d , g \}$ 。节点 $\mid c \mid$ 到节点 $g$ 的最短路径的代价为$\scriptstyle c o s t ( c , g ) = 3 + 2 + 1 = 6$ 。节点 $\mid c \mid$ 到节点 $g$ 的默认下一跳为 $d n ( c , g ) { = } a$ ，节点 $\mid c \mid$ 到节点 $f$ 的默认下一跳为 $d n ( c , f ) = b$ 。

![](images/e90e95266e81e9bbb6afe00fc707dd690a58825d81cf84b902b0d4d4cb618ef8.jpg)  
图1以节点 $\mid c \mid$ 为根的最短路径树 spt(c) Fig.1Shortest path tree rooted at node $c$

# 1.2问题描述

为了提升网络可用性，提高用户体验，IETF提出利用LFA规则应对网络中的故障。下面将分别介绍LFA中的三个规则：

a)LFC。对于任意目的地址 $\textit { d }$ ，节点 $\mid c \mid$ 可以将报文发送给其邻居节点 $x$ ，当且仅当满足 $c o s t ( x , d ) < c o s t ( x , c ) + c o s t ( c , d )$ 。

b)NPC。对于任意目的地址 $\textit { d }$ ，节点 $\mid c \mid$ 可以将报文发送给其邻居节点 $x$ ，当且仅当满足 $c o s t ( x , d ) < c o s t ( x , f ) + c o s t ( f , d )$ ，其中 $f { = } d n ( c , d )$ ，即 $f$ 代表节点 $\boldsymbol { \mathscr { c } }$ 到目的地址 $^ d$ 的最优下一跳。

c)DC。对于任意目的地址 $d$ ，节点 $\mid c \mid$ 可以将报文发送给其邻居节点 $x$ ，当且仅当满足 $c o s t ( x , d ) < c o s t ( c , d )$ □

为了在节点 $\mid c \mid$ 上实现LFC规则，节点 $\mid c \mid$ 需要知道$\quad c o s t ( c , d )$ ， $\_ c o s t ( x , c )$ 和 $\_ c o s t ( x , d )$ 的数值。为了在节点 $\mid c \mid$ 上实现NPC规则，节点 $\boldsymbol { \mathscr { c } }$ 需要知道 $\_ c o s t ( x , d )$ ， $\_ c o s t ( x , f )$ 和 $\_ c o s t ( f , d )$ 的数值。实现DC 规则，节点 $\mid c \mid$ 需要知道 $\boldsymbol { c o s t } ( \boldsymbol { c } , d )$ 和 $\_ c o s t ( x , d )$ 的数值。节点 $\mid c \mid$ 可以通过 $s p t ( c )$ 计算出 $\_ c o s t ( x , c )$ 、 $_ { c o s t ( c , d ) }$ 和$_ { c o s t ( f , d ) }$ 的值，但是无法获得 $\_ c o s t ( x , d )$ 和 $\_ c o s t ( x , f )$ 的数值。因此，本文需要解决的问题可以描述为：对于节点 $\mid c \mid$ ，如果给定 $s p t ( c )$ ，是否可以找到一个算法快速计算出其所有邻居对应的 $\_ c o s t ( x , d )$ 和 $\_ c o s t ( x , f )$ ， $\boldsymbol { x } \in N ( c )$ 的数值，其中 $d \in V , d \neq x , d \neq f$ 。定理1回答了如何解决上述的问题，并且给出了证明。

定理1已知计算节点 $\mid c \mid$ 和以其为根的最短路径树$s p t ( c )$ ，对于网络中的任意节点 $d ( d \neq c , d \neq x )$ ，其中 $\boldsymbol { x } \in N ( c )$ ，spt(c)表示将链路 $( c , x )$ 的代价调整为 $ _ { - c o s t ( c , x ) }$ 时对应的新的以节点 $\mid c \mid$ 为根最短路径树。

如果 $d \in D ( s p t ( c ) , x )$ 成立，则 $\scriptstyle { c o s t ( x , d ) = c o s t ( c , d ) - c o s t ( c , x ) }$ ;

如果 $d \not \in D ( s p t ( c ) , x )$ 和 $d \in D ( s p t ^ { \prime } ( c ) , x )$ 同时成立，则${ } c o s t ( x , d ) { = } c o s t ^ { \prime } ( c , d ) + c o s t ( c , x )$ ， $c o s t ^ { \prime } ( c , d )$ 表示在 spt(c)中节点 $\mid c \mid$ 和节点 $^ d$ 之间的代价；

如果 $d \not \in D ( s p t ( c ) , x )$ 和 $d \not \in D ( s p t ^ { \prime } ( c ) , x )$ 同时成立，则${ } c o s t ( x , d ) { = } c o s t ( x , c ) + c o s t ( c , d )$ 。

# 证明：

因为 $d \in D ( s p t ( c ) , x )$ ，所以 $c o s t ( c , d ) = c o s t ( c , x ) + c o s t ( x , d )$ ，即${ \mathit { c o s t } } ( x , d ) { = } { \mathit { c o s t } } ( c , d ) { - } { \mathit { c o s t } } ( c , x )$ 。

因为 $d \not \in D ( s p t ( c ) , x )$ 和 $d \in D ( s p t ^ { \prime } ( c ) , x )$ 同时成立，所以$c o s t ^ { \prime } ( c , d ) { = } c o s t ^ { \prime } ( c , x ) + c o s t ^ { \prime } ( x , d )$ ， 即cos $t ^ { \prime } ( x , d ) = c o s t ^ { \prime } ( c , d ) - c o s t ^ { \prime } ( c , x ) = c o s t ^ { \prime } ( c , d ) + c o s t ( c , x )$ 。 由于$d \in D ( s p t ^ { \prime } ( c ) , x )$ ，所以节点 $x$ 到节点 $^ d$ 的最短路径不经过节点$\boldsymbol { \mathscr { c } }$ ，因此 $c o s t ^ { \prime } ( x , d ) = c o s t ( x , d )$ ，即 $c o s t ( x , d ) = c o s t ^ { \prime } ( c , d ) + c o s t ( c , x )$ 0

因为 $d \not \in D ( s p t ( c ) , x )$ 和 $d \notin D ( s p t ^ { \prime } ( c ) , x )$ 同时成立，所以$c o s t ( x , d ) \ge c o s t ( x , c ) + c o s t ( c , d )$ （204 这是因为如果$c o s t ( x , d ) < c o s t ( x , c ) + c o s t ( c , d )$ 成立，则 $c o s t ( x , d ) – c o s t ( x , c ) < c o s t ( c , d )$ 。在 $ s p t ^ { \prime } ( c )$ 中，如果 $c o s t ( x , d ) – c o s t ( x , c ) < c o s t ( c , d )$ ，则 $\begin{array} { r } { d \in D ( s p t ^ { \prime } ( c ) , x ) } \end{array}$ ，与 $d \not \in D ( s p t ^ { \prime } ( c ) , x )$ 矛盾。因此 ${ } c o s t ( x , d ) { = } c o s t ( x , c ) + c o s t ( c , d )$ 。

# 2 算法

# 2.1算法描述

AlgorithmERPISPF

Input: $G = ( V , E )$ 和 $s p t ( c )$ ：  
output: $\forall \nu \in V \quad b n ( c , \nu )$ ·  
1: for $\boldsymbol { x } \in N ( c )$ do  
2: （204号 $w e i g h t \gets c o s t ( c , x )$   
3: $c o s t ( c , x ) \gets \ - c o s t ( c , x )$   
4: 利用i-SPF算法构造 $s p t ^ { \prime } ( c )$   
5: 根据定理1计算 $c o s t ( x , d ) , d \in V , d \neq c , d \neq x$ （204号  
6: $c o s t ( c , x ) \gets w e i g h t$   
7:endfor  
8: for $d \in V$ do  
9: for $\boldsymbol { x } \in N ( c )$ do  
10: if lfa条件成立then  
11: $b n ( c , d ) \gets b n ( c , d ) \cup \{ x \}$   
12: endif  
13: endfor  
14: endfor  
15：return $b n ( c , \nu ) , \forall \nu \in V$   
算法ERPISPF说明了节点 $\boldsymbol { \mathscr { c } }$ 如何实现LFA夫

算法需要以 $G = ( V , E )$ 和 $s p t ( c )$ 为输入条件，算法执行完毕的时候返回节点 $\mid c \mid$ 到所有节点的LFA下一跳。访问节点 $\mid c \mid$ 的邻居节点 $x$ ，调整二者之间链路的代价为 $\boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { \mathbf { \mathit { \Sigma } } } \boldsymbol { c o s t } ( \boldsymbol { \mathbf { \mathit { c } } } , \boldsymbol { x } )$ （算法第2-3行），利用增量最短路径优先算法计算节点 $\mid c \mid$ 为根的最短路径树spt(c）（算法第4行），接着根据定理1计算$c o s t ( x , d ) , d \in V , d \neq c , d \neq x$ （算法第5行），最后调整链路 $( c , x )$ 的代价为原来的数值（算法第6行）。利用LFA条件计算节点$\boldsymbol { c }$ 到网络中其余所有节点的备份下一跳集合（算法第 8-14行）。算法第10行中的LFA条件表示LFC、NPC或者DC，修改这里的条件就可以计算出满足不同规则的备份下一跳。

# 2.2算法性能分析

# 定理2ERPISPF的运行复杂度为 $O \| E | l g | V | )$ 。

证明假设节点 $\boldsymbol { \mathscr { c } }$ 运行ERPISPF算法，从上述的程序可以看出该节点需要执行 $k$ 次最短路径优先算法， $k$ 代表 $\mid c \mid$ 的度数。如果用 $M ( l )$ 代表执行算法时变化的节点的数量， $P ( l )$ 代表执行算法时变化的边的数量，因此，ERPISPF的运行复杂度为 $\sum _ { l = 1 } ^ { k } M ( l ) l g M ( l ) \leq l g \left| V \right| \ast \sum _ { l = 1 } ^ { k } M ( l ) = O ( \left| E \right| l g \left| V \right| ) .$ 0

定理3算法ERPISPF可以计算出所有满足LFA规则的下一跳集合。

证明假设节点 $\mid c \mid$ 运行该算法，从算法的第1行到第7行可知，当该部分程序执行完毕后，算法可以计算出节点 $\boldsymbol { \mathscr { c } }$ 的所有邻居节点到其他节点的最小代价。只要知道了节点 $\boldsymbol { c }$ 的所有邻居节点到其他节点的最小代价，就可以利用LFA规则计算节点 $\mid c \mid$ 到其他节点的备份下一跳。因此该定理成立。

# 3 实验及结果

由于实现LFA中三个规则的算法是类似的，因此本文仅说明实现LFC规则的算法，并且在实验中用ERPISPF表示。

# 3.1实验中数据集合

1）真实拓扑

a）Abilene[27]，该拓扑包括11个路由器和 28条数据链路。

b）表2列出了Rocketfuel[28]项目发布的真实拓扑。

表1Rocketfuel拓扑参数Table1Rocketfuel parameters  

<html><body><table><tr><td>AS号码</td><td>AS名称</td><td>结点数量</td><td>链路数量</td></tr><tr><td>1221</td><td>Telstra</td><td>108</td><td>153</td></tr><tr><td>1239</td><td>Sprint</td><td>315</td><td>972</td></tr><tr><td>1755</td><td>Ebone</td><td>87</td><td>162</td></tr><tr><td>3257</td><td>Tiscali</td><td>161</td><td>328</td></tr><tr><td>3967</td><td>Exodus</td><td>79</td><td>147</td></tr><tr><td>6461</td><td>Abovenet</td><td>128</td><td>372</td></tr></table></body></html>

2）模拟拓扑

本文利用Brite[29]软件模拟生成网络拓扑结构，该软件的参数在表2中列出。

表2Brite生成拓扑结构的参数设置  
Table 2 Brite parameters   

<html><body><table><tr><td>模型</td><td>节点数量</td><td>HS</td><td>LS</td></tr><tr><td>Waxman</td><td>400</td><td>1000</td><td>100</td></tr><tr><td>链路节点比</td><td>NodePlacement</td><td>增长方式</td><td>alpha</td></tr><tr><td>2-10</td><td>Random</td><td>增量式</td><td>0.15</td></tr><tr><td>beta</td><td>BWDist</td><td>BwMin-BwMax</td><td>模式</td></tr><tr><td>0.2</td><td>Constant</td><td>10.0-1024.0</td><td>路由器</td></tr></table></body></html>

# 3.2评价指标

本文的评价指标主要有计算开销和故障保护率。

1)计算开销

计算开销 $\mathbf { \bar { \rho } } = \mathbf { \rho }$ 算法的实际运行时间/迪杰斯特拉算法的实际运行时间。

# 2)故障保护率

故障保护率 $= { \frac { \displaystyle \sum _ { s , d \in V } k ( s , d ) } { \displaystyle | V \left| ^ { * } ( \left| V \right| - 1 ) \right. } }$ $k ( s , d ) = \left\{ { \begin{array} { l } { 1 , \ i f \ b n ( s , d ) \not = \Phi } \\ { 0 , \ e l s e } \end{array} } \right.$

# 3.3计算开销

图2描绘了ERPISPF、LFC、TBFH和DMPA四种算法在Abilene 和Rocketfuel拓扑中的计算开销结果。根据图2可知，在所有运行的拓扑结构中，ERPISPF都拥有最高的执行效率，其次是DMPA和TBFH，LFC的执行效率是最差的。这是因为ERPISPF，DMPA和TBFH的计算开销并不会随网络度的变化而变化。根据定理2可知，ERPISPF的计算开销小于计算一棵最短路径树的时间。DMPA的计算开销等于计算一棵最短路径树的时间，TBFH的计算开销接近计算两棵最短路径树的时间。

图3表示在模拟网络中，网络拓扑大小和计算开销之间的关系。从图3可知，四种算法的计算开销与网络拓扑都没有关系，ERPISPF的计算开销仍然的四种算法中最小的。这是因为当网络拓扑大小增加的时候，算法的实际运行时间和迪杰斯特拉算法的实际运行时间都会增加，并且二者增加的比例几乎接近，所以四种算法的计算开销与网络拓扑大小几乎没有关系。

![](images/5d4377643c79eeb8e4334a12cf41cb11e70ab3fca95c6aa0e81770cd1658d837.jpg)  
图2在Abilene 和Rocketfuel拓扑中不同算法的计算开销 Fig.2Computational overhead of different algorithms on Abilene and Rocketfuel topologies

![](images/4629c470fc086d80895b3455d25e8b43615ec58720b8291b0d8f20129ab81fea.jpg)  
图3计算开销和网络拓扑大小的关系

图4表示在模拟网络中，网络节点平均度和计算开销之间的关系。从图4可以看出，LFC的计算开销和节点平均度呈现线性关系，其余三种算法与节点平均度几乎没有关系。该原因和图2的原因是一样的。

![](images/f07e9f80036352c772283b2892b32fb0835f465b9010cb93ae7d166a75f59bd8.jpg)  
Fig.3Relationship between computational overhead and topology size   
图4计算开销和节点平均度的关系  
Fig.4Relationship between computational overhead and average node degree

# 3.4故障保护率

图5描绘了ERPISPF、LFC、TBFH和DMPA四种算法在Abilene和Rocketfuel拓扑中的故障保护率结果。根据图5可知，在所有运行的拓扑结构中，ERPISPF 和LFC 的故障保护率是最高的，其次是DMPA和TBFH。这是因为根据定理3可知，ERPISPF可以计算出所有符合LFC规则的下一跳。由于DMPA和TBFH实现方法的局限性，并不能完整的计算出所有符合规则的下一跳。

![](images/9c7e79e243b23f15de7386cfff09a76dbfff03bb2b0177a8a8abd1746b4b011e.jpg)  
图5在Abilene 和Rocketfuel拓扑中不同算法的故障保护率 Fig.5Failure protection rate of different algorithms on on Abilene and Rocketfuel topologies

图6表示在模拟网络中，网络拓扑大小和故障保护率之间的关系；图7表示在模拟网络中，网络节点平均度和故障保护率之间的关系。从两个图中可以看出，LFC和ERPISPF的故障保护率始终是相同的。根据图7可知，故障保护率和网络节点平均度呈现出接近线性的关系。这是因为网络节点平均度增加时，每个节点的邻居节点数量随之增加，符合LFC规则的下一跳数量也随之增加。

![](images/cf7463d96d143a7b3143c5ea7fe1556c0215664d0e88d0b27c7617c2ea2f99f6.jpg)  
图6故障保护率和网络拓扑大小的关系

![](images/f7e011c31ab4cc9a73c347a1808f720dddbe5140bff4a4e18c20a9c051788d09.jpg)  
Fig.6Relationship between failure protection rate and topology size   
图7故障保护率和节点平均度之间的关系 Fig.7Relationship between failure protection rate and average node degree

# 4 结束语

为了提高LFA算法的计算效率，本文提出了一种基于增量最短路径优先算法的高效LFA实现方法。本文充分利用了增量最短路径优先的特性，巧妙地在一棵最短路径树上求解出根节点的邻居到其余所有节点的最小代价，从而快速实现LFA。最后在Abilene、Rocketfuel和Brite生成拓扑中模拟了该算法，结果表明ERPISPF的计算开销小于计算一棵最短路径树的时间，并且可以计算出所有符合LFA规则的下一跳。

# 参考文献：

[1]Abishek Gopalan,Srinivasan Ramasubramanian.IP fast rerouting and disjoint multipath routing with three edge-independent spanning trees [J]. IEEE/ACM Trans on Networking,2016,24(3):1336-1349.   
[2] Antonakopoulos S,Bejerano Y, Koppol P.Full protection made easy: the dispath ip fast reroute scheme [J]. IEEE/ACM Trans on Networking, 2015,23(4): 1229-1242.   
[3]Xu An,Bi Jun,Zhang Baobao.Failure inference for shortening traffic detours [C]//Proc of International Symposium on Quality of Service. Piscataway,NJ: IEEE Press,2016:1-10.   
[4]Krist P. Scalable and efficient multipath routing:complexity and algorithms [C]/Proc of IEEE International Conference on Network Protocols,Piscataway,NJ: IEEE Press,2015: 376-385.   
[5]Yang Yuan,Xu Mingwei,Li Qi. Tunneling on demand: a lightweight approach for IP fast rerouting against multi-link failures [C]/Proc of International Symposium on Quality of Service. Piscataway,NJ: IEEE Press,2016: 1-10.   
[6]Elhourani T,Gopalan A,Ramasubramanian S.IP fast rerouting for multi-linkfailures[C]/ProcofConferenceonComputer Communications.Piscataway,NJ: IEEE Press,2014: 2148-2156.   
[7]Narvaez P, Siu K Y, Tzeng H Y. New dynamic algorithms for shortest path tree computation [J].IEEE/ACM Trans on Networking,2000,8(6): 734-746.   
[8]Narväez P, Siu KY, Tzeng HY.New dynamic SPT algorithm based on aball-and-string model [J]. IEEE/ACM Transon Networking, 2001,9(6): 706-718.   
[9]Francois P,Filsfils C,Evans J,et al.Achieving sub-second IGP convergence in large IP networks [J].Computer Communication Review,2005,35(3): 35-44.   
[10] Narvaez P. Routing reconfiguration in IP networks [D].Cambridge: Massachusetts Institute of Technology, 2000.   
[11] Lakshminarayanan K,Caesar M，Rangan M,et al.Achieving convergence-free routing using failure-carrying packets [C]//Proc of ACM Special Interest Group on Data Communication,New York:ACM Press,2007: 241-252.   
[12] Francois P，Bonaventure O．Avoiding transient loopsduring the convergence of link-state routing protocols [J]. IEEE/ACM Trans on Networking,2007,15(6): 1280-1292.   
[13] Clad F, Merindol P,Vissicchio S,et al. Graceful router updates for link-state protocols [C]//Proc of IEEE International Conference on Network Protocols,Piscataway, NJ: IEEE Press,2013:1-10.   
[14] Zhang Baobao，Wu Jianping，Bi Jun.RPFP:IP fast reroute with providing complete protection and without using tunnels [C]// Proc of International Symposium on Quality of Service. Piscataway,NJ: IEEE Press,2013: 1-10.   
[15] Enyedi $\mathbf { G }$ Retvari G, Szilagyi P,et al. IP Fast ReRoute: lightweight not-via without additional addresses [C]// Proc of Conference on Computer Communications,Piscataway,NJ:IEEE Press,2Oo9:157-168.   
[16] Xu Mingwei,Yang Yuan,Li Qi.Selecting shorter alternate paths for tunnel-based IP fast ReRoute in linear time [J].Computer Networks, 2012,56(2): 845-857.   
[17] Joel Sommers,Paul Barford,Brian Eriksson.On the prevalence and characteristics of MPLS deployments in the open Internet [Cl//Proc of ACM SIGCOMM Conference on Internet Measurement.New York: ACM Press,2011: 445-462.   
[18] Hao F,Kodialam M,Lakshman T V. Optimizing restoration with segment routing [C]// Proc of IEEE International Conference on Computer Communications.Piscataway,NJ: IEEE Press,2016:1-9.   
[19] Rétvari G, Tapolcai J,Enyedi G,et al.IP fast ReRoute:loop free alternates revisited [C]//Proc of IEEE International Conference on Computer Communications． Piscataway,NJ:IEEE Press， 2011: 2948-2956.   
[20] Yang Xiaowei,Wetherall D.Source selectable path diversity via routing deflections[C]//Proc of ACM Special Interest Groupon Data Communication,New York:ACM Press,2006:159-170.   
[21] Lee S,Yu Y,Nelakuditi S,et al. Proactive Vs reactive approaches to failure resilient routing [C]//Proc of IEEE International Conference on Computer Communications,Piscataway,NJ:IEEE Press,2Oo4:1-9.   
[22] Zhong Z,Nelakuditi S,Yu Y,et al.Failure inferencing based fast

rerouting for handling transient link and node failures [C]//Proc of IEEE Computer and Communications Societies.Piscataway,NJ:IEEE Press,2005:2859-2863. [23] Wang Junling，Srihari Nelakuditi.IP fast reroute with failure inferencing[C]//Proc of the SIGCOMM workshop on Internet network management.New York:ACM Press,2007:268-273. [24] Kvalbein A, Hansen AF, Cicic T,et al. Fast IP network recovery using multipleroutingconfigurations[C]//ProcofIEEEInternational Conference on Computer Communications Barcelona,Piscataway,NJ: IEEE Press,2006:1-11. [25] Markopoulou M P,Francois P,Bonaventure O,et al.An efficient algorithm to enable path diversity in link state routing networks [J]. Computer Networks,2011,55(5):1132-1149. [26] Geng Haijun，Shi Xingang，Wang Zhiliang，et al.A hop-by-hop dynamic distributed multipath routing mechanism for link state network [J].Computer Communications,2018,116: 225-239. [27]Advancednetworkingforresearchandeducation，[EB/OL]. [2017-10-28] https://www. internet2.edu/products-services/advancednetworking. [28] Spring N,Mahajan R,Wetherall D,et al.Measuring isp topologies with rocketfuel[J].IEEE/ACM Trans on Networking,20O4:2-16. [29] Brite,[EB/OL].[2017-10-20].http://www.cs.bu.edu/brite/.