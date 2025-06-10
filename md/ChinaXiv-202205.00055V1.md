# 多基站下基于DRL的RAN切片资源分配

马英洪，江凌云†

(南京邮电大学 通信与信息工程学院，南京 210003)

摘要：在第五代移动通信中，网络切片被用来为各种业务提供一个最佳的网络。针对多基站下的RAN切片场景，以往的资源分配方法在切片的数量发生变化时无法满足切片的需求而且只适用于特定的场景，针对这个问题，提出了一种实现最佳资源分配且与切片数无关的方法。该方法先利用Ape-X方法(一种DRL方法)将资源分配给切片，再经过切片到基站的资源映射和用户资源分配来满足用户的需求。仿真结果表明，所提出的方法能够根据切片的状态和需求分配资源，分配了必要数量的RB 以满足切片的需求而且不受切片数量变化的影响。同时，该方法也具有很高的通用性能和扩展性。

关键词：多基站；网络切片；深度强化学习；无线接入网；资源分配 中图分类号：TN929.5 doi:10.19734/j.issn.1001-3695.2021.12.0706

RAN slice resource allocation in multi base stations based on DRL

Ma Yinghong, Jiang Lingyun† (College of Telecommunications &Information Enginering,Nanjing UniversityofPosts&Telecommunication,Nanjing 210003, China)

Abstract: Inthe fifth generation mobilecommunication,network slicing is used to provide anoptimal network forvarious services.For the RAN slice scenario under multi base stations,the previous resource allcation methods can not meet the demand ofslices when the numberof slices changes,and are onlysuitable for specific scenarios.To solve this problem,this paper proposes a method to achieve the best resource allocation independentof the numberof slices.This method first uses Ape-X method (a DRL method)allcate resources to slices,and then meet the needs of users through the resource mapping from slices to base stationsand userresource allocation.The simulationresults show that the proposed methodcanallocate resourcesaccording tote stateanddemandofslices,alocate thenecessrynumberofRBs tometthedemandofslices,and is notaffected bythechangeof thenumberof slices.Atthe sametime,this methodalso has high general performanceand scalability.

Keywords: multi base station; network slice; deep reinforcement learning; radio access network; resource allocation

# 0 引言

第五代移动通信(5G)网络作为解决日益增长的移动数据通信需求的解决方案引起了人们的关注。5G改善了第四代移动通信(4G)网络中未得到适当解决的一些领域，例如更高的数据速率、更低的端到端(EndtoEnd,E2E)延迟、更高的可靠性和大量的设备连接[I]。此外，5G中的服务类型也越来越多样化，例如需要高数据速率和低延迟的虚拟现实(VirtualReality,VR)，以及需要大量设备连接和低延迟的工厂自动化[2]。传统的通信网络主要用来服务单一的移动宽带业务，无法适应未来5G多样化的业务场景。因此，为了在同一个物理网络基础设施上同时支持多种具有不同性能要求的业务场景，满足多样化的业务需求，网络切片技术应运而生。5G使用网络切片(networkslice)技术，以切片为单位提供适合各种服务的网络[3]。切片设置了吞吐量、延迟和可靠性等要求。为了满足这些需求，网络资源被分配到切片上。网络切片通常包括接入网切片(包括无线接入和固定接入)和核心网切片[4]。其中，无线接入网(RadioAccess Network，RAN)必须要面对资源短缺的问题。而且，在实际分配无线资源的时候，切片的状态会不断变化，比如切片中的用户数量、业务的到达率以及用户的分布等。因此，需要一种能够根据切片状态有效地分配无线资源同时能够满足切片要求的方法[5.6]。

文献[7\~12]是几种在单基站环境下的无线资源分配方法文献[7]中的方法通过从没有需求的切片中分配资源来满足切片的需求。但是，没有评估资源分配的利用率。存在向切片分配过多资源的可能性。文献[8]提出了一种考虑切片需求和资源利用率的方法。但是无法对每个切片实现资源隔离，会受到其他切片的负载的影响。在文献[9]中采用了一种最早截止时间优先(EarliestDeadlineFirst，EDF)调度策略用于无线资源分配，可以使得在高负载下满足切片对于时延的要求，但是会严重影响对于吞吐量有需求的切片的性能。文献[10]提出了一种在C-RAN场景下基于在线学习的网络切片虚拟资源分配算法，以最大化平均网络切片和速率为目标，同时考虑到了平均网络切片约束以及网络平均回传链路带宽消耗约束。但是没有考虑到切片的资源利用率。在文献[11]中的方法，利用了深度强化学习，同时考虑到了切片的满意度和资源利用率，而且实现了切片间的资源隔离。但是，仅评估了特定的场景。5G中假设了各种服务场景，文献[11]中的方法可能并不适用。文献[12]提出了一种基于在线双向拍卖的网络切片资源调度机制。该机制能够在为高优先级切片服务的同时可以保证低优先级切片用户的QoS需求。但是没有考虑到切片间的资源隔离问题。

以上的文献研究的都是在单基站下的无线资源分配方法在多基站环境下的分配情况会不同。文献[13\~15]是几种在多基站环境下的资源分配方法。在文献[13]中，研究了RAN中混合业务的动态网络切片策略，考虑到了用户对时延和速率的QoS需求。但是对切片数量的设置不够灵活。文献[141中的算法考虑到了基站的回传容量，对不同切片的用户的时延和数据速率的需求也满足的很好。但是在低负载的情况下资源的利用率不高。文献[15]设计并实现了一个两层网络虚拟化基板(NetworkVirtualizationSubstrate，NVS)算法，基于切片的优先级和可实现速率实现切片的资源调度。在这种方法中切片在各个基站上均匀分配资源，可能会导致在有的基站上分配资源过多，在有的基站上分配过少。从而导致用户的满意度和资源利用率不够好。

针对上述文献中的问题，本文提出了一种在多基站环境下使用DRL分配满足切片要求的无线资源的方法。而且，即使切片的数量发生变化，所提出的方法也能为各个切片分配资源以满足用户的QoS需求。

# 1 系统模型

# 1.1网络模型

本文考虑 5G 基站 $k$ ， $k \in K$ ， $K$ 是一个基站集。基站为切片 $s$ 提供服务， $s \in S$ ， $s$ 是切片集。为了满足用户的服务质量(QualityofService，QoS)需求，必须在切片之间分配无线资源。在5G系统中，无线资源用资源块(ResourceBlock，RB)来表示。RB是基于时域和频域划分的资源单位。一个RB 由12 个子载波组成，每个子载波的间隔为 $1 5 \mathrm { k H z }$ 。时域以传输时间间隔(Transmission TimeInterval,TTI)为单位，TTI的长度为1ms。TTI是调度RB的最小单位，在每个TTI将RB分配给用户。

基站 $k$ 将RB分配给用户以满足用户的需求，用户 $\boldsymbol { u }$ 在一个 RB 上的可实现速率计算为： $r _ { k , u } = B \log _ { 2 } ( 1 + \frac { p _ { k } g _ { k , u } } { N _ { 0 } B } )$ 。其中，B表示一个RB 的带宽，即 $1 5 \mathrm { k H z } \times 1 2 \mathrm { = } 1 8 0 \mathrm { k H z } .$ 。 $p _ { k }$ 表示基站 $k$ 的发射功率， $g _ { k , u }$ 表示用户 $\mathbf { \Omega } _ { u }$ 在基站 $k$ 一个RB上的信道增益，$N _ { 0 }$ 表示噪声功率谱密度。用户 $u$ 在不同基站上的RB的可实现速率不同，因此，用户按照不同基站上RB的可实现速率由大到小设立等级，用户 $\boldsymbol { u }$ 对基站 $k$ 的等级记为 $\delta _ { u , k }$ ，可表示基站 $k$ 对用户 $u$ 的重要性。

不同切片的用户的QoS需求不同，在本文中，将需求分为两种：吞吐量需求和时延需求。对于需要高吞吐量的用户在每个TTI为其分配RB；对于有时延需求的用户在数据包到达时分配RB。假设用户 $\mathbf { \Omega } _ { u }$ 对吞吐量的需求为 $R _ { u }$ ，也就是对数据速率的需求。用户 $u$ 对时延的需求为 $T _ { u }$ ，用户 $\mathbf { \Omega } _ { u }$ 的数据包大小为 $p _ { u }$ 。因此，用户 $u$ 对数据速率的需求 $R _ { \alpha } = { \% }$ 。由于TTI是最小的时间调度单位，因此，用户 $\boldsymbol { u }$ 的数据速率需求$R _ { u }$ 需要转换成1ms上的速率需求。此外，本文将切片的需求设为用户的QoS需求，同一切片内的用户的QoS需求相同。

本文定义了两个指标：网络切片需求满意度(NSDS,network slicedemand satisfaction)和 RB 利用率(RBUR，RBusage ratio)。第一个指标NSDS用来衡量网络是否满足了该业务的需求。NSDS 表示为： $N S D S = \frac { \sum _ { k = 1 } ^ { | k _ { s } | } u _ { k } } { \mid k _ { s } \mid }$ 。 $k _ { s }$ 表示切片 $s$ 中的用户数量。 $u _ { k }$ 表示用户是否满足了切片需求。

$$
u _ { k } = \{ 0 , \ \ast \} \in \mathcal { V } \} _ { 1 } ^ { \pm } \frac { \sqrt { \Xi } } { \sqrt { \Xi } } \ast \} \hat { \zeta }
$$

