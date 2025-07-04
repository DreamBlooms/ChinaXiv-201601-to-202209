# 基于多碱基组合映射编码和DNA计算的一次一密算法

彭维平，程丹华，宋成(河南理工大学计算机科学与技术学院，河南省焦作市 454000)

摘要：为增强密码方案安全性，利用多碱基组合映射编码，采用模拟DNA生物操作的方式，提出了一种一次一密加解密方案。方案主要采用分段加密的机制，利用多碱基组合映射编码规则编码明文信息，通过Logistic 逻辑映射系统生成随机数构造一次一密密钥本，为每一个明文段选择不同的密钥。加解密算法运用 DNA 碱基运算规则，并将部分参数和最终密文经过处理后通过安全信道传送给解密方。对图像的仿真和安全性的分析表明，密钥本的制作基于混沌映射和多碱基DNA编码规则两层操作，密钥空间足够大，并且攻击者在密文图像中得不到任何有用的统计数据，另外，随着需要加密的明文数据量增加，攻击者完全破解所需计算的密钥空间量呈指数级增长，增强了算法安全性。

关键词：DNA密码；Logistic 映射；多碱基组合映射；一次一密密钥本；图像加密 中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2018.01.010c

# One-time-pad encryption scheme based on multibase combination mapping encoding and DNA computing

Peng Weiping, Cheng Danhua, Song Cheng (School of Computer Sciences & Technology Henan Polytechnic University,Jiaozuo Henan 454oo0, China)

Abstract: In order to enhance the security ofcryptographic scheme,using the multibase combination mapping encoding and the way ofsimulating the biological operation,aone-time-pad encryption scheme was proposed.The scheme mainly adopted themechanismofsegmentation encryption.The plaintext information was transformed intothe DNAsequencebythe multibase combination mapping encoding.The Logistic Logic Mappng System generated random numbers to construct a one-time-pad codebook and selected diferent key for each plaintext segment.The encryption/decryption algorithm used the DNA base algorithmand transmited someof the parameters and the final ciphertexttothe decryptionside through asecure chanel. Through theanalysisofthesimulationandsecurityoftheimageemulation,itisshownthat theproductionofthecodebook is based on the two-level operation: the chaos mapping and the multibasecombination mapping encoding,the key space is large enough,andtheatackercannotobtainanyuseful statistical date intheciphertextimage.Moreover,withthe increaseof the plaintextdata,theamountofkeyspacerequiredfortheattackertocrackisexponentiall increasing,which improves thesecurity of the algorithm.

Key words: DNA cryptography;Logistic logic mapping; the multibase combination mapping encoding; one-time codebok; image encryption

# 0 引言

DNA 编码继承了遗传分子强大的并行计算能力、能耗低和高信息密度等特性[I]，使得DNA 计算[2-]和DNA 密码在大量并行数据加密的应用中具有独特优势，也取得了一些成果，但其加密技术还很不成熟，还有很多亟需解决的问题，比如编码过程太复杂、生物实验失误率高、实验成本太高等。事实上，在DNA生物实验中因为操作环节多且错误会逐渐累积，所以要求实验操作的每个步骤都具备很高的成功率，否则得到的结果可能与准确值差别很大。当前，在DNA密码算法设计方面相对可行的方法是基于DNA计算的一些生物学特性，采用模拟DNA生物操作的方式，通过执行伪DNA计算的操作来实现信息加密[7]。2012年，文献[8]利用设计的DNA组件，将接收到的语音信息转换成文本形式，再将该文本利用DNA 编码转换成DNA序列的形式进行传送。文中设计使用的DNA编码规则为四个碱基组合对应英文字母、数字和特殊符号，密码本大小为98，由于四个碱基组合的种类有 $4 ^ { 4 }$ 种，则其密钥空间仅为

