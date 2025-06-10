# 适用于物联网通信的无证书聚合签密算法

胡荣磊，李文敬，蒋华，曾萍，王庆瑞，陈雷(北京电子科技学院 通信工程系，北京 100070)

摘要：针对目前无证书聚合签密（CLASC）方案计算效率较低的问题，提出了一个适合于物联网的无双线性对的聚合签密方案。该方案与目前最好方案[15]相比，运算效率提高了近六倍，在聚合签密阶段只需要（ $2 \mathrm { n } { + } 1$ ）次点乘运算，在聚合解签密阶段需要 ( $: 5 \mathrm { n } { + } 1$ ）次点乘运算。基于离散对数问题，在随机预言模型下证明了方案满足机密性和不可伪造性。在聚合签密验证阶段，不需要第三方的秘密信息，方案满足可公开验证性。最后，指出该方案能以较低的计算速率实现较高的安全性，更适合用于物联网。

关键词：无证书聚合签密；物联网；无双线性对；随机预言模型；可公开验证 中图分类号：TP309.7 doi:10.19734/j.issn.1001-3695.2018.05.0446

# Certificateless aggregate signcryption scheme for internet of things communication

Hu Ronglei,Li Wenjing, Jiang Hua, Zeng Ping,Wang Qingrui, Chen Lei (Dept.of Communication Engineering,Beijing Electronic Science &Technology Institute,Beijing 1Ooo7o,China)

Abstract:Aiming atthe problemof lowcomputational efficiencyof thecurrentcertificatelessaggregation signcryption (CLASC)scheme,this paper proposed anaggregate signcryption scheme which is suitableforthe Internet ofthings without bilinearpairings.Compared withthecurentbestscheme[15],theeficiencyofthescheme is increasedbynearly6times.The scheme only needs $( 2 \mathrm { n } + 1 ) ,$ ） times of dot multiplication operation in the aggregate signcryption stage, and $( 5 \mathrm { n } + 1 \cdot$ ）times of dot multiplicationoperationintheaggregateunsigncryption stage.Basedonthe discrete logarithmproblem,the schemesatisfied confidentialityandtheunforgeabilityundertherandomoracle model.Intheaggregate signcryptionverificationphase,thereis no need toprovidethethirdparty'ssecretinformation,sotheshemesatisfiespublicverifiability.Finaly,italsopontedout that the scheme can achieve higher security at lower computation speed and is more suitable for Internet of things.

Key words:certificatelessaggegate signcryption; Interetof things; withoutblinearpairings;andomoracle model; publicly verifiability

# 0 引言

2005年，国际电信联盟首次提出物联网（Intermet of things,IoT)的概念[1]。之后，越来越多的国家投入了对物联网的研究，并取得了丰硕的成果[2-5]。物联网已经广泛运用于食品安全、公共安全、健康监测、智能交通、安防、环保等诸多行业。网络规模从一个实验室到一栋大楼再到一个小区不断扩大，并且出现了不同系统的融合。随着网络规模的扩大，也暴露出物联网系统的问题：物联网终端分布广，而且结构较计算机网络的终端更为简单，面临终端功能欠缺和容易遭受攻击的缺点。而物联网的应用行业如食品安全、入侵检测等则要求物联网能够对突发事件、使用者和管理者提供快速、准确的响应，实现人与物的准确交流，同时还需要保证网络基础设施有一个经济的部署。这就需要系统在一个高效、可靠、安全的模式下协调运行，所以利用密码技术设计安全、高效的算法与协议是IoT研究的侧重点。

保证信息安全的核心技术就是现代密码技术，它可以保证网络环境下信息的保密性、完整性、可用性和抗抵赖性等。其中，保密性可以通过加密的方法来实现，认证性可以用数字签名来实现。如果需要同时实现保密性和认证性，传统的公钥密码技术是使用“先签名再加密”的方式，但这种方法效率低下。1997年，Zheng等人提出了签密的概念并给出了具体的方案。2002年，Baek等人7首次定义了签密方案的安全模型。

在实际应用中，当签密用户较多时，接受者需要同时验证多个密文。为了提高密文的批验证效率，2009 年，Selvi等人[8]结合聚合签名[9的优势提出了聚合签密的概念。2003年，Al-Riyami等人[0]首次提出了无证书密码（certificatelessaggregate signcryption，CLASC）体制，该密码体制不仅避免了公钥证书管理及验证问题，而且很好地解决了密钥托管问题。2008年，Barbosa等人[11首次提出了一个无证书签密方案并给出了其对应的安全模型。随后，Eslami 等人[12]、刘建华等人[13]、牛淑芬等人[14]和Han 等[15]又各自提出无证书签密方案。

通过对聚合密码体制的研究，本文提出了一种适合物联网系统的不需要双线性运算的无证书签密方案。因为没有复杂的双线性对运算，该方案具有较高的运算效率。经证明，该方案满足不可伪造性、机密性和可公开验证性。

# 1 预备知识

定义在 $F _ { _ P }$ （ $\boldsymbol { F } _ { P }$ 表示有 $P$ 个元素的有限域， $P$ 为素数且 $> 3$ ）上椭圆曲线方程为

$$
y ^ { 2 } = x ^ { 3 } + a x + b \quad a , b \in F _ { p }
$$

判别式为

$$
4 a ^ { 3 } + 2 7 b ^ { 2 } \neq 0 { \bmod { p } }
$$

椭圆曲线上的所有解与一个无穷远点 $o$ 构成的一个集合用 $E ( F _ { P } )$ 来表示，即： $E ( F _ { p } ) = \big \{ ( x , y ) \big | x , y \in F _ { p } \big \}$ ，且满足方程r $y ^ { 2 } = x ^ { 3 } + a x + b \} \cup \{ O \}$ ， $E ( F _ { P } )$ 上点的数目用 $q$ 表示，成为椭圆曲线的阶。

# 1.1离散对数问题

离散对数问题（Discretelogarithmproblem，DLP）：设 $G$ 是一个阶为 $\boldsymbol { q }$ 的加法循环群， $P$ 是 $G$ 的生成元，对于 $b \in Z _ { q } ^ { * }$ ，找到整数 $\boldsymbol { a }$ 使得 $b = a P$ 是困难的。

# 1.2计算 Diffie-Hellman 问题

计算Diffie-Hellman 问题（Computational Diffie-HellmanProblem，CDHP）：对于未知的 $a , b \in Z _ { q } ^ { * }$ ，给定（ $_ { a P , b P } ~ ;$ ），计算 $a b P$ 是困难的。

# 2 适合于物联网的不含双线性对的无证书聚合签密方案

本文提出了一个适用于物联网[16的的无证书聚合签密方案。一个完整的物联网由感知节点（sensorynode， $S N _ { i }$ ， $1 \leq i \leq n$ ）、网关节点（gateway node，GN）、云平台服务器（cloud platformserver，CPS）和应用终端（application terminal，AT）组成,,如图1所示。

感知节点的功能是将收集到的数据沿着其他感知节点进行逐跳地传输，并发送到网关节点。网关节点将数据自动保存，并在一定的时间间隔内将自动收集的数据周期性的传输至互联网云平台服务器。云平台服务器将得到的数据发送给应用终端，以供应用终端解密、分析。其中云平台服务器是诚实可靠地，负责系统管理与维护，包括对SN、GN和AT的登记，私钥分发等。云平台服务器与GN，GN与SN，GN与GN之间是通过无线通信。具体实现过程如下：

![](images/816994c86e306cc682698af5bad2d1064ac20c4880fe4e873d26b5a51bae1fdd.jpg)  
图1无线传感器网络的物联网结构  
Fig.1IoT architecture of WSN

a）系统初始化，该算法由GN执行。输入安全参数 $k$ ，选择一个大素数 $q$ （ $q > 2 ^ { k }$ ），设 $G$ 为椭圆曲线的一个循环群， $P$ 为 $\boldsymbol { G }$ 的生成元。选择三个抗碰撞的杂凑函数$H _ { 1 } : \left\{ 0 , 1 \right\} ^ { * } \times G \times G \to Z _ { q } ^ { * } , \quad H _ { 2 } : G \times G \to Z _ { q } ^ { * } , \quad H _ { 3 } , H _ { 4 } : \quad G \times G \times G \times G = G \times G .$ $\to { Z _ { q } } ^ { * }$ 。CPS 随机选择主密钥 $s \in Z _ { q } ^ { * }$ ，并将其秘密保存，计算主公钥： $P _ { p u b } = s P$ ，CPS发布系统公开参数params $= \{ q , P , G , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } \}$ 。

b)密钥生成，该算法由感知节点 ${ S N } _ { i }$ 执行。感知节点 $S N _ { i }$ 随机选取秘密值 $x _ { i } \in { Z _ { q } } ^ { * }$ ，并将其保存，计算 $X _ { i } = x _ { i } P$ ，将( $\mathrm { ~ ; ~ } I D _ { i }$ ， $X _ { i }$ ）发送给CPS。其中， $x _ { i }$ 为私钥， $X _ { i }$ 为公钥。

c)部分私钥生成，该算法由CPS 执行。CPS 随机选择秘密值 $r _ { i } \in { Z _ { q } } ^ { * }$ ，计算 $R _ { i } = r _ { i } P$ ， $h _ { i 1 } = H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } )$ ， $D _ { i } = r _ { i } + s h _ { i 1 }$ ，并将 $( \ R _ { i }$ ，$D _ { i }$ ）通过安全信道发送给各感知节点 $\boldsymbol { S } \boldsymbol { N } _ { i }$ 。其中， $R _ { i }$ 作为用户部分公钥， $D _ { i }$ 作为用户的部分私钥。

这样， ${ S N } _ { i }$ 的私钥为 $S K _ { i } = ( D _ { i } , x _ { i } )$ ，公钥为 $P K _ { i } = ( R _ { i } , X _ { i } )$ 。同样，应用终端AT的私钥为 $S K _ { \scriptscriptstyle B } = ( D _ { \scriptscriptstyle B } , x _ { \scriptscriptstyle B } )$ ，公钥为 $P K _ { _ B } = ( R _ { _ B } , X _ { _ B } )$ □

d)个体签密，该算法由感知节点 $S N _ { i }$ 执行。感知节点 $S N _ { i }$ 发送给AT的消息 $m _ { i }$ 进行签密的步骤如下：

