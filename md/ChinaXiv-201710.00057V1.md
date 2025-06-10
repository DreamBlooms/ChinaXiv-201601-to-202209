# 回收透平排气有效成分的功冷联产系统研究

陈宜12，韩巍1,2，孙流莉³，金红光1,2(1.中国科学院工程热物理研究所，北京市 海淀区100190;2.中国科学院大学，北京市石景山区100049；3.国家核电技术研发中心，北京市 昌平区 102209)

摘要：本文提出并研究了一种回收透平排气有效成分的新型功冷联产系统。该系统通过对高温高压过热氨水蒸气进行热能梯级利用和有效成分回收，实现了动力循环与制冷循环间能量和物质的双重耦合。经过部分冷凝后的透平排气中有效成分浓度明显提高，对这部分有效成分的回收可以有效增加系统制冷量。新系统等效作功效率为 $20 . 1 9 \%$ ，比常规分产系统提高了$4 4 . 3 2 \%$ ，相对节能率为 $3 1 . 6 1 \%$ 。与常规开式和常规闭式功冷联产系统相比，新系统等效作功效率提升幅度分别为 $7 . 2 8 \%$ 和$1 7 . 0 4 \%$ 。通过研究能量传递与转换过程，阐明了系统的节能机理。新提出了平均能量品位差 $\Delta A$ 的概念，分析了系统对输入烟的利用情况和热力性能进一步提升的潜力。另外，还初步探索了系统中动力循环与制冷循环的耦合特性。

关键词：功冷联产；循环耦合；热力学分析；有效成分回收，热能梯级利用中图分类号：TK123 文献标识码：A

# Analysis of a power/refrigeration cogeneration system in recovery of the active ingredient in the turbine exhaust vapor

CHEN Yi1,², HAN Wei1, SUN Liu-li3

(1. Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing 100190, China; 2. University of Chinese Academy of Sciences,Beijing 10o049, China; 3.State Nuclear Power Technology R&D Center, Beijing 102209,China)

Abstract:This paper proposed and studied apower/refrigeration cogeneration system inrecoveryof theactiveingredient inthe turbineexhaustvapor.Thethermalenergyoftehigh-temperatureandhigh-pressureammonia-watersuperheatedvaporisutilized in cascade andtheactiveingredient isrecovered.Inthisway,thecouplesofenergyand materials havebenrealizedbetweenthepower generationcycleandtherefrigerationcycle.Theconcentratiooftheactive ingredient intheturbineexhaustvaporinreass greatly aftercondensation,whichisvaluabletoimprovetherefrgeratiocapacityTheequivalenthat-to-powereficiencyofteproposed system is $20 . 1 9 \%$ $4 4 . 3 2 \%$ higher than the conventional separated system.The thermal energy saving ratio of the proposed system is as high as $3 1 . 6 1 \%$ . Compared with two conventionalcogeneration systems,the heat-to-power eficiencyof the proposed system ncreases $7 . 2 8 \%$ and $1 7 . 0 4 \%$ ,respectively.The energy saving mechanism of the system has been elucidated by studying the energy transfer and conversionprocesses.Aneconcept"averageenegyleveldierence"Awasproposed,andhsbeenusdtoanalyztheutilationof theinput exergyandtheimprovementpotentialofthethermodynamicperformance.Inadition,thecouplingcharacteristicsofthe power generation cycle and the refrigeration cycle were investigated.

Keywords:power/refrigerationcogeneration;cyclecoupling;thermodynamicanalysis;recoveryofactive ingredient;cascad utilization

# 0引言

对于传统的发电技术，如燃气轮机、内燃机发电机组等，约三分之二的能量输入都以热的形式排放到环境中了[]。回收这部分余热能有效减少化石燃料的消耗和提高能源利用效率。将余热回收后直接用于加热通过换热器就可以实现；但要将余热转换为功或冷就相对较为复杂，且单独的余热发电或余热制冷一般效率较低。

功冷联产系统通过动力循环与制冷循环的有机耦合，能够将热能高效转换为功和冷[2]。它可以作为底循环，用于回收传统动力循环(如燃气轮机、内燃机等)的余热，也可以作为独立的系统对工业余热、太阳能或地热能等加以利用。Goswami 等[3]以膨胀机代替氨水吸收式制冷循环中的冷凝器和节流阀，提出一种能在同一循环中产生功和冷的联产系统，被称为Goswami 循环。郑丹星等4在Kalina循环的基础上提出了一种新型吸收式动力/制冷复合循环，新流程在原流程的闪蒸器和第二吸收器之间增设了一台冷凝器和一台蒸发器，将原流程中的闪蒸器用精馏塔替代提高气相组分中的氨浓度，利用循环中富氨蒸汽经过冷凝节流后低温蒸发吸热，达到系统可以同时做功和制冷的目的。张娜等[5]在氨水吸收式制冷循环的稀溶液支路中引入蒸汽透平代替节流阀，并充分利用中温余热加热稀溶液产生蒸汽，同时实现了作功和制冷，该系统被称为并联循环，另外还提出了串联和混联系统。韩巍等[6,7]研究了动力循环与制冷循环之间的耦合关系，提出了开式和闭式供冷联产循环，余热利用效率得到了提高。

在功冷联产系统中，当动力循环与制冷循环采用相同的循环工质时，可以将二者的物流进行连通和交换，通过物质耦合提高系统的整体热力性能。氨水吸收式制冷循环中，氨是制冷的有效成分。在氨水混合工质朗肯循环的透平排气中，具有一定压力的氨水混合蒸气经过部分冷凝，气相中氨的浓度大幅提高，制冷有效成分氨的分压力增大，制冷潜力也有所提升。通过回收这一部分氨，可以提高逆循环中氨制冷剂流量，从而增大制冷量。据此，本文提出了一种回收透平排气有效成分的新型开式功冷联产系统，对其热力性能进行了评估，并进一步分析了系统的节能机理。