NSDS越接近1，就说明切片中用户的QoS需求满足的越好，就可以为服务提供更合适的切片。RBUR是一个用来衡量资源利用率的指标，RBUR表示为 $R B U R = U R B _ { A R B }$ 。URB表示消耗的RB数量，ARB表示分配给切片的RB数量。RBUR越接近1，RB的利用率就越高，资源利用率就越高。

当NSDS很低而RBUR很高时，分配给切片的RB都被消耗掉，切片中有的用户没有满足切片的需求。因此，给切片分配更多的RB可以改善NSDS。通过最大化NSDS和RBUR，可以实现以最少的RB数量满足切片的需求。

# 1.2问题模型

RB分配问题可以分成两步：切片间资源分配和切片内资源分配。切片间资源分配问题包括分配RB给切片和切片到基站的资源映射。切片间资源分配问题建模如下：

$$
\begin{array} { l } { { \displaystyle \operatorname* { m a x } \sum _ { i = 1 } ^ { S } N S D S _ { i } \times R B U R _ { i } } } \\ { { \displaystyle s . t . \sum _ { i = 1 } ^ { S } A R B _ { i } \le A l l R B } } \\ { { \displaystyle \sum _ { i = 1 } ^ { S } R _ { s , k } \le L _ { k } , \forall k \in K } } \end{array}
$$

目标是最大化切片的资源利用率RBUR和切片满意度NSDS的乘积，以最小的RB分配满足切片需求。式(2)中第一个约束表示所有切片所分配的RB 数量不能超过基站所拥有的RB总数。第二个约束表示在每个基站下，所有切片获得的RB的总数量不能超过该基站所拥有的RB数量。

在确定了切片在每个基站上的资源分布后，网络切片控制器执行切片内资源分配。切片中的用户优先接入RB等级最高的基站，这样可以最大化满足用户的QoS需求。在基站$k$ 下，设定分配给切片 $s$ 的RB集为 $M _ { s , k }$ ，切片内资源分配问题建模如下：

$$
\begin{array} { l } { \displaystyle \operatorname* { m a x } _ { A } \big \{ U _ { s , k } \big \} , \forall s \in S } \\ { \displaystyle s . t . : \displaystyle \sum _ { n \in M _ { s , k } } \sum _ { u \in U _ { s , k } } a ( u , n ) \leq R _ { s , k } } \\ { \displaystyle \sum _ { u \in U _ { s , k } } a ( u , n ) \leq 1 , \forall n = 1 , . . . R _ { s , k } } \end{array}
$$

在式(3)中，A是分配矩阵，如果将第 $n$ 个RB分配给第$u$ 个用户，则元素 $a ( u , n )$ 为1，否则为 $0$ 。 $U _ { s , k }$ 表示第 $s$ 个切片在第 $k$ 个基站上的效用，本文考虑 $\alpha$ -utility [16],如式(4)所示。

