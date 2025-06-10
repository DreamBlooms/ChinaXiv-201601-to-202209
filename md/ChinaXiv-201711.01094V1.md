# 低频射电天线数字终端的设计与实现

张金鹏1,²，何乐生²,，董亮²,，王 婷}，李学敏4云南大学信息学院，云南 昆明650091；2.中国科学院天体结构与演化重点实验室，云南 昆明650011;3.中国科学院云南天文台，云南 昆明 650011；4.昆明医科大学海源学院，云南 昆明650106)

摘要：自天文观测进入全波段观测时代以来，全波段中的低频射电信号是新的重要观测波段以及研究窗口。鉴于此波段的信息对于研究太阳以及行星的射电爆发具有重要意义，并且人类对此频段的研究几乎处于空白状态，现在欧美一些国家以及我国都已经适时地开启了相关研究。目前中国科学院云南天文台已经开启了此项目的建设，现已有4台低频射电天线可以测试使用。其低频射电天线阵可以和云南天文台已有的 $1 0 \mathrm { ~ m ~ }$ 太阳射电望远镜以及 $1 1 \mathrm { ~ m ~ }$ 太阳射电望远镜配合使用，用于更精确地观测太阳或者其他行星的射电信息。设计首先由A/D板卡接收来自低频射电天线的低频天文信号，接着A/D板卡把转换的数字信号以差分信号的形式传至现场可编程门阵列板卡；现场可编程门阵列对数据整合处理，通过异步先入先出队列(First Input First Output，FIFO)跨时钟域的形式把数据通过千兆以太网以UDP 协议的形式传至PC 端；然后PC 端设计的软件对传输来的数据做加窗和快速傅里叶变换处理并显示。

关键词：低频射电天线；FPGA；异步FIFO；千兆以太网；UDP中图分类号：P111.44 文献标识码：A 文章编号：1672-7673(2016)02-0170-08

# 1背景及研究意义

通过天文观测探索宇宙是人类探索宇宙奥秘最重要的方法之一，随着科技的进步和高新设备的出现，研究的方向以及范围在不断扩大。现在天文观测已经进入全波段观测时代。全波段中的低频射电波段( $1 0 { \sim } 2 5 0 ~ \mathrm { M H z } )$ 是一个新的重点观测和研究窗口，此频段射电辐射对于研究太阳以及行星射电爆发的信息具有重要意义。

