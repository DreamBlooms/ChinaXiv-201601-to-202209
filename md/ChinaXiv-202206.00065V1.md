# 基于整数线性规划的VLIWDSP指令分簇调度

周鹏1,²，刘纯纲1,²，郑启龙1,2

(1．中国科学技术大学，计算机科学与技术学院，合肥 230026;2.高性能计算安徽省重点实验室，合肥 230026)

摘要：在分簇VLIWDSP上，指令分簇是一项对程序性能有重要影响的编译优化，但现有的指令分簇算法只能处理顺序的程序区域，且难以获得最佳的分簇方案。针对这些问题，提出一种基于整数线性规划的统一指令分簇与指令调度的方法。该方法使用零一决策变量表示函数中指令的分簇、指令的局部调度、以及簇间传输指令的全局调度，并将指令之间的依赖关系和对处理器资源的竞争关系构造为线性约束，最终得到一个以最小化函数的估计执行时间为目标的整数线性规划模型。实验结果表明，求解该模型得到的分簇调度方案对程序性能的优化显著强于现有算法，并且求解模型所耗费的时间是可接受的。

关键词：DSP；VLIW；指令分簇；指令调度；整数线性规划 中图分类号：TP314 doi:10.19734/j.issn.1001-3695.2022.03.0120

Integer linear programming based instruction cluster assignment and schedule of VLIW DSP

Zhou Peng1, ², Liu Chungang1,², Zheng Qilong1, 2 (1.UniversityofScience&TechnologyofChina,CollegeofComputerSience&TechnologyHefei230026,China;2.Key Laboratory of High Performance Computing,Anhui Province,Hefei 230026,China)

Abstract: Cluster asignment is a compiler optimization that plays an important role in performanceof programs.However, the existingalgorithms onlyworkonstraight-line programarea,andis dificult tobeoptimal.Aimingat these problems,this paper proposed aunified cluster assgnment and instruction scheduling method based on integer inear programming.This method used zero-one decision variables torepresent cluster asignment,local instruction schedulingand global scheduling of inter-cluster transfer instructions,and formulated dependencyand processorresources competitionbetween instructions into linearconstraints,eventuallgot an integerlinear programming model whose objective is tominimizethe estimated execution timeof the function.Experimentalresults showthatthe cluster assignmentand scheduling scheme from solving the modelsignificantlyoutperforms theexistingalgorithmsonaccelerating programs,andthe timerequired tosolve the model is acceptable.

Key words: DSP; VLIW; cluster assignment; instruction scheduling; integer linear programming

# 0 引言

许多数字信号处理器(digital signal processor,DSP)采用超长指令字(verylong instructionword,VLIW)架构来提高指令级并行(instruction level parallelism,ILP)。VLIW 架构 DSP一般发射宽度较大，需要大量的运算设备和寄存器文件。让所有运算设备与所有寄存器直接连通会使处理器的设计复杂度较高，且功耗较大[1]。解决这个问题的一个方法是将运算设备和寄存器分为多个簇，每簇中运算设备与寄存器数目相同，簇内的运算设备能直接访问内部寄存器文件，不同簇之间通过总线连通，跨簇访问数据需要将其他簇的数据复制到本地簇内。这样的分簇架构中，簇内的数据访问延迟低，功耗低，而不同簇之间的数据访问延迟高，功耗高。

在分簇架构的处理器上，需要确定指令使用哪一个簇的运算资源，这一操作称为分簇(cluster assignment)。在一些早期的处理器上，分簇由硬件自动完成，例如文献[2]，在现代的分簇VLIWDSP上，分簇由编译器完成，例如由中国电子科技第38研究所研发的HXDSP。分簇的目的是让程序充分利用不同簇上的运算资源，同时避免过多的簇间通信，从而提高程序的指令级并行度，这使得分簇与指令调度这项编译优化紧密相关。在早期的工作中，分簇是一项独立的优化[3-6]，分簇完成后再进行指令调度，更近的一些工作则同时进行指令的分簇与调度[7\~10]。

