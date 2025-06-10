# 基于SecOC的车载网络通信安全模型研究

章意，李飞，张森葳(成都信息工程大学 网络空间安全学院，成都 610200)

摘要：车载电子设备的增加使得车载网络面对越来越多的威胁。车载网络中电子控制单元(ElectronicControlUnit，ECU)无认证、控制器局域网络(Controler Area Network,CAN)通信数据无加密等缺陷使得车载网络易遭受重放、ECU注入、中间人伪造消息、窃听等恶意攻击，造成严重后果。针对现在的车载网络威胁现提出一种基于 SecOC 的车载网络安全通信模型，该模型使用 SM4的密码算法与基于Bkake2s的改进密钥管理，实现车载 ECU的认证和车载网络消息的加密与认证。最后经过分析与测试，该模型可以保护车载网络安全并更高效。

关键词：板端加密通信；车载网络；SM4；Blake2s；PBKDF2；硬件安全模块 中图分类号：TP39 doi:10.19734/j.issn.1001-3695.2021.12.0703

Research on security model of vehicle network communication based on SecOC

Zhang Yi, Li Feit, Zhang Senwei (School of Cyberspace Security,Chengdu University ofinformation engineering,Chengdu 61020,China)

Abstract: The increase ofin-vehicle electronic equipment makes the in-vehicle network facemore and more threats.The lack ofauthenticationof theElectronicControl Unitinthein-vehiclenetworkandthe lackof encryptionofthecommunication dataof the Controller Area Network make the in-vehicle network vulnerable toreplay,ECU injection,man-in-the-midle forged messages,eavesdropping,etc, Witch make serious consequences. Aiming at the curent vehicle network threats,a vehicle network security communication model based on SecOC is proposed.This modeluses the SM4 cryptographic algorithm and the improved key managementbased on Bkake2s to realize the authentication of the vehicle ECU and the encryptionandauthenticationofthevehiclenetworkmessage.Finalyafteranalysisand testing,themodelcanprotectthe invehicle network security and be more efficient.

Key words: securityonboard communication; in-vehicle network;SM4;Blake2s; password-based keyderivation function 2: hardware security moduel

# 0 引言

车端威胁复杂，涉及众多车载组件，文献[1]中阐述了CAN和ECU存在的多种安全漏洞，车载网络在攻击方式多样化的如今成为首当其冲的薄弱点。

2016年，汽车开放系统架构4.3(AUTomotive open systemarchitecture，AUTOSAR)标准中提出了SecOC用于提高PDU(protocaldataunit)上关键数据的安全性，保护ECU通信[2]。SecOC的细节将在1.1节说明。此后，国内外学者关于SecOC模块的研究尚处于初步探索阶段。

