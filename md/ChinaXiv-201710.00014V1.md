# 聚光光伏与甲醇重整热化学互补发电系统性能研究

李文甲1,2，郝勇1,2,\*（1.中国科学院工程热物理研究所，北京100190；2.中国科学院大学，北京100039）(\*010-82543150, haoyong@iet.cn)

摘要：本文提出了太阳能光伏电池与甲醇中低温重整反应相结合的发电系统；通过太阳能的梯级利用以及物理能与化学能之间的品位耦合，太阳能净发电效率较单一光伏或甲醇热化学发电方式获得显著提升。热力学分析表明，在 $1 0 0 { - } 2 5 0 ^ { \circ } \mathrm { C }$ 的系统运行温度范围内，系统的理论太阳能净发电效率达 $4 3 . 6 \% - 4 4 . 3 \%$ （已考虑光学损失)，显著高于光伏系统（ $2 2 . 5 \%$ ）及热化学系统（ $3 2 . 7 \%$ )。系统约 $50 \%$ 的太阳净发电量来自甲醇重整产物氢气，以化学能形式实现了太阳能的高效储能，且光伏、热化学发电随温度变化的相反趋势间互补达到了稳定输出的效果。此外，系统产生的电能中约 $2 5 \%$ 来自太阳能，高于单一太阳能甲醇热化学发电系统的 $14 \%$ ，对化石能源的依赖度降低。光伏与热化学互补发电为太阳能高效综合利用提供了新的思路。

关键词：太阳能；光伏；光热；热化学；梯级利用中图分类号： TK123 文献标识码：A

# Performance analysis on a hybrid solar power generation system integrating concentrated photovoltaics and methanol reforming thermochemistry

Li Wen-Jial2² and Hao Yong1,2\* (1. Institute of Engineering Thermophysics, Chinese Academy of Sciences, Beijing 100190, China; 2. University of Chinese Academy of Sciences, Beijing 10o039, China)