当前的各种分簇方法在基本块或者trace[1这样的无分支的程序区域上进行分簇，不同的方法之间的主要区别在于采用了不同的启发因子确定指令被分派的簇。这些方法欠缺对全局数据流的处理，忽视了不同基本块中的指令之间的簇间通信开销，尽管在trace中分簇考虑了多个基本块，但在很多程序中，不同分支的跳转情况难以估计，不容易构造trace。另一问题是基于启发式决策的方法并不能保证得到最优的分簇方案，启发式方法的优点在于算法执行速度快，但在DSP的应用领域中，耗费更多的编译时间，实现更好的分簇方案，获得更高的执行性能往往是可以接受的。

组合优化是一类寻找问题最优解的方法，其中整数线性规划是一种形式简单，但被广泛使用的方法，在编译优化领域中也有不少应用，例如指令调度[12,13]、超字并行[14]。考虑到当前的分簇算法的不能保证最优的现状，使用整数线性规划进行分簇，进一步提高指令分簇的质量是比较好的选择

本文的主要贡献为：提出了一种VLIWDSP上的指令分簇与调度的整数线性规划建模方法，将整个函数中每条指令的分簇，每个基本块的指令调度，以及分簇导致的簇间传输指令的插入位置和调度，表示为一个整数线性规划模型。相比于现有的分簇方法，本文的方法以函数为单位进行分簇，解决了全局数据流之间的簇间传输指令的插入问题，并且求解得到的分簇调度方案是(在估计的代价模型下)最优的，此方法可以直接实现在其他程序区域上，例如只考虑循环内部的代码，基本块，或者trace等，当实现在无分支的程序区域上时，执行时间可以准确地评估，得到的分簇调度方案便是真正上最优的。

最早的指令分簇方法由Ellis 等人在Bulldog 编译器[3]中实现，称为 BUG(bottom up greedy)算法，此方法基于一项称为完成时刻(completioncycle)的启发因子进行分簇，指令关于某个簇的完成时刻定义为：将指令分派到该簇执行完成后，并将数据传输到流依赖后继所在的候选簇的最晚时刻。BUG算法从每个无后继的指令节点开始，逆向深度优先遍历数据流图，每次选择使指令完成时刻最小的簇作为当前指令的候选簇，依次对所有依赖前驱分簇，所有前驱分簇完毕后再将当前指令分派到某一个完成时刻最小的簇。

BUG 算法贪心地分簇并不能保证将所有位于关键路径上的指令分派到同一个簇，而且基于最小化完成时间的分簇可能导致首次深度优先遍历数据流图时将一部分有数据流依赖的指令分散到不同簇。Lowney等人[4]在实现BUG算法时进行了一些改进，他们的方法将数据流图分为多个部件，每个部件内部并行度较低，数据共享度高，在BUG 算法中计算完成时刻时，若两个相关部件(一个的数据被另一个使用)存在于不同的簇中，则在完成时刻上施加一个较大的惩罚值从而实现若干相关的部件分派到同一个簇，避免簇间通信代价过大。

Desoli等人[5]采用了一个多阶段的迭代算法实现分簇，首先采用类似BUG的算法得到初步的分簇，但分簇的依据是最小化簇间通信量，然后迭代地进行列表调度[15]，根据执行时钟周期数，寄存器压力，簇间通信量调整分簇，直到稳定。列表调度是最为广泛使用的指令调度框架，它根据一些启发因子，例如指令在数据依赖图中的高度，后继的数目等，对数据依赖图进行带优先级的拓扑排序，按照此拓扑序依次尽可能早的发射每一条指令。

Lapinskii等人[的方法按照最迟调度时刻，松弛度(最迟调度时刻与最早调度时刻之差)，数据流后继数目这三个因素对指令排序，按照这个顺序访问每条指令，将指令分派到使计算设备使用代价，总线使用代价，簇间通信代价的带权和最小的簇。在完成初步分簇后，此方法迭代地对不同簇的边缘指令(与其他簇存在通信的指令)进行“扰动”，尝试将其分派到其他簇能否得到更优的结果，进一步提高分簇效果。

Ozer等人[7首次提出了统一指令分簇与调度的方法，称为UAS(unified assignment and scheduling)。UAS 在列表调度的框架下进行，根据指令的数据流依赖前驱指令的完成时间(UAS 称为 completion-weighted predecessor,CWP)，在BUG称为开始时刻(StartCycle)，当前指令开始时刻等于依赖前驱完成时刻的最大值)决定当前待调度指令的被分派的簇，并尽可能早的发射当前指令和其所需的簇间传输指令。

Kailas等人[8提出的CARS代码生成框架基于列表调度实现了统一了指令分簇和调度，以及寄存器分配的算法，在CARS中，指令分簇依然采用了开始时刻作为分簇的启发因子。

Zhang等人[9提出了一个精心构造的启发因子，称为lmax-succesor-tree-consistentdeadline，定义为对指令及其所有后继的任意一种可行的分簇调度方案(每条指令的发射时刻都不超过给定的上界)中该指令的最晚的执行完成时间。这个方法在列表调度框架下，选择此启发因子最小的就绪指令，将其分派到能尽早发射的簇上，并确定发射时刻。

Porpodas等人[I0]提出的LUCAS算法综合了开始时刻与完成时刻作为启发因子，在列表调度框架下，当面临拥塞（就绪指令数目 $>$ 发射宽度 $\times$ 簇间通信延迟)或高松弛度(松弛度 $\because$ 发射宽度 $\times 2$ (簇间通信延迟-1)，松弛度为指令最迟调度时刻减去最早调度时刻)时选择使开始时刻最小的分簇，否则选择使指令完成时刻最小的分簇。

王玉林等人[16]则使用模拟退火算法进行分簇与调度，将调度后的时钟周期作为反馈，迭代的提高分簇质量。一些工作将分簇与循环的模调度一同实现，在对循环软件流水化时考虑指令的分簇，例如文献[17，18]，这些方法能有效的提升程序的性能，但循环软件流水要求循环内无分支，或者分支情况比较简单，能使用If-Conversion[19]转换为谓词指令再实现软件流水[20]，限制较大。

# 1 总览

本文的方法实现在编译器令选择之后，寄存器分配之前，以整个函数为输入，函数表示为控制流图，每个基本块表示为数据依赖图。

整数线性规划指变量取值为整数的线性规划，定义为，给定一系列整数变量 $\pmb { x } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) ^ { T }$ ，称为决策变量，在满足一系列不等式 $A x \geq b$ ，以及 $x _ { 1 } , x _ { 2 } , . . . , x _ { n } \geq 0$ 的条件下，使线性函数 $c ^ { \mathrm { T } } { \pmb x }$ 最小，其中A是一个实数矩阵，c是一个实数向量。决策变量仅取值为0或1的整数线性规划称为零一规划，是一种常见的建模方式。

本文中指令分簇与调度都使用零一规划来建模，主要决策变量以及相关符号见表1，约束规则可以粗略地分为三类，包括指令出现次数约束、资源约束和依赖约束，优化目标为每个基本块执行时间的带权和，权值为基本块的估计执行次数，基本块执行时间使用最后一条指令的发射时刻表示。

表1文中主要符合及其表示意义  
Tab.1Symbols in this paper and its meaning   

<html><body><table><tr><td>符号</td><td>意义</td></tr><tr><td>Pi,m</td><td>零一变量，指示指令i是否被分派到编号为m的簇。 i为函数中任意需要分簇的指令(如跳转，NOP等指 令不需要分簇),1≤m≤M。</td></tr><tr><td>TB.i,</td><td>零一变量，指示基本块B中的指令i是在时刻t发 射。B为函数中的任意基本块，i为B中任意指令， 1≤t≤T(B)。</td></tr><tr><td>nB.1</td><td>零一变量，指示基本块B中时刻t是否被占用，B为 函数中的任意基本块，1≤t≤T(B)。</td></tr><tr><td>8i</td><td>零一变量，指示指令i,j是否被分派到同一个簇。 i,j为任意两个存在反依赖或输出依赖的指令。</td></tr><tr><td>M T(B)</td><td>目标平台中簇的数目。</td></tr><tr><td>N</td><td>基本块B执行的时钟周期数的一个估计上界。 VLIW长度。</td></tr><tr><td>W(B)</td><td>基本块B的执行次数期望。</td></tr><tr><td>I(B)</td><td>基本块B中的非簇间传输指令集合</td></tr><tr><td>X(B)</td><td>基本块B中所有可能的簇间传输指令集合</td></tr><tr><td>RES(i,k,r)</td><td>指令i在流水线第k阶段占用机器资源r的数目</td></tr><tr><td>M(r)</td><td>目标机器中资源r的数目</td></tr><tr><td>x(v,m,m)</td><td>将变量V从簇m传输到簇m的簇间传输指令。</td></tr><tr><td>cluster(i)</td><td>整数规划中关于决策变量的表达式，值为指令i所在 的簇编号。</td></tr><tr><td>cycle(B,i)</td><td>整数规划中关于决策变量的表达式，值为基本块B</td></tr><tr><td></td><td>中指令i的发射时刻。 整数规划中关于决策变量的表达式，取值0或1，指</td></tr><tr><td>occur(B,x)</td><td>示簇间传输指令x是否在出现基本块B中。</td></tr></table></body></html>

# 2 簇间传输指令

考虑任意变量 $\nu$ ，它可能因为定义它的指令被分派到不同簇而出现在不同簇，使用 $ { \boldsymbol \nu }$ 的指令也可能被分派到其他不同的簇，因此需要簇间传输指令来传递 $\nu$ 。传输变量 $ { \boldsymbol \nu }$ 所有可能的簇间传输指令 $x ( \nu , m _ { 1 } , m _ { 2 } )$ 共有 $M ( M - 1 )$ 种。这些簇间传输指令可能被调度到定义与使用 $\nu$ 之间的任意一条路径上的任意基本块中，为了表示这些调度结果，对于每种簇间传输指令 $x ( \nu , m _ { 1 } , m _ { 2 } )$ ，在这些路径中的每个基本 $B$ 中，决策变量$\tau _ { B , x ( \nu , m _ { 1 } , m _ { 2 } ) , t }$ 都有定义。

例如，对于图1的控制流图，定义使用变量 $\nu$ 的路径包括， $\mathrm { A { \to } E , \mathrm { A { \to } E { \to } F , \mathrm { B { \to } C { \to } E } } } ,$ $_ { \mathrm { B \to C \to E \to F } }$ ， $\mathrm { B \to D \to F }$ 这5条路径，因此在A、B、C、D、E、F上关于传递 $\nu$ 的簇间传输指令的决策变量 $\tau$ 都应当有定义，否则无法表达所有可能的簇间传输指令插入方案，图2\~4显示了几种分簇与簇间传输指令插入方案(图中簇间传输指令形如 $\mathrm { X v } = \mathrm { Y v }$ ，表示将v从簇Y传递到X)，可见簇间传输指令可以出现在图中每个基本块中。

![](images/df5ed195a8bde1425a4ec2e12aca1df560ea266b00c0a1621651d8108111d7c7.jpg)  
图1控制流图

![](images/543b3a2c5478500b348dac8ff06070049dc69f28bebc8f0fcfcde38ae5b5b8ec.jpg)  
图2一种分簇与簇间传输指令插入方案

![](images/195e3db5701ebc68bd0574ba4bcc24ec1b6c3fed6ef18900c8915b6809504de6.jpg)  
Fig.1Control flow graph   
图3一种分簇与簇间传输指令插入方案  
Fig.3Acluster assignment and inter-cluster transfer instructions insertion scheme

![](images/ff2d70d909dbdd7534d225a8391725e59d832051b0d6e8153bea0a90f9617f42.jpg)  
Fig.2Acluster assignment and inter-clustertransfer instructions insertion scheme   
图4一种分簇与簇间传输指令插入方案  
Fig.4Acluster assignment and inter-cluster transfer instructions insertion scheme

但簇间传输指令只出现在输入函数中已有的基本块中并不一定是最优方案。考虑如图5所示的控制流图，当I1和I4 被分派到不同簇时，若将簇间传输指令插入在A中则会导致在程序执行路径为 $\mathrm { A } {  } \mathrm { C }$ 的情况下会执行一条多余的指令，如图6所示，而若插入在D中，则当程序执行路径为B$\mathrm { \Gamma \to D }$ 时，则执行该簇间传输会导致数据错误，如图7所示。这种情况的解决方案是将簇间传输指令插入在路径 $\mathrm { A \to D }$ 之间新构建的基本块中，如图8所示，确保仅在程序执行该路径时簇间传输指令才会被执行。尽管这样可能新的引入跳转指令，导致较长延迟，但若存较多的簇间传输指令插入，重复执行无用指令浪费的时钟周期可能更大。

重复执行与额外的跳转开销之间的权衡会在整数线性规划求解中得到最佳的选择，但必须保证解空间中存在这样的方案。因此，对于任意控制流图的边，若其起点有多条出边，终点有多条入边，则需要在该边上构建一个新的基本块，若该边是直接下落边(即前后两个基本块地址连续)，那么新插入的基本块为空基本块，否则其中应当存在一条跳转指令，跳转目标是该边的后继，这条跳转指令是否出现在最终的目标代码中依赖于新的基本块中是否有簇间传输指令；而若起点只有一条出边或终点只有一条入边，那么簇间传输指令可以插入在起点块或终点块中，插入在新构建的块上只会带来更大的开销。

A B   
I1: write V I2: write V   
1 1   
C D   
13: read v I4: read v

![](images/0284656041dc367c5bdf8345c0d244d5b1d8f0c5f0f76d2ad9199848a22352b2.jpg)  
图5控制流图

![](images/0da7d0860ae5b2c438ffc7d0670c921f20a8a0be1bea43a36df01099b49bf217.jpg)  
Fig.5Control flow graph   
图6执行多余指令的情况 Fig.6Case of execution redundant instruction   
图8簇间传输指令插入在新的基本块中的情况Fig.8Case of inter-clustertransfer instruction insertingin new basic block

![](images/9cfa34e7ecb533c9aef1a87d22c498351ece95b76c73b0dd4cced4f16c2704dd.jpg)  
图7引起数据错误的情况Fig.7Case of data error

# 3 约束

# 3.1指令出现次数约束

最基本的，待分簇的指令必须且只能被分派到一个簇中，对于任意待分簇指令 $i$ ，有如下约束规则：

$$
\sum _ { m = 1 } ^ { M } \rho _ { i , m } = 1
$$

在此约束的保障下，根据零一变量的特性，指令i被分派到的簇编号可以记为

$$
c l u s t e r ( i ) : = \sum _ { m = 1 } ^ { M } m \times \rho _ { i , m }
$$

同理，函数中原有的基本块 $B$ 中的任意 $i$ 必须且只能被调度到某一个时钟周期：

$$
\sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , i , t } = 1
$$

基本块 $B$ 中指令 $i$ 被调度的时钟周期可以记为

$$
c y c l e ( B , i ) : = \sum _ { t = 1 } ^ { T ( B ) } t \times \tau _ { B , i , t }
$$

簇间传输指令被调度的情况依赖于对应变量的定义与使用的指令的分簇情况，可以总结为以下四条规则：

对于任意变量 $\nu$ ，当任意两条读写变量 $\nu$ 的指令 $i , j$ 被分派到任意不同的两个簇 $m _ { 1 } , m _ { 2 }$ 时，簇间传输指令 $x ( \nu , m _ { 1 } , m _ { 2 } )$ 必须在它们之间的每条路径 $P$ 中的某个基本块内被调度。容易验证，此约束可以表示为如下形式：

$$
\sum _ { B \in P } \sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , x ( \nu , m _ { 1 } , m _ { 2 } ) , t } \geq \rho _ { i , m _ { 1 } } + \rho _ { i , m _ { 2 } } - 1
$$

