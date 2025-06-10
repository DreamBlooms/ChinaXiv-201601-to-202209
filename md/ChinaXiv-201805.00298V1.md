# 基于Spark的两表等值连接过程优化

张子栋1，郑延斌²

(1.集美大学 计算机工程学院，福建 厦门 361021;2.河南师范大学 计算机与信息工程学院，河南 新乡 453007)

摘要：在数据统计分析查询中表间的等值连接是常用的操作之一，但代价较高。大数据环境下大表之间等值连接的效率更低。为了解决该问题，提出了一种基于 Spark的两表等值连接过程优化方法。首先根据数据价值密度特征构建Bloom Filter完成表的过滤操作；其次结合 Simi-Join和Partition Join两者的优势，对过滤后的单侧表使用贪心算法进行拆分；最后对拆分后的子集进行连接，因此把两大表的连接过程转换为分阶段进行的两小表连接。代价分析和实验结果表明该算法与现有基于 Spark 的连接操作相比不仅在性能上得到了提升而且当出现数据倾斜时对算法效率影响较小。

关键词：Spark；等值链接；大数据；优化；拆分 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.08.0710

# Optimization of two-table equivalent connection process based on Spark

Zhang Zidong1, Zhang Yanbin² (1.CollegeofomputerEnginering,Jmei Unversity,XiamenFujian36,China;2.Collgeofomputer&Iotio Technology Henan Normal University,Xinxiang Henan 453007,China)

Abstract: Theequivalenceconection betweentablesinthe statisticalanalysis ofdata isoneofthecommonlyusedoperations, butthe price isrelativelyhigh.Inbigdataenvironment,theconnectionoflargescaledatatablesislessefficient.Inorderto solvethis problem,this paper proposedamethod foroptimizationoftwo-table equivalentconnection processbasedon Spark: first,constructedthe BloomFiltertocompletethefilteringoperationaccording tothelowdensityofdata density;secondly combinedtheadvantagesofSimi-JoinmethodandPartitionJoin methods,thehegreedyalgorithmSpliting methodsisused for thefilteredunilateraltable;lastlyjoinedthesplit subsets.Thentheconnectionprocessoftwobig tables waschanged into two stages of the two smalltableconnection,Cost analysisand experiments show that the proposed algorithm has improved performance compared with the existing Spark-based connection operation performance and data tilt.

Key Words:Spark; equivalent connection; large data analysis;optimize; split

# 0 引言

在大数据背景下，涌现出了Hadoop、Spark 等计算框架。作为一种分布式内存并行计算框架，Spark[1]以弹性分布式数据集（resilientdistributeddatasets,RDD）[2]为数据结构，并支持迭代计算，在大数据处理中表现出较好的性能。Spark环境中经常会执行数据统计分析、查询等任务，其中等值连接是常用的但是代价较高的操作之一。尤其是大数据环境下数据表规模巨大，大表之间的等值关联操作效率更加低下。

Spark 中对表等值连接的操作是RDD的执行操作[2]，主要采用 Spark SQL[3]组件中的 Broadcast Join、Shuffle Hash Join、SortMergeJoin等方式。BroadcastJoin方式是将其中一张数据表通过广播变量的方式广播到Spark所有集群节点上，然后再执行Join操作。BroadcastJoin方式由于每个Executor 都会接受到表的全部数据，占用一部分内存空间来储存接受的数据，以存储为代价避免了shuffle 操作。但是该方式局限性明显，只适合大表对小表或者小表间的Join。其他的连接方式如ShuffleHashJoin和SortMergeJoin等，都会对连接属性Key 进行重划分[4]，会涉及Shuffle。如果数据量大时，Shuffle会带来大量的网络通信和磁盘I/O，并且数据分布难以预知。当数据节点上数据倾斜问题出现时，会造成局部节点作业时间长、计算量较大，因而导致整体作业时间长、局部节点出现OOM和计算资源浪费等问题。由大数据的数据特征知道，数据价值密度低，进行连接操作的两表通常存在大量不需要join的数据元组。

