# 虚拟化云计算数据中心资源节能调度算法研究

宁士勇

(哈尔滨商业大学计算机与信息工程学院，哈尔滨 150028)

摘要：针对当前云计算数据中心资源调度过程耗时长、能耗高、数据传输准确性较低的问题，提出基于VR沉浸式的虚拟化云计算数据中心资源节能调度算法。构建云计算数据中心资源采样模型，结合虚拟现实(Virtual Reality，VR)互动装置输出、转换、调度中心资源，提取中心资源的关联规则特征量，采用嵌入式模糊聚类融合分析方法三维重构中心资源，建立虚拟化云计算数据中心资源的信息融合中心，采用决策相关性分析方法，结合差异化融合特征量实现对数据中心资源调度，实现虚拟化云计算数据中心资源实时节能调度。仿真结果表明，采用该方法进行虚拟化云计算数据中心资源节能调度的数据传输准确性较高，时间开销较短，能耗较低，在中心资源调度中具有很好的应用价值。

关键词：虚拟化；云计算；数据中心资源；VR沉浸式中图分类号：TP39 doi:10.19734/j.issn.1001-3695.2020.02.0037

Research on resource energy saving scheduling algorithm for virtual cloud computing data center

Ning Shiyong (School ofcomputer& information engineering,Harbin University ofCommerce,Harbin 150028,China)

Abstract: Inordertoadressthecurrent time-consuming processofcloud computingdata centerresource scheduling,high energy consumption,and lowdata transmissionaccuracy,we proposeda VR immersive virtualcloud computing data center resource energy-saving scheduling algorithm. Construction of cloud computing data centers resource sampling model, combindwith VR(Virtual Reality)interactivedeviceoutputs,transformed,anddispatchedcentralresources,extractedthe characteristicquantitiesoftheassociationrulesofthecentralresources,ndused embeddedfuzzyclustering fusionanalysis methods toreconstructthecentralresources three-dimensionallytoestablish virtual cloud computingdatacenterresources. Theinformation fusion centers toadoptadecision corelationanalysis methodand combines differentiated fusion feature quantities torealizedata center resourcescheduling,andrealizes real-time energy-saving scheduling for virtualized cloud computing datacenterresources.The experimentalresultsshowthatthedatatransmissonaccuracyof theproposedalgorithm is high,the timecostis shortandtheenergyconsumptionislow,soithasagoodapplicationvalue intheresoucescheduling of virtual cloud computing data center.

Key words: virtualization; cloud computing; data center resources;vr immersion

# 0 引言

云计算数据来自不同的传感器、控制器及计算终端，这些设备之间没有固定的体系规划，如何实现数据中心资源调度成为云计算服务必须解决的问题。VR技术是指利用计算机及最新传感器技术模拟出一个三维虚拟空间，使用户具有身临其境的沉浸感，创造了一种崭新的人机交互手段[1]。目前VR技术被广泛应用于多个研究领域，如医学领域、机械领域等[2]。为提高中心资源调度能力，需要在虚拟化视景仿真模型下进行中心资源调度，建立虚拟化云计算数据中心资源节能调度的三维数据重构模型，相关的虚拟化云计算数据中心资源节能调度算法研究受到人们的极大关注。