天体的特性和状态由天体的电磁辐射反映出来，在研究包括太阳和地球以及行星和太阳系外天体时射电观测是一种重要手段。目前射电天文学的观测研究呈现向低频和甚高频发展的趋势，频率在$8 0 ~ \mathrm { M H z }$ 以下的甚高频(Very High Frequency，VHF)频段射电辐射提供了大量关于太阳和行星射电及爆发的信息，该频段不是现在人类能够观测的电磁波段的简单外推，而是一个具有重大意义和重要地位的探索空间。因为这个频率范围几乎没有过有效空间分辨率的观测，人类对于这个频率的了解几乎为零，而且很多天文现象只有在甚低频波段才能探测。对于这个波段的研究具有重要的意义，预计的科学探测内容包括太阳日冕物质抛射和射电爆发、木星射电爆发、低频和甚低频脉冲星辐射、银河电离氢分布探测等，而由于对此波段的未知性，发现全新现象也有很大可能。针对其具有的现实意义，以及发展低频段的迫切需求，中国科学院云南天文台正致力于建设适应多科学目标的低频射电天文平台，工作频率设置在 $3 0 { \sim } 8 0 \mathrm { M H z }$ ，并可以和现有的 $1 0 \mathrm { m }$ 太阳射电望远镜( $6 2 5 \sim 1 5 0 0 \mathrm { M H z }$ ）、 $1 1 \mathrm { ~ m ~ }$ 太阳射电望远镜( ${ \mathrm { 7 0 } } { \sim } 7 0 0 ~ \mathrm { M H z }$ )一起配合使用实现频谱观测。

我国的射电天文学在米波到毫米波有了很大的进展，而且实现了米波段的综合孔径阵，在厘米波段实现了甚长基线干涉测量技术，在毫米以及亚毫米波段参与了国际阿塔卡马大型毫米波/亚毫米波天线阵计划和南极太赫兹天文观测计划。近年来我国在国际 $1 ~ \mathrm { k m } ^ { 2 }$ 接收面积射电阵和 $6 0 { \sim } 2 3 0 ~ \mathrm { M H z }$ 固定方向低频宇宙射电阵等观测技术领域也有了很大的进展。在十米波测量领域，今年还在空间项目论证如月面射电阵、空间低频预研究领域开展了一些调研论证工作。国际上，从射电天文观测系统成熟以来，只有少数国家的天文台在进行甚低频段的天文观测，所以开展我国的陆基低频射电观测研究具有相当大的意义[1]。

# 2系统设计

系统设计模型如图1。首先从低频射电天线接收两路模拟信号，通过模数转换器把接收的两路模拟信号转换为两路14 位数字信号，然后通过现场可编程门阵列（Field-Programmable Gate Array，FPGA)对得到的两路数据进行处理，并通过千兆以太网以用户数据报协议（User Datagram Protocol,UDP)的形式发送至PC端[1」，最后由C#编写的上位机软件接收数据，并对得到的数据进行整合处理后进行快速傅里叶变换、频谱显示、存储。系统中信号的采集开始由触发条件给予，包括手动触发和自动触发两种，最终实现观测终端的设计[2]。

![](images/34be0417923bc6a3149694eda4e896a39d5ec94493baa9c46a6f214a030c5950.jpg)  
图1系统模型Fig.1System model

本文重点介绍数字观测终端设计中现场可编程门阵列数据处理部分及上位机数据整理和处理部分，其中主要包括异步FIFO跨时钟域处理数据部分和千兆以太网传输以及上位机数据排序、加窗和快速傅里叶变换部分。具体的数据处理流程如图2。

![](images/971a477a0196c885ead005888ecd72073f9fdf98ede134e3bb1a39f3644f0572.jpg)  
图2现场可编程门阵列数据处理模型Fig.2The data processing model of FPGA

# 2.1现场可编程门阵列硬件设计

# 2. 1. 1 跨时钟域异步FIFO设计

在进行异步FIFO缓存之前，先对从模数转换器板卡过来的信号进行差分到单端的处理再通过简化亚稳态电路单端信号数据。两路信号均为14位，但是千兆以太网发送数据格式最小单元为8位，所以第1步要对得到的两路14位数据进行整合处理，本项目采用把A、 $B$ 两通道数据组成一个新的28位的数据， $A$ 通道数据在高14位， $B$ 通道数据在低14位；接着设置FIFO参数时选择写入数据宽度为28位，读出数据宽度为7位；又因为千兆以太网传输单元的问题，在FIFO输出7位数据的同时，给这个数据最高位补一个0，这样就得到所需要的8位数据。数据深度根据每次数据量填写，同时在设置FIFO参数时选择读写时钟相互独立，写时钟为系统主时钟 $2 4 5 . 7 6 \mathrm { M H z }$ ，读时钟为 $1 2 5 \mathrm { M H z }$ ○由于读写时钟的不同，所以必须要对读写信号加以控制，否则可能有溢出的情况出现。在本项目中由于数据量非常大，不可能全部进行处理，所以采取分段式的缓存数据并传至PC端。这里以每次传输0.5MB数据为例，异步FIFO的深度为131072，同时这也是项目可使用最大FIFO的深度[3]。

需要一个时序逻辑配合控制FIFO以达到跨时钟域数据缓存的问题，每次数据来临之前也就是初始状态FIFO是空，标志位为1，满标志位为0，同时读写标志位都为0；通过外部触发键位之后写标志为1，开始写入数据，此时空标志位和满标志位为0，读标志位为0；当FIFO被写满时，满标志位为1，同时反馈给写标志和读标志，此时写标志变为0，读标志变为1；这时开始读数据直至数据全部读完，空标志位变为1,并把信号反馈给读标志，然后读标志为0，同时写标志也为0，空标志位为1，满标志位为0又恢复至初始状态。至此一个完整的跨时钟域读写过程完毕，等下一次外部触发或者等待时间的自动触发又开始新的循环。具体流程如图3。

# 2.1.2千兆以太网设计及UDP协议实现

设计采用系统集成的千兆以太网IP 核，tx_axis_mac_tlast、tx_axis_mac_tready、tx_axis_mac_tuser、tx_axis_mac_tvalid，信号的控制实现发送逻辑[4-5]。所以只需要对其发送数据段的接口重新定义。在设计中根据实际需求简化了原来的时序逻辑，重新对发送、接收、间隔等定义[6]，千兆以太网IP 核模型如图4。

![](images/d112064fec5df6e3cbc324219a57d5e01032d63c3b81923b97d66e89095c9031.jpg)  
图3跨时钟域FIFO缓存数据时序逻辑Fig.3Asynchronous FIFO buffer sequential logic

![](images/5222cfc783123b0e8f3497178fc297e6ff22295ed2a3f0fc55fa7bec5c9388ac.jpg)  
图4千兆以太网传输模型 Fig.4Gigabit ethernet transmission model

在异步FIFO数据写满，同时触发条件也达到后，需要先传递帧头信息。帧头信息由12字节的物理网卡地址信息，20字节IP帧头以及8字节的UDP帧头3部分组成。在传输完帧头信息后开始数据传输，由于UDP协议的不可靠性所以在帧结尾处加了标记信息，以便传输完成数据重新排序整理。标记信息用两字节表示[7]。除了需要传输信息之外的数据达到了 $1 2 + 2 + 2 0 + 8 + 2$ 共44字节。

由于采用深度为131072，输人宽度为28位FIFO缓存数据，经过计算在输出数据首位补零情况下如果按照上文定义的每帧数据为1024字节，那么一个FIFO完整数据传输需要512帧数据。每帧实际传输数据量为 $1 0 2 4 + 4 4$ 共 $1 0 6 8$ 字节。由于两路14位数据从进入以太网传输开始就已经拆分重新组合，再加上帧头帧尾信息每帧的数据字节分配有些模糊，表1是每帧数据分配字节的详细信息。

通过表1可以直观看出每帧信息的发送格式。

帧间距的处理：触发传输条件之后，千兆以太网使能端开启，传输有效标志位为1，同时帧头开始传输直至每帧帧尾的标记信息传输完成（这里tlast标志位出现一个周期1信号），千兆以太网IP核使能端关闭，同时开始计数，根据计数数目计算时间，根据上位机UDPCLIENT类可实现数据吞吐速度为标准，采用等待时间为 $1 0 ~ \mathrm { { m s } }$ 左右。计数完成后再开始新一轮的循环，下一帧数据开始传输。

包间距处理：当一次FIFO中数据全部传完之后，系统进入等待状态，这里的等待会出现两种触发，一种是外部按键触发（触发条件同一个按键)，另一个等待是时间等待。这两个等待无论哪一个触发了传输等待系统都会重置，等待下次触发具体流程如图5。设计的等

