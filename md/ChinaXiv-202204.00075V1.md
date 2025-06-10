# 格上基于身份的可问责代理重加密方案\*

孟慧，任利娜，李英(河南理工大学 计算机科学与技术学院，河南 焦作 454003)

摘要：针对目前基于格的代理重加密方案中存在密钥滥用和数字证书管理等问题，引入问责机制，提出一种新的基于身份的可问责代理重加密方案。该方案采用用户身份ID计算生成矩阵作为公钥，并使用原像采样算法提取私钥，解决了数字证书管理的问题；使用双方用户公钥计算生成重密钥，提高了加解密时的计算效率；使用代理商公私钥参与重加密运算，完成问责算法，有效地抑制了代理商和被授权者共谋的行为。安全性分析表明方案满足选择明文攻击安全；在效率方面，方案的计算复杂度和密文开销较小。

关键词：代理重加密；格密码；带错误学习问题；可问责性 中图分类号：TP309 doi: 10.19734/j.issn.1001-3695.2021.12.0693

Identity-based accountable proxy re-encryption scheme from lattice

Meng Huit, Ren Lina, Li Ying (School of Computer Science & Technology,Henan Polytechnic University,Jiaozuo Henan 454o03,China)

Abstract: Aiming at the problems of key abuse and digitalcertificate management in thecurrent lattce-based proxyreencryption scheme,this paper proposed a new identity based accountable proxy re encryption scheme by introducing the acountability algorithm.This schemeused theuser ID to calculate matrix asthe public key andused the pre-image sampling algorithm toextract theprivate key,whichsolvedthe problemofdigitalcertificate management;used thepublic keys ofboth users tocalculate and generate there-encryption key，which improved thecomputational eficiencyof encryption and decryption;used the proxy'spublicand private keys to participate in the re-encryption calculation,completed the accountabilityalgorithm,and inhibitedthecollsionof the proxyand thedelegate.The securityanalysis shows that the scheme atisfies thechosen-plaintext attck security.In terms of eficiency,the schemehas less computationalcomplexity and ciphertext overhead.

Keywords:proxy re-encryption; lattice; learning with error; accountability

# 0 引言

