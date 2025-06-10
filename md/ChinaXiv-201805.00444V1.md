# 认知无线电网络中多目标频谱分配与功率控制

韩韧，高阳，叶孟宇

(上海理工大学光电信息与计算机工程学院上海市现代光学系统重点实验室光学仪器与系统教育部工程研究中心，上海 200093)

摘要：针对Underlay接入方式的认知无线电网络中的功率控制问题进行了研究，提出同时考虑频谱分配和功率控制两个因素。并且为了同时满足用户的多种需求，将网络容量和功耗效率构建成一个多目标优化问题，然后提出了一种基于NSGA-II的改进多目标优化算法对该问题进行建模求解，得到了适合用户不同需求的Pareto最优解集。最后将所提方法与SPEA-II算法进行了实验对比，仿真结果表明，所提方法能够有效地搜索到优化解，并且能够满足不同情况下的频谱和功率分配要求。

关键词：认知无线电；频谱分配；功率控制；多目标优化 中图分类号：TN914 doi:10.3969/j.issn.1001-3695.2018.03.0180

# Spectrum allocation and power control with multi-objective optimization in cognitive radio networks

Han Ren†, Gao Yang, Ye Mengyu (Shanghai KeyLaboratoryofModernOptical System,Engineering Research CenterofOptical Instrument &System,Ministry ofEducation,SchoolofOptical-Electrical& Computer Engineering,Universityof Shanghai for Science&Technology, Shanghai 200093, China)

Abstract:The problem ofpowercontrol incognitiveradio networksbased on Underlayaccessmethod is studied,and two factorsofspectrum alocationand powercontrolareconsidered simultaneously.Inorder to meet themultipleneedsof network users atthe same time,this paper addresses the spectrum allcationand power control with respect tooptimizing both power consumption eficiencyand network capacityincognitiveradio networks.Thenanimproved multi-objectiveoptimization algorithmbasedonNSGA-Iis proposedtosolve theproblem,andtheoptimalsetofParetosolutionssuitablefordiferentusers is obtained.Finally,theproposedmethodisompared withtheSPEA-Ialgorithm,andthesimulationresultsvalidatethatthe proposed strategycan harvest theoptimal solutions eficiently and satisfythe requirements of spectrum allcation and power control in various cases.

Key words: cognitive radio; spectrum allocation; power control; multi-objective optimization

# 0 引言

无线通信技术的迅猛发展和无线应用业务的惊人增长，使得世界对无线电频谱的需求日益增加。与此相对的是无线电频谱资源是由政府或国际机构管理的，并使用固定的频谱分配政策，长期分配给持有授权的机构。这种分配政策导致频谱的利用率在时间和空间上的差异性很大，大约在 $1 5 \% { \sim } 8 5 \%$ ，存在大量未被充分利用的授权频段[1]。因此，消除频谱利用的严重不平衡，充分利用频谱资源，是解决谱匮乏的主要问题。

为了解决频谱资源匮乏的问题，Mitola首次提出了认知无线电（cognitive radio）的概念。他认为认知无线电是一种智能的软件无线电，同时具备软件无线电的参数重构功能，还能够感知周围的环境以提供符合用户需求的无线资源和服务。在认知无线电网络中，未授权用户，即次用户（secondaryuser能够在不干扰授权用户（primaryuser）正常通信的前提下感知并智能接入空闲的授权频段，实现对频谱资源的高效利用。因此，与传统网络相比，它可以获得更多可用频谱段来提高网络性能和网络容量。

认知无线电技术能够将可用的频谱资源分配给用户，以实现频谱资源的高效利用，因此频谱分配技术是认知无线电的重要组成部分。频谱分配技术能够根据需要接入本网络的用户数目及用户的服务需求，将当前可用频段分配给这些用户，并且在不对授权用户造成过度干扰的前提下，使认知用户之间通过合理公平的方式共同使用频谱资源。由于频谱分配会对网络性能指标产生直接影响，认知无线电通常会根据用户的性能需求获取合适的频谱分配方案。然而网络中的性能指标是相互制约的，单纯优化某一个性能指标[2\~4]，有可能会降低其它方面的性能。而用户也不只追求一种性能的最优化，而往往希望考虑多个性能的均衡。因此，近年来一些研究人员开始将多目标优化方法应用于认知无线电的频谱分配，以便获得网络性能的平衡。文献[5]将底层频谱共享网络制中的频谱分配问题构建成多目标优化问题，以最大化吞吐量和频谱效率。并使用NSGA-II算法来搜索Pareto最优解。文献[6]将认知无线电网络的最大系统效益和次用户间的最大比例公平作为目标函数,基于多目标遗传算法并运用图论着色频谱分配模型,实现认知无线电中空闲频谱在次用户间的动态分配。

