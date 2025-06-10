# 一种适用于分布式审批工作流的多重短签名方案

左黎明ab，陈兰兰ab，周庆a,b(华东交通大学 a.理学院,b．系统工程与密码学研究所，南昌 330013)

摘要：传统单路线性工作流难以满足高并发、时效性高的管理事务需求，而采用多层网状分布式架构可以有效解决此类问题。针对分布式审批工作流业务系统中存在的数据交互安全问题，提出了一种安全性较高、签名长度较短的多重短签名方案。首先，在随机预言机模型和CDH困难问题假设下，证明了签名方案的安全性；基于此方案设计了分布式审批工作流交互协议，并进行了安全性分析；运用C语言实现了签名方案，并与同类签名方案进行了效率比较；最后对基于此签名方案的应用系统的优势进行了分析。结果表明，该签名方案效率较高、计算量小，因此，基于此方案的分布式审批工作流适用于高并发、时效性要求高的电子政务系统。

关键词：分布式架构；工作流；多重短签名；协议 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2018.07.0561

Short multi-signature scheme for distributed approval workflow

Zuo Liming1,², Chen Lanlan1,2, Zhou Qing1, 2 (a.SchoolofScience,b.SEC Institute,EastChina Jiaotong University,Nanchang 33oo13,China)

Abstract:Traditional single-route workflows are diffcult to meet the high concurrencyand time-sensitive management transactionrequirements,and multi-layer mesh distributed architecturecan effectively solve such problems.Aimingat the problemof data interaction securityinthe distributed approval workflow business system,this paper proposed a short multi-signature scheme suitable for distributed approval workflowwith high securityand shortsignature length.It firstly proved the security of the signature scheme under the random oracle model and the assumption of CDHdificult problem. Then,it designed adistributed approval workflow interaction protocol basedon the schemeandcarriedoutthe security analysis.It implemented the signature scheme by C language and compared the proposed signature scheme with some similar signature schemes.Finally,the paper analyzed the advantagesof theapplication system based on this signature scheme.Theresults showthat thesignature scheme proposed has high efciencyandsmallamountofcalculation.Therefore, the distrbuted approval workflow based on the scheme is suitable for e-government systems with the demands of high concurrency and time effectiveness.

Key words: distributed architecture;workflow; short multi-signature;protocol

# 0 引言

