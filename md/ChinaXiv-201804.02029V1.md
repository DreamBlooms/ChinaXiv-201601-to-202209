# LTE-A系统中基于QoE能效的无线资源分配算法

余翔，王宏刚，段思睿(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：针对无线通信网络能耗日益增加与用户体验质量(qualityof experience，QoE)难以得到保证的问题，提出一种LTE-A系统基于QOE能效的资源分配算法。首先，给出联合优化QOE和能效的数学模型，特别的考虑了用户最小QoE要求；其次，根据约束条件提出了一种迭代算法进行用户资源块(resource block，RB)分配，然后利用分数规划的性质并采用凸优化方法求得最优的发射功率来优化目标函数。仿真结果表明，相较现有基于能效的资源分配算法，该算法在提高系统性能的同时有效的保证了用户QoE。

关键词：LTE-A；体验质量；能效；资源分配 中图分类号：TN915.07 doi:10.3969/j.issn.1001-3695.2017.12.0766

# QoE-based energy-efficient wireless reource allocation in LTE-system

Yu Xiang, Wang Honggang, Duan Sirui (Telecommunication& Information Engineering Institute,Chongqing UniversityofPosts&Telecommunications,Chongqing 400065, China)

Abstract: Inorder todecrease theenergyconsumptionof wirelesscommunicationsystemand ensure theuser experience quality, this paperproposeda QoE-basedenergy eficiencyresource alocationalgorithmforLTE-Asystem.First,amathematicalmodel for jointlyoptimizing QoEand energyeficiency was proposed,speciallyconsidering theminimumQoErequirementofusers. Secondly,an iterative algorithmwas proposed toallocate userresource blocks (RBs）according totheconstraints.Then,the optimal objective function was optimizedbyusing the properties offractional programming and using theconvex optimization method toobtaintheoptimal transmitpower.Simulationresultsshowthatcompared withtheexistingenergyeficiencyresource allocation algorithm,the proposed algorithm can efectively guaranteed user's QoE while improving system performance.

Key words: LTE-advanced; quality of experience; energy-efficient; resource allocation

# 0 引言

体验质量需求越来越成为迅猛增长的高速率业务用户关注的重点。相应的，高效的利用无线网络资源的同时满足不同用户的QoE需求将是未来无线网络面临的主要挑战[1]。而资源分配是解决这一问题的关键。无线网络在为用户提供良好QoE的同时带来了大量的能耗，随着绿色通信的提出和发展，设计联合优化QoE和能效的资源分配算法变得至关重要。

现有的资源分配方案大多是对QoE[2-3]和能效(EE，energy-efficient)[4-7]分别进行优化。文献[2]提出一种多用户正交频分多址(OFDMA)系统中基于QoE的跨层资源分配算法，在保证了用户QoE 需求的同时提高了系统频谱效率。文献[3]在最大化系统平均QoE的同时考虑了用户间公平性，提出一种基于QoE比例公平的资源分配算法，显著的提高了系统平均QoE和小区边缘用户性能。文献[4]研究了LTE-A下行链路传输过程中的资源分配问题。文章提出两种节能的资源分配算法，一种在考虑用户数据速率保证下以最小化系统能耗为目标进行资源分配;一种以最大化系统能效为目标完成资源分配。文章中两种算法都只考虑了系统发射功率能耗，且不能够保证用户的体验质量。文献[5]研究了异构网络下基于QoS约束的能效最优问题，通过对约束做了特定的处理将该非凸优化问题转换为凸优化问题，并用迭代算法进行求解。该算法很好的保证了用户QoS需求。文献[6]对基于LTE的MIMI-OFDM系统单小区场景下能效资源分配问题进行了研究，在考虑用户最小数据速率约束及功率限制下，通过资源分配实现最大化系统能效。首先，通过分数规划性质并根据拉格朗日对偶分解求解优化问题，分别实现子信道和功率分配；最后给出了一种次优的基于QoS感知资源分配算法。在有效提高系统能效的同时很好的保证了用户QoS 需求。文献[7]在考虑比例速率公平约束下，提出一种多用户OFDM系统中最大化能效的资源分配算法。

上述算法虽然都有不错的性能提升，但依然无法做到QoE和能耗的同时优化。文献[8]不同于最大化“比特每焦耳”参数的传统能效资源分配算法，首先给出一种表示用户满意度和能耗比值的效用参数；其次以最大化效用参数为目标，提出一种OFDMA系统中基于能效效用的资源分配算法。该算法忽略了用户间公平性其缺乏QoE 保证。文献[9]对多小区OFDMA系统中QoE和能耗联合优化问题进行了研究，文章以最大化一种新颖的可以同时表征基于公平性的用户QoE和能耗的效用函数为目标进行建模，并分别提出迭代的RB和功率分配方案完成优化问题的次优求解。

基于上述分析，针对LTE-A下行多业务场景，本文提出一种基于QoE 能效的资源分配算法。首先，提出一个QoE 和能耗的联合优化模型来最大化系统性能。特别的，该模型考虑了用户间公平及QoE保证;其次，为了高效的求解上述优化问题，本文将其分为RB分配和功率分配两个子问题。仿真结果表明，相较于现有的能效算法，本文算法能够很好的保证不同业务的QoE 需求及公平性。

# 1 系统模型

# 1.1 LTE-A系统模型

本文主要研究LTE-A系统中多业务下行传输过程中资源分配问题。系统由单个小区构成，小区中包含K个用户、N个RB，其中每个RB 带宽为 $\mathbf { B }$ 。定义 $\Omega = \{ 1 , 2 , \cdots K \}$ 为用户集合，$\Omega _ { \scriptscriptstyle 1 }$ 为实时(RT，real-time)业务用户集，非实时(NRT，nonreal-time)用户集定义为Ω，其中Ω=ΩΩ。

定义 $p _ { k , n } \cdot \left| h _ { k , n } \right| ^ { 2 } \cdot \sigma _ { k , n }$ 分别为用户 $\mathbf { k }$ 在物理资源块 $\mathfrak { n }$ 上的传输功率、信道增益和噪声功率。根据香农公式，用户 $\mathbf { k }$ 在物理资源块 $\mathfrak { n }$ 上获得的数据速率如下：

$$
r _ { k , n } = B \log _ { 2 } \left( 1 + \frac { p _ { k , n } \left| h _ { k , n } \right| ^ { 2 } } { \sigma _ { k , n } } \right)
$$

从而得出用户 $\mathbf { k }$ 在小区内获得的数据速率以及功率消耗分别为：

$$
R _ { k } = \sum _ { n = 1 } ^ { N } \rho _ { k , n } r _ { k , n }
$$

$$
P _ { k } = P _ { c } + \xi \sum _ { n = 1 } ^ { N } \rho _ { k , n } p _ { k , n }
$$

其中:二进制变量 $\rho _ { m , n } \in \{ 0 , 1 \}$ 为RB分配指示符，即 $\rho _ { { } _ { m , n } } = 1$ 表示小区内第 $\mathbf { \Omega } _ { n }$ 个RB分配给用户 $\mathbf { \Sigma } _ { m }$ ，反之，则为0。 $P _ { c }$ 为固定电路功率， $\xi$ 表示功率放大器效率。

# 1.2 QoE模型

体验质量(QoE)是终端用户对应用或者服务整体的主观可接受程度[10]，通常由 MOS 值来衡量，MOS 值与QoE 的对应关系如表1所示。本文根据文献[7]MOS-吞吐量对数关系模型来表征用户QoE，具体表达式如下：

$$
M O S _ { k } = w _ { k } \ln \Bigl ( R _ { k } / \overline { { R } } _ { k } \Bigr )
$$

其中: $R _ { k }$ 为用户实现的数据速率， $\overline { { R } } _ { k }$ 为取得最小 MOS 值时对应的数据速率。 $w _ { k }$ 为与服务相关的参数，不同服务类型下取不同值。因此，可得出系统中用户总QoE表达式如下：

$$
{ M } _ { { t o t a l } } = \sum _ { k = 1 } ^ { K } M { O S } _ { k }
$$

表1MOS值与用户体验的对应关系  

<html><body><table><tr><td colspan="4">ＩＺε→Ｓ</td><td rowspan="2">MOS</td></tr><tr><td></td><td></td><td></td></tr><tr><td colspan="4"></td></tr></table></body></html>

# 1.3问题描述

本文的目标是通过最优化分配RB和功率资源，实现最大化系统用户QoE及最小化系统功率消耗。在此基础上，本文考虑了用户QoE保证以及用户间公平性。依据上述目标，优化问题表示如下：

$$
\operatorname* { m a x } { \eta _ { \scriptscriptstyle { M E E } } } = \operatorname* { m a x } { \frac { M _ { \scriptscriptstyle { t o t a l } } } { P _ { \scriptscriptstyle { t o t a l } } } } = \operatorname* { m a x } { \frac { \displaystyle \sum _ { k = 1 } ^ { K } M O S _ { k } } { \displaystyle \sum _ { k = 1 } ^ { K } P _ { k } } }
$$

约束条件为

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \rho _ { k , n } \leq 1 \ , \rho _ { k , n } \geq 0 \ , \forall k \in \Omega
$$

$$
M O S _ { k } \geq M O S _ { \mathrm { m i n } } \quad , \forall k \in \Omega _ { 1 }
$$

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \sum _ { n = 1 } ^ { \mathrm { N } } \rho _ { k , n } p _ { k , n } \leq P _ { \operatorname* { m a x } } , p _ { k , n } \geq 0 , \forall k \in \Omega
$$

其中: $\eta _ { _ { M E E } }$ 是用来表征系统性能的参数，可以理解为每单位功耗下的用户QoE 提升。约束条件(6b)表示每个RB 只能分配给一个用户；条件(6c)为用户最小QoE 限制， $M O S _ { \mathrm { { m i n } } }$ 为用户最小QoE 要求；条件(6d)为小区最大发射功率限制。

# 2 基于QoE能效的资源分配算法

# 2.1RB分配算法设计

假设给定了RB上的功率分配，即RB上分配的功率已知，上式优化问题可重写为

$$
\operatorname* { m a x } { \eta _ { \scriptscriptstyle { M E E } } } = \operatorname* { m a x } { \frac { M _ { \scriptscriptstyle { t o t a l } } } { P _ { \scriptscriptstyle { t o t a l } } } } = \operatorname* { m a x } { \frac { \displaystyle \sum _ { k = 1 } ^ { K } { M O S _ { k } } } { \displaystyle \sum _ { k = 1 } ^ { K } P _ { k } } }
$$

约束条件为

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \rho _ { k , n } \leq 1 \ , \rho _ { k , n } \geq 0 \ , \forall k \in \Omega
$$

$$
M O S _ { k } \geq M O S _ { \mathrm { m i n } } \quad , \forall k \in \Omega _ { 1 }
$$

本文将通过一个两步分配算法来进行RB分配。首先，本文将保证RT业务的最低QoE 要求。其次，最大化系统QoE 和频谱效率。具体分配步骤如下：

a)初始化。令 $R _ { k } = 0$ ，当前用户MOS 值 $M O S _ { i n i , k } = 0$ ，RB集合 $N = \left\{ 1 , \cdots , N \right\}$ ， $k \in \Omega _ { 1 }$ 。

b)找到 MOS 值最小的用户 $\mathbf { k }$ 。即，对于 $\forall k \in \Omega _ { 1 }$