Abstract: A hybrid solar power generation system integrating solar photovoltaics (PV） and mid-/lowtemperature methanol reforming is proposed; compared with PV-onlyand methanol thermochemistry-only power generation systems,the hybrid system achieves significant performance gains by cascaded utilization of solar energy and coupling of energy levels between physical energy and chemical energy. Thermodynamic analyses show that the theoretical net solar-electric (NSE) efficiency of the system reaches up to $4 3 . 6 \% - 4 4 . 3 \%$ within the operation temperature range of $1 0 0 { - } 2 5 0 ^ { \circ } \mathrm { C }$ ，significant higher than $2 2 . 5 \%$ of PV-only system and $3 2 . 7 \%$ of methanol thermochemistry-only system; $50 \%$ of the net solar electricity originates from methanol reforming product $\mathrm { H } _ { 2 }$ ,achieving effective storage of solar thermal energy in the form of chemical energy; besides,stability of power output of the hybrid system is much enhanced via the complementation between opposite trends of PV module and thermochemical module in response to operation temperature. Additionally, $2 5 \%$ of the electricity output of the system is generated from solar energy, higher than that of solar methanol reforming-only system(i.e. $14 \%$ ), decreasing dependence on fosil fuels. Power generation approaches via hybridization between solar PV and solar thermochemistry offer new perspectives towards the grand goal of effective solar energy utilization.

Key words: solar energy; photovoltaics; solar thermal; thermochemistry; cascade utilization

# 0前言

人类对化石能源消耗的迅速增加导致能源短缺、环境污染与气候变化等问题。太阳能因其总量巨大、分布广泛、清洁低碳等优点，有望逐步取代化石能源，促进可持续发展。国际能源署2014年预测[1]，至 2050 年太阳能光伏发电量将占全球总发电量的 $1 6 \%$ ，太阳能光热发电量将占全球总发电量的

现有太阳能利用技术的发展仍然受到效率低、成本高和供能不稳定等因素的限制。太阳能光伏发电技术实际效率仍然较低：单结光伏电池中，低于光伏电池带隙能的低能量光子无法经由单结光伏电池利用，高于光伏电池带隙能的高能量光子，其高于带隙能部分的能量也无法转换为电能。因此，在f非聚光条件下，单p-n 结光伏电池理论最高效率为（204号 $3 1 \% ^ { [ 2 ] }$ ，目前商业化的单结光伏电池效率在$1 0 \% { - 2 0 \% ^ { [ 1 ] } }$ ；多结光伏电池通过叠放具有不同带隙能的 $\mathtt { p - n }$ 结，可以增加光子能量与带隙能的匹配程度，从而提高其发电效率。非聚光条件下，其理论效率可达到 $69 \%$ ；当聚光比达到理论最大值（约46000倍）时，其理论效率达到 $8 6 \% ^ { [ 3 ] }$ ，但受制于材料、工艺与成本等方面的因素， $\mathsf { p } { \cdot } \mathsf { n }$ 结的数量一般在4 以下[4]；目前实验室内四结光伏电池的效率的最高纪录为 $4 6 \% ^ { [ 4 ] }$ ，意味着仍有超过一半的太阳能被转换为热能。更重要的是，从效率和成本等多角度考虑，多结光伏电池往往必须与聚光装置配合使用，故实际发电效率必须计入光学损失。如果将光学效率取为 $72 \%$ ，组件效率与电池效率之比取为 $90 \%$ ，标称效率 $46 \%$ 的光伏电池实际发电效率在室温（ $2 5 ^ { \circ } \mathrm { C } \cdot$ ）下仅为 $2 9 . 8 \%$ ，而聚光往往不可避免地带来较强烈的温升，导致光伏电池的实际效率还将进一步下降。

由于光伏电池在发电的同时不可避免地将一半以上的太阳能转换为热能，回收利用该部分热能可能带来太阳能利用效率的提升。Chubb等人提出了光伏与热机结合将光伏余热用于发电的概念[5]，之后众多研究者开展了类似研究[6][7]。Kosmadakis分析了硅基聚光光伏电池与有机朗肯循环结合的系统，但因为硅基光伏电池和有机朗肯循环的效率均偏低，系统并未获得较大的效率提升（从 $9 . 8 1 \%$ 至 $1 1 . 8 3 \%$ =仅提升2个百分点）[8]。Tourkov 等人[进一步提出了三结砷化镓光伏电池和有机朗肯循环相结合的系统，理论效率为 $45 \%$ 但并未计入光学损失。如果考虑光学效率为 $72 \%$ ，则系统的效率为 $32 \%$ ，相对单独光伏电池的效率（ $28 \%$ ）提升仅为4个百分点。

光伏电池和热机结合的系统效率提高较少，主要是因为太阳能电池的负温度效应显著、温度较低时热机的效率也较低（如 $1 5 0 ^ { \circ } \mathrm { C }$ 时为 $1 2 . 3 \% ^ { [ 1 0 ] } )$ 且随温度升高较慢。这使得在该类光伏光热系统中，热机对效率的贡献被光伏效率随温度的下降抵消了一大部分。此外，因为电能、热能长时间、大规模储能难度大，此类系统还面临着供能不稳定的问题。

1980年，吴仲华教授在中共中央书记处举办的科学技术知识讲座报告中，提出各种不同品位的能源要合理分配、对口供应，做到各得其所，提倡按照"温度对口、梯级利用"原则，大力发展各种联合循环、热电并供与余能利用等总能系统[11]。之后，金红光等进一步发展该理论，提出了化学能与物理能综合梯级利用的理论，并依据该理论，提出了中低温太阳能甲醇裂解发电系统，其太阳能理论净发电效率达到 $3 5 \% ^ { [ 1 2 ] }$ 。在系统内， $2 0 0 ^ { \circ } \mathrm { C }$ 左右的中低温太阳热能驱动甲醇裂解反应产生合成气中 $\mathrm { \small C H _ { 3 } O H ( g ) {  } C O ( g ) { + } 2 H _ { 2 } ( g ) } ,$ DH200℃C $\begin{array} { r l r l } {  { \mathbf { D } } H _ { 2 0 0 ^ { \circ } \mathrm { C } } ^ { \ominus } } & { { } } & { } & { { } = 9 6 . 7 9 } \end{array}$ $\mathrm { k J / m o l } )$ ，合成气通入燃气蒸汽联合循环，经过燃烧过程在高温（如 $1 3 0 0 ^ { \circ } \mathrm { C }$ ）下释放热能，经过该过程，低品位的太阳热能首先被转换为高品位的化学能储存在合成气中，并最终在燃烧过程转换为高温热能，太阳热能的品位得到了提升，因此系统效率较高。但在该系统的太阳能吸收转换过程中，高品位的太阳光能全部转换为较低品位的热能，不可逆损失仍较大，系统效率具有进一步提升的空间。

本文作者基于能的综合梯级利用理论，曾提出了太阳能聚光光伏与甲醇裂解互补的太阳能发电系统[13]。在系统内，太阳能依次经光伏电池与热化学反应器进行利用，太阳能理论净发电效率可达 $43 \%$ 0但甲醇裂解反应在温度高于 $2 0 0 ^ { \circ } \mathrm { C }$ 时方可达到较高的转化率（如图1所示)，较高的温度将使光伏电池效率下降，且不利于光伏电池长期运行；而甲醇重整反应则在 $1 5 0 ^ { \circ } \mathrm { C }$ 便可获得比较理想的转化率，有利于光伏电池的寿命、成本及选择范围。本文提出了基于甲醇重整反应的太阳能光伏热化学互补发电系统，并基于热力学定律，对比分析了单一太阳能光伏发电系统、单一太阳能甲醇热化学发电系统与太阳能光伏热化学互补系统的太阳能发电效率；重点地，从能的梯级利用角度，分析了互补系统效率提升的原因以及系统的储能特性与稳定供能的潜力。

![](images/89a2a478152905d97bb6ddac01f55e02bad6c4ab986257db4b56fbe806ae0cde.jpg)  
图1．甲醇裂解、重整反应在不同温度下的转化率[14] Fig.1 Comparison of methanol conversion rate between

decomposition and reforming reactions ofmethano[14]

# 1 系统描述