$C _ { 2 5 6 } ^ { 9 8 }$ ，在了解组件工作原理的情况下，利用穷举攻击密文信息很容易被破解得到明文。2014年，文献[9]提出随机生成一次一密密钥本加解密的方案，通过PCR技术进行密钥分配，利用电子计算机异或运算进行加解密操作，信息转换采用三联体编码的方式，编码由三个碱基组成的组合与字母、数字和符号对应关系组成，分析可得其对应关系只有 $C _ { 6 4 } ^ { 4 0 }$ 种，所提供的编码安全性相对较低。2015年，文献[10]提出一种改进的基于DNA 编码和混沌映射的图像加密方法，利用DNA加法、DNA减法和DNA补充方法三种算法对明文图像对应的DNA序列矩阵进行操作，补充了已有算法[1的不可逆性的缺点。但是，从编码安全考虑，该算法使用的DNA编码规则为传统的单碱基与双比特二进制的对应关系，又考虑其互补特性，即只有8种编码选择方式，算法所提供的编码安全性是远远不够的。2016年，文献[12]提出一种对称密钥密码方案，首先明文根据ASCII和传统的互补性DNA编码规则转换成DNA序列，将该序列4个一组根据随机密钥本找到相应最终的十进制密文。文中关键步骤在于随机密钥本的生成，该密钥本由四个碱基组合与1\~256数字的对应关系组成，其密钥空间为256!，但生成过程中需要排除较多具有相同对应关系的选择，因而实际可用的对应关系远远小于256!。综合上述文献方案中明文转换和密钥本的构造均仅利用简单的字符和DNA碱基组合的对应关系，所得密钥空间均为一固定值，跟明文的长度等没有关系。

相比较以上基于DNA编码的密码方案，本文方案利用两种 DNA碱基编码规则分别处理明文信息、制作密钥本和密文传输，针对不同数据选择不同的DNA编码规则，以增强算法编码安全性，并且，利用传统的一维Logistic 混沌映射对初始值的随机性和敏感性等固有特性制作一次一密密钥本，通过代入初始参数产生多对参数，根据设计的算法规则和编码规则经过转换添加引物信息后得到相应的单链DNA序列集合，即为密钥本。为增强安全性，加密完成后将密钥本制作的初始参数、挑选密钥的引物对和密文进行信息处理转化为可在安全通信信道传输的二进制序列传送给解密方，解密方收到密文，首先经过数据处理得到初始参数等，根据密钥本制作规则生成密钥本，再利用和加密相同的算法解密密文。最后，本文以图像为仿真对象，描述了算法的整个过程，分析表明本方案密钥空间与明文长度相关，并从密钥敏感度、灰度直方图、信息熵等方面分析了本方案的可行性和安全性。

# 1 算法基础

# 1.1相关参数

本文所用的参数如表1所示。

表1相关参数定义  

<html><body><table><tr><td>参数</td><td>定义</td></tr><tr><td>DNA编码规则</td><td>R(N ~ N4)</td></tr></table></body></html>

<html><body><table><tr><td>Logistic 混沌映射初始参数</td><td>(g,μ)</td></tr><tr><td>阈值函数</td><td>F(x)</td></tr><tr><td>明文二进制长度</td><td>n</td></tr><tr><td>明文分段长度</td><td>l</td></tr><tr><td>明文分段段数</td><td>S</td></tr><tr><td>图像矩阵</td><td>M×N</td></tr><tr><td>密钥本大小</td><td>K</td></tr><tr><td>单个密钥长度</td><td>m</td></tr><tr><td>信息熵</td><td>H(x)</td></tr></table></body></html>

# 1.2 DNA编码

DNA由A（腺嘌呤脱氧核苷酸），T（胸腺嘧啶脱氧核苷酸），C（胞嘧啶脱氧核苷酸）和G（鸟嘌呤脱氧核苷酸）四个脱氧核苷酸组成，其中A、T和C、G分别两两互补。为了提高方案的安全性，本文分别对明文转换和密文传输使用不同的编码规则，定义如下所示。

编码规则1单碱基映射双比特二进制编码[13]：将DNA碱基A，TC,G分别表示双比特二进制值00,01，10,11。

很显然，此对应方式有 $4 ! = 2 4$ 种，考虑DNA碱基之间的互补特性，实际可用的编码有8种，如表2所示。本文后续方案中密文等转换传输时采用的编码规则均选自于表2。

表2DNA编码I  

<html><body><table><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>00-A</td><td>00-A</td><td>00-C</td><td>00-C</td><td>00-G</td><td>00-G</td><td>00-T</td><td>00-T</td></tr><tr><td>01-C</td><td>01-G</td><td>01-A</td><td>01-T</td><td>01-A</td><td>01-T</td><td>01-C</td><td>01-G</td></tr><tr><td>10-G</td><td>10-C</td><td>10-T</td><td>10-A</td><td>10-T</td><td>10-A</td><td>10-G</td><td>10-C</td></tr><tr><td>11-T</td><td>11-T</td><td>11-G</td><td>11-G</td><td>11-C</td><td>11-C</td><td>11-A</td><td>11-A</td></tr></table></body></html>

编码规则2多碱基组合映射双比特二进制编码： $a$ 个碱基组成的组合分别对应双比特二进制00.01,10,11，在碱基A,T,C,G中任选 $a$ 个碱基进行组合，则共有 $4 ^ { a }$ 种组合方式。

很显然，当 $a = 1$ 时，此规则等价于上述编码I。

假设 $a = 4$ ，则4个碱基共有 $4 ^ { 4 } { = } 2 5 6$ 种组合方式，双比特二进制值随机对应4种不同的碱基组合方式。本文后续明文二进制串向明文DNA序列转化时运用此编码规则。

# 1.3DNA碱基运算

碱基之间除了DNA生物特性方面的反应之外，有专家和学者提出了构造算术或逻辑运算的方法，比如加法、减法运算，与、或、非和异或等逻辑运算。为遵循碱基之间互补特性和便于进行加解密运算，本文DNA碱基运算只采用异或运算操作。根据1.2节中的编码规则I，有8种不同的DNA编码方案，每一种编码方案对应相应的碱基运算结果。因而，可构造出8种不同的碱基运算表。例如，选用表1中的编码规则I（ $[ A = 0 0 , T = 1 1 , C = 0 1 , G = 1 0 ]$ ），按照传统异或算法可得DNA碱基之间的运算表如表3所示。

表3DNA碱基运算表  

<html><body><table><tr><td>运算结果</td><td>A</td><td>T</td><td>C</td><td>G</td></tr><tr><td>A</td><td>A</td><td>T</td><td>C</td><td>G</td></tr><tr><td>T</td><td>T</td><td>A</td><td>G</td><td>C</td></tr><tr><td>C</td><td>C</td><td>G</td><td>A</td><td>T</td></tr></table></body></html>

G G C T A

# 1.4 随机数生成

基于一维Logistic 混沌映射产生伪随机序列，并通过阈值函数可得到随机性很强的二进制序列，其数学定义如下所示，每个随机序列均由初始参数 $( g _ { 1 } , \mu _ { 1 } )$ ， $g _ { 1 } \in ( 0 , 1 ) , \mu _ { 1 } \geq 3 . 5 6 9 9 4 6$ 和阈值来确定，其中 $x _ { 1 } = g _ { 1 }$ □

$$
x _ { i + 1 } = \mu _ { j } x _ { i } ( 1 - x _ { i } ) , \mu _ { j } \in [ 0 , 4 ] , x _ { i } \in ( 0 , 1 )
$$

$$
F ( x ) = \left\{ { \begin{array} { l l } { 0 , } & { 0 < x _ { i } \leq 0 . 7 } \\ { 1 , } & { 0 . 7 < x _ { i } < 1 } \end{array} } \right.
$$

本文采用参数派生的方法，通过一组初始参数来产生多组参数，派生计算如下公式所示：

$$
g _ { i } = \mu _ { i } g _ { i - 1 } ( 1 - g _ { i - 1 } ) , g _ { i } \in ( 0 , 1 ) , \mu _ { 1 } \in [ 3 . 5 6 9 9 4 6 , 4 ]
$$

# 2 密码本构造

一次一密密钥本用于密码算法具有更高的加密强度，其所需密钥的长度取决于待加密明文的长度。为便于密钥的生成和管理，本文采用分段加密的方式，将明文对应的二进制信息进行分段加密操作，加解密所用的单个密钥长度不小于明文分段长度。每段明文可随机选择密钥本中不完全相同的任意一条密钥段进行加解密。

# 2.1分段规则

本文将明文数据归纳为文本信息和非文本信息两大类，非文本信息以图像信息为例。针对两种不同的数据类型，采用不同的分段方法，规则如下：

1)文本信息分段

文本信息首先转换为二进制，依据分段长度，即可计算出分段数。假设明文信息对应的明文二进制长度为 $n$ ，定义分段长度为、分段数为 $s$ 。

$$
S = \lceil n / l \rceil
$$

其中：第 $s$ 段长度若小于分段长度 $\mathbf { \xi } _ { l }$ ，采用 $^ { \mathrm { * } } 0 ^ { \mathrm { * } }$ 填充方式补齐。

# 2）图像信息分段

若加密的明文信息是图像数据，首先原始图像经过转化得到一个 $M \times N$ 的二进制矩阵，则默认原始图像对应的二进制矩阵的每一行为一段，矩阵的行数即为分段总数，即 $S = M$ □

# 2.2 密钥生成算法

通过以上分析，设定密码本大小为 $K$ ，则 $K > S$ 。密钥产生及构造密码本算法如下：

a)设定混沌映射初始值 $( g _ { 1 } , \mu _ { 1 } ) , g _ { 1 } \in ( 0 , 1 ) , \mu _ { 1 } \geq 3 . 5 6 9 9 4 6$ 。将初始值 $( g _ { 1 } , \mu _ { 1 } )$ 代入式(3)(4)得到初始值在内共 $\kappa$ 对参数$( g _ { i } , \mu _ { i } ) , g _ { i } \in ( 0 , 1 ) , \mu _ { i } \geq 3 . 5 6 9 9 4 6 , i \in [ 1 , K ]$ 。

