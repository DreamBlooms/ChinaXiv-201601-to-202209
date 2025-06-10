# 物联网中大规模RFID标签盘存方法研究

陈毅红，王锦，贺春林，何嘉林(西华师范大学 物联网感知与分布处理研究所，四川 南充 637002)

摘要：面向物联网应用，对大规模RFID标签盘存方法进行分析研究。首先介绍RFID系统基本原理，特别是大规模RFID 标签盘存方法，分析标签盘存中所包括的移动标签识别、丢失标签监测和未识别标签监测问题；其次，从现实信道环境角度考虑，分别着重综述标签盘存方法研究现状，包括对移动标签识别方法、丢失标签监测方法、未识别标签监测方法进行对比分析，并指出本领域存在主要问题及未来研究给出建议。

关键词：射频识别；移动标签；丢失标签；未识别标签；监测 中图分类号：TN915.05 doi:10.3969/j.issn.1001-3695.2017.12.0861

# Large scale RFID tag inventory method in Internet of things

Chen Yihong,Wangjin, He Chunlin,He Jialin (IoTPerception &Distribution Processing Institute,China West Normal University,Nanchong Sichuan 63702,China)

Abstract: Considering theapplicationofthe Internetofthings,the large-scaleRFIDtags inventoryproblemare analyzedand studied.Firstly,thebasicprincipleofRFIDsystem includingtheproblemoftaginventoryisintroduced.Secondly,themobile tagrecognition,monitoringoflosstagsandunknowntagsare analyzedintheinventory problem.Then,fromthe perspectiveof the real wireless channel environmentand comparativeanalysis,this article focuses on the currntresearch statusof the tag inventoryproblem,includingthe mobiletagrecognition method,te monitoringmethodofthemissing tags,andthe monitoring method of the unknown tags.The main problems in this field and the future research are given.

Key words: RFID; mobile tag; loss tag; unrecognized tag; monitoring

# 0 引言

物联网作为新一代信息技术在众多领域得到日益广泛的应用，包括食品溯源、智能物流、智能交通、生产线管理和轨道交通[等，由此促进了社会发展和经济转型升级。近年来，为了进一步促进物联网技术发展与应用，国家出台了一系列政策措施来加快物联网及相关技术研究和开发。物联网系统由传感层、网络层和应用层组成，传感层技术是它的基础，而射频识别(radio frequency identification,RFID)则是主要的传感层技术。RFID是一种应用领域广泛的自动识别技术。RFID系统由阅读器和众多标签构成，标签存储物体相关数据。阅读器通过无线信号获取标签中数据来自动识别该物体，然后通过网络实现这些识别物体联接来构建起物联网应用系统。

RFID系统由阅读器（reader，或称为盘存器inventory）和众多标签（tags）组成，实际系统还包括标签ID数据库服务器（serverwith tagIDdatabase)，如图1所示。阅读器通过无线信道在非视线范围内一次远距离扫描识别多个标签，故RFID 具有其他自动识别技术不可比拟优势，目前应用于各个行业，如供应链管理[1]和仓库管理[2'3]等。RFID已成为国内外研究热点。在RFID系统中，上述标签碰撞问题是RFID的基础性问题，国内外学者对该问题进行了多年研究，并不断取得新进展[4-6]。然而，随着RFID日益广泛应用，新应用模式不断出现[7-8]，其中大规模RFID标签盘存模式具有广泛应用代表性。

RFID 标签盘存主要包括标签出入库和清点操作，如图1所示。在仓库（Warehouse）出入口处（Entrance）阅读器通过移动标签识别协议读取新到标签（unKnownTag）ID，并存于数据库（TagIDDatabase），这些标签变为已知标签（Known Tag）。当仓库中标签（KnownTag）出库时，在出入口处阅读器也通过移动标签识别协议读取离开标签ID，然后在数据库中删除之，这些标签又变为unKnown。阅读器清点标签包括发现丢失标签（MissingTag）和未知标签（UnknownTag)，前者可能因盗窃等原因产生，后者可因标签误入仓库或阅读器错过对新到标签识别等缘故而出现，阅读器可分别通过丢失标签监测方法以及未知标签监测方法来发现。

![](images/8078f828da90d76a4c6d7d1ec1dfddc6a4cadd803465d2edb786a85810ee7d65.jpg)  
图1大规模RFID标签盘存系统

