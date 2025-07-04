# 区分站点状态的轮询系统 $\mathsf E ( \mathsf X )$ 特性分析

孙洋洋，杨志军(云南大学 信息学院，昆明 650500)

摘要：针对提高轮询控制系统的工作效率和资源利用率以及确保系统公平性不受损害，提出了区分站点忙闲状态的限定 $( \operatorname { K } \textstyle = 2 )$ 轮询控制系统。运用概率母函数与嵌入式马尔可夫链的方法研究了系统的数学模型。仿真实验结果表明，理论值与实验值近似相等，表明该分析方法正确合理。系统基于限定！ $( \mathsf { K } { = } 2 )$ 轮询服务策略，根据站点所处的不同状态，只对有信息分组的动态忙站点进行服务。采用限定 $\scriptstyle \mathrm { K = } 2 ,$ 服务策略保障了系统公平性，而区分站点的忙闲状态又避免了对无信息分组的空闲站点的查询服务，从而提高了系统工作效率和资源利用率。与已有的服务策略相比较，系统性能明显改善。

关键词： $\scriptstyle \mathrm { K = } 2$ ；分忙闲；轮询；工作效率 中图分类号：TN911 doi: 10.3969/j.issn.1001-3695.2018.06.0327

# Analysis of E(x) characteristics of polling system that distinguishes site status

Sun Yangyang,Yang Zhijun (SchoolofInformation YunnanUniversity,Kunming 65o5oO,China)

Abstract: Inorder to improve the eficiencyandresource utilizationof poling control systemand ensure system fairness is not impaired,alimited( $\mathrm { K } { = } 2$ ） poling control system was proposed to distinguish the busy and idle status of the site.The mathematical model of the system was studiedby using probability generating function and embedded Markov chain.The simulationresultsshow that: thetheoreticalvaluesandtheexperimentalvaluesareapproximatelyequal,indicatingthatthe analysis method is correct and reasonable.The system is based on a limited ( $\mathrm { K } { = } 2$ ） polling service strategy,according to the different status of the site,only dynamic busy sites with information groups are served.The limited $( \mathrm { K } { = } 2 )$ ） service strategy ensuresthe system fairness,and distinguishing busyandidlestatusof siteavoidsthequeryserviceforthe idle site without information groups,thereby improving system eficiencyandresource utilzation.Compared with existing service strategy,the system performance is obviously improved.

Key words: $\scriptstyle \mathrm { K } = 2$ ; distinguish busy and idle; polling; efficiency

# 0 引言

无竞争是轮询控制系统的核心本质，公平性良好，资源合理分配，使其在智能交通与现代网络中应用广泛[I]。文献[2,3]分析研究了轮询排队论系统在认知无线电网络以及研发管理模型中的应用，文献[4]分析研究了轮询控制系统在无线网络中的应用，文献[5]研究了其在FPGA数据采集系统中的应用。

文献[6]根据有限时间分析研究了限定服务轮询系统，适用于集中控制的宽带无线网。轮询控制方式分为三类经典服务策略，即完全服务策略、门限服务策略和限定服务策略。然而单一的门限和完全服务策略不能在不同的站点中区分优先级来改进系统性能，而限定服务可以根据不同站点区分优先级，从而应用于 $\mathrm { { G / G / 1 / K } }$ 轮询控制系统的序数优化。根据服务规则，当门限服务和完全服务在站点信息分组较多的情况下，在服务当前站点的信息分组时容易造成排队等待服务的站点得不到服务而产生“饥饿”现象，从而降低了系统公平性，而限定服务保障系统公平性克服该现象的发生。文献[8]构建“完全 $^ { + }$ 门限”两级轮询系统模型以区分业务优先级，但是这种按照固定路径查询包括空闲站点在内的所有站点，导致信道利用率受到限制且增加了系统的复杂性，系统服务灵活性也大大降低。

在IEEE802.11系列标准中，其无线网络PCF协议均采用限定 $( \mathbf { K } \mathbf { = } 1 )$ 轮询控制方式，但是该方式对于区分网络业务优先级的情况却显得不够灵活。由文献[9]轮询系统中的限定 $\mathrm { K } { = } \mathrm { N } )$ 服务系统，根据服务的类型不同，通过对K的不同取值，可以区分业务优先级，K值越大每次发送的信息分组也越大，优先级越高，从而达到多优先级的控制方式，然而文献[9]并没有对限定 $( \mathsf { K } { > } 1 )$ 服务策略作理论分析。随着现代网络技术的快速发展，以及对区分业务优先级的强烈需求，限定， $\mathrm { \ K = 1 } \$ 服务策略已不能满足实际需要，迫切需要限定 $( \mathsf { K } { > } 1 )$ 轮询控制策略，既能区分业务优先级又兼顾系统公平性，同时为限定服务的后续研究奠定理论基础。

轮询控制系统中，对无信息分组的空闲站点的查询会浪费系统资源。文献[10]通过对有信息发送需求的站点分配信道避免空闲查询。但是轮询调度表与站点状态相互独立，对于空闲站点来说，接收者要在第一个时隙内没有收到信息数据后才能转换至下一个发送者，当站点一直空闲时，接收者就要在每轮信道分配中都要对空闲站点进行查询，浪费系统资源。

针对上述问题，基于动态思想[11,12]本文提出了区分忙闲站点的限定 $\scriptstyle ( \mathbf { K } = 2 )$ 轮询系统模型(busy and idle polling limited$\scriptstyle \mathrm { K = } 2$ ，BIPL2)。系统采用限定 $( \mathrm { K } { = } 2 )$ 的服务策略：

a)若站点中信息分组个数 $\leq 1$ ，则服务器服务该站点中的一个信息分组或不服务；b)若站点中信息分组个数 $: = 2$ ，则服务器服务该站点中的两个信息分组；c)若站点中信息分组个数 $> 2$ ，则服务器依然只服务该站点中的两个信息分组。

