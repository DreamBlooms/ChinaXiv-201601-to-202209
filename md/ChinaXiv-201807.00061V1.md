# 具有行为效应的含AGV柔性车间调度研究\*

徐云琴，叶春明，曹磊(上海理工大学 管理学院，上海 200093)

摘要：为了研究行为效应对含AGV柔性车间调度问题的影响，构建了考虑学习效应以及恶化效应的以完工时间最短为目标的数学模型。针对该模型的特点，采用基于工序、机床和AGV分配的编码方式，并提出具有混沌局部搜索策略的鲸鱼算法求解。数值算例结果验证了算法的有效性和可行性。实验对比了学习效应、恶化效应、学习-恶化效应、不考虑效应四种情况下加工时间的差异。同时研究了加工任务批量、AGV 数量对加工时间的影响。通过实验证明了AGV资源约束和各效应共同影响了单位批量完工时间。

关键词：AGV；柔性车间调度；学习效应；恶化效应；鲸鱼算法 中图分类号：TP181 doi:10.3969/j.issn.1001-3695.2018.03.0243

# Research on flexible Job-Shop scheduling problem with AGVs constraints and behavioral effects

Xu Yunqin, Ye Chunming, Cao Lei (SchoolofBusiness,UniversityofShanghai forScience&Technology,Shanghai2ooo93,China)

Abstract: Inorder to study the effctof behavioral efects on flexible job-shop scheduling problem with AGV,this paper constructedamathematicalmodelwiththegoalofshortestcompletiontimeconsideringlearningefectanddeteriorationeffect. According to the characteristics of the model,this paper adopted a coding method based on processes,machine and AGV allocation,and proposed a whalealgorithm with chaotic localsearch strategy.Theresultsof numerical examples verifythe effectivenessand feasibilityofthealgorithm.The experimentcomparedthe processing time diferences betwee the learning effect,tedeteriorationeect,teleaing-deteriorationefect,andthebsenceofthectAttesametie,thispaperstudied theinfluenceof the numberof procesing tasks and the numberof AGVsonthe processingtime.Through experiments,it is proved that the AGV resource constraints and various eects jointly affect the unit batch completion time.

Key words:AGV;FJSP; learning effects;deteriorating effects;whale algorithm

# 0 引言

AGV（automatedguidedvehicle）是一种可以通过智能计算机控制系统进行控制的物料搬运移动式机器人[I]。它在生产制造领域应用最广泛，因此以AGV搬运约束的柔性车间调度为背景去进一步深入研究具有现实意义。

在实际生产过程中，工件加工时间会受行为效应的影响。广义的行为效应是通过研究人的行为规律、机器加工规律，找到提高生产效率的途径，包括学习效应、恶化效应等。本文研究工人具有学习效应与工件具有恶化效应时对加工时间的影响，旨在帮助企业更合理地安排生产加工计划。文献[2]考虑学习恶化因素并且机器具有可用性限制，实际加工时间为$\boldsymbol { P _ { j r } } = ( p _ { 0 } + b t ) \boldsymbol { r ^ { a } }$ （ $b$ 为工件恶化率， $a$ 为学习因子)使得单机调度问题更加符合实际地生产制造。当机器重复加工同一零件，随着加工数量的增加，加工单个零件的时间缩短，即产生学习效应；当零件开工时间变晚，使加工单个零件时间变长，即恶化效应。文献[3]提出具有恶化和学习效应及资源分配的排序模型，且将模型一般化为 $P _ { j r } = P _ { j } \operatorname* { m a x } \{ f _ { j } ( r ) , b _ { j } \} + c t - \beta _ { j } \mu _ { j }$ （其中 $u _ { j }$ 为工件j的可用资源，c成为恶化率， $\operatorname* { m a x } \{ f _ { j } ( r ) , b _ { j } \}$ 学习效应函数)。文献[4]研究的是考虑学习恶化效应的无等待流水调度学习恶化效应模型，利用局部搜索方法求解最小总延迟。文献[5]考虑了同时具有学习恶化效应的柔性作业车间调度问题，并用改进的遗传算法结合可变区域搜索进行求解。考虑到参数设置会影响算法性能，采用了田口的鲁棒设计方法来定义最佳参数值。文献[6]考虑学习效应以及设置时间的柔性车间调度问题，提出遗传算法结合变量领域搜索和迭代局部搜索，并采用自适应策略来调整参数。文献[7]考虑具有学习恶化效应的平行机调度问题,提出了一种基于蚁群优化算法求解。文献[8]考虑了同时具有学习恶化效应的柔性作业车间调度问题，并用改进的遗传算法结合邻域搜索进行求解。

笔者在查阅文献的过程发现：具有行为效应的含AGV柔性车间调度研究极少。目前学者研究考虑学习遗忘效应，或者学习恶化效应的调度问题，但研究者这往往取一个固定的学习率、遗忘率、恶化率求解分析与不含效应的调度问题对比然后就结束了研究。往往忽略分析不同的学习率，不同的遗忘率、不同的恶化率的影响差异性。本文不仅考虑了上述不同的效应因子对加工时间的影响,还分析了任务批量与AGV的数量对含AGV柔性车间调度的影响。

# 1含有AGV的FJSP描述与建模

# 1.1问题描述

含有AGV的柔性车间调度问题考虑 $\mathbf { n }$ 工件在 $\mathrm { ~ m ~ }$ 台设备上加工并由AGV负责工件在设备间的运输的过程，且每台设备都由一个工人操作。每个零件都有 $n _ { i }$ 道不同的工序 $n _ { i } < m$ ，每个工序可在多台设备上加工,有 $\mathrm { ~ \bf ~ r ~ }$ 台AGV，且 $\mathrm { r } { < } \mathrm { m } { + } 2$ 。有如下假设：

a)AGV的搬运路线是固定的，AGV搬运不延时，不同AGV搬运互不干扰。b）AGV工作内容是：从上一道工序加工设备的输出缓存区立即搬运至下一道工序的输入缓存区。c）零时刻，所有设备和机器都可用d)工件从加工设备的输入缓存区到开始加工的时间是瞬时完成，消耗时间忽略不计e)每台设备一次只能加工一个零件，每个零件在设备上加工时不中断。f）设备加工顺序约束，加工设备按先到先加工（FCFS）规则。g)不同工件先后无约束，同种工件必须先完成上一道工序，然后再进行下一道工序。h）所有待加工的工件放在装载台M0，加工好的工件放在卸载台 $\mathrm { { M m } } { + } 1$ 处。

# 1.2模型建立

# 1.2.1学习效应模型

学习效应是指在实际生产中，工人随着加工件数的增加，操作逐渐熟练使得加工工件的时间缩短。又因为学习效果因人而异，使得每个人加工相同工件时间不同。因此很有必要研究学习效应对加工时间的影响。

参数的取值可能使实验结果出现较大偏差，然而目前尚未有针对学习效应参数取值的研究。因此本文采用简洁的DeJong学习效应模型[]。模型如下：

