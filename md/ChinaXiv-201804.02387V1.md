# 云存储中基于MHT的动态数据完整性验证与恢复方案

李敬伟1，朱命冬1,2

(1．河南工学院 计算机科学与技术系，河南 新乡 453002;2．东北大学 计算机科学与工程学院，沈阳 110006)

摘要：针对云服务器上存储数据完整性验证过程中的高通信开销和动态数据验证问题，提出一种基于Merkle哈希树(MHT)的动态数据完整性验证与恢复方案。首先，基于MHT构建了一种新型分层认证数据结构，将数据块的每个副本块组织成副本子树，以此大幅降低多副本更新验证的通信开销。然后，在数据验证中，融入了对服务器安全索引信息的认证，以此避免服务器攻击。最后，当发现数据损坏时，通过二分查找和 Shamir秘密共享机制来恢复数据。实验结果表明，该方案在验证过程中能有效降低计算和通讯开销，并能够很好地支持数据的动态操作。

关键词：云存储；数据完整性验证；Merkle哈希树；动态数据；数据恢复中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.01.0097

Dynamic data integrity verification and recovery scheme in cloud storage based on MHT

Li Jingwei', Zhu Mingdong1, 2 (1.Dept.ofComputerScience Henan InstituteofTechnology,Xinxiang Henan 453002,China;2.ColegeofComputerScience &Engineering,Northeastern University,Shenyang l1ooo6,China)

Abstract:Forthe issues that the high communication overheadanddynamicdata verification inthe storage dataintegrity verification processonthecloud server,this paper proposedadynamic data integrityverificationand recoveryscheme based on Merkle hashtree (MHT).Firstly,itconstructedanewlayeredauthenticationdata structurebasedonMHT,andorganized each copy block ofthe datablock intoacopy sub-tree,thereby greatly reducing the communication overhead of multi-copy updateverification.Then,itcertifiedtheserversecurityindex informationauthenticationintothedatavalidation,inoderto avoid serverattacks.Finaly,itrecovered thedatabydichotomous discoveryand Shamir'ssecretsharingmechanism whenthe data is corrupted.Theexperimentalresultsshowthat thisschemecan efectivelyreduce thecomputationalandcommunication overhead and can support the dynamic operation of data in the verification process.

Key Words: cloud storage; data integrity verification; Merkle hash tree;dynamic data; data recovery

# 0 引言

