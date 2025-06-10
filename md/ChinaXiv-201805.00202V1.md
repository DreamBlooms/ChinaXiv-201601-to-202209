# 10轮Midori128的中间相遇攻击

刘亚la,1b,2†，刁倩倩la,3，李玮4,5，刘志强²(1.上海理工大学a.光电信息与计算机工程学院,b.上海市现代化光学重点实验室，上海 200093;2.上海交通大学计算机科学与工程系，上海 200240;3.上海观源信息科技有限公司，上海 200240;4.东华大学 计算机科学与技术学院，上海 201620;5.上海市信息安全综合管理技术研究重点实验室，上海 200240)

摘要：轻量级分组密码由于软硬件实现代价小且功耗低，被广泛地运用资源受限的智能设备中保护数据的安全。Midori是在2015年亚密会议上发布的轻量级分组密码算法，分组长度分为64bit和128bit两种，分别记为Midori64和Midori128，目前仍没有Midori128抵抗中间相遇攻击的结果。通过研究Midori128算法基本结构和密钥编排计划特点，结合差分枚举和相关密钥筛选技巧构造了一条7轮中间相遇区分器。再在此区分器前端增加一轮，后端增加两轮，利用时空折中的方法，提出对10轮的Midori128算法的第一个中间相遇攻击，整个攻击需要的时间复杂度为 $2 ^ { 1 2 6 . 5 }$ 次10轮Midoril28加密，数据复杂度为 $2 ^ { 1 2 5 }$ 选择明文，存储复杂度 $2 ^ { 1 0 5 }$ 128-bit块，这是首次对Midoril28进行了中间相遇攻击。

关键词：分组密码；中间相遇攻击；Midori128   
中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2017.07.0701

# Meet-in-the-middleattacks on 1O-roundMidori128

Liu $\mathrm { Y a } ^ { 1 \mathrm { a } , 1 \mathrm { b } , 2 \dagger }$ , Diao Qianqianla,3, Li Wei4,5, Liu Zhiqiang² (1.a.ScholofOptical-Electrical&ComputerEngineering,bEngineeingResearchCenterofOpticalInstrument&System, MinistryofEducation,ShanghaiKeyLabofModernOpticalSystem,UniversityofShanghaiforScience&Technology,hanghai 200093,China;2.Dept.ofComputer Science&Engineering,Shanghai JiaoTong UniversityShanghai 20o240,China;3. Shanghai Viewsource InformationScience&TechnologyCo,Ltd,Shanghai20240,China;4.SholofComputercience& Technology,Donghua Universityhanghai21620,China;5.hanghaiKeyLaboratoryfIntegrateAdministrationScuity Shanghai 200240, China)

Abstract: The lightweight block ciphers canbewidelyused invariousapplications,suchassmartcities,internetofthingsand cloud computationandsoon,inordertoprotectdataand informationsecure.Midorisalightweight blockcipherproposed in ASIACRYPT2015.Itsblock sizehas two scenarios,i.e,64bitsand128bit,denotedbyMidori64andMidori128respectively. Upto now,therearenoresultsabout met-in-the-middleattacksonMidoril28.This paper developed a meet-in-the-midle atack on10-round Midori128forthefirsttime.Specificaly,studying thebasicconstructionand keyscheduleofMidori128, this paperconstructeda7-round distinguisheron Midoril28byusing thediferential enumerationand key-dependent sieve techniques.Throughappendingoneroundatitstopandtworoundsatitsbotom,thispapermountedameet-in-the-middleattack on10-round Midori128.Inthe atack,time-memorytradeoftechniqueand some weak subkeys wereconsideredsoastoreduce the time complexity of online phase. Finally,the data, time and memory complexities of our attack are $2 ^ { 1 2 5 }$ chosen plaintexts, 2126.5 10-round encryptions and $2 ^ { 1 0 5 }$ 128-bit blocks, respectively.

Key Words:block cipher;meet-in-the-middle attack;midori128

# 0 引言

随着互联网技术的发展和智慧城市的建设，存储和计算资源受限的设备如RFID、传感器等在物联网、云计算以及智慧城市中运用的越来越广泛，如何保证这些设备中数据的安全是一个重要的研究课题。轻量级分组密码由于其软硬件实现效率快、功耗低等特点被广泛地运用到资源受限的设备中保护数据的安全，但高的实现效率必然会牺牲一部分安全性，因此研究轻量级分组密码算法抵抗各种有效的攻击手段是十分必要的。2015年，Banik等人[I在亚密上发布了一个新的轻量级分组密码算法一一Midori。该算法基于SPN结构，轮数为20，密钥长度为128bit，分组长度分为64bit和128bit两种。根据分组长度不同，将Midori算法记为Midori64和Midori128。

Midori算法由于功耗低、实现效率高，在现实生活中具有广泛的应用前景，而研究它的安全性可以为未来在现实中使用提供理论依据。目前，Midori64的安全性已经被差分攻击、不可能差分分析、相关密码不可能差分分析、高阶差分分析、中间相遇攻击以及不变子空间攻击评估过 $[ 2 ^ { - 6 ] }$ ，Midori128的安全性仅被差分分析、不可能差分分析和相关密钥差分分析评估过$[ 7 ^ { - } 1 0 ]$ 。文献[7,8]利用不可能差分分析分别攻击了不考虑白化密钥情况下的10轮Midori128和11轮Midori128；文献[9]运用了差分分析方法攻击了13轮Midori128；文献[10]给出了Midori128全轮的相关密钥差分分析。但目前国内外研究者还没有评估过Midori128抵抗中间相遇攻击的能力，而中间相遇攻击是近年来十分有效的攻击手段，被用来分析过许多著名密码算法的安全性并得到该算法最好的分析结果，如AES 算法[1I]等，因此研究Midori128抵抗中间相遇攻击也是重要的。

中间相遇攻击最早由Diffie 等人[12]提出，其主要思想是将分组密码分为两个部分或者三个部分（中间部分为区分器)，然后猜测两端的相关密钥来加/解密一系列的明密文。若得到的中间状态值相等或满足区分器的预计算表，则此猜测密钥被保留，否则被排除。通过一系列明密文最后可以筛选出正确的密钥。

在仔细研究了Midori128算法结构和密钥编排计划的基础上，首次提出了对10轮Midori128算法中间相遇攻击。在攻击过程中，利用差分枚举技术和相关密钥筛选技术构造了一个7轮的中间相遇区分器，再在区分器前端增加一轮，后端增加二轮，首次实现了对10轮Midori128算法的中间相遇攻击。

# 1 预备知识

# 1.1符号标记

在介绍算法之前，先列出符号标记，具体如下：a) $P , C$ ：明文，密文；b):轮密钥c) $x _ { i } , y _ { i } , z _ { i } , w _ { i }$ ：分别表示在第 $i$ 轮的单元替换、单元混合、列混淆和密钥加操作之前的中间状态值;d) $x _ { i } [ j ]$ ：表示 $i$ 轮的第 $j$ 个单元；e)[]：表示一系列[回]的第 $k$ 个取值;D $\Delta \bigtriangledown _ { \perp } ^ { \perp }$ []：△[] $= \ d \textcircled { 2 } \frac { \ d \textcircled { 2 } } { \ d \textcircled { 2 } }$ [回] $\oplus \sharp _ { \perp } ^ { 0 }$ [回]；g)BP $\bigstar _ { \bigstar }$ ${ \mathfrak { g } } =$ POPDPPDDD $^ { - 1 } ( \sharp \sharp _ { \sharp } )$ h $\textcircled { \cdot } \textcircled { \cdot }$ ： $\overline { { \triangledown } } _ { \perp } =$ PPPPPPPPP $^ { - 1 } ( \not \perp _ { \perp + 1 } )$ 。

# 1.2Midori算法描述

Midori算法是2015年亚密会议上由Banik等人发布的基于SPN结构的轻量级分组密码算法，每一轮的轮函数包括四种运算，分别为单元替换(SubCell)、单元混合(ShuffleCell)、列混淆(MixColumn)和密钥加(KeyAdd)，如图1所示。其中在第一轮加密之前对明文有一个轮密钥加操作，最后一轮取消了单元混合和列混淆操作，只包括单元替换和密钥加操作。

将Midori 算法的状态表示为如下的 $4 \times 4$ 矩阵，每一个单

元是8bit。

$$
S = \left( \begin{array} { c c c c } { { s _ { 0 } } } & { { s _ { 4 } } } & { { s _ { 8 } } } & { { s _ { 1 2 } } } \\ { { s _ { 1 } } } & { { s _ { 5 } } } & { { s _ { 9 } } } & { { s _ { 1 3 } } } \\ { { s _ { 2 } } } & { { s _ { 6 } } } & { { s _ { 1 0 } } } & { { s _ { 1 4 } } } \\ { { s _ { 3 } } } & { { s _ { 7 } } } & { { s _ { 1 1 } } } & { { s _ { 1 5 } } } \end{array} \right)
$$

单元替换(SubCell)：每一个字节运用非线性S盒作单元替换操作。

000:000

单元混合(ShuffleCell)：按字节做移位操作。

