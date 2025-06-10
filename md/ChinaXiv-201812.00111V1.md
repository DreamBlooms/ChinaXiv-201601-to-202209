# 突发事件下的医院应急资源动态分配模型研究

万志远，刘勤明，叶春明，刘文溢(上海理工大学 管理学院，上海 200093)

摘要：针对突发事件下医院里应急资源的供需不平衡问题，进行了医院应急资源动态分配模型研究。考虑到病人数量的增多以及病人的伤情演变导致医院应急资源供应相对紧缺，基于序贯决策理论，将病人需求的变化设计成一个马尔可夫决策过程，建立了医院应急资源动态分配模型。使用基本粒子群算法求解，通过某次地震发生后医院的救援实例进行分析。案例分析表明，马尔可夫决策过程可以动态地满足伤情演变下不同状态病人的需求，使得应急救援中整体的资源利用达到最优。

关键词：突发事件；资源分配；伤情演变；序贯决策；马尔可夫过程 中图分类号：C934；TP391 doi:10.19734/j.issn.1001-3695.2018.07.0529

Research on hospital emergency resource dynamic allocation model under emergencies

Wan Zhiyuan,Liu Qinming, Ye Chunming,Liu Wenyi (Business School,University of Shanghai for Science &Technology,Shanghai 2Ooo93,China)

Abstract:This paperstudies the dynamic alocation model of hospital emergencyresources inresponse to the imbalance betweensupply anddemand of emergencyresources in hospitals under emergencies.The emergency resource supply in the hospital is relatively scarce duetothe increase inthenumberof patientsandthe evolutionof thepatient's injury.Basedon thesequential decision theory，this paper designs the changes of patient needs into a Markov decision process and establishes a dynamic allcation model of hospital emergencyresources.Then the model is solvedby using the basic particle swarm optimization algorithm,which is analyzed byarescue example ofthe hospital after anearthquake.Thecase study shows that the Markov decision-making processcan dynamically meet the needs of patients in diferent states under the evolution of injuries,making the overall resource utilization in emergency rescues to be optimal.

Key words: emergencies; resource allocation; evolution of injuries; sequential decision-making; Markov process

# 0 引言

医疗应急是突发事件下应急管理和应急决策的核心问题，医院是应急救援的重要地点，其应急服务资源的及时供应是提高救治率的有效保障。突发事件具有不断演变、多阶段、不确定性的特征，应急救援过程中需要科学的应急决策。