$$
P _ { j r } = P _ { j } [ M + ( 1 - M ) r ^ { \alpha } ]
$$

$$
\alpha = \frac { \lg l } { \lg 2 }
$$

其中: $P _ { j r }$ 表示实际加工时间， $P _ { j }$ 表示理论加工时间，即没有学习效应时工件的加工时间， $\mathbf { r }$ 表示工件排在第 $\mathrm { ~ \bf ~ r ~ }$ 位加工。 $\alpha$ 表示学习因子。 $\mathbf { \xi } _ { l }$ 表示学习率。 $M$ 表示不可压缩因子：当 $\scriptstyle \mathbf { M } = 0$ 时，即Biskup 模型[10]，当 $\mathbf { M } { = } 1$ 时，则表示工件加工时不考虑学习效应的情况。

![](images/0a26bab14badb4ce1f0127de90a1da35f41e1aaf3fa62bd0b9e40c31c436a7f6.jpg)  
图1学习效应示意图

参考文献[11,12]可知，员工学习效果受员工的初始能力、员工的能力上限、员工的学习能力和重复作业次数四个方面的因素影响。起初员工到岗位作业时拥有不尽相等的初始能力，而且员工的初始能力和员工工作经验、是否有岗前培训有关。某一岗位员工的初始能力用员工加工工件的时间与标准加工工时的比值表示，初始能力越强， $p$ 越小；工作越复杂， $p$ 越大。构建员工初始能力矩阵 $P ^ { i n i t i a l }$ （其中 $p _ { i j } ^ { i n i t i a l } ( i = 1 , 2 , . . . , m ; j = 1 , 2 , . . . , n )$ 表示员工i加工工件 $j$ 的初始能力，一人独立操作一台加工设备，操作加工设备共 $m$ 台，工件 $n$ 共件):

$$
P ^ { i n i t i a l } = \left[ \begin{array} { c c c c } { p _ { 1 1 } ^ { i n i t i a l } } & { p _ { 1 2 } ^ { i n i t i a l } } & { \ldots } & { p _ { 1 n } ^ { i n i t i a l } } \\ { p _ { 2 1 } ^ { i n i t i a l } } & { p _ { 2 2 } ^ { i n i t i a l } } & { \ldots } & { p _ { 2 n } ^ { i n i t i a l } } \\ { \ldots } & { \ldots } & { \ldots } & { \ldots } \\ { p _ { m 1 } ^ { i n i t a l } } & { p _ { m 2 } ^ { i n i t i a l } } & { \ldots } & { p _ { m n } ^ { i n i t i a l } } \end{array} \right]
$$

学习能力与员工的观察力、记忆力、理解能力、注意力等有关，与员工本身有关。员工学习能力用学习率 $l$ （Learning Rate）表示，学习能力越强，那么学习率 $l$ 小；工作越简单， $\mathbf { \xi } _ { l }$ 越大。构建员工学习率矩阵L（其中 $l _ { i j } ( i = 1 , 2 , . . . , m ; j = 1 , 2 , . . . , n ; )$ 表示员工$i$ 加工工件 $j$ 的学习率):

$$
L = { \left[ \begin{array} { l l l l } { l _ { 1 1 } } & { l _ { 1 2 } } & { \dots } & { l _ { 1 n } } \\ { l _ { 2 1 } } & { l _ { 2 2 } } & { \dots } & { l _ { 2 n } } \\ { \dots } & { \dots } & { \dots } & { \dots } \\ { l _ { m 1 } } & { l _ { m 2 } } & { \dots } & { l _ { m n } } \end{array} \right] }
$$

随着重复操作次数变多，工件加工时间趋于稳定，即员工能力达到上限。员工能力上限与工作本身难度、员工本身有关，工作越难，能力上限越低；员工学习能力越弱，能力上限越低。其中 $p _ { i j } ^ { f i n a l } ( i = 1 , 2 , . . . , m ; j = 1 , 2 , . . . , n )$ 表示员工i加工工件 $j$ 的最大能

力。

$$
P ^ { f i n a l } = \left[ \begin{array} { c c c c } { { p _ { 1 1 } ^ { f i n a l } } } & { { p _ { 1 2 } ^ { f i n a l } } } & { { \ldots } } & { { p _ { 1 n } ^ { f i n a l } } } \\ { { p _ { 2 1 } ^ { f i n a l } } } & { { p _ { 2 2 } ^ { f i n a l } } } & { { \ldots } } & { { p _ { 2 n } ^ { f i n a l } } } \\ { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } \\ { { p _ { m 1 } ^ { f i n a l } } } & { { p _ { m 2 } ^ { f i n a l } } } & { { \ldots } } & { { p _ { m n } ^ { f i n a l } } } \end{array} \right]
$$

重复作业次数越多，员工学习效果越好，用r表示员工第r次加工该工件。根据学习效应的四大影响因素修正DeJong 学习模型得：

