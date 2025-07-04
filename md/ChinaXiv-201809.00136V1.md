# 一种基于无证书签密技术的NFC移动支付方案\*

柳毅，余浩(广东工业大学计算机学院，广州 510006)

摘要：针对现有的大部分NFC移动支付方案中存在的证书管理复杂、消费者隐私保护力度不大和运行效率不高等问题，结合无双线性对的无证书签密技术和匿名技术，提出了一个高效安全的NFC移动支付方案。该方案使用动态更新的匿名交易账户实现消费者匿名交易的同时实现了交易的不可链接性，商户作为消费者和移动支付服务提供商的通信桥梁，实现了消费者离线支付。分析结果表明，该方案提供了高安全性交易和高质量的个人隐私保护的同时实现了高效率的移动支付。

关键词：无证书签密技术；匿名技术；NFC通信技术；消费者离线支付；安全支付；隐私保护中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2018.05.0350

# NFC mobile payment scheme based on certificateless signcryption technology

Liu Yi, Yu Hao (School of Computer Guangdong University of Technology, Guangzhou 51ooo6,China)

Abstract: Most ofthe existing NFC mobile payment schemes have some problems such as complex certificate management, lowconsumerprivacyprotectionandlowoperating eficiency,usingthecertificatelessigncryption technologywithoutbilinear pairing operationsand the anonymous technology to propose an eficient and secure NFC mobilepayment scheme.The cheme usesthe dynamicalyupdated anonymous trading account to realize theanonymous transactionof theconsumer and the unlinkabilityofthe transaction,the merchant actsasa bridge between theconsumer and the mobile payment service provider, enablingtheconsumer topayofline.Theresult shows thatthescheme provides high-securitytransactionsand high-quality personal privacy protection as well as high-efficiency mobile payments.

Keywords:certificatelessigncryptiontechnology;anonymous technology;nearfieldcommunication;theoflinepaymentfor the consumer; secure payment; privacy protection

# 0 引言

随着智能移动终端的普及和移动支付技术的快速发展，基于移动终端的支付方式开始逐渐取代传统支付方式（刷卡支付或者现金支付等）在支付市场中占据主导地位，根据 Analysys易观发布的《中国第三方支付移动支付市场季度监测报告2017年第2季度》数据显示，2017年第二季度，中国第三方支付移动支付市场交易规模达230408.2亿元人民币，环比增长 $2 2 . 5 0 \%$ 0其中支付宝 $5 3 . 7 0 \%$ 的占有率高居榜首，腾讯金融以 $3 9 . 1 2 \%$ 市场份额紧随其后。支付宝和微信支付所使用的移动支付技术主要是二维码支付技术，该支付技术易于实现，支付便捷，但容易受到虚假或恶意二维码的攻击，安全性较差。而NFC移动支付技术具有良好的保密性和安全性，即使在手机没有电的情况下依然可以进行支付，因此NFC移动支付技术是未来移动支付技术中最有前景的支付手段之一。

移动支付过程中，用户最关心的除了便捷性外就是安全性，而现阶段NFC 移动支付中主要是使用传统密码技术实现交易数据的安全性和用户的身份合法性认证。此类技术不仅运算量大，而且基本都存在复杂的证书管理和秘钥托管问题。

文献[1]利用无证书签名技术和伪身份技术实现了移动支付中的身份认证和用户隐私保护，但该方案使用的无证书签名技术涉及到大量的双线对运算操作，时间开销大。文献[2]为NFC移动支付技术提出了一种基于双线性对运算操作的秘钥认证方案，该方案在认证过程中使用了大量的双线性对运算操作，增加了认证时间开销，同时由于交易过程中用户使用的是真实身份ID，不能提供匿名支付功能，用户个人隐私得不到有效保护。文献[5]使用随机变化的匿名ID作为用户交易的身份，增加了用户交易过程中的隐私保护力度，但该匿名ID 是由公钥、私钥和证书组成，存在证书的复杂管理问题。文献[6]给匿名交易账户ID设定了有效期和信用值，实现了用户匿名支付的同时也实现了交易信息的不可链接性，极大的提高了用户的隐私安全，但缺点是一旦超过有效期，需要用户自己重新申请新的匿名交易账户ID和虚拟银行账户ID，便捷性受到影响。文献[7]使用了无双线性对的无证书签密技术实现了移动支付中用户的身份认证，极大的提高了身份认证效率，但该方案的交易记录对于发卡方来讲是透明的，且没有实现用户离线支付，一旦移动终端没有网络支撑，该方案无法完成交易，大大限制了交易场所的范围。文献[8]提出了一种基于NFC的用户匿名移动支付协议，用户用虚拟账户和虚拟交易账户进行交易，虚拟账户和虚拟交易账户都由用户自己产生，只有银行知道用户的真实身份，但需要用户每次交易完成后去更新他/她的虚拟账户来实现交易的不可链接性。

在NFC通信技术基础上，本文结合无双线性对操作运算的无证书签密技术和匿名技术提出一个身份认证效率高、隐私保护力度大和使用范围广的NFC移动支付方案。

# 1 相关工作

# 1.1 NFC 通信技术

NFC（near fieldcommunication）即近场通信，是由非接触式射频识别（RFID）演变而来，是在RFID技术基础上的一种扩展，工作频率为 $1 3 . 5 6 \mathrm { M H z }$ ，传输距离为 $1 0 \mathrm { c m } ^ { [ 9 ] }$ ，传输速度为106 kbps、212 kbps 和 $4 2 4 ~ \mathrm { k b p s }$ ，一次只与一台设备连接，使用硬件安全模块进行加密，因此具有较好的保密性和安全性[10]。NFC 有三种工作模式：读写器模式、卡模拟模式和点对点模式[II]。因具有良好的便捷性和安全性，NFC技术现已广泛应用在移动支付、电子票务、服务发现、数据交换、门禁系统和公交系统等。

