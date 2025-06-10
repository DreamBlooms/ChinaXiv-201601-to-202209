# 软件定义网络可信连接设计与实现

李兆斌，刘梦甜，魏占祯，王守融(北京电子科技学院，北京 100070)

摘要：软件定义网络（software definednetworking，SDN）将控制层和数据转发层分离，由控制层对数据转发层进行统一管理。目前控制层及数据转发层设备间完整性认证机制尚不完善，若平台完整性损坏的设备接入网络，会给整个SDN 网络带来严重的安全问题。为确保双方设备在完整可信的前提下建立连接，进而在源头上保障设备安全、网络可信，提出了一种新的SDN可信连接方案。该方案以可信网络远程设备认证技术为基础，利用可信平台模块作为可信支撑，在 SDN数据转发设备与控制器的连接过程中添加完整性认证环节。测试分析表明，该方案有效可行，符合实际应用。

关键词：软件定义网络；可信连接；完整性认证；网络安全中图分类号：TP309 doi:10.3969/j.issn.1001-3695.2017.09.0937

# Design and realization of SDN trusted connection

Li Zhaobin, Liu Mengtian, Wei Zhanzhen, Wang Shourong (BeijingElectronic Science TechnologyInstitute,Beijing1ooo70,China)

Abstract: Software-Defined Networking separates thecontrollayerand thedatalayer.Data forwardingisunified management bythe controllayer in SDN.However,equipment integrityauthentication mechanism is notconsummate betweenthecontrol layerand thedata layer.If the falsified equipment triesto connect the network,the whole network willface serious security problems.Forensuringthattheconnection wasestablishedafterprovingtheequipmentcredibleand integratedandthatnetwork is available,this paper proposed aprojectof trustedconnection based on SDN.Combing the trusted network remote device authenticationtechnologyand usingthetrustedplatformoduleas trustedsupport,theprojectaded integritycertificationto linkingprocess ofdata forwardingdevicesandcontrollrs.Accordingtotheexperiment,theprojectissuitableforactualnetwork environment.

Key Words:software defined networking; trusted connection; integrated authentication; network security

# 0 引言

软件定义网络（softwaredefinednetworking，SDN）将控制层和数据转发层分离后，由控制层通过接口对数据转发层进行统一连接及管理，以便简化网络管理，提高网络灵活性，降低网络调整配置成本。然而，更强的可变性在带来优势的同时也产生了一些亟需解决的安全问题。作为各类网络功能实现的前提，如何使控制层和数据转发层中的设备正常且安全建立连接就是其中之一。

当数据转发层的数据转发设备（openvSwtich,OVS）新加入网络时，可通过配置位于控制层的控制器IP地址建立底层通信连接，并在此基础上开始协商双方共同支持的OpenFlow协议最高版本，若协商顺利，连接建立成功。也就是说，控制器与OVS建立连接时并未对即将连接的对端设备进行平台完整性认证，两类设备都有可能与被窜改后的设备进行连接。控制器作为SDN的核心，一旦遭受攻击而无法正常工作，可能会导致网络的瘫痪，而OVS作为具体工作的执行者，若被危险设备利用，同样会对网络报文转发甚至对整体网络造成影响[1,2]。因此，在连接建立前添加设备完整性校验对解决控制器与OVS连接认证问题极为必要。

在认证连接这一问题上，OpenFlow 规范允许用户在通道建立时自主选择是否采用TLS安全机制。但TLS在实际部署中的复杂性及自身局限性导致安全通道实现困难，因此大多数用户还是更倾向于直接采用TCP明文来建立连接通道。况且，TLS的保护目标是数据，并不能对设备的软、硬件完整性校验提供帮助[3]。

另外，通过引入第三方认证中心为设备颁发证书也是一种认证设备的方案，但因处理方式复杂，并没有被广泛应用。除此之外，物理隔离也被视为保障控制器及其他设备安全的有效方法，不过该方法对部署环境、管理员管理等多方面的要求很高，并不容易实现[3]。张团利等人[4]提出控制器与交换机失效后的路径保护、链路保护等恢复机制，虽然可以有效帮助遭受攻击的设备在短时间内恢复功能，但已连接的仿冒设备若重复发起攻击，仍会对网络造成影响。而周睿康[5]、潘秋月[]也仅仅是分别引入可信计算技术完成控制器间的认证或对交换机协议方面入手进行改进。

不难发现，现有设备认证方案鲜有提及控制器与交换机间认证，然而建立安全连接作为一切功能的起点对整体网络运行至关重要，所以完善连接过程的必要性不言而喻。经过分析，本文结合可信网络远程证明协议，利用可信平台模块作为可信支撑，选择Ryu作为控制器，在不改变流程的前提下添加设备完整性认证过程，对OpenFlow协议、OVS系统及Ryu系统进行改造扩展，实现Ryu与OVS可信连接，避免窜改后设备威胁网络安全。

# 1 相关工作

# 1.1SDN与 OpenFlow

