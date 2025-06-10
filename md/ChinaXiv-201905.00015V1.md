# 抗密钥泄露的在线/离线身份基加密机制

张秀洁

(潍坊学院 计算机工程学院，山东 潍坊 261061)

摘要：在线离线身份基加密（IBOOE）方案是一种具有高效的密钥生成和加密算法的密码方案。然而，目前已有的IBOOE 方案无法抵抗边信道攻击，它将引起密码系统秘密信息泄露问题。新方案通过将随机提取器嵌入在线加密算法来隐藏私钥泄露和密文之间的关系，提出首个有界泄露模型下安全的 IBOOE 方案；新方案基于合数阶双线性群上的三个静态假设，利用双系统加密技术在标准模型下抵抗选择明文攻击达到完全安全性和泄露弹性。此外，与传统的IBOOE方案相比较，新方案特别适用于敏感数据存储且资源受限的场景。

关键词：基于身份加密；在线/离线；泄露弹性；双系统加密；可证明安全 中图分类号：TP309.7 doi: 10.19734/j.issn.1001-3695.2018.11.0892

Identity based online/offline encryption resistant to key leakage

Zhang Xiujie† (School of Computer Engineering,Weifang University,Weifang Shandong261061, China)

Abstract: Identity based online/oflineencryption(IBOOE)system is an cryptographyscheme of efcient keygeneration and encryption algorithm.Buttheexist IBOOE systemscan’tresilient to sidechannel attack,it willead to secret information leakage problem of cryptosystem.This paper embed random extractor toonline encryption procedure to mask therelationship betwen the leakage ofsecret keyandthe ciphertext and firstlyputforward abound leakage IBOOE scheme. The proposed scheme employs dual system encryption to prove fully security and chosen plaintext security against key leakage attack in the standard model from three static assumptions on composite order bilinear groups.In addition, compared with the traditional IBOOE scheme,the proposed scheme is extremely suitable for the scenarios where store sensitive data and resource-constrained.

Key words: identitybased encryption; online/ofline; leakage resilient; dual system encryption; provable security

# 0 引言

为了解决传统的基于证书的公钥体制中复杂的证书管理问题，Shamir[1]于1984 年美密会上首次提出基于身份加密(IBE)。在一个IBE系统中，用户公钥是基于用户身份的随机串，例如邮箱地址或电话号码。然而IBE方案[2\~4]必须执行幂乘或双线性对等复杂运算，不适用于无线传感器网络等计算能力非常有限的环境。2008年Guo等人[5]首次提出在线离线身份基加密（IBOOE）方案，将加密过程分解成离线和在线两个阶段，离线阶段在不知道明文和用户身份的前提下，对复杂计算进行预处理输出离线密文；在线阶段获知消息和身份后，仅需少量简单计算即可生成密文，大大提高了在线加密算法的效率，但是其密文长度非常大，不适用于轻量级设备。2009年ACNS会议上，Liu等人[在随机预言机模型（ROM）下，构造了高效的IBOOE方案，特别适合计算能力有限的传感器和智能卡等终端设备。2011年ASIACCS会议上Chow等人[7在ROM下构造了首个在线/离线身份基密钥封装机制（IBOOKEM)，并基于此给出IBOOE方案的通用构造。2014年王等人[20采用双系统加密系统构造了完全安全的IBOOE方案。2015年ACISP会议上，Lai等人[8采用新的方法将基于接收者身份的计算量分成离线和在线两个阶段由IBOOKEM给出IBOOE的高效半通用构造。2017年Lai等人[在ROM下提出一个高效的IBOOE方案，与以前的方案相比较，它具有较短的密文。

然而，现有的IBOOE方案都没有考虑恶意程序的边信道攻击。作为传统的密码系统，假定用户私钥对于可能的攻击来说是完全保密的，但在实际应用中通过边信道攻击（例如时间攻击、能量消耗、冷启动攻击等）可以从保密的私钥或者加密系统内部获取私钥的部分信息。为了模拟上述密钥泄露攻击，泄露弹性密码体制允许攻击者在获得密码方案的部分敏感信息的前提下实现其可证明安全性。2009年Akavia等人[10]首次设计出公钥密码体制下密钥泄露，在用户私钥部分泄露的情况下，方案仍然能够保证安全性。Naor 等人[II]提出有界泄露模型下的公钥加密方案。2010年，Chow等人[12]基于Lekow-Waters 的双系统加密机制[4]，在三个静态假设下给出高效的抗泄露IBE方案。文献[13,14]中提出利用双系统加密技术容忍密钥有界泄露，在双线性对群中构造了泄露弹性加密方案。Hazay 等人[15]提出基于任一标准的公钥加密方案构造泄露弹性公钥加密方案的通用转换，基于单向函数构造了泄露弹性伪随机数生成器和泄露弹性消息认证码。为了模拟实际的泄露，假定存在泄露预言机允许敌手访问，从而获取关于私钥的多项式时间可计算函数的输出。近几年，为了抵抗不同的密钥泄露攻击，文献[16\~19]提出各种相关的泄露弹性密码原语。

通过分析，已有的IBOOE方案无法抵抗密钥泄露攻击，借鉴Chow等人[12]提出有界泄露模型刻画密钥泄露攻击，针对传统的在线/离线身份基加密方案，本文设计了首个泄露弹性在线/离线加密（IrIBOOE）方案。在该机制中，使用在线和离线加密技术提高了系统的计算效率。离线加密预处理复杂计算过程，并保存计算结果为离线密文；轻量级设备执行在线加密算法，利用离线密文仅需少量简单计算即可生成，这里使用随机提取器来隐藏私钥泄露和密文之间的关系，使得敌手即使得到一定量的私钥量也无法攻破IBOOE方案，从而达到密钥泄露弹性。此外，基于Lekow-Waters[4]的双系统加密机制，通过一系列游戏刻画出详细的敌手模型，并在合数阶双线性群上基于三个静态假设证明了游戏之间的不可区分性，从而在标准模型下证明新方案抵抗选择明文攻击达到完全安全性和泄露弹性。

# 1 预备知识

# 1.1统计距离、熵和提取器

定义1两个随机变量 $X , Y$ 的统计距离定义为$S D ( X , Y ) = 1 / 2 \sum _ { x } \left| P r [ X = x ] - P r [ Y = x ] \right|$ ，其中 $X \stackrel { s t a t } { \approx } Y$ 表示$S D ( X , Y ) \leq \varepsilon$ 表两个随机变量 $X , ~ Y$ 在统计上是不可区分的。$X \stackrel { s t a t } { \approx } Y$ 表示统计距离对于安全参数是可忽略的。后者本文称$X , Y$ 是统计上不可区分的。

定义2随机变量 $X$ 的最小熵定义为$H _ { \infty } ( X ) = - \mathrm { l o g } ( \mathrm { m a x } _ { x } P r [ X = x ] )$ ，而 $X$ 在随机变量 $Y$ 下的平均条件最小熵 $H _ { \infty } ( X \vert Y ) { \mathrm { = } } { \mathrm { = } } { \mathrm { l o g } } ( E _ { y  Y } [ \operatorname* { m a x } _ { x } \operatorname* { P r } [ X = x \vert Y { \mathrm { = } } y ] ] )$ ，其中 $E _ { y  Y }$ 表示遍历所有 $Y$ 值的期望值。即对所有函数 $f ,$ 满足 $\operatorname* { P r } [ f ( Y ) = X ] \leq 2 ^ { - { \hat { H } } _ { x } ( X | Y ) }$ ，并且存在某个 $f$ 对等号成立。

直观上，随机变量的最小熵是用来衡量任一敌手描述变量的值的困难程度。最小熵越大，则敌手成功的概率越小，因为最优策略是用最大的概率 $\mathrm { m a x P r } [ X = x ]$ 来描述变量的值。平均最小熵则是在已知另外一个随机变量的情况下描述随机变量 $X$ 的困难程度。下面的函数称作提取器，它典型应用于构造泄露弹性系统。

定义3提取器。一个多项式时间的函数$e x t { : } G \times \{ 0 , 1 \} ^ { u } \mathrm { \longrightarrow } \{ 0 , 1 \} ^ { m }$ 是一个平均的 $\left( h , \varepsilon \right)$ 强的提取器，如果对随机变量 $( X , Y )$ 的所有对，满足 $H _ { \infty } ( X | Y )$ ≥h, $X , Y \in G$ ，有$S D ( ( e x t ( X , U _ { \mu } ) , U _ { \mu } , Y ) , ( U _ { m } , U _ { \mu } , Y ) ) \le$ ，其中 $G$ 是一个非空集合， $U _ { \mu }$ 、 $U _ { m }$ 分别是 $\{ 0 , 1 \} ^ { u }$ 、 $\{ 0 , 1 \} ^ { m }$ 上的两个均匀分布的随机变量。

# 1.2合数阶双线性群

该群是用一个群生成器 $G$ ，输入一个安全参数 $k$ 来定义的，它的输出是双线性群的一个具体的描述。本文输出群系统 $( N = p _ { 1 } p _ { 2 } p _ { 3 } , G , G _ { T , e } )$ 。其中 $N { = } p _ { 1 } p _ { 2 } p _ { 3 }$ 为阶，它是3个不同的素数的乘积，群 $G$ 和 $G _ { T }$ 是 $N$ 阶循环群。一个双线性映射$e { \mathrel { : } } G { \times } G {  } G _ { T }$ 满足下述性质：

a)双线性。对于任意的 $g , h \in G$ ， $a , b \in Z _ { \mathrm { N } }$ ，均有$e ( g ^ { a } , h ^ { b } ) { = } e ( g , h ) ^ { a b }$ 成立。

b)非退化性。存在 $g \in G$ 使得 $e ( g , g )$ 在群 $G _ { T }$ 中的阶为 $N _ { \circ }$ c)可计算性。对于任意 $g , h \in G$ ， $e ( g , h )$ 可快速求取。

d)正交性。 $G _ { 1 }$ 、 $G _ { 2 }$ 和 $G _ { 3 }$ 表示群 $G$ 中阶分别为 $p 1 \setminus p 2$ 和$p _ { 3 }$ 的子群，则当 $h _ { i } \in G _ { i }$ ， $h _ { j } \in G _ { j }$ 且 $i { \neq } j$ ， $e ( h _ { i } , ~ h _ { j } )$ 是 $G _ { T }$ 的单位元。具体来说，假设 $h _ { 1 } \in G _ { 1 }$ ， $h _ { 2 } \in G _ { 2 }$ ， $g$ 表示 $G$ 中的一个生成元，则有结论 $g ^ { { p _ { 1 } } { p _ { 2 } } }$ 能生成群 $G _ { 3 }$ 、 $g ^ { { p _ { 1 } } { p _ { 3 } } }$ 能生成群 $G _ { 2 }$ 、 $g ^ { p _ { 2 } p _ { 3 } }$ 能生成群 $G _ { 1 }$ 。因此对于某些值 $\alpha _ { 1 } , \alpha _ { 2 } , h _ { 1 } = ( g ^ { p _ { 1 } p _ { 3 } } ) ^ { \alpha _ { 1 } }$ 和 $h _ { 2 } = ( g ^ { p _ { 1 } p _ { 3 } } ) ^ { \alpha _ { 2 } }$ ，应满足 $e ( h _ { 1 } , h _ { 2 } ) = e ( g ^ { p _ { 2 } p _ { 3 } \alpha _ { 1 } } , g ^ { p _ { 1 } p _ { 3 } \alpha _ { 2 } } ) =$ $e ( g ^ { \alpha _ { 1 } } , g ^ { p _ { 3 } \alpha _ { 2 } } ) ^ { p _ { 1 } p _ { 2 } p _ { 3 } } = 1$ ，则本文称群$G _ { 1 } , G _ { 2 }$ 和 $G _ { 3 }$ 的这一特性为正交性。

