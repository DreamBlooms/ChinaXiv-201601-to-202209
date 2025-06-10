# 多MapReduce作业协同下的大数据挖掘类算法资源效率优化

廖彬1，张陶²，于炯²，黄静莱'，国冰磊²，刘炎(1.新疆财经大学 统计与信息学院，乌鲁木齐 830012;2.新疆大学 信息科学与工程学院，乌鲁木齐 83008;3．清华大学 软件学院，北京 100084)

摘要：由于任意的MapReduce 作业都需要独立的进行任务调度、资源分配等一系列复杂的操作，这使得同一算法协同的多个MapReduce作业之间，存在着大量的冗余磁盘I/O及资源重复申请操作，导致计算过程中资源利用效率低下。大数据挖掘类算法通常被切分成多个MapReduce Job 协作完成，以ItemBased 算法为例，对多 MapReduce 作业协同下的大数据挖掘算法存在的资源效率问题进行了分析，提出基于 DistributedCache 的 ItemBased 算法，利用DistributedCache 将多个MapReduce Job之间的I/O数据进行缓存处理，打破作业之间独立性的缺陷，减少Map 与Reduce 任务之间的等待时延。实验结果表明，DistributedCache 能够提高 MapReduce 作业的数据读取速度，利用DistributedCache 重构后的算法极大地减少了Map与Reduce任务之间的等待时延，资源效率提高3倍以上。

关键词：MapReduce 优化；ItemBased算法；内存文件系统；I/O效率；资源优化 中图分类号：TP393.09 doi:10.19734/j.issn.1001-3695.2018.11.0795

# Resource efficiency optimization for big data mining algorithm with multi MapReduce collaboration scenario

Liao Bin1†, Zhang Tao², Yu Jiong²,Huang Jinglai1, Guo Binglei²,Liu Yan³ (1.CollegeofStatistics&Information,Xinjiang UniversityofFinance&Economics,Urumqi83012,China;2.Schoolof Information Science& Enginering，Xinjiang University， Urumqi 830o08，China；3.School of Sofware，Tsinghua University,Beijing 100084,China)

Abstract: Because any MapReduce job requires a series of complex operations such as task scheduling and resource allocation independently,there are alotofredundant disk I/Oandresource duplicate application operations among multiple MapReduce jobscoordinatedby thesame algorithm,causing ineficient resource utilization in jobcomputing process.Big data mining algorithms are usually divided into several MapReduce Jobs,taking ItemBased algorithm as an example,this papere analyze the resource eficiency of mining algorithm with multi-MapReduce jobcollaboration scenario.It proposed anItemBased algorithm based onDistributedCache,which used DistributedCache to cache I/Odatabetweenmultiple MapReduce Jobs,breaks thedefectof independence between jobs,and reduced the waiting delay between Map and Reduce tasks.The experimental results show that, DistributedCache can improve the data reading speed of MapReduce jobs.The algorithm reconstructed by DistributedCache greatlyreduces the waiting delay between Mapand Reduce tasks，and improves the resource effciency by more than three times.

Key words: MapReduce optimization; ItemBased algorithm; memory file system; I/Oeficiency; resource optimization

# 0 引言

