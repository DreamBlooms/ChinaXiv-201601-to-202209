# 可证安全的无对运算的无证书签密方案

陈虹，赵悦，肖成龙，肖振久，宋好(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：无证书签密体制继承了基于身份签密体制无须使用公钥证书的特点，又对其密钥托管问题进行了改进，具有一定优越性。针对已有的无证书签密方案计算效率低、安全性差等缺点，基于一种安全的签名方案，提出一类新的无对运算的无证书签密方案。采用将哈希函数与用户身份绑定以及公钥与私钥相结合生成新密钥的方法进行构造。在随机预言模型下基于计算椭圆曲线上的离散对数困难问题证明了方案的机密性和不可伪造性。并与已往方案进行对比，在保证安全性的同时，该方案不使用双线性对和指数运算，效率较高。

关键词：无证书签密；机密性；不可伪造性；随机预言模型 中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2017.10.0938

# Certificateless signcryption scheme of verifiable security without pairing

Chen Hong, Zhao Yue,Xiao Chenlong, Xiao Zhenjiu, Song Hao (CollegeofSoftwareLiaoning Technical University,Huludao Liaoningl25105,China)

Abstract:Thecertificateless signcryptionscheme effectivelysolved the keyescrow problem inidentity based signcryption scheme while kept itscertificate-free property.Aiming atthe low computation eficiencyand poor securityof the existing certificateless signcryptionscheme,this paper proposed anewcertificatelessigncryption scheme without pairings basedona sortofsecuresignature scheme.The scheme usedbinding thehash functions with identities ofusers andthe method ofcombing the public and private keyto generateanew key.Thescheme wasconfidentialand unforgeable basedonthe hard problemof discretelogarithmontheelipticcurveunderthe random oracle model．Compared with existing schemes，the proposed method improves the eficiency without using bilinear pairing and exponential operation under the secure situation.

Key Words:certificateless signcryption; confidentiality; unforgeability; random oracle model

# 0 引言

机密性和认证性是密码学中衡量信息是否安全的两个重要指标。为了达到这一标准，传统算法是先将信息进行数字签名，然后加密。但这种方法的计算量是两者之和，效率较低。为解决这个问题，Zheng[1在1997年首次提出签密这一概念。它能在一个逻辑步骤内同时实现签名和加密两项功能，并且与传统算法相比，计算量和通信成本都要更低。此后，签密技术作为热点被广泛研究。

随着签密技术不断发展，基于公钥基础设施（public keyinfrastructure，PKI）的签密方案被提出，基于PKI的签密方案中公钥证书解决了签密方案易受“公钥替换”攻击的问题，通过检验证书的合法性来辨别公钥的正确性。但公钥证书的颁发、验证、管理繁杂和计算量大等问题抑制了该方案的发展。此后，基于身份的签密方案被提出，它取消了公钥证书，避免了证书管理困难等问题。但由于它的私钥完全由私钥生成中心（privatekeygenerator，PKG）提供，则出现了密钥托管问题，即PKG可以获得任意用户私钥，伪造成任意用户对信息进行解密和验证签名而不被发现，就避免不了会引起安全问题。后来有人又将无证书密码体制与签密体制相结合，形成了无证书签密（certificateless signcryption，CL-SC）体制，它同时解决了基于PKI签密方案中的公钥证书问题和基于身份的签密方案中的密钥托管问题。2008年，首个CL-SC方案[2]被提出，后来被验证其不能抵抗扩展不可伪造攻击。随后许多CL-SC方案被提出，其中一部分采用了双线性对运算，双线性对运算复杂性高，计算量大。因此，Selvi 等人[3]提出了一个无对运算的CL-SC 方案，并证明了该方案的安全性。然而在该方案中多次运用指数运算，计算效率依然不高。后来朱辉等人[4]和刘文浩等人[5]也分别提出了无对运算的CL-SC方案，但都已被证明是不安全的。

本文在汤永利等人[构造的高效、安全的签名方案上，利用发送者的私钥与接收者的公钥相结合作为加密密钥，发送者的公钥与接收者的私钥相结合作为解密密钥的方法，构造出一种无对运算的CL-SC方案，并在随机预言模型下证明该方案的安全性，与近年的几种签密方案进行对照，其性能更优。

# 1 预备知识

# 1.1数学困难问题

定义在 $F _ { p }$ （ $F _ { p }$ 表示有 $p$ 个元素的有限域， $p$ 为素数且 $p > 3$ ）上的椭圆曲线方程为

$$
y ^ { 2 } = x ^ { 3 } + a x + b \qquad a , b \in F _ { p }
$$

判别式为

$$
4 a ^ { 3 } + 2 7 b ^ { 2 } \neq 0 { \bmod { p } }
$$

椭圆曲线上的所有解与一个无穷远点 $o$ 构成的一个集合用$E ( F _ { p } )$ 来表示，即： $E ( F _ { p } ) = \{ ( x , y ) | x , y \in F _ { p } \}$ ，且满足方程式$\{ y ^ { 2 } = x ^ { 3 } + a x + b \} \cup \{ O \}$ ， $E ( F _ { p } )$ 上点的数目用 $n$ 表示，成为椭圆曲线的阶。

椭圆曲线上的离散对数问题：

已知椭圆曲线 $E ( F _ { p } )$ ，阶为 $n$ 的点 $P \in E ( F _ { p } )$ ， $Q \in < P >$ ，若整数 $x \in [ 0 , n - 1 ]$ ，使得 $Q = [ x ] P$ 。

# 1.2 CL-SC方案定义

一个CL-SC 方案由密钥生成中心（key generation center,KGC)，发送者 $I D _ { i }$ ，接收者 $I D _ { j }$ 三个合法参与者参与。

一个CL-SC方案通常由下列几种算法组成：

a)系统参数建立。由KGC运行初始化系统。该算法将安全参数 $k$ 作为输入，KGC 选择主密钥 $s$ ，输出系统参数params。并且由KGC保密 $s$ ，公开params。

b)用户部分密钥生成。该算法由KGC完成。将某个用户的身份 $I D _ { i }$ 、 $s$ 、params 作为输入，KGC 生成该用户的部分私钥$D _ { i }$ 和部分公钥 $R _ { i }$ ，并返回给用户。