b)将a)得到的 $K$ 对参数 $( g _ { i } , \mu _ { i } )$ 均代入Logistic 混沌式(1)中生成 $\kappa$ 个随机数序列 $\{ \{ ( x _ { i } ) _ { 1 } \} , \{ ( x _ { i } ) _ { 2 } \} , . . . \{ ( x _ { i } ) _ { k } \} \}$ ,经过阈值函数式(2)判断得到 $K$ 个二进制序列串 $\{ \{ ( b _ { i } ) _ { 1 } \} , \{ ( b _ { i } ) _ { 2 } \} , \dots \{ ( b _ { i } ) _ { k } \} \}$ 。

c）依次从b)中生成的 $\kappa$ 个二进制串中截取不完全相同的长度为 $m$ 的 $\kappa$ 条二进制序列$\{ \{ ( b _ { i } , b _ { i + 1 } , . . . b _ { i + m - 1 } ) _ { 1 } \} , \{ ( b _ { i } , b _ { i + 1 } , . . . b _ { i + m - 1 } ) _ { 2 } \} , . . . \{ ( b _ { i } , b _ { i + 1 } , . . . b _ { i + m - 1 } ) _ { k } \} \}$ 。 $\mathbf { \nabla } _ { m }$ 的取值依据 2.1节中对明文分段大小来确定，若加密数据为明文信息为文本信息，则 $\scriptstyle m = l$ ；若为图像信息，则 $\scriptstyle { m = N }$ 。

