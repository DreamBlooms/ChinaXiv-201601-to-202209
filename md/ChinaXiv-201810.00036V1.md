# 分布式SOM结合K-均值聚类的软件定义网络泛洪攻击检测方法\*

汪海涛1，余松森²

(1．广东科贸职业学院 信息与自动化学院，广州 510620;2.华南师范大学 软件学院，广东 佛山 528225)

摘要：针对软件定义网络(SDN）泛洪攻击导致的上层性能瓶颈和过载问题，提出一种分布式自组织映射（DSOM)结合K-均值聚类的网络流量攻击检测方法。首先，位于应用层的DSOM控制器将现有数据集发送给集成了DSOM扩展包的交换机，在每个交换机上分别训练DSOM映射；然后，在预定时间内合并DSOM映射；最后，DSOM控制器将合并后的DSOM映射发送到所有OpenFlow交换机，利用K-均值聚类完成最终的分类。实验结果表明，DSOM方案能够有效检测异常流量、解决瓶颈问题，相比传统方法具有一定的优势。此外，提出的方法提高了系统对攻击流量的反应速度，同时给网络系统带来较小的开销。

关键词：软件定义网络；泛洪攻击；分布式自组织映射；K-均值聚类；OpenFlow中图分类号：TP393.08 doi:10.3969/j.issn.1001-3695.2018.06.0401

# Software-defined network flooding attack detection method based on distributed SOM and K-means clustering

Wang Haitaol, yu Songsen2 (1.Collegeof Information&Automation GuangdongPolytechnicofScience&Trade,Guangzhou510620,China;2.Schoolof Software, South China Normal University,Foshan Guangdong 528225, China)

Abstract:Aimingat theproblemofperformance botleneck andoverload inupper layercausedbysoftware-defined network flooding attacks,this paper proposed a software-defined network floodingatack detectionmethod based on distributed SOM and $\mathbf { k }$ means clustering.The DSOMcontrolerat theapplication layer firstsentthe existing dataset tothe switch which hadthe DSOM extension package integratedand it trained the DSOM mappng on each switch.Then,it consolidated the DSOM mapping within apredetermined time.Finally, te DSOMcontrollersentte merged DSOM mapping toall OpenFlow switches and used $\mathbf { k }$ -means clustering to complete the final classification.Experimental results show that the DSOM scheme can ffectivelydetectabnormaltrafficandsolve botleneck problems,whichhascertainadvantagesover traditional methods.In addition,the proposed method improves theresponse speed ofthe systemto attck trafic andat thesame time itbrings less overhead to the network system.

Key Words: software-defined network; flooding attcks; distributed self-organizing map; K-means clustering; OpenFlow

# 0 引言

软件定义网络（software defined network，SDN）[1]是一种优秀的网络架构模型。在SDN中，控制层和数据层的分离为网络运营商在流量管理方面带来了巨大的好处。OpenFlow 协议[2]是 SDN 中的一个主要组件，它是 SDN 控制器和OpenFlow 交换机之间的通信者。SDN控制器使用OpenFlow协议，根据安全和路由策略等网络业务指令，配置和更新OpenFlow交换机内部的流表。

在OpenFlow交换机数量较多的大型网络中，由于安全服务和应用程序的资源分配，SDN控制器自然而然成为性能瓶颈。

