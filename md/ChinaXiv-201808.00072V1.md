# 一个可追踪密钥的策略隐藏属性基加密方案\*

欧毓毅，刘春龙(广东工业大学 计算机学院，广州 510006)

摘要：传统的属性基加密方案中存在着访问策略所包含的属性会泄露用户的敏感信息以及恶意用户泄露私钥获取非法利益而不会被追责的问题。同时私钥长度、密文长度和解密运算量均会随属性数量增加而带来较大的通信开销和计算开销。针对以上问题提出了一种可追踪且隐藏访问结构的属性基加密方案。该方案在不影响加/解密效率的前提下提高了加密算法的安全性，并采用双因子身份认证机制实现了更安全高效的访问控制。并且引入一个安全的签名机制用于支持可追踪密钥来追踪恶意用户。该方案基于DBDH假设，在标准模型下被证明是安全的。

关键词：基于属性加密；可追踪；隐藏策略；双因子身份验证 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.05.0316

# Policy-hidden attribute-based encryption scheme with traceabe keys

Ou Yuyi, Liu Chunlong, (School of Computers Guangdong University of Technology,Guangzhou 51ooo6,China)

Abstract:Inthe traditional atribute-based encryption scheme,thereare problems that theatributes contained intheaccess policy may leak sensitive information of theuser and the malicious user leaks the private key togainillegal profits without being blamed.Atthesametime,withtheincreaseofthenumberofatributesthelengthoftheprivatekey,ciphertext,and the decryption operation willincrease anditbring greater communication overhead and computational overhead.To solve these problems,an atribute-based encryption scheme that can track keys and hide theaccesstructure is proposed.The scheme improvesthe securityof theencryptionalgorithm without affctingthe eficiencyof encryptionand decryption.The scheme adopts atwo-factorauthentication mechanismtoachieve more secure and eficientacesscontrol,and ituseasecure signature mechanism forsupporting traceable keys to track malicious users.Finaly,the theoretical analysis show thatour scheme proved to be safe under the standard model based on the DBDH hypothesis.

Key words:attribute-based encryption; traceability; hidden policies; two-factor authentication

# 0 引言