国内的研究中，文献[3\~8]都实现了SecOC模块中的ECU通信。吴志红等人[4]基于CMAC实现MAC认证，但没有细节说明数据帧的格式；罗峰[5]使用会话密钥加密通信消息，但ECU需要保管多个密钥并不安全；黄大权[将会话密钥初始化写入ECU，造成ECU存储压力且密钥易丢失；罗超7基于CAMC-AES截取16位的MAC码，安全性有限，且根据数据帧信息动态从本地密钥库更新会话密钥会造成额外的计算开销，延迟通信；刘毅[8实现了车载CAN通信的认证与加密，但ECU存储与计算压力都超过现有框架。

国外对于车载网络的安全通信研究较早，在SecOC尚未推出时，已有学者设计了符合AUTOSAR架构的安全通信模型。Bohner等人[9扩展了AES用于数据加密，但是并没有具体描述模型的流程，并且软件形式的保护不完善，缺乏密钥管理；Radu等人[o]提出了一种CAN认证协议LeiA，使用派生的会话密钥实现ECU间身份认证，但是两两认证易使车载通信时效低，ECU需要保存消息ID对应的长期密钥，这存在泄露风险；Nyurnberger 等人[11]设计了一种vatiCAN 模型使用长期密钥验证消息，但固定密钥并不是安全策略，且周期性的新鲜度值更新存在概率重放攻击漏洞。Jo等人[12]在文献[10,11]的基础上提出VuICAN，但其MAC验证需要加倍的通信量，消息ID与会话密钥绑定验证的方式使得密钥管理复杂。

待到SecOC出现后，Wu 等人[3]在 SecOC中使用2字节的新鲜度值和2字节的基于AES的MAC认证码；Rosenstatter[14,15]对于官方 SecOC 的Profile3 进行了一定的修改，在其基础上提出了Profile4，但增加了车载网络的通信负担，易引起混乱；Bellad等人[16]将CINNAMON作为SecOC模块的继承与扩展，实现数据的加密，但是密码管理不清晰；Yang 等人[7设计了KDC风格的密钥分发协议SKDC，但方案中ECU存储和计算压力过大；Yalcin 等人[18]在硬件中实现AES算法与SecOC的E2E安全通信，但密钥存在遗失风险。

可见基于SecOC的安全模型虽然实现了消息认证与验证，但依然存在以下问题需要解决：

a）明文传输，不能防窃取和中间人攻击。  
b)会话密钥缺乏安全地管理。  
c）通信ECU缺乏有效认证手段。  
d）保证安全性时，通信效率有待提升。  
本研究基于SecOC设计一种车载网络安全通信模型：首

先根据汽车安全完整性等级(Automotive Safety IntegrityLevel，ASIL)将ECU划分安全等级，其次在点火阶段使用Blake2s改进的PBKDF2算法来计算会话密钥，接着再通信阶段使用SM4加密解密通信数据、Blake2s计算验证MAC，最后分析并验证模型的安全性与效率。

# 1 相关知识

# 1.1 SecOC

SecOC[2]提供完整性与真实性保障的SecuredI-PDU，它包含一个Authentic I-PDU,Freshness Value 以及Authentictor,如图1所示，其中AuthenticI-PDU是一个任意的AUTOSARI-PDU，Authentictor是消息认证码MAC或者签名，FreshnessValue是新鲜度值，分为计数器或时间戳两种。

![](images/46564267467154eb3bbccba18182049a32d3994aef621be8c89a8812ac6959f8.jpg)  
图1Secured I-PDU 结构图  
Fig.1Structure diagram of secured i-pdu

1.2 HSM

硬件安全模块(Hardware Security Module，HSM)是一个用于管理密钥和提高数据加解密处理速度的物理计算设备，通常形为插入式卡片或外接设备，能够为数据提供安全性保障[19]。硬件安全模块提供比软件更高级别的安全，具有不可复制性，抗渗透性，抗非法的连接及窜改。所以使用HSM可以更快地计算的同时，也可以提供更高的安全性，并且硬件安全模块在设计之初，作为一种外接式设备，天生适合现在的车联网环境。例如欧洲资助的项目之一，EVITA为车载网络安全开发了HSM模块，HSM采用专用硬件实现，优化固件之后，计算速度快于软件，具有低延迟，高性能和节约成本的特点。本研究中使用已经写入算法并优化固件的HSM完成相关计算。

# 1.3 CAN-FD

CAN-FD(CANwithFlexibleData-Rate)是BOSCH推出的CAN改进版，可支持最高64字节长度的数据载荷，并且可调速率最高达8Mbps[20]。文献[2]中表明，AUTOSAR对CAN-FD 的支持度与推荐度非常高。CAN-FD具有更快的对象池传输、更低的总线负载使用、更短的最坏情况响应时间和更低的抖动。CAN-FD的引入是在正确的时间进行的正确的创新，该技术能够跟上汽车以太网技术带来的未来通信机制和网络概念。

# 2 模型设计

# 2.1 ECU安全等级划分

划分ECU等级是为了更好地利用总线的资源，使得车载网络通信效率高，时延低，根据ECU的安全需求，对数据帧进行CRC校验，HMAC验证或者数据加密。Woo[21]基于汽车安全完整性等级(Automotive Safety IntegrityLevel，ASIL)设计了ASL0-3四个等级的ECU划分方案。同时刘毅[8也根据ASIL规则划分了数据帧安全性等级，但可惜的是CAN数据帧的长度限制了安全等级的细节设计。

ASIL 是ISO26262中对车辆进行危害分析与风险评估(hazardanalysisandriskassessment，HARA)而得到的对于相关危害进行识别归类的方法。ASIL制定了四级的程度划分，由低到高分别为A、B、C和D。本研究依据ASIL将ECU划分如表1所示。

ECUs1以服务为主的ECU节点，包括座椅ECU、电子仪表盘(EIS)、收音机等和以感知功能为主的ECU节点，包括速度感知ECU、夜视ECU等。ECUs2以智能决策为主的ECU节点，包括信号识别ECU，轮胎压力监测系统(TPMS)等。ECUs3以协同控制为主的ECU节点，包括自动变速器控制(ECT)、引擎管理系统(EMS)、自动车身水平控制(ALC)等。ECUs_4以安全相关功能为主的ECU节点，包括安全气囊系统(SRS)、汽车安全辅助系统(SAS)、自动防抱死刹车系统(ABS)等。

表1ECU等级划分  
Tab.1ECUclassification   

<html><body><table><tr><td>ASIL 等级</td><td>ECU类型</td><td>通信设计</td><td>安全等级</td></tr><tr><td>A</td><td>ECUs_1</td><td>Blake2s/2B</td><td>NSL0</td></tr><tr><td>B</td><td>ECUs_2</td><td>Blake2s/4B</td><td>NSL1</td></tr><tr><td>C</td><td>ECUs_3</td><td>SM4+Blake2s/6B</td><td>NSL2</td></tr><tr><td>D</td><td>ECUs_4</td><td>SM4+Blake2s/8B</td><td>NSL3</td></tr></table></body></html>

# 2.2 改进的PBKDF2

PBKDF2是RSA实验室在PKCS#5标准中提出的一种密钥派生函数，该函数基于伪随机函数HMAC-SHA1进行多轮迭代，输出不定长度的密码序列。PBKDF2以其快速与安全性应用于诸多场景，如区块链中的分层确定性钱包，OpenSSL或其他物联网环境等。但是PBKDF2-HMAC-SHA1存在以下问题：

1)HAMC中的填充计算存在冗余问题。2）相较而言，SHA1存在安全性低的问题，需要足够的迭代次数才可以保证密钥安全性，且低安全度的密钥易被GPU阵列或彩虹表破解。

现有的优化方案中，基于硬件的加速，或者基于结构优化的加速[22]，或为了安全性的提升使用SHA-256 算法等并不适合车联网中计算性能受限的环境和高安全要求，尤其是官方推荐算法迭代轮数达到10000次才具备较高的安全性，所以本研究中提出了基于Blake2s的改进PBKDF2算法，Blake2s-PBKDF2。

Blake2[23]是SHA-3决赛的入围者Blake的优化版本，其安全性不低于最新标准的 SHA-3，但计算速度快于 SHA-1。所以Blake2更适合作为密码哈希算法的伪随机函数(PseudorandomFunction,PRF)[20]，并且Blake2 在硬件中已可以实现[24]。其中Blake2s是Blake2针对32位平台优化的计算模式，更适合车载系统。在本研究中，本文拟使用Blake2s代替HMAC-SHA-1作为PBKDF2的PRF函数，在计算受限的车联网环境中，本算法可以使用更低的迭代轮数实现更高的安全性，同时计算效率更高，同时Blake2s可选长度1至32字节，更适用于分级策略。Blake2s-PBKDF2伪代码描述如下：

算法1 Blake2s-PBKDF2

输入：Password,Salt,Iterations,Dklen。  
输出：DK[0：DKlen]。  
a）r = ceil(DKlen/Hlen)。  
/／执行块数，Hlen 为PRF 函数得到的长度，推荐并行程度为rb)for 1 to r： ${ \textsf { T } } =$ Blake256(Password，Salt |li)； $\mathsf { U } = \mathsf { T }$ 。c）for 1 to Iterations：T $\mathbf { \sigma } = \mathbf { \sigma }$ Blake256(Password，T)； $\textsf { U } =$ U XORT。//此c)步骤代码在b)循环中执行  
d) ${ \mathsf { D } } { \mathsf { K } } \ = \ { \mathsf { D } } { \mathsf { K } }$ IlU。执行后转步骤 b)  
e)return DK[0：DKlen]