$$
\{ \begin{array} { l l } { \displaystyle P _ { i j r } = \{ p _ { i j } ^ { i n i t a l } P _ { i j } [ M + ( 1 - M ) r ^ { \alpha _ { i j } } ] } & { P _ { i j r } \geq p _ { i j } ^ { j n a l } P _ { i j } } \\ { \displaystyle P _ { i j } ^ { j n a l } P _ { i j } } & { P _ { i j r } < p _ { i j } ^ { j n a l } P _ { i j } } \\ { \displaystyle \alpha _ { i j } = \frac { \log l _ { i j } } { \log 2 } } & \\ { \displaystyle r \in N ^ { * } } & \end{array} 
$$

为了验证员工的初始能力、员工的能力上限、员工的学习能力和重复作业次数是影响员工技能变化的重要因素，假定有两个员工，分别加工同一批工件同一道工序： $P _ { 1 1 } ^ { i n i t i a l } = 0 . 9$ ，（204 $l _ { 1 1 } = 0 . 8$ ， $P _ { 1 1 } ^ { f n i a l } = 0 . 7 ~ P _ { 2 1 } ^ { i n i t i a l } = 0 . 8$ ， $l _ { 2 1 } = 0 . 9$ ， $P _ { 2 1 } ^ { f i n i a l } = 0 . 7 5$ ， $M = 0 . 5$ 。两人技能曲线变化图如下图所示。由图可得，员工2初始技能强于员工1，但是学习能力弱于员工1，当重复加工5次时，员工2的技能弱于员工1，并在 $\scriptstyle \mathbf { r } = 6$ 时，两人技能保持不变。

![](images/6b969d389219afc502b7243b87c7024a255600bcde1de9657b053fd8c254f80a.jpg)  
图2员工技能曲线图

# 1.2.2恶化效应模型

实际生产加工中，当工件的开工时间足够晚或者位置足够后面时，工件的加工时间不可能无限大。然而，在我们能看到大量的关于恶化效应研究成果中，都忽视对这一方面的研究。因此本文在一般线性恶化模型的基础上进行模型改进。一般线性恶化模型[13]： ${ P } _ { i j } ^ { * } = { P } _ { i j } + b _ { j } t _ { j }$ 其中 $P _ { _ { i j } }$ 为基本加工时间， $t _ { j }$ 为该工件开始加工时间， $0 < b _ { j } < 1$ 为恶化因子且只与工件有关。

$$
\begin{array} { r } { \left\{ \begin{array} { l } { P _ { i j } ^ { * } = P _ { i j } + b _ { j } [ \operatorname* { m a x } \{ t - t _ { j } ^ { \operatorname* { m i n } } , 0 \} - \operatorname* { m a x } \{ t - t _ { j } ^ { \operatorname* { m a x } } , 0 \} ] } \\ { \mathbf { B } = \left[ b _ { 1 } \quad b _ { 2 } \quad \ldots \quad b _ { n } \right] } \end{array} \right. } \end{array}
$$

![](images/ae34dd95a0278096bf4e069e052dfc11cdc7b3b14edaf1be8c3ca397001bec54.jpg)  
图3恶化效应示意图

# 1.2.3学习-恶化效应模型

学习效应主要是工人通过技能的熟练，使加工时间缩短，然而恶化效应是指工件开工时间延后导致加工时间变长。加工时间长短受两者共同作用，因此有必要综合考虑学习效应、恶化效应对工件加工的影响，即学习-恶化效应。

本文采用Cheng（2017）提出学习-恶化模型[14]：$P _ { i j r } ^ { * } = ( P _ { i j } + b _ { j } t _ { j } ) r ^ { \alpha _ { i j } }$ ，结合本文改进的学习效应模型得改进学习-恶化模型：

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { P _ { i j ^ { \prime } } = p _ { i j } ^ { i n i a l } ( P _ { i j } + b _ { j } [ \operatorname* { m a x } \{ t - t _ { j } ^ { \mathrm { m i n } } , 0 \} - \operatorname* { m a x } \{ t - t _ { j } ^ { \mathrm { m a x } } , 0 \} ] ) [ M + ( 1 - M ) r ^ { \alpha _ { i j } } ] } \\ { \nleq ! \mathrm { f } \mathrm { f } _ { i j ^ { \prime } } \geq p _ { i j } ^ { i n a l } ( P _ { i j } + b _ { j } , t _ { j } ) } \\ { P _ { i j ^ { \prime } } = p _ { i j } ^ { j n a l } ( P _ { i j } + b _ { j } [ \operatorname* { m a x } \{ t - t _ { j } ^ { \mathrm { m i n } } , 0 \} - \operatorname* { m a x } \{ t - t _ { j } ^ { \mathrm { m a x } } , 0 \} ] ) } \end{array} \right. } \\ & { \left\{ \begin{array} { l l } { \displaystyle \mathfrak { f } _ { i j ^ { \prime } } \mathrm { f } _ { i j ^ { \prime } } < p _ { i j } ^ { j m a l } ( P _ { i j } + b _ { j } , t _ { j } ) } \\ { \displaystyle \mathfrak { a } _ { i j } = \frac { \mathrm { l g } \bar { l } _ { i j } } { \mathrm { l g } 2 } } \\ { \displaystyle r \in N ^ { \ast } } \end{array} \right. } \end{array}
$$

# 2 鲸鱼算法设计

# 2.1算法编码和解码

本文用一个座头鲸位置代表一个候选调度方案，其中维数为3L，由Tr（transport sequence）向量、M（machine）向量、R（robot）向量构成，且这三个向量每一维上是相互对应的。其中 $L = \sum _ { i = 1 } ^ { n } n _ { i } + n$ （ $n$ 为工件数， $n _ { i }$ 为第 $i$ 个工件的总工序数)，且 Tr向量分量小于等于工件总数、M向量分量小于等于加工设备（含装载台、卸载台）总数、R向量分量小于等于AGV的数量。表1为一个编码示例。

表1粒子编码向量矩阵  

<html><body><table><tr><td>粒子维数</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td></tr><tr><td>Tr向量</td><td>1</td><td>2</td><td>3</td><td>4</td><td>2</td><td>3</td><td>2</td><td>1</td><td>4</td><td>1</td><td>3</td><td>2</td><td>3</td><td>4</td><td>1</td><td>3</td></tr><tr><td>M向量</td><td>1</td><td>2</td><td>3</td><td>4</td><td>1</td><td>5</td><td>2</td><td>3</td><td>1</td><td>5</td><td>4</td><td>6</td><td>3</td><td>6</td><td>6</td><td>6</td></tr><tr><td>R向量</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td><td>1</td><td>2</td></tr></table></body></html>

按鲸鱼优化算法更新位置公式计算，不可避免出现非整数值。又因为在FJSP中工序有先后顺序和工序、加工设备、AGV必须为整数。因此按如下规则调整迭代结果。

a）Tr向量。由算法公式可知，分量不可避免会出现小数。

针对FJSP中工序有先后顺序约束和工序为整数的特点，采用下图方法修正迭代结果。首先将迭代后的Tr向量按数值大小从小到大到排序后得到新的向量，然后将新向量的值所对应的初始值重新排列，最后得到修正后的向量序列，即得到一个新的可行工序加工方案。

初始Tr向量 1 2 1 4 2 3 2 1 4 1 3 3 4 1 3  
迭代后 2.1 7 22.1 2.9 0.3 2.9 0.8 -0.1 0.9 0.8 0.5 8.7 7.9 2.3  
从小到大 2.1 7 2.7 2.1 2.9 0.3 2 福 1 0.9 0.8 -0.5 8.7 7.9 2.3  
-0.5 -0.1 0.3 0.8 0.8 0.9 2. 2 2.9 7 7.9 8.7  
修正后 3 4 3 1 3 2 2 1 4

b)M向量。由算法公式可知，分量不可避免会出现小数。针对FJSP中加工设备为整数的特点(加工设备满足全部柔性），采用下图方法修正迭代结果。首先将迭代后的M向量向上取整，因为加工设备数量的限定，然后按边界取值，即将所有超出上界（加工设备总数）的取值为上界，低于下界的取值为1。若加工设备为部分柔性，首先获取已修正的Tr向量，得到加工工序顺序。然后，将迭代后M向量的分量与对应工序可选加工加工设备集的加工设备编号距离最近的数更新为新的M向量。

![](images/be857676a49014652d2e513e76d74fa6fe31c07a7bcb6693b418aa80c1fee437.jpg)  
图4Tr向量调整

c)R向量。调整规则同M向量(加工设备满足全部柔性)。

![](images/fc538b020cc6992e97b2503bf413dd96aa3369ac90c08834f36ce9707be105f4.jpg)  
图5M向量调整  
图6R向量调整

# 2.2种群初始化

根据上文编码方式，第一步随机生成搬运序列，第二步采用贪婪法分配机器，第三步启发式生成R向量，并借鉴文献[15]启发式调整的思想，调整R向量，使空载时间减少。

采用贪婪法分配机器：

a）随机生成的Tr向量可得到加工工序顺序。b)逐一计算工序的最早完工时间，则将最早完工的工序分配给对应加工设备加工。c)若多台加工设备的完成工时间相等，那么判断该工序加入是否需要等待，那么分配等待时间短的加工设备加工该工件；若等待时间相同，随机分配一台加工设备加工该工件。

