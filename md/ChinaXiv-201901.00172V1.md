# 抗同步化攻击的轻量级RFID双向认证协议

柳毅1，陈添笑¹，洪洲²

(1．广东工业大学 计算机学院，广州 510006;2．广州城市职业学院科研处，广州 510405)

摘要：针对现有的RFID认证协议在安全认证过程中，由于协议的设计的缺陷，导致的协议安全性不足的问题，提出了一种利用同步化随机数以及PUF改进的轻量级RFID认证协议。首先提出了一种对RFID协议的去同步化攻击方法，并分析其原因；然后通过在标签和读写器两端设置一个同步化随机数，增强协议抗去同步化攻击的能力；最后，在标签中引入了PUF，通过PUF的不可克隆性提高了标签密钥的抗攻击能力。分析结果表明，新协议能有效地抵抗多种攻击，在保证一定效率和开销的同时具有更高的安全性。

关键词：RFID；轻量级；物理不可克隆函数；双向认证；CRC 中图分类号：TP393.08 doi: 10.19734/j.issn.1001-3695.2018.09.0756

Lightweight RFID two-way authentication protocol with anti-synchronization attack

Liu $\mathrm { Y i ^ { 1 } }$ , Chen Tianxiaol,Hong Zhou² (1.SchoolofComputer Sience&Technology,Guangdong UniversityofTechnology,Guangzhou510o6,China;2.Offce ofAcademic Research, Guangzhou City Polytechnic, Guangzhou 510405, China)

Abstract: In viewof the existing RFIDauthenticationprotocol is insufficient in the securityauthentication process dueto theflaws in the design of the protocol,this paper presented an improved lightweight RFID authentication protocol using synchronized random number and PUF.It first proposed a desynchronizing atack method onRFID protocols,and analyzed thereason.Then it enhanced the protocol'sability to resist desynchronizationatacksbyseting a synchronized random numberatbothendsofthetagandreader.Finally,itintroducedthePUFinthetag,usedtheUF'snon-clonalitytoimprove thetag'santi-atackcapability.Theanalysis resultsshow that thenew protocolcanefectivelyresist multipleatacks,and it has higher security while ensuring certain efficiency and overhead.

Keywords:RFID;lightweight; puf; mutual-authentication; CRC

# 0 引言

射频识别（radio frequency identification，RFID)，又称无线射频识别，是一种非接触式识别技术，可通过无线电讯号识别特定目标并读写相关数据而无须与目标物体进行物理接触。RFID已被广泛应用于许多领域，如物流、军事、交通等。

RFID通常由三部分组成：标签、读写器和后端数据库。后端数据库和读写器之间的通信信道一般被认为是安全可靠的[1]。读写器和标签之间的信道由于采用的是无线连接，缺乏保护非常脆弱，容易遭到窃听和欺骗。随着RFID技术的发展，RFID的安全性问题得到了越来越多的重视。为了保障RFID的安全，设计一个安全的RFID认证协议具有重要意义。

RFID 标签要求低成本，所以计算能力往往不强，传统的公钥密码算法如RSA等，不适用于RFID协议。所以如何设计安全性高的、低成本的、高效的轻量级RFID认证协议成为当下研究的热点之一。

保持RFID标签的轻量性具有重要意义。文献[2,3]将传统的密码学工具应用于RFID协议中，虽然具有良好的安全性，但并未考虑到标签的计算力。文献[2]提出了一种基于hash函数和时间戳的认证协议，该协议采用了时间戳防止攻击者的重放消息，但并未对hash函数进行优化，导致标签计算成本过高。文献[3]提出了一种基于CRC和伪随机数发生器的轻量级协议，在传输信息过程中先用CRC的单向性进行加密，然后第一条message的高位与令一条message的低位交叉组合传送。但是标签采用了伪随机数发生器，由于RFID标签计算能力的局限性，协议效率不高。

