# 基于 $( \boldsymbol { n } , \boldsymbol { r } , \boldsymbol { k } )$ Fork-Join队列分析的NWR数据库写延时模型

王华进1,²，黎建辉1，沈志宏‘

(1．中国科学院计算机网络信息中心，北京 100190;2.中国科学院大学，北京 100049)

摘要：NWR数据库的写延时估计，可用于发现实现集群构建和运行成本最小化的节点数量、副本因子的配置组合。现有基于基准测试或模拟队列的方法受限于特定的测试配置和测试环境，只能给出写延时随配置变动的粗略结果。从分析NWR 数据库Cassandra的写操作的(n，r，k)Fork-Join队列结构入手，给出了该类队列期望逗留时间的解析解和NWR数据库写延时的理论模型，可用于建立更完备的写延时结论。分别在模拟队列和Cassandra集群上验证了(n,r,k)队列解析解和写延时模型的准确性。

关键词：数据库队列；副本因子；一致性；写延时 中图分类号：TP311 doi:10.3969/j.issn.1001-3695.2017.09.0878

# Write latency model for NWR databases based on $( n , r , k )$ Fork-Join queueing analysis

Wang Huajin1,²,Li Jianhui1†, Shen Zhihongl (1.Computer Network Information Center,ChineseAcademyofSciences,Beijing10o190,China;2.UniversityofChinese Academy of Sciences,Beijing 100049,China)

Abstract: The exactapproximation ofwrite latency forNWR databases under various consistencylevels canserve thebuilding andoperatingofdatabase clusters,byfinding theoptimalcombinationofclustersizeandreplication factor that minimizes the building and operating cost.Existing benchmarking orqueue simulating based approaches can only give incompleteresults as theyare limitedtospecificconfigurationsandtestbeds.Thispaperdepictedthefirstclose-formanalysisof(n,,K)fork-join queueing processof Cassndra (a typical NWR database） write operations,based on which this paper proposed the first theoretical write latency model forNWR databases.The model iscapableof giving morecomprehensive latency results. Experimentsvalidatedtheclose-formanalysisof(n,,k)fork-joinqueuesandthe writelatencymodelrespectivelyonsimulated queues and a Cassandra cluster.

Key Words: database queue; replication factor; consistency level; write latency

# 0 引言

NWR是一种流行的Key-Value 数据库一致性策略：1）每个Key-Value 对被存储在位于N个位于不同节点的副本中；2)完成读操作至少需要读取R个副本中最新的数据；3）完成写操作至少需要成功写入W 个副本；4）当 $R + W > N$ 时可以保证读到最新写入的数据。Amazon Dynamo[1]和ApacheCassandra[2]是两个流行的采用了NWR一致性策略的Key-Value数据库（以下简称NWR数据库）。

在NWR数据库中，写操作是通过Fork-Join队列分发到各个副本上并发执行的：a)客户端提交的写操作在控制节点被复制（Fork）为N份，分发到目标记录所在的N个副本节点上；b)每个副本节点写完成后，给出控制节点操作完成的答复；c)

控制节点接收（Join）到第W个答复后，给出客户端写请求已成功执行的响应。

显然在NWR数据库中，写操作的延时由集群节点数量L、副本因子N、一致性水平W共同决定。一般而言，L越大、N越大、W越小，延时越小。但L越大，集群的构建成本越大；N 越大，集群在存储和操作上的运行成本越大。鉴于NWR数据库集群往往针对特定目标场景负载的SLA（服务水平协议）构建，需满足SLA中对各种一致性水平下的写延时的要求。通行做法是，提供尽可能大规模的集群和较高设置的副本因子，以保证在极端负载压力下仍能满足写延时要求，但这往往导致系统资源和能源的浪费。准确估计各种一致性水平和负载压力下的NWR数据库的写延时，可用于发现满足延时要求的最小的L、N组合，从而为成本最小化集群的构建和配置提供重要

参考依据。

现有针对Cassandra等NWR数据库的操作延时分析方法主要有：a）基于基准测试的方法[3-6]，采用分布式数据库的主流基准测试工具得出实际集群在各种节点数量、副本因子、一致性水平、负载压力下的读写操作延时。但限于基准测试不能穷尽所有的配置组合，这些工作只是各自给出了延时随部分配置组合变动的粗略趋势，并不能证明其结论具有普遍适用性（完备性）;b）基于模拟队列的方法[7-l3]，构建与Cassandra 等数据库的读写操作执行过程等价的模拟队列网络（QueueNetwork)，通过运行模拟队列而非实际集群获取延时数据，以减轻测试的开销。由于模拟队列的结构和参数都只是对真实集群在特定配置和负载下的近似，其测试结果的可靠性要差于基准测试，并且所得出的结论同样是粗略、不完备的。

本文给出了NWR数据库的写延时理论模型。该模型的输入参数为最高一致性水平（ $\mathbf { W } = \mathbf { N }$ ）下的写操作在不同配置组合下的期望延时，输出为各种较弱一致性水平( $\mathbf { W } = 1 , 2 , . . . , \mathbf { N } - 1$ /下的写操作在相关配置组合下的期望延时的估计值。输入参数既可以通过理论计算获取，也可以借助基准测试获取。借助该模型进行同等规模的基准测试可以获取更为详细和完备的写延时结论。该理论模型的推导建立在对Cassandra写过程的排队结构 $( n , r , k )$ Fork-Join 队列的逗留时间的定量分析上。现有$( n , r , k )$ 队列逗留时间的研究仅给出了较为粗略的上下界[14]。本文通过证明 $( n , r , k )$ 队列的期望逗留时间为基本Fork-Join 队列$( i , i , i )$ 队列（ $1 \leq i \leq r$ )的期望逗留时间的线性组合，将较为困难的 $( n , r , k )$ 队列分析转换为较为容易的(i,i,i)队列分析。最后，通过解剖Cassandra 写过程的排队结构，将 $( n , r , k )$ 队列的定量分析应用于实际数据库写延时的估计上。

