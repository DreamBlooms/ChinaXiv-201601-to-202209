# 一种基于双重KGC的无证书短签名方案

左黎明ab，张梦丽äb，胡凯雨ab，易传佳ab(华东交通大学 a.理学院;b.系统工程与密码学研究所，南昌 330013)

摘要：为了解决无证书短签名方案中单KGC权力过于集中的问题,提出一种基于双重KGC的无证书短签名方案，其中双重KGC之间相互制约，有效地减少了单KGC主密钥泄露和被恶意操控带来的危害。随后在随机预言机模型、k-CAA 和Inv-CDH问题困难性假设下，证明了签名方案在适应性选择消息攻击下是存在性不可伪造的。最后与其他无证书数字签名方案进行了比较，并用C语言实现了该方案.实验结果和分析表明该方案计算量较低，运行效率和安全性较高。

关键词：无证书；双重KGC；短签名；可证明安全；随机预言机模型 中图分类号：TP309.7 doi: 10.19734/j.issn.1001-3695.2018.10.0828

Certificateless short signature scheme with double KGC

Zuo Liminga,b, Zhang Menglia,b, Hu Kaiyua,b, Yi Chuanjiaa,b (a.School ofScience,b.SEC Institute,East China Jiaotong University,Nanchang 33o013,China)

Abstract: In orderto solve the problem that the powerof thesingle KGC in certificatelessshort signature is too concentrated,this paper proposed a certificatelessshort signature scheme with double KGC,in which double KGC was restricted byeach other.So itcan effctivelyreduce the harm of thesingle KGC's main key leakage and malicious manipulation.Then,under the random oracle model,the difficult problem of $\mathbf { k }$ -CAA and Inv-CDH,it proved that the signaturescheme was existentiallyunforgeable under adaptive chosen message attack.Finally,itcompared the signature scheme with other certificatelesschemes,and implemented the signature scheme in Clanguage.The experimentalresults and analysis show that the scheme has lower computational cost, higher operating efficiency and security.

Key words:certificateless; double kgc; short signature; provably secure; random oracle model

# 0 引言

为了解决传统公钥密码体制中用户公钥证书管理和证书传递耗时的问题，Shamir[1]于1984年提出了基于身份的密码体制，其中所有用户的私钥由一个可信的第三方私钥生成器(privatekeygenerator,PKG)生成，因此恶意的 $P K G$ 可以冒充用户生成签名或者解密发给用户的密文，这样就存在一个密钥托管问题。为了解决基于身份的密码体制的密钥托管问题，2003年，Al-Riyami和Paterson[2]提出了一个无证书的公钥密码体制，在无证书公钥密码体制中，用户私钥由密钥生成中心(keygenerationcentre,KGC)与用户共同产生，这样既解决了基于身份的密码体制中的密钥托管问题，同时也消除了传统密码体制中证书的存储和管理问题。随后，许多无证书数字签名方案相继被提出。2012年，冯蕾等人[3]在标准模型下提出了一个高效的无证书多重签名方案。2016年，Islam 等人[4基于双线性对构建了一个无证书数字签名方案。2017，Gao等人[5]基于CDH(computationalDiffie-Hellman)问题提出了无泄露的无证书数字签名方案。

在无证书密码系统中，有两种类型攻击者[6] $\boldsymbol { A } _ { I }$ 和 $A _ { 2 }$ ，一种是不诚实的用户 $\boldsymbol { A } _ { I }$ ，它不知道系统主密钥及用户部分私钥，但可以代替用户的公钥；另一种是恶意的 $K G C A _ { 2 }$ ，它掌握系统主密钥和用户部分私钥，但不能替换用户的公钥。

目前已有的基于单KGC的无证书签名方案，部分不能抵抗恶意 $K G C$ 攻击。2017年，张永洁等人[7]分析了文献[8\~10]提出的无证书聚合签名方案的安全性，指出这三个方案存在恶意KGC攻击，并分别构造了攻击算法，实现了伪造攻击。同年，葛丽霞等人[1分析了刘晓红和张建中提出的一个无证书代理签名方案[12]，发现其不能抵抗恶意KGC攻击。

因此可见，单个 $K G C$ 的无证书签名方案由于 $K G C$ 权力过大，恶意KGC 可以掌握系统主密钥和用户的部分私钥，从而可以伪造签名，会对系统产生一定危害。为解决单KGC权力过于集中的问题，本文提出了一种在随机预言机模型下可证安全的基于双重KGC的无证书短签名方案，相比于其他基于单KGC无证书签名方案，一方面，双重KGC之间可以相互制衡，具有分权的效果，使得针对KGC的相关攻击的成功概率减少，从而可以降低对系统的危害，另一方面，结合了短签名[13]的优势，增强了本文方案的实用性。

# 1 基础知识

# 1.1双线性映射

双线性对[14,15](Bilinear Pairings)：设 $G _ { \mathrm { 1 } }$ 为 $q$ 阶加法循环群， $G _ { 2 }$ 为 $q$ 阶乘法循环群， $P$ 为 $G _ { \mathrm { { l } } }$ 的生成元，称映射$e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 为双线对，如果 $\boldsymbol { \mathscr { e } }$ 满足以下三条性质：

a)双线性。对任意 $m , n \in Z _ { q } ^ { * }$ ，有 $e ( m P , n P ) = e ( P , P ) ^ { m n }$ 。b)非退化性。 $e ( P , P ) \neq 1$ 。c)可计算性。假设 $m , n \in Z _ { q } ^ { * }$ ，则存在多项式时间算法计算

$e ( m P , n P )$ 。

# 1.2 困难问题的假设

定义1 $k { \mathrm { - } } C A A$ 问题。对某一个整数 $k$ 和 $s \in Z _ { q } ^ { * }$ （ $s$ 是未知的随机数）， $P \in G _ { 1 }$ ，给定 $\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { k } \} \in Z _ { q } ^ { * }$ ， $P , s P$ 和$\left\{ { \frac { 1 } { \sin \displaystyle + e _ { 1 } } } P , { \frac { 1 } { s + e _ { 2 } } } P , \cdots , { \frac { 1 } { s + e _ { k } } } P \right\}$ ，计算 $( c , { \frac { 1 } { s + c } } P )$ ，其中 $c \in Z _ { q } ^ { * }$ ，且$c \not \in \{ e _ { 1 } , e _ { 2 } , \cdots , e _ { k } \}$ 。

定义2逆 CDH 问 题(inverse computationalDiffie-Hellmanproblem， $I n \nu – C D H )$ 。给定 $P \in G _ { \mathrm { l } }$ ， $a P \in G _ { \mathrm { 1 } }$ （ $a \in Z _ { q } ^ { * }$ 是未知的)，计算 $a ^ { - 1 } P$ 。

# 1.3基于双重KGC的无证书数字签名定义

一个基于双重 $K G C$ 的无证书数字签名方案由7个算法组成，具体如图1所示。

