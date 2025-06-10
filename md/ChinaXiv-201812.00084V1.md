# 可并行识别的UHFRFID防碰撞算法研究

何怡刚，佘培亮，佐磊，张超群(合肥工业大学 电气与自动化工程学院，合肥 230009)

摘要：针对于传统的动态帧时隙 Aloha 多标签防碰撞算法（DFSA）的系统吞吐率低、系统识别率低等问题进行了研究，提出一种可并行识别的UHFRFID 防碰撞算法(OVSF-DFSA）。该算法通过基于正交可变扩频因子（OVSF)码作为扩频码的码分多址技术和动态帧时隙 ALOHA（DFSA）协议相结合，突破了传统算法中单一时隙中只能识别一个标签的局限性，实现了标签碰撞到码碰撞的转变。以理论分析和仿真实验为基础，探究了该算法下的系统吞吐率、系统总时隙数及系统识别率等方面的性能。仿真结果表明，当帧长 $\mathrm { f s } { > } 2$ 且OVSF码长 $\mathrm { m } { > } 2$ ，当标签数目大于200 时，OVSF-DFSA 算法下系统吞吐率是 DFSA 算法的m 倍，且与 DFSA，MS-DFSA，PIGDFSA 算法相比，OVSF-DFSA算法在上述性能方面效果更佳。

关键词：射频识别；可并行识别；码分多址；OVSF-DFSA 中图分类号：TN929.5 doi:10.19734/j.issn.1001-3695.2018.07.0550

Research on anti-collision algorithm of UHF RFID based on parallellizable identification

He Yigang†, She Peiliang, Zuo Lei, Zhang Chaoqun (SchoolofElectrical Engineering&Automation,Hefei University ofTechnology,Hefei 23ooo9,China)