云计算是新一代的分布式计算平台，对于大数据的存储和处理提供了很大便利[1。云存储的安全性是云计算主要关心的问题之一，安全性的三个主要方面是机密性、完整性和可用性[2]。存储在云存储服务器(CSP)上的大数据集本质上是动态的，数据更新频繁。因此，使一些公共审计机制等云安全机制支持动态数据具有重要意义[3]。

公共审计机制是用来对外部数据进行完整性验证。凭借可证明数据持有(PDP)和可检索证明(POR)[4]，数据拥有者或第三方审计人员(TPA)可以验证其数据的完整性，而无需检索其数据[5]。现有的公共审计机制已经可以支持对动态更新数据进行验证，例如文献[6]使用了一种基于层级的认证跳表技术(RASL)作为认证数据结构，提出了一种支持动态数据更新验证的PDP方案。但是，可变大小的文件块在其框架中不受支持。文献[7]提出了一种基于BLS签名和Merkle哈希树认证数据结构的方案，可以支持公共审计和数据动态，但其不能抵御服务器伪造认证攻击。文献[8]同样通过基于Merkle哈希树认证数据结构中的辅助认证信息(AAI)来支持这种动态审计。

但是，这些方法仍然存在一些问题。首先，现有的研究缺乏对维护多个副本的动态数据集进行有效公共审计。存储多个副本是远程云存储中提高可靠性和可用性的常用策略[9]。对于高度动态的数据，每次更新都会导致更新每个副本。考虑到当前审计方案中的更新验证具有 $O ( l o g n )$ 通信复杂度，逐个验证这些副本在通信方面将是非常昂贵的。其次，目前的动态公共审计方案由于缺乏块索引认证，容易受到恶意服务器的攻击。

为此，本文提出了一个基于Merkle哈希树(MHT)的多副本动态公共审计方案，通过一个新设计的认证数据结构解决上述问题。本文的主要研究贡献如下：

a）为了解决多副本云存储种数据更新的验证效率问题，提出了一种基于Merkle哈希树的多副本公共审计方案，其中每个数据块的所有副本块被组织成相同的副本子树，以此大幅降低更新验证的通信开销。同时，在基于Merkle哈希树在动态数据公开审计中，融入了对服务器安全索引信息的认证，以此避免服务器攻击。

b）设计了一种能够一次性验证所有副本的验证机制，且在服务器端也可以减少额外的存储开销。

c）当完整性验证失败时，融入了损坏数据块定位和恢复过程，即通过二分查找来定位损坏数据块，通过Shamir秘密共享机制来恢复数据。

# 1 问题描述与分析

# 1.1多副本验证

存储多个副本是云存储服务商的默认设置，将副本存储在不同的服务器，以便用来将用户数据从服务故障中恢复。用户验证多个副本完整性的直接方法是将它们作为单独的文件存储并逐一验证。目前，用于支持副本数据动态修改的最常用技术是构建一种支持更新的认证数据结构(ADS)。对于ADS的存储复杂性为 $\log \left( n \right)$ ， $n$ 为块的总数，当文件很大时其非常大。更重要的是通信复杂性，当每个数据块发生更新时将需要更新每个副本中相应的块[10]，这将造成高通信成本。本文试图用一个新的ADS 解决这个问题，将每个块的所有副本链接在一起。

文献[11]中提出了一个多副本验证方案，命名为MR-PDP，将每个块和所有副本块只关联一个同态线性验证器(HLA)，效率较高。虽然这种方法可以带来很多好处，如服务器端存储成本较低，客户端预处理时间较短，但用第三方审计人员验证时，存在安全性问题。验证过程需要私有的随机数 $r _ { i , j }$ ，如果被泄露，另一方将知道如何计算基于任何副本的原始消息，以及如何基于原始文件块来计算任意副本。更糟的是，如果 $r _ { i , j }$ 被云服务器所知，则云服务器将能够伪造任何副本块的完整性证明。

总而言之，从本文的考虑，多副本验证方案应同时包括以下内容：

a）能够支持公开审计和动态数据更新。使第三方审计人员能够在不需要任何秘密信息的情况下为客户进行常规验证，并允许客户验证数据更新。b）能够支持全面验证。可以一次对所有的副本进行有效的验证，如果任何副本失败，服务器会及时通知。c）能够支持单副本验证。可以对某些特定块的任意副本进行验证，因为验证者可能只想知道对于不重要的数据是否至少有一个副本是完整的。

# 1.2安全的动态公共审计

图1显示了客户/数据拥有者(DO)、云服务提供商(CSP)和第三方审计者(TPA)在公开审计中的关系。其中客户授权TPA审核存储在CSP上的数据，三方之间并不完全信任。

![](images/a71fad156196d243ef9dbec6e027952185471138668d33865f093ce7216e367f.jpg)  
图1云数据公共审计中参与方的关系MHT或RASL等认证数据结构可以支持第三方审计者验

证数据块的内容和更新[12]。对块索引进行验证可以避免恶意服务器根据另一个完整的块和其AAI来伪造证明。其次，对于动态数据的审计，在验证器计算中需要块的本身哈希值，而不是包含块索引的任何哈希值，例如 $H \left( i \right)$ 或 $H \left( \nu \left. \right. i \right)$ ，否则插入/删除操作将导致所有下层块改变。因此，每个验证者都将具有一个哈希值 $H \left( m _ { i } \right)$ 。作为客户验证 $H \left( m _ { i } \right)$ 正确性的唯一方法是通过 ADS，服务器可以用另一个哈希和 AAI来欺骗客户端。换句话说，服务器可以采取任何其他的完整块来代替应该被验证的块，这就影响了完整性验证的结果。

文献[13]提出的RASL方法可以为索引提供认证，这对上述攻击具有抵抗性。其中认证者T被计算为 $T = g ^ { m }$ ， $g$ 是生成者， $m$ 是要审核的消息。但是RASL不能直接应用到支持动态数据的公共审计方案中。如前所述，消息块 $H \left( m _ { i } \right)$ 的哈希值将被用在验证者中以支持动态数据。因此，客户需要通过云服务器的计算来验证。为了实现索引信息的可验证性，叶节点不再存储文件块的哈希值，而是以$f \left( \nu \right) = H \left( l \left( \nu \right) , r \left( \nu \right) , x \left( \nu \right) , f \left( r g t \left( \nu \right) \right) \right)$ 的形式连接多个哈希值。因此，服务器需要发回 $f \left( \nu \right) \operatorname { \pi } H \left( m \right)$ 给客户端进行认证。

RASL中存在一个缺陷，即当一条验证路径上具有多个叶节点。在这种情况下，如果需要验证一个数据库，则服务器不仅需要返回该数据块上的所有三个值，而且还需要计算和传递所有相同路径上数据库的验证值。为此，本文选择Merkle哈希树来构建ADS。

# 2 双线性配对和Merkle哈希树

# 2.1符号定义

文中所涉及的一些符号及其含义描述如表1所示。

表1文中所涉及的符号及含义  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>F</td><td>客户端上传的原始数据文件，存储在CSP中。</td></tr><tr><td>mi</td><td>F 的第i个文件块，总共有n个块。</td></tr><tr><td>F</td><td>文件F 的第j个副本。</td></tr><tr><td>bii</td><td>副本F,的第i个块。</td></tr><tr><td>ri.j</td><td>用于生成副本块bi；的填充消息与原始文件块 m的关系。</td></tr><tr><td>T</td><td>基于m开发的MR-MHT。</td></tr><tr><td>T</td><td>基于mi的T的副本-子树。</td></tr><tr><td>H(m)</td><td></td></tr><tr><td></td><td>消息m的哈希值。</td></tr><tr><td>h(v)</td><td>存储在节点V中来自于从MR-MHTT的</td></tr><tr><td>1(v)</td><td>节点V的层级。</td></tr><tr><td>r(v)</td><td>可以从V到达叶子层中的最大节点数量。</td></tr><tr><td>Oi,j</td><td>的同态标签。</td></tr><tr><td>S</td><td>每块的段数。</td></tr></table></body></html>

<html><body><table><tr><td></td><td>用于RSTT中的所有中间节点的元组</td></tr><tr><td></td><td>{h,l,q,t}。</td></tr><tr><td>sig AUTH</td><td>用于授权TPA的签名。</td></tr><tr><td>Ω</td><td>用作m的辅助认证信息的元组。</td></tr><tr><td>R</td><td>存储在T中根节点上的哈希值。</td></tr><tr><td>(fk,nk,qk,dk)</td><td>Ω中的第k个元组，其中f是哈希值，lk是</td></tr><tr><td rowspan="3"></td><td>节点的层级，qk是层级值，dk指示该节点是左</td></tr><tr><td>子节点还是右子节点。</td></tr><tr><td>用于验证的变量元组。对于成功的验证，在用</td></tr><tr><td rowspan="2">(2k,nk,5k,Sk)</td><td>进行迭代计算之后，λ将成为总文件块的数量，</td></tr><tr><td>7将成为根值R，将成为块索引，将成为 反向块索引，即从右边的块数。</td></tr></table></body></html>

# 2.2双线性配对

双线性配对在用于建立和验证同态验证器的公共审计方案中是必不可少的[14]。假设一个群 $G$ 是一个间隙 Diffie-Hellman(GDH)群，它的质数为 $p$ 。双线性映射是一个构造$e : G { \times } G \to G _ { _ { T } }$ 的映射，其中 $G _ { \scriptscriptstyle T }$ 是具有素数的乘法循环群。一个有用的双线性映射 $e$ 应该具有以下属性：

a）双线性, $\forall m , n \in G \Rightarrow e \Bigl ( m ^ { a } , n ^ { b } \Bigr ) \Rightarrow e \bigl ( m , n \bigr ) ^ { a b } ;$ b）非退化性, $\forall m \in G , m \neq 0 \Rightarrow e \left( m , n \right) \neq 1$ c）可计算性, $e$ 应该是有效可计算的；d）安全性,计算 $G _ { \scriptscriptstyle T }$ 中的离散对数问题是困难的。

# 2.3 Merkle哈希树

Merkle哈希树类似于二叉树，在叶子节点存储数据信息，非叶子节点的值是通过对其叶子节点值进行哈希运算得到，从底层向上层逐步运算，得到根节点值，用来描述数据信息的完整性[15]。每个节点 $N$ 将具有最多两个子节点。MHT $T$ 上的一个节点 $N$ 中的信息被构造如下：对于包含文件块 $m _ { i }$ 的叶节点，节点值计算为 $h _ { i } = H \left( m _ { i } \right)$ ； $N _ { \mathrm { 1 } }$ 和 $N _ { _ 2 }$ 的父节点被构造为$N _ { p } = \{ H ( h _ { 1 } \| h _ { 2 } ) \}$ 。叶子节点 $m _ { i }$ 的辅助认证信息 $\Omega _ { i }$ 是其上级节点选择的一组哈希值，这样就可以通过 $\left( m _ { i } , \Omega _ { i } \right)$ 计算根值 $R$ 。MHT认证数据的结构如图2所示。

![](images/32a7e786da4d43df96749f4e4ffdd431868fc55b39ef238926311ca1d26127df.jpg)  
图2MHT认证数据的结构

# 3 提出的多副本动态数据验证方案

# 3.1多副本Merkle 哈希树结构

多副本Merkle哈希树是一种新颖的认证数据结构，专为数据更新以及对块索引进行验证而设计。基于具有3个块和1个副本文件构建的一个多副本MHT的示例如图3所示。

![](images/fe0282917efd5733720290545cce52b7db555f8bdbbe33ce9c5bbaf23e86fc84.jpg)  
图3一个多副本 MHT 的例子

多副本MHT与传统MHT的差异如下：

a）存储在叶节点中的值是所存储的副本块的哈希值。在多副本 MHT中，叶节点代表副本块 $b _ { i , j }$ ，即第 $i$ 个文件块的第 $j$ 个副本。

b)存储在非叶节点 $\nu$ 中的值是由其子节点的哈希值和另外两个索引 $l \left( \nu \right)$ 和 $r \big ( \nu \big )$ 计算得来的。 $l { \left( \nu \right) }$ 是节点 $\nu$ 的层级，$r \big ( \nu \big )$ 是 $\nu$ 可以到达的叶子节点的最大数目。这些层级是从上到下的顺序定义的，根节点 $R$ 的层级定义为0，其子节点的层级定义为1。叶子节点中存储的值为$H \left( 1 \| l \left( b _ { i , j } \right) \| { \cal H } \left( b _ { i , j } \right) \right)$ ；在每个非叶节点中的值为$H \left( r \left\| l \right\| h _ { _ { l e f t } } \left\| h _ { _ { r i g h t } } \right) \right.$ ，其中 $h _ { \mathit { l e f t } }$ 和 $h _ { { r i g h t } }$ 分别表示存储在其左子节点和右子节点中的值。在图3中，根据本文的定义，$l \left( b _ { i , j } \right)$ (对于所有叶节点)是3， $r \left( b _ { i , j } \right) = 1$ 。例如， $h _ { d }$ 的计算公式如下：

