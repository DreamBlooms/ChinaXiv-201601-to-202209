# 大数据下的分布式精确模糊KNN分类算法‘

邹劲松1，李芳²

(1．重庆水利电力职业技术学院 电子信息工程系，重庆 402160;2.重庆大学 计算机学院，重庆 400044)

摘要：针对K-近邻(KNN)方法处理大数据集的效率问题进行了研究，提出了一种基于 Spark框架的分布式精确模糊KNN分类算法。该方法创新性地将 Spark框架分布式map和reduce过程与模糊KNN结合，首先对不同分区中训练样本类别信息进行模糊化处理，得到类别隶属度，将训练集转换为添加类隶属度的模糊训练集；然后使用 KNN 算法对先前计算的类成员测试集计算得到k个最近邻；最后通过距离权重进行分类。针对百万级大数据集样本的实验，以及与其他算法的对比实验表明，所提算法是可行的和有效的。

关键词：大数据；分布式Spark框架；类隶属度；精确模糊KNN算法中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.04.0373

# Accurate distributed fuzzy KNN classification algorithm for big data

Zou Jinsong1,Li Fang ² (1.Dept.ofElectronics &InformationEngineering,Chongqing CollgeofWaterResources &ElectricEngineering,Chongqing 402160, China; 2. School of Computer Science, Chongqing University, Chongqing 400044, China)

Abstract: Ithas aresearch on the eficiencyof processing large data sets with K Nearest Neighbormethod,and thena distributed exact fuzzy KNNclasification algorithm basedon the Spark framework was proposed.The method inovatively combines the Spark framework distributed map andreduce processes withthe fuzzy KNN.Firstly,the trainingsamplecategory informationindiffrentpartitions is procesed toobtaintheclassmembershipdegeeThe trainingsetisconvertedintoafuzzy training set withadding membershipdegrees,andthen the KNNalgorithm isusedtocalculate the K nearest neighborof the previouslycalculated classmember testset.Finally,itisclasifiedbydistance weight.Experimentsonmega-scale dataset samples and comparison experiments with other algorithms show that this method is feasible and effective. Key words: big data; distributed Spark framework; class membership degree; exact fuzzy KNN algorithm

# 0 引言

K-近邻方法（KNN）是一种有效的分类算法[I]，其分类规则基于对未知样本采集训练集中 $k$ 个最相似的样本，它的相似性通常是一个距离度量，如欧几里德距离或曼哈顿距离。尽管其简单性，KNN算法以其性能上的优势成为数据挖掘的十大算法之一[2,3]。

KNN算法在分类的时候给每个邻居赋予同样的重要性，因此可能存在误判的情况，越来越多的人对于KNN算法的改进算法作出研究。Fuzzy-KNN通过模糊集来解决传统KNN的误判缺点，提高分类准确率[4,5]，已经在医药[6]、经济和其他许多领域得到应用。KNN算法在处理大数据集时存在运行时间和内存消耗两个主要问题[7]。而Fuzzy-KNN算法虽然在分类精度上高于KNN，不过由于该算法需要一个额外的阶段来计算类的隶属度，所以时长和内存消耗会更大一些。为了解决这个问题，可以用基于MapReduce和Spark框架的云技术来解决大数据问题。

目前对于KNN及改进KNN算法对大数据处理的研究逐渐增多。文献[8]提出的方法是由两个阶段组成的近似KNN算法。首先，将数据分区以将整个数据集分成不同的分区；其次，计算每个分区中的KNN，从而得到不同的原始KNN结果。文献[9]提出了快速KNN的大数据分类算法，该算法首先用聚类方法对样本进行分块，在测试过程找出距离待测样本最近的块；然后用使用KNN对该块（作为新的训练样本）进行分类。文献[10]提出了一种可以对大数据集进行分类的精确KNN方法，该方法在 map 阶段分割训练集并计算每个测试样本的KNN;reduce阶段收集所有候选者作为最近邻居，并报告最后k个最近邻居。因此，该算法能够处理运行时间较长的大训练和测试集，并获得与传统KNN算法一样的准确度。在文献[11]中作者通过简单的分割数据并在每个分割中应用Fuzzy-KNN，然后收集每个分组的所有标签，并通过多数投票计算最终结果。其缺点是当训练集和测试集很大时，改算法需要太多的分割，并且在最后阶段产生大量的投票计算。

