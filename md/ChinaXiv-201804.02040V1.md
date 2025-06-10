# 一种新型基于格上LWE问题密钥交换协议的设计\*

李子臣1²，谢婷1,，张筱薇，蔡居良

(1．西安电子科技大学 通信工程学院，西安 710071;2.北京印刷学院，北京 102600;3．北京电子科技学院，北京100070)

摘要：基于格上困难问题设计高效、安全的后量子密钥交换协议具有非常重要的理论意义和实用价值。提出了一种新型高效实用的基于格上错误学习问题被动安全密钥交换协议。该协议采用加密机制的构造方式并使用了密文压缩技术，与2016年Bos 等人基于错误学习问题并使用Peikert 错误调和机制设计的密钥交换协议Frodo相比，通信量只增加了 $1 . 0 9 \%$ ，但方案复杂度有效降低，计算更加简洁高效，且协议在被动攻击下可证明安全，可有效抵御量子攻击。该协议与现有的基于错误学习问题设计的密钥交换协议相比，具有很强的竞争力。

关键词：格；密钥交换协议；错误学习问题；被动安全 中图分类号：TP301.4 doi:10.3969/j.issn.1001-3695.2017.11.0755

# New key exchange protocol of based on LWE problem

Li Zichen1, ², Xie Ting 1,³, Zhang Xiaowei³, Cai Juliang (1.CommunicationEngineringInstitute,Xidian University,Xian70o1China;2.BeijingInstituteofGraphicCommunication, Beijing 10260o China;3.Beijing Electronic Science and Technology Institute,Beijing 10o070 China)

Abstract:The design of eficient and secure latice-based post quantum key exchange protocols hascertain practical and theoretical significance.In thispaper,ascheme was proposed,which used straight-forward transformation LWEencryption mechanismandaciphertext compresion technology.Thisisapassivelysecureand practicalkeyexchange protocol.Frodo was a key exchange scheme basedonLWE problem proposed byBos et al,which usedthe error reconciliation mechanismproposed byPeikert.ThemainadvantageoftheschemeoverFrodoissimplicityComparedwithFrodo,thecommunicationstrafficmerely increased by only $1 . 0 9 \%$ ,the complexity of the scheme is reduced effectively.The scheme is proved to be passive security,Also, whichcanresist quantum computer atacks.Compared with existing key exchange protocolbased on learning with eor,this protocol is very competitive.

KeyWords:lattice;key exchange protocol; LWE; passively secure

# 0 引言

密钥交换协议[1,2]在安全通信领域中具有重要的基础性作用，它使得两方或多方通过在公开信道上交换信息达成一个共享的会话密钥，被认为是公钥密码学中的一个重要应用。1976年，Diffie-Hellman 提出了第一个密钥交换协议[3]，自DH密钥交换协议提出以来，由于它的构造结构简单且实用，因此之后很多密码学者以此结构为基础来构造高效的密钥交换协议。随着量子计算技术的飞速发展，基于经典的数论困难问题构造的传统公钥密码算法的安全性面临现实威胁。美国国家标准和技术研究院(NIST)于2015 年颁布的后量子密码学报告[4]中指出：由于量子计算技术的迅速发展，现有的公钥密码标准将不再安全。美国国家标准和技术研究院（NIST）、美国国家安全局（NSA）、以及由欧盟赞助的PQCRYPTO项目目前已经在全球范围内展开了后量子密码算法标准的有关征集工作。量子计算机环境下可证明安全的公钥密码算法的研究已成为当前密码学界的热点。其中，后量子密钥交换协议的需求最为迫切，已被美国国家标准和技术研究院（NIST）列为一项重大科研项目。因此设计高效安全的后量子密钥交换协议具有重要的理论意义和应用价值。

基于格理论的密码系统具有较高的渐进效率、可并行计算、可抵御量子攻击等优点，因此格理论被公认为后量子密码算法标准最有力的竞争者。近年来，基于格理论在构造加密[5-7]、数字签名[8.9]、密钥交换[10\~15]具有可证明安全性方案以及基于格的零知识研究[16等方面取得了大量研究成果。2005年Regev等人提出带误差的学习问题（learningwith errors，LWE）[7]，并指出可使用量子规约技术将LWE问题的平均情形困难性和格上的困难问题的最坏情形困难性联系起来。2010 年，LyubashevskyPeikert 和 Regev 提出了基于环带误差的学习问题[18]（ringlearningwitherrors，RLWE)，显著改进了密钥长度的大小并有效提升了执行的效率。2015年,Langlois和Stele 研究了模LWE[19],它是LWE与RLWE的推广。基于LWE、RLWE、模LWE 在密钥交换协议的构造方面已经得到了广泛应用。

近几年来在基于格困难问题构造被动安全的密钥交换协议方面，出现了许多优秀的成果。起初，2012年丁等人首次提出一种基于LWE 变体 SLWE 的密钥交换协议[I0]，并将该方案扩展到RLWE上。2014年，Peikert首先提出了一种高效的选择明文安全的密钥封装机制及一种有效但计算复杂的错误调和机制构造认证密钥交换协议[II]。在2015年，Bos 等人在S&P会议上提出一种Diffie-Hellman 类密钥交换协议[l2]，其安全性基于RLWE 问题，进一步将Peikert的密钥封装机制集成到了TSL中有效证明了协议的可行性。之后的2016年USENIX安全会议上，Alkim，Ducas，Popplemann和Schwabe 提出了一个基于RLWE的后量子密钥交换方案NewHope[13]，之后谷歌公司进行了后量子TLS 实验，在Chrome 浏览器中部署了NewHope 方案并进行了运行效率及安全性能测试。不久，Alkim等人在NewHope方案的基础上又提出了一种使用加密机制的被动安全密钥交换协议 NewHope-Simple[14]。该协议在一方通信量上仅增加了 $6 . 2 5 \%$ ，在实现分享密钥准确度和有效性不变的情况下，并且未使用计算复杂的调和技术达到了几乎与NewHope 相同的安全性能。虽然RLWE问题环的代数结构使得密钥交换方案具有更为实用的密钥尺寸，可构造更加高效的通信协议，但是RLWE问题附加环的代数结构可能存在安全性能上的潜在威胁。2016年CCS大会上，Bos 等人使用Peikert 错误调和机制的多比特变形提出了一个基于LWE问题新型且实用的被动安全密钥交换协议Frodo[15]，与之前基于RLWE 问题构造的密钥交换协议相比，虽然计算时间和通信量较大，但安全性能更可靠。

本文主要在Bos 等人提出的基于LWE问题构造的Frodo协议的基础上，由Alkim等人设计的基于RLWE问题使用加密体制的方式构造的NewHope-Simple方案得到启示，提出了一种新型高效的基于LWE问题被动安全的密钥交换协议，使用了加密机制而未使用计算复杂的错误调和机制，计算简洁高效。该方案仅以一方通信量从11296字节增至11520字节，大小仅增加 $1 . 0 9 \%$ 的微小代价，达到了有效抵御量子攻击同等的安全性能，并使用了NIST杂凑函数标准 SHA-3，进一步提高了协议的安全度。与现有的基于LWE问题设计的密钥交换协议相比，具有较强的竞争力。

# 1 基础知识

# 1.1 带误差学习问题