Abstract:Aiming attheproblems oflowsystemthroughputrateandlowsystemidentificationrateof traditionaldynamic frame timegap Aloha multi-label collision prevention algorithm (DFSA），this paper proposes an UHFRFIDcollision prevention algorithm (OVSF-DFSA）which can be identified in parallel.Bycombining the code division multiple access technology based onorthogonal variable spread spectrum factor(OVSF)code as spread spectrum code and dynamic frame time slot ALOHA(DFSA)protocol,the algorithm breaks the limitationofrecognizingonlyonetag inasingle time slotand realizes the transformation fromlabelcolision tocodecollsion.Basedon theoretical analysis and simulation experiment, this paper explores the performanceofthe systemthroughput rate,total time slot number and systemrecognitionrate under the algorithm. Experimental results show that when the frame length of $\mathrm { f s } { > } 2$ and OvSF code length $\mathrm { m } { > } 2$ ，and the tag number is greater than 2O0,the system throughput rate under OVSF-DFSA algorithm is mtimes thatof DFSA algorithm, and compared with DFSA,MS-DFSA and PIGDFSA algorithm,OVSF-DFSA algorithm has beter performance in the above performance.

Key words:RFID; parallel recognition; code division multiple access; OVSF-DFSA

# 0 引言

标签密集环境下的RFID系统中，阅读器与标签之间的通信会产生数据（标签）碰撞问题，影响系统的工作性能如识别率、效率等。多标签识别碰撞产生的本质原因是无线信道共享引起的冲突，因此，标签防碰撞算法的目的就是控制多个标签对无线信道的访问，从而降低标签之间的碰撞率。目前，解决无线信道共享冲突的技术主要有空分多址（SDMA）、频分多址（FDMA）、码分多址（CDMA）和时分多址（TDMA）四大类[1]。

在 RFID系统中，由于无源标签的低功耗、低存储能力等特点，其标签防碰撞算法主要采用TDMA技术。基于TDMA技术的算法主要有两类，即树型算法（确定性算法）[2:3]和 ALOHA 算法（随机性算法）[4]，因树型算法基于标签ID 的唯一性来选择标签进行通信，随着标签数量的急增，造成阅读器开销大，识别时间长等问题，难以适用于大容量密集标签RFID系统，而ALOHA算法因其简单易实现等优点而被采用。但是在ALOHA算法及其各种改进算法如帧时隙ALOHA(FSA)算法、动态帧时隙 ALOHA(DFSA)算法[5]及分组动态帧时隙 ALOHA(GDFSA)算法[6中,单个时隙内阅读器最多只能识别一个标签，导致系统的吞吐率较低。文献7提出改进的GDFSA 算法，使得系统的最大吞吐率稳定在$3 4 . 6 \% { \sim } 3 6 . 8 \%$ ；文献[8基于马尔可夫时隙状态模型，提出连续时隙预测机制和自适应散列方案，有效的减少无效时隙的出现，使得系统的吞吐率保持在 $60 \%$ 以上；进一步地，分组自适应分配时隙ALOHA(GAAS)算法中阅读器直接跳过空闲时隙和碰撞时隙，使得系统的吞吐率保持在 $71 \%$ 以上[9，但是上述文献仍未能突破单个时隙只能识别一个标签的局限性，故系统的吞吐率未能从根本上得到提升；文献[10I1]引入盲源分离技术，实现了单个时隙可并行识别多个标签的技术突破，如文献[I2I引入FastICA技术到GDFSA算法中提出了可并行识别的PIGDFSA算法，使得系统的吞吐稳定在 $9 2 \% { \sim } 9 7 . 3 \%$ ，但是上述算法对阅读器天线数目的要求较高。无线通信中，码分多址技术（CDMA）能够在同一时间内并行处理多个应答器，但受限于RFID系统中标签低功耗、低存储能力的限制难以单独应用，文献[13.14]提出了一种基于OVSF 正交可变扩频码的CDMA技术和DFSA协议相结合的可并行识别的DFSA-OCRFID系统，但是其采用Schoute算法估计待识别标签数，不能很好的适应标签数的动态变化。

由于硬件条件对扩频码长度 $m$ 以及通信带宽的限制，为此本文将正交可变扩频码分多址技术（CDMA）和动态帧时隙防碰撞协议（DFSA）相结合，因同一时隙内各个标签携带的扩频码不同，可实现阅读器在单个时隙内并行识别多个标签。通过预估待识别标签数，进一步地动态调整扩频码码长，不但兼顾了RFID系统的性能及复杂度，而且提高了系统的最大吞吐率、降低了系统识别时间、提高了系统的识别率。

# 1 OVSF-DFSA 算法描述

# 1.1 OVSF-DFSA系统

CDMA技术广泛的应用于各种无线通信应用中，可供多个标签在同一时间段内同时存取信息。为了降低传统ALOHA算法（DFSA）中多个标签在单一时隙内的碰撞概率，提高系统吞吐率和系统识别率，本文提出在UHFRFID系统中，将CDMA和TDMA技术相结合，既彻底消除了现行UHFRFID单信道体制的标签碰撞，又可以像DFSA协议中那样给每个标签分配一个时隙，而同一个时隙内的标签则以不同的OVSF扩频码来区分，本文将该系统称之为OVSF-DFSA系统。该系统主要分为下行扩展频谱正交编码链路（本文不做介绍）和上行扩展频谱正交并行应答链路（如图1所示），上行链路由下行链路提供时钟同步，标签由阅读器提供时钟同步。

# 1.2正交可变扩频因子（OVSF）码

在CDMA技术中，扩频码的选择影响系统的抗多址干扰能力，通常选择自相关性好的为随机序列(PN)作为扩频码，如MS 码[15]、Gold码[16]及OVSF码。Gold码无法对下行链路扩展频谱解扩，只适用于有源标签。OVSF码因其较好的正交性，其可变长性质可支持多速率的通信业务，被广泛的应用于CDMA系统。OVSF码可由Hadamard矩阵经递归法生成[17],具有树型结构，如图2所示。每一个OVSF由 $C _ { \mathrm { k , n } }$ 唯一标志，其中， $k$ 为所在层号， $n$ 为所在层位置号，码树上同一层的所有码都是相互正交的。每个码长 $m { = } 2 ^ { k }$ ，实际应用中取决于通信协议的选择和硬件资源的约束。系统只能在同层码树上分配OVSF码给每个应答器。

# 1.3OVSF-DFSA系统防碰撞原理及算法实例

在OVSF-DFSA 系统下行链路(阅读器到标签的通信过程，图1未给出)中，首先，阅读器首先发送一个包含初始化帧长fs、OVSF码长 $\mathbf { \nabla } m$ 的查询命令给标签，标签接收到阅读器查询命令，提取参数fs， $m$ ，从已预先建立好的OVSF码表库里随机选择一个OVSF 码对其ID 信息进行扩频调制。在OVSF-DFSA系统上行链路中，如图1所示。当阅读器接收到来自标签的响应时，需对其信号进行解码；继而阅读器依据标签发送的OVSF码长参数 $m$ ，通过在其OVSF码表树中查询，获取所有码长为 $m$ 的扩频码，再对其进行扩频解调，进而获取待识别标签的ID信息[15]。

![](images/1d5f16ab25cee81683874655e62290692a3fc4d00f7c996a850dea7ff4b17fcb.jpg)  
图1OVSF-DFSA系统上行链路结构框图Fig.1.Block diagram of OVSF-DFSA system uplink  
图3 CDMA-DFSA防碰撞算法实例  
Fig.3The example of the collision prevention algorithm of CDMA-DFSA

![](images/38bb014e67b3e96717ddb42140e79008b89913dee0209b5e6aec8bbb0a56195d.jpg)  
图2 OVSF码表树  
Fig. 2 OVSF code table tree

时隙码 Doun uuD S 成功识别时隙  
标签6 S S C碰撞时隙  
时隙号 5 5  
扩频码 0000 1-10- 日 空闲时隙  
标签7 图 图 一 (i=1.2.3···)  
时隙号 4  
扩频码 1111  
标签6 S  
时隙号 4  
扩频码 1-11-1 /  
标签7 S 1  
时隙号 2 1 1  
扩频码 1-11- 1-11-1 1.10-  
标签4 C C S  
时隙号 2 1 1  
扩频码 1-11- 1-11-1 1-10-1  
标签3 C C S  
时隙号 2 一 2 1  
扩频码 1-11- 1-11-  
标签2 □ 母  
时隙号  
扩频码 11-1-1 1 1  
标签1 S 一  
帧时隙号 12 12↑ 时间第一帧 第二帧第三帧(fs=8) (fs=5) (fs=3)

如图3所示，在OVSF-DFSA系统中阅读器对大容量密集标签识别，可能出现以下三种情况（初始化 $f \mathrm { s } { = } 8$ ， $\scriptstyle m = 4$ ）：

a)单个时隙内只有一个标签响应，如同DFSA协议一样，阅读器可成功识别该标签，如图2中时隙1。

同一个时隙内有 $n$ ( $n \geq 2$ ）个标签响应，当 $n$ 个标签所携带的OVSF码相同时，则发生码碰撞，未能成功识别，如图2中时隙2内标签2、3、4；当 $n$ 个标签所携带的OVSF码不同时，可被成功识别，如图2中时隙4内的标签6、7。

b)某时隙内无标签响应，即该时隙为空闲时隙，如图2中时隙3、6、7、8。

OVSF-CDMA算法突破了传统DFSA算法中单一时隙中只能识别一个标签的局限性，从而实现了标签碰撞到码碰撞的转变，若无码碰撞，单个时隙内可最多识别 $m$ 个标签，一帧内可最多识别 $m ^ { \mathrm { { f s } } }$ 个标签。一方面，当待识别标签数量 $N$ 及帧长fs一定时，OVSF码长 $m$ 越大，单一时隙内码碰撞的概率越小，即系统的吞吐率越高；另一方面，OVSF码长 $m$ 越大，系统占用的频率（信道）资源越多，对系统的硬件计算能力、存储容量的性能要求越高，通常 $m < 1 2 8$ 即可满足应用需求。

实际读取中，UHFRFID系统内待识别标签的数量是未知的且是变化，为了使得系统获得最佳吞吐率，帧长fs及OVSF码长 $\mathbf { \nabla } _ { m }$ 应实现动态调整。但是受限于RFID系统中标签的计算能力， $m$ 为一定值，而要求帧长 $f \mathrm { { s } }$ 能够依据待识别标签的数量实时动态调整。1）标签数量 $n$ 较大时，使用较大的帧长fs来提高系统的吞吐率U、降低系统开销、降低识别时间；2)标签数量 $n$ 较小时，使用较小的帧长 $f s$ 来提高系统的吞吐率E、减少系统总时隙数、降低识别时间。

# 1.4未识别标签数目n估计方法

CDMA-DFSA要求阅读器在开始新的一轮识别前，对识别区域内的未识别标签作出估计，从而动态的调整帧长，提高系统的信道利用率和吞吐率。目前常用的大容量密集标签数量估计方法有Schoute 算法、Vogt算法、Cha 算法及MAPP算法等。Vogt算法利用切比雪夫不等式来最小化实际统计结果$( c _ { 0 } , c _ { s } , c _ { c } )$ 和理论计算结果 $( a _ { \mathrm { o } } , a _ { \mathrm { s } } , a _ { \mathrm { c } } )$ 之间的差距，估计准确性较高，误差稳定，故本文采用Vogt算法对未识别标签进行估计。

$$
\varepsilon ( f s , c _ { \mathrm { 0 } } , c _ { \mathrm { s } } , c _ { \mathrm { c } } ) = \operatorname* { m i n } \left| { \binom { a _ { \mathrm { 0 } } } { a _ { \mathrm { s } } } } - \left( \begin{array} { l } { c _ { \mathrm { 0 } } } \\ { c _ { \mathrm { s } } } \\ { c _ { \mathrm { c } } } \end{array} \right)  \right|
$$

其中空闲时隙数 $a _ { 0 }$ 、成功时隙数 $a _ { \mathrm { s } }$ 、碰撞时隙数 $a _ { \mathrm { c } }$ 的期望值可由文献[914]易得，分别为

$$
a _ { 0 } = f s { \bullet } P _ { 0 } = f s \biggl ( 1 { - } \frac { 1 } { f s } \biggr ) ^ { n }
$$

$$
a _ { \mathrm { s } } = f s \bullet P _ { \boldsymbol { k } } = f s \times { \boldsymbol { k } } { \left( 1 - \frac { 1 } { m } \right) } ^ { \boldsymbol { k - 1 } } C _ { n } ^ { \boldsymbol { k } } { \left( \frac { 1 } { f s } \right) } ^ { \boldsymbol { k } } { \left( 1 - \frac { 1 } { f s } \right) } ^ { n - { \boldsymbol { k } } }
$$

$$
a _ { \mathrm { c } } = f s { \bullet } ( 1 - P _ { \mathrm { 0 } } - P _ { \mathrm { \ell } } ) = f s - a _ { \mathrm { 0 } } - a _ { \mathrm { s } }
$$

# 2 OVSF-DFSA 算法步骤

在ISO/IEC18006-6协议下，基于CDMA技术的可并行识别多个标签的OVSF-DFSA防碰撞算法具体步骤如下：

a）阅读器发送查询命令"Query”（包含帧长参数： $f \mathrm { s }$ OVSF码长参数： $\mathbf { \nabla } _ { m }$ 。)给进入识别范围内的所有待标签，开始盘存周期，标签进入就绪状态。

b）标签接收到阅读器查询命令"Query"后，提取参数fs,$\mathbf { \nabla } _ { m }$ 。每个标签首先随机生成一个时隙号Si（ $\boldsymbol { S } \boldsymbol { i } \in$ [1,fs]），存入时隙计数器 Sc中。

c）阅读器发送确认命令“ACK"给进入就绪状态的标签。时隙计数器 $\scriptstyle \mathbf { S c = 0 }$ 的所有标签响应，并且随机生产一个码索引号 $R$ （ $R \in [ 1 , m ]$ ），用于从已预先建立好的OVSF码表中选择一个相对应的OVSF码。每个标签使用随机选择的OVSF码对其ID数据信息进行扩频调制，然后再发送给阅读器。

d）阅读器接收到响应标签的信号，对其进行解码，发生码碰撞的标签跳转至步骤c），等待下一轮识别；没有发生码碰撞的标签，阅读器对其调制信号进行扩频解调，获取其ID 信息。该轮识别完以后，阅读器统计空闲时隙数 $a _ { 0 }$ 、成功时隙数 $a _ { \mathrm { s } }$ 、碰撞时隙数 $a _ { \mathrm { c } }$ ，以便对未识别标签数量进行预估，继而调整帧长fs。

e)阅读器开始新的一轮识别，发送查询命令"QueryRep",未识别的标签时隙计数器Sc-1，跳转步骤3），直至所有的标签识别完。

# 3 OVSF-DFSA算法性能分析与验证

# 3.1理论推导

在RFID系统中，系统的吞吐率(吞吐量)是指被成功识别的标签数目与帧长度的比值[9，即一个时隙内成功识别标签数量的期望值，是反映系统防碰撞算法性能的重要参数。OVSF-DFSA算法中因一个时隙可以识别多个标签，故其系统吞吐率的计算较为复杂。假定RFID系统内待识别标签的数目为 $N$ ，OVSF扩频码码长为 $m$ （即有 $\mathbf { \nabla } m$ 个不同的OVSF码），单个时隙内有 $n$ 个标签被分配到不同的OVSF码的概率为

$$
P ( n , m ) = \frac { C _ { m } ^ { 1 } ( m - 1 ) ^ { n - 1 } } { m ^ { n } } = \left( 1 - \frac { 1 } { m } \right) ^ { n - 1 }
$$

由DFSA协议可知， $n$ 个标签选择同一个时隙的概率为

$$
P _ { \mathrm { m } } ( N , f s , n ) = C _ { N } ^ { n } \times \left( \frac { 1 } { f s } \right) ^ { n } \times \left( 1 - \frac { 1 } { f s } \right) ^ { N - n } = \frac { N } { f s } \left( 1 - \frac { 1 } { f s } \right) ^ { N - n }
$$

结合式（5）（6）可知 $n$ 个标签被成功识别的概率为

$$
P _ { n } = P ( n , m ) { \bullet P } _ { m } ( N , f s , n )
$$

任意一个时隙内，阅读器可最多识别 $\mathrm { m i n } ( m , N )$ 个标签，则OVSF-DFSA算法的系统吞吐量期望值为

$$
E ( N , L , m ) = \sum _ { n = 1 } ^ { \mathrm { m i n } ( m , N ) } n P = \sum _ { n = 1 } ^ { \mathrm { m i n } ( m , N ) } n \bigg ( 1 - \frac { 1 } { m } \bigg ) ^ { n - 1 } C _ { N } ^ { n } \bigg ( \frac { 1 } { f s } \bigg ) ^ { n } \bigg ( 1 - \frac { 1 } { f s } \bigg ) ^ { N - n }
$$

a)当 $m { = } 1$ 时，式（8）可化简为（此处 $0 \ d m \times 0$ 的值定义为1)

$$
E ( N , L , 1 ) = \frac { N } { f s } \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 }
$$

对式（9）关于 $\mathbf { N }$ 求导可得

$$
\begin{array} { l } { \displaystyle \frac { d E ( N , L , 1 ) } { d N } = \displaystyle \frac { 1 } { f s } \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 } + \frac { N } { f s } \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 } \ln \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 } } \\ { \displaystyle = \frac { N } { f s } \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 } \Biggl [ 1 + N \ln \Biggl ( 1 - \frac { 1 } { f s } \Biggr ) ^ { N - 1 } \Biggr ] } \end{array}
$$

