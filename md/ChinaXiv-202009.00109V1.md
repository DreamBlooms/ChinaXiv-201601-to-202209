# 基于MapReduce的并行频繁项集挖掘算法研究

刘卫明，张弛，毛伊敏(江西理工大学 信息工程学院，江西 赣州 341099)

摘要：针对并行 MRPrePost (paralel PrePost algorithm based on MapReduce)频繁项集挖掘算法在大数据环境存在运行时间长，内存占用量大和节点负载不均衡的问题。提出一种基于 DifNodeset 的并行频繁项集挖掘算法—PFIMD(paralel frequentitemsets mining using DiffNodeset)。该算法首先采用一种数据结构 DiffNodeset，有效的避免了N-list基数过大的问题；此外提出一种双向比较策略“T-wcs"(2-way comparison strategy)，以减少两个 DiffNodeset在连接过程中的无效计算，极大的降低了算法时间复杂度；最后考虑到集群负载对并行算法效率的影响，进一步提出了一种基于动态分组的负载均衡策略"LBSBDG"(load balancing strategy based on dynamic grouping)，该策略通过将频繁1项集F-list中的每项进行均匀分组，降低了集群中每个计算节点上PPC-Tree 树的规模，进而减少了先序后序遍历 PPC-Tree树所需的时间。实验结果表明，该算法在大数据环境下进行频繁项集挖掘具有较好的效果。

关键词：DiffNodeset 数据结构；MapReduce 编程模型；T-wcs 策略；LBSBDG 策略；频繁项集挖掘中图分类号：TP311 doi:10.19734/j.issn.1001-3695.2020.02.0039

Research on parallel frequent itemset mining algorithm based on MapReduce

Liu Weiming, Zhang Chi, Mao Yimin† (Schoolof Information Engineeing Jiangxi UniversityofScience&Technology,GanzhouJiangxi341099,China)

Abstract:Aimingat theproblemofexcesive time,spacecomplexityandunbalancedloadforeachnode basedontheparalel frequentitemset miningalgorithm MRPrePost,this paper proposedanoptimizationparalelfrequent itemset miningalgorithm basedonMapReduce,namedPFIMD.Firstly,thisalgorithmadoptedadatastructurecalledDiffNodeset,whicheffectively avoidthedefectthattheN-listcardinalitygotverylarge intheMRPrePostalgorithm.Secondly,inordertoreducethetime complexityof thisalgorithm,itdesigned theT-wcs (2-way Comparison Strategy）toavoid the invalidcalculation in the procesion of two DifNodesets connection.Finally,considering the impactof cluster loadonthe eficiencyof parallel algorithm,it proposed the LBSBDG(Load Balancing Strategy Based on Dynamic Grouping),which decreased the size of PPC-Tree on eachcomputing node and reduced the amount of time requiredto traverse the PPC-Tree by evenly grouping each itemin the F-list.The experimental results show thatthe modified algorithm has beter performanceon mining frequent itemset in a big data environment.

Key words: difodeset structure; MapReduce;2-way comparison strategy; load balancing strategy based on dynamic grouping; frequent item mining

# 0 引言

随着互联网信息技术的快速发展，大数据在社交网络、电子商务、精准营销等领域得到了广泛的应用。相较于传统数据，大数据的4V特性：Volume(数量大)、Variety(种类多)、Velocity(速度快)、Value(价值密度低)，使得在大数据环境下的数据挖掘算法需要满足以下几个条件：a）在大数据存储时，不仅需要存储结构化数据而且还要存储半结构和非结构化数据；b)数据量增大的同时，数据的价值密度降低，要求算法的挖掘精度能更高；c）新产生的数据必须要尽快处理，要求算法的实时性高1。鉴于此，大数据环境下的数据挖掘成为目前研究领域的一个重要主题。

数据挖掘又被称为知识发现KDD(knowledgediscoverindatabase)，其目的在于发现大量数据中有用的信息。常见的数据挖掘任务有关联规则挖掘、分类、聚类等。其中关联规则挖掘是其重要分支之一，通过关联规则的研究能够准确的找出有用的规则，这些规则对于企业管理上的决策具有巨大帮助[2]。传统关联规则挖掘算法根据其所挖掘的数据源呈现形式分为两类：a)基于水平型数据的算法，所谓水平型是指事务记录在数据库中按行存储，典型算法有Apriori算法[3]和FP-Growth算法[4]；b)基于垂直型数据的算法，所谓垂直型是指事务记录在数据库中按列存储，代表算法有Eclat算法[5]。随着信息技术高速发展，大数据环境下需要处理的数据量不断增加，运行时间和内存使用量成为传统关联规则挖

掘算法的重要瓶颈，单纯的通过提升计算机硬件水平来满足人们对大数据分析与处理的需求，显得尤为困难。此时并行化的计算思想变得非常重要，通过改进传统的关联规则挖掘算法，并与分布式计算模型相结合成为当前研究的主要方向。

近年来在大数据处理方面，Google开发的MapReduce 并行编程模型由于其操作简单、自动容错、负载均衡、扩展性强等优点深受广大学者和企业的青睐[]。同时 Apache 研发的Hadoop[7作为一种广泛使用的MapReduce 开源框架,不仅实现了对MapReduce的动态调用而且在很大程度上促进了MapReduce的应用开发。目前许多基于MapReduce计算模型的关联规则挖掘算法已成功应用到大数据的分析与处理领域中。文献[8\~10]采用传统Apriori算法多次迭代的思想，在每次迭代过程使用一个MapReduce 任务，实现了Apriori算法的并行化。但是在迭代过程中需要频繁访问数据集，对数据集进行多次迭代，消耗大量的时间和空间。鉴于并行Apriori算法的固有缺陷，文献[11\~14]中通过将FP-Growth 算法向MapReduce 计算模型进行迁移提出了并行FP-Growth算法。与并行Apriori算法不同，此类算法在挖掘过程中不产生候选项集，而是通过两次扫描事务数据集，在多个并行的节点上生成局部FP-Tree 树，并对局部FP-Tree树进行遍历得到局部频繁项集，然后将其合并得到全局频繁项集。此外在挖掘局部频繁项集的过程中，各计算节点之间可以独立计算，既不需要相互等待也不需要相互交换数据，极大的提高了并行关联规则挖掘算法的效率。然而并行FP-Growth算法在挖掘过程中需要花费大量时间来递归构建频繁项FP-Tree 树，且大数据环境下并行FP-Growth算法所构造的FP-Tree 树的规模十分巨大，对于FP-Tree 树的存储需要消耗大量的内存。考虑到并行水平格式算法的不足，文献[15\~18提出了并行的Eclat算法，此类算法在一定程度上克服了从海量数据集中挖掘频繁项集时存在内存和计算能力不足的问题。但并行的Eclat 算法需要将水平数据集转换为垂直数据集作为输入数据，这对于大数据来说是无法实现的。

为减少并行计算中单个节点的内存需求量与节点之间的通信量，Liao 等人[19]结合不同算法的优势提出了一种将dist-Eclat[15]与传统的FP-Growth 算法[4]相结合的混合算法--MRPrePost算法。该算法分为三个阶段：首先通过分布式计算得到频繁1项集F-list；其次构造F-list所对应的PPC-Tree树，并通过对PPC-Tree树进行先序和后序遍历产生频繁项的N-list；最后对N-list进行分组，并分布在多个节点上进行频繁项集的挖掘。相较于其他单一的并行关联规则挖掘算法，MRPrePost算法结合了并行FP-Growth算法和并行垂直算法的优点，既能对原始事务集进行无损压缩又可以快速计算项集的支持度，此外该算法将对树的挖掘过程转变成与垂直格式交运算类似的N-list合并过程，该过程不需要将PPC-Tree树保存在内存中，因此极大的节省了算法的计算时间和内存空间。但是该算法仍存在几个明显不足：1)在某些数据集上频繁项的N-list 基数过大，极易造成内存溢出；2)在合并两个频繁项的N-list时需要逐一比较两者中的每一项，时间复杂度较高；3)在并行挖掘频繁项集的过程中未能充分考虑到集群负载均衡对算法性能的影响。针对上述问题，本文提出了一种基于 DiffNodeset[21,22]结构的并行频繁项集挖掘算法—PFIMD(parallel frequent itemsets mining using DiffNodeset)。该算法采用了一种数据结构DiffNodeset，有效的避免了N-list 基数过大的问题；此外提出了一种双向比较策略"T-wcs"(2-way comparison strategy)，来减少两个DiffNodeset 在连接过程中的无效计算，极大的降低了算法时间复杂度；最后考虑到集群负载对并行算法效率的影响，进一步提出了一种基于动态分组的负载均衡策略"LBSBDG"(load balancingstrategy based on dynamic grouping)，该策略通过将频繁1项集F-list中的每项进行均匀分组，降低了集群中每个计算节点上PPC-Tree 树的规模，进而减少了先序和后序遍历PPC-Tree 树所需的时间。实验结果表明，该算法在大数据环境下进行频繁项集挖掘具有较好的效果。

