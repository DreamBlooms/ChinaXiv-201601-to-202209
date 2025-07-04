# 基于双线性映射的三因子远程身份认证协议研究

魏春英，郭中华

(宁夏大学 物理与电子电气工程学院，银川 750021)

摘要：为了提高多服务器环境身份认证的安全性，降低计算复杂度，提出一种基于双线性映射的三因子认证协议，这些因子包括生物信息、智能卡和双线性映射密码。所提协议包括系统设置、服务器注册、用户注册、登录、认证和密钥协商，以及密码更新六个阶段，其中，生物因子和智能卡作为核心因子涉及注册、登录和认证和更改阶段。Oracle形式化证明验证了所提协议的安全性，攻击者无法得到标志、密码、生物特征信息等，可以实现密钥协商和双向身份认证。与其他相关协议相比，所提协议在安全特征、智能卡存储成本、通信成本等方面具有一定优势。

关键词：多服务器；身份认证；双线性映射；生物信息；智能卡；形式化证明中图分类号：TP393.08 doi:10.19734/j.issn.1001-3695.2018.06.0476

Research of three factor remote authentication protocol based on bilinear mapping

Wei Chunying, Guo Zhonghua (CollegeofPhysics&Electronic Electrical EngineeringNingxia University,Yinchuan75oo21,China)

Abstract:To improve thesecurityof authentication in multiple-server environment and reduce thecomputational complexity, athreefactorauthentication protocolbasedonbilinear mapping is proposed,which includes three factorsof bioinformatics, smartcard and bilinear mappng cipher.The proposed protocolincludes 6 stages:system setup,server registration，user registration,login,uthenticationandkeyagreement,andpasswordupdate.Amongthem,bologicalfactorsandsmartcardsas thecorefactors involveregistration,landing,authenticationandmodification.FormalverificationofOracleverifiesthesecurity ofthe protocol.Atackerscanotgetidentification,passwrd,iomtriciformation,etc,andthisieveskeyagreetd mutualauthentication.Compared with otherrelated protocols,the proposed protocolhassome advantages insecurity features, smart card storage cost, communication cost and so on.

Key words: multiple-server;authentication; bilinear mapping;bioinformatics; smartcard; formal verification

# 0 引言

