# 基于DNA编码和超混沌系统的图像加密算法

张勋才，刘奕杉，崔光照(郑州轻工业学院 电气信息工程学院，郑州 450002)

摘要：针对DNA编码规则单一和混沌加密算法对密钥的灵敏度低等问题。提出一种基于DNA编码和超混沌系统的图像加密方案。该算法首先使用SHA-3算法计算明文图像的哈希值，用于超混沌系统的初始值，增加明文敏感性；其次将图像转换为DNA序列，并与所构建的S盒子进行 DNA序列运算；最后用超混沌系统产生的序列对图像进行置乱。结果和理论分析表明，该算法不仅提高了密钥敏感性和传输数据的安全性，而且具有较好的抗穷举攻击、统计攻击和差分攻击能力。

关键词：图像加密；DNA编码；超混沌系统；S盒子；SHA-3   
中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2017.10.0997

# Image encryption algorithm based on DNA encoding and hyper-chaotic system

Zhang Xuncai, Liu Yishan, Cui Guangzhao (CollegeofElectrical&InformationEngineering,Zhengzhou UniversityofLightIndustry,Zhengzhou450,China)

Abstract: Aimingatthedeficiencyof thesingleDNAencodingruleandchaoticencryptionalgorithmhaslowsensitivityto key. This paer proposed an image encryptionalgorithmbasedon DNA encodingand hyper-chaotic system.Firstly,the algorithm usedtheSHA-3algorithmtocalculatethehashvalueoftheplaintextimage,whichusedfortheinitialvalueofthehyper-chaotic systemandincreases thesensitivityofplaintext.Secondly,the itconverted image into DNAsequenceand performed theDNA sequenceoperation with theconstructed S-box.Finally,itscrambled the image bythesequence produced byhyper-chaotic system.The simulationresultsandtheoreticalanalysis showthatthe algorithmimproves thesensitivityofkeyandthe security of data transmission,and has better ability of anti-exhaustive attck,statistical attack and diferential attack.

ey Words: image encryption; DNA encoding; hyper-chaotic system; S-box; SHA-3

# 0 引言

近年来图像传输在医学影像、在线教学、通信等各个领域中被广泛使用。然而网络的开放性和共享性使得图像传输的安全性遭到巨大威胁。2013年的“棱镜门”事件让人们意识到解决信息安全传输问题刻不容缓。图像加密技术是保护图像安全传输的一种有效方案。由于图像具有高冗余度、大数据容量、像素之间相关性强等特点，所以图像加密需要使用快速的算法[1\~4]。传统的加密方法，如DES、AES 和 RSA等已经不能满足当前的图像加密。

近年来学者们提出了一些新的图像加密算法，如基于混沌理论的图像加密方法[5\~8]和基于DNA序列的图像加密方法[9]。混沌系统具有良好的伪随机特性、轨道的不可预测性、对初始状态及控制参数的敏感性等一系列特性。这些特性与密码学的很多要求是吻合的。也正因为混沌与密码学之间有着密切的联系，所以混沌密码学得到了大量的研究，并应用于图像的加密中[10,11]。但是低维混沌系统产生的混沌只可短期预测，混沌序列随机性往往较差，加密图像密钥空间小，安全性能低，易于破译[12,13]。为扩大密钥空间和增加混沌序列的随机性，学者们设计了基于超混沌[14,5]、多级混沌[16,17]等图像加密算法。目前超混沌已广泛应用于非线性电路、安全通信、激光、神经网络、生物系统等领域。但随着密码分析技术的提高，超混沌加密技术也暴露出了对密钥的低敏感性等问题。