# 1 算法及相关概念介绍

# 1.1PrePost算法相关定义

定义1 PPC-Tree[20]。PPC-Tree 树是一种树型数据结构,树中的每个节点均由以下五部分组成：

a)Item-name:节点名称b) count:节点计数c)pre-order:先序遍历序号d)post-order:后序遍历序号e)children-list:孩子节点集合

定义2 PP-code[20]。PP-code 编码又被称为先序后序编码，主要由 pre-order、post-order 和count 三部分组成。对于PPC-Tree树中的任意节点 $N$ ，则称(N.pre-order, $N$ post-order,N.count)为该节点的PP-code 编码。

性质1祖先孩子关系[20]。给定PPC-Tree 中任意两节点$N _ { 1 }$ 和 $N _ { 2 }$ （ $N _ { 1 } \neq N _ { 2 }$ )的PP-code，若满足 $N _ { 1 }$ .pre-order $< N _ { 2 }$ .pre-order,$N _ { \mathrm { 1 } }$ .post-order $> N _ { 2 }$ .post-order则称节点 $N _ { \mathrm { 1 } }$ 是节点 $N _ { 2 }$ 的祖先节点，$N _ { 2 }$ 为 $N _ { \mathrm { 1 } }$ 的孩子节点。

定义3频繁1项集的N-list[20]。在PPC-Tree 树中，代表相同项的所有PP-code编码根据先序遍历顺序连接生成的序列，被称为频繁1项集的N-list。

性质2频繁1项集的支持度[20]。给定项 item，其N-list为 $( x _ { 1 } , y _ { 1 } , z _ { 1 } ) , ( x _ { 2 } , y _ { 2 } , z _ { 2 } ) , . . . , ( x _ { \mathrm { m } } , y _ { \mathrm { m } } , z _ { \mathrm { m } } )$ ，则项item的支持度为$z _ { 1 } + z _ { 2 } + , . . . , + z _ { m }$ 。

# 1.2 DiffNodeset相关定义

定义4‘<’关系[21,22]。给定频繁1项集中的任意两项 $i _ { 1 }$ 和 $i _ { 2 }$ ，若 $i _ { 2 }$ 的支持度大于 $i _ { 1 }$ 的支持度，则表示为 $i _ { 1 } \prec i _ { 2 }$ □

定义52项集的DiffNodeset[21,22]。给定频繁1项集中的任意两项 $i _ { 1 }$ 和 $i _ { 2 } \left( i _ { 1 } \prec i _ { 2 } \right)$ ，其 $\mathrm { ~ N ~ }$ -list 结构分别为 $\mathrm { \Delta N - l i s t _ { \mathrm { l } } }$ ， $ { \mathbf { N } }  { - }  { \mathrm { l i s t } _ { 2 } }$ 。2项集 $i _ { 1 } i _ { 2 }$ 的DiffNodeset 结构记为 $D i f f N o d e s e t _ { 1 2 }$ ，定义如下：

$$
x \in \mathrm { N \mathrm { - l i s t } } _ { 1 } \land \lnot ( \mathrm { y \in N \mathrm { - l i s t } } _ { 2 } ) \}
$$

其中 $y$ 对应节点是 $x$ 对应节点的祖先节点。

性质32 项集的支持度[21,22]。给定2 项集 $i _ { 1 } i _ { 2 }$ ，其DiffNodeset表示为 $( x _ { 1 } , y _ { 1 } , z _ { 1 } ) , ( x _ { 2 } , y _ { 2 } , z _ { 2 } ) , . . . , ( x _ { n } , y _ { n } , z _ { n } )$ ，若 $i _ { 1 }$ 的支持度为 $\mathrm { s u p p o r t } ( i _ { 1 } )$ ，则 $i _ { 1 } i _ { 2 }$ 的支持度等于 $\mathrm { s u p p o r t } ( i _ { 1 } ) \cdot ( \mathrm { z } _ { 1 } \mathrm { + z } _ { 2 } \mathrm { + } , \mathrm { . . . , + z } _ { \mathrm { n } } )$ 。

定义6 $k$ 项集的DiffNodeset[21,22]。假设 $k$ 项集 $P = i _ { 1 } i _ { 2 } . . . i _ { k - 1 } i _ { k }$ $( i _ { 1 } \prec i _ { 2 } \prec \ldots \prec i _ { k - 1 } \prec i _ { k } )$ ，频繁 $k { - } 1$ 项集 $P _ { 1 } = i _ { 1 } i _ { 2 } . . . i _ { k - 2 } i _ { k - 1 }$ ， $P _ { 2 } = i _ { 1 } i _ { 2 } . . . i _ { k - 2 } i _ { k }$ 所对应的DiffNodeset分别记为 $D N _ { 1 }$ ， $D N _ { 2 }$ 。项集 $P$ 的DiffNodeset记为 $D N _ { P }$ ,其计算公式如下：

$$
{ D N _ { P } } = { D N _ { 2 } } / { D N _ { 1 } }
$$

其中 $\cdot _ { / } ,$ 表示集合差。

