# 基于马尔可夫链的802.15.4网络防丢包信道访问机制研究

程宏斌1，乐德广1，王晓喃1，王海军²，孙霞‘(1．常熟理工学院 计算机科学与工程学院，江苏 常熟 215500;2.湖北第二师范学院 计算机学院，武汉 430205)

摘要：为了降低802.15.4MAC 层数据帧丢包率，在分析丢包率的原因基础上，提出了一种基于Mark0V链的信道竞争机制模型。通过对网络发送、退避和信道检测状态的稳态概率进行数学推导，研究了信道碰撞和数据帧的丢包率分析式；最后研究了参数数据包到达速率、节点数量、误码率、后退指数、后退等待次数对碰撞概率和丢包率的影响。实验结果表明，与节点无休眠态的802.15.4网络相比，节点丢包率平均降低了 $23 . 7 \%$ ，模型较好地描述了提出的MAC层信道访问机制，合理的网络参数设置能够优化数据帧丢包率,研究结果对无线传感网的应用提供可靠传输优化参考。

关键词：802.15.4媒体接入控制；马尔可夫链；碰撞概率；丢包率中图分类号：TP393.03 doi:10.3969/j.issn.1001-3695.2017.10.0954

# Research on channel access mechanism of anti packet loss for 802.15.4 network based on Markov chain

Cheng Hongbin1,Le Deguangl,Wang Xiaonan],Wang Haijun², Sun Xial (1.SchoolofomuterSience&Engineeing,ChangshuIstituteofTehnolgy,ChangshuJiangsu2550,Chna;2hool ofComputerHubei University of Education,Wuhan 430205,China)

Abstract: In order toreduce the packet lost rate in 8O2.15.4MAC layer,this paper raised a model of channel competition mechanismbasedon Markovchain byanalyzingthereasonofpacketlossrate.Then,throught the mathematicalderivationsof thesteady-stateprobabilityonthe network transmission,backofandthechanneldetectionstatebasedonthe modelofchael access,thispaperdiscussd theformulasofchannelcollsionandtheframepacketlostrate.Finallythis paperstudiedthempact of protocolparameterssuchaspacketarrivalrate,thenumberofodes,biterorrate,backoffexponent,andnumberofacoffs on the collsionprobabilityandthe packetlostrate.Experimentalresultsshowthat,compared with8O2.15.4network without node sleep state, the packet lost rate was reduced by $23 . 7 \%$ . And the model describes the MAC layer channel access mechanism verywell,andreasonable settingsforparameterscouldoptimize theframepacketlostrate.Theresearchoutcomecould provide reference for the reliable transmission optimization in the practical application of wireless sensor network.

Key Words:802.15.4 MAC; Markov chain; collision probability; packet lost rate

# 0 引言

无线传感网是一种低功耗、短距离通信的自组织网络，而作为无线传感网媒体接入控制（mediaaccesscontrol，MAC）层规范的IEEE802.15.4协议是一个低成本、低复杂度和低功耗的标准，它定义了无线传感网的MAC层和PHY层规范，关于其MAC层的研究受到业界的广泛关注，特别是采用Markov 链等数学建模方法进行协议的性能优化成为一个研究热点[1\~4]。由于网络中的节点使用分时共享的时隙载波监听多址接入/冲突避免（carrier sense multiple access with collision avoid, CSMA/CA算法竞争访问信道，所以MAC层信道丢包现象成为802.15.4网络需要解决的重要问题之一。