$$
k ^ { * } = \arg \operatorname* { m i n } M O S _ { k }
$$

c)将信道条件最好的 RB $\mathfrak { n }$ 分配给用户 $k ^ { * }$ ，即$n ^ { * } = \arg \operatorname* { m a x } \left| h _ { k , n } \right| ^ { 2 }$ ，更新RB集合 $N = N - \{ n \}$ 。

d)根据式(2)(4)分别更新 R 和用户 MOS值 MOSsend,k 。

e)如果对于 $\forall k \in \Omega _ { 1 }$ ，存在 $M O S _ { k } \geq M O S _ { \operatorname* { m i n } }$ ，则跳到下一步,否则返回步骤(2)。

f)如果 $N \neq \Phi$ ，找到数据发送前后QoE增量最大的用户 $\mathbf { k }$ 0即，对于∀k∈Ω

$$
k ^ { * } = \arg \operatorname* { m a x } _ { { \bf { \Lambda } } } \Delta M O S = \arg \operatorname* { m a x } \left( { M O S } _ { { s e n d } , k } - M O S _ { { i n i } , k } \right)
$$

g)将信道条件最好的RB $\mathbf { \bar { n } }$ 分配给用户 $k ^ { * }$ ，即$n ^ { * } = \arg \operatorname* { m a x } \left| h _ { k , n } \right| ^ { 2 }$ ，更新RB集合 $N = N - \{ n \}$ 。