# 表1帧数据字节信息分配表

Table1The frame data byte of information distribution table   

<html><body><table><tr><td>0~41字节</td><td colspan="2">帧头信息</td></tr><tr><td></td><td colspan="2">数据位分布(一个字节8位数据)</td></tr><tr><td>42字节</td><td>第7位：0</td><td>第6~0位：A通道13~7</td></tr><tr><td>43字节</td><td>第7位：0</td><td>第6~0位：A通道6~0</td></tr><tr><td>44字节</td><td>第7位：0</td><td>第6~0位：B通道13~7</td></tr><tr><td>45字节</td><td>第7位：0</td><td>第6~0位：B通道6~0</td></tr><tr><td>46字节</td><td>第7位：0</td><td>第6~0位：A通道13~7</td></tr><tr><td></td><td></td><td></td></tr><tr><td>1065字节</td><td>第7位：0</td><td>第6~0位：B通道6~0</td></tr><tr><td>1066~1067字节</td><td colspan="2">帧尾信息</td></tr></table></body></html>

待时间为16s左右，主要为上位机存储数据，做数据分析、快速傅里叶变换、显示等功能留下充裕的时间。

# 2.2上位机软件设计

在现场可编程门阵列工作部分完成后，数据通过千兆以太网以UDP协议传输，本节需要做的工作是在上位机部分接收并处理数据[8]。

# 2.2. 1 数据接收部分设计

在上位机上，数据处理最重要的部分是数据完整性检测，对数组重新排序并去除顺序标记位。

(1)数据完整性检测，从UDP 缓存区异步读取数据之后，首先要对数据的长度进行检测，从UDP 接收的数据包含帧尾信息，共1026字节，512帧数据。如果每帧数达到了1026字节，那么进入

下一步筛选，否则删除数据等待下次接收。第二步筛选则是通过检测帧尾信息决定，由于共有512帧数据，因为是从0帧开始算起，最后一帧帧尾的最后两个字节是01FF（511），所以第二步通过检测最后一帧帧尾信息决定信息是否需要删除。第三步，由于数据共有512帧，对接收的数据进行帧数的计数，如果达到了512帧则进入下一个处理环节，如果没有达到则数据删除并等待下一包数据的到来。流程原理如图5。

