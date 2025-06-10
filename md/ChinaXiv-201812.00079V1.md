# 可公开验证的属性基数据可恢复性证明方案

任燕1,2，唐春明²

(1.运城学院 数学与信息技术学院，山西 运城 044000;2.广州大学 数学与信息科学学院 广东省信息安全技术重点实验室，广州 510006)

摘要：数据可恢复性证明方案可以有效解决用户将数据存储在不诚实的服务器上时，需要对数据的完整性进行验证的问题。针对目前存在的大部分方案都是使用的基于身份的密码体制的问题，采用更直观灵活的基于属性的密码体制设计了基于属性的数据可恢复性证明方案。给出了方案的相关定义、安全模型和具体的构造，同时证明了方案的正确性和安全性。

关键词：云计算；基于属性密码学；数据可恢复证明；公开验证 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2018.06.0557

# Attribute-based proof of retrievability with public verifiability

Ren Yan1, 2, Tang Chunming² (1.School of Mathematics&InformationTechnology，Yuncheng University，YunchengShanxi O440o0,China;2.Key Laboratory of Information Security,Guangzhou University, Guangzhou 51ooo6, China)

Abstract:When theuser stores the dataonan dishonest server,the integrityof the data needs to beverified,so the proof-of-retrievability(POR)system is proposed.Aimingatthe problemof identity-based cryptosystemused inmostof the existing solutions,a more intuitiveand flexible atribute-based cryptosystem isadopted todesignanatribute-based data recoverability prof scheme.This paper firstly proposed definition and modelof anatribute-based proof of retrievability withpublicverifiabilitythen,constructedanatribute-basedproofofretrievabilitywithpublicverifiability,finalyproved its correctness and security.

Key words:cloud computing; attribute-based cryptography; proof-of-retrievability; public verifiability

# 0 引言

在数据外包存储服务中，如何使数据拥有者有效而且安全地验证存储服务器是否正确存储了他们的数据是非常重要的。为了解决这个问题，Juels 等人[I首次正式地提出了数据可恢复性证明(proof of retrievability,POR)的概念和方案。在数据可恢复性证明的方案中，存储服务器必须向用户证明他们确实正确存储了用户的数据，并且让用户确信他可以恢复先前存储在服务器上的文件。文献[1]中所提的方案中，通过将一个伪装块隐藏在不变的文件块中来发现服务器对数据的修改，同时这个方案的通信代价是与每个文件块中元素数目成线性关系的。在此之后，很多学者对数据可恢复性证明的方案进行了研究。近年来的研究成果主要有：文献[2,3]中提出具有常数通信的POR方案；朱岩等人[4]在交互式证明系统的标准模型下提出了交互式可恢复性证明的形式化定义，并提出了一个实用的零知识可恢复性证明。该方案在Diffie-Hellman假设下被证明具有完备性、合理性和零知识性，该证明是通过建立多项式时间的知识提取器实现的，且该协议只需要发送固定大小的数据量就能够实现承诺、挑战、响应过程，并最大限度地减少网络通信。因此，该方案可用于大范围分布存储系统中实现大尺寸文件的公共远程验证。文献[5]提出了两个有效的动态的数据可恢复性证明方案，一个是私有验证，一个可以公开验证。文献[6\~9]分别提出了几个动态可公开验证的数据可恢复性证明方案。

目前存在的大部分方案都是使用的基于身份的密码体制的思想,本文考虑将基于属性的密码体制用在数据可恢复性证明中，与基于身份的密码体制相比,基于属性的密码体制更直观。例如,从签名来说,某人使用一个基于身份的签名对消息进行签名后，验证者可以证实该消息的签名确实来自这个人，但是对于这个人所拥有的权限和社会职能却一无所知；而基于属性的签名中验证者可以检验签名是否为相应的属性的拥有者的签名，所以可以知道签名者的权限和职能，并且对于签名者的身份具有匿名性。如果用现实中的盖章来说明基于身份的签名与基于属性的签名的不同，则基于身份的签名就像是盖私章，而基于属性的签名就像是盖公章，私人章只能说明负责人是谁，而公章则可以表明颁发此签名的单位机构或者属性。在实际生活中，公章显然比签名章更具可信度。

本文首次提出了基于属性的可公开验证的数据可恢复性证明方案的的定义和安全模型，实现了基于属性的可公开验证的数据可恢复性证明方案的构造，给出了方案的正确性和安全性证明。在本文的方案中,用户只知道文件所有者的属性，而不知道关于文件所有者的任何的身份信息。

# 1 预备知识

# 1.1双线性映射

设 $G _ { \mathrm { { r } } }$ ， $G _ { 2 }$ 是两个循环乘法群， $G _ { \mathrm { { \scriptscriptstyle i } } }$ 、 $G _ { 2 }$ 的阶均为素数q。设

$e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 为一个双线性映射.假定在 $G _ { 1 } , G _ { 2 }$ 上的离散对数问题(DLP问题)都是困难的,则双线性映射满足以下性质：

a)双线性性。对任意的 $P _ { \cdot }$ ， $Q \in \ G _ { 1 }$ 和所有的 $a , b \in Z _ { q }$ ，有$e ( P ^ { a } , Q ^ { b } ) = e ( P , Q ) ^ { a b }$ 。