陈述等人[1根据多属性决策理论，将重大突发事件的应急决策问题抽象成多目标优化模型。Botega等人[2l认为情境意识（SAW）是一种广泛传播于需要关键决策应用领域的概念，例如应急调度系统，突发事件中的情景演变过程及发展态势复杂是一种动态变化问题。郑昊等人[3结合应急系统中多点出救的特征，在资源消耗速率为非负可积函数的情况下，构建了基于应急时间最早的连续型应急资源调度模型。复杂环境下决策者对于应急事件作出的决策往往会面对偏好转移的问题，徐选华等人[4提出了一种新的大群体风险型动态应急决策方法。张敏[5运用冲突管理的基本原理，提出了博弈论指导下代表最大利益一方的最优决策模型。突发事件应急决策问题具有典型的复杂系统特性，王刚桥等人[深入分析了传统决策问题和应急决策问题之间的差异，提出了面向突发事件的"基于跨域仿真的应急决策方法”。为了更好的在突发事件下的应急决策中动态地调整方案，姜艳萍等人[7构建了一种基于风险评估的风险决策方法。Luscombe等人[8:9]提出动态调度框架，为管理紧急部门的稀缺资源提供实时支持。刘长石等人[10'研究了应急调度过程中的最短路径问题，根据需求分割策略，建立了一个突发事件下应急物资多种方式供应的多周期模糊优化模型。应急过程中，应急物资的供应与配送处于不同受灾点需求不确定、需求程度不一致和运输途径动态变化的复杂现实环境，田军等人[12:13]基于动态模糊逻辑对这些问题进行了分析，为突发事件下的动态应急决策提供了新的思路和理论方法。由于社会变化和公众需求增加，救护车召唤的人数不断增加，导致成本增加和人员短缺。Mould-Millman等人[14:15]研究了动态的数据驱动紧急医疗服务决策支持系统，为医院外急救护理资源和专业知识提供了一种手段。当前针对医院应急资源分配优化的研究还不多，大多数的研究也仅仅通过事前制定好的静态应急预案或经验作为应急策略。因此，针对突发事件下医院里应急资源的供需不平衡问题，本文进行了医院应急资源动态分配模型研究。

# 1 模型描述

# 1.1序贯决策下基于伤情状态演变的马尔可夫决策过程

在研究决策问题时，不是事先规定样本的数量，而是逐个取样，直到样本提供足够的信息，能帮助决策者恰当地作出决策为止，这样的统计决策过程称为序贯分析。本文根据系统中某一次观察到的信息，从可用的行动集合中选用一个行动作出决策，系统下一步的状态是随机的，且这种状态的转移概率具有马尔可夫性，对于这样有着无后效状态转移的决策系统，其相应的序贯分析决策过程称为马尔可夫决策过程。在现阶段已有的预测模型中，这种决策过程要更加的简单，它可以为系统的状态演化趋势提供一套可以量化的方案，很适合本文的数学建模，因此将其应用于本文的突发事件下医院的应急资源决策分配。

突发事件发生后，被送到医院的病人对医院的应急资源有了需求，导致医院的医疗服务资源及时供应压力加大，突发事件下的医院应急管理要求其能够短时间内迅速调度全部应急资源。假设 $J$ 为病人 $j$ 的集合， $J = \{ j | 1 , 2 , 3 \cdots , j _ { m a x } \}$ ， $K$ 为医院应急资源 $k$ 的集合， $K = \{ k | 1 , 2 , 3 \cdots , k _ { m a x } \}$ ，将突发事件下的医院应急资源分配问题设计成一个动态多阶段的应急决策问题，将各阶段的表示为集合 $T = \{ t | 1 , 2 , 3 \cdots , t _ { m a x } \}$ 。在医院里应急资源供需不平衡的现实环境下，在某个阶段，某个病人的应急资源需求能完全被分配到称为该病人的需求被"满足”，资源需求和病人的伤情相关。假设在每一个决策阶段，要对每个病人的应急资源需求是否要现在满足或者是到下一个阶段再满足进行决策。因此，本文的医院应急决策框架是动态性的"现在满足病人需求&将来满足病人需求”，和传统静态性的"现在满足病人需求&现在不满足病人需求"决策框架。将是否满足在阶段 $t$ 时病人 $j$ 对资源 $k$ 的需求决策变量记为$Z _ { j } ^ { \prime }$ ，则：

$$
Z _ { j } ^ { t } = \left\{ { \begin{array} { l l } { 1 } & { { \ddag } { \iiint } \boldsymbol { \ddot { f } } { \ddot { \varphi } } _ { x } ^ { t } t \ \mathrm { ~ j } \varlimsup _ { j } { \bigwedge } j \not \forall j \qquad \mathrm { ~ j } \not \in \dot { g } \not \} _ { \overrightarrow { \mathrm { f f } } } \not \equiv \not \exists \not \times \dot { g } { \downarrow } \not \in \dot { p } { \downarrow } \not \in \qquad } \\ { 0 } & { \underset { \array} { \bigoplus } \iiint } \end{array} } \right. ,
$$

在不同的阶段，病人的伤情以及资源需求是不同的，决策者在某阶段作出了是否满足需求的决策，决策结果的不同会影响下一阶段的决策过程，这是一个常见的动态规划问题。设需求状态集为：

$$
\mathcal { S } = \{ \theta | 1 , 2 , \cdots , \mathcal { S } _ { m a x } \}
$$

该状态代表应急需求资源的规模，也能反映与病人伤情直接相关的需求需要被满足的迫切程度。其中1表示伤重程度为轻，数值越大意味着病人伤情越重，病人的需求越多，需求越需要优先被满足。显然，病人的伤情状态因医院的服务水平、服务环境以及病人自身的年龄、性别、体质，特别是因阶段（时间）的不同而异。

为了反映这种现象，设计一个参数 $G _ { j k } ^ { t }$ 来表示在 $t$ 阶段时病人 $j$ 对资源 $k$ 的需求状态。比如， $G _ { j k } ^ { 1 } = 2$ 表示在1阶段时病人 $j$ 对资源 $k$ 的需求状态为2。对于这样的状态，有如下几个性质：

性质1在病人的需求未被完全满足的情况下，其需求状态是一个单调不减函数。

假设所有病人的需求只能由决策者提供的应急服务资源而得到满足。在病人的需求未被完全满足的情况下，根据病人的伤情演变趋势，随着时间的推迟，病人的需求量只可能增加或不变，而不可能会减少。在病人需求未被完全满足的前提下有

$$
G _ { j k } ^ { t _ { 1 } } \le G _ { j k } ^ { t _ { 2 } }
$$

其中： $t _ { 1 } , t _ { 2 } \in T$ ，且 $1 \leq t _ { 1 } \leq t _ { 2 } \leq t _ { m a x }$ 。

性质2病人需求状态的变化是随机的。

因为各个病人需求的不同和不确定性，两个相邻阶段之间病人的需求状态转移是随机的，它只因当前阶段的需求状态和将来的需求状态变化而变化，所以 $G _ { j k } ^ { t }$ 实质上是一个随机变量。如果在某个阶段的需求状态为 $\theta _ { \mathrm { { l } } }$ ，则伤情演化一个阶段后需求状态为 $\theta _ { 2 }$ （ $1 \leq \theta _ { 1 } , \theta _ { 2 } \leq \theta _ { m a x }$ ）的概率为 $R _ { j k } \left( \theta _ { 1 } , \theta _ { 2 } \right)$ ，称之为状态转移概率。其组成的病人需求状态转移概率矩阵为$R _ { j k }$ ，且 $R _ { j k }$ 是一个上三角矩阵，矩阵里对角线下面的各个元素都是0。

$$
R _ { j k } = \left[ \begin{array} { c c c c } { R _ { j k } \left( 1 , 1 \right) } & { R _ { j k } \left( 1 , 2 \right) } & { \cdots } & { R _ { j k } \left( 1 , \theta _ { m a x } \right) } \\ & { R _ { j k } \left( 2 , 2 \right) } & { \cdots } & { R _ { j k } \left( 2 , \theta _ { m a x } \right) } \\ & { \ddots } & { \vdots } \\ & & & { R _ { j k } \left( \theta _ { m a x } , \theta _ { m a x } \right) } \end{array} \right]
$$

在各个病人的需求未被完全满足的情况下，按照病人自身伤情演变趋势而自然演变的需求状态值称之为“自然值”，用 $\tilde { G } _ { j k } ^ { t }$ 表示为在阶段 $t$ 时病人 $j$ 对资源 $k$ 需求的"自然值”。由$\tilde { G } _ { j k } ^ { t }$ 在不同阶段产生的"自然值"序列 $\tilde { G } _ { j k } ^ { 1 } , \tilde { G } _ { j k } ^ { 2 } , \cdots$ 是一个马尔可夫链。其下一阶段的"自然值"只和当前阶段的病人需求状态有关，与以前的需求状态无关。将病人在 $t + 1$ 阶段时"自然值”的期望表示为 $E G _ { j k } ^ { t + 1 }$ ，有

$$
E \tilde { G } _ { j k } ^ { t + 1 } = \sum _ { \theta = \tilde { G } _ { j k } ^ { \prime } } ^ { \theta _ { m a x } } \theta \cdot R _ { j k } \left( \tilde { G } _ { j k } ^ { t } , \theta \right)
$$

显然 $E \tilde { G } _ { j k } ^ { t + 1 }$ 并不一定是整数，本文在前面假设了病人的需求状态数值是非负整数，所以 $E \tilde { G } _ { j k } ^ { t + 1 }$ 并不一定会和病人需求状态的取值点重合，即 $E \tilde { G } _ { j k } ^ { t + 1 } \neq \tilde { G } _ { j k } ^ { t + 1 }$ 。两个数值只有在相邻时间趋向于0时才会相等。设 $\mathrm { ~ L ~ }$ 为相邻时间，则当 $\mathrm { ~ L ~ }$ 趋向于0时，

$$
\operatorname * { l i m } _ { L  0 } E \tilde { G } _ { j k } ^ { t + 1 } = \tilde { G } _ { j k } ^ { t + 1 }
$$

证明当 $H \to 0$ 时，状态的取值是连续的， $\tilde { G } _ { j k } ^ { t + 1 }$ 的取值范围变为 $\left[ \tilde { G } _ { j k } ^ { t } , \theta _ { m a x } \right]$ 上的所有的点。因此 $E \tilde { G } _ { j k } ^ { t + 1 }$ 必然会和病人需求状态的取值点相重合。然而连续性的决策问题很难解决，为了使公式的等号成立，将连续型决策转换为离散型决策，因此对式（4）等式的右项进行取整，得到相邻时间“自然值”之间的病人需求状态转移公式：

$$
\tilde { G } _ { j k } ^ { t + 1 } = r o u n d \left( \sum _ { \theta = \tilde { G } _ { j k } ^ { t } } ^ { \theta _ { m a x } } \theta \cdot R _ { j k } \left( \tilde { G } _ { j k } ^ { t } , \theta \right) \right)
$$

其中，round $( x )$ 表示对 $x$ 进行随机取整，其方法见式（7)，该公式可以使 $x$ 尽可能的与自身最接近的整数进行取值。其中，rand 表示[0,1]之间的随机数， $[ x ]$ 表示 $x$ 的整数部分。

$$
r o u n d ( x ) = \{ \begin{array} { l l } { { [ x ] } } & { { \ddag \ddag r a n d \ge ( x - [ x ] ) } } \\ { { [ x ] + 1 } } & { { \ddag \ddag | \Downarrow \downarrow } } \end{array} 
$$

除了式(6)，还需规定一个初始值：

$$
{ \tilde { G } } _ { j k } ^ { 1 } = \theta _ { j k } ^ { 0 }
$$

其中， $\theta _ { j k } ^ { 0 } \in \mathcal { S }$ 0

性质3若在某个阶段，病人的需求被完全满足，则其需求状态值将回会变为需求的初始值，然后再重新开始需求状态演变的过程。

如果在病人需求可能被完全满足的情况下，病人需求状态的自然演变过程受到了干扰，本文将其变化值之为"干扰值”，将 $\hat { C } _ { j k } ^ { t }$ 表示为在阶段 $\textit { t }$ 时病人 $j$ 对资源 $k$ 需求的"干扰值”。在式（6）和（8）中加入干扰行为产生对病人需求状态转移的影响，得出相邻时间里"干扰值"之间的状态转移方程为

$$
\hat { G } _ { j k } ^ { t } = \left\{ \begin{array} { c c } { \theta _ { j k } ^ { \scriptscriptstyle 0 } } & { \vec { \Xi } t = 1 } \\ { \big ( \theta _ { j k } ^ { \scriptscriptstyle 0 } \big ) ^ { Z _ { j } ^ { t } } \cdot \left( r o u n d \left( \begin{array} { c c } { \frac { \theta _ { m a x } } { \theta _ { j k } ^ { \scriptscriptstyle 0 } } } \end{array} \theta \cdot R _ { j k } \big ( \hat { G } _ { j k } ^ { t - 1 } , \theta \big ) \right) \right) ^ { 1 - Z _ { j } ^ { t } } } & { \overset { , , } { \vec { \Xi } \mathrm { 1 } } \mathtt { M } \mathtt { M } } \end{array} \right.
$$

在各阶段病人需求状态的"干扰值"被计算得到后，需要继续求出病人需求值，因此需要定义一个公式：病人的需求与其需求状态成正比，设 $\mu _ { j k }$ 是根据病人的年龄、性别、伤重程度、身体素质等因素综合得到的权重因子，则在阶段 $t$ 时病人 $j$ 对资源 $k$ 的需求为

$$
\begin{array} { r } { d _ { j k } ^ { t } = \left( \hat { G } _ { j k } ^ { t } - 1 \right) \mu _ { j k } } \end{array}
$$

# 1.2医院应急资源动态分配模型的建立

突发事件下的医院应急资源是指在突发事件下医院应急管理中能够短时间内迅速征调或积极响应的全部各类资源的总称，应急资源主要有人力、物力等多种存在形式。人力资源主要包括决策指挥人员、医疗专家人员、医疗咨询人员和后勤辅助人员等资源；物质资源主要包括基础设施、医疗技术设备、应急物资和药品等资源。突发事件下医院应急管理和决策不同于一般事件的资源调度，医院应急救援的首要原则是最快地满足病人的资源需求，实效的重要性明显优先于低成本的重要性。

医院应急服务资源的分配和使用不是单阶段的工作，需要根据实际的情况变化和前一阶段的效果，动态地、多阶段地分配应急资源，直至救援完成。突发事件本身的随机变化与动态性等性质决定了应急管理的资源分配是一个动态的多阶段过程。相对于大量病人的需求而言，资源总是表现出相对的稀缺性，从而要求决策者对有限的、相对稀缺的资源进行合理配置，以便用最少的资源耗费，满足救援目的。

本文将医院决策指挥人员作为模型的决策者，决策对象为突发事件发生后被送到医院的病人，医院的关键资源为医生和护士，模型的决策过程主要是医生和护士资源对病人动态多阶段的需求满足。在此基础上，本文的目标函数为

$$
\mathrm { m i n } \sum _ { j \in J } \sum _ { k \in K } \sum _ { t \in T } S d _ { j k } ^ { t }
$$

其中： $S d _ { j k } ^ { t }$ 表示在阶段 $t$ 时病人 $j$ 对资源 $k$ 的需求。因为病人需求的演变与决策者对病人的需求满足策略紧密相关，一个迅速及时有效的需求满足策略能够最大限度的拖延病人需求的演变过程，本文以最小化所有阶段所有病人的需求总和作为目标。

除了式（1）～（10）之外，本文还需要增加两个约束条件：

$$
S d _ { j k } ^ { t } = \frac { d _ { j k } ^ { t } - d _ { j k } ^ { \Delta } } { d _ { j k } ^ { \nabla } - d _ { j k } ^ { \Delta } }
$$

$$
\sum _ { j \in J } Z _ { j } ^ { t } \cdot d _ { j k } ^ { t } \leq S _ { k } ^ { t }
$$

因为医院里的应急资源的种类不同，而且不同种类资源数量不一样，所以需要通过式(12)对应急资源进行归一化整合，从而得到一个统一的需求值 $\boldsymbol { S } \boldsymbol { d } _ { j k } ^ { t }$ 。其中 $\boldsymbol { d } _ { j k } ^ { \nabla }$ 和 $\boldsymbol { d } _ { j k } ^ { \Delta }$ 分别表示病人 $j$ 对应急资源 $k$ 需求的最大值和最小值。式(13)表示在各个阶段病人被完全满足的需求量总和不能超过实际的医院里应急资源的供应量总和，其中 $\boldsymbol { S } _ { \boldsymbol { k } } ^ { t }$ 表示在阶段 $t$ 时对资源 $k$ 需求供应的上限。

# 2 模型求解

由于本文的医院应急资源决策分配模型是在突发事件发生的情况下，所以模型对其求解时间的要求较高。粒子群优化算法属于进化算法的一种，与模拟退火算法有很多相似的地方，它从随机解出发，通过迭代寻找最优解，根据适应度评价解得品质，最后收敛于全局最优解。与遗传算法相比较，它的规则更简单，没有遗传算法的交叉和变异操作，计算速度快，通过追寻当前搜索到的最优值来寻找全局最优，对于种群规模并不敏感。粒子群算法以其实现容易、收敛快、精度高等优点适用于众多的优化问题。

算法基本描述如下：在维数为 $M$ 的空间里有 $I$ 个粒子，粒子的最大进化代数为 $n _ { m a x }$ 。第 $i$ 个粒子进化到第 $n$ 代（ $n = 1 , 2 , \cdots , n _ { m a x } - 1$ ）的位置为 $X _ { i } ^ { ( n ) } = \left\{ X _ { i 1 } ^ { ( n ) } , X _ { i 2 } ^ { ( n ) } , \cdots , X _ { i M } ^ { ( n ) } \right\}$ ，速度为 $V _ { i } ^ { ( n ) } = \left\{ V _ { i 1 } ^ { ( n ) } , V _ { i 2 } ^ { ( n ) } , \cdots , V _ { i M } ^ { ( n ) } \right\}$ ，计算过程中粒子与目标函数有关联的适应度函数相对应。单个粒子在运行过程中的个体最优位置记为 $P _ { i } ^ { ( n ) } = \left\{ P _ { i 1 } ^ { ( n ) } , P _ { i 2 } ^ { ( n ) } , \cdots , P _ { i M } ^ { ( n ) } \right\}$ ，所有粒子的全局最优位置记为$P _ { g } ^ { ( n ) } = \left\{ P _ { g 1 } ^ { ( n ) } , P _ { g 2 } ^ { ( n ) } , \cdots , P _ { g M } ^ { ( n ) } \right\}$

# 2.1粒子位置和速度更新

本文涉及的是离散空间的优化问题。由于决策变量 $\boldsymbol { Z } _ { j } ^ { t }$ 是0-1整数变量，所以将粒子的维度设为 $( { j _ { m a x } } \times t _ { m a x } )$ ，即$M = j _ { m a x } \times t _ { m a x }$ 。将 $ { \boldsymbol { X } } _ { i j t } ^ { n }$ 表示第 $i$ 个粒子进化到第 $n$ 代的位置矩阵的第 $j$ 行第 $t$ 列的元素，同样地，粒子速度、个体最优位置和全局最优位置矩阵内的元素分别记为 $V _ { i j t } ^ { n }$ 、 $P _ { i j t } ^ { n }$ 、 $P _ { g j t } ^ { n }$ 为了保证粒子的初始位置和更新后的位置与目标函数值相对应，设计粒子初始位置和初始速度分别为

$$
X _ { i j t } ^ { 0 } = \left\{ { 0 \atop 1 } \right. \stackrel { \# } { \mathop { \mathbb { E } } ^ { * } } r a n d < 0 . 5
$$

$$
V _ { i j t } ^ { 0 } = r a n d
$$

然后，设计粒子速度的更新公式分别为

$$
V _ { i j t } ^ { n + 1 } = w \pmb { V } _ { i j t } ^ { n } + c _ { 1 } \cdot r a n d \cdot \left( P _ { i j t } ^ { n } - X _ { i j t } ^ { n } \right) + c _ { 2 } \cdot r a n d \cdot \left( P _ { g j t } ^ { n } - X _ { i j t } ^ { n } \right)
$$

其中： $w$ 为惯性权重， $c _ { 1 } \setminus c _ { 2 }$ 为学习因子。

由于速度需要映射到[0,1]区间，需要让更新后的速度转换为位置取1的概率，使用sigmoid函数：

$$
S V _ { i j t } ^ { n + 1 } = \left( 1 + e ^ { - V _ { i j t } ^ { n + 1 } } \right) ^ { - 1 }
$$

继而设计粒子位置的更新公式为

$$
X _ { i j t } ^ { n + 1 } = \{ \begin{array} { l l } { 0 } & { \stackrel { \scriptscriptstyle +  } { \mathrm { / } } r a n d < S V _ { i j t } ^ { n + 1 } } \\ { 1 } & { \stackrel { \scriptscriptstyle \bigwedge } { \mathrm { / } } \mathbb { M } } \end{array} 
$$

式（13)是不等式约束，将其合并到原目标函数式(11)中，

如下：

$$
F i t _ { i } ^ { n } = \operatorname* { m i n } _ { \substack { j \in J k \in K } } \sum _ { t \in T } S d _ { j k } ^ { t } + \sum _ { k \in K t \in T } \bigg | m i n \bigg ( 0 , S _ { k } ^ { t } - \sum _ { j \in J } \big ( X _ { i j t } ^ { n } \mathcal { U } _ { j k } ^ { t } \big ) \bigg ) \bigg |
$$

其中，记 $F i t _ { i } ^ { n }$ 为第 $n$ 代第 $i$ 个粒子的适应度函数。

# 2.2算法步骤

粒子群算法求解医院应急资源决策问题的求解过程如下。

a)初始化 $n = 0$ ：

b)通过式(14)和(18)对粒子的位置进行初始化和更新，通过式(15)和(16)对粒子的速度进行初始化和更新;

c)通过式（19）计算适应度函数；

d)计算个体的最优值最优位置，计算全局最优值和最优位置；

e)比较n与 $n _ { m a x }$ ：若 $n \neq n _ { { } _ { m a x } }$ ，转到步骤f)，若 $n = n _ { { } _ { m a x } }$ ，转到步骤 $\mathbf { g } ^ { \cdot }$ ：

f)置 $n = n + 1$ ，转到步骤b);  
g)停止计算，输出全局最优值和最优位置。