$\frac { d { \cal E } ( N , L , 1 ) } { d N } = 0$ 2=0，解得N $N = \left[ - { \frac { 1 } { \ln ( 1 - 1 / f s ) } } \right]$ 即有最佳帧长度$f s = \left( 1 - e ^ { - 1 / N } \right) ^ { - 1 }$ 。当密集标签数量 $N$ 趋于无穷大时，$f s \approx \frac { 1 + 1 / N } { 1 + 1 / ( N - 1 ) } = N + 1$ ，取 $N = f s$ ，此时系统的吞吐量最大值为

$$
\operatorname* { l i m } _ { n = \infty } E ( N , L , 1 ) = \operatorname* { l i m } _ { n = \infty } \left( 1 - { \frac { 1 } { f s } } \right) ^ { n - 1 } = e ^ { - 1 } = 0 . 3 6 8 1
$$

易得此时该算法即为典型的DFSA算法。

b)当 $\scriptstyle m = 2$ 时，式（8）可化简为

$$
\begin{array} { l } { \displaystyle { E ( N , L , 2 ) = \sum _ { n = 1 } ^ { \operatorname* { m i n } ( m , N ) } n P } } \\ { = \sum _ { n = 1 } ^ { \operatorname* { m i n } ( m , N ) } n \bigg ( \displaystyle \frac { k } { 2 } \bigg ) \bigg ( 1 - \frac { 1 } { 2 } \bigg ) ^ { n - 1 } C _ { N } ^ { n } \bigg ( \displaystyle \frac { 1 } { f s } \bigg ) ^ { n } \bigg ( 1 - \frac { 1 } { f s } \bigg ) ^ { N - n } } \end{array}
$$