传统的工作流技术面向集中式应用，但随着现代企业规模的日趋扩大，信息呈现出一种分布、异构、松散耦合的状态，传统的工作流技术已无法满足海量数据下的信息管理需求。尤其对于面向政府机关的电子政务系统，管理事务繁琐、需要层层审批，在高并发、时效性要求高的环境下，传统工作流难以满足此类系统需求，而采用多层网状的分布式架构可以有效地解决此类问题。2018年，Pan[1对分布式工作流管理系统的代理根据其功能进行划分，并对代理的每种类型的执行过程进行分析，对流程执行和资源管理等关键技术进行了研究与实现。但Pan对分布式工作流的技术研究主要关注于其功能，很少提及对审批信息的安全性保护。对于面向政府机关内部以及其他政府机构的系统，信息的保密至关重要。因此，将数字签名应用于分布式审批工作流中，构造一种适用于分布式审批工作流的多重短签名方案，对审批信息进行保护，对采用分布式审批工作流的业务系统的数据安全性而言具有重要意义。

多重签名（multi-signature,MS）的概念由Itakura 等人[2]于1983年首次提出，是一种多个用户对同一消息的特殊签名，适用于一个文件需要多个人同时签名的场景，比如逐层审批的文件，在电子商务、电子政务等领域具有广泛的应用。近年来，国内外许多专家学者对多重签名方案进行构造与改进。2015年，Sahu等人[3提出了采用双线性对的基于身份的多代理多重签名方案，并在计算Diffie-Ellman假设和随机预言模型下证明其在自适应选择身份攻击下是抗存在伪造的。2016年，杜红珍[4采用双线性对技术构造了一种高效的基于身份的有序多重签名机制，并在计算性Diffie-Hellman困难假设下证明了其在适应性选择消息和身份攻击下是抗存在性伪造。2017年，Pankaj等人[5提出了一种采用双线性对的基于身份的多代理多重签名方案，并证明该方案具有较高的效率和安全性。还有一些学者相继提出其他多重签名方案[6-9]。但上述大部分签名方案签名长度较长，在网络条件较差的环境下，存在签名传输、存储效率较低等问题。因此，构造一种签名长度较短、安全性较高的多重签名具有重要意义。

短签名的概念由Boneh等人[10首次提出，其签名长度是DSA签名长度的一半，具有更高的签名效率。本文将短签名引入多重签名，构造了一种适用于分布式审批工作流的多重短签名方案，该方案具有签名长度短、安全性高的优势。并设计了相应的交互协议，适用于需要逐层审批的电子政务系统，并且满足安全性高、数据量大、高并发、松耦合的事务管理需求。

# 1安全的分布式审批工作流原理

如图1所示，本文论述的安全的分布式审批工作流的业务系统需要有密钥生成中心（keygenerationcentre，KGC）和审批网络。审批网络结构如图2所示，主要包括信息提交用户User、信息接收节点Start、退回节点 $F a i l$ 、审批完成节点End、信息处理节点 $I n f o$ 以及 $\mathbf { \Omega } _ { M }$ 个审批层 $A _ { i }$ （204号 $( 1 \leq i \leq M )$ ，其中每个审批层中包含若干个审批节点 $U _ { i , j }$ 1 $( 1 \leq i \leq M$ ， $1 \leq j \leq N _ { i } )$ 。令 $U _ { i } \in \{ U _ { i , 1 } , U _ { i , 2 } , \cdots , U _ { i , N _ { i } } \}$ $( i = 1 , 2 , \cdots , M )$ ，即从每个审批层中选取一个审批节点，则选取的 $M$ 个审批节点 $U _ { 1 } , U _ { 2 } , \cdots , U _ { \scriptscriptstyle M }$ 与节点Start以及 $E n d$ 构成一条审批链 $\textbf { \em L }$ ，审批链中的每个节点选取规则是选择每个审批层中当前队列最短的审批节点，且一条审批链完成一轮工作流审批。具体参数说明如表1所示。

表1参数列表Tab1Parameters list  

<html><body><table><tr><td>序号</td><td>参数名</td><td>说明</td></tr><tr><td>1</td><td>User</td><td>信息提交用户</td></tr><tr><td>2</td><td>Start</td><td>信息接收节点</td></tr><tr><td>3</td><td>Fail</td><td>退回节点</td></tr><tr><td>4</td><td>End</td><td>审批完成节点</td></tr><tr><td>5</td><td>Info</td><td>信息处理节点</td></tr><tr><td>6</td><td>A</td><td>审批层</td></tr><tr><td>7</td><td>Ui</td><td>审批节点</td></tr><tr><td>8</td><td>Ui</td><td>选取的审批节点</td></tr><tr><td>9</td><td>L</td><td>审批链</td></tr></table></body></html>

审批工作流要件具体说明如下：

a)密钥生成中心，主要工作是为审批网络中每个审批节点产生并分配密钥对。由于用户提交的待审批信息具有私密性，密钥生成中心需要对审批过程进行全程监控，故系统需求分析上有一些特殊要求： $\textcircled{1}$ 仅密钥生成中心可验证，在获得密钥生成中心授权情况下被授权者也可验证； $\textcircled{2}$ 利用密钥生成中心主密钥和审批节点索引号即可进行安全认证。

b)审批网络。如图2所示，审批网络包括若干条审批链，对于一条审批链 $L = \{ S t a r t , U _ { 1 } , U _ { 2 } , \cdots , U _ { M } , E n d \}$ ，信息提交用户提交信息给信息接收节点Start，节点Start将信息封装后，发送给审批链 $\boldsymbol { L }$ 的第一个审批节点 $U _ { 1 }$ 。 $U _ { \scriptscriptstyle 1 }$ 先审批信息，如果不满足审批要求，则将退回结果和信息发送给退回节点 $F a i l$ ，否则对信息进行签名，并发送给下一个审批节点 $U _ { 2 }$ 。 $U _ { \scriptscriptstyle 2 }$ 先验证签名的有效性，如果无效，则将无效结果和信息直接退回到节点Fail；如果有效则开始审批信息，若不满足审批要求，则将退回结果和信息发送给节点Fail，否则对信息进行签名，并发送给下一个审批节点。直到最后一个审批节点 $U _ { \scriptscriptstyle M }$ 接收信息，先验证签名的有效性，如果无效，则将无效结果和信息直接退回到节点Fail；如果有效则开始审批信息，若不满足审批要求，则将退回结果和信息发送给节点Fail，否则对审批通过结果和信息进行签名，将签名发送给审批完成节点End。至此，一条审批链审批工作结束。节点Fail和End最终将审批结果发送给信息处理节点Info，节点Info再将审批结果返回给信息提交用户。

根据以上系统原理与需求，本文设计了一种适用于分布式审批工作流的多重短签名方案，以此来提高工作流系统的安全性，而设计一种安全高效的多重短签名方案是关键。

![](images/c281036278ac8612e6bb7ad293941e61d3706b01dc1f7335c34b9865304d323d.jpg)  
图1系统模型Fig.1System model

![](images/c7a93a803845859ce59e829dd335bb2537745a9c912fdc4477846af19043658d.jpg)  
图2审批网络结构  
Fig.2Approval network structure

# 2多重短签名方案设计与安全性分析

# 2.1数学基础

定义1 计算性 Diffie-Hellman 问题(computationalDiffie-Hellman,CDH)。给定 $P , a P , b P \in G _ { 1 }$ （ $a , b \in Z _ { q } ^ { * }$ 是未知的随机数)，计算 $a b P \in G _ { 1 }$ 是困难的。

定义2双线性对（bilinear pairings）。给定一个安全参数 $k$ ， $G _ { \imath }$ 为 $q$ 阶循环加法群， $G _ { 2 }$ 为同阶循环乘法群，其中 $P$ 为 $G _ { 1 }$ 的生成元，q为一个 $k - b i t$ 素数，则称映射 $e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 为双线性对，如果满足以下三条性质：

a)双线性性，对 $\forall a , b \in Z _ { q } ^ { * }$ ，有 $e ( a P , b P ) = e ( P , P ) ^ { a b }$ ：b)非退化性， $e ( P , P ) \neq 1$ ;c)易计算性， $\forall Q , R \in G _ { 1 }$ ，存在有效算法计算 ${ \mathbf { \Psi } } _ { e ( Q , R ) }$ 。