# 1.2无证书公钥密码技术

无证书公钥密码学概念是由Al-Riyami和Paterson在2003年的亚密会上提出的[12]。与基于PKI（公钥基础设施）的传统公钥密码技术相比，无证书公钥密码技术和基于身份的密码技术一样不需要公钥证书，消除了公钥证书的复杂性管理问题，同时，在无证书公钥密码技术中，秘钥生成中心只是负责生成用户的部分秘钥，完整的秘钥是结合用户随机选取的秘密值生成的，且私钥由用户秘密存放，因此秘钥生成中心无法得知用户完整的私钥，从而克服了基于身份密码技术中私钥托管问题。可以说，无证书公钥密码技术是一种性能优良、运行效率高的公钥密码技术[13]。

公钥密码技术分为加密技术、签名技术、秘钥协商技术和签密技术。其中签密技术由Zheng[14提出，相对于对消息进行独立的加密和签名来讲，实现了加密和签名的同时降低了计算成本和通信开销。无证书公钥签密技术一般由以下七个算法[15]定义：

a）建立系统参数。KGC输入安全参数 $k$ ，输出系统私钥msk、系统公钥mpk 和系统公开参数params。b)生成部分私钥。KGC输入系统公钥 $m p k$ ，系统私钥 $m s k$ 和用户 $U _ { _ A }$ 的身份 $I D _ { \scriptscriptstyle A }$ ，输出用户的部分私钥 $d _ { _ A }$ ，并通过安全信道把d发送给用户UA。

c）生成秘密值。用户 $U _ { \scriptscriptstyle A }$ 选取个随机数 $y _ { _ A }$ 作为其秘密值。d)生成私钥。用户 $U _ { \scriptscriptstyle A }$ 输入系统公钥 $m p k$ 、用户身份 $I D _ { \scriptscriptstyle A }$ 、部分私钥 $d _ { _ A }$ 和秘密值 $y _ { _ A }$ ，输出完全私钥 $s _ { \scriptscriptstyle A }$ 。e)生成公钥。用户 $U _ { \scriptscriptstyle A }$ 输入系统公钥 $m p k$ 、用户身份 $I D _ { \scriptscriptstyle A }$ 、部分私钥 $d _ { \scriptscriptstyle A }$ 和秘密值 $y _ { _ A }$ ，输出公钥 $P K _ { A }$ 。f)签密。输入系统参数params、签密者身份 $I D _ { \scriptscriptstyle A }$ 、接收者身份 $I D _ { { } _ { B } }$ 、接收者公钥 $P K _ { _ B }$ 、签密者公钥 $P K _ { A }$ 、签密者完全私钥 $s _ { \scriptscriptstyle A }$ 和要签密的消息 $\mathrm { ~ m ~ }$ ，输出密文c。g）解密验证。输入系统参数params、签密者身份 $I D _ { \scriptscriptstyle A }$ 、签密者公钥 $P K _ { A }$ 、接收者身份 $I D _ { { } _ { B } }$ 、接收者公钥 $P K _ { _ B }$ 、完全私钥（20 $s _ { B }$ 和密文c，如果验证通过，则输出明文消息 $\mathrm { ~ m ~ }$ ，否则输出无效消息。

# 2 支付框架模型

本支付方案分为注册阶段和支付阶段，注册阶段分为消费者注册和商户注册两部分，消费者注册部分的参与方为消费者、移动支付服务提供商和可信第三方匿名生成中心，在这部分中，消费者在移动支付服务提供商处注册使用的匿名账户的合法性认证由可信第三方匿名生成中心提供。商户注册部分的参与方为商户、移动支付服务提供商和实名认证中心，在这部分中，商户身份合法性认证由实名认证中心提供。支付阶段的参与方有消费者、商户和移动支付服务提供商，消费者和商户提供相关信息给移动支付服务提供商，其中消费者提供的相关信息由商户进行转发，移动支付服务提供商提供身份认证和转账功能，若本次交易为大金额支付，消费者还需要输入支付口令才能顺利完成交易。图1为该方案的支付框架模型。

![](images/2091de2e13df23772e1d6d2809437a7faf012fb94eead4ddbf67a90556404f24.jpg)  
图1支付框架模型

# 3 方案描述

# 3.1初始化系统参数

移动支付服务提供商在自己的云服务器上输入安全参数 $k$ ，产生两个大素数 $p$ 和 $q$ ，且 $_ { p - 1 }$ 被 $q$ 整除。 $G$ 为椭圆曲线上的一个循环群， $P$ 为 $G$ 上任意一阶为 $q$ 的生成元。选取3个哈希函数： $H _ { 1 } : \{ 0 , 1 \} ^ { * } \times G  { Z _ { q } ^ { * } }$ 、 $H _ { 2 } : \{ 0 , 1 \} ^ { * }  Z _ { q } ^ { * }$ 和 $\boldsymbol { H _ { 3 } } : \boldsymbol { G } \to \left\{ 0 , 1 \right\} ^ { * }$ 。选取一个随机数 $e \in Z _ { q } ^ { * }$ 作为系统私钥并秘密保存在云服务器SE中，计算 $P _ { p u b } = e P$ 作为系统公钥。公开系统参数