另外，在流量大的情况下，数据层与控制层之间的通信通道可能也会成为瓶颈，使得延迟增加并且会阻碍到应用层的流量[3]。因此，许多研究人员为大型软件定义网络引入了多个控制器，比如谷歌的B4网络[4等。在遇到泛洪攻击或分布式拒绝服务（DDoS）攻击[5时，上述问题将成为大型 SDN架构的严重缺陷，它会发送极大量的网络流量到受害者系统，以便耗尽资源并降低公共服务的质量。因此，位于SDN架构上层的安全应用需要处理大量的流量信息，由于资源枯竭和性能瓶颈，系统可能会崩溃。因此，在大型 SDN模型中，高流量情况下，为了降低运行在上层的安全应用的巨大性能压力，数据层需要支持更高级的功能。

为解决以上问题，提高大型SDN模型的鲁棒性，本文提出了一种基于聚类算法和分布式自组织映射的软件定义网络系统。在这个提出的方案中引入聚类算法和DSOM机制，并让安全模块分布在OpenFlow交换机上，而不是分布在控制层或应用层，这些模块由分布式系统控制器控制，在SDN 架构的应用层作为安全应用运行。此外，在OpenvSwitch中实现了扩展模块，允许连接到OpenvSwitch的默认代理，以实现统计、修改规则以及与分布式系统控制器进行通信的目的

# 1 相关工作

# 1.1软件定义网络和 OpenFlow 协议

软件定义网络（SDN）为未来提供了一个有前景的网络架构。在该网络中，位于SDN控制器中的控制层与数据层是分离的。运行在应用层上的应用可以提供复杂的网络服务和功能。数据层处理硬件级别，并侧重于基于控制器配置的数据包处理。控制层（SDN控制器）和数据层（OpenFlow交换机）之间的通信由OpenFlow 协议定义。在交换消息之前，OpenFlow 交换机必须建立到SDN控制器的安全连接以进行认证。该协议使控制器能够访问OpenFlow 交换机中的流表，以使用安全连接进行控制、配置和统计[7,8]。

# 1.2K-均值聚类

K-均值聚类[9,10]属于典型的启发式的算法，在聚类过程中，将 $n$ 个数据对象分成 $\boldsymbol { K }$ 个簇，使得每个簇内的对象具有高度相似性，而不同簇之间具有低度相似性。首先，算法从所有 $\mathbf { \Omega } _ { n }$ 个对象中选出 $K$ 个，以此为初始聚类中心，其余对象以自身到不同聚类中心的距离为标准，加入到最相近的类中。然后，算法更新各个类的中心，不断重复上述过程，直到得出理想的簇集。

# 1.3 自组织映射算法

自组织映射（Self-Organization Mapping，SOM）[11]是人工神经网络中的无监督学习方案之一。该算法将高维输入空间转换为低维表示，称为SOM映射。SOM根据两种主要模式（训练和映射）分类或检测新的输入向量。训练过程使用输入样本建立、重新组织映射，而映射过程通过在映射中找到其获胜的神经元或节点，自动分类新的输入向量。

定义以下参数：

a） $N$ 为迭代次数或训练样本 $[ \stackrel {  } { x } _ { 1 } , . . . , \stackrel {  } { x _ { N } } ]$ 数量。

b）映射有 $s$ 个神经元，每个神经元由一个向量 $W$ 组成，$W$ 由 $w$ 个权重值组成。

c） $R$ 是矩形映射的半径，其定义为：

$$
R = \frac { \operatorname* { m a x } ( M a p W i d t h , M a p H e i g h t ) } { 2 }
$$

d） $\lambda$ 是一个时间常数，计算公式为：

$$
\lambda = { \frac { N } { \log ( R ) } }
$$

e） $\sigma ( t )$ 是获胜神经元（最佳匹配单元）的近邻半径，并随着时间的推移逐渐减小。假设近邻保持以同一个神经元为中心，实际上最佳匹配单元将根据下面的步骤b)中的计算公式来移动。在算法的第 $\mathbf { \Phi } _ { t }$ 次迭代中， $\sigma ( t )$ 计算公式为

$$
N \sigma ( t ) = R \times \exp \Biggl ( - \frac { t ^ { 2 } } { \lambda } \Biggr ) , t = 1 , . . . , N
$$

自组织映射算法的主要步骤如下：

a)初始化。用随机值或固定值初始化神经元的 $m$ 维权重：$W _ { i } = [ W _ { i 1 } , W _ { i 2 } , W _ { i 3 } , . . . , W _ { i w } ]$ ，其中 $1 \leq i \leq S$ 。

b）选择最佳匹配单元（BMU）。输入向量x =[kl,Xk2,Xk3,Xk]，通过计算输入向量到所有神经元i的欧几里得距离 $D _ { i s t }$ ，从而把输入向量馈送到映射中。

$$
D _ { i s t } = \sqrt { \sum _ { j = 1 } ^ { w } \bigl ( x _ { k j } - W _ { i j } \bigr ) ^ { 2 } }
$$

为输入向量 $x _ { k }$ 选择距离 $D _ { i s t }$ 最小的神经元作为最佳匹配单元。