$\left( \sharp _ { \boldsymbol { \partial } } , \sharp _ { \boldsymbol { \mathscr { I } } } , \sharp _ { 2 } , \sharp _ { 3 } , \sharp _ { 4 } , \sharp _ { 5 } , \sharp _ { 6 } , \sharp _ { 7 } , \sharp _ { 8 } , \sharp _ { 9 } , \sharp _ { 1 0 } , \sharp _ { 1 2 } , \sharp _ { 1 2 } , \sharp _ { 1 3 } , \sharp _ { 1 4 } , \sharp _ { 1 5 } \right)$ $\gets ( \flat _ { \boldsymbol { \mathcal { D } } } , \flat _ { \boldsymbol { \mathcal { D } } } , \flat _ { \boldsymbol { \mathcal { S } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { S } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } , \flat _ { \boldsymbol { \mathcal { I } } _ { \boldsymbol { \mathcal { I } } } } )$ 列混淆(MixColumn)：每一列乘以 $4 \times 4$ 的 $\mathbf { M }$ 矩阵运算。

$$
M = \left( { \begin{array} { c c c c } { 0 } & { 1 } & { 1 } & { 1 } \\ { 1 } & { 0 } & { 1 } & { 1 } \\ { 1 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 1 } & { 1 } & { 0 } \end{array} } \right)
$$

密钥加(KeyAdd)：将轮密钥和S作异或操作。

密钥编排算法：Midori128算法第一轮的白化密钥和最后一轮的子密钥是128bit主密钥。中间轮密钥为主密钥与一个常数异或，即 $r k _ { i } = K _ { i } \oplus \beta _ { i } ( 1 \leq i \leq 1 9 )$ ，其中 $\beta _ { i }$ 为常数。

定义1(2-δ-set)[13]2-8-set将一个状态的2 个字节(活动单元）取任意值，其他14个字节（固定单元）取固定值所得到的一个集合，此集合共有 $2 ^ { 2 \times 8 }$ 个元素。

命题1(S盒的差分特性)对于一个给定的S盒，若输入差分为 $\Delta _ { i }$ ，输出差分为 $\Delta _ { o }$ ，则平均有一个输入值 $x$ 满足$S ( x ) \oplus S ( x \oplus \Delta _ { i } ) = \Delta _ { o } { \mathrm { ~ } } _ { }$

# 2 中间相遇攻击简介

中间相遇攻击最早是由Diffie和Hellman 提出的，被广泛应用于Hash函数和分组密码尤其是AES算法的安全性分析中[14]。它的基本原理有两种：第一种将加密算法 $E$ 分解成 $E =$ $E _ { 2 } ^ { \circ } E _ { 1 }$ ，其中 $E _ { 1 }$ 和 $E _ { 2 }$ 部分的密钥分别为 $k _ { 1 }$ 和 $k _ { 2 }$ ，猜测 $k _ { 1 }$ 和 $k _ { 2 }$ 的值，若对某个明密文对 $( P , C )$ ，使得 $E _ { 1 } ( P , k _ { 1 } ) = E _ { 2 } ( C , k _ { 2 } )$ ，则 $k _ { 1 }$ 和 $k _ { 2 }$ 的猜测值是正确的，否则即为错误的密钥；第二种将一个加密算法 $E$ 分解成三个部分 $\mathrm { E } = { E _ { 2 } } ^ { \circ } { E _ { m i n } } ^ { \circ } { E _ { 1 } }$ ，其中 $E _ { m i n }$ 中存在一条多轮的区分器， $E _ { 1 }$ 和 $E _ { 2 }$ 部分的相关密钥分别为 $( k _ { 1 } , k _ { 2 } )$ ，首先在$E _ { m i n }$ 部分预计算一个有序序列，然后对某个明密文对 $( P , C )$ ，猜测 $k _ { 1 }$ 和 $k _ { 2 }$ 的值，若 $E _ { 1 } ( P , k _ { 1 } )$ 和 $E _ { 2 } ( C , k _ { 2 } )$ 满足预计算的有序序列，则此猜测密钥是正确的，否则被淘汰。

2000 年，Gilbert等人[15]利用4轮的AES区分器进行7轮碰撞攻击。2008年，Demirci等人[16将AES中间相遇区分器扩展为5轮，并改进8轮的AES-256的分析结果。随后，在2010年，Dunkelman 等人[17]提出了差分枚举技巧等几个降低预计算参数的方法，改进7/8轮AES-192/256的中间相遇分析结果。2014年，Li等人[18]利用密钥编排规律，改进了5轮AES的中间相遇区分器，并给出了9 轮的 AES-192的中间相遇攻击。2016年，文献[11]利用了差分枚举技巧和依赖密钥筛选技巧来构造6轮中间相遇区分器，进一步降低预计算参数，并改进10轮AES-256的分析结果。此外，文献[19\~22]也给出了LED、CLEFIA、Camellia、TWINE、LBlock算法的中间相遇分析。

# 3 10轮Midori128算法的中间相遇攻击问题

首先运用差分枚举和密钥筛选策略构造一个7轮中间相遇区分器，如图2所示，然后在此区分器的前端增加1轮，后端增加2轮实施了对10轮Midori128算法的中间相遇攻击。

# 3.110轮Midori128中间相遇区分器

在图2中，因为 ${ \dot { [ \mathfrak { L } ] } } _ { 8 } [ 5 ] = [ \mathfrak { L } _ { 8 } [ 4 ] \oplus [ \mathfrak { L } _ { 8 } [ 6 ] \oplus [ \mathfrak { L } _ { 8 } [ 7 ]  $ ， $\mathcal { \left[ 3 \right] } _ { 8 } [ 6 ] =$ $\Theta _ { 8 } [ 4 ] \oplus \perp _ { 8 } [ 5 ] \oplus \perp _ { 8 } [ 7 ]$ ，所以 $\left. \vert \vec { \mathfrak { z } } _ { 8 } [ 5 ] \oplus \right. \perp _ { 8 } [ 6 ] = \left. \perp _ { 8 } [ 6 ] \oplus \right. \perp _ { 8 } [ 5 ]$ 。令$\Theta _ { \perp \perp } = \perp _ { 8 } [ 6 ] \oplus \perp _ { 8 } [ 5 ]$ ， $\Theta _ { \mathtt { B B B } } = \Theta _ { 9 } [ 5 ] \oplus \Theta _ { 9 } [ 6 ]$ ，则 $\underline { { \perp } } _ { \perp \perp \perp } = \perp _ { \perp \perp } \oplus$ 8[5][6]。

命题2设 $\bar { \cdot } \mathscr { Q } _ { 2 } [ 3 , 1 2 ]$ 为活动字节，则{,，…， $\bigtriangledown _ { 2 } ^ { 2 ^ { 1 6 } - 1 } \big \}$ 构成了一个2-δ-set。取 $\boldsymbol { \mathbf { \mathit { \mathcal { B } } } _ { 2 } ^ { 0 } }$ ，然后再依次选取18个 $\check { \Xi } _ { 2 } ^ { \perp } ( \check { \Xi } = 1 , \cdots , 1 8 )$ （204号使得其经过S盒运算后满足 $\Delta \bigtriangledown _ { 2 } ^ { \perp _ { \perp } } [ 3 ] = \Delta \bigtriangledown _ { 2 } ^ { \perp _ { \perp } } [ 1 2 ]$ ，将这19个值经过7轮加密，若此集合中一个元素满足图2中的截断差分，则与19个值相关的144bit的有序序列$( \mathbb { P } _ { \mathtt { r p p } \mathtt { p p } } ^ { \sharp _ { 1 } } \oplus \mathbb { P } _ { \mathtt { l o p p } } ^ { \sharp _ { 1 0 } } , \mathbb { P } _ { \mathtt { z p q } \mathtt { z q } } ^ { \sharp _ { 2 } } \oplus \mathbb { P } _ { \mathtt { z p q } \mathtt { z q } } ^ { \sharp _ { 0 } } , \cdots , \mathbb { P } _ { \mathtt { z p p } \mathtt { z p } } ^ { \sharp _ { 1 8 } } \oplus \mathbb { P } _ { \mathtt { z p p } \mathtt { z p } } ^ { \sharp _ { 0 } } )$ ，共 $2 ^ { 1 3 6 }$ 个值。

证明如图2所示，当一个消息对 $( \check { \perp } _ { 2 } ^ { \perp } , \check { \perp } _ { 2 } ^ { \perp } )$ 满足截断差分链时，那么经过7轮加密后，输出差分序列$( \sharp _ { \sharp \sharp \sharp \sharp } ^ { 1 } \oplus \sharp _ { \sharp \sharp \sharp } ^ { 0 } , \sharp _ { \sharp \sharp \sharp } ^ { 2 } \oplus \sharp _ { \sharp \sharp \sharp } ^ { 0 } , \cdots , \sharp _ { \sharp \sharp \sharp \sharp } ^ { 1 8 } \oplus \sharp _ { \sharp \sharp \sharp } ^ { 0 } )$ 的值是由如下 46 个字节决定的：

$$
\begin{array} { r l } & { \check { \check { \Xi } } _ { 2 } ^ { \flat _ { 0 } } [ 3 , 1 2 ] \ \| \ \check { \Xi } _ { 3 } ^ { \flat _ { 0 } } [ 9 , 1 0 ] \ \| \ \check { \Xi } _ { 4 } ^ { \flat _ { 0 } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ] } \\ & { \qquad \| \ \check { \Xi } _ { 5 } ^ { \flat _ { 0 } } [ 0 , 1 , 2 , 3 , 4 , 5 , 7 , 8 , 9 , 1 0 , 1 1 , 1 2 , 1 3 , 1 5 ] } \\ & { \qquad \| \ \check { \Xi } _ { 6 } ^ { \flat _ { 0 } } [ 0 , 1 , 2 , 3 , 4 , 5 , 6 , 8 , 9 , 1 0 , 1 1 , 1 2 , 1 3 , 1 5 ] } \\ & { \qquad \| \ \check { \Xi } \| \check { \Xi } _ { 6 } [ 1 , 3 , 4 , 9 , 1 1 , 1 2 ] \ \| \ \check { \Xi } \| \check { \Xi } _ { 7 } [ 4 , 1 1 ] } \end{array}
$$

可以进一步将上述46个字节减少到如下31个字节：$\Theta _ { 2 } ^ { \perp _ { 0 } } [ 9 ] \parallel \Delta \perp _ { 2 } ^ { \perp _ { 0 } } [ 3 ] \parallel \perp _ { 3 } ^ { \perp _ { 0 } } [ 9 , 1 0 ] \parallel \perp _ { 4 } ^ { \perp _ { 1 } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ $\parallel \Delta \perp _ { 5 } ^ { \perp _ { \perp _ { \perp } } } [ 0 , 1 , 2 , 3 , 5 , 7 , 8 , 9 , 1 0 , 1 2 , 1 3 , 1 4 ]$ $\parallel \perp _ { 7 } ^ { \perp _ { 0 } } [ 1 , 3 , 4 , 9 , 1 1 , 1 2 ] \parallel \perp _ { 8 } ^ { \perp _ { 0 } } [ 4 , 1 1 ] \parallel \Delta [ \Sigma ] _ { 8 } ^ { \perp _ { \perp } } [ 5 ]$

事实上，由于差分存在关系 $\Delta \perp _ { 2 } ^ { \perp _ { \perp _ { \perp } } } [ 3 ] = \Delta \perp _ { 2 } ^ { \perp _ { \perp } } [ 1 2 ] = \Delta \perp _ { 2 } ^ { \perp _ { \perp } } [ 9 ] =$ $\Delta \sharp _ { 2 } ^ { \sharp _ { \bigstar } } [ 1 0 ]$ 并且差分 $\mathbf { \partial } \cdot \Delta \bigtriangledown _ { 2 } ^ { \perp _ { \perp } } \big [ 8 , 1 1 \big ] = 0$ ，故可计算 $\Delta \big [ \mathfrak { R } _ { 3 } ^ { \perp _ { \perp } } [ 9 , 1 0 ]$ 的值。再根据 $\boldsymbol { \bigtriangledown } _ { 3 } ^ { \perp _ { 0 } }$ [9,10]的值，可计算出 $\Delta \bigtriangledown _ { 3 } ^ { \perp _ { \perp } }$ [9,10]的值，进而可以推导出$\Delta \mathbb { B } _ { 4 } ^ { \perp _ { \perp } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 的值。又因为 $\bigtriangledown _ { 4 } ^ { \bigtriangledown _ { 4 } ^ { \bigtriangledown _ { 0 } } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 已知，所以$\Delta \mathbb { B } _ { 4 } ^ { \perp _ { \perp } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 的值可计算。类似地，可以计算 $\Delta \Xi _ { 5 } ^ { \perp _ { \perp } }$ [回] $\bigtriangledown \ne$ 6,14)。根据 $\bigtriangledown _ { 3 } ^ { \perp _ { 0 } } [ 9 , 1 0 ]$ 和 $\mathcal { \perp } _ { 4 } ^ { \perp _ { 0 } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 的值同时能够计算出[1,8]。

因为， $\Delta \mathbb { B } _ { 5 } ^ { \flat } [ 7 ] = \Delta \mathbb { B } _ { 5 } ^ { \flat } [ 4 ] \oplus \Delta \mathbb { B } _ { 5 } ^ { \flat _ { \flat } } [ 5 ] \oplus \Delta \mathbb { B } _ { 5 } ^ { \flat _ { \flat } } [ 6 ] = 0$ ， $\Delta \perp _ { 5 } ^ { \perp _ { \perp } } [ 1 4 ] =$ $\Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp _ { \perp } } } [ 1 2 ] \oplus \Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp _ { \perp } } ^ { \perp } } [ 1 3 ] \oplus \Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp _ { \perp } } } [ 1 5 ] = 0$ ，并且 $\Delta \big [ \mathfrak { P } _ { 5 } ^ { \perp } \big [ 4 \big ] = 0$ ，所以，得到$\Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp } } [ 5 ] = \Delta \perp _ { 5 } ^ { \perp _ { \perp } } [ 6 ]$ 和 $\Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp } } [ 1 5 ] = \Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp } } [ 1 2 ] \oplus \Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp } } [ 1 3 ]$ 。由于$\Delta \texttt { B } [ 0 \sim 3 , 5 , 7 \sim 1 4 ]$ 已知，故可计算 $\Delta \mathbb { B } _ { 5 } ^ { \perp _ { \perp } } [ 0 \sim 5 , 7 \sim 1 3 , 1 5 ]$ 和$\Delta \texttt { B } [ 0 \sim 6 , 8 \sim 1 4 , 1 5 ]$ 的值。又因为 $\Delta \beta _ { 5 } ^ { \mathrm { [ 3 ] } }$ [回] $( \varTheta \neq 6 , 1 4 )$ 的值之前已经计算出，所以根据命题1，可以计算出 $\bigtriangledown _ { 5 } ^ { \bigtriangledown } [ 0 - 5 , 7 \sim 1 3 , 1 5 ]$ 和$\bigtriangledown _ { 5 } ^ { \bigtriangledown _ { \perp _ { \perp } } } [ 0 \sim 3 , 5 \sim 1 0 , 1 2 \sim 1 5 ]$ 。然后根据回 $( \breve { \triangleright } ) \neq 6 , 1 4 \AA ,$ ）和$\checkmark _ { 4 } ^ { \perp _ { 0 } } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 的值，计算4[0,1,6,8,9,14]的值。

