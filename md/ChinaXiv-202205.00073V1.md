# 基于国密算法SM2、SM3、SM4的高速混合加密系统硬件设计

李建立，莫燕南，粟涛，陈弟虎(中山大学 电子与信息工程学院，广州 510006)

摘要：随着电子信息技术的快速发展，数据的安全性问题日益严峻，传统单一制密码算法在安全性与运算速率上已不能满足要求。为了解决大数据时代下所提出的加密需求，提出了一种基于国密算法 SM2、SM3、SM4的高速混合加密系统的硬件设计方案，并针对 SM2和SM4算法的底层硬件结构进行优化：对 SM2算法采用Karatsuba-Ofman模乘器与点运算并行方案进行优化；对 SM4算法提出了一种基于复合域 S盒的二次流水全展开硬件架构。实验结果表明，该系统所实现的各算法电路均具有较高性能：SM2的点乘时间缩短至 $6 8 . 3 7 ~ \mu \mathrm { s }$ ；SM3 的杂凑值生成仅需$0 . 7 1 ~ \mu \mathrm { s }$ ；SM4 吞吐率最高达 53.76Gbit/s。相比同等安全性的 SM2 算法，该混合系统在加密时间上减小了 $2 6 . 6 7 \%$ 具有实用价值。与相关工作进行对比分析，可证明该方案在安全性和加解密性能上均有一定优势。

关键词：SM2公钥密码算法；SM4分组加密算法；硬件设计；混合加密中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0072

Hardware design of high-speed hybrid encryption system based on SM2, SM3 and SM4 algorithm

Li Jianli, Mo Yannan, Su Tao†, Chen Dihu (SchoolofElectronics& Information Technology,Sun Yat-Sen University,Guangzhou 51ooo6,China)

Abstract:With therapid developmentof electronic information technology,the securityof data hasbecome increasingly serious.The traditionalsinglecipheralgorithmcannotmeet therequirements any more.Inorderto solve these problems,this paper proposed a hardware design scheme of high-speed hybrid encryption system based on SM2,SM3,SM4,in which the hardware structure of SM2and SM4 algorithms is optimized.Besides,this paper optimized the SM2 algorithm with Karatsuba-Ofman modular multiplierand paralel with point operation.For SM4algorithm，this paper designed a subpipelining hardwarearchitecturebasedoncomposite fieldS-box soas to improve itsthroughout.Theexperimentalresults showedthatallthe algorithm circuitsimplemented bythe system have high performance:the point multiplication timeof SM2 was $6 8 . 3 7 ~ \mu \mathrm { s }$ ；the hash generation of SM3 only took $0 . 7 1 ~ \mu \mathrm { s } ;$ the throughput of SM4 was up to $5 3 . 7 6 \mathrm { G b i t / s }$ . Compared with the SM2 algorithm with the same security,this hybrid system had $2 6 . 6 7 \%$ less encryption time.By comparing and analyzing withrelated work,itcanbeprovedthat hisscheme hascertainadvantages insecurityandencryptionanddecryption performance.

Key words:SM2 algorithm; SM4 algorithm; hardware design; hybrid encryption

# 0 引言

近年来，随着计算机技术的快速发展以及大数据、云计算、物联网等技术产业的横空出世，人们在生活与生产中越来越离不开各种信息数据的传递与交互。信息技术在推动经济与社会发展的同时，也面临着巨大的安全隐患：网络攻击、信息泄露、隐私数据被盗等事件频发，信息安全问题日益加剧。另外，各类侧信道密码攻击技术的发展也使得各种单一加密算法面临着严峻的安全性挑战。与此同时，5G技术的日益成熟让人们步入了高带宽时代，也对数据的加密速度提出了更高的要求。在即时通信、车联网应用、远程医疗等对延时要求较高的场景下，加密系统的数据处理速度变得十分关键。因此，在大数据时代下，研究如何在高速传输的情况下保障数据信息安全至关重要。

