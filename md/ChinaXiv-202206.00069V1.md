# 门诊动态溢流排队系统感性和理性退出率分析

李军祥，卢宜玲，潘龙博(上海理工大学 管理学院，上海 200093)

摘要：在现实医疗服务中，面对医生座席数量供不应求的现状，采用传统的双队列独立排队系统很难高效利用医院资源。对此，在不改变医院现有资源的情况下设置系统动态用来合理配比各门诊患者容量，在传统双队列独立排队系统的基础上建立动态溢流门诊排队生灭模型，并考虑患者在感性与理性因素下退出系统的概率，便于更准确地分析系统的真实状态。借助 ProModel这一灵活、可靠的离散事件仿真软件，将模型可视化研究，并与传统的门诊排队模型进行对比分析。仿真结果显示，新型排队模型的队列的平均长度，患者的等待时间等服务指标均优于传统的排队模型。

关键词：排队系统；动态溢流；退出率；感性；理性 中图分类号：TP391.9 doi:10.19734/j.issn.1001-3695.2022.03.0116

Analysis of exit rate with perceptual and rational factors in outpatient dynamic overflow queuing system

Li Junxiang†,Lu Yiling, Pan Longbo (Business School,University ofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract: Inthe practical appicationof medical service system,under the short supplyofdoctorseats,traditional doublequeue independent queuing system is inadequate forsufficient utilizationof hospital resources.In this regard,itbuilt a dynamic system toalocate reasonably thecapacityofeach outpatient queuing system witout increasing thecurrent hospital resources.Furthermore,itmodeledthedynamicoverflowoutpatientqueuing systemto improve the traditional double-queue independentqueuing system,andconsideredthe probabilityofexitingsystemunder perceptualandrational factors toanalyze accurately therealconditionofsystem.With thehelpofProModel,aflexibleandreliablediscrete eventsimulationsoftware, it nalyzedand compared visuall the dynamic model with traditional outpatient queuing model.The simulationresults show that the average queue length,waiting time of patients and other service indices of the new overflow queuing model are superior to those of traditional queuing model.

Key words:queuing system; dynamic overflow; exit rate; perceptual; rational

# 0 引言

近年来，随着医疗服务水平的提升及人民服务需求的不断扩大，我国在医疗服务行业的发展尤为迅速。国家卫生健康委员会有关报告曾指出：一个国家的医疗质量和医疗安全直接关系到人民群众健康[1]。为了持续构建优质高效医疗卫生服务体系，更好满足人民日益增长的健康需求，各国医疗技术能力和医疗质量水平显著提升，同时相应的医疗卫生投入也稳步增长。在各国医疗卫生投入大幅度增加的同时，医疗体制的改革取得了一定的成果，但大部分医院的运营效率并未成正比例的提升，其依旧面临着门诊量大、患者排队拥挤和等待时间过长等重要问题。据相关数据显示，患者在就诊过程中的有效诊疗时间大约占门诊时间的 $1 0 \% { \sim } 1 5 \%$ ，非治疗耗时高达 $8 5 \%$ 左右[2]。由此可见，若要医疗质量与患者安全得到保障，不仅要考虑对医疗卫生资金投入，更需要探究如何能有效提高医疗服务系统的各个运作环节的效率。

目前，国内外许多学者对提高医院运作效率的相关问题做了一定的研究工作。Joseph等人[3]运用回顾性队列研究，采用广义估计方程压缩的方法预测医生每小时服务的患者数量，并研究了医生工作量、患者安全、科室选址和服务质量之间量化关系。Andersen等人[4]将患者流建模为瞬态的排队网络，使用整数规划递归的方法评估和分配患者到系统，直到网络的所有队列中都遵循等待时间目标。Zhang 等人[5]提出了一种新的具有优先权的病人排队模型，以优化急诊服务的管理与经典排队规则相比，该模型考虑了服务的关键因素根据相关排队指标探讨了应急服务的优化问题。Barros 等人[6]对比分析预测需求和可用医疗资源之间的误差，用仿真模型来评估设施和资源的不同配置性能的差异。Wu等人[7]应用病床容量和服务交互的多阶段串联排队模型对医疗系统进行建模。李凌洋等人[8]根据对医院收费过程中随机动态特征的研究，采用 $\mathrm { M } / \mathrm { M } / \mathrm { c } / \infty / \infty / \mathrm { F C F S }$ 排队模型对医院窗口优化设置进行研究。荆彤等人[9研究了带有工作故障和顾客止步的重试排队系统，为现实的医院运营情况提供了一种风险预测和决策评估。羊英等人[10]在考虑专家服务质量和患者的排队成本以及焦虑程度等因素下，建立了患者决策是否选择某专家为其提供服务的价值模型。运用该模型推算出患者能够接受的最长等待时间和队列长度等性能指标，并提出了详细优化意见。He 等人[以离散事件模拟法为基础，建立常州市某三级医院牙科服务流程优化模型。通过实地调研收集数据，然后根据现有的服务模型设置模型参数。建议在分诊流程中加入预检，在有限的资源条件下提高医院服务质量和资源利用率，减少病人等待时间。Kang等人[12]借助韩国国家急诊信息系统，利用前馈神经网络、正则化等人工智能技术分析研究符合标准的多例急诊患者的数据，建立急诊重症患者预检分诊算法，并将该算法与急诊严重程度指数、修正预警评分及国家早期预警评分等进行比较。结果显示，人工智能算法优于目前临床常用的预检分诊算法。

综上所述，现有文献主要针对医疗人员的调配、患者决策和关键性服务指标等维度进行的独立队列静态优化研究，同时运用排队理论和算法仿真进行有效求解。但在实际场景中，医院分诊调配和队列动态调度的优化可以极大程度地提高服务的运作效率。目前此部分的研究甚少，大量的研究[11,12]仅停留在理论性论述。

因此，本文为了弥补上述研究的不足，提出了一种新型的分诊模型，结合考虑患者的心理和理性因素，从医生服务效率及患者实行溢流操作的角度探讨了排队系统状态，并对排队系统的各个指标进行量化研究。首先，在传统的双队列独立排队系统的基础上加了系统动态，当前队列已满而另一队列仍有等待空间时，根据患者的自身意愿，允许护士台通过二次分诊操作将患者从该队列溢流到另一队列。其次，分析患者因心理和理性因素而选择退出系统的概率，综合考虑多方面约束，使降低患者等待时间和不增加患者退出率保持动态平衡的状态。最后，在不改变医院现有资源的情况下与传统的门诊排队模型进行对比分析，从而达到降低患者队列的平均长度，减少患者的等待时间的研究目的。由于本文研究的模型变动性较强，利用传统的算法或均衡状态方程对模型进行求解得出的是一个静态的平均值[13]，本文所研究的排队系统是一个不断变化的动态过程，通过固定数值无法反映系统的运行情况。因此利用ProMode1仿真进行系统模拟统计出相关的性能指标在运行中的变化图，通过观察波峰、波谷以及涨幅趋势，更加有效且直观地体现系统的服务过程

# 1 模型描述

对考虑患者双向溢流的门诊溢流排队系统进行描述，并假设相关参数。

患者按照参数为 $\lambda _ { i }$ 的泊松流到达医院( $i = 1 , 2$ 分别表示普通和专家患者)，系统有 $\mid c \mid$ 个医生服务座席， $c _ { i }$ 为队列i的医生座席数量 $\left( c = c _ { 1 } + c _ { 2 } \right)$ 。当患者到达系统时，发现医生座席正忙，则需进入队列等待服务。

如果等待队列过长或者医生的服务效率较低时，患者可能出现情绪烦躁，甚至选择离开排队系统。当队列不需等待时，患者到达后进入系统的概率为1；当队列等待的人数大于0时，患者则不会全部进入等待队列。患者退出系统的因素出于两种情况：一是因为心理效用，根据患者得到的服务效用与其付出的成本差值判断患者是否退出系统。若选择退出，则有部分患者流失在刚进入系统阶段，假设进入队列的速率参数为 $\overline { { \lambda _ { i } } }$ ；二是理性效用，在排队过程中，患者根据队列长度和自身的敏感性参数等性能指标判断是否选择退出系统。

当队列i处于饱和阈值上限 $L _ { i } ^ { \operatorname* { m a x } }$ 且另一队列未达到饱和阈值下限 $L _ { i } ^ { \mathrm { m i n } }$ 时，系统会给予拦截，此时系统将判断是否符合溢流分诊的条件。如果满足条件，患者以 $\lambda _ { i } ^ { \prime }$ 溢流到另一门诊系统就诊，否则患者继续处于当前队列等候。为了保证医院的经营效益及满足患者的就诊需求，确保在增加溢流操作的系统中不会损失更多的患者。系统要求各队列患者的退出数量不得高于溢流人数的 $k$ 倍 $\left( k > 1 \right)$ 。

当医生座席处于正常工作状态时， $i$ 队列的医生服务速率服从参数为 $\mu _ { i }$ 的指数分布。在诊治患者的过程中，医生会根据当前的工作时间改变其平均服务强度。此时系统中的i队列患者人数小于 $c _ { i } + n _ { i } ^ { \prime }$ 时(为了方便后续计算，此时系统总患者阈值用 $c _ { i } + n _ { i } ^ { \prime }$ 表示， $n _ { i } ^ { \prime }$ 为此时队列的总患者阈值)，各医生的服务速率是 $\mu _ { i , 1 }$ (表示单位时间诊治人数均值)， $\rho _ { i , 1 }$ 为患者在快诊治速率下的诊治强度；反之，各医生的服务速率因产生疲劳而有所降低设为 $\mu _ { i , 2 }$ ， $\rho _ { i , 2 }$ 为患者在慢诊治速率下的诊治强度，其中 $\mu _ { i , 1 } > \mu _ { i , 2 }$ 。

患者到达医院的时间间隔、医生座席的服务速率、患者的不耐烦强度均是相互独立。系统服务规则服从先到先服务的原则(First In First Out)。

考虑上述的几种因素，建立二次分诊的就诊排队模型的路由规则如图1所示。患者通过多种途径预约或现场挂号，挂号信息引导患者到相应诊室的护士台确认就诊，诊区的分诊候诊单元可实现多功能对业务的管理和操作。根据挂号要求将患者分为普通和专家门诊。首先考虑心理效用，判断患者的服务效用是否大于服务费用与相应的等待成本之和，若满足则患者的心理效用为正，可进入相应的队列，否则终止退出系统。其次判断是否满足溢流条件，若该队列达饱和状态系统会给予拦截，此时系统将判断是否符合溢流分诊的条件。如果满足条件，该队列患者可以溢流到另一门诊系统就诊；否则，继续在当前队列等待。最后，患者根据理性效用决策是否退出系统。进入队列后，由于医生服务效率降低或溢流操作等因素，判断患者是否因等待时间过长而产生不耐烦因素退出系统，否则，继续在该队列等待服务。患者在采用先到先服务的排队规则等待接受服务时，该路由降低了患者在等候区等候的拥挤状况且提高了各门诊医生座席的利用率。

![](images/913b9742b3bf1df7bae34b6a37a323de54c823bf9d66f4b90410f299246be369.jpg)  
图1双向溢流排队模型路由规则  
Fig.1Two-way overflow queuing model routing rules

# 2 模型建立

# 2.1 目标函数

本文考虑服务能力有限且服务速率可变的 $\mathbf { M } / \mathbf { M } / \mathbf { c } / \mathbf { N }$ 就诊排队模型，对系统中存在的状态转移进行分析。该模型为有容量限制的多服务台系统，则就诊排队系统的状态可以用以下集合中的元素来表示[14]:

$$
S = \left\{ { \left( n _ { 1 } \left( t \right) , n _ { 2 } \left( t \right) \right) } | 0 \leq n _ { 1 } \left( t \right) < N _ { 1 } , 0 \leq n _ { 2 } \left( t \right) \leq N _ { 2 } \right\}
$$

其中， $n _ { i } \left( t \right)$ 表示 $t$ 时刻系统中 $i$ 队列的患者数量， $t \in \left[ 0 , T \right]$ ，$T$ 为门诊医生的工作的总时长。 $N _ { i }$ 为 $i$ 队列门诊系统的最大容纳量。

由相关文献研究结果显示[15]，当医生的服务速率会受其工作时间长度、诊治患者的数量或患者病情复杂程度等因素的影响。假设服务速率随着系统中患者的数量而变化，即i队列医生服务速率由式(2)所示。

$$
\begin{array} { r } { \mu _ { i } = \left\{ \begin{array} { l l } { n _ { i } \left( t \right) \mu _ { i , 1 } , } & { 0 < n _ { i } \left( t \right) < c _ { i } } \\ { c _ { i } \mu _ { i , 1 } , } & { c _ { i } \leq n _ { i } \left( t \right) < c _ { i } + n _ { i } ^ { \prime } } \\ { c _ { i } \mu _ { i , 2 } , } & { n _ { i } \left( t \right) \geq c _ { i } + n _ { i } ^ { \prime } } \end{array} \right. } \end{array}
$$

对上述情形采用生灭过程进行建模，寻找稳态水平是生灭过程建模的重要问题，本部分给出生灭过程稳态条件的定理及证明。假设 $P _ { n _ { i } ( t ) }$ 表示 $i$ 队列在 $t$ 时刻到达的前 $n$ 位患者的概率， $P _ { 0 }$ 是初始状态，为系统中 $i$ 队列没有患者的概率。

定理若 ${ \rho } _ { i , 1 } = \lambda _ { i } / \mu _ { i , 1 }$ ， ${ \rho } _ { i , 2 } = \lambda _ { i } / \mu _ { i , 2 }$ ，且 $\rho _ { i , 1 } < 1$ ， $\rho _ { i , 2 } < 1 \ ( i = 1 , 2 )$ 。即系统是稳定的，则存在服务率可变的排队系统的稳态分布：

$$
P _ { n _ { i } ( t ) } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { n _ { i } \left( t \right) ! } \rho _ { i , 1 } { } ^ { n _ { i } ( t ) } P _ { 0 } , } & { 1 \le n _ { i } \left( t \right) < c _ { i } - 1 } \\ { \displaystyle \frac { \rho _ { i , 1 } { } ^ { n _ { i } ( t ) } } { c _ { i } ! c _ { i } ^ { n _ { i } ( t ) - c _ { i } } } P _ { 0 } , } & { c _ { i } - 1 \le n _ { i } \left( t \right) < c _ { i } + n _ { i } ^ { \prime } } \\ { \displaystyle \frac { \rho _ { i , 1 } c _ { i } + n _ { i } ^ { \prime } \rho _ { i , 2 } { } ^ { n _ { i } ( t ) - \left( c _ { i } + n _ { i } ^ { \prime } \right) } } { c _ { i } ! c _ { i } ^ { n _ { i } ( t ) - c _ { i } } } P _ { 0 } , } & { n _ { i } \left( t \right) \ge c _ { i } + n _ { i } ^ { \prime } } \end{array} \right.
$$

证明由生灭过程平衡状态的 $\mathrm { ~ K ~ }$ 氏代数方程(输入率等于 输出率)得

对 $n _ { i } \left( t \right) = 0$ 状态，有 $\lambda _ { i } P _ { 0 } = \mu _ { i , 1 } P _ { 1 }$ ，故 $P _ { 1 } = \frac { \lambda _ { i } } { \mu _ { i , 1 } } P _ { 0 } = \rho _ { i , 1 } P _ { 0 }$ 对 $n _ { i } \left( t \right) = 1$ 状态，有 $\lambda _ { i } P _ { 1 } = 2 \mu _ { i , 1 } P _ { 2 }$ ，故 $P _ { 2 } = \frac { 1 } { 2 } \rho _ { i , 1 } P _ { 1 } = \frac { 1 } { 2 ! } { \rho _ { i , 1 } } ^ { 2 } P _ { 0 }$ 对 $n _ { i } \left( t \right) = c _ { i } - 1$ 状态，有 $\lambda _ { i } P _ { c _ { i } - 1 } = c _ { i } \mu _ { i , 1 } P _ { c _ { i } }$ ，故 $P _ { c _ { i } } = \frac { 1 } { c _ { i } } \rho _ { i , 1 } P _ { c _ { i } - 1 } = \frac { 1 } { c _ { i } ! } \rho _ { i , 1 } { } ^ { c _ { i } } P _ { 0 }$ 对 $n _ { i } \left( t \right) = c _ { i }$ 状态，有 $\lambda _ { i } P _ { c _ { i } } = c _ { i } \mu _ { i , 1 } P _ { c _ { i } + 1 }$ ，故 $P _ { c _ { i } + 1 } = \frac { \lambda _ { i } } { c _ { i } \mu _ { i , 1 } } P _ { c _ { i } } = \frac { \rho _ { i , 1 } { } ^ { c _ { i } + 1 } } { c _ { i } \{ c _ { i } }  P _ { 0 }$ 对 $n _ { i } \left( t \right) = c _ { i } + n _ { i } ^ { \prime } - 1$ 状态，有 $\lambda _ { i } P _ { c _ { i } + n _ { i } ^ { \prime } - 1 } = c _ { i } \mu _ { i , 1 } P _ { c _ { i } + n _ { i } ^ { \prime } }$ ，故 $P _ { { { \it c } _ { i } } + { { n } _ { i } } ^ { \prime } } = \frac { { { \lambda } _ { i } } } { { { c } _ { i } } \mu _ { i , 1 } } P _ { { { \it c } _ { i } } + { { n } _ { i } } ^ { \prime } - 1 } =$ $\frac { \rho _ { i , 1 } { } ^ { c _ { i } + n _ { i } ^ { \prime } } } { c _ { i } ! c _ { i } ^ { n _ { i } ^ { \prime } } } P _ { 0 } \ ;$ 对 $n _ { i } \left( t \right) = c _ { i } + n _ { i } ^ { \prime }$ 状态，有 $\lambda _ { i } P _ { { } _ { c _ { i } + n _ { i ^ { ' } } } } = c _ { i } \mu _ { i , 2 } P _ { { } _ { c _ { i } + n _ { i ^ { ' } } + 1 } }$ ，故 $P _ { c _ { i } + n _ { i } ^ { \prime } + 1 } = \frac { \lambda _ { i } } { c _ { i } \mu _ { i , 2 } } P _ { c _ { i } + n _ { i } ^ { \prime } } =$ $\frac { \lambda _ { i } } { c _ { i } \mu _ { i , 2 } } \frac { \rho _ { i , 1 } ^ { \phantom { } } c _ { i } + n _ { i } ^ { \prime } } { c _ { i } ^ { \phantom { } } ! c _ { i } ^ { n _ { i } ^ { \prime } } } P _ { 0 } = \frac { \rho _ { 1 } ^ { \phantom { } } c _ { i } ^ { \phantom { } + n _ { i } ^ { \prime } } \rho _ { i , 2 } ^ { \phantom { } } } { c _ { i } ^ { \phantom { } } ! c _ { i } ^ { n _ { i } ^ { \prime } + 1 } } P _ { 0 } \ ;$

证毕。

得到系统稳态概率 $P _ { n _ { i } ( t ) }$ 后，系统的主要性能指标需做如下分析。

在 $\mathrm { M } / \mathrm { M } / \mathrm { c } / \mathrm { N }$ 系统中，只要有等待的患者，则说明患者的数量大于医生座席的数量，即系统状态中有 $c _ { i }$ 位患者正在接受就诊服务，按照求均值定义[16]，系统稳态下的 $t$ 时刻 $i$ 队列门诊排队等候患者的平均队长 $L _ { ☉ } ( t )$ 为

$$
L _ { i } ( t ) = \sum _ { n _ { i } ( t ) = 1 } ^ { N _ { i } - c _ { i } } n _ { i } \left( t \right) P _ { n _ { i } ( t ) }
$$

由Little方程[17]，在 $t$ 时刻 $i$ 队列患者的平均等候服务时间为等候患者的平均队长与患者到达速率之比。假设 $W _ { i } ^ { \prime } ( t )$ 为传统排队模型中患者的平均等候服务时间。传统的双队列独立排队系统患者排队等待时间总和 $\Gamma _ { 1 } ( t )$ 为

$$
\Gamma _ { 1 } \left( t \right) = \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } W _ { i } ^ { \prime } ( t ) = \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } \frac { L _ { i } ( t ) } { \lambda _ { i } }
$$

假设 $W _ { i } ( t )$ 为新型溢流排队模型中患者的平均等候服务时间，则其患者排队等待时间总和 $\Gamma _ { 2 } ( t )$ 为

$$
W _ { 1 } ( t ) = \frac { L _ { 1 } ( t ) } { \lambda _ { 1 } - \lambda _ { 1 } ^ { \prime } + \lambda _ { 2 } ^ { \prime } }
$$

$$
W _ { 2 } ( t ) = \frac { L _ { 2 } ( t ) } { \lambda _ { 2 } - \lambda _ { 2 } ^ { ' } + \lambda _ { 1 } ^ { ' } }
$$

$$
\Gamma _ { 2 } \left( t \right) = \sum _ { t = 0 } ^ { T } \left( W _ { 1 } ( t ) + W _ { 2 } ( t ) \right)
$$

目标函数为患者溢流操作前后系统所有患者排队的总等待时间差值，目标函数如下：

$$
\begin{array} { l } { \displaystyle \Delta \Gamma = \big | \Gamma _ { 1 } \big ( t \big ) - \Gamma _ { 2 } \big ( t \big ) \big | = } \\ { \displaystyle  | \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } \frac { L _ { i } \big ( t \big ) } { \lambda _ { i } } - \sum _ { t = 0 } ^ { T } ( \frac { L _ { 1 } ( t ) } { \lambda _ { 1 } - \lambda _ { 1 } ^ { \prime } + \lambda _ { 2 } ^ { \prime } } + \frac { L _ { 2 } ( t ) } { \lambda _ { 2 } - \lambda _ { 2 } ^ { \prime } + \lambda _ { 1 } ^ { \prime } } ) | ^ { ( 9 ) } } \end{array}
$$

# 2.2约束条件

1）考虑心理因素的退出约束

效用(utility)通常用于度量服务满足患者需求的能力，是患者进行是否接受服务决策的重要评价指标，基于效用理论[18]，将患者心理效用定义为：患者从医生服务中得到的心理满足程度。假设患者通过医生服务获得的治疗效果为$R _ { i }$ ，支付的服务费用为 $C _ { i }$ ，相应的单位时间等待成本为 $K _ { i }$ u普通患者和专家患者的心理效用 $U _ { i } ( t )$ 分别为

$$
\begin{array} { r } { U _ { 1 } ( t ) = R _ { 1 } - C _ { 1 } - K _ { 1 } E [ W _ { 1 } ( t ) ] - \sigma _ { 1 } \left( \lvert E [ W _ { 1 } ( t ) ] - E [ W _ { 2 } ( t ) ] \rvert \right) } \end{array}
$$

$$
U _ { 2 } \left( t \right) = R _ { 2 } - C _ { 2 } - K _ { 2 } E \left[ W _ { 2 } \left( t \right) \right] - \sigma _ { 2 } \left( \left| E \left[ W _ { 2 } \left( t \right) \right] - E \left[ W _ { 1 } \left( t \right) \right] \right| \right)
$$

其中， $\sigma _ { i }$ 为患者的选择偏好值，其与 $t$ 时刻各队列的期望等待时间 $E [ W _ { i } ( t ) ]$ 具有强关联性。若 $E \big [ W _ { 1 } ( t ) \big ] \geq E \big [ W _ { 2 } ( t ) \big ]$ ，则 $\sigma _ { 1 } \geq 0$ ：否则 $\sigma _ { 1 } < 0$ ；若 $E \big [ W _ { 2 } \left( t \right) \big ] \geq E \big [ W _ { 1 } \left( t \right) \big ]$ ，则 $\sigma _ { 2 } \geq 0$ ，否则 $\sigma _ { 2 } < 0$ 。由于专家门诊服务费用高于普通门诊( $C _ { 1 } < C _ { 2 }$ )，则相应患者获得服务效用成正相关， $R _ { \mathrm { { I } } } < R _ { \mathrm { { 2 } } }$ 。

患者是否选择进入服务系统是由心理效用决定的，选择退出系统应满足 $U _ { i } \left( t \right) \leq 0$ 。因此选择退出系统的患者的单位等待时间成本应满足：

$$
K _ { 1 } \ge \left( R _ { 1 } - C _ { 1 } - \sigma _ { 1 } \left( \left| E \big [ W _ { 1 } \left( t \right) \big ] - E \big [ W _ { 2 } \left( t \right) \big ] \right| \right) \right) / E \big [ W _ { 1 } \left( t \right) \big ]
$$

$$
K _ { 2 } \ge \left( R _ { 2 } - C _ { 2 } - \sigma _ { 2 } \left( \left| E \left[ W _ { 2 } \left( t \right) \right] - E \left[ W _ { 1 } \left( t \right) \right] \right| \right) \right) / E \left[ W _ { 2 } \left( t \right) \right]
$$

假设 $t$ 时刻普通和专家患者因心理效用选择退出系统的概率 $\overline { { P } } _ { 1 } ( t )$ 和 $\overline { { P } } _ { 2 } ( t )$ 分别为

$$
\begin{array} { r } { \overline { { P } } _ { 1 } \left( t \right) = \overline { { P } } \left( K _ { 1 } \geq \left( R _ { 1 } - C _ { 1 } - \sigma _ { 1 } \left( \left| E \left[ W _ { 1 } \left( t \right) \right] - E \left[ W _ { 2 } \left( t \right) \right] \right| \right) \right) / E \left[ W _ { 1 } \left( t \right) \right] \right) } \end{array}
$$

$$
\begin{array} { r } { \overline { { P } } _ { 2 } \left( t \right) = \overline { { P } } \left( { K _ { 2 } \geq \left( { R _ { 2 } - C _ { 2 } - \sigma _ { 2 } \left( { \left| E \left[ { W _ { 2 } \left( t \right) } \right] - E \left[ { W _ { 1 } \left( t \right) } \right] \right| } \right) } \right) / E \left[ { W _ { 2 } \left( t \right) } \right] } \right) } \end{array}
$$

根据上述分析可知， $\textit { t }$ 时刻患者进入队列的到达率 $\overline { { \lambda _ { i } } }$ 为

$$
\overline { { \lambda _ { i } } } = \lambda _ { i } \left( 1 - \overline { { P } } _ { i } \left( t \right) \right)
$$

2）考虑患者溢流操作的队列约束判断患者是否选择溢流操作需要满足以下两个条件：

a)队列约束。当队列 $i$ 中排队等候患者的平均队长到达阈值上限 $L _ { i } ^ { \operatorname* { m a x } }$ ，另一队列中排队等候患者的平均队长控制在阈值下限 $L _ { i } ^ { \mathrm { m i n } }$ 的条件下，系统方可提供溢流操作的选择，队列约束如下式：