性质4 $k$ 项集的支持度[21,22]。给定 $k$ 项集 $P = i _ { 1 } i _ { 2 } . . . i _ { k - 1 } i _ { k }$ ，其DiffNodeset结构表示为 $( x _ { 1 } , y _ { 1 } , z _ { 1 } ) , ( x _ { 2 } , y _ { 2 } , z _ { 2 } ) \ldots , ( x _ { l } , y _ { l } , z _ { l } )$ ，若项集$P _ { 1 } = i _ { 1 } i _ { 2 } , . . . , i _ { k - 2 } i _ { k - 1 }$ 的支持度为 $\mathrm { s u p p o r t } ( P _ { 1 } )$ ，则项集 $P$ 的支持度等于support(P) - $( \mathsf { z } _ { 1 } { + } \mathsf { z } _ { 2 } { + } . . . { + } \mathsf { z } _ { l } )$ 。

# 2 PFIMD 算法

PFIMD算法主要包括三个阶段：挖掘频繁1项集、频繁1项集均匀分组和并行挖掘频繁项集。在第一阶段主要通过调用一次MapReduce任务来并行获取频繁1项集F-list；在第二阶段中考虑到集群负载均衡对并行算法挖掘效率的影响，使用动态分组策略LBSBDG将F-list中的每一项进行均匀分组，从而生成哈希表G-list；在第三阶段中主要包含并行挖掘频繁项集的 Map 阶段和Reduce 阶段，其中在Map 阶段各个节点根据前两个阶段产生的F-list和G-list来构造映射路径，在Reduce阶段各节点首先根据映射路径构造子PPC-Tree树，然后根据子PPC-Tree 树来挖掘局部频繁项集，最后合并得到全局频繁项集。

# 2.1挖掘频繁1项集

对于数据集DB,其频繁1项集的生成过程主要包括 SplitMap、Combine 以及Reduce 四个阶段。a)在 Split 阶段：使用Hadoop 默认的文件块策略，将原始数据集划分成大小相同的文件块Block;b)在Map 阶段：文件块Block作为输入数据，Mapper节点通过调用Map函数以键值对 $< k e y = \mathrm { i t e m } , \nu a l u e = 1 >$ 的形式统计出相应节点中各项出现的次数；同时为了降低集群中各节点的数据通信量，经过Mapper节点处理后的数据不会立刻发送给Reducer节点，而是先通过combiner进行本地结合；c)在Combine 阶段：本地节点中key 值相同的键值对进行累加，经过本地合并处理后的键值对会被自动分配到不同的Reducer 节点，同时key 值相同的键值对分配到相同的Reducer节点；d)在Reduce 阶段：需要对这些键值对的value值进行再次合并，即可得到每个数据项key在整个数据集中的支持数，最后根据最小支持度min_sup 筛选出频繁1项集F-list。

# 2.2频繁1项集均匀分组

针对大数据环境下频繁1项集F-list规模太大，无法在有限的内存空间中构造PPC-Tree 树的问题。本文提出了一种动态分组策略“LBSBDG”，该策略通过对F-list进行均匀分组，将原事务数据集各记录中的频繁项根据分组结果进行重新划分，并将原PPC-Tree树分割成多个独立的子树，使得每个节点上的子PPC-Tree树能够适应内存大小。采用“LBSBDG"分组策略对频繁1项集F-list进行均匀分组时，其关键在于计算F-list中每一项的负载量，即频繁1项集中每个项所对应N-list结构的长度。然而N-list中的元素与PPC-Tree 树中的节点一一对应，在未构造PPC-Tree 树之前无法准确计算出每一项的负载量。为了解决该问题，在“LBSBDG”分组策略中通过估计函数E(item)对频繁1项集item的长度规模进行预测。

定义7负载量估计函数E(item)。若频繁项item 的支持度为count，且在F-list中的位置为 $\mathbf { \xi } _ { l }$ ，则其负载量估计函数如下所示。

$$
E ( \mathrm { i t e m } ) = \operatorname* { m i n } \{ \mathrm { c o u n t } , 2 ^ { l - 1 } \}
$$

证明对于频繁项item来说，其N-list 的长度表示该项在PPC-Tree 树中的节点个数，显然对于每一项来说节点数的最大值为该项的支持度。而且在构造PPC-Tree 树时，树中每一项的节点数与其自身在F-list序列中的位置有关。对于频繁1项集item来说，假设其在F-list的位置为l，则最坏情况是排在item之前的l-1项中任意项组合在PPC-Tree中都有对应的路径，且该路径也包含项item，在此情况下这样的路径最多有 $2 ^ { \iota - 1 }$ 条。因此F-list中的每一项item的N-list长度不超过 $2 ^ { \iota - 1 }$ 与该项支持度之间的较小值。

对于频繁1项集F-list，采用“LBSBDG”分组策略将其划分为 $G$ 组的分组思想如下：首先根据式(3)计算出F-list中每一项的负载量，并根据负载量的降序排列生成L-list，选取L-list中的前 $G$ 项作为初值依次添加到 $0 { \sim } ( G { - } 1 )$ 组，并更新每一组的负载总量；然后继续对L-list 中未分组的项进行分组操作，每次读取 $\sigma$ 项，在划分之前需要判定当前每组的负载总量是否相同，若每组的负载总量均相同则顺序添加，即将$G$ 项分别添加到0\~(G-1)组，若不相同则逆序添加，即将 $G$ 项分别添加到 $( G { - } 1 ) { - } 0$ 组中，如果L-list中未分组项的个数小于 $G$ 则将其依次添加到负载量最小的组中；最后将所得到的分组结果G-list保存到分布式文件系统HDFS中，从而使得集群中任意节点都能访问到G-list。

“LBSBDG”分组过程的形式化如算法1所示。

算法1“LBSBDG"分组策略  
输入：频繁1项集F-list，分组数G  
输出：分组结果G-list  
a）计算F-list中每一项的负载量L-list $ \emptyset$   
1 Foreach item in F-list do  
2 Compute item_load by Eq.(3)$\mathrm { L - l i s t } \gets < k e y = i t e m , \nu a l u e = i t e m \_ l o a d >$   
3Sorted(L-list)//L-list 按value 值进行非递减排F  
4 End for  
b）F-list均匀分组$\mathrm { G - l i s t }  \{ \emptyset _ { 1 } , \emptyset _ { 2 } , . . . , \emptyset _ { G } \}$   
1 IfL-list.length $> = \mathbf { G }$ do  
2insert_item $$ {item,item.,...,item $\mathsf { I } _ { \mathrm { G } - 1 }$ }//每次选取L-list中的前G项  
3 If 每组的负载量均相同 do  
4G-list[i] $\left| \gets i t e m _ { i } \right. /$ /按顺序将每项添加到 $\scriptstyle { \Theta \sim \left( G - 1 \right) }$ 组  
5 G-list[i].load $\scriptstyle + = i t e m _ { i }$ .load//更新每组负载量  
6 Elsedo//如果每组负载量不全相同  
7G-list[ $G - i - 1 ] \gets i t e m _ { i } / /$ 逆序将每项添加到 $( G - 1 ) \sim \theta$ 组G-list[G-i- I].load $\scriptstyle + =$ item,.load  
8Del(insert_item)//删除已添加项  
9 End if  
10 Else do //如果L-list中剩余不足G项  
11 Foreach item in L-list do  
12 $g i d =$ getMinload(G-list)//获取目前负载量最小的组号G-list[gid] $$ itemG-list[gid].load $+ { = }$ item.load  
13 End for  
14 End if  
15 Output(G-list)