启发式生成、调整R向量：

a）生成R向量：为每个搬运序列的搬运工序启发式均匀分配AGV搬运，得到R向量。

b)调整R向量：某AGV搬运工件到达加工加工设备后，检查该加工设备缓存区是否有工件等待搬运。如果有，则该AGV紧接着搬运缓存区的工件，即将工件对应的搬运工序调整到该搬运操作之后，从而减少该AGV的空载时间；如果无，则执行搬运序列的下一个搬运操作。根据R向量，将搬运序列从左至右逐一检查，从而调整R向量，最终使R向量的AGV空载时间最短。

# 2.3位置更新策略

鲸鱼优化算法[16](whale optimization algorithm,WOA)是由澳大利亚学者Mirjalili等人于2016年时提出的一种新型群体智能优化算法，其源于对自然界中鲸鱼群体捕食行为的模拟;通过鲸鱼群体搜索、包围和追捕攻击猎物等一系列过程实现搜索优化的目的。虽然WOA已被证明在求解精度和收敛速度方面均优PSO、DE、引力搜索算法(gravitational search algorithm,GSA)和GWO算法等，但其依然存在全局搜索与局部搜索难以协调、易陷入局部最优等缺陷[17]，而对WOA算法在这些问题上的改进研究国内外仍然尚未展开。

由WOA算法思想可知，座头鲸的位置是“游走觅食”“包围收缩”“螺线捕食”三种行为分互相影响作用的结果。

a)游走觅食。座头鲸依靠种群随机个体位置来导航搜索猎物，其空间位置更新如下公式所示。

$$
\left\{ \begin{array} { l l } { X _ { t + 1 } = X _ { r a n d } - D \cdot A } \\ { D = \left| C \cdot X _ { r a n d } - X _ { t } \right| } \end{array} \right.
$$

其中: $X _ { t }$ 、 $X _ { t + 1 }$ 分别表示座头鲸第t、 $_ { \mathrm { t + l } }$ 次迭代的位置。A、C为系数向量且 $C \in [ 0 , 2 ]$ ， $A \in [ - 2 , 2 ]$ ，当 $\left| A \right| \leq 1$ 时，表明随机个体为猎物所处位置，座头鲸游近随机个体去觅食；否则，远离该随机个体搜索其他更适合猎物。

系数向量A和C计算方法如下： $A { = } 2 a \cdot r { - } a$ 、 $C = 2 r$ 。其中，随着迭代次数的增加， $\boldsymbol { a }$ 是从2到0单调递减，表达式$a = 2 - \frac { 2 t } { T _ { \mathrm { m a x } } }$ $\mathrm { ~ \bf ~ r ~ }$

b)包围收缩。座头鲸使用种群最优个体位置来导航包围食物，收缩捕食范围。

$$
\left\{ \begin{array} { l l } { X _ { t + 1 } = X _ { b e s t } - D \cdot A } \\ { D = \left| C \cdot X _ { b e s t } - X _ { t } \right| } \end{array} \right.
$$

其中: $X _ { b e s t }$ 是种群中全局最优个体，也是猎物所处位置或者距猎物最近的位置;A、C同上，当 $\left| A \right| { > } 1$ 时，表明座头鲸远离随机个体 $X _ { r a n d }$ ，向全局最优个体 $X _ { b e s t }$ 游近。

c）螺线捕食。座头鲸在向 $X _ { \ b e s t }$ 游近的同时，还有一定的概率 $\mathfrak { p }$ 会以对数螺旋线的轨迹运动。

$$
\left\{ \begin{array} { c } { X _ { t + 1 } = X _ { t } + D _ { b e s t } \times e ^ { b l } \times \cos ( 2 \pi l ) } \\ { D _ { b e s t } = \left| X _ { b e s t } - X _ { t } \right| } \end{array} \right.
$$

其中: $D _ { b e s t }$ 是座头鲸当前位置与最优个体的距离; $b$ 为构造螺旋线轨迹的常数; $l$ 是随机数 $l \in \left[ - 1 , 1 \right]$ 。

# 2.4混沌搜索策略

在WOA算法中，座头鲸将最优个体坐标为导航，并以螺旋运动同时缩小包围圈的轨迹游向猎物。虽然这可以加快收敛速度但是易使群体快速聚集在一起，从而容易陷入局部最优[17]。混沌搜索是一种具有遍历性，为随机性特点的搜索方法。在一定程度上能够跳离局部最优值从而找到全局最优值。但混沌搜索无法从经验中学习，搜索不可避免存在搜索盲目性[18,19]。为了结合WOA的快速寻优和混沌搜索的遍历性，将混沌引入WOA算法之中。

混沌搜索思想是：首先，将座头鲸的空间位置通过混沌映射转换为混沌变量；然后，利用混沌自映射函数做遍历性搜索。再将搜索得到的混沌向量序列通过函数转换为解向量序列，得到最优解向量；最后更新座头鲸个体空间位置。

混沌搜索过程如下：

a）座头鲸个体空间位置经下面公式转换到混沌区间（-1，1）内。其中 $x _ { i } \in ( a _ { i } , b _ { i } )$ 。

$$
Z _ { i } = { \frac { 2 ( x _ { i } - a _ { i } ) } { b _ { i } - a _ { i } } } - 1
$$

b)采用比经典逻辑映射具有更好遍历性的逻辑自映射函数[20,21]来产生多个混沌变量序列，其中 $Z _ { i }$ ， $\displaystyle i = 0 , 1 , 2 , . . . ;$ 是混沌变量，且 $Z _ { i } \in ( - 1 , 1 )$ 。当 $Z _ { 0 } \neq 0 . 0 . 5$ 时，混沌就会发生。

$$
Z _ { _ { i + 1 } } = 1 - 2 Z _ { _ { i } } ^ { 2 }
$$

c)将所得到的多个混沌变量序列经下面公式转换成多个解向量序列，即得到该座头鲸个体多个新的空间位置。

$$
{ \boldsymbol { x } } _ { i } ^ { \prime } = { \frac { 1 } { 2 } } ( b _ { i } - a _ { i } ) \times { \boldsymbol { Z } } _ { i } + { \frac { 1 } { 2 } } ( b _ { i } + a _ { i } )
$$

d)对多个空间位置进行适应度值的计算，选择最优的适应度值所对应的空间位置来代替该座头鲸的空间位置。

# 2.5算法求解步骤

a）参数初始化设置，设置种群规模N，当前迭代次数t，最大迭代次数 $T _ { \mathrm { m a x } }$ 。构造螺旋线轨迹的常数 $\boldsymbol { \mathbf { b } }$ ，随机向量r，随机数1、p。

