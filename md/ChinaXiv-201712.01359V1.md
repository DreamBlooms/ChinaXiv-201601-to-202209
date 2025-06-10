# 基于无标度网络模型和传染病模型的舆论演化仿真研究

韩普1²王鹏¹  
1(南京邮电大学管理学院南京 210003)  
2(江苏省数据工程与知识服务重点实验室南京 210023)

摘要：【目的】精确地呈现网络社交中信息传播状态和传播过程，从而更深入理解网络信息的传播机制。【方法】在无标度网络模型和传染病模型基础上，加人可调整参数，构建改进的网络信息传播模型，并在NetLogo平台上进行舆情传播演化仿真。【结果】仿真实验结果表明：在信息传播过程中，不断变化的传播速率能够更好地描述网络信息传播；在集群度大的网络中对信息传播进行引导和控制的最佳时机是在传播速率增大阶段。【局限】模型对人群分类仍然不够精细。【结论】模型不仅能够在设定条件下模拟不同类型信息的传播过程，还可以为网络舆情监测、引导和控制提供支持。

关键词：无标度网络传染病模型 舆情传播分类号：TP311 G350DOI: 10.11925/infotech.2096-3467.2017.0503

# 1引言

随着计算机技术和通信技术的发展，信息的传播途径发生了巨大改变，这种改变主要表现在网络渠道已成为信息的主要传播方式。网络信息传播与传统条件下信息传播的主要不同是其传播载体变成了网络。传统社交主要局限于现实生活，往往是相识的人构成一个小世界网络。而现今人们的交往开始转向网络社交，小世界特性不再是主导，取而代之的是幂律分布特性。此外，网络条件下，信息的新奇性、权威性、娱乐性等使得不同类型信息具有不同的传播特征。本文在无标度网络[模型的基础上，构建包含传播者、未知者、接触者和抵抗者的社交网络结构，以改进传染病模型作为网络信息传播的动力模型，利用多主体仿真平台NetLogo，通过调整节点间信息传播概率、节点恢复概率和获得传播能力概率等参数，对网络信息传播过程进行仿真研究。

# 2网络信息传播模型

1998 年,Watts 和Storogatz[2提出WS小世界网络模型，开创了复杂网络研究的新纪元。复杂网络包括规则网络、随机网络、小世界网络和无标度网络[3]。小世界网络与随机网络度分布相似，但某些性质上与真实的网络并不完全相同。在研究现实社会中的各种网络时，有学者发现现实世界中的复杂系统大多具有幂律分布特性和无标度特征。Barabasi等[1]提出无标度网络模型，该模型包含增长和选优两个机制，增长机制强调复杂网络是一个开放系统，新的节点不断加入，节点总数不断增加；优选机制强调节点间增加边的概率依赖于已有的度，即遵循富者更富或马太效应。宋楠等4采用BA无标度网络模型刻画社会结构，基于NetLogo软件建立异质性多主体模型，模拟恐怖信息在网络中的传播过程和政府的干预措施，发现网络恐怖信息的传播速度主要取决于网络结构和个体的从众程度。沈贤[5通过分析现实世界中网络谣言的传播特性、传播方式和在无标度网络中仿真谣言的传播演化过程，发现要抑制谣言传播，就要减小网络的度和聚类系数，减小网络中用户的活跃度。余海林等采用BA无标度网络对群体性突发事件信息传播网络结构特性进行分析，发现群体成员之间的信息传播行为同时受择优和随机作用机制的影响。易成岐[在分析信息传播过程与传染病传播过程的异同后，引入正向感染及负向感染两个状态，提出一种新型社会网络的信息传播模型。黄宏程等[8针对经典传染病模型的不足,引入感染用户的衰减函数，提出适合社交网络的信息传播模型，并在真实的邮件网络中进行仿真。徐翔斌等9构建基于复杂网络理论改进的 SIR 网络信息传播模型，通过多Agent仿真研究网络度分布、网络平均度及初始激活节点对网络信息传播的影响。

目前，国内外学者在该领域取得了大量成果，但网络模型主要还是停留在 BA 网络阶段，这并不能精确刻画现实网络社交。此外，已有研究中网络传播模型主要针对网络拓扑结构不变的情况[10]，而在现实生活中，大部分网络拓扑结构都是动态的。随着网络时代的发展，社交网络不再局限于小世界网络，通过网络可以在全球范围建立社交。不仅如此，网络社交还具有诸多独特之处，如影响力比较大的节点更容易受到网民关注；社交网络结构随着时间而动态变化。鉴于此，本文在BA无标度网络模型和文献[11]基础上,随机赋予新加入节点不同吸引力来构建现实网络中人与人之间的关系，进而对网络条件下的信息传播模型进行仿真研究。

# 2.1 度分布

通常，度分布定义为：在 $t$ 时刻从网络中任意选择一个节点，假设 $P ( k , \ t )$ 表示节点的度数为 $k$ 的概率,$\{ P ( k , t ) , k { = } 0 , 1 , 2 ^ { \cdots } \}$ 被称为在 $t$ 时刻网络的度分布，如果极限存在 $\begin{array} { r } { P ( k ) = \operatorname* { l i m } _ { t  \infty } P ( k , t ) ( k = 0 , 1 , 2 \cdots ) } \end{array}$ ，则该网络具有稳定的度分布 $\{ P ( k ) , k { = } 0 , 1 , 2 ^ { \ldots } \}$ 0

# 2.2 网络演化模型

现实社会关系网络同时具有无标度特性与小世界特性，并且以无标度特性为主，即集聚系数大，平均路径小的特点。但在BA无标度网络模型中，当网络规模越大时，集聚系数越小，而平均路径却越大。考虑到实际社会中的小世界特性与网络社会中的无标度特性，在改进无标度网络模型时，加入内部边，从而使所构建的无标度网络具有小世界特性，并且在模型中赋予每个新加入点初始吸引力，这解决了原有模型中初始节点与原节点随机连接的不足。

# 2.3 模型构造算法

本文以文献[11]中无标度网络模型为基础，构建改进的网络信息传播模型。改进模型构造算法如下：

$\textcircled{1}$ 初始化 $m \_ { 0 }$ 个孤立节点构成网络模型，并给每个节点随机赋予初始吸引力α, $\scriptstyle { \alpha \geq 0 }$ 。

$\textcircled{2}$ 随机选择一个节点i，以择优概率 $\Pi ( k _ { i } , \alpha ) =$ $\frac { k _ { i } + \alpha } { \sum _ { j } ( k _ { j } + \alpha ) }$ 一选择另一个未连接的节点j，然后连接这两个节（204号点。其中 $k _ { i }$ 是节点 $i$ 的度数， $\alpha$ 为节点 $i$ 的吸引力。重复步骤$\textcircled{2} n$ 次，则模型中添加了 $n$ 条这样的边。

$\textcircled{3}$ 在已有基础上扩张网络，每次新加入一个节点，新加入节点连接到原网络的规则同步骤 $\textcircled{2}$ O

$\textcircled{4}$ 改变模型中节点间的连接状态，任意选择一个节点 $i _ { : }$ （在与该节点相连的边中任意选择一条边 $l _ { i j } ,$ 以择优概率$\Pi ( k _ { i } ^ { \prime } , \alpha )$ 选择另一个节点 $i ^ { \prime } ( i ^ { \prime } \neq i )$ 与节点 $j$ 相连接，并用新边线 $l _ { i ^ { \prime } j }$ 取代原来的边 $l _ { i j } ,$ 重复步骤 $\textcircled{4}$ ，即重新连接若干条边。

$\textcircled{5}$ 执行步骤 $\textcircled{3}$ 和步骤 $\textcircled{4}$ 共 $t$ 次，该模型演化成为一个具有总节点数为 $N ( t ) { = } m _ { 0 } { + } t$ 和总边数为 $t ( m { + } \ 1 )$ 的网络模型。

和已有模型不同的是，本文在已有算法上做如下改进:

(1）在步骤 $\textcircled{1}$ 中，给每个节点随机赋予初始吸引 力。在对每个节点赋予初始吸引力时有两种方案：按 分布概率：如随机取序列0.6，0.05，0.05，0.05，0.05, 0.05,0.05,0.05,0.05中之一(序列和为1)；所有节点吸 引力相同：如所有吸引力相等为0.1。

(2）在步骤 $\textcircled{3}$ 中，新加入节点并且接入网络后，需要更新所有节点择优概率Ⅱ；新加入节点与原有网络中的相连节点的个数发生改变，假设为 $\mathbf { \nabla } m$ 个 $\stackrel { \cdot } { m } \leqslant$ $m _ { 0 } { + } i )$ ，即改变模型中该节点与另一个节点的连接状态。

# 2.4 模型实现

为更加清楚直观地呈现网络结构，本文采用Matlab实现上述模型。图1给出了示例网络，设置初始节点数为10个，目标网络节点数为300个，初始化

# 54 数据分析与知识发现

状态下有8个节点之间有边连接。新加入节点与网络中10个节点相连，重新连接8条已存在的边，生成网络节点邻接矩阵，并将其导入Netlogo，使用Network扩展程序生成可视化网络，如图1所示。

![](images/c7de174eed9a4046ff58554b746109360d164be31a39e15515e73c7c8060650b.jpg)  
图1 网络规模为300的无标度网络

图2为网络规模为300和3000时，网络节点度分布图。

![](images/8f170c61e5e2eca01679e1276c7253976c4e059b3a89497ddec23ac3f2cbb1f0.jpg)  
图2网络节点为300和3000的度分布

从图2发现，模型中节点度的概率分布呈递减趋势，改进网络模型的度分布曲线图整体上满足幂律分布，符合无标度网络特性。而且节点数越多，网络幂律分布特性越明显。

# 3改进的信息传播模型

信息技术的发展导致人类社交方式发生巨大改变，社交网络也随之发生变化。尽管如此，信息传播方式仍然遵从一定的规律，即信息总是由已知者传递给未知者，这也是典型传染病模型的基本思想[12]。但经典传染病模型参数较少，不能充分体现传播个体间差异。因此，本文在经典传染病模型基础上加以改进，引入参数并增加人群分类，提出加入可调整参数的信息传播模型。

# 3.1 基本假设

针对上述模型，本文提出以下假设:

(1）根据人群对信息传播的反应及传播状态可将人群分为4类: $S ( t ) , \ I ( t ) , \ C ( t ) , \ R ( t ) .$ 。其中 $S ( t )$ 表示在$t$ 时刻从未接触过有关信息的人； $I ( t )$ 表示在 $t$ 时刻接触过有关信息并且传递信息的人，即传播者； $C ( t )$ 表示在$t$ 时刻接触过信息的人; $R ( t )$ 表示在 $t$ 时刻接触过信息并表示抵触的人；

(2）大部分个体仅传播一次信息;(3）所有个体构成改进的无标度网络;(4）系统在任何时刻，有 $S ( t ) \substack { + I ( t ) + C ( t ) + R ( t ) = A ( t ) }$ $A$ 为总人口数量;(5）系统初始状态只有极少部分个体为接触者，并且均为传播者。

# 3.2网络信息传播的特点

(1）初始状态下信息仅被极少数个体所接触，他们为传播者，其余所有个体为潜在传播者;(2）模型仅呈现个体接触信息后的响应，即传播、不传播、抵触;(3）个体接触到信息之后有两种行为：传播和不传播。传播即变为传播者，不传播即变为接触者，传播者中将来会有一部分变为抵触者，一部分变为潜在传播者；潜在传播者有可能再一次变为传播者，其余部分仍然为传播者。

# 3.3 信息传播规则

本文采用NetLogo平台实现信息传播模型。每个turtle 表示一个个体，个体有4种类型：

(1）susceptible(潜在者)：表示有潜在可能传播信息的人，包括未对信息知情和传播后有可能继续传播的人;(2)infected(传播者):在当前状态下，传播信息的人;(3)contacted(接触者):历史中接触过信息的人;(4)resistant(失去兴趣者)：传播过信息之后，失去兴趣的人。

在网络结构中，将人视为节点，定义节点间的交互规则如下:

(1）初始阶段，网络中有 $n$ 个节点，有 $n _ { - } 0$ 个节点为知情者，即接触到信息的人，设定其为红色，其余节点为未知者，颜色为绿色;(2)接触者以概率 $k$ 将信息传递给与之相连的节点，被传递者变为传播者，表现为红色，传递者传递之后变为接触者，颜色为蓝色;(3）传播者以概率 ${ \mu \times \varphi }$ 变为抵触者，颜色为橙色，以概率 $\mu \times ( 1 - \varphi )$ 变为潜在传播者，颜色恢复为绿色，他们在将来可能再次变为传播者。(4）不断循环，终止条件为全部节点均不为传递者，即系统中不存在传播者。

# 3.4 模型构建

根据模型基本假设[13-15]及个体交互规则，建立以下微分方程模型。

$$
\begin{array} { l } { \displaystyle { \left[ \frac { d S ( t ) } { d t } = - \lambda k S ( t ) I ( t ) + \mu ( 1 - \varphi ) I ( t ) \right. } } \\ { \displaystyle { \left. \begin{array} { l } { \displaystyle \frac { d I ( t ) } { d t } = \lambda k S ( t ) I ( t ) - \mu I ( t ) } \\ { \displaystyle \frac { d C ( t ) } { d t } = S ( t ) } \\ { \displaystyle \frac { d R ( t ) } { d t } = \mu \varphi S ( t ) } \end{array} \right] } } \end{array}
$$

微分方程中各参数表示如表1所示。

表1微分方程参数表  

<html><body><table><tr><td>微分方程</td><td>实际意义</td><td>NetLogo 中表示</td></tr><tr><td>k</td><td>潜在传播者与传播者接触， 接受并传播信息的概率</td><td>virus-spread-chance</td></tr><tr><td></td><td>网络模型中节点的度</td><td></td></tr><tr><td>μ</td><td>传播者变为抵触者和潜在传 播者的概率</td><td>recovery-chance</td></tr><tr><td></td><td>传播者转变为抵触者的概率 gain-resistant-chance</td><td></td></tr></table></body></html>

# 4实证研究

# 4.1 实验数据说明

本文选取2017年6月26日16点左右网上开始发酵的“徐玉玉案开庭案例事件"作为分析对象，观察从6月26日16点至6月27日16点时间段在新浪微博平台上的信息传播趋势以及关键传播者。需要说明的是，实验中使用的对照数据来自于新浪微舆情平台提供的《徐玉玉案开庭微博分析报告》，该数据集包含5532条新浪微博信息。

# 4.2 模型检验

首先抽取事件传播的关键用户以及关系网络，如“中国新闻网”、“央视新闻”、“新京报”、“北京热门搜罗"等54个核心传播媒体和机构，将各机构之间的关系网络用邻接矩阵表示，然后导入NetLogo，该事件被新闻媒体认定为敏感信息，因此系统里将传播概率 $\mu$ 设置为 $3 5 \%$ ，观察信息模拟传播状态，如图3所示。

![](images/2cff3df8cbc6926e98ad437a5a69a846f585e65bcb0660da61bc0b7798e1db3e.jpg)  
图3“徐玉玉案开庭案例事件"传播趋势模拟图

其中，时间单位默认为 NetLogo平台时间单位tick。在82tick时，传播数量占比为 $12 \%$ ，之后传播趋势开始快速增大，126tick时传播数量占比达到峰值$83 \%$ ，之后开始下降，在190tick时占比为 $2 9 \%$ ，之后下降趋势开始变缓。图4是真实的事件传播趋势，数

据来自新浪微舆情。

图4中每隔4个小时记录一次数据，其中横坐标真实时间从16时开始，晚上及次日凌晨是休息时间，因此信息大范围传播时间是27日凌晨4点以后。27日8点转发量达到163，所占比例为 $1 3 . 5 \%$ ，10点转发量达到峰值1072，占比 $89 . 3 \%$ 。之后开始下降，至12时转发量下降到392，占比为 $3 2 . 7 \%$ 。通过与模拟趋势图对比，除了时间上有差异，传播趋势几乎一致，转发量占比也很接近。考虑到时间因素与人们作息有关，该模型并没有加入这一因素。总体上该模型能够相对准确地模拟网络信息的传播趋势。

![](images/f3e900c3a5648702625cd3abdde5ff418c8b03975bb0da2e845205438c4000ea.jpg)  
图4“徐玉玉案开庭案例事件"传播趋势真实图

# 5模型研究与解释

为更准确地呈现真实网络中的信息传播特征与过程，现以两个不同参数的网络对模型进行研究和解释。其中，网络A，从参数 $\dot { \mu }$ 不变和可变以及有无外界触发对模型进行验证；网络B，解释触发对模型的影响，以新浪微博为例，验证模型的仿真效果。网络A和网络B的具体参数如表2所示。

表2两个网络参数对照表(时间单位:tick)  

<html><body><table><tr><td>参数</td><td>网络A</td><td>网络B</td></tr><tr><td>初始孤立节点个数</td><td>10</td><td>8</td></tr><tr><td>目标网络节点个数</td><td>1000</td><td>2000</td></tr><tr><td>初始化网络选择连接点数</td><td>10</td><td>8</td></tr><tr><td>新加入节点时与网络中连接的节点个数</td><td>3</td><td>10</td></tr><tr><td>初始节点个数</td><td>3</td><td>2</td></tr><tr><td>重新连接边数</td><td>4</td><td>10</td></tr><tr><td>Gain-resistant-chance(变为抵触者概率)</td><td>8%</td><td>8%</td></tr><tr><td>Virus-spread-chance(传播概率)</td><td>2%</td><td>2%</td></tr><tr><td>Recovery-chance(传播者变为抵触者和潜在传 播者的概率)</td><td>3%</td><td>3%</td></tr></table></body></html>

# 5.1 网络A

网络A的演化过程如图5所示。

![](images/ebd57edaacba6214b0641d70dda5e09112bc796d1ad8d56e58073a4971351156.jpg)  
图5 网络A系统演化图I

在图5中 susceptible、infected、contacted 和 resistant分别表示潜在传播者 $( S )$ 、传播者 $( I )$ 、接触者(C)和抵触者 $( R )$ ，后文以表示潜在传播者、传播者、接触者和抵触者，曲线表示该时刻该人群占总人数的百分比。在演化过程中发现, $C$ 占比在前10ticks-70ticks里迅速增加，增加趋势减缓；在标记1处， $I$ 占比并没有直接达到峰值，而是达到一定值然后起伏波动，后又上升达到最大值，如标记2处；此后在一段时间内上下波动，但在标记2附近区域总体呈下降趋势。在 $C$ 比例接近1时，即该网络内绝大部分个体已经接触到信息，此时 $I$ 曲线并不在上升状态，而是在下降状态。如标记2-3。标记3处, $R$ 曲线与 $I$ 曲线相交，两者数量相等，之后 $s$ 曲线趋于平缓且有上升趋势，如标记3-5, $R$ 曲线缓慢上升，且上升趋势逐渐放缓，在现实中可解释为：在信息传播过程中，随着信息爆发式蔓延后，对信息不再感兴趣的人逐渐增多，最终达到稳定状态，同时潜在传播者有平缓上升趋势。

图5演化过程中参数值一直没有变化，这与真实的情况并不相符。正常情况下，第一次接触信息的人发现很多人都关注并传播信息时，很可能也会加入传播者队伍；同时，当很多人都对信息冷淡的时候，接触到信息的人也很可能不再关注，文献[16]将这一现象称为微博传播的衰减效应，并给出衰减方程，但并没有指出微博传播的增益效应。通过对比可知, $\mu$ 的变化与传播者比例的变化呈同方向，其中 $\mu$ 表示微博传播概率。此时，系统演化如图6所示。

与图5对比，在 $I$ 占比第一次急剧增加的阶段(图5标记1处和图6标记1之前)，图6增加幅度明显高于图5，这更加符合现实情况。“徐玉玉案开庭案例事件"微博的转发趋势如图7(数据来自新浪微舆情)所示。

![](images/86434d6ad0debbb1e53ef6751200a05f0a146be1c2f5e0d25d4623f4ac80badd.jpg)  
图6网络A系统演化图Ⅱ

![](images/469cad46bdfa304493436e6e1d5a78911519373a0035fc05553a54bdc59a4715.jpg)  
图7“徐玉玉案开庭案例事件”微博转发趋势图

图7标记1和2分别对应图6的标记1和2。对于这种传播速率呈指数级增长的信息，即敏感信息，此类信息是人们比较关注的民情民生、娱乐八卦信息等。通常人们对这类信息的传播是不理智的，大部分人通过转发让更多人看到信息或者分享观点，但同时也给网络舆情控制增加了困难。

图6中标记1处， $I$ 占比达到峰值，几番波动然后大幅度下降，在1-2阶段 $\mu$ 逐渐减小。在标记2处， $I$ 和 $R$ 占比相同， $R$ 仍然缓慢上升,1继续下降，达到谷底，此时信息传播概率突然增大，潜在传播者S受到影响转变为传播者，信息热度又一次攀上高峰，如标记3处，但峰值低于标记1处，因为系统设定总人数不变,I来源主要是 $S _ { ; }$ 而 $s$ 不可能全部变为 $I _ { \circ }$ 达到峰值之后，即使传播概率 $\mu$ 不变, $I$ 也会降低，因为始终有一部分I转变为抵触者 $R , \mu$ 随着 $I$ 下降而变小。从标记1、3和5来看,即使信息传播概率变大， $I$ 比例的峰值也不会大于前一个峰值，因为 $I$ 会转变为 $S$ 和 $R , R$ 不会减少，因此即使未来 $S$ 全部转变为 $I ,$ 也达不到前一个峰值。现实中也存在信息热度高于之前的情况，因为现实中涉及到信息传播的网络结构是动态的。系统继续演进，如图8所示。

![](images/c74a39be66c71d27be1294f0ea802f37c18b890be7b5e3f215c332eb4618e49d.jpg)  
图8网络A系统持续演化图

随着时间推进，网络中所有人都接触到了信息(图8中C指向线） $\scriptstyle \cdot { I }$ 占比继续呈现下降趋势，但逐渐放缓，偶尔会向上波动，最终 $I$ 为0，网络中不再有传播者，系统停止。此时系统中除了接触者 $C$ 只有 $R$ 和 $s$ 两种人群，即只有具有潜在传播信息的人和对信息完全失去兴趣的人。从图8可知，虽然潜在传播者 $s$ 有上升趋势，但由于传播者I数量极少，他们虽然有传播信息的可能性，但信息源不足，无法传播。同时， $s$ 的来源之一也是I，因此，系统终止是可以理解的。

在真实网络中，热门信息的热度并不是经过一次大爆发式传播之后就随即慢慢下降，而是往往经新闻媒体再次报道，在传播过程中突然会出现信息热度大大增加。为了模拟这一现象，本文增加一个临时事件,该事件使得当前传播信息者对信息进行更大范围的传播，从而使网络内更多个体接触到信息。此类事件往往是人为触发的，并且这与之前提到的信息传播概率u增大是不一样的，这个临时事件是来自网络外部的，信息传播幅度增大是被动的，而 $\mu$ 的增大来自网络内部，是系统的主动行为。同样，如果没有外部的触发，在正常情况下1呈现逐渐下降趋势。系统仿真效果如图9所示。

![](images/86cefa327458e3801645490f9340dda1394a05e9eb88a32a331fa23b878f52a8.jpg)  
图9媒体参与的系统演化图

在媒体第二次参与时，传播者数量并没有持续多久。在媒体第三次参与时，传播者数量持续了一段时间，然后逐渐下降。这表明，媒体参与对信息传播造成的影响与传播者占比有关，传播者占比越低，媒体影响越小。媒体参与对信息传播是增益影响。从控制舆情发展视角，若想利用媒体对网络舆情进行正确引导，最佳时机就是传播者比例最大的时候，当然，如果能够提前觉察到舆情发展，在传播者占比急剧增加阶段控制传播不失是一个很好的方案。

# 5.2 网络B

从概率角度来说，网络规模越大，个体误差带来的影响会越小。当网络初始规模为10，最终规模为2000时，网络度分布如图10所示。

显然，随着网络规模变大，度分布越呈现出幂律分布的特性。此时系统演化状态如图11所示(这里假定传播概率 $\mu$ 不变)。

![](images/e5c812f5f3ba046089cf0544ac5be8343385e63e73de152655b80ae8bb552223.jpg)  
图10 网络B度分布图

![](images/8ee7a6276b9ee583c5db5aeb929de75c08b26b97293b48b2ffeaaf9a33d771b1.jpg)  
图11 网络B系统演化图

在图11箭头指向处，tick为 $3 9 . 9 \%$ ，此时 $I$ 达到峰值，增加速率接近 $\ 0 , I$ 占比为 $8 4 . 7 \%$ ；按照当前状态发展， $I$ 应该会缓慢下降，但如果此时给系统一个人为触发， $I$ 比例会突然增大，甚至比之前的峰值还要高出$3 \%$ ，这非常符合现实情况。相反，如果这时对信息传播进行控制，效果也很明显，这也验证了前文中的假设，

如果在信息热度比较低时触发，效果不会这么明显。如图12所示，在 $I$ 比较小的时候，也就是信息热度较低时触发系统，其变化随着信息热度下降而逐渐降低，甚至消失。

![](images/b62c65f3c5ca9050da7f4d78cdf1cebd99ec77d404350c902e19452ef8ed66bd.jpg)  
图12信息热度不同时获得相同触发的网络状态

在该模型中，所有变量在传播过程中均遵循同一规律。 $I$ 数值先增大再减小，而且该系统演变是有原始起点的，也就是演变从事件最初的源头开始。但在现实生活中，在观察某事件的热度时，往往从某个时间点开始，因为此时事件的热度已经足够大到引起人们关注，但该时间点往往不是事件的起点。

# 5.3 网络A与网络B对比分析

网络A和网络B具体参数见表2。假定传播概率$\mu$ 始终不变，并且信息传播过程没有媒体参与。网络A和B的演变趋势如图13和图14所示。

![](images/30080d95003f97821d0d0add1ffa936c843ea49241b4652d4f468d87938af3c8.jpg)  
图13 网络A演变趋势图

![](images/2198bc90d8da7125c06a89a2f38d398f4b1d9c05a7a5a152a82aa56cdfb3820c.jpg)  
图14 网络B演变趋势图

图13中，网络A的 $I$ 占比在108tick到达峰值$57 \%$ ，图14中网络B的 $I$ 占比在35tick达峰值 $86 \%$ ，约为A的1.5倍，说明网络节点间的紧密程度能够加快信息的传播速度，同时也更能够扩大信息传播范围。在909tick时，网络A和网络B中I的比例分别为 $6 . 5 \%$ 和 $9 . 5 \%$ ，网络B约为网络A的1.5倍，说明随着信息传播， $I$ 的数量不论怎样变化，仍然跟网络集群度有很大关联。在909tick时，网络A和网络B中 $s$ 的比例分别为 $41 \%$ 和 $10 \%$ 。由于网络集群度的关系，网络B在 35tick时有 $86 \%$ 的传播者，潜在传播者迅速减至$10 \%$ 左右。随着系统演变，虽然有部分传播者变为潜在传播者，但由于系统中设定的概率很低，因此大量其余传播者变为抵触者，最终抵触者比例很高。而网络A 中，由于网络集群度较低, $I$ 占比的峰值为 $57 \%$ ，而此时信息传播时间较短， $s$ 变为 $I$ 的概率低于 $I$ 变为 $s$ 的概率。在系统演变到909tick时，S比例为 $41 \%$ ，而网络B中 $s$ 比例仅为 $10 \%$ 。简而言之，随着信息传播时间的持续，网络中 $s$ 与 $R$ 的比例与 $I$ 第一次达到的峰值有很大关联，峰值越高，最终 $s$ 的比例越低, $R$ 的比例越高。

# 6结语

在系统演化过程中，所有主体的行为是同时发生并且相互独立的。NetLogo平台可以对每一个主体Agent都赋予行为，因此更加适合对真实社会网络演化过程进行系统仿真。本文提出的仿真模型能够在一定假设前提下模拟不同类型信息的传播状态和传播过程。仿真模拟发现，在传播过程中，动态的传播速率能够更好地描述网络信息传播。通过对两种集群度不同的网络进行对比，发现在集群度大的网络中，信息传播得更快，传播范围也更大，并且最终对信息抵触的人也更多。从舆情控制视角，对信息传播进行引导和管控的最佳时机是在传播速率增大的阶段。今后将继续改进无标度网络生成算法，充分融人社会化媒体中社交网络特征；在模型中继续增加人群分类，使其更加符合现实社交网络，从而更全面地挖掘舆情传播特征，以便更好地实现网络舆情引导。

# 参考文献：

[1]Barabasi A,Albert R.Emergence of Scaling in Random Networks[J]. Science,1999,286(5439): 509-512.   
[2]Watts D J, Strogatz S H. Collective Dynamics of‘SmallWorld' Networks[J]. Nature,1998,393(6684): 440-442.   
[3]Chen P Y,Chen K C. Information Epidemics in Complex Networks with Opportunistic Links and Dynamic Topology [C]// Proceedings of the 2010 IEEE Global Telecommunications Conference (GLOBECOM).2010: 1-6.   
[4]宋楠，付举磊，鲍勤，等．基于无标度网络的恐怖信息传 播与最优应对策略[J]．系统工程理论与实践，2015,35(3): 630-640.(Song Nan，Fu Julei，Bao Qin，et al.Cyber Terrorism Spreading and Optimal Intervention Policies Based on a Scale-free Network[J]. Systems Engineering—Theory & Practice,2015,35(3): 630-640.)   
[5]沈贤．基于无标度网络的谣言传播模型与控制策略的研究 [D]．南京：南京邮电大学，2013．(Shen Xian．The Propagation and Control Strategies of Rumors in Scale-free Network[D]. Nanjing: Nanjing University of Postsand Telecommunications,2013.）   
[6]余海林，庄亚明．具有无标度特性的群体性突发事件信息 传播网络模型及仿真[J].情报科学，2015，32(11):90-94. (Yu Hailin, Zhuang Yaming.Modeling and Simulating of the Information Propagation Network of Mass Unexpected Incidents with Scale-free Characteristic [J].Information Science,2015,32(11): 90-94.)   
[7]易成岐．社会网络的信息传播机制及控制方法研究[D]．哈 尔滨：哈尔滨理工大学，2016.(Yi Chengqi．Research on Mechanismsof Information Propagation and Control Strategies in Social Networks[D].Harbin: Harbin University of Science and Technology,2016.)   
[8]黄宏程，蒋艾玲，胡敏．基于社交网络的信息传播模型分 析[J]．计算机应用研究，2016，33(9):2738-2742.(Huang Hongcheng, Jiang Ailing,Hu Min. Analysis of Information Diffusion Model on Social Network[J].Application Research of Computers, 2016,33(9): 2738-2742.)   
[9]徐翔斌，李恒，王坤.Web2.0 网络信息传播影响机制研究 [J].情报科学,2015,33(8):44-49.(Xu Xiangbin,Li Heng, Wang Kun. Research on the Influence Mechanism of Information Spreading in Web2.0 Network[J]. Information Science,2015,33(8): 44-49.)   
[10]孙立晟，何东之．改进无标度网络模型研究[J].电子设计 工程，2016,24(6):115-117.(Sun Lisheng,He Dongzhi. Research on Improved Scale-free NetworksModel[J]. International Electronic Elements,2016,24(6):115-117.)   
[11]李涛，刘启明．基于无标度网络的谣言传播模型研究[J]. 河北师范大学学报，2016，40(3):195-199.(Li Tao,Liu Qiming.A Study of Rumors Spreading Model with on Scale-free Network[J]. Journal of Hebei Normal University, 2016,40(3): 195-199.)   
[12]姜启源，谢金星，叶俊.数学模型[M].第4版.北京：高等 教育出版社，2011.(Jiang Qiyuan，Xie Jinxing，Ye Jun. Mathematical Model [M]. The 4th Edition.Beijing: Higher Education Press,2011.)   
[13]魏静，朱恒民，宋瑞晓，等．个体视角下的网络舆情传递 链路预测分析[J]．现代图书情报技术，2016(1):55-64.(Wei Jing，Zhu Hengmin,Song Ruixiao,et al.Link Prediction Analysis of Internet Public Opinion Transfer from the Individual Perspective[J]. New Technology of Library and Information Service,2016(1): 55-64.)   
[14] 朱恒民，刘凯，卢子芳．媒体作用下互联网舆情话题传播 模型研究[J].现代图书情报技术，2013(3)：45-50.(Zhu Hengmin,Liu Kai,Lu Zifang. Study on Topic Propagation Model of Internet Public Opinion Under the Influence of the Media[J]. New Technology of Library and Information Service,2013(3):45-50.)   
[15]马知恩．传染病动力学的数学建模与研究[M]．北京：科学 出版社，2004．(Ma Zhien．Mathematical Modeling and Research on Dynamics of Infectious Diseases[M]. Beijing: Science Press,2004.）   
[16] 沈乾，马宁，黄远，等．微博传播波的函数解析实证研究 [J]．数学的实践与认识,2014,44(21):143-151.(Shen Qian, Ma Ning,Huang Yuan,et al. Empirical Study on Microblog ForwardingWaveBasedonFunctionalAnalysis[J]. Mathematics in Practice and Theory,2014,44(21): 143-151.)   
[17] 刘咏梅，彭琳，赵振军．基于小世界网络的微博谣言传播 演进研究[J]．复杂系统与复杂性科学，2014，11(4)：54-60. (Liu Yongmei, Peng Lin, Zhao Zhenjun. The Evolution of Rumor Spread on Micrblog Based on Small-World Network [J]. Complex Systems and Complexity Science,2014,11(4): 54-60.)

# 作者贡献声明：

韩普：提出研究思路，设计研究方案，论文撰写、修改以及最终版本修订;  
王鹏：方法设计与仿真实现，论文撰写。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

[1] 韩普.network.m.基于Matlab 的模型生成算法.  
[2]韩普.infotransport.txt.基于NetLogo 的信息传播仿真实验.

收稿日期:2017-05-31   
收修改稿日期:2017-08-24

支撑数据由作者自存储,E-mail:1961345450@qq.com

# Simulating Public Opinion Evolution with Scale-Free Network Model and Infectious Disease Model

Han Pu1,²Wang Pengl 1 (School of Management, Nanjing University of Posts & Telecommunications, Nanjing 210o03, China) ² (Jiangsu Key Laboratory of Data Engineering and Knowledge Service, Nanjing 210023, China)

Abstract:[Objective]Thisarticle tries to explore the information disseminationstatusand process inthe social network systems,aiming to reveal theonline information evolutionmechanism.[Methods]First,weadded adjustable parameters to the scale-free network model and the infectious disease model.Then, we executed the modified model on the NetLogo platform to simulate the evolution of public opinion. [Results] We found thatthe changing propagation rate was abetter wayto describe the online information dissemination process.We could efectively guide and control the information flow in alarge network at the stage with increasing propagation rate.[Limitations] We need beter classification method for the target population.[Conclusions] The proposed model could simulate information evolution and then support the online public opinion monitoring, guidance and control.

Keywords: Scale-Free Network Infectious Disease Model Public Opinion Communication