本文的主要贡献为:a)第一次给出了 $( n , r , k )$ Fork-Join 队列期望逗留时间的确切解析表达式，并在独立同指数服务时间分布的 $( n , r , k )$ Fork-Join 模拟队列上验证了该表达式的准确性；b）第一次给出了NWR数据库写延时的理论模型，并在实际Cassandra集群上验证了该理论模型的适用性。

# 1 非清除 (n,r,k) Fork-Join 队列分析

本文考虑一个由 $n$ 个节点构成的集群，其中每个节点 $i$ 0 $\cdot _ { 1 \leq i \leq n }$ )处理同类作业子任务时的服务时间 $X _ { i }$ 具有相同的概率分布（即节点同质)。每个节点上有一个先到先服务的子队列$q _ { i }$ ，假定子队列容纳能力无限。令：到达率 $\lambda$ 表示单位时间内提交到集群的作业数量，服务率 $\mu$ 表示单位时间内一个子队列可以完成服务的子任务数量，负载因子 $\rho \equiv \frac { \lambda } { \mu }$ 1

定义1非清除 $( n , r , k )$ Fork-Join队列。如图1所示，在一个由 $n$ 个子队列组成的非清除 $( n , r , k )$ Fork-Join 队列中：1)客户端提交的作业在到达控制节点时被复制（Fork）为 $\boldsymbol { r }$ 个相同开销的子任务，每个子任务被分配到 $\boldsymbol { r }$ 个不同节点上运行，每个节点被选中运行子任务的概率相同；2）节点执行完子任务后向控制节点发回答复；3）控制节点收到（Join）前 $k$ 个节点的答复后，对客户端发出作业完成的响应；4）剩余 $r - k$ 个节点上的子任务会继续执行（非清除），但其结果无须控制节点处理。

![](images/d6c4c4418bfbb5bef7f6b94911b727f1cf95559b5ebda18e535e30bf67715c42.jpg)  
图1一个非清除（5,3,2）Fork-Join 队列示例：红色子任务正在被服务

定义2期望逗留时间 $\mathbb { T } _ { n , r , k } ^ { \rho }$ 。非清除 $( n , r , k )$ Fork-Join 队列的期望逗留时间 $\mathbb { T } _ { n , r , k } ^ { \rho }$ 为：当该队列在负载因子 $\rho$ 下达到稳态时，一个新作业从在控制节点被Fork开始计时到在控制节点完成Join结束计时，所经历的时间间隔的期望值。

# 1.1一般服务时间队列的分析

引理设有2个服务时间分布相同的Fork-Join 队列，其中一个为处于负载因子 $\rho$ 下的非清除 $( n , r , k )$ 队列，另一个为处于负载因子 $\underline { r } \underline { \rho }$ 下的非清除 $( r , r , k )$ 队列。在忽略了渐进独立性$n$ （204[15]的情况下，上述两个队列的期望逗留时间相同，即：$\mathbb { T } _ { n , r , k } ^ { \rho } = \mathbb { T } _ { r , r , k } ^ { \frac { r \rho } { n } } \circ$

证明在上述 $( n , r , k )$ 队列和 $( r , r , k )$ 队列中，一个新到达的作业都会有 $\boldsymbol { r }$ 个子任务分配到 $\boldsymbol { r }$ 个不同子队列中，并等待前 $k$ 个子任务完成。由于每个节点被选中运行子任务的概率相同，$( n , r , k )$ 队列的每个子队列承受的子任务到达率与 $( r , r , k )$ 的子队列承受的子任务到达率均为 $\underline { { \underline { { r \lambda } } } }$ ，又由于所有子队列的服务$n$ （20时间分布相同，因此在两种队列达到稳态后，所有子队列的期望长度相同。设随机变量 $S _ { i }$ 表示一个子任务在子队列 $q _ { i }$ 中的逗留时间，次序统计量 $S _ { ( r , k ) }$ 表示 $S _ { 1 } , S _ { 2 } , . . . , S _ { r }$ 的第 $k$ 次序统计量。在忽略了渐进独立性[15]的情况下：T,=E[S(r.k)]，$\mathbb { T } _ { r , r , k } ^ { \frac { r \rho } { n } } = E [ S _ { ( r , k ) } ] ^ { \circ }$

定理1非清除 $( n , r , k )$ Fork-Join 队列的期望逗留时间为

$$
\mathbb { T } _ { n , r , k } ^ { \rho } = \sum _ { i = k } ^ { r } W _ { i } ^ { r , k } \mathbb { T } _ { i , i , i } ^ { \frac { r \rho } { n } }
$$

其中：常量系数 $W _ { i } ^ { r , k } = \sum _ { j = k } ^ { i } \binom { r } { j } A _ { i } ^ { r , j }$