c)用户秘密值生成。该算法由用户独立运行，将 $I D _ { i }$ 、params作为输入，输出一个秘密值 $\boldsymbol { x } _ { i } \in \boldsymbol { Z } _ { q } ^ { * }$ 作为长期私钥，并且该值对于KGC是保密的。

d)用户私钥生成。该算法由每个用户运行一次。它将 $I D _ { i }$ 、$D _ { i }$ 、 $x _ { i }$ 作为输入，并为该用户生成完整的私钥 $S K _ { i } = ( x _ { i } , D _ { i } )$ 。

e)法用户公钥生成。该算法由用户运行。它将 $I D _ { i }$ 、params、$R _ { i }$ 以及 $x _ { i }$ 作为输入，输出用户公钥 $P K _ { i } = ( X _ { i } , R _ { i } )$ 。得到的公钥是公开的。

f)签密(signcrypt)。输入params、明文消息 $m$ 、签密者身份$I D _ { i }$ 及其私钥 ${ \cal { S } } K _ { i }$ 、接收者身份 $I D _ { j }$ 及其公钥 $P K _ { j }$ ,输出密文 $\sigma$ 并发送给接收方。

g)解签密(unsigncrypt)。输入params、 $\sigma$ 、 $I D _ { i }$ 、 $P K _ { i }$ 、 $I D _ { j }$ 以及 $S K _ { j }$ ，对解签密获得的消息 $m$ 进行验证，如果通过，则用户输出明文消息 $m$ ，否则拒收消息 $m$ 。

CL-SC方案组成及通信模型也可由图1表示。

![](images/234376b44475492a7a8bf38db449fcf56b4c4a041be7bbfefe29edeefb6af41d.jpg)  
图1CL-SC方案组成及通信模型

发送者 $\mathbf { \nabla } _ { I D _ { i } }$ 利用自己的私钥以及发送者的公钥对明文消息$m$ 进行签密生成密文 $\sigma$ ，并将密文通过公开信道发送给接收者$I D _ { j }$ 。接收者利用自己的私钥以及发送者的公钥对密文 $\sigma$ 进行解签密,若所获得的明文能通过验证，则接收。发送者和接收者的私钥都需要一部分由KGC提供，一部分为自己生成的秘密值。

# 2 新的无对运算的CL-SC方案

# 2.1方案描述

本文构造的无对运算的CL-SC方案的具体过程如下：

a)系统参数建立。输入参数 $k$ ,选择一个 $\mathbf { \xi } _ { l }$ 位的大质数 $p$ ，设$G$ 为椭圆曲线 $E ( F _ { p } )$ 的一个循环群， $p$ 为 $G$ 的一个生成元。选择3个安全的哈希函数 $H _ { 1 } : \{ 0 , 1 \} ^ { * }  Z _ { q } ^ { * }$ ， $H _ { 2 } : \{ 0 , 1 \} ^ { * }  Z _ { q } ^ { * }$ ，$H _ { 3 } : Z _ { q } ^ { * } \times Z _ { q } ^ { * } \to Z _ { q } ^ { * }$ 。KGC 选择主密钥 $s$ ,并计算主公钥： $P _ { p u b } = s P$ 。KGC保密主密钥 $s$ ，公开系统参数$p a r a m s = \{ p , q , G , P , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } \}$ 。

b)用户部分密钥生成。给定用户身份 $I D _ { i }$ ，KGC 随机选择$r _ { i } \in Z _ { q } ^ { * }$ ，计算 $R _ { i } = r _ { i } P$ ， $D _ { i } = r _ { i } + s H _ { 1 } ( I D _ { i } , R _ { i } )$ ,则生成用户的部分私钥 $D _ { i }$ 和部分公钥 $R _ { i }$ ,并将其返回给用户。

c)秘密值生成。随机选择 $\boldsymbol { x } _ { i } \in \boldsymbol { Z } _ { q } ^ { * }$ 作为用户的长期私钥。

d)用户私钥生成。生成对应的私钥 $( x _ { i } , D _ { i } )$ 。因此，用户A的私钥为 $S K _ { \scriptscriptstyle A } = ( x _ { \scriptscriptstyle A } , D _ { \scriptscriptstyle A } )$ ，用户B的私钥为 $S K _ { \scriptscriptstyle B } = ( x _ { \scriptscriptstyle B } , D _ { \scriptscriptstyle B } )$ 。

e)用户公钥生成。计算 $X _ { _ i } = x _ { _ i } P$ ,生成公钥 $( X _ { i } , R _ { i } )$ 。所以用户A的公钥为 $P K _ { _ A } { = } ( X _ { _ A } , R _ { _ A } )$ 。用户B的公钥为 $P K _ { _ B } { = } ( X _ { _ B } , R _ { _ B } )$ 。然后计算等式 $R _ { i } + H _ { 1 } ( I D _ { i } , R _ { i } ) P _ { p u b } = D _ { i } P$ 是否成立。若成立，则KGC分配的部分私钥符合规则。

f)签密。当发送者A对明文 $m$ 进行签密发送给接收者B时，执行以下步骤：

(a)用户A随机选取 $t \in Z _ { q } ^ { * }$ ,计算 $T = t P$ 。