b）初始化种群，按本文提出的初始化规则初始化种群，并计算每个个体的适应度值并得到 $X _ { b e s t }$ 。

c）如果随机数 $p < p ^ { * } ( p \in [ 0 , 1 ] )$ 且 $\left| { \cal A } \right| { \le } 1$ ，则个体选择“游走觅食”来更新空间位置，否则个体选择“包围收缩”来更新空间位置。如果随机数 $p \geq p ^ { * }$ ，则个体选择“螺线捕食”来更新空间位置，并计算每个个体的适应度值并更新 $X _ { b e s t }$ 。

d）根据混沌搜索策略，对新更新的群体中精英群体（适应度值前2-10）进行混沌搜索，并更新精英群体，合并未进行混沌搜索的个体，从而得到新的群体并更新 $X _ { b e s t }$ 。

e）算法达到最大迭代次数，算法终止，输出 $X _ { b e s t }$ ，及对应的最佳调度排序。

# 3 问题求解

# 3.1参数分析

WOA算法中主要参数是构造螺旋线轨迹的常数b、概率$p ^ { * }$ 、种群数N、迭代次数。为了研究b， $p ^ { * }$ 、N、 $T _ { \mathrm { m a x } }$ 取值不同对 WOA的优化性能的影响，本文对8x8 测试示例[21]通过正交实验做了以下测试。

a)结合鲸鱼算法相关文献参数取值，确立参数水平的取值，即可建立四因素三水平正交实验表（ $L _ { 9 } ( 3 ^ { 4 } )$ ）。

表2参数水平  

<html><body><table><tr><td rowspan="2">参数</td><td colspan="3">水平</td></tr><tr><td>1</td><td>2</td><td>3</td></tr><tr><td>b</td><td>0.5</td><td>1</td><td>2</td></tr><tr><td>p*</td><td>0.4</td><td>0.5</td><td>0.8</td></tr><tr><td>N</td><td>100</td><td>200</td><td>500</td></tr><tr><td>Tmax</td><td>50</td><td>100</td><td>200</td></tr></table></body></html>

b)将各参数水平组合独立运行20次，以20次结果平均值作为评价参数性能的指标。其中运行结果如表3所示。

c）求出每一因素的极差，根据极差，得到各参数的重要程度，从而找到最佳因素水平组合。从下表可得出，N的极差最大，等级最高。说明种群数目N对算法寻优性能影响最大。然而构造螺旋线轨迹的常数b、概率 $p ^ { * }$ 则对算法寻优性能影响不明显。同样从下图可以很直观地看出，种群数对寻优性能的影响大，种群数越大，当迭代次数相同时，算法获得的可行解成指数增长，因此得到更优解的概率变大。

表3正交实验表  

<html><body><table><tr><td rowspan="2">实验号</td><td colspan="4">因素</td><td rowspan="2">average</td></tr><tr><td>b</td><td>p*</td><td>N</td><td>Tmax</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>18.55</td></tr><tr><td>2</td><td>1</td><td>2</td><td>2</td><td>2</td><td>17.8</td></tr><tr><td>3</td><td>1</td><td>3</td><td>3</td><td>3</td><td>17.15</td></tr><tr><td>4</td><td>2</td><td>1</td><td>2</td><td>3</td><td>17.842</td></tr><tr><td>5</td><td>2</td><td>2</td><td>3</td><td>1</td><td>17.526</td></tr><tr><td>6</td><td>2</td><td>3</td><td>1</td><td>2</td><td>18.632</td></tr><tr><td>7</td><td>3</td><td>1</td><td>3</td><td>2</td><td>17.421</td></tr><tr><td>8</td><td>3</td><td>2</td><td>1</td><td>3</td><td>18.053</td></tr><tr><td>9</td><td>3</td><td>3</td><td>2</td><td>1</td><td>18.105</td></tr></table></body></html>

表4参数性能分析  

<html><body><table><tr><td rowspan="2">水平</td><td colspan="4">参数</td></tr><tr><td>b</td><td>p*</td><td>N</td><td>Tmax</td></tr><tr><td>1</td><td>17.833</td><td>17.938</td><td>18.411</td><td>18.061</td></tr><tr><td>2</td><td>18</td><td>17.793</td><td>17.916</td><td>17.951</td></tr><tr><td>3</td><td>17.86</td><td>17.962</td><td>17.366</td><td>17.682</td></tr><tr><td>极差</td><td>0.167</td><td>0.169</td><td>1.046</td><td>0.379</td></tr><tr><td>等级</td><td>4</td><td>3</td><td>1</td><td>2</td></tr></table></body></html>

由实验数据和分析可得，建议的参数组合： $b = 0 . 5$ ， $p ^ { * } = 0 . 5$ ，$N = 5 0 0 , T _ { \mathrm { m a x } } = 2 0 0$

# 3.2算法寻优能力验证

实验仿真环境为Windows7，64操作系统，处理器主频$2 . 5 \mathrm { G H z }$ ，内存4G，采用MatlabR2014编译软件，每个算例运行20次取最优值。群种群规模N为500，最大迭代次数为200，b取0.5， $p ^ { * }$ 取0.5。

为了验证粒子群算法的寻优能力，从Bilge[22]等提出的 40个算例中选取部分进行计算：4台加工设备、装载台、卸载台与AGV构成了四种布局，并且考虑AGV的搬运时间和空载时间，求出最短加工时间。算例“Ex21”表示，2表示Jobset2，

1表示Layoutl。MAS表示文献[23]提出算法的结果。GAHA-2、GAHA-3表示文献[24]提出的2个和3个AGV在考虑工件加工完成搬运至卸载台的情况下，采用遗传算法与启发式混合算法所得到的结果。FDE、FMAS分别表示文献[25,26]提出算法的结果。PSO 和FPSO表示使用本文改进粒子群算法，分别计算车间调度和柔性车间调度的最短加工时间。通过实验结果可知本文提出的改进粒子群算法有较好的寻优能力：运用本文算法计算车间调度问题时， $41 . 6 7 \%$ 的解优于MAS（ $\scriptstyle \mathrm { R = } 2$ ）与GAHA ( $\scriptstyle \mathrm { R = } 2$ )的最优解， $91 . 6 7 \%$ 的解优于GAHA（ $\scriptstyle 1 = 3$ )的解。在计算柔性车间调度问题时， $50 \%$ 的解优于FDEC $\scriptstyle \mathrm { R } = 2$ )与FMAS（ $\scriptstyle 1 = 2$ ）的最优解。同时不难发现，增加AGV能够缩短整个完工时间，完工时间越长，增加AGV更有效。

表5算例实验结果  