![](images/0709ccc48749d246059cce9b339a0dff6a042596f1cc0286d0a769d0a926a587.jpg)  
图2Midori128 算法7轮中间相遇区分器

因为 $\Delta \perp _ { 8 } ^ { \perp _ { \perp } } [ 4 , 7 ] = \Delta \perp _ { 8 } ^ { \perp _ { \perp } } [ 4 , 7 ] = 0$ ，所以 $\Delta \bigtriangledown _ { 8 } ^ { \perp _ { \perp } } [ 5 ] = \Delta \bigtriangledown _ { 8 } ^ { \perp _ { \perp } } [ 6$ 1。因为$\Delta \perp _ { 8 } ^ { \perp } [ 5 ]$ 和 $\rVert _ { 8 } ^ { \perp _ { 0 } } [ 4 , 1 1 ]$ 已知，故 $\Delta \mathbb { B } _ { 8 } ^ { [ 2 ] _ { \perp } } [ 4 , 1 1 ]$ 和 $\Delta \mathbb { B } _ { 7 } ^ { \sharp _ { \mathtt { h } } } [ 1 , 3 , 4 , 9 , 1 1 , 1 3 ]$ 可知。由于 $\bigtriangledown _ { 7 } ^ { \perp _ { 0 } } [ 1 , 3 , 4 , 9 , 1 1 , 1 2 ]$ 已知，故可计算出 $\Delta \mathbb { B } _ { 7 } ^ { \perp _ { \perp } } [ 1 , 3 , 4 , 9 , 1 1 , 1 3 ]$ ，并且根据输出差分的逆运算推导出 $\Delta \mathbb { B } _ { 6 } ^ { \perp _ { \perp } } [ 0 \sim 6 , 8 \sim 1 3 , 1 5 ]$ 。同样地，根据命题1，由 $\Delta \mathbb { B } _ { 6 } ^ { \perp _ { \perp } } [ 0 \sim 6 , 8 \sim 1 4 , 1 5 ]$ 和 $\Delta \texttt { B } [ 0 \sim 6 , 8 \sim 1 3 , 1 5 ]$ 可以得出$\check { \Xi } _ { 6 } ^ { \perp _ { \perp } } [ 0 \sim 6 , 8 \sim 1 4 , 1 5 ]$ 。根据 $\sharp _ { 8 } ^ { \sharp _ { 0 } } [ 4 , 1 1 ]$ ，[1,3,4,9,11,12]值，$\check { \Xi } _ { 6 } ^ { \perp _ { \perp } } [ 0 \sim 6 , 8 \sim 1 4 , 1 5 ]$ 可以计算出[4,11]，[1,3,4,9,11,12]。根据$\mathcal { \perp } _ { 6 } ^ { \perp _ { \perp } } [ 0 \sim 6 , 8 \sim 1 4 , 1 5 ]$ 和 $\bigtriangledown _ { 5 } ^ { \bigtriangledown } [ 0 \sim 5 , 7 \sim 1 3 , 1 5 ]$ 可以计算出5[0,1,2,3,7,8,9,10,14]和5[0,1,2,3,4,11,12,13,15]。

因为，根据列混淆运算知道 $\mathring { \vert \mathfrak { P } \vert } _ { 6 } \big [ 9 \big ] \oplus \mathring { \vert \mathfrak { P } \vert } _ { 6 } \big [ 1 0 \big ] =$ $\sharp \mathbb { P } _ { 6 } [ 9 ] \oplus \sharp \mathbb { P } _ { 6 } [ 1 0 ]$ ，并且回 $\bar { \mathfrak { I } } _ { 6 } [ 9 , 1 0 ]$ 可以由[9,10]推导出，所以可以计算出[10]。根据密钥编排规律，[9,10]可以从[9,10]推导出，并且已经知道 $\boldsymbol { \underline { | } } _ { 3 } ^ { \underline { | } 2 _ { 0 } }$ [9,10]，可以计算出 $\bigtriangledown _ { 2 } ^ { \perp _ { 0 } }$ [9,10]。因为，由列混淆运算知道 $\big | \mathring { \Xi } _ { 2 } ^ { \perp _ { 0 } } [ 9 ] = \mathring { \Xi } _ { 2 } ^ { \perp _ { 0 } } [ 8 ] \oplus \mathring { \Xi } _ { 2 } ^ { \perp _ { 0 } } [ 1 0 ] \oplus \mathring { \Xi } _ { 2 } ^ { \perp _ { 0 } } [ 1 1 ]$ ， $\bar { \perp } _ { 2 } ^ { \perp _ { 0 } } [ 1 0 ] =$ $\perp _ { 2 } ^ { \perp _ { 0 } } [ 8 ] \oplus [ 2 ] _ { 2 } ^ { \perp _ { 0 } } [ 9 ] \oplus [ 2 ] _ { 2 } ^ { \perp _ { 0 } } [ 1 1 ]$ ，所以 $\perp _ { 2 } ^ { \perp } [ 9 ] \oplus \perp _ { 2 } ^ { \perp _ { 0 } } [ 1 0 ] = \perp _ { 2 } ^ { \perp _ { 0 } } [ 9 ] \oplus \perp _ { 2 } ^ { \perp _ { 0 } } [ 1 0 ] ,$ 0知道 $\boldsymbol { \cdot } \underline { \vartriangle } { \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \underline { | \cdot } \boldsymbol { \mu } } } } } } } } }$ [9]，可以算出 $\flat _ { 2 } ^ { \flat _ { 2 } } [ 1 0 ]$ 。根据密钥编排规律，[1,8]可以被5[1,8]推导出， $\mathring { \ge } _ { 4 } [ 0 , 1 , 8 , 9 , 1 4 ]$ 可以被回4[0,1,8,9,14]推导出，[4,11]可以被[4,11]推导出，[1,3,4,11,12]可以被[1,3,4,11,12]和推导出。根据依赖密钥筛选技术，可以将46个字节降低到31个字节，共 $2 ^ { 1 3 6 }$ 种可能值。