这条约束使簇间传输指令总是从定义变量的指令所在的簇读取数据，排除了簇间传输指令“接力”传递的情况。尽管“接力”方案也是合法方案，但在大多分簇VLIWDSP上，“接力”方案不可能是唯一的最优方案。从数据流依赖情况来看，簇间传输指令从其他簇间传输指令的结果中读取数据的最早发射时刻总是晚于直接从定义变量的指令所在的簇读取数据。从资源占用方面来看，只有簇间传输指令占用簇间传输总线这一机器资源，且簇间传输指令只占用该资源，因此，无论簇间传输指令从哪个簇读取资源，其资源占用情况都对非簇间指令不构成竞争关系，不会在资源方面影响调度，另一方面，由于总线的特性，只有从同一个簇读取同一数据的簇间传输指令可能在同一个周期发射，因此所有簇间传输指令全都从定义变量的指令所在的簇读取数据能得到的结果总是优于或等于多个簇间传输指令接力的情况，因此，此约束并不会限制降低分簇质量。

对于任意变量 $\nu$ ，设定义它的指令为 $i$ ，在控制流图中，任意一条从 $i$ 到使用 $\nu$ 的指令的路径 $P$ 上，对于任意簇 $m$ ，仅当指令 $i$ 没有被分派到簇 $m$ 时，将数据传输到 $m$ 的簇间传输指令才允许出现，且最多在某个基本块中某个时刻出现一次。此约束为