混合加密技术是结合了多种加密体制和算法的一种新型加密技术，可以根据实际需求选择不同的加密体制进行加密方案的构建。目前，许多国内外学者对混合加密体制进行了大量的研究与分析。Mostafaa等人[1]提出了一种基于AES和ECC的轻量级混合加密硬件系统，并通过优化AES算法使得整体方案更加适合硬件资源有限的场景。V.Shende等人[2]则结合了AES和RSA两种算法的优点提出了一种混合加密方案，提高了系统的安全性。在国密算法方面，文献[3,4]分别选择了SM4-ECC和SM4-SM2的算法组合构建其加密方案，并从软件层面证明所提出的混合加密体制在安全性与扩散性系数上均高于单一制算法。文献[5]则通过研究SM2、SM3与SM4算法在变电站局域网中的应用情况，设计出一种基于国密算法的云存储混合加密方案。X.Zheng 等人[利用软硬件协同设计的方法，提出了同样基于SM2、SM3和SM4的加解密和数字签名方案，与相关工作相比其处理速度提高了 $10 \%$ 以上。总体而言，混合加密体制不仅提高了算法的安全性，同时也能兼顾加解密的高效性与密钥管理的便利性，优于传统单一制加密算法。

国密算法SM2和SM4是目前国内较为主流国产密码算法，在安全性研究与硬件实现上已有大量的研究成果。文献[7]基于Montgomery 模乘算法，设计了一种高速双域SM2模乘器，并提出了一种新型的Wallace树乘法单元，节省了大量资源。文献[8]提出了一种基于改进蒙哥马利点乘算法的并行点运算架构，通过坐标压缩以减少模乘步骤。文献[9]针对低端FPGA芯片，从算法和硬件实现两方面优化了SM2的模乘和模逆运算，提高了硬件资源的复用率，实现了面积和速度的平衡。而在SM4算法硬件架构的研究上，Gao[10]和Wang $\mathrm { H } ^ { [ 1 1 ] }$ 均采用了32轮轮间流水全展开型架构，降低了每一组数据加解密的平均时间，提供了极高的吞吐率。文献[12]提出了一种轮密钥扩展与加解密模块硬件复用的架构，其占用的资源仅为传统设计的 $5 5 \%$ 。文献[13]和 $\mathrm { F u H }$ 等人[14]则在轮间流水全展开的基础上对轮函数内部进行了二次流水切分，减少了电路的关键路径。

从文献分析与研究结果看，目前在混合加密方面国外的研究重点偏重于AES、RSA以及ECC这类国际算法，而国内对国密算法的混合加密研究关注点主要集中在算法安全性方面，对混合加密算法的硬件优化和性能提升上的研究比较欠缺。此外，在国密算法SM2与SM4的硬件实现研究上也仍存在一定的优化提升空间。

基于上述现状问题的分析，本文结合三种国密算法各自的优势，提出了一种基于国密算法SM2、SM3、SM4的混合加密硬件系统设计，在提高了加密系统安全性的同时可完成大量信息数据的高速加解密运算。同时，还针对SM2与SM4算法的结构对其硬件架构进行了优化设计，最终设计出一个集运算速率、硬件资源利用率以及数据安全性于一体的高速混合加密硬件系统，以解决信息化建设中对应用数据提出的高速率、高吞吐率加解密传输需求。

# 1 算法原理与混合加密系统设计原理

# 1.1SM2 算法原理

SM2椭圆曲线密码算法是我国公钥密码算法标准，于2010年12月首次公开。相关研究表明，SM2算法的安全性达到了公钥密码算法的最高安全级别[15]。

# 1.1.1 SM2曲线参数选择

SM2算法具有与ECC算法相同的数学概念基础，是一种基于求解椭圆曲线离散对数问题的加密算法。椭圆曲线是一种特殊的曲线，它实际上是Weierstrass方程所构成的平面光滑曲线，定义在伪梅森素数域GF(p)上的SM2椭圆曲线表达式为

$$
E : y ^ { 2 } = x ^ { 3 } + a x + b
$$

其中， $a , b \in \operatorname { G F } ( { \mathfrak { p } } )$ ，且 $4 a ^ { 3 } + 2 7 b ^ { 2 } \neq 0 { \bmod { p } }$ 。在国家密码标准中，推荐的定义在256位素数域上的SM2椭圆曲线系统参数为(所有值均以16 进制表示)：

素数 $p =$ FFFFFFFEFFFFFFFFFFFFFFFFFFFFFFFF

FFFFFFFFOOOOOOOOFFFFFFFFFFFFFFFF 系数 $a =$ FFFFFFFEFFFFFFFFFFFFFFFFFFFFFFFF

FFFFFFFFOOOOOOOOFFFFFFFFFFFFFFFC 系数 $b = 2 8$ E9FA9E9D9F5E344D5A9E4BCF6509A7

F39789F515AB8F92DDBCBD414D940E93

# 1.1.2 SM2 算法层次结构

SM2算法在结构上具有明显的层次性特点，其自顶向下可以划分为四个层次，如图1所示。顶层为SM2应用层，包括数字签名、密钥交换和公钥加密，主要通过调用点乘计算模块来实现不同的加密功能。群运算层为点乘模块，是SM2的核心运算，通过调用点加与倍点实现。点运算层分为点加和倍点两个模块，分别实现椭圆曲线上两个基础计算功能。底层则是最基本的模运算单元，包括模加、模减、模乘以及模逆运算，分别实现有限域上的各种模运算。本文对于SM2算法的硬件加速研究主要集中在点运算层与模运算层，通过并行化点运算以及优化模乘运算实现高效运算，从而提高SM2整体性能。

![](images/09b7f90be1f84d1b1050776e04df4a76246bd17b809a195166c3d29ae38e235d.jpg)  
图1 SM2 算法层次结构Fig.1 Hierarchy of SM2

# 1.2SM3 算法原理

SM3算法是一种分组迭代的杂凑算法，可以将任意长度的输入转为恒为256bit的摘要值输出，由国家密码管理局于2010年12月17日发布。SM3算法主要分为填充分组以及迭代压缩两个步骤，其计算流程如图2所示。

![](images/bb009879594d36df8f465d3fd912632e27871e6c5c871ab1e9d9c2fc6b919ad6.jpg)  
图2SM3 算法计算流程  
Fig.2Calculation process of SM3

填充分组：假设输入的长度为 $l$ 比特。首先将比特“1”添加到消息的末尾，再添加 $k$ 个 ${ } ^ { \mathfrak { s } } 0 ^ { \mathfrak { s } }$ ， $k$ 为满足 $l + 1 + k \equiv 4 4 8$ mod512的最小非负整数。然后再添加一个长度 $l$ 二进制表示的比特串。填充后的比特长度为512的倍数，并按512bit一组分组。

迭代压缩：对分组后的消息按下列方式进行迭代计算：

$$
V ^ { ( i + 1 ) } = C F ( V ^ { ( i ) } , B ^ { ( i ) } ) , i = 0 , 1 , 2 , . . . , n - 1
$$

其中， $n { = } ( l { + } k { + } 6 5 ) / 5 1 2$ ； $C F$ 是压缩函数， $V ( 0 )$ 为256bit初始值IV， $B ^ { ( \mathrm { i } ) }$ 是消息分组， $V ^ { ( \mathrm { n } ) }$ 是最后的杂凑值结果。

# 1.3 SM4算法原理

SM4分组密码算法是我国密码管理局于2006年公布的国内第一个商用密码算法，对于我国密码学研究的发展起了极大的推动作用[16]。SM4 算法是一种分组算法，分组长度和密钥长度均为128bit。SM4内部的加解密运算和密钥扩展运算都是32轮的非线性迭代结构，而非线性变换里的基本运算单元为S盒。其主要运算结构以字 $( Z _ { 2 } ^ { 3 2 } )$ 为单位，一次运算为一轮变换。定义 $\oplus$ 为32bit异或运算， $< < < i$ 为32bit循环左移 $i$ 位；加密密钥以 $M K$ 表示；轮密钥以 $r k _ { \mathrm { i } }$ 表示，系统参数以 $F K = ( F K _ { 0 } , F K _ { 1 } , F K _ { 2 } , F K _ { 3 } )$ 表示，固定参数以$( C K _ { 0 } , C K _ { 1 , \cdot \cdot \cdot , C K _ { 3 1 } } )$ 表示。

# 1.3.1加解密算法

加密算法过程如算法1所示。

算法1 SM4 加密算法输入： $( X _ { 0 } , X _ { 1 } , X _ { 2 } , X _ { 3 } ) \in ( Z _ { 2 } ^ { 3 2 } ) ^ { 4 }$ ， $r k _ { 0 } , r k _ { 1 } , . . . , r k _ { 3 1 } \in Z _ { 2 } { } ^ { 3 2 }$ 为轮密钥。输出： $( Y _ { 0 } , Y _ { 1 } , Y _ { 2 } , Y _ { 3 } ) \in ( Z _ { 2 } ^ { 3 2 } ) ^ { 4 }$ 。1. $\scriptstyle { i = \theta , 1 , 2 , \ldots , 3 1 }$ $X _ { i + 4 } = F ( X _ { i } , X _ { i + 1 } , X _ { i + 2 } , X _ { i + 3 } , r k _ { i } ) = X _ { i } \oplus T ( X _ { i } \oplus X _ { i + 1 } \oplus$ $X _ { i + 2 } \oplus X _ { i + 3 } \oplus r k _ { i } )$ 2． $( Y _ { 0 } , Y _ { 1 } , Y _ { 2 } , Y _ { 3 } ) = ( X _ { 3 5 } , X _ { 3 4 } , X _ { 3 3 } , X _ { 3 2 } )$ 其中， $F$ 为轮变换函数； $T$ 为合成置换，包含了非线性变换 $\boldsymbol { \tau }$ 和线性变换 $L$ ，即 $\scriptstyle { T ( . ) = L ( \tau ( . ) ) }$ ； $\boldsymbol { \tau }$ 内部为四个并行 S 盒， $L$ 为线性变换。合成置换 $T$ 过程如算法2所示。

算法2合成置换 $T$ 算法输入： $A = ( a _ { 0 } , a _ { 1 } , a _ { 2 } , a _ { 3 } ) \in ( Z _ { 2 } ^ { 8 } ) ^ { 4 }$ 。输出： $C = ( c _ { 0 } , c _ { 1 } , c _ { 2 } , c _ { 3 } ) \in ( Z _ { 2 } ^ { \mathrm { ~ 8 ~ } } ) ^ { 4 }$ 。1. $B = ( b _ { 0 } , b _ { 1 } , b _ { 2 } , b _ { 3 } ) = \tau ( A ) = ( S b o x ( a _ { 0 } ) , S b o x ( a _ { 1 } ) , S b o x ( a _ { 2 } ) , S b o x ( a _ { 3 } ) )$ 2． $C = L ( B ) = B \oplus ( B < < 2 ) \oplus ( B < < < 1 0 ) \oplus ( B < < 1 8 ) \oplus ( B < < 2 4 )$ 解密算法与加密算法的运算流程相同，只是轮密钥的使用次序与加密相反。

# 1.3.2密钥扩展算法

密钥扩展运算过程如算法3所示。

算法3密钥扩展算法输入： $M K = ( M K _ { 0 } , M K _ { 1 } , M K _ { 2 } , M K _ { 3 } ) , M K _ { i } \in Z _ { 2 } { } ^ { 3 2 } ( i = 0 , 1 , 2 , 3 )$ 输出： ${ r k _ { i } } \in { Z _ { 2 } } ^ { 3 2 } ( i = 0 , 1 , 2 , . . . , 3 1 )$ （204号1. $( K _ { 0 } , K _ { 1 } , K _ { 2 } , K _ { 3 } ) = ( F K _ { 0 } \oplus M K _ { 0 } , F K _ { 1 } \oplus M K _ { 1 } , F K _ { 2 } \oplus M K _ { 2 } , \ F K _ { 3 } \oplus M K _ { 3 } )$ 2. $\scriptstyle { i = \theta , 1 , 2 , \ldots , 3 1 }$ .$r k _ { i } = K _ { i + 4 } = K _ { i } \oplus T ^ { \prime } ( K _ { i + 1 } \oplus K _ { i + 2 } \oplus K _ { i + 3 } \oplus C K _ { i } )$ 其中， $T ^ { : }$ 中的线性变换为 $L ^ { \prime } \ ^ { \prime } : \ ( B { < } { < } { < } { 1 3 } ) \oplus ( B { < } { < } { < } { < } { 2 3 } )$ ，其余部分与加解密运算中的 $T$ 变换相同。

# 1.4基于SM2、SM3、SM4算法的高速混合加密系统

SM2非对称算法得益于椭圆曲线密码体制，其公钥可对外公开，可实现密钥的便捷管理，信息传输的安全性也较高。但是由于涉及大位宽的复杂模运算，SM2算法的加解密速度普遍较慢，仅适用于加密小块数据。SM3 算法属于单向加密的密码体制，对于明文信息只能计算出杂凑值，而无法从杂凑值反向推算出对应明文数据。SM4对称算法虽然结构简单，复杂度低、加解密速度快，但是其需要额外的安全信道分发密钥，密钥管理复杂且安全性难以保证。

本文在研究了SM2、SM3以及SM4三种算法各自的特点后，提出了一种兼顾加密安全性、高速性以及密钥管理便利性的混合加密系统，其基本原理如下：基于大数据时代高速率加解密传输的需求，采用经本文硬件优化后的SM4算法快速加解密海量的应用数据；利用SM2算法安全性高、密钥管理简单的特点，采用同样经优化后的SM2算法对SM4密钥进行加解密；另外，本系统还采用SM3杂凑算法对加解密前后的明文进行杂凑值对比验证，防止信息在传输过程中被窜改。由于混合使用了三种不同体制的加密算法，本文提出的混合加密系统在传输密钥时不再需要额外的安全信道，同时还可以实现大量数据的高速加解密与验证运算，其加解密流程如图3所示。

![](images/d07667066bf34015ff02c382725ac0c77b989f132e897e098d5903230a64e4b3.jpg)  
图3混合加密系统加解密流程

Fig.3Encryption and decryption process of hybrid encryption system假设需要加密传输的数据为信息明文P，且发送方和接收方之间的传输通道是不安全的，则具体的加解密传输过程如下：

a）首先接收方使用SM2 算法生成配对的公钥和私钥，并在加密计算前先将公钥发送给发送方；

b）发送方接收到SM2公钥后，使用SM2算法加密SM4密钥生成密钥密文，同时使用 SM4 算法加密信息明文P生成信息密文C，另外再使用SM3算法计算P中首尾两组数据块的摘要值。待三种算法均计算完成后，将三组数据打包，通过传输通道一同发送给接收方；

c）接收方在收到数据后，首先利用SM2私钥，通过SM2算法将SM4密钥解密出来。然后利用SM4密钥，通过SM4算法解密所收到的信息密文C，得到尚未验证的信息明文P。接着使用SM3算法计算得到信息明文P的摘要值B，并与所收到的摘要值A进行对比验证：若一致，则代表数据在传输过程中没有被窜改，可输出所解密的信息明文P，完成解密；若两组摘要值不一致，则说明数据在传输中已被窜改，解密出来的数据存在安全风险，系统发出警告并退出解密。

从理论上分析本文提出的混合加密系统可以发现：在加密过程中最耗时的步骤为海量数据明文的SM4加密计算；而因为解密过程是三种算法串行执行的，所以决定解密速度的步骤主要为对密钥密文的SM2解密计算，以及对大量信息密文的SM4解密计算。基于以上分析可知，若想提高混合加密系统的整体性能，需考虑提升SM2和SM4算法的计算速率和硬件效率。因此，本文的研究重点将集中在对SM2和 SM4算法的硬件优化和性能提升上，采用并行化与流水线技术对两个算法的硬件架构进行优化设计，解决制约加解密速度提升的瓶颈，保证混合加密系统能够满足高性能密码运算的需求。

# 2 SM2算法的硬件加速设计

椭圆曲线的点乘运算是SM2算法的核心运算，其运行速度决定了SM2算法的速度。点乘运算一般涉及大量大数运算，而这些运算操作用软件实现会非常复杂且效率低下，因此通常采用硬件优化的实现方式以提高SM2算法的性能。本文在综合考虑性能与资源的情况下，采用自底向上的思路，对SM2算法的硬件实现进行优化设计。首先从底层的模乘运算出发，对模乘器的硬件实现采用Karatsuba-Ofman算法进行优化设计，降低计算复杂度与硬件资源的消耗。其次，本文还分析研究了不同架构下点加和倍点运算的硬件性能提升与资源消耗情况，在资源合理运用的情况下实现了SM2算法的快速点乘运算。

# 2.1模乘运算优化设计

SM2算法在进行点乘运算的过程中会频繁地调用乘法器进行大数模乘运算，故实现模乘的快速运算是提高SM2算法性能的一个关键。常见的模乘方法主要有Barrett算法、Montgomery 算法、大数乘法搭配快速模约减等[l7]。Barrett算法除了乘法以外还采用了除法操作，对于硬件实现来说该算法在运算时间与资源消耗上都非常低效。而Montgomery 算法虽然通过移位和加法操作代替了除法操作，但是其运算结果并非模乘的最后结果，仍需要进一步的转换运算，更适合用于多次乘法的模幂运算，对于单次模乘计算并无优势。因此，本文选择采用大数乘法搭配快速模约减的方式实现模乘运算。

在大数乘法方面，运用Karatsuba-Ofman算法的分治思想，将256位的乘法拆分成三次128位乘法，并以基于129位乘法器的方式完成大数乘法运算。相比于直接使用256位乘法器[18],Karatsuba-Ofman算法虽然需要更多的时钟周期来完成，但是减少了 $2 5 \%$ 的计算量，硬件资源消耗更小，提高了运算效率与资源利用率，基于该算法实现的256位乘法如算法4所示。

算法4 256位Karatsuba-Ofman算法输入：256位整数A，B，且有 $A = a _ { \cal H } \times 2 ^ { 1 2 8 } + a _ { \cal L }$ ， $B = b _ { { \scriptscriptstyle H } } \times 2 ^ { 1 2 8 } + b _ { { \scriptscriptstyle L } }$ 。输出： $\scriptstyle { C = A \times B }$ ， $\mathsf { c }$ 为512位整数。1. $\mathsf { \Pi } _ { L } ^ { \mathsf { D } } = a _ { L } \times b _ { L } \ , \quad a _ { S } = a _ { H } + a _ { L } \ , \quad b _ { S } = b _ { H } + b _ { L }$ 2. $P _ { H } = a _ { H } \times b _ { H } ~ , ~ C _ { 1 } = P _ { H } + P _ { L } ~ , ~ C _ { 2 } = \{ P _ { H } , P _ { L } \} - C _ { 1 } \times 2 ^ { 1 2 8 }$ 3.3． $P _ { S } = a _ { S } \times b _ { S }$ ， $C = C _ { 2 } + P _ { S } \times 2 ^ { 1 2 8 }$ （204号

该算法中包含了三次128位的加/减法、两次512位的加/减法、两次128位的乘法以及一次129位的乘法。同时，算法中2的幂次运算在硬件中可以通过移位操作实现，以节省硬件消耗与计算时间。根据算法4，提出如图4所示的256位Karatsuba-Ofman乘法硬件设计：

![](images/5cdbeebf3d2f6c3b69537d5b77c67a7fe4f7f31170e1b43bb20254b86e811b74.jpg)  
图4256位Karatsuba-Ofman 乘法硬件设计

该硬件设计采用一个129位的乘法器、两个并行的512位加法器以及移位寄存器实现，同时对加法运算进行二级并行处理，将256位的乘法运算降低至三个时钟周期。其中乘法器负责128位与129位的乘法运算，加法器负责128位与512位的加减法运算，通过是否取补码实现。该设计在缩短运算周期的同时也实现了较低的硬件开销，资源利用率达到了 $8 8 . 8 \%$ 。

在取模方面，由于本文选取的素数 $p$ 为伪梅森素数。根据其性质，该素数可表示为少量的2的幂的和或差，本文选取的素数则可改写为 $p _ { 2 5 6 } = 2 ^ { 2 5 6 } - 2 ^ { 2 2 4 } - 2 ^ { 9 6 } + 2 ^ { 6 4 } - 1$ 。根据该表达式,可以采用快速模约减算法快速地对512位的乘法结果取模。参考文献[19]中的快速模约减算法，完成整体模乘器的硬件电路设计如图5所示。快速模约减算法通过简单的截位拼接与加减法即可完成取模运算，省去了常规取模中繁琐的乘法与除法运算，有利于缩短整体的运算时间、节省硬件的资源消耗。

![](images/efbdb37b0421bfd295778fdfbd7726e54b520066a4354c23da4b43c5d4572c46.jpg)  
Fig.4Hardware design forKaratsuba-Ofman multiplication in 256 bits   
图5模乘器硬件结构  
Fig.5Hardware structure of modular multiplication

该模乘器采用了Karatsuba-Ofman 算法与快速模约减算法相匹配的方式，仅利用低位宽加法、乘法以及移位等简单的操作，最终在四个周期内完成了复杂的256位模乘运算。

# 2.2点运算并行优化设计

点运算层是实现点乘运算的基础，因此对点加和倍点运算进行优化加速也非常重要。在Jacobian投影-仿射混合坐标下实现点加、在Jacobian投影坐标下实现倍点的组合方式可以避免耗时的模逆运算，同时该组合方式也是众多坐标系中运算复杂度最低的选择。Jacobian投影-仿射混合坐标下点加运算与Jacobian投影坐标下倍点运算的定义分别如算法6、7所示[19]：

算法6Jacobian投影-仿射混合坐标下点加运算输入： $P { = } ( X _ { 1 } , Y _ { 1 } , Z _ { 1 } )$ ， $\mathscr { Q } = ( X _ { 2 } , Y _ { 2 } , 1 )$ ， $P \neq Q$ ， $Z _ { \mathrm { 1 } } \neq 0$ 。输出： $P + Q = ( X _ { 3 } , Y _ { 3 } , Z _ { 3 } )$ 。$X _ { 3 } = ( Y _ { 2 } Z _ { 1 } { } ^ { 3 } - Y _ { 1 } ) ^ { 2 } - ( X _ { 2 } Z _ { 1 } { } ^ { 2 } - X _ { 1 } ) ^ { 2 } ( X _ { 2 } Z _ { 1 } { } ^ { 2 } + X _ { 1 } )$ $Y _ { 3 } = ( Y _ { 2 } Z _ { 1 } ^ { 3 } - Y _ { 1 } ) ( X _ { 1 } ( X _ { 2 } Z _ { 1 } ^ { 2 } - X _ { 1 } ) ^ { 2 } - X _ { 3 } ) - Y _ { 1 } ( X _ { 2 } Z _ { 1 } ^ { 2 } - X _ { 1 } ) ^ { 3 }$ $Z _ { 3 } = ( X _ { 2 } Z _ { 1 } ^ { 2 } - X _ { 1 } ) Z _ { 1 }$ 算法7Jacobian投影坐标下倍点运算输入： $P = ( X _ { 1 } , Y _ { 1 } , Z _ { 1 } )$ ， $Z _ { 1 } \neq 0$ ， $a = p - 3$ 。输出： $2 P = ( X _ { 3 } , Y _ { 3 } , Z _ { 3 } )$ 。$X _ { 3 } = [ 3 ( X _ { 1 } + Z _ { 1 } ^ { \ 2 } ) ( X _ { 1 } - Z _ { 1 } ^ { \ 2 } ) ] ^ { 2 } - 8 X _ { 1 } Y _ { 1 } ^ { 2 }$ $Y _ { 3 } = 3 ( X _ { 1 } + Z _ { 1 } ^ { 2 } ) ( X _ { 1 } - Z _ { 1 } ^ { 2 } ) ( 4 X _ { 1 } Y _ { 1 } ^ { 2 } - X _ { 3 } ) - 8 Y _ { 1 } ^ { 4 }$ $Z _ { 3 } = 2 Y _ { 1 } Z _ { 1 }$ 对于点加算法，通过分析算法中各步骤数据间的依赖关  
系，将不存在相关性的运算进行并行加速，从算法实现层面  
降低点加运算时间。对算法步骤进行拆分，根据运算相关性  
提出了点加计算的二级并行加速方案，如算法8所示。算法8Jacobian投影-仿射混合坐标下二级并行点加运算输入： $P { = } ( X _ { 1 } , Y _ { 1 } , Z _ { 1 } )$ ， $\mathscr { Q } = ( X _ { 2 } , Y _ { 2 } , 1 )$ ， $P \neq Q$ ， $Z _ { \mathrm { 1 } } \neq 0$ 。输出： $P + Q = ( X _ { 3 } , Y _ { 3 } , Z _ { 3 } )$ 。模乘器0模乘器1模加减器0模加减器11 $A { = } Z _ { 1 } \times Z _ { 1 }$ $\begin{array} { r } { B = Y _ { 2 } \times Z _ { 1 } } \end{array}$ NA NA2 $\begin{array} { r l } { 4 \times B } & { { } \ C = A \times X _ { 2 } \quad A = A B - Y _ { 1 } \quad B = C - X _ { 1 } } \end{array}$ 3 $\begin{array} { r } { Z _ { 3 } = B { \times } Z _ { 1 } \quad D = B { \times } B \quad E = C + X _ { 1 } } \end{array}$ NA4 $1 A \times A D \times E X _ { 3 } = A A - D E$ NA5 $D \times X _ { 1 }$ $\begin{array} { r l } { X _ { 1 } } & { { } B = D \times B \quad C = D X _ { 1 } - X _ { 3 } } \end{array}$ NA6 $A { \times } C B { \times } Y _ { 1 } Y _ { 3 } = A C - B Y _ { 1 }$ NA

由算法6可知，点加运算需要进行9次的模乘计算与3次的模平方运算，若采用传统的循环串行计算方式则至少需要十二轮运算来完成。而本文提出的二级并行方案则通过采用两个模乘器的方法进行加速，对乘法运算采用并行的计算方式处理，从而将运算迭代缩短至六轮。根据所提出的点加二级并行方案，点加模块在硬件实现上需要实例化两个模乘器、三个模加减器，并通过共享的寄存器 $( A , B , C , D , E )$ 存储与调用中间的计算结果。在研究了串行、二级并行以及三级并行[20]三种方案每轮迭代中最长的运算路径后，可得出如表1所示的运算时间对比表：

表1不同并行度点加方案的运算时间对比

Tab.1Comparison of operation time for point addition   

<html><body><table><tr><td colspan="3">schemeswithdifferentparallelism</td></tr><tr><td>并行度</td><td>运算周期</td><td>加速比</td></tr><tr><td>串行</td><td>11M×5cycles+2A/S×lcycle+lcycle=58cycles</td><td>NA</td></tr><tr><td>二级并行</td><td>6M×5cycles+4A/S×lcycle+lcycle=35cycles</td><td>1.657</td></tr><tr><td>三级并行</td><td>5M×5cycles+5A/S×lcycle+lcycle=3lcycles</td><td>1.871</td></tr></table></body></html>

其中 $M$ 代表模乘， $_ { A / S }$ 代表模加与模减运算。由于在模乘运算以及每轮迭代后，共享寄存器需要额外一个时钟周期进行数据的暂存与传输，因此在点运算中模乘实际需要5个时钟周期。

通过对比可知，二级并行方案和文献[20]中的三级并行方案与传统串行方案相比在速度上均有极大的提升。而三级并行方案[20]虽然在运算时间上是三种方案中最快的，但是该方案需要例化三套模乘器与模加减器，其在硬件消耗上也是三者中最高。因此，本文在综合考虑性能与硬件资源的因素后，最终决定采用二级并行的方式实现点加运算。

同理，对于倍点算法本文采用相同的分析方式提出了如算法9所示的二级并行加速方案。

算法9Jacobian 投影坐标下二级并行倍点运算输入： $P = ( X _ { 1 } , Y _ { 1 } , Z _ { 1 } )$ ， $Z _ { \scriptscriptstyle 1 } \neq 0$ ， $a = p - 3$ .

输出： $2 P = ( X _ { 3 } , Y _ { 3 } , Z _ { 3 } )$

模乘器0模乘器1模加减器0模加减器1模加减器2

1 $A = Y _ { 1 } \times Z _ { 1 } \quad Z _ { 1 } \times Z _ { 1 } \quad B = Y _ { 1 } + Y _ { 1 } \quad C = X _ { 1 } + Z _ { 1 } ^ { 2 } \quad C = X _ { 1 } - Z _ { 1 } ^ { 2 }$ 2 $A { = } C { \times } D$ $\begin{array} { r l } { \times D } & { { } B = B \times B \quad Z _ { 3 } = A + A \quad C = B + B \quad | } \end{array}$ NA $\begin{array} { r } { \begin{array} { l l l l } { { 3 } } & { C = C \times X _ { 1 } } & { D = B \times X _ { 1 } } & { A = A + A } & { A = A + 2 A } \end{array} } \end{array}$ NA $A \times A \quad B \times Y _ { 1 } \quad B = B Y _ { 1 } + B Y _ { 1 } \quad X _ { 3 } = A A - C \quad C = D - X _ { 3 }$ 5 $A { \times } C B { \times } Y _ { 1 } Y _ { 3 } = A C - B Y _ { 1 }$ NA NA

倍点运算需要进行6次的模乘计算与4次的模平方运算，根据本文提出的二级并行方案，可将倍点运算的迭代减小至五轮。在硬件实现上，倍点模块同样需要实例化两个模乘器与三个模加减器，以及四个共享寄存器。倍点运算三种方案的运算时间对比如表2所示。

# 表2不同并行度倍点方案的运算时间对比

Tab.2Comparison of operation time for double point   
schemeswithdifferentparallelism   

<html><body><table><tr><td>并行度</td><td>运算周期</td><td>加速比</td></tr><tr><td>串行</td><td>9M×5cycles+1A/Sxlcycle+lcycle=47cycles</td><td>NA</td></tr><tr><td>二级并行</td><td>5M5cycles+5A/S1cycle+lcycle=3lcycles</td><td>1.516</td></tr><tr><td>三级并行</td><td>4M×5cycles+6A/S×lcycle+lcycle=27cycles</td><td>1.741</td></tr></table></body></html>

可以看到，二级并行方案在运算周期上比串行方案有一定的提升。为了提高硬件利用率，本文在倍点运算的实现同样选择了兼顾性能与资源消耗的二级并行方案。

# 2.3点乘运算的实现

点乘运算的实质是对椭圆曲线坐标进行多次点加与倍点计算的结果，故在电路实现上需要频繁调度点加与倍点模块。由于本文采用不同的坐标系实现点加和倍点运算以减少耗时的模逆运算次数，因此还需要相应的坐标转换模块，从而将最终的点乘结果转换至仿射坐标系下。图6为点乘运算的组成模块。

![](images/9194b4d1f377fad184275a61ad1976d3442987c60f8e1da27607db03a0e6f507.jpg)  
Fig.6Structure of point multiplication module

点乘模块通过循环调用256次两个点运算模块完成256位的点乘计算，并采取移位寄存器搭配多路选择器的方式来判断是否需要进行点加。其中倍点与点加模块均采用了二级并行的方案与Karatsuba-Ofman算法模乘器进行加速。

# 3 SM4算法的硬件加速设计

SM4算法的高速实现是提升大量数据加解密速度的关键，在硬件实现上对SM4算法进行优化加速同样重要。本文对S盒的硬件实现进行了研究，采用复合域求逆的方式来构造；同时，还在此基础上提出一种二次流水全展开硬件架构，并对轮函数模块进行硬件复用，以较小硬件开销实现了极高的吞吐量。

# 3.1基于复合域求逆S盒的实现

S盒是SM4实现中对性能影响最大的部分，其在很大程度上决定了整个SM4算法的硬件实现性能。目前S盒的构造方法主要分为查表式与代数式。传统的查表式S盒是一个包含256个数据的字节代换表，虽然硬件上可以采用寄存器或ROM的方式简单实现，但是面积开销较大，电路性能也难以提升。代数式S盒又分为有限域求逆和复合域求逆两种构造方式。而有限域上的求逆运算非常复杂，难以用硬件实现；复合域求逆的方式则在运算量和硬件消耗上均很小，适合用以硬件实现。

在2007年Liu等[2I提出了一种用式(3)所示的代数式构造S盒的方法，即S盒可以通过仿射变换和乘法求逆来实现：

$$
S ( x ) { } = I ( x \cdot A _ { 1 } + C _ { 1 } ) \cdot A _ { 2 } + C _ { 2 }
$$

其中， $x$ 是S盒的8位二进制输入； $\scriptstyle A _ { 1 }$ ， $\mathbf { \nabla } A _ { 2 }$ 为循环矩阵； $C _ { 1 }$ $C _ { 2 }$ 为行向量； $I ( x )$ 是GF(28)域上的乘法求逆运算。在复合域上进行乘法求逆，可以在很大程度上简化运算复杂度。利用复合域求GF(28)域上乘法逆元的运算过程如图7所示。

![](images/86d84ad50138618f4070ceee9dbc0a768a8722fedc333f9240c844c64e86f56c.jpg)  
图7复合域乘法求逆运算过程

其主要步骤如下：一、利用同构映射 $T _ { 1 }$ 和 $T _ { 2 }$ 将GF(28)域上的元素映射到复合域 $\mathrm { G F } ( ( 2 2 ) ^ { 2 } ) ^ { 2 } )$ ；二、在GF(2)域上用异或运算求出GF(22)的逆元；三、将GF(22)的逆元结果回代运算，用基于GF(22)的乘法运算求出 $\mathrm { G F } ( ( 2 2 ) ^ { 2 } )$ 逆元；四、将$\mathrm { G F } ( ( 2 2 ) ^ { 2 } )$ 逆元结果回代运算，用基于 $\mathrm { G F } ( ( 2 2 ) ^ { 2 } )$ 的乘法运算求出 $\mathrm { G F } ( ( 2 2 ) ^ { 2 } ) ^ { 2 } )$ 的逆元；五、利用逆同构映射 $T _ { 1 } { } ^ { - 1 }$ 和 $T _ { 2 } { } ^ { - 1 }$ 将求逆结果从 $\mathrm { G F } ( ( 2 2 ) ^ { 2 } ) ^ { 2 } )$ 映射回GF(28)域，最终得到GF(28)域的乘法逆元结果。

