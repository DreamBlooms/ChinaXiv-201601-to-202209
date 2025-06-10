# 热力学与传热学的共性理论基础 可逆与不可逆过程普适的有效能方程

陈则韶¹　李 川²　王 刚

(1．中国科学技术大学工程科学学院，合肥230027；2．中国科学技术大学国家同步辐射实验室，合肥230029;3．东北电力大学能源与动力工程学院，吉林 132012)

摘要回顾总结了热力学与传热学共性理论基础研究的系列成果，从正视热力学第二定律、“熵产”理论在实际应用中存在的问题入手，以势能理论为依据，用相对环境平衡态的势能为基准态势能定义了能量中的有效能和无效能。这种定义具有与“烟”相同的性质，又能从定义式直接写出有效能函数的表达式。继而利用热力学第一定律方程，推导出了普适的有效能方程、有效能率方程，并与熵方程、耗散方程和烟方程进行了比较。前者方程各项都只与状态有关，都能独立计算出来，而后三个方程都有一项与不可逆过程有关的补缺项。把有效能率方程应用于传热过程，导出了传热效率的表达式；应用于实际热机系统，导出了传热与热力耦合系统的输出功率、输入热流率、效率、换热器传热系数以及热源参数之间的关系，并举例应用于系统优化设计。本文构建的热力学和传热学共性理论，为热机与换热器耦合进行热力系统综合分析和协调优化提供了理论基础。

关键词热力学；传热学；有效能；有效能方程；不可逆热力学；传热效率中图分类号：TK123 文献标识码：A 文章编号:0253-231X(2017)08-1589-08

# Common Theoretical Foundation of Thermodynamics and Heat Transfer—Universal Effective Energy Equation for Reversible and Irreversible Processes

CHEN Ze-Shao1 LI Chuan² WANG Gang³

(1.School of Engineering Science,Universityof Science and Technology ofChina，Hefei 230o27,China; 2.National Synchrotron Radiation Laboratory, Universityof Scienceand Technologyof China，Hefei230029,China; 3.School of Energy and Power Engineering,Northeast Electric Power University，Jilin1320l2,China)

Abstract This paper reviews and summarizes the results of the basic research on the common theory of thermodynamics and heat transfer.Starting with the problems of the second law of thermodynamics and the“entropy generation” theory in practice, based on the theory of potential energy, the effective energy and the ineffcient energy are defined on the basis of the relative equilibrium state. This kind of definition has the same property as “exergy”，and the expression of effective energy function can be deduced directly from it. Then,by using the frst law of thermodynamics, the universal efective energy equation and effective energy rate equation are deduced and compared with the entropy equation,the entransy dissipation equation and the exergy equation. Each term of first two equations is only related to the state so that can be independently calculated,and the last three equations all need an adding term related with irreversible process.The effctive power rate equation is applied to the heat transfer process,and the expression of heat transfer efficiency is deduced. It is also applied to the actual heat engine system which is a coupling system of heat transfer and thermodynamics，and the relationship between output power， input heat fow rate, efficiency, heat transfer coefficient of the heat exchanger， and heat source parameters is deduced and applied to system optimization design. The common theory of thermodynamics and heat transfer,which is constructed in this paper，provides a theoretical basis for the analysis and optimization of the thermodynamic system which is coupled by heat engine and heat exchanger.

通信作者：李川，工程

Key wordsthermodynamics; heat transfer; efective energy; effective energy equation; irreversible thermodynamics；heat transfer efficiency

# 0引言

热力学[1,2]和传热学[3]同属热学，是工程热物理学科的两个重要基础分支学科，两个学科所建立的理论都是为提高热/功转换设备效率服务的。可是两个学科独立发展的理论体系，除了能量守恒有共同处以外，缺乏能在热力和传热耦合的实际的热力系统中去协同指导优化设计的理论。

热力学的基础理论是热力学第一、二定律，利用热力学第一定律和平衡态以及可逆过程的假设条件，研究热力系的状态变化与外界的功/热量交换的关系，系统与功源和热源的能量交换没有阻力的约束，理论推导出没有时间参量的理想过程的效率，例如，卡诺循环热机的效率，以此作为实际系统能量转化效率的追求标准。因此，经典热力学没有给出输入、输出的能量功率与能量有效利用率的理论关系，只能通过实验测试某功率条件下实际能量转化效率，这是经典热力学的不足。

在人类追求把热能全部转化为功的不断失败后，科学家总结出热力学第二定律，热力学第二定律有不同的表述[1,2]，克劳修斯（Rudolf Clausius）的说法[4](1854)：不可能把热量从低温物体传到高温物体而不引起其他变化；开尔文(LordKelvin）的说法(1851)：不可能从单一热源吸取热量使之完全变为功而不引起其他变化。但是，这样描述的定律，显然不够彻底，虽然指出了怎么做不行，却没有清楚指出怎么做才行，没有回答把热量从低温物体传到高温物体会引起什么其他变化，其变化是多少。当然，热力学第二定律的对科学和能源工程的贡献是巨大的。

传热学研究热量传输的规律，总结出三种传热形式：热传导、对流和辐射，认为温差或温度梯度是传热的起因，采用熵产和“爆”耗散度量传热过程的不可逆性，并以最小“熵产率"[5]和最小“”耗散率的理论指导换热器优化研究[6]。上述两种理论仍然无法给出热量输运的效率合理定义式，因此难以在热力系统中热力循环和换热器协同优化。

实际热力或制冷系统是包括工质循环和高、低温换热器的系统，存在工质循环内部和外部换热的不可逆过程，系统设计要在满足输入、输出功率条件下有高的能量利用效率和低的设备成本。经典热力学没有时间参量，传热学又不能计算传热过程的动力能消耗，因此，研究热力学与传热学的共性理

论有重要意义。

# 1热力学中的热力学第二定律数学描述及其相关理论

# 1.1克劳修斯不等式和“熵产”

作为定律，应当提供可供计算的数学表达式。克劳修斯(1865)年提出了克劳修斯积分式， $\oint \ d \mathbf { \delta Q } / T \leq$ 0，并定义了熵参数 $\mathrm { d } S = \delta Q / T$ ， $Q$ 是系统与外界交换的热量，温度 $T$ 和熵 $\boldsymbol { S }$ 都是系统的状态参数。于是，用“熵变” $\mathrm { d } S$ 表示的热力学第二定律克劳修斯不等式为

$$
\mathrm { d } S \geqslant { \frac { \delta Q } { T } }
$$

式（1）的等式用于可逆过程计算，不等式用于不可逆过程的判据。为了能够对不可逆过程提供量化判据，提出“熵产”概念，“熵产”定义为系统在在不可逆过程比可逆过程增加的熵变量，记作 $\delta S _ { \mathrm { g } }$ 或$\Delta S _ { \mathrm { g } }$ 。当把可逆过程的熵变量记为 $\mathrm { d } S _ { \mathrm { f } }$ 时得到熵方程表示

$$
\mathrm { d } S = \mathrm { d } \mathrm { S } _ { \mathrm { f } } + \delta S _ { \mathrm { g } }
$$

在孤立系中熵变量 $\mathrm { d } S _ { \mathrm { i s o } } > 0$ ，即熵增定理。据此可以建立孤立系求得过程的“熵产” $\delta S _ { \mathrm { g } }$ 。一百多年来，热力学和传热学就是用“熵产”，“熵产率”的理论讨论不可逆过程的热力学和传热学问题。

虽然“熵产”理论已经被科技界接受和应用，但是，不可回避的问题是：1）“熵产”可以判断过程可逆与否，但是不能回答能量输运的动力能量源，不能描述过程中的能量转换关系；2)不等式的热力学第二定律的数学表达式难以像热力学第一定律方便应用；3)熵原本是状态量，由系统状态决定，系统状态变化的“熵变”是与过程无关的，而“熵产”的“熵变”却跟不可逆过程有关，这种由过程而来的“熵产”在物理学看来是无中生有的量；4）从“熵产”理论推导不出传热过程效率的表达式。