# 1.3 困难性假设

在合数阶群上有下面三个困难问题假设。

假设1子群判定假设。挑战者运行 $G ( 1 ^ { n } )$ ，生成$D ^ { 1 } \mathrm { = } ( N , G , G _ { T } , e , g _ { 1 } , g _ { 3 } )$ 并将其发送给敌手 $A$ 。挑战者随机选择 $\mathbf { \Phi } _ { \nu }$ $\ r \in \{ 0 , 1 \}$ 和 $( a , b ) \gets Z _ { p _ { 1 } } \times Z _ { p _ { 2 } }$ ，计算 $T _ { 0 } ^ { 1 } = g _ { 1 } ^ { a }$ 和 $T _ { 1 } ^ { 1 } = g _ { 1 } ^ { a } g _ { 2 } ^ { b }$ ，将 $T _ { \nu } ^ { 1 }$ 发送给 $A$ 。最后，敌手 $A$ 输出一个值 $\mathbf { \Lambda } _ { \nu } ^ { \mathbf { \Lambda } }$ ，如果 $\scriptstyle \nu ^ { \prime } = \nu$ ，则敌手 $A$ 成功。

本文定义敌手 $A$ 攻击假设1的优势为

$$
A d \nu _ { G , A } ^ { 1 } ( k ) = \left| \operatorname* { P r } [ A ( D , T _ { 0 } ^ { 1 } ) = 1 ] - \operatorname* { P r } [ A ( D , T _ { 1 } ^ { 1 } ) = 1 ] \right|
$$

定义4称 $G$ 满足假设1，如果对任意多项式时间敌手 $A$ ，有 $A d \nu _ { G , A } ^ { 1 } ( k )$ 是关于安全参数 $k$ 的可忽略函数。

假设2挑战者运行 $G ( 1 ^ { n } )$ ，随机选择 $( x _ { 1 } , x _ { 2 } , x _ { 3 } ) \gets$ $Z _ { p _ { 1 } } \times Z _ { p _ { 2 } } \times Z _ { p _ { 3 } }$ ，将 $D ^ { 2 } = ( N _ { 1 } , G , G _ { T } , e , g _ { 1 } , g _ { 3 } , g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } )$ 发送给敌手 $A$ 。挑战者随机选择一个值 $\nu \in \{ 0 , 1 \}$ ，随机选择$( a , b , c ) \gets Z _ { p _ { 1 } } \times Z _ { p _ { 2 } } \times Z _ { p _ { 3 } }$ ，计算 $T _ { 0 } ^ { 2 } = g _ { 1 } ^ { a } g _ { 3 } ^ { c } , T _ { 1 } ^ { 2 } = g _ { 1 } ^ { a } g _ { 2 } ^ { b } g _ { 3 } ^ { c }$ ，将 $T _ { \nu } ^ { 2 }$ 发送给 $\boldsymbol { \mathscr { A } }$ 。最后，敌手 $A$ 输出一个值 $\mathbf { \Lambda } _ { \nu } ^ { \mathbf { \Lambda } }$ ，如果 $\scriptstyle \nu ^ { \prime } = \nu$ ，则敌手 $A$ 成功。

本文定义敌手 $A$ 攻击假设2的优势为

$$
A d \nu _ { G , A } ^ { 2 } ( k ) = \left| \operatorname* { P r } [ A ( D , T _ { 0 } ^ { 2 } ) = 1 ] - \operatorname* { P r } [ A ( D , T _ { 1 } ^ { 2 } ) = 1 ] \right|
$$

定义5称 $G$ 满足假设2，如果对任意多项式时间敌手 $A$ ，有 $A d \nu _ { G , A } ^ { 2 } ( k )$ 是关于安全参数 $k$ 的可忽略函数。

