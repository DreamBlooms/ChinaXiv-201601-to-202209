# 安全增强的智能电网轻量级匿名认证方案

丁志帆‘，胡洪波aʰ，杨庆余‘，肖思远a(湘潭大学a.自动化与电子信息学院;b.网络与信息管理中心，湖南 湘潭 411105)

摘要：现有的智能电网身份认证方案大多存在计算成本高和认证流程复杂的问题，不适用于智能电网中资源受限的智能设备。而一些轻量级的方案却存在各种安全漏洞，这些方案都无法在效率和安全性之间实现所需的权衡。针对上述问题，基于椭圆曲线加密算法设计了一个增强的可证明安全的智能电网轻量级匿名认证方案。引入辅助验证器，摆脱在认证阶段对于电力供应商的依赖，在保护智能电表真实身份的条件下实现网关和智能电表之间的相互认证。同时，可以通过伪身份对恶意智能电表进行身份的溯源和撤销。通过在随机预言模型下的安全性分析和仿真工具ProVerif证明了方案具备较高的安全属性。性能分析表明，所提方案能够满足智能电网环境下对于安全性和高效性的要求。

关键词：智能电网；身份认证；椭圆曲线；随机预言模型；ProVerif 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2022.03.0118

Security enhanced lightweight anonymous authentication scheme for smart grid

Ding Zhifana, Hu Hongboa, b, Yang Qingyua, Xiao Siyuana (a.ColegeofElectronicInformation&Automation,b.Network&InformationManagementCenter,Xiangtan University Xiangtan Hunan 411105, China)

Abstract:Most of theexisting smart grid authentication schemes suffer from high computational costs and complex authentication processes,which arenot suitable forresource-constrainedsmart devices in thesmart grid,while some lightweightschemes sufferfromvarious securityvulnerabilities,noneof whichcanachieve therequiredtrade-offbetween eficiency and security.To solve these problems,this paper designed an enhanced provably secure smart grid lightweight anonymous authentication scheme based on elipticcurve encryption algorithm.Introducing auxiliaryvalidator to get ridof therelianceonthe power supplier inthe authentication phase and toachieve mutual authentication between the gateway and the smart meter underthecondition ofprotecting the true identityof the smart meter.Inaddition,the schemecan trace and revokethe identityofmalicious smart meters through pseudo identity.Throughthe securityanalysis undertherandomoracle modeland simulation toolProVerifverifies thathe proposedschemehas highsecurityproperties.Performanceanalysis shows that the proposed scheme can meet the requirements for security and effciency in smart grid environment.

Key words: smart grid; identity authentication; elliptic curve; random oracle model; ProVerif

# 0 引言

传统的电力系统因其自身的局限性，已不足以应对新兴工业生产以及社会经济发展的挑战。智能电网作为下一代电力系统，将传感、计算和通信等先进技术嵌入电网中，以提供可行、高效、可持续、具有经济效益和安全的电力供应，显著提高现有电网的效率[1]。在发电端通过将可再生能源并入电网，智能电网可以实现更准确的监控、潮流优化和更环保的绿色能源发电[2。在用户端为了实现对用户用电量的实时监控，智能电表等智能计量基础设施被部署在智能电网中，每个用户都配备一个智能电表，用于定期收集用户的用电数据，网关定期聚合区域内一组用户的用电数据，电力供应商分析聚合的用电数据并动态更新价格以实施用户侧管理[3]。

尽管智能电网有许多优点，但它的互连性和动态性以及对信息通信技术和网络系统的高度依赖使得智能计量基础设施容易受到许多安全威胁，如中间人攻击、假冒攻击和重放攻击等各类已知攻击[4]。由于电力供应商，网关和智能电表之间的通信是双向流动的，攻击者能够从多个入口渗入智能电网系统并窃取用户的用电数据信息，并进一步入侵电力供应商的电力数据库。因此，网络安全成为智能电网最关键的问题[5]。然而，传统的网络安全技术如密码保护、反恶意软件和防火墙等都有其自身的局限性[。为了解决这些问题，需要将安全高效的认证机制集成到智能电网的通信系统中，以支持通信实体之间安全的信息交换，同时保护其隐私。身份认证和密钥协商方案是安全高效的认证机制，能够保障智能电网各通信方的远程安全通信，实现数据机密性、用户隐私和消息完整性，为智能电网提供可靠的电力服务。

为了应对智能电网中存在的安全问题，研究人员近年提出了许多适用于智能电网的身份认证和密钥协商方案，但仍存在着两个主要问题：

a)现有的方案大部分都被指出存在各种安全漏洞，容易遭受各类已知攻击，不能提供会话密钥的安全性或智能电表的匿名性，无法满足在智能电网环境下的安全需求。b)现有的一些方案由于使用了指数运算或双线性配对此类高开销的操作而导致了较高的计算和通信成本，而智能电表的资源十分有限，难以满足方案的需求。

