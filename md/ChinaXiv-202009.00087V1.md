# 考虑约束参数切换的小蜂窝LTE移动负载自适应均衡

刘航，罗建国，许兴民

(华北科技学院 机电工程学院 河北省矿山设备安全监测重点实验室，河北 廊坊 065201)

摘要：针对因用户设备移动性和小区覆盖率造成的网络负载周期性不平衡问题，引入小蜂窝网络以支持高数据率服务和密集部署，提出一种自适应网络负载状态并考虑负载估计的小蜂窝网络移动性负载平衡算法。首先，该算法根据过载单元和相邻单元调整进行参数切换，资源的利用取决于信号质量和所连接的用户设备在长期演进网络(LTE)中的流量需求，并定义资源块利用率作为单元负载的度量，根据网络负载情况使用自适应阈值来确定过载单元。然后，为避免性能振荡，考虑移动负载对网络的影响，进行负载均衡过程设计。最后，通过系统级仿真评价了该算法在不同环境下的性能，仿真结果表明，该算法在网络间提供了更均衡的负载(即小区间的标准差较小)，比以前的算法具有更高的网络吞吐量。

关键词：有约束；参数切换；小蜂窝；移动设备；负载均衡；自适应 中图分类号：TN929.5 doi:10.19734/j.issn.1001-3695.2020.02.0061

Adaptive load balancing for small celular mobile systems with constrained parameter switching

Liu Hang, Luo Jianguo†, Xu Xingmin (Key Laboratoryofmine equipment safety monitoring in Hebei Province,School of mechanical& electrical engineering, North China institute ofscience & technology,Langfang,Hebei O65201,China)

Abstract:Aimingat theperiodic load imbalancecaused byuser equipment mobilityandcellcoverage,acelular network was introduced to support high data rate services and intensive deployment,and an adaptive load balancing algorithm for cellular networks considering load estimation is proposed.Firstly,the algorithm switched parameters according tothe adjustmentofoverloadunitsandadjacentunits.Theutilizationofresources dependsonthe signalqualityandthe traffic demand ofthe connected user equipment in the long-term evolution.The utilization rateof resource blocks was defined as a measureofunit load,andthe overload istis determinedbyusing adaptive thresholdaccording tothe network loadsituation. Then,in order to avoid performanceoscilation,considering the impact of mobile load on the network,the load balancing process was designed.Finaly,the performance of the algorithm in diferent environments was evaluated by system-level simulation.Thesimulationresultsshowthatthealgorithmprovidedamorebalancedloadbetween networks (i..,testandard deviation between cells is smaller),and had higher network throughput than previous algorithms.

Key words: constrained; parameter switching; cellular; mobile devices; load balancing; adaptive

# 0 引言

随着智能设备信息和通信技术应用的增加，对具有更高数据速率和更高服务质量(qualityofservice,QoS)的移动宽带服务的需求迅速增加。据统计，预计2021年对无线数据的预期需求是49艾字节，为2016年的7倍。为了支持数据需求提高网络容量，近些年引入小蜂窝理论，以支持未来的数据需求，并将在未来第五代(5G)网络中发挥重要作用。但是由于小蜂窝网络服务区域较小，易受用户设备(userequipment,UE)单元移动性影响，并且由于传输功率较低，每个小蜂窝只能为少量UE提供数据传输，容易导致UE的移动性导致整个网络负载不平衡。

为克服UE移动性导致的小区网络负载不均衡问题，文献[9]提出无须人工干预的自组织网络(self-organizednetwork,SON)来配置和优化网络。该算法采用集中式子系统结果，所有功能都位于单独的子系统中，问题是结构较为复杂。文献[10]设计了分布式子系统结构，所有功能都位于静态基站中。子系统算法优化了切换参数，实现了负载平衡，不会对用户体验产生负面影响。文献[11]考虑到小区链路环境，提出基于规则的小区单点偏移(cellindividualoffset,CIO)优化过程，以实现网络均衡。但由于作者只考虑了目标小区负载状态来寻找合适目标，但是没有考虑到从用户端到用户端的服务质量。文献[12]提出考虑网络中小蜂窝和多通道的负载均衡算法。然而该算法还采用了固定阈值来确定过载小蜂窝，阈值设定较为复杂。文献[13]提出的算法采用网络流理论，在平衡过程中包含相邻和非相邻超负荷邻域小蜂窝。该算法高度依赖于负载不足的邻域小蜂窝，在峰值负载情况下不能保证邻域小蜂窝之间的负载均衡。上述算法虽然取得了很好的效果，但是之前这些工作无法在各种极端负载情况下提供有效的负载平衡，例如负载不足的邻域情况和负载过高的邻域情况。

本文提出有约束调整切换参数的小蜂窝移动负载均衡算法(mobility load balancing,MLB)，与传统固阈值方法不同,该算法使用自适应阈值来查找过载小蜂窝。通过为过载小蜂窝引入最大可移动负载，将过载小蜂窝释放的负载限制到相邻小蜂窝，并对当前过载单元和候选目标单元的负载状态进行估计，以确定用户单元切换，实现有效地负载分配，避免性能振荡。此外，为改变候选用户单元，根据用户单元报告的测量值调整服务和目标用户单元信息。因此，该方法不仅限于小蜂窝网络，而且适用于宏蜂窝和异构网络。仿真结果表明，该算法能够保证移动负载均衡，获得更好的效果。