$$
A _ { i } ^ { r , j } = \left\{ \sum _ { l = 1 } ^ { 1 } \binom { 1 } { l } A _ { i - l } ^ { r , j } \quad j + 1 \leq i \leq r . \right.
$$

证明 根据引理，T $\mathbb { T } _ { n , r , k } ^ { \rho } = \mathbb { T } _ { r , r , k } ^ { \frac { r \rho } { n } }$ "。根据文献[16]的定理5可知：$\mathbb { T } _ { r , r , k } ^ { \frac { r \rho } { n } } = \sum _ { i = k } ^ { r } W _ { i } ^ { r , k } \mathbb { T } _ { i , i , i } ^ { \frac { r \rho } { n } } \circ$

值得注意的是：定理1的成立无须假设子队列的服务时间相互独立。

定理2非清除 $( n , r , k )$ Fork-Join 队列的期望逗留时间$\mathbb { T } _ { n , r , k } ^ { \rho }$ 的上下界为： $\mathbb { T } _ { k , k , k } ^ { \frac { r \rho } { n } } \geq \mathbb { T } _ { n , r , k } ^ { \rho } \geq E [ X _ { ( r , k ) } ] + \frac { r \lambda E [ X _ { ( r , 1 ) } ^ { 2 } ] } { 2 ( n - r \lambda E [ X _ { ( r , 1 ) } ] ) } \ ;$ 或 $\mathbb { T } _ { k , k , k } ^ { \frac { r \rho } { n } } \geq \mathbb { T } _ { n , r , k } ^ { \rho } \geq E [ X _ { ( r , k ) } ] + \frac { r \lambda E [ X _ { ( r , k ) } ^ { 2 } ] } { 2 ( n - r \lambda E [ X _ { ( r , k ) } ] ) }$ 如果服务时间是独立同指数分布的。其中 $E [ X _ { ( r , k ) } ]$ 表示 $\boldsymbol { r }$ 个子队列的服务时间变量 $X _ { 1 } , X _ { 2 } , . . . , X _ { r }$ 的第 $k$ 次序统计量的期望。

证明 $\mathbb { T } _ { n , r , k } ^ { \rho } \equiv \mathbb { T } _ { r , r , k } ^ { \frac { r \rho } { n } } \equiv E [ S _ { ( n , k ) } ] \leq E [ S _ { ( k , k ) } ] \equiv \mathbb { T } _ { k , k , k } ^ { \frac { r \rho } { n } }$ 是显然的。（20根据文献[14]的定理4可推得到达率 $\frac { r \lambda } { - }$ 下的清除型 $( r , r , k )$ Fork-$n$ Join队列（即作业join完成后，剩余任务被从各子队列和运行态中立即清除）的期望逗留时间下界为$E [ X _ { ( r , k ) } ] + \frac { r \lambda E [ X _ { ( r , 1 ) } ^ { 2 } ] } { 2 ( n - r \lambda E [ X _ { ( r , 1 ) } ] ) }$ ，又根据文献[16的定理10，独立同指数服务时间分布的上述清除型队列存在一个更紧密的下界$E [ X _ { ( r , k ) } ] + \frac { r \lambda E [ X _ { ( r , k ) } ^ { 2 } ] } { 2 ( n - r \lambda E [ X _ { ( r , k ) } ] ) }$ ，显然此处的非清除 $( r , r , k )$ 队列的期望逗留时间的下界不小于上述下界。

根据定理1和定理2，非清除 $( n , r , k )$ 队列的期望逗留时间$\mathbb { T } _ { n , r , k } ^ { \rho }$ 的求解可以转换为较容易计算的 $( i , i , i )$ 队列的期望逗留时间 $\mathbb { T } _ { i , i , i } ^ { \rho }$ 和子队列服务时间的次序统计量 $X _ { ( r , k ) }$ 。

s0  
0 X ??s0-p:0.01 p:0.2 p:0.4 p:0.5 -p:0.6 -p:0.8 p:0.9 -x-\$ :0.950'1-  
0 Sp:06:::? \*火  
回留用 1 友1xF20 5X + 人 \4\ 杆杆↓ /1 计 中 ×\* x 4￥T ? ? LL!i!1 太丫 大 Y ?0 中 +  
（） 5 SIM p:0.01 --APP p:0.01 -+SIMp:0.2 -x-APPp:0.2 -·-SIMp:0.4 γ· APP p:0.4 -+-SIMp:0.5 x·APP p:0.5\*4  
回由田票 3 X+? X ? Y2 公 米￥ 茶 ?杀 ? ?I ? ? 茶 老老￥023 1,2,3, 1,2,3，4,5 1,2,3, 1,2,3,4,5 234567 1.,3) 1,2,3,4,5 1.23,4,5.67 234507893,3,3, 3,3,3， 5,5,5,5，5， 3,3,3， 5,5,5,5,5， 7,7,7,7,7,7,7， 3,3,3， 55555 Z77777， 999999999333 566 66666 777 77777 7777777 999 99 9999999 999999999

# 1.2指数服务时间队列的估计

鉴于独立同指数服务时间分布的(i,i,i)Fork-Join 队列的期望逗留时间 $\mathbb { T } _ { i , i , i } ^ { \rho }$ 存在较为准确的Nelson 估计方法[17]，本文在定理3中给出该类队列期望逗留时间的估计值。

定理3服务时间为独立同指数分布的非清除 $( n , r , k )$ Fork-Join队列的期望逗留时间：

$$
T _ { n , r , k } ^ { \rho } \simeq \operatorname* { m i n } \Bigl ( \operatorname* { m a x } \big ( N e l s o n T _ { n , r , k } ^ { \rho } , L o w T _ { n , r , k } ^ { \rho } \big ) , U p T _ { n , r , k } ^ { \rho } \Bigr )
$$

其中：

$$
\mathit { N e l s o n T } _ { n , r , k } ^ { \rho } \equiv \left\{ \begin{array} { c } { \frac { n r } { \mu ( n - r \rho ) } + \frac { 1 2 n - r \rho } { 8 8 \mu ( n - r \rho ) } \times } \\ { \frac { r } { i = 2 } W _ { i } ^ { r , 1 } \Bigg [ \frac { 1 1 \mu H _ { i } + 4 r \rho ( H _ { 2 } - H _ { i } ) } { n H _ { 2 } } \Bigg ] } \\ { \frac { 1 2 n - r \rho } { 8 8 \mu ( n - r \rho ) } \times } \\ { \sum _ { i = k } ^ { r } W _ { i } ^ { r , k } \Bigg [ \frac { 1 1 n H _ { i } + 4 r \rho ( H _ { 2 } - H _ { i } ) } { n H _ { 2 } } \Bigg ] } \end{array} \right. \ l ^ { k = 1 } ,
$$

$$
L o w T _ { n , r , k } ^ { \rho } = \frac { H _ { r } - H _ { r - k } } { \mu } + \frac { r \rho ( H _ { r ( r - r \rho / n ) } - H _ { ( r - k ) ( r - k - r \rho / n ) } ) } { n \mu }
$$

$$
U p T _ { n , r , k } ^ { \rho } = \left\{ \begin{array} { l l } { \displaystyle \frac { n } { \mu ( n - r \rho ) } } & { k = 1 , } \\ { \displaystyle \frac { 1 2 n - r \rho } { 8 \mu ( n - r \rho ) } \Biggl [ \frac { H _ { k } } { H _ { 2 } } + \frac { 4 r } { 1 1 n } \Biggl ( 1 - \frac { H _ { k } } { H _ { 2 } } \Biggr ) \rho \Biggr ] } & { k \geq 2 . } \end{array} \right.
$$

上述公式中， $H _ { _ { m } } = \sum _ { i = 1 } ^ { m } { \frac { 1 } { i } }$ 为调和级数， $H _ { m ( m - \rho ) } = \sum _ { i = 1 } ^ { m } { \frac { 1 } { i ( i - \rho ) } }$

证明将文献[17的式(6)代入定理1可以得出 $T _ { n , r , k } ^ { \rho }$ 的具体估计值 $N e l s o n T _ { n , r , k } ^ { \rho }$ ；将文献[17]的式(6)代入定理2 的下界可以得出 $T _ { n , r , k } ^ { \rho }$ 的下界 $L o w T _ { n , r , k } ^ { \rho }$ 。很容易得出 $\boldsymbol { r }$ 个独立同指数分布的服务时间变量的第 $k$ 次序统计量的期望 $E [ X _ { ( r , k ) } ] = { \frac { H _ { r } - H _ { r - k } } { \mu } }$ 该值代入定理2的上界得出UpTn,k。由于单独使用 NelsonTn,.k作为估计值可能带来较大的误差[1]，采用上下界UpTn,k$L o w T _ { n , r , k } ^ { \rho }$ 对估计值进行了限定。

如图2所示，采用模拟值（SIM）对从定理3中得出的估计值（APP）进行了验证。针对每一组 $( n , r , k )$ ，给模拟器Fokulator- $\cdot \mathsf { p } ^ { \mathrm { 1 } }$ 施加指定负载压力（ $\rho$ ）的作业到达流。当队列到达稳态后，以 $10 \%$ 的采样率获得100000个样本作业的延时均值为模拟值。误差率的计算公式为 APP $\frac { \mathrm { A P P } } { \mathrm { S I M } } - 1$ 。

从图2中可以看出，与模拟值对比，估计值的误差在大部分情况下较为可控。只有当负载特别重( $\rho > 0 . 8$ 且 $k < \frac { 2 } { \pi }$ 时误r差较为明显（大于 $2 5 \%$ )。这是由于：当 $\rho$ 较大时，通过Nelson估计方法得出的 $T _ { i , i , i } ^ { \frac { r \rho } { n } }$ 的误差较大；而 $k$ 较小时，更多的 $T _ { i , i , i } ^ { \frac { r \rho } { n } }$ 误差项被积累到了估计值里。未来本文可以通过改进指数队列 $\mathbb { T } _ { i , i , i } ^ { \rho }$ 的估计方法，降低该误差。

# 2 Cassandra写操作排队分析

Cassandra写操作的执行架构如图3所示。

![](images/6411b1d94a52383137d7772f03561d64616f3226ea90280fa0ed76bd9d372aa4.jpg)  
图3Cassandra 写操作的执行架构

a)客户端(CassandraDriver)向由 $n$ 个节点构成的Cassandra集群提交写操作请求，所连接的节点成为Coordinator；b）Coordinator将写命令发送到存储有目标记录副本的 $\boldsymbol { r }$ 个节点上（即副本因子为 $r$ )；c）当Coordinator从副本节点收到的回复数量达到一致性要求的下限 $k$ 时，就给出客户端写完成的响应。当Coordinator本身是副本节点时，称之为本地Coordinator，否则为远程Coordinator。默认配置下，一条Key-Value记录顺时针连续地存放在集群的 $\boldsymbol { r }$ 个节点上，其中第1个节点的位置是通过对Key进行散列确定的。这种存储划分方式可以基本保证各个节点存储同等数量的Key-Value记录。

Cassandra内 部 采 用了SEDA (Staged Event-DrivenArchitecture)[18]的设计框架，将写操作表达为一个由Native-Transport-Requests、Mutation、RequestResponse 等步骤组成的串行操作序列。每个步骤包含一个处理线程池，空闲线程从一个事件到达队列中取操作请求并执行，执行结果送入下一个步骤的到达队列。写操作的具体实现为：a）客户端的请求送到Coordinator 的Native-Transport-Requests 阶段的到达队列，该阶段首先获取目标副本所在的节点信息，然后通过MessagingService组件将写操作传输到每个副本节点的Incoming队列；b）副本节点上的Mutation 阶段从Incoming 队列中获取并执行写请求（追加Commitlog 和写入Memtable);c）副本节点通过MessagingService 组件将写操作的执行结果传输回Coordinator的Incoming队列；d）Coordinator的RequestResponse 阶段读取并计算Incoming队列中答复写操作的消息数量；e）若该数量达到一致性水平要求的下限，则向客户端发出最终响应。由于上述各阶段的队列长度上限为2-1因此当不对操作施加timeout限制时，所有阶段的到达队列都可近似为非损失制。

如上所述，Cassandra写操作的执行过程非常适合采用本文定义的非清除 $( n , r , k )$ Fork-Join 队列进行描述。本文将写操作的每个内部执行步骤视为队列服务过程的一部分，得出如图 4所示的简化Cassandra写操作排队模型。

![](images/f7f9e80682cf4aa903c31158d25506afa0cada744bd6d55a30b5facc2d02baa1.jpg)  
图4Cassandra写操作的简化Fork-Join排队模型：远程写(左）、本地写（右)

Cassandra客户端可以设置不同的负载均衡策略来控制Coordinator的选取：TokenAwarePolicy优先使用本地Coordinator，若所有本地Coordinator过载，则尝试使用远程Coordinator；RoundRobinPolicy等概率选取集群中的所有节点作为Coordinator；HostFilterPolicy可以指定具体节点做Coordinator。由于本地Coordinator下的写操作（本地写）的服务时间远小于远程Coordinator下的写操作（远程写）的服务时间，写延时模型必须反映本地写的比例。据此本文得出如下写延时模型。

定理4运行在一个同质集群上的 Cassandra 数据库的写操作期望延时模型为

$$
\mathbb { T } _ { n , r , k } ^ { \rho , l } = l \times L T _ { n , r , k } ^ { \rho } + ( 1 - l ) \times R T _ { n , r , k } ^ { \rho }
$$

其中：

$$
\begin{array} { r l } { R T _ { n , r , k } ^ { \rho } } & { = \displaystyle \sum _ { i = k } ^ { r } W _ { i } ^ { r , k } R T _ { i , i , i } ^ { \frac { r \rho } { n } } } \\ { L T _ { n , r , k } ^ { \rho } } & { = \left\{ \begin{array} { l l } { L T _ { 1 , 1 , 1 } ^ { \frac { r \rho } { n } } } & { k = 1 , } \\ { \displaystyle \sum _ { i = k - 1 } ^ { r - 1 } W _ { i } ^ { r - 1 , k - 1 } R T _ { i , i , i } ^ { \frac { r \rho } { n } } } & { k \geq 2 . } \end{array} \right. } \end{array}
$$

模型输入参数：a） $\mathbf { \xi } _ { l }$ 为本地写的比例；b) $L T _ { 1 , 1 , 1 } ^ { \frac { r \rho } { n } }$ 为本地写在负载压力为 $\underline { r } \underline { \rho }$ ，节点数、副本因子、一致性水平均为1时的$n$ 期望延时；c) $R T _ { i , i , i } ^ { \frac { r \rho } { n } } ,$ (k-1≤i≤r)为远程写在负载压力为，$n$ （204号节点数（不计入Coordinator节点）、副本因子、一致性水平均为 $i$ 时的期望延时。上述参数共计 $r – k { + } 4$ 个。