DNA分子所固有的超大规模并行性、超低的能量消耗和超高的存储密度，使得基于DNA计算的图像加密算法具有传统密码算法所不具有的独特优势[18\~20]。因为生物实验耗费巨大，Ning 等人提出一种伪DNA加密方法。该方法利用DNA计算中所涉及的基本思想，在电子计算机上模拟信息加密，但该方法不太适用于图像加密。2010年薛等人提出了一种基于DNA编码与混沌序列相结合的加密方法。该方法利用DNA编码和超混沌系统对初始条件的敏感性和高度随机性提供了很好的加密效果。文献［21]提出一种基于混沌和DNA动态编码的图像加密算法，该算法加入了动态DNA编码规则，但是加密过程中DNA运算规则单一。文献［22］提出一种基于DNA序列的彩色图像加密算法，该算法在位平面进行DNA 编码，但是编码与解码方式单一。文献[23]指出采用固定编码和单一运算规则的DNA混沌图像加密算法容易通过选择明文攻击进行破解。文献[24\~26提出了改进的基于编码和多混沌映射的图像加密算法，用超混沌系统置乱像素位置和像素值，用DNA编码规则编码进行伪DNA运算，最后通过DNA解码获得加密图像。文献[27]指出当前基于DNA 编码和混沌理论对真彩图的加密算法对明文攻击的脆弱性，加密算法中存在对明文的低敏感性和对密钥的低敏感性等不足之处。文献[28]研究发现当算法加密过程与明文无关时，算法无法有效抵抗已知明文和选择明文攻击。

为此，本文结合超混沌系统、DNA计算和哈希函数对图像进行分块加密，使用哈希函数SHA-3对原图像进行处理，进而获得超混沌系统的初始值以及与原图像异或的图像矩阵，将原图像与密钥的获得联系在一起，再利用超混沌系统产生的超混沌序列值，构造S盒子，使用S盒子对图像进行加、减和移位等操作。该算法不仅能有效提高密钥敏感性、传输数据的安全性，还能有效地抵抗已知明文和选择明文攻击，而且具有较好的抗穷举攻击、统计攻击和差分攻击能力等。

# 1 混沌系统与DNA编码

# 1.1超混沌LU系统

2005年，文献[29]给出了超混沌吕系统的详细描述：

$$
\left\{ \begin{array} { l l } { \dot { x } = a ( y - x ) + u } \\ { \dot { y } = - x z + c y } \\ { \dot { z } = x y - b z } \\ { \dot { u } = x z + d u } \end{array} \right.
$$

其中：参数 $\ a , \ b , \ c$ 为吕系统的参数；参数 $d$ 是待定的控制增益参数； $x , \ y , \ z , \ u$ 是变量。当 $a { = } 3 6$ ， $b = 3$ ， $c { = } 2 0$ ， $- 0 . 3 5 { < } d { \leqslant }$ 1.3时，上述系统处于超混沌状态。

# 1.2 DNA编码与运算

1)DNA 编码

DNA 是一种由脱氧核糖核酸作为基本单位的高分子聚合物。而脱氧核苷酸则是由三部分组成，分别为一分子的磷酸、一分子的脱氧核糖和一分子的含氮碱基。含氮碱基共有四种类型，即腺嘌呤(A)、胞嘧啶(C)、鸟嘌呤(G)、胸腺嘧啶(T)。其中A与T、G与C分别是两两互补的关系[30]。灰度图像的每一个像素可用8位二进制数表示，而二进制数中0和1互补，所以00和11、01和10也是分别互补的。因此，如果用四个脱氧核苷酸A、T、C、G分别表示二进制数00、11、01、10，则每一个像素值就可以用长度为4的DNA序列来表示。例如十进制值200表示为 $( 1 1 0 0 1 0 0 0 ) _ { 2 }$ ，被转换为4位DNA序列是TAGA。满足DNA碱基之间互补关系的编码规则有八种，如表1所示。

表1八种DNA 编码规则  

<html><body><table><tr><td colspan="7">规则1 规则2 规则3 规则4 规则5 规则6 规则7 规则8</td></tr><tr><td>00-A</td><td>00-A</td><td>00-C</td><td>00-C</td><td>00-T</td><td>00-T</td><td>00-G</td><td>00-G</td></tr><tr><td>01-C</td><td>01-G</td><td>01-T</td><td>01-A</td><td>01-C</td><td>01-G</td><td>01-A</td><td>01-T</td></tr><tr><td>11-T</td><td>11-T</td><td>11-G</td><td>11-G</td><td>11-A</td><td>11-A</td><td>11-C</td><td>11-C</td></tr><tr><td>10-G</td><td>10-C</td><td>10-A</td><td>10-T</td><td>10-G</td><td>10-C</td><td>10-T</td><td>10-A</td></tr></table></body></html>

2)DNA序列的运算

DNA序列的加减法类似于传统的代数计算。当用00-A、11-T、01-C、10-G进行编码时，碱基之间的加减法运算规则如表2所示。

表2DNA加减法则  

