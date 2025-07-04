# 伽罗瓦域GF(2上高矩阵为密钥的HiII加密衍生

刘海峰aʰ，卢开毅‘，梁星亮b(陕西科技大学 a.电气与信息工程学院;b.文理学院，西安 710021)

摘要：针对传统的Hill加密算法仅是利用伽罗瓦域 $\mathrm { G F } ( \mathfrak { p } )$ 上可逆的数字方阵作为密钥矩阵与明文向量做模p乘法进行加密运算，提出了一种新的在伽罗瓦域 $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathrm { p } ( \mathrm { x } )$ 上以多项式高矩阵作为密钥矩阵的Hill加密衍生算法。在 Hill加密衍生算法中，明文向量为明文字符对应的多项式构成的多项式向量，随机选取密钥矩阵的一列作为加密时的平移增量，在 $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ 上进行密钥矩阵与明文向量的模8次不可约多项式 $\mathfrak { p } ( \mathbf { x } )$ 的乘法和加法，然后获得元素为多项式的密文向量，从而实现明文信息加密。当攻击者在不知道 $\mathfrak { p } ( \mathbf { x } )$ 、密钥矩阵以及随机抽取的平移向量的情况下由密文破解得到明文的难度更大，从而提高了伽罗瓦域 $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ 上Hill加密衍生算法的抗攻击能力。

关键词：伽罗瓦域 $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ ；Hill加密；多项式高矩阵；不可约多项式 中图分类号：TN918.4 doi: 10.3969/j.issn.1001-3695.2018.03.0228

# Hill encryption derivative algorithm in galois field $\mathrm { G F } ( 2 ^ { 8 } )$ with high-matrix as key matrix

