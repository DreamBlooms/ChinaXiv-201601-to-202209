# 基于Goldwasser-Micali加密算法的安全子集计算

王倩，任方ʰ，郑东ʰ(西安邮电大学 a.计算机学院;b.通信与信息工程学院，西安 710121)

摘要：针对集合间的安全子集问题进行了研究，目前存在解决此类问题的协议大多只能保护一个集合元素的隐私，因此，对于此类问题的研究具有重要的现实意义。在半诚实模型下，利用布隆过滤器及Goldwasser-Micali同态加密算法构建了一个安全子集计算协议，并使用安全多方计算中普遍采用的模拟范例证明方法证明了协议的安全性。利用布隆过滤器将拥有大量元素或大数域元素的数据集合映射为较小的数据集合，提升协议的效率及适用范围，同时，借助 Goldwassr-Micali同态加密算法保证协议的安全性。相关研究大多是基于二次剩余等困难问题，不可抵抗量子攻击，可抵抗量子攻击的安全子集计算是进一步的研究方向。

关键词：安全多方计算；同态加密；布隆过滤器；Goldwasser-Micali加密算法；安全子集问题中图分类号：TP309.7 doi:10.19734/j.issn.1001-3695.2018.09.0758

Secure subset computation based on Goldwasser-Micali encryption algorithm

Wang Qiana, Ren Fangb, Zheng Dongb (a.Schoolofcomputer science,b.SchoolofCommunications&InformationEngineering,Xi'an UniversityofPosts& Telecommunications,Xi'an 710121,China)

Abstract: Study the problem of secure subset, most of the existing protocols that solve such problems can only kep the elementsofoneset private,therefore,ithasgreatpracticalsignificancetostudythis kindofproblem.Under thesemi-honest model,this paperconstructed a secure subset protocol byusing Bloom fiter and Goldwassr-Micali homomorphic encryption algorithm,and proved the securityof the protocol by using common simulation examples in secure multi-party computing.ItusedtheBloomflter to mapadata set withalarge numberorlarge number field elements intoasmalerdata set,improved theeficiencyandrangeof the protocol,atthesame time,itused the Goldwasser-Micali homomorphic encryption algorithm to ensure the securityof the protocol.Mostof therelevant researchesare basedon the dificult problems suchthatsecondary residuals,itis impossible toresist quantumattacks,andthe secure subset computation which can resist quantum attacks is a further research direction.

Key words:secure multi-partycomputation；homomorphic encryption;bloom filter；Goldwasser-Micaliencryption algorithm; secure subset problem

# 0 引言

网络的迅速发展给多方合作计算中参与者的信息安全带来了巨大的挑战，使安全多方计算[1,2](secure multi-partycomputation,SMC)成为国际密码学界研究的热点问题。安全多方计算指多个参与者共同秘密计算，且每个参与者的输入信息是保密的，计算结束后，各个参与者除了得到正确的输出结果外，无法获知任何其他输入信息。在借助可信第三方的情况下，安全多方计算非常简单，但在复杂网络中，找到公认的可信第三方是不可能的，因而需要使用其他方式解决该问题。