对式（12）关于 $N$ 求导可得：

$$
\begin{array} { l } { \displaystyle \frac { d E ( N , L , 2 ) } { d N } = \sum _ { n = 1 } ^ { \operatorname* { m i n } ( \mathbf { m } , N ) } \frac { n C _ { N } ^ { n } \left( 1 - \frac { 1 } { f s } \right) ^ { N - n } \left( 1 - \frac { 1 } { m } \right) ^ { n - 1 } } { f s ^ { n } } } \\ { \displaystyle \times \left[ \sum _ { i = N - n + 1 } ^ { 1 } \frac { 1 } { i } + \ln ( 1 - \frac { 1 } { f s } ) \right] } \end{array}
$$

令式(13)等于0，化简后可得

$$
\begin{array} { l } { { \displaystyle N ^ { 2 } ( m - 1 ) \ln ( 1 - \frac { 1 } { f s } ) + \Biggl [ ( m L - 2 K + 1 ) \ln ( 1 - \frac { 1 } { f s } ) + 2 ( m - 1 ) \Biggr ] N } } \\ { { \displaystyle + ( m L - 2 m + 1 ) = 0 } } \end{array}
$$

由上式得到 $\mathbf { N }$ 的一个正数解为：

$$
\begin{array} { c } { { N ^ { + } = \displaystyle \frac { 1 } { - 2 ( m - 1 ) \ln ( 1 - \displaystyle \frac { 1 } { f s } ) } \times } } \\ { { { } } } \\ { { \left[ ( m L - 2 m + 1 ) \ln ( 1 - \displaystyle \frac { 1 } { f s } ) + 2 ( m - 1 ) + \displaystyle \right. } } \\ { { { \left. \left[ ( m L - 2 m + 1 ) ^ { 2 } \ln ^ { 2 } ( 1 - \displaystyle \frac { 1 } { f s } ) + [ 2 ( m - 1 ) ] ^ { 2 } \right] \right. } } } \end{array}
$$

进一步地,

$$
\operatorname* { l i m } _ { L  \infty } N ^ { + } = \frac { \sqrt { 5 } + 1 } { 2 } L
$$

$$
\operatorname* { l i m } _ { n = \infty } E ( N , L , 2 ) = ( \sqrt { 5 } + 2 ) e ^ { \frac { \sqrt { 5 } + 1 } { 2 } } \approx 0 . 8 4 0
$$

c)当 $m { > } 2$ 时, $E ( N , L , m )$ 计算比较复杂。本文假定 $f \mathrm { s } { > } 2$ 则式（8）可以化简为