参数 $l$ 可以从负载均衡策略中推出，如RoundRobinPolicy对应的 $l = \stackrel { r } { - }$ 、轻量级负载下 TokenAwarePolicy 对应的 $l = 1$ ；参$n$ L和RT 既可以从本地写/远程写的服务时间的概率分布中估算得出（参见节1.2，及一般服务时间分布的 $( i , i , i )$ 队列的期望逗留时间的估计方法[19.20])，也可以用基准测试测得的延时样本均值估计。

# 3 实验

本文通过实验测得由6个同质节点组成的Cassandra集群在不同副本因子 $( \mathbf { \Phi } _ { r } ) _ { \mathbf { \Phi } }$ 一致性水平 $( \mathbf { \Phi } _ { k } \mathbf { \Lambda } )$ 、负载均衡策略 $( \mathbf { \Phi } _ { l } )$ ，负载压力（ $\boldsymbol { \rho }$ ）下的写延时，并与基于定理4的延时模型得出的估计值进行比较，以验证延时模型的适用性。其中：a）测出值通过Cassandra自带的查询追踪（Trace）功能得出，其精度为微秒级 $( 1 0 ^ { - 6 } s$ )。由于查询追踪本身的开销不可忽略，限定一个写操作被追踪的概率不大于 $6 \%$ 。测试中，每秒提交写操作的数量标记为 $\lambda$ ，写操作的提交间隔依照指数分布 $e x p ( \lambda )$ 选取:b）预测值通过将从集群测出的LIi 和 $R T _ { i , i , i } ^ { \frac { r \rho } { n } }$ 等参数值代入定理4得出。