b)非退化性。存在 $P , Q \in G _ { \mathrm { 1 } }$ 使得 $e ( P , Q ) \neq 1$ 。

c)可计算性。对于 $P , Q \in G _ { \mathrm { 1 } }$ 存在一个高效的算法计算$e ( P , Q )$ 。

# 1.2拉格朗日插值定理

设 $f ( x )$ 为 $x$ 的一个次数为 $n$ 的多项式 $f$ 的函数,如果给定多项式 $n { + } 1$ 个不同点 $( x _ { i } , f ( x _ { i } ) )$ ,则通过式(1)能唯一确定任意一个 $x$ 所对应的多项式 $f ( x )$ 值：

$$
f ( x ) = \sum _ { i = 1 } ^ { n } f ( x _ { i } ) ( \prod _ { 1 \leq k \neq i \leq n } ( x - x _ { k } ) { \big / } ( x _ { j } - x _ { k } ) )
$$

对于式(1)中可以定义拉格朗日系数 $\Delta _ { i , s }$ ,其中 $i \in Z _ { p }$ ，集合$s$ 中的元素取自 $Z _ { p }$ ：

$$
\Delta _ { i , s } \left( x \right) = \prod _ { i \in s , j \neq i } \frac { x - j } { i - j }
$$

# 1.3本方案依赖以下困难性问题

a)离散对数问题(DLP)。设 $\boldsymbol { G }$ 是一个阶为素数 $p$ 的加法循环群,对 $P , Q \in G$ ,不存在多项式时间的算法可以以不可忽略的优势计算出 $n \in Z _ { \mathfrak { q } }$ ,使得 $P = n Q$ 。

b)双线性对求逆问题。设 $\boldsymbol { \mathscr { e } }$ 是一个双线性映射, $\boldsymbol { G }$ 是一个阶为素数 $p$ 的加法循环群,对 $P \in G$ 和 $a = e ( P , Q )$ ,不存在多项式时间的算法可以以不可忽略的优势计算出 $Q \in G$ 。

c)计算Diffie-Hellman 问题(CBDH)。设 $G$ 是一个阶为素数 $q$ 的乘法循环群,对 $a , b \in Z _ { q }$ 和 $( P , P ^ { a } , P ^ { b } ) \in G _ { 1 }$ ,不存在多项式时间的算法可以以不可忽略的优势计算出 $e ( P , P ) ^ { a b }$ 。

# 2 基于属性的可公开验证数据可恢复性证明方案的定义和安全模型

一般地，一个基于属性的可公开验证的数据可恢复性证明方案有三个参与实体：数据拥有者、客户和云服务提供商。数据拥有者对数据进行采集，为了提高数据的鲁棒性，数据拥有者把采集到的数据进行纠错码编码，然后将编码后的数据存储到云端。满足数据拥有者指定属性的客户可以访问编码后的数据并对数据的完整性进行检验.为了验证数据的完整性，客户端生成一个挑战信息并把它发送给云端，然后云端对客户端所选择的文件块进行计算证明响应。收到证明后，客户端可以通过验证算法验证数据的完整性。

# 2.1基于属性的可公开验证的数据可恢复性证明的形式化定义