![](images/d1e6f58b62a922dbf10d9aac059cbfc8371f183c7e88238bd96315e6e9012746.jpg)  
图310轮Midori128的中间相遇攻击

# 3.210轮Midori128中间相遇攻击过程

基于Midori128算法的7轮中间相遇区分器，在区分器前端增加一轮，在区分器后端增加两轮来构造一个10 轮的中间相遇攻击。如图3所示。攻击过程分为两个部分：预计算阶段和密钥筛选阶段。

# 1）预计算阶段

在这一阶段，需要建立一个表来存储所有的有序序列$( \mathbb { P } _ { \mathtt { r h e r p } } ^ { \sharp _ { 1 } _ { 1 } } \oplus \mathbb { P } _ { \mathtt { p h e r p } } ^ { \sharp _ { 1 } _ { 0 } } , \mathbb { P } _ { \mathtt { z p } \mathtt { z p } } ^ { \sharp _ { 2 } } \oplus \mathbb { P } _ { \mathtt { z p } \mathtt { z p } } ^ { \sharp _ { 0 } } , \cdots , \mathbb { P } _ { \mathtt { z p } \mathtt { z p } \mathtt { z p } } ^ { \sharp _ { 1 8 } } \oplus \mathbb { P } _ { \mathtt { z p } \mathtt { z p } \mathtt { z p } } ^ { \sharp _ { 0 } } )$ ，但在此之前，需要建立预计算表 $\bar { \mathfrak { P } } _ { \perp } ( 1 \leq \bar { \mathfrak { Q } } \leq 6 )$ 。

$\left. \mathfrak { A } _ { 1 } \right.$ ：猜测72bit △8[5] Ⅱg[4,11] Ⅱ[1,3,4,9,11,12]所有可能值，则可计算出[1,3,4,9,11,13],[4,11],[4,11]，进而可得到 $_ 7 [ 4 , 1 1 ] = \perp _ { 7 } [ 4 , 1 1 ] \oplus \perp _ { 8 } [ 4 , 1 1 ]$ 。又因为 $\Delta \bigtriangledown _ { 8 } [ 5 ] = \Delta \bigtriangledown _ { 8 } [ 6 ]$ ，故可计算出 $\Delta \perp _ { 8 } [ 4 , 1 1 ]$ 和[1,3,4,9,11,12]，从而可计算出△[1,3,4,9,11,12]和 △6[1,3,4,9,11,12]。将 △[1,3,4,9,11,12][1,3,4,9,11,12]I[4,11]存储在表中，并通过[4,11]来检索，每一个检索值对应 $2 ^ { 5 6 }$ 个存储值。

$\left. \exists _ { 2 } \right.$ ：猜测72bit $\Delta \perp _ { 2 } [ 3 ]$ Ⅱ[9,10]Ⅱ图4[0,2,3,9,10,11]所有可能值，则可计算出[1,8] $\mathbb { \Xi } _ { 3 } [ 1 , 8 ]$ ，进而可以通过关系式得到（20 $\Xi \vert \Xi _ { 3 } [ 1 , 8 ] = \bar { \Xi } _ { 3 } [ 1 , 8 ] \oplus \Xi _ { 3 } [ 1 , 8 ]$ 。又因为 $\Delta  \vec { \bigtriangledown } _ { 2 } [ 3 ] = \Delta \vec { \bigtriangledown } _ { 2 } [ 1 2 ]$ ，故可计算出 $\Delta \perp _ { 3 } [ 9 , 1 0 ]$ 和△4[0,2,3,9,10,11]，从而可计算出 $\Delta \perp _ { 4 } [ 0 , 2 , 3 , 9 , 1 0 , 1 1 ]$ 和 $\Delta \perp _ { 4 } [ 0 , 1 , 6 , 8 , 9 , 1 4 ]$ 。然后，将△4[0,1,6,8,9,14] I图4[0,2,3,9,10,11] #$\rVert _ { 3 } [ 9 , 1 0 ]$ 存储在表 $\cdot \bigtriangledown _ { 2 }$ 中，并通过 $_ { | 3 } [ 1 , 8 ]$ 来检索,每一个检索值对应 $2 ^ { 5 6 }$ 个存储值。

$\left. \vert \mathfrak { I } _ { 3 } \right.$ ：猜测112bit △4[1,6,8,9,14] △5[0,1,2,3]△[1,3,4,11,12]所有可能值，通过 $\Delta \triangle _ { 4 } [ 1 , 6 , 8 , 9 , 1 4 ]$ 可计算出$\Delta \perp _ { 5 } [ 0 , 5 , 1 0 , 1 5 ]$ ，通过 $\Delta \perp _ { 5 } [ 0 , 1 , 2 , 3 ]$ 可计算出 $\Delta \perp _ { 5 } [ 0 , 5 , 1 0 , 1 5 ]$ 和$\Delta \perp _ { 6 } [ 0 , 1 , 2 , 3 ]$ ，通过△[1,3,4,11,12]可计算出 $\Delta \perp _ { 6 } [ 0 , 1 , 2 , 3 ]$ 。根据命题1，可以推导出5[0,5,10,15]和回6[0,1,2,3]，进而计算出$\mathbb { R } _ { 5 } [ 0 , 1 , 2 , 3 ]$ 和5[0,1,2,3]并可以由关系式计算得到 $_ 5 [ 0 , 1 , 2 , 3 ] =$ $\vec { \scriptscriptstyle \perp } _ { 5 } [ 0 , 1 , 2 , 3 ] \oplus \vec { \scriptscriptstyle \perp } _ { 5 } [ 0 , 1 , 2 , 3 ] ,$ 。将5[0,5,10,15]I[0,1,2,3]存储在表中，并通过5[0,1,2,3] $\Delta \perp _ { 4 }$ [1,6,8,9,14] I $\Delta \perp _ { 6 }$ [1,3,4,11,12]来，每一个检索值有1个存储值。