# 1系统流程及特征

# 1.1新型功冷联产系统

回收透平排气有效成分的新型开式功冷联产系统的流程如图1所示，系统具有如下两个主要特征：(1)根据"温度对口，梯级利用"的原则，将外热源的高温部分用于作功子循环，外热源的低温部分用于制冷，同时作功子循环的排热也用于制冷子循环；(2)回收动力子循环中透平排气中的有效制冷工质，使其在逆循环中得到进一步利用，且透平排气压力不受逆循环精馏过程压力的限制。

该系统由动力循环(虚线部分)和制冷循环(实线部分)两部分组成，两个子循环间不仅有能量的耦合，还有物质的耦合。从吸收器底部流出的浓溶液1分为两股：一股进入动力子循环，另一股进入吸收式制冷子循环。进入动力子循环的流股2经高压溶液泵加压后在蒸气发生器被烟气的较高温部分加热，形成高温高压的氨水混合蒸气4，然后在透平中膨胀作功。透平排气经过再沸器和换热器部分冷凝后形成气液混合物，然后进入气液分离器，分成较高浓度的氨蒸气和稀溶液。气液分离器顶部的较高浓度的氨蒸气经过压缩机升压后进入精馏塔；底部的稀溶液通过溶液换热器先给精馏塔进料溶液预热，然后与精馏塔塔底稀溶液汇合后进入吸收器。进入吸收式制冷子循环的流股13先经过低压溶液泵加压，然后分为两股15和18。15经过溶液换热器被预热后进入烟气换热器回收烟气的较低温热量，然后进入精馏塔；18依次经过低压溶液换热器和预热器回收透平排气的热量，最后进入精馏塔。在精馏塔中，来自压缩机的浓氨蒸气9和塔釜再沸器中产生的上升氨蒸气与被预热的浓溶液17和20进行充分的传热传质，完成精馏过程，最终分离为塔顶的氨蒸气25和塔釜的稀溶液21。塔顶氨蒸气25进入冷凝器冷凝成液氨26后，进入过冷器回收来自蒸发器的氨蒸气29的部分冷量，形成过冷液氨27。27经过节流阀节流降压(从冷凝压力降为蒸发压力)后形成湿蒸气，在蒸发器中蒸发吸热，制冷效应即在此产生。完成制冷后的氨气，经过冷器变成具有一定过热度的氨蒸气30，随后进入吸收器。塔釜稀溶液21 经过溶液换热器被来自吸收器的浓溶液冷却后，与来自气液分离器底部的稀溶液汇合，再经过减压阀降压(由发生压力降为吸收压力)后进入吸收器。在吸收器中，稀溶液吸收氨气后变为浓溶液，然后开始下一个循环；吸收子过程中放出的吸收热通过冷却水循环带走。

![](images/340904deeee4d538b328bedf4f62d1cccd49a591719ac5a54d5d5eb9425eb6a8.jpg)  
图1回收透平排气有效成分的新型开式功冷联产系统流程 Fig.1 Schematic diagram of the new open-style power/refrigeration cogeneration system

# 1.2参比系统

上述功冷联产系统的能量输入为中低温热源，输出为功和冷。为对其热力性能进行合理评价和分析，本节研究中采用常规的分产系统作为参比系统。分产的动力循环采用以水为工质的简单朗肯循环，分产的制冷循环采用单级氨水吸收式制冷循环，如图2所示。热源分别进入动力循环的余热锅炉和制冷循环的再沸器，两循环各自独立运行，分别输出功和冷量。参比系统与联产系统具有相同类型的能量输入和输出，在相同的热边界条件下进行模拟计算。

![](images/3d36a588680eaff70bc2e10301ca57c50c1855ac4b1f89023f0eb20b8222f640.jpg)  
(a)蒸汽朗肯循环(SCR) (a) Steam Rankine Cycle (SCR)

![](images/980e20d6deacc4d2cbf4ca5558316221b3c8f42f671eb90e37fced7a72588081.jpg)  
图2常规分产系统流程图  
Fig.2 Schematic diagram of conventional separated system

# 2系统模拟与评价

# 2.1循环模拟计算和基本假设

在本研究中，对新系统和参比系统均采用Aspen Plus 进行模拟计算[8,9]。其中，依据质量守恒、能量守恒和组分守恒建立模型，相对误差不超过 $0 . 0 1 \%$ 。新系统的模拟过程中，采用PSRK(Predictive Soave-Redlich-Kwong)物性方程计算 $\mathrm { N H } _ { 3 } – \mathrm { H } _ { 2 } \mathrm { O }$ 溶液的热力参数[10,1]。采用Steam-TA物性方程计算 $\mathrm { H } _ { 2 } \mathrm { O }$ 的热力参数。通过选择这些物性方法，计算结果和IIR(InternationalInstitute ofRefrigeration)物性结果吻合良好[12]。

适用于新系统的外部热源为分布式能源系统中的余热，如内燃机或燃气轮机排烟等。燃气内燃机被广泛应用于分布式能源系统，因此，在本文研究中，采用燃气内燃机排烟作为系统外部热源。

参照相关的研究文献[13,14]，确定了基本参数的设定，如表1所示。

为了便于关键问题研究，对系统做了如下简化和假设：

1)系统循环处于稳定工况条件；  
2)系统中的管路和一般换热器的压力损失忽略不计;  
3)部件和管路的热损失忽略不计；  
4)再沸器、吸收器、冷凝器出口处的工质均处于饱和状态；$5 ) \mathrm { N H } _ { 3 }$ 压缩机的等熵效率根据压比 $R _ { \mathfrak { p } }$ 分别按

如下公式进行计算[15]