$\textcircled{1}$ 感知节点 $S N _ { i }$ 随机选取 $k _ { i } , t _ { i } \in Z _ { q } ^ { * }$ 。$\textcircled{2}$ 计算 $K _ { i } = k _ { i } P , T _ { i } = t _ { i } P$ ;$\textcircled{3}$ 计算 $Q _ { i 1 } = k _ { i } X _ { { \scriptscriptstyle B } }$ ， $Q _ { i 2 } = t _ { i } ( R _ { B } + \ P _ { p u b } H _ { 1 } ( I D _ { B } , \ R _ { B } , X _ { B } ) ) \ ;$ $\textcircled{4}$ 计算 $h _ { i 2 } = H _ { 2 } ( Q _ { i 1 } , Q _ { i 2 } )$ ;$\textcircled{5}$ 加密， $C _ { i } = h _ { i 2 } \oplus ( m _ { i } \parallel I D _ { i } )$ ；$\textcircled{6}$ 计算 $h _ { i 3 } = H _ { 3 } ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } ) \ , \quad h _ { i 4 } = H _ { 4 } ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } ) \ ,$ （20$\textcircled{7}$ 签名， ${ \cal { S } } _ { i } = k _ { i } + t _ { i } + h _ { i 3 } D _ { i } + h _ { i 4 } x _ { i }$ 。感知节点 ${ S N } _ { i }$ 发送给AT的关于 $m _ { i }$ 的签密为：$\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } ) \quad ( \ 1 \leq i \leq n \ )$ 。

e)聚合签密，该算法由网关节点CN执行。

收到 $n$ 个签密者信息 $\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ （ $1 \leq i \leq n$ ），聚合者CN 计算 $S = \sum _ { i = 1 } ^ { n } S _ { i }$ ，则聚合签密为 $\sigma = < \left\{ K _ { i } , T _ { i } , C _ { i } \right\} _ { i = 1 } ^ { n } ,$ $s >$ ，并将其发送给AT。

f)解签密，该算法由应用终端AT执行。

应用终端AT对 $S N _ { i }$ 发送的签密 $\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ 解密步骤

为：

$\textcircled{1}$ 计算 $Q _ { i 1 } = K _ { i } x _ { B }$ ，$Q _ { i 2 } = T _ { i } ( r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) = T _ { i } D _ { B } \ ;$   
$\textcircled{2}$ 计算 $h _ { i 2 } = H _ { 2 } ( Q _ { i 1 } , Q _ { i 2 } )$ ：  
$\textcircled{2}$ 恢复明文， $( m _ { i } \parallel I D _ { i } ) = C _ { i } \oplus h _ { i 2 }$ ；  
$\textcircled{4}$ 计算 $h _ { i 3 } = H _ { 3 } ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } )$ ，$h _ { i 4 } = H _ { 4 } ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } ) ;$ （204号

验证签名的正确性：

$$
S _ { i } P = K _ { i } + T _ { i } + h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) + h _ { i 4 } X _ { i }
$$

如果成立，证明聚合签密是有效的，输出 $m _ { i } \parallel I D _ { i }$ ，否则，输出为“false”。

$\mathbf { g } )$ 聚合解签密，该算法由应用终端AT执行。

