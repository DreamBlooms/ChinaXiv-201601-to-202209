# 面向高密度Wi-Fi部署环境下的抗干扰策略

贺泽宇，张伟

(北京信息科技大学 计算机学院，北京 100101)

摘要：高密度Wi-Fi部署环境如银行、写字楼、mall等，普遍存在的同质干扰问题是制约用户体验及网络质量提升的痛点。首先，针对该问题研究了干扰检测技术并提出一种识别和度量Wi-Fi节点干扰的干扰程度评估模型。随后提出了“容忍 $^ +$ 避让”的抗干扰策略，容忍策略基于捕获效应理论及无线资源管理技术，提升了干扰条件下数据通信质量；避让策略采用局部化信道自协调算法和去中心分布式架构，解决同质干扰中的冲突问题。最后，实现了抗干扰机制WifiAAS。测试结果表明，该机制可提升 $10 \%$ 设备性能，且未带来过大开销。

关键词：无线局域网；抗干扰；信道分配；干扰评估模型；去中心分布式架构中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2017.08.0726

# Anti-interference for high density Wi-Fi deployment environment

He Zeyu, Zhang Wei (Computer School,Beijing Information Science & Technology University,Beijing 100101, China)

Abstract:Thesignal interferenceprobleithisig-densityeploymentofW-Filikanks,ice,allitisteinoint restrictsserexperienceandetworkquality.Firstly,studedtheterferencedetectiontechnolog,andproposinganiterferce level evaluationmodeltorecognizeand measurethe interferenceofWi-Finodes.Then,putforwardthestrategyof"tolerance &avoidance"and the tolerancepolicybasesonthe capture effect theoryand wirelessresource management technology.It improved thequalityofdata communicationunder interferencecondition.Thecollsion avoidance strategyadopted the local channel self-coordinationalgorithmand thedecentralized distributedarchitecturetosolve theconflict problem inthe homogeneous interference.Finaly,itimplementedthe mechanism WifiAAS.Testresultsshow itcanimprovethe performance of $10 \%$ and not too expenses.

Key Words: WLAN; anti-jamming;channel allcation; interference assessment model; distributed architecture

# 0 引言

无线局域网是公共场所用户接入网络的重要方式，无线Wi-Fi网络服务被业界默认为酒店、购物中心、娱乐中心等人员流量密度较高场所的配套服务[I]。随着公共空间Wi-Fi服务覆盖程度不断增长，提高无线局域网Wi-Fi设备的抗干扰能力已经成为一项重要课题[2\~51，特别是高密度Wi-Fi部署环境，同质干扰问题尤为突出。公共场所Wi-Fi实际部署的两种常见场景：a）如酒店、ktv、饭店等房型以10\~15平方米小隔间为主的场所，经营者为保证所有房间用户正常上网，通常为每个隔间都设置Wi-Fi节点；b）如大厅、剧院、运动场等空间范围 $4 0 0 \mathrm { m } ^ { 2 }$ 及以上场所，经营者同样会部署大量Wi-Fi设备来满足高密度的上网需求。因此，公共场所的无线局域网建设方案，一般具有网络规模大、节点密度高、局部负载重的特点。在高密度Wi-Fi部署环境下，同质干扰会严重影响无线局域网提供的网络服务质量，这不仅使用户上网体验变差还变相提高维护成本。

目前，对于同质干扰问题业，国内学者已经进行了许多相关研究。例如基于集中式wlan架构的无线局域网资源管控技术研究[67]、基于信道分配方法的抗干扰技术研究[8\~II以及干扰评估方法的相关技术研究[12.13]。这些研究非常具有前瞻性和创新性，但是并不能完全处理好高密度Wi-Fi部署环境下的同质干扰问题。首先，这种应用场景对扩展性要求高，然后随着无线网络节点规模的增长，同质干扰问题如邻近Wi-Fi设备的信道冲突现象频率剧增；此外，同质干扰情况受规模和密度影响,将变得更加复杂且难以准确评估；最后，用户聚集的公共场所对网络服务可靠性较为敏感但对同质干扰敏感度较低。因此，应避免导致Wi-Fi服务离线的操作，如信道重分配操作。

高密度Wi-Fi部署环境下的同质抗干扰策略面临以下两个挑战：a)wifi设备很难有条不紊的使用信道及其他网络资源。一方面，由于设备个体的信道分配策略在整个无线局域网络中具有盲目性，信道调整会引发多米诺骨牌效应，从而导致同质干扰问题更加严重。另一方面，由于无线局域网的规模大且需要灵活扩展，实现统一有序的管理是很困难的；管理大规模分布式集群需要复杂有效的调度机制，占用更多宝贵的带宽资源，并解决服务端节点的瓶颈问题。而这些要求反而会因成本问题限制无线局域网络的规模。b)Wi-Fi设备很难准确评估同质干扰及其网络影响。如图1所示，Wi-Fi设备受性能及基本结构限制，无法对外部环境进行准确的信号分析、频谱分析；此外，如Wi-Fi部署环境示意图2所示，在高密度环境下Wi-Fi设备处于信号覆盖边缘成为常态，且根据文献[14,15]可知设施内封闭的空间及墙体结构对信号造成反射、衍射、投射等消耗，这更增加了干扰程度评估的难度。综上所述，误差较高的干扰评估结果和盲目无序的抗干扰策略，无法有效地提升高密度Wi-Fi设备环境下的抗干扰能力。

![](images/670b04fddbef5277884631f28a4f308734ca8dba28b998953cee8a08b11b6a94.jpg)  
图1Wi-Fi设备的主板结构