假设3挑战者运行 $G ( 1 ^ { n } )$ 并随机选择 $( x _ { 1 } , x _ { 2 } , \beta , z ) \gets$ $Z _ { p _ { 2 } } \times Z _ { p _ { 2 } } \times Z _ { p _ { 1 } } \times Z _ { p _ { 1 } }$ 。将 $D ^ { 3 } = ( N _ { 1 } , G , G _ { T } , e , g _ { 1 } , g _ { 3 } , g _ { 1 } ^ { \beta } g _ { 2 }$ ， $g _ { 1 } ^ { z } g _ { 2 } ^ { x _ { 2 } } , g _ { 2 } ^ { y _ { 2 } } )$ 发送给敌手 $A$ 。挑战者随机选择 $\nu \in \{ 0 , 1 \}$ ，随机选择 $\eta  Z _ { \scriptscriptstyle N }$ ，计算$T _ { 0 } ^ { 3 } = e ( g _ { 1 } , g _ { 1 } ) ^ { \beta z }$ 和 $T _ { 1 } ^ { 3 } = e ( g _ { 1 } , g _ { 1 } ) ^ { \beta \eta }$ ，将 $T _ { \nu } ^ { 3 }$ 发送给 $A$ 。最后，敌手 $A$ 输出一个值 $\mathbf { \Lambda } _ { \nu } ^ { \mathbf { \Lambda } }$ ，如果 $\scriptstyle \nu ^ { \prime } = \nu$ ，则敌手 $A$ 成功。

本文定义敌手 $A$ 攻击假设3的优势为

$$
A d \nu _ { G , A } ^ { 3 } ( k ) = \left| \operatorname* { P r } [ A ( D , T _ { 0 } ^ { 3 } ) = 1 ] - \operatorname* { P r } [ A ( D , T _ { 1 } ^ { 3 } ) = 1 ] \right|
$$

定义6称 $G$ 满足假设3，如果对任意多项式时间敌手 $A$ 有 $A d \nu _ { G , A } ^ { 3 } ( k )$ 是关于安全参数 $k$ 的可忽略函数。

# 2 泄露弹性身份基在线/离线加密方案的模型定义

# 2.1泄露弹性身份基在线/离线加密方案的形式化定义

泄露弹性身份基在线/离线加密（IrIBOOE）方案包括初始化算法 Setup、密钥提取算法Ext、离线加密算法Encff、在线加密算法Enco和解密算法Dec五个算法。

a)Setup(1)算法。输入系统安全参数 $k$ ，输出系统公开参数 $P P$ 和主密钥MSK。系统参数包括消息集合 $M$ 和密文集合 $C$ 。其中，主密钥MSK由密钥生成中心秘密存储。

$\mathbf { b } ) \mathbf { E x t } ( P P , I , M S K )$ 算法。输入系统公开参数 $P P$ 、用户的身份信息 $I$ 和系统主密钥MSK，生成该用户的私钥 $S K _ { I }$ ，并通过安全信道将其发送给该用户。

$\mathbf { c } ) \mathbf { E n c ^ { o f f } } ( P P )$ 算法。输入系统公开参数 $P P$ ，返回离线密文 $C T ^ { \mathrm { { o f f } } }$ 。

$\mathbf { d } ) \mathbf { E n c ^ { o n } } ( M , I , \ C T ^ { \mathrm { o f f } } , P P )$ 算法。输入消息 $M$ 、用户的身份信息 $\mid I _ { \setminus }$ 离线密文 $C T ^ { \mathrm { { o f f } } }$ 和系统公开参数 $P P$ ，输出密文 $\mathbf { \Psi } _ { C T \in \mathbf { \Psi } }$ $C$ 。

$\mathbf { e } ) \mathbf { D e c } ( S K _ { I } , C T , P P )$ 算法。输入用户私钥 $S K _ { I }$ 、密文 $C T \in C$ 和公开参数 $P P$ ，返回消息 $M \in M$ 或 $\perp$ 。

上述给出的算法要求满足下面的正确性约束条件：对于给定的身份信息 $I$ 和与之对应的私钥 $S K _ { I }$ ，有$\mathrm { D e c } ( S K _ { I } , \mathrm { E n c } ^ { \mathrm { o n } } ( M , I , \mathrm { E n c } ^ { \mathrm { o f f } } ( P P ) , P P ) , P P ) \lnot M _ { \circ }$

# 2.2安全模型

lrIBOOE方案抵抗选择明文攻击达到完全安全性和泄露弹性，如果任一概率多项式时间（PPT）算法在下面挑战者 $B$ 与敌手 $A$ 游戏 $\mathbf { G a m e } _ { \mathrm { R e a l } }$ 中的优势是可忽略的。对于安全参数$k$ 和泄露参数 $\scriptstyle { l = l ( k ) }$ ，游戏GameReal定义如下：

初始化阶段。挑战者 $B$ 输入安全参数 $k$ 运行 Setup(1)算法，将系统公开参数 $P P$ 返回给敌手 $A$ ，秘密保存主私钥MSK。此外， $B$ 初始化两个集合 $K = \emptyset$ 和 $L { = } \emptyset$ 分别用于统计密钥提取询问和密钥泄露询问。两个集合 $K$ 和 $L$ 都是身份 $I$ ，用户私钥 $S K _ { I }$ 和计数器cntr三个元组的集合。即 $( I , S K _ { I } , c n t r )$ $\in I { \times } S K { \times } N _ { \circ }$ （204号

阶段1敌手 $A$ 适应性地进行如下询问。

a) $\mathtt { e x t } ( I )$ 询问：挑战者 $B$ 运行 $\mathbf { E x t } ( P P , I , M S K )$ 算法生成对应 $I$ 的用户私钥 $S K _ { I }$ ，并将元组 $( I , S K _ { I } , 0 )$ 从集合 $L$ 移到 $K$ 。

b)Leak $( I , h _ { \mathrm { i } } )$ 询问：挑战者 $B$ 首先检查是否满足 $( I , S K _ { I , c n t r } )$ $\in L$ ，若不满足，则 $B$ 调用 $\mathbf { E x t } ( P P , I , M S K )$ 算法生成 $S K _ { I }$ ，并将元组 $( I , S K _ { I } , 0 )$ 添加到集合 $L$ 中，然后 $B$ 再检查是否满足$c n t r + l _ { i } { \leq } l$ ，若满足则将 $h _ { \mathrm { i } } ( S K _ { I } )$ 转发给敌手 $A$ ，同时设置 $c n t r =$ $c n t r + l _ { i }$ ；否则，返回 $\perp$ 。

c)Reveal $( I )$ 询问：挑战者 $B$ 首先检查是否满足 $( I , S K _ { I , c n t r } )$ $\in L$ ，若满足，则将元组 $( I , S K _ { I } , c n t r )$ 移到集合 $K$ 中，并将私钥$S K _ { I }$ 转发给敌手 $A$ 。若不在集合 $L$ 而在集合 $K$ 中，则 $B$ 泄露$S K _ { I }$ ；若既不在集合 $L$ 也不在集合 $K$ 中，则 $B$ 调用$\mathbf { E x t } ( P P , I , M S K )$ 算法生成 $S K _ { I }$ ，将元组 $( I , S K _ { I } , 0 )$ 添加到集合 $K$ 中，并返回 $S K _ { I }$ 。

挑战阶段。敌手 $A$ 输出两个等长消息 $M _ { 1 } , M _ { 2 } \in M$ 和挑战身份 $\boldsymbol { I } ^ { * }$ 。挑战者 $B$ 随机选取 $b \in \{ 0 , 1 \}$ ，设置 $C T ^ { * } { = } \mathbf { E n c } ^ { 0 \mathbf { n } } ( M _ { b } ,$ $I , { \mathrm { E n c } } ^ { \mathrm { o f f } } ( P P ) , P P )$ 并将 $\boldsymbol { C } \boldsymbol { T } ^ { * }$ 发送给敌手 $A$ 。

