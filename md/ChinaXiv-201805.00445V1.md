# 一种B-树和Bloomfilter相结合的IPv6路由查找算法

姚明，赵晶晶，贺兴亚，杨云(扬州大学 信息工程学院，江苏 扬州 225005)

摘要：为了提高 IPv6的路由查找效率，针对 IPv6路由前缀分布不均匀的问题，提出了一种基于B-树和Bloom filter相结合的IPv6路由查找算法（BTBF)。BTBF分为B-树和 Bloom filter查找两部分，首先利用B-树查找路由前缀的前16bit值，然后通过B-树节点中位向量的映射，将下一步链接到 Bloomfilter，再利用 Bloomfilter位数组的值映射提取下一跳。实验结果表明，BTBF 算法与其他树形和Bloomfilter 类算法相比有效减少了空间和时间占用，在路由表项数变化较大的情况下也能维持稳定的查找性能。

关键词：路由查找算法；B-树；Bloomfilter；IPv6骨干路由表 中图分类号：TP393.03 doi:10.3969/j.issn.1001-3695.2018.03.0179

# Fast IPv6 routing lookup combining B-tree and Bloom filter

Yao Ming1, Zhao Jing Jing1, He Xing Ya1, Yang Yun1 (1. Information Engineering College of YangZhou University,Yangzhou 225002,China)

Abstract: Inorderto improve the eficiencyofIPv6 routing lookup,this paper put forwardanIPv6routing lookupalgorithm (BTBF)basedon thecombinationofB-Tree and Bloomfilterforthe uneven distributionofIPv6 routing prefix.BTBFincludes two parts,namely,B-Treeand BloomFilterlookup:firstly,this paperlookedupthefirst16bit valueofrouting prefix withBtreeand linkedthenextsteptoBloomfilterthroughthemappingofmiddlebitvectorofB-treenode;then,extractedtheNext hopthrough the value mappingof Bloom filter bit arry.Theexperimentalresults showthat,compared withother Tre and Bloom filteralgorithms,BTBFalgorithmcanefectivelyreducespaceandtime,and maintainstable routing performanceunder the condition of larger changes in Routing-Table Entries.

Key Words: routing lookup algorithm; B-tree; Bloom Filter; IPv6 backbone routing table

# 0 引言

IPv6 得到了产业界和学术界的广泛关注和认可，中国的下一代互联网CNGI（Chinanext generationInternet）与美国联邦机构也早已对IPv6 进行了预先部署[1]。IPv6地址长度从IPv4的32bit变为128bit，使得互联网的骨干网路由器在进行表项查找时遇到巨大的性能瓶颈。因此，必须研究针对IPv6路由表的可靠快速的查找机制[2][3]。

IP路由查找算法可分为基于前缀长度和基于前缀值的查找算法。基于前缀长度的算法多采用树形数据结构，不过在推广至IPv6查找时，IP地址长度增长至IPv4的4倍，树形结构的查找深度变大从而降低了查找效率。基于前缀值的查找算法可以避免查找树的较大深度的问题，Zhong[4]提出了一种以B-树为基础的递归平衡多路径区间树（RBMRTs）的数据结构进行最长前缀匹配，查找和更新的时间复杂度均为 $\mathrm { O } ( \mathrm { l o g } _ { \mathrm { m } } \mathrm { N } )$ 。但是，