SDN架构[7如图1所示，分别是应用层、控制层以及数据转发层。控制层与另外两层分别通过北向接口及南向接口（如OpenFlow）进行数据交互。控制层根据应用层功能需求调用数据转发层实现功能，而数据转发层则根据控制层所发出的指令进行数据转发、存储、上传等工作。

![](images/f3dec19bde253d4b417e0aeb9a5da0eb9b4936f201cf0aca8b7303b641f8dd33.jpg)  
图1软件定义网络基本架构

OpenFlow作为构建SDN网络的标准规范，是一种集中控制模型，其要素包含控制器、OVS、两者间OpenFlow 通道建立的连接以及OVS 流表[8。在 SDN 中通道建立、设备配置、定期交互实现均通过OpenFlow 消息来实现。OpenFlow支持以下三类消息：Controller-to-Switch（控制器到数据转发设备消息）Asynchronous（异步消息）以及Sysmetic（对称消息）8。其中，Sysmetic是控制器和数据转发设备都可以自主发起的，一般用来进行设备初始化，在发送前也无须进行请求和确认。在控制器和数据转发设备建立连接前发送的Hello消息以及定期发送的ECHO信息都是属于Sysmetic，该类消息虽然是最简单的一种，但对于通道建立以及维护稳定连接来说不可或缺。

# 1.2可信平台与远程设备可信认证

可信平台中身份认证密钥（attestation identitykey,AIK）用于提供平台的身份证明[。平台配置寄存器（PCR）则通过记录动态可信度量摘要值来记录系统运行状态[10]，因为PCR值对于设备完整性认证至关重要，所以为避免被恶意窜改或伪造，寄存器不能通过端口随意读写，仅能通过重置操作和扩展操作来变更。

可信计算认证技术利用内嵌硬件设备TPM加密芯片在设备启动时执行不可逆的信任传递机制，利用一环度量一环的基本原则完成自系统固件至设备平台的度量，并将各阶段可信度量摘要值存储至 PCR 中[1\~12]，通过对比 PCR 值来识别设备软硬件是否经过窜改，而非仅依赖于系统启动完成后的用户身份验证。

不过，如果涉及到远程设备身份认证时，可信认证技术需要配合远程证明技术共同完成。

目前，匿名认证方案（direct anonymous authentication,DAA）作为最基础的远程证明方案被广泛应用在远程身份设备认证中。该方案在交互双方中确定不同可信域的质询方和证明方后，通过挑战/应答协议交换并判断认证值的方式完成认证[13]。

借助远程认证技术，可信平台也可以对远程设备进行设备完整性报告。远程质询方（挑战者）首先利用产生随机数并发送给证明方（应答者)，证明方利用认证身份密钥对当前设备的PCR值以及随机数一同进行签名后报告给质询方，质询方可利用随机数来避免重放攻击，利用证明方PCR值与期望值对比可证明其可完整可信（图2）。

![](images/8fe0a1734c57585506c8023dc5c15bf0cfbada10622f5f50c9f69c0aadcbd8cb.jpg)  
图2远程设备可信认证流程

# 2 SDN可信连接设计

# 2.1可信连接模型设计

SDN可信连接模型跨越控制层与数据转发层，主要由可信平台模块、控制器、OVS以及负责完整性认证的可信连接通道组成。模型中的OVS与控制器在建立连接时通过验证对方平台完整性校验值来确认其设备是否可信，从而决定是否完成本次连接的建立。只有双方同时认证通过，连接才可成功建立并继续进行后续的配置查询交互，有一方认证失败，则停止连接。

可信连接模型如图3所示。

![](images/c77741d4048f03fd4e3e79847a69a9f59e46c8baf7c0eb266b889c1019d608be.jpg)  
图3可信连接模型  
图4可信认证过程

# 2.2完整性认证过程概述及安全性证明

2.2.1具体完整性认证过程

完整性认证过程为SDN可信连接模型中重要部分，具体过程如图4所示。完整性认证过程符号解释说明如表1所示。

-1.{nonce_ryu||PCR_IDR}R1}OPUB   
Ryu OVS ←-2.{Hash(O_PCRidllnonce_ryu)|lnonce_ryulIDo}AIK_OVS-l}RPUB   
TPM -3.{{nonce_ovs|PCR_IDo}O"}RPUB TPM 4.{Hash(R_PCRid|lnonce_ovs)llnonce_ovs|lIDR} AIK_Ryu}OPUB

表1完整性认证过程符号解释说明  

<html><body><table><tr><td>R</td><td>控制器，认证主体之一</td></tr><tr><td>0</td><td>交换机，认证主体之一</td></tr><tr><td rowspan="2">nonce_ryu</td><td>Ryu 请求认证时产生的随机数，与交换机相应度</td></tr><tr><td>量值进行散列运算</td></tr><tr><td>nonce_ovs</td><td>OVS 请求认证时产生的随机数，与控制器相应度</td></tr><tr><td rowspan="2">PCR_IDR</td><td>量值进行散列运算</td></tr><tr><td>Ryu 请求认证时指定认证的PCR序号，OVS 需根</td></tr><tr><td></td><td>据序号提供特定的值进行认证 OVS 请求认证时指定认证的PCR序号，Ryu 需根</td></tr><tr><td>PCR_IDo</td><td>据序号提供特定的值进行认证</td></tr><tr><td>OPUB</td><td>OVS预置公钥</td></tr><tr><td>RPUB</td><td>Ryu预置公钥</td></tr><tr><td>0-1</td><td>OVS 预置私钥</td></tr><tr><td>R-1</td><td>Ryu预置私钥</td></tr><tr><td>R_PCR</td><td>Ryu 指定序号的PCR值</td></tr><tr><td>O_PCR</td><td>OVS指定序号的PCR值</td></tr><tr><td>IDR</td><td>Ryu 设备平台ID</td></tr><tr><td>IDo</td><td>OVS 设备平台ID</td></tr><tr><td>AIK_OVS-1</td><td>OVS 身份认证密钥私钥，用于校验数据签名</td></tr><tr><td>AIK_Ryu1</td><td></td></tr><tr><td>Hash()</td><td>Ryu 身份认证密钥私钥，用于校验数据签名 TPM中基于 SHA-1 引擎的 Hash()函数</td></tr></table></body></html>

# 2.2.2完整性认证过程形式化描述以及安全性证明

BAN逻辑[5是多种证明协议安全性逻辑系统中最具影响力工具，由10个基本语法语义组成，另外BAN逻辑推理还包括由7个定理组成的5个主要规则。下面将以BAN逻辑对完整性认证过程进行安全性证明。

1）完整性认证过程形式化描述   
$\mathrm { R \to O ~ : \{ \{ n o n c e \underline { { { \mit \mathrm { \Phi } } } \mathrm { \scriptscriptstyle { \mathrm { \scriptstyle { \mathrm { \scriptstyle { \Upsilon } } } \mathrm { \scriptscriptstyle { \mathrm { \scriptstyle { \mathrm { \cal { P } } } \mathrm { \scriptscriptstyle { \scriptstyle { \mathrm { \cal { R } } } } \mathrm { \scriptscriptstyle { \scriptstyle { \mathrm { \scriptstyle { \underline { { { \mathrm { \Lambda } } } } \mathrm { \scriptscriptstyle { \scriptstyle { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { \scriptstyle { \Lambda } } \mathrm { \scriptscriptstyle { \Lambda } } \mathrm { \scriptscriptstyle { \Lambda } } \mathrm { \scriptscriptstyle { \Lambda } } \mathrm { \scriptscriptstyle { \Lambda } } \mathrm { \scriptscriptstyle { \Lambda } } } } } } } } } } } } } } } } } }  $   
$\begin{array} { r } { \mathrm { ~ O \to R ~ } } \end{array}$ ：{Hash(O_PCRid|lnonce_ryu) |lnonce_ryul|IDo}   
AIK_OVS-1}RPUB   
O→R：{nonce_ovsl|PCR_IDo}O-1}RPUB   
$\mathbb { R } \to \mathrm { O }$ ：{Hash(R_PCRid|lnonce_ovs) |lnonce_ovs||IDR}   
AIK_Ryu-1}OPUB

2）BAN逻辑安全目标

根据完整性认证过程的安全需求，设定安全目标如表2所示。

表2完整性认证过程安全目标设定  

<html><body><table><tr><td>0 |=R |=nonce_ryu</td><td>OVS 相信 Ryu 相信 nonce_ryu 可信</td></tr><tr><td>R |=0|=nonce_ovs</td><td>Ryu 相信OVS 相信 nonce_ovs 可信</td></tr><tr><td>O|=R|=PCR_IDR</td><td>OVS 相信Ryu 相信PCR_IDR可信</td></tr><tr><td>R|=0|=PCR_ID0</td><td>Ryu 相信 OVS 相信 PCR_IDo可信</td></tr><tr><td>0 |=R|=R_PCRid</td><td>OVS 相信Ryu 相信 nonce_ryu 可信</td></tr><tr><td>R |=0 |=0_PCRid</td><td>Ryu 相信OVS 相信 nonce_ovs 可信</td></tr><tr><td>0|=R|=IDR</td><td>OVS 相信Ryu 相信 IDR可信</td></tr><tr><td>R |= 0|=ID0</td><td>Ryu 相信OVS相信IDo可信</td></tr></table></body></html>

3）BAN逻辑初始化假设

为验证上述BAN逻辑安全目标，对其进行符合BAN逻辑的初始化假设：

$$
\begin{array} { r l r l } & { \textcircled { 1 } ~ { \omega } ~ | \equiv ~ \frac { A I K . R y u } { R } ~ R ~ } & & { R | \equiv \frac { A I K . o V s } { O } ~ O } \\ & { \textcircled { 2 } ~ { O } ~ | \equiv \frac { R _ { P U B } } { \omega } ~ R ~ } & & { R | \equiv \frac { O _ { P U B } } { \omega } ~ O } \\ & { \textcircled { 3 } ~ { O } ~ | \equiv \# ( n o n c e _ { - } r y u ) ~ } & & { R ~ | \equiv \# ( n o n c e _ { - } o v s ) } \\ & { \textcircled { 4 } ~ { O } ~ | \equiv \# ( P C R _ { - } I D _ { R } ) ~ } & & { R | \equiv \# ( P C R _ { - } I D _ { O } ) } \\ & { \textcircled { 5 } ~ { O } ~ | \equiv \# ( I D _ { R } ) ~ } & & { R ~ | \equiv \# ( I D _ { O } ) } \\ & { \textcircled { 6 } ~ { O } ~ | \equiv \# ( R _ { - } P C R _ { \mathrm { i d } } ) ~ } & & { R ~ | \equiv \# ( O _ { - } P C R _ { \mathrm { i d } } ) } \end{array}
$$

利用3）中安全初始化假设，对2）中安全目标进行推理验证：

$\textcircled{1}$ 推理1由 $\mathrm { R \to O ~ : \{ \{ n o n c e \underline { { { \mit \mathrm { \Phi } } } \mathrm { \scriptscriptstyle { { \mathrm { \scriptstyle { \mathrm { \Lambda } } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \mathrm { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \Lambda } } } \mathrm \mathrm { \scriptscriptstyle { { \mathrm \Lambda } } } } } } } } } } } } } } } } } } } } } $ 因 $\begin{array} { r } { | \small { \cal O } \ | \equiv \xrightarrow { R _ { P U B } } \ { R } ^ { , 0 } { < } | \{ n o n c e _ { - } r y u | | P C R _ { - } I D _ { R } \} { R } ^ { - 1 } } \end{array}$ （204号根据消息含义规则[5]可推： $O | \equiv R | { \sim } n o n c e \_ r y u | | P C R \_ I D _ { R }$ 根据接收消息规则以及信念规则[5可推：$O | \equiv R | { \sim } n o n c e _ { - } r y u O | \equiv R | { \sim } P C R _ { - } I D _ { R }$ 因 $O \mid \equiv \# ( n o n c e \_ r y u )$ 且 $O \mid \equiv \# ( R \_ P C R _ { \mathrm { i d } } )$ 根据临时值验证规则[5]可得$O \ | \equiv R \ | \equiv n o n c e _ { - } r y u \quad O \ | \equiv R \ | \equiv P C R _ { - } I D _ { R }$ $\textcircled{2}$ 推理2由 $\mathrm { ~ O \to R ~ }$ ： $\mathrm { \{ \{ H a s h ( O \_ P C R i d \vert \vert n o n c e \_ r y u ) }  $ $\mathrm  | | n o n c e \underset { - } { r y u } | | I D o \underset { - } { \ y A I K \_ O V S ^ { - 1 } } \} R _ { P U B }$ 因R|三 $R ~ \vert \equiv ~ \xrightarrow { A I K \_ O V S } ~ O$ ，$R { < } | \{ H a s h ( { O _ { \bot } } P C R _ { \mathrm { i d } } | | n o n c e _ { - } r y u ) | | n o n c e _ { - } r y u | | I D _ { O } \} A I K _ { - } O V S ^ { - 1 }$

根据消息含义规则[5]可推：$R | \equiv O | \sim H a s h ( O _ { - } P C R _ { \mathrm { i d } } | | n o n c e _ { - } r y u ) | | n o n c e _ { - } r y u | | I D _ { O }$ 根据接收消息规则与信念规则可推：$R | \equiv O | { \sim } O _ { - } P C R _ { \mathrm { i d } } \quad R | \equiv O | { \sim } I D _ { O }$ 因 $R \ | \equiv \# ( O \_ P C R _ { \mathrm { i d } } )$ 且 $R \ | \equiv \# ( I D _ { O } )$ （204号根据临时值验证规则可得$R \ | \equiv O \ | \equiv O \_ P C R _ { i d } \quad \quad R \ | \equiv O \ | \equiv I D _ { O }$ $\textcircled{3}$ 推理3由 $\mathrm { \Sigma  R \ : } \ \{ \{ \mathrm { n o n c e \ L _ { - } o v s } \} | \mathrm { P C R \ L _ { - } I D _ { 0 } } \} \mathrm { O ^ { - 1 } } \} \mathrm { R _ { P U B } }$ 可知与推理1同理，从而可得$R ~ \lvert \equiv O \ \lvert \equiv n o n c e \_ o v s \quad R \ \lvert \equiv O \ \lvert \equiv P C R \_ I D _ { O }$ $\textcircled{4}$ 推理4由 $\mathrm { R  O ~ : } \{ \{ \mathrm { H a s h } ( \mathrm { R \_ P C R _ { i d } } | | \mathrm { n o n c e } \_ { \mathrm { o v s } } ) $ $\mathrm  \| n o n c e \_ o v s \| I D _ { R } \} A I K \_ R y u ^ { - 1 } \} O _ { P U B }$ 可知与推理2同理，从而可得： $O \ \lvert \equiv R \ \lvert \equiv R _ { - } P C R _ { i d } \qquad O \ \lvert \equiv R \ \lvert \equiv I D _ { R \circ }$ （204号

从上述BAN逻辑推理可以看出，结果与2）所设置的安全目标一致，该过程可以保证随机数、PCR值等信息的安全性，因此完整性认证过程可以满足可信连接模型的安全需求。

# 2.3 可信连接建立过程 (图5）

$\textcircled{1}$ OVS与Ryu进行连接初始化并开始建立连接;

$\textcircled{2}$ 发送OFPT_HELLO消息开始协商双方共同支持的最高OpenFlow协议版本;

$\textcircled{3}$ Ryu发起认证请求，发送OFPT_AUTH_REQUEST消息（含{{nonce_ryu||PCR_IDR}R-1}OPUB);