$$
E ( N , L , m ) = \frac { N } { f s } ( 1 - \frac { 1 } { f s \bullet m } ) ^ { N - 1 }
$$

由式（9）观察易得，式（18）偏导数的零点为 $N = m \bullet f s$ ，此时系统吞吐量的最大值为

$$
\operatorname* { l i m } _ { N = \infty } E ( N , L , m ) = \operatorname* { l i m } _ { N = \infty } \frac { N } { f s } ( 1 - \frac { 1 } { f s \bullet m } ) ^ { N - 1 } = m e ^ { - 1 }
$$

即OVSF-DFSA算法中的系统吞吐量的理论值约是经典DFSA算法的 $m$ 倍。

# 3.2仿真结果与分析

为了分析CDMA-DFSA算法的性能，将之与经典DFSA算法、MS-DFSA算法及PIGDFSA算法就系统吞吐量、阅读器总时隙数及系统识别率等方面做比较。仿真实验在Windows7操作系统下利用MATLAB2014软件平台上完成[18],其中电脑硬件配置为：CPU为i5-4590处理器，主频为3.30GHz，内存为4GB，64位。

# 3.2.1系统吞吐量仿真结果与分析

结合上节理论分析式（8）及式（9）(17)(19）可得系统吞吐量最大值 $N = m \bullet f s$ 与帧长fs及OVSF码长 $\mathbf { \nabla } _ { m }$ 之间的变化关系，如图4所示。在理论计算中，fs依次取{2s，（ $\mathrm { s } { = } 2 , 3 , . . . , 1 0 \$ } $m$ 依次取{2k，（ $\scriptstyle \mathbf { k = } 0 , 1 , \dotsc , 7 )$ }。当 $f \mathrm { { s } }$ 为定值时， $E _ { \operatorname* { m a x } } ( N , L , m )$ 随 $m$ 的增大而增大；当 $m$ 为定值（除 $m { = } 1$ 外），$E _ { \operatorname* { m a x } } ( N , L , m )$ 随 $f \mathrm { { s } }$ 的增大而减小。当 $m = 1$ 时，由上述分析可知，此时OVSF-DFSA算法退化为经典DFSA算法，进一步地由式（7）（9）可知， $E _ { \operatorname* { m a x } } ( N , L , m )$ 稳定在0.3681；当 $\scriptstyle { m = 1 2 8 }$ 时，$E _ { \mathrm { m a x } } ( N , 1 0 2 4 , m ) = 4 7 . 1 3 4 6$ ，而 $E ( N , 4 , m ) = 0 . 9 9 2 2$ ，系统吞吐量骤降，原因在于标签 $N \in [ 1 , 1 0 2 4 ]$ 时，而帧长fs却有1024，即随机分配到每个时隙的标签数量很少，这种情况下不足以体现出OVSF-DFSA算法中码碰撞代替标签碰撞的优势。在实际应用中，受限于硬件资源约束， $m$ 设置为32，已足以满足应用需求了。