文献[1]中针对802.15.4协议MAC层信道接入机制建模，然后研究了能耗和吞吐量等网络性能，但没有深入描述节点退避机制。文献[2]考虑了节点空闲状态，并对信道竞争机制建模，但没有考虑节点的睡眠态，对协议性能分析缺乏准确性。文献[3]没有全面分析超帧结构，也没有考虑节点的睡眠期，对数据帧平均服务时间等性能分析繁琐。文献[4]采用占空比自适应机制优化网络的生存周期，但没有均衡多种协议参数的影响。文献[5]分析在瑞利衰落信道下无线局域网MAC层的丢包率性能并研究了分组长度和调制方式对丢包率的影响。文献[6]对无线传感网络MAC层碰撞问题和丢包率进行数学分析，但是其对节点发送数据帧概率的分析采用简单估计，不能够精确描述节点的各种状态的特点，也没有详细研究协议参数如负载长度、误码率和退避窗口对碰撞概率和丢包率的影响。文献[7]通过非线性检验方法研究得出不同实验环境下无线传感器网络中发送数据速率和丢包率均具有均衡关系，且该关系具有明显的非线性特征，但是其研究方法不能对无线传感网MAC协议进行准确的数学分析。文献[8]通过Markov建模的方法分析了单跳通信模式下的802.15.4MAC层的冲突概率，但是并没有详细研究丢包率问题。

基于上述研究基础，本文通过对802.15.4MAC协议的关键算法分析，精确描述节点在信道访问期间的各种状态及其特点，提出一种基于马尔可夫链的802.15.4协议信道访问机制模型，基于该模型对节点碰撞问题和丢包性能进行详细分析。

# 1 丢包率

IEEE802.15.4网络中的节点使用直流电池电源,所以能耗优化问题成为802.15.4网络的重要研究热点。造成网络节点耗能的原因很多，如丢包、重传、空闲侦听等。与大多数MAC层协议一样，数据帧碰撞严重影响系统整体性能，它可能增大节点能量的浪费，降低吞吐量，增大数据帧丢包率，所以降低MAC层数据帧碰撞和丢包率成为改善协议能耗性能的一个重要的措施。相对于有线信道，无线信道的丢包现象更严重，而碰撞是造成丢包的一个非常重要的因素。但是碰撞现象在IEEE802.15.4网络中是不可避免的，因为802.15.4MAC使用CSMA/CA随机访问机制竞争接入信道时，节点使用的无线信道是共享的，且节点在发送信号的同时无法侦听信道，从而造成数据帧冲突的发生。一般数据帧碰撞发生在两个或两个以上的节点同时进入信道监测状态时，多个节点检测信道时两次监测CCA后均发现信道处于空闲,之后节点就同时开始发送数据帧,多个数据帧到达目的节点时将会发生碰撞。

针对IEEE802.15.4协议，本文研究分析参数PER和碰撞率、误码率、节点数、minBE、NB对丢包率的影响。通过优化网络主要参数设置来降低碰撞概率，从而进一步降低网络丢包率，改善和均衡网络的主要性能。

# 2 MAC协议建模

802.15.4协议主要应用于数据量少和速率低的应用环境，网络一般处于非饱和负载的情形。基于这种特点可以适当调整没有成功竞争信道的节点的状态，以便改善网络冲突和丢包的问题。本文对支持信标使能的802.15.4MAC层协议进行研究，网络所有节点通过超帧进行定时，以便与协调器保持同步。超帧由活跃期与睡眠期组成，而活跃期又由信标时间和竞争期组成，竞争期又由后退期和数据发送期组成。所有节点按照时隙CSMA/CA算法竞争信道，从而实现信道的分时共享。基于超帧结构的精确设定，节点能够在下述条件下进入睡眠期：a)竞争期内节点等待了最大的后退次数之后没有成功进入发送数据期;b)竞争期内节点负载为空;c)超帧睡眠期时隙到来之后[9\~I1]。

设802.15.4网络所有节点的非饱和负载服从速率为λ的泊松过程，而且各个节点负载到达过程互相独立，所有节点按照时隙CSMA/CA算法访问信道的动态随机过程正好符合Markov链中分析对象是离散状态空间的特点，所以能够基于Markov理论对节点在信道中的动态状态变化过程进行建模，通过该模型对802.15.4网络MAC层的相关性能进行研究。模型如图1所示。

![](images/55d8d9033241b089c568e5ff11b40a6d941ab79cb502cb603213702771472120.jpg)  
图1节点状态变换模型