$$
\rho _ { i , m } + \sum _ { B \in P } \sum _ { t = 1 } ^ { T ( B ) } \sum _ { 1 \leq m _ { 1 } \leq M } \tau _ { B , x ( \nu , m _ { 1 } , m ) , t } \leq 1
$$

这一项约束既限制了同一个变量的相同簇间传输指令最多出现一次，还排除了同一条执行路径上存在多个向某个簇中的变量写入数据的不合法方案，如图7的情况。

在定义、使用变量 $\nu$ 的任意一条路径上的每个基本块 $B$ 中，只有当使用 $\nu$ 的指令 $j$ 被分派到簇 $m$ 时，才允许簇间向$m$ 传输数据的传输指令 $x ( \nu , \mathbf { \Lambda } _ { - } , m )$ 在该基本块中出现：

$$
\sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , x ( \nu , \dots m ) , t } \leq \rho _ { j , m }
$$

同理，在定义、使用变量 $\nu$ 的任意一条路径上的每个基本块 $B$ 中，只有当定义 $\nu$ 的指令 $i$ 被分派到簇 $m$ 时，才允许簇间从 $m$ 传输数据的传输指令 $x ( \nu , m , _ { - } )$ 在该基本块中出现：

$$
\sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , x ( \nu , m , _ { - } ) , t } \leq \rho _ { i , m }
$$

簇间传输指令 $x$ 是否出现在基本块 $B$ 可以记为

$$
o c c u r ( B , x ) : = \sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , x , t }
$$

在任意一个新插入的基本块 $B$ 中，只可能存在簇间传输指令和一条跳转指令 $j$ ，当存在其他簇间传输指令被调度，跳转指令 $j$ 必须在 $B$ 中被调度，此约束可以表示为如下形式：

$$
T ( B ) \sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , j , t } \geq \sum _ { x \in X ( B ) } o c c u r ( B , x )
$$

反之，若 $B$ 中不存在簇间传输指令，则 $B$ 可以整个删去，这一条规则不需要表达成约束，因为多一条跳转指令不可能是最优解，会在求解过程中被排除掉。