Spark/MapReduce 编程中常用的连接算法有广播连接(mapside join)和重划分连接(reduce side join)两种，但是它们都有局限性。Xu 等[5基于MapReduce 模型提出了SemiJoin，其基本思路是选取一个小表R，将其参与join的key抽取出来，保存到文件F中（F文件很小可以放到内存中)。在map 阶段，使用DistributedCache将F复制到各个TaskTracker上，然后将另一个表Q中不在F中的key对应的记录过滤掉，剩下的reduce阶段的工作与reduce side join 相同；Ramesh 等[提出了一种基于BloomFilter 的等值连接算法，该算法采用BloomFilter 对待连接的数据集进行过滤操作，减少 Shuffle 阶段的数据量。然而其中的等值连接方法是基于MapReduce 计算框架，将处理的中间结果存储在磁盘中，与Spark的机制不同，因此整体处理的效率较慢，而且其没有考虑数据倾斜；Zhou等人7指出数据倾斜是因为Hadoop 本身无法感知mapper端输出数据的分布情况，导致reducer 的负载不均衡，影响连接执行的效率；Gufler等人[8.9]提出了两种根据采样结果来确定划分函数的方法，从而保证reducer负载均衡。如果能够对mapper任务输出的中间结果进行统计分析，确定数据分布情况，从而设计适应的分区函数和数据分发机制，就能确保每个reducer的负载均衡；卞昊穹等人[10提出了一种基于Spark的等值连接的优化方法，其优化思想是：首先获取Fact表连接属性的无重集合FactUK，并记录对应记录的位置：其次用FactUK与Dim表进行连接，生成JoinedUK。最后根据JoinedUK中记录的位置将JoinedUK与Fact表进行组装，得到最终结果。但是该方法只适用于大表与小表之间等值连接的情况，且默认数据表均可以缓存到内存中，然而在实际应用中，大部分数据表是很难完全缓存到内存中。

为了解决以上连接过程中的问题，本文提出了一种基于Spark的两表等值操作优化算法。该算法首先对数据表构建标准BloomFilter[1]进行过滤；其次结合Simi-Join和PartitionJoin两者优势，通过对一侧表连接属性Key的分区信息和另一侧表Key 数据倾斜[12]情况的分析结果，做为贪心策略的启发选择；最后对过滤后的单侧表使用贪心算法[13进行拆分，并对拆分后的子集进行连接。从而把两大表的连接过程转换为分阶段进行的两小表连接，并得到连接结果。代价分析和实验表明了本文的算法比基于Spark的连接操作在性能上得到了提升，当出现数据倾斜时对算法的影响较小。

# 1基于Spark的两表等值连接优化方法

在对两大表等值连接过程中，首先要对两表中存在的大量不符合连接条件的元组进行过滤优化，降低整体数据量。针对Spark中BroadcastJoin、ShuffleHashJoin、Simi-Join 等的局限性，提出了一种在 Spark上做等值连接的优化方法，分为两个阶段如图1、2所示，图中的符号如表1所示。

# 1.1过滤连接表

因为BloomFilter具有占用时空间小，运算快速快等优点，该阶段采用标准的BloomFilter进行数据过滤。

抽取两个数据表（RDD_a、RDD_b）的连接属性 join Key，得到Joinkey_a和Joinkey_b 两个新的RDD，然后使用Spark自带的distinct操作对这两个RDD进行去重，得到两个无重的数据集Joinkey_a和Joinkey_b。使用Spark类库的BloomFilter分别对无重集JoinKey_a和JoinKey_b的进行压缩处理，并计算得到两个位数组 $\mathrm { B F _ { A } }$ 和 $\mathrm { B F _ { B } }$ ，再对 ${ \mathrm { B F _ { A } } }$ 和BFb 进行and运算，生成最终的过滤位数组BF。使用BF分别对需要连接的两张数据表进行过滤操作，过滤掉不满足join连接的数据记录，生成两个数据表RDD_a_f和RDD_b_f。

![](images/cca60a7959c9f8340d5f12a917976d77d2b93395db280c490e069286f045d144.jpg)  
图1算法第一阶段：过滤连接表

![](images/a1844e13dd232c03c41a75e0e777d75b4cc8159d698e6c5f2091b6ed8011f073.jpg)  
图2算法第二阶段：采样统计数据分布

![](images/a7e0c9b9d7629fa98b1c0a2f29796ae2c788a14b1f7526cbe009afe69642e3e6.jpg)  
图3算法第三阶段-分段预连接并组装连接结果

表1图中所用符号说明  

<html><body><table><tr><td>符号</td><td>描述</td></tr><tr><td>RDD_a(b)</td><td>RDDa(数据表a,数据表b)</td></tr><tr><td>JoinKey_a(b)</td><td>RDD a(b)的连接属性</td></tr><tr><td>BFA(B)</td><td>RDDa(b)的BloomFilter位数组</td></tr><tr><td>BF</td><td>BloomFilter位数组</td></tr><tr><td>RDD_a(b)_f</td><td>分区后的RDD_a(b)</td></tr><tr><td>RDDai(bi)</td><td>RDD_a(b)拆分出的分区</td></tr><tr><td>JoinKey_a(b)_f</td><td>对RDD_a(b)_f抽取Joinkey 操作获得的集合</td></tr></table></body></html>

# 1.2采样分析-统计数据分布

对过滤后的两个分区RDD_a_f和RDD_b_f分别抽取Joinkey操作获得JoinKey_a_f和JoinKey_b_f两个集合。对JoinKey_a_f和JoinKey_b_f两个RDD使用sample 算子，分别对两个分区的Joinkey进行采样（如果采样率太大会造成数据量很大的计算负担，根据帕累托法则，将采样率定为0.2)，得出两份样本，然后对两个样本进行统计分析量，计算出来两张表中数据量最大的是哪几个key和相应的数据倾斜情况。

# 1.2.1采样分析

设两个表中较小的表为RDDS，下面对RDDS连接属性Key 进行采样分析。

给定采样率β，对RDD_S进行采样得到样本集合SampleKeysRs并分析 SampleKeysRs 样本中Key 的倾斜情况，依据Key 频次分布和Key整体分布进行划分为两类互不相交的集合，把频次分布频次高的放在集合 $\mathbf { S } _ { \mathrm { s t e w } }$ ，频次相对均匀或者频次低的放在集合 $\mathrm { \Delta S _ { d i s } }$ 中。RDD_S中出现未在 SampleKeyRs包含的Key，依据统计概率，属于频次很低的key，也放入 $\mathrm { \ S d i s }$ 中。

$$
R D D _ { - } S _ { _ { K e y } } = S _ { _ { s t e w } } \bigcup S _ { _ { d i s } }
$$

采样操作使用 Spark 提供的ReservoirSample(水塘采样算法)进行操作,其目的在于从包含 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个项目的集合S中选取 $\mathbf { k }$ 个样本，其中 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 为一很大或未知的数量，尤其适用于不能把所有n个项目都存放到主内存的情况，使用ReservoirSample可以减少采样占用的内存空间。

# 1.2.2统计数据分布

对于采样得到的两个样本集JoinKey_a_s和JoinKey_b_s分别进行统计分析和对比，主要目标是查看两个RDD中key 对应数据分布情况和数据倾斜情况。由于 Spark Statistics 库中有概括统计、分层统计、核密度估算等方法，故使用SparkStatistics进行统计分析。对于单个样本集进行统计分析主要是为了查看单个RDD中数据的倾斜情况，和估算单个表中Key 对应数据总量。对于两表的样本集统计分析结果进行对比是为了找出两个分区中相同Key值的数据分布情况。在做统计分析时，利用SparkStatistics库中的方法，得到如下统计信息：a)单个RDD单个 Key 占的比例 $\scriptstyle \mathrm { \mathrm { R } } _ { \mathrm { k } }$ ；b)单个RDD 数据倾斜严重的 Key；c)单个RDD 中Key 按照采样样本中的量的自然排序；d)两个RDD中相同Key 的数据比例Rs。