# 2.2多重短签名方案

一般多重短签名的方案定义如文献[4]中所述，根据前述对安全审批工作流的需求分析要求，本文构造了一种适用于分布式审批工作流的多重短签名方案。方案由系统初始化、审批节点密钥生成与注入、审批链与多重签名、多重签名验证以及授权签名验证五个高效算法组成，具体过程如下：

a)系统初始化。密钥生成中心KGC给定一个安全参数 $k$ ，选择一个大素数 $q$ ， $G _ { 1 }$ 、 $G _ { 2 }$ 为 $q$ 阶循环群， $P$ 为 $G _ { 1 }$ 的生成元。选择一个安全的双线性映射 $e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 。KGC 随机选择（204号 $s \in Z _ { q } ^ { * }$ 作为系统主密钥，并计算 $P _ { p u b } = s P$ 作为主公钥。选择安全的Hash 函数 $H _ { 1 } : \{ 0 , 1 \} ^ { * }  Z _ { q } ^ { * }$ ， $H _ { 2 } : \{ 0 , 1 \} ^ { * }  G _ { 1 }$ ，则KGC公布系统参数params={q,P,e, $G _ { 1 } , G _ { 2 } , P _ { p u b } , H _ { 1 } , H _ { 2 } \}$ ，KGC掌握系统主密钥（204号 $s$ 。

b)审批节点密钥生成与注入。在连接审批网络前，每个审批层的每个节点需要在 KGC 登记。每个审批节点输入身份 $I D$ ，KGC随机选择一个密钥生成标记 $K _ { \scriptscriptstyle I D } \in Z _ { q } ^ { * }$ ，生成审批节点私钥 $x _ { I D } = s H _ { 1 } ( I D , K _ { I D } , s )$ ，并秘密保存 $K _ { \iota D }$ ，计算公钥$y _ { I D } = x _ { I D } P$ 。密钥生成中心通过身份 $I D$ 建立索引对审批节点的信息进行管理，不同身份的审批节点使用不同的密钥生成标记，并通过安全方式向身份 $I D$ 的审批节点注入密钥。这种密钥生成的方式与已有的数字签名方案均有不同，是为了实现前述特殊要求的 $\textcircled{1}$ 和 $\textcircled{2}$ 。

c)审批链与多重签名。对于一条审批链$L = \{ S t a r t , U _ { 1 } , U _ { 2 } , \cdots , U _ { M } , E n d \}$ ，用户提交待审批信息到信息接收节点Start，如果该信息符合所有审批条件，则会执行到审批通过节点 $_ { E n d }$ ，否则，退回到退回节点Fail。审批链对提交的待审批信息 $m \in \{ 0 , 1 \} ^ { * }$ 具体审批步骤如下：

(a) Start具体操作过程如下：设 $T$ 为Start收到信息 $m$ 的时间，用于记录消息初次进入审批队列时间。将消息 $m$ 和时间$T$ 发送给第一个审批节点 $U _ { \mathrm { { \scriptscriptstyle 1 } } }$ 。

(b) $U _ { 1 }$ 收到信息后操作过程如下：计算 $h = H _ { 2 } ( m , T )$ ，$S _ { 1 } = I D _ { 1 } x _ { I D _ { 1 } } h$ ，将部分签名 $S _ { 1 }$ 、身份 $I D _ { 1 }$ 、信息 $m$ 以及 $T$ 发送给下一个审批节点 $U _ { 2 }$ 。

(c) $U _ { \scriptscriptstyle 2 }$ 首先验证 $S _ { 1 }$ 的有效性，再附加签名，具体过程如下：

i）计算 $h = H _ { 2 } ( m , T )$ ；

ii）验证 $e ( S _ { 1 } , P ) = e ( h , I D _ { 1 } y _ { I D _ { 1 } } )$ 是否成立，如果不成立，则将信息 $m$ 发送给退回节点 $F a i l$ 并结束审批，否则 $U _ { \mathbf { \lambda } _ { 2 } }$ 继续审批;

iii）计算 $S _ { 2 } = S _ { 1 } + I D _ { 2 } x _ { I D _ { 2 } } h$ ，将部分签名 $S _ { 2 }$ ，身份 $I D _ { 1 }$ ， $I D _ { 2 }$ ，信息 $m$ 以及 $T$ 发送给下一个审批节点 $U _ { 3 }$ 。

(d) $U _ { i }$ $( i = 3 , 4 , \cdots , M )$ 收到第i-1个审批节点 $U _ { i - 1 }$ 发送的部分签名 $S _ { i - 1 }$ ，身份 $I D _ { 1 }$ ， $I D _ { 2 }$ ，…， $I D _ { i - 1 }$ ，信息 $m$ 以及 $T$ 后，首先验证 $S _ { i - 1 }$ 的有效性，再附加签名，具体过程如下：

i）计算 $h = H _ { 2 } ( m , T )$ ：

