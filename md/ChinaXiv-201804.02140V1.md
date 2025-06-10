# 基于多对一Gale-Shapley 算法的D2D 通信资源分配

李中捷，谢东朋

(中南民族大学 智能无线通信湖北省重点实验室，武汉 430074)

摘要：针对D2D通信复用异构蜂窝网络上行信道产生的干扰问题和频谱资源优化问题进行研究，提出一种基于多对一Gale-Shapley 算法的D2D通信资源分配方案。本方案允许多个D2D用户共享一个蜂窝用户信道资源，通过设置信干噪比（SINR）门限保证用户的通信服务质量（QOS)。根据信道分配情况，构建D2D用户和信道的偏好列表，最大化系统总容量。仿真结果表明，该方案收敛较快、复杂度较低，能够有效保证用户的通信服务质量，系统总容量接近最优解。本研究为实现D2D用户和蜂窝用户的频谱资源共享，提高频谱利用率提供了一种有效方案。

关键词：D2D通信；Gale-Shapley算法；异构蜂窝网络；资源分配；系统容量中图分类号：TN929.53 doi:10.3969/j.issn.1001-3695.2018.02.0050

Resource allocation for D2D communication based on many-to-one Gale-Shapley algorithm

Li Zhongjie, Xie Dongpeng† (Hubei KeyLaboratoryofIntelligent Wireless Communication,South-Central Universityfor Nationalities，Wuhan43004, China)

Abstract:In order to solve the problem of interferenceand spectrum optimization caused by D2D(device-to-device) communication multiplexing uplink channel of heterogeneous celular networks,this paper proposed aresource alocation scheme based on many toone Gale-Shapley algorithm.It alowed multiple D2Dusers to shareacellular userchannel resource and guaranted thecommunicationqualityofservice (QOS)ofusers byseting thethresholdofsignaltointerferenceand noise ratio (SINR).The scheme constructed a preference list forD2Dusers and channels and maximized system total capacity based onchannelallcation.Simulationresultsshowthattheschemeconverges fastandhaslowcomplexity.Thesystemtotalcapacity is closetotheoptimal solution while guarantees thequalityofserviceofusers efectively.Theresearch provides an effective scheme to realize the spectrum sharing between D2D users and celllar users and improve spectrum utilization.

Keywords:D2D communication; Gale-Shapley algorithm；heterogeneous celllar network；resource alocation；system capacity

# 0 引言

为了提高无线频谱利用率，D2D通信作为很有前景的技术成为近些年的研究热点[I\~3]。传统蜂窝网络用户之间需要经过基站转发数据来进行通信，而D2D用户可以进行近距离的直接通信。因此，与蜂窝通信相比，D2D通信有更小的通信延迟，能够通过复用蜂窝用户的频谱资源来提高频谱效率，获得更高的吞吐率和能量效率[4]。由于复用蜂窝频谱资源会在蜂窝通信和D2D 通信之间产生严重的干扰[5]，大量研究工作采用资源分配减轻干扰[6\~10]。文献[6]提出了一种基于局部搜索的资源分配算法，该算法只能获得局部最优解。文献[7]提出了一种分布式资源分配算法，然而并没有明确给出相比其他算法所获得的性能增益。文献[8]提出了一种基于背包理论的干扰感知资源分配算法，但在很多情况下，该算法并不能得到一个可行的分配结果。文献[9]中首先给D2D用户分配资源，然后根据D2D用户在每个资源块上的分配情况为蜂窝用户分配资源，但是在实际中一般要先保证蜂窝用户的通信，所以蜂窝用户在进行比例公平调度时改变了权值，降低了公平性。由Gale 和 Shapley 两人提出的一对一Gale-Shapley 算法（延迟接受算法）最初应用是为了合理的解决男女婚姻匹配问题，使男女之间达到一个合理的匹配[10]。文献[11]提出了一种基于延迟接受算法的稳定匹配方案为D2D用户分配资源，但该方案有以下几点不足：a）以距离为准则建立用户的偏好列表并不是最好的选择；b）当一次性为蜂窝用户分配好资源时并没有考虑到蜂窝用户服务质量的限制c）只允许一个D2D 对共享一个蜂窝用户的频谱资源，因此随着D2D用户的增多，不能更好地提高频谱利用率；d）仿真环境只是考虑单小区的蜂窝网络，并没有考虑异构蜂窝网络的情况。本文针对这四点不足对文献[11]中的算法进行改进，提出一种在异构蜂窝网络环境下基于多对一Gale-Shapley 算法的资源分配方案。仿真结果显示，本方案在保证蜂窝用户的通信服务质量的前提下，能够增加D2D用户的连接数，提高系统总容量。