<html><body><table><tr><td>+</td><td>A</td><td>T</td><td>C</td><td>G</td><td></td><td>A</td><td>T</td><td>C</td><td>G</td></tr><tr><td>A</td><td>A</td><td>T</td><td>C</td><td>G</td><td>A</td><td>A</td><td>T</td><td>C</td><td>G</td></tr><tr><td>T</td><td>T</td><td>A</td><td>G</td><td>C</td><td>T</td><td>T</td><td>T</td><td>A</td><td>C</td></tr><tr><td>C</td><td>C</td><td>G</td><td>A</td><td>T</td><td>C</td><td>C</td><td>C</td><td>G</td><td>T</td></tr><tr><td>G</td><td>G</td><td>C</td><td>T</td><td>A</td><td>G</td><td>G</td><td>G</td><td>C</td><td>A</td></tr></table></body></html>

# 2 方案设计

通过采用超混沌系统、DNA编码和哈希函数对图像进行混淆和置乱来实现对图像的加密。

# 2.1对角线提取法

![](images/909076de59d55135898bae05aff7f80d6a3b491438df168382398efa4c8c8ccf.jpg)  
图1对角线示意图

对于大小为 $L ^ { * } L$ 的原始灰度图像(在此默认灰度图像为方阵图像，若加密图像不是方阵，则进行填补，填补规则在后面叙述)，定义图像的主对角线为diag(O)，主对角线以上平行于对角线每条线线依次定义为diag(-1)，diag(-2)，.， $\mathrm { d i a g } ( - L + I )$ 主对角以下平行于对角线的每条线定义为 diag(1),diag(2.)，.,diag(L-1)。定义方式如图1所示。

为了达到置乱的效果，本文重新组合像素的位置。从图中提取像素的规则如下：

$$
\scriptstyle \mathrm { X } _ { i } = \mathrm { d i a g } ( i ) + \mathrm { d i a g } ( - L + i )
$$

其中： $\scriptstyle { i = 0 }$ ，1，2，..， $_ { L - 1 }$ 。

举例：当 $\scriptstyle { i = 0 }$ 时， $\mathrm { X } _ { 0 } { = }$ diag(0) $+$ diag(-L)=diag(O);$\scriptstyle \mathrm { X } _ { 1 } = \mathrm { d i a g } ( 1 ) + \mathrm { d i a g } ( - L + I ) \circ$

按此方法，将每次提取出的 $L$ 个元素分别转换成 $\sqrt { L } * \sqrt { L }$

的图像子矩阵，由此将得到 $L$ 个 $\sqrt { L } * \sqrt { L }$ 的图像子矩阵。

# 2.2 SHA-3 算法

SHA-3算法基于海绵结构[31]，是现代密码学中最基本的模块之一，以任意长度的消息值作为输入，都将生成固定长度的HASH值。由哈希值产生的密钥，即使原图像有极其微小的变化，都将产生一个完全不同的加密密钥。因此这种加密方法能有效地抵抗蛮力攻击。

原始图像用SHA-3转换后，将产生出一组256位的哈希值： dbbf374d57de108723c923b41d768d018c8e538a2de7479962c487a0335e1e85；将生成的哈希值作为下次哈希函数的输入信息来产生新的哈希值。循环产生八次，共得到 $2 5 6 ^ { * } 8$ 位哈希值。选择一种DNA编码规则对所得到的哈希值进行编码，每8位哈希值一组进行编码，将 $2 5 6 ^ { * } 8$ 位哈希值编码后转换为$1 6 ^ { * } 1 6$ 的DNA编码矩阵。比如按第一种编码规则：$\mathrm { { d b } {  } 1 1 0 1 1 0 1 1 {  } \mathrm { { T C G T } _ { c } } }$ （204

# 2.3 密钥的产生

利用SHA-3产生的第一组哈希值作为密钥 $K$ ，用于产生混沌系统的初始值。将 $K$ 按字节划分，可表示为 $k _ { 1 }$ $k _ { 2 } , \ k _ { 3 } ,$ …,$k _ { 3 2 }$ 。通过式(3\~6)来计算混沌系统的初始值。

$$
{ x } _ { 1 } { = } ( k _ { 1 } \oplus k _ { 2 } \oplus . . . . . \oplus k _ { 8 } ) / 4 { + } x _ { 0 }
$$

$$
y _ { 1 } = ( k _ { 8 } \oplus k _ { 9 } \oplus . . . . . \oplus k _ { 1 6 } ) / 4
$$

