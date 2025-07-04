# 一种基于海绵函数的快速伪随机序列生成方法

赵磊ab，郑东ab，任方a,b

(西安邮电大学 a.通信与信息工程学院;b.无线网络安全技术国家工程实验室，西安 710121)

摘要：海绵函数使用较短的密钥和初始向量，因而作为一种新型的伪随机生成器结构被使用。针对 Meziani等人提出的2SC（sponge code-based streamcipher）伪随机序列生成方法效率低、速度慢等问题，结合编码理论，提出了一种基于海绵函数的快速伪随机序列生成方法。使用一个通用的状态转换将其安全性归约为正则校验子译码问题，但是其计算能力相比于正则编码更好。理论分析和实验结果表明，该伪随机序列生成器保留了海绵函数的特性，但是效率大大提高。对于160bits的安全级别，其速度比原方案提高到了5倍以上。同时NIST统计测试及序列的平衡度、互相关性等测试结果表明生成的伪随机序列具有良好的随机特性。

关键词：海绵函数；伪随机序列；编码理论；正则字；校验子译码 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2018.05.0451

# Fast pseudo-random sequence generation method based on sponge function

Zhao Leia, b, Zheng Donga,b, Ren Fanga, bt (a.SchoolofTelecommunication&InformationEngineering,b.NationalEngineeringLaboratoryforWirelessecurityXi’an University ofPosts& Telecommunications,Xi'an 710121,China)

Abstract: The spongefunction uses shorter keysand initial vectors,so it isused asanew pseudo-random generatorstructure. This paper proposeda fast pseudo-random sequence generation methodbasedonspongy function incombination withthecoding theory,to solve the problemsoflow eficiency and slow speed of 2SC(sponge code-based streamcipher）pseudo-random sequencegeneration method proposed by Meziani et al.uses a generic state transformation which is reducible tothe Regular SyndromeDecoding problem(RSD),buthasbetercomputational characteristics thantheregularencoding.Theoreticalanalysis andexperimentalresults showthatthe pseudo-random sequence generator preserves thecharacteristics ofsponge function,but itimproved theeficiency greatly.Forthesecuritylevelof16obits,its 5times faster thantheoriginal scheme.At thesame time,NISTstatisticaltest,squencebalanceandcrosscorelationtestresultsshowthatthegenerated pseudo-randomsequence has good random characteristics.

Key words: sponge function; pseudo-random sequence; coding theory; regular word; syndrome ddecoding

# 0 引言

密码技术是网络安全的根基。在网络行为已经渗透到社会生活每个领域的今天，无论是网上银行、电子商务还是电子邮件、即时消息服务，密码技术无时无刻不在保护着用户的信息安全。流密码[1]作为一种主流的加密方式，加解密实现方式简单、速度快、理论相对成熟，因而在许多实际中应用，特别是无线通信标准，如IEEE802.11b和蓝牙。伪随机序列常作为流密码的密钥流，与待加密的明文流进行简单的“异或”运算得到密文流。这是一种“一次一密”的加密方式，能够得到最高的安全性一完善保密性。因而密钥流的生成成为了流密码算法的关键，当前，主要的密钥流生成器都是基于伪随机数生成器设计和实现的，因此设计性能良好的伪随机数发生器（pseudo-randomnumberGenerator，PRNG）已经成为密码学领域的一个研究热点[2-3]。

作为在流密码中的应用，伪随机序列不仅需要具备良好的统计特性和有效性，同时需要可证明安全的伪随机序列生成器，即需要把伪随机序列的安全性规约到特定的困难问题上。在已有的伪随机序列生成方法中，基于线性反馈移位寄存器（linearfeedbackshiftregister,LFSR）的生成方法是常见的方法之一，然而存在许多安全弱点，线性复杂度低。为了抵抗攻击，在20 世纪80 年代初，BIum[4]等人提出了基于大整数分解问题的可证明安全的伪随机序列生成器，随后，Kaliski[提出了另一种方案其安全性依赖于离散对数问题的难解性。Alexi等人[6提出了基于RSA问题的可证明安全的伪随机序列生成方法。

尽管上面所提到的伪随机序列生成方法是可证明安全的，但它们在量子攻击[7下都将失去原有的安全性。因此，设计基于其他假设的伪随机数生成器显得尤为重要，这也是近年来抗量子密码技术研究的方向之一。最早提出抗量子攻击的伪随机序列生成器是Impagliazzo 等人[8],提出了基于子集和问题的可证明安全的伪随机序列生成方法。之后，Fisher 和Stern[提出了一种基于校验子译码(SD)问题的伪随机序列生成器，但是存在两个缺陷：运算速度慢，用于计算校验子的矩阵占用内存大，因此难以得到应用。Gaborit[10]等人在2007年提出了新的方案，称为SYND,是对文献的一种改进，并将其安全性规约到 SD问题。2011年，Meziani[11]等人利用海绵结构提出了一种新的基于校验子译码问题的伪随机序列生成方法，称为2SC。这种密码结构相比于SYND，在性能指标上更加有效，而且只需小的密钥大小和初始向量就可以获得较高的安全级别。但是其最大的缺点是需要大的矩阵。2016年，Gaborit[12]等人基于RankMetric码的校验子译码问题的困难性构造了一种伪随机序列生成器。

本文重新考察了由Meziani等人提出的2SC方案，提出了一种对2SC改进的高效算法。保留了海绵结构，使得密钥和初始向量较短。相比于 2sc，本文摒弃了将码字编码为正则字[13]的过程，而使用哈希算法中压缩函数的构造思想，将其转换为一种可以规约为正则字校验子译码问题的编码方式。从而使得伪随机序列生成速度更快。

# 1 编码理论

本节主要回顾了基于编码的密码学基础，简单描述了编码理论中的常见困难问题，最后介绍了基于编码的哈希函数。

# 1.1线性分组码

有限域 $F _ { q }$ 上的一个 $\scriptstyle { \left( n , k \right) }$ 线性分组码 $c$ 定义为 $n$ 维线性空间 $F _ { q } ^ { n }$ 的一个 $k$ 维线性子空间。其中 $F _ { q } ^ { n }$ 中的向量称为字，而 $C$ 中的向量称为码字(codeword)， $n$ 称为分组码的码长， $k$ 称为分组码的维数。

定义1一个 $\scriptstyle { \left( n , k \right) }$ 线性分组码 $C$ 的生成矩阵是一个 $k \times n$ 的矩阵 $G$ ，其中 $G$ 的行向量构成了 $c$ 的一组基。

线性分组码 $c$ 的生成矩阵 $G$ 不唯一，但是不同的生成矩阵可以通过初等行变换相互转换，即若 $G$ 是 $c$ 的一个生成矩阵，$P$ 是一个初等矩阵，则 $P G$ 也是 $c$ 的一个生成矩阵。

定义2一个 $\scriptstyle { \left( n , k \right) }$ 线性分组码 $c$ 的校验矩阵是一个$\left( n - k \right) \times n$ 的矩阵 $H$ ，其中 $H$ 的任意行向量与 $c$ 的生成矩阵 $G$ 的任意行向量正交，即 $H G ^ { \mathrm { T } } = 0$ 。

线性分组码的校验矩阵不唯一且可以通过初等行变换相互转换。长为 $n$ 的向量 $\boldsymbol { c }$ 是 $C$ 的一个码字的充分必要条件是$H c ^ { \mathrm { T } } = 0$ 。对于任意的字 $c$ ，将 $H { { c } ^ { \mathrm { { T } } } }$ 称为 $c$ 的校验子。

定义3线性分组码的两个码字， $u = { \big ( } u _ { 1 } , u _ { 2 } , \cdots , u _ { n } { \big ) }$ ，$\nu = \left( \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { n } \right)$ 的 Hamming距离 $d \big ( u , \nu \big )$ 定义为 $u$ 和 $\nu$ 的不同分量的个数，即 $d \big ( u , \nu \big ) { = } | \{ i : u _ { i } \neq \nu _ { i } \} |$ 。

码字 $u$ 的 Hamming重量 $w ( u )$ 定义为 $u$ 的非零分量的个数，码 $c$ 的非零码字的最小Hamming 重量称为 $c$ 的最小距离，记作 $d _ { \operatorname* { m i n } }$ 。码的最小距离决定了码的纠错能力，一般来说，线性分组码的纠错能力 $t$ 满足。

定义4给定长度为 $n$ 重量为 $w$ 的字 $x$ ，将其转换成 $w$ 个长度为 $n / w$ 的块，每一块都有固定的“1”，称这样的码字为正则字。

# 1.2 困难问题

在基于编码的密码学中，其安全性大多都规约到以下困难问题中。

Q1校验子译码问题(Syndrome Ddecoding,SD)

给定有限域 $F _ { q }$ 上的一个 $\left( n - k \right) \times n$ 的矩阵 $H$ ，向量（204号 $s \in F _ { q } ^ { n - k }$ ，整数 $w > 0$ ，问是否存在一个字 $x \in F _ { q } ^ { n }$ ，其重量小于等于 $w$ ，使 $H x ^ { \mathrm { T } } = s$ 。

Q2寻找码字问题(Codeword Finding,CF)

给定有限域 $F _ { q }$ 上的一个 $\left( n - k \right) \times n$ 的矩阵 $H$ ,整数 $w > 0$ ，问是否存在一个非零的字 $x \in F _ { q } ^ { n }$ ，其重量小于等于 $w$ ，使$H \boldsymbol { x } ^ { \mathrm { { T } } } = 0$ 9

SD问题和CF问题在文献[14]中已被证明是NP-完全问题。SD 问题的一个特例就是RSD问题，该问题在文献[13]中证明为NP-完全问题，具体描述如下。

Q3正则校验子译码问题(Regular SyndromeDecoding,RSD)

给定有限域 $F _ { q }$ 上的 $w$ 个 $\left( n - k \right) \times n / w$ 矩阵 $H _ { i }$ ，向量（204 $s \in F _ { q } ^ { n - k }$ ，整数 $w > 0$ ，问是否存在 $w$ 个向量 $h _ { i } , h _ { i }$ 是 $H _ { i }$ 的列向量，使 $s$ 等于这些向量之和。

# 1.3基于编码的 Hash 函数构造

Hash函数的构造中，最核心的部分是压缩函数 $g$ 。基于编码困难问题的压缩函数 $g$ 的构造方法如下。

随机选择一个 $\left( n , k \right)$ 码字 $x$ ，其中：

$$
n = 2 ^ { m } , k = n - m t
$$

选择正整数 $w | n$ ，显然有

$$
w = 2 ^ { m ^ { \prime } } ( m ^ { \prime } < m )
$$

另取

$$
l = \frac { n } { w } = 2 ^ { m - m ^ { \prime } }
$$

则可以将长度为 $n$ 的每一个字分成等长的 $w$ 个块，每一块包含 $l$ 个比特。

随机选取一个 $\left( n - k \right) \times n$ 的校验矩阵 $H$ ,可以将 $H$ 分成 $w$ 个子矩阵，即

$$
H = \left( H _ { 1 } , H _ { 2 } , \cdots H _ { w } \right)
$$

其中每一个子矩阵

$$
H _ { i } = \left( h _ { j } \right) ( i = 1 , 2 , \cdots w ; j = ( i - 1 ) l + 1 , ( i - 1 ) l + 2 , \cdots i l )
$$

$h _ { j }$ 为矩阵 $H$ 的第 $j$ 列。

定义压缩函数

$$
\begin{array} { r l } { g : } & { { } F _ { 2 } ^ { e } \to F _ { 2 } ^ { r } , } \end{array}
$$

$$
e = w \log _ { 2 } ^ { l } , r = n - k = m t
$$

对于任意的 $x \in F _ { 2 } ^ { e }$ ，将 $x$ 也按照上述的划分方法分成 $w$ 个块，即 $x = \left( x _ { 1 } , x _ { 2 } , \cdots , x _ { w } \right)$ ，其中 $x _ { i } \in F _ { 2 } ^ { \log _ { 2 } ^ { l } }$ ，将 $x _ { i }$ 转换成0至l-1之间的数，选择矩阵 $H _ { i }$ 的第 $x _ { i } + 1$ 列，即 $h { \big ( } i - 1 { \big ) } l + x _ { i } + 1$ ，计算$z = \sum _ { i = 1 } ^ { w } h \big ( i - 1 \big ) l + x _ { i } + 1$ ，则函数的输出：

$$
g \left( x \right) = z
$$

定理1上述的压缩函数 $g$ 的输出等价于计算一个长为 $n$ ，重量为 $w$ 的正则字的校验子，即对于任意的 $g ( x )$ ，存在正则字$\boldsymbol { c }$ ，使得 $H c ^ { \mathrm { T } } = g ( x )$ 。证明参考文献[15]。

# 2 基于Sponge函数的伪随机序列生成方法-2SC

# 2.1Sponge 函数 (海绵函数）

Sponge 函数最先由Peeters等人在文献[16]提出，它为迭代哈希函数设计提供了一种新的方法。它使用有限的状态，接收任何长度的输入位元流，然后可以满足任何长度的输出。

Sponge 函数由三个部分组成，如图1所示。

a）一个内存状态 $s$ ，包含 $s$ 个位元。内存状态会分成两个区块， $R$ （大小为 $r$ 位元）与 $c$ （大小为 $c = s - r$ 位元)。这里的参数 $r$ 又叫做转换率（bitrate），而 $c$ 叫做容量（capacity）。

b)一个能置换或者转换内存状态，固定大小的转换函式 $f$ 。

c）一个填充函数（paddingfunction） $P$ 。填充函式会在输入里面增加足够的长度，让输入的位元流长度变成 $r$ 的整数倍。因此填充过后的输入可以被切成长度为 $r$ 的整数个分段。

Sponge 函数的具体运行过程如下：

a） $s$ 先初始化为零。b）输入经过填充函式处理。c）填充后输入的前 $r$ 个位与 $R$ 进行异或运算。d） $s$ 经过函式 $f$ 转换成 $f ( S )$ 。e）如果填充后输入还有剩余，下一 $r$ 位则与上一步 $R$ 进行异或运算。f） $s$ 转换成 $f ( S )$ 。

：

这个过程一直重复到所有的输入都用完为止，称为absorbing阶段。（在海棉的譬喻里面，表示被函数“吸收”了）。

输出块 $Z _ { i }$ 的数量由用户选择，这一阶段称为 squezzing 阶段（“挤出”)，具体过程如下：

a）通过absorbing阶段得到新的内存状态，此时 $R$ 表示输出的前 $r$ 个位元。b）如果需要更多输出，则把 $s$ 转换成 $f ( S )$ 。c）此时 $R$ 则表示输出的下 $\boldsymbol { r }$ 个位元。

这一过程会重复到满足输出所需要的长度为止。需要注意的是，输入绝对不会与 $c$ 这部分的内存作异或运算，而且这一部分内存也不会直接被输出。这一部分的内存仅仅只和转换函式相关。在杂凑里面，防止撞击攻击(Collisionattack)或者原像攻击(preimage attack)是依靠这段内存做到的。

![](images/a3b104746f2a5545b3007946d0f78e81208600788212b362d2fd860a7515311c.jpg)  
图1 Sponge 函数结构  
Fig.1Sponge function structure

# 2.2 2sc方案结构

基于上节所提到的Spange 函数，Meziani等人设计了一种伪随机序列生产方法。令 $K$ 和 $I V$ 分别表示密钥和初始向量，并且 $r = \left| K \right| = \left| I V \right|$ ，内部状态 $s$ 的大小 $s = w \log 2 { \big ( } n / w { \big ) }$ ，其中$n > w , n / w = 2 ^ { l } \circ$ （20

Initialization初始化函数 $f$ 通过输入密钥 $K$ 和初始向量$I V$ ，计算并且返回初始状态，定义如下：

$$
f : F _ { 2 } ^ { | k | } \times F _ { 2 } ^ { | I V | }  F _ { 2 } ^ { s }
$$

$$
\left( x _ { 1 } , x _ { 2 } \right) \right. f \left( x _ { 1 } , x _ { 2 } \right) = f _ { 1 } \left( \left( f _ { 1 } ^ { \left[ r \right] } \left( x _ { 1 } \left| 0 ^ { c } \right) \oplus x _ { 2 } , f _ { 1 } ^ { \left[ c \right] } \left( x _ { 1 } \left| 0 ^ { c } \right) \right| \right) \right)
$$

其中：“|”表示级联，“ $0 ^ { c }$ ”是大小为 $\boldsymbol { c }$ 的全零向量。 $f _ { 1 } ^ { [ r ] }$ 表示 $f _ { 1 } ( \cdot )$ 的前 $r$ 位比特， $f _ { 1 } ^ { [ c ] }$ 表示 $f _ { 1 } ( \cdot )$ 的剩余 $c$ 位比特。校验子映射 $f _ { 1 }$ 定义如下：

$$
x  f _ { 1 } ( x ) = \phi ( x ) { \cdot } H _ { 1 } ^ { T }
$$

这里，函数 $x \to \phi ( x )$ 指正则编码，将 $s$ 位的字符串转换成长度为 $n$ 和重量为 $w$ 的正则字。矩阵 $H _ { 1 }$ 是大小为 $s \times n$ 的二元随机矩阵，该初始化步骤需要计算两个函数并进行两个异或运算。因此，当每个安全级别选择最优参数 $\left( n , s , w \right)$ ，那么比SYND方案更加有效。通过初始化过程得到初始状态 $e _ { 0 }$ 。

Update 在此步骤中，将使用一个新的随机函数 $g$ 来更新内部状态(比如 $N$ 次)。 $g$ 运行的次数是由用户选择的，更新的次数也因此影响着结构的安全性和效率。函数 $g$ 的定义如下:

$$
g : F _ { 2 } ^ { s } \to F _ { 2 } ^ { s }
$$

$$
x  g ( x ) = \phi ( x ) \cdot H _ { 2 } ^ { T }
$$

其中: $H _ { 2 }$ 同样是一个 $s \times n$ 的二元随机矩阵，函数 $x \to \phi ( x )$ 指正则编码，与初始化步骤中的过程相同。

Squeezing通过更新过程得到 $e _ { i }$ ，2SC 最终产生每组大小为 $r$ 比特密钥流 $z _ { i } ( i \geq 1 )$ ，描述如下：

a) $z _ { 1 } = g { \left( e _ { 0 } \right) } ^ { \left[ r \right] }$ ,表示初始状态 $\boldsymbol { e } _ { 0 }$ 经过更新函数得到新的内部状态 $\boldsymbol { e } _ { 1 }$ ， $\boldsymbol { e } _ { 1 }$ 的前 $r$ 位输出即为 $z _ { 1 }$ 。

b)对于 $i \geq 2$ ， $e _ { i } = g \big ( e _ { i - 1 } \big )$ ,其中 $\boldsymbol { e } _ { i }$ 是更新状态下 $g$ 的 $i$ 次迭代的输出。

上述所描述的结构如图2所示。

# 3 一种基于海绵函数的快速伪随机序列生成方法

在实验仿真过程中发现上节所介绍的伪随机序列生成方法在正则编码 Niederreiter 变换[17]，即 $x \to \phi ( x )$ 过程中需要消耗大量时间，因此希望通过另一种编码方式将其性能提高，同时不降低安全性。基于编码的哈希函数的构造方法思想将上述方案进行改进，具体描述如下。

![](images/fa0274e24396f9d181d12dfc64c6e97174c99a2da945f05b50fc98c540588fd5.jpg)  
图22SC密钥流生成器结构图Fig.22SC key stream generator

给定输入 $x$ ，由 $w$ 块 $x _ { 1 } , x _ { 2 } , \cdots , x _ { w }$ 组成， $x _ { i }$ （ $1 \leq i \leq \nu$ ）的大小为 $b$ 比特，本文首先通过函数 $f$ 来给每个块提供数据，得到输出 $y _ { i }$ ，将 $y _ { 1 } , y _ { 2 } , \cdots , y _ { w }$ 进行异或运算最终得到输出。结构如图3所示。

![](images/7be6f5f2cfbf6bdd0566f129fdbfc491bc32cbc3a5523f2efeb00dc8f065ff9b.jpg)  
图3 $f \left( x \right)$ 函数结构  
Fig.3 $f ( x )$ function structure

$f$ 函数具体描述为：选取大小为 $w b \times 2 ^ { b }$ 的二元随机矩阵$\textstyle H _ { 1 }$ ，将其分成 $w$ 个大小为 $w b \times 2 ^ { b }$ 子矩阵 $H _ { 1 } , H _ { 2 } , \cdots , H _ { w }$ （ $H = H _ { 1 } \vert H _ { 2 \vert } \vert \cdots \vert H _ { w } \ )$ ，子矩阵 $H _ { i } = \left( h _ { i } ^ { ( 0 ) } , h _ { i } ^ { ( 1 ) } , \cdots , h _ { i } ^ { ( 2 ^ { b } - 1 ) } \right)$ 中， $h _ { i } ^ { ( j ) } \in F _ { 2 } ^ { w b }$ ， $j \in \{ 0 , 1 , \cdots , 2 ^ { b } - 1 \}$ 。令 $x _ { i }$ 的十进制等于 $j$ ，那么 $x _ { i }$ 通过函数 $f$ 得到 $y _ { i } = h _ { i } ^ { ( j ) }$ ，每一个 $y _ { i }$ 则有 $2 ^ { b }$ 种可能，按照上述方法重新定义了函数 $f _ { 1 }$ 和函数 $g$ ：