# 1 系统模型和问题描述

# 1.1系统模型

考虑小蜂窝网络集合 $\mathcal { N } = \{ 1 , \cdots , N \}$ ，由小蜂窝构成的集中式自组织网络(cSON)如图1所示。小蜂窝以开放接入方式工作，通过 $X 2$ 接口相互连接。当UE从一个小蜂窝移交给另一小蜂窝时，通过 $X 2$ 接口交换转移相关信息数据。cSON通过S1接口与所有小蜂窝连接。

![](images/b9df3b467a502c2f119c8d7e9d309fa0b82be308451c45b9732f0cde82a63695.jpg)  
图1自组织网络模型结构  
Fig.1Self organizing network model structure

根据从小蜂窝收集的信息，cSON周期性地优化和更新小蜂窝的切换参数，以平衡长期演进网络(LTE)中的负载，物理资源块(physical resource block,PRB)的最小蜂窝参数：180kHz带宽和 $0 . 5 \mathrm { ~ m ~ }$ 时长。频率分为12个 $1 5 ~ \mathrm { k H z }$ 带宽的子载波，一个时隙包含七个正交频分复用符号集(OFDM)。资源元素定义为子载波和符号周期构成。因此，资源块由 $1 2 \times 7$ 个资源元素组成，即一个资源块是七个OFDM符号集，具有 $1 2 \times 1 5$ kHz 带宽频率。分配资源调度时间单位是 $\mathrm { { 1 m s } } ( 2 \$ 个时隙)，称为传输时间间隔，本文考虑的是分辨率为1ms的离散系统时间。根据系统带宽可设置小区可用物理资源块总数，对于20兆赫系统带宽，PRB总数为100。

# 1.2小蜂窝负载测量

为实现网络性能负载平衡优化，必须找到合适测量方法，以便准确地表示小蜂窝负载。为确定小蜂窝网络是否超载，利用物理资源块计算资源块利用率(resource blockutilizationratio,RBUR)，定义为小蜂窝格使用的PRBs与小蜂窝格中PRBs总数的比率。在给定时间段 $T$ 内，时刻 $t$ 的小蜂窝 $i$ 的平均RBUR为

$$
\overline { { R B U R } } _ { i } ^ { t } = \frac { 1 } { T \cdot N _ { P R B } } \sum _ { \tau \in ( t - T , t ) } R B _ { i } ^ { \tau }
$$

其中， $R B _ { i } ^ { \tau }$ 和 $N _ { { P R B } }$ 是时间 $t$ 时分配的资源块数和小蜂窝中的资源块总数，小蜂窝的平均RBUR值越高，表示当小蜂窝的RBUR值达到1时，小蜂窝的服务负载越高，可用资源越少。

小蜂窝资源被完全耗尽，移动到该小蜂窝的UE或者会丢失，或者会遭遇低吞吐量。不考虑任何类型呼叫接纳控制，当新UE到达过载小蜂窝时，它将被该小蜂窝容纳，但小蜂窝中的每用户吞吐量将受到影响。因此，通过将部分UE从高负载蜂窝移动到轻负载蜂窝，有助于提高数据传输质量。

# 1.3问题模型

本文目标是平衡小蜂窝间的负载，提高网络性能。为此，通过基于测量的移动边缘UEs来减少小蜂窝间的负载差异。当时间段 $T$ 内，时刻 $t$ 的 $n$ 个小蜂窝网络的平均RBUR为

$$
\overline { { R B U R } } _ { N e t } ^ { t } = \frac { 1 } { N } { \sum _ { i \in \mathcal { N } } } \overline { { R B U R } } _ { i } ^ { t }
$$

网络中各小蜂窝RBUR的标准差为

$$
\sigma \left( \overline { { R B U R } } ^ { t } \right) = \frac { 1 } { N } \sqrt { \sum _ { i \in \mathcal { N } } \left( \overline { { R B U R } } _ { i } ^ { t } - \overline { { R B U R } } _ { N e t } ^ { t } \right) ^ { 2 } }
$$

则问题可表示为

$$
{ \mathrm { m i n i m i z e } } \ \sigma { \Big ( } { \overline { { R B U R } } } ^ { t } { \Big ) }
$$

s.t.

$$
0 \leq R B _ { i } ^ { \tau } \leq N _ { P R B } , \quad \forall i \in \mathcal { N } , \quad \forall \tau \in ( t - T , t )
$$

为将负载从过载小蜂窝转移到欠载小蜂窝以平衡网络，自适应地调整切换参数，并考虑负载转移对网络影响进行切换。

# 2 移动性负载平衡参数切换优化

为实现移动管理、容量和覆盖率等参数优化，每个小区都需测量相邻小区信号质量、参考信号接收功率(referencesignalreceivedpower,RSRP)或参考信号接收质量(referencesignalreceivedquality,RSRQ)。为此，网络允许用户将信号质量以周期性或基于事件报告的形式向服务小蜂窝报告。测量报告包括来自服务小区和相邻小区的信号质量信息。

# 2.1 LTE事件