同一周期发射的指令数目不能超过VLIW长度，对于基本块 $B$ 中的调度，在任意时刻 $t$ ，有：

$$
\sum _ { t = 1 } ^ { T ( B ) } \tau _ { B , j , t } \leq N \eta _ { B , t }
$$

上式除了约束同一时钟周期发射的指令条数，也确保若时刻t存在指令发射，变量 $\eta _ { B , t }$ 为1。但这并不够，为了正确统计基本块 $B$ 中指令调度结果中最后一条指令的发射时刻，必须确保流水线停顿的周期 $\textit { t }$ 对应的变量 $\eta _ { B , t }$ 也为1，还需要增加如下约束：

$$
\forall 2 \leq t \leq T ( B ) : \eta _ { B , t - 1 } \geq \eta _ { B , t }
$$

此约束也使得指令总是被调度到最早的连续若干个时钟周期。

# 3.2依赖约束

基本块中指令之间的依赖关系包括三种数据依赖，分别是流依赖，反依赖输出依赖，另一项依赖关系是，基本块中其他所有指令不能在跳转指令(若存在)之后执行，简单起见：

这一项依赖在本文中简称为控制依赖，值得一提的是，广泛使用的术语“控制依赖”有另外的意义[21]。

依赖约束是指，存在数据依赖或控制依赖的两条指令在被调度后，两者所发射的时刻之差应该大于等于依赖延迟。

基本块 $B$ 中，指令 $i , j$ 之间的依赖若与簇内寄存器无关，或是控制依赖时，依赖约束可以统一表示为

$$
c y c l e ( B , i ) - c y c l e ( B , j ) \geq L
$$

其中 $\boldsymbol { L }$ 表示依赖延迟，在VLIWDSP中，一般控制依赖、反依赖为延迟为0，输出依赖为1，流依赖与流水线长度有关。

当反依赖或输出依赖由簇内寄存器传递时，若依赖的前驱或后继被分派到不同的簇时，则依赖自然地被消除，依赖的前后两条指令可以任意调度，否则就需要满足延迟约束，两种情况统一的约束规则可以用大M法如下表示：

$$
c y c l e ( j ) - c y c l e ( i ) + 2 T ( B ) ( 1 - \delta _ { i , j } ) \geq L
$$

$\delta _ { i , j }$ 表示指令 $i , j$ 是否被分派到同一个簇，它的语义还需要添加如下约束来得到保证：

$$
\begin{array} { l } { { a _ { i , j } + \delta _ { i , j } + b _ { i , j } = 1 } } \\ { { c l u s t e r ( i ) - c l u s t e r ( j ) \geq - M a _ { i , j } + b _ { i , j } } } \\ { { c l u s t e r ( i ) - c l u s t e r ( j ) \leq M b _ { i , j } - a _ { i , j } } } \end{array}
$$

上式中还引入了两个辅助的零一变量 $a _ { i , j } , b _ { i , j }$ ，分别表示$i , j$ 之间簇的编号关系是小于或大于。

流依赖涉及簇间传输指令，考虑指令 $i , j$ 分别定义、使用变量 $\nu$ ，对于任意簇 $m _ { 1 } , m _ { 2 }$ ，仅当 $x \big ( \nu , m _ { 1 } , m _ { 2 } \big )$ 被调度到 $i$ 所在的基本块 $B$ 的某个时刻，且 $i$ 被分派到簇 $m _ { 1 }$ ，才有$x ( \nu , m _ { 1 } , m _ { 2 } )$ 流依赖于 $i$ ，即：

$$
\begin{array} { r l } & { c y c l e ( B , x ( \nu , m _ { 1 } , m _ { 2 } ) ) - c y c l e ( B , i ) + } \\ & { 2 T ( B ) ( 2 - o c c u r ( B , x ( \nu , m _ { 1 } , m _ { 2 } ) ) - \rho _ { i , m _ { 1 } } ) } \\ & { \geq L _ { f l o w } } \end{array}
$$

同理，仅当 $x ( \nu , m _ { 1 } , m _ { 2 } )$ 被调度到 $j$ 所在的基本块，且 $j$ 被分派到簇 $m _ { 2 }$ ， $j$ 才流依赖于 $x ( \nu , m _ { 1 } , m _ { 2 } )$ ，有：

$$
c y c l e ( B , j ) - c y c l e ( B , x ( \nu , m _ { 1 } , m _ { 2 } ) ) +
$$

$$
\begin{array} { r l } & { 2 T ( B ) ( 2 - o c c u r ( B , x ( \nu , m _ { 1 } , m _ { 2 } ) ) - \rho _ { i , m _ { 2 } } ) } \\ & { \geq L _ { \boldsymbol { f l o w } } } \end{array}
$$

当 $i , j$ 在同一个基本块时，若它们被分派到同一个簇，它们存在流依赖，因此需要添加同式13一样的约束，只是将不等式中的延迟换成流依赖的延迟，若它们被分派到不同的簇,则它们之间必然存在簇间传输指令，约束16，17确保了它们的延迟关系能得到满足。

# 3.3资源约束

合法的指令调度还必须满足：对于机器中的任意资源，譬如ALU，立即数通道等，在任意时刻执行的指令使用的每一类资源不能超过机器限制。指令i在流水线第 $k$ 阶段使用的资源 $\boldsymbol { r }$ 的数目记为 $R E S ( i , k , r )$ ，大多数情况下资源冲突只会发生在少数流水线阶段，不同的指令可能会在占用资源的阶段也可能不同， $R E S ( i , k , r )$ 只在这些会冲突的阶段上有定义。

分簇DSP的资源可以被划分为两类。一类是全局资源由整个DSP共用的，指令使用该资源的情况与指令所在的簇无关；另一类是簇内资源，只能由簇内的指令使用，且每个簇拥有相同数目。值得注意的是，簇间数据总线也是簇内资源，表示为每个簇中的若干个读写端口。