ii）验证 $e ( S _ { i - 1 } , P ) = e ( h , \sum _ { j = 1 } ^ { i - 1 } I D _ { j } y _ { I D _ { j } } )$ 是否成立，如果不成立，则将信息 $m$ 发送给退回节点 $F a i l$ 并结束审批，否则 $U _ { i }$ 继续审批；

iii）计算 $S _ { i } = S _ { i - 1 } + I D _ { i } x _ { I D _ { i } } h$ ，则 $S _ { i }$ 为 $i$ 个审批节点 $U _ { 1 } , U _ { 2 } , \cdots , U _ { i }$ 对信息 $m$ 的部分签名。当 $i = M$ 时，得到的签名 $S _ { M }$ 为审批链 $\boldsymbol { L }$ 中 $M$ 个审批节点 $U _ { 1 } , U _ { 2 } , \cdots , U _ { M }$ 对信息 $m$ 的多重短签名。

最后，审批节点 $U _ { \scriptscriptstyle M }$ 将签名 $S _ { M }$ ，身份 $I D _ { 1 }$ ， $I D _ { 2 }$ ，…， $J D _ { y }$ ，信息 $m$ 以及 $T$ 发送给审批通过节点 $E n d$ 。

d)多重签名验证。审批通过节点End验证（204号 $e ( S _ { M } , P ) = e ( h , \sum _ { i = 1 } ^ { M } I D _ { i } y _ { i } )$ 是否成立，如果成立，则签名有效，将审批通过结果发送给 $I n f o$ ；否则签名无效，退回到Fail，Fail再将审批失败结果发送给Info。Info最终将审批结果进行处理并返回给用户。签名算法正确性验证如下：

$$
e ( S _ { \scriptscriptstyle M } , P ) = e ( \sum _ { i = 1 } ^ { M } I D _ { i } x _ { { I D } _ { i } } h , P ) = e ( h , \sum _ { i = 1 } ^ { M } I D _ { i } y _ { { I D } _ { i } } )
$$

e)授权签名验证。密钥生成中心向验证者公开身份为 $I D _ { i }$ 的审批节点对应的授权信息 $Q _ { i } = H _ { \scriptscriptstyle 1 } ( I D _ { i } , K _ { \scriptscriptstyle I D _ { i } } , s )$ ，任何人都可以通过审批节点的身份 $I D$ 和 $\varrho$ 验证签名的有效性。验证等式

$$
e ( S _ { \scriptscriptstyle M } , P ) \ = e ( H _ { \scriptscriptstyle 2 } ( m , T ) , \sum _ { i = 1 } ^ { M } I D _ { i } Q _ { i } P _ { p u b } )
$$

是否成立，如果成立，则签名有效，确认审批通过，否则签名无效，确认审批失败。

# 2.3安全模型与安全性分析

定义3 敌手 A(签名攻击算法)和挑战者C之间的攻击游戏交互过程如图3所示，如果伪造的签名 ${ S } _ { n } ^ { * }$ 满足存在一个$\hat { m }$ 没有做过多重签名询问条件，并在验证算法中验证有效，则称A在游戏中获胜。

![](images/efc06b5ca366ba0e741a3b82a563711b62038a25ba8068dd6b42119a0cb35090.jpg)  
图3攻击游戏交互过程  
Fig.3Attack game interaction process

如果不存在概率多项式签名攻击算法A在如图3游戏中获胜，则称该方案在适应性选择消息下抗存在性伪造攻击。

定理1在随机预言机模型和CDH困难问题假设下，本文提出的多重短签名方案在适应性选择消息攻击下是抗存在性伪造的。

引理1假设存在敌手A 在概率多项式时间 $\textit { t }$ 内以不可忽略的概率 $\varepsilon$ 攻破本文方案，记 $H _ { i } ( i = 1 , 2 )$ 预言机询问、公钥询问和多重签名询问次数分别为 $q _ { H _ { i } }$ $( i = 1 , 2 )$ 、 $q _ { K }$ 和 $q _ { s }$ ，一次询问所需时间分别为 $t _ { H _ { i } }$ 、 $t _ { K }$ 和 $t _ { s }$ ， $\delta \in ( 0 , \frac 1 2 )$ ，则存在算法C,在时间：

$$
t ^ { \prime } { < } t + ( q _ { s } t _ { s } + q _ { K } t _ { K } + 2 q _ { H _ { 1 } } t _ { H _ { 1 } } + 2 q _ { H _ { 2 } } t _ { H _ { 2 } } )
$$

内以不可忽略的优势： $\varepsilon ^ { \prime } \ge ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) \delta ( 1 - \delta ) ^ { q _ { s } }$ 解决CDH问题。

证明设挑战者C 挑战的 CDH 问题实例为：给定$P , a P , b P \in G _ { \mathrm { l } }$ （ $a , b \in Z _ { q } ^ { * }$ 未知)，计算 $a b P \in G _ { 1 }$ 。 $\mathrm { ~  ~ { ~ C ~ } ~ }$ 要借助A的能力求解困难问题实例。

