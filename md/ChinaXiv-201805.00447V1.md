# 命名数据网络中分组报文缓存优化方法\*

智江¹²，李俊」，吴海博‘

(1．中国科学院计算机网络信息中心，北京 100190;2．中国科学院大学，北京 100190)

摘要：传统网络缓存系统中数据包级别的缓存难以实现，信息中心网络的出现使这个难题得以缓解。即使如此，数据包级别的缓存仍然面临严重的扩展性问题。通过分析当前限制数据包级别缓存实现的若干问题，提出了一种分组报文缓存优化方法。这种方法通过根据分组前缀而非单个报文前缀建立索引来减少高速存储器的使用量，同时分组级别的流行度也用于优化缓存决策。定义了大量的评估指标，并通过广泛的实验来评估此方案的性能。实验结果表明，与之前的数据包级别的缓存方案相比，此方法可以大大减少高速存储器使用量，并且在服务器负载减少率、平均跳数减少率和平均缓存命中率方面取得显着改善。

关键词：包缓存；命名数据网络；网内缓存；缓存决策 中图分类号：TP393.0 doi:10.3969/j.issn.1001-3695.2018.03.0177

# Grouped-packet caching optimization approach for NDN

Zhi Jiang1,²,Li Jun],Wu Haibol (1.Computer NetworkInformation Center,ChineseAcademyofSciences,Beijingl00l90,China;2.UniversityofChiese Academy of Sciences,Beijing 100049,China)

Abstract:Packet-levelcachingisdifficulttoimplementintheraditionalcachingsystem.TheemergenceofInformation-centric networking has alleviatedthis problem.However,the packet-levelcaching is stillfacingseverescalability issues.This paper analyzedtheissues which limitthe implementationofpacket-levelcachingand proposedapacket-levelcachingoptimization approach.This schemereduces theconsumptionofast memory by creatingthe index with group prefixes insteadofthe packet prefixes,whilethe group-levelpopularityisalsousedtooptimizecachingdecision.This paperevaluated theperformanceofthe scheme through extensive simulation experiments regarding a wide range of performance metrics.The experimental results indicatethe schemecanreduce the fast memory usage andachieve significant improvementin terms ofserverloadreduction ratio,average hop reductionratio and average cache hit ratio,compared with currnt packet-level caching schemes.

Key Words: packet caching; named data networking (NDN); in-network caching; caching decision

# 0 引言

现今互联网的主流应用已经由端到端模式的通信转变为了以内容分发和获取为主的应用。根据思科VNI报告中错误!未找到引用源·预测，预计 2021年内容获取类应用产生的网络流量（如互联网视频、Web数据、文件共享等)将占总网络流量的 $8 5 \%$ 以上。网络缓存这是缓解上述流量压力的重要技术之一。网络缓存设备可以暂存内容对象并响应之后的用户请求。一些研究指出，相比于整个内容对象的缓存，更细的粒度的缓存（比如数据包级别的缓存）能够获得更好的缓存效果。因为数据包级别的缓存可以做出更细粒度的缓存决策，从而可以进一步提高网络性能，尤其是当对象的不同部分具有不同的流行度时错误!未找到引用源。

然而，在传统的TCP/IP网络中，数据包级别的缓存却难以实现，因为它需要借助诸如DPI等会产生较高开销的技术，这将造成严重性能瓶颈和扩展性问题。

传统缓存中数据包级别的缓存所面临的问题可以通过新近出现的信息中心网络架构（information-centric networking，ICN）来缓解[3-6]。ICN架构采用了接受者驱动的通信模型，并且将命名的数据作为网络中传输的基本元素。通过名字可以标识这些数据包，因此在ICN体系结构中，命名的数据可以存储在任何有缓存能力的网络设备中（如路由器)。当请求消息到达时，网络设备可以从其存储库中检索内容数据。如果内容已被缓存，则可以直接响应用户请求，而无需将请求转发向内容服务器。这样，网络带宽消耗和内容服务器的负载可以显着降低。同时，