目前，云存储和云端数据共享在网络数据存储与计算中占据核心地位，用户将大量的数据存储在网络云盘中，减轻自己存储设备的负担，同时，更利于用户之间共享数据。在复杂的网络环境中，用户为了保护数据隐私需要将数据加密后再上传至云服务器存储或共享，但是，数据发送者需要实时查看是否有用户访问数据，并将要访问的数据下载后转发给数据接收方。代理重加密解决了传统云计算环境中数据拥有者需要实时在线的问题，减轻了用户频繁访问云端密文数据的负担，增强了数据的可靠性和机密性。1998年，Blaze 等人[1]首次提出了代理重加密(Proxy Re-encryption，PRE)的概念，在公钥加密系统中加入代理商的角色，并由代理商使用重密钥完成密文转换。2007年，Green等人[2]第一次提出了基于身份的代理重加密(IB-PRE)方案，方案中，公钥直接使用用户身份ID，公钥基础设施中的证书管理问题得到解决，该方案满足多跳性和非交互性。然而，随着量子计算机的发展，传统数论难题的安全性受到威胁。2010年，Xagawa等人[3]首次提出了格上的代理重加密方案，该方案不仅可以能够抵抗量子攻击还降低了计算复杂度。2014年，Singh等人[4]将身份基和代理重加密融合，提出了一个可以加密多比特信息的PRE方案，提高了运算效率。而且所提方案满足匿名性、多跳性。2021年，汤永利等人[5]利用RLWE(RingLearning

WithErrors)难题构造了一个PRE方案，有效缩短了密文、密钥尺寸，提高了加解密的效率。但是，以上几种方案都具有双向性，不能抵抗合谋攻击，且存在密钥泄漏等安全问题。2016年， $\mathrm { K i m ^ { [ 6 ] } }$ 等人提出了第一个基于最坏情况的格上难题且满足单向性的代理重加密方案，方案中的被授权者无法感知代理商的存在，即使用重密钥加密的密文和使用被授权方公钥加密的密文是不能被区分的。2020年，wang[7等人指出了Kim方案中重加密密文无法解密或解密错误率高的问题，提出了一个新的满足单向性的代理重加密方案，经证明方案满足选择明文攻击(Chosen-plaintextAttack，CPA)安全。2021年，Dutta等人[8提出第一个针对选择性和自适应身份的抗合谋单向IB-PRE的具体构造，所提结构具有非交互性和非传递性，不满足多跳性。

2013年，Wang等人[9]提出了一个新的原语 $\mathrm { P R E ^ { + } }$ ，与传统PRE的不同点在于解密权的委托者不同。传统PRE解密权限的委托者是密文接收方，而PRE+解密权限的委托者是密文发送者，即加密者将解密权委托给被授权者。且重密钥生成算法中的输入元素不同，传统PRE由密文接收方的私钥与被授权者的私钥或公钥生成重密钥，而PRE+是由两者的公钥生成重密钥。2020年，Singh等人[10]提出了单向的PRE和PRE+方案， $\mathrm { P R E ^ { + } }$ 能够提高加解密时的计算效率，适用于细粒度授权和不可转让授权，在安全云计算和组播等方面应用广泛。被授权者和代理商的合谋攻击虽然不会暴露授权者的长期密钥，但是，他们可能合谋并为不受委托方信任的恶意用户提供新的重密钥。另外，由于代理重加密的固有功能可能会使PRE方案存在重密钥滥用问题，即代理商和被授权者合谋获得授权者的解密能力，并将其保存在任何载体上，如解密设备。为了缓解这个问题，2005年，Ateniese等人[11]提出不可转让的概念，当Bob和代理商合谋分发Alice的解密能力时，Bob必须公开他自己的解密能力作为代价。2019年，Guo等人[12]使用不可区分性混淆和K-不可伪造认证构造了不可转让的代理重加密方案。不可转让性对恶意用户有一定的威慑作用，但是，当Bob的密钥远没有数据拥有者的密钥有价值时，Bob可能会为了更大的利益而公开自己的解密能力。此时代理商可以从中分发Alice的解密能力，却不用付出任何代价，甚至否认自己的恶意行为。2021年，Guo等人[13]为了解决上述问题提出了可问责的代理重加密(Accountable Proxy Re-encryption，APRE)方案，并引入一个判断算法来判断代理商是否不承认自己分发授权者解密能力的行为。可问责代理重加密模型如图1所示。

![](images/6465ca52ff5ee96497808e6989ed09ea23d85307eb6c85c41810797679231d2e.jpg)  
图1可问责代理重加密模型  
Fig.1Accountable proxy re-encryption model

为了解决公钥加密中的数字证书管理和密钥滥用等问题基于文献[13]中的问责算法构造一个新的格上基于身份的可问责代理重加密方案。利用用户身份ID计算生成一个矩阵作为公钥，取代传统公钥加密体制中将用户身份和公钥联系起来的数字证书，使用原像采样算法提取私钥，并且令代理商公私钥参与重密钥和重加密的计算，最后，使用一个公开的审判算法判断恶意代理是否在否认自己分发授权者解密能力的行为。与文献[13]不同的是，本文方案基于带错误学习(LearningwithError，LWE)困难假设，使用用户身份作为公钥并使用授权者公钥参与重密钥的运算。安全分析表明，方案在标准模型下达到适应性选择身份的选择明文攻击安全下的不可区分性(IND-aID-CPA)。效率分析则说明方案在存储空间、性能和复杂度上的优势。

# 1 预备知识

# 1.1格

设 $\pmb { { \cal B } } = \{ b _ { I } , b _ { 2 } , . . . , b _ { n } \}$ 是由 $\mathbb { R } ^ { m }$ 中 $\mathfrak { n }$ 个向量组成的矩阵，且这些向量是线性无关的，则这 $\mathfrak { n }$ 个向量的所有整系数的线性组合所构成的集合为一个 $\mathrm { ~ m ~ }$ 维格 $\Lambda$ ，即：

$$
\Lambda = \mathcal { L } ( B ) = \{ \pmb { y } \in \mathbb { R } ^ { m } , s . t . \exists s \in \mathbb { Z } ^ { n } , \pmb { y } = B s = \sum _ { i = 1 } ^ { n } s _ { i } \pmb { b } _ { i } \}
$$

其中： ${ \pmb { b } } _ { I } , { \pmb { b } } _ { 2 } , . . . , { \pmb { b } } _ { n }$ 是格 $\Lambda$ 的一组基，当 $m = n$ 时，称格 $\Lambda$ 是满秩格。

定义1设 $\mathsf { q }$ 为素数，矩阵 $\pmb { A } \in \mathbb { Z } _ { q } ^ { n \times m }$ ，定义两个 $\mathbf { m }$ 维满秩整数格：

$$
\Lambda _ { q } ^ { \perp } ( A ) = \{ e \in \mathbb { Z } ^ { m } , s . t . A e = \pmb { \theta } ( \mathrm { m o d } q ) \}
$$

$$
\Lambda _ { q } ( A ) = \{ \pmb { y } \in \mathbb { Z } ^ { m } , s . t . \exists \pmb { s } \in \mathbb { Z } _ { q } ^ { n } , A ^ { T } \pmb { s } = \pmb { y } ( \mathrm { m o d } q ) \}
$$

格上的陷门函数在格密码学中有着广泛的应用，陷门基是格的一个短基，方案中使用陷门生成算法产生的陷门基作为主私钥。

引理1[14][ 陷门生成算法：整数 $q \geq 3$ ， $m { = } \lceil 6 n \log q \rceil$ 。存在一个概率多项式时间(Probabilistic Polynomial-time,PPT)算法 $\operatorname { T r a p G e n } ( q , n )$ 生成矩阵 $\pmb { A } \in \mathbb { Z } _ { q } ^ { n \times m }$ 和 $\Lambda _ { q } ^ { \perp } ( A )$ 的一组基 $\pmb { T } \in \mathbb { Z } _ { q } ^ { m \times m }$ ，其中 $A$ 在 $\mathbb { Z } _ { q } ^ { n \times m }$ 上的分布与均匀分布是不可区分的，且i $\| \leq \mathrm { O } ( { \sqrt { n \log q } } )$ 和 $\left\| \pmb { T } \right\| \le \mathrm { O } ( n \log q )$ 以绝对的优势成立。

# 1.2 离散高斯分布

高斯分布常用于格上困难问题的研究，本节将对离散高斯分布和其相关引理作出详细介绍。

对于 $\forall s \in \mathbb { R } _ { + }$ ， $c \in \mathbb { R } ^ { m }$ ，定义 $\mathbf { m }$ 维格 $\Lambda$ 上的离散高斯分布：

$$
D _ { \Lambda , s , c } ( \pmb { x } ) = \frac { \rho _ { s , c } ( \pmb { x } ) } { \rho _ { s , c } ( \pmb { \Lambda } ) } = \frac { \rho _ { s , c } ( \pmb { x } ) } { \sum _ { \pmb { x } \in \Lambda } \rho _ { s , c } ( \pmb { x } ) }
$$

文献[14]中介绍了原像采样算法，其中包含的SamplePre算法负责使用陷门基 $\pmb { T } _ { A }$ 求解给定像值 $\pmb { u }$ 对应的原像值 $\mathbf { \sigma } _ { \mathbf { { x } } }$ 0

引理2[14]SamplePre $( A , T _ { A } , \sigma , { \pmb u } )$ 已知格 $\Lambda _ { q } ^ { \perp } ( A )$ 上的一个陷门基 $\pmb { T } _ { A }$ ，实数 $\sigma \ge \left\| \tilde { T } _ { A } \right\| \omega ( \sqrt { \log n } )$ ，对于任意向量 $\pmb { u } \in \mathbb { Z } _ { q } ^ { n }$ ，存在一个PPT算法SamplePre $( A , T _ { A } , \sigma , u )$ ，在统计量接近 $D _ { \Lambda _ { q } ^ { s } ( A ) , \sigma , c } ( { \pmb x } )$ 的分布中抽取一个向量 $\pmb { x } \in \Lambda _ { q } ^ { u } ( A )$ ，满足 $A x = \pmb { u } ( \mathrm { m o d } q )$ 。

引理 $3 ^ { [ 1 5 ] }$ 设正整数 $n \ , \ q$ ，其中 $\boldsymbol { q }$ 为素数， $m \geq 2 n \log _ { 2 } { q }$ 。那么对于 $A \in \mathbb { Z } _ { q } ^ { n \times m }$ ， $\sigma \geq \omega ( \sqrt { \log _ { 2 } m } )$ ， $e \gets D _ { \mathbb { Z } ^ { m } , \sigma }$ ， $\pmb { u } = \pmb { A } e \bmod q$ 的分布与 $\mathbb { Z } _ { q } ^ { n }$ 上的均匀分布的统计量相近。

# 1.3格上困难问题

定义2[16]小整数解问题 SIS。给定素数 $q > 0$ ，随机选择矩阵 $\pmb { { B } } \in \mathbb { Z } _ { q } ^ { n \times m }$ ，找到一个非零向量 $\pmb { u } \in \mathbb { Z } _ { q } ^ { m }$ ，使 $B u = \pmb { \theta } { \bmod { q } }$ ，并且满足 $\left\| \pmb { u } \right\| \leq \delta$ ，其中，常数 ${ \delta > } 0$ 。

文献[17]给出从最坏情况困难到SIS的归约，证明SIS问题在某些参数下是足够困难的。

定理 $1 ^ { [ 1 7 ] }$ 设整数 $n \geq 1$ ， $m = p o l y ( n )$ 和实数 $\beta \ge \beta _ { \infty } \ge 1$ ，令$\pmb { Z } ^ { \ast } = \{ \tau \in \mathbb { Z } ^ { m } : \| \boldsymbol { z } \| _ { 2 } \leq \beta , \| \boldsymbol { z } \| _ { \infty } \leq \beta _ { \infty } \}$ 并且 $q \geq \beta n ^ { \delta }$ ，常数 ${ \delta > } 0$ 。则求解解集为 ${ \pmb Z } ^ { * } \backslash \{ 0 \}$ 的 $S I S _ { m , n , q , \delta }$ 问题至少与在 $\mathfrak { n }$ 维格上将最坏情况下的格问题逼近到 $\operatorname* { m a x } \{ 1 , \beta \cdot \beta _ { \infty } / q \} \cdot \tilde { \mathrm { O } } ( \beta \sqrt { n } )$ 一样困难。

定义 $3 ^ { [ 1 8 ] }$ 带错误学习问题LWE。给定正整数 $\mathfrak { n }$ 和q,选择均匀随机的矩阵 $\pmb { A } \in \mathbb { Z } _ { q } ^ { n \times m }$ 和向量 $\pmb { S } \in \mathbb { Z } _ { q } ^ { n }$ ，向量 $e \gets \chi ^ { m }$ 服从错误分布。LWE困难问题就是给定 $( A , A ^ { r } s + e )$ ，以不可忽略的概率寻找s。

定义4[4] $\mathrm { L W E } _ { q , \chi }$ 判定问题DLWE。设正整数 $\mathfrak { n }$ ， $\mathrm { ~ m ~ }$ 以及素数q， $\chi ^ { \mathrm { m } }$ 是 $\mathbb { Z } _ { q }$ 上的高斯分布。LWE的判定性问题是指通过随机给出一系列来自分布 $\mathbf { A } _ { s , \chi }$ 的独立抽样或者来自 $\mathbb { Z } _ { q } ^ { n } \times \mathbb { Z } _ { q }$ 的均匀随机抽样，判断抽样是否来自分布 $\mathbf { A } _ { s , \chi }$ 的问题。

文献[18]中给出了LWE和DLWE的关系以及从最短向量问题(SVP)到LWE的归约，证明LWE对于某些参数是足够困难的。

定理 $2 ^ { [ 1 8 ] }$ $n , q$ 为正整数，实数 $\alpha \in ( 0 , 1 )$ ，满足 $\alpha q > { \sqrt { 2 n } }$ □若LWE问题能被一个有效的算法解决，那么近似决策性最短向量问题(Gap-SVP)和最短独立向量问题(SIVP)的最坏情况问题也能够被一个量子算法以 ${ \tilde { \mathrm { O } } } ( n / \alpha )$ 的时间复杂度解决。

# 2 可问责代理重加密定义及安全模型

# 2.1可问责代理重加密的定义

下面是对身份基可问责代理重加密定义的介绍，安全参数为。

(1)初始化Setup()：输入安全参数λ，输出公共参数  
params 和主私钥msk ;(2)私钥提取 $\mathrm { E x t r a c t } ( p a r a m s , m s k , i d )$ ：输入params，msk 和用  
户 $i d$ ，输出用户私钥 $\mathit { S K }$ ：(3)加密 $\mathrm { E n c } ( p a r a m s , i d _ { i } , m )$ ：输入 $i d _ { i }$ 和明文 $m$ ，输出二级密  
文 $C _ { i }$ ：(4)重密钥生成 $\mathrm { R e K e y G e n } ( p a r a m s , i d _ { i } , i d _ { j } , i d _ { p } )$ ：以公共参数  
params 和双方用户及代理商的身份 $i d$ 作为输入，输出重密钥 $r k _ { i  j }$ ：

(5)重加密 $\mathrm { R e E n c } ( p a r a m s , r k _ { i  j } , S K _ { p } , C _ { i } )$ ：输入 $r k _ { i  j }$ ，代理商私 钥 $S K _ { p }$ 和 $C _ { i }$ ，输出一级密文 $C _ { j }$ ：

(6)二级密文解密 $\mathrm { D e c } _ { 2 } ( p a r a m s , S K _ { i } , C _ { i } )$ ：输入 ${ \cal { S } } K _ { i }$ 和二级密 文 $C _ { i }$ ，算法解密恢复出明文 $\mid m$

(7)一级密文解密 $\mathrm { D e c } _ { 1 } ( p a r a m s , S K _ { j } , C _ { j } )$ ：输入 ${ \cal S } K _ { j }$ 和一级密文 $C _ { j }$ ，输出明文 $\mathbf { \nabla } _ { m }$

(8)问责算法 $\mathrm { J u d g e } ^ { D _ { i , \mu } } ( p a r a m s , i d _ { i } , i d _ { p } )$ ：通过黑盒访问解密设备 $D _ { i , \mu }$ ， $i d _ { i }$ 和 $i d _ { p }$ 作为输入，该算法输出Proxy 或Delegator,输出结果即为恶意解密设备的生成者。

正确性：方案满足以下两个条件，即可正确恢复明文。

$$
\mathrm { D e c } _ { 2 } ( p a r a m s , S K _ { i } , \mathrm { E n c } ( p a r a m s , i d _ { i } , m ) ) = m
$$

$$
\mathrm { D e c } _ { 1 } ( p a r a m s , S K _ { j } , \mathrm { R e E n c } ( p a r a m s , r k _ { i  j } , S K _ { P } , \mathrm { E n c } ( p a r a m s , ~ i d _ { i } , m ) ) ) = m
$$

# 2.2可问责代理重加密的安全模型

# 2.2.1 CPA安全

本小节将介绍基于IND-aID-CPA 游戏的可问责代理重加密安全模型[19]，设安全参数为 $\lambda$ ，游戏是由敌手 $\mathcal { A }$ 和下列预言机组成，过程如下：

初始化阶段：挑战者 $\mathcal { C }$ 将Setup()输出的公共参数params发送给敌手 $\mathcal { A }$ 。

阶段1：敌手 $\mathcal { A }$ 发出问询，挑战者 $\mathcal { C }$ 作出回答：

私钥生成预言机 $O _ { s \kappa }$ ：使用Extract(params,msk,idi)生成用户私钥 $S K _ { i }$ 并存储，当敌手 $\mathcal { A }$ 输入 $i d _ { i }$ 时，若用户i为恶意用户，则挑战者 $\mathcal { C }$ 发送 ${ \cal { S } } K _ { i }$ 给敌手 $\mathcal { A }$ 。否则，发送 $\perp$ ·

重密钥生成预言机 $O _ { r k }$ ：敌手 $\mathcal { A }$ 输入 $( i d _ { i } , i d _ { j } , i d _ { p } )$ ，得到ReKeyGen 生成的重密钥 $r k _ { i  j }$ ：

重加密预言机 $O _ { r e }$ ：如果用户 $\mathrm { j }$ 是不诚实的，则敌手 $\mathcal { A }$ 输入 $( r k _ { i  j } , S K _ { p } , C _ { i } )$ ，并输出 $\perp$ ；否则，输出重加密后的密文$C _ { j } = \mathrm { R e E n c } ( \mathrm { R e K e y G e n } ( i d _ { i } , i d _ { j } , i d _ { p } ) , S K _ { p } , C _ { i } )$

挑战预言机 $o _ { c }$ ：敌手 $\mathcal { A }$ 输入一个目标用户和两个消息$m _ { 0 } , m _ { 1 }$ 。预言机随机选择 $b \in \{ 0 , 1 \}$ ，返回挑战者密文$C ^ { * } = \mathrm { E n c } ( i d ^ { * } , m _ { b } )$ 0

猜测：输入 $b ^ { \prime } \in \{ 0 , 1 \}$ ，如果 $b ^ { \prime } = b$ ，则挑战者 $\mathcal { C }$ 输出1，否则输出0。

定义5IND-CPA 安全。定义敌手 $\mathcal { A }$ 的优势为

$$
\mathrm { A D V } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { I N D - C P A } } ( n ) = \big | \operatorname* { P r } [ \mathrm { E x p } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { I N D - C P A } } ( n ) = 1 ] - \frac { 1 } { 2 } \big |
$$

当 $\mathbf { A D V } _ { \mathrm { P R E } , \mathrm { A } } ^ { \mathrm { I N D - C P A } } \left( n \right)$ 是可忽略的,称方案是IND-CPA安全的。

# 2.2.2恶意代理安全

若敌手输出的解密设备使审判者相信诚实的授权者有罪，则敌手赢得游戏。实验过程如下[13]:

Experiment $\mathrm { E x p } _ { \mathrm { P R E } \ J , A } ^ { \mathrm { m p } } ( n )$ （204 params←Setup(λ) $S K _ { p } \gets \mathrm { E x t r a c t } ( p a r a m s , i d _ { p } )$ $D _ { i , \mu }  A ^ { o _ { s \kappa } , o _ { r \hslash } } ( p a r a m s , i d _ { p } , S K _ { p } )$

Where $\mu$ is a non-negligible probability value; If $\mathbf { J u d g e } ^ { \mathrm { { D } } _ { i , \mu } } ( i d ^ { * } , i d _ { p } ) =$ Delegator

Return 1;   
else return 0.

定义6恶意代理安全。敌手的优势被定义为$\mathrm { A D V } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { m p } } ( n ) \mathop { = } \big | \operatorname* { P r } [ \mathrm { E x p } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { m p } } ( n ) = 1 ] \big |$