c）更新BMU的近邻权重：按照等式（3）计算BMU的近邻。之后，根据以下等式调整这些近邻的权重，进行下一次迭代，以使它们更接近输入向量。

$$
W ( t + 1 ) = W ( t ) + L ( t ) * \Theta ( t ) * { \big ( } x _ { k } ( t ) - W ( t ) { \big ) }
$$

其中: $L ( t )$ 是学习率，随着时间的推移也会衰减，计算公式为

$$
L ( t ) = L _ { 0 } * \exp \biggl ( - \frac { t } { \lambda } \biggr )
$$

$\Omega ( t )$ 是邻近神经元与 BMU 的距离对其学习的影响量,定义为

$$
\Omega ( t ) = \exp \left( - \frac { D _ { i s t } ^ { 2 } } { 2 \sigma ^ { 2 } ( t ) } \right)
$$

d）循环：重复步骤（b）c)，直到没有更多的输入向量馈送到映射。

# 1.4SDN 视角下的泛洪攻击

在传统的网络架构中，泛洪攻击一般分为两类：带宽耗尽攻击和资源耗尽攻击。在带宽耗尽攻击中，攻击者往往用不受欢迎的流量淹没受害者网络，目的是耗尽受害者网络的带宽。这导致正常流量无法正常访问受害者系统，如ICMP泛洪、UDP泛洪或Smurf和Fraggle攻击等。在资源耗尽攻击中，攻击者希望将异常IP数据包或误用的网络协议数据包发送给受害者。因此，每当开放连接的数量达到系统阈值时，受害者网络就会遭受资源耗尽，并可能停止工作[12]。

# 2 分布式网络流量攻击检测方法

# 2.1系统概述

在大规模软件定义网络中，为了处理网络系统受到泛洪攻击时的性能瓶颈问题，引入了基于聚类算法的分布式SDN系统。图1显示了所提出的系统概览，所有交换机都在SDN控制

器的控制下运行。在应用层中，放置一个叫做DSOM控制器的应用程序来控制DSOM操作。

![](images/e32a5ffc9069ee2c4ed61dc82ce1c6d67a831d532eff351c41fc6fdb00693514.jpg)  
图1提出的分布式SOM系统

# 2.2系统工作流程

引入的DSOM系统设计有四个主要过程：

a）初始化。位于应用层的DSOM控制器将现成的数据集发送给集成了DSOM扩展包的交换机。在每个交换机上，使用从控制器接收到的数据集来训练DSOM映射。

b）合并DSOM。此阶段负责在预定时间内合并 $\mathrm { D S O M _ { \circ } }$ DSOM控制器从OpenFlow交换机收集DSOM映射，生成合并的 SOM映射，表示为

$$
M e r g e d M a p = \sum _ { j = 1 } ^ { j = n } \frac { \chi _ { j } } { \displaystyle \sum _ { i = 1 } ^ { j } \chi _ { i } } \times M a p D S O M _ { j }
$$

其中： $\chi _ { j }$ 是第 $j$ 个 DSOM 的训练输入样本总数， $M a p D S O M _ { j }$ 是第 $j$ 个DSOM的映射。

c）更新。DSOM控制器将合并的SOM映射发送到所有的OpenFlow 交换机。合并的 SOM 映射替换 $D S O M _ { j }$ 映射，以在交换机上继续分类过程。

d)分类。 $D S O M _ { j }$ 根据他们的神经元对输入进行计算并给出结果，然后将这些结果发送到DSOM控制器作进一步的决定。

# 2.3 DSOM交换机层

在交换机层，为OpenFlow交换机添加了一些附加模块，称为DSOM扩展模块：流收集器、特征提取器、训练数据库、DSOM映射、快速策略实施和DSOM交换机代理。图2显示了这些模块是如何连接的，以及如何与OpenFlow 交换机的默认模块一起工作。DSOM交换机代理充当本地交换机层DSOM系统的核心，并控制DSOM映射过程的训练和更新，将分类结果发送到快速策略实施和DSOM控制器。