$$
\gamma _ { i , 1 } ( t ) - \gamma _ { i , 2 } ( t ) = 0 \quad \not \equiv \quad \gamma _ { i , 1 } ( t ) , \gamma _ { i , 2 } ( t ) \neq 0
$$

其中， $\gamma _ { i , 1 } ( t )$ 和 $\gamma _ { i , 2 } \left( t \right)$ 均为0-1变量，当 $L _ { 1 } \left( t \right) \geq L _ { 1 } ^ { \operatorname* { m a x } }$ 时， $\gamma _ { 1 , 1 } \left( t \right) = 1$ ：否则 $\gamma _ { 1 , 1 } ( t ) = 0$ ；当 $L _ { 2 } \left( t \right) \leq L _ { 2 } ^ { \mathrm { m i n } }$ 时， $\gamma _ { 1 , 2 } \left( t \right) = 1$ ，否则 $\gamma _ { 1 , 2 } \left( t \right) = 0$ ，此种情况为普通患者溢流的队列约束。当 $L _ { 2 } \left( t \right) \geq L _ { 2 } ^ { \operatorname* { m a x } }$ 时，$\gamma _ { 2 , 2 } \left( t \right) = 1$ ，否则 $\gamma _ { 2 , 2 } \left( t \right) = 0$ 。当 $L _ { 1 } \left( t \right) \le L _ { 1 } ^ { \mathrm { m i n } }$ 时， $\gamma _ { 2 , 1 } \left( t \right) = 1$ ，否则$\gamma _ { 2 , 1 } \left( t \right) = 0$ ，此种情况为专家患者溢流的队列约束。