定义1 判定性 LWE 问题。已知参数 $n \geq 1$ ，模数 $q \geq 2$ ，输入数据为矩阵 $\mathbf { A }$ 和向量 $\nu$ ，已知 $\mathbf { \sigma } _ { \nu = \mathbf { A } s + e }$ ，其中 $\mathbf { A } \in \mathbb { Z } _ { q } ^ { m \times n }$ ，$s \in \mathbb { Z } _ { q } ^ { n }$ 且满足 $\mathbf { A } \xleftarrow { \texttt { s } } u ( \mathbb { Z } _ { q } ^ { m \times n } )$ ， $s  s  u ( \mathbb { Z } _ { q } ^ { n } )$ ，即矩阵 $\mathbf { A }$ 、向量 $s$ 分别在 $\mathbb { Z } _ { q } ^ { m \times n }$ 和 $\mathbb { Z } _ { q } ^ { n }$ 中按照均匀分布随机选择，错误向量 $\mathbf { \Psi } _ { e }$ 在$\mathbb { Z } _ { q } ^ { m }$ 上服从某种公开的概率分布 $\chi ^ { m }$ ，判定性LWE 问题是指给定 $\left( A , \nu \right)$ ，区分 $\left( A , \nu \right)$ 为LWE 分布还是随机选择于均匀分布$( \mathbb { Z } _ { q } ^ { m \times n } , \mathbb { Z } _ { q } ^ { m } )$ 。

定义 $\pmb { 2 } ^ { [ 1 5 ] }$ $\left( m , { \overline { { n } } } \right)$ -矩阵判定性LWE 问题。已知参数 $n \geq 1$ ，模数 $q \geq 2$ ，输入数据为矩阵 $\mathbf { A }$ 和向量 $\boldsymbol { V }$ ，已知 $V = \mathbf { A } S + E$ ，其中 $\mathbf { A } \in \mathbb { Z } _ { q } ^ { m \times n }$ ，且满足 $\mathbf { A } \xleftarrow { \texttt { s } } u ( \mathbb { Z } _ { q } ^ { m \times n } )$ ，即 $\mathbf { A }$ 分别在 $\mathbb { Z } _ { q } ^ { m \times n }$ 中按照均匀分布随机选择，向量 $s$ 、错误向量 $E$ 分别在 $\mathbb { Z } _ { q } ^ { n }$ 和 $\mathbb { Z } _ { q } ^ { m }$ 上服从某种公开的的概率分布 $\chi ^ { n } \cdot \chi ^ { m } \cdot ( m , \overline { { { n } } } )$ -矩阵判定性LWE 问题是指给定 $\left( \mathbf { A } , V \right)$ ,区分 $\left( \mathbf { A } , V \right)$ 为 LWE 分布还是随机选择于均匀分布 $( \mathbb { Z } _ { q } ^ { m \times n } , \mathbb { Z } _ { q } ^ { m } )$ 。

# 1.2错误调和机制与一般化错误调和机制

# 1.2.1 错误调和机制（errorreconciliation mechanism）