当所有PPT敌手 $\mathcal { A }$ 的优势 $\mathrm { A D V } _ { \mathrm { P R E } , A } ^ { \mathrm { m p } } ( n )$ 是可忽略的，方案满足恶意代理安全。

# 2.2.3恶意授权者安全

根据下面实验，当解密设备 $D _ { i , \mu }$ 使审判者相信诚实的代理商有罪，则敌手赢得游戏。

Experiment ExprRE.A (n) $\begin{array} { l } { p a r a m s \gets \mathrm { S e t u p } ( \lambda ) } \\ { S K _ { p } \gets \mathrm { E x t r a c t } ( p a r a m s , i d _ { p } ) } \end{array}$

$$
D _ { i , \mu }  A ^ { o _ { S K } , o _ { i } } ( p a r a m s , i d _ { P } )
$$

Where $\mu$ isanon-negligible probability value;

If Ju $\mathbf { \mathrm { l g e } } ^ { \mathbf { D } _ { i , \mu } } ( i d ^ { * } , i d _ { p } ) = \mathbf { \mathrm { P r } }$ oxy

Return 1;   
else return 0.

定义7恶意授权者安全。敌手 $\mathcal { A }$ 的优势被定义为

$$
\mathrm { A D V } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { m d } } \left( n \right) = \big | \operatorname* { P r } [ \mathrm { E x p } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { m d } } \left( n \right) = 1 ] \big |
$$

当所有PPT敌手 $\mathcal { A }$ 的优势 $\mathrm { A D V } _ { \mathrm { P R E } , A } ^ { \mathrm { m d } } \left( n \right)$ 是可忽略的，称方案是恶意授权者安全的。

如果PRE方案同时满足恶意代理安全和恶意授权者安全，则称这个方案满足可问责性。

# 3 代理重加密方案