$$
U _ { s , k } = \sum _ { u \in U _ { s , k } } \left\{ \frac { \big ( \sum _ { n \in M _ { s , k } } a ( u , n ) r _ { u , n } \big ) ^ { 1 - \alpha } } { 1 - \alpha } , \alpha \neq 1 \right.
$$

本文选择 $\scriptstyle a = 1$ ，即比例公平方式。在式(3)中，第一个约束表示在基站 $k$ 下，每个切片内的用户分配的RB的总数不能超过该切片可用的资源。第三个约束确保一个RB只能分配给一个用户。

# 2 算法设计

# 2.1方法概述

在RAN切片中，需要一种以最小RB分配满足切片需求的方法，该方法与切片数量无关。因此，本文提出了一种利用Ape-X[7]的灵活RB分配方法。由于使用了Ape-X,learner学习的模型包括基于每个actor 收集的各种经验。因此，当切片数量变化时无须重新训练模型即可进行RB分配。在现有方法中，agent控制的切片数量是固定的，因此如果训练和评估之间的切片数量不同，则需要重新训练模型。在所提出的方法中，一个agent将 RB 分配给一个切片，当有多个切片时，agent会被多次调用。这种设计实现了与切片数量无关的RB分配。在每次RB分配后，网络切片控制器会更新切片在每个基站上的资源配置，以便BS可以在每个调度时期适应系统状态。

此外，代理学习以最少所需的RB数量分配来满足切片的需求，从而最大化满足需求的切片数量，同时提高RB的利用效率。在本文中，为每种服务类型定义一个切片。当切片中的用户数变为1或更多时生成切片，在用户数变为0时终止切片。所提出的算法的流程图如图1所示。

![](images/de03318ee9b703623d0b6704d47a83f1b69c8b728fbd54c4c2893cabcf4af2e9.jpg)  
图1所提出的算法的流程图

# 2.2利用Ape-X的RB分配

所提出的方法采用Ape-X方法，将分布式学习应用于DRL。其中，一个actor控制一个切片，当切片的数量发生变化时，actor的数量也随之变化，切片的数量没有限制，分配RB不依赖于切片的数量。所提出的方法可以灵活设置切片数量和分配RB。learner学习一种策略，该策略以最少的RB数量满足切片的需求。分配方法的架构如图2所示。由于切片数量没有限制，所以有1到N个切片，每个切片包含多个用户。除了管理切片之外，网络切片控制器还桥接了基站和actor。actor是Ape-X代理，和切片的数量相同。由于actor使用了learner训练的策略，所有actor都具有相同的控制策略。在每个资源调度时期，执行RB的分配操作。基站收集每个切片的状态信息，包括切片中的用户是否满足了QoS需求以及切片的资源利用率等信息。随后，基站将切片状态通知给网络切片控制器。网络切片控制器根据切片状态生成状态和奖励，并将其传递给切片对应的actor。actor根据策略生成动作，把动作输出到网络切片控制器。当网络切片控制器接收到每个切片的动作时，它会计算分配给它们的RB数量，在学习过程中，奖励、状态和动作作为经验传递给回放记忆(replaymemory)。在切片级资源更新后，资源需要映射到所有基站上。2.3节介绍了基站资源更新的算法流程。在进行基站级资源更新后，网络切片控制器通知各基站每个切片在其上的资源分布。各个基站为每个切片中的用户分配RB，以满足用户的吞吐量和时延需求。

![](images/85460093f62a2b43e6d675891e26778105e29a3c034cd74faba621c4990acfff.jpg)  
Fig.1Flow chart of the proposed method   
图2RB分配方法的架构  
Fig.2Architecture ofRB allocation method

本文利用深度强化学习解决切片间资源分配问题，作出最优决策。在下面详细介绍强化学习架构中各个要素的内容。

状态是代理确定动作的重要因素。如果状态被设计为尽可能地消除不确定元素，则学习结果会更好。基于这一点，本文将学习RB分配时的状态分为表1中给出的三种类型。这三种类型分别是NSDS相关、RBUR相关和切片状态。首先，NSDS相关，对于代理识别切片的需求很重要。第二个，RBUR相关，帮助代理识别切片的RB分配情况。第三个是为了解决状态的模糊性。

表1RB 分配的状态设计  
Tab.1State design of RB allocation   

<html><body><table><tr><td>状态类型</td><td>值</td></tr><tr><td>NSDS 相关</td><td>NSDS</td></tr><tr><td rowspan="3">RBUR相关</td><td>吞吐量需求</td></tr><tr><td>时延需求</td></tr><tr><td>RBUR</td></tr><tr><td rowspan="3">切片状态</td><td>分配RB的数量</td></tr><tr><td>到达数据包的数量</td></tr><tr><td>传输数据包的数量 缓冲区中数据包的数量</td></tr></table></body></html>

动作是代理对环境执行的控制。所提出的方法为每个切片分配RB。由actor输出的动作记为 $a$ ， $a$ 可以为负，0或正。 $a$ 为负表示分配给切片的RB数量减少， $a$ 为0表示分配给切片的RB数量不变， $\mathbf { \Delta } _ { a }$ 为正表示分配给切片的RB数量增加。动作 $\mathbf { \Delta } _ { a }$ 的取值范围为[-0.8,-0.6,-0.4,-0.2,0,0.2,0.4,0.6,0.8]，动作 $\mathbf { \Delta } _ { a }$ 为九个维度。在 $_ { \mathrm { t + l } }$ 时刻，分配给切片的RB数量可以计算为 $A R B _ { t + 1 } = A R B _ { t } \times ( 1 + a )$ 。计算出的ARB不考虑分配给其他切片的RB。然而，由于基站具有有限数量的RB，分配给切片的RB总数可能会超过基站的所有RB。因此，网络切片控制器根据算法1调整分配给每个切片的RB数量。对每个切片计算时间t处分配的RB数和NSDS的乘积，按照从小到大的顺序进行排列。按照这个次序为切片分配资源。这使得需要较少RB的切片或具有较小NSDS的切片在时间 $_ { \mathrm { t + l } }$ 时优先分配。这样可以避免需要更多RB的切片占用多余的资源，提高了资源利用率。另一方面，可以改善切片的NSDS。

奖励向代理表明一个动作对于一个状态是好是坏。在所提出的算法中，目标是以最少的RB分配满足切片的需求，最大化NSDS和RBUR是学习的目标。奖励 $\boldsymbol { r }$ 被设计为

$$
r = \left\{ \begin{array} { l l } { 1 , ( A R B = 0 , B u f f = 0 ) } \\ { 0 , ( A R B = 0 , B u f f > 0 ) } \\ { 0 , ( A R B > 0 , B u f f = 0 ) } \\ { N S R S \times R B U R , ( A R B > 0 , B u f f > 0 ) } \end{array} \right.
$$

ARB是分配给切片的RB数量，Buff是存储在缓冲区中的数据包的数量。当缓冲区为空时，不需要分配RB，因此如果ARB为0，则 $\boldsymbol { r }$ 为1；ARB不为0， $\boldsymbol { r }$ 为0。当缓冲区有数据包而ARB为0，即切片有需求但没有被分配RB， $\boldsymbol { r }$ 为0。当数据包存储在缓冲区中并且ARB不为0 时，NSDS和RBUR会随着分配的ARB 而变化。因此， $\boldsymbol { r }$ 是根据 NSDS和RBUR计算得出的。

DQN 的框架如图3所示，其中包含两个神经网络，$Q ( s , a ; \theta )$ 代表预测Q网络， $\theta$ 表示预测神经网络的参数，用于评估当前状态-动作对的价值； $Q ( s , a ; \theta ^ { * } )$ 代表目标Q网络，用于计算目标值， $\theta ^ { * }$ 表示目标神经网络的参数。损失函数 $L ( \theta )$ 计算为： $L ( \theta ) { = } E [ ( y _ { t } - Q ( s _ { t } , a _ { t } ; \theta ) ) ^ { 2 } ]$ ， $y _ { t } = r _ { t + 1 } + \gamma \operatorname* { m a x } _ { a \in A } Q ( s _ { t + 1 } , a ; \theta ^ { \ast } )$ 。 $y _ { t }$ 是目标值， $y _ { t } - Q ( s , a ; \theta )$ 即为TD(TemporalDifference)误差 $\delta _ { t }$ 。利用损失函数计算梯度。计算表达式为

$$
\frac { \hat { \sigma } L ( \theta ) } { \hat { \sigma } \theta } { = } \frac { \hat { \sigma } E [ ( y _ { t } - Q ( s _ { t } , a _ { t } ; \theta ) ) ^ { 2 } ] } { \hat { \sigma } \theta }
$$

本文使用RMSProp优化算法更新网络参数，每经过M步迭代，复制预测网络的参数 $\theta$ 给目标网络参数 $\theta ^ { * }$ 。

Ape-X 使用了DDQN[18]，利用预测网络选择动作，目标网络计算Q值，降低了高估。此外，Ape-X还使用了多步引导目标(multistep bootstrap target)[19]，即考虑多步的奖励，使学习的效果更好。因此，目标值 $y _ { t }$ 变为

$$
\begin{array} { r l } & { y _ { t } = r _ { t + 1 } + \gamma r _ { t + 2 } + \cdots + \gamma ^ { n - 1 } r _ { t + n } } \\ & { \qquad + \gamma ^ { n } Q ( s _ { t + n } , \arg \operatorname* { m a x } Q ( s _ { t + n } , a ; \theta ) ; \theta ^ { * } ) } \end{array}
$$

由于采用了决斗网络[20]， $Q ( s _ { t } , a _ { t } ; \theta )$ 被划分为状态价值函数 $V ( s _ { t } ; \theta )$ 和优势函数 $A d \nu ( s _ { t } , a _ { t } ; \theta )$ 。状态价值函数仅和状态 $s _ { t }$ 有关，与动作 $a _ { t }$ 无关。优势函数同时和状态 $s _ { t }$ 和动作 $a _ { t }$ 都有关。Q值表示如下：

$$
Q ( s _ { t } , a _ { t } ; \theta ) = V ( s _ { t } ; \theta ) + ( A d \nu ( s _ { t } , a _ { t } ; \theta ) - \frac { 1 } { \vert A \vert } \sum _ { a \in A } A d \nu ( s _ { t } , a ; \theta ) )
$$

其中，A表示动作集，A是动作集的维度。actor与环境交互产生经验 $( s , a , r , s ^ { \prime } )$ 。本文采用 $\varepsilon$ -greedy 策略，actor以ε的概率选择动作值最高的动作，以概率1-g选择随机动作。actor根据其网络参数计算经验的TD误差，根据TD误差设置经验的优先级 $p _ { k }$ ， $p _ { k } = \mid \delta _ { k } \mid$ ， $k$ 是经验的编号。经验 $( s , a , r , s ^ { \prime } , p _ { k } )$ 被存入经验回放中，预测网络和目标网络使用优先级采样代替随机采样，从经验回放中提取经验。经验的采样概率为∑。，每次抽取batch 个样本。

在更新网络参数后，计算batch个样本的TD 误差和优先级，然后更新经验回放中这些样本的优先级。随着学习的进行，动作值被更新，旧经验的准确性降低，存储在经验回放中的旧经验的优先级被更新为低。当经验回放被装满时，删除旧经验。

每隔 $N$ 步，actor从预测网络处复制经过训练的参数，以将其参数更新为最新版本。这样，通过优先学习具有较大TD误差的经验，同时执行分布式学习来加速学习，从而提高了学习效率。

![](images/94ce1c147ceb38d5d5ef6bf2f1ec7089f95666bb78f2a4938c46bf5ba08eb227.jpg)  
图3DQN框架

图4显示了所提出方法的神经网络结构。该网络结构有一个输入层、几个隐藏层和一个输出层。因为状态维度被设计为输入维度，所以输入层是八维的。输出层的维度为9维，和动作维度相同。隐藏层有128个神经元。第4个隐藏层分支到状态值和优势函数。使用这些规格进行了 $2 \times 1 0 ^ { 6 }$ 步训练。训练大约需要2天。

![](images/3d41cc8f37b6a95044aa6731c9b065ecadd0ca208358711f05ece9db2d73a270.jpg)  
Fig.3DQN framework   
图4神经网络结构  
Fig.4Neural network structure

算法1切片的RB分配

输入： $C R { B } _ { t + 1 } ^ { s }$ 是在 $^ { \ t + 1 }$ 时刻计算出的分配给切片s的RB数， $A R B _ { t } ^ { s }$ 是在t时刻分配给切片 $s$ 的RB 数，NSRS是切片 $s$ 的网络切片需求满意度，S是切片集， $A L \bot R B$ 是所有基站所拥有的全部资源。  
输出： $A R B _ { t + 1 } ^ { s }$ 是在 $^ { \ t + 1 }$ 时刻分配给切片 $s$ 的RB数。  
1)开始：  
2)for $s \in S$   
3） $\mathsf { w l } [ s ]  &  = A R B _ { t } ^ { s } \times N S R S ^ { s }$   
4)end for  
5)remainRB=AllRB  
6)for $s \in S$ #按照 $\boldsymbol { \mathsf { W } }$ 的升序提取 $s$   
7) if $C R { B } _ { t + 1 } ^ { s }$ <remainRB  
8) $A R B _ { t + 1 } ^ { s } = C R B _ { t + 1 } ^ { s }$ ：  
9) remainRB $\mathbf { \tau } = \mathbf { \tau }$ remainRB - $A R B _ { t + 1 } ^ { s }$ （204号  
10) else  
11) ARBi+= remainRB  
12) ${ \mathrm { r e m a i n R B } } = 0$   
13) end if  
14)end for  
15)结束

