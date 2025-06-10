# 基于静态和移动传感器的WSNs的 $k .$ -覆盖研究

贺春林1,2，赵海军1,²，陈毅红1,2

(1．西华师范大学计算机学院，四川 南充 637009;2.物联网感知与大数据分析南充市重点实验室，四川 南充637009)

摘要：针对无线传感器网络的k-覆盖问题进行了研究。首先定义一个表征网络覆盖效率的过度提供因子，并在此基础上对静态传感器网络和全移动传感器网络的k-覆盖问题进行分析，得到这两种情形下的过度提供因子以及全移动传感器网络中移动传感器的最大移动距离；进而提出一种由静态传感器和少量移动传感器构成的混合网络结构，并得到了这种网络结构下不依赖于网络大小的k-覆盖以及调度移动传感器移动的分布式移动调度算法，从而实现有效覆盖。仿真结果表明，提出的混合网络结构不仅能够实现精确的k-覆盖，而且相比于其他k-覆盖算法，有更高的覆盖率。

关键词：无线传感器网络；k-覆盖；移动性；网格点；分布式调度；覆盖率 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2020.02.0063

# Research on k-coverage based on static and mobile sensors in WSNs

He Chunlin1,², Zhao Haijun1,², Chen Yihong1, 2 (1.SchoolofComputer,China-WestNormal University,Nanchong6370o9,China;2.NanchongKeyLaboratoryofInteret ofThings Perception& Big Data Analysis,Nanchong 637009,China)

Abstract:This paper studied the k-coverage problem for wirelesssensor networks.Firstly,this work definedanoverproviding factor to indicate the coverage efficiency of the network,and on this basis,it analysed the $\mathbf { k }$ -coverage problems of staticsensor networksandall-mobilesensornetworks,and obtained theover-providing factors in thesetwocases and the maximum mobile distance of mobile sensors inall-mobile sensor networks.Furthermore,it proposed a hybrid network structure composed of static sensors and a small number of mobile sensors,and obtained $\mathbf { k }$ -coverage which was independent of network size in this network structure and adistributed mobile scheduling algorithm which scheduledthe movementof mobile ensors,soas toachieve efective coverage.The simulationresults show that theproposed hybrid network structure can not only achieve accurate k-coverage,but also has higher coverage than other $\mathbf { k }$ -coverage algorithms.

Key words: wireless sensor networks; k-coverage; mobility; grid points; distributed scheduling; coverage

# 0 引言

无线传感器网络(wireless sensornetworks，WSNs)由大量简单和低成本传感器构成。传感器以自组织方式执行诸如环境监测、目标跟踪或基础设施监控等任务[1,2]。WSNs中一个重要的研究内容就是覆盖问题；单个传感器的感知区域通常抽象为一个半径为 $\boldsymbol { r }$ 的圆盘，当区域中的每个点在至少 $k$ 个传感器的感知区域内时，就说该区域为 $k \mathrm { . }$ -覆盖(即被 $k$ 个传感器覆盖)[3.4]。

决定覆盖质量的一个关键是网络部署。由于网络大小和地形的复杂性等多种因素，实现网络最优确定性部署往往是不现实的，常见的做法是将传感器随机分散到感兴趣的区域。这样做尽管简化了网络部署，但却很难保证网络的有效覆盖。

由于移动传感器可以重新定位自身来恢复网络中的覆盖空洞，从而补偿传感器部署中的随机性，所以可提高网络覆盖效率。移动传感器常用于网络的覆盖提高[5]、负荷平衡[]和寿命延长[7]。但这些研究大都没考虑移动传感器所能移动的距离限制，且假设移动传感器可反复充电；还有一些研究试图最小化全部传感器的总移动距离或总移动次数。这也是不够的，因为移动传感器之间的能量是不能转移的。因此，最好就是通过在短距离内移动若干个传感器来限制每个移动传感器的最大移动距离，如级联运动[8]；文献[9]提出了一种基于翻转传感器的移动调度算法，以最大化网络覆盖；文献[10]把该问题进一步构建为一个最优化问题，使得不同区域中的传感器变动最小化。然而，文献[9]和[10]没有给出部分覆盖面积或最大移动距离；文献[11提出了一种多目标 $k$ 覆盖保持算法。通过网络模型建立传感器节点与目标节点之间的从属关系和不同节点之间的能量转换来提高网络生存周期和覆盖率；文献[12]提出了一种三维表面 $k \mathrm { . }$ -覆盖多连通部署方法。方法在目标区域自由选择网格大小进行划分，并在各网格之间建立多连通关系，再通过方向梯度概率感知模型在网格内构造 $k \mathrm { . }$ -覆盖集，然后利用最小生成树算法构造连通图来找出关键节点构造双连通图。仿真结果表明，该方法能够对目标区域进行完全覆盖和连通，并能保证网络的健壮性；文献[13]提出了一种无须坐标信息的 $k \mathrm { . }$ -覆盖空洞检测算法。首先提出1-覆盖空洞检测算法，然后扩展至 $k \mathrm { . }$ 覆盖空洞情形，通过在已被节点覆盖的目标区域内寻找独立覆盖的节点子集，并休眠该集合内的节点，使网络覆盖度减1。然后重复1-覆盖空洞检测算法，发现更高阶的覆盖空洞，迭代上述步骤k-1次，就可以发现所有 $k \mathrm { . }$ -覆盖空洞的边界线段和边界圆周。仿真结果表明，提出的算法与基于坐标的覆盖空洞检测算法相比，可以提高覆盖空洞的检测。

上述针对WSNs的覆盖或 $k \mathrm { . }$ -覆盖研究，大多是在静态传感器部署或不考虑移动传感器成本的条件下，这样一方面不能更好地利用有效的传感器资源，另一方面也不能满足实际WSNs监测中的动态需求。对此，本文研究了静态和动态传感器同时部署的WSNs更一般情形下的 $k \mathrm { . }$ 覆盖问题。

# 1 采用静态和移动传感器的 $\mathsf { k }$ 覆盖

# 1.1系统模型

考虑边长为 $\smash { l _ { s } }$ 面积为 $L { = } l { \times } l$ 的正方形感知区域(把它称为网络大小)。假设有 $N { = } \lambda L$ 个静态传感器均匀且独立分散在网络中。当 $N$ 较大时，面积为 $A$ 的区域中的静态传感器数量（以 $n _ { A }$ 表示)将是以λA为均值的泊松分布[14]：