云存储以分布式计算技术为基础，在开放的网络环境下为用户提供了强大的共享和存储能力，然而传统的加密技术已经不能满足用户对于细粒度的访问控制要求[1]。因此，为了实现加密数据的细粒度访问控制，Sahai 等人[1]于 2005 年首先提出的一种新的公钥加密机制一一属性基加密（ABE)，实现了公钥密码体制一对多的加密。为了表示更灵活的访问控制策略，相关学者在之后又提出了密钥策略属性基加密[2]和密文策略属性基加密[2两类ABE加密机制。在对于密文策略的属性加密方案，加密者使用访问结构加密消息，解密者根据自身所拥有的属性预先从一个可信的授权方获取解密密钥，如果解密者本身的属性不满足嵌入在密文中的访问结构，解密者将不能解密该密文。

然而在传统的密文策略属性基加密方案中，访问策略和加密的明文往往会被一起发送给解密者，而访问结构有可能包含着与明文相关的信息，一旦密文被截获，加密者的隐私将有被泄露的风险。为了解决该问题，出现了许多隐藏访问结构的密文策略属性基加密方案。2007年，Kapadia 等人[3通过引入一个可信第三方，首次提出可匿名的密文一策略属性基加密方案，但该方案不能抵抗合谋攻击。之后，文献［4，5］分别以不同的形式实现了策略半隐藏，但文献［5]没有实现密钥追踪。文献 $[ 3 , \ 6 \sim 8 ]$ 均实现了策略完全隐藏，但是均没有实现密钥追踪，即无法对恶意泄露信息的用户进行追踪。随后，文献［9」提出一个高表达力并可对恶意用户进行白盒追踪的CP-ABE方案，可以对恶意用户进行追踪，但性能开销较大。文献「10」提出支持大规模属性空间的可追踪方案。但文献［9,10］均不对访问策略进行隐藏。文献[5」提出了一个可追踪并隐藏部分属性的密钥策略基于属性加密方案，该方案将属性集分为公共正常属性集、隐藏正常属性集、隐藏身份相关属性集三个子集，但方案只能隐藏部分属性，且密文和用户公钥长度较长。在实际应用中，过长的密文会带来较大的通信开销。文献[11]同时实现了可追踪和策略完全隐藏，但是该方案的公钥长度有所增加。

在云存储环境下，基于属性加密（ABE）的加密方案可以实现灵活的用户访问控制，其中身份认证是访问控制的第一道防线，是云存储环境安全的基础。双因子身份认证是一种强化的网络访问控制机制，它为登录过程增加了额外的安全层。因此采用文献[8]中的双因子身份验证机制,实现更安全高效的访问控制。并且由于基于属性加密的特点，用户私钥只与一组描述用户的属性相关，在实际应用中，合法用户可能会为了获取利益，恶意地将私钥泄露给非法用户而无法被追究责任。因此增加身份认证的过程以及设计能对泄露信息的用户进行追踪的加密方案具有现实意义。

本文在文献[7]的系统模型上，结合文献[11]的签名机制和文献[8]中的双因子身份验证机制提出一种具有可追踪性并隐藏访问结构的属性基加密方案。首先利用双因子身份验证机制初步判断用户的合法性；然后利用访问树将访问结构嵌入密文中，多值与门转换为访问树来表达访问结构，访问结构中的每个属性可以取多个值，增加了系统的灵活性，通过降低双线性对的运算数量提高了加密和解密的效率。方案基于判断性DBDH假设，在标准模型下被证明是安全的。

# 1 相关工作

# 1.1双线性映射

设群 $G _ { \mathrm { r } }$ ， $G _ { 2 }$ 和 $G _ { \scriptscriptstyle T }$ 均是阶为素数 $\mathsf { p }$ 的乘法循环群， $g , \ h$ 分别是是群 $G _ { \mathrm { r } }$ ， $G _ { 2 }$ 生成元，一个映射e： $G _ { 1 } \times G _ { 2 } \to G _ { T }$ 是非对称双线性映射，若映射e满足下列特征：

a）双线性。对于∀a、 $b \in Z _ { _ p }$ ，都有等式 $e ( g ^ { a } , h ^ { b } ) = e ( g , h ) ^ { a b }$ b）非退化性。 $e ( g , \ h ) \neq 1$ （204c）可计算性。对于任意的 $g , \ h$ ，能够在有效的多项式时间算法内计算 $e ( g , \ h )$

# 1.2访问结构

在本文中，用户的身份由特定的属性集合来表示，访问结构使用多值与门来表达。令 $\mathrm { U } = \{ a t t _ { 1 } , a t t _ { 2 } , . . . , a t t _ { N } \}$ 代表一个所有可能的属性取值集合，系统中属性个数为 $\mathfrak { n }$ ，ni 表示第i个属性的取值个数 ${ \cal { S } } _ { i } { = } ~ \{ a t { t _ { i , 1 } } , a t { t _ { i , 2 } } , . . . , ~ a t { t _ { i , n i } } \}$ 是一个属性可能的取值集合，其 $n i$ 为属性 $S _ { i }$ 可能取值的个数。用户的属性列表为$L = [ L _ { 1 } , L _ { 2 }$ ，.， $\boldsymbol { L } _ { n } \boldsymbol { ] }$ ，其中 $L _ { i } = a t t _ { i , t } , t \in ( 1 , 2 , . . . , n i )$ 。访问结构为$W = [ W _ { 1 } , W _ { 2 }$ ，…， $\textstyle { W _ { n } } ]$ ，其中 $\mathbb { W } _ { i } \subset S _ { i }$ 。对于 $\forall i = 1 , 2 , \ldots$ ， $n$ ，若$\boldsymbol { L } _ { i } \in \mathbb { W } _ { i }$ ，则称用户属性列表 $L$ 满足访问结构 $W$ 。

本文方案中用多值与门来表达访问结构，以增加系统的灵活性。在加密消息之前，加密者首先将访问结构转换成一棵访问树 $\tau$ ，访问树的中间节点表示 $\wedge , \vee$ 运算符，叶子节点表示属性。密文中不能显示地包含访问树，访问时由加密者隐式地嵌入到密文中，因此，解密者仅仅知道他自己是否有能力解密该密文，而不能获得任何有关其他能够解密该密文的解密者信息。图1给出了由访问结构$W = \left[ \left\{ a t t _ { 1 , 1 } , a t t _ { 1 , 2 } \right\} , \left\{ a t t _ { 2 , 2 } \right\} , \left\{ a t t _ { 3 , 1 } , a t t _ { 3 , 2 } , a t t _ { 3 , 3 } \right\} , \left\{ a t t _ { 4 , 3 } \right\} \right]$ 转换而成的访问树 $\tau$ 。有很多属性集合可以满足图1中的访问树，如属性集 $S = \{ a t t _ { 1 , 1 } , ~ a t t _ { 2 , 2 } , a t t _ { 3 , 3 } , a t t _ { 4 , 3 } \}$ 以及 $S = \{ a t t _ { 1 , 2 } , ~ a t t _ { 2 , 2 } , a t t _ { 3 , 1 } , a t t _ { 4 , 3 } \}$ 等，但是如属性集 $S = \{ a t t _ { 2 , 2 } , a t t _ { 3 , 2 } , a t t _ { 4 , 3 } \}$ 以及$S = \{ a t t _ { \mathrm { l , l } }$ ， $a t t _ { 2 , 2 } , a t t _ { 3 , 3 } \}$ 等是不满足图1中的访问树的。

![](images/fb7b6417ba72f1f82fe3347473710ae73fb2ab5ee0829e2348e04b324e87bf9e.jpg)  
图1访问树

# 1.3安全模型

对于用户口令认证协议攻击者模型一直沿用经典的Dolev-Yao 模型[18]，即攻击者可任意侦听、截获、插入、删除或阻断流经公开信道中的消息。近年来，随着边信道攻击技术的发展（如功耗攻击、电磁场攻击和时间攻击)，攻击者A可分析出智能卡内安全参数，攻击能力得到增强。本文攻击者能力如表1所示。

表1攻击者拥有的能力  

<html><body><table><tr><td>能力</td><td>含义</td></tr><tr><td>C-00</td><td>A可以离线穷举Did×Dpw中所有元素。</td></tr><tr><td>C-01 C-1</td><td>A（非评估隐私安全）可以获取用户身份标识ID。 A任意侦听、截获、插入、删除或阻断流经公开信</td></tr><tr><td></td><td>道中的消息，对于双因子协议，A可以（1）获取用 户口令；（2）提取智能卡内秘密信息，但二者不可 兼得，否则为平凡攻击。</td></tr><tr><td>C-2 C-3</td><td>A可以获取过期的会话密钥。 A可以获知服务器长期私钥，此能力仅用于评估系 统终极失效时的强健性。</td></tr></table></body></html>

本文方案可在选择属性模式下达到选择明文攻击的密文不可区分性，其所基于的安全模型[19]通过以下攻击者A与挑战者B之间的交互游戏进行描述。

初始化阶段：A提供给B两个挑战访问结构 $W _ { 0 }$ 和 $W _ { 1 }$ 。挑战者B选定安全参数入并运行初始化算法得到公钥PK和主密钥MSK。B将PK发送给A，并保留主密钥MSK。

第一阶段：攻击者A提供一个属性列表 $L$ ，属性列表L不满足访问结构 $\mathrm { w } _ { 0 }$ 和访问结构 $\mathsf { W } _ { 1 }$ 是挑战访问结构的要求。满足要求时挑战者B才运行私钥产生算法，并将私钥SK发送给攻击者A。攻击者可以进行多项式次数的询问。

挑战阶段：攻击者A提交2个长度相等的消息 $\mathrm { ~ M } _ { 0 }$ 和 $\mathbf { M } _ { 1 }$ 给挑战者B。挑战者B随机选取一个 ${ \mathbf { M _ { b } } } ^ { * , }$ ，用 $\mathbf { W _ { b } } ^ { * }$ 进行加密。挑战者运行加密算法并将密文返回给攻击者。

第二阶段：重复第一阶段和挑战阶段的过程，继续私钥询问。

猜测阶段：如果 $\scriptstyle \mathrm { T } = e \left( g , g \right) ^ { a b c }$ ，则表明攻击者A就能准确输出对 $\boldsymbol { \mathbf { b } }$ 的猜测 $\boldsymbol { \mathbf { b } } ^ { * }$ ；否则， ${ \mathrm { T } } = e \left( g , g \right) ^ { z }$ ，攻击者A只能做一个随机的猜测。如果 $\boldsymbol { \mathsf { b } } ^ { * } { = } \boldsymbol { \mathsf { b } }$ ， $\mathbf { B }$ 输出 $\beta = 1$ ；否则，输出 ${ \beta } { = } 0$ 。

攻击者获得攻击游戏胜利的优势定义为 Adv $\scriptstyle ( { \mathrm { A } } ) = \left| \operatorname* { P r } \left[ { \mathfrak { b } } ^ { * } = { \mathfrak { b } } \right] - { \frac { 1 } { 2 } } \right|$ （204

定义1在多项式时间内，若不存在以不可忽略的优势赢得上述游戏的多项式时间攻击者，则称该隐藏访问结构的密文策略基于属性加密方案是选中明文安全的。

# 1.4方案定义

方案由用户注册（Registration）、身份验证（Verification）、初始化算法（Setup）、密钥生成算法（Keygen）、加密算法（Encrypt）、解密算法（Decrypt）和追踪算法（Trace）等算法组成。方案中采用双因子身份验证机制，每个用户有其唯一ID和登录密码PW。解密时先进行用户登录，根据验证体制对用户身份进行第一道的判断，提高了攻击者破解合法用户身份信息伪装成合法授权用户的难度。通过身份验证后，用户分别将自己具有的属性私钥分量分别代入进行解密计算，验证用户私钥是否满足访问结构。若满足访问结构，则解密密文。下面分别对各种算法进行描述：

Registration注册用户，用户输入身份ID和密码PW，授权机构选取系统参数c、b以及当前注册时间t进行计算得到$\left\{ { M , N , y } \right\}$ 返回给用户。

Verification身份验证，用户登录输入身份ID和密码PW，根据验证算法，对用户身份进行第一道的判断，验证用户身份信息是否合法。

Setup 初始化算法，由授权机构完成。系统建立输入安全参数入，输出主密钥MSK和公共参数PK。并产生一个包含二元组(k，ID）的查询列表T，初始化时查询列表T为空集。

Keygen 密钥生成算法，输入主密钥MSK、属性列表L、公钥PK和用户身份ID，输出关于属性列表L的私钥SK。并将二元组(k，ID)存入查询列表T中。

Encrypt数据加密算法，由信息发送方完成。输入需要加密的明文消息M，访问策略W和公共参数PK，并输出密文CT。

Decrypt加密算法，信息接收者输入公钥 $P K$ 、隐式地嵌入访问结构W的密文CT和包含属性列表 $L$ 的用户私钥 $\mathit { S K }$ 。当解密密钥中的属性满足密文中的访问结构时，可以正确解密，得到信息M，否则输出」。

Trace 追踪算法，输入用户的公钥 $P K$ 、私钥SK 和查询列表T。先验证私钥SK是否标准定义的，若验证成功，输出与 $S K$ 对应的用户身份ID，否则输出符号」。定义符号」表示该用户私钥不用追踪。

# 2 方案构造

本文在文献[7]的系统模型上，采用双因子身份认证体制，

提出了一种可追踪且隐藏访问结构的CP-ABE加密方案。

# 2.1用户注册

Registration（ID，PW)

双因子身份验证的实施需要两个阶段来完成，即注册阶段和验证阶段。为了方便描述给出如下定义：S为远程服务器，U为用户，哈希函数 $H _ { i } = \left\{ 0 , 1 \right\} ^ { * } = \left\{ 0 , 1 \right\} ^ { l i }$ ， $i = 1 , 2 , 3$ 。权威机构S 的私钥为 $\mathrm { ~ x ~ }$ ，计算 $y = g ^ { x } m o d p$ ，用户输入身份ID和密码PW，客户端 SC 选取随机数 $\mathrm { ~ c ~ } _ { \circ }$ 计算 $H _ { 0 } ( c | | P W )$ ，将 $\{ I D , H _ { 0 } ( c \parallel P W ) \}$ 发送给权威机构S，S选取随机数b，根据用户注册时间t进行计算： $M = H _ { 0 } ( H _ { 0 } \big ( I D \big ) \oplus H _ { 0 } ( c | | P W ) )$ ，$N = H _ { 0 } ( c \parallel P W ) \oplus H _ { 0 } ( x \parallel I D \parallel t )$ ，并将 $\{ { I D } , t , { c } \}$ 存储在用户数据库中， $\left\{ M , N , y \right\}$ 保存在智能卡 SC 中。

# 2.2身份验证

Verification(ID，PW)

用户登录输入身份 $\mathrm { I D } ^ { * }$ 和密码 $\mathrm { P W } ^ { * }$ ，智能卡 SC 执行下列操作：

计算 $\boldsymbol { M } ^ { * } = H _ { 0 } ( H _ { 0 } \big ( I D ^ { * } \big ) \oplus H _ { 0 } ( \mathsf { c } \| P \boldsymbol { W } ^ { * } ) )$ )，若 $\boldsymbol { M } ^ { * } = \boldsymbol { M }$ ,SC选取随机数d,计算：