为得出可比较和可重复的测出值，本文尽可能固定除副本因子、一致性水平、负载压力、负载均衡策略之外的变量（如写操作的数据量)，并采用6台位于同一机架的相同配置的物理机节点作为测试床。每个测试节点的配置为：双路IntelXeonE5-2603v3处理器、64GB内存、 $3 . 6 ~ \mathrm { T B }$ 机械磁盘、万兆以太网互连。测试用Cassandra版本为3.11.0。副本因子在1\~5变动，一致性水平从ONE( $\stackrel { \cdot } { k } = 1$ ）、QUORUM $\scriptstyle ( k = \left\lceil { \frac { n + 1 } { 2 } } \right\rceil )$ 、ALL（ $k = n$ )中选取，施加的目标负载压力标记为 $\lambda$ 。本文为各副本因子预先创建一个表空间（keyspace)，并各存入1亿条Key-Value记录。

为获取定理4给出的延时模型的输入参数并详细界定该延时模型的适用范围，本文设计了“微测试"和"扩展测试"两种实验方案。

800 米   
(sr) 600 400 200 + bench: 入=51200 Y Y approx:X=51200 0 + + bench: $\lambda = 1 0 2 4 0 0$ × × approx: $\lambda = 1 0 2 4 0 0$ （204号 L 福 123 333 22 333 444' 555 4 555 aouee 0.2 入=51200 Y Y 入=102400 0.1   
率 0.0 -0.1 -0.2 12 134 135 22 1 555 22 333 333 4 44 555 U a C U P P aitte 。 0 □ O O 。 O O 。 e e 巴 e e 800 米 (sr) 600 \*米 美美 \*\*\* \*￥ \*\* 米 兴票 400 美 × 士 200 米 米 米 \*\* bench:λ=18000 Y Y approx:X=18000 0 + + bench:λ=42000 × × approx:入=42000 111222 111222333 133344 111333555 2.2.2.2.2.2 333333333 女 555555555 666666 666666666 6666 66666 666666666 R 5 R 0.2 =18000 Y Y 42000 0.1 . Y   
率 Y   
差 0.0 Y   
误 -0.1 Y -0.2 111222 3 1333555 222222 333333332 555555555 666666 666 。 0 。 0 0 。 666 。 0 6 0 。 。 666 0 66666 R R