阶段2同阶段1，但是不允许敌手 $A$ 进行Leak $( I , h _ { \mathrm { i } } )$ 询问和Reveal $( I )$ 询问，继续 $\operatorname { E x t } ( I )$ 询问 $\boldsymbol { ( I \ne I } ^ { * }$ ）。

猜测阶段。敌手 $A$ 输出对 $b$ 的猜测 $b$ 。如果 $b = b$ ，则 $A$ 获胜。

定义7如果任何概率多项式时间敌手 $A$ 赢得游戏Gamereal的概率都可以忽略，则称该lrIBOOE方案抵抗选择明文攻击达到完全安全性和泄露弹性（IND-Ir-CPA)。

# 3 本文所提出的IrIBOOE方案

本文的IrIBOOE方案 $\varSigma$ 由五个算法组成：初始化算法Setup、密钥提取算法 Ext、离线加密算法 Encof、在线加密算法 Enco 和解密算法Dec。

a)Setup算法。输入系统安全参数 $k$ 0

(a)选取阶为 $N = { \ p } _ { 1 } p _ { 2 } { p } _ { 3 }$ 的双线性群 $G$ ，其中 $p _ { 1 } , ~ p _ { 2 }$ 和 $p _ { 3 }$ 是3个不同的素数，令 $G _ { i }$ 表示 $G$ 中阶 $p _ { i }$ 的子群，合数阶群的一个双线性映射 $e { \mathrel { : } } G { \times } G {  } G _ { T }$

(b)选取一个具有参数 $( \log | G _ { 1 } | - l , \varepsilon _ { \mathrm { e x t } } )$ 的提取函数 $e x t$ ，随机选取 $u , g , h \in G _ { 1 } , \alpha , \beta \in Z _ { \mathrm { N } }$ ，选取群 $G _ { 3 }$ 的生成元 $g _ { 3 }$ ，输出系统公开参数 ${ \cal P } { \cal P } = ( N , G , G _ { T } , e , g , u , h , e ( g , g ) ^ { \alpha } , e ( g , g ) ^ { \beta } , e x t )$ 和主密钥$\scriptstyle M S K = ( \alpha , \beta , g _ { 3 } )$ 。

$\mathbf { b } ) \mathbf { E x t } ( P P , I , M S K )$ 算法。随机选取 $t , r \in Z _ { \mathrm { N } }$ 和 $\rho , \rho ^ { \prime } \in Z _ { \mathrm { N } }$ 设置身份 $I$ 的私钥 $S K _ { I } = ( k _ { 1 } , k _ { 2 } , k _ { 3 } ) = ( t , g ^ { \alpha } g ^ { - \beta t } ( u ^ { I } h ) ^ { r } g _ { 3 } ^ { \rho } , g ^ { - r } g _ { 3 } ^ { \rho ^ { * } } )$ 。

（204号 $\mathbf { c } ) \mathbf { E n c ^ { o f f } } ( P P )$ 算法：随机选取 $s \gets \{ 0 , 1 \} ^ { u }$ 和 $\theta , w , z \in { Z } _ { \mathrm { N } }$ ，设置 $c _ { 1 } = s$ ，计算计算 $c _ { 2 } { = } g ^ { z }$ ， $c _ { 3 } \mathrm { = } ( u ^ { \theta } h ) ^ { z }$ ， $\scriptstyle c _ { 4 } = u ^ { z w }$ ， $_ { c 5 } { = } e ( g , g ) ^ { \beta z }$ ， $\scriptstyle c _ { 6 } =$ $e ( g , g ) ^ { \alpha z }$ 。输出离线密文 $C T ^ { \mathrm { o f f } } { = } ( c _ { 1 } { , } c _ { 2 } { , } c _ { 3 } { , } c _ { 4 } { , } c _ { 5 } { , } c _ { 6 } { , } w , \theta )$ 。

$\mathbf { d } ) \mathbf { E n c ^ { o n } } ( M , I , \ C T ^ { \mathrm { o f f } } , P P )$ 算法。输入消息 $M$ ，用户身份 $I$ 离线密文 $C T ^ { \mathrm { { o f f } } }$ 和公开参数 $P P$ ，计算 $c _ { 0 } = e x t ( c _ { 1 } , c _ { 6 } ) \oplus M$ ，输出密文 $C T = \left( c _ { 0 } , c _ { 1 } , c _ { 2 } , c _ { 3 } , c _ { 4 } , c _ { 5 } , w _ { 1 } \right)$ ，其中 $w _ { 1 } { = } w ^ { - 1 } ( I { - } \theta ) { \bmod { Z } } _ { \mathrm { N } }$ 。

e)Dec( $S K _ { I }$ ， $_ { C T , P P ) }$ 算法。给定密文$C T = \left( c _ { 0 } , c _ { 1 } , c _ { 2 } , c _ { 3 } , c _ { 4 } , c _ { 5 } , w _ { 1 } \right)$ ，采用用户私钥 $S K _ { I }$ 解密如下：

$$
{ \cal M } = c _ { 0 } \oplus e x t ( e ( k _ { 2 } , c _ { 2 } ) e ( k _ { 3 } , c _ { 3 } c _ { 4 } ^ { w _ { 1 } } ) c _ { 5 } ^ { k _ { 1 } } , c _ { 1 } )
$$

正确性验证：

$$
\begin{array} { r l } & { c _ { 0 } \oplus e x t ( e ( k _ { 2 } , c _ { 2 } ) e ( k _ { 3 } , c _ { 3 } c _ { 4 } ^ { w _ { 1 } } ) c _ { 5 } ^ { k _ { 1 } } , c _ { 1 } ) } \\ & { = c _ { 0 } \oplus e x t ( e ( g ^ { \alpha } g ^ { - \beta t } ( u ^ { I } h ) ^ { r } g _ { 3 } ^ { \rho } , g ^ { z } ) e ( k _ { 3 } , c _ { 3 } c _ { 4 } ^ { w _ { 1 } } ) e ( g , g ) ^ { \beta z t } , c _ { 1 } ) } \\ & { = c _ { 0 } \oplus e x t ( e ( g ^ { \alpha } ( u ^ { I } h ) ^ { r } , g ^ { z } ) e ( g ^ { - r } g _ { 3 } ^ { \rho } , ( u ^ { \theta } h ) ^ { z } ( u ^ { z w } ) ^ { w ^ { - 1 } ( I - \theta ) } ) , c _ { 1 } ) } \\ & { = c _ { 0 } \oplus e x t ( e ( g ^ { \alpha } ( u ^ { I } h ) ^ { r } , g ^ { z } ) e ( g ^ { - r } , ( u ^ { I } h ) ^ { z } ) , c _ { 1 } ) } \\ & { = c _ { 0 } \oplus e x t ( e ( g ^ { \alpha } , g ^ { z } ) , c _ { 1 } ) = c _ { 0 } \oplus e x t ( c _ { 6 } , c _ { 1 } ) = M } \end{array}
$$

# 3.1半功能材料

半功能密文：假定标准密文 $C T = ( c _ { 0 } ^ { \prime } , c _ { 1 } ^ { \prime } , c _ { 2 } ^ { \prime } , c _ { 3 } ^ { \prime } , c _ { 4 } ^ { \prime } , c _ { 5 } ^ { \prime } , w _ { 1 } ^ { \prime } )$ ，设 $g _ { 2 }$ 是子群 $G _ { 2 }$ 的生成元，选取随机值 $\begin{array} { r l } { \delta , z _ { c } \gets } & { { } Z _ { N } \times Z _ { N } } \end{array}$ ，设置半功能密文为 $C T = ( c _ { 0 } ^ { \prime } , c _ { 1 } ^ { \prime } , c _ { 2 } ^ { \prime } g _ { \ 2 } ^ { \delta } , c _ { 3 } ^ { \prime } g _ { \ 2 } ^ { \delta z _ { c } }$ ， ${ c _ { 4 } } ^ { \prime } g _ { 2 } ^ { \delta } , { c _ { 5 } } ^ { \prime } , { w _ { 1 } } ^ { \prime } )$ 。