h)根据式(2)(4)分别更新 $R _ { k }$ 和MOS值。

i)如果对于 $\forall k \in \Omega$ ，存在 $M O S _ { _ k } \geq M O S _ { _ { t a r } }$ ，其中 $M O S _ { t a r }$ 为用户QoE上限。

j)更新用户集 $\Omega = \Omega - \left\{ k \right\}$ 。  
$\mathbf { k } )$ 如果 $N \neq \Phi$ ，则返回步骤f);否则，结束。

# 2.2功率分配算法设计

在已知RB分配方案的情况下，上式(6优化问题可简化如下：

$$
\operatorname* { m a x } { \eta _ { \scriptscriptstyle { M E E } } } = \operatorname* { m a x } { \frac { M _ { \scriptscriptstyle { t o t a l } } } { P _ { \scriptscriptstyle { t o t a l } } } } = \operatorname* { m a x } { \frac { \displaystyle \sum _ { k = 1 } ^ { K } { M O S _ { k } } } { \displaystyle \sum _ { k = 1 } ^ { K } P _ { k } } }
$$

约束条件为

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \sum _ { n = 1 } ^ { \mathrm { N } } \rho _ { k , n } p _ { k , n } \leq P _ { \operatorname* { m a x } } , p _ { k , n } \geq 0 , \forall k \in \Omega
$$

式(7)目标函数是非凸的，且是分数形式。因此，本文首先确定数据速率下界，从而确定目标函数下界；然后采用分数规划性质将分数形式的目标函数转换为减数形式。

本文采用文献[11]给出的数据速率下界 $\tilde { \boldsymbol { R } } _ { k , m }$ 表达式如下：

$$
\tilde { R } _ { k , n } = \alpha _ { k , m } B \log _ { 2 } \left( \gamma _ { k , m } \right) + \beta _ { k , m }
$$

其中 $\gamma _ { \boldsymbol { k } , n }$ 是用户 $\mathbf { k }$ 在 RBn 上的信号干扰和噪声比，具体表达式如下：

$$
\gamma _ { \boldsymbol { k } , n } = \frac { \boldsymbol { p } _ { \boldsymbol { k } , n } \left| h _ { \boldsymbol { k } , n } \right| ^ { 2 } } { \sigma _ { \boldsymbol { k } , n } }
$$

$$
\alpha _ { k , n } = \gamma _ { k , n } / \left( 1 + \gamma _ { k , n } \right)
$$

$$
\beta _ { k , n } = \log _ { 2 } \left( 1 + \gamma _ { k , n } \right) - \alpha _ { k , n } \log _ { 2 } \left( \gamma _ { k , n } \right)
$$

从而得出用户 $\mathbf { k }$ 在小区内获得的速率下界 $\tilde { \boldsymbol { R } } _ { k }$ 表达式如下：

$$
\tilde { R } _ { k } = \sum _ { n = 1 } ^ { N } \rho _ { k , n } \tilde { R } _ { k , n }
$$

用 $\tilde { \boldsymbol { R } } _ { k }$ 替代(4)中的 $R _ { k }$ ，可以推导出目标函数的下界如下：

$$
\operatorname* { m a x } \eta _ { \scriptscriptstyle { M E E } } = \operatorname* { m a x } \frac { \tilde { M } _ { \scriptscriptstyle { t o t a l } } } { \tilde { P } _ { \scriptscriptstyle { t o t a l } } } = \operatorname* { m a x } \frac { k = 1 } { \displaystyle \sum _ { k = 1 } ^ { K } P _ { k } }
$$

约束条件为

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \sum _ { n = 1 } ^ { \mathrm { N } } \rho _ { k , n } p _ { k , n } \leq P _ { \operatorname* { m a x } } , p _ { k , n } \geq 0 , \forall k \in \Omega
$$

采用分数规划性质，上式的减数形式如下：

$$
\begin{array} { c } { { F \big ( q ^ { * } \big ) = \operatorname* { m a x } \tilde { \cal M } _ { \scriptscriptstyle \mathit { t o t a l } } \big ( P \big ) - q ^ { * } P _ { \scriptscriptstyle \mathit { t o t a l } } } } \\ { { = \operatorname* { m a x } \displaystyle \sum _ { k = 1 } ^ { \mathrm { K } } w _ { k } \ln \biggl ( \tilde { R } _ { k } / \overline { { R } } _ { k } \biggr ) - } } \\ { { q ^ { * } \biggl ( \varepsilon _ { 0 } \displaystyle \sum _ { k = 1 } ^ { K } P _ { k } + P _ { c } \biggr ) } } \end{array}
$$

约束条件为

$$
\sum _ { k = 1 } ^ { \mathrm { K } } \sum _ { n = 1 } ^ { \mathrm { N } } \rho _ { k , n } p _ { k , n } \leq P _ { \operatorname* { m a x } } , p _ { k , n } \geq 0 , \forall k \in \Omega
$$

其中：

$$
q ^ { * } = \operatorname* { m a x } \frac { \tilde { M } _ { \mathit { t o a t l } } } { P _ { \mathit { t o t a l } } }
$$

至此，上述问题可用凸优化方法来求解，本文采用朗格拉日对偶分解方法来求解。目标函数的拉格朗日函数可表达如下：

$$
\begin{array} { r l r } {  { L \bigl ( \lambda \bigr ) = \operatorname* { m a x } \sum _ { k = 1 } ^ { \mathrm { K } } w _ { k } \ln \biggl ( \tilde { R } _ { k } / \overline { { R } } _ { k } \biggr ) - } } \\ & { } & { q \biggl ( \xi \sum _ { k = 1 } ^ { K } P _ { k } + P _ { c } \biggr ) + \lambda \biggl ( P _ { \mathrm { m a x } } - \sum _ { k = 1 } ^ { \mathrm { K } } P _ { k } \biggr ) } \end{array}
$$

给定 $\lambda$ ，采用KKT条件 $\frac { \partial L \big ( \lambda \big ) } { \partial P _ { k } } = 0$ ，最优的发射功率 $P _ { \boldsymbol { k } }$ 如下：

$$
\frac { \partial L \big ( \lambda \big ) } { \partial P _ { k } } = \frac { w _ { k } } { \tilde { R } _ { k } } \frac { \partial \tilde { R } _ { k } } { \partial P _ { k } } - q \xi - \lambda
$$

$$
= \frac { w _ { k } } { \tilde { R } _ { k } } \frac { { B \frac { \left| { h _ { k } } \right| ^ { 2 } } { \sigma _ { k } } } } { { ( 1 + p _ { k } \frac { { \left| { h _ { k } } \right| ^ { 2 } } } { \sigma _ { k } } ) } } - q \xi - \lambda = 0
$$

进行一步推导：

$$
\frac { 1 } { \left( 1 + P _ { k } \frac { \left| h _ { k } \right| ^ { 2 } } { \sigma _ { k } } \right) } = \frac { \left( q \xi + \lambda \right) \tilde { R } _ { k } } { w _ { k } B \frac { \left| h _ { k } \right| ^ { 2 } } { \sigma _ { k } } }
$$

化简可得出

$$
P _ { k } = \left[ \frac { w _ { k } B } { \tilde { R } _ { k } \left( q \varepsilon _ { 0 } + \lambda \right) \ln 2 } - \frac { \sigma _ { k } } { \left| h _ { k } \right| ^ { 2 } } \right] ^ { + }
$$

朗格拉日乘子 $\lambda$ 递推表达式如下：

$$
\lambda ^ { ( i + 1 ) } = \left[ \lambda ^ { ( i ) } - \varsigma ^ { ( i ) } \left( P _ { \operatorname* { m a x } } - \sum _ { k = 1 } ^ { \mathrm { K } } P _ { k } \right) \right] ^ { + }
$$

其中 ${ [ \ ] } ^ { + }$ 表示向上取整， $i$ 表示迭代次数， $\varsigma$ 为迭代步长。根据文献[12]的Dinkelbach方法，给出的迭代功率分配算法步骤如下：

a)初始化。 $\tilde { R _ { k } } \left( P _ { k } \right) = \tilde { R } _ { k } \left( P _ { 0 } \right) , q ^ { * } = 0 , \lambda = 0 , \delta = 0 . 0 1 , i = 1 $ 最大迭代次数L。