# 3 算例分析

# 3.1算例描述

设某自然灾害发生后，某医院在应急救援的过程中，有$j$ 名病人急需 $k$ 种医疗资源，病人对应急资源（主要是医生和护士）的需求不断发生动态演变，假设需求有三个状态，其伤重程度与需求状态对比表、需求状态转移概率矩阵和基准需求数据分别如表1\~3所示。假设医院应急资源分配过程中每个阶段的应急资源储备对医生和护士的供应分别为5人和14人。

# 3.2算例分析

在CPU为 $3 . 4 ~ \mathrm { G H z }$ 、内存为4GB的计算机上，通过MATLABR2017a编程求解。设置种群数量为200，最大进化的次数取值为200，惯性权重的取值为0.7298，两个学习因子的取值都为1.49445。连续运行程序20次，求解时间在13.40212\~13.82192(s)之间，说明该求解的结果和时间都具有较高的稳定性。求解结果的适应度函数变化曲线如图1所示。

表1伤重程度与需求状态对比表  
Table 2Patient transfer probability matrix for doctors and nurses   

<html><body><table><tr><td>需求程度</td><td>轻中重</td><td></td><td></td></tr><tr><td>需求状态值</td><td>1</td><td>2</td><td>3</td></tr></table></body></html>

表2病人对医生和对护士的需求状态转移概率矩阵

