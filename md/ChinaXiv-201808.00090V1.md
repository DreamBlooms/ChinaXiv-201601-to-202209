# 基于元胞自动机的普通超市火灾疏散模型的构建 F

江雨燕，刘军

(安徽工业大学 管理科学与工程学院，安徽 马鞍山 243032)

摘要：通过分析已有的元胞自动机理论，结合人员疏散的特点，构建了考虑出口吸引力、火灾排斥力、摩擦力、排斥力和从众吸引力的普通超市火灾疏散模型。该模型充分考虑了多个因素对疏散过程的影响，对影响因素进行归一化处理，以综合影响因素建立的元胞转移强度作为行人移动规则。针对超市疏散人数、出口宽度及相隔距离、从众心理对疏散时间的影响进行了研究，并采用仿真疏散软件Pathfinder+FDS对模型进行验证，说明疏散模型具有一定可信性。研究表明：行人疏散时间随人数呈线性正相关，人数存在临界值；出口宽度越宽或出口越多疏散时间相对越短，当达到出口阀值时对疏散时间影响不大；在陌生疏散环境或紧急情况下适当的从众行为会提高疏散效率。

关键词：元胞自动机；元胞转移强度；从众吸引力；火灾疏散模型 中图分类号：TP391.9 doi:10.3969/j.issn.1001-3695.2018.05.0297

# Construction of fire evacuation model for ordinary supermarket based on cellular automata