# 1 标签盘存问题

# 1.1移动标签识别

标签入库和出库过程中，如果阅读器不能及时地识别到达或离开标签，导致标签漏读，ID数据库无法真实反映仓库标签存在，故研究高识别率的移动标签识别协议非常重要。然而，现实信道中因干扰和噪声引起数据包接收失败，还存在误码和捕获效应问题，以及移动标签出入库时在阅读器区域内识别时限要求，这些因素都会影响入库和出库时的标签识别率。这就带来了问题：面对现实信道中数据包接收失败、误码和捕获效应问题，研究高识别率的移动标签识别协议是标签盘存方法研究的基础与关键。

# 1.2丢失标签监测

对于已知标签ID，如果阅读器未收到该标签响应，则判断其丢失。包括检测标签丢失和识别丢失标签两种方式，前者以一定准确性检测到标签丢失事件，后者目的在于发现具体丢失标签。在实际应用中两者相互结合，即前者检测到丢失事件后，再通过后者来确认，这样可提高标签丢失发现能力与效率。然而，阅读器如果误将未丢失标签当成丢失标签，导致假阴性问题。反之，如未发现丢失标签，就产生假阳性问题。在标签丢失识别与检测期间，如正常标签出库时，来不及更新ID数据库，会发生标签丢失误报，故最小化标签丢失识别与检测时间非常重要。不可靠信道中干扰会引起阅读器接收标签响应数据包接收失败，会误报标签丢失，产生假阴性问题。当标签丢失后，本应没有响应，但阅读器可能将不可靠信道中噪声当成丢失标签短响应，也会误报标签存在，引起假阳性问题产生。

# 1.3未知标签监测

阅读器需用标签短响应和帧前向量来判别未识别标签，包括检测未知标签和识别未知标签两种方式，前者以一定准确性检测到未知标签事件，后者目的在于发现具体未知标签。在实际应用中两者相互结合，即前者检测到未知标签事件后，再通过后者来确认，这样可提高未知标签发现能力与效率。然而在现实信道环境中噪声与短响应间混淆和误码传送帧前向量，引起未识别标签的判别机制失效：阅读器如果误将干扰信号作为标签短响应，导致假阳性问题；反之，如未知标签响应丢失，就产生假阴性问题。。

# 2 移动标签识别方法

# 2.1移动标签识别策略

a)标签移动策略。识别协议方法支持标签移动包括两类，即以传送带为平台的恒速定密度标签沿固定线路移动类和自由移动的普通类。基于传送带的标签识别协议无须事先知道和控制标签数分布，所要解决的问题是如何调整传送带速度以获得更高的移动标签识别率。虽然这些协议研究了移动标签识别，但没有研究不受控制、自由移动的普通类，显然，支持传送带的标签识别协议无法应用于普通类标签移动环境，而随着物联网RFID应用发展，这种带有普遍性的移动环境应用正越来越多。

b)识别机制策略。识别协议方法所采用基本识别机制分为两类，即TREE和DFSA机制。基于TREE的移动标签识别协议中，ABS协议和PRB协议均对BS协议进行改进以支持标签到达和离开，而QSA协议则修改QT协议来识别移动标签，但BS和QT协议标签识别时延较长，时间效率较低，BS和QT分别约为 $40 \%$ 和 $41 \%$ 。由于DFSA机制更容易支持标签到达时选择帧时隙参与识别，绝大部分移动标签识别协议采用了DFSA机制，分析现有移动标签识别协议所采用DFSA机制后发现，在移动标签识别过程中，存在较多空闲时隙和碰撞时隙，平均系统识别效率约仅为 $3 6 . 8 \%$ ，极少部分协议采用不相等时隙时长后，时间效率提高后才达到 $70 \%$ 。

c)目标性能策略。从识别目标性能看，大部分协议以移动标签识别率为目标，少部分协议以识别效率和吞吐率为目标。其实这些目标性能本质上是一致的，即识别效率越高或吞吐率越高，则识别率越高。然而识别率是移动标签识别关键指标，在协议设计时，直接将识别率作为目标，更容易获得高的识别率。

d)识别顺序策略。标签移动环境中，科学合理安排标签识别顺序，有利于降低标签漏读率。现有协议识别顺序包括随机识别和分组识别，其中分组方式有按到达时间顺序分组、按标签类型的优先权分组、按载止期限分组。随机识别方式未按到达时间先后次序，容易造成标签漏读，而各种分组识别均考虑了标签到达先后次序，但是以组为单位，粒度较大，会造成后到标签先识别而出现标签漏读现象。