半功能密钥：假定标准密钥 $S K _ { I } = ( k _ { 1 } ^ { \prime } , k _ { 2 } ^ { \prime } , k _ { 3 } ^ { \prime } )$ ，设 $g _ { 2 }$ 是子群 $G _ { 2 }$ 的生成元，选取随机值 $\gamma , z _ { k } \gets Z _ { N } \times Z _ { N }$ ，设置半功能密钥为 $S K _ { I } = ( k _ { 1 } ^ { ~ \prime } , k _ { 2 } ^ { ~ \prime } g _ { ~ 2 } ^ { \gamma } , k _ { 3 } ^ { ~ \prime } g _ { ~ 2 } ^ { \gamma z _ { k } } )$ 。

# 3.2安全模型

这里给出一系列附加的游戏模型 $G a m e _ { R e s t r i c t e d }$ 、 $L e a k _ { i }$ 、 $K G _ { i }$ 和 $G a m e _ { F i n a l }$ 。此外，前面定义的游戏 $G a m e _ { R e a l }$ 是一个真实的游戏，在这个游戏过程中生成的密文和密钥都是标准的。下面给出游戏模型的刻画。

a)游戏 $G a m e _ { R e s t r i c t e d }$ 。这是一个限制性游戏，限制敌手不能对模 $p _ { 2 }$ 后与挑战身份相等的身份的私钥进行密钥查询，即不能询问 $I { = } I ^ { * } { \bmod { p } } _ { 2 }$ 的身份 $I$ 的私钥。这个限制性条件在后续定义的游戏中都成立。

b)游戏Leaki。令L表示Leak询问中互不相同的最大的身份数。对于 $i \in [ \mathrm { L } \mathrm { - } 1 ]$ ，游戏 $L e a k _ { i }$ 与游戏 $G a m e _ { R e s t r i c t e d }$ 类似，除了Leaki中的密文是半功能的，并且前 $i$ 个身份（不包含挑战身份）的泄露私钥是半功能的。这里的Ext询问的密钥都是标准的。其中， $L e a k _ { 0 }$ 表示构造的所有密钥都是标准的，所有密文都是半功能的； $L e a k _ { L - 1 }$ 表示除了挑战身份的私钥外，所有泄露的私钥都是半功能的。

c)游戏 $K G _ { i }$ 。令K表示Ext询问的最大次数。对于 $i \in [ 1 , \mathrm { K } ]$ 游戏 $K G _ { i }$ 构造的密文都是半功能的，除了挑战身份之外所有泄露的密钥都是半功能的，由Ext询问生成的前 $i$ 个私钥都是半功能的，剩余的私钥都是标准的。注意，区别于L表示不同身份的最大数目，K是询问的次数。

d)游戏 $G a m e _ { F i n a l }$ 。与游戏 $K G _ { \kappa }$ 一样，除了密文是一个“修改的”半功能密文。这里， $t ^ { * }$ 是挑战身份私钥的标签。

$$
\begin{array} { r l } & { \sigma \gets \{ 0 , 1 \} , ( z , \eta ) \gets Z _ { N } \times Z _ { N } , } \\ & { c _ { 0 } = e x t ( c _ { 6 } , c _ { 1 } ) \oplus M _ { \sigma } , c _ { 1 } \gets \{ 0 , 1 \} ^ { u } , } \\ & { c _ { 6 } = e ( g , g ) ^ { \alpha z } e ( g , g ) ^ { \beta ( \eta - z ) t ^ { * } } } \\ & { c _ { 2 } = g ^ { z } g _ { 2 } ^ { \delta } , c _ { 3 } = ( u ^ { \theta } h ) ^ { z } g _ { 2 } ^ { \delta z _ { c } } , } \\ & { c _ { 4 } = u ^ { z \eta } g _ { 2 } ^ { \delta } , c _ { 5 } = e ( g , g ) ^ { \beta \eta } , } \end{array}
$$

# 3.3安全性证明

基于三个静态困难问题假设，通过证明上面的一系列游戏模型 $G a m e _ { R e a l }$ 、 $G a m e _ { R e s t r i c t e d }$ 、 $L e a k _ { i }$ 、 $K G _ { i }$ 和 $G a m e _ { F i n a l }$ 之间的不可区分性，推导出敌手在实际游戏 $G a m e _ { R e a l }$ 中的优势可忽略，则在标准模型下IrIBOOE方案 $\Sigma$ 在选择明文攻击的不可区分性游戏中达到 $l .$ 密钥泄露安全

定理1如果假设1\~3成立，上面的IrIBOOE方案 $\varSigma$ 抵抗选择明文攻击达到完全安全性和泄露弹性（IND-Ir-CPA）。

证明证明见下面6个引理。

引理2如果存在敌手 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { G a m e _ { R e a l } } - A d \nu _ { \Sigma , A } ^ { G a m e _ { R e s t r i c d } } = \varepsilon$ ,则可构建一个PPT挑战者B至少以 $\varepsilon / 4$ 的优势攻破假设1或假设2。

证明 $B$ 收到 $D ^ { 2 } = ( N _ { 1 } , G , G _ { T } , e , g _ { 1 } , g _ { 3 } , g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } )$ 和 $T \sb { \circ } B$ 随机 选择 $( x , y , \alpha , \beta ) \gets Z _ { N } ^ { 4 }$ ，令 $u { = } g ^ { x } , h { = } g ^ { y }$ ，生成公开参数 $P P$ 和主密 钥 $M S K { = } ( \alpha , \beta , g _ { 3 } ) \circ B$ 调用算法 $\mathbf { E x t } ( P P , I , M S K )$ 响应敌手 $A$ 的私

钥询问。

由 $A d \nu _ { \Sigma , A } ^ { G a m e _ { R e a l } } - A d \nu _ { \Sigma , A } ^ { G a m e _ { R e m i r i e d } } = \varepsilon$ 知敌手 $A$ 以 $\varepsilon$ 的概率询问$I { = } I ^ { * } { \bmod { p } } _ { 2 }$ ，即 $p _ { 2 }$ 整除 $\boldsymbol { I { - } } \boldsymbol { I } ^ { * }$ ，则 $B$ 通过计算 $a { = } g c d ( I { - } I ^ { * } , N )$ 得到$N$ 的一个非平凡因子。设置 $b { = } N / a$ ，则分为下面两种情况：

a） $b { = } p _ { 1 }$ 或 $b { = } p _ { 1 } p _ { 3 }$ 。挑战者B通过验证 $T _ { \nu } ^ { b }$ 是否是单位元攻破假设1。

b） $b { = } p _ { 3 }$ 。挑战者B通过验证 $e ( ( g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } ) ^ { b } , T _ { \nu } )$ 是否是单位元攻破假设2。

通过上述分析，挑战者B可以根据 $A$ 的输出区分两种可能的结果，从而确定处于哪个游戏中。但是，根据假设1和假设2成立，游戏 $G a m e _ { R e a l }$ 和 $G a m e _ { R e s t r i c t e d }$ 是不可区分的。

引理3如果存在PPT敌手 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { G a m e _ { R e m r i c t e d } } - A d \nu _ { \Sigma , A } ^ { L e a k _ { 0 } } = \varepsilon$ 则可构建一个挑战者B以 $\varepsilon / 2$ 的优势攻破假设1。

