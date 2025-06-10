# 基于激活标志位的改进RFID密钥无线生成算法

杨俊1，邹志革²

(1．武汉职业技术学院，武汉 430074;2．华中科技大学，武汉 430074)

摘要：针对现有三种常见无线射频识别密钥无线生成场景下,设计的相应密钥生成算法中存在的算法理论证明缺失、重放攻击、密钥伪造攻击以及RFID标签身份ID泄露的安全性问题，设计了更安全的基于激活标志位的改进RFID 系统密钥无线生成算法。改进算法仅基于多种超轻量级位运算来组合构建安全的算法框架，降低成本，提高效率；利用激活标志位AckBit 机制以及新鲜性机制抵抗重放、密钥伪造攻击；通过完整GNY逻辑证明过程与安全性对比分析，证明目标算法的安全可行性。最后，给出原算法与改进算法之间的标签成本代价对比，表明改进的算法在满足低成本的条件下具有更高的安全性。

关键词：无线射频识别；密钥无线生成；更安全；激活标志位；GNY逻辑证明 中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2018.06.0404

# Improved RFID key wireless generation algorithm based on activation flag

Yang Junl, Zou Zhige² (1.Wuhan Polytechnic,Wuhan 43074,China;2.Huazhong UniversityofScience&Technology,Wuhan430074,China)

Abstract:Inthescenarioofwireless generationofthreecommonradio frequencyidentificationkeys,thesecuritykeyproblem of replayattck,key forgeryattck andRFID tag identity ID leakage and the lack of algorithm theoryarefound in the corresponding key generation algorithms.This paper designed amore secure RFID-based key generation algorithm based on activation flag.The improvedalgorithmonlycombinedmultiplesuper-lightweightbitoperations toconstructasecurealgorithm framework,which reduced cost and improves eficiency.Itused the activation flag‘AckBit’mechanismand the freshne mechanism to resist replayand key forgery atacks.Through the complete GNY logic proof processand safetycomparison analysis,itprovedthesafetyandeasibilityofthetargetalgorithm.Finally,Tispaperpresentedthecomparisonofetagcost between theoriginalalgorithmandtheimprovedalgorithm,whichshows thatthe improvedalgorithmhas highersecurityunder the condition of satisfying the low cost.

Key words:RFID; wireless key generation; more secure;activation flag; GNY logic proof

# 0 引言

随着物联网的不断发展其感知层的重要技术一无线射频识(radio frequency identification，RFID)也越来越受到人们的重视[1]。在RFID系统中标签和读写器通常需要进行相互认证、识别、定位等操作，这就需要共享密钥的参与，而密钥的下发通常有两种方式一种是在出厂已经设置好，密钥值单一固定；另一种方式是通过密码学相关算法手段在读写器和标签两端同时实现密钥的无线生成，具有动态、便捷的优点[2-3]。这第二种方法是近年来的研究热点，但是也正是由于RFID系统这种动态开放性，使得共享密钥如何快速、安全、准确的生成成为了当下RFID密钥无线生成算法需要解决的重点问题[4]。近年来以超轻量位运算为基础的密钥无线生成算法，因为其具有动态不可预测性、成本低、安全性较为可靠等优点被广泛研究。

# 1 相关研究

文献[5]首次提出RFID密钥无线生成思想，跳出了密钥事先预设带来的局限性，并根据"后向信道不可窃听"的假设，提出了“WiKey”RFID密钥无线生成算法。但是，随后多篇文献指出了WiKey算法假设的应用局限性，大多指出了其因为所有通信数据均明文传输而存在密钥伪造的风险，并分别提出了各自的改进算法，主要有文献[6-9]，其中主要优缺点具体分析如下：

文献[6]提出了一种基于多种位运算（字合成位运算、交叉位运算、异或、与运算）的RFID 密钥生成算法。其利用标签编号信息通信，认证效率有所提升，但是该算法在单标签密钥生成场景中其实也存在标签身份ID 暴露的风险；又因为系统标签端每个标签都需要生成随机数来进行认证计算，这会增加系统成本与复杂性，不能满足低成本应用。

文献[7]也提出了一种新的密钥生成算法，虽然解决了WiKey算法的安全性缺陷，但是该算法的认证过程需要进行两轮通信才能完成，效率不高。

文献[8]提出了一种基于标签部分ID的改进算法，该算法由于只引入标签ID信息和随机数，成本较低，适合低成本应用环境，但是通过本文的研究发现该算法在生成群组标签的场景下，因为不能抵抗窃听、重放攻击而造成标签身份泄露以及密钥伪造。具体漏洞分析如下： $\textcircled{1}$ 标签身份泄露漏洞：因为在通信过程中，攻击者A可以窃听第二步通信过程，组内标签 $T _ { \mathrm { i } }$ 会发送 $\scriptstyle M _ { i } = I D _ { i r } \oplus I D _ { i l }$ 得到所有标签的 $M _ { \mathrm { i } }$ ，接着继续窃听第三步，读写器向所有标签明文发送 $( I D _ { i l } , k _ { i } )$ ，攻击者A即可根据窃听得到的信息，解密得到 $\scriptstyle { I D _ { i r } = M _ { i } \oplus I D _ { i l } }$ ，因为事先已经获得窃听得到的明文标签ID的左半部分，这样标签完整身份ID信息得到（ $: I D _ { i } = I D _ { i l } \parallel I D _ { i r } )$ ，标签身份泄露。 $\textcircled{2}$ 密钥伪造漏洞：又因为算法设计中缺少随机数新鲜性验证，攻击者A完全可以假冒标签，重放 $M _ { \mathrm { i } }$ 或者根据解密得到的 $( I D _ { i r } ^ { } , I D _ { i l } ^ { } )$ 重新计算 $M _ { \mathrm { i } }$ ，通过数据库的合法性验证得到密钥计算因子 $k _ { \mathrm { i } }$ ，解密得到密钥$k { = } k _ { i } \oplus I D _ { i r }$ ，或者直接根据已经得到的所有标签ID信息，直接计算得到密钥 $\mathbf { k }$ 。因此，该算法不能抵抗重放攻击存在密钥伪造以及标签身份泄露风险。