令 $\omega$ 是可能的属性集合， $\omega$ 上的一个断言实际上是一个输入为关于属性 $\omega$ 的布尔函数。当 $\Gamma ( \omega ^ { \prime } ) = 1$ 时，本文称属性集合 $\omega ^ { \prime } \subseteq \omega$ 满足一个断言「。方案的主要步骤如下所示：

算法  
setup 生成主公钥和主密钥  
keygen 生成属性集合密钥  
outsource1、编码2、计算认证标签  
proof用户发起挑战时服务器为用户生成  
verify用户验证文件是否完整保存

综上，一个基于属性的可公开验证的数据可恢复性证明方案语义定义如下：

定义1形式上一个基于属性的可公开验证的数据可恢复性证明方案由初始化算法 Setup、密钥生成算法Keygen、外包存储算法Outsource、证明算法 Proof 和验证算法 Verify

组成：

a)Setup。该算法的输入为安全参数 $k$ ，输出为系统的主公钥pk和主私钥mk。

b)Keygen。属性中心为用户所选择的属性集合生成密钥。

c)Outsource。外包存储分为两个阶段。第一个阶段为编码：输入为用户的私钥和文件 $M$ ，输出一个大小为 $n$ 的编码文件 $\tilde { M }$ ,第二个阶段为认证标签的计算：输入为编码文件 $\tilde { M }$ ，输出为标签。

d)Proof。输入为系统参数、断言「、满足 $\Gamma ( \omega ^ { \prime } ) = 1$ 的含有$\mathbf { \xi } _ { l }$ 个元素的属性集合 $S \subseteq \omega$ 和编码后的文件消息 $\tilde { M }$ ，输出为证明响应prf 。

e)Verify。输入为系统参数、证明响应prf，该算法的输出为 accept 或者 reject。

# 2.2安全模型

在这一节描述基于属性的可公开验证的数据可恢复性证明方案的安全模型。与文献[11\~13]一样，本文认为存储服务提供者是不可信且可能是恶意的，要求方案必须满足正确性和合理性。

# 定义2 正确性。