次用户接入授权频段首先是不影响主用户的正常通信，再者就是尽量减少对于同频段次用户的影响，这样才能获得良好的网络性能。实现这两个目标需要对次用户进行功率控制，优化的功率分配策略可以保证次用户的传输，同时控制对于其它用户的干扰，所以功率控制对于实现认知无线电网络性能的优化至关重要，近年来研究人员也对功率控制的多目标优化问题做了大量研究。文献[7]基于猫群优化的概念来优化基于OFDM的认知无线电引擎参数自适应问题。同时考虑了主用户和次用户之间的频谱干扰，最后提出了一种基于模糊逻辑的策略，以便在Pareto前沿中找到一个折中的解决方案。文献[8]介绍了一种新的称为干扰效率的性能指标，用来表示在主用户接收机上被施加的每单位干扰能量传输的位数。IE优化问题通过优化多个目标来解决，即最大化多个认知用户的各态历经总速率并最大限度地减少对主用户的干扰。为了提高认知无线电网络的能量效率，文献[9]提出联合最大化各态历经容量并最大限度地减少平均传输功率。文献[10]研究了基于OFDM的认知无线电系统的最佳链路自适应问题，并且将其构建成两个相互冲突的目标：最大化系统吞吐量和最小化其发射功率。所提出的方法在满足主用户的预定干扰阈值和频谱感知误差的约束条件下优化了每个认知用户子载波的位和功率分配。在文献[11]中，作者将交叉熵优化应用于绿色合作认知无线电（GCCR)网络中的联合多中继分配和源/中继功率分配问题。基于蒙特卡罗的交叉熵优化算法被用于优化两个相互冲突的目标：最大化GCCR网络中的总体速率和最小化温室气体排放。

以上文献在优化多个网络性能时只考虑了频谱或者功率，而忽略了两者会同时对网络性能产生影响。因此本文从认知无线电网络中次用户的频谱和功率着手，同时调节次用户的发射功率和工作频段来保证网络中所有用户的正常通信。为此，本文提出了一种基于遗传算法的多目标优化算法来求解认知无线电的频谱分配和功率控制问题，使网络在最大功耗效率和最大网络吞吐量之间获得折衷。理论分析和仿真结果表明，该方法能够很好地解决所提问题，并能获得优秀的分配方案。

# 1 系统模型

本文考虑一个包含若干通信链路的认知无线网络模型，如图1所示，网络中主用户作为接收端的通信链路称为主链路，次用户作为接收端的通信链路称为次链路，它们共同存在于一个区域内。

![](images/808c377cbb11cb063495a7b25a6c29c7cdd56ca84a29124189d9d0989969004a.jpg)  
图1认知无线网络分布模型

网络中所有主用户由相应的发射机提供服务，且其位置是固定的。而在次链路中，一台发射机只服务于一个次用户，且随机分布于该区域中。本文采用Underlay的频谱接入方式，允许主用户和次用户同时使用某一频段，即在不影响网络中所有用户正常通信的前提下，同一频段可以被分配给一个或多个次链路使用。

# 1.1认知无线电网络模型

考虑到主用户网络和认知无线电网络混合存在，于是本网络模型将整个网络分为包含主用户的通信网络和包含次用户的通信网络两个部分，记为主网络和次网络，分别用 $V$ 和 $U$ 来表示。并且定义了集合 $\pmb { M }$ 、 $_ { P L }$ 和 $_ { S L }$ ，其中 $\pmb { M }$ 是当前网络可分配信道的集合， $_ { P L }$ 和 $_ { S L }$ 则分别表示主网络中所有主链路的集合和次网络中所有次链路的集合。

在当前网络模型中，主、次链路的传输性能会受当前频段所有用户发射功率的影响。具体来说，主链路在传输时会受到同频段次链路的干扰，相反，次链路也会受到同频段的主链路的影响，同时还受同频段的其它次链路的干扰。因此为了保证网络的整体性能，需要评估网络中所有链路的传输质量。在无线网络传输中，通常使用信号干扰噪声比SINR（Signal toInterferenceplusNoiseRatio）来衡量接收信号的质量。SINR可以被定义为接收机处的预期信号接收功率除以同一信道上其他链路的非预期信号（干扰）的接收功率之和。以图1为例具体说明：主链路1工作于 $m _ { 1 }$ 信道，与其在同一信道传输数据的有次链路1和2。因此，主链路接收机 $V _ { I } ^ { R }$ 在接收发射机 $V _ { I } ^ { s }$ 信号的同时，也会接收到次链路发射机 $\boldsymbol { U } _ { I } ^ { s }$ 和 $U _ { ? } ^ { S }$ 的信号。同理，次链路接收机 $U _ { I } ^ { R }$ 和 $U _ { 2 } ^ { R }$ 在接收各自发射机的信号时，不仅会受到对方发射机的干扰，同时也受主链路发射机 $V _ { _ { I } } ^ { s }$ 的干扰。