最近，Gope等人[7提出一个空间数据聚合方案，用于在智能电网中安全获取电力需求，该方案包括两个阶段：认证和数据聚合。他们声称其方案是安全的，在认证阶段能够实现安全的认证和密钥协商，并且具备对已知攻击的抵抗力，是智能电网环境的最佳选择。但是，本文发现该方案无法抵抗密钥泄露伪装攻击，并且其会话密钥是不安全的，这会严重影响智能电网通信系统的安全性。

为了解决上述问题，本文基于椭圆曲线加密算法，提出一种新的且可证明安全的智能电网轻量级匿名认证方案，能够满足智能电网环境的安全需求，在性能上也更具优势。本文的主要贡献有：

a）对Gope等人方案中的认证阶段进行安全性分析，证明该方案无法抵抗密钥泄露伪装攻击,并且其会话密钥安全性薄弱。b）设计了适用于智能电网的身份认证和密钥协商方案，引入一个辅助验证器，使得电力供应商不介入方案的认证阶段。c）本文方案在消息认证时不暴露智能电表的身份信息，保证了智能电表的匿名性和不可追踪性，通过对称加密算法实现了轻量级的伪身份更新，特定情况下通过伪身份对恶意智能电表进行溯源和撤销。d）使用随机预言模型以及仿真工具ProVerif证明了会话密钥的安全性以及抵御各类已知攻击的能力，与相关方案对比分析显示所提方案在安全性，计算成本以及通信量三个方面都有优势。

# 1 相关研究

近年来已经提出了多种加密协议，包括数字签名、加密、数据聚合、安全数据存储和身份认证方案作为作为学术界和工业界保护智能电网安全的解决方案[8]，其中身份认证方案是保障智能电网数据安全和实施隐私保护的第一道防线，是智能电网部署的重要要求。2015年，Tsai和 $\mathrm { L o } ^ { [ 9 ] }$ 采用双线性配对提出了基于身份的签名方案和基于身份的加密方案，实现了服务提供商和智能电表的相互认证。2016年，Odelu等人[10]中指出Tsai和Lo的方案[9]无法保证智能电表秘密凭证的隐私和会话密钥的安全性，并提出了一个安全高效的认证密钥协商方案，成功解决了Tsai和Lo的方案中存在的潜在隐私泄露问题。2017年，Chen 等人[1]表明Odeul等人的方案[10容易遭受假冒攻击，并且可以通过密钥生成中心追踪智能电表。为了解决文献[10]中的问题，Chen等人改变了智能电表在密钥生成中心的注册方式，智能电表的身份在发送前被加密，并且智能电表的私钥不会泄露给密钥生成中心，因此不受密钥生成中心发起的各种潜在攻击的影响。然而，上述方案[9\~11]使用了双线性配对和指数运算，并且存在密钥托管问题，因此会产生较高的计算成本。

为了满足轻量级的需求，越来越多的研究人员采用椭圆曲线加密算法(ECC)构建智能电网认证方案。2016年，He等人[12]为了降低Tsai和Lo的方案[9]中使用双线性配对和指数运算而导致的高计算成本，提出了一个基于椭圆曲线加密算法的轻量级匿名密钥协商方案，在没有可信第三方的情况下实现智能电表和服务供应商的相互认证。2018年，Abbasinezhad等人[13]指出He等人的方案[12]无法抵抗已知会话的临时信息攻击和智能电表的临时秘密值泄露攻击，并提出了一个基于椭圆曲线加密算法的密钥协商方案，能够提供会话密钥的安全性并且解决了以往方案的密钥托管问题，然而被指出缺乏智能电表的匿名性[14]。2020 年，Garg 等人[15]提出了一种安全的身份认证方案，将完全散列Menezes-QuVanstone(FHMQV密钥交换机制和椭圆曲线加密算法相结合，能够抵御各类已知攻击，计算成本低，但是被证明无法实现智能电表的匿名性和不可追踪性[16]。2021年，Srinivas等人[17]结合椭圆曲线加密算法和 Schnorr 的签名方案设计了一种新的基于匿名签名的认证密钥交换方案，支持在初始部署后添加新的动态智能电表，但是被指出无法抵抗中间人攻击和假冒攻击，并且不提供匿名功能[18]。

为了保护智能电表的匿名性，伪身份生成技术也在不断发展。2021年，Azeem等人[19]提出了一种用于智能电网需求响应管理的轻量级认证密钥方案，使用哈希散列函数生成伪身份以确保智能电网设备的匿名性，并且支持伪身份的更新。然而，由于哈希散列函数的单向不可逆，他们的方案不支持伪身份的溯源。2022年，Safkhani等人[20]提出一种智能电网的认证和密钥协商方案，使用物理不可克隆函数(PUF)和对称加密算法构建用户的伪身份保证了匿名性。但是，他们的方案不支持伪身份的更新和溯源。Gope等人的方案[7在智能电表上传用户用电数据前，电力供应商，智能电表和第三方聚合器进行身份认证，确保通信实体的合法性。该方案使用对称加密算法构建伪身份以提供智能电表的匿名性，具备对常见已知攻击的抵抗力，并且使用低成本的加密原语实现了通信实体之间的轻量级认证。然而，本文通过安全性分析发现，Gope等人的方案无法抵抗密钥泄露伪装攻击，并且会话密钥安全性薄弱。

# 2 预备知识

本节主要介绍本文方案的困难性问题、系统模型等理解本文所需的知识。

# 2.1 困难性问题

椭圆曲线离散对数难题(ECDLP)：假设 $q$ 是一个大素数，$G$ 是一个阶为 $\boldsymbol { q }$ 的加法循环群，对于给定的 $P \in G$ 和 $a \cdot P \in G$ ，计算 $a \in Z _ { q } ^ { * }$ 是困难的。

椭圆曲线Diffile-Hellman 难题(ECDHP)：对于给定的$P , a \cdot P , b \cdot P \in G$ ，其中 $a , b \in Z _ { q } ^ { * }$ ，计算 $a , b \in Z _ { q } ^ { * }$ 是困难的。

# 2.2 系统模型

如图1所示，在已有模型[721]的基础上提出本方案的系统模型，该模型中有4个通信实体：电力供应商( $P S$ )，网关（GW），相应家庭局域网中的智能电表(SM)，辅助验证器(AV)。

![](images/1847a8ad157b6cef1e66ae99b0f6c63b57ff6c84ea351083540da5c48df957bb.jpg)  
图1系统模型Fig.1System model

a）电力供应商(PS)。它是整个智能电网的管理员，主要负责生成和发放安全参数，对来自网关的聚合用电数据进行监控和分析并调整电价，与文献[7,21]相比，本方案中电力供应商只提供注册服务，不介入智能电表和网关的身份认证和密钥协商。

b)网关(GW)。它具有庞大的存储空间和优秀的计算能力，收集并聚合来自其负责区域内家庭局域网的智能电表加密用电数据，将处理好的数据发送给电力供应商。这是一个诚实但对智能电表的加密用电数据好奇的半可信第三方实体，收到辅助验证器的用电数据聚合请求后，对其进行身份认证，认证通过即发起与智能电表的相互认证并建立会话密钥。

c）智能电表(SM)。它是智能电网的终端设备，负责定期收集并加密用户的用电数据，这是一种资源受限的智能设备，存储空间和计算能力有限。

d)辅助验证器(AV)。它是一个第三方智能防窜改设备，向电力供应商注册获取相关安全参数，收到电力供应商的用电数据收集指令后，向网关发送用电数据聚合请求，网关需对其认证后方才同智能电表协商会话密钥。

# 2.3安全目标

一个安全高效的智能电网身份认证和密钥协商方案需为通信实体提供良好的安全性，应实现以下安全目标：

a）相互认证：为确保智能电表的数据上传给授权合法的网关以及网关接收来自合法智能电表的加密用电数据，在智能电表和网关之间应能提供相互认证。b）智能电表的匿名性不可追踪性：确保攻击者无法追踪到智能电表的真实身份以及智能电表在通信网络中的任何活动踪迹。c）会话密钥的前向安全性：即使攻击者获得网关和智能电表的长期秘密参数，也能确保先前已建立会话密钥的安全性。d)抵抗密钥泄露伪装攻击：即使网关或智能电表一方的私钥泄露，攻击者也无法伪装成私钥泄露方同另一方进行密钥协商。e）抵抗各类已知的攻击：能够抵抗假冒攻击，重放攻击，中间人攻击和智能电表临时秘密值泄露攻击。

# 2.4攻击者模型

本文结合Dolev-Yao 威胁模型和CK攻击者模型，构造了一个强大的攻击者，其在概率多项式时间内具有以下能力：

a）A可以任意窃听，拦截，修改，删除，注入通信通道上的消息。b）A可以获取系统先前的会话密钥。c）在评估对密钥泄露伪装攻击的抵抗时， $A$ 可以获取通信实体的私钥。

# 3 Gope等人方案的安全性分析

在本节中，回顾了Gope 等人方案的认证阶段，并分析该方案存在的安全漏洞。

# 3.1Gope 等人方案认证阶段的回顾

电力供应商(PS)为家庭局域网内的每个智能电表( $\cdot \ s M _ { i }$ ）  
生成伪身份 $P I D _ { i }$ 和私钥 $k _ { i }$ ，并与第三方聚合器(TPA)共享私  
钥 $K _ { a s }$ 。在收集用户用电数据聚合前，电力供应商,第三方聚  
合器,智能电表进行三方之间的相互认证，下面是具体过程。a) $\boldsymbol { S } \boldsymbol { M } _ { i }$ 生成随机数 $\boldsymbol { N _ { s } }$ ，计算 $V _ { 0 } = h \{ { P I D } _ { i } \parallel { N } _ { s } \parallel { k } _ { i } \}$ ，将消息  
$M _ { { \scriptscriptstyle A _ { i } } } : \{ P I D _ { i } , N _ { s } , V _ { 0 } \}$ 发送给TPA。b） $T P A$ 生成随机数 ${ { N } _ { a } }$ ,计算 $V _ { 1 } = h \{ I D _ { A } \parallel N _ { a } \parallel K _ { a s } \}$ ，发送消息  
$M _ { A _ { 2 } } = \{ ( P I D _ { i } , N _ { s } , V _ { 0 } ) \| ( I D _ { A } , N _ { a } , V _ { 1 } ) \}$ 给 $P S$ 。c） $P S$ 依据伪身份 $P I D _ { i }$ 在数据库中找寻对应 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 的真实  
身份 $I D _ { S M _ { i } }$ ，并验证 $V _ { 0 }$ 和 $V _ { 1 }$ 的正确性，验证通过则表明 $P S$ 认证  
了 $S M _ { i }$ 和 $T P A$ 的身份，为 $S M _ { i }$ 生成新的伪身份 $P I D _ { i } ^ { n e w }$ ，计算  
$T = h ( I D _ { S M _ { i } } \parallel K _ { a s } \parallel N _ { s } )$ ， $x = h ( k _ { i } \| T \| N _ { s } ) \oplus h ( K _ { a s } \| N _ { a } )$ ， $y = h ( T \| N _ { s } \| k _ { i } ) \oplus$   
${ \cal N } _ { a }$ ， $z = h ( T \| I D _ { S M _ { i } } \| k _ { i } ) \oplus P I D _ { i } ^ { n e w }$ ， $V _ { 2 } = h ( K _ { a s } \parallel N _ { a } \parallel x )$ ， $V _ { 3 } = h ( T \| y \| z \| k _ { i } )$ ，  
发送消息 $M _ { A _ { 3 } } : \{ x , y , z , V _ { 2 } , V _ { 3 } \}$ 给 $T P A$ 。d)TPA验证 $V _ { 2 }$ 的正确性，验证通过后计算  
$\begin{array} { l } { { \displaystyle T K = x \oplus h ( K _ { a s } \parallel N _ { a } ) } } \end{array}$ ，生成会话密钥 $k h _ { i } = h ( T K \| N _ { a } \| N _ { s } )$ ，生成一组  
$\boldsymbol { S } \boldsymbol { M } _ { i }$ 的临时身份 $T I D _ { i q } = \{ t i d _ { i 1 } , ~ t i d _ { i 2 } , { \cdots } , t i d _ { i q } \}$ ，使用 $k h _ { i }$ 加密 $T I D _ { i q }$ 即  
$T I D _ { i q } ^ { * } = E _ { k h _ { i } } [ T I D _ { i q } ]$ ，计算 $V _ { 4 } = h ( T I D _ { i q } ^ { * } \parallel k h _ { i } \parallel I D _ { A } )$ ，存储 $\{ T I D _ { i q } , k h _ { i } \}$ ，并发  
送消息 $M _ { A _ { 4 } } : \{ ( y , z , V _ { 3 } ) \| ( T I D _ { i q } ^ { * } , V _ { 4 } ) \}$ 给 $S M _ { i }$ □e） $S M _ { i }$ 计算 $T = h ( I D _ { S M _ { i } } \parallel K _ { a s } \parallel N _ { s } )$ ，验证 $V _ { 3 }$ 的正确性，验证通  
过即认证了 $P S$ 的身份，计算 $N _ { a } = h ( T \lVert N _ { a } ) \oplus k _ { i } \oplus y$ ，  
$\mathit { T K } = h ( k _ { i } \| T \| N _ { s } )$ ， $k h _ { i } { = } h ( T K \parallel N _ { s } \parallel N _ { a } )$ ， $P I D _ { i } ^ { n e w } = h ( T \mid \mid I D _ { S M _ { i } } \mid \mid k _ { i } ) \oplus z$ ，

