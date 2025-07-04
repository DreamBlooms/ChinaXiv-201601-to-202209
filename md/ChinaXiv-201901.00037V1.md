# 面向EPCGen2标准的RFID标签分组多位隙并行识别协议

杨新爱'，段富²†

(1．山西工程职业技术学院 计算机工程系，太原 0300092．太原理工大学 信息与计算机学院，太原 030024)

摘要：在分析EPC global UHFclasslgeneration2协议和基于DFSA 协议的高速标签识别算法的基础上，采用位隙FSA 协议标签响应标志位隙的设置方法，通过在标签上设置一个组位隙响应标志字，提出了一种EPCGen2 标准下的RFID 标签分组多位隙并行识别协议GMBPIP，设计了一条新的分组查询命令和基于DFSA的多组标签并行识别协议流程，从理论上了分析GMBPIP 协议的性能，并使用EPCGen2 标准协议时间参数进行了仿真实验。结果表明，GMBPIP 协议在不增加标签太多计算负担的情况下，能够在EPCGen2标准下有效降低了时隙空闲率和冲突率，提高了标签的识别率、时隙利用率；平均识别率不仅突破了帧时隙ALOHA协议最高 $3 6 . 8 \%$ 的瓶颈，而且高于目前文献所述同类算法的性能指标，达到了 $7 0 . 9 5 \% { \sim } 8 1 . 6 1 \%$ 。GMBPIP可以作为低成本RFID系统高速识别大量被动标签的支撑协议。

关键词：EPCGen2标准；位隙帧时隙ALOHA；被动式标签；并行识别协议 中图分类号：TP393.04 doi:10.3969/j.issn.1001-3695.2018.10.0642

RFID tag group multiple bit-slot parallel identification protocol for EPC GEN2 standard

Yang Xin'ai',Duan $\mathrm { F u } ^ { 2 \dag }$ （204 (1.Dept.ofComputer，Shanxi Engineering Vocational College,Taiyuan O30o09,China;2.Collgeof Information& Computer,Taiyuan University of Technology,Taiyuan O3o024,China)

Abstract:Absrtact:Basedon the analysis of the EPCglobal UHFclass1 generation2 protocol and the high speed tag identificationalgorithm forFSAprotocol，thispaperproposedagroup multiple bit-slotparallelidentification protocol(GMBPIP)for RFID passive tags under EPC Gen2 standard,and designed GMBPIP communication processing flow based on DFSA. GMBPIP set up group bit-slot word onatag bythe methodof setting multiple bit-slotfor tag response in Bit-SlotFSA protocol,and designed anew groupquerycommand.It analyzed theoretically the performanceof GMBPIP protocol,andcarredoutthe simulation experiment using the time parameter ofEPCGen2 standard protocol.Theresults show that without adding too much computational burden to the tag for EPC GEN2 standard,the GMBPIP protocolcan efectivelyreduce the time slotidlerateandcollsionrate,improve thetag identificationrateandthetime slotutilization ratio.Theaverage identification rate notonly breaks through the botteneck of the frame time slot ALOHA protocol upto $3 6 . 8 \%$ ,but also is higher than the performance index of the same kind of algorithm,reaching $7 0 . 9 5 \%$ $8 1 . 6 1 \%$ . GMBPIP can be used as a support protocol for low cost RFID system to identifya large number of passve tags at high speed.

Key Words: EPC GEN2 standard; bit-slot FSA; passive tags; parallel identification protocol

# 0 引言

