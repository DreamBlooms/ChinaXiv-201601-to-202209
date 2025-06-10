# 基于公交网络的车载群智感知方法及其优化

吴振钰，吴茂强，叶东东，余荣，何昭水(广东工业大学 自动化学院，广州 510006)

摘要：公交车具有固定的行驶路线和发车周期、统一的车载设备标准、低隐私泄露风险等特性。根据公交车的特性，设计了一个基于公交网络的车载群智感知系统，系统中的数据中心通过公交网络中的公交车来采集城市数据，以满足数据用户的需求；随后研究系统中的任务分配问题和数据交易问题。基于贪婪算法设计优化任务分配策略以最小化系统的数据采集能耗成本，和根据博弈论设计最优数据交易策略以最大化系统的经济效益。最后通过仿真，验证了提出的策略的有效性和优越性。

关键词：车载群智感知；公交车；数据采集；数据交易；斯坦克尔伯格博弈中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2017.10.1008

# Strategy and optimization for public bus network-based vehicular crowd sensing

Wu Zhenquan, Wu Maoqiang†, Ye Dongdong,Yu Rong,He Zhaoshui (School ofAutomation Guangdong University of Technology,Guangzhou 51ooo6,China

Abstract: Public buses haveunique characteristics,such as fixed moving paths and time periods,uniform vehicular device standards,low risk of privacy exposure.This paper designed a public bus network-based vehicular crowd sensing system, considering thecharacteristicsofpublicbuses.Inthesystem,datacenterutilizespublicbusesofthebus network tocollecturban data which isrequired bydatausers.Italsostudiedthetask asignmentproblemandthedata trading problem inthe system. This paper proposed an optimized task asignment strategy based on a greedy algorithm to minimize the system energy consumptionofdatacollction,and proposed anoptimal data trading strategy basedongame theory to maximizethe system utility. Finally, numerical results demonstrate the effectiveness of proposed strategies.

Key Words: vehicular crowd sensing; public buses; data collection; data trading; Stakelberg game

# 0 引言

移动群智感知(Mobile Crowed Sensing)是一种新兴的城市数据采集方法，利用城市里广泛分布的智能移动设备采集城市数据，从而使得城市数据采集的范围更广，方式更灵活[1]。随着无线通信和传感器技术的发展，如今手机、平板、车载设备等智能移动设备集成了越来越多的传感器，拥有越来越强大的计算、存储、通信功能。移动群智感知通过激励这些用户，让他们利用自己的智能移动设备采集和上传周围的环境数据，从而满足城市数据采集的需求[2.3]。

车载群智感知(VehicularCrowdSensing)是移动群智感知的一个典型场景。随着车联网的发展，车辆上装载了大量的车载智能设备，包括传感器、处理器、通信装置等。车感群智感知通过激励车主,利用其车载设备来采集和上传车辆周围的城市数据[4]。因为车辆在城市环境中无处不在，而且车辆比普通设备用户的移动速度更快，所以车载群智感知比普通的移动群智感知覆盖范围更广，采集方式更加灵活[5.6]。

在现实运用中，车载群智感知往往利用私家车作为感知工具，但存在以下问题：

a)车载群智感知可能会泄露驾驶者的个人隐私信息，如GPS位置。驾驶者考虑到个人隐私问题往往不愿意提供完整的采集数据[7]。

b)不同牌子的汽车产自不同的厂商，没有统一的软件和硬件标准。因此它们的传感器无法采集统一格式的城市数据，这对后面的大数据处理带来了困难[8]。

c)汽车的行驶路径常常缺乏规律性，车载群智感知对感知车辆的选择需要预测汽车的行驶路径。行驶路径预测的准确度往往影响了车载群智感知的效果[9]。

为了克服以上缺陷，本文考虑将公交车引入车载群智感知网络中，从而充分利用公交车作为城市数据采集的有效工具。相比较其他汽车，公交车有以下特性：a)公交车属于城市公共服务，对于城市来说公交车没有特别的隐私信息需要隐藏，因此没有隐私泄露的风险；b)公交车一般有统一的软件和硬件的标准，它们可以装配统一的多种类的传感器，采集统一格式的城市数据；c在公交网络中，每辆公交车有固定的行驶路线和发车周期，这有利于找到合适的公交车完成数据采集任务。