设安全参数为 $k$ ，C运行系统初始化算法，将 $a P$ 作为系统主公钥 $P _ { p u b }$ 的值，生成系统参数$p a r a m s = \{ q , P , e , G _ { 1 } , G _ { 2 } , P _ { p u b } , H _ { 1 } , H _ { 2 } \}$ ，将params发送给 $\mathbf { A }$ 。为了方便后面的签名伪造，C维护一个特定的消息集 $\Omega$ ，并初始化为空。假设A在签名询问前都已做过相应的 $H _ { \mathfrak u }$ 询问和 $H _ { 2 }$ 询问等前置询问，所有记录列表初始化置为空。

a) $H _ { \mathrm { 1 } }$ 询问。C 维护一个列表 $L _ { { \scriptscriptstyle H _ { 1 } } }$ ，记存储结构为数组$( I D _ { i } , K _ { I D _ { i } } , r _ { i } )$ 。当A输入 $( I D , K _ { I D } )$ 进行 $H _ { 1 }$ 预言机询问时，C查询$L _ { H _ { 1 } }$ 中是否存在对应的记录 $( I D , K _ { I D } , r )$ ，如果存在，则返回相应值 $\boldsymbol { r }$ 给A，否则C随机选择一个 $r \in Z _ { q } ^ { * }$ ，将 $\boldsymbol { r }$ 返回给A，并将$( I D , K _ { I D } , r )$ 记录到列表 $L _ { { \scriptscriptstyle H _ { 1 } } }$ 中。

b)公钥询问。C 维护一个列表 $L _ { \kappa }$ ,记存储结构为数组$( I D _ { i } , r _ { i } , y _ { i } )$ 。当A输入 $I D$ 进行公钥询问时，C查询 $L _ { \kappa }$ 中是否存在对应的记录 $( I D , r , y )$ ，如果存在，则返回相应的公钥 $y$ 给A，否则先做 $H _ { \mathrm { 1 } }$ 询问获得 $\boldsymbol { r }$ ，计算公钥 $y = r a P$ 返回给A，同时将 $( I D , r , y )$ 添加到列表 $L _ { \kappa }$ 中。

c) $H _ { 2 }$ 询问。C 维护一个列表 $L _ { H _ { 2 } }$ ，记存储结构为数组$( m _ { i } , T _ { i } , t _ { i } , h _ { i } )$ 。A输入 $( m , T )$ 进行 $H _ { 2 }$ 询问时，C查询 $L _ { H _ { 2 } }$ 中是否已经存在对应的记录 $( m , T , t , h )$ ，如果存在，则返回其中相应值 $h$ 给A，否则：

(a)C 以 $\delta$ 的概率随机选择一个 $t \in Z _ { q } ^ { * }$ ，将 $t b P$ 返回给A，并将 $( m , T , t , h = t b P )$ 记录到 $L _ { H _ { 2 } }$ 中，并将 $m$ 添加到消息集 $\Omega$ 中；

(b)C以 $_ { 1 - \delta }$ 的概率随机选择一个 $t \in Z _ { q } ^ { * }$ ，将 $t P$ 返回给A, 并将 $( m , T , t , h = t P )$ 记录到 $L _ { H _ { 2 } }$ 中。

d)多重签名询问。A输入消息 $m$ 、时间 $T$ 以及$I D _ { 1 } , I D _ { 2 } , \cdots , I D _ { j - 1 }$ 上的部分签名 $S _ { j - 1 }$ ，进行关于身份 $I D _ { j }$ $( 2 \leq j \leq M )$ （204的部分签名询问：

(a)如果 $\ b { m } \in \Omega$ ， $\mathrm { ~  ~ { ~ C ~ } ~ }$ 挑战失败，并输出“FAILURE”（记此事件为 $E _ { \mathrm { l } }$ 事件);

(b)如果 $m \not \in \Omega$ ，C从列表 $L _ { H _ { 1 } }$ 中获得对应的记录$( I D _ { j } , K _ { I D _ { j } } , r _ { j } )$ ，从列表 $L _ { H _ { 2 } }$ 中获得对应的记录 $( I D _ { j } , m , T , t _ { j } , h _ { j } = t _ { j } P )$ ，计算 $S _ { j } = S _ { j - 1 } + I D _ { j } r _ { j } t _ { j } a P$ ， $\mathrm { ~  ~ { ~ C ~ } ~ }$ 把 $S _ { j }$ 作为对消息 $m$ 的部分签名，并将 $S _ { j }$ 返回给A。

经过多项有界式次适应性询问后，A停止询问并输出一个关于消息 $m ^ { * }$ 和有序身份集 $L _ { I D } ^ { * } = \{ I D _ { 1 } ^ { * } , I D _ { 2 } ^ { * } , \cdots I D _ { M } ^ { * } \}$ 的有效多重签名 $S _ { M } ^ { * }$ 。

(a)如果 $m ^ { * } \notin \Omega$ ，则C挑战失败，并输出“FAILURE”,（记此事件为 $E _ { 2 }$ 事件);

(b)如果 $m ^ { * } \in \Omega$ ，则C从列表 $L _ { \kappa }$ 中获取记录$( I D _ { i } ^ { * } , \boldsymbol { r } _ { i } ^ { * } , \boldsymbol { y } _ { i } ^ { * } )$ $( 1 \leq i \leq M )$ ，从列表 $L _ { H _ { 2 } }$ 中获取记录 $( m ^ { * } , T ^ { * } , t ^ { * } , h ^ { * } )$ ，此时 $h ^ { * } = t ^ { * } b P$ ，从而有