b)如果 $F \Big ( q ^ { * } \Big ) = \operatorname* { m a x } \Bigg ( \tilde { M } _ { { \mathrm { \it { t o t a l } } } } - q ^ { * } P _ { { \mathrm { \it t o t a l } } } \Bigg ) \geq \delta$ 并且 $i \le L$ 。

c)更新 $q ^ { * } = \tilde { M } _ { \mathit { t o t a l } } / P _ { \mathit { t o t a l } } , \quad i = i + 1$ 。

d)根据式（12）（19）（20）分别更新Rκ，Pκ，λ。   
e)返回 $q ^ { * } , P _ { k }$ 的值。   
f)否则，结束。

# 3 仿真及结果分析

# 3.1仿真环境

参照文献[6]，本文考虑一个六边形单基站OFDMA系统，小区半径设为 $5 0 0 \mathrm { m }$ 。假设系统中用户随机均匀分布在小区中，无线信道为6径的瑞利信道，路径损耗采用改进的Hata城市传播模型。其中RT业务以视频为代表，NRT业务以文件下载服务为代表，其他仿真参数设置如表2所示。

# 3.2 仿真结果分析

为验证本文算法（QoE-EE）性能，本文与文献[6]最小速率约束下的能效资源分配算法(QoS-EE)及文献[4]能效算法(EE)进行了对比。主要的性能比较参数为：系统性能参数 $\eta _ { _ { M E E } }$ 、用户体验质量QoE。