$$
f _ { 1 } \left( x \right) = a _ { 1 } ^ { ( x _ { 1 } ) } \oplus a _ { 2 } ^ { ( x _ { 2 } ) } \oplus \cdots \oplus a _ { w } ^ { ( x _ { w } ) }
$$

$$
g \big ( x \big ) = b _ { 1 } ^ { ( x _ { 1 } ) } \oplus b _ { 2 } ^ { ( x _ { 2 } ) } \oplus \cdots \oplus b _ { w } ^ { ( x _ { w } ) }
$$

其中： $A$ 和 $B$ 是大小为 $w b \times w \cdot 2 ^ { b }$ 的二元随机矩阵， $A _ { i }$ 和 $B _ { i }$ 分别是 $A$ 和 $B$ 的子矩阵， $a _ { i } ^ { ( j ) }$ 则表示矩阵 $A$ 的第 $i$ 个子矩阵的第$j + 1$ 列， $b _ { i } ^ { ( j ) }$ 则表示矩阵 $B$ 的第 $i$ 个子矩阵的第 $j + 1$ 列。

通过以下的一个例子将上述的方法展示。首先，令 $w = 3$ ，$b = 2$ 。矩阵 $A$ 则是 $( 3 \cdot 2 ) { \times } ( 3 \cdot 2 ^ { 2 } ) { = } 6 { \times } 1 2$ 阶矩阵。随机选取一个符合上述要求的矩阵 $A$ 如下：

