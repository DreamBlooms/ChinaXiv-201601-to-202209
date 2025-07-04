# 柴油机朗肯循环余热回收系统的效率预测模型

杨灿;谢辉;周奎;程彰

（天津大学内燃机燃烧学国家重点实验室，天津300072）

摘要：有机朗肯循环（ORC）技术可以有效回收重型车用柴油机的排气热能。但在道路运行过程中，其排气热源不稳定，冷源的维持也需要消耗能量，使得蒸发压力和冷凝压力的在线优化与控制实施均存在严峻挑战。为此，建立了ORC余热回收系统的效率预测模型，以ORC系统的热力学第一定律模型为基础，抓住蒸发器阶跃响应的宏观特征，提出了有效换热量的动态修正模型，以及工况模式切换的预判因子，并采用简化机理和数据建模相结合的方法，建立了冷凝器散热功耗的经验模型；提出了基于效率预测模型的ORC余热回收系统优化控制架构及策略。道路仿真结果表明了效率模型和优化算法的有效性：ORC系统的有效做功时间达到 $94 \%$ ，蒸汽过热度控制在5-15K之间，冷凝器散热功耗与发电功率的比值维持在 $20 \%$ 以下。

关键词：柴油机；有机朗肯循环；余热回收；效率预测模型中图分类号：TK421 文献标识码：A

# Efficiency Prediction Model of a Diesel-Engine ORC Exhaust Heat Recovery

System

YANG Can, XIE Hui, ZHOU Kui, CHENG Zhang (State Key Laboratory of Engines，Tianjin University，Tianjin 3OoO72，China)

Abstract: The ORC (organic Rankine cycle) system is regarded as one of the most potential ways for exhaust heat recovery of heavy-duty vehicle diesel engines.But the exhaust energy fluctuates widely during driving cycles,also the ORC cooling willintroduce extra energy consumption. Consequently, it is a big challenge to optimize and control the evaporation pressure and condensation pressure in the driving cycle.To this end,a control-oriented ORC effciency prediction model was completed at first: basing on a foundation model of the first law of thermodynamics; focusing on the dominant feature of the ORC system step response,an effective heat absorption dynamic model and operating modes corrected factor were built up;and an empirical model was established to describe the energy consumption for ORC cooling. Afterwards,a sequence optimization algorithm was proposed to seek optimum values of the evaporation pressure and condensation pressure dynamically.The validation results based on a simulation plat were encouraging: the effective working time percentage achieves $94 \%$ ，the superheat degree is controlled as 5K-15K,and the cooling power consumption is kept less than $20 \%$ of the ORC power generation.

Key Words: diesel engine； organic Rankine cycle；waste heat recovery； efficiency prediction model

# 0引言

能是改善发动机燃油经济性，满足未来更严苛油耗法规的热点技术[I]。BMW、AVL、橡树岭等研究结果表明，该技术在重型车上可获得 $5 . 1 0 \%$ 的燃油经采用ORC技术回收和利用重型柴油机的余热

济性改善效果[2-5]。