2.部分私钥提取(Extract-Partial-Private-1.系统建立(Setup): Key):输入安全参数L,KGCA运行算 输入params,KGCA系统主密钥 $\scriptstyle x _ { A } .$ 和身份 $I D _ { \mathrm { i } }$   
法，返回KGCA系统主密钥 $x _ { A } ,$ （20 KGCA运行该算法并输出KGCA部分私钥 $d _ { A }$ ：KGCB运行算法返回 $K G C _ { B }$ 系 输入params,KGCB系统主密钥xB,和KGCA部  
统主密钥XB和系统公共参数 分私钥 $d _ { A }$ ，KGCB运行该算法并输出部分私钥  
params. $d _ { I D } ,$ 并通过安全信道发给相应的用户4.私钥建立(Set-Private-3.秘密值建立(Set-SecretKey): Value):输入params和用户的身份ID,输出用  
输入params,用户的部分私户的秘密值XID该算法由系统中的每个用户来钥diD和他的秘密值，输出私钥 执行.秘密值空间是由系统公共参数params  
skID,该算法由系统中每个用  
户来执行. 和用户的身份ID决定的.6.签名(CL-Sign):  
5.公钥建立(Set-Public- 输入params,待签名消息 ${ } _ { . m , }$ 用户的身份ID公  
Key):输入params和用户的 钥pkiD以及私钥 $s k _ { I D } ,$ 该算法输出签名S.  
秘密值 $\boldsymbol { x } _ { I D } ,$ 输出用户的公钥  
pkD.该算法由系统用户执行，  
且执行完该算法后公开公钥. 7.验证(CL-Verify):  
公钥空间是由系统公共参数 这是一个确定的签名验证算法.输入params,签名人的身份ID,公钥 $p k _ { I D } ,$ 消息m以及签名 $s ,$   
params和用户的身份信息ID返回“1”说明该签名有效,否则返回 $^ { \mathfrak { s } } 0 ^ { \mathfrak { s } }$ ，说  
共同定义的.明该签名无效.

# 1.4基于双重KGC的无证书数字签名的安全模型

在无证书密码系统中，存在两种类型的攻击。一方面，因为用户公钥没有得到认证，所以敌手有权利用自己选择的不合法公钥替换用户的公钥，但不知道系统主密钥及用户的部分私钥，即存在用户公钥替换攻击；另一方面，由于KGC知道系统主密钥，从而可以计算出用户部分私钥，但是不能替换用户公钥，即存在恶意但被动的KGC攻击。因此，一个安全的无证书密码方案应该至少抵抗上述两种攻击。

本文基于上述传统单 $K G C$ 无证书攻击类型，结合双重$K G C$ 的特点，详细给出了针对于本文方案具备不同能力的两种敌手，一种是不诚实的用户，记为 $A _ { 1 }$ ，另一种是恶意但被动的 $K G C$ ，记为 $A _ { 2 }$ 。这里将本文方案里的双重KGC记为$K G C _ { A }$ 和 $K G C _ { B }$ 。

类型 $\boldsymbol { \mathsf { I } }$ 的敌手 $A _ { \mathrm { l } }$ 。至多知道一个 $K G C$ 系统主密钥，但不知道用户的部分私钥，并且能替换用户的公钥。

类型 $\pmb { { \cal U } }$ 的敌手 $A _ { 2 }$ 。掌握 $K G C _ { A }$ 和 $K G C _ { B }$ 系统主密钥，知道用户的部分私钥，但它不能替换用户的公钥。

定义3一个无证书数字签名方案在适应性选择消息攻击下是存在性不可伪造的，如果敌手 $A _ { 1 }$ ， $A _ { 2 }$ 在以下两个游戏中获胜的概率是可以忽略的。

游戏1

挑战者 $c$ 和类型 $I$ 的敌手 $A _ { \mathrm { l } }$ 交互如图2所示。最后 $A _ { \mathrm { l } }$ 输出一个挑战身份 $I D ^ { * }$ 和公钥 ${ p k } _ { I D ^ { * } }$ 的消息/签名对 $( m ^ { * } , S ^ { * } )$ 。如果$V e r i f y ( p a r a m s , I D ^ { * } , m ^ { * } , p k _ { _ { I D ^ { * } } } , S ^ { * } ) = 1$ 和下面的条件成立，则 $A _ { 1 }$ 获胜。

类型I挑战者C 敌手A发送params,发送至多一个KGC的主密钥  
输入安全参数1,运提交任何一个值的Hash值询问  
行Setup算法产生 1.Hash 值询问  
KGCA,KGCB系统  
主密钥分别为XA和 返回相应的Hash值  
XB和系统参数  
params,然后发送  
ams给A，，秘 提交一个分外 2.部分私钥询问返回ID对应的部分私钥dID_提交一个除ID\*以外合法身份ID的私钥询问 3.私钥询问返回ID对应的私钥sKIDT提交一个除ID\*以外合法身份ID的公钥询问 4.公钥询问返回ID对应的公钥pkID提交一个自己选择的公钥pkID'替换pkID 5.公钥替换提交一个除ID\*以外合法身法ID和消息m的签名询问6.签名询问返回(m,ID对应的签名S根据身份ID对应的私钥 输出一个身份ID\*生成消息m pkiD对应的消息/的签名S 对 $\cdot ( m ^ { * } , S ^ { * } )$ ，游戏结  
Fig.3Game process between Challenger C and adversary of type IIa) $I D ^ { * }$ 从来没有被提交给私钥提取预言机;b) $I D ^ { * }$ 从来没有既被提交给替换公钥预言机又时提交给  
部分私钥提取预言机；c) $( m ^ { * } , S ^ { * } , I D ^ { * } , p k _ { I D ^ { * } } )$ 不是由签名预言机得到的。

![](images/ab340494fd8f715be1aa5d45397ddcd0bf9daa1e3a68fb8ec5a990c8b6d7027c.jpg)  
图1基于双重KGC 的无证书数字签名定义Fig.1Certificateless digital signature definition  
图2挑战者C与类型I敌手游戏过程  
Fig.2Game process between Challenger C an d adversary of type I   
图3挑战者C与类型ⅡI敌手游戏过程

游戏2

挑战者 $c$ 和类型 $I I$ 的敌手 $A _ { 2 }$ 交互如图3所示。最后 $A _ { 2 }$ 输出一个挑战身份 $I D ^ { * }$ 和公钥 ${ p } k _ { \mathrm { \it I D ^ { * } } }$ 的消息/签名对 $( m ^ { * } , S ^ { * } )$ ：$V e r i f y ( p a r a m s , I D ^ { * } , m ^ { * } , p k _ { _ { I D ^ { * } } } , S ^ { * } ) = 1$ 和下面的条件成立，则 $A _ { 2 }$ 获胜。

a) $I D ^ { * }$ 从来没有被提交给私钥提取预言机；  
b) $( m ^ { * } , S ^ { * } , I D ^ { * } , p k _ { I D ^ { * } } )$ 不是由签名预言机得到的。

# 2 基于双重KGC的无证书短签名方案

# 2.1方案构造

a)系统建立。给定安全参数 $\mathbf { \xi } _ { l }$ ， $G _ { \mathrm { { l } } }$ 和 $G _ { 2 }$ 分别是加法循环群和乘法循环群， $P$ 是 $G _ { 1 }$ 的生成元， $G _ { 1 }$ 的阶 $q$ 。双线性对$e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ ，选择两个抗碰撞的Hash 函数： $H _ { 1 } : \{ 0 , 1 \} ^ { * } \to Z _ { q } ^ { * }$ ，$H _ { 2 } : \{ 0 , 1 \} ^ { * } \times \mathbf { G } _ { 1 }  Z _ { q } ^ { * }$ 。 $K G C _ { A }$ 选取一个秘密值 $\boldsymbol { x } _ { A } \in Z _ { \boldsymbol { q } } ^ { * }$ 作为 $K G C _ { A }$ 系统的私钥，计算 $y _ { A } = x _ { A } P \in G _ { 1 }$ 作为 $K G C _ { A }$ 系统的公钥并公布，然后秘密保存 $x _ { A }$ 。 $K G C _ { B }$ 选取一个秘密值 $x _ { B } \in Z _ { q } ^ { * }$ 作为 $K G C _ { B }$ 系统的私钥，计算 $y _ { B } = x _ { B } P \in G _ { 1 }$ 作为 $K G C _ { B }$ 系统的公钥，并计算$T = x _ { B } y _ { A } = x _ { A } x _ { B } P$ 作为联合公钥公布，然后秘密保存 $x _ { B }$ 。任何人都可以通过 $e ( T , P ) = e ( y _ { A } , y _ { B } )$ 来验证 $T$ 的有效性。 $K G C _ { A }$ 和$K G C _ { B }$ 公布联合系统参数 $p a r a m s = \{ G _ { 1 } , G _ { 2 } , e , q , P , H _ { 1 } , H _ { 2 } , y _ { A } , y _ { B } , T \}$ 。