$$
A = \left[ \begin{array} { c c c c c c c c c c } { \frac { a _ { 1 } ^ { ( 0 ) } a _ { 1 } ^ { ( 1 ) } a _ { 1 } ^ { ( 2 ) } a _ { 1 } ^ { ( 3 ) } | a _ { 2 } ^ { ( 0 ) } a _ { 2 } ^ { ( 1 ) } a _ { 2 } ^ { ( 2 ) } a _ { 2 } ^ { ( 2 ) } a _ { 2 } ^ { ( 3 ) } | a _ { 3 } ^ { ( 0 ) } a _ { 3 } ^ { ( 1 ) } a _ { 3 } ^ { ( 2 ) } a _ { 3 } ^ { ( 3 ) } } { 1 } } \\ { 1 } & { 0 } & { 1 } & { 0 } & { 1 } & { 0 } & { 1 } & { 1 } & { 0 } & { 1 } \\ { 0 } & { 0 } & { 1 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 1 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 1 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 0 } & { 0 } & { 1 } & { 1 } & { 1 } \\ { 1 } & { 0 } & { 0 } & { 1 } & { 1 } & { 1 } & { 1 } & { 1 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 1 } & { 0 } & { 1 } & { 1 } & { 0 } & { 1 } & { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 1 } & { 0 } & { 0 } & { 0 } & { 1 } \end{array} \right]
$$