若对任意的由如上定义的算法(KeyGen,Outsource,Proof）生成的有效证明，验证算法都输出accept，则称一个基于属性的可公开验证的数据可恢复性证明方案是正确的。

对于合理性，若任意恶意的云服务提供者可以生成一个证明，通过验证算法，即验证算法相信他确实正确的存储了文件M，则他必须要有证明需要的 $\tilde { M }$ 。由[10-12]中提出的关于合理性的安全模型。类似地，本文给出下面的游戏。

a) Setup。挑战者运行 Setup 算法，获得公私钥对 $( p k , s k )$ ，并将pk发送给敌手。b)Outsource。敌手选择一个文件 $M$ ，将它发送给挑战者。挑战者运行Outsource 算法，用编码的文件来响应 $\tilde { M }$ 。c) Proof。(a)挑战随机生成一个挑战信息，并将它发送给敌手；(b）因为敌手可能丢失或者修改文件 $\tilde { M }$ 的一部分，敌手首先随机生成一个文件 $\tilde { M }$ ：(c）敌手通过运行任意的算法生成一个证明prf，并将prf发送给挑战者。d)Verify。挑战者运行验证算法来检验prf.当且仅当敌手可以对文件 $\tilde { M }$ 生成的证明prf且挑战者通过运行算法输出 accept 的时候，本文称敌手赢得游戏。

# 定义3合理性。

若对任意的概率多项式时间的敌手赢得上述游戏的概率是可忽略的，则称一个基于属性的可公开验证的数据可恢复性证明方案是合理的。

# 3 可公开验证的基于属性的可恢复性证明方案

假设集合 $U$ 中有 $\mathbf { \xi } _ { l }$ 个属性. $U$ 中每个元素对应于 $Z _ { _ { p } }$ 中一个唯一整数。在这个方案中文件 $\mathbf { \Omega } _ { M }$ 的规模是任意长度的比特串。

现在描述基于属性的可公开验证的数据可恢复性证明方案，它支持所有的断言 $\Gamma$ 。特别地，对门限值 $^ d$ 有

$$
\Gamma _ { { d , \omega } ^ { * } } ( \omega ^ { \prime } ) = \left\{ { 1 , \left| \omega ^ { \prime } \cap \omega ^ { * } \right| > d } \right.
$$

具体的构造如下：

1）初始化 (Setup)  
Setup阶段由以下几步完成：  
a）定义属性集合 $\omega$ ,简单起见令 $| \omega | = l$ 且本文可以取 $Z _ { { _ p } }$

的前 $\mathbf { \xi } _ { l }$ 个元素来做为这个集合,即： $1 , 2 , \cdots , l ( \mathrm { m o d } ) p$ 。

b）设 $G _ { \imath }$ 是阶为素数 $\boldsymbol { p }$ 的乘法循环群,随机选择一个生成元 $g \in G _ { 1 }$ ,随机选取 $x , \in Z _ { p } ^ { * }$ ，并令 $X = g ^ { x }$ 。

c）随机选择一个长度为 $n$ 的向量 $U = ( u _ { 1 } , u _ { 2 } , . . . , u _ { n } )$ ,这里的$u _ { i }$ 是群 $G _ { 1 }$ 中的元素且 $n < l$ 。

则公共参数为： $p a r a m s = ( g , X , d , U )$ 0主密钥为 $x$ 。

2）密钥生成 (key generation)按照如下步骤为用户设定的的属性集合 $\omega$ 生成私钥。

a)选择一个 $d - 1$ 阶的多项式 $q ( x )$ 满足 $q ( x ) = 0$ 。

b）对每个 $i \in \omega$ 计算： $\begin{array} { r } { d _ { i } = g ^ { q ( i ) } } \end{array}$

c）对每个 $i \in \omega$ 输出 $d _ { i }$ 做为私钥。

3）外包存储

a）给定一个数据文件 $M$ ，利用纠错码得到编码后的文件 $\tilde { M }$ 。

b）将编码后的文件 $\tilde { M }$ 分成 $n$ 个块, $\tilde { M } = ( \mu _ { 1 } , \mu _ { 2 } , . . . , \mu _ { n } )$ 其中$\mu _ { i } \in \{ 0 , 1 \} ^ { t }$ 。

c）对每个数据块按照如下的步骤完成认证标签计算：

(a)从 $\boldsymbol { Z } _ { p } ^ { * }$ 中随机选择一个文件名 name;

(b）随机选取的一个值 $s \in Z _ { p }$ ，并公开 $g ^ { s }$ ：

(c）计算： $\sigma _ { i } = d _ { i } ^ { \Delta _ { i , S } ( 0 ) } ( u ^ { H ( n a m e \parallel i ) } \prod _ { i = 1 } ^ { n } u _ { i } ^ { \mu _ { i } } ) ^ { s }$ ，这里 $i \in \{ 1 , 2 , \cdots , ~ n \} ~ , ~ S$ 是属性集合 $\omega$ 的一个子集,且 $\vert S \cap \omega \vert \geq d$ ， $u$ 为客户端随机选择的一个数，然后将 $\tilde { M }$ 和 $\sigma _ { i }$ 外包给云服务器存储。

4）验证挑战(verify challenge)

客户端为了验证服务器是否正确存储了文件,随机选择属性集合 $U$ 的 $^ d$ 个元素的子集 $\boldsymbol { s ^ { \prime } }$ 和 $r \in Z _ { { p } } ^ { * }$ 并将它们作为挑战发送给服务器。

5）证明生成 (ProofGen)

服务器收到验证挑战后计算： $\boldsymbol { \sigma } = \prod _ { i = 1 } ^ { n } \boldsymbol { \sigma _ { i } ^ { \prime } }$ ， $\psi = \prod _ { i = 1 } ^ { n } u _ { i } ^ { \mu _ { i } }$ .则生成的证明 $p r f = ( \sigma , \psi )$ .然后服务器将证明发送给客户端。

6）验证 (verify)

收到证明 $p r f$ 后，客户端首先计算： $\eta _ { i } = u ^ { H ( n a m e | i ) }$ $\scriptstyle \eta = \prod _ { i } \eta _ { i }$ ，然后验证如下等式是否成立来验证服务器是否正确存储了文件，且未对文件进行窜改：

$$
e ( \sigma , g ) = e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) e ( X , g ^ { r } )
$$

# 4 正确性和安全性分析

# 4.1 正确性分析

定理1方案的验证过程是正确的。

$$
e ( \sigma , g ) = e ( \prod _ { i = 1 } ^ { n } { \sigma _ { i } ^ { r } } , g ) =
$$

证明

$$
e ( \prod _ { i = 1 } ^ { n } d _ { i } ^ { \Delta _ { i , S } ( 0 ) r } ( u ^ { H ( n a m e | i ) } \prod _ { i = 1 } ^ { n } u _ { i } ^ { \mu _ { i } } ) ^ { r s } , g ) =
$$

$$
e ( \prod _ { i = 1 } ^ { n } d _ { i } ^ { \Delta _ { i , s } ( 0 ) r } , g ) e ( ( \prod u ^ { H ( n a m e | i ) } ) ^ { r s } , g ) { \bullet } e ( ( \prod _ { i = 1 } ^ { n } u _ { i } ^ { { \mu } _ { i } } ) ^ { s } , g ^ { r } ) =
$$

$$
e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) e ( X , g ^ { r } )
$$

# 4.2安全性分析

定理2本文方案中的证明prf 在CBDH假设下满足合理性，即它是不可伪造的。

证明假设一个概率多项式时间的敌手 $F$ 可以以不可忽略的优势赢得合理性游戏,则本文可以构建一个算法 $A$ 来解决CDH 问题。即算法 $A$ 在给定 $g$ ， $g ^ { r }$ ， $g ^ { \boldsymbol { x } }$ ,时,可计算出$e ( g , g ) ^ { r x }$ .具体过程如下：

1)初始化 (Setup)