AT对 ${ S N } _ { i }$ 发送的签密 $\sigma = < \left\{ K _ { i } , T _ { i } , C _ { i } \right\} _ { i = 1 } ^ { n }$ $s >$ 解密步骤为：

$\textcircled{1}$ 计算 $Q _ { i 1 } = K _ { i } x _ { B }$ ，$Q _ { i 2 } = T _ { i } ( r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) = T _ { i } D _ { B } \ ;$ （204号  
$\textcircled{2}$ 计算 $h _ { i 2 } = H _ { 2 } ( Q _ { i 1 } , Q _ { i 2 } )$ ;  
$\textcircled{3}$ 恢复明文， $( m _ { i } \parallel I D _ { i } ) = h _ { i 2 } \oplus C _ { i }$ （204号  
$\textcircled{4}$ 计算 $h _ { i 3 } = H _ { 3 } ( C _ { i } ,  { Q _ { i 1 } } ,  { Q _ { i 2 } } , K _ { i } )$ ，$h _ { i 4 } = H _ { 4 } ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } ) ~ .$ 1

验证签名的正确性:

$$
S P = \sum _ { i = 1 } ^ { n } K _ { i } + \sum _ { i = 1 } ^ { n } T _ { i } + \sum _ { i = 1 } ^ { n } [ h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) ] + \sum _ { i = 1 } ^ { n } h _ { i 4 } X _ { i }
$$

如果成立，证明聚合签密是有效的，输出 $m _ { i } \parallel I D _ { i }$ ，否则，输出为“false”

# 3 方案分析

# 3.1 正确性

定理1接收者能够验证签密、聚合签密的正确性，并能得到正确的解密明文 $m _ { i }$ 。

证明a）AT能够验证签密 $\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ （ $1 \leq i \leq n$ ）的正确性。

$$
\begin{array} { r l } & { S _ { i } P = [ k _ { i } + t _ { i } + h _ { i 3 } D _ { i } + h _ { i 4 } x _ { i } ] P } \\ & { \qquad = [ k _ { i } + t _ { i } + h _ { i 3 } ( r _ { i } + s h _ { i 1 } ) + h _ { i 4 } x _ { i } ] P } \\ & { \qquad = K _ { i } + T _ { i } + h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) + h _ { i 4 } X _ { i } } \end{array}
$$

b)AT能够验证聚合签密 $\sigma = < \left\{ K _ { i } , T _ { i } , C _ { i } \right\} _ { i = 1 } ^ { n }$ $s >$ 的正确性。

$$
S P = \sum _ { i = 1 } ^ { n } [ k _ { i } + t _ { i } + h _ { i 3 } D _ { i } + h _ { i 4 } x _ { i } ] P
$$

$$
\begin{array} { l } { { \displaystyle = \sum _ { i = 1 } ^ { n } [ K _ { i } + T _ { i } + h _ { i 3 } D _ { i } + h _ { i 4 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) ] } } \\ { { \displaystyle = \sum _ { i = 1 } ^ { n } K _ { i } + \sum _ { i = 1 } ^ { n } T _ { i } + \sum _ { i = 1 } ^ { n } [ h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) ] + \sum _ { i = 1 } ^ { n } h _ { i 4 } D _ { i } } } \end{array}
$$

c)AT能够得到正确解密明文 $m _ { i }$ □

$$
h _ { i 2 } = H _ { 2 } ( Q _ { i 1 } , Q _ { i 2 } )
$$

$$
\begin{array} { r l } { } & { = H _ { 2 } ( k _ { i } X _ { B } , t _ { i } ( X _ { B } + R _ { B } + P _ { p u b } H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) ) } \\ { } & { = H _ { 2 } ( k _ { i } x _ { B } P , t _ { i } P ( x _ { B } + r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) ) } \\ { } & { = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } ( x _ { B } + r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) ) } \\ { } & { = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } D _ { B } ) = { h _ { i } } ^ { \prime } } \end{array}
$$

由于 ${ S N } _ { i }$ 通过计算 $C _ { i } = h _ { i 2 } \oplus ( m _ { i } \parallel I D _ { i } )$ 对明文进行加密，AT通过计算 $m _ { i } \parallel I D _ { i } = { h _ { i } } _ { 2 } ^ { \prime } \oplus C _ { i }$ 对密文进行解密，又由于 ${ h _ { i } } _ { 2 } = { h _ { i } } _ { 2 } ^ { \prime }$ ，所以可以确保CPS最后得到正确的明文。

# 3.2不可伪造性

定理2在随机预言模型中且DLP难解的情况下，本文提出CLASC方案在适应性选择消息攻击下是存在性不可伪造的（EUF-CLASC-CMA）。

引理1随机预言模型下，如果存在一个概率多项式时间攻击者 $A _ { \mathrm { I } }$ 以不可忽略的概率赢得游戏，那么存在算法 $\check { C } _ { 1 }$ 能够解决DLP问题（其中， $A _ { \mathrm { I } }$ 最多执行 $q _ { H _ { i } }$ （ $i = 1 , 2 , 3 , 4$ ）次 $H _ { i }$ 问询、$q _ { s \kappa }$ 次私钥问询、 $q _ { P S K }$ 次部分私钥问询、 $q _ { P K }$ 次公钥问询以及 $q _ { s c }$ 次签密问询，聚合签名的用户数为 $n$ ）。

证明假设算法 $\check { C } _ { 1 }$ 是一个DLP 的解决者,输入元组为( $P$ ，bP），其中 $b \in Z _ { q } ^ { * }$ 且未知，目标是计算 $b$ ，以 $A _ { \mathrm { I } }$ 作为子程序的挑战者。 $\check { C } _ { 1 }$ 维护以下6个列表 $L _ { ☉ }$ 、 $L _ { 2 }$ 、 $L _ { 3 }$ 、 $L _ { 4 }$ 、 $L _ { _ { I D } }$ 、 $L _ { s c }$ 分别记录 $A _ { \mathrm { I } }$ 对预言机 $\boldsymbol { H } _ { 1 }$ 、 $H _ { 2 }$ 、 $H _ { 3 }$ 、 $H _ { 4 }$ 、创建用户、签密的问询数据，列表初始化均为空。

# 1）系统初始化阶段。

$\check { C } _ { 1 }$ 设 $P _ { p u b } = b P$ （这里 $b$ 默认作为系统主密钥，并且对 $A _ { \mathrm { I } }$ 保密），选择并发送系统参数！ $\mathrm { p a r a m s } { = } \{ q , P , ~ G , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } \}$ 给敌手 $A _ { \mathrm { I } }$ 。

# 2）问询阶段

$\boldsymbol { H } _ { 1 }$ 问询。 $\check { C } _ { 1 }$ 维护列表 $L _ { 1 } ~ = \{ I D _ { i } , R _ { i } , X _ { i } , h _ { i 1 } \}$ 。当 $A _ { \mathrm { I } }$ 输入${ ( I D _ { i } , R _ { i } , X _ { i } ) }$ ， $\check { C } _ { 1 }$ 作出以下回应：