系统根据站点是否有信息分组发送需求将其区分为忙闲状态，每轮查询根据站点缓冲区状态更新轮询调度表，服务器仅对有服务需求的忙站点进行服务，从而降低了系统平均等待时间，提高了系统工作效率。采用概率母函数[13]与嵌入式马尔可夫链14的方法，对系统模型进行了深入分析，最后通过仿真实验验证了模型理论分析的正确合理性。

# 1 系统模型

# 1.1模型原理分析

BIPL2系统中有N个站点和一个服务器如图1所示。服务器首先对站点的状态进行更新，这样服务器只对有发送需求的忙站点进行发送服务。服务器不再侦听查询空闲站点，从而降低了系统的平均排队队长和平均等待时间。服务过程中采用限定 $( \operatorname { K } \textstyle = 2 )$ 服务方式就是每次轮询仅发送2个信息分组。

![](images/a4a9484e9100cf59b0261e75f5d8373e20ad4c00da645bd39e5cf9096e67851a.jpg)  
图1轮询系统模型

# 1.2变量定义

$\xi _ { i } ( n )$ ：站点 $i ( i = 1 , 2 . . . N )$ 在 $t _ { _ n }$ 时刻所缓存的信息分组的个数；Vi(n)：服务器对i号站点按限定服务策略对信息分组发送所

需要的时间;

η(v)：在vi(n)时间内进入i站点的信息分组的个数，且$j ( j = 1 , 2 . . . N )$ （

# 1.3模型假设条件

a)到达各站点的信息分组服从独立同分布的泊松过程，其分布的概率母函数、均值、方差分别是A(zi），λ=A(l)，${ \sigma _ { \lambda } } ^ { 2 } = A _ { i } ^ { " } ( 1 ) + \lambda - \lambda ^ { 2 } ~ ;$

b)服务器对任意一个信息分组的的服务时间服从独立、同分布的概率分布，其分布的概率母函数、均值、方差分别是$B _ { i } ( z _ { i } ) , \beta = B _ { i } ^ { ' } ( 1 ) , \sigma _ { \beta } ^ { ' 2 } = B _ { i } ^ { ' } ( 1 ) + \beta - \beta ^ { 2 } ;$ c)服务器完成站点的发送服务后，在站点之间切换时，所耗费的时间分布概率母函数为 $R _ { i } ( z _ { i } )$ ，均值为 $\gamma = R _ { i } ^ { ' } ( 1 )$ ，方差为 $\sigma _ { \gamma } ^ { \ 2 } = R _ { i } ^ { \prime } ( 1 ) + \gamma - \gamma ^ { 2 }$ ；d)每个终端站点内的存储器有足够大的缓存容量，不会发生数据信息丢失；e)对于进入到存储器内的缓存信息分组，将按照先到先服务(FCFS)的策略进行发送。

# 1.4概率母函数