在初始化步骤中，从DSOM控制器发送的训练数据集通过OpenFlow交换机的OpenFlow通道到达DSOM交换机代理。然后转发到训练数据库，并且成为DSOM映射的训练输入。当训练过程完成后，DSOM交换机代理向DSOM映射、特征提取器以及流收集器发送启动命令，以启动这些模块。如该方案的工作原理一样，流量收集器周期性地向交换机数据层发送统计消息，以在特征提取阶段获取单独的流量信息，该阶段侧重于通过交换机的每个用户的特征提取。此外，由特征提取器的输出更新训练数据库，并且在由DSOM交换机代理设置的时间段内再次调用训练DSOM映射过程。这种训练使DSOM映射能够适应即将到来的流量，并提高了每个本地DSOM交换机的分类性能。

![](images/729133853bbec72a83ca4208136ed55f4ebf315c1cd4d250c59f34ef2d9729a8.jpg)  
OpenFlow交换机  
图2DSOM交换机层

让更详细地了解特征提取器，以了解在DSOM映射的输入中使用了多少特征。对于每种类型的网络流量，这些特征可以是多样的；但是，正如前文所述，从SDN角度考虑普通的泛洪攻击，并将其分为两种主要类型：带宽耗尽攻击和资源耗尽攻击。因此，本文工作主要集中在两种类型的泛洪攻击，的方法是在预定的时间内观察每个用户。DSOM映射与单个SOM执行相同的操作。它确定哪些用户是正常的用户哪些用户是异常的用户。为了作出最后的决定，将K-均值聚类算法应用到系统中，将 $n$ 个模式划分为 $K$ 个聚类。在攻击用户被明确定义之后，DSOM映射将用户信息发送到DSOM交换机代理，然后这个代理通过OpenFlow通道将这些数据传送到快速策略实施和DSOM控制器。在交换机上放置快速策略实施模块的目的是，通过在流表中设置直接的规则来对攻击流量进行快速反应，而位于DSOM控制器中的策略检查模块则负责验证规则，并且如果需要的话它可以覆盖规则。

# 3 实验

# 3.1数据集和攻击模拟器

# 3.1.1训练和测试数据集

从CAIDA[13]、NSL-KDD[14]和DARPA[15]这三个数据集中分析和构建了一套SOM训练样本和测试样本。这些数据集的简短描述总结如下：

CAIDA数据集可用于Web、FTP、Ping等多种不同类型流量的混合研究。从表1的描述来看，通常情况下，TCP和ICMP协议构成网络流量的比例最高。

表1以字节为单位统计的CAIDA数据集  

<html><body><table><tr><td>流量状态</td><td>TCP (%)</td><td>ICMP (%)</td><td>其他 (%)</td></tr><tr><td>正常</td><td>88.45</td><td>6.0</td><td>5.55</td></tr><tr><td>攻击型</td><td>7.58</td><td>91.25</td><td>1.17</td></tr></table></body></html>

对于NSL-KDD 数据集，只研究DoS攻击。因此，只考虑使用DoS样本来训练和测试所提出的系统，如表2所示。

表2NSL-KDD 数据集中的Dos攻击  

<html><body><table><tr><td>Dos 攻击类型</td><td>训练模式</td><td>测试模式</td><td>特征数量</td></tr><tr><td>back</td><td></td><td></td><td></td></tr><tr><td>land</td><td></td><td></td><td></td></tr><tr><td>neptune</td><td></td><td></td><td></td></tr><tr><td>pod</td><td>45927</td><td>7458</td><td>41</td></tr><tr><td>smurf</td><td></td><td></td><td></td></tr><tr><td>teardrop</td><td></td><td></td><td></td></tr></table></body></html>

从三个数据集的pcap文件中提取并随机选择样本（包括正常和攻击模式）进行测试。

# 3.1.2攻击模拟器

利用BoNeSi进行测试，BoNeSi不仅可以模拟僵尸网络的流量，还可以通过定义的僵尸网络向目标网络或指定的IP地址生成TCP、ICMP或UDP泛洪攻击。

# 3.2SDN中的系统设置

实验测试的网络拓扑连接如图3所示，使用一个控制器（Controller）、四个与DSOM模块集成的OpenvSwitch（DSOMOpenvSwitch）、一个网络服务器以及三个主机（h1，h2，h3，h4）作为流量发生器。表3给出了DSOM映射的详细参数。另外，由于大部分用户的访问是正常、合法的，本文设置聚类中心的数目为4，以便构成正常用户的集合。