假设输入 $x = \left[ 1 0 | 0 1 | 0 0 \right]$ ，将 $x$ 分成 $w$ 组并表示为十进制,则 $x ^ { \prime } { = } \left[ 2 1 0 \right] .$ 根据公式 $z _ { i } = ( x _ { i } + 1 ) + ( i - 1 ) 2 ^ { b }$ ，计算得到 $z _ { 1 } = 3$ ，$z _ { 2 } = 6$ ， $z _ { 3 } = 9$ 。在二进制记数法中， $z _ { i }$ 表示Z的非零项的位置，即 $z = \left[ 0 0 1 0 \left| 0 1 0 0 \right| 1 0 0 0 \right]$ 。因此可以验证：

$$
g \big ( x \big ) = a _ { 1 } ^ { ( 2 ) } \oplus a _ { 2 } ^ { ( 1 ) } \oplus a _ { 3 } ^ { ( 0 ) } = \big [ 0 0 1 1 1 1 \big ] ^ { T } = A \cdot z ^ { T }
$$

# 4 安全性分析

本章将从两个角度来分析该算法的安全性。在理论上，很难逆向恢复出密钥 $K$ 和初始向量 $I V$ ；而在实际攻击中，需要敌手解决 SD 问题，目前已知的有两种可以有效的针对 SD 问题的攻击：信息集译码攻击（ISD)和广义的生日攻击（GBA)。

# 4.1理论安全性

由第3节所描述的转换函数 $f _ { 1 } ( x )$ 和 $g { \big ( } x { \big ) }$ ，定义一个通用的函数 $D$ ：

$$
D \big ( \boldsymbol { x } \big ) = a _ { 1 } ^ { ( x _ { 1 } ) } \oplus a _ { 2 } ^ { ( x _ { 2 } ) } \oplus \cdots \oplus a _ { w } ^ { ( x _ { w } ) }
$$

$$
\forall x = \left( x _ { 1 } , x _ { 2 } , \cdots , x _ { w } \right) \in F _ { 2 } ^ { w b }
$$

在这个转换过程中， $A$ 是大小为 $w b \times w \cdot 2 ^ { b }$ 的二元随机矩阵， $A _ { i }$ 是 $A$ 的子矩阵， $a _ { i } ^ { ( j ) }$ 则表示矩阵 $A$ 的第 $i$ 个子矩阵的第 $j + 1$ 列（ $j = 0 , 1 , \cdots 2 ^ { b } - 1 \rangle$ 。需要证明两点：

a）对于每一个输入码字 $x$ ，存在一个正则字Z，使得$D ( x ) = A \cdot z ^ { T } \ ,$

b）由 $y = D ( \boldsymbol { x } )$ 求解 $x$ 等价于寻找一个正则字z，重量小于或等于 $w$ ，使得 $\boldsymbol { A \cdot z } ^ { T } = \boldsymbol { y }$ 。这正是RSI $) \left( n , r , w \right)$ 对 $r = w b$ 和 $n = w 2 ^ { b }$ 的实例化。因此，改进后方案的安全性可以规约到RSD 问题。