但车辆在道路运行过程中，其发动机基本处于怠速、大负荷、小负荷等动态变工况运行状态，内燃机的排气流量和温度也必然呈现出强烈的瞬变特征，且变化范围较大。前期研究[67发现：ORC余热回收系统在循环工况中呈现出强烈的动态行为特征，包括蒸汽参数的波动以及工况模式的切换，从而恶化了其实际的节油效果。法国石油研究院IFP的Tona[8等人研究指出ORC系统在动态变工况条件下的优化控制是其应用的主要瓶颈。

此外，热机不可能从单一热源取热，并使之完全转化为有用功而不产生其它影响。ORC系统在回收发动机排气能量发电的同时，也通过冷凝器将低温热量释放到发动机冷却系统当中，增加了冷却系统的散热负荷和散热功耗。HorstTA等[9]的研究表明，ORC系统散热会增加冷却水泵的功耗，从而导致其节油潜力下降了 $1 . 3 \% 1 . 8 \%$ 。ORC系统回收的余热能越多，其散热需求也越大，冷却系统的散热功耗也会越大。ORC系统发电和发动机冷却系统耗电两者之间存在着一定的盈亏耦合关系[10]。

可以发现，ORC系统在回收车用内燃机排气能量时，会呈现出强烈的动态特征和耦合特征，使得ORC系统在动态变工况条件下的优化决策和控制实施均存在严峻挑战。为此，本文以ORC系统的动态特征和耦合特征为核心，旨在建立面向ORC系统优化控制的效率预测模型，支持对蒸发压力和冷凝压力进行在线决策和控制。

# 1问题描述

# 1.1研究对象

图1为本文研究对象的系统构型：采用ORC技术回收一台重型车用柴油机增压涡轮后的排气能量；并为ORC系统匹配了一套可控的冷却系统。

![](images/6a1eab3306e21ab99cc54a9318a86380acec71514c233c833056081448b138c1.jpg)  
图1柴油机ORC余热回收系统的构型示意图 Fig.1Schematic diagram of the diesel-engine ORC exhaust heat recoverysystem

# 1.2问题描述

ORC系统优化和控制研究的核心任务是：在道路运行过程中，根据排气流量和排气温度的瞬变特征，以系统效率最优为目标，实时决策ORC系统的运行状态，并通过控制手段加以实现。ORC系统的系统效率为

$$
\eta _ { S y s t e m } = \frac { W _ { _ { R C } } - W _ { c } } { E _ { E x } }
$$

$$
= f ( X _ { _ { R C } } \vert R _ { _ { E x } } )
$$

式中， $\eta _ { s y s t e m }$ 为系统效率， $E _ { \scriptscriptstyle E x }$ 为排气能量， $W _ { R C }$ 为ORC系统的循环净功， $W _ { c }$ 为冷却附件的功率消耗，$R _ { E x }$ 表示排气边界条件， $X _ { _ { R C } }$ 表示ORC系统的运行状态，包括蒸发压力、过热度、冷凝压力和过冷度。

想要在整个动态运行历程中，时刻保持ORC系统工作在最佳状态，获得最优的系统效率，则需要在每一个控制步长，根据排气边界条件，包括排气温度和排气流量，优化和控制ORC系统的蒸发压力、过热度、冷凝压力和过冷度。其中，根据近期的研究[6,10]可以发现，过热度和过冷度的最优取值比较简单，不会随着运行工况的变化而变化。然而，蒸发压力和冷凝压力的最优化规律尚不清晰，分而论之，主要有如下三点原因：

# 1.2.1 动态特性

稳态研究[表明，最优的蒸发压力与排气温度正相关。排气温度和蒸发压力在数值上是一一对应的，但在动态运行过程中，两者在时间上并不一致，存在一定的时间差，因为发动机和ORC 两个系统转化能量的时间尺度存在较大差异，如表1所示。

表1发动机与ORC系统能量转化特征的对比 Tablel Comparison of energy conversion features between   

<html><body><table><tr><td>engire</td><td>发动机</td><td>ORC系统</td></tr><tr><td>装置工作方式</td><td>往复</td><td>连续</td></tr><tr><td>能量转化方式</td><td>缸内燃烧</td><td>间壁传热</td></tr><tr><td>动态时间尺度</td><td>快：工作循环</td><td>慢：分钟</td></tr></table></body></html>

发动机往复式的工作方式，以及爆炸燃烧的能量释放形式，使得燃油的化学能在一个工作循环内完成到机械能的转化；其能量转化的动态时间尺度较快，为一个工作循环。然而，ORC的工作方式是连续的；发动机瞬态的排气能量经过间壁传热被ORC工质吸收，加热蒸发，推动膨胀机做功产生电能；系统的传热和流动惯性使得ORC能量转化的动态时间尺度较大，需要几十秒甚至数分钟，如表1所示。这种动态特征使得蒸发压力和排气温度一一对应的稳态控制律在动态运行过程中无法实施，需要对蒸发压力进行在线优化。

# 1.2.1工况特性

Tona[8等人研究指出，ORC系统从冷起动开始，逐渐被加热、升压，直至完全蒸发、过热，到推动膨胀机对外输出做功，会经历一系列的动态过程。Xiel6等人将其定义为四种基本的工况模式，包括起动模式、冲转模式、做功模式和保护模式。并指出工况模式的波动会降低ORC系统的有效做功时间，进而影响节油效果的发挥。因此，在道路运行过程中，ORC系统优化与控制更大的任务是调节蒸发压力，避免ORC系统落入到保护模式，缓解工况模式的波动，提高ORC系统有效做功时间。因此，调节蒸发压力不单单是优化ORC系统在每一个控制步长上的系统效率，更重要的是，避免ORC系统工况模式的波动。

![](images/e219d997fcb7e40225cfde8319bb1ebe4a1510a87797d6088237ddc98e4fb7da.jpg)  
图2ORC系统动态的工作过程及模式定义 Fig.2Dynamic working process and mode definition of the ORC system   
图3冷凝压力对耦合关系的调控作用 Fig.3Effects of the condensing pressure on the profit-loss relationship

# 1.2.1耦合特性

热机不可能从单一热源取热，并使之完全转化为有用功而不产生其它影响。ORC系统在回收发动机排气能量发电的同时，也通过冷凝器将低温热量释放到发动机冷却系统当中，增加了冷却系统的散热负荷和散热功耗。Yang[10]]等人研究表明，ORC系统回收的余热能越多，其散热需求也越大，冷却系统的散热功耗也会越大。ORC系统发电和发动机冷却系统耗电两者之间存在强烈的耦合关系，如图3所示。而冷凝压力的取值对这种耦合关系有着强烈的调控作用，应随着发动机转速和负荷的增加而增加。换句话说，冷凝压力的最优取值也受到排气条件的强烈影响。

14 公 12 OR压电功率外包络线 O—冷凝压力4bar 10 △—冷凝压力5bar —冷凝压力6bar 8 ◇冷凝压力7bar 个—冷凝压力8bar 6 盈亏平衡线 4 2 0 0 2 4 6 8 10 12 14 ORC系统的发电功率[kW]

综上所述，在道路运行过程中，因为ORC系统的动态特性、工况特征和耦合特性，使得蒸发压力和冷凝压力的优化和控制存在严峻挑战，而建立面向ORC系统优化控制的效率预测模型是突破这一挑战的关键。

# 2 效率预测模型

# 2.1控制架构

综合考虑ORC系统的动态特性、工况特征和耦合特性，提出了ORC系统的优化控制架构，如图4所示。针对给定排气边界条件 $R _ { { } _ { E x } }$ ，管理器和效率观测器协同工作，优化得到最优的蒸发压力$P _ { R C , 3 }$ 和冷凝压力 $P _ { R C , 4 }$ ，和蒸汽温度 $T _ { R C , 3 }$ 和透平转速$N _ { { R C } , T }$ 一起作为控制器的控制目标 $Y _ { R C , S e t }$ ；在控制层面直接采用成熟的PID控制算法，控制ORC系统透平转速、膨胀比，工质泵流量，以及冷却系统附件功率等。该架构的关键之处在于建立一个宏观的、具有预测功能的效率模型。

# 2.2效率模型

根据图4，效率模型的核心功能是：在管理器的任意决策时刻 $\kappa$ ，根据该时刻的排气参数 $R _ { E x } ( \kappa )$ 以及ORC系统的状态参数 $X _ { _ { R C } } ( \kappa )$ ，需要预测，如果管理器给出决策变量为 $X _ { _ { R C , O p t } } ( \kappa )$ ，则在 $\kappa { + } 1$ 时刻ORC系统的工况模式、输出功率以及冷却功耗，将系统效率 $\eta _ { s y s t e m } \left( \kappa + 1 \right)$ 反馈给管理器。系统效率 $\eta _ { s y s t e m }$ （204号的定义式为公式（2）。

![](images/0de70be0ea449d3355b7a562090a6ab694689a28885fa214173a8b0cbbc7507d.jpg)  
Fig.4 Control framework of the ORC exhaust heat recovery system

$$
\begin{array} { r l r } {  { \eta _ { S y s t e m } = \frac { W _ { R C } ( \tau ) - W _ { C } ( \tau ) } { E _ { E x } } \xi _ { m } } } \\ & { } & { ~ = f ( R _ { E x } , X _ { R C , O p t } , Y _ { R C } ) } \end{array}
$$

其中， $E _ { \scriptscriptstyle E x }$ 表示发动机的排气能量， $W _ { R C } ( \tau )$ 表示ORC系统未来一段时间内的发电量， $W _ { c } ( \tau )$ 表示冷却系统所消耗的功率， $\xi _ { m }$ 表示ORC系统的工况模式。

根据ORC系统的动态特性，发动机工作循环是其完成能量转化的基本时间单位，如果以发动机的工作循环为时间基准的话，ORC系统的动态特性非常显著，其能量转换的时间尺度远大于一个发动机工作循环。因此ORC系统的发电量是一个动态模型，用 $W _ { R C } ( \tau )$ 表示，其中 $\tau$ 表示时间。相应的，ORC系统发电所需要的冷却功耗用 $W _ { c } ( \tau )$ 表示。

除此之外，ORC系统的效率模型还需要具备一项重要的功能，就是预测ORC系统的工况模式，其对于系统效率 $\eta _ { s y s t e m }$ 而言是一个0-1关系。准确地预测ORC系统的工况模式，是避免其模式波动，提高做功模式所占时间比例的关键。

总之，ORC系统的效率模型描述的对象包括ORC系统及其控制器，需要能够动态地预测ORC系统的工况模式 $\xi _ { m }$ 、发电功率 $W _ { R C } ( \tau )$ 以及冷却功耗 $W _ { c } ( \tau )$ ，其建模思路如图5所示。

利用蒸发器的传热动态效应，建立ORC系统吸热量的实时预测模型；考虑管理器的决策变量以及控制器的执行能力，基于ORC系统的热力学模型，预测ORC系统的输出功率、散热量以及过热度；并根据冷却功耗模型和工况模型，预测冷却功耗和工况模式，在此基础上计算ORC系统的效率。

在效率模型的建立过程中，首先作如下两点假设：

1）管理器给出的决策变量 $X _ { R C , O p t }$ 被控制器完全执行，不考虑执行器的执行过程和执行能力。  
2) 不考虑膨胀机、发电机、工质泵、冷却系统和阀门的硬件执行过程，只关注其输出量，包括膨胀比πRc.τ、发电负载TRC.load \`工质流量 $n _ { \mathcal { K } , L } ^ { \ell }$ 、冷却附件功率 $W _ { c }$ 和阀门开度Valves。

![](images/0a54685a50c4b83c45ea6508aabc92a389055f41361f12be503131022954967a.jpg)  
图4ORC余热回收系统的优化控制架构  
图5ORC系统效率预测模型的建模思路  
Fig.5 Structure diagram of the ORC system efficiency modeling

# 2.2.1有效吸热量

ORC系统的有效吸热量受到蒸发器对流换热过程的控制，考虑到所建效率模型需要在控制器中实时计算，因此，其模型不能够过于复杂，需要在描述精度和计算实时性之间进行折中处理，然后将模型中不准确的部分用先进的控制算法进行补偿。因此，蒸发器对流换热过程的描述采用基于集总参数法的平均值模型。

在排气侧，排气外掠叉排管束换热过程的控制方程包括，对流换热方程、能量守恒方程和对数温差方程，如公式（2）、（3）和（4)，

$$
Q _ { E x } = h _ { E x } A _ { E x } \overline { { \Delta T _ { E x } } }
$$

$$
Q _ { E x } = c _ { E x } n \pmb { \mathrm { \& } } _ { E x } ( T _ { E x , i n } - T _ { E x , o u t } )
$$

$$
\overline { { \Delta T _ { E x } } } = \frac { \Delta T _ { E x , i n } - \Delta T _ { E x , o u t } } { \ln { \frac { \Delta T _ { E x , i n } } { \Delta T _ { E x , o u t } } } }
$$

其中， $h _ { { } _ { E x } }$ 为排气侧的平均换热系统，其服从茹卡乌斯卡斯（Zhukauskas）换热准则，在此基础上可以增加排气换热系数的标定因子 $\lambda _ { E x }$ ； $A _ { E x }$ 表示排气侧的有效换热面积， $n _ { \mathrm { { E } } x } ^ { \& }$ 表示排气的质量流量， $T _ { E x , i n }$ 和$T _ { _ { E x , o u t } }$ 分别为排气在蒸发器入口处、出口处与管壁平均温度 $T _ { _ { E P } }$ 的差值， $c _ { _ { E x } }$ 为柴油机排气的比热容，工程上常取值为 $1 . 0 8 8 \mathrm { k J / ( k g \cdot K ) }$ 。联立求解可以得到，

$$
\begin{array} { r } { Q _ { _ { E x } } = c _ { _ { E x } } n \pmb { \beta } _ { E x } ( T _ { E x , i n } - T _ { E P } ) ( 1 - e ^ { - \frac { h _ { E x } A _ { E x } } { c _ { _ { E x } } n \pmb { \beta } _ { E x } ^ { * } } } ) } \end{array}
$$

公式（5）可以解读为两个部分，最大换热量QEx Max和排气侧换热效率 $\eta _ { _ { E x , E } }$ ，分别可表示为

$$
Q _ { { } _ { E x , M a x } } = c _ { { } _ { E x } } n \pmb { \beta } _ { { } _ { E x } } ( T _ { E x , i n } - T _ { E P } )
$$

$$
\eta _ { _ { E x , E } } = 1 - e ^ { - \frac { h _ { E x } A _ { E x } } { c _ { E x } n _ { E x } ^ { 8 } } }
$$

在公式（7）中，指数项表征了排气的实际换热热流与可传递的最大热流密度的比值，其可进一步表示为，

$$
\eta _ { _ { E x , E } } = 1 - e ^ { - \zeta \times S t }
$$

其中， $S t$ 为斯坦顿数，是表征强制对流强弱的一个无量纲书。 $S t$ 越大，发生于排气与蒸发器管壁之间的对流换热过程就愈强烈。 $\zeta$ 是排气的换热面积与通流面积之比。 $\zeta$ 越大，排气与蒸发器管壁之间的换热过程进行得越充分，换热效率越高。需要说明的是，蒸发器管壁的平均温度 $T _ { _ { E P } }$ 不能直接测量。但是，因为管壁蓄热作用的存在，其温度不可能快速变换，因此可以迭代求解，在 $\kappa { + } 1$ 时刻，可以采用第 $\kappa$ 时刻的管壁温度 $T _ { _ { E P } } ( \kappa )$ 来计算排气侧的换热量 $Q _ { E x } ( \kappa )$ ，然后，根据管壁的能量守恒重新计算 $\kappa { + } 1$ 时刻对应的管壁温度 $T _ { _ { E P } } ( \kappa + 1 )$ 。

在计算得到排气换热量 $Q _ { \scriptscriptstyle E x }$ 之后，可以根据蒸发器管壁的集总传热模型，计算ORC工质的有效吸热量 $Q _ { R C , e f f }$ ，其控制方程为

$$
c _ { E P } m _ { { } _ { E P } } \frac { d T _ { E P } } { d \tau } = Q _ { { } _ { E x } } - Q _ { { } _ { R C , e f f } }
$$

$$
Q _ { R C , e f f } = h _ { R C , E A _ { R C , E } } ( T _ { E P } - \overline { { T _ { R C , E } } } )
$$

如前面所述，在控制器功能执行完美的假设下，液相、两相和汽相的边界相对稳定，故可认为工质在蒸发器中换热的平均温度TRc.E受到蒸发压力PRC.3唯一控制，蒸发压力高，则平均温度高， $\overline { { T _ { R C , E } } }$ 是关于决策量 $P _ { R C , 3 }$ 的函数。在这样的条件下，公式（9)和公式（10）无法得到解析解，微分方程组联立求解的计算负担是内燃机控制器无法承担的，必须得换一种角度来解决这个问题。

假设第 $\kappa$ 时刻的蒸发压力为 $P _ { R C , 3 } ( \kappa )$ ，在 $\kappa { + } 1$ 时刻管理器给出蒸发压力决策值为 $P _ { R C , 3 } ( \kappa + 1 )$ ，并且$P _ { R C , 3 } ( \kappa + 1 ) \neq P _ { R C , 3 } ( \kappa )$ ，那么工质的平均温度必然会发生相应的变化，使得 $\overline { { T _ { R C , { \cal E } } ( \kappa + 1 ) } } \ne \overline { { T _ { R C , { \cal E } } ( \kappa ) } }$ 。然而，因为蒸发器管壁的蓄热作用，其温度 $T _ { _ { E P } }$ 不会立即发生改变。根据（10）可知，其有效吸热量$\mathcal { Q } _ { R C ~ e } \{ \kappa + 1 )$ 会因为工质平均温度 $\overline { { T _ { R C , \ E } ( \kappa + 1 ) } }$ 的突变而产生一个脉冲响应，脉冲能量的大小等于蒸发器管壁因为温度变化而释放或者吸收的能量。如果$P _ { R C , 3 } ( \kappa + 1 ) < P _ { R C , 3 } ( \kappa )$ ，则蒸发器管壁释放能量；反之则吸收能量，其值表征为

$$
\delta ( Q _ { _ { E P } } ) = c _ { _ { E P } } m _ { _ { E P } } \Delta T _ { _ { E P } }
$$

其中， $\Delta T _ { _ { E P } }$ 可以表示为蒸发压力 $P _ { R C , 3 }$ 变化而导致工质饱和温度变化量 $\Delta T _ { R C , S }$ 的线性关系，系数为 $\lambda _ { E P }$ 。通过这种处理，可将公式（9）和（10）改造为

$$
Q _ { R C , e f f } ^ { } = \frac { Q _ { E x } + \delta ( Q _ { E P } ) } { 1 + T _ { C H T } }
$$

其中， $T _ { C H T }$ 表示蒸发器动态传热的惯性时间常数，表征了蒸发器的蓄热能力与工质换热能力的比值。考虑到工质侧换热系数预测的复杂性，其惯性时间$T _ { C H T }$ 可通过激励试验得到，并且考虑到流量和温度对雷诺数和物性参数的影响，故对激励试验得到的惯性时间进行流量和温度修正，修正因子为 $\lambda _ { R C , n \alpha }$ 和$\lambda _ { R C , T }$ 。在此基础上，根据公式（5）和公式（12）可以实时预测ORC系统蒸发器的有效吸热量

$Q _ { R C , e f f } ( \tau )$ 。

# 2.2.2工况模式因子

工况模式 $\xi _ { m }$ 是一个0-1 变量，在有效吸热量$\boldsymbol { Q } _ { R C , e f f }$ 给定的情况下，受到决策变量 $P _ { R C , 3 }$ ，以及控制器调节质量流量 $n _ { \mathcal { k } _ { L } } ^ { \& }$ 的共同影响，但是管理器需要知道当决策变量Prc.3被执行，且质量流量c.L来不及调节时，ORC系统的工况模式 $\xi _ { m }$ ，是否有可能落入到保护模式，关注的是一种可能性。

对于给定的有效吸热量 $\boldsymbol { Q } _ { R C , e f f }$ ，以及决策变量$P _ { R C , 3 }$ ，计算当决策变量 $P _ { R C , 4 }$ 和控制器调节质量流量 $n _ { \mathcal { K } , L } ^ { \ell }$ 来不及影响蒸汽状态时，ORC系统瞬时的工况模式 $\xi _ { m }$ 。也就是说，在第 $\kappa$ 时刻，ORC系统工质在蒸发器入口的温度 $T _ { R C , 2 } ( \kappa )$ 和质量流量$r \big \& _ { \scriptscriptstyle \mathcal { R } C , V } ( \kappa )$ 与第 $\kappa { - } 1$ 时刻的值相同，那么要使蒸发器出口蒸汽的温度达到蒸发压力 $P _ { R C , 3 }$ 对应的安全温度 $T _ { R C , 3 , m i n }$ ，则需要的最小能量 $Q _ { R C , e f f , m i n } ( \kappa )$ 为

$$
Q _ { R C , e f f , m i n } ( \kappa ) = n \& _ { R C , V } ( \kappa - 1 ) ( h _ { R C , 3 , m i n } - h _ { R C , 2 } ( \kappa - 1 ) )
$$

则工况模式 $\xi _ { m }$ 为

$$
\xi _ { { \scriptscriptstyle m } } ( \kappa ) = i f ( Q _ { R C , e f f } ( \kappa ) - Q _ { R C , e f f , m i n } ( \kappa ) )
$$

其含义为，如果有效吸热量 $Q _ { R C , e f f } ( \kappa )$ 大于$Q _ { R C , e f f , m i n } ( \kappa )$ ，则ORC 系统工作在做功模式， $\xi _ { { \scriptscriptstyle m } }$ 取值为1；反之ORC系统会进入到保护模式， $\xi _ { { \scriptscriptstyle m } }$ 取值为0。

# 2.2.3冷却消耗功率

ORC系统发电功率 $W _ { R C } ( \tau )$ 表示当决策变量$P _ { R C , 3 }$ 和 $P _ { R C , 4 }$ 在一个决策周期内的被控制器完全执行之后的预测值。ORC系统中工质泵入口为状态1点，如图6所示，其饱和压力为 $P _ { R C , 4 }$ ，其比焓为$H _ { R C , 1 }$ ；根据工质泵的效率 $\eta _ { _ { R C , P S } }$ 可以计算得到2的状态，用一对变量 $( \ P _ { R C , 3 } \ , \ T _ { R C , 2 } \ )$ ）表示，其比焓为 $H _ { R C , 2 }$ ；3点的状态由决策变量 $P _ { R C , 3 }$ 控制，用一对变量（ $\langle P _ { R C , 3 } , \quad T _ { R C , 3 } \rangle$ ，其比焓为 $H _ { R C , 3 }$ ；最后，根据膨胀机的等熵效率 $\eta _ { R C , T S }$ 可以计算得到4 点比焓为 $H _ { R C , 4 }$ ，在此基础上，调用REFPROP软件，可以计算得到ORC系统在该条件下的循环效率为

$$
\eta _ { R C , C y c l e } = \frac { ( H _ { R C , 3 } - H _ { R C , 4 } ) - ( H _ { R C 2 } - H _ { R C 1 } ) } { H _ { R C , 3 } - H _ { R C 2 } }
$$

则ORC系统发电功率的预测值为

$$
W _ { R C } ( \tau ) = \mathcal { Q } _ { R C , e f f } \left( \tau \right) \eta _ { R C , C y c l e }
$$

同时，冷凝器的散热量为

$$
Q _ { R C , \mathrm { C o n } } ( \tau ) = Q _ { R C , e f f } ( \tau ) ( 1 - \eta _ { R C , C y c l e } )
$$

![](images/33e01378f2086c3fcc37ca5c317e345da46bb1874a31ae3169d3341bb1006c7a.jpg)  
图6ORC系统循环示意图  
Fig.6 Thermodynamic cycle diagram of the ORC system

ORC系统冷却消耗功率主要包括水泵功耗、风扇功耗和迎风阻力产生的功耗。

对于水泵，其功耗可表示为

$$
W _ { { \scriptscriptstyle C P } } = \lambda _ { 1 } \ l { } { \ l } { \ l } { \ l } _ { C P } ^ { \& } \Delta { \cal P } _ { { \scriptscriptstyle C P } }
$$

式中， $\lambda _ { 1 }$ 是水泵的效率的倒数， $\beta _ { C P } ^ { \& }$ 表示工质经过水泵的体积流率， $\Delta P _ { c P }$ 表示水泵的实际扬程。当然，对于冷却水的流动循环而言，水泵的扬程其实是为了克服管路阻力，包括沿程损失和局部损失。因此，水泵的扬程 $\Delta P _ { C P }$ 可近似表示为

$$
\Delta P _ { C P } = \lambda _ { 2 } \ l { \vert } \& { } _ { P }
$$

将忽略一次项所产生的误差放在系数 $\lambda _ { 2 }$ 中进行标定，故整合公式（18）和公式（19）可以得到

$$
W _ { C P } = \lambda _ { 1 } \lambda _ { 2 } \ltimes \ltimes \ l ^ { 3 }
$$

一般地，冷却水流量和散热量直接相关，可以将公式（20）变形为

$$
W _ { C P } = \lambda _ { 1 } \lambda _ { 2 } \lambda _ { 3 } Q _ { C o n } ^ { 3 }
$$

式中， $\boldsymbol { Q } _ { c o n }$ 为冷凝器中的散热量。在公式（21）的基础上，可以将 $\lambda _ { 1 } , ~ \lambda _ { 2 }$ 和 $\lambda _ { 3 }$ 合并，得到

$$
W _ { { \scriptscriptstyle C P } } = \lambda _ { { \scriptscriptstyle C P } } Q _ { { \scriptscriptstyle C o n } } ^ { 3 }
$$

同理，可以推导得到风扇功耗，以及迎风阻力所产生功耗的表征模型，如公式（23）和（24)，

$$
\begin{array} { l } { { W _ { _ { C F } } = \beta _ { _ { C F } } Q _ { _ { R a d , F } } ^ { 3 } } } \\ { { W _ { _ { C D } } = \gamma _ { _ { C D } } Q _ { _ { R a d , D } } ^ { 3 } } } \end{array}
$$

其中， $Q _ { R a d , F }$ 和 $Q _ { R a d , D }$ 分别表示风扇冷却和迎风冷却从散热水箱中带走的热量。迎风冷却是被动作用的，受道路工况影响，而风扇辅助冷却是可以主动调节的，但两者的效率相差很大。如果是风扇辅助冷却，那么其功耗为

$$
W _ { { \scriptscriptstyle C F } } = \beta _ { 1 } \beta _ { { \scriptscriptstyle C F } } ^ { \& } \Delta P _ { { \scriptscriptstyle C F } }
$$

如果是迎风冷却，其阻力所产生的功耗近似为

$$
W _ { { \scriptscriptstyle C D } } = \ l [ \& \ r _ { { D } } \Delta P _ { { \scriptscriptstyle C D } }
$$

因为迎风冷却是直接作用，没有能量转化环节，效率近似为 $100 \%$ ；而风扇是一个效率较低部件，其等熵效率通常在 $30 \%$ 以下。引入一个迎风冷却的比例因子 $\omega _ { \scriptscriptstyle R }$ ，表征了ORC系统与发动机冷却系统的集成程度。当迎风冷却所占比例增高时，ORC放热过程的能效比增大。将公式（23）和（24）合并，得到

$$
W _ { C } = f ( \omega _ { R } ) Q _ { R a d } ^ { 3 }
$$

根据能量守恒，冷凝器的散热量和散热水箱的散热量相等，即

$$
Q _ { R C , c o n } = Q _ { c o n } = Q _ { R a d }
$$

根据公式（22）和（27)，可以得到放热过程总功耗的特征模型

$$
W _ { C } = ( \lambda _ { C } + f ( \omega _ { R } ) ) Q _ { R C , c o n } ^ { 3 }
$$

定义公式（29）中子项“ $\lambda _ { c } + f ( \omega _ { R } )$ ”的倒数为ORC冷却系统的能效系数 $C O P _ { c o r r }$ ，受冷凝压力控制。根据Yang[10]等人的研究结果，当全部采用风扇冷却时，

$$
\begin{array} { c } { { C O P _ { C o r r } = - 3 6 7 5 \times P _ { R C , 4 } ^ { 3 } + 6 8 4 2 0 \times P _ { R C , 4 } ^ { 2 } } } \\ { { - 2 8 5 2 0 0 \times P _ { R C , 4 } + 4 2 9 3 0 0 } } \end{array}
$$

# 2.2.4效率模型集成

根据效率模型的建立过程，将公式（12）采用后向离散处理可以得到

$$
\begin{array} { l } { \displaystyle { Q _ { R C , e f f } \left( \kappa \right) - ( 1 - \frac { \Delta \tau } { T _ { C H T } \left( \kappa \right) } ) Q _ { R C , e f f } \left( \kappa - 1 \right) } } \\ { \displaystyle { = \frac { \Delta \tau } { T _ { C H T } } ( Q _ { { \cal E } x } \left( \kappa \right) + \delta ( Q _ { { \cal E } P } \left( \kappa \right) ) ) } } \end{array}
$$

其中， $\Delta \tau$ 为决策步长，第 $\kappa$ 时刻排气的放热量$Q _ { E x } ( \kappa )$ 为

$Q _ { E x } ( \kappa ) = c _ { E x } n _ { E x } ^ { \vartheta } ( \kappa ) ( T _ { E x , i n } ( \kappa ) - T _ { E P } ( \kappa - 1 ) ) \eta _ { E x , E }$ (32式中，蒸发器管壁的平均温度采用第 $\kappa { - } 1$ 时刻的温度值，而第 $\kappa$ 时刻的温度值可由公式（33）进行计算，

$$
\begin{array} { l } { { c _ { \scriptscriptstyle E P } m _ { \scriptscriptstyle E P } \left( T _ { \scriptscriptstyle E P } \left( \kappa \right) - T _ { \scriptscriptstyle E P } \left( \kappa - 1 \right) \right) } } \\ { { \mathrm { } } } \\ { { \mathrm { } = Q _ { \scriptscriptstyle E x } \left( \kappa \right) - Q _ { \scriptscriptstyle R C , \it e f f } \left( \kappa \right) } } \end{array}
$$

第 $\kappa$ 时刻，因为决策变量 $P _ { R C , 3 } ( \kappa )$ 变化导致蒸发器管壁热容吸收或者释放的脉冲能量 $\delta ( Q _ { \scriptscriptstyle E P } ( \kappa ) )$ 为

$$
\delta ( Q _ { _ { E P } } ( \kappa ) ) = c _ { _ { E P } } m _ { _ { E P } } \lambda _ { _ { E P } } \Delta T _ { _ { R C , S } } ( \kappa )
$$

式中， $\Delta T _ { R C , S } ( \kappa )$ 表示第 $\kappa$ 时刻决策变量 $P _ { R C , 3 } ( \kappa )$ 对应的工质的饱和温度，与第 $\kappa { - } 1$ 时刻决策变量PRc.3(K-1)对应的工质的饱和温度之差。

并根据（14）、（16）和（29）进行分别计算第$\kappa$ 时刻的工况模式 $\xi _ { m } ( \kappa )$ 、发电功率 $W _ { R C } ( \kappa )$ 和冷却功耗 $W _ { C } ( \kappa )$ ，其离散形式为

$$
\xi _ { { \scriptscriptstyle m } } ( \kappa ) = i f ( Q _ { R C , e f f } ( \kappa ) - Q _ { R C , e f f , m i n } ( \kappa ) )
$$

$$
W _ { R C } ( \kappa ) = Q _ { R C , e f f } \left( \kappa \right) \eta _ { R C , C y c l e } ( \kappa )
$$

$$
W _ { C } ( \kappa ) = \frac { \left[ Q _ { R C , e f f } ( \kappa ) ( 1 - \eta _ { R C , C y c l e } ( \kappa ) ) \right] ^ { 3 } } { C O P _ { C o r r } ( \kappa ) }
$$

由此，可计算ORC系统在第 $\kappa$ 时刻的系统效率为

$$
\eta _ { S y s t e m } = \frac { W _ { R C } ( \kappa ) - W _ { C } ( \kappa ) } { E _ { E x } ( \kappa ) } \xi _ { m } ( \kappa )
$$

总共有四个系数需要标定，分别为排气侧换热系数缩放因子 $\lambda _ { E x }$ ,惯性时间 $T _ { C H T }$ 的流量修正因子 $\lambda _ { R C , n \alpha }$ 和温度修正因子 $\lambda _ { R C , T }$ ，以及蒸发器管壁热容吸收或者释放的脉冲能量温差修正因子 $\lambda _ { E P }$ 。

# 3效率模型验证

基于文献[所示仿真平台，对所建效率模型进行验证，并且应用到图4所示的控制架构中，对ORC系统进行在线优化和管理，从应用效果上进一步验证所建立效率模型的有效性。

# 3.1模型精度验证

在低转速小负荷，到高转速大负荷四个工况点对效率模型进行标定和校准，参数设置如表2所示。效率模型的校准结果如图7所示。

表2参数设置Table2 Parameters setup  

<html><body><table><tr><td>变量</td><td>取值</td><td>单位</td></tr><tr><td>工况</td><td>ESC工况（除怠速点）</td><td></td></tr><tr><td>工质</td><td>R123</td><td>:</td></tr><tr><td>蒸发压力</td><td>3</td><td>MPa</td></tr><tr><td>过热度</td><td>10</td><td>K</td></tr><tr><td>冷凝压力</td><td>0.4</td><td>MPa</td></tr><tr><td>冷却方式</td><td>水冷 (风扇辅助)</td><td>二</td></tr></table></body></html>

![](images/0465abd8a85fa83ab228c2d4addded8b4ce7ab3b2072b142722ef7283ec43331.jpg)  
图7效率模型与仿真模型的对标结果 Fig.7 Calibration of the efficiency model

虽然无法获得足够的试验数据验证所建立的效率模型，但是如果所建立的效率模型在趋势上完全能够与详细的仿真模型吻合，有潜力代替详细的

仿真模型，用于ORC余热回收系统的在线优化与控制。

# 3.2模型应用验证

将所建立的效率应用到图4所示ORC系统的优化控制架构中，在线优化决策蒸发压力和冷凝压力，改善ORC系统的动态特性、工况特性和耦合特性。

车辆满载，且完全采用风扇冷却，在HWFET工况，对所建立效率模型进行应用效果的验证。需要说明的是：HWFET工况时间为765s，时间是有限的，因此，需要控制ORC系统的热容量，否则起动时间太长，反而无法验证控制方法的有效性。因此，在该验证过程中，采用了较低的热容量，为$5 0 \mathrm { k g }$ 不锈钢当量；在该条件下，因为蒸发器管壁的蓄热能力较差，对排气扰动的缓冲能力不足，其对ORC系统的蒸汽状态影响较大，在这样比较不利的条件下，验证所提出的控制架构和效率模型，应该更具有普适性。验证结果如图8所示。

![](images/837187c373172b88a84273f2c670a45bbb2a80b3e3bbc364b1b3ba030ae55c2a.jpg)  
图8ORC系统在HWFET工况下的控制效果  
Fig.8 Control effect of the ORC system during the HWFET driving cycle

制的实现过程阐述如下：

1) 采用低压起动策略，缩短ORC系统起动时间。

2）在起动过程中，冷凝压力为上限值$\mathbf { 0 . 8 M P a }$ ，仕台架运行中该值会受到工质泵入口压力的限制。该决策使得冷却系统不工作，一方面可以降低冷却水泵和冷却风扇的功耗；另一方面可以热量的散失，促进ORC 系统快速暖机和起动。

3）ORC系统在起动、冲转之后，进入到做功模式。在该模式下，管理器与效率模型协同工作，完成三大功能：1是工况模式的管理，尽可能避免ORC系统进入到保护模式；2 是动态效率的优化，在一段时间内，控制ORC系统的蒸发压力与排气温度相适应，提高ORC系统效率；3盈亏耦合关系的平衡，管理冷凝压力，优化调节ORC系统发电与冷却系统功耗之间的盈亏关系。具体实现结果如下：a）当车辆突然减速，排气能量不足，蒸汽温度下降，过热度也会下降；这时，通过降低蒸发压力，维持蒸汽的过热度，避免其在短时间内跌破安全限值而进入到保护模式。当然，与此同时，控制器也会使得工质泵的流量降低，与蒸发压力协同配合，在整个循环工况中，ORC系统的蒸汽过热度一直控制在10K左右的水平。b）当车辆高速巡航，或者加速时，排气能量充足，蒸汽过热度有充分的保障，在这种情况下，蒸发压力逐渐升高，保持ORC 系统的高效运行。c）针对ORC 系统发电与冷却系统功耗之间盈亏关系的平衡问题，当车辆加速时，ORC系统的持续吸热量和散热量都较大，冷却系统负荷比较大，这时，通过提高冷凝压力的控制目标，增大冷却系统的散热温差和能效比，降低冷却系统功耗；当车辆减速或者巡航时，ORC系统的持续吸热量和散热量较小，冷却系统的功耗比较小，在这种情况下，降低冷凝压力的控制目标，以提高ORC系统的转化效率为主。

总体而言，采用所建立的效率模型和控制架构，ORC系统的有效做功时间达到 $94 \%$ ，蒸汽过热度控制在5K-15K之间，散热功耗与发电功率的比值维持在 $20 \%$ 以下，在HWFET工况中的节油效果为 $2 . 2 \% .$ 一 $- 2 . 8 \%$ 。

# 4结论

本文为突破ORC余热回收系统在线优化控制的瓶颈，综合考虑ORC系统的动态特性、工况特性和耦合特性，建立了ORC系统的效率预测模型，并提出了基于效率预测模型的在线优化控制架构和策略，仿真结果验证了效率模型和控制架构的有效性，形成如下结论：

1）柴油机ORC 余热回收系统存在强烈的动态特性、工况特性和耦合特性，使得基于稳态标定的优化控制律在动态运行过程中无法实施，需要对蒸发压力和冷凝压力进行在线优化。  
2) 以ORC系统的热力学第一定律模型为基础，抓住蒸发器阶跃响应的宏观特征，提出了有效换热量的动态修正模型，以及工况模式切换的预判因子，并采用简化机理和数据建模相结合的方法，建立了冷凝器散热功耗的经验模型，集成建立了ORC余热回收系统的效率预测模型。  
3） 所建效率预测模型在仿真平台上的对标误差小于 $5 \%$ ，且在趋势上完全能够与详细的仿真模型吻合，可用于ORC余热回收系统的在线优化与控制。  
4) HWFET道路仿真结果从应用效果上验证了所建效率预测模型的有效性，ORC系统的有效做功时间达到 $94 \%$ ，蒸汽过热度控制在5K-15K之间，散热功耗与发电功率的比值维持在 $20 \%$ 以下。

# 参考文献

[1] Taylor A M K P. Science Review of Internal Combustion Engines [J]．Energy Policy，2008，36: 4657-4667.   
[2] RinglerJ, SeifertM,GuyototV,etal.Rankine Cycle for Waste Heat Recovery of IC Engines [C]// SAE Paper. Detroit,Michigan,USA,2009,2009-01-0174.   
[3] TengH,Regner G,Cowland C.AchievingHigh Engine Efficiency forHeavy-DutyDieselEngines byWasteHeat Recovery Using Supercritical Organic-Fluid Rankine Cycle[C]// SAEPaper.Detroit,Michigan,USA,2006, 2006-01-3522.   
[4] Park T,Teng H,Hunter $\mathbf { G }$ et al.A Rankine Cycle System for Recovering Waste Heat from HD Diesel Engines-Experimental Results [C] // SAE Paper. Detroit, Michigan,USA,2011,2011-01-1337.   
[5] TengH,Klaver J,Park T, etal.ARankine Cycle System forRecoveringWasteHeat fromHD Diesel Engines-WHR System Development [C]// SAE Paper. Detroit,Michigan,USA,2011,2011-01-0311.   
[6] Xie H,Yang C.Dynamic Behavior of Rankine Cycle SystemforWasteHeatRecoveryofHeavyDutyDiesel Engines under Driving Cycle [J].Applied Energy,2013, 112: 130-141.   
[7] Yang C,Xie H, Zhou SK.Efficiency Analysis of the Rankine Cycle System Used for Engine Exhaust Energy Recovery under Driving Cycle [C]// SAE Paper.Detroit, Michigan,USA,2014,2014-01-0671.   
[8] TonaP,PeralezJ,Sciarretta A.Supervision and Control Prototyping for an Engine Exhaust Gas Heat Recovery System Based on a Steam Rankine Cycle [C]// IEEE/ASME International Conference on Advanced Intelligent Mechatronics.Kaohsiung,Taiwan:IEEE.2012: 695-701.   
[9] HorstTA,TegethoffW,EiltsP.Prediction ofDynamic Rankine Cycle Waste Heat Recovery Performance and Fuel Saving Potential in Passenger Car Applications ConsideringInteractionswithVehicles’Energy Management [J].Energy Conversion and Management, 2014,78: 438-451.   
[10] Yang C,Xie H, Zhou S K. Overall optimization of Rankine cycle system for waste heat recovery of heavy-dutyvehicle diesel engines considering the cooling power consumption [J].Science China Technological Sciences,2016,59(2):309-321.