在模型中，A表示节点检查信道的状态，S表示节点接入信道成功后发送数据状态，DO表示节点睡眠状态。 $\mathbf { R } _ { \mathrm { i , k } }$ 表示节点第 $i$ 次信道接入失败后第 $k$ 个时隙等待状态（ $i \in [ 0 , \ N B ]$ ，$k \in [ 0 , W _ { i - 1 } ] \mathrm { ~ , ~ }$ ）。 $N B$ （numberofbackoff）是最大的后退次数。节点初始后退时的等待时间 $W _ { 0 }$ 为 $2 ^ { m i n B E }$ ，节点第 $i$ 次退避时的等待时间 $W _ { i } { = } \ W _ { 0 } 2 ^ { \mathrm { i } }$ ， $m a x B E - m i n B E \equiv i \equiv m a x B E$ 。 $B E$ （backoffexponent）是后退指数，其最大和最小值用maxBE和minBE表示。 $s$ 和 $t$ 分别为节点在 $\mathbf { A } _ { \mathrm { i } , 1 }$ 和 $\mathbf { A } _ { \mathrm { i } , 2 }$ 这两次信道检查后没有成功的概率。 $g _ { 1 }$ 表示节点完成一次传输后负载为空的概率， $g _ { 2 }$ 表示节点从睡眠期唤醒后负载仍为空的概率。基于超帧周期划分，并参考文献[1]的计算， $g _ { 1 } { = } e ^ { - \lambda T s e r \nu i c e }$ ， $g _ { 2 } { = } e ^ { - \lambda W \theta }$ ，其中 $T _ { s e r v i c e }$ 为数据包平均服务时间。模型中各个状态的一步转移概率和主要状态的稳态概率方程[12\~14]如下：

$$
\begin{array} { r l } & { P ( \mathcal { R } _ { s , z } \mid \mathcal { A } _ { x } ) = \langle x , y , i \in ( 0 , m ) , k \in ( 0 , W _ { i } - 1 ) } \\ & { P ( \mathcal { R } _ { s , z } \mid S ) = ( 1 - s ) ^ { 2 } \rangle | \mathcal { R } _ { s , k } \in ( 0 , W _ { i } - 1 ) } \\ & { P ( \mathcal { T } | \mathcal { A } _ { z } ) = 1 - t _ { i } = ( 0 , m ) } \\ & { P ( \mathcal { R } _ { s , z } \mid S ) = ( 1 - s _ { z } ) | \mathcal { R } _ { w , k } \in ( 0 , W _ { i } - 1 ) } \\ & { P ( \mathcal { R } _ { s , z } \mid S ) = ( 1 - g _ { z } ) \alpha / W _ { i , k } \in ( 0 , W _ { i } - 1 ) } \\ & { \pi _ { \mathcal { R } ^ { 0 } } = ( 1 - s _ { z } ) \overline { { \mathfrak { R } } } _ { z , x } } \\ & { \pi _ { s } = ( 1 - t _ { i } ^ { \mathfrak { N } } ) \pi _ { \mathcal { R } _ { s , z } } } \\ & { \pi _ { s , z } = ( 1 - s ) \pi _ { \mathcal { R } _ { s , z } } + x \pi _ { \mathcal { R } _ { s , z } } \mathcal { E } ^ { * } + \tau ( 1 - s ) \pi _ { \mathcal { R } _ { s , z } } \mathcal { E } ^ { * } \mid \mathcal { R } ( 1 - g _ { z } ) } \\ & { \pi _ { s , z } = ( 1 - s ) \pi _ { \mathcal { R } _ { s , z } } = ( 1 - s ) \pi _ { \mathcal { R } _ { s , z } } \mathcal { E } ^ { * } = ( 1 - s ) \pi _ { s , z } \mathcal { E } } \\ & { \pi _ { s , z } = \pi _ { \mathcal { R } _ { s , z } } ( s + ( 1 - s ) ^ { 2 } ) \pi _ { \mathcal { R } _ { s , z } } \mathcal { E } = s _ { t } - s t } \\ & { \pi _ { s , z } = ( \mathcal { W } _ { z } - k ) \pi _ { \mathcal { R } _ { s , z } } \mathcal { W } _ { t } \mathcal { E } = ( 0 , W _ { i } - 1 ) } \end{array}
$$