$( p , q , P , P _ { p u b } , H _ { 1 } , H _ { 2 } , H _ { 3 } ) \ _ { \mathrm { ~ c ~ } }$

# 3.2用户注册

# 3.2.1消费者注册

消费者C通过移动终端上的APP（由移动支付服务提供商S开发）进行注册，具体过程如下：

a）打开移动终端上的APP，输入用户名username、登录□令 $l p w$ 、支付口令PPW、PIN码、匿名账户$A I D _ { c } ( A I D _ { c } \in \left\{ 0 , 1 \right\} ^ { * } )$ 和手机号码 $P N$ 等注册信息，其中 $A I D _ { c }$ 由可信第三方匿名生成中心生成，作为消费者在S处注册使用的唯一身份标志。计算 $H ( u s e r n a m e \parallel l p w ) \setminus H ( P I N )$ 和 $H ( p p w )$ ，保存 $H ( u s e r n a m e \parallel l p w )$ 到本地 SE 中，把 $H ( p p w ) \setminus A I D _ { c }$ 和 $P N$ 通过安全信道发送给S。

b）S接收到C发来的注册信息后，根据C提供的手机号码发送短信验证码 ${ _ { S M S } }$ 给C，确认该号码是否有效和本次注册申请是否是C本人操作。

c）C在APP上输入短信验证码并发送给S，S把接收到的SMS 与之前发送给C的短信验证码相比较，如果相同则把$A I D _ { c }$ 通过安全信道发送给匿名生成中心进行身份合法性认证，否则发送注册失败信息给C。

d）匿名生成中心收到S发送过来的 $A I D _ { c }$ ，在自己的数据库中进行查找，若数据库中存在该匿名账户，则发送身份确认回执 $C o n f i r m _ { c }$ 给S，否则发送认证失败信息给S，S再发送注册失败信息给C。

e）S 对匿名生成中心发送过来的 $C o n f i r m _ { c }$ 进行辨别，如果是身份确认回执，则保存 $H ( p p w )$ 和 $A I D _ { c }$ 在本地 SE 中，并为C开通一个电子钱包，C可以往电子钱包里进行充值，也可以进行提现操作。同时S生成匿名交易账户 $T A I D _ { _ C } \in \left\{ 0 , 1 \right\} ^ { * }$ 和会话密钥 $K E Y$ ，且 S 选择一个随机数 $r _ { S C } \in Z _ { _ q } ^ { * }$ ，计算 $R _ { c } = r _ { s c } P$ 和Dc=rsc+eH(AIDc,Rc)作为C 的部分公钥和部分私钥，最后把生成的部分密钥、 $K E Y$ 和 $T A I D _ { c }$ 通过安全信道发送给C。

f）C收到S发送过来的部分密钥后，计算等式$R _ { c } + H _ { 1 } ( A I D _ { c } , R _ { c } ) P _ { p u b } = D _ { c } P$ 是否成立，若成立则接受部分密钥和 $T A I D _ { c }$ ，计算 $D = H _ { 2 } ( H ( P I N ) ) \oplus D _ { C }$ ，并把 $D \cdot { \boldsymbol { K E Y } }$ 和 $T A I D _ { c }$ 保存在本地 SE 中，同时删除 $H ( P I N )$ 。否则发送密钥重申请求给S进行密钥重申操作。

具体注册流程如图2所示，本方案注册流程和支付流程中出现的符号，其解析如表1所示。

![](images/8d0234986ba0df81f6bd24ed2beb49f8e705b6a309a564bedbcd46912594f3a0.jpg)  
图2消费者注册流程

表1方案中符号解析  

<html><body><table><tr><td>标志</td><td>描述</td></tr><tr><td>C</td><td>消费者</td></tr><tr><td>M</td><td>商户</td></tr><tr><td>S</td><td>移动支付服务提供商</td></tr><tr><td>ppw</td><td>支付口令</td></tr><tr><td>AIDc</td><td>消费者匿名账户</td></tr><tr><td>IDM</td><td>商户的真实身份</td></tr><tr><td>HO</td><td>哈希函数</td></tr><tr><td>TLS</td><td>TLS 协议</td></tr><tr><td>SMS</td><td>短信验证码</td></tr><tr><td>Confirmx</td><td>X的身份确认信息</td></tr><tr><td>TAIDc</td><td>匿名交易账户</td></tr><tr><td>Rx</td><td>X的部分公钥</td></tr><tr><td>Dx</td><td>X的部分私钥</td></tr><tr><td>KEY</td><td>会话密钥</td></tr><tr><td>AM</td><td>商户注册验证码</td></tr><tr><td>AU</td><td>实名认证中心</td></tr><tr><td>AGC</td><td>匿名生成中心</td></tr><tr><td>Token</td><td>商户的身份标志</td></tr><tr><td>m</td><td>支付信息</td></tr><tr><td>(hx,sx)或(hx,sx)</td><td>X生成的签名</td></tr><tr><td>Cx或Cx</td><td>X生成的密文</td></tr><tr><td>=</td><td>连接运算符</td></tr><tr><td>+</td><td>异或运算符</td></tr></table></body></html>

# 3.2.2商户注册

商户M在S的官方网站上进行注册。

a）M 在注册界面中输入真实身份 $I D _ { M }$ 、IMSI码、地址address、电话号码TN、电子邮箱email和其他相关注册信息Others，并通过安全信道发送给S。

b）S 收到注册信息后，发送验证码 $_ { A M }$ 给 $\mathbf { M }$ 。