# 1.3分段预连接并组装连接结果

对两表中较小的表RDD_S，进行Key抽样，得到Key抽样样本集合SampleKeysRs。根据 SampleKeyRs 中Key 的倾斜情况和RDD_B_UK中Key 的分区号对RDD_S进行拆分。拆分过程使用贪心算法把RDD_S动态拆分成一定数目的子集RDD_Si。每次拆分出一个子集RDD_Si就进行RDD_B与该子集的连接，连接后再拆分并连接，直至所有RDD_S 数据连接完成。这一过程中都是每次拆分出RDD_Si后再连接再拆，因而每次的RDD_Si的数据量相对于RDD_S很小，无须占用大量内存空间和计算量。下面分别对单侧表拆分方法、预连接和连接结果的组装进行了详细的描述。

# 1.3.1单侧表拆分方法

对预连接得到的PreJoined，需要根据PreJoined中Key包含的分区号进行重划分，因此PreJoined中包含的分区号的均匀分布和整体性是影响划分并行度的因素。而每个分区号对应的所有Key的数据倾斜情况是直接影响连接组装各个计算节点负载量，为此选取的贪心策略主要参考以下三点：

a)拆分的子集RDD_Si的所有Key包含的分区号要均匀分布，每个Key对应的分区号数量上要基本相等。所有Key对应的分区号整体性要接近RDD_B的所有分区号整体性。