为了降低标签成本和提高效率，在最早的一批超轻量级RFID认证协议中，使用了一些简单的运算函数和认证步骤，提高了效率但降低了安全性。Chien提出的SASI协议认证过程中加入了Rot移位运算[4]，但是文献[5]随后指出了对SASI协议的Dos攻击和标签追踪攻击;文献[6]在SASI的基础上提出了Gossamer协议，协议结构基本相似，在后面的密钥更新过程中引入了MixBits运算，提高了安全性，但Zeeshan 在文献[7]中提出了对该协议的去同步化攻击以及其他安全性分析。

Tian 等人在2012年提出了一个超轻量级的认证协议RAPP[8]，不过随后Eyad 等人在文献[9]中指出了对RAPP 协议的一种抗同步攻击方法。随后文献[10]对RAPP协议进行了改进，提出了一种PAPP协议，用标签中的加密算法的单向性产生随机数，防止去同步化攻击。这种方法相比与一般的直接加随机数发生器来说，共用了标签中的门电路，减少了标签开销。

由于文献[4-6.8,10]的协议过于简单而存在的安全性问题。在文献[11]中，Zhang等人对以上这批超轻量的认证协议的协议周期和安全强度进行了详细分析，结果发现这些协议采用的运算都比较简单，复杂度低，抗攻击能力弱。随后提出了一种基于哈希类函数 M-Hash 函数的认证协议 MH 协议，M-Hash函数具有硬件资源需求低，抗碰撞性强等特性。在MH协议中Zhang等人还通过减少M-Hash的逻辑操作位，来提高协议的效率。Zhang 等人的协议实现了RFID 协议安全性与效率的平衡，但M-Hash实现所需的门电路依然较多。

Yang在文献[12]提出了一种新的轻量级认证协议，认证过程中采用了CRC和交叉位运算Cro。该协议标签的计算量和通信量非常低，非常适用于轻量级RFID系统。但是经过分析协议并不能抵抗去同步化攻击且仅仅依靠CRC和Cro这些简单的运算更新密钥安全性不高。

为了解决文献[12]中的安全性问题，文章结合一个同步化随机数和物理不可克隆函数(PUF)在该协议的基础上进行改进，提出一种新的轻量级认证协议。旨在保持协议低成本的同时具有更高的安全性。物理不可克隆函数(PUF)是一个利用物理特征把输入值映射到应答值的函数[13]。PUF具有不可克隆性，每给定一个输入，都会得到一个唯一且不可预测的输出。对于相同的输入，每个PUF的输出都不同。

# 1 对Yang的协议的分析

# 1.1符号描述

$I D$ ：标签真实身份标志  
$T I D ^ { o l d }$ ：上一轮标签临时身份标志  
$T I D ^ { n e w }$ ：本轮的标签临时身份标志  
$K _ { i } ^ { o l d }$ :标签和读写器上一轮共享密钥 $( i { = } 1 , 2 )$ （2号$K _ { i } ^ { n e w }$ :标签和读写器本轮的共享密钥 $( i \mathrm { = } 1 , 2 )$ $N _ { i }$ 读写器生成的随机数 $( i { = } 1 , 2 )$ （204号  
$r _ { n }$ 读写器和标签初始的同步化随机数。A-E:读写器和标签之间的交换信息  
$\oplus$ ：按位异或运算  
$C r o ( X , Y )$ ：交叉位运算  
$C R C { - } 1 6 ( X )$ ：循环校验函数，加密 $X$ 的值1 $\left[ G _ { n } , G _ { n + 1 } \right]$ ):PUF初始验证对。  
PUF(X):随机置换函数(通过PUF实现)。

# 1.2Yang 的协议描述

Yang 的协议如图1所示，下面给出对于Yang的协议的一种去同步化攻击：

a）在第 $\mathfrak { n }$ 次认证的时候，阻塞认证协议第 $\textcircled{5}$ 步，使得读写器更新了密钥以及标签的临时身份TID而标签没有跟新。此时读写器拥有的信息是( $\boldsymbol { T I D } _ { n e w } ^ { n + 1 }$ ， $\boldsymbol { T I D _ { o l d } ^ { n } }$ ， $K _ { i n e w } ^ { n + 1 }$ （20 $( \mathrm { i } { = } 1 , 2 , 3 ) , K _ { i o l d } ^ { n }$ $( \mathrm { i } { = } 1 , 2 , 3 )$ ),标签拥有的信息为（ $\mathbf { \boldsymbol { T } } \boldsymbol { I } \boldsymbol { D } _ { o l d } ^ { n } ,$ $K _ { i _ { o l d } } ^ { n } ( \mathrm { i } \mathrm { = } 1 , 2 , 3 )$ )。并窃听到他们第 $\mathfrak { n }$ 次认证的通信消息Hello"、 $A \| B ^ { n }$ 、 $C ^ { n }$ 、 $D \| E ^ { n }$ 。此时标签和读写器依然能相互认证。

