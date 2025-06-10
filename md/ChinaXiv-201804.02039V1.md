# 基于双线性对的k-匿名隐私保护方案研究

宋成，张亚东，彭维平，闫玺玺(河南理工大学 计算机科学与技术学院,焦作 454003)

摘要：针对移动互联网环境下位置服务的隐私保护问题，基于双线性对性质和k-匿名的思想，提出了一个高服务质量的隐私增强方案。通过终端在欧几里得距离环形区域内均匀生成2k个虚假位置，利用位置熵、位置分散度和地图背景信息从中筛选出k-1个虚假位置，进而达到更优的k-匿名效果。通过安全性分析，本方案不仅满足隐私性、匿名性、不可伪造性等安全特性，而且能够抗查询服务追踪攻击；仿真实验表明，本方案虚假位置节点选取具有更优的均匀度，同时在假节点生成和选取效率也有所提高。

关键词：基于位置的服务；双线性对；k-匿名；隐私保护中图分类号：TP309 doi:10.3969/j.issn.1001-3695.2017.11.0756

# Research on k-anonymous privacy protection scheme based on bilinear pairing

Song Cheng, Zhang Ya-dong, Peng Wei-ping, Yan Xi-xi (School of Computer Science and Technology Henan Polytechnic University,Jiaozuo 454003,China)

Abstract: Aimingatthe privacyprotectionproblemoflocationservice inmobile Internetenvironment,ahighqualityofservice privacy enhancement scheme based on bilinear pairing property and anonymity is proposed.The terminal generates $2 k$ evenly distributed false locations in thering area ofEuclidean distance.According to location entropy,location dispersion and map background information,the terminal screens superior $k { - } 1$ false locations from them to achieve better $\mathbf { k }$ -anonymity. Through the security analysis,thescheme notonlysatisfies theprivacy,anonymity,unforgeabilityetc.,butalsocanresist queryservice trackingatack.Thesimulationexperimentsshowthateselectionoffalsepositionnodesinthisschemehasabeteruniformity and the efficiency of the false node generation and selection is also improved.

ey words: location-based services; bilinear pairings; k-anonymity; privacy protection

# 0 引言

随着移动通信技术、定位技术及智能设备的迅猛发展，基于位置的服务[I\~3]（LBS）得到广泛的应用，越来越多的人受益于相关服务[4]。LBS应用服务系统已经涉及到各种领域，例如医疗，交通，社交网络、大众娱乐等。然而，基于位置的服务在为用户提供服务的同时，用户敏感数据信息可能被搜集，从而推测出用户个人隐私。如：用户位置信息统计，可推断出用户的家庭和单位地址；结合地图相关信息，可以推断出用户的健康状况，生活习惯和宗教信仰[5]。因此，位置服务中的用户隐私保护一直是国内外学者关注的焦点[6\~8]。