# 2.3切片到基站的资源映射

# 2.3.1基站资源更新

在切片资源更新后，资源必须映射到所有基站上。算法2 描述了基站资源更新过程。基站资源更新依赖于基站对特定切片的权重。切片中的用户在不同基站上的RB等级 $\delta _ { { u , k } }$ 不同，可以得到切片 $s$ 在基站 $k$ 上的等级： $\overline { { r } } _ { s , k } = \sum _ { u = 1 } ^ { \vert U _ { s } \vert } \delta _ { u , k } , \forall u \in U _ { s }$ 。因此，切片 $s$ 在基站 $k$ 上的权重可以表示为： $r _ { - } r a t _ { s , k } = \frac { \overline { { r } } _ { s , k } } { \sum _ { k = 1 } ^ { K } \overline { { r } } _ { s , k } }$ ，权重 $r _ { - } r a t _ { s , k }$ 表示了基站 $k$ 对切片 $s$ 的重要性。在每个调度时间，这些权重都会更新，以更新基站资源。切片 $s$ 在基站 $k$ 上占有的资源计算为： $R _ { s , k } = A R B _ { s } \times r \_ r a t _ { s , k }$ 。计算出的 $R _ { s , k }$ 没有考虑到每个基站的容量限制，所有切片在基站 $k$ 上分配的RB总数可能会超出基站 $k$ 的容量。因此，需要调整切片在每个基站上所分配的资源。遍历所有基站，将分配资源量超出基站容量的基站添加进待重新分配队列Q_BS。

对于属于Q_BS队列的基站 $k$ ，先确定属于该基站 $k$ 的用户。根据用户的RB等级得到切片 $s$ 在基站 $k$ 上的用户集合 $U _ { s , k }$ ， $k = \operatorname* { m a x } \{ \delta _ { u , k } ( k ) \}$ ，用户 $u$ 优先选择RB 等级最高的基站接入。切片 $s$ 在基站 $k$ 上的速率需求为： $W _ { s , k } = \sum _ { u = 1 } ^ { | U _ { s , k } | } R _ { u }$ ， $R _ { u }$ 表示用户 $\mathbf { \Omega } _ { u }$ 的需求速率。因此，切片 $s$ 在基站 $k$ 上的权重可以计算为： ，由此得到，在基站k上分配给切片$s$ 的RB 数为： $R _ { s , k } = L _ { k } \times \omega _ { s , k }$ ， $L _ { k }$ 为基站 $k$ 所拥有的 RB 总数。

在对基站的资源进行重新分配后，有的切片分配的资源总数可能会低于ARB，需要将基站剩余的资源分配给切片。首先检查每个基站的剩余资源量以及分配资源不够的切片。还有剩余资源的基站队列设为QreBS，分配RB数不够的切片队列设为Q_slice。遍历基站队列Q_reBS，比较切片队列Q_slice中的所有切片在该基站上的权重 $\boldsymbol { \omega } _ { s , k }$ ，按照权重由大到小的次序，将基站的剩余RB资源分配给切片直到满足切片的RB需求或基站的资源全部被分配。

算法2基站资源更新

