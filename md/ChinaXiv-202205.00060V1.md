# 基于超奇异同源的零知识证明及群签名方案

赵兴波，李梦东，王 颖，朱屹霖(北京电子科技学院 密码科学与技术系，北京 100070)

摘要：Bullens 等人在CSI-Fish 中留下一个开放问题，即设计一个识别协议，允许系统挑战空间是 $\mathbb { Z } _ { N }$ ，而不是小集合 $\{ - S , \cdots , S \}$ 。本文提出了一个基于超奇异同源的零知识证明方案。该方案将挑战C作为一个同源，从而解决了这一问题，并实现了更小的稳固性误差以及公钥长度。该方案也可以通过Fiat-Shamir 变换为非交互零知识证明，进而可以在量子随机预言下实现基于超奇异同源的签名方案以及群签名方案。且本文分析了方案的安全性以及正确性。

关键词：零知识证明；超奇异；同源；群签名 中图分类号：TP doi:10.19734/j.issn.1001-3695.2021.12.0705

Zero-knowledge proof and group signatures based on supersingular isogeny

Zhao Xingbo,Li Mengdong†,Wang Ying, Zhu Yilin (Dept.ofCryptologyScience&Technology,BeijingElectronicScience&TechnologyInstitute,BeijinglOo0,China)

Abstract: Bullens etal.left anopenproblems inCSI-Fish is todeviseaidentificationprotocol thatallowsforthechallenge set to be $\mathbb { Z } _ { N }$ rather than the small set $\{ - S , \cdots , S \}$ . This paper proposed a zero-knowledge proof scheme based on supersingular isogeny.This scheme addresses theopen problemby taking thechalenge Casa isogeny,andreduces the soundness error andthesizeofpublickey.Thisschemecanbeturmedintonon-interactivezero-knowledge proofschemeusingtheFiat-Shamir transform.Then signature scheme and group signature scheme based on supersingular isogeny can be implemented under the quantum random oracles model. And this paper analyzes the security and correctness of these schemes.

Key words: zero-knowledge proof; supersingular; isogeny; group signature

# 0 引言