a)若该 $\mathbf { \Phi } ( I D _ { i } , R _ { i } , X _ { i }$ )对应的问询已存在于列表 $L _ { ☉ }$ 中，则返回对应的 $h _ { i 1 }$ 给 $A _ { \mathrm { I } }$ 。

b)否则， $\check { C } _ { 1 }$ 随机选择 $h _ { i 1 } \in Z _ { q } ^ { * }$ ，将（ $I D _ { i } , R _ { i } , X _ { i } , h _ { i 1 } \ .$ )加入列表 $L _ { \mathrm { 1 } }$ 中，并返回 $h _ { i 1 }$ 给 $A _ { \mathrm { I } }$ 。

$H _ { 2 }$ 问询。 $\check { C } _ { 1 }$ 维护列表 $L _ { 2 } = \{ Q _ { i 1 } , Q _ { i 2 } , h _ { i 2 } \}$ 。当 $A _ { \mathrm { I } }$ 输入 $\left( Q _ { i 1 } , Q _ { i 2 } \right)$ $\check { C } _ { 1 }$ 作出以下回应：

a)若该（ $\cdot Q _ { i 1 } , Q _ { i 2 }$ )对应的问询已存在于列表 $L _ { 2 }$ 中，则返回对应的 $h _ { i 2 }$ 给 $A _ { \mathrm { I } }$ 。

b)否则， $\check { C } _ { 1 }$ 随机选择 $h _ { i 2 } \in Z _ { q } ^ { * }$ ，将（ $Q _ { i 1 } , Q _ { i 2 } , h _ { i 2 }$ ）加入列表 $L _ { 2 }$ 中，并返回 $h _ { i 2 }$ 给 $A _ { \mathrm { I } }$ 。

$H _ { 3 }$ 问询。 $\check { C } _ { 1 }$ 维护列表 $L _ { 3 } \ = \{ C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 } \}$ 。当 $A _ { \mathrm { I } }$ 输入$\big ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } \big )$ ， $\check { C } _ { 1 }$ 作出以下回应：

a)若该 $\mathbf { \Phi } ^ { \prime } C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i }$ )对应的问询已存在于列表 $L _ { _ { 3 } }$ 中，则返回对应的 $h _ { i 3 }$ 给 $A _ { \mathrm { I } }$ 。

b)否则， $\check { C } _ { 1 }$ 随机选择 $h _ { i 3 } \in Z _ { q } ^ { * }$ ，将（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 }$ ）加入列表 $L _ { 3 }$ 中，并返回 $h _ { i 3 }$ 给 $A _ { \mathrm { I } }$ 。

$H _ { 4 }$ 问询。 $\check { C } _ { 1 }$ 维护列表 $L _ { 4 } \ = \{ C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 } \}$ 。当A输入$\big ( C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } \big )$ ， $\check { C } _ { 1 }$ 作出以下回应：

a)若该( $\cdot _ { C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } }$ )对应的问询已存在于列表 $L _ { 4 }$ 中，则返回对应的 $h _ { i 4 }$ 给 $A _ { \mathrm { I } }$ 。

b)否则， $\check { C } _ { 1 }$ 随机选择 $h _ { i 4 } \in Z _ { \boldsymbol { q } } ^ { * }$ ，将（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 }$ ）加入列表 $L _ { 4 }$ 中，并返回 $h _ { i 4 }$ 给 $A _ { \mathrm { I } }$ 。

用户创建问询。 $\check { C } _ { 1 }$ 维护初始为空的列表 $L _ { I D _ { i } } = \{ I D _ { i } , h _ { i 1 } , D _ { i }$ $r _ { i } , R _ { i } , x _ { i } , X _ { i } \}$ 。提交用户身份 $I D _ { i }$ ，如果（ $\cdot \ I D _ { i } , h _ { i 1 } , D _ { i } , r _ { i } , R _ { i } , x _ { i } , X _ { i } \ )$ 在 $L _ { _ { I D _ { i } } }$ 中已存在，则忽略；否则， $\check { C } _ { 1 }$ 执行 $\boldsymbol { H } _ { 1 }$ 询问，取得 $h _ { i 1 }$ ，然后：

a)如果 $I D _ { i } = I D _ { j }$ ， $\check { C } _ { 1 }$ 随机选择 $r _ { j }$ ， $x _ { j } \ \in \ Z _ { q } ^ { * }$ ，计算 $R _ { j } = r _ { j } P$ 和$X _ { _ j } = x _ { _ j } P$ ，将 $( \ I D _ { j } , h _ { j 1 } , \bot , r _ { j } , R _ { j } , x _ { j } , X _ { j }$ ）插入 $L _ { _ { I D } }$ ;

b)否则， $\check { C } _ { 1 }$ 随机选择 $D _ { i } , x _ { i } \ \in \ Z _ { q } ^ { * }$ ，计算 $R _ { i } = D _ { i } P - h _ { i 1 } P _ { p u b }$ 和$X _ { i } = x _ { i } P$ ，将（ $\mathrm { \langle ~ } I D _ { i } , h _ { i 1 } , D _ { i } , \bot , R _ { i } , x _ { i }$ ， $X _ { i }$ ）插入 $L _ { _ { I D } }$ 。

部分私钥问询。 $A _ { \mathrm { I } }$ 提交用户身份 $I D _ { i }$ ， $\check { C } _ { 1 }$ 作出以下回应：

a)如果 $I D _ { i } = I D _ { j }$ ， $\check { c }$ 终止游戏;

b)否则， $\check { C } _ { 1 }$ 返回 $D _ { i }$ 给 $A _ { \mathrm { I } }$ 。

私钥问询。 $A _ { \mathrm { I } }$ 提交用户身份 $I D _ { i }$ ， $\check { C } _ { 1 }$ 则返回对应的 $x _ { i }$ 给 $A _ { \mathrm { I } }$ 。

公钥问询。 $A _ { \mathrm { I } }$ 提交用户 $I D _ { i }$ ， $\check { C } _ { 1 }$ 返回 $I D _ { i }$ 对应的公钥 $\textit { ( R _ { i } , X _ { i } }$ ）作为应答。

公钥替换问询。 $A _ { \mathrm { I } }$ 用一个新的公钥（ $X _ { i } ^ { \prime } , R _ { i } ^ { \prime }$ ），替换合法签密者 $I D _ { i }$ 的原公钥（ $X _ { i } , R _ { i } ~ )$ 。