LTE 指定8个事件用于测量报告，其中6个事件（A、$A _ { 2 }$ 、 $\left| \mathbf { \nabla } A _ { 3 } \right.$ 、 $A _ { 4 }$ 、 $A _ { 5 }$ 和 $A _ { 6 }$ )用于LTE内测量，2个事件( $B _ { \mathrm { { l } } }$ 和 $B _ { 2 }$ ）用于RAT内测量。考虑LTE内部负载平衡时，放弃RAT内事件测量。当特定事件标准在预先指定时间内得到满足时，称为触发时间，UEs向服务小蜂窝报告基于LTE事件的测量，事件触发量和报告的测量值可以是RSRP或RSRQ。所有LTE内事件( $A _ { 3 }$ 和 $A _ { 6 }$ 除外)在与预设阈值比较时，会导致事件触发。然而，事件 $A _ { 3 }$ 和 ${ A } _ { 6 }$ 是基于小蜂窝间的实时信号质量比较触发的。在基于阈值事件中，当服务小蜂窝信号质量比预设阈值好时，UE 触发事件 $A _ { 1 }$ 。当信号质量比给定阈值差时，UE触发事件 $A _ { 2 }$ 。当相邻小蜂窝的信号质量比预设阈值好时，触发事件 $A _ { 4 }$ 。然而，当服务小区比预设阈值更差，相邻小区比另一阈值更好时，事件 $\mid A _ { 5 }$ 由UE触发；事件 $A _ { 3 }$ 被定义为当相邻小区的服务偏移更好时的触发事件。当相邻小区的信号质量偏移大于第二小区时，UE触发事件 $A _ { 6 }$ 。主小蜂窝是在初始连接建立期间由UEs选择小蜂窝。在考虑载波时，二次信元可由一次信元根据终端业务需求添加或删除。假设RSRP报告测量信号质量，采用 $A _ { 3 }$ 、 $A _ { 4 }$ 事件测量分别触发切换和选择候选UE切换。

# 2.2事件切换负载转移

当相邻信元信号偏移大于服务信元信号偏移时，触发事件 $A _ { 3 }$ ，UE向服务信元报告测量结果。由于事件 $A _ { 3 }$ 的触发逻辑取决于相邻小区的相对信号质量，因此事件 $A _ { 3 }$ 最适合于寻找最佳相邻小区，即使在LTE内事件中也是如此。因此，事件 $A _ { 3 }$ 在无线网络中广泛用于触发切换。如果 $A _ { 3 }$ 触发标准时间长于触发时间，则小蜂窝决定触发切换。事件 $A _ { 3 }$ 测量报告条件如下：

$$
\begin{array} { r } { M n + O f h + O c n - H y s t > } \\ { M p + O f p + O c p + O f f } \end{array}
$$

其中， $M n$ 和 $M p$ 表示平均RSRP值； $O f n$ 和 $O f p$ 表示频率特定偏移； $o c n$ 和 $\ o c p$ 分别表示目标和服务小蜂窝的单独偏移；Hyst表示滞后参数； $o f f$ 表示主要和目标相邻小蜂窝间的 $A _ { 3 }$ 事件偏移。在本文中，因为用于频率间切换，则放弃 $O f n$ 和 $O f p$ u

通过改变 $\mathit { O c n } , \mathit { O c p }$ 和Off 的值，可改变Handover决策区。根据服务小蜂窝和目标小蜂窝的负载情况，可故意拖延或加快交接。如果某个小蜂窝中相邻小蜂窝的 $o c n$ 值增加，或Ocp值降低，则该小蜂窝范围会减小，且该小蜂窝的UEs可转移给相邻小蜂窝以减少负载。如果 $o c n$ 值降低或 $\ o _ { c p }$ 值增加，小蜂窝将从相邻小蜂窝吸引UEs来增加负载。例如，在图 2a中，小蜂窝 B 超载四个UEs，其相邻小蜂窝 A和C 轻载两个UE。小蜂窝 A和B的边界有边缘UEs(UE3和UE4)，但小蜂窝B和C的边界没有边缘UEs，因此，通过降低小蜂窝A的 $o c n$ ,UE3从小蜂窝B向小蜂窝A转移，网络负载平衡，尽管更改 $o _ { c p }$ 可延迟或加速转移，但它对所有相邻小蜂窝的范围影响。因此，对于特定相邻小蜂窝的负载转移，参数 $o c n$ 更适合调整。

# 2.3事件查找移动边缘UEs

通过将超负荷小区中的郊区用户转移到相对较低负荷小区中实现负载平衡。为此，SON需要有关过载小蜂窝中边缘UE 的信息。由于事件 $A _ { 4 }$ 是在相邻小蜂窝的 RSRP比提供的阈值更好时触发的，因此它适用于从小蜂窝收集郊区UEs信息。使用事件 $A _ { 4 }$ ，网络中所有的小蜂窝都收集郊区的信息并与子系统分享。触发事件 $A _ { 4 }$ 的标准表示为

$$
M n + O f n + O c n - H y s t > T h r e s h
$$

其中，Thresh 是事件 $A _ { 4 }$ 的阈值。满足式(6中条件的UE报告测量结果，包括服务小蜂窝和相邻小蜂窝的信号强度。因此，通过设置合理阈值并选择报告测量值的UEs，小蜂窝可获得边缘UEs的信息并列出要移动以进行负载平衡的候选UEs。例如，在图2b中，UE3在小蜂窝B的 $A _ { 4 }$ 事件边界之外，并报告测量值。当小蜂窝电量B过载时，使用来自UE3的测量报告。小蜂窝B可通过减少小蜂窝A的 $o c n$ 将UE3移交给小蜂窝A。因此，每个小蜂窝 $i$ 根据 $A _ { 4 }$ 事件报告生成边缘UEs的集合。集中式的从所有小蜂窝收集边缘用户的信息 $\varepsilon$ 确定$\mathcal { E } = \{ \mathcal { E } _ { 1 } , \cdots , \mathcal { E } _ { N } \}$ 。

![](images/f0abff83be8cc91bb8ed767f3563e1ee43b6301d8aa90f2b3e31e2a21ff71a37.jpg)  
Fig.2Basic working process of algorithm

# 3移动性负载平衡算法

# 3.1自适应阈值和负载估计

如果阈值太高，算法将很难找到用于负载平衡的过载小蜂窝。网络负载情况也会随着时间和空间的变化而变化。因此，确定超载小蜂窝的固定阈值是不合理的。因此，为识别不同负载情况下的过载小蜂窝，引入自适应阈值 $T h _ { A d a p t }$ 定义为

$$
T h _ { \scriptscriptstyle A d a p t } = \operatorname* { m a x } \left\{ \overline { { R B U R } } _ { N e t } , T h _ { \scriptscriptstyle I n i t } \right\}
$$

其中， $T h _ { I n i t }$ 是预定义可接受负载阈值，如果至少有一个小蜂窝负载状态超过 $T h _ { I n i t }$ ，网络是否需要负载平衡，算法将启动负载平衡。 $T h _ { I n i t }$ 的值应保持最小，以便平衡负载。

切换前后为边缘UEs提供服务所需的资源块(RBs)是不同的，因为UEs经历了来自不同小蜂窝的不同信号质量(RSRP或RSRQ)，为平衡负载，算法确定了要从过载小蜂窝移动边缘UEs的负载，以及在从香农公式(信道容量C)进行切换之前，为目标相邻小区的边缘UEs提供服务的负载定义为 $C = B \cdot \log ( 1 + \theta )$ ，其中 $B$ 是传输带宽， $\theta$ 是信噪比加噪声比(SINR)。负载平衡算法对位于小蜂窝边缘区域且在低信噪比情况下接收信号质量信噪比较低的UEs进行切换，通过泰勒级数展开，信道容量可近似为

$$
C \cong B \cdot \theta
$$

对于小蜂窝 $i$ 的给定SINR和所需容量 $C _ { r e q }$ ，UE $e$ 所需的RBs 数量与SINR成反比，可定义为

$$
\theta = P _ { s } / ( P _ { i } + P _ { n } )
$$

其中， $P _ { s }$ 是信号功率， $P _ { i }$ 是由多个小蜂窝同时使用的资源块之间的冲突引起的平均干扰， $P _ { n }$ 表示背景噪声信号功率 $P _ { s }$ 是在整个带宽中的12个子载波上通过 $N _ { \mathit { P R B } }$ 测量的，然后归一化为单个子载波带宽，因为RSRP是在整个带宽上承载特定于小区的RS的资源元素的平均功率，可以使用RSRP和每个天线子载波因子进行计算：

$$
P _ { s } = x \cdot 1 2 \cdot N _ { \mathit { r R B } } \cdot R S R P
$$

当 $x = 1$ 时，满负荷传输SINR可表示为

$$
\theta = \left( \frac { 1 2 \cdot N _ { P R B } } { P _ { i } + P _ { n } } \right) R S R P
$$

在干扰和噪声相同情况下，SINR与边缘区域处的RSRP成线性关系。由于交接发生在小蜂窝边缘，小蜂窝边缘的UE受到几乎相同的干扰和噪声，因此，对于给定数量的RBS(NPRB)，将服务于小蜂窝 $i$ 边缘的UE 的平均负载表示为 $\rho ( i , e )$ 。然后，服务于邻近小蜂窝 $j$ 处小蜂窝 $i$ 边缘的估计负载 $\hat { \rho } ( j , e )$ 可表示为

$$
\hat { \rho } _ { ( j , e ) } \approx \rho _ { ( i , e ) } \frac { M s _ { ( i , e ) } } { M n _ { ( j , e ) } }
$$

其中， $M s _ { ( i , e ) }$ 和 $M n _ { ( j , e ) }$ 分别是服务于小蜂窝 $i$ 和相邻小细胞 $j$ 的测量RSRPs。根据边缘UEs及其从小蜂窝收集的负载信息，子小蜂窝可以周期性地计算边缘UEs的平均负载，表示为

$$
\rho _ { e d g e } = { \frac { 1 } { \| { \mathcal { E } } \| } } \sum _ { i \in \mathcal { N } } \sum _ { e \in { \mathcal { E } } _ { i } } \rho _ { ( i , e ) }
$$

其中，是集合 $\varepsilon$ 中的UEs总数。

# 3.2算法描述

a)信息收集。在信息收集例行程序中，SON收集可移动和位于小蜂窝边界的UEs的信息。根据 $A _ { 3 }$ 事件测量报告，收集服务小蜂窝边缘区域和最适合转移相邻小蜂窝的UEs信息。算法建立UEs集合， $\mathcal { U } = \{ \mathcal { U } _ { 1 } , \cdots , \mathcal { U } _ { N } \}$ ，其中 $\mathcal { U } _ { i }$ 是报告的UEs集。为调整每个小蜂窝 $A _ { 4 }$ 的阈值，对所有服务小蜂窝RSRPs进行平均，对于小蜂窝 $i$ ，该值表示如下：

$$
\overline { { M s } } _ { i } = \frac { 1 } { \lVert M _ { i } \rVert } \sum _ { u \in \mathcal { U } _ { i } } M s _ { ( i , u ) }
$$

其中， $\forall i \in \mathcal N$ 。 $\boldsymbol { B } _ { i }$ 是小蜂窝 $i$ 的相邻小蜂窝集。因此，在为 $A _ { 4 }$ 事件阈值设定自适应阈值后， $A _ { 4 }$ 阈值会根据 $A _ { 3 }$ 事件参数的更新进行自适应调整，然后子小蜂窝收集 $A _ { 4 }$ 事件下的测量报告。UEs报告 $A _ { 4 }$ 事件被认为是可将负载转移到相邻小蜂窝以减轻服务小蜂窝的负载的候选者。SON根据每个小蜂窝的 $A _ { 4 }$ 事件触发的测量报告建立数据库：服务小蜂窝UEs、RSRPs(Mss和 Mns)。设 $\mathcal { E } _ { i } = \left\{ e _ { i } ^ { ( 1 ) } , e _ { i } ^ { ( 2 ) } , \cdots , e _ { i } ^ { ( | \boldsymbol { \varepsilon } _ { i } | ) } \right\}$ 向小蜂窝 $i$ 报告 $A _ { 4 }$ 事件测量值，并按相邻小蜂窝的 ${ \mathrm { R S R P } } ( M n )$ 的降序排序。集合${ \mathcal { T } } _ { i } = \left\{ \tau _ { i } ^ { ( 1 ) } , \tau _ { i } ^ { ( 2 ) } , \cdots , \tau _ { i } ^ { ( | \varepsilon _ { i } | ) } \right\}$ 表示在 $A _ { 4 }$ 事件下由边缘 UEs向服务小蜂窝报告的相邻小蜂窝集。

b)负载平衡。在负载平衡中，SON根据平均RBUR和估计的转移负载，定期将UEs从高负载小蜂窝移动到低负载的相邻小蜂窝，从而形成负载平衡。首先，集中式SON接收来自所有小蜂窝的RBUR信息，并计算边缘UEs、 $\rho _ { e d g e }$ 的平均RBUR。然后，对所有小蜂窝按RBUR 降序排序，子算法将列表最大 $R B U R _ { m a x }$ 与预设阈值 $T h _ { I n i t }$ 进行比较，以确定网络是否需平衡负载。如果小蜂窝的最大RBUR大于阈值，则认为网络过载。根据网络上的负载不同，转移到其他小蜂窝的负载也不同。因此，设置适应网络负载状态阈值 $T h _ { A d a p t }$ ，如式(5)所示，以确定网络中相对过载小蜂窝。如果网络上的平均负载$\overline { { R B U R } } _ { N e t }$ 大于预设阈值 $T h _ { I n i t }$ ，自适应阈值设置为网络平均负载否则阈值设置为 $T h _ { I n i t }$ 。该算法建立了过载小蜂窝集合 $\mathcal { O }$ ，对于 $o \in { \mathcal { O } }$ 和 $\mathcal { O } \subset \mathcal { N }$ 令 $\overline { { R B U R } } _ { o } \geq T h _ { A d a p t }$ 。因此，为平衡网络负载，该算法按小蜂窝负载顺序将过载小蜂窝从 $\mathcal { O }$ 中依次取出。在负载平衡过程中，通过从过载小蜂窝移动UEs来减少对欠载相邻小蜂窝的负载，移动负载可能使欠载小蜂窝过载，从而在多个小蜂窝之间引发振荡，导致无限循环以避免此类振荡，定义小蜂窝负载 $R B U R _ { l o w }$ 下限：