根据以上定义，首先求解主链路 $p l$ 工作在信道 $m$ 时，其用

户的预期接收功率为

$$
\mathscr { B } _ { p l } \left( m \right) = G \left( V _ { p l } ^ { s } , V _ { p l } ^ { R } \right) P \left( V _ { p l } ^ { s } \right)
$$

其中： $V _ { p l } ^ { S }$ 和 $\boldsymbol { V } _ { p l } ^ { R }$ 分别代表主链路 $p l$ 的发射机和接收用户，而$P \big ( V _ { p l } ^ { S } \big )$ 表示该发射机的发射功率。 $G \big ( V _ { p l } ^ { S } , V _ { p l } ^ { R } \big )$ 则表示从发射机$V _ { p l } ^ { S }$ 到其接收用户 $V _ { p l } ^ { R }$ 的路径损耗：

$$
G \big ( V _ { p l } ^ { S } , V _ { p l } ^ { R } \big ) { = } k \Big / d \big ( V _ { p l } ^ { S } , V _ { p l } ^ { R } \big ) ^ { \alpha }
$$

其中： $k$ 和 $\alpha$ 分别为路径损耗常数和指数， $d \big ( V _ { p l } ^ { S } , V _ { p l } ^ { R } \big )$ 则表示从 $V _ { p l } ^ { S }$ 到 $V _ { p l } ^ { R }$ 的距离。

本文假设在当前区域的所有主链路均工作在不同的通信信道。因此，在计算非预期信号的接收功率时，除接收设备的热噪声外，仅需考虑所有工作在信道 $m$ 的次链路发射机对该主用户的干扰之和：

$$
N _ { p l } ( m ) \ = \sum _ { s l \in S L , s l \in I ( m ) } G \bigl ( U _ { s l } ^ { s } , V _ { p l } ^ { R } \bigr ) P \bigl ( U _ { s l } ^ { s } \bigr )
$$

其中 $I ( m )$ 表示次链路 $s l$ 工作在信道 $m$ 上。

根据式错误！未找到引用源。 $\sim$ 错误！未找到引用源。，工作在信道 $m$ 上的主用户的SINR可以表示为

$$
S I N R _ { _ { p l } } \left( m \right) = \frac { \mathbb { E } _ { p l } \left( m \right) } { \mathcal { N } \underline { { \rho } } + N _ { p l } \left( m \right) }
$$

常数 $\mathcal { N } _ { - }$ 指代设备的热噪声。简言之，该式中 $\textstyle | { \overline { { E } } } _ { p l } ( m )$ 决定了主用户 $V _ { p l } ^ { R }$ 能够接收到的信号强度。而 $\mathcal { N } _ { - } / + \mathbb { N } _ { p l } ( m )$ 则定义了该用户受到的全部干扰，其中 $N _ { p l } ( m )$ 代表所有与该用户使用相同信道的次链路对它的干扰总和。

当网络进行频谱分配和功率控制时，不仅需要保障主用户的正常通信，还应该保证工作在同信道的次用户间的干扰尽可能低。因此需要将所有次用户的SINR考虑在内。在计算次用户的SINR时，所有工作在同信道的主链路和次链路的信号对当前用户而言都是干扰，需要分别考虑。首先考虑同时工作于信道 $m$ 上的主链路 $p l$ 对次链路 $s l$ 产生的干扰：

$$
\begin{array} { r } { N _ { s l } ^ { V } \big ( m \big ) = G \big ( V _ { p l } ^ { s } , U _ { s l } ^ { R } \big ) P \big ( V _ { p l } ^ { s } \big ) } \end{array}
$$

同理，其他所有工作于信道 $m$ 上的次链路对当前次链路产生的干扰可以定义为

$$
\ N _ { s l } ^ { U } ( m ) \ = \ \sum _ { ( i , s l ) \in { \bf { S } } L , i \neq s l } G \big ( U _ { i } ^ { s } , U _ { s l } ^ { R } \big ) P \big ( U _ { i } ^ { s } \big )
$$

由于该次用户的预期信号接收功率可以定义为

$$
\mathscr { L } _ { s l } \left( m \right) = G \left( U _ { s l } ^ { s } , U _ { s l } ^ { R } \right) P \left( U _ { s l } ^ { s } \right)
$$