如图2所示，太阳能光伏热化学互补系统主要由太阳能光伏热化学反应装置、气体分离装置与燃料电池发电装置几部分组成。其中，太阳能光伏热化学反应装置由点聚焦菲涅尔透镜、聚光光伏电池、甲醇重整预热器、反应器等装置组成。在系统内，甲醇与水以摩尔比1:1的比例通入太阳能光伏热化学反应装置。太阳光由菲涅尔透镜汇聚至聚光光伏电池表面，经光伏电池转换为电能与热能；电能直接对外输出，热能作为甲醇重整反应预热器、反应器的热源，预热、汽化甲醇与水，并驱动甲醇与水发生重整反应（根据 Lin 等的研究[15]，可以通过催化剂控制甲醇重整反应的产物，使其仅为 $\mathrm { C O } _ { 2 }$ 与 $\mathrm { H } _ { 2 }$ 即仅发生如下反应 $\mathrm { C H } _ { 3 } \mathrm { O H } ( \mathrm { g } ) + \mathrm { H } _ { 2 } \mathrm { O } ( \mathrm { g } )  \mathrm { C O } _ { 2 } ( \mathrm { g } ) +$ $3 \mathrm { H } _ { 2 } ( \mathbf { g } )$ ， $\mathrm { D } H _ { 2 0 0 ^ { \circ } \mathrm { C } } ^ { \ominus } = 5 6 . 7 1 \ \mathrm { k J } / \mathrm { m o l } )$ ；反应器出口温度较高的产物（ $\mathrm { C O } _ { 2 }$ 、 $\mathrm { H } _ { 2 }$ ）与未反应的反应物（ $\mathrm { C H } _ { 3 } \mathrm { O H }$ 、$\mathrm { H } _ { 2 } \mathrm { O }$ ）的余热用于预热反应物；最终产物（ $\mathrm { \ C O } _ { 2 } , \mathrm { \ H } _ { 2 } )$ 与未反应的反应物（ $\mathrm { C H } _ { 3 } \mathrm { O H }$ 、 $\mathrm { H } _ { 2 } \mathrm { O }$ ）通入气体分离装置，其中 $\mathrm { C O } _ { 2 }$ 与 $\mathrm { H } _ { 2 }$ 通过膜法进行分离，并对分离后的 $\mathrm { C O } _ { 2 }$ 捕集回收，而氢气储存于氢气储罐中，按需适时通入燃料电池产生电能，剩余的未反应的反应物进行回收再利用。

# 2系统热力学性能模拟

太阳能经聚光镜汇聚至光伏电池表面，在汇聚过程中存在光学损失，光学损失能量与光伏电池吸收的太阳光能量分别为

$$
\begin{array} { r } { \mathcal { Q } _ { \mathrm { o p t , l o s s } } ( T ) = D N I \stackrel {  } { \doublebarwedge } \mathbf { \mathscr { A } } ( 1 - \mathbf { \mathscr { h } } _ { \mathrm { o p t } } ) } \end{array}
$$

$$
Q _ { \mathrm { a b s } } ( T ) = D N I \stackrel { \scriptscriptstyle \perp \leq } { \scriptscriptstyle \sharp \neq 1 } h _ { \mathrm { o p t } }
$$

式中， $D N I$ 是太阳能直射辐射强度； $A$ 是太阳能聚光

镜面积； $h _ { \mathrm { o p t } }$ 是光学效率，取 $72 \%$ ．光伏电池将吸收的太阳能一部分转换为电能，其余部分转换为热能，二者分别为

$$
W _ { \mathrm { P V } } ( T ) = \underbrace { Q _ { \mathrm { a b s } } ( T ) ? h _ { T , \mathrm { P V } } } _ { }
$$

$$
\mathcal { Q } _ { \mathrm { t h e r m a l } } ( T ) = \mathcal { Q } _ { \mathrm { a b s } } ( T ) ? ( 1 \ \quad h _ { T , \mathrm { P V } } )
$$

式中， $h _ { T , \mathrm { P V } }$ 是是温度为 $T$ 时光伏电池组件的效率，本文根据甲醇重整反应的温度范围选择了在高温下工作性能优异的三结砷化镓光伏电池，该光伏电池可较长时间工作于 $2 5 0 ^ { \circ } \mathrm { C }$ 的高温下[16],其组件效率表达式为[17]:

$$
\begin{array} { r } { h _ { T , \mathrm { c e l l } } = \mathsf { \Pi } [ 0 . 2 9 8 + \mathsf { 0 } . 0 1 4 2 \mathrm { l n } C \mathsf { \Omega } } \\ { + \mathrm { \Pi } ( - \mathrm { \Omega } 0 . 0 0 0 7 1 5 + \mathrm { 6 } . 9 7 7 \mathrm { \Omega } 1 0 ^ { - 5 } \mathrm { l n } C ) } \\ { ? \mathrm { \Gamma } ( T 2 5 ) ] ? h _ { \mathrm { m o d } } \quad } \end{array}
$$

式中， $C$ 是点聚焦菲涅尔透镜的聚光比，本文取为500。太阳热能的一部分通过辐射、对流的方式散失到环境中，表示为