# 3.1 微测试

微测试在不同副本因子、一致性水平、负载压力、负载均衡策略下大量重复执行针对同一个Key-Value记录的写操作，以：1）获取延时模型的输入参数LIi 致 愛和機 $R T _ { i , i , i } ^ { \frac { r \rho } { n } }$ ：2）校验基于（204号 $( n , r , k )$ Fork-Join 队列的简单形式 $( r , r , k )$ 队列的延时模型估计Cassandra 数据库单一写操作延时的适用性。其中，负载均衡策略是基于HostFilterPolicy定制实现的全部本地写策略(local）和全部远程写策略（remote)。这两种策略对应的延时模型1参数值分别为1和0。

每种配置组合的测试结果抽样率为 $1 \%$ ，样本数为60000。  
实验结果如图5所示。延时模型的估计值（approx）较为接近  
测出值（bench)，基本验证了延时模型估计单一写操作延时的  
适用性，其中误差率的计算为approx $\frac { \mathrm { a p p r o x } } { \mathrm { ~ \iota ~ ~ ~ } } - 1$ bench

注意图中的 $\lambda$ 只是测试程序施加的压力目标，受限于Python 测试脚本自身的开销、基于sleep(函数间隔相邻操作的精度、Cassandra集群的实际处理能力，实际负载压力要低于目标压力。

# 3.2扩展测试

扩展测试在不同副本因子、一致性水平、负载压力、负载均衡策略下大量执行混合在一起的针对不同Key-Value 记录的$L T _ { 1 , 1 , 1 } ^ { \frac { r \rho } { n } }$ 和 和Rr:b)校验Cassandra写延时模型估计混合写操作延时的适用性。混合测试负载的构造确保了每个节点等概率地成为Coordinator，且承受同等压力的副本写入请求，以尽可能反映实际场景下负载在各节点上的均衡分配特性。其中，被测试的负载均衡策略包括全部本地写、全部远程写和RoundRobinPolicy，这3种策略对应的延时模型i参数值分别为1、0、rn。

每种配置组合的测试结果抽样率为 $6 \%$ ，全部本地写、全部远程写、RoundRobinPolicy的样本数分别为 $4 2 0 0 , 6 0 0 0 0 , 4 2 0 0 ,$ 实验结果如图6所示：延时模型的大部分估计值（approx）非常接近测出值（bench)，基本验证了延时模型估计混合写操作延时的适用性。注意图中的 $\lambda$ 同样为目标值，实际达成的负载压力水平低于该值。

值得注意的是，图6中的基准测试测出值和延时模型估计值均显示了：在相同副本因子、一致性水平、负载压力下，全部本地写、RoundRobinPolicy、全部远程写这3种负载均衡策略的写延时呈递增趋势。从该结果可以推断：TokenAwarePolicy均衡策略（该策略与全部本地写策略相近，l值均为1）要优于RoundRobinPolicy均衡策略。

# 4讨论

如引言所述，该理论模型的输入参数为最高一致性水平（ $\mathbf { W } = \mathbf { N }$ ）下的写操作在不同配置组合下的期望延时，输出为各种较弱一致性水平（ $\mathbf { W } = 1 , 2 , . . . , \mathbf { N } - 1$ ）下的写操作在相关配置组合下的期望延时的估计值。如节3所述，本文采用基准测试测出理论延时模型的输入参数。显然，在进行同等开销的基准测试时，理论延时模型可以得出比仅采用基准测试多N-1倍的延时结论。

节3初步验证了本文提出的NWR数据库理论延时模型的准确性，但通过基准测试获取模型参数的开销较大。更为理想的方案是，只需通过实验测出无压力下本地写和远程写操作的服务时间分布，然后借助该分布计算出上述参数在各种负载压力下的估计值。

![](images/8d2d640e3cebd635385b0333785100d62934da7c5493011326f8cd01e9e31d90.jpg)  
图7Cassandra集群的远程写服务时间分布（样本量50000）