b)患者意愿决策约束。以马科维兹的均值一方差理论[19]为基础建立患者是否选择转移队列的决策约束，将患者等待时间的平均值 $W _ { i } \left( t \right)$ 和标准差 $W _ { i } ^ { \sigma } \left( t \right)$ 之间的权衡关系作为患者选择决策的重要指标。各队列患者进行客观权衡时，仍存在均值与方差两者之间的非对称偏好，根据文献研究表明[20].相较于标准差，患者对减少均值的偏好更高。假设 $\nu$ 为患者非对称偏好系数 $( 0 < \nu < 1 )$ 。 $\pi _ { n _ { 1 } } ( t )$ 为t时刻普通患者选择溢流操作的意愿，当普通患者等待时间的均值和标准差均大于专家队列时，或均值的减少量大于标准差增加量的 $\upsilon$ 倍时，$\pi _ { n _ { 1 } } \left( t \right) = 1$ ，否则 $\pi _ { n _ { 1 } } ( t ) = 0$ 。 $\pi _ { n _ { 2 } } \left( t \right)$ 为 $t$ 时刻专家患者选择溢流操作的意愿，表示含义同上。

综上，溢流系统的平均队长 $L _ { i } ^ { \prime } ( t )$ 为

$$
L _ { i } ^ { \prime } ( t ) = \frac { 1 } { 2 t } \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } \pi _ { n _ { i } } \left( t \right)
$$