d)根据1.2中的编码规则2，从 ${ { N } _ { 4 } }$ 种对应方式中选择 $\kappa$ 种不完全相同的方式对截取出的 $K$ 条二进制序列进行DNA转换，得到 $K$ 条DNA单链序列 $\{ \{ D _ { 1 } ^ { \prime } \} , \{ D _ { 2 } ^ { \prime } \} , . . . \{ D _ { K } ^ { \prime } \} \}$ 。

e)分别对 $K$ 条DNA单链序列前后随机添加长为10bp 的引物对 $\{ ( q _ { 1 } , q _ { 1 } ^ { \mathrm { ~ , ~ } } ) , ( q _ { 2 } , q _ { 2 } ^ { \mathrm { ~ , ~ } } ) , . . . ( q _ { K } , q _ { K } ^ { \mathrm { ~ , ~ } } ) \}$ 。

此 $K$ 条DNA单链构造的集合即为加解密的密钥本。约束条件：

$\boldsymbol { K }$ 条DNA单链必须符合以下条件：a）任意两条单链的引物对不完全相同；b）任意两条单链的密钥序列不完全相同。

# 3 加/解密算法设计

# 3.1 算法初始化

a)依据明文信息类别按照2.1节所述规则，计算得到分段参数 $s$ ，确定密钥本大小 $K$

b)设定初始参数 $( g _ { 1 } , \mu _ { 1 } )$ 、 $w$ 、引物对信息$\{ ( q _ { 1 } , q _ { 1 } ^ { \mathrm { ~ , ~ } } ) , ( q _ { 2 } , q _ { 2 } ^ { \mathrm { ~ , ~ } } ) , . . . ( q _ { K } , q _ { K } ^ { \mathrm { ~ , ~ } } ) \}$ 、编码规则I中的 $R _ { I }$ 以及编码规则II中的 $R _ { 2 }$ 和 $R _ { 3 }$ 。

c)以上参数通过安全信道传送给解密方。

# 3.2加密算法

初始化完成后，依据初始参数，构造密码本，在密码本中选择 $s$ 对引物对应的密钥作为加密密钥，并和明文段按照碱基运算规则进行加密操作。具体加密步骤如下：

a)根据 $R _ { 2 }$ 将明文二进制段转化为对应的明文DNA序列段 $\{ \{ D _ { 1 } \} , \{ D _ { 2 } \} , . . . , \{ D _ { s - 1 } \} , \{ D _ { s } \} \}$

b)利用共享参数 $w$ 、初始参数 $( g _ { 1 } , \mu _ { 1 } )$ 、编码规则 $R _ { 3 }$ 以及全部引物对 $\{ ( q _ { 1 } , q _ { 1 } ^ { \mathrm { ~ \prime ~ } } ) , ( q _ { 2 } , q _ { 2 } ^ { \mathrm { ~ \prime ~ } } ) , . . . ( q _ { K } , q _ { K } ^ { \mathrm { ~ \prime ~ } } ) \}$ 按照2.2节密钥本生成算法制作密钥本;

c)在引物对集合 $\{ ( q _ { 1 } , q _ { 1 } ^ { \mathrm { ~ , ~ } } ) , ( q _ { 2 } , q _ { 2 } ^ { \mathrm { ~ , ~ } } ) , . . . ( q _ { K } , q _ { K } ^ { \mathrm { ~ , ~ } } ) \}$ 中随机挑选 $s$ 对引物 $\{ ( q _ { i } , q _ { i } ) , . . . ( q _ { s } , q _ { s } ^ { } ) \}$ ，从密钥本中对应挑选出 $s$ 个密钥$\{ \{ D _ { i } ^ { \prime } \} , . . . , \{ D _ { s } ^ { \prime } \} \}$ ：