验证 $V _ { 4 }$ 的正确性，验证通过即认证了 $T P A$ 的身份，最后 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 使用 $k h _ { i }$ 解密 $T I D _ { i q } ^ { * }$ 获得 $T I D _ { i q }$ ，存储参数 $\{ P I D _ { i } ^ { n e w } , T I D _ { i q } , k h _ { i } \}$ 。

# 3.2Gope 等人方案的安全漏洞

本节展示Gope等人方案的认证阶段无法抵抗2.4节构建的攻击者 $A$ 进行的密钥泄露伪装攻击，且无法提供会话密钥的安全性。攻击者 $A$ 窃听 $T P A$ 和 $S M _ { i }$ 以及 $T P A$ 和 $P S$ 之间的通信通道，并获取参数 $\{ P I D _ { i } , N _ { s } , V _ { 0 } \}$ 和 $\{ I D _ { A } \}$ ，根据密钥泄露伪装攻击的假设[22],攻击者可以获取 $P S$ 和 $T P A$ 的共享私钥 $K _ { a s }$ ，伪装成 $T P A$ ，同 $P S$ 进行会话。具体攻击过程如下。a) $A$ 窃听并拦截消息 $M _ { A _ { 1 } } : \{ P I D _ { i } , N _ { s } , V _ { 0 } \}$ 和 $\{ I D _ { A } \}$ ，生成随机数 $N _ { A }$ ，计算 $V _ { A } = h ( I D _ { A } \parallel N _ { A } \parallel K _ { a s } )$ ,发送消息 $M _ { A _ { 2 } } = \{ ( P I D _ { i } , N _ { s } , V _ { 0 } ) \|$ $( I D _ { A } , N _ { A } , V _ { A } )  \}$ 给 $P S$ 。b） $P S$ 依据伪身份 $P I D _ { i }$ 在数据库中找寻对应 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 的真实身份，并验证 $V _ { \mathrm { { 0 } } }$ 和 $V _ { A }$ 的正确性，验证通过则表明 $P S$ 认证了$S M _ { i }$ 和 $A$ 的聚合器身份，为 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 生成新的伪身份 $P I D _ { i } ^ { n e w }$ ，计算$T = h ( I D _ { S M _ { i } } \parallel K _ { a s } \parallel N _ { s } )$ ， $x = h ( k _ { i } \| T \| N _ { s } ) \oplus h ( K _ { a s } \| N _ { A } )$ ， $y = h ( T \| N _ { s } \| k _ { i } ) \oplus$ $N _ { A }$ ， $\begin{array} { r } { z = h ( T \parallel I D _ { S M _ { i } } \parallel k _ { i } ) \oplus P I D _ { i } ^ { n e w } , V _ { 2 } = h ( K _ { a s } \parallel N _ { A } \parallel x ) } \end{array}$ ， $V _ { 3 } = h ( T \| y \| z \| k _ { i } )$ ，发送消息 $M _ { A _ { 3 } } : \{ x , y , z , V _ { 2 } , V _ { 3 } \}$ 给 $A$ 。c) $A$ 验证 $V _ { 2 }$ 的正确性，验证通过后计算 $T K = x \oplus h ( K _ { a s } \parallel N _ { A } )$ ，生成会话密钥 $k h _ { i } = h ( T K \parallel N _ { A } \parallel N _ { s } )$ ，伪造一组 $S M _ { i }$ 的临时身份$T I D _ { i A q } = \{ t i d _ { i A 1 } , t i d _ { i A 1 } , \cdots , t i d _ { i A q } \}$ ，使用 $k h _ { i }$ 加密 $T I D _ { i A q }$ 即 $T I D _ { i A q } ^ { * } = E _ { k h _ { i } } [ T I D _ { i A q } ]$ ，计算 $V _ { 4 } = h ( T I D _ { i A q } ^ { * } \parallel k h _ { i } \parallel I D _ { A } )$ 并存储 $\{ T I D _ { i A q } , k h _ { i } \}$ ，发送消息$M _ { A _ { 4 } } : \{ ( y , z , V _ { 3 } ) \| ( T I D _ { i A q } ^ { * } , V _ { 4 } ) \}$ 给 $S M _ { i }$ 。d) $\boldsymbol { S } \boldsymbol { M } _ { i }$ 计算 $T = h ( I D _ { S M _ { i } } \parallel K _ { a s } \parallel N _ { s } )$ ，验证 $V _ { 3 }$ 的正确性，验证通过即认证了 $P S$ 的身份，计算 $N _ { A } = h ( T \| N _ { A } ) \oplus k _ { i } \oplus y$ ，（20 $\begin{array} { r } { T K = h ( k _ { i } \parallel T \parallel N _ { s } ) } \end{array}$ ， $k h _ { i } { = } h ( T K \parallel N _ { s } \parallel N _ { A } )$ ， $P I D _ { i } ^ { n e w } = h ( T \mid \mid I D _ { S M _ { i } } \mid \mid k _ { i } ) \oplus z$ ，验证 $V _ { 4 }$ 的正确性，验证通过即认证了 $A$ 聚合器身份，最后 $S M _ { i }$ 使用 $k h _ { i }$ 解密 $T I D _ { i A q } ^ { * }$ 获得 $T I D _ { i A q }$ ，存储参数 $\{ P I D _ { i } ^ { n e w } , T I D _ { i A q } , k h _ { i } \}$ 。

综上， $A$ 成功伪装成 $T P A$ 同 $P S$ 和 $\mathbf { \nabla } S M _ { i }$ 进行会话，可见Gope等人的方案无法抵抗密钥泄露伪装攻击，并且在 $P S$ 和 $T P A$ 的共享私钥 $K _ { a s }$ 丢失的情况下， $A$ 能够成功计算出会话密钥 $k h _ { i }$ ，所以Gope等人的方案无法提供会话密钥的安全性。

# 4 提出的方案及正确性证明

为了抵抗文献[7]存在的安全漏洞，并确保智能电网的通信安全，本文提出了一个增强的且可证明安全的身份认证和密钥协商方案。该方案由初始化、注册、身份认证和密钥协商以及恶意智能电表撤销四个阶段组成。

# 4.1 初始化

在此阶段，电力供应商 $P S$ 初始化生成以下参数：a)选择大素数 $\textit { p , q }$ ，基于 $F _ { p }$ 选择一条椭圆曲线 $E$ ， $F _ { p }$ 表示为模 $p$ 的有限域，选择点 $P$ 为椭圆曲线 $E$ 上阶为 $q$ 的基点。b）选择随机数 $s k _ { P S } \in Z _ { q } ^ { * }$ 作为 $P S$ 的私钥，计算 $p k _ { P S } = s k _ { P S } \cdot P$ 作为 $P S$ 的公钥。c）选取安全的单向哈希散列函数 $h$ 。d)定义一种对称加密算法 $E n c _ { ( k ) }$ ，使得 $D e c _ { ( k ) } ( E n c _ { ( k ) }$ (message)) $\ l =$ message，其中 $k$ 是加密和解密的密钥, $D e c _ { ( k ) }$ 是对称解密，message为需要被加密的参数。