$\textcircled{4}$ OVS响应Ryu认证请求，回复OFPT_AUTH_COMPARE 消息（含{Hash(O_PCRid|lnonce_ryu)[|nonce_ryu||IDO}

AIK_OVS-1}RPUB);

OVS发起认证请求，发送OFPT_AUTH_REQUEST消息（含{{nonce_ovs||PCR_IDO}O-1}RPUB);

$\textcircled{5}$ Ryu响应OVS认证请求，回复OFPT_AUTH_COMPARE 消息(含{{Hash(R_PCRid|Inonce_ovs)[|nonce_ovslIDR}

AIK_Ryu-1}OPUB);

$\textcircled{6}$ Ryu 对OVS进行认证。若认证失败，连接建立失败，回复认证失败OFPT_ERROR信息；若认证成功，连接建立成功，继续发送后续OFPT_FEATURES_REQUEST 消息，查询OVS配置；

$\textcircled{7}$ OVS对Ryu进行认证。若认证失败，连接建立失败，直接丢弃连接；若认证成功，则将当前连接状态设置为成功，并继续接收、回复OFPT_FEATURES_REPLY消息；

$\textcircled{8}$ 定期交互FPT_ECHO_REQUEST/OFPT_ECHO_REPLY消息，确认连接状态。

SDN 可信连接实现。流程图如图5所示。

# 2.4OVS与Ryu连接建立过程

OVS可通过配置Ryu地址与其建立底层连接，此时并无OpenFlow协议消息交互。OVS系统开始运行后会通过连接管理实体识别底层连接是否建立完成。若已建立，则向Ryu发送

OPFT_HELLO消息用于协商协议版本，协商完成即表示OpenFlow通道建立完成。OVS具体程序执行过程如图6所示。

![](images/b3ca844811741b4ed4c79bda2f3285376ba78f770edaaac4a4362b74cf35dbe1.jpg)  
图5SDN可信连接建立流程

![](images/96909f12dd843edc26e0baec95756a4ab507f3526feb9ea4fe9074b9b4692d0f.jpg)  
图6OVS连接建立程序执行流程

OVS中ofconn、rconn、vconn三类实体会对连接进行逐级管理。vconn 作为最基础的连接管理实体，最主要的工作就是负责OFPT_HELLO消息的发送和接收，并可快速将当前连接情况向上报告（图6标示部分)，rconn以及ofconn将根据vconn传递的结果执行后续动作。