e)现实无线信道环境中存在着数据包接收失败和捕获效应现象。

# 2.2移动标签识别协议综合分析

基于上面移动标签识别策略，本文分别从移动类型、识别机制、目标性能、识别顺序、数据包接收失败和捕获效应分析等角度对主要移动标签识别协议(方法)进行综合分析比较，表1

列出了分析结果。

表1国内外文献中移动标签识别协议  

<html><body><table><tr><td>协议</td><td>移动类型</td><td>识别机制</td><td>目标性能</td><td>识别顺序</td><td>接收失败</td><td>捕获效应</td></tr><tr><td>m-ASAp[9]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr><tr><td>ABS[10]</td><td>普通</td><td>TREE</td><td>时间</td><td>随机</td><td>未分析</td><td>未分析</td></tr><tr><td>m-AFSA[11]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr><tr><td>PRB[12]</td><td>普通</td><td>TREE</td><td>时间</td><td>随机</td><td>未分析</td><td>未分析</td></tr><tr><td>XIELEI[13]</td><td>传送带</td><td>DFSA</td><td>吞吐率</td><td>时间分组</td><td>已分析</td><td>未分析</td></tr><tr><td>CU/DM[14]</td><td>普通</td><td>DFSA</td><td>识别率</td><td>随机</td><td>未分析</td><td>未分析</td></tr><tr><td>DBDFSA[15]</td><td>普通</td><td>DFSA</td><td>吞叶率</td><td>随机</td><td>未分析</td><td>未分析</td></tr><tr><td>CDFSA[16]</td><td>普通</td><td>DFSA</td><td>识别效率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr><tr><td>PrIME[17]</td><td>普通</td><td>DFSA</td><td>识别率</td><td>分类优先权</td><td>未分析</td><td>未分析</td></tr><tr><td>IC1G2MRS[18]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr><tr><td>GBDFSA[19]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr><tr><td>QSA[20]</td><td>普通</td><td>TREE</td><td>识别效率</td><td>随机</td><td>未分析</td><td>未分析</td></tr><tr><td>SAC[21]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>截止期限分组</td><td>未分析</td><td>未分析</td></tr><tr><td>AMMT[22]</td><td>传送带</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>已分析</td><td>未分析</td></tr><tr><td>G2-CDFSA[23]</td><td>普通</td><td>DFSA</td><td>识别率</td><td>时间分组</td><td>未分析</td><td>未分析</td></tr></table></body></html>

# 2.3存在的问题与未来研究方向

由移动标签识别协议综合分析可知，现有移动标签识别协议机制未同时考虑数据包接收失败、误码和捕获效应因素，而且它们的分析模型中没有纳入这些因素，故优化后所得参数不能同时反映现实信道这些制约因素，难以获得真实有效最优识别率。现有协议的所采用的基本识别机制存在较多空闲时隙和碰撞时隙，识别效率约为 $3 6 . 8 \%$ ，同时这些协议主要按随机或粗粒度的分组顺序识别移动标签，会导致漏读问题，明显地影响着移动标签识别率。

未来研究有着广泛应用的支持自由移动型标签识别，考虑现实信道环境中客观存在的数据包接收失败和捕获效应现象，设计研究高效率DFSA机制，并且该机制基于标签到达先后采用细粒度来安排标签识别顺序以进一步减少标签漏读率，将是本领域研究未来主要方向。

# 3 丢失标签监测方法

# 3.1丢失标签监测策略

a)丢失监测策略。检测标签丢失协议是概率性协议，能够较快发现标签丢失事件，而识别丢失标签协议是获知所有丢失标签ID的确定性协议，时间开销较大，两种协议各有自己优缺点，能够互补。

b)标签范围策略。参与检测与识别的未知标签数用于衡量整个系统能量，全部标签方式适用于应用广泛的低成本被动标签，而通过采样和分类则让部分标签参与，适用于特定用途的高成本主动标签。

c)目标性能策略。部分协议考虑主动标签应用而将能耗与时间作为目标性能，其他协议仅将时间作为目标性能，前者需要在两个指标间权衡，而后者受到制约因素相对更少，能够将时间开销减少到更低程度。