b)任意一个分区上对应的所有Key的数据规模要和其他分区上接近。

c)对于上述两点，贪心策略主要依据 RDD_B_UK 中 Key所对应分区列表及RDD_S的Key抽样分析划分的集合 $\mathbf { S } _ { \mathrm { s t e w } }$ 和Sdis 作启发选择。

整个拆分过程是使用贪心算法把RDD_S动态拆分成一定数目 $\mathfrak { n }$ 的子集RDD_Si， $0 \leq i < n$ 。拆分过程是n-1次运算，每次使用贪心策略每次对输入的 RDD_Sj拆分出其 RDD_Si，其中， $0 \leq j < n$ 。

数据表RDD_Sj和RDD_Si满足以下关系：

始化输入RDD_Sj的值为RDD_S

$$
R D D _ { - } S = R D D _ { - } S _ { j } \cup R D D _ { - } S _ { i }
$$

$$
R D D _ { - } S _ { j } = R D D _ { - } S _ { j + 1 } \cup R D D _ { - } S _ { i }
$$

$$
i , j = n - 1 , R D D _ { i } = R D D _ { j }
$$

拆出RDD_S 的子集 $\mathrm { R D D \underline { { S } } _ { i } }$ 后，就用RDD_B_UK和RDD_Si进行连接阶段，连接阶段包括预连接和组装连接结果。重复上述过程直至RDD_S中所有Key 都被拆分出来，并进行过连接。

# 1.3.2预连接

RDD_B_UK和RDD_S的子集RDD_Si进行并行连接得到连接结果PreJoined，PreJoined中每个元素包含了一个Key和RDD_Si中对应于该Key的元组，以及该Key对应的RDD_B分区号的列表。经过拆分的RDD_Si的数据规模远小于RDD_S,且RDD_B_UK的数据量也很小，故预连接的速度很快，并且预连接的结果分布在计算结果中，减少了Shuffle的开销。

# 1.3.3组装连接结果

将PreJoined数据进行按照Key所对应的分区号的重划分，而且分区号与RDD_B（选定较大的表RDD_B，并且生成连接属性Key与分区号列表的无重集，就是为了减少连接过程中数据重划分的量）分区号是一一对应，划分得到的结果集和RDD_B 存储在相同的分区，之后再通过 zipPartitions 操作将

RDD_B和PreJoined 做快速的组装。这一过程没有在网络上传输 RDD_B中的数据。且前面选择的贪心策略会使这一过程中数据倾斜度降低，各个节点负载基本平衡，且分区号的分布均匀，这种整体性能够充分利用集群节点的并行计算能力，提高计算速度。

# 2 算法分析

# 2.1网络I/O代价分析

本连接算法中，单表去重阶段没有网络开销，网络I/O开销来自广播BloomFilter进行过滤和连接阶段的预连接过程的数据划分和连接结果的组装，如式(2)所示：

$$
N e t C o s t = N e t C o s t _ { b f } + N e t C o s t _ { p j } + N e t C o s t _ { z p }
$$

算法虽然是拆分单侧表，但所有拆分并连接的网络I/O数据量等于单侧表网络I/O数据量，且每次拆分并连接的网络I/O数据量远小于单侧表网络I/O数据量造成的网络压力。其中NetCostpj是预连接数据划分的网络I/O代价，用数据量表示，如式(3)所示：

$$
N e t C o s t _ { p j } = S i z e \big ( R D D _ { - } B _ { - } U K \big ) + \alpha \bullet S i z e \big ( R D D _ { - } S \big )
$$

由于过滤去重后的RDD_B_UK中元组个数少于RDD_B,且每个元组仅包含一个Key值及其对应的分区号，因此RDDBUK的数据量远小于RDDB，即：

$$
\begin{array} { r } { { S i z e ( R D D \_ B \_ U K ) } = \alpha \bullet \varepsilon \bullet { S i z e ( R D D \_ B ) } \quad } \end{array}
$$

其中， $0 < \alpha \ll 1 , 0 < \varepsilon \ll 1$