# 1 系统模型和问题规划

# 1.1系统模型

本文研究D2D用户复用异构蜂窝网络上行信道的资源分配问题，假设信道总数为N，宏蜂窝用户信道只能被一个微蜂窝用户复用，但能被多个D2D用户复用，同时假设一个微蜂窝用户或D2D用户只能复用一个信道资源。如图1所示的异构蜂窝网络中有三种通信模式的用户和两种基站，宏基站位于小区中心，微蜂窝基站以密度为 $\lambda _ { _ s }$ 的泊松点过程在小区中随机分布，蜂窝用户和D2D用户分别以密度为 $\lambda _ { c }$ 和 $\lambda _ { d }$ 的泊松点过程在小区中随机分布。各基站可以获取各个通信链路的信道状态信息。集合 $M = \left\{ 1 , 2 , \cdots , C \right\}$ ， $\textit { W } = \left\{ 1 , 2 , \cdots , J \right\}$ ， $H = \left\{ 1 , 2 , \cdots , D \right\}$ 分别代表宏蜂窝用户集合，微蜂窝用户集合和D2D用户集合。

![](images/b4f4acd0442ffb776b7c0dc34a14542b82e260efd81752279d860e9961f05f07.jpg)  
图1异构蜂窝网络通信系统

根据文献[12]，路径损耗模型如式(1)所示。其中： $d$ 代表发射机与接收机之间的距离（单位为 $\mathbf { m }$ )； $f _ { c }$ 为载频。

$$
P L = 3 6 . 7 \mathrm { l g } \left( d \right) + 2 2 . 7 + 2 6 \mathrm { l g } \left( f _ { c } \right)
$$

信道增益由路径损耗和小尺度衰落构成，所以信道增益可以表示为式(2)。其中： $P L ^ { a , b }$ 和 $h ^ { a , b }$ 分别代表a和 $\boldsymbol { \mathbf { b } }$ 之间的路径损耗和小尺度衰落系数。

$$
G ^ { a , b } = P L ^ { a , b } h ^ { a , b }
$$

为了研究干扰最严重的情况，假设 $\mathrm { ~  ~ N ~ }$ 个信道资源全部被C个宏蜂窝用户占用，如果一个宏蜂窝用户只能占用一个信道，则 $N = C$ 。 $\mathrm { ~ J ~ }$ 个微蜂窝用户和 $\mathrm { ~ D ~ }$ 个D2D用户分别复用这 $\mathrm { ~  ~ N ~ }$ 个信道资源。二进制变量 $ { \boldsymbol { X } } _ { c } ^ { n }$ 、 $\boldsymbol { X } _ { j } ^ { n }$ 和 $ { \boldsymbol { X } } _ { d } ^ { n }$ 为1时表示宏蜂窝用户 $\mathrm { ~  ~ c ~ }$ 、微蜂窝用户j和D2D用户d使用信道 $\mathfrak { n }$ ，否则为 $0$ 。

宏蜂窝用户 $\mathrm { ~  ~ c ~ }$ 在信道 $\mathfrak { n }$ 上的信干噪比为

$$
S I N R _ { c } ^ { n } = { \frac { P ^ { c } G ^ { c , B } } { \displaystyle \sum _ { j \in W } X _ { j } ^ { n } P ^ { j } G ^ { j , B } + \sum _ { d \in H } X _ { d } ^ { n } P ^ { d } G ^ { d , B } + N _ { 0 } } }
$$

其中： $P ^ { c }$ 为宏蜂窝用户 $\mathbf { \Psi } _ { c }$ 的发射功率； $P ^ { d }$ 和 $P ^ { j }$ 是D2D用户 $d$ 和微蜂窝用户 $j$ 的发射功率； $G ^ { c , B }$ 是宏蜂窝用户 $\mathbf { \Psi } _ { c }$ 到宏基站B的信道增益; $G ^ { j , B }$ 是微蜂窝用户 $j$ 到宏基站B的信道增益； $G ^ { d , B }$ （204号是D2D用户 $d$ 到宏基站B的信道增益； $N _ { 0 }$ 是噪声功率。