$F$ 输出挑战断言，即 $\mathbf { \xi } _ { l }$ 个元素的属性集合 $\omega ^ { * }$ 的门限为 $\textit { d }$ 的函数．令 $g _ { 1 } = g ^ { x }$ 口

2)密钥生成 (key generation)

$A$ 可以对私钥进行查询.按照如下方式模拟生成属性 $\omega$ 的私钥:

a)随机选取 $s _ { 1 } \in Z _ { p } ^ { * }$ ,令 $s = - y + s _ { 1 } $ 。

b)定义三个集合 $\Gamma = \omega ^ { * } \cap \omega$ ， $\Gamma ^ { \prime }$ ， $S = \dot { \Gamma } \cup \{ 0 \}$ ，这里 $\Gamma ^ { \prime }$ 满足$\Gamma \subseteq \Gamma ^ { \prime } \subseteq \omega$ 。

若 $i \in \Gamma ^ { \prime }$ 则 $\begin{array} { r } { d _ { i } = g _ { 1 } ^ { \ \tau _ { i } } } \end{array}$ ,这里的 $\tau _ { i }$ 是在 $Z _ { p }$ 中随机选取。

若ieT,令,则d= 8 $d _ { i } = g _ { 1 } ^ { \ \sum _ { ( j \in \Gamma ^ { * } } \Delta _ { j , S } ( i ) q ( j ) + \Delta _ { 0 , S } ( i ) q ( 0 ) }$ $q ( i ) = \sum _ { ( j \in \Gamma ^ { \prime } } \Delta _ { j , S } ( i ) q ( j ) + \Delta _ { \scriptscriptstyle 0 , S } ( i ) q ( 0 )$ 可知 $A$ 正确模拟了私钥。因此有 $g _ { 1 } ^ { ~ q ( i ) } = g _ { 1 } ^ { ~ \sum _ { j = \Gamma ^ { * } } \Delta _ { j , S } ( i ) q ( j ) + \Delta _ { 0 , S } ( i ) q ( 0 ) }$

3)外包存储模拟

$A$ 可以用属性集合 $\omega$ 完成对消息 $\mid m$ 的外包存储。

若 $| \omega \cap \omega ^ { * } | \geq d$ ，则 $A$ 通过如下过程模拟签名：

选择随机的 $s \in Z _ { q }$ ,按照正常的方式得到属性集合 $\omega$ 对消息 $m$ 的外包存储。

若 $d \geq | \omega \cap \omega ^ { * } | \geq k$ ，则 $A$ 可以如下模拟签名：

$$
\sigma _ { i } ^ { ' } = g _ { 1 } ^ { ~ x } ( u ^ { H ( n a m e \parallel i ) } \prod _ { i = 1 } ^ { n } u _ { i } ^ { ~ \mu _ { i } } ) ^ { s } ~ _ { \circ }
$$

4)验证挑战模拟(verifychallenge)

客户端随机选择属性集合 $U$ 的 $\boldsymbol { \mathscr { d } }$ 个元素的子集 $\boldsymbol { S ^ { \prime \prime } }$ 和$r ^ { \prime } \in Z _ { p } ^ { * }$ 并将它们发送给服务器。

5)证明生成模拟 (ProofGen)