<html><body><table><tr><td>算例</td><td>MAS [22] R=2</td><td>GAHA [23] R=2</td><td>WOA 本文 R=2</td><td>FDE [24] R=2</td><td>FMAS [25] R=2</td><td>FWOA 本文 R=2</td><td>GAHA [23] R=3</td><td>WOA 本文 R=3</td></tr><tr><td>EX11</td><td>130</td><td>116</td><td>126</td><td>96</td><td>111</td><td>99</td><td>96</td><td>96</td></tr><tr><td>EX12</td><td>98</td><td>91</td><td>92</td><td>82</td><td>87</td><td>80</td><td>86</td><td>84</td></tr><tr><td>EX13</td><td>109</td><td>100</td><td>104</td><td>84</td><td>91</td><td>83</td><td>90</td><td>90</td></tr><tr><td>EX14</td><td>168</td><td>140</td><td>155</td><td>103</td><td>128</td><td>106</td><td>110</td><td>111</td></tr><tr><td>EX21</td><td>143</td><td>121</td><td>131</td><td>100</td><td>128</td><td>104</td><td>104</td><td>99</td></tr><tr><td>EX22</td><td>86</td><td>88</td><td>92</td><td>76</td><td>88</td><td>74</td><td>84</td><td>81</td></tr><tr><td>EX23</td><td>98</td><td>95</td><td>94</td><td>86</td><td>102</td><td>90</td><td>86</td><td>86</td></tr><tr><td>EX24</td><td>169</td><td>151</td><td>152</td><td>106</td><td>131</td><td>114</td><td>118</td><td>116</td></tr><tr><td>EX31</td><td>142</td><td>134</td><td>114</td><td>99</td><td>114</td><td>96</td><td>105</td><td>90</td></tr><tr><td>EX32</td><td>114</td><td>101</td><td>94</td><td>85</td><td>99</td><td>80</td><td>89</td><td>84</td></tr><tr><td>EX33</td><td>103</td><td>107</td><td>102</td><td>86</td><td>102</td><td>84</td><td>91</td><td>90</td></tr><tr><td>EX34</td><td>167</td><td>166</td><td>150</td><td>110</td><td>128</td><td>124</td><td>130</td><td>110</td></tr></table></body></html>

# 3.3实验分析

# 3.3.1AGV边际效用

从2017-2020年中国移动机器人（AGV）行业调研报告可知，中高端 AGV产品单价区间在20-50万元，甚至高达100 万元。因为AGV价格较高，企业投资AGV数量决策尤为重要，因此本文引入经济学中的边际效用理论来衡量企业每投资一台AGV使工件加工时间减少的效果。

边际效用理论指出商品价值由该商品的边际效用决定，意思是每多买一单位商品或服务给消费者带来的总效用增量[27]。根据理论，本文用效用代表加工所有工件减少的时间，商品指的是AGV，公式如下：

$$
M U = { \frac { \Delta T U } { \Delta Q } } = { \frac { \Delta T i m e } { \Delta Q } } = \Delta T i m e
$$

为了深入研究AGV的边际效用，本文选取加工设备和加工工件较多的算例 $1 5 \times 1 0 ^ { [ 2 8 ] }$ ，取不同数量的 AGV，分别计算20 次，所得结果如下所示。从下表可以发现当AGV数量大于等于14时，最优完工时间在170。其中，当AGV数量为13时，边际效用为4，而AGV数量为14时，边际效用为6，笔者认为边际效用小幅度增加的原因是计算次数不是足够多。

表6基于不同数量AGV的最优加工时间  

<html><body><table><tr><td>15×10 优8]</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td></tr><tr><td>WOA最优 1325</td><td>1555</td><td>768</td><td>524</td><td>404</td><td>333</td><td>282</td><td>252</td><td>232</td><td>214</td></tr><tr><td>时间</td><td></td><td>736</td><td>506</td><td>390</td><td>326</td><td>287</td><td>253</td><td>223</td><td>205</td></tr><tr><td>15×10 [8]</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td><td>17</td><td>18</td></tr><tr><td>WOA最优 194</td><td>199</td><td>191</td><td>185</td><td>181</td><td>182</td><td>184</td><td>184</td><td>181</td><td>181</td></tr><tr><td>时间</td><td></td><td>186</td><td>180</td><td>176</td><td>170</td><td>170</td><td>170</td><td>170</td><td>170</td></tr></table></body></html>

图8表明AGV的边际效用符合边际效用递减规律，随着AGV数量的增加，总效用增加（整个加工时间减少)，但边际效用递减(增加一台AGV缩短的时间减少)。当 $\mathrm { A G V } { = } 1 5$ 时，边际效用为0，说明14台和15台AGV总效用相同，即总效用在 $\mathrm { A G V } { = } 1 4$ 时达到最大。此时加工时间主要受加工设备和工序的约束，不能通过简单的增加AGV来减少加工时间。

![](images/cb958a7ee4f80cbb152ee7846ade74a93a25232779fdd3e9212c0b69777eaa93.jpg)  
图8AGV的边际效用曲线

# 3.3.2学习效应和恶化效应

1）不考虑员工、工件的异质性

当员工初始技能，最终技能相同且工件开始恶化时间，停正恶化时间相同时，即不考虑员工、工件的异质性，来讨论不同学习率与不同恶化因子对完工时间的影响。由下表可看出，学习曲线从 $90 \%$ 到 $60 \%$ ，含AGV柔性车间调度问题的完工时间大大缩短（ $\mathbf { A G V } { = } 2$ )，即学习率越小，完工时间越小，即学习效应能够提高工厂生产率。同时可以发现，随着恶化因子的增加，完工时间逐渐增大，这表明较大的恶化因子相当于引起较大学习效果退化。

表7学习率及恶化因子对寻优结果的影响  

<html><body><table><tr><td>E31</td><td>取值</td><td>最优解</td></tr><tr><td>学习率</td><td>0.9</td><td>122</td></tr><tr><td>b=0.1</td><td>0.8</td><td>111.3004</td></tr><tr><td></td><td>0.7</td><td>107</td></tr><tr><td></td><td>0.6</td><td>105.7818</td></tr><tr><td>恶化因子</td><td>0.1</td><td>111.3004</td></tr><tr><td>1=0.8</td><td>0.15</td><td>114</td></tr><tr><td></td><td>0.2</td><td>119.476</td></tr><tr><td></td><td>0.25</td><td>122</td></tr></table></body></html>

# 2）考虑员工、工件的异质性

以EX31问题为仿真实例，对所有工件进行小批量生产，且批量为1，2，3，4，5。下面矩阵表示的是每个员工分别对每种工件的初始能力、最大能力、学习率，如矩阵中0.77（第二行第四列）表示，员工2（行）对工件2的初始能力0.77。其中工件的恶化因子为B=[0.20.20.10.20.15]，开始恶化时间t_min=[50,50,50,50,50] ， 恶化结束时间t_max=[100,100,100,100,100] 。