b)在第 $n { + } 1$ 次认证的时候，再次阻塞认证协议第 $\textcircled{5}$ 步。此时读写器拥有的信息是( $T I D _ { n e w } ^ { n + 2 }$ ， ${ T I D } _ { o l d } ^ { n }$ ， $K _ { i _ { n e w } } ^ { n + 2 }$ （20 $( \mathrm { i } { = } 1 , 2 , 3 ) , K _ { i _ { o l d } } ^ { n }$ $( \mathrm { i } { = } 1 , 2 , 3 )$ ),标签拥有的信息为( $\overline { { T I D _ { o l d } ^ { n } } }$ $K _ { i _ { o l d } } ^ { n } ( \mathrm { i } \mathrm { = } 1 , 2 , 3 )$ ）

c)重放第一步中听到的消息，首先读写器向标签发送Hello"，标签返回他的 $\boldsymbol { T I D _ { o l d } ^ { n } }$ ，再按照步骤发送 $A \| B ^ { n }$ 和 $D \| E ^ { \scriptscriptstyle { ( | E ^ { \scriptscriptstyle { n } } } }$ 给标签。重放过后，标签中的信息为( $\boldsymbol { T I D } _ { n e w } ^ { n + 1 }$ $K _ { i _ { n e w } } ^ { n + 1 } ( \mathrm { i } \mathrm { = } 1 , 2 , 3 ) ,$ 。而此时读写器中的信息为 $( T I D _ { n e w } ^ { n + 2 }$ ， $T I D _ { o l d } ^ { n }$ ， ${ K _ { i } } _ { n e w } ^ { n + 2 }$ （204号 $( \mathrm { i } { = } 1 , 2 , 3 ) , K _ { i _ { o l d } } ^ { n }$ $( \mathrm { i } { = } 1 , 2 , 3 )$ )，则标签和读写器之间不能进行验证。

攻击者通过上述步骤能使被攻击过后的标签不能被读写器认证，从而实现了对协议的去同步化攻击。

![](images/04ec1de1ea53ebdb9f0f0108c1a0378ef66431b11d69234a6b9e32761c08280d.jpg)  
图1Yang 的协议Fig.1Yang's protocol

Yang 的协议之所以会存在该问题最主要的原因是在标签没有更新的一定时间段内，对于每一个 $A$ 、 $B$ 消息的响应消息都是一样的。这种情况也导致了可以对其进行跟踪攻击。攻击者可以在每次验证时阻断标签密钥更新，随后通过发送之前一样的消息 $A , B$ 得到相同的回应，从而实现跟踪攻击。

一般对于这种安全问题的改进方法通常是增加一个随机数发生器，文献[14]的协议也存在类似去同步化问题，文献[15]对其用随机数发生器进行了改进，虽然利用加密算法的一部分产生随机数，但仍有一定的计算量。本节采用同步化随机数和物理不可克隆函数(PUF)在Yang的协议的基础上进行改进，提出了一种新的轻量级协议。

# 2 新的协议

协议的符号说明与1.1节相同。新协议如图2所示。

协议初始阶段读写器中持有相应PUF事先生成好的验证对 $( G _ { n } , \ G _ { n + 1 } )$ ，密钥 $K _ { 1 } , K _ { 2 } ,$ 同步随机数 $\mid r _ { n }$ 。标签中持有$\{ I D , T I D , K _ { 1 } , K _ { 2 } , r _ { n } \}$ 。

协议过程详细描述如下：

$\textcircled { 1 } H e l l o$ ：读写器向标签发送“Hello”信号发起验证，协议认证过程开始。