目前独立同指数服务时间分布的 $( i , i , i )$ Fork-Join 队列的期望逗留时间存在较为准确的估算方法[17]。但本文实验测出的服务时间分布并不符合指数分布（见图7)。尽管对于一般服务时间分布的 $( i , i , i )$ 队列，存在一些基于插值[19]和回归[20]的估计方法，但其准确性依赖于所测出的服务时间分布的精度。受限于测量精度，本文测出的服务时间的分布并不十分稳定。这也是目前Fork-Join 队列的理论研究（如文献[14,21]）鲜有能被实际集群验证的原因，大部分工作只是给出了在模拟队列上的验证。未来，本文将进一步研究更为鲁棒的一般服务时间(i,i,i)队列的估计方法。

# 5 相关工作

# 5.1Fork-Join 队列分析

虽然 $( i , i , i )$ 队列是最基本的Fork-Join 队列，当 $i > 2$ 时其期望逗留时间仍然没有确切的解析解，只有一些估计方法存在。如：Nelson 等人[17]给出了指数服务时间分布的 $( i , i , i )$ 队列的期望逗留时间估计式；针对服务时间分布较为一般的(i,i,i)队列，Varma 等人[19]提出了基于插值的估计方法，Thomasian 等人[20]提出了基于测试结果回归分析的的估计方法，Rizk 等人[22]给出了基于鞅(martingales)的上界,Fidler等人[23]给出了多步骤Fork-Join队列网络的上下界。本文提出的延时模型的准确性依赖于上述估计方法的准确性。

对于清除型 $( r , r , k )$ 队列的期望逗留时间：仅当 $k = 1$ 时存在确切的解析解[24,25]； $k > 2$ 时仅存在较为粗略的上下界[14,21]。对于非清除 $( r , r , k )$ 队列的期望逗留时间：Fidler等人[23]给出了较为粗略的非渐进统计型上下界，Wang等人[16给出了基于线性变换的确切解析解，并用该解改进了清除型 $( r , r , k )$ 队列的期望逗留时间的上界。

针对 $n \not = r$ 的一般 $( n , r , k )$ 队列的期望逗留时间，Joshi 等人[14]给出了清除型队列的上下界。本文在Wang 等人[16]工作的基础上第一次给出了非清除 $( n , r , k )$ 队列的确切解析解。

# 5.2NWR数据库延时分析

目前针对Cassandra等NWR数据库的操作延时分析，主要分为基于基准测试的方法和基于模拟队列的方法。

通过基准测试分析NWR数据库性能的工作[3-6采用主流的分布式数据库基准测试工具YCSB[26]，分析包括节点数量、副本因子、一致性水平、负载压力等配置变量对读写操作延时的影响。限于基准测试不能穷尽所有的配置组合，这些工作只是各自给出了延时随配置变量变动的粗略趋势。此外，测试结果是基于特定负载下的特定集群得出的，并不能证明其结论具有普遍适用性（完备性)。与之相比，本文给出综合了各配置变量的通用写延时理论模型。基准测试只是用来获取模型的参数、验证模型适用性的辅助手段。

通过模拟队列分析NWR数据库性能的主要思路是：1）基于对目标数据库读写操作过程的详细分析建立与之等价的模拟队列网络（QueueNetwork)；2）通过基准测试确定模拟队列的服务时间、网络传输延时等各种参数；3）针对一些配置变量组合运行模拟队列，以获取目标配置下的延时。如：Huang等人[7]详细分析了Cassandra 写操作的执行过程和队列结构；Osman等人[8]详细分析了Cassandra的读操作的队列结构，并使用Queueing PetriNets 对其模拟。其他相关工作有[9-13]。相比基准测试，这类工作减轻了测试的运行开销，但由于模拟队列的结构很难完全反映真实集群的内部结构，其参数也很难概括真实集群在各类负载下的实际值，导致基于模拟队列的测试结果的可靠性要差于基准测试。此外其结论同样是粗略且不完备的。

# 6 结束语

由于NWR数据库的广泛应用，对该类数据库的性能分析，尤其是节点数量、副本因子、一致性水平、负载压力对读写操作延时的影响日显重要。现有基于基准测试或模拟队列的分析方法存在结论粗略、完备性欠缺等问题。本文：a）从分析NWR数据库写操作的排队模型——非清除 $( n , r , k )$ Fork-Join 队列入手，第一次给出了该类队列的期望逗留时间的解析解，并在独立同指数服务时间分布的模拟 $( n , r , k )$ 队列上验证了解析解的准确性；b）基于上述解析解，第一次给出了NWR数据库的理论延时模型。该模型可以反映不同节点数量、副本因子、一致性水平、负载压力、负载均衡策略对写延时的影响。模型的输入为最高一致性（ALL）下的期望延时的基准测试测出值或理论估计值，输出为其他一致性（ONE、QUORUM等）下的期望延时估计值。相较已有工作，基于该模型得出的结论更为详细和完备。本文在NWR数据库Cassandra的真实集群上验证了写延时模型的适用性。

未来的研究方向包括：a)借助非清除 $( n , r , k )$ 队列的期望逗留时间的解析解，改进清除型 $( n , r , k )$ 队列的期望逗留时间的上界；b）借助 Limited Processor Sharing(LPS)排队理论[27]，将CassandraSEDA每个阶段的线程池的大小纳入延时模型，从而使其可以反映不同线程数对写延时的影响；c）更为鲁棒的一般服务时间(i,i,i)队列的期望逗留时间估计方法，从而进一步减少延时模型的输入参数；d）更为综合的负载（不同读写比例、访问数据的分布、整体数据的分布）的延时模型；e）满足SLA延时要求且能够实现集群构建和运行成本最小化的节点数和副本因子的配置组合的计算方法。