# 3.1方案构造

本文基于问责算法与LWE困难问题，结合代理重加密与基于身份的加密体制，提出格上基于身份的可问责代理重加密方案，方案具体构造如下：

(1)初始化 Setup()： $\lambda$ 为安全参数，随机矩阵 $A \in \mathbb { Z } _ { q } ^ { n \times m }$ 和陷门基矩阵 $\pmb { T } \in \mathbb { Z } _ { q } ^ { m \times m }$ 由陷门生成算法TrapGen(q,n）生成，$\leq  { \operatorname { O } ( { \sqrt { n \log q } } ) }$ ，陷门函数 $f _ { A } ( \pmb { x } ) = A \pmb { x } \bmod q ( f : \mathbb { Z } ^ { m } \to \mathbb { Z } _ { q } ^ { n } )$ 。随机选择$\mathrm { m } { + } 1$ 个矩阵 $U _ { o } , U _ { I } , . . . , U _ { m } \in \mathbb { Z } _ { q } ^ { n \times m }$ ，且线性无关，则主密钥为$m p k = ( A , U _ { o } , U _ { I } , . . . , U _ { m } )$ ，主私钥 $m s k = T$ ，公共参数par $a m s = ( m , n , q , m p k )$ 。

(2)私钥提取 $\mathrm { E x t r a c t } ( p a r a m s , m s k , i d )$ ：输入公共参数params,主私钥msk和用户/代理身份 $i d = \{ i d _ { 1 } , i d _ { 2 } , . . . , i d _ { m } \} \in$ {0,1}，计算$\begin{array} { r } { U = U _ { \theta } + \sum _ { i = 1 } ^ { m } i d _ { i } U _ { i } = ( u _ { I } , u _ { 2 } , . . . , u _ { m } ) } \end{array}$ ，使用原像采样算法产生一个向量$\pmb { x } _ { i } \in \mathbb { Z } _ { q } ^ { m }$ ，使其满足 $\pmb { u _ { i } } = \pmb { A } \pmb { x _ { i } } \bmod { q } \ , \ \lVert \pmb { x _ { i } } \rVert \leq \sigma \sqrt { m }$ 。令 $X = ( { \boldsymbol { x } _ { I } } , { \boldsymbol { x } _ { 2 } } , . . . , { \boldsymbol { x } _ { m } } )$ ，则 $A X = U \bmod q$ ，用户/代理私钥 $S K = X$ 。

(3)加密 $\mathrm { E n c } ( p a r a m s , i d _ { i } , m )$ ：输入用户i的身份 $i d _ { i }$ 和明文（204号 $m \in \{ 0 , 1 \} ^ { m }$ ，随机选择向量 $\pmb { S } \in \mathbb { Z } _ { q } ^ { n }$ ， $e \gets \chi ^ { m }$ ；计算 $C _ { 1 } = U _ { i } ^ { T } s + m  { \left\lfloor \frac { q } { 2 } \right\rfloor } + e$ $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，输出二级密文 $C _ { i } = ( C _ { 1 } , \mathbf { y } )$ 。

(4)重密钥生成 $\mathrm { R e K e y G e n } ( m p k , s , i d _ { i } , i d _ { j } , i d _ { p } )$ ：输入随机向量 $s$ ，用户身份 $i d _ { i }$ ， $i d _ { j }$ 和代理商身份 $i d _ { p }$ ，选择 $e _ { I } \gets \chi ^ { m }$ ，由用户 $\mathrm { ~ i ~ }$ 计算重密钥 $r k _ { i  j } = ( U _ { j } ^ { T } - U _ { i } ^ { T } + U _ { p } ^ { T } ) s + e _ { I }$ 。

(5)重加密 $\mathrm { R e E n c } ( p a r a m s , r k _ { i  j } , S K _ { p } , C _ { i } )$ ：输入重密钥 $r k _ { i  j }$ ，代 理商私钥 $S K _ { p }$ 和二级密文 $C _ { i }$ ，选择 $e _ { 2 } \gets \chi ^ { { \scriptscriptstyle m } }$ ，计算 $C _ { 1 } ^ { ' } = C _ { 1 } + r k _ { i  j } - S K _ { p } ^ { T } { \bf y } + { \pmb e } _ { 2 }$ ，输出一级密文 $C _ { j } = ( C _ { 1 } ^ { ' } , { \bf { y } } )$ 。

(6)二级密文解密 $\mathrm { D e c } _ { 2 } ( p a r a m s , S K _ { i } , C _ { i } )$ ：输入 ${ \cal { S } } K _ { i }$ 和二级密文 $C _ { i }$ ，计算 $m { = } C _ { 1 } { - } S K _ { i } ^ { T } y ( \mathrm { m o d } q )$ ；令 $m = ( m _ { 1 } , m _ { 2 } , . . . , m _ { m } )$ ，如果 $m _ { i }$ 与$\left\lfloor { \frac { q } { 2 } } \right\rfloor$ 相比更接近0，则 $m _ { i } = 0$ ；否则， $m _ { i } = 1$ ；输出 $\boldsymbol { m } = ( m _ { 1 } , m _ { 2 } , . . . , m _ { m } )$ u

(7)一级解密 $\mathrm { D e c } _ { 1 } ( p a r a m s , S K _ { j } , C _ { j } )$ ：输入 $S K _ { j }$ 和一级密文 $C _ { j }$ ，计算 $m = C _ { 1 } ^ { \cdot } - S K _ { j } ^ { \tau } y ( \mathrm { m o d } q )$ ；令 $\boldsymbol { m } = ( m _ { 1 } , m _ { 2 } , . . . , m _ { m } )$ ，如果 $m _ { i }$ 与 $\left\lfloor { \frac { q } { 2 } } \right\rfloor$ 相比更接近0，则 $m _ { i } = 0$ ；否则， $m _ { i } = 1$ ；输出 $\boldsymbol { m } = ( m _ { 1 } , m _ { 2 } , . . . , m _ { { m } } )$ 。

(8)问责算法 $\mathrm { J u d g e } ^ { D _ { i , \mu } } ( p a r a m s , i d _ { i } , i d _ { p } )$ ：提供一个解密设备 $D _ { i , \mu }$ 作为预言机：

1)重复下面的实验 $n = \lambda / \mu$ 次。选择均匀随机向量 $s \in \mathbb { Z } _ { q } ^ { n }$ 和明文 $\mathrm { ~ m ~ }$ ，并且计算 $C _ { 1 } = ( U _ { i } ^ { T } + U _ { p } ^ { T } ) s + m \Bigg \lfloor \frac { q } { 2 } \Bigg \rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，密文$\ b { C } = ( \ b { C } _ { 1 } , \ b { y } )$ ；运行解密设备 $D _ { i , \mu }$ ,并将C作为 $D _ { i , \mu }$ 的输入,输出 $m ^ { \prime }$ ：

2)如果 $m ^ { \prime } = m$ ，输出"Proxy"并退出；否则输出"Delegator”。3.2正确性