$$
Y _ { 1 } = g ^ { d } m o d ~ p
$$

$Y _ { 2 } = y ^ { d } m o d ~ p ~ , ~ K = H _ { 0 } ( x \mid \mid I D \mid \mid t ) = N \oplus H _ { 0 } ( c \mid \mid P W )$ $C I D = I D ^ { * } \oplus H _ { 0 } ( Y _ { 1 } \parallel Y _ { 2 } ) \quad \quad , \quad \quad C M K = ( b \parallel K ) \oplus H _ { 0 } ( Y _ { 1 } \parallel Y _ { 2 } )$ （20$M _ { 2 } = \{ H _ { 0 } ( Y _ { 2 } \parallel K \parallel C I D \parallel C M K ) \}$ 。用户将 $\left\{ Y _ { 2 } , C I D , C M K , M _ { 2 } \right\}$ 发送给权威机构 S。

根据用户登录请求信息，S执行以下操作：计算${ M _ { 2 } } ^ { * } = \{ { H _ { 0 } } ( Y _ { 1 } \parallel K \parallel C I D \parallel C M K ) \}$ ，验证 $\boldsymbol { M } _ { 2 } ^ { * } = \boldsymbol { M } _ { 2 }$ 是否成立，若成立，则计算 $C _ { 2 } = H _ { 1 } ( I D \parallel Y _ { 2 } \parallel C _ { 1 } \parallel K \parallel K _ { s } )$ )并将 $\mathrm { { C _ { 2 } } }$ 发送给U。