# 2.3 ECU自检

为了防止车辆ECU程序中被植入木马，ECU固件被刷入恶意代码，或者车载网络中被接入非法信息收发设备，所以车载网络的防护中，对ECU节点进行认证。Choi[25]利用CAN的电信号特性来区分发送方节点，但方案对于ECU固件刷新和ECU被劫持没有有效的防护。本研究设计了一种在汽车启动时进行ECU检测的方案，拟在点火阶段完成ECU节点哈希指纹值的验证。汽车启动时ECU自检方案如下：

a）在汽车出厂时，计算各ECU节点的固件与软件hash值，并将节点ECUi的hash值与其ID，即EIDi对应存储在车载T-Box 中的不可窜改存储介质中。其中HMAC表示Blake2s算法，EFWi表示ECUi的固件软件代码。

$$
\scriptstyle M A C _ { i } = H M A C \left( E F W _ { \mathrm { i } } \parallel E I D _ { \mathrm { i } } \right)
$$

b）汽车启动时，ECUi将自己的软件固件数据和ECUIDi经过CANIF模块传递和CANTP模块封装后，成为I-PDU格式，由PDURouter 转发至 SecOC 模块，SecOC 将该I-PDUi传进HSM设备中。HSM设备将Blake2s计算的hash值返回至 SecOC。

