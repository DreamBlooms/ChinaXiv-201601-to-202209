# RS译码优化及卫星通信CCSDS下RS译码仿真\*

王兵锐1²，杨晓非²，姚行中+

(1．南阳师范学院 软件学院，河南 南阳 473007；2.华中科技大学 光学与电子信息学院，武汉 430074;3．火箭军研究院，北京 1000853)

摘要：针对里德所罗门(RS)译码的关键步骤错误值求解不灵活的问题提出一种更加通用的求解算法。该算法融入多种本原元运算，使得对不同参数都普遍适用；针对该算法在求解错误值多项式时计算量过大，根据伽罗华域的特征提出了一种优化方法，从而省去一半运算以及节省存储资源。针对RS 译码另一个步骤求解错误位置多项式时迭代复杂度过高的问题，经过对补偿差值的详细分析，给出了一种快速搜索迭代次数的算法，且迭代复杂度由 $O ( n ^ { 2 } )$ 下降了一个数量级到 $O ( n )$ 。以卫星通信中的国际空间数据系统咨询委员会(CCSDS)标准下RS(255，223)为具体研究对象，结合优化后的译码算法进行了数据仿真分析和误比特率测试。实验结果表明，采用改进的求错误值算法和优化的迭代次数搜索算法，可以有效快速解码。

关键词：里德所罗门码；伽罗华域；错误值多项式 中图分类号：TN911.2 doi:10.19734/j.issn.1001-3695.2018.11.0839

# Improved RS decoding algorithm and RS decoding simulation under CCSDS standard in satellite communications

Wang Bingrui1, 2, Yang Xiaofei², Yao Xingzhong3+ (1.SchoolofSoftware,Nanyang Normal UniversityNanyang Henan4730o7,China;2.Schoolof Optics&Electronics, Huazhong UniversityofScience&Technology,Wuhan430074,China;3.RocketArmyAcademyBeijing100085,China)

Abstract:Focusing on the inflexibilityoferror value solving in the keysteps ofRS decoding,this paper proposeda general algorithm.The algorithm dealt witha varietyof primitiveelements,making ituniversallyapplicable to diferentparameters. Then,with regard to large computational complexityof errorvalue polynomial involved in the algorithm,this paper describedanoptimization methodto eliminate halfof theoperationand save storage resources,according to characteristics ofthe Galois field.There isaproblemthattheiterativecomplexity is high whensolving theerrorlocationpolynomialof RS decoding.Basedonthedetailed analysisofcompensation diference,analgorithm forfastsearch iterations was presented, and the complexity of search iteration was reduced from $O ( n ^ { 2 } )$ to $O ( n )$ .Taking RS(255,223) code under the satellite communication CCSDS standard as the specific object,combined with the proposed RS decoding algorithm,the paper caried out specific data simulation and BER test. Simulation experiments show that the improved eror value solving algorithm and optimized fast search algorithm are effective.

Key words:reed solomon (rs) code; galois field; error value polynomial

# 0 引言