输入：分配给切片 $s$ 的RB数 $A R B ^ { s }$ ，切片 $s$ 在基站 $\boldsymbol { h }$ 上的等级 $\overline { { r _ { s , k } } }$ ，用户 $\boldsymbol { u }$ 的请求速率 $\scriptstyle { R _ { u } }$ ，切片集S，基站集 $\boldsymbol { \kappa }$ ，切片缺少的RB数reRB，基站 $\boldsymbol { h }$ 的RB容量 $L _ { k }$ ，基站 $\boldsymbol { h }$ 剩余的RB资源Lk_remain，待重新分配切片队列Q_slice，有剩余资源的基站队列Q_reBS，在 $^ { \ t + 1 }$ 时刻分配给切片 $s$ 的RB数 $A R B _ { t + 1 } ^ { s }$ 。

输出： $R _ { s , k }$ 是基站 $\boldsymbol { h }$ 分配给切片 $s$ 的RB数。

1)开始：初始化Q_slice，Q_reBS 队列 2)Stepl：初步资源映射 3)for $s \in S$ （20 4）for $k \in K$ （2 5） （204号 $R _ { s , k } = A R B ^ { s } \times \frac { \overline { { r } } _ { s , k } } { \sum _ { k = 1 } ^ { K } \overline { { r } } _ { s , k } } ~ ;$ 6 end 7)end 8)for $k \in K$ （204号 9） $B S _ { - } e x c e e d ^ { k } = \sum _ { s = 1 } ^ { | s | } R _ { s , k }$ ; 10) $\mathrm { i } \mathsf { f } \ B S _ { - } e x c e e d ^ { k } > L _ { k }$ （204 11) for $s \in S$ 12） 获取一个用户集 $U _ { s , k } , ~ k = \operatorname* { m a x } \{ \delta _ { u , k } ( k ) \}$ （204号 13） $W _ { s , k } = \sum _ { u = 1 } ^ { \vert U _ { x , k } \vert } R _ { u } \ ;$ （20 14） （204号 $\omega _ { s , k } = \frac { \overline { { r } } _ { s , k } \times W _ { s , k } } { \sum _ { s = 1 } ^ { | S | } \overline { { r } } _ { s , k } \times W _ { s , k } } \~ ;$ 15） （204号 $R _ { s , k } = L _ { k } \times \omega _ { s , k }$ ; 16) end 17) end 18） if BS_exceed ${ { \mathit { \Sigma } } ^ { k } } < { { \cal { L } } _ { k } }$ （2 19） （204号 $L _ { k _ { - } r e m a i n } = L _ { k } - B S \_ e x c e e d ^ { k } ;$ 20) $\mathcal { Q } \_ r e B S . \mathrm { a d d } ( k ) ;$ 21) end 22)end 23)Step2：基站剩余资源分配 24)for $s \in S$ （204号 25） sunRB =∑R； 26) if $s u m R B ^ { s } < A R B ^ { s }$ 27） $r e R B ^ { s } = A R B ^ { s } - s u m R B ^ { s } \ ;$ 28） Q_slice.add(s); 29) end 30)end 31)for $k \in Q \_ r e B S$ （20 32） 按照切片 $s$ ，在基站 $\boldsymbol { h }$ 上的权重 $\omega _ { s , k }$ 由大到小进行排序，得 到Rank 33） $\mathrm { i f ~ l e n } ( Q \_ s l i c e ) { = } { = } 0$ （20 34) break; 35) end 36） for $s \in R a n k$ （20 37） if $L _ { k _ { - } r a m a i n } \geq r e R B ^ { s }$ 38） （204 $r e R B ^ { s } { = } 0 ;$ 39) Q_slice.delete(s); 40） （204号 $L _ { k \_ r e m a i n } = L _ { k \_ r e m a i n } - r e R B ^ { s } \ ;$ 41) else 42） reRB = reRBs -L_remain ； 43） end 44） if $L _ { k _ { - } r e m a i n } = = 0$ 45） Q_reBS.delete(k); 46) break; 47) end 48) end 49)end 2.3.2用户资源分配和连接控制

为了解决切片内资源分配的问题，本文提出了一个迭代的解决方案。分配矩阵A最开始为空，然后通过迭代将 RB分配给用户。在这里定义一个增益因子：$g _ { u } ^ { \ ( i + 1 ) } = \log ( \hat { R } _ { u } ^ { ( i ) } + r _ { u , \hat { n } } ) - \log ( \hat { R } _ { u } ^ { ( i ) } )$ 。 $\hat { R } _ { u } ^ { \ ( i ) }$ 表示用户 $\mathbf { \Omega } _ { u }$ 已分配的速率， $r _ { u , \hat { n } }$ 表示用户 $\boldsymbol { u }$ 在 $\hat { n }$ 上的可实现速率， $\hat { n }$ 是还未分配的RB。如果用户 $\boldsymbol { u }$ 具有最大的增益因子而且该用户的数据速率需求还未得到满足，则将 $\hat { n }$ 分配给该用户。然后进入下一次迭代，当所有的RB被分配完成或者所有用户的需求都被满足时，迭代停止。

当所有基站下的所有切片的迭代分配过程完成后，检查是否所有用户都满足了需求以及切片的资源是否都被利用了。因为可能接入一个基站的用户过多而分配的资源不够，接入其他基站的用户少而分配的资源很多。因此，为了充分利用资源以及满足用户需求，将切片在其他基站上的资源分配给未满足需求的用户。对于未满足需求的用户，按照 RB 等级次序，检查其他基站是否有剩余的RB资源，如果有，就将用户连接到下一个基站，根据比例公平方式迭代将该基站剩余的RB资源分配给重新接入该基站的用户们，直到切片中的用户都满足了需求或分配给切片的资源全部被利用就停止迭代。

# 3 仿真结果

# 3.1仿真概述

所提出的方法是根据它是否达到满足切片需求的最小RB分配来评估的，而且不受切片数量变化的影响。在所提出的方法中，必须首先训练RB分配的模型。然后使用经过训练的模型评估所提出的方法。评估分为三种。第一种表明所提出的方法在所创建的特定场景中适当地实现了RB 分配。第二种展示了基于随机生成的多个场景评估模型的通用性能在第三种类型中，本文评估切片数量与性能之间的关系，并描述了所提出方法的可扩展性。

# 3.2 训练