近年来，无线射频识别技术(radio frequency identification.RFID)在供应链管理、仓库管理和访问控制等领域应用广泛。受RFID多址问题的限制，对此类应用的挑战之一是要高效率地读取大量标志物品对象的RFID 标签。为了解决这一问题，识别协议在控制多址访问方面起着重要作用，提高了识别大量标签的效率,如目前在RFID系统中广泛使用的动态帧时隙(dynamic frame slottedaloha，DFSA)识别被动式标签算法，就是基于 EPC Gen2（EPCglobal UHF class1 generation 2）标准协议[设计的。

在EPCGen2中，阅读器和标签之间的通信过程以帧时隙（frameslottedaloha，FSA)方式组织，通信过程被划分为若干帧，每帧被进一步划分时隙。阅读器以帧为周期对其覆盖范围内的标签按时隙盘存，每个时隙盘存的结果为没有标签响应的空闲时隙,仅一个标签签响应的成功时隙；或多个标签响应的冲突时隙。理论分析表明，FSA算法在帧长 $L$ 与未被识别的标签数相等时，信道的使用效率最高，标签的识别率，冲突率和空闲率分别为 $3 6 . 8 \%$ 、 $2 6 . 4 \%$ 和 $3 6 . 8 \%$ ，每个冲突时隙平均有2.39个标签。因此，未被识别标签的估算及由此确定帧长的方法成为达到最高信道的使用效率的关键。估算的方法除了比较经典的最小值方法、泊松分布方法、冲突因子方法外，也出现了适用于标签数量较大的采样和复合估算方法：文献[2]提出的基于采样的线性标签数估算方法；文献[3]提出了时隙结果采样统计的分情况标签数估算方法；文献[4]提出了一种时隙数选择方法能够基于冲突时隙的个数动态的调整当前帧长；文献[5]中总结并列出不同帧长时理想的标签数范围，通过查表的方式动态调整当前帧长；但由于估算误差及EPCGen2通过 $\boldsymbol { \mathcal { Q } }$ 值 $Q \in [ 0 \ 1 5 ]$ ，帧长 $L = 2 ^ { Q } ,$ 确定帧长的方法，标签的识别率在 $3 5 \%$ 左右，尤其在未识别标签数量较少和较大时，情况变得更差。针对这一问题，文献[6,7]提出了一种改进的分组DFSA算法，以354（对应帧长256，$\scriptstyle { \mathrm { Q } = 8 }$ ）作为标签数分组的门限值，将大量标签分组，然后按组依次识别；并当本组未识别标签较少时（尾标签）合并到下一组一起识别。

为了进一步提高RFID系统的大量被动标签的识别率，减少冲突率和空闲率，研究者提出了多种高速标签识别算法。该类算法充分利用了非成功时隙，使识别效率达到 $45 \%$ 以上。文献[8]中标签生成两个随机数并划分优先级，将部分空闲时隙转换为成功时隙而将识别效率提高到 $4 5 . 3 \%$ 。文献[9]中，通过将3级随机数部署在单个标签上，将部分空闲和冲突时隙转换为成功时隙，识别率达到 $6 9 . 3 5 \%$ 。文献［10］中提出了一种位隙分组帧时隙算法。该算法把一定长度的位隙标志位（设为Ls位）置于标签ID的后面，标签响应阅读器时随机选取位隙标志位置1，其余全为0；阅读器解析出置1位隙标志位的位置，然后从高到低依次把位置信息回传给标签，冲突时隙内的标签对该位置信息进行匹配，匹配成功的标签再向阅读器应答。理论上一个冲突时隙，最多可识别Ls个冲突的标签。文献［11］在分析文献［10］位隙分组的基础上，提出了分段式位隙FSA算法。该算法将位隙分为两段，在标签发生冲突时，由该时隙内发生冲突的标签先后发送前后两段位隙标志位进行再识别：若在前段位隙中成功识别该时隙内所有冲突的标签，则进入下一个时隙的标签识别；若经过前段位隙再识别后仍存在冲突标签，则继续发送后段位隙进行识别。在标签数量1万以内保持平坦，识别率达到 $6 5 \%$ 以上，且通信量最低。文献「12」结合基于分组和多级随机数标签识别算法的设计思想，将多级随机数分别部署在不同组的标签中，以DFSA算法框架为基础，提出了基于分组的多级随机数并行识别算法，按照多级随机的轮询机制轮询各组标签，并通过组间合并解决负载不均衡问题，4组并行时获得了 $70 \%$ 的识别率。文献「15」针对目前一些已有算法存在查询次数过多且识别率不高的问题进行研究，提出一种基于多处冲突位探测的标签防碰算法。上述这些算法虽然提高了标签的识别率，但实际应用时对标签的计算能力要求较高，缺乏协议支撑，需要设计复杂的逻辑电路实现。本文在EPCGen2 标准下，采用位隙FSA算法标签响应标志位隙的设置方法，通过在标签上设置一个组位隙响应标志字，提出了一种 EPCGen2 标准下的RFID 标签分组并行识别协议（multiple-group parallel identification protocol，GMBPIP),并针对不同的并行组数和每组对应的位隙数两种情况，分析了协议的性能，进行了仿真实验。

# 1 并行识别协议设计

# 1.1标签分组及组标签位隙响应标志字