另外，模型中信道检查状态、数据发送状态和后退状态的总稳态概率分析公式为

$$
\begin{array} { r l } & { \frac { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 1 } } = \sum _ { s = 0 } ^ { \infty } \pi _ { R _ { a _ { 0 } } } ( 1 . . . 6 ^ { \mathrm { s e r } / s } ) ( 1 . . 6 ) = \mathcal { E } } { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 1 } } ( 1 . . 6 ^ { \mathrm { s e r } / s } ) ( 1 . 6 ) } = } \\ & { \frac { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 2 } } = ( 1 - s ) \mathcal { E } } { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 3 } } = ( 1 - s ) \mathcal { E } } } \\ & { \frac { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 1 } } ( 1 - ( s ) ( 1 - s ) \mathcal { E } } { \displaystyle \sum _ { i = 0 } ^ { N } \pi _ { A _ { 1 } } = \frac { \sum _ { i = 0 } ^ { N - 1 } \pi _ { A _ { 1 } } ( 1 . 6 ^ { \mathrm { s e r } / s } ) \alpha _ { 1 } } { 1 . 6 } } \frac { \displaystyle \sum _ { i = 0 } ^ { N - 1 } \pi _ { A _ { 2 } } ( 1 . 6 ^ { \mathrm { s e r } / s } ) \alpha _ { 1 } } { 1 . 6 } } \\ & { + W _ { 0 } \frac { \displaystyle \frac { 1 } { 1 . 1 6 } ( 2 \mathcal { E } ) ^ { \mathrm { m o d u c } / s } \alpha _ { 1 } - \frac { 1 . . 5 ^ { \mathrm { m i n } - 1 } } { 1 . 6 } \times \pi _ { R _ { a _ { 0 } } } } { 1 . 2 } } \\ &  \frac { \displaystyle \sum _ { i = 0 } ^ { N } \alpha _ { A _ { 1 } } + \sum _ { s = 0 } ^ { N } \alpha _ { A _ { 2 } } + \pi _ { D _ { 0 } } + \frac { \sum _ { i = 0 } ^ { N } \frac { 1 } { \sqrt { s } } } { \displaystyle \sum _ { i = 0 } ^ { N } \alpha _ { R _ { a } } - \alpha _ { 1 } ^ { 2 } \alpha _ { R _ { a } } } + \frac { \sum _ { i = 1 } ^ { N } \pi _ { R _ { a } } } { \displaystyle \sum _ { i = 0 } ^ { N } \alpha _ { R _ { a } } } = 1 } \end{array}
$$

由上述转移概率和稳态概率公式，可以分析出初始后退状态稳态概率 $\scriptstyle \mathrm { \mathsf { R } } _ { 0 , 0 }$ 为

$$
\begin{array} { c } { { \pi _ { _ { R _ { 0 , 0 } } } = } } \\  { { 1 / ( ( g _ { _ { 1 } } \times ( 1 - E ^ { m + 1 } ) + s \times E ^ { m + 1 } + t \times ( 1 - s ) \times E ^ { m } ) / ( 1 - g _ { _ { 2 } } ) + L \times ( 1 - E ^ { m + 1 } ) +  } } \\ { { \displaystyle  \frac { 1 - E ^ { m + 1 } } { 1 - E } + \frac { ( 1 - E ^ { m + 1 } ) ( 1 - s ) } { 1 - E } + \frac { 1 } { 2 } ( W _ { _ { 0 } } 2 ^ { m a x B E - m i n B E } \frac { E ^ { m a x B E - m i n B E + 1 } - E ^ { N B } } { 1 - E } +  } } \\ { { \displaystyle  W _ { _ { 0 } } \frac { 1 - ( 2 E ) ^ { m a x B E - m i n B E + 1 } } { 1 - 2 E } - \frac { 1 - E ^ { m + 1 } } { 1 - E } ) ) } } \end{array}
$$