(1）二级密文解密 $\mathrm { D e c } _ { 2 } ( p a r a m s , S K _ { i } , C _ { i } )$

$$
\begin{array} { l } { m = C _ { 1 } - S K _ { i } ^ { T } { \mathbf { y } } ( \mathrm { m o d } q ) } \\ { \quad = { \mathbf { } } U _ { i } ^ { T } s + m \left\lfloor \displaystyle \frac { q } { 2 } \right\rfloor + e - X _ { i } ^ { T } ( A ^ { T } s + e ) ( \mathrm { m o d } q ) } \end{array}
$$

$$
\begin{array} { r l } & { \mathbf { \tau } = U _ { i } ^ { T } s + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor + e - U _ { i } ^ { T } s - X _ { i } ^ { T } e ( \mathrm { m o d } q ) } \\ & { \mathbf { \tau } = e - X _ { i } ^ { T } e + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor ( \mathrm { m o d } q ) } \end{array}
$$

因为 $\scriptstyle { e }$ 和 $S K _ { i } ^ { T }$ 是从高斯分布的集合 $\psi _ { s }$ 中选择的，所以在$s = \alpha _ { q }$ 时， $e - X _ { i } ^ { T } e$ 小于 $\left\lfloor { \frac { q } { 4 } } \right\rfloor$ ，成功恢复 $\mathrm { ~ m ~ }$ 。

(2)一级密文解密 $\mathrm { D e c } _ { 1 } ( p a r a m s , S K _ { j } , C _ { j } )$ （204号

$$
\begin{array} { l } { C _ { 1 } ^ { \prime } = C _ { 1 } + r k _ { i  j } - S K _ { { P } } ^ { T } { \bf { y } } + { \bf { e } } _ { 2 } } \\ { \quad = U _ { i } ^ { T } s + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor + e + ( U _ { j } ^ { T } - U _ { i } ^ { T } + U _ { { p } } ^ { T } ) s + e _ { I } - X _ { { p } } ^ { T } { \bf { y } } + { e _ { 2 } } } \\ { \quad = U _ { j } ^ { T } s + e + e _ { I } - X _ { { p } } ^ { T } e + e _ { 2 } + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor } \end{array}
$$

$$
\begin{array} { r l } & { m = C _ { 1 } ^ { \prime } - C _ { 2 } ^ { \prime } - S K _ { { j } } ^ { T } { \bf y } ( \bmod q ) } \\ & { \quad = { \bf U } _ { { j } } ^ { T } s + e + e _ { I } - X _ { { j } } ^ { T } e + e _ { 2 } + m \Biggl \lfloor \frac { q } { 2 } \Biggr \rfloor - X _ { { j } } ^ { T } ( A ^ { T } s + e ) ( \bmod q ) } \\ & { \quad = e + e _ { I } - X _ { { j } } ^ { T } e - X _ { { p } } ^ { T } e + e _ { 2 } + m \Biggl \lfloor \frac { q } { 2 } \Biggr \rfloor ( \bmod q ) } \end{array}
$$

因为 $e _  \mathrm { ~ \bf ~ \} } , e _ { I } \ , e _ { 2 } \ , S K _ { j } ^ { T }$ ， $S K _ { P } ^ { \textit { T } }$ 是从高斯分布的集合 $\psi _ { s }$ 中选择的，所以在 $s = \alpha _ { q }$ 时， $e + e _ { I } - X _ { j } ^ { T } e - X _ { p } ^ { T } e + e _ { 2 }$ 小于 $\left\lfloor { \frac { q } { 4 } } \right\rfloor$ ，成功恢复 $\mathrm { ~ m ~ }$ 。

# 3.3多跳性

代理者执行第一次重加密：

$$
C _ { 2 } = C _ { 1 } + r k _ { 1  2 } - S K _ { p } ^ { T } { \pmb y } + { \pmb e } _ { 2 }
$$

代理者执行第二次重加密：

$$
\begin{array} { c } { { C _ { 3 } = C _ { 2 } + r k _ { 2  3 } - S K _ { p } ^ { T } { \bf y } + { e _ { 2 } } } } \\ { { = C _ { 1 } + r k _ { 1  2 } + r k _ { 2  3 } - 2 S K _ { p } ^ { T } { \bf y } + 2 e _ { 2 } } } \end{array}
$$

代理者执行第N-1次重加密：

$$
\begin{array} { r l } {  { C _ { N } = C _ { N - 1 } + r K _ { N - 1 , \gamma N } - S K _ { p } ^ { T } y + e _ { 2 } } } \\ & { = C _ { N - 2 } + r K _ { N - 2 , \gamma N - 1 } + r K _ { N - 1 , \gamma N } - 2 S K _ { p } ^ { T } y + 2 e _ { 2 } = . . . } \\ & { = C _ { 1 } + \frac { N - 1 } { \sum _ { i = 1 } ^ { N } { k _ { i } } + \gamma _ { i } + 1 } - ( N - 1 ) S K _ { p } ^ { T } y + ( N - 1 ) e _ { 2 } } \\ & { = C _ { 1 } + \frac { N - 1 } { \sum _ { i = 1 } ^ { N } { ( U _ { i + i } ^ { T } - U _ { i } ^ { T } + U _ { p } ^ { T } ) ^ { S } } + e _ { i } } ) - ( N - 1 ) X _ { p } ^ { T } y + ( N - 1 ) e _ { 2 } } \\ & { = U _ { 1 } ^ { T } s + m \lfloor \frac { Q } { 2 } \rfloor + e + ( - U _ { 1 } ^ { T } + U _ { 1 } ^ { T } ) s + ( N - 1 ) e _ { i } - ( N - 1 ) X _ { p } ^ { T } e + ( N - 1 ) e _ { 2 } } \\ & { = m \lfloor \frac { Q } { 2 } \rfloor + e + U _ { 1 } ^ { T } s + ( N - 1 ) e _ { i } - ( N - 1 ) X _ { p } ^ { T } e + ( N - 1 ) e _ { 2 } } \end{array}
$$

完成N-1次重加密后，使用用户 $\mathrm { ~  ~ N ~ }$ 的私钥 $S K _ { N }$ 完成解密：

$$
\begin{array} { r l } & { m = C _ { N } - S K _ { N } ^ { T } y ( \bmod q ) } \\ & { \quad = m \left\lfloor \displaystyle \frac { q } { 2 } \right\rfloor + e + U _ { N } ^ { T } s + ( N - 1 ) e _ { I } - ( N - 1 ) X _ { p } ^ { T } e + ( N - 1 ) e _ { 2 } - } \\ & { \quad \quad \quad X _ { N } ^ { T } ( A ^ { T } s + e ) ( \bmod q ) } \\ & { \quad = m \left\lfloor \displaystyle \frac { q } { 2 } \right\rfloor + e + ( N - 1 ) e _ { I } - ( N - 1 ) X _ { p } ^ { T } e + ( N - 1 ) e _ { 2 } - X _ { N } ^ { T } e ( \bmod q ) } \end{array}
$$

当 $\pmb { e } + ( N - 1 ) \pmb { e } _ { I } - ( N - 1 ) X _ { p } ^ { T } \pmb { e } + ( N - 1 ) \pmb { e } _ { 2 } - X _ { N } ^ { T } \pmb { e }$ 小于 $\left\lfloor { \frac { q } { 4 } } \right\rfloor$ 时，成功恢复 $\mathrm { ~ m ~ }$ 。

# 4 安全性与效率分析

# 4.1 CPA 安全

定理4.1令 $\lambda$ 为安全参数，对于任意明文 $m \in \{ 0 , 1 \}$ ，若LWE问题在多项式时间是不可解的，则该方案满足IND-aID-CPA安全。即敌手 $\mathcal { A }$ 在多项式时间t内成功攻破方案的优势$\begin{array} { r } { \mathbf { A D V } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { I N D - C P A } } ( t ) \leq n e g l ( \lambda ) } \end{array}$ 。

证明：通过证明下列游戏的不可区分性来证明PPT 敌手 $\mathcal { A }$ 成功攻破方案的优势是可忽略的。

游戏1原始的IND-aID-CPA方案。在挑战阶段，当挑战者 $\mathcal { C }$ 收到 $( i ^ { * } , m _ { 0 } , m _ { 1 } )$ 后，挑选其中一个明文 $m _ { \mathrm { b } }$ ，计算挑战密文 $C ^ { * } = ( C _ { 1 } , { \bf y } )$ 给敌手 $\mathcal { A }$ ，其中 $C _ { 1 } = U _ { i } ^ { T } s + m _ { \mathrm { b } } \left\lfloor \frac { q } { 2 } \right\rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ 。最后，敌手 $\mathcal { A }$ 猜测 $\boldsymbol { b ^ { \prime } }$ ，若猜测成功，则 $\mathcal { C }$ 输出1，否则输出0。

游戏2在游戏2 中矩阵 $\pmb { A } \in \mathbb { Z } _ { q } ^ { n \times m }$ 与矩阵 $U _ { o } , U _ { I } , . . . , U _ { m } \in \mathbb { Z } _ { q } ^ { n \times m }$ 的生成方式与游戏1不同。在游戏2中，挑战者 $\mathcal { C }$ 模拟真实的方案，并回答敌手 $\mathcal { A }$ 的各种问询。首先挑战者模拟真实方案如下：

初始阶段：挑战者 $\mathcal { C }$ 选择一个随机矩阵 $\pmb { A } \in \mathbb { Z } _ { q } ^ { n \times m }$ ，根据以下步骤生成 $U _ { o } , U _ { I } , . . . , U _ { m } \in \mathbb { Z } _ { q } ^ { n \times m }$ ：