在阅读器感知到其覆盖范围内的标签集合定义为T，使用文献[7]中的算法估算出 $T$ 中的标签数量 $n _ { t }$ ，参照文献[3]的分组方法，将标签集合 $T$ 分为适合帧长 $L < = 2 ^ { Q }$ · $Q \in [ 4 , \ 8 ]$ 标签数 $< = 3 5 4$ 的 $n _ { g }$ 组，得到分组标签集合 $\mathrm { G T } { = } \{ g T _ { i } \ | i \in [ 1$ $\left| n _ { g } \right| \}$ ，其中 $\Sigma | g T _ { i } | = | T | , n _ { g }$ 为 $m \in [ 4 , 1 6 ]$ 的整数倍。从GT取出前$m$ 组放入 $\mathsf { P G T } \mathop { = } \{ \mathrm { p g T } _ { \mathrm { j } } \big | \} \in [ 1 , m ] \}$ ，参照文献[10]并在每个标签上设置长度为 $m ^ { * } p$ 位的二进制组位隙响应标志字 $W _ { \mathrm { G P S } }$ ， $p \in$ [1,4]每组对应的标签响应的位隙数； $W _ { \mathrm { G P S } }$ 分为 $\mathrm { ~ m ~ }$ 段，每段 $p$ 位二进制，对应于一组标签在某个时隙的响应情况；用$W _ { \mathrm { G P S } } ( \mathrm { g b } , 1 { \cdot } \mathrm { p } )$ 表示第gb组标签在某个时隙的响应情况。第一组标签有响应时随机的从 $\mathsf { W } _ { \mathrm { G P S } } ( 1 , 1 { : } \mathsf { p } )$ 中的 $\mathsf { p }$ 位选择一位置1，第二组标签有响应时随机的从 $\mathbf { W _ { G P S } } ( 2 , 1 { \cdot } { \mathsf { p } } )$ 中的 $\mathsf { p }$ 位选择一位置 $\mathbf { \Omega } _ { 1 } , \cdots ,$ 第 $\mathbf { \nabla } m$ 组标签有响应时随机的从 $W _ { \mathrm { G P S } } ( m , 1 ; p )$ 中的 $p$ 位选择一位置1。

初始化PGT内各组内已识别标签的集合为 $\mathrm  S P G T = \{ s p g T _ { j } \$ $\vert \mathbf { j } \in [ 1 , m ] \vert = \varnothing$ ，未读标签的数目集合为 $\mathrm { U P G T = \{ u p g T _ { j } \} j \in [ 1 , }$ （204号$\mathrm { m l } \} \mathrm { = } | { \mathrm { P G T } } |$ 。

# 1.2命令定义

本文所提GMBPIP协议基于EPCGen2标准，除了使用EPCGen2协议的命令外，还需要定义分组访问控制命令C $\mathrm { \underline { { ) u e r y R e p G ( g b , g p ) , g b \in [ 1 , m ] , g b } } }$ 的二进制编码长度为 $\log _ { 2 } \mathfrak { m }$ ：$\mathrm { { g p } \in [ 1 , p ] }$ ，gp的二进制编码长度为 $\log _ { 2 } { \mathfrak { p } }$ 。阅读器通过QueryRepG对满足 $\mathrm { W _ { G P S } ( g b , \mathrm { g p } ) { = } 1 }$ 的第gb 组标签分布的进行查询，该组标签接收到QueryRepG(gb，gp)，与WGPS(gb,$\scriptstyle \mathrm { g p } ) = 1$ 匹配的标签，发送自己的EPC响应，如果没有冲突，则成功识别这个标签，否则参加下一轮标签识别。协议描述中用到的命令列于表1。

表1 GMBPIP协议的命令  
Table 1 Commands for the GMBPIP protocol   

<html><body><table><tr><td>命令</td><td>描述</td></tr><tr><td>Select</td><td>EPCGen2命令，选择一个特定的标签集 EPCGen2帧查询命令，开启一帧时隙周期查询，</td></tr><tr><td>Query(Q)</td><td>Q∈[0,15]</td></tr><tr><td>QueryAdjust</td><td>EPCGen2相对于上轮Q值调节的帧查询命令，Q 值不变或加减1，开启一帧时隙周期查询</td></tr><tr><td>QueryRep</td><td>EPCGen2时隙重复查询命令，开启下一个时隙的 查询</td></tr><tr><td>ACK</td><td>EPCGen2确认命令，对成功识别的标签EPC进行 确认</td></tr><tr><td></td><td>GMBPIP 自定义命令，对满足WGPs(gb,ps)=1的第</td></tr><tr><td></td><td>QueryRepG(gb,gp)gb 组标签进行查询，gb∈[1,m]，m∈[4,16]并行</td></tr><tr><td></td><td>组数；gp∈[1,p]，p∈[1,4]多位隙数</td></tr></table></body></html>

# 1.3协议流程设计

本文提出的GMBPIP协议是基于EPCGen2标准的，可对多组被动标签进行并行识别，具体流程描述如下。

# GMBPIP协议流程

输入： $\mathrm { P G T = \{ p g T _ { j } | j \in [ 1 , m ] \} }$ ， $Q \in [ 4 , 8 ]$ 和 $\mathrm { m } \in [ 4 , 1 6 ]$ ，每个标签上设置 $\mathrm { \Delta W _ { G P S } = 0 }$ 和gb。