以 $\oplus$ 代表异或门，根据图7并参考文献[22]中关于复合域求逆的设计，对仿射变换和同构映射部分进行化简合并，设计出复合域求逆S盒的硬件结构如图8\~11所示。

8bit 8bit 8bit XAT GF-1（(24）2) XT-1·A

![](images/cbb107a06157ac0ac29d69ef149a47a8bc934209340e3d7e8668688d1f23f306.jpg)  
Fig.7The process of inverse transformation over composite field   
图8复合域S盒基本结构  
Fig.8Structure of S-box based on the inverse transformation over composite field   
图9GF(24)2)逆元电路

![](images/36055e0acde556f8677b24b4e587a3cceba60076298fd643538a741fe1cb1ac3.jpg)  
图6点乘模块组成结构  
Fig.9Hardware structure of inversion on GF((24) 2)   
图10GF(22)2)逆元电路  
Fig.10Hardware structure of inversion on GF((22) 2)

![](images/05a8451873cfea7a5c1ff266002952121c332ca41ff451b3af464538d1c67e49.jpg)  
Fig.11Hardware structure of inversion on GF(22)

可见，在最底层GF(22)子域上的求逆运算仅仅只用到了异或运算。另外，根据扩展式对系数乘方运算进行化简优化后，设计出各域上的乘法电路与系数乘方电路硬件电路结构分别如图12和13所示。