证明a)首先 $A = A _ { 1 } \mid A _ { 2 } \mid \cdots \mid A _ { w }$ ，每一个子矩阵 $A _ { i }$ 的大小为恰为 $w b \times 2 ^ { b }$ ，每个子矩阵的列 $j$ 从 $a _ { i } ^ { ( 0 ) } , a _ { i } ^ { ( 1 ) } , \cdots a _ { i } ^ { ( 2 ^ { b } - 1 ) }$ 。

对于正则字Z，长度 $n = w 2 ^ { b }$ ，重量为 $w$ ，令 $z _ { 1 } , z _ { 2 } , \cdots z _ { w }$ 分别表示其非零项的位置（因为这个字是正则字，所以每个 $z _ { i }$ 在 ${ { \left( i - 1 \right) } \ o { \left| { \boldsymbol { \omega } } ^ { b } + 1 \right.}  }$ 和 $i 2 ^ { b }$ 之间是唯一的值)。

令输入 $x = \left( x _ { 1 } , x _ { 2 } , \cdots , x _ { w } \right)$ ，则 $x _ { i }$ 与 $z _ { i }$ 存在这样的关系：$z _ { i } = ( x _ { i } + 1 ) + ( i - 1 ) 2 ^ { b }$ ，那么由 $z$ 到 $x$ 的逆向变换如下所示：