输出：已识别标签的集合为 $\scriptstyle \mathrm { S P G T = \{ s p g T _ { j } \mid j \in [ 1 , \ m ] \} }$ ，未读标签的集合为 $\scriptstyle \mathrm { U P G T = \{ u p g T _ { j } \mid j \in [ 1 , m ] \} }$ 。

1阅读器向 $\mathrm { ~ m ~ }$ 组标签集 ${ \mathrm { P G T } } { = } \{ { \mathrm { p g T } } _ { \mathrm { j } } | { \mathrm { j } } { \in } [ 1 , { \mathrm { m } } ] \} /$ 广播query（Q）查询命令；

2 标签随机选择时隙，将其装入自己的槽计数器 SC;

3槽计数器SC为0的标签，按该标签所在的组号gb在 $\mathbf { W _ { G P S } }$ 相应段位，随机从p位中选一位置1，并立即启动响应并发送 $\mathbf { W _ { G P S } }$

4 阅读器检查标签的返回WGPs位隙信息。如果本时隙没有响应信号则转7；

5阅读器查看 $\mathbf { W _ { G P S } }$ 信息里有几段不为0。如果有n段不为0，则说明本时隙内有 $\mathbf { n }$ 组标签产生响应， $\mathrm { g b } = 1$

$5 . 1 \ \mathrm { g p } { = } 1$ ；如果第gb段的位隙信息为0，转(6);

5.2对第gb段的位隙信息，如果 $\mathsf { W } _ { \mathrm { G P S } }$ （gb，gp）不为0，并将该信息包含到一个分组查询命令QueryRepG(gb，gp)中。本时隙内的标签在收到该命令后，提取出该位置信息，并分别与自己的组号和WGPs相应位隙信息进行匹配。匹配成功的标签将自己的数据包返回给阅读器。阅读器检测返回的ID信息。如果没有冲突，就利用ACK命令进行确认；

5.3阅读器将 $\mathsf { W } _ { \mathrm { G P S } }$ （gb，gp）清零，如果第gb段的位隙信息不为0，gp++，转5.2;

6 阅读器将第gb段的位隙信息清零，如果WGPs 不为0，则 $^ \mathrm { g b + + }$ 然后执行5.1\~6步，直到WGPs为0；（7)

7阅读器发送QueryRep命令，查询范围内的标签接到命令后将自己的槽计数器 SC减1，然后转3，如果本时隙是最后一个时隙，结束本轮查询并转1;

8 某一轮查询中，所有时隙都是空时隙，整个查询过程结束。

在GMBPIP协议中，阅读器向 $\mathbf { m }$ 组标签广播query（Q)或者QueryAdj查询命令，各组标签则按照相应的 $\boldsymbol { Q }$ 值生成一个介于0到 $2 ^ { { \it Q } _ { - 1 } }$ 之间的随机数记为SC，如果是QueryRep则将SC减1。在一个时隙内， $\scriptstyle S C = 0$ 的所有标签向阅读器发送组位隙响应标志字WGPs；阅读器通过统计分析WGPs 每一段的置1的情况，然后对有响应的组，分别使用QueryRepG按组及位隙查询，该组标签以自己的EPC编码响应，阅读器检测是否有冲突？没有则成功识别一个标签。GMBPIP协议阅读器和各组标签之间的通信应答过程流程如图1所示。

# 2 并行识别协议分析

本文所设计的协议是一种多组标签并行识别的协议，每组标签的数量大致相同，阅读器使用相同帧时隙周期按时隙对各组标签进行查询，各组标签在同一个时隙内同时通过组位隙响应标志字WGPs响应；阅读器通过统计分析WGPs每一段的置1的情况，然后对有响应的组，分别使用QueryRepG按组及位隙查询，该组标签以自己的EPC编码响应，阅读器检测是否有冲突？没有则成功识别一个标签。

就一组标签的识别过程而言，与单组FSA协议过程基本相同，其标签的响应率 $\mathrm { \bf P _ { P l } }$ （成功率 $\mathrm { P s } _ { 1 } + .$ 冲突率 $\mathrm { \sf P } _ { \mathrm { C 1 } }$ ）和空闲率 $\mathrm { \bf P _ { E 1 } }$ 也一样。不同的是，阅读器要在每个帧时隙面向各组发组播查询命令QueryRep，以得到组位隙响应标志字WGPs,一帧需要额外增加L个 $\mathsf { W } _ { \mathrm { G P S } }$ 响应时隙。设一次处理 $\mathbf { m }$ 组标签，帧长为L，每组的位隙段长为p，则平均有 $\scriptstyle \mathbf { S } _ { \mathrm { A } } = \mathbf { m } ^ { * } \mathbf { L } ^ { * } \mathbf { P } _ { \mathrm { P l } }$ 即为WGPs的组的位隙段不为0的个数，需要增加SA个时隙使用QueryRepG分别按组查询，以最终识别一个标签。由于只对有响应的标签组进行再查询，没响应的不用再查询，这样就把空闲时隙转换为成功和冲突时隙；而标签组的响应通过p位位隙段来反映，其值由该组的响应标签随机选取相应位隙段的1位并置1来确定；由于每组的位隙段有p位，相比原来的一位，冲突时隙降低到原来的 $1 / \mathsf { p }$ ，这样又将响应时隙中部分冲突时隙转换为成功时隙；每组位隙全部没响应的概率很低。从以上分析可知，所提GMBPIP协议的识别率 $\mathbf { P s }$ 、冲突率 $\mathrm { P _ { C } }$ 和空闲率 $\mathbf { P } _ { \mathrm { E } }$ ，当 $\scriptstyle \mathrm { p = 1 }$ 按式（1）～（3）计算；当 $\mathsf { p } { \mathord { > } } 1$ 按式（4）～（6）计算；