![](images/bcb7aeac5789d341abdf0358022a447fbb423493c8c880b647746f70646a8d33.jpg)

图3DSOM实现的拓扑结构  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>半径</td><td>（宽度+高度）/2</td></tr><tr><td>学习速率</td><td>0.1</td></tr><tr><td>神经元数量</td><td>400，900，1600</td></tr><tr><td>输入维度</td><td>6</td></tr><tr><td>输出维度</td><td>2</td></tr></table></body></html>

# 3.3系统测试

# 3.3.1性能瓶颈测试

为了评估提出的系统在性能瓶颈方面与单个SOM相比取得的效果，建立了如图3所示的系统，并进行了两个测试实例：单个SOM和DSOM系统。在第一个测试场景中，在控制器中实现了一个SOM 模块，其中控制器包含四个功能：流量收集器、特征提取器、SOM映射、策略实施。同时，在所提出的系统中，只将DSOM控制器模块作为SDN控制器中的应用运行，其他模块在交换机中实现。在这两个实例中，使用了总共12000个样本的同一个数据集来训练 SOM 映射，其中从每个数据集随机提取了4000个模式。然后使用BoNeSi工具生成两个流量级别（50Mbps和100Mbps）来攻击网络服务器，并在两种情况下测量SDN控制器的CPU利用率。

# 3.3.2SOM性能测试

对于介绍的解决方案中SOM映射的性能检测，进行了以下设置实例来评估DSOM系统，并证明所提出的方法与传统的SOM机制具有相同的性能：

单一SOM：一个单一的 SOM，四个与第3.3.1节中描述的相同模块。控制器从OpenvSwitch收集流量信息，然后检测攻击用户。如果检测到异常用户，策略实施会立即将规则应用于OpenvSwitch。

DSOM1：1：1：这个情况是在提出的DSOM系统中进行的，初始化过程中训练数据集的比例是1：1：1。

·DSOM1：2：3：这种情况与前一情况相同，只是初始化过程中训练数据集的比例为1：2：3。

在这个实验中，分别对每种情况进行以下测试：

如表4所示，SOM映射初始化和训练过程在单独的数据集（CAIDA，NSL-KDD和DARPA）上进行。然后，通过来自训练数据集的5次交叉验证执行测试程序，使用来自BoNeSiDDoS模拟器的流量进行测试。

通过随机合并三个相同的数据集而产生的混合数据集对SOM映射进行初始化和训练。并且，测试过程也由5次交叉验证以及BoNeSiDDoS模拟器执行。

对SOM映射中不同值的神经元数量：400,900和1600，进行了多次测试过程。

表3SOM映射参数  
表4用于SOM检测性能测试的训练和测试样本  

<html><body><table><tr><td rowspan="2">实例 初始化 训练</td><td>单个SOM</td><td>DSOM1:1:1</td><td>DSOM1:2:3</td><td rowspan="2"></td></tr><tr><td>4000 6000</td><td>4000:4000:4000</td><td>4000:4000:4000</td></tr><tr><td colspan="3">CAIDA</td><td>2000:2000:2000</td><td>1000:2000:3000</td></tr><tr><td rowspan="6">测试</td><td>数据集 NSL-KDD</td><td>30000</td><td>30000</td><td>30000</td></tr><tr><td>数据集</td><td>30000</td><td>30000</td><td>30000</td></tr><tr><td>DARPA 数据集</td><td>30000</td><td>30000</td><td>30000</td></tr><tr><td>混合 数据集</td><td>30000</td><td>30000</td><td>30000</td></tr><tr><td>BoNeSi 工具</td><td>6000</td><td>6000</td><td>6000</td></tr></table></body></html>

# 4 性能评估

# 4.1处理性能瓶颈