文献[9]提出了一种基于假名标志的加密RFID 密钥生成算法，引入假名标志一定程度上可以防止标签身份信息泄露，但是经过本文的研究发现，该算法在单个标签密钥生成场景下仍然存在密钥伪造攻击漏洞。因为，在读写器向标签发送加密的$A { = } r _ { 1 } \oplus I D S$ 、 $B { = } r _ { 2 } \oplus I D S$ 消息时，攻击者可以直接通过窃听跟踪得到消息A、B，并用这两个数据本身破解计算1 $\stackrel { \cdot } { A } \oplus B = r _ { 1 } \oplus I D S \oplus r _ { 2 } \oplus I D S = r _ { 1 } \oplus r _ { 2 } = k$ ）即可得到该算法的密钥信息 $k$ ，所以攻击者可以根据算法本身设计的漏洞快速暴力破解得到系统密钥信息 $k$ ，因此该协议存在密钥伪造攻击漏洞。

综上所示，现有的RFID系统密钥无线生成算法主要存在以下缺点，如表1所示。

表1现有算法漏洞分类  

<html><body><table><tr><td>现存协议缺点</td><td>相关文献</td></tr><tr><td>效率较低</td><td>文献[7]</td></tr><tr><td>缺少形式化证明</td><td>文献[5、6、7、8、10]</td></tr><tr><td>重放攻击</td><td>文献[5、8、9]</td></tr><tr><td>标签身份ID 泄露</td><td>文献[6、8]</td></tr><tr><td>密钥伪造攻击</td><td>文献[5、6、8、9、10]</td></tr></table></body></html>

针对以上文献[5]和文献[8，9]中存在的算法漏洞，本文提出了一种改进的更安全的在单标签密钥生成、多标签密钥生成、群组标签密钥生成三种场景下分别适用的算法。

# 2 改进的更安全的RFID系统密钥无线生成算法

# 2.1 前提与符号说明

同一般RFID系统密钥无线生成算法的基本前提假设特征相似，后台数据库和读写器之间视为统一安全整体，下文统称读写器；而读写器和标签之间视为不安全的通信信道[11-12]因此需要在设计协议时进行加密传输保证安全性。其中自组合交叉位运算 $S a c ( X , Y )$ 基本原理参考文献[13]，本算法所需符号说明如下表2所示。

表2符号说明  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>Tag</td><td>合法标签</td></tr><tr><td>Reader</td><td>合法读写器</td></tr><tr><td>ID</td><td>标签唯一身份标志、</td></tr><tr><td>TID</td><td>标签假名身份标志</td></tr><tr><td>TID_L</td><td>标签假名身份标志的左部分</td></tr><tr><td>TID_R</td><td>标签假名身份标志的右部分</td></tr><tr><td>Key</td><td>标签与读写器之间共享密钥</td></tr><tr><td>ki</td><td>密钥生成因子</td></tr><tr><td>AckBit</td><td>激活标志位,AckBit=1标签激活；AckBit=0 标签未激活</td></tr><tr><td>r1、r2</td><td>标签与读写器之间随机数</td></tr><tr><td>r、rr</td><td>随机数的左、右两部分</td></tr><tr><td>A，B,C,D</td><td>通信数据</td></tr><tr><td>Sac(X,Y)</td><td>自组合交叉位运算</td></tr><tr><td>Rot(X, Y)</td><td>循环移位运算</td></tr><tr><td></td><td>异或运算</td></tr></table></body></html>

# 2.2算法具体过程

在协议初始状态中，标签保存唯一身份标志 $I D$ ，，并且利用自身的标志信息 $I D$ 生成标签Tag的假名信息$T I D = R o t ( I D _ { - } L , I D _ { - } R )$ ，将 $T I D$ 的左右两部分保存，最后标签端存储字段内容为 $( I D _ { i } , T I D _ { i } \tiny { \underline { { { \cal L } } } } , T I D _ { i - } R )$ ，其中i为标签标号；每个标签在读写器中的数据存储结构为(i， $I D$ ， $T I D _ { i \_ L }$ $T I D _ { i \_ R }$ ，AckBit $\scriptstyle \cdot = 0$ （初始状态为0））。

2.2.1基于多标签密钥批量无线生成场景下算法

读写器为多标签批量生成相应的个体密钥算法具体过程如下，如图2所示。多密钥生成与单密钥生成算法过程相似，不同之处在于：

a）Tagi，…，Tagi多个标签发送密钥生成请求命令以及自身标号i， ${ < } R q$ ，1，4，i，>等待读写器回复。b)读写器在给定时间内内依次响应并按标号i顺序排队等待验证，所有标签 $T _ { \mathrm { i } }$ ，依次按步骤c)\~f完成密钥的生成过程，如果超时或者认证失败，协议终止；如果数据库同步生成密钥成功后，进行步骤f)。