服务器计算： $\sigma ^ { \prime } = \prod _ { i = 1 } ^ { n } \sigma _ { i } ^ { { \prime } }$ ， $\psi ^ { \prime } = \prod _ { i = 1 } ^ { n } { u _ { i } ^ { \mu _ { i } } }$ ,则生成的证明$p r f ^ { \prime } = ( \sigma ^ { \prime } , \psi ^ { \prime } )$ .然后将证明发送给客户端。

验证过程模拟;

收到证明 $p r f ^ { \prime }$ 后，客户端首先计算： $\begin{array} { r } { \eta _ { i } = u ^ { H ( n a m e \parallel i ) } , \eta = \prod \eta _ { i } } \end{array}$ 然后如下等式成立：

$$
e ( \sigma ^ { \prime } , g ) = e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { \prime r } , g ^ { s } ) e ( X , g ^ { r } )
$$

这里 $p r f ^ { \prime } = ( \sigma ^ { \prime } , \psi ^ { \prime } ) \neq p r f = ( \sigma , \psi )$ （204号

由此可以得到：

$$
\begin{array} { c } { { e ( \sigma , g ) = e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) e ( X , g ^ { r } ) } } \\ { { e ( \sigma ^ { \prime } , g ) = e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { \prime r } , g ^ { s } ) e ( X , g ^ { r } ) } } \end{array}
$$

用式（1）除以式（2）得到 $\frac { e ( \sigma , g ) } { e ( \sigma ^ { \prime } , g ) } = \frac { e ( \psi ^ { r } , g ^ { s } ) } { e ( \psi ^ { \prime r } , g ^ { s } ) }$ 下面分析第一种情形：

若 $\sigma \neq \sigma ^ { \prime } , \psi = \psi ^ { \prime }$ 则： $e ( \sigma , g ) = e ( \sigma ^ { \prime } , g )$

即

