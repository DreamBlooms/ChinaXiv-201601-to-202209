# 一种支持撤销的位置分层属性加密研究

沈学利，崔海韵，陈鑫彤(辽宁工程技术大学 电子与信息工程学院，辽宁 葫芦岛 125105)

摘要：基于属性加密的位置分层访问方案允许用户依据自身的情况灵活设置自己的位置访问信息，不仅解决了社交网络中位置共享问题，还在算法上进行改进使解密效率得以提升。但在系统运行过程中，存在用户有更正自己属性信息的需求或运行过程中部分私钥遭泄露的可能，因此支持撤销对于系统安全非常必要。基于此提出了一种支持撤销的位置分层属性加密方案，将部分解密运算外包给解密服务器，并结合了双因子身份认证的方法。该方案在减少用户的计算代价的同时，提高了算法的安全性。

关键词：属性加密；撤销；位置分层；解密外包；双因子身份认证中图分类号：TP309.7 doi:10.19734/j.issn.1001-3695.2018.06.0477

# Research on encryption of location hierarchical attributes supporting revocation

Shen Xueli, Cui Haiyun, Chen Xintong (School ofElectronics & Information Enginering Liaoning Technical University,Huludao Liaoning 125105,China)

Abstract:The location-based hierarchical accesschemebased onatribute encryption allows users toflexiblysettheirown locationaccessinformationaccrdingtotheirownsituation.Notonlysolving theproblemoflocationsharing insocialnetworks, but alsoimprovingthealgorithmtoimprovethedecryptioneffciency.However,duringtheoperationof tesystem,there isa possibilitythatthe user has coected hisown atribute information or the private key maybe leaked during the operation, supportingthe withdrawal is very necesary forsystem security.Basedonthis,a location hierarchical atributeencryption scheme supportingundo is proposed,whichoutsources partoftedecryptionoperationtothe decryptionserverandcombines the methodoftwo-factoridentityauthentication.This solutionreduces theuser'scomputationalcostandimproves thesecurity of the algorithm.

Keywords:atribute encryption;revocation;hierarchicalaccesscontrol;outsourceddecryption;two-factorauthentication

# 0 引言

云存储是一种基于云计算建立起来的网络存储技术，随着互联网的飞速发展，云存储也成为信息技术领域研究的热点。近年来各种定位服务逐渐增多，在分布式开放的网络环境下，社交网络中的用户可以享受多样性的定位服务，比如车辆的导航服务，酒店查询服务等。但用户在享受服务多功能性的同时，也注意到了社交软件中存在的安全性问题。为了提高自身定位信息的安全性，相关的位置信息保护方法也得到重视。目前保护个人位置信息的常用方法大致可以分成两类：空间位置隐藏技术[1和虚假定位技术[2]，这两种方法都是通过模糊用户的位置信息、制造虚假信息来混淆攻击者，以达到保护信息的目的，但是都不能允许用户进行细粒度的访问控制，也不能根据用户的特定需求提供最简洁的位置信息，同时也很容易导致信息被泄露。

针对上述问题，Lin等人[在传统的基于属性加密算法[]的基础上提出了基于属性加密的新算法，并借鉴文献[4,5]中的线性秘密共享方案设计了一种位置分层访问控制方案，该方案以属性加密和对称加密混合的方式加密用户位置信息，让用户可以根据自己的需求设定位置信息访问策略。但是用户权限会随着用户修改属性发生变化，Lin等人所提的方案中，并不能实现属性的及时撤销。Pirretti等人[7]于2006年又提出了密文策略的属性撤销方案，其思想是中央机构周期性更新被设定有效期的属性的版本，撤销指定属性即可达到用户撤销的目的。Hur 等人[8在2011年提出一种支持撤销的属性基加密方案，可以在外包的环境下实现细粒度访问控制，但不能抵抗用户合谋攻击。Zhao 等人[9提出了一个两方计算的可撤销CP_ABE方案，需要将属性中心拆分为属性权威和中央控制。

在分布式开放的网络环境下，对使用者的身份认证是确保安全的基础和关键。双因子身份认证技术弥补了传统密码认证方法中的存在的某些弊端。也为用户登录提供了安全性保障。1999 年，Yang 等人[o]推出了第一个基于智能卡的密码认证方案，它并没有设置一个敏感信息存储表，这是该方案相较于传统方案的一个关键优势。为了保护与静态用户相关的ID信息，Das 等人[1]提出了一种可行方法，即采用“动态ID技术”，解决了信息遭受攻击的问题。2015年，Wang等人通过对两个最重要的匿名双因子方案[12:13]进行密码分析后提出了一个分布式系统中的双因子身份验证方案[14]，经分析与验证，该方案安全性更强。

为了解决上述问题，参考已有的支持撤销的CP_ABE 解密方案[15]，本文提出了一种可撤销的位置分层属性加密方案，本方案支持细粒度的属性撤销和用户撤销，提高了系统的安全性。为了减少用户的计算负担将解密时复杂的计算外包给代理商，使系统更为灵活。又结合已有的匿名双因子认证机制[14]，进一步保护用户的隐私与数据安全。

# 1 相关知识

# 1.1双线性映射

$G _ { \mathrm { { \scriptscriptstyle 1 } } }$ 和 $G _ { 2 }$ 是乘法循环群,且阶为素数p.满足下列属性:1)双线性  
对于 $\forall u , \nu \in G _ { 1 } , a , b \in Z _ { p }$ ，有 $e ( u ^ { a } , \nu ^ { b } ) = e ( u , \nu ) ^ { a b }$ ;2)非退化性  
$\exists u , \nu \in G _ { \scriptscriptstyle 1 }$ 使得 $e ( u , \nu ) \not = 1$ ·  
3）可计算性  
对于 $\forall u , \nu \in G _ { 1 }$ ,可以有效计算出 $\boldsymbol { e } ( u , \nu )$ 。

# 1.2线性秘密共享

定义参与者集合为 $\mathrm { ~ \bf ~ P ~ }$ ，如果 $\mathrm { ~ \bf ~ P ~ }$ 上的某一个秘密共享方案满足如下两个条件，则为线性的。

a）每个参与者的秘密值表示 $Z _ { p }$ 上的一个向量。

b） $\boldsymbol { \mathscr { M } }$ 是一个 $l \times h$ 的矩阵，映射函数将矩阵 M 的每一行对应一个属性值，第i行对应第i个属性。随机选择列向量$V = \left( s , r _ { 2 } , . . . , r _ { n } \right)$ ，其中 $s \in Z _ { p }$ ， $s$ 表示秘密值 $\mathrm { , r }$ 为 $Z _ { p }$ 中的一组随机数。令 $\lambda _ { i } = M _ { i } \cdot \nu , i = 1 , 2 , . . . , l , \lambda _ { i }$ 是秘密 $s$ 的第i个值， $\lambda _ { i }$ 属于参与者 $\rho ( i )$ 。

每个线性秘密共享方案都满足线性重组的性质：假设 $\mathcal { B }$ 是访问结构A的一个线性秘密共享方案，S是A中的任意授权集合，定义 $I = \{ i : \rho ( i ) \in S \}$ ,如果 $\{ \lambda _ { i } \}$ 是秘密S的有效值，就一定存在常数集合 $\{ \omega _ { i } \in Z _ { p } \} _ { i \in I }$ ，使得 $\sum _ { i \in I } \omega _ { i } \lambda _ { i } = s$ ：

# 1.3Diffie-Hellman DBDH 假设

挑战者基于系统的安全参数，随机选取 $a , b , c , t \in Z _ { p }$ 。定义双线性映射 $e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ ， $\mathrm { \bf ~ g }$ 为 $G _ { \mathrm { { \scriptscriptstyle 1 } } }$ 的生成元，素数 $\mathrm { ~ \bf ~ P ~ }$ 是群组$G _ { 1 } , G _ { 2 }$ 的阶。

敌手优势为 $\mathrm { P r } [ b = b ^ { \prime } ] - 1 / 2$ ，且无法以不可忽略的优势从中 $( g ^ { a } , g ^ { b } , g ^ { c } , e ( g , g ) ^ { t } )$ 判定出 $( g ^ { a } , g ^ { b } , g ^ { c } , e ( g , g ) ^ { a b c } )$ ：

# 1.4双因子身份认证

双因子身份认证分以下两个阶段：注册阶段，验证阶段。其中 S为服务器,x为S的私钥,哈希函数H():{0,1}\*→{0,1}，P为椭圆曲线 $E _ { p }$ 的基点，用户注册时间为 $\mathrm { \Delta T }$ 。

1)注册阶段

用户 $U _ { i }$ 选择自己的身份 $I D _ { i }$ 并且自由设置密码 $P W _ { i }$ 。再选择一组随机数 $n _ { i }$ 。随后用户通过安全信道将信息发送至服务器 S。则服务器从用户 $U _ { _ i }$ 处收到请求

$$
\{ I D _ { i } , H , ( P W _ { i } \parallel n _ { i } ) \}
$$

服务器S选择随机数 $m _ { i }$ 并计算安全的参数

$$
Q = H ( P W _ { i } \parallel n _ { i } ) \oplus H ( I D _ { i } \parallel x \parallel T )
$$

继续发送给用户：S→U,:Q

用户将私钥 $n _ { i }$ ，安全参数Q存入智能卡中。

2)验证阶段