$$
\mathrm { P _ { s } = m ^ { * } L ^ { * } P _ { s 1 } / ( L + m ^ { * } L ^ { * } P _ { p 1 } ^ { \phantom { * } } ) } = \mathrm { m } ^ { * } \mathrm { P _ { s 1 } / ( l + m ^ { * } P _ { p 1 } ^ { \phantom { * } } ) }
$$

$$
\mathrm { P _ { c } = m ^ { * } L ^ { * } P _ { c 1 } / ( L + m ^ { * } L ^ { * } P _ { p 1 } ) } { = } \mathrm { m ^ { * } P _ { c 1 } / ( l + m ^ { * } P _ { p 1 } ) }
$$

$$
\mathrm { P _ { E } = 1 - P _ { C } - P _ { S } }
$$

$$
\mathrm { P _ { s } } = \left( 1 - \mathrm { m } { ^ { * } \mathrm { P _ { c l } } } / \left( 1 + \mathrm { m } { ^ { * } \mathrm { P _ { p l } } } \right) / \ p \right) + \mathrm { m } { ^ { * } \mathrm { P _ { s l } } } / \left( 1 + \mathrm { m } { ^ { * } \mathrm { P _ { p l } } } \right)
$$

$$
\mathrm { P _ { C } = m ^ { * } P _ { C l } \ : / \left( 1 + m ^ { * } P _ { p l } \right) / \ : p }
$$

$$
\mathrm { P _ { E } = 1 - P _ { C } - P _ { S } }
$$

由于单组帧时隙ALOHA协议最高的标签识别率 $\mathrm { \sf P s } _ { 1 }$ ，冲突率 $\mathbf { P } \mathrm { c } _ { 1 }$ 和空闲率 $\mathbf { P } _ { \mathrm { E 1 } }$ 分别为 $3 6 . 8 \%$ 、 $2 6 . 4 \%$ 和 $3 6 . 8 \%$ ，每冲突时隙平均有2.39个标签，因此可取多位隙长度 $\scriptstyle \mathrm { p = } 2 , 3 , 4$ 0当 $\mathrm { m } { = } 1 { , } 4 { , } 8 { , } 1 6$ 且 $\scriptstyle \mathrm { p = 1 }$ 时，代入式（1)\~（3)，可计算得GMBPIP协议1个位隙时的识别率 $\mathrm { P s }$ 、冲突率 $\mathrm { \sf P c }$ 和空闲率 $\mathrm { \sf P _ { E } }$ ，列于表2。当 $\mathrm { m } { = } 1 6$ ， $\mathrm { p } { = } 1 , 2 , 3 , 4$ 时；代入式（4）～（6)，可计算得GMBPIP协议多位隙时的识别率 $\mathbf { P s }$ 、冲突率 $\mathrm { P _ { C } }$ 和空闲率 $\mathrm { \sf P _ { E } }$ 列于表3。

Table 2Performance analysis of GMBPIP Protocol (one bit-slot $\mathsf { p } { = } 1$   

<html><body><table><tr><td></td><td>m=1</td><td>m=4</td><td>m=8</td><td>m=16</td></tr><tr><td>PS</td><td>36.8%</td><td>41.72%</td><td>48.61%</td><td>52.99%</td></tr><tr><td>PC</td><td>26.4%</td><td>29.93%</td><td>34.87%</td><td>38.01%</td></tr><tr><td>PE</td><td>36.8%</td><td>28.35%</td><td>16.52%</td><td>10.00%</td></tr></table></body></html>

表3GMBPIP协议（多位隙 $\mathrm { p } { > } { = } 1$ $\mathrm { m } { = } 1 6$ ）性能分析

表2GMBPIP协议（单位隙 $p { = } 1$ ）性能分析  

<html><body><table><tr><td colspan="5">p>=1,m=16)</td></tr><tr><td></td><td>p=1</td><td>p=2</td><td>p=3</td><td>p=4</td></tr><tr><td>PS</td><td>52.99%</td><td>71.99%</td><td>78.33%</td><td>81.5%</td></tr><tr><td>PC</td><td>38.01%</td><td>19.01%</td><td>12.67%</td><td>9.5%</td></tr><tr><td>PE</td><td>10.00%</td><td>10.00%</td><td>10.00%%</td><td>10.00%</td></tr></table></body></html>