Liu Haifenga, b, Lu Kaiyia, Liang Xingliangb (a.Collegeof Electrical & Information Engineering,b.Collegeof Arts& Sciences，Shannxi Universityof Science& Technology, Xi'an 710021,China)

Abstract: In traditional Hillencryptionalgorithm,the modulopmultiplicationof the invertible matrixand plaintext vectorin Galois field GF(P)is used tocalculate ciphertext vector,this paper proposed anew Hillencryptionderivative algorithm in galois field $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ , which took polynomial high-matrix as key matrix. In this new Hil encryption derivative algorithm, it composed plaintextvectorof polynomial derived from corrsponding plaintext,it selected a column of key matrix as translation increment randomly modulo eighth degree irreducible polynomial $\mathfrak { p } ( \mathbf { x } )$ multiplication of the polynomial high-matrix and plaintext vector in Galois field $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ was done,then modulo eighth degree irreducible polynomial $\mathfrak { p } ( \mathbf { x } )$ addition of the product and translation increment in Galois field GF(2) $[ \mathrm { x } ] / \mathrm { p } ( \mathrm { x } )$ was carried out,thus it obtained the polynomialciphertext vector,andachievedthepurposeofencryptingtheplaintextmessagesecauseitismore diiculttoget plaintext from ciphertext under the condition that $\boldsymbol { \mathrm { p } } ( \mathbf { x } )$ ,key matrix and random selected translation vector are unknown, the new Hill encryption derivative algorithm in Galois field $\mathrm { G F } ( 2 ) \left[ \mathrm { x } \right] / \mathrm { p } ( \mathrm { x } )$ improve the capability for anti-attack.

Keywords: Galois field $\mathrm { G F } ( 2 ) [ \mathrm { x } ] / \mathsf { p } ( \mathrm { x } )$ ; Hill encryption; polynomial high-matrix; irreducible polynomial

# 0 引言

伽罗瓦域亦称有限域[1,2]，其域的元素是有限的。传统的Hill加密算法将英文字母、数字以及常见的符号构成编码字符集，编码字符集的基数为 $p$ ，以一定的规则进行编码，并对应到 $0 \sim$ $_ { p - 1 }$ 之间的整数。但是如果编码字符集的基数 $p$ 不为素数[3],还需要注意到必须要使得加密矩阵行列式的值在模 $p$ 下有乘法逆元。文献[4,5]给出了在模26情况下的数字方阵作为密钥矩阵所需要满足的要求，并给出了在模26意义下选取密钥矩阵的方法。文献[6]针对密钥矩阵在模26意义下的逆矩阵可能是分数的问题提出了行列变换的改进；当 $p$ 为素数时，可以得到一个具有 $p$ 个元素的伽罗瓦域 $G F ( p )$ ，但其上的Hill加密的密钥矩阵仍然十分脆弱。

伽罗瓦域 $G F ( 2 ^ { 8 } )$ 是一种特殊的有限域[7]，其具有 $2 ^ { 8 }$ 个元素，而不是像有限域 $G F ( p )$ 上必须有 $p$ 个元素( $p$ 为素数)。有限域 $G F ( 2 ^ { 8 } )$ 上每个元素都可以表示为8位的二进制数，并可以将元素唯一地映射为一个系数为0、1的8次以下的一元多项式，其有限域上多项式的加法和乘法等运算具有封闭性，在密码学、信息编码等领域都是很重要的数学工具[8]，有限域$G F ( 2 ^ { 8 } )$ 的算术运算还具有一定复杂性和特殊性，相比于传统的

HilI加密而言在很大程度上提高了算法的安全性。

本文论述有限域 $G F ( 2 ^ { 8 } )$ 上的Hill加密是对传统Hill加密的衍生，把有限域 $G F ( 2 ^ { 8 } )$ 上互为伪逆的一对矩阵作为加密和解密密钥，能满足安全密码系统的基本条件。本文选取空格和255个互异的可见字符进行字符编码，如表1所示，并按照 $0 \sim 2 5 5$ 的顺序对表格中的字符按照行优先进行编码。

表1字符编码  

<html><body><table><tr><td>space</td><td>a</td><td>b</td><td>C</td><td>d</td><td>e</td><td>f</td><td>g</td><td>h i</td><td>j</td><td>k</td><td>1</td><td>m</td><td>n</td><td>0</td><td>P q</td></tr><tr><td>r</td><td>s</td><td>t</td><td>u</td><td>V</td><td>W</td><td>X</td><td>y</td><td>Z A</td><td>B</td><td>C</td><td>D</td><td>E</td><td>F</td><td>G H</td><td>I</td></tr><tr><td>J</td><td>K</td><td>L</td><td>M</td><td>N</td><td>0</td><td>P</td><td>Q</td><td>R S</td><td>T</td><td>U</td><td>V</td><td>W</td><td>X Y</td><td>Z</td><td>0</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9 ！</td><td>@</td><td>#</td><td>$</td><td>%</td><td>^ &</td><td>*</td><td>（</td></tr><tr><td>）</td><td></td><td>一</td><td>=</td><td>+</td><td></td><td>/</td><td>I</td><td>]</td><td></td><td>，</td><td>：</td><td>/</td><td>{ 1</td><td>：</td><td>：</td></tr><tr><td></td><td><</td><td>></td><td>？</td><td>a</td><td>β</td><td>Y</td><td>8</td><td></td><td></td><td>0</td><td>1 K</td><td>入</td><td>μ</td><td>V</td><td></td></tr><tr><td>0</td><td></td><td>p</td><td>0</td><td>T</td><td>U</td><td></td><td>X</td><td>W</td><td>A</td><td>B</td><td></td><td>△</td><td>E Z</td><td>H</td><td>?</td></tr><tr><td>I</td><td>K</td><td>></td><td>M</td><td>N</td><td></td><td>0</td><td>II</td><td>P £</td><td>T</td><td>T</td><td></td><td>X</td><td>Ω</td><td>℃</td><td>F</td></tr><tr><td>I</td><td>II</td><td>IⅢI</td><td>IV</td><td>V</td><td>VI</td><td>VII</td><td>VIII IX</td><td>X</td><td>XI</td><td>XII</td><td>i</td><td>ii</td><td>ii iv</td><td>V</td><td>vi</td></tr><tr><td>vii</td><td>vi</td><td>ix</td><td>X</td><td>A</td><td>6</td><td>B</td><td>Γ</td><td>Ⅱ E</td><td>E</td><td>K</td><td>3</td><td>N</td><td>K</td><td>I</td><td>M</td></tr><tr><td>H</td><td>0</td><td>ⅡI</td><td>P</td><td>C</td><td>T</td><td>y</td><td></td><td>X L</td><td>4</td><td></td><td>E</td><td>b</td><td>bI b</td><td></td><td>IO</td></tr><tr><td></td><td>★</td><td>☆</td><td>▲</td><td>△</td><td>→</td><td><</td><td>■</td><td>□ 0</td><td>O ↑</td><td></td><td>『』</td><td></td><td></td><td></td><td>《》</td></tr><tr><td>（</td><td>）</td><td></td><td>「」</td><td>【</td><td>】 ：</td><td>f</td><td></td><td>￥ ↑ S ≤</td><td>W</td><td>→ 大</td><td>→</td><td>7</td><td>√</td><td>√</td><td>E</td></tr><tr><td>√</td><td>8</td><td>S</td><td>~</td><td>：</td><td></td><td></td><td></td><td></td><td></td><td></td><td>+</td><td>三</td><td></td><td>× ÷</td><td>士</td></tr><tr><td>·</td><td></td><td>M</td><td></td><td></td><td></td><td></td><td></td><td></td><td>(表中的 space 表示空格符)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 1 伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 的定义

$G F ( 2 ) [ x ]$ 的定义： $G F ( 2 ) [ x ]$ 指二元域 $G F ( 2 )$ 上的一元多项式全体的集合。

设 $p ( x )$ 是 $G F ( 2 )$ 上的一个8次不可约多项式，$G F ( 2 ) [ x ] / p ( x ) = < S , + , * , p ( x ) >$ 是一个代数结构，有$S = \{ a ( x ) { \mid } a ( x ) \in G F ( 2 ) [ x ] , \deg ( a ( x ) ) < 8 \}$ ，且 $G F ( 2 ) [ x ] / p ( x )$ 关于有限域上的加法构成阿贝尔群，其单位元为零多项式，$G F ( 2 ) [ x ] / p ( x ) - \{ 0 \}$ 关于有限域上的乘法 $" * "$ 构成阿贝尔群，且$" *$ 对 $" +$ "满足左右分配律，也即对 $\forall a ( x ) , b ( x ) , c ( x ) \in S$ ，本文记 $a ( x ) = \sum _ { i = 0 } ^ { 7 } a _ { i } x ^ { i }$ ， $b ( x ) = \sum _ { i = 0 } ^ { 7 } b _ { i } x ^ { i }$ ， $c ( x ) = \sum _ { i = 0 } ^ { 7 } c _ { i } x ^ { i }$ ，其中系数有$a _ { i } , b _ { i } , c _ { i } \in \{ 0 , 1 \}$ 满足左右分配律$( a ( x ) + b ( x ) ) * c ( x ) = a ( x ) * c ( x ) + b ( x ) * c ( x )$ ，$c ( x ) * ( a ( x ) + b ( x ) ) = c ( x ) * a ( x ) + c ( x ) * b ( x )$ 成立。考虑到 $G F ( 2 ^ { 8 } )$ （204号与 $G F ( 2 ) [ x ] / p ( x )$ 上的元素及其元素间相应的运算具有一一对应的同构的性质，因此从结构上讲，同构的对象是完全等价的，所以下文重点讨论 $G F ( 2 ) [ x ] / p ( x )$ 上的 Hill 加密衍生算法。伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上相应的运算定义如下：

$$
\begin{array} { c } { { a ( x ) + b ( x ) = \displaystyle \sum _ { i = 0 } ^ { 7 } ( ( a _ { i } + b _ { i } ) { \bmod { 2 } } ) x ^ { i } } } \\ { { { } } } \\ { { a ( x ) - b ( x ) = a ( x ) + b ( x ) } } \\ { { { } } } \\ { { a ( x ) * b ( x ) = ( \displaystyle \sum _ { i = 0 } ^ { 7 } \sum _ { j = 0 } ^ { 7 } ( ( a _ { i } \times b _ { j } ) { \bmod { 2 } } ) x ^ { i + j } ) { \bmod { p ( x ) } } } } \end{array}
$$

$a ( x ) ^ { - 1 }$ ：当且仅当 $a ( x ) \ast a ( x ) ^ { - 1 } = 1$ $a ( x ) / b ( x ) = a ( x ) * b ( x ) ^ { - 1 }$

2 伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上多项式和多项式矩阵的求逆

2.1伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 的多项式求逆

对 $\forall a ( x ) \in G F ( 2 ) [ x ] / p ( x ) , a ( x ) \neq 0$ ，因为 $p ( x )$ 为不可约多项式，显然有 $\operatorname* { g c d } ( a ( x ) , p ( x ) ) = 1$ ，根据代数性质，必然存在有限域上的唯一的多项式 $b ( \boldsymbol { x } )$ 使得$b ( x ) = a ( x ) ^ { - 1 }$ 为 $a ( x )$ 的乘法逆元。可用如下方法求多项式$a ( x )$ 的逆多项式：

a）令 $a ( x ) = a _ { k } x ^ { k } + \cdots + a _ { 2 } x ^ { 2 } + a _ { 1 } x + a _ { 0 }$ ，其中有$a _ { i } \in \{ 0 , 1 \} , k \leq 7 \circ$ （204号

b）设 $b ( \boldsymbol { x } )$ 是 $a ( x )$ 在模 $p ( x )$ 下的逆多项式，令$b ( x ) = b _ { 7 } x ^ { 7 } + \cdots + b _ { 2 } x ^ { 2 } + b _ { 1 } x + b _ { 0 }$ ，其中 $b _ { i } \in \{ 0 , 1 \}$ 。

c) 由多项式的乘法可得 $c ( x ) = a ( x ) * b ( x ) =$ $a _ { k } b _ { 7 } x ^ { k + 7 } + ( a _ { k - 1 } b _ { 7 } + a _ { k } b _ { 6 } ) x ^ { k + 6 } + \cdots + a _ { 0 } b _ { 0 }$ 也即有