$$
z _ { 1 } { = } ( k _ { 1 6 } \oplus k _ { 1 7 } \oplus . . . . . \oplus k _ { 2 4 } ) / 4
$$

$$
\boldsymbol { u } _ { 1 } \mathrm { = } ( k _ { 2 4 } \oplus k _ { 2 5 } \oplus . . . . . \oplus k _ { 3 2 } ) / 4
$$

其中： $x _ { 1 }$ 、y1、z1、 $u \mathrm { 1 }$ 为超混沌吕系统的初始值； $x _ { 0 }$ 位给定值。

通过这种方式生成的密钥具有良好的随机性、周期性以及长密钥空间性等优势。将原图像信息与密钥相结合，算法将有效抵抗已知明文和选择明文攻击。

# 2.4 S盒子

设定超混沌吕系统中的控制参数 $\scriptstyle \mathtt { a } = 3 6$ ， $\scriptstyle \mathbf { b } = 3$ ， $\scriptstyle { \mathsf { c } } = 2 0$ ， $\mathrm { d } { = } 1$ ，采用2.3节得到的初始值，用超混沌吕系统生成四组超混沌序列，并用生成的混沌序列构造S盒子。其步骤如下：

a)构造一个空序列 $\mathbf { M }$ 。

b)将区间[0，256]划分成 256个子区间[(0，1)，..，(i,$j { + } 1 )$ ，.，((255，256)]，并用 $T _ { j }$ 表示j=(0，1，2...，255)，如图2所示。

![](images/a791b23572931d387b75b133cbe61cbfa63595539f692b1248ee0d04f14b564a.jpg)  
图2子区间与整数值之间的对应关系

c)超混沌吕系统迭代 $i$ 次得到的状态值 $x _ { i }$ ， $y _ { i }$ ， $z _ { i }$ 和 $u _ { i }$ 。通过式（7）～（10）对产生的混沌序列进行预处理，得到最终值

$$
\begin{array} { l l l } { { f ( x _ { i } ) \setminus f ( y _ { i } ) \setminus f ( z _ { i } ) \setminus f ( u _ { i } ) \circ } } & { { } } & { { } } \\ { { } } & { { } } & { { f ( x _ { i } ) { = } { \bmod { ( } } x ( i ) ^ { * } 1 0 0 0 , \ 2 5 5 ) \ } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { f ( y _ { i } ) { = } { \bmod { ( } } y ( i ) ^ { * } 1 0 0 0 , \ 2 5 5 ) \ } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { f ( z _ { i } ) { = } { \bmod { ( } } z ( i ) ^ { * } 1 0 0 0 , \ 2 5 5 ) \ } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { f ( u _ { i } ) { = } { \bmod { ( } } u ( i ) ^ { * } 1 0 0 0 , \ 2 5 5 ) \ } } \end{array}
$$

d)若 $f ( { \boldsymbol { x } } _ { i } )$ 位于第 $j$ 个子区间 $( j , \ j { + } 1 )$ ，且 $j$ 不存在于序列M中，则在序列M中加上 $j$ ，其他依此类推。

e)如果在序列 $\mathbf { M }$ 中的元素个数小于256,继续步骤c)和d)，直到序列M中的元素个数为 $2 5 6 .$ 0

f)将序列 $\mathbf { M }$ 中的256个元素转换成 $1 6 ^ { * } 1 6$ 的矩阵，得到一个 $1 6 ^ { * } 1 6$ 的S盒子。依照这种方法构造16 个 $1 6 ^ { * } 1 6$ 的S盒子,并进行顺序编码。例如，通过初始值迭代超混沌吕系统生成的值233.6，这个值位于子区间于233\~234中，属于T233。若233不在序列M中，则把该值添加到序列M中，并进行DNA 编码。

# 2.5加密方案

该加密算法主要内容是首先将原始图像按2.1节所示的提取规则分割成L个子图像矩阵，其次将 SHA-3 算法产生的哈希值编码后与DNA编码过的子图像矩阵进行DNA编码运算，最后用超混沌吕系统生成的序列值所构造的S盒子对图像进行置换与置乱等加密。加密流程如图3所示。具体步骤如下：

a)输入8位灰度图像 $\operatorname { I } ( m , ~ n )$ 。将图像按以下规则进行补图得到图像I $( L , \ L )$ ：