![](images/70277626e6ffac11408ff6bec945879d811d420224c85f4cd04481380dbb0264.jpg)  
图11GF(22)逆元电路

![](images/da23ffce26a4fdff0a19d5d380e84fad56229b5ffa1b119af3137950471c3ddb.jpg)  
Fig.12Hardware structure of multiplication on GF((24)2)and GF (22)   
图13GF((24)2)和GF((22)2)系数乘方电路

经优化后的S盒电路仅使用数量较少的异或门和与门即可实现256位数据的替换运算，相比于直接使用查找表的方式，该方案极大地降低了运算复杂度和硬件开销。同时，采用纯组合逻辑实现的S盒电路也为后续进行轮内流水优化提供了便利。在基于复合域求逆S盒的基础上，根据SM4算法的描述，完成了SM4单轮轮函数的硬件设计，并分析各电路模块的资源消耗情况和关键路径如表3所示。

表3SM4各电路模块的资源消耗与关键路径  
Tab.3 Gate counts and critical paths of functional blocks in SM   

<html><body><table><tr><td>电路模块</td><td>逻辑门数</td><td>关键路径</td></tr><tr><td>GF(24)）系数乘方电路</td><td>4 XOR</td><td>2 XOR</td></tr><tr><td>GF(22)乘法电路</td><td>3AND+4XOR</td><td>1AND+2XOR</td></tr><tr><td>GF(24)乘法电路</td><td>6AND+13XOR</td><td>1 AND+4XOR</td></tr><tr><td>GF(22)逆元电路</td><td>1 XOR</td><td>1 XOR</td></tr><tr><td>GF((22)²)逆元电路</td><td>9 AND+15 XOR</td><td>2 AND+7XOR</td></tr><tr><td>GF((24))逆元电路</td><td>27AND+60 XOR</td><td>4AND+17XOR</td></tr><tr><td>映射模块</td><td>30 XOR</td><td>7 XOR</td></tr><tr><td>逆映射模块</td><td>26 XOR</td><td>7 XOR</td></tr><tr><td>复合域S盒</td><td>27AND+116XOR</td><td>4AND+31XOR</td></tr><tr><td>SM4单轮轮函数</td><td>108AND+472XOR</td><td>4AND+36XOR</td></tr></table></body></html>