$$
\begin{array} { l } { { \displaystyle \mathcal { Q } _ { \mathrm { l o s s , t h e r m a l } } ( T ) = h \frac { \mathcal { A } } { C } ( T \cdot 2 5 ) } } \\ { { \displaystyle ~ - ~ s \frac { \mathcal { A } } { C } ( T + 2 7 3 . 1 5 ) ^ { 4 } } } \end{array}
$$

式中， $h$ 为对流换热系数，取为 $1 0 \mathrm { \ : W } / ( \mathrm { m } ^ { 2 } \cdot \mathrm { K } )$ ; $s$ 为斯蒂芬波尔兹曼常数。预热器、反应器中甲醇与水吸收的热量是光伏电池转换的热能与散热损失之差

$$
\mathcal { Q } ( T ) = \mathcal { Q } _ { \mathrm { t h e r m a l } } ( T ) \cdot \mathcal { Q } _ { \mathrm { l o s s , t h e r m a l } } ( T )
$$

吸收的热量用于预热甲醇与水并驱动其发生重整反应，预热过程与反应过程所需热量在ASPENPlus中进行模拟[14]。此外，反应产物（ $\mathrm { C O } _ { 2 }$ 、 $\mathrm { H } _ { 2 }$ ）与未反应的反应物的余热回收也通过ASPENPIus进行模拟。

![](images/c0fdf3a7b45aabefed0d5e00358d370e72c2cad7b90710096801ca9bafe2f595.jpg)  
图2.太阳能光伏热化学互补系统示意图，包括太阳能光伏热化学反应装置、气体分离装置与燃料电池发电装置 Fig.2 Schematic diagram of solar photovoltaic and thermochemical hybrid system, including solar photovoltaic and thermochemical reactors, gas separators and fuel cells.

反应产物 $\mathrm { H } _ { 2 }$ 的化学能一部分来源于甲醇化学能，其余部分来源于太阳能，则太阳能转换所得化学能为

$$
\begin{array} { l } { { \mathcal { Q } _ { \mathrm { s o l a r - c h e m } } = 3 n \& ? H H V _ { \mathrm { H _ { 2 } } } } } \\ { { \mathrm { ~ - ~ } n \& 2 H H V _ { \mathrm { m e t h a n o l } } } } \end{array}
$$

式中， $^ { \mathbf { \alpha } } _ { n } \mathbf { \& }$ 为甲醇摩尔流量， $H H V _ { \mathrm { H _ { 2 } } }$ 是氢气的高位热值， $H H V _ { \mathrm { { \ m e t h a n o l } } }$ methanol为甲醇高位热值。

经过余热回收的反应产物（ $\mathrm { C O } _ { 2 }$ 、 $\mathrm { H } _ { 2 }$ ）通入气体分离装置，通过膜分离方法将二者分离为 $\mathrm { C O } _ { 2 }$ 与 $\mathrm { H } _ { 2 }$ 。在分离过程中，需要耗功； $\mathrm { C O } _ { 2 }$ 与 $\mathrm { H } _ { 2 }$ 的分离功（实际泵功）分别为[18].

$$
\begin{array} { r l } { W _ { \mathrm { C O _ { 2 } , p u m p } } ~ { = } ~ n \& ^ { \sum _ { i \ge \hat { \mathcal R } _ { g } } ^ { \pm } } ~ ( T _ { 0 } + 2 7 3 . 1 5 ) } \\ { \quad } & { \frac { \lesssim } { \lesssim } \frac { P _ { 0 } } { P _ { \mathrm { C O _ { 2 } } } } ) ^ { 0 . 5 4 4 } ~ \ln ( \frac { P _ { 0 } } { P _ { \mathrm { C O _ { 2 } } } } ) } \end{array}
$$

$$
W _ { \mathrm { H } _ { 2 } , \mathrm { p u m p } } ~ = ~ 3 n \& ~ { \stackrel { \scriptscriptstyle \mathrm { E } \dot { \Xi } \dot { R } } { \scriptscriptstyle \mathrm { E } } } _ { g } ~ ( T _ { 0 } ~ + ~ 2 7 3 . 1 5 )
$$

式中， $R _ { g }$ 为通用气体常数， $T _ { 0 }$ 为环境温度， $P _ { 0 }$ 是环境压力， $P _ { \mathrm { C O } _ { 2 } }$ 为分离前二氧化碳的分压力， $P _ { \mathrm { H _ { 2 } } }$ 是分离前氢气的分压。分离的氢气储存在储罐中，并按需要供给到燃料电池中发电，则燃料电池发电功率为：

$$
W _ { \mathrm { F C } } = ~ 3 n \& H H V _ { \mathrm { H _ { 2 } } } \quad h _ { \mathrm { F C } }
$$

式中， $h _ { \mathrm { F C } }$ 是燃料电池的效率，并且根据参考文献取为 $5 0 \% ^ { [ 1 9 ] }$ 。因为 $\mathrm { H } _ { 2 }$ 的化学能一部分来源于太阳能，所以 $\mathrm { H } _ { 2 }$ 经由燃料电池产生的电能同样一部分来源于太阳能，燃料电池内由太阳能产生的电能为：