目前已有相关学者对虚拟化云计算数据中心资源节能调度作出了研究。文献[3]提出了一种基于多尺度量子谐振子算法(MQHOA)的任务调度算法，运用高斯采样特性将各调度方案比作采样位置查找部分最优解，并确定该算法能否处于能量值平稳的形态，若稳定，则能量值降低并替换最差调度方案，在尺度降低的过程中，该算法由整体查找转变为部分查找，重复反馈该过程多次后，算法结束得出最优解。该算法在调度过程中，可以快速收敛，减少总任务完成时间，但该方法的调度能耗较高。文献[4]提出一种云数据中心资源利用率均衡的虚拟机调度算法，采用自适应粒子群优化算法，构建虚拟机调度模型，将调度问题概括为多维向量，其中每一维向量表示一种类别的资源，从而完成云数据中心资源虚拟机调度，该方法可以平衡资源利用率，降低数据传输能耗，但该方法对资源数据传输准确性较低，调度实时性不好。文献[5]中提出了云计算数据中心的节能资源配置，采用云计算数据中虚拟机的不同能源感知资源分配选择算法，设计正在进行或已实施的针对云环境的能源意识资源分配技术。该方法能够降低硬件、软件和维护的运营成本，但大型数据中心的数量增加，消耗了大量的电力，对环境有负面影响。文献[6]提出基于遗传算法的云计算中任务调度双目标决策支持系统，采用遗传方法构建云计算中的任务计划问题模型，根据云计算中的任务计划，运行一组任务所需的时间，设计核心决策支持系统，该方法能够降低处理成本，调度过程耗时短，但数据传输准确性较低。文献[7]中提出云计算数据中心中的代理的容错感知调度方法，通过群集记录事件的位置，并设置CPU、内存和带宽的范围，采用故障跟踪方法检查违规并将其请求数据与群集数据进行比较，由此完成调度请求，该方法减少了执行时间并提高了性能，但群集数据传输的准确性较低。文献[8]提出了地理分布混合用途建筑物的联合能源调度，采用建筑物中的数据中心和非数据中心负载之间的协调方法，通过耦合布置在建筑物中的边缘数据中心来调度工作负载，以在整个时间范围内调度整个系统。该方法实现最大程度地因减少负载而导致的系统成本，解决了资源调度过程耗时长的问题。文献[9]提出了一种云计算数据的动态负载平衡调度(DLBS)方法，依据DLBS问题，构建OpenFlow网络模型，开发一套有效的启发式调度算法，以平衡每个时隙的数据流，该方法平衡调度的数据传输准确性较高，但该方法调度耗时长，实时性不好。

针对上述问题，本文提出基于VR沉浸式的虚拟化云计算数据中心资源节能调度算法，构建中心资源调度数据的模型，建立虚拟化云计算数据中心资源的信息融合中心，采用多尺度特征分解的方法实现虚拟化云计算数据中心资源的特征分解和统计分析，结合统计特征量实现对数据中心资源调度，根据调度结果指导中心资源调度，提高承载中心资源实时调度能力。仿真测试分析，采用所提方法进行虚拟化云计算数据中心资源节能调度的数据传输准确性较高，资源调度过程耗时短，节能性较好。

# 1中心资源调度数据采样和特征分析

# 1.1云计算中心资源数据采样模型

为了实现虚拟化云计算数据中心资源节能调度，需要首先构建云计算中心资源数据采样模型，选择 $q$ 为最小嵌入维数、 $\tau$ 为最佳时延，对云计算中心资源数据特征重构，建立云计算中心资源数据的相空间重构模型，采用链路随机分配模型进行虚拟化云计算数据中心资源的实体数据集分析，结合实时传输调度的方法[10]，对云计算中心资源数据进行实时调度，得到中心资源调度的虚拟资源的信息流模型为

$$
P = x ( t _ { 0 } + q \Delta t ) - h [ \tau ( t _ { 0 } + q \Delta t ) ] + \omega _ { n }
$$

其中， $x$ 为中心资源重构数据， $t _ { 0 }$ 、 $\Delta t$ 分别为重构初始时间及总耗时， $\textbf { \textit { h } }$ 为虚拟化云计算数据中心资源流的多元数量值函数， $\omega _ { n }$ 为自适应加权系数。选取实时采集的方法调度虚拟化云计算数据中心资源，以采集的云计算数据中心资源信息流作为初始样本序列，采用VR虚拟现实互动装置，将中心资源调度的虚拟资源的信息流模型输入到主机系统中运行，内置传感器在VR虚拟现实互动装置中匹配中心资源信息流，并输入中心资源多元数量值函数，将其转换为中心资源信息流重构数据，结合实时资源信息分析的方法，进行云计算数据中心资源信息流重构，求得虚拟云计算数据中心资源信息流的有限数据集为

