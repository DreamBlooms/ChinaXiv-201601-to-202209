# 基于时间窗的双小车岸桥与AGV协调调度研究

唐世科，严南南

(上海海事大学 物流科学与工程研究院，上海 201306)

摘要：针对自动化集装箱码头（automated containerterminals，ACT）的自动导引车（automatic guided vehicle，AGVs)与自动化双小车岸桥（double-trolleyquay cranes，QCs）协调调度优化问题，以上海洋山港四期工程的实际布局和装卸工艺为基础，考虑装卸同时进行条件下以最小化任务总完工时间为目标，建立带有时间窗约束的双小车岸桥和AGV的协调调度模型，并采用遗传算法对实际算例进行求解。通过灵敏度分析，验证了该模型及算法的有效性，并对遗传算法参数设置的有效性进行检验。结果分析表明，该调度方法有助于提高自动化集装箱码头的作业效率，减少集装箱船的在港时间，提高码头竞争力。

关键词：自动化集装箱码头；双小车岸桥；AGV；时间窗；遗传算法 中图分类号：TP272 doi:10.3969/j.issn.1001-3695.2017.12.0807

# Research on coordinated scheduling of double-trolley quay crane and AGV based on time window

Tang Shike, Yan Nannan (InstituteofLogistics Science& Engineering,Shanghai Maritime University,Shanghai 20l306,China)