$\textcircled{2} T I D$ ：标签收请求后，将自身的临时身份TID发给读写器，读写器将此TID传到后台的数据库中进行查找，若能够找到对应的 $T I D$ ，则后台数据库将与之相匹配的密钥 $K _ { i }$ 发送给读写器，标签和读写器开启双向认证阶段。若该TID在数据库中不存在，则认证失败，需重新开始认证。

$\textcircled{3} A$ 和 $B$ ：双向认证阶段中，读写器产生两个随机数 $\boldsymbol { N } _ { 1 } , \boldsymbol { N } _ { 2 }$ 计算 $A$ 和 $B$ 发送给标签，请求标签通过PUF计算进行验证。发送完成后读写器计算 $r _ { n + 1 } { \mathrm { = } } \mathrm { C R C } ( r _ { n } \oplus N _ { 1 } )$ 。标签通过密钥$K _ { 1 } , K _ { 2 }$ ，提取出 $A$ 中的 $G _ { n }$ 用于随后的PUF计算，然后用 $K _ { 1 } , K _ { 2 }$ $G _ { n }$ 计算得到 $B$ 中的随机数 $N _ { 1 }$ 。

$\textcircled{4} R$ 和 $C$ 标签利用PUFO函数和读写器发过来的 $G _ { n }$ 和计算 $\mathrm { P U F } ( G _ { n } )$ 得到 $G _ { n + 1 }$ ，再计算 $G _ { n + 2 } { = } \mathrm { P U F } ( G _ { n + 1 } )$ 和 $r _ { n + 1 } { = } \mathbf { C } \mathbf { R } \mathbf { C } ( r _ { n }$ $\oplus N _ { 1 } )$ ，利用密钥 $K _ { 1 } , K _ { 2 } , N _ { 1 } , r _ { n + 1 } , G _ { n + }$ 和 $G _ { n + 2 }$ 计算 $R$ 和 $C$ 发送给读写器。同样，读写器先从 $R$ 中得到标签发送过来的 $G _ { n + 1 }$ 并与自己的 $G _ { n + 1 }$ 进行比较，若相等，则读写器对标签认证成功。若不相等，认证失败。

![](images/b721938410d6a6f1a9d73cd7e3d85f2b46751b1e2b97d24870850bf04c8d4ab5.jpg)  
图2新的协议  
Fig.2The new protocol

认证成功后再用 $K _ { 1 } , K _ { 2 }$ + $N _ { 1 }$ ， $r _ { n + 1 }$ ， $G _ { n + 1 }$ 计算得到 $C$ 中的$G _ { n + 2 }$ ， $\left( G _ { n + 1 } \mathrm { ~ } , G _ { n + 2 } \right)$ 作为下一次读写器认证和标签的PUF验证对，随后读写器进行密钥更新。

$\textcircled{5} D$ 和 $E$ 读写器用之前生成的随机数 $N _ { 2 }$ 计算 $D$ 和 $E$ 并发送给标签,标签提取 $D$ 中的 $N _ { 2 }$ 并计算 $E ^ { \prime }$ 与 $E$ 进行比较，若相等，则说明读写器得到了 $G _ { n + 2 }$ 并拥有正确的 $\boldsymbol { r } _ { n + 1 }$ ，标签对读写器认证成功。用随机数 $\boldsymbol { N } _ { 1 } , \boldsymbol { N } _ { 2 }$ 和 $r _ { n + 1 } , G _ { n + 1 }$ 1 $G _ { n + 2 }$ 更新自己的密钥，协议结束。若不相等，则认证失败且不更新密钥。

新协议通过在标签和读写器中同步了一个随机数使得协议具有能力抵抗攻击者的去同步化攻击，且该随机数不需要标签发送，减少了通信量。

PUF的使用增强了协议的安全性，在协议某轮中即使攻击者通过某种方式得到（ $G _ { n }$ ， $G _ { n + 1 } \} _ { \begin{array} { l } { \ } \\ { \left( G _ { n + 1 } \right) } \end{array} } ,$ )，攻击者无法逆向推导出之前使用的认证对，以及推出之后使用的认证对。使标签认证相比于之前的CRC更新的密钥更安全。