$$
\pmb { X } = \{ x _ { 1 } , x _ { 2 } , . . . x _ { n } \}
$$

采用空间动作捕捉的方法，得到云计算数据中心中的资源信息流传递特征量分布为 $x _ { n } \to x _ { n + 1 }$ ，在高维演化模型中，云计算数据中心资源信息流的高维映射向量为 $N$ ，采用基于VR沉浸式虚拟现实技术，得到数据中心资源信息传输时间为 $T$ ，其峰值参量模型为

$$
Y = x ( T + K ) \sum _ { i = 1 } ^ { n } h _ { i } ( N - 1 ) ^ { \Gamma }
$$

其中， $\kappa$ 为虚拟化云计算数据中心资源的实时信息分布的正交特征向量， $\Gamma$ 为虚拟化云计算数据中心资源的采样时间延迟，由此构建虚拟化云计算数据中心资源采样模型为

$$
C { = } X Y f e ^ { { - } j 2 \pi { \ j } k }
$$

其中： $f$ 为归一化初始频率， $e ^ { - j 2 \pi f k }$ 为虚拟化云计算数据中心资源的实时流量的归一化相关系数。采用非线性特征分解方法进行虚拟化云计算数据中心资源的信息采集和特征重组，进行虚拟化云计算数据中心资源的实时信息采集，以根据上述分析，构建了中心资源调度云计算中心资源数据采样模型，根据采样结果进行云计算中心资源的输出转换调度。

# 1.2云计算中心资源的输出转换调度

结合VR虚拟现实互动装置进行虚拟化云计算数据中心资源的输出转换调度，提取云计算数据中心资源的关联规则特征量，采用时间-频率联合特征分析方法构建虚拟化云计算数据中心资源的输出转换调度模型，得到输出特征量描述为

$$
Q = R \{ a _ { n } ( t ) e ^ { - j 2 \pi f k } s _ { l } ( t - \tau ) e ^ { - j 2 \pi f k } \}
$$

其中， $R$ 为全局匹配函数， $a _ { n } ( t )$ 为第 $n$ 条传输通道上的中心资源调度资源输出信息流， $s _ { l }$ 为频率特征量， $t$ 为调度时间。虚拟化云计算数据中心资源的输出响应可描述为

$$
c ( \tau , t ) = \sum _ { n } a _ { n } ( t ) R ^ { - 2 \pi f _ { c } } \tau _ { n } ( t )
$$

其中， $\tau _ { n } ( t )$ 为第 $n$ 条传输通道上的时延， $f _ { c }$ 为调制频率，采用频谱自适应调度方法，进行虚拟化云计算数据中心资源的谱特征提取，得到特征提取结果为

$$
\int _ { - \infty } ^ { + \infty } W _ { x } ( t , \nu ) d t = \left| \boldsymbol { X } ( \nu ) \right| ^ { 2 }
$$

其中， $X ( \nu )$ 为虚拟化云计算数据中心资源传输的短时窗函数，通过频谱特征结果进行虚拟化云计算数据中心资源的输出转换调度，提高虚拟化云计算数据中心资源节能调度能力[11-12]。

# 2 云计算数据中心资源节能调度算法优化

# 2.1云计算数据中心资源的三维重构

在完成虚拟化云计算数据中心资源输出转换调度的基础上，进一步优化中心资源节能调度算法。采用嵌入式模糊聚类融合分析方法对云计算数据中心资源进行三维重构，得到云计算数据中心资源的匹配滤波调度的迭代公式为

$$
W = \theta _ { 1 } ( k ) - R [ y ( k ) \varphi ^ { * } ( k ) ]
$$