$$
R B U R _ { l o w } = \overline { { R B U R } } _ { n e t } - \frac { 1 } { 2 } \rho _ { e d g e }
$$

因此，在平衡负载后，过载小蜂窝的平均负载不低于过载小蜂窝下限，该算法执行以下过程。首先，该算法计算过载小蜂窝 $o \in { \mathcal { O } }$ 的最大负载，称为转移负载，表示为

$$
\widetilde { \rho } _ { o } = \overline { { R B U R } } _ { o } - R B U R _ { l o w }
$$

在计算 $o \in \mathcal { O }$ 过载小蜂窝的可移动负载( $\cdot \tilde { \rho } _ { o }$ )后，将所有$i \in \mathcal { N }$ 的估计小蜂窝负载(RBUR's)初始化为 $R B U R _ { i } \mathrm { s }$ 之后，该算法随后在特定过载小蜂窝中找到可能候选UEs。为此，对于每个边缘UEs， $e _ { o } ^ { ( n ) } \in \mathcal { E } _ { o }$ ，计算当前服务小蜂窝 $o \in \mathcal { O }$ 中作为$\rho _ { ( o , e _ { o } ^ { ( n ) } ) }$ 的负载贡献，以及负载估计 $\hat { \rho } _ { \left( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } \right) }$ 。然后设定算法条件：

$$
\tilde { \rho } _ { o } > \rho _ { \left( o , e _ { o } ^ { ( \kappa ) } \right) }
$$

$$
\overline { { R B U R } } _ { n e t } > R B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } + \hat { \rho } _ { \left( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } \right) }
$$

