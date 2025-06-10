# 高效的可撤销SM9标识签名算法

张博鑫¹，耿生玲²，秦宝东1

(1．西安邮电大学 网络空间安全学院，西安 710121;2．青海师范学院 计算机学院，西宁 810008)

摘要：SM9-IBS是中国于2016年公布的一种标识签名算法行业标准。标识签名算法虽然降低了系统管理用户公钥的复杂性，但是却存在密钥撤销的难题。此外，SM9的特殊结构使得已有技术无法完全适用。为此，提出了一种可撤销SM9标识签名算法，可快速实现对用户签名权限的撤销和更新操作。该算法引入一棵完全子树，密钥中心借助该树为每个合法用户生成临时签名密钥，只有使用该密钥生成的签名才可以通过签名验证。在安全性方面，该算法在随机预言机模型中，被证明在适应性选择消息和标识攻击模型下满足存在性不可伪造。在效率方面，该方案在密钥更新阶段当系统用户数量较大、被撤销用户数量较少时，密钥中心更新用户签名密钥的时间开销远小于 Boneh等人的更新技术。

关键词：标识密码系统；SM9签名算法；密钥撤销；完全子树 中图分类号：TP309 doi:10.19734/j.issn.1001-3695.2022.02.0073

Efficient revocable SM9 identity-based signature algorithm

Zhang Boxin1, Geng Shengling², Qin Baodongl† (1.SchoolofCyberspace Security,Xi'an UniversityofPosts&Telecommunications,Xi'an710l21,China;2.Schoolof Computer,Qinghai Normal University,Xining 8100o8,China)

Abstract:SM9-IBS isanindustrystandard for identity-based signature (IBS)algorithms isuedbyChina in2O16.Although the IBS algorithms can bereduce the complexity of management ofuser keys,theyhave the problem ofkey revocation.In addition,theexisting technologiesarenotfullapplicableto SM9-IBS due to itsspecial algebraic structureofusers’secret keys.Therefore,thispaperproposesaneficientrevocableSM9 identity-basedsignature (shortedasCS-SM9-RIBS)algorithm, which can quicklyrevoke and update theuser's signature authority.The algorithm introduces acomplete subtree,which is usedbythekey generationcenter(KGC)generates temporarysignaturekeys foreach legitimate user,sothatonly thesignature generatedbythis keycanpass thesignature verification.I terms ofsecurity,thenewalgorithmisproventobeexistentially unforgeableunderadaptivechosen messageand identityatacks intherandomoracle model.Intermsof eficiency,whenthe number ofusers in thesystem is largeand the numberofrevoked users issmallinthe keyupdate stage,the timecostof the KGC to update the user's signature key is much smallr than Boneh et al. 's update technology.

Key words: identity-based cryptosystem; SM9 signature algorithm; key revocation; complete subtree

# 0 引言

1984 年，Shamir[1]首次提出了标识密码(Identity-BasedCryptosystem)的概念，包括标识加密算法(Identity-BasedEncryption,IBE)和标识签名算法(Identity-Based Signature,IBS)。它可以采用用户的唯一标识，如身份证号、手机号、电子邮件地址等作为用户公钥，由密钥中心根据系统密钥以及用户标识生成相应的用户私钥。与传统公钥密码算法相比，标识密码算法简化了PKI/CA应用中的证书分发和公钥交换的过程，降低了密钥和证书管理的复杂性。2000年，Ohgishi和Kasahara[2]发表了一篇使用椭圆曲线对提出的基于身份的密钥共享方案。直到2001年,Boneh和Franklin[3]以及Cocks[4]才分别给出首个标识加密算法(Identity-Based Encryption，简称IBE)的构造。随后，美国，英国和日本开始设计相应的算法，如文献[5\~8]。

中国国家密码学管理局于2008年正式发布了SM9[9商用标识密码算法，并于2016年3月28日发布并实施了SM9标识密码算法标准。SM9系列算法包括密钥交换，签名以及加密三种，其中签名算法与加密算法分别已于2018 年11月[10]和2021年2月[11]被纳入国际标准。SM9因其结构简单，功耗低等优点，在密码技术和网络空间安全领域愈来愈受到广泛地应用与发展，如文献[12\~16]。

虽然标识密码体系简化了用户公钥管理的环节，但是包括SM9在内的标识密码算法并没有提供用户密钥撤销机制，一旦用户私钥泄露，用户标识就需作废无法继续使用，否则攻击者就会使用泄露的密钥访问用户所有的密文或者代表用户签署任何文献。针对标识密码系统的密钥泄露问题，2001年，Boneh等人[3]提出利用身份标识级联时间戳作为用户临时身份，例如 $I D \| 2 0 2 2 . 0 1$ ，密钥中心定期将相应的密钥发送给未被撤销的用户。该方法具有通用性，适用于任意标识密码系统，但是密钥中心更新密钥的复杂度与系统用户数量线性增长，为 $O ( N - R )$ ，其中 $N$ 是系统用户数量， $R$ 是被撤销用户数量。此外，该方法需要安全信道传输用户的密钥。2008 年，Boldyreva 等人[17提出第一个高效的可撤销IBE方案。该方案为每个用户预分配一组长期密钥并利用完全子树覆盖技术实现用户临时密钥的安全更新，从而使得密钥更新的复杂度从线性降至 $O ( R \cdot \log ( N / R ) )$ ，且不需要安全信道传输更新密钥。近年来，一些学者从适应性身份安全性[18]、临时密钥泄露攻击[19]、更新密钥的复杂性[20]、抗量子计算攻击[21,22]、云计算辅助撤销[23\~25]等方面，提出了一系列可撤销的标识密码方案。这些方法主要利用完全子树(CompleteSubtree，CS)覆盖技术或子集合差分(SubsetDifference，SD)技术确定更新节点数量，从而降低更新密钥的复杂性。同时，利用主密钥与用户密钥之间存在的同态性质，计算各个更新节点的更新密钥。然而，SM9"指数倒置"的特殊代数结构，使得构造上述方法无法直接用于SM9标识密码系统。2019年，Ma等人[26]利用完全子树覆盖技术提出一种构造可撤销标识加密方案的通用方法。与文献[3]中的通用方法相比，该方法将更新密钥的复杂度从$O ( N - R )$ 降至 $O ( R \cdot \log ( N / R ) )$ ，但是密文长度从 $O ( 1 )$ 扩展到了${ \cal O } ( \log N )$ ，或者依赖基于身份的广播加密。将该方法直接应用到SM9上，密文的数量至少为 $O ( \log N )$ ，效率较低。截止目前，还没有针对SM9签名算法的高效密钥撤销机制的研究。

解决思路：针对标识加密算法，Ma等人[26]提出的更新密钥的主要思想是：通过引入一棵完全子树，将用户的身份标识与该树叶子节点一一对应。在更新密钥时，利用完全子树覆盖技术确定仅覆盖未被撤销用户的最小节点集合，再利用时间戳级联更新节点信息作为更新标识，计算出更新密钥集合。在加密时，由于发送者需要将时间戳与接收者身份标识对应的叶子节点到根节点路径上的所有节点信息级联作为临时身份标识用于加密消息，从而使得密文数量至少为$O ( \log N )$ 。受此思想的启发，针对SM9标识签名算法，可以采用同样的更新密钥的策略并利用长期密钥和更新密钥生成消息的两份签名。但是，用户在验证签名的合法性时，除了利用签名者的身份标识进行一次验签外，还要利用至少$O ( \log N )$ 个临时标识进行验签，从而使得签名验证算法的效率较低。为了解决该问题，本文在签名时，将使用的更新密钥的节点信息嵌入到签名中，用户首先验证嵌入的节点信息是否在用户的路径上，再使用该节点信息(作为临时标识)验证签名的合法性，从而使得验签次数降至2次。

本文工作：本文提出了一种可撤销SM9 标识签名算法(简称CS-SM9-RIBS)，它利用完全子树实现在SM9标识签名算法中对用户密钥的撤销和更新机制。在该算法中，密钥中心会根据用户的身份生成一个长期签名密钥，根据更新节点集合生成更新密钥并发送给用户，使得只有未被撤销的用户才能合成一个合法的临时签名密钥，用于签名消息。与Boneh等人[3]的方案(简称BF-SM9-RIBS)相比，该方案不需要数据发送者和服务器之间建立一条安全信道，并且更新密钥的数量也大大降低：从 $O ( N - R )$ 降至 $O \big ( R \cdot \log ( N / R ) \big )$ 。通过实验分析表明，当系统用户数量为 $N = 2 ^ { 1 3 } = 8 1 9 2$ ，被撤销用户数量$R \in [ 0 , 1 0 0 ]$ 时，BF-SM9-RIBS方案密钥更新的时间约为45秒，而CS-SM9-RIBS方案所需要时间在15秒以下。

# 1 基础知识

# 1.1符号说明

在本文中，“ $\boldsymbol { A } \parallel \boldsymbol { B }$ "表示将两个比特串A和B进行级联。若 S 是一个算法，则 $s  S$ 表示执行算法S输出的结果为 s;若 S 是一个集合，则 $s  S$ 表示从集合 S中以均匀随机分布选取一个元素s。

在SM9 算法中，

a) $\boldsymbol { H } _ { \nu }$ 为输入为任意比特串，输出为 $\mathbf { v }$ 比特的密码杂凑函数。b) $\mathrm { H } 2 \mathrm { R F } ( H _ { \nu } , Z , p )$ 为输入为密码杂凑函数 $\boldsymbol { H } _ { \nu }$ ，比特串Z和整数 $\mathfrak { p }$ ，输出为整数 $h \in [ 1 , p - 1 ]$ 的密码函数。