c)读写器根据标签发送的标号 $i$ 以及激活标志AckBit判断算法是否继续。如果检索到 $i$ 并且激活标志 $\scriptstyle A c k B i t = 0$ ，算法继续，将检索到的数据(i，IDi， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ ，AckBit)计算得到对应的 $\mathit { T I D } _ { i } = R o t ( I D _ { i } \_ L , I D _ { i } \_ R )$ ，并生成两个随机数 $r _ { 1 } , \ r _ { 2 }$ 计算得到 $A { = } T I D _ { i } \mathrm { ~ } _ { - } L \oplus r _ { 1 }$ 、 $B { = } T I D _ { i } \mathrm { ~ } _ { - } R \oplus r _ { 2 }$ ，最后将 $A , B$ 发送给标签Tag；如果标号 $i$ 检索成功但是激活标志 $A c k B i t { = } 1$ ，说明标签密钥已生成过，重复申请，算法终止；如果标号 $i$ 检索失败，算法终止。

d）标签Tag在收到数据 $A , \ B$ 后，利用事先存储的假名信息 $( T I D _ { i } { } _ { - } L , T I D _ { i } { } _ { - } R )$ ，解密 $A , B$ 得到随机数 $r _ { 1 } , \ r _ { 2 }$ ，具体解密过程如下： $r _ { 1 } { = } T I D _ { i }  L \oplus A$ 、 $r _ { 2 } { = } T I D _ { i } \mathrm { ~ } _ { - } R \oplus B$ ，解密成功后，标签生成待验证数据 $C$ ，$C = R o t ( r _ { 1 } \_ L , T I D _ { i } \_ L ) \oplus R o t ( r _ { 2 } \_ L , T I D _ { i } \_ L )$ ，最后将数据C发送给读写器。

e）读写器收到消息 $c$ 后，通过原有生成的 $r _ { 1 } , r _ { 2 }$ 以及 $\boldsymbol { T I D } _ { i }$ 信息，计算得到 $C ^ { \prime }$ ，随后验证 $C$ 是否等于 $\mathbf { \nabla } C ^ { \dagger }$ ，如果相等读写器验证标签成功，标签合法，向标签发送密钥生成命令Create,同时数据库同步为标签生成密钥Keyi，$K e y _ { i } = S a c ( r _ { 1 } ^ { } - R , I D _ { i } ^ { } ) \oplus S a c ( r _ { 2 } ^ { } - R , I D _ { i } ^ { } )$ ，得到标签新的存储字段(i， $I D$ ， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ ，Keyi，AckBit=1)。

f）标签Tag收到密钥生成命令Create后，密钥生成得到 Keyi， $K e y _ { i } = S a c ( r _ { 1 } ^ { } \_ R , I D _ { i } ^ { } ) \oplus S a c ( r _ { 2 } ^ { } \_ R , I D _ { i } ^ { } ) \ _ { \circ }$

![](images/d0681850163556c6652f31961698b8c1621c0f9cdfb348a2bef3fcac903fce70.jpg)  
图1基于多标签密钥批量无线生成场景下改进算法过程图

2.2.2基于单标签密钥无线生成场景下算法

读写器为单个标签生成相应的个体密钥算法作为多标签的特例具体过程将不做重复描述，单标签过程图具体如下，如图2所示。

![](images/e7ef62b6f2a1b43b9766da5f4666e6099363166fe3621e26dc652a357158d95e.jpg)  
图2基于单标签密钥无线生成场景下改进算法过程图

2.2.3基于组标签组密钥无线生成场景下算法

读写器为群组标签生成统一的组密钥算法具体过程如下，如图3所示。

a）首先读写器向群组标签广播，下发密钥生成命令。

b）群组标签收到命令 $\mathrm { R q }$ 后，组内所有标签分别利用自身的假名信息计算得到验证数据 $\scriptstyle A _ { 1 }$ ， $\mathbf { \nabla } _ { A _ { 2 } }$ ，…Ai，并将所有 $\mathbf { A } \mathrm { { i } }$ 信息发送给读写器， $A _ { i } = R o t ( T I D _ { i } \dots R , T I D _ { i } \dots R ) \oplus i ,$ 0