$$
R B U R _ { o } ^ { \prime } - \rho _ { ( o , e _ { o } ^ { ( n ) } ) } > R B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } + \hat { \rho } _ { ( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } ) }
$$

如果满足这三个条件，则接受将UEs $e _ { o } ^ { ( n ) }$ 转移给相邻小区，相关小区个别偏移更新如下：

$$
C I O = M _ { \left( o , e _ { o } ^ { ( n ) } \right) } - M _ { \left( o , t _ { o } ^ { ( n ) } \right) } + H y s t _ { o } + \Delta
$$

$$
O c n _ { ( \rho , \tau _ { \rho } ^ { ( n ) } ) } = C I O
$$

$$
O c n _ { ( \tau _ { o } ^ { ( n ) } , o ) } = - C I O
$$

其中， $M _ { \left( o , e _ { o } ^ { ( n ) } \right) }$ 是服务于 $\mathrm { U E } e _ { o } ^ { ( n ) }$ 的过载小蜂窝 $\mid o \mid$ 的RSRP， $M _ { \left( o , t _ { o } ^ { ( n ) } \right) }$ 是由UE $e _ { o } ^ { ( n ) }$ 测量的目标小蜂窝 $\tau _ { o } ^ { ( n ) }$ 的RSRP, $H y s t _ { o }$ 是小蜂窝 $\mid o \mid$ 的滞后参数， $\Delta$ 是规定的步进增量。该算法在(21\~22)中同时对称更新服务小蜂窝和目标小蜂窝的单个偏移量，以保持平衡水平。最后，该算法更新服务小蜂窝和目标小蜂窝的负载信息如下：