现代网络通信技术的迅猛发展使得在线服务[1的功能大量增加，服务质量大幅提高。诸如电子邮件、电子医疗、网上银行和商务已经成为人们日常生活的重要组成部分。然而，这些在线服务大多在不可信信道上进行，造成不法分子的有机可乘。因此，因此在线服务的隐私性、完整性、保密性等安全性问题至关重要，其中，身份认证[2是在线服务的重要前提，是网络安全性的研究热点和难点。

按照服务器的分布性，身份认证协议可分为单服务器环境和多服务器环境。单服务器环境中，用户必须注册到每个应用服务器，其最大缺点是用户必须记住多个服务器对应的密码和标志，用户体验较差，这种情况适用于一些特别安全考虑的情形，如某些健康安全系统[3]。多服务器环境则不需要这样繁琐，单次注册即可访问多个服务器。

多服务器环境的身份认证研究得较广，如文献[4]提出了一种基于多服务器环境的鲁棒双因子认证协议，即智能卡和曲线密码，该协议能够抵御多种潜在的网络攻击。文献[5]研究了文献[4]的协议，证明其存在安全漏洞。易受假冒攻击、密码猜测攻击和特权内部者攻击，并提出了克服上述缺陷改进的双因子协议。相关研究表明[，双因子认证协议可靠性不足，因为用户通常会选择一个低熵密码，易受字典攻击。文献[7]针对当前跨信任域密钥协商协议无法满足网络需求的问题，提出一种跨身份的自治域密钥协商协议，使用不同的公开参数和PKG主密钥，该协议所使用的因子较少。文献[8]指出研究了文献[9]的身份认证协议，指出其易受智能卡丢失攻击、服务器模仿攻击等缺点，难以保护用户的隐私性。并基于生物特征和扩展混沌映射，提出了一个改进的身份认证协议。

当前很多研究者为了降低复杂度，使用了双线性配对或点乘用于身份认证，本文也运用了双线性配对，提出了一种基于双线性映射[0的三因子远程身份认证协议，这些因子包括生物因子、智能卡和密码，分析结果表明所提协议具有较高的安全性和计算效率。

# 1 提出的远程身份认证协议

# 1.1 系统设置阶段

注册中心 $R C$ 选择一个随机数 $S _ { R S } \in Z _ { q } ^ { * }$ ，并保留该随机数作为密钥。其计算 $P u b _ { _ { R S } } = S _ { _ { R S } } \cdot P$ ，式中 $P$ 为组 $G _ { 1 }$ 的生成器。RC将 $\{ \hat { \mathrm { e } } , G _ { 1 } , G _ { 2 } , q , P , P u b _ { R S } , H ( . ) , h ( . ) \}$ 声明为公共参数。

# 1.2服务器注册阶段

该阶段中，一个新的应用服务器 $S S _ { j }$ 加入多服务器环境以向远程用户 $U _ { i }$ 提供服务。服务器 $S S _ { j }$ 选择一个身份标志 $S I D _ { j } ( 1 <$ $j < m$ ），其中， $m$ 表示多服务器环境中包含的 $S S _ { j }$ 总数量。服务器 $S S _ { j }$ 将 $S I D _ { j }$ 发送到注册中心 $R C _ { \circ }$ 在接收到来自 $S S _ { j }$ 的 $S I D _ { j }$ 后，$R C$ 计算 $S _ { j } = h ( S I D _ { j } \parallel S _ { R S } ) \cdot P \in G _ { 1 }$ ， $P u b _ { j } = S _ { j } \cdot P \in { \cal G } _ { 1 }$ ，然后，通过一个可靠信道将 $S _ { j }$ 发送到应用服务器 $S S _ { j }$ ，并公开 $P u b _ { j }$ 作为公共参数。

# 1.3用户注册阶段

当远程用户 $U _ { i }$ 希望接入 $S S _ { j }$ 的服务时， $U _ { i }$ 需要通过以下步骤注册到 $R C$ 0

a)用户 $U _ { i }$ 选择 $I D _ { i }$ 和 $P W _ { i }$ ，并在传感器输入其生物特征 $B _ { i }$ $U _ { i }$ 计算 $U I D _ { i } = H ( I D _ { i } ) \in G _ { 1 }$ 和 $H P W _ { i } = h ( P W _ { i } \parallel I D _ { i } ) \cdot P \in { \cal G } _ { 1 }$ ，通过一个可信信道将 $\{ U I D _ { i } , H P W _ { i } , B _ { i } \}$ 发送到 $R C$ 0

b)在收到来自 $U _ { i }$ 的注册消息后， $R C$ 计算 $b _ { i } = H _ { 1 } ( B _ { i } )$ ，$R e g _ { i } = h ( U I D _ { i } \parallel H P W _ { i } ) \in Z _ { q } ^ { * } \qquad , \qquad D I D _ { i } = S _ { _ { R S } } \cdot U I D _ { i } \in G _ { 1 }$ ，$Z _ { i } = h ( H P W _ { i } ) \cdot P \in { \cal G } _ { 1 }$ 以及 $S _ { i } = D I D _ { i } + Z _ { i } \in G _ { 1 } \circ R C$ 为每个用户每次生成一个唯一表示( $\cdot T I D _ { i } \rangle$ ，并计算 $P I D _ { i } { = } h ( T I D _ { i } | | S _ { R S } )$ 。其后，RC 在数据库中存储 $\{ P I D _ { i } , U I D _ { i } \}$ 和状态位 $( 0 , 1 )$ ，其中状态位表示用户的状态。最后，RC生成一张包含信息 $\{ T I D _ { i } , b _ { i } , R e g _ { i } , S _ { i } ,$ PubRs, $H ( . ) , h ( . ) , H 1 \}$ 的智能卡，并通过一个可靠信道将其发送至 $U _ { i }$ 。

# 1.4登录阶段

当用户 $U _ { i }$ 希望登录到服务器 $S S _ { j }$ 时，需要执行以下步骤:

a $U _ { i }$ 将智能卡插入终端，输入 $\boldsymbol { I D } _ { i } ^ { * }$ 、 $\boldsymbol { P } \boldsymbol { W } _ { i } ^ { * }$ 和 ${ B } _ { i } ^ { * }$ 。智能卡读卡器计算 $U I D _ { i } ^ { * } = H ( I D _ { i } ^ { * } )$ ， $H P W _ { i } ^ { * } = h ( P W _ { i } ^ { * } \parallel I D _ { i } ^ { * } ) \cdot P$ ，和${ b } _ { i } ^ { * } = H _ { 1 } ( B _ { i } )$ ，并检查 $\boldsymbol { b } _ { i } ^ { * } = \boldsymbol { b } _ { i }$ 是否成立。若成立，则意味着用户 $U _ { i }$ 输入了正确的生物统计信息；若不成立，则中止连接。此后，智能卡计算 $R e g _ { i } ^ { * } = h ( U I D _ { i } ^ { * } \parallel H P W _ { i } ^ { * } )$ ，并将其与存储的 $R e g _ { i }$ 进行比较。若两者匹配，则确认 $U _ { i }$ 输入了正确的 $\{ I D _ { i } , P W _ { i } \}$ ，并进入下一步骤。

b)智能卡生成一个随机数ri，并计算Zi=h(HPWi)·P∈G，$D I D _ { i } = S _ { i } - Z _ { i } \in { \cal G } _ { 1 } \ , \quad R _ { i } = r _ { i } \cdot P \in { \cal G } _ { 1 } \ , \quad M _ { i } = r _ { i } \cdot P u b _ { R S } \in { \cal G } _ { 1 } \ $ ，和$d _ { i } = h ( U I D _ { i } \parallel S I D _ { i } \parallel M _ { i } \parallel D I D _ { i } ) \in Z _ { q } ^ { * } ,$ 。最后，智能卡读卡器将登陆消息 $M _ { 1 } = \{ R _ { i } , T I D _ { i } , S I D _ { j } , d _ { i } \}$ 通过一个不可靠信道发送给 $R C$ 。

# 1.5验证和密钥协商阶段

该阶段中执行以下步骤：

a)在收到来自用户的登陆消息 $M _ { 1 }$ 后， $R C$ 计算$P I D _ { i } ^ { * } = h ( T I D _ { i } \parallel S _ { R S } )$ ，并检查数据库中是否存在 ${ P I D } _ { i } ^ { * }$ 。若不存在，则 $R C$ 退出会话；若存在， $R C$ 从数据库中得到 $U I D _ { i }$ 并进入下一步骤。

$\mathsf { b } ) R C$ 计算 ${ M } _ { i } ^ { * } = { R } _ { i } \cdot { S } _ { R S } = { M } _ { i }$ ， $D I D _ { i } ^ { * } = U I D _ { i } \cdot S _ { \scriptscriptstyle R S }$ 和$\ r { d } _ { i } ^ { * } = h ( \ r { U I D } _ { i } \parallel \ r { S I D } _ { j } \parallel \ r { M } _ { i } ^ { * } \parallel \ r { D I D } _ { i } ^ { * } )$ ，并检查 $\boldsymbol { d } _ { i } ^ { * } = \boldsymbol { d } _ { i }$ 和（20 $\hat { e } < U I D _ { i } , P u b _ { _ { R S } } > = \hat { e } < D I D _ { i } , P >$ 是否成立。若两个条件均成立，则 $R C$ 执行下一个步骤；否则，会话将被终止。

$_ { \mathrm { c } ) R C }$ 生成一个随机nonce $n _ { i }$ ，并计算$S _ { j } = h ( S I D _ { j } \parallel S _ { R S } ) \cdot P \in { \cal G } _ { 1 } \quad , \qquad L _ { i } = n _ { i } \cdot P \quad , \qquad w _ { i } = n _ { i } \cdot P u b _ { j } \quad$ ，$k _ { j } = U I D + w _ { i }$ ，以及 $T _ { i } = h ( U I D _ { i } \parallel S I D _ { j } \parallel S _ { j } \parallel w _ { i } )$ 。随后， $R C$ 通过一个公共信道将 $M _ { 2 } = \{ L _ { i } , K _ { i } , S I D _ { j } , T _ { i } \}$ 发送给 $S S _ { j }$ 。