所以该用户的SINR可以通过下式得到：

$$
S I N R _ { s l } \left( m \right) = \frac { \mathcal { \mathbb { E } } _ { s l } \left( m \right) } { \mathcal { N } _ { - } ^ { \omega } + \mathcal { N } _ { s l } ^ { V } \left( m \right) + \mathcal { N } _ { s l } ^ { U } \left( m \right) }
$$

综上所述，在网络中主、次用户同时存在的情况下，频谱

分配和功率控制对网络的性能会产生很大影响。因此为了保证网络的整体性能，需要根据网络需求设定网络需要达到的目标。

# 1.2 优化目标

本文采用Underlay的频谱接入方式，次用户可以接入到主用户正在使用的授权频段。在此情况下，次用户对主用户的干扰必须在主用户可容忍范围之内。因此次链路的发射功率是造成网络干扰的主要原因。虽然减小次链路的发射功率能够减少对主用户的干扰，但是盲目地减小却不能保证网络的通信性能。所以，合理的功率控制既能保证不对主用户造成严重的干扰，又能保障次用户的通信性能。由此，在Underlay情况下进行频谱分配时，可以进一步考虑功率控制，通过联合分配两种资源达到网络性能的优化。在分配频谱和控制功率时，会对网络的多个性能产生影响，为了获得多个网络性能间的均衡优化，本文将以上问题定义成一个多目标优化问题，以最大化网络的功耗效率和系统容量。

# 1.2.1功耗效率

在无线通信网络中，功率控制是一个最为重要的问题。功率控制不仅可以降低网络用户间的干扰，还能节省网络设备的功耗，为设备的持续工作提供了保障。本文假设次链路发射机在其最大功率的基础上能够向下调节自身发射功率。因此提出功耗效率这一性能指标，并将其定义为：在最大功率基础上节省出来的功耗与最大功率之比，如式错误！未找到引用源。所示。

$$
f _ { 1 } = 1 - { \sum _ { s l = 1 } ^ { | s L | } } \frac { P \big ( U _ { s l } ^ { S } \big ) } { \tilde { P } \big ( U _ { s l } ^ { S } \big ) }
$$

其中： $P \big ( U _ { s l } ^ { S } \big )$ 表示次链路 $s l$ 中发射机的当前发射功率， $\tilde { P } \big ( U _ { s l } ^ { S } \big )$ 表示该发射机的最大发射功率。

# 1.2.2网络容量

本文将网络容量定义为整个网络的总的数据率(DataRate)，即所有主链路与次链路获得的数据率之和。其大小主要取决于主次链路共享信道的带宽以及当前的通信环境（如衰减和干扰等)。根据香农模型[2]给出主、次链路的容量公式：

$$
\begin{array} { l } { { C _ { p l } = W \log _ { 2 } \left( 1 + S I N { R _ { p l } } \left( m \right) \right) } } \\ { { C _ { s l } = W \log _ { 2 } \left( 1 + S I N { R _ { s l } } \left( m \right) \right) } } \end{array}
$$

其中： $C _ { p l }$ 和 $C _ { s l }$ 分别表示主链路 $p l$ 和次链路 $s l$ 的数据率大小。$W$ 表示共享信道的带宽，并且本文假设所有参与分配的频段的带宽相同。由式错误！未找到引用源。推导出网络的总容量为

$$
f _ { 2 } = \sum _ { p l = 1 } ^ { \left| P L \right| } C _ { p l } + \sum _ { s l = 1 } ^ { \left| S L \right| } C _ { s l }
$$

# 1.3 优化问题描述

根据上文所述，次链路传输功率的增加会降低网络的功耗效率，但是却不一定会提高网络的容量，因为随着功率的增加，网络的干扰也更严重。所以功耗效率和网络容量是两个相互冲突的目标，适合用多目标优化方法优化。根据公式错误！未找到引用源。和公式错误！未找到引用源。将该问题定义为如公式错误！未找到引用源。所示的多目标优化问题。

$$
M a x \ 1 - { \sum _ { s l = 1 } ^ { | s L | } } \frac { P \big ( U _ { s l } ^ { s } \big ) } { \tilde { P } \big ( U _ { s l } ^ { s } \big ) }
$$

$$
M a x \sum _ { p l = 1 } ^ { \left| P L \right| } C _ { p l } + \sum _ { s l = 1 } ^ { \left| S L \right| } C _ { s l }
$$

$$
\begin{array} { l l } { s . t . } & { S I N R _ { p l } \left( m \right) \geq \beta _ { p l } \quad p l \in { \pmb { P L } } } \\ { s . t . } & { S I N R _ { s l } \left( m \right) \geq \beta _ { s l } \quad s l \in { \pmb { S L } } } \end{array}
$$