b)部分私钥提取。给定身份 $I D \in \left\{ 0 , 1 \right\} ^ { * }$ ， $K G C _ { A }$ 计算$Q _ { I D } = H _ { 1 } ( I D )$ ， $d _ { _ A } = { \frac { 1 } { x _ { _ A } + Q _ { _ I D } } } P$ ，将 $d _ { \scriptscriptstyle A }$ 通过安全信道发送给 $K G C _ { B }$ □$K G C _ { B }$ 首先验证 $d _ { \scriptscriptstyle A }$ 的有效性通过下面等式成立：$e ( d _ { A } , y _ { A } + Q _ { I D } P ) = e ( P , P )$ 。验证成功后，计算 $Q _ { I D } = H _ { 1 } ( I D )$ ，$d _ { I D } = \frac { 1 } { x _ { B } + Q _ { I D } } d _ { A }$ ，然后通过安全信道发送部分私钥 $d _ { \scriptscriptstyle I D }$ 给身份为 $I D$ 的用户。

c)秘密值建立。用户 $I D$ 随机挑选 $x _ { I D } \in Z _ { q } ^ { * }$ 作为自己的秘密值。d)私钥建立。用户根据部分私钥 $d _ { \scriptscriptstyle I D }$ 和他的秘密值 $x _ { I D }$ ，输出数据 $( d _ { I D } , x _ { I D } )$ 作为该用户的私钥。

e)公钥建立。用户计算 $Q _ { I D } = H _ { 1 } ( I D )$ ，$R = T + Q _ { I D } y _ { A } + Q _ { I D } y _ { B } + Q _ { I D } ^ { 2 } P$ ，产生该用户的公钥为 $p k _ { I D } = x _ { I D } R$ 。

f)签名。身份为 $I D$ 的用户对消息 $m \in \left\{ 0 , 1 \right\} ^ { * }$ 签名如下：

(a)令 $h = H _ { \scriptscriptstyle 2 } ( m , p k _ { \scriptscriptstyle I D } )$ ;

(b)计算S= $S = \frac { 1 } { h + x _ { I D } } d _ { I D }$

则 $s$ 就是身份为 $I D$ 的用户对消息 $m$ 的签名。

g)验证。给定消息/签名对 $( m , S )$ ，验证者计算如下：

(a)令 $h = H _ { \scriptscriptstyle 2 } ( m , p k _ { \scriptscriptstyle I D } )$ ：

(b)接受该签名并返回a）当且仅当以下等式成立：$e ( S , h R + p k _ { I D } ) = e ( P , P )$ 。

签名等式的正确性证明如下：

$$
e ( S , h R + p k _ { I D } ) \ = e ( \frac { 1 } { h + x _ { I D } } \cdot d _ { I D } , h R + p k _ { I D } )
$$

$$
= e ( \frac { 1 } { h + x _ { I D } } \cdot \frac { 1 } { x _ { B } + Q _ { I D } } \cdot \frac { 1 } { x _ { A } + Q _ { I D } } P , h R + p k _ { I D } )
$$

$$
\begin{array} { l } { { \displaystyle = e ( \frac { 1 } { h + x _ { I D } } \cdot \frac { 1 } { x _ { A } x _ { B } + x _ { A } Q _ { I D } + x _ { B } Q _ { I D } + Q _ { I D } ^ { 2 } } P , h R + p k _ { I D } ) } } \\ { { \displaystyle = e ( \frac { 1 } { h + x _ { I D } } \cdot \frac { 1 } { x _ { A } x _ { B } + x _ { A } Q _ { I D } + x _ { B } Q _ { I D } + Q _ { I D } ^ { 2 } } P , h R + x _ { I D } R ) } } \end{array}
$$

$$
\begin{array} { l } { \displaystyle = e ( \frac 1 { h + x _ { I D } } \cdot \frac 1 { x _ { A } x _ { B } + x _ { A } Q _ { I D } + x _ { B } Q _ { I D } + Q _ { I D } ^ { 2 } } P , ( h + x _ { I D } ) R ) } \\ { \displaystyle = e ( \frac 1 { h + x _ { I D } } \cdot \frac 1 { x _ { A } x _ { B } + x _ { A } Q _ { I D } + x _ { B } Q _ { I D } + Q _ { I D } ^ { 2 } } P , } \\ { \displaystyle ( h + x _ { I D } ) \cdot ( x _ { A } x _ { B } P + Q _ { I D } y _ { A } + Q _ { I D } y _ { B } + Q _ { I D } ^ { 2 } P ) ) } \end{array}
$$

# 2.2 安全性分析

设单 $K G C$ 密钥泄露的概率为 $p$ ，那么本文所构造的双重 $K G C$ 密钥泄露的概率为 $p ^ { 2 }$ ，所以如果基于单 $K G C$ 是安全的，那么基于双重 $K G C$ 也是安全的。

定理1在随机预言机模型中，在 $q _ { E } - C A A$ 及 $I n \nu - C D H$ 难题假设下，本文提出的基于双重 $K G C$ 的无证书短签名方案在适应性选择消息攻击下是存在性不可伪造的。

定理1可由下面的引理1\~3推导出。

引理1针对敌手I类型，假定存在一个适应性选择消息和签名攻击算法 $A _ { 1 }$ 以在概率多项式时间 $\textit { t }$ 内以不可忽略的优势 $\varepsilon$ 攻破了本方案，不妨设 $A _ { 1 }$ 不知道 $K G C _ { A }$ 系统主密钥，但是知道 $K G C _ { B }$ 系统主密钥，并记 $q _ { H _ { i } }$ ， $q _ { E }$ ， $q _ { E } ^ { \prime }$ ， $q _ { p k }$ ， $q _ { s }$ 分别为 $A _ { 1 }$ 进行 $H _ { i } ( i = 1 , 2 )$ 询问、部分私钥提取询问、私钥提取询问、公钥询问和签名询问的次数， $t _ { H i }$ ， $t _ { E }$ ， $t _ { E ^ { \prime } }$ ， $t _ { p k }$ ， $t _ { s }$ 分别表示一次 $H _ { i }$ 预言机询问、一次部分私钥提取预言机、一次私钥提取询问、一次公钥询问、一次签名询问所需时间，则存在一个 $( t ^ { \prime } , \varepsilon ^ { \prime } )$ 算法 $c$ ， 在时间$t ^ { \prime } < t + ( q _ { E } t _ { E } + q _ { E ^ { \prime } } t _ { E ^ { \prime } } + q _ { p k } t _ { p k } + q _ { S } t _ { S } ) + 2 ( q _ { H _ { 1 } } t _ { H _ { 1 } } + q _ { H _ { 2 } } t _ { H _ { 2 } } )$ （20 内 以$\varepsilon ^ { \prime } \geq ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) ( \frac { q _ { E } } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { E } ^ { \prime } + q _ { s } } ( \frac { q _ { H _ { 1 } } - q _ { E } } { q _ { H _ { 1 } } } )$ （E++q，（q-E）优势解决qE-CAA问题。

证明 给定算法 $c$ 一个 $q _ { E } - C A A$ 问题的实例：公开$P , y _ { A } = x _ { A } P \in G _ { 1 } , \enspace , e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \in Z _ { q } ^ { * } \not \exists \not \parallel \frac { 1 } { x _ { A } + e _ { 1 } } P , \frac { 1 } { x _ { A } + e _ { 2 } } P , \cdots , \frac { 1 } { x _ { A } + e _ { q _ { E } } } \enspace ( \textit { x } _ { A } + e _ { q _ { E } } ) \in S ,$ 是未知的)， $c$ 的目标是调用 $A _ { \mathrm { l } }$ 为子程序，最后输出 $q _ { E } - C A A$ 问题的一个解 $( Q ^ { * } , { \frac { 1 } { x _ { A } + Q ^ { * } } } P )$ ，其中 $\mathcal { Q } ^ { * } \notin \left\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \right\}$ 。