c）M在验证码输入框输入验证码，发送给S。

d)S 确认验证码的正确性，如果正确则将 $I D _ { M }$ 发送给实名认证中心AU进行身份合法性认证，若认证通过，AU将发送身份确认回执 $C o n f i r m _ { { \scriptscriptstyle M } }$ 给S，否则发送认证失败信息给S，S再发送注册失败信息给 $\mathbf { M }$ 。

e）S收到身份确认回执 $C o n f i r m _ { \scriptscriptstyle M }$ 后，计算$T o k e n = H ( I D _ { \scriptscriptstyle M } \parallel I M S I \parallel r a n d _ { \scriptscriptstyle M } ) \in \{ 0 , 1 \} ^ { \ast }$ ，选取一个随机数$r a n d _ { { \scriptscriptstyle M } } \in { \cal Z } _ { q } ^ { * }$ 。接着随机选择一个 $r _ { S M } \in Z _ { q } ^ { * }$ ，分别生成M的部分公钥和部分私钥 $R _ { \scriptscriptstyle M } = r _ { \scriptscriptstyle S M } P , D _ { \scriptscriptstyle M } = r _ { \scriptscriptstyle S M } + e H _ { \scriptscriptstyle 1 } ( T o k e n , R _ { \scriptscriptstyle M } ) $ ，并生成一个会话密钥 $K E Y$ ，最后通过安全信道把部分密钥、 $K E Y$ 和Token发送给 $\mathbf { M }$ 。

f)M收到部分密钥后，验证部分私钥的正确性，并把部分密钥、 $K E Y$ 和 $T o k e n$ 保存到 SIM卡里。

具体注册流程如图3所示。

![](images/8b26161d35fb39e68ac977296d7b238b5a906f3f16bc1a6a07ce3a6962715ce5.jpg)  
图3商户注册流程

# 3.3身份认证