据IDC(InternetDataCenter)2015年发布的报告[1]显示，全世界在2015年产生的数据总和接近10ZB，并且这一数字预计到2020年将达到44ZB。数据爆发式的增长为IT产业带来了机遇与挑战，数据产生的过程由被动模式转变为主动产生，标志着大数据时代的来临。大数据的规模效应导致其存储、计算、分析及管理等成本不断上升，这使得高效率低成本的大数据计算技术逐渐成为学术界及工业界的研究热点。自谷歌2003年发表论文公开分布式存储系统GFS[2及计算模型MapReduce[3]以来,MapReduce 计算模型逐渐成为Hadoop、Spark、Pig、Hbase及Hive等大数据系统最通用的底层计算框架。

MapReduce与之前的并行计算模型(如PRAM、MPI等)相比，根本区别是MapReduce秉承“移动计算"而非“移动数据"的思想，“移动计算"的核心本质是将计算程序调度到离数据最近(本地)的计算节点，以达到减少数据密集型作业计算过程中的数据传输量的目的。但是当MapReduce 作业(Job)被调度系统分解成若干任务(Task)后，由于任务之间并不是孤立存在的，任务之间的协同执行过程，需要大量的磁盘读写和网络的传输操作(MapReduce 任务执行流程如图1所示)，比如Split、RecordReader、Partition及Shuffler 等操作，都会涉及将中间计算结果在不同机器之间网络传输并存到磁盘上作为之后pipeline 输入的操作。特别基于MapReduce 模型实现的大数据挖掘类算法，由于复杂度较高，算法通常需由多个MapReduce作业协作完成，如MapReduce下的PageRank算法会被分解为4个作业，而最常见的Bayes算法则会被分解为10个作业。但是同一算法下的多个MapReduce 作业之间，资源的调度与管理并不协同，严重的冗余磁盘读写及重复的I/O资源申请操作，造成算法的资源利用效率较低[4-6]。

![](images/e0db2d86515a0c0e29a3dbfc828480d8b2ba6e42e055d8bdf9d676c9898dd74c.jpg)  
图1MapReduce 任务执行流程  
Fig.1MapReduce's task execution process

推荐算法属于大数据挖掘类算法中应用最广泛的一种，本文以ItemBased协同过滤算法为研究对象，研究大数据挖掘类算法多MapReduce作业之间的资源效率问题，本文做了如下几个方面的工作：首先，对MapReduce环境下的ItemBased算法存在的资源效率问题进行了分析；其次，在问题分析的基础上，提出将同一算法协同的多个MapReduce作业之间的I/O数据进行统一的缓存处理，整体上减少算法计算过程中冗余的I/O操作，从而达到优化资源利用效率的目的；最后，通过对比实验验证了资源利用效率的提升。

# 1 相关研究

针对大数据挖掘类算法的研究，以推荐算法为例，大部分研究目标都是以提高算法在特定应用场景下(如电子商务、新闻推荐、视频推荐等)的推荐质量。评价算法优越性的主要参数有准确率(Precision)、召回率(Recall)、F值(F-Measure)、E值(E-Measure)、平均正确率(AveragePrecision)等。很少研究会关注到算法的执行环境优化、资源利用效率优化等方面。但随着算法处理数据量指数级的增长，以及大数据并行计算模型MapReduce的逐渐普及，算法逐渐从单机模型向分布式模型方向发展，并且算法的计算及资源利用效率等方面也逐渐受到学术界及工业界的重视。

文献[7,8]尝试借助MapReduce 程序的并行性来提高基于用户(User-Based)的协同过滤算法的计算效率，在 Hadoop平台上进行了算法的实现，并通过灵活设置作业map 及reduce任务的数量，进一步提高了算法的计算效率。Schelter等人[9]针对近邻(similarity-based neighborhood)协同过滤算法在面对海量数据增长时可扩展性差的问题，基于MapReduce模型对算法进行了重新实现，并通过7亿Yahoo音乐数据的测试，验证了算法在计算效率上的提升。文献[10]将MinHash聚类、概率潜在语义索引（PLSI）及Covisitation计数技术引入到Google news 的协同过滤算法中，其中MinHash进行概率聚类适用于聚类精度要求不高的场景，在此基础上再利用Mapreduce、Bigtable 等技术进一步提高算法的计算速度。文献[11]将协同过滤算法中最核心的计算步骤切分成四个MapReduce作业，并提出通过数据分区策略减小算法执行过程中的数据传输量，实验表明有效地提高了Itembased推荐算法的网络资源的利用效率。但不管是UserBased还是ItemBased协同过滤算法，MapReduce环境下的协同过滤算法都需要多个作业协作完成，MapReduce作业之间存在着大量的冗余I/O及资源重复申请操作，算法在资源利用效率上还存在着较大的优化空间。目前，面对MapReduce 数据挖掘类算法资源效率低下的问题，已有工作选择对算法进行平台移植，例如将算法从Hadoop 平台移植到Spark平台[12]，利用Spark内存及迭代计算的优势，达到提高算法效率的目的。虽然此方法能够带来不错的优化效果，但是算法平台的迁移主要存在以下两个方面的问题：

a）迁移成本问题。将算法从已有的Hadoop 迁移到Spark平台，由于开发语言从Java到Scala，算法整个实现的业务代码都必须按照新的API及语法重写[12]。迁移过程中，研发人员面临较高的学习及开发成本，而系统管理人员面临较高的系统迁移及部署成本。

b)稳定性问题。算法进行平台迁移后，由于新平台未经过长期的稳定性测试，新平台下的算法稳定性容易影响上层应用的服务质量。

基于以上讨论，本文与以往工作不同的是：以ItemBased推荐算法为例，分析其在MapReduce平台中存在的资源效率缺陷，提出将同一算法协同的多个MapReduce 作业之间的I/O 数据进行统一的缓存处理，整体上减少算法计算过程中冗余的I/O操作，从而达到优化资源利用效率的目的；与以往平台移植的方案相比，不需要重新开发业务代码，节省迁移及部署成本的同时，保证了系统的稳定性。

# 2多MapReduce作业协作的资源效率缺陷