1%   

<html><body><table><tr><td></td><td colspan="3">病人1</td><td colspan="3">病人2</td><td colspan="3">病人3</td><td colspan="3">病人4</td><td colspan="3">病人5</td><td colspan="3">病人6</td></tr><tr><td rowspan="3">医生</td><td>20</td><td>41</td><td>39</td><td>15</td><td>30</td><td>55</td><td>25</td><td>40</td><td>35</td><td></td><td>535</td><td>60</td><td>35</td><td>20</td><td>45</td><td></td><td>22 38</td><td>40</td></tr><tr><td>0</td><td>40</td><td>60</td><td></td><td>045</td><td>55</td><td></td><td>56</td><td>44</td><td>0</td><td>65</td><td>35</td><td>0</td><td>43</td><td>57</td><td>0</td><td>35</td><td>65</td></tr><tr><td>0</td><td>0</td><td>100</td><td>0</td><td>0</td><td>100</td><td></td><td>0</td><td>100</td><td>0</td><td>0</td><td>100</td><td></td><td>0</td><td>100</td><td></td><td>0</td><td>100</td></tr><tr><td rowspan="3">护士</td><td>35</td><td>50</td><td>15</td><td>40</td><td>45</td><td>15</td><td>36</td><td>51</td><td></td><td>15</td><td>45 40</td><td></td><td>32</td><td>43</td><td>25</td><td>25</td><td>45</td><td>30</td></tr><tr><td>0</td><td>54</td><td>46</td><td>0</td><td>48</td><td>52</td><td>0</td><td>44</td><td></td><td>0</td><td>45 55</td><td></td><td>0</td><td>41 59</td><td></td><td>0 50</td><td>50</td><td></td></tr><tr><td>0</td><td>0 100</td><td></td><td>0</td><td>0 100</td><td></td><td>0</td><td>0 100</td><td></td><td>0</td><td>100</td><td></td><td>0</td><td>100</td><td></td><td>0 0</td><td>100</td><td></td></tr></table></body></html>