在游戏中假定对任意用户身份 $I D$ ，签名攻击算法 $A _ { 1 }$ 在进行部分私钥提取询问，私钥提取询问，公钥替换，签名询问以及输出签名之前都询问过关于用户身份 $I D$ 的 $H _ { 1 }$ 和 $H _ { 2 }$ 预言机。

$c$ 运行 $K G C _ { A }$ 系统建立算法,令 $y _ { A } = x _ { A } P$ 作为 $K G C _ { A }$ 系统的公钥(这里 $x _ { A }$ 充当的是 $K G C _ { A }$ 系统主密钥, $x _ { A }$ 对 $c$ 是未知的)。

$c$ 运行 $K G C _ { B }$ 系统建立算法，选择 $x _ { B } \in Z _ { q } ^ { * }$ 充当 $K G C _ { B }$ 系统主密钥，计算 $y _ { B } = x _ { B } P$ 作为 $K G C _ { B }$ ，系统的公钥， $T = x _ { B } y _ { A } = x _ { A } x _ { B } P$ 作为系统联合公钥( $x _ { B }$ 对是已知的)，发送系统联合参数$p a r a m s = \{ P , H _ { 1 } , H _ { 2 } , y _ { A } , y _ { B } , T \}$ 和 $K G C _ { B }$ 系统主密钥 $x _ { B }$ 给 $A _ { \mathrm { l } }$ 。则攻击算法 $A _ { 1 }$ 向挑战者 $c$ 适应性执行下面询问：

a) $H _ { 1 }$ 询问： $c$ 维护一个列表 $H _ { 1 } ^ { l i s t }$ ，该列表由表项 $( \mathbf { I D } _ { i } , \boldsymbol { Q } _ { i } )$ 组成的，构造如下：准备了 $q _ { H _ { 1 } }$ 个应答 $Q _ { 1 } , Q _ { 2 } , \cdots , Q _ { q _ { H _ { 1 } } }$ ，其中将数据$e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } }$ 随机分布在集合中。当 $A _ { \mathrm { l } }$ 进行关于身份 $I D _ { i }$ 的 $\boldsymbol { H } _ { 1 }$ 询问， $c$ 执行如下操作：

(a)如果 $I D _ { i } = I D ^ { * }$ ， $c$ 从列表中挑选一个 $\boldsymbol { Q } ^ { \ast } \not \in \left\{ \boldsymbol { e } _ { 1 } , \boldsymbol { e } _ { 2 } , \cdots , \boldsymbol { e } _ { q _ { E } } \right\}$ 返回给 $A _ { 1 }$ □

(b)否则， $c$ 从集合 $\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \}$ 中随机挑选一个值 $\boldsymbol { e } _ { i }$ ，并令 $H _ { 1 } ( I D _ { i } ) = e _ { i }$ ，返回 $Q _ { i } = e _ { i }$ 给 $A _ { \mathrm { l } }$ 。

b)部分私钥提取询问。 $c$ 维护一个列表 $E ^ { l i s t }$ ，该列表由表项 $( I D _ { i } , Q _ { i } , d _ { I D _ { i } } )$ 组成。当 $A _ { 1 }$ 进行关于身份 $I D _ { i }$ 的部分私钥时，$c$ 从 $H _ { 1 } ^ { l i s t }$ 中恢复 $( I D _ { i } , Q _ { i } )$ ，然后执行如下操作：

（a)如果Q{e,），则令d=++Q (不妨设$Q _ { i } = e _ { j }$ )，然后将 $d _ { I D _ { i } }$ 返回给 $A _ { 1 }$ 并增加记录 $( I D _ { i } , Q _ { i } , d _ { I D _ { i } } )$ 到列表$E ^ { l i s t }$

(b)否则 $c$ 停止模拟并输出"FAILURE"（该事件发生用 $E _ { \mathrm { l } }$ 表示)。

c)公钥询问。 $c$ 维护一个列表 $p k ^ { l i s t }$ ，该列表由表项$( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ 组成，该表初始化为空。当 $A _ { 1 }$ 进行关于身份 $I D _ { i }$ 的公钥询问时， $c$ 检查列表中是否存在对应的值。如果存在，则输出对应的值。否则， $c$ 从列表 $H _ { 1 } ^ { l i s t } : ( I D _ { i } , Q _ { i } )$ 恢复出 $Q _ { i }$ ，然后挑选一个随机数 $r _ { i } \in Z _ { q } ^ { * }$ ，计算 $p k _ { I D _ { i } } = r _ { i } ( T + Q _ { i } y _ { A } + Q _ { i } y _ { B } + Q _ { i } { } ^ { 2 } P )$ ，并返回公钥 $p k _ { _ { I D _ { i } } }$ 给 $A _ { 1 }$ 。然后增加记录 $( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ 到列表$p k ^ { l i s t }$ 。

d)私钥提取询问。当 $A _ { 1 }$ 进行关于身份 $I D _ { i }$ 的私钥提取询问时， $c$ 首先从 $H _ { 1 } ^ { l i s t }$ 列表中恢复出 $Q _ { i }$ ，然后执行如下操作：

(a)如果 $\mathcal { Q } _ { i } \in \left\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \right\}$ ，从列表 $E ^ { l i s t }$ 和列表 $p k ^ { l i s t }$ 中恢复出相应的记录 $( I D _ { i } , Q _ { i } , d _ { I D _ { i } } )$ 和记录 $( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ ， $c$ 令$s k _ { I D _ { i } } = ( d _ { I D _ { i } } , r _ { i } )$ 并将 $s k _ { I D _ { i } }$ 作为对应私钥返回给 $A _ { 1 }$ 。

(b)否则， $c$ 停止协议并输出"FAILURE"该情况用 $E _ { 2 }$ 表示)。