基于这些特性，公交车比其他车载群智感知更适于做城市数据采集。而且，公交车的路线基本覆盖了城市的主要区域，可以保证城市主要区域的数据采集。

本文建立了一个基于公交网络的车载群智感知系统，包含数据中心和公交网络。一方面，数据中心把数据采集任务分配给公交网络中的公交车，利用公交车采集所需的城市数据。另一方面，数据中心通过数据交易把采集到的城市数据处理后发送给需要数据的数据用户，换取经济效益。为了实现上述这两方面的功能，本文分别研究数据中心的采集任务分配问题和城市数据交易问题。基于贪婪算法，本文提出了优化任务分配策略以最小化公交车采集数据的能耗成本。再者，基于博弈论，本文提出了最优数据交易策略，使得数据中心在数据交易中获取最大的经济效益，同时满足数据用户的需求。实验结果证明本文提出的策略的有效性能。

# 1 公交车载群智感知系统

# 1.1 系统的组成成分

图1展示了本文提出的基于公交网络的车载群智感知系统架构。公交车载群智感知系统由以下部分组成：

a)数据用户。需要各种城市数据来进行数据分析，并基于分析结果进行决策，以提高城市服务质量。

b)数据中心。给公交网络的公交车分配城市数据采集任务；对收集的城市数据进行整合、清洗、处理；把处理好的数据交易给数据用户以获取经济收益。

c)公交车。根据数据中心分配的任务，利用车载智能设备进行城市数据感知。并把感知的数据上传到数据中心。

![](images/241911aeb0105a16e7b258c364828c778596345474355dabfb886d8f744f78cf.jpg)  
图1基于公交网络的车载群智感知系统结构

数据中心的功能有数据交易，任务分配，数据处理。具体功能如下：

a)数据交易。数据中心与数据用户协商数据交易的价钱和所要求的数据需求，并根据数据需求产生相应的数据采集任务，包含目标区域的位置和采集的数据量。

b)任务分配。数据中心根据公交车的移动线路和发车时间选取合适的公交车对指定的数据目标区域执行采集任务，并尽可能地减少采集能耗成本。

c数据处理。数据中心对公交车上传的城市数据进行预处理，并把处理后的数据发送给数据用户，以换取激励。

公交车是数据采集任务的执行者。每一辆公交车都装载了统一的传感器和计算设备、通信设备。这些设备使得公交车有足够的感知、计算、存储、通信能力，对目标区域进行数据采集，并通过无线网络把采集的数据及时上传。通过公交车，可以对目标区域感知和采集多种类型的数据，包括交通数据（如GPS 数据、行驶速度数据）、环境数据（如温湿度数据、空气质量数据）和多媒体数据（如图像、视频数据)。

# 1.2系统的工作流程

公交群智感知系统是采用周期性运行机制。在每一个周期里，有不同的数据用户希望通过系统采集自己想要的数据。通过协商，数据中心和数据用户确定了双方满意的激励和数据需求。接着数据中心根据数据需求产生相应的数据采集任务。数据采集任务包含所要的目标区域、采集时间、数据类型和数据量。数据中心从公交网络中获取这个周期城市里的公交车实时位置和状态。通过该公交车的位置、速度等状态，数据中心预测公交车是否能在周期内到达数据目标区域，以及能够在目标区域感知的数据量与消耗的感知能量。数据中心综合考虑以上因素，选择最合适的公交车执行该目标区域的数据采集任务，并把数据采集任务通过无线网络发送给被选择的公交车。

公交车接到数据采集任务后，沿着自己的移动线路到达数据目标区域附近。只有目标数据区域在自己传感器的感知距离内，公交车才能感知到有效的数据。公交车根据收到的数据采集任务，对目标区域采集指定的数据类型和足够的数据量。通过智能交通网络，公交车把收集到的数据及时传输到数据中心，完成自己在这个周期内的采集任务。