Ryu 并非如OVS一般复杂。启动后，Ryu开始接收OVS消息并进行回复，版本协商一致后则确认连接建立并进行配置询问。

因此，SDN可信连接实现可分别从OVS三类连接管理实体以及Ryu连接响应部分入手。

# 2.5 SDN可信连接实现

2.5.1OpenFlow协议可信连接实现

1）添加OpenFlow可信连接消息类型 $\textcircled{1}$ 完整性认证请求消息（OFPT_AUTH_REQUEST)

如图7所示，消息来源以及数据内容各8位，分别用于表示该消息发送源以及所携带数据内容；数据为160字节，用于

发送签名并加密后的随机数nonce_ryu或nonce_ovs以及指定的PCR序号。

![](images/0a540e803b6f6c6594b47400c4b831b95ccd8560e0493bbb355041e6b1b2ee25.jpg)  
图7可信连接认证请求消息结构

表3可信连接认证请求消息说明  

<html><body><table><tr><td rowspan="2">source</td><td>0000</td><td>来源于OVS</td></tr><tr><td>0001</td><td>来源于Ryu</td></tr><tr><td rowspan="2">content</td><td>0000</td><td>数据内容为随机数</td></tr><tr><td>0001</td><td>数据内容为其他(供扩展用)</td></tr></table></body></html>