e)公钥替换。 $A _ { \mathrm { l } }$ 输入 $( I D _ { i } , p k _ { I D _ { i } } ^ { \prime } )$ ， $c$ 修改列表 $p k ^ { l i s t }$ 中的记录 $( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ 为 $( I D _ { i } , { \cal Q } _ { i } , p k _ { I D _ { i } } ^ { \prime } , r _ { i } )$ ，将用户 $I D _ { i }$ 的公钥 $p k _ { I D _ { i } }$ 替换为 $p k _ { I D _ { i } } ^ { \prime }$ □

r) $H _ { 2 }$ 询问。 $c$ 维护一个列表 $H _ { 2 } ^ { l i s t }$ ，该列表由表项$( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ 组成。当 $A _ { \mathrm { l } }$ 进行关于 $( I D _ { i } , m _ { i } )$ 的 $H _ { 2 }$ 询问时， $c$ 随机选择 $h _ { i } \in Z _ { q } ^ { * }$ ，令 $h _ { i } = H _ { \scriptscriptstyle 2 } ( m _ { i } , p k _ { \scriptscriptstyle I D _ { i } } )$ 并返回给 $A _ { 1 }$ ，然后增加记录 $( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ 到 $H _ { 2 } ^ { l i s t }$ 。

g)签名询问。当 $A _ { \mathrm { l } }$ 进行关于 $( I D _ { i } , m _ { i } )$ 的签名询问时， $c$ 首先从 $H _ { 1 } ^ { l i s t }$ 中恢复 $( I D _ { i } , Q _ { i } )$ ，然后执行如下操作：

(a)如果 $\mathcal { Q } _ { i } \in \left\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \right\}$ ， $c$ 从列表 $E ^ { l i s t }$ 提取记录$( I D _ { i } , Q _ { i } , d _ { I D _ { i } } )$ ，从 $p k ^ { l i s t }$ 中提取记录 $( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ ，从列表 $H _ { 2 } ^ { l i s t }$ 中提取 记录 $( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ （204号 计算$S _ { i } = \frac { 1 } { r _ { i } + h _ { i } } d _ { I D _ { i } } = \frac { P } { ( r _ { i } + h _ { i } ) ( x _ { A } + Q _ { i } ) ( x _ { B } + Q _ { i } ) } \circ$

(b)否则，停止协议，输出"FAILURE"(该情况用 $E _ { 3 }$ 表示)。$c$ 输出签名 $S _ { i }$ 0

最后， $A _ { 1 }$ 停止训练并输出一个挑战身份 $I D ^ { * }$ 的消息/签名对 $( m ^ { * } , S ^ { * } )$ ， $I D ^ { * }$ 对应的公钥为 $p k _ { _ { I D } ^ { * } }$ ，且满足等式$V e r i f y ( m ^ { * } , I D ^ { * } , p k _ { I D ^ { * } } , S ^ { * } ) = 1$ 。 $c$ 从列表 $p k ^ { l i s t }$ 提取相应的记录$( I D ^ { * } , Q ^ { * } , p k _ { I D ^ { * } } , r ^ { * } )$ ，从列表 $H _ { 2 } ^ { l i s t }$ 提取记录 $( I D ^ { * } , m ^ { * } , Q ^ { * } , p k _ { I D } , h ^ { * } )$ ，然后执行如下操作：

(a)如果 $\boldsymbol { Q } ^ { \ast } \in \left\{ \boldsymbol { e } _ { 1 } , \boldsymbol { e } _ { 2 } , \cdots , \boldsymbol { e } _ { q _ { E } } \right\}$ ， $c$ 输出"FAILURE"并停止该协议(该事件用 $E _ { 4 }$ 表示)。

(b 否则，就有下面的等式成立：

$$
e ( S ^ { * } , h ^ { * } ( T + Q ^ { * } y _ { A } + Q ^ { * } y _ { B } + Q ^ { * 2 } P ) + p k _ { I D ^ { * } } ) = e ( P , P )
$$

即

$$
\begin{array} { r l } & { e ( S ^ { * } , ( h ^ { * } + r ^ { * } ) ( T + Q ^ { * } y _ { A } + Q ^ { * } y _ { B } + Q ^ { * 2 } P ) } \\ & { = e ( S ^ { * } ( h ^ { * } + r ^ { * } ) ( x _ { A } + Q ^ { * } ) ( x _ { B } + Q ^ { * } ) , P ) } \\ & { = e ( P , P ) } \end{array}
$$

所以 $c$ 可以成功地计算出 ${ \frac { 1 } { ( x _ { A } + Q ^ { * } ) } } P = ( h ^ { * } + r ^ { * } ) ( x _ { B } + Q ^ { * } ) S ^ { * }$ 0$c$ 输出数组 $( \boldsymbol { Q } ^ { * } , \frac { 1 } { ( \boldsymbol { x } _ { A } + \boldsymbol { Q } ^ { * } ) } \boldsymbol { P } )$ $\mathcal { Q } ^ { * } \not \in \left\{ e _ { 1 } , e _ { 2 } , \cdots , e _ { q _ { E } } \right\}$ 作为问题的解，

从而 $c$ 解决了 $q _ { E } - C A A$ 问题。

下面分析 $c$ 在这个游戏中获胜的优势：

a) $A _ { 1 }$ 的 $H _ { 1 }$ 和 $H _ { 2 }$ 的询问的应答是均匀分布的，与现实不可区分。

b)部分私钥提取询问，私钥提取询问和签名询问能够顺利的进行不停止，即事件 $E _ { \mathrm { 1 } }$ ， $E _ { 2 }$ ， $\phantom { + } E _ { 3 }$ 都不发生。

c)果事件 $E _ { 1 }$ ， $E _ { 2 }$ ， $\boldsymbol { E } _ { 3 }$ 和 $E _ { 4 }$ 都不发生时，则 $c$ 能解决$q _ { E } - C A A$ 问题的一个实例。则可得事件 $E _ { 1 }$ ， $E _ { 2 }$ ， $E _ { 3 }$ 和 $E _ { 4 }$ 都不发生的概率满足：

$$
\operatorname* { P r } ( \lnot E _ { 1 } \land \lnot E _ { 2 } \land \lnot E _ { 3 } \land \lnot E _ { 4 } ) \geq ( \frac { q _ { E } } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { E } ^ { \prime } + q _ { s } } ( \frac { q _ { H _ { 1 } } - q _ { E } } { q _ { H _ { 1 } } } )
$$

但是当 $A _ { 1 }$ 没有询问 $H _ { 2 }$ 而伪造了一个有效的签名时，这种模拟是存在漏洞的，考虑到预言机输出满足均匀分布，该事件发生的概率为 $\frac { 1 } { 2 ^ { k } }$ ，所以 $c$ 在该游戏中的优势为（20 $\varepsilon ^ { \prime } \geq ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) ( \frac { q _ { E } } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { E } ^ { \prime } + q _ { s } } ( \frac { q _ { H _ { 1 } } - q _ { E } } { q _ { H _ { 1 } } } )$ ，运行时间满足$t ^ { \prime } < t + ( q _ { E } t _ { E } + q _ { E } ^ { \prime } t _ { E ^ { \prime } } + q _ { p k } t _ { p k } + q _ { S } t _ { S } ) + 2 ( q _ { H _ { 1 } } t _ { H _ { 1 } } + q _ { H _ { 2 } } t _ { H _ { 2 } } ) \ _ { \mathrm { q } }$

引理2对敌手I类型，假定存在一个适应性选择消息和签名攻击算法 $A _ { 1 }$ 以在概率多项式时间 $t$ 内以不可忽略的优势 $\varepsilon$ 攻破了本方案，不妨设 $A _ { \mathrm { i } }$ 既不知道 $K G C _ { A }$ 系统主密钥，也不知道 $K G C _ { B }$ 系统主密钥，并记 $q _ { H _ { i } }$ ， $q _ { E }$ ， $q _ { E } ^ { \prime }$ ， $q _ { p k }$ ， $q _ { s }$ 分别为 $A _ { 1 }$ 进行 $H _ { i } ( i = 1 , 2 )$ 询问、部分私钥提取询问、私钥提取询问、公钥询问和签名询问的次数， $t _ { H i }$ ， $t _ { E }$ ， $t _ { E ^ { \prime } }$ ， $t _ { p k }$ ， $t _ { s }$ 分别表示一次 $H _ { i }$ 预言机询问、一次部分私钥提取预言机、一次私钥提取询问、一次公钥询问、一次签名询问所需时间，则存在一个 $( t ^ { \prime } , \varepsilon ^ { \prime } )$ 算法 $c$ ， 在时间$t ^ { \prime } < t + ( q _ { E } t _ { E } + q _ { E ^ { \prime } } t _ { E ^ { \prime } } + q _ { p k } t _ { p k } + q _ { S } t _ { S } ) + 2 ( q _ { H _ { 1 } } t _ { H _ { 1 } } + q _ { H _ { 2 } } t _ { H _ { 2 } } )$ 内 以$\varepsilon ^ { \prime } \geq ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) ( \frac { q _ { E } } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { E } ^ { \prime } + q _ { s } } ( \frac { q _ { H _ { 1 } } - q _ { E } } { q _ { H _ { 1 } } } )$ E)E++g(qm-E)优势解决qE-CAA问题。

引理2证明类似引理1的证明，限于篇幅，本文不给出证明。

