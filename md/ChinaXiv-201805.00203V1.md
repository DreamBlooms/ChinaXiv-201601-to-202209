# 一种隐藏访问结构的文件层次属性加密研究

沈学利‘，吕莹楠b

(辽宁工程技术大学 a.电子与信息工程学院;b.研究生院，辽宁 葫芦岛 125105)

摘要：基于文件层次结构的属性加密方案在云存储环境下是高效率、低存储的，但访问结构本身包含敏感信息，存在用户信息泄露、文件易被窃取的风险，针对这一问题提出了一种隐藏访问结构的文件层次属性加密方案。该方案在不影响加密解密效率的前提下提高了加密算法的安全性，并采用双因子身份认证机制实现了更安全高效的访问控制。该研究成果基于判定性双线性Diffie-Hellman 假设，在标准模型下被证明是安全的。

关键词：云存储；访问结构；文件层次；属性加密；双因子身份验证 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.07.0698

Research on file hierarchy attribute encryption of hidden access structure

Shen Xuelia, Lyu Yingnanb (a.SchoolofElectronics&InformationEngineering;b.SchoolofGraduateStudiesLiaoningTechnical UniversityHuludao Liaoning 125105,China)

Abstract:Theatributeencryptionschemebasedoflehierarchyis eficientandlowinthecloudstorage environment,utthe accesstructure itselfcontainssensitiveinformation,there is theriskofuser informationleakageandeasytobestolen.Aiming atthis problem,thispaperproposedafile-levelatributeencryptionscheme withhidenaccess structure.Thescheme improved thesecurityoftheencryptionalgorithmwithoutaffcting theencryptionanddecryption eficiency,andadoptedatwo-factor authentication mechanism toachieve a more secureand eficient accesscontrol.Theresults of the studyarebased on the deterministic bilinear Diffe-Hellman hypothesis,which is proved to be safe under the standard model.

Key Words: cloud storage; accesstructure; file hierarchy; attribute encryption; two-factor authentication

# 0 引言