表3病人的基准需求（单位：人）/状态初始值

Table 3Patient's baseline demand (unit: person) / state initial value   

<html><body><table><tr><td></td><td>病人1</td><td>病人2</td><td>病人3</td><td>病人4</td><td>病人5</td><td>病人6</td></tr><tr><td>医生</td><td>1/2</td><td>1/1</td><td>2/2</td><td>2/3</td><td>2/3</td><td>1/2</td></tr><tr><td>护士</td><td>4/3</td><td>2/2</td><td>2/3</td><td>3/1</td><td>4/1</td><td>3/3</td></tr></table></body></html>

![](images/398de4287ffc8064851a7025673cc9aef565ea7f0bc5d5426451f176a61fc668.jpg)  
图1适应度函数的变化曲线  
Fig.1Variation curve of fitness function

需求满足的最优策略如表4所示。因为医院应急资源供不应求，所以每个阶段都无法完全满足全部的病人需求，只能有选择地满足。相对来说，病人3、4、5获得需求满足的机会比另外三个病人更多。图2为这一现象给出了理由。

在图2中，蓝色曲线代表的是需求状态在没有需求满足策略干扰下的“自然值"变化曲线，该曲线反映了需求状态演变的马尔可夫过程。显然，病人2、4、5的资源需求较紧急，究其原因可能是病人2、4、5的基准需求较大，而另外三个病人则基准需求较少。针对需求较大的病人，应优先考虑，需求满足策略应优先支持，表4的结果也表明了这一点。