$$
\begin{array} { l } { h _ { d } = H \left( r \left( d \right) \left. l \left( d \right) \right. h \left( b _ { 1 , 1 } \right) \left. h \left( b _ { 1 , 2 } \right) \right) } \\ { \qquad = H \left( 2 \left. 3 \right. h \left( b _ { 1 , 1 } \right) \right. h \left( b _ { 1 , 2 } \right) \right) } \end{array}
$$

且

$$
h { \big ( } b _ { 1 , 2 } { \big ) } = H { \big ( } 1 \| 4 \| H { \big ( } b _ { 1 , 2 } { \big ) } { \big ) }
$$

$h _ { b } = H ( 6 \| 1 \| h _ { 1 } \| h _ { 2 } )$ 等。

c）其中的 AAI $V _ { i , j }$ 与 MHT 不同。每个节点上包含了一组信息 $\{ h , l , q , d \}$ 。 $h$ 为存储在该节点上的哈希值， $l$ 为该节点的层级， $q$ 为从该节点可到达叶节点的最大数量， $d$ 用来指示该节点到根节点 $R$ 是向右(0)或向左(1)。例如，在图3中，对于副本块 $b _ { 2 , 1 }$ ， $\Omega _ { 2 , 1 }$ （204号 被定义为$\left\{ \begin{array} { l l } { \big ( h \big ( b _ { 2 , 1 } \big ) , 4 , 1 , 0 \big ) , \big ( h \big ( b _ { 2 , 2 } \big ) , 4 , 1 , 0 \big ) , } \\ { \big ( h \big ( b _ { 2 , 3 } \big ) , 3 , 1 , 0 \big ) , \big ( h _ { 2 } , 1 , 6 , 0 \big ) } \end{array} \right\}$ 它的验证路径为$\left\{ h \big ( b _ { 2 , 1 } \big ) , h \big ( e \big ) , h \big ( 2 \big ) , R \right\} \circ$ （204号

d)一个文件块的所有副本被组织成一个相同结构的副本子树(RST)。子树中的叶节点数量为总副本数量 $c$ 。副本块是独立处理的，每个副本块都有自己的验证器。每个RST的根，表示为 $h _ { \scriptscriptstyle i }$ ，将在多副本验证和更新验证中发挥重要作用。本文使用$\Omega _ { i }$ 来表示 $h _ { \scriptscriptstyle i }$ 的 AAI。另外，本文将 $\Gamma _ { i }$ 定义为每个 RST中所有中间节点的元组 $\{ h , l , q , t \}$ 的集合，其中 $t$ 是节点的序号。由于副本数量较少(小于10)，为了简化描述，本文假设 $T _ { i }$ 结构存储在客户端和TPA端，这适用于每个RST，并且只占用可忽略的存储量。在这种情况下，客户端可以计算出 $\Gamma _ { i }$ ，因此可以根据 $h \left( b _ { i , j } \right)$ 和 $l \left( b _ { i , j } \right)$ 来计算 $\Gamma _ { i }$ ，而不需要从服务器请求 $\Gamma _ { i }$ （20