接收到来自权威机构S的消息后，SC执行计算：${ C _ { 2 } } ^ { * } = H _ { 1 } ( I D \parallel Y _ { 2 } \parallel Y _ { 1 } \parallel C _ { 1 } \parallel K \parallel K _ { u } )$ ，验证 ${ C _ { 2 } } ^ { * } = { C _ { 2 } }$ 是否成立。若成立计算： ${ C _ { 3 } } ^ { * } = H _ { 2 } ( I D \parallel Y _ { 2 } \parallel Y _ { 1 } \parallel C _ { 1 } \parallel K \parallel K _ { s } )$ ，用户将 $\mathrm { C _ { 3 } }$ 发送给权威机构S。

S 接受后执行以下操作：计算${ C _ { 3 } } ^ { * } = H _ { 2 } ( I D \parallel Y _ { 2 } \parallel Y _ { 1 } \parallel C _ { 1 } \parallel K \parallel K _ { s } )$ 验证 ${ C _ { 3 } } ^ { * } = C _ { 3 }$ 是否成立，若成立，则验证通过,则开始执行加密算法,若不通过则返回 $\perp$ 。

# 2.3加密算法

令 $\mathrm { U } = \{ a t t _ { 1 } , a t t _ { 2 } , . . . , a t t _ { N } \}$ 代表一个所有可能的属性取值集合， ${ { S } _ { i } } \mathrm { { = \ } } \left\{ { a t t _ { i , 1 } , a t t _ { i , 2 } , . . . , \ a t t _ { i , n i } } \right\}$ 是一个属性可能的取值集合，其$\mathbf { \Psi } _ { n i }$ 为属性 $S _ { i }$ 可能取值的个数。用户的属性列表为$\scriptstyle { L = [ L _ { 1 } , L _ { 2 } }$ ，， $\boldsymbol { L } _ { n } \boldsymbol { ] }$ ，其中 $L _ { i } = a t t _ { i , t } , t \in ( 1 , 2 , . . . , n i )$ 。访问结构为$W = [ W _ { 1 } , W _ { 2 }$ ，， $\boldsymbol { W _ { n } } ]$ ，其中 $\mathsf { W } _ { i } \subset S _ { i }$ 。

1） Setup(12)

初始化算法输入安全参数 $\lambda$ ，定义一个双线性映射e: $G _ { 1 } \times G _ { 2 } \to G _ { T }$ ， $\mathrm { G } _ { 1 }$ 和 $\mathrm { G } _ { 2 }$ 是阶为素数p的乘法循环群， $\mathrm { g _ { 1 } , \ g _ { 2 } }$ 分别是是群 $\mathrm { G } _ { 1 }$ 、 $\mathrm { G _ { 2 } }$ 生成元，随机选取 $\boldsymbol { y } \in \boldsymbol { Z } _ { \textit { p } } ^ { * }$ ， $a _ { i , j } \in Z _ { \textit { p } } ^ { * }$ ，并计算廳 $Y = e { \left( g _ { 1 } , g _ { 2 } \right) } ^ { y }$ 愛和樂 $A _ { i , j } = g _ { 1 } ^ { \ a i , j }$ 。

输出：公钥 $P K = \left( e , g _ { 1 } , g _ { 2 } , Y , A _ { i , j } \right)$ 和主密钥$M S K = \left( y , a _ { i , j } \right)$ ，其中 $i \in \left[ 1 , n \right] , j \in \left[ 1 , n _ { i } \right]$ 。同时生成一个包含二元组的(k，ID)的查询列表T，初始化时列表为空集 $\boldsymbol { \Phi }$ 。

2） $K e y g e n ( P K , M S K , I D , L )$