[0.85 0.78 0.8 0.91 0.78 0.80 0.80 0.70 0.80 0.80 0.70 0.80 0.88 0.70 0.80] 0.92 0.8 0.9 0.77 0.70 0.90 0.90 0.82 0.90 0.90 0.82 0.90 0.90 0.82 0.90 0.94 0.75 0.7 0.97 0.75 0.70 0.92 0.85 0.70 0.92 0.85 0.70 0.92 0.85 0.70 [0.800.6 0.75 0.93 0.80 0.75 0.75 0.70 0.75 0.75 0.70 0.75 0.82 0.70 0.75

图9\~11为当2个搬运机器人搬运时，讨论行为效应对单位批量完工时间的影响。

![](images/9af20e7ed7901eaad9dbbe9aed32dd4ce7b73d41b7b88d87795713a70b1b27b0.jpg)  
图9行为效应对单位批量完工时间的影响

![](images/08d866d21a5a8b348bfaabfd10a3a7388d8d77266c46d0f1db73f6f7f4fd36a5.jpg)  
图10行为效应对单位批量完工时间的影响

其中由图9可以看出：

同一批量下，只含学习效应的单位批量完工时间 $<$ 含学习恶化效应的单位批量完工时间 $<$ 无效应的单位批量完工时间 $<$ 只含恶化效应的单位批量完工时间；这说明批量 $^ { = 1 }$ ，AGV ${ \bf \bar { \rho } } = \boldsymbol { 2 } { \bf \rho }$ 时，工件开工时间不长，员工学习还未达到最大技能，工件处于刚开始恶化阶段，因此学习效应起的缩短时间的效果 $>$ 恶化效应增长时间的效果（批量 $^ { = 2 }$ ， $\mathbf { A G V } { = } 2$ 同理)。

相同效应下，批量为2的单位批量完工时间 $<$ 批量为1的单位批量完工时间。这说明，AGV常处于等待工序加工完成然后去运输到下一加工设备的阶段，即AGV资源不是瓶颈资源。

其中图10可以看出：

同一批量下，只含学习效应的单位批量完工时间 $<$ 无效应的单位批量完工时间 $<$ 含学习恶化效应的单位批量完工时间 $<$ 只含恶化效应的单位批量完工时间；这说明批量 $\scriptstyle : = 3$ ，AGV ${ \bf \bar { \rho } } = \boldsymbol { 2 } { \bf \rho }$ 时，工件开工时间较长，员工学习已达到最大技能，工件处于恶化阶段，因此恶化效应增长时间的效果 $>$ 学习效应缩短时间的效果（批量 $\scriptstyle = 3$ ，4，5， $\mathbf { A G V } { = } 2$ 同理）。

不同效应下，批量不同的单位批量完工时间大小关系在变化。这说明，AGV资源约束和各效应共同影响了单位批量完工时间。为了剔除效应的影响，进一步探究AGV资源约束与批量之间的内在关系，补充实验。

表8批量与AGV数量对单位批量完工时间的影响

<html><body><table><tr><td rowspan="3">E31</td><td colspan="6">无效应</td></tr><tr><td colspan="2">r=1</td><td colspan="2">r=2</td><td colspan="2">r=3</td></tr><tr><td>总完工时间</td><td>完工时间/批量</td><td>总完工时间</td><td>完工时间/批量</td><td>总完工时间</td><td>完工时间/批量</td></tr><tr><td>批量=1</td><td>186.00</td><td>186.00</td><td>112.00</td><td>112.00</td><td>90.00</td><td>90.00</td></tr><tr><td>批量=2</td><td>347.00</td><td>173.50</td><td>208.00</td><td>104.00</td><td>151.00</td><td>75.50</td></tr><tr><td>批量=3</td><td>507. 17</td><td>169.06</td><td>304.00</td><td>101. 33</td><td>222.00</td><td>74.00</td></tr><tr><td>批量=4</td><td>680.00</td><td>170.00</td><td>390.00</td><td>97.50</td><td>295.00</td><td>73.75</td></tr><tr><td>批量=5</td><td>864.00</td><td>172.80</td><td>498.00</td><td>99.60</td><td>365.00</td><td>73.00</td></tr></table></body></html>

![](images/f1a3648534afeaab276659b9e7a88ff5e7d0a662678225f0477bdbe4862dbae0.jpg)  
图11批量与AGV数量对单位批量完工时间的影响

由图11可以看出：

当批量相同时，搬运机器人越多，单位批量完工时间越短。搬运机器人为1和2时，随着批量越多，单位批量完工时间先降低后升高，且 $\scriptstyle \mathbf { r } = 1$ 时，批量 $\scriptstyle : = 3$ 时间最短， $\scriptstyle \mathbf { r } = 2$ 时，批量 $\scriptstyle : = 4$ 时间最短。当搬运机器人为3时，随着批量越多，单位批量完工时间越短。这说明搬运机器人为1和2时，由于工件批量变多，AGV变成瓶颈资源，加工设备需要等待AGV搬运工件才能开始加工，且搬运机器人为1较搬运机器人为2时，AGV变成瓶颈资源的批量更小，而搬运机器人为3时，AGV还未变成瓶颈资源。

学习效应、恶化效应现象在实际工厂生产制造过程中的确客观存在，同时由上实验可知，学习效应、恶化效应在生产制造过程中对调度的影响是不容忽视的。

# 4 结束语

本文采用基于工序、机床和AGV分配的编码方式[29]，用3L维向量表示1种可行的生产调度。并将混沌局部搜索策略运用到鲸鱼算法中，有效避免了迭代中易陷入局部最优解的问题。同时运用田口的鲁棒设计法求得最优参数组合。最后从算例表明了具有局部混沌搜索策略的鲸鱼算法具有较高的优化性能，并发现学习效应能够提高工厂生产率，恶化效应反之，相当于学习效果的退化；AGV资源约束和学习效应、恶化效应共同影响了单位批量完工时间；随着加工时间的推移，学习效应缩短工件加工时间的效果越来越明显，直到员工能力达到上限；当开工时间达到工件恶化时间时，恶化效应延长工件加工时间的效果越来越明显，直到超过最大恶化时间。影响工件加工时间的因素还有很多，比如遗忘效应、员工请假、员工倦怠，本文并没有涉及相关因素的探讨。因此在以后的研究有必要从更多的角度分析加工时间的影响因素。

