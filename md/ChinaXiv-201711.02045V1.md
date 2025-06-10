# 协同创新中知识供需系统的模拟研究

吴江陈君张劲帆(武汉大学信息管理学院武汉 430072)

摘要：【目的】探讨协同创新环境下知识型团队的交互对团队绩效的影响。【方法】采用多智能体建模仿真方法，从知识管理微观层面构建知识供需系统，将时间成本和资金成本作为工作绩效的评价指标，基于 PythonNetworkX实现该系统。【结果】大规模的组织在降低创新成本上比小规模的组织有优势；无标度结构的组织完成任务耗时长并且成本高；组织中个体的连接邻域数增加并没有单调地提升组织的创新效率，当平均领域数超过某个阈值后创新成本开始增加。【局限】未考虑人与人之间的互动在协同创新中的优化设置。【结论】基于多智能体建模的知识供需系统从微观层面对知识型团队的知识整合过程进行模拟，有助于认识团队内部知识的管理，为组织提升知识利用效率，降低创新成本提供新的视角。

关键词：协同创新知识供需系统多智能体仿真复杂网络计算实验 分类号：G350

# 1引言

移动互联网时代以手机APP为输出形式的服务创新层出不穷。随着APP数量的快速增长，组织需要在较短时间内对市场做出响应。知识型团队想要获取竞争优势，应当充分地调动组织内部和外部的资源，有效地整合不同知识背景的人，以降低创新的时间成本和资金成本。如何实现较高水平的协同创新需要进行深入研究。

本文采用多智能体仿真方法从知识管理的微观层面模拟组织内部知识供求双方的匹配过程、项目实现过程中的知识利用，通过计算机模拟实现人和项目交互的知识供需系统。体现了“人和项目在知识维度上的匹配-项目的实现-知识再匹配-项目再实现"这样一个循环的、动态的组织协同作业过程。组织中个体所在的网络拓扑结构对工作绩效具有决定作用[1]，本文将人所处的环境设置为4种典型的网络：随机网络、小世界网络、无标度网络、规则网络，着重分析网络平均度、网络规模等对组织创新绩效的影响，以及个体在4种拓扑结构下实现高水平知识协同的异同。

# 2相关文献综述

# 2.1 协同创新

随着互联网技术的发展，创新环境也发生了变化朝着2.0范式发展[2]。知识经济时代知识本身的复杂性(知识结构复杂性、知识载体复杂性)和人的复杂性(表现在人的知识活动以及人之间的社会联系)都加大了组织知识管控的难度。复杂的协同创新系统无法通过线性分析法得到完全的分析，需要从整体和协作角度探究知识创新的机制。

知识创新中最具活力和创造力的部分就是协同创新[3]，协同创新是基于竞争与合作的资源匹配的过程，可以从知识整合和互动两个维度分析[4]。Henderson 等[5]首次完整地阐述了知识整合的过程：在产品开发过程中，当组织知识受到外部市场的需求拉动，会形成结构性知识。整合维度包括知识、资源、行为和表现。

互动维度指个体之间的知识共享、资源的优化配置、知识活动的同步。