随着云计算的发展，对于大数据分类的研究成为热点，已经有文献对大数据作出研究。文献[12]文献提出基于Storm 的流数据KNN分类算法，能够满足大数据背景下对流数据分类的高吞吐量、实时性和准确性的要求。文献[13]提出一种基于语言模糊规则的大数据分类系统，使用MapReduce 框架来学习和融合规则库，能够有效实现大数据分类。文献[14]提出了一种新的大数据模糊规则分类系统，解决了随着并行度的增加，分类性能显着降低的问题。文献[15]提出了一种针对大数据的多层差分KNN算法，避免了传统改进算法中剪辑样本带来的判别误差，又大大降低了无效计算量。文献[16]提出了一种MapReduce和分布式缓存的KNN并行方法，提高了算法效率。

在研究了以上大数据分类方法的基础上，针对上述方法的不足，本文提出了一种在Spark上实现的基于精确模糊KNN 算法(EF-KNN)。该算法利用Spark的内存原语通过分割数据来管理大型训练集；另外，该算法还可以通过遍历这个集合的块来处理巨大的测试集。第一阶段计算类隶属度，map 阶段分配训练集并计算每个分配的KNN，reduce阶段收集所有的候选者成为最近邻并获得最终 $k$ 个最近样本，然后计算类成员并用这个信息报告一个新的训练集，加快了运行速度。第二阶段中的 map阶段计算分配的测试样本和训练集之间的距离，每个映射得到$k$ 个候选并做标记。多个reduce 阶段，通过统计map 阶段的标记信息，计算最终 $k$ 个邻居，然后根据先前计算的类隶属度进行分类。

# 1 模糊KNN算法

模糊KNN算法是对标准KNN算法的改进，其在精度方面非常具有较好性能。该方法与传统KNN的不同之处是：模糊化未知样本和 $k$ 个最近邻的距离，然后每个类别设置隶属度。该方法用训练集来预先计算类成员，之后计算测试集中每个样本的KNN。Fuzzy-KNN算法的正式表示法如下：

设 $\scriptstyle { \begin{array} { l } { \scriptstyle { T R } } \end{array} }$ 为训练数据集， $T S$ 为测试集，分别由确定的样本数$n$ 和样本 $\mathbf { \Phi } _ { t }$ 组成，每个样本 $X _ { i }$ 是一个向量 $\left( { { x } _ { i 1 } } , { { x } _ { i 2 } } , . . . , { { x } _ { i j } } \right)$ ，其中$x _ { i j }$ 是第 $i$ 个样本的第 $j$ 个特征值。 $T R$ 的每个样本都属于一个已知的类别 $w$ ，而对于 $T S$ 来说它是未知的。模糊KNN有两个不同的阶段，第一个阶段是计算 $\scriptstyle { \mathcal { T } } R$ 本身的 $k _ { m e m b }$ 最近邻居，通过计算 $X _ { t r a i n }$ 和 $T R$ 的所有样本之间的距离来搜索 $k _ { m e m b }$ 个最接近的样本，当得到最近邻居，就会创建如式（1）所示的类隶属度，因此训练数据集 $\ l _ { T R }$ 具有一个具有类隶属度向量而不是原来的类标签。