NetCostzp是结果组装的网络I/O代价，通常由于预连接之后相当于RDD_B_UK在连接属性上又做了全局的去重且排除了不能连接的元组，NetCostzp会远低于 $\mathrm { N e t C o s t _ { p j } }$ 。而NetCostbf是使用BloomFilter进行两表过滤生成的压缩位数组的网络I/O代价，因此数据量也远小于 $\mathrm { N e t C o s t _ { p j } }$ 。

设参与连接的节点数为 $\mathrm { ~ N ~ }$ ，则总的通信量将由这些节点分摊，因此本文算法的网络I/O代价估算结果如式(4)所示：

$$
N e t { \bf C o s } t \approx N e t { \bf C o s } t _ { p j } + N e t { \bf C o s } t _ { z p } + N e t { \bf C o s } t _ { b f }
$$

$$
\leq \frac { \alpha \bullet \varepsilon \bullet S i z e ( R D D _ { - } B ) + S i z e ( R D D _ { - } S ) } { N }
$$

其中， $0 < \alpha \ll 1 , 0 < \varepsilon \ll 1$

# 2.2 内存空间代价分析

算法中构建的BloomFilter数据结构在过滤完表后就释放，不需要缓存在内存中。整个拆分过程中需要缓存过滤后两表Key及其分区号和Key的倾斜集合 $\mathbf { S } _ { \mathrm { s t e w } }$ ，并且预连接的结果也需要缓存，故占用了一定的内存消耗。Sstew是根据给定抽样率对过滤后的RDD_S 的倾斜数据的Key 的集合，因此 $\mathrm { S } _ { \mathrm { s t e w } }$ 内存销号远小于Size(RDD_S),所以算法的内存代价如式(5)所示：

$$
\begin{array} { c } { { M e m \mathrm { C o s } t = 2 \times S i z e ( R D D _ { - } B _ { - } U K ) + } } \\ { { \alpha { \bullet } S i z e ( R D D _ { - } S ) + S i z e ( S _ { s t e w } ) } } \\ { { \approx 2 \times S i z e ( R D D _ { - } B _ { - } U K ) + \alpha { \bullet } S i z e ( R D D _ { - } S ) } } \end{array}
$$

# 2.3对比分析

由于SparkBroadcastJoin只能应用于两表中有一表是小表的场景，因此本文只和目前应用较为广泛的HashJoin方式作对比分析。HashJoin 是重划分连接，所以每个节点的网络通信量为 $( \mathrm { S i z e ( R D D \_ B ) 4 S i z e ( R D D \_ S ) ) / N }$ ，故所需内存空间为$\operatorname { S i z e } ( \mathrm { R D D \_ B } ) { \operatorname { + S i z e } } ( \mathrm { R D D \_ S } )$ 。本文算法与 SparkHashJoin 算法的对比如表2所示。

表2两种等值连接算法代价对比分析  

<html><body><table><tr><td colspan="2">等值链接 网络I/O代价 算法</td><td rowspan="2">内存空间代价</td></tr><tr><td rowspan="2">Hash连接</td><td>Size(RDD_B)+Size(RDD_S)</td></tr><tr><td></td><td>Size(RDD_B) +Size(RDD_S)</td></tr><tr><td rowspan="3">本文算法</td><td>N α·ε·Size(RDD) B)</td><td></td></tr><tr><td>N</td><td>≈ α·Size(RDD_S)</td></tr><tr><td>+ Size(RDD S) N</td><td>+2× Size(RDD_B_UK)</td></tr></table></body></html>

# 3 实验分析

实验选用了2组数据表，每组都是2个数据大小不同的数据表(第一组数据倾斜程度低于第二组)，给定的抽样率为 $40 \%$ 分别使用本文算法和 Spark 的HashJoin 算法对数据进行了关联操作，并作对比分析。两表的关联字段分别是C_RID 和P_RID。数据表大小如表3所示：

<html><body><table><tr><td>表3</td><td>数据集大小</td></tr><tr><td>数据集</td><td>1 2</td></tr><tr><td>表1</td><td>7.2G 7G</td></tr><tr><td>表2</td><td>8.6G 9.1G</td></tr></table></body></html>

# 3.1实验环境

实验环境使用的软件名称，如表4所示。

表4软件环境  

<html><body><table><tr><td>操作系统</td><td>JDK版本</td><td>Hadoop</td><td>Spark</td></tr><tr><td rowspan="2">CentOS7-x64</td><td>Oracle</td><td>Apache</td><td>Apache</td></tr><tr><td>jdk1.8.0_92</td><td>Hadoop 2.7</td><td>Spark 2.1.0</td></tr></table></body></html>