# 3 协议的安全性分析

本节将对改进后的协议进行安全性分析，具体从假冒攻击、信息泄露攻击、跟踪攻击、克隆攻击、重放攻击、去同步化攻击、后向安全性以及双向认证八个方面说明改进后的协议的安全性。说明了新的协议能抵抗之前提到的去同步化攻击的原因。

# 1）假冒攻击

假冒攻击是指攻击者冒充标签或读写器进行认证，试图得到一些有用的认证信息的一种攻击。在改进后的协议中，无论协议的那一部分被修改，标签和读写器都是可以发现的。因为 $K _ { i } , N _ { 1 } , N _ { 2 } , r _ { n + 1 }$ 以及PUF产生的认证对都是动态变化的，且协议中每一步读写器和标签都能进行认证，攻击者没有相应的 $K _ { i }$ 和认证对无法假冒标签和读写器进行完整的认证。攻击者通过假冒攻击最多只可能得到TID，除此之外得不到任何有价值的信息。而TID只是一个临时的身份标志，并且每轮认证成功后都会改变，没有实际意义，故该协议能够抵抗假冒攻击。

# 2）信息泄露攻击

信息泄露攻击是指攻击者对来自读写器的消息进行特定的修改，然后发送给标签，从标签的响应中推出协议的相关信息[13]。由于本协议中每个步骤都是加密的或随机的，所用的 $\boldsymbol { N } _ { 1 } , \boldsymbol { N } _ { 2 }$ 和 $r _ { n + 1 } , G _ { n + 1 }$ ， $G _ { n + 2 }$ 也都是经过CRC 和 $C r o$ 加密传输，且在读写器和标签每一次收到消息时，都会对其进行验证，若验证失败，协议将被终止。所以当攻击者试图修改协议中的任何一个信息时，都会被认证发现，协议将被终止，故该协议能够抵抗信息泄露攻击。

# 3）跟踪攻击

协议的整个过程中都是使用标签临时的TID来作为标签的身份标志，协议的整个过程都没有标签真实的 $I D$ 出现，所以攻击者无法通过截获的协议内容得到标签的真实身份$I D$ ，从而无法对ID 进行跟踪。若攻击者想对某个截获的标签TID进行跟踪，由于TID每轮协议完成后都会由随机数$\boldsymbol { N } _ { 1 } , \boldsymbol { N } _ { 2 }$ 和 $G _ { n + 1 }$ 进行更新，所以由TID对标签的跟踪攻击也无法实现。故该协议能抵抗跟踪攻击。

# 4）克隆攻击

对于克隆攻击，本协议采用了物理不可克隆函数PUF产生的验证对作为标签每轮认证读写器的方法。由于PUF的不可克隆特性，攻击者没办法伪造出和该标签中PUF一模一样的PUF，从而无法克隆出一个含有合法的PUF的标签。故本协议能够抵抗克隆攻击。

# 5）重放攻击

每当一轮协议运行成功结束时，读写器和标签中的密钥$K _ { i }$ ，同步化随机数 $r _ { n }$ 以及 $T I D$ 等都会改变。假设攻击者假装读写器对标签进行重放攻击，首先重放第一步的Heuo，标签返回更新后的 $T I D$ ，在重放第三步的消息 $^ { A , B }$ 然而经过了上轮的更新后， $^ { A , B }$ 中的密钥 $K _ { i }$ 并不能对应更新后的TID。所以即使攻击者截取上一轮的认证信息进行重放，也通过不了认证。故该协议能够抵抗重放攻击。

# 6）去同步化攻击

改进后的协议能抵抗之前提到的对原协议的去同步化攻击。原理是通过在标签和读写器中加入了一个同步化随机数$r _ { n }$ 。读写器每次第三步请求标签时，读写器都会计算新的$r _ { n + 1 } { \mathrm { = } } \mathrm { C R C } ( r _ { n } \oplus N _ { 1 } )$ ，当标签接收到读写器发来的请求时，也会计算一个同样的 $r _ { n + 1 }$ 。从而保障了第四步的信息 $C$ 每轮都不一样，因此新协议具有抗该种去同步化攻击的能力。