其中， $\theta _ { 1 } ( k )$ 为滤波迭代后得到资源信息， $y ( k )$ 为匹配资源信息， $\varphi ^ { * } ( k )$ 为滤波资源信息，结合实时特征序列分布式调度的方法，进行云计算数据中心资源调度和输出调度，运用频谱自适应调度法对数据中心资源进行谱分析[13-15]，得出虚拟化云计算数据中心资源的输出谱特征量 $E$ ，再采用模糊关联规则调度的方法，虚拟化云计算数据中心资源优化调度，得到资源传输优化调度集为

$$
A ( t ) = E + W \sqrt { a } B ^ { H } ( t )
$$

其中， $\mathbf { \Delta } _ { a }$ 为虚拟化云计算数据中心资源信息的振荡幅值，$B ^ { H } ( t )$ 为模糊关联规则系数。采用经验模态分解方法，得到虚拟化云计算数据中心资源的VR重构输出为

$$
\nu _ { x } ( t ) = \frac { A ( t ) + ( \nu _ { 0 } + 2 \beta t ) } { Y _ { p } ( u ) }
$$

其中， $\nu _ { x } ( t )$ 表示的输出的虚拟化云计算数据中心资源的交叉项， $Y _ { p } ( u )$ 为非高斯色噪声项， $\beta$ 为模态分解系数， $\nu _ { 0 }$ 为虚拟化云计算数据中心资源白噪声项。根据VR重构处理，获得数据中心资源谱特征量，进行虚拟化云计算数据中心资源的实时监控[16-17]。用 $D _ { i }$ 表示虚拟化云计算数据中心资源的关联规则项，根据上述分析，进行虚拟化云计算数据中心资源的优化调度和挖掘，得到虚拟化云计算数据中心资源共享调度的优先级聚类模型为

$$
V = \frac { \nu _ { x } ( t ) } { D _ { i } ^ { + } + D _ { i } ^ { - } }
$$

其中， $D _ { i } ^ { + }$ 表示正关联项， $D _ { i } ^ { - }$ 为负关联项。综上分析，构建虚拟化云计算数据中心资源的自适应融合聚类处理模型，进行虚拟化云计算数据中心资源的节能调度[18-20]。

# 2.2云计算数据中心资源节能调度算法

通过上述分析，采用决策相关性分析方法，结合差异化融合特征量，实现云计算数据中心资源节能调度算法为

输入：根据虚拟化云计算数据中心资源共享调度的优先级聚类模型，使用VR沉浸式表达方法，输入虚拟化云计算

数据中心资源的模糊指标集。

输出：虚拟化云计算数据中心资源。

a）采用决策相关性分析方法，构建虚拟化云计算数据中心资源信息智能化共享的融合模型。

b）使用多元回归分析方法，得到虚拟化云计算数据中心资源智能化共享的计算公式为

$$
U _ { i } \left( t \right) = \exp \Bigl [ \bigl [ z _ { i } \left( t \right) - V \bigr ] ^ { 2 } \Bigr ]
$$

其中， $z _ { i } \left( t \right)$ 为相关性的统计分析特征值，得到虚拟化云计算数据中心资源共享的相似度为

$$
S _ { i } \left( t \right) = \frac { p _ { i } \left( t \right) - s \cdot p _ { i , j } \left( t \right) } { \Delta p ( t ) }
$$

其中： $s$ 为虚拟化云计算数据中心资源相关性系数， $p _ { i , j } ( t )$ 为虚拟化云计算数据中心资源共享的模糊相关性特征分布集，$\Delta p ( t )$ 为虚拟化云计算数据中心资源共享的模糊决策增量值。

c）在[01]范围内进行虚拟化云计算数据中心资源共享的模糊相关性特征分析，得到虚拟化云计算数据中心资源共享的差异化融合特征量：

$$
J _ { m } = \sum _ { i = 1 } ^ { m } S _ { i } \left( t \right) ^ { m } ( d _ { i k } ) ^ { 2 }
$$