由于物品与物品之间的相似度较为稳定，所以ItemBased推荐算法相比其他算法(如基于流行度、基于内容、基于模型的算法等)更加适合做离线计算，应用也最为广泛。ItemBased算法的核心思想是“物以类聚”，即假设能够引起用户兴趣的Item必定与其评分高的Item相似。算法首先计算用户对物品的喜好程度，然后根据用户的喜好计算Item之间的相似度，最后找出与每个Item最相似的top-N个Item。表1所示为Hadoop 平台下机器学习库 Mahout 中ItemBased 推荐算法的输入参数。

表1ItemBased 推荐算法主要参数  
Table1Main parameters of itembased recommendation algorithm   

<html><body><table><tr><td>参数名</td><td>意义</td></tr><tr><td>input</td><td>输入HDFS文件地址,其中行数据文件格式为： userid itemid preference</td></tr><tr><td>output</td><td>算法结果HDFS文件系统输出路径</td></tr><tr><td>numRecommendations</td><td>推荐数量(Top-N)</td></tr><tr><td>usersFile</td><td>推荐的 userFile</td></tr><tr><td>itemsFile</td><td>推荐的 itemFile</td></tr><tr><td>maxPrefsPerUser</td><td>阈值设置：最大偏好值</td></tr><tr><td>minPrefsPerUser</td><td>阈值设置：最小偏好值</td></tr><tr><td>maxSimilaritiesPerItem</td><td>给每一个Item计算最多的相似item数目</td></tr><tr><td>threshold</td><td>去除低于参数 threshold的item对</td></tr><tr><td>similarityClassname</td><td>指定进行相似性计算时调用的方法类名</td></tr></table></body></html>

ItemBased算法主要包括以下四个阶段：a)准备User-Item与Item-Item 两个矩阵;b)计算User-Item与Item-Item两个矩阵的相似度；c）partialMultiply，即将相似度矩阵用相同的Item 作为key聚合到一起，为后续的矩阵乘法做准备；d）计算推荐向量。进一步分解，可将以上四个步骤细分为以下九个MapReduce 作业，具体的MapReduce 作业所属阶段即执行顺序如表2所示。

单个 MapReduce 作业通过任务调度器分解为多个 map及reduce任务，通过input参数的设置值，输入数据从HDFS等文件系统中读入后送入相应的 Map 任务。当Map 计算结束后，数据通过Shuffle与Sort操作将 ${ \mathrm { < K , V > } }$ 键值对数据发送到指定的 Reduce 任务，其中 Reduce 计算过程中以<key,Iterator<value>>作为数据输入格式，最后将Reduce 结果写入到output参数指定的文件路径中。由于MapReduce作业的独立性，即任意 MapReduce 作业都需要独立的进行任务调度、资源分配、HDFS数据读取、任务计算、数据 Shuffle、结果输出等一系列复杂的操作。特别对于ItemBased推荐算法包含九个MapReduce作业的情况，以磁盘I/O资源为例，算法执行过程中需要分别执行多达18次对HDFS的读取与写入操作。这些高频次的数据读写操作降低MapReduce 集群资源的利用效率的同时，降低了算法整体的运行效率。并且由于磁盘I/O资源是MapReduce集群的性能瓶颈所在，高频次的磁盘I/O资源申请及释放操作容易产生资源竞争，使得 Map与Reduce任务之间容易出现等待现象，不同程度上进一步降低了算法的计算效率。通过以上分析表明MapReduce环境下的ItemBased算法性能优化并不能单从优化算法本身入手，MapReduce作业之间的独立性导致的重复磁盘I/O读取与写入操作，是导致ItemBased算法执行过程中资源利用与运行效率低下的主要原因。

表2ItemBased 推荐算法MapReduce 作业执行分解 Table 2Mapreduce job execution decomposition of itembased   

<html><body><table><tr><td colspan="3">recu onargorrhn MapReduce 阶段 MapReduce作业名称</td></tr><tr><td>步骤 1</td><td rowspan="3"></td><td>ItemIDIndexMapper-Reducer</td></tr><tr><td>2</td><td>PreparePreferenceMatrixJob ToItemPrefsMapper-Reducer</td></tr><tr><td>3</td><td>ToItemVectorsMapper-Reducer</td></tr><tr><td>4</td><td rowspan="4">RowSimilarityJob</td><td>CountObservationsMapper-Reducer</td></tr><tr><td>5</td><td>VectorNormMapper-Reducer</td></tr><tr><td>6</td><td></td></tr><tr><td></td><td>CooccurrencesMapper-Reducer</td></tr><tr><td>7</td><td></td><td>UnsymmetrifyMapper-Reducer</td></tr><tr><td>8 9</td><td>partialMultiply RecommenderJob</td><td>partialMultiply PartialMultiplyMapper-Reducer</td></tr></table></body></html>

# 3 ItemBased算法MapReduce作业资源优化

# 3.1ItemBased 算法多作业运行效率分析