c）读写器收到所有 $\mathbf { A } _ { \mathrm { i } }$ 信息后，在给定的时间内，根据存储的字段信息(i， $I D$ ， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ ，AckBit)，计算$A _ { i } \oplus i = R o t ( T I D _ { i } \_ L , T I D _ { i } \_ R )$ ，检查读写器组内标签记录中的字段是否全部有对应的 $\mathbf { A } _ { \mathrm { i } }$ 消息满足，如果全部满足并且相等，说明组内所有标签的信息在读写器中都可以找到，组内所有标签激活成功，读写器存储的字段信息更新为 $( i , \ I D , \ T I D _ { i } \ { \_ } L$ $T I D _ { i \_ R }$ ，AckBit $\scriptstyle \{ = 1 \atop  \sum $ )；若读写器组内标签记录中任意一条记录未与标签发送的 $\mathrm { \mathbf { A } } _ { \mathrm { i } }$ 消息对应，组内标签激活失败，在给定时间内，再次启动新一轮激活，直到组内标签记录全部相等，如果时间超时，算法终止。当组内所有标签激活成功后，读写器生成随机数 $\textit { r }$ ，开始为群组标签生成共享组密钥Key，$K e y = S a c ( I D _ { 1 } , r ) \oplus S a c ( I D _ { 2 } , r ) \oplus \cdots \oplus S a c ( I D _ { i } , r )$ ，并为组内每个标签生成加密的组密钥计算因子 $K _ { \mathrm { i } }$ ， $K _ { i } = K e y \oplus S a c ( I D _ { i } , r )$ 因为组内标签需要得到随机数 $\boldsymbol { r }$ 才能解密得到组密钥 $K e y$ ，所以读写器还需为组内标签发送一组消息 $B _ { \mathrm { i } }$ 、Ci、 $D _ { \mathrm { i } }$ ，具体加密过程如下： $B _ { i } = T I D _ { i } \_ L \oplus r \_ L$ ， $\begin{array} { r } { C _ { i } = T I D _ { i } \underline { R } \oplus r \underline { R } } \end{array}$ ，$D _ { i } = R o t ( T I D _ { i } , r )$ 。最后向标签发送消息 ${ < } K _ { \mathrm { i } }$ 、 $B _ { \mathrm { i } }$ 、 $C _ { \mathrm { i } }$ 、 $D _ { \mathrm { i } } { > }$ 。

d）组内标签在收到消息 ${ < } K _ { \mathrm { i } }$ 、 $B _ { \mathrm { i } }$ ， $C _ { \mathrm { i } }$ 、 $D _ { \mathrm { i } } { > }$ 后，首先根据各标签端存储字段内容为 $( I D _ { i } , T I D _ { i } \_ L , T I D _ { i } \_ R )$ ，解密得到随机数 $\boldsymbol { r }$ ，具体解密过程如下： $r _ { - } L = T I D _ { i } \ O _ { - } L \oplus B _ { i }$ ，$r _ { - } R = T I D _ { i } \ O _ { - } R \oplus C _ { i }$ ， $r = r _ { - } L \| r _ { - } R$ 。随后标签计算得到 $D ^ { \prime }$ ，验证是否和收到 $D$ 相等，如果相等，说明标签对读写器验证成功，组内各标签利用解密得到的 $\mathbf { r }$ 以及自身的身份ID信息计算得到组密钥 $K e y _ { i }$ ， $K e y _ { i } = K _ { i } \oplus S a c ( I D _ { i } , r )$ 。并依次向读写器发送确认命令 $S _ { i } = K e y _ { i } \oplus T I D _ { i } \_ L \oplus T I D _ { i } \_ R .$ 0

e)读写器在规定时间内收到组内所有 $S _ { \mathrm { i } }$ 确认命令，需要对比组内标签计算得到的组密钥是否全部相等。Reader根据存储的各个标签字段 $\mathit { \Omega } _ { : } ( i , \ { I D } , \ { T I D } _ { i \_ L } , \ { T I D } _ { i \_ R } , \ { A c k B i t } { = } 1 )$ ，解密 $S _ { \mathrm { i } }$ 解密得到如果 $K e y _ { 1 } = K e y _ { 2 } = \cdots = K e y _ { i }$ 全部相等，说明组内各个标签成功得到组密钥，最后，读写器存储的字段信息更新为(i，$I D$ ， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ ，Key，AckBit $\scriptstyle \sum \prime$ )，向标签组广播回复update命令；如果有任意 $K e y _ { i }$ 不相等，说明组密钥因子错误，算法终止。

f)标签端收到update命令，组内各标签存储字段内容更新为 $( I D _ { i } , T I D _ { i } \_ L , T I D _ { i } \_ R , K e y )$ ，至此算法完成。

综上所述，本节分别在三种不同场景下设计了改进的更安全的的可密钥伪造、标签隐私泄露的RFID系统密钥无线生成算法，该算法基于循环移位、异或、自组合交叉位运算实现标签激活和加密认证过程；在组密钥生成场景下引入随机数保证密钥新鲜性，防止重放攻击；在整个通信过程中标签真实身份ID 匿名隐藏，仅利用假名TID代替ID进行计算，防止身份泄露；利用标签标号i和AckBit激活标志位的对应关系标记标签

状态信息，提高算法效率。

![](images/f41d5842ceb6ad02eed98f629c7c2a39e9e197013a21ece746bb8c64449791cb.jpg)  
图3基于组标签密钥无线生成场景下改进算法过程图

# 3 算法形式化证明

GNY逻辑是基于知识和信念的逻辑推理方法之一，其证明思想与方法较普遍的应用在RFID 算法证明中。GNY逻辑是由若干公理、规则组成其基本定义可参见文献[14,15]，本文证明过程中主要用到了以下规则：