$$
\begin{array} { r } { W _ { \mathrm { s o l a r , F C } } ~ = ~ 3 n \& ~ \dot { \Xi } \dot { \mathcal { E } } I H V _ { \mathrm { H _ { 2 } } } ~ h _ { \mathrm { F C } } } \\ { ~ - ~ n \& ~ \dot { \Xi } \dot { \mathcal { E } } I H V _ { \mathrm { m e t h a n o l } } ~ h _ { \mathrm { F C } } } \end{array}
$$

# 3系统热力学性能模拟

# 3.1互补系统效率提升

太阳能光伏热化学互补系统作为多输入的太阳能发电系统，本文采用太阳能净发电效率评价其将太阳能转换为电能的能力，太阳能净发电效率定义如下：

$$
h _ { \mathrm { s { \mathrm { - } } } } = { \frac { W _ { \mathrm { s o l a r } } } { D N I \ { \stackrel { \Xi } {  } } } } = { \frac { W _ { \mathrm { _ { P V } } } + W _ { \mathrm { _ { s o l a r , F C } } } - \ W _ { \mathrm { _ { p u m p } } } } { D N I \ A } }
$$

式中， $\boldsymbol { W } _ { \mathrm { s o l a r } }$ 为太阳能净发电量， $W _ { \mathrm { p u m p } }$ 为气体膜分离

耗功（甲醇泵功可忽略)。如果将燃料电池产生的功率与分离过程耗功取为0，则上式可以认为是单一太阳能光伏发电系统的太阳能发电效率，其表达式为

$$
h _ { _ { \mathrm { s - e } } } = h _ { _ { \mathrm { o p t } } } ? h _ { _ { T , \mathrm { P V } } }
$$

如果将光伏电池效率 $h _ { { } _ { T , \mathrm { P V } } }$ 取为0，则式（13）所得效率为单一太阳能甲醇热化学发电系统的太阳能净发电效率。

图3为单一太阳能光伏发电系统、单一太阳能甲醇热化学发电系统与太阳能光伏热化学互补发电系统的太阳能净发电效率随运行温度的变化趋势。此处，“运行温度”对于单一光伏系统指的是光伏电池的运行温度，对于其余两个系统，“运行温度”指的是甲醇重整的反应温度。由图3可以发现，从运行温度对互补系统太阳能净发电效率影响的角度，在运行温度升高时，互补系统太阳能净发电效率呈现先升后降的趋势，但相对单一光伏系统与单一热化学系统，互补系统效率在运行温度变化时可以更稳定，这主要是因为单一光伏系统与单一热化学系统的效率随温度变化均较小，且两者效率对运行温度的响应相反的趋势之间产生相互抵消的作用。

![](images/2497d164684de50652923200abb0ee01f5b9ae6fa68a2d40d16974cf5e632eda.jpg)  
图3．单一太阳能光伏系统、单一太阳能甲醇热化学系统与太阳能光伏热化学互补系统的太阳能净发电效率随运行温度的变化趋势

Fig.3Net solar-electric efficiencies of the PV-only system, methanol thermochemical-only system and solar PV thermochemical hybrid system versus operation temperature

具体的，对于单一太阳能光伏系统，因光伏电池的负温度效应，其系统效率随光伏电池运行温度的升高而降低，如光伏电池运行温度为 $2 5 ^ { \circ } \mathrm { C } , 1 0 0 ^ { \circ } \mathrm { C }$ /$2 5 0 ^ { \circ } \mathrm { C }$ 时，其光伏组件发电效率分别为 $3 3 . 5 \%$ ， $3 1 . 3 \%$ 与 $2 6 . 6 \%$ ，（计入菲涅尔透镜光学损失后）系统发电效率分别为 $2 4 . 2 \%$ ， $2 2 . 5 \%$ 与 $1 9 . 1 \%$ ，对于单一太阳能热化学发电系统，随甲醇重整反应温度由 $1 0 0 ^ { \circ } \mathrm { C }$ 上升至 $2 5 0 ^ { \circ } \mathrm { C }$ ，其太阳能净发电效率由 $30 . 8 \%$ 升至$3 2 . 7 \%$ .这是因为，一方面，甲醇重整反应的转化率随反应温度升高而增大，使未反应的反应物回收量减小、回收过程能量损失减小，进而使得系统效率升高；另一方面，随温度的升高，系统的散热损失升高并进而使系统的效率降低。两者比较，温度较低时，转化率的影响占主导，使效率升高；但甲醇重整反应在 $1 0 0 { - } 2 5 0 ^ { \circ } \mathrm { C }$ 范围内反应转化率变化不大（如图1)，这也使得热化学系统效率升高幅度较小，这将有利于互补系统的效率稳定。