$$
u _ { j } \left( x \right) = \left\{ \begin{array} { l l } { 0 . 5 1 + \left( n _ { j } / k _ { m e m b } \right) \cdot 0 . 4 9 i f j = i } & { } \\ { \left( n _ { j } / k _ { m e m b } \right) \cdot 0 . 4 9 } & { i f j \neq i } \end{array} \right.
$$

第二阶段计算与第一阶段类似的 $k$ 个最近邻居，不同之处

是计算 $_ { T S }$ 的每个样本在 $\scriptstyle { \mathcal { T } } R$ 中 $k$ 个最近邻居，最终按式(2)进行计算。

$$
u _ { i } \left( x \right) = \frac { \sum _ { j = 1 } ^ { K } u _ { i j } \Biggl ( 1 \mathord { \left/ { \vphantom { \sum _ { j = 1 } ^ { K } u _ { j } } } \right. \kern - delimiterspace } x - x _ { j } \Biggl \lvert ^ { \frac { 2 } { m - 1 } } \Biggr ) }  { \sum _ { j = 1 } ^ { K } \Biggl ( 1 \mathord { \left/ { \vphantom { \sum _ { j = 1 } ^ { K } u _ { j } } } \right. \kern - delimiterspace } x - x _ { j } \Biggl \lvert ^ { \frac { 2 } { m - 1 } } \Biggr ) } 
$$

其中： $\mathbf { \Sigma } _ { m }$ 为模糊权重调节因子，如果$u _ { i } ( x ) \mathrm { { = } } \mathrm { { m a x } } \{ u _ { z } ( x ) \} , z \mathrm { { = } } 1 , 2 , . . . , w$ 且 $w \not = i$ 时，则可以得出样本 $x$ 属于第 $i$ 类。

# 2 大数据的精确模糊 KNN(EF-KNN)算法

Spark 是MapReduce一个新的实现，解决了Hadoop 的一些缺点，最重要的特征是数据的类型结构以透明的方式并行计算，它被称为弹性分布式数据集（RDDs)；另外，RDD允许持久化和重用数据。此外，其开发与Hadoop 合作，特别是与其分布式文件系统（hadoop distributed file system,HDFS）。

本文在Spark 框架基础上提出了一种基于Spark 框架大数据环境的分布式精确模糊KNN分类算法。该算法分为两个阶段，第一阶段计算隶属度，第二阶段进行分类。

# 2.1计算类隶属度

这个过程是计算训练集类成员隶属度的MapReduce过程。图1给出了EF-KNN的流程。

TR' TR'1 TR'2 TR'v Fuzzy Training 1st iter 2nd iter Vth iter Set (FTR) Wit iteratples ↓ 化t·f。 Key Value Key 1 1 2 <ClassM - Dist> k <ClassM - Dist> k <ClassM-Dist>t Split 1 T/V · <ClassM - Dist> · k : 1 <ClassM-Dist>rmst · TR1 Key Value Split 2 Key 2   
TrainingSet TR2 2 1 <ClassM - Dist> - k <ClassM - Dist> - k <ClassM-Dist> ··· (TR) · W <ClassM - Dist> - k <ClassM-Dist>kr   
With N samples TRM ·.. ··.   
ftft..f Split M Ky clasmx-Dist-k KeyT/V 2 <ClassM − Dist> · k <ClassM-Dist>koit · · W <ClassM – Dist> · k <ClassM-Dist>krpt map reduce

由图中可知，计算过程分为 map 和 reduce 部分两部分。Map 阶段划分训练数据集 $T R$ 并计算每个分割的距离，并为每个训练样本取 $\mathbf { k }$ 个最近邻的类别；reduce 阶段将所有候选者加入到k个最近邻中，并获得k个最接近的定义样本，形成一个新的添加具有类隶属度向量的训练集，被称为模糊训练集（fuzzy training set,FTS）。

1）Map 过程从HDFS 读取的训练集TR作为RDD对象开始，TR 被分成 $\mathbf { m }$ 个分区，作为用户定义的参数，因此，对于每个分区 $T R _ { j } , 1 \le j \le m$ 具有一个map任务(map,,map,,mapm)，每个 map 包含大约相同数量的训练样本。

为了获得一个精确的类隶属度方法，需要对每个训练样本中的所有训练样本进行比较，以将每个训练样本与整个训练集进行比较。假设 $T R _ { j }$ 和 $T R$ 在内存中一起使用；否则，TR 将被分区成 $\nu$ 块，并以顺序的方式迭代，以允许存储在内存中并正确执行。算法1中包含了map 函数伪代码。

算法1隶属度计算中 map 函数输入： $T R _ { j } , T R _ { \nu } ,$ kmemb

1、 For $\scriptstyle t = 0$ tosize(TRv)do  
2、 计算 $\mathrm { K N N } ( T R _ { j } , T R _ { \nu } , k _ { m e m b } )  C l a s \& D i s t _ { t , j }$   
3、 （204 $( k e y \colon t , \nu a l u e \colon C l a s \& D i s t _ { t , j } ) \to r e s u l t _ { j }$

# 4、 end for

5、输出resultj