$$
R B U R _ { 0 } ^ { \prime } = R B U R _ { 0 } ^ { \prime } - \rho _ { \left( o , e _ { r } ^ { ( n ) } \right) }
$$

$$
B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } = R B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } + \hat { \rho } _ { \left( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } \right) }
$$

$$
\tilde { \rho } _ { o } = \tilde { \rho } _ { o } - \rho _ { ( o , e _ { o } ^ { ( n ) } ) }
$$

对于超载小蜂窝的下一候选UE，上述过程将针对网络中的所有超载小蜂窝继续进行。所提出的MLB 算法负载平衡过程见算法1。

算法1负载平衡算法

1. 从所有小蜂窝 $\mathcal { N }$ 获取RBUR信息  
2. 计算边缘UEs 的 $\rho _ { e d g e }$   
3. 根据 RBUR 对 $\mathcal { N }$ 排序并找到 $R B U R _ { m a x }$   
4. if $R B U R _ { \operatorname* { m a x } } > T h _ { I n i t }$ then  
5. $\overline { { R B U R } } _ { N e t }  \mathrm { m e a n } ( R B U R _ { i } )$   
6. $T h _ { \scriptscriptstyle A d a p t } \gets \operatorname* { m a x } \left( \overline { { R B U R } } _ { \scriptscriptstyle N e t } , T h _ { \scriptscriptstyle I n i t } \right)$   
7. while $R B U R _ { i } \geq T h _ { A d a p t }$ do  
8. $i \in \mathcal { O }$ ，即 $\boldsymbol { \mathscr { O } }$ 包含小蜂窝 $i$   
9. end while  
10. for $o \in \mathcal { O }$ do  
11. $\tilde { \rho } _ { o } = \overline { { R B U R } } _ { o } - \overline { { R B U R } } _ { n e t } + \frac { 1 } { 2 } \rho _ { e d g e }$   
12. 获得候选 $\mathcal { E } _ { o }$ （204号  
13. $R B U R _ { o } ^ { \prime }  \overline { { R B U R _ { o } } }$   
14. for all $e _ { o } ^ { ( | \mathcal { E } _ { o } | | ) }$ do  
15. 计算 $\rho _ { \left( o , e _ { o } ^ { ( n ) } \right) }$ ，并估计 $\hat { \rho } \big ( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } \big )$   
16. if 设定算法条件(17\~19)满足 then  
17. $\begin{array} { r l } & { C I O \xleftarrow { M } _ { ( o , \varepsilon _ { o } ^ { ( n ) } ) } - M _ { ( o , \tau _ { o } ^ { ( n ) } ) } + H y s t _ { o } + \Delta } \\ & { O c n _ { ( o , \tau _ { o } ^ { ( n ) } ) } \xleftarrow { } C I O ; O c n _ { ( \tau _ { o } ^ { ( n ) } , o ) } \xleftarrow { } C I O } \\ & { R B U R _ { o } ^ { \prime } \xleftarrow { } R B U R _ { o } ^ { \prime } - \rho _ { ( o , e _ { o } ^ { ( n ) } ) } } \\ & { R B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } \xleftarrow { } R B U R _ { \tau _ { o } ^ { ( n ) } } ^ { \prime } + \hat { \rho } _ { ( \tau _ { o } ^ { ( n ) } , e _ { o } ^ { ( n ) } ) } } \end{array}$   
18.  
19.  
20.  
21. $\tilde { \rho } _ { o } \gets \tilde { \rho } _ { o } - \rho _ { ( o , e _ { o } ^ { ( n ) } ) }$   
22. endif  
23. endfor  
24. endfor  
25.endif