$$
\begin{array} { r } { ( x ) = ( x ^ { k + 1 } , x ^ { k + 6 } , \cdots , x ^ { 7 } , \cdots , x ^ { 2 } , x ) , \left( \begin{array} { l l l l l l l l } { a _ { k } } & { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { a _ { k - 1 } } & { a _ { k } } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { a _ { k - 2 } } & { a _ { k - 1 } } & { a _ { k } } & { \cdots } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { a _ { 1 } } & { a _ { 2 } } & { a _ { 3 } } & { \cdots } & { a _ { k } } & { \cdots } & { 0 } & { 0 } \\ { a _ { 0 } } & { a _ { 1 } } & { a _ { 2 } } & { \cdots } & { a _ { k - 1 } } & { \cdots } & { 0 } & { 0 } \\ { 0 } & { a _ { 0 } } & { a _ { 1 } } & { \cdots } & { a _ { k - 2 } } & { \cdots } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { a _ { 0 } } & { a _ { 0 } } \end{array} \right) \left( b _ { k } \right) } \\ { ( x ) = ( x ^ { k + 1 } , x ^ { k + 6 } , \cdots , x ^ { 7 } , \cdots , x ^ { 2 } , x ) , \left( \begin{array} { l l l l l l l l } { a _ { k } } & { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } \\ { a _ { 0 } } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } \end{array} \right) \left( b _ { k } \right) } \end{array}
$$

其中的二维矩阵是一个 $( k + 8 ) \times 8$ 的矩阵，可以把 $c ( \boldsymbol { x } )$ 中方次大于7的项 $x ^ { m } ( m > 7 )$ 用模 $p ( x )$ 的余式替换掉，也即在伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 中用 $x ^ { m } \mod p ( x )$ 得到的结果替换掉 $x ^ { m }$ ，从而消去 $x$ 的方次大于7的项，替换后合并同类项得到降幂的多项式 $c ( x ) = c _ { 7 } x ^ { 7 } + \cdots + c _ { 2 } x ^ { 2 } + c _ { 1 } x + c _ { 0 }$ 其中 $c _ { i }$ 包含未知数 $b _ { 7 } , b _ { 6 } , \cdots b _ { 1 } , b _ { 0 }$ 。

d) 由于设 $b ( \boldsymbol { x } )$ 是 $a ( x )$ 在模 $p ( x )$ 下的逆多项式，所以 $c ( x ) = a ( x ) * b ( x ) = 1 { \bmod { p ( x ) } }$ ，也即可以得到$c ( x ) = c _ { 7 } x ^ { 7 } + \cdots + c _ { 2 } x ^ { 2 } + c _ { 1 } x + c _ { 0 } = 1 { \bmod { p } } ( x )$ ，又因为 $c ( x ) \in G F ( 2 ) [ x ] / p ( x )$ ，所以可以得到$c ( x ) = c _ { 7 } x ^ { 7 } + \cdots + c _ { 2 } x ^ { 2 } + c _ { 1 } x + c _ { 0 } = 1$ ，因此有下面的方程组成立

$$
\begin{array} { r l } & { \left[ c _ { 7 } ( b _ { 7 } , b _ { 6 } , \cdots , b _ { 2 } , b _ { 1 } , b _ { 0 } ) = 0 \right. } \\ & { \left. \begin{array} { l } { \vdots } \\ { c _ { 1 } ( b _ { 7 } , b _ { 6 } , \cdots , b _ { 2 } , b _ { 1 } , b _ { 0 } ) = 0 } \\ { c _ { 0 } ( b _ { 7 } , b _ { 6 } , \cdots , b _ { 2 } , b _ { 1 } , b _ { 0 } ) = 1 } \end{array} \right. } \end{array}
$$

用模2下的高斯消元法解此方程组，最后即可得 $b ( \boldsymbol { x } )$ 中各项的系数，得到 $a ( x )$ 的逆多项式 $b ( \boldsymbol { x } )$ 。

# 2.2伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 的方阵求逆

设有限域上的 $n$ 阶多项式方阵 $K e y ( x )$ 满足$K e y ( \boldsymbol { x } ) = \left[ \begin{array} { c c c c } { a _ { 1 1 } ( \boldsymbol { x } ) } & { a _ { 1 2 } ( \boldsymbol { x } ) } & { \cdots } & { a _ { 1 n } ( \boldsymbol { x } ) } \\ { a _ { 2 1 } ( \boldsymbol { x } ) } & { a _ { 2 2 } ( \boldsymbol { x } ) } & { \cdots } & { a _ { 2 n } ( \boldsymbol { x } ) } \\ { \vdots } & { \vdots } & { } & { \vdots } \\ { a _ { n 1 } ( \boldsymbol { x } ) } & { a _ { n 2 } ( \boldsymbol { x } ) } & { \cdots } & { a _ { n n } ( \boldsymbol { x } ) } \end{array} \right]$ 其中有$a _ { i j } ( x ) \in G F ( 2 ) [ x ] / p ( x )$ ，先根据代数学方法求 $K e y ( x )$ 在有限域 $G F ( 2 ) [ x ] / p ( x )$ 上的行列式$\operatorname * { d e t } ( K e y ( x ) ) = \mid K e y ( x ) \mid \mathrm { m o d } p ( x ) { \mathrm { , } } \ \mid K e y ( x ) { \mid }$ 为矩阵$K e y ( x )$ 的普通 $n$ 阶行列式。定义伴随矩阵

$$
K e y ( x ) ^ { * } = { \left[ \begin{array} { l l l l } { A _ { 1 1 } ( x ) } & { A _ { 2 1 } ( x ) } & { \cdots } & { A _ { n 1 } ( x ) } \\ { A _ { 1 2 } ( x ) } & { A _ { 2 2 } ( x ) } & { \cdots } & { A _ { n 2 } ( x ) } \\ { \qquad \vdots } & { \qquad \vdots } & { \qquad \vdots } \\ { A _ { 1 n } ( x ) } & { A _ { 2 n } ( x ) } & { \cdots } & { A _ { n n } ( x ) } \end{array} \right] } ,
$$

阵中的 $A _ { i j } ( x )$ 为多项式方阵 $K e y ( x )$ 中元素 $a _ { i j } ( \boldsymbol { x } )$ 在模$p ( x )$ 意义下的对应的代数余子式。如果有det $: ( K e y ( x ) ) \neq 0$ ，则可以根据上节的有限域$G F ( 2 ) [ x ] / p ( x )$ 上多项式求逆的方法可以求得多项式det $( K e y ( x ) )$ 的逆多项式 $| K e y ( x ) | ^ { - 1 }$ ，最后逆矩阵$K e y ( x ) ^ { - 1 } = ( \vert K e y ( x ) \vert ^ { - 1 } \cdot K e y ( x ) ^ { \ast } ) \bmod p ( x ) .$

2.3伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 的多项式高矩阵左伪逆求解 线性代数中的高矩阵[10]：指诸列线性无关的矩阵叫做高矩 阵。可逆方阵为高矩阵的一种特例。

伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上的多项式高矩阵：有限域$G F ( 2 ) [ x ] / p ( x )$ 上的高矩阵指列满秩的多项式矩阵，其中多项式矩阵的元素属于 $G F ( 2 ) [ x ] / p ( x )$ ， $p ( x )$ 是$G F ( 2 )$ 上的一个8次不可约多项式。

根据一般的数字高矩阵 $A$ 求左伪逆的公式$p i n \nu ( A ) = ( A ^ { \prime } { * } A ) ^ { - 1 } * A ^ { \prime }$ [](其中 $A$ 为列满秩的数字矩阵)，可得伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上高矩阵求左伪逆的方法，可以设加密的密钥高矩阵

$A ( x ) = { \left[ \begin{array} { l l l l } { a _ { 1 1 } ( x ) } & { a _ { 1 2 } ( x ) } & { \cdots } & { a _ { 1 l } ( x ) } \\ { a _ { 2 1 } ( x ) } & { a _ { 2 2 } ( x ) } & { \cdots } & { a _ { 2 l } ( x ) } \\ { \vdots } & { \vdots } & { } & { \vdots } \\ { a _ { k 1 } ( x ) } & { a _ { k 2 } ( x ) } & { \cdots } & { a _ { k l } ( x ) } \end{array} \right] }$ 是列满秩的矩阵，且高矩阵 $A ( x )$ 的行和列满足 $k \geq l$ ，则有${ ( A ( x ) ^ { * } A ( x ) ) } _ { i j } = ( \sum _ { t = 1 } ^ { k } a _ { t i } ( x ) a _ { t j } ( x ) ) { \bmod { p ( x ) } }$ ，其中$( i , j = 1 , 2 \cdots , l )$ ,然后利用上节伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上多项式方阵求逆的方法可求得 $A ^ { \prime } ( x ) * A ( x )$ 在模 $p ( x )$ 意义下的逆多项式矩阵 $\left( A ^ { \prime } ( x ) * A ( x ) \right) ^ { - 1 }$ ，最后用求得的$\left( A ^ { \prime } ( x ) * A ( x ) \right) ^ { - 1 }$ 与 $A ^ { \prime } ( x )$ 做模 $p ( x )$ 的多项式矩阵的乘法，即可求得高矩阵 $A ( x )$ 的左伪逆矩阵 $p i n \nu ( A ( x ) )$ 。

# 3 伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上的 Hil 加密衍生算法及其解密算法

文献[12\~14]提出了有限域上有关衍生的 Hill 加密以及分组加密的思想，其中包括利用有限域上圆锥曲线密码体制等结合Hill分组加密来保证数据的安全，本文对一般的HilI加密算法做了如下衍生。

# 3.1伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上的 Hil 加密衍生算法

假设由字符编码集中的字符构成明文字符串$M = M _ { 1 } M _ { 2 } \cdots M _ { m }$ ，现需要对明文进行加密发送，首先选取伽罗瓦域上合适的列满秩的加密矩阵

$$
e K e y ( x ) = \left[ { \begin{array} { c c c c } { a _ { 1 1 } ( x ) } & { a _ { 1 2 } ( x ) } & { \cdots } & { a _ { 1 l } ( x ) } \\ { a _ { 2 1 } ( x ) } & { a _ { 2 2 } ( x ) } & { \cdots } & { a _ { 2 l } ( x ) } \\ { \vdots } & { \vdots } & & { \vdots } \\ { a _ { k 1 } ( x ) } & { a _ { k 2 } ( x ) } & { \cdots } & { a _ { k l } ( x ) } \end{array} } \right]
$$

$k > l$ )和一个8次不可约多项式 $p ( x )$ ，若明文字符串的长度$m$ 不满足 $l | m$ ，则根据文献[15]处理哑元的方法，添加 $i$ 个空格字符作为哑元构成新的明文字符串${ \cal M } = { \cal M } _ { 1 } { \cal M } _ { 2 } \cdots { \cal M } _ { k } \cdots { \cal M } _ { m } \cdots { \cal M } _ { m + i }$ ，使 $l \left. \left( m + i \right) \right.$ ，其中$i < l$ ，加密时对字符串 $M$ 按 $l$ 个字符为一组进行分组，然后对每一组进行HilI加密，对加密后的字符串不做更改。