同源密码是后量子密码学的一个很有发展前景和研究价值的候选者。同源是两条椭圆曲线之间保持基点的同态映射，是一种群同态1。基于同源的密码系统在开始主要研究通常曲线[2.3],但因为通常曲线同源问题存在亚指数时间的量子算法，而Biasse等人[4研究发现超奇异同源问题的量子算法为指数时间，因此目前同源密码大多是超奇异椭圆曲线上的方案。

目前构造同源签名的基础主要是以下两个同源问题：计算超奇异同源(CSSI)问题[5]和类群作用逆问题(GAIP)[6]。且基于同源的签名大多是结合Fiat-Shamir 变换来构造的[7.8]。在[9,10]中提出的基于CSSI的签名方案,即使在最优化的变体[10]中也产生至少12KB大小的签名。另一方面，依靠GAIP并采用Fiat-Shamirwithaborts方法,DeFeo和Galbraith提出了一个新的签名方案，称为 SeaSign[1I]。SeaSign 提供的签名非常小，在128位安全级别下小于1千字节。最近,Beullens[12]等人通过计算理想类群，改进了 SeaSign 并获得了第一个实用的基于同源的签名方案，命名为CSI-FiSh。它允许从理想类群中进行均匀抽样，并对其元素进行规范表示。CSI-FiSh只需要390毫秒来签名或验证消息，签名大小只有263字节。因此，基于CSI-FiSh同源特征的签名是非常实用的。

通过对CSI-FiSh 方案以及其他基于超奇异同源签名方案的研究与分析，本文提出了一种基于超奇异同源的零知识证明系统。该系统改进了Bullens等人提出的CSI-Fish中的证明系统，解决了CSI-Fish中提出的开放问题，即将系统的挑战空间由小集合 $\{ - S + 1 , S - 1 \}$ 提升为CSIDH-512中理想类群的阶数 $\mathrm { ~ N ~ } _ { \circ }$ 本方案与CSI-FiSh方案相比具有更小的稳固性误差以及公钥长度，本文仅需一个椭圆曲线作为公钥。基于该证明系统，本文构造了基于超奇异椭圆曲线同源的签名方案以及群签名方案，并对签名方案的进行了安全性证明。

# 1 背景知识

# 1.1超奇异椭圆曲线及同源

椭圆曲线之间的同源 $\varphi : E \to E _ { 1 }$ 为一个态射，也是群同态且 $\varphi ( { \mathcal { O } } _ { E } ) = { \mathcal { O } } _ { E _ { 1 } }$ 。Tate指出[13]:有限域 $\mathbb { F } _ { \mathtt { p } }$ 上的两条椭圆曲线 $E$ + $\boldsymbol { E _ { 1 } }$ 是同源的当且仅当 $\# E \left( \mathbb { F } _ { q } \right) = \# E _ { 1 } \left( \mathbb { F } _ { q } \right)$ 。

对于同源 $\varphi : E \to E _ { 1 }$ ，当 $\scriptstyle { E = E _ { 1 } }$ 时称为自同态。椭圆曲线的自同态集用 $\operatorname { E n d } ( E )$ 表示，具有点加法和函数复合运算的环结构[14]。在 $\operatorname { E n d } _ { \mathfrak { p } } \left( E \right)$ 中, $E$ 的 Frobenius 自同态 $\pi$ 满足特征方程:$\pi ^ { 2 } - t \pi \ + q = 0$ ， $\mathrm { ~  ~ { ~ t ~ } ~ }$ 称为Frobenius迹。当且仅当 $\scriptstyle t = 0$ 时，曲线 $E$ 是超奇异的。Fp-有理自同态环 $\operatorname { E n d } _ { \mathfrak { p } } \left( E \right)$ 是虚二次域 $\scriptstyle { \mathrm { K = } } \mathbb { Q }$ $\mathbf { k } = \mathbb { Z } { \left( { \sqrt { - p } } \right) }$ 的序 $\mathcal { O }$ 。 $\operatorname { E n d } _ { \mathrm { p } } \left( E \right)$ 中总是包含 $Z \big [ \pi _ { \mathrm { q } } \big ]$ 这个子环。

设 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 表示在 $\mathbb { F } _ { \mathtt { p } }$ 上定义的所有超奇异椭圆曲线 $E$ 的集合，设 $\mathcal { O }$ 是虚二次域的序 $\pi \in { \mathcal { O } }$ 使得 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 非空。理想类群 $\mathrm { c l } ( { \mathcal { O } } )$ 自由地和传递地作用于集合 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ ，在 $\mathscr { O }$ 和$\operatorname { E n d } _ { \mathfrak { p } } \left( E \right)$ 之间存在一个 Frobenius 映射使得 $\varphi ( { \mathcal { O } } _ { E } ) = { \mathcal { O } } _ { E }$ 且$( x , y ) \to \left( x ^ { \mathfrak { p } } , y ^ { \mathfrak { p } } \right)$ ，用 $\star$ 表示这一作用[15]。最近，该作用 $\star$ 被用来设计几种密码原语—CSIDH及其延伸签名方案 SeaSign、CSI-Fish等。这几种方案的安全性都是基于类群作用逆问题，定义如下：

问题1(类群作用逆问题—GroupActionInverse Problem:GAIP)给定两个曲线 $E _ { 0 }$ ， $E _ { \mathrm { { l } } }$ ，其自同态环 $\begin{array} { r } { E \mathrm { n d } ( E _ { 0 } ) { = } E \mathrm { n d } ( E _ { 1 } ) = \mathcal { O } , } \end{array}$ 找到一个理想 $\mathfrak { a } \subset \mathcal { O }$ 使得 $E _ { 1 } = \mathfrak { a } \star E$ 。

# 1.2 CSI-Fish

Beullens等人提出了一种基于CSIDH-512困难性的有效签名方案。对于在CSIDH中为CSIDH-512参数集选择的素数集 $\boldsymbol { \mathrm { l } } _ { 1 } \cdots \boldsymbol { \mathrm { l } } _ { 7 4 }$ ，Beullens等人确定了自同态环的相关类群是循环的，由 $\mathrm { \bf ~ g }$ 生成，且阶数 $\scriptstyle \mathbf { N = c l } ( { \mathcal { O } } )$ 由下式给出

$N = 3 \times 3 7 \times 1 4 0 7 1 8 \times 5 1 5 9 3 6 0 4 2 9 5 2 9 5$ 867744293584889×31599414504681 99585300827874558732204909

对于任何理想 $\mathfrak { a } \in \mathrm { c l } ( \mathcal { O } )$ ，可以写作 ${ \mathfrak { a } } { = } { \mathfrak { g } } ^ { \mathrm { a } }$ ，其中 $\mathbf { a } \in \mathbb { Z } _ { N }$ ，因为群是循环的。只要使用CSIDH-512参数集，任何人都可以对类群元素进行均匀采样，并拥有唯一的表示。对于与 $\phantom { + } E _ { 0 }$ 同源的椭圆曲线 $E ^ { \prime }$ ，简化符号 ${ \mathfrak { a } } \star E _ { 0 } = [ { \mathfrak { a } } ] E _ { 0 }$ 有了这个符号，就有了 $[ \mathrm { a } ] ( [ \boldsymbol { \mathsf { b } } ] E _ { 0 } ) { = } [ \mathrm { a } + \boldsymbol { \mathsf { b } } ] E _ { 0 } ^ { \phantom { + } } [ 1 2 ]$ 0

# 1.3零知识证明

零知识证明(zero-knowledge proof $\because$ ZKP)是证明者和验证者之间的双方协议，证明者通过和验证者交互，向验证者证明它知道一些秘密信息，而除了声明本身已经揭示的之外，不透露任何关于秘密的信息。

对于一个语言 $L \subseteq \left\{ 0 , 1 \right\} ^ { * }$ ，其中的串 $\textbf { \^ { x } }$ 都伴随着一个二元关系 $\mathbb { R } \subseteq \left\{ 0 , 1 \right\} ^ { * } \times \left\{ 0 , 1 \right\} ^ { * }$ ，存在w 使得 $( x , w ) \in \mathbb { R }$ ，w称为 $\mathbf { x } \in L$ 的证据(witness)。参考[16]，下面对零知识证明进行定义：

定义1设(P,V)是一个双方协议，其中 $\mathrm { \Delta V }$ 是概率多项式时间(probabilistic polynomial time:PPT)算法，设 $\textbf { \em L }$ ， $L ^ { \prime } \subseteq$ $\left\{ 0 , 1 \right\} ^ { * }$ 是具有二元关系 $R$ ， $\scriptstyle { R ^ { \prime } }$ 的语言，使得 $R \subseteq R ^ { \prime }$ 当且仅当它满足下列条件，那么 $( P , V )$ 称为 $\textbf { \em L }$ ， $\boldsymbol { L ^ { \prime } }$ 具有完全性误差 $\alpha$ ，挑战集 $C$ ，公共输入 $x$ 和秘密输入 $w$ 的 $\Sigma$ 协议。

三轮形式(Three-moveform):协议的形式如下:证明者 $P$ 在输入 $( x , w )$ 时，计算承诺 $\mathbf { \chi } _ { t }$ 并将其发送给验证者 $V _ { \mathrm { { c } } }$ ，验证者$V$ 在输入 $\textbf { x }$ 时，选择一个挑战 $c  C$ 并将其发送给 $P$ 。证明者向验证者发送一个响应r。根据协议文本 $\left( t , c , r \right)$ ，验证者最终接受或拒绝证明。

证明系统需要具有以下三个性质：

完全性(Completeness):对于一个诚实的证明者 $P$ 和验证者 $V _ { ; }$ ，当任一 $( x , w ) \in \mathbb { R }$ ，则验证者接受的概率至少为 $_ { 1 - \alpha }$ 。

特殊稳固性(Specia Soundness):存在一种PPT 算法 $K ($ 知识提取器)，其将满足 $c \neq c ^ { \prime }$ 的两个接受文本 $\left( t , c , r \right)$ ， $\left( t , c ^ { \prime } , r ^ { \prime } \right)$ 作为输入，并输出 $w ^ { \prime }$ ，使得 $\left( x , w ^ { \prime } \right) \in R ^ { \prime }$ 。稳固性误差 $\delta { = } 1 / \mathrm { C }$ 。

诚实验证者零知识(Honest-Verifier Zero Knowledge:HVZK):存在以 $\mathbf { x } \in L$ 和 $\mathsf { c } \in C$ 为输入的 $P P T$ 模拟器，该算法输出 $\left( t , r \right)$ ，使得三元组 $\left( t , c , r \right)$ 与由真实协议运行生成的协议文本不可区分[16]。

一个3轮-特殊稳固的-诚实验证者零知识证明协议，可以应用Fiat-Shamir转换将其转换为非交互式零知识证明协议。

定义2一个规范的认证方案 $\mathrm { I D } { = } ( K , P , V , c )$ ,其中 $K$ 是概率多项式时间的密钥生成算法,在输入安全参数入时输出一对 $\left( p k , s k \right) ; P$ 也是PPT 算法，输入sk 输出一条消息 m; $\mathrm { ~ c ~ } \geq$ 1是挑战的整数位长度； $V$ 是一种确定性多项式时间验证算法，将pk和证明文本作为输入，输出0或 $1 ^ { [ 1 7 ] }$ 。

# 1.4签名

一个签名方案 $\mathrm { \Delta S = }$ (KeyGen,Sign,Verify）由如下三个算法组成:

·KeyGen(1）：密钥生成算法输入安全参数入，输出一对公/私钥对 $\left( p k , s k \right)$ 。

· Sign $\left( s k , m \right)$ ：签名算法输入私钥 sk 和消息 m，输出一个签名 $\sigma$ 。

·Verify $\mathrm { { ( p k , m , s ) } }$ ：验证算法输入公钥pk，消息m 和签名 $\sigma$ ，输出一个比特,1代表 $\sigma$ 是消息 $\mathrm { ~ m ~ }$ 的一个合法签名,0代表不合法。

定义3选择消息攻击下的不可伪造性：EUF-CMA 安全,如果对于所有 PPT 敌手 A，有 $\mathrm { A d v _ { A , S } ^ { E U F - C M A } ( l ^ { \lambda } ) = P r [ A \ w i n ] = n e g l }$ (1）则一个签名方案S是EUF-CMA安全的[18]。

定理1[10]设R与生成算法K是困难关系，令 $( P , V )$ 是 $\Sigma$ 协议中R的证明者和验证者，对于某些整数 $\mathbf { c } \geqslant 1$ 具有c比特挑战。假设Σ协议是完整的，特殊稳固的以及诚实验证者零知识的。那么(K,P,V,c)是一个规范的识别方案，在被动攻击下是安全的。

定理2[10]令ID是一个规范的认证方案，在被动攻击下是安全的。设S为使用Fiat-Shamir变换从ID中导出的签名方案。在随机预言模型下，S在选择消息攻击下是不可伪造的。

# 1.5群签名

下面介绍群签名的定义以及安全模型。

定义4群签名。群签名方案由下面的五个多项式时间算法组成:

·GSetup:输入安全参数，生成系统公共参数和群公，私钥对 $\left( \mathbf { G } \mathbf { M } _ { \mathrm { p k } } , \mathbf { G } \mathbf { M } _ { \mathrm { s k } } \right)$ ·

·GJion：成员加入是由用户和群管理员执行的交互式算法，若算法成功，则用户成为有效的群成员，并得到公、私钥对 $\big ( \mathrm { U } _ { \mathrm { p k } } , \mathrm { U } _ { \mathrm { s k } } \big )$ ·，

·GSign：对于给定的消息m，其签名由管理员和群成员共同合作完成;

·GVerify：验证者根据群公钥和消息m对签名进行验证;

·GTrace:通过该算法，管理员GM可以找出对消息m真正的签名者。

群签名的安全性定义需满足以下性质：

1）正确性：对于给定的消息m，只有经合法的群成员运行签名算法产生的群签名才能够被正确的验证。

2）不可伪造性：只有合法的群成员通过和管理员交互才能够产生被验证正确的群签名。

3）匿名性：只有群管理员能够确定签名者的身份，其他人只能验证群签名是否正确。

4)可跟踪性：当出现矛盾争端的时候，管理员可以通过追踪算法打开群签名，识别出具体的签名者身份，并给出证据。

5)抗合谋性：即使多个群成员合谋在一起，也不能产生有效的被管理员追踪不到的群签名。

# 2 新的零知识证明以及签名方案

# 2.1零知识证明的身份认证协议

对于CSIDH-512参数集,CSI-FiSh指出其理想类群是循环的，具有已知阶数N和生成元g。只要使用CSIDH-512参数集，任何人都可以对类群元素进行均匀采样，并拥有唯一的表示。在此基础上，本文描述了新的基于超奇异同源问题的身份认证协议(如图1)，与CSI-Fish 中的身份认证协议相比，本文的认证协议实现了更小的稳固性误差(soundnesserror)，且具有更小的公钥长度。

零知识证明协议的设置如下：

参数设置：选取大素数 $\mathrm { p { = } } 4 { \cdot } \mathrm { l _ { \mathrm { 1 } } } { \cdot } { \cdot } { \cdot } \mathrm { l _ { \mathrm { n } } } { - } 1$ ，其中 $\mathrm { \Delta l _ { i } }$ 是小的不同的奇素数，给定集合 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 和理想类群以及在 $\mathbb { F } _ { \mathfrak { p } }$ 上具有自同态环的超奇异椭圆曲线 $\phantom { + } E _ { \phantom { + } \mathrm { { \scriptscriptstyle 0 } } }$ ，为了证明秘密 $\boldsymbol { a }$ 的知识，证明者与验证者进行如下£协议操作，如图2。

密钥生成：选取一个随机的同源 $[ a ] \colon E _ { 0 } \to E _ { 1 }$ ，得到一个随机椭圆曲线 $E _ { 1 }$ 。公钥为 $E _ { 1 }$ ，密钥为 $\boldsymbol { a }$ 。

识别协议如下：

承诺：证明者随机选取 $b \in _ { R } \mathbb { Z } _ { N }$ ，且 $b \neq a$ ，将 $\scriptstyle { E = \left[ { \mathfrak { b } } \right] E _ { 0 } }$ 发送给验证者。

挑战：验证者检验 $E$ 是否等于 $E _ { 1 }$ ，若相等，则拒绝。否则随机选取挑战 $\mathbf { c } \in \mathbb { Z } _ { N }$ ，然后发送给证明者。

响应：证明者发送 $r = c + b - a { \bmod { N } }$ 给验证者。

验证：验证者检查是否 ${ \big [ } \mathbf { r } { \big ] } E _ { 1 } = { \big [ } c { \big ] } E = E _ { 2 }$ ，相等则接受；否

则拒绝。

![](images/2074784251328926087a5233bdc5b0e7a4475019927f8f40f1b460ad6e423406.jpg)  
图1 识别协议

![](images/fb3d1962edeaf33bbab90b83bd0389add3c61b6273af68ed6b61afe03b2912fc.jpg)  
图2零知识证明  
Fig.2Zero knowledge proof

# 2.2安全性分析

定理3基于同源的识别协议是一个完整和安全的 $\Sigma$ 协议，它具有完全性、特殊稳固性以及诚实验证者零知识的。

证明：完全性：假设证明者的行为总是诚实的，即其知道一个秘密 ${ E } _ { \mathrm { { l } } } = \left[ \mathrm { { a } } \right] { E } _ { \mathrm { { 0 } } }$ 。验证者检查 ${ \big [ } \mathbf { r } { \big ] } E _ { 1 } = { \big [ } c { \big ] } E = E _ { 2 }$ 是否成立,因为$[ \Gamma ] E _ { 1 } = [ c ] [ b ] [ a ] E _ { 1 } = [ c ] [ b ] [ a ] [ - a ] E _ { 0 } = [ c ] [ b ] E _ { 0 } = [ c ] E$ 这证明了验证者总是接受诚实生成的证明。

特殊稳固性：给定两个具有不同挑战的有效证明，即$\pi = \left( E , c , r \right)$ 和 $\pi ^ { \prime } { = } \big ( E , c ^ { \prime } , r ^ { \prime } \big )$ ，其中 $c \neq c ^ { \prime }$ 那么 $\boldsymbol { r } \neq \boldsymbol { r } ^ { \prime }$ 。本文有${ \big [ } \mathrm { r } { \big ] } E _ { 1 } = { \big [ } c { \big ] } E$ 以及 ${ \big [ } \mathbf { r } ^ { \prime } { \big ] } E _ { 1 } = { \big [ } c ^ { \prime } { \big ] } E$ ，因此可以提取 ${ \big ( } c - c ^ { \prime } { \big ) } + { \big ( } r - r ^ { \prime } { \big ) }$ ，其为GAIP问题的一个解。与此同时，作弊证明者不能通过验证，除非它成功猜测挑战c。特别是，由于挑战空间现在是 $\mathbb { Z } _ { \scriptscriptstyle N }$ ，其中包含 $\mathrm { ~  ~ N ~ }$ 个元素，所以该协议实现了1/N的稳固性误差。

诚实验证者零知识：为了模拟证明，从 $\mathbb { Z } _ { N }$ 中随机抽取样本c，模拟器从 $\mathbb { Z } _ { N }$ 中随机抽取 $\mathrm { ~ \bf ~ r ~ }$ 。计算 $E _ { 2 } = \left[ \mathbf { r } \right] E _ { 1 }$ 并输出证明$\pi = \left( E , c , r \right)$ 。根据决策GAIP问题，模拟器生成的证明与诚实执行的挑战等于c的协议证明是无法区分的，因为真实证明和模拟证明都具有 $\boldsymbol { r }$ 以及 $E _ { 2 } = \left[ \mathbf { r } \right] E _ { 1 }$ 的均匀随机分布值作为响应，因此该认证协议诚实验证者零知识的。

# 2.3签名方案

在算法1到算法3中描述了基于同源的签名方案，该方案的安全性基于GAIP困难假设。它是通过对2.1节中介绍的零知识证明协议应用Fiat-Shamir变换得到的。其主要思想是用临时密钥E以及消息 $\mathbf { m }$ 的哈希值来替换挑战c，即$c = H { \bigl ( } E \| m { \bigr ) }$ 。签名 $\sigma$ 由 $r , E$ 组成，验证者计算 $c ^ { \prime } { = } H \bigl ( E \| m \bigr )$ ，并检查是否[r] $E _ { \scriptscriptstyle 1 } = \bigl [ c ^ { \prime } \bigr ] E$ 。为了减少了签名的大小，

下面详细描述了基于超奇异同源的签名方案，具体如下：算法1 KeyGen输入：初始曲线 $\phantom { + } E _ { 0 }$ 以及理想类群的阶数输出：公、私钥对 $( s k , p k )$ ·$a \gets _ { R } \mathbb { Z } _ { N }$ （204号${ \cal E } _ { 1 } = \big [ a \big ] { \cal E } _ { 0 }$ （204号 $p k = E _ { \mathrm { 1 } }$ return $\begin{array} { r } { ( s k = a , p k = E _ { 1 } } \end{array}$ 算法2 Sign输入：消息 $\mathfrak { m }$ 以及私钥sk输出：签名 $\sigma = \left( r , E \right)$ ：$b  { \bf \infty } _ { R } \mathbb { Z } _ { N } , b \neq a$ ${ \cal E } = \big [ b \big ] { \cal E } _ { 0 }$ $c = H { \bigl ( } E \| m { \bigr ) }$ $r = c + b - a \bmod N$ return $\sigma = \left( r , E \right)$ （204号算法3Verify输入：消息 $\mathfrak { m }$ 2 $\phantom { + } E _ { 0 }$ ,公钥pk以及签名o输出：Valid 或Invalid.$( r , E ) \gets \sigma$ $c ^ { \prime } { = } H \bigl ( E \| m \bigr )$ If ${ \big [ } \mathbf { r } { \big ] } E _ { 1 } = { \big [ } c ^ { \prime } { \big ] } E$ then1．return Valid2.Else3.return Invalid

# 2.4安全性分析

定理4在随机预言模型中，上述基于超奇异同源的签名方案具有选择消息攻击下的不可伪造性，即EUF-CMA安全。

证明：如上一节所示，该身份认证方案(∑ 协议)具有特殊稳固性和诚实验证者零知识。因此，定理1意味该认证方案是安全的，可以抵御假冒被动攻击。由定理2可知，该签名方案在随机预言模型中是EUF-CMA安全的。

# 2.5对比分析

CSI-Fish中描述的基础身份认证协议如下:证明者为了证明其知道一个群元素a使得 ${ \cal E } _ { \mathrm { 1 } } = \big [ a \big ] { \cal E } _ { \mathrm { 0 } }$ ，然后证明者随机选取$\mathbf { b } \in \mathbb { Z } _ { N }$ ，并将 $\scriptstyle { E = \left[ b \right] E _ { 0 } }$ 发送给验证者。验证者随机选取比特 $\mathbf { \boldsymbol { c } } \in$ $\{ 0 , 1 \}$ ，然后发送给证明者。当 $\scriptstyle { \mathsf { c } } = 0$ 时，证明者回复 $\scriptstyle \mathbf { r } = \mathbf { b }$ ，验证者检查是否 $\boldsymbol { E = } \boldsymbol { \left[ r \right] } \boldsymbol { E _ { 0 } }$ ；当 $\scriptstyle { \mathsf { c } } = 1$ 时，证明者回复 $r { = } b { - } a { \bmod { N } }$ ，验证者检查 $E$ 是否等于 $[ r ] E _ { \scriptscriptstyle 1 }$ 。该协议的挑战空间仅为二进制比特 $\mathbf { c } \in \{ 0 , 1 \}$ ，公钥长度为1个曲线。

为了降低稳固性误差，CSI-Fish增加了挑战空间，但这也增加了公钥的大小。其方法为选择一个正整数S，密钥是 S-1维的向量，如 $( a _ { 1 } , \cdots , a _ { s - 1 } )$ ，公钥为 $\left( E _ { 0 } , [ a _ { 1 } ] E _ { 0 } , \cdots , [ a _ { s - 1 } ] E _ { 0 } \right)$ 。证明者现在必须证明它知道一个秘密 $s \in \mathbb { Z } _ { N }$ ，使得 $E _ { j } = \left[ s \right] E _ { i }$ 出现在公钥列表中的某对椭圆曲线上。证明者再次随机选择 $\mathfrak { b } \in \mathbb { Z } _ { N }$ ，并通过 ${ \cal E } = \left[ b \right] { \cal E } _ { 0 }$ 来对它进行承诺。验证者从集合 $\{ - S + 1 , S - 1 \}$ 中均匀地采样挑战c，证明者用 $\mathbf { r } = \mathbf { b } - \mathbf { a } _ { c } { \bmod { N } }$ 来响应。验证检查$\boldsymbol { E } = \left[ r \right] \boldsymbol { E } _ { c }$ ，当c为负值时，有 $E _ { - c } = E _ { c } ^ { t }$ 。CSI-FiSh 的这种适应方案实现了1/2S-1的安全稳固性，公钥长度为S-1个曲线。

在CSI-FiSh的基础上，证明者可以简单地模仿基于离散对数的构造，因为现在可以在环 $\mathbb { Z } _ { N }$ 中工作，因此可以创建特有的响应，来表达临时密钥、秘密密钥和挑战的组合。然而,主要的问题是验证者如何验证这个组合是正确的，因为当考虑曲线 $g ^ { a } \star E$ 时，群作用只允许在 $\mathrm { \bf ~ g }$ 的指数上增加一个已知的常数。也就是，若像在经典DH中进行系数乘 $( r = b + a c )$ 的形式，则群作用就成为了映射 $g ^ { a }  ( g ^ { a } ) ^ { c }$ ，但在环 $\mathbb { Z } _ { N }$ 的环境下是不存在这种类似映射的[18]。

本文方案将挑战 $\mathbf { \Psi } _ { c }$ 视作一个同源，这样做的好处是可以将临时密钥 $b$ 和挑战 $\boldsymbol { \mathscr { c } }$ 结合到一起，变为 $\left[ b + c \right]$ 的形式,避免出现 $g ^ { a }  ( g ^ { a } ) ^ { c }$ 的情况。且这样做使得挑战c可以在环 $\mathbb { Z } _ { { N } }$ 中随机选取，也就使得挑战空间变为类群阶数N，从而实现了1/N的安全稳固性。但是采用这种方案的缺点是需要多计算一次同源，即 $\boldsymbol { E _ { 2 } } = \left[ c \right] \boldsymbol { E }$ ，这增加了计算时间，提高了额外计算量。本文的方案公钥长度为1个椭圆曲线。表1、表2分别给出了本文方案与CSI-Fish中的识别协议与签名方案的比较结果，

Tab.1 Comparison of Identification protocol   

<html><body><table><tr><td>方案</td><td>公钥长度</td><td>挑战空间</td><td>稳固性误差</td><td>同源次数</td></tr><tr><td>CSI-Fish基础方案</td><td>1</td><td>{0,1}</td><td>1/2</td><td>2</td></tr><tr><td>CSI-Fish适应方案</td><td>S-1</td><td>{-S+1,S-1}</td><td>1/2S-1</td><td>2</td></tr></table></body></html>

表2签名方案比较

表1识别协议方案比较  

<html><body><table><tr><td>方案</td><td>公钥长度</td><td>签名长度</td><td>同源次数</td></tr><tr><td>CSI-Fish签名方案</td><td>S</td><td>2S</td><td>2S</td></tr><tr><td>本文签名方案</td><td>1</td><td>2</td><td>2</td></tr></table></body></html>

# 3 基于新ZK的群签名方案

在群签名中，为了代表群签名，群成员需要生成一个NIZK来证明他有一个有效的密钥/公钥对。签名包括密文和证明(消息嵌入在证明中)。为了验证签名，验证者只是检查证明的有效性。下面，本文给出了本文的群签名方案的详细描述。它与[19]一样借助状态列表的方法实现群签名,[19]中采用双线性映射来实现成员的身份认证，但本文采用上面提出的同源ZK来实现。用同源来实现群签名方案的优点是密钥短、抗量子攻击等，但缺点是计算量更大，计算时间较长。

本群签名方案存在公钥状态列表 $L _ { P K }$ 、群管理员GM、群成员 $U _ { i }$ 以及可信时间戳机构4类实体。其中，公钥状态列表中显示当前群成员的身份信息 $I D _ { i }$ 、公钥 $E _ { i }$ 、授权签名起始时间 $T i m e _ { s t a r t }$ 和终止时间 $\mathrm { T i m e } _ { \mathrm { e n d } }$ ；管理员GM负责群成员的加入、群签名的追踪以及实时更新维护，并向所有群成员广播最新的 $L _ { P K }$ ；可信时间戳机构负责向群管理员及群成员提供时间戳服务；群成员 $\mathrm { \Delta U _ { i } }$ 负责完成群签名。

# 3.1基于超奇异同源的群签名方案

本文方案包含系统建立、成员加入、签名、验证和追踪五个步骤。

# 1）系统建立

选取大素数 $\mathsf { p { = } } 4 \cdot \mathsf { l _ { \mathrm { 1 } } } \cdots \mathsf { l _ { \mathrm { n } } } - 1$ ，其中 $\mathrm { \Delta l _ { i } }$ 是小的不同的奇素数，给定集合 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 和理想类群以及在 $\mathbb { F } _ { \mathtt { p } }$ 上具有自同态环的超奇异椭圆曲线 $E _ { _ { 0 } }$ ， $H _ { 1 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { N }$ ， $H _ { 2 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { N }$ 。对于GM:取$x  _ { R } \mathbb { Z } _ { N }$ ，计算 $E _ { G M } = \big [ \boldsymbol { x } \big ] E _ { 0 }$ ，其中 $\textbf { x }$ 为群管理员私钥， $E _ { G M }$ 为公钥。故群公共参数为 $\left\{ p , N , E _ { 0 } , H _ { 1 } , H _ { 2 } \right\}$ ，群公钥为 $E _ { G M }$ 。

# 2）成员加入

成员 $U _ { i }$ 想要加入，先随机选取 $x _ { i } , a _ { i }  _ { R } \mathbb { Z } _ { N }$ ，计算${ E } _ { i } = \left[ \boldsymbol { x } _ { i } \right] { E } _ { 0 }$ ， $h _ { i } = a _ { i } +$ $H _ { 1 } ( I D _ { i } ) { \bmod { N } }$ ， $E _ { m i } = \left[ a _ { i } \right] E _ { 0 }$ ，最后将$\left( I D _ { i } , E _ { I D i } , E _ { i } , h _ { i } \right)$ 发送给 $\mathrm { G M } _ { \circ }$ 其中 $I D _ { i }$ 代表成员 $U _ { i }$ 的现实身份信息。

收到 $\left( I D _ { i } , E _ { I D i } , E _ { i } , h _ { i } \right)$ 后，GM先验证等式 $\big [ H _ { 1 } \big ( I D _ { i } \big ) \big ] E _ { I D i } = \big [ h _ { i } \big ] E _ { 0 }$ 是否成立，确认 $I D _ { i }$ 的有效性。若成立，计算 $E _ { \scriptscriptstyle G M i } = \left[ x \right] E _ { i }$ ，将$E _ { G M i }$ 发送给 $U _ { i }$ ，并存储 $I D _ { i }$ 、 $E _ { i }$ 。其中 $I D _ { i }$ 、 $E _ { i }$ 以及时戳Time构成公开的公钥状态列表 $L _ { P K }$ 见表3。

成员 $U _ { i }$ 收到 $E _ { G M i }$ 后，计算 $E _ { G M i } = \left[ x _ { i } \right] E _ { G M }$ 是否成立。若成立,则成员 $U _ { i }$ 公钥为 $E _ { i }$ ，私钥为 $x _ { i }$ 。

# 3）群签名过程

群成员 $U _ { i }$ 对消息 $\mathrm { ~ m ~ }$ 进行签名，需要和管理员GM共同完成。

群成员 $U _ { i }$ 随机选择 $b _ { i }  _ { R } \mathbb { Z } _ { N }$ ，并向可信时间戳机构请求当前时间Time，然后计算 $\begin{array} { r } { E _ { b i } = \big [ b _ { i } \big ] E _ { 0 } } \end{array}$ ， $t _ { i } = H _ { 2 } \big ( E _ { i } \big \| E _ { 0 } \big \| E _ { b i } \big \| m \big )$ ，$s _ { i } = t _ { i } + b _ { i } - x _ { i } \ \mathrm { m o d } \ N$ ，群成员 $U _ { i }$ 将 $( T \mathrm { i m e } , E _ { i } , m , E _ { b i } , s _ { i } )$ 发送给 $\mathbf { G M }$ 。

表3公钥列表 $\mathbf { L } _ { \mathrm { P } k }$   
Tab.3Public Key list $\mathrm { l } _ { \mathrm { p } k }$   

<html><body><table><tr><td>序号</td><td>群成员</td><td>成员公钥</td><td>开始时间</td><td>终止时间</td></tr><tr><td>i</td><td>IDi</td><td>E</td><td>Time start-i</td><td>Timeend-i</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr></table></body></html>

注：公钥状态列表 $L _ { P K }$ 的实时维护由群管理员GM负责，每当群成员加入或撤销,都要实时更新 $L _ { P K }$ ，并向所有群成员广播最新的 $L _ { P K }$ ，同时将 $( I D _ { i } , E _ { i } , T i m e _ { s t a r t - i }$ ， $T i m e _ { e n d - i } )$ 发送给群成员 $U _ { i }$ ，作为群成员 $U _ { i }$ 的群签名证书。设计一个公钥状态列表$L _ { P K }$ 可以实现动态地增加和撤销群成员，提高执行效率。在撤销某个群成员时，只需将 $L _ { P K }$ 中群成员对应的终止时间修改为当时的时间即可。当成员被撤销后，它不可以生成新的合法群签名。当群成员公钥有效时，可以将其终止时间设置为一个足够大的值。

GM接收到 $\left( E _ { i } , m , E _ { b i } , s _ { i } \right)$ 后，先根据 $E _ { i }$ 值查找 $L _ { P K }$ ，看其在当前时间是否为有效值;若有效,则检验 $\mathbf { t } _ { i } ^ { \prime } = H _ { 2 } ( E _ { i } \parallel E _ { 0 } \parallel E _ { b i } \parallel m )$ ，且 $\big [ t _ { i } ^ { \prime } \big ] E _ { b i } = \big [ s _ { i } \big ] E _ { i }$ 是否成立。若成立，则管理员GM计算$E _ { v i } = \left[ x + t ^ { \prime } \right] E _ { 0 }$ 。并将 $I D _ { T r a } = ( I D _ { i } , m , E _ { v i } , t _ { i } ^ { \prime } , s _ { i } )$ 存储到追踪列表，如表4.群成员对消息 $\mathbf { m }$ 的签名记为 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 。

Tab.2Comparison of Signature scheme   
表4追踪列表LTrack  
Tab.4Track list $\mathbf { l } _ { t r a c k }$   

<html><body><table><tr><td>序号</td><td>群成员</td><td>IDTra</td></tr><tr><td>i</td><td>IDi</td><td>IDTra=(ID,m,Evi,t,)</td></tr><tr><td>：</td><td>：</td><td>：</td></tr></table></body></html>

4)验证

验证者接收到签名后，检验 $E _ { v i } = \big [ t _ { i } ^ { \prime } \big ] E _ { G M }$ 是否成立。若成立,则接受 $\sigma _ { i } = \left( E _ { v i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 为消息 $\mathbf { m }$ 的群签名；否则，不接受。

# 5）追踪

关于签名 $\sigma _ { i } = \left( E _ { v i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 产生矛盾分歧时，群管理员可以通过查询追踪列表中对应的 $t _ { i } ^ { \prime } , s _ { i }$ 追踪到该签名的签名人 $U _ { i }$ 的身份，GM根据签名追踪列表中的 $I D _ { T r a } = \left( I D _ { i } , m , E _ { v i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 信息，查找相应 $I D _ { i }$ 证明该签名确实是群成员 $U _ { i }$ 产生的。

# 3.2 正确性分析

该方案中的系统建立存在管理员与成员双向验证身份的过程。

1)成员加入过程中管理员与成员互验身份。

管理员GM接收到成员 $U _ { i }$ 送的 $\left( I D _ { i } , E _ { I D i } , E _ { i } , h _ { i } \right)$ 后，检验$\big [ H _ { 1 } \big ( I D _ { i } \big ) \big ] E _ { I D i } = \big [ H _ { 1 } \big ( I D _ { i } \big ) \big ] \big [ a _ { i } \big ] E _ { 0 } = \big [ h _ { i } \big ] E _ { 0 }$ 成立，则证明了 $I D _ { i }$ 的有效性。管理员完成对成员的检验后，计算 $E _ { \scriptscriptstyle G M i } = \left[ x \right] E _ { i }$ 并将其发送给$U _ { i }$ ， $U _ { i }$ 验证 $E _ { { \scriptscriptstyle G M i } } = \left[ x _ { i } \right] E _ { { \scriptscriptstyle G M } }$ 是否成立，确认GM的身份。

2)签名过程中验证成员身份。

群管理员GM和群中成员 $U _ { i }$ 协作生成群签名。在GM接收到 $( T \mathrm { 1 m e } , E _ { i } , m , E _ { b i } , s _ { i } )$ 后，先首先检验 $U _ { i }$ 在当前时间内是否存在，若成立，则检验 $t _ { i } ^ { \prime } = H _ { 2 } \left( E _ { i } \parallel E _ { 0 } \parallel E _ { b i } \parallel m \right)$ ，且 $\big [ t _ { i } ^ { \prime } \big ] E _ { b i } = \big [ s _ { i } \big ] E _ { i }$ 是否成立，若成立，则证明发送方确为群中成员 $U _ { i }$ 。

3)签名的正确性。

验证签名中 $E _ { \nu i }$ 的有效性，即检验 $E _ { v i } = \left[ x + t _ { i } ^ { \prime } \right] E _ { 0 } = \left[ t _ { i } ^ { \prime } \right] E _ { G M }$ 证明群管理员参与了签名过程。

验证 $t _ { i } ^ { \prime } = H _ { 2 } \left( E _ { i } \parallel E _ { 0 } \parallel E _ { b i } \parallel m \right)$ 的正确性，即验证:

$$
\begin{array} { r l } & { t _ { i } ^ { \prime } = H _ { 2 } \left( E _ { i } \parallel E _ { 0 } \parallel E _ { b i } \parallel m \right) = H _ { 2 } \left( E _ { i } \parallel E _ { 0 } \parallel \left[ b _ { i } \right] E _ { 0 } \parallel m \right) } \\ & { = H _ { 2 } \left( E _ { i } \parallel E _ { 0 } \parallel \left[ s _ { i } + x _ { i } - t _ { i } \right] E _ { 0 } \parallel m \right) } \end{array}
$$

仅需验证 $\big [ b _ { i } \big ] E _ { 0 } = \big [ s _ { i } + x _ { i } - t _ { i } \ \mathrm { m o d } \ N \big ] E _ { 0 }$ 。

因为 $s _ { i } = t _ { i } + b _ { i } - x _ { i } \ \mathrm { m o d } \ N$ ，所以 $\left[ b _ { i } \right] E _ { 0 } = \left[ s _ { i } + x _ { i } - t _ { i } \right.$ mod $N ] E _ { 0 } =$

$$
\begin{array} { r } { \left[ s _ { i } - t _ { i } \mathrm { ~ m o d ~ } N \right] E _ { i } = \left[ s _ { i } - t _ { i } ^ { \prime } \mathrm { ~ m o d ~ } N \right] E _ { i } } \end{array}
$$

通过以上分析，证明了本文所提方案的正确性。

# 3.3 安全性分析

定理5匿名性.对于任意多项式时间敌手A，本方案在随机预言模型下是匿名的。

证明：通过挑战者C和敌手A之间的游戏完成证明。

$G _ { 0 }$ 游戏如下:

1）挑战者C 输入安全参数 $p { = } 4 \cdot l _ { 1 } \cdots l _ { n } - 1$ ，其中 $l _ { i }$ 是小的不同的奇素数，给定集合 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 和理想类群 $_ { c l ( \mathcal { O } ) }$ 以及在 $\mathbb { F } _ { \mathfrak { p } }$ 上具有自同态环的超奇异椭圆曲线 $E _ { _ { 0 } }$ ， $H _ { 1 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { N }$ ，$H _ { 2 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { _ { N } }$ 。随机选取 $\mathbf { \Delta } x \gets _ { R } \mathbb { Z } _ { N }$ ，计算 $E _ { _ { G M } } = \big [ \boldsymbol { x } \big ] E _ { _ { 0 } }$ 。公开群公共参数为 $\left\{ p , N , E _ { 0 } , H _ { 1 } , H _ { 2 } \right\}$ 以及群公钥 $E _ { { } _ { G M } }$ ，保留私钥 $\mathbf { x }$ 。

2)敌手A输入需签名的消息 $\mathrm { ~ m ~ }$ ，两个群成员$U _ { i _ { 0 } } , U _ { i _ { 1 } } \in L _ { p k }$ 给挑战者C，挑战者C选取 $ { \mathbf { b } } = 0$ ，其中 $b \in \{ 0 , 1 \}$ ，生成群成员 $U _ { _ { i _ { b } } }$ 对应的私钥 $x _ { i _ { 0 } } \in _ { R } \mathbb { Z } _ { N }$ ，令实际群成员 $U _ { \mathrm { { \scriptscriptstyle i } } } = U _ { \mathrm { { \scriptscriptstyle i } _ { 0 } } }$ 执行签名算法。

3)挑战者C运行签名算法,生成签名 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ ，并发送给敌手 A。

4）敌手A收到签名后给出关于b的猜测。

$G _ { 1 }$ 游戏如下:

$G _ { 1 }$ 游戏与 $G _ { 0 }$ 游戏的过程类似，其区别在于挑战者C选取 ${ \mathfrak { b } } = 1$ ，其中 $b \in \{ 0 , 1 \}$ ，生成群成员 $U _ { i _ { b } }$ 对应的私钥 $x _ { i _ { b } } \in _ { R } \mathbb { Z } _ { N }$ ，并用群成员 $U _ { i _ { 1 } }$ 对应的私钥执行签名算法，生成签名$\sigma _ { i } ^ { * } = \left( E _ { v i } ^ { * } , t _ { i } ^ { \ast } , s _ { i } ^ { * } \right)$ ，并发送给敌手A。敌手A收到签名后给出关于b的猜测。

下面说明假设敌手A赢得匿名性攻击游戏的优势$A d \nu _ { A } ^ { a n o n } = \left| \mathrm { P r } \left[ b ^ { * } = b \right] - 1 / 2 \right| = \varepsilon$ 是可忽略的，只需要证明挑战者C用成员 $U _ { i _ { b } }$ 的私钥计算生成的群签名 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 与用群成员 $U _ { i _ { 1 - b } }$ 的私钥计算生成的群签名 $\sigma _ { i } ^ { * } = \left( E _ { * i } ^ { * } , t _ { i } ^ { * } , s _ { i } ^ { * } \right)$ 是不可区分的即可。

对于签名 $\sigma _ { i }$ ，由签名过程易知，当挑战者C用成员 $U _ { i _ { b } }$ 的私钥计算签名时，均匀抽样 $b _ { i }  _ { R } \mathbb { Z } _ { N }$ ， $t _ { i } = H _ { 2 } \big ( E _ { i } \| E _ { 0 } \| E _ { b i } \| m \big )$ ，$s _ { i } = t _ { i } + b _ { i } - x _ { i } \ { \bmod { N } }$ ，最终生成签名 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ ；当挑战者C用成员 $U _ { i _ { 1 - b } }$ 的私钥计算签名时，均匀抽样 $b _ { i } ^ { * }  _ { R } \mathbb { Z } _ { N }$ ，并最终生成签名 $\sigma _ { i } ^ { * } = \left( E _ { v i } ^ { * } , t _ { i } ^ { \ast } , s _ { i } ^ { * } \right)$ 。根据决策CSIDH，签名 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 与$\boldsymbol { \sigma _ { i } ^ { * } } = \left( \boldsymbol { E _ { v i } } ^ { * } , t _ { i } ^ { \kappa } , \boldsymbol { s _ { i } } ^ { * } \right)$ 是不可区分的。因此，敌手A的优势是 $A d \nu _ { A } ^ { a n o n }$ 可以忽略的。

综上所述，本文提出的基于超奇异同源的群签名满足随机预言模型下的匿名性。

定理6不可伪造性。如果GAIP问题是困难的，本文提出的基于超奇异同源的群签名在随机预言模型下是不可伪造的。

证明：通过挑战者C 和敌手A之间的游戏完成证明。假设敌手A能够以不可忽略的概率ε成功伪造签名，下面将展示挑战者C如何利用敌手A的伪造结果找到一个理想e,构造一个GAIP问题的解。敌手A与挑战者C之间的游戏如下：

1)Setup:输入安全参数，挑战者C进行如下操作：

挑战者C输入安全参数 $\mathsf { p { = } } 4 { \cdot } \mathsf { l _ { \mathrm { 1 } } } { \cdot } { \cdot } { \cdot } \mathsf { l _ { \mathrm { n } } } { - } 1$ ，其中 $\mathrm { \Delta l _ { i } }$ 是小的不同的奇素数，集合 $\varepsilon \lambda \lambda ( 0 , \ \pi )$ 和理想类群以及在 $\mathbb { F } _ { \mathfrak { p } }$ 上具有自同态环的超奇异椭圆曲线 $\boldsymbol { E } _ { \scriptscriptstyle \mathrm { ~ 0 ~ } }$ ， $H _ { 1 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { N }$ ， $H _ { 2 } : \{ 0 , 1 \} ^ { * }  \mathbb { Z } _ { N }$ 。将群公共参数 $\left\{ p , N , E _ { 0 } , H _ { 1 } , H _ { 2 } \right\}$ 发送给敌手 $\mathrm { \bf A }$ 。

2)Query：敌手A可以进行多项式次访问预言机并进行如下询问，挑战者C作出响应，挑战者C分别建立列表$L _ { 1 } , L _ { 2 } , L _ { 3 } , L _ { 4 }$ 来存储敌手A的 $H _ { \mathrm { 1 } }$ 询问、 $H _ { 2 }$ 询问、私钥询问及签名询问，所有列表初始化为空。设在进行私钥及签名询问之前，已进行过所有相关的Hash询问。

# 1）哈希询问

$H _ { 1 }$ 询问:A可以选择群成员身份 $I D _ { i }$ 进行询问,C检查列表 $L _ { ☉ }$ ，若 A 进过此询问，则返回相同结果。否则令 $h _ { i } = a _ { i } + H _ { 1 } \left( I D _ { i } \right) \mod N$ ，将 $h _ { i }$ 返回给 A，并将 $\left( I D _ { i } , h _ { i } , a _ { i } \right)$ 加入列表 $L _ { ☉ }$ 。

$H _ { 2 }$ 询问：接收到 A 查询输入 $\left( m , E _ { b i } \right)$ 时,C 检查列表 $L _ { 2 }$ ，若A进过此询问，则返回相同结果。否则C随机选择 $t _ { i } \gets _ { R } \mathbb { Z } _ { N }$ 返回给 $\mathrm { \bf A }$ ，并将 $\left( m , E _ { b i } , t _ { i } \right)$ 加入列表 $L _ { 2 }$ 。

# 2）私钥询问

A可以选择群成员身份 $I D _ { i }$ 进行私钥询问，C随机选取私钥 $x _ { i } \gets _ { R } \mathbb { Z } _ { N }$ ，并输出 $\left( U p k _ { i } , U s k _ { i } \right) = \left( E _ { i } , x _ { i } \right)$ ，将私钥返回给 A，并将 $\left( I D _ { i } , E _ { i } , x _ { i } \right)$ 加入列表 $L _ { _ { 3 } }$ 。

3）签名询问

A可以选择群成员身份 $I D _ { i }$ ，提交待签消息 $\mathrm { ~ m ~ }$ 的签名询问，C查询列表 $L _ { 2 }$ ， $L _ { _ { 3 } }$ 找到对应记录并用签名算法计算对消息 $\mathbf { m }$ 的签名结果 $\sigma _ { i }$ ，随机选取 $b _ { i }  _ { R } \mathbb { Z } _ { N }$ ，计算 $t _ { i } = H _ { 2 } ( E _ { i } \parallel E _ { 0 }$ $E _ { b i } \parallel m )$ ， $s _ { i } = t _ { i } + b _ { i } - x _ { i } \ \mathrm { m o d } \ N$ ，最终生成签名签名 $\sigma _ { i } = \left( E _ { \nu i } , t _ { i } ^ { \prime } , s _ { i } \right)$ 。

Forgery:敌手A 向挑战者C 提交一个消息 $m ^ { * }$ ，群成员身份为 $\boldsymbol { I D } _ { i } ^ { * }$ 以及伪造的群签名 $\sigma _ { i } ^ { * } = \left( E _ { v i } ^ { * } , t _ { i } ^ { \ast } , s _ { i } ^ { * } \right)$ 且满足以下两个条件：敌手A没有询问过用户 $\boldsymbol { I } \boldsymbol { D } _ { i } ^ { * }$ 的签名私钥；敌手A没有询问过 $\left( { E _ { \nu i } } ^ { * } , t _ { i } ^ { \prime * } , { S _ { i } } ^ { * } \right)$ 的签名。

如果签名 $\sigma _ { i } ^ { * } = \left( E _ { v i } ^ { * } , t _ { i } ^ { \ast } , s _ { i } ^ { * } \right)$ 是合法签名，下面将展示挑战者C 如何利用敌手A的伪造结果求得理想e，其为GAIP问题的一个解。挑战者C查询敌手A的询问列表 $L _ { 2 }$ ，若不存在集合 $( m ^ { * } , E _ { b i } { } ^ { * } , t _ { i } ^ { * } )$ ，挑战者C放弃并终止游戏。否则，因为$\sigma _ { i } ^ { * } = \left( E _ { v i } ^ { * } , t _ { i } ^ { \ast } , s _ { i } ^ { * } \right)$ 是合法签名，由签名的验证过程，本文有

$$
\begin{array} { l } { \left\{ { E _ { \nu i } = \left[ t _ { i } ^ { \prime } \right] E _ { G M } } \right. } \\ { \left. { E _ { \nu i } } ^ { * } = \left[ t _ { i } ^ { \prime * } \right] E _ { G M } \right. } \end{array}
$$

若 $t _ { i } - t _ { i } ^ { * } = 0$ ，则挑战者放弃游戏，否则可以计算出$E _ { v i } = \left[ t _ { i } - t _ { i } ^ { * } \mathrm { m o d } N \right] E _ { v i } { } ^ { * }$ 。令 $e = t _ { i } - t _ { i } ^ { * } { \bmod { N } }$ ，则有 $\boldsymbol { E _ { v i } } = \boldsymbol { \left[ e \right] } \boldsymbol { E _ { v i } } ^ { * } = { \mathsf { e } } \boldsymbol { E _ { v i } } ^ { * }$ 。即理想e是GAIP问题的一个解。

综上所述，如果GAIP问题是困难的，本方案在随机预言模型下是不可伪造的。

定理7抗合谋性。对于任意多项式时间敌手A，本方案在随机预言模型下是抗合谋的。

证明：抗合谋攻击是指即使部分成员联合起来也无法产生GM追踪不到的合法群签名。在本方案的群成员加入算法中，管理员GM将成员身份信息存储在群成员列表中，签名时先通过搜索列表中的存储信息验证成员的身份合法性，验证成功才提供签名帮助，与群成员合作产生签名，避免了群中成员合谋产生无法追踪的签名。此外基于GAIP问题的困难性，使群管理员GM无法获知群成员的私钥，且群成员之间无法得出其他成员的私钥。最后，群中所有成员以及管理员GM的私钥都完全保密，且互相无关。所以，该方案具有抗合谋性。

定理8可追踪性。对于任意多项式时间敌手A，本方案在随机预言模型下是可追踪的。

证明：方案的可追踪性是指管理员可以通过打开签名来找到签名者的真实身份。本方案的签名由管理员和群成员共同完成，在执行签名算法时，用户会先声称自己的部分签名，然后将其发送给GM，GM收到签名后，查询用户 $U _ { i }$ 是否在群成员列表中，并通过判断 $\big [ t _ { i } ^ { \prime } \big ] E _ { b i } = \big [ s _ { i } \big ] E _ { i }$ 是否成立来验证用户签名的合法性。在通过验证之后，管理员才会计算签名。同时将其存储到追踪列表里。因此可以看出，管理员GM只需通过搜索追踪列表来打开签名，即可查出签名者身份。

此外，攻击者无法在没有群管理员的情况下独自生成合法签名。假设敌手A具有增加和撤销群成员的权力以及获得群私钥和群中任意成员的私钥的能力。此外，A还可以运行签名预言机和打开预言机。

若在 $I D _ { i }$ 下对于消息M，A伪造群成员i的签名 $\sigma _ { i }$ ，但只要群管理GM是安全的，GM的私钥不被获取，那么A就无法伪造出不能被GM追踪到的签名。因为群签名是由群成员和群管理员共同合作完成的。 $U _ { i }$ 只有在GM协助下才可以产生有效的群签名，而GM在协助 $U _ { i }$ 时，将 $U _ { i }$ 的相关身份信息记录在追踪列表LTrack中，此外因为GAIP问题是困难的，是计算不可行的，那么即使群成员被攻破，只要GM的私钥未被泄露，签名仍然不可伪造，所以本方案满足可跟踪性。

# 3.4性能分析

将本文群签名方案与文献[19]的方案进行比较。[19]中的方案采用双线性映射，实现群管理员对群成员的身份认证，而本文采用的方案为本文第三节中提出的基于同源的零知识身份认证。且同样具有以下优点：1）工作效率高:本文提出的签名方案中群签名长度是固定不变的，不随群中成员个数的变化而变化，且签名长度短。公钥和签名长度均与群成员的数量n无关，所以整体群签名效率较高。本文方案适合大群组的群签名方案。2）动态性：本文方案设置了公钥状态列表，可以实现动态地增加和撤销群成员，其加入、撤销代价较小，群成员可以随机的加入和撤销。群成员的撤销简单快捷，只要修改群成员对应的终止时间便能实现群成员的即时撤销。不同之处在于：1）本文群签名方案基于同源的GAIP问题，由公钥求出私钥是困难的，规避了被撤销成员联合得出其他成员私钥的风险。2）本文群签名中群成员的私钥由自己随机选择生成，因此可以抵挡群管理员的陷害攻击。3）本文群签名方案包含了超奇异同源的特殊性质，如密钥短、抗量子攻击等，但计算时间长。

# 4 结束语

本文在Bullens 等人提出的CSI-Fish的基础上，提出了一个新的零知识证明方案。与CSI-Fish中的方案相比,该方案在仅有一个公钥的前提下,将挑战空间提升为类群阶数N,实现了更强的稳固性。同时本文通过应用Fiat-Shamir变换，在量子随机预言模型下得到了基于超奇异同源的签名方案以及群签名方案，并对提出的签名方案进行了安全性证明。

# 参考文献：

[1]Silverman JH. The arithmetic of elliptic curves [M]. Springer Science & Business Media,2009.   
[2]Rostovtsev A, StolbunovA.Public-key cryptosystem based on isogenies [J].Cryptology ePrint Archive,2006/145.   
[3]Childs A,Jao D, Soukharev V.Constructing eliptic curve isogenies in quantum subexponential time [J]. Journal of Mathematical Cryptology, 2014,8(1): 1-29.   
[4]Biasse JF,Jao D,Sankar A.A quantum algorithm for computing isogenies between supersingular elliptic curves [C]// International Conference on Cryptology in India. Springer, Cham,2014: 428-442.   
[5]Jao D,De Feo L.Towards quantum-resistant cryptosystems from supersingular elliptic curve isogenies [C]// International Workshop on Post-Quantum Cryptography. Springer,Berlin,Heidelberg,2011:19-34.   
[6]Castryck W,Lange T,Martindale C,et al. CSIDH: an eficient postquantum commutative group action [C]//International Conference on the Theory and Application of Cryptology and Information Security. Springer, Cham,2018: 395-427.   
[7]Fiat A,Shamir A.How to prove yourself: Practicalsolutions to identification and signature problems [C]// Conference on the theory and application of cryptographic techniques. Springer, Berlin, Heidelberg, 1986: 186-194.   
[8] Abdalla M,An JH,Bellare M,et al. From identification to signatures via the Fiat-Shamir transform: Minimizing assumptions for security and forward-security [C]//International Conference on the Theory andApplicationsof Cryptographic Techniques.Springer, Berlin, Heidelberg,2002: 418-433.   
[9]Yoo Y,Azarderakhsh R, Jalali A,et al.A post-quantum digital signature scheme based on supersingular isogenies [C]/ International Conference on FinancialCryptography and Data Security. Springer, Cham, 2017: 163-181.   
[10] Galbraith S D,Petit C,Silva J. Identification protocols and signature schemes based on supersingular isogeny problems [C]// International conference on the theoryand application of cryptologyand informationsecurity. Springer, Cham,2017: 3-33.   
[11] De Feo L,Galbraith S D. SeaSign: Compact isogeny signatures from class group actions [C]//Annual International Conference on the Theory and Applications of Cryptographic Techniques. Springer, Cham, 2019: 759-789.   
[12] Beullens W,Kleinjung T, VercauterenF.CSI-FiSh:Eficientisogeny based signatures through class group computations [C]// International Conference on the Theory and Application of Cryptology and Information Security. Springer, Cham,2019: 227-247.   
[13] Galbraith S D.Mathematics ofpublic key cryptography[M].Cambridge University Press,2012.   
[14] DeFeo L.Mathematics of isogeny based cryptography[J].arXiv preprint arXiv: 1711.04062,2017,12.   
[15] Cozzo D, Smart N P. Sashimi: Cuting up CSI-FiShsecret keys to produce anactively secure distributedsigning protocol [C]// International Conference on Post-Quantum Cryptography. Springer, Cham,2020: 169- 186.   
[16]Benhamouda F,Camenisch J,Krenn S,et al.Betterzero-knowledge proofs for lattice encryption and their application to group signatures [C]// International Conference on the Theory and Application of Cryptology and Information Security.Springer,Berlin,Heidelberg,2014: 551-572.   
[17] Bellare M,Poettering B,Stebila D.From identification to signatures, tightly:a framework and generic transforms [C]// International Conference on the Theory and Application of Cryptologyand Information Security. Springer,Berlin,Heidelberg,2016: 435-464.   
[18] EI Kaafarani A,Katsumata S,Pintore F.Lossy CSI-FiSh:Efficient signature scheme with tight reduction to decisional CSIDH-512 [C]// IACR International Conference on Public-Key Cryptography. Springer, Cham,2020:157-186.   
[19] Yu Xuan,Hou Shuhui.Efficient and Secure Group Signature Scheme [J]. Communications Technology,2018,51(2):413-418．于璇，侯书会．- 种高效安全的群签名方案[Jl.通信技术.2018.51(2):413-418.