与单一太阳能光伏或单一太阳能热化学系统类似，在光伏热化学互补系统中（图3），随运行温度由 $1 0 0 ^ { \circ } \mathrm { C }$ 升高至 $1 7 0 \ \mathrm { ^ { \circ } C }$ ，光伏部分效率下降（ $2 2 . 5 \% - 2 1 . 9 \%$ ），热化学部分效率上升0 $2 1 . 1 \% - 2 2 . 5 \%$ ），此时后者占主导，使得太阳能净发电效率随温度升高逐渐升高（ $4 3 . 6 \% - 4 4 . 3 \%$ ）；随运行温度由 $1 7 0 ^ { \circ } \mathrm { C }$ 升高至 $2 5 0 ^ { \circ } \mathrm { C }$ ，光伏部分效率继续下降（ $2 1 . 9 \% - 2 1 . 1 \%$ ），热化学部分效率上升但幅度减缓（ $2 2 . 5 \% - 2 3 . 0 \%$ ），此时前者占主导，使得太阳能净发电效率随温度升高略微降低 $( 4 4 . 3 \% - 4 4 . 1 \% )$ 。总体而言，在 $1 0 0 { - } 2 5 0 ^ { \circ } \mathrm { C }$ 区间，光伏部分与热化学部分对运行温度的相反响应使得系统效率变化范围更窄、更稳定（ $4 3 . 6 \% - 4 4 . 3 \%$ ，小于单一光伏系统的$1 9 . 1 \% - 2 5 . 0 \%$ 与单一热化学系统的 $3 0 . 8 \% { - 3 2 . 7 \% }$ ）。此外，因为光伏电池部分在温度更低时具有更高的效率，所以增加光伏电池后互补系统相对单一热化学系统的最高效率对应的温度更低，这将有利于系统的设计与运行，尤其是可以拓宽光伏电池的选择范围，延长光伏电池的使用寿命。

整体来看，由图3可以发现，太阳能光伏热化学互补系统的太阳能净发电效率最高为 $44 . 3 \%$ ，相对于太阳能热化学系统最高效率 $3 2 . 7 \%$ 提高了11.6个百分点，相对于太阳能光伏发电系统在 $2 5 \mathrm { ^ \circ C }$ 时的效率 $2 4 . 2 \%$ 提高了20.1个百分点。互补系统相对单一热化学系统的效率提升主要是因为先光伏后热化学的太阳能梯级利用；相对单一光伏系统的效率提升主要是由于太阳热能（物理能）与甲醇化学能的品位耦合带来的太阳热能品位提升（至氢气的化学能）；光伏热化学系统的整体高效率则是来源于太阳能梯级利用以及物理能、化学能品位耦合间的协同作用。

其中，太阳能的梯级利用是通过在单一热化学系统的太阳能吸收转换过程引入光伏电池实现的：引入光伏电池后，在太阳能吸收转换过程中，高品位的太阳光能首先通过光伏电池部分转换为电能；与单一热化学系统相比，直接转换为低品位（ $2 0 0 ^ { \circ } \mathrm { C }$ 左右）热能的太阳能比例降低，太阳能吸收转换过程的不可逆损失减小，太阳能吸收转换过程获得的烟增加。为定量分析太阳能的梯级利用对太阳能吸收转换过程获得烟的影响，分别定义了单一热化学系统与光伏热化学互补系统在太阳能吸收转换过程单位太阳能转换的烟，

$$
E x _ { _ { \mathrm { t h e r m a l } } } = { \frac { Q ( T ) ? ( 1 } { D N I \times A _ { _ { \mathrm { T C - o n l y } } } } } T ^ { _ { 0 } } )
$$

$$
E x _ { _ { \mathrm { h y b r i d } } } = { \frac { W _ { _ { P V } } + Q ( T ) ? ( 1 } { T } } \quad { \frac { T _ { _ { 0 } } } { T } } )
$$

式中， $A _ { \mathrm { { T C - o n l y } } }$ 为单一热化学系统的聚光镜面积。相应地，互补系统相对单一热化学系统在太阳能吸收转换过程获得的烟增加比例被定义为

$$
r _ { _ { E x , \mathrm { a b s } } } = { \frac { E x _ { _ { \mathrm { h y b r i d } } } \cdot E x _ { _ { \mathrm { t h e r m a l } } } } { E x _ { _ { \mathrm { t h e r m a l } } } } }
$$

如图4所示，光伏热化学互补系统相对单一热化学系统在太阳能吸收转换过程获得了更多的烟，其烟增加比例随反应温度降低而单调升高，在反应温度为 $1 0 0 ^ { \circ } \mathrm { C }$ 时达到 $12 5 \%$ （继续降低反应温度，烟增加比例将更高，但本文温度范围限定100一$2 5 0 ^ { \circ } \mathrm { C }$ ），可见通过增加光伏电池，互补系统在太阳能吸收转换过程比单一热化学系统多获得了一倍以上的烟；之后随温度升高烟增加比例逐渐下降，并最终降为 $2 5 0 ^ { \circ } \mathrm { C }$ 时的 $69 \%$ ．这是因为温度较低时，单一热化学系统获得的热能的品位低，转换获得的烟较少，故而光伏热化学互补系统具有更大的提升空间，而且此时光伏电池的效率更高，可以获得更多的电能，从而减少太阳能转换为低品位热能的比例，最终导致温度较低时互补系统烟提升比例更大。