图4所示为SDN控制器的CPU利用率，从图中可以看出，在测试实例之间存在显著差异，单个SOM机制总是消耗SDN控制器更多CPU资源，而DSOM系统则使控制器系统消耗的CPU 资源处于稳定水平。在产生流量是50Mbps 的实例中，在攻击发起后仅12秒和33秒，CPU利用率的值就达到 $40 \%$ 和$60 \%$ 。同时，DSOM解决方案在所有测试时间内仅占用约 $23 \%$ 的CPU资源。在100Mbps的情况下也可以看出同样的差别：单个SOM方案在仅仅10秒之后SDN控制器的CPU利用率就达到了 $60 \%$ ，并且在测试结束之前一直在这个值上下波动。相比之下，DSOM 解决方案在CPU的占用方面一直保持较低水平。

![](images/07a975510116ec487a839c2156a07c02cc3b1abcb01d6e9127f2989f66c2db7c.jpg)  
图4SDN控制器的CPU 消耗  
图5在三种不同神经元数量、四个不同数据集情况下，SOM映射的检测率

从以上结果可以看出，DSOM系统是完全胜过单一SOM方案的很好的一个解决方案。在单个SOM情况下，为了获取流量信息，控制器必须频繁地向交换机发送信息，然后将其转发到下一个模块，以便进一步处理。而且，同时处理来自所有边缘交换机的流量信息对于模块来说是一项繁重的工作。而DSOM系统将流量处理任务委派给边缘交换机以减少工作量，仅在策略检查时处理少量信息。另外，每个边缘交换机只处理从外部网络进入其端口的流量。因此，与单个SOM方案相比，DSOM交换机代理的压力并不大。

# 4.2 SOM性能评估

在评估 DSOM方法的性能之前，本文作出如下定义：TP表示攻击用户被分类为攻击用户的概率， $\ d _ { T N }$ 表示正常用户被认为是正常用户的概率， $F P$ 表示异常用户被认为是正常用户的概率， $F N$ 表示正常用户被认定为攻击用户的概率。

# 4.2.1检测率

为了评估所提出的DSOM系统的效率，考虑了一个关键的标准，即检测率。检测率计算如下：

$$
D R = { \frac { T P } { T P + F N } }
$$

图5显示了对不同的四个数据集，在三种情况下SOM映射的检测率。从图中可以看出，在相同数量的神经元下，三种情况在所有四个数据集中只有轻微的差异。这是因为使用均值聚类算法来区分正常用户和异常用户，并使用 $k$ 倍交叉验证技术来评估数据集本身的检测率。然而，即使使用攻击工具来产生流量，由于训练样本数量很大，训练好的 SOM也可以很容易地检测到攻击用户。此外，这些实验还表明，如果SOM映射具有更多的神经元，这意味着检测性能更高，并且所提出的DSOM和单个SOM系统相比，没有太大差异。

400个神经单元 98.2   
97.6 98.0 97.4 A 1 二   
例   
比 97.2 山 97.0 96.8 96.6 CAIDA NSL-KDD DARPA 混合 ■SingleSOM ■DSOM 1:1:1 ■DSOM 1:2:3 900个神经单元 99.0   
8 50 山川 97.5   
5 97.0 1 96.5 96.0 CAIDA NSL-KDD DAR PA 混合 ■SingleSOM ■DSOM 1:1:1 ■DSOM 1:2:3 1600个神经单元 99.6 99.4 ldh" 99.2 99.0   
98.8 98.6   
例 比 98.4 98.2 98.0 97.8 97.6 ■SingleSOM ■DSOM 1:1:1 ■DSOM 1:2:3

# 4.2.2准确性

准确度[1]即 SOM映射作出决定的准确程度，计算公式为：

$$
A c c u r a c y = { \frac { T P + T N } { T P + T N + F P + F N } }
$$

图6显示了对不同的四个数据集，在三种情况下SOM映射的准确度，三个实验的准确性均比较高。在400个神经元的情况下，最低的准确率约为 $9 6 . 9 \%$ ，而在900和1600个神经元的情况下，它的准确率都在 $97 \%$ 以上。原因在于，当SOM映射的学习样本数目增加时，对用户作出决定的准确性也更准确。而且，当SOM映射达到可以作出完全准确决定的阈值时，神经元的数量对准确性的影响不大。这就是为什么在精度方面这些测试之间只有微小的差别。

# 4.2.3系统开销