表1系统模拟参数规定  
Table 1 System simulation specifications   

<html><body><table><tr><td>项目</td><td>数值</td></tr><tr><td>泵效率/%</td><td>75</td></tr><tr><td>透平等熵效率/%</td><td>85</td></tr><tr><td>透平排气最小干度/%</td><td>85</td></tr><tr><td>过热器热端温差/℃</td><td>30</td></tr><tr><td>发生器最小换热温差/℃</td><td>15</td></tr><tr><td>烟气换热器最小换热温差/℃</td><td>15</td></tr><tr><td>其它换热设备最小温差/℃</td><td>5</td></tr><tr><td>精馏塔压降/MPa</td><td>0.01</td></tr><tr><td>吸收器压降/MPa</td><td>0.02</td></tr></table></body></html>

# 2.2评价准则

考虑到系统输出的功和冷品位不同，传统热力学第一定律效率并不能很好地适用于多产品输出的系统。为了对系统进行合理评价，可以通过机械压缩式制冷循环系统性能系数 $( \mathrm { C O P _ { C } ) }$ 将输出冷量等效转化为输出功，和系统原本的输出功一起作为系统的产出。因此，等效作功效率可以定义为：

$$
\eta _ { \mathrm { { w , e q } } } = \frac { W _ { \mathrm { { T U R } } } - W _ { \mathrm { { C O M P } } } - W _ { \mathrm { { p } } } + \mathcal { Q } _ { \mathrm { { c } } } \mathrm { { / C O P } _ { \mathrm { { c } } } } } { \mathcal { Q } _ { \mathrm { { f } } } }
$$

其中， $W _ { \mathrm { T U R } }$ 表示透平输出功， $W _ { \mathrm { C O M P } }$ 和 $W _ { \mathrm { P } }$ 表示机械压缩机和溶液泵的耗功， $\varrho _ { \mathrm { c } }$ 表示蒸发器中的冷量输出， $Q _ { \mathrm { f } }$ 表示烟气携带的热能。

为了直观地表示研究系统的先进性，同时采用相对节能率(TESR)作为评价指标对系统进行评价。TESR考察了以实现相同的作功量和制冷量为基准，联产系统与常规的分产系统在消耗输入热能数量上的差异。TESR定义为联产系统的热能消耗减少值与参照系统能耗的比值：

$$
\mathrm { T E S R } { = } \frac { \left( P / \eta _ { \mathrm { t h } } + Q _ { \mathrm { c } } / \mathrm { C O P _ { A } } \right) { - } Q _ { \mathrm { i n } } } { \left( P / \eta _ { \mathrm { t h } } + Q _ { \mathrm { c } } / \mathrm { C O P _ { A } } \right) }
$$

其中， $Q _ { \mathrm { i n } }$ 为联产系统的热量消耗量； $P$ 和 $\varrho _ { \mathrm { c } }$ 分别为分产系统的作功量和制冷量， $\eta _ { \mathrm { t h } }$ 为分产作功系统的热发电效率， $\mathrm { C O P _ { A } }$ 为分产余热制冷系统的性能系数，这些效率在与联产系统相同的热边界条件下获得。

# 2.3烟分析方法

基于热力学第二定律的烟分析方法可以揭示系统中各个过程不可逆损失的大小，从而阐明系统性能提高的原因和进一步提高的潜力。对于任意控制体的烟平衡表达式为：

$$
E _ { \mathrm { { D } } } = \sum m _ { \mathrm { { i n } } } e _ { \mathrm { { i n } } } - \sum m _ { \mathrm { { o u t } } } e _ { \mathrm { { o u t } } } - W + \sum Q _ { j } \left( 1 { - } { \frac { T _ { 0 } } { T _ { j } } } \right)
$$

其中，下标in表示进入控制体的物流，下标 out表示流出控制体的物流， $W$ 表示穿过控制体边界的功流， $Q _ { j }$ 表示穿过控制体的热流， $T _ { j }$ 为该热流的温度， $e$ 表示随着物流进入控制体的比烟。 $T _ { 0 }$ 表示环境温度，取 $2 9 8 . 1 5 \mathrm { K }$ [16]。比烟可以用下式计算：

$$
e = ( h - h _ { 0 } ) - T _ { 0 } ( s - s _ { 0 } )
$$

(1)烟效率

本文还采用了烟效率来表示系统对输入烟的利用率，表达式为：

$$
\eta _ { \mathrm { e x } } = \frac { W _ { \mathrm { n e t } } + E _ { \mathrm { C } } } { E _ { \mathrm { f } } }
$$

其中， $W _ { \mathrm { n e t } }$ 表示系统净输出功； $E _ { \mathrm { C } }$ 表示系统输出的冷烟，根据低温蒸发器制冷剂进出口烟的变化计算得出：

$$
E _ { \mathrm { c } } = m _ { \mathrm { r e f } } \left[ \left( h _ { \mathrm { E V A , i n } } - h _ { \mathrm { E V A , o u t } } \right) - T _ { \mathrm { 0 } } \left( s _ { \mathrm { E V A , i n } } - s _ { \mathrm { E V A , o u t } } \right) \right]
$$

其中， $m _ { \mathrm { r e f } }$ 表示制冷剂的流量， $h _ { \mathrm { E V A , i n } }$ ， $s _ { \mathrm { E V A , i n } }$ 和$h _ { \mathrm { E V A , o u t } }$ ， $s _ { \mathrm { E V A , o u t } }$ 分别表示制冷剂在流入和流出蒸发器时的比焓和比熵。

式(6)中， $E _ { \mathrm { f } }$ 表示系统输入热烟，根据烟气热源进入系统和在环境状态下的焓和熵进行计算：