引理3对敌手ⅡI类型，假定存在一个适应性选择消息和签名攻击算法 $A _ { 2 }$ 以在概率多项式时间 $t$ 内以不可忽略的优势 $\varepsilon$ 攻破了本方案，记 $q _ { H _ { i } } , q _ { E } , q _ { p k } , q _ { s }$ 为 $A _ { 2 }$ 进行 $H _ { i } ( i = 1 , 2 )$ 询问、私钥提取询问、公钥询问和签名询问的次数， $t _ { H _ { i } }$ ， $t _ { E }$ ， $t _ { p k }$ ，$t _ { s }$ 分别表示一次 $H _ { i }$ 询问、私钥提取询问、公钥询问、签名询问所需时间，则存在一个 $( t ^ { \prime } , \varepsilon ^ { \prime } )$ 算法 $c$ ，在时间（204号 $t ^ { \prime } < t + ( q _ { E } t _ { E } + q _ { p k } t _ { p k } + q _ { s } t _ { s } ) + 2 ( q _ { H _ { 1 } } t _ { H _ { 1 } } + q _ { H _ { 2 } } t _ { H _ { 2 } } )$ （204 内 以$\varepsilon ^ { \prime } \ge ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) ( 1 - \frac { 1 } { q _ { H _ { 1 } } } ) ^ { q _ { E ^ { + q _ { s } } } } \frac { 1 } { q _ { H _ { 1 } } }$ 的优势解决 $I n \nu - C D H$ 问题。

证明定给 $c$ 一个问题的实例：给定 $P \in G _ { 1 } , h ^ { * } \in Z _ { q } ^ { * }$ 和$( r + h ^ { * } ) P \in G _ { 1 } \left( r \in Z _ { q } ^ { * } \right.$ 是未知的)， $c$ 的目标是通过与 $A _ { 2 }$ 交互输出$\frac { P } { ( r + h ^ { * } ) }$ 。

$c$ 运行 $K G C _ { A }$ 系统建立算法，挑选 $\boldsymbol { x } _ { A } \in Z _ { \boldsymbol { q } } ^ { * }$ 作为 $K G C _ { A }$ 系统主密钥,计算 $y _ { A } = x _ { A } P$ 作为 $K G C _ { A }$ 系统的公钥(这里 $x _ { A }$ 对 $c$ 是已知的)。

$c$ 运行 $K G C _ { B }$ 系统建立算法，选择 $x _ { B } \in Z _ { q } ^ { * }$ 作为 $K G C _ { B }$ 系统主密钥，计算 $y _ { B } = x _ { B } P$ 作为 $K G C _ { B }$ 系统的公钥，计算$T = x _ { B } y _ { A } = x _ { A } x _ { B } P$ 作为系统联合公钥，并令 $X = r P$ ，(这里 $x _ { B }$ 对$c$ 和 $A _ { 2 }$ 是已知的， $\boldsymbol { r }$ 对 $c$ 是未知的)， $c$ 挑选身份 $I D _ { \imath }$ 作为挑战身份，发送系统联合参数 $p a r a m s = \{ P , H _ { 1 } , H _ { 2 } , y _ { A } , y _ { B } , T \}$ ， $K G C _ { A }$ 系统主密钥 $x _ { A }$ 和 $K G C _ { B }$ 系统主密钥 $x _ { B }$ 给 $A _ { 2 }$ 。然后攻击算法 $A _ { 2 }$ 向挑战者 $c$ 适应性执行下面询问：

a) $H _ { \mathrm { 1 } }$ 询问。 $c$ 维护一个列表 $H _ { 1 } ^ { l i s t }$ ，该列表由表项 $( \mathbf { I D } _ { i } , Q _ { i } )$ 组成。当 $A _ { 2 }$ 进行关于身份 $I D _ { i }$ 的 $H _ { 1 }$ 询问时，如果该询问值已在列表中， $c$ 返回列表中对应的值。否则 $c$ 执行如下操作：

(a)如果 $I D _ { i } = I D _ { I }$ ， $c$ 挑选一个随机数 $\boldsymbol { Q } ^ { * } \notin \{ \boldsymbol { Q } _ { 1 } , \boldsymbol { Q } _ { 2 } , \cdots , \boldsymbol { Q } _ { q _ { E } } \}$ 并返回给 $A _ { 2 }$ ，并增加记录 $( I D _ { i } , Q ^ { * } )$ 到列表 $H _ { 1 } ^ { l i s t }$ 。

(b)否则， $c$ 从集合 $\{ \mathcal { Q } _ { 1 } , \mathcal { Q } _ { 2 } , \cdots , \mathcal { Q } _ { q _ { E } } \}$ 中随机挑选一个值 $Q _ { i }$ ，并定义 $H _ { 1 } ( I D _ { i } ) = Q _ { i }$ ，返回 $Q _ { i }$ 给 $A _ { 2 }$ 。 $c$ 增加记录 $( I D _ { i } , \mathcal { Q } _ { i } )$ 到列表$H _ { 1 } ^ { l i s t }$ 。

b)公钥询问。 $c$ 维护一个列表 $p k ^ { l i s t }$ ，该列表由表项$( I D _ { i } , { \cal Q } _ { i } , p k _ { I D _ { i } } , r _ { i } )$ 组成，该表初始化为空。当 $A _ { 2 }$ 进行关于 $I D _ { i }$ 的公钥询问时， $c$ 检查列表中是否存在对应的值。如果存在，则输出对应的值，否则， $c$ 从 $H _ { 1 } ^ { l i s t }$ 提取出记录 $( I D _ { i } , Q _ { i } )$ ，然后执行如下操作：

(a)如果 $I D _ { i } = I D _ { I }$ ，令 $p k _ { I D _ { i } } = ( x _ { A } x _ { B } + x _ { A } Q _ { i } + x _ { B } Q _ { i } + Q _ { i } { } ^ { 2 } ) X$ ，返回$p k _ { _ { I D _ { i } } }$ 给 $A _ { 2 }$ ，并且增加记录 $( I D _ { i } , { Q } _ { i } , { p k } _ { I D _ { i } } )$ 到列表 $p k ^ { l i s t }$ 0

(b)否则，挑选一个随机数 $r _ { i } \in Z _ { q } ^ { * }$ ，计算$p k _ { I D _ { i } } = r _ { i } ( T + Q _ { i } y _ { A } + Q _ { i } y _ { B } + Q _ { i } ^ { \ : 2 } P )$ ，返回公钥 $p k _ { I D _ { i } }$ 给 $A _ { 2 }$ 。然后增加记录 $( I D _ { i } , { \cal Q } _ { i } , p k _ { I D _ { i } } , r _ { i } )$ 到列表 $p k ^ { l i s t }$ 。

c)私钥提取询问。当 $A _ { 2 }$ 进行关于 $I D _ { i }$ 的私钥询问时， $c$ 执行如下操作：

(a)如果 $I D _ { i } = I D _ { I }$ ， $c$ 停止协议并输出"FAILURE"(该情况用 $E _ { \scriptscriptstyle 1 }$ 表示)。

(b)否则， $c$ 从 $H _ { 1 } ^ { l i s t }$ ， $p k ^ { l i s t }$ 中提取相应的记录 $( I D _ { i } , \mathcal { Q } _ { i } )$ 和记录 $( I D _ { i } , Q _ { i } , p k _ { I D _ { i } } , r _ { i } )$ ， $c$ 令 $s k _ { I D _ { i } } = ( \frac { P } { ( x _ { A } + Q _ { i } ) ( x _ { B } + Q _ { i } ) } , r _ { i } )$ （xA +Q）x+0））并发送给A。