a)C在APP登陆界面输入用户名usermame 和登录口令 $l p w$ 打开支付功能并输入PIN码提取部分私钥：$D _ { C } = H _ { 2 } ( H ( P I N ) ) \oplus D$ ，同时提取 $K E Y$ 和 $T A I D _ { c }$ 。接着APP 随机选择 $r _ { C } \in Z _ { q } ^ { * }$ ，计算 $Q _ { c } = r _ { c } P$ ，生成C的完全私钥$S K _ { c } = ( r _ { c } , D _ { c } )$ 。APP 随机选择 $\dot { r _ { c } } \in Z _ { q } ^ { * }$ ，计算 $T _ { c } = r _ { c } ^ { ' } P$ ，$h _ { 1 } = H _ { 1 } ( I D _ { S } , R _ { S } )$ 。与此同时， $\mathbf { M }$ 从 SIM卡中取出部分公钥 $R _ { M }$ 、部分私钥 $D _ { \cal M } \cdot \mathrm {  ~ \cal ~ K E Y ~ }$ 和 $T o k e n$ ，选取一个随机数 $r _ { { \scriptscriptstyle M } } \in Z _ { { \scriptscriptstyle q } } ^ { * }$ ，计算$Q _ { M } = r _ { M } P$ ，生成 $\mathbf { M }$ 的完全私钥 $S K _ { M } = ( r _ { M } , D _ { M } )$ 。接着再次选取一个随机数rm∈Za，计算Tm=rP，h=H(IDs,Rs），

$$
h _ { M } = H _ { 2 } ( T _ { M } \left. T o k e n \right. m ) , s _ { M } = \frac { \dot { r _ { M } } } { r _ { M } + D _ { M } + h _ { M } } ,
$$

$V _ { \scriptscriptstyle M } = \dot { r _ { \scriptscriptstyle M } } ( Q _ { s } + R _ { s } + h _ { \scriptscriptstyle 1 } P _ { \scriptscriptstyle p u b } )$ ，密文 $C _ { M } = H _ { 3 } ( V _ { M } ) \oplus m$ 和密文$\{ m \} K E Y$ 。

b）C把移动终端靠近M的POS终端接收 $\mathbf { M }$ 发送过来的信息 $\{ m \} K E Y$ ，C 用刚才提取出的 $K E Y$ 来解密密文信息得到支$h _ { c } = H _ { 2 } ( T _ { c } \parallel A I D _ { c } \parallel m ) , \quad s _ { c } = \frac { \dot { r _ { c } } } { r _ { c } + D _ { c } + h _ { c } }$ ，再从本地 SE中取出S的公钥 $P K _ { s } = ( Q _ { s } , R _ { s } )$ ，算出$V _ { c } = \dot { r _ { c } } ( Q _ { s } + R _ { s } + h _ { 1 } P _ { p u b } )$ ，密文 $C _ { c } = H _ { 3 } ( V _ { c } ) \oplus m$ ，最后把$\{ h _ { c } , s _ { c } , C _ { c } , Q _ { c } , T A I D _ { c } \}$ 发送给M。

c）M发送C的 $\{ h _ { c } , s _ { c } , C _ { c } , Q _ { c } , T A I D _ { c } \}$ 和自身的$\{ h _ { { \scriptscriptstyle M } } , s _ { { \scriptscriptstyle M } } , C _ { { \scriptscriptstyle M } } , Q _ { { \scriptscriptstyle M } } , I D _ { { \scriptscriptstyle M } } \}$ 给S。

d）S 收到M发来的签密信息后，在数据库中查找TAIDc对应的 $A I D _ { c }$ 和 $I D _ { M }$ 对应的 $T o k e n$ ，若存在则继续在本地 SE 中查找 $A I D _ { c }$ 的部分公钥 $R _ { c }$ 和 $I D _ { M }$ 的部分公钥 $R _ { \scriptscriptstyle M }$ ，结合发送过来的 $\boldsymbol { Q _ { c } } , \boldsymbol { Q _ { u } }$ 可以得到C 的完整公钥 $P K _ { c } = ( Q _ { c } , R _ { c } )$ 和 $\mathbf { M }$ 的完整公钥 $P K _ { M } = ( Q _ { M } , R _ { M } )$ 。接着计算 $h _ { 1 } ^ { ' } = H _ { 1 } ( A I D _ { c } , R _ { C } )$ ，（204号 $V _ { S } = s _ { C } ( r _ { S } + D _ { S } ) ( Q _ { C } + R _ { C } + \dot { h _ { 1 } } P _ { p u b } + h _ { C } P )$ ，解密 $C _ { c }$ 得到 $\mathrm { m } =$ CcH(Vs)，C的具体解密过程如下：

$$
V _ { \scriptscriptstyle S } = s _ { \scriptscriptstyle C } ( r _ { s } + D _ { s } ) ( Q _ { \scriptscriptstyle C } + R _ { \scriptscriptstyle C } + \dot { h _ { 1 } } P _ { p u b } + h _ { \scriptscriptstyle C } P )
$$

$$
\begin{array} { l } { \displaystyle = \frac { \dot { r _ { c } } } { { r _ { c } } + { D _ { c } } + { h _ { c } } } ( r _ { s } + { D _ { s } } ) ( r _ { c } P + { r _ { s c } } P + { h _ { 1 } } { e } P + { h _ { c } } P ) } \\ { \displaystyle = \frac { \dot { r _ { c } } } { { r _ { c } } + { D _ { c } } + { h _ { c } } } ( r _ { s } + { D _ { s } } ) ( r _ { c } P + { D _ { c } } P + { h _ { c } } P ) } \\ { \displaystyle = \dot { r _ { c } } P ( r _ { s } + { D _ { s } } ) } \end{array}
$$

$$
\begin{array} { l } { { = \dot { r _ { c } } ( Q _ { s } + r _ { s s } P + e H _ { \scriptscriptstyle 1 } ( I D _ { s } , R _ { s } ) P ) } } \\ { { = \dot { r _ { c } } ( Q _ { s } + R _ { s } + h _ { \scriptscriptstyle 1 } P _ { p u b } ) } } \end{array}
$$

由上述结果可以知道 $V _ { s } = V _ { c }$ ，因此 $\mathrm { m } { = } \ { C _ { c } \oplus H _ { 3 } ( V _ { s } ) } =$ $C _ { c } \oplus H _ { 3 } ( V _ { c } )$ ，明文恢复成功，同理可得到商户的明文。明文得到恢复后，S比较来自消费者的 $\mathrm { ~ m ~ }$ 和来自商户的 $\mathrm { ~ m ~ }$ 是否相同，若相同则对两者进行身份认证操作，否则返回认证失败信息给消费者和商户并中断本次交易。C的具体身份认证过程如下：

$$
H _ { 2 } ( s _ { C } ( Q _ { C } + R _ { C } + h _ { 1 } P _ { p u b } + h _ { C } P ) \left\| A I D _ { C } \right\| m )
$$

$$
\begin{array} { r l } & { \qquad \underset { \underset { \displaystyle } { r _ { c } + D _ { c } + h _ { c } } ( r _ { c } P + r _ { s c } P + h _ { \mathrm { c } } ^ { \prime } P + h _ { c } P + h _ { c } \vert P ) \vert } { \overset { \cdot } { = } } \lbrace A I D _ { c } \rbrace } \\ & { = H _ { 2 } ( \frac { r _ { c } ^ { \prime } } { r _ { c } + D _ { c } + h _ { c } } ( r _ { c } P + D _ { c } P + h _ { c } P ) \vert A I D _ { c } \vert \vert m ) } \\ & { = H _ { 2 } ( \frac { r _ { c } ^ { \prime } } { r _ { c } + D _ { c } + h _ { c } } ( r _ { c } P + D _ { c } P + h _ { c } P ) \vert A I D _ { c } \vert \vert m ) } \\ & { = H _ { 2 } ( r _ { c } ^ { \prime } P \vert \vert A I D _ { c } \vert \vert m ) } \\ & { = H _ { 2 } ( T _ { c } \vert \vert A I D _ { c } \vert \vert m ) } \\ & { = \relax _ { h } } \end{array}
$$

若上式成立，则身份认证通过。同理可认证商户M的身份。当两者身份都得到认证后，则接受支付信息 $\mathrm { ~ m ~ }$ 。

# 3.4支付交易

支付交易分两种情况，分别是小金额交易和大金额交易。

1)小金额交易

S对消费者和商户完成身份认证后，将根据 $\mathrm { ~ m ~ }$ 上的相关支付信息进行转账，若C的电子钱包余额不足但开通了银行快捷支付，那么消费者可以选择使用银行快捷支付完成交易。若电子钱包和银行账户的余额都不足，或消费者没有选择银行快捷支付，那么此次交易失败，S将发送交易失败信息给C和 $\mathbf { \delta M }$ 。

2)大金额交易