所提出方法中的模型从切片状态中学习最大化NSDS和RBUR的RB分配。在5G中，假设了各种类型的服务。因此，仿真场景是随机生成的，模型使用各种类型的服务进行训练。表2给出了用于训练的场景。表3给出了用于训练和评估的共同参数。每次仿真后都会生成一个新场景。切片的数量固定为三个切片，但在仿真过程中，切片的数量从0到3不等，因为切片的开始和结束时间不同。此外，每个切片的用户数量、数据包生成间隔和数据包大小都不同。切片的需求为吞吐量需求、时延需求或两者都有。根据长期演进(Long TermEvolution,LTE）规范，子载波间隔和TTI分别设置为 $1 5 ~ \mathrm { k H z }$ 和 $1 ~ \mathrm { m s }$ 。系统带宽设置为 $2 0 ~ \mathrm { M H z }$ ，每个TTI的RB 总数为100。由于RB是根据规范分组的，因此每个基站控制的RB数为25。RB分配的控制间隔为1ms，和TTI一样。

表4 给出了Ape-X 的参数值，和[17]中的相同。actor 的数量是根据计算机的性能设置的参数。训练电脑的配置为AMD$3 7 0 0 \mathrm { x }$ CPU，32GB内存，rtx 2070super 显卡。进行仿真的电脑为 $3 7 0 0 \mathrm { x }$ CPU，16GB内存。本文使用一台计算机进行学习，六台计算机进行仿真。在一台计算机上运行5个仿真，而一个仿真有4个actor，所以总共有120个actor(6 计算机 $. { \times } 5$ 个仿真 $. { \times } 4$ 个actor)。折扣因子决定了考虑未来奖励的折扣因子。在RB分配中，切片状态也会快速变化，因此根据状态变化快速分配RB是很重要的。因此，本文将折扣因子设置为0.5以最大化短期奖励。出于同样的原因，将 $n$ 设为1。

# 3.3评估结果

# 3.3.1RB分配评估

在本节中，本文评估所提出的方法是否能在切片数量不同的场景中将RB分配给切片。所考虑的移动网络场景基于5G网络标准，所使用的参数汇总在表3和5。在给定的$5 0 0 \mathrm { m } { \times } 5 0 0 \mathrm { m }$ 区域内，四个基站均匀分布。每两个相邻的BS保持 $1 2 0 \mathrm { m }$ 的固定距离。路径损耗(PathLoss,PL)模型定义如下： $\mathrm { P L } ( \mathrm { d B } ) { = } 2 0 \log 1 0 ( \mathrm { d } ) { + } 2 0 \log 1 0 ( \mathrm { f } ) { - } 2 7 . 5 5 ,$ 。其中，d(以米为单位)和f(以MHz为单位)分别表示用户-基站的距离和信道频率。基于5G切片类别，本文定义了4个切片：消息业务、应用程序、音频、视频，每个切片匹配一种业务。每个切片具有不同的用户数量、数据包长度和切片需求。通过设置每个切片的切片开始和结束时间来模拟切片数量的变化。在仿真中，切片数量从最少两个切片到最多四个切片不等。具体的参数如表5所示。切片中的用户数量随时间而变，如图5所示。

表2训练场景-Uniform[min,max]表示从min 到 max 的均匀分布Tab.2Training scenario-Uniform[min,max],represents a uniform  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>仿真时间</td><td>30s</td></tr><tr><td>基站数量</td><td>4</td></tr><tr><td>基站间距离</td><td>120m</td></tr><tr><td>最大用户数mu</td><td>400</td></tr><tr><td>切片数量</td><td>4</td></tr><tr><td>切片的开始时间st</td><td>Uniform[1,10][s]</td></tr><tr><td>切片的结束时间</td><td>st+Uniform[1,20][s]</td></tr><tr><td>切片中的用户数量</td><td>Uniform[1,200]，所有切片的用户总数不超过mu</td></tr><tr><td>数据包生成间隔pi</td><td>Uniform[1,1000][ms]</td></tr><tr><td>数据包大小ps</td><td>Uniform[1,65535][Bytes]</td></tr><tr><td>吞吐量需求</td><td>tcxps×1000/pi[Bps],tc=Uniform[0.8,1],当tc=0.8时，对吞吐量没有需求</td></tr><tr><td>时延需求</td><td>dl=Uniform[3,1000][ms],当dl=1000时，对时延没有需求</td></tr></table></body></html>

表3训练和评估的共同参数  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>区域大小</td><td>500×500[m²]</td></tr><tr><td>用户移动性</td><td>随机路点模型</td></tr><tr><td>基站发射功率</td><td>46dBm</td></tr><tr><td>子载波间隔</td><td>15kHz</td></tr><tr><td>TTI</td><td>1[ms]</td></tr><tr><td>系统带宽</td><td>20[MHz]</td></tr><tr><td>噪声功率谱密度</td><td>-174dBm/Hz</td></tr><tr><td>控制间隔</td><td>1[ms]</td></tr></table></body></html>

表4Ape-X参数

Tab.4Ape-X parameters   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>Actor数量</td><td>120</td></tr><tr><td>目标网络更新间隔</td><td>2500[step]</td></tr><tr><td>网络参复制间隔</td><td>100[step]</td></tr><tr><td>训练batch 大小</td><td>512</td></tr><tr><td>学习率α</td><td>0.00025/4</td></tr><tr><td>折扣因子γ</td><td>0.5</td></tr><tr><td>优化算法</td><td>RMSProp</td></tr><tr><td>多步 bootstrap 目标n</td><td>1</td></tr></table></body></html>

本文中对比了两种方法。方法描述如下所示。

a)hard-slicing。hard方法是一种将所有RB按切片数量划分的方法。切片 $s$ 的 ARB 可以计算为： $A R B ^ { s } = A l l R B ^ { \prime } { } _ { \mathrm { t } { \jmath } }$ 片数量。

b)NVS(NetworkVirtualization Substrate)方法[18]。资源基于系统中切片的权重来分配，切片的权重计算如下：$\omega _ { s } = \sum _ { u = 1 } ^ { | U _ { s } | } R _ { u } , \forall u \in U _ { s }$ 。定义为切片 $s$ 中的所有用户的聚合数据速率请求。因此，分配给切片 $s$ 的 RB 计算为： $\boldsymbol { A R B ^ { \prime } } = \boldsymbol { A l l R B } \times \frac { \boldsymbol { \omega } _ { s } } { \sum _ { s = 1 } ^ { | s | } \omega _ { s } }$ 。

在 NVS方法中，为每个切片提供的资源量在基站之间平均分配。本文所提出的方法以及hard方法采用2.3节所述的资源映射方式。

![](images/7e9918c35b8aed83ff0c1b84384e58a7738a62520893ee29ba0fbc489883b049.jpg)  
图5用户数量变化图  
Fig.5Changes in the number of users

Tab.3Common parameters for training and evaluation   
表5评估场景  
Tab.5Evaluation scenario   

<html><body><table><tr><td>参数</td><td colspan="3">值</td></tr><tr><td>仿真时间</td><td colspan="3">600s</td></tr><tr><td>基站数量</td><td colspan="3">4</td></tr><tr><td>基站间距离</td><td colspan="3">120m</td></tr><tr><td>用户的总数</td><td colspan="3">290</td></tr><tr><td>切片的数量</td><td colspan="3">4</td></tr><tr><td>切片编号</td><td>1</td><td>2</td><td>3 4</td></tr><tr><td>服务类型</td><td>消息业务</td><td>应用程序</td><td>音频 视频</td></tr><tr><td>用户数量</td><td>25</td><td>200</td><td>20 45</td></tr><tr><td>数据包到达率/包/s</td><td colspan="3">Uniform[80,120]</td></tr><tr><td>数据包大小/Byte</td><td>476</td><td>76</td><td>147 1055</td></tr><tr><td>吞吐量需求/Mbps</td><td>无</td><td>0.07</td><td>无 0.82</td></tr><tr><td>时延需求/ms</td><td>10</td><td>无</td><td>50 100</td></tr><tr><td>切片开始时间/s</td><td>0</td><td>0</td><td>100 200</td></tr><tr><td>切片结束时间/s</td><td>600</td><td>600</td><td>400 500</td></tr></table></body></html>