当用户 $U _ { i }$ 想要访问服务器S时，用户将插入智能卡，并输入自己的身份 $I D _ { i }$ ，密码 $P W _ { i }$ 。智能卡进行预先计算

$$
\begin{array} { l } { Q ^ { * } = H ( P W _ { i } \parallel n _ { i } ) \oplus H ( I D _ { i } \parallel x \parallel T ) } \\ { e = a _ { 1 } \times P , c = a _ { 1 } \times P _ { s } } \end{array}
$$

存储并保留信息{Q",e,c,a}

用户计算 $H ( I D _ { i } \mid \mid x \mid \mid T ) = H ( P W _ { i } \mid \mid b ) + Q$ ，选择随机数 $a _ { 2 }$ ，计算 $M _ { 1 } = ( I D _ { i } \parallel H ( I D _ { i } \parallel x \parallel T ) \oplus a _ { 2 } ) ) \oplus H ( c )$ ,并将信息返回给服务器 $\mathrm { \Delta } \mathrm { s }$ 。

S 选择随机数 $a _ { s }$ ,进行以下计算:

$$
\begin{array} { r l } & { H ( e \times x ) \oplus ( I D _ { i } \parallel H ( I D _ { i } \parallel x \parallel T ) \oplus A _ { 2 } ) ) \oplus H ( c ) = H ( e \times x ) + M _ { 1 } } \\ & { M _ { 2 } = H ( H ( I D _ { i } \parallel x \parallel T ) \parallel a _ { 2 } \parallel e ) } \\ & { S K = H ( M _ { 2 } \parallel e \parallel a _ { s } \times a _ { 1 } \times P ) } \\ & { M _ { 3 } = H ( S K \parallel H ( I D _ { i } \parallel x ) \parallel M _ { 2 } \parallel a _ { 2 } \parallel e ) } \\ & { S  U _ { i } : \{ M _ { 2 } , M _ { 3 } \} } \end{array}
$$

收到S的回复后，用户计算：

$$
\begin{array} { l } { S K = H ( M _ { 2 } \parallel e \parallel a _ { s } \times a _ { 1 } \times P ) } \\ { M _ { 3 } ^ { * } = H ( S K \parallel H ( I D _ { i } \parallel x ) \parallel M _ { 2 } \parallel a _ { 2 } \parallel e ) } \end{array}
$$

并进一步判断,

若 ${ M _ { 3 } } ^ { * } = { M } _ { 3 }$ ，则 $U _ { i } \to S : \{ N U L L \}$   
若 ${ M _ { 3 } } ^ { * } \ne { M _ { 3 } }$ ，用户计算 $M _ { 4 } = M _ { 3 }$   
U,→S:{M4},即S收到 M4后,执行以下操作

若 $\begin{array} { r } { \boldsymbol { M _ { 4 } ^ { \ast } } = H ( S K \parallel H ( I D _ { i } \parallel x ) \parallel M _ { 2 } \parallel \boldsymbol { a } _ { 2 } \parallel \boldsymbol { e } ) = \boldsymbol { M _ { 4 } } } \end{array}$ ，那么S准许$U _ { i }$ 的请求。反之，则用户被拒绝。

# 1.5安全模型

本方案通过挑战者和敌手之间的对弈游戏来描述支持撤销的位置分层加密方案的安全模型。具体过程如下：

SetupO挑战者运行算法 SetupO,输入公共参数 $P P A$ ，并将输出的公开密钥PK和属性公开密钥 $P K _ { a t t }$ 以及公共参数发送给敌手。

Phase 1挑战者提交一个集合 $D = \{ I _ { k e y } \}$ 并设置整数 $\scriptstyle \mathbf { k } = 0$ 敌手可以向挑战者重复进行如下询问：

转换密钥询问：挑战者选择 $\mathbf { k } { = } \mathbf { k } { + } 1$ ，随后运行 $I _ { k e y }$ 外包密钥算法，挑战者返回相应的转换密钥TK。

属性密钥查询：敌手提交一个对应于 $I _ { k e y }$ 的访问策略进行查询，再将生成的相应属性密钥SK传送给攻击者。