# 3.2SM4算法的流水线结构设计

SM4 算法的吞吐率计算公式如式4所示，其中 $B$ 代表处理的数据位宽，在这里固定为128位； $f$ 代表电路频率； $N$ 代表平均每组加解密数据的处理轮数。由此可见，要提高SM4算法的吞吐率一方面要对电路的关键路径进行优化，提升硬件整体频率 $f$ ，另一方面还要降低每组加解密数据的平均处理轮数 $N _ { \circ }$ （204号

$$
T h r o u g h p u t = \frac { B \times f } { N }
$$

根据SM4算法的定义可知，该算法是由32轮完全相同的轮函数组成，且在加解密过程中前后数据完全独立，因此可以采用流水线处理的结构来实现 SM4 分组密码算法的高

吞吐率计算。本文首先采用轮内流水的结构实现单轮轮函数以提高时钟频率 $f$ ，再采用轮间流水的结构完成整体SM4算法电路以降低平均处理轮数 $N$ ，从而实现高速运算。

# 3.2.1轮内流水处理结构

要想提高电路的时钟频率，就必须要降低每轮运算中的运算量，尤其是在轮函数运算较为复杂的时候，其关键路径限制了在硬件实现下的最大时钟频率。针对这种情况，可以采用轮内流水处理结构进行加速，通过将轮函数内的运算单元进行拆解后插入寄存器以建立流水线，进而构造轮内流水结构。