每个 map 过程建立一个 $T R _ { \nu }$ 中每一个训练样本的 $k _ { m e m b }$ 维 $\leq$ 类别,距离>的向量Class&Dist,j,步骤2计算类别及其与 kmemb最近样本的距离。为了加速还原器中最近邻居的最新实现，每个矢量Class& $D i s t _ { t , j }$ 按升序排序。每个map 任务都会建立一个Class&Dist矩阵，表示候选样本是最近邻居，通过步骤3中过程得到。通过该方案，可以使用多个reducers来处理大型训练集。

2）Reduce 过程 多个reducers从map 任务中输出得到的kmemb最近邻居，其目标是获得 $T R _ { \nu }$ 中包含的每个训练样本的最近邻居。要做到这一点，所有元素都key分组，并计算类的隶属度，具体过程见算法2。

算法2隶属度计算中reduce 伪代码 输入：resultkey,kmemb,contl $\scriptstyle = 0 .$ cont2 $\scriptstyle = 0$

While $i < k _ { m e m b }$ do

If $r e s u l t _ { k e y } ( c o n t 1 ) . D i s t \quad \le \qquad r e s u l t _ { r e d u c e r } ( c o n t 2 ) . D i s t$ then $r e s u l t _ { k e y } ( c o n t 1 ) . D i s t  o u t ( i ) , c o n t 1 + +$   
else if $e s u l t _ { k e y } ( c o n t 1 ) . D i s t = r e s u l t _ { r e d u c e r } ( c o n t 2 ) . D i s t$ then if   
$i < k _ { m e m b }$ then $\begin{array} { l r c l } { { i + + } } \\ { { r e s u l t { _ { k e y } ( c o n t 2 ) } } } & { {  } } & { { o u t ( i ) } } \\ { { } } & { { } } & { { } } \\ { { c o n t 2 + + } } \end{array}$ end if   
else （204 $\begin{array} { l l } { { r e s u l t _ { k e y } ( c o n t 2 ) ~  ~ o u t ( i ) } } \\ { { } } \\ { { c o n t 2 + + } } \end{array}$   
end if   
$i + +$

# end while

输出out

Reduce任务将通过合并map的输出来更新kmemb最近邻候选者选择，由于来自map的矢量根据距离排序，所以更新过程变得更快。这包括合并两个排序列表，确保尽可能地保留相同距离的邻居。这个函数一个一个地比较距离，如果距离小于当前的距离，则更新距离和类；如果距离更远，则被丢弃；如果距离完全相同，则保存两者。然后得到训练集中每个样本的$k _ { m e m b }$ 近邻，另一个map 阶段将计算类隶属度，计算方法见式(1)，并将表示每个类隶属度向量的单个标签更改。最后返回保存原始特征的每个原始样本，并更改用于计算的类成员的标签，即产生了一种新的模糊训练集，这是2.2节中分类部分的输入。

# 2.2分类过程

图2给出了分类阶段的流程，分为MapReduce的两个基本操作。

Output Test Set (TS) TS1 TS2 TSu 1st iter 2nd iter Uth iter Majority voting with With T samples ↓ max class membership and U iterations Key Value Key 1 12 <CasM − ist>-.k <ClassDist . · · Split 1 元 <Class - istsk <ClssMDist>t FTR1 Split 2 Key classm-Dist-k Key2 Fuzzy Training FTR2 2 <ClassM – Dist> · k <ClassM-Dist>1 ,• \* Set (FTR) ·· r <ClassM − Dist>krt <ClassM - Dist> · k 1 With N samples FTRM ： ··. tft|f Split M ， sCM-D clss-Disb.k T/u .·· <ClassM – Dist> - k · <ClassM−Dist>ks map reduce

Map 过程需要训练数据集TR，测试集TS和参数 $k$ 作相应分区，并计算每个TR分区的K近邻和TS类的每一个样本的距离；reduce阶段收集每个分区的所有 $\mathbf { k }$ 个最近邻，并计算 $\mathbf { k }$ 个最接近的样本，最后通过多数投票报告每个样本的分类标签，分类阶段的重点是获得从模糊训练集FTR开始的确切结果。

1)Map 过程FTR分成 $\mathrm { ~ m ~ }$ 个部分，其中包含大约相同数量的样本，测试集TS必须未分区，以便通过分布式map 操作来计算所有候选者为FTR的每个分区中 $\mathbf { k }$ 个最近邻。如果FTR的分区数保持为TR的分区，则避免了shuffle阶段，因此在运行时效率会提高。