对于之前的去同步化攻击在新协议的情况下：

a）同样的在第 $\mathfrak { n }$ 次认证的时候，阻塞认证协议第 $\textcircled{5}$ 步，使得读写器更新了密钥以及标签的临时身份TID而标签没有跟新。此时读写器拥有的信息是( $\boldsymbol { T } \boldsymbol { I } \boldsymbol { D } _ { n e w } ^ { n + 1 }$ ， $\boldsymbol { T I D _ { o l d } ^ { n } }$ ， $K _ { i _ { n e w } } ^ { n + 1 } ( \mathrm { i } \mathrm { = } 1 , 2 )$ ，$K _ { i _ { o l d } } ^ { n } ( \mathrm { i } \mathrm { = } 1 , 2 )$ ， $G _ { n + 1 }$ ， $G _ { n + 2 }$ ， $r _ { n + 1 } , \ I D )$ ，标签拥有的信息为( $\overline { { T I D _ { o l d } ^ { n } } }$ $K _ { i o l d } ^ { n } ( \mathrm { i } \mathrm { = } 1 , 2 )$ ， $I D$ ， $\begin{array} { r } { r _ { n + 1 } \dot { } } \end{array}$ 。并窃听到他们第 $\mathfrak { n }$ 次认证的通信消息Hello"、 $A \Vert B \mathfrak { n } _ { \mathfrak { d } } \ C \mathfrak { n }$ 、 $R _ { n }$ 、 $D \| E ^ { n }$ 。此时标签和读写器依然能相互认证。

b)在第 $n { + } 1$ 次认证的时候，再次阻塞认证协议第 $\textcircled{5}$ 步。此时读写器拥有的信息是( $T I D _ { n e w } ^ { n + 2 }$ ， $T I D _ { o l d } ^ { n }$ ， $K _ { i n e w } ^ { n + 2 } ( \mathrm { i } \mathrm { = } 1 , 2 )$ ， $K _ { i o l d } ^ { n }$ （204 $( \mathrm { i } { = } 1 , 2 )$ ， $G _ { n + 2 }$ ， $G _ { n + 3 }$ ， $r _ { n + 2 }$ ， $| D )$ ，标签拥有的信息为( $\overline { { T I D _ { o l d } ^ { n } } }$ $K _ { i _ { o l d } } ^ { n } ( \mathrm { i } \mathrm { = } 1 , 2 )$ ， $I D$ ， $r _ { n + 2 } ,$ 。

c)重放第一步中听到的消息，首先读写器向标签发送Hello"，标签返回他的 $T I D _ { o l d } ^ { n }$ ，再按照步骤发送 $\ A \| B ^ { n }$ ，然而和之前不同的是，标签的应答消息结合了标签和读写器的新一轮同步化随机数 $r _ { n + 3 }$ ，攻击者收到后再重放第一步中的消息$D \| E ^ { n }$ 时，由于 $E ^ { n }$ 里含有的是前两轮的同步化随机数 $r _ { n + 1 }$ ，所以无法通过验证，读写器认证失败，协议终止。从而阻止了去同步化攻击。

7）前向后向安全性

在协议的认证中即使攻击者通过某种方式获取了某一轮的密钥 $K _ { i }$ ， $G _ { n }$ ， $G _ { n + 1 }$ ，但是由于没有时刻跟踪标签，标签和读写器进行了若干次认证，更新了之前的 $K _ { i }$ ， $G _ { n }$ ， $G _ { n + 1 }$ 等信息。一段时间后，攻击者之前得到的密钥以及认证对将无法再用来进行验证。且在密钥更新过程中，使用CRC、Cro 和随机数 $N _ { 1 }$ 、 $N _ { 2 }$ 、 $r _ { n + 1 }$ 以及 $G _ { n + 1 }$ $G _ { n + 2 }$ 计算得到新的密钥，使得攻击者无法从本次获得的密钥推出之后的密钥，保证了协议的前向安全性。