![](images/ac6742bc438a4f49f045c700124c85549422b984809207343eda7d6129c81086.jpg)  
图2Wi-Fi部署环境示意图

针对高密度Wi-Fi部署环境下的同质干扰问题，本文的主要工作包括：a)提出了一个4D干扰程度评估模型(4dimensionalinterferenceassessmentmodel),即通过获取带宽损失、网络质量、设备负载、信道噪声四个纬度，使wifi设备可以更准确的评估复杂情况下的干扰程度；b）设计了一个增益最佳期望模型，使容忍抗干扰策略根据干扰程度，选用最优的性能资源调整计划；c）改进一致性hash 算法用于协调信道分配和结果同步，确保无线局域网中负载高的wifi设备获得优质信道，同时避让同频和邻频设备造成的强信号干扰；d)实现自主调整的抗干扰 机 WifiAAS(anti-interference with auto-regulatingstrategyforWi-Fi)。WifiAAS 依据4D干扰程度评估模型周期性检测外部信号干扰，并根据结果指标WINLR调度“容忍 $^ +$ 避让”抗干扰策略，提升Wi-Fi节点及局域网络的抗干扰能力。实际测试结果表明，在高密度wifi设备部署环境下，WifiAAS可以提升 $10 \%$ 设备性能，并使得无线网络服务更加稳定。

# 1 相关工作

目前在无线局域网同质干扰的度量、Wi-Fi信道分配及Wi-Fi抗干扰机制等方面已经有一些相关研究。

对于干扰情况下的无线网络性能表现，文献[16,17]阐述了采用SINR模型用于评估和约束无线局域网优化算法的相关成果。SINR是有用信号与干扰和噪声的比例模型，S表示有用信号的强度，I表示干扰信号的强度，N表示噪声信号的强度。SINR通过三个维度评估无线网络表现，但是并没有考虑wifi设备负载程度的影响。

文献[18]中何源等人将 $2 . 4 ~ \mathrm { G H z }$ 的同质干扰归纳为无线协议共存问题之一，并系统的阐述和分析了共存问题的成因、影响以及相关技术的研究进展。此外，他们还论述了同质干扰环境下三种共存技术思路，即避让、容忍、并发传输。避让共存技术通过多信道技术[19\~22]，从时间、频率的维度避免干扰。容忍共存技术通过应用捕获效应[23]增加对同质干扰的容忍能力，避免传输效率降低[24,25]。并发传输共存技术实质上是物理层多径效应的容忍现象，通过提升包接收率提高网络性能。

文献[26\~28]阐述了基于集中式wlan 架构实现无线网络资源统一管理的物联网技术研究。但wlan系统的接入控制器AC会成为限制规模和扩展性的瓶颈。另一方面，复杂的管控、通信、安全机制会占用宝贵的带宽资源，这对普遍存在于实际应用场景的4M、8M、 $1 0 \mathrm { { M } }$ 有线带宽是不可接受的。文献[29]提出了一个基于客户端驱动和冲突集着色的无线信道管理方法。虽然该方法可有效调解同质信道冲突，但对信道资源的管理使用依旧是无序的。

本文设计了一个4D干扰程度评估模型，相比于SINR，该模型将设备负载作为一个重要维度评估干扰影响，并依据Wi-Fi设备特点重新设计了噪声、有用信号、干扰的计算模型。此外，设计了增益期望模型，通过一组最佳的调整计划有序的调度性能资源，提升信号传输过程的容忍性。最后，改进了一致性hash算法，按资源权重以信道间隔逐轮递减的配对方式，完成信道资源的重分配，并同步各设备的分配结果，保证相邻Wi-Fi设备避让已占用的信道资源。

# 2 4D干扰程度评估模型

# 2.1高密度Wi-Fi部署环境下同质干扰问题分析

本节通过实验、调研的方式分析高密度Wi-Fi部署环境下的同质干扰问题。

首先，文献[30]中所提及的实验结果例证了Wi-Fi干扰与信道质量的关系。如图3所示，干扰条件下信道质量相差巨大，

且Wi-Fi速率越高信道的通信质量越差。文献[31]阐述了无线局域网wifi的性能评估方法，说明了丢包率、吞吐量、误码率、网络时延等指标与 Wi-Fi 性能及干扰程度存在关联；文献[32]阐述了使用PRR-SINR模型评估无线局域网信号干扰的方法，明确指出了包接收率PRR是衡量干扰程度的重要指标。

![](images/615e8a6d50dc6f8aeb74f1c8f50c6e967c1ebbc3adc89e93c493b703e725f50b.jpg)  
图3同质干扰下的信道质量

此外，通过实验分析同质信号干扰对Wi-Fi无线网络质量的影响及干扰特征。图4给出了邻近Wi-Fi设备共享信道资源时，设备优质连接数的统计结果和无线带宽损失程度的统计结果，其中优质连接是活动状态下能够至少占用 $1 5 0 \mathrm { ~ k ~ }$ 带宽的连接。可见，Wi-Fi负载能力受干扰影响，干扰越强负载能力越低，提供的网络服务越差。而且，无线带宽损失率与丢包率有很强的相关性，丢包率越高，带宽损失率的值越大。

![](images/ce232e2c20d2c3c8e344f5b3e4026e71b2adf327660f96f41b4d487ecf9e21ea.jpg)  
图4Wi-Fi干扰下的设备负载能力