(b)计算 $h _ { 1 } = H _ { 1 } ( I D _ { { B } } , R _ { { B } } ) , h _ { 2 } = H _ { 2 } ( m , T , R _ { { A } } , X _ { { A } } ) , u = t + x _ { A } h _ { 1 } + D _ { A } h _ { 2 }$

(c)计算 $K _ { 1 } = x _ { A } X _ { B }$ ， $K _ { _ 2 } = ( R _ { _ B } + P _ { _ { p u b } } h _ { _ 1 } ) D _ { _ A }$ ， $V _ { \cal A } = H _ { 3 } ( K _ { 1 } , K _ { 2 } )$ ，加密明文 $c = V _ { \scriptscriptstyle A } \oplus m$ □

(d)用户A向用户B发送签密密文 $\sigma = ( c , h _ { 2 } , u )$ 。

g)解签密。用户B收到 $\sigma = ( c , h _ { 2 } , u )$ 后，执行以下步骤：

(a)计算 $\dot { h _ { 1 } ^ { \prime } } = H _ { 1 } ( I D _ { A } , R _ { A } )$ 和 $T ^ { ' } = u P - X _ { \scriptscriptstyle A } h _ { \scriptscriptstyle 1 } - R _ { \scriptscriptstyle A } h _ { \scriptscriptstyle 2 } - P _ { \scriptscriptstyle p u b } \dot { h _ { \scriptscriptstyle 1 } } h _ { \scriptscriptstyle 2 }$ 。

(b)计算 $V _ { _ B } = H _ { 3 } ( X _ { _ A } x _ { _ B } , ( R _ { _ A } + P _ { _ { p u b } } \dot { h _ { 1 } } ) D _ { _ B } )$ ,恢复明文 $m = V _ { \scriptscriptstyle B } \oplus c$ 。

(c)计算 $\dot { h _ { 2 } } = ( m , T ^ { ' } , R _ { A } , X _ { A } )$ ,若 $\dot { h _ { 2 } ^ { ' } } = h _ { 2 }$ ，则输出 $m$ ，若不成立则拒接。

# 2.2 正确性证明

新方案的正确性分析如下：

因为

$$
\begin{array} { r l } & { V _ { A } = H _ { 3 } ( x _ { A } X _ { B } , ( R _ { B } + P _ { p u b } h _ { 1 } ) D _ { A } ) } \\ & { \qquad = H _ { 3 } ( x _ { A } x _ { B } P , ( r _ { B } + s h _ { 1 } ) P D _ { A } ) } \\ & { \qquad = H _ { 3 } ( x _ { A } x _ { B } P , D _ { A } D _ { B } P ) } \end{array}
$$

$$
\begin{array} { r l } & { V _ { B } = H _ { 3 } ( X _ { A } x _ { B } , ( R _ { A } + P _ { p u b } h _ { 1 } ) D _ { B } ) } \\ & { \qquad = H _ { 3 } ( x _ { A } x _ { B } P , ( r _ { A } + s \dot { h _ { 1 } } ) P D _ { B } ) } \\ & { \qquad = H _ { 3 } ( x _ { A } x _ { B } P , D _ { A } D _ { B } P ) } \end{array}
$$

可知， $V _ { _ A } = V _ { _ B }$ 。由于用户A通过计算 $c = V _ { \scriptscriptstyle A } \oplus m$ 对明文进行加密，用户B通过计算 $\boldsymbol { m } = V _ { \boldsymbol { B } } \oplus { \boldsymbol { c } }$ 对密文进行解密，由于 $V _ { _ A } = V _ { _ B }$ ，所以可以确保用户最后能得到正确的明文。

因为

$$
\begin{array} { r l } & { T ^ { ' } = u P - X _ { A } h _ { 1 } - R _ { A } h _ { 2 } - P _ { p u b } h _ { 1 } h _ { 2 } } \\ & { = ( t + x _ { A } h _ { 1 } + D _ { A } h _ { 2 } ) P - X _ { A } h _ { 1 } - R _ { A } h _ { 2 } - P _ { p u b } h _ { 1 } h _ { 2 } } \\ & { = [ T + x _ { A } h _ { 1 } P + r _ { A } h _ { 2 } P + s H _ { 1 } ( I D _ { A } , R _ { A } ) h _ { 2 } P ] } \\ & { - X _ { A } h _ { 1 } - R _ { A } h _ { 2 } - P _ { p u b } h _ { 1 } h _ { 2 } } \\ & { = T } \end{array}
$$

所以 $\dot { h _ { 2 } } = H _ { 2 } ( m , T ^ { ' } , R _ { { \scriptscriptstyle A } } , X _ { { \scriptscriptstyle A } } ) = h _ { 2 }$ ，说明可以确保解密获得的消息$m$ 能够通过验证。

# 3 安全性分析

# 3.1 安全性定义

判定一个签密方案安全性的基本条件是至少满足机密性即选择密文攻击下加密不可区分性（IND-CCA2)和不可伪造性即选择消息攻击下不可伪造性（EUF-CMA)。根据文献[7]论述，CL-SC 方案通常面对两类攻击者A、 $A _ { 2 }$ 和四类模拟游戏（gameI、gameII、gameIII、gameIV)。对于第一类攻击者A而言，不能拥有 KGC产生的主密钥，但具有替换任意用户公钥的能力。对于第二类攻击者 $A _ { 2 }$ 而言，它能够获取KGC生成的主密钥，则具有构造任意合法用户的部分私钥的能力，但无法替换用户公钥。

文献[8]具体介绍了四类模拟游戏的定义，本文主要以第一类攻击者A为例，给出在适应性选择密文攻击和选择消息攻击下的示意图，如图2、3所示。

![](images/c05d45c23aacebbf25571856f6c85d64972f10e24d7d5b135e4e87df81f4bef5.jpg)  
图2攻击者为 $A _ { 1 }$ 的适应性选择密文攻击模拟示意图

其中 $c$ 为该游戏中的挑战者，首先 $c$ 运行系统参数建立算法，将生成的params发送给攻击者 $A _ { 1 }$ ，并保密主密钥 $s$ 。询问分为两个阶段，第一阶段包括Hash函数查询、部分密钥查询、私钥查询、公钥查询、公钥替换查询、签密查询、解签密查询， $c$ 按照要求返回查询值。 $A _ { 1 }$ 选择两个想挑战的用户 $( I D _ { \scriptscriptstyle I } , I D _ { \scriptscriptstyle J } )$ 和两个等长明文 $( m _ { 0 } , m _ { 1 } )$ 发送给 $c$ ,其中未对 $I D _ { J }$ 进行过部分密钥和私钥查询。 $c$ 任选其中一明文 $m _ { b }$ $( b \in \{ 0 , 1 \} )$ 进行签密，然后返回密文 $\sigma ^ { * }$ 给 $A _ { \mathrm { i } }$ 。 $A _ { 1 }$ 进行第二阶段询问，但不可以执行 $\sigma ^ { * }$ 的解签密查询，也不可以执行 $I D _ { \jmath }$ 的部分密钥查询和私钥查询，最后A返回 $\boldsymbol { b } ^ { \prime }$ 给 $c$ 。若 $\boldsymbol { b ^ { \prime } } = \boldsymbol { b }$ ，则 $A _ { 1 }$ 在游戏中获胜。

对于攻击者为 $A _ { 2 }$ 的适应性选择密文攻击而言， $c$ 运行系统参数建立算法，将生成的params 和 $s$ 都发送给 $A _ { 2 }$ 。要求在询问阶段不允许进行公钥替换查询，并且在第二阶段的询问中，也不允许对挑战用户进行部分私钥提取查询和对挑战消息进行签密或解签密查询，其他与在A下攻击过程类似。

![](images/ded2e8de646bbb9ed80ad79f2a08daa3998a2340b26f2d649624be695420d4e8.jpg)  
图3攻击者为A的选择消息攻击模拟示意图

挑战者 $c$ 运行系统参数建立算法，将生成的params 发送给$A _ { 1 }$ ，并保密 $s$ 。 $A _ { \mathrm { i } }$ 向 $c$ 发起询问，询问阶段与适应性选择密文攻击游戏中第一阶段询问相同。伪造阶段， $A _ { 1 }$ 向 $c$ 发送元组$( I D _ { I } , I D _ { J } , \sigma ^ { * } )$ ， $I D _ { \iota }$ 为发送者， $I D _ { J }$ 为接收者， $\sigma ^ { * }$ 为 $A _ { 1 }$ 从 $I D _ { \imath }$ 到 $I D _ { J }$ 对明文 $m$ 的签密值，其中在询问阶段未执行过该元组的签密查询，并且也未执行过 $I D _ { J }$ 的部分私钥查询。经过验证，若 $\sigma ^ { * }$ 是对 $( I D _ { I } , I D _ { J } , m )$ 的有效签密，则 $A _ { 1 }$ 赢得游戏。

对于攻击者为 $A _ { 2 }$ 的选择消息攻击而言， $c$ 运行系统参数建立算法，将生成的params 和 $s$ 发送给 $A _ { 2 }$ 。在询问阶段，不进行公钥替换查询，并且在伪造阶段，要求挑战用户未进行过签密查询也未进行过部分私钥提取查询，其他与在A下的选择消息攻击过程类似。

# 3.2机密性分析

若攻击者想从密文 $\sigma = ( c , h _ { 2 } , u )$ 中获得明文，就一定要计算出加密密钥 $V _ { _ A }$ 。若想获得 $V _ { _ A }$ 则须知道用户A的私钥，即使在第二类攻击者 $A _ { 2 }$ 攻击下，恶意的KGC仅有部分私钥 $D _ { _ A }$ ，若想从$X _ { _ A }$ 中求出另一部分私钥 $x _ { _ A }$ ，则面临解离散对数问题，从而无法获得加密密钥，无法恢复密文。另一方面，由于 $V _ { _ A } = V _ { _ B }$ ，进而若能计算出 $V _ { _ B }$ 同样可以破解密文。同理若想求出 $\boldsymbol { V } _ { B }$ 则必须计算出B的完整私钥，同样面临解离散对数问题。

该方案的机密性详细证明如下：

引理1攻击者 $A _ { 1 }$ 下的机密性。在随机预言模型且ECDLP难解的情况下，在概率多项式时间内存在敌手 $A _ { 1 }$ 以 $\varepsilon$ 的优势赢得游戏IND-CCA2，则存在一个区分者 $c$ 以（202 $S u c c _ { A _ { 1 } } ^ { E C D L P } \ge \sqrt [ \xi ] { q _ { 1 } } \left( 1 - \big / _ { q _ { 1 } } \right) ^ { q _ { p p } } \left( 1 - \big / _ { q _ { 3 } ^ { 2 } } \right)$ 的概率解决ECDLP 困难问题。

证明若想攻破本文的CL-SC 方案，就必须存在算法 $c$ 利用 $A _ { 1 }$ （第一类攻击者）攻击解决ECDLP问题，即已知 $( p , a p )$ ，可 $\boldsymbol { a }$ 求的值。

1)初始化 $c$ 运行系统参数建立算法，并保存 $s$ ，发送params给 $A _ { 1 }$ 。

2)询问阶段