其中

$$
\begin{array} { r } { \pi _ { n _ { 1 } } \left( t \right) = \left\{ \begin{array} { c c } { 1 , } & { W _ { 1 } \left( t \right) - W _ { 2 } \left( t \right) > \nu \left( W _ { 2 } ^ { \sigma } \left( t \right) - W _ { 1 } ^ { \sigma } \left( t \right) \right) \mathrm { { i } } } \\ { W _ { 1 } \left( t \right) > W _ { 2 } \left( t \right) \mathrm { { E } } W _ { 1 } ^ { \sigma } \left( t \right) > W _ { 2 } ^ { \sigma } \left( t \right) } \\ { 0 , } & { \sharp \sharp \mathcal { M } } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r } { \pi _ { n _ { 2 } } \left( t \right) = \left\{ \begin{array} { c c } { 1 , } & { W _ { 2 } \left( t \right) - W _ { 1 } \left( t \right) > \nu \left( W _ { 1 } ^ { \sigma } \left( t \right) - W _ { 2 } ^ { \sigma } \left( t \right) \right) \varTheta } \\ { W _ { 2 } \left( t \right) > W _ { 1 } \left( t \right) \operatorname { E } W _ { 2 } ^ { \sigma } \left( t \right) > W _ { 1 } ^ { \sigma } \left( t \right) } \\ { 0 , } & { \varXi \backslash \dag \mathrm { H } \mathscr { L } } \end{array} \right. } \end{array}
$$

# 3）考虑理性因素的退出约束

在患者实现溢流操作的同时考虑其不耐烦因素，如果患者排队等候的时间过长，可能会引起等待患者出现烦躁情绪，甚至有的患者会选择离开排队系统。假设 $t$ 时刻队列中不耐烦患者最终离开排队系统的强度与系统稳态下的排队等候患者的平均队列长度 $L _ { i } \left( t \right)$ 和溢流系统的平均队长 $L _ { i } ^ { \prime } ( t )$ 有关。患者退出系统的概率为 $\Delta _ { i } \left( t \right)$ 。患者之间的选择是独立的，考虑每个人的耐受性是不同的。假设 $\varepsilon$ 为患者的敏感性参数。患者的退出率为平均队长的线性函数，其止步概率为[21];

$$
\Delta _ { 1 } \left( t \right) = \left( L _ { 1 } \left( t \right) + L _ { 2 } ^ { \prime } \left( t \right) \right) / \varepsilon
$$

$$
\Delta _ { 2 } \left( t \right) = \left( L _ { 2 } \left( t \right) + L _ { 1 } ^ { \prime } ( t ) \right) / \varepsilon
$$

其中，系统中的该队列排队等候患者的平均队列长度 $L _ { i } \left( t \right)$ 和溢流系统的平均队长 $L _ { i } ^ { \prime } ( t )$ 最大容纳量分别为 $\overline { { L _ { i } } }$ 和 $\overline { { L _ { i } ^ { \prime } } }$ ，$\overline { { L } } _ { 1 } + \overline { { L } } _ { 2 } ^ { \prime }$ 为普通队列等候区域容量的最大值， $\overline { { L } } _ { 2 } + \overline { { L } } _ { 1 } ^ { \prime }$ 为专家队列等候区域容量的最大值，假设 $\overline { { L } } _ { 1 } + \overline { { L } } _ { 2 } ^ { \prime } < \varepsilon$ ， $\overline { { L } } _ { 2 } + \overline { { L } } _ { 1 } ^ { \prime } < \varepsilon$ 。 $\varepsilon$ 越小，则表明患者的敏感性越大，越容易产生不耐烦因素。考虑每个人的耐受性是不同的，患者的敏感性参数应在一个合理的区间内波动，聚集度不可过高或过低，假设 $\varepsilon$ 在 $\left[ \underline { { \varepsilon } } , \ \overline { { \varepsilon } } \right]$ 上均匀分布， $\underline { { \varepsilon } }$ 、 $\overline { { \varepsilon } }$ 表示患者敏感性参数的下限和上限（204号 $\left( \underset { - } { \varepsilon } > 0 \right)$ 。系统中 $t$ 时刻普通和专家患者总的退出数量 $l _ { i } ( t )$ 为

$$
{ l } _ { i } \left( t \right) = \Delta _ { i } \left( t \right) L _ { i } \left( t \right)
$$

为了保证均衡各医生座席利用率的同时，不造成原本患者的大量流失，假设 $t$ 时刻患者离开队列数量不得高于溢流患者人数的 $k$ 倍，则有以下约束：

$$
l _ { 1 } ( t ) \leq k L _ { 2 } ^ { \prime } ( t )
$$

$$
l _ { 2 } ( t ) \leq k L _ { 1 } ^ { \prime } ( t )
$$

本文研究的目的是使患者实施溢流操作前后系统所有患者排队的总等待时间差值最大，则表明溢流排队系统可极大程度地降低患者在队列中的等待时间。综合以上全部约束，整合出的优化模型如下：

$$
\operatorname* { m a x } \left\{ | \Delta \Gamma | = \left| \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } \frac { L _ { i } \left( t \right) } { \lambda _ { i } } - \sum _ { t = 0 } ^ { T } \left( \frac { L _ { 1 } \left( t \right) } { \lambda _ { 1 } - \lambda _ { 1 } ^ { \prime } + \lambda _ { 2 } ^ { \prime } } + \frac { L _ { 2 } \left( t \right) } { \lambda _ { 2 } - \lambda _ { 2 } ^ { \prime } + \lambda _ { 1 } ^ { \prime } } \right) \right| \right\}
$$

$$
\begin{array} { r } { \mathrm { s . t } \left\{ \begin{array} { l } { \displaystyle \overline { { \lambda _ { i } } } = \lambda _ { i } \left( 1 - \overline { { P _ { i } } } \left( t \right) \right) } \\ { \displaystyle \gamma _ { i , 1 } \left( t \right) - \gamma _ { i , 2 } \left( t \right) = 0 , \frac { \ast \ast } { \sharp } \gamma _ { i , 1 } \left( t \right) \neq 0 , \gamma _ { i , 2 } \left( t \right) \neq 0 } \\ { \displaystyle L _ { i } ^ { \prime } \left( t \right) = \frac { 1 } { 2 t } \sum _ { i = 1 } ^ { 2 } \sum _ { t = 0 } ^ { T } \pi _ { n _ { i } } \left( t \right) } \\ { \displaystyle l _ { 1 } \left( t \right) \leq k L _ { 2 } ^ { \prime } \left( t \right) , l _ { 2 } \left( t \right) \leq k L _ { 1 } ^ { \prime } ( t ) } \end{array} \right. } \end{array}
$$

# 3 数值仿真

# 3.1仿真模块分析

ProModel是一个模拟离散事件系统的仿真软件，其时间分辨率可达0.01小时\~0.0001秒这个范围，可以极大地提升模拟的精确度[22]。它主要应用于模拟各种生产系统和服务系统。本文则运用该软件进行仿真建模，致力于降低患者的等待时间，优化门诊流程中的各项服务指标。

根据现实的场景进行仿真实验，设置实验组与对照组进行对比分析，实验组考虑溢流排队模型及其3个约束(如图2所示)，其余变量与对照组保持一致，从而研究新型排队模型是否对各项服务指标有一定的影响。

ProModel建模要素包括系统对象要素和系统操作两种类型，涉及十几个要素模块，其模块基本要素参数设置如表1\~3 所示。

# 1)Location(位置)/Entitie(实体)

Location主要用来表示在医院对患者进行排队等待的固定地点或场所、相应的容量及单元数，并设置时间序列(TimeSeries)收集基本的数据和追踪位置的时间序列值。Entities是仿真要服务的对象，本文指医院中就诊的患者(为了区分不同位置的实体，将用病人和患者两种表述)。

![](images/01a70dfbde77473d1d7bedf9cc37f50ed02a4bad7ef90f880d6ac1d30d5f358d.jpg)  
图2仿真界面图  
Fig.2Simulation interface diagram

2) Arrival (到达)

患者到达医院有一定的容量限制并且还需要服从一定的概率分布。为了研究结果更具使用价值，运用现场调研法对某医院的外科诊室的实际调研数据进行筛选处理后作为仿真参数。根据1个工作日的数据进行计算分析，普通门诊工作时间8:00-16:15，专家门诊的工作时间上午8:00-12:00；下午13:00-16:00。运用SPSS统计软件分别对普通和专家患者到达数据及普通和专家医生座席服务情况进行单样本柯尔莫戈洛夫一斯米诺夫检验，检验结果表示专家和普通患者进入系统到达率数据的渐近显著性(双尾)均大于0.05，因此近似服从泊松分布。针对专家和普通医生服务情况检验的渐近显著性(双尾)结果均大于0.05，因此医生座席的服务时间是服从指数分布的。患者到达医院的速率 $\lambda _ { i }$ 和患者选择进入该队列的速率'均服从泊松分布，此时Arrivals界面设置如表1所示，在仿真模块中的到达界面中，如果患者的数量超过容量限制，系统将禁止患者进入。

Tab.1Arrival interface   

<html><body><table><tr><td>实体</td><td>位置</td><td>每次人数</td><td>容量</td><td>到达速率</td></tr><tr><td>普通患者</td><td>医院</td><td>1</td><td>1000</td><td>12.976</td></tr><tr><td>专家患者</td><td>医院</td><td>1</td><td>1500</td><td>8.249</td></tr><tr><td>普通患者</td><td>普通队列</td><td>1</td><td>950</td><td>11.986</td></tr><tr><td>专家患者</td><td>专家队列</td><td>1</td><td>1300</td><td>7.145</td></tr><tr><td>普通患者</td><td>溢流队列2</td><td>1</td><td>80</td><td>0.084</td></tr><tr><td>专家患者</td><td>溢流队列1</td><td>1</td><td>300</td><td>0.232</td></tr></table></body></html>

3) Cost(成本)