# 3.2 初始化设置过程

用户和云服务器将首先建立通用参数，包括双线性映射$e : G { \times } G \to G _ { _ { T } }$ 和一个密码哈希函数 $H$ [16]。

产生密钥操作 $K e y G e n { \left( 1 ^ { k } \right) }$ ：客户端生成一个秘密值$\alpha \in Z _ { p }$ 和一个 $G$ 的生成器 $g$ ，然后计算 $\nu = g ^ { a }$ ，其中 $\nu$ 、（204号 $g$ 是公钥， $\alpha$ 是密钥。另一个签名密钥对 $\{ s p k , s s k \}$ 是根据指定的签名方案来选择的，其签名算法被表示为 $S i g ( )$ 。该算法输出 $\{ s s k , \alpha \}$ 作为密钥 $s k$ ， $\{ s p k , \nu , g \}$ 作为公钥 $p k$ 。

文件预处理操作 $F i l e P r e P r o c ( F , s k , c )$ ，其分为以下三个步骤：

a）为了将数据集存储在云服务器上，客户端将首先根据原始文件制作 $c$ 个副本。为了能够验证这些副本，它们应该是彼此不同的，否则服务器可能会用正确的证据来回应挑战，从而欺骗客户，但实际上只存储一个副本。原始文件为$F = \left\{ m _ { 1 } , m _ { 2 } , . . . , m _ { n } \right\}$ ，本文将其第 $j$ 个副本文件表示为$\tilde { F } _ { j } = \left\{ b _ { 1 , j } , b _ { 2 , j } , . . . , b _ { n , j } \right\}$ ， $j \in \left[ 1 , c \right]$ 。副本中的块 $b _ { i , j }$ 从 $m _ { i }$ （204转换而来，并且转换是可逆的，即客户可以通过任何副本 $\tilde { F } _ { _ { j } }$ 来恢复原始文件 $F$ 。例如，可以选择 $n$ 个伪随机函数 $\psi$ 来计算随机值 $r _ { i , j } = \psi \big ( j \| i \big )$ ，然后输出 $b _ { i , j } = m _ { i } + r _ { i , j }$ 。

b）客户端基于 $b _ { i , j }$ 构造一个多副本 MHT，计算根值 $R$ ，并用 $s s k$ 计算其签名 $s i g$ 。c）对于每个副本块 $b _ { i , j }$ ，客户端将计算一个认证者$\sigma _ { i , j } = \left( H \left( b _ { i , j } \right) \mu ^ { b _ { i , j } } \right) ^ { \alpha } \circ$ （20号

最后，初始化过程输出 $\left\{ b _ { i , j } , \sigma _ { i , j } , s i g \right\}$ ，并上传到云服务器。

# 3.3数据更新和验证过程

数据动态更新类型有全块插入(I)，删除(D)和修改 $( \mathbf { M } )$ 。在多副本场景中，当需要更新块 $m _ { i }$ 时，也需要以相同的方式更新其所有对应的副本块 $b _ { i , j }$ 以保持一致性。同时客户端将计算新的副本块 $b _ { i , j } ^ { \prime }$ ，然后将它们与更新类型(I、D或M)一起发送到服务器。

数据更新操作PerformUpdate(UpdateReq):

服务器将UpdateReq解析为 $\left\{ { T y p e , i , \left\{ b _ { i , j } ^ { \prime } \right\} } \right\}$ 。并根据更新请求对文件块、索引和ADS 进行更新。请注意， $\Omega _ { i }$ 中非叶节点中的值在更新过程后保持不变。

对于插入和删除，相邻RST中的所有叶节点的层级也被改变，其中插入操作时 $+ 1$ ，删除操作时-1。

例如在图4中，随着 $\left\{ b _ { 2 , j } ^ { \prime } \right\}$ 的插入， $\left\{ b _ { 2 , j } \right\}$ 的层级增加了1，这将导致所有 $\left\{ h \big ( b _ { 2 , j } \big ) \right\}$ 的改变 ；如果再将插入的块$\left\{ b _ { 2 , j } \right\}$ 删除，旧的 $\left\{ b _ { 2 , j } ^ { \prime } \right\}$ 的层级减少了1。

![](images/b04f473e287bffd527da32a2f54c87a1180b40971b8d698f62f0e8f34c131e68.jpg)  
图4在第2个副本前插入块。

对于插入和修改操作，服务器计算$P _ { u p d a t e } = \left\{ \left\{ h { { \left( b _ { i , j } \right) } \right\} } , \Omega _ { i } , R ^ { \prime } , s i g \right\}$ 并将其返回给客户端。对于删除，服务器将需要另外发送 $h ^ { \prime } \big ( b _ { i , j } \big )$

验证更新操作 VerifyUpdate $( p k , P _ { u p d a t e } )$

为了验证这个更新，客户端首先需要解析 $P _ { u p d a t e }$ 。令 $\Omega _ { i }$ 中的 $\pi$ 元组为 $\left( f _ { k } , l _ { k } , q _ { k } , d _ { k } \right)$ ，对于每个节点 $N _ { \boldsymbol { k } }$ 按降序排列，即 $l _ { 1 } = l \left( h _ { i } \right) , . . . , l _ { \pi - 1 } = 2 , l _ { \pi } = 1$ 。与先前定义有一点不同， $q _ { k }$ 为可以从 $N _ { \boldsymbol { k } }$ 到达的 RST 根的最大数目，而不是叶节点。由于RST 的结构对于客户是已知的，将能够分别计算 $h _ { \scriptscriptstyle i }$ 和$h _ { \mathrm { i } } ^ { \prime }$ ，并根据 $h \left( b _ { i , j } \right)$ (从服务器获得)和 $h ^ { \prime } \big ( b _ { i , j } \big )$ 计算 $T _ { i }$ 的新根和旧根。