还通过测量两个系统的处理时间和分类时间，来评估DSOM机制和单个SOM的性能。对于DSOM系统，假设通过数据包连接传输数据所需的时间仅为几毫秒，则处理时间主要是通过两个过程的和来计算：第一个是在OpenvSwitch上训练DSOM映射，它占用了最多的时间，第二是在DSOM控制器上的合并时间。同时，单个SOM的处理时间只是其训练时间。用输入集训练DSOM和单个SOM映射，如表5所示。

400个神经单元98.498.298.097.8  
例97.2 97.4 比97.0 小 1 1 196.896.696.496.2CAIDA NSL-KDD DARPA 混合■SingleSOM ■DSOM 1:1:1 ■DSOM 1:2:3900个神经单元98.498.2  
897.8 97.6 I 三 h  
比97.497.297.0CAIDA NSL-KDD DARPA 混合■SingleSOM ■DSOM 1:1:1 ■DSOM 1:2:31600个神经单元99.599.0  
75 川 川96.5CAIDA NSL-KDD DAR PA 混合■SingleSOM ■DSOM 1:1:1 ■ DSOM 1:2:3

图6在三种不同神经元数量、四个不同数据集情况下，SOM映射的准确性

表5中的结果表明，如果在SOM映射中使用更多数量的神经元，则DSOM系统的处理时间比单个SOM更快。因为OpenvSwitch的DSOM使用较小的数据集进行训练，而单个SOM总是需要更大的输入数据集来训练其映射。关于分类时间，三种情况大致相等，并且与神经元数量成正比增加。这可以通过对控制器和OpenvSwitch使用相同的配置来解释；因此，这三种情况下的CPU处理时间没有太大的差别。

表5处理时间和分类时间  

<html><body><table><tr><td>神经元数量</td><td>实例</td><td>处理（s)</td><td>分类（ms)</td></tr><tr><td rowspan="3">400</td><td>单个 SOM</td><td>10.14</td><td>0.956</td></tr><tr><td>DSOM 1:1:1</td><td>9.16</td><td>0.932</td></tr><tr><td>DSOM 1:2:3</td><td>9.81</td><td>0.895</td></tr><tr><td rowspan="3">900</td><td>单个 SOM</td><td>25.95</td><td>1.82</td></tr><tr><td>DSOM 1:1:1</td><td>15.71</td><td>1.81</td></tr><tr><td>DSOM 1:2:3</td><td>18.04</td><td>1.70</td></tr><tr><td rowspan="3">1600</td><td>单个SOM</td><td>37.77</td><td>4.55</td></tr><tr><td>DSOM 1:1:1</td><td>23.99</td><td>4.03</td></tr><tr><td>DSOM1:2:3</td><td>28.72</td><td>4.45</td></tr></table></body></html>

根据以上实验结果，可以评估软件定义网络中DSOM系统

的性能，并且与单个SOM进行比较。首先，在处理性能瓶颈问题和方面，DSOM系统是一个很好的解决方案，完全胜过单一SOM方案。而且，这两个系统对异常流量的检测率和准确率方面都表现出优异的性能。在使系统准备好分类过程的开销方面，所提出的DSOM比使用单个SOM要少。总的来说，软件定义网络中的DSOM系统能够有效地解决大型网络中泛洪攻击下的瓶颈问题，与传统方法相比具有一定的优势。

# 5 结束语

本文提出了一种K-均值聚类算法和分布式自组织映射系统，通过使用分布式系统而不是集中式的系统对网络数据进行分析，处理由于大型软件定义网络中上层泛洪攻击引起的聚合而导致的瓶颈问题。实验结果表明，在处理性能瓶颈方面，本文所提出的方法完全胜过传统的方法。此外，实验结果不但显示了的机制与单个SOM系统的性能相同，而且表明了DSOM系统的开销要优于单个SOM。

# 参考文献：