$$
\left\{ \begin{array} { l } { { x _ { 1 } \equiv z _ { 1 } - 1 \left( \mathrm { m o d } \ 2 ^ { b } \right) } } \\ { { x _ { 2 } \equiv z _ { 2 } - 1 \left( \mathrm { m o d } \ 2 ^ { b } \right) } } \\ { { \qquad \dots } } \\ { { x _ { w } \equiv z _ { w } - 1 \left( \mathrm { m o d } \ 2 ^ { b } \right) } } \end{array} \right.
$$

因此，很容易验证：

$$
\begin{array} { r l } & { A \cdot z ^ { T } = a ^ { ( z _ { 1 } - 1 ) } \oplus a ^ { ( z _ { 2 } - 1 ) } \oplus \cdots \oplus a ^ { ( z _ { w } - 1 ) } } \\ & { \qquad = a _ { 1 } ^ { ( z _ { 1 } - 1 ) ( \mathrm { m o d } 2 ^ { b } ) } \oplus a _ { 2 } ^ { ( z _ { 2 } - 1 ) ( \mathrm { m o d } 2 ^ { b } ) } \oplus \cdots \oplus a _ { w } ^ { ( z _ { w } - 1 ) ( \mathrm { m o d } 2 ^ { b } ) } } \\ & { \qquad = a _ { 1 } ^ { ( x _ { 1 } ) } \oplus a _ { 2 } ^ { ( x 2 ) } \oplus \cdots \oplus a _ { w } ^ { ( x _ { w } ) } } \\ & { \qquad = \mathrm { D } \big ( x \big ) } \end{array}
$$

b）已经证明了对于每个输入 $x$ ，可以找到一个重量为 $w$ 的正则字 $z$ ，使得 $\boldsymbol { A \cdot z } ^ { T } = \boldsymbol { D } \boldsymbol { \left( x \right) }$ 。假设存在一个可以逆向求出$D ( x )$ 的敌手，即给定 $y = D ( \boldsymbol { x } )$ ，敌手输出 $x$ 。那么给定一个矩阵 $A$ 和一个值 $y = { D } ( x ) = A \cdot z ^ { T }$ ，同样的敌手便可以输出正则字Z。这正是 $\mathrm { R S D } \left( n , r , w \right)$ 的一个实例，对于 $r = w b$ 和 $n = w 2 ^ { b }$ 。因此，可以把该算法的安全性规约到RSD问题的困难性上，而RSD 问题同SD问题一样为NP完全问题。

# 4.2 实际安全性

在实践中，敌手将面临两个问题。一方面，敌手获得 $r$ 位的输出，但无法得到剩余的 $c = b - r$ 位，容量越大，系统越安全。另一方面，即使成功地猜测了这些比特，对手也必须解决RSD 问题的一个实例。对于一个选择适当的参数集，有效解决RSD问题和SD问题一样困难。事实上，所有已知的SD攻击都是完全指数型的，只有两种算法可以攻击基于SD问题的系统：信息集译码（ISD）[10]和广义生日算法（GBA）[18]。在文献[19]中提出了针对基于编码的密码系统的最新的GBA算法并将用于选择2SC的安全参数。

注意，还有一种攻击称为Memory trade-off attacks，这种攻击最初是在[20]中引入的，作为攻击分组密码的通用方法。为了避免这种攻击，初始向量 $I V$ 应该至少和密钥 $K$ 一样大，而 $s$ 至少应该是密钥的两倍。

根据这一节及前两节的描述，本文从结构上对比2SC方案和本文的方案，如表1所示。在下一章将对其进行具体的实验仿真对比。

表12SC方案和本文方案的结构对比  
Table 1 Structural comparison between 2SC scheme and proposed scheme   

<html><body><table><tr><td>方案</td><td>循环结构</td><td>编码算法</td><td>依赖的困难问题</td><td>问题性质</td><td>特点</td></tr><tr><td>2SC</td><td>Sponge结构</td><td>Niederreiter 变换</td><td>SD问题</td><td>NP完全</td><td>耗时较长</td></tr><tr><td>本文</td><td></td><td>Sponge 结构 基于编码的 hash 变换</td><td>RSD问题</td><td>NP完全</td><td>耗时较短</td></tr></table></body></html>

# 5 实验仿真

对改进后的伪随机序列生成算法进行分析，并与原始的2SC算法进行比较，同时测试生成序列的随机性。

# 5.1算法的效率分析

基于4章所提出的方案，利用Python语言对其过程进行仿真实现。 $\scriptstyle { \left( n , r , w \right) }$ 参数选取必须在已知的攻击下具有高效率和高安全性。首先，根据TimeMemory Trade-Off attacks， $s$ 至少应该是密钥的两倍。

$$
s = r + c = w \log _ { 2 } \bigl ( n / w \bigr ) \geq 2 \bigl | I V \bigr |
$$

$$
\left| K \right| = \left| I V \right| = r
$$

选取最优值 $b = \log _ { 2 } { \left( n / w \right) } = 8$ ，对于每个安全级别 $\lambda$ ，解决RSD问题的复杂度至少为 $2 ^ { \lambda }$ 。实验测试了不同安全级别下，产生 $r \times N$ （ $N$ 表示循环次数）比特伪随机序列所需要的时间。表1给出了在几个安全级别上，通过选取最优的参数集 $\scriptstyle { { \binom { n , r , w } { n , r , w } } }$ 而获得序列的测试结果。需要注意的是，在仿真实现过程中，只使用了随机的二元矩阵，而未使用任何特定的结构。但是当奇偶校验矩阵为准循环矩阵时，可以找到提供相同安全级别的参数[10]。

表2中的结果在Pycharm 中利用Python 所实现，操作系统为windowsl0，主频 $2 . 3 \mathrm { G H z }$ 。对于不同的安全级别，通过循环了10次产生 $r { \times } 1 0$ 位的数据。可以看到，随着校验矩阵 $n$ 的增大，生成序列的时间相应的增加，但是安全性也随之提高。表3将2SC算法实现结果与新的算法实现结果进行对比分析，取 $N = 1 0 0$ 。

由表2可以得到以下结论。对于80bit的安全级别，生成$9 . 6 \times 1 0 ^ { 3 }$ bit 的伪随机序列，本文的方法比与原先的2SC方法速度提高了3.19倍；对于120bit的安全级别，生成 $1 . 4 4 \times 1 0 ^ { 4 }$ bit的伪随机序列，本文的方法比与原先的2SC方法速度提高了3.02倍；对于160bits的安全级别，生成 $1 . 9 2 \times 1 0 ^ { 4 }$ bit 的伪随机序列，本文的方法比与原先的2SC方法速度提高了5.75倍；对于 400 bit的安全级别，生成 $3 . 0 4 \times 1 0 ^ { 4 }$ bit 的伪随机序列，本文的方法比与原先的2SC方法速度提高了4.5倍。

Table2 Test results under different security levels   

<html><body><table><tr><td>安全级别</td><td>n</td><td>S</td><td>W</td><td>C</td><td>|Keyl/bits</td><td>时间/s</td></tr><tr><td>80</td><td>8192</td><td>256</td><td>32</td><td>160</td><td>96</td><td>0.213</td></tr><tr><td>120</td><td>12288</td><td>384</td><td>48</td><td>240</td><td>144</td><td>0.485</td></tr><tr><td>160</td><td>16384</td><td>512</td><td>64</td><td>320</td><td>192</td><td>0.835</td></tr><tr><td>200</td><td>20480</td><td>640</td><td>80</td><td>400</td><td>240</td><td>1.332</td></tr><tr><td>240</td><td>24576</td><td>768</td><td>96</td><td>480</td><td>288</td><td>1.868</td></tr><tr><td>280</td><td>28672</td><td>896</td><td>112</td><td>560</td><td>336</td><td>2.569</td></tr></table></body></html>

注：测试时间并未计算初始化时间

表2不同安全级别下的测试结果  
表3不同安全级别下性能对比  
表4随机性测试结果  

<html><body><table><tr><td>安全级别</td><td>n</td><td>s</td><td>W</td><td>C</td><td>|Keyl/bits</td><td>2SC/s</td><td>Our/s</td><td>比率</td></tr><tr><td>80</td><td>8192</td><td>256</td><td>32</td><td>160</td><td>96</td><td>7.6022</td><td>2.382</td><td>3.19</td></tr><tr><td>120</td><td>12288</td><td>384</td><td>48</td><td>240</td><td>144</td><td>14.756</td><td>4.886</td><td>3.02</td></tr><tr><td>160</td><td>16384</td><td>512</td><td>64</td><td>320</td><td>192</td><td>44.663</td><td>7.765</td><td>5.75</td></tr><tr><td>400</td><td>32768</td><td>1024</td><td>128</td><td>720</td><td>304</td><td>137.682</td><td>30.596</td><td>4.50</td></tr></table></body></html>

Table 3 Performance comparison under different security levels   
Table4Test results ofRandomness   

<html><body><table><tr><td>测试项</td><td>1组测试值2组测试值3组测试值4组测试值5组测试值6组测试值</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Frequency</td><td>0.644081</td><td>0.096914</td><td>0.153868</td><td>0.849309</td><td>0.379944</td><td>0.921932</td></tr><tr><td>Block Frequency</td><td>0.328677</td><td>0.800956</td><td>0.106402</td><td>0.668934</td><td>0.250088</td><td>0.867440</td></tr><tr><td>Cumulative Sums</td><td>0.782085</td><td>0.106226</td><td>0.207897</td><td>0.812076</td><td>0.572709</td><td>0.667091</td></tr><tr><td>Runs</td><td>0.107008</td><td>0.821789</td><td>0.782522</td><td>0.057691</td><td>0.206671</td><td>0.275709</td></tr><tr><td>Longest Run of Ones</td><td>0.270825</td><td>0.739232</td><td>0.348457</td><td>0.341358</td><td>0.566602</td><td>0.116106</td></tr><tr><td>Rank</td><td>0.675960</td><td>0.041286</td><td>0.284170</td><td>0.251623</td><td>0.275808</td><td>0.984463</td></tr><tr><td>DiscreteFourier Transform</td><td>0.435383</td><td>0.502925</td><td>0.183317</td><td>0.129989</td><td>0.876031</td><td>0.212023</td></tr><tr><td>Non-periodic Template</td><td>0.376496</td><td>0.237213</td><td>0.022931</td><td>0.524622</td><td>0.510644</td><td>0.630072</td></tr><tr><td>OverlappingTemplate</td><td>0.663812</td><td>0.234041</td><td>0.163913</td><td>0.962218</td><td>0.800859</td><td>0.441365</td></tr><tr><td>Universal Statistical</td><td>0.583128</td><td>0.324725</td><td>0.147473</td><td>0.491854</td><td>0.835538</td><td>0.850540</td></tr><tr><td>Approximate Entropy</td><td>0.609971</td><td>0.290362</td><td>0.237763</td><td>0.762622</td><td>0.564112</td><td>0.006234</td></tr><tr><td>Random Excursions</td><td>0.226235</td><td>0.343650</td><td>0.095483</td><td>0.502313</td><td>0.790699</td><td>0.425471</td></tr><tr><td>Random ExcursionsVariant</td><td>0.636178</td><td>0.049265</td><td>0.496225</td><td>0.385500</td><td>0.061161</td><td>0.566982</td></tr><tr><td>Serial</td><td>0.483546</td><td>0.272573</td><td>0.524176</td><td>0.277855</td><td>0.873444</td><td>0.694912</td></tr><tr><td>Linear Complexity</td><td>0.206177</td><td>0.978800</td><td>0.885160</td><td>0.820437</td><td>0.862190</td><td>0.361264</td></tr></table></body></html>

注：有下划线的测试值表示未通过测试

# 5.2 NIST SP800-22测试分析

对算法产生的伪随机序列进行随机性测试，测试软件为美国国家标准与技术研究所的NISTSP800-22 测试包sts-2.1.1测试软件[21]。软件的测试项目包含15项，序列的测试长度需要大于 ${ 1 0 } ^ { 6 }$ bit，当测试值 $P _ { - } \nu a l u e \ge 0 . 0 1$ 时，认为序列在该项测试中为随机的；当测试值 $P _ { - }$ value $< 0 . 0 1$ 时，认为序列在该项的测试中为非随机的。现用sts-2.1.1测试软件对算法产生的

$6 . 7 2 \times 1 0 ^ { 6 }$ bis 的伪随机序列进行测试，测试分为6组，每组的长度为 ${ 1 0 } ^ { 6 }$ bits。测试结果如表4所示。

由测试结果可以看出，15个测试项的P-value值只有一个测试值未通过测试，其余都大于显著性水平 $\alpha$ （ $\alpha = 0 . 0 1$ )。其中，FrequencyTest 测试均值大于0.5，表示伪随机序列中0和1的个数接近相等，序列的均衡性较好；Runs测试均值为0.375，说明序列中游程数接近真随机序列中游程的个数；Serial测试均值大于0.5，说明指定长度的子序列出现的次数趋于等概；Cumulative Sums测试值3个都在0.6以上，说明0、1的分布较为均匀；LinearComplexity 测试值4个都在0.8以上，说明序列的复杂度较高。因此，本文生成的伪随机序列具有良好的随机特性。