而需求满足的效果也是病人2、4、5更好些，包括：

a）需求满足策略是总的资源需求显著减少。图2中两种颜色曲线之间的区域面积是两种需求状态变化曲线与坐标轴围合面积之差，它代表需求满足策略使总需求的减少量，显然病人2、4、5的两种曲线之间的区域面积更大。

b）需求满足策略使需求变化曲线趋向平缓。图2中的橙色曲线代表的是需求状态在需求满足策略干扰下的“干扰值"变化曲线。所有需求状态点的“干扰值”曲线总体走势都趋于平缓。

综上所述，本文的马尔可夫决策方法可以动态地作出合适的需求满足策略，使得整体的需求状态走势保持平稳，整体的需求水平降到最低。在突发事件下资源稀缺供应不足的环境下，本文的决策方法选择需求演变较快、基准需求较大的病人作为优先救援对象，并随时间的推移动态地调整需求满足策略，使得应急资源分配的公平性和效率性从整个应急救援计划的角度来看保持平衡。需求的马尔可夫过程很好地演示了需求状态演变规律。

Table1 Comparison of injury severity and demand status   
表4需求满足的最优策略  
Table 4Optimal strategies for demand satisfaction   

<html><body><table><tr><td></td><td>病人1</td><td>病人2</td><td>病人3</td><td>病人4</td><td>病人5</td><td>病人6</td></tr><tr><td>阶段1</td><td></td><td></td><td>满足</td><td>满足</td><td>满足</td><td></td></tr><tr><td>阶段2</td><td>满足</td><td></td><td></td><td></td><td>满足</td><td></td></tr><tr><td>阶段3</td><td></td><td>满足</td><td></td><td>满足</td><td></td><td>满足</td></tr><tr><td>阶段4</td><td>满足</td><td></td><td>满足</td><td></td><td>满足</td><td>满足</td></tr></table></body></html>