c)SecOC将hash值经过RTE层传递至T-Box，T-Box根据本地存储的出厂哈希值对比，若对比通过，则返回ID与通过Flag，若对比失败，则返回Error报警信息。

# 2.4会话密钥管理

使用固定密钥加密数据并不可取，所以本研究中不使用长期的出厂密钥，在车辆启动时根据车内环境信息的真随机数使用Blake2s-PBKDF2算法派生出会话密钥，并设置过期时间(车辆启动至熄火)保存在HSM的安全存储介质内。该存储介质只有HSM内固定的程序可读，HSM模块可设置在车载T-BOX中，不增加额外硬件成本。汽车启动时密钥生成方案设计如下：

a)汽车点火启动时，HSM 模块取电池信号特征，选取128bits长度为随机序列，选取16bits为 salt值。

b）调用HSM内已经编译好的Blake2s-PBKDF2算法模块，计算DK。其中BKDF表示改进的Blake2s-PBKDF2算法，random为随机序列，salt为盐值，c为函数内部执行轮数，dkLen为期望输出的密钥长度。

$$
D K { = } B K D F ( { \mathrm { r a n d o m } } , { \mathrm { s a l t } } , { \mathrm { c } } , { \mathrm { d k l e n } } )
$$

c）步骤b)中得到的DK长度为256bits，取高128bits为车载网络的会话加密密钥(SessionKey，SK)，保存在HSM的安全存储内。

会话密钥分发需要考虑安全性与效率性，故而文献[8]使用RSA证书分发的方式不适用于车载网络，文献[5]的组会话密钥致使经过多轮密钥分发才能通信，文献[7,16]在SecOC中添加了数据加密的操作，但存在密钥管理问题。文献[21]设计的密钥分发过程较为复杂，每一个ECU都要与网关交互数次，通信量较大。本研究采用与文献[17]相近的KDC风格的密钥分发协议。本研究中引入密钥服务器(KeyServer，KS)来分发SK，KS 设置在T-BOX中，与HSM模块集成。假设需要加密的ECUi与KS已预共享密钥Keyi，Keyi表示ECUi的长期密钥，存储在ECU的安全固件中，KS的安全存储中存有ECU的id与Key的对照表。

密钥分发步骤如下：

a) $\mathrm { K S ^ {  } }$ ECUi：KS 将执行式(3)得到结果 send_msgi，并将其广播至车载网络中。其中r为一个随机数，Enc 表示 SM4算法。

$$
s e n d \_ m s g _ { i } = r \parallel E n c _ { K e y _ { i } } ( S K ) \parallel H M A C ( S K \parallel r )
$$

b) $\mathrm { E C U _ { i } { \to } K S }$ ：ECUi接收到send_msgi后，使用密钥Keyi解密消息，获取SK并验证，验证过后ECUi将执行式(4)得到结果ack_msgi并返回，若验证不通过或未获取密钥，将执行式(5)得到结果errmsgi并返回。其中EIDi表示ECUi的ID标识：

$$
a c k \_ m s g _ { i } = E n c _ { K e y _ { i } } ( r + 1 \| E I D _ { i } ) \| H M A C ( r + 1 \| E I D _ { i } )
$$

$$
e r r _ { - } m s g _ { i } = E n c _ { K e y _ { i } } ( r - 1 \parallel E I D _ { i } ) \parallel H M A C ( r - 1 \parallel E I D _ { i } )
$$

c)KS服务器根据ECUi的返回结果决定是否重新执行密钥分发操作。

# 2.5 ECU通信流程设计

保护ECU通信分为发送端和接收端，本研究中采取符合SAEJ1939规范的64BCAN-FD数据帧格式，符合J1939标准的PDU 格式如图2所示。

优先级P 扩展数据 数据页位 PDU格式 PDU特定 源地址SA 数据域3bits 页EDP 1bit DP 1bit 8bits PF 域PS 8bits 8bits DATA 64Byte

a）发送端消息处理过程如下：

(a)ECU数据帧的层层传递：CANDriver收取ECU的报文生成L-PDU，L-PDU进入CANInterface进行抽象处理成为 N-PDU，N-PDU 进入CANTp 生成I-PDU，PDUR 模块将需要添加认证的I-PDU路由至SecOC模块。

(b) SecOC模块初始化缓存区后识别PDU中的源地址，判断该发送端ECU属于NSL0-3这四个级别中的那个级别，并分别执行对应的操作以生成MAC或者密文：