d)按照1.3节中DNA碱基运算规则对每段明文DNA序列$\{ \{ D _ { 1 } \} , \{ D _ { 2 } \} , . . . , \{ D _ { s - 1 } \} , \{ D _ { s } \} \}$ 和对应的密钥 $\{ \{ D _ { i } ^ { \prime } \} , . . . , \{ D _ { s } ^ { \prime } \} \}$ 按顺序进行加密操作，得到密文DNA序列 $\{ \{ C _ { 1 } \} , \{ C _ { 2 } \} , . . . , \{ C _ { s - 1 } \} , \{ C _ { s } \} \}$ ：

e)将引物对 $\{ ( q _ { i } , q _ { i } ^ { \mathrm { ~ \prime } } ) , . . . ( q _ { s } , q _ { s } ^ { \mathrm { ~ \prime } } ) \}$ 以及密文DNA序列$\{ \{ C _ { 1 } \} , \{ C _ { 2 } \} , . . . , \{ C _ { s - 1 } \} , \{ C _ { s } \} \}$ 按照 $R _ { I }$ 转化成适合通信信道传输的二进制编码发送给接收者。

# 3.3解密算法

解密方得到密文信息后，首先根据共享参数制作密钥本，然后利用密文信息中的引物对信息选择密钥和密文进行解密。具体解密步骤如下：

a)根据初始参数 $( g _ { 1 } , \mu _ { 1 } )$ 按照密钥本生成规则和 $R _ { 3 }$ 生成DNA序列，并按顺序添加共享的全部引物对信息$\{ ( q _ { 1 } , q _ { 1 } ^ { \mathrm { ~ , ~ } } ) , ( q _ { 2 } , q _ { 2 } ^ { \mathrm { ~ , ~ } } ) , . . . ( q _ { K } , q _ { K } ^ { \mathrm { ~ , ~ } } ) \}$ 得到密钥本;

b)将密文二进制编码根据 $R _ { I }$ 还原得到引物对信息$\{ ( q _ { i } , q _ { i } ^ { \mathrm { ~ \prime } } ) , . . . ( q _ { s } , q _ { s } ^ { \mathrm { ~ \prime } } ) \}$ 和原始密文DNA序列 $\{ \{ C _ { 1 } \} , \{ C _ { 2 } \} , . . . , \{ C _ { s - 1 } \} , \{ C _ { s } \} \}$ ·

c)根据密文中引物对信息 $\{ ( q _ { i } , q _ { i } ^ { \mathrm { ~ \prime ~ } } ) , . . . ( q _ { s } , q _ { s } ^ { \mathrm { ~ \prime ~ } } ) \}$ 在密钥本中找到对应的密钥DNA序列 $\{ \{ D _ { i } ^ { \prime } \} , . . . , \{ D _ { s } ^ { \prime } \} \}$ ;

d)密钥 DNA 序列 $\{ \{ D _ { i } ^ { \prime } \} , . . . , \{ D _ { s } ^ { \prime } \} \}$ 和原始密文 DNA 序列$\{ \{ C _ { 1 } \} , \{ C _ { 2 } \} , . . . , \{ C _ { s - 1 } \} , \{ C _ { s } \} \}$ 依据DNA碱基运算规则进行操作得到明文DNA序列；

e)利用加密时操作明文信息的编码规则 $R _ { 2 }$ 还原明文DNA序列得到原始明文信息。

# 4 实验仿真

本文选择灰色图像作为仿真对象。明文图像可转化成每一个像素为0\~255的二维矩阵。按照上述加解密流程，将明文图像的每一行作为一个明文段进行加密操作，为了达到更好的加密效果，在实施加密算法之后对图像进行Arnold置乱处理。以Lena图像为例，其大小为 $2 5 6 \times 2 5 6$ ，原图经过转化得到一个大小为 $2 5 6 \times 2 0 4 8$ 的二进制灰度值矩阵，将矩阵的每一行作为一段进行加密，即 $\scriptstyle { S = 2 5 6 }$ ， $K > S = 2 5 6$ ，设置密钥大小 $K = 3 2 0$ 。首先，设定Logistic 混沌映射初始值为 $g _ { 1 } = 0 . 5 0 4 , \mu _ { 1 } = 3 . 6 8$ ，参数 $w = 3$ ，初始值带入公式(3)和(4)，顺序选择320 对参数 $( g _ { i } , \mu _ { i } )$ 带入公式(1)和(2)，对生成的每条随机二进制串从第100位开始截取长度为 $\scriptstyle { m = N = 2 0 4 8 }$ 的二进制序列。然后，根据随机选择的320种不完全相同的编码规则II $\left. R _ { 3 } \right.$ ）得到对应的DNA密钥序列，添加前后引物后即为密钥本。表4为该一次一密密钥本的一部分密钥序列。