两个参与者的安全多方计算最早于1982 年由姚期智教授[1]提出，1987年，Goldreich等人[2]提出了可以计算任意函数的基于密码学安全模型的安全多方计算协议，1988年Ben和Goldwasser[3]提出了多个参与者的安全多方计算，1998年，Goldreich对安全多方计算做了比较完整的总结，并提出了安全多方计算的安全性定义。Goldreich和Goldwasser等人的研究推动了安全多方计算的发展，同时激励着研究人员研究各种具有实际应用背景的安全多方计算问题，包括百万富翁问题[1,4,5]、保密的信息比较[、保密的统计分析[]、保密的计算几何[8-10]、保密的数据挖掘[11]、保密的集合问题[12\~14]等。

Goldwasser-Micali 加密算法是 1982 年由 Goldwasser[15]等人提出的，其安全性基于二次剩余困难问题，该加密算法具有异或同态性。文献[16,17]基于Goldwasser-Micali加密算法提出了隐私交集基数协议，其中文献[16]以布隆过滤器(Bloom filter)[18]为工具。本文利用Goldwasser-Micali 同态加密算法和布隆过滤器，在半诚实模型下，构建了一个安全子集计算协议，并对其进行了正确性、安全性证明。

# 1 预备知识

# 1.1安全子集问题

假设Alice输入集合 $A = \left\{ a _ { 1 } , a _ { 2 } , . . . , a _ { m } \right\}$ ，Bob输入集合$B = \{ b _ { 1 } , b _ { 2 } , . . . , b _ { n } \}$ ，Alice 和 Bob 想要在不向对方泄露其集合元素任何信息的情况下，输出集合 $B$ 是否是集合 $A$ 的子集，即判断 $B \subseteq A \ ?$ 的问题称为安全子集问题[12]。

# 1.2二次剩余问题

对于整数 $n > 1$ ，定义 $Z _ { n } ^ { * } = \{ a \in Z _ { n } : \operatorname* { g c d } ( a , n ) = 1 \}$ 。当存在 $d \in Z _ { n }$ ，使得 $d ^ { 2 } \equiv a { \bmod { n } }$ ，称 $\mathbf { \Delta } _ { a }$ 为模 $n$ 的二次剩余；否则称 $\mathbf { \Delta } _ { a }$ 为模 $n$ 的二次非剩余。判断 $\mathbf { \Delta } _ { a }$ 是否为模 $n$ 的二次剩余的问题称为模$n$ 的二次剩余问题[17]。

# 1.3Goldwasser-Micali同态加密方案

Goldwasser-Micali(GM)加密方案是第一个证明为CPA安全的公钥加密方案，其安全性依赖于从合数模的二次非剩余中区分二次剩余困难性假设[19]。具体如下。

a）密钥生成算法。用户随机生成两个大素数 $p$ 和 $\boldsymbol { q }$ ，计算 $n = p q$ ， $z$ 是模 $n$ 的二次非剩余中的随机数。系统公钥$p k = \left( n , z \right)$ ，系统私钥 ${ \mathit { s k } } = \left( { \mathit { p } } , { \mathit { q } } \right)$ 0b）加密算法。明文空间是 $\{ 0 , 1 \}$ ，对于明文 $\boldsymbol { x } \in \{ 0 , 1 \}$ ，加密方选取秘密随机数 $r \in Z _ { n } ^ { * }$ ，利用系统公钥 $p k$ 计算密文$E ( x ) = r ^ { 2 } z ^ { x } { \bmod { n } }$ 。c）解密算法。对于密文 $E ( x )$ ，判断 $E ( x )$ 是否为模 $n$ 的二次剩余，若 $E ( x )$ 是模 $n$ 的二次剩余，则明文 $D ( E ( x ) ) = 0$ ：若 $E ( x )$ 不是模 $n$ 的二次剩余，则 $D ( E ( x ) ) = 1$ 。GM加密系统的安全性是基于模 $n$ 的二次剩余问题。对于私钥的拥有者，知道大整数 $n$ 的因子分解，求解模 $n$ 的二次剩余问题是容易的；而对于攻击者，无法获知 $n$ 的因子分解，求解模 $n$ 的二次剩余问题是困难的，继而保证了该加密方案的安全性。

该加密方案具有如下性质：

a）异或同态性。设明文 $x _ { 1 }$ 和 $x _ { 2 }$ 的密文为 $E ( x _ { 1 } )$ 和 $E \big ( x _ { 2 } \big )$ ，则 $E { \left( x _ { 1 } \right) } \cdot E { \left( x _ { 2 } \right) }$ 是 $x _ { 1 } \oplus x _ { 2 }$ 的密文，即 $D ( E ( x _ { 1 } ) \cdot E ( x _ { 2 } ) ) = x _ { 1 } \oplus x _ { 2 }$ ；b）非运算同态性。即 $E ( x ) \cdot z = E ( x \oplus 1 ) = E ( { \overline { { x } } } )$ ;c）重复加密随机性。即 $D ( E ( x ) \cdot E ( 0 ) ) = D ( E ( x ) )$ 0

# 1.4布隆过滤器 (Bloom Filter)

布隆过滤器（Bloom filter）是1970 年由Bloom[18]提出的一种基于多个哈希函数映射压缩参数空间的数据结构，由一个很长的二进制向量和一组hash 函数构成，通过hash 函数将拥有大量元素或大数域元素的数据集合映射为较小的数据集合，如需判断一个元素是否在集合中，将元素用相同的hash函数处理，并将产生的hash值与布隆过滤器中的数据集合比较，相等说明元素在集合中，否则，元素不在集合中。具体工作过程如下：

a)初始化。设集合 $B$ 的布隆过滤器为 $B F _ { B } = \left( \omega , n , k , H \right)$ ， $\omega$ 是 $B F _ { B }$ 的向量组大小， $H = \left( { { h _ { 1 } } , { h _ { 2 } } , . . . , { h _ { k } } } \right)$ 是 $k$ 个相互独立的 hash函数，在初始状态下，将 $B F _ { B }$ 的每一位都置为0。b）存储映射过程。集合 $B$ 中的任意元素 $b$ 经过布隆过滤器的hash 映射时，每个映射值所对应的 $B F _ { B }$ 中的位置均被置为1，即 $B F _ { \scriptscriptstyle B } \left[ h _ { j } \left( b \right) \right] = 1$ ， $j = 1 , 2 , . . . , k$ ，所有 $B$ 中的元素都映射存储在 $B F _ { B }$ 中后， $B F _ { B }$ 代表集合 $B$ 。如图1所示。

![](images/046bad12d1395bebbd3fb9015586849cce03da129ff96aa9274ebfc350ff9809.jpg)  
图1布隆过滤器的存储映射过程  
Fig.1Stored mapping procedure for bloom filter   
Fig.2Find mapping procedure for bloom filter

c）查找映射过程。若要判断元素 $b ^ { \prime }$ 是否是集合 $B$ 中的元素，需要对元素 $b ^ { \prime }$ 进行hash 映射，计算并验证当 $j = 1 , 2 , . . . , k$ 时， $B F _ { B } \big [ h _ { j } ( b ^ { \prime } ) \big ]$ 是否均为1，若其中有一位为0，则 $b ^ { \prime }$ 不是集合 $B$ 中的元素，否则 $b ^ { \prime }$ 有较高的几率是集合 $B$ 中的元素。如图2所示。

![](images/e76c8b6a27c1c094c04c5094e01a35be43dffa92e3b46914abba5ae71d81d345.jpg)  
图2布隆过滤器的查找映射过程

布隆过滤器的优点是空间及查询效率远高于其他算法，不需要存储元素本身，仅需要几个简单的字节位即可保存一个元素；缺点是会对一些未处理或不属于集合的元素产生误判，随着存入查询频率的增多，误判率越大，例如：如果 $b$ 是集合 $B$ 中的元素， $j = 1 , 2 , . . . , k$ 时 $B F _ { B } \left[ h _ { j } \left( b ^ { \prime } \right) \right]$ 一定为1；如果 $b$ 不是集合 $B$ 中的元素， $j = 1 , 2 , . . . , k$ 时 $B F _ { B } \left[ h _ { j } \left( b ^ { \prime } \right) \right]$ 可能为1。