仿真实验中，阅读器初始化帧长设置为： $f \mathrm { s } { = } 8$ 。其中，OVSF-DFSA 算法中OVSF码长 $\scriptstyle { m = 3 2 }$ ；MS-DFSA算法中M码长 $\scriptstyle { m = 3 2 }$ ；PIGDFSA算法中天线数 $\scriptstyle m = 8$ 。实验中，将标签设置为均匀分布，标签数初始化值为20，然后从50变化到1000，步进值为50，即标签数增加50，计算一次系统的吞吐量，如图5所示。当待识别标签数量大于200时，GDFSA算法的吞吐量为0.354，接近于理论极限值0.3681，但难以突破1，原因在于经典的DFSA 算法中，单一时隙最多只能识别一个标签；PIGDFSA算法基于盲源分离技术可在单个时隙内最多并行识别 $m$ 个标签，但是受限于天线数量 $m$ 的限制(通常 $m \leq 8$ ），PIGDFSA算法的吞吐量在2.53\~4.47之间，且波动性较大；M-DFSA算法和OVSF-DFSA算法基于CDMA技术，在标签数量大于200 时，系统吞吐量稳定，且OVSF-DFSA算法的吞吐量（11.262）是SM-DFSA算法的吞吐量（2.238）的5.03倍；是经典DFSA算法吞吐量（0.354）的31.81倍，接近理论推导值（ $\scriptstyle { m = 3 2 }$ 倍）。

![](images/7bbadb63ad7126afbe523b5aba9b1c3a8f3ee8cd6c2cd6bb0ed39414e13d8357.jpg)  
图4系统吞吐量最大值随帧长fs和码长 $\mathrm { ~ m ~ }$ 的变化 Fig.4The maximum system throughput varies with frame length $f \mathrm { { s } }$ and code length m

![](images/6f8833075e4dbdbb1f906b8ef55768d1ad150c08e5017d927a071a4024e18569.jpg)  
图5系统吞吐量仿真  
Fig.5System throughput simulation

# 3.2.2总时隙数仿真结果与分析

总时隙数即为阅读器识别完所有待识别标签所需的空闲时隙数 $a _ { 0 }$ 、成功时隙数 $a _ { \mathrm { s } }$ 、碰撞时隙数 $a _ { \mathrm { c } }$ 之和，其与系统的吞吐率成反比，故能够反映出系统的性能。实验中， $m$ 依次取{2k，（ $\scriptstyle \mathbf { k = 0 , 1 , \ldots , 7 } )$ }；标签数从50变化到1000，步进值为50，即标签数增加50，阅读器统计一次总时隙数，如图6所示。当 $\scriptstyle m = 1$ 时，即经典的DFSA算法，识别完所有标签所需的时隙数为3140；当 $\scriptstyle m = 2$ 时，该值为1627，识别时间减少了 $4 8 . 1 8 \%$ 当 $\scriptstyle { m = 1 2 8 }$ 时，该值为2850，识别时间减少了 $9 0 . 7 6 \%$ ，得益于单个时隙内,该算法可识别 $\mathbf { m }$ 个标签，降低了单轮识别过程中标签碰撞的概率。图7表明当待识别标签数目达到1000时，DFSA，MS-DFSA，PIGDFSA（ $\scriptstyle . m = 8$ ）及OVSF-DFSA（ $\scriptstyle { m = 3 2 }$ ）算法下系统识别完所有标签所需的时隙数分别为3140、1015、820、515,即OVSF-DFSA算法较DFSA，MS-DFSA，PIGDFSA算法在系统总时隙数上分别减少 $51 0 \%$ 、 $9 7 . 1 \%$ 和 $5 9 . 2 \%$ 。从图7中不难发现，当 $m$ 一定时， $N$ 越大，OVSF-DFSA算法的优势越明显。