其中， $m$ 为虚拟化云计算数据中心资源分布的有限数据集，$( d _ { i k } ) ^ { 2 }$ 为相似度分布映射。

d)由此得出虚拟化云计算数据中心资源的决策性自变量为

$$
( d _ { i k } ) ^ { 2 } = \left\| x _ { k } - J _ { m } \right\| ^ { 2 }
$$

其中， $x _ { k }$ 为虚拟化云计算中心资源数据截距。

如果不满足确定性关系，令 $s = s + 1$ ，转回步骤(1)，直至满足函数关系。

e)结束

综上分析，实现虚拟化云计算数据中心资源实时节能调度。

# 3 实验分析

为验证所提方法在虚拟化云计算数据中心资源节能调度中的应用性能，进行仿真实验。实验选择CloudSim云仿真平台，结合Visual $\mathrm { C } { + } { + }$ 仿真工具，并将调度模型应用在中心资源调度和实操模拟中，结合VR虚拟现实技术进行虚拟化云计算数据中心资源节能调度。

# 3.1实验环境和数据集

实验采用Redis 数据集(https://github.com/microsoftarchive/redis/releases)内的数据，在CloudSim平台中，仿真设置 500 台计算机的云计算中心资源数据共 200G，6000byte。对虚拟化云计算数据中心资源的采样时间长度为120s，频率为 $1 2 0 \mathrm { K H z }$ ，载波频率为 $2 4 \mathrm { K H z }$ ，在400-600采样点之间设定一个 $2 5 0 \mathrm { H z }$ 的频率分量进行载波调制，得出虚拟化云计算数据中心资源信息采样结果如图1所示。

![](images/0bb88647cd091e9b996e4a3c6b44aafc0fc21d69b5dbd43c472a3e7fbe1d8d7f.jpg)  
图1虚拟化云计算数据中心资源信息采样结果Fig.1Sampling results of resource information in virtualized cloudcomputing data center

# 3.2实验指标

实验指标为

a)数据传输误码率(BER)：在虚拟化云计算数据中心资源调度数据传输中，误码率是衡量数据传输准确性的指标，其数据传输误码率的计算公式为

$$
W = \frac { Q _ { C } } { Q _ { z } } \times 1 0 0 \%
$$

其中， $\scriptstyle Q _ { c }$ 表示虚拟化云计算数据中心资源调度数据传输错误的数据量， $Q _ { z }$ 表示虚拟化云计算中心资源调度数据总量。

b） 信噪比(SNR)：是有用信号功率与噪声功率的比，其计算公式为

$$
\mathrm { S N R } = { \frac { P _ { \mathrm { s i g n a l } } } { P _ { \mathrm { n o i s e } } } } = \left( { \frac { A _ { \mathrm { s i g n a l } } } { A _ { \mathrm { n o i s e } } } } \right) ^ { 2 }
$$

其中， $P _ { \mathrm { s i g n a l } }$ 表示信号功率， $P _ { \mathrm { n o i s e } }$ 表示噪声功率， $A _ { \mathrm { s i g n a l } }$ 表示信号幅度， $A _ { \mathrm { n o i s e } }$ 表示噪声幅度。

c）资源调度总功率：主要指资源调度后数据负载长度增加的能耗和数据空负载运行时的能耗之和，总功率越小，说明算法的能耗越低。其计算公式为

$$
W _ { z } = E _ { F } + E _ { K F }
$$

其中， $E _ { F }$ 表示资源调度后数据负载长度增加的能耗， $E _ { \kappa F }$ 表示数据空负载运行时的能耗。

d）资源调度时间：以资源调度耗时为指标，将所提方法与文献[4]、文献[5]、文献[6]进行对比，验证所提方法的性能。

# 3.3实验结果