d)在接收到来自RC的消息M后,SSj计算w=L·Sj=Wi,$U I D _ { i } = K _ { i } - w _ { i } ^ { * } \in { \cal G } _ { 1 }$ ，以及 ${ T _ { i } ^ { * } } = h ( U I D _ { i } \parallel S I D _ { j } \parallel S _ { j } \parallel { w _ { i } ^ { * } } ) \in { Z _ { q } ^ { * } }$ ，并检查 ${ T _ { i } ^ { * } } = T _ { i }$ 是否成立。若成立，则用户 $U _ { i }$ 和注册中心 $R C$ 对于服务器 $S S _ { j }$ 是可信的；若不成立，则终止会话。此后， $S S _ { j }$ 生成 $c _ { i }$ 并计算 $y _ { i } = c _ { i } \cdot P \in G _ { 1 } , \ D _ { i } = y _ { i } + U I D _ { i } \in G _ { 1 } , \ G _ { i } = h ( y _ { i } \| U I D _ { i } ) \in Z _ { q } ^ { * }$ 和 $E _ { i } = h ( U I D _ { i } \parallel S I D _ { j } \parallel y _ { i } \parallel G _ { i } ) \in Z _ { q } ^ { * }$ ，通过一个不可靠信道将 $M _ { 3 }$ $= \{ S I D _ { j } , K _ { i } , D _ { i } , E _ { i } \}$ 发送给用户 $U _ { i \circ }$

e)在接收到来自 $S S _ { j }$ 的消息 $M _ { 3 }$ 后， $U _ { i }$ 计算 ${ \boldsymbol { y } } _ { i } ^ { * } = { \boldsymbol { D } } _ { i } - U I { \boldsymbol { D } } _ { i }$ ，$\boldsymbol { w } _ { i } ^ { * } = \boldsymbol { K } _ { i } - U I D _ { i } \qquad , \qquad \boldsymbol { G } _ { i } ^ { * } = h ( \boldsymbol { y } _ { i } ^ { * } \parallel U I D _ { i } )$ ， 以及$E _ { i } ^ { * } = h ( U I D _ { i } \parallel S I D _ { j } \parallel y _ { i } ^ { * } \parallel G _ { i } ^ { * } )$ ，并检查 $\boldsymbol { E } _ { i } ^ { * } = \boldsymbol { E } _ { i }$ 是否成立。若成立，则 $R C$ 和 $S S _ { j }$ 通过 $U _ { i }$ 的身份验证。此外，用户 $U _ { i }$ 计算$S K = h ( U I D _ { i } \parallel S I D _ { j } \parallel M _ { i } \parallel y _ { i } ^ { * } \parallel w _ { i } ^ { * } ) \quad \quad , \qquad O _ { i } = M _ { i } + y _ { i } ^ { * }$ 以及$V _ { i } = h ( O _ { i } \parallel S K )$ ，并通过一个不可靠信道将消息 ${ M _ { 4 } } \mathrm { { = } } \left\{ { V _ { i } , O _ { i } } \right\}$ 发送至 $S S _ { j }$ 。