4：猜测 $8 0 \mathrm { b i } \tan \tt { \Delta } \tt { 4 } [ 0 , 6 , 8 , 9 ] \parallel \Delta \Delta \perp _ { 5 } [ 5 , 7 ] \parallel \Delta \Delta \perp _ { 6 } [ 1 , 3 , 4 , 9 ] )$ 所有可能值。因为 $\Delta \perp _ { 5 } [ 7 ] = 0$ ，所以 $\Delta \Xi _ { 5 } [ 5 ] = \Delta \Xi _ { 5 } [ 6 ]$ 。通过 $\Delta \perp _ { 4 } [ 0 , 6 , 8 , 9 ]$ 可计算出 $\Delta \perp _ { 5 } [ 1 , 4 , 1 1 ]$ ，通过 $\Delta \perp _ { 5 } [ 5 , 6 , 7 ]$ 可计算出 $\Delta \perp _ { 5 } [ 1 , 4 , 1 1 ]$ 和$\Delta \perp _ { 6 } [ 4 , 5 , 6 ]$ ，通过 $\Delta \perp _ { 6 } [ 1 , 3 , 4 , 9 ]$ 可计算出 $\Delta \perp _ { 6 } [ 4 , 5 , 6 ]$ 。根据命题1，可以推导出s[1,4,11]和 $\textcircled { ! } _ { 6 } [ 4 , 5 , 6 ]$ ，进而计算出 $_ 5 [ 5 , 6 , 7 ] , \textcircled { 7 } _ { 5 } [ 4 ]$ 和$\overline { { \perp } } _ { 5 } [ 7 ]$ 并能得到 $\bar { \mathfrak { I } } _ { 5 } [ 7 ] = \bar { \mathfrak { A } } _ { 5 } [ 7 ] \oplus \bar { \mathfrak { Q } } _ { 5 } [ 7 ]$ ， $\textcircled { 7 } \textcircled { 7 } _ { 5 } [ 4 ] = \textcircled { 7 } _ { 5 } [ 4 ] \textcircled { 9 } \textcircled { 7 } _ { 6 } [ 4 ]$ 。将5[1,4,11] Ⅱ[4,5,6]存储在表 $\textcircled { \scriptsize { 1 } } _ { 4 }$ 中，并通过 $\textcircled { 7 } \textcircled { 7 } \textcircled { 1 } \textcircled { 7 } \textcircled { 2 } \textcircled { 4 } \textcircled { 1 }$ $\Delta \perp _ { 4 } [ 0 , 6 , 8 , 9 ] \parallel \Delta \perp _ { 6 } [ 1 , 3 , 4 , 9 ]$ 来检索,每一个检索值有 1 个存储值。

$\beta _ { 5 }$ ：猜测 $9 6 \mathrm { ~ b i ~ t } \Delta \perp _ { 4 } [ 0 , 1 , 8 , 1 4 ] \parallel \Delta \perp _ { 5 } [ 8 , 9 , 1 0 ] \parallel \Delta \perp _ { 6 } [ 3 , 4 , 9 , 1 1 , 1 2 ]$ 所有可能值，通过 $\Delta \perp _ { 4 } [ 0 , 1 , 8 , 1 4 ]$ 可计算出 $\Delta \perp _ { 5 } [ 3 , 9 , 1 2 ]$ ，通过$\Delta \vartriangle { 1 } \lambda _ { 5 } [ 8 , 9 , 1 0 ]$ 可计算出 $\Delta \perp _ { 5 } [ 3 , 9 , 1 2 ]$ 和 $\Delta \perp _ { 6 } [ 8 , 9 , 1 0 , 1 1 ]$ ，通过$\Delta \perp _ { 6 } [ 3 , 4 , 9 , 1 1 , 1 2 ]$ 可计算出 $\Delta \perp _ { 6 } [ 8 , 9 , 1 0 , 1 1 ]$ 。根据命题1，可以推导出图5[3,9,12]和[8,9,10,11]，进而计算出5[8,9,10]和5[8,9,10,11]然后，可以计算出 $\mathtt { \backslash } \mathtt { \backslash } \mathtt { P } _ { 5 } [ 8 , 9 , 1 0 ] = \mathtt { \backslash } \mathtt { J } _ { 5 } [ 8 , 9 , 1 0 ] \oplus \mathtt { \backslash } \mathtt { j } _ { 5 } [ 8 , 9 , 1 0 ]$ 。将$\beta _ { 5 }$ [3,9,12]I[8,9,10,11]存储在表 $\textcircled { 2 } _ { 5 }$ 中，并通过5[8,9,10]$\Delta \perp _ { 4 } [ 0 , 1 , 8 , 1 4 ] \parallel \Delta \perp _ { 6 } [ 3 , 4 , 9 , 1 1 , 1 2 ]$ 来检索,每一个检索值有 1 个存储值。

$\textcircled { 1 } _ { 6 }$ ：猜测80bit △4[0,1,6,9,14] △5[12,13,14] #$\Delta \perp _ { 6 } [ 1 , 9 , 1 1 , 1 2 ]$ 所有可能值。因为 $\Delta \perp _ { 5 } [ 1 4 ] = 0$ ，所以 $\Delta \ b q _ { 5 } [ 1 5 ] =$ $\Delta \mathbb { B } _ { 5 } [ 1 2 ] \oplus \Delta \mathbb { B } _ { 5 } [ 1 3 ] ,$ 。通过 $\Delta \perp _ { 4 } [ 0 , 1 , 6 , 9 , 1 4 ]$ 可计算出 $\Delta \perp _ { 5 } [ 2 , 7 , 8 , 1 3 ]$ ，通过△[12,13,14]可计算出 $\Delta \perp _ { 5 } [ 2 , 7 , 8 , 1 3 ]$ 和 $\Delta \perp _ { 6 } [ 1 2 , 1 3 , 1 5 ]$ ，通过$\Delta \perp _ { 6 } [ 1 , 9 , 1 1 , 1 2 ]$ 可计算出 $\Delta \perp _ { 6 } [ 1 2 , 1 3 , 1 5 ]$ 。根据命题1，可以推导出$\perp _ { 5 } [ 2 , 7 , 8 , 1 3 ]$ 和[12,13,15]，进而计算出[12,13,15]，并且能够得到 $\begin{array} { r } { \frac { \ d \textcircled { 2 } \vert \vec { \tau } \vert _ { 5 } } { \ d { 5 } } [ 1 2 , 1 3 , 1 5 ] = \ d { 1 } \textcircled { 1 } _ { 5 } [ 1 2 , 1 3 , 1 5 ] \textcircled { 6 } \ d { 1 } _ { 6 } [ 1 2 , 1 3 , 1 5 ] } \end{array}$ 。然后，将$\perp _ { 5 } [ 2 , 7 , 8 , 1 3 ] \parallel \perp _ { 6 } [ 1 2 , 1 3 , 1 5 ]$ 存储在表 ${ \cdot } \boxed { \cdot } 6$ 中，并通过[12,13,15]$\Delta \perp _ { 4 } [ 0 , 1 , 6 , 9 , 1 4 ] \parallel \Delta \perp _ { 6 } [ 1 , 9 , 1 1 , 1 2 ]$ 来检索,每一个检索值有 1 个存储值。

$\left. \vert \mathfrak { I } _ { 0 } \right.$ ：猜测 96bit5[0,1,2,3,7,8,9,10]I[4,12,13,15]所有可能值，做如下运算。

根据密钥编排计划，通过4[4]和[8,9,10]可以得到[4,11]。然后通过[4,11]搜索表 $\left. \overline { { \mathfrak { A } } } _ { 1 } \right.$ ，得到值△6[1,3,4,9,11,12]Ⅱ[1,3,4,9,11,12]Ⅱ[4,11]。同样，通过5[1,8]，可以得到值[1,8]，搜索表，得到△4[0,1,6,8,9,14]图4[0,2,3,9,10,11] [9,10]。

对于所有在以上过程中已经搜索得到的 $2 ^ { 1 1 2 }$ 个值$\Delta \perp _ { 6 } [ 1 , 3 , 4 , 9 , 1 1 , 1 2 ] \parallel \perp _ { 7 } [ 1 , 3 , 4 , 9 , 1 1 , 1 2 ] \parallel \perp _ { 8 } [ 4 , 1 1 ] \parallel$ △4[0,1,6,8,9,14] Ⅱ[9,10] Ⅱ4[0,2,3,9,10,11]，检测表可以得到值5[0,5,10,15] ‖☑6[0,1,2,3]。因为 $\lvert _ { 5 } [ 7 ]$ 和5[4]已知，通过5[7]I5[4]I△4[0,6,8,9] I△[1,3,4,9]检测表 $\textcircled { \scriptsize { 1 } } _ { 4 }$ 得到值5[4,11,1] ‖6[4,5,6]。同样地，通过[8,9,10] I△4[0,1,8,14]$\Delta \perp _ { 6 } [ 3 , 4 , 9 , 1 1 , 1 2 ]$ 检测表5得到值[3,9,12]Ⅱ[8,9,10,11]。通过5[12,13,15]I△4[0,1,6,9,14]I△[1,9,11,12]检测表得到值5[7,13,2,8] I 6[12,13,15]。