$$
e ( S _ { M } ^ { * } , P ) \ = e ( h ^ { * } , \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } y _ { i } ^ { * } )
$$

$$
\begin{array}{c} \begin{array} { l } { { \displaystyle \ } } \\ { { \displaystyle \ } } \\ { { \displaystyle \ } } \\ { { \displaystyle \ } } \\ { { \displaystyle \ } } \end{array} = e ( t ^ { * } b P , \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } r _ { i } ^ { * } a P )  \\ { { \ } } \\ { { \displaystyle \ } } \\ { { \displaystyle \ } } \end{array}
$$

因此 $\mathrm { ~  ~ { ~ C ~ } ~ }$ 可以成功计算出：

$$
a b P = ( \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } r _ { i } ^ { * } t ^ { * } ) ^ { - 1 } S _ { M } ^ { * } \ ,
$$

解困难问题实例的优势满足：

$$
\varepsilon ^ { \prime } \ge ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) \delta ( 1 - \delta ) ^ { q _ { S } } ~ ,
$$

时间限满足：

$$
t ^ { \prime } < t + ( q _ { S } t _ { S } + q _ { K } t _ { K } + 2 q _ { H _ { 1 } } t _ { H _ { 1 } } + 2 q _ { H _ { 2 } } t _ { H _ { 2 } } ) \ _ { \mathrm { ~ \pm ~ } }
$$

因此C以不可忽略的优势 $\varepsilon ^ { \prime }$ 在多项式时间 $t ^ { \prime }$ 内成功的解决了一个CDH问题的实例，这与CDH问题困难性矛盾。所以本文方案是存在性不可伪造的。因此定理1得证。

# 3 应用协议设计与安全性分析

# 3.1协议设计

传统的审批工作流为单路线性工作流，不适合在高并发和时效性要求高的场合，尤其是某些需要多部门配合层层审批的电子政务系统，而采用多层网状分布式架构能有效地解决此类问题，但跨多个服务器可能存在审批流程出现安全问题。利用本文方案可以构造了一个安全的分布式审批工作流协议。具体协议交互过程如下：

(1) $U s e r \to S t a r t ^ { \colon } m \ ;$ （204号(2) $S t a r t  U _ { 1 } \colon m , T$ 1(3)U→U: $S _ { 1 } , I D _ { 1 } , m , T , t _ { i }$ ：(4) $U _ { i - 1 } \ \to \ U _ { i } : \quad S _ { i } , I D _ { 1 } , I D _ { 2 } , \cdots , I D _ { i - 1 } , m , \ T , t _ { i - 1 } \ ,$ 其中 $i = 3 , 4 , \cdots , M$ 1(5) $U _ { M } \ \to \ E n d \ : \quad S _ { M } , I D _ { 1 } , I D _ { 2 } , \cdots , I D _ { M } , \ m , T , t _ { i }$ (6) $E n d$ 验证签名 $S _ { M }$ ，若验证通过，则签名有效，将审批完成结果  
发送给 $I n f o$ ，否则签名无效，退回到 $F a i l ~  { } , ~ { } \ F a i l$ 再将审批失败结果发送  
给 $I n f o$ ：（204号 $\begin{array} { l l } { ( 7 ) I n f o } & {  U s e r } \end{array}$ ：“true”或“false”。

# 3.2协议交互过程的安全性分析

(a)对 $H _ { \mathrm { 1 } }$ 和 $H _ { 2 }$ 询问的每个应答在 $\boldsymbol { Z } _ { \boldsymbol { q } } ^ { * }$ 和 $G _ { \mathrm { { l } } }$ 中是均匀分布的，且应答都是有效的;

1)抗存在性伪造攻击

从3.1协议的交互过程可以看出，节点间传递是单向的，只有一次交互，协议安全性由签名方案的安全性保证。由2.3节签名方案安全性分析可知，本文提出的基于多重短签名的分布式工作流审批协议在适应性选择消息攻击下是抗存在性伪造的。

所以C输出 ${ ( \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } r _ { i } ^ { * } t ^ { * } ) } ^ { - 1 } S _ { M } ^ { * }$ 作为 CDH 困难问题实例的一个解。下面分析C成功解决困难问题的时间和优势：

(b)只有当询问阶段事件 $E _ { \scriptscriptstyle 1 }$ 一直不发生和签名伪造阶段$E _ { 2 }$ 也不发生时，多重签名询问的应答才是有效的。事件 $E _ { 1 }$ 不发生的概率满足： $P ( \neg E _ { 1 } ) \geq ( 1 - \delta ) ^ { q _ { S } }$ ，事件 $E _ { 2 }$ 不发生的概率满足：$P ( \neg E _ { 2 } ) \geq \delta$ 。然而，如果A没有询问 $H _ { 2 }$ 就伪造了一个有效签名，这种模拟就存在缺陷，其发生概率为 $\frac { 1 } { 2 ^ { k } }$ ，所以C成功求

由本文构造的多重短签名方案可知，恶意中间人攻击者若要成功伪造目标身份的签名 $S _ { M }$ ，必须满足以下验证等式：