d)帧前向量策略。阅读器通过包含已知标签信号的帧前向量，让其区域内未知标签传送其ID 或短响应用于阅读器识别或检测未知标签，因此帧前向量的可靠传送到标签是关键，而目前所有协议均没有考虑到现实信道环境中数据包接收失败问题。

e)响应长度策略。当阅读器逐个发出查询命令时，标签可以将其ID作为响应，阅读器将收到ID与ID库比较可立即知道是否为未知标签。

f)现实无线信道环境中存在着数据包接收失败和捕获效应现象。

# 3.2丢失标签监测协议综合分析

基于上面丢失标签监测策略，本文分别从监测方式、参与标签范围、目标性能、帧前向量、响应长度、数据包接收失败和捕获效应分析等角度对主要丢失标签监测协议(方法)进行综合分析比较，表2列出了分析结果。

表2国内外文献中丢失标签监测协议  

<html><body><table><tr><td>协议</td><td>监测方式标签范围</td><td></td><td>目标性能</td><td>帧前向量</td><td>响应长度</td><td>接收失败捕获效应</td><td></td></tr><tr><td>TRP[24]</td><td>检测</td><td>全部</td><td>时间</td><td>无</td><td>短响应</td><td>未分析</td><td>未分析</td></tr><tr><td>TPp[25]</td><td>识别</td><td>全部</td><td>时间</td><td>无</td><td></td><td>短响应+轮询定性分析未分析</td><td></td></tr><tr><td>TPP/TR[25]</td><td>识别</td><td>全部</td><td>时间</td><td>无</td><td></td><td>短响应+轮询定性分析未分析</td><td></td></tr><tr><td>TPP/CSTR[25]</td><td>识别</td><td>全部</td><td>时间</td><td>无</td><td></td><td>短响应+轮询定性分析未分析</td><td></td></tr><tr><td>THP[25]</td><td>识别</td><td>全部</td><td>时间</td><td>有</td><td>短响应</td><td>定性分析</td><td>未分析</td></tr><tr><td>EMD[26]</td><td>检测</td><td>全部</td><td>时间+能耗</td><td>无</td><td>短响应</td><td>未分析</td><td>未分析</td></tr><tr><td>IIP[27]</td><td>识别</td><td>采样</td><td>时间</td><td>有</td><td>短响应</td><td>未分析</td><td>未分析</td></tr><tr><td>MSMD[28]</td><td>检测</td><td>采样</td><td>时间+能耗</td><td>有</td><td>短响应</td><td>定性分析</td><td>未分析</td></tr><tr><td>MMT[29]</td><td>识别</td><td>全部</td><td>时间</td><td>有</td><td>短响应</td><td>定性分析</td><td>未分析</td></tr><tr><td>ECMTI[30]</td><td>识别</td><td>分类</td><td>时间</td><td>有</td><td>短响应</td><td>定性分析</td><td>未分析</td></tr><tr><td>SFMT[31]</td><td>识别</td><td>全部</td><td>时间</td><td>有</td><td>短响应</td><td>未分析</td><td>未分析</td></tr><tr><td>MTIP[32]</td><td>检测</td><td>全部</td><td>时间</td><td>无</td><td>短响应</td><td>定性分析</td><td>未分析</td></tr><tr><td>BMD[33]</td><td>检测</td><td>全部</td><td>时间</td><td>无</td><td>短响应</td><td>未分析</td><td>未分析</td></tr></table></body></html>

# 3.3存在的问题和未来研究方向

丢失标签监测协议综合分析可知，部分协议对不可靠信道引起的数据包接收失败影响进行了定性分析，但协议机制没有考虑接收失败，性能分析模型也没有纳入接收失败因素，这会导致标签丢失判别机制失效，无法保证检测与识别准确性，也难以获得真实有效的最优协议参数和性能。现有协议均采用短响应方式判别丢失标签，然而，当阅读器与标签间距离较远时，短响应较易与噪声混淆而引起假阳性问题和假阴性问题，而使标签丢失判别机制面临失效风险。

未来本领域应当考虑现实信道环境中客观存在的数据包接收失败和捕获效应现象，设计能够抗噪声的带多位校验长响应来解决假阳性问题和假阴性问题。同时，现有协议仅在期望单标签时隙来判别丢失标签，多标签时隙被浪费掉，还需研究提高时隙利用率的协议机制。设计具有抗噪声能力的短响应，尽量少引入轮询而多采用所设计的短响应，避免在阅读器和标签间传递帧前向量，并且利用碰撞时隙来增加标签丢失检测与识别的机会，将捕获效应与接收失败因素一起纳入协议分析模型，以获得有效的协议参数和最优识别性能。