签密问询。 $\check { C } _ { 1 }$ 维护初始为空的列表$L _ { _ { S C } } = \{ m _ { i } , I D _ { i } , I D _ { _ B } , K _ { i } , T _ { i } , h _ { i 2 } , h _ { i 3 } , h _ { i 4 } , S _ { i } , c _ { i } \}$ 。 $A _ { \mathrm { I } }$ 提交待签密消息 $m _ { i }$ 、发送者身份 $I D _ { i }$ 和接受者身份 $I D _ { { } _ { B } }$ □

a)如果 $I D _ { i } = I D _ { j }$ ， $\check { C } _ { 1 }$ 随机选择 $S _ { i } , h _ { i 3 } , h _ { i 4 } , k _ { i } \in \ Z _ { q } ^ { * }$ ，计算 $K _ { i } = k _ { i } P$ ，$T _ { i } = S _ { i } P - h _ { i 3 } x _ { j } - h _ { i 4 } D _ { j } - K _ { i }$ 和 $h _ { i 2 } = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } ( x _ { B } + r _ { B } +$ （204号$s H _ { \scriptscriptstyle 1 } ( I D _ { \scriptscriptstyle B } , R _ { \scriptscriptstyle B } , X _ { \scriptscriptstyle B } ) ) )$ ，查询列表 $L _ { 3 }$ 和 $L _ { 4 }$ ，如果 $L _ { 3 }$ 中存在$\begin{array} { r l } { ( } & { { } C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 } ^ { ' } } \end{array}$ ）或 $L _ { _ 4 }$ 中存在 $\left( \begin{array} { c c c c } { { } } & { { C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 } ^ { ' } } } \end{array} \right)$ ），且$h _ { i 3 } \neq { h _ { i 3 } } ^ { \prime } \times h _ { i 4 } \neq { h _ { i 4 } } ^ { \prime }$ ， $\check { C } _ { 1 }$ 重新选择 $S _ { i } , h _ { i 3 } , h _ { i 4 } , k _ { i }$ ；否则， $\check { C } _ { 1 }$ 计算$C _ { i } = h _ { i 2 } \oplus ( m _ { i } \parallel I D _ { i } )$ ，返回密文 $\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ ：

b)否则 $I D _ { i } \neq I D _ { j }$ ， $\check { C } _ { 1 }$ 按照签密算法进行计算，并根据需要执行 $\textstyle H _ { i }$ （ $i = 1 , 2 , 3 , 4$ ）问询和密钥问询，然后返回签密密文$\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ ：

最后， $\check { C } _ { 1 }$ 将 $\langle ~ m _ { i } , I D _ { i } , I D _ { B } , K _ { i } , T _ { i } , h _ { i 2 } , h _ { i 3 } , h _ { i 4 } , S _ { i } , c _ { i } ~$ ）插入到 $L _ { s c }$ 中，将（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 }$ ）和（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 }$ ）分别插入到 $L _ { 3 }$ 和 $L _ { 4 }$ 。

# 3）伪造阶段

询问阶段结束后， $A _ { \mathrm { I } }$ 提交挑战用户身份（ $I D _ { { _ j } } , { _ { I D _ { { _ B } } } }$ ）、挑战消息 $m _ { j }$ 及其签密密文 $( C _ { j } , K _ { j } , T _ { j } , S _ { j } )$ 。

$\check { C } _ { 1 }$ 计算 $h _ { i 2 } = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } ( x _ { B } + r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , , X _ { B } ) ) )$ ，解密消息$m _ { j } = h _ { i 2 } \oplus C _ { j }$ 。根据分叉引理[17]， $\check { C } _ { 1 }$ 利用预言机重放攻击技术可以得到两个合法的签名 $\{ m _ { j } , I D _ { j } , I D _ { B } , K _ { j } , T _ { j } , h _ { j 3 } , h _ { j 4 } , S _ { j } \}$ 和$\{ m _ { j } , I D _ { j } , I D _ { { \scriptscriptstyle B } } , K _ { j } , ~ T _ { j } , h _ { j 3 } ^ { { \mathrm { ~ \prime ~ } } } , h _ { j 4 } , S _ { j } ^ { { \mathrm { ~ \prime ~ } } } \}$ 。其中 $\begin{array} { r } { S _ { i } \ne S _ { i } ^ { ' } ~ , ~ h _ { j 3 } \ne h _ { j 3 } ^ { ~ \prime } } \end{array}$ ，并且满足：

$$
{ \cal { S } } _ { j } = k _ { j } + t _ { j } + h _ { j 3 } D _ { j } + h _ { j 4 } x _ { i }
$$

$$
{ S _ { j } } ^ { \prime } = { k _ { j } } + { t _ { j } } + { h _ { j 3 } } ^ { \prime } D _ { j } + h _ { j 4 } x _ { i }
$$

那么， $\check { C } _ { 1 }$ 计算：

$$
{ S _ { j } } ^ { \prime } - S _ { j } = { k _ { j } } + { t _ { j } } + { h _ { j 3 } } ^ { \prime } D _ { j } + h _ { j 4 } x _ { i } - \left( { k _ { j } } + { t _ { j } } + { h _ { j 3 } } D _ { j } + h _ { j 4 } x _ { i } \right)
$$

$$
{ \bf \Omega } = ( { h _ { j 3 } } ^ { \prime } - { h _ { j 3 } } ) { \cal D } _ { j }
$$

$b = \frac { ( D _ { j } - r _ { j } ) } { H _ { 1 } ( I D _ { j } , R _ { j } , X _ { j } ) } = \frac { S _ { j } ^ { \prime } - S _ { j } - ( { h _ { j 3 } } ^ { \prime } - h _ { j 3 } ) r _ { j } } { ( { h _ { j 3 } } ^ { \prime } - h _ { j 3 } ) H _ { 1 } ( I D _ { j } , R _ { j } , X _ { j } ) }$ S′-Sj-(hj'-h3）²,作为对DLP的回

答。

因此， $\check { C } _ { 1 }$ 成功获得 DLP 困难问题的一个实例。 $\check { C } _ { 1 }$ 能够成功解决DLP困难问题的优势为 $\varepsilon ^ { \prime } = \frac { 1 } { q _ { P S K } + n } \Biggl ( 1 - \frac { 1 } { q _ { P S K } + n } \Biggr ) ^ { q _ { P S K } + n - 1 } \varepsilon$ 。证毕。

引理2随机预言模型下，如果存在一个概率多项式时间攻击者 $A _ { \mathrm { I I } }$ 以不可忽略的概率赢得游戏，那么存在算法 $\check { C } _ { 2 }$ 能够解决DLP问题（其中， $A _ { \mathrm { I I } }$ 最多执行 $q _ { H _ { i } }$ （ $i = 1 , 2 , 3 , 4$ ）次 $\boldsymbol { H } _ { i }$ 问询、$q _ { s \kappa }$ 次私钥问询、 $q _ { P S K }$ 次部分私钥问询、 $q _ { P K }$ 次公钥问询以及 $q _ { s c }$ 次签密问询，聚合签名的用户数为 $n$ ）。

证明：假设算法 $\check { C } _ { 2 }$ 是一个DLP的解决者，输入元组为（ $P$ ，bP），其中 $b \in Z _ { q } ^ { * }$ 且未知，目标是计算 $b$ ，以 $A _ { \mathrm { I } }$ 作为子程序的挑战者。 $\check { C } _ { 1 }$ 维护以下6个列表 $L _ { ☉ }$ 、 $\boldsymbol { L } _ { 2 }$ 、 $L _ { 3 }$ 、 $L _ { 4 }$ 、 $L _ { _ { I D } }$ 、 $L _ { s c }$ 分别记录 $A _ { \mathrm { I } }$ 对预言机 $\boldsymbol { H } _ { 1 }$ 、 $H _ { 2 }$ 、 $H _ { 3 }$ 、 $H _ { 4 }$ 、创建用户、签密的问询数据，列表初始化均为空。

# 1）系统初始化阶段

设 $P _ { p u b } = s P \qquad , \qquad s \in { \cal Z } _ { q } ^ { * }$ ，生成系统参数params $\mathsf { \Omega } _ { 5 } = \{ q , P , \ G , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } \}$ 。 $\check { C } _ { 2 }$ 发送（ $q , P , \ G , P _ { p u b } , s$ ）给 $A _ { \parallel }$ 。

# 2）问询阶段

$A _ { \mathrm { I I } }$ 执行多项式有界次的以下问询。

$H _ { 1 }$ 、 $H _ { 2 }$ 、 $\boldsymbol { H } _ { 3 }$ 和 $H _ { 4 }$ 问询，与定理1相同。

用户创建问询。 $\check { C } _ { 2 }$ 维护初始为空的列表$L _ { I D _ { i } } ~ = ~ \{ I D _ { i } , h _ { i 1 } , D _ { i } , r _ { i } , R _ { i } , x _ { i } , X _ { i } \}$ 。提交用户身份 $I D _ { i }$ ，如果$\{ I D _ { i } , h _ { i 1 } , D _ { i } , r _ { i } , R _ { i } , x _ { i } , X _ { i } \}$ 在 $L _ { { I D } _ { i } }$ 中已存在，则忽略；否则， $\check { C } _ { 2 }$ 执行 $H _ { \mathfrak u }$ 询问，取得 $h _ { i 1 }$ ，然后：

a)如果 $I D _ { i } = I D _ { j }$ ，令 $X _ { _ j } = b P$ ，计算 $R _ { j } = r _ { j } P$ 和$D _ { j } = r _ { j } + s H _ { 1 } ( I D _ { j } , R _ { j } , X _ { j } )$ ，将（ $I D _ { j } , h _ { j 1 } , \bot , r _ { j } , R _ { j } , x _ { j } , X _ { j }$ ）插入 $L _ { _ { I D } }$ ：

b)否则， $\check { C } _ { 2 }$ 随机选择 $D _ { i }$ ， $x _ { i } \in Z _ { q } ^ { * }$ ，计算 $R _ { i } = r _ { i } P$ 、 $D _ { i } = r _ { i } + s h _ { i 1 }$ 和 $X _ { _ i } = x _ { _ i } P$ ，将（ $I D _ { i } , h _ { i 1 } , D _ { i } , \bot , R _ { i } , x _ { i } , X _ { i }$ ）插入 $L _ { _ { I D _ { i } } }$ 。