![](images/0b0645b19a5907b379849ad682d9ccda8dd36935f837d53e59600ee5d8f2d76d.jpg)  
图6总时隙数随OVSF码长 $\mathrm { ~ m ~ }$ 的变化

![](images/994b76bb8d42266e6a5c4cbb681da23b09c7964121d165dd30028b1567ca2080.jpg)  
Fig.6Change of total time slots with the length $m$ of OVSF   
图7各算法下的系统总时隙数仿真比较

# 3.2.3系统识别率仿真结果与分析

系统的识别率（亦称算法效率），反映了阅读器每轮识别中可以成功识别的标签数量与系统总时隙数的比值。实验中，标签数从5变化到100，步进值为5，即标签数增加5，计算一次系统的识别率，如图8所示。当标签数 $N { = } 1 0 0$ 时，DFSA、PIGDFSA、OVSF-DFSA（ $\scriptstyle { \cdot } m = 3 2$ ）算法的识别率分别为0.15、0.32、0.42，性能分别提高了 $1 8 0 \%$ 、 $3 1 . 2 5 \%$ ，原因在于经典的DFSA算法只允许阅读器在单一时隙内识别一个标签，故算法识别率较低；此处PIGDFSA算法中，阅读器天线数目为8，可并行识别多个标签，故系统识别率有所提高；OVSF-DFSA算法理论上单个时隙内可最多识别32个标签，如前文所述，由于此处标签数量仅为100，阅读器识别过程中，分配到单个时隙内的标签数较少，不足以体现该算法的优势，故系统识别率提高的不太明显。

![](images/a6e9bd1c8f8a9ac07598997d57e1ac885e93d8f87092c772073677da860dca6c.jpg)  
Fig.7Simulation comparison of the total time slots of the system under each algorithm   
图8系统识别率仿真  
Fig.8Simulation of system recognition rate

# 4 结束语

在ISO/IEC18000-6国际标准下，本文提出的CDMA-DFSA算法基于OVSF扩频码的CDMA技术与DFSA协议相结合，实现了单一时隙内对多个标签的识别，实现了标签碰撞到码碰撞的转变。仿真实验结果表明，当帧长 $f \mathrm { s } { > } 2$ 且OVSF 码长 $m { > } 2$ 时，较经典DFSA 算法，OVSF-DFSA算法在系统吞吐量上提高了 $\mathbf { \nabla } m$ 倍；在系统总时隙数及系统识别率等性能上较其他算法均有所提高。但是阅读器一个帧长内仍然存在碰撞时隙和空时时隙，下一步工作将结合自适应分配时隙原则来跳过碰撞时隙和空闲时隙进一步的提高系统的吞吐率。

# 参考文献：