a) $H _ { \mathrm { 1 } }$ 询问： $c$ 维护列表 $L _ { { \scriptscriptstyle H _ { 1 } } }$ ，初始为空，格式为 $( I D , R _ { _ { I D } } , D _ { _ { I D } } , h _ { _ { 1 } } )$ ，当 $c$ 接收到 $A _ { 1 }$ 对 $H _ { \mathrm { 1 } } ( I D , R _ { \mathit { I D } } )$ 的询问，若该列表中存在则返回 $h _ { 1 }$ 给$A _ { 1 }$ ，若不存在则随机选择 $h _ { 1 } \in Z _ { q } ^ { * }$ 返回，并加入到列表 $L _ { { \scriptscriptstyle H _ { 1 } } }$ 中。

b) $H _ { 2 }$ 询问： $c$ 维护列表 $L _ { { \scriptscriptstyle H _ { 2 } } }$ ，初始为空，格式为$( m , T , R _ { \scriptscriptstyle I D } , X _ { \scriptscriptstyle I D } , h _ { \scriptscriptstyle 2 } )$ ，当 $c$ 接收到 $A _ { \mathrm { i } }$ 对 $H _ { 2 }$ 的询问时，若该列表中存在则返回 $h _ { 2 }$ ，若不存在则随机选择 $h _ { _ 2 } \in Z _ { _ q } ^ { ^ { * } }$ 返回给A，并加入到列表 $L _ { { \scriptscriptstyle H _ { 2 } } }$ 中。