# 3 丢包率实验

根据上文对网络数据帧碰撞和丢包问题的理论分析，下面通过实验研究802.15.4网络协议参数对MAC层数据帧碰撞和丢包性能的影响，同时也对本文提出的节点状态转换模型进行评价。

假设网络节点数量 $N$ 为 $5 \sim 6 0$ ，信标指数 $B O$ 值为6，超帧指数 $s o$ 为 $4 { \sim } 5$ ，后退指数 $B E$ 值为 $2 { \sim } 5$ ，后退等待次数NB值取 $4 { \sim } 5$ ，数据包长 $L$ 为6时隙。 $B I$ 值为 $9 6 0 ^ { * } 0 . 0 1 6 ^ { * } 2 ^ { B O }$ ，超帧活跃期为 $9 6 0 ^ { * } 0 . 0 1 6 ^ { * } 2 ^ { S O }$ 。接收信标帧时间为 $\scriptstyle T _ { b } = 0 . 3 { \mathrm { s l o t } } .$ 。一个超帧时隙宽度为20个符号宽度，每个符号宽度 $0 . 0 1 6 \mathrm { m s }$ ，超帧周期一个时隙值为 $0 . 3 2 \mathrm { m s }$ 。下面分析网络MAC层的数据包碰撞概率和数据帧的丢包率性能。

# 3.1碰撞概率

根据模型图1的数学分析和概率计算，下面分析网络单个节点的数据帧碰撞概率。若两个节点同时检测到信道空闲，然后向接收端发送数据，接收端产生碰撞的概率表示为： $p _ { C } = 1$ $- ( 1 - r ) ^ { \mathrm { N } - 1 }$ ，其中 $\boldsymbol { r }$ 为节点发送数据帧的概率，即是 $\pi _ { s }$ ， $N$ 是节点数。

图2是节点发送状态稳态概率趋势图。随着节点数目的增加，节点发送数据概率呈递减趋势。而且退避指数 $B E$ 值越大，发送概率越小。这是因为 $B E$ 初始值越大，节点首次退避时间相对较长。从而导致节点更多的时间处于退避状态，发送数据帧的概率有所降低。