# 5.3相关性分析

序列的自相关系数与互相关系数是评价序列随机性的常用统计量[22]。设伪随机序列 $b _ { n }$ ，长度为 $N$ ,则所得序列的自相关系数定义如下。

$$
a c ( m ) = \frac { 1 } { N } \cdot \sum _ { i = 1 } ^ { N - m } b _ { i } b _ { i + m }
$$

其中， $m$ 为步长，序列的自相关系数与步长有关，当步长 $m$ 变化时，自相关系数变化越小，说明序列的随机性能越好。

当步长 $m$ 为0时的理论值为0.5，其余步长时，理论值为0.25 设两个不同的伪随机序列分别为 $b _ { 1 n }$ 和 $b _ { 2 n }$ ，$n = 1 , 2 \cdots , N$ ，序列 $b _ { 1 n }$ 和 $b _ { 2 n }$ 的互相关系数定义为:

$$
c c ( m ) = \left\{ \begin{array} { l l } { \displaystyle { \frac { 1 } { N } } \cdot \sum _ { i = 1 } ^ { N - m } b _ { 1 i } \cdot b _ { 2 ( i + m ) } } & { \quad 0 \leq m \leq N } \\ { \displaystyle { \frac { 1 } { N } } \cdot \sum _ { i = 1 } ^ { N - m } b _ { 1 ( i + m ) } \cdot b _ { 2 i } } & { \quad - N \leq m \leq 0 } \end{array} \right.
$$

互相关系数理论值为0。序列的自相关和互相关系数值越接近理论值，说明序列的随机性越好。实验随机选取了两组长度为 $N = 5 0 0 0$ 的伪随机序列 $c _ { 1 }$ 和 $c _ { 2 }$ 进行测试，实验结果如图4所示。

实验结果显示，序列的自相关性及互相关性分布均接近于理想状态，说明本文方法所得序列之间相关程度较小，具有较好的随机性。

# 5.4平衡性分析

设伪随机序列的长度为 $N$ ,序列中0和1的个数分别为 $P$ 和 $\boldsymbol { Q }$ ，则序列的平衡度定义为

$$
E { \big ( } N { \big ) } = { \frac { \left| P - Q \right| } { N } }
$$

平衡度的值 $E { \big ( } N { \big ) }$ 越小，说明该序列中的0和1的个数越相近，随机性越好。实验选取了三组长度为 $N = 3 8 4 0 0$ 的生成序列 $c _ { 1 }$ 、 $c _ { 2 }$ 和 $c _ { 3 }$ 进行测试，图5给出了实验所得序列的平衡度分析。

![](images/b2acf02b1825e2c8c36784b753553110f2ca16ca610ff7c85e4fd5be35c65217.jpg)  
图4序列 $c _ { 1 }$ 和序列 $c _ { 2 }$ 的自相关及互相关系数

![](images/47456121d1e6d478166a8d7e1eb64832d83efd771e319417f230b2a6b8558605.jpg)  
Fig.4Autocorrelation and cross-correlation coeficients of sequences $c _ { 1 }$   
图5序列的平衡度测试  
Fig.5Sequence balance test

实验结果表明，三组伪随机序列的平衡度都在0.010以下，接近于0。因此表明序列中的0和1的个数十分接近，因此序列的性能稳定，平衡度良好。

# 5.5游程检验

游程即伪随机序列的一个子序列，由连续的0或1元素组成，其前一部分和后一部分的元素均和该元素不同，其中0或1 连续出现的个数称为游程长度；随机序列中，任意长度的序列的0和1的个数近似相同，其中游程长度为 $L$ 的序列约占总序列长度的 $1 / 2 ^ { L }$ ，实验生成的伪随机序列越接近理想状态，则说明序列的随机性越好。实验所测序列的长度均为 $N = 3 8 4 0 0$ ，对三组序列进行游程统计测试，具体统计情况如表5\~7所示。

Table 5 Travel statistics of sequence $c _ { 1 }$   
表6序列 $c _ { 2 }$ 的游程统计  

<html><body><table><tr><td rowspan="2">游程</td><td colspan="8">游程长度</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>0</td><td>4788</td><td>2422</td><td>1209</td><td>568</td><td>312</td><td>153</td><td>78</td><td>48</td></tr><tr><td>1</td><td>4842</td><td>2356</td><td>1212</td><td>593</td><td>328</td><td>16</td><td>68</td><td>36</td></tr><tr><td>0/1</td><td>0.9888</td><td>1.0280</td><td>0.9975</td><td>0.9578</td><td>0.9512</td><td>1.1250</td><td>1.1471</td><td>1.3333</td></tr><tr><td>实测值</td><td></td><td>0.50120.2487</td><td>0.1260</td><td>0.06040.0333</td><td></td><td>0.0150</td><td>0.0076</td><td>0.0044</td></tr><tr><td>理论值 0.5000 0.2500 0.1250 0.0625 0.0313</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0156 0.0078 0.0039</td><td></td></tr></table></body></html>

表5序列 $c _ { 1 }$ 的游程统计  

<html><body><table><tr><td colspan="8">Tableo 1 tatistiesOrsequenee 2</td></tr><tr><td rowspan="3">游程</td><td colspan="8">游程长度</td></tr><tr><td rowspan="2">1</td><td rowspan="2">2</td><td rowspan="2">3</td><td rowspan="2">4</td><td rowspan="2">5</td><td rowspan="2">6</td><td rowspan="2">7</td><td rowspan="2">8</td></tr><tr><td></td></tr><tr><td>0</td><td>4855</td><td>2396</td><td>1168</td><td>607</td><td>323</td><td>155</td><td>74</td><td>46</td></tr><tr><td>1</td><td>4852</td><td>2485</td><td>1185</td><td>552</td><td>289</td><td>144</td><td>78</td><td>40</td></tr><tr><td>0/1</td><td></td><td>1.0006 0.9641</td><td></td><td></td><td>0.9856 1.0996 1.1176</td><td>1.0763</td><td>0.9487</td><td>1.1500</td></tr><tr><td></td><td></td><td>实测值0.50270.2527</td><td>0.1218</td><td>0.0600</td><td></td><td>0.0316 0.0154</td><td>0.0078 0.0044</td><td></td></tr><tr><td>理论值0.5000 0.2500</td><td></td><td></td><td></td><td>0.1250 0.0625</td><td></td><td></td><td>0.0313 0.0156 0.0078 0.0039</td><td></td></tr></table></body></html>

Table 6 Travel statistics of sequence $c _ { 2 }$   
表7序列 $c _ { 3 }$ 的游程统计Table 7 Travel statistics of sequence C3  

<html><body><table><tr><td rowspan="2">游程</td><td colspan="8">游程长度</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>0</td><td>4828</td><td>2358</td><td>1193</td><td>590</td><td>330</td><td>156</td><td>84</td><td>43</td></tr><tr><td>1</td><td>4816</td><td>2403</td><td>1176</td><td>618</td><td>309</td><td>147</td><td>65</td><td>40</td></tr><tr><td>0/1</td><td>1.0025</td><td>0.9813</td><td>1.0145</td><td>0.9547</td><td></td><td>1.0680 1.06121.2923</td><td></td><td>1.0750</td></tr><tr><td>实测值</td><td></td><td></td><td>0.5020 0.2478 0.1233</td><td></td><td></td><td></td><td>0.0629 0.0333 0.0158 0.0078 0.0043</td><td></td></tr><tr><td></td><td>理论值 0.5000 0.2500 0.1250 0.0625 0.0313 0.0156 0.0078 0.0039</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

根据三组实验结果可知，生成的伪随机序列的游程统计接近理论值，其中0和1的个数接近相等。不同游程长度的序列占总序列的百分比与理论值相当。因此本文实验所得的序列符合游程统计特性。

# 6 结束语

本文提出了一种基于海绵函数的快速伪随机序列生成方法，是对2sc伪随机序列生成方法的改进。该方法一方面使得密钥和初始向量长度缩短，另一方面将码字编码为正则字的过程转换为一种可以规约为正则字校验子译码问题的编码方式，其计算速度相比于原来大大提高。实验仿真结果表明本文的方法在相同安全级别下将比原来序列生成速度至少提高3倍。NIST的测试结果表明本文方法生成的伪随机序列具有良好的随机性，序列的自相关性、互相关性、平衡度、游程统计都符合理论值。同时，方案的安全性依赖于RSD问题，这使得该方法可以抵抗现有的量子攻击。

# 参考文献：

[1]张斌，徐超，冯登国．流密码的设计与分析：回顾、现状与展望[J]．密 码学报,2016,3(6): 527-545.(Zhang Bin,Xuchao,Feng Dengguo.Design and analysis of stream ciphers: past, present and future directions [J]. Journal of Cryptologic Research,2016,3 (6): 527-545)   
[2] Avaroglu E, Koyuncu i, Ozer A B,et al. Hybrid pseudo-random number generator for cryptographic systems [J]. Nonlinear Dynamics,2015,82 (1- 2): 58-61.   
[3]Wang Yong,Liu Zhaolong,Ma Jianbin,et al.A pseudorandom number generator based on piecewise logistic map [J].Nonlinear Dynamics,2016, 83 (4): 2373-2391.   
[4]Blum M, Micali S. How to generate cryptographically strong sequences of pseudo random bits [C]/ Proc of Symposium on Foundations of Computer Science.2008: 112-117.   
[5]Bernstein DJ,Hamburg M,Krasnova A,et al.Elligator: elliptic-curve points indistinguishable from uniform random strings [C]//Proc of ACM SIGSAC Conference on Computer & Communications Security.New York:ACM Press,2013: 967-980.   
[6]Alexi W, Chor B,Goldreich O,et al. RSAand Rabin functions: certain parts are as hard as the whole[J]. SIAMJournal on Computing,1988,17(2): 194- 209.   
[7]刘文瑞．抗量子计算攻击密码体制发展分析[J].通信技术,2017,50(5): 1054-1059.(Liu Wenrui. Quantum Computing Attack Password System Development Analysis [J]. Communications Technology，2017,50 (5): 1054-1059.)   
[8]Impagliazzo R,Naor M.Efficient cryptographic schemes provably as secure as subset sum [C]// Proc of Symposium on Foundations of Computer Science.1989: 236-241.   
[9] Fischer JB,Stern J. An efficient pseudo-random generator provably as secure as syndrome decoding [Cl// Proc of International Conference on Theory and Application of Cryptographic Techniques. Springer-Verlag, 1996: 245-255.   
[10] GaboritP,Lauradoux C,Sendrier N.SYND:a fast code-based stream cipher with a security reduction [C]//Proc of IEEE International Symposium on Information Theory.IEEE Xplore,2007:186-190.   
[11] Meziani M,CayrelPL,Alaoui SMEY.2SC:an efficient code-based stream cipher [C]// Proc of International Conference on Information Security and Assurance. Berlin: Springer, 2011: 111-122.   
[12] Gaborit P, Hauteville A,Tillich JP. RankSynd a PRNG based on rank metric [M]/ Post-Quantum Cryptography. Springer International Publishing, 2016.   
[13] Augot D,Finiasz M,Sendrier N.A Family of Fast Syndrome Based Cryptographic Hash Functions [Cl// Proc of International Conference on Cryptology in Malaysia.Berlin: Springer, 20o5: 64-83.   
[14] Berlekamp ER,Mceliece R J,Van Tilborg H C A.On the inherent intractability of certain coding problems (Corresp.）[J]. IEEE Trans. inf. theory,1978,24(3): 384-386.   
[15]任方，郑东．一种基于编码的数字签名算法的改进[J]．西安邮电   
[16] 大学学报,2015,20(5): 38-43.(Ren Fang,Zheng Dong.An improved code based digital signature algorithm [J]. Journal ofXI’AN University of Post and Telecommunications,2015,20 (5): 38-43.)   
[17] BertoniG,Daemen J,Peeters M,et al. Sponge functions [J].Ecrypt Hash Workshop, 2007.   
[18] Overbeck R,Sendrier N. Code-based cryptography [M]// Post-Quantum Cryptography.Springer Berlin Heidelberg,2009: 95-145.   
[19] Shenghui Su,Tao Xie,Shuwang Lü.A provably secure non-iterative hash function resisting birthday attack [J],Theoretical Computer Science, 2016, 654 (22): 128-142   
[20]Finiasz M, Sendrier N.Security Bounds for the Design of Code-Based Cryptosystems [C]// Proc of International Conference on Theory and Application of Cryptology and Information Security.Proceedings.2009: 88- 105.   
[21] Hellman M.A cryptanalytic time-memory trade-off[J].IEEE Trans on Infomation Theory,1980,26 (4): 401-406.   
[22] Rukhin A, Soto J,Nechvatal J, et al.A statistical test suite for random and pseudorandom number generators for cryptographic applications [J]. Applied Physics Letters,2015,22(7): 1645-179.   
[23]韩蕊，张雪锋．基于高维猫映射的伪随机序列生成方法[J].计算机工 程与应用,2016,52(10): 91-99.(HanRui,Zhang Xuefeng.Pseudo-random sequence generating method based on high dimensional cat map [J]. Computer Engineering and Applications,2016,52(10): 91-99.)