微蜂窝用户 $j$ 在信道 $n$ 上的信干噪比为

$$
S I N R _ { j } ^ { n } = \frac { P ^ { j } G ^ { j , b _ { j } } } { \displaystyle \sum _ { c \in { \cal M } } X _ { c } ^ { n } P ^ { c } G ^ { \mathrm { c } , b _ { j } } + \displaystyle \sum _ { d \in { \cal H } } X _ { d } ^ { n } P ^ { d } G ^ { d , b _ { j } } + N _ { 0 } }
$$

其中： $b _ { j }$ 为微蜂窝用户 $j$ 接入的微蜂窝基站； $G ^ { j , b _ { j } }$ 是微蜂窝用户 $j$ 到微蜂窝基站 $b _ { j }$ 的信道增益； $\boldsymbol { G } ^ { c , b _ { j } }$ 是宏蜂窝用户 $\boldsymbol { \mathbf { \mathit { c } } }$ 到微蜂窝基站 $b _ { j }$ 的信道增益； $\boldsymbol { G } ^ { d , b _ { j } }$ 是 D2D用户 $d$ 到微蜂窝基站 $b _ { j }$ 之间信道增益。

当多个D2D用户复用同一个信道资源时，D2D用户不但要受到宏蜂窝用户和微蜂窝用户的干扰，还要受到在此信道上其他D2D用户的干扰，所以D2D用户 $d$ 在信道 $n$ 上的信干噪比为

$$
S I N R _ { d } ^ { n } = \frac { P ^ { d } G ^ { d _ { t } , d _ { r } } } { \displaystyle { \sum _ { c \in M } X _ { c } ^ { n } P ^ { c } G ^ { c , d _ { r } } + \sum _ { j \in W } X _ { j } ^ { n } P ^ { j } G ^ { j , d _ { r } } + \sum _ { i \in H , i \ne d } X _ { i } ^ { n } P ^ { d } G ^ { i , d _ { r } } + N _ { 0 } } }
$$

其中： $G ^ { d _ { t } , d _ { r } }$ 是D2D用户 $d$ 发射方 $d _ { t }$ 与接收方 $d _ { r }$ 之间的信道增益； $G ^ { c , d _ { r } }$ 是宏蜂窝用户 $\mathbf { \Psi } _ { c }$ 到D2D 接收方 $d _ { r }$ 的信道增益； $G ^ { j , d _ { r } }$ （204号是微蜂窝用户 $j$ 到D2D 接收方 $d _ { r }$ 的信道增益； $G ^ { i , d _ { r } }$ 是D2D用户 $i$ 到D2D接收方 $d ,$ 的信道增益。

# 1.2问题规划

本文在宏蜂窝用户和微蜂窝户信道资源分配都已确定，并且保证宏蜂窝用户和微蜂窝用户通信服务质量的前提下，以最大化系统的总容量为目标函数给D2D用户分配信道。假设每个信道上可以允许两个D2D用户复用，根据香农公式，可以得到优化问题的目标函数及约束条件为式(6)\~(11)