综合考虑各版本协议消息情况，将认证请求消息识别码设定为40。

$\textcircled{2}$ 完整性校验值回复消息（OFPTAUTHCOMPARE）

如图8所示，消息来源以及数据置入方式各8位，分别用于表示该消息发送源以及所携带数据内容置入系统方式；数据为160字节经加密及签名后的完整性校验值

![](images/0fc94c85aece466634f7b3f373348436740eb5cbd0ee6d3f0c2f8fe1052eca51.jpg)  
图8可信连接认证值回复消息结构

表4可信连接认证值回复消息说明  

<html><body><table><tr><td rowspan="2">source</td><td>0000</td><td>来源于OVS</td></tr><tr><td>0001</td><td>来源于Ryu</td></tr><tr><td rowspan="2">means</td><td>0000</td><td>数据为自动置入</td></tr><tr><td>0001</td><td>数据为管理员手动置入</td></tr></table></body></html>

综合考虑各版本协议消息情况，将完整性校验值回复消息识别码设定为41。

2）添加错误消息类型一一认证失败

当交换机身份并未通过控制器认证时，控制器下发错误类型为：认证失败（AUTH_FAILED）的错误消息，提示待连接的交换机当前认证及连接建立状态。该环节没有直接由控制器丢

弃连接，而是先发出错误消息，告知认证失败原因。当控制器被交换机视为不可信设备时，交换机不考虑其认证失败原因，直接丢弃连接停止继续收信。

# 2.5.2Ryu系统可信连接实现

1）添加认证状态调度器

在Ryu 核心程序handler.py中handshake以及config两个调度器之间添加认证状态调度器，在ofp_handler.py 等执行具体函数的文件中添加相应调度器，以保证相关函数顺利运行。

Ryu中原有handshake\config\dead\main四个调度器，其中handshake与config分别承担连接建立前Hello握手以及建立后配置的工作，无论是发送、接收Hello消息还是发送配置询问消息，相应函数执行前都需先将状态进行调整。

# 2）定义各项新添变量

在 ofproto_v1_0.py、ofproto_v1_2.py、ofproto_v1_3.py、ofproto_v1_4.py 等各版本文件中定义新添OpenFlow 消息识别码、消息格式、消息中来源等变量识别码以及认证失败错误消息类型识别码等变量。

3）构造、发送、接收认证请求消息及设备完整性验证值回复消息

当前版本Ryu 可以支持多版本OpenFlow协议，以OpenFlow_1.3为例说明本部分实现。

在ofp_handler.py及ofproto_vl_3_parser.py中共同实现：

$\textcircled{1}$ 认证请求消息构造与解析

self.logger.debug('move onto authentication')   
datapath.Set_state (AUTHENTICATION_DISPATCHER)   
auth_request_msg = datapath.ofproto_parser.OFPAuthenticationRequest (datapath)

# $\textcircled{2}$ 设备完整性验证值回复消息构造与解析

@set_ev_handler(ofp_event.EventOFPAuthenticationRequest， AUTHENTICATION_DISPATCHER) def switch_authentication_request_handler(self,ev):

@_register parser @_set_mSg_type (ofprOto.OFPT_AUTHENTICATION_COMPARE) class OFPAuthenticationCompare (MsgBase) : 田 def init (self,datapath,source-None，means-None, data-None): Gclassmethod 里 def parser(cls, datapath, version， msg_type, msg_len, xid, buf) : 申 def _serialize_body(self) :

# $\textcircled{3}$ 证明方完整性校验

信息接收VCS_RECV_RYU_AUTH_COMPARE四类状态，保证消息构造发送、接收解析能够顺利执行。

2）定义新消息结构