![](images/60e31d818b2a57cb1e519eb4fa7fe48d250bcb1327720fb796b355c64226297f.jpg)  
图4.单一热化学系统与光伏热化学互补系统在太阳能吸收转换过程获得的烟

物理能、化学能品位耦合主要是指太阳能经光伏转换后产生的热能（物理能）以甲醇的品位降低至氢气的品位作为代价，经由甲醇重整反应提升为更高品位的（氢气）化学能。这部分太阳能可长期稳定储存，并可按需转换为电能。为分析物理能、化学能品位耦合对系统效率的影响，选取低品位太阳热能直接经热机发电作为参比，则热机中单位太阳能转换的电能定义为

$$
E _ { _ { \mathrm { \scriptsize ~ h e a t ~ e n g i n e } } } = \frac { a \stackrel { \Xi \not \in } { \mathcal { Q } } ( T ) ( 1 - \frac { T _ { _ 0 } } { T } ) } { D N I \times d }
$$

式中， $\mathfrak { a }$ 为热机的热力学完善度，本文取 $0 . 6 ^ { [ 1 7 ] }$ 。在互补系统中，热化学部分单位太阳能转换的电能为

$$
E _ { _ \mathrm { t h e r m o c h e m i c a l } } = { \frac { W _ { _ \mathrm { s o l a r , F C } } } { D N I \times A } }
$$

则在互补系统中，物理能、化学能品位耦合带来的热利用部分的电能增加比例定义为

$$
r _ { \mathrm { c h e m } } = \frac { E _ { \mathrm { t h e r m o c h e m i c a l } } - E _ { \mathrm { h e a t \ e n g i n e } } } { E _ { \mathrm { h e a t \ e n g i n e } } }
$$

![](images/d18cc94e9fa49723f7e714db9453521be58eb9b0d3f65a2cce237caa4b107f34.jpg)  
Fig.4 Exergy obtained during solar energy absorption and conversion in the thermochemical-only system and solar PV thermochemical hybrid system

如图5所示，随运行温度由 $1 0 0 ^ { \circ } \mathrm { C }$ 升高至 $2 5 0 ^ { \circ } \mathrm { C }$ =太阳热能经热机利用产生的电能不断升高（占太阳能输入能量比例由 $5 . 5 \%$ 升至 $8 . 1 \%$ ），这主要是因为随温度不断升高，热能的品位不断升高，从而其转换的电能不断增加；随运行温度由 $1 0 0 ^ { \circ } \mathrm { C }$ 升高至$2 5 0 ^ { \circ } \mathrm { C }$ ，太阳热能经热化学利用产生的电能也不断增多，这是因为随温度升高，热化学反应转化率不断升高（如图1），且未反应的反应物回收过程的损失减小，从而产生的电能增加。通过对比可以发现，太阳热能经热化学利用产生的电能高于太阳热能经热机利用产生的电能，提高比例在 $1 6 4 \% - 2 8 1 \%$ 范围内。这主要是因为，一方面，太阳热能品位低，直接通过热机转换为电能的效率受限于卡诺效率而较低（即提高潜力大）；另一方面，以甲醇品位降低为代价，太阳热能经甲醇重整反应转换为品位较高的化学能，发电效率不再受到热能低品位的限制。

# 3.2互补系统能量份额

除发电效率优势外，热化学部分的储能优势还弥补了光伏部分的储能劣势，提升了系统发电稳定性和持续性。如图6所示，太阳能产生的电能来源于两部分，一部分来自光伏电池直接发电，另一部分来自热化学部分吸收的太阳热能转换的电能；分析表明，两部分电能的比例在1:1左右，因此约 $50 \%$ 的太阳能净发电量可通过氢气（热化学产物）化学能转换而来。在此基础上，可以根据太阳辐照的变化实时调控氢气供应速度，使燃料电池的电能输出起到为光伏电池的电能输出削峰填谷的作用，从而使得整个系统的电能输出更稳定。

另一方面，互补系统太阳能净发电量占系统总发电量的 $2 5 \%$ 左右，而单一热化学系统中该比例仅为 $14 \%$ ，这主要是因为光伏电池的引入增加了太阳能的利用率，提高了太阳能净发电量所占份额。随运行温度的升高，太阳能净发电量占系统总电量的比例由 $2 5 . 9 \%$ 微降至 $2 4 . 8 \%$ ．这是因为对于每单位太阳能输入，随着运行温度升高，光伏电池提供给热化学反应的热能上升（同时光伏发电量下降），将驱动更多的甲醇发生重整反应，导致甲醇产生电量的份额逐渐增加、太阳能净发电量的份额逐渐下降。

![](images/82c509becdb93aa57f1e252a5c26b8b8a22f636494bf8dc0297f9a13977ab50b.jpg)  
图5.物理能化学能品位耦合带来的热能转换电能的增加 Fig.5 Increase of electricity from solar thermal energy resulting from coupling between physical energy and chemical energy   
图6.光伏热化学互补系统发电量份额

# 4结论