$$
e ( S _ { M } , P ) = e ( h , \sum _ { j = 1 } ^ { M } I D _ { j } y _ { I D _ { j } } )
$$

而由2.3节签名方案安全性分析可知，当 $P _ { p u b } = a p$ ， ${ h } _ { M } ^ { * } = b P$ 时，有如下等式成立：

2)抗中间人攻击

$$
e ( S _ { \scriptscriptstyle M } ^ { \ast } , P ) = e ( b P , \sum _ { i = 1 } ^ { \cal M } I D _ { i } ^ { \ast } r _ { i } ^ { \ast } a P )
$$

$$
= e ( \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } r _ { i } ^ { * } a b P , P )
$$

此时可以计算出 $a b P = ( \sum _ { i = 1 } ^ { M } I D _ { i } ^ { * } r _ { i } ^ { * } t ^ { * } ) ^ { - 1 } S _ { M } ^ { * }$ ，其中 $S _ { M } ^ { * }$ 为目标身份$I D _ { M } ^ { * }$ 的伪造签名，意味着解决了CDH困难问题。因此恶意中间人攻击者无法伪造目标身份的签名。

3)抗消息重放攻击

在工作流审批过程中采用了时戳机制，对每次用户提交的待审批信息在初次进入审批工作流都会添加时戳 $ { T }$ ，从而保证了信息的新鲜性。任何截取了待审批信息的攻击者都不能通过重放再次通过验证，审批链中每个审批节点会重新对时戳进行验证，若验证有效，则接受签名，否则将信息退回并拒绝继续签名。

# 4签名方案实现与效率分析

# 4.1方案实现

本文在windows764位操作系统的MicrosoftVisualStudio2012开发平台下，采用C语言实现本文签名方案，实现结果如图4所示，方案核心代码如下：