RBMRTs的内部节点中存储了许多重复点，路由更新时增加了时间和内存需求。BSRPS算法[5将相邻的前缀值区间作为一个集合放置在一个节点中以减少查找树产生多余的空置与重复节点，但是该算法面对IPv6的海量地址空间时依然产生很多空置节点，大大增加了访存次数。Dharmapurikar 等人提出了基于Bloom filter的最长前缀匹配算法[，该算法将不同长度的IP 地址前缀，分别存储在不同的Bloomfilter中，在进行查找时，将待查找IP地址并行输入到各个过滤器中进行查询。该算法容易产生过多的误判，而且路由表中不同前缀长度对应的路由表的规模大小差异很大，无法保证找到一个适应力强的Bloomfilter。基于TCAM的高效浮动关键词匹配算法[7中采取前缀扩展的方式减少了Bloomfilter的数量，但是同时也扩大了路由表，降低了查找速度。基于Bloom 滤波器的快速路由查找方法[8]主要在索引表中探测首字节以减少Bloomfilter查询次数，但是未对首字节长度做出规定，因此首字节过滤效率不明确，而且在IPv6海量地址空间基础上索引表会增加查找时间。

针对以上问题，在当前骨干路由器IPv6路由表数据统计分析的基础上，结合B-树和Bloomfilter，提出了一种IPv6 路由查找算法。因为B-树在查询数量较多的路由表项时会出现大量重复节点的现象，所以仅用B-树查找前16bit前缀值，并形成对Bloomfilter的索引，然后对路由表进行进一步的查找。B-树深度小，能有效避免空置集合，在B-树的索引下，降低Bloomfilter 需要查找的路由表项规模、误判率和查找时间。

# 1 IPv6地址结构和骨干路由表特点

# 1.1IPv6 地址结构

RFC3587规定的最新IPv6全球单播地址结构如图1所示，由3个部分组成：nbit的全球路由前缀、64-nbit的子网标志和64bit的接口标志。全球路由前缀标志一个站点，子网标志用于标志站点内的一个子网，接口标志是用IEEEEUI-64格式生成的用来表示子网内的主机，用于路由的前缀长度最长为64bit。根据对骨干路由器的统计分析得知IPv6前缀长度最小为19bit。

![](images/c203b8f9a13c089092e84fd3e28ca6abd832aebbf3827aaf32f608550492282f.jpg)  
图1IPv6全球单播地址结构

# 1.2骨干路由表特点

对骨干路由器potaroo9自治域 AS131072 的所有8万余条路由表项的统计分析，可以发现目前骨干路由器中IPv6地址有如下特点：

a）如图2所示，对前16bit取值统计发现，无前缀长度小于16bit的路由表项，前16bit取值有39个，其分布不均匀且数目差别较大。基于前缀值的查找方法不能有效匹配到数量较多的前缀集合中，在针对IPv6进行路由查找时，一方面需要增加路由查找取值较多集合的概率，另一方面需要减少路由前缀值查找树的深度，以便更快的找到所需要探测的集合，BTBF算法中采用B-树以实现更低的查找树深度。

![](images/33d923d05906acb13e2b1a2558b0ffc433b012f8ff0f6cc99b6af77680558452.jpg)  
图2 potaroo 路由器所有前16bits 取值统计

b）potaroo官网数据显示，IPv6路由表由前缀长度值从/16到/64的分布差异很大，对AS131072路由表进一步统计分析后得到图3，图中一条线代表了一个前16bit取值的集合、在不同前缀长度的路由表前缀集合数目变化。

![](images/85d1f8b9b65e584536350e8ab7d461a895f5d8c5ab1c3051a007278ea08a0fe4.jpg)  
图3potaroo 路由表项前16bits 取值及长度统计

虽然前16bit前缀值形成的各集合元素个数差异较大，但是从图3中可以看出，其分布的特征基本相同。利用B-树和前缀长度值，把整个路由表项划分成很多个元素个数较少的集合，图中每一个峰值对应一个划分好的集合，代表BloomFilter 需要查找的路由表项。为了简化算法设计，对所有集合的数目设定一个阈值用来划分级别，图3中的虚线位置1000将这些集合划分了千级和百级。这样BloomFilter可以针对划分好的级别，得到最优的Hash函数个数和位数组大小，以便在降低错误率的同时提升查找效率。

# 2 基于B-树和Bloom filter的路由查找算法

IPv6路由表中前16bit取值较少，在2001、2600和2804上较为集中，其余的取值路由表项较少。BTBF首先利用B-树对前16bit的取值进行查询，将每个对应的路由表依据前缀长度进行分类，如potaroo 骨干路由器可以从/19-/64共分为46个组。每组对应一个Bloomfilter，对不同规模的组，采取不同数量的hash函数和位数组大小，降低无效探测的次数。

# 2.1数据结构

# 2.1.1前16bit值的B-tree树型结构

B-tree的查找、插入和删除操作皆以"对数时间"的速度完成，它是一种自平衡的树，所以B树不需要像其他平衡查找树那样频繁地重新保持平衡。子节点数量的上界和下界，根据特定的实现而设置，根据前16bit取值出现的数量较少，数值分布不均匀的特征，设定B树子节点数量的上界为2，下界为3，通常这种树也被称之为2-3树。该树有三个重要特征:非空节点上的"数据项"大于等于1且小于等于2；每个节点最多有3个子节点；该树是自平衡树。在进行更新时需要将4-node 转换为3-node或2-node，这个转换操作只需要在常数量级的时间内即可实现。

# 2.1.2B-tree节点的数据结构

B-tree的节点类型分为叶子节点和非叶子节点，每个节点上存储有1-2个数据项，这些数据项存储了前16位前缀值。节点与Bloomfilter 的转发操作利用到两个长 $\mathbf { \nabla } _ { m }$ bit 的位向量：$V _ { S } [ h ( / 1 9 ) , h ( / 2 0 ) , h ( / 2 1 ) , . . . , h ( / 6 4 ) ]$ 和 $V _ { L } [ h ( / 1 9 ) , h ( / 2 0 ) , h ( / 2 1 ) , . . . _ { ! }$ $h ( / 6 4 ) ]$ 。 $V _ { S }$ 和 $V _ { L }$ 分别存储了集合元素的映射信息，向量内的Hash函数 $h ( / n )$ 会根据前缀长度 $n$ 将集合映射到向量 $V$ 中，其中树节点的数据结构如图4所示。

<html><body><table><tr><td>S</td><td colspan="2">L</td></tr><tr><td>LNode</td><td>MNode</td><td>RNode</td></tr><tr><td colspan="3">Vs[h(/19),h(/20),h(/21),·h(/64)]</td></tr><tr><td colspan="2">VL[h(/19),h(/20),h(/21),·h(/64)]</td><td></td></tr></table></body></html>

该节点含有两个数据项 $s$ 和 $L$ ，标志位CNUMBER，三个指针LNode，MNode和RNode，及两个向量 $V _ { S }$ 和 $V _ { L \circ } ~ S$ 和 $L$ 分别为节点中较小的前缀值和较大的前缀值，各16位。CNUMBER为该节点的子节点数量，标记节点类型为2-node、3-node或叶子节点，共有2位，取值可为11、10或00。如果CNUMBER为11该节点则为3-node，并表示节点最多有3个子节点，节点中存储全部的数据项、子节点指针和向量；如果CNUMBER为10 该节点则为2-node，并表示节点最多拥有两个子节点，数据项仅保留 $s$ ，向量仅保留 $V _ { S }$ ；如果CNUMBER的值为00时表示当前节点无子节点即为叶子节点。LNode，MNode和RNode分别为节点的左中右子节点指针。 $V _ { S }$ 和 $\boldsymbol { V } _ { L }$ 为节点中的两个向量，映射路由前缀前16bit的值为 $s$ 或 $L$ 的路由表项集合，该向量的每个元素为hash值 $h ( / n )$ ， $h ( )$ 为hash 函数， $n$ 为前缀长度。 $h ( / n )$ 表示前缀长度为 $n$ 的路由表项集合地址。根据目前IANA的IPv6地址分配策略，骨干路由器中无前缀长度小于19的路由表项，因此向量的元素从 $h ( / 1 9 )$ 至 $h ( / 6 4 )$ 有序存储。路由查找两个阶段的转发操作利用到了 $\mathit { V } _ { S }$ 和 $V _ { L }$ ：当B-树节点匹配成功时，算法选取数据项 $s$ 或者 $L$ 对应的向量，读取向量元素存储的路由集合地址，转发至Bloomfilter查询。

# 2.1.3Bloomfilter 的数据结构

如图5所示，首先，Bloomfilter初始化后有一个 $\mathbf { \nabla } _ { m }$ 位的位数组，数组元素全为0。同时，定义了 $k$ 个不同的Hash 函数，每一个hash 函数都随机的将输入元素映射到位数组中的一个位上。那么在没有发生误判的情况下，对于一个确定的输入，都会得到一个确定的位数组值。

![](images/3802fcab7dfdcd5951a9ff4b66b09cbc0d1bfd541bfeb73dc8cff8c3131cb522.jpg)  
图5基本Bloomfilter与改进后的Bloomfilter

在标准Bloomfilter 算法中常常会碰到哈希算法中的冲突（碰撞）问题，不同数值经过哈希得到的两个结果值有可能相同，这时就会发生误判[0]。图5中，当插入x、y、z这三个元素之后，再来查询w是否在集合之中，而如果w经过三个hash函数计算得出的结果所得索引处的比特位全是1，那么Bloomfilter则得出w在集合之中，实际上这里是误报，w并不在集合之中。标准Bloomfilter不能进行删除操作，改用counters计数数组改进原有的位数组。在插入元素时给计数数组的 $k$ 个元素的值分别加1，删除元素时给计数数组 $k$ 个元素的值分别减1。

Bloomfilter用来探测B-树的匹配节点转发到的路由表项集合，具体方案是：首先，读取 $V [ h ( / 1 9 ) , h ( / 2 0 ) , h ( / 2 1 ) , . . . , h ( / n ) ]$ 向量各个非空元素值，得到 $m$ 个集合的地址（ $1 { < } m { < } n { - } 1 8 )$ ，每一个集合都对应了一个Bloom filter，所以共有 $\mathbf { \nabla } _ { m }$ 个Bloom filter。然后，将数据包的目的IP地址并行输入到这 $\mathbf { \nabla } _ { m }$ 个Bloomfilter中查询。最后，根据匹配到的BloomFilter 计数数组的取值索引路由表，提取下一跳地址。

![](images/ab0531018c2381154435dd1679d6e19a3300eb5cf8a03041e00dcf2bd1ae8757.jpg)  
图4B-tree节点数据结构  
图6路由前缀集合存储与地址映射

在最后一个步骤中，Bloomfilter仅能探测有无符合目标IP地址的最长前缀，它的本身是不存储路由表的，具体的下一跳地址需要进一步地搜索路由表。即使骨干路由表按照前缀长度进行了分类，但是某些长度的集合表项依然十分庞大，传统的搜索提取会对查找性能造成影响，所以提出BloomFilter的映射方式对目标路由表项进行快速提取。BloomFilter中插入一个新的前缀X时，得到counters位数组的值 $C _ { n }$ 。如图5，X的值$C _ { x } = 0 1 0 0 0 1 0 0 0 0 1 0 0 0 = 0 { \mathrm { x } } 2 2 0 8$ 。通过 $C _ { n }$ 的值建立地址映射 $f _ { x }$ $( C _ { n } )$ ，此地址映射就是目标IP地址前缀在路由表中的具体位置。通过这种方法可以对IP数据包进行快速查找并转发。图6给出了路由表项的存储及各表项地址的关系示意图。

# 2.2路由查找

路由查找的伪代码如下所示：

input:dstIP;//目的IP地址   
output:next hop;   
1. search BTBF(dstIP){   
2. $\mathbf { B M P } =$ next hop of default route;   
3. key $\ O =$ the 1-16bit of dstIP;   
4. node $\mathbf { \Sigma } =$ search B-Tree of order 3(key);   
5. if(node.CNUMBER $\scriptstyle = = 2$ )node.S $\ O =$ node.L; 6. if(key $! =$ node.S $\parallel$ key $! =$ node.L) {

7. if(key $<$ node.S） node $\ O =$ node.LNode;   
8. if(key $>$ node.S&&key $<$ node.L) node $\ c =$ node.MNode;   
9. if(key $>$ node.L) node $\ c =$ node.RNode;   
10.search BTBF(dstIP);   
11.}else{   
12.if(node.CNUMBER $\scriptstyle = = 0 ^ { \cdot }$ )returnBMP;   
13.if(key $\ O =$ node.S return Vs[];   
14.if(key $\ O =$ node.L return $\mathrm { \Delta V _ { L } [ ] }$   
15. $\}$ （204号   
16.i $\ O =$ the length of route prefix;   
17.counters $\mathbf { \Sigma } =$ BinaryArray of Bloom Filter;   
18.for( $\dot { 1 } = 6 4$ down to 19)search dstIP%i;   
19.if $\mathrm { ( V [ h ( / i ) ] = 1 }$ )return counters[i];   
20.return $\mathbf { B M P } =$ fx(counters $[ \mathrm { i } ] ) \mathrel { - } > \mathrm { n e }$ xthop;}

先将路由器的默认下一跳存入BMP（BestMatchingPrefix）（第2行)，然后提取目的IP地址的前16bit在B-树上查找（3-14 行)，具体查找过程如下，首先判断当前节点类型是2-node还是3-node类型，如果节点类型是2-node，则数据项 $s$ 赋值为$L$ （第5行)。然后赋值目的IP地址的前16位值为key并与数据项比较，在key与数据项都不相等的情况下，根据条件式决定转发至LNode，MNode或RNode查找。（6-10行）。如果无匹配到的节点并且当前节点为叶子节点，说明路由表项中不存在匹配的前缀，转发数据包至默认下一跳。（第12行)。如果有匹配的节点，则返回节点中对应的向量 $V$ (13-14行)。最后在BloomFilter中查找目的IP地址对应前缀长度前缀，如果找到，则返回counters数组值，并根据这个值对地址进行提取；如果没有找到，则转发至默认路由下一跳（16-20行）。

图7为算法流程图，算法采用B-树和BloomFilter相结合的方式进行路由查找，因此图7共分为2大部分，左边部分为B-树查找过程，右边部分为BloomFilter 查找过程。B-树部分查找过程如下：

a）截取当前需要查询的IP地址的前16bit，并将它的值赋予变量key，将节点变量node赋值为B-树根节点；

b)第二步进入B-树的遍历查找，首先判断key是否和节点node中的 $s$ 相等，若等，则匹配成功，进入BloomFilter查询 $V _ { S }$ 向量映射的路由表集合。若不等，则判断是否和节点node中的 $L$ 相等，若等，则进入BloomFilter查询 $V _ { L }$ 向量映射的路由表集合。