表2主要仿真参数  

<html><body><table><tr><td>仿真参数</td><td>设置值</td></tr><tr><td>载波频率</td><td>2G Hz</td></tr><tr><td>系统带宽</td><td>10 MHz</td></tr><tr><td>资源块带宽</td><td>180 KHz</td></tr><tr><td>用户数</td><td>40</td></tr><tr><td>基站最大放射功率</td><td>45W</td></tr><tr><td>固定电路功率</td><td>412.4W</td></tr><tr><td>路径损耗模型</td><td>122+38lg(max{d,0.05})</td></tr><tr><td>阴影衰落方差</td><td>8dB</td></tr><tr><td>MOS min, MOStar</td><td>3,4.5</td></tr></table></body></html>

图1给出了小区内用户平均QoE随用户数变化的曲线。可以看出，文献[6]算法性能优于文献[4]算法，因为相较于文献[4],文献[6]算法考虑了用户最小速率要求，有效的保证了用户服务质量(QoS)，从而用户体验质量(QoE)相应的得到提升；而本文算法性能略优于文献[6]算法，因为本文算法用最小体验质量(QoE)要求替代了文献[6]算法中的最小速率要求，更加有效的保证了用户QoE。

![](images/474b9421dd5f82bc556e9fd410d6aabc6daf8c281365eaa2dfa1d59b01c93939.jpg)  
图1三种算法用户平均QoE 比较