如表2所示，ItemBased推荐算法中，一次计算过程切分为PreparePreferenceMatrixJob、RowSimilarityJob、partialMultiply及RecommenderJob四个阶段，并包括ItemIDIndexMapper-Reducer 等在内的九个MapReduce 作业。设MapReduce平台下某算法的运行总时间为 $T _ { s u m }$ ，计算过程被切分为 $N$ 个MapReduce 作业，并设每个MapReduce 作业的完成时间为 $\boldsymbol { \mathit { \Pi } } _ { T i }$ 。当一个MapReduce 作业完成后，下一MapReduce作业执行前需要进行资源准备，设两个MapReduce作业 $i$ 与 $i { + } l$ 之间的资源准备时间为 $P _ { i } ^ { i + 1 }$ ，那么算法的总体完成时间 $T _ { s u m }$ 为

$$
T _ { s u m } = \sum _ { i = 1 } ^ { N } T _ { i } + \sum _ { i = 1 } ^ { N - 1 } P _ { i } ^ { i + 1 }
$$

为了排除资源状态对真实的MapReduce 作业运行时间的影响，将受资源状态影响较大的数据输入时间 $T _ { i } { } ^ { i n p u t }$ ，计算结果输出时间 $T _ { i } { } ^ { o u t p u t }$ 以及作业执行过程中资源等待时间， $T _ { i } { } ^ { \mathrm { w a i r } }$ 等可变时间称为资源准备时间。那么某MapReduce作业 $i$ 的资源准备时间 $P _ { i } ^ { i + 1 }$ 为

$$
P _ { i } ^ { i + 1 } = T _ { i } ^ { \it i n p u t } + T _ { i } ^ { \it o u t p u t } + T _ { i } ^ { \it w a i t }
$$

而排除资源状态对MapReduce作业执行效率的影响后，单个MapReduce作业的实际运行时间由每个作业的子阶段

map、shuffler及reduce的运行时间累加而成：

$$
T _ { i } = T _ { m a p } + T _ { s h u f f e r } + T _ { r e d u c e }
$$

由式(1)\~(3)，可以得到整个算法的执行时间 $T _ { s u m }$ ：

$$
\begin{array} { c } { { \displaystyle T _ { s u m } = \sum _ { i = 1 } ^ { N } ( T _ { m a p } + T _ { s h u f f l e r } + T _ { r e d u c e } ) i } } \\ { { + \displaystyle \sum _ { i = 1 } ^ { N - 1 } ( T _ { i } ^ { i n p u t } + T _ { i } ^ { \it o u t p u t } + T _ { i } ^ { { \it u n d t } } ) } } \end{array}
$$

式(4)中，作业的子阶段 map、shuffler 及reduce 的运行时间与任务数量、节点计算能力、资源状态及数据量等因素关系密切。但是在任务数量、数据量及节点计算能力相同的条件下，资源状态则是影响作业运行时间的主要因素。由于不同 MapReduceJob之间的独立性，使得即使是同一算法的不同作业之间，在计算过程中，存在严重的磁盘I/O冗余及资源重复申请操作，导致MapReduce 算法资源利用效率严重降低。根据式(4)，理论上提高MapReduce 作业之间资源的利用效率(协作效率)，打破作业之间独立性的缺陷，能够达到提高MapReduce 复杂算法计算效率的目的。

# 3.2多MapReduce作业资源优化方法

通过第2章的缺陷分析及3.1节的理论分析，表明提高MapReduce作业之间资源的协作效率，解决作业之间独立性带来的资源重复操作，能够提高作业对的资源利用效率。总体上，可以通过以下两种方法来优化多MapReduce作业之间的资源效率：a)利用 MapReduce 框架内置的分布式缓存(DistributedCache)机制，打破MapReduce作业之间资源共享的屏障。缓存系统能够将共享数据分发到各计算节点的内存中，提高作业的计算效率；b)在基于磁盘的分布式文件(如HDFS)之上，引入以内存为中心的虚拟的分布式存储系统，将多MapReduce作业之间共享的数据资源从HDFS中加载到分布式共享内存中，从而减少对磁盘I/O的调用次数。优化方法a)的优点是针对特定算法级别的，灵活性较高；但是需要对算法部分代码进行重构和部署，需要对算法代码进行部分修改。优化方法b)将新的分布式内存文件系统部署到生产系统中，容易对整个系统的稳定性造成影响，但是省去了对算法代码的修改。针对单个的ItemBased算法，本文中采用方法a)来提高资源的利用效率。如下算法所示为基于DistributedCache的ItemBased算法步骤。

算法1 基于DistributedCache 的 ItemBased 算法.

INPUT:Parameterl:<userID，itemID，score>用户 评分 矩阵，Parameter2:InputURL.

OUTPUT:Parameterl:<userID，itemIDS $>$ 推荐结果，Parameter2: OutputURL.