不妨设取分组中的第一组字符进行加密，取 $M$ 的前 $l$ 个字符 $M _ { 1 } M _ { 2 } \cdots M _ { l }$ ，对其中的每个字符 $M _ { j } ( 1 \leq j \leq l )$ 在字符编码表1中查询其对应位置的索引值 $I n d e x _ { j }$ ，并将对应位置的索引值Indexj转换成对应的二进制形式的表达式，也即有廳 $I n d e x _ { j } = m _ { j _ { 7 } } * 2 ^ { 7 } + m _ { j _ { 6 } } * 2 ^ { 6 } + \dots + m _ { j _ { 1 } } * 2 + m _ { j _ { 0 } } \ ,$ （204把式中的2替换为 $x$ 可以得到多项式$f _ { j } ( x ) \in G F ( 2 ) [ x ] / p ( x )$ ，最后可以得到一个明文字符串$M _ { 1 } M _ { 2 } \cdots M _ { l }$ 所对应的一个多项式向量$f ( x ) = \left[ f _ { 1 } ( x ) \quad f _ { 2 } ( x ) \quad \cdots \quad f _ { l } ( x ) \right] ^ { T }$ ，在伽罗瓦域上左乘加密矩阵 $e K e y ( x )$ ，并选取密钥矩阵的第 $l$ 列(也可以随机选取密钥矩阵的其他列)作为平移增量，利用加密矩阵进行 Hill加密后的密文向量 $e ( x )$ ，其中$e ( x ) = \left[ e _ { 1 } ( x ) e _ { 2 } ( x ) \cdots e _ { k } ( x ) \right] ^ { T }$ ，向量分量满足有$e _ { j } ( x ) = ( ( \sum _ { i = 1 } ^ { l } a _ { j i } ( x ) * f _ { i } ( x ) ) + a _ { j l } ( x ) ) \bmod p ( x )$ $j = 1 , 2 \cdots , k$ 。上式用矩阵的形式来表示即为$e ( x ) = ( e K e y ( x ) ^ { * } f ( x ) + a _ { \cdot _ { l } } ( x ) ) { \bmod { p ( x ) } }$ ，其中$a _ { \cdot _ { l } } ( x )$ 表示抽取矩阵 $e K e y ( x )$ 中的第 $l$ 列。将密文多项式向量中每个多项式中的变量 $x$ 用2 替换，并求多项式的值，也即得到加密后密文字符在字符编码表中所对应的索引值，通过查表转换即可得到密文字符串 $C _ { 1 } C _ { 2 } { \cdot } { \cdot } { \cdot } C _ { l } { \cdot } { \cdot } { \cdot } C _ { k }$ 。

# 3.2伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上的 Hil加密衍生算法的解密

先根据上节的方法求加密矩阵 $e K e y ( x )$ 在有限域  
$G F ( 2 ) [ x ] / p ( x )$ 的左伪逆矩阵，并记左伪逆矩阵为  
$d K e y ( x )$ ，使得求解得到的 $d K e y ( x )$ 作为解密矩阵。  
$d K e y ( \boldsymbol { x } ) = \left[ \begin{array} { c c c c } { b _ { 1 1 } ( \boldsymbol { x } ) } & { b _ { 1 2 } ( \boldsymbol { x } ) } & { \cdots } & { b _ { 1 k } ( \boldsymbol { x } ) } \\ { b _ { 2 1 } ( \boldsymbol { x } ) } & { b _ { 2 2 } ( \boldsymbol { x } ) } & { \cdots } & { b _ { 2 k } ( \boldsymbol { x } ) } \\ { \vdots } & { \vdots } & { } & { \vdots } \\ { b _ { l 1 } ( \boldsymbol { x } ) } & { b _ { l 2 } ( \boldsymbol { x } ) } & { \cdots } & { b _ { l k } ( \boldsymbol { x } ) } \end{array} \right] .$ 其中，由  
于加密时已经对相应的哑元进行了替换处理，所以加密后的密  
文字符串的长度必然为 $k ( m + i ) / l$ ，且有 $l \left. \left( m + i \right) \right.$ ，因此  
可以直接对密文字符串 $C = C _ { 1 } C _ { 2 } { \cdots } C _ { k } { \cdots } C _ { m } { \cdots } C _ { k ( m + i ) / l }$ （204  
以 $k$ 个字符为一组进行分组，再对每一组进行解密运算。现在对分组中的其中一组密文字符讨论解密算法，不妨取