a）对于在 $\Omega _ { i }$ 中包含节点 $N _ { \boldsymbol { k } }$ 的验证路径上的节点，客户端将首先迭代计算元组 $\left( \lambda _ { k } , \eta _ { k } , \xi _ { k } , \zeta _ { k } \right)$ ，其中 $k = 1 , . . . , \pi$ ：如 果 $d _ { k } = 1 \colon \lambda _ { k } = q _ { k - 1 } + \lambda _ { k - 1 }$ $\eta _ { k } = H \left( \lambda _ { k } \parallel l _ { k } \parallel f _ { k } \parallel \eta _ { k - 1 } \right) \quad \textrm { , } \quad \xi _ { k } = \xi _ { k - 1 } + q _ { k }$ 和$\zeta _ { k } = \xi _ { k - 1 }$ 。或者：如果 $d _ { k } = 0 \colon \lambda _ { k } = q _ { k - 1 } + \lambda _ { k - 1 }$ 、$\eta _ { k } = H \left( \lambda _ { k } \parallel l _ { k } \parallel \eta _ { k - 1 } \parallel f _ { k } \right) \qquad , \qquad \xi _ { k } = \xi _ { k - 1 }$ 和（20 $\zeta _ { k } = \xi _ { k - 1 } + q _ { k }$ 。其中， $\begin{array} { r } { \eta _ { \mathrm { 0 } } = h \big ( b _ { i , j } \big ) , \lambda _ { \mathrm { 1 } } = 1 , \xi _ { \mathrm { 0 } } = 0 } \end{array}$ 和$\zeta _ { 0 } = 0$ 。

那么在得到 $\left\{ \lambda _ { \pi } , \eta _ { \pi } , \xi _ { \pi } , \zeta _ { \pi } \right\}$ 后，客户端将用 $s i g$ 验证$R = \eta _ { \pi }$ ，并且验证是否 $\xi _ { \pi } = i - 1$ 和 $\zeta _ { \pi } = n - i$ 能够同时成立。如果三个值都通过了这个认证，那么 $\Omega _ { i }$ (也是 $b _ { i , j }$ )和它的索引 $i$ 的真实性可以被证实。

b)对于删除操作,客户需要验证 $h ^ { \prime } \big ( b _ { i , j } \big )$ 。注意， $h ^ { \prime } \big ( b _ { i , j } \big )$ 代表相同的块和副本，其RST 的根被存储作为 $\Omega _ { i }$ 中的第一个元组。客户端有足够的信息通过 $h \left( b _ { i , j } \right)$ 、 $\Omega _ { i }$ 和 $R$ 来验证$h ^ { \prime } \big ( b _ { i , j } \big )$ 。 对于插入操作， $h \big ( b _ { i , j } \big )$ 已经与 $\Omega _ { i }$ 一起验证了，客户可以安全地计算新的 $h _ { i _ { - } n e w }$ ，而不需要额外的验证。

c)根据 $R S T$ 结构，客户端将根据 $h ^ { \prime } \big ( b _ { i , j } \big )$ 计算 $h _ { \mathrm { i } } ^ { \prime }$ ，然后根据 $\Omega _ { i }$ 和 $h _ { \mathrm { i } } ^ { \prime }$ 计算 $R _ { n e w }$ ，并将 $R _ { n e w }$ 与 $R$ 进行比较。

以上验证成功后，客户端将更新块的数量 $n$ ，并计算同态标签 $\sigma _ { i , j } ^ { \prime } ( b _ { i , j } ^ { \prime }$ 的验证者)，存储在服务器上。

图5显示了数据更新验证的过程，其中分别包含了全块插入、删除和修改操作时的更新验证。

插入操作客户端 存储服务器基于更新块 $m _ { i }$ 计算新副本 $\left\{ I , i , \left\{ b _ { i , j } ^ { \prime } \right\} \right\}$ （204号  
块 $b _ { i , j } ^ { \prime } ,$ 并发送更新请求。用 $b _ { i , . } ^ { \prime }$ 创建一个新子树 $T _ { i }$   
基于h(bi,)和Ω计算h，用 {h(b.)）).,sig} 更新叶节点的层级  
h和Ω计算R，用 $R$ 验证sig。$\sigma _ { i , j } ^ { \prime }$ sig' 更新 $\sigma _ { i , j }$ 为 $\sigma _ { i , j } ^ { \prime }$ ，更新  
如果验证成功，计算 $\sigma _ { i , j } ^ { \prime }$ ，且生成新签名sig'。 sig为sig'。

# (a)数据块插入的更新验证过程

![](images/a004a891bc3e9b9eb01c79b23be6e4910e155a349a66fd57d1de740c97fb7372.jpg)

# (b)数据块修改的更新验证过程

![](images/5705d239b2305faa1b142bf06cb4d7c7b0ecfdee7303db90288241486a7a24f2.jpg)  
(c)数据块删除的更新验证过程图5数据块的更新和验证过程

# 3.4抵御服务器攻击

本文验证方案中的标签数据都是通过密码哈希函数 $H$ 来构建。为此，云存储中会存在以下类型的攻击：

a)重放攻击。当用户更新一个数据块后，会相应的计算一个标签 $H ( i )$ 。如果存在一个恶意的存储服务器，其私自更改数据，并当审计者审计数据完整性时，将之前的标签 $H ( i )$ 提交给审计者进行验证。

为此，本文在数据完整性验证之前，先通过 MHT 和每个副本的初始向量 $\nu _ { i } = \left\{ h ( b _ { i , 1 } ) , h ( b _ { i , 2 } ) , \cdots , h ( b _ { i , j } ) \right\}$ ，分别计算 $h \left( b _ { i , j } \right)$ 和 $h ^ { \prime } \big ( b _ { i , j } \big )$ 来计算 $T _ { i }$ 的新根 $R _ { n e w }$ 和旧根，然后计算标签 $\sigma _ { i , j } ^ { \prime }$ 来对标签进行了验证。