![](images/016fda78fd530d448e11978514426986012f1fa947c27d7dd97a7a9fcfe82b43.jpg)  
图7路由查找流程图

c）如果key和 $s$ 与 $L$ 都无法匹配，那么需要进入下一节点查询。首先根据CNUMBER取值判断node节点有几个孩子节点，若CNUMBER为00，则表示其为叶子节点，此时匹配项为默认下一跳；若CNUMBER为01，则表示该节点有两个子节点，当key 值大于S时进入左节点LNode查询，小于 $s$ 时，进入右节点RNode查询；若CNUMBER为11，则表示该节点有三个子节点，当key 小于 $s$ 时进入左节点LNode查询，key 大于 $s$ 且小于 $L$ 时进入中节点MNode 查询，key大于 $L$ 时进入右节点LNode查询。最后将查找到的LNode，RNode或MNode赋予node变量，进入第b）步循环查找。

当目的地址IP的前16bit在B-树查找匹配成功后，将得到其值对应的向量 $V$ 所映射的路由表项集合，在该集合里，按照前缀长度/19-/64再次划分为46个小集合，每个集合对应一个Bloomfilter，然后进入Bloomfilter查询阶段：

a）将目的IP地址按位从/19至/64并行输入到对应长度的BloomFilter中进行查找;