1)挑战者 $\mathcal { C }$ 随机选择服从高斯分布 $D _ { \sigma / ( m + 1 ) , 0 }$ 的 $\mathrm { m } { + } 1$ 个矩阵$X _ { 0 } , X _ { I } , . . . , X _ { m }$ ；

2)计算 $A X _ { k } = U _ { k } { \bmod { q } }$ ， $k = 0 , 1 , . . . , m$ ：

3)若生成的矩阵 $\boldsymbol { U } _ { k }$ 是线性相关的，则重新选择生成 $X _ { k }$ u

挑战者 $\mathcal { C }$ 将公共参数 $A \in \mathbb { Z } _ { q } ^ { n \times m }$ 和 $U _ { o } , U _ { I } , . . . , U _ { m } \in \mathbb { Z } _ { q } ^ { n \times m }$ 发送给敌手 $\mathcal { A }$ 。

阶段1：敌手 $\mathcal { A }$ 可以进行下面一系列的问询过程，挑战者回答敌手 $\mathcal { A }$ 下列问询：

(1)代理密钥问询：代理商的私钥 $\boldsymbol { X } _ { p } \in \mathbb { Z } _ { q } ^ { m \times m }$ 是由挑战者 $\mathcal { C }$ 均匀随机选择的小范数矩阵，计算 $\boldsymbol { A } \boldsymbol { X } _ { p } = \boldsymbol { U } _ { p }$ ，将代理商的私钥对$S K _ { p }$ 发送给 $\mathcal { A }$

(2)密钥提取问询：敌手 $\mathcal { A }$ 发送用户身份 $i d$ 给挑战者 $\mathcal { C }$ ， $\mathcal { C }$ 计算 $\begin{array} { r } { X = X _ { o } + \sum _ { i = 1 } ^ { m } i d _ { i } X _ { i } } \end{array}$ ，所以 $\scriptstyle A X = U = U _ { 0 } + \sum _ { i = 1 } ^ { m } i d _ { i } U _ { i } ( { \mathrm { m o d } } q )$ 。最后， $\mathcal { C }$ 将$\begin{array} { r } { X = X _ { o } + \sum _ { i = 1 } ^ { m } i d _ { i } X _ { i } } \end{array}$ 发送给 $\mathbfcal { \mathcal { A } }$ 作为用户私钥；

(3)重加密密钥问询：敌手 $\mathcal { A }$ 发送身份集 $( i d _ { i } , i d _ { j } , i d _ { p } )$ 给挑战者 $\mathcal { C }$ ，挑战者 $\mathcal { C }$ 按照上面的步骤计算生成 $\pmb { U } _ { i }$ ， $U _ { j }$ 和 $\boldsymbol { U } _ { p }$ ，然后，使用计算好的公钥计算生成重密钥 $r k _ { i  j } = ( U _ { j } ^ { T } - U _ { i } ^ { T } + U _ { p } ^ { T } ) s + e _ { I }$ ，并发送给 $\mathcal { A }$ 。

阶段2(挑战阶段)：当挑战者 $\mathcal { C }$ 收到来自敌手 $\mathcal { A }$ 的id\*， $m _ { 0 } , m _ { 1 }$ √挑战者随机选择 $b \in \{ 0 , 1 \}$ ，计算 $C = { U _ { i d ^ { * } } ^ { T } s + m _ { b } } \left\lfloor \frac { q } { 2 } \right\rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，并发送 $C ^ { * } = ( C , \mathbf { y } )$ 给敌手。最后敌手 $\mathcal { A }$ 猜测 $\vert \boldsymbol { b } ^ { \prime }$ ，如果 $b ^ { \prime } = b$ ，则挑战者 $\mathcal { C }$ 输出1，否则输出0。

游戏3在游戏2中，通过加密算法计算生成挑战密文$\mathbf { C } ^ { * }$ 。在游戏3中，直接从 $\mathbb { Z } _ { q } ^ { m } \times \mathbb { Z } _ { q } ^ { m }$ 中随机选择 $\mathbf { C } ^ { * }$ 。显然，敌手$\mathcal { A }$ 在游戏3中可获得的优势为0。

通过将问题规约到LWE难题来证明两个游戏的不可区分性。若敌手 $\mathcal { A }$ 能够区分两个游戏的优势为 $\varepsilon$ ，则使用下面的算法B 能够攻破LWE 困难问题[12]。

算法B收到了随机实例 $( { \pmb a } _ { i } , { \bf y } _ { i } ) \in \mathbb { Z } _ { q } ^ { n } \times \mathbb { Z } _ { q }$ ,其中 $y _ { i } = \pmb { a } _ { i } ^ { T } \pmb { S } + \pmb { e } _ { i }$ ，$\pmb { A } = ( \pmb { a } _ { I } , \pmb { a } _ { 2 } , . . . , \pmb { a } _ { m } )$ ， $\mathbf { y } = ( y _ { 1 } , y _ { 2 } , . . . , y _ { m } )$ 。计算：

$$
\begin{array} { l } { C ^ { * } = X ^ { T } y + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor } \\ { = X ^ { T } ( A ^ { T } s + e ) + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor } \\ { = U ^ { T } s + e + m \Bigg \lfloor \displaystyle \frac { q } { 2 } \Bigg \rfloor } \end{array}
$$

若敌手 $\mathcal { A }$ 成功猜测出 $\mid m$ ，则算法 $\mathbf { B }$ 输出1，否则输出0。

如果 $y$ 选取的是均匀随机的向量，则 $\mathbf { C } ^ { * }$ 也是均匀随机的，敌手 $\mathcal { A }$ 以不超过1/2的概率成功猜测出 $\mathbf { \nabla } _ { m }$ 。

若 $y$ 是由 $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ 产生的，则 $\mathbf { C } ^ { * }$ 也是均匀分布的。此时敌手 $\mathcal { A }$ 有 $( 1 + \varepsilon ) / 2$ 的优势猜测出 $\mid m$ ，算法B同样有 $( 1 + \varepsilon ) / 2$ 的概率输出1。即算法B有 $\varepsilon / 2$ 的优势解决LWE 问题。但是，LWE为格上难题，算法B不能求解出LWE困难问题，所以$\varepsilon / 2$ 的优势是可忽略的。

显然，游戏2和游戏3是不可区分的。因此，敌手 $\mathcal { A }$ 在游戏2中的可以取得优势也为0。

同样地，对于任意PPT敌手 $\mathcal { A }$ 来说，游戏1和游戏2也是不可区分的。由于矩阵A是随机的，且 $\pmb { U } _ { i }$ 服从高斯分布，根据定理3， $A X _ { i } = U _ { i } { \bmod { q } }$ 上的分布与 $\mathbb { Z } _ { q } ^ { n \times m }$ 上的均匀分布在统计量上是接近的，故无法区分游戏1和2。因此，敌手 $\mathcal { A }$ 在游戏1中获得的优势也为0。

综上所述，在标准模型下，APRE方案满足IND-aID-CPA安全性。

# 4.2 可问责性

为了证明方案的可问责性，本文将证明方案满足恶意代理安全和恶意授权者安全。

# 4.2.1恶意代理安全

定理4.2在LWE困难问题下，若敌手 $\mathcal { A }$ 在多项式时间t内成功诬陷授权者的优势 $\mathbf { A D V } _ { \mathrm { P R E } , \mathcal { A } } ^ { \mathrm { m p } } ( t ) \leq n e g l ( \lambda )$ ，则方案满足恶意代理安全，即敌手 $\mathcal { A }$ 输出一个解密算法，使审判算法输出"Delegator"的优势是可忽略的。

证明为了证明方案是恶意代理安全的，本文提出以下两个实验，通过证明两个实验的不可区分性和在实验 $\mathsf { E x p } _ { 1 }$ 中敌手 $\mathcal { A }$ 的优势是可忽略的完成恶意代理安全的证明。

实验 $\mathtt { E x p } _ { 0 }$ 原始恶意代理安全实验。敌手 $\mathcal { A }$ 输出一个能够以不可忽略的概率 $\mu$ 获得明文的解密设备 $D _ { * , \mu }$ ，挑战者 $\mathcal { C }$ 用$n$ 个不规则明文作为输入运行解密设备 $D _ { \ast , \mu }$ 。不规则密文为$C _ { 1 } = ( { \pmb U } _ { i } ^ { T } + { \pmb U } _ { p } ^ { T } ) s + m \biggl \lfloor \frac { q } { 2 } \biggr \rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，其中 $s \gets \mathbb { Z } _ { q } ^ { n }$ 。

