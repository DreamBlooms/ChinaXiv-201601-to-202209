# 基于多素数和参数替换的改进RSA算法研究

周金治a，高磊b

(西南科技大学 a.信息工程学院;b.特殊环境机器人技术四川省重点实验室，四川 绵阳 621010)

摘要：为了提高RSA 公钥算法在消息加密过程中的安全性，在深入分析传统RSA算法的基础上，对其进行一些改进性研究，提出了一种比传统RSA算法更加有效的方法优化其安全性。在将传统RSA改进为四素数RSA的基础上，再运用数学变换进行参数替换，消除了在公钥中对传输两个随机素数的乘积n的需要，引入了一个新的参数 $\mathbf { x }$ 代替原参数n。针对改进后的算法在运算效率方面的不足，采用中国剩余定理(Chinese remainder theorem，CRT)优化大数模幂运算。实验结果证实了改进算法的可行性，为通过公钥加密消息发送和接收提供了更安全的路径；同时，对改进算法与传统RSA 和四素数RSA算法的解密(签名)时间进行比较分析。实验结果表明改进后的算法对消息发送方和接收方之间签名效率也有一定程度的优化。

关键词：RSA算法；数据加密；参数替换；中国剩余定理；公钥；签名效率中图分类号：TP312 doi: 10.3969/j.issn.1001-3695.2017.09.0879

# Research on improved RSA algorithm based on multi-prime number and parameter substitution

Zhou Jinzhiat, Gao Leib (a.SchoolofInformationEngineering,b.RobotTechnologyfor Special Environment KeyLaboratoryofSichuanProvince, Southwest University of Science & Technology,Mianyang Sichuan 621o10, China)

Abstract: Inorder toachieve greatersafety inRSAencryptionalgorithmin thedata enryption proces,this paper made some improvements basedonin-depth analysis onthe traditional RSAalgorithm.It put forward a more secure method with changing traditional double primes intofour primes inthetraditionalRSAalgorithmand eliminatingtherequirementfortransfering the productnoftworandom primes in public keyonthe basisof parameter substitution.Instead,this paper replaced the original parameter n toanew introduced parameterx.Inorder to boost theeficiency in the introduced algorithm,this paperused the CRT(Chineseremainder theorem)to expedite the exponentiationof large numbers.Theresultsdemonstrates the feasibilityof theimprovedalgorithm,provides asaferpath for messages transmision throughpublic keyencryption.Atthe same time,this papercaried outacomparative analysis of encryption and decryption time among the improved algorithm and the traditional double primes andfour primes RSAalgorithms.Theresults shows that theimproved algorithmtoacertaindegree enhanced the encryption and decryption efficiency between the message sender and receiver.

Key Words:RSAalgorithm;data encryption;parameter substitution;the Chineseremainder theorem; public key;decryption efficiency

# 0 引言