分析表3中SM4电路的关键路径，在轮函数电路中的不同位置插入寄存器，设计出如图14所示的四种轮内流水结构。轮内流水结构将每一轮的运算从内部切分，缩短了整体电路的关键路径，极大地降低了电路中每一拍的运算时间。

![](images/d02d3836935cd5e906736a0943372549622726bbbdbf2fcd8be00ff6988afb5c.jpg)  
图12GF((24)2)和GF(22)乘法电路  
图14SM4 轮内流水结构  
Fig.14 Subpipelined structure of the round function circuit in SM4 3.2.2轮间流水处理结构

一般而言，传统的SM4 算法采取循环迭代式的结构实现，即仅实例化一个轮函数电路，并通过不断重复调用此电路以实现32轮的运算。对于传统循环迭代式结构，其每组数据的加解密时间至少为 32个周期，下一组数据需要等待上一组数据循环计算 32 次后方可开始计算，实际吞吐率并不高。因此，该结构虽然能节省大量电路开销，但是其运算效率低下，不适合高性能加解密系统的设计。

而轮间流水处理结构则是指以轮函数作为基本运算单元，采取循环展开的方式，构造流水线，实现数据的流水处理。具体而言，轮间流水结构在进行电路设计时实例化32个轮函数电路，并在每一轮运算之间用寄存器隔开，每组数据无须等待，可以以流水的形式紧跟上组数据输入电路进行计算。轮间流水处理的优势在于，当流水线一旦构造完成，系统将在每个时钟周期完成一组密码运算，平均下来每组数据的加解密时间仅为一个周期，极大地提升了整体电路的吞吐率。

在采用图14所示的轮内流水结构的基础上，对SM4电路进行循环全展开，以轮间流水的方式实现SM4的整体电路设计，最终SM4算法的硬件电路架构如图15所示。

![](images/9603c2d501d641279e3d1b7c2dbd493cce52831351d1373a20bb4f660251b401.jpg)  
Fig.13Hardware structure of square on GF((24) 2)and GF((22)2)   
图15SM4 硬件电路架构  
Fig.15High speed hardware architecture for SM4

该电路采用了复合域求逆S盒、轮内流水处理以及32轮全展开轮间流水处理三种优化技术，为加解密电路带来了极大的性能提升。同时，本文还根据加解密模块和轮密钥扩展模块在算法结构上的相似性，在轮函数电路内对这两个模块进行了硬件上的复用合并，并通过多路选择器来对输入数据以及移位逻辑进行选择，进一步地提高硬件电路的利用率。

# 4 实验结果与性能对比

# 4.1实验环境

本文基于所述硬件架构，使用硬件描述语言Verilog-HDL实现了高速混合加密系统的整体硬件设计，并在硬件平台XilinxUltrascale+系列的ZCU102开发板上进行板级测试，验证设计正确性及分析工作性能。

# 4.2实验结果

本设计完成了一个高性能的混合加密系统，其系统框图如图16所示。该系统主要由SM2、SM3、SM4三种加密算法模块、状态机控制模块以及输入输出缓存器模块组成，可以采用三种加密算法进行高速防窜改混合加密运算。

图16高速混合加密系统框图  
![](images/24038a5ad7fb7b04c275cf7b8e2e4868d291defb36b48ee430ec66c0ef96f403.jpg)  
Fig.16Structure of the high speed hybrid encryption system

在系统中三个密码模块相互独立且工作频率各不相同，模块间数据交互以异步方式处理。表4为总系统以及各算法模块工作频率与资源消耗情况。

表4混合加密系统及各算法模块硬件实现结果

Tab.4Hardware Implementaion results of the hybrid encryption system and each algorithm module   

<html><body><table><tr><td colspan="3">SySten argo</td></tr><tr><td>算法模块</td><td>Fmax(MHz)</td><td>资源消耗</td></tr><tr><td>SM2</td><td>215</td><td>41067LUTs+ 13837Regs+320 DSPs</td></tr><tr><td>SM3</td><td>200</td><td>1513LUTs +1744 Regs</td></tr><tr><td>SM4</td><td>400</td><td>14264LUTs+13874Regs</td></tr><tr><td>混合加密系统</td><td>200</td><td>58313LUTs+36032 Regs +320 DSPs</td></tr></table></body></html>

由表4中可看出，各算法模块的最高频率与资源消耗各不相同。其中 SM2算法模块的面积开销最大，所需的LUT与DSP最多。而SM3模块由于采取了循环迭代的方式实现，极大地降低了电路资源消耗，电路开销最小。SM4算法模块在考虑硬件效率的情况下选择了轮间全展开加上轮内四级流水的架构实现，其平均每组数据加密时间降低至一个时钟周期，同时工作频率也提升至 $\boldsymbol { 4 0 0 } \mathrm { M H z }$ ，非常适合大量数据的

快速加解密运算。

此外，分别利用三种单一制算法加密大小为16K的明文数据，与本文的混合加密系统进行加密性能以及相关特性的对比，具体情况见表5。

Tab.5Comparison of performance and characteristics of different   

<html><body><table><tr><td colspan="4">encryptionalgorithms</td></tr><tr><td>加密算法</td><td>加密时间(μs)</td><td>双向加解密</td><td>额外安全信道</td></tr><tr><td>SM2</td><td>183.82</td><td>支持</td><td>不需要</td></tr><tr><td>SM3</td><td>24.70</td><td>不支持</td><td>不需要</td></tr><tr><td>SM4</td><td>0.64</td><td>支持</td><td>需要</td></tr><tr><td>混合加密</td><td>134.80</td><td>支持</td><td>不需要</td></tr></table></body></html>

可以看到，虽然SM3与SM4算法在加密时间上均有优势，但它们均有一些算法体制上的不足：SM3算法只能进行单向加密计算，无法从杂凑值反推得到明文数据；SM4算法需要额外的安全通道进行密钥的传输，在密钥管理上繁琐复杂。而混合加密算法不仅与SM2算法一样不存在上述算法体制的问题，而且在加密时间上也比SM2算法缩短了 $2 6 . 6 7 \%$ 充分体现了本文设计的混合加密系统的优越性。

在SM2算法的点运算层优化上，本文的二级并行方案与传统串行方案[23]、三级并行方案[20]的复现结果性能对比如表6、7所示。其中 $\mathbf { A } \mathbf { T } ^ { 2 }$ 为硬件电路的面积与运算时间平方的乘积，用以评估不同方案性能优劣。

表5不同体制加密算法性能与特性对比  
表6点加方案的性能对比  

<html><body><table><tr><td>点加方案</td><td>资源消耗(LUT)</td><td>运算时间(us)</td><td>AT2(×10²)</td></tr><tr><td>传统串行[23]</td><td>8988</td><td>0.32</td><td>9.204</td></tr><tr><td>二级并行(本文)</td><td>18141</td><td>0.175</td><td>5.556</td></tr><tr><td>三级并行[20]</td><td>24744</td><td>0.155</td><td>5.945</td></tr></table></body></html>

表7倍点方案的性能对比

Tab.7Comparison of performance for double   
point schemes from different desigr   

<html><body><table><tr><td colspan="2">Polrt taesrgh</td><td colspan="2">运算时间(μs)</td></tr><tr><td>倍点方案 传统串行[23]</td><td>资源消耗(LUT) 8382</td><td>0.235</td><td>AT2(X 102) 4.629</td></tr><tr><td>二级并行(本文)</td><td>17045</td><td>0.155</td><td>4.095</td></tr><tr><td></td><td></td><td></td><td>4.437</td></tr><tr><td>三级并行[20]</td><td>24347</td><td>0.135</td><td></td></tr></table></body></html>

可以看到，本文设计的二级并行加速方案虽然在运算时间上并不是最短的，但是其 $\mathrm { A T } ^ { 2 }$ 指标均为最小，相比于传统串行方案分别降低了 $3 9 . 6 \%$ 和 $1 1 . 5 \%$ ，在运算时间和面积开销的协调平衡上最具优势。