$$
\begin{array} { l } { { \displaystyle \operatorname* { m a x } _ { X _ { c } ^ { n } , X _ { j } ^ { n } , X _ { d } ^ { n } , ( c \in M , j \in W , d \in H ) } T \Big ( X _ { c } ^ { n } , X _ { j } ^ { n } , X _ { d } ^ { n } \Big ) = } } \\ { { \displaystyle \operatorname* { m a x } _ { \mathrm { \tiny { \Psi } } } \operatorname* { m a x } _ { X _ { j } ^ { n } , X _ { d } ^ { n } , ( c \in M , j \in W , d \in H ) } \sum _ { n = 1 } ^ { N } \biggl [ \sum _ { c \in M } X _ { c } ^ { n } \log _ { 2 } ( 1 + S I N R _ { c } ^ { n } ) + } } \\ { { \displaystyle X _ { c } ^ { n } , X _ { j } ^ { n } , X _ { d } ^ { n } , ( c \in M , j \in W , d \in H ) _ { n = 1 } \biggl [ \sum _ { c \in M } X _ { c } ^ { n } \log _ { 2 } ( 1 + S I N R _ { d } ^ { n } ) + } } \end{array}
$$

$$
S I N R _ { c } ^ { n } \geq S I N R _ { c , t h r e s h o l d } ^ { n } , \forall c \in M
$$

$$
S I N R _ { j } ^ { n } \geq S I N R _ { j , t h r e s h o l d } ^ { n } , \forall j \in W
$$

$$
S I N R _ { d } ^ { n } \geq S I N R _ { d , t h r e s h o l d } ^ { n } , \forall d \in H
$$

$$
\sum _ { n = 1 } ^ { N } X _ { j } ^ { n } \leq 1 , \sum _ { j \in W } X _ { j } ^ { n } \leq 1 , \forall j \in W
$$

$$
\sum _ { n = 1 } ^ { N } X _ { d } ^ { n } \leq 1 , \sum _ { d \in H } X _ { d } ^ { n } \leq 2 , \forall d \in H
$$

式(7)\~(9)保证了宏蜂窝用户，微蜂窝用户和 D2D用户的信噪比大于门限值。式(10)保证一个微蜂窝用户最多复用一个信道资源，并且一个信道上最多允许一个微蜂窝用户通信。式(11)保证一个D2D用户最多复用一个信道资源，并且一个信道资源最多能同时被两个D2D用户复用。

# 2 基于多对一Gale-Shapley 算法的D2D 通信资源分配方案

在1.2节中，由式(6)\~(10)定义的目标函数和约束条件属于混合整数非线性优化问题，最优解需要遍历所有的可能分配，复杂度较高，因此本文研究采用复杂度较低，逼近最优解的次优方案。本方案首先分别建立D2D用户和信道的偏好列表。每个D2D用户根据在不同信道上的系统容量建立偏好列表Due_list，偏好列表中每行的第一个值具有最高的偏好值。表1展示了三个D2D用户的偏好列表。其中，第二个D2D用户的偏好列表为 $D u e \_ l i s t ( 2 ) = \left[ 3 , 5 , 2 , 4 , 1 \right]$ ，表示第二个D2D用户最想复用的信道资源为3。按类似方法，每个信道根据让不同的D2D用户通信可实现的系统总容量的大小建立信道偏好列表Channel_list。

表1D2D用户偏好列表  

<html><body><table><tr><td>D2D用户对</td><td colspan="5">偏好级别</td></tr><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>1</td><td>3</td><td>4</td><td>5</td><td>1</td><td>2</td></tr><tr><td>2</td><td>3</td><td>5</td><td>2</td><td>4</td><td>1</td></tr><tr><td>3</td><td>1</td><td>2</td><td>3</td><td>5</td><td>4</td></tr></table></body></html>

本方案还需要定义以下参数：

a)信道与D2D用户之间联系的集合Association，集合Association(k)表示信道 $\mathbf { k }$ 包含已经匹配的D2D用户；

b)D 对D2D用户最想复用的信道列表 $\mathrm { P r } e = \left[ \delta _ { 1 } , . . . , \delta _ { k } , . . . , \delta _ { \scriptscriptstyle D } \right]$ 由用户偏好列表可知 $\delta _ { \scriptscriptstyle k }$ 是 $D u e \_ l i s t ( k )$ 列表的第一个元素；

c)定义Cluster $\left( \mathbf { k } \right)$ 为目前最想复用信道 $\mathbf { k }$ 的 D2D用户对集合，例如 $C l u s t e r ( k ) = \left\{ 1 , 3 , 4 \right\}$ 表示当前第1、3和4个D2D用户对最想复用信道 $\mathbf { k }$ ，即 $\delta ( d ) = k \big ( \forall d \in C l u s t e r ( k ) \big )$

d)没有匹配的D2D用户对集合表示为UNMATCH;

e)信道总数 $\mathrm { ~  ~ { ~ N ~ } ~ }$ ，迭代次数为Iteration，最大迭代次数为MAXGEN。

算法的伪码如算法1所示

# 算法1 基于多对一Gale-Shapley 的D2D 通信资源分配算法