# 1.5半诚实模型下的安全性

假设有一个可信第三方（trustedthirdparty,TTP)，在任何情况下都不会泄露任何不该泄露的信息。多个参与者联合进行安全计算时，将秘密信息发送给可信第三方，由可信第三方完成运算并将结果发送给各个参与者，这种计算模型称为可信第三方模型。计算结束后，参与者只得到可信第三方发送给自己的计算结果而得不到任何其他信息，这种可信第三方模型具有最高的安全性，但是现实生活中很难找到可以完全信任的第三方机构，因此，这种可信第三方模型也称为理想模型。

在目前的安全多方计算研究中，很少使用理想模型。在半诚实模型下，实际的安全多方计算协议可通过与理想的安全多方计算协议对比来检验其安全性，目前普遍采用的安全性证明方法模拟范例就是基于此类方式证明，如果实际的安全多方计算协议不比理想的安全多方计算协议泄露更多信息，则证明这个协议是安全的[20]。本文采用的安全性证明方式即为模拟范例。

假设参与者 $P _ { 1 }$ 和 $P _ { 2 }$ 要计算函数f:

$$
\{ 0 , 1 \} ^ { * } \times \{ 0 , 1 \} ^ { * } \mapsto \{ 0 , 1 \} ^ { * } \times \{ 0 , 1 \} ^ { * }
$$

其中: $f ( x , y ) = ( f _ { 1 } ( x , y ) , f _ { 2 } ( x , y ) )$ ， $\pi$ 是参与者 $P _ { 1 }$ 和 $P _ { 2 }$ 计算函数 $f$ 的一个双方协议。

参与者 $P _ { 1 }$ 和 $P _ { 2 }$ 在协议 $\pi$ 的执行过程中得到的信息分别记为

$$
\mathbf { v i e w } _ { 1 } ^ { \Pi } \left( x , y \right) { = } \left( x , r ^ { 1 } , m _ { 1 } ^ { 1 } , m _ { 2 } ^ { 1 } , . . . , m _ { t } ^ { 1 } \right)
$$

$$
\mathbf { \Phi } ^ { \mathrm { I } } \left( x , y \right) = \left( y , r ^ { 2 } , m _ { 1 } ^ { 2 } , m _ { 2 } ^ { 2 } , . . . , m _ { t } ^ { 2 } \right)
$$

其中: $r ^ { i }$ 表示参与者 $P _ { i }$ 产生的随机数， $m _ { j } ^ { i }$ 表示 $P _ { i }$ 收到的第 $j$ 条信息。协议执行完后，参与者 $P _ { i }$ 的输出结果记为 $\mathrm { o u t p u t } _ { i } ^ { \Pi } \left( x , y \right)$ 。

对于函数 $f = \left( f _ { 1 } , f _ { 2 } \right)$ ，本文称协议 $\pi$ 在半诚实模型下安全的计算函数 $f ,$ ，当且仅当存在概率多项式时间算法 $S _ { 1 }$ 和 $S _ { 2 }$ 满足

$$
{ \left\{ { S _ { 1 } } \left( x , { f _ { 1 } } \left( x , y \right) \right) , { f _ { 2 } } \left( x , y \right) \right\} } \equiv \left\{ { \mathrm { v i e w } _ { 1 } ^ { \Pi } \left( x , y \right) , \mathrm { o u t p u t } _ { 2 } ^ { \Pi } \left( x , y \right) \right\} }
$$

$$
\{ f _ { 1 } ( x , y ) , S _ { 2 } \left( y , f _ { 2 } ( x , y ) \right) \} \overset { \mathrm { c } } { \equiv } \{ \mathrm { o u t p u t } _ { 1 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) , \mathrm { v i e w } _ { 2 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) \}
$$

其中: $\circleddash$ 表示随机变量簇的计算不可区分[17]。

# 2 基于Goldwasser-Micali 加密算法的安全多方子集计算

本节基于Goldwasser-Micali同态加密算法的重复加密随机性，利用布隆过滤器，在半诚实模型下构建了一个安全子集计算协议，并给出了正确性证明，同时，利用模拟范例证明方式对协议进行了安全性证明。协议通过使用布隆过滤器，可将拥有大量元素或大数域元素的数据集合，通过hash函数映射为较小的数据集合，提升了协议的效率及适用范围。具体协议如协议1。

2.1协议1

输入：Alice 输入集合 $A = \left\{ a _ { 1 } , a _ { 2 } , . . . , a _ { m } \right\}$ ，Bob 输入集合$B = \{ b _ { 1 } , b _ { 2 } , . . . . , b _ { n } \}$ 。

输出：集合 $B$ 是否是集合 $A$ 的子集，即 $B \subseteq A \ ?$ 。

a）Alice和Bob共同协商参数 $\omega , k , H = ( h _ { 1 } , h _ { 2 } , . . . , h _ { k } )$ ，并分别构建其输入集合的Bloomfilter，其中集合 $A$ 的 Bloom filter记为 $B F _ { A }$ ，集合 $B$ 的 Bloom filter 记为 $B F _ { B }$ ;

$$
B F _ { A } = \left( B F _ { A } \left[ 1 \right] , B F _ { A } \left[ 2 \right] , \ldots , B F _ { A } \left[ \omega \right] \right)
$$