实验 $\mathbf { E x p } _ { 1 }$ 原始恶意代理安全对比实验。与 $\mathbf { E x p } _ { 0 }$ 的不同在于不规则密文， $\mathbf { E x p } _ { 1 }$ 中密文为 $C _ { 1 } = U _ { i } ^ { T } s + m  { \left\lfloor \frac { q } { 2 } \right\rfloor } + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，其中 $s \gets \mathbb { Z } _ { q } ^ { n }$ 。

接下来使用引理4.1和引理4.2证明以上两个实验在计算上的不可区分性，且在实验 $\mathsf { E x p } _ { 1 }$ 中敌手成功诬陷授权者的概率可忽略。

引理4.1基于LWE困难问题假设下， $\mathsf { E x p } _ { \mathsf { l } }$ 与 $\mathtt { E x p } _ { 0 }$ 在计算上是不可区分的。

按照游戏2中的步骤生成 $U _ { \boldsymbol { \theta } } , U _ { \boldsymbol { I } } , . . . , U _ { m }$ ，可知 $A X _ { i } = U _ { i } { \bmod { q } }$ 的分布与 $\mathbb { Z } _ { q } ^ { n \times m }$ 上均匀分布的统计量相近。

敌手 $\mathcal { A }$ 输出一个解密设备 $D _ { i , \mu }$ ，挑战者 $\mathcal { C }$ 运行审判算法JudgeDi. :

1)重复以下实验 ${ \mathfrak { n } } = \lambda / \mu$ 次。均匀随机的选择向量 $\pmb { S } \in \mathbb { Z } _ { q } ^ { n }$ ，$\pmb { r } \in \mathbb { Z } _ { q } ^ { n }$ 和明文 $\mathrm { ~ m ~ }$ ，计算 $C _ { 1 } = { U } _ { i } ^ { T } s + { r } + m  { \left\lfloor \frac { q } { 2 } \right\rfloor } + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，密文$\pmb { C } = ( C _ { 1 } , \pmb { y } )$ ；运行解密设备 $D _ { i , \mu }$ ，并将C作为 $D _ { i , \mu }$ 的输入，输出m';

2)如果 $m ^ { \prime } = m$ ，输出"Proxy"并退出；否则输出"Delegator”对于上述审判算法，若 $\scriptstyle r = e$ ，则 $C _ { 1 } = ( U _ { i } ^ { T } + U _ { p } ^ { T } ) s + m \Bigg \lfloor \frac { q } { 2 } \Bigg \rfloor + 2 e$ ，此时 $\mathcal { C }$ 成功模拟实验 $\mathtt { E x p } _ { 0 }$ ；若 $\boldsymbol { r } = - X _ { p } ^ { T } \boldsymbol { \mathbf { y } }$ ，则 $C _ { 1 } = U _ { i } ^ { T } s + m \biggl \lfloor \frac { q } { 2 } \biggr \rfloor +$ $( e - X _ { p } ^ { T } e )$ ，此时 $\mathcal { C }$ 成功模拟实验 $\mathsf { E x p } _ { 1 }$ ；由于 $\scriptstyle { \pmb e }$ 和 $X _ { p }$ 均服从高斯分布，故对于 $\mathcal { A }$ 是不可区分的。即实验 $\mathbf { E x p } _ { 1 }$ 与 $\mathbf { E x p } _ { 0 }$ 在计算上是不可区分的。

引理4.2在 $\mathsf { E x p } _ { 1 }$ 中敌手 $\mathcal { A }$ 输出一个解密设备，使得审判算法输出"Delegator"的优势可以忽略。

在一次实验中，由于 $\mathbf { E x p } _ { 1 }$ 解密设备的输入密文$C _ { 1 } = ( { \pmb U } _ { i } ^ { T } + { \pmb U } _ { p } ^ { T } ) s + m \bigg \lfloor \frac { q } { 2 } \bigg \rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，为普通密文，所以 $D _ { i , \mu }$ 将以 $\mu$ 的概率返回明文 $m ^ { \prime } = m$ ，则敌手 $\mathcal { A }$ 在 $\mathsf { E x p } _ { \mathsf { l } }$ 中的优势为$( 1 - \mu ) ^ { n } = ( 1 - \mu ) ^ { \lambda / \mu } \leq { \frac { 1 } { e ^ { \lambda } } }$ ，故敌手的优势是可忽略的。

4.2.2恶意授权者安全

定理4.3在LWE困难假设下，若敌手 $\mathcal { A }$ 在多项式时间t 内成功诬陷代理商的优势 $\mathbf { A D V _ { P R E , \mathcal { A } } ^ { m d } } \left( t \right) \leq n e g l ( \lambda )$ ，则方案满足恶意代理安全，即敌手 $\mathcal { A }$ 输出一个解密算法，使审判算法输出“Proxy"的优势是可忽略的。

证明为了证明方案是恶意授权者安全的，提出以下两个实验，通过证明两个实验的不可区分性和在实验 $\mathsf { E x p } _ { 1 }$ 中敌手 $\mathcal { A }$ 的优势是可忽略的完成恶意授权者安全的证明。

实验 $\mathtt { E x p } _ { 0 }$ 原始恶意授权者安全实验。当敌手 $\mathcal { A }$ 输出一个能够以不可忽略的概率 $\mu$ 获得明文的解密设备 $D _ { i , \mu }$ ，挑战者 $\mathcal { C }$ 用 $n$ 个不规则明文作为输入运行解密设备 $D _ { i , \mu }$ 。不规则密文为 $C _ { 1 } = ( U _ { i } ^ { T } + U _ { p } ^ { T } ) s + m \Bigg \lfloor \frac { q } { 2 } \Bigg \rfloor + e$ ， $\scriptstyle y = A ^ { T } s + e$ ，其中 $s \gets \mathbb { Z } _ { q } ^ { n }$ 。

实验 $\mathsf { E x p } _ { 1 }$ 原始恶意授权者安全对比实验。与 $\mathtt { E x p } _ { 0 }$ 不同是审判算法的输入密文不同。均匀随机的选择矩阵 $\pmb { R } \in \mathbb { Z } _ { q } ^ { n \times m }$ ，密文为 $C _ { 1 } = ( { \pmb U } _ { i } ^ { T } + { \pmb R } ^ { T } ) s + m \lfloor \frac { q } { 2 } \rfloor + e$ ， $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ ，其中 $s \gets \mathbb { Z } _ { q } ^ { n }$ 。

接下来使用引理4.3和引理4.4证明以上两个实验在计算上的不可区分性，且在实验 $\mathsf { E x p } _ { 1 }$ 中敌手成功诬陷代理商的概率可忽略。

引理4.3基于LWE 困难问题假设下， $\mathbf { E x p } _ { 1 }$ 与 $\mathtt { E x p } _ { 0 }$ 在计算上是不可区分的。

使用游戏2中的方式生成 $U _ { o } , U _ { I } , . . . , U _ { m }$ ，可知 $\mathbf { \boldsymbol { A } } \mathbf { \boldsymbol { X } } _ { i } = \mathbf { \boldsymbol { U } } _ { i }$ mod q的分布与 $\mathbb { Z } _ { q } ^ { n \times m }$ 上的均匀分布在统计量上相近，故得证。

引理4.4在 $\mathbf { E x p } _ { 1 }$ 中敌手输出一个解密设备，使审判算法输出"Proxy"的优势是可忽略的。

解密设备 $D _ { i , \mu }$ 的输入密文为 $C _ { 1 } = ( { \pmb U } _ { i } ^ { T } + { \pmb R } ^ { T } ) s + m \lfloor \frac { q } { 2 } \rfloor + e$ $\pmb { y } = \pmb { A } ^ { T } \pmb { S } + \pmb { e }$ 。由于R 是均匀随机的， $D _ { i , \mu }$ 输出 $m ^ { \prime } = m$ 的概率为$1 / \vert M \vert = \frac { 1 } { 2 ^ { m } }$ 。根据二级解密算法可知，解密结果为 $R ^ { T } s + e - X _ { i } ^ { T } e + m \biggl \lfloor \frac { q } { 2 } \biggr \rfloor$ 因为 $R$ 是均匀随机的，无法恢复出明文 $\mathrm { ~ m ~ }$ ；且 $( \frac { 1 } { \vert M \vert } ) ^ { n } < \frac { 1 } { 2 ^ { m } }$ □知敌手 $\mathcal { A }$ 在 $\mathsf { E x p } _ { 1 }$ 的优势是可忽略的。