最后公布参数 $\{ p , q , E , P , p k _ { P S } , h , E n c _ { ( k ) } \}$ 。

# 4.2 注册

在此阶段，辅助验证器 $\left( A V \right)$ ，网关(GW）和第 $i$ 个智能电表 $( \mathbf { \nabla } S M _ { i }$ )通过电力供应商(PS)进行注册，生成下一阶段所需的参数，通过秘密通道进行传输。

# 4.2.1 AV注册

$A V$ 选定身份标识符 $I D _ { A V }$ 发送给 $P S$ 请求注册， $P S$ 选择随机数 $s k _ { G W } \in Z _ { q } ^ { * }$ 返回， $A V$ 选择随机数 $r _ { A V } \in Z _ { q } ^ { * }$ ，计算$R _ { _ { A V } } = h ( s k _ { _ { G W } } \parallel r _ { _ { A V } } )$ 并将 $\{ r _ { A V } , R _ { A V } \}$ 发送给 $P S$ 完成注册。

# 4.2.2GW注册

a) $G W$ 在 $A V$ 注册完成后即选定身份标识符 $I D _ { G W }$ 发送给$P S$ 请求注册。

b) $P S$ 计算 $R _ { { \scriptscriptstyle G W } } = h ( s k _ { { \scriptscriptstyle G W } } \| { \cal I } D _ { { \scriptscriptstyle G W } } ) \cdot { \cal P }$ ，选择随机数 $r _ { P S } \in Z _ { q } ^ { * }$ ，生成 $\overrightharpoon { G W }$ 的签名 $s _ { G W } = h ( R _ { G W } \parallel I D _ { G W } ) s k _ { P S } + r _ { P S }$ ，计算 $B _ { 1 } = h ( I D _ { A V } \Vert p k _ { P S } )$ ，$B _ { { 2 } } = r _ { A V } \oplus B _ { { 1 } }$ ， $B _ { 3 } = h ( I D _ { G W } \vert \vert I D _ { A V } ) \oplus r _ { P S }$ ， $V _ { A V } = h ( R _ { A V } \parallel r _ { P S } )$ 作为 $A V$ 的认证令牌，为第i个智能电表 $S M _ { i }$ 选定身份标识符 ${ \cal { I } } D _ { s M i }$ ，将参数$\{ s k _ { G W } , s _ { G W } , B _ { 2 } , B _ { 3 } , V _ { A V } , I D _ { S M i } \}$ 发送给 $G W$ 。

c） $G W$ 将 $s k _ { G W }$ 作为私钥，计算 $p k _ { G W } = s k _ { G W } \cdot P$ 作为公钥，存储参数 $\{ B _ { 2 } , B _ { 3 } , V _ { A V } , I D _ { S M i } , s k _ { G W } , s _ { G W } , p k _ { G W } \}$ ，选择随机数 $r _ { P I D } \in Z _ { q } ^ { * }$ ，利用私钥 $s k _ { G W }$ 加密 $\mathbf { \nabla } S M _ { i }$ 的真实身份标识符 $| D _ { S M i }$ ，生成 $\mathbf { \nabla } S M _ { i }$ 的伪身份 $P I D _ { S M i } = E n c _ { s k _ { G W } } ( I D _ { S M i } \parallel r _ { P I D } )$ 并将其发送给 $P S$ 完成注册。

# $4 . 2 . 3 ~ \ S M _ { i }$ 注册

$P S$ 在 $G W$ 注册完成后生成 $S M _ { i }$ 的签名$s _ { S M i } = h ( P I D _ { S M i } \parallel s _ { G W } ) s k _ { P S }$ ，将参数 $\{ s _ { S M i } , I D _ { S M i } , P I D _ { S M i } , I D _ { G W } \}$ 发送给 $S M _ { i }$ ，$S M _ { i }$ 选择随机数 $r _ { S M i } \in Z _ { q } ^ { * }$ ，计算 $s k _ { S M i } = r _ { S M i } S _ { S M i }$ ， $p k _ { S M i } = r _ { S M i } \cdot p k _ { P S }$ 分别作为私钥和公钥，最后存储参数 $\{ I D _ { S M i } , I D _ { G W } , s k _ { S M i } , p k _ { S M i } , P I D _ { S M i } \}$ 注册完成。

# 4.3身份认证和密钥协商

在此阶段，辅助验证器 $A V$ 向网关 $G W$ 发送用户用电数据聚合请求，网关 $G W$ 对辅助验证器 $A V$ 进行身份认证，验证通过即发起与智能电表 $S M _ { i }$ 的相互认证并协商会话密钥。

a) $A V$ 将 $I D _ { S M i }$ 发送给GW，GW计算 $B _ { 1 } = h ( I D _ { A V } \parallel p k _ { P S } )$ ，$r _ { A V } = B _ { 1 } \oplus B _ { 2 }$ ， $R _ { _ { A V } } { = } h ( s k _ { _ { G W } } \parallel r _ { _ { A V } } )$ ， $r _ { P S } = h ( I D _ { G W } \| I D _ { A V } ) \oplus B _ { 3 }$ ，验证$h ( R _ { A V } \parallel r _ { P S } ) = V _ { A V }$ 是否成立，成立则 $A V$ 身份验证通过。GW 选择随机数 $q _ { G W } \in Z _ { q } ^ { * }$ ，计算 $Q _ { G W } = q _ { G W } \cdot p k _ { G W }$ ，将消息 $M _ { 1 } : \{ Q _ { G W } \}$ 发送给 $S M _ { i }$ 。

b) $S M _ { i }$ 选择一个随机数 $q _ { S M i } \in Z _ { q } ^ { * }$ ，计算 $Q _ { S M i } = q _ { S M i } \cdot p k _ { S M i }$ ，$k _ { S G } = s k _ { S M i } q _ { S M i } \cdot Q _ { G W }$ ，生成认证令牌 $V _ { S M i } = h ( k _ { S G } ) \oplus h ( I D _ { S M i } \parallel I D _ { G W } )$ ，将消息 $M _ { 2 } : \{ P I D _ { S M i } , Q _ { S M i } , V _ { S M i } \}$ 发送给 $G W$ 。

c）GW计算 $k _ { _ { G S } } = Q _ { S M i } \cdot q _ { _ { G W } } s k _ { _ { G W } } h ( P I D _ { S M i } \parallel s _ { _ { G W } } )$ ，验证$h ( k _ { G S } ) \oplus h ( I D _ { S M i } \parallel I D _ { G W } ) = V _ { S M i }$ 是否成立，成立则 $S M _ { i }$ 身份验证通过。$G W$ 选择随机数 $r _ { P I D } ^ { n e w } \in Z _ { q } ^ { * }$ ，利用私钥 $s k _ { G W }$ 对 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 的伪身份进行解密，即 $( I D _ { S M i } \parallel r _ { P I D } ) = D e c _ { s k _ { G W } } ( P I D _ { S M i } )$ ，得到 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 的真实身份标识符${ { I D } _ { { S M i } } }$ ，并为 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 生成一个新的伪身份 $P I D _ { S M i } ^ { n e w } = E n c _ { s k _ { G W } } ( I D _ { S M i } \parallel r _ { P I D } ^ { n e w } )$ ，生成会话密钥 $S K _ { G S } = h ( Q _ { S M i } \parallel Q _ { G W } \parallel k _ { G S } )$ ，计算 ${ X P } = P I D _ { S M i } ^ { n e w } \oplus h ( S K _ { G S } )$ 生成认证令牌 $V _ { G W } = h ( P I D _ { S M i } ^ { n e w } \parallel S K _ { G S } ) \oplus h ( I D _ { S M i } \parallel I D _ { G W } )$ ，将消息$M _ { 3 } : \{ X P , V _ { G W } \}$ 发送给 $S M _ { i }$ 。

d) $S M _ { i }$ 生成会话密钥 $S K _ { S G } = h ( Q _ { S M i } \parallel Q _ { G W } \parallel k _ { S G } )$ ，计算$P I D _ { S M i } ^ { n e w } = X P \oplus h ( S K _ { S G } )$ ，验证等式 $h ( P I D _ { S M i } ^ { n e w } \parallel S K _ { S G } ) \oplus h ( I D _ { S M i }$ $\parallel I D _ { G W } ) = V _ { G W }$ 是否成立，成立则 $G W$ 身份验证通过， $S M _ { i }$ 更新自己的伪身份 $P I D _ { S M \bar { i } } ^ { n e w }$ 用于下一次认证。