# 4 实验分析

实验区域的小区半径为 $8 0 \mathrm { m }$ ，信号发射设备与独立用户设备的间距区间是 $1 \mathrm { m } { \sim } 5 \mathrm { m }$ ，设置噪声干扰的功率谱参数取值是-174dBm/Hz。户外实验设备平台见图3所示。

![](images/6aa63428ba562e4283ce64d40ceb229fc2a7c6077aaada6d722b8acd5f5bd259.jpg)  
图3测试场地 Fig.3Test site

设定小区内通信数据传输过程中的路径损耗模型形式是$1 2 8 . 1 + 3 7 . 6 \log 1 0 ( d _ { n k } ) \mathrm { d B }$ ，参数 $d _ { n k }$ 是移动用户设备 $k$ 与信号发射基站 $n$ 之间的直线距离(单位 $\mathrm { k m } \mathrm { \Omega }$ 。为验证所提算法有效性，选取对比负载均衡方案为：最大信噪比通信数据接入方案(MSA)；最高可达速率通信数据接入方案(MARA)；有偏信噪比通信数据接入方案(BSA)；有偏可达速率通信数据接入方案(BRA)。为实现对网络负载均衡情况的更高精度计算，采用Jain 指数对其进行表征，计算形式为

$$
J = \frac { \left( \sum _ { n \in \mathcal { N } _ { m p } } y _ { n } \right) ^ { 2 } } { N _ { m p } \sum _ { n \in \mathcal { N } _ { m p } } y _ { n } ^ { 2 } }
$$

其中， $y _ { n } = \sum _ { s \in S } y _ { n s }$ 。Jain指数 $J$ 的取值位于区间 $\big [ 1 / N _ { m p } , 1 \big ]$ 范围内，该指数取值越大，表明数据传输负载的均衡性越好。

图4实验区域内，选取不同负载均衡算法进行实验对比。根据实验结果可知，本文算法相对于选取的对比算法具有更高的Jain指数 $J$ 的取值，表明本文算法在进行小区网络数据的负载均衡过程中具有更好的实验结果。原因在于，本文算法对小区网络数据的负载均衡过程不依赖于基站发射功率，因此在负载的均衡度上更为合理，具有更好的随机性。MARA方案和MSA方案负载均衡性能相对较差，BRA方案和BSA方案因为采用了有偏约束的通信数据接入方案设计，并且考虑了负载转移策略，因此其在考虑负载均衡性上具有更高的精度，其所具有的负载均衡效果更为理想，在负载均衡性指标上仅次于本文算法。

![](images/4cc6279963e64d84b8e8eab1ecce1970628b823f1b09930cfb1fd70050b47bd5.jpg)  
图4负载平衡水平对比  
Fig.4Load balance level comparison

为更进一步研究负载平衡性能的增益指标，这里选取有效速率指标的累积分布函数(CDF)进行实验对比，结果见图5所示。

![](images/2a22b2c1d44112de11232e8f5910aff7be437f65645f0cd6c3fbb6c34935b050.jpg)  
图5有效速率累积分布

根据图5结果可知，MARA方案和MSA方案在有效速率指标的累积分布函数曲线上具有相对较低的数据表现，这表明MARA方案和MSA方案的网络数据的有效速率较低，也就是网络的传输速度相对不高。主要原因是网络数据的均衡性较差，容易造成数据传输的拥堵，没有发挥网络数据传输的最佳性能。BRA方案和BSA方案因为具有相对更为理想的数据传输均衡性，因此其在数据传输的有效速率上性能表现更佳。与上述算法相比，本文算法的有效速率指标的累积分布函数指标表现最好，其具有最佳的网络服务质量体验。

对于选取的网络数据传输资源划分方式 $\eta$ ，图6所示是对于设置的不同目标速率 $\rho$ 指标情况下，覆盖率指标的实验数据结果。本实验选取的覆盖率指标指的是用户设备的有效速率参数高于设定目标速率的比例。根据实验结果可知，随着目标速率 $\rho$ 指标取值增加，覆盖率指标的实验数据曲线降低，根据覆盖率指标的定义很容易理解。另一方面，随着参数 $\eta$ 的取值增加，覆盖率指标的实验数据先增加后降低，原因在于参数 $\eta$ 的取值增加会导致可用数据传输资源的降低和干扰的下降，两种因素此消彼长造成覆盖率指标数据出现先增加后降低现象。

![](images/f1631ea89a0581c910939e023ed985213297939c2f2312222c8ff747412c6262.jpg)  
Fig.5Effective rate cumulative distribution   
图6覆盖率实验数据  
Fig.6Coverage experimental data

# 5 结束语

为提升网络负载均衡算法的有效性，降低网络数据的丢包率，并提升网络的数据吞吐率，本文提出一种自适应网络负载状态并考虑负载估计的小蜂窝网络移动性负载平衡算法。传统固定负载分配模式的网络负载处理方式，对于过载数据的资源分配无法得到满足，即便是临近小区内具有足够的网络数据资源，也无法有效进行分配和调剂，而不平衡负载同样会导致网络数据吞吐数据量的降低。在LTE情况下，资源使用取决于无线信号质量和UEs流量需求。因此，为开发一种负载平衡算法，定义资源块利用率作为单元负载度量，并根据网络负载情况采用自适应阈值来确定过载单元。通过估计移动负载对现有单元负载影响，不仅考虑了单元过载，而且考虑了相邻单元负载。仿真结果表明，该算法在网络间提供了更均衡的负载，比以前的算法具有更高的网络吞吐量。下一步研究方向： $\textcircled{1}$ 进一步提升算法的负载均衡性能； $\textcircled{2}$ 研究算法的实际应用研究。

参考文献：   
[1]Emad Hmood Salman,Nor Kamariah Noordin,Shaiful Jahari Hashim,et al.Erratum to:An overview of spectrum sensing techniques for cognitive LTE and LTE-A radio systems [J]. Telecommunication Systems,2017, 65 (2): 339-345.   
[2] Nasreddine Mallouki, Bechir Nsiri, Sofien Mhatli，,et al.Erratum to: Analysis ofFull Volterra and Sparse Volterra Nonlinear Equalization for Downlink LTE System [J]. Wireless Personal Communications,2016,89 (4): 1433-1449.   
[3]Emad Hmood Salman,Nor Kamariah Noordin,Shaiful Jahari Hashim,et al. An overview of spectrum sensing techniques for cognitive LTE and LTE-A radio systems [J]. Telecommunication Systems,2017,65 (2): 215-228.   
[4] Jinling Hu,Shanzhi Chen,Li Zhao,et al.Link level performance comparison between LTE V2X and DSRC[J]. Journalof Communications and Information Networks,2017,2 (2):101-112.   
[5]Shubham Gupta,Balu L.Parne,Narendra S Chaudhari.DGBES: Dynamic Group Based Efficient and Secure Authentication and Key Agreement Protocol for MTC in LTE/LTE-A Networks [J].Wireless Personal Communications,2018,98 (3): 2867-2899.   
[6] Ibrahim Shgluof, Mahamod Ismail, Rosdiadee Nordin.An Enhanced System Information Acquisition Scheme for CSG Femtocells in 3GPP LTE/LTE A Systems [J]. Wireless Personal Communications,2017, 96 (3): 3995-4011.   
[7]Saehoon Kang，Wonyong Yoon. SDN-based resource allocation for heterogeneous LTE and WLAN multi-radio networks [J].The Journal of Supercomputing,2016,72 (4): 1342-1362.   
[8]David Gonzalez G,Mario Garcia-Lozano,Silvia Ruiz Boqué.Intercell Interference Coordination for Control Channels in LTE and LTE-A: An Optimization Scheme Based on Evolutionary Algorithms [J]. Wireless Personal Communications,2017,93 (3): 687-708.   
[9]Fuad M Abinader Jr,Vicente A de Sousa Jr,Sayantan Choudhury, et al. LTE/Wi-Fi Coexistence in 5 GHz ISM Spectrum: Issues,Solutions and Perspectives [J]. WirelessPersonal Communications,2018,99 (1): 403- 430.   
[10] David Gonzalez G,Mario Garcia-Lozano，Silvia Ruiz,et al．A metaheuristic-based downlink power allcation for LTE/LTE-A cellular deployments [J].Wireless Networks,2014,20 (6): 1369-1386.   
[11] Zahra Alavikia,Abdorasoul Ghasemi. Overload control in the network domain ofLTE/LTE-A based machine type communications [J]. Wireless Networks,2018,24 (1): 1-16.   
[12] Haipeng Du,Qinghua Zheng,Weizhan Zhang,et al. LTE-EMU: A High Fidelity LTE Cellr Network Testbed for Mobile Video Streaming [J]. Mobile Networks and Applications,2017,22 (3): 454-463.   
[13] Ying Loong Lee,Jonathan Loo,Teong Chee Chuah,etal. Multiobjective Resource Allcation for LTE/LTE-A Femtocell/HeNB Networks Using Ant Colony Optimization [J].Wireless Personal Communications,2017,92 (2): 565-586.   
[14] Alexandre Ragaleux, Sebastien Baey, Cedric Gueguen. Adaptive and Generic Scheduling Scheme for LTE/LTE-A Mobile Networks [J]. Wireless Networks,2016,22(8): 2753-2771.   
[15] Diego Castro-Hernandez,Raman Paranjape.Dynamic Analysis of Load Balancing Algorithms in LTE/LTE-A HetNets [J].Wireless Personal Communications,2017,96 (3): 3297-3315.