由于请求延迟的减少，用户体验也将大大改善。

ICN架构的出现缓解了数据包级别缓存遇到的一些问题，然而，ICN架构下数据包级别的缓存在实现上仍然存在诸多挑战：高速存储器（如SRAM）的容量限制;对于线速转发的要求;数据包级别的流行度统计等。

为了以较低的成本实现数据包级别的缓存，本文根据空间局部性原理，引入一种了基于分组数据包的缓存方法（grouped-packetcaching，GPC)。在GPC中，我们使用分组前缀代替单个报文的前缀来建立索引项目以减少高速存储器容量的消耗。另一方面我们利用一个BloomFilter的存储器来过滤无效缓存查询请求，从而加速请求转发。此外，我们使用分组的流行度来优化缓存决策。具体来说，本文的主要贡献总结如下：

a)本文分析了限制数据包级别缓存实现的相关问题。并且基于空间局部性原理，引入分组报文的概念来缓解数据包级别缓存中存在的扩展性问题。

b)本文提出了一种名为GPC的数据包级别的缓存机制，可以显著加速那些未缓存的数据包的转发过程，同时大大降低高速存储器的使用量。

c)定义了若干评价指标来评估GPC机制的效果。实验结果表明，高速存储器的使用量显着降低。同时，与主流的几种包级别的缓存方案相比，GPC显示出了更优的缓存性能。

# 1 相关工作

在传统TCP/IP网络中，IP数据包由五元组标识，而其有效负载对网络设备不可见。为了实现数据包级别的网络缓存，则需要通过特定的方法（如 suppressingreplicated data，deltacoding或深度包检测等）来消除数据冗余。由于计算开销成本过高，在传统的TPC/IP网络难以实现数据包级别的缓存。因此，传统网络缓存通常存储完整的数据对象而不是单独的数据包。

近来出现的信息中心网络(ICN)使数据包级别的缓存变得可行。ICN体系结构将对象划分为命名的数据块，用户通过向网络发送一系列包含数据块名称的请求来获取内容对象。这些命名的数据块可以缓存在任何具有缓存能力的ICN设备中，这些设备也可以响应对已缓存数据块的请求。

由于ICN的出现，数据包级别的缓存方案引起了更多研究人员的关注。在文献错误！未找到引用源。错误！未找到引用源。中，作者通过确定内容缓存的位置来提高整体缓存效果。但是，它们没有考虑内容流行度的对缓存性能的影响，而事实上这一点是不能忽视的。最近，学者们普遍认识到内容流行对提高缓存性能起着至关重要的作用错误!未找到引用源。。因此，一些缓存策略通过同时考虑缓存位置和内容流行度来提高缓存效率[10-15]。然而，这些研究缺乏对对象流行度和数据包流行度之间的关系的分析，同时忽略了数据包级别流行度统计量的开销，这将会产生严重的扩展性问题。

在文献错误！未找到引用源。中，作者阐述了分块缓存的优势，并提出了一种量化效用的方法。评估结果表明，简单的基于效用的网内缓存算法和低复杂度的均匀分块足以发挥分块缓存的最大优势。Thomas 等人错误!未找到引用源·提出了一种面向内容对象的数据包级别的缓存机制（OPC)。在OPC中，缓存索引条目是基于整个对象而建立，而非针对单个的数据包建立（一个对象可以划分为多个数据包)。通过这种方法可以大大节省高速内存使用量。为了实现数据包级别的缓存，在这种机制中缓存系统中需要连续保存对象的前n个块而没有间隙，并且在缓存索引中加以标识。OPC可以解决数据包缓存的两个常见问题：循环替换和大对象污染问题。但是，由于作者没有考虑对象内部的流行度差异，因此缓存性能仍有提升空间。此外存储连续的n的数据块的方法不够灵活(分块缓存必须按序存储)，造成做出的缓存决策也较为僵化。