随着信息通信技术在互联网时代的不断发展，信息安全问题日益受到人们的广泛关注，以密码学为基础的信息安全技术也得到了飞速的发展。数据加密技术根据密钥的类型发展出了两种不同的密码体制，分别是对称的密码密钥体制（symmetrickeycryptosystem）和非对称密钥密码体制（asymmetric-keycryptosystem）。其中，非对称密钥密码体制涉及使用两个不同但相关的密钥，即公钥和私钥[1。明文通过公钥被转换成密文。

这个过程称为加密，由发送方执行。另一方面，通过使用接收方的私钥来执行密码文本的解码。这个过程称为解密，由接收者执行。为了保持私钥的机密性，公开密钥公开给公众。公钥用于身份验证，以确保消息来自预定发送者。只有接收方的私钥才能解密源于发送方的密码文本。因为公钥的知识不足以解密密文，所以消息的通信可以以安全的方式进行。

传统RSA算法容易遭受到选择密文攻击、出错攻击、连分数攻击和对模数 $n$ 的分解攻击[2]。关于如何改进RSA算法以提高其安全性，文献[3,4]提出了一种新的算法概念和为加快整个网络的数据交换过程中RSA算法实现的改进形式，通过在公钥和私钥的构成中使用额外的第三素数的方法增加参数 $n$ 的因式分解复杂性，但容易受到选择密文攻击。文献[5]提出了一种消除参数 $n$ 的改进RSA密码体制，但只给出了一个特例进行说明，缺乏基于实验的科学论证，结论不具备说服力。文献[6]提出了一种基于参数 $n$ 的改进RSA算法，通过使用四个素数优化现有的RSA算法，这种方法依然可以通过因数分解的方法得到密钥，从而对消息进行攻击。

在标准RSA算法中，公钥和私钥这两者之间存在一个数学关系，这一事实为密码攻击者发现与破解密钥之间的关系进而成功地派生出私钥提供了可能性。本文应用一种数学变换替换参数 $n$ ，增加了攻击者确定这个因素的困难度，从而优化RSA算法的安全性能。

# 1 RSA算法及相关问题分析

# 1.1算法原理

非对称加密算法中最著名的是由美国MIT的Rivest等人[7]于1978年发表的RSA算法，它也是目前应用最为广泛的公钥加密算法，现在被国际标准化组织（International Organization forStandardization，ISO）推荐为公钥数据加密标准。它是一种非对称密钥密码体制，涉及到将公共密钥和私有密钥分配给发送方和接收方来加密和解密消息。在加/解密时使用的是两种不同的密钥，即加密密钥与解密密钥。其安全性是基于数论和计算复杂性理论，两个大素数乘积的计算是十分容易的，但是想要很快将两个大素数的乘积分解，求出它的因子在计算上是困难的，至今还没有一种方法能够很好的将其破解。利用RSA公钥加密算法对消息加密后，消息的安全性主要就是依赖于大整数因式分解的复杂性[8]。RSA公钥加密算法包含密钥生成、消息加密、消息解密三个步骤，下面给出算法描述。

# 1.1.1RSA密钥生成

任意选取两个不相干的大素数 $p$ 和 $q$ 将其保密存储起来;

计算 $n _ { \mathrm { \Delta } } = p q$ 和欧拉函数 $\phi \left( n \right) \ = \left( p - 1 \right) \left( q - 1 \right)$ ：

随机地选取一个正整数 $e$ ，使其满足 $1 < e < \phi ( n )$ ，并且要求$e$ 和 $\phi ( n )$ 的最大公约数 $G C D ( e , \phi ( n ) ) = 1$ ,那么公开的加密密钥，即公钥为 $( e , ~ n )$

计算解密密钥 $d$ ，使其满足 $0 < d < \phi ( n )$ ，且$e d \equiv 1 ( m o d ~ \phi ( n ) )$ ，即私钥为 $( d , \ n )$ 。

# 1.1.2 消息加密

消息发送方使用下面方式对明文 $M$ 进行加密：

$$
C = M ^ { \it e } m o d ( n )
$$

1.1.3消息解密

消息接收方使用下面方式对密文 $C$ 进行解密：

$$
\boldsymbol { M } = \boldsymbol { C } ^ { d } m o d ( n )
$$

其中： $M$ 代表需要加密的明文； $C$ 代表加密后的密文； $e$ 代表加密时候的密钥； $d$ 代表解密时候的密钥； $n$ 代表模数。

# 1.2 可优化性分析

RSA从发表到现在已有近四十年的时间，其间经历了各种攻击的考验，是最典型也是被研究得最成熟的，至今仍是公钥密码学最优秀的算法之一。虽然RSA算法的安全性是建立在大整数的因式分解基础之上，但是到目前还没有从理论上证明破译RSA的难度等价于大整数因式分解的难度，即从理论上掌握RSA的加密性能还无法实现。而且对于大量数据的加/解密，RSA算法的可优化之处分为算法安全性和运算效率两个方面，下面逐一分析。

# 1.2.1安全性分析

本文就针对参数 $n$ 的攻击进行算法安全性分析。

（1）模数 $\mathfrak { n }$ 的因式分解

在公开密钥中，密码攻击者可以利用伪造的签名对模数 $n$ 进行分解，那么则有可能计算出 $\phi \left( n \right) ~ = { \left( p - 1 \right) } { \left( q - 1 \right) }$ 。这样，解密密钥就可以求出，从而整个RSA公钥算法就被破译了。例如，密码攻击者可以通过下述方法对 $n$ 进行因子分解：

(a)根据 $\phi ( n ) \ = ( p - 1 ) ( q - 1 ) = n - ( p + q ) + 1$ 和 $n = p q$ 可以求得 $p + q = \phi { \bigl ( } n { \bigr ) } + 1$ ；

(b） $( p + q ) ^ { 2 } = p ^ { 2 } + 2 p q + q ^ { 2 } = ( p - q ) ^ { 2 } + 4 p q$ 可以求得 $p - q = \sqrt { \left( p + q \right) ^ { 2 } - 4 n } \ ;$

(c）根据 $p = ( ( p + q ) + ( p - q ) ) / 2$ 求出 $p$ (d)再由 $n = p q$ 求出 $q$ 。

至此，攻击者完成了对参数 $n$ 的因子分解，由此就可能破解RSA密码系统。

# （2）RSA的选择密文攻击

由于 $n$ 是通过公钥传输的，所以攻击者可以使用公钥加密明文，然后通过点击和试用找出其影响因素。如果任何密文与之匹配，攻击者就可以了解秘密消息，从而降低RSA算法的安全系数。选择密文攻击是指密码攻击者事先选择不同的密文，让被攻击的算法解密，利用未知的密钥取得与之对应的明文，由此推算出私钥或模数，进而获得自己想要的明文，是针对RSA等公钥算法最常用的攻击方法[9]。例如，如果攻击者想破译消息 $x$ 获取其签名，可以事先虚构两个合法的消息 $x _ { 1 }$ 和 $x _ { 2 }$ ，使得 $x \equiv ( x _ { 1 } x _ { 2 } ) { \big ( } m o d n { \big ) }$ ，并骗取用户对 $x 1$ 和 $x 2$ 的签名$S _ { 1 } = x _ { 1 } ^ { \ d } ( { \bmod { n } } )$ 和 $S _ { 2 } = x _ { 2 } ^ { ~ d } ( { \bmod { n } } )$ ，就可以计算出 $\mathbf { x }$ 的签名：

$$
S = x ^ { d } = ( ( ( x _ { 1 } x _ { 2 } ) ( { \bmod { n } } ) ) ^ { d } ) ( { \bmod { n } } )
$$

$$
= ( S _ { 1 } S _ { 2 } ) ( { \bmod { n } } ) \circ
$$

# 1.2.2效率分析

RSA公钥算法发展的最大瓶颈是大整数的模幂运算，目前RSA密码系统的模数 $n$ 已经可以到2048位，其算法效率必然会受到如此巨大的模数的影响。关于如何加快数据传输过程中的RSA算法的实现，目前有很多不同的算法被提出，比如Sliding window、modular repeat squaring 算法、基于乘同余对称特性和指数2k次方组合优化算法等[10]。文献[4]和[11]分别提出了一种在RSA 算法中对关键参数的离线存储和密钥脱机生成的方法，在一定程度上优化算法的运算效率，但程度很低。文献[12]使用四个素数因子，计算了一对公钥和私钥中的两个自然数，这两个自然数增加了密码体制的安全性，然而并没有从实验角度证明改进后算法的可行性与正确性。文献[13]综合使用对称密码算法AES-128和非对称密码算法RSA。AES-128算法在消息传递过程中保持数据消息的机密性和完整性，RSA算法来处理消息的认证性和不可否认性，在效率上也有比较优秀的表现。本文从算法运算效率的角度出发，将CRT融入四素数RSA算法，再将其运用到数字签名中。

# 2 RSA算法优化

# 2.1基于四素数的 RSA

对于相同的密钥位数，四素数RSA算法比传统RSA算法所要求产生的随机素数要小，还能够减少密钥生成的运算量。另外，素数因子越小，大整数因式分解就越便利。但是素数使用得越多，RSA算法的安全强度会越低。本文对比传统RSA算法，采用选取四个随机大素数的方法，其描述简述如下。

# 2.1.1密钥生成

随机产生四个不同的大素数 $\boldsymbol { p } , \boldsymbol { q } , \boldsymbol { r }$ 和 $s$ ，计算：

$$
n = p q r s ~ \not \exists \vdash \emptyset \left( n \right) = ( p - 1 ) ( q - 1 ) ( r - 1 ) ( s - 1 )
$$

2.1.2消息加密

$$
C = M ^ { \mathit { ^ { e } } } m o d ( n )
$$

2.1.3消息解密

$$
M = C ^ { d } m o d ( n )
$$

# 2.2中国剩余定理优化运算效率

中国剩余定理(Chinese remainder theorem,CRT)是中国古代求解一次同余式组的方法，也是初等数论中重要的基本定理之一。其内容为：设 $m _ { 1 } , m _ { 2 } , . . . , m _ { k }$ 是 $k$ 个两两互素的正整数,$a _ { 1 } , a _ { 2 } , . . . , a _ { k }$ 是 $k$ 个任意整数， $M = m _ { 1 } m _ { 2 } . . . m _ { k }$ ， $i = 1 , 2 , \cdots , k$ ，则同余数组 $x = a _ { i } { \bmod { m _ { i } } }$ 唯一解的表达式为 $x = \sum _ { i = 1 } ^ { k } a _ { i } M _ { i } b _ { i } ( { \mathrm { m o d } } M )$ 口其中， $b _ { i } M _ { _ i } = 1 { \bmod { m _ { i } } } , M _ { _ i } = M / m _ { _ i } , i = 1 , 2 , \cdots , k \circ$ （204

假设明文为 $M$ ，密文为 $C$ ，下面给出在RSA算法中应用中国剩余定理的具体过程：

计算 $M$ 的剩余

$$
\begin{array} { r } { \left( \begin{array} { l } { M _ { p } = C _ { p } ^ { \ d _ { p } } \bmod p } \\ { M _ { q } = C _ { q } ^ { \ d _ { q } } \bmod q } \\ { M _ { r } = C _ { r } ^ { \ d _ { r } } \bmod r } \\ { M _ { s } = C _ { s } ^ { \ d _ { s } } \bmod s } \end{array} \right) } \end{array}
$$

其中：C ${ \bf \dot { \theta } } _ { p } = C \mathrm { m o d } p \ , \ C _ { q } = C \mathrm { m o d } q \ , \ C _ { r } = C \mathrm { m o d } r \ , \ C _ { s } = C \mathrm { m o d } s$ ：$\begin{array} { l l l } { { d _ { p } = d \mathrm { m o d } ( p - 1 ) } } & { { , } } & { { d _ { q } = d \mathrm { m o d } ( q - 1 ) } } \\ { { } } & { { } } & { { { d _ { r } = d \mathrm { m o d } ( r - 1 ) } } } \\ { { } } & { { } } & { { { d _ { \theta } = d \mathrm { m o d } ( r - 1 ) } } } \end{array} ,$ ，$d _ { s } = d { \bmod { ( s - 1 ) } }$ 。

根据中国剩余定理，可得

$$
\begin{array} { r } { \left( \begin{array} { l } { M \equiv M _ { _ { p } } \bmod p } \\ { M \equiv M _ { q } \bmod q } \\ { M \equiv M _ { _ { r } } \bmod r } \\ { M \equiv M _ { _ { s } } \bmod s } \end{array} \right) } \end{array}
$$

可解得

${ \cal M } = ( M _ { p } ( q r s ) ^ { p - 1 } + M _ { q } ( p r s ) ^ { q - 1 } + M _ { r } ( p q s ) ^ { r - 1 } + M _ { s } ( p q r ) ^ { s - 1 } ) \mathrm { m o d } n ,$ 即为原明文 $M _ { \circ }$ （20

由上述过程可见，该定理的优势在于能把大整数的模幂运算转换成相对较小的数的模幂运算，在RSA算法应用CRT，能够降低消息解密时的运算量和复杂度。

# 2.3参数n的替换优化安全性

在传统RSA算法中，两个密钥都包含参数 $n$ ，这可以被分解为两个大素数。如果密码攻击者猜出 $n$ 的因素，就很容易得到私钥。为了克服1.2.1节所分析的针对参数 $n$ 攻击的这一弱点，本文在四素数CRT-RSA算法基础上，再试图消除两个密钥中 $n$ 的分布，用一种改变原模（两个素数乘积）的方法，即引入了一个新的参数 $x$ 代替原参数 $n$ ，使攻击者难以通过针对 $n$ 进行攻击。更改的模数值将被公开声明，这可能是假值。即使攻击者因式分解这种新的模值，他无法找到原来的解密密钥。无法找到原始解密密钥，分解是毫无价值的。至此，结合2.1和2.2节所述的优化方法，改进后的RSA算法同样包含三个步骤，即生成替换参数 $n$ 的密钥、消息加密和消息解密。

# 2.3.1密钥生成

选定四个任意的大素数 $\boldsymbol { p } , \boldsymbol { q } , \boldsymbol { r }$ 和 $s$ ，计算 $n = p q r s$ 和欧拉函数 $\phi \big ( n \big ) = ( p - 1 ) ( q - 1 ) ( r - 1 ) ( s - 1 ) ~ ,$

随机地选取一个正整数 $e$ ，使其满足 ${ \sqrt { n } } < e < \phi ( n )$ ，并且要求 $\mathbf { \Delta } _ { e }$ 和 $\phi ( n )$ 的最大公约数 $G C D ( e , \phi ( n ) ) = 1$ 。

计算 $x$ （用来代替 $n$ ），计算步骤如下：

如果 $q < p$ ，则定义 $x$ ： $( n - p ) < x < n$ ，G $C D \ ( x , n ) \ = \ 1$ ：

如果 $q > p$ ，则定义 $x$ ： $( n - q ) < x < n$ ， $G C D \ ( x , n ) \ = \ 1$

计算解密密钥 $\boldsymbol { \mathscr { d } }$ ，而且 $e d \equiv 1 ( m o d ~ \phi ( n ) )$ 。此时，公钥为$( e , \ x )$ ，私钥为 $( d , \ x )$ 。

2.3.2消息加密

消息发送方使用 $( e , \ x )$ 对明文 $M$ 进行加密：

$$
C = M ^ { \mathit { ^ { e } } } \mathrm { m o d } ( x )
$$

# 2.3.3消息解密

消息接收方使用 $( d , \ x )$ 对密文 $C$ 进行解密：

$$
M = C ^ { d } { \bmod { ( } } x )
$$

改进RSA算法流程如图1所示。

# 3 实验结果及分析

实验在i5-2450MCPU，6GB内存和Windows64位系统下选用MATLABR2016a工具进行，在算法实现关键步骤中，素性检测采用最成熟的Robin-Miller检测法，用中国剩余定理CRT 的算法来实现大整数模取幂的运算，求解解密密钥 $d$ 时的模逆运算采用费马小定理： $\boldsymbol { a }$ 是整数， $p$ 是素数，且 $\mathbf { \Delta } _ { a }$ 和 $p$ 互素，即 $G C D ( a , p ) = 1$ ，恒有 $a ^ { p - 1 } { \bmod { p } } = 1$ 。进而 $a ^ { - 1 } = a ^ { p - 2 } { \bmod { p } }$ 将模逆运算用多项式运算来替代，在原算法基础上进一步优化运算的效率。通过对比文献[14]中散列函数MD5、SHA-160,SHA-256和SHA-512，本实验中采用SHA512。

![](images/266d04748c9522a383b96c8447cad1f970b4f5c83214e1e750e4ddd98ec63273.jpg)  
图1改进RSA算法流程

本实验中，将传统RSA算法改进为融入CRT的四素数RSA算法，并用一个新的参数 $x$ 代替原本公开的 $n$ 进行了保密处理，通过生成两组随机素数进行对比，加密后的密文无法被识别，很好地保护消息的安全性，证实这种改进RSA算法能取得良好加/解密效果。

改进RSA算法效果如图2所示。

一种针对标准RSA算法的改进方案  
Key (Bits)关于明文RSA是目前最有影响力和最常 随机素数用的公钥加密算法，它能够抵 p（保密） 15101抗到目前为止已知的绝大多数 q（保密） 15349密码攻击，已被ISO推荐为公 q（保密） 16087钥数据加密标准。s（保密） 16319密文204236611533900314826334 加密指数002094770173407781010863 e（公开） 6074567574704900590116431679700400857226 参数x104750832696913409257601x（公开） 8577385747906356631118042839555818213072私钥解密后的明文 d（保密） 6794403878615927RSA是目前最有影响力和最常用的公钥加密算法，它能够抵抗到目前为止已知的绝大多数密码攻击，已被ISO推荐为公 参数生成 加密(E) 解密(D)钥数据加密标准。

本文用Robin-Miller算法分别生成256bit、512bit和1024bit素数，然后让传统RSA、传统四素数算法和改进后的算法分别在位大小变化的情况下进行测试。

# 3.1 密钥生成时间对比

算法的密钥生成时间如表1所示。由表中三种算法生成密钥所耗时间对比可知：256bit时改进算法的密钥生成速度是传统RSA算法1.68倍；512bit时为1.73倍；1024bit时达到1.81倍。虽然改进算法相比传统四素数RSA算法耗时有所增加，但比起改进算法在安全性方面所做贡献而言微不足道，本文将在3.3节加以分析。为了更加直观地观察两种算法效率，将两种算法所耗时间放在图3中进行对比（下同）。

表1算法生成密钥耗时情况  

<html><body><table><tr><td rowspan="2">时间/ms</td><td rowspan="2">传统RSA算法 生成密钥</td><td rowspan="2">四素数RSA算法</td><td rowspan="2">改进RSA算</td></tr><tr><td>生成密钥 法生成密钥</td></tr><tr><td>256 bit</td><td>3128</td><td>1784</td><td>1855</td></tr><tr><td>512 bit</td><td>9 319</td><td>5235</td><td>5368</td></tr><tr><td>1024 bit</td><td>75 701</td><td>39 472</td><td>41 736</td></tr></table></body></html>

![](images/7ae5ec10b9886a2faeb23d94aed9c5953e259a286e0126f6c5889d4de61fdf01.jpg)  
图3算法密钥生成时间对比

# 3.2算法解密时间对比

三种算法的解密时间如表2所示。对比所耗时间可知，256bit情况下，改进后的算法解密速度达到了传统RSA算法的5.88倍；512bit时为9.85倍，与理论值10.86倍接近；1024bit时达到10倍。对比改进算法与四素数RSA算法，其速度也有大幅度提升。算法解密时间对比如图4所示。

表2算法解密耗时情况   

<html><body><table><tr><td rowspan="2">时间/ms</td><td>传统RSA</td><td>四素数RSA</td><td>改进RSA</td></tr><tr><td>算法解密</td><td>算法解密</td><td>算法解密</td></tr><tr><td>256 bit</td><td>459</td><td>201</td><td>78</td></tr><tr><td>512 bit</td><td>3261</td><td>1020</td><td>331</td></tr><tr><td>1024 bit</td><td>24 783</td><td>8182</td><td>2 469</td></tr></table></body></html>

![](images/8cc0f1c8015d36ba4d7d68d8cfca9de519f55453db986c430cd0c054de76941b.jpg)  
图2改进RSA算法效果  
图4算法解密时间对比

# 3.3 Brute-force攻击时间对比

为了对大整数 $n$ 因式分解，采用基于椭圆曲线的分解算法（ECM）和一般数域筛法（GNFS）相结合的方法。ECM通常用于小整数因式分解，而GNFS能够分解位数大于100的大整数。实验分别对对三种算法采用暴力攻击（brute-force），所耗时间如表3所示。从表中可以看出，生成16bit素数情况下，传统算法暴力分解参数 $n$ （改进算法中替换为 $x$ 需要78.676s，四素数RSA算法需要 $1 2 6 . 4 9 8 \mathrm { ~ s ~ }$ ，而改进算法中则需要243.95s。改进算法被暴力分解的所需时间是传统RSA算法的3.1倍，是四素数RSA算法的1.93倍。可以推断，当比特更高时，传统RSA算法与改进算法耗时的差距会更大。由此可见，改进后的算法有助于克服RSA中参数 $n$ 易被因式分解攻击的弱点。Brute-force攻击时间对比如图5所示。

表3Brute-force 攻击耗时情况  

<html><body><table><tr><td rowspan="2">时间/s</td><td>传统RSA算</td><td>四素数RSA算法</td><td>改进算法</td></tr><tr><td>法 Brute-force</td><td>Brute-force</td><td>Brute-force</td></tr><tr><td>8 bit</td><td>1.564</td><td>6.383</td><td>13.894</td></tr><tr><td>10 bit</td><td>6.151</td><td>19.578</td><td>35.204</td></tr><tr><td>16 bit</td><td>78.676</td><td>126.498</td><td>243.95</td></tr></table></body></html>

![](images/9dd1332afe7494a90e3dfb4b9addfec4270c0e95d62e008b69fad57d66a7bdb2.jpg)  
图5Brute-force 攻击时间对比

# 4 结束语

针对RSA公钥算法攻击最直接的方法是对模数 $n$ 进行素因子分解，本文在讨论算法可优化性的基础上，提出了一种改进的RSA公钥算法，在四素数算法中融入中国剩余定理，并消除原始RSA算法中的参数 $n$ ，添加一个新的参数 $x$ 替换私有和公钥中的 $n$ ，并通过实验验证了提出的RSA算法的有效性。同时，针对生成的256bit、512bit和1024bit素数分别用标准RSA、四素数RSA算法和改进RSA算法进行实验，记录算法的密钥生成时间和解密所耗的时间。实验结果显示，改进RSA算法的签名时间大幅降低，提高了算法签名的效率，比传统RSA算法具有一定的优势。用Brute-force攻击8bit、10bit和16 bit时的参数 $n$ ，对比三种算法的被攻破时间，改进算法所消耗的时间显然长于其他两种算法。结果表明改进算法在提高签名速度的同时还提高了算法的安全性，证明了基于多素数和替换参数 $n$ 的改进RSA算法的优越性和实用性。在今后的实验和应用中使用该改进算法提高RSA系统的安全系数和运算速度，使RSA 算法得到进一步发展。

参考文献：   
[1] Chhabra A,Mathur S.Modified RSA algorithm: a secure approach[C]//Proc of International Conference on Computational Intelligence and Communication Networks.Gwalior, India: IEEE Press, 2011: 545-548.   
[2] 肖振久，胡驰，陈虹．四素数 RSA 数字签名算法的研究与 实现[J]．计算机应用,2013,33(5):1376-1377.   
[3]Arora S, Pooja. Enhancing cryptographic security using novel approach based on enhanced-RSA and elamal: analysis and comparison[J].International Journal of Computer Applications, 2015,112 (13): 35-39.   
[4] Al-Hamami A H,Aldariseh IA. Enhanced method for RSA cryptosystemalgorithm[C]//AdvancedComputerScience Applications and Technologies. Kuala Lumpur, Malaysia: IEEE Press,2013: 402-408.   
[5] Sahu J, Singh V, Sahu V, et al. An enhanced version of RSA to increase the security[J]. Journal of Network Communications and Emerging Technologies,2017,7(4): 1-4.   
[6] Thangavel M, Varalakshmi P,Murrali M, et al. Comment on an enhanced and secured RSA key generation scheme (ESRKGS)[J]. Journal ofInformation Security & Applications,2015,20 (C): 3-10. [7] Rivest R, Shamir A, Aldeman L. A method for obtaining digital signatures and public-key cryptosystems[J]. Communications of the ACM,1978,21(2): 120-126.   
[8] 冯登国，赵险峰．信息安全技术概论[M]．北京：电子工业 出版社,2012:30-32.   
[9] 李家兰.RSA 算法的攻击方法研究[J]．科技视界,2015(2): 50.   
[10] 何俊杰，焦淑云，祁传达．一个基于身份的签密方案的分 析与改进[J]．计算机应用研究,2013,30(3):913-916,920.   
[11] Nagar S A, Alshamma S. High speed implementation of RSA algorithm with modified keys exchange[C]//Proc of the 6th International Conference on Sciences of Electronics, Technologies of Information and Telecommunications.Sousse， Tunisia: IEEE Press,2012: 639-642.   
[12]Mahaveerakannan R, Dhas C S G. Customized RSA public key cryptosystem using digital signature of secure data transfer natural 22 number algorithm[J]. International Journal of Computer Technology & Applications,2016,9(5): 2627-2632.   
[13] Siregar H,Junaeti E, Hayatno T. Implementation of digital

signature using aes and rsa algorithms as a security in disposition system af letter[J].Materials Science and Engineering,2017, 180(1):12-55.

[14]Mansour AH.Encryption and decryption analysis of the RSA digital signature based on MD5 and SHA hash functions using strong prime[J]. Journal of Soft Computing and Decision Support Systems,2017,4(1): 7-15.