# 1.2郎特（Rant）定义“烟”和烟方程

上世纪中期，为了定义能量的品位，提出用能量中能够转变为有用功部分多少来衡量。这种有用功是指技术上有用的可以输给功源的功，后来由南斯拉夫学者郎特(Rant）命名为“烟"(exergy)[7]，通常用符号 $E _ { \mathrm { x } }$ 表示，现在称为有效能；能量中不能转变为有用功的部分称为“妩”(anergy)，又称为无效能。按郎特定义的“拥”的计算，是选取环境为低温热源，把所论系统的能量经过可逆过程变化到与环境平衡态时所能做的最大有用功量 $W _ { \mathrm { m a x } }$ 。这种定义方式计算“烟”涉及过程和环境热源，计算步骤繁琐复杂，即使在环境约定情况下把“烟”认为状态参数理由不充分，而且 $W _ { \mathrm { m a x } }$ 的表达式中都要减去一项系统带给环境的有效能。例如，闭口系的最大功或其有效能表达式为[1,2]

$$
W _ { U , \operatorname* { m a x } } = ( U - T _ { 0 } S + p _ { 0 } V ) - ( U _ { 0 } - T _ { 0 } S _ { 0 } + p _ { 0 } V _ { 0 } )
$$

式 (3)的等号右边的第二项 $( U _ { 0 } - T _ { 0 } S _ { 0 } + p _ { 0 } V _ { 0 } )$ 是系统变化到环境平衡态时留下的有效能。在以环境为基准和约定可逆过程时， $( U _ { 0 } - T _ { 0 } S _ { 0 } + p _ { 0 } V _ { 0 } ) = 0$ 。因此，式(3)留下的项就称为闭口系的有效能函数

$$
\psi _ { \mathrm { { U } } } = U - T _ { 0 } S + p _ { 0 } V
$$

对于一个进行热力过程的系统，“烟”平衡方程是：

$$
E _ { x , \mathrm { i n } } = E _ { x , \mathrm { o u t } } + \Delta E _ { x , \mathrm { f } } + E _ { x , \mathrm { i r } }
$$

式中， $E _ { x , \mathrm { i n } }$ 、 $E _ { x , \mathrm { o u t } }$ 分别是输入、输出系统的烟,$\Delta E _ { x , \mathrm { f } }$ 是系统的烟变化， $E _ { x , \mathrm { i r } }$ 是不可逆过程损失的烟。

熵方程和烟平衡方程中的 $E _ { x , \mathrm { i r } }$ 和 $\delta S _ { \mathrm { g } }$ 都不能像$Q , W$ 或 $U$ 可以独立测量或由状态参数求出， $E _ { x , \mathrm { i r } }$ 和 $\delta S _ { \mathrm { g } }$ 都是不可逆过程而产生的量，消耗了而不明去处，增加了而不能说明来源，不符合物理学的能量和质量守恒定律。所以，熵方程和烟平衡方程不是完美真正的平衡方程。

# 2 热力学第二定律的量化描述及其有效能方程

# 2.1有效能函数的新定义式

陈则韶[8.9]认为势能是系统所处的状态相对于某个稳定的平衡态所具有的相对能量，具有向稳定平衡态移动和释放其能量，对外界做功或转化为其他形式的能量的能力。势能是标量，势能函数通常采用势强度参数和广延参数的一对共轭参数的乘积表示，

$$
E = X J
$$

其中， $E$ 表示势能； $X$ 表示能势，为势强度参数，例如温度 $T$ 、压力 $P$ 等， $J$ 表示物系所对应的广延参数，例如熵 $S$ 、体积 $V$ 等。由于势能是与基准状态有关的函数，式(6)是绝对势能的广义表达式。热力学视环境为稳定的平衡态，所以以环境的平衡态为基准，其能量势记为 $X _ { 0 }$ ，可以把热力系的绝对势能$E$ 分解为相对环境的势能 $E _ { \mathrm { u } }$ 和环境基准势能 $E _ { \mathrm { n } }$ 两部分，分解式为

$$
E = X J = ( X - X _ { 0 } ) J + X _ { 0 } J = E _ { \mathrm { u } } + E _ { \mathrm { n } } 
$$

$$
E _ { \mathrm { u } } = \left( X - X _ { 0 } \right) J
$$

$$
E _ { \mathrm { n } } = X _ { 0 } J
$$

式 $( 8 ) E _ { \mathrm { u } }$ 定义为有效能函数，只与状态参数有关，与过程无关。根据式 $( 8 ) E _ { \mathrm { u } }$ 定义，只要明确了能函数的 $X J$ 关系式和环境平衡态的势强参数 $X _ { 0 }$ ，就能够直接给出所论能量的有效能表达式，例如，已知热量 $Q = T S$ 、体积能 (膨胀功量) $\vert E _ { p } = p V \vert$ 、闭口系的热力学能 $U = T S - P V$ 和开口系的 $H =$ $U + p V = T S$ ，就能直接写出它们有效能函数式和微分有效能函数分别是：

$$
E _ { \mathrm { u } , T } = \left( T - T _ { 0 } \right) S = \left( 1 - T _ { 0 } / T \right) Q ,
$$

$$
\mathrm { d } E _ { \mathrm { u } , T } = \left( T - T _ { 0 } \right) \mathrm { d } S = \left( 1 - T _ { 0 } / T \right) \mathrm { d } Q
$$

$$
\begin{array} { r } { E _ { \mathrm { u } , p } = \left( p - p _ { 0 } \right) V , } \end{array}
$$

$$
\mathrm { d } E _ { \mathrm { u } , p } = \left( p - p _ { 0 } \right) \mathrm { d } V
$$

$$
{ \cal E } _ { \mathrm { u } , U } = \left( T - T _ { 0 } \right) S - \left( p - p _ { 0 } \right) V = U - T _ { 0 } S + p _ { 0 } V ,
$$

$$
\mathrm { d } E _ { \mathrm { u } , U } = \mathrm { d } U - T _ { 0 } \mathrm { d } S + p _ { 0 } \mathrm { d } V
$$

$$
\begin{array} { r } { E _ { \mathrm { u } , H } = \left( T - T _ { 0 } \right) S = H - T _ { 0 } S , } \end{array}
$$

$$
\mathrm { d } E _ { \mathrm { u } , H } = \mathrm { d } H - T _ { 0 } \mathrm { d } S
$$

新定义式表达的有效能函数式与“拥”的函数式是一样的，但无需构建做功系统和计算最大有用功。

# 2.2热力学第二定律的量化表述及普适有效能方程

当用势能理论和有效能、无效能的定义重新审视热力学第一、二定律，就可以获得由热力学第一定律推导出的可逆和不可逆过程普适的有效能方程。

热力学第一定律给出的系统与外界能量交换时系统的内能变化量 $\Delta E$ 与外界交换的功量 $W$ 、热量$Q$ 之间的能量守恒关系，但是没有涉及过程和时间，不能揭示过程的方向和程度。能量的传递转移和转换是一个过程，为了能对能量过程清楚描述，把热量 $Q$ 和内能都分解为有效能和无效能表示，功量为有用功，并约定： $\Delta E _ { \mathrm { u } }$ 表示系统有效能总减量， $\Delta E _ { \mathrm { n } }$ 表示无效能总增量， $\pm W$ 的正号表示输出功、负号表示输入功。于是根据能量守恒定律，导出系统与外界作用过程的有效能变化量、功量与无效能变化量的数学表达式，简称有效能方程：

$$
\Delta E _ { \mathrm { u } } = \Delta E _ { \mathrm { n } } \pm W
$$

其中， $\Delta E _ { \mathrm { u } }$ 是包括输入输出热量和系统工质过程始末的有效能总减量， $\Delta E _ { \mathrm { n } }$ 是包括输出输入热量和系统工质始末的无效能总增量，两者分别定义为

$$
\Delta E _ { \mathrm { u } } = E _ { \mathrm { u , i n } } - E _ { \mathrm { u , o u t } } + E _ { \mathrm { u , a } } - E _ { \mathrm { u , b } }
$$

$$
\Delta E _ { \mathrm { n } } = E _ { \mathrm { n , b } } - E _ { \mathrm { n , a } } + E _ { \mathrm { n , o u t } } - E _ { \mathrm { n , i n } }
$$

式中，下角标的a、b、in和out分别代表过程的起点、终点、输入和输出， $\mathrm { ~ u ~ }$ 用以表示有效能， $\mathbf { n }$ 用以表示无效能； $E _ { \mathrm { u , i n } }$ 、 $\boldsymbol { E _ { \mathrm { u , o u t } } }$ 为输入、输出的有效能； $E _ { \mathrm { u , a } } , E _ { \mathrm { u , b } }$ 分别为系统在过程初始、结束时的有效能; $E _ { \mathrm { n , i n } \setminus E _ { \mathrm { n , o u t } } }$ 为输入、输出的无效能； $E _ { \mathrm { n , a } } , E _ { \mathrm { n , b } }$ 分别为系统在过程初始a点、结束b点的有效能；并且与热量 $Q$ 和内能 $E$ 满足式（7）的关系，即$Q _ { \mathrm { i n } } = E _ { \mathrm { u , i n } } + E _ { \mathrm { n , i n } }$ ， $Q _ { \mathrm { o u t } } = E _ { \mathrm { u , o u t } } + E _ { \mathrm { n , o u t } }$ ， $E _ { \mathrm { a } } =$ $E _ { \mathrm { u , a } } + E _ { \mathrm { n , a } } , E _ { \mathrm { b } } = E _ { \mathrm { u , b } } + E _ { \mathrm { n , b } } .$ （2号

有效能方程（14）用在可逆过程和不可逆过程时，分别简化为

$$
\Delta E _ { \mathrm { u } } = W ( \Delta E _ { \mathrm { n } } = 0 )
$$

$$
\Delta E _ { \mathrm { u } } = \Delta E _ { \mathrm { n } } ( W = 0 )
$$

势能方程（7）和有效能方程（14）可以作为热力学第二定律的数学方程，其物理阐释是[10]：热力系的能量是相对于环境基准的有效能和环境基准平衡态的无效能组成；能量能够自发地朝有效能减少的方向，即从高势能系统向低势能系统转移或转换；能量过程伴随着有效能量变化，不可逆过程消耗有效能，并变为无效能，可逆过程有效能消耗为零，高势能系所减少的有效能量变为输出功量；能量向有效能增加的方向转移时，必须由外界补充转移能量所增加的有效能和能量转移过程累计消耗的有效能；在孤立系的能量转移和转换过程中，系统的总有效能变化量、总无效能变化量和总功量三者之和，守恒为零。

方程（14）可以拓展为多过程复杂系统，并用下角标 $\mathbf { \chi } _ { i }$ 表示过程的序号。拓展的普适能量方程方程为：

$$
\sum _ { i } \Delta E _ { \mathrm { u } , i } = \sum _ { i } \Delta E _ { \mathrm { n } , i } \pm \sum _ { i } W _ { i }
$$

# 2.3有效能消耗率方程

在工程应用中常使用传热速率，热流率，功率的参数。因此为了方便讨论有热流率的工程问题，需要把有效能消耗方程 $( 1 4 ) { \sim } ( 1 9 )$ 变化为单位时间的能量方程，其单位也由焦耳J转换为功率单位瓦特W，并用符号 $\Delta \dot { E } _ { \mathrm { u } }$ 表示有效能变化率， $\Delta \dot { E } _ { \mathrm { n } }$ 表示无效能变化率， $\pm P$ 表示输出、输入功率， $\varphi$ 表示热流率。对应方程(14)和方程(19)的有效能变化率方程分别为

$$
\Delta \dot { E } _ { \mathrm { u } } = \Delta \dot { E } _ { \mathrm { n } } \pm P
$$

$$
\sum _ { i } \Delta \dot { E } _ { \mathrm { u } , i } = \sum _ { i } \Delta \dot { E } _ { \mathrm { n } , i } \pm \sum _ { i } P _ { i }
$$

# 3应用举例

# 3.1传热过程的不可逆度和传热效率[

热传导是典型传热过程，设热量 $Q$ 从 $T _ { 1 }$ 高温热源通过热导体传给温度 $T _ { 2 }$ 低温热源，热量在导体中传递时的有效能减少量 $\Delta E _ { \mathrm { u } }$ 或无效能增量 $\Delta E _ { \mathrm { n } }$ 据方程(14)和式(10)计算得

$$
\begin{array} { c } { \Delta E _ { \mathrm { u } } = E _ { \mathrm { u } , 1 } - E _ { \mathrm { u } , 2 } = \Delta E _ { \mathrm { n } } = E _ { n , 2 } - E _ { n , 1 } = } \\ { Q T _ { 0 } \left( \displaystyle \frac { 1 } { T _ { 2 } } - \frac { 1 } { T _ { 1 } } \right) = Q \frac { T _ { 0 } \left( T _ { 1 } - T _ { 2 } \right) } { T _ { 1 } T _ { 2 } } } \end{array}
$$

当已知传热流率 $\varphi$ 时，参照方程 (22)，得传热过程有效能消耗率 $\Delta \dot { E } _ { \mathrm { u } }$ 或无效能增量率 $\Delta \dot { E } _ { \mathrm { n } }$ 计算式为

$$
\Delta \dot { E } _ { \mathrm { u } } = \Delta \dot { E } _ { \mathrm { n } } = \varphi \frac { T _ { 0 } \left( T _ { 1 } - T _ { 2 } \right) } { T _ { 1 } T _ { 2 } }
$$

当 $T _ { 2 } = T _ { 0 }$ 时， $\Delta E _ { \mathrm { u } } = Q \left( 1 - T _ { 0 } / T _ { 1 } \right)$ ， $\Delta \dot { E } _ { \mathrm { u } } = $ $\varphi \left( 1 - T _ { 0 } / T _ { 1 } \right)$ 。

相同问题的熵产率为 $\Delta \dot { S } _ { \mathrm { g } } = \varphi \left( 1 / T _ { 2 } - 1 / T _ { 1 } \right)$ ，“”耗散率为 $P _ { \phi } = \varphi \left( T _ { 1 } - T _ { 2 } \right)$ ，比较之得知

$$
\Delta \dot { E } _ { \mathrm { n } } = T _ { 0 } \Delta \dot { S } _ { \mathrm { g } }
$$

$$
\Delta \dot { E } _ { \mathrm { n } } = \frac { T _ { 0 } } { T _ { 1 } T _ { 2 } } P _ { \phi }
$$

传热过程的不可逆度定义为传热过程的无效能增量与传热量之比，或无效能增量率与传热流率之比，数学式为

$$
\eta _ { \mathrm { { u , i r } } } = { \frac { \Delta E _ { \mathrm { { n } } } } { Q } } = { \frac { \Delta { \dot { E } } _ { \mathrm { { n } } } } { \varphi } } = { \frac { T _ { 0 } } { T _ { 2 } } } \left( 1 - { \frac { T _ { 2 } } { T _ { 1 } } } \right)
$$

传热效率定义为单位有效能消耗的传输热量或单位有效能消耗率的传输热流率，数学式为

$$
\eta _ { \mathrm { h } } = { \frac { Q } { \Delta E _ { \mathrm { u } } } } = { \frac { \varphi } { \Delta \dot { E } _ { \mathrm { u } } } } = { \frac { 1 } { \eta _ { \mathrm { u , i r } } } } = { \frac { T _ { \mathrm { 1 } } T _ { \mathrm { 2 } } } { T _ { \mathrm { 0 } } \left( T _ { \mathrm { 1 } } - T _ { \mathrm { 2 } } \right) } }
$$

由于“熵产”和“爆”的量纲与能量的量纲不一致，所以不能通过熵产率和“ ”耗散率与输运热流率的比值定义出不可逆度。

对流传热的有效能消耗必须把驱动载热流体流动消耗的功率包括在内，流速增加使输入泵功率增加和传热温差减小，因此可以用传热效率或传热过程不可逆度的最小值优化流速。

# 3.2实际热机的输出功率与效率的关系

实际热机系统包括工质循环和工质与高、低温热源的换热以及与功源的功交换，通过等价热力变换，可以等价变换为图1所示的热机 $T - Q$ 或 $T - \phi$ 图。 $T _ { \mathrm { H } } , T _ { \mathrm { L } }$ 分别为等价高温、低温热源温度， $T _ { 1 } , T _ { 2 }$ 分别为工质理论循环的等效高温、等效低温, $\varphi _ { 1 } , \varphi _ { 2 }$ 分别为高温吸热、低温放热的热流率，环境温度为$T _ { 0 \circ } \ P _ { 1 \setminus } \ P _ { 1 }$ 分别为输入、输出功率。系统稳态的能流率方程和传热方程分别为

$$
\varphi _ { 1 } = \varphi _ { 2 } + \left( P _ { 2 } - P _ { 1 } \right)
$$

$$
\varphi _ { 1 } = K _ { 1 } \left( T _ { \mathrm { H } } - T _ { 1 } \right)
$$

$$
\varphi _ { 2 } = K _ { 2 } \left( T _ { 2 } - T _ { \mathrm { L } } \right)
$$

$$
\varphi _ { 1 } = \dot { m } \left( h _ { 1 } - h _ { 4 } \right) = \dot { m } T _ { 1 } \left( \mathrm { s } _ { 1 } - \ : s _ { 4 } \right)
$$

$$
\varphi _ { 2 } = \dot { m } \left( h _ { 2 } - h _ { 3 } \right) = \dot { m } T _ { 2 } \left( \mathrm { s } _ { 2 } - \mathrm { s } _ { 3 } \right)
$$

$$
P _ { 1 } = { \dot { m } } \left( h _ { 4 } - h _ { 3 } \right)
$$

$$
P _ { 2 } = { \dot { m } } \left( h _ { 2 } - h _ { 4 } \right)
$$

![](images/b0ec2245f19c24e2c313c6834ae6e10461da72c83407ef5ff20441ed262e4c82.jpg)  
图1图1实际热机等价 $T - \phi$ 示意图 Fig.1 equivalent $T - \phi$ diagram for actual heat engine

上列式中 $h _ { 1 }$ 、 $h _ { 2 }$ 、 $h _ { 3 }$ 、 $h _ { 4 }$ 和 $s _ { 1 }$ 、 $s _ { 2 }$ 、 $s _ { 3 }$ 、 $s _ { 4 }$ 分别为对应于图2中理论循环的1、2、3、4节点的比焓和比熵；非可逆循环分析时，采用图2中包含非定熵压缩和非定熵膨胀循环的1、 $2 ^ { \prime }$ 、3、 $4 ^ { \prime }$ 节点的参数，即用 $h _ { 2 ^ { \prime } }$ 、 $h _ { 4 ^ { \prime } }$ 、 ${ \bf \nabla } _ { s _ { 2 ^ { \prime } } }$ 、 $s _ { 4 ^ { \prime } }$ 取代上列式中的$h _ { 2 } \ 、 h _ { 4 } \ 、 s _ { 2 } \ 、 s _ { 4 \circ } \ K _ { 1 \bullet } \ K _ { 2 }$ 分别为吸热、放热换热器的总传热系数 (等效传热系数与传热面积的乘积)。据能流率方程(28)和有效能方程 $\Delta \dot { E } _ { \mathrm { u } } = \sum \Delta \dot { E } _ { \mathrm { n } } + P$ 通式，得图1模型的热机有效能率方程为

$$
\begin{array} { l } { \displaystyle \varphi _ { 1 } \left( 1 - \frac { T _ { 0 } } { T _ { \mathrm { H } } } \right) - \varphi _ { 2 } \left( 1 - \frac { T _ { 0 } } { T _ { \mathrm { L } } } \right) = } \\ { \displaystyle \varphi _ { 1 } \left( \frac { T _ { 0 } } { T _ { 1 } } - \frac { T _ { 0 } } { T _ { \mathrm { H } } } \right) + \varphi _ { 2 } \left( \frac { T _ { 0 } } { T _ { \mathrm { L } } } - \frac { T _ { 0 } } { T _ { 2 } } \right) + \left( P _ { 2 } - P _ { 1 } \right) } \end{array}
$$

解得净输出功率 $P = P _ { 2 } - P _ { 1 }$ 和热效率 $\eta$ 分别为

$$
P = \varphi _ { 1 } \left( 1 - T _ { 2 } / T _ { 1 } \right)
$$

$$
\eta = { \frac { P } { \varphi _ { 1 } } } = \left( 1 - { \frac { T _ { 2 } } { T _ { 1 } } } \right)
$$

在 $T _ { \mathrm { H } } = T _ { 1 } , \ T _ { \mathrm { L } } = T _ { 2 }$ 时，极限热效率 $\eta _ { \mathrm { m a x } }$ 为

$$
\eta _ { \mathrm { m a x } } = { \frac { P } { \varphi _ { 1 } } } = \left( 1 - { \frac { T _ { \mathrm { L } } } { T _ { \mathrm { H } } } } \right)
$$

这是卡诺热机效率，可是，如果换热器传热面积不是无穷大，输出功率为0。

有效能效率 $\eta _ { \mathrm { u } }$ 为

$$
\eta _ { \mathrm { u } } = \frac { P } { \Delta \dot { E } _ { \mathrm { u } } } = \frac { \eta } { \eta _ { \mathrm { m a x } } } = \left( 1 - \frac { T _ { 2 } } { T _ { 1 } } \right) \bigg / \left( 1 - \frac { T _ { \mathrm { L } } } { T _ { \mathrm { H } } } \right)
$$

当 $T _ { 1 } = T _ { 2 }$ ，解得 $P = 0 , \eta = 0 ,$

由方程 (36)联立方程 (28)～(30)得

$$
{ \frac { \varphi _ { 2 } } { \varphi _ { 1 } } } = { \frac { K _ { 2 } \left( T _ { 2 } - T _ { \mathrm { L } } \right) } { K _ { 1 } \left( T _ { \mathrm { H } } - T _ { 1 } \right) } } = { \frac { T _ { 2 } } { T _ { 1 } } }
$$

当 $T _ { \mathrm { H } }$ 、 $T _ { \mathrm { L } }$ 、 $\kappa = K _ { 2 } / K _ { 1 }$ 已知时，解得 $T _ { 1 }$ 与 $T _ { 2 }$ 的关系式为

$$
T _ { 1 } = \frac { T _ { \mathrm { H } } T _ { 2 } } { [ ( T _ { 2 } - T _ { \mathrm { L } } ) \kappa + T _ { 2 } ] }
$$

继而把式(41)的 $T _ { 1 }$ 关系式代入方程(28) $\sim$ (30)(37)，解出 $P$ 和 $\eta$ 的计算式分别为[11,12]

$$
P = \varphi _ { 1 } - \varphi _ { 2 } =
$$

$$
K _ { 1 } T _ { \mathrm { H } } \left( 1 - \frac { T _ { 2 } } { \left[ \left( T _ { 2 } - T _ { \mathrm { L } } \right) \kappa + T _ { 2 } \right] } - \frac { \kappa \left( T _ { 2 } - T _ { \mathrm { L } } \right) } { T _ { \mathrm { H } } } \right) =
$$

$$
K _ { 1 } T _ { \mathrm { H } } \left( \eta - \frac { \eta } { 1 - \eta } \cdot \frac { T _ { 2 } } { T _ { \mathrm { H } } } \right)
$$

$$
\eta = 1 - [ ( T _ { 2 } - T _ { \mathrm { L } } ) \kappa + T _ { 2 } ] / T _ { \mathrm { H } }
$$

令 $\pi ~ = ~ P / K _ { 1 } T _ { \mathrm { H } }$ 为无量纲输出功率，无量 纲温度分别为 $\tau _ { 1 } ~ = ~ T _ { 1 } / T _ { \mathrm { H } }$ ， $\tau _ { 2 } ~ = ~ T _ { 2 } / T _ { \mathrm { H } }$ ， $\pi _ { \mathrm { { L } } } ~ =$ $T _ { \mathrm { L } } / T _ { \mathrm { H } }$ ， $\tau _ { \mathrm { H } } = T _ { \mathrm { H } } / T _ { \mathrm { H } } = 1$ ，则

$$
\pi = \eta - \frac { \eta \tau _ { 2 } } { 1 - \eta }
$$

$$
\eta = 1 - \left[ ( T _ { 2 } - T _ { \mathrm { L } } ) \kappa + T _ { 2 } \right] / T _ { \mathrm { H } } = 1 - \left( \tau _ { 2 } - \tau _ { \mathrm { L } } \right) \kappa - \tau _ { 2 }
$$

据输出功率 $P$ 的计算式（42）对 $T _ { 2 }$ 变量求极值 $\mathrm { d } P / \mathrm { d } T _ { 2 } = 0$ 可以解出对应输出功率最大时的温度 $T _ { 2 , \mathrm { m } }$ 为

$$
T _ { \mathrm { 2 , m } } = { \frac { T _ { \mathrm { L } } \kappa + { \sqrt { T _ { \mathrm { H } } T _ { \mathrm { L } } } } } { 1 + \kappa } }
$$

最大输出功率 $P _ { \mathrm { m a x } }$ 及其对应的效率 $\eta _ { \mathrm { m } }$ 计算式分别为

$$
P _ { \mathrm { m a x } } = \frac { T _ { \mathrm { H } } K _ { 2 } \left( 1 - \sqrt { T _ { \mathrm { L } } / T _ { \mathrm { H } } } \right) ^ { 2 } } { 1 + \kappa }
$$

$$
\eta _ { \mathrm { m } } = \eta _ { \mathrm { C A } } = 1 - \sqrt { T _ { \mathrm { L } } / T _ { \mathrm { H } } }
$$

![](images/0428e96b930cabd4ad012cbaf6ddc541ffe10dcb596c2d610519bcb72d3d46bd.jpg)  
图3内可逆卡诺循环对比输出功率 $\pi _ { \gamma }$ ， $\tau _ { 1 }$ ， $\tau _ { 2 }$ 与效率 $\eta$ 的关系Fig.3 $\pi _ { \gamma }$ ， $\tau _ { 1 }$ ， $\tau _ { 2 } - \eta$ diagram for endoreversible Carnot cycle

其中， $\pi _ { \gamma }$ 为对比输出功率：

$$
\pi _ { \gamma } = { \frac { P } { P _ { \operatorname* { m a x } . \kappa = 1 } } } = { \frac { P } { P _ { \operatorname* { m a x } } } } { \frac { P _ { \operatorname* { m a x } } } { P _ { \operatorname* { m a x } , \kappa = 1 } } } = { \frac { 2 \kappa } { 1 + \kappa } } P _ { \mathrm { r } }
$$

其中， $P _ { \mathrm { r } } = P / P _ { \mathrm { m a x } }$ ，为相同 $\kappa$ 值不同 $\tau _ { 2 }$ 的热机输出功率 $P$ 与其自己最大输出功率的比值，经过作图法验证，不同 $\kappa$ 值的 $P _ { \mathrm { r } }$ 都与 $\kappa { = } 1$ 的 $P _ { \mathrm { r } }$ 关系相同。

![](images/9ab9e0ae0cc5b821f57e2e297445ca1030289ee020b0a07637b745bf9ec7487d.jpg)  
图2实际过热郎肯循环 Fig.2 actual overheating Rankine cycle

$$
\begin{array} { l } { \displaystyle P _ { \mathrm { r } } = \frac { P } { P _ { \mathrm { m a x } } } = } \\ { \displaystyle \left. \left( \eta - \frac { \eta } { 1 - \eta } \cdot \frac { T _ { 2 } } { T _ { \mathrm { H } } } \right) \middle / \left( \eta _ { \mathrm { C A } } - \frac { \eta _ { \mathrm { C A } } } { 1 - \eta _ { \mathrm { C A } } } \cdot \frac { T _ { 2 \mathrm { m } } } { T _ { \mathrm { H } } } \right) \right. } \end{array}
$$

本文根据稳定态求解获得的式 (48)，也与国内许多学者如严子浚[13]、陈林根[14]，陈金灿[15]在介绍一种假定热机的吸、放热过程交替进行并且各消耗有限时间的方法的有限时间热力分析法时都有提及的 CurzonFL，Ahlborn B.的著名的 $\eta _ { \mathrm { C A } }$ 效率[16]一致。顺便提一句，这种交替吸、放热有限时间分析法求解得到的最大输出功率时的效率表达式与本文采用的定态热力分析法的式（47）不同，其计算结果因为换热器间歇工作而比假定实际定态运行热机的输出功率偏小。

图3为假定 ${ \cal T } _ { \mathrm { H } } { = } 1 0 0 0$ K， $\scriptstyle { T _ { \mathrm { L } } = 3 0 0 \mathrm { ~ K ~ } }$ ，在$\kappa { = } 1 . 5$ 、1、0.5三种情况下实际热机的无量纲的对比输出功率 $\pi _ { \gamma }$ 、温度 $\tau _ { 1 } , \tau _ { 2 }$ 和效率 $\eta$ 的关系图。

式（49）中的 $2 \kappa / { ( 1 + \kappa ) }$ 为不同 $\kappa$ 值的最大输出功率的比值。图中的三组抛物线，自上而下分别表示$\kappa { = } 1 . 5$ ，1和0.5的对比输出功率 $\pi _ { \gamma }$ 曲线, $\pi _ { \gamma }$ 随 $\kappa$ 的增大而增大，三组不同 $\kappa$ 值的输出功率极值所对应的效率 $\eta _ { \mathrm { m } }$ 都相同，为 $\eta _ { \mathrm { C A } } = 1 - \sqrt { 0 . 3 } = 0 . 4 5 2 2 8$ 图中三组喇叭形曲线，上、中、下分别为 $\kappa { = } 0 . 5$ 、1、1.5的无量纲等效温度 $\tau _ { 1 }$ 、 $\tau _ { 2 }$ 曲线，每组曲线 $\tau _ { 1 }$ 曲线在上， $\tau _ { 2 }$ 曲线在下, $\tau _ { 1 } , \tau _ { 2 }$ 都随 $\kappa$ 的增大而降低，而且$\tau _ { 1 }$ 降低的更多。也因此，在 $K _ { 1 }$ 不变的前提下，高温吸热换热器有更大的传热温差，吸收更多的热量，在效率不变前提下，可输出更多的功率， $\kappa$ 的增大付出的代价是，低温放热换热器传热面积需要增大。

# 3.3实际热机的优化设计

实际热机的优化设计，需要在既定的热源和环境冷却条件下，即 $T _ { \mathrm { H } }$ 和 $T _ { \mathrm { L } }$ 确定下，设计满足输出功率 $P$ 时追求高效率 $\eta$ ，并尽可能降低设备成本，即单位输出功率的设备成本。作者曾建议采用最大输出功率的效率 $\eta _ { \mathrm { C A } }$ 和最大效率 $\eta _ { \mathrm { C } }$ (卡诺热机效率，零输出功率)等权重法选择最佳效率 $\eta _ { \mathrm { o p t } }$ ，

$$
\eta _ { \mathrm { o p t } } = 0 . 5 \eta _ { \mathrm { C A } } + 0 . 5 \eta _ { \mathrm { C } }
$$

在效率 $\eta$ 确定后，根据式(37)， $T _ { 2 } / T _ { 1 }$ 的比值已经被限定；另外，提高输出功率 $P$ 可以通过增加 $\kappa$ 值获得，参看图3；通常工质循环的高温 $T _ { 1 }$ 由高温换热器材料的耐温极限限制，即 $T _ { 1 }$ 首先确定，相继温度 $T _ { 2 }$ 以及高、低温换热器的传热温差也被确定；根据设计需要的 $\varphi _ { 1 }$ 或 $\varphi _ { 2 }$ ，则能确定 $K _ { 1 }$ 或 $K _ { 2 }$ 之一，继而再优化选择 $\kappa$ 值后，再确定 $K _ { 2 }$ 或 $K _ { 1 }$ 。优化 $\kappa$ 值原则：提高输出功率的效益必须大于成本增加费用。

热力系统的设备成本由高温换热器、低温换热器、膨胀机、液体循环泵和其它辅助设备的成本构成，假定以 $\kappa { = } 1$ 时的高温换热器成本为基准，各成本系数分别为 $1 , a , b , c$ 和 $d$ ，在 $\kappa \neq 1$ 时，高温换热器的 $K _ { 1 }$ 不变成本不变，并忽略液体循环泵和其它辅助设备的成本系数随 $\kappa$ 的变化；可以通过建立单位输出功率的设备成本与 $\kappa$ 关系方程，并对 $\kappa$ 变量求极值，得到优化的 $\kappa _ { \mathrm { o p t } }$ 值。 $\kappa _ { \mathrm { o p t } }$ 参考计算式为

$$
\kappa _ { \mathrm { o p t } } = { \sqrt { \frac { 1 + c + d } { a } } }
$$

式中， $\smash { 1 , a , c }$ 和 $d$ 分别为高温换热器、低温换热器、液体循环泵和其它辅助设备的成本系数。

根据式(51)选定 $\eta _ { \mathrm { o p t } } = 0 . 5 \left( 1 - \sqrt { 0 . 3 } \right) + 0 . 5 \times$ $0 . 7 = 0 . 5 7 6 1$ ；当 $a = 0 . 8$ 、 $b = 1$ 、 $c + d = 1$ 时优化得最佳总传热系数为 $\kappa _ { \mathrm { o p t } t } = 1 . 5 4 7$ ；根据式(45)得

$$
T _ { 2 } = \tau _ { 2 } T _ { \mathrm { H } } = \left( \frac { 1 - \eta + \kappa \tau _ { \mathrm { L } } } { 1 + \kappa } \right) T _ { \mathrm { H } }
$$

再由式 (37)得

$$
T _ { 1 } = \tau _ { 1 } T _ { \mathrm { H } } = \left( \frac { \tau _ { 2 } } { 1 - \eta } \right) T _ { \mathrm { H } }
$$

再据式（42）解得

$$
P = T _ { \mathrm { H } } K _ { 1 } { \frac { 2 \kappa } { ( 1 + \kappa ) } } P _ { \mathrm { r } }
$$

本例的数据解得， $T _ { 2 } = \tau _ { 2 } T _ { \mathrm { H } } = 0 . 3 4 8 6 5 T _ { \mathrm { H } }$ ， $T _ { 1 } =$ $\tau _ { 2 } T _ { \mathrm { H } } = 0 . 8 8 8 5 T _ { \mathrm { H } }$ ， $P = 0 . 9 9 9 7 T _ { \mathrm { H } } K _ { 1 }$ ，参见图3中$\eta _ { \mathrm { o p t } } \mathrm { L i n e }$ 线与 $\tau _ { 2 } , \tau _ { 1 }$ 、 $\pi _ { \mathrm { r } }$ 线的交点。

本文用有效能方程推导出的输出功率 $P$ 和热效率 $\eta$ 的计算式，没有用到内可逆循环的假定，因此适合于膨胀做功过程有部分用于克服流动阻力的功量变成热量汇入 $Q _ { 2 }$ 或 $\phi _ { 2 }$ 低温换热器的情况。对于有热量漏泄情况，利用有效能方程也很容易解决。

# 3.4有效能方程应用方法总结

根据上述应用例，利用有效能方程求解传热和热力学耦合的复杂问题步骤如下：

1）对实际过程进行等价热力变换，定义各过程的等效热力温度；2)写出能量方程和传热方程；3）写出有效能方程，并根据本文的有效能定义式给出各项的有效能表达式；4）利用定态有限时间热力分析法，对问题进行求解，给出输运热流率、输入输出功率与效率关系；5)根据效率、功率的关系式，调整相关参数，在保证设计功率条件下的追求高效率，达到系统优化目的。