分析结果表明：(1)不同信道的通信质量相差巨大，且同质干扰影响设备负载能力。当干扰程度越大，设备负载连接数越高时，Wi-Fi设备的无线网络服务质量越差，应使负载人数多的设备，获得质量更好的信道。(2)在高密度Wi-Fi部署环境下，当同质信号干扰越强时，Wi-Fi设备的无线带宽受干扰影响损失越大。此外，丢包率、误码率、网络时延和背景噪声都与同质干扰程度存在较强的关联。因此，本文提出一种Wi-Fi干扰程度评估模型，结合多个维度的指标来衡量高密度Wi-Fi部署环境下的同质干扰程度。

# 2.2干扰程度评估模型

由3.1节分析结论，干扰程度与带宽损失、网络质量、信号噪声及设备负载关联性强。为准确评估高密度Wi-Fi部署环境下的复杂同质干扰情况，干扰程度评估模型结合4个维度，即 4D 干扰程度评估模型(4 dimensional interference assessmentmodel)。

无线网络带宽相对于有线网络带宽的损失，可代表同质干扰造成网络性能损失，为了方便理解，本文将其定义为干扰损失。丢包率、误码率和网络延迟是评价网络通信质量的有效指标，本文使用这三个指标全面描述当前通信状态，为了方便理解将其定义为通信水平；Wi-Fi设备的负载连接数是动态的，且Wi-Fi设备最大负载能力受本身性能影响，本文将Wi-Fi设备当前负载连接数与设计指标中最大负载连接数的比值作为核心指标评价负载状态，为了方便理解将其定义为负载水平；场景噪声是影响干扰程度的重要指标，本文使用同频信道Wi-Fi信道强度的均值来描述背景噪声的强度，为了方便理解将其定义为噪声水平。

记 $U _ { w i r e d }$ 为以周期 $T _ { s }$ 采集的一组有线带宽(Mbps)所组成的向量。 $U _ { w i r e l e s s }$ 为以周期 $T _ { s }$ 采集的一组无线带宽(Mbps)所组成的向量。用 $| U _ { w i r e d }$ |表示所采集的有线带宽(Mbps)值的个数。用$| U _ { w i r e l e s s } |$ 表示所采集的无线带宽(Mbps)值的个数。

定义1干扰损失。 $\left| U _ { n u m } \right|$ 为周期 $T _ { s }$ 内采集的有效带宽数据的个数，则干扰损失为

$$
P = \sum _ { i = 1 } ^ { \left| { { U _ { n u m } } } \right| } { \frac { { { U _ { w i r e l e s s } } } } { { { U _ { w i r e d } } } } }
$$

记 $T _ { \mathit { d e l a y } }$ 为以周期 $T _ { s }$ 采集的一组网络时延所组成的向量，$\mid T _ { d e l a y }$ |表示所采集的网络时延数据的个数。 $U _ { b i t e r r }$ 为以周期 $T _ { s }$ 采集的误码率。 $U _ { l o s s }$ 为以周期 $T _ { s }$ 采集的丢包率。

定义2信号水平。 $C _ { d e l a y }$ 为网络延迟常量，代表最低可接受的网络延迟，单位为毫秒(ms)，则信号水平为

$$
F = U _ { b i t e r r } + U _ { l o s s } + \left[ \frac { \sum { T _ { d e l a y } } } { C _ { d e l a y } \times \left| T _ { d e l a y } \right| } \right] \times 2 0 \% \times \frac { \sum f \left( C _ { d e l a y } , T _ { d e l a y } \right) } { \left| T _ { d e l a y } \right| }
$$