(2)数组排序是把得到的512行数组的行重新排序，相当于把得到的512帧数据根据原来帧尾标记排序。循环排序：检索每行数据最后两个字节，从0开始，找到后把这行数据作为第1帧数据存储，并且在存储时，只存储前面1024位，这样只需要512次循环就可以完美解决排序这一难点。

# 2.2.2加窗及快速傅里叶变换设计

加窗：需要通过一个窗函数与数据信号相乘

![](images/95d7160d98cad53056935a17ab57a32359c20c76127d701b253250855944fe90.jpg)  
图5数据接收检测流程图 Fig.5Data receiving inspection

即可实现[9]

快速傅里叶变换：首先要把时域数据放到复数域中，这步通过建立一个复数域的类实现，完成之后实现频率域和时域对象的建立；第二步则是对信号进行快速傅里叶变换，此处主要通过蝶形运算实现，第三步是对变换过的信号求平方根，并取对数得到最终结果[10]。然后就可以显示得到的信号,这里定义 $X$ 轴为频率，Y轴为幅度(dB）。图6为上位机界面。

![](images/956c249a5d08870e767b934daa579c6f099879331fa083ad9c19c6a375aacfd4.jpg)  
图6上位机界面Fig.6Computer UI

# 3重要指标分析

由于在低频射电观测前端的采集中器件的低频噪声和电磁干扰相对较大，所以在数字终端的设计上就要在无杂散动态范围和频分辨率上有非常好的性能，否则无法准确得到采集信号并对信号进行分析。由于数字终端采集数据精度较高、速度较快而导致数据吞吐量较大，所以为了有利于后期的存储等在快速傅里叶变换运算时间上也有较高的要求。

# 3.1无杂散动态范围

无杂散动态范围用来表示整个动态范围的一部分，是指当两个等功率信号输入时，没有超过噪底3dB 的虚假信号范围。接收机的动态范围是指可用输入信号的范围。确定动态范围下限的标准称为最小可检测信号，被定义为在一个给定的中频带宽内大于等效噪声功率3dB 的信号。

通过公式计算以及实际测量测试信号和射电信号进行对比确定项目的准确性。

$$
P _ { \mathrm { \Phi } } = M D S = - \ 1 7 1 \mathrm { d B m } \ + \ N F + \ 1 0 1 \mathrm { g } B ,
$$

其中， $P _ { \mathrm { ~ l ~ } }$ 表示动态范围下限，单位为 $\mathrm { { d B m } }$ ；MDS表示最小可检测信号，单位为 $\mathrm { { d B m } }$ ；NF为噪声系数，单位为dB； $B$ 表示带宽，单位为 $\mathrm { H z }$ 。

无杂散动态范围（Spurious Free Dynamic Range，SFDR)的上限规定为：产生等于最小可检测信号的三阶互调产物的两个等电平输入信号电平。

$$
M D S = 3 ( P u ) - 2 ( I P ) ,
$$

其中， $P u$ 表示无杂散动态范围上限； $I P$ 表示接收机三阶截点，单位为 $\mathrm { { d B m } }$ 。功率上限值为

$$
P u = \frac { 1 } { 3 } ( M D S + 2 I P ) ,
$$

基于 $P u$ 和 $P _ { \mathrm { ~ l ~ } }$ ，可以得到无杂散动态范围的公式为

$$
\begin{array} { l } { { \displaystyle S F D R = P u - P _ { \mathrm { l } } } } \\ { { \displaystyle \quad = \frac { 2 } { 3 } ( I P - N F - 1 0 \mathrm { l g } B + 1 7 \mathrm { l d B m } ) , } } \end{array}
$$

其中，SFDR的单位为 $\mathrm { { d B m } }$ ； $N F$ 为噪声系数，其理论公式为

$$
N F = P _ { \mathrm { { F S } } } + 1 7 4 \mathrm { { d B m } } - S N R - 1 0 { \mathrm { l g } } B - 1 0 { \mathrm { l g } } { \frac { f _ { \mathrm { { s } } } } { 2 B } } ,
$$

其中，SNR为信噪比； $P _ { \mathrm { { F S } } }$ 为输入功率； $f _ { \mathrm { s } }$ 为采样频率； $B$ 为带宽。根据ADS62P49数据手册给出的参数，可算出噪声系数为 $1 0 ~ \mathrm { d B m }$ 。输入截点为 $- 5 ~ \mathrm { d B m }$ ，如果对 $5 \ : \mathrm { M H z }$ 信号进行采样，通过计算可以得到无杂散动态范围SFDR为 $5 9 . 3 ~ \mathrm { d B }$ ，通过使用信号发生器产生 $5 \ : \mathrm { M H z }$ 信号进行实际测量可知，最大谐波为0.1dB，而最高频点为6dB，两者相比，可以得到实际 SFDR为 $6 0 ~ \mathrm { d B ^ { [ 1 1 ] } }$ 。