b)如果Bloomfilter验证没有匹配项，则进入默认下一跳。如果Bloomfilter验证有匹配项，则根据BloomFilter中的前缀地址映射得到对应的下一跳。至此，查找流程结束。

# 2.3路由更新及算法性能分析

# 2.3.1路由的更新过程

BTBF算法支持增量更新，在路由表发生变化时只需要局部更新数据结构而不需要重头重新构建整个数据结构。当需要添加一个新的路由表项时，需要分别执行B-树的插入操作并在BloomFilter中执行计数数组元素值增加操作。

a）B-树中的插入操作为：获取路由项的前16bits前缀值value和前缀长度 $n$ ，在B-树查找value并得到匹配节点，如果匹配节点的 $s$ 或者 $L$ 值有相同数值，则转发向量 $V [ h ( / n ) ]$ 元素索引的BloomFilter进入第b）步更新；如无此值，则在B-树节点中插入该值，B-树（本章算法使用的是2-3树）会根据需要自动旋转以致平衡，最后，更新向量元素 $V [ h ( / n ) ]$ ，并转发至$h ( / n )$ 映射的BloomFilter进入第（2）步更新。

b）Bloomfilter的插入操作为：第a）步映射的BloomFilter的counters计数数组探测到的元素值 $^ { + 1 }$ 。