$$
f \left( x , y \right) = { \left\{ \begin{array} { l l } { 1 , 2 x - y < 0 } \\ { 0 , 2 x - y \geq 0 } \end{array} \right. }
$$

记 $U _ { _ { c o n n } }$ 为以周期 $T _ { s }$ 采集的一组在线连接数所组成的向量，$| U _ { c o n n }$ |表示所采集的在线数据的个数。

定义3负载水平。 $C _ { c o n n }$ 为设备负载连接数上限，则负载水平为

$$
G = \frac { \sum { U _ { c o n n } } } { C _ { c o n n } { \times } | U _ { c o n n } | }
$$

定义4噪声水平。 $U _ { n o i s e }$ 为以周期 $T _ { s }$ 采集的一组噪声信号强度所组成的向量，单位为（ $\mathrm { \Delta } \mathrm { \ d B m }$ ）。 $U _ { s i n g a l }$ 为以周期 $T _ { s }$ 采集的一组设备信号强度所组成的向量，单位为（dBm）。用 $\mid U _ { \mathit { s i n g a l } } \mid$ 表示所采集的设备信号强度数据个数。用 $\left| U _ { n o i s e } \right|$ 表示所采集的噪声信号强度的个数。则噪声水平为

$$
N = \frac { \sum U _ { n o i s e } \times \left| U _ { n o i s e } \right| \times \left| U _ { s i n g a l } \right| } { \left| U _ { n o i s e } \right| \times \left[ \left( \left| U _ { n o i s e } \right| \times \sum U _ { s i n g a l } \right) + \left( \left| U _ { s i n g a l } \right| \times \sum U _ { n o i s e } \right) \right] }
$$

4D干扰程度评估模型的核心指标WINLR是无线网络质量与同质干扰影响的比，可以准确反映干扰环境的因果关系，WINLR为

$$
W I N L R = \frac { 1 - F } { P + N + G }
$$

# 3 “容忍 $+$ 避让”抗干扰策略

# 3.1容忍策略

容忍策略是一种提升信号传输容忍性的资源调度策略，它可以有序调整信号强度、频宽、设备负载三个Wi-Fi性能资源。本文设计了一个数学模型，并计算wifi资源调整后，WINLR增益的数学期望，为选择一组最佳的资源调度计划提供依据。

由于周期 $T _ { s }$ 内Wi-Fi设备所受到的同质干扰情况是不变的，可设此时的干扰程度为 $W I N L R _ { t m p }$ ，容忍策略调整后受到的干扰程度估计值为 $W I N L R _ { e \nu a l }$ ，则策略调整增益为

$$
\Delta W I N L R = W I N L R _ { e v a l } - W I N L R _ { t m p }
$$

容忍策略抗干扰模块包含信号强度调整、频宽调整和设备负载调整三部分，每部分策略彼此相互独立，设 $\Delta W I N L R _ { s i g n a l }$ 为信号强度调整获得的增益， $\Delta W I N L R _ { w i d t h }$ 为频宽调整获得的增益，$\Delta W I N L R _ { l o a d }$ 为负载上限调整获得的增益，则容忍策略获得的抗干扰增益数学期望可定义为

$$
E \big ( \Delta W I N L R \big ) =
$$

$$
P _ { s i g n a l } \Delta W I N L R _ { s i g n a l } + P _ { w i d t h } \Delta W I N L R _ { w i d t h } + P _ { l o a d } \Delta W I N L R _ { l o a d }
$$

其中： $P _ { s i g n a l } > P _ { w i d t h } > P _ { l o a d } ~ { \cal H } ~ P _ { s i g n a l } + P _ { w i d t h } + P _ { l o a d } = 1$

信号强度和频宽的可调整空间可表示为 $\left[ T m p , M a x \right]$ ，Max值为Wi-Fi设备额定性能指标而Tmp 值为当前值；如果设 $C _ { a c t }$ 为无线接入 $C o n n _ { i }$ 的网络用量 $U s e d _ { i }$ 的阈值，则不活跃连接构成的集合为 $U _ { s l e e p } = \left\{ \left( C o n n _ { i } , U s e d _ { i } \right) \left| U s e d _ { i } < C _ { a c t } \right. \right\}$ ， $\left| U _ { s l e e p } \right|$ 不活跃连接的数量，设备负载可调整空间可表示为 $\left[ 0 , \left| U _ { s l e e p } \right| \right]$ 。

因此，容忍策略可以定义为：设 $x$ 为信号强度， $y$ 为频宽，乙为设备负载，对于 $\forall x , \forall y \in \left[ T m p , M a x \right]$ ， $\forall z \in \Big [ 0 , \big | U _ { s l e e p } \Big | \Big ]$ ，都有 $E \left( \Delta W I N L R _ { 1 } \right) - E \left( \Delta W I N L R _ { 2 } \right) > 0$ ，则称 $E { \big ( } \Delta W I N L R _ { \mathrm { 1 } } { \big ) }$ 对应的一组 $\left( x , y , z \right)$ 为最佳性能资源调度计划即容忍策略。

# 3.2避让策略

避让策略改进了一致性hash算法，用于协调干扰空间内信道资源分配和结果同步。该策略使每一台参与信道分配的Wi-Fi 设备，都维护相同的一致性hash 环形空间即 $[ 0 , 2 ^ { 3 2 } - 1 ]$ 的环形数字空间如图5所示，这有效地避免了为同步分配结果时的复杂通信过程。

此外，对于信道资源和设备负载设置权重，使信道调整结果倾向于让工作负载越重的Wi-Fi设备获得更加优质的信道资源。如图6所示，可见避让策略按顺时针方向查找，并为Wi-Fi设备分配相应资源权重的优质信道。

![](images/4c9c5aba2ba6966a8714e3187a838b8584a695cbdb2f9e74c74da847f26ab885.jpg)  
图5一致性hash 环形空间

![](images/f21bed9169cc12ffb2aac2bfc71f6957870d3ffdfcccca10d07f53547129c583.jpg)  
图6信道分配实例图  
图7冲突协调实例图

避让策略恪守一种严格的冲突避让规则，相邻Wi-Fi设备在获得信道资源时必须保持安全的信道间距，信道的同频占用和邻频使用都被视为信道分配冲突。如图7所示，Wlan1与Wlan2为同频冲突，与Wlan3为邻频冲突，与相距两信道间隔Wlan4为合适信道分配结果。

11 1 =3 一 (wlan3 1 1 Wlan2 目 (p) Wlan4 二 二 二 Channel 6 Channel 7 Channel 8 Channel 9

# 4高密度Wi-Fi部署环境下的抗干扰机制WifiAAS

本章描述WifiAAS的设计与实现。高密度Wi-Fi部署环境下，无线局域网的主流拓扑结构如图8所示。这种无线局域网结构简单但规模大、节点密度高，每个节点都嵌入了WifiAAS。该机制包含通信模块、干扰检测模块、调度模块、容忍策略模块、避让策略模块五个部分，都以独立线程的方式运行，WifiAAS的整体架构如图9所示。

干扰检测模块负责周期性的监测Wi-Fi设备的WINLR指标（详述请见3.2节），并将状态信息提交给调度模块。调度模块是WifiAAS策略的主控核心，负责调度不同的策略模块提升Wi-Fi设备的抗干能力，以及调用通信模块与邻近的Wi-Fi设备沟通干扰状态。容忍策略模块和避让策略模块的活动是互斥的，根据状态信息触发，容忍策略模块是一种可动态调整的抗干扰手段，而避让策略模块倾向于高效能低频度调解干扰问题。

![](images/451621b305c13fcfc3c2c1e332a52040a5cae7a623a65ce41819a23689585e44.jpg)  
图8主流部署环境拓扑结构

![](images/61c49ccaed4f57dabed3129d1554107b3c0524a71ea7ac9e1b9b08c341863dfd.jpg)  
图9 WifiAAS机制架构

# 4.1WifiAAS 的干扰检测模块

本节介绍WifiAAS的干扰检测模块及策略调度模块的设计与流程。

WifiAAS借鉴文献[33]思想，但采用以Wi-Fi设备自我为中心的干扰分析模型和文献[34]中使用的包接收率PRR，计算通信范围及干扰指数计算方法。若高密度环境下无线局域网 $N _ { i }$ 中的 $\nu$ 节点受到邻居无线局域网 ${ N } _ { j }$ 节点 $u$ 同质同信道干扰，则邻居无线局域网 $N _ { _ j }$ 对 $\nu$ 产生的干扰指数为$I ( u , N _ { j } ) { = } | \{ \nu | \nu \in N _ { j } \land u \in D ( \nu , R _ { \nu } ^ { + } ) \} |$ ，那么其中 $D ( \nu , R _ { \nu } ^ { + } )$ 是以无线局域网 $N _ { i }$ 中的 $\nu$ 节点为干扰程度评估中心，以 $R _ { \nu } ^ { + }$ 为半径的圆形Wi-Fi信号覆盖范围。 $R _ { \nu } ^ { + } = \left( 1 + r \right) R _ { \nu }$ ， $r > 0$ ， $R _ { \nu }$ 为节点 $\nu$ 的有效通信半径。假设 $R _ { \nu } ^ { + }$ 范围内的节点均受到节点 $\nu$ 干扰， $R _ { \nu }$ 是包接收率PRR满足某一常量的空间区域。节点 $\nu$ 调用WifiAAS的通信模块广播 $X _ { _ { p r o b e } }$ 个Beacon 探针包，并将PRR大于等于 $X _ { p r o b e } ^ { - } / X _ { p r o b e }$ 的空间范围视为干扰可影响域。

由于无线局域网的同质干扰产生规律，符合空间局部性原理且节点间的干扰是相互的。因此，可以令 $N _ { j } = N _ { i }$ ，若设无线局域网 ${ N } _ { j }$ 代表局部干扰事件中全部受干扰节点构成的集合，其中节点总数为 $k$ ，则无线局域网 $N _ { _ j }$ 对节点 $\nu$ 产生的干扰指数为 $I ( u , N _ { j } ) = \mid \{ u \in ( \nu , R _ { \nu } ^ { + } ) \} \mid$ ，且整个无线局域网 $N _ { _ j }$ 所受到的同质信号干扰可以定义为

$$
I \left( N _ { j } \right) { = } \frac { \sum _ { u \in N _ { j } } I \left( u , N _ { j } \right) } { k }
$$

WifiAAS抗干扰策略调用干扰检测模块以Wi-Fi设备自身为中心，周期性的检测并统计WINLR指标。WINLR反映了Wi-Fi设备在周期 $T _ { s }$ 内受到的干扰情况，帮助调度模块灵活的使用容忍策略模块和避让策略模块。干扰检测及策略调度的具体流程如下：

a)干扰检测模块经过周期性检测发现WINLR指标超过某阈值 $W I N L R _ { t h r }$ 时，调度模块会把WINLR结果附加在探针数据包内向周边广播，变更设备状态为“受干扰”，并开始接收其他设备探针数据包。同时，策略调度模块还将启动容忍抗干扰策略改善设备当前同质干扰状况。

b)干扰检测模块根据周期内收集的其他受干扰影响wifi设备的WINLR指标，统计“受干扰”设备集合构成的无线局域网的同质信号干扰 $I ( N _ { j } )$ 。当检测发现 $I ( N _ { j } )$ 指标超过某阈值$W I N L R _ { a i r }$ 时，调度模块将停止使用容忍抗干扰策略，并将周期统计的内探针包归属名单及窗口约定加入数据包广播。

