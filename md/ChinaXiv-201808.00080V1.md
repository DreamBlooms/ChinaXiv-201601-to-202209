# 基于IFOA-GA任务调度算法在云计算MapReduce模型中的研究

陈暄1，潘春平1，龙丹²(1．浙江工业职业技术学院，浙江 绍兴 312000;2.浙江大学，杭州 310058)

摘要：针对传统的云计算任务调度算法存在效率低，利用率不高的问题，采用改进的果蝇算法(improved fruit flyoptimization algorithm，IFOA)和遗传算法(genetic algorithm，GA)融合的算法用于处理任务调度。首先，将任务调度转换为DAG(directed acyclic graph，DAG)并通过Kruskal 算法将任务调度顺序进行化简；其次，针对果蝇算法的种群采用正交数组和量化技术进行初始化，对果蝇算法边界进行处理，对探索步长进行动态调整，并使用GA算法对个体选择进行选择处理；最后，将融合后生成的算法IFOA-GA用于仿真平台中的云计算任务调度，相对于IGA,IFOA,IPSO算法在QoS 的四个指标对比中具有一定的优势，说明 IFOA-GA算法能够有效的提高云计算调度效率。

关键词：云计算；任务调度；果蝇算法；种群初始化；边界处理 中图分类号：TP301 doi:10.3969/j.issn.1001-3695.2018.06.0307

# Research on cloud computing MapReduce model based on IFOA-GA task scheduling algorithm

Chen Xuan1, Pan Chunpin1,Long Dan² (1.Zhejiang IndustryPolytechnic Collge，ShaoxingZhejiang 312oo0,China;2.Zhejiang University，Hangzhou310058, China)

Abstract: Aimingat thelow eficiencyandlowutilizationrateoftraditionalcloudcomputing task schedulingalgorithms,this paper proposed an improved algorithmusing the improved fruitflyoptimization algorithm (IFOA)and genetic algorithm (GA) for task scheduling.Firstly,the task scheduling isconverted intoa DAG(Directed Acyclic Graph),andthe task scheduling sequence is simplified throughthe kruskal algorithm.Secondly,thepopulationof Drosophilaalgorithm is initialized using orthogonalarrysandquantizationtechniques.Theboundariesofthe Drosophilaalgorithmalgorithmareprocessd,the explorationstepsizeisdyamicallyadjusted,andtheindividualselectionisprocessdusingtheGAalgorithm.Finlly,the fusionalgorithm IFOA-GAisused incloudcomputing task scheduling in the simulation platform.Compared with IGA,IFOA and IPSO algorithm,ithas certainadvantages in thecomparison offour indexes of QoS,which shows that the IFOA-GA algorithm can be effective in mproving cloud computing scheduling efficiency

Key words: cloud computing; task scheduling;Drosophila algorithm;population initialization;boundary processing

# 0 引言