# 2.3并行挖掘频繁项集

采用“LBSBDG”分组策略对F-list进行均匀分组是为了将原始事务数据集中的事务进行重新划分，并把划分后的事务集映射到集群中的各个计算节点上。通过在各个节点上构建子PPC-Tree 树，来完成频繁项集的挖掘任务。在此过程中主要包括并行挖掘频繁项集的Map阶段和Reduce阶段，同时为了降低内存消耗，需要对原始数据集进行预处理，用项item在F-list中的位置来替换原始数据集中的item。经过预处理后，各个节点启动新的MapReduce任务进行频繁项集的挖掘。

# 2.3.1Map 阶段

在并行挖掘频繁项集的Map阶段，其主要任务是将预处理后的数据跟据哈希表HTable映射到集群中不同的计算节点上，其具体过程为：首先从分布式文件系统HDFS中读取全局频繁1项集F-list和算法1中所获得的哈希表G-list，并将G-list每组所包含的项作为key，组号gid作为value构建HTable；之后依次读取预处理后的每一条记录，逆序遍历该记录中的项item，根据之前得到的HTable，确定其组号gid，然后以 $g i d$ 为key，排在 item之前所有项为value组成键值对。与此同时为了避免同一条记录多次映射到同一节点，删除HTable中value $= g i d$ 的所有键值对。如果在映射时找不到对应的组号，则读取前一项执行相同操作，直到该记录执行完毕；最后将所得的所有结果作为Reduce阶段的输入传送给Reduce函数。其操作过程如算法2所示。

算法2并行挖掘频繁项集的 Map 过程  
输入：预处理后的数据pre_data，F-list，G-list  
输出：映射路径<key,value=path>  
a）建立哈希表HTable  
1 从HDFS 中读入G-list  
2 Foreach g in G-list do  
3 Foreach item in g doHtable[g[item]]=gid  
4 End for  
5 End for  
b）生成映射路径  
1 Foreach trans in pre_data do  
2 items[]←Split(trans）//将输入的数据进行分解并保存到空  
数组items[]中  
3 For j=len(items)-1 to 0 do  
4 IfHtable[items[j]] not null do//判断items[j]所在路  
径属于哪个组  
path $\mathbf { \sigma } = \mathbf { \sigma }$ {items[0],items[1],…,items[j]}  
5 End if  
output(key=Htable[items[j]],value=path)  
del(Htable[items[j]])  
6 End for  
7 End for

# 2.3.2Reduce阶段

在Reduce阶段，首先采用DiffNodeset数据结构避免N-list基数过大的问题。此外在合并两个频繁1项集的N-list过程中使用双向比较策略“T-wcs”能够极大减少比较次数，从而加快完成频繁1项集的N-list合并任务。

性质5序列一致性原则。对于频繁项 $N$ ，其N-list 表示为 $\{ ( x _ { 1 } , y _ { 1 } , z _ { 1 } ) , ( x _ { 2 } , y _ { 2 } , z _ { 2 } ) , . . . , ( x _ { n } , y _ { n } , z _ { n } ) \}$ ，则有 $x _ { 1 } < x _ { 2 } < . . . < x _ { n }$ ， $y _ { 1 } < y _ { 2 } < . . . < y _ { n }$ □

证明跟据 N-list 的定义本文可知 $x _ { 1 } < x _ { 2 } < . . . < x _ { n }$ 。假设$( x _ { 1 } , y _ { 1 } , z _ { 1 } )$ 对应节点 $N _ { 1 }$ ， $( x _ { 2 } , y _ { 2 } , z _ { 2 } )$ 对应节点 $N _ { 2 }$ ，由于$N _ { 1 }$ .item-name $\mathbf { \Psi } = N _ { 2 } \mathbf { \Psi }$ .item-name,则 $N _ { \mathrm { l } }$ 与 $N _ { 2 }$ 不存在祖先孩子关系，而 $x _ { 1 } < x _ { 2 }$ 说明 $N _ { 2 }$ 相较于 $N _ { \mathfrak { l } }$ 来说一定在右子树上，跟据后序遍历的规则，一定存在 $N _ { \mathfrak { l } }$ 的后序遍历序列小于 $N _ { 2 }$ 的后序遍历序列，即 $y _ { 1 } < y _ { 2 }$ ，依此类推 $y _ { 1 } < y _ { 2 } < . . . < y _ { n }$ 成立。

在并行挖掘频繁项集过程中最重要的一步是将频繁1项集的N-list结构合并产生2项集的DiffNodeset结构，如何降低该过程的运行时间是该算法的关键所在。为此本文提出了一种双向搜索策略“T-wcs”，该策略通过利用序列一致性原理和祖先孩子关系能够大大减少合并过程中所需要比对的次数。

给定两个频繁1项集 $i _ { 1 } , i _ { 2 } ( i _ { 1 } , i _ { 2 } \in \mathbb { F } \mathrm { - } \operatorname { l i s t } \wedge i _ { 1 } \prec i _ { 2 } )$ ，其N-list 分别表示为 $\mathrm { N - l i s t } _ { i 1 }$ 和 $\mathrm { N - l i s t } _ { i 2 }$ ，且长度为 $\mathbf { \nabla } _ { m }$ 和 $n$ ，其具体形式如下：

$$
\mathrm { N \mathrm { - } l i s t _ { \it i 1 } = \{ ( x _ { \it { i 1 } } , y _ { \it { i 1 } } , z _ { \it { i 1 } } ) , ( x _ { \it { i 2 } } , y _ { \it { i 2 } } , z _ { \it { i 2 } } ) , . . . , ( x _ { \it { i m } } , y _ { \it { i m } } , z _ { \it { i m } } ) \} } 
$$

$$
\mathrm { N - l i s t } _ { i _ { 2 } } { = } \{ ( x _ { 2 1 } , y _ { 2 1 } , z _ { 2 1 } ) , ( x _ { 2 2 } , y _ { 2 2 } , z _ { 2 2 } ) , { \ldots } , ( x _ { 2 n } , y _ { 2 n } , z _ { 2 n } ) \}
$$

在比较两者中的任意项 $( x _ { 1 a } , y _ { 1 a } , z _ { 1 a } )$ 和 $( x _ { 2 b } , y _ { 2 b } , z _ { 2 b } )$ 时，根据序列一致性原则只存在三种情况：

a) ${ \bf y } _ { 1 a } > { \bf y } _ { 2 b }$ ， $( 1 \leq a \leq m , 1 \leq b \leq n )$ 。根据祖先孩子关系可知$( x _ { 2 b } , y _ { 2 b } , z _ { 2 b } )$ 在PPC-Tree 树中所对应的节点 $N _ { i 2 } [ b ]$ 不是 $( x _ { 1 a } , y _ { 1 a } , z _ { 1 a } )$ （204号所对应节点 $\mathrm { N _ { i l } } [ a ]$ 的祖先节点。此外根据序列一致性原理可知频繁1项集的 $\mathrm { ~ N ~ }$ -list是按照post-order的升序序列排序，所以$N _ { i 2 } [ b ]$ 也不是 $\mathrm { N - l i s t } _ { i 1 }$ 中排在 $\mathrm { N _ { i l } } [ a ]$ 之后元素所对应的祖先节点，选择 $N _ { i 2 } [ b ]$ 下一个节点进行比较。