最后GW和 $S M _ { i }$ 存储会话密钥 $^ { S K }$ （ $S K _ { G S } = S K _ { S G }$ )用于它们之间的进一步交互。

# 4.4恶意智能电表撤销

当GW检测到其管辖区域内的智能电表存在恶意行为，如发送错误的认证信息或电力消费数据异常等，向 $P S$ 提出身份溯源请求。 $P S$ 对该智能电表的数据和行为进行审核后，将恶意智能电表的伪身份 $P I D _ { S M i }$ 发送给GW进行溯源。由于智能电表的伪身份是由GW生成的，所以只有 $G W$ 能够对智能电表的伪身份进行溯源。

GW利用私钥 $s k _ { G W }$ 对恶意智能电表的伪身份 $P I D _ { S M i }$ 进行解密锁定其真实身份，并将其通过秘密通道传输给 $P S$ ， $P S$ 将恶意智能电表的真实身份和伪身份一起添加到撤销列表中，通信系统中的所有成员均可查询撤销列表以避免与列表中的恶意智能电表交互。

# 4.5 正确性证明

证明GW生成的会话密钥 $S K _ { G S } = h ( Q _ { S M i } \parallel Q _ { G W } \parallel k _ { G S } )$ 与 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 生 成的会话密钥 $S K _ { S G } = h ( Q _ { S M i } \parallel Q _ { G W } \parallel k _ { S G } )$ 相等，需要证明 $k _ { G S }$ 与 $k _ { S G }$

相等，证明过程由以下方程式示出。

$$
\begin{array} { r l } { k _ { G S } = Q _ { S M i } \cdot q _ { G W } s k _ { G W } h ( P I D _ { S M i } \parallel s _ { G W } ) = } & { } \\ { p k _ { S M i } \cdot q _ { S M i } q _ { G W } s k _ { G W } h ( P I D _ { S M i } \parallel s _ { G W } ) = } & { } \\ { p k _ { P S } \cdot r _ { S M i } q _ { S M i } q _ { G W } s k _ { G W } h ( P I D _ { S M i } \parallel s _ { G W } ) = } & { } \\ { P \cdot s k _ { P S } r _ { S M i } q _ { S M i } q _ { G W } s k _ { G W } h ( P I D _ { S M i } \parallel s _ { G W } ) = } & { } \\ { r _ { S M i } h ( P I D _ { S M i } \parallel s _ { G W } ) s k _ { P S } q _ { S M i } q _ { G W } s k _ { G W } . P } & { } \end{array}
$$

$$
\begin{array} { r l } { k _ { S G } = s k _ { S M i } q _ { S M i } \cdot Q _ { G W } = } & { { } } \\ { r _ { S M i } s _ { S M i } q _ { S M i } \cdot Q _ { G W } = } \\ { r _ { S M i } h ( P I D _ { S M i } \parallel s _ { G W } ) s k _ { P S } q _ { S M i } \cdot Q _ { G W } = } \\ { r _ { S M i } h ( P I D _ { S M i } \parallel s _ { G W } ) s k _ { P S } q _ { S M i } q _ { G W } \cdot p k _ { G W } } & { { } = } \\ { r _ { S M i } h ( P I D _ { S M i } \parallel s _ { G W } ) s k _ { P S } q _ { S M i } q _ { G W } s k _ { G W } \cdot P } \end{array}
$$

# 5 随机预言模型下形式化安全性分析

使用安全模型进行形式化分析成为现代密码学中强有力的安全证明之一。在现有的安全模型中，本文使用随机预言模型来执行本方案的形式化分析。

# 5.1随机预言安全模型

本方案的身份认证和密钥协商阶段， $\boldsymbol { S } \boldsymbol { M } _ { i }$ 和 $G W$ 是两个主要的参与者，假设每个 $\boldsymbol { S } \boldsymbol { M } _ { i }$ 和 $G W$ 能够运行多个会话， $S _ { i }$ 表示 $S M _ { i }$ 的第 $i$ 个会话实例， $G _ { j }$ 表示 $G W$ 的第 $j$ 个会话实例，每个会话实例都被称为一个预言机。当攻击者对预言机发起预言查询时，预言机需要返回相应的响应参数。定义实例$O \in \{ S _ { i } , G _ { j } \}$ ，在随机预言模型中， $\mid o \mid$ 代表两个会话实例 $S _ { i }$ 和 $G _ { j }$ 之一。概率多项式时间内的攻击者 $A$ 可以任意窃听，拦截，修改，删除，注入通信通道上的消息，其攻击能力由以下预言查询体现。

Extract(o)：此查询用于模拟 $A$ 的被动攻击， $A$ 可以获取各个通信方在公共通信通道上的所有消息。

$s e n d ( o , M )$ ：此查询用于模拟 $A$ 的主动攻击， $A$ 将在通信通道上获取到的消息 $M$ 发送给 $\mid o \mid$ ， $\mid o \mid$ 将相应的消息返回。

Corrupt(o)：此查询使 $A$ 获取实例 $\mid o \mid$ 的长期秘密参数。

$_ { T e s t ( o ) }$ ：此查询用于模拟实例 $\mid o \mid$ 会话密钥的语义安全性。进行 $T e s t ( o )$ 查询后， $\mid o \mid$ 抛掷一个硬币 $b$ ，如果 $\scriptstyle b = 1$ (硬币为正面)，$\mid o \mid$ 将会话密钥返回给 $A$ ，如果 $\scriptstyle b = 0$ (硬币为反面)，则返回给 $A$ 一个随机字符串，其长度跟会话密钥相等。

安全性定义：本方案的安全性通过游戏 $G _ { i } ( i = 0 , 1 , 2 , 3 , 4 , 5 )$ 进行评估。在游戏中 $A$ 可以对 $\mid o \mid$ 发起多次 $T e s t ( o )$ 查询，收到查询后 $\mid o \mid$ 抛掷硬币 $b$ (结果为0或1)，如果 $A$ 正确猜中 $b$ 值，则认为 $A$ 赢得游戏，将攻击者 $A$ 攻破本方案 $s$ 安全性的优势定义为

$$
A d \nu _ { s } ( A ) = \mid 2 P r [ S u c c _ { A } ] - 1 \mid < \varepsilon
$$

其中， $P r [ S u c c _ { A } ]$ 是 $A$ 在游戏 $G _ { i }$ 中猜中 $b$ 值的概率， $\varepsilon$ 是一个及其小可忽略的值。

# 5.2 安全性分析

定理1攻击者 $A$ 在概率多项式时间内赢得游戏 $G _ { i }$ 的概率是可以忽略的， $A$ 最多能够执行 $q _ { h }$ 次哈希查询， $\textit { q } _ { s }$ 次Send查询以及 $q _ { e }$ 次 Execute 查询， $A$ 攻破方案 $s$ 安全性的最大优势为

$$
A d \nu _ { s } ( A ) = \frac { q _ { h } ^ { 2 } } { \vert H a s h \vert } + \frac { ( q _ { s } + q _ { e } ) ^ { 2 } } { p } + 2 ( \frac { q _ { s } } { \vert H a s h \vert } + A d \nu _ { E ( k ) } ( A ) + A d \nu _ { E C D L P } ( A ) )
$$

其中， $\mid H a s h \mid$ 是哈希查询的规模， $A d \nu _ { E ( k ) } ( A )$ 表示 $A$ 违反对称加密算法 $E n c _ { ( k ) }$ 的优势， $A d \nu _ { _ { E C D L P } } ( A )$ 表示概率多项式时间内 $A$ 解决ECDLP的优势。

证明通过游戏 $G _ { i } ( i = 0 , 1 , 2 , 3 , 4 , 5 )$ 推导 $A$ 攻破本方案 $s$ 的优势， $P r [ S u c c _ { i } ]$ 表示 $A$ 猜中游戏 $G _ { i }$ 中硬币 $b$ 值的概率。

游戏 $G _ { 0 }$ ：该游戏模拟的是真实的攻击场景，得到

$$
A d \nu _ { s } ( A ) = \mid 2 P r [ S u c c _ { 0 } ] - 1 \mid
$$