# 4 未知标签监测方法

# 4.1未知标签监测策略

a)未知监测策略。检测未知标签协议是概率性协议，能够较快发现未知标签事件，而识别未知标签协议是获知所有未知标签ID的确定性协议，时间开销较大，两种协议各有自己优缺点，能够互补。

b)标签范围策略。参与检测与识别的标签数用于衡量整个系统能量，全部标签方式适用于应用广泛的低成本被动标签，而通过采样和分类则让部分标签参与，适用于特定用途的高成本主动标签。

c目标性能策略。部分协议考虑主动标签应用而将能耗与时间作为目标性能，其他协议仅将时间作为目标性能，前者需要在两个指标间权衡，而后者受到制约因素相对更少，能够将时间开销减少到更低程度。

d)帧前向量策略。阅读器通过包含已知标签信号的帧前向量，让其区域内未知标签传送其ID或短响应用于阅读器识别或检测未知标签，因此帧前向量的可靠传送到标签是关键。

e)标签响应策略。当阅读器发现查询命令后，标签可以其ID作为响应，也可先以短响应给阅读器，阅读器收到短响应后，标签根据阅读器命令情况再传送其ID，前者主要用于未知标签识别协议，时间和能耗较大，后面如果只有短响应，则能耗较小，适用于未知标签检测协议。

f)现实无线信道环境中存在着数据包接收失败。

# 4.2未知标签监测协议综合分析

基于上面未知标签监测策略，本文分别从监测方式、目标性能、帧前向量、标签响应、数据包接收失败等角度对主要未知标签监测协议(方法)进行综合分析比较，表3列出了分析结果。

表3国内外文献中未知标签监测协议  

<html><body><table><tr><td>协议</td><td>监测方式</td><td>目标性能</td><td>帧前向量</td><td>标签响应</td><td>接收失败</td></tr><tr><td>CU[34]</td><td>识别</td><td>识别率</td><td>无</td><td>ID 响应+短响应</td><td>未分析</td></tr><tr><td>BUIP[35]</td><td>识别</td><td>识别率</td><td>有</td><td>ID 响应+短响应</td><td>未分析</td></tr><tr><td>BUIP-CE[35]</td><td>识别</td><td>识别率</td><td>有</td><td>ID 响应+短响应</td><td>未分析</td></tr><tr><td>FUT[36]</td><td>识别</td><td>识别率</td><td>有</td><td>ID响应</td><td>未分析</td></tr><tr><td>IFUTI[36]</td><td>识别</td><td>速度</td><td>有</td><td>ID响应</td><td>未分析</td></tr><tr><td>B-UTD[37]</td><td>检测</td><td>准确率</td><td>有</td><td>短响应</td><td>未分析</td></tr><tr><td>S-UTD[37]</td><td>检测</td><td>准确率</td><td>有</td><td>短响应</td><td>未分析</td></tr></table></body></html>

# 4.3存在的问题和未来研究方向

综合分析未知标签监测协议可知，现实信道环境的误码传送帧前向量问题，会引起已知标签干扰未知标签识别和漏检未知标签，从而降低未知标签的识别效率和降低未知标签检测概率，而目前采用帧前向量的协议均未处理分析误码传送向量问题。短响应与现实信道噪声间的混淆导致协议的判别机制失效。未知标签检测协议机制没有考虑误码传送帧前向量问题和未知标签响应的阅读器数据包接收失败问题，而且协议分析模型没有纳入误码率和接收失败率，因此不能得到现实信道环境下协议真实有效的最优参数，也难以获得真实有效的协议最优性能。现有协议均基于单标签时隙对未知标签和已知标签进行判别，其他时隙被浪费掉，而致协议效率低下。在未来研究中应当现实信道中存在的数据包接收失败问题，设计好的协议机制以克服这些问题所导致的假阳性问题和假阴性问题，并在协议分析的数学模型中纳入随机概率因素。

# 5 结束语