证明 $B$ 收到 $D ^ { 1 = } ( N , G , G _ { T } , e ,$ $g _ { 1 , g 3 } )$ 和 $T$ ，其中 $T = g _ { 1 } ^ { a }$ 或$g _ { 1 } ^ { a } g _ { 2 } ^ { b }$ 。同引理2挑战者B选择和设置公开参数 $P P$ 和主密钥MSK。 $B$ 调用算法 $\mathbf { E x t } ( P P , I , M S K )$ 响应敌手 $A$ 的私钥询问。在挑战阶段， $A$ 发送给挑战者B两个等长的消息 $M _ { 0 }$ 、 $M _ { 1 }$ 和挑战身份 $\boldsymbol { I } ^ { * }$ 。挑战者B随机选择 $\sigma \gets \{ 0 , 1 \}$ ，利用 $T$ 构造挑战密文如下：

$$
\begin{array} { r l } & { c _ { 0 } ^ { * } = e x t ( c _ { 1 } ^ { * } , c _ { 6 } ^ { * } ) \oplus M _ { \sigma } , c _ { 1 } ^ { * } \gets \{ 0 , 1 \} ^ { u } , \sigma \gets \{ 0 , 1 \} , } \\ & { ( w , \theta ) \gets Z _ { N } \times Z _ { N } , c _ { 2 } ^ { * } = T , c _ { 3 } ^ { * } = T ^ { x \theta + y } , c _ { 4 } ^ { * } = T ^ { \theta w } , } \\ & { c _ { 5 } ^ { * } = e ( T , g ) ^ { \beta } , c _ { 6 } ^ { * } = e ( T , g ) ^ { \alpha } , w _ { 1 } ^ { * } = w ^ { - 1 } ( I ^ { * } - \theta ) { \bmod { N } } } \end{array}
$$

如果 $T = g _ { 1 } ^ { a }$ ， $A$ 执行游戏 $G a m e _ { R e s t r i c t e d }$ ；如果 $T = g _ { 1 } ^ { a } g _ { 2 } ^ { b }$ ，则挑战密文是一个半功能密文且 $z _ { c } = x \theta + y$ ，由于 $z _ { c }$ 模 $p _ { 2 }$ 的值与xmodpi和ymodpi不相关，所以挑战密文的分布是正确的。敌手 $A$ 以 $\varepsilon$ 的优势区分游戏 $G a m e _ { R e s t r i c t e d }$ 和 $L e a k _ { 0 }$ ，则 $B$ 以同样的优势攻破假设1。通过上述分析，根据假设1成立，游戏$G a m e _ { R e s t r i c t e d }$ 和 $L e a k _ { 0 }$ 是不可区分的。

引理4 如果存在 PPT 敌手 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { L e a k _ { i - 1 } } - A d \nu _ { \Sigma , A } ^ { L e a k _ { i } } = \varepsilon$ ，则可构建一个挑战者B以 $\varepsilon / 2 L$ 的优势攻破假设2。

证明在挑战阶段之前， $B$ 不确定哪一个身份是挑战身份 $\boldsymbol { I } ^ { * }$ ，它随机选取 $i ^ { * } \gets \{ 1 , 2 , . . . , L \}$ 作为对挑战身份的猜测，猜对的概率为 $1 / L _ { \circ }$ 则对于第 $i ^ { * }$ 次私钥询问， $B$ 总用标准密钥响应。

$B$ 收到 $D ^ { 2 } = ( N _ { 1 } , G , G _ { T } , e , g _ { 1 } , g _ { 3 } , g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } )$ 和 $T$ ，其中 $T = g _ { 1 } ^ { a } g _ { 3 } ^ { c }$ 或 $g _ { 1 } ^ { a } g _ { 2 } ^ { b } g _ { 3 } ^ { c }$ 。公开参数 $P P$ 和主密钥MSK的构造同引理2。挑战者B和敌手 $A$ 交互如下：

密钥询问：

对于前i-1个密钥询问， $B$ 选取 $t , r , \rho , \rho ^ { , } , \rho ^ { , \prime } { \in } Z _ { \mathrm { N } }$ ， $I$ 表示敌手 $A$ 询问的身份。 $B$ 构造私钥如下：

$k _ { 1 } = t , k _ { 2 } = g ^ { \alpha } g ^ { - \beta t } ( u ^ { I } h ) ^ { r } ( g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } ) ^ { \rho } , k _ { 3 } = g ^ { - r } ( g _ { 2 } ^ { x _ { 2 } } g _ { 3 } ^ { x _ { 3 } } ) ^ { \rho ^ { \prime } } g _ { 3 } ^ { \rho ^ { \ast } }$ （204号 对于第 $i$ 个密钥询问， $B$ 选取 $t { \mathrm { , } } \rho { \in } Z _ { \mathrm { { N } } }$ 和 $\scriptstyle z _ { k } = x \theta + y$ ，采用挑战项 $T$ 构造私钥如下：

$$
k _ { 1 } = t , k _ { 2 } = g ^ { \alpha } g ^ { - \beta t } T ^ { z _ { k } } g _ { 3 } ^ { \rho } , k _ { 3 } = T
$$

其中， $t , \rho \gets Z _ { N } \times Z _ { N }$ ， $z _ { k } = x \theta + y$ 。

对于其他的密钥询问， $B$ 总用主私钥构造标准密钥来响应。

挑战阶段：当 $B$ 对挑战身份 $\boldsymbol { I } ^ { * }$ 的猜测不正确则退出；否则 $B$ 随机选择 $\sigma \gets \{ 0 , 1 \}$ ，并给 $A$ 返回如下的挑战密文：

$$
\begin{array} { r l } & { c _ { 0 } ^ { * } = e x t ( c _ { 1 } ^ { * } , c _ { 6 } ^ { * } ) \oplus M _ { \sigma } , c _ { 1 } ^ { * } \gets \{ 0 , 1 \} ^ { u } , } \\ & { c _ { 2 } ^ { * } = g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , c _ { 3 } ^ { * } = ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } ) ^ { x \theta + y } , c _ { 4 } ^ { * } = ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } ) ^ { \theta w } , } \\ & { c _ { 5 } ^ { * } = e ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , g ) ^ { \beta } , c _ { 6 } ^ { * } = e ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } , g ) ^ { \alpha } , } \\ & { ( w , \theta ) \gets Z _ { N } \times Z _ { N } , w _ { 1 } ^ { * } = w ^ { - 1 } ( I ^ { * } - \theta ) \bmod N } \end{array}
$$

这是合理分布的半功能密文，其中暗含半功能参数$z _ { c } = x \theta + y$ ，即 $c _ { 3 } ^ { * } c _ { 4 } ^ { * w _ { 1 } ^ { * } } = ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } ) ^ { x \theta + y }$ 。在敌手 $A$ 看来，对所有的$I \neq I ^ { * } { \bmod { N } }$ ， $z _ { c } = x \theta + y$ 和 $z _ { k } = x \theta + y$ 是模 $p _ { 2 }$ 下的随机分布。

如果 $T = g _ { 1 } ^ { a } g _ { 3 } ^ { c }$ ， $A$ 执行游戏 $L e a k _ { i - 1 }$ ；如果 $T = g _ { 1 } ^ { a } g _ { 2 } ^ { b } g _ { 3 } ^ { c }$ ，则 $A$ 执行游戏Leaki。因此，如果敌手 $A$ 以 $\varepsilon$ 的优势区分游戏 $L e a k _ { i - 1 }$ 和 $L e a k _ { i }$ ，则 $B$ 以 $\varepsilon / 2 L$ 的优势攻破假设2。通过上述分析，根据假设2成立，游戏 $L e a k _ { i - 1 }$ 和Leaki是不可区分的。

引理5如果存在 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { L e a k _ { L - 1 } } - A d \nu _ { \Sigma , A } ^ { K G _ { 1 } } = \varepsilon$ ，那么就能构建一个挑战者B以 $\varepsilon / 2 L$ 的优势攻破假设2。