由环境噪声或其他无线电传输引起的干扰会降低接收机处的 SINR，是影响网络通信稳定性的重要原因之一，因此，为了保证网络通信的服务质量（QoS)，SINR一般要求大于某一阈值。为此，在式错误！未找到引用源。中加入了通信链路关于SINR的约束条件， $\beta _ { { } _ { p l } }$ 和 $\beta _ { s l }$ 分别表示主链路 $p l$ 和次链路 $s l$ 的SINR 阈值。

# 2 多目标频谱分配与功率控制算法

式错误！未找到引用源。所定义的多目标优化问题较为复杂，在搜索频谱和功率分配方案时需要耗费大量的计算成本，而频谱和功率分配需要根据当前环境和性能需求，快速高效地给出分配方案，因此需要设计有效的启发式算法获得优化解。为了快速获得最优解，本文选择基于精英主义的非支配排序遗传算法[13](NSGA-II)来求解式错误！未找到引用源。错误！未找到引用源。定义的多目标优化问题。NSGA-II算法是非支配排序遗传算法[14]（NSGA）的改进版，它们都是基于Pareto最优（Paretooptimality）概念的多目标优化算法。与基于非Pareto 最优概念的算法（如基于向量评估的遗传算法[15]（VEGA)）相比，该算法克服了容易陷入局部最优的缺点，能有效地搜索整个特征空间。该算法提出了一种快速非支配排序方法，能有效地对种群中的所有解决方案进行排序，并将其分级为多个非支配前沿。与NSGA相比，其计算复杂度由 $O ( m N ^ { 3 } )$ 降低到了 $O ( m N ^ { 2 } )$ ，其中 $m$ 是目标函数的数量， $N$ 是种群大小。同时，该算法引入了精英保护策略，将父代和子代组合以共同竞争产生下一代群体，保证了某些优良的种群个体在进化过程中不会被丢弃，因此，随着算法不停地迭代，优秀的个体将迅速增加，从而提高了优化结果的精度。

本文基于NSGA-II 的思想将其改进以适用于处理公式错误！未找到引用源。定义的多目标优化问题。为了求解该问题，首先需要对频谱和功率的分配方案进行编码，编码构成如图 2所示。在编码频谱分配方案时，定义了向量 $\boldsymbol { C } _ { i }$ ，表示为$\pmb { C } _ { i } = ( c _ { 1 } , c _ { 2 } , \cdots , c _ { | S L | } )$ ，其中 $c _ { i } \in M$ ，代表次链路 $i$ 分配获得的信道编号， $i$ 的取值范围为 $\big [ 1 , \big | S L \big | \big ]$ 的整数。另外，考虑次链路信道分配的同时还需要进行功率分配。同理，定义向量$\pmb { P _ { i } } \mathrm { = } ( p _ { 1 } , p _ { 2 } , \cdots , p _ { | s L | } )$ ,其中 ${ { p } _ { i } }$ 表示次链路 $i$ 中发射机 $\boldsymbol { U } _ { i } ^ { s }$ 的发射功率， $i$ 的取值范围同样为 $[ 1 , | S L | ]$ 的整数。

![](images/66daa615d616c254e240457fb5fe2f657030c9b32bb7db6715c4d1cede118b8f.jpg)  
图2编码结构

图2中 $f _ { 1 }$ 和 $f _ { 2 }$ 是根据 $\pmb { C } _ { i }$ 、 $\pmb { P } _ { i }$ 以及式错误！未找到引用源。错误！未找到引用源。求解得出的目标值。在求解最优解时，所提算法首先需要对整个种群进行非支配排序。非支配排序算法将种群中每个个体的两个目标值分别与其它个体进行比较，以此确定个体间的支配关系。在本文的网络场景中，对于种群中任意的两个个体 $p$ 和 $q$ ，其目标值满足式错误！未找到引用源。中的任意一种情形时， $p$ 支配 $q$ 成立。

$$
\begin{array} { r l } { f _ { 1 } ( p ) > f _ { 1 } ( q ) } & { a n d \quad f _ { 2 } ( p ) > f _ { 2 } ( q ) } \\ { f _ { 1 } ( p ) > f _ { 1 } ( q ) } & { a n d \quad f _ { 2 } ( p ) = f _ { 2 } ( q ) } \\ { f _ { 1 } ( p ) = f _ { 1 } ( q ) } & { a n d \quad f _ { 2 } ( p ) > f _ { 2 } ( q ) } \end{array}
$$