算法3显示了map函数的伪代码。对于TS的每个样本计算它的 $k$ 个最近邻。变量neigh-memb保存距离和类隶属度矢量，最后将每个测试样本的id添加为key，并将其发送到reduce阶段。

算法3分类过程中map 伪代码输入： $T R _ { j } ,$ TS, $k$

1、for $\scriptstyle t = 0$ to size(TS) do   
2、计算 $\mathrm { K N N } ( T R _ { j } , T S , k )  n e i g h – m e m b _ { t , j }$   
3、(key: t, value: neighborstj) $$ resultt

# 4、end for

5、输出resultt

2）Reduce过程其目的是汇总所有候选最近邻，以便最终获得整个模糊训练集FTR的 $k$ 个最近邻，保持距离和类隶属度向量。

算法4分类过程reduce 伪代码

参数设置： $a n d _ { k e y , 1 , ~ c a n d _ { k e y , 2 } , ~ k , ~ C 1 = 0 , ~ C 2 = 0 }$

# While $i < k$ do

（20 ${ \bf I f } c a n d { k e y , 1 } ( C 1 ) . D i s t \le c a n d { k e y , 2 } ( C 2 ) . D i s t \mathrm { \bf t h e n }$ $c a n d _ { k e y , 1 } ( C 1 )  r e s u l t ( i )$ （204号 $\mathbf { f \ } c a n d _ { k e y , 1 } ( C 1 ) . D i s t = c a n d _ { k e y , 2 } ( C 2 ) . D i s t$

# then

$$
i + +
$$

$$
\begin{array} { l } { { c a n d _ { k e y , 2 } ( C 2 ) ~  ~ r e s u l t ( i ) } } \\ { { } } \\ { { C 2 + + } } \end{array}
$$

# end if

# end if

$$
C 1 + +
$$

$$
\begin{array} { l } { { c a n d _ { k e y , 2 } ( C 2 ) ~  ~ r e s u l t ( i ) } } \\ { { } } \\ { { C 2 + + } } \end{array}
$$

# end if

$$
i + +
$$

# endwhile

考虑到一些样本的距离可能是相同的，因此，当 $k$ 参数允许时将保留两个邻居。最后，利用得到的邻居，应用最后一个map 函数计算预测的类标签，式(2)应用于测试集的每一个样本分类。

# 3 实验结果与分析

采用UCI机器学习库的三个大数据集(PokerHand、Susy、Higgs)来评估提出的模型。表1给出了样本描述。

表1数据集描述  

<html><body><table><tr><td>数据集</td><td>样本</td><td>属性数</td><td>类别</td></tr><tr><td>PokerHand</td><td>1 025 010</td><td>10</td><td>10</td></tr><tr><td>Susy</td><td>5 000 000</td><td>18</td><td>2</td></tr><tr><td>Higgs</td><td>11 000 000</td><td>28</td><td>2</td></tr></table></body></html>

模型中用到的参数 $k _ { m e m b }$ 选择3、5、7做邻居数量来计算类成员， $k$ 为未知样本的邻区数，另外并发式计算map任务数即为数据集TR分区数量。

所有执行都在由另一个主节点管理的16个计算节点组成的集群上运行.节点具有以下特点：2个IntelXeonCPUE5-2620处理器，每个处理器6个内核（12个线程)，2GHz和64GBRAM,每个任务都有2GB可用主内存，每个节点都使用 Spark1.6.2进行配置。

从运行时间和准确性方面分析了所提出的方法。表2给出了使用Poker数据集时，计算类成员阶段的时间（MembT）、分类阶段的时间（ClasT）和总运行时间（TotalT）以及分类准确度（Acc)。为了简化显示的结果， $k _ { m e m b }$ 和 $k$ 的值是相同的，并且等于3、5、7，map数设为256。

表2本文算法对Poker数据集实验结果  

<html><body><table><tr><td>Kmemb 和k</td><td>MembT</td><td>ClasT</td><td>TotalT</td><td>ACC</td></tr><tr><td>3</td><td>462.2232</td><td>130.7489</td><td>592.9721</td><td>72.57%</td></tr><tr><td>5</td><td>484.2841</td><td>145.6419</td><td>629.926</td><td>73.13%</td></tr><tr><td>7</td><td>499.0342</td><td>141.0916</td><td>640.1258</td><td>73.36%</td></tr></table></body></html>