$$
L = \operatorname* { m a x } ( \left\lfloor ( { \sqrt { m } } ) ^ { 2 } \right\rfloor , \left\lfloor ( { \sqrt { n } } ) ^ { 2 } \right\rfloor )
$$

其中： $\left\lfloor ( { \sqrt { m } } ) ^ { 2 } \right.$ 为 $\lfloor ( { \sqrt { m } } ) ^ { 2 }$ 上取整。

b)将图像依照 2.1节所示方法转换成 $L$ 个 $\sqrt { L } * \sqrt { L }$ 的图像子矩阵。

c)对图像子矩阵的每个元素进行DNA编码。

d)将通过2.2节得到的大小为 $1 6 ^ { * } 1 6$ 的DNA编码矩阵，与步骤c中得到的 $L$ 个图像子矩阵根据表2中的规则进行DNA序列运算。

e)用2.4节中构造的16个S盒子与步骤d)中所得的L个图像子矩阵根据表2中的规则进行DNA编码运算。再对进行运算后的L个图像子矩阵进行左循环移3位加密操作（根据多次实验，循环移3位效果最佳。）

f)提取超混沌序列 $f ( x _ { i } ) , f ( y _ { i } )$ 的前1/2的奇数位相加，序列$f ( z _ { i } ) , f ( u _ { i } )$ 的前1/2的偶数位相加组合成新的混沌序列 $G$ ，对该混沌序列取模256，顺序提取该序列的 $L$ 个数，提取 $L$ 组，分别为 $G _ { 1 }$ 、 $G _ { 2 } { \cdots } G _ { \mathrm { { L } } }$ ，将每组 $L$ 个数转换为 $\sqrt { L } * \sqrt { L }$ 的矩阵，将 $L$ 个矩阵转换为二进制并选择一种DNA 编码规则进行编码，再与步骤e)所得的L个 $\sqrt { L } * \sqrt { L }$ 图像子矩阵根据表2中的DNA编码运算规则进行运算。

g)将步骤f)所得的 $L$ 个图像子矩阵合成一个图像矩阵 $I _ { 1 }$ 。

h)根据式(12)产生的矩阵C，将矩阵 $I _ { 1 }$ 与C 根据表2中的规则进行DNA序列运算，得到一个图像矩阵 $I _ { 2 }$ 。

$$
C { = } L ^ { \ast } L ^ { \ast } ( \mathrm { x } ( L + j ) { + } 0 . 5 ) ) ^ { \ast } \mathrm { o n e s } ( L , 1 )
$$

其中:j=1，2，3，…，256。

i)提取超混沌序列 $f ( x _ { i } ) \lrcorner f ( y _ { i } )$ 前1/2的偶数位相加，序列 $f ( z _ { i } )$ 、$f ( u _ { i } )$ 前1/2的奇数位相加组合成新的混沌序列 $G _ { 0 }$ ，按从小到大的顺序排列，得到新序列，用新序列各元素所在的位置之值替换原序列中的该元素，得到新序列的索引，用新序列索引对图像矩阵 $I _ { 2 }$ 进行置乱，得到图像 $I _ { 3 }$ 。

j)对图像 $I _ { 3 }$ 进行DNA解码，得到加密图像 $I _ { 4 }$ 。

解密算法是加密算法的逆过程。在此不再详述。

![](images/b2683ee5b9deb44cd32bbbcba56e25a749c65a6b95058ad0938cc447998ff07d.jpg)  
图3加密流程

# 3 仿真实验

在MATLAB7.1环境下对本文提出的算法进行仿真。原始图像采用标准的 $2 5 6 ^ { * } 2 5 6$ 的Lena灰度图像，在 $\scriptstyle x _ { 0 } = 1$ 的条件下,该算法的实验结果如图4所示。

![](images/086fa196ec3e0b78b56ded0df372d6cf90bd8d5126a817b55a155a20aa5e6b9b.jpg)  
图4图像加密、还原前后对比

# 4 安全性分析

算法的安全性分析主要包括密钥空间、灵敏性分析及抗统

计攻击分析等。

# 4.1穷举攻击分析

1)密钥空间分析