# 4 结束语

本文回顾总结了热力学与传热学共性理论基础研究的系列成果，正视了热力学第二定律只是定性不能定量的问题，由于熵参数和“”参数的量纲与能量量纲不一致，决定放弃直接用“熵产”或“熵产率”以及“”耗散数和“爆”耗散率与过程的能量之比，定量表示过程不可逆度的努力；转而从势能理论出发，定义了有效能和无效能，比较了与“烟”定义的差别；用相对势能定义的有效能不涉及过程，有效能函数完全由状态参数组成；继而，在热力学第一定律基础上推导出能量输运和转换过程的有效能变化与无效能增量以及功量变化的方程，简称为有效能方程，无论可逆和不可逆过程，有效能方程都能由过程初始和终止状态获得平衡，而熵方程、“”耗散方程和“烟”方程中用在不可逆过程时，都是通过补缺项才能平衡；把有效能方程推广到有效能率方程，能准确地定量表达了传热效率；对实际热机系统应用例的热力分析表明，利用有效能率方程能够方便导出传热与热力耦合问题的输入输出功率、热流率与效率以及换热器传热系数、热源条件的关系。

总之，本文构建的热力学和传热学共性理论，为热机与换热器耦合进行热力系统综合分析和协调优化提供了理论基础。

# 参考文献