在协议的整个过程中，每轮协议产生的随机数无法预测，保证了各条信息每轮认证都不相同，且攻击者无法从 $G _ { n + 2 }$ 逆推 $G _ { n + 1 }$ 等之前的认证对。因此攻击者无法通过本次攻击的得到的信息，推出之前协议认证的消息内容。故该协议具有后向安全性。

# 8）双向认证

新协议实现了读写器和标签的相互认证。读写器通过自身产生的随机数TID、 $N _ { 1 }$ 、 $( G _ { n } , G _ { n + 1 } )$ 以及密钥 $K _ { i }$ 来认证标签的合法性，标签通过自身PUF计算的 $G _ { n + 1 } , \ r _ { n + 1 }$ 及密钥 $K _ { i }$ 来验证读写器的合法性。满足了双向认证的要求。

表1是新协议与Yang 的协议进行比较。Y表示能抵抗该种攻击，N表示不能抵抗该种攻击。如表所示，新的协议比Yang的协议具有较高的安全性。

Table1 Security comparison between new and other protocols   

<html><body><table><tr><td>攻击类型</td><td>Yang的协议</td><td>新协议</td><td>文献4</td><td>文献6</td></tr><tr><td>假冒攻击</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>信息泄露攻击</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>跟踪攻击</td><td>N</td><td>Y</td><td>N</td><td>N</td></tr><tr><td>克隆攻击</td><td>N</td><td>Y</td><td>N</td><td>N</td></tr><tr><td>重放攻击</td><td>Y</td><td>Y</td><td>N</td><td>Y</td></tr><tr><td>去同步化攻击</td><td>N</td><td>Y</td><td>N</td><td>N</td></tr><tr><td>前向后向安全</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>双向认证</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr></table></body></html>

# 4 协议的性能分析

本节从标签的计算操作、存储空间、通信成本三方面来讨论新协议的性能。假设协议中所有消息的长度为L。

计算代价上来说，本文与改进前的协议相比，除了CRC、Cro和 $\oplus$ 操作外，多了一个PUF操作，总的来说这四种运算都是一些轻量级运算，计算开销小，很容易在标签中实现。而协议中开销较大的两个随机数的产生放在了读写器，提高了协议的计算效率。

存储量来说，新协议在原协议的基础上由于PUF的引入而减少了一个密钥 $K _ { i }$ ，但新的协议中标签需要存储一个同步化随机数，所以标签需要存储 $\{ I D , T I D , r _ { n } , K _ { 1 } , K _ { 2 } \}$ ,存储量不变，仍为5L。

通信成本上来说，新协议在一次完整的认证过程中需要发送一个TID以及消息 $R$ 和 $C$ 。总的通信量为3L。

表2是与其他一些算法的比较。

表1新协议与其他协议的安全性比较  
表2新协议与其他的协议的性能比较  
Table 2Performance comparison between new and other protocols   

<html><body><table><tr><td>协议名</td><td>计算代价</td><td>存储量</td><td>通信成本</td></tr><tr><td>文献[4]</td><td>∧,V,,+,Rot,</td><td>7L</td><td>2L</td></tr><tr><td>文献[6]</td><td>④,+,Rot,MixBit</td><td>7L</td><td>2L</td></tr><tr><td>文献[15]</td><td>Rabin,,&</td><td>5L+标志位</td><td>3L</td></tr><tr><td>本文协议</td><td>CRC,Cro,,PUF</td><td>5L</td><td>3L</td></tr></table></body></html>

# 5 结束语

RFID技术自出现以来，一直存在许多安全问题。本文对Yang的提出的一种轻量级RFID的协议的安全性的不足进行了分析，并用物理不可克隆函数（PUF）改进，提出了一种新的协议。经过分析，与原来的协议相比具有更高的安全性，在保证协议效率的同时能抵抗更多的攻击方法、满足更多的安全需求。综上所述，新的协议具有低成本、高效率、高安全性等特点，非常适用于轻量级RFID系统。

# 参考文献：