$\textcircled{1}$ for $\scriptstyle { i = 0 }$ to readData(InputURL).blocksize-1 do   
$\textcircled{2}$ block $$ MEMORY.load(InputURL)//读取文件块   
$\textcircled{3}$ DistributedCache.addCacheFile(block)//将文件块加载内存   
$\textcircled{4}$ end for   
$\textcircled{5}$ foreach job inList<PreparePreferenceMatrixJob> list   
$\textcircled{6}$ MapReduce.start().getJob(list)   
$\textcircled{7}$ context.setCacheFiles(PreparePreferenceMatrixJob)   
$\textcircled{8}$ context.getCacheFiles()   
$\textcircled{9}$ end for   
$\textcircled{10}$ foreach job inList<RowSimilarityJob> list   
$\textcircled{1}$ MapReduce.start().getJob(list)   
$\textcircled{12}$ context.setCacheFiles(RowSimilarityJob)   
$\textcircled{1}$ context.getCacheFiles()   
$\textcircled{14}$ end for   
$\textcircled{15}$ MapReduce.start().getJob(partialMultiply)   
$\textcircled{16}$ context.setCacheFiles(partialMultiply)   
$\textcircled{1}$ context.getCacheFiles()   
$\textcircled{1}$ context.setCacheFiles(PartialMultiplyMapper-Reducer)   
$\textcircled{19}$ context.getCacheFiles()   
$\textcircled{20 }$ MapReduce.start().getJob(PartialMultiplyMapper-Reducer)   
$\textcircled{2 1 }$ returnJob.addCacheFile(new File("OutputURL"))

算法 $\textcircled{1}$ ， $\textcircled{4}$ 行将ItemBased算法根据输入参数InputURL 将输入数据加载到分布式缓存中； $\textcircled{5} \sim \textcircled { 9 }$ 行执行 PreparePreferenceMatrixJob 阶段所有的MapReduce 任务，使 得ItemIDIndexMapper-Reducer、ToItemPrefsMapper-Reducer 及ToItemVectorsMapper-Reducer三个Job之间在内存中实现 了数据共享； $\textcircled{10}$ ， $\textcircled{14}$ 行执行 RowSimilarityJob 阶段所有的 MapReduce任 务，DistributedCache实 现了CountObservationsMapper-Reducer、VectorNormMapper-Reducer、 CooccurrencesMapper-Reducer及UnsymmetrifyMapperReducer 四个Job 之间的内存数据共享；由于 partialMultiply 与RecommenderJob 两个阶段由单个MapReduce 作业组成， $\textcircled{15} \sim \textcircled { 2 0 }$ 实现了partialMultiply与PartialMultiplyMapperReducer 两个作业的内存数据读写操作；最后， $\textcircled{21}$ 行将算法计算结果 写入内存级的文件中。

# 4 实验评价与比较

# 4.1实验环境配置

为了对比ItemBased算法在不同测试环境下的执行效率及资源利用情况，本文设计了两组实验：实验1为MapReduce原生环境及DistributedCache 内存缓存条件下数据吞吐量的测试；实验2为ItemBased推荐算法在MapReduce原生环境及DistributedCache内存缓存条件下的对比测试。实验集群节点总数为11，其中管理(Master)节点数为1，作业执行节点(Worker)数为10。集群节点实验环境如表3所示。

表3总体实验环境描述  

<html><body><table><tr><td>项目</td><td>描述</td></tr><tr><td>操作系统</td><td>Ubuntu 14.04.5 LTS (Trusty Tahr)</td></tr><tr><td>JVM Version</td><td>1.8 forLinux OS</td></tr><tr><td>Hadoop</td><td>2.7.1</td></tr><tr><td>Version</td><td></td></tr><tr><td>节点CUP</td><td>Intel core i5 Skylake 3.2GHz</td></tr><tr><td>节点内存</td><td>8GB-DDR4-2400MHz (4GB*2)</td></tr><tr><td>节点硬盘</td><td>SeagateBarracuda1TB 7200 32MB SATA3</td></tr><tr><td>网卡信息</td><td>ST31000524AS TP-LINKTG-3269CPCIRJ-45</td></tr></table></body></html>

# 4.2实验1MapReduce 作业数据吞吐量对比测试

为了测试MapReduce 原生环境及DistributedCache 内存缓存条件下数据吞吐量的区别，本实验协同执行10个读取文本文件的MapReduceJob，这样可以将实验的MapReduce作业的性能瓶颈控制到I/O性能上。实验数据量大小为40GB的文本文件，HDFS及DistributedCache中数据块大小分别设置为 ${ 5 1 2 \mathrm { M B } }$ 与1GB不同的两组。HDFS中数据块的分布策略为默认的机架感知模式，每组分别进行三次测试，首先当数据块大小为512MB时测试结果如表4所示。