/\* OFPT_AUTHENTICATION_REQUEST: Authentication request message (controller ->datapath). \*/   
struct ofp_authentication_request { OFP_ASSERT(sizeof(struct ofp_authentication_request) = 116); /\* OFPT_AUTHENTICATION_COMPARE: Authentication value message ( datapath -> controler). \*/   
struct ofp_authentication_compare{   
OFP_AsSERT (sizeof(struct ofp_authentication_compare) == 184);

为保证OpenFlow 消息处理函数顺利解析各类消息，在ofputil.h中同样定义新消息结构：

![](images/e1de65e6c0b5672103f249f3f2607ca1afa6df7e5e9f979171421b66a46c1d04.jpg)

# 3）编写消息接收、提取接口

可信连接在连接初始阶段实现，此时并未进入OpenFlow协议消息处理环节中，消息处理略有不同。系统原有消息提取接□不能在本阶段从认证请求消息以及完整性校验值回复消息中准确提取所需信息，同时为避免和其他交互信息发生冲突，因此在ofpbuf.h中编写消息提取接口ofpbuf_auth_pull:

static inline void \*ofpbuf_auth_pull(struct ofpbuf \*b, size_t size) 申{

# 4）消息构造、发送与接收

在vconn.c与ofp-util.c两个文件中编写承担主要工作的程序。

$\textcircled{1}$ 实现认证消息构造与发送：

struct ofpbuf \* ofputilencodeuthequeat(conatstructoputilautheqesteqest，eumofpversionvsionovabe2xid) 田

$\textcircled{2}$ 实现认证消息接收与解析：

$\textcircled{3}$ 实现设备完整性校验值回复消息构造与发送：

struct ofpbuf \* ofputil_encodeauthcopare(const structofputil_authcompareompare,eumofpversionversionos_be32 xid)   
田

$\textcircled{4}$ 实现设备完整性校验值回复消息接收与完整性校验：

![](images/e0049dbe162dfc75ac4937fe2174b8cd74c6a4e60606d7c4b7a107103b33e537.jpg)

# 5）在上层调用程序中完善认证消息处理分支

分别在rconn.c、ofproto.c 等相关文件中，完善认证消息处理分支，以避免系统处理OpenFlow 消息时将认证相关消息视为错误信息而影响完整性认证及后续连接建立过程。

switch (type){   
case OFPTYPE_HELLO:   
case OFPTYPE_ERROR:   
CaSe OFPTYPE_AUTHENTICATION_REQUEST :   
CaSe OFPTYPE_AUTHENTICATION_COMPARE:

6）完善 ofp-errors.h\ofp-errors.c\ofp-error.inc、ofp-msgs.h lofp-msgs.c\ofp-msgs.inc，编写ofp-auth.h\ofp-auth.inc

在ofp-errors 相关文件中添加认证失败错误类型的识别码、失败原因、原因说明及识别码；在ofp-msgs 相关文件中添加新消息类型名称、支持版本范围等基础内容；编写ofp-auth相关文件以说明完整性认证环节支持的版本情况。

# 3 SDN可信连接测试

# 3.1SDN可信连接测试环境

# 3.1.1可信平台模块仿真环境搭建

本文可信连接测试环境采用可信平台模块仿真器TPM_emulator代替TPM加密芯片完成设备平台软、硬件完整性的测试。TPM_emulator由德国研究人员开发，是目前应用最广泛的 TPM仿真器[14]，该软件使用Cmake 组织源代码，可在Linux平台下使用，能够很好的模拟TPM的功能，包括随机数发生、生成RSA密钥以及进行数字签名等。

TPM_emulator的运行需要依赖跨平台编译工具、运算库、图形库以及TSS软件栈、界面管理模块等，图形化管理界面做为选择性安装的模块可以帮助用户更好的管理可信平台。

# 3.1.2SDN可信连接测试拓扑搭建

SDN可信连接网络拓扑主要由两个控制器以及三个交换机组成。其中Ryul、OVS1以及OVS3为可信设备，OVS2以及Ryu2为不可信设备。逻辑上，OVS1以及OVS2直接连接Ryu1，OVS3则需要从Ryu1以及Ryu2中选择可信设备连接，实验设置其优先连接Ryu2。只有双方同时通过可信认证，连接才可建立成功。

![](images/42d0942aa07b621e0890981b0b5efd779b5a3aaad44e9b423379720f272c0105.jpg)  
图9可信连接测试拓扑1：控制器为可信控制器，测试OVS

# 3.1.3Wireshark协同OpenFlow协议功能扩展

目前，Wireshark较多版本已可以支持抓取、解析OpenFlow消息，但是自定义添加消息只能被抓取而不能作出解析，这样无疑是对可信连接后期分析过程造成了阻碍。因此，根据可信连接各模块的分析需求，对Wireshark-2.0.9中OpenFlow 协议进行功能扩展，使其支持可信连接信息的解析，从而在测试阶段直观地对分析认证过程，对通信实体的认证情况进行把控。

# 3.1.4SDN测试环境软、硬件说明

改造工作主要包含以下四个方面：a)添加可解析的消息类型：进行完整性认证请求消息及完整性校验值回复消息的名称和消息编号的定义和匹配，实现抓包时的正常识别；b）定义并初始化消息中出现的各类变量：单独定义消息以及认证失败的错误消息结构中各变量，并将其进行初始化，实现内容的顺利提取；c）编写自定义消息解析函数：配合已定义的变量，根据消息格式编写消息解析函数，实现消息的完整解析；d）将新添加消息的解析过程添加流程：在主函数中添加新消息处理的分支，实现对消息的识别与处理。

![](images/1bfa96e02e406a828273a3a69857c8dbbccf08b79cbb875ba21e2e2a9a18aabb.jpg)  
图10可信连接测试拓扑2：控制器为不可信控制器，测试控制器  
图11TPM_emulator及界面管理器启动成功

表5SDN 测试环境网络配置说明  

<html><body><table><tr><td>设备名称</td><td>IP配置</td><td>测试角色</td></tr><tr><td>Ryul</td><td>192.168.2.158</td><td>可信控制器</td></tr><tr><td>OVS1</td><td>192.168.2.40</td><td>可信交换机，连接Ryul</td></tr><tr><td>OVS5</td><td>192.168.2.50</td><td>不可信交换机，连接Ryul</td></tr><tr><td>Ryu2</td><td>192.168.2.168</td><td>不可信控制器</td></tr><tr><td>OVS6</td><td>192.168.2.60</td><td>可信交换机,连接Ryu2</td></tr></table></body></html>

表6SDN 测试环境硬件设备说明  

<html><body><table><tr><td>设备名称</td><td>操作系统</td><td>功能</td></tr><tr><td>Ryu 1</td><td>Ubuntu14.04.1</td><td>SDN 控制器</td></tr><tr><td>Ryu 2</td><td>Ubuntu14.04.1</td><td>SDN控制器</td></tr><tr><td>OVS 1</td><td>Ubuntu14.04.1</td><td>SDN 交换机</td></tr><tr><td>OVS 5</td><td>Ubuntu14.04.1</td><td>SDN 交换机</td></tr><tr><td>OVS 6</td><td>Ubuntu14.04.1</td><td>SDN 交换机</td></tr></table></body></html>

表7SDN 测试环境软件安装说明  

<html><body><table><tr><td>软件名称及版本</td><td>软件功能</td><td>安装位置</td></tr><tr><td>Ryu</td><td>本文改造控制器</td><td>Ryul</td></tr><tr><td rowspan="3">OVS-2.4.0</td><td></td><td>Ryu2 OVS1</td></tr><tr><td>本文改造交换机</td><td></td></tr><tr><td></td><td>OVS5 OVS6</td></tr><tr><td>Wireshark-2.0.9（扩展）</td><td>解析连接建立过程的</td><td>Ryul</td></tr><tr><td></td><td>交互信息</td><td>Ryu2</td></tr><tr><td>tpm_emulator 0.7.4</td><td></td><td>Ryul</td></tr><tr><td>libgtk 2.0</td><td>搭建可信平台仿真环</td><td>Ryu2</td></tr><tr><td>TrouSerS 0.3.8</td><td></td><td>OVS1</td></tr><tr><td>tpm_tools 1.3.8</td><td>境，实现可信认证</td><td>OVS5</td></tr><tr><td>tpmmanager 0.8.1</td><td></td><td>OVS6</td></tr></table></body></html>

# 3.2测试步骤及结果分析

3.2.1SDN可信连接设备处理动作测试步骤

本测试将拓扑图中的设备分为可信控制器Ryu1—可信交换机OVS1、可信控制器Ryul—不可信交换机OVS5、不可信控制器Ryu2—可信交换机OVS6三组，旨在对交换机完整性认证设备处理动作、控制器完整性认证设备处理动作及各测试组交互信息数量情况进行测试。

(1)可信平台模拟器运行测试;

(2)测试交换机可信认证情况，启动可信控制器Ryul。

$\textcircled{1}$ 测试可信交换机OVS1。

启动OVS1，配置控制器Ryu1地址用于发现Ryu1；观察Ryul认证结果，利用Wireshark工具抓取认证及后续过程设备间交互信息。

$\textcircled{2}$ 测试不可信交换机OVS5。

启动OVS5，配置控制器Ryu1地址用于发现Ryul；观察Ryul认证结果，利用Wireshark工具抓取、记录认证及后续过程设备间交互信息数据包。

(3)测试控制器可信认证情况，启动不可信控制器Ryu2。

启动可信交换机OVS5，配置控制器Ryu2地址用于发现Ryul；利用Wireshark工具抓取、记录认证及后续过程设备间交互信息数据包，观察OVS6认证后的动作响应。

(4)对三组测试数据包交互情况进行对比分析。

3.2.2SDN可信连接用时测试步骤 (1)可信平台模拟器运行测试

(2)启动改造后可信控制器Ryu1，启动OVS1，配置控制器Ryu1地址，记录可信连接建立用时。(3)测试传统连接用时并与可信连接建立用时进行比较

# 3.2.3可信平台模拟器运行测试结果

TPM模拟环境成功运行，可以查看平台版本号、公钥等内容且TPM_emulator管理器启动成功。

pts 做 一 动   
peLe 2 T 0   
ErataRevtsan: 1 |ei PRE 1 E H E 排0 1 K 灯柜 m 当 0 2   
p   
ebd PE mn   
Be 0 1   
Ptic Edrseetey PCE   
： 一 ： POX 82 中 Aperite: 0C 1 P008 UipatureSchee：tomeminion） 福 中 Pittcfey: P0(2] 42ec3fe15ee 672188729tetada5tc1de6cb45o5eadce W c555d4cc4c4t52c53 Cne 1 Cwe be 2 Te96tae33728175a9M275t058781d4f7cchfet6M34F7ac0Wftc48537

3.2.4SDN可信连接设备处理动作测试结果及分析SDN可信连接设备处理动作3组测试结果如表8所示。

表8SDN可信连接测试结果  

<html><body><table><tr><td>认证组别</td><td>质询方</td><td>证明方</td><td>认证结果</td><td>设备处理动作</td></tr><tr><td rowspan="2">1</td><td>Ryu1</td><td>OVS1</td><td>成功</td><td>继续后续配置查询</td></tr><tr><td>OVS1</td><td>Ryu1</td><td>成功</td><td>定期发送OFPT_ECHO 消息探查连接情况</td></tr><tr><td rowspan="2">2</td><td>Ryu1</td><td>OVS5</td><td>失败</td><td>发送认证失败信息 停止发包、丢弃连接</td></tr><tr><td>OVS5</td><td></td><td></td><td>（图12） 仅单方面建立连接</td></tr><tr><td rowspan="2">3</td><td></td><td>Ryu1</td><td>成功</td><td>控制器不响应其消息 控制器单方面连接</td></tr><tr><td>Ryu2 OVS3</td><td>OVS6 Ryu2</td><td>成功 失败</td><td>交换机不响应其信息</td></tr></table></body></html>

root@ubuntu:/home/lmt/ryu# ryu run loading_app ryu.controller.ofp_handler instantiating app_ryu.controller.ofp_handlerofOFPHandler authentication failed

67.698692366 192.168.2.59 192.168.2.158 TCP 66 35895 - 6633 [ACK] Seq=1 Ack=1 Win=29312 Len=@ TSv_ 77,699625672 192.168.2.158 192.168.2.59 OpenFL. 74 8 7.699638479 12.168.2.59 192.165.2.158 TCP 66 35895 - 6633 [ACK] Seq=1 Ack9 vin=29312 Len9 TSr. 9 7.722975474 192.168.2.59 192.168.2.158 OpenFL. 74 Type: OFPT_HELL0 107.723385715 192.168.2.158 192.165.2.59 TCP 666633-35895[AC]Seq=9Ack=9in=29656 Len=9TSv 11 7.724857895 192.168.2.158 192.168.2.59 OpenFl.. 94Typ:OFPT_AHENTICATIN_REUEST 12 7.726449753 192.168.2.59 192.168.2.158 OpenFL. 94Type:OFPT_AUMHENTICATION_REUEST 13 7.727317812 192.168.2.158 192.168.2.59 0penFL. 142Type:OFAHENTICATIOCOPE 147.733831796 192.168.2.59 192.168.2.158 OpenFL.. 142T：OFHNTICATCOE 157.734826543192.168.2.158 192.168.2.50 0penF1 99Type:0FPT_ERRR   
Frane15:9bytesenwire（792bits），99bytescaptured(192bits)oninterfaceθ   
Ethernet IISrc:Vre_2e:a:（:c:29:2eca:da），0st:re6c7:7d（8:c:29:8:c7:7d）   
InternetProtooe1Verson4，Src:192.168.2.158，0st:192.158.2.50   
Transnission Control Protocol, Src Port:6633 (533), Dst Port: 35895 (35895), Seq: 13, Ack: 113, Len: 33   
nF13 ern: 1.3 (8x) Type:OFPT_ERROR（1)） Legth:33 Transaction ID:2558955469 Type: OFPET_AJTE_FAILED (18) Code:OFPAC_N5_VALUE（1） Deta: authentication failed

3组测试结果及相应设备处理动作与可信连接流程设定一致，可见SDN可信连接能够完成连接时的设备完整性认证工作。

另外，测试组交互信息数量情况如图13所示。

![](images/eddbafa67c8ba2e7fc42758b0c24294cb321544c4c1f81b7d72bd48eda69a2cb.jpg)  
图12Ryul认证OVS5 结果  
图13测试组OpenFlow信息交互情况

1组认证结束后连接建立成功，并定期交互echo信息维持连接；2组因认证失败没有后续配置信息的交互且连接丢弃，因此在后面的时间里2组不在出现OpenFlow消息;3组中OVS6尝试连接Ryu2，但因其不可信而断掉连接，后续并无信息交互。

# 3.2.5SDN可信连接用时测试结果及分析

与传统连接流程相比，加入可信连接过程后步骤有所增加，

连接占用时间也略微产生变化，因此对添加可信连接过程与传统连接过程用时进行测试。

![](images/e8a5633036d4765bda3fcd5f36afb48a3cc6320278d4a84a74b38424d194e128.jpg)  
图14可信连接与传统连接建立完成时间对比结果

由测试结果（图14）可见，虽然可信连接时间有所增加，但与传统连接时间相比，尚在可以接受的范围之内且没有对后续流程产生影响。

# 4 结束语

软件定义网络可信连接通过分析控制层与数据转发层间安全需求，确定控制层与数据转发层间完整性认证机制不完善是当前亟需解决的安全问题之一。经测试，本文提出的可信连接实现了在设备连接前完成设备完整性认证，可以有效防止遭窜改的设备恶意连接。不过，软件定义网络发展迅速，系统也在不断更新，除控制器与交换机间设备完整性认证问题外，应该继续选择适用、成熟的安全技术解决其他待解决的认证问题。

# 参考文献：

[1]Shu Z,WanJ,Li D,etal. Security in software-defined networking: threatsand countermeasures [J].Mobile Networks& Applications,2016,21(5): 1-13.  
[2]Bawany N Z, Shamsi JA,Salah K.DDoS attack detection and mitigationusing SDN:methods,practices,and solutions [J].Arabian Journal forScience & Engineering,2017,42 (2): 425-441.  
[3]左青云，张海粟．基于OpenFlow 的 SDN网络安全分析与研究[J].信息网络安全,2015(2):26-32.  
[4]张团利，吕光宏，杨沛霖．基于OpenFlow的 SDN可靠性综述[J]．电子科技，2016,29(2):177-181.  
[5]周睿康．基于 SDN 的可信网络系统研究[D].北京：北京工业大学,2015.  
[6] 潘秋月．基于OpenvSwitch 的可信交换机 STP 协议的可信改进[D].北京：北京工业大学,2014.  
[7]张朝昆，崔勇，唐骂祎，等．软件定义网络(SDN)研究进展[J].软件学报，2015,26(1):62-81.  
[8]马文婷.基于OpenFlow的 SDN控制器关键技术研究[D].北京：北京邮电大学,2015.

[9]池亚平，王全民．基于USBkey 的可信平台模块的研究与仿真设计[J].北京电子科技学院学报,2007,15(4):13-15.

[10]张焕国，陈璐，张立强．可信网络连接研究[J].计算机学报，2010,33(4): 706-717.

[11]冯登国，秦宇，汪丹，等．可信计算技术研究[J].计算机研究与发展,

2011,48 (8): 1332-1349.  
[12]温博为．可信计算平台技术应用研究[D]．西安：陕西师范大学,2013.  
[13]王晓明．可信网络远程认证的相关研究[D].济南：山东大学,2015.  
[14]罗洪达，董增寿，杨威．基于TPM仿真器的可信计算实验平台设计[J].太原科技大学学报,2013,34(5):337-341.