Jiang Yuyan, Liu Jun (School of Management Science & Engineering Anhui University of Technology,Ma'anshan Anhui 243032 China)

Abstract:Byanalyzing theexisting cellular automata theoryand combiningthecharacteristics ofgroupevacuation,this paper establishesanordinarysupermarket fire evacuation model that considersthe atractivenessof exit,firerepulsion,friction, repulsionandoccupant psychology.Themodel fullyconsiders theinfluence ofmultiple factors onthe evacuation,normalizes theinfluencingfactors,anduses thecelltransfer intensityestablished byconsideringthecomprehensive influencing factorsas thepedestrian movementrule.This paperstdies theimpactofthe numberofevacuees insupermarket,export widthanddistance, andherd mentalityonevacuation time.Pathfinder+FDS,asimulation evacuation software,isusedtoverifythe model,which showed thatthe evacuation model hascertain credibility.Theresearch shows that pedestrian evacuation time is linearlyand positivelycorrelated with the numberof evacuees,andthere isacritical pointfor thenumberof evacues; thewiderthe exit width isor the moreexitsare,theshortertheevacuationtimeis,butoncetheexitthreshold isreached,theimpactonthe evacuation time is not significant; inunfamiliar environmentsor emergency situations,appropriate herdingbehavior wil improve the efficiency of evacuation.

Key Words: cellular automata; cell transfer intensity; occupant psychology; fire evacuation model

# 0 引言

近几年我国火灾事故频频发生，如8.12天津港特大火灾爆炸事故、河南鲁山康乐园老年公寓特大火灾和北京大兴11.18火灾等。特别是大型公共场所，人员相对比较集中且建筑结构比较复杂，疏散难度较大，一旦发生火灾群体人员能否快速、安全疏散直接关系着人们的生命和财产安全。火灾情景下如何快速和安全地进行疏散是值得研究的问题[l\~4]。

目前，国内外对疏散方面的研究主要集中在疏散模型的建立和疏散路径规划方面，常见的群体疏散模型主要包括社会力模型、磁力场模型、格子气模型和元胞自动机模型。Wan等人[5]提出了一种社会力和高斯烟团相结合的模型，研究地铁站突发有毒气体对疏散人员速度和伤亡的影响；Guo等人[将CA模型和格子气模型结合来模拟行人疏散，研究人员密度和出口拥挤度对疏散过程的影响；Yue等人[7针对视线受影响和无恐慌踩踏行为情景下建立CA模型，对行人疏散流进行仿真研究；Hu 等人[8为了研究三维空间中行人移动过程中的碰撞，提出了三维空间CA模型，验证了“快即是慢"现象；李世威等人[通过定义行人方向模糊可视域改进了CA模型，改进的模型能有效出现初始非均匀的行人自组织现象。路径规划算法主要包括 $\mathbf { A } ^ { * }$ 算法、Dijkstra 算法、Floyd 算法、蚁群算法和粒子群算法等，王茹等人[10建立了基于改进蚁群算法的CA 模型，对 ACO 算法中的启发函数和禁忌规则进行修改，结果表明该模型能快速找到最优路径；Tsai等人[1提出了基于PSO的疏散仿真框架，该框架可以适应多种场景变化，如疏散人数、障碍物、出口和指示标志的改变；段鹏飞等人[12]采用遗传算法交叉和变异对蚁群算法中的信息素更新进行改进，研究大型场所疏散中的路径优化问题。人员疏散是一个复杂的过程，其中涉及到火灾环境、人员心理和疏散行为等多个因素影响，以上研究未综合考虑多个影响因素对人员疏散过程的影响。

本文基于元胞自动机模型建立了充分考虑群体在疏散时的心理特点和行为的疏散模型，并对超市疏散过程进行模拟，为超市出口和布局设置更有效提高疏散效率提供依据。

# 1 仿真模型建立

将二维平面分割成大小相同的网格，一个网格代表一个元胞。网格有两种情形：障碍物或人占据，或为空。模型中每个元胞划分为 $0 . 4 \mathrm { m } { \times } 0 . 4 \mathrm { m }$ 的网格，疏散中每个人员占据一个元胞。人员在疏散过程中速度为 $1 . 0 \mathrm { m / s }$ ，每个时间步为 $0 . 4 { \mathrm { ~ s ~ } } _ { \mathfrak { i } }$ 0每个时间步内人员只能移动一个方格，领域类型选取Moore型正方向网格，每个时间步的元胞以一定的转移强度向其未被占据邻居8个元胞移动或者静止，元胞的转移方向如图1所示的8个方向，火灾的蔓延模型采用扩展的Moore型如图2所示。

![](images/6c4e0719617dbcbe824723dad9d5f2204c97a7a49c61e2447f365398fd177ad5.jpg)  
图1正方向网格模型  
图2火灾蔓延模型

# 1.1元胞转移强度计算

人员在疏散过程中会遵循一定的行走规则，行为会在每步更新时随周围环境做出动态调整。元胞在移动过程中主要存在两个基本问题需要解决：其一行人转向问题，本文采用出口吸引力、火灾排斥力、摩擦力、排斥力和从众吸引力综合影响的元胞转移强度来判断人员转向；其二多人竞争同一位置时采用竞争力大者占据该位置。

紧急情况下人员疏散以安全出口为目标，疏散人员会选择最近路径来向出口运动。出口吸引力与距离出口远近呈正相关，距离出口越近的元胞对疏散人员的吸引力越大，相应的 $D _ { i j }$ 值也越大。采用疏散人员位置到出口的欧式距离做为出口吸引力。当出口宽度不只一个元胞大小时，取距离出口最近的该元胞位置计算距离。当存在多个疏散出口时，计算到多个出口的欧式距离取最小值。具体公式如下：

$$
D _ { i j } = m i n _ { m } \left\{ m i n _ { n } \big \{ \sqrt { ( i - i _ { n } ^ { m } ) ^ { 2 } - ( j - j _ { n } ^ { m } ) ^ { 2 } } \big \} \right\}
$$

其中： $D _ { i j }$ 为疏散人员位置 $( \mathrm { i } , \mathrm { j } )$ 距离出口距离； $( i _ { n } ^ { m } , j _ { n } ^ { m } )$ 为出口 $\mathbf { m }$

中n元胞的坐标位置。有障碍物存在时，先采用Dijkstra算法找出最优路径并计算距离，再利用公式(2)进行归一化处理。根据计算的最小距离，再做归一化处理，出口吸引力概率公式为

$$
\begin{array} { r } { P _ { d e c i d e } ( i , j ) = \frac { D _ { m a x } - D _ { i j } } { D _ { m a x } - D _ { m i n } } } \end{array}
$$

其中： $P _ { d e c i d e } ( i , j )$ 为人员位置 $( \mathrm { i } , \mathrm { j } )$ 的出口吸引力概率； $D _ { m a x }$ 为相邻8个元胞中距离出口最大值； $D _ { m i n }$ 为相邻8个元胞中距离出□最小值； $D _ { i j }$ 为(ij)位置距离出口距离。

火灾排斥力为人员在疏散过程中希望远离火灾的趋势。计算元胞空间距危险源的欧式距离，从而引入排斥力概率：

$$
\begin{array} { r } { P _ { f i r e } ( i , j ) = - \frac { F _ { i j - } F _ { m i n } } { F _ { m a x } - F _ { m i n } } } \end{array}
$$

其中： $P _ { f i r e } ( i , j )$ 为元胞 $( \mathrm { i } , \mathrm { j } )$ 的排斥概率； $F _ { m a x }$ 为相邻8个元胞中距离火灾的最远欧氏距离； $F _ { m i n }$ 为相邻8个元胞中距离火灾最近的欧式距离； $F _ { i j }$ 为元胞 $( \mathrm { i } , \mathrm { j } )$ 距离火灾的欧式距离，离火灾源越近的位置火灾排斥力越大。火灾发生地具有随机性，且随机选择扩散。

模仿社会力模型，人员在疏散过程中也存在排斥力和摩擦力，排斥力主要存在多人竞争同一位置、相向运动、人员避免与墙或障碍物碰撞。对此宋卫国[13]等人引入了排除和摩擦概率，本模型借鉴此方法，排斥力概率公式为

$$
\begin{array} { c } { { R _ { i j } = \displaystyle \frac { 1 - e ^ { - \mu V } } { 1 + e ^ { - \mu V } } \qquad P _ { r } ( i , j ) } } \\ { { \displaystyle = - \frac { R _ { i j } - R _ { m i n } } { R _ { m a x } - R _ { m i n } } } } \end{array}
$$

其中：V为人员移动速度， $\mu \in [ 0 , \infty ]$ 为硬度系数，疏散人员密度越大，碰撞的恐慌越大，排斥力越大， $\mu { = } 1$ （人与人之间）、$\mu { = } 1 . 5 \up$ (人与墙或障碍物之间)。摩擦力主要存在于人与人、人与墙和障碍物之间，其大小主要受接触程度、相对速度和摩擦系数影响。由于元胞中格点相同，则接触程度是一样的。摩擦力概率公式为

$$
\begin{array} { r } { F _ { i j } = { \theta } * \mathrm { { V } } \qquad P _ { f } ( i , j ) = - \frac { F _ { i j } - F _ { m i n } } { F _ { m a x } - F _ { m i n } } } \end{array}
$$

其中：V为人员移动速度， $\theta \in [ 0 , 1 ]$ 为摩擦系数，主要反映人员在疏散过程中人与人、人与墙或障碍物的摩擦程度， $\scriptstyle { \Theta = 0 . 1 }$ （人与人、 $\scriptstyle { \Theta = 0 . 3 ( }$ (人与墙或障碍物之间)。

突发火灾情况下，人员在疏散过程中会出现恐慌，会向人多的地方运动，这种原因主要是从众心理导致的。在公共场所发生火灾时，从众因素对人员疏散产生较大影响，在构建疏散模型时，应当考虑从众因素，从众因素主要表现在疏散过程中的从众吸引力。从众吸引力与视野范围内人员密度有关，视野范围与火灾的大小和蔓延情况、障碍物、可见度有关，为了便于计算，取黑色方格为人所在位置，视野范围为 $\mathrm { r } \le 3$ 的区域。首先确定8个方向，如图3所示。视野范围划分8个领域，如图4所示。人员在疏散中密度反应是群体容易聚集的地方，而不能正确反映真正人员疏散中的人流的运动方向，因此加入人员疏散中的方向性，具体公式如下：

$$
P _ { f e l l o w } \left( i , j , n \right) = \frac { N _ { i , j , n } } { \sum _ { n = 1 } ^ { 8 } { N _ { i , j , n } } }
$$

其中： $N _ { i , j , n }$ 为第 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 个时间步，在中心元胞的视野范围内，(i,j)位置朝向 $\mathfrak { n }$ 方向的总人数，比较该元胞在第t个时间步与其上个时间步的移动位置，如果与该元胞方向相同，则取1，其它取0； $\textstyle \sum _ { n = 1 } ^ { 8 } N _ { i , j , n }$ 为中心元胞视野范围内的总人数，该公式表明朝某个方向运动的人数越多，则该位置从众吸引力越大。

![](images/b94123af2d12909a6651da2da5255a396c9f6501cedce7658ada22ff9f846cab.jpg)  
图3疏散方向标志

![](images/5c1565e5ca52ffc1034b5b337a4cb3c38f894a5f4d57bcbcb825226a29bf3c8c.jpg)  
图4疏散人员视野范围 $( \Gamma \leq 3 )$

基于以上转移影响因素，元胞的转移强度 $\mathrm { P ( i , j ) }$ 可以通过式(7)计算得出。

$\mathrm { P ( i , j ) } = \beta _ { 1 } P _ { d e c i d e } + \beta _ { 2 } P _ { f i r e } + \beta _ { 3 } P _ { r } + \beta _ { 4 } P _ { f } + \beta _ { 5 } P _ { f e l l o w }$ (7)其中 $\beta _ { 1 } \setminus \beta _ { 2 } \setminus \beta _ { 3 } \setminus \beta _ { 4 } \setminus \beta _ { 5 }$ 为各影响因素系数， $\beta _ { 1 } { + } \beta _ { 2 } { + } \beta _ { 3 } { + } \beta _ { 4 } { + } \beta _ { 5 } { = } 1$ 不同系数由疏散中哪些力占据主导位置，不同疏散环境下影响系数不同。

冲突避让原则。人员在疏散过程中存在多人同时竞争一个目标点的情况，人员竞争力值越大，越容易成功到达该位置。当转移强度计算完后，疏散人员选择下一个目标点时，可能存在多个元胞选择同一位置的现象，此时竞争力 $C _ { o m p }$ 将参与确定到达该位置的元胞。如果竞争力相差较大时，选择 $C _ { o m p }$ 值高的到达该位置，其它元胞选择次位置。如果竞争力相差在(0-0.2)之间时，采用随机选择的方式确定抢占该位置元胞，竞争力公式为

$$
= \left\{ \begin{array} { l l } { P . a g e \displaystyle _ { \int 1 8 } - 0 . 3 * P . c h i + ( 0 . 7 + 0 . 3 * P . g ) \medskip } \\ { \displaystyle \qquad 0 \leq \mathrm { P . a g e } \leq 2 2 } \\ { 4 0 \displaystyle _ { \big / P . a g e } - 0 . 3 * P . c h i + ( 0 . 7 + 0 . 3 * P . g ) \medskip } \\ { \displaystyle \qquad 2 2 < \mathrm { P . a g e } } \end{array} \right.
$$

$$
\begin{array} { r } { \mathrm { P . c h i } = \left\{ \begin{array} { l l } { ~ 1 } & { ~ \frac { 1 + \frac { 4 \pi } { 3 \gamma } \cdot \Pi \cdot \vec { f } \tilde { \mathcal { X } } } { \sqrt { 3 \gamma } \cdot \Pi \cdot \vec { f } \mathcal { X } } } \\ { ~ 0 } & { ~ \widehat { \mathcal { X } } \frac { \dag \mathbb { H } \div \frac { 4 \pi } { 3 \gamma } \cdot \Pi \cdot \vec { f } \tilde { \mathcal { X } } } { \sqrt { 3 \gamma } \cdot \Pi \cdot \vec { f } \mathcal { X } } } \end{array} \right. \qquad \mathrm { P . g } = \left\{ \begin{array} { l l } { ~ 1 } & { } \\ { ~ 0 } & { } \end{array} \right. } \end{array}
$$

其中：P.age 代表年龄，P.g为是性别，P.chi为是否携带小孩。该公式表明竞争力与年龄、是否携带小孩和性别有关。青年相对老年竞争力大，携带小孩的疏散人员减少0.3，男性相对女性竞争力更强。

# 1.2元胞疏散过程

研究人员在二维平面中的疏散情况，将疏散人员离开出口作为疏散过程的结束。疏散过程流程图，如图5所示。初始化主要设置疏散平面尺寸、出口、障碍物、火源位置和添加疏散人员。疏散时间为最后一个人员疏散完成时间，疏散时间 $\scriptstyle = \mathbf { t } \times$ 时间步长，t为疏散步数。

在位置更新之前，需要判断该元胞8个邻居是否被占据，计算未被占据的邻居元胞转移强度。元胞位置更新流程图，如图6所示。具体步骤如下：

a)确定每个元胞周围未被占据的邻居元胞转移强度，选择转移强度最大的作为目标位置；

b)当不只一人竞争同一位置时，计算参与竞争者的竞争力，竞争力最大者占据该位置;

c)判断人员是否到达出口，Y代表到达出口，疏散成功，N代表未到达出口，未疏散成功，需参加下一次更新；

d)更新每一个人的位置状态，重新计算每一个未成功疏散元胞的邻居元胞转移强度；

e)不断重复以上步骤，直到最后一个人疏散成功为止。

# 2 模型仿真

基于以上建立的模型，采用MATLAB 软件编写程序，对一个 $3 2 \mathrm { m } ^ { * } 4 0 \mathrm { m }$ 的超市火灾疏散过程进行模拟，并对实验结果进行了分析，超市平面图如图7所示。仿真初始时，随机分布疏散人员位置，火灾发生于 $( 8 \mathrm { m } , 2 8 \mathrm { m } )$ 位置，火灾中的燃烧材料为塑料。模型中 $\beta _ { 2 }$ 、 $\beta _ { 3 }$ 和 $\beta _ { 4 }$ 均为恒定值，分别取 $10 \%$ 、 $5 \%$ 、 $5 \%$ ，实验结果均为多次模拟取平均值所得。

超市的布局和火灾位置对疏散时间的影响。模型中超市上下货架面积很相近，货架摆放方向不同。在疏散过程中下方疏散比上方快，当下方出口没人时，上方出口仍有人，说明货物摆放朝向出口位置有利于疏散。对不同位置发生火灾时对人员疏散进行研究，发现当火灾发生不在人员行走主干道时对疏散影响较小，在超市中间左侧发生火灾比右侧影响疏散小。

仿真主要从出口宽度、疏散人数和从众心理对疏散时间的影响进行分析。图8为单出口宽度对疏散时间影响(初始设置400人，$\beta _ { 1 } = 5 0 \%$ ， $\beta _ { 5 } = 3 0 \%$ ，出口位置在中心)，图中数据表明疏散时间随着出口宽度越大，疏散时间越短，当出口宽度达到某一临界值时，增大出口对疏散时间的影响并不是很明显(将该临界值定义为出口阀值)；如果出口宽度未达到出口阀值时，疏散时间随出□

宽度减少呈线性增加。图9为双出口宽度对疏散时间的影响，图中数据表明现象与图8很相似，但在同宽度，分为两出□疏散时，双出口的疏散时间比单出口疏散时间都要小，说明双出口的疏散效率比单出口要高，当达到出口阀值时，增大出□对减少疏散时间效果不是很明显。图10双出口相隔距离对疏散时间的影响，图中数据表明达到疏散能力范围的出口之间相隔距离对疏散时间影响不大。因此，出口的设置应根据实际容纳人数，合理设置出口大小，如果在出口宽度固定时，应设置多个出口。

![](images/f82c1402cbfbc5b3213f628fa1e5bd42c3014872e0ee63e8ee20d44ac9490137.jpg)  
图5疏散过程流程图

![](images/de6a335e7ff74d59a330990c79e011fb797ecfa100322f868d5c459b7dbf0246.jpg)  
图6元胞每时间步更新流程图

00 8800 8 808 800 08 0。 8 08 0O 888888808808 08 0 8 008 8 0。 808808888088 808 08 08 08 08888008 8 88 8 8 8 888 。 O 0 000 88 8 8 00

![](images/6b02c65a2e0a72f8a152fe51c7a53fa78c66613fb9bcf25f6b21d9d1e828b232.jpg)  
图8单出口宽度对疏散时间影响

![](images/9e847d1a88ed35d2a2a48ec00547bdb3fa71b8226c7ffaf3f8f1eecf30d998ed.jpg)  
图9双出口宽度对疏散时间影响

图11为火灾环境下疏散人数对疏散时间的影响(初始设置双出口宽度 $3 \mathrm { m } ,$ ，疏散时间随人数呈线性增加。当人数在350\~400之间时，疏散时间的变化增加较慢，400人以后疏散时间增加较快，表明该点是疏散拥堵与否的临界点。如果超过该点人数，疏散比较缓慢，疏散时间增加较快。因此，确定场所的最佳人流量对疏散效率的提高有重大意义。图12为从众系数对疏散时间的影响，当完全没有从众行为时，疏散时间较长，在0.3之前疏散时间随着从众系数的增大而逐渐减小，由于部分人对疏散环境不太熟悉，选择跟随人群疏散有利于疏散。当从众系数达到0.3时，疏散时间最短，随后疏散时间随着从众系数增加而逐渐增大，由于大多数疏散人员选择盲目跟随疏散，导致某些位置产生拥堵和出口利用率降低，影响疏散效率。因此，在对疏散环境不是很熟悉的情况下，适当的从众行为有利于疏散，而盲目从众将导致疏散时间延长。

![](images/76a3b883597195184b4b3ef6e78598c2bad3519e64f804589a9b8ab03f1cefa1.jpg)  
图7超市布局平面图及20s时人员疏散图  
图10双出口相隔距离对疏散时间影响

![](images/5402ee726df75349fb064f2bd57eb761bdcce1d8e398d4c44760d652ef5a87fb.jpg)  
图11疏散人数对疏散时间的影响

![](images/b957bc59bead4abe40635d53ce61642fb77b987b9873fdda94488ecaa0015445.jpg)  
图12从众系数对疏散时间的影响  
图13Pathfinder模拟20s时人员疏散图

对模型进行合理性验证。初始元胞自动机模型设置( $\mathrm { \Delta } \beta _ { 1 } =$ $5 0 \%$ ， $\beta _ { 5 } = 3 0 \%$ ，出口为双出口，出口宽度 $3 \mathrm { m }$ ，疏散人数为400人)如图7所示，经过多次模拟，疏散时间均值为64.6s。采用疏散软件Pathfinder+FDS进行验证，火灾发生位于零食货架，燃烧热释放速率为 $5 0 0 \mathrm { k W / m ^ { 2 } }$ ，利用仿真疏散软件FDS建立火灾疏散模型，模拟超市火灾发展过程。火灾烟气向四周扩散，温度急剧上升，周围可见度下降，软件仿真的烟气比较真实且考虑因素较多，元胞自动机模型中火灾是随机扩散，实现人员躲避火灾行为。将FDS模型导入Pathfinder，选择 Steering运动模式进行仿真，仿真进行20s时如图13所示，疏散时间 $6 3 . 4 \mathrm { s } .$ 0软件仿真和模型模拟疏散时间相差不大，小1.2s可能是由于元胞自动机模型中火灾烟气对疏散产生影响，但火灾位置在左上角处对大部分疏散人员影响不大，可能导致疏散时间延迟一些，模型具有一定的可信性。

1出

# 3 结束语

基于元胞自动机模型建立了人与人、障碍物和火灾环境之间相互作用的群体火灾疏散模型，该模型比较全面的考虑了火灾过程中人员疏散影响因素，并对影响因素归一化处理，以元胞转移强度作为人员移动规则。通过仿真软件验证建立模型的合理性，元胞自动机模型和软件仿真疏散时间相近，疏散过程中在出口形成拱形疏散状态，说明模型具有一定的可信性，将模型用于对超市疏散过程进行模拟，可以得到以下结论：

a)超市货架对人员疏散产生阻碍，货架横向对着出口位置则更有利于疏散。火灾发生在主干道或者出口附近将导致人员疏散效率降低，人员绕行显现加重，超市可将易燃物品摆放在靠墙边或者相对靠后位置。

b)出口宽度设置应根据超市实际人流量，出口宽度存在一个阀值，且同等宽度情况下，应采用双出口。

c)超市行人疏散时间随疏散人数呈线性正相关，人数存在一个临界值，超过该值，疏散时间急剧增加，超市应根据规模合理控制人流量。

d)当环境熟悉程度不高或者过度紧张情况下，适当的从众心理有利于找到最优路径，提高疏散效率，但当从众心理过于严重或盲目跟从将导致出口利用率降低，不利于疏散。在疏散过程人员交汇处或者出口处设置引导人或指示标志，可以减少从众心理，帮助疏散人员找到合适的疏散路径和出口。