由表2中数据可以得出，对于参数 $k _ { m e m b }$ 和 $k$ ，由于设计的

执行，尽管样本量增加以及reduce阶段的邻居计算量增加，但三种模型中的任何一种的总运行时间都不会增加太多，且 $k _ { m e m b }$ 和 $k$ 取值3、5、7时分类准确率相差较少。Susy 数据集在不同map数的实验结果如表3所示。

表3Susy 数据集在不同map 数的实验结果  

<html><body><table><tr><td rowspan="2">Kmemb 和 k</td><td colspan="3">Accuracy</td></tr><tr><td>128</td><td>256</td><td>384</td></tr><tr><td>3</td><td>83.38%</td><td>82.46%</td><td>82.84%</td></tr><tr><td>5</td><td>83.50%</td><td>82.92%</td><td>82.78%</td></tr><tr><td>7</td><td>83.19%</td><td>82.91%</td><td>82.38%</td></tr></table></body></html>

由表3中数据可知，大数据分类精度随着map 数的增加而降低，这是因为对于测试样本，有几个训练数据点的距离完全相同，当分布式执行时，最终邻居将依赖于从每个映射输出到达的顺序。

图3给出了总运行时间（以s为单位）与map任务数量之间的关系， $k _ { m e m b }$ 和 $k$ 的值相同且等于3。图4给出了本文算法在三个数据集分类获得的运行时间(以s为单位)，其中 $k _ { m e m b }$ 和 $k$ 的值相同且等于3和map 任务数量为384。

![](images/8d0441f24fb7f5752c08de2ae80c139fb1b88068415181ac4188824434aa8dfb.jpg)  
图3Map数量对总运行时间的影响

![](images/66f6cad0f1c4bdee87c39fbbbe6e2d55af5684688ee9bbee7f99875eaebe1367.jpg)  
图4不同数据集的运行时间

分析图3和4可知，本文所提出的模型可伸缩性是线性的，但是在运行时Higgs数据集的时间相当高，并揭示了该算法的弱点，运行时需要更多硬件条件。

为了验证本文方法的先进性，将本文算法与其他算法进行比较。实验中本文算法中kmemb和k的值均取为3，分类准确率对比结果见表4。

表4不同算法分类准确率性能比较 $1 \%$ （204号  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="4">方法</td></tr><tr><td>[11]</td><td>[13]</td><td>[17]</td><td>本文算法</td></tr><tr><td>PokerHand</td><td>75.12</td><td>71.96</td><td>77.99</td><td>89.25</td></tr><tr><td>Susy</td><td>69.06</td><td>60.31</td><td>63.14</td><td>83.38</td></tr></table></body></html>

<html><body><table><tr><td>Higgs</td><td>62.63</td><td>55.61</td><td>55.86</td><td>77.82</td></tr></table></body></html>

由表中数据可以得出，与其他大数据分类算法相比较，所提算法分类准确率性能优于其他算法，说明所提方法的先进性。

# 4 结束语

为解决大数据分类效率问题，提出一个可扩展的分布式基于 Spark 框架的精确模糊K-NN 算法。该算法在 Spark 框架上首先进行数据分区，计算类隶属度，得到模糊数据集，最后使用KNN实现大规模数据的分类。实验表明，本文方法在保证分类精度的前提下，可实现百万一千万数据规模的数据分类，且总运行时间不会增加太多。通过与其他算法的实验比较，说明所提方法的可行性与有效性。未来的工作将通过一个近似模型来加速模糊KNN模型，着重于减少计算类隶属度时间。

# 参考文献：