游戏 $G _ { 1 }$ ：该游戏通过执行 Extract(o)查询模拟 $A$ 的被动攻击。 $A$ 通过窃听得到消息 $M _ { 1 } : \{ Q _ { G W } \}$ ， $M _ { 2 } : \{ P I D _ { S M i } , Q _ { S M i } , V _ { S M i } \}$ ，$M _ { 3 } : \{ X P , V _ { G W } \}$ ,但是 $A$ 无法通过这些消息计算会话密钥 $^ { S K }$ 。所

以在该游戏结束时， $A$ 进行 $T e s t ( o )$ 查询无法判断 $\mid o \mid$ 返回的参数是真实的会话密钥还是等长随机字符串。因此，与真实的攻击场景相比， $A$ 在该游戏中并没有增加优势，所以有

$$
P r [ S u c c _ { 0 } ] { = } P r [ S u c c _ { 1 } ]
$$

游戏 $G _ { 2 }$ ：该游戏去除游戏 $G _ { 1 }$ 中存在的两种碰撞情形，模拟 $A$ 的主动攻击。

情形1根据生日悖论[23]，哈希查询的输出发生碰撞，其概率小于等于 $q _ { h } ^ { 2 } / 2 | H a s h |$ 。

情形 2选取的随机数发生碰撞，其概率小于等于$( q _ { s } + q _ { e } ) ^ { 2 } / 2 p$ 。

除非发生上述碰撞，否则 $G _ { 2 }$ 与 $G _ { \imath }$ 不可区分，因此有

$$
P r [ S u c c _ { 2 } ] - P r [ S u c c _ { 1 } ] \leq \frac { q _ { h } ^ { 2 } } { 2 \vert H a s h \vert } + \frac { ( q _ { s } + q _ { e } ) ^ { 2 } } { 2 p }
$$

游戏 $G _ { 3 }$ ：该游戏去除游戏 $G _ { 2 }$ 中 $A$ 无须进行哈希查询而猜测到认证令牌 $V _ { S M i }$ 或 $V _ { G W }$ 的情形，这种情形的概率小于等于$q _ { s } / \vert H a s h \vert$ 。因此有

$$
P r [ S u c c _ { 3 } ] - P r [ S u c c _ { 2 } ] \leq \frac { q _ { s } } { \vert H a s h \vert }
$$

游戏 $G _ { 4 }$ ：该游戏去除游戏 $G _ { 3 }$ 中 $A$ 对 $P I D _ { S M i }$ 成功解密获得$I D _ { S M i }$ 的情形，因此有

$$
P r [ S u c c _ { 4 } ] - P r [ S u c c _ { 3 } ] \leq A d \nu _ { E ( k ) } ( A )
$$

游戏 $G _ { 5 }$ ：该游戏对游戏 $G _ { 4 }$ 进行修改，模拟 $A$ 的密钥泄露伪装攻击。在该游戏中 $A$ 执行 Extract(o)查询获取通信通道上的参数，执行Corrupt(o)查询获得 $S _ { i }$ 和 $G _ { j }$ 的长期秘密参数。在已知 $\{ s k _ { S M i } , Q _ { G W } , Q _ { S M i } , p k _ { S M i } \}$ 的情况下，要想获得 $S _ { i }$ 的会话密钥$S K _ { S G } = h ( Q _ { S M i } \parallel Q _ { G W } \parallel k _ { S G } )$ ，需要计算 $k _ { S G } = s k _ { S M } q _ { S M i } \cdot Q _ { G W }$ ，但从$Q _ { S M i } = q _ { S M i } \cdot p k _ { S M i }$ 中得到 $q _ { S M i }$ 需要解决椭圆曲线离散对数难题(ECDLP)，对于 $G _ { j }$ 同理。因此，比较该游戏与游戏 $G _ { 4 }$ 的区别可以得出

$$
P r [ S u c c _ { 5 } ] - P r [ S u c c _ { 4 } ] \leq A d \nu _ { E C D L P } ( A )
$$

在该游戏中， $A$ 在猜测 $b$ 值上并没有增加优势，因此

$$
P r [ S u c c _ { 5 } ] = \frac { 1 } { 2 }
$$

根据式(3)和(4)，得到

$$
{ \frac { 1 } { 2 } } A d \nu _ { s } ( A ) = { \big | } P r [ S u c c _ { 0 } ] - { \frac { 1 } { 2 } } { \big | } \mathbf { - } { \big | } P r [ S u c c _ { 1 } ] - { \frac { 1 } { 2 } } { \big | }
$$

根据式(9)和(10)，得到

$$
{ \frac { 1 } { 2 } } A d \nu _ { s } ( A ) = \mid P r [ S u c c _ { 1 } ] - P r [ S u c c _ { 5 } ] \mid
$$

根据式 $( 5 ) { \sim } ( 8 )$ 和三角不等式，得到

$$
\begin{array} { r l } & { \big | P r [ S u c c _ { 1 } ] - P r [ S u c c _ { 5 } ] \big | = } \\ & { \big | P r [ S u c c _ { 1 } ] - P r [ S u c c _ { 2 } ] + P r [ S u c c _ { 2 } ] - P r [ S u c c _ { 3 } ] + } \\ & { P r [ S u c c _ { 3 } ] - P r [ S u c c _ { 4 } ] + P r [ S u c c _ { 4 } ] - P r [ S u c c _ { 5 } ] \big | \leq } \\ & { \big | P r [ S u c c _ { 1 } ] - P r [ S u c c _ { 2 } ] \big | + \big | P r [ S u c c _ { 2 } ] - P r [ S u c c _ { 3 } ] \big | + } \\ & { \big | P r [ S u c c _ { 3 } ] - P r [ S u c c _ { 4 } ] \big | + \big | P r [ S u c c _ { 4 } ] - P r [ S u c c _ { 5 } ] \big | \leq } \\ & { \frac { q _ { k } ^ { 2 } } { 2 \big | H a s h \big | } + \frac { ( q _ { s } + q _ { e } ) ^ { 2 } } { 2 p } + \frac { q _ { s } } { \big | H a s h \big | } + A d v _ { E ( k ) } ( A ) + A d v _ { E c o L P } ( A ) } \end{array}
$$

根据式(11)和(12),得到式(2)

$$
A d \nu _ { s } ( A ) = \frac { q _ { h } ^ { 2 } } { \vert H a s h \vert } + \frac { ( q _ { s } + q _ { e } ) ^ { 2 } } { p } + 2 ( \frac { q _ { s } } { \vert H a s h \vert } + A d \nu _ { E ( k ) } ( A ) + A d \nu _ { E C D L P } ( A ) )
$$

由此，定理一证毕。以上证明过程意味着 $A$ 在游戏中获胜的概率是可忽略的，因此，本方案在随机预言模型下是安全的。

# 6 ProVerif仿真分析

ProVerif是一个被广泛使用的自动化密码协议仿真工具，支持多种密码学原语，如加密、解密、数字签名、散列函数等，并指定了重写规则和方程式。该工具能够证明可达性、认证性以及观测等效性。它由三个部分组成，即协议输入、

系统处理和结果输出，系统输入部分是运用Pi演算或Horn逻辑来编码的协议，系统处理部分是运用一阶逻辑对编码的协议的安全性进行推导，结果输出部分能够在编码的协议不满足某种特定的安全属性时给出相应的攻击序列。此外，ProVerif中还具有一个攻击者模型，可以进行窃听、拦截、修改或重新传输消息，这些攻击仅受到加密方法的限制。

本文将所提方案在ProVerif中建模为四个不同的场景，以便证明所提方案对已知攻击的抵抗能力，并且进一步验证方案具备智能电表的匿名性和会话密钥的前向安全性。

在场景一中，没有泄露任何的秘密参数，仅对方案在ProVerif中进行建模，对一些常见的攻击进行查询，证明了智能电表的匿名性和方案的可达性，仿真结果如图2所示，结果 $\textcircled{1}$ 是对方案可达性的查询，证明了会话密钥的安全性；结果 $\textcircled{2}$ 证明了智能电表的匿名性；结果 $\textcircled{3}$ 和 $\textcircled{4}$ 表明智能电表和网关可以进行相互认证，并且能够抵抗假冒、重放、中间人等常见的攻击。