在SM4算法的流水线优化上，表8则列出了在32轮全展开轮间流水的结构下不同轮内流水级数架构的FPGA电路实现情况。同时，表中还引入了吞吐率/面积的指标，以衡量各架构的速度与资源消耗情况。其中CLB代表XilinxFPGA 芯片的可配置逻辑单元(ConfigurableLogicBlock,CLB)。

Tab.6Comparison of performance for point addition schemes from different desigr   
表8SM4 轮内流水结构  
Tab.8Comparisons of FPGA implementations for SM4 different subpipelined structure   

<html><body><table><tr><td rowspan="2">轮内流水级数</td><td colspan="4">资源消耗</td><td rowspan="2">关键路径</td><td rowspan="2">Fmax (MHz)</td><td rowspan="2">吞吐率 (Mbps)</td><td rowspan="2">吞吐率/面积 (Mbps/CLB)</td></tr><tr><td>LUT</td><td>LUTRAM</td><td>Register</td><td>CLB</td></tr><tr><td>No</td><td>12372</td><td>NA</td><td>6419</td><td>1547</td><td>4 AND + 36 XOR</td><td>169</td><td>21632</td><td>13.98</td></tr><tr><td>2</td><td>14852</td><td>NA</td><td>12214</td><td>1857</td><td>2 AND+18XOR</td><td>259</td><td>33152</td><td>17.85</td></tr><tr><td>3</td><td>12161</td><td>496</td><td>14912</td><td>1963</td><td>1 AND +14 XOR</td><td>334</td><td>42752</td><td>21.77</td></tr><tr><td>4</td><td>14264</td><td>1488</td><td>13874</td><td>2110</td><td>2 AND +8 XOR</td><td>400</td><td>51200</td><td>24.26</td></tr><tr><td>5</td><td>13216</td><td>1504</td><td>14624</td><td>2239</td><td>2 AND +7 XOR</td><td>420</td><td>53760</td><td>24.01</td></tr></table></body></html>

由表8可以看到，五级轮内流水架构的时钟频率和吞吐率均为最高，分别达到了 ${ 4 2 0 } \mathrm { M H z }$ 和 53.7Gbps，吞吐率相比无轮内流水提高了 $1 3 6 . 7 \%$ 。而在吞吐率/面积指标上，四级轮内流水架构取得了最佳的性能，高达24.26Mbps/CLB，相比优化前提升了 $7 3 . 5 \%$ 。在对加密速率和整体硬件消耗进行取舍后，选取四级轮内流水架构作为混合加密系统中SM4算法的实现方案，以实现高吞吐率与硬件消耗的性能平衡。

# 4.3 相关工作对比

# 4.3.1SM2性能对比

将SM2算法模块的硬件实现结果与其他同类型文献工作对比，得出如表9所示的SM2算法点乘运算性能对比情况。

Tab.9Comparison of performance from different hardware implementation of point multiplication   

<html><body><table><tr><td>文献</td><td>平台</td><td>资源消耗</td><td></td><td>Fmax/MHz 运算时间/μs</td></tr><tr><td>文献[23]</td><td>40nm</td><td>127K Gates</td><td>388</td><td>480</td></tr><tr><td>文献[18]</td><td>130nm</td><td>659K Gates</td><td>163.7</td><td>20.36</td></tr><tr><td>文献[24]</td><td>130nm</td><td>352.5K Gates</td><td>100</td><td>305.82</td></tr><tr><td>文献[25]</td><td>130nm</td><td>248.9K Gates</td><td>200</td><td>71.5</td></tr><tr><td>文献[7]</td><td>Stratix II</td><td>4742ALMs+8DSPs</td><td>62.3</td><td>770</td></tr><tr><td>文献[20]</td><td>Virtex-7</td><td>29876LUTs+144DSPs</td><td>73.6</td><td>221</td></tr><tr><td></td><td>文献[27]Virtex-2</td><td>12425LUTs</td><td>55.7</td><td>8250</td></tr><tr><td></td><td>文献[28]Virtex-2</td><td>36524LUTs</td><td>63.2</td><td>1470</td></tr><tr><td>本文</td><td>ZCU102</td><td>41067LUTs+320DSPs</td><td>215</td><td>68.37</td></tr></table></body></html>

从表9可知，本文设计的SM2点乘电路的最高工作频率高达 $2 1 5 \mathrm { { M H z } }$ ，仅需 $6 8 . 3 7 \mu \mathrm { s }$ 即可完成一次点乘计算，在运算速度上具有一定优势。经本文优化后的点乘电路仅次于文献[18]，而文献[18]由于采用了多个256位大位宽乘法器，可以在一个周期内完成模乘计算，虽然具有高性能的优势，但是硬件开销也非常庞大，并不适合资源有限的场景。此外，在同样使用FPGA开发平台的工作中，本设计在工作频率和运算速度上的优势更为明显：与综合性能较优的文献[20]相比，本设计的最高频率提升了约2.92倍，运算时间缩短了约$6 8 . 9 \%$ 。

综上所述，本设计的模乘单元采用了KO算法和模加运算并行的实现方案，有效地降低了模乘运算的运算周期，同时还对点运算层进行二级模乘运算并行的优化设计，使得优化后的SM2算法电路取得最佳的性能，更加适合本文混合加密系统。

# 4.3.2SM4性能对比

表10中列举了同样在32轮全展开轮间流水的结构下，本文的SM4设计方案与各文献方案的电路实现情况性能对比，表中的吞吐率均为理论峰值吞吐率。相比于各参考文献，在同等采用轮间流水优化结构的情况下，本文设计的四级与五级轮内流水架构突破了单轮运算关键路径过长的瓶颈，其系统最高工作频率分别可达到 $4 0 0 \mathrm { { M H z } }$ 和 $4 2 0 \mathrm { M H z }$ ，峰值吞吐率分别高达51.2Gbit/s 和53.76Gbit/s。与性能较优的文献[30]相比，本设计的最高频率分别提升了 $1 6 . 3 \%$ 和 $22 \%$ ，吞吐率提高了 $2 1 . 6 \%$ 和 $2 7 . 7 \%$ ，完成了高吞吐率加解密算法硬件实现的目标，可以很好地满足本文提出的高速混合加密系统的需求。

# 5 结束语

本文提出了一种基于国密算法SM2、SM3、SM4的高速混合加密系统，通过混合使用三种加密算法避免了单一密码体制安全性不高、加密速率过慢、密钥管理不便等缺点。此外，本文还对系统中限制整体加解密速度提升的SM2和SM4算法进行硬件实现上的优化设计。实验结果表明，本文设计的SM2硬件电路由于采用了二级点运算并行架构，在运算速率与硬件利用率上相比于现有工作更具优势。另外，本文在轮间流水结构的基础上，对内部电路进行分析与优化，设计出了一种基于复合域S盒的 SM4二次流水架构，进一步提高了电路工作频率，其最高峰值吞吐率达到了53.76Gbit/s。综上所述，本文所设计的混合加密系统通过采用多种加密算法以及对相关电路进行优化，在保证安全性的同时提供了极高的运算速率，解决了大数据时代下海量数据加解密的高速加解密需求。

表9点乘运算硬件实现性能对比  
表10SM4 硬件设计性能对比  
Tab.10Comparison of performance from different hardware   

<html><body><table><tr><td colspan="5">implementationofSM4</td></tr><tr><td>文献</td><td>平台</td><td>资源消耗</td><td>Fmax/MHz 吞吐率/Gbps</td><td></td></tr><tr><td>文献[10]</td><td>Stratix II</td><td>8373 ALMs</td><td>162</td><td>20.736</td></tr><tr><td>文献[11]</td><td>Stratix II</td><td>7661 ALMs</td><td>170</td><td>21.760</td></tr><tr><td>文献[26]</td><td>Stratix IV</td><td>8045 ALMs</td><td>212.13</td><td>27.153</td></tr><tr><td>文献[13]</td><td>Virtex-4</td><td>7669 CLBs</td><td>298</td><td>26.224</td></tr><tr><td>文献[29]</td><td>Cyclone IV</td><td>33397LEs</td><td>100</td><td>12.8</td></tr><tr><td>文献[30]</td><td>Kintex-7</td><td>3213LUTs +7736 Regs +33BRAMs</td><td>344</td><td>42.1</td></tr><tr><td>本文(四级轮内流水)</td><td>ZCU102</td><td>2110 CLBs</td><td>400</td><td>51.200</td></tr><tr><td>本文(五级轮内流水)</td><td>ZCU102</td><td>2239 CLBs</td><td>420</td><td>53.760</td></tr></table></body></html>

# 参考文献：