[1]马闯，吴涛，段梦雅．基于 K-近邻隶属度的聚类算法研究[J].计算机 工程与应用,2016,52(10):55-58.(Ma Chuang,Wu Tao,Duan Mengya. Clustering algorithm based on membership degree ofK-nearest neighbor [J]. Computer Engineering and Applications,2016,52 (10): 55-58.)   
[2] 郭曦，王盼，王建勇，等．基于K-近邻最弱前置条件的程序多路径验证 方法[J].计算机学报,2015,38(11):2203-2214.(Guo Xi,Wang Pan, Wang Jianyong,et al.Program multiple execution paths verification based on K-proximity weakest precondition [J]. Chinese Journal of Computers, 2015,38 (11): 2203-2214.)   
[3]Samanthula B K,Elmehdwi Y,Jiang W.K-nearest neighbor classfication over semantically secure encrypted relational data [J].IEEE Trans on Knowledge and Data Engineering,2015,27(5):1261-1273.   
[4]Kermani EF,Barani G A,Hessaroeyeh MG.Cavitation damage prediction on dam spillways using fuzzy-KNN modeling [J]. Journal of Applied Fluid Mechanics,2018,11(2):323-329.   
[5]Derrac J,Chiclana F,Garcia S,et al.Evolutionary fuzzy K-nearest neighbors algorithm using interval-valued fuzzy sets [J].Information Sciences,2016, 329: 144-163.   
[6]Chen HL,Huang C C,Yu XG,et al.An efficient diagnosis system for detection of Parkinson's disease using fuzzy K-nearest neighbor approach [J].Expert Systems with Applications,2013,40(1): 263-271.   
[7]Jivani AG,Shah K, Koul S,et al. The adept K-nearest neighbour algorithm: an optimization to the conventional K-nearest neighbour algorithm[J].Trans on Machine Learning and Artificial Intelligence,2016,4(1): 52-57.   
[8]Deng Z,Zhu X, Cheng D,et al. Efficient K NN classification algorithm for big data [J]. Neurocomputing,2016,195 (C): 143-148.   
[9]苏毅娟，邓振云，程德波，等．大数据下的快速 KNN 分类算法[J].计 算机应用研究,2016,33(4):1003-1006.(Su Yijuan,Deng Zhenyun,Cheng Debo,et al. Fast KNN classification algorithm under big data [J]. Application Research of Computers,2016,33 (4):1003-1006.)   
[10] Maillo J,Ramirez S,Triguero I,et al. KNN-IS:an iterative spark-based design of the K-nearest neighbors clasifier for big data [J]. KnowledgeBased Systems,2017,117: 1003-1006.   
[11] Hegazy O,Safwat S,El Bakry M.A mapreduce fuzzy techniques of big data classification [C]//Proc of SAI Computing Conference.London, UK: IEEE Press,2016: 118-128.   
[12]周志阳，冯百明，杨朋霖，等．基于 Storm 的流数据 KNN 分类算法的 研究与实现[J].计算机工程与应用,2017,53(19):71-75.(Zhou Zhiyang, Feng Baiming, Yang Penglin,et al. Research and Implementation of KNN classification algo-rithm for streaming data based on Storm [J]. Computer Engineering and Applications,2017,53 (19): 71-75.)   
[13] Rio S D,Lpez V,BenitezJM,et al.AMapReduce approach toaddresig data classification problems based on the fusion of linguistic fuzzy rules [J]. International Jourmal of Computational Intellgence Systems,2015,8 (3): 422-437.   
[14] Elkano M,Galar M,Sanz J,et al.A global distributed approach to the Chi et al.fuzzy rule-based classification system for big data classification problems [C]// Proc of IEEE International Conference on Fuzzy Systems. Naples, Italy: IEEE Press,2017: 1-6.   
[15]耿丽娟，李星毅．用于大数据分类的KNN算法研究[J].计算机应用研 究,2014,31 (5):1342-1344.(Geng Lijuan,Li Xingyi. Improvements of KNN algorithm for big data clasification [J]. Application Research of Computers,2014,31(5): 134-1344. )   
[16] 涂敬伟，皮建勇．基于MapReduce和分布式缓存的KNN分类算法研究 [J]．微型机与应用，2015,34(2):18-21.(Tu Jingwei,Pi Jianyong. Paralelized K-nearest neighbor algorithm based on MapReduce and distributedcache[J].icrocomputer&itsApplications,015,4():18 21.）   
[17]李正杰，黄刚．基于Hadoop 平台的 SVM_KNN 分类算法的研究[J]. 计算机技术与发展，2016,26(3):75-79.(Li Zhengjie,Huang Gang. Research on SVM KNN clasification algorithm based on hadoop platform [J]. Computer Technology and Development,2016,26 (3): 75-79.)