f)在接收到来自Ui的消息M4后，服务器计算M=Oi－yi,$S K ^ { * } = h ( U I D _ { i } \parallel S I D _ { i } \parallel M _ { i } ^ { * } \parallel y _ { i } \parallel w _ { i } ^ { * } )$ ，以及 $\boldsymbol { V } _ { i } ^ { * } = h ( \boldsymbol { O } _ { i } \parallel S \boldsymbol { K } )$ ，并检查$\boldsymbol { V } _ { i } ^ { * } = \boldsymbol { V } _ { i }$ 是否成立。若成立，则会话密钥有效， $S S _ { j }$ 和 $U _ { i }$ 就可以使用该共享密钥 $S K$ 相互通信；若不成立，则会话被终止。

# 1.6 密码更改阶段

该阶段中，用户能够通过执行以下步骤，在不需要注册中心任何帮助的情况下，将旧密码 $P W _ { i }$ 替换为新密码 $P W _ { i } ^ { n e w }$ 。

a)用户 $U _ { i }$ 将智能卡插入终端，并在特定设备上输入 $\{ I D _ { i }$ $P W _ { i } \ S$ 和生物统计信息 $B _ { i \cdot }$ 0

b)智能卡计算 $U I D _ { i } = H ( I D _ { i } ) \in { \cal G } _ { 1 }$ ，$H P W _ { i } = h ( P W _ { i } ^ { * } \parallel I D _ { i } ^ { * } ) \cdot P \in { \cal G } _ { 1 }$ ，以及 $\boldsymbol { b } _ { i } ^ { * } = H _ { 1 } ( B _ { i } )$ ，并检查 $\boldsymbol { b } _ { i } ^ { * } = \boldsymbol { b } _ { i }$ 是否成立。若成立，则意味着 $U _ { i }$ 输入了正确的生物统计信息；若不成立，则中止会话。

c)智能卡计算 $R e g _ { i } ^ { * } = h ( U I D _ { i } \parallel H P W _ { i } )$ ，并检查 $R e g _ { i } ^ { * } = R e g _ { i }$ 是否成立。若不成立，则智能卡拒绝密码更改请求；若成立，智能卡要求用户 $U _ { i }$ 输入一个新的密码 $P W _ { i } ^ { n e w }$ 。

d)智能卡计算 $D I D _ { i } = S _ { i } - Z _ { i } = S _ { R S } \cdot U I D _ { i }$ ，$H P W ^ { n e w } = H ( P W _ { i } ^ { n e w } \parallel I D _ { i } ) \cdot P$ ， $R e g _ { i } ^ { n e w } = h ( U I D _ { i } \parallel H P W ^ { n e w } )$ ，$Z _ { i } ^ { n e w } = h ( H P W ^ { n e w } ) \cdot P$ ，以及 $S _ { i } ^ { n e w } = D I D _ { i } + Z _ { i } ^ { n e w }$ 。最后，智能卡将其存储器中旧的 $\{ R e g _ { i } , S _ { i } \}$ 替换为 $\{ R e g _ { i } ^ { n e w } , S _ { i } ^ { n e w } \}$ ，至此密码更改

阶段成功完成。

# 2 Oracle形式化安全证明

本章将使用随机Oracle 模型[11]（ROM）的形式化安全分析，对于本文协议，证明攻击者 $A$ 无法得到标志 $I D _ { i \setminus }$ 密码 $P W _ { i }$ ，生物特征 $B _ { i }$ 和会话密钥 $S K .$ 。本文首先在定义1\~4中分别解释可忽略函数、抗冲突特性和Revealoracle，其后将证明这些定理。

定义1可忽略函数对于所有正整数 $d$ ，若存在一个整数 $k _ { 0 }$ ，使得对于每个 $k \geq k _ { 0 }$ ， $h ( k ) < k ^ { d }$ ，那么 $h ( k ) < k ^ { d }$ 被称为可忽略函数。

定义2抗冲突特性 抗冲突定义是$A d \nu _ { \mathcal { A } } ^ { H } ( t ) = p r b ( r e , r e ^ { \prime } ) \Leftarrow = = _ { R } \mathcal { A }$ 以及 $h ( r e ) = h ( r e ^ { \prime } )$ ，式中，$p r b ( r e , r e ^ { \prime } )$ 表示事件 $( r e , r e ^ { \prime } )$ 的成功概率， $\scriptstyle \Longleftarrow = _ { R } { \mathcal { A } }$ 表示 $A$ 所选择的事件 $( r e , r e ^ { \prime } )$ ， $A d \nu _ { \mathcal { A } } ^ { H } ( t )$ 表示在时间周期 $t$ 中事件 $( r e , r e ^ { \prime } )$ 的优势函数。