$$
E _ { \mathrm { f } } ^ { \mathrm { } } = m _ { \mathrm { f } } \left[ \left( h _ { \mathrm { f , i n } } ^ { } - h _ { \mathrm { f , 0 } } ^ { } \right) - T _ { \mathrm { 0 } } ^ { } \left( s _ { \mathrm { f , i n } } ^ { } - s _ { \mathrm { f , 0 } } ^ { } \right) \right]
$$

(2)烟损系数

烟效率并不能直接表明系统中烟损失的分布情况，无法揭示出薄弱环节。与此相对应的是损失占输入烟的比例，它能揭示过程中烟退化的不为和程度，与烟效率可以起到相辅相成的作用，本文按下式定义各个部件的烟损系数：

$$
\Omega _ { \mathrm { { D } } } = { \frac { E _ { \mathrm { { D } } } } { E _ { \mathrm { { f } } } } }
$$

(3)关键过程能量品位分析

常规烟分析方法可以很好地表征不可逆损失的大小，但在分析系统性能提升潜力时还存在一些问题。比如，对于一个传热过程，烟损失较大的原因可能是由于其本身传热量比较大，传热过程本身已经较为优化，并没有太大的性能提升潜力，此时采用常规烟分析方法就会产生误导。据此，本文提出了平均能量品位差 $\Delta A$ 的概念，定义式为：

$$
\Delta A = { \frac { \Delta E } { \Delta H } }
$$

其中， $\Delta \mathrm { E }$ 表示能量传递或转换过程中的烟损失，AH表示能量释放侧与接受侧焓值的变化量。

平均能量品位差 $\Delta A$ 作为一个无量纲参数，表征了发生单位能量传递或转换过程中造成的不可逆损失大小。 $\Delta A$ 越大，说明该过程能量品位匹配度越差，热力性能进一步提升的潜力也越大。

# 3系统热力性能

设计工况下，热源烟气和冷却水的初始温度分别取为 $3 5 0 ^ { \circ } \mathrm { C }$ 和 $3 0 ^ { \circ } \mathrm { C }$ ，制冷蒸发温度设定为 $. 1 5 \mathrm { ^ \circ C }$ 。余热锅炉热端温差设定为 $3 0 ^ { \circ } \mathrm { C }$ ，其他参数假设如表1所示。通过模拟计算得到新型开式功冷联产系统中各个关键点的温度、压力、质量流率、焓、熵等参数，并进一步计算出各个主要部件的负荷如表3所示。联产系统与常规分产系统的热力性能对比结果如表4所示。由表3中数据可知，当联产系统输入的烟气热量为 $3 5 8 . 8 3 \mathrm { ~ k W }$ 时，透平作功量为$3 5 . 1 8 \mathrm { ~ k W }$ ，压缩机和泵耗功量分别为 $3 . 0 6 ~ \mathrm { k W }$ 和$3 . 6 4 \mathrm { k W }$ ，输出 $2 8 . 4 8 \mathrm { k W }$ 净功和 $1 2 7 . 0 1 \mathrm { k W }$ 冷量(功冷比为0.224)，等效作功效率为 $20 . 1 9 \%$ 。在相同热边界条件下，对于常规分产系统，同样为了输出$2 8 . 4 8 ~ \mathrm { k W }$ 净功和 $1 2 7 . 0 1 \ \mathrm { k W }$ 冷量，需要输入烟气热量为 $5 2 4 . 6 7 \mathrm { k W }$ ，等效作功效率为 $1 3 . 8 0 \%$ 。其中，蒸汽朗肯循环输入烟气热量 $2 1 0 . 6 0 \mathrm { k W }$ ，透平作功量为 $3 0 . 9 7 \mathrm { k W }$ ，部分产功用于满足分产系统中的泵耗功；吸收式制冷循环输入烟气热量 $3 1 4 . 0 7 \mathrm { k W }$ ，蒸发器制冷量为 $1 2 7 . 0 1 \ \mathrm { k W }$ ，制冷COP为0.404。与分产系统相比，该联产系统等效作功效率提高了6.39个百分点，相对节能率达到了 $3 1 . 6 1 \%$ 。

Table 2 Load of each component of the proposed cogeneration system   
表3新型开式功冷联产系统与常规分产系统热力性能对比  

<html><body><table><tr><td>项目 数值</td><td>项目</td><td>数值</td></tr><tr><td>吸收器QABs/kW</td><td>193.38</td><td>低压溶液泵耗功WLp/kW 2.08</td></tr><tr><td>高压溶液泵耗功WHP/kW</td><td>1.56</td><td>高压溶液换热器QHSHx /kW 272.69</td></tr><tr><td>余热锅炉QHRVG/KW</td><td>202.71</td><td>烟气换热器QGHEX/KW 58.46</td></tr><tr><td>透平作功WTUR/KW</td><td>35.18</td><td>分凝器QPc/kW 37.42</td></tr><tr><td>再沸器QREB/KW</td><td>84.34</td><td>冷凝器QcoN/kW 129.04</td></tr><tr><td>预热器QPREH/KW</td><td>38.07</td><td>过冷器QsUBc/kW 11.85</td></tr><tr><td>压缩机耗功WcoMP/kW</td><td>3.06</td><td>蒸发器QEVA/KW 127.01</td></tr><tr><td>低压溶液换热器QLSHx/KW</td><td>15.40</td><td>排烟损失 Qf,loss/kW 97.66</td></tr></table></body></html>

表2新型开式功冷联产系统中各部件负荷  
Table 3 Thermodynamic performance of the proposed cogeneration system and the conventional separated systen   