d) $H _ { 2 }$ 询问。 $c$ 维护一个列表 $H _ { 2 } ^ { l i s t }$ ，该列表由表项$( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ 组成。当 $A _ { 2 }$ 进行关于 $( I D _ { i } , m _ { i } )$ 的 $H _ { 2 }$ 询问时， $c$ 随机选择 $h _ { j } \in Z _ { q } ^ { * }$ ，令 $h _ { i } = H _ { 2 } ( m _ { i } , p k _ { I D _ { i } } )$ 。然后增加记录$( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ 到 $H _ { 2 } ^ { l i s t }$ 。

e)签名询问。当 $A _ { 2 }$ 进行关于 $( I D _ { i } , m _ { i } )$ 的签名询问， $c$ 执行如下操作：

(a)如果 $I D _ { i } = I D _ { I }$ ，则停止协议，输出"FAILURE"(该情况用 $E _ { 2 }$ 表示)。

(b)否则， $c$ 从 $p k ^ { l i s t }$ 中恢复 $( I D _ { i } , { \cal Q } _ { i } , p k _ { I D _ { i } } , r _ { i } )$ ，从列表 $H _ { 2 } ^ { l i s t }$ 调出 $( I D _ { i } , m _ { i } , Q _ { i } , p k _ { I D _ { i } } , h _ { i } )$ ，计算 $S _ { i } = { \frac { 1 } { r _ { i } + h _ { i } } } d _ { I D _ { i } } = { \frac { P } { ( r _ { i } + h _ { i } ) ( x _ { A } + Q _ { i } ) ( x _ { B } + Q _ { i } ) } } \ ,$ $c$ 输出签名 $S _ { i }$ 。

最后， $A _ { 2 }$ 停止询问并输出一个挑战身份 $I D ^ { * }$ 的消息/签名对 $( m ^ { * } , S ^ { * } )$ ， $I D ^ { * }$ 对应的公钥为 $p k _ { _ { I D } ^ { * } }$ ，且满足等式$V e r i f y ( m ^ { * } , I D ^ { * } , p k _ { I D ^ { * } } , S ^ { * } ) = 1$ ，然后 $c$ 执行如下操作：

(a)如果 $I D ^ { * } \neq I D _ { I }$ ， $c$ 输出"FAILURE"并停止该协议(该事件用 $E _ { 3 }$ 表示)。

(b)否则， $c$ 从列表 $p k ^ { l i s t }$ 中提取相应的记录 $( I D ^ { * } , Q ^ { * } , p k _ { I D * } )$ ，从列表 $H _ { 2 } ^ { l i s t }$ 中提取记录 $( I D ^ { * } , m ^ { * } , Q ^ { * } , p k _ { I D } , h ^ { * } )$ ，从而有下面的等式成立：

即

$$
\begin{array} { r l } & { e ( S ^ { * } , h ^ { * } ( T + Q ^ { * } y _ { A } + Q ^ { * } y _ { B } + Q ^ { * 2 } P ) + p k _ { I D ^ { * } } ) = e ( P , P ) } \\ & { \quad e ( S ^ { * } , ( h ^ { * } + r ) ( T + Q ^ { * } y _ { A } + Q ^ { * } y _ { B } + Q ^ { * 2 } P ) } \\ & { \quad = e ( S ^ { * } ( h ^ { * } + r ) ( x _ { A } + Q ^ { * } ) ( x _ { B } + Q ^ { * } ) , P ) } \\ & { \quad = e ( P , P ) } \end{array}
$$

所以 $c$ 可以成功地计算出 ${ \frac { 1 } { ( r + h ^ { * } ) } } P = ( x _ { A } + Q ^ { * } ) ( x _ { B } + Q ^ { * } ) S ^ { * }$ 。 $c$ 输出数组 ${ \frac { 1 } { ( r + h ^ { * } ) } } P$ 作为对 $A _ { 2 }$ 的挑战的应答。从而 $c$ 解决了

$I n \nu - C D H$ 问题。

下面分析 $c$ 在这个游戏中获胜的优势：

a)对 $A _ { 2 }$ 的 $H _ { \mathfrak { l } }$ 和 $H _ { 2 }$ 的询问的应答是均匀分布，与现实不可区分。

b)对私钥提取询问和签名预言机询问能够顺利的进行不停止，即事件 $E _ { 1 }$ ， $\boldsymbol { E } _ { 2 }$ 都不发生。

c)所以整体来说，如果事件 $E _ { \scriptscriptstyle 1 }$ ， $E _ { 2 }$ 和 $\boldsymbol { E } _ { 3 }$ 都不发生时，则$c$ 能解决 $I n \nu - C D H$ 问题的一个实例。则可得事件 $E _ { 1 }$ ， $E _ { 2 }$ 和 $\boldsymbol { E } _ { 3 }$ 都不发生的概率满足：

$$
\operatorname* { P r } ( \lnot E _ { 1 } \land \lnot E _ { 2 } \land \lnot E _ { 3 } ) \geq ( 1 - \frac { 1 } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { s } } \frac { 1 } { q _ { H _ { 1 } } }
$$

当 $A _ { 2 }$ 没有询问 $H _ { 2 }$ 而伪造了一个有效的签名时，这种模拟是存在漏洞的，考虑到预言机输出满足均匀分布，该事件发生的概率为 $\frac { 1 } { 2 ^ { k } }$ ，所以 $c$ 在该游戏中的优势为$\varepsilon ^ { \prime } \geq ( \varepsilon - \frac { 1 } { 2 ^ { k } } ) ( 1 - \frac { 1 } { q _ { H _ { 1 } } } ) ^ { q _ { E } + q _ { s } } \frac { 1 } { q _ { H _ { 1 } } }$ 运行时间为$t ^ { \prime } < t + ( q _ { E } t _ { E } + q _ { p k } t _ { p k } + q _ { S } t _ { S } ) + 2 ( q _ { H _ { 1 } } t _ { H _ { 1 } } + q _ { H _ { 2 } } t _ { H _ { 2 } } )$ 。

# 2.3方案性能分析

如表1所示，将本文方案与近几年的椭圆曲线版本的无证书数字签名方案从签名过程，验证过程，签名长度等性能方面进行比较，其中 $S m$ 表示一次在 $G _ { 1 }$ 上的倍点运算， $P r$ 表示一次双线性对运算， $H$ 表示一次映射到点的哈希运算。$\mathrm { T s o } ^ { [ 1 6 ] }$ 方案在签名过程中用了一次 $G _ { 1 }$ 上的倍点运算，一次映射到点的哈希运算，在验证过程用了2次双线性对运算，一次 $G _ { 1 }$ 上的倍点运算和一次映射到点的哈希运算。Chen[17]方案在签名过程中用了一次 $G _ { 1 }$ 上的倍点运算，在验证过程用了二次双线性对运算，一次 $G _ { 1 }$ 上的倍点运算和一次映射到点的哈希运算。Gayathri[18]方案在签名过程中用了3次 $G _ { \mathrm { { l } } }$ 上的倍点运算，在验证过程用了2次双线性对运算，一次 $G _ { 1 }$ 上的倍点运算。Karati[19]方案在签名过程中用了2次 $G _ { 1 }$ 上的倍点运算，在验证过程用了1次双线性对运算，2次 $G _ { 1 }$ 上的倍点运算。相比以上的方案，本文的方案在签名过程中用了1次 $G _ { \mathrm { { l } } }$ 上的倍点运算，在验证过程用了1次双线性对运算，1次 $G _ { 1 }$ 上的倍点运算，结果表明本方案效率更高。在签名长度方面，比较的无证书数字签名方案中，除Gayathri和Karati签名长度为 $2 | G _ { \mathrm { i } }$ |，剩余方案都为 $\left. G _ { \mathrm { l } } \right|$ ，通过以上对比表明本方案的签名长度较短，具有较低的计算量和较高的运行效率。

表1方案性能比较  
Table1 Performance comparison of schemes   

<html><body><table><tr><td>方案</td><td>签名过程</td><td>验证过程</td><td>签名长度</td></tr><tr><td>文献[16]</td><td>1Sm+1H</td><td>2Pr+1Sm+1H</td><td>|G1|</td></tr><tr><td>文献[17]</td><td>1Sm</td><td>2Pr+1Sm+1H</td><td>|G1</td></tr><tr><td>文献[18]</td><td>3Sm</td><td>2Pr+1Sm</td><td>2|Gi|</td></tr><tr><td>文献[19]</td><td>2Sm</td><td>1Pr+2Sm</td><td>2|Gi|</td></tr><tr><td>本文方案</td><td>1Sm</td><td>1Pr+1Sm</td><td>|G1</td></tr></table></body></html>