c) $\boldsymbol { H } _ { 3 }$ 询问： $c$ 维护列表 $L _ { { \scriptscriptstyle H _ { 3 } } }$ ，初始为空，格式为 $( K _ { 1 } , K _ { 2 } , h _ { 3 } )$ ，当 $c$ 接收到 $A _ { 1 }$ 对 $\boldsymbol { H } _ { 3 }$ 的询问时，若列表中存在则返回 $h _ { 3 }$ ，若不存在则随机选择 $h _ { 3 } \in Z _ { \boldsymbol { q } } ^ { * }$ 返回给 $A _ { 1 }$ ，并加入到列表 $L _ { { \scriptscriptstyle H _ { 3 } } }$ 中。

d)部分私钥询问：当 $c$ 接收 $A _ { 1 }$ 对用户 $I D$ 的部分私钥询问时，若 $\boldsymbol { I D } = \boldsymbol { I D } ^ { * }$ ，则 $c$ 终止；若不等，则查询列表 $L _ { H _ { 1 } }$ 中是否有对应项，若有返回 $D _ { _ { I D } }$ 给 $A _ { 1 }$ ，若没有则先进行 $H _ { 1 }$ 询问，再返回。

e)公钥询问： $c$ 维护列表 $L _ { P K }$ ，初始为空，格式为 $( I D , x _ { I D } , X _ { I D } )$ u当 $c$ 接收到 $A _ { 1 }$ 对某一 $I D$ 的公钥询问时，先进行 $L _ { { \scriptscriptstyle H _ { 1 } } }$ 查询，若存在对应项则返回 $R _ { \mathit { I D } }$ 给 $A _ { 1 }$ ；若不存在则先进行 $H _ { \mathrm { 1 } }$ 询问，再返回。$c$ 再查询 $L _ { P K }$ ，列表中若存在对应项，则返回 $X _ { \mathit { m } }$ 给 $A _ { 1 }$ ，若不存在，则选任意随机数 $\boldsymbol { x } _ { I D } \in \boldsymbol { Z } _ { q } ^ { * }$ ，计算 $X _ { _ { I D } } = x _ { _ { I D } } P$ ，再返回 $X _ { _ { I D } }$ 给 $A _ { 1 }$ 。并把该项加入到列表 $L _ { P K }$ 中。

f)公钥替换询问： $c$ 接收到 $A _ { 1 }$ 关于 $( I D , X _ { I D } ^ { ' } )$ 的公钥替换询问时， $c$ 查找 $L _ { P K }$ 列表，若存在对应项，则用 $X _ { I D } ^ { ' }$ 替换 $X _ { _ { I D } }$ 并令$x _ { \ I D } = \perp$ 。

g)私有秘密值询问：当 $c$ 接收到 $A _ { \mathrm { i } }$ 对某一 $I D$ 的私有秘密值 询问时， $c$ 查询 $L _ { P K }$ ，若存在相应项且 $x _ { _ { I D } }$ 有值，则返回该 $x _ { _ { I D } }$ 给 $A _ { 1 }$ ，若 $x _ { I D } = \perp$ ，则表示公钥已被替换，则 $c$ 返回 $\perp$ 。

h)签密询问： $A _ { \mathrm { i } }$ 选择 $( m , I D _ { a } , I D _ { b } )$ 进行签密询问，其中 $I D _ { a }$ 为发送者， $I D _ { b }$ 为接收者。 $c$ 接收到该询问后进行如下处理：若$I D _ { a } \neq I D ^ { * }$ 且 $I D _ { a }$ 公钥未被替换，则 $c$ 通过相关询问并按照签密算法算出密文并返回给 $A _ { 1 }$ ；若 $I D _ { a } = I D ^ { * }$ 或 $I D _ { a }$ 的公钥被替换过，则$I D _ { b } \neq I D ^ { * }$ ， $c$ 查询的 $I D _ { b }$ 部分私钥 $\boldsymbol { D } _ { b }$ 和秘密值 $x _ { b }$ ，然后通过公钥查询查出 $I D _ { a }$ 的公钥，再请求 $\boldsymbol { H } _ { 3 }$ 询问，最后 $c$ 按照签密算法算出密文并返回给 $A _ { 1 }$ 。