假定在 $t _ { n }$ 时刻 $i$ 号忙站点 $( i = 1 , 2 , . . . , N )$ 接受服务器的发送服务，当 $i$ 号忙站点按限定（ $\scriptstyle ( \mathbf { K } = 2 )$ 服务的规则对存储器内缓存的信息分组服务完成后，服务器转去服务 $i + 1$ 号忙站点， $i + 1$ 号站点在 $t _ { n + 1 }$ 时刻接受服务器的服务。定义随机变量 $\xi _ { i } ( n )$ 为 $i$ 号忙站点 $( i = 1 , 2 , . . . , N )$ 在 $t _ { n }$ 时间其存储器内缓存的等待被服务的数据信息分组的个数，则在 $t _ { n }$ 时刻系统的状态可表示为[5(n),(n)..5\~(n)]。轮询系统的站点数量相对确定，服务开始时刻系统状态是可数的，由离散时间可数状态变量可构成嵌入式马尔可夫链，在系统稳定条件下，该马尔可夫过程是齐次，不可约，非周期的，并且有唯一的稳态分布。稳态状态下概率分布为 $p [ \xi _ { i } ( n ) = x _ { i } ; i = 1 , 2 , 3 , . . . N ]$ 。在 $t _ { n + 1 }$ 时刻，系统的状态可表示为：{5(n+1),5(n+)5(n+1),,N(n+1)}

在 $N \lambda \beta < 1$ 的系统稳定[15]条件下其概率分布的母函数定义为

$$
G _ { i } ( Z _ { 1 } , Z _ { 2 } , . . . Z _ { i } , . . . Z _ { N } ) = \sum _ { x _ { 1 } = 0 } ^ { \infty } \sum _ { x _ { 2 } = 0 } ^ { \infty } . . . \sum _ { x _ { i } = 0 } ^ { \infty } . . . \sum _ { x _ { N } = 0 } ^ { \infty } \pi _ { i }
$$

$$
( x _ { 1 } , x _ { 2 } , . . . x _ { i } , . . . x _ { N } ) Z _ { 1 } ^ { x _ { 1 } } Z _ { 2 } ^ { x _ { 2 } } . . . Z _ { i } ^ { x _ { i } } . . . Z _ { N } ^ { x _ { N } }
$$

$$
i ( i = 1 , 2 . . . N )
$$

当服务器在 $t _ { n + 1 }$ 时刻开始对 $i + 1$ 号忙站点服务时，有关系式为

$$
\left\{ \begin{array} { l l } { \xi _ { j } ( n { + } 1 ) = \xi _ { j } ( n ) + \eta _ { j } ( \upsilon _ { i } ) } \\ { \xi _ { i } ( n + 1 ) = \eta _ { j } ( \upsilon _ { i } ) } \end{array} \right. \qquad j \neq i
$$

则系统在 $t _ { n + 1 }$ 时刻的状态变量的母函数为

$$
G _ { i + 1 } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { i } , \cdots , z _ { N } ) = \operatorname * { l i m } _ { t \to \infty } E [ \prod _ { j = 1 } ^ { N } z _ { j } ^ { \xi _ { j } ( n + 1 ) } ] =
$$

$R _ { i } ( \prod _ { i = 1 } ^ { N } A _ { i } ( z _ { i } ) ) B _ { i } ^ { 2 } ( \prod _ { j = 1 } ^ { N } A _ { j } ( z _ { j } ) ) \frac { 1 } { z _ { i } ^ { 2 } } [ G _ { i } ( z _ { 1 } , z _ { 2 } , , , z _ { N } ) - z _ { i } G _ { i } ^ { ' } ( z _ { 1 } , . . . z _ { i - 1 } , 0 , z _ { i + 1 } , . . . z _ { N } ) -$ 由式(7)和(8)计算 $\sum _ { i = 1 } ^ { N } g _ { i + 1 } ( j , k )$ gi+1(j,k)得到

$$
G _ { i } ( z _ { i } , \mathfrak { z } _ { i - 1 } , 0 , \mathfrak { z } _ { i + 1 } , . . . \mathfrak { z } _ { N } ) ] + G _ { i } ( \mathfrak { z } _ { i } , . . . \mathfrak { z } _ { i - 1 } , 0 , \mathfrak { z } _ { i + 1 } , . . . \mathfrak { z } _ { N } )
$$

$$
+ B _ { i } [ \prod _ { j = 1 } ^ { N } A _ { j } ( z _ { j } ) ] G _ { i } ^ { ' } ( z _ { 1 } , . . . z _ { i - 1 } , 0 , z _ { i + 1 } , . . . z _ { N } ) - G _ { i } ( 0 . . . 0 ) + \sum _ { j = 1 } ^ { N } A _ { j } ( z _ { j } ) G _ { i } ( 0 . . . 0 )
$$

其中： $( i = 1 , 2 , . . . , N ) \ : . \ : G _ { i } ( 0 , 0 , . . . 0 )$ 为 $t _ { \mathfrak { n } }$ 时刻全部 $\mathbf { N }$ 个终端站存储器内存储的信息分组数均为0时的系统状态变量概率分布母函数。

# 1.5 平均排队队长

定义：第 $i$ 号站点在 $t _ { \mathfrak { n } }$ 时刻进行发送时，第 $j$ 号站点存储器内存储的信息分组数 $g _ { i } ( j )$ 为平均排队队长。

定义系统一阶偏导特性为

$$
g _ { i } ( j ) = \operatorname* { l i m } _ { z _ { 1 } , z _ { 2 } , \cdots , z _ { N }  1 } \frac { \partial G _ { i } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { N } ) } { \partial z _ { j } }
$$

$$
i = 1 , 2 , . . . , N ; j = 1 , 2 , . . . , N
$$

$$
g _ { i 0 } ( j ) = \operatorname* { l i m } _ { \substack { z _ { 1 } , z _ { 2 } , \cdots , z _ { i - 1 } , z _ { i + 1 } , \ldots , z _ { N }  1 } } \frac { \hat { \sigma } G _ { i } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { i - 1 } , 0 , z _ { i + 1 } , \ldots , z _ { N } ) } { \hat { \sigma } z _ { j } }
$$