输入：系统公钥 $P K$ 、系统主私钥 $M S K$ 以及用户的属性列表 $L = [ L _ { 1 } , L _ { 2 } , L _ { 3 } , . . . , L _ { n } ]$ 。对于 $1 \leq i \leq n$ ，授权中心 $C A$ 选择（20 $\boldsymbol { r } \in \boldsymbol { Z } _ { \textit { p } } ^ { * }$ .计算 $k = r \ : , \ : \ : \ : \ : D _ { 0 } = g _ { 2 } ^ { \ : ( y - r ) / k } \ : , \ : \ : \ : D _ { i , j } = g _ { 2 } ^ { \ : r } A _ { i , j } ^ { \ : - 1 }$ （20

输出：用户私SK=(k,D,{Dj) 同时将二元组 $( k , I D )$ 存入查询列表 $\mathrm { ~ T ~ }$ 。

3） $E n c r y p t \left( P K , W , M \right)$

输入：系统公钥 $P K$ 、明文 $M$ 、相关的访问结构$W = [ W _ { 1 } , W _ { 2 }$ ，， $\textstyle { W _ { n } } ]$ 。加密者首先将使用多值与门表达的访问结构按转换规则转换成对应的访问树 $\tau$ 。加密者选择 $s \in Z _ { \textit { p } } ^ { * }$ 后按规则为访问树的每一个孩子节点i选择 $\boldsymbol { s } _ { i } \in \boldsymbol { Z } _ { \textit { p } } ^ { * }$ ，其中$s = \sum _ { i = 1 } ^ { N } s _ { i }$ 。计算 $C _ { 0 } = g _ { 1 } ^ { ~ s } , ~ C _ { 1 } = M \cdot e ( g _ { 1 } , ~ g _ { 2 } ) ^ { y s } , ~ C _ { i , j } = A _ { i , j } ^ { ~ s i }$ 输出：密文CT=(C,C,{C)

# 2.4解密算法

$$
D e c r y p t ( P K , C T , S K )
$$

输入：系统公钥 $P K$ 、隐式地嵌入访问结构 $W$ 的密文 $C T$ 和包含属性列表 $L$ 的用户私钥 $S K$ 。计算

$$
{ \cal M } = { \frac { C _ { 1 } } { \displaystyle \mathrm { e } ( C _ { 0 } ^ { \mathrm { \normalsize ~ k } } , D _ { 0 } ) \prod _ { 1 } ^ { n } \mathrm { e } ( C _ { i , j } , D _ { i , j } ) } }
$$

输出：明文 $\mathtt { M }$ 0

# 2.5追踪算法

$$
T r a c e \big ( P K , T , S K \big )
$$

追踪算法可以分为验证和查询两个阶段。根据输入的用户公钥 $P K$ 、私钥 $S K$ 和查询列表 $T$ ，输出用户 $I D$ 或符号 $\perp$ 。

1）验证阶段在验证阶段，根据如下几个公式验证私钥  
SK 是否合法，即符合标准形式下的密钥。验证方法如下：  
$k \in Z _ { \textit { p } } ^ { * } , \ D _ { 0 } , D _ { i , j } \in G _ { 2 }$ e(g, D)=e(g, g2(y-k)/k)≠1（204号 $e ( g _ { 1 } , \ D _ { i , j } ) = e ( g _ { 1 } ^ { \ \Sigma - a i j } , \ g _ { 2 } ^ { - k } )$ （20

2）查询阶段若验证私钥SK是有效的用户私钥，则根据查询列表T中查询 $\mathrm { \Delta k }$ ，并输出与 $\mathrm { ~ k ~ }$ 对应的用户 $I D$ 。若验证无效，则输出符号 $\perp$ 。

# 3 方案分析

# 3.1安全性分析

3.1.1双因子认证安全分析

针对表1中攻击者A的C-00能力，方案中采用了公钥技术，由于不能得到用户的属性私钥，即使通过离线穷举得到正确用户的ID和PW，同样不能访问加密文件。针对表1中C-01能力，即用户匿名性的基本要求：对用户ID进行Hash运算进行保护，攻击者不能获取用户的身份标志ID。针对表1中C-1能力，即用户匿名性的高层次要求：采用了两次Diffie-Hellan密钥交换技术和公钥密码技术结合方式，攻击者即使能够得到智能卡中的参数和公钥，没有私钥仍然也不能破解其他人的不可追踪性。现有研究已经从理论上证明，要实现多因子安全性，采用公钥技术是实现用户匿名性、抗离线口令猜测攻击、前向安全性的必要条件【20]。针对表1中C-3能力，即用户前向安全性问题：引入传统的Diffie-Hellman密钥交换技术，每次验证都使用不同临时值 $\mathrm { ~ g ~ } ^ { \mathrm { ~ x ~ } }$ 和 $\mathrm { ~ g ~ } ^ { \mathrm { { y } } }$ ，不能根据过期的会话密钥破解下一次的密钥。

3.1.2抵抗选择明文攻击

定理1如果一个概率多项式时间内的攻击者A没有不可忽略的优势赢得选择性明文攻击下的安全游戏，则该方案是安全的。

证明若攻击者 A 能以不可忽略的优势 $\varepsilon / 2$ 来攻破本文方案，那么存在一个挑战者B能以相同的优势 $\varepsilon / 2$ 来打破DBDH假设。具体过程描述如下：

挑战者给定挑战元组 $\left[ g , g ^ { a } , g ^ { b } , g ^ { c } , Z \right]$ ，其中 $Z$ 的取值与$e { \big ( } g , g { \big ) } ^ { a b c }$ 在 $\mathbf { G } _ { \mathrm { T } }$ 中具有相同的概率分布。

初始化阶段：A提供给B两个挑战访问结构$W _ { 0 } = [ W _ { 0 , 1 } , W _ { 0 , 2 }$ ，…， $W _ { 0 , n } ]$ ， $W _ { 1 } = \left[ W _ { 1 , 1 } , W _ { 1 , 2 } , . . . , W _ { 1 , n } \right] ,$ B 抛币得到随机值 $\mathsf { b } \in \{ 0 , 1 \}$ 。 $\textbf { B }$ 令 $Y = e { \Big ( } g ^ { a } , g ^ { b } { \Big ) } = e { \Big ( } g , g { \Big ) } ^ { a b }$ ，即有 $y = a b$ 。对于 $1 \leq i \leq n , 1 \leq j \leq n i$ ，随机选取 $a _ { i , j } \in Z _ { \textit { p } } ^ { * }$ ，当 $a t t _ { i , j } \in W _ { b , i }$ 时，算法B令 $A _ { i , j } = g _ { 1 } ^ { \ a i , j }$ ，当 $a t t _ { i , j } \notin W _ { b , i }$ 时，令 $A _ { i , j } = g _ { 1 } ^ { \ a i , j b }$ 。挑战者B把系统公钥 $P K = ( e , g _ { 1 } , g _ { 2 } , Y , A _ { i , j } )$ 发送给攻击者A，挑战者B 自己保留主密钥 $\mathbf { M K }$ 。

第一阶段：攻击者A提供一个属性列表$\begin{array} { r } { { \cal L } = [ L _ { 1 } , L _ { 2 } , L _ { 3 } } \end{array}$ ，， $\boldsymbol { L _ { n } } \boldsymbol { ] }$ ，属性列表L不满足访问结构 $\mathrm { w } _ { 0 }$ 和访问结构 $\mathsf { W } _ { 1 }$ 是挑战访问结构的要求，所以一定存在一个 ${ \mathrm { j } } \in \left[ 1 , n \right]$ ，使得 $L _ { j } \not \in W _ { b , j }$ 。挑战者B选择 $\boldsymbol { r } \in \boldsymbol { Z } _ { \textit { p } } ^ { * }$ .计算 $k = r$ ， $D _ { 0 } = { g _ { 2 } } ^ { ( y - r ) / k }$ $D _ { i , j } = { g _ { 2 } } ^ { r } { A _ { i , j } } ^ { - 1 }$ ，挑战者 B 将私钥 $S K = \left( k , D _ { 0 } , D _ { i , j \{ i \in [ 1 , n ] , j \in [ 1 , n i ] \} } \right)$ 发送给攻击者 $\mathbf { A }$ 。

第二阶段：攻击者 $\mathrm { ~ A ~ }$ 提交2个长度相等的消息 $\mathrm { ~ M } _ { 0 }$ 和 $\mathbf { M } _ { 1 }$ 给挑战者 B，挑战者 B 随机 $\boldsymbol { s } _ { i } \in \boldsymbol { Z } _ { \textit { p } } ^ { * }$ ，其中 $s = \sum _ { i = 1 } ^ { N } s _ { i }$ ，计算 $C _ { 0 } = { g _ { 1 } } ^ { s }$ ，如果 $i = j$ ，则 $C _ { 1 } = { M _ { b } } ^ { * } \cdot e ( \ g _ { 1 } , \ g _ { 2 } ) ^ { y s }$ ， $C _ { i , j } = { A _ { i , j } } ^ { s i }$ ；如果 $i \neq j$ ，则 $C _ { 1 } = { M _ { b } } ^ { * } \cdot e ( g _ { 1 } , ~ g _ { 2 } ) ^ { z }$ ， $C _ { i , j } = { A _ { i , j } } ^ { s i }$ 。

第三阶段：重复第一阶段和第二阶段的过程，继续私钥询

问。

猜测阶段：如果 $\scriptstyle \mathrm { T } = e \left( g , g \right) ^ { a b c }$ ，则表明攻击者A就能准确输出对b 的猜测 $\boldsymbol { \mathbf { b } } ^ { * }$ ；否则， $\scriptstyle \mathrm { T } = e \left( g , g \right) ^ { z }$ ，攻击者A只能做一个随机的猜测。如果 $ { \mathbf { b } } ^ { * } =  { \mathbf { b } }$ ， $\mathbf { B }$ 输出 $\beta = 1$ ；否则，输出 ${ \beta } { = } 0$ 。

因此，挑战者B能够以 $\varepsilon / 2$ 的优势解决 $D B D H$ 问题，即在DBDH假设下，证明提出的方案是安全的。

# 3.1.3抵抗用户窜谋攻击

本方案采用双因子身份验证机制，每个用户有其唯一 $I D$ 和登录密码PW。用户进行数据加密上传和获取解密文件前先进行用户登录，根据验证体制对用户身份进行第一道的判断，提高了攻击者破解合法用户身份信息伪装成合法授权用户的难度。通过身份验证后，用户分别将自己具有的属性私钥分量分别代入进行解密计算，验证用户私钥是否满足访问结构。该方案中用户只能知道自己是否具有访问秘密文件的条件，但不能获知自己能够满足访问结构的具体属性表达式，这就有效防止了多个非法用户或腐化用户窜谋，结合属性私钥获取解密密钥，获取共享文件，或者低授权用户进行越权盗取高级加密文件的风险。

# 3.1.4白盒可追踪性

数据拥有者的数据在上传至云服务器之前首先进行身份认证，认证成功后使用访问策略W加密，只有授权的用户才能在解密服务器的帮助下解密出明文。

用户解密之前也需要进行身份认证，并且用户私钥生成时中加入因子k，同时，将二元组 $( k , I D )$ 存入查询列表T。为了能解密得到密文，攻击者必须具备系统公钥 $P K$ 、密文CT和私钥SK，并且属性集合必须满足访问控制策略。数据提供者可以根据用户的私钥SK、系统公钥 $P K$ ，首先验证私钥SK是否标准定义的，若验证成功，根据因子k查询列表T后输出与SK 对应的用户身份ID，否则输出符号」。

# 3.2效率分析

属性基加密机制的效率问题主要考虑通信开销和计算开销。一方面密文长度决定了通信开销，降低密文长度可以减少通信开销；另一方面 ABE一对多的通信方式，使得系统中解密相对加密是一个高频行为，且双线性对的计算效率要低于其他运算，减少解密过程中双线性对的计算次数，可以有效降低计算开销。因此本文现将本文方案与所列文献中的方案分别从加/解密时间开销、功能特征和密文长度、私钥长度等相关参数方面进行比较。其中系统中属性个数为 $\mathfrak { n }$ ，ni表示第i个属性的取值个数， $N = \sum _ { \mathrm { i = 1 } } ^ { n } n i$ 表示属性空间中所有属性的取值总个数,$\left| G \right| , \left| G _ { _ T } \right|$ 和 $\left| { Z _ { P } } ^ { * } \right|$ 表示 $G \mathrm { ~ , ~ } G _ { \scriptscriptstyle T }$ 和 $Z _ { \mathrm { p } } ^ { \mathrm { ^ * } }$ 中元素的单位长度， $G$ 、 $G _ { \scriptscriptstyle T }$ （204号分别为群 $G$ 、 $G _ { \scriptscriptstyle T }$ 上计算所用的时间， $C _ { \varepsilon }$ 表示双线性对所需要的时间。具体比较结果如表 $2 { \sim } 4$ 所示。

表2方案功能特征比较  

<html><body><table><tr><td>方案</td><td>可追踪性</td><td>策略隐藏</td><td>双因子认证</td></tr><tr><td>文献[4]</td><td>无</td><td>部分隐藏</td><td>无</td></tr><tr><td>文献[5]</td><td>可追踪</td><td>部分隐藏</td><td>无</td></tr><tr><td>文献[6]</td><td>无</td><td>完全隐藏</td><td>无</td></tr><tr><td>文献[7]</td><td>无</td><td>完全隐藏</td><td>无</td></tr><tr><td>文献[8]</td><td>无</td><td>完全隐藏</td><td>有</td></tr><tr><td>文献[9]</td><td>可追踪</td><td>无</td><td>无</td></tr><tr><td>文献[10]</td><td>可追踪</td><td>无</td><td>无</td></tr><tr><td>文献[11]</td><td>可追踪</td><td>完全隐藏</td><td>无</td></tr><tr><td>本文方案</td><td>可追踪</td><td>完全隐藏</td><td>有</td></tr></table></body></html>

表3方案的相关参数大小  

<html><body><table><tr><td>方案</td><td>PK</td><td>MK</td><td>SK</td><td>CT</td></tr><tr><td></td><td>文献[11] (N+3)|G|+|Gr](N+2)|Zp*(n+1)]G|(2n+1)|G|+|Gr|</td><td></td><td></td><td></td></tr><tr><td></td><td>文献[7](N+1)|G|+|Gr|N|Zp*|+|Gr|(2n+1)|G|(2n+1)|G| +|Gr|</td><td></td><td></td><td></td></tr><tr><td></td><td>本文方案(N+1)|G| +|Gr|N|Zp*|+|Gr|(n+1)|G|(n+1)|G| +|Gr|</td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td colspan="3">表4时间开销</td></tr><tr><td>方案</td><td>加密时间</td><td>解密时间</td></tr><tr><td>文献[11]</td><td>(n+1) G + GT</td><td>(2n+1) C& +3 GT</td></tr><tr><td>文献[7]</td><td>(2n+1) G + GT</td><td>(2n+1) C& +3 GT</td></tr><tr><td>本文方案</td><td>(n+1) G + GT</td><td>(n+1) Cg +3 GT</td></tr></table></body></html>