# 3 仿真实验

在MATLAB环境中，编制了GMBPIP协议的仿真程序，使用表4所列的时间参数，分不同并行处理组数和每组不同位隙数两种情况进行了仿真实验。其中：GMBPIP协议仿真所用时间参数参照文献[1]中 EPC Gen2 标准协议及文献[2]设定。表4中Tari为读写标签信令的参考时间间隔，对于读写标签链路的 data-O 和 data-1 的持续时间分别为 $1 2 . 5 ~ \mu \mathrm { s }$ 和 $2 5 ~ { \mu \mathrm { s } }$ ，传输速率为 $8 0  { \mathrm { k b p s } }$ ；而标签到阅读器反向链路的data-0 和 data-1 的持续时间均为 $6 . 2 5 ~ { \mu \mathrm { s } }$ ，相应的传输速率160kbps；对于 $\mathrm { m } { = } 1$ 的单组情况没有使用组位隙响应标志字WGPs，对应的仿真程序使用文献[6,7]改进的分组DFSA算法编程。

Table 3Performance analysis of GMBPIP protocol (multi bit-slo   
表4MPIP协议定时参数  
Table 3MPIP protocol timing parameters   

<html><body><table><tr><td>项目</td><td>时间(μs)</td><td>备注</td></tr><tr><td>Tari</td><td>12.5</td><td></td></tr><tr><td>TQuery</td><td>412.5</td><td>Query(Q)</td></tr><tr><td>TQueryRep</td><td>75</td><td>QueryRep</td></tr><tr><td>TQueryAdj</td><td>168.75</td><td>QueryAdjust</td></tr><tr><td>TQueryRepG</td><td>75</td><td>QueryRepG(gb,gp)</td></tr><tr><td>TwGPS</td><td>100</td><td>标签TwGPs响应</td></tr><tr><td>TEPC</td><td>1037.5</td><td>标签PEPC响应</td></tr><tr><td>Tc</td><td>337.5</td><td>标签冲突响应</td></tr><tr><td>TIdl</td><td>112.5</td><td>标签空闲响应</td></tr><tr><td>TSin</td><td>675</td><td>标签成功响应</td></tr></table></body></html>

# 3.1不同并行处理组数的仿真实验

仿真实验中被动标签的规模在2000\~12000，间隔500，标签分组估计采用文献[13]中相同的程序，并行处理组数$\mathrm { m } { = } 1 , 4 , 8 , 1 2 , 1 6$ ，重复仿真多次后取平均值，实验结果如图2\~4所示。其中图2为识别率、冲突率和空闲率变化比较图；图3为标签识别速度和标签读取速度变化比较图;图4为分组数、帧（Q值）调整次数和多组未识别尾标签合并数的比较曲线。从图中可以看出，GMBPIP多组并行协议在标签识别率、时隙利用率（响应率）明显高于单组协议；而帧（Q值)调整次数则明显低于单组协议。平均识别率突破了FSA协议最高 $3 6 . 8 \%$ 的瓶颈，达到了 $4 1 . 1 \% { \sim } 5 7 . 4 \%$ ，标签识别速度高达839\~975个/s标签读取速度448\~485个/s；时隙利用率为$9 2 \% { \sim } 9 7 \%$ 。就GMBPIP多组并行协议而言，随着并行处理组数 $\mathbf { m }$ 的增加，标签识别率、时隙利用率均有所提高，与理论分析基本一致；有些情况下由于多组尾标签合并，使协议工作在高效的识别范围内（单组256个标签)，因而其性能指标会高于理论值。然而，当 $\mathrm { m } > = 1 2$ 时，增长变慢。