里德所罗门 (Reed Solomon,RS)码能纠正随机错误和突发错误，而且纠正后者能力更强。RS码被广泛应用于数据存储和通信中。随着物联网技术的发展，越来越多的设备被连接并产生大量数据。通过将计算密集型任务转移到边缘设备，基于云的存储技术已成为主流。Wang等人[1提出了一种基于雾计算的数据同步新架构。并采用RS码来保证安全。Demirkan 和 Silvus[2]结合软输出维特比算法，提出了一种多重交织RS码架构，应用在垂直磁记录上。Li等人[]针对伴有加性高斯白噪声的突发瑞利衰落信道，提出了两种RS 解码方法。在仅包含加性高斯白噪声的区域中，只需进行纠错处理。在突发衰落区域中进行纠错纠删处理。利用分子作为信息载体的纳米级通信中，分子通信是一种新的范例。在基于扩散的分子通信中，系统性能容易受连续分子交叉引起的符号间干扰的影响。为了解决这个问题，Dissanayake 等人[4]采用RS码来提高传输的可靠性。在基于单模光纤的直接检测光学系统，Chen等人[5]从实验上阐述了RS码结合多符号交织实时正交频分复用信号传输。这是首次在实时光正交频分复用系统中采用RS码。Lubytransform和Raptor这些纠删码可以对计算机网络进行弹性纠删分布。Borujeny和Ardakani提出了一类基于RS码的纠删码，能保证接收零开销。

RS 码的应用非常广泛。针对RS译码算法中两个关键步骤一求解错误位置多项式和求解错误值，本文进行了研究分析和优化。在求解错误位置多项式时，需要进行搜索迭代运算，其复杂度为 $\textstyle { \pmb { O } } ( n ^ { 2 } )$ 。当校验位和码长数值不断增大时，复杂度较高。本文提出一种改进方法，降低搜索复杂度是十分有意义的。在具体设计RS码时，会引入很多参数，使得参与计算的系数偏小且具有对称性。小系数更方便计算，系数对称可以节约存储。例如32个数据中前16个数据和后16个数据是对称的，那么只需存储一半数据。RS码参数设计灵活，需要一个通用的求解错误值算法，但文献[7]介绍的求解错误值算法涉及的参数比较单一。本文给出一种更加通用的求解错误值算法具有一定的意义。在用于卫星通信的国际空间数据系统咨询委员会(Consultative Committee for SpaceDataSystems,CCSDS)标准下，依据改进的算法对RS(255,223)进行了具体数值分析和误比特率仿真测试。

# 1 求解伴随式

对不超过RS码纠错能力的一组错误信息，RS译码算法都可以检测其中的错误，确定错误位置多项式，找到错误发生的位置以及求出错误值并最终纠正过来。译码流程图如图1所示。

![](images/54a1ecadbc3a62f26f0e0686bff9960c68fa0290358b323d50f6544b91d545b8.jpg)  
图1RS 译码流程图  
Fig.1RS decoding flow chart

为方便研究，定义以下多项式。信息多项式可以表示为

$$
m ( x ) = m _ { 0 } + m _ { 1 } x + \cdots + m _ { k - 1 } x ^ { k - 1 }
$$

编码后的多项式为

$$
c ( x ) = c _ { 0 } + c _ { 1 } x + \cdots + c _ { n - 1 } x ^ { n - 1 }
$$

信道中产生的错误多项式为

$$
e ( x ) = e _ { 0 } + e _ { 1 } x + \cdots + e _ { n - 1 } x ^ { n - 1 }
$$

接收到的多项式可以写为

$$
r ( x ) = r _ { 0 } + r _ { 1 } x + \cdots + r _ { n - 1 } x ^ { n - 1 }
$$

多项式(2)(3)与(4)关系是 $r ( x ) = e ( x ) + c ( x )$ 。含有 $t$ 个错误的多项式表达式为

$$
e ( x ) = e _ { j 1 } x ^ { j 1 } + e _ { j 2 } x ^ { j 2 } + \cdots + e _ { j t } x ^ { j t }
$$

其中： $\boldsymbol { e } _ { j 1 }$ ， $e _ { j 2 }$ ，…， $\boldsymbol { e } _ { j t }$ 为错误值，对应的 $j 1$ ，…， $j t$ 为错误位置。 $j t$ 作为一个整体代表错误位置，并不是 $j$ 和 $t$ 的乘积。为表达方便，用 $Y _ { j }$ 来代替 $\boldsymbol { e } _ { j i }$ ， $X _ { j }$ 代替 $x ^ { j i }$ ， $1 \leq i \leq t$ 。式(5)转换为

$$
e ( x ) = Y _ { 1 } X _ { 1 } + Y _ { 2 } X _ { 2 } + \cdots + Y _ { t } X _ { t }
$$

生成多项式定义为

$$
g ( x ) = \prod _ { j = 1 } ^ { 2 t } ( x - \alpha ^ { C ^ { * } ( b + j ) } )
$$

其中： $C$ 和 $b$ 为一个常数， $\alpha$ 为伽罗华域中的一个本原元，针对CCSDS 标准， $C$ 的取值为11， $b$ 的取值为111。容易发现 $\alpha ^ { C ^ { * } ( b + j ) }$ 是式(7)的根。把 $\alpha ^ { C ^ { * } ( b + j ) }$ 代入到 $r ( x )$ 中得到的值称为伴随式并记做 $s$ 。

$$
s _ { j } = r ( \alpha ^ { C ^ { * } ( b + j ) } ) = r _ { 0 } + r _ { 1 } ( \alpha ^ { C ^ { * } ( b + j ) } ) + \cdots + r _ { n - 1 } ( \alpha ^ { C ^ { * } ( b + j ) } ) ^ { n - 1 }
$$

其中： $1 \leq j \leq 2 t$ ，观察式(8)容易发现，伴随式可以采用循环迭代的方法实现。

$$
s _ { j } = ( \cdots ( r _ { n - 1 } ( \alpha ^ { C ^ { * } ( b + j ) } ) + r _ { n - 2 } ) ( \alpha ^ { C ^ { * } ( b + j ) } ) + \cdots + r _ { 1 } \cdots ) ( \alpha ^ { C ^ { * } ( b + j ) } ) + r _ { 0 }
$$

# 2 求解错误位置多项式

# 2.1原求解算法

根据RS码的编码理论[8]有

$$
s _ { j } = e ( \alpha ^ { C ^ { * } ( b + j ) } ) = \sum _ { i = 1 } ^ { t } Y _ { i } ( \alpha ^ { C ^ { * } ( b + k ) } ) ^ { j i }
$$

RS 解码就是要确定错误值 $Y _ { \mathrm { l } }$ 到 $Y _ { t }$ 和错误位置 $j 1$ 到 $j t$ 。但难以直接求解，一般采用间接求解。定义错误位置多项式为

$$
\sigma ( x ) = \prod _ { i = 1 } ^ { t } ( 1 - \alpha ^ { C ^ { * } j i } x ) = 1 + \sigma _ { 1 } x + \cdots + \sigma _ { t } x ^ { t }
$$

一般采用BM(Berlekamp-Massey)算法来求解错误位置多项 $[ 9 , 1 0 ]$ 。设 $\mu$ 是迭代次数， $\sigma ^ { ( \mu + 1 ) } \left( x \right)$ 是第 $\mu$ 次迭代对应的错误多项式， $d _ { \mu }$ 是第 $\mu$ 次的差值， $l _ { \mu }$ 是 $\sigma ^ { ( \mu ) } ( x )$ 的次数。为求解下一个多项式 $\sigma ^ { ( \mu + 1 ) } \left( x \right)$ ，必须验证差值 $\boldsymbol { d } _ { \mu }$ 。有以下表达式：

$$
d _ { \mu } = s _ { \mu + 1 } + \sigma _ { 1 } ^ { ( \mu ) } s _ { \mu } + \cdots + \sigma _ { l _ { \mu } } ^ { ( \mu ) } s _ { \mu - l _ { \mu } + 1 }
$$

如果 $d _ { \mu }$ 为 $0$ ，则有 $\sigma ^ { ( \mu + 1 ) } \left( x \right) = \sigma ^ { ( \mu ) } \left( x \right)$ 和 $l _ { \mu + 1 } = l _ { \mu }$ 。如果 $d _ { \mu }$ 不为0，则校正 $\sigma ^ { ( \mu ) } ( x )$ 来求 $\sigma ^ { ( \mu + 1 ) } ( x )$ 。校正方法：寻找在第 $\mu$ 次迭代之前的某次迭代 $\rho$ ，使 $d _ { \rho } \neq 0$ 且 $\rho - l _ { \rho }$ 最大， $l _ { \rho }$ 为 $\sigma ^ { \left( \rho \right) } \left( x \right)$ 的次数。则有

$$
\sigma ^ { \left( \mu + 1 \right) } \left( x \right) = \sigma ^ { \left( \mu \right) } \left( x \right) - d _ { \mu } d _ { \rho } ^ { - 1 } x ^ { \mu - \rho } \sigma ^ { \left( \rho \right) } \left( x \right)
$$

从第一次按照这个步骤操作直到 $2 t$ 次迭代结束。那么寻找 $\rho$ 次迭代是BM算法的一个关键步骤。

# 2.2改进的搜索算法

对于式(13)，先假设 $\sigma ^ { ( \mu ) } ( x )$ 和 $\sigma ^ { \left( \rho \right) } ( x )$ 的次数都为 $l _ { \mu }$ 。当所有的 $\boldsymbol { d } _ { \mu }$ 不为0时，那么 $d _ { \rho } ^ { - 1 }$ 也不为0。 $\rho \sigma ^ { ( \mu + 1 ) } ( x )$ 是 $\mu$ 次之前的某次迭代，所以 $\mu - \rho$ 大于1，于是 $d _ { \mu } d _ { \rho } ^ { - 1 } x ^ { \mu - \rho } \sigma ^ { ( \rho ) } ( x )$ 这一项的次数大于 $l _ { \mu }$ ，这样导致 $\sigma ^ { ( \mu + 1 ) } \left( x \right)$ 的次数大于 $l _ { \mu }$ ，这与刚才的假设矛盾。同时注意到， $\sigma ^ { \left( \rho \right) } \left( x \right)$ 是第 $\mu$ 次之前的任意一次， $\sigma ^ { \left( \rho \right) } \left( x \right)$ 可以是 $\sigma ^ { ( \mu - 1 ) } \left( x \right)$ ，也就是第 $\rho$ 次可以是 $\mu - 1$ 次。 $\sigma ^ { ( \mu + 1 ) } ( x )$ 、 $\sigma ^ { ( \mu ) } ( x )$ 和 $\sigma ^ { ( \mu - 1 ) } \left( x \right)$ 的次数都为 $l _ { \mu }$ 这是不成立的。于是得出这样的结论，当 $\boldsymbol { d } _ { \mu }$ 从不为0时，任意连续3次的迭代，得到的多项式的次数不会相等。

又因 $\sigma ( x )$ 的系数有 $\mathbf { \Psi } _ { t }$ 个，需要迭代2t次才能求出 $\mathbf { \chi } _ { t }$ 个系数[11]。 $l _ { \rho }$ 的最大值为 $t$ ， $\sigma ( x )$ 的次数 $l _ { \rho }$ 不能在2t次迭代中呈每次加1的方式增加，那样就会达到2t次。也就是说，任意连续的3次迭代，这3次产生的 $\sigma ( x )$ 的次数不会是差值为1的3个等差数列。而且次数只会增加，不会减小。

根据之前的分析，当所有的 $\boldsymbol { d } _ { \mu }$ 不为0时，任意连续3次求出的 $\sigma ( x )$ 的次数不会相等，也不会全部不相等。所以， $\sigma ( x )$ 的次数 $l _ { \rho }$ 会连续2次相等，即0，0，1，1，2，2，…，这种趋势增加。同时迭代次数 $\rho$ 是从1开始到 $2 t$ 结束差值为1的数列。 $\rho - l _ { \rho }$ 的值是随着迭代次数的增大而增大。

所以当所有的 $\boldsymbol { d } _ { \mu }$ 不为0时，寻找的第 $\rho$ 次迭代，是第 $\mu - 1$ 次，即 $\mu - \rho$ 为1。这就是改进的搜索算法。此时得到改进的公式为

$$
\sigma ^ { ( \mu + 1 ) } \left( x \right) = \sigma ^ { ( \mu ) } \left( x \right) - d _ { \mu } d _ { \mu - 1 } ^ { - 1 } x \sigma ^ { ( \mu - 1 ) } \left( x \right)
$$

在改进搜索算法的基础上，当碰到某次 $d _ { \mu }$ 为0时，找到$\mu$ 次前最近的 $\boldsymbol { d } _ { \mu ^ { * } }$ 不为0的第 $\mu ^ { \mathrm { ' } }$ 次，当求解新的 $\sigma ( x )$ 时，比较$\mu ^ { \cdot } - d _ { \mu ^ { \cdot } }$ 和 $\mu - 1 - d _ { \mu - 1 }$ 大小，并保存下最大的值，只需比较一次。原来的BM算法，其搜索的次数需要 $t ( 1 + 2 t )$ ，复杂度为 $\mathbf { O } ( \mathrm { n } ^ { 2 } )$ U而改进的算法，搜索的次数需要 $2 t$ ，复杂度为 $\mathbf { O } ( \mathrm { n } )$ ，下降了一个数量级。

# 3 求解错误位置

对于 $\mathrm { R S } ( n , k )$ ，使得式(11)为0的值的倒数就是错误位置。试探的值就有 $n$ 个，即 $\alpha ^ { 0 } , \alpha ^ { 1 } , \alpha ^ { 2 } , \cdots , \alpha ^ { n - 2 } , \alpha ^ { n - 1 }$ 。为了方便表示，用 $\alpha ^ { d }$ 表示 $\alpha ^ { 0 } , \alpha ^ { 1 } , \alpha ^ { 2 } , \cdots , \alpha ^ { n - 2 } , \alpha ^ { n - 1 }$ 这 $n$ 个值，其中 $0 \leq d \leq n - 1$ 。把 $\alpha ^ { d }$ 代入到式(11)中，有

$$
1 + \sigma _ { 1 } \alpha ^ { d } + \sigma _ { 2 } \left( \alpha ^ { d } \right) ^ { 2 } \cdots + \sigma _ { t } \left( \alpha ^ { d } \right) ^ { t }
$$

观察式(15)，可以用循环迭代的方法求解，也就是变为

$$
( \cdots ( \sigma _ { t } \alpha ^ { d } + \sigma _ { t - 1 } ) \alpha ^ { d } + \cdots + \sigma _ { 1 } \cdots ) \alpha ^ { d } + 1
$$

# 4 求错误值

# 4.1通用求解错误值算法

在文献[7]介绍的求错误值算法基础上，推导了适合多种标准的求解错误值公式。所有伴随式的值都是确定的实整数值，可以写成多项式的形式：

$$
s ( x ) = 1 + s _ { 1 } x + \cdots + s _ { 2 t } x ^ { 2 t } = 1 + \sum _ { i = 1 } ^ { 2 t } s _ { i } x ^ { i }
$$

结合式(10)， $s ( x )$ 还能表示为

$$
s ( x ) = 1 + \sum _ { i = 1 } ^ { 2 t } \sum _ { k = 1 } ^ { t } Y _ { k } ( \alpha ^ { C ^ { * } ( b + i ) } ) ^ { j k } x ^ { i }
$$

其中： $Y _ { k }$ 为错误值， $j k$ 作为一个整体代表错误位置， $j k$ 的取值是 $j l , j 2 , . . . , j t _ { \circ } ( \alpha ^ { C ^ { * } ( b + i ) } ) ^ { j k }$ 这一部分过于复杂可以改写为（20 $\alpha ^ { j k ( c * b + C * i ) }$ ，也就是 $\alpha ^ { j k ( C ^ { * } b ) } \alpha ^ { ( j k ^ { * } C ) i }$ 。经过求错误位置后， $j k$ 的值是知道的，所以对于 $\alpha ^ { j k ( C ^ { * } b ) } \alpha ^ { ( j k ^ { * } C ) i }$ 这个式子,第一项是个常数，于是 $s ( x )$ 可以表示为

$$
\begin{array} { l } { { \displaystyle s ( x ) = 1 + \alpha ^ { \beta ^ { i } ( c ^ { * } b ) } \sum _ { k = 1 } ^ { l } Y _ { k } \sum _ { i = 1 } ^ { 2 l } ( \alpha ^ { ( j k ^ { * } C ) } x ) ^ { i } } } \\ { { \displaystyle ~ = 1 + \alpha ^ { j k ( c ^ { * } b ) } \sum _ { k = 1 } ^ { l } Y _ { k } \frac { \alpha ^ { ( j k ^ { * } C ) } x \left( 1 - \left( \alpha ^ { ( j k ^ { * } C ) } x \right) ^ { 2 l } \right) } { 1 - \alpha ^ { ( j k ^ { * } C ) } x } } } \\ { { \displaystyle ~ = 1 + \alpha ^ { j k ( c ^ { * } b ) } \sum _ { k = 1 } ^ { l } Y _ { k } \frac { \alpha ^ { ( j k ^ { * } C ) } x - \left( \alpha ^ { ( j k ^ { * } C ) } x \right) ^ { 2 l + 1 } } { 1 - \alpha ^ { ( j k ^ { * } C ) } x } } } \end{array}
$$

定义一个错误值多项式 $w ( x )$ ，且 $w ( x ) = s ( x ) \sigma ( x )$ 。 $s ( x )$ 最高次为2t， $\sigma ( x )$ 的最高次为 $t$ ，二者相乘会出现 $3 t$ 次，需要对$w ( x )$ 做 $2 t { + } 1$ 求余运算，有

尝试对 $\sigma ( x )$ 求一阶导数，有

$$
\begin{array} { l } { { \displaystyle \sigma ^ { * } ( x ) = ( 1 - \alpha ^ { c ^ { * } j _ { 1 } } x ) ^ { * } ( 1 - \alpha ^ { c ^ { * } j _ { 2 } } x ) \cdots ( 1 - \alpha ^ { c ^ { * } j _ { t } } x ) + } } \\ { { \displaystyle ( 1 - \alpha ^ { c ^ { * } j _ { 1 } } x ) ( 1 - \alpha ^ { c ^ { * } j _ { 2 } } x ) ^ { * } \cdots ( 1 - \alpha ^ { c ^ { * } j _ { t } } x ) + \cdots + } } \\ { { \displaystyle ( 1 - \alpha ^ { c ^ { * } j _ { 1 } } x ) ( 1 - \alpha ^ { c ^ { * } j _ { 2 } } x ) \cdots ( 1 - \alpha ^ { c ^ { * } j _ { t } } x ) ^ { * } } } \\ { { \displaystyle = - \sum _ { i = 1 } ^ { t } \alpha ^ { c ^ { * } j _ { i } } \prod _ { \underset { k \neq i } { k = i } } ^ { t } ( 1 - \alpha ^ { c ^ { * } j _ { k } } x ) } } \end{array}
$$

$$
\sigma ^ { \prime } ( \alpha ^ { - j m ^ { * } C } ) = - \alpha ^ { C ^ { * } j m } \underset { k \neq m } { \prod ^ { \nu } } ( 1 - \alpha ^ { C ^ { * } j k } \alpha ^ { - j m ^ { * } C } )
$$

其中： $1 \leq m \leq t$ ， $1 \leq k \leq t$ ，且 $k \neq m$ 。

把 $\alpha ^ { - j m ^ { * } c }$ 代入到式(22)中有

错误位置 $j m$ 是已知的。把 $\alpha ^ { - j m ^ { * } c }$ 代入到式(20)中，由于$\alpha ^ { - j m ^ { * } c }$ 是 $\sigma ( x )$ 的一个根，所以 $\sigma ( x )$ 这一项为0。式(20)的最后一项中的 $\prod _ { i = 1 } ^ { t } ( 1 - \alpha ^ { c * j i } x )$ ，是 $\sigma ( x )$ 的另一种表达形式，所以最后一项也为0。式(20)整理后，有

结合式(21)有

即

$$
w ( \alpha ^ { - j m ^ { * } C } ) = \alpha ^ { j m ( C ^ { * } b ) } Y _ { m } { \frac { \sigma ^ { ' } ( \alpha ^ { - j m ^ { * } C } ) } { - \alpha ^ { C ^ { * } j m } } }
$$

$$
Y _ { m } = \frac { - \alpha ^ { c ^ { * } j m } w ( \alpha ^ { * } { } ^ { c } ) } { \alpha ^ { j m } ( c ^ { * } b ) \sigma ^ { ' } ( \alpha ^ { - } { } ^ { j m ^ { * } } c ) } = \frac { - w ( \alpha ^ { - } { } ^ { j m ^ { * } } c ) } { \alpha ^ { j m b } \sigma ^ { ' } ( \alpha ^ { - } { } ^ { j m ^ { * } } c ) } = \frac { - \alpha ^ { - j m b } w ( \alpha ^ { - } { } ^ { j m ^ { * } } c ) } { \sigma ^ { ' } ( \alpha ^ { - } { } ^ { j m ^ { * } } c ) }
$$

$Y _ { m }$ 就是需要求的错误值。当 $s ( x )$ 和 $\sigma ( x )$ 求出来之后， $w ( x )$ 和 $\sigma ^ { \prime } ( x )$ 都是已知的。RS码的运算是在伽罗华域上进行，于是进一步把式(25)化简为

$$
\begin{array} { r l } & { \mathbb { N } ( x ) = 1 + [ \alpha ^ { 8 ( x - 1 ) } \frac { \gamma } { 2 \lambda _ { 1 } } \frac { \alpha ^ { 4 ( x - 1 ) } x } { 1 - \alpha ^ { 6 ( x - 1 ) } x } \frac { \alpha ^ { 2 } ( x ) } { x }  } \\ & {  - \sigma ( x ) ) + \sigma ^ { 1 ( x - 1 ) } \frac { \gamma } { 1 - \alpha ^ { 4 ( x - 1 ) } x } \frac { \alpha ^ { 4 ( x - 1 ) } x } { 1 - \alpha ^ { 4 ( x - 1 ) } x } ( \alpha )  } \\ & {  = \sigma ( x ) + [ \alpha ^ { 1 ( x - 1 ) } x \frac { \alpha ^ { 4 ( x - 1 ) } x } { 1 - \alpha ^ { 4 ( x - 1 ) } x } +  } \\ & {  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & {  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { = \sigma ( x ) + \alpha ^ { 1 ( x - 1 ) } x \frac { \alpha ^ { 4 ( x - 1 ) } x } { 1 - \alpha ^ { 4 ( x - 1 ) } x } \frac { \alpha ^ { 4 ( x - 1 ) } x } { 1 - \alpha ^ { 4 ( x - 1 ) } x } \frac { \alpha } { x } \Big \vert ( 1 - \alpha ^ { 4 ( x - 1 ) } x ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array}
$$

$$
\begin{array} { c } { { \displaystyle = \sigma ( x ) + \alpha ^ { j m ( C ^ { * } b ) } Y _ { m } \alpha ^ { ( j m ^ { * } C ) } x \prod _ { i = 1 \atop i \neq m } ^ { t } ( 1 - \alpha ^ { C ^ { * } j i } x ) + } } \\ { { \displaystyle \alpha ^ { j k ( C ^ { * } b ) } \sum _ { k \neq m } ^ { t } Y _ { k } \frac { \alpha ^ { ( j k ^ { * } C ) } x } { 1 - \alpha ^ { ( j k ^ { * } C ) } x } \prod _ { i = 1 } ^ { t } ( 1 - \alpha ^ { C ^ { * } j i } x ) } } \end{array}
$$

$$
Y _ { m } = { \frac { w ( \alpha ^ { - j m ^ { * } } c \alpha ^ { - j m b } ) } { \sigma ^ { ' } ( \alpha ^ { - j m ^ { * } } c ) } } = { \frac { w ( \alpha ^ { - j m ( { \cal C } + b ) } ) } { \sigma ^ { ' } ( \alpha ^ { - j m ^ { * } } c ) } } = { \frac { w ( \alpha ^ { n - j m ( { \cal C } + b ) } ) } { \sigma ^ { ' } ( \alpha ^ { n - j m ^ { * } } c ) } }
$$

就是本文推导的适合多种参数的求解错误值公式。

# 4.2求值公式的优化

式(26)中涉及到的 $w ( x )$ 是一个最高次为 $t$ ，由 $t$ 个因式组成的多项式，即 $( 1 - Y _ { 1 } ) ( 1 - Y _ { 2 } ) ( 1 - Y _ { 3 } ) \cdots ( 1 - Y _ { t } )$ ，其中 $1 \leq j \leq t$ 。所以求解 $w ( x )$ 时，不需要把 $s ( x )$ 和 $\sigma ( x )$ 乘加 $2 t$ 次。参与求解的 $s ( x )$ 只需常数项和小于次数 $t { + } 1$ 的系数参与，而 $\sigma ( x )$ 的所有项都参与，这样会省去一半运算。于是有 $w ( x ) = 1 + w _ { 1 } x + w _ { 2 } x ^ { 2 } + \cdots + w _ { t } x ^ { t }$ 且

$$
w ( \alpha ^ { - j m ^ { * } C } ) = \alpha ^ { j m ( { C ^ { * } b } ) } Y _ { m } \prod _ { \stackrel { i = 1 } { i \neq m } } ^ { t } ( 1 - \alpha ^ { C ^ { * } j i } \alpha ^ { - j m ^ { * } C } )
$$

$$
\begin{array} { r l } & { \mathrm {  ~ \sigma ~ } _ { : } ) = 1 + ( s _ { 1 } + \sigma _ { 1 } ) x + } \\ & { \qquad ( s _ { 2 } + s _ { 1 } \sigma _ { 1 } + \sigma _ { 2 } ) x ^ { 2 } + \ldots + } \\ & { \qquad ( s _ { t } + s _ { 1 } \sigma _ { t - 1 } + \cdots + s _ { t - 1 } \sigma _ { 1 } + \sigma _ { t } ) x ^ { t } } \end{array}
$$

# 5 卫星通信中CCSDS的RS译码仿真测试

观察发现 $\prod _ { i = 1 \atop i \ne m } ^ { t } ( 1 - \alpha ^ { C ^ { * } j i } \alpha ^ { - j m ^ { * } C } )$ 比 $\prod _ { i = 1 } ^ { t } ( 1 - \alpha ^ { c * j i } x )$ 少了一个幂次，

测试的RS码是CCSDS 标准下的RS(255,223)[12]。输入的信息数据是1,2,3，…,221,222,223这223个信息符号。RS 编码后产生的32个校验信息分别是[223,143,243,66,0,177,182,232,176,79,114,129,85,7,223,153,129,150,94,238,241,200,6,100,229,108,173,61,98,107,173,240]。那么编码后的255个数据为[1,2,3,,222,223,223,143,243,66,0,177,182,232,176,79,114,129,85，7,223，153，129,150,94,238,241,200,6,100,229,108,173,61,98,107,173,240]。那么这255个数据从左到右，分别对应于发送信息多项式中的 $c _ { n - 1 } , c _ { n - 2 } , \cdots , c _ { 1 } , c _ { 0 }$ 。为了验证本文提出的RS 译码算法那的准确性，令编码后的32个校验数据的前16个数据为1到16，也就是将编码后的数据变为[1,2,3，，222,223,1,2,3，…,14,15,16，129,150,94,238,241,200,6,100,229,108，173，61，98，107，173，240]，对应接收多项式中的$r _ { n - 1 } , r _ { n - 2 } , \cdots , r _ { 1 } , r _ { 0 }$ 。计算后得到的伴随式为[80,194,209,59,138,42,166,186,62,249,35,8,226,71,92,184,126,58,88,203,99,42,131,225,17,110,48,216,73,7,102,241]。

应用改进搜索算法，产生的错误位置多项式的系数为[68,  
40,156,53，121,91,24,126，158,88,97,123,31,134，146,  
251]，一共16个。产生的32个差值 $d _ { \mu }$ 为[80,152,138,172,  
10,243,237,13,158,140,78,176,247,19,23,206,167,130,  
179，70，171，205，79，193，220,31，197,55，172,205,224,  
178]，一共32个。每次运行产生的 $\mu - l _ { \mu }$ 为[0,0,1,1,2,2,3,

3,4,4,5,5,6,6,7,7,8,8,9,9,10,10,11,11,12,12,13,13,14,14,15,15]，一共32个，这些值也正好验证了改进BM搜索算法的正确性。接下来求得错误位置为[224，225，226,227,228,229,230,231,232,233,234,235,236,237,238,239]，相应的错误值为[222,141,240,70,5,183，177,224，185,69,121,141,88,55,208,137]。在伽罗华域里面，把接收信息中错误位置的错误值和RS译码求出的错误值进行相加，就能得到正确的结果。也就是把[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16]和[222，141,240,70,5,183,177,224,185,69,121,141,88,55,208,137]对应相加，得到[223,143,243,66,0,177,182,232,176,79,114,129,85,7,223,153]。修正后的16个值和编码后32个校验值的前16个值是相等的。既原先加入的16个错误，得到了纠正。

接下来，调制方式采用BPSK，噪声为高斯白噪声，在MATLAB环境下进行误比特率测试实验。RS码采用CCSDS的RS(255,223)码。一个符号为8bit，码长255个符号，信息长度为223个符号。编码时涉及到的系数为[1,91,127,86,16,30,13,235,97,165,8,42,54,86,171,32,113,32,171,86,54,42,8,165,97,235,13,30,16,86,127,91,1]。然后根据改进的译码算法，运行百万次测试后得到误比特率曲线，并与理论未编码的BPSK曲线进行对比，如图2所示。

![](images/b77fd83f473d928967263c21c4a139e8804c92167cf0767d529c17d2143de51e.jpg)  
图2 RS(255,223)误比特率曲线Fig.2The BER curve of RS(255,223)

观察图2可以发现，信噪比为 $0 { \sim } 4 ~ \mathrm { d B }$ ，RS(255,223)的曲线和理论值基本一致。但随着信噪比的不断增大，RS(255,223)的曲线开始陡峭，误比特率急速下降。在误比特率为 $1 0 ^ { - 7 }$ 时，RS(255,223)比未编码的BPSK多获得5dB的增益。从而验证了改进译码算法的正确性。

# 6 结束语

本文对RS译码算法进行了深入分析，对求解伴随式、错误位置多项式、错误位置和错误值都进行了研究。其中，通常采用BM算法求解错误位置多项式。BM算法中关键步骤是搜索某一步迭代，本文分析了一种改进的搜索算法，使得搜索复杂度降低了一个数量级；对求解错误位置也进行了优化，结合传统算法，推导了一个更通用的公式。以CCSDS标准下RS(255,223)为研究对象，采用改进的译码算法求解错误位置和求解错误值，进行了具体的数值实验测试和误比特率测试。测试结果表明，采用改进的译码算法可以快速正确译码，同时验证了改进算法的正确性。进一步的工作包括：a)对伴随式模块进行优化研究，根据伴随式的值判断错误发生的情况;b)在硬件电路上实现RS 高速并行译码器和低功耗串行译码器。

# 参考文献：

[1]Wang Tian, Zhou Jiyuan,Liu Anfeng,et al. Fog-based computing and storage offloading for data synchronization in IoT[J].IEEE Internet of Things Journal,2018,DOI:10.1109//JIOT.2018.2875915.   
[2]Demirkan I,Silvus G.Multilevel Reed-Solomon codes for PMR channels [J]. IEEE Trans on Magnetics,2016,52(2):1-8.   
[3]Li Yong,Huang Xiang,He Jiguang,et al.On soft-information-based error and erasure decoding of Reed-Solomon codes in burst rayleigh fading channels [J].IEEE Trans on Communications,2018,DOI:10. 1109//TCOMM.2018.2872033.   
[4]Dissanayake MB,Deng Y,Nallanathan A,et al. Reed Solomon codes for molecular communication with full absorption receiver [J].IEEE Communications Letters,2017,21(6):1-4.   
[5]Chen Ming,Xiao Xin,Li Xinying,et al. Improved BER performance of real-time DDO-OFDM systems using interleaved Reed-Solomon codes [J].IEEE Photonics Technology Letters,2016,28(9):1014-1017.   
[6]Borujeny RR,Ardakani IM.A new class of rateless codes based on Reed-Solomon codes [J].IEEE Trans on Communications,2016,64(1): 49-58.   
[7]张宗橙．纠错编码原理和应用[M].北京:电子工业出版社,2003: 120-130.   
[8]Moon T K.Error correction coding: mathematical methodsand algorithms [M].Hoboken:Wiley,2005:235-280.   
[9]Massey JL. Shift-register synthesis and BCH decoding[J].IEEE Trans on Information Theory,1969,15(1): 122-127.   
[10] Park JI，Lee K,Choi C S,et al. High-speed low-complexity Reed-Solomon decoder using pipelined Berlekamp-Massey algorithm and its folded architecture [J].Journal of Semiconductor Technology & Science,2010,10(3): 193-202.   
[11] Jorge C M,Patrick G F. Essentials of error-control coding [M]. Hoboken:Wiley,2006:100-153.   
[12]CCSDSSecretariat.CCSDS131． 0-B-3BlueBook,TM synchronization and channel coding [S].Washington DC:Management Council of CCSDS,2017.