从表2可以看出，文献 $[ 4 \sim 8 ]$ 只实现了策略隐藏，文献[9,10]只实现了密钥可追踪。文献[5]虽然同时实现了可追踪和策略隐藏，但只能对策略部分隐藏。文献[11]也同时实现了可追踪和策略完全隐藏，但是该方案的公钥长度有所增加，本文方案可以同时实现可追踪和策略隐藏，并使用双因子身份验证机制，可以有效的抵抗用户合谋攻击。

如表3所示，本文方案虽然与文献[7]的系统公钥长度和主密钥长度一样，但是比文献[11]的短，其用户私钥长度与文献[7]一样,比文献[11]的短，加密所得到的密文长度比文献[11，7]的都短，在数据访问人数比数据加密者多的情况下，私钥长度关系着授权中心的效率，而密文长度则关系着通信代价。

根据表 4所示，本方案的加密时间文献[11]一样，但是解密时间均比文献[11]的更短，相比文献[7]来说加密时间和解密时间均更短，因为双线性运算代价减少了近一半，所以方案的效率得以提高。

# 4 结束语

本文提出了一个可追踪密钥且隐藏访问结构的密文策略属性基加密方案。在不影响加/解密效率的前提下，方案中结合双因子身份认证机制实现对用户身份的匿名认证，解决了用户敏感信息易被泄露、文件易被窃取的风险，并且证明了在DBDH假设下该方案能够抵抗选择明文攻击，实现了密文的不可区分性。在保证数据安全性的同时，通过降低双线性对运算的数目，大大降低了通信开销和计算开销。但本方案的不足之处是只能进行白盒追踪，因此下一步工作是实现能够进行黑盒追踪的加密方案。