考虑基本块 $B$ 的调度，对于全局资源 $\boldsymbol { r }$ ，在任意时刻 $t$ 执行的所有指令使用资源 $r$ 的总和不超过机器限制，有：

$$
\sum _ { i \in B } \sum _ { k \le t } \tau _ { B , i , t - k } \times R E S ( i , k , r ) \le M ( r )
$$

簇内资源中，簇间读写端口需要单独考虑。当 $\boldsymbol { r }$ 是簇间总线的读端口时，对于任意簇 $m$ ，仅有从 $m$ 读取数据的簇间传输指令会占用，设在可能在 $B$ 中被调度的这些簇间传输指令为 $X ( B , m , _ { - } )$ ，簇间传输指令使用总线的约束如下：

$$
\sum _ { i \in X ( B , m , \supset } \sum _ { k \leq t } \tau _ { B , x , t - k } \times R E S ( x , k , r ) \leq M ( r )
$$

类似的，当资源 $\boldsymbol { r }$ 是簇间总线的写端口，对于任意簇 $m$ ，设在可能在 $B$ 中被调度的、目标是 $m$ 的簇间传输指令为$X ( B , . . , m )$ ，约束为

$$
\sum _ { i \in X ( B _ { \cdot - } , m ) } \sum _ { k \leq t } \tau _ { B , x , t - k } \times R E S ( x , k , r ) \leq M ( r )
$$

对于簇内的其他资源，资源使用情况则与待分簇指令自身分派的簇有关，资源约束为

$$
\sum _ { i \in X ( B , \_ m ) } \sum _ { k \leq t } ( \rho _ { i , m } \wedge \tau _ { B , x , t - k } ) \times R E S ( x , k , r ) \leq M ( r )
$$

上式中的 $\wedge$ 表示零一变量的逻辑合取，通过引入额外的一个零一变量，并添加约束 $2 ( \alpha \wedge \beta ) \geq \alpha + \beta , ( \alpha \wedge \beta ) \leq \alpha , ( \alpha \wedge \beta ) \leq \beta$ 得到线性表达。

# 4 优化目标

分簇调度的目标是使函数执行时间最短，但程序的执行时间是不可判定问题，只能近似。基本块在前文约束的保证下，基本块 $B$ 的最后一条指令的发射时刻为

$$
\sum _ { t = 1 } ^ { T ( B ) } \eta _ { B , t }
$$

设输入的函数为 $F$ ，优化目标为

$$
\sum _ { B \in { \cal F } } W ( B ) \sum _ { t = 1 } ^ { T ( B ) } \eta _ { B , t }
$$

在没有其他信息的情况下，估计基本块 $B$ 的执行次数W(B)基于一个直观的原则：处于循环中的基本块，循环层次越靠内，执行次数越大，远远大于循环外的块，除了循环的回边外，假设跳转指令的分支概率相同。设分簇调度的函数的控制流图是可规约的，本文采取如下方法估计基本块的执行次数：

忽略控制流图中的回边，若在新插入的块在回边上也一同忽略该块，将控制流图的入口块为执行次数设为 $W _ { 0 } = 1$ ，广度优先遍历控制流图，基本块的出边平分基本块的次数，基本块的执行次数等于入边次数之和。

识别流图中的自然循环，合并具有相同首节点的循环。设基本块(或边)被包含在循中的次数为 $k$ ，那么该块(或边)的次数估计为 $1 0 0 ^ { k } W _ { 0 }$ ，循环的回边平分回边的起点的权值，回边上插入的基本块的执行次数等于该边的执行次数。

# 5 其他细节

# 5.1处理函数调用指令

出于简化表达的目的，上文中线性整数规划建模忽略了函数调用指令这一特殊情况。函数调用指令实际执行时间依赖于被调用的函数，无法判断，并且当函数返回时，返回值寄存器中的数据已准备好，即使下一条指令要使用函数的返回数据，也不需要再等待流依赖延迟，前文中的依赖约束不能准确的表达这种情况。将函数指令看做基本块边界能绕过这一问题，但会稍微错失一点并行机会，另一个方法是让函数调用指令的发射占用多个时钟周期，等于最大延迟 $\boldsymbol { L }$ ，这样当函数调用指令执行完后所有依赖它的指令都已满足延迟，能直接发射，不用改变前文的建模方式。尽管这样做会使优化目标中对最后一条指令发射时刻的计算不精确，但是并不影响最终目的，即对程序执行时间的近似。在这种方法下，函数调用指令发射占用的第2到 $\boldsymbol { L }$ 时钟周期，不应该有其他指令占用，设基本块 $B$ 中的函数调用指令为 $\boldsymbol { \mathscr { c } }$ ，这项约束为

$$
\sum _ { u = t } ^ { \forall 1 \le t \le T ( B ) - L : } \sum _ { i \in B \land i \neq c } \tau _ { B , i , u } \le ( 1 - \tau _ { B , c , t } ) T ( B ) N
$$

# 5.2优化求解速度

由于DSP的各簇都是同构的，所以存在许多对称的分簇方案，破除这些对称往往能加快整数线性规划求解，思路为尽量将指令分派到簇编号较小的簇。可以通过添加如下约束不等式来实现目标：

$$
\forall 2 \leq m \leq M : \sum _ { i \in F } \rho _ { i , m - 1 } \geq \sum _ { i \in F } \rho _ { i , m }
$$

基本块 $B$ 中每条指令实际能发射的时刻范围一般远远小于1到 $T ( B )$ 约束每条指令的发射周期范围能够大幅降低整数线性规划求解时的搜索空间。将程序依赖图看做一个AOE网，容易求出每条指令 $i$ 的最早发射时间与最晚发射时间。如果不考虑机器资源，显然指令只能在最早发射时间与最晚发射时间之间被发射，但由于分簇可能插入簇间传输指令，以及DSP的发射数限制，实际上指令合法的发射时刻可能会大于该最晚发射时间，因此实际上使用如下方法保守的估计指令发射时刻的区间：

a)对于任意基本块，遍历不含簇间传输指令的程序依赖图，计算最早发射时刻：