其中： $f _ { 1 } ( \boldsymbol { p } )$ 和 $f _ { 1 } ( q )$ 分别是个体 $p$ 和 $q$ 对应的目标 $f _ { 1 }$ 的值，$f _ { 2 } ( \boldsymbol { p } )$ 和 $f _ { 2 } ( q )$ 同理。

然后利用个体间的支配关系将个体分级，在图2中用 $\boldsymbol { r }$ 表示该个体的等级。最后得出的等级最高的个体组成的解集即为Pareto 最优解，也称Pareto 前沿。获得Pareto 前沿的具体步骤如下所示：

a)对于每一个个体 $p$ ，将其目标值与其它个体依次进行比较，得出种群中支配 $p$ 的个体数目，记为 $n _ { p }$ 。同时将被 $p$ 支配的个体计入 $S _ { p }$ 中；

b)将种群中所有 $n _ { { } _ { p } } = 0$ 的个体的等级记为1，同时对 $S _ { p }$ 中的个体 $q$ 执行 $n _ { { \scriptscriptstyle q } } = n _ { { \scriptscriptstyle q } } - 1$ ：

c)重复步骤b)产生下一等级。

图2中 $d$ 表示拥挤度（crowdingdistance），用来表示种群中该个体周围其它个体分布的密度。在算法中，拥挤度的计算是保证同一非支配等级中种群多样性的重要环节。根据文献[13]给出的拥挤度的概念，个体 $p$ 的拥挤度可以由以下公式计算得出：

$$
d _ { p } = \sum _ { k = 1 } ^ { 2 } { \frac { f _ { k } ( p + 1 ) - f _ { k } ( p - 1 ) } { f _ { k } ^ { \operatorname* { m a x } } - f _ { k } ^ { \operatorname* { m i n } } } }
$$

其中: $f _ { k } ( p + 1 )$ 和 $f _ { k } ( p - 1 )$ 分别表示与个体 $p$ 处于同一非支配等级的前后个体的第 $k$ 个目标值。 $f _ { k } ^ { \operatorname* { m a x } }$ 和 $f _ { k } ^ { \mathrm { m i n } }$ 分别表示当前非支配前沿中 $f _ { k }$ 的最大值及最小值。

综上所述，基于图2所示的个体编码结构，将算法应用于频谱分配与功率控制问题中以获得Pareto最优解，其详细过程如下所示：

a)随机初始化大小为 $N$ 的种群 $F _ { t }$ ：

b)通过非支配排序算法对 $F _ { t }$ 进行分级操作，同时计算其拥挤度；

c)通过二进制锦标赛算法从 $F _ { t }$ 中选择优秀个体进行交叉和变异操作，产生新种群 $Q _ { t }$ ：

d)合并种群 $F _ { t }$ 和 $Q _ { t }$ ，产生组合种群 $R _ { t }$ ：

e)通过非支配排序算法对 $R _ { t }$ 进行分级操作，同时计算其拥挤度，根据非支配等级和拥挤度选择前 $N$ 个最优个体，组成种

群 $F _ { t + 1 }$

f)若不满足结束条件，则跳转到(2)继续执行。

最后一次迭代后，从中选取支配等级最高的个体组成Pareto 前沿。因此，Pareto前沿是最优解的集合，而集合中的每一个解都对应着一种频谱分配和功率控制的方案。

# 3 仿真及结果分析

为评估前文提出的多目标优化算法在求解式错误！未找到引用源。定义问题时的性能，本章针对不同网络需求进行了仿真验证。仿真网络如图3所示：20条次链路随机分布在 $3 0 0 0 \mathrm { m } { \times } 3 0 0 0 \mathrm { m }$ 的区域中，次链路发射机到接收机的距离被限定在120米以内。同时，区域中固定了4条主链路，主链路间使用的信道互不干扰，且所有可分配信道的带宽都为5MHz。由于上文假设信道强度只由路径衰落决定，根据公式错误！未找到引用源。给出的路径衰落定义，定义路径损耗常数$k { = } 1$ 、路径衰落指数 $\scriptstyle \alpha = 3$ 。为了简化计算，假设次链路发射机的最大发射功率为 $5 \mathrm { m W }$ ，在次链路发射机调整发射功率时可将其调至 $1 { \sim } 5 \mathrm { m W }$ 中任意整数功率，同时假设所有链路的SINR值相同，即 $\beta _ { { } _ { p l } } = \beta _ { { } _ { s l } }$ 。

![](images/ee4906db2ee7dd8a16d3342a4acf27f4a9fd5d24a6c0b758f716bfa1c5b08027.jpg)  
图3仿真网络分布图