b) $x _ { 1 a } > x _ { 2 b } , y _ { 1 a } < y _ { 2 b }$ ， $( 1 \leq a \leq m , 1 \leq b \leq n )$ 。根据祖先孩子关系可知$( x _ { 2 b } , y _ { 2 b } , z _ { 2 b } )$ 在PPC-Tree 树中所对应的节点 $N _ { i 2 } [ b ]$ 是 $( x _ { 1 a } , y _ { 1 a } , z _ { 1 a } )$ 所对应节点 $\mathrm { N _ { i l } } [ a ]$ 的祖先节点。所以节点 $\mathrm { N _ { i l } } [ a ]$ 不包含在2项集的DiffNodeset中，选择 $\mathrm { N } _ { \mathrm { i l } } [ a ]$ 的下一个元素进行比较。

c） $\mathrm { \Delta _ { X _ { l a } } } < \mathrm { \Delta _ { X _ { 2 b } } } , \mathrm { \mathbf { y } _ { l a } } < \mathrm { y } _ { 2 b }$ ， $( 1 \leq a \leq m , 1 \leq b \leq n )$ 。根据祖先孩子关系可知$( x _ { 2 b } , y _ { 2 b } , z _ { 2 b } )$ 所对应的节点 $N _ { i 2 } [ b ]$ 不是 $( x _ { 1 a } , y _ { 1 a } , z _ { 1 a } )$ 所对应节点 $\mathrm { N _ { i l } } [ a ]$ 的祖先节点，此外 $\mathrm { N _ { i l } } [ a ]$ 也不可能是 $N _ { i 2 } [ j ]$ 之后任意元素的孩子节点，满足2项集DiffNodeset定义。故而将 $\mathrm { N } _ { \mathrm { i l } } [ i ]$ 插入到2项集的DiffNodeset中，并选择 $\mathbf { N } _ { \mathrm { i l } } [ i ]$ 的下一个节点进行比较。

其操作过程如算法3所示。

算法3双向搜索策略T-wcs 的执行过程输入：频繁1项集的N-list 结构输出：2项集的DiffNodesetProcedure T-wcs （ii）$D N _ { i 1 i 2 }  \emptyset$ （204号1 $a \gets 0$ ， $b \gets \mathbf { O }$ 2 $l _ { \mathrm { l } } \gets \mathrm { N } \mathrm { - } \mathrm { l i s t } _ { \mathrm { i } 1 }$ 的长度， $l _ { 2 } \gets \mathrm { N } \mathrm { - l i s t } _ { \mathrm { i } 2 }$ 的长度

3 while $a < l _ { 1 } \land b < l _ { 2 }$ do   
4 If $N _ { i 1 }$ [a].post-order $> N _ { i 2 } [ { \sf b } ] .$ post-order do   
$b \gets b + 1$   
5 Else   
6 If $N _ { i 1 } [ \mathrm { a } ]$ post-order $< N _ { i 2 } [ \mathrm { b } ]$ -post-order ^   
7 $N _ { i 1 }$ [a].pre-order $> N _ { i 2 }$ [b].pre-orderdo   
$\mathsf { a } \gets \mathsf { a } + 1$   
8 Else   
$D N _ { i 1 i 2 }  D N _ { i 1 i 2 } \cup \{ N _ { i 1 } l a J \}$   
$\mathsf { a } { \gets } \mathsf { a } { + } 1$   
9 End if   
10 End $\mathbf { i } \mathsf { f }$   
11 End while   
12 If $a < l _ { \mathrm { l } }$ then   
13 while $a < l _ { 1 }$ do   
$D N _ { i 1 i 2 }  D N _ { i 1 i 2 } \cup \{ N _ { i 1 } l a J \}$   
$\mathsf { a } { \gets } \mathsf { a } { + } \mathsf { 1 }$   
14 End while   
15 End   
16 Output $D N _ { i 1 i 2 }$ （204号

在并行挖掘频繁项集的Reduce阶段，系统中每个计算节点先要根据Map 阶段输出的键值对，通过调用insert_tree(函数在各个节点中构造PPC-Tree树，并对PPC-Tree树进行先序、后序遍历，从而得到频繁1项集的N-list，同时为了减少内存消耗，通常将 PPC-Tree 树从内存中删除；然后采用双向搜索策略“T-wcs”和性质3将频繁1项集的N-list结构进行合并得到频繁2项集的DiffNodeset；最后根据定义6和性质4迭代挖掘出所有的频繁项集。

算法4并行挖掘频繁项集的Reduce 过程输入：最小支持度min_sup,映射路径<key=Htable[Items[j]]，value $\mathbf { \sigma } = \mathbf { \sigma }$ path>输出：频繁项集F_itema）构造 PPC-TreeF_item $ \emptyset$ 1 root $$ null //PPC-Tree 初始化为空2 Foreach t in value do3 curNode $$ root//插入当前节点4 Foreach item in t do5 Call insert_tree(curNode,item)//调用insert_tree()函数构造 PPC-Tree 树6 End for7 End forF_item=F_item U F1b）生成频繁1项集的N-list1 scan_by_pre(root）//先序遍历 PPC-Tree2 scan_by_post(root）//后序遍历 PPC-Tree3 NL1[] $$ N-list_Constructtion(root)//生成所有频繁1项集的 $N$ -listc）生成频繁2项集的DiffNodeset$\mathsf { F } _ { 2 } \gets \emptyset$ $\mathsf { F } _ { 1 } \gets$ items1 Foreach item in $\mathsf { F } _ { 1 }$ do2 If groupID(item) $\scriptstyle = =$ key do3 DNi2 ← T-wcs(item)//调用 T-wcs 生成以 item 开头的DiffNodeset4 Foreach item in ${ \mathsf { D N } } _ { 1 2 }$ do5 Compute item_sup by property(3)6 If item_sup ≥min_sup do

F2.add(item)  
7 End if  
8 End for  
9 End if  
10 End for  
F_item=F_item U F2  
d）递归生成所有频繁项集  
1 Function:Mining_Fre_Items(DN_k,min_sup)  
2 Foreach DN_k[i],DN_k[j] in DN_k do  
3 $\mathrm { D N } _ { \mathrm { l } } \gets$ DN_k[i].DiffNodeset,  
$\mathsf { D N } _ { 2 } \gets$ DN_k[j].DiffNodeset  
$\mathrm { D N } _ { 1 2 } = \mathrm { D N } _ { 1 } \cup \mathrm { D N } _ { 2 }$   
$\mathrm { D N } _ { 1 2 }$ .DiffNodeset ${ \bf \mathrm { \Omega } } = { \mathrm { D N } _ { \mathrm { { 1 } } } } / { \mathrm { D N } _ { \mathrm { { 2 } } } }$   
4 Calculate $\mathrm { s u p ( D N _ { 1 2 } ) }$ ）by property(4)  
5 If sup $\mathrm { ( D N } _ { 1 2 }$ )≥min_sup do  
DN_k_1.add $\mathrm { \mathrm { D N } } _ { 1 2 } , \mathrm { D N } _ { 1 2 }$ DiffNodeset)  
6 End if  
7 End for  
F_item $$ F_itemUDN_k_1  
8 If DN_k_1 not null do  
9Mining_Fre_Items(DN_k_1,min_sup)//递归调用频繁项  
10 End if  
11 Output（F_item）