在本算法中，密钥包含： $x _ { 1 } , y _ { 1 } , z _ { 1 } , u _ { 1 }$ 、SHA-3函数的256个字节。如果 $x _ { 1 }$ 、y1、z1、 $u _ { 1 }$ 的计算精度为 $1 0 ^ { 1 4 }$ ，吕系统的密钥空间为 $1 0 ^ { 1 4 } { \times } 1 0 ^ { 1 4 } { \times } 1 0 ^ { 1 4 } { \times } 1 0 ^ { 1 4 } { = } 1 0 ^ { 5 6 }$ ，SHA-3 的密钥空间为 $2 ^ { 1 2 8 }$ 。总的密钥空间为 $1 0 ^ { 5 6 } { \times } 2 ^ { 1 2 8 } { \approx } 3 . 4 { \times } 1 0 ^ { 9 4 }$ 可见该算法具有足够大的密钥空间来抵抗穷举攻击。

2)密钥的灵敏度分析

为测试密钥的灵敏性，用微小差异的密钥进行解密。图 5(a)表示 $\scriptstyle x _ { 1 } = 3$ 其他密钥不变的解密图； (b)\~(d)分别表示 $y _ { 1 } { = } 1 0$ $z _ { 1 } = 3 0$ ， $u _ { 1 } { = } 2$ 其他密钥不变的解密图。只要密钥有的小差异，原始图像将不能正确解密，且错误解密图像不能反映原始图像的信息。因此，可以得到该算法具有密钥的敏感性，并能有效抵抗暴力攻击。

![](images/fd47b6699b3fbe667298d18a1e4055e4caea83be828dab7219dd968d001a1b3b.jpg)  
图5错误密钥下的解密图像

# 4.2 统计攻击分析

1)直方图分析

对于原始图像和加密图像的统计分析，分析其统计特性。图6(a)给出了原始图像直方图，(b)给出了加密图像直方图。原始图像象素值比较集中，而加密图像的直方图基本上是均匀的，攻击者难以利用像素灰度值的统计特性恢复原图像。由此可见该算法具有很好的抗统计分析能力。

![](images/ab3976dcd7bc41ff2df3ef9071ae35cae7543d947aefa5c708ef9d2d9776f1d9.jpg)  
图6灰度直方图分析

# 2)相关性分析

从原始图像和加密图像中随机的选取在水平方向、垂直方向以及对角方向上2500 对相邻像素点，然后利用式(13\~16)计算像素间的相关性。

$$
E ( x ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } x _ { i }
$$