在总结上述已有工作的基础上，提出了一种新的数据包级别缓存的优化方法。

![](images/d726e8cc14e90f9c642619480343948b9c03058ea562db7c7355ae4527964f9d.jpg)  
图1数据包流行度差异

# 2 问题分析

# 2.1 有限的存储资源

在一个网络缓存设备中，内容数据通常存放在DRAM 或者 SSD 等低速存储器中，而查询索引则存储在SRAM等高速存储器中。在传统缓存中，一条索引对应一个整体的内容对象，而在包级别的缓存系统中，一条索引对应一个独立的数据包。由于一个内容对象通常可以划分为大量的数据包，相应所需的索引条目的数量也大大增多了。由此可知，与对象存储相比，数据包级别的缓存需要占用更多的高速内存来存储索引表，而高速存储器的成本限制了数据包级别缓存的发展。

# 2.2 无效的缓存查找

在ICN架构中，缓存系统不再是单个缓存设备，而是一个由大量设备组成的复杂的缓存网络。尽管缓存网络的总体容量可以很大，但由于受到线速转发的条件的制约，单个缓存节点的缓存容量大大受限。由于这个限制，单个缓存节点具有相对较低的缓存命中率。换句话说，大多数用户请求不会被单个缓存设备满足，而这些未命中的请求应该直接转发到下一跳。尽管如此，路由器总是查询外部存储器中的索引表，这将会导致性能瓶颈。

# 2.3数据包级别流行度的难题

为了提高网络缓存系统的效率，将高热度的内容对象快速推送到网络边缘至关重要。在传统的网络缓存系统中，缓存节点通常存储整个对象而不是数据包。实际上，一个内容对象的不同部分，特别是视频文件等，可能具有不同的流行度。因此，包级别的缓存的可以提高缓存性能错误!未找到引用源。但是，基于对象级别的流行统计不能充分发挥数据包级别缓存的优势，因为使用对象的流行度统计来估计数据包的流行度通常是不准确的。我们在图1用一个简单例子来说明这个问题。在图1（a）中，内容对象1的整体热度高于内容对象2。然而，对于部分A和部分B，可以看到，A中的数据包比B中的数据包具有更高的热度。因此，基于内容对象的热度统计，A的热度可能被低估，这可能会减少缓存这些数据包的几率。在图1（b）中，C的序号小于D，但D的热度更高。在这种情况下，优先选择内容对象中排在前面的数据包的缓存方法（如OPC错误！未找到引用源。）将过高估计C部分的热度，而决定缓存C而不是热度更高的D。以上两种情况都由于存储了热度较低的内容而导致缓存性能的下降。由此可知数据包级别的热度统计对于提升缓存性能十分重要。但同时这也会带来过多系统的开销，因此阻碍了包级别缓存的发展。

![](images/060cc030976a9ff54b81c52fb2ada9b4032dc0cb29f90bf7981e3be3a9b82ef9.jpg)  
图2CS索引数据结构

# 3 方案设计

# 3.1系统模型

为了简化描述，本文以ICN体系结构中的典型代表NDN（nameddatanetworking）作为示例来演示本文的缓存机制。

在本文中，认为一个NDN网络由多个具有有限容量缓存存储结构（content store，CS）的路由器组成。在NDN体系结构中，存在两种类型的数据包，即Interest报文和Data 报文。每一个Data数据包都具有一个名字前缀，客户端发送包含该名字前缀的Interest数据包到网络中以获取相应的Data数据包。中间路由器根据存储在转发信息库（FIB）中的信息将请求逐跳转发至内容持有者。转发信息库通过基于名称的路由协议（如OSPFN 错误!未找到引用源。或 NLSR 错误!未找到引用源。）建立。在请求过程中，路由器的PendingInterestTable（PIT）结构中记录该请求过程的路径的信息，通过这些信息，Data数据包可以沿着反向路径返回到请求者。