[1]周永彬，冯登国．RFID 安全协议的设计与分析[J].计算机学报, 2006,29 (4): 581-589.(Zhou Yongbin, Feng Dengguo.Design and analysis of cryptographic protocols for RFID [J]. Chinese Journal of Computers,2006,29 (4): 581-589.)   
[2]Yu Wenjin, Jiang Yixiang. Mobile RFID mutual authentication protocol based on hash function [Cl/ Proc of International Conference on Cyber-Enabled Distributed Computing and Knowledge Discovery. Piscataway,NJ: IEEE Press,2017:358-361.   
[3]Shi Zhicai,Chen Jiwei,Chen Shanshan,et al.A lightweight RFID authentication protocol with confidentiality and anonymity [C]//Proc of the 2nd IEEE Advanced Information Technology，Electronic and Automation Control Conference.Piscataway,NJ: IEEE Press,2017: 1631-1634.   
[4]Chien H Y. SASI: a new ultralightweight RFID authentication protocol providing strong authentication and strong integrity [J]. IEEE Trans on Dependable and Secure Computing,2007,4(4): 337-340.   
[5]Cao Tianjie,Bertino E,Lei Hong.Security analysis of the SASI protocol[J].IEEE Trans on Dependable and Secure Computing,2009,6 (1): 73-77.   
[6]Peris-Lopez P,Hernandez-Castro JC,Tapiador JM.et al.Advances in ultralightweight cryptography for low-cost RFID tags:gossamer protocol [C]// Proc of the 9th International Workshop on Information Security Applications. Springer-Verlag, 2009: 56-58.   
[7]Bilal Z,Masood A,Kausar F. Security analysis of ultra-lightweight cryptographic protocol for low-cost RFID tags: gossmer protocol [C]// Proc of International Conference on Network-Based Information Systems.Piscataway,NJ: IEEE Press,2009:260-267.   
[8]Tian Yun,Chen Gongliang,Li Jianhua.A new ultralightweight RFID authentication protocol with permutation [J]. IEEE Communications Letters,2012,16 (5): 702-705.   
[9]TaqieddinE, SarangapaniJ.Vulnerabilityanalysisoftwo ultra-lightweight RFID authentication protocols:RAPP and gossamer [C//Proc of the 7th International Conference for Internet Technology and Secured Transactions.Piscataway,NJ: IEEE Press,20l2: 80-86.   
[10] 马庆，郭亚军，曾庆江，等．一种新的超轻量级 RFID 双向认证协议 [J]．信息网络安全,(Ma Qing,Guo Yajun,Zeng Qingjiang,et al.A new ultra-lightweight RFID mutual authentication protocol [J].Netinfo Security,2016 (5):44-50.)   
[11] 张兴，李畅，韩冬，等．基于 Hash 轻量级 RFID 安全认证协议 [J]. 计算机工程与设计,2018,39(5):1269-1275.(Zhang Xing,Li Chang, Han Dong,et al.Lightweight security authentication protocol for RFID based on hash functions [J]. Computer Engineering and Design,2018, 39 (5): 1269-1275.)   
[12] 杨昕，凌捷．一种低成本超轻量 RFID 双向认证协议[J].计算机科 学，2016，43 (4):160-162．(Yang Xin，Ling Jie．Low-cost ultralightweight RFID mutual-authentication protocol [J].Computer Science,2016,43 (4):160-162.)   
[13]柳毅，顾国生．一种新的轻量级RFID双向认证协议[J].计算机科 学，2017,44 (2):206-208.(Liu Yi，GuGuosheng.New mutual authentication for lightweight RFID protocols [J]. Computer Science, 2017,44(2):206-208.)   
[14]马远佳，刘道微．一种改进的满足后向安全的 RFID双向认证协议 [J]．计算机工程与应用，2017,53(9):136-140.(Ma Yuanjia,Liu

Daowei. Improved mutual authentication with backward security for RFID protocols.Computer Engineering and Applications,2017,53 (9): 136-140.) [15]魏棉裕，欧毓毅.改进的抗去同步化攻击RFID 安全协议[J].计算 机工程与设计，2017,38(7):1719-1723.(Wei Mianyu,Ou Yuyi, Improved resistance de-synchronization attack RFID security protocol [J].Computer Engineering and Design,2017,38(7):1719-1723.)