c策略调度模块解析并统计固定窗口期内收集的归属名单的交集作为避让机制协调对象名单提交给避让抗干扰策略模块。

# 4.2容忍策略抗干扰模块

本节介绍容忍策略抗干扰模块的核心工作流程，具体内容如下：

a)容忍策略模块启动后开始等待干扰检测模块的检测结果。当干扰检测模块的检测周期 $T _ { s }$ 结束时，容忍策略模块将周期$T _ { s + 1 }$ 作为策略增益估算周期，同时，将干扰检测模块 $T _ { s }$ 周期内的WINLR指标作为周期 $T _ { s + 1 }$ 内的 $W I N L R _ { { _ { t m p } } }$ 指标。

b)容忍策略模块在 $T _ { s + 1 }$ 周期收集策略的可调整空间，然后，根据分别估算各信号强度调整、频宽调整、设备负载调整三种策略在各自可调整空间下的抗干扰增益并代入抗干扰增益数学期望模型进行计算。

c)容忍策略模块将抗干扰增益数学期望最高的策略组合设置为可执行策略，并在周期 $T _ { s + 2 }$ 执行该策略。

# 4.3避让策略抗干扰模块

本节介绍避让策略抗干扰模块的算法设计。避让策略的信道资源权重和设备负载权重都为3级，信道资源闲置率排序前$30 \%$ 权重为3，其后 $50 \%$ 权重为2，最后 $20 \%$ 权重为1；负载率高于 $80 \%$ 的wifi设备权重为3，小于等于 $80 \%$ 但大于 $40 \%$ 设备权重2，低于 $40 \%$ 的设备权重为1。

算法1：信道自动协调分配算法