$$
D ( x ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( x _ { i } - E ( x ) ) ^ { 2 }
$$

$$
C O V ( x , y ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( x _ { i } - E ( x ) ) ( { \bf y } _ { i } - E ( x ) )
$$

$$
\mathbf { r } _ { x y } = \frac { C O V ( x , \ y ) } { \sqrt { D ( x ) } \times \sqrt { D ( y ) } }
$$

其中： $x$ 和 $y$ 是图像中相邻像素的灰度值； $\operatorname { c o v } ( x , y )$ 是协方差；$D ( x )$ 是方差； $E ( x )$ 是平均值。类似地，其他结果如表3所示。图7显示了原始图像和加密图像水平方向、垂直方向、对角线方向相邻像素的相关性。加密图像的相邻像素的相关系数为-0.0005348。因此，该图像加密算法具有较强的抗统计攻击能力。

表3原始图像和加密图像中两个相邻像素相关系数对比  

<html><body><table><tr><td>相关系数</td><td>原始图像</td><td>加密图像</td></tr><tr><td>水平</td><td>0.9684</td><td>-0.0060</td></tr><tr><td>垂直</td><td>0.9394</td><td>-0.0038</td></tr><tr><td>对角线</td><td>0.9172</td><td>-0.0033</td></tr></table></body></html>

3)信息熵

信息熵被定义为描述系统的不确定性的程度，可以用来表示图像信息的不确定性。图像灰度值分布越均匀，其信息熵越大。其公式如下：

$$
H ( m ) = - { \sum _ { t = 0 } ^ { t } } P ( m _ { i } ) \log _ { 2 } P ( m _ { i } )
$$

$P ( m _ { i } )$ 是信息 $m _ { i }$ 出现的概率。对于灰度图像来说，信息 $\mathbf { \nabla } _ { m }$ 有256 种状态，最小值0，最大值为255。一个理想的随机图像，信息熵的值是8。实验的信息熵7.9897，说明该加密算法的有效性。

# 4.3 差分攻击分析

差分攻击是指攻击者通过对明文稍微改变，比较相应密文改变前后的差异，然后找出相应明文图像和密文图像的关系。通常采用NPCR(像素改变率)和UACI(像素平均改变强度)指标用来检测图像加密方案抵抗差分攻击的能力。采用下面的公式计算NPCR和UACI:

$$
\ N P C R = \frac { \displaystyle \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { N } C ( i , j ) } { M \times N } \times 1 0 0 \%
$$

$$
\mathit { U A C I } = \frac { \underset { \sum } { M } \sum _ { j } ^ { N } \left| P _ { 1 } ( i , j ) - P _ { 2 } ( i , j ) \right| } { 2 5 5 \times M \times N } \times 1 0 0 \%
$$

$$
C ( i , j ) = \left\{ \begin{array} { l l } { 0 , i f . . P 1 ( i , j ) = P 2 ( i , j ) } \\ { 1 , i f . . P 1 ( i , j ) \neq P 2 ( i , j ) } \end{array} \right.
$$

其中：M和N分别代表图像的长度和宽度； $\mathrm { P } _ { 1 } ( i , j )$ 和 $\mathbf { P } _ { 2 } ( i , \ j )$ 分别表示明文改变前后相对应的密文像素值。NPCR值越接近于 $100 \%$ ，说明图像加密方案对明文图像敏感性越高，其抵抗差分攻击的能力越强。UACI的理想值为 $3 3 \%$ ，其越接近于理想值，则说明抵抗差分攻击的能力也越强。

![](images/b6e130d96380feac07d0d6855fa71fa941ea4075b206039e5b45eb6b9c976bbf.jpg)  
图7原始图像与加密图像在水平方向、垂直方向、对角线方向的两个相邻像素的相关性

改变明文图像中某一个像素值，如位置为(7，8)的像素值由128 改为30，然后根据上式可计算出 $\mathrm { N P C R } { = } 9 9 . 5 9 5 6 \%$ ，UACI$= 3 3 . 3 9 \%$ 。由此可见，NPCR接近于 $100 \%$ ，并且UACI值也接近于 $33 \%$ ，这验证了该图像加密方案具有抵抗差分攻击的能力。

# 5 结束语

本文提出了一种基于DNA编码和超混沌相结合的图像加密算法，该算法通过采用DNA编码规则，并使用SHA-3算法提高了密钥空间；其次使用超混沌序列增加了本算法的复杂度和密文的不可预测性；最后S盒子的使用为本算法提供了双重安全性。实验分析表明，该算法不仅具有较好的加密效果，对密钥的敏感度较高；还可以有效抵抗穷举攻击、统计攻击和差分攻击。

# 参考文献：

[1]朱淑芹，李俊青，王文宏．对改进的基于DNA 编码和混沌的图像加密算法的安全性分析[J].计算机应用研究,2017,34(10):3090-3093

[2]Van Droogenbroeck M.Partial encryption of images for real-time applications [C]// Proc ofthe 4th IEEE Signal Processing Symposium. 2004: 11-15.   
[3]Seripeariu L,Frunza M D.A new image encryption algorithm based on inversable functions defined on galois fields [C]//Proc ofIEEE International Symposium on Signals, Circuits and Systems.2005: 243-246.   
[4] Chen RJ,Lai Y T,Lai JL.Architecture design of the re-configurable 2-D Von neumann celllar automata for image encryption application [C]// Proc of IEEE International Symposium on Circuits and Systems. 2005:3059- 3062.   
[5]Zhen W, Xia H, YuxiaL,etal.Anewimage encryptionalgorithmbasedon the fractional-order hyperchaotic Lorenz system [J]. Chinese Physics B, 2013,22 (1).   
[6]Wang X,Teng L, Qin X. A novel colour image encryption algorithm based on chaos [J]. Signal Processing,2012,92(4):1101-1108.   
[7]Guesmi R,Farah MA B,Kachouri A,et al.A novel chaos-based image encryption using DNA sequence operation and secure hash algorithm SHA2[J]. Nonlinear Dynamics,2016,83(3): 1123-1136.   
[8]Wang X,Wang X, Zhao J. Chaotic encryption algorithm based on alternant of stream cipher and block cipher[J].Nonlinear Dynamics,2011,63,587- 597.   
[9]Wei X,Guo L, Zhang Q,et al.A novel color image encryption algorithm based on DNA sequence operation and hyper-chaotic system [J]. Journal of Systems and Software,2012,85 (2): 290-299.   
[10] Zhang Y, Tang Y.A plaintext-related image encryption algorithm based on chaos [J]. Multimedia Tools and Applications,2017:1-23.   
[11] AkhavanA,Samsudin A,Akhshani A.Cryptanalysis ofan image encryption algorithm based on DNA encoding [J]. Optics & Laser Technology,2017, 95: 94-99.   
[12] Alvarez G,Montoya F,Romera M,etal. Cryptanalysis ofan ergodic chaotic cipher [J].Physics Letters A,2003,311 (2): 172-179.   
[13] Elnashaie S,Abashar ME.On the chaotic behaviour of forced fluidized bed catalytic reactors [J]. Chaos,Solitons & Fractals,1995,5(5): 797-831.   
[14] Liu W, Sun K, Zhu C.A fast image encryption algorithm based on chaotic map [J].Optics & Lasers in Engineering,2016,84: 26-36.   
[15]朱从旭，胡玉平，孙克辉．基于超混沌系统和密文交错扩散的图像加密 新算法[J]．电子与信息学报,2012,34(7):1735-1743.   
[16] Gao Tiegang,Chen Zengqiang.A new image encryption algorithm based on hyper-chaos [J].Physics Letters A,2008,372 (4):394-400.   
[17] Kumar M,Iqbal A, Kumar P.Anew RGB image encryption algorithm based on DNA encoding and elliptic curve diffie-Hellman cryptography[J]. Signal Processing,2016,125: 187-202.   
[18] Zhou C, Wei X, Zhang Q,et al. DNA sequence splicing with chaotic maps forimage encryption [J]. Journal of Computational and Theoretical Nanoscience,2010,7(10): 1904-1910.   
[19]WangQ,ZhangQ，Wei X.Image encryption algorithm based on DNA biological propertiesand chaotic sys-tems[C]// Proc of the 15th International Conference on Bio-Inspired Computing:Theoriesand Applications (BIC-TA).2010: 132-136.   
[20] Adleman L.Molecular computation of solutions to combinatorial problems [J]. Science,1994,266 (5187): 1020-1024.   
[21]田海冰，雷鹏，王永．基于混沌和 DNA 动态编码的图像加密算法[J]. 吉林大学学报：工学版,2014,44(3): 801-806.   
[22]涂正武，金聪．基于DNA序列的彩色图像加密算法[J].计算机工程与 科学,2015,37 (10): 1933-1939.   
[23]Ozkaynak F, Yavuz S.Analysis and improvement of a novel imagefusion encryption algorithm based on DNA sequence operation andhyper-chaotic system[J]. Nonlinear Dynamics,2014,78 (2): 1311-1320.   
[24] Ozkaynak F, Ozer AB, Yavuz S. Security analysis of an image encryption algorithmbasedonchaosandDNAencoding[C]//Proc of the 21st Signal Processing and Communications Applications Conference. 2013: 1-4.   
[25] Zhang Q,LiuL,Wei X. Improved algorithm for image encryption based on DNA encoding and multi-chaotic maps [J].AEU-International Journal of Electronics and Communications,2014,68 (3): 186-192.   
[26] Kong L,LiL.A new image encryption algorithm based on chaos [C]/ Proc of the 35th Chinese Control Conference.2016: 4932-4937.   
[27] Liu Y,Tang J, Xie T.Cryptanalyzing aRGB image encryption algorithm based on DNA encoding and chaos map[J]. Optics & Laser Technology, 2014, 60: 111-115.   
[28]刘金梅，丘水生，刘伟平．基于超混沌系统的图像加密算法的安全性分 析术[J].计算机应用研究,2010,27(3):1042-1044.   
[29] Chen A,Lu J,Lu J,et al. Generating hyperchaotic Lu attractor via state feedback control [J].Physica A-statistical Mechanics and Its Applications, 2006: 364: 103-110.   
[30] Shiu H,Ng K,Fang J,et al. Data hiding methods based upon DNA sequences [J]. Information Sciences,2010,180(11): 2196-2208.Enayatifar R,Sadaei H J, Abdullah A H, et al. A novel chaotic based image encryption using a hybrid model of deoxyribonucleic acid and cellular automata [J]. Optics and Lasers in Engineering,2015: 71:33-41.