删除前缀信息的操作与更新操作类似，首先执行更新过程的第a）步的B-树查找操作，不过，第b）步counters计数数组元素的值-1。此外，当BloomFilter的counters 数组值 $C _ { n }$ 为0时，表示该集合已无路由前缀，这时需要回溯至B-树节点，向量元素 $V [ h ( / n ) ]$ 置0，并释放地址映射。若向量 $V$ 所有元素值均为0，则需要回溯至B-树，删除节点中相应数据项，最后执行自动平衡旋转操作。

# 2.3.2算法性能分析

B-树的高度决定了查找效率，BTBF算法采用的2-3树形结构，在最坏的情况下，也就是所有的节点都是2-node节点，查找效率为 $\lg \mathrm { N }$ 。最好的情况所有的节点都是3-node节点，查找效率为log3N约等于0.631lgN距离来说，对于1百万个节点的2-3树，树的高度为12-20之间，对于10亿个节点的2-3树，树的高度为18-30之间。插入只需要修改与该节点关联的节点即可，不需要检查其他节点，所以效率与查找相同。

本文算法中B-树仅负责查找前16bit前缀值，而当前骨干路由表的前16bit值只有几十个，可以形成较好的树形，因此时间复杂度约为O(log3N)，而仅使用B-树进行路由查找的RBMRTs算法查找效率为 $\mathrm { O } ( \mathrm { l o g N } )$ 。本文算法每个节点至少可存储两个路由匹配项，最好情况下需要N/3-N/2个节点，RBMRTs算法则至少需要2N个节点。