# 1.2双线性映射

令 $\mathcal { P } ( 1 ^ { \lambda } )$ 表示一个双线性对群生成算法，输入1为安全参数，输出为 $\left( e , \mathbb { G } _ { 1 } , \mathbb { G } _ { 2 } , \mathbb { G } _ { T } , p , g , h \right)$ ，其中 $\mathbb { G } _ { 1 }$ 、 $\mathbb { G } _ { 2 }$ 和 $\mathbb { G } _ { T }$ 是阶为素数$p$ 的循环群，映射 $e : \mathbb { G } _ { 1 } \times \mathbb { G } _ { 2 } \to \mathbb { G } _ { T }$ 为双线性对， $g$ 和 $h$ 分别是$\mathbb { G } _ { 1 }$ 和 $\mathbb { G } _ { 2 }$ 的生成元。一个双线性映射应该满足以下性质：

a）双线性性：对于任意的 $\alpha , \beta \in \mathbb { Z } _ { p }$ ，有 $e \left( g ^ { \alpha } , h ^ { \beta } \right) = e \left( g , h \right) ^ { \alpha \beta }$ ：b）非退化性： $\exists g _ { 1 } \in \mathbb { G } _ { 1 } , g _ { 2 } \in \mathbb { G } _ { 2 }$ 满足 ${ e } \left( { { g } _ { 1 } } , { { g } _ { 2 } } \right) \ne { { 1 } _ { { \mathbb { G } } _ { T } } }$ ;c）可计算性：对于任意的g和 $h$ ，存在有效多项式时间算法计算 $e { \big ( } g , h { \big ) }$ □

# 1.3 困难问题假设

本节主要介绍文献[27]提出的SM9签名算法满足适应性选择消息和标识攻击下的存在性不可伪造攻击安全性(Existentially Unforgeable against adaptive Chosen Message andIdentityAttacks，简称EU-CMIA安全性)依赖的 $\mathsf { q }$ -SDH问题(q-strong Diffie-Hellman)。令 $e : \mathbb { G } _ { 1 } \times \mathbb { G } _ { 2 } \to \mathbb { G } _ { T }$ 为一个双线性映射，$g$ 和 $h$ 分别是 $\mathbb { G } _ { 1 }$ 和 $\mathbb { G } _ { 2 }$ 的生成元，群 $\mathbb { G } _ { 1 }$ 、 $\mathbb { G } _ { 2 }$ 和 $\mathbb { G } _ { T }$ 的阶为 $p$ □则基于双线性群的 $\mathsf { q }$ -SDH问题的定义如下：

定义1 $\mathsf { q }$ -SDH问题。已知 $q + 2$ 个群元素$\left( g , h , h ^ { a } , h ^ { a ^ { 2 } } , . . . , h ^ { a ^ { q } } \right) \in \mathbb { G } _ { 1 } \times \mathbb { G } _ { 2 } ^ { q + 1 }$ ，其中 $a$ 未知，找到一个二元组 $\left( c , g ^ { 1 / \left( c + a \right) } \right)$ ，其中 $c \in \mathbb { Z } _ { p }$ 。

若 $\mathbf { q } { \mathrm { - } } \mathbf { S } \mathbf { D } \mathbf { H }$ 问题在多项式时间内可解的概率是可忽略的,则称 $\mathsf { q }$ -SDH假设成立。

# 1.4 SM9-IBS 标识签名算法

SM9 标识签名算法(简称 SM9-IBS 算法)，包括4个(概率)多项式时间算法：系统参数生成算法、用户密钥提取算法、签名生成算法和验证算法。

下面本文简要回顾SM9-IBS算法。

a）系统参数 SM9.Setup(l)：输入安全参数1，密钥中心首先运行算法 $\mathcal { P } ( 1 ^ { \lambda } )$ 生成一个双线性对配对群$\mathcal { G } \mathrm { = } ( e , \mathbb { G } _ { 1 } , \mathbb { G } _ { 2 } , \mathbb { G } _ { T } , p , g , h )$ ；然后，选取随机数 $s \in \mathbb { Z } _ { p }$ ，计算 $P _ { p u b - s } = g ^ { s }$ 和 $u = e \left( g , h \right) ^ { s }$ 。则系统的主公钥和主私钥分别为

$$
m p k = ( \mathcal { G } , P _ { p u b - s } , u , H ( i d ) , h i d )
$$

$$
m s k = s
$$

其中 $H ( i d )$ 是密码函数 $\mathrm { H 2 R F } ( H _ { \nu } , i d , p )$ ，hid=3。假设系统的主公钥作为其他算法的默认输入，而省略不写。

b）用户密钥SM9.Extract $( m s k , i d )$ ：对于身份标识为 $i d$ 的用户，密钥生成中心为用户计算签名私钥为

$$
d s _ { i d } = g ^ { \frac { s } { H _ { 1 } ( i d \parallel h i d , N ) + s } }
$$

则签名者公钥为 $i d$ ，私钥为 $d s _ { i d }$ 。

c）签名 $\mathrm { S M 9 . S i g n } ( d s _ { i d } , M )$ ：身份标识为 $i d$ 的签名者对消息$M$ 进行签名，签名过程如下：