b)伪造攻击。在传统验证方案中，对于每个副本块 $b _ { i , j }$ ，客户端将计算一个同态标签 $\sigma _ { i , j }$ 。那么，此时恶意存储服务器能够伪造一个标签，例如 $\sigma _ { i , j } = \left( H \left( b _ { i , j } \right) \mu ^ { b _ { i , j } } \right) ^ { \alpha }$ 和$\sigma _ { k , j } = \left( H \left( b _ { k , j } \right) \mu ^ { b _ { k , j } } \right) ^ { \alpha }$ 分别为两个同态标签。恶意服务器可以根据同态标签的运算规则，制造一个假标签（20 $\sigma ^ { \prime } = \sigma _ { i , j } \cdot \sigma _ { k , j } = \left( H \left( b _ { i , j } \right) \cdot H \left( b _ { k , j } \right) \cdot \mu ^ { b _ { i , j } + b _ { k , j } } \right) ^ { \alpha } ,$

同样，为了抵抗伪造攻击，本文对向量$\nu _ { i } = \left\{ h ( b _ { i , 1 } ) , h ( b _ { i , 2 } ) , \cdots , h ( b _ { i , j } ) \right\}$ 进行了验证，结合索引信息就可以知道数据库的位置。为此，伪造签名不能通过审计者检查。

# 3.5多副本公共审计的挑战和验证过程

在本文的自顶向下的分层设置中，验证者将需要$H \left( b _ { i , j } \right)$ 来验证审计方程，因为它不存储在多副本 MHT 中。这里本文讨论如何一次性对一组副本块进行验证。

a)产生挑战操作GenChallenge $( A c c , p k , s i g _ { A U T H } )$ ：第三方审计员TPA以给定准确度 $A c c$ 生成挑战消息，并发送授权。挑战信息是 $\left\{ s i g _ { _ { A U T H } } , i , \nu _ { i , j } \right\} _ { i \in I }$ ，其中 $s i g _ { _ { A U T H } }$ 用于授权， $I$ 是为验证而选择的随机索引集合， $\nu _ { i , j }$ 是用于 $b _ { i , j }$ 的集成的随机数。

b)产生证据操作GenProof $( p k , F , \Phi , c h a l )$ ：云服务器将首先验证 $s i g _ { A U T H }$ 。那么对于每个副本，它将计算（204号 $\textstyle \sigma _ { j } = \prod _ { i \in I } \sigma _ { i , j } ^ { \nu _ { i , j } }$ 和 $\mu _ { j } = \sum _ { j } \nu _ { i , j } b _ { i , j }$ ，并发送$\left\{ u _ { j } , \sigma _ { j } , \left\{ H \left( b _ { i , j } \right) , h \left( b _ { i , j } \right) , \Omega _ { i } \right\} _ { i \in I } , s i g \right\}$ 到 TPA。

c)验证操作Verify $( p k , P )$ ：由于验证者知道 RST 的结构，所以它将用 $\left\{ h \left( b _ { i , j } \right) , \Omega _ { i } \right\}$ 计算 $R$ ，并且对第 $i$ 个选择的块验证 $s i g$ 。此外，还需要通过验证是否$h \left( b _ { i , j } \right) = H \left( 1 \| l \left( b _ { i , j } \right) \| H \left( b _ { i , j } \right) \right)$ 成立来验证 $H \left( b _ { i , j } \right)$ 的真实性，其中可以从 $\Omega _ { i }$ 中第一个节点层级的 $l \left( h _ { i } \right)$ 推断出$l \left( b _ { i , j } \right)$ 。例如，在图3中，如果设置复制品数量 $c = 3$ ，那么$l \left( h _ { \mathrm { 1 } } \right) = 2 \mathrm { ( } h _ { \mathrm { 1 } }$ 是 $\Omega _ { 2 }$ 中的第一个节点)， $l \left( h _ { 2 } \right) = 2$ ，此时可以很容易地推导出 $l \left( b _ { 2 , 1 } \right) = 4 \mathrm { ~ , ~ } l \left( b _ { 2 , 2 } \right) = 4 \mathrm { ~ \# ~ } l \left( b _ { 2 , 3 } \right)$ $l \left( b _ { 2 , 3 } \right) = 3$ 。如果这个验证通过，TPA 将认为检索到的 $H \left( b _ { i , j } \right)$ 是真实的,那么它可以通过验证以下等式来验证 $c$ 个复制品：

$$
\begin{array} { r } { e \big ( \sigma _ { j } , g \big ) = e \Big ( \prod _ { i } H \big ( b _ { i , j } \big ) ^ { \nu _ { i , j } } \mu ^ { \mu _ { j } } , \nu \Big ) , j \in \left[ 1 , c \right] \circ } \end{array}
$$

如果这些等式成立，则验证将输出“接受”，否则输出“拒绝”。

# 3.6安全性分析

本节对本文方法的安全性进行证明。本文方案的安全性主要是基于散列函数的抗碰撞性，双线性Diffie-Hellman问题的难度，以及所用签名方案的不可伪造性。下面对本文方案中数据更新认证的安全性假设进行证明。

假设：如果在服务器执行更新请求 $\left\{ { T y p e , i , \left\{ b _ { i , j } ^ { \prime } \right\} } \right\}$ 中，新数据内容或索引有任何错误，那么客户端验证将失败。

证明服务器返回 $R S T$ 根 $h _ { \scriptscriptstyle i }$ 和它的 $A A I \ \Omega _ { i }$ ，并判断是否正确，否则 $R$ 的验证将失败。

对于插入和修改操作，如果 $b _ { i , j } ^ { \prime }$ 被错误更新，那么由于散列函数 $H$ 的抗碰撞性，那么 $h _ { \mathrm { i } } ^ { \prime }$ 和 $R ^ { \prime }$ 将会被错误地计算。根据MHT的性质， $\Omega _ { i }$ 在整个更新期间内保持相同。由于客户有正确的 $b _ { i , j } ^ { \prime }$ 和 $\Omega _ { i }$ ,可以计算正确的 $h _ { \mathrm { i } } ^ { \prime }$ 和 $R ^ { \prime }$ 。为此客户端的值 $h _ { \scriptscriptstyle i } ^ { \prime }$ 和 $R ^ { \prime }$ 与反馈值不同，所以验证会失败。

对于删除操作，一旦此更新中有任何错误,返回的 $h \left( b _ { i , j } ^ { \prime } \right)$ 将不正确。由于 $h \left( b _ { i , j } ^ { \prime } \right)$ 包含在 $\Omega \big ( b _ { i , j } \big )$ 中，如果 $h \left( b _ { i , j } ^ { \prime } \right)$ 不正确，客户将能识别异常。

因此，通过本文的验证方案，客户端将能够检测到更新中由于意外或不诚实行为而导致的任何故障。

# 4 损坏定位与数据恢复

当发生数据损坏时，需要通过其他数据来进行数据恢复。在完整性审计中，如果审计结果为损坏，则需要对数据进行恢复。此时，用户向CSP发送定位请求信息，CSP通过二分查找的方式来定位损坏数据块的位置。在找到损坏数据块的位置后，只要 $j$ 个副本中有对应的数据块没有被损坏，则可以通过Shamir 秘密共享机制来进行恢复。假设，数据块副本 $\tilde { F } _ { j }$ 中存在数据损坏，数据恢复的流程如下描述：

a）用户向CSP发送数据恢复请求。

b)CCS定位损坏数据，并通过完整性验证检测出对应的且完整的数据块b.,b. $b _ { r _ { 1 } , j } , b _ { r _ { 2 } , j } , . . . , b _ { r _ { k } , j }$ brk,j，并将其发送给用户。