$C$ 的第1组的 $k$ 个字符 $C _ { 1 } C _ { 2 } \cdots C _ { k }$ ，对其中的每个字符

$C _ { j } ( 1 \leq j \leq k )$ 在字符编码表中查询其对应位置的索引值$I n d e x _ { j }$ ，并将对应的索引值 $I n d e x _ { j }$ 转换成对应的二进制形式的表达式，也即有（204号 $I n d e x _ { { } _ { j } } = c _ { { } _ { j _ { 7 } } } * 2 ^ { 7 } + c _ { { } _ { j _ { 6 } } } * 2 ^ { 6 } + \cdots + c _ { { } _ { j _ { 1 } } } * 2 + c _ { { } _ { j _ { 0 } } }$ ，同时把表达式中的2替换为 $x$ 可以得到多项式（20 $g _ { j } ( x ) \in G F ( 2 ) [ x ] / p ( x )$ ，最后可以得到一个密文字符串$C _ { 1 } C _ { 2 } \cdots C _ { k }$ 所对应的一个多项式向量$g ( x ) = \left[ g _ { 1 } ( x ) \quad g _ { 2 } ( x ) \quad \cdots \quad g _ { k } ( x ) \right] ^ { T }$ ，在有限域上先减去平移增量(即密钥矩阵的第 $l$ 列)，再用得到的结果右乘解密矩阵 $d K e y ( x )$ ，然后可以得明文向量 $d ( x )$ ，其中明文向量$\begin{array} { r } { d ( x ) = \big [ d _ { 1 } ( x ) \quad d _ { 2 } ( x ) \quad \cdots \quad d _ { l } ( x ) \big ] ^ { T } } \end{array}$   
$d _ { j } ( x ) = ( \sum _ { i = 1 } ^ { k } b _ { j i } ( x ) * ( g _ { i } ( x ) - a _ { i l } ( x ) ) ) { \bmod { p } } ( x )$   
$j = 1 , 2 \cdots , l$ 。以上的式子用矩阵形式来表示即为$d ( x ) = ( d K e y ( x ) ^ { \ast } ( g ( x ) - a _ { \cdot _ { l } } ( x ) ) ) { \bmod { p ( x ) } }$ ，其中$a _ { \cdot _ { l } } ( x )$ 表示抽取矩阵 $e K e y ( x )$ 中的第 $l$ 列。将明文多项式向量中每个多项式中的变量 $x$ 用2 替换，并求多项式的值，即得到解密后明文字符在字符编码表中所对应的索引值，通过查表转换即可得到明文字符串 $M _ { 1 } M _ { 2 } \cdots M _ { l }$ 。

# 4 多项式环 $G F ( 2 ) [ x ]$ 中8次不可约多项式

$G F ( 2 ) [ x ]$ 上的8次不可约多项式是指系数只能为0、1的8次不可约的一元多项式，即8次不可约多项式$p ( x ) = x ^ { 8 } + a _ { 7 } x ^ { 7 } + \cdots + a _ { 1 } x + a _ { 0 }$ （204 （其中$a _ { 7 } , \cdots , a _ { 1 } , a _ { 0 } \in \{ 0 , 1 \} \backslash$ ，满足不能分解成 $G F ( 2 ) [ x ]$ 上7次及7次以下的多项式的乘积。为了求解 $G F ( 2 ) [ x ]$ 上的8次不可约多项式的集合 $A$ ，可以先通过遍历相乘的方法求出多项式环 $G F ( 2 ) [ x ]$ 上的8次可约多项式的集合 $B$ ：通过分析，$G F ( 2 ) [ x ]$ 上的8次可约多项式的集合可以表示为$B = B _ { 1 } \cup B _ { 2 } \cup B _ { 3 } \cup B _ { 4 }$ ，其中 $B _ { 1 }$ 为任意1次和任意7次多项式乘积的集合， $B _ { 2 }$ 为任意2次和任意6次多项式乘积的集合， $B _ { 3 }$ 为任意3次和任意5次多项式乘积的集合， $B _ { 4 }$ 为任意两个4 次多项式乘积的集合。然后利用 $G F ( 2 ) [ x ]$ 上的8次多项式的全集 $S$ 对 $B$ 作差集运算，即可得相应的8次不可约多项式的集合 $A = S - B$ 。其多项式环上8次不可约多项式集合求解的Python 程序如下所示：

# 5 伽罗瓦域 $G F ( 2 ) [ x ] / p ( x )$ 上的 Hil 加密衍生算法和解密的实例验证