将HDFS 中的数据块大小配置项dfs.block.size以及DistributedCache中的数据块大小配置项从512MB设置为1GB，再次进行三次测试，得到测试结果如表5所示。

表4数据块大小为512MB时的测试结果Table 4Test resultswhen data block size is512MB  

<html><body><table><tr><td>编号</td><td>耗时/s</td><td>HDFS</td><td>DistributedCache</td><td>性能提升</td></tr><tr><td rowspan="5">1</td><td>Application total time</td><td>238</td><td>203</td><td>14.71%</td></tr><tr><td>Job total time</td><td>227</td><td>188</td><td>17.18%</td></tr><tr><td>Average map running time</td><td>8</td><td>6</td><td>25%</td></tr><tr><td>Shuffler running time</td><td>177</td><td>153</td><td>13.56%</td></tr><tr><td>Application total time</td><td>245</td><td>203</td><td>17.14%</td></tr><tr><td>2</td><td>Job total time</td><td>226</td><td>186</td><td>17.7%</td></tr><tr><td></td><td>Average map running time</td><td>8</td><td>6</td><td>25%</td></tr><tr><td rowspan="5">3</td><td>Shuffler running time</td><td>178</td><td>153</td><td>14.04%</td></tr><tr><td>Application total time</td><td>244</td><td>202</td><td>17.21%</td></tr><tr><td>Job total time</td><td>228</td><td>188</td><td>17.54%</td></tr><tr><td>Average map running time</td><td>8</td><td>6</td><td>25%</td></tr><tr><td>Shuffler running time</td><td>177</td><td>151</td><td>14.69%</td></tr></table></body></html>

表5数据块大小为1GB 时的测试结果

Table 3Description of experimental environment   
Table 5Test results when data block size is 1 GB   

<html><body><table><tr><td>编号</td><td>耗时/s</td><td>HDFS</td><td>DistributedCache</td><td>性能提升</td></tr><tr><td rowspan="5">1</td><td>Application total time</td><td>204</td><td>141</td><td>30.88%</td></tr><tr><td>Job total time</td><td>176</td><td>120</td><td>31.82%</td></tr><tr><td>Average map running time</td><td>15</td><td>9</td><td>40%</td></tr><tr><td>Shuffler running time</td><td>132</td><td>87</td><td>34.09%</td></tr><tr><td>Application total time</td><td>187</td><td>131</td><td>29.95%</td></tr><tr><td rowspan="5">2</td><td>Job total time</td><td>169</td><td>116</td><td>31.36%</td></tr><tr><td>Average map running time</td><td>15</td><td>10</td><td>33.33%</td></tr><tr><td>Shuffler running time</td><td>128</td><td>86</td><td>32.81%</td></tr><tr><td>Application total time</td><td>187</td><td>136</td><td>27.27%</td></tr><tr><td>Job total time</td><td>174</td><td>118</td><td>32.18%</td></tr><tr><td>3</td><td>Average map running time</td><td>15</td><td>10</td><td>33.33%</td></tr><tr><td></td><td>Shuffler running time</td><td>133</td><td>88</td><td>33.83%</td></tr></table></body></html>

根据表4与5中的数据可知，相比原生态的HDFS，无论是比较应用总体完成时间、作业总体完成时间、Map任务平均完成时间以及Shuffler运行时间，DistributedCache均能够提高MapReduce作业读取数据的速度。特别的，对比表4与5的数据，可以发现数据块大小为1GB时效率比 ${ 5 1 2 } \mathrm { M B }$ 效率提升更大。这是由于当数据块变大时，在作业数据集大小固定的前提下，整个MapReduce 作业Map 任务数量减少。由于相同集群中资源数量固定，所以资源竞争压力小，导致Map任务的读取速度变大，从而出现数据块越大，性能提升越明显的现象。

# 4.3实验2 ItemBased 推荐算法对比测试

实验中所采用的ItemBased推荐算法的实现版本来自于  
mahout的0.11.1版本，具体的算法运行类入口为  
org.apache.mahout.cf.taste.hadoop.item 包下的  
RecommenderJob类，使用原生HDFS文件系统为存储目标  
时的运行命令为：  
./hadoop jar  
/home/hadoop/mahout0.11.1/mahout-examples-0.11.1-job.jar  
org.apache.mahout.cf.taste.hadoop.item.RecommenderJob  
-i/mahout/itemcf/inputdata  
-o/mahout/itemcf/result  
-sSIMILARITY_LOGLIKELIHOOD  
--tempDir/mahout/itemcf/temp1  
其中：inputdata 为输入数据目录;result为输出文件目录;temp  
为作业运行过程中的临时文件目录。当使用DistributedCache