数据中心对所有公交车传输上来的数据进行数据融合和数据处理，使得数据满足数据用户的格式要求。最后数据中心把处理后的数据分别传给数据用户，数据用户把协商好的激励发送给数据中心。这个周期的数据采集交易结束。

# 2 任务分配

采集任务分配是公交群智感知系统的一个重要功能。当数据需求确定时，数据中心需要把数据采集任务分配给合适的公交车去完成。不同公交车的移动路径不同，因此它们对各个目标区域所能采集到的数据量和采集需要消耗的能量也不一样。需要根据公交车的移动路径来选择合适的公交车以最小能耗来采集所需要的数据需求量。当采集任务分配结束，被选择的公交车将根据分配的数据采集任务，来感知指定的目标区域和完成数据采集任务。本文的目标寻找优化任务分配策略选择合适的公交车，从而以最小的能耗成本完成对目标区域的数据采集。

# 2.1问题描述

一个周期内有 $\textit { I }$ 辆公交车，第 $i$ 辆公交车的路径为$L _ { i } = \{ ( x _ { i } , y _ { i } ) \}$ ，其中 $( x _ { i } , y _ { i } )$ 是公交车的位置坐标。本文假设公交车的移动速度为 $\mathbf { \Phi } _ { \nu }$ ，公交车能按照常规的时间完成自己的行驶线路。为了简化问题，本文只考虑对一类城市数据进行采集。通过协商，数据中心和数据用户确定了双方满意的激励和数据任务需求。数据任务包含 $J$ 个目标区域和要求数据采集量为 $D$ u第 $j$ 个目标区域的坐标为 $( x _ { j } , y _ { j } )$ 。公交车路径与目标区域的最小距离为

$$
d _ { i } ^ { j } = \operatorname* { m i n } | | { ( x _ { i } , y _ { i } ) - ( x _ { j } , y _ { j } ) } | |
$$

由于公交车装载统一规格的传感器，所以所有公交车的数据采集能力相同，具有相同的数据采集速度 $\nu ^ { \prime }$ 和相同的感知距离 $R$ 。只有当目标区域在公交车的感知距离内，公交车才能对目标区域进行数据采集。因为公交车的采集能力相同，因此公交车对一个目标区域感知的数据量大小由目标区域在公交车的感知距离内停留的时间决定，即与公交车在采集过程中行驶的路径长度有关。设公交车 $i$ 在对目标区域 $j$ 感知过程中行驶的路径长度为 $l _ { i } ^ { j }$ ，则公交车 $i$ 对目标区域 $j$ 的数据采集量为

$$
D _ { i } ^ { j } = \nu ^ { \prime } \frac { l _ { i } ^ { j } } { \nu }
$$

由文献[10,11]可知，传感器采集的能耗与感知距离的平方成正比。在有效感知距离内，公交车离目标区域越远，则消耗更多的能量。由于公交车在感知的过程中公交车与目标区域的距离 $r _ { i } ^ { j }$ 不断变化，传感器所消耗的能量也随着不断变化。则公交车 $i$ 在对目标区域 $j$ 感知过程中的采集成本为

$$
C _ { i } ^ { j } = 2 \int _ { d _ { l } ^ { i } } ^ { R } c \Big ( r _ { i } ^ { j } \Big ) ^ { 2 }
$$

其中： $\mathbf { \Psi } _ { c }$ 是单位采集成本，不同类型的数据，需要的传感器的单位采集成本不一样。设定一个指示器 $T _ { i } ^ { j }$ ，其值代表对公交车$i$ 对目标区域 $j$ 的状态。当公交车 $i$ 被选择感知目标区域 $j$ 时，$T _ { i } ^ { j } = 1$ 。当公交车 $i$ 不需要感知目标区域 $j$ 时， $T _ { i } ^ { j } = 0$ 。所有$T _ { i } ^ { j } = 1$ 的集合为 $T _ { _ Y }$ 。所有 $T _ { i } ^ { j } = 0$ 的集合为 $T _ { n }$ 。

本文研究的优化任务分配方案是在满足采集数据的需求前提下，选择合适的公交车，从而使用最小的采集能耗成本完成数据采集任务。因此任务分配问题可以表示为