$$
\begin{array} { c } { { e ( \sigma ^ { \prime } , g ) = e ( \sigma , g ) = e ( \prod \sigma _ { i } ^ { ' } , g ) = } } \\ { { e ( \prod d _ { i } ^ { \Delta _ { i , s } ( 0 ) r } ( u ^ { H ( n a n e | i ) } \prod u _ { j } ^ { \mu _ { j } } ) ^ { s r } , g ) = } } \\ { { e ( \prod _ { i = 1 } ^ { n } d _ { i } ^ { \Delta _ { i , s } ( 0 ) r } , g ) e ( ( \prod u ^ { H ( n a n e | i ) } ) ^ { r s } , g ) { \bullet e } ( ( \prod _ { i = 1 } ^ { n } u _ { i } ^ { \mu _ { i } } ) ^ { s } , g ^ { r } ) = } } \\ { { e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) e ( X , g ^ { r } ) } } \end{array}
$$

由于 $\psi = \psi ^ { \prime }$ ，且 $\eta _ { i } = u ^ { H ( n a m e \| i ) }$ $\scriptstyle \eta = \prod { \eta _ { i } }$

所以敌手可以计算 $e ( g ^ { x } , g ^ { r } ) = { \frac { e ( \sigma ^ { \prime } , g ) } { e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) } }$

而 $\mathbf { \Psi } _ { x , r }$ 对于敌手是保密的，所以敌手可以解决CBDH问题。

下面分析第二种情形：

若 $\sigma = \sigma ^ { \prime } , \psi \neq \psi ^ { \prime }$

则

$$
{ \boldsymbol { e } } ( \psi ^ { \prime } , g ) = e ( \psi , g )
$$

即

$$
e ( \psi ^ { \prime r } , g ^ { s } ) = e ( \psi ^ { r } , g ^ { s } ) = e ( ( \prod u _ { j } ^ { ~ \mu _ { j } } ) ^ { r } , g ^ { s } )
$$

所以，敌手可以计算 $e ( ( \prod u _ { j } ^ { ~ \mu _ { j } } ) ^ { r } , g ^ { s } ) = e ( \psi ^ { \prime r } , g ^ { s } )$ （204号

而 $s , r$ 对于敌手是保密的，所以敌手可以解决CBDH问题。

下面分析第三种情形：

若 $\sigma \neq \sigma ^ { \prime } , \psi \neq \psi ^ { \prime }$

则

$$
\frac { e ( \sigma , g ) } { e ( \sigma ^ { \prime } , g ) } = \frac { e ( { \psi ^ { \prime } , g ^ { s } } ) } { e ( { \psi ^ { \prime \prime } , g ^ { s } } ) }
$$

$$
e ( \sigma ^ { \prime } , g ) = { \frac { e ( \psi ^ { \prime \prime } , g ^ { s } ) e ( \sigma , g ) } { e ( \psi ^ { \prime } , g ^ { s } ) } } =
$$

即

$$
\frac { e ( \psi ^ { \prime r } , g ^ { s } ) e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { r } , g ^ { s } ) e ( X , g ^ { r } ) } { e ( \psi ^ { r } , g ^ { s } ) } =
$$

$$
e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { \prime r } , g ^ { s } ) e ( X , g _ { 1 } ^ { ~ r } )
$$

由于 $\eta _ { i } = u ^ { H ( n a m e | i ) }$ $\scriptstyle \eta = \prod { \eta _ { i } }$

所以，敌手可以计算： $e ( g ^ { x } , { g _ { 1 } } ^ { r } ) = \frac { e ( \sigma ^ { \prime } , g ) } { e ( \eta ^ { r } , g ^ { s } ) e ( \psi ^ { \prime r } , g ^ { s } ) }$

而 $x , r$ 对于敌手是保密的，所以敌手可以解决CBDH问题。

# 5 结束语

本文首次将基于属性的签名思想用在数据可恢复性证明中，提出了基于属性的可公开验证的数据可恢复性证明方案的的定义和安全模型，实现了基于属性的可公开验证的数据可恢复性证明方案的构造,给出了方案的正确性和安全性证明。

# 参考文献：

[1]Juels A,Jr Kaliski B S.PORs:proofs of retrievability for large files [C]//Procofthe 14thACM ConferenceonComputerand Communications Security.New York:ACM Press,2007:584-597.   
[2]Xu,Jia,Chang E C. Towards efficient provable data possession [J]. IACR Cryptology ePrint Archive,2011,2011:574.   
[3]Yuan，Jiawei，Yu Shucheng．Proofs of retrievability with public verifiability and constant communication cost in cloud [C]// Proc of International Workshop on Security in Cloud Computing.2013:19-26.   
[4]Zhu,Yan,Wang Huaixi,Hu Zexing,et al.Zero-knowledge proofs of retrievability [J]. Science China Information Sciences,2O11,54(8): 1608-1617.   
[5]Shi E,Stefanov E,Papamanthou C.Practical dynamic proofs of retrievability[C]//ProcofACM Conferenceon Computerand Communications Security.New York:ACMPress,2013:325-336.   
[6]Beng T C,Hijazi M H A,Lim Y，et al.A survey on Proof of Retrievability for cloud data integrity and availability:cloud storage state-of-the-art,issues,solutions and future trends[J].Journal of Network and Computer Applications,2018,110(2018):75-86.   
[7]Ren Zhengwei，Wang Lina,Wang Qian,et al.Dynamic proofs of retrievability for coded cloud storage systems[J]. IEEE Trans on Services Computing,2018,11(4),685-698.   
[8]Fu Anmin,Li Yuhan,Yu Shui,et al.DIPOR:an IDA-based dynamic proof of retrievability scheme for cloud storage systems [J]. Journal of Network and Computer Applications,2018,104: 97-106.   
[9]Sengupta B,Ruj S.Eficient proofs of retrievability with public verifiability for dynamic cloud storage [J]. IEEE Trans on Cloud Computing,2017.   
[10] Cash D,Kupcü A,Wichs D.Dynamic proofs of retrievability via obliviousRAM[J]. Journal of Cryptology,2017,30(1): 22-57.   
[11] Juels A,Kaliski Jr B S.PORs:Proofs of retrievability for large files [C]//Procof the14th ACM Conferenceon Computerand Communications Security.ACM,2007: 584-597.   
[12] Shacham H, Waters B.Compact proofs of retrievability[C]//Advances in Cryptology-Asiacrypt. Berlin:Springer,20o8:90-107.