<html><body><table><tr><td colspan="2">3While iteration<MAXGENdo</td></tr><tr><td>4</td><td>if UNMATCH=O</td></tr><tr><td colspan="2">5 for k=1 to N do</td></tr><tr><td>6</td><td>当前信道k上的D2D用户对数S=0</td></tr><tr><td>7</td><td>If Cluster(k)≠O and S<=2</td></tr><tr><td>8</td><td>根据信道k 的偏好列表Channel_list（k）从集合Cluster(k)中找</td></tr><tr><td></td><td>到优先级最高的D2D 用户d</td></tr><tr><td>9</td><td>if 满足式(7)~(11)约束条件</td></tr><tr><td>10</td><td>Association(k)=Association(k)U {d}</td></tr><tr><td>11</td><td>UNMATCH=UNMATCH-{d}</td></tr><tr><td>12</td><td>S=S+1</td></tr><tr><td>13</td><td>else</td></tr><tr><td>14</td><td>Due_list(d)=Due_list(d)-δd，更新Pre 和 Cluster(k)</td></tr><tr><td>15</td><td>end</td></tr><tr><td>16</td><td>Cluster(k)=Cluster(k)-{d}</td></tr><tr><td>17</td><td>end</td></tr><tr><td>18</td><td>for rE Cluster(k)</td></tr><tr><td>19</td><td>Due_list(r)=Due_list(r)-δr</td></tr><tr><td>20</td><td>end</td></tr><tr><td>21</td><td>end</td></tr><tr><td>22</td><td>if Due_list(w)=O (w∈H)</td></tr><tr><td>23</td><td>UNMATCH=UNMATCH-{w}</td></tr><tr><td>24</td><td></td></tr><tr><td></td><td>end</td></tr><tr><td>25</td><td>end</td></tr><tr><td>26</td><td>Iteration=Iteration+1</td></tr></table></body></html>

算法1的步骤如下：

a)首先初始化D2D用户和信道的偏好列表，集合Association，未被匹配的D2D对集合UNMATCH，发射功率等参数。

b)第3\~27行是算法的核心部分，只有达到最大迭代次数，循环才会终止。算法第7\~17行表示对于每个子信道k，首先从集合Cluster(k)中找到一个当前最想复用信道k的D2D用户对d，然后检查该用户对是否满足式(7)\~(11)的约束条件。如果满足条件，则继续根据信道k的偏好列表往Association(k)中添加D2D用户，直到有两个D2D对和信道k分享资源，否则更新D2D 用户偏好列表，Cluster(k)和Pre。

c)算法第18\~20行表示当信道k上已有两个D2D对。如果集合Cluster(k)中还有想复用信道k的D2D对r，则信道k拒绝分配资源给D2D对r，更新D2D对r的偏好列表。

d)算法第22\~24行表示在算法的最后阶段，某些D2D用户因为信干噪比门限的限制无法找到合适的信道资源，本文也假设这种用户已找到合适的资源，从集合UNMATCH中移除这些D2D用户。

# 3 仿真结果

# 3.1 仿真环境建立

为了验证所提算法性能，在异构蜂窝网络环境下进行仿真实验。宏蜂窝小区半径设为 $1 0 0 0 \mathrm { m }$ ，蜂窝用户及D2D用户在小区中为独立的泊松点过程分布。具体的系统仿真参数设置如表2所示。采用蒙特卡洛方法每次随机生成2000个分布场景，最后将本文算法得到的系统性能结果取平均值。假设每个宏蜂窝用户占据单个独立的信道，且每个信道上都有一个微蜂窝用户与宏蜂窝用户复用资源，接入的D2D用户需要根据当前的信道状态选择合适的信道进行通信。因为本文假设一个信道资源上最多可以有两对D2D用户通信，所以每个信道上接入的D2D用户对的数量设置为2。

表2仿真实验中的参数设置  

<html><body><table><tr><td>参数名</td><td>参数取值</td></tr><tr><td>小区半径</td><td>1 000 m</td></tr><tr><td>D2D 用户能共享的信道数</td><td>2</td></tr><tr><td>宏蜂窝用户数(信道数目)</td><td>10~50</td></tr><tr><td>微蜂窝基站密度</td><td>1e-5个/m²</td></tr><tr><td>信道带宽</td><td>1.8e§ Hz</td></tr><tr><td>D2D用户发射功率</td><td>20 dBm</td></tr><tr><td>宏、微蜂窝用户发射功率</td><td>20 dBm</td></tr><tr><td>高斯白噪声密度</td><td>-174dBm/Hz</td></tr></table></body></html>