BloomFilter 的插入/查询时间都是常数 ${ \mathrm { O } } ( k )$ ， $k$ 为Hash 函数个数，使用BloomFilter需要考虑到它的错误率（误判率），错误率 $p$ 由以下公式确定：

$$
p = \left( 1 - \left( 1 - { \frac { 1 } { m } } \right) ^ { k n } \right) ^ { k } \approx \left( 1 - e ^ { \frac { k n } { m } } \right) ^ { k }
$$

$m$ 是位数组大小， $n$ 是BloomFilter查找的集合元素个数。上述公式表明随着 $\mathbf { \nabla } _ { m }$ 的增加，错误率会下降，同时随着插入元素个数 $n$ 的增加，错误率又会上升，对于给定的错误率 $p$ ，最优Hash函数个数 $k$ 由以下公式确定：

$$
k = \frac { m } { n } l n 2 \approx 0 . 7 \frac { m } { n }
$$

最优的位数组大小 $\mathbf { \nabla } _ { m }$ 由以下公式确定：

$$
m = - \frac { n l n p } { ( l n 2 ) ^ { 2 } }
$$

根据以上公式，可以确定出BloomFilter最优的位数组大小和Hash函数个数，从而大大降低它的错误率。假设将错误率控制在0.001左右，根据前文骨干路由器的数据统计可知，在数据最庞大的2001:：段，前缀长度集合根据数量可分为千级和百级，如/48长度的为2970个，2620::段/32长度的为1362个，为了方便分级定位千级的集合统一取 $n$ 值为2500，根据计算结果可知即使是大的集合，最优的位数组大小也仅为 $m { \approx } 3 5 \mathrm { K b }$ ，最优Hash 函数的个数 $k$ 为10.06，所以 $k { = } 1 0$ 。与上述同理，百级集合取近似中位数200，它的最优位数组大小和Hash函数个数分别为 $2 . 8 \mathrm { K b }$ 和 10 个。相比 SARANG D[6]和 J.H.Mun[10]提出的BloomFilter类路由查找算法，本文在两次划分集合后使集合元素个数和Hash函数的数量都得到大幅度缩减。同类型的BloomFilter 需要查找整个路由表项，Hash函数个数在13个以上，不仅增加了误报率，还增加了查找时间，降低查找效率。