密钥本制作好之后，根据引物对选择相应的密钥序列，对每段明文按照DNA碱基运算规则操作即可得到密文图像。

表4部分密码本  

<html><body><table><tr><td>编号</td><td>密钥序列</td></tr><tr><td>1</td><td>ATCGGGTACG AGGCTGACTGACAGGCTGACTGACTGACTGACTGACTGACGACCTGACTGACTGAC..</td></tr><tr><td>2</td><td>TCGACGTGGAGGCCCTTAGGCCTTCCTTAGGCAGGCAGGCCCTTAGGCAGGCAGGCAGCAGGC.</td></tr><tr><td>3</td><td>TGCGATGCAC TCGCTCGCTCGCTCGCTCGCTCGCCCATCCATTCGCTCGCCATCCATTCGCTCG...</td></tr><tr><td>4</td><td>CGCGCGCTATAGAAAGAAAGAATGACAGAATGACTGACTGACTGACTGACAGAATGACAGAAAGAA.. TGATAGCATG</td></tr><tr><td>5</td><td>TIAAGGGATGTTTACTATCTATCTATCTATTTTATTTATTATTATTTATTTCTTTCTTTCTTC..</td></tr><tr><td>6</td><td>TAGATAGTCCTTTGTTTGATACATACTTTGATACATACTTTGATACATACTTTGTTTGATACTTTG.. GGTATCGCCC</td></tr><tr><td>7</td><td>AAACCTGGGAGCGAACCGACCGACCGGCGAGCGAGCGAGCGAGCGAGCGAACCGACCGACCGTCGG..</td></tr><tr><td>8</td><td>GTGTGACGAG TTAATTAAGACGTTAATTAATTAATTAAGGACGGACGGACGGACGGACTTAAGGAC.. ATGCGCTAAG</td></tr><tr><td>9</td><td>GGGTTCGAAATTCATTCATTCAGTCAGTCATTCATTCATTCACTAGCTAGTTCATTCATTCATTCA...</td></tr><tr><td>10</td><td>TAGCTGTGATGGGAGGGAGGGAGGGATGTTTGTTTGTTGGGAGGGAGACTGACTGGGAGGGAGGGA.. CCCGGAGAGT</td></tr></table></body></html>

表5加密过程数据处理  
a)Lena图像中部分像素二进制矩阵  

<html><body><table><tr><td>0000 1011</td><td>0011 0011</td><td>0111 1001</td></tr><tr><td>00001000</td><td>00110000</td><td>0111 1000</td></tr><tr><td>0000 1010</td><td>00011100</td><td>0110 1010</td></tr><tr><td>0000 1100</td><td>00011101</td><td>0110 1000</td></tr><tr><td></td><td>b）明文二进制对应DNA序列</td><td></td></tr><tr><td>第一行二进制数</td><td></td><td>对应DNA序列</td></tr><tr><td>00001011 00110011 01111001</td><td></td><td>AATTAATTCCCGGTACAATTGTACA ATTGTACCCCGGTACCTTTCCCG</td></tr><tr><td></td><td>c)第一行密钥分配和计算后的密文结果</td><td></td></tr><tr><td>引物序列 密钥序列</td><td>DNA 密文序列</td><td>对应密文二进制数</td></tr><tr><td></td><td></td><td>0011101101110111</td></tr><tr><td></td><td>AGGCTGACTGACAG AGCGTGTGGTCT1101100111101111</td><td></td></tr><tr><td></td><td>ATCGCGTACG-GCTGACTGACTGACTGCGGTGTGCCAA0111011110100000</td><td></td></tr><tr><td>TTAAGCCTGT</td><td>GACTGACTGACGAC AGTGCCAAGTCT0011011110100000</td><td></td></tr><tr><td></td><td>CTGACTGACTGAC</td><td>CCAATTGGGTCT1101100110100000 0101111111011001</td></tr></table></body></html>

表5中,a)图为原始Lena图像转化得到的部分二进制序列，以a)中第一行明文为例，与密钥本中对应的加密钥进行加密操

作，数据处理结果如表5b)和c)所示。图像加解密的具体操作流程如图1所示，加密前后图像对比如图2所示。

![](images/41c0a071233cd47c0e651a41e47c348672505619e1a8e694548f506ca2149773.jpg)  
b）解密流程图

![](images/9edf055bd106b2d158683a409a04934b8d95258ed2eb4ad091eb161865a6a54e.jpg)  
图1加解密流程图

# 5 算法分析

# 5.1 密钥空间分析

密钥空间大小和算法抵抗穷举攻击能力的大小密切相关，密钥空间越大，算法抵抗穷举攻击能力越大。本文密钥空间参数有以下几种：

a）密文二进制到DNA的转化对应关系为编码规则I，不考虑互补性， $R _ { I }$ 的选择有 $N _ { \mathfrak { r } }$ 种，则