i)解签密询问： $A _ { \mathrm { i } }$ 作出解签密询问 $( I D _ { a } , I D _ { b } , \sigma )$ 其中 $I D _ { a }$ 是发送者身份， $I D _ { b }$ 是接收者身份：若 $I D _ { b } \neq I D ^ { * }$ ，则 $c$ 查询表 $L _ { { \scriptscriptstyle H _ { 1 } } }$ 的$( I D _ { a } , R _ { a } , D _ { a } , h _ { 1 } )$ 、 $( I D _ { b } , R _ { b } , D _ { b } , h _ { 1 } )$ ，表 $L _ { { \scriptscriptstyle H _ { 2 } } }$ 的 $( m , T , R _ { a } , X _ { a } , h _ { 2 } )$ 和 $L _ { P K }$ 的$( I D _ { a } , x _ { a } , X _ { a } )$ 、 $( I D _ { b } , x _ { b } , X _ { b } )$ ，计算 $T ^ { ' } = u P - X _ { a } h _ { 1 } - R _ { a } h _ { 2 } - P _ { p u b } h _ { 1 } h _ { 2 }$ ，计算 $V _ { b }$ ，解密消息 $\boldsymbol { m } = V _ { b } \oplus \boldsymbol { c }$ ，查表 $L _ { { \scriptscriptstyle H _ { 2 } } }$ 中是否存在，若成立则返回 $\mid m \mid$ 否则终止，若 $I D _ { b } = I D ^ { * }$ 则终模拟。

当上述模拟结束， $A _ { 1 }$ 挑选挑战的两个用户身份 $( I D _ { I } , I D _ { J } )$ 和等长的明文 $( m _ { 0 } , m _ { 1 } )$ 发送给 $c$ ，若 $I D _ { J } \neq I D ^ { * }$ 则终止，否则 $c$ 任意选择 $b \in \{ 0 , 1 \}$ ， $t ^ { * } \in Z _ { q } ^ { * }$ ，计算 $\boldsymbol { T } ^ { * } = \boldsymbol { t } ^ { * } \boldsymbol { P }$ ， $h _ { 1 } = H _ { 1 } ( I D _ { J } , R _ { J } )$ ，$h _ { _ 2 } ^ { ^ { * } } = H _ { _ 2 } ( m _ { b } , T ^ { ^ * } , R _ { _ I } , X _ { _ I } )$ ， $u ^ { * } = t ^ { * } + x _ { I } h _ { 1 } + D _ { I } h _ { 2 } ^ { * }$ ，计算$V _ { I } = H _ { 3 } ( x _ { I } X _ { J } , ( R _ { J } + P _ { p u b } h _ { 1 } ) D _ { I } )$ ， $c = V _ { I } \oplus m _ { b }$ 最后将 $\boldsymbol { \sigma } ^ { * } = ( c , h _ { 2 } ^ { * } , u ^ { * } )$ 发送给$A _ { 1 }$ 。

$A _ { 1 }$ 可以继续询问，但不可以执行 $\boldsymbol { I D } ^ { * }$ 的部分私钥和对 $\sigma ^ { * }$ 的解签密查询，最后输出 $A _ { 1 }$ 对 $b$ 的猜测 $\boldsymbol { b } ^ { \prime }$ 。 $A _ { 1 }$ 若未选择 $I D _ { \jmath }$ 作为挑战用户，进行过 $\boldsymbol { I D } ^ { * }$ 部分私钥提取询问，进行过 $V _ { _ { I } }$ 的 $\boldsymbol { H } _ { 3 }$ 询问，则挑战失败。假设 $A _ { 1 }$ 在多项式时间内至多进行 $q _ { p p }$ 次部分私钥询问， $q _ { i }$ 次 $\boldsymbol { H } _ { i }$ 查询。因此 $A _ { 1 }$ 选择 $I D _ { J }$ 为挑战用户的概率是 $\textstyle \bigwedge _ { q _ { 1 } }$ （20$A _ { 1 }$ 未进行过部分私钥查询的概率至少是 $\left( 1 - \mathop { \gamma } _ { q _ { 1 } } \right) ^ { q _ { p p } }$ ， $A _ { 1 }$ 未进行过$V _ { _ { I } }$ 的 $\boldsymbol { H } _ { 3 }$ 询问的概率 $\left( 1 - \mathop { V _ { 2 } } _ { \displaystyle { q _ { 3 } ^ { 2 } } } \right)$ ，则 $c$ 成功解决ECDLP 的概率为（20 $S u c c _ { A _ { 1 } } ^ { E C D L P } \ge \sqrt [ \xi ] { q _ { 1 } } \left( 1 - \big / { q _ { 1 } } \right) ^ { q _ { p p } } \left( 1 - \big / { q _ { 3 } ^ { 2 } } \right)$ ，证毕。

引理2攻击者 $A _ { 2 }$ 下的机密性。在随机预言模型且ECDLP难解的情况下，在概率多项式时间内存在敌手 $A _ { 2 }$ 以 $\boldsymbol { \varepsilon }$ 的优势赢得游戏IND-CCA2，则存在一个区分者 $\boldsymbol { c }$ 以（204号 $S u c c _ { A _ { 1 } } ^ { E C D L P } \ge \sqrt [ \xi ] { q _ { 1 } } \left( 1 - \big / \frac { \ d } { q _ { 1 } } \right) ^ { q _ { p p } } \left( 1 - \big / \frac { \ d } { q _ { 3 } ^ { 2 } } \right)$ 的概率解决 ECDLP 困难问题。

证明若想攻破本文的CL-SC 方案，就必须存在算法 $c$ 利用 $A _ { 2 }$ （第二类攻击者）攻击解决ECDLP 问题，即已知 $( p , a p )$ ，可求 $a$ 的值。证明过程与引理1相似。

# 3.3 不可伪造性分析

引理3攻击者为A的不可伪造性。在随机预言模型下且ECDLP难解的情况下，在概率多项式时间内存在敌手A以 $\varepsilon$ 的优势赢得游戏EUF-CMA，则存在一个区分者 $c$ 以（204号 $S u c c _ { A _ { 1 } } ^ { E C D L P } \ge \sqrt [ \varepsilon ] { q _ { 1 } } \left( 1 - \big / \frac { \ d } { \ d q _ { 1 } } \right) ^ { q _ { p p } }$ 的概率解决 ECDLP 困难问题。

证明若想攻破本文的CL-SC 方案，就必须存在算法 $c$ 利用 $A _ { 1 }$ （第一类攻击者）攻击解决ECDLP问题，即已知 $( p , a p )$ ，可求 $a$ 的值。

a)初始化。 $c$ 运行系统参数建立算法生成$p a r a m s = \{ p , q , G , P , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } \}$ ，并将主密钥保存，其他参数发送给 $A _ { \mathrm { { l } } }$ 。其中 $P _ { p u b } = a P$ ，用 $a$ 模拟系统主秘钥。