/3.审批链与多重签名  
/计算 $\scriptstyle \mathbf { h } = \mathrm { H } 2 ( \mathbf { m } , \mathrm { T } )$ （204  
element_from_hash(h,m,strlen(m));  
//用户1部分签名  
element_mul(datal,ID1,X1);  
element_mul(S1,datal,h);  
//用户2验证  
element_pairing(left1,S1,P)://等式左边  
element_mul(temp1,ID1,Y1)://ID1\*Y1  
element_pairing(right1,h,templ)://等式右边 $\mathrm { \ s ( h , I D 1 ^ { * } Y 1 }$ ）  
/左右比较  
if (element_cmp(right1,left1))printf("用户1签名无效！\n");//左右不同  
else{printf("用户1签名有效！ $\mathbf { \epsilon } \ln \mathbf { \eta } ^ { \mathbf { + } }$ );//左右相同//用户2部分签名element_mul(datal,ID2,X2);element_mul(temp4,datal,h);element_add(S2,S1,temp4);//用户3验证element_pairing(left1,S2,P)://e(S2.P)element_mul(temp2,ID2,Y2)://ID2\*Y2$/ / \mathrm { I D 1 ^ { * } Y 1 / + I D 2 ^ { * } Y 2 }$ （204element_add(temp3,temp1,temp2);element_pairing(right1,h,temp3);Ⅱ左右比较if (element_cmp(right1,left1))printf("用户2签名无效！ $\ln ^ { \prime \prime } )$ ：else{printf("用户2签名有效！\n");//相同//用户3签名，S3为最终多重签名element_mul(datal,ID3,X3);element_mul(temp5,datal,h);element_add(S3,S2,temp5);//4.多重签名验证element_pairing(left1,S3,P)://e(S3,P)element_mul(temp5,ID3,Y3):/D3 \*Y3element_add(temp6,temp3,temp5);element_pairing(right1,h,temp6);1  
1

# 4.2效率分析

通过查阅文献，其他学者关于多重短签名方案的研究很少，因此本文只与其他多重签名方案进行效率分析。表2为本文方案与其他多重签名方案在签名和验证阶段的比较，其中 $P$ 表示双线性对运算， $\mathbf { \Omega } _ { M }$ 表示标量乘运算， $\mathbf { \Omega } _ { E }$ 表示指数运算。

由表2可见，本文方案在签名阶段需要2次标量乘运算，验证阶段需要1次标量乘运算和2次双线性对运算。与文献[12]方案相比，计算量较接近，与文献[5,11]方案相比，本文无论在计算性能和签名长度上都有优势。

用户1名效  
用户2签名有效！  
e(S3,P) =1075350967734  
8067934588333103533489384436587085529506  
6894928940254985910793400822373251272468  
7996861694479465645124799348399624813728  
6476149038070158281047950268801881133135  
3209895451942145534142007069601354044785  
8153638528044169462399965878435301254797  
6541228221734846502939792297931293406785  
53016844560470  
e<h,ID1\*Y1+ID2\*Y2+ID3\*Y3> =1075350967734  
8067934588333103533489384436587085529506  
6894928940254985910793400822373251272468  
7996861694479465645124799348399624813728  
6476149038070158281047950268801881133135  
3209895451942145534142007069601354044785  
8153638528044169462399965878435301254797  
6541228221734846502939792297931293406785  
53016844560470  
多重签名有效！  
本方 签名与验证所消耗时间：0.238000

Tab 2 Efficiency comparison of multi signature schemes   

<html><body><table><tr><td>方案</td><td>签名</td><td>验证</td><td>签名长度</td></tr><tr><td>文献[5]方案</td><td>4M</td><td>4P+2E</td><td>320</td></tr><tr><td>文献[11]方案</td><td>3M+1E</td><td>3P+1E</td><td>320</td></tr><tr><td>文献[12]方案</td><td>2E</td><td>2E</td><td>2208</td></tr><tr><td>本文方案</td><td>2M</td><td>1M+2P</td><td>160</td></tr></table></body></html>

# 5 基于多重短签名方案的系统应用优势分析

# 5.1系统整体安全性优势分析

一般分布式工作流系统可以满足高并发、时效性要求高的事务管理需求，但往往需要跨多个服务器运行，数据在传输时面临着数据伪造、抵赖、冒充和窜改等信息安全问题，而基于多重短签名方案的分布式工作流系统能有效避免这些问题。多重短签名方案适用于多个用户对同一消息签名的场景，基于该签名方案，分布式工作流系统审批网络中每条审批链的每个审批节点在接收到信息后，都可以对信息的有效性进行验证，从而大大提高数据来源的可靠性和数据传输的完整性，防止审批节点否认与伪造信息。

# 5.2签名性能优势分析

本文提出的基于多重短签名方案，其签名长度减少到160bit，是DSA签名长度的一半，且具有高效的计算效率，在网络状态较差、网络传输不稳定的条件下具有良好的适用性。在移动网络环境下，对于一个长度为1480Byte的消息，短签名长度为20Byte，而普通签名则需 40Byte，交互1次可以节省20Byte 流量。而通信过程中一次传输所能通过的最大数据包大小有限，由于缩短了签名长度，每次交互可以携带更多的业务信息，从而避免因数据量大被分片而导致通信效率降低，因此对事务繁琐、交互频繁的业务系统具有明显的优势。

# 6 结束语

本文提出了一种适用于分布式审批工作流的多重短签名方案，并设计了适用的安全交互协议。在CDH困难问题假设和随机预言机模型下，证明了签名方案在适应性选择消息下是抗存在性伪造的，同时实现了签名方案，并进行了效率分析。该方案适用于需要逐层审批的电子政务系统，采用多层网状分布式架构，满足高并发和时效性高的业务需求，同时签名方案又具有较高的安全性，使系统可以安全高效地运行。

# 参考文献：

[1]Pan Tianheng.Research and implementation of key technologies in multi-agentsystemtosupportdistributedworkflow[C]/IOP Conference Series:Earth and Environmental Science,2018.   
[2]Itakura K,Nakamura K.A public-key cryptosystem suitable for digital multisignatures [J].NECResearch& Development,1983(71):1-8.   
[3]Sahu R A,Padhye S.Identity-based multi-proxy multi-signaure scheme provably secure in random oracle model [J]. Transactions on Emerging Telecommunications Technologies,2015,26(4):547-558.   
[4]杜红珍.适于车载网的安全高效的有序多重签名机制[J].计算机 应用研究，2016，33(10):3105-3108.(Du Hongzhen．Secure and efficient sequential multisignature scheme for VANET[J].Application Research of Computers,2016,33(10):3105-3108.)   
[5]Sarde P,Banerjee A,Dewangan CL.A secure and an efficient ID-based multi-proxymulti-signaturescheme from bilinearpairings[J]. International Journal of Computer Applications,2017,157(1O): 1-6.   
[6]Naoto Y,Eikoh C，Masahiro M,et al.A CDH-based ordered multisignature scheme provably secure without random oracles [J]. Journal of Information Processing,2014,22(2):366-375.   
[7]WangF,Chang CC,Lin C,et al. Secure and efficient identity-based proxy multi-signature using cubic residues [J]. International Journal of Network Security,2016,18(1):90-98.   
[8]杨青，辛小龙，李小光．改进的超椭圆曲线结构化多重盲签名[J]. 工程数学学报，2017,34(3):247-261.(Yang Qing，Xin Xiaolong,Li Xiaoguang.Improved structured blind multisignature schemes based on hyperelliptic curves [J].Chinese Journal of Engineering Mathematics, 2017,34(3):247-261.)   
[9]Wei L,Zhang L,Huang D,et al.Efficient and provably secure identity-based multi-signature schemes for data aggregation in marine wireless sensor networks [C]//Proc of IEEE International Conference on Networking,Sensing and Control. IEEE,2017: 593-598.   
[10] Boneh D,Lynn B,Shacham H. Short signatures from the weil pairing [C]//Proc of the 7th International Conference on Theoryand Application of Cryptology and Information Security.Berlin:Springer, 2001:514-532.   
[11]秦艳琳，吴晓平．高效的无证书有序多重签名方案[J].通信学报， 2013，34(7):105-110.(QinYanlin，Wu Xiaoping.Efficient certificatelesssequential multi-signature scheme [J].Journal on Communications,2013,34(7):105-110.)   
[12]Wei Lifei，Cao Zhenfu，Dong Xiaolei Secure.identity-based multisignature schemes under quadratic residue assumptions[J]. Security and Communication Networks,2013,6(6): 689-701.