假设需要加密传送的字符串为： $s t r i n g =$ hello, It's nice tomeet you。首先选取 $G F ( 2 ) [ x ]$ 上的一个8次不可约多项式为$p ( x ) = x ^ { 8 } + x ^ { 4 } + x ^ { 3 } + x + 1$ ，并选择伽罗瓦域  
上 import numpy  
2 import math  
3 $\mathrm { ~ C ~ } = \mathrm { ~ [ ] ~ }$ （20 $G F ( 2 ) [ x ] / p ( x )$ 上的一个 $3 \times 2$ 的列满秩的多项式高矩阵  
4 for i in range(1，5):#[1 2 3 4]  
56 $\begin{array} { r l } { \dot { \mathrm { ~  ~ j ~ } } = } & { { } - \dot { \mathrm { ~  ~ \cdot ~ } } } \end{array}$ $\mathrm { ~ \AA ~ } = \mathrm { ~ [ ] ~ }$ ${ } _ { ? ^ { \land } } e K e y ( x ) = { \left[ \begin{array} { l l } { x ^ { 5 } } & { \ x ^ { 2 } } \\ { x ^ { 3 } } & { x ^ { 2 } + 1 } \\ { x ^ { 3 } } & { x + 1 } \end{array} \right] } ,$   
7 8 for rowin range(1,int(math.pow(2，i)+1):# 从1取到2^ieKey(x)=x3 作为加密时的密钥矩阵，选取密  
9 tempList $\mathbf { \Sigma } = \mathbf { \Sigma } [ \mathbf { \Sigma } ]$   
10 for x in list((bin(row))[2:].zfill(i+1)):  
11 tempList.append(int(x))  
12 tempList ${ \sf { I } } ^ { } 0  ] \ : = \ : 1$ （204号  
13 A.append(tempList) 钥矩阵 $e K e y ( x )$ 的第2列 $a . _ { 2 } ( x ) = \left[ x ^ { 2 } x ^ { 2 } + 1 x + 1 \right] ^ { T }$   
14 for row in range(1，int (math.pow(2，j)) $+ 1$ ）:# 从1取到2^  
15 tempList $\mathit { \Theta } = \mathit { \Theta } [ ]$ （204号  
16 for x in list((bin(row))[2:].zfill $( \dot { ] } + 1 )$ )： 作为加密时候的平移增量，然后可以利用求解高矩阵左伪逆的  
17 tempList.append(int(x))  
18 tempList ${ \sf { I } } ^ { } 0  ] \ : = \ : 1$ 方法求得解密矩阵 $d K e y ( x )$ ：可以先求得对应的行列式19 B.append(tempList)20 for il in range(int(math.pow(2，i))): $\operatorname* { d e t } ( e K e y ( x ) ^ { \prime } { \ast } e K e y ( x ) ) = x ^ { 6 } + x ^ { 2 } + x$ ，再用多项式求21 for j1 in range(int(math.pow(2，j))):22 $\mathrm { \ p } 1 ~ =$ numpy.polyld(A[i1])23 $\mathtt { p } 2 \ =$ numpy.polyld(B[j1]) 逆的方法得多项式行列式在模 $p ( x )$ 下的乘法逆元为2425 tempCoeffs $\mathbf { \tau } = \mathbf { \tau }$ (p1 \* p2).coeffsfor $\mathrm { ~  ~ x ~ } _ { \ }$ in range(len(tempCoeffs)): $x ^ { 7 } + x ^ { 6 } + x ^ { 5 } + x ^ { 4 } + x ^ { 2 } + 1$ ，最后根据多项式高矩阵求左2627 C.append(tefs[x] $\mathbf { \tau } = \mathbf { \tau }$ tempCoeffs[x] & 2 伪逆的计算公式可以得 $d K e y ( x ) =$ 2829 for x in range(len(C)): $p i n \nu ( e K e y ( x ) ) = ( e K e y ( x ) ^ { * } e K e y ( x ) ) ^ { - 1 } * e K e y ( x ) ^ { \prime }$ 30 C[x] $\mathbf { \tau } = \mathbf { \tau }$ list(C[x])31 日for num in range(256): #0-25532 tempList $\mathbf { \Sigma } = \mathbf { \Sigma } [ \mathbf { \Sigma } ]$ （2 求得密钥矩阵所对应的解密矩阵为33 for x in list((bin(num))[2:].zfill(8)):34 tempList.append(int (x)) $d K e y ( x ) = { \left[ \begin{array} { c c c } { x ^ { 6 } + 1 } & { x ^ { 7 } + x ^ { 3 } } & { x ^ { 6 } + x ^ { 5 } + x ^ { 4 } + x ^ { 3 } + x ^ { 2 } + x + 1 } \\ { x ^ { 7 } + x ^ { 6 } + x ^ { 4 } + x ^ { 3 } } & { x ^ { 6 } } & { x ^ { 3 } + x ^ { 2 } + 1 } \end{array} \right] }$ 3536 if tempListemptiin) C:

通过以上Python 程序的运行结果，即可求得多项式环$G F ( 2 ) [ x ]$ 上的所有 8次不可约多项式，其降幂排列时对应的系数向量如表2所示。对以上的Python程序稍作修改还可以用来求解多项式环 $G F ( 2 ) [ x ]$ 上的 $N$ 次不可约多项式。

<html><body><table><tr><td colspan="2">表2多项式环GF(2)[x]上所有8次不可约多项式的系数向量</td></tr><tr><td>[1,0,0,0,1,1,0,1, 1],</td><td>[1,0,0,0,1,1, 1,0, 1], [1,0, 0,1,0, 1,0, 1, 1]</td></tr><tr><td>[1,0,0,1,0,1,1,0, 1], [1,0, 0,1,1, 1,0, 0, 1],</td><td>[1, 0, 0, 1, 1, 1, 1, 1, 1]</td></tr><tr><td>[1,0,1,0,0,1,1,0,1],</td><td>[1,0,1,0,1,1,1,1,1], [1,0, 1, 1,0, 0,0, 1, 1]</td></tr><tr><td>[1,0,1,1,0,0,1,0, 1],</td><td>[1,0,1,1,0,1,0,0,1], [1,0,1, 1, 1,0,0,0, 1]</td></tr><tr><td>[1,0, 1, 1, 1,0, 1,1, 1],</td><td>[1,0,1,1,1, 1,0,1, 1], [1,1,0,0,0,0,1, 1,1]</td></tr><tr><td>[1,1,0,0,0,1,0,1,1],</td><td>[1,1,0,0,0,1,1,0,1], [1, 1, 0, 0, 1, 1, 1, 1, 1]</td></tr><tr><td>[1,1,0,1,0,0,0,1, 1],</td><td>[1,1,0,1,0,1,0,0,1], [1,1, 0,1, 1, 0,0,0, 1]</td></tr><tr><td>[1,1,0,1,1,1, 1,0,1],</td><td>[1,1, 1,0,0,0,0,1,1], [1, 1, 1, 0, 0, 1, 1, 1, 1]</td></tr><tr><td>[1,1,1,0, 1,0, 1, 1, 1],</td><td>[1,1, 1,0, 1, 1, 1,0, 1], [1, 1, 1, 1, 0, 0, 1, 1, 1]</td></tr><tr><td>[1,1, 1, 1, 1,0,0,1,1],</td><td>[1,1,1,1,1,0,1,0,1], [1,1, 1, 1, 1, 1, 0, 0, 1]</td></tr></table></body></html>

# 5.1加密阶段

第一步先对以上要加密的字符串中的字符按照表1的对应关系转换成相应的数字索引，得到明文字符串索引表如表3所示。

表3明文字符串索引表  

<html><body><table><tr><td>h</td><td>e</td><td>1</td><td>1</td><td>0</td><td>，</td><td>space</td><td></td><td>I</td><td>t</td><td>，</td><td>S</td><td>space</td><td>n</td><td>i</td></tr><tr><td>8</td><td>5</td><td>12</td><td>12</td><td>15</td><td>83</td><td></td><td>0</td><td>35</td><td>20</td><td>90</td><td>19</td><td>0</td><td>14</td><td>9</td></tr><tr><td>C</td><td>e</td><td>space</td><td>t</td><td>0</td><td>space</td><td>m</td><td>e</td><td></td><td>e</td><td>t</td><td>space</td><td>y</td><td>0</td><td>u</td></tr><tr><td>3</td><td>5</td><td>0</td><td>20</td><td>15</td><td>0</td><td>13</td><td></td><td>5</td><td>5</td><td>20</td><td>0</td><td>25</td><td>15</td><td>21</td></tr></table></body></html>

第二步由于加密矩阵是 $3 { \times } 2$ 的高矩阵，所以对明文字符串按照每 2个字符进行分组，取明文字符串的前两个字符 he并将其索引转换成 $G F ( 2 ) [ x ] / p ( x )$ 上的多项式为$[ x ^ { 3 } , x ^ { 2 } + 1 ] ^ { T }$ ,先左乘加密矩阵，然后加上选取的平移增量$a _ { \cdot _ { 2 } } ( x )$ 并在模 $p ( x )$ 意义计算可以得到$\left( { \begin{array} { c c } { x ^ { 5 } } & { x ^ { 2 } } \\ { x ^ { 3 } } & { x ^ { 2 } + 1 } \\ { x ^ { 3 } } & { x + 1 } \end{array} } \right) { \left[ \begin{array} { c } { x ^ { 3 } } \\ { x ^ { 2 } + 1 } \end{array} \right] } + { \left[ \begin{array} { c } { x ^ { 2 } } \\ { x ^ { 2 } + 1 } \\ { x + 1 } \end{array} \right] } { \bmod { p ( x ) } } =$ ${ [ \begin{array} { l } {  x ^ { 3 } + x + 1 } \\ { x ^ { 6 } + x ^ { 4 } + x ^ { 2 } } \\ { x ^ { 6 } + x ^ { 3 } + x ^ { 2 } } \end{array} ] } ,$ 其结果向量多项式的二进制系数构成二进制数，将对应的二进制数转换成十进制数分别为11、84、76，也即得到了密文字符的索引值，查询字符编码表，可知对应索引的密文字符为 ${ \mathrm { k . ~ } } ^ { + }$ ，同理，对其他分组按照相同的方法加密，最后得到加密后的密文字符以及索引如表4所示。

表4密文字符串索引表  

<html><body><table><tr><td>k</td><td>：</td><td>+</td><td>N</td><td>：</td><td>B</td><td>B</td><td>△</td><td>℃</td><td>T</td><td>Ⅱ</td><td>1</td><td>b</td><td>y</td></tr><tr><td>11</td><td>84</td><td>76</td><td>175</td><td>89</td><td>119</td><td>168</td><td>121</td><td>142</td><td>136</td><td>170</td><td>102</td><td>193</td><td>140</td></tr><tr><td>，</td><td>；</td><td>ii</td><td>XII</td><td>土</td><td>：</td><td>入</td><td>T</td><td>L</td><td>T</td><td>：</td><td>#</td><td>！</td><td>s</td></tr><tr><td>77</td><td>82</td><td>157</td><td>155</td><td>251</td><td>88</td><td>104</td><td>112</td><td>12</td><td>20</td><td>84</td><td>65</td><td>63</td><td>255</td></tr><tr><td></td><td>Z</td><td>E</td><td>H</td><td>n</td><td>M</td><td>μ</td><td>W</td><td>Y</td><td></td><td>N</td><td>E</td><td>7</td><td><</td></tr></table></body></html>

其结果向量多项式的二进制系数构成二进制数，将对应的二进制数转换成十进制数分别为8、5，得到了相应明文字符的索引值，查询字符编码表，可知对应的明文字符为he，同理，对其他分组按照相同的方法解密，最后即可得到解密的明文字符串string $\ c =$ hello, It's nice to meet you 。

# 6 安全性分析

算法安全性取决于密钥的安全性及攻击复杂性，本文所使用的密钥的安全性表现在以下几个方面。

# 6.1一次一密通信

本文所使用的密钥矩阵是伽罗瓦域上随机选取的一个多项式高矩阵，本质上它是无法预测的，所以密钥产生的加密函数是安全的，对应的解密函数也是安全的。每次通信时都重新选择密钥矩阵，因而实现了一次一密通信[16]，信息论的创始人Shannon已经证明一次一密是绝对安全的，也即之前破解的密钥对之后密文的破解没有任何帮助，一次一密系统在理论上是不可攻破的密码系统[16]。

# 6.2 雪崩效应

由于Hi11加密是将明文消息分组混合进行加密，所以明文或者密钥的微小改变都将对密文产生很大的影响，特别是当密钥矩阵的规模更大的时候，明文的某一位发生变化将会导致这一组中的所有密文都发生变化，密钥矩阵的某一位发生变化将会导致每个分组固定位置的密文发生变化，此时这种雪崩效果更加明显，这使得攻击者要直接通过对密文的规律性分析来获得密钥矩阵不可行。

# 6.3 密钥空间大

$G F ( 2 ) [ x ] / p ( x )$ 上的 Hil 加密衍生算法的解密首先要知道正确的 $p ( x )$ ，在不知道 $p ( x )$ 的情况下，由于不能确定具体是在哪一个有限域上进行的加密运算，所以解密的难度更大。

本文还通过采用高矩阵作为密钥矩阵的方法增加了密钥空

<html><body><table><tr><td>125 123 171 24 100 244 10523 96 120 40 171 60 68</td></tr></table></body></html>

从上面的两表可以看出，通过高矩阵作为密钥加密明文后得到的密文字符的数量是原明文字符数量的1.5倍，也即利用高矩阵加密的特点是加密后密文的长度可以不和明文的长度一致。

# 5.2解密阶段

第一步解密阶段应先求出高矩阵的伪逆矩阵。前面已经求出高矩阵 $e K e y ( x )$ 的左伪逆矩阵 $d K e y ( x )$ 。第二步 对密文字符串按照3个字符为一组进行分组，不妨先取密文字符串的前3个字符 $\mathbf { k . } +$ 并将其对应的索引值转换成有限域上的多项式向量为 $[ x ^ { 3 } + x + 1 , x ^ { 6 } + x ^ { 4 } + x ^ { 2 } , x ^ { 6 } + x ^ { 3 } + x ^ { 2 } ] ^ { T }$ ,然后对得到的多项式向量先减去平移增量 $a _ { \cdot _ { 2 } } ( x )$ ，再左乘相应高矩阵的左伪逆多项式解密矩阵并在模 $p ( x )$ 意义下进行计算，可以得到

间的大小，对于一般的多项式方阵作为密钥矩阵而言，如果攻击者通过对密文长度的分析获得了密钥矩阵的阶数，则他很容易能够通过遍历这个阶的所有的多项式方阵，从而来暴力破解加密时的密钥矩阵，然而高矩阵由于行和列的数目不相同，加密后的密文长度和明文长度并不一致，因此能很好的抵御这种唯密文暴力攻击。在实际应用中可以采用更高阶的密钥矩阵，当密钥矩阵的阶越高的时候，其对应的 $k \times l$ 的多项式矩阵多达 $2 5 6 ^ { k \times l }$ 种，而且当选取的不可约多项式 $p ( x )$ 不同时，其对应的有限域也不同，从而使得暴力破解密钥矩阵更难，因此其上的Hil1加密有更高的安全性，适合大量数据的分组加密。

# 6.4平移增量

有限域 $G F ( 2 ) [ x ] / p ( x )$ 上的Hill 加密衍生算法$y = A x + b$ 在加密时新增添了一个平移增量 $\pmb { b }$ ，其中平移增量 $\pmb { b }$ 是从加密的密钥矩阵 $A$ 中随机选取的一列，解密的时候密文并不能直接乘以密钥矩阵 $A$ 的伪左逆矩阵 $\boldsymbol { A } ^ { - 1 }$ 来得到明文，必须得先减去加密时候的平移增量之后做相同的操作才能解密得到明文，因为敌手不知道是否有平移增量的存在，从而加大了攻击的复杂性。

# 7 安全性模型

根据上节密钥的安全性及攻击复杂性分析，可以得到算法的抗攻击强度。

# 7.1唯密文攻击

唯密文攻击指攻击者在仅知道已知加密文字下的穷举攻击。此时，攻击者掌握的信息最少，在本文高矩阵为密钥的Hill加密衍生算法中，攻击者仅根据密文并不知道对应的明文长度，不知道有限域的不可约多项式 $p ( x )$ ，因此不能得出加密的密钥高矩阵的规模，更不知道密钥会不会是特殊的高矩阵-可逆方阵，同时也不能确定从高矩阵中随机选取的一列的平移增量。

因此算法是唯密文攻击安全的。

# 7.2 已知明文攻击

已知明文攻击给出了特定的明文和对应的密文，在本文的加密算法下，可以根据密文和对应明文的长度比来确定高矩阵的行数 $k$ 和列 $\mathbf { \Phi } _ { l }$ 数的比例 $k : l$ ，尽管如此，实际高矩阵的规模则是 $t k \times t l$ ，因此，此时仍然不能确定高矩阵的具体规模，而且也无法确定有限域 $G F ( 2 ) [ x ] / p ( x )$ 所选择的不可约多项式p(x)。因此算法是已知明文攻击安全的。

# 7.3选择明 $( \sharp ^ { \sharp } )$ 文攻击

相对于唯密文攻击和已知明文攻击而言，选择明(密)文攻击是一种较强的攻击，它给与攻击者较大的权限，使得攻击者能够访问加(解)密预言机，从而得到攻击者自己构造的明(密)文加(解)密的结果，文献[17-19]提出了不同的关于CCA安全的公钥密码体制，选择明文攻击指攻击者获得了加密服务，选择密文攻击指攻击者获得了解密服务，在对称密码当中，这两种攻击都使得攻击者能够获得足够多的明(密)文和对应的密(明)文。此时攻击者可以通过大量的明文和密文对的信息来分析密钥矩阵的规模并进行验证。如果每次加密的密钥始终保持不变，则此时的密钥在这种攻击下是不安全的。因此，本文在上节的安全性分析当中提到可以使用一次一密来进行通信，且每次通信中每个分组使用的平移增量从密钥高矩阵的列向量中轮换选取，也即每一次通信选择的加密密钥只使用一次，使得加/解密能够保持前后向的安全性，也即保证当前密钥的泄露不会对以前的加密过程和未来的加密过程造成危害。

# 8 结束语

Hill加密算法的思想对密码学的学习有很重要的意义，本文提出了一种新的有限域 $G F ( 2 ^ { 8 } )$ 上的 Hill加密衍生算法，是对经典密码学中传统的HiI1加密算法的新的衍生，使得加密时的密钥高矩阵即使在保持固定不变的情况下，也至少能够抵抗对密钥高矩阵的已知明文攻击，因此其上的Hill加密相对于传统的Hill加密具有更高的安全性，对Hil1密码体系的进一步深入学习有一定的借鉴意义。

# 参考文献：

[1]冯克勤．有限域[M].长沙：湖南教育出版社,1991:24-57.(Feng Keqin.Finite fields [M]. Changsha: Hunan Education Press,1991: 24-57.)  
[2]胡冠章．应用近世代数[M].北京：清华大学出版社，1993:171-193.(HuGuangzhang，Appliedrecent algebra [M].Beijing:TsinghuaUniversity Press,1993:171-193.)  
[3]万福永，戴浩晖.Hill_2密码体系加密过程中的哑元问题[J].数学的实践与认识，2007(8):87-90.(Wan Fuyong,Dai Haohui. The design ofdummy variable in hill2 coding system [J].Mathematics in Practice andTheory,2007(8):87-90.)  
[4]杨淑菊.Hill 密码的加密解密矩阵的求法 [J].价值工程，2016(26):285-287.(Yang Shuju.Method for encryption and decryption matrix of hill

cipher [J].Value Engineering,2016 (26):285-287.)

[5]徐小华，黎民英.Hill密码加密解密时矩阵的求法[J]．电脑与信息技术, 2010(2):31-33.(Xu Xiaohua,Li Minying.The solution of matrix of hill cipher in encryption and decryption [J].Computer and Information Technology,2010 (2): 31-33.)

[6] 王容，廖群英，王云莹，曾茂俊，宁宇光，洪思奥.Hill加密算法的改进 [J]．四川师范大学学报：自然科学版,2015(1):8-14.(Wang Rong,Liao Qunying,Wang Yunying,et al. Improvement of hill encryption algorithm [J].Journal of Sichuan Normal University:Natural Science,2015(1)   
8-14.) [7]付卫平，陈继业．有限域GF(2\~n）的一种除法运算算法[J].邵阳学院 学报：自然科学版,2015(2):3-10.(Fu Weiping,Chen Jiye.An algorithm to implement division operation of finite field GF(2\~n）[J]. Journal of Shaoyang University: Natural Science Edition,20l15 (2): 3-10.) [8]蒲保兴，王伟平，．线性网络编码运算代价的估算与分析[J].通信学报,   
2011 (5):47-55.(Pu Baoxing,Wang Weiping. Evaluation and analysis of the computation cost of linear network coding [J]. Journal on Communications,201 (5): 47-55.) [9] 焦占亚，曾永莹，刘海峰．一次一密的密码算法研究[J]．西安科技大 学学报,2005 (4): 477-480. (Jiao Zhanya,Zeng Yongying,Liu Haifeng. Design and realizing of a system of block cipher[J].Journal of Xi’an Universityof Science and Technology,2005 (4): 477-480.) [10]谢邦杰．线性代数（第一版）[M].北京：高等教育出版社，1978.(Xie Bangjie.Linear algebra (first edition)[M].Beijing: Higher Education Press,   
1978.) [11]王松桂．广义逆矩阵及其应用[M].北京：北京工业大学出版社，2006. (Wang Songgui.Generalized inverses and applications[M]. Beijing: Beijing University of Technology Press,2006.） [12]张玉安，冯登国．一种实用的仿一次一密分组加密方案[J].北京邮电 大学学报,2005 (2):101-104.(Zhang Yu’an,Feng Dengguo.A practical one-time-pad-like block cipher scheme [J]. Journal of Beijing University of Posts and Telecommunications,2005 (2):101-104.) [13]刘海峰，吴鹏，马令坤．基于有限域上圆锥曲线的分组加密算法及实现 [J]．吉林大学学报：理学版,2012,50(1): 54-58.(Liu Haifeng,Wu Peng, Ma Lingkun.Implementation of group encryption algorithm based on conic curve over finite fields[J]. Journal of Jilin University: Science Edition,2012,50 (1): 54-58.) [14]卢开澄．计算机密码学——计算机网络中的数据保密与安全 (第3版) [M]．北京：清华大学出版社，2003．(Lu Kaicheng.Computer cryptology-data privacy and security in computer networks (third edition)， [M]. Beijing: Tsinghua University Press,2003.) [15]刘海峰，何立勇，郭改慧，等.Hill 密码体系中的加密矩阵与哑元[J]. 西南大学学报：自然科学版，2014(11):138-142.(LiuHaifeng，He

Liyong,Guo Gaihui,et al. The dummy and encryption matrix in the Hill coding system [J]. Journal of Southwest University:Natural Science Edition,2014,36 (11): 138-142.

[16]卿斯汉．密码学与计算机网络安全[M].北京：清华大学出版社，2001. (Qin sihan. Cryptography and computer network security. [M]. Beijing: Tsinghua University Press,2001.)

[17]李素娟，张明武，张福泰.抗(持续）辅助输入CCA安全的PKE 构造 方案的分析及改进[J].计算机学报，2017:1-13.(Li Sujuan,Zhang Mingwu,Zhang Futai. Security analysis and improvement of CCA secure PKE with(continual) auxiliary input [J].Chinese Journal of Computers, 2017: 1-13.)

[18]王欣，薛锐．对于一个新的CCA安全的密码方案的分析[J]．密码学报,

2017(2):106-113.(Wang Xin,Xue Rui.Analysis ofa new CCA-secure public-key cryptosystem [J]. Journal of Cryptologic Research,2O17 (2): 106-113.)

[19]王占君，马海英，王金华．基于适应性选择密文不可区分性的抗辅助输 入泄漏公钥加密方案[J].计算机应用，2014(5):1288-1291.(Wang Zhanjun,Ma Haiying,Wang Jinhua. Public key encryption scheme with auxiliary inputs based on indistinguishability under adaptive chosen ciphertext attack [J]. Journal of Computer Applications,2O14 (5): 1288-1291. )