# 3 实验验证

实验阶段收集了IPv6骨干路由器自治域AS6447、AS131072和AS3356的路由前缀，使用 $\mathrm { C } { + } { + }$ 语言在VisualStudio平台上编写了测试代码。首先统计了三个自治域的路由表项，根据统计结果和上文中BloomFilter最优数组大小 $\mathbf { \nabla } _ { m }$ 和Hash函数个数 $k$ 值的公式，将经过B树分类后的路由表项集合进行了分类处理。分类结果与上文相同，确定了两个级别：千和百级，$\mathbf { \nabla } _ { m }$ 和 $k$ 分别为35Kb、10和2.8Kb、10。对应的错误率为0.001。实验中为了符合实际情况，均使用各自治域的活跃路由项。

表1三个自治域中前缀统计  

<html><body><table><tr><td>路由表项数</td><td>AS6447</td><td>AS3356</td><td>AS13172</td></tr><tr><td>前16bit为2001</td><td>2899</td><td>3619</td><td>5440</td></tr><tr><td>前16bit为 2600</td><td>1167</td><td>1609</td><td>2287</td></tr><tr><td>路由表项总数目</td><td>48348</td><td>56444</td><td>85899</td></tr></table></body></html>

在实现BloomFilter时多采用简单、性能较优的折叠异或哈希函数。生成了10万个数据包进行测试，为了验证数据包的大部分都有匹配条目， $8 5 \%$ 的数据包是从路由表中选择的路由条目，另外 $1 5 \%$ 的验证包是完全随机生成的，这样验证包可以匹配到路由条目，也可以匹配到默认下一跳。为了验证BloomFilter的错误率稳定性，分别对以上三个自治域的2001:：段和2600::段做了BloomFilter错误次数的统计。统计结果如图8所示。从图8可以看出实验结果基本与算法设计相符，错误率保持在0.001左右。在实际应用中，还可以根据每一个集合的大小定制最优的BloomFilter，从而使错误率更加符合预设。

算法内存消耗主要用于B-树、BloomFilter的位数组和路由表项的加载。在内存消耗的实验中，使用AS131072的BGP路由表，BTBF 算法的实现占用内存保持在 $2 7 0 0 ~ \mathrm { K B }$ ，其中绝大多数用于对路由表的加载。表2给出了内存消耗比较的结果。

![](images/458979821f8d9391a5ebc9cdd17e6ebb9251ecbdcee99a7800adfbe62a6047af.jpg)  
图8BloomFilter错误次数统计

表2真实路由表测试内存占用比较结果  

<html><body><table><tr><td>查找算法</td><td>表项数</td><td>内存</td></tr><tr><td>本文算法</td><td>85899</td><td>3.16M</td></tr><tr><td>基于Hash和CAM的IPv6路由算法</td><td>65535</td><td>15.33M</td></tr><tr><td>基于Bloom 滤波器的快速路由查找</td><td>25000</td><td>4M</td></tr><tr><td>BSRPS</td><td>78430</td><td>4.8M</td></tr></table></body></html>

理论上BTBF 算法时间复杂度最多为O(5)。查找性能部分的实验，继续使用上文中的10万个数据包进行测试，并与RBMRTs 算法，BSRPS 算法和Bloom 滤波器路由查找算法进行了比较。RBMRTs 算法的查找树内部节点中存储了许多重复的端点，当路由表项增大时，重复的端点也会成倍增加，导致不能输出稳定的性能。

BSRPS算法是根据前缀值区间所做的集合树进行查找，其性能表现稳定，但是由于IPv6的海量地址空间，集合树的深度不能控制到一个较低的级别，所以性能并不是十分良好。