此外，假设Data 数据包的大小等于网络的MTU（默认为1500 Byte）。同时NDN路由器中具有内容热度统计表（PST)，可以记录和更新一段时间内数据包的访问热度。缓存的Data数据包存储在低速存储器中，例如DRAM或SSD 等。而索引信息则存储在如 SRAM 的高速存储器中。NDN 中数据包的名字由对象前缀（Object_Prefix）和序号（Seq）组成，其中序号表示该数据包在内容对象中的顺序。例如，名字前缀/ndn/file/video/sample/57表示对象/ndn/file/video/sample的一个数据包，并且数据包的顺序号为57。

# 3.2缓存机制

# 3.2.1报文分组

通常情况下，索引条目使用哈希表结构存储于高速存储器中。哈希表的优点是高效：元素操作（如查找，插入和删除）的时间复杂度为O（1)。但是，与对象级别的缓存不同，报文级别的缓存中存储的最小单位是数据包。由于一个内容对象通常由至少数百个块组成，因此会生成大量索引条目，从而需要占用大量的高速内存空间来存储这些索引条目。但事实上，隶属于同一个对象的不同数据包，它们的对象前缀都相同，区别仅仅是最后的序号部分。因此，减少内存消耗的一个可能的解决方案是采用字典树结构来存储索引。然而，尽管字典树可以通过共享相同的对象前缀来节省存储空间，但字典树的查询效率相对较低，尤其是当前缀的数量较大时。例如，要搜索前缀/ndn/file/video/sample/57，它需要进行五次匹配的操作。为了兼顾查询效率和存储空间节省，采用了分组报文索引的方式。

根据空间局部性原理：如果在某个特定的时间里某个特定数据块被请求，则相近的数据块也可能在近期被请求。基于上述观点，将N个连续数据包作为一个分组，并将该组中第一个数据包的名字前缀指定为分组前缀。缓存中的索引条目基于分组前缀来创建的。在每个索引条目中，添加一个Bit-Map 结构来标识分组中的某个数据包是否已被缓存。当且仅当相应的位值为1时，表明该数据包被缓存；反之该值为0时，表示该数据包未被缓存。实际的Data数据包以unorder_set的形式被存储在低速存储器中。unorder_set是一种基于哈希表的容器，其检索的时间复杂度为O（1)。索引条目包含一个指针，指向低速存储器中的该分组的容器。此外，高速存储器中还包含一个侵入式列表，用来对索引条目进行排序来完成替换功能。图2中描述了GPC策略使用的数据结构。缓存模块的核心操作包括有：

a)插入。路由器首先根据数据包隶属的分组的前缀创建索引条目（如果此条目此前未创建)，然后将相应的Bit-Map的位值设置为1。

b)换出。将Bit-Map中的相应位值设置为0。此外，如果该索引条目的Bit-Map中所有值均为0，则同时删除该索引条目。

c)查找。根据数据包隶属的的分组前缀首先查找L1级索引。如果找到分组前缀，则路由器检查Bit-Map。如果对应位值为1，则路由器访问低速存储器以检索块数据。否则直接转发请求。

# 3.2.2请求过滤

正如之前所讨论的，由于缓存容量的限制，单个路由器无法满足大部分的用户请求。为了加速数据包转发，我们利用一个芯片内置的BloomFilter 来减少外部存储器的访问次数。BloomFilter是一种查询效率很高并且占用空间较小的数据结构，可以快速而高效地对集合的内容进行检索。将索引信息同步到BloomFilter中。通常的BloomFilter只支持插入操作，为了增加对移除操作的支持我们采用的 BloomFilter 的一种扩展结构CountingBloomFilter。路由器缓存的L1索引条目的各项操作都被同步到BloomFilter中。由于存储在L1索引中的条目是基于分组前缀的，所以存储在BloomFilter 中的相应元素数量也大大减少了。例如，对于配备了4GBytesDRAM的路由器，当分组大小为32并且BloomFilter的假阳性概率为0.05时，只需要273KBytes来存储分组前缀。而如果要存储所有的报文前缀，BloomFilter所需的容量大约是8.5MBytes。显然，基于分组报文的缓存不但可以减少L1索引条目的数量也可以降低所需的BloomFilter的容量。所需的CountBloomFilter的容量可以通过式（1）计算。其中Cstorage表示低速存储器的容量，packet_size表示数据包的大小，group_size表示分组的大小， $\boldsymbol { \varepsilon }$ 表示假阳性的概率。