Yhash(device);}/\*for\*///计算设备在一致性hash 环形空间的位置3.for（j=current；j<len(list_channels);j++）{if(device_hash<=chanel_hash){if(device_weight>=chanel_ weight){list_result .append((device_id,chanel_id));}/\*if\*/}/\*if\*/}/\*for\*///在一致性hash 空间中从当前位置顺时针查找合适的信道，为负载重的设备分配资源权重高的信退4.if（Pairing failure）{for（j=0；j<len(list_channels);j++）{if(device_hash<=chanel_hash){if(device_weight>=chanel_ weight){list_result.append((device_id,chanel_id));}/\*if\*/}/\*if\*/}/\*for\*/}/\*if\*///如果分配失败，则从一致性hash 空间中的原点位置再次顺时针查找合适的信道

5.load(list_result)  
//加载全部完成信道分配的结果  
6.for（row in list_result）{if (device.channel-near_device.channel<=interval){return Ture;}/\*if\*/else{remove(conflict_channelid);goto 3 step;}/\*if\*/  
}/\*for\*/  
//遍历分配结果，如果临近设备信道间隔小于常量interval，则认为分配冲突；  
//从一致性hash 空间中移除冲突的信道节点，并返回第3步为设备重新分配信道；  
7.if (Conflict of coordination failure){interval $\mathbf { \sigma } = \mathbf { \sigma }$ interval -1;goto 6 step;  
}/\*if\*/  
//如果信道分配冲突协调失败，则减小信道间隔常量interval，并返回第6步重新  
8.return list_result;  
//返回最终信道分配结果

算法1采用一致性hash环形空间，使得全部参与信道分配的设备高度同调的获得一致的信道分配结果。这一思路有效的省去Wi-Fi设备间为同步分配结果的复杂通信过程和较长的通信周期，大幅降低了算法的收敛时间。此外，该算法还有力的

避免邻近信道造成的干扰，进一步提升信道分配的抗干扰效果。  
因篇幅有限本文省略该算法的具体说明。

# 5 WifiAAS性能评价

本章首先通过实际部署场景测试，检测WifiAAS策略的有效性，并通过与产品机Wi-Fi设备对比测实验证WifiAAS 的抗干扰性能；然后借助仿真实验测试高密度Wi-Fi部署环境下WifiAAS收敛性能表现。

# 5.1实际部署场景评测

本节通过实际部署测实验证WifiAAS策略的性能。测试地点位于富海大厦12层，房型结构与酒店包间、饭店隔间类似，在测试空间内可以检测到来自其他办公室的Wi-Fi信号，甚至可以检测到来自其他楼层的Wi-Fi信号，实际部署环境的信号状况如图10所示。测试空间是一个 $1 0 \mathrm { m } ^ { 2 }$ 大小的会议室，测试机wlan1通过lan口网线直连的方式与一台作为测试服务器的台式机相连，1台笔记本电脑及4部测试手机作为Wi-Fi设备负载，通过无线接入的方式使用测试机wlan1提供的网络服务。此外，在测试空间内还设置了一台没有安装WifiAAS策略的同款产品机wlan2。产品机wlan2以同样的方式与测试服务器和作为负载的移动设备相连。测试环境的网络拓扑结构如图11所示，测试环境相关实验参数如表1所示。

表1实验参数  

<html><body><table><tr><td>设备名称</td><td>测试机wlanl</td><td>产品机wlan2</td></tr><tr><td>操作系统</td><td>Openwrt</td><td>Openwrt</td></tr><tr><td>负载设备数</td><td>5台</td><td>5台</td></tr><tr><td>抗干扰机制</td><td>WifiAAS</td><td>无</td></tr></table></body></html>

已连接的网络：47_49427C  
信道：10 BSSID:d4:ee:07:49:42:7c192.168.199.156 18/5 72MbpsIP 2.4/5 GHZ 速度  
unTang.- F79525-383308.-35  
-40 B51-5250E8,-42HiWiFi_493D14,-48  
-50 54ceRodm,-57  
名称1-03,-6574  
-80  
-901234567891011121314

![](images/3108a06a456f4e0ab8cdb1ab49018d1452fc663ddef0e129b88367cfbc81e822.jpg)  
图10实际部署环境的信号状况  
图11网络拓扑结构

# 5.2 吞吐量分析

吞吐量是衡量网络通信质量的一个关键指标，本节着重分析同质信号干扰对Wi-Fi设备吞吐量的影响。这里吞吐量指的是端到端的吞吐量，即单位时间内，测试服务器收到的通过测试机wlan1转发的数据包平均数据量。

为了测试干扰对吞吐量的影响，使用Loadrunner工具进行吞吐量测试。图12(a)和(b)给出了实验组与对照组平均吞吐量的走势图。由图可知，在整个测试过程中测试机wlan1的吞吐量都要高于产品机wlan2的吞吐量，且随着时间的推移产品机wlan2的吞吐量走势越来越低。虽然测试机wlan1的吞吐量有不同幅度的波动，但基本稳定在高位。

![](images/c3134c4a5f6fda277f17da0a68816762286d12ea660b700fc7d3a2c26b358295.jpg)  
图12吞吐量走势图

图13(a)和(b)是强同质干扰下的吞吐量走势图。可见，实验组和对照组都产生了剧烈的波动。但测试机wlan1在WifiAAS的作用下维持一个稳中有升的无线网络吞吐量，而产品机wlan2在的吞吐量在剧烈震动之后，出现持续低迷的走势，特别是产品机wlan2出现了短时间的无线网络服务中断。此外，网络服务中断导致了Wi-Fi设备重启，产品机会随机选择新的信道，因此吞吐量会有个急剧上升的过程。

因此，可以得出结论：在Wi-Fi设备受到干扰时，WifiAAS策略可以有效的提高抗干扰能力，并显著的提升wifi的吞吐量即保护用户在干扰状态下的无线用网质量。