Challenge敌手提交两个长度相等的信息 $\mathbf { M } _ { 0 } , \mathbf { M } _ { 1 }$ 和 $\boldsymbol { I } ^ { * }$ ，其中 $I _ { k e y }$ 对应的解密密钥不能满足 $\boldsymbol { I } ^ { * }$ 的访问策略。挑战者随机选择选择 $b \in \{ 0 , 1 \}$ ，并以 $\boldsymbol { I } ^ { * }$ 加密 $\boldsymbol { M } _ { b }$ ，将加密后的 $\boldsymbol { C } \boldsymbol { T } ^ { * }$ 发送给敌手。

Phase 2 类似 phasel，但敌手不能直接查询可以解密 $\boldsymbol { M } _ { b }$ 的密钥对 $\boldsymbol { C } \boldsymbol { T } ^ { * }$ 进行解密。

Guess敌手输出对 $b$ 的猜测值 $b ^ { \prime }$ ，若 $\boldsymbol { b ^ { \prime } } = \boldsymbol { b }$ ，则敌手获得成功。该实验过程中，敌手的优势为

$$
\mathrm { P r } [ b = b ^ { \prime } ] - 1 / 2 = 0 \textdegree
$$

定义1如果任何多项式时间敌手在实验过程中都无法以不可忽略的优势赢得选择明文攻击下的安全游戏，则该方案是安全的。

# 2 方案设计