本文的硬件环境是在实验室的计算机上使用VMWare创建的CentOS7虚拟集群环境中进行的，集群中共有6个节点，每个虚拟节点硬件配置如表5所示。

表5硬件环境  

<html><body><table><tr><td>CPU</td><td>内存</td><td>硬盘</td><td>网络</td></tr><tr><td>2核2.6GHz</td><td>2GB</td><td>60 GB</td><td>100 Mbps</td></tr></table></body></html>

# 3.2实验结果

两组实验的运行结果如图4所示。

图4中的执行时间是3次执行取得的平均值，单位为 $\operatorname* { m i n }$ 。通过实验结果本文连接算法的执行速度仍然比SparkSQL中的

HashJoin高出1倍以上，并且通过图4中两组实验中使用同一种算法的执行速度对比，当两组实验的数据表规模变化不大时，如果数据倾斜情况不一样，使用SparkHashJoin得到的两次时间变化比较明显，尤其是第二组实验的数据集倾斜情况比第一组数据严重，对应的HashJoin执行时间明显比第一组满了4.8min；而本文算法的执行速度变化不大，本文算法第二组实验比第一组仅慢了 $0 . 7 \mathrm { m i n }$ 。通过以上分析，可见本文的算法在做连接操作时，不仅比SparkHashJoin 操作的执行速度快，而且在面对数据倾斜情况依然具有变化不大的执行效率。

![](images/55e0fcd588213905d383ffe41ab41b1b3d8c7740c26599616b6aa99b3329d467.jpg)  
图4连接执行时间对比

# 4 结束语

目前 Spark在数据分析中已经普及，交互式大数据分析业务需求越来越多。链接性能一直是交互式数据分析中的性能瓶颈。本文通过对目前Spark/MapReduce上的等值连接算法进行了分析研究，提出了一种基于Spark的等值连接过程优化算法。本算法有很好的适用性，从大数据价值密度低特征和数据倾斜情况出发，过滤、去重、拆分连接过程，并通过实验和分析证明了比现有的连接算法的性能提升，且对数据倾斜具有适应性。

# 参考文献：

[1]Spark [EB/OL].http://spark.apache. org/.   
[2]于俊，向海，代其锋，等.Spark 核心与高级应用[M].北京：机械工业 出版社,2016.   
[3]Armbrust M, Xin R S,Lian C,et al. Spark SQL: relational data processing in Spark $[ \mathrm { C } ] / \AA$ Proc of ACM SIGMOD International Conference on Management of Data.New York: ACMPress,2015:1383-1394.   
[4]Blanas S,Patel JM, Ercegovac V,et al.Acomparison ofjoin algorithms for log processing in MaPreduce [C]//Proc of ACM SIGMOD International Conference on Management ofData.New York: ACMPress,2010: 975-986.   
[5]Xu Y, Zhou X, Chen L,etal. Handling data skew in parallel joins in sharednothing systems [C]// Proc of ACM SIGMOD International Conference on Management of Data.New York:ACMPress,2008:1043-1052.   
[6]Ramesh S,Papapetrou O, Siberski W. Optimizing distributed joins with bloom filters [Cl//Proc of International Conference Distributed Computing and Internet Technology. 2008: 145-156.   
[7]Zhou J, Wang Q, Gao J,et al. An approach for load balancing in MapReduce via dynamic partitioning [J]. Journal ofComputer Research & Development, 2013.   
[8]Gufler B,Augsten N,Reiser A,et al. Load balancing in mapreduce based on scalable cardinality estimates [C]// Proc of IEEE International Conference onData Engineering.Washington DC:IEEE Computer Society,2012:522- 533.   
[9] Gufler B,Augsten N, Reiser A,et al. Handling data skew in MapReduce [C]// Proc of International Conference on Cloud Computing and Services Science.2011: 574-583.   
[10]卞昊穹，陈跃国，杜小勇，等.Spark上的等值连接优化[J].华东师范 大学学报：自然科学版,2014,2014(5):263-270.   
[11] Hacigumus H,Iyer B,Mehrotra S.Providing database as aservice [C]//Proc of International Conference on Data Engineerin.2oo2:29-38.   
[12]王卓，陈群，李战怀，等．基于增量式分区策略的MapReduce 数据均衡 方法[J].计算机学报,2016,(1):19-35.   
[13]聂长海，蒋静．覆盖表生成的可配置贪心算法优化[J].软件学报,2013 (7): 1469-1483.