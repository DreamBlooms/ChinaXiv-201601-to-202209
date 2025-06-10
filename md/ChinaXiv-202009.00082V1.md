# 基于国产众核处理器三维地震声波正演模拟

陈宏博1,²，钱雪忠1，甘霖2,3

(1.江南大学，物联网工程学院，物联网技术应用教育部工程研究中心，江苏无锡 214122;2.国家超级计算无锡中心，江苏无锡 214131;3．清华大学，北京 100084)

摘要：三维地震声波理论与计算方法是地质勘探研究的基础，通过分析不同介质中声波的传播特性，完成三维地震声波正演模拟。针对三维地震声波有限差分交错网格方程正演过中存在数值计算大、内存消耗大等实际问题，本文提出基于“神威·太湖之光”超级计算机系统中，国产异构众核处理器(申威26010)的三维地震声波正演模拟编程模型，完成基于处理器间的进程级并行，与基于计算核心间的线程级并行优化策略。研究了DMA(直接内存读取)通信方式，提出2.5D流水线任务划分、通信与计算的相互掩盖的多角度的优化策略。实验结果表明该策略有效缓解了带宽瓶颈，发挥了处理器强大的计算能力，解决了程序在申威26010异构众核处理器处理有限差分问题时，并行效率过低的问题。在大规模测试下，使用266240个计算核心，程序仍能够保持稳定的计算性能，达到5.5GFlops 的场值更新。

关键词：并行计算；地震声波正演；交错网格；高性能计算 中图分类号：TP doi:10.19734/j.issn.1001-3695.2020.03.0066

3d seismic acoustic wave forward modeling based on domestic heterogeneous many-core processors

Chen Hongbo1,2, Qian Xuezhong1, Gan Lin2, 3 (1.EngineeringResearchCenterofInternetofThings TechnologyApplicationsMinistryofEducationchoolofInternetof Things Engineering,Jiangnan UniversityWuxi 214122,China;2.National supercomputingcenterin Wuxi,Wuxi214131, China; 3. Tsinghua university,Beijing 100084, China)

Abstract:3d seismic acoustic wave theory and calculation method are the basis of geological exploration research.By analyzing the propagation characteristicsof acoustic waves in diferent media,wecanapplythe 3d seismic acoustic wave forward mod-eling in exploration work.In order to solve the problem of huge numerical calculation and large memory consumption while proceeding 3Dseismic wave equationstaggered gridfinite diference forwarding model,we studiedand implementedthe parallloptimizationonthe heterogeneous many-core processors of the Sunway Taihulightsupercomputer. Based on the implementation of a two-level parallel programming model by using MP $^ +$ Sunway Athread, we generated the DMA communication,2.5D pipelining task divisionand other optimization strategies.The model with this improvement reduced thenegativeefects bybandwidthand greatlyutilizedthecomputingpower.Inlarge-scaleconditions,wetackledthe issueoflow eficiencyabout program executiononSW260l0 het-erogeneous many-core processors.Theexperimentalresults revealthat the performanceofparallel-ismofasinglenodeis muchbeterthan thatofamastercore.Another example is the calculationofsolving numeri-calstressis 8Otimesfasteronthecore groupthanthatonthesingle mastercore.This experiment could keep a con-stant performance by using 266240 cores,5.5GFlpos updates of field.

Key words: parallel computing; seismic waves are developing; staggered grid; high performance computing

# 0 引言

地震声波正演技术在研究多种区域地震资料的采集与处理的过程中发挥了重要作用，是地震数据采集、处理、解析三大环节的基础，深入研究地震声波正演模拟技术，对于整个地震勘探的研究具有重要意义。

上世纪60年代末国内外专家学者已开始对地震声波正演模拟技术进行研究。1968年，Alterman和Karal将有限差分法引入到波动方程正演模拟中，实现了层状介质二维弹性波动方程的有限差分离散形式[1]。1976年Madariaga 首次提出了速度-应力交错网格的有限差分法[2]。Virieux在1984用交错网格差分格式对横波在而为非均匀介质中进行正演模拟[3]，1986 年又对转换横波做了交错网格的正演模拟[4]。随着研究的深入有限差分法在声波研究领域的重要性逐渐显现，已成为声波数值模拟的主流方法。