# 3.2 复杂度及性能分析

采用MATLAB仿真软件对提出的多对一Gale-Shapley 算法的D2D通信资源分配算法进行仿真，并与基于延迟接受算法（DARA）、随机资源分配算法[13]和最优算法[14]在复杂度及性能上进行了对比。

由于文献[11]中基于延迟接受算法的资源分配方案是在宏蜂窝网络环境下建立的，为了使文献[11]的算法适应宏蜂窝和微蜂窝组成的异构蜂窝网络，本文将匹配的双方改为D2D用户和信道。D2D用户根据在信道上所实现的系统容量建立偏好列表；信道根据让不同D2D通信实现的系统总容量的大小建立偏好列表。另外，当信道第一次被分配给D2D用户时也需要检查宏蜂窝用户和微蜂窝用户的通信服务质量，这个方案能够使D2D用户找到合适的信道，获得D2D用户和信道之间的一个稳定匹配，但只允许一个信道最多和一个D2D用户分享资源。随机资源分配算法只需满足式(7)\~(11)的条件即可获得一种分配方案。

# 3.2.1复杂度分析

四种资源分配算法的复杂度分析如下：a）随机资源分配算法复杂度随着蜂窝用户数目的增加线性增长，即为O（C）（C为宏蜂窝用户数)，算法计算量最低；b）DARA方案的最坏情况下的复杂度为 $\mathrm { O } ( \mathrm { C } ^ { 2 } )$ ，平均复杂度为Clog(C)（C为宏蜂窝用户数)；c）最优算法是满足约束条件下的穷举搜索算法，需要遍历所有可能的分配方式，计算量最高；d）本文提出方案的复杂度为 $\mathrm { O } ( \mathrm { N } ^ { 2 } )$ (N为信道数量)，计算量相比随机分配算法适当增加，但比最优算法计算量显著降低。

# 3.2.2性能分析

图2的仿真比较了四种资源分配算法的系统总容量。从图中可以看出，系统总容量随着信道数目的增加而变大。当信道数目一定时，本文提出算法的系统总容量优于文献[11]的算法和随机资源分配算法，逼近最优解。因为所提算法允许多个D2D 用户复用同一个蜂窝用户信道资源，所以获得的系统总容量优于文献[11]中的算法，而随机资源分配算法只是在保证用户通信服务质量的前提下随机进行资源分配，并没有进行系统容量的优化，所以性能最差。

![](images/e67308b8e6bc8b4589fd2ccec9b488d6863e4dcb6510d175b4f36ba061f4216c.jpg)  
图2分配算法的系统总容量对比

图3的仿真比较了四种分配算法的最大允许接入D2D用户数。从图中可以看出，本文所提算法允许接入的最大D2D用户数优于文献[11]的算法和随机分配算法，但达不到理论值。因为本文所提算法能够实现信道和D2D用户的一对多匹配，所以能够让更多的D2D用户同时进行通信。但是由于SINR门限的限制，可允许的连接D2D用户数并不能达到理论值。

![](images/6023021acae84affb50d6a733259228e7eaf5406229837662131499107473fab.jpg)  
图3分配算法的最大允许接入D2D用户数对比

图4表示SINR门限设置为-10dB时，蜂窝用户的SINR累计分布函数（CDF)。从图中可以看出，宏蜂窝用户和微蜂窝用户的 SINR均大于指定的门限值。因为SINR是保证通信服务质量的重要指标，所以本文所提算法能够保证蜂窝用户通信的服务质量。

![](images/15ad94e18bfccec1aab2b9a5274d3b6259bdaf2b993c610d479a628df6650291.jpg)  
图4蜂窝用户的SINR累计分布函数

图5的仿真结果表明SINR门限对系统总容量的影响。从图中可以看出，系统总容量随着SINR门限的增加而变小。当SINR门限超过10dB时，系统总容量不再变化，达到最小值。这说明为了保证蜂窝用户的通信服务质量，不允许为D2D用户分配信道资源进行通信，只有宏蜂窝用户和微蜂窝用户可以进行通信。

![](images/4dc9b3ab9a10543d44d017a77c589fbd53fcacb1850b7841d8c0770383df2ff2.jpg)  
图5SINR门限值对系统总容量的影响