$$
B F _ { B } = \left( B F _ { B } \left[ 1 \right] , B F _ { B } \left[ 2 \right] , . . . , B F _ { B } \left[ \omega \right] \right)
$$

b）Alice 生成Goldwasser-Micali 加密系统的公私钥对$( p k , s k )$ ，公开其公钥 $p k = \left( n , z \right)$ ，并用公钥 $p k$ 逐比特加密得$E \big ( B F _ { A } \big )$ ，将加密后的 $E \big ( B F _ { A } \big )$ 发送给Bob;

$$
E \left( B F _ { A } \right) = \left( E \left( B F _ { A } \left[ 1 \right] \right) , E \left( B F _ { A } \left[ 2 \right] \right) , . . . , E \left( B F _ { A } \left[ \omega \right] \right) \right)
$$

c）Bob根据 $B F _ { B }$ 中为1的位 $\left\{ B F _ { B } \left[ i _ { 1 } \right] , B F _ { B } \left[ i _ { 2 } \right] . . . , B F _ { B } \left[ i _ { t } \right] \right\}$ ，从$E \big ( B F _ { A } \big )$ 选取 $\{ E ( B F _ { A } \left[ i _ { 1 } \right] ) , E ( B F _ { A } \left[ i _ { 2 } \right] ) , . . . , E ( B F _ { A } \left[ i _ { t } \right] ) \}$ 。描述成伪代码如下：

$$
\begin{array} { r l } & { i = 1 \quad \mathrm { t o } \quad \omega } \\ & { \mathrm { i f } \quad B F _ { \scriptscriptstyle B } \left[ i \right] = 1 } \\ & { \qquad \mathrm { r e t u r n } \quad E \big ( B F _ { \scriptscriptstyle A } \left[ i \right] \big ) } \end{array}
$$

d）Bob 随机生成 $\mathbf { \chi } _ { t } ^ { }$ 个数 $\{ r _ { 1 } , r _ { 2 } , . . . , r _ { t } \}$ ，并用 $\{ r _ { 1 } , r _ { 2 } , . . . , r _ { t } \}$ 对$\{ E ( B F _ { A } \left[ i _ { 1 } \right] ) , E ( B F _ { A } \left[ i _ { 2 } \right] ) , . . . , E ( B F _ { A } \left[ i _ { t } \right] ) \}$ 进行加密得：$\{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \}$ $\begin{array} { r l } & { \mathsf { \Gamma } _ { = } ^ { \star } \bigl \{ E \bigl ( B F _ { A } \left[ i _ { 1 } \right] \bigr ) \cdot r _ { 1 } ^ { 2 } \bmod n , E \bigl ( B F _ { A } \left[ i _ { 2 } \right] \bigr ) \cdot r _ { 2 } ^ { 2 } \bmod n , . . . , E \bigl ( B F _ { A } \left[ i _ { t } \right] \bigr ) \cdot r _ { t } ^ { 2 } \bmod n \bigr \} } \end{array}$

并将 $\{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \}$ 发送给Alice，其中 $n$ 是密钥参数中的模数；

e）Alice对 $\{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \}$ 进行解密得 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ：

$$
\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \} = \{ D ( C _ { 1 } ) , D ( C _ { 2 } ) , . . . , D ( C _ { t } ) \} _ { } \nonumber
$$

输出 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ，如果 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ 均为1，那么 $B \subseteq A$ ，否则 $B \not \subset A$ 。

其中Bob执行协议部分，即协议1的第c)d)步骤如图3所示，假设集合B的布隆过滤器 $B F _ { B }$ 中的某些位为1。

![](images/abf71c09aa55ab6faabdf06c8ea7e6b581ca68f53e4d30724e0d57a9580cde4a.jpg)  
图3Bob执行协议部分框图

Fig.3Bob executes part of the protocol block diagram

# 2.2 正确性分析

在半诚实模型下，Alice和Bob都严格遵循协议1。对于任意 $i = 1 , 2 , . . . , t$ ，均有

$$
r _ { i } ^ { 2 } \bmod n = r _ { i } ^ { 2 } \cdot z ^ { 0 } { \bmod { n } } = E ( 0 ) \ ,
$$

即 $r _ { i } ^ { 2 } \bmod { n }$ 可视为 $\mathrm { \bar { \cdot } 0 ^ { \cdot } }$ 的密文，根据Goldwasser-Micali同态加密方案的重复加密随机性可知：

$$
\begin{array} { r } { E \big ( B F _ { A } \left[ i _ { 1 } \right] \big ) \cdot r _ { 1 } ^ { 2 } \bmod n = E \big ( B F _ { A } \left[ i _ { 1 } \right] \big ) \cdot E ( 0 ) = E \big ( B F _ { A } \left[ i _ { 1 } \right] \big ) } \\ { \vdots } \end{array}
$$

$$
E { \big ( } B F _ { A } [ i _ { t } ] { \big ) } \cdot r _ { t } ^ { 2 } \mod n = E { \big ( } B F _ { A } [ i _ { t } ] { \big ) } \cdot E { \big ( } 0 { \big ) } = E { \big ( } B F _ { A } [ i _ { t } ] { \big ) }
$$

相当于对 $\{ E ( B F _ { A } \left[ i _ { 1 } \right] ) , E ( B F _ { A } \left[ i _ { 2 } \right] ) , . . . , E ( B F _ { A } \left[ i _ { t } \right] ) \}$ 进行了重复加密，因此