Completing equations...   
Completing equations..   
-- Process 1-- Query not attacker(SK) in process 1   
Completing...   
200 rules inserted.Base: 175 rules (40 with conclusion selected).Queue: 44 rules. 400 rules inserted.Base: 364 rules (62 with conclusion selected).Queue: 37 rules. Starting query not attacker(SK)   
RESULT not attacker(SK) is true. $\textcircled{1}$ - Query not attacker(IDSMi[]) in process1   
Completing...   
200 rules inserted. Base:175 rules (40 with conclusion selected). Queue: 44 rules. 400 rules inserted. Base: 364 rules (62 with conclusion selected). Queue: 37 rules. Starting query not attacker(IDSMi[])   
RESULT not attacker(IDSMi[]) is true. $\textcircled{2}$ （20 -- Query inj-event(endSMi $\scriptstyle \implies$ inj-event(startSMi) in process 1   
Completing..   
200 rules inserted. Base: 171 rules (33 with conclusion selected). Queue: 42 rules. 400 rules inserted. Base: 358 rules (58 with conclusion selected). Queue: 88 rules. Starting query inj-event(endSMi) ==>inj-event(startSMi)   
RESULT inj-event(endSMi) $\scriptstyle \implies$ inj-event(startSMi) is true. $\textcircled{3}$ -- Query inj-event(endGW) $\Rightarrow$ inj-event(startGW) in process 1   
Completing...   
200 rules inserted. Base:176 rules (33 with conclusion selected). Queue: 37 rules. 400 rules inserted. Base: 365 rules (62 with conclusion selected). Queue: 57 rules. Starting query inj-event(endGW)==> inj-event(startGW)   
RESULT inj-event(endGW) $\scriptstyle \Rightarrow$ inj-event(startGW) is true. $\textcircled{4}$ （204

在场景二中，验证本方案具备会话密钥的前向安全性，使用命令 $( ( \lfloor p G W ) \vert ( \ ! p P S ) \vert ( \ ! p S M i ) \vert ( \ ! p A V ) \vert ( p h a s e \mathrm { 1 } ; o u t ( n e t ,$ $( p k S M i , p k G W , s k S M i , s k G W , s G W ) ) )$ 向攻击者泄露会话密钥中的长期秘密参数，查询结果如图3所示，攻击者获取会话密钥失败。

Completing equations...   
Completing equations..   
-- Process 1-- Query not attacker_pl(SK) in process 1   
Completing...   
200 rules inserted.Base:180 rules (59 with conclusion selected). Queue: 31 rules. 400 rules inserted. Base: 364 rules (89 with conclusion selected). Queue: 70 rules. Starting query not attacker_p1(SK)   
RESULT not attacker_pl(SK) is true.

在场景三中，验证本方案具备密钥泄露伪装攻击的抵抗力，使用命令 $( ( ! p G W ) \big | ( ! p P S ) \big | ( ! p S M i ) \big | ( ! p A V ) \big | ( p h a s e 2 ; o u t$ $( n e t , ( s k S M i , s k G W ) ) ) ,$ 向攻击者泄露智能电表和网关的私钥，查询结果如图4所示，攻击者获取会话密钥失败。

Completing equations...   
Completing equations...   
-- Process 1-- Query not attacker_p2(SK) in process 1   
Completing...   
200 rules inserted. Base: 179 rules (73 with conclusion selected).Queue: 41 rules. 400 rules inserted. Base: 363 rules (105 with conclusion selected). Queue: $^ { 6 9 }$ rules. 600 rules inserted. Base: 556 rules (115 with conclusion selected). Queue:19 rules. Starting query not attacker_p2(SK)   
RESULT not attacker_p2(SK) is true.

在场景四中，验证本方案具备智能电表临时秘密值泄露的抵抗力，使用命令 $( ( ! p G W ) \big | ( ! p P S ) \big | ( ! p S M i ) \big | ( ! p A V ) \big | ( p h a s e 3 ; $ $o u t ( n e t , ( q S M i , Q S M i ) ) )$ 向攻击者泄露智能电表的临时秘密值，查询结果如图5所示，攻击者获取会话密钥失败。

# 7 性能分析

本节从安全性，计算成本以及通信量三个方面对本方案进行性能分析，将本方案与文献[7,9,10,12,17,19,20]的方案进行比较。

Completing equations...   
Completing equations...   
Process1--Query not attacker_p3(SK_GW_SMI[]) in process1   
Completing...   
200 rules inserted.Base:184 rules (75 with conclusion selected).Queue: 36 rules. 400 rules inserted. Base: 374 rules (107 with conclusion selected).Queue:71 rules. 600 rules inserted. Base: 566 rules (112 with conclusion selected). Queue: 14 rules. Starting query not attacker_p3(SK_GW_SMI[])   
RESULT not attacker_p3(SK_GW_SMI[]) is true.

如表1所示，在安全性上，本方案能够提供相互认证、智能电表的匿名性和不可追踪性、会话密钥的安全性以及抵抗各类已知的攻击。Gope等人方案7无法提供相互认证和会话密钥的安全性，并且无法抵抗密钥泄露伪装攻击。其他文献[9,10,12,17,19,20]的方案也均存在各种安全缺陷，因此就安全性而言，本方案优于现有方案。

采用文献[24]在Ubuntu12.04.1LTS32位操作系统上获得的实验结果对比8个方案在认证阶段的计算成本。哈希操作的计算成本 $T _ { h } \approx 0 . 0 0 2 3 \mathrm { m s }$ ；对称加/解密的计算成本 $T _ { e d } \approx$ $0 . 0 0 4 6 \mathrm { m s }$ ；ECC点乘的计算成本 $T _ { m } \approx 2 . 2 2 6 \mathrm { m s }$ ；ECC点加的计算成本 $T _ { a } \approx 0 . 0 2 8 8 \mathrm { m s }$ ；指数运算的计算成本 $T _ { e } \approx 3 . 8 5 \mathrm { m s }$ ；双线性配对的计算成本为 $T _ { p } \approx 5 . 8 1 1 \mathrm { m s }$ ，个别操作由于计算成本过低忽略不计[25]。通信量是协议执行期间通过网络传输的总位数，较低的通信量可提供更快的数据传输和更少的时间延迟，为了计算通信量，假设身份标识，随机数，哈希散列输出，时间戳，对称加/解密块等为 $1 6 0 \mathrm { b i t }$ ；椭圆曲线上的点为320bit；双线性映射组的生成元 $G _ { 1 }$ 为1024bit。表2为计算成本和通信量的对比结果。

在计算成本方面，本方案主要采用哈希散列函数和二进制运算此类轻量级运算，同时辅以ECC点乘运算和对称加/解密运算，计算成本为 $8 . 9 5 2 3 \mathrm { m s }$ 。文献[9,10]采用双线性配对运算和指数运算，大幅增加了计算量。文献[12,17,20]主要采用ECC点乘运算，然而ECC点乘运算的使用次数均超过本方案。本方案的计算成本相比于文献[9,10,12,17,20]分别减少了 $7 4 . 4 \%$ ， $70 . 8 \%$ ， $60 . 0 \%$ ， $3 3 . 4 \%$ ， $4 2 . 7 \%$ 。Gope 等人方案[7]主要采用哈希散列函数构建其认证方案，没有额外的高成本运算，计算成本较低。然而由表1可知，Gope等人方案]由于使用轻量级的加密原语导致其安全性不足，容易遭受安全攻击。

表1安全性对比  
Tab.1Safety comparison   

<html><body><table><tr><td>方案</td><td>P1</td><td>P2</td><td>P3</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td></tr><tr><td>文献[9]</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td><td>×</td></tr><tr><td>文献[10]</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td><td>√</td><td>√</td><td>×</td></tr><tr><td>文献[12]</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td><td>×</td></tr><tr><td>文献[17]</td><td>√</td><td>×</td><td>×</td><td>√</td><td>×</td><td>√</td><td>√</td><td>×</td></tr><tr><td>文献[19]</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td><td>×</td></tr><tr><td>文献[20]</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td></tr><tr><td>文献[7]</td><td>×</td><td>√</td><td>√</td><td>√</td><td>√</td><td>×</td><td>√</td><td>×</td></tr><tr><td>本文方案</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td></tr></table></body></html>

注：P1相互认证P2智能电表匿名性和不可追踪性P3 抗中间人攻击P4抗重放攻击P5抗假冒攻击P6会话密钥的前向安全性P7抗智能电表临时秘密值泄露攻击P8抗密钥泄露伪装攻击。

在通信量方面，本方案在保证安全性的情况下将认证阶段的消息传输次数减少至3次，实现了通信过程的精简化，通信量仅为 $1 7 6 0 { \mathrm { b i t } }$ 。而Gope等人方案[7]在认证阶段的消息传输次数为4次，通信量达到了3040bit。本方案的通信量相比于文献[7,9,10,12,17,19]分别减少了 $4 2 . 1 \% , 5 0 . 5 \% , 5 2 . 6 \%$ $2 1 . 4 \%$ ， $1 5 . 4 \%$ ， $9 . 0 \%$ ，大大降低了通信时延。

由表1和2可知，本方案在提供足够安全性的同时，也能够保证较低的计算成本和通信量。Gope等人方案[7]足够轻量级，然而却存在安全性不足和认证流程复杂进而导致通信量过高的问题，无法兼顾高效性和安全性。此外，Gope等人的方案不支持伪身份的更新和溯源，而本方案GW在会话中能够生成新的智能电表伪身份 $P I D _ { S M i } ^ { n e w }$ 并发放给 $\boldsymbol { S } \boldsymbol { M } _ { i }$ ， $S M _ { i }$ 则更新伪身份用于下一次会话。同时，本方案能够通过伪身份溯源恶意智能电表的真实身份并将其撤销。

表2计算成本和通信量对比

Tab.2 Calculation time and traffic comparison   

<html><body><table><tr><td>方案</td><td>操作</td><td>计算成本/ms</td><td>通信量/bit</td></tr><tr><td>文献[9]</td><td>10Th +7Tm+2Ta+2Te+2Tp</td><td>34.9846</td><td>3552</td></tr><tr><td>文献[10]</td><td>12Th +5Tm +6Ta +2Te+2Tp</td><td>30.6524</td><td>3712</td></tr><tr><td>文献[12]</td><td>11Th +10Tm + 3Ta</td><td>22.3717</td><td>2240</td></tr><tr><td>文献[17]</td><td>14Th + 6Tm + 2Ta</td><td>13.4458</td><td>2080</td></tr><tr><td>文献[19]</td><td>18Th</td><td>0.0414</td><td>1920</td></tr><tr><td>文献[20]</td><td>7Th +7Tm +8Ted</td><td>15.6349</td><td>1440</td></tr><tr><td>文献[7]</td><td>22Th + 2Ted</td><td>0.0598</td><td>3040</td></tr><tr><td>本文方案</td><td>12Th +7Ted +4Tm</td><td>8.9523</td><td>1760</td></tr></table></body></html>

# 8 结束语

本文针对现有智能电网通信认证方案安全性不足和效率低的问题，分析证明了Gope 等人方案的安全漏洞，并基于椭圆曲线加密算法提出了一个适用于智能电网的身份认证和密钥协商方案，通过仿真工具ProVerif和理论分析验证了所提方案的安全性，与同类认证方案对比表明，所提方案在安全性，计算成本和通信量三个方面均具有优势，能够满足智能电网在通信过程中对于安全性和高效性的要求。

本方案仅支持网关对智能电表进行一对一的单点认证，网关的计算成本与其管辖区域内的智能电表数量成线性关系。在智能电表部署愈发完善的情况下，网关可能在同一时间段需要进行大量的认证服务，这将会导致很高的网络时延，并且对网关的计算能力也是一个极大的考验。下一步将研究单个网关对多个智能电表进行批量认证以减少网关的计算负担。

# 参考文献：

[1]Sadhukhan D,Ray S,Obaidat MS,et al.Asecure and privacy preserving lightweight authentication scheme for smart-grid communication using elliptic curve cryptography [J].Journal of Systems Architecture,2021, 114: 101938.   
[2]Ferrag MA,MaglarasLA,Janicke H,et al.A systematic review of data protectionandprivacypreservationschemesforsmartgrid communications [J]. Sustainable Cities and Society,2018,38:806-835.   
[3]Mahmood K,Chaudhry S A,Naqvi H,et al.A lightweight message authentication scheme for smart grid communications in power sector [J]. Computers& Electrical Engineering,2016,52(C):114-124.   
[4]Li Xiong,Wu Fan,Saru K,et al.A provably secure and anonymous message authentication scheme for smart grids [J].Journal of Parallel and Distributed Computing,2019,132:242-249.   
[5]Dua A,Kumar N, Singh M,et al. Secure message communication among vehicles using elliptic curve cryptography in smart cities [C]//Proc of theInternational ConferenceonComputerInformationand Telecommunication Systems.Kunmin,NJ:IEEE Press,2016:1-6.   
[6]Wang Wenye,Lu Zhou.Cyber security in the smart grid: survey and challenges [J].Computer Networks,2013,57 (5):1344-1371.   
[7]Gope P,Sikdar B.Lightweight and privacy-friendly spatial data aggregation for secure power supply and demand management in smart grids [J].IEEE Trans on Information Forensics and Security,2019,14 (6): 1554-1566.   
[8]Wu Libing,Wang Jing，Sherali Z,et al.Anonymous and efficient message authentication scheme for smart grid [J]. Security and Communication Networks,2019:1-12.   
[9]Tsai JL,Lo N W.Secure anonymous key distribution scheme for smart grid[J].IEEE Trans on Smart Grid,2016,7(2):906-914.   
[10] Odelu V,Das A K,Wazid M,et al. Provably secure authenticated key agreement scheme for smart grid[J].IEEE Trans on Smart Grid,2018,9 (3): 1900-1910.   
[11] Chen Yuwen，Martinez JF,Castillejo P,et al.An anonymous authentication and key establish scheme for smart grid: FAuth [J]. Energies,2017,10(9):1354-1377.   
[12] He Debiao,Wang Huaqun,Khan MK,et al.Lightweight anonymous key distribution scheme for smart grid using elliptic curve cryptography [J]. Iet Communications,2016,10 (14):1795-1802.   
[13] Abbasinezhad M D,Ostad SA,Nikooghadam M.et al.A secure and efficient key establishment scheme for communications of smart meters and service providers in smart grid [J].IEEE Trans on Industrial Informatics,2020,16(3):1495-1502.   
[14] Fan Wu,Xu Lili,Li Xiong,et al.A lightweight and provably secure key agreement system for a smart grid with elliptic curve cryptography [J] IEEE Systems Journal,2019,13 (3):2830-2838.   
[15] Garg S,KaurK,Kaddoum G,etal. Secure and lightweight authentication scheme for smart metering infrastructure in smart grid [J].IEEE Trans on Industrial Informatics,2020,16 (5): 3548-3557.   
[16]Fatty S,Osama E.A lightweight authenticated key establishment scheme for secure smart grid communications [J]. International Journal of Safety and Security Engineering,2020,10 (4): 549-558.   
[17] Srinivas J,Das A K,Li Xiong,et al. Designing anonymous signaturebased authenticated key exchange scheme for internet of things-enabled smart grid systems [J].IEEE Trans on Industrial Informatics,2021,17 (7): 4425-4436.   
[18] TanveerM,KhanAU,ShahH,et al.ARAP-SG:Anonymous and reliable authentication protocol for smart grids [J].IEEE Access,2021,9: 143366-143377.   
[19] Azeem I, Shehzad A C,Mamoun A,et al.A secure demand response management authentication scheme for smart grid [J].Sustainable Energy Technologies and Assessments,2021,48:101571.   
[20] Safkhani M,Kumari S,Shojafar M,et al.An authentication and key agreement scheme for smart grid [J].Peer-to-Peer Networking and Applications,2022,15:1595-1616.   
[21] Huang Chengpeng,Wang Xiaoming,Gan Qingqing,et al.A lightweight and fault-tolerable data aggregation scheme for privacy-friendly smart grids environment [J].Cluster Computing,2021,24: 3495-3514.   
[22] Daniel R M,Rajsingh EB,Silas S.An efficient eCK secure identity based two party authenticated key agreement scheme with security against active adversaries [J].Information and Computation,2020,275: 104630.   
[23]齐小晨，黎妹红，杜晔．多服务器环境下基于动态ID的轻量级身份 认证协议 [J].北京航空航天大学学报,2021,47(12):2632-2640.(Qi Xiaochen,Li Meihong,Du Ye.Lightweight identity authentication protocol based on dynamic ID in multi-server environment [J]. Journal of Beijing University of Aeronautics and Astronautics,2021,47 (12): 2632-2640.)   
[24] Kilinc HH, Yanik T.A survey of sip authentication and key agreement schemes [J].IEEE Communications Surveys& Tutorials,2014,16(2): 1005-1023.   
[25]李晓天，陈建华．更安全的匿名三因子多服务器身份认证协议研究 [J]．计算机应用研究，2020,37(9):2781-2788.(Li Xiaotian,Chen Jianhua.Research on security-enhanced three-factor multi-server authentication scheme with anonymity [J].Application Research Of Computers,2020,37(9): 2781-2788.)