# 参考文献：

[1]Sahai A，WatersB.Fuzzy identity-based encryption [C]// Proc of International Conference on Theory and Applications of Cryptographic Techniques.[S.1.]: Springer-Verlag,2005: 457-473.   
[2]Goyal V,Pandey O,Sahai A,et al.Attribute-based encryption for fine-grained accesscontrol of encrypted data [C]// Proc of ACM Conference on Computer and Communications Security.[S.1.]:ACM Press,2006: 89-98.   
[3]Kapadia A, Tsang PP, Smith S W.Atribute-based publishing with hidden credentials and hidden policies [C]// Proc of Network and Distributed System Security Symposium.San Diego,California:[s.n.]，2007: 179-192.   
[4] 应作斌，马建峰，崔江涛．支持动态策略更新的半策略隐藏属性加密方 案[J].通信学报,2015,36 (12):178-189.(Ying Zuobin,MaJianfeng, Cui Jiangtao. Partially policy hidden CP-ABE supporting dynamic policy updating [J]. Journal on Communications,2015,36 (12):178-189.)   
[5]Yu Shucheng,Ren Kui,Lou Wenjing,et al.Defending against key abuse attacks in KP-ABE enabled broadcast systems [M]// Security and Privacy in Communication Networks.20o9: 311-329.   
[6]刘雪艳，郑等凤．基于素数群完全隐藏访问结构的CP-ABE 方案[J]. 计算机工程，2016,42(10):140-145.(Liu Xueyan，Zheng Dengfeng. CP-ABE scheme based on prime group with fully hidden accesstructure [J].Computer Engineering,2016,42(10): 140-145.)   
[7] 汪海萍，赵晶晶．隐藏访问结构的密文策略的属性基加密方案[J].计 算机科学，2016，43(2):175-178.(Wang Haiping，Zhao Jingjing. Ciphertext-policy atribute-based encryption with anonymousaccess structure [J]. Computer Science,2016,43 (2): 175-178.)   
[8] 沈学利，吕莹楠．一种隐藏访问结构的文件层次属性加密研究[J/OL]. 计算机应用研究，2019，36(1):1-2[2018-05-17].http://kns.cnki. net/kcms/detail/51.1196.TP.20180208.1714.084. html.(Shen Xueli,Lu Yingnan.Research on file hierarchy atribute encryption of hidden access structure [J/OL]. Application Research of Computers,2019,36 (1):1-2 [2018-05-17].http://kns.cnki. net/kcms/detail/51.1196.TP. 20180208. 1714. 084. html.)   
[9]Yadav U C. Ciphertext-policy atribute-based encryption with hiding access structure [C]// Advance Computing Conference.[S.1.] : IEEE Press, 2015: 6-10.   
[10] Ning Jianting，Cao Zhenfu，Dong Xiaolei,et al. Large universe ciphertext-policy attribute-based encryption with white-box traceability [J]. 2014, 8713: 55-72.   
[11]王梅，孙磊．一个安全可追踪的策略隐藏属性基加密方案[J]．计算机 应用与软件，2017 (2):267-271.(Wang Mei,Sun Lei.A secure and traceable attribute-based encryption scheme with hiding access structure [J]. Computer Applications and Software,2017(2): 267-271)   
[12] Ning Jianting，Cao Zhenfu,Dong Xiaolei,et al.White-box traceable ciphertext-olicy attribute-based encryption supporting flexible attributes [J].IEEE Trans on Information Forensics& Security,2015,10(6): 1274-1288.   
[13] Zhong Hong, Zhu Wenlong,Xu Yan,et al. Multi-authority atribute-based encryption access control scheme with policy hidden for cloud storage [J]. Soft Computing,2016,22(1):1-9.   
[14] Odelu V,Das A K，Rao Y S,et al. Pairing-based CP-ABE with constant-size ciphertexts and secret keys for cloud environment [J]. Computer Standards& Interfaces,2017,54 (P1): 3-9.   
[15] Qin Baodong，Deng Robert H,Liu Shengli，et al.Atribute-based encryption with efficient verifiable outsourced decryption [J]. IEEE Trans on Information Forensics and Security,2015,10(7):1384-1393.   
[16] Liu Zhen,Cao Zhenfu, Wong D S.White-box traceable ciphertext-policy atribute-based encryption supporting any monotone access structures [J]. IEEE Trans on Information Forensics & Security,2013,8(1): 76-88.   
[17]陈露，王赜．基于ATP-ABE的访问控制方案[J/OL].计算机工程与应 用，1-9[2018-05-17].http://kns.cnki．net/kcms/detail/11.2127．TP. 20180409.1448.O16.html.(Chen Lu，Wang Wei．An access control schemebasedon ATP-ABE [J/OL]. Computer Engineeringand Applications,1-9 [2018-05-17]. http://kns.cnki.net/kcms/detail/11.2127. TP. 20180409.1448.016. html.)   
[18]Dolev D,Yao A. On the security of public key protocols [J]. IEEE Trans on Information Theory,1983,29 (2):198-208.   
[19] Nishide T, Yoneyama K, Ohta K.Atribute-based encryption with partially hidden encryptor-specified access structures [M]// Applied cryptography and network security.Berlin: Springer,20o8:111-129.   
[20]汪定，李文婷，王平．对三个多服务器环境下匿名身份认证协议的安全 性分析[J/OL].软件学报,1-16 [2018-06-25].https://oi.org/10.13328/j. cnki. jos.O05361.(Wang Ding,Li Wenting,Wang Ping.Crytanalysis of three anonymous authentication schemes for multi-server environment [J/OL]. Journal of Software,1-16 [2018-06-25]. htps://doi.org/10.1338/j. cnki. jos. 005361. )