图6(a)到6(c)显示了NSDS、RBUR、ARB和仿真时间之间的关系。这里，RB以一毫秒的间隔分配给切片，但NSDS和 RBUR 是以一毫秒为间隔测量的一秒的平均值，ARB是1s 的总ARB( $1 0 0 \times 1 0 0 0 \mathrm { R B } )$ 。NSDS的结果表明，所提出的方法几乎完全满足切片需求。在所提出的方法中，当切片的数量在110s、205s、400s 发生变化时，NSDS不会下降。基于这些结果，即使切片的数量发生变化，切片的性能需求也能得到满足。

在hard方法中，RB分配和切片的数量有关，因此，对数据速率需求低的切片1、3总是能够满足切片需求。切片2中的用户数量多，在320s到400s之间时，切片2的用户数量不断增加，但是分配的RB数量没有增加，资源分配不足，导致NSDS降低。切片4需要高吞吐量，在350s到400s之间时，用户数量增加，对数据速率的需求也会增加，但是ARB不会变化，NSDS下降。

在图6(c)中，依据nvs方法，分配给切片的资源和切片的数据速率需求有关。数据速率需求越高，获得的资源就越多。因此，从图(c)中可以看出，在大约90s和160s之间，切片1的需求都能得到满足，在160s到200s之间，随着切片2的用户数量不断增加，切片2对于数据速率的需求也越来越高，切片2获得的资源也变多，导致切片1的NSDS下降。在200s和500s之间，切片4因为其高吞吐量需求，而占有了过多的资源。在400s左右时，切片 4的用户数量达到最大，获得RB最多，其他切片的NSDS也达到最低。切片3由于其数据速率需求低而且用户数量少，因此获得的RB 数量少，NSDS 很低，无法满足切片对于时延的需求。

根据RBUR结果，所提出方法的RBUR约为0.75或更高。这表明RB的过度分配低于 $2 5 \%$ 。在hard方法中，由于将RB均匀地分配给切片，而不管切片的状态和需求，因此RBUR的表现很差，在每个切片中都存在过度分配，如图(b)所示。对于nvs方法，切片2和切片4的数据速率需求高，过度分配严重，RBUR性能表现很差。切片1和切片3对数据速率的需求低，导致分配的RB不足，所分配的RB都被利用了，因而资源利用率比较高。

综上所述，基于NSDS和RBUR的结果，所提出的方法对比其他方法在NSDS和RBUR两个指标上表现更好，能够根据切片的状态和需求分配资源，分配了必要数量的RB以满足切片的需求而且不受切片数量的变化的影响。

![](images/953c7a811b620e1f8f1499ae8659a04f194701f20640b6a3655ed993ebcc99a6.jpg)  
Fig.6RB allocation comparison chart

# 3.3.2通用性能评估

在本节中，本文使用模拟各种服务的场景来评估所提出方法的通用性能。作为包括DRL在内的通用机器学习，可以通过仅训练特定数据来估计目标数据的最优解决方案。但是不能对其他未经训练的数据进行正确的估计。这称为过度适应环境。当只针对特定的时区、地点或服务时，这种模型是有效的。但是，如果模型只用于特定情况，则使用网络切片的优势就丧失了。这是因为在RAN中，会有很多的服务类型，而网络切片是一种将网络适用于各种服务的技术。

使用第3.2节中的随机生成场景评估所提出方法的通用性能。由于该场景随机确定用户数量、数据包生成间隔和切片需求，因此可以模拟各种业务类型。需要注意的是，并非所有生成的场景都可以通过现有服务来解释。本文使用与训练中不同的种子值来评估未经训练的场景，以显示模型的通用性能。

总共测试了3000个场景。评估指标为NSDS和RBUR，是一秒内测量值的平均值。结果表示为累积分布函数 (CDF)和测量数据的平均值。如果 NSDS 和 RBUR 较高，则表明它们在各种随机生成的场景中都较高。

图7(a)和7(b)显示了NSDS评估结果。所提出的方法的平均NSDS约为0.92，几乎满足了切片需求。对比方法的平均NSDS 都在0.7以下。由图7(b)可以看出，hard切片方法的NSDS在没有用户满足需求的0.0处以大约 $2 8 \%$ 分布，在所有用户都满足需求的1.0处以大约 $50 \%$ 分布。结果表明，切片中的一个用户有 $28 \%$ 的概率无法满足需求。对于nvs方法，切片中的一个用户有 $31 \%$ 的概率无法满足需求，切片中的用户的需求全部得到满足的概率是 $50 \%$ 。

所提出的方法的NSDS在0.0处以不到 $10 \%$ 分布，在1.0处大约 $82 \%$ 分布。结果表示切片中的一个用户无法满足需求的概率不到 $10 \%$ ，切片中的用户的需求全部被满足的概率达到了 $82 \%$ 。根据以上结果，表明所提出的方法实现了高水平的通用性能，几乎可以满足各种场景下的切片需求。

图8(a)和8(b)显示了RBUR评估结果。所提出的方法的平均RBUR约为0.77。对比方法的平均RBUR都在0.7之下，资源过度分配都超过了 $30 \%$ 。hard方法的平均RBUR最低，因为hard切片将所有RB平均分配给各个切片。有的切片会存在过度分配。nvs方法根据不同切片的数据速率请求进行分配。但是可能有的切片请求的速率比其他切片高太多，导致有的切片分配了过多资源从而RBUR很低。

综上所述，对于随机生成的场景，所提出的方法能够有效地将RB分配给切片，几乎满足了各种切片的需求，实现了高水平的通用性能，同时资源利用率也很高。

![](images/210e30d261fabc6ed8c7f95318b803bd0e398d742e1b9e27d3d720603e62ce4d.jpg)  
图6RB分配对比图  
图7NSDS 的通用性能Fig.7General performance of NSDS

![](images/6617f704e5fcdacdcb3036f7e5ceb53aa41dc853d845e069a2050b7ecd7d8631.jpg)  
图8RBUR的通用性能

# 3.3.3扩展性评估

本文通过评估切片数量与性能之间的关系来评估所提出方法中切片数量的可扩展性。此评估场景使用第3.2节中使用的随机生成场景，切片数量根据每个场景的均匀分布从1到8中选择。评估时的切片数量不是根据场景创建时设置的切片数量来计算的，而是通过同时运行的切片数量来计算的。例如，如果切片数量设置为7，但同时运行的切片数量为3，则计为3个切片。评估指标为NSDS和RBUR，测量结果为一秒内测量值的平均值。

图9显示了切片数量与NSDS的关系。对于所有测试方法，NSDS 随着切片数量的增加而降低。当切片数量增加时，需要更多的RB。NSDS减少是因为无法保证切片所需的RB数。当切片数量达到4个及以上时，所提出方法的NSDS比其他方法高出了0.2以上，实现了更好的效果。在切片数量少于8个时，NSDS为0.8以上，切片中有 $80 \%$ 以上的用户完全满足了QoS需求。当切片数量为8时，NSDS约为0.78。

对比方法中，nvs方法表现最差，因为一方面可能有的切片对于数据速率需求高，而有的切片对于数据速率需求低，导致对数据速率需求低的切片获得的RB数量过少，也就使得NSDS很低；另一方面，nvs方法在基站之间均等分配资源，可能会使得在某个基站上分配过多资源，有的基站分配过少，导致用户接入的基站资源过少而降低了需求满意度。hard方法将资源均等分配给各个切片，当切片数量增多时，每个切片获得资源变少，导致有的切片分配资源不足，需求满意度下降。