# 4.3效率分析

文献[13]中提出的可问责代理重加密基于DBDH困难假设，计算复杂度较高且存在证书管理问题。文献[20]中提出了格上基于身份的PRE方案，该方案可以加密多比特信息，但是方案是交互式的，被授权者需要提供自己的私钥来生成重密钥，容易造成密钥泄露的问题。文献[21]中提出单跳的格上PRE方案，使用陷门生成私钥。本文所提方案完成了可问责性和抗合谋攻击的设计；具有单向性和多跳性，密文扩展性良好；能够抵抗量子攻击。表1给出了文献[13]、[20]与本方案的存储空间和性能上的对比。其中，G是群 $\mathbb { G }$ 中元素的个数， $\left| \mathbb { G } _ { \mathrm { T } } \right|$ 表示 $\mathbb { G }$ 中元素的位长， $\log q$ 表示 $\log _ { 2 } q$ 。表2选择文献[20]、[21]与本方案的三个格上代理重加密方案进行计算和通信复杂度对比，其中，密文开销指1bit明文对应的密文大小，MMM为矩阵间乘法，MMA为矩阵间加法，VMM为向量矩阵乘法，VCM为常数向量乘法，VVM为向量间加法，EGT为群 $\mathbb { G } _ { \mathrm { T } }$ 中的幂运算，EG为群 $\mathbb { G }$ 中的幂运算。

表1存储空间和性能比较  
Tab.1Comparison of storage space and performance   

<html><body><table><tr><td>方案</td><td>私钼尺寸</td><td>单向性</td><td>困难问题</td><td>IBE</td><td>可问责性</td></tr><tr><td>文献[13]</td><td>2|G|</td><td>是</td><td>DBDH</td><td>香</td><td>是</td></tr><tr><td>文献[20]</td><td>O(ml log q)</td><td>香</td><td>LWE</td><td>是</td><td>否</td></tr><tr><td>文献[21]</td><td>O(n²k logq)</td><td>是</td><td>LWE</td><td>香</td><td>香</td></tr><tr><td>本文方案</td><td>O(mn log q)</td><td>是</td><td>LWE</td><td>是</td><td>是</td></tr></table></body></html>

结合两个表格的比较结果，本文方案在私钥尺寸上优于文献[21]，并且相较于其他方案满足单向性和可问责性；计算复杂度低于文献[20]，且密钥开销与文献[13]、[21]相比较低。因此，本文方案较为良好的安全性和较高的效率。

# 表2计算和通信复杂度比较

Tab.2Comparison of computational and communication complexity   

<html><body><table><tr><td>方案</td><td>计算复杂度</td><td>密文开销</td></tr><tr><td rowspan="2">文献[13]</td><td>2EGT+2EG</td><td>2|Gr|+2|G|</td></tr><tr><td></td><td>G</td></tr><tr><td>文献[20]</td><td>2VMM+2VCM+3VVA</td><td>2</td></tr><tr><td rowspan="2">文献[21]</td><td rowspan="2">2MMM+2MMA+1VMM</td><td>n²+nlogn</td></tr><tr><td>nlog n</td></tr><tr><td>本文方案</td><td>2VMM+1VCM+3VVA</td><td>2</td></tr></table></body></html>

# 5 结束语

本文提出了一个格上基于身份的可问责代理重加密方案。在方案中，用户的身份被计算为一个矩阵作为公钥，提高了私钥提取的效率；重密钥由用户公钥计算生成，具有非交互性；使用公共问责算法抑制恶意代理商滥用重密钥的行为。该方案具有单向性和多跳性等性质。安全分析表明，方案满足标准模型下的IND-aID-CPA安全；效率分析则说明了方案在存储空间和性能方案较有优势。但是方案在计算效率上还有一定的优化空间，构造更加高效的格上可问责的代理重加密的方案也是未来的研究方向。

# 参考文献：

[1]Blaze M,Bleumer G,Strauss M,et al.Divertible protocols and atomic proxy cryptography [C]// Theory and Application of Cryptographic Techniques,1998:127-144   
[2]Green M,Ateniese G.Identity-Based Proxy Re-encryption [C]// applied cryptography and network security,2007:288-306.   
[3]Xagawa K.Cryptography with Latices [D].[Ph.D.dissertation],Tokyo Institute of Technology,2010.http://xagawa.net/pdf/2010Thesis. pdf.   
[4]Singh K,Rangan C P,Banerjee A K.Lattice-based identity based unidirectionalproxyre-encryptionscheme[C]//International Conference on Security,Privacy,and Applied Cryptography Engineering, Pune,India,2014: 76-91.   
[5]汤永利，刘琦，张晓航，等．格上基于RLWE难题的身份基代理重加 密方案[J].计算机应用研究,2021,38(04):1199-1202.(Tang Yongli, Liu Qi,Zhang Xiaohang，et al.Identity-based proxy re-encryption scheme based on RLWE problem [J].Application Research ofComputers, 2021,38 (04):1199-1202.)   
[6]Kim K S,Jeong I R.Collusion-resistant unidirectional proxy reencryption scheme from lattices [J]. Journal of Communications and Networks,2016:1-7.   
[7]Wang X Y,HuAQ,Hao F.Improved collusion-resistant unidirectional 2020: 342-351.   
[8]Dutta P, Susilo W,Duong D H,et al. Collusion-Resistant Identity-based Proxy Re-Encryption: Latice-based Constructions in Standard Model [J]. Theoretical Computer Science,vol. 871,2021: 16-29.   
[9]Wang X A,Ge Y, Yang X. PRE+: Dual of proxy re-encryption and its application [C]// Cryptology ePrint Archive,2013.   
[10] Singh K,Rangan CP,Agrawal R,et al. Provably secure lattice based identity based unidirectional PRE and PRE+schemes [J].Journal of Information Security and Applications,2020,54 (3/4):102569.   
[11] Ateniese G,Fu K,Green M,et al.Improved Proxy Re-Encryption Schemes with Applications to Secure Distributed Storage [J].ACM Transactions on Information and System Security,vol.9,no.1,2006:1-30.   
[12] Guo H, Zhang ZF,XuJ,et al. Non-Transferable Proxy Re-Encryption [J].The Computer Journal,vol. 62, no.4,2019: 490-506.   
[13] Guo H, Zhang Z F,Xu J,et al.Accountable Proxy Re-Encryption for Secure Data Sharing [J].IEEE Transactions on Dependable and Secure Computing,vol.18,no.1,2021: 145-159.   
[14] Ajtai M.Generating hard instances of lattice problems [C]// The 28th ACM Symposium on Theory of Computing.New York: ACM,1996: 99-108.   
[15] Gentry C,Peikert C,Vaikuntanathan V. How to use a short basis: Trapdoors for hard lattices and new cryptographic constructions [C]// The 40th ACM Symposium on Theory of Computing, Victoria, Canada, 2008:197-206.   
[16]王凤和，胡予濮，贾艳艳．标准模型下的格基数字签名方案[J]．西 安电子科技大学学报,2012,39 (04):57-61,119.(Wang Fenghe,Hu Yupu, Jia Yanyan. Latice-based signature scheme in the standard model [J].Journal of Xidian University,2012,39 (04): 57-61,119.)   
[17] Micciancio,D,Peikert C.Hardness of SIS and LWE with Small Parameters [C]//The 33rd Annual International Cryptology Conference, vol. 2013:21-39.   
[18] Regev O.On Lattices,Learning with Errors,Random Linear Codes, and Cryptography [Cl//Proceedings of the 37th annual ACM symposium on Theory of computing.ACM,2005: 84-93.   
[19] Wang XY,Hu AQ,Hao F.Feasibility Analysis of Lattice-Based Proxy Re-Encryption [Cl// Proc of the 17th International Conference on Cryptography, Security and Privacy,2017: 12-16.   
[20] Hou J,Jiang M,Guo Y,et al.Efficientidentity-based multi-bit proxyreencryption over lattice in the standard model [J]. Information Security Technical Report, 2019: 329-334.   
[21] Kirshanova E.Proxy re-Encryption from lattices [C]//Proc of the 17th International Conference on Public-Key Cryptography Volume 8383, 2014: 77-94.