$$
\begin{array} { r l } & { \{ d _ { 1 } , . . . d _ { t } \} } \\ & { = \{ D ( C _ { 1 } ) , . . . , D ( C _ { t } ) \} } \\ & { = \{ D ( E ( B F _ { A } [ i _ { 1 } ] ) \cdot r _ { 1 } ^ { 2 } \bmod n ) , . . . , D ( E ( B F _ { A } [ i _ { t } ] ) \cdot r _ { t } ^ { 2 } \bmod n ) \} } \\ & { = \{ D ( E ( B F _ { A } [ i _ { 1 } ] ) ) , . . . , D ( E ( B F _ { A } [ i _ { t } ] ) ) \} } \\ & { = \{ B F _ { A } [ i _ { 1 } ] , . . . , B F _ { A } [ i _ { t } ] \} } \end{array}
$$

若 $\{ B F _ { A } [ i _ { 1 } ] , B F _ { A } [ i _ { 2 } ] , . . . , B F _ { A } [ i _ { t } ] \}$ 均为1，说明对于任意元素$\scriptstyle x \in B$ ，都有 $x \in A$ ，即 $B \subseteq A$ ;

若 $\{ B F _ { A } [ i _ { 1 } ] , B F _ { A } [ i _ { 2 } ] , . . . , B F _ { A } [ i _ { t } ] \}$ 中至少有一位为0，说明存在元素 $\boldsymbol { x } \in \boldsymbol { B }$ ，使得 $x \not \in A$ ，即 $B \not \subset A$ 。

由此可知，协议1正确。

# 3 安全性分析

在半诚实模型下，Alice和Bob都严格遵循协议1，允许他们借助自己在执行协议过程中的全部中间信息，去推测对方的秘密输入信息。