对于从表，，，检测到的值 $\mathcal { Q } _ { 5 } [ 0 { \sim } 5 , 7 { \sim } 1 3 , 1 5 ]$ =4[0,2,3,9,10,11]，可以计算出图4[0,1,6,8,9,14]和4[0,1,6,8,9,14]，从而可以得到 $\begin{array} { r } { { \vert { \vert { \boldsymbol { q } } \vert } } _ { 4 } [ 0 , 1 , 6 , 8 , 9 , 1 4 ] = \bar { \boldsymbol { { \vert { \boldsymbol { \mathcal { Q } } } } \vert } } _ { 4 } [ 0 , 1 , 6 , 8 , 9 , 1 4 ] \oplus \bar { \boldsymbol { { \vert { \boldsymbol { \Xi } } \vert } } } _ { 4 } [ 0 , 1 , 6 , 8 , 9 , 1 4 ] , } \end{array}$ 同样，通过 $\scriptstyle { \mathbb { P } } _ { 6 } [ 0 \sim 6 , 8 \sim 1 3 , 1 5 ]$ [1,3,4,9,11,12]可以计算出[1,3,4,9,11,12]。根据密钥编排计划，通过4[0,1,8,9,14]和6[1,3,4,11,12]可以计算出密钥5[0,1,8,9,14]和图[1,3,4,11,12]将该计算出的值与原来的猜测密钥[0,1,8,9,14]I[1,3,4,11,12]进行对比。如果两个值相等，则保留该一系列的值 [9,10] I[4[0,2,3,9,10,11]I5[] ${ \tt \{ \breve { \sf { \cdot } } \breve { \sf { \cdot } } \breve { \sf { \cdot } } \breve { \sf { \cdot } } }  \neq 6 , 1 4 ,$ 回 $( { \bigtriangledown } \neq$ 7,14)‖6[1,3,4,9,11,13] [4,11]。一共有 $2 ^ { 1 1 2 }$ 个检索值，但是每个值被保留的概率为 $2 ^ { - 8 0 }$ ，所以最终有 $2 ^ { 3 2 }$ 个值保留下来。

对于所有 $2 ^ { 3 2 }$ 个值，根据密钥编排规律和已经计算出的密钥值可以推导出 $\left| _ { 2 } \big [ 9 , 1 0 \big ] \right|$ 并且计算 $\dot { \cdot } \textcircled { > } 1 0 ]$ 。根据列混淆运算，可以知道 ${ \perp } _ { 2 } [ 9 ] \oplus { \perp } _ { 2 } [ 1 0 ] = { \perp } _ { 2 } [ 9 ] \oplus { \perp } _ { 2 } [ 1 0 ]$ ，所以对于 $2 ^ { 8 }$ 个值[9]，可以计算出[10]并此推导出 $\bar { \bigtriangledown } _ { 2 } \big [ 3 , 1 2 \big ]$ 。由此，得到所有46字节的参数。通过这些所计算的参数计算有序序列$( \mathbb { P } _ { \mathtt { r p p l e } } ^ { \sharp _ { 1 } } \oplus \mathbb { P } _ { \mathtt { r p p } ; \mathtt { r p } } ^ { \sharp _ { 0 } } , \mathbb { P } _ { \mathtt { r } \sharp \sharp \sharp \sharp } ^ { \sharp _ { 2 } } \oplus \mathbb { P } _ { \mathtt { r p p } ; \mathtt { r p } } ^ { \sharp _ { 0 } } , \cdots , \mathbb { P } _ { \mathtt { r p p l e p } } ^ { \sharp _ { 1 8 } } \oplus \mathbb { P } _ { \mathtt { r p p } ; \mathtt { r p } } ^ { \sharp _ { 0 } } )$ ，并且将56bit5[0,1,2,3,12,13] [9]的值一并保存。

# 2）密钥筛选阶段

在对密钥进行筛选之前，需要预计算4个预计算表 $T _ { i } ( 7 \leq$ $i \leq 1 0 \$ 0，具体如下：

：猜测 $\begin{array} { r } { 7 2 \mathrm { b i } ^ { \mathrm { t } } \Delta \mathbb { B } _ { 9 } [ 5 ] \parallel \Delta \mathbb { B } _ { 9 } [ 2 , 1 1 ] \parallel \perp _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ] \hat { \textmu } \hat { \mathrm { f } } \hat { \mathrm { f } } \hat { \mathrm { \textmu } } \stackrel { \mathrm { ~ \scriptsize ~ . ~ } } { \mathrm { ~ \textmu } } } \end{array}$ 可能值，可以计算出 $\Delta \perp _ { 9 }$ [5,6]， $\overline { { | \bar { \mathfrak { I } } _ { 9 } [ 2 , 1 1 ] } }$ 。因为 $\mathsf { I } \Delta \bar { \mathsf { z } } _ { 9 } [ 5 ] = \Delta \bar { \mathsf { z } } _ { 9 } [ 6 ]$ ，根据命题1，可得到[5,6], $\mathbb { \rho } _ { \mathfrak { g } } [ 2 , 1 1 ]$ 。然后可以计算出 $_ { 9 } [ 2 , 1 1 ] =$ $\bar { \perp } _ { 9 } [ 2 , 1 1 ] \oplus \perp _ { 9 } [ 2 , 1 1 ]$ 。将[5,6]Ⅱ△[5]存储在表中，并通过[2, $1 1 ] \parallel \perp _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ] \parallel \Delta \perp _ { 9 } [ 2 , 1 1 ]$ 来检索，每一个检索值对应 $2 ^ { - 8 }$ 个存储值。

$\textcircled { \mathfrak { A } } _ { 8 }$ ：猜测 $\mathsf { 5 6 b i t } \Delta \mathsf { P } [ 0 , 5 , 1 0 ] \parallel \mathsf { P } [ 0 , 5 , 1 0 ] \parallel \Delta \perp _ { 1 } [ 3 ] .$ 所有可能值，可以计算出 $\Delta \perp _ { 1 } [ 0 , 5 , 1 0 ]$ ， $\Delta \emptyset _ { 1 } [ 0 , 5 , 1 0 ]$ 。根据命题1，可得到$\mathtt { \Pi } _ { \mathtt { N } _ { 1 } } [ 0 , 5 , 1 0 ]$ 和[0,5,10]，然后计算出 $\perp _ { 0 } [ 0 , 5 , 1 0 ] ( =$ P[0,5,10]④[0,5,10])和 $\bigtriangledown _ { 1 } [ 3 ]$ 。将[3]△[3]‖[5]存储在表 $\exists _ { 8 }$ 中，并通过[0,10] Ⅱ△P[0,5,10] ⅡP[0,5,10]来检索,每一个检索值对应 $2 ^ { - 8 }$ 个存储值。

：猜测 56bit△P[2,8,13] ⅡP[2,8,13] I△[12]所有可能值，计算出 $\Delta \perp _ { 1 } [ 2 , 8 , 1 3 ]$ ， $\Delta \perp _ { 1 } [ 2 , 8 , 1 3 ]$ 。根据命题1，可得到[2,8,13]和[2,8,13]，然后计算出 $\scriptscriptstyle { \Theta [ \vec { \Theta } ] _ { 0 } [ 2 , 8 , 1 3 ] = \Theta [ 2 , 8 , 1 3 ] \oplus \vec { \Theta } _ { 1 } [ 2 , 8 , 1 3 ] }$ 和$\perp _ { 1 } [ 1 2 ]$ 。将[12] $\parallel \Delta \perp _ { 1 } [ 1 2 ]$ 丽 $\mathbb { J } _ { 0 } [ 2 , 1 3 ]$ 存储在表中，并通过[8]I△P[2,8,13]IP[2,8,13]来检索，每一个检索值对应1个存储值。

$\textcircled { \mathfrak { A } } _ { 1 0 }$ ：猜测40bit $\Delta \perp _ { 1 } [ 3 , 1 2 ] \parallel \perp _ { 1 } [ 3 , 1 2 ] \parallel \Delta \perp _ { 2 } [ 3 ]$ 所有可能值，计算△[3,12]。因为 $\Delta \perp _ { 2 } [ 3 ] = \Delta \perp _ { 1 2 } [ 1 2 ]$ ，根据命题1，可以得到$\mathbb { P } _ { 2 } \left[ 3 , 1 2 \right]$ 和 $\perp _ { 2 } [ 3 , 1 2 ]$ ，再计算 $\mathbb { i } _ { 1 } [ 3 , 1 2 ] = \mathbb { i } _ { 1 } [ 3 , 1 2 ] \oplus \mathbb { i } _ { 2 } [ 3 , 1 2 ]$ 。然后，将[3,12][12]存储在表 $\textcircled { \mathfrak { A } } _ { 1 0 }$ 中，通过 $\perp \perp _ { 1 } [ 3 ] \parallel \Delta \perp _ { 1 } [ 3 , 1 2 ] \parallel$ $\mathbb { \ R } _ { 1 } [ 3 , 1 2 ]$ 来检索，每一个检索值对应1个存储值。