仿真中的成本模块主要用来约束模型中考虑患者心理的退出效用，以判断患者是否因为心理效用为负而选择直接退出系统。在文献[23]对供需双方利益的研究的基础上设置患者通过医生服务获得的效用参数。普通和专家的患者支付的服务费用分别为15元和40元，相应的等待成本分别为0.5和0.65，如表2所示。

表1到达界面  
表2成本界面  
Tab.2 Cost interface   

<html><body><table><tr><td>实体</td><td>费用</td><td>规则</td></tr><tr><td>普通患者服务费用</td><td>15</td><td>IF clock(min)(普通)>=U(100,10)and clock (min)</td></tr><tr><td>专家患者服务费用</td><td>40</td><td>(专家)<=U(90,8)then α=0.25 else α =-0.25;</td></tr><tr><td>普通患者等待成本</td><td>0.5</td><td>IF clock(min)(专家)>=U(100,10)and clock(min)</td></tr><tr><td>专家患者等待成本</td><td>0.65</td><td>(普通)<=U(98.9)then α=0.25 else α=-0.25</td></tr><tr><td>普通患者收获效益</td><td>40</td><td>INC vPer_Total_Entity_Cost,</td></tr><tr><td>专家患者收获效益</td><td>60</td><td>Get Cost</td></tr></table></body></html>