为存储系统时，按照算法1对ItemBased算法进行重构。重构后，由于需要在DistributedCache中运行，其运行命令与HDFS不同，其运行命令为：

./hadoop jar

/home/hadoop/mahout0.11.1/mahout-examples-0.11.1-job.jar org.apache.mahout.cf.taste.hadoop.item.RecommenderJob -idistributedCache://ubuntu201:23456/ratings/ratings.data -0 distributedCache://ubuntu201:23456/ratings/result -sSIMILARITY_LOGLIKELIHOOD --tempDir distributedCache://ubuntu201:19998/ratings/temp 其中：distributedCache://ubuntu201:19998/ratings/ratings.data 为算法输入数据路径；distributedCache://ubuntu201:23456/ ratings/result 为输出数据路径；distributedCache://ubuntu201:

23456/ratings/temp为临时文件目录；SIMILARITY_LOGLIKELIHOOD为相似性计算参数。

实验中，用户评分矩阵中<userID,itemID,score>数据对为 2000 万，将实验运行三次取平均值，得到HDFS 与DistributedCache资源效率对比如表6所示。

据表6中实验数据，当存储系统为HDFS时，算法总的资源等待时延为181s；当存储系统为DistributedCache时，算法总的资源等待时延缩短至 $3 9 \mathrm { ~ s ~ }$ 。利用DistributedCache重构后的算法，大大提高了作业的资源利用效率，资源等待总时延从原来的181s减少为 $3 9 \mathrm { ~ s ~ }$ ，资源效率提高了 $3 6 4 . 1 \%$ 。实验结果正好验证了3.1节中对MapReduce作业运行效率的分析，证明DistributedCache对资源的准备时间，即资源的利用效率方面的极大改进。

表6计算数据量为2000万时计算效率对比  
Table 6Comparison of computational efficiency when data is 20 million   

<html><body><table><tr><td colspan="3">ItemBased 算法阶段切分</td><td colspan="4">运行时间/s</td></tr><tr><td>Step</td><td>MapReduce 阶段</td><td>MapReduce 作业名称</td><td>HDFS 作业运 HDFS 资源等 DistributedCacheDistributedCache 行时间</td><td>待时延</td><td>作业运行时间</td><td>资源等待时延</td></tr><tr><td>1</td><td></td><td>ItemIDIndexMapper-Reducer</td><td>201</td><td>64</td><td>199</td><td>8</td></tr><tr><td>2</td><td>PreparePreferenceMatrixJob</td><td>ToItemPrefsMapper-Reducer</td><td>269</td><td>15</td><td>268</td><td>4</td></tr><tr><td>3</td><td></td><td>ToItemVectorsMapper-Reducer</td><td>207</td><td>14</td><td>207</td><td>3</td></tr><tr><td>4</td><td></td><td>CountObservationsMapper-Reducer</td><td>195</td><td>12</td><td>192</td><td>3</td></tr><tr><td>5</td><td>RowSimilarityJob</td><td>VectorNormMapper-Reducer</td><td>218</td><td>16</td><td>216</td><td>4</td></tr><tr><td>6</td><td></td><td>CooccurrencesMapper-Reducer</td><td>436</td><td>14</td><td>433</td><td>4</td></tr><tr><td>7</td><td></td><td>UnsymmetrifyMapper-Reducer</td><td>423</td><td>13</td><td>424</td><td>4</td></tr><tr><td>8</td><td>partialMultiply</td><td>partialMultiply</td><td>222</td><td>17</td><td>218</td><td>5</td></tr><tr><td>9</td><td>RecommenderJob</td><td>PartialMultiplyMapper-Reducer</td><td>826</td><td>16</td><td>821</td><td>4</td></tr></table></body></html>

![](images/6ee5aa2556351e3cf766480ecac6d3ad5abd5b8ebc499bf1f96c263df6023ad8.jpg)  
图2存储为HDFS时的磁盘IO情况

![](images/460a0102469e2fbea9f43246eced2b5f81605a9cb6841237a1097d2460191916.jpg)  
Fig.2Disk IO situation when storing as HDFS   
图3存储为DistributedCache 时的磁盘IO情况  
Fig.3Disk IO situation when storing as distributedcache

算法在不同的条件下，运行过程中的对磁盘I/O使用情况监控如图2与3所示。其中图2为存储系统为HDFS时的磁盘I/O使用情况，图3为存储系统为DistributedCache时的磁盘I/O使用情况。比如两图可以发现相比原生的HDFS，DistributedCache的磁盘I/O在作业运行过程中几乎为空闲状态，只有在最后作业运行完毕，即将作业运行结果写入HDFS时，才产生了较高的磁盘I/O资源消耗，这也进一步验证了实验结果中作业资源准备时间大大缩短的原因。使用DistributedCache时，快速的内存I/O代替了密集的磁盘I/O，不仅优化了作业运行过程中的资源利用效率，大大缩短了资源的准备时间，从而整体上提高了作业的运行效率。