$$
e t ( i ) = \left\{ \begin{array} { c c } { 0 } & { i f \ p r e d ( i ) = \emptyset } \\ { \displaystyle { \operatorname* { m a x } _ { j \in p r e d ( i ) } ( e t ( j ) + l a t _ { i , j } ) } } & { o t h e r w i s e } \end{array} \right.
$$

其中pred(i)分别表示指令 $i$ 的在图中的所有直接间接前驱，$l a t _ { i , j }$ 表示指令 $i , j$ 之间的延迟。

b)遍历包含簇间传输指令的依赖图，使用步骤a)中的公式，以及结果，计算每条簇间传输指令的最早发射时刻。

c）计算指令发射时刻的下界：

$$
l b ( i ) = \operatorname* { m a x } \biggl ( e t ( i ) , \biggl \lfloor \frac { \mid p r e d ( i ) \vert } { N } \biggr \rfloor \biggr )
$$

d)遍历不含簇间传输指令的程序依赖图，设当前处理的基本块为 $B$ ，计算指令的最晚发射时刻：

$$
\mathit { l t } ( i ) = \left\{ \begin{array} { r } { T ( B ) \quad \quad i f \ s u c c ( i ) = \emptyset } \\ { \operatorname* { m i n } _ { \substack { j \in s u c c ( i ) } } ( \mathit { l t } ( j ) - \mathit { l a t } _ { i , j } ) \quad \ o t h e r w i s e } \end{array} \right.
$$

其中 $s u c c ( i )$ 表示指令 $i$ 的所有直接间接后继。此处的最晚发射时刻 $l t$ 与AOE网络中的定义并不一样，实际上是反方向计算的最早发射时刻。

e）遍历包含簇间传输指令的依赖图，使用步骤d)中的公式，以及结果计算每条簇间传输指令的最晚发射时间。

f）计算指令发射时刻的上界：

$$
u b ( i ) = \operatorname* { m i n } \Bigg ( l t ( i ) , T ( B ) - \Bigg \lfloor \frac { \mid s u c c ( i ) \mid } { N } \Bigg \rfloor \Bigg )
$$

对于任意基本块 $B$ ，限制非簇间传输指令发射在估计的区间内的约束为

$$
l b ( i ) \leq c y c l e ( B , i ) \leq u b ( i )
$$

簇间传输指令 $x$ 的发射时刻上界约束与其他指令的相同，但由于簇间传输指令 $x$ 不一定被调度， $c y c l e ( B , x )$ 可能为0,所以，其发射时刻上界约束为

$$
l b ( i ) { \le } c y c l e ( B , x ) + T ( B ) ( 1 - o c c u r ( B , x ) )
$$

# 6 实验评估

本文选用HXDSP1042作为算法的验证平台，HXDSP1042一款典型的分簇VLIWDSP，由中国电子科技集团第38研究所研发，支持16发射，有4个簇，13级流水线，各簇之间通过总线通信，已经被大量运用在雷达信号处理上。整数线性规划求解是另一个复杂的话题，超出本文讨论的范围，本文使用求解器gurobi[22]来实现本文的算法。测试程序选择的是DSPStone[23]，编译时开启O2优化，仅替换指令分簇与指令调度优化，并实现了几种统一分簇与调度的方法作为参考，这些算法对测试程序中每个基本块分别进行，而本文的方法实现在整个函数上，测试程序在HXDSP1042的仿真器上执行，结果显示了本文的方法相比效果最好的近似算法LUCAS在不同的测试程序上有 $20 \%$ 到 $3 5 \%$ 的性能提升。图9显示了几种方法在DSPStone中几项测试程序中的归一化执行时间，使用UAS 算法的结果作为基准1。其中UAS-CC表示使用完成时间作为为启发因子的UAS算法，LSTC 表示文献[9]提出的算法，ILP表示本文的方法。

![](images/9f78e022db73ef6f3cf599fd6443b80c020adbf377d08ccba5e5e6ad71e9ad16.jpg)  
图9性能测试结果  
Fig.9Benchmark results

尽管整数线性规划是NP问题，但对于一般程序中的函数，使用分支定界法往往能较快的求解出最优解。本文从在GSL[24]、FANN[25]、Zlib、DSPStone 中随机选择了共4000个函数，在一台intelCorei5-8300H的笔记本电脑上测试了本文的算法，结果显示，其中约 $81 \%$ 的函数能在0.5s内得到结果，如表2所示。

表2算法耗时  
Tab.2Time used by algorithm   

<html><body><table><tr><td colspan="5">耗时范围最少指令数 最多指令数平均指令数函数个数占总数比例</td></tr><tr><td>≤0.02s</td><td>4</td><td>7</td><td>5.2 361</td><td>9.03%</td></tr><tr><td>0.02-0.1s</td><td>4</td><td>34</td><td>16.9 648</td><td>16.20%</td></tr><tr><td>0.1-0.5s</td><td>15</td><td>139</td><td>47.2 2237</td><td>55.93%</td></tr><tr><td>0.5-2.5s</td><td>27</td><td>213</td><td>92.1 354</td><td>8.85%</td></tr><tr><td>2.5-10s</td><td>20</td><td>563</td><td>159.5 296</td><td>7.40%</td></tr><tr><td>>10s</td><td>74</td><td>1588</td><td>410.6 104</td><td>2.60%</td></tr></table></body></html>

# 7 结束语