$$
\frac { C _ { s t o r a g e } \times \log _ { _ { 2 } } e \times \log _ { _ { 2 } } ( \frac { 1 } { \varepsilon } ) } { 2 \times p a c k e t \_ \mathrm { s } i z e \times g r o u p \_ s i z e }
$$

当用户请求到达时，路由器首先测试BloomFilter以确定L1索引中是否存在该分组前缀。如果测试结果为真，则路由器继续访问外部高速存储器以完成后续操作。否则，路由器直接转发请求。这样，绝大多数的用户请求将被过滤，并且访问外部存储器的次数大大减少。图3（a）描述了Interest报文的处理流程。

![](images/62a30328d81910bc2935e8456ada6c4bc5e72c63c89a1bee97cbd5d9e0193468.jpg)  
图3数据包处理流程

# 3.2.3分组级别的热度统计

数据包级别的热度统计很难实现，因为它将产生巨大的开销，尤其是是存储空间的消耗。因此，我们提出了分组级别的热度统计的概念。根据空间局部性原理可以推知，顺序上临近的报文具有相似的请求热度。因此，我们使用分组热度代替数据包热度来辅助路由器做出缓存决策。路由器在PST中记录分组热度信息，并根据分组前缀创建索引。这样将大大减少热度统计带来的开销。

当Data数据包到达时，路由器查找PST以获取该数据包隶属的分组的热度。如果它的热度值大于一个的阈值，则路由器决定存储该Data数据包。否则，路由器只转发Data数据包而不进行缓存。该阈值定义如下：

$t h r e s h o l d = \theta \times M i n ( p o p u l a r i t y ) \quad \theta \in [ 0 , 1 ]$ (2)其中Min（popularity）表示当前存储在CS中的内容的热度的最小值。 $\theta$ 是一个调整参数，用来适应网络中内容对象热度的动态变化，较小的0值适合于网络内容热度变化较快的场景。图3（b）描述了Data 数据包处理的流程。

# 4 性能评估

# 4.1实验设定

为了评估本方案的实际性能，本文在ndnSIM上实现了该方案。ndnSIM 是一个基于 NS-3 错误!未找到引用源·实现的模块，加入了NDN特性的数据结构和转发逻辑。基于ndnSIM增加了一些数据结构并修改了部分转发逻辑来实现GPC方案。在实验评估里，定义了三种不同分组大小的方案，其大小分别为8、16和32，命名为GPC-8，GPC-16和GPC-32。本文将这三种GPC策略与如下包级别的缓存策略进行对比：

a)CEE(cacheeverythingeverywhere)[2]：每一个缓存设备都会将经过的任何数据包缓存下来。

b)OPC (object-oriented packet caching)错误！未找到引用源。：面向内容对象的包缓存策略，用以对象级别建立索引，并对一个内容对象的前N个数据包进行连续存储。