从协同创新的知识整合范围上划分，可以分为组织间和组织内。协同创新是复杂的创新组织方式，其关键是形成以大学、企业、研究机构为核心要素，以政府、金融机构、中介组织、创新平台、非营利性组织等为辅助要素的多元主体协同互动的网络创新模式，通过知识创造主体和技术创新主体间的深入合作和资源整合，产生系统叠加的非线性效用[。组织间协同创新相当一部分理论和实践都是在产学研基础上进行。组织内协同创新强调组织内部资源的优化配置，实现资源利用的效益最大化。吴江等7通过多智能方法模拟研究交互记忆系统对知识型团队中人群和工作互动的影响，模拟研究过程中人系统和物系统外部环境的激励环境作为一个重要的影响因素。张古鹏[8]从社会网络视角出发探究个体所在的交互网络环境的周期性动态演化对于个体创新绩效的影响。徐升华等[9]运用系统动力学方法建立组织内部知识整合的量化模型。将工作绩效和创新绩效作为组织个体行为评价指标的计算实验成果已经较多，而从协同创新视角构建模拟系统的成果还很少。

# 2.2 组织内部协同创新的分析基础 -知识供需系统

知识供需研究包含两类对象：知识需求体和知识供给体。基于知识维度的知识供给双方的有效匹配是知识得到合理利用的前提，在知识管理和人工智能相关研究中都有较多的涉及。郭韧等[10]从知识特性的知识供需匹配、基于信息系统建设的知识供需匹配、基于知识服务知识供需匹配三个方面，梳理了知识供需匹配的已有研究。刘景方等[1构建基于本体的任务和知识个体匹配模型，提出一种综合改进的概念义相似度计算方法，用以提高概念间的语义相似度计算的准确性。本文的研究重点不在于探究知识供求双方的匹配机理，而是把知识供求匹配作为知识供需模型中的一个重要环节。

本文研究组织内部的协同创新，为了对组织内部知识供给智能体和知识需求智能体的知识交互过程进行分析，本文提出"知识供需系统”，主要过程包括"人和项目在知识维度上的匹配-项目的实现-知识再匹配-项目再实现”，体现了一个循环的、动态的协同作业过程。组织作为一个复杂的社会技术系统，包括本身存在联系的人智能体集合，以及各种资源、设备和知识。从知识维度上看，组织就是一个复杂的知识供需系统，核心部分包括作为知识供给智能体(人)，知识需求智能体(项目、任务)，以及贯穿知识供需系统各项流程的知识智能体(技能)等。

# 3组织计算模型建模

计算和数学方法在组织学理论发展过程中扮演了重要的角色[12]。计算和数学模型有助于对组织形式、组织过程、集体决策、一致性协商、资源配置、组织结构等问题进行界定。多智能体仿真是一种自下而上的仿真范式，通过研究个体的特征和行为建模，将带有特征和行为的个体看作是智能体。个体特征映射为智能体属性，个体行为映射为方法[13]。最后建立仿真引擎连接起这些智能体驱动系统运行。利用智能体自治、推理、通讯和协作机制，模拟群体中相互独立又相互作用的现象，从而发现群体的整体结构和功能[14]。本文使用多智能体建模方法对不同网络类型下知识整合的基本问题进行模拟分析，对协同创新中组织的知识管理提供新的视角。

# 3.1 知识供需系统

知识供需系统(Knowledge Supply& Demand System,KSDS)包含4种智能体：开发者、项目、项目团队、网络环境，图1描述了4类智能体之间的交互。

![](images/8d4440f8986ae846559b0064044c748301ed2d9d0872226361e7fcd662887651.jpg)  
图1协同创新的组织内部结构

个体是知识点的集合，个体的知识集合代表其知识背景。项目可以拆分成多个任务，任务是知识点集合。任务的知识结合代表对知识的需求，这样项目就是存在一定分布规律的知识需求文档，只有当每个需求都得到实现后项目才算完成。个体知识集合在微观层面上和项目的知识需求发生交互，基于规则选择个体组建项目团队，以团队为作业单元完成对应项目。知识供需系统中项目的实施过程是由项目的知识需求出发，以团队形式动态、持续地填充知识需求文档的过程

# 3.2 模型假设

在符合实际情况的前提下，笔者简化了模型表示，提出以下基本假设：

(1）项目均由开发者动态组建的项目团队协作开发实现;(2）开发者的技能和项目的技能需求均由10 个元素组成的有序集合表示;(3）一个项目由10个任务组成，分别对应10项技能的工作量;(4）一个开发者在一个时间单元只能参与一个项目中的一个任务，负责任务完成后可以参与到项目中其他任务。当项目中所有任务均完成后，团队成员才有机会参与到其他项目。

# 3.3 规则定义

知识供需系统中，项目分配和实施是完全自组织的过程,开发者、项目和团队基于以下规则进行交互：

# (1）规则1:组建团队

在项目团队组建初期和实施过程中都需要从网络环境中补充人员配置。团队组建初期，开发者群体和项目在系统运行过程中不断地交互，当开发者的技能至少满足项目技能需求的一项(开发者的某项技能程度达到项目的最低要求)，这时候开发者和项目的匹配度大于等于1，可以将个体纳入到项目团队中，笔者提出匹配度计算公式如下：

$$
\mathrm { S K _ { j i } } { \geqslant } \mathrm { S K _ { p i } } \quad ( \mathrm { i } { = } 0 , 1 , \cdots , 9 ) \qquad \mathrm { M D } = \mathrm { M D } + 1
$$

其中,SK表示有序的技能列表，包含10项技能。当j表示开发者个体， $\mathrm { S K _ { j } }$ 就指代个体j对10项技能的掌握程度, $\mathrm { S K _ { j i } }$ 指个体j第i项技能的掌握程度。当 $\mathrm { S K _ { j i } }$ 为0时，表明个体j不具备这项技能。当p表示开发者个体, $\mathrm { S K _ { \mathrm { p } } }$ 就指代项目 $\mathsf { p }$ 的在开发过程中的技能需求,$\mathrm { { S K _ { \mathrm { { p i } } } } }$ 指项目p第i项技能上的要求。当 $\mathrm { { S K _ { \mathrm { { p i } } } } }$ 为0时,表明项目p在实施过程中，不需要第i项知识。MD(MatchDegree)表示匹配度。

项目实施过程中，根据项目中任务的完成情况，匹配度计算做出调整，仅匹配项目中还未完成任务，即从开发者中筛选出能够匹配未完成任务的技能需求的个体，笔者提出公式(2)如下:

ifSKji $\geqslant$ Skpiand $\mathrm { W p i } > 0 \quad ( \mathrm { i } = 0 , 1 , \cdots , 9 ) \quad \mathrm { M D } = \mathrm { M D } + 1$

其中, $\mathrm { S K _ { j i } }$ 指个体j第i项技能的掌握程度; $\mathrm { W _ { p } }$ 是项目 $\mathsf { p }$ 各项技能所对应的所需完成的工作量。 $\mathrm { W _ { p i } }$ 指项目 $\mathfrak { p }$ 中第i项技能的工作量，当 $\mathrm { W _ { p i } } { > } 0$ 表示这项任务还未完成，当 $\mathrm { W _ { \mathrm { p i } } { \leqslant } 0 }$ 表明任务已完成。

(2）规则2：团队内部任务分派

一个项目可以分为10个任务，每个任务由开发者个体共同负责。假设：个体在一个项目中可以参与到多个不同的任务，但在一个时间单元只能负责一个任务。当个体负责的任务完成后，将继续参与到项目的其他任务中，直到项目中所有的任务都完成为止。在给每个任务指派负责人时，每个任务对应的是一项技能的工作量，从资源优化配置的角度，单个任务总是寻找项目成员中在这项技能上掌握程度最高的个体。和基于项目技能需求的组建团队过程不同，在匹配任务过程，要求负责人在指定任务的技能熟练程度是当前团队配置中最高的，笔者提出公式(3)如下:

$$
\mathrm { S K _ { j i } = m a x ( S K _ { k i } ) } \qquad \mathrm { j \in M _ { P } , k \in M _ { P } }
$$

其中, $\mathrm { S K _ { j i } }$ 指个体 $\mathrm { j }$ 第i项技能的掌握程度, $\mathbf { M } _ { \mathrm { p } }$ 是项目 $\mathsf { p }$ 的成员列表。若个体j是任务i的负责人，必须满足公式(3)。

(3）规则3：项目实施

项目实施过程中，每天项目中每个任务的工作量都会减少，笔者提出公式(4)如下:

$$
\mathrm { W _ { p i } ( t + 1 ) = W _ { p i } ( t ) - \sum { S K _ { j i } } \qquad j \in M _ { P } }
$$

其中, $\mathrm { W _ { p i } ( t ) }$ 指项目 $\mathsf { p }$ 的第i个任务在t时间的剩余工作量, $\mathrm { S K _ { j i } }$ 指个体 $\mathrm { j }$ 第 $\mathrm { ~ i ~ }$ 项技能的掌握程度，同时也表示开发者运用这项技能每天能够完成的工作量。 $\mathbf { M } _ { \mathrm { p } }$ 是项目 $\mathfrak { p }$ 的成员列表。

# 3.4 环境因素

个体的行为受到环境因素的影响，笔者假设环境是相对稳定的，提供固定的条件。这里环境因素指网络结构，可以从网络节点(个体)的属性和网络性质两个方面考量，本文着重考虑网络性质。

(1）网络性质包含：网络规模由行动者的数量表示，网络的平均度反映行动者之间联系的紧密程度。

(2)假定知识供需系统中个体都是遵循规则的自组织行为，环境中必然存在激励机制使得个体的行为在微观上可控，重复执行智能体行为完成一个又一个的项目。

# 3.5 评价指标

本文采用项目开发的平均时间成本和平均资金成本作为评价组织的协同创新能力的指标。

(1）平均时间成本 $\mathrm { T _ { a v e r a g e } }$ ：组织完成项目开发工作的平均时间，笔者提出公式(5)如下:

$$
\mathrm { { T _ { a v e r a g e } } = \sum _ { p = 0 } ^ { N P - 1 } ( E T _ { p } - S T _ { p } ) / N P }
$$

其中, $\mathrm { E T _ { p } }$ 是项目 $\mathsf { p }$ 的完成时间, $\mathrm { { S T _ { p } } }$ 是项目p第一次成功匹配成员的时间，NP是完成的项目数量。

(2)平均资金成本 $\mathrm { C _ { a v e r a g e } }$ ：组织完成项目开发的平均资金，笔者提出了以下公式:

$$
\mathrm { C _ { a v e r a g e } = \frac { \sum _ { p = 0 } ^ { N P - 1 } \sum _ { j } ( E T _ { p j } - S T _ { p j } ) \times S _ { j } } { N P } } \qquad \mathrm { j \in M _ { p } }
$$

其中, $\mathrm { E T _ { p j } }$ 是个体j参与项目的时间, $ { \mathrm { S T _ { p j } } }$ 是个体j从项目 $\mathsf { p }$ 中离开的时间，也是项目完成的时间。 $\mathrm { S _ { j } }$ 表示个体j的薪资, $\mathbf { M } _ { \mathrm { p } }$ 是项目 $\mathfrak { p }$ 的成员列表，NP 是完成的项目数量。

# 3.6 模拟引擎

模拟引擎整合了智能体和网络环境，使得系统依据前面制定的规则运行，步骤如图2所示：

![](images/06f927ebfaa31902f485e24f4436c6bbde035e529b07e3d4e9768e94da9ae77e.jpg)  
图2仿真流程图

(1）初始化网络环境：网络的平均度，开发者数量和项目数量，以及初始化开发者(初始状态 available)和项目(初始状态undone);

(2）组建项目团队：在团队组建初期，从网络环境中遍历开发者，基于规则1从开发者中匹配出一个符合项目技能需求的个体，形成项目负责团队，项目状态变为processing，团队成员状态变成occupied；从项目成员的邻域节点中继续匹配符合条件的个体;

(3）基于规则2给团队中的成员指定负责的任务，成员状态改为working;(4）项目实施过程，基于规则3改变每项任务的工作量;(5）若单个项目完成，计算项目的时间成本和资金成本，将项目成员的状态改为available;(6）系统终止运行条件：所有项目完成。基于公式(5)和公式(6)计算每个项目完成的平均时间和资金成本。

# 3.7 知识供需系统的实现

基于Python语言实现KSDS模拟系统，其中交互网络环境通过复杂网络建模工具包NetworkX[15]产生。通过调用NetworkX模块的不同方法构造出特定的网络结构(随机网络、小世界网络、无标度网络、规则网络)。通过设置网络生成的参数调整特定交互网络的特征，本文分析网络平均度、网络规模等对组织创新绩效的影响。例如，随机网络的平均度等于节点数和连接概率的乘积，在实验中通过控制网络的节点数和连接的概率就可以确定交互网络环境的平均度。

# 4实验与结果分析

对开发者的技能列表和项目技能需求列表均为随机产生，探讨知识智能体所处的网络环境对协同创新绩效的影响，从时间成本和资金成本反映在4类典型的网络结构下开发者的协作效率。

为了探究网络平均度对项目开发所需时间的影响，实验模拟了4种网络下1000个开发者以团队协作的方式完成100个项目的开发工作，通过调节网络初始化时的参数，使得网络平均度从6逐步增加到100左右(随机网络平均度从6到103，小世界网络：6-104，无标度网络:6-98，规则网络:6-104)。每一组参数设置进行100次反复实验，计算得到单种类型网络下完成单个项目所需的平均时间和平均资金花费，结果如图3和图4所示：

![](images/99dc52559b40ff1c3f2aa92248e8597e6a68d4fa4c05f1773a5bd4b94f14dcae.jpg)  
图3不同网络平均度下项目时间成本

![](images/e07b676dc2e144e05ada218fa244f82966dcb689864d9e14e6c46e75a7e46650.jpg)  
图4不同网络平均度下项目资金成本

当平均度大于20时，开发者处于小世界网络下其协作完成项目开发所需时间成本和资金成本较低。当平均度大于10，无标度网络下所需的时间成本和资金成本较高。随机网络、小世界网络、规则网络下，随着平均度从6开始递增至20时，项目开发所需的时间急剧减少，资金成本也降低。从图4中可以看出平均度在6到100的范围内，随机网络、小世界网络、规则网络存在资金成本的局部最优，最优解在15到30之间。平均度从20到60这个阶段，项目开发所需的时间成本继续平稳地减少，而资金成本总体上呈现增长趋势。平均度大于60之后，时间成本和资金成本在总体上趋于稳定。无标度网络下的协作绩效变化与前面三种类型网络不同。当平均度从6变化到100的过程中，时间成本上存在多个局部最优。平均度从6到40这个阶段，平均资金成本一直在增加，到达40后一个项目开发所需的资金稳定在65000元左右。

为了探究开发者数量对创新绩效的影响，实验设定了项目数量为100。基于前面实验得到的结果，在平均度为15到30范围内存在使得资金成本最低的局部最优，这里将4种类型网络的平均度均设置为16。从图3和图4看出，当平均度为16，且开发者数量为1000，时间成本 $\mathrm { T _ { b a } { > } T _ { e r } { > } T _ { w s } { > } T _ { r e } }$ (ba表示无标度网络，er表示随机网络，ws表示小世界网络，re表示规则网络)，资金成本$\mathrm { C _ { \mathrm { { b a } } } \mathrm { > C _ { \mathrm { { w s } } } \mathrm { > C _ { \mathrm { { e r } } } \mathrm { > C _ { \mathrm { { r e } } } } } } }$ 。下面实验过程首先将开发者个体数量设置1020，以20为步长，逐步提高到2000人，每组参数设置均反复实验100次，取均值。实验结果如图5和图6所示：

![](images/dbc3950387e6e1c15777b069182d7f01f171fe422ee807c0b793f8ffcc19198c.jpg)  
图5不同节点数下项目的时间花费

![](images/2496b31811a8fc0e38e4ac4f7ee3bcbff6ace89b4fd43a5b5200d6fadbd6fe58.jpg)  
图6不同节点数下项目的资金花费

平均度为16，随着节点数增加，当节点数大于1260时，时间成本从 $\mathrm { T _ { b a } { > } T _ { e r } { > } T _ { w s } { > } T _ { r s } }$ 转变为 $\mathrm { T _ { b a } \mathrm { > T _ { w s } \mathrm { > } } }$ $\mathrm { T _ { e r } { > } T _ { r e } }$ ，资金成本从 $\mathrm { C _ { \mathrm { { b a } } } \mathrm { > C _ { \mathrm { { e r } } } \mathrm { > C _ { \mathrm { { w s } } } \mathrm { > C _ { \mathrm { { r e } } } } } } }$ 转变为 $\mathrm { C _ { \mathrm { { b a } } } \mathrm { > C _ { \mathrm { { w s } } } \mathrm { > } } }$ $C _ { \mathrm { e r } } { > } C _ { \mathrm { r e } }$ 。随着开发者数量增多，4种类型网络单个项目开发的时间成本均有不同程度的降低，说明组织规模对于降低项目开发的时间成本有着显著的积极作用。另外，开发者数量对无标度网络下资金成本的影响较小。开发者数量从1020到1300范围内，随机网络和规则网络的资金成本均有平稳的下降过程。

图7是分别在4种网络下10000名开发者完成2000个项目的完成率随时间的变化情况，网络平均度仍旧取16。可以看出在项目初期，都存在一个“完成率 $0 \% ^ { \prime }$ 的阶段。而后，随机网络、小世界网络、规则网络的项目完成数量都出现一个快速增加过程，完成率 $50 \%$ (完成1000个项目的开发工作)只花费不到50天的时间，随后完成的项目继续增加但是增速明显减慢，所有项目完成的时间超过了140天。而无标度网络则在经历了“完成率 $0 \%$ 阶段后就进入到一个项目完成数量平稳增加的过程：完成率为 $3 5 \%$ (完成700个项目)，用时约为40天。完成率为 $70 \%$ ，用时约为80天。可以得到无标度交互网络环境下组织内部每天的产出较恒定。

![](images/efb69d9b92be17cb0241bce114e1b2f5f080d850dd2ebd0ecdaf6decec0cd00d.jpg)  
图7项目完成情况比较

# 5总结和展望

本文以移动互联网为研究背景，从知识整合、创新要素(个体、知识以及创新团队等)的交互为机制，研究个体的交互环境对组织内部协同创新的影响。组织内部的协同创新是对知识合理并且高效的利用，是知识需求、供给双方在知识维度上的有效匹配。本文采用多智能体仿真方法从微观层面构建出知识供需系统，并通过PythonNetworkX实现。实验结果表明，大规模的组织在降低创新成本上比小规模的组织有优势；组织中个体的邻域节点数增加并没有单调地提升组织的创新效率，当平均度超过某个阈值后创新成本开始增加。知识供需系统着重模拟知识供需双方的知识匹配过程，以及组织中个体动态组建团队完成项目的知识协同过程。该系统对于组织提升其知识利用的效率提供了新的视角。

未来研究工作将使用实证数据对本文的结论进行检验和扩展。人之间的互动在团队协作过程中也是重要影响因素，下一步将会在知识供需系统中考虑互动因素，人与人的互动改变交互的网络环境，网络环境又会影响人的协作过程，这样一个动态、协同的创新过程将是未来模拟研究重点。

# 参考文献：

[1]Gao D,Deng X, Zhao Q,et al.Multi-Agent Based Simulation of Organizational Routines on Complex Networks [J]. Journal of Artificial Societies & Social Simulation, 2015,18(3): Article No. 17.   
[2]宋刚，张楠．创新 2.0：知识社会环境下的创新民主化[J]. 新华文摘，2009(10):140-143.(Song Gang，Zhang Nan. Innovation 2.0: Democratizing Innovation in the Knowledge Society [J]. Xinhua News Digest, 2009(10): 140-143.)   
[3]Practitioner P A K M. Knowledge Management:The Collaboration Thread [J]. Bulletin of the American Society for Information Science & Technology,2005,28(6): 8-11.   
[4]Serrano V,Fischer T.Collaborative Innovation in Ubiquitous Systems [J].Journal of Intelligent Manufacturing， 2007, 18(5): 599-615.   
[5]Henderson R M, Clark K B.Architectural Innovation: The Reconfiguration of Existing Product Technologies and the Failure of Established Firms [J].Administrative Science Quarterly,1990,35(1): 9-30.   
[6]陈劲．协同创新与国家科研能力建设[J]．科学学研究, 2011,29(12):2-3.(Chen Jin.Collaborative Innovation and the Construction of National Scientific Research Capacity [J]. Studies in Science of Science,2011,29(12): 2-3.)   
[7]吴江，胡斌，刘天印．交互记忆系统影响人群与工作交 互的模拟研究[J]．管理科学，2009，22(1)：48-58.（Wu Jiang,Hu Bin,Liu Tianyin.A Simulation Study of the Impact of Interactive Memory System on Group-Task Interaction [J]. Journal of Management Sciences,2009, 22(1): 48-58.)   
[8]张古鹏．小世界创新网络动态演化及其效应研究[J]．管理 科学学报，2015，18(6):15-29.(Zhang Gupeng．Dynamic Evolution of Small World Innovation Network and Its Effects [J].Journal of Management Sciences in China,2015,18(6): 15-29.)   
[9]徐升华，尹红丽．组织内部知识整合的系统动力学模型研 究[J]．管理学报,2013,10(6):890-897.(Xu Shenghua,Yin Hongli. Model of Knowledge Integration Based on System Dynamic in the Organization [J]. Chinese Journal of Management, 2013,10(6): 890-897.)   
[10]郭韧，陈福集．知识供需匹配的研究综述[J].情报理论与 实践,2013,36(12):114-118.(Guo Ren,Chen Fuji.Review onMatchingKnowledge Supply and Demand [J].Information Studies:Theory& Application,2013,36(12):114-118.)   
[11]刘景方，邹平，张朋柱．基于本体的任务和知识个体匹配 模型研究[J]．计算机工程与科学，2010，32(9):119-121. (Liu Jingfang,Zou Ping,Zhang Pengzhu. Research on the Matching Model Between Tasks and Knowledge Individuals Based on Ontology [J]. Computer Engineering and Science, 2010,32(9):119-121.)   
[12] Carley K M.Computational and Mathematical Organization Theory:Perspective and Directions [J].Computational & Mathematical Organization Theory,1995,1(1): 39-56.   
[13]Macal C M,North M J.Tutorial on Agent-based Modeling and Simulation [C].In:Proceedings of the 37th Conference on Winter Simulation.2005.   
[14]Carley K M.A Comparison of Artificial and Human Organizations[J].Journal of Economic Behavior& Organization,1996,31(2):175-191.   
[15]Hagberg A,Schult D,Swart P.Exploring Network Structure, Dynamics, andFunctionUsingNetworkX[C].In: Proceedings of the 7th Python in Science Conference.2007.

# 作者贡献声明：

吴江：提出研究思路，设计研究方案和程序，论文修订;  
陈君：编写程序，进行实验，撰写论文;  
张劲帆：编写程序。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版 http://www.infotech.ac.cn。  
[1]陈君．开发者数量影响.xlsx.开发者数量作为自变量的实验结果记录.  
[2]陈君．平均度影响.xls.网络平均度作为自变量的实验结果记录.  
[3]陈君.完成情况比较.xls.4种网络结构下项目完成率结果记录.

收稿日期:2016-04-11   
收修改稿日期:2016-05-31

# A Knowledge Supply-Demand Simulation System for Collaborative Innovation

Wu Jiang Chen JunZhang Jinfan (School of Information Management, Wuhan University, Wuhan 430072, China)

Abstract: [Objective]This paper investigates the network environments facing knowledge-based team as wellas their impacts to the job performance.[Methods]First,we constructed a Knowledge Supply & Demand System from the perspective of micro level knowledge management with the multi-agent based simulation technology.Second,we added time and financial costs as the criteria for performance evaluation.We developed this new system with Python NetworkX.[Results] We found that the large organizations reduced more costs of innovation than their smal counterparts.Increasing the number of nodes in the neighborhood of individuals did not improve the inovation efciency. Once the average numberof fields exceeded acertain threshold,the cost of innovation began to rise. [Limitations]The study did not optimize interactions among individuals for collborative innovation.[Conclusions] The proposed Knowledge Supply& Demand System simulates the knowledge integration processof an organization at the micro level.The new system helps us understand knowledge management, improve the efficiencyof knowledge utilization, and reduce the cost of innovation.

Keywords: Collaborative innovationKnowledge Supply & Demand SystemMulti-agent simulation Complex networksComputational experiments