$$
N _ { 1 } = 2 4
$$

b）明文转换规则 $R _ { 2 }$ 选自编码规则 $\mathrm { I I }$ ，设有 $N _ { \scriptscriptstyle 2 }$ 种：

$$
N _ { 2 } = 4 ^ { 4 } { = } 2 5 6
$$

c）密码本的制作也运用编码规则 $\mathrm { I I }$ ，与对明文的转化不同的是：二进制双比特可随机选择相同的四个碱基组合，即每个二进制双比特对应碱基组合的映射均有256种。 $, R _ { 3 }$ 的选择有 ${ \cal N } _ { 3 }$ 种，则

$$
N _ { 3 } = C _ { 2 5 6 ^ { 4 } } ^ { K }
$$

（4）第四个步骤中，假设引物的选择有 ${ { N } _ { 4 } }$ 种，则

$$
N _ { 4 } = C _ { 4 ^ { 1 0 } } ^ { 2 K }
$$

其次，本文利用Logistic 混沌映射系统生成随机数序列。此过程需要 $K$ 对 $( g _ { i } , \mu _ { i } )$ 作为密钥参数,相当于存在 $K$ 个密钥。将计算精度设置为 $1 0 ^ { - 1 4 }$ ，则参数对应密钥空间的大小为 $1 0 ^ { 1 4 \times K }$ ， $K$ 值取决于明文分段的个数 $s$ 。

![](images/0ddcb0dab8d23cd47a1e9df3decd180552f9ac93a1848383653c6fb3a2e97363.jpg)  
图2原图和密文图

第4节仿真实验中 $K = 3 2 0$ ，综上，总的密钥空间为

$$
N _ { 1 } \times N _ { 2 } \times N _ { 3 } \times N _ { 4 } \times 1 0 ^ { 1 4 \times K } = 3 \times 2 ^ { 1 1 } \times C _ { 2 5 6 ^ { 4 } } ^ { 2 5 6 } \times C _ { 4 ^ { 1 0 } } ^ { 5 1 2 } \times 1 0 ^ { 1 4 \times 3 2 0 }
$$

显然，该算法密钥足够大，可以抵抗穷举攻击。

# 5.2 密钥敏感度分析

Logistic混沌映射对系统参数十分敏感。在攻击者破译密钥本时，初始值即使有轻微的变化，解密出来的图像和原始图像就会有很大差距。以上述生成密钥本中的初始参数$g _ { 1 } = 0 . 5 0 4 , \mu _ { 1 } = 3 . 6 8$ 为例，若变为$g _ { 1 } = 0 . 5 0 4 0 0 0 0 0 0 0 0 0 1 , \mu _ { 1 } = 3 . 6 8 0 0 0 0 0 0 0 0 0 1$ ，从同样的位置截取二进制数，通过转换得到的DNA序列为AGGCTGACTGACTGACTGACAGGCTGACAGGCTGACTGACTGACTGACAGGCAGGC。

如图3所示，（a）是根据轻微变化所得密钥解密的图像，与（b）原始明文图像是完全不同的。

# 5.3 防统计攻击分析

灰度直方图是对图像中不同种类灰度的像素计数，是图像最基本的统计图。图4为原始图像加密前后的灰度直方图，可看出加密后的灰度值分布更均匀，和原图的直方图存在较大差异。因此，攻击者在密文图像中得不到任何有用的统计数据，这表明本文算法可以有效抵御使用数据的统计攻击。

![](images/035dce89bf04fe0c4669adcb05f627d2983ebd991bf9f1ed399680ae9acd4850.jpg)  
图3解密结果图  
b)密文图像直方图  
图4直方图比较

# 5.4信息熵分析

所谓信息熵，是一个度量信息量的概念。信息熵的值越高，表示一个信息越混乱，也可代表信息的不确定性更大。图像信息熵的计算公式如下：

$$
H ( x ) = - { \sum _ { i = 1 } ^ { 2 N - 1 } p ( x _ { i } ) \log _ { 2 } p ( x _ { i } ) }
$$

研究表明，密文图像的信息熵值 $H ( x )$ 越近于8，其灰度直方图的分布越均匀，表示加密效果更强。按照以上公式计算得到本文方案的 $H ( x ) = 7 . 9 4 3 3$ ，可见该算法对图像加密十分有效。

# 5.5效率分析

根据仿真实验设定的参数，在 $2 . 3 0 \mathrm { G H z }$ 处理器、4GB内存的PC机上对算法进行了运行测试，分别设定了三组不同大小的灰度图像作为测试对象，每组图像均进行了10轮实验测试，并对10轮测试的加解密执行时间进行了平均值计算。算法测试结果如表6所示。测试结果表明，对同一大小的数据加解密所耗费的时间基本相当，且随着数据量的增加，加解密所需耗费的时间也逐渐递增，但对三组不同大小图像的加解密时间均较短，在较为合理的范围内。