$$
\begin{array} { l } { { \displaystyle \operatorname* { m i n } _ { T _ { i } ^ { j } } \sum _ { T _ { i } ^ { j } \in T _ { y } } C _ { i } ^ { j } } } \\ { { \mathrm { s . t . } \quad \displaystyle \sum _ { T _ { i } ^ { j } \in T _ { y } } D _ { i } ^ { j } \geq D } } \end{array}
$$

$$
\sum _ { i \in I } T _ { i } ^ { j } \geq 1 , j \in J
$$

# 2.2分配策略

由式(4)可知，本文的目标是在所有目标区域都被采集，且满足数据采集的要求总量的条件下，选择合适的公交车，从而使得数据采集的总能耗最小。每辆公交车只能被选择一次，这是一个典型的0-1背包问题[]。0-1背包问题是一个NP完全问题，不一定能找到完美的求解方法[12]。利用迭代优化的思想，本文基于贪婪算法设计了一个优化任务分配策略。

具体的算法步骤如下：

a)初始化所有T=0，Tγ=。

b)根据公交车的移动轨迹，计算每一辆公交车对每一个目标区域的数据采集量 $D _ { i } ^ { j }$ 和能耗成本 $C _ { i } ^ { j }$ 。则公交车 $i$ 对目标区域j的单位数据采集能耗成本为ei=C /Di

c)对于每一个目标区域 $j \in J$ ，挑选 $e _ { i } ^ { j }$ 最小的公交车，使$T _ { i } ^ { j } = 1$ 。

d)如果 $\sum _ { T _ { i } ^ { j } \in T _ { y } } D _ { i } ^ { j } < D$ ，继续从 $T _ { n }$ 中挑选 $e _ { i } ^ { j }$ 最小的公交车 $i$ 对目标区域 $j$ 进行采集， $T _ { i } ^ { j } = 1$ ；如果 $e _ { i } ^ { j } = C _ { i } ^ { j } / D _ { i } ^ { j }$ ，则输出 $T _ { _ Y }$ 。

算法通过迭代优化，每一轮都挑选单位数据采集能耗成本最小的公交车分配任务。因此挑选出的公交车集合在在满足了数据采集中所有目标区域都被采集和数据采集总量达到要求总量的条件下，总能耗成本也近似最小。

# 3 数据交易

在公交群智感知系统的工作中，数据交易是一个需要解决的问题。因为公交群智感知系统在一个周期内感知的数据能力有限，不能无限制地满足所有数据用户的数据需求。当数据用户要求的采集量增加，公交群智感知系统的数据采集成本和数据处理成本也会随之增加。因此数据中心会根据采集成本来调整价格并发送给每个数据用户。每个数据用户根据数据中心提供的价格衡量自己的收益，并调整自己要求的采集量。最后数据中心和每个数据用户以双方满意的价格和采集量达成数据交易。

本文用斯坦克尔伯格博弈(Stackelberg game)来解决数据交易的问题。斯坦克尔伯格博弈是一个特殊的非合作博弈模型，在现实中应用广泛。斯坦克尔伯格博弈中，存在着两方参与者，分别是主方参与者和从方参与者。假设所有的参与者都是理性的，自私的，追求自己的利益最大化。在斯坦克尔伯格博弈中，当主方参与者作出决策时，所有从方参与者都会观察主方的决策，并根据主方的决策选择对自己最优的决策，即从方参与者总会作出针对主方参与者的决策的最优反映[13-14]。因此如果主方参与者选择决策使到自己利益最大化时，博弈就达到了斯坦克尔伯格均衡(Stackelbergequilibrium,SE)。在斯坦克尔伯格博弈里，所有人都达到了最佳收益，没有人再愿意改变自己的决策。

因为本文的目的是使得数据中心的利益最大化，同时数据用户也可以得到相应的最优效益。这问题正符合斯坦克尔伯格博弈模型。因此，本文用斯坦克尔伯格博弈为数据中心和数据用户分别设计了他们的交易策略。在本文的博弈中，主方参与者是数据中心，其策略是提供给数据用户的交易价格；而从方参与者是数据用户，其策略是各自提供给数据中心的数据需求量；所有参与者都是理性的，自私的，追求最优的决策使得自己的利益最大化；当数据中心的利益达到最大时，博弈将达到了斯坦克尔伯格均衡，双方都不会再愿意改变自己的决策。