$$
P ( n _ { A } = i ) = \frac { ( \lambda A ) ^ { i } \mathrm { e } ^ { - \lambda A } } { i ! }
$$

其中λ为静态传感器的密度。此外，不相交区域中的传感器数量是相互独立的，因此，当网络足够大时，就可以近似为一个平稳泊松点过程。在后面的推导中，直接采用泊松点过程的性质。

假设每个静态传感器可以覆盖一个半径为 $r { = } 1 / \sqrt { \pi }$ 的圆盘区域，即每个传感器可以覆盖一个单位面积的圆盘。当这个圆盘中的每个点都能被至少 $k$ 个传感器覆盖时，就说该区域为 $k \mathrm { . }$ -覆盖；为了网络在完全覆盖时能连接，假设传感器的通信范围大于 $2 r$ ；假设移动传感器是均匀且独立分布在网络中，总的移动传感器数量为 $M { = } _ { \mathit { 1 L } }$ ， $\varLambda$ 为移动传感器的密度，且移动传感器与静态传感器有相同的覆盖范围。由于能量和成本限制，假设每个移动传感器在有限距离上仅移动一次，以弥补网络中的覆盖空洞，且假设移动传感器有足够的能量供应，以至于在重定位后，可以保持至少与静态传感器相同的感知和通信时间；目标就是确保整个区域是 $k \mathrm { . }$ -覆盖的，其中 $k$ 由网络运营商在部署之前确定。

# 1.2 过度提供因子

定义一个新的指标，称为过度提供因子 $\scriptstyle \eta = ( \lambda + \lambda ) / k$ ，即传感器密度(静态传感器密度和移动传感器密度A之和)与网络覆盖要求之比。显然， $\eta$ 越小，提供 $k \mathrm { . }$ -覆盖的网络部署就越有效。

对于随机部署来说，监测区域中的许多小区域可能有超过 $k$ 个传感器覆盖它们，同时也存在少数区域由周围的 $k$ 个传感器覆盖它们。显然，对于大型网络来说，随机部署策略有较大的过度提供因子和较低的效率，而对于确定部署的网络来说， $\eta$ 的上限可以通过将传感器放置在规则网格上来得到。例如，将传感器放置在边长为 $d _ { \mathrm { s } } { = } \sqrt { 2 } r$ 的正方形网格上，可以对网络提供1-覆盖。如果要求 $k \mathrm { . }$ 覆盖，可以将 $k$ 个传感器放置在每个网格点上。可见，对于任何部署，过度提供因子都是以1作为下界，因为全部传感器感知区域的面积总和应当大于感知区域大小的 $k$ 倍。因此，对于确定部署的传感器网络来说，最佳过度提供因子为 $O ( 1 )$ 。

# 1.3采用静态传感器的网络 $\mathbf { k }$ 覆盖

现在来研究随机部署密度为?的静态传感器网络的过度提供因子。根据随机覆盖过程理论，不被覆盖的预期总面积为 $\mathrm { e } ^ { - \lambda } L ^ { [ 1 4 ] }$ 。

通过选取足够大的?，可以使得不被覆盖面积的百分比 $\mathrm { e ^ { - } }$ $\lambda ( \mathrm { e } ^ { - \lambda } L / L )$ 变成任意小。然而，当网络大小 $L {  } { \infty }$ 时，对于传感器密度恒定为λ的网络来说，存在大于单位面积的连接覆盖空洞的概率就接近于1。原因是：当网络中的一个点在与它的距离为 $2 r$ 的范围内没有传感器时，在围绕该点的半径$r = 1 / \sqrt { \pi }$ 的圆盘将不被覆盖，这就是一个面积至少为1的覆盖空洞。当网络不被增大的 $2 r$ 感知范围完全覆盖时，这种点总是存在的。根据随机覆盖过程定理，当概率接近1时，当网络大小达到无穷大时，网络不能完全被范围为 $2 r$ 的传感器的恒定密度所覆盖。因此，随着网络大小的增大，恒定传感器密度λ并不能保证网络中不存在大的空洞，即使网络的大部分区域被覆盖。

为了实现大型网络的 $k \mathrm { . }$ -覆盖，静态传感器密度需要随着网络大小的增大而增大，即 $\lambda { = } \log L { + } ( k { + } 2 ) \log \log ( L ) ^ { [ 4 ] }$ 。因此，随机部署静态传感器时网络的过度提供因子为