NSL0和NSL1：此级别中的数据帧需要添加MAC码以保证其完整性检验，在本研究中，使用更加快捷的Blake2s计算。SecOC将以下数据传输至连接的优化固件的HSM中：I-PDU的标识符ID，ECU数据和完整的新鲜度值，HSM接收这三个数据之后，HSM使用以下公式计算MAC码。其中PIDi为该PDU标识符，DATAi为PDU中携带的数据，FV为完整的新鲜度值，dklen为期望得到的长度，此处为2或者4。

Authenticator ${ } = H M A C { \left( { \mathrm { P I D } } _ { \mathrm { i } } \parallel { \mathrm { D A T A } } _ { \mathrm { i } } \parallel { \mathrm { F V } } , { \mathrm { d k l e n } } \right) }$

NSL2和NSL3：此部分的SecuredI-PDU构建过程中需要保护数据防窃取，与上述步骤中不同的是，Blake2s期望得到的长度不一，ECU需要先执行SM4加密算法得到加密的数据，将密文和MAC传输至SecOC模块。式(6)中的dklen分别为6或8。

$$
C i p h e r = E n c _ { S K } \left( D A T A _ { i } \right)
$$

$$
A u t h e n t i c a t o r = H M A C ( P I D _ { i } \parallel C i p h e r _ { i } \parallel F V , d k l e n )
$$

(c)SecOC中新鲜度值管理器(FreshnessManager，FVM)提供接口收发字节数组形式的新鲜度值，在本研究中，新鲜度值以计数器的形式出现，并将新鲜度值截取长度设置为8，所以在securedI-PDU构建的过程中，将截取新鲜度值的低8bits作为参数添加在报文中。只有当SecOC调用PduR模块进行进一步路由时，该新鲜度值计数器递增。