# 3.1问题描述

假设一个周期存在 $K$ 个数据用户，第 $k$ 个用户的数据需求量是 $D _ { \boldsymbol { k } }$ ，出的价格是 $P _ { \boldsymbol { k } }$ 。数据分析的精度随着数据量的增长而提高，但是当数据量增长到一定程度，数据分析精度的提高将减缓[15]。数据中心的收益取决于数据分析的精度，即$a _ { k } \mathbb { I b } \big ( D _ { k } + 1 \big )$ ，其中 $a _ { \scriptscriptstyle k }$ 是收益的参数。不同的数据用户的 $a _ { \scriptscriptstyle k }$ 不同。而数据用户的成本则为 $P _ { k } D _ { k }$ 。所以第 $k$ 个用户的收益函数为

$$
U _ { k } = a _ { k } \mathbb { l b } ( D _ { k } + 1 ) - P _ { k } D _ { k }
$$

数据中心的收入为从所有数据用户处获得的价钱总和，即$\textstyle \sum _ { k \in K } P _ { k } D _ { k }$ 。数据中心的成本包含数据采集成本和数据处理成本。由本文提出的优化任务分配策略可知，完成采集任务所需的最小能耗成本为 $\textstyle C = \sum _ { { T _ { i } ^ { j } } \in T _ { y } } C _ { i } ^ { j }$ 。数据中心处理数据的成本设为$\begin{array} { r } { m \sum _ { k \in K } D _ { k } } \end{array}$ ， $\mathbf { \Sigma } _ { m }$ 为单位处理成本。则数据中心的收益函数为

$$
U _ { D } = \sum _ { k \in { \cal K } } P _ { k } D _ { k } - m \sum _ { k \in { \cal K } } D _ { k } - C
$$

本文的问题是找到斯坦克尔伯格博弈均衡来完成数据交易，目标函数为

$$
\begin{array} { l } { \displaystyle \operatorname* { m a x } _ { P _ { k } } U _ { D } } \\ { \displaystyle \mathrm { ~ s . t . ~ } \operatorname* { m a x } _ { D _ { k } } U _ { k } } \end{array}
$$

# 3.2决策分析

对数据用户的收益函数用 $D _ { k }$ 求导，得到：

$$
\frac { \partial U _ { k } } { \partial D _ { k } } = \frac { a _ { k } } { D _ { k } + 1 } - P _ { k }
$$

$$
\frac { \partial ^ { 2 } U _ { k } } { \partial D _ { _ k } ^ { 2 } } = \frac { - a _ { k } } { \left( D _ { _ k } + 1 \right) ^ { 2 } }
$$

因为二阶导数是负数，所以数据用户的收益函数是关于 $D _ { k }$ 的凸函数，存在最优的 $D _ { k }$ 使得收益最大。使 $\partial U _ { k } / \partial D _ { k } = 0$ ，求得最优的数据需求量为 $D _ { k } ^ { * } = a _ { k } \mathrm { ~ / ~ } P _ { k } - 1$ 。很明显，数据用户能接受的价格不能超过 $a _ { k }$ ，即 $P _ { k } < a _ { k }$ ，否则数据用户无法从买到的数据里获取利益。把 $\boldsymbol { D } _ { k } ^ { * }$ 代入数据中心的收益函数得到：

$$
\begin{array} { l } { \displaystyle { U _ { D } = a _ { k } - P _ { k } + \sum _ { n \in K \backslash \{ k \} } ( a _ { n } - P _ { n } ) } } \\ { \displaystyle { - m ( \frac { a _ { k } } { P _ { k } } - 1 ) - m \sum _ { n \in K \backslash \{ k \} } ( \frac { a _ { n } } { P _ { n } } - 1 ) - C } } \end{array}
$$

对 $U _ { p }$ 用 $P _ { \boldsymbol { k } }$ 求导，得到：