4)Process (流程模块)

a）首先读取Arrival模块中的医生工作时刻表，根据时刻表确定该队列的最大容纳量，判断患者实体是否能够进入各队列的系统。

b)专家和普通患者系统是一个并联关系，同类队列中存储同类患者实体，存储实体按先到先服务的排队规则等待输出至医生座席。次序1中该队列实体根据接受到的该系统状态信息(心理效用约束)，判断是否选择退出系统，各队列的实体以P(0.03)的速率退出。当实体作出相应的选择后，为仍在系统的实体添加相应的标签，统计实际进入系统的泊松流。

c）当被标记的实体进入各自队列的等待暂缓区时，会触碰各队列患者人数统计条件，次序2判断该队列是否超过存储阈值 $L _ { \tilde { \imath } } ^ { \mathrm { m a x } }$ ，且另一队列保持在储存阈值 $L _ { i } ^ { \mathrm { m i n } }$ 以内时，在超过存储阈值数量之外的实体中，判断该队列实体的转移意愿。若满足条件的实体将该实体以P(0.232)的频率转移至另一队列的暂存区继续等待接受处理，否则直接进入次序3进行处理。

d)次序3实体直接进入该队列的等候暂存区等待服务。各队列暂存区的实体等待输入各医生座席，当该队列的平均队长及溢流队列的平均队长达到阈值时，计算实体的等待时间是否超过上限判断实体是否选则退出系统或仍在暂存区等待接受服务。具体路由规则如表3所示，以普通患者为例仅列举部分Process流程，专家患者以相同的逻辑规则进行仿真。

Tab.3Routing rules   

<html><body><table><tr><td>实体</td><td>位置</td><td>操作加工</td><td>次序</td><td>输出</td><td>目的地</td><td>规则</td></tr><tr><td>病人</td><td>医院</td><td>Wait P (5.6,1.2)</td><td>1</td><td>病人</td><td>挂号系统</td><td>Until Full 1</td></tr><tr><td>病人</td><td>挂号系统</td><td>Wait U (3.2,0.3)</td><td>1</td><td>患者</td><td>分诊台</td><td>Random 1</td></tr><tr><td rowspan="5">患者</td><td rowspan="5">分诊台</td><td></td><td>1</td><td>普通</td><td rowspan="2">普通患者</td><td rowspan="2">First Available 1</td></tr><tr><td>Wait N (2.0.8) Split as 普通患者</td><td></td><td>病人</td></tr><tr><td>and 专家患者</td><td></td><td>专家</td><td></td><td></td></tr><tr><td></td><td>2</td><td>病人</td><td>专家患者</td><td>First Available 1</td></tr><tr><td></td><td>1</td><td>普通</td><td>心理</td><td>Probability</td></tr><tr><td rowspan="5">普通 病人</td><td rowspan="5"></td><td>If clock (min)>=U (100,10)</td><td></td><td>病人</td><td>效用退出</td><td rowspan="2"></td></tr><tr><td></td><td></td><td>普通</td><td></td></tr><tr><td>普通患者 and contents(普通队列)>=80</td><td>2</td><td>病人</td><td></td><td>普通队列 If Load Request 1</td></tr><tr><td>then route 1 else route 2 and rout 3</td><td>3</td><td>普通</td><td></td><td></td></tr><tr><td></td><td></td><td>病人</td><td>溢流队列</td><td>If Join Request 1</td></tr><tr><td>普通</td><td>心理</td><td>P(0.03)</td><td></td><td>普通</td><td></td><td>Most Available</td></tr><tr><td>病人</td><td>效用退出</td><td></td><td>1</td><td>病人</td><td>Exit1</td><td></td></tr><tr><td>普通</td><td></td><td>If clock (min)> =U (120,15)</td><td>1</td><td>普通</td><td>普通</td><td>First Available 1</td></tr><tr><td>病人</td><td></td><td>普通队列 and contents(普通队列)>=150</td><td></td><td>病人 普通</td><td>医生座席 理性</td><td></td></tr><tr><td></td><td></td><td>then route 2 else route 1</td><td>2</td><td>病人</td><td>效用退出</td><td>Probability</td></tr><tr><td>普通</td><td>溢流患者</td><td></td><td></td><td>普通</td><td></td><td></td></tr><tr><td>病人</td><td></td><td>Wait P (4.3,1.2)</td><td>1</td><td>病人</td><td></td><td>专家队列 If Load Request 1</td></tr><tr><td>普通</td><td>普通</td><td>If clock (min)> =U (150,25) then</td><td></td><td>普通</td><td></td><td></td></tr><tr><td>病人</td><td></td><td></td><td>1</td><td></td><td>Exit2</td><td>Most Available 4</td></tr><tr><td></td><td></td><td>医生座席 wait E(5)min else wait E(4)min</td><td></td><td>病人</td><td></td><td></td></tr><tr><td>普通</td><td></td><td></td><td></td><td>普通</td><td>专家</td><td></td></tr><tr><td></td><td>专家队列</td><td>Wait U (4,1)</td><td>1</td><td></td><td></td><td>First Available 1</td></tr><tr><td>病人</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>病人</td><td>医生座席</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>普通</td><td></td><td></td><td></td><td>普通</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>专家</td><td>If clock (min)<=U (150,20) then</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>1</td><td></td><td>Exit3</td><td>Most Available 4</td></tr><tr></table></body></html>

# 3.2 仿真结果分析

实验与仿真环境均为Windows10，采用LINGO18.0和ProModelversion7.0版本的软件求解实现。为了证明仿真结果的有效性，选择LINGO求解器求解传统排队模型与其对比分析。由于LINGO软件适用于线性或非线性优化求解等问题的求解，无法将溢流排队模型的约束进行有效量化。因此通过设置3组不同患者到达率(分别为 $\lambda _ { 1 } { = } 1 2 . 9 7 6 , \lambda _ { 2 } { = } 8 . 2 4 9$ 的0.8、1和1.2倍)，横向对比随着患者到达率的增加，不同时刻患者的平均等待时间的变化情况(仅列举 $t { = } 1 2 0 , 2 4 0 , 3 6 0$ 的结果)。运行结果如表4所示，计算理论求解值和仿真模拟值之间平均差值为9.6444E-02，平均方差为2.386E-03。综上分析，仿真模拟的数据结论较为准确。

由表4在三个模型求解结果可看出，随着患者到达率的正向增加，其平均等待时间也随之延长，测试结果未出现异常值，变化趋势亦符合现实情况。传统模型与优化模型2组数据结果横向对比显示，相同时刻，到达率保持一定的条件下，优化后的平均等待时间表现出明显的优势，说明该系统的优化路由及约束起到了正向影响的作用。

表4理论-仿真求解

表3路由规则  
Tab.4Theory-simulation solution   