# 5.3开销分析

WifiAAS是一款开机自启动的后台进程，会占用Wi-Fi设备宝贵的内存、flash、CPU资源，此外，在信道协调的过程中，

# WifiAAS也会有一定的存储空间、通信开销。

![](images/0c2fff72bb005c074f6a88f73d282b8272a908ece75c6683259d8b022200ed84.jpg)  
图13强同质干扰下吞吐量走势图

(b)产品机wlan2吞吐量走势图

为了准确获得WifiAAS的通信状况，测试机wlan1上面安装了tcpdump 监听分析工具并统计每次信道调整平均通信包的总数。WifiAAS通信信息包括信道调整通知、收发的设备名单、干扰程度检测报告。WifiAAS的平均控制包数量为26.72个，而且统计的过程中随着被协调设备的增多控制包数量的数量也会成倍增加，可见在大规模组网的情况下，WifiAAS需要更加严格的控制通信机制，削减冗余的通信过程。然而，在真实的高密度Wi-Fi设备部署环境中，需要协调信道的干扰事件往往是局部的，而且经过统计发现，每天需要协调信道的情况并不多。所以，WifiAAS的通信开销是可接受的。

对于内存资源和CPU资源的用量问题，本文通过top日志分析和统计发现，WifiAAS对这两种资源的占用从未超过 $10 \%$ ，也不存在内存一直增长不释放的内存泄漏问题。此外，如图14所示，WifiAAS策略与固定信道分配机制FixChnl、跳频机制ARCH嵌入式程序部分存储用量的对比图。WifiAAS占用flashROM空间31.2KB，这比FixChnl、ARCH机制都要高出许多，但目前常用的Wi-Fi设备平台126KBRAM和16MflashROM，只要存储占用不超过1M 都是可以接受的。WifiAAS在经过UPX压缩后其可执行程序用量锐减至 $6 1 . 1 \%$ ，从而在无须牺牲性能的情况下，进一步降低FlashRom的资源占用情况。

# 5.4收敛性分析

当同质干扰发生时，WifiAAS的避让策略的信道协调算法，会协同无线局域网内所有受干扰设备进行一系列的信道分配、协调、切换操作，避让策略的时间收敛性也是衡量Wi-Fi抗干扰机制的一个重要指标。为了评鉴WifiAAS的收敛性能，分别部署三种高密度wifi部署环境的仿真场景，即4节点、8节点、10节点。然后，分别统计信道调整开始到全部受干扰节点信道切换完成的平均时间。

图15分别给出了三种仿真场景下20次Wi-Fi设备信道协调耗时的算数平均值。可以看出，随着场景中节点数目的增加，参与避让策略也节点增加了，同时导致了收敛时间延长。然而当无线局域网节点总数超过4个时，由于信号覆盖范围受空间限制，同质干扰具有空间局部性，参与避让策略的节点数自急剧减少，无线局域网避让策略的收敛时间徘徊在35s左右。以上结果表明，WifiAAS的信道避让策略具有良好的收敛性能，而且随着Wi-Fi局域网规模的增加不会导致收敛时间大幅延长。

![](images/c98728bc83677dc26376f63fd162888c400f0d0dcec240f1151dfe1ac42b9ef6.jpg)  
图14FlashRom资源占用对比

![](images/92d9ca72d80033983fe89cf78614d6f681a811db5bc9a51db601dacb49174190.jpg)  
图15收敛时间分析

# 6 结束语

针对高密度Wi-Fi部署环境下的同质干扰问题，本文提出了4D干扰程度评估模型和“容忍 $+$ 避让”抗干扰策略，并实现了一个抗干扰机制WifiAAS。WifiAAS首先通过干扰检测模块根据内置的4D干扰程度评估模型周期性的检测Wi-Fi设备的WINLR，并上报状态信息；然后，调度模块通过评估最大增益调整容忍策略来抵消干扰造成的网络影响；最后，局部无线局域网空间处于干扰状态时，调度模块通过基于分布式去中心架构的避让策略，实现信道资源有序合理的分配使用，让负载重的wifi设备获得更优质的信道资源，从而提升无线局域网在密度wifi部署环境下的抗干扰能力、无线网络表现和用户网络体验。

结果表明：a)WifiAAS能够根据Wi-Fi设备的负载程度提供与之相对应的优质信道资源，调解同质干扰问题，并提升吞吐量和上网表现；b）在相同干扰条件下，内置WifiAAS的Wi-Fi设备能够根据干扰程度有序的使用无线资源，拥有更好的上网表现和吞吐量；c)WifiAAS并未带来过大的通信、存储的消耗。因此，由WifiAAS的实验验证可知，本文提出的4D干扰程度评估模型和“容忍 $. +$ 避让”抗干扰策略是有效的。

“容忍 $+$ 避让”抗干扰策略对于Wi-Fi设备密集、规模庞大的室内无线局域网场景有较强的适用性，如大型会场、商圈、酒店等。但对于管控能力要求高、安全级别要求高的无线局域网，该策略的资源管理能力仍不完善。本文的下一步工作要将“容忍 $^ +$ 避让”抗干扰策略与自适应局域网的相关技术结合起来，进一步改进该策略，以满足自适应、智能化、感知网络的大数据物联网相关需求。

# 参考文献：