令 $f _ { 1 } ( x , y ) = \{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ， $f _ { 2 } \left( x , y \right) = \perp$ (空字符)，下面构造概率多项式时间模拟器 $S _ { 1 }$ 和 $S _ { 2 }$ ，使下面两个关系成立。

$$
{ \left\{ { S _ { 1 } } \left( { x , f _ { 1 } } \left( x , y \right) \right) , f _ { 2 } \left( x , y \right) \right\} } \equiv \left\{ { \mathrm { v i e w } _ { 1 } ^ { \mathrm { \tiny { \Pi } } } } \left( x , y \right) , \mathrm { o u t p u t } _ { 2 } ^ { \mathrm { \tiny { \Pi } } } \left( x , y \right) \right\}
$$

$$
\{ f _ { 1 } ( x , y ) , S _ { 2 } \left( y , f _ { 2 } ( x , y ) \right) \} \overset { \mathrm { c } } { \equiv } \{ \mathrm { o u t p u t } _ { 1 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) , \mathrm { v i e w } _ { 2 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) \}
$$

1）构造模拟器 $S _ { 1 }$ ，使得等式（3-1）成立

执行完协议1后，Alice的view为

$$
\nu i e w _ { 1 } ^ { \Pi } \left( x , y \right) = \left( A , R _ { 1 } , \{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \} \right) ,
$$

其中 $R _ { 1 }$ 是Alice生成的随机数， $\{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \}$ 是Alice从Bob处收到的信息。

$S _ { 1 }$ 的模拟过程如下：

$S _ { 1 }$ 根据集合 $A$ 和参数 $\scriptstyle { \omega , k , H }$ 构建集合 $A$ 的Bloom filter记为 $B F _ { A }$ ;

由于 $S _ { 1 }$ 拥有 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ，它根据 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ 构造集合 $B$ 的Bloom filter 记为 $B F _ { B } ^ { \prime }$ ，使得 $B F _ { B } ^ { \prime }$ 中为1的位

$$
\left\{ B F _ { B } ^ { \prime } [ i _ { 1 } ] , B F _ { B } ^ { \prime } [ i _ { 2 } ] , . . . , B F _ { B } ^ { \prime } [ i _ { t } ] \right\} ,
$$

对应的 $B F _ { A }$ 中分别为

$$
B F _ { A } \left[ i _ { 1 } \right] = d _ { 1 } , B F _ { A } \left[ i _ { 2 } \right] = d _ { 2 } , . . . , B F _ { A } \left[ i _ { t } \right] = d _ { t } \ ,
$$

$S _ { 1 }$ 用公钥 $p k$ 对 $\{ B F _ { A } [ i _ { 1 } ] , B F _ { A } [ i _ { 2 } ] , . . . , B F _ { A } [ i _ { t } ] \}$ 加密得

$$
\left\{ E ^ { \prime } ( B F _ { A } \left[ i _ { 1 } \right] ) , E ^ { \prime } ( B F _ { A } \left[ i _ { 2 } \right] ) , . . . , E ^ { \prime } ( B F _ { A } \left[ i _ { t } \right] ) \right\}
$$

$S _ { 1 }$ 随机生成 $\mathbf { \chi } _ { t }$ 个数 $\left\{ \boldsymbol { r } _ { 1 } ^ { \prime } , \boldsymbol { r } _ { 2 } ^ { \prime } , . . . , \boldsymbol { r } _ { t } ^ { \prime } \right\}$ ，并对

$$
\left\{ E ^ { \prime } ( B F _ { A } \left[ i _ { 1 } \right] ) , E ^ { \prime } ( B F _ { A } \left[ i _ { 2 } \right] ) , . . . , E ^ { \prime } ( B F _ { A } \left[ i _ { t } \right] ) \right\}
$$

进行加密，得：

$$
\begin{array} { r l } & { \left\{ C _ { 1 } ^ { \prime } , . . . , C _ { t } ^ { \prime } \right\} } \\ & { = \{ E ^ { \prime } ( B F _ { A } \left[ i _ { 1 } \right] ) \cdot r _ { 1 } ^ { \prime 2 } \bmod n , . . . , E ^ { \prime } ( B F _ { A } \left[ i _ { t } \right] ) \cdot r _ { n } ^ { \prime 2 } \bmod n \} } \end{array}
$$

$S _ { 1 } ( x , f _ { 1 } ( x , y ) ) = ( A , R _ { 1 } ^ { \prime } , \{ C _ { 1 } ^ { \prime } , C _ { 2 } ^ { \prime } , . . . , C _ { t } ^ { \prime } \} )$ ,其中 $R _ { 1 } ^ { \prime }$ 是 S1生成的随机数。

下面证明 $\left\{ S _ { 1 } \left( x , f _ { 1 } \left( x , y \right) \right) , f _ { 2 } \left( x , y \right) \right\} \overset { \mathrm { c } } { = } \left\{ \mathrm { v i e w } _ { 1 } ^ { \Pi } \left( x , y \right) , \mathrm { o u t p u t } _ { 2 } ^ { \Pi } \left( x , y \right) \right\}$ 成

立，其中 $f _ { 2 } \left( x , y \right) { = } \mathrm { o u t p u t _ { 2 } ^ { \Pi } } \left( x , y \right) { = } \perp$ 。只需证明

$$
S _ { 1 } \left( x , f _ { 1 } \left( x , y \right) \right) { \stackrel { \mathrm { c } } { = } } \mathrm { v i e w } _ { 1 } ^ { \Pi } \left( x , y \right) ,
$$

即证明下面的关系成立：

$$
\left( A , R _ { 1 } ^ { \prime } , \left\{ C _ { 1 } ^ { \prime } , C _ { 2 } ^ { \prime } , . . . , C _ { t } ^ { \prime } \right\} \right) ^ { \mathrm { c } } = \left( A , R _ { 1 } , \left\{ C _ { 1 } , C _ { 2 } , . . . , C _ { t } \right\} \right) \circ
$$

由于 $\left| R _ { \mathrm { l } } ^ { \prime } \right.$ 和 $R _ { \mathrm { 1 } }$ 分别是 $S _ { 1 }$ 和Alice生成的随机数，因此$\left\{ R _ { 1 } ^ { \prime } \right\} \overset { \mathrm { ~ c ~ } } { = } \left\{ R _ { 1 } \right\}$ ，又 $C _ { i } = E \big ( { \cal B } F _ { A } \left[ i \right] \big ) \cdot r _ { i } ^ { 2 } \mathrm { m o d } n \ , \quad C _ { i } ^ { \prime } = E ^ { \prime } \big ( { \cal B } F _ { A } \left[ i \right] \big ) \cdot r _ { i } ^ { \prime 2 } \mathrm { m o d } n \ ,$ （20其中 $r _ { i }$ 与 $r _ { i } ^ { \prime }$ 分别是 Bob 和 $S _ { 1 }$ 选取的随机数，故 $C _ { i }$ 和 $C _ { i } ^ { \prime }$ 是随机的， $\left\{ C _ { i } \right\} \equiv \left\{ C _ { i } ^ { \prime } \right\}$ ，

综上可得：

$$
\left\{ S _ { 1 } \left( x , f _ { 1 } \left( x , y \right) \right) , f _ { 2 } \left( x , y \right) \right\} \overset { \mathrm { c } } { = } \left\{ \mathrm { v i e w } _ { 1 } ^ { \mathrm { \scriptscriptstyle T \| } } \left( x , y \right) , \mathrm { o u t p u t } _ { 2 } ^ { \mathrm { \scriptscriptstyle T \| } } \left( x , y \right) \right\} \ : \circ
$$

2）构造模拟器 $S _ { 2 }$ ，使得等式（3-2）成立执行完协议1后，Bob的view为

$\begin{array} { r } { \nu i e w _ { 2 } ^ { \Pi } \left( x , y \right) = \left( B , R _ { 2 } , \left\{ E \left( B F _ { A } \left[ 1 \right] \right) , E \left( B F _ { A } \left[ 2 \right] \right) , . . . , E \left( B F _ { A } \left[ \omega \right] \right) \right\} \right) , } \end{array}$ 其中： $R _ { 2 }$ 是Bob生成的随机数，$\{ E ( B F _ { A } \left[ 1 \right] ) , E ( B F _ { A } \left[ 2 \right] ) , . . . , E ( B F _ { A } \left[ \omega \right] ) \}$ 是 Bob 从 Alice 处收到的信息。

$S _ { 2 }$ 的模拟过程如下：

$S _ { 2 }$ 根据集合 $B$ 和参数 $\scriptstyle { \omega , k , H }$ 构建集合 $B$ 的 Bloom filter记为 $B F _ { B }$ ;

由于 $S _ { 2 }$ 拥有 $\{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ，它构造集合 $A$ 的 Bloom filter记为 $B { F _ { A } } ^ { \prime } = \left\{ B F _ { A } ^ { \prime } \big [ 1 \big ] , B F _ { A } ^ { \prime } \big [ 2 \big ] , . . . , B F _ { A } ^ { \prime } \big [ \omega \big ] \right\}$ ，使得 $B F _ { B }$ 中为1的位

$$
\left\{ B F _ { B } \left[ i _ { 1 } \right] , B F _ { B } \left[ i _ { 2 } \right] , \ldots , B F _ { B } \left[ i _ { t } \right] \right\} ,
$$

对应的 $B F _ { A } ^ { \prime }$ 中分别为

$$
B F _ { A } ^ { \prime } \left[ i _ { 1 } \right] = d _ { 1 } , B F _ { A } ^ { \prime } \left[ i _ { 2 } \right] = d _ { 2 } , . . . , B F _ { A } ^ { \prime } \left[ i _ { t } \right] = d _ { t } \ ;
$$

$S _ { 2 }$ 用公钥 $p k$ 对 $B F _ { A } ^ { \prime }$ 加密得

$$
\left\{ E ^ { \prime } ( B F _ { A } ^ { \prime } [ 1 ] ) , E ^ { \prime } ( B F _ { A } ^ { \prime } [ 2 ] ) , . . . , E ^ { \prime } ( B F _ { A } ^ { \prime } [ \omega ] ) \right\} ;
$$

$S _ { 2 }$ 随机生成 $\mathbf { \Phi } _ { t }$ 个数 $\left\{ \boldsymbol { r } _ { 1 } ^ { \prime } , \boldsymbol { r } _ { 2 } ^ { \prime } , . . . , \boldsymbol { r } _ { t } ^ { \prime } \right\}$ ，并对

$$
\{ E ^ { \prime } ( B F _ { A } ^ { \prime } \left[ 1 \right] ) , E ^ { \prime } ( B F _ { A } ^ { \prime } \left[ 2 \right] ) , . . . , E ^ { \prime } ( B F _ { A } ^ { \prime } \left[ \omega \right] ) \}
$$

进行加密，得

$$
\begin{array} { r l } & { \left\{ C _ { 1 } ^ { \prime } , . . . , C _ { t } ^ { \prime } \right\} } \\ & { = \{ E ^ { \prime } ( B F _ { A } \left[ i _ { 1 } \right] ) \cdot r _ { 1 } ^ { \prime 2 } \bmod n , . . . , E ^ { \prime } ( B F _ { A } \left[ i _ { t } \right] ) \cdot r _ { n } ^ { \prime 2 } \bmod n \} } \end{array}
$$

$$
S _ { 2 } \left( f _ { 2 } ( x , y ) , y \right) = \left( B , R _ { 2 } ^ { \prime } , \left\{ E ^ { \prime } ( B F _ { \cal A } ^ { \prime } [ 1 ] ) , E ^ { \prime } ( B F _ { \cal A } ^ { \prime } [ 2 ] ) , . . . , E ^ { \prime } ( B F _ { \cal A } ^ { \prime } [ \omega ] ) \right\} \right) \quad ,
$$

其中 ${ R _ { 2 } ^ { \prime } } ^ { \prime }$ 是 S2生成的随机数。

下面证明 $\{ f _ { 1 } ( x , y ) , S _ { 2 } \left( y , f _ { 2 } ( x , y ) \right) \} \overset { \mathrm { c } } { = } \{ \mathrm { o u t p u t } _ { 1 } ^ { \mathrm { \Pi } } ( x , y ) , \mathrm { v i e w } _ { 2 } ^ { \mathrm { \Pi } } ( x , y ) \}$ 成立，其中 $f _ { 1 } ( x , y ) { = } \mathrm { { o u t p u t } } _ { 1 } ^ { \Pi } ( x , y ) { = } \{ d _ { 1 } , d _ { 2 } , . . . , d _ { t } \}$ ，只需证明

$$
S _ { 2 } \left( y , f _ { 2 } \left( x , y \right) \right) { \stackrel { \mathrm { c } } { = } } \mathrm { v i e w } _ { 2 } ^ { \Pi } \left( x , y \right) ,
$$

即证明下面的关系成立：

$$
\bigl ( B , R _ { 2 } ^ { \prime } , \{ E ^ { \prime } ( B F _ { A } ^ { \prime } [ 1 ] ) , . . . , E ^ { \prime } ( B F _ { A } ^ { \prime } [ \omega ] ) \} \bigr ) \stackrel { \scriptscriptstyle \mathrm { c } } { = } \bigl ( B , R _ { 2 } , \{ E ( B F _ { A } [ 1 ] ) , . . . , E ( B F _ { A } [ \omega ] ) \} \bigr )
$$

由于 ${ \boldsymbol { R _ { 2 } ^ { \prime } } }$ 和 $R _ { 2 }$ 分别是 $S _ { 2 }$ 和 Bob生成的随机数，因此$\left\{ R _ { 2 } ^ { \prime } \right\} \overset { \mathrm { ~ c ~ } } { \equiv } \left\{ R _ { 2 } \right\}$ ，又根据Golewasser-Micali 加密算法， $E \big ( B F _ { A } \big [ i \big ] \big )$ 和E'(BF[i])具有随机性，{E(BFA[i]}={E'(BF[i])}，

综上可得：

$$
\left\{ f _ { 1 } ( x , y ) , S _ { 2 } \big ( y , f _ { 2 } ( x , y ) \big ) \right\} \overset { \mathrm { c } } { = } \left\{ \mathrm { o u t p u t } _ { 1 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) , \mathrm { v i e w } _ { 2 } ^ { \mathrm { \scriptscriptstyle T } } ( x , y ) \right\} \ : \circ
$$

定理证毕。

综上，本文基于Goldwasser-Micali同态加密算法构建的安全子集协议在半诚实模型下是安全的，同时，通过使用布隆过滤器，使协议具有较高的效率，并且扩大了协议的适用范围。

# 4 结束语

保密的判断集合间的关系对于现实生活中的实际意义越来越重要，现有的协议大多只能保护一个集合中元素的隐私。为此，本文基于Goldwasser-Micali同态加密算法在半诚实模型下构建了一个的安全子集计算协议，并对协议进行了正确性及安全性证明。协议通过使用布隆过滤器，可判断拥有大量元素或大数域元素的集合间关系，将其映射为较小的数据集合，提升了协议的效率及适用范围。目前的相关研究大多是基于二次剩余等困难问题，不可抵抗量子攻击，随着量子计算机的迅速发展，研究可以抵抗量子攻击的安全子集计算具有重要的意义，将是进一步的研究方向。

# 参考文献：

[1]Yao A C.Protocols for secure computations [C]//Proc of Symposium on Foundations of Computer Science.Washington DC:IEEE Computer Society,1982:160-164.   
[2]Goldreich O,Micali S,Wigderson A.How to play any mental game [C]/Proc of the 19th ACM Symposium on Theory of Computing.New York:ACMPress,1987:218-229.   
[3]Ben-Or M,Goldwasser S,Wigderson A.Completeness theorems for non-cryptographic fault-tolerant distributed computation [C]//Proc of ACM Symposium on Theory of Computing.New York:ACM Press, 1988:1-10.   
[4]Li Shundong,Guo Yimin, Zhou Sufang,et al.Efficient protocols for the general millionaires'problem [J]. Chinese Journal of Electronics,2017, 26 (4):696-702.   
[5]Grigoriev D,Kish L B,Shpilrain V. Yao's millionaires'problem and public-key encryption without computational assumptions [J].Interna tional Journal of Foundations of Computer Science,2017,28 (4): 11.   
[6]秦静，张振峰，冯登国，等．无信息泄漏的比较协议[J].软件学报, 2004,15 (3): 421-427.(Qin Jing, Zhang Zhenfeng,Feng Dengguo,et al. A protocol of comparing information without leaking [J].Journal of Software,2004,15 (3): 421-427.)   
[7]杨波，禹勇，杨中皇．恶意敌手模型下的安全点乘协议[J].计算机 科学与技术,2013,28(1):152-158.(Yang Bo,Yu Yong,Yang Zhong huang.A secure scalar product protocol against malicious adversaries [J].Journal of Computer Science and Technology，2013，28(1): 152-158.)   
[8]Li Shundong,Wu Chunying,Wang Daoshun,et al. Secure multiparty computation of solid geometric problems and their applications [J]. Information Sciences,2014,282:401-413.   
[9]He Feng,Wang Ting.Research and application of secure multi-party computation in several computational geometry problems [C]// Proc of International Conference on Industrial Control and Electronics Engineering.Piscataway,NJ:IEEE Press,2012:1434-1437.   
[10]辛欣，郝林，汤瑜.空间两平行直线间距离的保密计算协议[J].计 算机应用研究,2013,30(5):1530-1532.(Xin Xin,Hao Lin,Tang Yu. Privacy-preserving computational protocol on minimum distance between two three-dimension parallel straight line [J].Application Research of Computers,2013,30(5):1530-1526.)   
[11] Pathak FAN,Pandey S B S.An efficient method for privacy preserving data mining in secure multiparty computation [C]//Proc of Nirma University International Conference on Engineering. Piscataway,NJ: IEEE Press,2013.   
[12] Zhou Sufang，Li Shundong，Dou Jiawei,et al.Efficient secure multiparty subset computation [J]. Security & Communication Networks,2017,2017 (3): 1-11.   
[13]李顺东，周素芳，郭奕昊，等．云环境下集合隐私计算[J].软件学 报,2016,27 (6):1549-1565.(Li Shundong,Zhou Sufang,Guo Yimin, et al. Secure set computing in cloud environment [J].Journal of Software,2016,27(6):1549-1565.)   
[14] Bogdanov D，Niitsoo M，Toft T,et al.High-performance secure multi-party computation for data mining applications [J]. International Journal of Information Security,2012,11 (6): 403-418.   
[15] Goldwasser S,Micali S.Probabilistic encryption $\&$ how to play mental poker keeping secret all partial information [C]//Proc of the14th ACM Symposium on Theory of Computing.New York:ACM Press, 1982: 365-377.   
[16] Debnath S K,Dutta R.Secure and eficient private set intersection cardinality using Bloom filter [C]//Proc of International Information Security Conference.Springer International Publishing,2O15:209-226.   
[17]马敏耀，陈松良，左羽．基于Goldwasser-Micali 加密系统的隐私交 集基数协议研究[J].计算机应用研究,2018,35(9):2748-2751．(Ma Minyao,Chen Song liang,Zuo Yu.Research on private set intersection cardinality protocol based on Goldwasser-Micali encryption system [J].Application Research of Computers,2018,35(9):2748-2751..)   
[18] Heydon A,Najork M.Mercator: a scalable,extensible web crawler [J]. World Wide Web-internet & Web Information Systems,1999,2(4): 219-229.   
[19]孙茂华．安全多方计算及其应用研究[D].北京：北京邮电大学， 2013.(Sun Maohua.Research on secure multi-party comptation and its application[D].Beijing:BeijingUniversityofPostsand Telecommunications,2013.)   
[20]周素芳，窦家维，郭奕旻，等．安全多方向量计算[J].计算机学报， 2017,40(5):1134-1150.(Zhou Sufang,Dou Jiawei,Guo Yimin,et al. Secure multiparty vector computation [J]. Chinese Journal of Computers,2017,40(5):1134-1150.)