国内很多学者在波场模拟中引入交错网格差分格式[5]。董良国将交错网格与高阶差分法有机结合，求解各向同性一阶速度一应力弹性波方程，使用交错网格高阶有限差分法，解决声波传导问题。李斌等提出了高精度的交错网格方法[]，近几年多种不规则网格的差分格式不断涌现[7]。

一方面，为提高计算效率，一大批学者通过GPU(graphicprocessingunit，图形处理器)对计算部分进行加速，宋鹏等人通过MPI+OpenMP的方式完成了完成了三维声波方程的GPU加速版本[8]。2010年Komatitsch通过MPI通信协议使用大规模GPU集群实现了地震声波正演[]。然而，在实际正演过程中由于核心计算对存储量需求过大，并行效率降低，特别是当空间维度由二维伸展到三维，空间网格数呈现几何倍增长，网格点数增至百万甚至亿级别，此时对数据仅作简单的并行计算，难以满足实际应用需求。

另一方面，在过去的几十年里高性能计算技术得到了飞速发展。中国自主研制的高性能计算机也在近十年的时间里实现了一系列重大突破，先后诞生了天河系列[10,I1]、神威系列[12]等超算系统，得到了世界范围专家学者的高度认可[13]。

本文基于“神威·太湖之光"超级计算机体系架构，实现三维地震程有限差分高阶交错网格方程正演模拟的多级并行，分析神威并行编译工具的多种并行模式，设计并行策略提升程序并行效率。一级并行采用MPI信息传递接口通信协议，重新划分数据减少通信，实现进程级别并行。二级并行使用神威线程加速库提高芯片利用率，在大规模计算中采用多级异构并行协作方案，通过2.5D流水线与通信计算相互掩盖的策略，降低内存和LDM(局部数据存储)的存储消耗，缓解了带宽限制。实验发现，在大规模规模测试下程序仍有较好的扩展性能，为国产自主研发芯片应用与地球物理核心算法提供了重要技术参考。

# 1 三维地震声波正演模拟简介

# 1.1三维声波方程

三维地震声波正演技术以已知地质结构为研究基础，通过数值计算等方法生成地震记录与地震声波场传播快照。在地震声波正演模拟的实际应用中，有限差分法是当前理论最成熟、应用最广泛地模拟方法。

有限差分方法将模拟区域按矩阵进行划分，通过网格点上数据的差商离散声波方程的一阶或多阶导数得到差分方程组，求解方程既可得到区域的波场值。在非均匀各项同性介质中，若各项力为零，三维声波一阶应力-速度方程可表示为[18]

$$
\frac { \hat { c } P } { \hat { c } t } = \rho \nu ^ { 2 } \left( \frac { \hat { \sigma } V _ { x } } { \hat { \sigma } x } + \frac { \hat { \sigma } V _ { y } } { \hat { \sigma } y } + \frac { \hat { \sigma } V _ { z } } { \hat { \sigma } z } \right)
$$

$$
\frac { \partial V _ { x } } { \partial x } { = } \frac { 1 } { \rho } { \times } \frac { \partial P } { \partial x }
$$

$$
\frac { \partial V _ { y } } { \partial y } { = } \frac { 1 } { \rho } { \times } \frac { \partial P } { \partial y }
$$

$$
\frac { \partial V _ { z } } { \partial z } { = } \frac { 1 } { \rho } { \times } \frac { \partial P } { \partial z }
$$

其中， $P$ 为应力； $\rho$ 为介质密度； $\nu$ 为波速； $V _ { x } , V _ { y } , V _ { z }$ 分别为x,y,三个不同方向上的质点振动速度。

# 1.2交错网格差分格式

交错网格差分格式的优点为：数值频散降低、泊松比的变化对其影响变小、稳定性提升，特别是在不同介质交界处的正演模拟效果极其显著。将应力与速度分别放在对应的不同网格中，相互交错半个网格，在同等差分交错的条件下，交错网格能够实现更加精准、稳定的波场外推[19]。