c）用户根据Shamir秘密共享机制，在本地搜索出对应的

Shamir 参数 $x _ { r _ { 1 } } , x _ { r 2 } , . . . , x _ { r _ { k } }$

d）用户对每个 Shamir 参数计算Lagrange 插值多项式：$L _ { \iota } ( 0 ) = \prod _ { r _ { 1 } \leq l \leq r _ { k } , t \neq l } \frac { - x _ { t } } { x _ { l } - x _ { t } }$ 从而可以得到原始数据块$m _ { j } = \sum _ { l = r _ { 1 } } ^ { r _ { k } } L _ { l } ( 0 ) b _ { l , j } \circ$ （20

e）用户随机选择 $a _ { k - 1 } , . . . , a _ { 1 } \in Z _ { l }$ ，并从 $\{ x _ { 1 } , x _ { 2 } , . . . , x _ { n } \}$ 中选择 $x _ { i }$ ，用来重新计算数据块 $m _ { j }$ 的第 $i$ 个副本$b _ { i , j } = a _ { k - 1 } x _ { i } ^ { k - 1 } + \cdots + a _ { 1 } x _ { i } + a _ { 0 j }$ ， $a _ { 0 j } = m _ { j }$ 。并将其发送给CSP替换掉遭受损坏的数据块。

# 5 实验及分析

# 5.1实验环境

本文构建一个云计算环境用来进行实验。每个计算节点上安装了Linux 操作系统。在虚拟化数据中心安装Hadoop 以方便实现MapReduce 编程模型和分布式文件系统[17]。此外，还安装了OpenStack开源云平台、负责全局管理、资源调度、任务分配以及与用户的交互。云平台共具有36个CPU核心，32GBRAM和1TB存储的虚拟机。

# 5.2性能评估

将本文提出的基于多副本MHT的数据验证方法(MR-MHT)与文献[7]提出的基于BLS签名和MHT的动态数据验证方案(BLS-MHT)，在更新验证过程的通信和存储成本方面进行比较。其中，BLS-MHT是一种具有独立索引副本的动态公众审计的方案。使用1GB随机生成的数据集进行测试，副本为$b _ { i , j } = m _ { i , j } + r _ { i , j }$ 。BLS 参数选择为80位，即 $G$ 的阶数长度为160位。另外，为了简化过程，设定每块的扇区数为 $s = 1$ 和 $s = 1 0$ 两种情况。

首先，本文测试了不同副本数量 $c$ 和块大小 $s$ 值下数据修改、插入和删除操作的数据传输开销，结果如图6所示。可以看出，BLS-MHT的数据传输开销将随着数据副本数量的增加而迅速增加。对于块插入和修改，需要上传新的数据块。因此，总传输开销会随着的增加而增加。但MR-MHT的数据传输开销要显著小于BLS-MHT。

在删除操作中，由于没有数据上传过程，所以在不同的 $s$ 值下，两种方法的总传输开销保持不变。无论哪种情况，与BLS-MHT相比，MR-MHT中更新验证的传输开销始终具有显著优势。

![](images/1f740a98a5be5dee35f197f2a145fbeade1b361232dc8acc98cd1f65523e1556.jpg)  
图6不同 $s$ 时一个块验证更新的总通信

然后，对于动态完整性数据审计的存储开销和通信开销进分析。虽然认证者总数保持不变，但本文中只有一个MHT，而不是BLS-MHT中的 $c$ 个MHT。图7给出了 $s = 1 0$ 时，不同副本数量下，在服务器端的额外存储开销，以支持公共审计和数据动态更新。可以看出，当存在多个副本时，MR-MHT的额外存储成本会大大降低。

图8给出了 $s = 1 0$ 时，多副本验证的通信开销。可以看到，MR-MHT方案优于BLS-MHT。另外，随着副本数量的增长，MR-MHT中用于验证所有副本的通信开销与验证单个副本相当，而 BLS-MHT的开销则成倍增长。例如，当 $c = 5$ 时，使用MR-MHT验证所有5个副本的通信量比仅仅验证1个副本（ $c = 1$ 多 $27 \%$ ，而BLS-MHT 却多了 $3 9 0 \%$ 。因此，MR-MHT方案不仅对于动态数据的验证有效，而且在进行多次副本更新时也具有良好效果。

![](images/14f69c29683314c64ff2aaa475059aa0032862d32857060ad11101473b2ab555.jpg)  
图7服务器端的存储开销。