b)询问阶段。同引理1。

c)伪造阶段。当多项式有界询问结束后， $A _ { 1 }$ 提交用于挑战的两个用户身份 $( I D _ { \scriptscriptstyle I } , I D _ { \scriptscriptstyle b } )$ 和对某一明文 $m$ 的有效签密$\sigma = ( c , h _ { 2 } , u )$ ，若 $I D _ { I } \neq I D ^ { * }$ 则终止;否则通过分叉引理[9]，重放 $H _ { 2 }$ 询问可得两个有效的签密 $( c , h _ { 2 } , u )$ 和 $( c , h _ { 2 } ^ { * } , u ^ { * } )$ 。并且 $u ^ { * } = t + x _ { i } h _ { 1 } + D _ { i } h _ { 2 } ^ { * }$ ，$u = t + x _ { i } h _ { 1 } + D _ { i } h _ { 2 }$ ， $D _ { i } = r _ { i } + a \cdot H _ { \mathrm { 1 } } ( I D _ { i } , R _ { i } )$ ，所以可以解得(u-u)/(h-h)-r，进而C成功解决了ECDLP问题。

若 $A _ { 1 }$ 对 $I D _ { \imath }$ 进行过部分私钥询问或 $I D _ { I } \neq I D ^ { * }$ 则游戏终止。假设 $A _ { \mathrm { i } }$ 在多项式时间内至多进行 $q _ { p p }$ 次部分私钥询问， $q _ { i }$ 次 $H _ { i }$ 查询。 $A _ { 1 }$ 未对 $I D _ { \imath }$ 进行私钥询问的概率至少为 $\Big ( 1 - \mathop { \sum } _ { q _ { 1 } } \Big ) ^ { q _ { p p } }$ ， $A _ { 1 }$ 选择$I D _ { I } = I D ^ { * }$ 作为挑战用户的概率为 $\textstyle \bigwedge _ { q _ { 1 } }$ ，则 $c$ 成功解决 ECDLP 的概率为 $S u c c _ { A _ { 1 } } ^ { E C D L P } \geq { \mathcal { E } } / { q _ { 1 } } { \left( 1 - \biggamma _ { q _ { 1 } } ^ { \boldsymbol { \mathscr { q } } _ { p p } } \right) ^ { q _ { p p } } }$ ，证毕。

引理4攻击者为 $A _ { 2 }$ 的不可伪造性。在随机预言模型下且ECDLP难解的情况下，在概率多项式时间内存在敌手 $A _ { 2 }$ 以 $\varepsilon$ 的优势赢得游戏EUF-CMA，则存在一个区分者 $c$ 以（20 $S u c c _ { A _ { 1 } } ^ { E C D L P } \ge \xi \bigg / _ { q _ { 1 } } \Big ( 1 - \big \gamma _ { q _ { 1 } } \Big ) ^ { q _ { p p } }$ 的概率解决ECDLP困难问题。

证明若想攻破本文的CL-SC 方案，就必须存在算法 $c$ 利用 $A _ { 2 }$ （第二类攻击者）攻击解决ECDLP问题，即已知 $( p , a p )$ ，可求 $a$ 的值。证明过程与引理三相似。

# 4 性能分析

本文提出的新的CL-SC方案无须使用双线性对运算和指数运算，在签密阶段使用6次点乘运算，分别为 $T = t \cdot P$ ，$\begin{array} { r } { u = t + x _ { _ A } \cdot h _ { 1 } + D _ { _ A } \cdot h _ { 2 } , \quad K _ { 1 } = x _ { _ A } \cdot X _ { _ B } , \quad K _ { 2 } = ( R _ { _ B } + P _ { _ { p u b } } \cdot h _ { 1 } ) \cdot D _ { _ A } } \end{array}$ ；在解签密阶段使用8次点乘运算，分别为 $\overset { \triangledown } { \boldsymbol { T } ^ { * } } = \boldsymbol { u } \cdot \boldsymbol { P } - \boldsymbol { X } _ { \mathrm { { A } } } \cdot \boldsymbol { h } _ { 1 } - \boldsymbol { R } _ { \mathrm { { A } } } \cdot \boldsymbol { h } _ { 2 } - \boldsymbol { P } _ { p u b } \cdot \boldsymbol { \dot { h _ { 1 } } } \cdot \boldsymbol { h _ { 2 } }$ ，$V _ { _ B } = H _ { 3 } ( X _ { _ A } \cdot x _ { _ B } , ( R _ { _ A } + P _ { p u b } \cdot h _ { 1 } ^ { \cdot } ) \cdot D _ { _ B } ) ,$ 0