云存储以分布式计算技术为基础，在开放的网络环境下为用户提供了强大的共享和存储能力，然而传统的加密技术已经不能满足用户对于细粒度的访问控制要求[I]。因此Waters等人提出了一种基于密文策略的属性加密方案(CP-ABE)[2]实现细粒度的访问控制。已有很多学者提出的一些基于密文策略的属性加密方案[3\~7在加密具有层次结构的文件时是高开销、低效率的。Wang等人[8]为此提出了一种基于文件层次的属性加密访问控制方案 (简称FH-CP-ABE)，该方案通过访问结构分层模型来解决多层次文件共享的问题，文件使用一个集成的访问结构进行加密以减少存储成本和计算复杂度，但由于访问结构本身具有敏感信息，对访问结构进行攻击易造成用户信息泄露、文件易被窃取的风险。

在云存储环境下，基于属性加密（ABE）的加密方案可以实现灵活的用户访问控制，其中身份认证是访问控制的第一道防线，是云存储环境安全的基础。双因子身份认证是一种强化的网络访问控制机制，它为登录过程增加了额外的安全层。1999年Yang等人[9首次提出了一种使用智能卡的密码认证方案，区别于常规的密码方案该方案的关键是首次采用双因子身份验证策略。随后在此方案的基础上一些学者提出了大量关于双因子认证方案，比如Fan 等人[10]提出的一种强大的远程认证方案与智能卡。Das 等人[1]提出的一种基于动态ID 的远程用户认定方案,解决静态用户ID 被攻击的安全问题。2015年Wang 等人[12]提出了一种分布式系统中匿名双因子认证机制，该方案是高效的且安全的。

本文为解决上述问题，参考已有的隐藏访问策略的加密模型[13\~16提出一种隐藏访问结构的文件层次属性加密方案（简称HASFH-CP-ABE)。通过对访问结构进行部分隐藏，防止访问结构泄露敏感信息，造成用户信息泄露，文件被窃取的风险。同时采用文献[12]中的双因子身份验证机制，实现更安全高效的访问控制。

本方案基于判断性DBDH假设，在标准模型下被证明是安全的。

# 1 相关工作

# 1.1双线性映射

Go和 $\mathbf { G } _ { 1 }$ 是两个阶为素数 $\mathfrak { p }$ 的乘法循环群， $\mathrm { \bf ~ g }$ 为 $\mathrm { \bf G } _ { 0 }$ 的生成元，双线性映射e： $G _ { 0 } \times G _ { 0 } \to G _ { 1 }$ ，e满足以下性质：

(a)双线性。对 $\forall u , \nu \in G _ { 0 }$ ， $a , b \in Z _ { p }$ ，都有 $e \left( u ^ { a } , \nu ^ { b } \right) = e \left( u , \nu \right) ^ { a b }$ 。  
(b)非退化性。存在 $u , \nu \in G _ { 0 }$ ,使得 $e \big ( u , \nu \big ) \not = 1$ 。  
(c)可计算性。对所有 $u , \nu \in G _ { 0 }$ ,存在有效计算 $e { \bigl ( } u , \nu { \bigr ) }$ 。

# 1.2 复杂性假设DBDH

挑战者基于系统安全参数下，选择阶为素数 $\mathrm { ~ p ~ }$ 的群组 $G _ { 0 } , G _ { 1 }$ ，使得 $a , b , c \in Z _ { p }$ ， $r \in G _ { 1 }$ ’ $\mathrm { \Delta g }$ 为 $G _ { 0 }$ 的生成元,判断是否 $r = e \left( g , g \right) ^ { a b c }$ 。给定一个算法 $\mathrm { ~ B ~ }$ ，如果：

$$
\begin{array} { r l } & { \left| \operatorname* { P r } \bigg [ B \Big ( g , g ^ { a } , g ^ { b } , g ^ { c } , e \big ( g , g \big ) ^ { a b c } = 0 \Big ) \bigg ] \right| _ { \textstyle \geq \varepsilon , } } \\ & { - \operatorname* { P r } \bigg [ B \Big ( g , g ^ { a } , g ^ { b } , g ^ { c } , r = 0 \Big ) \bigg ] } \end{array}
$$

则称B 解决DBDH问题的优势为 $\varepsilon$ 。

定义1如果没有多项式算法有不可忽略的优势解决DBDH问题，则称DBDH假设成立。

# 1.3访问结构

设 $p = \ \{ p _ { 1 } , p _ { 2 } L \ L \ p _ { n } \}$ 为用户集合，对于集合A， $A \subseteq 2 ^ { P }$ 是 $2 ^ { p }$ 上的一个非空子集，即 $A \subseteq 2 ^ { P } \setminus \{ \varphi \}$ 。如果 $B \in A$ 且 $B \subseteq C$ ，那么$C \in A$ ，则称A为单调的。包含于访问结构A中的集合称为授权集合，不包含于A中的集合称为非授权集合。

# 1.4访问结构树

访问结构树T代表一个访问结构，这里本文假设所要共享的文件分成 $\mathbf { k }$ 个访问级别，则 $M = \left\{ m _ { 1 } , m _ { 2 } L \ m _ { k } \right\}$ ，其中 $m _ { \mathrm { 1 } }$ 代表最高级别， $m _ { k }$ 为最低级别。访问树中的节点用 $( \mathrm { x } , \mathrm { y } )$ 表示。叶子节点表示属性，非叶子节点表示阈值，为了便于访问树的使用，本文给出如下定义：

$n u m _ { ( x , y ) }$ ,表示节点 $( \mathrm { x } , \mathrm { y } )$ 的孩子节点的个数。

$k _ { ( x , y ) }$ ，表示节点阈值。若节点为叶子节点时， $k _ { ( x , y ) } ~ = 1$ ；若节点为非叶子节点时： $k _ { ( x , y ) } ~ = 1$ ，表示OR， $k _ { ( x , y ) } { \mathrm { \Omega } } = n u m _ { ( x , y ) }$ ，表示AND。

$p a r e n t _ { ( x , y ) }$ ,节点 $( \mathrm { x } , \mathrm { y } )$ 的父节点。

$\left( x _ { i } , y _ { i } \right)$ ，表示级节点,每个级节点是被集成的访问树的根节点。其中 $\left( x _ { 1 } , y _ { 1 } \right)$ 表示最高级,从上到下级别依次递减。

child $\left( x , y \right)$ :表示节点 $( \mathrm { x } , \mathrm { y } )$ 的孩子节点。

$a t t \left( x , y \right)$ ：表示与节点 $( \mathrm { x } , \mathrm { y } )$ 相关联的属性。

index $\left( x , y \right)$ ,表示访问树为每个节点的孩子节点任意分配从1至$n u m _ { ( x , y ) }$ 的数值。 $i n d e x { \bigl ( } x , y { \bigr ) }$ 返回与该节点相关的唯一数值。

# 1.5 双因子身份验证[12]

双因子身份验证的实施需要两个阶段来完成即注册阶段和验证阶段。为了方便描述给出如下定义： $s$ 为远程服务器， $A$ 为用户服务器，哈希函数 $H _ { i } = \left\{ 0 , 1 \right\} ^ { * } = \left\{ 0 , 1 \right\} ^ { l _ { i } }$ ， $\mathrm { i } { = } 1 , 2 , 3 , \ \Rightarrow$ 表示安全通道， $$ 表示普通通道。 $\textbf { x }$ 为 S 的私钥，计算 $y = g ^ { x } { \bmod { p } }$ 。

1）注册阶段

用户 $U _ { i }$ 选取其身份 $I D _ { i }$ 密码 $P W _ { i }$ ，随机字符串a，则

$$
U _ { i } \Rightarrow { S : \left\{ { I D } _ { i } , { H } _ { 0 } \left( a P P W _ { i } \right) \right\} }
$$

用户的注册时间为t,S选取随机数 $\boldsymbol { \mathbf { b } }$ ，计算验证参数：

$$
M _ { i } = H _ { 0 } \left( \left( H _ { 0 } \left( I D _ { i } \right) \oplus H \left( a P P W _ { i } \right) \right) \right)
$$

将以下内容存储在存储条目中：

$$
\{ I D _ { i } , t , a , H o n e y  _ { - } L i s t = N U L L \}
$$

计算：

$$
N _ { i } = H _ { 0 } \left( a P P W _ { i } \right) \oplus H _ { 0 } \left( x P I D _ { i } P t \right)
$$

具有安全参数的智能卡 SC则为

$$
S \Rightarrow U _ { i } : \left\{ N _ { i } , M _ { i } , y \right\}
$$

2）验证阶段

用户将智能卡插入读卡器，并且输入身份信息和密码信息$I D _ { i } ^ { \prime } , P W _ { i } ^ { \prime }$ ，SC执行下列操作：

$$
{ M _ { i } ^ { ' } = \{ H _ { 0 } ( H _ { 0 } ( I D _ { i } ^ { ' } ) \oplus ( a P P W _ { i } ^ { ' } ) ) \} }
$$

若 ${ M } _ { i } ^ { ' } = { M } _ { i }$ ，SC 选取随机数d,计算：

$$
Y _ { 1 } = g ^ { d } \bmod p , Y _ { 2 } = y ^ { d } \bmod p
$$

$$
K = H _ { 0 } \left( x P I D _ { i } P t \right) = N _ { i } \oplus H _ { 0 } \left( a P P W _ { i } \right)
$$

$$
C I D _ { i } = I D _ { i } ^ { ' } \oplus H _ { \mathrm { 0 } } \left( Y _ { \mathrm { 1 } } P Y _ { \mathrm { 2 } } \right)
$$

$$
C M K _ { i } = \left( b P k \right) \oplus H _ { 0 } \left( Y _ { 2 } P Y _ { 1 } \right)
$$

$$
{ M _ { i } } ^ { \prime } = \{ H _ { 0 } ( Y _ { 2 } P K P C I D _ { i } P C M K _ { i } ) \}
$$

$$
U _ { i } \to S : \{ Y _ { 2 } , C I D _ { i } , C M K _ { i } , M _ { i } ^ { \prime \prime } \}
$$

根据用户登录请求信息，S执行以下操作：

计算：

$$
Y _ { 2 } = Y _ { 1 } ^ { x } \bmod p , I D _ { i } = C I D _ { i } \oplus H _ { 0 } \left( Y _ { 1 } P Y _ { 2 } \right) , K = H _ { 0 } \left( x P I D _ { i } P t \right)
$$

$M _ { i } ^ { \prime \prime \prime } { = } H _ { 0 } ( Y _ { 1 } P K P C I D _ { i } P C M K _ { i } )$ ,验证 ${ M _ { \mathrm { i } } ^ { \prime \prime } } = { M _ { i } ^ { \prime } } ^ { \prime }$ 是否成立。若成立S 随机生成e,生成临时密钥

$$
K _ { s } = Y _ { 1 } ^ { \mathrm { e } } { \bmod { p } }
$$

$$
\begin{array} { l } { { C _ { 1 } = g ^ { e } \bmod p , C _ { 2 } = H _ { 1 } \big ( I D _ { i } P I D _ { s } P Y _ { 2 } P C _ { 1 } P K P K _ { s } \big ) } } \\ { { S  U _ { i } : \big \{ C _ { 1 } , C _ { 2 } \big \} } } \end{array}
$$

接收到来自远程服务器S的消息后，SC执行计算：

$$
K _ { \scriptscriptstyle U } = C _ { 1 } ^ { \scriptscriptstyle U } \mathrm { m o d } p , C _ { 2 } ^ { \prime } = H _ { 1 } \big ( I D _ { i } P I D _ { s } P Y _ { 2 } P C _ { 1 } P K P K _ { \scriptscriptstyle U } \big )
$$

验证 ${ C _ { 2 } } ^ { \prime } = { C _ { 2 } }$ 是否成立。若成立计算：

$$
{ C _ { 3 } } ^ { \prime } = { H _ { 2 } } ( I D _ { \mathrm { i } } ^ { \prime } P I D _ { s } P Y _ { 2 } P C _ { \mathrm { i } } P K P K _ { \scriptscriptstyle U } ) , { U _ { i } }  S : \{ C _ { 3 } \}
$$

S 接受后计算：

$C _ { 3 } ^ { ' } = H _ { 2 } \left( I D _ { \mathrm { i } } P I D _ { s } P Y _ { _ 2 } P C _ { 1 } P K P K _ { s } \right)$ ，验证 ${ C _ { 3 } } ^ { \prime } = C _ { 3 }$ 是否成立若成立，则验证完成用户 $U _ { \mathrm { i } }$ 和S认证 $K _ { s }$ 为会话密钥。

# 2 HASFH-CP-ABE方案构造

本文在文献[8]的基础上，采用双因子身份认证体制，提出了一种HASFH-CP-ABE 加密方案。

# 2.1用户注册

权威机构S的私钥为 $\mathbf { x }$ ，计算 $y = g ^ { x } { \bmod { p } }$ 作为系统公钥，用户选取随机字符串a,并且输入身份和密码 $I D _ { i }$ ， $P W _ { i }$ 。计算$H _ { 0 } \left( a P P W _ { i } \right)$ ，将 $\left\{ I D _ { i } , H _ { 0 } \left( a P P W _ { i } \right) \right\}$ 发送给权威机构 S，S随机选取参数 $\boldsymbol { \mathbf { b } }$ ，根据用户注册时间t进行计算：

$$
M _ { i } = H _ { 0 } \left( \left( H _ { 0 } \left( I D _ { i } \right) \oplus H \left( a P P W _ { i } \right) \right) \right) , N _ { i } = H _ { 0 } \left( a P P W _ { i } \right) \oplus H _ { 0 } \left( x P I D _ { i } P t \right)
$$

并将 $\{ I D _ { i } , t , a , H o n e y  _ { - } L i s t = N U L L \}$ 存储在用户数据库中，将$\left\{ N _ { i } , M _ { i } , y \right\}$ 保存在智能卡 SC 中。

# 2.2加密算法

定义一个双线性映射 $e : G _ { 0 } \times G _ { 0 } \to G _ { 1 }$ 。 $G _ { 0 } , G _ { 1 }$ 是阶为素数p的乘法循环群， $\mathrm { \Phi _ { g } }$ 是生成元，A表示系统中的属性集合$A = \left\{ S _ { 1 } , S _ { 2 } L L S _ { n } \right\}$ ，每个属性 $S _ { i }$ 都有 $\mathfrak { m }$ 个取值，即

$$
S _ { i } ~ = \bigl \{ t _ { i , 1 } , t _ { i , 2 } L L t _ { i , m } \bigr \} ~ \bigl ( 1 \leq i \leq n , m = 1 , 2 , 3 L L \bigr )
$$

用户的属性列表 $L = \left\{ l _ { 1 } , l _ { 2 } L ~ M _ { j } \right\}$ ， $L \subseteq A , l _ { i } \in S _ { i }$ 。定义两个哈希函数：

$$
\begin{array} { r } { { H _ { 1 } ^ { * } : \{ 0 , 1 \} ^ { * }  G _ { \mathrm { 0 } } } } \\ { { H _ { 2 } ^ { * } : \{ 0 . 1 \} ^ { * }  G _ { 1 } } } \end{array}
$$

T为访问结构W对应的的访问结构树，每个访问结构都对应一个访问结构树，其中访问结构树的根节点为 $\mathrm { ~ \tt ~ R ~ }$ 。

Setup ${ \left( { \bf \Phi } _ { 1 } { \lambda } \right) }$ ：系统初始化，输入安全参数 $\lambda$ ，为系统中的任一属性值随机选取 $\textit { u } _ { i , j } { \in } Z _ { p } ^ { * }$ 1 $\quad 1 \leq i \leq n , 1 \leq j \leq m )$ 。并随机选取 $\alpha , \beta \in Z _ { p } ^ { * }$ ，

计算:

$$
H = g ^ { \beta } , A _ { i , j } = g ^ { u _ { i , j } } , Y = e \bigl ( g , g \bigr ) ^ { \alpha }
$$

输出：

$$
\begin{array} { c } { { P K = \left\{ G _ { 0 } , g , H , A _ { i , j } , Y \right\} \left( 1 \leq i \leq n , 1 \leq j \leq m \right) } } \\ { { \nonumber } } \\ { { M S K = \left\{ g ^ { \alpha } , \beta , u _ { i , j } \right\} \left( 1 \leq i \leq n , 1 \leq j \leq m \right) } } \end{array}
$$

系统公开公钥 $P K$ ，保存主密钥MSK。

Encrypt(PK,M,T):为每一个节点 $( \mathrm { x } , \mathrm { y } )$ 选取一个多项式$q _ { ( x , y ) }$ ，多项式的选取规则如下：从根节点 $\mathrm { ~ R ~ }$ 开始，每个节点 $( \mathrm { x } , \mathrm { y } )$ 的多项式 $q _ { ( x , y ) }$ 的阶数为 $d _ { ( x , y ) } = k _ { ( x , y ) } - 1$ 。

根节点R的级坐标为 $\left( x _ { 1 } , y _ { 1 } \right)$ ，随机选取 $w \in Z _ { p }$ ，设置$q _ { \scriptscriptstyle ( R ) } \left( 0 \right) = q _ { \scriptscriptstyle ( x _ { 1 } , y _ { 1 } ) } \left( 0 \right) = w$ ，多项式在其他 $d _ { ( R ) }$ 个点的值随机选取来使其定义完整，访问树中除根节点R外其他节点（204号 $q _ { ( x , y ) } \left( 0 \right) = q _ { p a r e n t ( x , y ) } \left( i n d e x _ { ( x , y ) } \right)$ ，其他 $d _ { ( x , y ) }$ 个点的值随机定义：

$$
q _ { _ { c h i l d } } \left( 0 \right) = q _ { _ { \left( x , y \right) } } \left( i n d e x \left( c h i l d \left( x , y \right) \right) \right)
$$

$$
c h i l d \left( x , y \right) = \left\{ c h i l d _ { \left( x , y \right) _ { 1 } } , c h l i d _ { \left( x , y \right) _ { 2 } } L \ L \ c h l i d _ { \left( x , y \right) n u m _ { \left( x , y \right) } } \right\}
$$

对于访问树结构T,本文将每个级节点下的子树中不包含级节点的子树擦除来实现访问结构的隐藏，擦除后的访问结构用$\bar { T }$ 表示。输入验证参数：

$$
\Re { \left( L , W \right) } = \frac { Y ^ { q _ { x _ { i } , y _ { i } } ( 0 ) } } { D e c r y p t { \left( x , y \right) } }
$$

每个级节点 $\left( \mathbf { \nabla } x _ { i } , y _ { i } \right)$ 都是被集成的原访问结构树的根节点，且每个级节点都对应一个级别的密文。计算:

$$
C _ { i } = m _ { i } e \left( g , g \right) ^ { \alpha q _ { \left( x _ { i } , y _ { i } \right) } \left( 0 \right) } , C _ { i } ^ { \prime } = g ^ { q _ { \left( x _ { i } , y _ { i } \right) \left( 0 \right) } }
$$

集合 $\mathrm { \Delta Y }$ 为访问结构树中叶子节点的集合，对于任意的$\left( x , y \right) \in Y$ 计算：

$$
\begin{array} { c } { { C _ { ( x , y ) } = H ^ { q ( x , y ) ( 0 ) } } } \\ { { { } } } \\ { { C _ { ( x , y ) } ^ { \prime \prime } = H _ { 1 } ( a t t ( x , y ) ) ^ { q _ { ( x , y ) } ( 0 ) } } } \end{array}
$$

设置X为传输节点的集合，TN表示传输节点的孩子节点

中代表阈值的节点的集合。计算：

$$
C _ { ( x , y ) } ^ { \mathrm { \tiny ~ \wedge ~ } } = Y ^ { \left( q _ { ( x , y ) } ( 0 ) + q _ { c h i l d ( x , y ) } ( 0 ) \right) } \times H _ { 2 } \left( e \left( g , g \right) ^ { \alpha q _ { ( x , y ) } ( 0 ) } \right)
$$

输出密文：

$$
C T = \{ \overbar { T } , C _ { ( x , y ) } , C _ { ( x , y ) } ^ { \prime \prime } , C _ { i } , C _ { i } ^ { \prime } , C _ { ( x , y ) } ^ { \mathrm { ~ \tiny ~ \wedge ~ } } , \Re \}
$$

# 2.3身份验证及用户私钥生成

(1)用户登录输入身份信息和登录口令 $I D _ { i } ^ { \prime } , P W _ { i } ^ { \prime }$

计算 ${ M _ { i } ^ { \prime } } = \biggl \{ H _ { 0 } \left( H _ { 0 } \left( I D _ { i } ^ { \prime } \right) \oplus \left( a P P W _ { i } ^ { \prime } \right) \right) \biggr \}$ ，验证 $M _ { i } ^ { ' } = M _ { i }$ 是否成立,若成立则智能卡SC随机选取d,计算：

$$
\begin{array} { c } { { Y _ { 1 } = g ^ { d } \mathrm { m o d } p , Y _ { 2 } = y ^ { d } \mathrm { m o d } p } } \\ { { { \cal K } = H _ { 0 } \left( x P I D _ { i } P t \right) = N _ { i } \oplus H _ { 0 } \left( a P P W _ { i } \right) } } \\ { { { \cal C } I D _ { i } = I D _ { i } ^ { ' } \oplus H _ { 0 } \left( Y _ { 2 } P Y _ { 2 } \right) , C M K _ { i } = \left( b P k \right) \oplus H _ { 0 } \left( Y _ { 2 } P Y _ { 1 } \right) } } \end{array}
$$

用户将 $\left\{ { Y _ { 2 } , C I D _ { i } , C M K _ { i } , M _ { i } ^ { " } } \right\}$ 发送给权威机构 $\mathrm { S } _ { \bullet }$ （20

S执行 $K = { { H } _ { \mathrm { { 0 } } } } \left( x P I D _ { \mathrm { { i } } } P t \right)$ ，并计算：

$M _ { i } ^ { \prime \prime } = H _ { 0 } ( Y _ { 1 } P K P C I D _ { i } P C M K _ { i } )$ 验证 ${ M _ { \mathrm { i } } ^ { \prime \prime } } = { M _ { i } ^ { \prime } } ^ { \prime }$ 是否成立,若成立则： $C _ { 2 } = H _ { 1 } \big ( I D _ { i } P I D _ { s } P Y _ { 2 } P C _ { 1 } P K P K _ { s } \big )$ 并将 $C _ { 2 }$ 发送给 $U _ { i }$ ， $U _ { i }$ 进行计算：

$$
{ C _ { 2 } } ^ { \prime } = H _ { 1 } ( I D _ { i } P I D _ { s } P Y _ { 2 } P C _ { 1 } P K P K _ { U } )
$$

验证 ${ C _ { 2 } } ^ { \prime } = { C _ { 2 } }$ 是否成立，若成立计算：$C _ { 3 } ^ { ' } = H _ { 2 } \left( I D _ { \mathrm { i } } P I D _ { s } P Y _ { 2 } P C _ { 1 } P K P K _ { U } \right)$ ,用户将计算结果返回给 $U _ { i }$ $C _ { 3 } ^ { ' } = H _ { 2 } \left( I D _ { \mathrm { i } } P I D _ { s } P Y _ { _ { 2 } } P C _ { \mathrm { i } } P K P K _ { s } \right)$ ，验证 ${ C _ { 3 } ^ { ' } = C _ { 3 } }$ 是否成立，若成立则验证通过,则执行用户私钥生成算法,若不通过则返回 $\perp$ 。

(2)KeyGen(PK,MSK,L):授权中心执行密钥生成算法，随机选取 $r ^ { * } \in Z _ { P } ^ { * }$ 。计算:

$$
{ \cal D } = g ^ { \alpha } { \cal H } ^ { \dot { r } } \qquad { \cal D } _ { l _ { ( i , j ) } } = g ^ { r ^ { * } } \times { \cal H } _ { 1 } ( l _ { ( i , j ) } ) ^ { u _ { i , j } } \qquad { \cal D } _ { l _ { ( i , j ) } } ^ { \eta } = { \cal H } ^ { u _ { i , j } } \ .
$$

输出私钥：

$$
S K = \{ D , D _ { l _ { ( i , j ) } } , D _ { l _ { ( i , j ) } } ^ { \prime } \}
$$

# 2.4解密算法

(1）验证判断

系统为每个用户的属性分配一个属性分量，解密过程中，用户将自己的属性分量分别代入计算。判断验证参数 $\Re$ 的值，若 $\Re = 1$ 执行下面解密操作，若 $\Re \neq 1$ ，则系统返回错误标识符 $\perp$ 。

(2)Decrypt(CT,SK, $( \mathrm { x } , \mathrm { y } )$ )：若 $\Re = 1$ ，当节点 $( \mathrm { x } , \mathrm { y } )$ 为叶子节点时，令 $i = a t t \left( x , y \right)$ ，如果 $i \not \in S$ ，那么 $D e c r y p t { \big ( } C T , S K , ( x , y ) { \big ) } = \perp$ ，若 $i \in S$ ，定义解密算法如下：

$$
D e c r y p t { \left( C T , S K , \left( x , y \right) \right) } = \frac { e ( D _ { l _ { ( i , j ) } } , C _ { ( x , y ) } ) } { e ( D _ { l _ { ( i , j ) } } ^ { \prime } , C _ { ( x , y ) } ^ { \prime } ) }
$$

$$
= \frac { e \Bigg ( g ^ { r ^ { * } } H _ { 1 } \left( l _ { ( i , j ) } \right) ^ { u _ { i , j } } , H ^ { q _ { ( x , y ) } ( 0 ) } \Bigg ) } { e \Bigg ( H ^ { u _ { i , j } } , H _ { 1 } \left( a t t \left( x , y \right) \right) ^ { q _ { ( x , y ) } ( 0 ) } \Bigg ) }
$$

$$
= \frac { e \Big ( g ^ { \tilde { r } } , H ^ { q _ { ( x , y ) } ( 0 ) } \Big ) e \Big ( H _ { 1 } \big ( l _ { ( i , j ) } \big ) ^ { u _ { i , j } } , H ^ { q _ { ( x , y ) } ( 0 ) } \Big ) } { e \Big ( H ^ { u _ { i , j } } , H _ { 1 } \big ( a t t \big ( x , y \big ) \big ) ^ { q _ { ( x , y ) } ( 0 ) } \Big ) } = e \big ( g , g \big ) ^ { r ^ { * } \beta q _ { ( x , y ) } ( 0 ) }
$$

当 $( \mathrm { x } , \mathrm { y } )$ 为非叶子节点， $( \mathrm { x } , \mathrm { y } )$ 的所有孩子节点的集合为Q，对于集合Q里的节点，执行解密操作 $D e c r y p t \big ( C T , S K , Q \big )$ 。将所得结果存储在 $F _ { \varrho }$ 当中， $S _ { ( x , y ) }$ 表示孩子节点集合Q的任意阈值大小。$S _ { ( x , y ) }$ 存在则 $F _ { Q } \neq n u l l$ ，否则 $F _ { \varrho } = n u l l$ 。令 $i = i n d e x ( Q )$ ，定义拉格朗日系数：

$$
\Delta _ { k , s } = \prod _ { l \in s , l \not \in k } \frac { \left( x - l \right) } { \left( k - l \right) } , S _ { ( x , y ) } ^ { \prime } = \left\{ i n d e x \left( Q \right) : Q \in S _ { ( x , y ) } \right\}
$$

计算：

$$
\begin{array} { c }   \displaystyle  \begin{array} { c } { { { \cal D } \ e c r y p t \big ( { \cal C T } , S K , ( x , y ) \big ) = { \cal F } ( x , y ) } } \\ { { } } \\ { { = \displaystyle { \prod _ { \varrho \in \mathcal { S } _ { \lfloor \infty , \cdot \rangle } \forall e } \int _ { 0 } ^ { x _ { i } ( x , y ) \vert n \rangle } = \displaystyle { \prod _ { \varrho \in \mathcal { S } _ { \lfloor \infty , \cdot \rangle } \forall \rho _ { \operatorname { m } } ( \varrho \rho , y ) } } \delta _ { \sigma _ { i , \cdot \rangle n } } ^ { \sigma _ { i , \cdot \rangle n } } | n \rangle } } } \\ { { } } \\ \\ { { = \displaystyle { \sum _ { \varrho \in \mathcal { S } _ { \lfloor \infty , \cdot \rangle } \in ( e , g ) } ^ { - \rho _ { m _ { \langle \cdot \rangle } \langle \theta _ { \tau _ { i } , \cdot \rangle } ( i \binom { 1 } { \theta } } \delta _ { \tau _ { i } , \cdot \sigma _ { y } , n } \vert n \rangle } = e ( g , g ) ^ { - \rho _ { m _ { \langle \cdot \rangle } \langle \theta _ { \tau _ { i } , \cdot } \rangle ^ { \rho _ { m _ { \langle \cdot } \rangle } ( i \binom { 1 } { \theta } } } { \sigma _ { i , \cdot \sigma _ { y } , n } } } ) } } } \\ { { } } \\ \\  { { \displaystyle { \begin{array} { c } { { { \cal A } _ { i } = \displaystyle { \frac { e ( C _ { i } ^ { \prime } , D ) } { D e c \gamma p t ( C T , S K ( x , y , y ) ) } = \displaystyle { \frac { e ( g , g ) ^ { - \rho _ { i } } \mu _ { \langle \tau _ { i } , \cdot \rangle n } } { e ( g , g ) ^ { \top } \rho _ { i , \cdot \sigma _ { i } } ( n \rangle } ) } } } } \end{array} } } } \end{array} \end{array}
$$

$$
= \frac { e \Big ( g ^ { \boldsymbol { q } _ { ( x , \eta ) } ( 0 ) } , g ^ { \alpha } \times g ^ { \beta ^ { * } } \Big ) } { e \big ( g , g \big ) ^ { \tilde { r } ^ { \beta } \boldsymbol { q } _ { ( x , \eta ) } ( 0 ) } } = \frac { e \Big ( g ^ { \boldsymbol { q } _ { ( x , \eta ) } ( 0 ) } , g ^ { \alpha } \Big ) e \Big ( g ^ { \boldsymbol { q } _ { ( x , \eta ) } ( 0 ) } , g ^ { \beta ^ { * } } \Big ) } { e \big ( g , g \big ) ^ { \tilde { r } ^ { \beta } \boldsymbol { q } _ { ( x , \eta ) } ( 0 ) } } \ = e \big ( g , g \big ) ^ { \alpha _ { { q } _ { ( x , \eta ) } } ( 0 ) }
$$

基于访问树的层次性，如果一个用户的属性集包含低授权节点，那么可以通下面这个公式递归计算出每个授权节点的 $\mathbf { \boldsymbol { A } } _ { i }$ 值。计算公式如下：

$$
A _ { ( i + 1 ) , j } = \frac { \overset {  } { C _ { ( x _ { i } , y _ { i } ) } } } { A _ { i } \times H _ { 2 } ( A _ { i } ) } = \frac { \overset {  } { \underset { e  } { Y ^ { ( q _ { ( x _ { i } , y _ { i } ) } ( 0 ) + q _ { ( c h i j ) } ( 0 ) ) } } } \times H _ { 2 } ( e ( g , g ) ^ { \alpha q _ { ( x _ { i } , y _ { i } ) } ( 0 ) } ) } { e ( g , g ) ^ { \alpha q _ { ( x _ { i } , y ) } } \times H _ { 2 } ( e ( g , g ) ^ { \alpha q _ { ( x _ { i } , y _ { i } ) } ( 0 ) } ) }
$$

$$
= e \big ( g , g \big ) ^ { \alpha q _ { c h i l d _ { j } } ( 0 ) }
$$

得到 $A _ { i }$ 后，利用下列公式获得授权文件：

$$
M = \frac { C _ { i } ^ { \prime } } { A _ { i } } { = } \frac { m _ { i } e \big ( g , g \big ) ^ { { \alpha } q _ { ( x _ { i } , y _ { i } ) } ( 0 ) } } { e \big ( g , g \big ) ^ { { \alpha } q _ { ( x _ { i } , y _ { i } ) } ( 0 ) } } { = } m _ { i }
$$

# 3 安全性分析

# 3.1抵抗选择明文攻击

定理1如果一个概率多项式时间内的敌手B没有不可忽略的优势赢得选择性明文攻击下的安全游戏，则该方案是安全的。

证明构建一个模拟器 B，该模拟器能够以 $\varepsilon / 2$ 的优势辨别出DBDH元组和随机元组的区别。定义一个有效的可计算的双线性映射 $e : G _ { 0 } \times G _ { 0 } \to G _ { 1 }$ ，随机选取 $l , m , n \in Z _ { p }$ ， $u \in \{ 0 , 1 \}$ ， $R \in G _ { \mathrm { 1 } }$ ，$\mathrm { \Phi _ { g } }$ 为 $G _ { 0 }$ 的生成元。挑战者定义一个访问结构树T,T的值定义如下：

$$
T = \left\{ \begin{array} { l l } { \displaystyle e \left( g , g \right) ^ { l m n c } , u = 0 } \\ { \quad } \\ { R , u = 1 } \end{array} \right.
$$

模拟器B在该游戏中为挑战者，攻击者为A.这里假设只有一个文件需要被加密。

(1)Initializatton:攻击者A 选择访问结构 $\cdot \bf { \sigma } ^ { \prime }$ ,并将 $\cdot \bf { \Phi } ^ { \prime }$ 发送给 挑战者B.

(2)Setup：挑战者B运行初始化算法，随机选取 $\displaystyle { \big \langle } \mathbf { \Pi } \in { \cal Z } _ { p }$ ，定义 $l = \stackrel { \prime } { l } + \ln$ ， $H = g ^ { \beta } = B = g ^ { n }$

计算：

$$
\begin{array} { c } { { e \left( g , g \right) ^ { l } = e \left( g , g \right) ^ { l + \ln } } } \\ { { = e \left( g , g \right) ^ { l } e \left( g , g \right) ^ { \ln } } } \end{array}
$$

挑战者B将公共密钥PK发送给攻击者 $\mathrm { \bf A }$ 。

(3)Phase1:攻击者A可以自适应性地向挑战者询问私钥提供的属性集：

$\boldsymbol { S } _ { i , j } = \left\{ \boldsymbol { s } _ { i , j } \in { \cal A } \right\} \left( { \cal S } _ { i , j } \notin { \cal A } ^ { \prime } \right)$ 的私钥 $\mathit { s K }$ 。挑战者B 根据 $\mathrm { ~ A ~ }$ 提供的访问结构 $\left| A ^ { \prime } \right|$ ，随机选择 $r ^ { \prime } \in Z _ { p }$ ，定义 $r = r ^ { \prime } - l$ 。计算：

$$
D = g ^ { l } \times H ^ { r } = g ^ { l ^ { \prime } + \mathrm { l n } } g ^ { n r } = g ^ { l ^ { \prime } + n r ^ { \prime } }
$$

对于每一个属性 $\textbf { \textit { s } } _ { i , j } \in A$ ， $\mathrm { ~ B ~ }$ 为每个属性随机选取 $u _ { i , j } ^ { \prime } \in Z _ { p }$ 。计算：

$$
D _ { i , j } ^ { \prime } = g ^ { ( r ^ { \prime } - l ) } \times H _ { 1 } \left( s _ { i , j } \right) ^ { u _ { i , j } ^ { \prime } } = \frac { g ^ { r ^ { \prime } } } { g ^ { l } } \times H _ { 1 } \left( s _ { i , j } \right) ^ { u _ { i , j } ^ { \prime } }
$$

$$
\boldsymbol { D } _ { i , j } ^ { \prime \prime } = \boldsymbol { H } ^ { u _ { i , j } ^ { \prime } } = g ^ { n u _ { i , j } ^ { \prime } }
$$

最后，挑战者B将私钥发送给 $\mathrm { \bf A }$ 。

(4)Challenge：攻击者A提供两个等长的密文消息 $m _ { 1 }$ 和 $m _ { 2 }$ ，挑战者B随机选取 $x \in \{ 0 , 1 \}$ ，在访问结构 $\left| A ^ { \prime } \right|$ 下，运行加密算法。计算： ${ \Big \langle } = g ^ { m }$

$$
\begin{array} { r } { \dot { C } ^ { \prime } = m _ { x } e \left( g , g \right) ^ { l m } = m _ { x } e \left( g , g \right) ^ { \left( l + \ln \right) m } = m _ { x } T e \left( g , g \right) ^ { l m } } \end{array}
$$

挑战者将密文CT发送给攻击者 $\mathrm { \bf A }$ 。

(5)Phase 2:重复Phase1。

(6)Guess:攻击者A输出对于 $u$ 的猜想 $\iota ^ { \prime \prime } \ \left( u ^ { \prime \prime } \in \left\{ 0 , 1 \right\} \right)$

如果 $u = u ^ { \prime \prime }$ ，挑战者B输出 $u = 0$ ，那么 $T = e \left( g , g \right) ^ { l m n }$ ,密文CT为有效的，攻击者的优势为 $\varepsilon$ ，即：

$$
\operatorname* { P r } \biggl [ B \left( g , g ^ { l } , g ^ { m } , g ^ { n } , T = e \left( g , g \right) ^ { l m n } \right) = 0 \biggr ] = \frac { 1 } { 2 } + \varepsilon
$$

如果 $\boldsymbol { u } \neq \boldsymbol { u } ^ { \prime \prime }$ ，则输出 $u = 1$ ，那么 $T = R$ ，从攻击者的角度来看$\acute { c } ^ { \prime }$ 是完全随机的，因此 $\boldsymbol { u } \neq \boldsymbol { u } ^ { \prime \prime }$ 和 $u = u ^ { \prime \prime }$ 的概率一样都为 $1 / 2$ ，即

$$
\mathrm { P r } \Big [ B \Big ( g , g ^ { l } , g ^ { m } , g ^ { n } , T = R \Big ) = 0 \Big ] = \frac { 1 } { 2 }
$$

在选择性明文攻击的安全游戏中， $\mathbf { B }$ 的优势为

$$
A d \nu _ { B } = \frac { 1 } { 2 } \left( \operatorname* { P r } \left[ B \left( g , g ^ { l } , g ^ { m } , g ^ { n } , T = e \left( g , g \right) ^ { l m n } \right) = 0 \right] + \right) - \frac { 1 } { 2 } \ = \frac { \varepsilon } { 2 }
$$

由上可知挑战者解决DBDH问题的优势为 $\varepsilon / 2$ ，在DBDH假设下，证明提出的数据共享方案是安全的。

# 3.2抵抗用户窜谋攻击

本方案采用双因子身份验证机制，每个用户有其唯一ID和登录密码PW，解密时先进行用户登录，根据验证体制对用户身份进行第一道的判断，提高了攻击者破解合法用户身份信息伪装成合法授权用户的难度。通过身份验证后，用户分别将自己具有的属性私钥分量分别代入进行解密计算，验证用户私钥是否满足访问结构。该方案中用户只能知道自己是否具有访问秘密文件的条件，但不能获知自己能够满足访问结构的具体属性表达式，这就有效防止了多个非法用户或腐化用户窜谋，结合属性私钥获取解密密钥，获取共享文件，或者低授权用户进行越权盗取高级加密文件的风险。

# 4 验证

本实验代码基于pbc-0.5.14库[17]和CP-ABE工具包进行验证。实验结果如图1、2所示。

图1表示在共享的文件数为固定值的情况下(设 $\scriptstyle \mathbf { k } = 4 )$ 加密解密所需的时间随属性个数的变化。图2表示在属性个数一定的情况下（ $\scriptstyle \mathbf { N = } 3 0$ ）加密解密所需的时间随文件个数的变化。对于变化的属性数目和文件个数，属性个数和文件个数的实验仿真数据取值分别为 $\mathrm { N } { = } \{ 1 0 , 1 5 , 2 0 , 2 5 , 3 0 , 3 5 , 4 0 \}$ 和 $\scriptstyle \mathbf { k } = \{ 2 , 4 , 6 , 8 \}$ 。

由实验验证可知当共享文件数为固定值时，随着属性的增多，本方案在加密时是优于原方案的，但在解密时效果不如原方案。当属性值为固定值时，随着文件个数的增多，本方案在加密解密时的效率与原方案无太大差别。因此改进的方案在提高安全性的同时未对加密解密效率产生过多影响。

![](images/b7207978b62ce66959b53f9d058611409394899871d039ab9f9a32761e85d7a1.jpg)  
图1加/解密时间与属性个数变化关系

![](images/0849cb4fb5b4f0a67488947b5acb895be2b9a3ed6a5d852ac5b42bf4632dfe39.jpg)  
图2加、解密时间与文件个数变化关系

# 5 结束语

通过实验结果验证，本方案在不影响加密解密效率的前提下，解决了用户信息易被泄露、文件易被窃取的风险，并且结合双因子身份认证机制实现对用户身份的匿名认证，使得方案更加高效提高了加密算法的安全性。研究成果在DBDH假设下被证明是安全的。

参考文献：   
[1]KhalilIM, Khreishah A,Azeem M. Cloud computing security: Asurvey [J]. IEEE Computers,2014,3(1): 1-35.   
[2]Bethencourt J，Sahai A，Waters B. Ciphertext-policy atribute-based encryption.[J] IEEE Symposium on Security & Privacy,20o7,2008 (4): 321-334.   
[3]Li J,Wang Q,Wang C,et al. Enhancing atribute-based encryption with attribute hierarch[J].Mobile Net works and Applications,2011,16(5): 553- 561.   
[4]Wang G J,Liu Q,Wu J,et al. Hierachical attribute-based encryption and scalable user revocation for sharing data in cloud servers [J].Computers & Security,Advances in Network and Sstem Security,2011,30(5): 320-331.   
[5]Hur J.Improving security and efficiency in attribute-based data sharing [J] IEEE Trans on Knowledgeand Data Engineering,2013,25(10): 2271-2282.   
[6] Green M, Hohenberger S,Waters B.Outsourcing the decryption of ABE ciphertexts [J]. Usenix Conference on Security2011,49 (3-4):34-34.   
[7]LaiL,Deng HR,Guan C,et al.Attribute-based encryption with verifiable outsourced decryption [J]. IEEE Trans on Information Forensics and Security,2013,8 (8): 1343-1354   
[8]Wang Shulan, Zhou Junwei,Yu Jianping,et al.Anovel file hierarchy access controlscheme using atribute-based encryption [J]. Applied Mechanics and Materials,2015,701-702: 911-918.   
[9]Yang W,Shieh S P.A Password authentication schemes with smart cards [J]. Computers& Security,1999,18 (8): 727-733.   
[10] Fan C, Chan Y, Zhang Z. Robust remote authentication scheme with smart cards [J].Elsevier Advanced Technology Publications,2005,24(8): 619- 628.   
[11] Das M, Saxena A, Gulati V.A dynamic ID-based remote user authentication scheme[J]. IEEE Trans on Consumer Electronics,2004,50 (2): 629-631.   
[12] Wang Ding，He Debiao,Wang Ping，et al. Anonymous two-factor authentication in distributed systems:certain goalsare beyond attainment [J].IEEE Trans onDependable& Secure Computing,2015,12(4): 428-442.   
[13] Nishde T, Yoneyama K,Ohta K. Atribute-based encryption with partially hidden encryptor-specified access structures [M].Berlin: Springer,2008: 111-129.   
[14]解理，任艳丽．隐藏访问结构的高效基于属性加密方案[J].西安电子 科技大学学报,2015,42(3):97-102.   
[15]宋衍，秦臻，刘凤梅，等．基于访问树的策略隐藏属性加密方案[J]. 通信学报,2015,36(9):119-126.   
[16]李新，彭长根，牛翠翠．隐藏树型访问结构的属性加密方案[J].密码 学报,2016,3 (5): 471-479.   
[17] LynnB.Thepairing-basedcryptography (PBC）library [EB/L] http://crypto. Stanford. edu/pbc/.