表5列出了在标签总数为147000 的情况下，GMBPIP多组并行协议与单组协议[1在标签识别效率，平均识别速度和读取速度，运行时间的比较。

表5GMBPIP不同并行处理组数仿真结果比较分析

Table 5Comparison of simulation results of different parallel processing groups in GMBPIP   

<html><body><table><tr><td colspan="2">P</td><td>P m=4</td><td>m=8</td><td>m=12</td><td>m=16</td></tr><tr><td>平均识别效率</td><td>m=1（单组） 35.8%</td><td>42.1%</td><td>51.14%</td><td>55.05%</td><td>57.43%</td></tr><tr><td>最好识别效率</td><td>36.5%</td><td>42.7%</td><td>52.65%</td><td>57.49%</td><td>59.72%</td></tr><tr><td>最差识别效率</td><td>35.2 %</td><td>41.4%</td><td>49.52%</td><td>51.75%</td><td>52.58%</td></tr><tr><td>平均识别速度</td><td>803/s</td><td>839/s</td><td>920/s</td><td>954/s</td><td>975/s</td></tr><tr><td>平均读取速度</td><td>438/s</td><td>448/s</td><td>471/s</td><td>480/s</td><td>485/s</td></tr><tr><td>运行时间</td><td>11.16s</td><td>11.20s</td><td>10.52s</td><td>9.88s</td><td>9.55s</td></tr></table></body></html>

# 3.2不同位隙数的仿真实验

仿真实验中被动标签的规模从2000到12.000间隔1000，标签分组估计采用文献[13]中相同的程序，并行处理组数$\mathrm { m } { = } 1 6$ ，重复仿真多次后取平均值，实验结果如图5\~7所示。其中图5为识别率、冲突率变化比较图；图6为标签识别速度和标签读取速度变化比较图;图7为分组数、帧（Q值）调整次数和多组未识别尾标签合并数的比较曲线。从图中可以看出，GMBPIP多位隙并行协议在标签识别率、时隙利用率（响应率）明显高于单位隙协议；而帧（Q值）调整次数则明显低于单位隙协议。平均识别率在多组单位隙$4 1 . 1 \% \sim 5 7 . 4 \%$ 基础上，通过多位隙的设置又将响应时隙中部分冲突时隙转换为成功时隙，标签平均识别率为$7 0 . 9 5 \% { \sim } 8 1 . 6 1 \%$ ，识别速度高达1110\~1207个/s标签读取速度516-536个/s;；均高于目前文献[9,11,12,14]所述同类算法的性能指标。就GMBPIP并行协议多位隙而言，随着位隙数p 的增加，标签识别率、时隙利用率均有所提高，与理论分析基本一致；有些情况下由于多组尾标签合并，使协议工作在高效的识别范围内（单组256个标签)，因而其性能指标会高于理论值。然而受冲突时隙中标签数的限制（平均2.39个）随着p的增加，增长变慢；p从3增长到4，平均识别率只增加了 $3 . 6 \%$ 。因此 $\mathfrak { p }$ 取3或4较为合适。表6列出了在标签总数为77000的情况下，GMBPIP多组并行协议与单组协议[1在标签识别效率，平均识别速度和读取速度，运行时间的比较。

表6GMBPIP协议多位隙仿真结果比较分析 $\scriptstyle ( m = 1 6$   
Table 6Comparative analysis of multi bit-slot simulation results of   

<html><body><table><tr><td colspan="5">GMBPIP protocol (m=16)</td></tr><tr><td></td><td>p=1(单位隙)</td><td>p=2</td><td>p=3</td><td>p=4</td></tr><tr><td>平均识别效率</td><td>57.98 %</td><td>70.95%</td><td>78.07%</td><td>81.61%</td></tr><tr><td>最好识别效率</td><td>60.41 %</td><td>73.42%</td><td>80.01%</td><td>82.28%</td></tr><tr><td>最差识别效率</td><td>55.22 %</td><td>68.20%</td><td>76.05%</td><td>80.42%</td></tr><tr><td>平均识别速度</td><td>980/s</td><td>1110/s</td><td>1176/s</td><td>1207/s</td></tr><tr><td>平均读取速度</td><td>486/s</td><td>516/s</td><td>530/s</td><td>536/s</td></tr><tr><td>运行时间</td><td>2.41s</td><td>21.97s</td><td>19.61s</td><td>18.24s</td></tr></table></body></html>

# 4 结束语

本文以EPCGen2协议为基础，充分考虑了RFID系统阅读器较强的计算能力和巨量的被动标签非常受限的计算资源，采用位隙FSA协议标签响应标志位隙的设置方法，通过在标签上设置一个组位隙响应标志字，提出了一种 EPCGen2标准下的RFID标签分组多位隙并行识别协议GMBPIP，设计了一条新的分组查询命令和基于DFSA的多组标签并行识别协议流程，从理论上分析了协议的性能，并使用EPCGen2标准协议的时间参数进行了仿真实验。结果表明，在不增加标签太多计算负担的情况下，能够在EPCGen2标准下有效的把空闲时隙转换为成功和冲突时隙，多位隙的设置又将部分冲突时隙转换为成功时隙，大大降低了时隙空闲率和冲突率，提高了标签的识别率、时隙利用率，平均识别率不仅突破了DFSA协议最高 $3 6 . 8 \%$ 的瓶颈，而且高于目前文献[9,11,12,14]所述同类算法的性能指标，标签平均识别率达到了 $7 0 . 9 5 \% { \sim } 8 1 . 6 1 \%$ ，识别速度高达1110\~1207个/s标签读取速度516\~536个 $/ \mathrm { s } ;$ ；时隙利用率为 $9 2 \% { \sim } 9 7 \%$ 。可以作为低成本RFID系统高速识别大量被动标签的支撑协议。

# 参考文献：

[1]EPCGlobal.EPCradio-frequencyidentityprotocols，class-1 generation-2 UHF RFID protocol for communications at 860 MHz\~960 MHz, version 2.0.0 [S].2013.   
[2] Chen W T.A Feasible and easy-to-implement anti-colision algorithm for the EPCglobal UHF class-1 generation-2 RFID protocol [J]. IEEE Trans on Automation Science and Engineering,2014,11(2): 485-491.   
[3]Duan Litian,Wang Zizhong J, Duan Fu. An identification algorithm in grouping and paralleling for data-intensive RFID systems [C]//Proc of the 1st International Conference on Big Data Computing and Communications.Cham: Springer, 2015.   
[4] Daneshmand M，Wang C,Sohraby K.A new slot-count selection algorithm for RFID protocol [C]/Proc of the 2nd International Conference on Communications and Networking.2007.   
[5]Myung J,Lee WJ,Srivastava J.Adaptive binary splitting for efficient RFID tag anti-collision [J]. IEEE Communications Letters,2O06(10): 144-146.   
[6] Lee S R,Joo S D,Lee C W.An enhanced dynamic framed sloted ALOHA algorithm for RFID tag identification [C]// Proc of the 2nd Annual International Conference on Mobile and Ubiquitous Systems: Networking and Services.Washington DC:IEEE Computer Society, 2005:166-174.   
[7]Wang Hui,Xiao Shengliang,Lin Feiyu.Group improved enhanced dynamic frame slotted ALOHA anti-collision algorithm [J]. Journal of Supercomputer, 2014,69(3): 1235-1253.   
[8]史长琼，肖瑞强，吴丹．改进的动态帧时隙 ALOHA 防碰撞算法[J]. 计算机工程与设计,2014,35(6):1897-1900.(Shi Changqiong，Xiao Ruiqiang,Wu Dan. Improved anti-collision algorithm based dynamic frame timeslot ALOHA[J]. Computer Engineering and Design,2014, 35(6): 1897-1900. )   
[9]杜永兴，白文浩，李宝山.RFID 系统动态帧时隙 ALOHA 算法的改 进[J]．高技术通讯,2015,25(3):313-318.(Du Yongxing,BaiWenhao, Li Baoshan.Improvement of the dynamic framed sloted ALOHA algorithm for RFID systems [J]. Chinese High Technology Letters, 2015,25(3): 313-318. )   
[10]栗华.UHF RFID 多标签防碰撞算法的研究与性能分析 [D].济南: 山东大学,2Ol1.(Li Hua.Research and performance analysis of UHF RFIDmulti-taganti-collision algorithms[D]. Jinan:Shandong University, 2011)   
[11]邢志鹏，杨恒新，张昀．分段式位隙分组帧时隙 ALOHA 算法[J].计 算机技术与发展,2016,26(4):31-35.(Xing Zhipeng,Yang Hengxin, Zhang Yun.A frame slot ALOHA algorithm of sectional bit-slot group [J].Computer Technology and Development,2016,26(4): 31-35.)

[12]段力畑，王子中，段富.基于分组的多级随机数RFID标签并行识别 算法[J].太原理工大学学报，2016，47(4):495-500.(Duan Litian, Wang Zizhong,Duan Fu.A parallel identification algorithm for RFID tags with group-based multiple-random numbers[J]. Journal of Taiyuan University of Technology,2016,47(4): 495-500.)

[13] Duan L T,Zhang X Y,Wang Z Z,et al.Grouping-paralleling identification and authentication algorithm for RFID system in EPCglobal G2V2 [J]. Journal of Computational and Theoretical

Nanoscience,2016,13(5):3183-3196.   
[14]赵璐璐.RFID 标签防碰撞算法研究[D].广州:广东技术师范学院, 2017.(Zhao Lulu.Research on anti-collision algorithm of RFID tag [D]. Guangzhou: Guangdong Polytechnic Normal University,2017.)   
[15]傅豪磊,陆王延.基于多处碰撞位探测的标签防碰撞算法研究[J]. 2018,35(12):3757-3760,3765.(Fu Haolei,Lu Wangyan.Research of tag anti-collision algorithm based on multiple collision bits detection [J]. 2018,35(12):3757-3760,3765.)