$$
i = 1 , 2 , . . . , N ; j = 1 , 2 , . . . , i - 1 ; i + 1 , . . . , N
$$

定义系统二阶偏导特性为

$$
g _ { i } ( j , k ) = \operatorname* { l i m } _ { \substack { z _ { 1 } , z _ { 2 } , \cdots , z _ { j } , \ldots , z _ { k } , \ldots , z _ { N }  1 } } \frac { \widehat { \partial } ^ { 2 } G _ { i } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { j } , \ldots , z _ { k } , \ldots , z _ { N } ) } { \widehat { \partial } z _ { j } \widehat { \partial } z _ { k } }
$$

$$
i = 1 , 2 , . . . , N ; j = 1 , 2 , . . . , N ; k = 1 , 2 , . . . , N
$$

根据式(4) $\sim ( 6 )$ 对式(3)中变量 $A _ { i } ( \mathbf { z } _ { i } )$ 、 $B _ { i } ( z _ { i } )$ 、 $R _ { i } ( z _ { i } )$ 、$G _ { i } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { N } )$ 和 $G _ { i } ( z _ { 1 } , z _ { 2 } , \cdots , z _ { i - 1 } , 0 , z _ { i + 1 } , . . . , z _ { N } )$ 求一阶和二阶偏导化简后可得式(7） $\sim ( 1 0 )$ 。

$$
g _ { i + 1 } ( j , k ) = \theta \lambda [ B ^ { ' } ( 1 ) \lambda ^ { 2 } + \lambda ^ { 2 } \beta + \gamma ] + c ( \lambda ^ { 2 } + \gamma ^ { 2 } \beta ) +
$$

$$
\lambda \beta [ 2 g _ { i } ( k ) - g _ { i 0 } ^ { \cdot } ( k ) - 2 g _ { i 0 } ( k ) ] + g _ { i } ( j , k )
$$

$$
+ \lambda \beta [ 2 g _ { i } ( j ) - g _ { i 0 } ^ { \cdot } ( j ) - 2 g _ { i 0 } ( j ) ]
$$

$$
g _ { i + 1 } ( j , i ) = \theta \lambda [ B ^ { ' } ( 1 ) \lambda ^ { 2 } + \lambda ^ { 2 } \beta - 2 \lambda \beta + \gamma ^ { 2 } \beta ]
$$

$$
+ ( \left( \lambda + \gamma \right) \beta - 1 ) [ 2 g _ { i } ( j ) - g _ { i 0 } ^ { ' } ( j ) - 2 g _ { i 0 } ( j ) ]
$$

$$
+ 2 ( \lambda + \gamma ) \beta g _ { i } ( i ) + c \lambda ^ { 2 } + g _ { i } ( j , i )
$$

$$
( i \neq j )
$$

$$
g _ { i + 1 } ( j , j ) = \theta \lambda [ B ^ { ' } ( 1 ) ( \lambda ^ { 2 } + \gamma ^ { 2 } ) + A ^ { ' } ( 1 ) \beta ] + g _ { i } ( j , j )
$$

$$
+ ( \lambda - \gamma ) \beta [ 4 g _ { i } ( j ) - 2 g _ { i 0 } ^ { ^ { \prime } } ( j ) - 4 g _ { i 0 } ( j ) ] + A ^ { ^ { \prime } } ( 1 ) c
$$

$$
( i \neq j )
$$

$$
\begin{array} { r l } & { g _ { i + 1 } ( i , i ) = \theta \lambda [ B ^ { ' } ( 1 ) ^ { ( } \lambda ^ { 2 } + \gamma ^ { 2 } ) + A ^ { ' } ( 1 ) \beta + 4 } \\ & { } \\ & { + ( 4 \lambda \beta - 4 ) g _ { i } ( i ) + A ^ { ' } ( 1 ) c + g _ { i } ( i , i ) - 4 ( \lambda + \gamma ) \beta ] } \end{array}
$$

$$
\theta \lambda [ N B ^ { ^ { \prime } } ( 1 ) ( \lambda ^ { 2 } + \gamma ^ { 2 } ) - 4 ( \lambda + \gamma ) \ \beta + \lambda ] -
$$

$$
\begin{array} { c } { { [ 2 g _ { j } ( k ) - g _ { j 0 } ^ { ' } ( k ) - 2 g _ { j 0 } ( k ) ] - [ 2 g _ { k } ( j ) - g _ { k 0 } ^ { ' } ( j ) - 2 g _ { k 0 } ( j ) ] } } \\ { { { } } } \\ { { + 2 \lambda \beta [ \displaystyle \sum _ { i = 1 } ^ { N } g _ { i } ( j ) + \displaystyle \sum _ { i = 1 } ^ { N } g _ { i } ( k ) ] - \lambda \beta [ \displaystyle \sum _ { i = 1 } ^ { N } g _ { i 0 } ^ { ' } ( j ) + \displaystyle \sum _ { i = 1 } ^ { N } g _ { i 0 } ^ { ' } ( k ) ] } } \\ { { { } } } \\ { { + 2 \lambda \beta [ \displaystyle \sum _ { i = 1 } ^ { N } g _ { i 0 } ( j ) + \displaystyle \sum _ { i = 1 } ^ { N } g _ { i 0 } ( k ) ] } } \end{array}
$$

由式(9)和(10)计算 $\sum _ { i = 1 } ^ { N } g _ { i + 1 } ( j , j )$ 得到

$$
\begin{array} { l } { { \displaystyle \theta \lambda [ N B ^ { ' } ( 1 ) ( \lambda ^ { 2 } + \gamma ^ { 2 } ) - 4 ( \lambda + \gamma ) \beta ] + \theta \dot { A ^ {              \prime } } ( 1 ) - 4 g _ { j } ( j ) = 0 \nonumber } } \\ { { \displaystyle + 4 \lambda \beta \sum _ { i = 1 } ^ { N } g _ { i 0 } ( j ) - 2 \lambda \beta \sum _ { i = 1 } ^ { N } g _ { i 0 } ^ { ' } ( j ) - 4 \lambda \beta \sum _ { i = 1 } ^ { N } g _ { i 0 } ( j ) ( 1 2 } } \end{array}
$$

对式(1)计算 $\sum _ { j = 1 } ^ { N } \sum _ { \stackrel { k = 1 } { k \neq j } } ^ { N }$ （204号 对式(12)计算 $\sum _ { j = 1 } ^ { N }$ 两式化简后得到平均排队队长为

$$
g _ { i } ( i ) = \frac { \theta \lambda ^ { 2 } } { 4 ( 1 - N \lambda ( \gamma + \beta ) ) } [ N \lambda B ^ { * } ( 1 ) + N \lambda ( \gamma + \beta ) - 4 N \beta - \lambda \beta
$$

$$
+ \frac { 4 + \left( \gamma + \beta \right) \ A ^ { * } ( 1 ) - N ^ { ( } \gamma + \beta ) \ A ^ { * } ( 1 ) } { \lambda } + \frac { \dot { A ^ { * } } ( 1 ) } { \lambda ^ { 2 } } ]
$$

$$
i = 1 , 2 , . . . , N
$$

# 1.6 平均等待时间

定义：从信息分组到达站点内到对其开始进行发送服务时的平均时间间隔就是平均等待时间。

$$
E [ w _ { L } ] = \frac { g _ { i } ( i ) } { \theta \lambda ^ { 2 } } - \frac { 1 } { \lambda } - \frac { A ^ { ' } ( 1 ) } { \left( 2 \lambda \right) ^ { 2 } }
$$

$$
= \frac { 1 } { 4 ( 1 - N \lambda ( \gamma + \beta ) ) } [ N \lambda B ^ { \circ } ( 1 ) + N \lambda ^ { ( } \gamma + \beta ) - \lambda \beta
$$

$$
+ \frac { N \dot { A ^ {                                 } } ( 1 ) \lambda ^ { ( } \gamma + \beta ) } { \lambda ^ { 2 } } + \frac { ( \gamma + \beta ) \dot { A ^ { ' } } ( 1 ) - N \dot { A ^ { ' } } ( 1 ) \beta } { \lambda } ]
$$

# 1.7平均查询周期

定义：系统平均查询周期是指两次查询同一站点间的平均时间，由系统一阶求导得出。

$$
\theta = \frac { N c } { 1 - N \lambda ( \gamma + \beta ) }
$$

# 1.8系统吞吐量

定义：系统吞吐量是指单位时间内系统所能传输的信息分组数。

$$
T = N \lambda \beta
$$

其中： $c = { G _ { i } } ( 0 , 0 . . . 0 )$ ， $\theta = \frac { N c } { 1 - N \lambda ( \gamma + \beta ) }$

# 2 实验分析

# 2.1实验仿真

根据以上所建立的BIPL2系统模型，在系统稳定条件下进行数值计算和仿真实验，且BIPL2系统理论值由式(13)\~(16)计算得出。

实验仿真在MATLAB2014a平台完成。通过函数生成为均值的泊松分布序列，模拟站点中到达的信息分组数量。仿真模拟的通信过程处于理想状态，就是所有信息分组全部发送成功，丢包率和重传率为零。归一化后时间轴按时隙划分。

a)每个站点在任一单位时隙内进入其存储器内的信息分组数服从泊松分布；

b)对称控制系统即到达各站点的信息分组服从相同的概率分布；

c)系统稳定条件为 $N \lambda \beta < 1$ ：

d)仿真参数标注于图形下方。

![](images/003611fef5b6bf4f6d511faaf1accb7184fc01e2216c9041c20c73942055884a.jpg)  
图2吞吐量变化（ $\scriptstyle \mathrm { N = } 2 0$ $\beta = 2$ ， $\scriptstyle \gamma = 1$ ）

![](images/0255bc29e18c0173ae2d264ea760948a4dc9350502b4a4f6af8aa70c4f1260da.jpg)

![](images/794905a7c051773d013023e124000b264d1fca2e77a1f7fb5f65595b6b0f421d.jpg)  
图3平均等待时间变化 $( \Nu = 2 0$ $\beta = 2$ ， $\scriptstyle \gamma = 1$ ）  
图4平均排队队长变化 $( \Nu = 2 0$ $\beta = 2$ ， $\scriptstyle \gamma = 1$ ）

![](images/b4b8fb72e1ce2293550cc9e29837280cc767f07bb78fe3fbaf950d73eb7813a0.jpg)  
图5平均查询周期变化 $\scriptstyle \mathrm { N = } 2 0$ $\beta = 2$ ， $\scriptstyle \gamma = 1$ ）

![](images/b14b4c033d19a5d1c29be5c008013bed0468f1dda58a263d69b7c358491f310b.jpg)  
图6和限定 $( \mathrm { K } { = } 1 )$ 时延比较（ $\beta = 2 , \gamma = 1$ ）

![](images/7e0cf79fc1d7e6ffad75f51ed3cffe0278569c3dabf50643f6bc9e1cee2fe9c2.jpg)  
图7和单一门限服务与完全服务的平均等待时间的比较

# 2.2结果分析

首先从图2\~5能够看出，本文采用的理论分析方法能较为合理的描述BIPL2轮询控制系统，理论计算值和计算机仿真实验值近似程度较好。

图4、5分别描述了平均排队队长与平均查询周期与系统负载的关系。从图中可以看出，平均排队队长与平均查询周期随系统负载的加大而相应增加，且理论值与实验值误差较小，与公式理论推导相一致。

其次图3描述了平均等待时间与站点信息分组到达率的关系。图中平均等待时间随到达率的增加呈线性增加趋势，这是因为信息分组的到达过程随着到达率的增加而增加，从而增大了整个系统平均等待时间。

并且图2描述了吞吐量与站点信息分组到达率的关系，系统吞吐量随站点信息分组到达率的加大也呈线性增大趋势。另一方面，图3中到达率的增大同时造成平均等待时间的增加。因此，在考虑如何提高系统吞吐量时还应该以系统平均等待时间作为约束条件。

![](images/f747cbf998705f83cb6720a828aa1e087689fe4294adfae5b8b6f21078496802.jpg)  
图8吞吐量比较 $( \Nu = 2 0$ ， $\beta = 2$ ， $\scriptstyle \gamma = 1$ ）

![](images/16ff2c2131dcbf9d09a5e36e509a662960114d2770c37e90ecdb244fd9118ac2.jpg)  
图9平均等待时间比较！ $( \Nu = 1 0$ $1 0 , \beta = 2 , \gamma { = } 1 )$ （20

BIPL2控制系统的核心为采用限定 $( \mathrm { K } { = } 2 )$ 的服务策略再通过区分站点忙闲状态来提高系统效率和资源利用率，与已存在的现有服务策略相比较本文得出下列结果：

由图6可以看出，BIPL2系统相比于单一限定 $( \mathsf { K } \mathrm { = } 1 )$ 系统在平均等待时间方面得到极大改善。图6表明随系统到达率的增大单一限定 $( \mathrm { K } { = } 1 )$ 的平均等待时间急剧增加，而BIPL2系统的平均等待时间则变化缓慢趋于稳定，且当站点个数N由10 增加到20时，单一限定 $\mathrm { \ K = 1 }$ 的平均等待时间增加迅速波动大，而BIPL2系统则增加缓慢波动很小。而图7描述了在相同的实验环境下，单一门限服务和完全服务的平均等待时间与BIPL2系统的平均等待时间的变化。从图中可以直观地看出，BIPL2系统的平均等待时间明显小于单一门限服务和完全服务。而轮询系统的完全服务、门限服务和限定服务三类经典服务策略，其平均等待时间在相同的条件下是依次递增的。之所以图7描述的BIPL2系统的平均等待时间明显小于单一门限服务和完全服务，是因为BIPL2系统避免了对无信息分组的空闲站点的查询服务，从而降低了系统平均等待时间，提高了系统工作效率。

由图2和3可以得出，系统吞吐量和平均等待时间随着到达率的增加而增加，所以应以平均等待时间作为增大系统吞吐量的限制条件。图8为BIPL2系统和限定 $( \mathrm { K } { = } 1 )$ 系统吞吐量的比较。从图中可以看出在相同的平均等待时间条件下BIPL2系统吞吐量更大。

推导得出分忙闲限定 $\mathrm { ( K = } 1 \mathrm { ) }$ )轮询系统模型(busy and idlepolling limited $\scriptstyle \mathrm { K = 1 }$ ，BIPL1)。在此选取平均等待时间为比较指标，如图9所示，随着信息分组到达率的增加，BIPL2系统与BIPL1系统得到很好的业务优先级的区分，且BIPL2系统的平均等待时间明显小于BIPL1系统。正如文章所述，限定 $\mathrm { K } { = } 2 )$ 服务策略每次能发送2个信息分组，相比于限定 $\scriptstyle ( \mathrm { K = 1 } )$ 策略增加了每次所能发送的信息分组个数，因此BIPL2系统在兼顾系统公平性的同时还降低了平均等待时间。

轮询控制系统具有无竞争及服务质量(qualityofservice,QoS)保障等优点。QoS关键技术指标包含吞吐量、时延和时延变化等。如图2、3、6\~9所示，BIPL2系统可以实现更高的吞吐量，极大降低系统时延且时延变化缓慢波动小，具有良好的QoS保障。

# 3 结束语

本文提出的BIPL2系统，基于限定 $( \mathrm { K } { = } 2 )$ 服务策略，依托站点的忙闲状态仅对有信息分组的忙站点进行服务，这样减少了对空闲站点的查询耗能，提高了系统工作效率和资源利用率。采用概率母函数和嵌入式马尔可夫链的方法建立了系统数学模型，并精确解析了系统各个重要特性参数。

轮询控制系统可以提供无冲突的信息接入且为时延敏感类业务提供时延保障，一直是无线传感器网络MAC层的一种重要的调度控制方式，而传统的超密集无线传感器网络被推荐作为蜂窝网络的补充，基于MIMO通信技术提出了5G超高密度蜂窝网络，相信BIPL2轮询控制系统在5G的优化与改进中必将有突出作用[16]。

# 参考文献：

[1]赵继军，谷志群，薛亮.WSN中层次型拓扑控制与网络资源配置联合 设计方法[J]．自动化学报，2015，41(3):646-660.(Zhao Jijun，Gu Zhiqun,Xue Liang.Joint design method of hierarchical topology control and network resource allocation in WSN[J].Journal of Automation,2015, 41 (3): 646-660. )   
[2]张旭，刘聪，胡胜．认知无线电网络中基于排队论的集中式频谱分配策 略[J].计算机应用研究,2015,32(1):187-190.(Zhang Xu,Liu Cong, Hu Sheng.Centralized spectrum allocation strategy based on queuing theory in cognitive radio networks [J].Application Research of Computers, 2015,32(1): 187-190.)

[3]代应，宋寒，邢乐斌．基于反馈优先服务策略的产品研发管理模型研究 [J].计算机应用研究,2015,32(3):705-708,716.(Dai Ying,Song Han, Xing Lebin.Research on product development management model based onfeedback priority service strategy [J].Application Research of Computers,2015,32(3): 705-708,716.)

[4] 孙泽华，裴二荣，韩昊哲．无线传感器网络中基于网络覆盖的节点睡眠 调度机制[J].计算机应用研究，2016,33(9)：2731-2734，2742.(Sun Zehua,Pei Errong,Han Haoze.Node sleep scheduling mechanism based on network coverage in wireless sensor networks [J].Application Research of Computers,2016,33(9):2731-2734,2742.)   
[5]于艳艳，黄倩，王磊．基于FPGA的动态优先轮询策略在Ad hoc 网络数 据采集系统中的研究与应用[J].云南大学学报：自然科学版，2014,36 (1):16-2O.(Yu Yanyan,Huang Qian,Wang Lei.Research and application of dynamic priority polling strategy based on FPGA in Ad hoc network data acquisition system [J]. Journal of Yunnan University: Natural science, 2014,36(1):16-20.)   
[6]Hong Shengchen，Yang Fengyan.Optimization of broadband wireless networks with centralized control using memetic algorithm [C]// Proc of International Conference on Information Networking.Beijing:Tsinghua University Press,2014: 572-577.   
[7]Hong Shenchen,Lin Shiyang. Ordinal optimization of G//G//1//K poling systems with k-limited service discipline [J]. Journal of Optimization Theory and Applications,2009,140 (2): 213-231.   
[8]杨志军，丁洪伟，陈传龙．完全服务和门限服务两级轮询系统E(x）特 性分析[J]．电子学报，2014，42(4):774-778.(Yang Zhijun Ding Hongwei,Chen Chuanlong.Full service and threshold service two-level polling system E(x) characteristics analysis [J].Electronic Journal,2014, 42 (4): 774-778.)   
[9]Winands E MM, Adan IJBF, Van Houtum G J. A state-dependent polling model with k-limited service [J].Probability in the Engineering and Information Science,2009,23 (2): 385-408.   
[10] Zhao Wenbin, Tang Xinyan． Scheduing sensor data collection with daynastic trsffic patterns [J].IEEE Trans on Parallel and Distributed Systems,2013,24(4): 789-802.   
[11]韩忠明，毛锐，郑晨烨．一个有效的动态网络节点影响力模型[J].计 算机应用研究,2019,2(7):1-9.(Han Zhongming,Maorui, Zhengchenhua. An effective dynamic network node influence model [J].Application Research of Computers,2019,2(7): 1-9.)   
[12]陶勇，沈济南．基于动态关键路径的云工作流调度算法[J].计算机应 用研究,2018,35(5):1500-1505.(Tao Yong,Shen Jinan.Cloud workflow scheduling algorithm based on dynamic critical path [J].Application Research of Computers,2018,35(5):1500-1505.)   
[13]李勇，蔡梦思，李黎．基于协调博弈的交通拥塞传播临界值研究[J]. 计算机应用研究,2016,33(7):1971-1973,1982.(Li Yong,Cai Mengsi, Li Li.Research on threshold value of trafic congestion propagation based on coordination game [J].Application Research of Computers,2016,33 (7): 1971-1973,1982. )   
[14]程宏斌，孙霞，王晓喃．基于马尔可夫链的 802.15.4协议MAC层数据 包服务时间研究[J].计算机应用研究，2016,33(4):1216-1218,1223. (Cheng Hongbin,Sun Xia,Wang Xiaonan.Research on MAC layer packet service time of 802.15.4 protocol based on Markov chain [J].Application Research of Computers,2016,33(4): 1216-1218,1223.)   
[15]张芬，张艳邦.转移概率部分未知的时滞不确定Markov 跳跃系统稳定 性分析[J].计算机应用研究，2017，34（7):1993-1996.(Zhang Fen, Zhang Yanbang. Stability analysis of uncertain Markov jump systems with unknown transitionprobabilitypart[J].Application Researchof Computers,2017,34(7): 1993-1996.)   
[16] Ge Xin,Tu Shan,Mao Ge,Wang Chenxing.5Gultra densecellularnetworks [J].IEEEWirelessCommunications,2016,23(1):72-79.