(a)计算 $w = u ^ { r }$ ，其中 $\boldsymbol { r }$ 为随机数且满足 $\textstyle r \in \mathbb { Z } _ { p }$ ;  
(b）计算 $h { = } \mathrm { H } 2 \mathrm { R F } ( H _ { \nu } , M \parallel w , p )$ ;  
(c）计算 $l = ( r - h ) { \bmod { p } }$ ，若 $\scriptstyle { l = 0 }$ ，则返回第二步；  
(d)计算 ${ \boldsymbol { S } } = d s _ { i d } ^ { l }$ 。

则签名者对消息的签名结果为 $\sigma = \left( h , S \right)$ 。

d）验证 SM9.Verify $( i d , M ^ { \prime } , \sigma ^ { \prime } )$ ：验证者在收到签名者的身份标识 $i d$ ，消息 $M ^ { \prime }$ 和签名结果 $\sigma ^ { \prime } = \left( h ^ { \prime } , S ^ { \prime } \right)$ 后，执行以下步骤进行签名验证。

(a)计算 $t = u ^ { h ^ { \prime } }$ ：  
(b)计算 $P = h ^ { H ( i d ) } \cdot P _ { p u b - s }$ ;  
(c）计算 $w ^ { \prime } = \alpha \cdot t$ ，其中 $\alpha = e ( S ^ { \prime } , P )$ ：  
(d)计算 $h _ { 2 } = \mathrm { H } 2 \mathrm { R F } ( H _ { \nu } , M ^ { \prime } \| w ^ { \prime } , p )$ ：  
(e)若 $h _ { 2 } = h ^ { \prime }$ ，则验签通过；否则验签失败。

注释1：为了提高签名和验证算法的效率，可以将原始SM9-IBS 算法中计算的固定值 $u = e \big ( g , P _ { p u b - s } \big )$ 放到系统公钥中，从而使得签名和验证算法都减少一次双线性配对运算，而系统公钥将增加一个群 $\mathbb { G } _ { T }$ 上的元素。

标识签名算法的EU-CMIA安全模型：在标识签名算法中，适应性选择消息和标识攻击下的存在性不可伪造EU-CMIA安全模型的定义与传统签名算法的安全模型定义类似，除了平凡的询问外，允许攻击者选择任意标识并获取相应的签名密钥，以及任意消息并获取签名结果，具体参见文献[27]。在该模型下，有以下结论：

定理1 SM9-IBS 的安全性[27]。在随机预言机模型下,如果q-SDH问题是困难的，则SM9-IBS满足EU-CMIA安全性。

# 2 CS-SM9-RIBS标识签名算法

# 2.1 RIBS的定义

图1给出了可撤销标识数字签名算法的系统模型，它包含以下四个实体：

a)密钥中心(KGC)：主要负责产生系统主公钥mpk 和主私钥msk，为身份标识为id的用户生成长期签名密钥 $d s _ { i d }$ ，生成更新密钥集合 $u k _ { t }$ ，维护用户撤销列表RL及一个与所有用户身份标识id对应的身份二叉树Tree。

b)数据签名者(DS)：主要负责计算原始消息 $M$ 的数字签名结果 $\sigma$ □

c）存储服务器(SS)：主要负责存储用户的签名。

d)签名验证者(SV：主要负责对接收到的签名 $\sigma$ 进行合法性验证。

![](images/052086bc8c0430dc341f4f29b3fe034635c9f1824fa4905531fe5762c0d6ad24.jpg)  
图1 RIBS系统模型  
Fig.1System model of RIBS

定义2RIBS的定义。一个RIBS算法包含系统参数生成算法、用户注册算法、未撤销用户的更新节点生成算法、更新密钥生成算法、临时签名密钥生成算法、签名算法、验证算法和用户撤销算法8个(概率)多项式时间算法，具体如下：

a）系统参数 Setup(l)：该算法由密钥中心负责执行。它的输入为安全参数λ，输出为系统的主公钥mpk和主私钥msk。此外，密钥中心维护一个初始化为空集的撤销列表RL，以及一个与所有用户身份标识 $i d$ 对应的满二叉树 Tree 。

b）用户注册Regist(msk,id)：该算法由密钥生成中心负责执行。它的输入为系统的主私钥和用户的身份标识 $i d$ ，将用户的身份标识 $i d$ 加入到Tree，并输出用户的长期签名密钥dsid。

c）更新节点KUNode(Tree, $R L , t )$ ：该算法由密钥中心执行。它输入身份二叉树Tree，撤销列表 $R L$ 和时间 $t$ ，输出所有需要生成更新密钥的节点集合KUNodes。

d）更新密钥UpdateK(msk,t,KUNodes)：该算法由密钥中心执行。输入为系统主私钥msk，时间 $\textit { t }$ 以及未撤销结集合KUNodes，输出为更新密钥集合 $u k _ { t }$ ，并通过公开信道广播给系统用户。

e）临时签名密钥 $\mathrm { T e m p K } ( d s _ { i d } , u k _ { t } )$ ：该算法由数据签名者执行。它输入用户的长期签名密钥 $d s _ { i d }$ 和更新密钥集合 $u k _ { t }$ 。若该用户未被撤销，则算法输出为用户的临时签名密钥 $t s d _ { i d , t }$ （该签名密钥不仅包含了用户的身份 $i d$ 和更新的时间 $t$ ，同时也包含了对应的更新节点信息 $\theta$ ）。

f)签名 $\mathrm { S i g n } ( t s d _ { i d , t } , M )$ ：该算法由数据签名者执行。它的输入为原始消息 $M$ ，用户临时签名密钥 $t s d _ { i d , t }$ ，计算出消息 $M$ 的签名 $\sigma$ 。该签名包含了时间周期和更新节点信息。最后，将消息和签名 $( M , \sigma )$ 一同发送给存储服务器进行储存。

g）验证 $\mathrm { V e r i f y } ( i d , M , \sigma )$ ：该算法由签名验证者执行。算法的输入为签名者的身份标识 $i d$ 、消息 $M$ 和签名 $\sigma$ 。输出签名的验证结果。若签名合法，则输出1，否则输出0。

h）用户撤销Revoke $( i d , t , R L )$ ：该算法由密钥中心执行。它的输入为被撤销的用户身份标识 $i d$ 、时间周期 $t$ 和用户撤销列表RL。密钥中心将(t,id)加入撤销列表，返回更新后的撤销列衣KL。