3.2谱分辨率及快速傅里叶变换运算时间

# 3.2.1 谱分辨率

谱分辨率即在进行离散傅里叶变换时，在频率轴上可以得到的最小频率间隔。根据采样频率为 $1 2 2 . 8 8 ~ \mathrm { M H z }$ ，进行快速傅里叶处理时每次处理点数为131072个，计算可知进行快速傅里叶变换之后频谱图的频率分辨率为 $0 . 9 \mathrm { \ k H z }$ 左右。图7是通过对 $5 \mathrm { M H z }$ 进行测试处理得到的历史数据进行Matlab分析图，能实时反映系统对频率的响应情况。由图7可以看到每隔 $0 . 9 \mathrm { k H z }$ 就有信号的能量值，完全符合系统设置最低频率分辨率的 $0 . 9 \mathrm { k H z }$ 。

# 3.2.2快速傅里叶变换运算时间

通过千兆以太网以UDP方式发送数据，传输

![](images/b7953bf5c4fba22d55f2b8ab5ccdc43e7fe6ea77b5d08bad265138c4c4b49d32.jpg)  
图7频率分辨率检测  
Fig.7Frequency and resolution detection

过程中每包数据即为一次发送。其中每个数据包共有 512 帧数据，而帧与帧之间的时间间隔是根据Udp Client类接收数据的速度决定，通过不同速度尝试，最后以帧间隔 $1 0 ~ \mathrm { { m s } }$ 最为准确，UDP方式的丢帧等情况发生最少。在512帧数据全部发送完成后也就是一包数据传输完成，这时需要对数据进行快速傅里叶变换处理，意味着在快速傅里叶变换处理没有完成之前下一包数据不能到来，否则造成程序报错。每包数据共512帧，帧间隔 $1 0 ~ \mathrm { { m s } }$ ，也就是每包数据传完需要 $5 . 1 2 \mathrm { ~ s ~ }$ 。再通过对131072个点做快速傅里叶变换运算时间进行测试，看到需要时间为0.87s左右，所以包与包之间间隔完全可以为0，这包数据接收完成并做快速傅里叶变换后存储（存储时间0.1s左右)，同时下一包数据传输，在本包数据快速傅里叶变换运算和存储都完成的情况下，下包数据还需要 ${ 5 . 1 2 \ \mathrm { s } } \sim 0 . \ 1 \ \mathrm { s } \sim 0 . \ 8 7$ s才能传输成功，在时间上完全可以达到要求。数据存储完毕后可以再次把接收的数据重新进行分析。

# 4结果分析

对远场信号测试得到频谱图如图8，可以看到在 $5 9 . 4 ~ \mathrm { M H z }$ 有很明显的频点凸起，通过和天文台采集设备AD6557A比较可以看到，在无杂散动态范围、频率分辨率、快速傅里叶变换时间以及存储和后续显示上有明显的进步。

![](images/3ec5f5fcc55e9b98857a01527136c8b17d652cff42e6a915b3b7384ab988743e.jpg)  
图8远场加上单极化天线采集图形 Fig.8Observatory field testing

# 5结束语

系统针对低频射电信号的接收及观测提出了完整的解决方案，系统主要实现了数据千兆以太网的UDP 传输以及快速傅里叶变换频谱分析。目前系统已经完成测试并加人了实际信号，实践证明系统的正确性、可行性以及可靠性。上述通过现场可编程门阵列和高速AD以及上位机软件界面进行低频射电观测的方法被证明是有效的，未来在低频射电领域发挥巨大的作用。

# 参考文献：