群体疏散过程是一个复杂的过程，对保障人员生命安全和减少财产损失有重大意义，今后将不断完善模型，其一使之适合更加复杂的场景，特别是多层疏散；其二将元胞自动机模型与其它模型进行融合，构建多种模型和思想基础上的充分考虑疏散行为、建筑结构和火灾环境的模型。

# 参考文献：

[1]Wang Shujie,Cao Shuchao,Wang Qiao,et al.Effect of exit locations on ants escaping a two-exit room stressed with repellent [J].Physica A: Statistical Mechanics & Its Applications,2016,457(4):239-254.   
[2]Guan Junbiao,Wang Kaihua,Chen Fangyue.Acellular automaton model for evacuation flow using game theory [J].Physica A: Statistical Mechanics & Its Applications,2016,461 (3): 655-661.   
[3]Han Yanbin,Liu Hong.Modified social force model based on information transmission toward crowd evacuation simulation [J].Physica A:Statistical Mechanics and its Applications,2016,469 (6): 499-509.   
[4]Qu Yunchao,Gao Ziyou,Xiao Yao,et al. Modeling the pedestrian's movement and simulating evacuation dynamics on stairs [J]. Safety Science, 2014,70 (70): 189-201.   
[5]Wan Jiahui, Sui Jie,Yu Hua.Research on evacuation in the subway station in China based on the Combined Social Force Model [J].Physica A: Statistical Mechanics & Its Applications,2014,394(4):33-46.   
[6]Guo Xiwei, Chen Jianqiao,Zheng Yaochen,et al.A heterogeneous lattice gas model for simulating pedestrian evacuation [J].Physica A: Statistical Mechanics& Its Applications,2012,391(3):582-592.   
[7]Yue Hao,Shao Chunfu,Guan Hongzhi,etal. Simulation of pedestrian evacuation flow with affected visual field using cellular automata [J].Acta Physica Sinica,2010,59(7): 4499-4507.   
[8]Hu Jun,You Lei.A cellular automata model of pedestrian evacuation in three-dimmensional space [J].Acta Physica Sinica,2014,63 (8): 65-74.   
[9] 李世威，王建强，刘应东．初始分布非均匀的行人流疏散仿真研究[J]. 计算机应用研究,2017,34(3):702-705.(Li Shiwei,Wang Jiangqiang,Liu Yindong.Simulation of pedestrian flow evacuation with asymmetrical pedestrian distribution [J].Application Research of Computer,2017,34 (3): 702-705.)   
[10]王茹，周磊，刘俊．基于改进蚁群算法的元胞自动机疏散模型研究[J]

中国安全科学学报,2018,28(1):38-43.(Wang Ru,Zhou Lei,Liu Jun. Study on cellular automation evacuation model based on improved ant

colony opumizauon aigoritnm [JJ. Cnina Saiety Science journaI, zU18,∠8 (1):38-43.)   
[11] Tsai PC,Chen C M, Chen YP.PSO-based evacuation simulation framework [C]//Proc of IEEE Congress on Evolutionary Computation. 2014:1944- 1950.   
[12]宋卫国，于彦飞，范维澄，等．一种考虑摩擦与排斥的人员疏散元胞自 动机模型[J]．中国科学：技术科学,2005,35(7):725-736.(SongWeiguo, Yu yanfei,Fan weicheng,etal.A person evacuation celluar automata model considering friction and repulsion [J]. Science in China Ser.E Engineering & Materials Science,2005,35(7):725-736.)   
[13]段鹏飞，熊盛武，李辉．面向大型场馆疏散的改进多蚁群算法[J].计 算机应用研究,2013,30 (2):357-359.(Duan Pengfei,Xiong Shengwu,Li Hui. Improved multiple ant colony algorithm for emergency evacuation in large building[J].Application Research of Computer,2013,30 (2):357- 359.)