$$
\frac { \partial U _ { k } } { \partial P _ { k } } = - 1 + \frac { m a _ { k } } { P _ { k } ^ { 2 } }
$$

$$
{ \frac { { \hat { \sigma } } ^ { 2 } U _ { { } _ { k } } } { { \hat { \sigma } } P _ { { } _ { k } } ^ { 2 } } } = - 2 { \frac { m a _ { k } } { P _ { k } ^ { 3 } } }
$$

显然当 $P _ { k } > 0$ ，数据中心的收益函数是关于 $P _ { \boldsymbol { k } }$ 的凸函数，存在最优的使得收益最大化。使 $\partial U _ { \boldsymbol { k } } / \partial D _ { \boldsymbol { k } } = 0$ ，求得最优的价格为 $\boldsymbol { P } _ { k } ^ { * } = \sqrt { m \boldsymbol { a } _ { k } }$ 。

定理1这个斯坦克尔伯格博弈存在唯一的斯坦克尔伯格博弈均衡。

证明由式(9)可知，这个斯坦克尔伯格博弈存在这唯一的斯坦克尔伯格博弈均衡。从公式可以知道， $U _ { \boldsymbol { k } }$ 是关于 $D _ { k }$ 的凸函数。对于数据中心给出的任何 $P _ { \boldsymbol { k } }$ ，数据用户 $k$ 都有唯一的决策使得自己的收益最大化。显然，当一个博弈里面所有的参与者分别获得他们自己的最大收益时，这个博弈就达到均衡。所以只要找到最优的 $\boldsymbol { P } _ { k } ^ { * }$ ，本文提出的斯坦克尔伯格博弈就存在斯坦克尔伯格博弈均衡。从式(12)可以知道， $U _ { p }$ 是关于 $P _ { \boldsymbol { k } }$ 的凸函数。对于数据中心给出的任何 $D _ { \boldsymbol { k } } > 0$ ，数据中心都有唯一的决策 $\boldsymbol { P } _ { k } ^ { * }$ 使得自己的收益最大化。因此这个斯坦克尔伯格博弈存在这唯一的斯坦克尔伯格博弈均衡。

# 3.3博弈过程

由式(12)可以看出，如果数据中心能够知道每个数据用户的信息，它可以直接计算出 $\boldsymbol { P } _ { k } ^ { * }$ 。但是，在现实中，每个数据用户不愿意透露自己的隐私信息，所以双方的最优交易策略如下：

a)初始化 ${ \boldsymbol { P } } _ { k } ^ { * } = 0 ~ , ~ { \boldsymbol { U } } _ { D } ^ { * } = 0$ 。

b)数据中心根据历史经验提供统一的价格 $P _ { \boldsymbol { k } }$ 给每一个数据用户。c)每一个数据用户根据数据中心提供的价格计算自己的最优数据需求量 ${ D } _ { k } ^ { * } = a _ { k } / { P } _ { k } - 1$ ，并提供给数据中心。d)数据中心根据数据用户提供的数据量调节自己的价格$P _ { \boldsymbol { k } }$ 以提高效益 $U _ { p }$ 。e)如果 $U _ { p } > U _ { D } ^ { * }$ ，则 $\boldsymbol { P } _ { k } ^ { * } = \boldsymbol { P } _ { k }$ ，并跳转到步骤3；如果 $\boldsymbol { U } _ { D } = \boldsymbol { U } _ { D } ^ { * }$ ，则输出P，D。

在这个博弈过程里，数据中心根据每一个数据用户提供的采集需求量调整自己的价格。因为数据中心的效益函数是一个凸函数，所以最优价格 $\boldsymbol { P } _ { k } ^ { * }$ 一定可以保证数据中心的效益最大化。每一个数据用户根据数据中心提供的最优价格调节自己的数据需求量。因为数据用户的效益函数是凸函数，所以一定有最优数据需求量 $\boldsymbol { D } _ { k } ^ { * }$ 使数据用户效益最大化。因此，这个分布式算法总能保证博弈达到斯塔克尔伯格均衡，即数据中心和数据用户能达成协调得到双方满意的激励和数据需求量。