<html><body><table><tr><td>模型求解</td><td>到达率</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td></tr><tr><td>Lingo</td><td>λ=10.3808，λ=6.5992</td><td>0.329</td><td>1</td><td>0.469</td><td>1</td><td>0.537</td><td>1</td></tr><tr><td>理论</td><td>λ=12.976， =8.249</td><td>0.584</td><td>1</td><td>0.753</td><td>1</td><td>0.679</td><td>1</td></tr><tr><td>求解</td><td>λ=15.5712，=9.8988</td><td>0.713</td><td>1</td><td>0.825</td><td>1</td><td>0.903</td><td>1</td></tr><tr><td rowspan="2">传统模型 仿真</td><td>λ=10.3808, =6.5992</td><td>0.282</td><td>1</td><td>0.390</td><td>1</td><td>0.467</td><td>1</td></tr><tr><td> =12.976, =8.249</td><td>0.451</td><td>1</td><td>0.563</td><td>1</td><td>0.659</td><td>1</td></tr><tr><td></td><td>λ =15.5712, =9.8988</td><td>0.575</td><td>1</td><td>0.716</td><td>1</td><td>0.821</td><td>1</td></tr><tr><td rowspan="3">优化模型 仿真</td><td>λ=10.3808,=6.5992</td><td>1</td><td>0.097</td><td>1</td><td>0.153</td><td>1</td><td>0.193</td></tr><tr><td>λ =12.976, =8.249</td><td>1</td><td>0.134</td><td>1</td><td>0.201</td><td>1</td><td>0.258</td></tr><tr><td>λ =15.5712, =9.8988</td><td>1</td><td>0.232</td><td>1</td><td>0.294</td><td>1</td><td>0.407</td></tr></table></body></html>

注：表4 中第一行的1.2...,6分别指 $\Gamma _ { 1 } ( 1 2 0 )$ ， $\Gamma _ { 2 } ( 1 2 0 )$ ， $\Gamma _ { 1 } ( 2 4 0 )$ ，$\Gamma _ { 2 } ( 2 4 0 )$ ， $\Gamma _ { 1 } ( 3 6 0 )$ ， $\Gamma _ { 2 } ( 3 6 0 )$ ，单位/小时。

在控制变量的条件下，分别仿真了传统的医院排队模型和基于患者双向溢流并增加考虑患者因心理或理性因素退出系统的医院排队模型，运行周期为 $4 8 0 \mathrm { m i n }$ ，仿真次数为20次，当置信水平为 $90 \%$ 时，以保证系统可达到平衡稳定的状态。

图3为优化前后各队列输出患者人数对比图。从图3中可以得出两点结论：其一，优化后普通和专家队列的输出患者人数的总和大于传统模型，说明单位时间内医院服务的总人数有明显的提升。其二，在传统的医院排队模型中专家队列输出的患者人数远大于普通队列，这种现象可能导致专家队列的堵塞率急增或普通医生座席空闲等情况发生。优化后的模型使普通和专家队列的输出患者人数达到一个相对均衡的状态且两个队列的曲线渐进重合，可以很好的避免以上现象的发生。

![](images/836cb38b5e19978c3da0066c7a7010c0cc071f252a0aa3f44a6c0a7576e03f53.jpg)  
图3优化前后各队列输出患者人数对比  
Fig.3Comparison of the number of output patients in each queue before and after optimization

图4显示了优化前后各队列退出患者人数对比情况，传统的专家和普通队列患者退出人数均大于优化后的退出人数(此患者退出人数包括因心理和理性因素的总和)。原因如下：其一，优化后的排队模型提高了医生座席的利用率，相对应的减少了不同阶段各队列患者的等待时间，因此整体降低了患者因不耐烦或等待时间过长等因素而考虑退出系统的数量。其二，优化后的模型给患者提供了多项选择机会和服务渠道，而不是只能单一地让患者选择退出系统或进入下一时间段的服务等待区，从而更加灵活和人性化地解决了患者看病的需求，因此患者退出人数综合有所降低。

图5显示新型双向溢流排队模型中普通和专家队列分别溢流的患者人数。由仿真结果可知，普通队列向专家队列溢流的患者人数在实时动态下均大于专家队列向普通队列溢流的患者人数，说明在现实情景中挂号专家门诊的患者大部分是由于病情需要，其认为专家医生诊治效果更精准，因为等待时间过长、队列拥挤或其他因素选择溢流去普通队列的患者可能是由于心理需求而非病情必须选择专家队列；相反，若普通队列的患者发现当前队列相较于专家队列需要花费更长的等待时间时，其愿意花费更高的费用溢流去专家队列，以达到节约时间成本的目的。

![](images/b6d3ea3948e5ae269b794579a0914b7b16a86922de5830466a88abcbef8cb476.jpg)  
图4优化前后各队列退出患者人数对比

![](images/b91e80090483c3986730f6787f23e158d2a84b355c4c30057983613933da541f.jpg)  
Fig.4Comparison of the number of patients who dropped out of each queue before and after optimization

Fig.5Comparison of overflow patients in general and expert queues图6为优化前后普通和专家队列平均等待长度对比图。由图6可知，在传统排队模型中普通和专家队列的平均等待长度分别稳定在30\~40人和10\~20人左右，而增加考虑患者双向溢流这一渠道后，普通和专家队列的平均等待长度均有明显的下降趋势。普通队列平均等待时间控制在0\~5人的区间范围内，专家队列的平均等待时间稳定状态处于0\~6人左右，有几处明显的增加是由于普通队列溢流到专家队列所导致，因此结果处于合理范围的波动。