接下来，在密钥筛选阶段，首先要找到一对正确对满足截断差分链；再通过这一个正确对计算有序序列$( \sharp _ { \sharp \sharp \sharp \sharp } ^ { \sharp _ { 1 } } \oplus \sharp _ { \sharp \sharp \sharp } ^ { \sharp _ { 0 } } , \sharp _ { \sharp \sharp \sharp } ^ { \sharp _ { 2 } } \oplus \sharp _ { \sharp \sharp \sharp } ^ { \sharp _ { 0 } } , \cdots , \sharp _ { \sharp \sharp \sharp \sharp } ^ { \sharp _ { 1 8 } } \oplus \sharp _ { \sharp \sharp \sharp } ^ { \sharp _ { 0 } } )$ ，检测其是否满足表，最后利用表 $\bigtriangledown _ { 0 }$ 中存储的密钥再次判断计算出的密钥[0,1,2,3,12,13]I[9]是否满足表，并筛选出正确的密钥。

假设明文 $P [ 0 , 2 , 5 , 8 , 1 0 , 1 3 ]$ 取任意值，其余10个字节取固定值，这样形成了一个结构，共有 $2 ^ { 4 8 }$ 个明文值，可以形成 $2 ^ { 4 8 + 4 7 } =$ $2 ^ { 9 5 }$ 个明密文对。选取P[1,3,4,6,7,9,11,12,14,15]的 $2 ^ { 6 5 }$ 个不同的值，也即选取 $2 ^ { 1 1 3 }$ 个明文，形成 $2 ^ { 1 6 0 }$ 个明密文对。因为一个明文对能够满足7轮截断差分链的概率为 $2 ^ { ( 1 - 6 + 1 - 1 6 ) \times 8 } = 2 ^ { - 1 6 0 }$ ，所以在每一个猜测密钥下，平均有一对能够满足截断差分链。加密这 $2 ^ { 1 1 3 }$ 个明文得到密文，筛选出满足密文差分为$\Delta \mathrm { C } [ 2 , 4 , 5 , 6 , 7 , 1 1 , 1 2 , 1 3 , 1 4 , 1 5 ] = 0$ 的明密文，共 $2 ^ { 1 6 0 - 1 0 \times 8 } = 2 ^ { 8 0 }$ 明密文对。

对于这 $2 ^ { 8 0 }$ 明密文对，做如下操作：

a)猜测 $\Delta \perp _ { 9 } [ 2 , 1 1 ]$ 的所有可能值，可以计算出$\Delta \perp _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ ，根据命题1，通过 $\Delta \perp _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ 和△C[0,1,3,8,9,10]可以得到 $\mathcal { Q } _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ ，计算出$\mathtt { \mathtt { P } } \mathtt { P } _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ ，从而可以得到 $\mathtt { \backslash } \mathtt { P } _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ 的值，即[2,11]的值。一共有 $2 ^ { 1 6 }$ 个值 $\Delta \perp _ { 9 } [ 2 , 1 1 ]$ ，所以推导出 $2 ^ { 1 6 }$ 个△[2,11] I o[0,1,3,8,9,10]  图[2,11] $\parallel \perp _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ]$ ，对于这些值搜索表，得到 $2 ^ { - 8 }$ 个检索值[5,6]Ⅱ△[5]，则有 $2 ^ { 8 }$ 个值满足截断差分链后端的差分。

b）对于 $2 ^ { 8 }$ 个值回o[0,1,3,8,9,10] I[2,11],根据密钥编排计划，可以计算出 $\sharp \sharp _ { 0 } [ 0 , 1 0 ]$ 。利用 $\mathtt { P I } \mathtt { P } _ { 0 } [ 0 , 1 0 ] \parallel \Delta \mathsf { P } [ 0 , 5 , 1 0 ] \parallel$ P[0,5,10]搜索表g，平均来讲，对于每一个检索得到 $2 ^ { - 8 }$ 个值$\mathtt { \beta } _ { 1 } [ 3 ] \parallel \Delta \perp _ { 1 } [ 3 ] \parallel \bigtriangledown \perp _ { 0 } [ 5 ]$ 。所以，平均来说一共有1个值o[0,1,3,8,9,10]I图[2,11]Ⅱ[[3]I△[3]Ⅱ[5]被保留。

c）对于这一个值o[0,1,3,8,9,10] [2,11] $\parallel \perp _ { 1 } [ 3 ] \parallel$ $\Delta \bigtriangledown _ { 1 } \big [ 3 \big ]$ ‖[5]，根据密钥编排计划，可以计算出 $\mathsf { l } _ { 0 } [ 8 ]$ ，搜索表 $\bigtriangledown _ { 9 }$ ，平均来，可以得到1个检索值 $\vec { \mathbb { L } } \perp _ { 1 } [ 1 2 ] \parallel \Delta \perp _ { 1 } [ 1 2 ] \parallel \perp \perp _ { 0 } [ 2 , 1 3 ] ,$

d）对于以上步骤中已得到的值 $\mathfrak { I } _ { 1 0 } [ 0 , 1 , 3 , 8 , 9 , 1 0 ] \ \parallel$ [2,11]‖[3]Ⅱ△[[3]Ⅱ[2,5,13]Ⅱ[12]Ⅱ△[12]，可以通过亚 $\vert _ { 1 0 } [ 3 ]$ 计算 $\lvert _ { 1 } [ 3 ]$ ，并且搜索表 $\textcircled { \mathfrak { P } } _ { 1 0 }$ ，得到1个检索值[3,12]Ⅱ[12]。最终对于每一个明密文对来说，平均只有1个可能值o[0,1,3,8,9,10] [2,11] [0,2,5,8,10,13]

（204 $\perp \perp _ { 1 } [ 3 , 1 2 ] \parallel \perp _ { 2 } [ 3 , 1 2 ] \circ$

e）根据有序序列的差分值，改变[3,12]的值得到一个序列为 $\{ \varTheta _ { 2 } ^ { \perp _ { 0 } } , \vec { \bigtriangledown } _ { 2 } ^ { \perp _ { 1 } } , \cdots , \vec { \bigtriangledown } _ { 2 } ^ { \perp _ { 1 8 } } \}$ 。根据检测到的密钥将这一序列$\{ \varTheta _ { 2 } ^ { \perp _ { 0 } } , \flat _ { 2 } ^ { \perp _ { 1 } } , \cdots , \flat _ { 2 } ^ { \perp _ { 1 8 } } \}$ 推导出明文值 $\{ \mathsf { P } ^ { \perp _ { 0 } } , \mathsf { P } ^ { \perp _ { 1 } } , \cdots , \mathsf { P } ^ { \perp _ { 1 8 } } \}$ ，并且计算出相应密文 $\{ \mathsf { C } ^ { \perp _ { 0 } } , \flat ^ { \perp _ { 1 } } , \cdots , \mathsf { C } ^ { \perp _ { 1 8 } } \}$ 。同样，用所求的密钥解密得到$( \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 1 } } \oplus \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 1 } } , \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 2 } } \oplus \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 2 } } , \cdots , \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 1 } } \oplus \mathbb { P } _ { \mathtt { P I P D } } ^ { \mathtt { P } _ { 0 } } ) ,$ 。若所计算的序列值不在表$\bigtriangledown _ { 0 }$ 中，则排除相应密钥。若序列值存在表 $\ L _ { \left. \right.}  0$ 中，则再次判断密钥值 $\sharp \sharp _ { 0 } [ 2 , 1 3 ] \ \lVert \ \underline { > } \rVert _ { 1 } [ 3 , 1 2 ] \ \lVert \ \bigtriangledown \perp _ { 1 0 } [ 0 , 1 , 3 , 9 ]$ 是否能够推导出表 $\ L _ { \left. \right.}  0$ 中的5[0,1,2,3,12,13] $\parallel \perp \perp _ { 6 } [ 9 ]$ 。若能，则此密钥被保留，保留下来的概率为 $2 ^ { ( 1 7 - 1 8 ) \times 8 - 5 6 } = 2 ^ { - 6 4 }$ 。

将剩下 $2 ^ { 1 6 }$ 个密钥和6个字节的未猜测密钥进行穷举搜索。

# 3.3 复杂度分析

攻击的复杂度分析分为预计算阶段和密钥筛选阶段两部分。在预计算阶段，构造 ${ \mathrm { ~ T } } _ { 0 }$ 需要对19个信息值进行 $2 ^ { 1 3 6 }$ 次7轮的部分的加密，所以时间复杂度为 $2 ^ { 1 3 6 } { \times } 1 9 { \times } 4 4 / 1 6 0 { = } 2 ^ { 1 3 8 }$ 次10轮Midori128加密，存储复杂度为 $^ { 1 } 2 ^ { ^ { 1 3 6 } \times 1 9 \times 8 \times 2 ^ { - 7 } = 2 ^ { 1 3 6 } }$ 个128-bit 块,且它们决定了预计算阶段的复杂度。在筛选密钥阶段，首先需要加密 $2 ^ { 1 1 3 }$ 个选择明文来得到相应的密文，并筛选出符合密文差分的明密文对。所以时间复杂度为 $2 ^ { 1 1 3 }$ 次10轮Midori128加密，数据复杂度 $2 ^ { 1 1 3 }$ 个明文。然后对剩余的 $2 ^ { 8 0 }$ 个明密文对以及相应的19个信息值部分加密来判断有序序列是否属于表 ${ \mathrm { \Omega } } _ { \mathrm { T 0 } }$ 中。时间复杂度为 $2 ^ { 8 0 } { \times } 1 9 { \times } 1 6 / 1 6 0 { = } 2 ^ { 8 1 }$ 次 10轮 Midori128加密。因此密钥筛选阶段的数据复杂度、时间复杂度和存储复杂度分别为$2 ^ { 1 1 3 }$ 个选择明文， $2 ^ { 8 1 }$ 次10轮Midoril28加密和 $2 ^ { 8 2 1 2 8 \mathrm { b i t } }$ 块。综上，整个攻击的数据复杂度、时间复杂度和存储复杂度分别为$2 ^ { 1 1 3 }$ 个选择明文、 $2 ^ { 1 3 8 }$ 次10轮Midoril28加密和 $2 ^ { 1 3 6 }$ 个128-bit块。