在实验中，假设用户请求服从 Zipf 分布错误:来找到引用源。，并且将默认的Zipf分布参数值设定为1.0。此外，为了考察 Zipf分布参数对缓存性能的影响，将其值的变化范围设定为 $0 . 7 { \sim } 1 . 3$ 。假定组成一个内容对象的数据包数量服从 $N$ （1000,250)。通过实际采样得到的数据包的数量值分布于区间[68,2026]。利用流量生成器来生成可变流行度的数据包并分别采用BA 模型错误\*找到引用源。和 WS 模型普误！未找到引用源。构建实验拓扑。实验拓扑由 100个节点构成，包含一个随机选择内容服务器节点和66个边缘路由器节点，其余节点为中间路由器节点。设定每个节点的缓存容量为1000个数据包,BloomFilter 的默认容量为150 Byte,并且将其变化范围设定为90\~210Bytes来考察其容量对过滤效果的影响。请求速率设置为200个请求/s。除了Zipf分布参数、分块数量和BloomFilter容量外，其余参数都固定为默认值，表1描述了实验的主要参数设置。

表1实验参数设定  

<html><body><table><tr><td>参数</td><td>默认值</td><td>变化范围</td></tr><tr><td>Zip 分布参数α</td><td>1.0</td><td>0.7~1.3</td></tr><tr><td>分块数量</td><td>1000</td><td>68~2 026</td></tr><tr><td>BF容量</td><td>150 Bytes</td><td>90~210 Bytes</td></tr><tr><td>内容总数</td><td>1000</td><td>-</td></tr><tr><td>缓存容量</td><td>1000</td><td>-</td></tr><tr><td>请求速率</td><td>200 req/s</td><td></td></tr><tr><td>总节点数</td><td>100</td><td></td></tr><tr><td>边缘路由器数</td><td>66</td><td></td></tr><tr><td>仿真时间</td><td>180s</td><td>-</td></tr></table></body></html>

![](images/270a9c30e9df50d25795a2d56947ca5e1e3639a00b34fce40ac432b44f2b74e7.jpg)  
图6存储器访问减少率

图5链路负载率  
图7索引占用量

# 4.2性能指标

本文定义了如下性能指标来评估GPC方案的实际性能：

a)服务器负载减少率，用来描述缓存系统使内容服务器工作负载降低的比率，具体定义为

$$
S L R R = 1 - \frac { S \_ c o u n t s } { R \_ c o u n t s }
$$

其中：S_counts表示由服务器响应的请求总数，而 $R$ _counts表示

总的用户请求数。

b)平均跳数减少率,反映由于缓存系统的加入，使用户请求内容跳数减少的比率，定义为：

$$
A H R R = 1 - \frac { \displaystyle \sum _ { 1 } ^ { R _ { - } c o u n t s } h o p s _ { - } c } { \displaystyle \sum _ { 1 } ^ { R _ { - } c o u n t s } h o p s _ { - } n c }
$$

其中:hops_c 表示缓存命中节点到请求用户之间的跳数,而hops_nc表示请求用户到内容服务器之间的跳数,R_counts表示总的用户请求数。.

c)平均缓存命中率,反映所有缓存节点的平均命中率，定义为.

$$
A C H R = \frac { \displaystyle \sum _ { R } H i t _ { \mathrm { - } } c o u n t s _ { r } } { \displaystyle \sum _ { R } R _ { \mathrm { - } } c o u n t s _ { r } }
$$

其中：Hit_countsr表示用户请求在路由器 $\boldsymbol { r }$ 处命中的次数，R_countsr表示路由器 $\boldsymbol { r }$ 收到的用户请求的总次数。

d)链路负载率,反映特定链路在一定时期内的流量负载状况。

e)存储器访问减少率,反映由于加入BloomFilter使得访问存储器次数减少的比率，具体定义为

$$
S A R R = \frac { \displaystyle \sum _ { R } F _ { - } c o u n t s _ { r } } { \displaystyle \sum _ { R } R _ { - } c o u n t s _ { r } }
$$

其中:F_countsr表示用户请求在路由器 $\boldsymbol { r }$ 处被BloomFilter过滤的总次数，R_countsr表示路由器 $\boldsymbol { r }$ 收到的用户请求的总次数。

f)索引占用量，反映特定节点中缓存索引所占用的高速存储器的容量。

# 4.3 结果分析