38 Hwl  
25 15  
8 新型普通队列平均等待长度 Y/■传统普通队列平均等待长度 人10  
15  
15  
0 100 200 300 400 500 0 100 200 300 400 500时间/分钟 时间/分钟  
(a)普通队列平均长度对比图 (b）专家队列平均长度对比图

![](images/08af0b283ed90e0e5b558104d7f9a0f031a532a079da469ae7ed2ac1ab593b1a.jpg)  
图5普通和专家队列溢流患者对比  
图6优化前后普通和专家队列平均长度对比  
Fig.6Comparison of the average length of general and expert queues before and after optimization   
(a）普通队列平均等待时间对比图(b)专家队列平等待时间对比图 图7优化前后普通和专家队列平均等待时间对比 Fig.7Comparison of the average waiting time of general and expert queues before and after optimization

图7为优化前后普通和专家队列患者平均等待时间对比图。由图7可知传统的医院排队模型中普通和专家队列患者的平均等待时间均处于20\~40分钟内无规律剧烈波动，系统的稳定性不佳，突发大幅度增加平均等待时间的现象及可能增加患者的不耐烦因素，引起医患矛盾等事件的发生。优化后的排队模型将各队列患者的平均等待时间均控制在10 分钟内，相比于传统排队模型，患者的平均等待时间有了明显的下降，且各队列平均等待时间的曲线波动变化情况相对稳定，可以看出新型的排队模型的系统稳定性更好。

# 4 结束语

本文探讨了在考虑医生因疲劳会改变服务速率的基础上建立双向溢流的排队模型。首先对患者就诊排队问题和路由规则进行描述分析；其次运用排队理论及拟生灭过程对各评价指标进行量化表达，并对该排队系统相应的容纳量、患者决策、退出率等因素进行约束；最后运用ProModel软件对比分析，并应用LINGO理论求解证明仿真的有效性。研究发现在控制变量的条件下，新型排队模型不仅能减少患者在整个就诊过程中的等待时间，还能合理均衡医患数量配比和各门诊医生的服务强度。该模型为患者在排队过程中因队列或等待时间过长而只能单一选择退出系统提供了新的渠道。

本文优化结果对探讨科学有效地改善就诊流程提供了科学参考依据，同时该模型的思路可运用于分级诊疗体系，医疗机构双向转诊，城市突发公共卫生事件的应急调度等现实问题的优化。基于本文的研究内容，还有很多角度值得进一步拓展性研究，比如：从智慧医疗或“互联网 $+$ ”医疗的角度出发考虑双向溢流系统；运用强化学习或聚类[24]等算法设置患者的决策约束等；还可增加考虑患者的差异化偏好、病情的严重程度、医疗成本等更为贴近实际情况的溢流约束条件等。

# 参考文献：

[1]中国人民国共和国中央人民政府．国家卫生健康委员会就2019年我 国医疗服务与质量安全有关情况举行例行发布会[EB/OL].(2020. 10.17）[2021-9-27].http://www.gov.cn/xinwen/2020- 10/17/content_5551912.(Central People's Govermment of the people's Republic of China.The National Health Commission held a regular press conference on the quality and safety of medical services in China in 2019 [EB/OL].(2020.10.17) [2021-9-27].http://www.gov.cn/xin wen/2020- 10/17/content_5551912.)   
[2]杜燕平，母建层．流程优化在医院门诊管理中的实践与改进[J]．现 代医院,2020,20 (06): 827-829.(Du Yanping,Wu Jianceng.Practice and improvement of process optimization in hospital outpatient managemen [J].Modern Hospitals,2020,20 (06): 827-829.)   
[3]Joseph JW,Davis SR,Wilker EH,et al.Emergency physicians'active patient queues over the course of a shift [J].American Journal of Emergency Medicine,2020,46(8): 254-259.   
[4]Andersen AR,Nielsen B F,Reinhardt LB,et al.Staff optimization for time-dependent acute patient flow [J].European Journal of Operational Research,2019,272(1): 94-105.   
[5]Zhang A,Zhu XM,Lu Q,et al. Impact of Prioritization on the Outpatient Queuing System in the Emergency Department with Limited Medical Resources [J]. Symmetry Basel,2019,11 (6):796-797.   
[6]Barros O，Weber R，Reveco C.Demand analysis and capacity management for hospital emergencies using advanced forecasting models and stochastic simulation [J]. Operations Research Perspectives, 2021,doi: https://doi.org/10.1016/j.orp.2021.100208.   
[7]Wu XD,Li Jand Chu C H.Modeling multi-stage healthcare systems with service interactions under blocking for bed allocation [J].European Journal of Operational Research,2019,278 (3): 927-941.   
[8]李凌洋，李晨阳．基于排队论的医院收费窗口优化设置[J].河北大 学学报：自然科学版，2020,40(05):449-453.(Li Linyang，Li Chenyang.Optimization of hospital toll window seting based on queuing theory [J]. Journal of Hebei University: Natural Science Edition, 2020,40 (05):449-453.)   
[9]荆彤，叶晴晴，张晓亮等．带有工作故障与顾客止步的 M/M/1 重试 排队性能分析[J].重庆师范大学学报：自然科学版，2020,37(05): 1-9.(Jing Tong,Ye Qingqing, Zhang Xiaoliang,et al. The performance analysis of a retrial M/M/l queue with working breakdowns and balking [J].Journal of Chongqing Normal University: Natural Science,2020,37 (05): 1-9.)   
[10]羊英，李静．基于排队行为的专家门诊预约中患者决策建模研究 [J]．重庆师范大学学报：自然科学版，2019,36(01):21-28.(Yang Ying,Li Jing.Study on patients’decision making modeling in specialist outpatient appointment based on queueing behavior [J]. Journal of Chongqing Normal University: Natural Science,2019,36 (01): 21-28.)   
[11] He QD, Huo JZ,Pan Y.The optimization model for the service process of stomatology department via DES simulation [J].Cogent Business & Management,2020,7(1): 78-81.   
[12] Kang DY, Cho,KJ,Kwon O,et al. Artificial intelligence algorithm to predict the need for critical care in prehospital emergency medical services.Scandinavian Journal of Trauma, Resuscitation and Emergency Medicine,2020,28 (8),325-331.   
[13]刘健，赵洪款，刘思峰．基于顾客不公平规避的服务定价研究[J]. 中 国管理科学,2018,26 (02):46-53.(Liu Jian,Zhao Hongkuan,Liu Sifeng.A study of service pricing with unfairness averse customers [J]. Chinese Journal of management science,2018,26 (02): 46-53.)   
[14]陈顶，方志耕，刘思峰．可修排队系统备件灰色生灭预测模型[J]. 系统工程理论与实践,2020,40 (05):1326-1338.(Chen Ding,Fang Zhigeng,Liu Sifeng.Grey BD prediction model for spare parts of repairable queuing system [J]. Systems Engineering—Theory&Practice, 2020,40 (05): 1326-1338.)   
[15]卢宜玲，李军祥，齐缘．疫情下考虑疲劳度的可变服务率排队模型 [J/OL].上海理工大学学报，2021.(2021-09-30)[2022-02-23]. https://kns.cnki.net/kcms/detail/31.1739.t.20 210929.1137.001.html (Lu Yiling,Li Junxiang,Qi Yuan.Queuing model with variable service rate considering fatigue under epidemic situation [J/OL].J.University of Shanghai for Science and Technology2021.(2021-09-30) [2022-02-23]. https://kns.cnki.net/kcms/detail/31.1739.t.20210929.1137.001.html)   
[16]孙敬煊，高郡，张峻川等．带接触匹配的M/M/C 排队模型[J].数学 的实践与认识,2020,50(19):186-192.(Sun Jingxuan,Gao Jun,Zhang Junchuan,et al.M/M/C queuing model with the state of matching and abandoning[J].Mathematics in practice and theory,2020,50 (19):186- 192.)   
[17]张立帆，焦朋朋，司铭锴．城市道路落客区车辆延误模型[J]．系统 仿真学报,2020,32(09):1839-1846.(Zhang Lifan,Jiao Pengpeng,Si Mingkai.Delay model of vehicles at urban road drop-off area[J]. Journal of System Simulation,2020,32 (09):1839-1846.)   
[18]王静雯，李华强，李旭翔等．综合能源服务效用模型及用户需求评 估[J].中国电机工程学报,2020,40(02):411-425.(Wang Jingwen,Li Huaqiang,Li Xuxiang,et al.utility model and demand assessment method of integrated energy service [J].Proceedings of the CSEE,2020, 40 (02): 411-425.)   
[19]Mariani F,Polinesi G,Recchioni M C.A tail-revisited Markowitz meanVariance approach and a portfolio network centrality [J]. Computational Management Science,2022,DOI:10.1007/S10287-022-00422-2.   
[20]徐红利，刘煜昊，徐薇等．考虑决策惯性的随机网络路径选择与交 通流分配模型[J]．系统工程理论与实践，2021,41(04):1010-1017. (Xu Hongli,Liu Yuhao,Xu Wei,et al.Route choice model in stochastic network and its application in traffic assignment with consideration to travelers’decision inertia [J]. Systems Engineering—Theory&Practice, 2021,41 (04): 1010-1017.)   
[21]于淼，宫俊，唐加福等．考虑顾客耐心的呼叫中心等待提示决策模 型[J].工业工程与管理,2015,20(06):108-113.(Yu Miao,Gong Jun, Tang Jiafu,et al.Decision model of delay information for call centers based on consideration of customers’patirnce [J].Industrial Engineering and Management,2015,20 (06): 108-113.)   
[22]李军祥，藏万斌．基于耐心阈值下联络中心放弃率的仿真研究[J]. 系统仿真学报,2021,33(01):169-179.(Li Junxiang,Zang Wanbin. Simulation Research on Abandonment Rate of Contact Center Based on Patience Threshold [J]. Journal of System Simulation,2021,33 (01): 169-179.)   
[23]李武强，刘德智，许晓晴.提供补救服务情境下专家薪酬、服务优化 对服务策略的影响研究[J].管理学报,2020,17(10):1554-1563.(Li Wuqiang,Liu Dezhi, Xu Xiaoqing.The effect of expert wages and service optimization on service policy when providing remedial service [J]. Chinese Jourmal of Management,2020,17 (10): 1554-1563.)   
[24]耿秀丽，王著鑫．考虑用户兴趣分析的差分隐私方案推荐[J]．计算 机应用研究，2022,39(02):474-478.(Geng Xiuli，Wang Zhuxin. Recommendation of differential privacy scheme considering user interest analysis [J].Application Research ofComputers,2022,39 (02): 474-478.)