本文基于能的梯级利用思想，提出了太阳能聚光光伏与甲醇重整热化学互补发电系统。该系统具有太阳能发电效率高、储能比例大、供电稳定与化石能源比例低等优点。系统通过太阳能梯级利用、物理能与化学能的品位耦合，在运行温度为 $1 7 0 ^ { \circ } \mathrm { C }$ 时，获得了 $44 . 3 \%$ 的太阳能理论净发电效率，高于单一热化学发电系统的 $3 2 . 7 \%$ 与单一聚光光伏发电系统的$2 4 . 2 \%$ ，而且约 $50 \%$ 太阳能净发电量来自于甲醇重整产物氢气，以化学途径实现了较高比例的太阳能储能。系统可通过调控太阳能燃料（即甲醇重整产物氢气）流量对光伏输出削峰填谷，提高太阳能供电稳定性。相对于单一太阳能甲醇热化学发电系统，本文提出的互补系统通过引入光伏电池提高了太阳能总体发电效率，降低了化石能源占比暨对化石能源的依赖度。本文提出的太阳能光伏热化学互补系统为太阳能技术的发展提供了新的思路。

# 参考文献

[1] International Energy Agency. Technology Roadmap: Solar Photovoltaic Energy [R].2014.   
[2] Shockley W,Queisser H J.Detailed Balance Limit of Efficiency of p-n Junction Solar Cells [J].Journal of Applied Physics,1961,32(3):510-519.   
[3] Marti A, Araujo G L. Limiting Efficiencies for Photovoltaic Energy Conversion in Multigap Systems [J]. SolarEnergyMaterials&SolarCells,1996, 43(2):203-222.   
[4] https://www.nrel.gov/pv/assets/images/efficiency-chart.png   
[5] Chubb L，Donald． Performance Characteristicsofa Combination Solar Photovoltaic Heat Engine Energy Converter. [C]//Proceedings of the 22nd Intersociety Energy Conversion Engineering Conference,Philadelphia, 10-14 August 1987:254-263.   
[6] Vorobiev Y,Gonzalez-Hernandez J,Vorobiev P,et al. Thermal-photovoltaic Solar Hybrid System for Efficient Solar Energy Conversion [J]. SolarEnergy，2006, 80(2):170-176.   
[7] HAN Xue,XU Chao, JU Xing,etal.Energy Analysis of a Hybrid Solar Concentrating Photovoltaic/concentrating Solar Power (CPV/CSP） System [J]. Science Bulletin, 2015,60(4):460-469.   
[8] Kosmadakis G,Manolakos D,Papadakis G.Simulation and Economic Analysis of a CPV/thermal System Coupled with an Organic Rankine Cycle for Increased Power Generation [J]. Solar Energy,2011,85(2):308-324.   
[9] Tourkov K，Schaefer L.Performance Evaluation of a PVT/ORC (Photovoltaic Thermal/organic Rankine Cycle) System with Optimization of the ORC and Evaluation of Several PV (Photovoltaic）Materials [J].Energy，2015, 82:839-849.   
[10]Lecompte S,Huisseune H, van den Broek M, etal.Review oforganic Rankine Cycle(ORC)Architectures for Waste Heat Recovery [J].Renewable and Sustainable Energy Reviews,2015,47:448-461.   
[11]金红光 林汝谋．能的综合梯级利用与燃气轮机总能系 统[M]．科学出版社,2008. JIN Hongguang，LIN Rumou． Cascade Utilization of Energy and Gas Turbine Total Energy System [M]. Beijing: Science Press,2008.   
[12] HONG Hui, JIN Hongguang, JI Jun,et al. Solar thermal power cycle with integration of methanol decomposition and middle-temperature solar thermal energy[J]． Solar Energy,2005,78(1):49-58.   
[13]LI Wenjia,HAO Yong.Efficient solar power generation combiningphotovoltaicsandmid-/low-temperature methanol thermochemistry [J].Applied Energy，2017, 202:377-385.   
[14] Aspen Plus $\textsuperscript { \textregistered }$ .Aspen technology， Inc.， version 8.2, http://www.aspentech.com/.   
[15] LIN Lili, ZHOU Wu,GAO Rui, et al. Low-temperature Hydrogen Production from Water_and Methanol Using Pt/α-MoC Catalysts [J].Nature,2017,544(7648): 80-83.   
[16]van Leest R H,de Kleijne K，Bauhuis G J,et al. Degradation mechanism(s） of GaAs solar cells with Cu contacts [J].Physical Chemistry Chemical Physics,2016, 18(15):10232-10240.   
[17]Kribus A,Mittelman K G.Potential of Polygeneration with Solar Thermal and Photovoltaic Systems [J].Journal of Solar Energy Engineering,2008,130(1):555-567.   
[18] Jarrett C,Chueh W,Yuan C,et al. Critical Limitations on the Efficiency of Two-step Thermochemical Cycles [J]. Solar Energy,2016,123:57-73.   
[19] Bizon N. Improving the PEMFC Energy Efficiency by Optimizing the Fueling Rates Based on Extremum Seeking Algorithm [J]. International Journal of Hydrogen Energy, 2014,39(20):10641-10654.