图中，文献[1的基于无节点休眠状态的发送概率比有休眠状态的发送概率稍低。这是因为基于休眠的时隙CSMA/CA算法竞争信道能够一定程度的降低MAC信道的冲突，改善网络性能。

图3是节点发送数据后发生碰撞的概率趋势图。很明显，随着 $N$ 的逐渐增加，碰撞概率逐渐增大，信道冲突加剧。

协议参数 $B E$ 对碰撞概率影响较大， $B E$ 越大的情况下网络碰撞概率越小，这是因为节点初始的退避时隙数相对较大，更多处于退避态，节点试图检测信道发送数据的概率低些，自然发生冲突的概率降低。而协议参数NB 越大，有利于减小信道冲突，从而降低MAC层碰撞。这是因为退避次数增大，节点退避等待时间延长，一定程度降低了碰撞现象。

0.04 minBE=2 sleep   
0.03 minBE-2 sep minBE=3 no sleep   
0.02 OOO0O0000OO   
0.01 0 20 40 60 80 100 节点数目N个

![](images/ed8b8d7e420f32a92ddf53c13564950210606a8db4d05e838e8bc980335623b5.jpg)  
图2数据发送概率

图4是MAC层碰撞概率随数据包到达速率变化的趋势图。很明显，随着非饱和负载的逐渐增加，碰撞概率逐渐增加。

![](images/bbd4b8c0a23f3e7458eb3aad454710e6fa302849730525bae8993f5e3a278502.jpg)  
图3碰撞概率随节点数变化  
图4碰撞概率随λ的变化

NB 和BE对碰撞概率影响较大，如图中所示BE越小碰撞概率越大，这说明初始退避指数小时，节点检测信道之前退避的时间较短，各个节点监测到信道状态为忙的概率增大，MAC层碰撞现象加剧。

另外，当网络的非饱和负载数据流量较小时（ $\lambda { < } 7 1$ ），退避次数NB 越小时，碰撞概率越严重。这是因为小的NB时节点退避等待的轮数减少，节点试图竞争信道的概率大些，发生冲突的概率自然增大。当非饱和负载较大时 $\lambda { > } 7 1$ 0，退避次数NB越大时，碰撞概率越严重。这是因为负载大了之后，通过增大退避次数对缓解数据帧碰撞作用不明显。

# 3.2 丢包率

基于前述对碰撞概率的分析，下面分析MAC层丢包率问题。丢包问题主要是由于信道误码和碰撞引起的。数据帧在信道传输过程中发生错误的概率 ${ \bf P } _ { 1 }$ 为： $1 - ( 1 - B E R ) ^ { L D }$ ，其中 $_ { L D }$ 为数据包长度，值取400bit。 $B E R$ 为无线网络信道误码率，即传输1bit信息过程中发生错误的概率。根据文献[3]，通过瑞利衰落信道来描述无线传感网信道的多径衰落特性，BER与路径损耗指数和传输距离有关。本文设定BER 的取值在 $7 \times 1 0 ^ { - 4 } \sim$ $3 \times 1 0 ^ { - 3 }$ 。无重传的数据帧丢包率[15]可表示为： $p _ { d } = 1 ~ - ~ ( ~ 1 ~ - ~$ $P _ { 1 } ) \left( 1 - \ p _ { C } \right)$ （204号

图5为数据帧丢包率随节点数目的变化趋势。随着节点数的增加，数据帧的丢包率逐渐递增。这是因为网络规模大了之后，竞争MAC层信道的节点更多，节点发送失败概率加大。另外，NB 越小，数据帧丢包率越大。这是因为较小的NB导致节点退避时间减少，从而加剧信道冲突概率。并且最小退避指数minBE越大，节点退避时间更长，信道冲突一定程度减弱，导致数据帧的丢包率降低。图5反映出在网络规模的较大网络中，BE 和NB对丢包率的影响很大。

![](images/212aeb97cce9d04c1c297c444c87f0fba6ff781de2cdd87cab8c494f1005796f.jpg)  
图5丢包率随节点数的变化

另外，从实验结果还可以看出，文献[1]中无节点休眠的模型的丢包率明显高的多。有节点休眠状态的超帧周期机制数据帧丢包率降低了 $2 3 . 7 \%$ ，这说明加入休眠状态后MAC层的碰撞现象减少，数据发送可靠性得到显著提高。

从图6中看出，随着信道传输状况的恶化，数据帧的丢包率随误包率的增加而加大。这反映出信道质量对MAC层的影响比较大。另外，NB越大，数据帧丢包率越小。这是因为较大的NB延长了节点监测信道之前的等待时间，从而降低信道冲突。并且最小退避指数minBE越大，导致节点后退等待时间过更长，从而一定程度的降低数据帧碰撞，降低丢包率。图6反映出在信道质量一样的情况下，BE和NB对丢包率的影响不是非常大。

图7为数据帧丢包率随数据帧到达速率的变化趋势。随着的逐渐增大，数据帧的丢包率缓慢增大。这反映出非饱和负载较小时对MAC层的丢包率影响较小。

![](images/cab2275616dbb54f39e14477ad02743a478ab8daf8cb96be11fff3c5a4bb2cd5.jpg)  
图6丢包率随误码率的变化

![](images/02de463375cbfa4d5a835a21b81b12250ec01e2accce0c136f631ea17e145acb.jpg)  
图7丢包率随λ的变化

另外，后退次数NB 越小，数据帧丢包率越大。这也是因为节点检查信道前的退避时间缩短，从而加重信道冲突。最小退避指数minBE越小，数据帧丢包率变化较大。图7反映出在同等负载情形下，BE对丢包率的影响比NB大。

经过对基于模型的协议碰撞概率、丢包率和参数的分析比较，提出的模型能够较好地分析802.15.4协议MAC层在休眠模式下的数据帧传输性能。而且通过提出的模型可以更精确研究网络参数配置对MAC层数据帧发送的影响，为802.15.4标准的实际使用提供性能优化参考。

# 4 结束语

针对802.15.4MAC层数据帧丢包优化问题，本文重点分析数据帧碰撞问题及其对MAC层数据丢包的影响，通过对MAC层信道接入机制分析建模的基础上，推导出节点在信道竞争过程中的数据发送概率等状态的稳态概率；然后根据丢包率的数学分析式，分析网络协议的参数NB和minBE和网络负载、网络规模 $N$ 和BER对碰撞概和丢包率的影响。

分析结果表明，提出的分析模型能够准确分析网络的相关性能指标，网络状态参数和协议参数设置能够优化数据帧丢包率，今后进一步改进协议的核心算法，对其建立与实际网络更相符的数学模型，提出新的优化策略，使协议具有更广泛的应用。

# 参考文献：

[1]Ramachandran I, Das AK,Roy S,Analysis of the contention access period ofIEEE 802.15.4 MAC[J].ACMTrans on Sensor Networks,2007,3(1): 4: 1-4: 22.   
[2]Wen Hao,Lin Chuang,Chen Zhi Jia,et al.An improved Markov model for IEEE 802.15.4 slotted CSMA//CA mech-anism [J].Journal of Computer Science and Technology,2009,24(3): 495-504.   
[3]方梅，陆阳，官骏鸣．非饱和态 802.15.4网络吞吐量建模分析[J]．系 统仿真学报,2010,22(4):1037-1041.   
[4]Park P,Ergen SC,Fischione C,etal.Duty-cycle optimization for IEEE 802. 15.4 wireless sensor networks [J].ACM Trans on Sensor Networks,2013, 10 (1): 12: 1-12: 32.   
[5]程远，张源，高西奇．差错信道下无线局域网丢包率性能分析[J].通 信学报,2007,28 (5):53-56.   
[6]李志华，连彬，魏忠诚，等．无线传感器网络能效和延时性能分析[J]. 计算机应用研究，2014.31(8):2473-2476.   
[7]周祥云，钱慧，余轮．低丢包率无线传感器网络S-MAC协议的研究[J]. 计算机科学,2011,38(10A):367-369.   
[8]Prasad Y,PachamuthuR.Analytical model of adaptive CSMA-CAMAC for reliable and timely clustered wireless multi-hop communication [Cl// Proc ofIEEE World Forum on Internet of Things.Piscataway,NJ:IEEE Press, 2014:212-217.   
[9]Hussein O,Sadek N M,Elnoubi S,et al.Analytical model of multihop IEEE 802.15.4 with unslotted CA//CSMA[J].International Journal of Computer and Communication Engineering,2014,3(3): 226-230.   
[10] Du Wan,Navarro D,Mieyeville F.Performance evaluation of IEEE 802.15. 4 sensor networks in industrial applications [J]. International Journal of Communication,2015,28(10): 1657-1674.   
[11]Hussein O,Sadek NM,Elnoubi S,etal.Analytical model of multihop IEEE 802.15.4 with unslotted CA//CSMA[J]. International Journal of Computer and Communication Engineering,2014,3(3): 226-230.   
[12]程宏斌，王晓喃，梁伟．启用节点睡眠态的6LoWPAN 网络节能研究 [J].计算机工程与科学,2012,34(10):53-56.   
[13] Kim TO,Baek S,Choi BD.Performance analysis of IEEE 802.15.4 superfame structure with the inactive period [J].Performance Evaluation, 2016,106:50-69.   
[14] Patel N R,Kumar S.Enhanced clear channel assessment for slotted CSMA//CA in IEEE 802.15.4[J].Wireless Personal Communications,95 (4): 4063-4081.   
[15] Park P,Di Marco P,Fischione C,et al.Modeling and optimization of the IEEE 802.15.4 protocol for reliable and timely communications [J].IEEE Trans on Parallel and Distributed Systems,2013,24(3): 550-564.