基于Bloom滤波器的算法采用了首字节索引的方式排除了一部分不在路由表中匹配的IP 地址，降低了对Bloom过滤器的探测次数，不过，当被查询地址的首字节对应的索引数量较多时，首字节索引方式较并行查询的优势会缩小，滤波器数量的减少导致错误率和查找时间增大。图9中给出了这三种算法与BTBF算法在同一环境下的性能对比结果。

![](images/caa7828816901be0774bcee6a91d98c920421889d90c0f4b039dd86ee2ea2a3c.jpg)  
图9用生成的路由表测试的查找性能比较结果

从图中可以看到，随着表项的增加，算法的查找速度一直趋于稳定，并且保持在较高的性能上。这是由于BTBF算法对前缀进行了B-树和前缀长度的分类，这两种方式都能适应数据量的巨大变化，Bloom过滤器的查找集合一直保持在稳定的大

小。

# 4 结束语

分析了IPv6 地址结构，分配策略和IPv6骨干路由表的特征，将B-树和Bloom 过滤器相结合，提出了一种基于B-树和Bloom 过滤器的BTBF 算法。与已有算法相比，BTBF 算法查找速度快，占用内存小，有较好的扩展性，并且支持增量更新。实验结果表明，BTBF算法在保持优良的查找性能外还能适应路由表大小的改变，始终保持稳定状态。这得益于对B-树查找深度低这一优良特点的充分利用，促使整个算法的正确性和可靠性，实验结果也验证了该方法的有效性。

# 参考文献：

[1]李振强，郑东去，马严.TSB:一种多阶段 IPv6 路由表查找算法[J]．电 子学报,2007,35 (10): 1859-1864.(Li Zhenqiang, Zheng Dongqu,Ma Yan. TSB:a multi-stage algorithm for IPv6 routing table lookup [J].Acta Electronica Sinica,2007,35(10):1859-1864.)   
[2]Hsiao Yimao,Chu Yuansun,Lee Jengfarn,et al.Ahigh-throughput and highcapacity IPv6 routing lookup system [J]. Computer Networks the International Journal of Computer & Telecommunications Networking, 2013,57 (3): 782-794.   
[3]Bando M,Chao H J.Flashtrie:hash-based prefix-compressed trie for IP route lookup beyond 100Gbps [C]// Proc of IEEE INFOCOM.2010: 1-9.   
[4] Zhong Pingfeng.An IPv6 address lookup algorithm based on recursive balanced multi-way range trees with efficient search and update [Cl// Proc of International Conference on Computer Science and Service System.2011: 2059-2063.   
[5]崔宇，田志宏，张宏莉，等．基于前缀区间集合的 IPv6 路由查找算法 [J]．通信学报,2013,34(06):29-37,48.(Cui Yu,Tian Zhihong,Zhang Hongli,etal.Bianary search on range of IPv6 prefix sets [J]. Journal on Communications,2013,34 (06): 29-37+48.）   
[6]Dharmapurikar S.Longest prefix matching using bloom filters[J]. IEEE//ACM Transactions on Networking,2006,14(2): 397-409.   
[7]李鲲鹏，兰巨龙．基于TCAM的高效浮动关键词匹配算法[J].计算机 工程,2012,38 (4): 269-274.(Li Kunpeng,Lan Julong.Efficient unfixed keywords matching algorithm based on TCAM [J]. Computer Engineering, 2012,38 (4): 269-274.)   
[8] 于明，王振安，王东菊．基于 Bloom 滤波器的快速路由查找方法[J]. 哈尔滨工程大学学报,2014,35(10):1247-1252.(Yu Ming,Wang Zhen an,Wang Dongju.A fast method for IP lookups based on Bloom filters [J]. Journal of Harbin Engineering University,2014,35(10):1247-1252.)   
[9]http://bgp.potaroo.net [EB/OL].2017.   
[10] Ju HM, Lim H. New approach for efficient IP address lookup using a Bloom filter in trie-based algorithms [J]. IEEE Trans on Computers 2016,65 (5): 1558-1565.