# 2.4实验与仿真

在Windows7操作系统下，利用微软VisualStudio2012平台，结合C语言环境下椭圆曲线上的双线性对运算和PBC库实现了本文方案，然后在同一环境下(操作系统：Windows7 64位操作系统，CPU：Intel(R)CoreTMi3-4150 CPU $@$ 3.50$\mathrm { G H z }$ ，内存：金士顿HX424C15FB28GB)，运行近几年的椭圆曲线版本的无证书数字签名方案，取方案运行100次的平均耗时进行比较，实验结果如表2所示，本文方案平均总耗时为0.126s，其中签名平均耗时为0.024s，验证平均耗时为$0 . 0 3 2 \mathrm { s }$ 。本文方案平均总耗时比Tso方案减少了约 $2 7 \%$ ，比

Chen方案减少了约 $1 9 \%$ ，比Gayathri方案减少了约 $2 5 \%$ 比Karati方案减少了约 $21 \%$ 。

表2方案运行100 次平均耗时比较  
Table 2 Comparison of the average time-consuming of the 1oo results   

<html><body><table><tr><td>方案</td><td>签名平均 耗时/s</td><td>验证平均 耗时/s</td><td>方案平均 总耗时/s</td></tr><tr><td>文献[16]</td><td>0.031</td><td>0.071</td><td>0.173</td></tr><tr><td>文献[17]</td><td>0.028</td><td>0.046</td><td>0.155</td></tr><tr><td>文献[18]</td><td>0.083</td><td>0.041</td><td>0.167</td></tr><tr><td>文献[19]</td><td>0.059</td><td>0.037</td><td>0.159</td></tr><tr><td>本文方案</td><td>0.024</td><td>0.032</td><td>0.126</td></tr></table></body></html>

# 3 结束语

本文在现有的无证书密码体制的基础上，提出了一种基于双重KGC的无证书短签名方案，并且在随机预言机模型下，证明了本文方案在适应性选择消息攻击下是存在性不可伪造的。本文方案的双重KGC之间相互制约，具有分权的效果，从而降低了KGC主密钥泄露的概率，减少了因为KGC主密钥泄露和KGC 被恶意用户操控对系统产生的危害，提高了方案的安全性，并且方案的签名长度较短，若 $G _ { 1 }$ 为160比特的椭圆曲线群，则本文的签名长度只有160比特。综上知，本文方案具有运行效率较高，计算量较低，签名长度较短，实用性和安全性较强等特点，适用于宽带较低的环境中，并且双重KGC的特性更易于KGC的部署和云化KGC的实现。在实际应用中，对于身份认证而言，光依靠签名是不够的,还需要结合其他技术比如双因子认证[20,21]来加强安全性,因此进一步的研究重点是如何在应用开发中实现多种技术融合身份认证。

# 参考文献：

[1]Shamir A.Identity-based cryptosystems and signature schemes [C]/Proc of Workshop on the Theory & Application of Cryptographic Techniques.Berlin:Springer,1984:47-53.   
[2]Alriyami S S,Paterson KG. Certificateless public key cryptography [J]. Asiacrypt,2003,2894(2):452-473.   
[3]冯蕾，彭长根，彭延国．一种高效的无证书多重签名方案[J].计算机 应用研究，2012,29(2):644-645.(Feng Lei,Peng Changgen,Peng Yanguo.Efficient certificateless multi-signature scheme [J].Application Research of Computers,2012,29(2): 644-645.)   
[4]Islam S H,Obaidat M S.Design of provably secure and efficient certificateless blind signature scheme using bilinear pairing [J]. Security & Communication Networks,2016,8(18):4319-4332.   
[5]Gao Zhuo,Hu Liang，Li Hongtu．A new efficient leakage-free certificatelesssignature [C]//Proc ofInternational Forumon Mechanical,Control and Automation．Paris: Atlantis Press,2017: 978-986.   
[6]Gong Zheng,Long Yu,Hong Xuan,et al.Two certificateless aggregate signatures from bilinear maps [J].Journal of Information Science & Engineering,2007,26(6): 2093-2106.   
[7] 张永洁，张玉磊，王彩芬．聚合签名方案的安全性分析与改进[J]. 计算机应用与软件，2017，34(8):307-311.(Zhang Yongjie，Zhang Yulei, Wang Caifen. Security analysis and improvement of aggregate signature schemes [J]. Computer Applications and Software,2017, 34(8): 307-311. )   
[8]Chen Yuchi,Horng G,Liu Chaoliang.Efficient certificateless aggregate signature scheme [J]. Journal of Electronic Science and Technology, 2012,10(3): 209-214.   
[9]喻绣瑛，何大可．一种新的无证书聚合签名[J].计算机应用研究, 2014,31(8): 2485-24879.(Yu XiuYing,He Dake.New certificateless aggregate signature schemes [J]. Application Research of Computers, 2014,31 (8): 2485-24879.)   
[10]张玉磊，周冬瑞，李臣意，等．高效的无证书广义指定验证者聚合签 名方案[J].通信学报，2015，36(2):48-55.(Zhang Yulei，Zhou Dongrui,Li Chenyi，etal.Certificateless-basedeficientaggregate signature scheme with universal designated verifier [J]. Journal on Communications,2015,36(2): 48-55.)   
[11]葛丽霞，李虓，何明星，等．一个改进的无证书代理签名方案[J]. 计算机工程与应用，2017,53(8):92-94.(Ge Lixia,Li Xiao,He Mingxing,et al. Improved certificatelessproxy signature scheme [J]. Computer Engineering and Applications,2017,53(8): 92-94.)   
[12]刘晓红，张建中．对一种无证书代理签名方案的分析与改进[J].计 算机工程与应用，2014，50(22):115-117．(Liu Xiaohong，Zhang Jianzhong. Analysis and improvement of certificateless proxy signature scheme [J]. Computer Engineering and Applications,2014,50(22): 115-117. )   
[13] Boneh D,Lynn B, Shacham H. Short signatures from the weil pairing [C]//Proc of the 7th International Conference on the Theory and Application of Cryptology and Information Security. Berlin: Springer, 2001: 514-532.   
[14] Boneh D,Franklin M.Identity-based encryption from the weil pairing [J].Siam Journal on Computing,2003,32(3): 213-229.   
[15] Galbraith S, Harrison K, Soldera D.Implementing the tate pairing [C]// Proc of International Symposium on Algorithmic Number Theory. Berlin: Springer,2002: 324-337.   
[16] Tso R,Huang Xinyi,Susilo W. Strongly secure certificateless short signatures [J]. Journal of Systems & Software,2012,85(6): 1409-1417.   
[17] Chen Yuchi, Horng G,Liu Chaoliang. Strong non-repudiation based on certificateless short signatures [J].Iet Information Security,2013,7(3): 253-263.   
[18] Gayathri N B,Reddy P V.Eficient certificateless signature scheme with provable security [C]//Proc of IEEE International Conference on Advanced Computing.2016: 322-337.   
[19] Karati A,Islam S H,Karuppiah M. Provably secure and lightweight certificateless signature scheme for IIoT environments [J].IEEE Transactions on Industrial Informatics,2018,14 (8): 3701-3711.   
[20] He Debiao,Wang Ding.Robust biometrics-based authentication scheme for multiserver environment [J]. IEEE Systems Journal, 2015,9(3): 816-823.   
[21] Wang Ding，Wang Ping.Two birds with one stone:two-factor authentication with security beyond conventional bound [J].IEEE Trans on Dependable and Secure Computing,2016,15(4): 708-722.