部分私钥问询。 $A _ { \mathrm { I I } }$ 提交用户身份 $I D _ { i }$ ， $\check { C } _ { 2 }$ 则返回对应的 $D _ { i }$ 给 $A _ { \mathrm { I I } }$ □

私钥问询。 $A _ { \mathrm { I I } }$ 提交用户身份 $I D _ { i }$ ， $\check { C } _ { 2 }$ 作出以下回应：

a)如果 $I D _ { i } = I D _ { j }$ ， $\check { C } _ { 2 }$ 终止游戏;

b)否则， $\check { C } _ { 2 }$ 返回 $x _ { i }$ 给 $A _ { \mathrm { I } }$ 。

公钥问询。 $A _ { \mathrm { I I } }$ 提交用户 $I D _ { i }$ ， $\check { C } _ { 2 }$ 返回 $I D _ { i }$ 对应的公钥 $\textit { ( R _ { i } , X _ { i } }$ ）作为应答。

公钥替换问询。 $A _ { \mathrm { I I } }$ 提交用户身份 $I D _ { i }$ ，以及替换公钥 $X _ { i } ^ { \prime }$ ，如果 $I D _ { i } = I D _ { j }$ ， $\check { C } _ { 2 }$ 终止游戏；否则 $\check { C } _ { 2 }$ 用 $X _ { i } ^ { \prime }$ 替换替换 $I D _ { i }$ 原有的公钥 $X _ { i }$ （20

签密问询。 $\check { C } _ { 2 }$ 维护初始的为空的列表 $L _ { \scriptscriptstyle S C } = \{ m _ { \scriptscriptstyle i } , I D _ { \scriptscriptstyle i } , I D _ { \scriptscriptstyle B }$ $K _ { i } , T _ { i } , h _ { i 2 } , h _ { i 3 } , S _ { i } , c _ { i } \}$ 。 $A _ { \mathfrak { h } }$ 提交待签密消息 $m _ { i }$ 、发送者身份 $I D _ { i }$ 和接受者身份 $I D _ { { } _ { B } }$ 。

a)如果 $I D _ { i } = I D _ { j }$ ， $\check { C }$ 随机选择 $S _ { i } , h _ { i 3 } , t _ { i } \ \in \ Z _ { q } ^ { * }$ ，计算 $T _ { i } = t _ { i } P$ ，$K _ { i } = S _ { i } P - h _ { i 3 } ( x _ { j } + D _ { j } ) - T _ { i }$ 和 $h _ { i 2 } = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } ( x _ { B } + r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B }$ $\textstyle { \boldsymbol { X } } _ { B } ) ) _ { \boldsymbol { \cdot } } ^ { \phantom { \dagger } }$ ，查询列表 $L _ { 3 }$ 和 $L _ { 4 }$ ，如果 $L _ { _ { 3 } }$ 中存在 $( \ C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 } ^ { \textit { \prime } } )$ 或 $L _ { 4 }$ 中存在（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 } ^ { \mathrm { ~ \tiny ~ \prime ~ } } )$ ，且 $h _ { i 3 } \neq { h _ { i 3 } } ^ { \prime } \times { h _ { i 4 } } \neq { h _ { i 4 } } ^ { \prime }$ ， $\check { C } _ { 2 }$ 重新选择$S _ { i } , h _ { i 3 } , h _ { i 4 } , t _ { i }$ ；否则， $\check { C } _ { 2 }$ 计算 $C _ { i } = h _ { i 2 } \oplus ( m _ { i } \parallel I D _ { i } )$ ，返回密文$\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ ：