<html><body><table><tr><td rowspan="2">项目</td><td rowspan="2">新型开式</td><td colspan="3">常规分产</td></tr><tr><td>SRC</td><td>AARC</td><td>SRC+AARC</td></tr><tr><td>输入烟气热量，Qf(kW)</td><td>358.83</td><td>210.60</td><td>314.07</td><td>524.67</td></tr><tr><td>透平作功，WTIR(KW)</td><td>35.18</td><td>30.97</td><td>，</td><td>30.97</td></tr><tr><td>压缩机耗功，WcOMP(kW)</td><td>3.06</td><td></td><td></td><td></td></tr><tr><td>泵耗功，Wp(kW)</td><td>3.64</td><td>0.10</td><td>2.39</td><td>2.49</td></tr><tr><td>净产功量，Wnet(kW)</td><td>28.48</td><td>30.87</td><td></td><td>28.48</td></tr><tr><td>制冷量，Qc(kW)</td><td>127.01</td><td>-</td><td>127.01</td><td>127.01</td></tr><tr><td>功冷比，R</td><td>0.224</td><td>-</td><td>-</td><td>0.224</td></tr><tr><td>等效作功量，Weq (kW)</td><td>72.43</td><td>30.87</td><td>43.95</td><td>72.43</td></tr><tr><td>等效作功效率，nw.eq(%)</td><td>20.19</td><td>14.66</td><td>13.99</td><td>13.80</td></tr></table></body></html>

将构建的新型开式功冷联产系统与已经发表的常规闭式功冷联产系统和常规开式功冷联产系统进行对比分析。表4中列出了在同等热边界条件下，常规开式功冷联产系统和常规闭式功冷联产系统的热力性能参数。在输入热源相同的情况下，新型开式联产系统的制冷量与常规开式联产系统相比略有减少，从 $1 3 3 . 6 5 \mathrm { k W }$ 减少到 $1 2 7 . 0 1 \mathrm { k W }$ =相当于等效作功量减少了 $2 . 3 0 \mathrm { k W }$ ；但在净输出功方面，新型系统比常规开式系统增加了$3 3 . 7 1 \% ( 7 . 1 8 \mathrm { k W } )$ 。因此，新型系统功冷比有所增大，且等效作功效率比常规开式功冷联产系统提高$7 . 2 8 \%$ ，相对节能率提高了4.51个百分点。与常规闭式功冷联产系统相比，新型开式功冷联产系统的热力性能提升幅度更大，等效作功效率和相对节能率分别提高了 $1 7 . 0 4 \%$ 和 $6 8 . 7 7 \%$ 。

表4常规开式与常规闭式功冷联产系统热力性能 Table 4 Thermodynamic performance of the two conventional cogeneration systems   

<html><body><table><tr><td>项目</td><td>常规开式</td><td>常规闭式</td></tr><tr><td>输入烟气热量,Qr(kW)</td><td>358.83</td><td>358.83</td></tr><tr><td>透平作功,WTUR (KW)</td><td>25.45</td><td>37.86</td></tr><tr><td>压缩机耗功,WcoMP(kW)</td><td></td><td></td></tr><tr><td>泵耗功,Wp (kW)</td><td>4.15</td><td>3.12</td></tr><tr><td>净产功量,Wnet (kW)</td><td>21.30</td><td>34.74</td></tr><tr><td>制冷量,Qc (kW)</td><td>133.65</td><td>78.46</td></tr><tr><td>功冷比,Rw/c</td><td>0.159</td><td>0.443</td></tr><tr><td>等效作功量,Weq (kW)</td><td>67.55</td><td>61.89</td></tr><tr><td>等效作功效率,nw.eq (%)</td><td>18.82</td><td>17.25</td></tr><tr><td>相对节能率,TESR(%)</td><td>27.10</td><td>18.73</td></tr></table></body></html>

# 4分析与讨论

# 4.1系统能量传递与转换过程分析

新型开式功冷联产系统中主要传热和能量转换过程如图3所示。热源烟气的较高温部分(从$3 5 0 ^ { \circ } \mathrm { C }$ 到 $1 7 0 . 8 ^ { \circ } \mathrm { C }$ ， $2 0 2 . 7 1 \mathrm { k W } )$ 在动力循环的余热锅炉中将高压氨水溶液从 $3 7 . 1 \mathrm { { ^ \circ C } }$ 加热到 $3 2 0 ^ { \circ } \mathrm { C }$ (状态点3-4)，产生高温高压过热氨水蒸气。该氨水蒸气依次在动力循环和制冷循环中进行了深度梯级利用。在烟气换热器中，热源烟气的较低温部分(从

$1 7 0 . 8 ^ { \circ } \mathrm { C }$ 到 $1 1 7 . 9 ^ { \circ } \mathrm { C }$ ， $5 8 . 4 6 \mathrm { k W } )$ 用于预热制冷循环中的精馏塔进料，实现热量回收利用。

高温高压过热氨水蒸气首先经过透平膨胀作功(状态点4-5)。透平进出口焓降为 $3 5 . 1 8 \mathrm { ~ k W }$ ；其中， $6 . 7 0 \mathrm { k W }$ 用于满足系统中压缩机和溶液泵耗功，剩余 $2 8 . 4 8  { \mathrm { ~ k W } }$ 为系统净输出功。图3中的状态点4-5表示常规开式功冷联产系统透平膨胀作功的情况。为了将透平排气直接通入制冷循环的精馏塔中，需要将透平排气压力提高到与精馏压力一致，此时透平排气压力和温度都处于较高的水平(1.356MPa， $1 7 3 . 0 1 ^ { \circ } \mathrm { C } \cdot$ )。该条件下，一方面氨水蒸气膨胀不充分，另一方面精馏塔中较大的换热温差导致不可逆损失增加。相比而言，新系统中的透平排气可以膨胀到更低的压力水平 $( 0 . 6 ~ \mathrm { M P a }$ 或更低)，比焓降较大，作功能力明显提高。