$\lfloor x \rceil = \left\lfloor x + { \frac { 1 } { 2 } } \right\rfloor \in \mathbb { Z }$ 为近似取整函数，定义 $\lfloor x \rceil _ { { _ p } } { : = } \lfloor x \cdot { \frac { p } { q } } \rceil$ $I _ { 0 } : = \{ 0 , 1 , . . . , \lfloor \frac { q } { 4 } \rceil - 1 \} ~ , ~ I _ { 1 } : = \{ - \lfloor \frac { q } { 4 } \rfloor , . . . , - 1 \}$ ；定义交叉近似函数$\left. \cdot \right. _ { 2 } : \mathbb { Z } _ { q } \to \mathbb { Z } _ { 2 }$ ，具体地， $\left. \nu \right. _ { 2 } : = \left\lfloor \frac { 4 } { q } \cdot \nu \right\rfloor { \bmod { 2 } }$ mod2；定义模近似函数$\begin{array} { r } { \lfloor \nu \rceil _ { { \scriptscriptstyle 2 } } = \left\{ \begin{array} { c c } { 0 , } & { \breve { \equiv } \lfloor \nu \in I _ { \mathrm { 0 } } \bigcup I _ { 1 } ; } \\ { 1 , } & { \breve { \equiv } \mathscr { H } \mathscr { H } . } \end{array} \right. } \end{array}$

引理 $1 ^ { [ 1 1 ] }$ 对于偶数 $\mathsf { q }$ ，如果 $\nu \in \mathbb { Z } _ { q }$ 是均匀随机的，那么给定 $\left. \nu \right. _ { 2 }$ 时， $\left\lfloor \nu \right\rceil _ { 2 }$ 在 $\mathbb { Z } _ { q }$ 上也是均匀随机的。令 $E { = } \Big [ { - } { \frac { q } { 4 } } , { \% } \Big ]$ ，则调和函数 $r e c : \mathbb { Z } _ { q } \times \mathbb { Z } _ { 2 } \to \mathbb { Z } _ { 2 }$ 定义为

$$
r e c ( w , b ) = \left\{ \begin{array} { l r } { 0 , } & { w \in I _ { 1 } + E ( \mathrm { m o d q } ) ; } \\ { 1 , } & { \mathrel { \phantom { = } } \mathbb { H } \backslash \{ \downarrow . }  \end{array} \right.
$$

引理 $\pmb { 2 } ^ { [ 1 1 ] }$ 对于偶数q,如果 $w = \nu + e \mod q$ ，且$w \in \mathbb { Z } _ { q } , e \in E$ ,那么 $r e c ( w , \left. \nu \right. _ { 2 } ) = \bigl \lfloor \nu \bigr \rceil _ { 2 }$ 。

当q为奇数时，为了避免派生未流的不均匀性，引入了随机化函数。令 $d b l : \mathbb { Z } _ { q } \to \mathbb { Z } _ { 2 q } , d b l ( x ) = 2 x - \overline { { e } }$ ,其中 $\overline { { e } }$ 为随机项,$\overline { { e } }$ 为0的概率为 $\% ^ { \mathrm { ~ e ~ } }$ 为1和-1 的概率为 $\%$ ，从而保证 $\overline { { e } }$ 在模2运算后是均匀的。

引理 $\pmb { 3 } ^ { [ 1 1 ] }$ 对于奇数q,如果 $\nu \in \mathbb { Z } _ { q }$ 是均匀随机的，令$\overline { { \nu } } = d b l ( \nu ) \in \mathbb { Z } _ { 2 q }$ ，那么在给定 $\left. d b l ( \nu ) \right. _ { 2 }$ 的情况下, $\left\lfloor \overline { { \nu } } \right\rceil _ { 2 }$ 在 $\mathbb { Z } _ { 2 q }$ 上是均匀随机的。令 $E = [ - \frac { q } { 4 } , \% )$ ，则调和函数n $c : \mathbb { Z } _ { 2 q } \times \mathbb { Z } _ { 2 } \to \mathbb { Z } _ { 2 }$ 定义为

$$
r e c ( w , b ) = \left\{ \begin{array} { l r } { 0 , } & { w \in I _ { 1 } + E ( \mathrm { m o d q } ) ; } \\ { 1 , } & { \mathrel { \phantom { = } } \sharp _ { \setminus } / \{ \updownarrow \} . } \end{array} \right.
$$

引理 ${ \bf 4 } ^ { [ 1 1 ] }$ 对于奇数q,令 $\nu = w + e \in \mathbb { Z } _ { q }$ ， ${ w , e } \in \mathbb { Z } _ { q }$ ，且$2 e + { \overline { { e } } } \in E { \mathrm { ~ m o d } } q$ ，那么 $r e c ( 2 w , \left. \overline { { \nu } } \right. ) = \left\lfloor \overline { { \nu } } \right\rceil _ { 2 }$ 。

# 1.2.2一般化错误调和机制（generalized errorreconciliation mechanism)

Peikert错误调和机制双方仅能通过调和函数 $r e c$ 提取1比特密钥，一般化错误调和机制是Peikert错误调和机制的多比特变形，可保证双方可以通过调和函数 $r e c$ 提取 $2 ^ { ^ B }$ 比特密钥。

已知模数 $q = 2 ^ { n }$ ，其中 $n$ 为正整数， $B < ( \log _ { 2 } { \tt q } ) - 1$ ，令$\overline { { B } } = ( \log _ { 2 } \mathfrak { q } ) - \mathbf { B }$ ，对于任意的 $\nu \in Z _ { q }$ ，定义近似函数$\left\lfloor \cdot \right\rceil _ { 2 ^ { B } } : \nu \to \left\lfloor 2 ^ { - { \bar { B } } } \cdot \nu \right\rceil { \bmod { 2 ^ { B } } }$ ，定义交叉近似函数$\left. \cdot \right. _ { 2 ^ { B } } : \nu \to \left\lfloor 2 ^ { - { \overline { { B } } } + 1 } \cdot \nu \right\rfloor { \bmod { 2 } } \circ$

引理 $\pmb { 5 } ^ { [ 1 5 ] }$ 如果 $\nu \in Z _ { q }$ 是均匀随机的，那么给定 $\left. \nu \right. _ { 2 ^ { B } }$ 时，$\big \lfloor \nu \big \rceil _ { 2 ^ { \frac { B } { B } } }$ 在 $Z _ { \boldsymbol { q } }$ 上也是均匀随机的。

引理 ${ \bf 6 } ^ { [ 1 5 ] }$ 如果 $\big | \nu - w \big | < 2 ^ { \bar { B } - 2 }$ ，那么 $r e c ( w , \left. \nu \right. _ { 2 ^ { B } } ) = \bigsqcup _ { 2 ^ { B } }$ 。

# 1.3构造被动安全的LWE密钥交换协议的两种方式

基于LWE问题构造被动安全密钥交换协议过程中对于针对LWE问题其错误向量的处理是需要解决的关键问题，而错误向量的存在是问题困难性的关键，其存在使得通信双方得到近似相等的值。因此，对错误的处理是基于LWE问题设计密钥交换协议关键的技术难点。对于错误的处理有两种方式，一种是基于调和机制，一种是基于加密机制。

# 1.3.1基于调和机制构造密钥交换协议

Peikert在2014年后量子密码会议上提出了一种高效的基于错误调和机制构造的被动安全密钥封装体制，此技术成为了基于格理论构造认证密钥交换协议的重要基础，后续在Peikert错误调和机制的基础上构造了许多高效实用的密钥交换协议。Bos 等人基于RLWE问题，使用错误调和机制构造了一个密钥交换协议，图1为BCNS15[12]方案的具体描述。

表1基于调和机制构造的密钥交换协议  

<html><body><table><tr><td colspan="2">KEM.SetupO:</td></tr><tr><td>a←R</td><td></td></tr><tr><td>Alice</td><td>Bob</td></tr><tr><td>KEM.Gen(a):</td><td>KEM.Encaps(a.b):</td></tr><tr><td>s,ex</td><td>s,e,e"x</td></tr><tr><td>b←as+e</td><td>b μ←as'+e'</td></tr><tr><td></td><td>v←bs'+e"</td></tr><tr><td>KEM.Decaps ((s,(μ,c)):</td><td>v ←dbl(v) ∈Z2q</td></tr><tr><td>v←2μs</td><td>c←(v>2</td></tr><tr><td>μ←Rec(v',r)</td><td>μ←Lv]</td></tr></table></body></html>

对于 Alice，经计算得到的环元素值为 $\nu ^ { \prime } = \mu s = a s s ^ { \prime } + e ^ { \prime } s$ ，对于 Bob，计算得到的环元素值为v=bs'+e"=ass'+es'+e"，由引理3可知，已知 $\left. \overline { { \nu } } \right. _ { 2 }$ 的情况下，并不会泄露 $\left\lfloor \overline { { \nu } } \right\rceil _ { 2 }$ 的任何信息，并且在 $\nu = w + e$ 时，得到 $r e c ( 2 w , \left. \overline { { \nu } } \right. ) = \left\lfloor \overline { { \nu } } \right\rceil _ { 2 }$ 。因此，对于Alice，只需计算 $\mu = r e c ( 2 \mu s , r )$ ，而 Bob 计算 $\mu = \left\lfloor \overline { { \nu } } \right\rceil _ { 2 }$ ，因此Alice 与 Bob 经过密钥交换得到共享密钥 $\mu$ 。

# 1.3.2基于加密机制构造密钥交换协议

使用错误调和机制构造基于格的密钥交换协议可以有效减少通信量，但是方案的计算复杂。之后的NewHope-Simple[14]方案和基于模LWE[19]问题的Kyber.KE[20]方案均是使用加密机制构造的密钥交换协议。

已知 Alice 和Bob 有一个共同的系统元素 $a \in R _ { q }$ ，Alice从错误分布中取样 $\scriptstyle ( s , e )$ ，计算公钥 $b = a s + e$ 给 Bob，Bob 从 $\chi$ 中取样 $\left( s ^ { \prime } , \mathbf { e } ^ { \prime } \right)$ ，计算 $\mu = a s ^ { \prime } + e ^ { \prime }$ 、 $\nu = \big ( a s + e \big ) s ^ { \prime } = a s s ^ { \prime } + e s ^ { \prime }$ ，之后Alice 根据收到消息计算 $\nu ^ { \prime } = \mu s = \big ( a s ^ { \prime } + e ^ { \prime } \big ) s = a s s ^ { \prime } + e ^ { \prime } s$ ，Bob 增加一个噪声项 $e ^ { \prime \prime }$ ，而 $e ^ { \prime \prime }$ 同样取自 $\chi$ ，Bob计算得到$\nu ^ { \prime \prime } = a s s ^ { \prime } + e s ^ { \prime } + e ^ { \prime \prime }$ ，由于 $s  s ^ { \prime } , e \mathrm { ~ , ~ } e ^ { \prime }$ 及 $e ^ { \prime \prime }$ 是很小的量，因此，$\nu ^ { \prime } \approx \nu ^ { \prime \prime } \approx a s s ^ { \prime }$ ，这个结论正是基于加密机制构造密钥交换协议的基础。

在LWE加密方案中，Bob通过编码函数将一个秘密消息 $\nu$ 变成较大的值， $k = E n c o d e ( \nu )$ ，计算 $c = \nu + k$ ，并将 $\mu \setminus c$ 发送给 Alice，Alice 计算 $k ^ { \prime } = c - \nu ^ { \prime } \approx k$ ，即恢复了 $k$ 的值，注意,编码函数必须是单射函数，Alice才能恢复最原始的消息 $\mathbf { \Phi } _ { \nu }$ 。表2为基于加密机制构造密钥交换协议的描述。

表2基于加密机制构造的密钥交换协议  

<html><body><table><tr><td colspan="2">KEM.SetupO:</td></tr><tr><td>aR Alice</td><td>Bob</td></tr><tr><td>KEM.Gen(a):</td><td>KEM.Encaps(a,b):</td></tr><tr><td>s,ex</td><td>s',e,ex</td></tr><tr><td>b←as+e</td><td>μ←as'+e'</td></tr><tr><td rowspan="7">KEM.Decaps(s,(μ,c): v←μs</td><td></td></tr><tr><td>v←bs'+e"</td></tr><tr><td>v←{0,1}"</td></tr><tr><td>k ←Encode(v)</td></tr><tr><td>←μc c←v+k</td></tr><tr><td>μ ←Extract(k)</td></tr><tr><td></td></tr></table></body></html>

# 1.3.3两种构造方式的优势与劣势

在基于格LWE问题设计的密钥交换协议中使用调和机制构造方式可以减少通信量，这正是其优势所在，但是调和机制所使用的调和函数计算相当复杂。使用调和机制构造的密钥交换协议主要有基于RLWE设计的NewHope 和基于LWE设计的Frodo。而使用加密机制的构造方式设计的密钥交换协议的优势是在计算上更为简洁高效，但是较之调和机制增加了通信量，为了降低通信量的大小，在加密机制中往往使用密文压缩技术，将密文元素从 $\mathbb { Z } _ { q }$ 映射到 $\mathbb { Z } _ { p }$ 上，其中 $p { < } q$ 。密文的低位比特主要是噪声信息，运用密文压缩技术，会使这些信息丢失，但是这些噪声信息的丢失对于恢复其所加密得到的密钥影响并不大。使用加密机制构造的密钥交换协议主要为基于RLWE 设计的NewHope-Simple和基于模LWE设计的Kyber.KE。综上，目前基于LWE问题被动安全的密钥交换协议主要基于以上两种机制设计，两种机制有其各自的优势与劣势。

# 2 基于LWE问题的密钥协商协议

# 2.1Frodo 密钥交换协议

2016年CCS大会上，Bos等人提出了基于LWE问题的密钥交换协议Frodo，参数 $n = 7 5 6 \ , \quad q = 2 ^ { 1 5 } \ ,$ $\chi$ 是一种抽样效率较高的离散概率密度函数构成的扰动分布，其中 ${ \overline { { m } } } = { \overline { { n } } } = 8$ ，$B = 4$ 。由于 $\overline { { m } } \cdot \overline { { n } } \cdot B \geq 2 5 6$ ，这样协议可以达到128比特的后量子安全水平。 $\textstyle { \overline { { m } } } \cdot { \overline { { n } } }$ 是LWE 问题的维度， $B$ 是双方提取的矩阵每个元素的密钥比特值， $B$ 变大时， $\textstyle { { \overline { { m } } } \cdot { \overline { { n } } } }$ 相应减小，即降低了矩阵的维度，这样可以有效减少带宽，而且可以有效避免Lojam攻击。Frodo 方案如表3所示。

表3Frodo 密钥交换协议  

<html><body><table><tr><td>Alice</td><td>Bob</td></tr><tr><td>seedA ←U({0,1})</td><td></td></tr><tr><td>A ←Gen(seedA)</td><td></td></tr><tr><td>S,E←x(Z）</td><td></td></tr><tr><td>B←AS+E</td><td>seedA.B A ←Gen(seedA) ∈{0.1}×Zxn</td></tr><tr><td rowspan="6"></td><td>S',E'←x(Zxn)</td></tr><tr><td>B'← S'A+E'</td></tr><tr><td>E"←x(Z）</td></tr><tr><td>V←SB+E"</td></tr><tr><td>B'C C←{V)</td></tr><tr><td></td></tr><tr><td>K ← rec(B's,C)</td><td>K ←Lv]28</td></tr></table></body></html>

# 2.2新型密钥交换协议NewFrodo

Frodo方案是一个通过一般错误调和机制方式构造的密钥交换协议，这种构造方式虽然高效但计算复杂。本文在Frodo方案基础上，基于加密机制构造了一种新型实用的密钥交换协议NewFrodo。该方案是基于LWE构造的可证明被动安全的密钥交换协议，避免使用计算复杂的一般化错误调和机制，并使用NIST杂凑函数标准SHA-3有效提高了安全性能，可抵御量子攻击，并且计算简洁高效。

该方案中，为有效抵御量子攻击，对参数作如下设置：其中维度 $n = 7 5 2$ ，模数 $q = 2 ^ { 1 5 }$ ， $\chi$ 为抽样效率较高的离散概率密度函数 $\left( P D F \right)$ 构成的扰动分布，参数 $\overline { { { m } } } = \overline { { { \bf n } } } = 8 { \bf \ , } B = 4$ ，并且满足 $\overline { { m } } \cdot \overline { { n } } \cdot B \geq 2 5 6$ 。具体参数选择参考文献[15]。下面分别为方案中的具体算法。

算法1 NFEncode 对应函数 $f : K _ { _ { B i j } } \gets \left\lfloor K _ { i j } \cdot \frac { q } { 2 ^ { B } } \right\rfloor$ 输入是矩阵 $\mathbf { K } \in \mathbb { Z } _ { 2 ^ { B } } ^ { \bar { m } \times \bar { n } }$ ，矩阵元素为 $K _ { i j }$ ， $0 \leq i \leq \overline { { m } } - 1 , 0 \leq j \leq \overline { { n } } - 1$ ，输出是矩阵 $\mathbf { K } _ { \mathbf { B } } \in \mathbb { Z } _ { q } ^ { \bar { m } \times \bar { n } }$ ，矩阵元素为 $K _ { \scriptscriptstyle B i j }$ ， $0 \leq i \leq \overline { { m } } - 1$ ，$0 \leq j \leq \overline { { n } } - 1$ ：

算法2 NFDecode 对应函数 $f : K _ { _ { A i j } } \gets \left\lfloor K _ { _ { i j } } \cdot \frac { 2 ^ { B } } { q } \right\rfloor$ ，输入是矩阵 $\mathbf { K } _ { \mathbf { A } } \in \mathbb { Z } _ { q } ^ { \bar { m } \times \bar { n } }$ ，矩阵元素为 $K _ { _ { A i j } }$ $, \ 0 \leq i \leq \overline { { { m } } } - 1 \ , \ 0 \leq j \leq \overline { { { n } } } - 1$ ，输出是矩阵 $\mathbf { K } ^ { \prime } \in \mathbb { Z } _ { 2 ^ { B } } ^ { \bar { m } \times \bar { n } }$ ，矩阵元素为 $K _ { i j } ^ { \prime }$ ， $0 \leq i \leq \overline { { m } } - 1$ ，$0 \leq j \leq \overline { { n } } - 1$ ：

算法3 $t r a n ^ { 1 }$ 为字符串转换为矩阵，对应函数$f : K _ { i j } \gets \{ \nu _ { 4 k } ^ { \prime } , \nu _ { 4 k + 1 } ^ { \prime } , \nu _ { 4 k + 2 } ^ { \prime } , \nu _ { 4 k + 3 } ^ { \prime } \} , 0 \leq k \leq 6 4$ ，输入是字符串$\nu ^ { \prime } \in \left\{ 0 , 1 \right\} ^ { 2 5 6 }$ $1 \} ^ { 2 5 6 } \ : \ : \ : , \ : \ : \ : \ : \big \{ \nu _ { 4 k } , \nu _ { 4 k + 1 } , \nu _ { 4 k + 2 } , \nu _ { 4 k + 3 } \big \} , 0 \leq k \leq 6 4$ ，输出是矩阵$\mathbf { K } \in \mathbb { Z } _ { 2 ^ { B } } ^ { \bar { m } \times \bar { n } } ~ , ~ B = 4$ ，矩阵元素为 $K _ { i j } \ , \ 0 \leq i \leq \overline { { { m } } } - 1 \ , \ 0 \leq j \leq \overline { { { n } } } - 1$ ;

算法 $4 : \quad t r a n s ^ { 2 }$ 为矩阵转换为字符串，对应函数$f : \left\{ \nu _ { 4 k } ^ { \prime } , \nu _ { 4 k + 1 } ^ { \prime } , \nu _ { 4 k + 2 } ^ { \prime } , \nu _ { 4 k + 3 } ^ { \prime } \right\} \gets K _ { i j } ^ { \prime } , 0 \leq k \leq 6 4$ ，输入是矩阵 $\mathbf { K } ^ { \prime } \in \mathbb { Z } _ { 2 ^ { B } } ^ { \bar { m } \times \bar { n } }$ ，$B = 4$ ，矩阵元素为 $K _ { i j } ^ { \prime }$ ， $0 \leq i \leq \overline { { m } } - 1$ ， $0 \leq j \leq \overline { { n } } - 1$ ，输出是字符串 $\nu ^ { \prime \prime } \in \left\{ 0 , 1 \right\} ^ { 2 5 6 }$ $^ { \mathrm { ~ ~ 6 ~ } } , \quad \bigl \{ \nu _ { 4 k } ^ { \prime \prime } , \nu _ { 4 k + 1 } ^ { \prime \prime } , \nu _ { 4 k + 2 } ^ { \prime \prime } , \nu _ { 4 k + 3 } ^ { \prime \prime } \bigr \} , 0 \leq k \leq 6 4 \ \mathrm { ~ c ~ }$

下面是方案的具体执行过程：

a)首先 Alice 从 $\left\{ 0 , 1 \right\} ^ { s }$ 随机均匀抽样，得到密钥种子 $s e e d _ { A }$ ，通过Gen函数形成矩阵 $\mathbf { A } \in Z _ { q } ^ { n \times n }$ ，从噪声分布 $\chi$ 中随机均匀抽样得到矩阵 $\mathbf { S } , \mathbf { E } \in \mathbb { Z } _ { q } ^ { n \times \overline { { n } } }$ ，Alice计算 $\mathbf { B } = \mathbf { A } \mathbf { S } + \mathbf { E }$ 得到矩阵（204号 $\mathbf { B } , \mathbf { B } \in Z _ { q } ^ { n \times \bar { n } }$ ，Alice将 $s e e d _ { A } .$ B发送至Bob;

b）Bob 同样利用 $s e e d _ { A }$ 产生相同的矩阵 $\mathbf { A } \in \mathbb { Z } _ { q } ^ { n \times n }$ ，从噪声分布 $\chi$ 中随机均匀抽样得到矩阵 $\mathbf { S } ^ { \prime } , \mathbf { E } ^ { \prime } \in \mathbb { Z } _ { q } ^ { \bar { m } \times n }$ ，Bob 计算（204号 $\mathbf { B } ^ { \prime } = \mathbf { S } ^ { \prime } \mathbf { A } + \mathbf { E } ^ { \prime }$ ， $\mathbf { B } ^ { \prime } \in \mathbb { Z } _ { q } ^ { \bar { m } \times n }$ 。从噪声分布 $\chi$ 中随机均匀抽样得到矩阵 $\mathbf { E ^ { \prime \prime } } \in \mathbb { Z } _ { q } ^ { \bar { m } \times \bar { n } }$ ， $\mathbf { \Lambda } _ { \nu }$ 是一段长度为 256 比特的 $\{ 0 , 1 \}$ 字符串，使用$S H A 3 - 2 5 6$ 得到字符串 $\nu ^ { \prime }$ ，再经过 $t r a n s ^ { 1 }$ 将字符串转变为 $\bar { m } \times \overline { { n } }$ 的矩阵 $\mathbf { K }$ ，且矩阵中的每个元素 $K _ { _ i } \in \mathbb { Z } _ { _ 2 ^ { B } }$ ，对矩阵 $\textbf { K }$ 由NFEncode函数得到矩阵 $\mathbf { K } _ { B }$ ，Bob 计算 $\mathbf { C } = \mathbf { S } ^ { \prime } \mathbf { B } + \mathbf { E } ^ { \prime \prime } + \mathbf { K _ { B } }$ ，发送矩阵 $\mathbf { B ^ { \prime } } \cdot \mathbf { C }$ 给Alice。Bob 对 $\nu ^ { \prime }$ 使用 SHA3-256 得到共享密钥$S K _ { _ B }$ ；

c)Alice 计算 ${ \bf { K } } _ { \bf { A } } = { \bf { C } } - { \bf { B } } ^ { \prime } { \bf { S } }$ ， $\mathbf { K } _ { \mathbf { A } } \in \mathbb { Z } _ { q } ^ { \bar { m } \times \bar { n } }$ ， $\mathbf { K } _ { \mathbf { A } }$ 由 NFDecode得到矩阵 $\mathrm { ~ \bf ~ K ~ } ^ { \prime } \cdot \mathrm { ~ \bf ~ K ~ } ^ { \prime }$ 经过 $t r a n s ^ { 2 }$ 由矩阵转变为长度为 $\scriptstyle { { \overline { { m } } } \cdot { \overline { { n } } } \cdot B }$ 的字符串 $\nu ^ { \prime \prime }$ ,Alice 对字符串 $\nu ^ { \prime \prime }$ 使用 SHA3-256 得到共享密钥 $S K _ { A }$ 。

由上述方案，由双方的传输消息进行方案的相关正确性分析：将 Bob 计算量 $\mathbf { C } = \mathbf { S } ^ { \prime } \mathbf { B } + \mathbf { E } ^ { \prime \prime } + \mathbf { K _ { B } }$ 代入Alice 计算式$\mathbf { K } _ { \mathrm { A } } = \mathbf { C } - \mathbf { B } ^ { \prime } \mathbf { S } = \mathbf { S } ^ { \prime } \mathbf { B } + \mathbf { E } ^ { \prime } + \mathbf { K } _ { \mathrm { B } } - \mathbf { B } ^ { \prime } \mathbf { S } = \mathbf { S } ^ { \prime } \left( \mathbf { A } \mathbf { S } + \mathbf { E } \right) + \mathbf { E } ^ { \prime } + \mathbf { K } _ { \mathrm { B } } - \left( \mathbf { S } ^ { \prime } \mathbf { A } + \mathbf { E } ^ { \prime } \right) \mathbf { S } ^ { \mathbf { l } , \mathbf { S } } \xrightarrow [ \mathbf { \Gamma } ] { \mathbf { J } ^ { \prime } \mathbf { B } - \mathbf { s } } \chi \big ( \mathbf { \overline { { \mathbf { \mathcal { U } } ^ { \prime \prime } \mathbf { \Psi } } } } \big )$ ，由于 $\mathbf { \nabla } \mathbf { E } ^ { \mathbf { \nu } , \mathbf { \nu } } \mathbf { E ^ { \prime } } ^ { \mathbf { \nu } , \mathbf { \nu } } \mathbf { E ^ { \prime } }$ 是很小的量，因此可得 $\mathbf { K _ { A } } = \mathbf { C } - \mathbf { B ^ { \prime } S } = \mathbf { K _ { B } }$ 。由NFEncode，NFDecode可得 ${ \bf K } ^ { \prime } \approx { \bf K }$ ，进而可得$S K _ { \scriptscriptstyle A } = S K _ { \scriptscriptstyle B } = S K$ 。

表4本文设计方案  
表5算法的具体流程  

<html><body><table><tr><td colspan="2">Alice</td><td>Bob</td></tr><tr><td>seed ←U({0,1})</td><td></td><td></td></tr><tr><td>A←Gen(seedA)</td><td></td><td></td></tr><tr><td>S,E←x(z)</td><td></td><td></td></tr><tr><td>B←AS+E</td><td>seed.B ∈{0,1}×Zg</td><td>A←Gen(seed )</td></tr><tr><td rowspan="8"></td><td></td><td>S',E←x(z)</td></tr><tr><td></td><td>B'←S'A+E'</td></tr><tr><td></td><td></td></tr><tr><td></td><td>E"←x(Z）</td></tr><tr><td></td><td>V←{0,1}256</td></tr><tr><td></td><td>V ← SHA3- 256(v)</td></tr><tr><td></td><td>K ←trans'(v')</td></tr><tr><td></td><td>KB←NFEconde(K)</td></tr><tr><td>K←C-B'S</td><td></td><td>C← SB+E" +KB</td></tr><tr><td>K'←NFDecode(KA)</td><td></td><td>SKB← SHA3-256(v')</td></tr><tr><td>v" ←trans²(K')</td><td></td><td></td></tr><tr><td>SK ← SHA3-256(v")</td><td></td><td></td></tr></table></body></html>

# 3 安全性分析

本文协议被动攻击下可证明安全，首先通信报文不泄露关于秘密的信息，其次需证明双方交换的密钥与随机数不可区分。考虑敌手M尝试在给定密钥交换协议中区分会话密钥 $\mathit { s K }$ 和均匀随机密钥 ${ \boldsymbol { s } } { \boldsymbol { K } } ^ { \prime }$ ,定义敌手 $\mathbf { M }$ 赢得游戏的优势为

$$
\begin{array} { r l } & { A d { \cal V } _ { n , \bar { n } , \bar { m } , B , q , \chi } ^ { d d h - l i k e } \left( { \cal M } \right) = } \\ & { \left| \mathrm { P r } \left[ { \cal M } \left( { \bf A } , { \bf B } , { \bf B } ^ { \prime } , { \bf C } , S K \right) = 1 \right] - \mathrm { P r } \left[ { \cal M } \left( { \bf A } , { \bf B } , { \bf B } ^ { \prime } , { \bf C } , S K ^ { \prime } \right) = 1 \right] \right| . } \end{array}
$$

定理1令 ${ } _ { n , { \overline { { n } } } , { \overline { { m } } } , B }$ 和q是有效整数， $\chi$ 是 $Z _ { \boldsymbol { q } }$ 上一特定错误分布，如果Gen是一个安全的伪随机函数，并且设置参数为$\left( n , q , \chi \right)$ ，此时判定性LWE 问题是困难的，即本文提出的密钥交换协议产生的密钥是难以区分的，即

$$
\begin{array} { r l } & { A d \nu _ { n , \bar { n } , \bar { m } , B , q , \chi } ^ { d d h - l i k e } \left( M \right) \leq A d \nu _ { G e n } ^ { \mathrm { P r } f } \left( B _ { 0 } \right) + } \\ & { \overline { { n } } \cdot A d \nu _ { n , q , \chi } ^ { d l w e } \left( M \cdot B \right) + \overline { { m } } \cdot A d \nu _ { n , q , \chi } ^ { d l w e } \left( M \cdot B _ { 2 } \right) } \end{array}
$$

表5为 $B _ { \imath }$ ， $B _ { 2 }$ 算法的具体流程， $B _ { 0 }$ 隐含在证明中。

$B _ { 1 } { \big ( } \mathbf { A } , \mathbf { B } { \big ) }$ E)s1S,E←x(（Zx) B(Y,Z):2.B'←S'A+E' （AT)（20 $3 . \mathbf { E } ^ { \prime \prime } { \xleftarrow { \mathfrak { s } } } \chi \left( \mathbb { Z } _ { q } ^ { { \bar { m } } \times { \bar { n } } } \right)$ （BT） ↑Y（20 $4 . \nu \longleftarrow \{ 0 . 1 \} ^ { 2 5 6 }$ （20 2.v←{0,1}256$5 . \nu ^ { \prime }  S H A 3 - 2 5 6 ( \nu )$ 3.v'← SHA3-256(v)6.K ←trans1(v) $4 . \left( \mathbf { B } ^ { \mathrm { { T } } } \right) \gets \mathbf { Z }$ $7 . \mathrm { K } _ { \mathrm { s } } \gets N F E n c o d e ( \mathbf { K } )$ $\mathbf { 8 . C  S ^ { \prime } B + E ^ { \prime \prime } + K _ { B } }$ $5 . \mathbf { K } _ { \mathrm { a } } \gets \mathbf { C } - \mathbf { B } ^ { \prime } \mathbf { S }$ $9 . \mathbf { K } _ { \mathbf { A } } \gets \mathbf { C } - \mathbf { B } ^ { \prime } \mathbf { S }$ （204号 $6 . S K  S H A 3 - 2 5 6 \ l ( \nu ^ { \prime } )$ $1 0 . S K  S H A 3 - 2 5 6 \ l ( \nu ^ { \prime } )$ $7 . S K ^ { \prime } { \xleftarrow { \cdot } } { \underline { { u } } } { \left( { \left\{ 0 , 1 \right\} } ^ { { \overline { { n } } } \cdot { \overline { { m } } } \cdot B } \right) }$ （20 $1 1 . 5 K ^ { \prime } {  } u { ( { \{ 0 , 1 \} } ^ { { \overline { { n } } \cdot \overline { { m } } \cdot B } } ) }$ $8 . b ^ { * } \longleftarrow \left( \{ 0 , 1 \} \right)$ （204号$1 2 . 6 ^ { * } \longleftarrow s \_ u ( \{ 0 , 1 \} )$ 9.如果 $\boldsymbol { \mathrm { b } } ^ { * } { = } \boldsymbol { 0 }$ ，返回 $\left( A , B , B ^ { \prime } , C , \mathrm { S K } \right)$ 13.如果 $\boldsymbol { \mathrm { b } } ^ { * } = \boldsymbol { 0 }$ ，返回 $\left( A , B , B ^ { \prime } , C , \mathrm { S K } \right)$ 10.否则返回 $\left( A , B , B ^ { \prime } , C , \mathrm { S K ^ { \prime } } \right)$ 14.否则返回 $\left( A , B , B ^ { \prime } , C , \mathrm { S K ^ { \prime } } \right)$

证明在下述游戏证明中， $S _ { i }$ 表示在 $G a m e _ { i }$ 中表示敌手猜测 $\boldsymbol { b } ^ { * }$ 的值， $b ^ { * } \in \{ 0 , 1 \}$ 。$G a m e _ { 0 }$ .消息是由本文协议真实产生的。以下均是LWE 分布实例,(A,B)包含秘密值S， $\left( \mathbf { A } , \mathbf { B } ^ { \prime } \right)$ 与(B,V)包含秘密值 $\mathbf { s } ^ { \prime }$ ,因此

$$
A d \nu _ { n , \bar { n } , \bar { m } , B , q , \chi } ^ { d d h - l i k e } \left( M \right) = \left| \mathrm { P r } \left( S _ { 0 } \right) - \frac { 1 } { 2 } \right|
$$

Game.公钥矩阵 $\mathbf { A }$ 是随机均匀产生的,而不是使用 $G e n$ 函数,由 $s e e d _ { A }$ 伪随机产生的。

$G a m e _ { 0 }$ 与 $G a m e _ { 1 }$ 的区别:敌手 $\mathbf { M }$ 可以区分这两个游戏,则需要一个区分器B，B

$$
\left| \operatorname* { P r } \bigl ( S _ { 0 } \bigr ) - \operatorname* { P r } \bigl ( S _ { 1 } \bigr ) \right| \leq A d \nu _ { G e n } ^ { \operatorname* { P r } f } \left( B _ { 0 } \right)
$$

$G a m e _ { 2 }$ .Alice 的临时公钥 $\mathbf { B }$ 是随机均匀产生的，而非从$\left( n , { \overline { { n } } } \right) -$ 矩阵的判定性 LWE 问题实例中产生，LWE 分布实例$\left( \mathbf { A } , \mathbf { B } ^ { \prime } \right)$ 和(B,C)都有秘密矩阵 $\mathbf { S ^ { \prime } }$ 。

Game与 $G a m e _ { 2 }$ 的区别：在 $G a m e _ { 1 }$ 中，(A,B)是 $O _ { x , s }$ 分布的一个样本，在参数为 $\left( n , q , \chi \right)$ 的判定性 LWE 问题的假设下,这两种分布是难以区分的。

更准确地说，图5中的算法B的输入为(A,B)，若(A,B)是 $O _ { x , s }$ 分布的一个样本，并且满足 $\mathbf { S } \gets \_ \_ \bigstar \bigstar \bigstar \bigstar$ ，则 $B _ { 1 }$ 的输与 $G a m e _ { 1 }$ 输出相同，若(A,B)是 $u \big ( \mathbb { Z } _ { q } ^ { n \times \bar { n } } \big ) \times u \big ( \mathbb { Z } _ { q } ^ { n \times \bar { n } } \big )$ 分布的一个样本，则的输出与 $G a m e _ { 2 }$ 的输出相同，输出 $B _ { 1 }$ 与 $G a m e _ { 2 }$ 相同。如果敌手 M 可以区分 $G a m e _ { 1 }$ 和 $G a m e _ { 2 }$ ，那么 $M \cdot B _ { \mathrm { l } }$ 可以区分$O _ { x , s }$ 分布和 $u \big ( Z _ { q } ^ { n \times \bar { n } } \big ) \times u \big ( Z _ { q } ^ { n \times \bar { n } } \big )$ 分布。因此,

$$
\left| \operatorname* { P r } \left( S _ { 1 } \right) - \operatorname* { P r } \left( S _ { 2 } \right) \right| \le \overline { n } \cdot A d \nu _ { n , q , \chi } ^ { d l w e - s s } \left( M \cdot B _ { 1 } \right) .
$$

$G a m e _ { 3 }$ .Bob 的临时公钥 $\mathbf { B ^ { \prime } }$ 和矩阵 $\mathbf { c }$ 同时由 $\mathbf { S ^ { \prime } }$ 产生，在Game中，包含秘密值 $\mathbf { S ^ { \prime \prime } }$ 的 $\left\{ { \left( \mathbf { A } ^ { \mathrm { T } } \right) } , { \left( \mathbf { B } ^ { \prime \mathrm { T } } \right) } \right\}$ 是 $\left( n + \overline { n } , \overline { m } \right) -$ 矩阵判定性LWE 问题的一个实例。

$G a m e _ { 2 }$ 与 $G a m e _ { 3 }$ 的区别。由分析可知

$$
\mathbf { P r } \big ( \mathbf { S } _ { 1 } \big ) = \mathbf { P r } \big ( \mathbf { S } _ { 2 } \big )
$$

Game,.Bob的临时公钥 $\mathbf { B ^ { \prime } }$ 和矩阵 $\mathbf { c }$ 均是随机均匀产生的,而不是同时从 $\mathbf { S ^ { \prime } }$ 中产生的。

$G a m e _ { 3 }$ 与 $G a m e _ { 4 }$ 的区别。在 $G a m e _ { 3 }$ 中， $\left( \left[ \mathbf { A } \| \mathbf { B } \right] , \left[ \mathbf { B } ^ { \prime } \| \mathbf { C } \right] \right)$ 是$\left( n + \overline { n } , \overline { m } \right) -$ 矩阵判定性LWE问题的随机 $O _ { \chi , s ^ { \prime } }$ 分布的一个样本。在 $G a m e _ { 4 }$ 中， $\left( \left[ \mathbf { A } \| \mathbf { B } \right] , \left[ \mathbf { B } ^ { \prime } \| \mathbf { C } \right] \right)$ 是 $u \big ( \mathbb { Z } _ { q } ^ { ( n + \overline { { n } } ) \times n } \big ) \times u \big ( \mathbb { Z } _ { q } ^ { ( n + \overline { { n } } ) \times m } \big )$ 的一个样本。设置参数为 $\left( n , q , \chi \right)$ ，在判定性 LWE 问题的假设下，这两种分布是难以区分的。更准确地说，图5所示的 $B _ { 2 }$ 算法将（20 $( \mathbf { Y } , \mathbf { Z } ) \in \mathbb { Z } _ { q } ^ { ( n + \overline { { n } } ) \times n }$ 作为输入，若 $( { \bf Y } , { \bf Z } )$ 是 $\left( n + { \overline { { n } } } , { \overline { { m } } } \right) -$ 矩阵判定性LWE问题的随机Ox分布的一个样本，且满足S←χ(Z""）则 $B _ { 2 }$ 的输出与 $G a m e _ { 3 }$ 输出相同，若(A,B)是 $u \big ( \mathbb { Z } _ { q } ^ { n \times \bar { n } } \big ) \times u \big ( \mathbb { Z } _ { q } ^ { n \times \bar { n } } \big )$ 分布的一个样本，则 $B _ { 2 }$ 的输出与 $G a m e _ { 4 }$ 的输出相同。如果敌手M可以区分 $G a m e _ { 3 }$ 和 $G a m e _ { 4 }$ ，那么 ${ \boldsymbol { M } } \cdot { \boldsymbol { B } } _ { 2 }$ 可以区分 $O _ { \chi , s ^ { \prime } }$ 和$u \big ( \mathbb { Z } _ { q } ^ { ( n + \overline { { n } } ) \times n } \big ) \times u \big ( \mathbb { Z } _ { q } ^ { n \times \overline { { m } } } \big )$ 这两种分布的样本。因此，

$$
\left| \operatorname* { P r } \left( S _ { 3 } \right) - \operatorname* { P r } \left( S _ { 4 } \right) \right| \leq \overline { m } \cdot A d \nu _ { n , q , \chi } ^ { d d h - l i k e } \left( M \circ B _ { 2 } \right) .
$$

Game4的分析.敌手 $\mathbf { M }$ 猜测 $\boldsymbol { b } ^ { * }$ 的值从而来区分 $s _ { K }$ 和 $\boldsymbol { s K ^ { \prime } }$ ，在 $G a m e _ { 4 }$ 中， $\mathbf { \Delta } S K ^ { \prime }$ 是从 $\left\{ 0 , 1 \right\} ^ { \bar { m } \cdot \bar { n } \cdot B }$ 中随机均匀产生的，敌手M已知矩阵 $\mathbf { c }$ ，在给定 $\mathbf { c }$ 的情况下， $\mathbf { K } _ { \mathbf { A } }$ 是随机均匀的，进而可得SK也是随机均匀的，因此，敌手M无法得到 $\boldsymbol { b } ^ { * }$ 的任何信息，可得

$$
\mathrm { P r } ( \mathrm { S } _ { 4 } ) = \frac { 1 } { 2 }
$$

综合等式 $( 1 ) \sim ( 6 )$ ，定理1得证。

本文提出的基于LWE 问题构造的密钥交换协议NewFrodo,根据Regev 给出的格最坏情况困难问题到LWE问题的归约结论，该协议的安全性最终可以基于格下标准最坏情况困难假设。因此，本文提出的密钥交换协议在被动攻击下可证明安全。

# 4 效率分析

通过目前公开的学术文献，对现有的基于LWE问题来构造的被动安全的密钥交换协议进行综合分析。为了说明方案的优劣，选取最典型的 BCNS15[12]、Newhope、NewHope-Simple、Frodo 四个方案，通过密钥交换协议方案的参数设置、困难问题假设、使用的KEM方式、消息长度等方面，进行对比以便突显本方案综合性能。表1是本方案与现有的基于RLWE、LWE的密钥交换方案进行对比。

BCNS15 方案选取的参数为维度n=1024，模数q=2-1错误分布是离散高斯分布且方差为 $4 \sqrt { 2 }$ 。在该参数的设置下（204号最终生成共享会话密钥失败的概率很低，后量子安全性约为80比特。该方案通信双发最终可生成1024比特大小的共享密钥，但在实际需求中仅需 256比特；2015年，Akim 等人全面提升了BCNS15 协议,提出了一种基于RLWE 问题的协议NewHope密钥交换协议，在参数设置方面采用了相同的维度n，模数$\scriptstyle 9 = 1 2 2 8 9$ ，错误分布为中心二项分布。方差为8，在该参数的设置下，使得生成共享密钥失败的概率可以忽略，并且后量子安全性达到了206比特。选取中心二项分布代替原来的离散高斯分布，大大提高了协议的计算效率；2016年Akim等人提出了基于加密机制构造的协议NewHope-Simple,参数设置包括维度n，模数q以及错误分布与方差均相同。通信量与NewHope 相比只增加了 $6 . 2 5 \%$ ，但是方案未使用计算复杂的调和技术，协议更加简洁高效。由于参数设置相同，因此共享密钥失败概率几乎相等，且后量子安全性相同均为206 比特；由于RLWE 问题其环上特殊的代数结构存在安全性的潜在威胁，2016年CCS安全会议上Bos等人基于LWE问题使用调和机制构造了一种密钥交换协议Frodo,根据推荐参数，维度 $\scriptstyle \mathtt { n } = 7 5 6$ ，模数 ${ \mathsf { q } } ^ { = } 2 ^ { 1 5 }$ ，错误分布为抽样效率更高的离散概率密度（PDF）函数构成的扰动分布，方差为1.75，由于协议使用了更一般的调和机制，在每次执行rec 函数时可以得到4比特数据，使得生成共享密钥失败的概率增加，但在参数设置下，使得失败概率依然可以忽略，且该方案后量子安全性达到了130比特。

本方案与基于LWE问题构造的Frodo协议相比，以一方通信量从11296Byte 增至11520Byte,仅增加 $1 . 0 9 \%$ 的微小代价，避免使用计算复杂的调和机制而使用计算简单的加密机制，方案计算更加简洁高效，并使用了NIST杂凑函数标准SHA-3，进一步提高了协议的安全度。参数设置与Frodo方案相同，因此协议失败概率也可忽略，后量子安全性也达到 $1 3 0 { \mathrm { b i t } }$ 。且该协议在被动攻击下可证明安全，可有效抵御量子攻击。

# 5 结束语

本文设计了一种基于格上LWE 问题的被动安全的密钥交换协议，结合Bos等人提出的被动安全的密钥交换协议Frodo以及Alkim 等人提出的密钥交换协议NewHope-Simple 的突出优势。Frodo协议使用调和机制，虽然通信量较小，但错误调和机制rec函数计算复杂，本文方案正是避免使用错误调和机制而借鉴了NewHope-Simple 中的基于加密机制的构造方式，使得计算更加简洁高效。与基于RLWE问题构造的密钥交换协议相比，虽然密钥尺寸较大，但RLWE问题附加环的代数结构存在潜在的安全性威胁，基于LWE问题较之RLWE问题设计的密钥交换协议在安全性能上更加稳健。最近，Bos等人提出了一种基于模LWE问题的高效安全的密钥交换协议Kyber.KE[20]。下一步考虑基于LWE问题、RLWE问题及模LWE问题设计出更加实用、高效的密钥交换协议。

表1基于RLWE与LWE的密钥交换协议的性能比较  

<html><body><table><tr><td rowspan="2">方案</td><td rowspan="2">维度n</td><td rowspan="2">模数 q</td><td rowspan="2">错误分布x 方差²</td><td rowspan="2">困难假设</td><td rowspan="2">构造方式</td><td rowspan="2">通信计算复杂度</td><td colspan="2">通信量（byte)</td><td rowspan="2">后量子安 全(bit)</td></tr><tr><td>A→B</td><td>B→A</td></tr><tr><td>BCNS15</td><td>1024</td><td>2-1</td><td>高斯分布、4√2/ /π</td><td>RLWE</td><td>调和机制</td><td>n + 2nlog2q</td><td>4096</td><td>4224</td><td>80</td></tr><tr><td>NewHope</td><td>1024</td><td>12289</td><td>二项分布、8</td><td>RLWE</td><td>调和机制</td><td>2n+2nlog2q</td><td>1824</td><td>2048</td><td>206</td></tr><tr><td>NewHope-</td><td>1024</td><td>12289</td><td>二项分布、8</td><td>RLWE</td><td>加密机制</td><td>3n +2nlog2q</td><td>1824</td><td>2176</td><td>206</td></tr><tr><td>Simple Frodo</td><td>756</td><td>215</td><td>PDF 扰动分布、1.75</td><td>LWE</td><td>调和机制</td><td>(n + m)(nlog q +1)</td><td>11377</td><td>11296</td><td>130</td></tr><tr><td>本方案</td><td>756</td><td>215</td><td>PDF 扰动分布、1.75</td><td>LWE</td><td>加密机制</td><td>(n + m)(nlog q + 4)</td><td>11377</td><td>11520</td><td>130</td></tr></table></body></html>

# 参考文献：

[1]Dodis Y,Mironov I, Stephens-Davidowitz N. Message transmission with reverse firewalls-secure communication on corrupted machines [C]/ Advances in Cryptology-CRYPTO.Berlin: Springer,2016:341-372.   
[2] Benzvi A,Blackburn S R,Tsaban B.A practical cryptanalysis of the algebraic eraser [C]//Advances in Cryptology-CRYPTO.Berlin: Springer, 2016: 179-189.   
[3]Diffie W,Hellman M.New directions in cryptography [J]. IEEE Trans on Information Theory,1976,22(6): 644-654.   
[4] Chen L,Jordan S,et al. Report on post-quantum cryptography [M]. Gaithersburg:National Institute of Standards and Technology,2016.   
[5]Gorbunov S,Vaikuntanathan V,Wee H. Predicate encryption for circuits from LWE [C]//Proc of CRYPTO.Berlin: Springer,2015:503-523.   
[6]Gorbunov S,Vaikuntanathan V,Wee H.Attribute-based encryption for circuits [C]//Proc of ACM Symp on Theory of Computing.NewYork:ACM Press,2013: 545-554.   
[7]Boneh D,Gentry C,Gorbunov S,et al.Fully key-homomorphic encryption, arithmetic circuit ABE and compact garbled circuits [C]// Proc of EUROCRYPT.Berlin: Springer, 2014: 533-556.   
[8]Bai S,Galbraith S D.An improved compresson technique for signature based on learning with errors [C]//Proc of Topics in Cryptology.Berlin: Springer,2014: 28-47.   
[9]Lyubashevsky V.Digital signatures based on the hardness of ideal lattice problems in al rings [C]//Proc of ASIACRPT.Berlin: Springer,2016:196- 214.

[10]Ding J, Universuty C.A simple provably secure key exchange scheme based on the learning with errors problem[J].IACR Cryptology ePrint Archive, 2012.

[11] PeikertC.LatticecryptographyfortheInternet[C]//PostQuantumCryptography.Berlin: Springer,2014.197-219.   
[12] Bos JW, Costello C,Naehrig M, Stebila D.Post-quantum key exchange for the TLS protocol from the ring learning with errors problem [C]//Proc of IEEE Symposium on Security and Privacy, Washington DC: IEEE Computer Society Press,May 2015:553-570.   
[13] Alkim E,Popplemann D,Schwabe P.Post-quantum key exchange: a new hope[C]// USENIX Security 16.[S.1.] : USENIX Association,2015.   
[14] Alkim E,Popplemann D,Schwabe P.NewHope without reconciliation [J]. IACR Cryptology ePrint Archive,2016,2016: 1157.   
[15]Bos J,Costello C,et al.Frodo!take off the ring!practical, quantum secure key exchange from LWE [C]// Proc of Conference on Computer and Communications Security.New York:ACMPress,2016:1006-1018.   
[16] Benhamouda F, Camenisch J, Krenn S,et al. Better zero-knowledge proofs for lattice encryption and their application to group signatures [C]//Proc of ASIACRYPT.Berlin: Springer, 2014: 551-572.   
[17]Regev O.On latices,learning with errors,random linear codes,and cryptography[J].Journal of the ACM,2005,56(6): 84-93.   
[18] Lyubashevsky V,Peikert C,Regev O. On ideal latticesand learning with errors over rings [C]//Advance in EuroCrypt.Berlin: Springer,2010:1-23.   
[19] Langlois A,Stehlé D.Worst-case to average-case reductions for module lattices [J].Designs,Codes and Cryptography,2015,75 (3): 565-599.   
[20]BosJ,Ducas L,Kiltz E,etal. Crystals-Kyber:a CCA-secure module-latticebased KEM[J].IACR Cryptology ePrint Archive,2017,2017: 634.