图10显示了切片数量和RBUR之间的关系。在所提出的方法中，当切片数量超过4个时，RBUR随着切片数量的增加而降低，在切片数量为8时，RBUR为0.7。RB分配过多是为了在分配RB时能够可靠地满足切片的需求。所提出的方法学习了将NSDS优先于RBUR的分配方式，原因和奖励的设计有关。在设计奖励时综合考虑了资源利用率和切片需求满意度。如果所有用户都不能满足需求，则NSDS为0，而如果有用户使用了RB，则RBUR就大于0。奖励是NSDS乘以RBUR，如果其中一个变为0，则奖励也为0。在学习时，接近0的NSDS会被优先考虑以改善切片的需求满意度，导致RB的过度分配。

![](images/9fcbe81a785fc206c4779afb0047ce365ea8c4c8dc63e6bc0a10ce4fce332a31.jpg)  
Fig.8General performance ofRBUR

在nvs方法和hard方法中，当切片数量为1时，hard方法和nvs方法的RBUR不到0.3，因为这两种方法会将所有的资源都分配给这个切片导致资源利用率过低，当切片数量增加时，会有更多的切片需要资源，也就使得切片的资源利用率得到了提高。但是因为这两种方法的局限性，RBUR的表现都比所提出的方法要差，过度分配严重。

基于NSDS和RBUR的结果，即使切片数量发生变化，本文所提出的方法也能分配RB以满足切片对于吞吐量和时延的需求。此外，所提出的方法仅通过使用训练模型创建或终止执行RB分配的actor来应对切片数量的变化。综上所述，可以说所提出的方法在切片数量方面具有很高的可扩展性。

# 4 结束语

本文主要研究无线接入网(RAN)切片。在多基站环境下，为了能够有效地分配无线资源同时满足切片的需求，本文提出了一种使用Ape-X的RB分配方法，该方法不受切片数量的影响。仿真结果表明，所提出的方法能够根据切片的状态和需求分配资源，分配了必要数量的RB以满足切片的需求而且不受切片数量的变化的影响，同时对于随机生成的场景也实现了高水平的通用性能。

所提出的方法是基于LTE中的TTI设计的，在5G中，TTI是可变的，未来会在这个方向上继续研究。

![](images/4bc9f1641a938c06581c28918c152b48ae3c6fde0ab9323b5084b559a2f6cc36.jpg)  
图9NSDS 扩展性评估 Fig.9NSDS scalability evaluation   
图10RBUR 扩展性评估 Fig.10RBUR scalability evaluation

# 参考文献：

[1]NGMN Alliance.5G White Paper [EB/OL].[2015-02-17]. https://www. ngmn.org/wp-content/uploads/NGMN_5G_White_Paper_V1_0.pdf.   
[2]Elayoub SE,Fallgren M,Spapis P,et al.5G service requirements and operational use cases:Analysis and METIS II vision [C]//2o16 European Conference on Networks and Communications (EuCNC).Athens: IEEE, 2016:158-162.   
[3]AfolabiI, Taleb T, Samdanis K,et al.Network slicing and softwarization: A survey on principles,enabling technologies,and solutions [J]. IEEE Communications Surveys&Tutorials,2018,20 (3):2429-2453.   
[4]NGMN Alliance.Description of network slicing concept [EB/OL]. [2018-02-20]. http://www. ngmn. org/fileadmin/user_upload/160113_Network_Slicing_vl_0.pdf.   
[5]Foukas X,Patounas G,Elmokash A,et al. Network Slicing in 5G: Survey and Challenges [J].IEEE Communications Magazine,2017,55 (5):94- 100.   
[6]Elayoubi SE,Jemaa SB,Altman Z,et al.5G RAN Slicing for Verticals: Enablers and Challenges[J].IEEE Communications Magazine,2019,57 (1): 28-34.   
[7]ShrivastavaR,Samdanis K,Bakry A.On Policy Based RAN Slicing for Emerging 5G TDD Networks [C]//2018 IEEE Global Communications Conference(GLOBECOM).Emirates,United Arab Emirates:IEEE, 2018:1-6.   
[8]Chang C Y, Nikaein N, Spyropoulos T.Radio Access Network Resource Slicing for Flexible Service Execution [C]//IEEE INFOCOM 2018- IEEEConferenceonComputerCommunicationsWorkshops (INFOCOMWKSHPS) .Honolulu,HI,USA:IEEE,2018:668-673.   
[9]Guo T, Suarez A.Enabling 5G RAN Slicing with EDF Slice Scheduling [J].IEEE Transactions on Vehicular Technology,2019,68 (3):2865- 2877.   
[10]唐伦，魏延南，马润琳，等．虚拟化云无线接入网络下基于在线学习 的网络切片虚拟资源分配算法[J]．电子与信息学报,2019,41（7): 1533-1539.(Tang Lun,Wei Yannan,Ma Runlin,et al. Online Learningbased Virtual Resource Allocation for Network Slicing in Virtualized Cloud Radio Access Network[J]. Journal of Electronics & Information Technology,2019,41 (7):1533-1539.)   
[11] Abiko Y,Mochizuki D,Saito TD,et al.Proposal of Allocating Radio Resources to Multiple Slices in 5G Using Deep Reinforcement Learning [C]//2019 IEEE 8th Global Conference on Consumer Electronics (GCCE).Osaka:IEEE,2019:131-132.   
[12]陈前斌，施颖洁，杨希希，等．基于在线双向拍卖的虚拟网络切片资 源调度机制[J].电子与信息学报，2018,40(7):1738-1744.(Chen Qianbin,Shi Yingjie,Yang Xixi,etal.Resource SchedulingMechanism for Virtual Network Slice Based on Online Double Auction [J].Journal ofElectronics & Information Technology,2018,40(7):1738-1744.)   
[13] Sun G L，Xiong K，Boateng G O，et al.Autonomous Resource Provisioning and Resource Customization for Mixed Trafficsin Virtualized Radio Access Network[J].IEEE Systems Journal,2019,13 (3):2454-2465.   
[14] XiongK,Adolphe S Xiang R,Boateng G O,et al.Dynamic Resource Provisioning and Resource Customization for Mixed Traffics in Virtualized Radio Access Network [J].IEEE Access,2019,7:115449- 115453.   
[15] KokkuR,Mahindra R, Zhang H, et al.NVS:A Substrate for Virtualizing Wireless Resources in Cellular Networks [J].IEEE/ACM Transactions on Networking,2012,20 (5):1333-1346.   
[16] Caballero P,Banchs A,Veciana G D,et al.Network slicing games: Enabling customization in multi-tenant networks [J].IEEE/ACM Transactions on Networking,2019,27 (2): 662-675.   
[17] Horgan D,Quan J,Budden D,et al.Distributed prioritized experience Replay [EB/OL].[2018-03-02].http://arxiv.org/abs/1803.00933.   
[18] Hasselt HV,Guez A, SilverD.Deep reinforcement learning with double Q-learning [EB/OL].[2015-12-08].http://arxiv.org/abs/1509.06461   
[19] Sutton R S,Barto A G.Reinforcement Learning:An Introduction [J]. IEEE Transactions on Neural Networks,1998,9(5):1054-1054.   
[20] Wang Z,Schaul T,Hessel M,et al.Dueling network architectures for deepreinforcement learning[EB/OL].[2016-04-5].http://arxiv. org/abs/1511.06581