透平排气的温度和压力分别为 $1 4 1 ^ { \circ } \mathrm { C }$ 和0.6MPa，其冷凝热非常适合驱动吸收式制冷循环。如图3所示，透平排气依次通过制冷循环的再沸器和预热器实现了热量回收，先从 $1 4 1 ^ { \circ } \mathrm { C }$ 降至 $1 2 0 ^ { \circ } \mathrm { C }$ （状态点5-6， $8 4 . 3 4 \mathrm { k W } )$ ，最后降至 $9 5 ^ { \circ } \mathrm { C }$ (状态点6-7，$3 8 . 0 7 \mathrm { k W } )$ 。透平排气压力为 $0 . 6  { \mathrm { M P a } }$ ，如图4所示，气相组分中的氨浓度随着冷凝过程的进行快速提高。氨成分可通过制冷子循环回收利用，增加系统制冷量。状态点5、6、7对应的气液混合物中气相组分的氨质量浓度分别为0.396、0.697和0.889，在制冷循环中回收利用的价值越来越大。新系统通过气液分离器分离出状态点7中浓度较高的氨蒸气(图4中状态点7)，经过压缩机提高到吸收式制冷循环的精馏压力后送入精馏塔进一步提纯，以满足制冷的要求；由于是对过热蒸气的精馏，所以不需要额外消耗热，只需提供适当的冷却负荷即可。气液分离器底部稀溶液用来预热精馏塔进料溶液。

以上过程中，吸收烟气余热产生的高温高压过热氨水蒸气先经过透平膨胀作功，随后透平排气的冷凝热在制冷循环中被梯级利用，最后回收其中的有效成分用于增加制冷量，实现了动力循环与制冷循环间能量和物质的双重耦合。新型开式功冷联产系统有三方面的特点：(1)透平排气压力不受到制冷循环的限制，因此作功能力大幅上升；(2)依据"温度对口，梯级利用"的原则，烟气的较高温部分在动力循环加以利用，较低温部分和透平排气在制冷循环中进行了梯级利用；(3)经过部分冷凝后的排气中有效成分浓度明显提高，对这部分有效成分的回收只需要提供压力提升所需消耗的功，不需要消耗热量，可以有效增加系统制冷量。

![](images/49c7d70d7bb8ec3c14121087021e43d735f44f1b78d6a2a7fd5fa355f0bcf0da.jpg)  
图3主要能量传递与转换过程 $t – H$ 图

![](images/01a9020c455b5cd4e34c5328fb0c392c4c5d0c7820b00157b28045ad2497347b.jpg)  
Fig.3 t-Hdiagramof the main energy transferand conversion   
Fig.4 Ammonia mass concentration change in the turbine exhaust vapor

# 4.2系统烟分析结果

通过烟分析，列出了新型开式功冷联产系统与分产系统的烟平衡情况，如表5所示。对联产系统和分产系统进行模拟计算时，保证佣产出相同（2 $( 4 8 . 0 4 \mathrm { k W } )$ ，其中机械烟和冷烟分别为 $2 8 . 4 8 \mathrm { k W }$ 和$1 9 . 5 6 \mathrm { k W } .$ 。此时，烟输入(全部为热烟)分别为112.52kW和 $1 6 4 . 7 7 \mathrm { k W }$ ，分产系统多输入 $4 6 . 4 4 \%$ 。系统内部机械耗功由透平提供，且假设功传递过程中不存在机械损失。联产系统中各个部件的烟损失总和占输入烟的 $5 7 . 3 1 \%$ ，比参比系统低13.53个百分点。

联产系统和分产系统的烟效率分别为 $4 2 . 6 9 \%$ 和$2 9 . 1 6 \%$ 。

系统中的烟损失可以分为四大部分。图5和图6分别表示了四大部分中具体各个部件的烟损失分布情况，并给出了对应的平均能量品位差。

![](images/ba987d84c2b1d93e9ef7eae40ef1a695500a57b5169713d2713b4149e4e7c65a.jpg)  
图5新型开式功冷联产系统中烟损失分布及对应品位 差的对比分析 Fig.5 Exergy destruction and loss distribution and analysis of the energylevel difference

![](images/720c870c19d26c75591704f15c50c6e3c835940fa40d6903cbd879fdc36f2a3b.jpg)  
图4透平排气气相组分中氨质量浓度变化情况  
图6分产系统中烟损失分布及对应品位差的对比分析 Fig.6 Exergy destruction and loss distribution and analysis of the energy level difference

从表5中可知，新系统烟效率比分产系统高的原因主要在于第一部分(工质与热源换热过程)中烟损失的减小。在联产系统中，这部分烟损失占输入烟的比例 $( 1 5 . 1 8 \% )$ ，不到参比系统 $( 3 2 . 3 8 \% )$ 的一半。对比图5和图6可知，这主要是由于参比系统中$3 5 0 ^ { \circ } \mathrm { C }$ 的烟气直接用于驱动吸收式制冷循环，再沸器的换热过程中存在着较大的换热温差，烟损系数高达 $2 6 . 1 3 \%$ ，对应的平均能量品位差△A也较高(0.194)，具有较大的节能潜力。在新系统中，热源烟气用于驱动氨水动力循环，有效减小了换热温差，余热锅炉和烟气换热器中的 $\Delta A$ 都处于较低水平(分别为0.063和0.073)，换热过程热能品位匹配较好。第二部分，对于分产系统中与热阱换热过程的烟损失部分，排烟烟损系数为 $9 . 9 3 \%$ ， $\Delta A$ 也较高(0.167)。在新系统中，充分利用氨水混合工质的变温蒸发特性，有效降低了排烟温度(联产系统和SRC分别为 $1 1 7 . 9 ^ { \circ } \mathrm { C }$ 和 $1 8 1 . 0 ^ { \circ } \mathrm { C } \$ ，排烟部分的 $\Delta A$ 降为0.075。另外，在新系统和分产系统中，分凝器虽然烟损系数不高，但 $\Delta A$ 处于较高水平(0.145和0.139)，可以考虑将该部分冷凝热用于预热精馏塔进料以减小不可逆损失。第三部分是系统内部换热过程的烟损失，在联产系统中虽然内部换热部件较多，但都保证了良好的能量匹配 $\boldsymbol { \Delta } \boldsymbol { A }$ 处于较低水平)，因此总的烟损系数也较低 $( 9 . 4 3 \% )$ ，不可逆损失较少。透平排气携带的较高温冷凝热在再沸器中为精馏过程提供热负荷，较低温冷凝热用于预热精馏塔进料，实现了梯级利用。第四部分是压力调节过程的烟损失，该部分涉及的部件均为满足特定压力变化的成熟机械设备，进一步减小烟损失的潜力非常有限，一般不予以考虑。