![](images/b6eb681a7673c572731b03bfa9a21ad5a1b954b4017962e760b246c56789c1a2.jpg)  
图2自然值"和"干扰值"变化曲线  
Fig.2"Natural value"and "interference value"curve

# 4 结束语

针对突发事件下医院里应急资源的供需不平衡问题，进行了医院应急资源动态分配模型研究。考虑到病人数量的增多以及病人的伤情演变导致医院应急资源供应相对紧缺，基于序贯决策理论，将病人需求的变化设计成一个马尔可夫决策过程，建立了医院应急资源动态分配模型。本文的主要创新是，为突发事件下医院里病人由于伤情演变而导致需求的演变设计了一种符合其演变规律的决策过程，提出医院病人需求满足的最优策略，然后通过某次地震发生后医院的救援实例进行分析。案例分析表明，马尔可夫决策过程可以动态地满足伤情演变下不同状态病人的需求，使得应急救援中整

体的资源利用达到最优。

本文的模型仍然较为理想化，现实环境下医院应急决策所面对的实际情况更为复杂，考虑的因素也会有更多。有待进一步研究的方向包括：研究更复杂的多种医疗应急资源分配网络，研究更优的求解算法等。

# 参考文献：

[1]陈述，余迪，郑霞忠．重大突发事件的动态协同应急决策[J].中国安全科学学报，2015，25(3):171-176.(Chen Shu，Yyu Di,ZhengXiazhong.Dynamic Collaborative Emergency Decision-Making ofMajor Incidents [J].China Safety Science Journal,2O15，25(3):171-176.)