# 2.4PFIMD 算法步骤

PFIMD算法的具体实现步骤如下所示。a）通过Hadoop默认的文件块策略，将原始数据集划分成大小相同的文件块Block;b)对于每一个文件块调用频繁1项集F-list的生成过程，获得全局频繁1项集，并将结果存入分布式缓存系统HDFS中;c）调用均匀分组策略LBSBDG 将F-list 中的每一项进行分组，生成分组结果G-list;d）启动新的MapReduce任务，在Map阶段调用算法2将原始数据集分别映射到各个计算节点上，并在Reduce阶段调用算法4迭代挖掘全局频繁项集F_item。

# 2.5算法分析

PFIMD算法主要包括三个阶段：挖掘频繁1项集、频繁1项集均匀分组和并行挖掘频繁项集，因此该算法的时间复杂度主要有三部分组成。在挖掘频繁1项集阶段的Map阶段需要遍历事务数据集每一条记录中的每一项，假设每个Mapper节点上的记录数目为 $\mathrm { T _ { \mathrm { { D } } } }$ ，记录的平均长度为L，则其时间复杂度为 $O ( \mathrm { T _ { D } * L } )$ ；在Reduce 阶段需要将每个计算节点上的key值相同的键值对进行合并，假设每个Reducer节点中项的平均个数为 $\mathrm { T _ { i t e m } }$ ，Mapper节点个数为M，则其时间复杂度为 $O ( \mathrm { T _ { i t e m } * M } )$ ，因此获取频繁1项集的总时间复杂度为$O ( \mathrm { T _ { D } * L + T _ { i t e m } * M } )$ 。在频繁1项集均匀分组阶段主要是采用LBSBDG 将中的每一项进行分组，假设其F-list长度为，分组数为G，则其时间复杂度为 $O ( l / G )$ ，即为 $O ( l )$ 。在并行挖掘频繁项集过程中只需将当前频繁项集和频繁项集的DiffNodeset结构保存在内存中，极大的降低了内存的开销。同时该过程的时间复杂度主要取决于将频繁1项集的N-list结构合并生成2项集的DiffNodeset结构，假设频繁1项集F-list $\mathbf { \epsilon } = \{ I _ { 1 } , I _ { 2 } , . . . , I _ { l } \}$ ，项I所对应的N-list长度为L，采用搜索策略T-wcs生成2项集DiffNodeset时间复杂度为 $O ( \sum \sum ( \mathrm { L } _ { \mathrm { a } } + \mathrm { L } _ { \mathrm { b } } ) )$ ，其中a，b的取值范围为 $( 1 , \iota )$ ，因此对于PFIMD算法来说其时间复杂度为 $O ( \mathrm { T _ { D } * L + T _ { \mathrm { i t e m } } * M + \it l + \sum \sum ( L _ { a } + L _ { b } ) ) }$ 。在MRPrePost 算法中前两个阶段的时间复杂度基本相同，而在合并两个频繁1项集N-list过程中需要逐一比较两个N-list结构之间的每个元素其时间复杂度为 $O ( \sum \sum ( \mathrm { L } _ { \mathrm { a } } * \mathrm { L } _ { \mathrm { b } } ) )$ 。因此可知PFIMD算法的时

间复杂度更小。

# 3 实验结果及比较

# 3.1实验环境

为了验证PFIMD 算法的挖掘性能，本文设计了相关实验。实验环境包含4节点，其中1个Master节点，3个Slaver节点。所有节点的CPU为AMDRyzen7，每个CPU都拥有8 个处理单元，其内存均为16G，且四个节点处于同一个局域网，并通过 $2 0 0 \mathrm { M b / s }$ 以太网相连。在软件方面每个节点安装的Hadoop 版本为2.7.4，java版本为JDK1.8.0，操作系统均为Ubuntu16.04。各个节点的具体配置情况如表1所

Tab.1The foundation configuration of each node in   
  

<html><body><table><tr><td colspan="4">theexperimentalenvironment</td></tr><tr><td>节点类型</td><td>主机名</td><td>IP地址</td><td>角色</td></tr><tr><td>master</td><td>master</td><td>192.168.1.109</td><td>master/JobTracker/NameNode</td></tr><tr><td>slaver</td><td>slaver_1</td><td>192.168.1.110</td><td>slaver/TaskTracker/DateNode</td></tr><tr><td>slaver</td><td>slaver_2</td><td>192.168.1.111</td><td>slaver/TaskTracker/DateNode</td></tr><tr><td>slaver</td><td>Slaver_3</td><td>192.168.1.112</td><td>Slaver/TaskTracker/DateNode</td></tr></table></body></html>

# 3.2实验数据

PFIMD算法所使用的实验数据为三个真实的数据集，分别为Susy、webdocs 和kosarak。Susy[23]是一个记录使用粒子加速器探测粒子的数据集，该数据集包含5000000条实例，共有190项，具有数据量多，记录长度均匀，项数少等特点；webdocs 数据集是由意大利科学家ClaudioLucchese等人通过网络爬虫抓取的Web文档数据,该数据集包含1692082条数据，共有5267656个项，具有数据量多，记录长度长，项数多等特点[24]；kosarak 数据集[23]记录了匈牙利一家大型新闻网站点击流数据，该数据集包含990002条数据，共有41270项，具有数据量少，项数较多，数据离散等特点。数据集的具体信息如表2所示。

表1实验环境中各节点的基本配置  
表2实验数据集  
Tab.2Datasets used in the experimental   

<html><body><table><tr><td></td><td>Susy</td><td>webdocs</td><td>kosarak</td></tr><tr><td>记录数(条)</td><td>5000000</td><td>1692082</td><td>990002</td></tr><tr><td>项数(个)</td><td>190</td><td>5267656</td><td>41270</td></tr><tr><td>大小(MB)</td><td>321</td><td>1481.9</td><td>32.1</td></tr></table></body></html>

# 3.3PFIMD算法的性能分析

为验证PFIMD 算法在大数据环境下挖掘频繁项集的可行性，本文选取最小支持度阈值为1000，10000，20000和100000,分别将PFIMD 算法应用于Susy、webdocs和kosarak三个数据集中独立运行10次，取10次结果的均值，通过对算法运行时间和内存使用量的比较，从而实现对PFIMD 算法性能的综合评估。图1为PFIMD算法在3个数据集的执行结果。从图1中可以看出当支持度从1000变化到10000时，该算法在三种数据集的运行时间和内存使用量都有较大的下降。这是因为随着支持度的增大，频繁1项集F-list 的规模急剧下降，采用“LBSBDG”策略分配到每个计算节点上的项也有所减少，同时也降低了每个计算节点中子PPC-Tree树的规模，极大的减少了产生N-list结构所需的时间。此外，使用“T-wcs”搜索策略生成2项集的DiffNodeset时的时间复杂度是线性的，且在挖掘频繁项集时只需要将以当前项为前缀的频繁项集保存在内存中，极大的降低了内存占用量。然而随着支持度持续增加，算法的运行时间和内存使用量减小的趋势越来越缓慢，这是因为MapReduce计算模型工作调度以及在中间结果的I/O上占用了大部分时间从而影响了算法的性能。