[1]Mostafaa H,Eisaa S M, Issaa HH,et al. Lightweight hybrid encryption system with FPGA design proposal[J].IOP Conference Series:Materials Science and Engineering,2021,1051(1): 012023.   
[2]Shende V,Kulkarni M.FPGA based hardware implementation of hybrid cryptographic algorithm for encryption and decryption [C]// Proc of IEEE ICEECCOT. Piscataway, NJ: IEEE Press,2017: 416-419.   
[3]卞建秀，李垣江，王建华．基于 SM4 和 ECC 的混合加密算法研究 [J]．计算机应用与软件,2016,33(10):303-306,324.(Bian Jianxiu,Li Yuanjiang，Wang Jianhua. Study on SM4 and ECC-based hybrid encryption algorithm[J].Computer Applications and Software,2016,33 (10):303-306,324.)   
[4] 方轶，丛林虎，邓建球．基于国密算法的武器装备数据混合加密方 案[J].探测与控制学报,2020,42(01):121-126.(Fang Yi,CongLinhu, Deng Jianqiu.A hybrid encryption scheme of weapons and equipment data based on national security algorithm[J].Journal of Detection and Control,2020,42 (01): 121-126.)   
[5]Wang Tong,Cui Wenpeng,Li Tong,et al. The research of the SM2, SM3 and SM4 algorithms in WLAN of transformer substation [Cl//Proc of the 3rd International Conference on Electronic Information Technology and Computer Engineering.Piscataway,NJ:IEEE Press,2019:276-283.   
[6]Zheng Xin,Xu Chongyao,Hu Xianghong,et al. The software/hardware co-design and implementation of SM2/3/4 encryption/decryption and digital signature system [J].IEEE Trans on Computer-Aided Design of Integrated Circuits and Systems,2019,39 (10): 2055-2066.   
[7]郭晓，蒋安平，宗宇.SM2高速双域Montgomery模乘的硬件设计[J]. 微电子学与计算机,2013,30(9):5.(Guo Xiao,Jiang Anping,Zong Yu. A high speed structure for dual-field montgomery modular multiplication in SM2[J].Microelectronics and Computer,2013,30 (9):5.)   
[8]Zhang Dan,Bai Guoqiang.High-performance implementation of SM2 based on FPGA[C]//Proc of the 8th IEEE International Conference on Communication Software and Networks. Piscataway,NJ: IEEE Press, 2016: 718-722.   
[9] 杨博，孟李林，陶琼．基于FPGA 的F_P域模乘与模逆的设计与实 现[J].微电子学与计算机,2017,34(5):5.(Yang Bo,Meng Lilin,Tao Qiong.Design of F_P field modular multiplication and modular inversion based on FPGA[J].Microelectronics and Computer,2017,34 (5): 5.)   
[10] Gao Xianwei,Lu Erhong,Xian Liqin,et al. FPGA implementation of the SMS4 block cipher in the Chinese WAPI standard [C]//Proc of IEEE ICESS.Piscataway,NJ: IEEE Press,2008:104-106.   
[11] Wang Husen,Li Shuguo.High performance FPGA implementation for SMS4 [M].Berlin,Heidelberg: Springer,2011: 469-475.   
[12]王晨光，乔树山，黑勇．分组密码算法 SM4的低复杂度实现[J].计 算机工程,2013,39(7):4.(Wang Chenguang,Qiao Shushan,Hei Yong. Low complexity implementation of block cipher SM4 algorithm [J]. Computer Engineering,2013,39 (7): 4.)   
[13]周洲，何一凡，沈海斌，等.SMS4 密码算法高速引擎实现[J]．电子 器件,2007 (04):347-349,358.(Zhou Zhou,He Yifan,Shen Haibin,et al.High-speed implementation of the SMS4 algorithm engine [J]. Journal of Electron Devices,2007 (04): 347-349,358.)   
[14] Fu Hailiang,Bai Guoqiang,Wu Xingjun.Avery compact masked S-Box for high-performance implementation of SM4 based on composite field [C]// Proc of ICST. Berlin,Heidelberg: Springer,2017: 710-721.   
[15]汪朝晖，张振峰.SM2 椭圆曲线公钥密码算法综述[J].信息安全研 究,2016,2 (11): 972-982.(Wang Zhaohui, Zhang Zhenfeng. Overview on public key cryptographic algorithm SM2 based on elliptic curves [J]. Journal of Information Security Research,2016,2(11): 972-982.)   
[16]吕述望，苏波展，王鹏，等.SM4 分组密码算法综述[J].信息安全 研究,2016,2 (11):13.(Lyu Shuwang,Su Bozhan,Wang Peng,et al. Overview on SM4 algorithm [J].Journal of Information Security Research,2016,2(11): 13.)   
[17]邹雪城，周家乐，刘文超，等．小面积高兼容性RSA&SM2的硬件实 现方法[J]．华中科技大学学报：自然科学版,2019,47(01):79-84. (Zou Xuecheng,Zhou Jiale,Liu Wenchao,et al.Design method of RSA&SM2 hardware with low-area and high-compatibility [J]. Journal of Huazhong University of Science and Technology: Natural Science, 2019,47 (01): 79-84.)   
[18] Zhao Zhenwei,Bai Guoqiang.Ultra high-speed SM2 ASIC implementation [C]/ Proc of the 13th IEEE International Conference on Trust, Security and Privacy in Computing and Communications. Piscataway,NJ: IEEE Press,2014: 182-188.   
[19] Hankerson D,Menezes A J,Vanstone S.Guide to elliptic curve cryptography[M].[S.1.]: Springer Science & Business Media,2006.   
[20]李凡，李云峰，翁天恒，等．基于FPGA的 SM2 点运算快速并行实 现[J]．电子测量技术，2020(15):7.(LiFan,Li Yunfeng,Weng Tianheng，et al. Implementation of parallel and fast SM2 point calculation on FPGA[J. Electronic Measurement Technology,15 (020): 7.)   
[21] Liu Fen,Wen Ji,Lei Hu,et al.Analysis of the SMS4 block cipher [C]// Proc of ACISP. Berlin, Heidelberg: Springer,2007:158-170.   
[22]徐艳华，白雪飞，郭立．适合SMS4算法硬件实现的S盒构造新方法 [J]．中国科学技术大学学报,2009 (11):7.(Xu Yanhua,Bai Xuefei, Guo Li.Anew algorithm of S-box for hardware implementation of SMS4 [J].Journal ofUniversity of Science and Technology of China,2oo9(11): 7.)   
[23]陆启乐．一种面向椭圆曲线的双域点乘加速器的设计[D].南京： 东 南大学,2018.(Lu Qile.Design of a dual-field point multiplication accelerator in elliptic curve cryptography [D]. Nan Jing: Southeast University, 2018.)   
[24]陆江城．基于非对称加密算法的加密系统的研究与实现[D].广州： 广东工业大学,2020.(Lu Jiangcheng.Research and implementation of encryption system based on asymmetric encryption [D]. Guangzhou: Guangdong University of Technology,2020.)   
[25]张盛仕，胡湘宏，熊晓明．基于国密算法 SM2 软硬件协同系统的 FPGA 架构[J]．单片机与嵌入式系统应用,2019,19(7):5.(Zhang Shengshi， Hu Xianghong,Xiong Xiaoming.FPGA architecture of software and hardware co-design based on nation secret algorithm SM2 [J]. Microcontrollrs and Embedded Systems,2019,19 (7): 5.)   
[26] Guan Zhenyu,Li Yunhao,Shang Tao,et al.Implementation of SM4 on FPGA: trade-off analysis between area and speed [C]// Proc of IEEE ISR. Piscataway,NJ: IEEE Press,2018:192-197.   
[27] Liu Z,Liu D, Zou X.An efficient and flexible hardware implementation of the dual-field eliptic curve cryptographic processor [J]. IEEE Trans on Industrial Electronics,2017,64 (3): 2353-2362.   
[28]张丽．双域椭圆曲线密码协处理器关键技术研究[D]．西安：西安 电子科技大学,2019.(Zhang Li.Research on key technology of dualfieldelliptic curve cryptography coprocessor [D]. Xian: Xidian University, 2019.)   
[29] 刘金峒，梁科，王锦，等.SM4加密算法可裁剪式结构设计与硬件实 现[J].南开大学学报：自然科学版,2019,52(4):5.(Liu Jintong, Liang Ke,Yu Jin,et al. Tailorable structure design and hardware implementation of SM4 encryption algorithm [J]. Journal of Nankai University: Natural Science,2019,52 (4):5.)   
[30] 何诗洋，李晖，李凤华.SM4 算法的 FPGA 优化实现方法[J]．西安 电子科技大学学报,2021,48 (3):8.(He Shiyang,Li Hui,Li Fenghua. Optimization and implementation of the SM4 on FPGA[J]. Journal of Xidian University,2021,48 (3): 8.)