云计算任务调度一直以来都是云计算中研究的重要组成部分,其本质问题就是一种多目标优化问题,也是一种NP问题，传统的任务调度方法显然无法适应云计算任务调度,因此采用智能算法来求解是目前研究的主要方向[1]。国内外学者针对云计算任务调度算法进行了研究,在蝙蝠算法[2],遗传算法[3],蚁群算法[4-5],粒子群算法[中都对其进行了改进,取得了不错的效果;文献[7]提出了一种基于烟花算法的多目标优化调度模型,仿真实验说明了该算法具有良好的调度效率,该算法优点是利用了烟花算法性能高的特点,合理而快速的进行调度,缺点是仅仅与基本 PSO,GA 算法相比,缺乏对同类型的最新的算法进行对比;文献[8]提出了基于蝙蝠算法的云计算任务调度方法,通过对蝙蝠算法的种群初始化和依靠Powell局部搜索提高了云计算下的调度性能，该算法的优点是提高了虚拟机的处理效率,缺点是仅仅与聚类算法进行对比,缺乏与其他算法对比效果,文章说服力不够;文献[9]提出在云计算中采用改进的遗传算法,通过双向收敛蚁群算子求出精确解，该算法优点提高了求解精度和收敛速度，缺点是增加了算法的复杂性，提高了算法的求解时间;文献[10]提出将蚁群算法和粒子群算法进行改进后融合，用于云计算资源调度效率，该算法的优点是降低了消耗时间,降低了成本，缺点是降低了算法的精度。

本文在以上研究成果的基础上，提出了将改进的果蝇算法用于云计算的任务调度中。仿真实验通过与其他智能算法对比,取得了较好的效果。

# 7 云计算中的任务调度

# 1.1基于MapReduce 模型的任务定义

目前，大部分云计算任务模型都是采用基于MapReduce的思想,它是一种高效的任务调度模型,具体的工作流程已经在很多关于MapReduce文献中得到了体现,这里就不再进行描述了，在MapReduce 模型中,具有一定不足[11],其表现在:(1)用户提交的任务并不是都是简单的任务，(2)用户提交的任务不一定都能够分解成并行的子任务，子任务之间存在偏序的关系;(3）在Reduce中存在只有内层迭代完成才能进行外层迭代的问题。针对这些问题,本文对于MapReduce 模型进行了一些新的定义定义1:定义复杂任务所谓复杂任务是一组存在依赖关系的子任务构成的系统,该任务系统定义为 $( T , \prec , D , A )$

(1) $T = ( t _ { 1 } , t _ { 2 } , \cdots t _ { n } )$ 是一组可执行的任务; $t _ { i }$ 是任务 $T$ 中子任  
务(2)是 $T$ 上一个偏序关系,主要用来说明子任务之间的优  
先级,当 $t _ { i } \prec t _ { j }$ ,说明 $t _ { i }$ 要在 $t _ { j }$ 之前开始执行${ \left( 3 \right) } _ { D }$ 为通信矩阵, $d _ { i j } > = 0$ 表示从 $t _ { i }$ 到 $t _ { j }$ 的数据量(4) $A$ 是 $n$ 维向量, $A _ { i } > 0$ 表示任务 $t _ { i }$ 的计算量

显然云计算中作为组成复杂任务的子任务之间存在优先约束关系,复杂任务可以采用DAG 图来表示, $G = \left( T , E \right) , _ { T }$ 表示图中节点的集合,节点权值表示任务处理时间, $E$ 为边集合,边权值表示了数据之间依赖关系和通信时间,因此，一个DAG优先约束关系是一个节点在执行前,它的前序节点必须已经执行,当两个节点分配到同一个处理器,则他们的通信成本为0。

定义2：当 $G$ 为有向图,把以顶点 $\nu$ 为终点的边的数目，记作 $I D ( \nu )$ ,把以顶点 $\mathbf { \Lambda } _ { \nu }$ 为起点边的数目,记作 $O D ( \nu )$ ·

定义3:在一个DAG图的生成树是必须满足如下条件的子图 $T : G$ 和 $T$ 具有相同的顶点数,在 $T$ 中有足够的边连接 $G$ 中的所有顶点,当没有回路。当DAG图的每条边都指定一个权，因此集合中所有边的权最小生成树就是最小生成树。本文采用kruskal算法将DAG 图转换为最小生成树,其处理过程如下:图1(a)中表示DAG 图中描述的任务关系,图1(b)描述了最小生成树。两个图中的节点完全相同,有效的将DAG图中的冗余依赖关系精简了。

![](images/4284bfe5facf0851bd1b32c40eeba187471cf9c54427103795b36e35d5d69174.jpg)  
图1 (a)DAG之间的任务关系

![](images/0f47058b5897b4e6a9351575d52ac5307a4ffab514f759f52ed27a5658af33e1.jpg)  
图1 (b)生成最小生成树

# 1.2构建QOS的任务调度评价模型

本文选择基于服务质量QoS(Qualtiyof Service)作为MapReduce 模型中的任务调度的效果一个重要机制,在一般的QoS的基础上,将完成时间、花费成本,可靠性和能量消耗作为任务评价指标。

(1)完成时间：所谓完成时间主要是指一个任务在整个云计算资源调度中所花费的时间，一般而言,云计算的完成时间是用户最关心的问题,是衡量云计算任务调度效果好坏的重要标准。

(2)花费成本：云计算的任务调度肯定需要消耗云计算中若干资源,诸如CPU,内存,硬盘等等,这些资源具有各自的使用成本。因此云计算中的任务尽可能的在最低限度的消耗成本来保证任务的完成。

(3)可靠性：由于云计算自身就是一个将出于不同物理位置的计算机变成逻辑位置在一起的虚拟计算机系统，因此整个系统的可靠性是云计算任务调度的基础,由于系统可靠性无法采用具体的公式进行衡量，因此通过用户满意度来反映系统可靠性;

(4)能量消耗：云计算任务调度过程中不可避免的会涉及到能量消耗,这是因为云中不同的任务在调度不同的资源过程中，伴随着网络的带宽、硬件方面的消耗产生了能量消耗,在任务调度中,能量消耗是一个不能被忽视的问题。

为了能够获得高效的QoS,必须在同时满足以上四个评价标准的基础上,设 ${ \cal T } , { \cal C } , { \cal S } , { \cal E }$ 分别表示以上指标评价的完成时间、花费成本、可靠性和能量消耗,并且 $r 1 , r 2 , r 3 , r 4$ 代表其权重,且$r 1 + r 2 + r 3 + r 4 = 1$ ，使用 $F ( i )$ 表示第 $i$ 个任务调度方案,如公式(1)所示,当找到所有任务中的最优函数值即 $F _ { b e s t }$ 才是基于QoS的最佳的任务调度方案,如公式(2)所示。

$$
F ( i ) = r 1 \bullet T _ { i } + r _ { 2 } \bullet C _ { i } + r _ { 3 } \bullet S _ { i } + r _ { 4 } \bullet E _ { i }
$$

$$
F _ { b e s t } = B e s t ( F ( 1 ) , F ( 2 ) { \cdots } F ( i ) )
$$

# 2 FOA算法

2011年,Pan 提出了一种新型的群体智能优化算法:果蝇优化算法(FruitFly optimization algorithm,简称FOA),该算法主要模拟的是果蝇种群的觅食行为,采用基于群体协作机制进行寻优操作。FOA算法大致分为如下几个步骤

步骤1:设置种群规模Popsize,最大迭次数 $N u m$ ,群体范围$L r$ 和果蝇个体单次飞行范围 $F r$ ,果蝇群体中的个体的位置信息有对应的二维坐标给出,初始位置如下：

$$
\left\{ \begin{array} { l l } { { X _ { - } a x i s = r a n d ( L r ) } } \\ { { Y _ { - } a x i s = r a n d ( L r ) } } \end{array} \right.
$$

步骤2：嗅觉搜索过程

步骤2.1当群体中的一只果蝇通过嗅觉进行搜索的时候，赋值一个随机的飞行方向和距离,因此果蝇个体 $i$ 的新位置为：

$$
\begin{array} { l } { { \int } X _ { i } = X _ { - } a x i s + r a n d ( F r ) } \\ { \left[ Y _ { i } = T _ { - } a x i s + r a n d ( F r ) \right. } \end{array}
$$

步骤2.2食物的味道距离果蝇个体的位置是位置的，因此先计算果蝇个体到原点的距离 $D i s t _ { i }$ ,如公式(5),然后通过公式(6)设定味道的浓度值 Si

$$
D i s t _ { i } = \sqrt { X _ { i } ^ { 2 } + Y _ { i } ^ { 2 } }
$$

$$
S _ { i } = 1 / D i s t _ { i }
$$

步骤 2.3:通过公式(7)计算当前群体中的每一个果蝇个体 $i$ 的味道浓度 Smelli,

$$
S m e l l _ { i } = f i t n e s s ( S _ { i } )
$$

fitness(Si)表示浓度判断函数,通过FFOA算法优化问题求解,它是目标函数。

步骤2.4：选择当前种群中的最佳浓度值的果蝇个体，记录其味道的浓度值和相应位置

$$
[ b e s t S m e l l , b e s t I n d e x ] = \operatorname* { m i n } ( S m e l l )
$$

步骤3：视觉搜索过程

果蝇群体飞向步骤2中的最佳浓度的相应位置，即

$$
S m e l l B e s t = b e s t S m e l l
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { X _ { - } a x i s = X ( b e s t I n d e x ) } \\ { Y _ { - } a x i s = Y ( b e s t I n d e x ) } \end{array} \right. } \end{array}
$$

步骤4:不断的重复执行步骤2和步骤3,直到算法达到最大迭代次数。得到的最佳浓度的位置就是FFOA算法的最优解。

FOA算法的优点是整体算法简单,主要包括嗅觉搜索和视觉搜索两个部分，重要的算法参数仅为种群的数目和最大迭代搜索次数,文献[12-13]说明了FOA算法相比于其他智能算法具有良好的全局搜索策略和优化能力,但算法存在的缺点是局部搜索能力不足,寻优结果不稳定导致算法过早收敛。

# 3基于IFOA-GA算法的云计算任务调度策略

针对FOA算法存在的问题,本文从种群初始化、边界处理、步长变换和个体选择等4个方面进行改进，同时引入了GA与之进行融合,生成了新的算法IFOA-GA算法,并将此算法用于云计算任务调度中。

# 3.1种群初始化

实验表面对种群进行初始化能够对最优解具有积极的推动作用,能够有效的避免算法在前期中产生很多的无效的解[14],显然，FOA是没有进行种群初始化的,为了能够有效的避免这种情况的发生,保证有效解能够均匀额分布在解的空间中,特次需要对种群进行初始化。本文采用基于正交数组和量化技术的正交实验方法来进行FOA种群的初始化，这种方法可以使得初始解能够均匀的分布在可行解中，提高算法搜索最优解的速度。

步骤1:将FOA种群问题可行域 $[ l , u ]$ 划分为[,u],[l,u],[s,us],具体划分为

$$
\begin{array} { l } { \displaystyle { \left\{ l _ { i } = l + ( i - 1 ) \bigg ( \frac { u ( s ) - l ( s ) } { S } \bigg ) l _ { s } \right. } } \\ { \displaystyle { u _ { i } = u - ( S - i ) \bigg ( \frac { u ( s ) - l ( s ) } { S } \bigg ) l _ { s } } } \end{array} , i = 1 , 2 \cdots S
$$

其中, $u ( s ) - l ( s ) = \operatorname* { m a x } _ { 1 \leq i \leq D } \{ u _ { i } - l _ { i } \}$

步骤2:将子集 $[ l _ { i } , u _ { i } ]$ 进行 $Q _ { \mathrm { { l } } }$ 次量化后,得到

$$
a _ { i j } = \left\{ \begin{array} { l r } { l _ { i } , } & { ~ j = 1 } \\ { ~ } \\ { l _ { i } + ( j - 1 )  { \left( \frac { u _ { i } - l _ { i } } { Q _ { 1 } - 1 } \right) } ~ 2 \leq j \leq Q _ { 1 } - 1 } \\ { ~ } \\ { u _ { i } } & { ~ j = Q _ { 1 } } \end{array} \right.
$$

其中, $Q _ { 1 }$ 是奇数,构造正交数组 $L _ { M _ { 1 } } ( Q _ { 1 } ^ { N } ) = \left[ a _ { i j } \right] _ { M _ { 1 } \times N }$ ,根据公

式(13)

$$
\left\{ \begin{array} { l l } { ( a _ { _ { 1 , a _ { 1 1 } } } , a _ { _ { 2 , a _ { 1 2 } } } , \cdots , a _ { _ { N , a _ { 1 N } } } ) } \\ { ( a _ { _ { 1 , a _ { 2 1 } } } , a _ { _ { 2 , a _ { 2 2 } } } , \cdots , a _ { _ { N , a _ { 2 N } } } ) } \\ { \cdots } \\ { ( a _ { _ { 1 , a _ { M _ { 1 1 } } } } , a _ { _ { 2 , a _ { M _ { 1 2 } } } } , \cdots , a _ { _ { N , a _ { M _ { 1 N } } } } ) } \end{array} \right.
$$

选择 $M _ { \scriptscriptstyle 1 }$ 个个体,其中 $L _ { { \cal M } _ { 1 } } ( Q _ { 1 } ^ { N } )$ 按照如下规则进行构造,当满足 $( Q _ { 1 } ^ { J _ { 1 } } - 1 ) { \big / } ( Q _ { 1 } - 1 ) \geq N$ 的最小 $J _ { 1 }$ 。当 $( Q _ { 1 } ^ { J _ { 1 } } - 1 ) { \big / } ( Q _ { 1 } - 1 ) = N$ ，则$N ^ { ' } = N$ ，否则， $N ^ { ' } { = } ( Q _ { 1 } ^ { J _ { 1 } } - 1 ) \big / ( Q _ { 1 } { - } 1 )$ ，构造数组基本列$j = { \frac { { \cal Q } _ { 1 } ^ { k - 1 } - 1 } { { \cal Q } _ { 1 } - 1 } } + 1 \ , \ a _ { i j } = \left\lfloor \frac { i - 1 } { { \cal Q } _ { 1 } ^ { J _ { 1 } - k } } \right\rfloor \bmod { \cal Q } _ { 1 } \ , i = 1 , \cdots , M _ { 1 } , k = 1 , \cdots , J _ { 1 } \ n$ 非基本 列 为$j = \frac { Q _ { 1 } ^ { k - 1 } - 1 } { Q _ { 1 } - 1 } + 1 \qquad , \qquad a _ { j + ( s - 1 ) ( Q _ { 1 } - 1 ) + t } = ( a _ { s } \times t + a _ { j } ) \bmod Q _ { 1 }$ $s = 1 , \cdots , j - 1 , t = 1 , \cdots , Q _ { 1 }$ ,这样数组（204号 $L _ { { \cal M } _ { 1 } } ( Q _ { 1 } ^ { N } )$ 就构造完成。删除 $L _ { M _ { 1 } } ( Q _ { 1 } ^ { N } )$ 的最后 $N ^ { ' } - N$ 列得到$L _ { M _ { 1 } } ( Q _ { 1 } ^ { N } )$ ,其中, $M _ { 1 } = Q _ { 1 } ^ { J _ { 1 } }$ 步骤3:在 $M _ { 1 } S$ 个体中,选择 $\mathit { s N }$ 个适应度最高的个体作为初始种群。

# 3.2边界处理

FOA 中个体极其有可能会超出可行域的范围的边界,当某个个体 $x _ { i }$ 的第 $k$ 维超出边界时，则按照公式(4)的处理方法将超过边界的果蝇个体映射到一个新的位置,定义如下：

$$
\begin{array} { r } { \hat { x } _ { i , k } = \left\{ \begin{array} { l l } { \displaystyle x _ { o , k } + \frac { x _ { i , k } - x _ { o , k } } { \big \| \left| x _ { i } - x _ { o } \right\| } * \big | x _ { L B , k } - x _ { o , k } \big | \mathrm { ~ } i f \left. x _ { i , k } < x _ { L B , k } \right. } \\ { \displaystyle x _ { o , k } + \frac { x _ { i , k } - x _ { o , k } } { \big \| \left| x _ { i } - x _ { o } \right. \big \| } * \big | x _ { U B , k } - x _ { o , k } \big | \mathrm { ~ } i f \left. x _ { i , k } > x _ { U B , k } \right. } \end{array} \right. } \end{array}
$$

式(14)中, $x _ { U B , k } , x _ { L B , k }$ 分别为解空间中的第 $k$ 维的上下边界, $x _ { o }$ 表示解空间的原点。公式(14)借助图2的推理的过程如下:

(1)越上界

$$
\begin{array} { c } { \displaystyle \cos \alpha = \frac { x _ { i , k } - x _ { o , k } } { \big \| x _ { i } - x _ { o } \big \| } = \frac { m } { \big | x _ { U B , k } - x _ { o , k } \big | } } \\ { \displaystyle \Rightarrow m = \frac { x _ { i , k } - x _ { o , k } } { \big \| x _ { i } - x _ { o } \big \| } \ast \big | x _ { U B , k } - x _ { o , k } \big | } \end{array}
$$

以原点 $x _ { o }$ 作为中心,半径为 $\mathbf { \Sigma } _ { m }$ 进行画圆,通过与 $k$ 轴的交点就是超越边界处理后的第 $k$ 维的分量,即

$$
\begin{array} { c } { { \hat { x } _ { i , k } - x _ { o , k } = m = \displaystyle \frac { x _ { i , k } - x _ { o , k } } { \left\| \begin{array} { l } { { x _ { i } - x _ { o } } } \end{array} \right\| } * \left| x _ { U B , k } - x _ { o , k } \right| } } \\ { { \Rightarrow \hat { x } _ { i , k } = \displaystyle \frac { x _ { i , k } - x _ { o , k } } { \left\| x _ { i } - x _ { o } \right\| } * \left| x _ { U B , k } - x _ { o , k } \right| + x _ { o , k } } } \end{array}
$$

(2)超越下边界

$$
\begin{array} { c } { { \displaystyle \cos \beta = \frac { x _ { i , k } - x _ { o , k } } { \parallel x _ { i } - x _ { o } \parallel } = \frac { n } { \left| \begin{array} { c } { { x _ { L B , k } - x _ { o , k } } } \end{array} \right| } } } \\ { { \Rightarrow n = \frac { x _ { i , k } - x _ { o , k } } { \parallel x _ { i } - x _ { o } \parallel } \ast \left| \begin{array} { c } { { x _ { L B , k } - x _ { o , k } } } \end{array} \right| } } \end{array}
$$

与超越上边界一样,它以原点 $x _ { o }$ 作为中心,半径为 $n$ 进行画圆,通过与 $k$ 轴的交点就是超越边界处理后的第 $k$ 维的分量,即

$$
\begin{array} { c l } { \displaystyle \hat { x } _ { i , k } - x _ { o , k } = n = \frac { x _ { i , k } - x _ { o , k } } { \left\| \begin{array} { l l } { x _ { i } - x _ { o } } \end{array} \right\| } * \left| x _ { L B , k } - x _ { o , k } \right| } \\ { \displaystyle \Rightarrow \hat { x } _ { i , k } = \frac { x _ { i , k } - x _ { o , k } } { \left\| x _ { i } - x _ { o } \right\| } * \left| x _ { L B , k } - x _ { o , k } \right| + x _ { o , k } } \end{array}
$$

通过上面的推理可以发现,超越上边界的果蝇个体进行处理处理后，其位置能够能够靠近上边界，同理,当超越下边界的果蝇个体处理后,其位置就会靠近下边界,这样相对位置没有发生改变,保持了一些原有的数据特性。图2表示了越界处理坐标参考，图3表示假设一定范围后的越界前后的对比效果。

![](images/408905a76e5607f8773847f14abfbfd8f41084813839b247d1b3d88552d74b00.jpg)  
图2越界处理辅助示意图

![](images/b383503692fd183c34424a5120e81a15cc36186c90d49ffbb7b4eb5f6ea8806f.jpg)  
图3（1）越界前示意图

![](images/5bada56c3b2cf5e45846623f5de2e182c80abe059d898b89a0f62b93beefacb6.jpg)  
图3(2)越界后示意图

# 3.3搜索步长的改进

果蝇算法[15]会在果蝇新位置的诞生中设定一定的步长，这样设置的好处在于能够使得果蝇个体在向随机方向搜索的时候，不会超出一定的范围。当步长设置的过大的时候,算法的全局搜索能力就会较强，从而收敛速度快，但局部搜索能力降低，导致算法在后期收敛精度不够,当设置步长过小的时候,局部搜索能力过大,但全局搜索能力降低。因此,本文对步长采用可变换的思想进行改进,如公式(19)所示。

$$
\begin{array} { r l } & { \left\{ \begin{array} { l } { X _ { i } = X \_ { - } a x i s + r a n d ( F r ) \times H } \\ { Y _ { i } = T \_ a x i s + r a n d ( F r ) \times H } \end{array} \right. } \\ & { \quad \quad \quad s . t \ H _ { i } = \left\{ \begin{array} { l } { L \times ( 1 + \sin ( i ) ) ^ { \alpha } \ H _ { i } \leq L } \\ { L \qquad \ H _ { i } > L } \end{array} \right. } \\ & { \qquad \quad \quad \alpha = \mathrm { m o d } ( i , T ) } \end{array}
$$

式中， $\mathbf { \Omega } _ { L }$ 为算法搜索空间的长度， $T$ 为搜素迭代次数, $\alpha$ 为第 $i$ 次迭代取余，因此 $H _ { i }$ 分布如图4所示

![](images/6335c9ec7b1485ed776732623c288c1a9f74329de01d7310b1a4a689e3d47c7c.jpg)  
图4步长变化

从图4中发现,改进的步长方式将整个搜索过程分解为若干个周期,这样能够有效的增强搜索过程中的多样性,使得算法能够跳出局部收敛,减少了局部收敛的可能性,采用 $\sin ( x )$ 函数,使得步长在单位周期内进行有规律的变化,能够有效的控制步长在增加和减少对算法带来的影响,当 $\sin ( x )$ 在单调递增的时候,步长逐渐增大,使得算法具有较强的全局搜索能力,能够解决$\sin ( x )$ 在上一个单调递减内可能存在局部收敛的问题,在 $\sin ( x )$ 函数递减区,步长逐渐减少,使得算法能够在小范围内完成高精度的搜索，具有更好的收敛效果。

# 3.4个体选择改进

在FOA算法中,果蝇个体仅仅是凭借自身的浓度来选取方向，显然这种方式仅仅是从果蝇个体的角度出发，没有考虑到果蝇个体自身的优劣为在下一代迭代中产生的影响,没有从整体上考虑最优浓度值对整个算法的影响。因此,借助GA思想对果蝇个体选择进行改进。

(1)果蝇个体选择

果蝇个体根据浓度值来确定适应度值，并且将个体的最优的浓度值作为当前最优适应度,这样的方式存在一定的缺陷，主要是没有考虑到果蝇个体的浓度与整个种群对应的浓度的关系，在一定程度上造成算法解陷入布局最优。本文采用基于正向序列的适应度函数的构造，按照目标函数值的大小将种群中的个体按照从大到小的顺序排序，然后将排序后的个体按照映射关系计算适应度函数值。构造正向序列的适应度函数为

$$
f _ { i } = 1 - \frac { i + 1 } { N } , i = 1 , 2 , \cdots N
$$

式(20)中 $i$ 表示果蝇种群中的个体， $N$ 为种群规模,两个相邻的个体之间的适应度值差为：

$$
f _ { i + 1 } - f _ { i } = - \frac { 1 } { N }
$$

式(21)表明相邻个体之间的差异取决于种群的规模，因此按照轮盘选择个体方式来计算概率,第 $i$ 个个体被选择的概率为:

$$
p _ { i } = \frac { N - i + 1 } { \displaystyle \sum _ { i = 1 } ^ { N } N - i + 1 } , i = 1 , 2 , \cdots N
$$

两个相邻的个体被选择的概率误差为：

$$
p _ { i + 1 } - p _ { i } = - \frac { 1 } { \displaystyle \sum _ { i = 1 } ^ { N } N - i + 1 } , i = 1 , 2 , \cdots N
$$

$$
f ( x _ { i } ) = \sum _ { i = 1 } ^ { n } p _ { i } * ( y _ { i } ^ { ' } - y _ { i } )
$$

从式(24)中可以发现,相邻个体之间被选择的概率比较小，这就保证不会因为个体之间被选择的概率过大而影响选择操作，特别是当种群规模增大的时候,差异就越小,从而提高个体选择的能力,从而能够提高个体被选择的几率,增加了多种的多样性。

(2)变异操作：将第 $g$ 代种群中的第 $i$ 个果蝇个体 $x _ { i } ^ { g }$ 依据公式(25)的变异方式。

$$
V _ { i } ^ { g + 1 } = x _ { i } ^ { g } + F * ( x _ { r 1 } ^ { g } - x _ { r 2 } ^ { g } )
$$

式(25)中的 $V _ { i } ^ { g + 1 }$ 是变异后的种群中的个体， $F$ 为随机因子用来控制缩放程度，设定值为[0,1]之间。

(3)交叉操作:通过一定的概率选择,将变异的中第 $i$ 个体 $x _ { i } ^ { g }$ 与父代个体 $V _ { i } ^ { g + 1 }$ 之间在第进行交叉,得到新的个体

$$
\kappa _ { i } ^ { g } = \left\{ \begin{array} { l l } { V _ { i } ^ { g + 1 } , ~ t \in [ 0 , 1 ] } \\ { x _ { i } ^ { g } , o t h e r w i s e } \end{array} \right.
$$

式(26)中可以保证在交叉过程出现一个0到1之间的随机整数,能够保证κi,至少有一个分量来自yi.j。

# 3.5算法流程

步骤1:将云计算任务调度按照DAG图描述,根据kruskal算法精简为最小生成树，去掉冗余的信息,保留最精简的任务关系,并根据QoS模型设定好每一个任务的函数值,并与果蝇个体一一对应,当寻找到最佳果蝇个体即为最优的任务调度函数值，初始化果蝇算法中的相关参数

步骤2:采用公式(11-13)对果蝇种群进行初始化

步骤3：采用公式(19)对果蝇嗅觉搜索过程进行位置更新，执行公式(5-8),在视觉搜索过程中，如果飞行过程中出现越界情况，按照公式(14)的越界处理。

步骤4:对果蝇个体采用(20-26)进行更新

步骤5:判断算法是否达到最大迭代次数，如果达到了，就转步骤6.否则转步骤3

步骤6:算法结束，最优果蝇个体即为最佳的任务函数值。

流程如图5所示：

![](images/aa39a7568b986877885d03683e6e3c9d640e835f58fe8c0c86b5993e03920f63.jpg)  
图5本文算法流程图

# 3.6算法仿真

为了进一步说明IFOA-GA算法在云计算中具有的效果,本文选择硬件平台中的CPU为酷睿i57500,内存为4GDDR3,硬盘为1T,软件环境为64位的Windows系统,仿真平台采用Cloudsim。将IFOA-GA,IFOA[15],IPSO[16]和IGA[17]算法进行比较，设置算法的最大迭代次数为100次，任务数量为[10000,100000]。参与对比的算法的参数均以各自的文献为主。从完成时间、花费成本、可靠性和能量消耗四个方面进行对比。

![](images/f5696928f39f261b01ef6c5a89158a41c717b3092e6b26212c46769fc3c1ccfb.jpg)  
图6四种算法的完成时间对比

图6显示了四种算法的完成时间对比,伴随着任务数量的逐渐增多,四种算法的完成时间都在逐渐增多，IPSO,IGA都是改进后的智能算法,但是与IFOA-GA相比还是存在的一定的差距,从整个任务完成的情况来看，IFOA-GA所需要完成的时间还是最少的,这说明IFOA-GA算法相比其他三种算法具有一定的优势。

![](images/f07bcbabc14b6552a0d24f50f9f2bd37cfd18d779e4f8b41e263e2f92bbde9f1.jpg)  
图7四种算法的消耗成本对比

图7显示了四种算法的消耗成本对比，随着任务数量的逐渐增多，四种算法消耗成本都在逐渐的增多，IFOA-GA算法在初始阶段消耗的成本的曲线波动比较大，究其原因是因为算法在开始阶段进行种群的初始化,消耗了较多的成本，后期随着算法逐渐深入，算法消耗成本逐步稳定,相比其他三种算法,IFOA-GA算法在总体上还是处于一定的优势，这也说明IFOA-GA算法相比于其他三种算法能够有效的降低成本。

![](images/971e0db8696d4ceca2469ba7e3e3a3e685466a82a38654ac8d75149e5f1e2517.jpg)  
图8四种算法可靠性

图8显示了四种算法的可靠性的对比结果，随着任务数量的逐渐增多，IFOA-GA算法相比于其他三种算法具有一定的优势，这是因为IFOA-GA算法对FOA算法进行了改进,并结合GA优点,因此算法的性能更加突出,在云计算的任务调度中具有良好的效果。

![](images/30be921cdd858cd1926e7841a1bf083cf6f776c8b246d59e2790cf33bca0f9be.jpg)  
图9四种算法的能量消耗对比

图9显示了四种算法的能量消耗的对比结果，随着任务数量的逐渐增多，四种算法的能量消耗都在逐渐的增大，但是从整体上看，IFOA-GA算法能量消耗曲线稳定,波动性小,而其他三种算法的曲线波动性大,因此，IFOA-GA算法相比其他三种算法大致平均降低了 $7 . 2 7 \% , 9 . 3 3 \%$ 和 $1 5 . 4 9 \%$ 。

在以上的实验结果中说明了本文算法相比于IFOA,IPSO和IGA算法具有一定的优越性,通过在果蝇的种群初始化中使用正交数组和量化技术提高了算法最优解的速度,对果蝇个体可能出现的越界进行处理,对果蝇探索步长进行动态调整，使用GA算法对个体选择进行处理等措施,使得算法的整体性能得到提升，也进一步提高了云计算下的任务调度效率。

# 4 结束语

针对云计算任务调度存在的问题,本文在FOA和GA基础上进行算法融合生成了IFOA-GA算法,将该算法运用在云计算任务调度中获得较好的效果,但本文没有考虑虚拟机负载在任务调度中的影响,在下一步中将继续展开研究。

# 参考文献：

[1]张建勋，古志民，郑超．云计算研究进展综述[J].计算机应用研究，

2010,27 (2):429-433.(Zhang Jianxun. Survey of research progress on

cloud computing [J]，Application Research of Computers,2010,27 (2): 429-433. )   
[2]Santwana S,Saurabh B.Workflow Scheduling in Cloud Computing Environment Using Bat Algorithm [J],Proceedings of First International Conference on Smart System,Innovations and Computing,2O18,Doi. org//10.1007/978-981-10-5828-8_15   
[3]Kaur K.A Novel Context and Load-Aware Family Genetic Algorithm Based Task Scheduling in Cloud Computing [J],Data Engineering and Intelligent Computing,2017,Doi.org//10.1007/978-981-10-3223-3_51   
[4]Vinothina V.An Approach for Workflow Scheduling in Cloud Using ACO [J],Big Data Analytics,2017,Doi.org/10.1007/978-981-10-6620-7_50   
[5]Shabeera T P.Optimizing VM allocation and data placement for data-intensive applications in cloud using ACO metaheuristic algorithm [J], Engineering Science and Technology,an InternationalJournal,2O17, (2): 616-628   
[6]Sadhasivam N. Cancer Diagnosis Epigenomics Scientific Workflow Scheduling in the Cloud Computing Environment Using an Improved PSO Algorithm [J] Asian Pac JCancer Prev.2018;19 (1): 243-246.   
[7]黄伟建，郭芳．基于烟花算法的云计算多目标任务调度[J].计算机应 用研究，2017，34(6):1718-1720．(HuangJinwei，Guo Fang. Multi-objective task scheduling based on fireworks algorithm in cloud computing [J]，Application Research of Computers，2017，34(6): 1718-1720. )   
[8]乔良，林伟伟．基于改进蝙蝠算法的云计算任务调度研究[J].微电子 学与计算机．2017，34（7):27-32.(Qiao Liang，Lin wei-wei.Cloud Computing Task Scheduling Based on Improved Bat Algorithm [J], Microelectronics & Computer,2017,34(7):27-32)   
[9]赵俊普，殷进勇，金同标．遗传蚁群算法在云计算资源调度中的应用 [J].计算机工程与设计,2017,38(3): 693-697.(Zhao jun-pu,yin jin-yong, Jin tong-biao.Application of genetic ant colony algorithm in cloud computing resource scheduling [J]，Computer Engineering and Design, 2017,38 (3): 693-697.)   
[10]萨日娜．基于蚁群粒子群优化算法的云计算资源调度方案[J]，吉林大 学学报：理学版,2017,55(6):1518-1522.(Sa Rina,Cloud Computing

Resource Scheduling Scheme Based on Ant Colony Particle Swarm

Optimization Algorithm[J],Journal of Jilin University: Sci Ed,2017,55 (6): 1518-1522.) [11]方锦明．一种面向云计算的改进的 Mapreduce 模型[J].计算机测量与 控制,2012,20 (5): 1417-1419.(Fang jing-ming.An improved Mapreduce Models Based on Cloud Computing[J]，Computer Measurement & Control,2012, 20 (5): 1417-1419. ) [12]吴小文，李擎．果蝇算法和5 种群智能算法的寻优性能研究[J]．火力 与指挥控制,2013,38(4):17-20.(Wu xiao-wen,Li qing.Research of Optimizing Performance of Fruit Fly Optimization Algorithm and Five Kinds of Intelligent Algorithm[J],Fire Control & Command Control,   
2013, 38 (4): 17-20. ) [13]刘立群，韩俊英，代永强．果蝇优化算法优化性能对比研究．计算机技 术与发展,2015,25(8): 94-98.(Liu li-qun,Han jun-ying,Dai yong-qiang. Comparative Study on Optimization Performance of Fruit Fly Optimization Algorithm [J]，Computer Technology and Development,2015,25(8):   
94-98. ) [14]常天庆，白帆，李勇．解WTA问题群智能优化算法的种群初始化问题 研究[J].计算机应用研究，2013,30(5):1377-1380.(Chang tian-qing, Baifang，Li yong.Research on population initialization for swarm intelligenceoptimization solving WTA[J]，Application Researhof Computers,2013,30(5):1377-1380.) [15]段艳明，肖辉辉．一种新的自适应步长果蝇优化算法[J].河南师范大 学学报（自然版）,2016,44(1):161-168.(Duan yan-ming,Xiao hui-hui. Research of the Self-adaptive Step Fruit Fly Optimization Algorithm [J], Journal of Henan Normal University (Natural Science），2O16,44(1):   
161-168. ) [16]王晓天，韩啸．基于改进粒子群算法的云计算服务部署优化[J]．吉林 大学学报(理学版）,2017,55(2):393-397.(Wang xiao-tian,Han xiao. Cloud Computing Service Deployment Optimization Based on Improved Particle Swarm Algorithm[J],Journal of Jilin University: Sci Ed,2017, 55 (2): 393-397. ) [17]李超，戴炳荣，旷志光.云计算环境下基于改进遗传算法的多维约束任 务调度研究[J].小型微型计算机系统，2017,38(9):1945-1949.(Li chao,Dai bing-rong.Research on Task Scheduling with Multiple Constraints Based on Genetic Algorithm in Cloud Computing Environment [J],Mini-micro Systems,2017,38 (9): 1945-1949.)