为了便于理解，表1列出了算法中使用的部分参数及其取值。实验设计了一个包含100条个体的种群，并对该种群进行200次遗传迭代操作。

表1实验参数表  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>种群大小</td><td>100</td></tr><tr><td>迭代次数</td><td>200</td></tr><tr><td>交叉率</td><td>0.9</td></tr><tr><td>变异率</td><td>0.1</td></tr><tr><td>主链路数量</td><td>4</td></tr><tr><td>次链路数量</td><td>20</td></tr><tr><td>主链路功率</td><td>10mW</td></tr><tr><td>次链路功率</td><td>1~5mW</td></tr></table></body></html>

图4是所提算法在SINR为4dB时运行10次的结果。从图中最优解的分布可知：功耗效率和网络吞吐量是两个互相冲突的性能指标，网络吞吐量的提高通常伴随着功耗效率的降低。

但是通过对实验结果进一步分析，发现在功耗效率大幅提高的同时，网络吞吐量的降低比例相对较小，大约在 $20 \%$ 左右。这是因为在认知无线电网络中，同一信道被分配给多个链路使用，当这些链路同时进行网络传输时会造成较为严重的同信道干扰，导致网络容量骤降。所以，一味地提高发射功率并不会大幅提高网络的吞吐量。但是在需要节能的网络场景中，可以选择在一定程度上提高网络吞吐量的同时大幅提高功耗效率，以达到节省功耗的目的。

![](images/703dc3d940dbb712a09b4505df1d0233f0210db79d52008a0d495fe1e3cfb7f7.jpg)  
图4SINR阈值为4dB 时运行10次的结果

![](images/a49016522a0cdb8f66501f25abe0cb3ec36a73da2362e646718693a1dba375f6.jpg)  
图5SPEA-II算法在SINR 阈值为4dB时运行10 次的结果