b)否则 $I D _ { i } \neq I D _ { j }$ ， $\check { C } _ { 1 }$ 按照签密算法进行计算，并根据需要执行 $\boldsymbol { H } _ { i }$ （ $i = 1 , 2 , 3 , 4$ ）问询和密钥问询，然后返回签密密文$\sigma _ { i } = ( C _ { i } , K _ { i } , T _ { i } , S _ { i } )$ ：

最后， $\check { C } _ { 2 }$ 将 $( \ m _ { i } , I D _ { i } , I D _ { B } , K _ { i } , T _ { i } , h _ { i 2 } , h _ { i 3 } , h _ { i 4 } , S _ { i } , c _ { i }$ ）插入到 $L _ { s c }$ 中，将（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , K _ { i } , h _ { i 3 }$ ）和（ $C _ { i } , Q _ { i 1 } , Q _ { i 2 } , T _ { i } , h _ { i 4 }$ ）分别插入到 $L _ { 3 }$ 和 $L _ { 4 }$ 。

# 3）伪造阶段

询问阶段结束后， $A _ { \mathrm { I I } }$ 提交挑战用户身份（ $I D _ { { _ j } } , I D _ { { _ B } }$ ）、挑战消息 $m _ { j }$ 及其签密密文 $( C _ { j } , K _ { j } , T _ { j } , S _ { j } )$ □

$\check { C } _ { 2 }$ 计算 $h _ { i 2 } = H _ { 2 } ( K _ { i } x _ { B } , T _ { i } ( x _ { B } + r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , \ X _ { B } ) ) )$ ，解密消息$m _ { j } = h _ { i 2 } \oplus C _ { j }$ 。根据分叉引理[17]， $\check { C } _ { 2 }$ 利用预言机重放攻击技术可以得到两个合法的签名 $\{ m _ { j } , I D _ { j } , I D _ { s } , K _ { j } , T _ { j } , h _ { j 2 } , h _ { j 3 } , h _ { j 4 } , S _ { j } \}$ 和$\{ m _ { j } , I D _ { j } , I D _ { { \scriptscriptstyle B } } , K _ { j }$ ， $T _ { j } , h _ { j 2 } , h _ { j 3 } , h _ { j 4 } ^ { ' } , S _ { j } ^ { ' } \}$ 。其中 $S _ { i } \ne S _ { i } ^ { ' } ~ , ~ h _ { j 3 } \ne h _ { j 3 } ^ { ~ \prime }$ ，并且满足：

$$
\begin{array} { l } { { S _ { j } = k _ { j } + t _ { j } + h _ { j 3 } D _ { j } + h _ { j 4 } x _ { i } } } \\ { { { } } } \\ { { S _ { j } ^ { ' } = k _ { j } + t _ { j } + h _ { j 3 } D _ { j } + h _ { j 4 } { ' } x _ { i } } } \end{array}
$$

那么 $\check { C } _ { 2 }$ 计算：

$$
{ S _ { j } } ^ { \prime } - S _ { j } = { k _ { j } } + { t _ { j } } + { h _ { j 3 } } { D _ { j } } + { h _ { j 4 } } ^ { \prime } x _ { j } - \left( { k _ { j } } + { t _ { j } } + { h _ { j 3 } } { D _ { j } } + { h _ { j 4 } } x _ { i } \right)
$$

$$
{ \bf \Phi } = ( { h _ { j } } _ { 4 } ^ { \prime } - { h _ { j } } _ { 4 } ) x _ { j }
$$

$b = x _ { j } = \frac { S _ { j } ^ { \prime } - S _ { j } } { h _ { j 4 } ^ { \prime } - h _ { j 4 } }$ 作为对 DLP 的回答。

因此， $\check { C } _ { 2 }$ 成功获得 DLP 困难问题的一个实例。 $\check { C } _ { 2 }$ 能够成功解决DLP 困难问题的优势为 $\varepsilon ^ { \prime } = \frac { 1 } { q _ { P S K } + n } \Biggl ( 1 - \frac { 1 } { q _ { P S K } + n } \Biggr ) ^ { q _ { P S K } + n - 1 } \varepsilon$ 。证毕。

# 3.3 机密性

定理3随机预言模型下，基于CDHP，本文提出的CLASC方案在适应性选择密文攻击下是不可区分的，即IND-CLASC-CCA2安全。

引理3随机预言模型下，如果存在概率多项式时间敌手

$A _ { \mathrm { I } }$ （或 $A _ { \mathrm { I I } }$ ）以不可忽略的概率赢得游戏，则存在挑战者 $\check { c }$ 能够以不可忽略的概率解决CDPH的一个实例。

引理3的证明方法与文献[12]机密性证明方案类似，限于篇幅，略去此部分。

# 3.4 可公开验证性

本文方案中，当签密发送者和签名接受者关于聚合签密密文的真伪发生争执时，任意第三方均可验证下面等式：

$$
S P = \sum _ { i = 1 } ^ { n } K _ { i } + \sum _ { i = 1 } ^ { n } T _ { i } + \sum _ { i = 1 } ^ { n } [ h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) ] + \sum _ { i = 1 } ^ { n } h _ { i 4 } X _ { i }
$$

为该等式的验证无需接受者的参与，且不需要任何签密者的秘密信息，因此方案具有可公开验证性。

# 3.5性能分析

为了便于比较签密方案的计算效率，假设参与签密的用户有 $n$ 个，这里考虑三种运算：指数运算（标志为 $e$ ）、群 $G$ 上的乘法运算（标志为 $s$ ）、双线性对运算（标志为 $p$ ）。相比较前三种运算，散列运算和异或运算的耗时对整体效率的影响可以忽略不计。在本文方案中，签密阶段， $n$ 个签密者在计算$Q _ { i 1 } = k _ { i } X _ { B }$ $, Q _ { i 2 } = t _ { i } ( R _ { B } + P _ { p u b } H _ { 1 } ( I D _ { B } , \ R _ { B } , X _ { B } ) )$ 时，需要用到 $2 n + 1$ 次点乘运算（ $P _ { { p u b } } H _ { 1 } ( I D _ { { B } } , \ R _ { { B } } , X _ { { B } } )$ 的值固定，只需计算一次）；在解签密阶段， 验证等式计算$S P = \sum _ { i = 1 } ^ { n } K _ { i } + \sum _ { i = 1 } ^ { n } T _ { i } ~ + \sum _ { i = 1 } ^ { n } [ h _ { i 3 } ( R _ { i } + P _ { p u b } H _ { 1 } ( I D _ { i } , R _ { i } , X _ { i } ) ) ] + \sum _ { i = 1 } ^ { n } h _ { i 4 } X _ { i }$ 和计算$Q _ { i 1 } = K _ { i } x _ { B }$ ， $Q _ { i 2 } = T _ { i } ( r _ { B } + s H _ { 1 } ( I D _ { B } , R _ { B } , X _ { B } ) ) = \ T _ { i } D _ { B } $ ，共需要 $5 n + 1$ 次点乘运算。参考文献[18]所给的实验数据，三种运算所花费的时间代价（以毫秒为单位）分别为 $p \approx 2 0 . 0 1$ ， $E \approx 1 1 . 2 0$ ， $s \approx 0 . 8 3$ 。从表1中看出，对同样多的消息进行聚合签密，本方案相比于文献[12\~15]的方案相比，运算效率提升很多，与运算效率相对较高的方案相比，运算效率提升了近6倍。从方案的安全性能来看，只有文献[13]和本方案满足公开验证性。综合考虑方案的运算效率和安全性，本方案优于以上四种方案。