交错网格有限差分法在处理三维地震声波方程正演问题时，采用六套网格系统分析法，分别存储xy，上的速度分量以及应力分量，以实现时间与空间交错。采用交错网格有限差分法时各变量在交错网格中的空间分布如图1所示，不同变量分布状况，将应力在时间上的一阶微分方程，用二阶精度差分格式在时间域上展开。空间上根据阶数不同在空间半节点上展开，同时将 $V _ { x } , V _ { y } , V _ { z }$ 在时间半节点上展开，最后将速度在整点空间一阶微分应用在二阶差分格式中得到三维空间一阶速度-应力地震声波方程组的时间二阶的交错网格差分格式：

$$
P _ { ( i , j , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } = P _ { ( i , j , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } + \Delta t \rho \nu ^ { 2 } \sum _ { m = 1 } ^ { L } a _ { m } \left( + \frac { \widehat { \sigma } V _ { _ { x \left( i + \frac { 1 } { 2 } + m - 1 , j , k \right) } } ^ { 2 } + \widehat { \sigma } V _ { _ { x \left( i - \frac { 1 } { 2 } - m + 1 , j , k \right) } } ^ { 2 } } { \widehat { \sigma } x } \right)
$$

$$
V _ { x \left( i + \frac { 1 } { 2 } , j , k \right) } ^ { n + \Delta t } = V _ { x \left( i + \frac { 1 } { 2 } , j , k \right) } ^ { n } + \frac { 1 } { \rho } \sum _ { m = 1 } ^ { L } a _ { m } \frac { P _ { ( i + 1 + m - 1 , j , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } + P _ { ( i - m + 1 , j , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } } { \partial x }
$$

$$
V _ { y \left( i , j + \frac { 1 } { 2 } , k \right) } ^ { n + \Delta t } = V _ { y \left( i , j + \frac { 1 } { 2 } , k \right) } ^ { n } + \frac { 1 } { \rho } \sum _ { m = 1 } ^ { L } a _ { m } \frac { P _ { ( i , j + 1 + m - 1 , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } + P _ { ( i , j - m + 1 , k ) } ^ { n + \frac { 1 } { 2 } \Delta t } } { \partial y }
$$

$$
V _ { z \left( i , j , k + \frac { 1 } { 2 } \right) } ^ { n + \Delta t } = V _ { z \left( i , j , k + \frac { 1 } { 2 } \right) } ^ { n } + \frac { 1 } { \rho } \sum _ { m = 1 } ^ { L } a _ { m } \frac { P _ { ( i , j , k + 1 + m - 1 ) } ^ { n + \frac { 1 } { 2 } \Delta t } + P _ { ( i , j , k - m + 1 ) } ^ { n + \frac { 1 } { 2 } \Delta t } } { \hat { \mathcal { O } } z }
$$

其中， $\boldsymbol { a } _ { m }$ 为 $2 L$ 阶精度差分系数； $\hat { o } x , \hat { o } y , \hat { o } z$ 分别为三个分量方向空间网格大小； $\Delta t$ 为时间采样间隔； $i , j , k$ 为笛卡尔坐标系下标。对于二阶声波方程，由于应力分量与各方向的导数一一对应对应。

![](images/7774fbb80e085592b2ffb2012791ec359cac481b0f9fe47d738f14c5c0931f41.jpg)  
图1交错网格

在正演过程中，交错网格中数值频散和数值各项异性都很小。相对常规网格来说对泊松比的变化不明显，对于任意泊松比变化的模型正演结果都很稳定，更适合模拟固体、流体交界面的传播。同时交错网格采用具有高精度的差分算子，使得单位波场内网格点数减少，计算速度提升。

# 2 “神威·太湖之光"超级计算机

# 2.1申威26010异构众核处理器

“神威·太湖之光"超级计算机，共搭载四万多个计算阵列集群和分布式共享存储相结合的申威26010国产异构众核处理器，与中央控制系统组成神威异构众核体系结构。单个处理器架构如图2所示，单处理器上集成四个运算核组共计260个计算核心，每个核组由1个主核(控制核心)与从核阵列组成，从核阵列搭载 $6 4 ( 8 { \times } 8 )$ 个从核(计算核心)。从核阵列共享16kb的二级指令cache，每个从核独自占有64kb的LDM。从核阵列可通过片传输网络直接访问处理器上的所有主存空间，从核之间可通过阵列之间行通信总线与列通信总线进行LDM数据传输。

![](images/2e90997b7aae5770d7426ec6e27c9120bc15f690a9fb7a4ba59d5be8b3a58024.jpg)  
Fig.1Finite difference staggered grid   
图2申威26010芯片架构  
Fig.2SW26010 many-core processor architecture diagram

# 2.2申威26010并行方法

申威 26010 异构众核体系为用户提供 MPI+SunwayOpenACC与MPI+SunwayAthread两套并行加速工具。根据并行加速工具可以实现以下四种异构加速并行编程模型，分别是：主从加速并行，将计算段通过线程库加载到计算核心，在从核计算过程中主核处于等待阶段，通过计算后将计算结果返回到主核；主从协同并行，主核作为一个计算核心，协同从核一起完成计算任务；主从异步并行，在从核计算的同时，主核完成部分计算、通信与IO操作，实现通信与计算的相互隐藏，优化效果明显；主从动态并行，从核不固定的从主核接收计算任务达到并行的目的。在实际应用中根据不同的需求确定所需的编程模型策略。如图3所示。

![](images/f402986bd8c518169841b3128648c2a353d82668f6c52a457ccb0c788c1cb862.jpg)  
图3线程并行方法 Fig.3Thread method

# 3 三维地震声波正演模拟多级并行算法优化策略

# 3.1多级并行策略

三维地震声波正演主要包括四个模块：模型读取、PML吸收边界、应力求解与速度求解。在求解过程中主要应用有限差分法求解问题，本文主要针对有限差分计算过程中数据依赖关系、计算过程复杂等问题，设计多级并行数据高效衔接方法，实现应力速度计算模块的多级异构并行优化。如表1为串行程序在均匀介质中迭代400次的运行时间与时间占比，应力与速度的求解为核心计算模块中最耗时的模块。因此，由主核负责数据处理(模型读取、PML吸收边界等)，将核心计算任务(计算速度、计算应力)分配到计算核心中。

表1各模块时间占用比  
Tab.1Module time occupancy ratio   

<html><body><table><tr><td>模块名称</td><td>时间/s</td><td>占比</td></tr><tr><td>计算速度</td><td>2587.105</td><td>63.83%</td></tr><tr><td>计算应力</td><td>1442.196</td><td>35.58%</td></tr><tr><td>其他</td><td>24.087</td><td>0.59%</td></tr><tr><td>总计</td><td>4053.388</td><td>100%</td></tr></table></body></html>

根据三维地震声波传导算法特性，实现基于“神威·太湖之光"超级计算机的有限差分交错网格法的多级异构并行。在计算过程中，由于相邻计算单元数据相互影响，若数据划分不恰当会导致大量的通信，从而造成整体计算效率下降。本文结合神威系统架构设计出如图4所示的多级并行数据划分方案：一级并行阶段将数据划分到申威26010处理器核组中；二级并行将核心计算任务具体划分到64个计算从核中。

![](images/e15d650476c98a03dd0235bff1b3299a27c05c6700728cf0f6a262a426b10f98.jpg)  
图4并行划分策略

如图4所示，为计算任务划分到硬件系统中的对应图，为提升通信效率，保证硬件存储设备中数据的连续性，又必须有应对超大规模的能力，因此映射出数据任务与硬件系统的关系。

# 3.2一级并行策略

一级并行通过MPI信息接口通信协议，实现数据在申威26010 处理器中数据之间的通信。使用MPI并行优化过程中，主要针对进程之间通信耗时过大问题，提出了如下解决方案：通信耗时过大是由于传统方法采用数据块划分方式，导致6个面数据间的多次通信，如图5所示。并且，X,Y四个面通信过程中数据通信存在不连续现象，导致通信次数呈几何倍数增长。虽然通过数据打包的方式可以有效降低通信次数，但在打包与解包过程中依旧存在时间损耗问题，且最少需要六个面(上下左右前后)的六次通信。

为减少通信次数，数据一级并行划分采用按Z轴切割划分方法。数据存储中Z轴方向为最慢轴方向，按Z轴切割后的数据均为连续块，不需要打包等耗时操作。采用此种类型的并行策略通信次数有效降低，程序整体运行速度得到有效提升，且为二级并行划分策略奠定了基础。

![](images/247fdf2940c4fcfde344feb6e9b406148794dfa7c45dd590ca8162dd37675e2f.jpg)  
Fig.4Parallel partition method   
图5进程划分策略  
Fig.5Process partitioning method

# 3.3二级并行策略

二级并行划分将计算任务分发到计算核心阵列中，通过64个计算核心加快问题的求解速度。计算核心虽然可以直接从主存中读取数据，但由于神威系统带宽的限制，且在多个计算核心同时读取数据时带宽利用率不高。直接从主存读取数据需要花费数百个时钟周期，无法发挥系统强大的计算能力。为了加快数据访问速度，申威26010处理器为每个从核配备了可编程的64K局部数据高速缓存区(LDM)，从LDM单次读取数据仅需数个时钟周期。

数据从主存转移到LDM需要使用到神威线程工具。SunwayAthread神威线程库支持GLD/GST直接离散访问主存与DMA批量数据访问主存，可将数据加载到LDM中。通过SunwayAthread线程库用户可通过更多的编程操作实现对DMA通信进行控制。所以，使用好仅有的64KLDM空间是提升二级并行性能的关键。通过降低访存开销开销，来解决stencil 问题。

由于LDM容量受限，每个从核单次更新的数据块大小被限制，通过线程之间的数据划分，减少计算冗余比与访问主存次数，计算性能可有效提升。一级并行策略中数据按照Z 轴划分，将二级并行划分近似为 $X - Y$ 面的二维问题进行分析。在二维二阶有限差计算体系下本文拟定了如图6所示的两种分配方案。

图6中(a)(b)两种划分方案，(a)有效发挥了DMA带宽优势，却占用较大的LDM空间；(b)减少了LDM空间的占用，却需要多次的通信操作。拟对16384k的double 数据进行二阶有限差分计算，测试不同划分方案对性能的影响。为避免计算对性能结果的影响，测试中仅作LDM与主存的通信操作。性能结果如表2所示，虽减少通信次数可有效提升运行效率，但当其数据量超过LDM大小(64k)，启动一次从核无法完成计算。由测试结果可得在LDM所能承受的前提下，减少通信次数提升计算效率。根据这一特性本文设计了一种通过保证LDM承受范围，带宽占用率最高的方案，将(a)(b)两种划分策略的优点进行有效结合，设计出单次计算 $4 \times 7 \times$ 131的数据块的方案，使程序正演模拟速度最快。

$\scriptstyle \operatorname { F o r } ( \mathrm { i } = 0 ; \mathrm { i } < 7 ; \mathrm { i } + + )$ For(i=0;i<5;i++) Athread_get(length(7)); 123456789 Athread_get(length(13)); computing(); 12 computingO; Athread_put(length(9)); For(i=0;i<3;i++) Athread_put(length(9)); (a)通信次数优先 (b)空间占用优先

Tab.2Communication experiment results   

<html><body><table><tr><td>读取数据大小</td><td>68×36</td><td>36×68</td><td>20×132</td><td>12×260</td></tr><tr><td>返回数据大小</td><td>64×32</td><td>32×64</td><td>16×128</td><td>8×256</td></tr><tr><td>时间/s</td><td>1.867</td><td>1.166</td><td>0.858</td><td>N/A</td></tr></table></body></html>

上述优化方案仅停留在二维层面上。当数据扩大至三维，数据量几何倍的增长，在LDM大小有限的情况下高位面冗余数据增加，低位面的大小相对需要减小，导致每次可计算出的结果减少。为解决上述问题，本文设计出了一种2.5D流水线方案。如图7所示，固定LDM中Z轴的大小，在二阶下，第一次读入5层的数据，可计算完出第3层数据，再读第6层数据放入已使用完毕的第1层数据容器中，计算得到第4层冗余数据。此种计算方案仅在计算第一层数据时读入4倍的冗余数据，在之后的迭代过程中读取数据量与计算数据量达到1:1。此方案增加了LDM空间的利用率，有效的提高了模型的正演速度。

![](images/cde57982b23c42c489285b3d0e51fa19e911230fbecfdb3b254f271f65cbb7c4.jpg)  
Fig.6MA communication policy表2线程划分通信测试结果  
图72.5D流水线策略  
Fig.72.5-D Pipeline method

同时，2.5D更方便实现通信与计算的相互掩盖，对于异构众核加速计算程序，通信计算相互掩盖是性能提升的关键策略，具体如图8所示。

# 4算例验证与性能测试结果

# 4.1逆掩推覆体构造模型

为验证方法有效性，本文采如图9所示的逆掩推覆体构造模型速度模型验证程序的适用性，该模型是以低角度为主的一个滑动平面，沿该面发生了数公里以上的平面断层，断层面的倾斜角度较小，是低角度的逆断层，可有效判定实验结果的稳定性。

![](images/b84855fe66a8d87b8fe2fee9086938680c027c6d6d57dd0dbb907d89edd870ef.jpg)  
图8计算通信相互掩盖策略  
Fig.8Asynchronous communication

0 K   
50   
100   
150   
200 900   
900800 700800   
700 600 300400500 500 400300 200 200 100 0 0 100

掩推覆体构造模型单炮模拟记录结果如图10所示，分别在(150，450，0)、(450，450，0)、(750，450，0)三个空间点做波场记录，得到了声波在复杂地质模型传播过程中的反射波。由图10可知在浅层(1.0s前)3个点记录的数据差异性较小，在模拟记录中层 $( 1 . 0 \mathrm { s } { \sim } 2 . 0 \mathrm { s } )$ 可明显看出在(450，450，0)处有复杂的反射波，对比模型在该处存在断层。在深层(2s后)由于断层导致(750，450，0)处反射波提前被检波器记录。由三处记录与分析模型对比可以确定正演结果没有出现较大的精度误差，模拟结果具有较高的可信度。

![](images/6104efea8053200ff389dc1b7b0a2f2b289527506c6d2c0ab8502651056ed0b8.jpg)  
图6DMA通信策略  
图9逆掩推覆体构造模型Fig.9Overthrust  
图10掩推覆体构造模型正演模拟记录  
Fig.10 Overthrust experiment

# 4.2多级异构并行性能测试

基于“神威·太湖之光"超级计算机系统，对网格大小为$2 5 6 \times 2 5 6 \times 2 5 6$ ，采样间隔为0.001s，震源为网格中心的均匀介质模型，进行400次迭代测试程序并行性能。

一级并行测试采用128个进程；二级并行测试采用1个申威26010处理器，64个从核对计算部分加速；多级异构并行使用128个申威处理器并启动计算核心阵列加速。通过多级并行优化完成400次迭代运行，在不考虑I/O影响的前提下，仅计算从1442.296s(应力)和2587.105s(速度)提升到1.363s(应力)和1.858s(速度)的部分数据，如图11所示。

与2014年何香在“神威·太湖之光”超级计算机上做的三维声波方程多级并行[20]，以及龙桂华基于GPU(Tesla1060)三维交错网格声波正演模拟[21]相比较，性能对比如表3所示。何香采用MPI+Athread+向量化的多级并行方式，进行32炮测试；龙桂华通过GPU实现了正演模拟加速。在一级并行实验过程中，本文优化方案由于减少了通信面，在一级并行加速比上与何香的优化方案相比性能提升 $200 \%$ 。在多级并行上虽然本文少了一级向量化并行，但是通过2.5D流水线与通信计算相互掩盖的优化策略，本文测试结果在加速比上也优于其他策略。

![](images/23d9c75800755ead7126c438fc6aae7c4c0c0f26cde6b758de3ef3fc8d91f5ce.jpg)  
图11并行性能

Fig.11Performance experiment 表3性能比较   
Tab.3Performance comparison   

<html><body><table><tr><td>测试项目</td><td>神威(本文)</td><td>神威 (何香)</td><td>GPU(Tesla1060)</td></tr><tr><td>串行/s</td><td>4053.388</td><td>9993.416</td><td>4352.69</td></tr><tr><td>一级并行/s</td><td>65.500</td><td>327.975</td><td></td></tr><tr><td>多级并行/s</td><td>27.308</td><td>92.579</td><td>54.82</td></tr><tr><td>一级并行加速比</td><td>61.88</td><td>30.47</td><td></td></tr><tr><td>多级并行加速比</td><td>148.43</td><td>107.94</td><td>79</td></tr></table></body></html>

# 4.3扩展性测试

在并行优化中，可扩展性是高性能计算机所追求的一个重要指标[22,23]。本文对均匀介质模型，网格大小为 $2 5 6 \times 2 5 6$ $\times 2 5 6$ ，采样间隔为0.001s震源为网格中心算例，使用 $1 \sim$ 256个申威26010处理器测试多级异构程序的强扩展性。在64 进程时计算开销、I/O通信开销等开始趋于稳定，应力计算效率此时达到最高，如图12所示。

![](images/e0c35b82c5f6409dfcf3ff832cac3292d2350de1d0b19919eb3ac4f25e1191bf.jpg)  
图12强扩展性能

弱扩展性测试保持每32进程计算256网格数据，使用$3 2 { \sim } 4 0 9 6$ 个进程进行测试，测试结果如图13所示，当进程值大于512后的一段进程数目，随着进程增加计算开销与通信开销比呈现下降趋势，并行效率降低。但是在2048进程时计算开销与通信开销比重新达到最优值，整体计算性能达到最优。

![](images/c2567e8a6d162a7d6a784dd003542df6729919ee733c69295db30526e6edaca1.jpg)  
Fig.12Strong expandability experiment   
图13弱扩展性能  
Fig.13Weak expandability experiment

# 5 结束语

本文基于“神威·太湖之光”超级计算机系统中的国产异构众核处理器架构实现了三维地震声波有限差分高阶交错网格方程的正演以及多级异构并行优化。实验以实际情形为研究基础，在众核处理器上进行优化，通过逆掩推覆体构造模型进行稳定性测试，且计算效率有有效提升。文中采用MPI+SunwayAthread，针对申威26010芯片硬件架构特征，引入数据重新划分的策略，通过减少进程间的通信的并行方案，有效提升一级并行效率。二级并行上通过DMA通信、2.5D流水线、计算通信相互掩盖策略，有效缓解了从核访问主存带宽瓶颈，提高了LDM空间的利用率，使得多级并行策略得以实现。确保算法在大规模并行下依然保持良好的扩展效率与并行性能。本文研究也验证了国产自主研发芯片在特定领域具有较高的实用性。

此外，本文所提出的理方法同样适用于以有限差分为数值求解方法的弹性波模拟、逆时偏移以及全波反演等stencil问题计算中，为地震算法在神威上的移植提供了基础。

# 参考文献：

[1]Alterman Z,Karal Jr F C.Propagation of elastic waves in layered media by finite difference methods [J].Bulletin of the Seismological Society of America,1968,58(1): 367-398.   
[2]Madariaga R.Dynamics of an expanding circular fault [J].Bull. seism. soc.am,1976,66(3):639-666.   
[3]Virieux J. SH-wave propagation in heterogeneous media: Velocity-stress finite-difference method [J]. Geophysics,1984,49 (11):1933-1942.   
[4]Virieux J.P-SV wave propagation in heterogeneous media: Velocitystress finite-difference method [J]. Geophysics,1986,51 (4): 889-901.   
[5]Yang Pengliang,Gao Jinghuai,Wang Baoli.RTM using effective boundary saving:A staggered grid GPU implementation [J].Computers & Geosciences,2014,68: 64-72.   
[6] 李斌，温明明，牟泽霖．用于声波正演模拟的时空域高精度交错网 格有限差分方法[J].CT理论与应用研究，2017,26(3):259-266.(Li Bin,Wen MingMing,Mou Zelin A high precision staggered mesh finite difference method for acoustic forward modeling in space-time domain [J].Computerized Tomography Theory and Application,2017,26 (3): 259-266.)   
[7]谢海峰，王占刚，杜群乐，等．基于GPU 的三维交错网格有限差分 声波正演模拟[C]// 中国地球科学联合学术年会.2014.(Xie Haifeng, Wang Zhangang,Du Qunle,et al. Finite diference acoustic forward modeling based on gpu-based 3d staggered grid [C]//Annual meeting of Chinese geoscience union.2014)   
[8]Song Peng,Xie Chuang,Li Jinshan,et al. The 3D Modeling of Acoustic Wave Equation Based on MPI+OpenMP [J].Periodical of Ocean University of China,2015,46 (9): 97-102.   
[9]Komatitsch D,Erlebacher G,GDdeke D,et al.High-order finite-element seismic wave propagation modeling with MPI on a large GPU cluster [J]. Journal of Computational Physics,2010,229 (20): 7692-7714.   
[10] Yang Xuejun,Liao Xiangke,Xu Weixiao,et al. Th-1:China's first petaflop supercomputer [J].Frontiers of Computer Science in China, 2010,4 (4): 445-455.   
[11] Xue Wei,Yang Chao,Fu Haohuan，et al.Ultra-scalable CPU-MIC acceleration of mesoscale atmospheric modeling on Tianhe-2 [J]. IEEE Transactions on Computers,2014,64 (8): 2382-2393.   
[12] Fu Huan,Liao Junfeng,Yang Jinzhe,et al. The Sunway TaihuLight supercomputer: system and applications [J]. Science China Information Sciences,2016,59(7):072001. [13] Qiao Fangli,Wei Zhao,Yin Xunqiang,etal.Ahighly effective global surface wave numerical simulation with ultra-high resolution [C]// International Conference for High Performance Computing.2O16,1:46-   
56. [14]Fu Haohuan,Liao Junfeng,DingNan,et al.Redesigning CAM-SE for peta-scale climate modeling performance and ultra-high resolution on Sunway TaihuLight[C]//Proceedings of the International Conference for High Performance Computing,Networking,Storage and Analysis.ACM,   
2017: 1. [15] Fu Haohuan，Yin Wanwang,Yang Guangwen，et al.18.9-Pflops nonlinear earthquake simulation on Sunway TaihuLight: enabling depiction of 18-Hz and 8-meter scenarios [C]// Proceedings of the International Conference for High Performance Computing,Networking, Storage and Analysis.ACM,2017:2 [16] Xue Wei,Yang Chao,Fu Haohuan,et al.Enabling and Scaling a Global Shallow-Water Atmospheric Model on Tianhe-2 [P].Parallel and Distributed Processing Symposium,2014 IEEE 28th International,2014   
745-754. [17] C.A.Zelt †,Smith R B.Seismic traveltime inversion for 2-D crustal velocity structure [J]. Geophysical Journal International, 201o,108(1):   
16-34. [18]谢圣朝，谢久安，唐铁生．高阶精度交错网格有限差分法正演模拟 及完全匹配层吸收边界[J]．中国石油和化工标准与质量，2014(10): 263-263．(Xie Chaosheng，Xie Jiuan，Tang Tiesheng.High order precision staggered mesh finite difference method for forward modeling and fully matched layer absorption boundary [J].China Petroleum and Chemical Standard and Quality,2014 (10):263-263.)   
[19]何香，周明忠，刘鑫．三维声波方程正演多级异构并行算法设计与 实现[J]．计算机应用与软件，2014(01):270-273.(He Xiang,Zhou Mingzhong，Liu Xin.Design and implementation of multilevel heterogeneous parallel algorithm for three dimensional acoustic equation [J]. Computer Applications and Software,2014 (01):270-273.)   
[20]龙桂华，赵宇波，李小凡，等．三维交错网格有限差分地震波模拟的 GPU集群实现[J].地球物理学进展,2011(06):60-71.(LongGuihua, Zhao Yubo,Li Xiaofan,et al GPU cluster implementation of3d staggered grid finite difference seismic wave simulation [J]．Progressin Geophysics,2011 (06): 60-71)   
[21] Zheng Ziming,Lan Zhiling.Reliability-aware scalability models for high performance computing[C]//IEEE International Conference on Cluster Computing&Workshops.2009.   
[22] Palyart M,Lugato D,Ober I,et al.Improving Scalability and Maintenance of Software for High-Performance Scientific Computig by Combining MDE and Frameworks [M]// Model Driven Engineering Languages and Systems.2011.