Abstract: As for the problemofcoordinating optimization between the automatic guided vehicles (AGVs）and the doubletrolly quay cranes(QCs) inthe Automated ContainerTerminals (ACT),this paper was basedon theactual layout and loading and unloading technologyof Shanghai YangshanPortFourth project.Thetotal task completion time was taken as objective function consideringtheconditionofdualcycle.Adouble-trolleyquaycraneandAGV model with timewindowconstraints was establishedand used tocalculate the practical example by using the genetic algorithm.The sensitivity analysis verifies the validityof themodelandthealgorithm,andtests thevalidityofthegenetic algorithmparameterseting.Theresultsshowthat this methodcanhelpimprove theoperating eficiencyofAutomated Container Terminals,reducethecontaineratporttimeand improve the terminal competitiveness.

Key words: automated container terminals; double-trolley quay crane; AGV; time window; genetic algorithm

# 0 引言

随着国家一带一路战略的建设，港口扮演着越来越重要的作用。船舶大型化的趋势将使20000TEU以上的集装箱船在码头出现得越来越频繁。为了提高码头的装卸效率，世界各大港□纷纷研究并建设自动化码头，自动化码头能有效地提升码头的作业效率，安全、智能、绿色已经成为自动化码头的代名词。目前已建成的自动化码头国外有鹿特丹港、汉堡港等，国内有厦门远海码头、青岛港前湾码头，和上海洋山港四期。其中双小车岸桥、AGV、自动化轨道吊的装卸工艺能有效提升码头的装卸效率。吴沙坪等人[I针对洋山四期工程的特点，对洋山四期自动化集装箱码头装卸工艺设计作了深入的研究。

双小车岸桥[2]是一种新型的高效率集装箱装卸设备，通过改进装卸工艺能有效提高装卸效率。李锋等人[3]通过计算机软件对双小车岸桥作业仿真模拟，通过调整岸桥前小车和后小车的运行速度来优化作业。刘艳涛等人[4]以码头作业效率为优先原则，以失效安全为设计理念，建立了主小车摆动模型，提出了自动化双小车岸桥的动态防撞方法，保证双小车岸桥能安全作业并在此基础上提升作业效率。

在自动化集装箱码头AGV调度研究方面，国内外学者做了许多研究。Fazlollahtabar 等人[5]针对多个AGV同时调度的问题，考虑AGV的到达时间需在预定的时间周期内，过早到达会造成AGV等待时间增加，过晚到达会造成其他设备等待时间增加。Zaghdoud等人[将水平运输中的AGV问题分成路由、分配和调度三个子问题，运用Dijkstra 算法、遗传算法(GA)和启发式方法为每个集装箱选择AGV，并对这三种方法进行了比较研究。马越汇等人[7考虑自动化集装箱码头中的不确定因素（如集装箱码头堆场内的交通控制、交通拥堵等)，对AGV调度与配置问题，以最末任务结束时间最小化为目标建立模型，并设计算法求解。Luo等人[8研究了在自动化集装箱码头卸货过程中AGV调度和分配集装箱的仓储位置的的整合问题，并用遗传算法解决所提出的模型。康志敏[9对作业线和作业面两种 AGV基本调度方式进行了对比，提出了基于作业面的成本最小化的AGV调度方法，以等待时间最少为目标建立AGV调度模型求解。

国内外针对双小车岸桥与AGV协调调度的研究较少，目前主要的研究集中在普通岸桥与AGV的协调调度方面。Homayounis 等人[10]将岸桥和 AGV的协调调度问题定义为混合整数线性规划问题，并对该问题建模求解，使用Lingo软件与模拟退火算法进行求解并对比求解结果，结果表明在实际调度问题中模拟退火算法性能更优。柯冉绚等人[1针对AGV的调度优化问题，建立以无效最短时间为原则的数学模型，采用Netlogo 软件进行模拟仿真，并得出了六种情况下的最佳AGV和岸桥配置方式。Homayounis等人[12]研究了自动化集装箱码头岸桥、AGV和存储平台这三种设备的集成调度，并根据求解问题设计一种启发式算法对存储平台三个不同情况下的停留点进行了检验，并将已有算法与设计的启发式算法的求解结果进行比较，结果表明启发式算法在增加作业次数的情况下的求解结果比已有算法更优。

双小车岸桥最大的特点是主小车与门架小车进行接力作业其中接力点为双小车岸桥上的中转平台，中转平台可同时容纳两个40英尺或四个20英尺的集装箱，中转平台的缓存作用使得岸桥对任务的作业更加柔性，很好地解决了岸桥与AGV的耦合问题。双小车岸桥结构如图1所示。中转平台在双小车岸桥作业中起到缓冲的作用，研究缓存区对于双小车岸桥的中转平台的研究有参考价值。对缓存区的研究，Kim等人[13]将岸桥下方设置缓存区，并将缓存区容量限制问题转换为时间窗限制问题，给出了缓存区转换为时间窗限制的方法，减少设备的等待时间。汤鹏飞等人[14]在岸桥下方设置缓存区的情况下研究自动升降车(automated liftingvehicle,ALV)的调度问题，讨论了缓存区容量数量对设备作业的协调性和连贯性的影响。

![](images/a2d7d1dd20670d747c29dde1b8f6f0e4de74514ee0ad42b2736e8c61466a36ad.jpg)  
图1双小车岸桥示意图

# 1 问题描述

自动化集装箱码头作业时，双小车岸桥通过与AGV对接直接对船舶进行作业，自动化轨道吊负责堆场作业及与AGV对接，船舶和堆场之间的水平运输环节由AGV完成。一般出口集装箱放在堆场的海侧面，能使出口集装箱快速装船，进口集装箱放在堆场陆侧面，方便货主来取货。在集装箱卸船作业时，岸桥主小车抓取船上的集装箱并将其放置在岸桥的中转平台上，岸桥门架小车抓取中转平台上的集装箱放在岸桥下方等待的AGV上，然后AGV将此集装箱运输至堆场海侧的AGV伴侣处，AGV通过自身的自动升降装置将集装箱升起到AGV伴侣上，AGV便可去执行其他任务。集装箱装船作业时，海侧自动化轨道吊到集装箱所在的位置吊起集装箱运输到AGV伴侣上，再由AGV从AGV伴侣上装载集装箱运输至岸桥门架小车下方，岸桥门架小车抓取AGV上的集装箱放在中转平台上，再由岸桥主小车进行装船。双小车岸桥上的中转平台和堆场海侧的AGV伴侣很好地解决了AGV与岸桥和堆场之间的耦合问题，使岸桥和自动化轨道吊尽量地减少对AGV的影响，即让AGV小车尽量不要等待岸桥和自动化轨道吊。

本文采用作业面调度的方法：AGV不只服务于一个岸桥，如AGV完成岸桥1的任务后直接去完成岸桥2的任务，减少AGV的空载和等待时间。双小车岸桥的任务顺序和装卸类型都已定的情况下，中转平台上集装箱的数量在满足中转平台容量限制的条件下，岸桥主小车和门架小车都无法再抓取箱子放至中转平台上，通过合理的调度AGV可以减少设备间的等待时间，提高岸桥装卸速率，从而减少集装箱船在港时间。

# 2 数学模型

# 2.1问题假设

a)在堆场海侧处AGV都是对AGV伴侣进行操作，即从  
AGV伴侣上取箱或是将集装箱顶放到AGV伴侣上，此作业模  
式下AGV在水平运输作业中不发生拥堵；b)AGV每次只运输一个集装箱，运输均为40 英尺的集装  
箱；c)双小车岸桥的装卸作业顺序已知。

# 2.2集合参数

$o$ 、 $F$ ：分别表示虚拟开始岸桥和虚拟结束岸桥，其上的任务分别为虚拟开始任务和虚拟结束任务；$K ^ { o }$ ：表示增加虚拟岸桥O后的所有岸桥集合;$K ^ { F }$ ：表示增加虚拟岸桥F后的所有岸桥集合;$K$ ：岸桥的集合， $K = K ^ { o } \cup K ^ { F }$ ·$m _ { k }$ ：岸桥k的任务集合；$L$ ：所有装船集装箱任务集合；$U$ ：所有卸船集装箱任务集合；$\varrho$ ：所有集装箱任务的集合；V:：AGV集合;

$L ^ { k }$ ：岸桥k的装船集装箱任务集合；  
$\boldsymbol { U } ^ { k }$ ：岸桥k的卸船集装箱任务集合。

# 2.3符号参数及决策变量

i,j：集装箱任务；

k,l：岸桥编号；

$m$ ：岸桥数量；

$N _ { \boldsymbol { k } }$ ：双小车岸桥k的任务数量;

$p _ { i } ^ { k }$ ：岸桥 $\mathbf { k }$ 的主小车在中转平台放下(卸船)或拿起(装船)集装箱任务i的计划时刻;

$y _ { i } ^ { k }$ ：岸桥k 的主小车在中转平台放下(卸船)或拿起(装船)集装箱任务i的实际时刻；

$d _ { i } ^ { k }$ ：岸桥 $\mathbf { k }$ 的门架小车在中转平台拿起(卸船)或放下(装船)集装箱任务i的实际时刻;

$w _ { i } ^ { k }$ ：岸桥k的门架小车在 AGV 上放下(卸船)或拿起(装船)集装箱任务i的实际时刻；

$b _ { i } ^ { k }$ ：处理双小车岸桥 $\mathbf { k }$ 的集装箱任务i的AGV到达岸桥的门架小车下方的时刻;

$B _ { k i } ^ { l j }$ ：表示AGV完成集装箱任务i后去执行集装箱任务j的准备时间，即 $b _ { i } ^ { k }$ 结束到 $b _ { j } ^ { l }$ 发生AGV的准备时间；

$N$ ： $N = \sum _ { k } N _ { k } \ k \in K$ ,表示任务总数；  
$M$ ：一个很大的整数。

决策变量

$X _ { k i } ^ { l j } : 0 \mathrm { - } 1$ 变量, $X _ { k i } ^ { l j } { = } 1 , \mathrm { A G V }$ 完成岸桥 $\mathbf { k }$ 的集装箱任务i后去执行岸桥1的集装箱任务j; $X _ { k i } ^ { l j } { = } 0 , \mathrm { A G V }$ 作业为其他序列。

# 基本模型

$$
M i n T = m a x ( y _ { i } ^ { k } )
$$

$$
X _ { k i } ^ { o j } = 0 \ \forall k , o \in K ^ { o } , i \in m _ { k } , j \in m _ { o }
$$

$$
b _ { j } ^ { l } - ( d _ { i } ^ { k } + B _ { k i } ^ { l j } ) \geq M ( X _ { k i } ^ { l j } - 1 ) \forall k \in K , i \in m _ { k } ; \forall l \in K , j \in m _ { l } \ (
$$

$$
y _ { i } ^ { k } \geq d _ { i } ^ { k } \geq w _ { i } ^ { k } \geq b _ { i } ^ { k } \forall k \in K , i \in L ^ { k }
$$

$$
H _ { i } ^ { k } = [ y _ { u } ^ { k } , y _ { i } ^ { k } ] ~ u \leq i , u \in L ^ { k } \cup U ^ { k } , i \in L ^ { k } , k \in K
$$

$$
p _ { j } ^ { l } - p _ { i } ^ { k } \ge M ( X _ { k i } ^ { l j } - 1 ) ~ \forall k \in K , i \in m _ { k } ; \forall l \in K , j \in m _ { l }
$$

$$
\sum _ { l = 1 } ^ { m } \sum _ { j = 1 } ^ { m _ { l } } X _ { k i } ^ { l j } = 1 \forall k \in K , i \in m _ { k }
$$

$$
X _ { o i } ^ { F j } = 0 ~ \forall O \in K ^ { o } , \forall F \in K ^ { F } , i \in m _ { o } , j \in m _ { _ F }
$$

$$
X _ { k i } ^ { l j } = \left\{ 0 , 1 \right\} \forall k \in K , i \in m _ { k } ; \forall l \in K , j \in m _ { l }
$$

$$
X _ { { \scriptscriptstyle F i } } ^ { l j } = 0 ~ \forall F , l \in K ^ { F } , i \in m _ { _ { F } } , j \in m _ { _ l }
$$

$$
H _ { i } ^ { k } = [ y _ { i } ^ { k } , y _ { \nu } ^ { k } ] \ i \leq \nu , \nu \in L ^ { k } \cup U ^ { k } , i \in U ^ { k } , k \in K
$$

$$
y _ { i } ^ { k } \leq d _ { i } ^ { k } \leq w _ { i } ^ { k } \leq b _ { i } ^ { k } \forall k \in K , i \in U ^ { k }
$$

$$
\sum _ { k = 1 } ^ { m } \sum _ { i = 1 } ^ { m _ { k } } X _ { k i } ^ { l j } = 1 \ \forall k \in K , i \in m _ { k }
$$

$$
y _ { ( i + 1 ) } ^ { k } - y _ { i } ^ { k } \geq p _ { ( i + 1 ) } ^ { k } - p _ { i } ^ { k } \forall k \in K , i \in m _ { ( k - 1 ) }
$$

式(1)为目标函数，最小化岸桥主小车对最末任务的在中转平台上的实际操作时刻；岸桥 $o$ 是虚拟的初始任务，而岸桥 $F$ 表示虚拟的终止任务，如式(2)和(3)所示；式(4)表示虚拟开始任务的的下一个任务不能是虚拟终止任务；式(5)和(6)表示岸桥操作时任意一个任务只有一个紧前任务和只有一个后序任务；式(7)和(8)要求每个岸桥的装卸任务均被执行；式(9)表示岸桥主小车在中转平台放下(卸船)或拿起(装船)集装箱的实际时间要在计划时间之后；式(10)表示同一岸桥主小车在中转平台放下(卸船)或拿起(装船)两个任务的实际时间间隔要大于计划时间间隔；式(11)和(12)表示对于装船或卸船任务而言，AGV、门架小车、主小车对任务的操作时间需与实际操作情况相符；式(13)表示同一AGV处理相邻两个任务的时间要大于两任务之间的准备时间；式(14)表示岸桥主小车总是先去执行最早可执行时间在前的集装箱任务，减少集装箱在中转平台的等待时间；式(15)和(16)为中转平台容量约束转换为集装箱箱任务在中转平台上的时间窗约束， $\boldsymbol { H } _ { i } ^ { k }$ 表示岸 $\mathbf { k }$ 操作的集装箱任务 $i$ 在中转平台上的时间窗；式(17)表示变量为0,1变量。

$$
{ \sum } _ { k i j } X _ { k i } ^ { l j } = N _ { k } \forall k \in K , i \in m _ { k } ; \forall l \in K , j \in m _ { l }
$$

# 3 集装箱任务在中转平台上的时间窗求解

双小车岸桥的中转平台上的容量为2，本文只考虑40英尺的集装箱，中转平台可以同时容纳两个40英尺的集装箱。将双小车岸桥的中转平台容量约束转换为集装箱任务在在中转平台上的时间窗约束，对每一个集装箱任务，岸桥中转平台上的时间窗约束分为进口箱和出口箱的时间窗约束。对于进口箱，需要确定进口箱离开中转平台的最晚时刻，任务i的时间窗的上界由 $y _ { i }$ 向时间轴正向扩展；而对于出口箱，则需要确定出口箱进入中转平台的最早时刻，任务i的时间窗下界由yi向时间轴的负向扩展。集装箱任务时间窗从第一个任务开始计算，到最后一个任务结束。中控室可以根据集装箱的任务时间窗灵活调整门架小车和AGV的运行速度，保证整个水平运输系统的高效运转。

$$
{ \sum } _ { l i j } X _ { k i } ^ { l j } = N _ { l } \forall k \in K , i \in m _ { k } ; \forall l \in K , j \in m _ { l }
$$

$$
y _ { i } ^ { k } \ge p _ { i } ^ { k } \forall k \in K , i \in m _ { k }
$$

双小车岸桥中转平台容量为2，以计算10 个集装箱任务的时间窗为例。计算每个集装箱任务的在中转平台上的时间窗，其中 $y _ { i }$ 表示岸桥主小车实际放下或拿起集装箱的时间。任务1为出口箱任务， $[ 0 , y _ { 1 }$ 时间段内，中转平台内的集装箱任务数为0，则任务1的时间窗为 $[ 0 , y _ { 1 } ]$ 。任务2为进口箱任务，它的时间窗上界取决于后序的进口箱任务进入中转平台的时刻，接下来求解任务2后的进口箱任务的时间窗。任务2后序的出□任务为任务4且任务4之前的任务3为进口箱任务，所以在时段4内中转平台的容量已满，任务2的时间窗为[ $y _ { 2 } , y _ { 3 } ]$ 。任务3位进口箱任务，其后序的出口箱任务为任务4和任务7，则时段4和时段7都有一个集装箱任务，任务5和任务6均为进口箱任务，则时段6和时段7又分别占有一个集装箱任务，任务时间窗在时间轴上具有连续性且需要保证中装平台的利用率，所以任务3的时间窗上界只能拓展到 $y _ { 5 }$ ，任务3的时间窗为[ $y _ { 3 } , y _ { 5 } ]$ 。任务4的时间窗为 $[ 0 , y _ { 4 } ]$ 。任务5的后序出口箱任务为任务7，时段7的中转平台容量已满，任务5的上界只能扩展到 $y _ { 6 }$ ，所以任务5的时间窗为[ $y _ { 5 } , y _ { 6 } ]$ 。同理，可得其余任务的时间窗。任务时间窗求解过程如图2所示。

![](images/419e617fc0bccd3e75cb5bd2bcc43d9c59cb6ada14a51ba60385b94eabe12208.jpg)  
图2中转平台上的任务时间窗求解步骤示意图

# 4 遗传算法

# 4.1染色体编码

以某自动化集装箱码头为例，双小车岸桥数量为2，AGV数量为3，集装箱任务量为10。根据岸桥装卸任务顺序对集装箱任务进行优先级的编号，若存在任务计划时间相同的情况，则规定岸桥1的任务先于岸桥2的任务装卸。由岸桥装卸作业顺序确定各个任务的计划时间，将任务按照优先级顺序随机分配给可供作业的AGV，采用整数编码的方式，随机生成一条染色体，如图3所示。

![](images/49646edbb090d32bcbc8089322e766331c161cd675457be9c5088f875617c355.jpg)  
图3染色体编码示意图

图3中染色体编号的0表示AGV的出发点和结束点，根

据集装箱任务的优先级来确定AGV调度装载集装箱的顺序。  
图中的3辆AGV的作业顺序为：AGV1:1-5-6;AGV2:3-8-4-9;AGV3:7-2-10。

# 4.2适应度函数

本文直接采用以最末集装箱任务完成时间的目标函数值作为适应度值。优化的目标是选择适应度函数值尽可能小的染色体，即最末集装箱任务完成时间尽量小，适应度函数值越小的染色体越优质，反之越劣质。通过对比个体适应度函数值，简单明了的对个体优劣进行判断。

# 4.3选择操作

在选择操作中，个体被选中的概率与适应度值有关，个体适应度值越大，被选中的概率越大。为尽量保证遗传的多样性，使较优的个体能保留下来，本文遗传算法的选择概率设置为0.9，以轮盘赌选择方式对产生的种群进行选择。

# 4.4交叉操作

采用的是双切点交叉原则，P1、P2为父代染色体，C1、C2 为子代染色体。随机选择两个切点，交换两个切点之间的子串。若生成的中间代染色体编码合法，则得到子代染色体C1、C2；若生成的中间代染色体编码不合法，对于不合法的染色体进行修复，调整局部优先级，使得交叉后的染色体成为合法的染色体。

# 4.5变异操作

选择一个父代染色体 $P I$ ，随机地在染色体上选取两个位置，交换两个基因的序号，编码合法，则生成子代C1，完成染色体的变异操作，若生成的子代编码不合法，即出现乱序的情况，则调整局部优先级，使各路径中的优先级序号由小到大进行排列。

# 5 实例分析

# 5.1算例分析

为验证遗传算法对解决建立模型的有效性，采用MATLAB的语言开发环境设计遗传算法对模型进行求解。对于每个算例问题，均采用相同的参数设置，在MATLAB 里运行10 次，并取其结果的平均值，来判定所提出的算法的有效性。

以2台双小车岸桥，6辆AGV和30个集装箱任务为例，其中岸桥主小车的的装卸时间分别为 $1 2 0 \mathrm { s }$ ，110s，门架小车的装卸时间为80s，60s，考虑两个堆场箱区，堆场箱区既有进口集装箱任务，也有出口集装箱任务，不考虑集装箱船上的具体贝位。其中岸桥主小车的装卸作业顺序如表1所示。

利用MATLAB开发的遗传算法对以上问题进行求解，得到作业任务量为30，双小车岸桥数量为2，AGV数量为6时模型求解结果，求解所得收敛曲线图如图4所示。其中所求的最末任务完成时间最优解为3732s,AGV的调度方式为

AGV1: 2-6-8-15-18-26-27;

AGV2: 7-17-19-21-29;  
AGV3:1-4-5-12-16-23-24-28;  
AGV4: 3-10-14-22-25-30;  
AGV5:13;  
AGV6:9-11-20。

即AGV1的作业任务顺序为任务2，任务6，任务8，任务15，任务18，任务26，任务27。其余AGV的作业任务顺序如上所示。

表1岸桥主小车装卸计划时间  

<html><body><table><tr><td>任务ID 任务属性</td><td>装/卸时间</td><td>(s）</td><td>计划开始时刻(s)</td><td>任务所属岸桥</td></tr><tr><td>1 L</td><td></td><td>120</td><td>0</td><td>1#</td></tr><tr><td>2</td><td>U</td><td>110</td><td>230</td><td>1#</td></tr><tr><td>3</td><td>L</td><td>120</td><td>0</td><td>2#</td></tr><tr><td>4</td><td>L</td><td>120</td><td>230</td><td>1#</td></tr><tr><td>5</td><td>U</td><td>110</td><td>230</td><td>2#</td></tr><tr><td>6</td><td>L</td><td>120</td><td>230</td><td>2#</td></tr><tr><td>7</td><td>U</td><td>110</td><td>460</td><td>1#</td></tr><tr><td>8</td><td>U</td><td>110</td><td>460</td><td>2#</td></tr><tr><td>9</td><td>L</td><td>120</td><td>460</td><td>2#</td></tr><tr><td>10</td><td>U</td><td>110</td><td>690</td><td>1#</td></tr><tr><td>11</td><td>U</td><td>110</td><td>920</td><td>1#</td></tr><tr><td>12</td><td>U</td><td>110</td><td>1150</td><td>1#</td></tr><tr><td>13</td><td>U</td><td>110</td><td>690</td><td>2#</td></tr><tr><td>14</td><td>L</td><td>120</td><td>1150</td><td>1#</td></tr><tr><td>15</td><td>L</td><td>120</td><td>690</td><td>2#</td></tr><tr><td>16</td><td>U</td><td>110</td><td>920</td><td>2#</td></tr><tr><td>17</td><td>L</td><td>120</td><td>920</td><td>2#</td></tr><tr><td>18</td><td>U</td><td>110</td><td>1380</td><td>1#</td></tr><tr><td>19</td><td>U</td><td>110</td><td>1150</td><td>2#</td></tr><tr><td>20</td><td>U</td><td>110</td><td>1380</td><td>2#</td></tr><tr><td>21</td><td>L</td><td>120</td><td>1380</td><td>1#</td></tr><tr><td>22</td><td>L</td><td>120</td><td>1610</td><td>1#</td></tr><tr><td>23</td><td>L</td><td>120</td><td>1380</td><td>2#</td></tr><tr><td>24</td><td>U</td><td>110</td><td>1840</td><td>1#</td></tr><tr><td>25</td><td>L</td><td>120</td><td>1840</td><td>1#</td></tr><tr><td>26</td><td>L</td><td>120</td><td>1610</td><td>2#</td></tr><tr><td>27</td><td>U</td><td>110</td><td>1840</td><td>2#</td></tr><tr><td>28</td><td>L</td><td>120</td><td>1840</td><td>2#</td></tr><tr><td>29</td><td>U</td><td>110</td><td>2070</td><td>1#</td></tr><tr><td>30</td><td>L</td><td>120</td><td>2070</td><td>1#</td></tr></table></body></html>

![](images/e424e14b298040a482bc54e0a29a7d2541e8ffedbb8d3798a238df10a2ad0b9b.jpg)  
图4任务量为30、岸桥为2、AGV为6时的收敛曲线

# 5.2不同规模问题求解分析

为分析不同规模的问题，将变量参数设置如下：

a）任务量的设置变化范围为20\~200，其中有出口任务也有进口任务；AGV的变化范围为4\~8；双小车岸桥的设置变化范围为2\~3；堆场箱区为2，每个箱区既有出口集装箱又有进口集装箱。

b)遗传算法的参数设置：选择概率为0.9，交叉概率 $\mathrm { P c } { = } 0 . 6$ 变异概率 $\mathrm { P m } { = } 0 . 1$ ，种群大小size Pop $\scriptstyle 1 = 1 0 0$ ，最大迭代次数maxGen $\scriptstyle 1 = 3 0 0$ 。

对集装箱任务量、双小车岸桥与AGV之间的各种规模问题求解结果如表2所示。从表中所得到的结果显示，随着集装箱任务量的增大，算法的求解时间也在不断增大，且最末任务完成时间也增加的越来越快。随着岸桥和AGV数量的增加，最末完成任务时间在减小。从问题8、9和10可以发现，盲目的增加AGV数量,不仅作业效率不会提升，反而会使AGV在作业时产生冲突，造成拥堵。从问题12和13可以看出，岸桥数量的增加对最优解的影响很大，但是岸桥是码头的稀缺资源而且成本非常高，如果对于这个中等规模的问题增加岸桥，会导致岸桥之间距离过近，从而导致岸桥之间的作业冲突。岸桥与AGV的数量配比很重要，采取合理的数量配比能有效地减少 AGV在水平运输环节的冲突，达到能减少岸桥间的冲突和AGV之间在运输集装箱时的冲突的目的，使岸桥与AGV之间能较好的地协调运作，减少资源的浪费。结果也表明遗传算法在解决不同规模的问题时可靠性较高，可以为现实生活中自动化码头处理集装箱任务时提供设备数量关系参考。

表2不同规模问题求解结果  

<html><body><table><tr><td>问题编号</td><td>集装箱任务量</td><td>岸桥/AGV/箱区数</td><td>计算时间/s</td><td>OFV/s</td></tr><tr><td>1</td><td>20</td><td>2/4/2</td><td>4.32</td><td>2512</td></tr><tr><td>2</td><td>30</td><td>2/4/2</td><td>5.58</td><td>4132</td></tr><tr><td>3</td><td>30</td><td>2/5/2</td><td>5.42</td><td>3986</td></tr><tr><td>4</td><td>40</td><td>2/4/2</td><td>7.79</td><td>5863</td></tr><tr><td>5</td><td>40</td><td>2/5/2</td><td>7.68</td><td>5214</td></tr><tr><td>6</td><td>50</td><td>2/5/2</td><td>12.76</td><td>7065</td></tr><tr><td>7</td><td>50</td><td>2/6/2</td><td>14.88</td><td>6852</td></tr><tr><td>8</td><td>60</td><td>2/5/2</td><td>42.35</td><td>9162</td></tr><tr><td>9</td><td>60</td><td>2/6/2</td><td>43.78</td><td>8836</td></tr><tr><td>10</td><td>60</td><td>2/7/2</td><td>51.64</td><td>9134</td></tr><tr><td>11</td><td>80</td><td>2/5/2</td><td>78.56</td><td>13825</td></tr><tr><td>12</td><td>80</td><td>2/6/2</td><td>82.49</td><td>12356</td></tr><tr><td>13</td><td>100</td><td>2/6/2</td><td>111.26</td><td>13358</td></tr><tr><td>14</td><td>100</td><td>3/6/2</td><td>120.25</td><td>11285</td></tr><tr><td>15</td><td>120</td><td>3/5/2</td><td>165.40</td><td>13685</td></tr><tr><td>16</td><td>120</td><td>3/6/2</td><td>182.24</td><td>12152</td></tr><tr><td>17</td><td>150</td><td>3/6/2</td><td>244.28</td><td>15866</td></tr><tr><td>18</td><td>150</td><td>3/7/2</td><td>272.26</td><td>14896</td></tr><tr><td>19</td><td>180</td><td>3/7/2</td><td>325.60</td><td>18258</td></tr><tr><td>20</td><td>180</td><td>3/8/2</td><td>348.35</td><td>17125</td></tr><tr><td>21</td><td>200</td><td>3/8/2</td><td>398.37</td><td>19582</td></tr></table></body></html>

# 5.3遗传算法参数灵敏度分析

遗传算法在搜寻最优解时，不同的参数组合设置对不同的求解规模问题有着不同的影响。为了快速有效地找到所求解问题的最优解，使收敛曲线快速收敛，特别是当问题规模变大的时候，快速有效地求解问题非常重要。为了找到有效的算法参数设置组合，在这里考虑双小车岸桥数量为2、AGV数量为6、集装箱任务数量为30时的算例，其中有进口集装箱任务，也有出口箱任务。遗传算法主要参数变化范围如下：

交叉概率 $P c { = } ( 0 . 6 , 0 . 7 , 0 . 8 , 0 . 9 )$ 变异概率 $P m \mathrm { = } ( 0 . 0 6 , 0 . 0 8 , 0 . 1 0 , 0 . 1 2 )$ 种群规模 size Pop=(50,100,150,200);最大迭代次数 $m a x G e n { = } 3 0 0$ 。

图5\~7分别是算法不同参数设置之间的对求解结果的比较图5的算法参数设置为 $P m { = } 0 . 1 0 , M a x G e n { = } 1 0 0 ,$ 。从图5可以看出，四支曲线在100代以后都得到了收敛的最优解，其中交叉概率为0.7和0.8的求解收敛曲线达到了同一最小最优解，而且交叉概率为0.8的曲线收敛更早。图6的算法参数设置为$P c { = } 0 . 8 , M a x G e n { = } 1 0 0 _ { \circ }$ 从图6可以看出，由于变异概率的改变,变异概率较大的收敛曲线收敛较晚，变异概率较小的收敛曲线收敛较早，其中变异概率为0.06和变异概率为0.08的收敛曲线在170代以后收敛到同一最优解，而且变异概率为0.08的收敛曲线在50代以后就收敛到最优解。图7的算法参数设置为$P c { = } 0 . 8 , P m { = } 0 . 0 8$ 。从图7可以看出，四条收敛曲线的收敛趋势表明随着种群规模的扩大，得到的解也在趋向得到更小的最优解，当种群规模为200时，得到的求解结果最优且收敛最早。以上研究结果表明对算法参数的初始设置对遗传算法求解问题的效率和有效性是非常重要的。由以上分析所得到的参数设置(sizePop $scriptstyle - 2 0 0$ ， $P m { = } 0 . 0 8 , P c { = } 0 . 8 \$ 再次对双小车岸桥数量为2、AGV数量为6、集装箱任务数量为30的问题进行求解，求解结果如图8所示。求解的的最优解在80代以后就收敛到最优解，并且由于种群规模的扩大，解搜索空间的扩大，求出的最优解更小。

![](images/cc2f4a16be8917a85fca446cba533a6e30a6b3db733a5213e55a24da03b74020.jpg)  
图5sizePop $\scriptstyle 1 = 1 0 0$ ， $\mathrm { P m } { = } 0 . 1 0$ 时不同交叉概率的收敛曲线

![](images/beb24a01f3f8bba9dfdffeb8f4330304960d9c2deefb9705c4805e7887aa623e.jpg)  
图6sizePop $_ { \mathrm { 1 0 0 } }$ ， $\mathrm { P c } { = } 0 . 8$ 时不同变异概率的收敛曲线

![](images/e4dd1d7483875dea79f6f1cc3100732002c21bb64b8bb2f246c8f6273e5c608b.jpg)  
图7 $\mathrm { P c } { = } 0 . 8 , \mathrm { P m } { = } 0 . 0 8$ 时不同种群规模的收敛曲线

![](images/3df34923e762bec68bf148184810b6875691f0db7ad82b8303389bb4ff2d7612.jpg)  
图8优化后任务量为30、岸桥为2、AGV为6时的收敛曲线

# 6 结束语

本文考虑了双小车岸桥中转平台对双小车岸桥和 AGV协调调度的影响，为集装箱任务在中转平台上设置时间窗，建立了基于时间窗的AGV调度模型，求出了最末任务完成时间的最优解。对不同规模问题进行求解分析，合理的设备数量关系可以提升作业效率和减少设备之间的作业冲突。对遗传算法参数进行灵敏度分析，对遗传算法参数设置的有效性进行检验，验证了遗传算法参数设置的重要性，对大规模问题的求解，提高算法运算的效率。

文中构建的双小车岸桥和AGV协调调度模型及其实例求解分析可为当前自动化集装箱码头作业设备数量关系和AGV调度提供参考。后续的工作将以双小车岸桥、AGV和堆场自动化轨道吊三种设备间的协调调度为方向继续研究。

# 参考文献：

[1]吴沙坪，何继红，罗勋杰．洋山四期自动化集装箱码头装卸工艺设计 [J]．水运工程,2016 (9): $1 5 9 - 1 6 2 + 1 6 6$   
[2] 周崎，张氢，张勇，等．双小车岸边集装箱起重机自动装卸集装箱的关 键技术[J].起重运输机械,2016(3):70-74.   
[3]李锋，何钢，汤婷．双小车岸边集装箱起重机优化选型仿真分析[J]. 起重运输机械,2015 (3): $5 8 - 5 9 + 6 9$   
[4]刘艳涛，胡昱晖，单磊．一种双小车岸边集装箱起重机的小车防撞设计 方法[J].港口装卸,2017(3):26-28.   
[5]FazlollahtabarH,Saidi-Mehrabad M,Balakrishnan J,Mathematical optimization for earliness/tardiness minimization in a multiple automated guided vehicle manufacturing system via integrated heuristic algorithms [J]. Robotics and Autonomous Systems,2015,72:131-138.   
[6]Zaghdoud R,Mesghouni K,Dutilleul S C,et al.A hybrid method for assigning containers to AGVs in container terminal [J]. Original research articleI FAC-PapersOnLine,2016,49(3): 96-103.   
[7]马越汇，胡志华．不确定环境下自动化集装箱码头 AGV 调度与配置问 题[J].广西大学学报：自然科学版,2016,41(2):589-597.   
[8]Luo Jiabin, Wu Yue, Bergsten A. MendesModeling of integrated vehicle scheduling and container storage problems in unloading process at an automated container terminal Original research article [J].Computers & Industrial Engineering,2016,94(4): 32-44.   
[9]康志敏.集装箱自动化码头 AGV 路径优化和调度研究[D].武汉：武 汉理工大学,2011.   
[10] Homayounis M,Tangs H, Napsiah I. Using simulated annealing algorithm for optimization of quay crane sand automated guided vehicles scheduling [J]. Intern ational Journal of the Physical Sciences,2011,6(27): 6286-6294.   
[11]柯冉绚，任亚东．集装箱码头AGV调度优化[J].集美大学学报：自然 科学版,2016,21(1): 35-41.   
[12] Homayounis M,Tangs H,Motlagh O.A genetic algorithm for optimization of integrated scheduling of cranes，vehicles，and storage platformsat automated container terminals [J]. Journal of Computation a land Applied Mathematics,2014,270(1): 545-556.   
[13] Kim KH,Nguyen VD.A dispatching method forautomated lifting vehicles inautomated port container terminals [J].Computers & Industrial Engineering,2009,56:1002-1020.   
[14]汤鹏飞，梁承姬，丁一.考虑岸桥缓存区的 ALV 调度优化问题研究 [J]．广西大学学报：自然科学版,2015,40(6):1540-1550.