[1]苏健．大容量多标签防碰撞射频识别技术研究[D].成都：电子科 技大学，2O16.(Su Jian．Research on high-capacity multi-label anti-collision radio frequency identification technology [D]. Chengdu: University of Electronic Science and Technology,2016.)   
[2]史露强，何怡刚，罗旗舞，等.改进的混合查寻树 RFID 防碰撞算法 [J]．电子测量与仪器学报,2017,31(8):1281-1288.(Shi Luqiang,He Yigang,Luo Qiwu,et al.Improved hybrid query tree anti-collision algorithm of RFID [J]．Journal of Electronic Measurement and Instrument, 2017,31(8): 1281-1288.)   
[3]张小红，周伟辉．动态帧时隙的二进制树 RFID 防碰撞算法研究[J]. 系统仿真学报，2018(3):1063-1073.(Zhang Xiaohong,Zhou Weihui. Research on dynamic frame binary tree anti-collision algorithm for RFID system [J]. Journal of System Simulation,2018(3):1063-1073.）   
[4]Lee S R, Joo S D,Lee C W. An enhanced dynamic framed slotted ALOHA algorithm forRFIDtag identification[C]//Procof International Conferenceon Mobile and UbiquitousSystems: NETWORKING and Services.Piscataway，NJ:IEEE Press，2005: 166-174.   
[5] Chen Wentzu.Optimal frame length analysis and an efficient anti-collision algorithm with early adjustment of frame length for RFID systems[J].IEEE Trans on Vehicular Technology，2016,65(5): 3342-3348.   
[6]尹君，何怡刚，李兵，等．基于分组动态帧时隙的 RFID 防碰撞算法 [J]．计算机工程,2009,35(20): 267-269.(Yin Jun,He Yigang,Li Bing, et al.RFID anti-collision algorithm based on grouping dynamic frame sloted [J].Computer Engineering,2009,35(20): 267-269.)   
[7]庞宇，彭琦，林金朝，等．基于分组动态帧时隙的射频识别防碰撞算 法[J]．物理学报，2013,62(14):488-495.(Pang Yu,Peng Qi,Lin Jinchao,et al.Reducing tag collision in radio frequency identification systems by using a grouped dynamic frame slotted ALOHA algorithm [J].Acta Phys. Sin.,2013,62 (14): 488-495.)   
[8]付钰，钱志鸿，孟婕，等．基于连续时隙预测的帧时隙Aloha 防碰撞 算法[J].电子学报,2016,44(9):2081-2086.(Fu Wei,Qian Zhihong, Meng Wei,et al.FSA anti-collision algorithm based on continuous slot prediction[J].Chinese Journal of Electronics,2016,44(9):2081-2086.)   
[9]张小红，胡应梦.分组自适应分配时隙的 RFID 防碰撞算法研究[J]. 电子学报,2016,44(6):1328-1335.(Zhang Xiaohong,Hu Yingmeng. Research on a grouped adaptive allocating slot anti-collision algorithm in rfid system [J].Chinese Journal of Electronics，2016,44(6): 1328-1335.)   
[10]张小红，穆宇超．盲分离的帧时隙超高频 RFID 系统防碰撞算法[J].

计算机工程与科学，2015，37(3):559-565.(Zhang Xiaohong，Mu

Yuchao．Anti-collision algorithm for UHF RFID systems on blind separation and framed-slot [J].Computer Engineering and Science, 2015,37(3): 559-565.)   
[11]栗华，贾智平，王洪君，等．基于动态位隙分组盲分离的UHFRFID 防碰撞算法 [J].通信学报,2012,33(4):47-53.(LI Hua,Jia Zhiping, WANG Hongjun,et al.UHF RFID anti-collision algorithm based on blind separation and dynamic bit-slot grouping [J].Transactions of Communications,2012,33(4):47-53.)   
[12]袁莉芬，杜余庆，何怡刚，等．可并行识别的分组动态帧时隙 ALOHA标签防碰撞算法[J]．电子与信息学报，2018(4):944-950. (Yuan Lifen,Du Yuqing,He Yigang，et al.Grouped dynamic frame slotted aloha tag anti-collision algorithm based on parallelizable identification [J].Journal of Electronics & Information Technology, 2018(4): 944-950.)   
[13]Wang Bisheng，Yang Dongkai,Zhang Qishan.Efficient identification UHF RFID system scheme based on combination of DFSA and OVSF-CDMA[J].IEICE Electronics Express,2008,5(22): 954-961.   
[14]王必胜，张其善．可并行识别的超高频RFID系统防碰撞性能研究 [J]．通信学报，2009,30(6):108-113.(Wang Bisheng,Zhang Qishan. Study of anti-collision performance in parallelizable identification UHF RFID system [J].Trans of Communications,2009,30(6):108-113.)   
[15] Mutti C,Floerkemeier C.CDMA-based RFID systems in dense scenarios: concepts and challenges [C]//Proc of IEEE International Conference on RFID.Piscataway,NJ:IEEE Press 2008:215-222.   
[16]张雷，张青，杨恒新．基于CDMA和动态时隙ALOHA的UHFRFID 防碰撞研究[J]．现代电子技术，2012,35(24):101-104.(Zhang Lei, Zhang Qing,Yang Hengxin.Anti-collision performance in UHF RFID based on CDMA and dynamic slotted ALOHA[J].Modern Electronic Technol0gy,2012,35(24):101-104.)   
[17]Adachi F,Sawahashi M,Okawa K.Tree-structured generation of orthogonal spreading codes with different lengths for forward link of DS-CDMA mobile radio [J].Electronics Letters,1997,33(1): 27-28.   
[18]刘美玲.基于MATLAB环境下信道地址码 (OVSF码)的研究与功能 仿真[D]．大连：大连海事大学，2009.(Liu Meiling.Research and functional simulation of channel address code(OVSF code) based on MATLAB environment [D]. Dalian:Dalian Maritime University, 2009.)