下面将从计算效率、正确性、机密性和不可否认性几个方面来对方案进行性能分析。将本文所提出的签密方案与文献$[ 1 1 \sim 1 4 ]$ 进行对比，其中分别用E、P、M来表示指数运算，双线性对运算和点乘运算。分析结果如表1所示。

表1签密方案性能比较  

<html><body><table><tr><td>方案</td><td>签密</td><td>解签密</td><td>正确性</td><td>机密性</td><td>不可否认性</td></tr><tr><td>文献[11]</td><td>2E+6M</td><td>2P+2E+5M</td><td>√</td><td>√</td><td>√</td></tr><tr><td>文献[12]</td><td>2P+5M</td><td>2P+5M</td><td>√</td><td>√</td><td>√</td></tr><tr><td>文献[13]</td><td>1E+2M</td><td>6E+7M</td><td>√</td><td>×</td><td>×</td></tr><tr><td>文献[14]</td><td>5M</td><td>5M</td><td>×</td><td>×</td><td>×</td></tr><tr><td>本文方案</td><td>6M</td><td>8M</td><td>√</td><td>√</td><td>√</td></tr></table></body></html>

从表1可以看出，文献[11]的方案中使用了双线性对运算、指数运算和点乘运算，文献[12]的方案中使用了双线性对运算和点乘运算。根据Chen等人[15]研究表明，执行一次双线性对所消耗的运算量相当于执行21次椭圆曲线上的点乘运算。因此，就计算效率方面，本文优于以上两种方案。在安全性上，文献[13]不满足机密性和不可否认性，不能抵抗攻击者 $A _ { 1 }$ 的公钥替换攻击，即攻击者A通过替换发送者的公钥，从而冒充发送者伪造签密文发送给接收者而不被发现。文献[14]中的方案在计算签密的过程中使用KGC生成的临时秘密值，使整个方案面临主密钥泄露的危险，并且该方案不能抵抗 $A _ { 2 }$ 的伪造攻击和 $A _ { 1 }$ 公钥替换的机密性攻击。在文献[16，17]中详细描述对文献[14]的攻击方法，在此不做赘述。因此本文方案比文献[13，14]中的方案更加安全。

# 5 结束语

本文以汤永利等人的签名方案为基础，构造了一种无对运算的CL-SC方案，并在随机预言模型下证明了它的安全性。在与其他方案对比后，可知该方案的性能更优。CL-SC方案计算开销低、安全性高，在电子支付、无线传感设备、汽车自动驾驶等方面有广泛的应用。然而现有的一些方案仍存在安全性差、效率低等问题，因此如何构造安全高效的方案仍是值得研究的问题。

# 参考文献：

[1]ZhengYuliang.Digitalsigncryptionorhowtoachievecost (signature&encryption) $< <$ cost (signature) +cost (encryption)[C]//Proc of the 17th Annual International Cryptology Conference on Advances in Cryptology. Berlin: Springer-Verlag,1997: 165-179.   
[2]Barbosa M,Farshim P. Certificateless signcryption [C]/ Proc of ACM Symposium on Information, Computer and Communications Security. New York:ACMPress,2008: 369-372.   
[3]Selvi S S D, Vivek S S,Rangan C P.Cryptanalysis of certificateless signcryption schemes and an eficient construction whitout pairing [C]// Proc of the 5th International Conference on Information Security and Cryptology.Berlin: Springer-Verlag,2010:75-92.   
[4]朱辉，李晖，王育民．不使用双线性对的无证书签密方案[J].计算机 研究与发展,2010,47(9):1587-1594.   
[5] 刘文浩，许春香．无双线性配对的无证书签密方案[J]．软件学报,2011, 22 (8): 1918-1926.   
[6] 汤永利，王菲菲，闫玺玺，等．高效可证安全的无证书签名方案[J]. 计算机工程,2016,42(3):156-160.   
[7]Liu Zhenhua,Hu Yupu, Zhang Xiangsong,et al. Certificateless signcryption scheme in the standard model[J]. Information Sciences,201o,180(1):452- 464.   
[8] 沈丽敏，张福泰，孙银霞．对一种无双线性配对的无证书签密方案的安 全性分析 [J].密码学报,2014,1(2):146-154.   
[9]Pointcheval D,Stern J. Security arguments for digital signatures and blind signature [J].Journal of Cryptology,2000,13 (3):361-396.   
[10]周彦伟，杨波，张文政．不使用双线性映射的无证书签密方案的安全分 析及改进[J].计算机学报,2016,39(6):1257-1266.   
[11]邓伦治，李思维，于亚峰．高效的无证书签密方案[J].厦门大学学报： 自然科学版,2014,53(6):810-816.   
[12]汤鹏志，张庆兰，杨俊芳．一种改进的基于双线对的无证书签密方案 [J]．合肥工业大学学报：自然科学版,2016,39(7):917-923.

[13]高键鑫，吴晓平，秦艳琳，等．无双线性对的无证书安全签密方案[J].

计算机应用研究,2014,31(4):1195-1198.  
[14]夏昂，张龙军．一种新的无双线性对的无证书安全签密方案[J].计算机应用研究,2014,31(2):532-535.  
[15] Chen L,Cheng Z,Smart NP.Identity-based Keyagreement protocols frompairings [J]. International Journal of Information Security,2oo7,6(4):213-241.  
[16]邹昌芝．可证安全的无证书签密方案[J].计算机应用与软件,2016,33(3):327-333.  
[17]樊爱宛，潘中强，赵伟艇．两种无证书签密方案的密码分析和改进[J].计算机应用与软件,2016,33(7):313-317,333.