[2]Botega L C,Ferreira L C,Oliveira N P,et al.SAW-Oriented User Interfaces for Emergency Dispatch Systems [C]//Lecture Notes in Computer Science,vol 9173,2015:537-548. [3]郑昊，高岩．多资源消耗应急系统调度模型及算法[J].上海理工大 学学报，2013,35(5):415-419.(Zheng Hao,Gao Yan．Scheduling model and algorithm for multi-resource consumption emergency system [J].Journal of University of Shanghai for Science and Technology,2013,   
35 (5):415-419.) [4] 徐选华，杨玉珊．基于累积前景理论的大群体风险型动态应急决策 方法[J].控制与决策,2017,32(11):1957-1965.(Xyu Xuanhua, Yang Yyushan. Large-group risk dynamic emergency decision-making method based on cumulative prospect theory [J]. Control and Decision,   
2017,32(11): 1957-1965.) [5] 张敏．SARS一类社会突发事件处置的博弈分析和管理对策[J].上 海理工大学学报：社会科学版,2005,27(1):63-66.(Zhang Min.Game Analysis and Management Countermeasures for the Disposal of Social Incidents in SARS[J].Journal of University of Shanghai for Science and Technology: Social Sciences,2005,27(1):63-66.) [6]王刚桥，刘奕，杨盼，等．面向突发事件的复杂系统应急决策方法研 究[J]．系统工程理论与实践，2015，35(10)：2449-2458.(Wang Gangqiao,Liu Wei,Yang Pan,et al.Research on emergency decision methodforcomplexsystemsforincidents[J].Systems Engineering-Theory& Practice,2015,35(10):2449-2458.) [7]姜艳萍，樊治平，苏明明．应急决策方案的动态调整方法研究[J]. 中国管理科学,2011,19(5):104-108.(Jiang Yanping,Fan Zhiping,Su Mingming. Research on dynamic adjustment method of emergency decision-making scheme [J].Chinese Journal of Management Science,   
2011,19 (5): 104-108. ) [8]Luscombe R,Kozan E.Dynamic resource allocation to improve emergency department eficiency in real time [J].European Journal of Operational Research,2016,255(2):593-603. [9]Peng M,Zhang L M.Dynamic decision making for dam-break emergency management,part 2:application to Tangjiashan landslide dam failure [J]. Natural Hazards & Earth System Sciences,2O13,13 (2):   
[10]刘长石，寇纲，刘导波．震后应急物资多方式供应的模糊动态 LRP [J]．管理科学学报,2016,19(10):61-72.(Liu Changshi,Kou Gang, Liu Daobo. Fuzzy dynamic LRP for multi-method supply of emergency materials after earthquake [J].Journal of Management Sciences in China,2016,19(10):61-72.)   
[11]Laksono P,Wulan SR,Supangkat SH,etal.AHP and dynamic shortest path algorithm to improve optimum ambulance dispatch in emergency medical response [C]/Proc of International Conference on ICT for Smart Society. 2017: 1-6.   
[12]田军，马文正，汪应洛，等．应急物资配送动态调度的粒子群算法 [J]．系统工程理论与实践，2011，31(5):898-906.(Tian Jun，Ma Wenzheng,Wang Yingluo,et al.Particle swarm optimization algorithm for dynamic dispatch of emergency materials distribution [J]. Systems Engineering-Theory & Practice,2011,31(5): 898-906.)   
[13]Liu X,Ju Y,Wang A.A dynamic vague multiple atribute decision-making method for emergency capability assessment [J]. Journal of Convergence Information Technology, 2011,6(11): 86-94.   
[14] Mould-Millman N K,Vries SD, Stein C,et al. Developing emergency medical dispatch systems in Africa-Recommendations of the African Federation for Emergency Medicine/International Academiesof Emergency Dispatch Working Group [J].African Journal of Emergency Medicine,2015,5(3):141-147.   
[15]Alberto M,DianaP,Tamara Z,et al. The role of the emergency medical dispatch centre (EMDC) and prehospital emergency care safety: results from an incident report (IR) system [J].Canadian Journal of Emergency Medicine,2015,17(4):411-419.