# 5 结束语

MapReduce计算模式逐渐成为并行计算标准的同时，也存在一定的资源利用效率问题；特别在需要多个MapReduce作业协作完成的复杂大数据挖掘类算法场景，多个作业之间严重的冗余磁盘读写及重复的资源申请操作，使得MapReduce算法的执行时间、资源利用、能耗等方面的效率较低。本文发现造成该问题的原因是由于MapReduceJob的独立性，使得同一算法的不同作业之间存在严重的磁盘I/O冗余及资源重复申请操作，从而导致MapReduce算法执行效率严重降低。所以，本文首先对MapReduce环境下的ItemBased算法资源效率缺陷进行了分析，发现存在问题的同时提出利用DistributedCache缓存计算过程中产生的中间数据，从而减少算法执行过程中冗余的I/O操作，达到优化资源利用效率的目的。最后，通过两组实验证明了使用DistributedCache时，快速的内存I/O代替了密集的磁盘I/O，不仅优化了作业运行过程中的资源利用效率，大大缩短了资源的准备时间，从而整体上提高了资源的利用效率。通过实验结果表明，优化后的I/O资源效率提高3倍以上。下一步工作主要研究在集群负载压力较大时，即集群中同时运行多组大数据挖掘类算法时，DistributedCache资源的使用及调度效率。

# 参考文献：

[1]The digital universe in 2O2O:big data,bigger digital shadows,and biggest growth in the far east [EB/OL].[2018-3-15]. http://www. emc. com/collateral/analyst-reports/idc-the-digitaluniverse-in-2o20.pdf.   
[2]Ghemawat S,Gobioff H,Leung S T.The google file system [C]// Proc of the 19th ACM Symposium on Operating System Principles.New York:ACMPress,2003:29-43.   
[5]Cnen C,Lin J,Kuo S.Mapkeauce scneauiing Ior aeaqiine-constrainea jobs in heterogeneous cloud computing systems [J].IEEE Trans on Cloud Computing,2018,6 (1): 127-140.   
[4]廖彬，张陶，于炯，等.MapReduce 能耗建模及优化分析[J].计算 机研究与发展,2016,53(9):2107-2131.(Liao Bin,Zhang Tao,Yu Jiong,et al. Energy consumption modeling and optimization analysis for MapReduce [J]. Journal of Computer Research and Development, 2016,53 (9): 2107-2131.)   
[5]吴倩，王林平，罗相洲，等．基于MapReduce 的 top-k 高效用模式挖 掘算法[J]．计算机应用研究，2017,34(10):2897-2900.(WuQian, Wang Linping,Luo Xiangzhou,et al. Top-k high utility pattern mining algorithm based on MapReduce [J].Application Research of Computers, 2017,34 (10): 2897-2900.)   
[6] 廖彬，张陶，于炯，等.温度感知的 MapReduce 节能任务调度策略 [J]．通信学报,2016,37(1):61-75.(Liao Bin,Zhang Tao,Yu Jiong,et al.Temperature aware energy-efficient task scheduling strategies for mapreduce [J]. Journal on Communications,2016,37(1): 61-75.)   
[7]Zhao Zhidan，Shang Mingsheng.User-based collaborative-filtering recommendation algorithms on Hadoop [C]// Proc of International Conference on Knowledge Discovery and Data Mining.Piscataway, NJ: IEEE Press,2010: 478-481.   
[8]Ma M M,Wang S P. Research of user-based colaborative fltering recommendation algorithm based on Hadoop [C]// Proc of International Conference on ComputerInformation Systemsand Industrial Applications.New York: Atlantis,2015: 63-66.   
[9]Schelter S,Boden C,Markl V. Scalable similarity-based neighborhood methods with MapReduce [Cl// Proc of ACM Conference on Recommender Systems.New York: ACM Press,2012:163-170.   
[10] Das A S,Datar M, Garg A,et al. Google news personalization: scalable online collaborative filtering [C]//Proc of International Conference on World Wide Web.New York: ACMPress,2007: 271-280.   
[11] Jiang J,Lu J,Zhang G,et al.Scaling-Up Item-Based Collaborative Filtering Recommendation Algorithm Based on Hadoop [C]//Proc of IEEE World Congress on Services.Piscataway,NJ:IEEE Press,2011: 490-497.   
[12]廖彬，张陶，国冰磊,等．基于 Spark 的 ItemBased 推荐算法性能优化 [J]．计算机应用,2017,37(7):1900-1905.(Liao Bin,Zhang Tao,Guo Binglei,et al. Performance optimization of ItemBased recommendation algorithm based on Spark [J]. Journal of Computer Applications,2017, 37 (7):1900-1905.)