定义3Reveal1该Reveal Oracle无条件从散列输出 $y$ 中提供输入 $r e$ ，即 ${ \boldsymbol { y } } = { \boldsymbol { h } } ( { \boldsymbol { r e } } )$ 。

定义4Reveal2已知 $G \in E _ { p } ( a , b )$ 和公共参数$Q = x \cdot G \in E _ { p } ( a , b )$ ，则该oracle 输出私有密钥 $x$ 。

定理1假定不可逆散列函数作为一个随机oracle, $A$ 知晓通信消息 $\{ S I D _ { j } , Y _ { i } , K _ { i } , V _ { i } \}$ 。那么 $A$ 依然无法检索 $I D _ { i }$ 和会话密钥 $S K$ 。

证明首先，假定 $A$ 能够借助实验性算法“多服务器三因子远程认证方案的密码分析和改进[I2]（CITRASM）”检索 $I D _ { i }$ 和 $S K$ 。则CITRASM的成功概率表示如下：

$$
S u c c e s s 1 { = } \vert P r [ E x p 1 _ { \mathcal { A , C T R A S M } } ^ { H A S H } = 1 ] - 1 \vert
$$

其中：Pr()表示算法1的成功概率。此后，本文将 ExplCrRASM的优势定义为

$$
A d \nu 1 ( t _ { 1 } , q _ { r 1 } ) = { M a x \lrcorner \{ S u c c e s s 1 \} }
$$

其中：最大值取决于RevealOracle在时间区间 $t _ { 1 }$ 中所执行的查询 $q _ { r 1 }$ 的数量。

若 $A d \nu 1 ( t _ { 1 } , q _ { r 1 } ) > \varepsilon$ ，其中 $\varepsilon > 0$ ，则攻击者能够检索 $U _ { i }$ 的 $I D _ { i }$ 和 $S K _ { \circ }$ 该条件仅在攻击者能够对不可逆散列函数进行求逆的情况下才成立[13]。由于从散列函数中检索到的输入不具备计算可行性，即， $A d \nu 1 ( t _ { 1 } , q _ { r 1 } ) < \varepsilon$ 。因此，提出的方案能够阻止 $A$ 得到$U _ { i }$ 的 $I D _ { i }$ 和会话密钥 $S K$ 。

算法1 Exp1CTRAS

1.输入： $< S I D _ { j } , Y _ { i } , K _ { i } , G , V _ { i } >$

2.结果：1或0

3.在 $K _ { i }$ 上应用Reveal Oracle，以得到信息 $P _ { i }$ ， ${ \cal { W } } _ { i }$ ， $I D _ { i }$ $S I D _ { j }$ ，以及 $R S _ { j }$ ，即

$$
( P _ { i } ^ { * } \parallel W _ { i } ^ { * } \parallel I D _ { i } ^ { * } \parallel S I D _ { j } ^ { * } \parallel R S _ { j } ^ { * } )  R e \nu e a l 1 ( K _ { i } )
$$

4.计算 $\boldsymbol { Y _ { i } ^ { * } } = \boldsymbol { P _ { i } ^ { * } } + h ( I D _ { i } ^ { * } \parallel \boldsymbol { W } _ { i } ^ { * } ) \cdot \boldsymbol { G }$

5. if $( \boldsymbol { Y } _ { i } ^ { * } = \boldsymbol { Y } _ { i } )$ 且 $\left( S I D \right) _ { j } ^ { * } = S I D _ { j } \rangle$ ，then

6. $\boldsymbol { I D } _ { i } ^ { * }$ 为用户 $U _ { i }$ 的正确身份标志