$$
\eta _ { \mathrm { s } } = \frac { \log L + ( k + 2 ) \log \log L } { k }
$$

对于固定的 $k$ 值来说， $\eta \mathrm { { s } }$ 为 $O ( \log L )$ 。这表明随机部署静态传感器时网络的覆盖效率随着网络大小的增大而变差。

# 1.4采用全移动传感器的网络 $\mathsf { \mathbf { k } }$ 覆盖

现在考虑全部传感器都移动且随机部署的网络覆盖，这些移动传感器能重新定位自身，以提供 $k$ -覆盖。然而，关键问题是每个传感器必须移动的最大距离是多少，才能将自己放置在最佳位置。

全移动网络的最大移动距离由定理1给出。

定理1考虑一个均匀独立分布在面积为 $L$ 的正方形区域上的全移动传感器网络，网络可以提供 $k \mathrm { . }$ -覆盖，有过度提供因子 $\scriptstyle \eta _ { \mathrm { m } } = \pi / 2$ ，任何移动传感器移动的最大距离为$O ( \frac { 1 } { \sqrt { k } } \log ^ { 3 / 4 } ( k L ) )$ 。

证明对于确定性部署，是将 $k$ 个传感器放在边长为$d _ { \mathrm { s } } = \sqrt { 2 } r$ 的相同网格点上，现在将感知区域划分为边长为$d _ { \mathrm { a } } = \sqrt { 2 } r / k$ 的正方形网格，如图1所示。可以看出，网格点的密度为 $k / 2 r ^ { 2 } { = } \eta _ { \mathrm { m } } k$ 。

首先证明，可以每个网格点上放一个移动传感器实现网络 $k \mathrm { . }$ -覆盖，然后对匀分布移动传感器的最大移动距离进行限制，来实现这种规则网格部署。

假设移动传感器已重新定位，使得每个网格点上恰好有一个移动传感器。首先考虑内部网络区域的覆盖，这些区域与区域边界的距离大于 $\boldsymbol { r }$ 。如果一个点在距离 $\boldsymbol { r }$ 到至少 $k$ 个网格点之内，则它就被 $k$ -覆盖。根据一个圆覆盖的网格点的下界[15]，至少存在由一个以任意点为圆心、 $r$ 为半径的圆所覆盖的边长为 $d _ { \mathrm { a } }$ 的 $W ( k )$ 个网格点，即：

$$
W ( k ) \geq \frac { \pi ( r - d _ { \mathrm { a } } / \sqrt { 2 } ) ^ { 2 } } { d _ { \mathrm { a } } ^ { 2 } } = k \times \frac { \pi } { 2 } ( 1 - \frac { 1 } { \sqrt { k } } ) ^ { 2 }
$$

当 $k { \geq } 1$ 时， $W ( k ) / k$ 是单调递增函数，且当 $k { \geq } 2 5$ 时， $W ( k ) { > } k _ { \odot }$ 容易验证，当 $1 { \le } k { < } 2 5$ 时，网络至少是 $k$ -覆盖的。因此可以看到，如果在每个网格点上有一个传感器，则网络内部就是完全 $k \mathrm { . }$ -覆盖的。为了覆盖边界附近的点，可以稍微将部署区域增大为一个 $( l { + } 2 r ) { \times } ( l { + } 2 r )$ 的正方形。这样只会使密度增加一小部分 $O ( r / l )$ ，当网络很大时，这是可以忽略的。