[1] 张西洋，何乐生，董亮，等.800\~975MHz太阳射电数字观测终端的设计与实现［J]．天文研究与技术——国家天文台台刊，2014，11(2)：118-122.Zhang Xiyang，He Lesheng，Dong Liang，et al．Design and implementation of a digitalobservation terminal for solar radio observation within the 8OO-975MHz band ［J].AstronomicalResearch & Technology———Publications of National Astronomical Observatories of China，2014,11(2):118-122.  
[2] 朱凯，张坚.基于解析信号处理的下变频系统FPGA实现与天文应用［J]．天文研究与技术——国家天文台台刊，2009,6(1)：51-56.Zhu Kai, Zhang Jian. The FPGA realization of a DDC system based on analytical-signal processingand its application in astronomy[J]．Astronomic Research & Technology- Publications ofNational Astronomical Observatories of China，2OO9，6(1）：51-56.  
[3] 于海，樊晓雅．基于FPGA异步FIFO的研究与实现［J］．微电子学与计算机，2007，24(3):211-212.Yu Hai,Fan Xiaoya.Research and implementation of asynchronous FIFO based on FPGA[J].Microelectronics & Computer，2007，24(3）:211-212.  
[4] Tri-Mode Ethernet Media Access Controller（TEMAC）[EB/OL].[2015-03-28]. http://www.xilinx.com/products/intellectual-property/temac.html#overview.  
[5] Tri-Mode Ethernet MAC v9.0 LogiCORE IP Product Guide [EB/OL].[2015-03-28]. http ://www.xilinx.com/support/documentation/ip_documentation/tri_mode_ethernet_mac/ $\mathrm { ^ { \prime } v 9 \_ 0 / p g 0 5 1 } .$ tri-mode-eth-mac.pdf.  
[6] 韦宏，付友涛，孔凡鹏，等.基于FPGA的千兆以太网设计［J].现代电子技术，2012，35(18): 56-59.Wei Hong，Fu Youtao，Kong Fanpeng，et al. Design of gigabit Ethernet system based on FPGA[J].Modern Electronics Technique，2012，35(18）:56-59.  
[7] 胡维华，胡昔祥．网络协议分析与实现［M].北京：高等教育出版社，2012：155-156.  
[8] Jack_guanggong.C#的优点［EB/OL].[2015-03-28].http://1108038.blog.51cto.com/1098038/413401.  
[9] 刘广臣，张惠安，贾爱宾.数字信号处理中的加窗问题研究［J].长沙大学学报，2003，17(4): 59-63.Liu Guangcheng，Zhang Huian，Jia Aibin. Study on the window-adding problem in the digitalsignal processing [J]. Journal of Changsha University，2003，17(4） : 59-63.  
[10] 史浩．快速傅里叶变换与C#实现［J].福建电脑，2013，12：99-103.Shi Hao.The implementation of FFTon C#［J].FuJian Computer，2013，12：99-103.  
[11］穿越霓红-华欣．无杂散动态范围 SFDR——影响通信机性能的因素［EB/OL]．［2015-03-28].http://blog.sina.com.cn/s/blog_4b3107860100xdvu.html.

# The Design and Implementation of a Low Frequence Radio Antenna Array Digital Terminal

Zhang Jinpeng $^ { 1 , 2 }$ ，He Lesheng $^ { 2 , 3 }$ ，Dong Liang2,³，Wang Ting1，Li Xuemin4 (1.SchoolofInformationScienceandEngineering，Yunnan UniversityKunming650o1,China,Email：uanpingji@63.com;   
2.KeyLaboratoryforthe StructureandEvolutionofCelestialObjects，ChineseAcademyof Siences,Kunming 65ool1,China;   
3.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65Oo11,China；4.Kunming Medical University Haiyuan College，Kunming 65O1O6,China)

Abstract：Since the astronomical observation took its step into the era of full-wave observations，the low frequency radio signal of ful-wave observation has become a new yet important band for observation It also providesanew path for research.Radio information in this band plays an importantrole inthe studyof solar and other planets’radio burst，yetrelated researches in thisareaarealmost in a blank state.Therefore，some countries in Europe and America as wellas China have already started to do some related researches.Yunnan Observatories，Chinese Academy of Sciences，has launched this project.Now there are four low frequency radio antennas can be used in this project.The low-frequency radio antenna arrycan be used cooperatively with the ten-meter solar radio telescope and the eleven-meter solar radio telescope，which are already in service in Yunnan Observatories.Together theycan accurately observe the radio information of the Sun and other planets. Of this design，A/D card firstly receives the low frequency astronomical signal from the low frequency radio antenna；then theA/Dcard passes the converted digital signals to the FPGAcard bythe formof differential signal；FPGA integrates and processes the data. Besides,FPGA uses a form of asynchronous FIFO clock domain to pass he data to thePC terminal by Gigabit-Ethernetwith User Data-gram Protocol；then the software designed by PC terminal window displays the data and the processing of FFT.

Key Words:Low frequency radio antennas；FPGA；Asynchronous FIFO；UDP；Gigabit-ethernet