7. 在 $V _ { i }$ 上应用Reveal Oracle 以得到 $I D _ { i }$ 和 $S K$ 即：  
$( I D _ { i } ^ { * * } \parallel S K ^ { * } ) \gets R e \nu e a l 1 ( V _ { i } )$   
8. if $\left( I D _ { i } ^ { * } = I D _ { i } ^ { * * } . \right.$ ）then  
9. $\boldsymbol { S } \boldsymbol { K } ^ { * }$ 为正确的会话密钥  
10. Return 1 True  
11. else  
12. Return O False  
13. end if  
14. else  
15. Return O False  
16.end if

定理2假定散列函数作为一个随机oracle， $A$ 得到了智能卡参数 $C _ { i }$ 、 $E _ { i }$ 、 $G$ 和通信消息 $D _ { i }$ 、 $S I D _ { i }$ 、 $D I D _ { i }$ 、 $T _ { i }$ 。 $A$ 依然无法计算出用户的密码 $P W _ { i }$ ，生物特征密钥 $S P _ { i }$ 和私有密钥 $x$ 0

证明该证明与定理1相似。假定 $A$ 能够计算用户的密码$P W _ { i }$ 、生物特征密钥 $S P _ { i }$ 和私有密钥 $x _ { \circ } \ A$ 从公开信道上得到通信消息 $\{ D i , S I D i , D I D i , T i \}$ ，并从智能卡中提取数值 $\{ C _ { i } , E _ { i } , G \}$ 。那么， $A$ 执行算法以计算 $P W _ { i }$ $S P _ { i }$ 和 $x$ $E x p 2 _ { \mathcal { A } , C I T R A S M } ^ { H A S H }$ 的成功概率定义如下：

$$
S u c c e s s 2 = \left| P r [ E x p 2 _ { \mathcal { A , C I T R A S M } } ^ { H A S H } = 1 ] - 1 \right|
$$

那么，算法 $E x p 2 _ { \mathcal { A } , C I T R A S M } ^ { H A S H }$ 的优势函数定义如下：

$$
A d \nu 2 ( t _ { 2 } , q _ { r 2 } ) = M a x \mathcal { _ { A } } \{ S u c c e s s 2 \}
$$

其中：最大值取决于RevealOracle在时间区间 $t _ { 2 }$ 中所执行的查询 $q _ { r 2 }$ 的数量。

若 $A d \nu 2 ( t _ { 2 } , q _ { r 2 } ) > \varepsilon$ ，其中 $\varepsilon > 0$ ，则攻击者能够计算 $P W _ { i \setminus }$ （204号$S P _ { i }$ 和 $x$ 。该条件仅在攻击者能够对不可逆散列函数进行求逆的情况下才成立。由于从散列函数中推导出到的输入在多项式时间内不具备计算的可行性，这说明了 $A d \nu 2 ( t _ { 2 } , q _ { r 2 } ) < \varepsilon$ 。因此,提出的方案能够阻止 $A$ 得到 $P W _ { i }$ 、 $S P _ { i }$ 和 $x$ 0

算法2： $E x p 2 _ { \mathcal { A } , C I T } ^ { H A S H }$

1．输入： $< S I D _ { j } , G , D _ { i } , D I D _ { i } , T _ { i } , C _ { i } , E _ { i } >$

2.结果：1或0

3.在输入 $D _ { i }$ 上应用RevealOracle，以得到信息 $S I D _ { j } , I D _ { i }$ $P _ { i }$ 和 $A _ { i }$ ，即 $( S I D _ { j } ^ { * } \parallel I D _ { i } ^ { * } \parallel P _ { i } ^ { * } \parallel A _ { i } ^ { * } )  R e \nu e a l 1 ( D _ { i } )$

4.计算DID=IDh(P|A)

5. if $\left( D I D _ { i } ^ { * } = D I D _ { i } ^ { * } \right.$ 且 $\left( S I D _ { j } ^ { * } = S I D _ { j } ^ { } \right)$ ）then

6.在 $\boldsymbol { A } _ { i } ^ { * } = ( \boldsymbol { x } \cdot \boldsymbol { G } )$ 上应用 Reveal Oracle，以得到信息 $x$ 即 $x ^ { * } \gets R e \nu e a l 2 ( A _ { i } ^ { * } )$ （204号

7.计算P\*=T·x\*

8.if $\left( \boldsymbol { P } _ { i } ^ { * * } = \boldsymbol { P } _ { i } ^ { * } \right)$ ）then

9. $x ^ { * }$ 是RC正确的私有密钥

10. 计算 $C _ { i } - x ^ { * } \cdot G$ ，其等于 $h ( I D _ { i } \| R P W _ { i } ) \cdot G$

11. 在 $( h ( I D _ { i } \| R P W _ { i } ) \cdot G )$ 上应用 Reveal Oracle,以得到信息 $( h ( I D _ { i } \| R P W _ { i } ) )$ ，即：

$( h ( I D _ { i } \parallel R P W _ { i } ) ^ { * } ) \gets R e \nu e a l 2 ( h ( I D _ { i } \parallel R P W _ { i } ) \cdot G )$ 在 $( h ( I D _ { i } \| R P W _ { i } ) ^ { * } )$ 上应用Reveal Oracle，以得到信息 $I D _ { i }$

和 $R P W _ { i }$ ，即：

$( I D _ { i } ^ { * * } \parallel R P W _ { i } ^ { * } ) \gets R e \nu e a l 1 ( h ( I D _ { i } \parallel R P W _ { i } ) \cdot G$ 13. if $( I D _ { i } ^ { * * } = I D _ { i } ^ { * } )$ then 14. 在 $R P W _ { i } ^ { * }$ 上应用Revealoracle，以得到信息 $P W _ { i }$ 和 $S P _ { i }$ ，即 $h ( P W _ { i } ^ { * } \parallel S P _ { i } ^ { * } ) R e \nu e a l 1 ( R P W _ { i } ^ { * } )$ 15. 计算 $E _ { i } ^ { * } = h ( h ( I D _ { i } ^ { * } ) \| h ( h ( P W _ { i } ^ { * } \| S P _ { i } ^ { * } ) ) ) \mathrm { m o d } n _ { 0 } )$ （204号 16. if $( \boldsymbol { E } _ { i } ^ { * } = \boldsymbol { E } _ { i } )$ then 17. $\boldsymbol { P } \boldsymbol { W } _ { i } ^ { * }$ 为 $U _ { \mathrm { i } }$ 的正确密码， $S P _ { i } ^ { * }$ 为 $U _ { i }$ 的正确生 物特征密钥 18. Return1//True 19. else 20: Return 0 //False 21: end if 22: else 23: Return 0 //False 24: end if 25: else 26: Return 0 //False 27: end if 28: else 29: Return 0 //False 30:end if

# 3 性能分析

本章将给出所提协议与几种相关协议在安全特征、智能卡存储成本、通信成本、计算开销和估计时间方面的性能比较。

# 3.1智能卡存储成本和通信成本比较

表1给出了所提协议与其他协议在智能卡存储和通信成本（bit）上的比较。为评价智能卡存储和通信成本，本文考虑了IDi、PWi、随机nonce、散列函数均为160位，假定密钥加密或解密运算为512位。由表1可知，协议[45的智能卡存储成本和通信成本低于所提协议，但两种双因子协议[4,5]不能抵御一些安全攻击，例如用户不可跟踪性、特权内部者等。且不能提供一些安全特性，例如用户匿名性、前向加密性、高效的登录阶段和密码更改阶段。因此，付出一些额外成本得到更好的安全特性和功能是有必要的。

表1智能卡存储成本和通信成本比较(/bits)   
Table 1 Comparison of smart card storage cost and communication cost   

<html><body><table><tr><td colspan="3">/bit</td></tr><tr><td>协议</td><td>智能卡存储成本</td><td>通信成本</td></tr><tr><td>双因子认证[4]</td><td>640</td><td>2200</td></tr><tr><td>双因子改进[5]</td><td>724</td><td>2230</td></tr><tr><td>跨身份认证[7]</td><td>2640</td><td>2680</td></tr><tr><td>三因子认证[9]</td><td>1490</td><td>3460</td></tr><tr><td>三因子改进[8]</td><td>1520</td><td>2710</td></tr><tr><td>本文协议</td><td>1380</td><td>2240</td></tr></table></body></html>

# 3.2 安全性比较

抵御密码猜测攻击、用户匿名性、抵御服务器假冒攻击、抵御特权内部者攻击、抵御智能卡丢失攻击、提供前向保密性、抵御用户不可追踪性攻击和抵御会话密钥恢复攻击分别用A1\~A8表示。由表2可知，文献[4]易受到密码猜测攻击、特权内部攻击和服务器假冒攻击，其易受的攻击类型最多。文献[5]是文献[4]的改进型，可以抵御A1、A3和A4攻击，但难以抵御用户不可追踪性攻击和密钥恢复攻击。文献[8]是文献[9]的改进型，文献[8]在抵御智能卡丢失攻击时更加可靠。对于这八种攻击，文献[8.9]都表现出不错的安全性。文献[7]次之，其没有使用智能卡因子，加强了密码因子。本文协议具有提供了更好的安全保障，可以抵御更多的攻击，具有良好的安全性。本文没有列举其他更多类型的攻击。

Table 2 Comparison of safety characteristics   

<html><body><table><tr><td>协议</td><td>文献[4]</td><td>文献[5]</td><td>文献[7]</td><td>文献[8]</td><td>文献[9]</td><td>本文协议</td></tr><tr><td>A1</td><td>No</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr><tr><td>A2</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>A3</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>A4</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>A5</td><td>Yes</td><td>Yes</td><td>No</td><td>Yes</td><td>No</td><td>Yes</td></tr><tr><td>A6</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>A7</td><td>No</td><td>No</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>A8</td><td>No</td><td>No</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td></tr></table></body></html>

# 3.3计算成本和估计时间比较

为了更准确比较计算成本，本文首先定义一些符号，具体如表3所示，表3还给出了一些单次计算时间，这些时间数据来自文献[14]。

表2安全特性比较  
表3符号定义  
Table3 Symbolic definition   

<html><body><table><tr><td>符号</td><td>符号定义</td><td>单次计算时间/s</td></tr><tr><td>Th</td><td>散列函数</td><td>0.0005</td></tr><tr><td>Tme</td><td>模指数运算</td><td>0.522</td></tr><tr><td>Ts</td><td>对称密钥加密(解密 运算)</td><td>0.0087</td></tr><tr><td>Tbh</td><td>生物特征-散列函数</td><td>0.02102</td></tr><tr><td>Tfe</td><td>模糊提取器运算</td><td>0.0503</td></tr><tr><td>Tpm</td><td>双线性映射运算</td><td>0.0621</td></tr><tr><td>Tbp</td><td>点乘运算</td><td>0.0503</td></tr></table></body></html>

所提协议在注册阶段和登录验证阶段的计算成本分别为$7 T _ { h } { + } 3 T _ { p m } { + } 1 T _ { f e }$ 和 $2 3 T _ { h } { + } 1 2 T _ { p m } { + } 1 T _ { f e }$ ，而其他协议[4.5,7-9]在执行注册阶段和认证阶段的计算成本如表4所示。其中，一次模糊提取器函数的执行时间等于一次椭圆曲线点乘运算。可以看出本文协议处于中等偏上，在三因子方法中居于上游。

表4计算成本和估计时间比较  
Table4 Comparison of computation cost and estimated time   

<html><body><table><tr><td>协议</td><td>注册阶段</td><td>登录阶段</td><td>总执行时间/s</td></tr><tr><td>文献[4]</td><td>7Th</td><td>13Th +4Tme</td><td>2.098</td></tr><tr><td>文献[5]</td><td>2Th</td><td>6Th+7Tme</td><td>3.658</td></tr><tr><td>文献[7]</td><td>4Th</td><td>12Th+14Ts+Tme</td><td>0.652</td></tr><tr><td>文献[8]</td><td>6Th +4Tpm+2Tbh</td><td>18Th+11Tpm+3Tbp+1Tbh</td><td>1.157</td></tr><tr><td>文献[9]</td><td>6Th +6Tpm+4Tbh</td><td>18Th +12Tpm+4Tbp+1Tbh</td><td>1.373</td></tr><tr><td>本文</td><td>7Th+3Tpm+1Tfe</td><td>23Th+12Tpm+1Tfe</td><td>1.047</td></tr></table></body></html>

# 4 结束语

在多服务器环境下，本文提出了一种三因子的远程身份认证协议，三种因子在远程身份认证的整个过程扮演重要角色，显著提高了安全性。形式化证明验证了攻击者无法得到标志、密码、生物特征等信息。另外所提协议在运算开销等方面没有落后于其他协议。未来，本文将在满足基本安全特性的前提下，进一步降低协议的空间和时间复杂度，并考虑将所提协议延展到多种其他环境，例如医疗、云计算等。

# 参考文献：

[1]帅青红，苗苗．网上支付与电子银行[M].北京：机械工业出版社, 2015.(Shuai Qinghong,Miao Miao.Online payment and electronic banking [M].Beijing:Machinery Industry Press,2015.)   
[2] 谭志华．网络认证协议的高效模型检测研究[D].长沙：湖南大学, 2011.(Tan Zhihua.Research on effcient model checking of network authentication protocol [D]. Changsha: Hunan University,2011.)   
[3]Amin R,Islam S H,Biswas G P,et al.Cryptanalysis and enhancement of anonymity preserving remote user mutual authentication and session key agreement scheme for e-health care systems [J].Journal ofMedical Systems, 2015,39 (11): 1-21.   
[4]Pippal R S,Jaidhar C D,Tapaswi S.Robust smart card authentication scheme for multi-server architecture [J].Wireless Personal Communications, 2013,72(1): 729-745.   
[5]Wei Jianghong,Liu Wenfen,Hu Xuexian. Cryptanalysis and improvement of a robust smart card authentication scheme for multi-server architecture

[J].Wireless Personal Communications,2014,77(3):2255-2269.

[6] 龙丽萍，陈伟建，杨拥军，等．基于双因子认证技术的 RFID 认证协议 的设计[J].计算机工程与设计,2013,34(11):3726-3730.(Long Liping, Chen Weijian, Yang Yongjun,et al.Double factors based authentication protocol for RFID [J]. Computer Engineering and Design,2013,34 (11): 3726-3730.)   
[7] 张雪，李光松，韩文报，等．基于身份的跨自治域认证密钥协商协议 [J]．四川大学学报：工程科学版,2015,47(4):125-131.(Zhang Xue,Li Guangsong,Han Wenbao,et al. Identity-based authenticated key agreement protocol cross autonomous domains [J].Journal of Sichuan University: Engineering Science Edition,2015,47(4): 125-131.)   
[8]屈娟，李艳平，伍习丽．对两个基于智能卡的多服务器身份认证方案的 密码学分析与改进[J].计算机应用,2015,35(8):2199-2204.(Qu Juan, Li Yanping,Wu Xili. Cryptanalysis and improvement of two multi-server remote user authentication schemes using smart cards [J].Journal of Computer Applications,2015,35 (8): 2199-2204.)   
[9] Choi Y, Nam J,Lee D,et al. Security enhanced anonymous multiserver authenticated key agreement scheme using smart cards and biometrics. [J]. Scientific World Journal,2014,37(4): 281-292.   
[10]陈小峰，冯登国．一种基于双线性映射的直接匿名证明方案[J].软件 学报,2010,21(8): 2070-2078.(Chen Xiaofeng,Feng Dengguo.Direct anonymous atestation based on bilinear maps [J]. Journal of Software,2010, 21(8): 2070-2078.)   
[11]雷奇，尚涛，刘建伟．基于随机预言模型的量子仲裁签名方案安全性分 析[J].密码学报,2016,4(6): 619-628.(Lei Qi,Shang Tao,Liu Jianwei. Security analysis for arbitrated quantum signature scheme based on random oracle model[J]. Journal of Cryptologic Reseatch,2016,4(6): 619-628.)   
[12] Tang Yonglong.A user authentication protocol based on multiple factors [J]. Journal of Networks,2014,9(10): 1081-1090.   
[13]杨懿竣．指纹安全认证的不可逆变换技术研究 [D].深圳：深圳大学, 2015.(Yang Yijun. Research on irreversible transformation of fingerprint security authentication [D]. Shenzhen: Shenzhen University,2015.)   
[14] Chiou Shinyan, Ying Zhaoqin, Liu Junqiang. Improvement of a privacy authentication scheme based on cloud for medical environment [J]. Journal of Medical Systems,2016,40 (4): 101-115.