然而，在用户隐私保护技术中， $k \mathrm { . }$ 匿名[9是重要的技术之一，可以有效防止隐私的泄露，因此 $K -$ 匿名技术亦成为目前研究的热点。基于 $k \mathrm { . }$ 匿名的用户的隐私保护方案是由KIDO[10]等人在2005年首次提出。基本思想是：为用户生成多个虚假位置，然后将所选虚假位置和用户的真实位置一起发送到LBS服务器。以致攻击者和服务器均无法辨别用户的真实位置。LU等人在方案[11]中指出，如果虚假位置太过于集中，会降低用户的隐私保护程度，并提出了新的方案，将每个虚假位置均匀位于不同的圆形或矩形区域内，进而提高用户隐私保护程度。NIU等人[12]指出，上述方案均未考虑攻击者是否知晓背景信息，此信息会影响攻击者对用户的实际位置的推断概率。因此，他们提出一个新的解决方案：生成尽可能多地虚假位置，这些虚假位置与用户真实位置具有相同查询频率，从而加强用户的隐私保护。但该方案不适用于连续LBS服务请求查询，因为攻击者根据相邻查询时间和空间之间的联系，可以推断出用户的真实位置。

XU等人在文献[13]中通过在最小边界圆中选择不包含前一匿名区内所有其他用户的方法来生成匿名集合，并根据匿名集合大小来衡量用户位置隐私保护的强度。在文献[14]中，提出一个基于用户感觉的连续LBS 服务请求的隐私保护模型，让用户根据隐私保护的程度构建公共区域。但这两个方案均不能抵抗查询跟踪攻击。WANG等人在文献[15]中指出在连续的位置服务请求中，用户可能在不同位置隐私保护级别不同，提出一个位置感知的位置隐私保护方案。LI等[16指出，如果使用其他用户的历史足迹构建匿名区域，会造成匿名区域太大，进而降低服务质量。提出一个连续LSB请求环境下的需求感知位置隐私保护方案，通过删除最远的足迹缩小匿名区域范围，提高服务质量。但是，在用户预定/预测位置之外进行服务请求，该方案仍不能抵抗查询跟踪攻击。SCHLEGEL等人[17基于密文匹配思想，提出了基于密文的位置隐私保护方案，在确保第三方可信的情况下，可以抵抗查询跟踪攻击。针对以上不足之处，本文结合双线性对理论知识和 $k \mathrm { . }$ 匿名的思想，提出了一个安全加强的用户位置隐私保护的方案，通过移动终端在欧几里得距离环形区域内均匀生成 $2 k$ 个虚假位置，然后利用位置熵、位置分散度和地图背景信息从 $2 k$ 个虚假位置中筛选出 $k - 1$ 个更优的虚假位置，进一步提高虚假位置均匀度，进而达到更优的 $k \mathrm { . }$ 匿名效果。

# 1 预备知识

# 1.1位置隐私保护系统结构

本文在-匿名思想的基础上，增加了一个混淆服务器，如下图1所示，系统主要由三部分实体组成：移动终端、混淆服务器、位置信息服务器。各部分的作用如下：

移动终端：移动终端具有两个的作用，一是向混淆服务器发送用户假名生成请求并验证假名结果的有效性；二是生成并筛选虚假位置节点，向位置信息服务器发送位置查询请求，并接收来自位置信息服务器的查询结果。

混淆服务器：在匿名位置隐私保护中，通常需要配置一个混淆服务器，为移动终端用户生成假名并将结果发送给移动终端。

位置信息服务器：是位置隐私保护系统的核心部分，负责处理来自移动终端的匿名化查询；并将查询结果返回给移动终端。

# 1.2双线性对

设 $( G _ { 1 } , + )$ 为阶为素数 $q$ 的加法循环群， $( G _ { 2 } , \times )$ 为阶为素数$q$ 乘法循环群， $P$ 为 $G _ { 1 }$ 的生成元。双线性映射 $e : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 满足以下性质：

（1）双线性：对于：$\forall a , b \in Z _ { q } ^ { * } , P , Q \in G _ { 1 } , e ( a P , b Q ) = e ( P , Q ) ^ { a b }$ （2）非退化性： $\exists P , Q \in G _ { 1 }$ ，满足 $e ( P , Q ) \neq 1$ ；（3）可计算性：对于任意 $P , Q \in G _ { _ { 1 } }$ ，存在有效的算法计算 $^ { e ( P , Q ) }$ ；

# 1.3 位置熵

给定一个包含 $k$ 个虚假位置的匿名区域，用户在某一虚假位置 $i$ 的概率是 $Y _ { i }$ ，那么它的位置熵值为：

$$
Y _ { i }
$$

在移动终端用户向LBS服务器进行服务请求过程中，隐私级别通过单个用户隐私度量标准来衡量。假设匿名区域内 $k$ 个候选虚假位置节点， $k$ 个虚假位置的查询概率分别为$W _ { i } ( i = 1 , 2 \cdots k )$ ，那么每个位置成为真实位置的概率为：

![](images/d59c966afba3263205fde5d62dd4ca27cd4f9a0fa6b8302910ccba837438b74c.jpg)  
图1位置隐私保护系统模型

2K

因此，利用式（1）和（2）可计算出节点位置熵，即攻击者推导出真实位置的信息量。候选位置节点熵值越高，隐私保护水平越高。显然，当所有的 $Y _ { i }$ 相等时，位置节点位置熵值最大，隐私保护水平最高。

# 1.4位置分散度

若存在多个虚假位置节点集合中的节点位置熵相等且均是最大值时，将需要利用位置分散度对它们再次进行筛选。因为虚假位置节点集合的位置分散度越大，则表明其所形成的区域面积就越大，这样可以避免由于生成的假节点过于集中，导致攻击者能够推测出用户真实位置所在的区域而造成位置隐私泄露。通常采用虚假位置节点对之间的距离之积来衡量位置分散度。

如图2所示，假设 $o$ 是用户的真实位置， $p$ 为已选出的虚拟位置，通过构造椭圆从两个候选位置 $\mathbf { \Sigma } _ { m }$ 和 $n$ 中选择出第三个虚拟位置。将 $o$ 和 $p$ 作为椭圆的两个焦点，并将 $\mathbf { \Sigma } _ { m }$ 和 $n$ 构造到椭圆上。因为 $m o + m p = n o + n p$ ，无法根据虚拟节点对之间的距离之和确定选择哪个节点，但由于 $m o \times m p > n o \times n p$ ，最终选择节点 $\mathbf { \Sigma } _ { m }$ 作为虚拟位置而不是节点 $n$ ，因为节点 $\mathbf { \Sigma } _ { m }$ 的分散度更大。

![](images/94f9c47590118f520b7218004f20cffc72d9d95330246b9d171e09104d197806.jpg)  
图2候选节点筛选示意图

# 2 基于双线性对的K-匿名隐私增强方案

本方案主要包括四个阶段：系统初始化阶段、用户注册阶段、假位置生成与选取阶段和位置服务请求阶段。

# 2.1 系统初始化

系统初始化阶段主要生成系统参数，具体步骤如下：

Step1: $G _ { \imath }$ ， $G _ { 2 }$ 是两个阶数为素数 $q$ 的循环群，其中 $G _ { \imath }$ 为加法循环群， $G _ { 2 }$ 为乘法循环群， $P$ 是 $G _ { \mathrm { { \scriptscriptstyle 1 } } }$ 的生成元。$\mathbf { e } : G _ { 1 } \times G _ { 1 } \to G _ { 2 }$ 表示一个双线性映射。 $\boldsymbol { Z } _ { p } ^ { * }$ 表示模 $q$ 的整数乘法群。

Step2：定义2个安全哈希函数 $H _ { 1 } , H _ { 2 }$ 和一个基于椭圆曲线密码体制的加密函数 $e n c ( )$ 。其中 $H _ { 1 } \colon \{ 0 , 1 \} ^ { * } \to \{ 0 , 1 \} ^ { k }$ ，H:{0,1}→G[，{0,1}\*表示任意长度的二进制串。

Step3：混淆服务器选取系统主密钥 $s \in Z _ { p } ^ { * }$ ，计算其公共密钥为： $P _ { \mathrm { { A } } } = s P$ 。

Step4：混淆服务器保存系统主密钥 $s$ ，公开系统参数：

$$
\{ G _ { 1 } , G _ { 2 } , e , k , P , P _ { \scriptscriptstyle A } , H _ { 1 } , H _ { { } _ { 2 } } , e n c ( \ k ) \} \_
$$

# 2.2用户注册

由于本方案是基于 $k \mathrm { . }$ 匿名思想而设计的，因此，用户注册阶段，通过混淆服务器对用户的身份进行匿名化，具体步骤如下：

Step1:用户 $U s e r$ 随机选择一个秘密值 $r _ { \boldsymbol { u } } \in Z _ { p } ^ { * }$ ，并将 $r _ { u }$ 和用户真实身份 $I D$ 作为注册请求消息发送给混淆服务器，请求注册。

Step2：混淆服务器收到注册请求后，为用户计算虚假身份：$P I D _ { u } = e n c ( H _ { 1 } ( I D \parallel r _ { u } ) )$ ，然后计算 $\mathcal { Q } _ { \mathrm { u } } = H _ { 2 } ( P I D _ { u } , r _ { u } P ) , \ X _ { u } = s Q _ { u }$ 并将 $\{ P I D _ { u } , X _ { u } \}$ 返回给用户 $U s e r$ 。

Step3：用户 $U s e r$ 收到消息 $\{ P I D _ { u } , X _ { u } \}$ 后，计算$\tilde { Q _ { \mathrm { u } } } = H _ { \scriptscriptstyle 2 } ( P I D _ { \scriptscriptstyle u } , r _ { \scriptscriptstyle u } P )$ 并判断 $\mathsf { e } ( X _ { u } , P ) { \overset { ? } { = } } e ( { \overset { \sim } { Q } } _ { u } , P _ { A } )$ 是否成立。如果等式成立，注册成功；否则，返回 Step1重新注册。

# 2.3假位置生成与选取

本阶段通过用户移动终端生成虚假位置，并从 $2 k$ 个虚假位置中选取最优的 $k - 1$ 个位置，具体步骤如下：

Stepl：移动用户终端以用户 $U s e r$ 的真实位置 $L o c _ { U s e r }$ 为中心点，采用矩形区域内均匀分布随机点算法生成一个假位置$L o c _ { i }$ ，根据地图的背景信息判断该位置，若为山川、河流等位置，则放弃该位置从新生成；否则，计算 $L o c _ { U s e r }$ 和 $L o c _ { i }$ 两位置之间的欧几里得距离：dis(LocUser,Loci）。

Step2：移动用户终端判断不等式（204 $R _ { \mathrm { m i n } } < d i s ( L o c _ { U s e r } , L o c _ { i } ) < R _ { \mathrm { m a x } }$ 是否成立。如果满足，让 $c _ { i } = L o c _ { i }$ ，并将其加入位置集合 $C = \{ c _ { 1 } , c _ { 2 } , c _ { 3 } , . . . . . . , c _ { i - 1 } \}$ ，即$C = \{ c _ { 1 } , c _ { 2 } , c _ { 3 } , . . . . . . , c _ { i - 1 } \} \cup \{ c _ { i } \}$ ；如果不满足，重新返回 Step1。其中 $R _ { \mathrm { m i n } }$ 和 $R _ { \operatorname* { m a x } }$ 分别表示中心点到新生成假节点的最短距离和最长距离。

Step3：若 $i < 2 k \ , \quad i = i + 1$ ，并返回 Stepl；若 $\scriptstyle { i = 2 k }$ ，则执行下一步。

Step4：假设假位置节点集合 $c$ 内假位置的查询概率分别为$W _ { i } ( i = 1 , 2 \cdots 2 k )$ ，根据式（2）计算出每个假节点位置成为真实节点位置概率 $Y _ { i } \circ Y _ { i }$ 越接近真实位置 $L o c _ { U s e r }$ 的查询概率，位置熵 $H ( x )$ 越高，隐私保护水平就越高。根据该原则，从 $2 k$ 个假位置中选取最优的 $k - 1$ 个假位置 $\{ L o c _ { 1 } , L o c _ { 2 } { \cdot \cdot \cdot } L o c _ { k - 1 } \}$ 。

注：Step4 中若在临界位置存在并列无法排除的假节点，即若出现候选假位置 $L o c _ { k - 1 }$ 和 $L o c _ { k }$ 成为真实节点位置概率 $Y _ { i - 1 }$ 和 $Y _ { i }$ 相等的情况，移动终端根据位置分散度原则，判断不等式

$$
\begin{array} { r l } & { d i s ( L o c _ { { U s e r } } , L o c _ { { k - 1 } } ) \times d i s ( L o c _ { { p } } , L o c _ { { k - 1 } } ) ^ { ? } } \\ & { d i s ( L o c _ { { U s e r } } , L o c _ { { k } } ) \times d i s ( L o c _ { { p } } , L o c _ { { k } } ) } \end{array}
$$

是否成立，若成立，则选择 $L o c _ { k - 1 }$ 为候选位置，反之选择 $L o c _ { k }$ （204号为候选位置，其中 $L o c _ { U s e r }$ 为用户 $U s e r$ 的位置， $L o c _ { p }$ 为已选的假位置。最终选择最优的假位置集合CEnd ={c,C,C3,.,.Ck-}。

Step5：最优的假位置集合 $C _ { E n d }$ 内各位置节点分别进行用户注册，为每个假位置分别生成匿名用户 ID: $P I D _ { i } \left( \phantom { } 0 < i \leq k - 1 \right)$ 。

# 2.4位置服务请求

本阶段通过移动终端 $U s e r$ 随机选取一位置节点作为代表节点向LBS服务器发送服务请求，具体的请求步骤如下：

Step1：用户从包括真实位置节点在内的 $k$ 个位置节点中随机选取一位置节点 $c _ { j }$ （ $0 < j \leq k ^ { \mathrm { ~ } } \}$ 。

Step2：聚合 $k$ 个节点的假身份 $P I D _ { i }$ 、节点位置 $L o c _ { i }$ 以及查询内容 $Q _ { i }$ ，形成一个查询集合：$\{ M s g \{ ( P I D _ { 1 } , L o c _ { 1 } , Q _ { 1 } ) , ( P I D _ { 2 } , L o c _ { 2 } , Q _ { 2 } ) . . . . . . . . , ( P I D _ { k } , L o c _ { k } , Q _ { k } ) \} \}$ ，以$c _ { j }$ 位置为代表向LBS 服务器发送服务请求。

Step3：LBS服务器接收到服务请求后，将查询结果集$R s = \{ r s _ { 1 } , r s _ { 2 } , r s _ { 3 } , . . . . . . . , r s _ { k } \}$ 返回给用户。

Step4：用户收到 $R s$ 后，从中选取出用户需求的真实信息$r s _ { U s e r }$

# 3 安全性分析

方案从隐私保护、匿名性、不可伪造性和查询服务跟踪四个方面进行安全性分析。

# 3.1隐私保护

本方案通过设置最大半径和最小半径，并且限制最小半径的约束条件。同时再加上虚拟节点的产生是均匀的，在请求位置服务是时随机选取一个节点作为代表节点进行服务请求。这样即使攻击着获取了请求服务的信息也无法得知真实用户位置的信息。在用户注册阶段，所有用户都通过加密算法enc(对其节点真实身份 $I D$ 进行加密形成虚假身份$P I D _ { u } = e n c ( H _ { \mathrm { 1 } } ( I D \parallel r _ { u } ) )$ ，攻击者无法从 $P I D _ { u }$ 推导或获取节点的真实信息，从而保护了用户信息隐私。在服务请求阶段由于随机选取一个节点作为代表节点发送服务请求。具有随机性，降级攻击者辨别出到底哪个是真实用户的查询信息的概率。进而保护了真实用户查询信息的安全。

# 3.2 匿名性

本方案在用户注册阶段，通过加密算法 $e n c ( )$ 对所有节点真实身份 $I D$ 进行加密形成虚假身份 $P I D _ { u } = e n c ( H _ { \scriptscriptstyle 1 } ( I D \parallel r _ { u } ) )$ ，攻击者无法从 $P I D _ { u }$ 推导或获取节点的真实信息，实现匿名的效果。同时在虚假位置的生成和选取阶段，基于 $\ K -$ 匿名的思想，采用匿名区域内均匀分布随机点算法在欧几里得距离环形区间内选取 $2 K$ 个虚假节点，然后根据位置熵与位置分散度的原则从$2 k$ 个虚假节点内选取最优的 $k - 1$ 个虚假节点，实现混淆的效果。在服务请求阶段，用户从 $k$ 个节点中随机选择一个节点作为代表元素向LBS服务器发送服务请求，攻击者即使获得请求数据包，也无法确认信息是否来自真实节点，进一步增强了用户匿名效果。

# 3.3不可伪造性

在基于求解椭圆曲线离散对数难题及混淆服务器的前提下，攻击者无法冒充混淆服务器伪造用户注册信息。在用户注册阶段，混淆服务器为用户的真实身份进行加密生成可验证性的假身份 $P I D _ { u }$ ，混淆服务器返回给注册用户信息 $\{ P I D _ { u } , X _ { u } \}$ 后，用户需要计算 $\tilde { Q _ { \mathrm { u } } } = H _ { \scriptscriptstyle 2 } ( P I D _ { \scriptscriptstyle u } , r _ { \scriptscriptstyle u } P )$ 并判断等式 $\mathsf { e } ( X _ { u } , P ) \overset { ? } { = } e ( \overset { \sim } { \boldsymbol { Q } _ { u } } , P _ { A } )$ （20是否成立。若攻击者冒充混淆服务器伪造用户注册信息，在没有获得混淆服务器私钥 $s$ 的情况下，该等式无法成立。如果攻击者设法获取混淆服务器私钥 $s$ ，需要利用混淆服务器公钥信息 $( P , P _ { A } )$ ，通过 $P _ { \mathrm { { A } } } = s P$ 推导私钥 $s$ ，即面临求解椭圆曲线离散对数难题。

# 3.4抵抗查询追踪攻击

查询追踪攻击也称为连续查询攻击，其原理是攻击者根据不同时刻某一用户发出的连续查询，获取不同时刻内匿名区域包含的用户集，通过计算不同匿名区域的用户集的交集推断出发出查询的用户。在本方案中由于所选虚假节点均是均匀产生的，而且根据位置熵、位置分散度以及地图背景信息等原则，所选虚假节点与真实节点相似度高，形成的匿名区域面积大，有效抵制查询追踪攻击。而且每次发出LBS 服务请求都会从 $k$ 个位置节点中随机选取某一个元素作为代表元素发出请求信息，攻击者更无法通过用户连续查询请求节点的交集获取真实节点。

通过以上分析，本方案与相关文献方案的安全分析比较结果如表1所示。

表1安全性比较  

<html><body><table><tr><td>方案</td><td>文献[6]</td><td>文献[7]</td><td>文献[8]</td><td>本文方案</td></tr><tr><td>位置隐私</td><td>√</td><td>√</td><td>√</td><td>√</td></tr><tr><td>查询隐私</td><td></td><td>√</td><td>√</td><td>√</td></tr><tr><td>用户信息隐私</td><td></td><td></td><td></td><td>√</td></tr><tr><td>匿名性</td><td>√</td><td></td><td>√</td><td>√</td></tr><tr><td>不可伪造性</td><td></td><td></td><td></td><td>√</td></tr><tr><td>查询追踪攻击</td><td></td><td></td><td></td><td>√</td></tr></table></body></html>

# 4 仿真实验

本文仿真实验环境为：CPU：Inteli5 处理器，内存：8G。操作系统：Windows764位，仿真软件：MATLAB 软件。假设在一个具有理想的网络环境进行仿真实验。本实验将随机选择一个节点作为用户的真实位置，然后从符合用户需求的虚假位置生成效率和位置分布均匀度两个方面进行仿真。

虚假位置生成算法性能指标主要体现在效率和位置均匀度相同的实验环境下，通过对比传统方案、CirDummy方案和GirdDummy方案得出以下结论。如图3所示，生成符合用户条件虚假位置所需要的时间与匿名度 $k$ 成线性关系，随着匿名度$K$ 的增加，生成符合用户条件虚假位置生成所需时间也在逐步增加。这是由于随着匿名度 $k$ 的增加，生成的虚假位置数量也随着增多，需要判断的符合用户需求虚假位置个数增加，进而生成时间相应增加。通过仿真实验发现，当 $k \leq 5$ 时，本方案所生成的符合条件的虚假位置的效率与传统方案算法效率接近；当 $k > 5$ 时，本文方案所生成的符合条件的虚假位置的效率与传统方案相比，优势越来越明显，由于传统方案算法生成虚假位置在顺时针旋转的夹角 $\theta$ 内，既满足 $\theta = 2 \pi / \left( k - 1 \right)$ ，随着匿名度 $k$ 的增加，夹角 $\theta$ 越来越小，虚假位置生成在 $\theta$ 内的概率越来越小。因此，传统方案生成符合条件的虚假位置算法随着匿名度 $k$ 的增加效率越来越明显低于本文方案。同时对比CirDummy方案和GirdDummy方案，随着匿名度 $k$ 的增加，本文方案的效率也是越来越高于 CirDummy 方案和 GirdDummy方案。

![](images/33ad11d7e23681e505bb4458aca15de88e7c835029115d3e155e599b375dd05d.jpg)  
图3匿名度 $\mathbf { k }$ 与所选位置生成时间的关系

位置的均匀度代表所选的位置与真实位置越相似程度，其均匀程度越高，虚假节点分布越均匀，攻击者找到真实位置的几率越小。位置分布均匀度用 $V = f / k$ 表示，其中 $f$ 表示包含真实位置和虚假位置的最小矩形区域面积， $k$ 表示匿名度。显然，在 $f$ 一定的情况下，位置均匀度随着匿名度 $k$ 的增加而降低。本仿真实验是在最小区域半径为 $0 . 1 \mathrm { k m }$ ，最大区域半径为$0 . 1 5 \mathrm { k m }$ 内进行位置的选择。本方案通过与传统方案和CirDummy方案在同等环境下仿真对比结果如图4所示，由于本方案采用位置熵、位置分散度和地图背景信息筛选每个虚假位置，因此，本方案位置分布均匀度始终优于传统生成算法，避免了因位置节点分布集中而导致匿名区域面积缩小的情况，进而增加了攻击者确定用户的真实位置的难度。在位置均匀度仿真实验中之所以没有与GirdDummy方案进行对比分析是因为本文实验是在环形区域选取虚假节点，而GirdDummy 方案与之不符合。

![](images/e37023ec82a15becc0fe6c7d240d3f80458f3b1cd81fc86f267d453129b0017d.jpg)  
图4匿名度k与位置分布分均匀度的关系

# 5 结束语

本文针对移动互联网中用户使用LBS服务的位置隐私保护问题，结合双线性对理论知识和 $k \mathrm { . }$ -匿名的思想，提出了一个安全加强的用户位置隐私保护的方案。方案通过移动终端在欧几里得距离环形区域内均匀生成 $2 k$ 个虚假位置，然后利用位置熵、位置分散度和地图背景信息从 $2 k$ 个虚假位置中筛选出$k - 1$ 个更优的虚假位置。通过安全性分析，本方案解决隐私性、匿名性、不可伪造性以及查询攻击等相关安全问题，安全性得到有效增强；通过仿真实验分析，当 $k \leq 5$ 时，本方案所生成的符合条件的虚假位置的效率与传统方案算法效率接近；当 $k > 5$ 时，具有更高的效率，同时方案具有更高的虚假位置均匀度，从而进一步的提高了用户隐私的保护程度。因此本方案在资源受限的移动互联网或物联网环境中LBS位置隐私保护领域有着重要的理论研究意义和应用价值。

# 参考文献：

[1]Tiwari S,Kaushik S,JagwaniP,etal.ASurvey on LBS: System Architecture, Trends and Broad Research Areas [M]// Databases in Networked Information Systems.Springer Berlin Heidelberg,2011:223-241.   
[2]Krumm,John.A survey of computational location privacy[J].Personal and Ubiquitous Computing,2009,13 (6):391-399.   
[3]Sun Yanming,Chen Min,Hu Long,et al.ASA:Against statistical attacks for privacy-aware users in Location Based Service [J].Future Generation Computer Systems,2016,70.   
[4]Xin Mingjun,Lu Manli,Li Wweimin.An adaptive collaboration evaluation model and its algorithm oriented to multi-domain location-based services [J]. Expert Systems with Applications,2015,42 (5): 2798-2807.   
[5]万盛，李凤华，牛犇等．位置隐私保护技术研究进展[J].通信学报. 2016, 37 (12): 125.   
[6]Talukder N,Ahamed S I. Preventing multi-query attck in location-based services [C]//ACMConference on Wireless Network Security.ACM,2010: 25-36.   
[7]Gao Sheng,Ma Jianfeng, Shi Weisong,et al. TrPF:A Trajectory PrivacyPreserving Framework for Participatory Sensing [J]. IEEE Transactions on Information Forensics & Security,2013,8(6): 874-887.   
[8]Mascetti S,Freni D,Betini C,et al. Privacy in geo-social networks: proximity notification with untrusted service providers and curious budies [J].The international Journal on Very Large Data Bases,2011,20(4): 541- 566.   
[9]Liu Xinxin,Liu Kaikai, Guo Linke,et al.A game-theoretic approach for achieving $\mathbf { k }$ anonymity in Location Based Services [C]//INFOCOM,2013 Proceedings IEEE.IEEE,2013:2985-2993.   
[10] Kido H,YanagisawaY,Satoh T.Protectionof Location Privacyusing Dummies for Location-based Services [C]// International Conference on Data EngineeringWorkshops.IEEE Computer Society,2005:1248.   
[11] Lu Hua,Jensen CS,Man LY. PAD: privacy-area aware,dummy-based location privacy in mobile services $[ \mathrm { C } ] / \AA$ ACM International Workshop on Data Engineering for Wireless and Mobile Access, Mobide 2008, June 13, 2008,Vancouver,British Columbia, Canada,Proceedings.DBLP,2008:16- 23.   
[12] Niu Ben,Li Qinghua,Zhu Xiaoyan,et al. Achieving $\mathbf { k }$ -anonymity in privacy-aware location-based services [C]/ IEEE INFOCOM. IEEE, 2014: 754-762.   
[13] Xu T,Cai Ying.Exploring Historical Location Data for Anonymity Preservation in Location-Based Services [C]// INFOCOM 2008.the, Conference on Computer Communications.IEEE. IEEE,2008: 547-555.   
[14] Xu T, Cai Ying.Feeling-based location privacy protection for location-based services [Cl//ACM Conference on Computer and Communications Security. ACM,2009: 348-357.   
[15] Wang Yu,Xu Dingbang,He Xiao,et al. L2P2: Location-aware location privacy protection for location-based services [C]// INFOCOM,2012 Proceedings IEEE.IEEE,2012: 1996-2004.   
[16] Li Xinghua, Wang Ermeng, Yang Weidong,et al. DALP: A demand-aware location privacy protection scheme in continuous location-based services [J] Concurrency & Computation Practice & Experience,2016,28 (4):1219- 1236.   
[17] Schlegel R, Chow C Y,Huang Q,et al. User-Defined Privacy Grid System for Continuous Location-Based Services [J]. IEEE Transactions on Mobile Computing,2015,14(10): 2158-2172.