由上述分析可知，新型功冷联产系统中大部分部件中能量传递与转换过程△A都处于较低水平，品位匹配良好。特别是工质与热源换热过程和排烟，与分产系统相比烟损失大幅降低。新系统下一步可能改进的地方在于回收分凝器中的冷凝热。

表5新型开式功冷联产系统与分产系统烟平衡表  
Table 5 Exergy balance of the proposed cogeneration system   

<html><body><table><tr><td rowspan="3">功冷联产系统</td><td rowspan="2" colspan="2">新型开式</td><td colspan="4">分产系统</td></tr><tr><td>SRC</td><td>AARC</td><td>SRC+AARC</td><td></td></tr><tr><td></td><td>kW</td><td>%</td><td>kW</td><td>kW</td><td>kW</td><td>%</td></tr><tr><td>烟输入</td><td>112.52</td><td>100.00</td><td></td><td>-</td><td>164.77</td><td>100.00</td></tr><tr><td>热烟</td><td>112.52</td><td>100.00</td><td>66.13</td><td>98.64</td><td>164.77</td><td>100.00</td></tr><tr><td>机械烟</td><td></td><td></td><td>0.10</td><td>2.39</td><td>-</td><td></td></tr><tr><td>烟损失</td><td>64.48</td><td>57.31</td><td>35.26</td><td>81.47</td><td>116.73</td><td>70.84</td></tr><tr><td>工质与热源换热过程</td><td>17.08</td><td>15.18</td><td>10.31</td><td>43.05</td><td>53.36</td><td>32.38</td></tr><tr><td>系统与热阱换热过程</td><td>28.73</td><td>25.53</td><td>19.30</td><td>27.83</td><td>47.13</td><td>28.60</td></tr><tr><td>系统内部换热过程</td><td>10.61</td><td>9.43</td><td></td><td>7.54</td><td>7.54</td><td>4.58</td></tr><tr><td>压力调节过程</td><td>8.06</td><td>7.16</td><td>5.65</td><td>3.05</td><td>8.70</td><td>5.28</td></tr><tr><td>烟输出</td><td>48.04</td><td>42.69</td><td>30.97</td><td>19.56</td><td>48.04</td><td>29.16</td></tr><tr><td>机械焊</td><td>28.48</td><td>25.31</td><td>30.97</td><td>-</td><td>28.48</td><td>17.28</td></tr><tr><td>冷烟</td><td>19.56</td><td>17.38</td><td>，</td><td>19.56</td><td>19.56</td><td>11.87</td></tr></table></body></html>

# 4.3循环间耦合特性分析

研究中发现，透平排气压力 $p _ { \mathrm { T U R , i n } }$ 和进入气液分离器的部分冷凝温度 $t _ { \mathrm { P C } }$ 作为动力循环与制冷循环的耦合点参数，对新型开式功冷联产系统中有效成分的回收利用有重要影响。图5给出了在不同透平排气压力下部分冷凝温度 $t _ { \mathrm { P C } }$ 对系统性能的影响。由图可知，对于特定的透平排气压力，随着 $t _ { \mathrm { P C } }$ 的升高，系统的等效作功效率都是先升高后降低，存在最优值。不同排气压力下，系统最高等效作功效率对应的最佳 $t _ { \mathrm { P C } }$ 不同。具体而言，透平排气压力较高时，最佳 $t _ { \mathrm { P C } }$ 也较高；当透平排气压力分别为 $0 . 4 \mathrm { M P a }$ 、 $0 . 6  { \mathrm { M P a } }$ 和 $ { \mathbf { 0 . 8 \ M P a } }$ 时，最佳 $t _ { \mathrm { P C } }$ 分别为 $7 5 ^ { \circ } \mathrm { C } \mathrm { } , 9 5 ^ { \circ } \mathrm { C }$ 和 $1 0 0 ^ { \circ } \mathrm { C }$ 。当 $p _ { \mathrm { T U R , i n } } { = } 0 . 6 ~ \mathrm { M P a }$ $t _ { \mathrm { P C } } { = } 9 5 ^ { \circ } \mathrm { C }$ （204号时，新系统的等效作功效率达到最大值，为 $2 0 . 1 9 \%$ 。

![](images/8701e6f01d75d5c88994d28544e21e282b300a7b7f023223153ae51e82f0063e.jpg)  
图7不同透平排气压力下部分冷凝温度 $t _ { \mathrm { P C } }$ 对系统性能的影响  
Fig. 5 Effect of $t _ { \mathrm { P C } }$ on the thermodynamic performance of the proposed system at different turbine outlet pressure

# 5结论

本文建立了一种回收透平排气有效成分的新型开式功冷联产系统模型，对其基本热力性能进行了评估，并通过能量传递与转换过程分析和烟分析阐释了系统的节能机理和热力性能进一步提升的潜力。另外，还初步探索了系统循环间的耦合特性，为系统优化提供了理论依据。具体研究结论如下：