S 对消费者和商户完成身份认证后，发送 $\{ h _ { s } , s _ { s } , C _ { s } \}$ 给M,其中 $C _ { s }$ 是支付口令请求信息的密文。C 确认POS 终端上的支付金额正确后，在POS 终端上输入支付口令 $p p w$ ，发送$\{ h _ { M } ^ { ' } , S _ { M } ^ { ' } , C _ { M } ^ { ' } \}$ 给S，其中 $C _ { M } ^ { ' }$ 是 $H ( p p w )$ 的密文。S把收到的$H ( p p w )$ 与本地 SE中的值对比，若相同，则执行与小金额支付同样的支付流程，否则终止本次交易，并发送交易失败信息给C和 $\mathbf { \delta M }$ 。

# 3.5交易完成

交易成功后，S发送 $\{ h _ { _ { S M } } ^ { ' } , S _ { _ { S M } } ^ { ' } , C _ { _ { S M } } ^ { ' } , h _ { _ { S C } } ^ { ' } , S _ { _ { S C } } ^ { ' } , C _ { _ { S C } } ^ { ' } \}$ 给M，其中$C _ { S M } ^ { ' }$ 是S用M的公钥加密的支付成功回执的密文，而 $C _ { s c } ^ { ' }$ 是S用C的公钥加密的支付成功回执和新的匿名交易账户 $T A I D _ { c } ^ { ' }$ 的密文。 $\mathbf { M }$ 收到信息后，解密 $C _ { S M } ^ { ' }$ 得到支付成功回执并秘密存储，并把 $\{ h _ { s c } ^ { ' } , S _ { s c } ^ { ' } , C _ { s c } ^ { ' } \}$ 发送给用户 $\mathrm { ~ \varsigma ~ } _ { \mathrm { ~ \ / ~ C ~ } }$ ，C解密 $C _ { s c } ^ { ' }$ 得到支付成功回执和 $T A I D _ { c } ^ { ' }$ 并秘密存储到本地 SE 中，删除旧的 $T A I D _ { c }$ ，到此整个交易结束。

具体支付流程如图4所示（虚线表示只有大金额交易需要执行的步骤，实线表示大金额交易和小金额交易都必须要执行的步骤)。

![](images/dbe270a34806f0ca1ce9ae55d9d3ea8950fcda2aacf5e9caf450341eb2b8033b.jpg)  
图4支付流程

# 4 安全性分析

# 4.1抵抗数据窜改

M 和C之间传输的支付信息 $\mathrm { ~ m ~ }$ 通过会话密钥 $K E Y$ 进行加密，没有在S上注册的恶意用户在没有获得正确 $K E Y$ 的情况下无法解密获得正确的支付信息；若C是恶意用户，企图通过修改支付信息m来实现不正当交易，假设修改后的支付信息为$m ^ { ' }$ ，因S在进行用户身份认证之前会先比较来自C的支付信息 $m ^ { ' }$ 和来自 M的支付信息 $\mathrm { ~ m ~ }$ ，一旦发现 $m \neq m ^ { ' }$ ，则证明支付信息被恶意窜改，S将终止本次交易；若M是恶意用户，在输入支付口令阶段，C可以在商户的POS终端上确认S发送过来的支付金额是否合理，一旦发现支付金额有误，则可以直接拒绝在POS终端上输入支付口令，终止本次交易；假设攻击者冒充S接收签密信息，试图修改支付信息 $\mathbf { m }$ 来破坏本次交易，因攻击者无法获得S的私钥，故无法解密获得正确的支付信息 $\mathrm { ~ m ~ }$ 即无法对支付信息 $\mathbf { m }$ 进行修改。

# 4.2 抵抗假冒攻击

假设攻击者试图利用C的账户进行非法交易，因为攻击者无法得到C的手机，而C的部分私钥 $D _ { c }$ 只存储在C的手机中，所以攻击者无法获得正确的 $D _ { c }$ ，即使攻击者得到了C的手机，但因 $D _ { c }$ 是以 $D = H _ { \scriptscriptstyle 2 } ( H ( P I N ) ) \oplus D _ { \scriptscriptstyle C }$ 的加密方式存储在手机中，攻击者在不知道C 的 $P I N$ 码的情况下，依然无法获得正确的$D _ { c }$ 。因此，攻击者试图通过使用伪造的 $D _ { c } ^ { ' }$ 进行交易。攻击者计算 $s _ { c } ^ { ' } = \frac { r _ { c } ^ { ' } } { r _ { c } + D _ { c } ^ { ' } + h _ { c } }$ ，并通过 $\mathbf { \delta M }$ 发送给 S，S 把 $s _ { c } ^ { ' }$ 代入以下等式进行身份认证：

$$
\begin{array} { r l r } {  { \quad \quad \quad } } \\ & { = H _ { 2 } ( \frac { \displaystyle r _ { C } ^ { \prime } } { \displaystyle r _ { c } + D _ { c } ^ { \prime } + h _ { c } } ( r _ { c } P + r _ { s c } P + h _ { \mathrm { i } } ^ { \prime } e P + h _ { c } P ) \| A I D _ { c } \| m ) } \\ & { = \displaystyle H _ { 2 } ( \frac { \displaystyle r _ { C } ^ { \prime } } { \displaystyle r _ { c } + D _ { c } ^ { \prime } + h _ { c } } ( r _ { c } P + D _ { c } P + h _ { c } P ) \| A I D _ { c } \| m ) } \\ & { } & { \qquad \quad \neq \ h } \end{array}
$$

故身份认证失败，交易终止。

# 4.3抵抗重放攻击

假设M是恶意用户，试图通过不断发送已经完成交易的签密信息给S来进行非法交易，但因为每次交易所使用的公私钥都不相同，故生成的签密信息也不相同，又因为上一次交易完成的签密信息依然保存在S的服务器上，一旦S发现此签密信息已存在于服务器上，则会直接丢弃此签密信息，因此本方案可以有效防护恶意商户的重放攻击。

# 4.4 身份匿名性

C 与M交易时使用的是S分发的匿名交易账户 $T A I D _ { c }$ ，所以M和攻击者都不能够从中获取C的真实身份，除此之外，C在 S 中注册所使用的是匿名生成中心分发的匿名账户 AIDc，故S也不知道消费者C的真实身份，因此本方案充分地实现了消费者匿名交易，可以很好地保护消费者个人隐私。

# 4.5 不可否认性

当交易存在争议时，C向S提供支付成功回执和匿名账户$A I D _ { c }$ 和 M向S提供支付成功回执和真实身份 $J D _ { \scriptscriptstyle M }$ ，S 根据支付回执中的订单号和交易时间在服务器上查找历史交易记录，然后验证历史交易记录中的交易金额和双方交易账户名与支付回执中的是否一致，若都一致，说明交易正常，若有其中一项不同，则说明交易存在异常。若两者有一方试图否认本次异常交易，但因历史交易记录中保存有双方的签名，因此不存在否认成功。

# 4.6不可链接性

C 与 M 进行交易时使用的匿名交易账户 $T A I D _ { c }$ 在每次交易完成之后，都会进行更新，即实现了一次一户，即使C在同一家商店购买同样的商品，因交易时C使用的 $T A I D _ { c }$ 每次都不一样，因此M想获取C的真实身份是困难的。同时，因每次交易时 $T A I D _ { c }$ 的不同，M无法把每次购买的商品信息与真正的C相关联，因此M企图利用商品属性推断出C的职业、兴趣爱好或者健康状况等相关个人隐私信息是困难的。同理，即使在M与S之间传输的加密信息被攻击者暴力破解了，攻击者也无法推断出C的相关个人隐私信息，实现了交易的不可链接性，很好的保护了消费者的个人隐私。

# 4.7消费者离线支付

C与M的数据交换是通过NFC技术进行的，而M又作为  
C和S之间的通信桥梁，因此C即使在没有网络的情况下依然  
可以顺利完成交易，即实现了消费者离线支付。  
表2是本方案与文献[1,2]的安全性比较，其中Y代表可抵抗，N代表不可抵抗。

表2安全性对比  

<html><body><table><tr><td>安全属性</td><td>文献[1]</td><td>文献[2]</td><td>本方案</td></tr><tr><td>数据窜改</td><td>N</td><td>Y</td><td>Y</td></tr><tr><td>假冒攻击</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>重放攻击</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>身份匿名性</td><td>Y</td><td>N</td><td>Y</td></tr><tr><td>不可否认性</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>不可链接性</td><td>Y</td><td>N</td><td>Y</td></tr><tr><td>消费者离线支付</td><td>Y</td><td>Y</td><td>Y</td></tr></table></body></html>

# 5 效率分析

本文采用文献[4]中的方法对各方案进行效率分析，根据文献[1,3,4]的实验数据可以得到表3中的不同类型的密码操作时间开销，其中服务器端的时间开销是建立在MIRACLE[16密码库上的，服务器端搭配了一个 $\mathrm { P I V } 3 \mathrm { G H z }$ 的处理器、内存为512MB 和使用WindowsXP操作系统。客户端搭配了一个 $2 0 6 \mathrm { M H z }$ 的 ARM处理器，使用Linux操作系统，在其上的各个密码操作时间开销是通过以下等式进行估算的： $t _ { c } = t _ { s } \times 3 0 0 0 / 2 0 6  ( { t _ { c } }$ 表示客户端的估计时间， $t _ { s }$ 表示服务器端的密码操作时间)。

表3不同类型密码操作时间开销 /ms  

<html><body><table><tr><td>密码操作类型</td><td>服务器端</td><td>客户端</td></tr><tr><td>双线性对上的标量积</td><td>6.38</td><td>92.91</td></tr><tr><td>椭圆曲线上的标量积</td><td>2.21</td><td>32.18</td></tr><tr><td>双线性对运算</td><td>20.04</td><td>291.84</td></tr><tr><td>双线性对上的幂运算</td><td>10.64</td><td>154.95</td></tr></table></body></html>

根据表3中各个密码操作时间开销可知，在文献[1]里，生成签名到完成身份认证整个过程中，客户端需要执行1次双线性对运算、2次双线性对上的标量积运算和2次双线性对上的幂运算，而服务器端需要执行2次双线性对运算和1次双线性对上的幂运算，因此总的时间开销为 $8 3 8 . 2 8 \mathrm { m s }$ ；在文献[2]里，客户端需要执行5次椭圆曲线上的标量积运算和1次双线性对运算，而服务器端需要执行2次椭圆曲线上的标量积运算和1次双线性对运算，因此总的时间开销为 $4 7 7 . 2 \mathrm { m s }$ ；在本方案里，因为消费者和商户生成签名可以同时进行，因此客户端花费的时间为3次椭圆曲线上的标量积运算，而服务器端可以同时对消费者和商户的签名进行认证，所以服务器端的时间开销为3次椭圆曲线上的标量积运算，因此，总的时间开销为103.17毫秒。整个身份认证的过程需要在各个密码操作花费的时间如图5所示。

![](images/a6dfca737631c8d86f4ba3db97557c516f8768bffb32ea538264833d21d3933e.jpg)  
图5密码操作时间开销(以ms 为单位)

文献[1,2]和本方案整个身份认证过程所需时间开销如表4所示。

表4时间开销 /ms  

<html><body><table><tr><td>方案</td><td>时间开销</td></tr><tr><td>文献[1]</td><td>838.28</td></tr><tr><td>文献[2]</td><td>477.20</td></tr><tr><td>本方案</td><td>103.17</td></tr></table></body></html>

根据表4可知本方案从生成签名到完成身份认证所需要的时间开销比文献[1]快了约 $8 7 . 6 9 \%$ ，比文献[2]快了约 $78 . 3 8 \%$ 因此本方案效率更快，实用性更强。

# 6 结束语

本文结合无证书签密技术和匿名技术提出了一个安全高效的 NFC 移动支付方案，消费者部分私钥与其PIN 码结合加密存储在移动终端中，增强了部分私钥防泄露属性；消费者与移动支付服务提供商进行通信使用的是可信第三方匿名生成中心分发的匿名账户，实现了消费者通信匿名；消费者与商户进行通信使用的是移动支付服务提供商分发的匿名交易账户，且该账户每次交易完后会得到更新，实现了匿名通信的同时也提供了交易的不可链接性，提高了消费者隐私安全；消费者每次交易都会使用新生成的私钥进行签名，实现一次一密，提高了身份认证的安全性，且具有抗重放攻击属性；消费者与移动支付服务提供商的信息交换是通过商户转发的，实现了消费者离线支付，扩大了交易场所的范围。分析结果表明，该方案提高了NFC移动支付安全性的同时很好的保护了消费者个人隐私，且提高了支付效率，是一种安全高效的移动支付方案。

# 参考文献：

[1]Qin Zhen, Sun Jianfei,Wahaballa A,et al.A secure and privacy-preserving mobile wallet with outsourced verification in cloud computing [J]. Computer Standards& Interfaces,2017,54: 55-60.   
[2]Chen Xinyi, Choi K,Chae K.A secure and efficient key authentication using bilinear pairing for NFC mobile payment service [J].Wireless Personal Communications,2017,97(1): 1-17.   
[3] He Debiao,Chen Jianhua,Zhang Rui.Eficient and provably-secure certificateless signature scheme without bilinear pairings.[J]. International Journal of Communication Systems,2014,25 (11): 1432-1442.   
[4]Cao Xuefei, Zeng Xingwen,Kou Weidong,et al. Identity-based anonymous remote authentication for value-added services in mobile networks [J].IEEE Trans on Vehicular Technology,2009,58(7):3508-3517.   
[5]Eun H,Lee H, Oh H. Conditional privacy preserving security protocol for NFC applications [J].IEEE Trans on Consumer Electronics,2013,59 (1): 153-160.   
[6]Luo Jianing,Yang M H, Huang S Y.An unlinkable anonymous payment scheme based on near field communication [J]. Computers & Electrical Engineering,2016,49:198-206.   
[7]王亚涛，赵波，陶威．基于无证书公钥密码的 HCE 移动支付方案[J]. 计算机工程与设计,2017,38(1):32-36.(Wang Yatao,Zhao Bo,Tao Wei. HCE mobile payment scheme on CL-PKC [J]. Computer Engineering and Design,2017,38 (1): 32-36.)   
[8] Chen Shangwen,Tso R.NFC-based Mobile Payment Protocol with User Anonymity [C]// Proc of the 11th Asia Joint Conference on Information Security. n2016: 24-30.   
[9]贾凡，佟鑫.NFC 手机支付系统的安全威胁建模[J].清华大学学报: 自然科学版,2012,52(10):1460-1464.(JiaFan,Tong Xin.Threat modeling for mobile payments using NFC phones [J]. Journal of Tsinghua University (Science and Technology),2012,52(10): 1460-1464.)   
[10]张玉清，王志强，刘奇旭，等.近场通信技术的安全研究进展与发展趋 势[J].计算机学报，2016,39(6):1190-1207.(Zhang Yuqing,Wang Zhiqiang, Liu Qixu,et al. Research progress and trends on the security of near field communication [J]. Chinese Journal of Computers,2016,39 (6): 1190-1207. )   
[11]RajeshGP,PattarP,Divya MN,etal.Near field application:NFC smart notice board [C]//Proc of the 13th International Conference on Wireless and Optical Communications Networks.2016:1-5.   
[12]刘文浩，许春香．无双线性配对的无证书签密方案[J]．软件学报,2011, 22(8): 1918-1926. (Liu Wenhao，Xu Chunxiang.Certificateless signcryption scheme without bilinear pairing [J].Journal of Software,2011, 22 (8): 1918-1926.)   
[13]张福泰，孙银霞，张磊，等．无证书公钥密码体制研究[J].软件学报， 2011,22 (6):1316-1332.(Zhang Futai,Sun Yinxia,Zhang Lei,et al. Research on Certificateless Public Key Cryptography [J]. Journal of Software,2011,22(6): 1316-1332.)   
[14] Zheng Yuliang.Digital signcryption or how to achieve cost (signature & encryption) $\ll$ cost (signature）+cost (encryption） [C]// Advances in Cryptology. Berlin: Springer,1997,1294:165-179.   
[15]Selvi S S D,Vivek S S,Rangan CP.Cryptanalysis of certificateless signcryption schemes and an efficient construction without pairing [C]// Proc of International Conference on Information Security and Cryptology. Berlin: Springer-Verlag,2009:75-92.   
[16] Shamus Software Ltd.Miracl library [EB/OL].[2018-05-10].http://www. shamus.ie/index. php?page=home.