在多种拓扑下进行大量的仿真实验,分析了各种策略下，Zipf分布参数 $\mathfrak { a }$ 变化（ $\cdot 0 . 7 { \sim } 1 . 3 \$ ）对缓存性能的影响。结果表明GPC 策略在定义的评价指标上明显优于其他方案，同时内存的消耗量也大大降低了。

# 4.3.1缓存性能

图4(a)\~(c)分别显示了Zipf参数对缓存性能的影响。随着$\mathfrak { a }$ 的增加，所定义三个性能指标都有所改善。这是因为随着 zipf分布参数的增大，热门内容的热度也随之增加，这有助于缓存系统的性能的发挥。如图4所示，本文方案在三个性能指标方面都优于其对比方案。另一方面，可以发现GPC-8获得了最优的缓存性能。这是因为分组大小越小，获得的热度值就越精确，从而作出的缓存决策也更加准确。与OPC相比，GPC-8在三项指标上的平均改进分别为 $2 9 . 5 3 \%$ ， $48 . 8 6 \%$ 和 $82 . 3 6 \%$ 。而与CEE相比，性能指标的平均改善可以达到 $3 7 . 6 5 \%$ ， $105 . 9 9 \%$ 和$12 5 . 1 9 \%$ 。

# 4.3.2链路负载率

通过收集和分析链路数据传输状态来评估缓存策略对链路负载率的影响。图5显示了不同缓存策略下的前10名流量负载的链路的流量负载率。可以发现，使用GPC-8策略的场景下

链路负载率明显低于其他策略。就该项指标而言，GPC-8相对于CEE和OPC的平均改进为 $40 . 4 5 \%$ 和 $1 9 . 0 8 \%$ 。

# 4.3.3外部存储器访问

图6显示了BloomFilter 的作用。通过BloomFilter，大多数请求都直接转发而无须访问外部存储器。在图6中，随着BloomFilter容量的增加，转发效果逐步提升。但同时可以发现性能曲线是上凸的，表明性能改善率不断下降。也就是说BloomFilter的效果具有上限，因而不能为了获得更好地过滤效果而一味增大其容量。

# 4.3.4索引占用量

图7显示了低速存储器容量和索引大小之间的关系。假设每个索引条目的大小是40个字节，而数据包大小是1500 Byte。GPC-8，GPC-16，GPC-32的Bit-Map大小分别为1，2，4字节。对于GPC-8来说一个索引条目最多可以表示8个数据包，而一个CEE 索引条目只能标识一个数据包。因此，通过增加组大小，索引条目数量也可以减少，因而高速内存使用量可以相应减少。

# 5 结束语

本文提出了一种全新的数据包级别的缓存优化方法，它从多个角度入手缓解了NDN 架构下数据包级别缓存所遇到的扩展性问题。该策略将组成内容对象的若干数据包按照顺寻分成多个分组，并使用分组前缀建立索引条目以减少高速内存的使用量。另一方面，利用外置的BloomFilter过滤无效的缓存查询，加速数据包的转发速率。此外，该方案根据分组级别的热度统计来优化缓存决策，提高缓存整体性能。实验结果表明，提出的方案在服务器负载减少率，平均跳数减少率和平均缓存命中率等方面优于现有解决方案，并且显着提高了资源利用率。下一步将继续完善该方案，并将其部署在在实际的NDN 平台中，进行进一步测试和应用。

# 参考文献：