通过对三种标签盘存方法所采用策略分析，再基于策略对现有在标签盘存方法进行详细分析对比可以发现：a)现有移动标签识别协议的基本识别机制效率较低，而且基于随机或粗粒度的分组顺序识别移动标签，这些缺限会降低移动标签识别率;b)现有丢失标签监测协议和未识别标签监测协议很少考虑在无线信道中数据接收丢失和捕获效应现象，所导致的问题是判别机制失效，难以保证检测与识别准确性;c)没有纳入现实信道环境的数据包丢失、误码和捕获效应因素到三种标签盘存协议分析模型，难以获得现实信道环境下真实有效的协议参数，协议性能受现实信道因素影响而不能工作于最优性能状态。

未来本领域研究工作应当考虑现实信道环境存在的数据包接收失败、误码和捕获效应因素来设计可靠性高的标签识别和监测协议机制，并基于这些因素建立数学分析模型得到协议最优参数，研究出具有鲁棒性好、识别率高、速度快和准确率高的大规模RFID标签盘存方法。

# 参考文献：

[1]吴敏．基于RFID技术在轨道交通中的应用[J]．自动化博览,2017,14 (4): 100-103.   
[2]Zheng Yuanqing; Li Mo.Towards more efficient cardinality estimation for large-scale RFID systems [J].IEEE Transs on Networking,2014,21 (6): 7083-7091.   
[3]Zheng Y,Li M.Fast tag searching protocol for large-scale RFID systems [C]//Proc of IEEE International Conference Network Protocols.2011:363- 372.   
[4]Wu Haifeng,Zeng Yu,Feng Jihua,et al. Binary tree slotted ALOHA for passive RFID tag anticollision [J].IEEE Trans on Parallel and Distributed Systems,2013,24(1):19-31.   
[5]张小红，张留洋.RFID防碰撞时隙应变协处理算法研究[J]．电子学报, 2014,42 (6): 1139-1146.   
[6]Chen Yihong,Feng Quanyuan,Ma Zeng,et al.Multiple-bits-slot reservation alohaprotocol for tag identification [J].IEEE Trans on Consumer Electronics,2013,59(1): 93-100.   
[7] Yang Zhipeng，Ning Ting，Wu Hongyi. Distributed data query in intermittently connected passive RFID networks [J]. IEEE Trans on Parallel and Distributed Systems,2013,24 (10): 1972-1982.   
[8]Xie Lei,Han Hao,Li Qun,etal.Eficientprotocols forcollecting histograms in large-scale RFID systems [J].IEEE Trans on Parallel and Distributed Systems,doi:10.1109//TPDS.2014.2357021.   
[9]Khandelwal G, Yener A,Lee K,et al.A MAC protocol for dense and time constrained RFID systems [C]// Proc of IEEE International Conference on Communications. 2006: 4028-4033.   
[10] Myung J，Lee W， Srivastava J,et al. Tag-spliting:adaptive collsion arbitration protocols for RFID tag identification [J]. IEEE Trans on Parallel and Distributed Systems,2007,18(6):763-775.   
[11] Sarangan V,Devarapalli MR,Radhakrishnan S.A framework for fast RFID tag reading in static and mobile environments [J]. Computer Networks,2008, 52: 1058-1073.   
[12] Lai Y,Lin C.Twoblocking algorithms on adaptive binaryspliting: Single and pair resolutions forRFID tag identification[J].IEEE//ACM Trans on Networking,2009,17(3): 962-975.   
[13] Xie Lei,Sheng Bo,Tan CC,et al.Eficient tag identification in mobile RFID systems [C]//Proc of IEEE INFOCOM.2010.   
[14] Sheng Bo,Li Qun,Mao Weizhen. Efficient continuous scanning in RFID systems [C]//Proc of IEEE INFOCOM. 2010.   
[15] Lee C C,Lin Shengyue.Adouble blocking dynamic framed sloted ALOHA anti-collision method for mobile RFID systems [C]// Proc of International Conference on Genetic and Evolutionary Computing.2012: 581-584   
[16]陈毅红；冯全源．物联网中标签持续到达的 RFID 防碰撞算法[J].计 算机集成制造系统,2012,18(9):2076-2081.   
[17]Benedeti D, MaselliG,Petrioli C.Fastidentificationof mobile RID tags [Cl// Proc of IEEE International Conference on Mobile Ad hoc and Sensor Systems. 2012: 65-74.   
[18] Li Xiaowu,Feng Quanyuan.An improved EPC class 1 gen 2 protocol with FCFS feature in the mobile RFID systems [J].International Journal of Computers Comunications & Control,2013,8(6):854-862.   
[19] Li Xiaowu, Feng Quanyuan. Grouping based dynamic framed slotted ALOHA for tag anti-colision protocol in the mobile RFID systems [J]. Applied Mathematics& Information Sciences,2013,7(2L):655-659.   
[20] Gao Jianliang，Wang Jianxin,He Jianbiao. QSA: query spliting-based anticollision for mobile RFID-based Internet-of-things[J].International Journal of Distributed Sensor Networks, 2013.   
[21] Zhu Weiping,Cao Jiannong, Chan HC B,et al. Mobile RFID with a high identification rate [J].IEEE Trans on Computers,2014,63(7): 1778-1792.   
[22]Park CW,AhnJH,Lee TJ.Aprotocol minimizing missing tags ina moving RFID tag environment [J]. International Journal of Information and Electronics Engineering,2014,4(3): 244-248.   
[23] Chen Yihong;Feng Quanyuan.An efficient anti-collision algorithm for the EPC global class-1 generation-2 systemunder the dynamic environment[J]. KSII Transon Internet and Information Systems,2014,8(11):3997-4015.   
[24] Li Tao,Chen Shigang,Ling Yibei.Efficient protocols for identifying the missing tags ina largeRFID system[J].IEEE Transon Networking,2013, 21 (6): 1974-1987.   
[25]Tan CC,Sheng Bo,Li Qun.Efcient techniques for monitoring missing RFID tags [J]. IEEE Trans on WirelessCommunications,2011,9(6): 1882- 1889.   
[26]Li Tao,Chen Shigang,Ling Yibei. Identifying the missing tags in a large RFID system[C]// Proc of the 11th ACM International Symposium on Mobile Ad hoc Networking and Computing. New York: ACM Press, 2010: 1-10.   
[27]Luo Wen, Chen Shigang,Li Tao,et al.Efcient missing tag detection in RFID systems [C]//Proc of IEEE INFOCOM.2010: 356-360.   
[28] Luo Wen,Chen Shigang, QiaoYan,etal. Missing-tag detectionand energy time tradeoffin large-scale RFID systems with unreliablechannels [J].IEEE Trans on Networking,2014,22 (4): 1079-1091.   
[29]Liu Xiulong,Li Keqiu, Min Geyong,et al. A multiple hashing approach to complete identification of missing RFID tags [J].IEEE Trans on Communications,2014,62 (3): 1046-1057.   
[30] Zhao Jumin,Li Wenting,Li Deng'ao.Identifying the missing tags in categorized RFID systems [J]. International Journal of Distributed Sensor Networks,2014,http://dx.doi.org/10.1155/2014/582951.   
[31]Liu Xiulong,Li Keqiu,Min Geyong,et al. Completely pinpointing the missingRFID tagsina time-efficientway[J].IEEE TransonComputers, 2015, 64 (1): 87-96.   
[32] Zhang Rui,Liu Yunzhong,Zhang Yanchao,et al.Fast identification of the missing tags in a large RFID system [C]// Proc of IEEE Communications Society Conference on Sensor,Mesh and Ad hoc Communications and Networks. 2011: 278-286.   
[33]张士庚，刘光亮，刘璇，等．大规模 RFID 系统中一种能量有效的丢失 标签快速检测算法[J].计算机学报,2014,37(2):434-444.   
[34] Sheng Bo,Li Qun,Mao Weizhen.Eficient continuous scanning inRFID systems [C]/ Proc of IEEE INFOCOM. 2010.   
[35]Liu Xuan,Zhang Shigeng，Bu,Kai.Completeandfast unknown tag identification in large RFID systems [C]//Proc of IEEE International Conference on Mobile Ad-hoc and Sensor Systems.2012:47-55.   
[36] Liu Xiulong,Li Keqiu,Min Geyong.Efficient unknown tagidentification protocols in large-scaleRFID systems [J].IEEE Transon Parallel and Distributed Systems.2014,25 (12):3145-3155.   
[37]Liu Xiulong, Qi Heng,Li Keqiu,etal.Time-and energy-eficientdetection ofunknown tagsinlarge-scaleRFIDsystems[C]//Procof IEEE International Conference on Mobile Ad-hoc and Sensor Systems.2013: 95- 103.