[1]陈小锋．商业无线Wi-Fi的发展前景和价值研究[J].无线互联科技， 2017,13:14-15   
[2]Jiang Haoran,Liu Bin, Chen Changwen.Performance analysis for zigBee under wifi interference in smart home [C]// Proc of IEEE International Conference Communications.2017.   
[3]Kosek-Szott, K, Gozdecki J, Loziak K, et al. Coexistence Issues in Future WiFi Networks [C]//Proc of IEEE Network.2017.   
[4]Sha M, Hackmann G,Lu C.ARCH: practical channel hopping for reliable home-area sensor networks [C]// Proc of Real-time & Embedded Technology & Applications Symposium.2011: 305-315.   
[5]Zhang Jianxin,Lei Xuemei. Anti-interference performance optimization of Zigbee system from shaping filter [C]// Proc of IEEE International Conference on Information and Automation.2015.   
[6]Li Yi, Zhang Xin, Yeung KL.A novel delayed wakeup scheme for efficient power management in infrastructure-based IEEE 802.11 WLANs [C]//Proc ofIEEE Wireless Communications and Networking Conference.2015.   
[7]杨慧然．高密度环境下Wi-Fi解决方案研究与设计 [D].成都：电子科 技大学,2016.   
[8]邓昌建，陈东义，张衡，等．工业无线网Krylov子空间估计与动态信道 选择[J].计算机工程与应用,2015,51(11):62-66.   
[9]柳毅，叶远航，凌捷．一种 WLAN 信道传输干扰预测方法[J].计算机 科学,2015,42 (10): 106-112.   
[10]张松．基于马尔可夫链的 ZigBee 信道选择算法的研究[D].上海：上 海海洋大学,2014.   
[11]朱俊杰．无线传感器网络信道分配算法与实验研究[D].杭州：浙江大 学,2015.   
[12]陈明．关于无线通信抗干扰技术的探索[J]．中国新通信,2017，19(4): 44-44.   
[13]张毅，吴锦，罗元，等．新型 ZigBee-WiFi 无线网关的设计及其抗干扰 技术的研究[J].计算机应用与软件,2014(5):122-124.   
[14]王召召．城市环境下通信信号穿透损耗的定量研究[D].郑州：郑州大 学,2010.   
[15] Missaoui R,Joumaa H,Ploix S,et al. Managing energy smart homes according to energy prices:analysis of a building energy management system[J]. Energy & Buildings,2014，71(3): 155-167.   
[16] Chen A,Cohen A,Haddad Y,et al.SINR diagram with interference cancellation [J].Ad hoc Networks,2017,54: 1-16.   
[17] Huang B,Yu J, Cheng X,et al. SINR based shortest link scheduling with oblivious power control in wireless networks [J]. Journal of Network & Computer Applications,2017,77: 64-72.   
[18]何源，郑霄龙.2.4GHz无线网络共存技术研究进展[J].计算机研究与 发展，2016，53(1):26-37.   
[19] Zhou G,Huang C,Yan T,et al. MMSN: multi-frequency media access control for wireless sensor networks [C]// Proc of Infocom IEEE International Conference on Computer Communications.2015:1-13.   
[20] Qureshi FF,Reliable AG B.Cognitive Radio multi-channel MAC protocol for Adhocnetwork [C]//ProcofInternational Conferenceon Communications.2015:1-6.   
[21] Jovanovic MD, Djordjevic G L. TFMAC: multi-channel MAC protocol for wireless sensor networks [C]// Proc of International Conference on Telecommunications in Modern Satellite.2007: 23-26.   
[22] Sha M,Hackmann G,Lu C.Real-world empirical studies on multi-channel reliability and spectrum usage for home-area sensor networks [J].IEEE Trans on Network & Service Management,2013,10(1):56-69.   
[23] Leentvaar K,Flint J.The capture effect in FM receivers [J].IEEE Trans on Communications,1976,24 (5): 531-539.   
[24] Ji X,He Y,Wang J,etal.Voice over the dins: improving wireless channel utilization with collision tolerance [C]// Proc of IEEE International Conference on Network Protocols.2013:1-10.   
[25] Boudour G,Heusse M.A duda improving performance and fairness in IEEE 802.15.4 networks with capture effect [C]//Proc of IEEE International Conference on Communications.2013:1683-1687.   
[26] Dely P,Vestin J，Kassler A，et al. CloudMAC:an OpenFlow based architecture for 802.11 MAC layer processing in the cloud [C]// Proc of Globecom Workshops.2012:186-191.   
[27] Ali-Ahmad H, Cicconetti C,Oliva A D L,et al.An SDN-based network architecture for extremely dense wireless networks [C]// Proc of Future Networks & Services.2013:1-7.   
[28]麻信洛，李晓中，葛长涛．无线局域网构建及应用[M].北京：国防工 业出版社,2009.   
[29]Mishra A,Brik V,Banerjee S,et al.A client-driven approach for channel management in wireless LANs [C]// Proc of Infocom IEEE International Conference on Computer Communications.20o6:1-12.   
[30]张招亮，陈海明，黄庭培，等．无线传感器网络中一种抗无线局域网干 扰的信道分配机制[J].计算机学报,2012,35(3):504-517.   
[31]陈树斌，张磊，杨盘龙．基于WiFi的战术互联网路由协议性能分析[J]. 兵器装备工程学报,2010,31(2):52-55.   
[32] Liu S, Xing G, Zhang H, et al.Passive interference measurement in Wireless Sensor Networks [C]//Proc of IEEE International Conference on Network Protocols. 2010: 52-61.   
[33] Burkhart M,Rickenbach P V,Wattenhofer R,et al.Does topology control reduce interference?[C]//Proc of ACM International Symposium on Mobile Ad hoc Networking & Computing.2004: 9-19.   
[34] Lu J,Whitehouse K.Flash flooding: exploiting the capture effect for rapid flooding in wireless sensor networks [Cl// Proc of Infocom. 20o9:2491- 2499.