图6的仿真结果表明本文所提算法具有较快的收敛性。从图中可以看出，系统总容量随着迭代次数的增加逐步变大，当达到一定迭代次数时，系统总容量趋于稳定，表示已经分配完所有的D2D用户。系统中D2D用户越多，所需的迭代次数就越多，但总体上算法收敛所需的迭代次数较少，5\~8次即可收敛，计算复杂度较低。

![](images/d308baa5ec747d8215808e572c7f7bc1d0163aa82d8b8e055950c3535c776933.jpg)  
图6本文所提算法的收敛性

# 4 结束语

本文提出的基于多对一Gale-Shapley 算法的分配算法能够有效地解决异构蜂窝网络环境下D2D用户复用蜂窝用户信道的资源分配问题。为了提高无线频谱的利用率，该算法允许多个D2D用户共享一个蜂窝用户的信道资源，通过设置SINR门限保证蜂窝用户和D2D用户的通信服务质量。根据实现的系统容量建立D2D用户和信道偏好列表，最大化系统总容量目标函数。通过MATLAB仿真对所提出算法、基于延迟接受算法的资源分配算法、随机资源分配算法以及最优的穷举搜索算法的系统总容量和最大允许接入的D2D用户数进行了比较和分析，并且分析了所提算法的收敛性和蜂窝用户通信服务质量。仿真结果表明，本文提出的算法收敛速度快、复杂度较低，获得的系统总容量接近最优算法。

# 参考文献：

[1]Kaufman B,Aazhang B.Cellular networks with an overlaid device to device network [C]// Proc of the 42nd Asilomar Conference on Signals, Systems and Computers.2008: 1537-1541.   
[2]Doppler K,Rinne M, Wijting C,et al. Device-to-device communication as an underlay to LTE-advanced networks [J].IEEE Communications Magazine,2009,47(12): 42-49.   
[3]Peng Tao,Lu Qianxin，Wang Haiming，et al. Interference avoidance mechanisms in the hybrid cellular and device-to-device systems [C]//Proc of the 20th International Symposium on Personal, Indoor and Mobile Radio Communications.2009: 617-621.   
[4]Goratti L, Steri G,Gomez K M,et al. Connectivity and security in a D2D communication protocol for public safety applications [Cl//Proc of the 11th International Symposium on Wireless Communications Systems.2014: 548- 552.   
[5]Janis P,Koivunen J,Ribeiro C B,et al. Interference-avoiding MIMO schemes for device-to-device radio underlaying cellular networks [C]//Proc of the 2Oth International Symposium on Personal, Indoor and Mobile Radio Communications.2009:2385-2389.   
[6]Islam MT,TahaAE M,Akl S,et al.A local search algorithm for resource allocation for underlaying device-to-device communications [C]// Proc of IEEE Global Communications Conference.2015:1-6.   
[7]Hasan M,Hossain E.Distributed resource allocation in D2D-enabled multitier cellular networks: an auction approach [C]// Proc of IEEE International Conference on Communications.2015: 2949-2954.   
[8] Zhang Rongqing, Cheng Xiang, Yang Liuqing,et al. Interference-aware graph based resource sharing for device-to-device communications underlaying cellular networks [C]// Proc of IEEE Wireless Communications and Networking Conference.2013: 140-145.   
[9] Sun Hongguang，Wildemeersch M,Sheng Min,et al. D2D enhanced heterogeneous cellular networks with dynamic TDD [J]. IEEE Trans on Wireless Communications,2015,14 (8): 4204-4218.   
[10] Gale D, Shapley L S.College admissions and the stability of marriage [J]. The American Mathematical Monthly,1962,69 (1): 9-15.

[11] Islam M T,Taha A M,Akl SG,et al.A stable matching algorithm for resource allocation for underlaying device-to-device communications [C// Proc ofIEEE International Conference on Communications.2O16:1-6.

[12] ITU-R Recommendation M.1225.Guidelines for evaluation of radio transmission technologies for IMT-2000 [S]. International Telecommunication Union.1997.

[13] Sun Hongguang,Sheng Min,Wang Xijun,et al.Resource allocation for

maximizing the device-to-device communications underlaying LTEadvanced networks [C]// Proc of IEEE//CIC International Conference on Communications in China-Workshops.2013:60-64. [14] Gurobi. Optimization-the best mathematical programming solver [CP/OL]. http://www. gurobi.com.