在移动传感器随机部署在网络中后，需要重新定位它们，以使每个网格点恰好有一个移动传感器。这在本质上是移动传感器和网格点之间的匹配问题。移动传感器的最大移动距离可以采用极小-极大网格匹配理论[16来得到：考虑由单位边长的正方形网格构成的 $l { \times } l$ 的正方形区域。如果将 $L { = } l ^ { 2 }$ 个点按均匀分布随机独立地分散在区域内，则在 $L$ 个随机点和 $L$ 个网格点之间就存在完全匹配，且任意匹配对之间的最大距离为 $O ( \log ^ { 3 / 4 } L ) ^ { [ 1 6 ] }$ 。而在本文讨论的网络中，网格点总数为$k L / 2 r ^ { 2 }$ 而不是 $L$ ，因此，最大移动距离为网格边长的$O ( \log ^ { 3 / 4 } ( k L ) )$ 倍。由于网格大小为 $d _ { \mathrm { a } } = \sqrt { 2 } r / \sqrt { k }$ 而不是1，因此最大移动距离为 $O ( \frac { 1 } { \sqrt { k } } \log ^ { 3 / 4 } ( k L ) )$ 。

在全移动传感器网络中，与静态方法相比，移动传感器可对大型网络中的随机性进行不同补偿。静态方法需要采用更高的密度(与 $O ( \log L )$ 成比例)来补偿网络大小，而在移动传感器网络中，传感器密度为 $\pi / 2$ 保持不变。

![](images/6ee65728cd5b9883742a7701279d93af295c0dbcf23c983393013e3c3d8a58bc.jpg)  
图1全移动网络中移动传感器与网格点的匹配 Fig.1Matching between mobile sensor and grid point in all-mobile sensor networks

# 2 混合网络的 $\mathsf { k } .$ 覆盖

1.4讨论的全移动网络可以通过传感器移动较小的距离来实现确定性传感器部署，但移动传感器比静态传感器昂贵得多。为了降低网络成本，最好用少量的移动传感器来提高网络性能。本节研究混合网络的覆盖，其中部署大量静态传感器和一小部分移动传感器，其过度提供因子为 $O ( 1 )$ ，且所需的部分移动传感器少于 $\scriptstyle { 1 / { \sqrt { 2 \pi k } } }$ 。还进一步表明，对于这种特定部署，任何移动传感器必须移动的最大距离为 $O ( \log ^ { 3 / 4 } L )$

# 2.1移动传感器的密度

将静态传感器密度固定为 $\scriptstyle \lambda = 2 \pi k$ ，将网络划分为等边长$d _ { \mathrm { h } } = r / \sqrt { 2 }$ 的正方形单元格。由于感知范围为 $r$ ，则单元格中的任何传感器都可以完全覆盖单元格。每个单元格中静态传感器的平均数量为 $2 \pi k d ^ { 2 } \mathrm { h } { = } k$ 。

如果全部单元格包含至少 $k$ 个传感器，则网络将是 $k \mathrm { . }$ 覆盖的。由于部署的随机性，有些单元格可能包含的静态传感器少于 $k$ 个。如果一个单元格 $i$ 包含 $n _ { i } { < } k$ 个静态传感器，就说单元格 $i$ 有 $\scriptstyle \nu _ { i } = k - n _ { i }$ 个空洞。根据Poisson近似， $n _ { i }$ 将为独立同分布：

$$
P ( n _ { i } = j ) = { \frac { k ^ { j } \mathrm { e } ^ { - k } } { j ! } }
$$

随机变量 $\scriptstyle { \nu _ { i } = [ k - n _ { i } ] ^ { + } }$ （其中 $[ x ] ^ { + }$ 的意思是 $\operatorname* { m a x } \left\{ x , 0 \right\}$ 的分布为

$$
P \{ \nu _ { i } = j \} = \left\{ \begin{array} { l l } { { \displaystyle \frac { k ^ { k - j } \mathrm { e } ^ { - k } } { ( k - j ) ! } } } & { { 1 \leq j \leq k } } \\ { { 1 - \sum _ { m = 0 } ^ { k - 1 } { \frac { k ^ { m } \mathrm { e } ^ { - k } } { m ! } } } } & { { j = 0 } } \\ { { 0 } } & { { \ddag \sharp \sharp } } \end{array} \right.
$$

一个单元格中的空洞数量期望值为

$$
\begin{array} { r l } & { \mathbb { E } \{ v _ { i } \} = \sum _ { j = 1 } ^ { k } j \frac { k ^ { k - j } - \epsilon ^ { k } } { ( k - j ) ! } } \\ & { \quad = \sum _ { i = 0 } ^ { k - 1 } ( k - l ) \frac { k ^ { k } ( e ^ { - k } } { l ! } } \\ & { \quad = \sum _ { i = 1 } ^ { k - 1 } \bigg [ \frac { k ^ { l + 1 } - \epsilon ^ { - k } } { l ! } - \frac { k ^ { l } ( e ^ { - k } } { ( l - 1 ) ! } \bigg ] + k e ^ { - k } } \\ & { \quad = \sum _ { i = 1 } ^ { k } \frac { k ^ { l } ( e ^ { - k } ) } { ( l - 1 ) ! } - \sum _ { t = 1 } ^ { k - 1 } \frac { k ^ { l } \epsilon ^ { - k } } { ( l - 1 ) ! } } \\ & { \quad = \frac { k ^ { k } e ^ { - k } } { ( k - 1 ) ! } - k P \{ n _ { i } = k \} } \end{array}
$$

由于 $\mathbf { \sigma } _ { \nu _ { i } }$ 为独立同分布随机变量，在后面的推导中略去$\mathbb { E } \{ \nu _ { i } \}$ 中的下标 $i ,$ 。根据大数定律[17]，当网络较大时，每个单元格的平均空洞数将收敛到 ${ \mathrm { E } } \{ \nu \}$ ，即当 $L {  } { \infty }$ 时，对于任意小的 $\varepsilon$ 值，每个单元格的平均空洞数将在 $\left[ ( 1 - \varepsilon ) \mathrm { E } \left\{ \nu \right\} , ( 1 + \varepsilon ) \mathrm { E } \left\{ \nu \right\} \right]$ 范围内。因此，对于大型网络来说，当移动传感器密度为$\varLambda = ( 1 + \varepsilon ) \mathrm { E } \{ \nu \} / ( r / \sqrt { 2 } ) ^ { 2 } = ( 1 + \varepsilon ) 2 \pi \mathrm { E } \{ \nu \}$ 时，移动传感器数量几乎大于或等于总的空洞数。由于 $\dot { \varepsilon }$ 可以设置得任意小，则移动传感器密度 $\scriptstyle \varLambda \approx 2 \pi \operatorname { E } \left\{ \nu \right\}$ 。

使用Stirling近似 $k \approx k ^ { k } \mathbf { e } ^ { - k } \sqrt { 2 \pi k }$ 有：

$$
E \{ \nu \} = k { \frac { k ^ { k } \mathrm { e } ^ { - k } } { k ! } } \approx { \frac { \sqrt { k } } { \sqrt { 2 \pi } } }
$$

由于Stirling近似的误差阶数为 $O ( \mathrm { e } ^ { 1 / 1 2 k } )$ ，因此，当 $k {  } \infty$ 时有 $\mathbb { E } \{ \nu \}  \sqrt { k } / \sqrt { 2 \pi }$ ，进而有 $\varLambda \approx \sqrt { 2 \pi k }$ 。当静态传感器密度为$2 \pi k$ 时，移动传感器与静态传感器的密度比为 $\varLambda / \lambda \approx 1 / \sqrt { 2 \pi k }$ 。随着 $k$ 增大，只需要一小部分移动传感器来填充空洞。这是由于即随着 $k$ 的增大，一个单元格中静态传感器的泊松分布数将更多地集中在 $k$ 的均值附近。

移动传感器和静态传感器密度之和仍然为 $O ( k )$ ，因为$\scriptstyle \lambda = 2 \pi k$ 和 $\varLambda { \approx } \sqrt { 2 \pi k }$ 。更准确地说，对于任意大的网络和任意整数值 $k$ ，过度提供因子 $\scriptstyle \eta _ { \mathrm { h } } = ( \lambda + \varLambda ) / k \leq 2 \pi ^ { + } { \sqrt { 2 \pi } }$ 。

# 2.2移动传感器的移动距离

在混合网络中，需要移动移动传感器来填充每个单元格中的空洞，即需要在移动传感器和空洞之间建立一对一的匹配。

匹配构建分为两步：a)将移动传感器匹配到边长为$1 / { \sqrt { A } }$ 的网格点上，最大匹配距离为 l0g²4(AL))。当A和 L大于1时，函数 $\frac { 1 } { \sqrt { A } } \log ^ { 3 / 4 } ( A L )$ 是A的递减函数，因此，匹配距离随4而减小。b)将空洞匹配到边长为 $1 / { \sqrt { A } }$ 的网格的网格点上。定理2给出了最大匹配距离。

定理2考虑一个面积为 $L$ 的正方形网络，其中 $\varLambda L$ 个空洞按照式(5)独立同分布在边长 $\scriptstyle { d _ { \mathrm { h } } = r / { \sqrt { 2 } } }$ 的单元格中，则存在一个匹配，它在空洞和边长为 $1 / { \sqrt { A } }$ 的单元格的网格点之间有最大匹配距离 $O ( \log ^ { 3 / 4 } L )$ 。

根据前面分析和定理1以及版面所限，这里略去定理2的证明。

这样就在移动传感器和空洞之间构建起了一对一的匹配，且匹配对之间的最大距离为 $O ( \log ^ { 3 / 4 } L )$ 。

表1比较了3种不同网络结构的传感器密度和移动距离。

表13种不同网络结构的 $k \mathrm { . }$ 覆盖传感器密度和移动距离

Tab.1 $K$ -covering sensor density and moving distance for   
three different network structures   

<html><body><table><tr><td>网络结构</td><td>静态传感器密度</td><td>移动传感器密度</td><td>最大移动距离</td></tr><tr><td>静态</td><td>O(kloglogL+logL)</td><td>0</td><td>0</td></tr><tr><td>全移动</td><td>0</td><td>0(k)</td><td>O(log³/4(kL)/√k)</td></tr><tr><td>混合结构</td><td>0(k)</td><td>0（√k）</td><td>O(log3/4(L)</td></tr></table></body></html>

# 2.3分布式移动调度算法

简单的贪婪移动调度如将移动传感器移动到最近的空洞，无法用短距离移动来填充全部空洞。由于匹配问题是一种特殊的网络流问题，所以可以用一种网络流结构以分布式方式来解决移动调度。

# 2.3.1移动调度问题构建

将移动调度问题构建为：假设对于每个单元格 $i ,$ 有 $n _ { i }$ 个静态传感器和 $m _ { i }$ 个移动传感器，单元格 $i$ 中的空洞数量为$\scriptstyle { \nu _ { i } = [ k - n _ { i } ] ^ { + } }$ 。移动移动传感器来填充空洞的网络流问题如图2所示。

构建一个图 $G ( V , E )$ ，每个单元格为一个顶点。当单元格$i$ 和 $j$ 之间的中心距离小于 $D { = } O ( \log ^ { 3 / 4 } L )$ （204号

(即移动传感器可以移动的最大距离)时，从单元格i到单元格 $j$ 加入一条有向边 $( i , j )$ 。因此，当两个单元格之间的距离小于 $D$ 时，移动传感器可以在两个单元格之间移动，把从单元格 $i$ 移动到单元格 $j$ 的移动传感器数量记为 $x _ { i j }$ ，则移动调度问题可构建为

目标： $\begin{array} { r l } { \mathrm { M i n i m i z e } \quad } & { { } \sum _ { i , j } c _ { i j } \times x _ { i j } } \end{array}$

满足：

$$
\begin{array} { r l } { \sum _ { j } \mathrm { ~ } x _ { j i } - \sum _ { j } \mathrm { ~ } x _ { i j } \ge \nu _ { i } - m _ { i } \quad } & { { } \forall i } \\ { \sum _ { j } \mathrm { ~ } x _ { i j } \le m _ { i } \quad } & { { } \forall i } \\ { \mathrm { ~ } x _ { i j } \ge 0 \quad } & { { } } \end{array}
$$

其中 $c _ { i j }$ 为移动成本。在这个最优化问题中，式(9)为流守恒条件，它要求单元格 $i$ 的净流入流(移入单元格 $i$ 的移动传感器数量减去移出单元格 $i$ 的移动传感器数量)大于它所要求的移动传感器数量(单元格 $i$ 中的空洞数量减去初始移动传感器数量)。这个约束条件确保移动后单元格 $i$ 中最终的移动传感器数量将大于空洞数量；式(10)表示移出单元格 $i$ 的移动传感器总数量不应大于单元格 $i$ 中的初始移动传感器数量。移动成本 $c _ { i j }$ 决定了需要最小化的指标，如果设置全部 $c _ { i j } { = } 1$ ，则最优解将给出有最小移动次数的移动调度。如果选取 $c _ { i j }$ 为单元格间的距离，则可得到最小化总移动距离的调度。

单元格1 单元格2 单元格3 O空洞○ 1 静态传感器移动传感器  
单元格4 单元格5单元格61  
单元格7 单元格8 单元格9

由于 $\nu _ { i }$ 和 $m _ { i }$ 为整数，故最优解 ${ { x } ^ { * } } _ { i j }$ 为整数。因此，最优解意味着只需将 ${ { x } ^ { * } } _ { i j }$ 个移动传感器从单元格 $i$ 移动到单元格 $j$ 来确保每个单元格总共至少有 $k$ 个传感器。

# 2.3.2分布式移动算法

本节提出一种分布式移动算法来实现移动传感器的移动调度。首先提出一种移动算法来解决更简单的问题，即一个可行移动调度来填充全部空洞而无须最小化总移动成本，然后提出一种推动-重标记算法来获得最小成本流。

假设每个移动传感器或静态传感器知道它的位置，并知道它定位于哪个单元格中。在部署后，同一单元格i中的移动传感器和静态传感器相互通信来计算 $\mathbf { \sigma } _ { \nu _ { i } }$ 和 $m _ { i }$ 。每个单元格挑选出一个移动传感器或静态传感器作为整个单元格的代理用于保存算法执行过程中单元格的必要信息。单元格 $i$ 的代理还需要与邻居进行通信并交换信息。如果有空的单元格即不包含移动传感器或静态传感器，则可以随机分配相邻单元格中的一个移动传感器作为它的代理。由于前面已经表明空单元格可以用最大移动距离 $D$ 填充，故在 $D$ 的距离内至少有一个移动传感器。如果一个空单元格导致网络断开，则在执行算法前，最近的移动传感器移动到该空单元格来连接网络；推动-重标记算法的基本思想是在不能执行推动时，迭代地将一个顶点的多余流推动到具有较低高度的相邻顶点或重新标记它本身。重复推动-重标记算法，直至全部单元格没有多余的流。移动算法和推动-重标记算法共同构成一个分布式移动算法，它们的伪代码分别如算法1和算法2所示。

算法1单元格 $i$ 的移动算法

1.收集 $\boldsymbol { v } _ { i }$ 和 $m _ { i }$ 的单元格信息

2.设置 $i _ { \mathrm { i n } }$ 和 $i _ { \mathrm { o u t } }$ 的高度 $h ( i _ { \mathrm { i n } } )$ 和 $h ( i _ { \mathrm { o u t } } )$ 为0

3.设置多余的 $\scriptstyle { i _ { \mathrm { i n } } }$ 表示为 $e ( i _ { \mathrm { i n } } )$ 为0，多余的 $\dot { \imath } _ { \tt o u t }$ 表示为 $e ( i _ { \mathrm { o u t } } )$ 为$m _ { i } - v _ { i }$

4.while 存在顶点

5. call push-relabel( $( i _ { \mathrm { i n } } )$

6． call push-relabel( $\dot { \iota } _ { \mathrm { o u t } } )$

7．更新距离 $D$ 内相邻单元格的高度

# 8.endwhile

9.根据弧 $( j _ { \mathsf { o u t } } , i _ { \mathsf { i n } } )$ 上的流发送移动传感器到节点j算法2推动-重标记算法(对于顶点 $u$ ）

1.if $e ( u ) { > } \Theta$

2．while $e ( u ) { > } \theta$ 且存在弧 $( u , w )$ 满足 $h ( u ) { = } h ( w ) { + } 1$ 和弧 $( u , w )$ 的剩余容量 $c a p ( u , w ) { > } { \theta }$

3. 通过向与 $w$ 相关联的单元格发送消息并通过弧 $( u , w )$ 推送$y { = } \mathfrak { m i n } \{ e ( u ) , c a p ( u , w ) \}$

4. $e ( u ) { = } e ( u ) - y$

5. $e \left( w \right) { = } e \left( w \right) { + } y$

6. 更新 $c a p ( u , w )$

7. endwhile

8.if $e ( u ) { > } \theta$

9. 更新 $h ( u )$ 为 $1 + \mathfrak { m i n } \{ h ( w ) : \ c a p ( u , w ) > \theta \}$

10．广播 $h ( u )$ 給距离 $D$ 内的相邻单元格

11 endif

12.endif

算法对通过一个单元格的总流的容量进行限制来限制移出单元格的移动传感器数量。将每个单元格 $i$ 分裂成两个顶点 $i _ { \mathrm { i n } }$ 和 $i _ { \mathrm { o u t } }$ ，分别表示输入顶点和输出顶点。输入顶点通过单向弧 $( \boldsymbol { i } _ { \mathrm { i n } } , \boldsymbol { i } _ { \mathrm { o u t } } )$ 与输出顶点连接，具有与 $m _ { i }$ 相同的零成本和容量， $m _ { i }$ 是可以移出单元格 $i$ 的移动传感器的上限；然后，输出顶点 $i _ { \mathrm { o u t } }$ 与相邻单元格的输入顶点 $j _ { \mathrm { i n } }$ 通过单向弧 $( \boldsymbol { i } _ { \mathrm { o u t } } \boldsymbol { j } _ { \mathrm { i n } } )$ 连接；在推动-重标记算法中，每个单元格必须保持2个顶点；在算法中，单元格仅需要知道距离 $D$ 内相邻单元格的顶点高度，就可以执行推动或重标记操作。同一单元格中的 $i _ { \mathrm { i n } }$ 和 $i _ { \mathrm { o u t } }$ 之间的推动过程与不同单元格之间的推动过程相同，只是不需要发送消息。每个单元格将根据其输入单元格的流入流将移动传感器发送给相邻的单元格。

# 3 仿真结果

# 3.1全移动网络

首先考虑全部传感器都是移动的。仿真中，将 $M { = } M$ 个移动传感器均匀随机地部署到面积为 $L$ 的网络中， $\boldsymbol { A }$ 固定为$\pi / 2$ 。然后，将移动传感器匹配到边长为 $d _ { \mathrm { s } } = \sqrt { 2 } r$ 的网格的 $M$ 个网格点上，使得它们可以对整个区域提供全覆盖，网络大小从 $1 0 { \times } 1 0$ 网格变为 $5 0 { \times } 5 0$ 网格；通过对 $1 0 ^ { 5 }$ 个随机生成的拓扑进行重复，得到对于不同最大移动距离 $D$ 时不存在可行匹配的概率。

图3所示为在不同网络大小下对于不同最大移动距离 $D$ 时不存在可行匹配的概率，其中移动距离 $D$ 通过网格大小 $d \mathrm { s }$ 归一化。从图2可见，当移动距离从 $1 . 5 d \mathrm { s }$ 增加到 $3 . 5 d _ { \mathrm { s } }$ 时，不存在可行匹配的概率从1迅速下降到0，这是由于在随机几何图中，单调性表明临界阈值的现象，同时表明最大移动距离越大，越容易实现可行匹配；还可看到，大型网络的最大移动距离较小。例如，在边长为 $l { = } 5 0 d _ { \mathrm { s } }$ 的网络中，移动传感器最多只需移动 $3 . 5 d _ { \mathrm { s } }$ 即可形成一个规则网格部署，它小于网络大小的十分之一。对于较大的网络，差别更大，因为移动距离与 $O ( \log ^ { 3 / 4 } L )$ 成比例。

# 3.2混合网络

在混合网络的仿真中，将网络区域划分为边长 $d _ { \mathrm { h } } \mathrm { = } _ { r } / \sqrt { 2 }$ 的单元格。将 $N { = } \lambda L$ 个静态传感器和 $M { = } _ { \mathit { 1 L } }$ 个移动传感器均匀部署在网络中，其中 $\scriptstyle \lambda = 2 \pi k$ 且选取 $M$ 使得恰好有足够的移动传感器来填充所有空洞，一个单元格中的移动传感器可以移动到距离 $D$ 内的单元格中；图4所示为当 $k { = } 1 0$ 时，对于不同网络大小不存在可行移动调度填充所有空洞的概率，其中最大移动距离通过 $d _ { \mathrm { h } }$ 归一化。可见在混合网络中，移动传感器的最大移动距离也随着网络大小的增大而缓慢增大。由于 $d _ { \mathrm { h } } { = } 0 . 5 d _ { \mathrm { s } }$ ，故混合网络的实际移动距离与 $k { = } 1$ 时的全移动情形相当；图5所示为不同 $k$ 值下的情形，其中网络大小为900个单元格。可见，混合网络要求的最大移动距离随 $k$ 的增大而略有减小， $k { = } 5 0$ 和 $k { = } 1 0 0$ 的曲线几乎重叠，这表明当 $k$ 较小时，最大移动距离受到从移动传感器到网格点的匹配距离和从网格点到空缺的匹配距离的影响。当 $k$ 增大时，从移动传感器到网格点的匹配距离将随着移动密度的增大而减小到零，然后，移动距离受到从空缺到网格点的匹配距离的制约，不随 $k$ 的增大而改变了。

![](images/0677ce05a5f50f588033f2d35ab1d4b3f7f90d8d53528a53980799ae7210dd78.jpg)  
图3全移动网络不存在可行匹配的概率

10 业业 →100个单元格 0-400个单元格 ·-900个单元格 0-1600个单元格 A-2500个单元格 o 2 3 4 5 6 归一化移动距离

![](images/5b8c20ff2f36be012249cef0108cf89a506871b557aa9d33682a396a57947fee.jpg)  
Fig.3Probability that there is no feasible matching for all-mobile networks   
图4混合网络不存在可行匹配的概率  
Fig.4Probability that there is no feasible matching for hybrid networks   
图5不同k值的混合网络不存在可行匹配的概率  
Fig.5Probability that there is no feasible matching for hybrid networkswithdifferentk

图6所示为 $k { = } 1 0$ 时采用本文的混合网络实现 $k \mathrm { . }$ 覆盖与文献[10]、[9]和[13]算法实现 $k$ -覆盖的覆盖率比较结果。可以看到，本文的混合网络 $k \mathrm { . }$ -覆盖是最优的，在覆盖率方面较之于采用简单移动传感器实现 $k \mathrm { . }$ -覆盖的文献[10]和[9]的算法以及采用静态传感器实现 $k \mathrm { . }$ -覆盖的文献[13]的算法分别提高了约 $21 \%$ 、 $2 6 \%$ 和 $32 \%$ 。这是由于本文提出的混合网络结构既考虑了静态传感器的固定覆盖优势，又基于对网络区域的精细网格划分和移动传感器与覆盖空洞的精确匹配，采用合适的少量移动传感器移动最佳距离来填充覆盖空洞，从获得了更高的覆盖率。

![](images/8c6fc212ff2fa9fa57a298dffe7283270ca181bf8980ae782ab7e79832772d6a.jpg)  
图6不同算法实现 $\mathbf { k }$ -覆盖的覆盖率比较  
Fig.6Comparison of $\mathbf { k }$ -coverage achieved by different algorithms

# 4 结束语

本文针对传感器网络的 $k \mathrm { . }$ -覆盖问题进行了深入研究。首先定义了一个以表明WSNs部署效率的过度提供因子，然后在静态传感器网络和全移动传感器网络的 $k$ -覆盖研究基础上提出了一种由静态传感器和少量移动传感器构成的混合网络结构，以及实现移动传感器移动调度的分布式调度算法；仿真结果表明，提出的混合网络结构不仅能够实现精确的 $k \mathrm { . }$ 覆盖，而且相比于其他 $k \mathrm { . }$ -覆盖算法，有更高的覆盖率。

# 参考文献：

[1]方德亮．多传感器组网协同目标监视任务规划[D].郑州：解放军 信息工程大学,2017.(Fang Deliang.Mission Planning of Multisensor Collaborative Surveillance in Sensor Networks [D]. Zhengzhou: PLA Information Engineering University,2017.)   
[2]Liao WH,Kuai SC,Lin MS.An Energy-Efficient Sensor Deployment Scheme for Wireless Sensor Networks Using Ant Colony Optimization Algorithm [J].Wireless Personal Communications,2015,82 (4): 2135- 2153.   
[3]De P,Sarac K,Chandrasekaran R.Heuristics for 2-coverage multi point relay problem in wireless ad hoc and sensor networks [C]//Proc of 2016 14th International Symposium on Modeling and Optimization in Mobile, Ad-Hoc and Wireless Networks.Tempe,USA:IEEE Press,2016:1-8.   
[4]Shan A X,Xu X H, Cheng Z M. Target Coverage in Wireless Sensor Networks with Probabilistic Sensors [J]. Sensors,2016,16 (9):1372- 1393.   
[5]范兴刚，杨静静，王恒．一种无线传感器网络的概率覆盖增强算法 [J].软件学报,2016,27 (2):418-431. (Fan Xinggang,Yang Jingjing, Wang Heng.Algorithm for Enhancing Probabilistic Coverage in Wireless Sensor Network [J].Journal of Software,2016,27 (2):418-431.)   
[6]高建明，朱小华．无线传感网中一种负载均衡的多任务调度方案 [J].计算机应用与软件,2016,33(8):157-162,166.(Gao Jianming, Zhu Xiaohua.A load balancing-based multi-task scheduling scheme in wireless sensor networks [J].Computer Applications and Software,2016, 33 (8): 157-162,166.)   
[7]王远昊．无线传感器网络寿命分析与建模[D]．西安：西安电子科 技大学,2O16.(Wang Yuanhao.Modeling andAnalysis For The Lifetime of Wireless Sensor Networks [D]. Xian: XIDIAN University,2016.)   
[8]Saha D,Das N.Self-organized area coverage in wireless sensor networks by limited node mobility [J].Innovations in Systems and Software Engineering,2016,12(3):227-238   
[9]Ates E,Kalayci T E,UgUr A.Area-priority-based sensor deployment optimisation with priority estimation using K-means[J].IET Communications,2017,11(7):1082-1090   
[10]Dash D,Dasgupta A.Distributed restoring of barrier coverage in wireless sensor networks using limited mobility sensors [J].IET Wireless Sensor Systems,2017,7(6):198-207   
[11]高春玲，李孜，孙泽宇，等．无线传感器网络中多目标k-覆盖保持算 法[J].计算机工程,2016,42(7):59-64,71.(Gao Chunling,Li Zi,Sun Zeyu,et al.Multi-targetk-Coverage PreservationAlgorithmin Wireless Sensor Network [J].Computer Engineering,2016,42(7): 59-64,71.)   
[12]王丹丹，徐汀荣．无线传感器网络三维表面k-覆盖多连通部署方法 [J]．计算机应用研究，2018,35（7):2110-2113.（WangDandan，Xu Tingrong.k-coverage and multi connectivity method for 3D surface wireless sensor network [J].Application Research of Computers,2018, 35 (7):2110-2113.)   
[13] MaWY,YanF,Zuo XZ,et al.Coordinate-free k-coverage hole detection algorithm in wireless sensor networks [J].Journal of Southeast University (English Edition),2019,35(1): 8-15   
[14] Lambrou Theofanis P. Optimized Cooperative Dynamic Coverage in Mixed Sensor Networks [J].ACM Transactions on Sensor Networks, 2015,11 (3): 1-35   
[15] Jayakar S,Strichartz R.Average number of lattice points in a disk [J]. Communications on Pure and Applied Analysis,2017,15(1):1-8   
[16] Eppstein D,Van Kreveld M, Speckmann B,et al.Improved Grid Map Layout by Point SetMatching[J].International Journal ofComputational Geometry& Applications,2015,25(0):101-122   
[17] Cai G Q.Generation of correlated random variables and stochastic processes [J].Probabilistic Engineering Mechanics,2018,52:40-46