根据虚拟化云计算数据中心资源信息采样结果获取的资源数据，以数据传输误码率为测试指标，测试所提方法的对云计算数据中心资源调度的数据传输准确性。分别采用文献[4]、文献[5]、文献[6]方法及本文所提方法进行虚拟化云计算数据中心资源节能调度，得到调度后的数据传输误码率对比结果如图2所示。

![](images/1b7aed2e70f25b40a5af2e8f5c67c73f8270b805399cfd185f20d5f5f2b9f8c2.jpg)  
图2虚拟化云计算数据中心资源调度数据误码率Fig.2Bit error rate of resource scheduling data invirtualized cloud computing data center

根据图2得知，采用文献[4]方法进行虚拟化云计算数据中心资源调度后，数据传输误码率平均为10-2.5，文献[5]方法的数据传输误码率平均为10-2.2，文献[6]方法的数据误码率平均为10-2.4，而采用基于VR沉浸式虚拟现实技术进行云计算数据中心资源节能调度后，数据误码率为10-4.5，远远小于对比方法。这说明所提方法的数据传输准确性较高。

信噪比(SNR)：是有用信号功率与噪声功率的比，将上文计算式(23)输入到仿真软件中，在相同单位时间下，求取文献[4]、文献[5]、文献[6]方法及所提方法进行虚拟化云计算数据中心资源调度数据时的信噪比，结果如图3所示。

根据图3可知，在数据负载长度为2000byte 时，采用所提方法的资源调度数据信噪比为43dB，文献[4]方法的资源调度数据信噪比为14dB，文献[5]方法的资源调度数据信噪比为26dB，文献[6]方法的资源调度数据信噪比为23dB；在数据负载长度为4000byte时，采用所提方法的资源调度数据信噪比为46dB，文献[4]方法的资源调度数据信噪比为19dB，文献[5]方法的资源调度数据信噪比为30dB，文献[6]方法的资源调度数据信噪比为26dB；在数据负载长度为6000byte时，采用所提方法的资源调度数据信噪比为48dB，文献[4]方法的资源调度数据信噪比为21dB，文献[5]方法的资源调度数据信噪比为33dB，文献[6]方法的资源调度数据信噪比为30dB，由此可见，采用所提方法调度数据的信噪比最大，受到噪声的干扰最小。

![](images/944243a3807ef2b5f1a06ebd7a7a95ec32b8fc2deac54ada6e40167893ac3c7e.jpg)  
图3虚拟化云计算数据中心资源调度数据信噪比Fig.3SNR of virtualized cloud computing data centerresource scheduling data

为进一步验证调度方法的节能效果，测试3种方法的的输出网络效能，得到结果如图4所示。

![](images/aed1a3569abba6c23ef02a88c01c9d39c16440af311164a198a9a4e57d2cfbd7.jpg)  
图4虚拟化云计算数据中心资源调度的能耗测试 Fig.4Energy consumption test of resource scheduling in virtualized cloud computing data center

分析图4得知，采用文献[4]方法进行虚拟化云计算数据中心资源调度总功率为 $6 9 0 0 \mathrm { K W }$ ，文献[5]方法进行虚拟化云计算数据中心资源调度总功率为 $7 1 0 0 \mathrm { K W }$ ，文献[6]方法进行虚拟化云计算数据中心资源调度总功率为 $6 0 0 0 \mathrm { K W }$ ，而采用所提方法进行虚拟化云计算数据中心资源调度总功率为2300KW，由此可见，所提方法进行虚拟化云计算数据中心资源调度总功率最小，说明所提方法的能耗较低，能够实现中心资源的节能调度。可以将该算法应用在中心资源调度中，提高资源调度能力。