本文在基于属性加密位置分层访问策略[的基础上，引入解密外包，结合了双因子身份验证的方法，提出了一种支持撤销的CP_ABE 加密方案。

# 2.1用户注册及系统初始化

a）服务器S选取一个椭圆曲线 $E _ { p }$ ， $\mathbf { G }$ 为阶为 $\mathfrak { n }$ 的基点，$P _ { s } = { x } \times { P }$ 为系统的公钥。用户输入自己的 $I D _ { i }$ 和 $P W _ { i }$ 。

S从 $U _ { i }$ 处收到用户的请求并随机选择参数 $m _ { i }$ ，计算Q=H(PWIIni)H(IDi Ix|IT)。将安全参数发送给用户，用户保存私钥 $n _ { i }$ ，注册完毕。

b）Setup $( 1 ^ { \lambda } )$ ：定义一个哈希函数 $H : \{ 0 , 1 \} ^ { * }  G$ 和有效的双线性映射 $e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ ， $G _ { \imath }$ 和 $G _ { 2 }$ 两个阶为素数 $\mathfrak { p }$ 的乘法循环群， $\mathbf { g }$ 是 $G _ { 1 }$ 的生成元。 $\mathrm { \bf A }$ 表示主属性集合 $A = \{ h _ { 1 } , h _ { 2 } , \cdots , h _ { { } _ { u } } \}$ ，其中 $h _ { 1 } , h _ { 2 } , \cdots , h _ { _ u } \in G _ { 1 }$ ， $A ^ { \prime }$ 为次要属性集合 $A ^ { \prime } { = } \{ n _ { 1 } , n _ { 2 } , \cdots , n _ { { n _ { u } } } \}$ ，$n _ { 1 } , n _ { 2 } , \cdots , n _ { u } \in Z _ { p }$ 为系统中每一个属性设置主属性编号 $V _ { a t t }$ ，次属性编号Var·

系统进行初始化，以安全参数 $\lambda$ 作为输入，AA 随机选择$\alpha , \beta , n _ { 0 } \in Z _ { p }$ （204号 计算系统公钥$P K = < g , e ( g , g ) ^ { \alpha } , g ^ { \beta } , g ^ { n _ { 0 } } , h _ { 1 } , h _ { 2 } , \cdots , h _ { u } ,$ 和公开属性密钥$g ^ { \alpha n _ { 1 } / n _ { 0 } } , g ^ { \alpha n _ { 2 } / n _ { 0 } } , \cdots , g ^ { g ^ { \alpha n _ { u } / n _ { 0 } } } , H >$ $P K _ { a t t } = g ^ { V _ { a t t } } \quad \mathrm { ~ , ~ } \quad P K _ { a t t ^ { \prime } } = g ^ { V _ { a t t ^ { \prime } } }$ 再设置主密钥$\begin{array} { r } { M S K { = } \{ \alpha , \beta , n _ { 0 } , \{ \bigvee _ { a t t } \} _ { a t t \in S } , \{ \bigvee _ { a t t ^ { \prime } } \} _ { a t t ^ { \prime } \in S ^ { \prime } } \} } \end{array}$ ,AA 秘密保留 MSK。最后将PK和 $\begin{array} { r l } { P K _ { a t t } \ 、 } & { { } P K _ { a t t ^ { \prime } } } \end{array}$ 发送给代理商。

# 2.2加密算法

$E n c r y p t ( P K , P K _ { a t t } , k _ { 1 } , ( M , \rho ) )$ ：数据拥有者依据用户位置信息的分层策略使用对称加密算法（以E表示）生成三组对称密钥 $\mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \mathbf { k } _ { 3 }$ ，直接将对称密钥 $\mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \mathbf { k } _ { 3 }$ 定义为密文。随机加密位置信息 $\mathrm { m } _ { 1 } , \mathrm { m } _ { 2 } , \mathrm { m } _ { 3 }$ 得到加密密文

$$
E _ { k _ { 1 } } ( m _ { 1 } ) , E _ { k _ { 2 } } ( m _ { 2 } ) , E _ { k _ { 3 } } ( m _ { 3 } )
$$

输出密文 $C M = < E _ { k _ { 1 } } ( m _ { 1 } ) , E _ { k _ { 2 } } ( m _ { 2 } ) , E _ { k _ { 3 } } ( m _ { 3 } ) > .$

数据拥有者再进一步对对称密钥 $\mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \mathbf { k } _ { 3 }$ 进行加密，根据文献[5]提到的方法构造一个基于属性的访问策略 $( M , \rho )$ ，其中的LSSS矩阵用以表示主策略 ${ \bf P } _ { 1 }$ ， $\mathbf { \delta M }$ 表示一个1行 $\mathbf { h }$ 列的矩阵，（20 $\rho$ 是映射函数。随机产生列矢量 $\vec { V } = ( s , \nu _ { 2 } , . . . , \nu _ { h } ) \in Z _ { p }$ ，计算$\lambda { = } \overset {  } { \nu } { \cdot } \mathbf { M _ { \mathrm { i } } }$ $\cdot i = 1 , 2 , . . . , l$ ，其中 s表示待共享的秘密。随机从 $Z _ { { _ p } }$ 中选择 $r _ { 1 } , r _ { 2 } , \cdots , r _ { i }$ ，然后计算

$$
\begin{array} { r l } & { \tilde { C } _ { 1 } = k _ { 1 } e ( g , g ) ^ { \alpha s } \qquad C ^ { ' } = g ^ { s } } \\ & { \bigl ( C _ { 1 } = g ^ { \beta \lambda _ { 1 } } g ^ { V _ { a t } } H ( \rho ( i ) ) ^ { - r _ { 1 } } , D _ { 1 } = g ^ { r _ { 1 } } , ( M , \rho ) \bigr ) , \ldots , } \\ & { \quad ( C _ { l } = g ^ { \beta \lambda _ { l } } H ( \rho ( l ) ) ^ { - r _ { l } } , D _ { l } = g ^ { r _ { 1 } } , ( M , \rho ) ) } \end{array}
$$

以上为第一阶段加密。

$E n c r y p t ( P K , P K _ { a t t ^ { \prime } } , k _ { 2 } , k _ { 3 } , ( M , \rho ) )$ :在加密 $^ { \mathbf { \mathbf { k } } 2 , \mathbf { \mathbf { k } } 3 }$ 的过程中,以系统公钥PK中 $g ^ { n _ { 0 } }$ 和雲 $g ^ { \alpha n _ { 1 } / n _ { 0 } } , g ^ { \alpha n _ { 2 } / n _ { 0 } } , \cdots , g ^ { g ^ { \alpha n _ { u } / n _ { 0 } } }$ 计算:

$$
\begin{array} { r l } & { \tilde { \mathbf { C } } _ { 2 } = \mathbf { k } _ { 2 } e ( g ^ { n _ { 0 } s } , g ^ { \alpha n _ { 3 } / n _ { 0 } } ) = k _ { 2 } e ( g , g ) ^ { \alpha s n _ { 3 } } } \\ & { \tilde { C } _ { 3 } = k _ { 3 } e ( g ^ { n _ { 0 } s } , g ^ { \alpha n _ { 3 } / n _ { 0 } } g ^ { \alpha n _ { 4 } / n _ { 0 } } ) = k _ { 3 } e ( g , g ) ^ { \alpha s ( n _ { 3 } + n _ { 4 } ) } } \end{array}
$$

输出对称密钥密文

$$
\mathrm { C T } = < { \tilde { C } _ { 1 } } , { \tilde { C } _ { 2 } } , { \tilde { C } _ { 3 } } , \ \mathrm { C } ^ { \cdot } , ( C _ { i } , D _ { i } ) _ { \{ i \in l \} } >
$$

第二阶段加密结束。

# 2.3身份认证及私钥生成

a）用户完成登录后，智能卡保留预先计算的信息$\{ \boldsymbol { Q } ^ { * } , \boldsymbol { e } , \boldsymbol { c } , \boldsymbol { a } _ { 1 } \}$ ，其中 $Q ^ { * } = H ( P W _ { i } \parallel n _ { i } ) \oplus H ( I D _ { i } \parallel x \parallel T )$ 。

用户选择随机数 $a _ { 2 }$ ，计算$M _ { 1 } = ( I D _ { i } \parallel H ( I D _ { i } \parallel x \parallel T ) \oplus a _ { 2 } ) ) \oplus H ( c )$ 后，将 $\mathbf { M } _ { 1 }$ 发送给S。

服务器进行如下计算：

$$
\begin{array} { l } { H ( I D _ { i } \parallel x \parallel T ) \oplus a _ { 2 } ) \oplus H ( c ) \parallel I D _ { i } = H ( e \times x ) + M _ { 1 } } \\ { M _ { 2 } = H ( H ( I D _ { i } \parallel x \parallel T ) \parallel a _ { 2 } \parallel e ) } \end{array}
$$

随后选择随机数 $a _ { s }$ ，将计算所得的$\begin{array} { l } { S K = H ( M _ { \mathrm { 2 } } \parallel e \parallel a _ { s } \times a _ { 1 } \times P ) , } \\ { M _ { \mathrm { 3 } } = H ( S K \parallel H ( I D _ { i } \parallel x ) \parallel M _ { \mathrm { 2 } } \parallel a _ { 2 } \parallel e ) } \end{array}$ 发送至用户处。

用户判断 ${ M _ { 3 } } ^ { * }$ 与 $M _ { 3 }$ 是否相等，若不相等，那么用户被拒绝;若相等，用户则继续计算 $\mathbf { M } _ { 4 }$ ，最后由服务器执行计算$\boldsymbol { M _ { 4 } } ^ { * } = H ( S K \parallel H ( I D _ { i } \parallel x ) \parallel M _ { 2 } \parallel a _ { 2 } \parallel e )$ ；若 $\boldsymbol { M _ { 4 } } ^ { * }$ 不等于 $M _ { 4 }$ ，则用户身份验证失败；若 ${ M _ { 4 } } ^ { * } = { M } _ { 4 }$ ，用户身份验证成功。可继续执行私钥算法。

b） $K e y G e n ( M S K , u )$ :用户输入私钥MSK，AA 运行密钥产生算法，随机选择唯一的 $t \in Z _ { p }$ ，结合主属性集合和次要属性集为合法授权用户 $u$ 得到转换密钥

$$
\mathrm { T K } = < K _ { s } = g ^ { \alpha } \cdot g ^ { \beta t } , K _ { s } ^ { \phantom { \alpha } } = g ^ { \alpha / t } \cdot g ^ { \beta t } , L = g ^ { t } ,
$$

$$
\{ \mathrm  K _ { \mathrm { \scriptsize ~ a t t } } = ( g ^ { \mathrm { \scriptsize ~ V _ { \mathrm { \scriptsize ~ a t t } } } } H ( x ) ) ^ { \mathrm { \scriptsize ~ t } } \} _ { \mathrm { \scriptsize ~ v a t t + S } } , \{ K _ { \mathrm { \scriptsize ~ \cdot } } = ( g ^ { V _ { \mathrm { \scriptsize ~ a t t } } } H ( x ) ) ^ { t } \} _ { \mathrm { \scriptsize ~ v a t t + S } } , >
$$

转换密钥 TK 发送至代理商，用户私钥 $S K = \{ t \}$ 通过安全信道发给用户。

# 2.4解密算法

Decrypt(CT',SK）接收到用户的请求后,代理商输入对应的转换密钥TK,密文CT，运行转换算法判断用户属性是否满足主访问策略，若满足，则可在多项式时间内计算得一组常数$\{ w _ { i } \in Z _ { p } \} _ { i \in I }$ ，令 $\mathrm { I } \in \{ 1 , 2 , . . . , \ 1 \} , \mathrm { I } = \{ \mathrm { i } : \rho ( \mathrm { i } ) \in \mathrm { S } \}$ ，且 $\textstyle \sum _ { i \in I } w _ { i } { \lambda } _ { i } = s$ 成立。计算部分解密密文

$$
\begin{array} { r l } & { \mathbf { C T } _ { 1 } ^ { \prime } = e ( C ^ { ' } , K _ { s } ) / \prod _ { i \in I } ( e ( C _ { i } , L ) \cdot e ( D _ { i } , k _ { \rho ( i ) } ) ) ^ { w _ { i } } } \\ & { \qquad = e ( g , g ) ^ { \alpha s } \cdot e ( g , g ) ^ { \beta s t } / ( \prod _ { i \in I } e ( g , g ) ^ { t \beta \lambda _ { i } w _ { i } } ) } \\ & { \qquad = e ( g , g ) ^ { \alpha s } } \end{array}
$$

继续判断用户属性是否匹配次要访问策略，利用上阶段计算结果得

$$
\begin{array} { r l } & { ~ \boldsymbol { e } ( \boldsymbol { C } ^ { ' } , \boldsymbol { K } _ { s } ) / \prod _ { i \in I } ( \boldsymbol { e } ( \boldsymbol { C } _ { i } , L ) \cdot \boldsymbol { e } ( D _ { i } , \boldsymbol { k } _ { \rho ( i ) } ) ) ^ { w _ { i } } } \\ & { = \boldsymbol { e } ( \boldsymbol { C } ^ { ' } , \boldsymbol { K } _ { s } ) / e ( \boldsymbol { g } , \boldsymbol { g } ) ^ { \beta s t } } \\ & { = \boldsymbol { e } ( \boldsymbol { g } , \boldsymbol { g } ) ^ { \alpha s / t } } \end{array}
$$

同解密第一阶段,计算其余的部分解密密文

$$
\begin{array} { l } { { C T _ { 2 } ^ { ^ { \prime } } = e ( g , g ) ^ { \alpha s n _ { 3 } } = ( e ( g , g ) ^ { \alpha s / t } ) ^ { n _ { 3 } t } , } } \\ { { C T _ { 3 } ^ { ^ { \prime } } = e ( g , g ) ^ { \alpha s ( n _ { 3 } + n _ { 4 } ) } = ( e ( g , g ) ^ { \alpha s / t } ) ^ { n _ { 3 } t + n _ { 4 } t } } } \end{array}
$$

将部分解密密文 $\mathrm { C T _ { 1 } ^ { ' } } , \mathrm { C T _ { 2 } ^ { ' } } , \mathrm { C T _ { 3 } ^ { ' } }$ 发送给用户。用户计算

$$
\begin{array} { r l } & { \mathbf { k } _ { 1 } = \tilde { C } _ { 1 } / e ( g , g ) ^ { \alpha s } , \mathbf { k } _ { 2 } = \tilde { C _ { 2 } } / e ( g , g ) ^ { \alpha s n _ { 3 } } , } \\ & { \mathbf { k } _ { 3 } = \tilde { C _ { 3 } } / e ( g , g ) ^ { \alpha s ( n _ { 3 } + n _ { 4 } ) } } \end{array}
$$

最终通过对称密钥 $\mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \mathbf { k } _ { 3 }$ 得到解密后的明文信息：

$$
m _ { 1 } = D _ { k _ { 1 } } ( E _ { k _ { 1 } } ( m _ { 1 } ) ) , m _ { 2 } = D _ { k _ { 2 } } ( E _ { k _ { 2 } } ( m _ { 2 } ) ) , m _ { 3 } = D _ { k _ { 3 } } ( E _ { k _ { 3 } } ( m _ { 3 } ) )
$$

# 2.5属性撤销

该阶段撤销方案分为用户撤销和属性撤销两部分。

AA撤销指定用户时，该用户离开系统后无法解密数据服务器里的任何信息，用户 $\mathrm { ~  ~ u ~ }$ 的访问权限被撤销。AA设置一个撤销列表，令 $R T = R T \cup \{ u \} = \perp$ 。位于列表上的用户将被代理商拒绝返回部分解密密文，即实现用户撤销。

撤销用户的主要属性atti时，输入主密钥MSK和属性密钥$P K _ { a t t _ { 1 } }$ ，为该属性随机选择产生新的属性编号 $\overline { { { V } } } _ { a t t }$ ，属性权威计算并输出更新后的公开属性密钥 $P K _ { a u _ { 1 } }$ 并向数据拥有者发布公告，公开属性公钥已更新为{g"}·

AA为拥有该属性的用户产生转换密钥的更新密钥$U U K = g ^ { ( \overline { { { V } } } _ { a t t _ { 1 } } - V _ { a t t _ { 1 } } ) }$ ，并通过安全信道将更新密钥发送给代理商，部分用户仍拥有已撤销属性，代理商为其更新后的转换密钥为

$$
\begin{array} { r } { T K ^ { ^ { * } } = < K _ { s } ^ { ^ { * } } = g ^ { \alpha } \cdot g ^ { \beta t } , K _ { ^ { * } } ^ { ^ { * } } = g ^ { \alpha / t } \cdot g ^ { \beta t } , L ^ { ^ { * } } = g ^ { t } , } \end{array}
$$

$$
\begin{array} { r } { \{ \mathrm { K } _ { \mathrm { a t t } } = ( \mathbf { g } ^ { \mathrm { v } _ { \mathrm { a t t } } } \mathbf { H } ( \mathbf { x } ) ) ^ { \mathrm { t } } \} _ { \forall \mathrm { a t t } \in \mathsf { S } } , \{ K _ { \mathrm { \Omega } _ { \boldsymbol { x } } } ^ { * } = ( g ^ { V _ { \mathrm { a r t } } } H ( x ) ) ^ { t } \} _ { \forall a t t } _ { \in \mathsf { S } } , } \\ { K _ { a t t _ { 1 } } = K _ { a t t } \cdot U U K > \quad \quad } \end{array}
$$

为了避免新用户满足访问策略时无法访问之前的密文，所有访问策略里包含已撤销属性atti的关联密文需要进行更新。AA 产生密文更新密钥 $C U K = D _ { i } ^ { - ( \overline { { V } } _ { a t t _ { 1 } } - V _ { a t t _ { 1 } } ) }$ 并发送给代理商，代理

商将所有包含属性atti的密文进行升级，更新后的密文为

$$
\begin{array} { r l } & { C _ { 1 } ^ { * } = k _ { 1 } e ( g , g ) ^ { \omega s } \qquad C ^ { * } = g ^ { s } } \\ & { \Big ( C _ { 1 } ^ { * } = g ^ { \mathcal { B } _ { 1 } } g ^ { \nu _ { m } } H ( \rho ( i ) ) ^ { - n _ { 1 } } \ , \ D _ { 1 } ^ { * } = g ^ { n _ { 1 } } , ( M , \rho ) \Big ) , \ \dots , } \\ & { \qquad ( C _ { 1 } ^ { * } = g ^ { \mathcal { B } _ { 1 } } H ( \rho ( l ) ) ^ { - n _ { 1 } } , \ D _ { 1 } ^ { * } = g ^ { n _ { 1 } } , ( M , \rho ) ) } \\ & { \qquad \tilde { C _ { 2 } ^ { * } } = \mathbf { k } _ { 2 } e ( g ^ { n _ { 1 } s _ { 0 } } , g ^ { \omega n _ { 1 } j _ { 0 } } ) = k _ { 2 } e ( g , g ) ^ { \omega s n _ { 1 } } } \\ & { \qquad \tilde { C _ { 3 } ^ { * } } = k _ { 3 } e ( g ^ { n _ { 1 } s _ { 0 } } , g ^ { \omega n _ { 1 } j _ { 0 } } g ^ { \alpha n _ { 1 } j _ { n } } ) = k _ { 3 } e ( g , g ) ^ { \omega ( \alpha _ { 1 } - n _ { 4 } ) } } \\ & { \qquad \quad : = < \tilde { C } _ { 1 } ^ { * } , \tilde { C } _ { 2 } ^ { * } , \tilde { C } _ { 3 } ^ { * } , \ \mathbf { C } ^ { * } , ( C _ { 1 } ^ { * } , D _ { 1 } ^ { * } ) _ { \{ i \in \mathcal { I } \} } > } \end{array}
$$

撤销次要属性att时，与上述撤销主属性过程类似，代理商通过属性权威产生的新的转换密钥UUK =g $U U K = g ^ { ( \overline { { { V } } } _ { a t t _ { 2 } } - V _ { a t t _ { 2 } } ) }$ 和密文密钥 $C U K = { D _ { i } } ^ { - ( \overline { { V } } _ { a t _ { 2 } } - V _ { a t t _ { 2 } } ) }$ 对 TK 和密文CT进行更新，得到

$$
T K ^ { ^ { * } } = < K _ { s } ^ { ^ { * } } = g ^ { \alpha } \cdot g ^ { \beta t } , K _ { ^ { * } } ^ { ^ { * } } = g ^ { \alpha / t } \cdot g ^ { \beta t } , L ^ { ^ { * } } = g ^ { t } ,
$$

$$
\begin{array} { r l } & { \{ \mathrm { K } _ { \mathrm { a t t } } = ( \mathbf { g } ^ { \mathrm { V } _ { \mathrm { a t t } } } \mathbf { H } ( \mathbf { x } ) ) ^ { \mathrm { t } } \} _ { \forall \mathrm { a t t } \in \mathrm { S } } \ , \{ K _ { \mathrm { \Omega } _ { \vec { x } } } ^ { \ast } = ( g ^ { V _ { \mathrm { a t t } } } H ( x ) ) ^ { t } \} _ { \forall a t t ^ { \prime } \in S } , } \\ & { \quad K _ { a t t _ { 2 } } = K _ { a t t } \cdot U U K > } \end{array}
$$

$$
\mathrm { C T } = < \tilde { C } ^ { * } _ { 1 } , \tilde { C ^ { * } } _ { 2 } , \tilde { C ^ { * } } _ { 3 } , \ \mathrm { C ^ { * } } , ( C _ { i } ^ { * } , D _ { i } ^ { * } ) _ { \{ i \in l \} } >
$$

# 3 安全性分析

# 3.1选择明文攻击

Setup挑战者初始化程序，输出公共参数 PPA，公开密钥PK 和属性公开密钥 $\mathrm { P K } _ { \mathrm { a t t } }$

Phase 1

a)转换密钥查询。敌手可以重复询问已经掌握的主要属性信息 $l _ { 1 } , l _ { 2 } , \cdots , l _ { k }$ ,挑战者通过运行外包的密钥算法 $I _ { \boldsymbol { k } \boldsymbol { e } \boldsymbol { y } }$ ,获得转换密钥TK 和私钥SK。根据DBDH 假设，敌手的优势为Pr[b=b]-1/2=0,此时敌手无法获得与明文对应的私钥 SK。

随后输出

$\mathrm { T K } = < K _ { s } = g ^ { \alpha } \cdot g ^ { \beta t } , L = g ^ { t } , \{ \mathrm { K _ { a t t } = ( g ^ { \mathrm { v _ { a t } } } H ( x ) ) ^ { t } } \} _ { \mathrm { v a t t e S } } >$ 再将转换密钥TK发送给敌手。

b)用户私钥查询。转换密钥TK对应私钥SK，由于TK与对应的主属性集合均不能与密文 $\mathbf { M } _ { \mathrm { b } }$ 的访问策略匹配，敌手试图组合不同的转换密钥TK的访问策略来攻击位置信息 $\mathbf { m } _ { \mathrm { l } }$ 的访问策略。但本文中所有属性的访问策略都有随机参数t，根据转换算法，计算

$$
e ( C , K _ { s } ) / \prod _ { i \in I } ( e ( C _ { i } , L ) \cdot e ( D _ { i } , k _ { \rho ( i ) } ) ) ^ { w _ { i } }
$$

输入用户1和2的参数 $\mathbf { t } _ { 1 } , \mathbf { t } _ { 2 }$ ，两者试图联合并扩张自己属性集进行攻击，则计算出结果

$$
e ( g , g ) ^ { { \alpha } s / t } / e ( g ^ { r _ { i } \cdot w _ { i } } , ( g ^ { V _ { a n } } \cdot H ( x ) ) ^ { ( \frac { t _ { 1 } - t _ { 2 } } { t _ { 1 } \cdot t _ { 2 } } \cdot \beta ) } )
$$

根据DBDH假设，此时敌手无法计算出

$$
e ( g ^ { r _ { i } \cdot w _ { i } } , ( g ^ { V _ { a n } } \cdot H ( x ) ) ^ { ( \frac { t _ { 1 } - t _ { 2 } } { t _ { 1 } \cdot t _ { 2 } } \cdot \beta ) } )
$$

敌手优势可以忽略，将SK发送给敌手。

Challenge敌手提交两个明文信息 $\mathbf { M } _ { 0 }$ 和 $\mathbf { M } _ { 1 }$ ，另外生成 $\boldsymbol { I } ^ { * }$ ，并且 $I _ { k e y }$ 的所有解密密钥生成私钥与 $\boldsymbol { I } ^ { * }$ 对应的访问策略不匹配，即是无法解密。挑战者随机选择 $b \in \{ 0 , 1 \}$ ，对明文 $\mathbf { M } _ { \mathrm { b } }$ 进行加密，并将密文 $\boldsymbol { c } \boldsymbol { T } ^ { * }$ 发送给敌手。

Phase 2重复phase1的查询步骤。

Guess将敌手对 $b$ 的猜测 $b ^ { \prime }$ 输出，对密文 $\boldsymbol { C } \boldsymbol { T } ^ { * }$ 进一步作出 判断，确认其是否为 $\mathbf { M } _ { 0 }$ 和 $\mathbf { M } _ { 1 }$ 加密后的密文，即 $b$ 是否与 $b ^ { \prime }$ 的 值相等，若 $\boldsymbol { b } = \boldsymbol { b } ^ { \prime }$ ,则敌手成功。

上述过程中，敌手的优势为 $\mathrm { P r } [ b = b ^ { \prime } ] - 1 / 2$ ：

# 3.2数据保密性

数据的保密性定义为只有合法用户和数据拥有者可以解密获得明文消息。非法用户，已撤销的用户都无法访问数据。在本文方案中，加密的第二阶段的安全性依赖于Elgamal 算法中离散对数分解的NPC问题。假设未授权用户已满足第一阶段访问策略 $( M , \rho )$ ，解密获得对称密钥 $\mathbf { k } _ { 1 } = e ( g , g ) ^ { \alpha s }$ ，该用户想继续攻击并得到密钥 $k _ { 2 } = \tilde { C } _ { 2 } / e ( g , g ) ^ { \alpha s n _ { 3 } } , k _ { 3 } = \tilde { C } _ { 3 } / e ( g , g ) ^ { \alpha s ( { \bf n } _ { 3 } + n _ { 4 } ) }$ ，必须能够得到随机数 $^ { { \mathsf { n } } 3 , { \mathsf { n } } 4 }$ 。然而从系统公钥PK的gn/n,g/,,g&中计算出n3和n4的值是难以实现的，此种计算问题属于离散对数分解的NPC难题，从而可以验证数据的保密性。

# 3.3 抵抗合谋攻击

在解密的第一阶段，用户必须首先得到 $e ( g , g ) ^ { \alpha s }$ ，才能解出对称加密密钥 $\mathbf { k } _ { 1 }$ 。通常的情况下，若两个用户都不能满足主要策略，则用户不能从 $\prod _ { i \in I } ( e ( C _ { i } , L ) \cdot e ( D _ { i } , k _ { \rho ( i ) } ) ) ^ { w _ { i } }$ 中恢复出秘密值S。但也存在这两个用户会满足主要属性策略的某一部分的情况，此时可以通过交换主属性参数达到扩展权限的目的。由此将随机数t引入转换密钥TK，本文中所有的 $\mathrm { K } _ { \mathrm { x } }$ 都含有一个参数t,合谋用户无法通过他们掌握的私钥组合进行解密。解密第二阶段，用户的目的是想要获取密钥 $\mathbf { k } _ { 2 }$ ， $\mathbf { k } _ { 3 }$ ，此时用户若已经从第一阶段解密过程中获得 $e ( g , g ) ^ { \alpha s }$ ，也需要n3, $\mathtt { n 3 + n 4 }$ 配合解密。本文的系统并没有直接释放用户希望的参数 $\mathrm { { n } _ { l } , n _ { 2 } , . . . , n _ { u } , }$ （204号而是选择释放次要属性参数，则用户不能解密。继续讨论，当两个用户都无法满足次要属性策略时不能访问存在于私钥中的n3， $\mathtt { n } _ { 3 } + \mathtt { n } _ { 4 }$ ，无法解密。与部分次要属性策略匹配的用户，可以交换自身的参数 $\mathtt { n } _ { 1 } , \mathtt { n } _ { 2 } , . . . . , \mathtt { n } _ { \mathrm { u } }$ 进行配合攻击，和第一阶段采用同样的思想，同样选择随机数t，此时合谋用户也不能用组合私钥参数的方式来实现解密。经验证，本文的方案是可以抵抗合谋攻击的。

# 3.4前向安全和后向安全

前向安全：被撤销属性的用户无法解密更新后的密文访问关联该属性的密文，即使他持有该属性。

后向安全：新加入的用户在AA更新重加密密文仍可以解密之前的密文。

以撤销次要属性 $a t t ^ { \prime }$ 为例，当发生属性撤销时,AA便会为被撤销的属性 $a t t ^ { \prime }$ 产生一个新的属性编号 $V _ { a t t ^ { \prime } }$ ，并为未撤销该属性的用户升级密钥TK，而撤销该属性的用户不能进行密钥升级，同时为相关密文进行升级。若被撤销属性 $a t t ^ { \prime }$ 的用户试图使用自己之前的密钥去解密更新后的密文，根据数据解密的相关算法，最终解密结果为 $\tilde { C } _ { 2 } = k _ { _ 2 } \cdot e ( g , g ) ^ { \alpha s n _ { 3 } ( { \nu } _ { _ { a t t } } \cdot { - } { \nu } _ { _ { a t t } } ) }$ ，而敌手不能获得 $\alpha , s , n _ { 3 , } \nu _ { _ { a t t } } , - \nu _ { _ { a t t } }$ ，所以无法解密获得 $\mathbf { k } _ { 2 }$ 。对于新加入的用户，他们的私钥是由更新后的属性密钥CUK生成。AA将更新的属性密钥发送给代理商，代理商负责升级相关密文，所以新用户可以解密之前的密文，从而确保了方案的后向安全。

# 4 方案分析

本章主要给出本文方案与相关方案[3，5，6，8，9]在功能性、计算效率几方面进行的对比。

# 4.1功能比较

从表1可以看出，文献[6]使用了分层属性加密并对算法进行了优化，但是该方案安全性和减少计算成本上有待提升。文献[8]实现了属性级的立即撤销能力，但是没有实现细粒度的访问控制。文献[9]提出的无密钥托管可撤销属性方案实现了细粒度访问控制，但需要中央控制和授权机构两方计算，不能很好地与分层属性加密相结合。本文在此基础上支持用户撤销与属性撤销，将解密过程中的大量计算外包给了代理商，减少了用户的计算负担。

表1方案功能对比  
Table 1 Comparison of scheme functions   

<html><body><table><tr><td>方案</td><td>访问结构类型撤销机制</td><td></td><td>撤销粒度</td><td>支持位置分层解密外包</td><td></td></tr><tr><td>文献[3]</td><td>access tree</td><td>无</td><td>无</td><td>香</td><td>香</td></tr><tr><td>文献[5]</td><td>LSSS</td><td>无</td><td>无</td><td>香</td><td>香</td></tr><tr><td>文献[6]</td><td>LSSS</td><td>无</td><td>无</td><td>是</td><td>香</td></tr><tr><td>文献[8]</td><td>access tree</td><td>可撤销</td><td>属性撤销</td><td>香</td><td>香</td></tr><tr><td>文献[9]</td><td>LSSS</td><td>可撤销</td><td>属性/用户撤销</td><td>香</td><td>是</td></tr><tr><td>本文方案</td><td>LSSS</td><td>可撤销</td><td>属性/用户撤销</td><td>是</td><td>是</td></tr></table></body></html>

# 4.2效率分析

本文主要是针对文献[6]的安全性问题和计算量问题，提出结合支持撤销功能和解密外包的方案，与此同时要保证原方案位置分层多次加密的优势得以延续，并对加密解密效率不会造成影响。因此本文通过对两次属性加密和三次属性加密的效率进行分析，从表2和3可以看出，增加了撤销功能后不会影响原方案的加密效率，且引入的解密外包使得用户解密负担减少。对比过程中使用符号描述定义如下：p表示双线性对运算，e表示模指数运算，主要属性和次要属性关联的数目分别用a，b表示。

Table 2Efficiency analysis of two times attribute encrypton   

<html><body><table><tr><td>方案</td><td>结构类型</td><td>相关属性个数</td><td>加密计算量</td><td>解密计算量</td></tr><tr><td>文献[3]</td><td>access tree</td><td>a+b</td><td>(4a+4b+2)e+2p</td><td>(2a+2b)e+(2a+2b+4)p</td></tr><tr><td>文献[5]</td><td>LSSS</td><td>a+b</td><td>(6a+6b+2)e+2p</td><td>(2a+2b)e+(4a+4b+2)p</td></tr><tr><td>文献[6]</td><td>LSSS</td><td>a+b</td><td>(3a+1)e+2p</td><td>(a+1)e+(2a+2)p</td></tr><tr><td>本文方案</td><td>LSSS</td><td>a+b</td><td>(3a+1)e+2p</td><td>2e+p</td></tr></table></body></html>

表3三次加密效率分析

表2两次加密效率分析  
Table 3Efficiency analysis of three times attribute encrypton   

<html><body><table><tr><td>方案</td><td>结构类型</td><td>相关属性个数</td><td>加密计算量</td><td>解密计算量</td></tr><tr><td>文献[3]</td><td>Access tree</td><td>a+b</td><td></td><td>(6a+6b+3)e+3p (3a+3b)e+(3a+3b+6)p</td></tr><tr><td>文献[5]</td><td>LSSS</td><td>a+b</td><td></td><td>(9a+9b+3)e+3p (3a+3b)e+(6a+6b+3)p</td></tr><tr><td>文献[6]</td><td>LSSS</td><td>a+b</td><td>(3a+1)e+3p</td><td>(a+2)e+(2a+2)p</td></tr><tr><td>本文方案</td><td>LSSS</td><td>a+b</td><td>(3a+1)e+3p</td><td>3e+p</td></tr></table></body></html>

# 5 结束语

本文提出的一种支持撤销的位置分层属性加密的方案，在不影响加密效率和分层功能的前提下，结合了双因子身份认证机制，增强了系统安全性，提升解密效率，减少用户计算量，方案也具有保密性和抵抗用户合谋攻击的优点。本文通过对方案进行功能对比和效率分析，结果表明所提方案具有较高的解密效率和一定的安全性。

# 参考文献：

[1]Kido H, Yanagisawa Y, Satoh T.An anonymous communication technique using dummies for location-based services [C]// Proc of International Conference,Pervasive Services.2oo5: 88-97.   
[2]Yiu Manlung,Christian S,Jensen,et al. SpaceTwist: managing the tradeoffs among location privacy,query performance and query accuracy in mobile services [C]//Proc of the 24th IEEE International Conference on Data Engineering.Washington DC:IEEE Computer Society,2008:366-375.   
[3]Bethencourt J,Sahai A，Waters B.Ciphertext-policy attribute-based encryption [C]// Proc of IEEE Symposium on Security and Privacy. Washington DC:IEEE Computer Society.2007: 321-334.   
[4]Beimel A. Secure schemes for secret sharing and key distribution [D]. Israel: Israel Institute of Technology.1996.   
[5]Waters B.Ciphertext-policy attribute-based encryption: an expressive, efficient,and provably secure realization [J].Public Key Cryptography, 2011: 53-70.   
[6]Lin Xi,Han Yiliang,et al.Location hierarchical access control scheme based on attribute encryption [C]//Proc of the 36th Chinese Control Conference. 2017.   
[7]Pirretti M,Traynor P, Mcdaniel P,et al. Secure atribute-based systems [C]// Proc of the 13th ACM Conference on Computer and Communications Security. 2006: 99-112.   
[8]Hur J,Noh D K.Attribute-based access control with effcient revocation in data outsourcing systems [J].IEEE Trans on Parallel and Distributed Systems,2011,22(7): 1214-1221.   
[9] 赵志远，朱智强，王建平，等.云存储环境下无密钥托管可撤销属性基 加密方案研究[J].电子与信息学报,2018,40(1):1-10.(Zhao Zhiyuan, Zhu Zhiqiang. Wang Jianping,etal. Revocable attibute-based Encryption with escrow-free in cloud storage [J]. Journal of Electronics & Information Technology,2018,40 (1): 1-10.)   
[10] Yang Wenher, Shieh Shiuhping.A Password authentication schemes with smart cards [J].Computers & Security,1999,18 (8):727-733.   
[11] Das M, Saxena A, Gulati V.A dynamic ID-based remote user authentication scheme [J].IEEE Trans on Consumer Electronics,2004,50 (2): 629-631.   
[12] Tsai Jialun,Lo Naiwei,Wu Tzongchen. Novel anonymousauthentication scheme using smart cards [J].IEEE Trans on Ind.Inform,2013,9(4): 2004- 2013.   
[13] Li Chunta. A new password authentication and user anonymity scheme based on elliptic curve cryptography and smart card [J]. IET Inform.Se cur, 2013, 7 (1): 3-10.   
[14] Wang Ding,He Debiao,Wang Ping,et al. Anonymous two-factor   
[15] authentication in distributed systems: certain goals are beyond attainment [J].IEEE Trans on Dependable& Secure Computing,2015,12(4): 428-442.   
[16]李勇，曾振宇，张晓菲．支持属性撤销的外包解密方案[J].清华大学 学报：自然科学版,2013,53(12):1664-1669.(Li Yong,Zeng, Zhenyu, Zhang Xiaofei. Outsourced decryption scheme supporting attribute revocation [J].JTsinghua University:Sei&Technol,2013,53(12):1664- 1669.)   
[17]池水明，陈勤，党正芹．一种基于策略控制的可撤销属性基代理加密方 案[J].计算机工程与科学,2013,35(9): 94-98.(Chi Shuimng,Chen Qin, Dang Zhengqin.An atribute-based encryption scheme with attribute revocation and key delegation based on policy control [J]. Computing Engineering & Science,2013,35 (9): 94-98.）   
[18]闫玺玺，孟慧．支持直接撤销的密文策略属性基加密方案[J].通信学 报,2016,37(5): 44-50.(Yan Xixi,Meng Hui.Ciphertext policyatribute based encryption scheme supporting direct revocation [J]. Journal on Communications,2016,37 (5): 44-50.)   
[19] Huang Qinlong,Ma Zhaofeng,Yang Y,etal.Attribute-based secure data sharing with eficient revocation in cloud computing [J]. Chinese JournalElectronics,2015,24(4): 862-868.