[1]胡涛，张建辉，毛明.SDN中基于迁移优化的控制器负载均衡策略[J]. 计算机应用研究,2018,35(2):559-563.(Hu Tao,Zhang Jianhui,Mao Ming. Controller load balancing strategy based on migration optimizing in SDN[J].Application Research of Computers,2018,35 (2): 559-563.)   
[2]邱欣逸，李俊，周建二，等.OpenFlow 中基于精确时间戳的延迟测量方 法[J].通信学报,2017,38(11):178-187.(Qiu Xinyi,LiJun,Zhou Jianer, et al.New delay measurement method based on accurate timestamp in OpenFlow[J]. Journal on Communications,2017,38(11):178-187.)   
[3]Wang Haopei, Xu Lei, Gu Guofei. FloodGuard: A DoS Attck Prevention Extension in Software-Defined Networks [C]// Proc of International Conference on Dependable Systems and Networks.Washington DC: IEEE Computer Society,2015: 239-250.   
[4]Jain S,Kumar A,Mandal S,et al. B4: experience with a globally-deployed software defined wan [J]. Computer Communication Review,2013,43 (4): 3-14.   
[5]王启林，李小鹏，郁滨，等．基于连接认证的低功耗蓝牙泛洪攻击防御 方案[J].计算机应用研究，2017,34(2):499-502.(WangQilin,Li Xiaopeng,Yu Bin,et al. Defense scheme of flooding attcks in bluetooth low energy based on connection authentication [J].Application Research of Computers,2017,34 (2): 499-502.)   
[6]张永铮，肖军，云晓春，等.DDoS攻击检测和控制方法[J]．软件学报, 2012,23 (8):2058-2072.(Zhang Yongzheng, Xiao Jun,Yun Xiaochun,et al. DDoS attacks detection and Control mechanisms [J]. Journal of Software, 2012,23 (8): 2058-2072.)   
[7]Lara A,Kolasani A, Ramamurthy B. Network innovation using openflow: a survey[J]. IEEE Communications Surveys & Tutorials,2014,16(1): 493- 512.   
[8]Jafarian J H,Al-Shaer E,Duan Qi. Openflow random host mutation: transparent moving target defense using software defined networking $[ \mathrm { C } ] / \AA$ Proc of Workshop on Hot Topics in Software Defined Networks.New York: ACMPress,2012:127-132. [9]Sulaiman S N,Nor Ashidi Mat Isa.Adaptive fuzzy-K-means clustering algorithm for image segmentation [J].IEEE Trans on Consumer Electronics,   
2010,56(4):2661-2668. [10]张顺龙，库涛，周浩.针对多聚类中心大数据集的加速K-means 聚类算 法[J].计算机应用研究,2016,33(2):413-416.(Zhang Shunlong,Ku Tao, Zhou Hao.Accelerate K-means for multi-center clustering of big datasets [J].Application Research of Computers,2016,33 (2): 413-416.) [11]吴怡，杨琼，吴庆祥，等．基于自组织映射神经网络的VANET 组网算 法[J].通信学报，2011,32(12):136-145.(Wu Yi,Yang Qiong,Wu Qingxiang,et al.Networking algorithm based on self-organizing map neural network for VANET[J]. Journal on Communications,2011,32(12):136-   
145.) [12]章曙光，周学海，杨峰，等．无线传感器网络中基于邻居节点信息的溯

源追踪策略[J].小型微型计算机系统,2015,36(3):483-487.(Zhang

Shuguang,Zhou Xuehai, Yang Feng,et al. Traceback Mechanism Based on Neighbor Information in Wireless Sensor Networks[J]. Journal of Chinese Computer Systems,2015,36(3): 483-487.)   
[13] Wen Yuhao,Wang Han,Chen Zhen,et al. MASC:A bitmap index encoding algorithm for fast data retrieval [C]//Proc of IEEE International Conference on Communications.2016:1-6.   
[14]KumarShrivas A,DewanganAK.An Ensemble Model for Classification of Attacks with Feature Selection based on KDD99 and NSL-KDD Data Set [J].International Journal of Computer Applications,2014,99 (15): 8-13.   
[15]Moustafa N,Slay J.Creating novel features to anomaly network detection using DARPA-2oo9 data set [C]//Proc of European Conference on Cyber Warfare and Security Eccws.2015:23-24.   
[16]叶剑锋，王化明.AdaBoost 检测结合 SOM的自动人脸识别方法[J].哈 尔滨工程大学学报,2018,39(1):129-134.(Ye Jianfeng,Wang Huaming. An automatic face recognition method using AdaBoost detection and SOM [J].Journal of Harbin Engineering University,2018,39(1):129-134.)