# 参考文献：

[1]Decandia G,Hastorun D,Jampani M,et al. Dynamo [J].ACM SIGOPS Operating Systems Review,2007,41(6): 205-220.   
[2]Lakshman A,Malik P. Cassandra [J]. ACM SIGOPS Operating Systems Review,2010,44 (2): 35.   
[3]Dede E,Sendir B,Kuzlu P,etal.An evaluation ofcassandra for hadoop [C]/ Proc of IEEE International Conference on Cloud Computing. 2013: 494 501.   
[4]Wang H,Li J, Zhang H,et al. Benchmarking replication and consistency strategies in cloud serving databases: hbase and cassandra [C]// Proc of Workshop on Big Data Benchmarks,Performance Optimization，and Emerging Hardware.2014: 71-82.   
[5]Kuhlenkamp J, Klems M,Ross O.Benchmarking scalability and elasticity of distributed database systems [Cl//Proc of the VLDB Endowment. 2014: 1219-1230.   
[6]Huang X,Wang J,Yu P S,et al. An experimental study on tuning the consistency of nosql systems [J]. Concurrency and Computation: Practice and Experience,2017,29 (12): e4129.   
[7]Huang X,Wang J, Bai J,et al.Inherent replica inconsistency in cassandra [C]//Proc of IEEE International Congress on Big Data.2014: 740-747.   
[8] Osman R,Piazzolla P. Modelling replication in nosql datastores [C]/ Proc of/International Conference on Quantitative Evaluation of Systems.2014: 194-209.   
[9]Gandini A, Gribaudo M, Knotenbelt W J,et al. Performance evaluation of nosql databases [Cl// Proc of European Workshop on Performance Engineering.2014:16-29.   
[10]Pérez-Miguel C,Mendiburu A,Miguel-Alonso J.Modeling the availability of cassandra [J]. Journal of Parallel and Distributed Computing,2015,86: 29-44.   
[11] Niemann R.Evaluating the performance and energy consumption of distributed data management systems [C]// Proc of the 1Oth International Conference on Global Software Engineering Workshops.2015:27-34.   
[12] Dipietro S, Casale G,Serazzi G.A queueing network model for performance prediction of apache cassandra [C]/ Proc of the 1Oth EAI International Conference on Performance Evaluation Methodologies and Tools.New York: ACM Press,2017: 186-193.

[13] Huang X,Wang J,Qiao J,et al.Performance and replica consistency

simulation for quorum-based nosql system cassandra [C]//Proc of International Conference on Applications and Theory of Petri Nets and Concurrency.2017: 78-98.   
[14] Joshi G,Soljanin E, Wornell G.Eficient redundancy techniques for latency reduction in cloud systems [J].ACM Trans on Modeling and Performance Evaluation of Computing Systems,2017,2(2): 12: 1-12: 30.   
[15] Wang W,Harchol-Balter M, Jiang H,et al.Asymptotic response time analysis for multi-task parallel jobs [EB//OL]. (2017/10//27)[2017//11//12]. Arxiv: 1710.00296 [cs.PF].   
[16] Wang H,LiJ, Shen Z,et al.Approximations and bounds for (n,k) fork-join queues:a linear transformation approach [EB//OL]. (2017//09//08) [2017//09//12].Arxiv: 1707.08860 [cs.PF].   
[17]Nelson R,Tantawi AN.Approximate analysis of fork//join synchronization in parallel queues [J].IEEE Trans on Computers,1988,37(6): 739-743.   
[18] Welsh M,CullerD,Brewer E.Seda:an architecture for well-conditioned, scalable internet services [J].ACM SIGOPS Operating Systems Review. 2001,35 (5): 230-243.   
[19] Varma S,Makowski A M. Interpolation approximations for symmetric forkjoin queues [J].Performance Evaluation,1994,20 (1-3):245-265.   
[20] Thomasian A,Tantawi A N.Approximate solutions for $\mathbf { m } / \vert \mathbf { g } / / 1$ fork//join synchronization [C]//Proc ofWinter Simulation Conference.San Diego: Society for Computer,1994:361-368.   
[21] Joshi G,Liu Y,Soljanin E. Coding for fast content download $[ \mathrm { C } ] / \AA$ Proc of the 50th Annual Allerton Conference on Communication,Control,and Computing.2012:326-333.   
[22] Rizk A,Poloczek F, Ciucu F. Computable bounds in fork-join queueing systems [C]// Proc of ACM SIGMETRICS International Conference on Measurement and Modeling of Computer Systems.New York:ACM Press, 2015:335-346.   
[23] Fidler M, Jiang Y.Non-asymptotic delay bounds for(k,l) fork-join systems and multi-stage fork-join networks [C]// Proc of the 35th Annual IEEE International Conference on Computer Communications.2016.   
[24] Lee K,Pedarsani R,Ramchandran K.On scheduling redundant requests with cancellation overheads [J].IEEE//ACM Trans on Networking,2017, 25 (2): 1279-1290.   
[25] Gardner K,Zbarsky S,Doroudi S,etal.Reducing latency via redundant requests:exact analysis [C]//Proc of ACM SIGMETRICS International Conference on Measurement and Modeling of Computer Systems.New York:ACMPress,2015:347-360.   
[26] Cooper B F,Silberstein A,Tam E,et al.Benchmarking cloud serving systems with ycsb [C]// Proc of the 1st ACM Symposium on Cloud Computing.New York:ACM Press,2010:143-154.   
[27] Towsley D,Rommel C G,Stankovic JA.Analysis of fork-join program response times on multiprocessors [J].IEEE Trans on Parallel and Distributed Systems,1990,1(3): 286-303.