1)模拟计算结果表明，本文研究的新型开式功冷联产系统在烟气热源温度为 $3 5 0 ^ { \circ } \mathrm { C }$ ，冷却水温度为 $3 0 ^ { \circ } \mathrm { C }$ ，制冷蒸发温度为 $. 1 5 \mathrm { ^ \circ C }$ 时，系统等效作功效率为 $20 . 1 9 \%$ ，比常规分产系统提高了 $4 4 . 3 2 \%$ 相对节能率为 $3 1 . 6 1 \%$ 。新系统与常规开式和常规闭式功冷联产系统相比，等效作功效率提升幅度分别为 $7 . 2 8 \%$ 和 $1 7 . 0 4 \%$ 。

2)系统能量传递与转换过程分析结果表明，新系统通过对高温高压过热氨水蒸气进行热能梯级利用和有效成分回收，实现了动力循环与制冷循环间能量和物质的双重耦合。新系统中烟气的较高温部分和较低温部分分别在动力和制冷循环中进行梯级利用，透平排气先进行热能的梯级利用，后在制冷循环中进行了有效成分回收。经过部分冷凝后的排气中有效成分浓度明显提高，对这部分有效成分的回收只需要提供压力提升所需消耗的功，不需要消耗热量，可以有效增加系统制冷量。

3)基于烟分析，新提出了平均能量品位差△A的概念， $\Delta A$ 作为一个无量纲参数，表征了发生单位能量传递或转换过程中造成的不可逆损失大小。

$\Delta A$ 越大，说明该过程能量品位匹配度越差，热力性能进一步提升的潜力也越大。采用包含 $\Delta A$ 的烟分析的方法对新系统和参比系统进行了对比研究，明确了新系统在烟利用过程中的先进性和热力性能进一步提升的潜力。

4)透平排气压力和气液分离器入口的部分冷凝温度 $t _ { \mathrm { P C } }$ 作为动力循环与制冷循环的耦合点参数，对气液分离器出口气相组分中有效成分的浓度和回收率有重要影响。透平排气压力较高时，最佳$t _ { \mathrm { P C } }$ 也较高；当透平排气压力分别为 $0 . 4 ~ \mathrm { M P a }$ 、0.6MPa和 $0 . 8 \mathrm { M P a }$ 时，最佳 $t _ { \mathrm { P C } }$ 分别为 $7 5 \mathrm { ^ \circ C }$ 、 $9 5 ^ { \circ } \mathrm { C }$ 和$1 0 0 ^ { \circ } \mathrm { C }$ 。

# 奓考乂

[1] 金红光，郑丹星，徐建中．分布式冷热电联产系统装置 及应用[M]．中国电力出版社,2010.   
[2] G Demirkaya, R.V. Padilla, D.Y. Goswami. A review of combinedpowerandcoolingcycles[J].Wiley Interdisciplinary Reviews: Energy and Environment,2013, 2(5): 534-547.   
[3] D.Y. Goswami, F. Xu. Analysis of a new thermodynamic cycle for combined power and cooling using low and mid temperature solar collectors [J]. Journal of Solar Energy Engineering,1999,121(2): 91-97.   
[4] 郑丹星，陈斌，齐云，金红光．新型氨吸收式动力/制冷 复合循环的热力学分析 [J].工程热物理学报，2002,(05): 539-542.   
[5] N. Zhang,N. Lior. Methodology for thermal design of novel combined refrigeration/power binary fluid systems [J]. International Journal of Refrigeration,2007,30(6): 1072-1085. [6] L. Sun,W. Han, X. Jing,D. Zheng,et al. A power and cooling cogeneration system using mid/low-temperature heat source [J].Applied Energy,2013,112: 886-897.   
[7] L.Sun,W. Han,D. Zheng,H. Jin. Assessment of an ammonia-water power/cooling cogeneration systemwith adjustable solution concentration [J]. Applied Thermal Engineering,2013,61(2): 443-450.   
[8] S.M. Sadrameli， D.Y. Goswami. Optimum operating conditions for a combined power and cooling thermodynamic cycle [J]. Applied Energy,2007, 84(3): 254-265.   
[9] Aspen Plus?，Aspen Technology， Inc.，version 11.1. Available from: http://www.aspentech.com/.   
[10] F. Xu,D. Yogi Goswami, S. S Bhagwat.A combined power/cooling cycle[J].Energy,2000,25(3): 233-246.   
[11]曾纪珺，杨建明，张伟，郝妙莉，等．氨-水体系气液平 衡模型的研究[J].化工进展,2010,(S2):87-90.   
[12]International Institute of Refrigeration,Thermodynamic and Physical Properties $\mathrm { N H } _ { 3 } – \mathrm { H } _ { 2 } \mathrm { O }$ ,1994,Paris,France.   
[13] S.Karellas,A.D.Leontaritis,G. Panousis,E.Bellos,et al. Energetic and exergetic analysis of waste heat recovery systems in the cement industry [J].Energy,2013,58:147-156. [14]L.Sun,W.Han,H. Jin.Energy and exergy investigation ofahybridrefrigerationsystemactivated by mid/low-temperatureheatsource [J]. Applied Thermal Engineering,2015,91:913-923.   
[15]T.-S.Lee,C.-H. Liu,T.-W. Chen. Thermodynamic analysisofoptimalcondensingtemperature of cascade-condenser in $\mathrm { C O } _ { 2 } / \mathrm { N H } _ { 3 }$ cascade refrigeration systems [J]． International Journal of Refrigeration，2006, 29(7): 1100-1108.   
[16] M.J.Moran,H.N.Shapiro,D.D.Boetner,M. Bailey. Fundamentals of engineering thermodynamics [M].United States of America: John Wiley& Sons,2010.