本文使用整数线性规划方法，实现了分簇VLIWDSP上的指令分簇与指令调度，并在HXDSP1042进行了实验，结果表明本文方法能有效提高程序的性能，且算法的运行时间是可以接受的，尽管与近似算法还有一定差距，但已经具备了相当的实用性。一个不足之处在于对函数执行时间的估计过于粗糙，这个问题可以通过利用编译器高层的信息，或采用深度方法预测[26]分支概率得到改善。另一个问题是本文的方法的时间开销还有优化空间，其原因在于使用了一个大的整数线性规划模型来表示所有指令的分簇与调度，求解时间开销比较大，但实际上往往存在许多指令的分簇和调度与另外许多指令无关。因此下一步的研究将探索如何将函数分割为多个部分，对每个部分分别建模求解并保证整体结果最优，从而进一步提高求解速度。

# 参考文献：

[1]Mattson P,Dally WJ,Rixner S,et al.Communication scheduling [J]. ACM SIGOPS Operating Systems Review,2000,34 (5): 82-92.   
[2]KesslerR.The alpha 21264 microprocessor[J].IEEE Micro,1999,19 (2): 24-36.   
[3]Ellis JR.Bulldog: a compiler for VLSI architectures [M]. Cambridge, MA:Mit Press,1986.   
[4]LowneyPG,Freudenberger SM,Karzes TJ,et al.The multiflow trace Springer,1993: 51-142.   
[5]Desoli G. Instruction assignment for clustered VLIW DSP compilers: A new approach [M]. Palo Alto, California: Hewlett Packard Laboratories, 1998.   
[6]Lapinskii V S,Jacome MF,De Veciana G A. Cluster assignment for high-performance embedded VLIW processors [J].ACM Trans on Design Automation of Electronic Systems (TODAES),2002,7(3): 430- 454   
[7]Ozer E,Banerjia S,Conte T M. Unified assign and schedule: A new approach to scheduling for clustered register file microarchitectures [C]/ Proc of the 31st Annual ACM/IEEE International Symposium on Microarchitecture.Piscataway,NJ: IEEE,1998: 308-315.   
[8] Kailas K,Ebcioglu K, Agrawala A. CARS: A new code generation framework forclustered ILPprocessors [C]//Proc ofthe 7th International Symposium on High-Performance Computer Architecture. Piscataway, NJ: IEEE,2001: 133-143.   
[9]Zhang Xuemeng,Wu Hui,Xue Jingling.An efficient heuristic for instruction scheduling on clustered VLIW processors [C]// Proc of the 14th International Conference on Compilers,Architectures and Synthesis for Embedded Systems.2011: 35-44.   
[10] Porpodas V,Cintra M.LUCAS:latency-adaptive unified cluster assignment and instruction scheduling [J]. ACM SIGPLAN Notices, 2013, 48 (5): 45-54.   
[11]Fisher JA.Trace scheduling:A technique for global microcode compaction [J].IEEE Trans on Computers,1981,30 (07): 478-490.   
[12] Wilken K,Liu J, Heffrnan M. Optimal instructionscheduling using integer programming [J]. ACM SIGPLAN Notices,2000,35 (5):121- 133.   
[13] Kästner D,Winkel S.ILP-based Instruction Scheduling for IA-64 [J]. ACM SIGPLAN Notices,2001,36 (8): 145-154.   
[14] Mendis C,Amarasinghe S. goSLP: globally optimized superword level parallelism framework [J/OL]. Proc of the ACM on Programming Languages，2018,2 (OOPSLA): 1-28.(2018-10-24） [2022-05-07]. https://doi.0rg/10.1145/3276480.   
[15] Fisher JA. The optimization of horizontal microcode within and beyond basic blocks: An application of processor scheduling with resources [D]. New York: New York University,1979.   
[16]王玉林，郑启龙．魂芯分簇VLIWDSP上指令调度的优化[J].微 型机与应用,2017(11): 23-26.(Wang Yulin,Zheng Qilong.Instruction scheduling optimization for clustered VLIW HXDSP[J]. Microcomputer & Its Applications,2017 (11): 23-26)   
[17] Zalamea J,Llosa J,Ayguadé E,et al. Modulo scheduling with integrated register spilling for clustered VLIW architectures [C]//Proc of the 34th ACM/IEEE International Symposium on Microarchitecture. MICRO-34. Piscataway,NJ: IEEE,2001:160-169.   
[18] Aleta A,Codina JM,Sanchez J,et al.AGAMOS:A graph-based approach to modulo scheduling for clustered microarchitectures [J]. IEEE Trans on Computers,2009,58(6): 770-783.   
[19] MAHLKE S A,LIN DC,CHEN W Y, et al. Effective compiler support for predicated execution using the hyperblock [J].ACM SIGMICRO Newsletter,1992,23 (1-2): 45-54.   
[20] LLOSA J,GONZALEZ A，AYGUADE E，et al. Swing module scheduling:a lifetime-sensitive approach [C]// Proc of the 22nd Conference on Parallel Architectures and Compilation Technique. Piscataway,NJ: IEEE,1996:80-86.   
[21] Ferrante J, Ottenstein K J, Warren JD. The program dependence graph and its use in optimization [J]. ACM Trans on Programming Languages and Systems(TOPLAS),1987,9(3):319-349.   
[22] Gurobi Optimization,LLC.Gurobi Optimizer Reference Manual [EB/OL].[2022-05-07].https://www.gurobi.com.   
[23] Institute for Communication Technologies and Embedded Systems. DSPStone [EB/OL].[2022-05-07].https://www. ice．rwth-aachen. de/research/tools-projects/closed-projects/dspstone.   
[24] Gough B.GNU scientific library reference manual [M].[S.1.] :Network Theory Ltd.,2009.   
[25]Nissen S.Implementation of a fast artificial neural network library (fann) [EB/OL].(2003)[2022-05-07].http://fann.sourceforge.net/report.   
[26] BieberD,Sutton C,Larochelle H,et al.Learning to execute programs with instruction pointer attention graph neural networks [C/OL]/ Advances in Neural Information Processing Systems.New York,NY: Curran Associates,Inc.,2020:8626-8637. https://proceedings.neurips. cc/paper/2020/file/62326dc7c4f7b849d6f013ba46489d6c-Paper.pdf