参考文献：   
[1]Lacomme P,Larabi M,Tchernev N.Job-shop based framework for simultaneous scheduling of machines and automated guided vehicles [J]. International Journal of Production Economics,2013,143(1):24-34.   
[2]崔苗苗．带有学习与恶化效应的机器受限的总完工时间问题[J]．电子 测试，2017 (2):28-29.(Cui Miaomiao．Machine-constrained total completion time with learning and worsening efcts [J]. Electronic Test, 2017 (2): 28-29. )   
[3]汪佳．具有学习及恶化效应和资源分配的单机排序问题[D].沈阳：沈 阳航空航天大学,2016.(Wang Jia.A single machine scheduling problem with learning and deterioration effects and resource allocation [D]. Shenyang: Shenyang Aerospace University,2016.)   
[4] 李小平，陈活，许海燕，等．一种面向具有学习恶化效应无等待流水调 度问题的方法：中国,CN201610785498[P].2017-02-01.(Li Xiaoping, Chen Tian,Xu Haiyan,et al.A method for scheduling problems with learning deterioration efect is not available: China, CN 201610785498 [P] 2017-02-01. )   
[5]Tayebi Araghi ME,Jolai F,Rabiee M. Incorporating learning effect and deterioration for solvinga SDST flexible job-shop scheduling problem with a hybrid meta-heuristic approach [J].International Journal of Computer Integrated Manufacturing,2014,27 (8): 733-746.   
[6]Azzouz A,Ennigrou M,SaidLB.Aself-adaptive evolutionary algorithm for solving flexible job-shop problem with sequence dependent setup time and learning effcts [C]// Proc of IEEE Congress on Evolutionary Computation. 2017: 1827-1834.   
[7]Mir S,Saber M,Rezaeian J.Two meta-heuristic algorithms for parallel machines scheduling problem with past-sequence-dependent setup times and effects of deterioration and learning[J].International Journal of Industrial Engineering & Production Research,2016,27(1): 69-88.   
[8]Araghi M E T,Jolai F,Rabiee M. Incorporating learning effect and deterioration for solving a SDST flexible job-shop scheduling problem with a hybrid meta-heuristic approach [J]. International Journal of Computer Integrated Manufacturing,2014,27(8): 733-746.   
[9]Zhao Chuanli,Fang Ji,Cheng TCE,et al.Anote on the time complexity of machine scheduling with DeJong’s learning effect [J]. Computers& Industrial Engineering,2017,447-449.   
[10] Biskup D. Single-machine scheduling with learning considerations [J]. European Journal of Operational Research,1999,115(1):173-178.   
[11]于秀丽．人工作业系统(MOS）建模与员工组织优化[D]．广州：广东 工业大学,2013. (Yu Xiuli,Artificial operating system(MOS) modeling and employeeorganizationoptimization[D]. Guangzhou:Guangdong University of Technology,2013. )   
[12]曹磊，叶春明，黄霞．基于员工学习行为的多目标柔性车间调度

[J/OL].计算机集成制造系统,2018:1-21[2018-05-20].http://kns.cnki. net/kcms/detail/11.5946.TP.20170818.1120.008.html.(Cao Lei,Ye

Chunming,Huang xia.Multi-objective flexible shop scheduling based on employee learning behavior [J/OL]. Computer Integrated Manufacturing System,2018:1-21[2018-05-20]. http://kns.cnki.net/kcms/detail/11.5946. TP.20170818.1120.008.html.)

[13]Browne S,Yechiali U.Scheduling Deteriorating Jobs ona Single Processor [J]. Operations Research,1990,38 (3): 495-498.

[14] Wang X, Cheng TC E. Single-machine scheduling with deteriorating jobs and learning effects to minimize the makespan [J]. European Journal of Operational Research,2007,178(1): 57-70.   
[15]龙传泽，杨煜俊．基于遗传算法的柔性机器人制造单元调度问题研究 [J].组合加工设备与加工技术,2015,148(11):141-144.(Long Chuanze, Yang Yijun. Research on the scheduling problem of flexible robot manufacturing based on genetic algorithm [J]. Combination Processing Equipmentand Procesing Technology,2015,148 (11):141-144.)   
[16] Mirjalili S,Lewis A.The whale optimization algorithm [J].Advances in Engineering Software,2016,95: 51-67.   
[17]钟明辉，龙文．一种随机调整控制参数的鲸鱼优化算法[J].科学技术 与工程，2017(12): 68-73.(Zhong Minghui,Long Wen.Awhale optimization algorithm for stochastic control parameters [J].Science Technology and Engineering,2017(12): 68-73.)   
[18]刘竹松，李生．正余混沌双弦鲸鱼优化算法[J].计算机工程与应用， 2018（7).(Liu Zhusong,Li Zheng. The optimization algorithm of doublestring whale in thepositive chaos [J].Computer Engineeringand Applications,2018 (7) .)   
[19]贾兆红，陈华平，孙耀晖．多目标粒子群优化算法在柔性车间调度中的 应用[J].小型微型计算机系统，2008,29(5):885-889.(Jia Zhaohong, Chen Pinghua,Sun Yaohui. Application of multi-objective particle swarm optimizationalgorithmin flexible shop scheduling[J].Mini-Micro Systems, 2008,29 (5): 885-889. )   
[20]刘长平，叶春明．基于逻辑自映射的变尺度混沌粒子群优化算法[J] 计算机应用研究,2011,28 (8):2825-282.(Liu Changping,Ye Chunming. A variable scale chaotic particle swarm optimization algorithm based on logical self-mapping [J].Application Research Of Computers,2011,28 (8): 2825-282. )   
[21] Kacem I, Hammadi S,Borne P.Approach by localization and multiobjective evolutionary optimization for flexible job-shop scheduling problems [J]. IEEE Trans on Systems, Man,and Cybernetics,Part C: Applications and Reviews,2002,32(1): 1-13.   
[22] Bilge U, Ulusoy G.A Time window approach to simultaneous scheduling of machines and material handling system in FMS [J]. Operations Research, 1995, 43 (6): 1058-1070.   
[23] Erol R,Sahin C,Baykasoglu A,et al.A multi-agent based approach to dynamic scheduling of machines and automated guided vehicles in manufacturing systems [J].Applied Soft Computing,2012,12 (6): 1720- 1732.   
[24]龙传泽．柔性多机器人制造单元调度算法研究「Dl.广州：广东工业大

学,2015.(Long Chuanze.Research on scheduling algorithm of flexible multi-robot manufacturing unit [D]. Guangzhou: Guangdong University of Technology,2015.)

[25] Kumar MV S,Janardhana R,Rao C SP. Simultaneous scheduling of machines and vehicles in an FMS environment with alternative routing [J]. International Journal of Advanced Manufacturing Technology,2011,53(1- 4): 339-351.

[26] Sahin C,Demirtas M,ErolR,et al.Amulti-agent based approach to dynamic scheduling with flexible processing capabilities [J].Journal of Intelligent Manufacturing,2017,28(8): 1827-1845.

[27]李阳，王玉．基于边际效用函数的最佳人力资源管理模型研究[J]．系

统工程理论与实践,2016,36(1):106-112.(Li Yang,Yu Yu.Research on optimal human resource management model based on marginal utility function [J]. System Engineering Theory and Practice,2016,36 (1):106- 112.)   
[28]MousaviM,Yap HJ,Musa SN,et al.Multi-objective AGV scheduling in an FMS using a hybrid of genetic algorithm and particle swarm optimization [J].PLoS One,2017,12 (3): 1-24.   
[29]徐云琴，叶春明，曹磊.含有 AGV的柔性车间调度优化研究[J].计算 机应用研究,2018,35(11).(Xu Yunqin,Ye Chunming,Cao Lei.Research on flexible Job-Shop scheduling problem with AGV constraints [J]. Application Research Of Computers,2018,35(11) .)