图2给出了小区系统性能参数 $\eta _ { _ { M E E } }$ 随用户数变化的曲线。可以看出，本文算法表现优于其他两种算法，因为本文算法对QoE 和能耗进行了联合优化，以最大化用户QoE和最小化系统能耗为目标，特别的考虑了用户QoE 保证。文献[6]是以最大化系统吞吐量及最小化系统能耗为目标，同时考虑了用户QoS 要求。而文献[4]是以最小化系统能耗为目标，忽略了用户服务质量及体验质量要求。所以文献[6算法优于文献[4]算法，而本文算法略优于文献[6]算法。

![](images/2250c9c21e6356f275ac82f66782eee729e731356a3af7eb664dc8d75dccfe08.jpg)  
图2三种算法系统ηMEE性能参数比较

# 4 结束语

针对基于LTE-A的OFDMA下行系统，本文提出一种基于QoE 能效资源分配算法。其核心思想是联合优化QoE和能效，实现最大化用户QoE和最小化系统能耗的同时保证用户最小QoE 要求及公平性。并通过对RB分配及功率分配两个子问题的优化完成对复杂非凸联合优化问题的求解。仿真结果表明，该算法能够在提示系统性能的同时保证用户QoE。

# 参考文献：

[1]Feng D,Jiang C,Lim G,et al.A survey of energy-efficient wireless communications [J].IEEE Communications Surveys & Tutorials,2013,15 (1): 167-178.   
[2]Rugelj M, Sedlar U,Volk M,et al. Novel cross-layer QoE-aware radio resourceallocation algorithmsin multiuser OFDMA systems[J]. Communications IEEE Transactions on,2014,62(9): 3196-3208.   
[3]Yun H C,Kim H,Lee S H,et al.A QoE-aware proportional fair resource allocation for multi-cell OFDMA networks [J].IEEE Communications Letters,2015,19(1):82-85.   
[4]Ye Y,Wen H, Zhuo Y,etal.Energy eficient resource allocation in LTE-A [C]//Proc of IEEE//CIC International Conference on Communications in China.2013:496-501.   
[5]Huq K M S,Mumtaz S,Rodriguez J.QoS aware energy-efficient resource scheduling for HetNet CoMP[C]//Proc of IEEE International Conference on Communications.2015: 5954-5960.   
[6]Xiao X,Tao X,Lu J.Energy-efficient resource allocation in LTE-based MIMO-OFDMA systems with user rate constraints [J].IEEE Trans on Vehicular Technology,2015,64(1): 185-197.   
[7]Chen Y, Zheng Z,Li Y,et al.Energy-efficient resource allocation in multiuser OFDM systems with proportional rate constraints [J].Electronics Letters,2015,51 (20): 1611-1613.   
[8]Ye H,Tan Z.Energy-efficient utility-based resource allocation in OFDMA systems [C]//Proc of IEEE,International Symposium on Personal,Indoor, and Mobile Radio Communication.2015: 981-985.   
[9]Shao H,Jing W,Wen X,et al. Joint optimization of quality of experience and power consumption in OFDMA multicell networks [J].IEEE Communications Letters,2016,20 (2):380-383.   
[10]林闯，胡杰，孔祥震．用户体验质量(QoE）的模型与评价方法综述[J]. 计算机学报,2012,35(1):1-15.   
[11] Wang X, Zheng F C, Zhu P,et al.Energy-efficient resource allocation in coordinated downlink multicell OFDMA systems [J].IEEE Trans on Vehicular Technology,2016,65 (3): 1395-1408.   
[12] Dinkelbach W. On nonlinear fractional programming [J].Management Science,1967,13(7):492-498.