可识别规则 $\mathrm { R } _ { 1 } { = } \frac { P { \big | } { \equiv } \phi ( X ) } { P { \big | } { \equiv } \phi ( X , Y ) , P { \big | } { \equiv } \phi ( F ( X ) ) }$ 可识别规则 $\mathrm { R } _ { 2 } { = } \frac { P { \ l } { \equiv } { \phi } ( X ) , P \in \cal K } { P { \left| \equiv { \phi } ( X ) _ { K } , P \right| } { \equiv } { \phi } ( F ( X , K ) ) }$ 新鲜性规则 $\mathrm { F } _ { 1 } { = } \frac { P { \big | } { \equiv } \# ( X ) } { P { \big | } { \equiv } \# ( X , Y ) , P { \big | } { \equiv } \# ( F ( X ) ) }$ 消息解析规则 $\mathrm { I } _ { 1 } =$ $\begin{array} { r l } &  \frac  P \triangleleft ^ { * } ( X ) _ { \kappa } , P \in K , P \models P \widecheck { = } P \widecheck  \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } P \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } P \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { = } \widecheck  \widecheck { = } \widecheck { = } \widecheck { = } \widecheck { \widecheck { = } } \widecheck  \widecheck { = } \widecheck { = } \widecheck { } \widec i \widec i { } \widec i { } \widec i { = } \widec a { } \widec i \widec i { } \widec a { } { = } \widec a { } \widec a { } \widec a  { = } \widec a { } \widec a { } { = } \widec a { } \widec a { } { \widec a { } \widec a { } \widec a { } { = } \widec a { } \widec a { } { = } \widec a { } \widec a { } { } \widec a { \widec a { } \widec a { } \ m { } \widec a { } \ m { = } \ m \ m { } \ m { = } \widec a { } \ m { } \ m \ m { = } \ m \ m { } \ m \ m { } \ m \ m { \ m } \ m { \ i } \ m { } \ m \ m { \ m \ i } \ m { } \ m \ m { = } \ m \ m \ m \ a { } \ a \ m { } \ m { } \ m \ a { } \ a { } \ a \ a { } \ a } \ m \ a { \ a \ a } { { } \ a } \ a \ a { \ a \ a { } } \ a { \ a } \ a \ a { } \ a \ a { } \ a \ a { } } \end{array}$

1）初始化假设

由于3种不同场景算法过程类似，本节只对基于单标签密钥生成改进算法作具体分析证明，其余两种情况由于过程类似，篇幅有限，将不做重复描述。

首先对单个标签密钥生成算法进行初始化假设，其中， $\mathrm { H } _ { 1 }$ 、$\mathrm { H } _ { 2 }$ 表示标签、读写器已经拥有的； $\mathrm { H } _ { 3 }$ 、 $\mathrm { H } _ { 4 }$ 表示标签、读写器相信各自某些信息是可识别的； $\mathrm { H } _ { 5 }$ 、 $\mathrm { H } _ { 6 }$ 表示标签、读写器对某些数据新鲜性的相信。

$\mathrm { \Delta H _ { l } }$ $T a g \in ( i , I D , T I D \_ L , T I D \_ R )$   
$\mathrm { H } _ { 2 }$ ：1 $\displaystyle \ell a d e r \in ( i , I D , T I D \_ L , T I D \_ R )$   
H $\mathrm { ~ : ~ } T a g \vert \equiv \phi ( i )$   
H4: Reader/=Φ(r,r2)  
H5:Tag|=#(r,r2)  
$\mathrm { H } _ { 6 }$ : Reader|=#(TID,r,r2)

2）形式化模型

对单个标签密钥生成算法作过程进行GNY逻辑形式化建模，完整模拟算法交互过程。其中，用M表示通信过程，标签主体用Tag表示，读写器用Reader表示。

$\mathbf { M } _ { 1 }$ : Reader <\*(i)$\mathbf { M } _ { 2 }$ ： $T a g \triangleleft * F _ { 1 } ( r _ { 1 } , T I D \_ L ) , F _ { 2 } ( r _ { 2 } , T I D \_ R )$ $\mathbf { M } _ { 3 }$ : Reader $\triangleleft * F _ { 3 } ( r _ { 1 - } L , r _ { 2 - } L , T I D _ { - } L )$ （204号

3）安全目标

对单个标签密钥生成算法用GNY逻辑语言定义需要达到的安全性目标，其中， ${ \bf D } _ { 1 }$ 表示读写器对标签身份的初次识别；${ \bf D } _ { 2 }$ 、 ${ \bf D } _ { 3 }$ 表示标签对读写器验证，对发送信息新鲜性的相信； $\mathrm { D } _ { 4 }$ 表示读写器对标签验证，对标签身份的再次识别。

$$
\mathrm { D } _ { 1 } \colon \ R e a d e r \left| \equiv T a g \right| \phi ( i )
$$

$$
\begin{array} { r l } & { \textrm { D 1 : } \quad \scriptstyle \mathrm { X C a t e r : } \quad \scriptstyle \mathrm { \vdash } \quad \mathbf { \Psi } \displaystyle \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E } \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E ~ } \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E ~ } \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E ~ } \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E ~ } \mathrm { : } \ x \in \mathcal { A } \displaystyle \mathrm { ~ E ~ } \mathrm { : } } \\ & { \mathrm { D _ { 2 : } } \quad \scriptstyle T a g \Big | \equiv R e a d e r \Big | \sim \# F _ { 1 } ( r _ { 1 } , T I D _ { - } L ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \mathrm { ~ D _ { 3 : } ~ } \quad \scriptstyle T a g \Big | \equiv R e a d e r \Big | \sim \# F _ { 2 } ( r _ { 2 } , T I D _ { - } R ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \mathrm { ~ D _ { 4 : } ~ } \quad R e a d e r \Big | \equiv T a g \big | \phi F _ { 3 } ( r _ { 1 } , \dotsc , r _ { 2 } \mathbin { \_ L , T I D } \mathbin { \_ L } ) } \end{array}
$$

4）证明过程

当读写器收到消息 $\mathbf { M } _ { 1 }$ ，也即是Reader $\triangleleft { * ( i ) }$ ，读写器查找后台数据库记录(i，ID， $\mathrm { T I D } _ { \mathrm { i } } \mathrm { \underline { { ~ L ~ } } }$ ，TIDi_R，AckBit)，检索符合的标签标号信息i，如果检索成功，读写器初次识别标签成功，也即是 $R e a d e r \lvert \equiv \phi ( i )$ ，安全性目标 ${ \bf D } _ { 1 }$ 得证。

当标签收到消息 $\mathbf { M } _ { 2 }$ 后，也即是到 $A { = } T I D \_ L \oplus r _ { 1 }$ 、$B { = } T I D _ { - } R \oplus r _ { 2 }$ ，由初始化假设 $\mathrm { H } _ { 5 }$ ： $T a g \left| \equiv \# ( r _ { 1 } , r _ { 2 } ) \right.$ 可知$T a g \left| \equiv \# ( r _ { 1 } ) \right.$ ，再由初始化假设 $\mathrm { H } _ { \mathrm { l } }$ ：$T a g \in ( i , I D , T I D \_ L , T I D \_ R )$ 可知 $T a g \in ( T I D \_ L )$ ，$T a g \left| \equiv \phi ( T I D ) \right. \Rightarrow \phi ( r _ { 1 } , T I D )$ ，再根据新鲜性规则 F1可得$T a g \left| \equiv \# ( r _ { 1 } , T I D _ { - } L ) \right.$ ，继续根据新鲜性规则F1，可得$T a g \left| \equiv \# F _ { 1 } ( r _ { 1 } , T I D _ { - } L ) \right.$ ，接着根据消息解析规则I1（其中，$T a g \in ( i )$ 、Tag $T \longleftrightarrow R$ 、Tag l=𝜙(r,TID)、Tag $\triangleleft * ( r _ { 1 } )$ 、$T a g \left| \equiv \# F _ { 1 } ( r _ { 1 } , T I D _ { - } L ) \right. )$ ，终得 $T a g \left| \equiv R e a d e r \left| \sim \# F _ { 1 } ( r _ { 1 } , T I D _ { - } L ) \right. \right.$ ，安全性目标 ${ \bf D } _ { 2 }$ 得证。安全性目标 ${ \bf D } _ { 3 }$ ：由初始化假设 $\mathrm { H } _ { 5 }$ ：$T a g \left| \equiv \# ( r _ { 1 } , r _ { 2 } ) \right.$ 可知 $T a g \left| \equiv \# ( r _ { 2 } ) \right.$ ，再由初始化假设 $\mathrm { H } _ { \mathrm { l } }$ ：$T a g \in ( i , I D , T I D \_ L , T I D \_ R )$ 可知 $T a g \in ( T I D \_ R )$ ，再由可识别规则 ${ \bf R } _ { 1 }$ 、 ${ \bf R } _ { 2 }$ 可以得到 $T a g \left| \equiv \phi ( T I D ) \right. \Rightarrow \phi ( r _ { 2 } , T I D )$ ，再根据新鲜性规则F1可得 $T a g \left| \equiv \# ( r _ { 2 } , T I D _ { - } R ) \right.$ ，继续根据新鲜性规则F1，可得 $T a g \left| \equiv \# F _ { 2 } ( r _ { 2 } , T I D _ { - } R ) \right.$ ，接着根据消息解析规则I1（其中，Tag∈(i）、Tag|= $T a g \longleftrightarrow$ Reader

$T a g | \equiv \phi ( r _ { 2 } , T I D )  , \ T a g \ \triangleleft \ast ( r _ { 2 } )  , \ T a g | \equiv \# F _ { 2 } ( r _ { 2 } , T I D \_ R )  $ ，可得$T a g \left| = R e a d e r \right| \sim \# F _ { 2 } ( r _ { 2 } , T I D \_ R )$ ，安全性目标 ${ \bf D } _ { 3 }$ 得证。

当读写器收到来自标签的消息 $\mathbf { M } _ { 3 }$ 后，也即是：$C = R o t ( r _ { 1 } \_ L , T I D \_ L ) \oplus R o t ( r _ { 2 } \_ L , T I D \_ L )$ ，读写器再次查找后台数据库记录(i，ID， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ ，AckBit)，以及随机数$r 1 , \ r _ { 2 }$ ，验证标签，可以得到 $R e a d e r | \equiv \phi ( r _ { 1 - } L , r _ { 2 - } L , T I D _ { - } L )$ ，最后再根据可识别规则R1：得到$R e a d e r | \equiv \phi F ( r _ { 1 - } L , r _ { 2 - } L , T I D \_ L )$ ，预期目标 $\mathrm { D } _ { 4 }$ 实现。

# 4 算法安全性分析

本章主要从第2章提到文献[5,8,9]中存在的标签匿名性、重放攻击、密钥伪造攻击三个方面对本文改进算法进行分析。

在三个应用场景下改进算法都可以保证标签匿名性，分析如下：因为在三种场景下标签收到读写器的请求后，并没有直接利用标签本身的 $I D$ 信息进行计算，而是将标签的标号信息i进行初次识别，并且将标签 $I D$ 信息进行加密得到假名TID，$T I D = R o t ( I D _ { - } L , I D _ { - } R )$ ，再将 $T I D$ 分成左、右两部分，即使攻击者通过窃听得到 $< A$ 、 $B$ 、 $C >$ 也无法轻易以第二节描述的解密方式得到TID以及随机数 $r _ { 1 }$ 、 $r _ { 2 }$ 结果，改进协议可以在三种场景下安全的保证标签匿名性，而根据本文第2章相关研究中表明文献[8]不能保证标签匿名性。

在三个应用场景下改进算法都可以抵抗重放攻击，分析如下：基于单标签和多标签的应用场景下，无论是攻击者窃听重放 $\scriptstyle < A$ 、 $B$ 、 $c >$ 中的任意消息（ $A { = } T I D _ { - } L \oplus r _ { 1 }$ 、 $B { = } T I D \_ R \oplus r _ { 2 }$ 、$C = R o t ( r _ { 1 } \_ L , T I D \_ L ) \oplus R o t ( r _ { 2 } \_ L , T I D \_ L ) \stackrel { . } { \longrightarrow }$ ，都会因为随机数错误而使算法终止，在基于群组标签密钥生成场景中，改进算法在密钥Key的生成中加入随机数 $\boldsymbol { r }$ ，’$K e y = S a c ( I D _ { 1 } , r ) \oplus S a c ( I D _ { 2 } , r ) \oplus \cdots \oplus S a c ( I D _ { i } , r )$ ，即使攻击者重放A，因为攻击者不知道标签 $( I D _ { i } , T I D _ { i } \_ L , T I D _ { i } \_ R )$ 身份字段，也无法攻击成功，并且读写器端(i， $I D$ ， $T I D _ { i \_ L }$ ， $T I D _ { i \_ R }$ $A c k B i t ) A c k B i t$ 激活标志的存在，使得标签AckBit已经置1，当攻击者重放消息时，AckBit 激活标志检验出错误，算法一样会终止。因此，改进协议可以在三种场景下安全的抵抗重放攻击，而根据本文第2节相关研究中表明文献[5，8，9]均不能抵抗重放攻击。

在三个应用场景下改进算法都可以抵抗密钥伪造攻击，分析如下：因为在基于单标签应用场景下改进算法共享密钥的加密方式是 $K e y = S a c ( r _ { 1 } ^ { } - R , I D ) \oplus S a c ( r _ { 2 } ^ { } - R , I D )$ 、基于多标签应用场景下改进算法共享密钥的加密方式是$K e y _ { i } = S a c ( r _ { 1 } ^ { } - R , I D _ { i } ^ { } ) \oplus S a c ( r _ { 2 } ^ { } - R , I D _ { i } ^ { } )$ ，可以看出这两种场景下生成密钥的方式都需要随机数和标签身份信息的加入，而攻击者在整个通信过程中都不曾得到标签ID的信息，只有假名TID 的参与，攻击者并不能获得完整的数据；在基于群组标签应用场景下改进算法共享密钥的加密方式是$K e y = S a c ( I D _ { 1 } , r ) \oplus S a c ( I D _ { 2 } , r ) \oplus \cdots \oplus S a c ( I D _ { i } , r )$ ，而这第三种组密钥的产生方法中也同样引入随机数r，标签必须计算出所有组内正确的解密关键因子 $S a c ( I D _ { i } , r )$ ，才可以顺利的破解组密钥 $K e y = K _ { i } \oplus S a c ( I D _ { i } , r )$ ，并且因为AckBit 激活标志的存在，必须保证读写器对组内所有标签的记录都是 $( i , I D , T I D _ { i \_ L } , T I D _ { i \_ R } $ $A c k B i t { = } 1 \$ ，读写器才会为标签生成统一的组密钥 $( i , I D , T I D _ { i \_ L }$ ，$T I D _ { i \_ R }$ ， $K e y$ ，AckBit $\scriptstyle \{ = 1 \atop  \sum $ )，因此，改进协议可以在三种场景下安全的抵抗密钥伪造攻击，而根据本文第2节相关研究中表明文献[5、8、9]均不能抵抗密钥伪造攻击。

# 5 改进算法性能分析

根据第4节算法形式化证明以及第5节安全性对比分析，下面给出相关文献与本文算法的安全性对比，见表3，其中，√表示满足安全性； $\times$ 表示不能满足安全性。

表3算法安全性对比  

<html><body><table><tr><td>攻击类型</td><td>文献[5]</td><td>文献[8]</td><td>文献[9]</td><td>本算法</td></tr><tr><td>标签匿名</td><td>√</td><td>×</td><td>×</td><td>7</td></tr><tr><td>重放攻击</td><td>√</td><td>×</td><td>√</td><td>√</td></tr><tr><td>密钥伪造</td><td>×</td><td>×</td><td>×</td><td>√</td></tr><tr><td>算法证明</td><td>×</td><td>×</td><td>√</td><td>√</td></tr></table></body></html>

由于群组密钥组标签密钥无线生成场景和批量标签密钥无线生成场景下因为标签数量的不同无法计算对比，这里不再对比说明，本节主要统一对单个标签密钥场景下密钥无线生成算法，从标签的计算量、存储量和通信量三个方面与相关文献进行性能分析对比，如表4进行说明，在表4中，Xt表示异或运算，PRNG表示随机数产生器，R表示移位运算，Rt表示循环移位运算，Sa表示自组合交叉位运算，假名TID、标签唯一标志ID、密钥Key、随机数的长度都是I，X表示认证过程中的临时存储空间，通信量的单位为L。

表4单个标签密钥生成改进算法性能对比  

<html><body><table><tr><td>相关文献</td><td>计算量</td><td>存储空间</td><td>通信量</td></tr><tr><td>文献[5]</td><td>Xt+PRNG</td><td>I+X</td><td>L</td></tr><tr><td>文献[8]</td><td>7Xt</td><td>4I+X</td><td>L</td></tr><tr><td>文献[9]</td><td>5Xt+R</td><td>2I+X</td><td>L</td></tr><tr><td>本文</td><td>4Xt+2Rt+2Sa</td><td>3I+X</td><td>2L</td></tr></table></body></html>

![](images/096c5af7253ae7ea8748b63c374dc2764ec3d53302788f99133ebf133b02afbf.jpg)  
图4相关文献标签计算代价柱状对比图

通过表3、4，图4可以看出，对于单个标签密钥生成算法，相较于文献[5，8，9]，本文算法无论是标签计算量、存储空间还是通信量和对比算法类似，达到超轻量标准，但是相较于对比算法，本文的改进算法在保证算法安全性更高的同时标签端计算代价并没有提高，标签端计算代价低于平均值，满足低成

本应用。

# 6 结束语

本文在RFID 密钥无线生成三种场景下分别提出了更安全的改进算法，给出完整GNY逻辑证明过程，表明算法安全可行性，同时在满足RFID系统低成本应用的条件下弥补了原算法在标签匿名性、重放攻击、密钥伪造攻击三个安全方面的不足。

# 参考文献：

[1] Shen J,Tan H, Zhang Y,et al.A new lightweight RFID grouping authentication protocol for multiple tags in mobile environment [J]. Multimedia Tools& Applications,2017:1-23.   
[2]王金茹．基于部分假名ID的RFID系统密钥无线生成算法[J].计算机 工程与应用,2018,54(1):128-132.(Wang Jinru.Wireless key generation algorithm for RFID system based on partial pseudonym ID[J].Computer Engineering and Applications,2018,54 (1): 128-132)   
[3] Chen H,Wang Z, Xia F,et al.Efciently and Completely Identifying Missing Key Tags for Anonymous RFID Systems [J].IEEE Internet of Things Journal, 2017,PP (99): 1-1.   
[4]张兵，秦志光，万国根．基于PKI和CPK的RFID系统混合密钥管理机 制研究[J]．电子科技大学学报,2015,44(3):415-421.(Zhang Bing Qin Zhiguang Wan Guogen. Study on Hybrid Key Management Mechanisms of RFID System Based on PKIand CPK[J].Journal of University of Electronic Science and Technology of China,2015,44(3): 415-421.)   
[5]鲁力RFID系统密钥无线生成[J].计算机学报,2015,38(4):822-832. (Lu Li.WirelessKey Generation for RFID Systems [J].Chinese Journal of Computers,2015,38(4): 822-832.)   
[6]简碧园，刘道微．基于位运算的 RFID 系统密钥无线生成算法[J].计 算机工程与应用,2017,53(16):98-103.(Jian Biyuan Liu Daowei.Wireless key generation algorithm for RFID system based on bit operation [J]. Computer Engineering and Applications,2017,53 (16): 98-103.)   
[7]斯进，简碧园，刘道微.RFID系统密钥无线生成算法[J].计算机工程 与设计,2017,38(10): 2686-2690.(Si Jin Jian Biyuan Liu Daowei, Wireless Key genciauon aIguiuul oI ΛrID syste [Jj. Coputel Hgmceimg anu Design,2017,38(10):2686-2690.) [8] 黄琪，凌捷，何晓桃．一种改进的基于标签部分ID的RFID密钥无线生 成算法[J].计算机科学,2017,44(1):172-175.(Huang QiLing Jie He Xiaotao. Improved RFID Key Wireless Generation Algorithm Based on Tag Part ID [J]. Computer Science,2017,44(1): 172-175.) [9]苏庆，李倩，彭家进，等．基于假名标志的加密 RFID 系统无线密钥生 成协议[J].计算机工程,2017,43(8):173-177.(Su Qing Li Qian Peng Jiajin,etal.Wireless Key Generation Protocol for Encrypted RFID System Based on Pseudonym Logo [J]. Computer Engineering,2017,43 (8): 173-   
177.） [10]张朝晖，刘悦，刘道微．基于标签 ID 的 RFID 系统密钥无线生成算法 [J].计算机应用研究,2017,34(1):261-263.(Zhang Zhaohui Liu Yue Liu Daowei.Based on tag's ID wireless key generation for RFID system algorithm [J].Application Research of Computers,2017,34(1): 261-263.) [11] Labbi Z, MaarofA,Senhadji M, et al. Hybrid Encryption Approach Using Dynamic Key Generation and Symmetric Key Algorithm for RFID Systems [C]// Proc of International Conference on Networked Systems.Springer International Publishing,2016: 244-249. [12] Dimitriou T. Key evolving RFID systems: Forward//backward privacy and ownership transfer ofRFID tags [J].Ad Hoc Networks,2016,37: 195-208. [13]汪小威，卢志翔，陆涛．基于自组合交叉位运算的超轻量移动认证协议 [J]．计算机工程与设计，2017(12):3252-3257.(Wang Xiaowei,Lu Zhixiang,Lu Tao.Ultra-lightweight mobile authentication protocol based on self-assembly crossover [J]. Computer Engineering and Design,2017 (12): 3252-3257.) [14] Garcia R，Modesti P. An IDE for the Design，Verification and Implementation of Security Protocols [Cl// Proc of IEEE International Symposium on Software Reliability Engineering.Washington DC: IEEE Computer Society,2017: 157-163 [15]朱宏峰，刘天华．隐私保护安全协议研究[M].北京：科学出版社,   
2015.(Zhu Hongfeng,Liu Tianhua.Research on privacy protection security protocol [M]. Beijing: Science Press,2015.)