表6算法测试结果  

<html><body><table><tr><td>图像大小</td><td>加密/s</td><td>解密/s</td></tr><tr><td>64*64 (5,613 Byte)</td><td>0.3526914</td><td>0.3094166</td></tr><tr><td>128*128 (19,277 Byte)</td><td>0.3682398</td><td>0.3616362</td></tr><tr><td>256*256 (66,614 Byte)</td><td>0.4473368</td><td>0.5925266</td></tr></table></body></html>

# 6 结束语

本文提出了一种基于DNA密码的加解密算法，该算法具有以下几个特点：a)对原始数据的处理所设计的DNA编码规则种类增加;b)加密时对明文分段操作，每一段明文数据可根据随机引物对选择不同的密钥运算，即使获得密钥本，也无法降低破解密文的难度;c)密钥本的制作以Logistic 混沌逻辑映射为基础，满足生成序列的随机性，密钥本二进制到DNA序列的转换利用多碱基映射编码规则，双重保证安全性，且每次加解密使用的密钥本根据共享参数的变化而不同，可抵抗重放攻击;d)算法安全性不依赖算法本身的DNA运算操作，而是基于密钥本的制作规则，除了参数的获得外，还需要破解DNA 编码的映射规则;e)该算法的密钥空间随着明文数据量的增加而增大。

# 参考文献：

[1]陈霄.DNA 遗传算法及应用研究[D].杭州：浙江大学,2010.(Chen Xiao.DNA genetic algorithm and its application research [D]. Hangzhou: Zhejiang University,2010.)   
[2]Liu Qiuming,Wang Liman,Anthony G F,et al.DNA computing on surfaces [J].Nature,2000,403 (6766):175-9.   
[3]高琳，许进，张军英.DNA计算的研究进展与展望[J]．电子学报,2001, 29(7):973-977.(Gao Lin, Xu Jin, Zhang Junying.Research progress and Prospect of DNA computing [J].Acta Electronica Sinica,2001,29(7): 973- 977.)   
[4] 张成，杨静，王淑栋.DNA 计算中荧光技术的应用及其发展[J].计算 机学报，2009,32(12):2300-2310.(Zhang Cheng,Yang Jing，Wang Shudong. Application and development of fluorescence technology in DNA computing [J]. Chinese Journal of Computers,2009,32(12): 2300-2310.)   
[5]李一凡，吴燃峰，杨静，等．基于 DNA 核酶的分子加密系统[J]．信息 网络安全,2017(6):43-48.(Li Yifan,Wu Ranfeng,Yang Jing,et al.A molecular encryptionsystem based on DNAzyme [J]. Netinfo Security,2017 (6): 43-48. )   
[6] Adleman L M.Molecular computation of solutions to combinatorial problems [J]. Science New,1994,266 (5187): 1021.   
[7] Zhou Shihua,Wang Bin, Zheng Xuedong,et al. An image encryption scheme based on DNA computing and celular automata [J]. Discrete Dynamics in Nature and Society,2016,2016 (2): 1-9.   
[8]Agrawal A, Bhopale A, Sharma J, et al. Implementation of DNA algorithm for secure voice communication [J]. International Journal of Scientific & Engineering Research.2012,3 (6): 1-5.   
[9] 王子成，赵晓航，王宏，等．基于 DNA 密码的一次一密加密算法[J]. 计算机工程与应用,2014,50(15):97-100.(Wang Zicheng,Zhao Xiaohang, Wang Hong,et al.One-time-pad encryption algorithm based on DNA cryptography [J]. Computer Engineering and Applications,2014,50 (15): 97-100.)   
[10]魏广政，金鑫，赵耿，等．一种改进的基于 DNA 编码和混沌映射的图 像加密方法[J].计算机应用研究，2015,32（10):3049-3051.(Wei Guangzheng,Jin Xin, Zhao Geng,et al.An improved image encryption method based on DNA coding and chaotic mapping [J].Application Research of Computer, 2015,32 (10): 3049-3051.)   
[11] Zhang Qiang,Guo Ling,Wei Xiaopeng. Image encryption using DNA addition combining with chaotic maps [J]. Mathematical and Computer Modelling,2010,52 (11-12): 2028-2035.   
[12] Bonny B R,Vijay JF, Mahalakshmi T. Secure data transfer through DNA cryptography using symmetric algorithm [J]. International Journal of Computer Applications,2016,133 (2): 19-23.   
[13]陈惟昌，陈志华，陈志义，等．遗传密码和 DNA 序列的高维空间数字 编码[J]．生物物理学报,2000,16(4):760-768.(Chen Weichang,Chen Zhihua,Chen Zhiyi,et al. High dimensional spatial digital coding of genetic code and DNA sequence[J].Acta Biophysica Sinica,2000,16(4): 760-768.)