表1聚合签密方案运算量和安全性能比较  
Table 1 Comparison of computation and security performance of aggregation signcryption   

<html><body><table><tr><td>方案</td><td>签密</td><td>解签密</td><td>运算总量</td><td>代价估耗</td><td>安全性</td><td>公开验证性</td></tr><tr><td>文献[12]</td><td>np +ne</td><td>(2n +3)p +(n +1)s</td><td>ne +(3n+3)p +(n+1)s</td><td>72.06n + 60.86</td><td>可证安全</td><td>是</td></tr><tr><td>文献[13]</td><td>n(p +2s)</td><td>(n+3)p</td><td>(2n +3)p + 2ns</td><td>41.68n + 60.03</td><td>可证安全</td><td>香</td></tr><tr><td>文献[14]</td><td>ne +4ns</td><td>(n+2)p+ns</td><td>ne +5ns +(n +2)p</td><td>35.36n + 40.02</td><td>可证安全</td><td>香</td></tr><tr><td>文献[15]</td><td>3ne + np + ns</td><td>np + ns</td><td>2np + 3ne + 2ns</td><td>75.28n</td><td>可证安全</td><td>香</td></tr><tr><td>本方案</td><td>(2n + 1)s</td><td>(5n + 1)s</td><td>(7n + 2)s</td><td>5.81n + 1.66</td><td>可证安全</td><td>是</td></tr></table></body></html>

# 4 结束语

聚合签密因其加密、签名和批量处理的特性在物联网环境中具有很大的应用价值。为了提高无证书聚合签密的计算效率，在随机预言模型的基础上，提出了无双线性对的聚合签密方案，经证明该方案满足机密性、不可伪造性和可公开验证性。与已有的方案相比，本方案的计算速度更快，更适合在物联网中应用。

# 参考文献：

[1]Presser M,BarnaghiP,Eurich M,et al.The sensei project: integrating the physical world with the digital world of the network of the future [J].IEEE Communications Magazine,2009,47 (4): 1-4.   
[2]Han Jinsoo,Park W K,Lee I,et al.Home-to-home communications for smart community with Internet of things [C]// Proc of Consumer Communications& NetworkinG Conference.Piscataway,NJ:IEEE Press,

2017:720-723.

[3]Lanotte R,Merro M.A semantic theory of the Internet of things [C]// Proc of International Conference on Coordination Languages and Models. Berlin: Springer, 2016: 157-174.   
[4]Palade A,Cabrera C,Li Fan,et al.Middleware for Internet of things: an evaluation ina small-scale IoT environment [J]. Journal of Reliable Intelligent Environments,2018,1(4): 1-21.   
[5]Baldini G, Skarmeta A,Fourneret E,et al. Security certification and labelling in internet of things [C]//Proc of the 3rd IEEE World Forum on Internet of Things. Piscataway,NJ: IEEE Press,2016: 627-632.   
[6] Zheng Yuliang.Digital signcryption or how to achieve cost (signature & encryption) <<cost (signature) +cost (encryption) [Cl//Proc of International Cryptology Conference on Advances in Cryptology. Berlin: Springer,1997: 165-179.   
[7]Baek J,Steinfeld R,Zheng Yuliang.Formal proofs for the security of signcryption [J]. Journal of Cryptology,2007,20 (2): 203-235.   
[8] Selvi D S,Vivek S S，Shriram J，et al.Identity based aggregate signcryption schemes [C]// International Conference on Progress in Cryptology-indocrypt. Berlin: Springer,20o9:378-397.   
[9]张玉磊，李臣意，王彩芬，等．无证书聚合签名方案的安全性分析和改 进[J]．电子与信息学报，2015，37(8):1994-1999.(Zhang Yulei，Li Chenyi，Wang Caifen,et al.Security analysis and improvements of certificateless aggregate signature schemes [J]. Journal of Electronics & Information Technology,2015,37 (8):1994-1999.)   
[10] Al-Riyami S S,Paterson K G. Certificateless public key cryptography [J]. Asiacrypt,2003,2894 (2): 452-473.   
[11] Barbosa M,Farshim P.Certificateless signcryption [C]// Proc of ACM Symposium on Information, Computer and Communications Security. New York: ACM Press,2008:369-372.   
[12] Eslami Z,Pakniat N. Certificateless aggregate signcryption: security model and a concrete construction secure in the random oracle model [J]. Journal ofKing Saud University-Computer and Information Sciences,2O14,26 (3): 276-286.   
[13]刘建华，赵长啸，毛可飞．高效的无证书聚合签密方案[J].计算机工 程与应用,2016,52(12):131-135.(Liu Jianhua,Zhao Changxiao,Mao Kefei.Efficient certificateless aggregate signcryption scheme based on XOR [J]．Computer Engineering and Applications，2016,52(12): 131-135.)   
[14]牛淑芬，牛灵，王彩芬，等．一种可证安全的异构聚合签密方案[J]. 电子与信息学报,2017,39 (5):1213-1218.(Niu Sufen,Niu Ling,Wang Caifen,et al. A provable aggregate signcryption for heterogeneous systems [J].Journal of Electronics& Information Technology，2017,39(5): 1213-1218.)   
[15] Han Yiliang，Chen Fei．The multilinear maps based certificateless aggregate signcryption scheme [C]// Proc of International Conference on Cyber-Enabled Distributed Computingand Knowledge Discovery. Piscataway,NJ:IEEE Press,2015:92-99.)   
[16] Lin Jie,Yu Wei,Zhang Nan,et al.A survey on internet of things: architecture,enabling technologies,security and privacy,and applications [J].IEEE Internet of Things Journal,2017,4(5): 1125-1142   
[17]Pointcheval D,Stern J. Security arguments for digital signatures and blind signatures [J]. Journal of Cryptology,2000,13 (3): 361-396.   
[18] Deng Lunzhi, Zeng Jiwen,Qu Yunyun. Certificateless proxy signature from rsa [J].Mathematical Problems in Engineering,2014,2014(9): 1-10.