为了进一步评估本文所提算法的性能，本文采用改进的强度Pareto 进化算法[16]（SPEA-II）来处理多目标频谱分配问题并与之进行比较。SPEA-II被认为是一种有效的精英多目标进化算法，并被验证了在无线网络中解决MOP问题的高效性能[17,18]。图5是 SPEA-II在 SINR 阈值为4dB 时运行 10次的结果。对比图5可以看出，SPEA-II虽然在低功耗效率( $1 0 \% { \sim } 2 0 \%$ ）区间搜索到了部分解，但是在搜索 $20 \% { \sim } 4 0 \%$ 和 $70 \% { \sim } 8 0 \%$ 之间的有效解时性能较弱。对比图4，本文所提算法每次运行获得的Pareto 前沿分布非常均匀，这得益于其在选择个体时，倾向于选择少数拥挤距离较大的非支配个体作为子代，以此加强对当前Pareto前沿中较稀疏区域的搜索，使解集的解能够均匀扩散到整个Pareto 前沿中。

由于SINR 能够衡量用户接收信号的质量，从而当网络需要满足不同的通信质量要求时，可以通过改变SINR阈值获得满足要求的解集。根据不同SINR（4dB，8dB，12dB和16dB）阈值作如图4所示相同的实验，得出结果后取每种功耗效率下吞吐量的中值作为结果绘制在图5中。

根据上图中不同SINR阈值得出的最优解集合可知，随着SINR的提高，网络吞吐量也有一定提升，但是提升的幅度对于整个网络而言相对较小。这是因为网络吞吐量的大小取决于网络中各个用户的数据率。根据香农公式错误！未找到引用源。可知，随着SINR的不断提高，数据率的增长趋势明显放缓。因此对于小规模网络而言，提高用户的SINR阈值并不会大幅提高整个网络的吞吐量。但是对于用户而言，SINR的提高却能使其通信质量明显提升，以满足复杂的传输需求。同时注意到，随着SINR的提高，Pareto前沿中高功耗效率部分的解的数量在逐步减少，这在SINR增加到16dB时尤为明显，但是在低功耗效率部分却相反，解的数量在逐步增加。一方面，当功耗效率较高时，网络中发射机的功率整体较低。虽然对网络产生的同信道干扰较小，但是其较低的发射功率使得部分用户难以达到相应的SINR要求。另一方面，较低的功耗效率表示网络的整体发射功率较高，这时网络中的同信道干扰较为严重，满足要求的解相对减少。但是同时也缩小了算法的搜索空间，使得算法能快速收敛到最优解。

![](images/ab8e7b7258846d3cb68b912c7a04e4eb8d3294f62adab2210d17dd0cc35c3e04.jpg)  
图5不同SINR下最优解集合对比

# 4 结束语

本文主要研究了认知无线网络中频谱分配和功率控制问题，并将此问题构建成多目标优化模型，然后使用改进的多目标优化算法对网络进行了优化，以最大限度地提高网络的功耗效率和吞吐量。仿真结果表明，本文所提出的方法在搜索最优解时表现良好，同时相对于传统的单目标优化方法，能够很好地权衡网络中多个目标间的性能，使系统获得最大的效率。

# 参考文献：

[1]FCC.Notice of proposed rule making and order,ET docket no O3-222 [R]. 2003.   
[2] 谢军辉，冯平.认知无线网络中基于凸优化的功率分配研究[J].计算 机应用研究，2010,27(3):1161-1162.(Xie Junhui,Feng Ping.Power allocation for cognitive radio network based on convex optimization [J] Application Research of Computers,2010,27(3): 1161-1162.)   
[3]杜奕航，王可人，齐全．基于能量效率的认知无线网络联合优化算法 [J].计算机应用研究,2017,34(3):849-852.(Du Yihang,Wang Keren, Qi

Quan.Combined optimization algorithm based on energy efficiency for cognitive radio networks [J].Application Research of Computers,2017,34

(3): 849-852. )   
[4] 杨劲松，曾碧卿，胡翩翩.认知无线电网络中基于和声搜索的频谱分配 与功率控制[J].计算机科学,2015,42(S2):258-262.(Yang Jinsong, Zeng Biqing, Hu Pianpian. Spectrum alocation and power control based on harmony search algorithm in cognitive radio network[J]. Computer Science, 2015, 42 (S2): 258-262. )   
[5]Martinez-Vargas A, Dominguez-Guerrero J,Andrade AG,et al. Application of NSGA-II algorithm to the spectrum assignment problem in spectrum sharing networks [J]. Applied Soft Computing,2016,39 (C): 188-198.   
[6]姚再英，黄玉清．基于多目标遗传算法的认知无线电频谱分配[J].西 南科技大学学报,2010,25(4):82-86.(姚再英，黄玉清.Cognitive radio spectrum allocation based on multi-objective genetic algorithm [J]. Journal of Southwest University of Science and Technology,2010,25 (4): 82-86.)   
[7]Pradhan P M,Panda G.Pareto optimization of cognitive radio parameters using multiobjective evolutionary algorithms and fuzzy decision making [J]. Swarm and Evolutionary Computation,2012,7: 7-20.   
[8]Mili MR, Musavian L. Interference Efficiency: A new metric to analyze the performance of cognitive radio networks [J].IEEE Transon Wireless Communications,2017,16 (4): 2123-2138.   
[9]MiliMR,MusavianL,Hamdi KA,et al. How to Increase Energy Efficiency in Cognitive Radio Networks [J]. IEEE Trans on Communications,2016,64 (5): 1829-1843.   
[10] Bedeer E,Dobre OA,Ahmed MH,et al.A multiobjective optimization approach for optimal link adaptation of OFDM-based cognitive radio systems with imperfect spectrum sensing [J].IEEE Trans on Wireless Communications,2014,13 (4): 2339-2351.   
[11] Naeem M, Khwaja A S,Anpalagan A,et al. Green cooperativecognitive radio: a multiobjective optimization paradigm [J]. IEEE Systems Journal, 2016,10 (1): 240-250.   
[12] Shannon CE. Communication in the presence of noise [J]. Proceedings of the IEEE,1998,86 (2): 447-457.   
[13] Deb K,Pratap A,Agarwal S,et al.A fast and elitist multiobjective genetic algorithm: NSGA-II [J]. IEEE Trans on Evolutionary Computation,2002,6 (2): 182-197.   
[14] SrinivasN,Deb K.Multiobjective function optimizationusing nondominated sorting genetic algorithms [J]. IEEE Trans on Evolutionary Computation,1994,2 (3): 1301-1308.   
[15] Schaffer JD.Multiple objective optimization with vector evaluated genetic algorithms [C]// Proc of International Conference on Genetic Algorithms. 1985: 93-100.   
[16] Zitzler E,Laumanns M, Thiele L.SPEA2: improving the strength pareto evolutionary algorithm [J].Technical Report Gloriastrasse,2o01,103.   
[17] Jiang Hao,Chen Jing,Liu Tundong.Multi-objective design of an FBG sensor network using an improved Strength Pareto Evolutionary Algorithm

[J].Sensors and Actuators a-Physical,2014,220 (Supplement C):230-236. [18] Hajjej F,Ejbali R,Zaied M.Quality of Services based routing using evolutionary algorithms for Wireless Sensor Network [C]// Proc of

International Conference on Intelligent Systems Design and Applications.   
2015:237-242.