3000 webdoecs Sebdocs600-  
2500 kosarak kosarak  
1500 300 1.1.  
1000- 200  
500 ■ 100010 20 100Min_Sup（103） Min_Sup(10³）(a)算法的运行时间 (b)算法的内存使用量

# 3.4PFIMD 算法性能比较

# 3.4.1PFIMD算法时间复杂度比较

为验证PFIMD 算法的挖掘效果，本文将PFIMD 算法分别与PFP-GroWth 算法[11],LBPFP 算法[14],MREclat 算法[17],SPEclat算法[18]和MRPrePost算法[19]进行了对比。在执行上述并行算法时需要根据每个数据集的F-list规模设置分组数目，表3给出三种数据集在不同支持数下F-list数目的具体情况。根据F-list大小对于Susy数据集设置分组数为50组，kosarak数据集设置分组数为100组，webdocs数据集设置分组数为1000组，分别在上述三个数据集上运行六种并行算法，实验结果如图2所示。

表3不同支持度下各数据集的F-list规模  
[ab.3F-list size of each dataset under different support degree:

![](images/eb7b34d46d6dcd755fc17a425f468dd7847a5bcb9439d5000095bfe678d7eb11.jpg)  
图1PFIMD 算法的性能分析Fig.1The performance of PFIMD  
c）六种算法在 Susy上的执行时间  
图2不同算法在不同数据集上的运行时间比较  
Fig.2Comparison of time complexity of different algorithms

从图2中可以看出，相较于其他算法，PFIMD算法在各个数据集上的运行时间均有降低，其中在 kosarak 降低的最多,PFIMD算法比SPEclat，MREclat，PFP-Growth和LBPFP算法的执行时间分别降低了 $6 6 . 0 \%$ = $7 9 . 5 \%$ ， $6 2 . 1 \%$ 和 $5 2 . 1 \%$ 在webdocs数据集上降低的最少，但也分别降低了$3 1 . 5 \% , 3 7 . 6 \% , 1 7 . 3 \%$ 和 $1 7 . 0 6 \%$ 。这是由于在并行挖掘频繁项集过程中PFIMD算法将对树的遍历转换为对DiffNodeset数据结构的合并任务，极大的降低了算法的运行时间。相反，在挖掘频繁项集时，SPEclat 算法和MREclat 算法需要先将水平数据集转为垂直数据集，然后采用类Apriori算法通过多次迭代来完成频繁项集的挖掘，同样对于LBPFP算法和PFP-Growth算法需要递归的构建频繁项集的条件模式树，这两者都需要消耗大量的时间。此外，可以发现PFIMD算法比最优的MRPrePost算法的挖掘效果都好，尤其在Susy数据集上，PFIMD算法的执行时间比MRPrePost算法降低了 $2 1 . 8 \%$ 。主要因为PFIMD算法采用双向搜索策略“T-wcs”使得生成2项集的DiffNodeset时间复杂度是线性的，并且PFIMD算法在并行挖掘频繁项集时采用动态分组策略“LBSBDG”，均匀的将频繁1项集分配到各个计算节点中，在确保集群负载均衡的同时也减小了集群中各节点中子PPC-Tree 树的规模，因此减少了先序后序遍历子PPC-Tree树所需要的时间，进一步降低了PFIMD算法的运行时间。

# 3.4.2PFIMD算法空间复杂度比较

由于PFP-Growth算法、LBPFP算法、MRPrePost算法和PFIMD算法都对原始数据集进行了无损压缩，因此本文除了考察并行算法的运行时间外，还统计了支持度为10000,20000和100000下每种算法在集群中各个节点消耗的平均内存大小，如图3所示。

![](images/dc38b5434a22e49f235de27465f8b04809563488e393145586560c27158f3bcc.jpg)  
  
图3不同算法在不同数据集上的内存使用量比较Fig.3Comparison of space complexity of different algorithms

从图3可以看出，在三个数据集上MRPrePost算法和PFIMD算法所消耗的内存大小明显小于LBPFP算法和PFP-Growth算法，这是由于MRPrePost算法和PFIMD算法在挖掘频繁项集时只需要根据PPC-Tree 树生成频繁1项集的N-list 结构，之后将PPC-Tree树从内存中删除，节省了大量的内存空间，而对于LBPFP算法和PFP-Growth算法在挖掘频繁项集时需要递归构造条件模式子树，所有的条件模式子树都需要保留在内存中。同时相较于MRPrePost算法，PFIMD算法在对三个数据集挖掘频繁项集时所使用的内存空间更少，尤其在Susy 数据集上，其内存使用量比MRPrePost 算法减少了 $2 2 . 7 \%$ 。一方面是因为PFIMD 算法使用双向搜索策略“T-wcs”，每组在挖掘时只需要将以当前项为前缀的频繁项集保存在内存中，极大的降低了内存占用量，而且采用动态分组策略“LBSBDG”，均匀的将频繁1项集分配到各个计算节点中减小了各节点中子PPC-Tree树的规模；另一方面由于PFIMD算法采用DiffNodeset结构避免了在数据集上N-list 基数较大的问题，如表4所示，本文对Susy、webdocs、kosarak三个数据集的频繁项集的DiffNodeset结构和N-list结构基数进行了统计，从表中可以看出在各个数据集上频繁项集的DiffNodeset结构比N-list结构的规模小，尤其对于密集型数据集Susy来说DiffNodeset结构的优势更明显。

表4DiffNodeset 结构与N-list 结构对比

Tab.4The comparison ofDiffNodeset and N-list   

<html><body><table><tr><td>dataset</td><td>Min_Sup</td><td>Avg.DiffNodeset</td><td>Avg.N-list</td><td>reduction ration</td></tr><tr><td>Susy</td><td>15%</td><td>74</td><td>972</td><td>13.1</td></tr><tr><td>webdocs</td><td>1%</td><td>3604</td><td>5793</td><td>1.6</td></tr><tr><td>kosarak</td><td>0.2%</td><td>282</td><td>2091</td><td>7.4</td></tr></table></body></html>

# 4 结束语

为解决传统频繁项集挖掘算法在大数据环境下的不足，本文提出了一种新的并行频繁项集挖掘算法PFIMD。该算法首先采用DiffNodeset数据结构，有效避免了PrePost算法中N-list基数过大的问题；其次，提出一种双向搜索策略"T-wcs”以加快2项集的DiffNodeset生成任务，降低算法的时间复杂度；最后，结合Hadoop云计算平台和MapReduce 编程模型对改进后的ProPost 算法各步骤进行并行化处理，并且提出了一种基于动态分组的负载均衡策略“LBSBDG”，解决了集群各节点负载不均衡的问题。与其他并行频繁项集挖掘算法相比，该算法充分结合了水平型算法和垂直型算法的优点，利用其独特优势来实现频繁项集的挖掘。同时为了验证PFIMD算法的挖掘性能，本文在Susy、webdocs、kosarak 三个数据集上对PFIMD、MRPrePost、PFP-Growth、MREclat、LBPFP和SPEclat六种算法进行对比分析，实验结果表明相比于其他几种算法，PFIMD 算法在运行时间和内存使用量上都具有明显的优势。

# 参考文献：

[1]米云龙，米春桥，刘文奇．海量数据挖掘过程相关技术研究发展[J]. 计算机科学与研究,2015,9(6):641-659.(Mi Yunlong,Mi Chunqiao, Liu Wenqi.Research advance on related technology of massive data mining process [J].Journal of Frontier s of Computer Science and Technology,2015,9 (6): 641-659.)   
[2]肖文，胡娟，周晓峰．基于MapReduce 计算模型的并行关联规则挖 掘算法研究综述[J].计算机应用研究，2018,35(1):13-23.(Xiao Wen，Hu Juan,Zhou Xiaofeng.Parallel association rules mining algorithm based on MapReduce:a survey [J].Application Research of Computers,2018,35(1):13-23.)   
[3]Agrawal R, Srikant R.Fast algorithm for mining association rules [J].

Proc 20th Int Conf Very Large Data Bases(VLDB),1994.23 (3): 21-30. [4]Han Jiawei,Pei Jian,Yin Yiwen.Mining frequent patterns without candidate generation: A frequent-pattern tree approach [J].Data Mining &Knowledge-Based Systems,2004,8(1):53-87.

[5] Zaki M,Parthasarathy S,Ogihara M.New algorithms for fast discovery of association rules [Cl/ Proc of the 3rd International Conference on Knowledge Discovery and Data Mining,1999: 283-286.   
[6] 黄山，王波涛，王国仁等.MapReduce 优化技术综述[J].计算机科 学与探索,2013,7(10): 865-885.(Huang Shan,Wang Baotao,Wang Guoren,et al. A survey on MapReduce optimization technologies [J]. Journal ofFrontiers of Computer Science and Technology,2013,7 (10): 865-885.)   
[7]Afzali M, Singh N,Kumar S.Hadoop-MapReduce: a platform for mining large datasets [C]// International Conference on Computing for Sustainable Global Development. Piscataway, NJ: IEEE Pres,2016.   
[8]黄立勤，柳燕煌．基于 MapReduce 并行的 Apriori 算法改进研究[J]. 福州大学学报：自然科学版,2011,39(5):69-74.(Huang Liqin,Liu Yanhuang.Research on improved parallel Apriori with MapReduce [J]. Journal of Fuzhou University: Natural Science Edition,2011,39 (5): 69- 74.)   
[9]Zhou Xiaohao, Huang Yongfeng. An improved parallel association rules algorithm based on MapReduce framework for big data [C]//Proc of the 10th International Conference on Natural Computation,2014: 284-288.   
[10]秦军，郝天曙，董倩倩．基于MapReduce 的Apriori算法并行化改进 [J]．计算机技术与发展,2017,27(4):64-68.(Qin Jun,Hao Tianshu, Dong Qianqian.Parallel improvement of Apriori algorithm based on MapReduce [J]. COMPUTER TECHNOLOGY AND DEVELOPMENT, 2017,27 (4): 64-68.)   
[11] Li Haoyuan, Wang Yi, Zhang Dong.PFP: parallel FP-growth for query recommendation [C]// Proc of ACM Conference on Recommender systems.New York:ACMPress,2008:107-114.   
[12] 杨勇，王伟．一种基于 MapReduce 的并行FP-growth 算法[J]．重庆 邮电大学学报：自然科学版,2013,25(5):651-657,670.(Yang Yong, Wang Wei. A paralel FP-growth algorithm based on MapReduce [J]. Journal of Chongqing University of Posts and Telecommunications (Natural Science Edition),2013,25(5): 651-657,670.)   
[13] 陈兴蜀，张帅，董浩等．基于布尔矩阵和 MapReduce 的 FP-Growth 算法[J].华南理工大学学报：自然科学版,2014,42(1):135-141. (Chen Xingshu,Zhang Shuai,Dong Hao,et al.FP-Growth algorithm based on Boolean matrix and MapReduce [J].Journal of South China Universityof Technology (Natural Science Edition),2014,42(1): 135- 141.）   
[14]高权，万晓东．基于负载均衡的并行 FP-Growth 算法[J].计算机工 程,2019,45 (3):32-35,40.(Gao Quan,Wan Xiaodong.Parallel FPGrowth algorithm based on load balance [J]. Computer Engineering, 2019,45 (3): 32-35,40.)   
[15] Moens S,Aksehirli E, Goethals B.Frequent itemset mining for big data [C]//Proc of International Conference on Advanced Cloud and Big data, 2013: 111-118.   
[16] 章志刚，吉根林，唐梦梦．并行挖掘频繁项目集新算法-MREclat[J]. 计算机应用,2014,34(8):2175-2178.(Zhang Zhigang,Ji Genlin,Tang Mengmeng. MREclat: new algorithm for paralel mining frequent itemsets [J].Journal of Computer Applications,2014,34 (8): 2175-2178.)   
[17]张春，汲磊举．基于 MapReduce 的 Eclat 改进算法研究与应用[J]. 北京交通大学学报,2016,40 (3):1-6.(Zhang Chun,JiLeiju.Research and application of Eclat improved algorithm based on MapReduce [J]. JOURNAL OF BEIJING JIAOTONG UNIVERSITY,2016,40 (3): 1-6.)   
[18]冯兴杰，潘轩．基于 Spark 的并行 Eclat 算法[J].计算机应用研究, 2019,36(1):18-21.(Feng Xingjie,Pan Xuan.Eclat algorithm based on Spark[J].Application Research of Computers,2019,36(1):18-21.)   
[19]Liao Jinggui,Zhao Yuelong，Long Saiqin．MRPrePost:a parallel algorithmadapted forminingbigdata[C]//Proc ofIEEEWorkshop on Electronics,Computer and Applications,2014: 564-568.   
[20] Deng Zhihong,Wang Zhonghui, Jiang Jiajian.A new algorithm for fast mining frequent itemsets using N-list [J].Science China Information Sciences,2012,55 (9):2008-2030.   
[21] Deng Zhihong. DiffNodesets: An efficient structure for fast mining frequent itemset [J].Applied Soft Computing,2016,41: 214-223.   
[22]尹远，张昌，文凯等．基于DiffNodeset结构的最大频繁项集挖掘算 法[J]．计算机应用，2018,38（12):3438-3443.(Yin Yuan,Zhang Chang,Wen Kai,et al.Maximal frequent itemset mining algorithm based on DiffNodeset structure [J].Journal of Computer Applications,2018,38 (12):3438-3443.)   
[23] http://www.philippe-fournier-viger.com/spmf/index.php?link=datasets. php   
[24]程阳，章韵．基于MapReduce-HBase 的 Apriori 算法的改进与研究 [J]．南京邮电大学学报：自然科学版,2018,38(5):95-103.(Cheng Yang,Zhang Yun.Improvement and research on Apriori algorithm based on MapReduce-HBase [J]. Journal of Nanjing University of Posts and Telecommunications (Natural Science Edition),2018,38 (5):95-103.)