2.2安全模型为刻画方案具有密钥撤销机制，本文通过攻击者与挑战  
者的游戏描述适应性选择消息和标识攻击下的存在性不可伪  
造攻击(EU-CMIA安全性)。在该模型中，攻击者可以询问任  
意用户的长期签名密钥，当某一用户的签名密钥泄露(被攻击  
者询问)并在t时刻被密钥中心撤销时，方案的安全性能够保  
证在 $t ^ { * } \geq t$ 时刻，攻击者无法生成该用户的一个合法签名。定义3RIBS的EU-CMIA安全性。假设A是任意一个  
概率多项式时间攻击者，C 是一个挑战者。定义RIBS的安  
全性游戏ExpSI(1)如下：a)系统建立：挑战者通过运行系统参数生成算法  
Setup(l)，生成系统主公钥mpk 和主私钥msk，并初始化一个  
空的密钥撤销列表RL 和一个满二叉树Tree。挑战者将系统公  
钥 mpk 发送给攻击者。b）询问：攻击者可以适应性地询问进行以下询问，询问  
的次数为多项式次：(a）用户长期签名密钥询问．挑战者初始化一个空集合  
$L _ { 1 }$ 。当攻击者询问身份标识为 $i d$ 的用户长期签名密钥时，挑  
战者通过执行用户注册算法 $\mathrm { R e g i s t } ( m s k , i d )$ 生成密钥 $d s _ { i d }$ 并返  
回给攻击者。同时，挑战者将身份标识 $i d$ 添加到集合 $L _ { 1 }$ 中。(b)更新密钥询问．当攻击者询问 $t$ 时刻的更新密钥时，  
挑战者首先执行更新节点生成算法 KUNode(Tree,RL,t)得到 $t$ 时  
刻的更新节点集合KUNodes；然后执行更新密钥生成算法  
UpdateK(msk,t,KUNodes)得到 $t$ 时刻的更新密钥集合 $u k _ { t }$ ,并将它  
返回给攻击者。(c）签名询问.挑战者初始化一个空集合 $L _ { 2 }$ 。当攻击者询  
问消息 $M$ 在身份标识为 $i d$ 和时刻 $t$ 下的签名时，挑战者先利  
用该用户 $i d$ 的长期签名密钥 $d s _ { i d }$ 和 $t$ 时刻的更新密钥集合 $u k _ { t }$ ，  
通过临时签名密钥生成算法生成该用户的临时签名密钥  
$t s d _ { i d , t }$ ；然后，利用签名算法 $\mathrm { S i g n } ( t s d _ { i d , t } , M )$ 生成消息 $M$ 的签名 $\sigma$ ，  
并将该签名返回给攻击者。同时，挑战者将元素 $( i d , t , M )$ 添加  
到集合 $L _ { 2 }$ 中。(d)用户撤销询问．当攻击者询问 $t$ 时刻的标识为 $i d$ 的  
用户撤销时，挑战者将 $( t , i d )$ 添加到用户撤销列表 $R L$ 中。c）伪造．攻击者返回一个伪造的签名信息 $( M ^ { * } , \sigma ^ { * } )$ 以及  
身份标识 $i d ^ { * }$ 和时间 $t ^ { * }$ ，并满足以下限制条件(a)若用户在 $t ^ { * }$ 或之前时刻未撤销，即不存在 $t \leq t ^ { * }$ ，使得  
$( t , i d ^ { * } ) \in R L$ ，则攻击者不能访问过身份标识 $i d ^ { * }$ 的长期签名密  
钥，即 $i d ^ { * } \notin { L _ { 1 } }$ 并且 $( i d ^ { * } , t ^ { * } , M ^ { * } ) \not \in L _ { 2 }$ ；(b)若用户在 $t ^ { * }$ 或之前时刻已撤销，即存在 $t \leq t ^ { * }$ ，使得  
$( t , i d ^ { * } ) \in R L$ ，则攻击者可以询问身份标识 $i d ^ { * }$ 的长期签名密钥,  
即id∈L。

d)输出．若攻击者伪造的签名信息满足限制条件，并能

通过签名验证算法，则表示攻击者伪造成功，挑战者返回1；  
否则返回0。

在上述游戏中，A成功的概率定义为

$$
\mathrm { P r } [ \mathrm { A } \mathrm { H } \dot { \mathrm { \chi } } \mathrm { I } \dot { \mathrm { \jmath } } ] = \mathrm { P r } [ \mathrm { E x p } _ { \mathrm { R I B S , A } } ^ { \mathrm { E U - C M A } } ( \mathrm { l } ^ { \lambda } ) = 1 ]
$$

如果A成功的概率(关于安全参数1)是可忽略的，则称RIBS算法是EU-CMIA安全的。

# 2.3算法设计

本节利用完全子树覆盖技术，设计一种可撤销SM9标识签名算法(记作CS-SM9-RIBS)。具体构造如下：

a）系统参数 Setup(l)：在输入安全参数 $1 ^ { \lambda }$ 后，生成系统参数的过程如下：

(a)密钥中心运行算法 $\mathcal { P } ( 1 ^ { \lambda } )$ 生成一个双线性配对群$\mathcal { G } \mathrm { = } ( e , \mathbb { G } _ { 1 } , \mathbb { G } _ { 2 } , \mathbb { G } _ { T } , p , g , h )$ ；密钥中心选择一个随机元素 $s \in \mathbb { Z } _ { p }$ ，并计算

令 $H ( i d ) = \mathrm { H } 2 \mathrm { R F } \left( H _ { \nu } , i d , p \right)$ 、 $h i d = 3$ 。假设每个用户的身份标识长度为 $n$ 比特，则密钥中心初始化一棵高度为 $n { + } 1$ 的满二叉树Tree 以及一个空的用户撤销列表 $R L$ 0

(b)输出系统的主公钥mpk和主私钥 $m s k$ ：

$$
m p k = \left( \mathcal { G } , P _ { p u b - s } , u , H ( \cdot ) , h i d \right)
$$

$$
m s k = s
$$

b）用户注册Register $( m s k , i d )$ ：密钥中心在收到身份标识为$i d$ 的用户注册请求后，为用户注册生成一个长期签名密钥的过程如下：

(a)密钥中心使用 SM9的密钥提取算法为标识为 $i d$ 的用户生成签名密钥 $d s _ { i d }$ ，即：

$$
d s _ { i d } \gets \mathrm { S M 9 . E x t r a c t } ( m s k , i d )
$$

(b)密钥中心选择一个与用户身份标识匹配的叶子节点，将 $i d$ 添加到Tree上;

(c）将用户长期签名密钥 $d s _ { i d }$ 发送给用户。

c）更新节点KUNode(Tree $R L , t )$ ：在输入身份二叉树Tree，撤销列表 $R L$ 和时间 $t$ 后，令 $\theta$ 为Tree的非叶子节点， $\theta _ { \iota }$ 和 $\theta _ { r }$ 分别为 $\theta$ 的左子节点和右子节点， $\mathrm { P a t h } ( \theta _ { i d } )$ 为根节点到叶子节点 $\theta _ { i d }$ 路径上所有节点的集合，未撤销节点生成过程如下：

(a)令集合 $\scriptstyle { X , Y = \varnothing }$ ·

(b）对 $\forall ( t ^ { \prime } , i d ) \in R L$ 且 $t ^ { \prime } \leq t$ ，将 $\mathrm { P a t h } ( \theta _ { i d } )$ 中的每一个节点添加到集合 $\boldsymbol { \cal X }$ 中。

(c）对 $\forall \theta \in X$ ：

如果 $\theta _ { \iota } \not \in X$ ，则将 $\theta _ { l }$ 添加到集合 $Y$ 中；  
如果 $\theta _ { r } \not \in X$ ，则将 $\theta _ { r }$ 添加到集合Y中。

(d)如果 $Y = \emptyset$ ，那么将根节点root添加到集合 $Y$ 中；

(e）令KUNodes $\scriptstyle = Y$ ，并输出KUNodes。

图2和图3给出了更新节点选择算法的两个具体示例。在该示例中，二叉树的高度为4(用户的身份标识长度为3比特)，蓝色节点表示当前KUNodes所包含的更新节点，虚线节点表示被撤销的用户节点。在图2中，无用户被撤销，KUNodes仅包含根节点，即{root}；在图3中，标识为 $i d = 3$ 的用户被撤销， $K U N o d e s = \{ 0 0 , 0 1 0 , 1 \}$ 。

![](images/f2dfc49834e9847a6f6d2af8627dc1c7465d019d2101e276e5137e23afee3188.jpg)  
图2无用户被撤销  
Fig.2No user was revoked   
Fig.3The user identified as $\dot { \iota } d = 3$ was revoked

![](images/6f9f342897ef7632fd8cfd505f32cce77f6d5219d78a118903a08bafe50b21ce.jpg)  
图3用户 $i d = 3$ 被撤销

d）更新密钥UpdateK(msk,t,KUNodes)：在输入系统密钥msk，时间 $t$ 以及更新节点集合KUNodes后，密钥中心首先计算由时间和更新节点组成的更新标识集合 $U I D = \{ t \parallel \theta \} _ { \theta \in K U N o d e s }$ 。对于集合 $U I D$ 中的每个标识 $u i d = t \left\| \theta \right.$ ，调用SM9的密钥提取算法，生成相应的标识密钥，即

$$
d s _ { t \parallel \theta } \gets \mathrm { S M 9 . E x t r a c t } ( m s k , u i d )
$$

令 $u k _ { t , \theta } = d s _ { t \parallel \theta }$ 。则更新密钥集合为

$$
u k _ { t } = \{ u k _ { t , \theta } \} _ { \theta \in K U N o d e s }
$$

密钥中心通过公开信道广播给系统用户。

e)临时签名密钥 $\mathrm { T e m p K } ( d s _ { i d } , u k _ { t } )$ ：在输入用户的长期签名密钥 $d s _ { i d }$ 和更新密钥集合 $u k _ { t }$ 后，用户执行以下步骤：

(a)若该用户未被撤销，则用户路径上的节点集合$\operatorname { P a t h } ( \theta _ { i d } )$ 与更新节点集合KUNodes一定存在一个且唯一的公共节点 $\theta$ 。用户找到该节点对应的更新密钥 $u k _ { t , \theta }$ ，并将临时签名密钥定义为 $t s d _ { i d , t } = d s _ { i d } \parallel u k _ { t , \theta } \parallel \theta$ ；若该用户已被撤销，则不存在公共的更新节点 $\theta$ ，用户将临时签名密钥定义为终止符，即 $t s d _ { i d , t } = \perp$ ;

(b）返回临时签名密钥 $t s d _ { i d , t }$ 。

f)签名 $\mathrm { S i g n } ( t s d _ { i d , t } , M )$ ：在输入明文消息 $M$ ，用户的临时签名密钥 $t s d _ { i d , t }$ 后，该算法执行过程如下：

(a)若临时签名密钥 $t s d _ { i d , t } = \perp$ ，则用户终止算法并返回 $\perp$ ： 否则执行步骤(b);

(b)根据临时签名密钥恢复出用户的长期签名密钥 $d s _ { i d }$ ，更新密钥 $u k _ { t , \theta }$ 以及更新节点信息 $\theta$ ，并令 ${ \bar { M } } = M \left\| t \right\| \theta$ (假设不同的消息、时间和更新节点级联的结果不同)。

(c）以 $d s _ { i d }$ 作为签名密钥，执行 SM9 签名算法，生成消息 $\bar { M }$ 的第一部分签名 $\sigma _ { \mathrm { 1 } } = ( h _ { \mathrm { 1 } } , S _ { \mathrm { 1 } } )$ ，即

$$
( h _ { 1 } , S _ { 1 } ) \gets \mathrm { S M 9 . S i g n } ( d s _ { i d } , \bar { M } )
$$

(d)以 $u k _ { t , \theta }$ 作为签名密钥，再次执行SM9 签名算法，生成消息 $\bar { M }$ 的第二部分签名 $\sigma _ { 2 } = ( h _ { 2 } , S _ { 2 } )$ ，即

$$
( h _ { 2 } , S _ { 2 } ) \longleftarrow \mathrm { S M 9 . S i g n } ( u k _ { t , \theta } , \bar { M } )
$$

(e）令 $\sigma = ( \sigma _ { 1 } , \sigma _ { 2 } , t \lVert \theta )$ 为最终签名发送给存储服务器进行存储。

g）签名验证 $\mathrm { V e r i f y } ( i d , M , \sigma )$ ：在输入签名者的身份标识 $i d$ 、消息 $M$ 和签名 $\sigma$ 后，签名验证过程如下：

(a)签名验证者收到签名 $\sigma = ( \sigma _ { 1 } , \sigma _ { 2 } , t \lVert \theta )$ 之后，将其拆分为 $\sigma _ { 1 }$ ， $\sigma _ { 2 }$ 和 $t \parallel \theta$ 三部分。验证者首先判断节点 $\theta$ 是否在路径$\operatorname { P a t h } ( \theta _ { i d } )$ 上。如果不是，则算法终止并返回0；否则，执行步骤(b);

(b）验证者计算 ${ \bar { M } } = M \\| t \| \theta$ ，使用签名者的身份标识 $i d$ 利用SM9签名验证算法对消息 $\bar { M }$ 和签名 $\sigma _ { 1 }$ 进行验证，验证结果记为 $b _ { 1 }$ ，即：

$$
b _ { 1 } \gets \mathrm { S M 9 . V e r i f y } ( i d , \bar { M } , \sigma _ { 1 } )
$$

如果 $b _ { \mathrm { { l } } } = 0$ ，则算法终止并返回0；否则，执行步骤(c);

(c）接下来验证者使用更新标识 $t \left\| \theta \right\|$ 利用SM9签名验证算法对消息 $\bar { M }$ 和签名 $\sigma _ { 2 }$ 进行验证，验证结果记为 $b _ { 2 }$ ，即：

$$
b _ { 2 } \gets \mathrm { S M 9 . V e r i f y } ( t \| \theta , \bar { M } , \sigma _ { 2 } )
$$

如果 $b _ { 2 } = 0$ ，则算法终止并返回0；否则，执行步骤(d);

(d)上述验证均通过，算法返回1。

h）用户撤销 $\operatorname { R e v o k e } ( i d , t , R L )$ ：在输入被撤销用户身份标识id、时间周期 $\textit { t }$ 和撤销列表 $R L$ 后，若存在元素 $( t ^ { \prime } , i d ) \in R L$ 且$t ^ { \prime } \leq t$ ，则直接返回；否则，将(t,id)加入撤销列表 $R L$ ，返回$R L \cup ( t , i d )$ 0

正确性：假设 $\sigma = ( \sigma _ { 1 } , \sigma _ { 2 } , t \lVert \theta )$ 是利用签名算法 $\mathrm { S i g n } ( M , t s d _ { i d , t } )$ 计算的签名。因为 $\sigma _ { 1 } = ( h _ { 1 } , S _ { 1 } )$ 是利用标识为 $i d$ 的 SM9签名密钥 $d s _ { i d }$ 对消息 $\bar { M }$ 的签名，根据SM9签名算法的正确性，则验证算法在第(b)步输出结果应为 $b _ { \scriptscriptstyle 1 } = 1$ ：

若用户 $i d$ 在时刻 $t$ 未被撤销，根据更新节点选择算法，用户能够从更新密钥中获取临时签名密钥 $u k _ { t , \theta }$ 。该密钥对应的身份标识为 $t \parallel \theta$ ，并且 $\theta$ 属于路径 $\operatorname { P a t h } ( \theta _ { i d } )$ 上的点。因此，步骤(a)的验证通过。由于 $\sigma _ { 2 } = ( h _ { 2 } , S _ { 2 } )$ 是利用标识为 $t \parallel \theta$ 的SM9签名密钥 $u k _ { t , \theta }$ 对消息 $\bar { M }$ 的签名，根据SM9 签名算法的正确性，则验证算法在第(c)步输出结果应为 $b _ { 2 } = 1$ 0

综上，CS-SM9-RIBS 签名算法满足正确性。

# 3 安全性分析

定理2 CS-SM9-RIBS的安全性。假设A是任意一个概率多项式时间算法，I是一个CS-SM9-RIBS 签名算法。若A能够以概率 $\varepsilon _ { \Pi }$ 成功攻击II的EU-CMIA安全性，那么存在另一个概率多项式时间算法B，以相同的概率成功伪造原始SM9-IBS的一个签名。

证明本文利用算法A作为子程序，构造一个仿真算法B在EU-CMIA模型下，伪造SM9-IBS签名算法的签名。仿真算法 B 按照如下方式模拟攻击者 A 在游戏 ExpSM(l)中的环境。

a）系统建立：仿真算法B首先询问SM9-IBS的挑战者，获取SM9-IBS的一个挑战主公钥mpk，包括双线性对配对群$\mathcal { G } \mathrm { = } ( e , \mathbb { G } _ { 1 } , \mathbb { G } _ { 2 } , \mathbb { G } _ { T } , p , g , h )$ ，公钥元素 $P _ { p u b - s }$ 、 $u$ 和密码函数 $H ( i d )$ 及其标识hid。B将主公钥mpk发送给攻击者A。同时，B初始化一个空的密钥撤销列表 $R L$ 、一棵满二叉树Tree以及两个空集合 $L _ { 1 }$ 和 $L _ { 2 }$ 。

b）询问：B通过如下方式回答攻击者的询问：

(a)用户长期签名密钥询问．当攻击者A询问身份标识为 $i d$ 的用户长期签名密钥时，B 将 $i d$ 发送给 SM9-IBS 的挑战者，从而获取身份标识为 $i d$ 的密钥 $d s _ { i d }$ 并将它返回给攻击者 $\mathrm { \bf A }$ 。同时，A将身 $( i d , d s _ { i d } )$ 添加到集合 $L _ { ☉ }$ 中。

(b)更新密钥询问．当A询问 $\textit { t }$ 时刻的更新密钥时，B首先根据算法 $\mathrm { K U N o d e ( T r e e , } R L , t )$ 计算 $\textit { t }$ 时刻的更新节点集合KUNodes；然后确定更新节点标识集合 $U I D = \{ t \parallel \theta \} _ { \theta \in K U N o d e s }$ 。对于集合 $U I D$ 中的每个标识 $t \parallel \theta$ ，B询问SM9-IBS挑战者，获取该标识的密钥 $d s _ { t \parallel \theta }$ 。B 将密钥集合 $u k _ { t } = \{ d s _ { t \parallel \theta } \} _ { \theta \in K U N o d e s }$ 发送给A。同时，B将所有 $( t \| \theta , d s _ { t \| \theta } )$ 添加到集合 $L _ { 1 }$ 中。

(c)签名询问.当A询问消息 $M$ 在身份标识为 $i d$ 和时刻$\textit { t }$ 下的签名时，仿真算法B首先查找集合 $L _ { ☉ }$ 中是否存在以$t \parallel \theta$ 为标识的密钥 $d s _ { t \parallel \theta }$ ，其中 $\theta$ 必须在路径 $\operatorname { P a t h } ( \theta _ { i d } )$ 上(注：本文假设A总是可以先询问 $t$ 时刻的更新密钥)。若不存在，则B直接返回 $\perp$ 给A(表示在该时刻 $i d$ 已被撤销)。否则，B利用密钥 $d s _ { t \parallel \theta }$ 对消息 ${ \bar { M } } = M \\left\| t \right\| \theta$ 进行签名，得到第二部分签名$\sigma _ { 2 } = ( h _ { 2 } , S _ { 2 } )$ 。接下来，B查找集合 $L _ { \mathrm { 1 } }$ 中是否存在以 $i d$ 为标识的密钥 $d s _ { i d }$ 。若存在，则B利用密钥 $d s _ { i d }$ 对消息 ${ \bar { M } } = M \\left\| t \right\| \theta$ 进行签名，得到第一部分签名 $\sigma _ { 1 } = ( h _ { 1 } , S _ { 1 } )$ ；若不存在，B将消息M以及(身份)标识 $t \left\| \theta \right\|$ 发送给SM9-IBS的挑战者，获得消息M在(身份)标识 $t \parallel \theta$ 密钥下的签名 $\sigma _ { 2 } = ( h _ { 2 } , S _ { 2 } )$ 。最后，B 将签名$\sigma = ( \sigma _ { 1 } , \sigma _ { 2 } , t \lVert \theta )$ 发送给 $\mathrm { \bf A }$ 。同时，B将信息 $( i d , t , M )$ 添加到集合$L _ { 2 }$ 中。

(d)用户撤销询问.当A 在 $t$ 时刻以身份标识 $i d$ 询问撤销列表时，的撤销的用户撤销时，B首先查找集合 $R L$ 是否存在元素 $( t ^ { \prime } , i d )$ ，其中 $t ^ { \prime } \leq t$ 。若存在，则返回原撤销列表 $R L$ ；否则，返回 $R L \cup ( t , i d )$ 。

c）伪造．当攻击者A结束上述询问后，输出一个伪造的签名信息 $( M ^ { * } , \sigma ^ { * } )$ 以及挑战身份标识 $i d ^ { * }$ 和时间 $t ^ { * }$ 。

d)输出.若 $( M ^ { * } , \sigma ^ { * } )$ 是一个合法的CS-SM9-RIBS 签名，其中 $\sigma ^ { * } = ( \sigma _ { 1 } ^ { * } , \sigma _ { 2 } ^ { * } , t ^ { * } \lVert \theta ^ { * } )$ ，则该签名必须通过签名验证算法。特别地， $\theta ^ { * }$ 必须是用户路径。则B定义消息 $\overline { { M ^ { * } } } = M ^ { * } \left. t ^ { * } \right. \theta ^ { * }$ ，并按如下方式返回消息 $\overline { { M ^ { * } } }$ 的一个伪造 SM9-IBS签名 $\overline { { \sigma ^ { * } } }$ ：

(a)若 $( i d ^ { * } , \cdot ) \notin { L _ { 1 } }$ ，表明A从未询问过身份标识为 $i d ^ { * }$ 的密 钥，则B输出伪造签名 $\overline { { \boldsymbol { \sigma } ^ { * } } } = \sigma _ { 1 } ^ { * }$ ;

(b)若存在 $( i d ^ { * } , \cdot ) \in L _ { 1 }$ ，则表明A询问过身份标识 $i d ^ { * }$ 的密钥。根据游戏规则，该用户必须在 $t ^ { * }$ 之前的某时刻 $t$ 被撤销，即 $( t , i d ^ { * } ) \in R L$ 。根据更新节点生成算法，在 $t ^ { * }$ 时刻，算法$\mathbf { K U N o d e } ( \mathrm { T r e e } , R L , t ^ { * } )$ 输出的更新节点集合KUNodes肯定不包含挑战用户的路径 $\operatorname { P a t h } ( \theta _ { i d ^ { * } } )$ 上的节点 $\theta ^ { * }$ 。因此，在整个游戏过程中，B从未询问过标识为 $t ^ { * } \parallel \theta ^ { * }$ 的密钥及其签名。此时，B输出伪造签名 $\overline { { \boldsymbol { \sigma } ^ { * } } } = \sigma _ { 2 } ^ { * }$ 。

通过上述分析，B能够完美地仿真A在CS-SM9-RIBS中的游戏环境。同时，若攻击者能够成功伪造一个CS-SM9-RIBS签名，则仿真算法以相同的概率伪造一个SM9-IBS 签名。

定理2证毕！

# 4 性能分析

目前，除了直接应用Boneh-Franklin[3]通用密钥撤销思想可以构造针对SM9-IBS的密钥撤销算法外，还没有公开发表的针对SM9-IBS的密钥撤销算法。但是存在一些优秀的针对其他标识身份签名的密钥撤销算法，如[19,28\~30]。为此，本节首先从理论和实验两个角度分析和比较与SM9-IBS相关的密钥撤销算法的性能，包括本文提出的基于完全子树密钥撤销技术的CS-SM9-RIBS 算法、原始 SM9-IBS 签名算法[9]以及应用Boneh-Franklin[3]通用密钥撤销技术的BF-SM9-RIBS算法。再从理论上分析本文提出的CS-SM9-RIBS算法与国际上其他可撤销标识签名算法的优势。

表1从参数大小、算法时间及安全性等理论角度对上述与 SM9-IBS相关的三个算法的性能进行总结与比较。在这些算法中，本文选择使用对称双线性配对，即 $e : \mathbb { G } \times \mathbb { G } \to \mathbb { G } _ { T }$ ，其中群的阶为素数 $p$ 。在表中， $N$ 和 $R$ 分别表示系统用户数量和被撤销用户的数量；“E"和"P"分别表示一次群元素的指数运算和配对运算。在比较各算法所需运算操作次数时，忽略了除指数运算和配对运算之外的其他操作。表中符号“"表示该项不存在，‘ $^ { \cdot } 0 ^ { \cdot }$ 表示该项几乎不需要任何操作。

在BF-SM9-RIBS算法中，用户只需要保存每个周期的临时密钥，而无长期密钥。每个周期的临时签名密钥由密钥中心临时生成的更新密钥构成。更新用户签名密钥的策略是将用户的身份标识 $i d$ 与时间周期 $t$ 级联的结果 $i d \parallel t$ 表示当前时刻签名的签名公钥并将相应的私钥通过安全信道发送给相应的为撤销用户。因此，更新用户密钥的复杂度为 $O ( N - R )$ ，与系统用户数量线性增长。对于本文提出的算法，采用完全子树技术更新用户密钥，在平均情况下，更新密钥的数量仅为 $O ( R \cdot \log ( N / R ) )$ 且可以在公开信道上进行传输。

从表1中的比较可以看出，BF-SM9-RIBS和CS-SM9-RIBS两种算法都支持用户密钥撤销功能，同时保留了原始SM9-IBS算法的系统参数。在BF-SM9-RIBS算法中，用户不需要存储长期签名密钥并且临时签名密钥仅为1个群元素。在算法CS-SM9-RIBS中，用户需要存储1个长期签名密钥。尽管临时签名密钥包含2个群元素，但是它包括了用户的长期签名密钥，不需要额外空间存储该群元素。在签名大小、签名时间和验证时间方面，本文的CS-SM9-RIBS算法是原始SM9-IBS算法的2倍。这是因为，前者为了实现用户密钥的撤销功能，增加了一个额外的签名操作。BF-SM9-RIBS 算法在参数大小和计算效率方面和原始 SM9-IBS 算法几乎一样。但是该算法的密钥更新复杂度非常高且不支持公开信道传播更新密钥。

表1性能比较Tab.1Comparison of performance  

<html><body><table><tr><td></td><td>SM9-IBS 文献[9]</td><td>BF-SM9-RIBS 文献[3]</td><td>CS-SM9-RIBS 第2.3节</td></tr><tr><td>系统公钥大小</td><td>3|G|+|Gr|</td><td>3|G|+|Gr|</td><td>3|G|+|Gr|</td></tr><tr><td>系统私钥大小</td><td>|p|</td><td>|pl</td><td>|pl</td></tr><tr><td>长期密钥大小</td><td>|G|</td><td></td><td>G</td></tr><tr><td>更新密钥大小</td><td></td><td>O(N-R)|G|</td><td>O(Rlog(N/R))|G|</td></tr><tr><td>临时密钥大小</td><td></td><td>G</td><td>2|G|</td></tr><tr><td>签名大小</td><td>|G|+|p|</td><td>|G|+|p|</td><td>2|G|+2|pl</td></tr><tr><td>长期密钥时间</td><td>1E</td><td></td><td>1E</td></tr><tr><td>更新密钥时间</td><td>-</td><td>O(N-R)E</td><td>O(Rlog(N / R))E</td></tr><tr><td>临时密钥时间</td><td></td><td>0</td><td>0</td></tr><tr><td>用户撤销时间</td><td></td><td>0</td><td>0</td></tr><tr><td>签名时间</td><td>2E</td><td>2E</td><td>4E</td></tr><tr><td>验证时间</td><td>1P+2E</td><td>1P+2E</td><td>2P+4E</td></tr><tr><td>密钥更新信道</td><td></td><td>安全信道</td><td>公开信道</td></tr><tr><td>密钥撤销功能</td><td>不支持</td><td>支持</td><td>支持</td></tr></table></body></html>

本文在同一环境下对各算法进行了仿真实现，并测试了平均执行时间。编程测试环境为：2.4GHzInteli5-9300HCPU、16.0GB内存、Windows10家庭中文版操作系统。

本文主采用JPBC库对上述三种SM9签名算法进行仿真实现，选取的椭圆曲线类型为Type-F。表2列出了主要算法运行一次的平均时间，未考虑用户撤销等几乎不耗时的算法以及仅需要在系统建立时运行一次的系统参数生成算法。测试的算法主要包括生成长期签名密钥的用户注册(或密钥提取)算法、密钥更新算法(包括更新节点选取算法)、临时签名密钥生成算法、签名算法和验证算法。对于更新密钥生成算法，运行时间不仅与系统用户数量相关，而且与更新节点集合的大小相关。而更新节点集合的大小又与被撤销用户的数量及其在二叉树中的位置相关。为了简化分析，表2仅考虑系统中有100个用户且无用户被撤销的情况。根据理论分析，BF-SM9-RIBS算法需要生成100个更新密钥，而本文算法仅需要生成一个更新密钥。

Tab.2Comparison of average execution times   

<html><body><table><tr><td></td><td>SM9-IBS 文献[9]</td><td>BF-SM9-RIBS</td><td>CS-SM9-RIBS</td></tr><tr><td>长期密钥</td><td>0.006s</td><td>文献[3]</td><td>第2.3节 0.006s</td></tr><tr><td>更新密钥</td><td></td><td>0.685s</td><td>0.006s</td></tr><tr><td>临时密钥</td><td></td><td>0s</td><td>0s</td></tr><tr><td>签名</td><td>0.043s</td><td>0.042s</td><td>0.088s</td></tr><tr><td>验证</td><td>0.467s</td><td>0.478s</td><td>0.852s</td></tr></table></body></html>

从表2可以看出，BF-SM9-RIBS算法生成更新密钥的时间较慢，而本文的密钥更新算法很快。

为了更加清晰的比较CS-SM9-RIBS算法与BF-SM9-RIBS算法更新用户密钥的性能差异，测试方案设计如下：初始化的系统用户数量 $N$ 上限为8192(即Tree 高为14)。被撤销用户的数量 $R$ 从0增加到100，且随机选取被撤销用户的位置。图4展示当 $R$ 取不同值时更新密钥生成算法的时间开销。

![](images/8b55c78100d45a71d89120ca76ff25a90751b80ddc674c39c78eea72b7a26d15.jpg)  
图4更新密钥生成算法时间开销对比图  
Fig.4Comparison of time cost of update key generation algorithm

从图4可以看出，当系统用户数量较大，被撤销用户数量较少时，密钥中心利用完全子树技术更新用户签名密钥的时间开销要远远小于Boneh和Franklin的直接密钥更新技术。

最后，本文从理论上比较CS-SM9-RIBS算法与国际上针对其他标识签名的密钥撤销算法[19,28\~30]的性能，进一步说明CS-SM9-IBS可撤销标识签名算法的优势。在这些算法中，除了文献[30]基于三线性映射群外，其他算法都是基于标准的双线映射群设计的。表3将给出具体的比较结果。在表3中，除了文献[30]外，其他文献中的符号含义与表1中的符号一致。对于文献[30]， $\mathbb { G } _ { 2 }$ 表示三线性映射中的一个阶为素数 $p$ 的群，而“E”和“P”分别表示三线性映射中的群元素指数运算和配对运算。

表2平均执行时间比较  
表3与其他可撤销标识签名算法比较  
Tab.3Comparisons with other revocable IBS algorithms   

<html><body><table><tr><td></td><td>文献[19]</td><td>文献[28]</td><td>文献[29]</td><td>文献[30]</td><td>CS-SM9-RIBS</td></tr><tr><td>临时签名密钥大小</td><td>3|G|</td><td>4G|</td><td>3|G|</td><td>3|G|</td><td>2|G|</td></tr><tr><td>签名大小</td><td>4|G|</td><td>4|G|</td><td>4|G|</td><td>41G2|</td><td>2|G|+2| pl</td></tr><tr><td>签名时间</td><td>6E</td><td>0(1)E</td><td>3E</td><td>6E</td><td>4E</td></tr><tr><td>验证时间</td><td>4P</td><td>O(1)P</td><td>4P+E</td><td>4P</td><td>2P+4E</td></tr><tr><td>更新密钥时间</td><td>O(Rlog(N-R))·E</td><td>O(Rlog(N-R))· E</td><td>O(N-R)·E</td><td>O(R)·E</td><td>O(Rlog(N /R))·E</td></tr></table></body></html>

从表3可以看出，CS-SM9-RIBS算法的临时签名密钥和签名大小比其他方案较小。签名时间相较文献[29]多一次指数运算，但是文献[29]的更新密钥时间与系统用户数量线性增长。文献[30]的更新密钥仅与被撤销用户数量相关，但是该方案依赖三线性映射，没有双线性映射的理论基础成熟。总体而言，本文提出的CS-SM9-RIBS可撤销标识签名算法的性能优势更明显。

# 5 结束语

针对 SM9标识签名算法存在的密钥撤销问题，本文提出了一种可撤销SM9 标识签名算法。通过一棵完全子树的辅助，可以实现对用户权限的控制，从而实现密钥的撤销和更新机制。通过理论分析和实验表明，该方案相比于BF-SM9-RIBS算法在更新密钥方面具有一定的优势。在后续的工作中，存在以下问题值得进一步研究：该方案相比于BF-SM9-RIBS算法在签名和验签阶段多消耗一倍的时间，可进一步研究耗时更少的SM9标识签名算法的密钥撤销机制。

# 参考文献：

[1]Shamir A. Identity-based cryptosystems and signature schemes [C]// Proc of the 4th Advances in Cryptology-Crypto.Berlin: Springer,1984: 47-53.   
[2]Sakai R, Ohgishi K, Kasahara M. Cryptosystems based on pairing [J]. Symposium Cryptographic Information Security,20o0 (43): 26-28.   
[3]Boneh D,Franklin M.Identity-based encryption from the Weil pairing [C]// Proc of the 21th Advances in Cryptology-Crypto.Berlin: Springer, 2001:213-229.   
[4]Cocks C.An identity-based encryption scheme based on quadratic residues [Cl/ Proc of the IMA international conference on cryptography and coding. Berlin: Springer,2001: 360-363.   
[5]Hofheinz D,Jia D,Pan J. Identity-based encryption tightly secure under chosen-ciphertext attacks [C]/ Proc of the 29th Advances in CryptologyAsiacrypt.Berlin: Springer,2018:190-220.   
[6]Langrehr R,Pan J. Tightly secure hierarchical identity-based Encryption [J].Journal of Cryptology,2020,33 (4): 1787-1821.   
[7]Sahai A,Waters B.Fuzzy identity-based encryption [C]/ Proc ofthe 11th Advances in Cryptology-Eurocrypt. Berlin: Springer, 2005: 457-473.   
[8]Waters B.Eficient identity-based encryption without random oracles [C]// Proc of the 11th Advances in Cryptology-Eurocrypt.Berlin: Springer,2005:114-127.   
[9]Cheng Zhaohui.The SM9 cryptographic schemes [J]. Cryptology ePrint Archive,2017.   
[10] ISO/IEC 14888-3:2018,Information technology security techniques: digital signatures with appendix Part 3:Discrete logarithm based mechanisms [S].2018.   
[11] ISO/IEC 18033-5: 2015/AMD 1: 2021 Information technology security techniques: encryption algorithms Part 5:Identity-based ciphers Amendment 1: SM9 mechanism [S].2021.   
[12] Ji Honghan,Zhang Hongjie,Shao Lisong,et al.An efficient attributebased encryption scheme based on SM9 encryption algorithm for dispatching and control cloud [J].Connection Science,2021,33(4): 1094-1115.   
[13] Mu Yongheng, Xyu Haixia,LiPeili,et al. Secure two-party SM9 signing [J].Science China Information Sciences,2020,63 (8):1-3.   
[14]张昱，孙光民，李煜．基于 SM9 算法的移动互联网身份认证方案研 究[J].信息网络安全,2021,21(4):1-9.(Zhang Yyu,Sun Guangmin, Li Yyu.Research on Mobile Internet Authentication Scheme Based on SM9 Algorithm[J]. Netinfo Security,2021,21 (4):1-9.)   
[15]姚英英，常晓林，甄平．基于区块链的去中心化身份认证及密钥管 理方案[J]．网络空间安全,2019,10(6):33-39.(Yao Yingying,Chang Xiaolin， Zhen Ping.Decentralized identity authentication and key management scheme based on blockchain [J]. Cyberspace Security,2019, 10 (6): 33-39.)   
[16]马晓婷，马文平，刘小雪．基于区块链技术的跨域认证方案[J]．电 子学报,2018,46(11): 2571.(MA Xiaoting,MAWenping,LIU Xiaoxue. A cross domain authentication scheme based on blockchain technology [J].Acta Electonica Sinica,2018,46 (11): 2571.)   
[17] Boldyreva A,Goyal V, Kumar V.Identity-based encryption with efficient revocation [C]//Proc of the 15th ACM conference on Computer and communications security, New York: ACMPress,20o8: 417-426.   
[18] Libert B,Vergnaud D.Adaptive-ID secure revocable identity-based encryption [C]// Proc of the 9th Cryptographers'Track at the RSA Conference.Berlin: Springer,2009:1-15.   
[19] Seo JH,Emura K. Revocable identity-based cryptosystem revisited: security models and constructions [J].IEEE Trans on Information Forensics and Security,2014,9(7): 1193-1205.   
[20] Lee K,LeeDH,Park JW.Efficient revocable identity-based encryption via subset difference methods [J].Designs,Codes and Cryptography, 2017, 85 (1): 39-76.   
[21]Katsumata S,Matsuda T,Takayasu A.Lattice-based revocable (hierarchical） IBE with decryption keyexposure resistance [J]. Theoretical Computer Science,2020,809:103-136.   
[22] Takayasu A，Watanabe Y. Lattice-based revocable identity-based encryption with bounded decryption key exposure resistance [Cl// Proc ofAustralasian Conference on Information Security and Privacy. Berlin: Springer,2017: 184-204.   
[23] Li Jin,Li Jingwei, Chen Xiaofeng,et al. Identity-based encryption with outsourced revocation in cloud computing [J]. IEEE Trans on Computers, 2013,64 (2): 425-437.   
[24] Qin Baodong,Deng R H,Li Yingjiu,et al.Server-aided revocable identity-based encryption [C]// European Symposium on Research in Computer Security.Berlin: Springer 2015: 286-304.   
[25] Qin Baodong,Liu Ximeng,Wei Zhuo,et al.Space efficient revocable IBE for mobile devices in cloud computing [J]. Science China Information Sciences,2020,63 (3): 1.   
[26] Ma Xuecheng,Lin Dongdai. Generic constructions of revocable identitybased encryption [C]// Proc of the International Conference on Information Security and Cryptology. Berlin: Springer, 2019: 381-396.   
[27]赖建昌，黄欣沂，何德彪，等．国密 SM9 数字签名和密钥封装算法 的安全性分析[J].中国科学：信息科学,2021,51(11):1900-1913. (Lai Jianchang,Huang Xinyi,He Debiao,et al. Security analysis of SM9 digital signature and key encapsulation [J]. SCIENTIA SINICA Informationis,2021,51(11):1900-1913.)   
[28] Wei Jianghong,Liu Wenfen,Hu Xuexia.Forward-secure identity-based signature with efficient revocation [J]. International Journal of Computer Mathematics,2017,94(7): 1390-1411.   
[29] Yang Xiaodong,Ma Tingchun, Yang Ping,et al.Security analysis of a revocable and strongly unforgeable identity-based signature scheme [J]. Information Technology and Control,2018,47 (3): 575-587.   
[30] Zhao Jing，Wei Bin，Su Yang.Communication-efficient revocable identity-based signature from multilinear maps [J]. Journal of Ambient Intelligence and Humanized Computing,2019,10 (1): 187-198.