此外，为了优化算法的复杂度，可以对攻击过程进行数据、时间和存储复杂度折中，令折中的系数 $\scriptstyle \alpha = 2 ^ { 1 2 }$ ，所以预计算阶段的时间复杂度为 $2 ^ { 1 2 6 }$ 次10 轮Midoril28加密，存储复杂度为$2 ^ { 1 2 4 1 2 8 }$ -bit 块。而折中后密钥筛选阶段的数据复杂度为 $2 ^ { 1 2 5 }$ 个选择明文，时间复杂度为 $2 ^ { 1 2 5 } \substack { + 2 ^ { 9 3 } \approx 2 ^ { 1 2 5 } }$ 次 10 轮 Midoril28加密，存储复杂度为 $2 ^ { 9 4 1 2 8 }$ -bit 块。因此，整个攻击时间复杂度为$2 ^ { 1 2 6 } { + } 2 ^ { 1 2 5 } { \approx } 2 ^ { 1 2 6 . 5 }$ 次10轮 Midori128加密，数据复杂度为 $2 ^ { 1 2 5 }$ 个明文，存储复杂度为 $2 ^ { 1 2 4 } \substack { + 2 ^ { 9 4 } \approx 2 ^ { 1 2 4 } } 1 2 8$ -bit块。

更进一步，由于预计算阶段和密钥筛选阶段分别需要猜测的密钥包含 $\mathrm { { \dot { \ r u } _ { 5 } } [ 0 , 1 , 2 , 3 ] } ^ { \mathfrak { F } \mathbb { H } _ { \mathbf { r k } _ { 1 0 } } [ 0 , 1 , 3 ] / / \mathbf { r k } _ { 0 } [ 2 ] }$ ，可以根据密钥计划，利用它们的关系做弱密钥攻击，即对应于每个 $\mathrm { r u } _ { 5 } [ 0 , 1 , 2 , 3 ]$ 的固定值，建立 ${ \bf \nabla } \cdot { \bf { T } } _ { 0 }$ 的子表 ${ \mathrm { \Delta T _ { 0 } ^ { * } } }$ ，因此存储复杂度可以降低 ${ \cdot 2 } ^ { - 3 2 }$ 倍，故建立 $\cdot \mathrm { { T } _ { 0 } ^ { * } }$ 的存储复杂度在预计算阶段不占主要的，而建立预计算表T3所需的存储复杂度将占主导地位，因此整个攻击的存储复杂度可降为为 $2 ^ { 1 1 2 - 7 } = 2 ^ { 1 0 5 1 2 8 - }$ bit。

分组长度为128bit的Midori128算法结构与AES类似，使用了16个8bit的S盒和分支数为4的类MDS矩阵，但Midori128用按字节置换操作替换AES的行移位操作，使得算法的扩散性和混淆性更好，直接影响到中间相遇攻击区分器构造，提高了Midori128算法抵抗中间相遇攻击的能力。分析结果表明，在结合差分枚举和依赖密钥筛选的技巧下，10轮的Midori128算法不能够很好的抵抗中间相遇攻击，而更高轮数的Midori128算法目前可以抵抗中间相遇攻击。

# 4 结束语

本文主要研究了Midori128算法对抗中间相遇攻击的安全性分析。首先是利用利用差分枚举技巧和依赖密钥筛选技巧来构造一个7轮中间相遇区分器，并且在这个区分器前端增加一轮，后端增加两轮，实现了对Midori128 算法10 轮抵抗中间相遇攻击。最后运用时空复杂度折中和弱密钥分别降低了攻击的时间复杂度和存储复杂度。因此，整个攻击的数据复杂度 $2 ^ { 1 2 5 }$ 选择明文，时间复杂度为 $2 ^ { 1 2 6 . 5 } 1 0$ 轮Midori128加密，存储复杂度$2 ^ { 1 0 5 } 1 2 8$ -bit 块。这是第一个对Midori-128 抵抗中间相遇的分析。

# 参考文献：

[1]Banik S,BogdanovA,Isobe T, et al.Midori: a block cipher for low energy [C]//Advances in Cryptology-ASIACRYPT 2015.Berlin: Springer, 2015: 411-436.   
[2]Dong Xiaoyang, Shen Yanzhao. Cryptanalysis of reduced-round Midori64 block cipher [EB/OL]. htp://print.iacr. org/2016/676.pdf.   
[3]Chen Zhan，Bi Wenquan，Wang Xiaoyun． Impossible differential cryptanalysis of midori64 [EB/OL]. htp://eprint. iacr. org/2016/535. pdf.   
[4]Takahashi Y. Higher-order differential attack on the round-reduced variants of the block cipher Midori64,IEICE Tech.Rep.[R].2016:159-164.   
[5]Lin Li,Wu Wenling.Meet-in-the-middle attacks on reduced-round Midori64 [EB/OL].http://eprint.iacr.org/2015/1165.pdf.   
[6]Guo Jian,Jean J, Nikoli'c I,et al. Invariant subspace attack against full midori64 [EB/OL]. http://eprint. iacr.org/2015/1189.pdf.   
[7]Chen Zhan,Chen Huaifeng,Wang Xiaoyun. Cryptanalysis of Midori128 using impossible differential techniques [C]// Proc of Information Security Practice and Experience.Berlin: Springer, 2016:1-12.   
[8]Bi Wenquan,Li Zheng,Dong Xiaoyang. Impossible differential attack on Midori128 using rebound-like technique [EB/OL]. http://eprint.iacr. org/2017/286. pdf.   
[9]Tolba M,Abdelkhalek A, Youssef AM. Truncated and multiple differential cryptanalysis ofreduced round Midoril28 [C]//Proc of Information Security. Berlin: Springer, 2016: 3-17.   
[10] Gerault D,Lafourcade P.Related-key cryptanalysis of midori[C]//Proc of Cryptology-INDOCRYPT 2016.Berlin: Springer,2016:287-304.   
[11] Li Rongjia,Jin Chenhui.Meet-in-the-middle attacks on 10-round AES-256 [J].Designs, Codes and Cryptography,2016,80 (3): 459-471.   
[12] Diffie W, Hellman ME.Special feature exhaustive cryptanalysis ofthe NBS data encryption standard [J]. Computer,1977,10 (6): 74-84.   
[13] LiLeibo,Jia K,Wang Xiaoyun, et al.Improved meet-in-the-middle attacks on AES-192 and PEINCE [EB/OL]. http:/eprint. iacr.org/2013/573. pdf.   
[14]Daemen J,Rijmen V.The design of Rijndael: AES-the advanced encryption standard [M].Berlin: Springer,2002.   
[15] Gilbert H,Minier M.Acollision attack on7 rounds of Rijndael [C]//Proc of the 3rd AES Candidate Conference.Berlin: Springer,20oo:230-241.   
[16]Demirci H, Selcuk AA.A meet-in-the-middle attack on 8-round AES [C]// Proc of Fast Software Encryption.Berlin: Springer, 20o8:116-126.   
[17]Dunkelman O,Keller N, ShamirA. Improved single-key attacks on 8-round AES-192 and AES-256 [C]//Proc of Advances in Cryptology-ASIACRYPT 2010.Berlin: Springer, 2010:158-176.   
[18]LiLeibo, Jia K,Wang Xiaoyun.Improved single-key attacks on 9-round AES-192//256 [C]//Pro ofFast Software Encryption.Berlin: Springer,2015: 127-146.   
[19] Guo Jian,Peyprin T,Poschmann A,et al. The LED block cipher [C]//Proc ofCryptographic Hardware and Embedded systems.Berlin: Springer,2011: 326-341.   
[20] Li Leibo,Jia K,Wang Xiaoyun,et al.Meet-in-the-middle technique for truncated differential and its applications to CLEFIAand Camellia[C]//Pro ofFast Software Encryption.Berlin: Springer, 2O15: 48-70.   
[21]汪艳凤，吴文玲.分组密码 TWINE的中间相遇攻击[J].软件学报, 2015,26(10):2684-2695.   
[22]郑雅菲，吴文玲.LBlock 算法的改进中间相遇攻击[J].计算机学报， 2017,40(5):1080-1091.