![](images/cbffef1186a4f008299b19766e933a0ff09319693b4af246a60496273bbb3336.jpg)  
图8审计所有副本的通信开销。

从这些分析和实验结果可以看出，MR-MHT方案在审计具有多个副本的云存储方面具有显著的优势。公开审计的执行不受数据内容的影响。因此，文件块大小， $s$ 值和副本数量是影响整体性能的主要因素。

# 6 结束语

本文提出了一种基于多副本 MHT 的新型公共审计方案(MR-MHT)。引入了一种基于MHT的新型认证数据结构，树中节点的层级值以自顶向下的顺序生成，并将数据块的所有副本块组织成相同的副本子树。因此，该方案可以同时支持完全动态的数据更新、块索引验证和多个副本的高效验证。理论分析和实验结果表明，与现有的完整性验证方案相比，本文MR-MHT方案能够实现对具有多个副本的云数据集进行完整性验证，具有更少的通信和存储开销。

# 参考文献：

[1] 李谢华，刘婷，周茂仁.云存储中基于多授权机构可撤销的 ABE 访问 控制方法[J].计算机应用研究,2017,34(3):897-902.(LiXiehua,Liu Ting,Zhou Maoren.Multi-authority and revocable ABE scheme in cloud storage [J].Application Research of Computers,2017,34(3): 897-902.)   
[2] 薛矛，薛巍，舒继武，等．一种云存储环境下的安全存储系统[J].计 算机学报,2015,38 (5):987-998.(Xue Mao,Xue Hao,Shu Jiwu,et al.A secure storage system over cloud storage environment [J]. Chinese Journal of Computers,2015,38 (5): 987-998.)   
[3] 何凯，黄传河，王小毛，等．云存储中数据完整性的聚合盲审计方法 [J].通信学报,2015,36(10):119-132.(He Kai,Huang Chuanhe,Wang Xiaomao,et al.Aggregated privacy-preserving auditing for cloud data integrity[J]. Journal on Communications,2015,36(10):119-132.)   
[4]Dara U S, Chandra M S. Integrity verification in multiple cloud storage, using cooperative PDP method [J]. International Journal of Engineering Trends& Technology,2013,4(9):132-138.   
[5]李明富，陈立伟．一种基于身份代理重加密的云数据共享方案[J].湘 潭大学自然科学学报，2017,39(3):75-79.(Li Mingfu,Chen Liwei.A secure cloud data sharing scheme from identity-based proxy re-encryption [J].Natural Science Journal of Xiangtan University,2017,39 (3): 75-79.)   
[6]Erway C,Küpcu A,Papamanthou C,et al.Dynamic provable data possession [J].ACM Trans on Information& System Security,2015,17(4): 15-22.   
[7]Wang Qian,Wang Cong,Ren Kui,et al.Enabling public auditability and

data dynamics for storage security in cloud computing[J].IEEE Trans on Parallel & Distributed Systems,2011,22(5): 847-859.

[8]Liu Chang,Chen Jinjin, Yang Laurence T,et al.Authorized public auditing of dynamic big data storage on cloud with efficient verifiable fine-grained updates [J].IEEE Trans on Parallel & Distributed Systems,2014,25(9): 2234-2244.

[9] 田晖，陈羽翔，黄永峰，等．基于 Shamir 秘密共享的云端多副本审计 [J]．华中科技大学学报：自然科学版,2016,44(3):77-82.(Tian Hui, Chen Yuxiang,Huang Yongfeng,et al.Multiple-replica auditing in clouds using Shamir secret sharing [J].Journal ofHuazhong University of Science and Technology: Nature Science Edition,2016,44 (3): 77-82.)

[10]查雅行，罗守山，卞建超，等．基于多分支认证树的多用户多副本数据 持有性证明方案[J].通信学报,2015,36(11):80-91.(Cha Yahang,Luo Shoushan,Bian Jianchao,et al.Multiuser and multiple-replica provable data possession scheme based on multi-branch authentication tree [J]. Journal on Communications,2015,36(11): 80-91.)

[11] Curtmola R,Khan O,Burns R,et al.MR-PDP:multiple-replica provable data possession [C]// Proc of International Conference on Distributed Computing Systems.Piscataway: IEEE Press,20o8:411-420.

[12]KachkeevA,Esiner E,KipcüA,et al.Energy efficiency in secure and dynamic cloud storage [C]// Proc of European Conference on Energy Efficiency in Large Scale Distributed Systems.Berlin: Springer,2013:125- 130.

[13]LiLimin,Yang Yahui,Wu Zhonghai.FMR-PDP:flexible multiple-replica provable data possession in cloud storage [C]// Computersand Communications.:Piscataway,NJ:IEEE Press,2017:1115-1121.

[14]沈丽敏，张福泰，孙银霞．对一种无双线性配对的无证书签密方案的安 全性分析 [J].密码学报,2014,1(2):146-154.(Shen Limin,Zhang Futai, Sun Yinxia.Security analysis of a certificateless signcryption scheme without bilinear pairing[J].Journal of Cryptologic Reseatch,2014,1 (2): 146-154. )

[15] Kim SH,Kim Y,Kwon O,et al.Fully Batch processing enabled memory integrity verification algorithm based on Merkle tree [C]// Proc of International Workshop on Information Security Applications.Berlin: Springer,2015:386-398.

[16]周彦伟，杨波，张文政．不使用双线性映射的无证书签密方案的安全性分析及改进[J].计算机学报，2016,39(6):1257-1266.(Zhou Yanwei,Yang Bo,Zhang Wenzheng.Security analysis and improvement ofcertificateless signcryption scheme without bilinear pairing [J].ChineseJournal of Computers,2016,39(6): 1257-1266.)

[17]刘继华，强彦．基于Hadoop 分布式计算平台的磁流体动力学模型仿真 研究[J].计算机应用研究,2017,34(5):1353-1357.(Liu Jihua,Qiang Yan.Security analysis and simulation of magneto hydro dynamic model based on Hadoop distributed computing platform [J].Application Research of Computers,2017,34 (5): 1353-1357.)