# 4 仿真

本文使用真实数据集[16来检验系统的优化任务分配策略和最优数据交易策略。该数据集记录了西雅图真实公交网络中公交车的GPS轨迹，能反映现实场景中公交车网络的真实移动状况。本文考虑公交线路的分布，在数据集的地图里选择了一个公交线路分布合理的 $2 0 k m \times 2 0 k m$ 区域进行公交车载群智感知实验。因为数据集反映了公交网络中公交车的实时路径，因此实验中每个周期内的公交车数量，公交车轨迹和公交车速度都直接由数据集数据决定。本文参考文献[9,10]设定参数：$\nu ^ { * } = 1 u n i t / s  , R = 5 0 0 m ^ { \prime } , \mathbf { m } = 0 . 0 1 ^ { \prime } , c = 0 . 0 1 \circ$

# 4.1任务分配策略效果

在选定的实验区域里随机分布 20个目标区域。在一个周期内，数据中心利用在这个区域内活动的公交车来对20个目标区域进行采集。数据中心分别用提出的优化任务分配策略和随机任务分配策略来分配要求的城市数据采集任务。随机任务分配策略是数据中心随机选择公交车对目标区域进行感知，使得采集的数据量达到所需求的数据量。图2显示了两种不同的任务分配策略进行数据采集所使用的能耗成本的对比。随着要求的数据总量的提高，公交车执行数据采集任务所消耗的能量成本也不断增长。使用本文提出的优化任务分配策略要比使用随机任务分配策略使用更小的能耗成本完成相同的数据采集任务。

![](images/4a727b0190420baa82bc28c3d26c3e6439001e25b92dd103bb330b0cedf01ff1.jpg)  
图2任务分配策略效果

# 4.2数据交易策略效果

假设有5个数据用户，用户的收益参数 $a _ { k }$ 在区间[2000,2500]内随机选取。数据中心和数据用户分别使用各自的策略进行数据交易。图3显示数据交易达到斯坦克尔伯格均衡。红色曲线表示所有数据用户要求的数据总量，蓝色曲线表示数据中心对所有数据用户提供的价格平均值。两条曲线随着迭代次数增加，说明双方在调整自己的策略以提高自己的效益。最后两条曲线收敛，表示双方的博弈达到斯坦克尔伯格均衡，数据中心和所有数据用户都找到自己的最优策略达到最优效益，所有参与者都不愿意再改变自己的策略。

图4表示5个数据用户的效益值。数据用户根据数据中心的出价调整自己的数据需求策略，以最大化自己的效益。只有在达到斯坦克尔伯格均衡时，数据用户才得到最高的效益值。每个用户的最高效益不同，这是因为他们对这类数据的效益参数 $a _ { \scriptscriptstyle k }$ 不一样。 $a _ { \scriptscriptstyle k }$ 越高，数据用户从同样数量的数据中获取的收益越大，因此该用户愿意购买更多的数据以获得更大效益。

图5表示提出的数据交易策略和均匀定价交易策略、随机定价交易策略、线性定价交易策略的效果对比。均匀定价交易策略是数据中心对所有的数据用户提供相同的交易价格。随机定价交易策略是数据中心对数据用户提供随机的交易价格。线性定价交易策略是数据中心对数据用户提供的交易价格为$P _ { k } = P _ { 0 } - k D _ { k }$ ，其中 $P _ { 0 }$ 是初始价格， $k$ 是参数。数据用户购买的数据越多，数据中心提供的交易价格就越低。这种优惠策略在现实场景中很常见，数据中心可以刺激数据用户购买更多的数据以获取更高的收益。

![](images/16eb3215b51b1fb34bbc2e98fb904e2be4a3a6b3a67771e594be2a3922e26cc9.jpg)  
图3斯坦克尔伯格均衡

![](images/e9917184a071184e92950e5c54df291876e521ff378801d92a030dfcc4495801.jpg)  
图4数据用户在SE的效益

如图5所示，随着数据用户数量的增加，数据中心的经济效益将越来越高。这是因为数据用户的增加使得数据需求量增加。数据中心使用本文提出的最优定价交易策略要比使用另外三种定价交易策略得到更高的经济效益。图3\~5的结果表示，使用本文提出的最优交易策略，数据中心可以最大化自己的效益，同时每个数据用户的最优效益可以得到满足。

![](images/370a384cd0413abe10111bf897e91ad1b5d7da7ba416f107bf114700f4c3ad40.jpg)  
图5不同策略的效果对比

# 5 结束语

本文总结了车载群智感知在目前研究阶段的一些不足，并分析了利用公交车相比其他车辆做车载群智感知的优势。提出基于公交网络的车载群智感知系统，并研究系统里面的数据采集任务分配和城市数据交易的问题。本文基于贪婪算法设计了一个优化任务分配策略，并基于斯坦克尔伯格博弈设计了最优交易策略。实验结果表明，使用本文提出的优化任务分配策略，公交车完成数据采集任务的成本明显降低。使用最优交易策略，数据中心在满足数据用户的效益需求前提下得到最优的经济效益。

# 参考文献：

[1]Liu J,Shen H, Zhang X.A survey of mobile crowdsensing techniques:A critical component for the internet of things [C]//Proc of the 25th IEEE International Conference on Computer Communication and Networks.2016: 1-6.   
[2]Guo B,Wang Z,Yu Z,et al. Mobile crowd sensing and computing:The review of an emerging human-powered sensing paradigm [J].ACM Computing Surveys,2015,48 (1):7.   
[3]Ganti R K,Ye F,Lei H. Mobile crowd sensing:current state and future challenges [J].IEEE Communications Magazine,2011,49（11).   
[4]Chen Y,Nakazawa J,Yonezawa T,et al.An empirical study on coverageensured automotive sensing using door-to-door garbage collecting trucks [C]//Proc of the 2nd International Workshop on Smart.2016.   
[5]Lee U,Magistretti E,Gerla M, et al. Dissemination and harvesting of urban data using vehicular sensing platforms [J].IEEE Trans on Vehicular Technology,2009,58 (2): 882-901.   
[6]Liu Y,Niu J,Liu X.Comprehensive tempo-spatial data collection in crowd sensing using a heterogeneous sensing vehicle selection method [J]. Personal and Ubiquitous Computing,2016,20 (3):397-411.   
[7]Liu Y,Wang W,Ma Y,et al. Distributed task offloading in heterogeneous vehicular crowd sensing [J]. Sensors,2016,16(7):1090.   
[8]Lee U,Gerla M.A survey of urban vehicular sensing platforms [J]. Computer Networks,2010,54 (4): 527-544.   
[9]Liu Y,Li X.Heterogeneous participant recruitment for comprehensive vehicle sensing[J].PLoS ONE,2015,10(9):e0138898.   
[10][1ooJia J,Chen J,Chang G,et al. Multi-objective optimization for coverage control in wireless sensor network with adjustable sensing radius [J].Computers & Mathematics with Applications,2009,57(11): 1767-1775.   
[11] Huang S,Chen H, Zhang Y,et al. Sensing-energy tradeoff in cognitive radio networks with relays [J].IEEE Systems Journal,2013,7(1):68-76.   
[12]田烽楠，王于．求解0-1背包问题算法综述[J].教育技术导刊,2009,8 (1): 59-61.   
[13] Maharjan S,Zhu Q,Zhang Y,et al. Dependable demand response management in the smart grid:A Stackelberg game approach [J].IEEE Trans on Smart Grid,2013,4(1):120-132.   
[14] Tushar W, Chai B,Yuen C,et al. Three-party energy management with distributed energy resources in smart grid [J].IEEE Trans on Industrial Electronics,2015,62 (4): 2487-2498.   
[15] Zhu JY, Sun C,Li V O K. Granger-Causality-based air quality estimation with spatio-temporal (ST） heterogeneous big data [C]// Proc of IEEE Conference on Computer Communications Workshops.2015:612-617.   
[16] Jetcheva JG,Hu Y C,PalChaudhuri S,et al.CRAWDAD dataset rice/ad_hoc_city [DB/OL] (2003-09-11) http://crawdad. org/rice/ad_hoc_city/20030911.