[1]曾丹苓,敖越,张新铭，等．工程热力学[M]．北京：高等教育出版社，2002ZENG Danling， AO Yue, ZHANG xinming，etal.Engineering Thermodynamics [M].Beijing:Higher Ed-ucation Press,2002  
[2]陈则韶.高等工程热力学[M].北京：高等教育出版社,2008CHEN Zeshao.Advanced Engineering Thermodynamics[M]．Beijing:Higher Education Press,2008  
[3]杨世铭,陶文钰.传热学[M].第四版.北京:高等教育出版社,2006YANG Shiming,TAO Wenquan.Heat Transfer Theory[M]．4th Edition.Beijing:Higher Education Press,2006  
[4]Clausius R.On a Modified Form of the Second Fun-damental Theorem in the Mechanical Theory of Heat[J]．Philosophical Magazine Series 4,1856,12(77): 81-98  
[5]Bejan A.Entropy Generation Through Heat and FluidFlow[M].New York:Wiley,1982  
[6] 李孟寻,郭江峰,许明田,等.爆耗散理论在管壳式换热器优化设计中的应用[J]．工程热物理学报，2010,31(7)：1189-1192LI Mengxun， GUO Jiangfeng， XU Mingtian，etal．Application of Entransy Dissipation Theory in Op-timization Design of Shell-and-tube Heat Exchanger[J].Journal of Engineering Thermophysics,2O10,31(7):1189-1192  
[7]杨思文,金六一,孔庆煦,等.高等工程热力学[M].北京：高等教育出版社，1988YANG Siwen, JIN Liuyi, KONG Qingxu, et al.AdvancedEngineering Thermodynamics [M].Beijing:Higher Edu-cation Press,1988  
[8] 陈则韶，胡芃,李川.有效能消耗系数及其与熵产数和耗散数的比较[J].中国科学:技术科学,2014,44(9):946-952CHEN Zeshao,HU Peng,LI Chuan. Coefficient of exergyconsumption and its comparison with entropy produc-tion number and entransy dissipation number [J].ScienceChina: Technological Sciences,2014,44(9):946-952  
[9] 陈则韶,李川,胡汉平,等.不可逆过程的有效能消耗率及不可逆度[J]．工程热物理学报，2014,35(3)：411-415CHEN Zeshao,LI Chuan,HU Hanping,et al.AvailableEnergy Consumption Rate and Irreversibility Degree ofIrreversible Process [J]. Journal of Engineering Thermo-physics,2014,35(3): 411-415  
10] 陈则韶,李川．热力学第二定律的量化表述及其应用例[J].工程热物理学报，2016,37(1):1-5CHEN Zeshao,LI Chuan．Quantifable Expression ofThe Second Law of Thermodynamics and It's Application[J]．Journal of Engineering Thermophysics,2016,37(1):1-5  
[11]陈则韶，李川．一种实际热力系统参数优化方法（一)等价变换定常态有限时间分析[J]．工程热物理学报，2016,37(4):685-689CHEN Zeshao，LI Chuan．An Optimization Methodfor Actual Thermodynamic System Parameters(A)Equivalent Transformation Steady Finite-Time Analysis[J]．Journal of Engineering Thermophysics,2016,37(4):685-689  
[12]陈则韶．一种等价热力变换分析法：中国，201310190500.1[P].2014-01-22CHEN Zeshao.An Equivalent Thermodynamic Trans-formation Analysis Method: China, 201310190500.1[P].2014-01-22  
[13]严子浚．卡诺热机的最佳效率与功率间的关系[J]．工程热物理学报,1985,6(1):1-5YAN Zijun.The Relation Between Optimal Efficiency andPower of a Carnot Heat Engine [J].Journal of Engineer-ing Thermophysics,1985,6(1):1-5  
[14]陈林根，孙丰瑞，陈文振．有限时间热力学研究新进展[J].自然杂志,1992，15(4):249-253CHEN Lingen，SUN Fengrui，CHEN Wenzhen．RecentAdvances in Finite-Time Thermodynamics [J].NatureMagazine,1992,15(4):249-253  
[15]陈金灿，严子浚．有限时间热力学理论的特征及发展中几个重要标志[J]．厦门大学学报(自然科学版)，2001,40(2):232-240CHEN Jincan,YAN Zijun.The Characteristics of Finite-Time Thermodynamic Theory and Some ImportantMarks in Development [J].Journal of Xiamen University(Natural Science),2001,40(2):232-240  
[16]Curzon FL，Ahlborn B.Efficiency of a Carnot Engineat Maximum Power Output [J].American Journal ofPhysics,1975,43(1): 22-24