分析图5可知，在数据负载长度为2000byte时，采用所提方法的资源调度过程耗时为14s，文献[4]方法的资源调度过程耗时为27s，文献[5]方法的资源调度过程耗时为20s，文献[6方法的资源调度过程耗时为24s；在数据负载长度为4000byte 时，采用所提方法的资源调度过程耗时为15s，文献[4]方法的资源调度过程耗时为40s，文献[5]方法的资源调度过程耗时为31s，文献[6]方法的资源调度过程耗时为35s;

在数据负载长度为6000byte时，采用所提方法的资源调度过程耗时为18s，文献[4]方法的资源调度过程耗时为48s，文献[5]方法的资源调度过程耗时为42s，文献[6]方法的资源调度过程耗时为45s；传统方法在实现资源调度的过程中，由于受到噪声的干扰，不能准确地识别出数据之间的关联规则，当算法执行指令受到阻碍时，算法会自动返回数据采集模块重新计算数据之间关联规则，反复计算直到执行下一步时，从而严重的增加了调度的耗时，所提方法结合VR(virtualreality)虚拟现实互动装置输出、转换、调度中心资源，能准确的完成中心资源的关联规则特征量的提取，由此可见，采用所提方法调度耗时最短，达到了虚拟化云计算数据中心资源节能调度的目的。

![](images/563055719b23e587c71c922d9edb5bc05215587bfcf3d12aedf26223531597d0.jpg)  
图5虚拟化云计算数据中心资源调度耗时测试 Fig.5Time-consuming test of resource scheduling in virtualized cloud computing data center

# 4 结束语

为提升云计算数据中心资源调度过程耗时长、能耗高、数据传输准确性较低的问题，提出基于VR沉浸式虚拟现实技术进行虚拟化云计算数据中心资源节能调度设计，通过构建云计算数据中心资源采样模型，结合VR虚拟现实互动装置进行虚拟化云计算数据中心资源的输出转换调度，采用嵌入式模糊聚类融合分析方法三维重构中心资源，利用决策相关性分析方法，结合差异化融合特征量实现对数据中心资源调度，实现虚拟化云计算数据中心资源实时节能调度。分析仿真实验得知，采用所提方法进行虚拟化云计算数据中心资源节能调度的数据传输准确性较高，资源调度过程耗时短，节能性较好，在中心资源调度中具有很好的应用价值，但该研究对于算法的性能较为局限，仅可以用于模拟环境中，算法应用于真实环境中的效果有待研究。

# 参考文献：

[1]周成，孔超，居里锴，等．虚实结合的机械安全防护培训系统研究 [J]．中国安全科学学报,2018,28(5):166-171.(Zhou Cheng,Kong Chao,Curie Kai,et al.Research on the training system of mechanical safety protection combining virtual and real [J]. Chinese Journal of Safety Science,2018,28 (5):166-171).   
[2]郑瑛．云计算数据中心节能调度算法改进研究[J]．西南大学学报： 自然科学版,2019,41(12):135-142.(Zheng Ying.Improved Research on Energy Saving Scheduling Algorithm of Cloud Computing Data Center [J].Journal of Southwest University:Natural Science Edition, 2019,41(12):135-142).   
[3]韩虎，王鹏，程琨，等．基于多尺度量子谐振子算法的云计算任务调 度[J].计算机应用,2017,37(07):1888-1892.(Han Hu,Wang Peng, Cheng Kun,et al. Cloud computing task scheduling based onmulti-scale quantum harmonic oscillator algorithm [J].Journal of Computer Applications,2017,37 (07): 1888-1892.   
[4]朱亚会，陈丹，庄毅．云数据中心资源利用率均衡的虚拟机调度算 法[J].小型微型计算机系统，2017,38(02):232-237.(Zhu Yahui, Chen Dan,Zhuang Yi.Virtual Machine SchedulingAlgorithm for Cloud Data Center Resource Utilization Balance [J]. Small Microcomputer System,2017,38 (02):232-237).   
[5]Akhter,Nasrin,Othman,Mohamed.Energy aware resource allocation of cloud data center: review and open issues [J]. Cluster Computing,2016, 19 (3): 1163-1182.   
[6]Hatem Aziza, Saoussen Krichen.Bi-objective decision support system for task-scheduling based on genetic algorithm in cloud computing [J]. Computing,2018,100 (2): 65-91.   
[7]Pandita,Archana,Upadhyay,Prabhat K.Fault Tolerance Aware Scheduling for Brokers in Cloud Computing Datacenters [J].Recent Patents on Computer Science,2017,10 (4): 299-307.   
[8]Pham C,Tran NH,Ren S,et al. Joint Energy Scheduling and Water Saving in Geo-Distributed Mixed-Use Buildings [J].IEEE Transactions on Smart Grid,2019,10 (5):5345-5359.   
[9]Tang F,YangL T,Tang C,et al.ADynamical and Load-Balanced Flow Scheduling Approach for Big Data Centers in Clouds [J]．IEEE Transactions on Cloud Computing,2018,6 (4): 915-928.   
[10]张敏，谢辅雯，胡中栋．云环境下利用用户到数据中心建模的高效 节能路由算法[J].计算机应用研究，2017,34(12):3806-3810. (Zhang Min,Xie Fuwen,Hu Zhongdong.Efficient and energy-efficient routing algorithm using user to data center modeling in cloud environment [J].Journal of Computer Applications,2017,34(12): 3806- 3810).   
[11]齐平，王福成，王必晴，等．云计算环境下基于可靠性感知的任务调 度算法[J].计算机工程与科学,2018,40(11):1925-1935.(Qi Ping, Wang Fucheng,Wang Biqing,et al. Task scheduling algorithm based on reliability perception in cloud computing environment [J].Computer Engineering and Science,2018,40 (11):1925-1935).   
[12]王英，秦丁，刘杰，等．基于生产函数的效用优化云计算资源调度算 法[J]．计算机应用研究，2017,34(02):397-400.(Wang Ying，Qin Ding，Liu Jie，et al. Utility-optimized cloud computing resource scheduling algorithm based on production function [J].Journal of Computer Applications,2017,34 (02): 397-400)   
[13] Alla HB,Alla SB,Touhafi A,et al.A novel task scheduling approach based on dynamic queues and hybrid meta-heuristic algorithms for cloud computing environment [J].Cluster Computing,2018,21(4): 1797-1820   
[14] Nasim R,Zola E,KasslerAJ.Robust optimization for energy-efficient virtual machine consolidation in modern datacenters [J].Cluster Computing,2018,21 (3):1681-1709.   
[15] Arivudainambi D,Dhanya D. Scheduling Optimized Secured Virtual Machine Using Cuckoo Search and Flow Analyzer [J].Journal of Computational and Theoretical Nanoscience,2017,14 (6): 2715-2724.   
[16] V.M.Arul Xavier,Annadurai S.Chaotic social spider algorithm for load balance aware task scheduling in cloud computing [J].Cluster Computing,2019,22 (9): 287-297.   
[17] Abdolrasol M G M,Hannan MA,Mohamed A,et al.An Optimal Scheduling Controller for Virtual Power Plant and Microgrid Integration using Binary Backtracking Search Algorithm [J].IEEE Transactions on Industry Applications,2018,54 (3): 2834-2844.   
[18] Senthamarai N, Vijayalakshmi M.Dynamic Resource Allocation Based on Energy Consumption Using Hyped-Up Voltage Frequency Scaling Model in Cloud Computing [J].Journal of Computational and Theoretical Nanoscience,2017,14 (4): 1837-1843.   
[19]Ali MM,Huda S,Abawajy J,etal.A parallel framework for software defect detection and metric selection on cloud computing [J]. Cluster Computing,2017,20 (3):2267-2281.   
[20] Ehsan M,Chandrasekaran K,Chen Y,et al.Cost-Efficient Tasks and Data Co-Scheduling with AffordHadoop [J].IEEE Transactions on Cloud Computing,2019,7 (3): 719-732.