[1]Cisco.Cisco visual networking index:forecast and methodology， 2016- 2021 [EB/OL]. (2017）[2017-07-15].https://www. cisco. com/c/en/us/solutions/collateral/service-provider/visual-networking-indexvni/complete-white-paper-c11-481360.html   
[2]Wang Lan,Bayhan S,Kangasharju J. Optimal chunking and partial caching in information-centric networks [J].Elsevier Science Publishers B.V.2015, 61 (C): 48-57.   
[3]Jacobson V, Smetters D K,Thornton JD,et al. Networking named content [C]//Proc.of ACM CoNEXT.2009:1-12.   
[4]Koponen T,Chawla M,Chun B,et al.Adata-oriented (and beyond) network

architecture [C]//Proc.ofACM SIGCOMM.2007:181-192.   
[5]FP7 SAIL project [EB/OL]. htp://www.sail-project. eu/   
[6]Fotiou N,Nikander P,Trossen D,et al.Developing information networking further:from PSIRP to PURSUIT[C]//Proc of International Conference on Broadband Communications,Networks and Systems.Berlin: Springer, 2010: 1-13.   
[7]Chai WK,He Diliang,Psaras I,et al. Cache less for more in information centric networks [C]//Proc of NETWORKING.2012: 27-40.   
[8]Psaras I,Chai W K,Pavlou G.Probabilistic in-network caching for information-centric networks [C]//Proc of ACM SIGCOMM Workshop on ICN. New York: ACM Press,2012: 55-60.   
[9] Zhang Meng，Luo Hongbin， Zhang Hongke.A survey of caching mechanisms in information-centric networking [J].IEEE Communications Surveys & Tutorials,2015,17(3):1473-1499.   
[10] Bernardini C，Silverston T,Festor O.MPC:popularity-based caching strategy for content centric networks [C]// Proc.of IEEE International Conference on Communications.2013:3619-3623.   
[11] Wang Wei,Sun Yi, Guo Yang,et al.CRCache: exploiting the correlation between content popularity and network topology information for ICN caching [Cl//Proc.of IEEE International Conference on Communications. 2014:3191-3196.   
[12] Ren Jing,Qi Wen,Westphal C,et al. MAGIC: a distributed max-gain innetwork caching strategy in information-centric networks [C]// Proc ofIEEE INFOCOM.2014: 470-475.   
[13] Wu Haibo,Li Jun,Zhi Jiang.MBP:a max-benefit probability-based caching strategy in Information-Centric Networking [C]//Proc of IEEE International Conference on Communications.2015:5646-5651.   
[14] Hu Xiaoyan, Gong Jian, Cheng Guang. Enhancing in-network caching by coupling cache placement,replacement and location [C]// Proc of IEEE International Conference on Communications.2015:5672-5678.   
[15] Banerjee B, SeetharamA,Tellambura C.Greedy caching:a latency-aware caching strategy for information-centric networks [C]// Proc of IFIP Networking. 2017.   
[16] Thomas Y,Xylomenos G,Tsilopoulos C,et al.Object-oriented packet caching for ICN [C]//Proc of International Conference on InformationCentric Networking.2015: 89-98.   
[17] Wang Lan,Hoque A,Yi Cheng,et al. OSPFN: an OSPF based routing protocol for named data networking [R].University of Memphis and University of Arizona, 2012.   
[18] Hoque A,Amin S,Alyyan A,et al. NLSR: named-data link state routing protocol [C]// Proc of ACM SIGCOMM Workshop on Information-Centric Networking.New York: ACMPress,2013:15-20.   
[19] Afanasyev A,Moiseenko I, Zhang Lixia, ndnSIM: NDN simulator for NS3,NDN-0005 [R].NDN,2012.   
[20] Henderson TR,Roy S,Floyd S,et al.ns-3,project goals [C]//Proc of Workshop on ns-2: the IP Network Simulator.New York:ACMPress,2006.   
[21] Breslau L,Cao Pei,Fan Li,et al.Web caching and Zipf-like distributions: evidence and implications [C]// Proc of the 18th Joint Conference of the IEEE Computer and Communications Societies.Proceedings.2002:126- 134.   
[22] Barabasi A,AlbertR.Emergence of scaling in random networks [J]. Science, 1999,286 (5439): 509-512.   
[23] Watts D.J, Strogatz S.H. Collective dynamics of small world networks [J]. Letters to Nature,1998,393: 440-442.