(d）缓存区将按照如下公式构造SecuredI-PDU： SecuredIPDU $\mathbf { \Sigma } = \mathbf { \Sigma }$ SecurredIPDUHeader|lCipherllTruncatedFV||Authenticator

(e）当缓存区中构造完成SecuredI-PDU后，SecOC模块将 SecuredI-PDU交由PduR 路由(此时计数器递增)。

b)接收端消息处理过程如下：

(a)SecOC为每一个SecuredI-PDU维护一个验证构建计数器(AuthenticationBuildCounter，ABC)和验证尝试计数器(Authentication VerifyAttemptCounter，AVAC)，并设初始值为0。这两个计数器将参与整个SecuredI-PDU验证过程。FVM接收来自SecuredI-PDU的新鲜度值，在内部查询：若查询后无返回结果，则ABC递增，不执行验证尝试，反之返回值为可恢复错误如工作栈忙碌等，则ABC递增；若验证构建失败，且ABC未达到阈值，则重新刷新验证过程；若验证构建成功，但验证失败，譬如MAC验证不通过，AVAC递增，ABC置为0；若对新鲜度函数的查询返回一个不可恢复的错误，譬如新鲜度配置导致的系统故障，或者ABC、AVAC达到阈值，SecOC都将此SecuredI-PDU移出验证缓存区并丢弃；若验证通过，返回类型将被设置为SECOCVERIFI-CATIONSUCCESS。

(b)SecOC模块将按照如下方式去构建验证所需的新鲜度值(FreshnessVerifyValue，FVV)：由于本研究使用截断的新鲜度值，所以直接从非完整传输的构建方案开始，首先，AVAC将递增，接着对比新收到的SecuredI-PDU中的截断新鲜度值(NewFreshnessValue，NFV)与上次验证的新鲜度值(OldFreshnessValue,OFV)，若NFV大于OFV，则 $\operatorname { F V V } { \operatorname { \overline { { { V } } } } } = \operatorname { O F V }$ hign bits $\parallel \mathrm { N F V }$ ，反之FVV=OFVhign bits $^ +$ I $| | \mathsf { N F V }$ ，如此验证所需的新鲜度值便构建完成

(c)加密过的数据将由ECU自行解密，解密步骤在MAC 验证通过之后。计算公式如下，其中Dec为SM4的解密算法。

$$
D A T A { = } D e c _ { s K } \left( C i p h e r \right)
$$

(d)SecOC模块为MAC验证构造数据，与MAC生成过程一致，SecOC模块通过将DataToAuthenticator及其长度与从SecuredI-PDU解析的MAC及其长度传递到对应的认证算法中来验证MAC，在HSM中完成验证的计算操作。

DataToAuthenticator $= \left( P D U I D _ { i } \parallel D A T A _ { i } \parallel F V V , \mathrm { d k l e r n } \right)$

(e）验证模块验证该SecuredI-PDU的MAC，若根据传递的数据计算出的验证MAC与SecuredI-PDU的MAC对比一致，则返回验证正确结果，若验证不通过，则分以下两种情况，第一种为AVAC达到阈值，则直接丢弃该帧，第二种为AVAC未达到阈值，则AVAC与FVV都递增，再次执行MAC验证操作。

(f)SecOC需要将返回的验证结果传递给FVM，将该数据帧传递到上层应用或对应的ECU。

# 3 安全与性能分析

# 3.1安全分析

本章节对基于SecOC的车载网络安全通信模型的安全性进行形式化分析。

1）设E1、E2、E3和E4分别为2.1节中分类的ECUs_1至ECUs_4的ECU集合，则模型中的总ECU集合为 $\scriptstyle { \mathrm { E } = = \mathrm { E } 1 }$ UE2UE3UE4，则声明对象e1,e2:E，(e1,e2) $\in \mathrm { E } \times \mathrm { E }$ 。

2）设ECU的id:ID，ECU哈希指纹集合H，则存在ECU与其对应的哈希指纹表{id:ID;h:H}， $\mathrm { ( i d , h ) } { \in } \mathrm { I D } \mathrm { \times H }$ 。

3）设新鲜度值集合 $\scriptstyle \mathrm { F V = = } \{ \mathrm { x } : Z | 0 < \mathrm { x } \leq \mathrm { m a x } \}$ ，声明对象fv:FV。

4)HSM中已存储密钥k。

定理1ECU安全，修改固件或外装的ECU被检测出来

证明假设现有一个被注入恶意代码、修改固件程序或者后装的ECUfake在汽车内部已存在，在点火时经过HSM计算将指纹h_fake发送至T-BOX验证，(id.h_fake) $\neq$ (id,h)或者id! $\in$ ID∧h fake! $\in \mathrm { H }$ ，验证不通过则报警。

定理2抗重放攻击

证明假设车载网络中有一中间者监听到一个报文后多次放入网络。接收端将报文放入SecOC模块验证，重放报文的新鲜度值为fv_fake $\in \mathbf { N }$ ，从FVM中接受的新鲜度值为fv $\in \mathbf { N }$ ，在MAC验证过程中MAC_fv_fake $\neq$ MAC_fv，验证失败，此报文被丢弃。

# 定理3抗窜改报文欺骗

证明假设车载网络中有一中间者截获一个报文，将报文中载荷的DATA域数据部分修改后重传入网络，接收端验证报文时，DataToAuthenticat_data_fake $\neq$ DataToAuthenticat,Blake2s计算出的MAC不等，验证不通过丢弃此报文。

# 定理4抗信息窃听

证明假设车载网络中有一中间者要窃取汽车信息，截获关键ECU或系统的报文，本研究中关键数据已使用SM4加密，En(k,Data)，因为密钥在HSM安全区，中间者无法获取该信息。

定理5密码算法安全

证明本研究中使用的 SM4 的 S盒的表达中多项式为

254次、255项，具有最高的复杂度，根据差分密码分析、线性密码分析、多维线性密码分析等过重密码分析技术测试，SM4拥有足够的安全冗余度。文献[24]表明，Blake2对旋转密码分析、迭代差分分析和不可能差分分析等具有一定的抗性与安全冗余度。

# 定理6密钥安全

证明本研究中的会话密钥在车辆启动至熄火期间有效，128位的密钥破解复杂度为 $2 ^ { 1 2 8 }$ ，故而会话密钥安全。主密钥安全性可使用VulCAN[12]中的Sancus[26]结构，使用受保护模块(Protected Module Architectures，PMAs)保护主密钥安全。PM内存只能通过特定代码段访问，该代码段只能通过单个入□点输入，拥有高安全性和高效性，且成本低廉不增加设备。

# 3.2性能分析

在Linux5.4内核,4G 运行内存下，软件测试 SHA-256、Blake2s-256、改进HMAC的PBKDF2与Blake2s-PBKDF2计算效率如表2所示，相同条件下，Blake2s和基于Blake2s改进的Blake2s-PBKDF2拥有更好的计算效率。

Tab.2Efficiency testing in software environment   

<html><body><table><tr><td>执行轮数</td><td>SHA-256 /ms</td><td>Blake2s- 256/ms</td><td>改进HMAC 的 PBKDF2/ms</td><td>Blake2s- PBKDF2/ms</td></tr><tr><td>1000</td><td>0.3</td><td>0.07</td><td>1</td><td>0.2</td></tr><tr><td>10000</td><td>1.8</td><td>0.4</td><td>3</td><td>1</td></tr><tr><td>100000</td><td>15.9</td><td>3.6</td><td>27</td><td>10</td></tr></table></body></html>

将本研究中提出的基于SecOC的车载网络安全通信模型与现有模型对比，本文提供了更全面的安全保障，如表3所示。

表2软件环境中的效率测试  
表3基于SecOC的安全模型对比  
Tab.3Comparison of security models based on secoc   

<html><body><table><tr><td>模型</td><td>ECU 划分 消息加密</td><td></td><td>MAC</td><td>ECU认证</td><td>密钥管理</td></tr><tr><td>文献[4]</td><td>无</td><td>无</td><td>CAMC-AES</td><td>无</td><td>无</td></tr><tr><td>文献[6]</td><td>无</td><td>无</td><td>CAMC-AES</td><td>无</td><td>初始化写入ECU</td></tr><tr><td>文献[7]</td><td>DataID</td><td>AES</td><td>CMAC-AES/2B</td><td>无</td><td>根据数据从本地 密钥库更新</td></tr><tr><td>文献[13]</td><td>ASIL</td><td>无</td><td>CMAC-AES/2B</td><td>无</td><td>初始化写入ECU</td></tr><tr><td>文献[10]</td><td>无</td><td>无</td><td>CMAC-AES/2B</td><td>无</td><td>初始化主密钥、</td></tr><tr><td></td><td></td><td></td><td>CMAC-</td><td>基于主密</td><td>软件生成会话密钥 初始化主密钥、</td></tr><tr><td>文献[12]</td><td>无</td><td>无</td><td>AES/2B</td><td>钥认证</td><td>AS 软件分发会话密钥</td></tr><tr><td>文献[17]</td><td></td><td></td><td></td><td>基于主密</td><td>初始化写入ECU、</td></tr><tr><td></td><td>无</td><td>AES</td><td>HMAC-SHA/8B</td><td>钥认证</td><td>SKDC 分发会话密钥</td></tr><tr><td>文献[9]</td><td>DataID</td><td>无</td><td>CMAC-AES/</td><td>无</td><td></td></tr><tr><td>本文</td><td>ASIL</td><td>SM4</td><td>28bit/44bit</td><td></td><td>初始化写入ECU</td></tr></table></body></html>

# 4 结束语

本研究分析并总结现有国内外基于SecOC的车载网络保护模型的不足之处，提出一种基于SecOC的车载网络安全通信模型，模型中根据SAIL将ECU划分不同的安全等级，更好地利用车载网络资源；基于Blake2s改进现有的PBKDF2算法，在启动阶段使用车载环境的真实物理参数衍生出会话密钥，并存储在HSM模块中，在驾驶期间有效；在点火阶段验证通电ECU的哈希指纹值，在通信阶段使用SM4加密通信数据，Blake2s生成可选长度的MAC消息验证码。通过实验和分析证明，该模型计算效率高，并提供更全面的安全保护，符合中国信通院提出的由内而外地保护车联网安全要求。

密钥管理是加密模型中最重要的一环，相比于通过会话破解密码，直接从设备中获取密钥是更快捷的方式，所以在车载环境中设计加密步骤，需要着重考虑密钥管理方案。故而本研究中密钥管理将是下一步研究的重心，进一步优化密钥的生成，存储和使用。

# 参考文献：

[1]吴武飞，李仁发，曾刚，等．智能网联车网络安全研究综述[J].通 信学报,2020,41(6):14.(Wu Wufei,Li Renfa,Zeng Gang,et al. Summary of research on network security of intelligent network connected vehicles [J]. Journal of communications,2020,41 (6): 14)   
[2]Specification of Secure Onboard Communication． AUTOSAR_ SWS_Secure Onboard Communication [EB/OL].2020.https://www. autosar. org/   
[3]余其涛．基于AUTOSAR标准的CAN 通信栈设计与实现[D].上海 交通大学，2016.(Yu Qitao.Design and implementation of CAN communication stack based on AUTOSAR standard [D]. Shanghai Jiaotong University,2016.)   
[4] 吴志红，李清晨，朱元，等.AUTOSAR 规范下安全车载通信技术的 研究与实现[J].通信技术,2017,50 (12):2822-2827.(Wu Zhihong, Li Chenchen, Zhu Yuan,et al. Research and implementation of safety vehicle communication technology under AUTOSAR specification [J]. Communication technology,2017,50 (12):2822-2827)   
[5]罗峰，胡强，刘宇．基于CAN-FD总线的车载网络安全通信[J]．同 济大学学报：自然科学版,2019,47(3):386-391.(Luo Feng,Hu Qiang, Liu Yu. Vehicle network security communication based on can-fd bus [J]. Journal ofTongji University: Natural Science Edition,2019,47(3): 386- 391)   
[6]黄大权．车联网安全通信技术的研究与实现[D]．电子科技大学， 2019.(Huang Daquan. Research and implementation of secure communication technology for Internet of vehicles [D]. University of Electronic Science and technology, 2019)   
[7]罗超.面向联网汽车车内网络的防御技术研究与实现[D].电子科 技大学.2020 (Luo Chao.Research and implementation of Defense Technology for in vehicle network of networked vehicles [D]. University of Electronic Science and technology.2020)   
[8]刘毅．基于车载CAN 总线网络的安全协议研究[D]．吉林大学, 2019.(Liu Yi. Research on security protocol based on vehicle can bus network [D]. Jilin University,2019)   
[9]Bohner M,Mattausch A,Much A.Extending software architectures from safety to security[J].Automotive Safety & Security 2014,2015.   
[10] Radu AI,Garcia F D.LeiA:A lightweight authentication protocol for CAN [C]// European Symposium on Research in Computer Security. Springer, Cham,2016:283-300.   
[11] Nyurnberger S,Rossow C.-vatican-vetted,authenticated can bus [C]// International Conference on Cryptographic Hardware and Embedded Systems.Springer,Berlin,Heidelberg,2016:106-124.   
[12] Van B J,Myuhlberg JT,Piessens F.VulCAN:Efficient component authentication and software isolation for automotive control networks [CJ// Proceedings ot the 33rd Annual Computer Security Applications Conference. 2017: 225-237.   
[13] Wu Z, Zhu Y,Lei X,et al. Functional safety and secure CAN in motor control system design for electric vehicles [R]. SAE Technical Paper, 2017.   
[14] Rosenstatter T，Sandberg C，Olovsson T.Extending AUTOSAR's Counter-Based Solution for Freshness of Authenticated Messages in Vehicles [Cl/ 2019 IEEE24th Pacific Rim International Symposium on Dependable Computing (PRDC).IEEE,2019:1-109.   
[15] Rosenstater T. Towardsa Standardised Framework for Securing Connected Vehicles [M].Chalmers Tekniska Hogskola (Sweden),2019.   
[16] Bella G,Biondi P, Costantino G,et al.CINNAMON: A Module for AUTOSAR Secure Onboard Communication [C]// 2020 16th European Dependable Computing Conference (EDCC) .IEEE,2020:103-110.   
[17] Xiao Y,Shi S,Zhang N,et al. Session Key Distribution Made Practical for CAN and CAN-FD Message Authentication [C]// Annual Computer Security Applications Conference.2020: 681-693.   
[18] Yalcin S B,Soltekin M M E.Designing and Implementing Secure Automotive Network for Autonomous Cars [C]// 2021 29th Signal Processing and Communications Applications Conference (SIU).IEEE, 2021: 1-4.   
[19]胡嘉航．硬件安全模块的设计及应用[D].杭州电子科技大学.(Hu Jiahang.Design and application of hardware security module [D]. Hangzhou University of Electronic Science and technology)   
[20] Kang S,Seong J,Lee M. Controller area network with flexible data rate transmitter design with low electromagnetic emission [J].IEEE Trans on Vehicular Technology,2018,67 (8): 7290-7298.   
[21] Woo S,Jo HJ,KimI S,et al.APractical Security Architecture for InVehicle CAN-FD[J]. IEEE Trans on Intelligent Transportation Systems, 2016: 2248-2261.   
[22] Visconti A, Gorla F.Exploiting an HMAC-SHA-1 optimization to speed up PBKDF2 [J]. IEEE Transactions on Dependable and Secure Computing,2018,17 (4): 775-781.   
[23] Aumasson JP, Neves S,Wilcox-O'Hearn Z,et al. BLAKE2: simpler, smaller,fast asMD5 [C]// International Conference on Applied Cryptography and Network Security. Springer,Berlin,Heidelberg,2013: 119-135.   
[24] Atiwa S,Dawji Y,Refaey A,et al. Accelerated hardware implementation of blake2 cryptographic hash for blockchain [C]//2020 IEEE Canadian Conference on Electrical and Computer Engineering(CCECE) .IEEE, 2020: 1-6.   
[25] Choi W,Jo H J，Woo S,et al.Identifying ecus using inimitable characteristicsof signals in controller area networks [J].IEEE Trans on Vehicular Technology,2018,67 (6): 4757-4770.   
[26] Noorman J,FreilingF,Bulck JV,et al. Sancus 2.O: ALow-Cost Security Architecture for IoT Devices[J]. ACM Transactions on Privacy and Security,2017,20 (3): 1-33.