引理6如果存在 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { K G _ { i - 1 } } - A d \nu _ { \Sigma , A } ^ { K G _ { i } } = \varepsilon$ ，那么就能构建一个挑战者B以 $\varepsilon / 2 L$ 的优势攻破假设2。

证明引理5和6的证明与引理2和引理3的证明类似。这里省略。挑战者以 $1 / L$ 的概率猜测挑战身份，为所有泄露的身份 $I ( I \neq I ^ { * } { \bmod { N } }$ )创建半功能私钥。然后，对于引理5和6中分别仿真第一阶段的私钥或者第 $i$ 次密钥询问 $\mathrm { E x t } ( I )$ ，挑战者再利用假设2的挑战项来构造。第 $i$ 次密钥询问 $\mathrm { E x t } ( I )$ 之前返回半功能私钥，之后返回标准私钥。这里，注意计数询问次数，而非身份个数。此外，可能在阶段2进行第 $i$ 次密钥询问，区别于与泄露询问只在阶段1。

引理7如果存在 $A$ 使得 $A d \nu _ { \Sigma , A } ^ { K G _ { K } } - A d \nu _ { \Sigma , A } ^ { G a m e _ { F i n o l } } = \varepsilon$ ，那么就能构建一个挑战者B以 $\varepsilon / 2 L$ 的优势攻破假设3。

证明 $B$ 收到 $D ^ { 3 } = ( N _ { 1 } , G , G _ { T } , e , g _ { 1 } , g _ { 3 } , g _ { 1 } ^ { \beta } g _ { 2 } , g _ { 1 } ^ { z } g _ { 2 } ^ { x _ { 2 } } , g _ { 2 } ^ { y _ { 2 } } )$ 和 $T$ ，其中 $T = e ( g _ { 1 } , g _ { 1 } ) ^ { \beta z }$ 或 $e ( g _ { 1 } , g _ { 1 } ) ^ { \beta \eta }$ 。挑战者B随机选取 $( x , y , t ^ { * } , \tilde { \alpha } ) \gets Z _ { N } ^ { 4 }$ ，隐式地包含 $\alpha = \beta t ^ { * } + \tilde { \alpha }$ ，则设置公开参数（204号 $\begin{array} { r } { e ( g , g ) ^ { \beta } = e ( g _ { 1 } ^ { \beta } g _ { 2 } , g _ { 1 } ) ^ { \beta } , e ( g , g ) ^ { \alpha } = e ( g _ { 1 } ^ { \beta } g _ { 2 } , g _ { 1 } ) ^ { t ^ { * } } , u = g ^ { x } , \quad h = g ^ { y } } \end{array}$ ，并且发送公开参数 $P P$ 给敌手 $A$ 。

$B$ 以 $1 / L$ 的概率猜对挑战身份 $\boldsymbol { I } ^ { * }$ 的位置 $i ^ { * }$ 。

阶段1密钥询问：当 $A$ 对身份 $I$ 进行密钥查询时， $B$ 构造身份 $I$ 私钥如下：

当 $I \neq I ^ { ( i ^ { * } ) }$ 时， $B$ 随机选择 $\tilde { t } , \rho , \rho ^ { \prime } , \rho " , \rho "  Z _ { N } ^ { 5 }$ ，构造身份 $I$ 的私钥：

$$
( t ^ { * } - \tilde { t } , ( g _ { 1 } ^ { \beta } g _ { 2 } ) ^ { \bar { t } } g _ { 1 } ^ { \bar { \alpha } } ( u ^ { I } h ) ^ { r } g _ { 3 } ^ { \rho } ( g _ { 2 } ^ { y _ { 2 } } ) ^ { \rho " } , g _ { 1 } ^ { - r } ( g _ { 2 } ^ { y _ { 2 } } ) ^ { \rho " } g _ { 3 } ^ { \rho ^ { * } } ) \ _ { \bullet }
$$

当 $I = I ^ { ( i ^ { * } ) }$ 时， $B$ 均匀地随机选择 $r , \rho , \rho ^ { \prime }  Z _ { N } ^ { 3 }$ ，构造身份 $I$ 私钥 $( t ^ { * } , g _ { 1 } ^ { \tilde { \alpha } } ( u ^ { I ^ { ( * ) } } h ) ^ { r } g _ { 3 } ^ { \rho } , g _ { 1 } ^ { - r } ( g _ { 2 } ^ { y _ { 2 } } g _ { 3 } ^ { \rho ^ { * } } ) = ( k _ { 1 } ^ { * } , k _ { 2 } ^ { * } , k _ { 3 } ^ { * } )$ 。

挑战阶段：敌手 $A$ 发送给 $B$ 等长消息 $M _ { 0 }$ 和 $M _ { 1 }$ 。 $B$ 随机 选择 $\sigma \gets \{ 0 , 1 \}$ ，构造挑战密文为

$$
\begin{array} { r l } & { c _ { 0 } ^ { * } = e x t ( c _ { 1 } ^ { * } , c _ { 6 } ^ { * } ) \oplus M _ { \sigma } , c _ { 1 } ^ { * } \gets \{ 0 , 1 \} ^ { u } , } \\ & { c _ { 2 } ^ { * } = ( g _ { 1 } ^ { z } g _ { 2 } ^ { x _ { 2 } } ) ^ { x w } , c _ { 3 } ^ { * } = ( g _ { 1 } ^ { z } g _ { 2 } ^ { x _ { 2 } } ) ^ { x \theta + y } , c _ { 4 } ^ { * } = ( g _ { 1 } ^ { z } g _ { 2 } ^ { x _ { 2 } } ) ^ { \theta w } , } \\ & { c _ { 5 } ^ { * } = T , c _ { 6 } ^ { * } = e ( k _ { 2 } ^ { * } , c _ { 2 } ^ { * } ) e ( k _ { 3 } ^ { * } , c _ { 2 } ^ { * } c _ { 4 } ^ { * } ) c _ { 4 } ^ { * } , } \\ & { ( w , \theta ) \gets Z _ { N } \times Z _ { N } , w _ { 1 } ^ { * } = w ^ { - 1 } ( I ^ { * } - \theta ) { \bmod { N } } } \end{array}
$$

其中： $( k _ { 1 } ^ { * } , k _ { 2 } ^ { * } , k _ { 3 } ^ { * } )$ 是在阶段1中为挑战身份 $\boldsymbol { I } ^ { * }$ 构造的标准私钥。这里设置 $z _ { c } = x \theta + y$ ， $c _ { 3 } ^ { * } c _ { 4 } ^ { * w _ { 1 } ^ { * } } = ( g _ { 1 } ^ { x _ { 1 } } g _ { 2 } ) ^ { x \theta + y }$ ，因为 $^ { x , y }$ 的值只与模 $p _ { 1 }$ 有关系， $z _ { c }$ 的值只与模 $p _ { 2 }$ 相关，对于敌手 $A$ 而言，它们看起来是随机的。

如果 $T = e ( g _ { 1 } , g _ { 1 } ) ^ { \beta z }$ ，则 $A$ 执行游戏 $\operatorname { K G } _ { K }$

如果 $T = e ( g _ { 1 } , g _ { 1 } ) ^ { \beta \eta }$ ， $B$ 构造的是无效的半功能密文，因为$e ( k _ { 2 } ^ { * } , c _ { 2 } ^ { * } ) e ( k _ { 3 } ^ { * } , c _ { 2 } ^ { * } c _ { 4 } ^ { * } { } ^ { * } ) c _ { 4 } ^ { * } { } ^ { k _ { 1 } ^ { * } } = e ( g , g ) ^ { \alpha z } e ( g , g ) ^ { \beta ( \eta - z ) t ^ { * } }$ ，则 $A$ 执行游戏 $G a m e _ { F i n a l }$ ，则 $B$ 以 $\varepsilon / 2 L$ 的优势攻破假设2。但是，根据假设3成立，所以游戏 $K G _ { \kappa }$ 和 $G a m e _ { F i n a l }$ 是不可区分。

通过引理2\~7的证明，推导得出游戏 $G a m e _ { R e a l }$ 、 $G a m e _ { R e s t r i c t e d }$ ，$L e a k _ { i }$ 、 $K G _ { i }$ 和 $G a m e _ { F i n a l }$ 之间具有不可区分性，则敌手无法区分真实游戏 $G a m e _ { R e a l }$ 和游戏 $G a m e _ { F i n a l }$ 。因此，敌手 $A$ 攻击lrIBOOE方案 $\Sigma$ 失败，则lrIBOOE方案 $\Sigma$ 是IND-lr-CPA安全的，即

完成定理1的证明。

# 3.4性能比较

本小节在计算复杂性和存储代价方面对所提方案的效率进行分析，通过标准模型下传统的IBOOE方案[5,8,20]进行比较，具体如表1所示。其中， $E$ 表示群 $G$ 或 $G _ { T }$ 中的幂指数运算， $M E$ 表示群 $G$ 或 $G _ { T }$ 中的多点乘运算， $m _ { c }$ 是 $Z _ { p } ^ { * }$ 或 $Z _ { N }$ 中的模运算， $| G |$ 表示群 $G$ 中元素的长度。LR表示泄露弹性。

表1性能比较  
Table 1Performance comparison   

<html><body><table><tr><td>方案</td><td>离线加密</td><td>在线加密</td><td>安全性模型</td></tr><tr><td>文献[5]</td><td>3E</td><td>1mc</td><td>选择安全CPA</td></tr><tr><td>文献[8]</td><td>2E</td><td>1mc</td><td>选择安全CPA</td></tr><tr><td>文献[20]</td><td>4E+1ME</td><td>1mc</td><td>完全安全CPA</td></tr><tr><td>本文方案</td><td>4E+2ME</td><td>1mc</td><td>完全安全CPA 和LR</td></tr></table></body></html>

通过表1，本文的方案中构造的在线加密算法只需一个异或运算和模运算即可生成密文。由于在Z中的模运算比群$G$ 或 $G _ { T }$ 中的幂乘法运算快很多倍，这非常适用于计算能力受限的轻量级设备。本文的方案与文献[20]都采用了双系统加密系统，本文的方案在离线加密阶段增加了1个多点乘运算，但是本方案抵抗选择明文攻击达到完全安全性和泄露弹性。此外，在解密过程中，与传统IBOOE相比，没有额外增加运算量。通过对比，本文得出本方案在没有增加计算代价的前提下，达到完全安全性和密钥弹性泄露。因此，本文提出的lrIBOOE方案在保证效率的同时提供泄露弹性，特别适合于轻量级设备收集敏感数据。

# 4 结束语

本文首次构造了一个泄露弹性在线/离线身份基加密方案，采用一系列游戏对敌手模型进行了详细刻画，并且采用双系统加密机制，基于合数阶双线性群上的静态假设，在标准模型下对其在密钥泄露环境下的选择明文安全性进行了严格的证明。与现有的IBOOE方案相比较，本文方案是高效的和安全的。但是新方案没有考虑适应性选择密文安全性。因此如何基于双系统加密机制，构造抵抗密文攻击的、高效的抗主密钥泄露和用户密钥泄露的IBOOE方案是今后研究工作中一个亟待解决的问题。

# 参考文献：

[1]Shamir A.Identity-based cryptosystems and signature schemes [C]// Advances in Cryptology-CRYPTO.Berlin:Springer-Verlag，1984: 47-53.   
[2]Boneh D，Boyen X.Efficient selective-ID secure identity-based encryptionwithoutrandomoracles[C]//Advances in Cryptology-EUROCRYPT.Berlin: Springer-Verlag,2004:223-238.   
[3]Waters B.Efficient identity-based encryption without random oracles [C]//Advances in Cryptology-EUROCRYPT.Berlin: Springer-Verlag, 2005:114-127.   
[4]Lewko AB,Waters B.New techniques for dual system encryption and fully secure HIBE with short ciphertexts [C]//Proc of the 7th Theory of Cryptography Conference.Berlin: Springer-Verlag,2010:455-479.   
[5]Guo Fuchun，Mu Yi,Chen Zhide.Identity-based online/offline encryption [Cl// Financial Cryptography and Data Security.Berlin: Springer-Verlag,2008: 247-261.   
[6]Liu JK,Zhou Jianying.An efficient identity-based online//offline encryption scheme[C]//Applied Cryptographyand Network Security.Berlin: Springer-Verlag,2009:156-167.   
[7]CHOW S S,LIU JK, Zhou Jianying.Identity-based online//ofline key encapsulation and encryption [C]// Proc of the 6th ACM Symposium on Information, Computer and Communications Security, New York: ACM Press,2011: 52-60.   
[8]Lai Jianchang,Mu Yi,Guo Fuchun,et al. Improved identity-based online//offline encryption [Cl/Proc of the 20th Australasian Conference Information Security and Privacy:Berlin: Springer-Verlag，2015: 160-173.   
[9]Lai Jianchang，Mu Yi，Guo Fuchun.Eficient identity-based online/offline encryption and signcryption with short ciphertext [J]. International Journal of Information Security,2017,16(3): 299-311.   
[10] Akavia A, Goldwaser S,Vaikuntanathan V. Simultaneous hardcore bits and cryptography against memory attacks [C]// Proc of the 6th IACR Theory of Cryptography Conference.Berlin: Springer-Verlag， 2009: 474-495.   
[11] Naor M, Segev G.Public-key cryptosystems resilient to key leakage [J]. SIAM Journal on Computing,2012,41(4): 772-814.   
[12] Chow S S M,Dodis Y,Rouselakis Y,et al. Practical leakage-resilient identity-based encryption from simple assumptions [Cl// Proc of the 17th ACM Conference on Computer and Communications Security.New York: ACM Press,2010: 152-161   
[13]Lewko A B,Rouselakis Y,Waters B.Achieving leakage resilience through dual system encryption [C]//Proc of the 8th IACR Theory of Cryptography Conference.Berlin: Springer-Verlag,2011: 70-88   
[14] Zhang Mingwu，Yang Bo，Takagi T. Bounded leakage-resilient functional encryption with hidden vector predicate [J].The Computer Journal, 2013,56(4): 464-477.   
[15] Hazay C,Wee H,Wichs D.Leakage-resilient cryptography from minimal assumptions [J]. Journal of Cryptology,2016,29(3): 514-551.   
[16] Zhou Yanwei，Yang Bo.Continuous Leakage-resilient public-key encryption scheme with CCA security [J]. Computer Journal,2017:60 (8).   
[17] Yu Zuoxia,AU MH, Xu Qiuliang,etal. Towards leakage-resilient fine-grained access control in fog computing [J]. Future Generation Computer Systems,2018(78): 763-777.   
[18] Li Sujuan,Mu Yi, Zhang Mingwu,et al. Continuous leakage resilient lossy trapdoor functions [J]. Information,2017,8(2): 38.   
[19] Zhang Mingwu,LengWentao,Ding Yong，etal.Tolerating sensitive-leakage with larger plaintext-space and higher leakage-rate in privacy-aware Internet-of-things [J]. IEEE Access,2018(99):1-1.   
[20]王占君，李杰，马海英，等．完全安全的身份基在线/离线加密[J]. 计算机应用，2014,34(12):3458-3461.(Wang Zhanjun,Li Jie,Ma Haiying,et al.Fully secure identity-based online/offline encryption [J]. Journal of Computer Applications,2014,34(12): 3458-3461.)