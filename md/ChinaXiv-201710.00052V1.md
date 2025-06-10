# 进气预冷富燃预燃混排涡扇发动机热力循环

赵巍1,²，赵庆军1,2,3，徐建中1

(1．中国科学院工程热物理研究所，北京100190；2.中国科学院大学，北京100190;3．中国科学院轻型动力重点实验室，北京100190)

摘要：为满足高超声速飞行器对高比冲和大推力发动机的需要，提出了一种可重复使用的进气预冷富燃预燃混合排气涡扇发动机(Pre-cooled andFuel-rich Pre-bumed Mixed-flow Turbofan，PFPMT)热力循环。PFPMT发动机的特点是增大内涵空气进气预冷程度，内涵压气机为富燃燃气发生器提供空气作为氧化剂，内涵空气与预冷器出口燃料混合燃烧产生富燃燃气，驱动涡轮、带动内涵压气机与风扇增压，风扇外涵空气与涡轮出口排气在主燃烧室中掺混燃烧，产生高温燃气由喷管产生推力。对发动机热力循环进行了参数化分析，发动机比冲随着压气机压比的增大而增加，尤其是随着风扇压比增加的更为明显；单位推力主要随风扇压比增加而增加，受内涵压比影响较小。发动机地面的比冲与单位推力分别可以达到4500s与 $9 0 0 \mathrm { N s / k g }$ 以上；在Ma5.0飞行条件下，发动机比冲与单位推力在3500s与 $1 1 0 0 \mathrm { N \ s / k g }$ 以上。

关键词：高超声速飞行；发动机循环；参数化分析；富燃燃烧；进气预冷中图分类号：V235 文献标识码：A

# A Pre-cooled and Fuel-rich Pre-burned Mixed-flow Turbofan Cycle

Wei Zhao1,2, Qingjun Zhao1,2.3, Jianzhong ${ \mathrm { X u } } ^ { 1 }$ （20 (1. Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing 100190,China;   
2.University of Chinese Academy of Sciences,Beijing 10o190, China;   
3. KeyLaboratory of Light-duty Gas-turbine, Chinese Academy of Sciences,Beijing 10o190, China)

Abstract: A Pre-cooled and Fuel-rich Pre-burned Mixed-flow Turbofan (PFPMT) Cycle is presented for reusable hypersonic vehicles based on practical technologies.PFPMT uses an inlet hydrogen precooler to reduce the inlet temperature for a core flow compressor and thus reduces the compression work for a given pressure ratio. The core flow compressor provides pressurized air for a fuel-rich gas generator to burn with the warmed hydrogen from the precoolers. The gas from the gas generator is introduced to a turbine to drive the core flow compressor and a bypassflow fan.The exhaust of the turbine is mixed with the bypass flow in a combustor at an equal total pressure,and is ignited.The high temperature combustion products are expanded in a nozzle to generate thrust.The emphasis in this work is on the analysis of the design parameters for feasible PFPMT. Parametric studies are performed with the following parameters: 1) the bypass ratio; 2) the core flow fuel ratio, which is defined as the core flow mass over the fuel mass; 3) the core compressor pressure ratio; and 4) the bypass fan pressure ratio. The cycle simulation results for a PFPMT engine show that on the ground the specific impulse and specific thrust are greater than 4965s and （204 $9 4 4 \mathrm { N / ( k g / s ) }$ respectively. At the flight Mach number of 5.0 the specific impulse and specific thrust are greater than 3500s and $1 1 0 0 \mathrm { N } / ( \mathrm { k g } / \mathrm { s } )$ respectively.

Key words: hypersonic flight; engine cycle; parametric analysis; fuel-rich combustion; inlet precool

# 0引言

高超声速飞行器对实现快速的长距离运输系统具有积极意义[1]。在过去数十年中，研究人员探索了多种用于超声速飞行的组合循环发动机，其中包括有燃气发生器式 ATR(ATRGG，GasGenerator)、膨胀式ATR(ATR EX，Expander)和

SABRE等。ATRGG主要由风扇，高压富燃燃气发生器以及涡轮组成，通常采用双组元推进剂，包括燃料与氧化剂。该发动机具有高推重比、但比冲较低[2]。ATREX采用燃烧室换热器替代ATRGG的燃气发生器，加热燃料驱动涡轮。结合进气预冷，发动机最大工作马赫数可以达到 $\mathrm { M a } 6 ^ { [ 3 ] }$ 该发动机所需氧化剂从大气获得，比冲较高但推重比低于ATRGG。SABRE发动机的进气道出口空气在进入高压比压气机前被预冷至低温，压气机排气分别进入主燃烧室与富燃预燃燃烧室，高温富燃燃气由预燃室中排出通过换热器加热氨工质。被加热的氮工质驱动涡轮带动空气压气机，进入换热器被低温液氢燃料冷却。富燃燃气进入主燃烧室与空气混合燃烧，高温燃气由尾喷管排出产生推力[4]。SABRE 发动机涉及多种工质、结构复杂、不易实现。

本文提出了一种可水平起飞，无模态转换工作至高超声速的预冷富燃预燃混合排气涡扇发动机(PFPMT)热力循环。PFPMT发动机无需携带氧化剂、燃烧室不布置换热器，同时没有复杂氨中间循环，具有良好的比冲与推重比。

# 1 循环描述

PFPMT发动机循环流程接近涡扇发动机，但其设计意图主要为了解决ATRGG比冲较低的问题。ATRGG 燃气发生器中的氧化剂与燃料进行富燃燃烧产生高温富燃燃气驱动涡轮，发动机比冲相对较低。若ATR发动机氧化剂能够完全来自大气，发动机比冲将得到明显改善。

在ATRGG发动机中，为了使压气机与涡轮出口达到压力平衡，需要采用高压泵将氧化剂输送至涡轮上游富燃燃气发生器内。高压燃气发生器所产生的富燃燃气与压气机中空气之比较小，如以甲烷作为燃料燃空比取值在1/8至1/6范围。由于富燃燃气流量相对较低，涡轮膨胀比通常较高，一般为 $1 5 { \sim } 2 5$ ，使燃气发生器出口压力较大。

若能够降低涡轮膨胀比，将可以降低燃气发生器室压和燃料泵压比，从而有可能采用空气压气机替代燃料泵供应发动机所需的氧化剂，从而降低比冲。为此考虑：一方面，当给定涡轮前温度时，采用富燃预燃室增加富燃燃气流量、从而降低涡轮膨胀比和进口压力。此时可以增加涡轮叶高、减少涡轮二次流与叶顶泄漏流损失。另一方面，采用液氢进气道预冷器降低风扇与压气机入口温度，减少压缩部件耗功，从而降低涡轮膨胀比。采用上述两方面措施实现涡轮膨胀比下降，采用为数不多的压气机级即可实现涡轮入口所需的压力。涡轮膨胀比下降带来的另一项收益是减少涡轮级数，从而增大发动机推重比。

基于上述认识，建立PFPMT热力循环流程，如图1所示。两组液氢/空气预冷器安装在进气道内作为预冷器，一组位于风扇外涵入口，另一组位于内涵入口。内涵压气机压缩来流空气，排气与预冷器出口燃料在燃气发生器中进行掺混燃烧，产生富燃燃气驱动涡轮带动风扇与内涵压气机；涡轮排气与风扇外涵排气在主燃烧室中掺混燃烧，高温燃气经由尾喷管排除产生推力。在循环中，内涵压气机出口压力是涡轮膨胀比与风扇压比的乘积。由PFPMT的循环流程可见，该循环无需携带氧化剂，比冲比ATRGG 循环将有显著提高。

![](images/7a38d9c72774c184072e22667ac724b92eedec6382154a3ac81e52c65c2439b9.jpg)  
图1PFPMT热力循环结构示意图  
Fig.1PFPMT cycle component configuration

# 2 部件与循环模型

认识PFPMT发动机的基本性能需要建立发动机工质、部件与热力循环模型。

# 2.1工质模型

工质在给定条件下的热物性参数如焓、熵与组分相关。空气由 $21 \%$ 的 $\mathrm { O } _ { 2 }$ 与 $7 9 \%$ 的 $\Nu _ { 2 }$ 组成。燃气发生器与燃烧室中产物组分主要包括：H,O,OH, $\mathrm { H O } _ { 2 }$ $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ $\mathrm { H } _ { 2 } \mathrm { O }$ $\Nu _ { 2 }$ ,NO,N, $\mathrm { H } _ { 2 }$ 和 $\mathrm { O } _ { 2 }$ 。在给定压力和氧燃比前提下，燃烧产物由基于最小吉布斯自由能的化学平衡方法计算获得。假设涡轮与尾喷管中工质为冻结流，各种组分焓值由高阶多项式获得。

# 2.2进气道

自由来流空气通过进气道减速，静温与静压取值如下：

$$
\begin{array} { l } { T = ( 2 8 8 . 1 5 - 6 . 5 \times H ) } \\ { P = 1 0 1 3 2 5 \times ( 1 - \displaystyle \frac { H } { 4 4 . 3 0 8 } ) ^ { 5 . 2 5 5 3 } } \end{array} \left( 0 \leq H \leq 1 1 \right)
$$

$$
\begin{array} { l } { { T = 2 1 6 . 7 } } \\ { { { } } } \\ { { P = 0 . 2 2 7 \times e ^ { ( \frac { 1 1 - H } { 6 . 3 3 8 } ) \times 1 0 ^ { 5 } } } } \end{array} \left( H > 1 1 \right)
$$

在给定飞行高度与马赫数前提下，进气道入□总温、总压:

$$
P _ { 0 } = P ( 1 + \frac { k - 1 } { 2 } M a ^ { 2 } ) ^ { \frac { k } { k - 1 } }
$$

$$
T _ { 0 } = T ( 1 + \frac { k - 1 } { 2 } M a ^ { 2 } )
$$

出口总压：

$$
P _ { 2 } = P _ { 1 } \sigma
$$

# 2.3预冷器

预冷器将风扇、内涵压气机出口温度控制在材料所能承受范围之内，利用空气来流预热燃料，同时可改善进气道与压气机的流量匹配性能。在给定预冷器换热有效度与燃空比的前提下，基于能量守恒可获得预冷器冷端与热端出口温度：

$$
T _ { c 1 } = T _ { c 2 } - \mathfrak { s } ( T _ { h 1 } - T _ { c 1 } )
$$

$$
T _ { h 2 } = T _ { h 1 } - { \frac { C _ { c } } { C _ { h } } } ( T _ { c 2 } - T _ { c 1 } )
$$

# 2.4风扇与内涵压气机

风扇与压气机用于提供PFPMT循环中的压升。在已知压气机压比前提下，等熵过程中的焓增可通过下式计算：

$$
\Delta S = \int C p \frac { d T } { T } - R \ln ( \frac { P _ { _ 2 } } { P _ { _ 1 } } )
$$

$$
\Delta H _ { i } = f ( S _ { 1 } , P _ { 2 } ) - f ( S _ { 1 } , P _ { 1 } )
$$

根据压气机效率公式计算压缩过程中实际消耗功率：

$$
\eta = \frac { \Delta H _ { i } } { W }
$$

在效率给定条件下，风扇与压气机出口焓为：

$$
H _ { c 2 } = f \big ( \pi _ { c } , \eta _ { c } \big )
$$

$$
H _ { f 2 } = f \big ( \pi _ { f } , \eta _ { f } \big )
$$

空气总温为焓与总压的函数：

$$
T _ { 0 } = f ( H , P _ { 0 } )
$$

在给定空气质量流量前提下，风扇与内涵压气机所消耗的功率为：

$$
W = m _ { f } ( H _ { f 2 } - H _ { 1 } ) + m _ { c } ( H _ { c 2 } - H _ { 1 } )
$$

# 2.5预燃室与主燃烧室

预燃室与主燃烧室内分别为富燃燃烧与贫燃燃烧，所采用的燃烧模型相同。燃烧过程中燃料与空气混合比根据燃料与空气流量获得，再根据燃空比计算混合燃气单位质量焓值。基于定焓定压原则计算预燃室与主燃烧室内化学平衡，反应后产物组分与热物性参数通过最小吉布斯自由能方法获得。

$$
\delta G = \sum _ { j = 1 } ^ { N S } ( u _ { j } + \lambda _ { i } a _ { i j } ) \delta n _ { j } + \sum _ { i = 1 } ^ { l } ( b _ { i } - b _ { i } ^ { o } ) \delta \lambda _ { i } = 0
$$

$$
u _ { j } + \sum _ { i = 1 } ^ { l } \lambda _ { i } a _ { i j } = 0
$$

$$
b _ { i } = \sum _ { j = 1 } ^ { N S } a _ { i j } n _ { j }
$$

# 2.6涡轮

涡轮输出功率与风扇、压气机消耗功率平衡，涡轮出口焓值为：

$$
H _ { 2 } = H _ { 1 } - W _ { t }
$$

在假设涡轮效率前提下可获得等熵条件下涡轮出口焓值：

$$
H _ { i 2 } = \frac { H _ { 2 } } { \mathfrak { \eta } _ { t } }
$$

根据等熵条件下涡轮出口焓值与涡轮入口熵值可获得涡轮膨胀比：

$$
\pi _ { t } = f ( H , S )
$$

根据计算所得涡轮出口压力与温度，可获得涡轮出口截面工质热物性参数。

# 2.7尾喷管

尾喷管用于加速燃烧室高温燃气，使其膨胀至环境压力并高效的产生推力。假设尾喷管喉道面积与出口面积均可调，并且在理想状态下膨胀至环境压力。采用速度损失系数(实际速度与等熵膨胀速度之比)计算尾喷管处损失：

$$
V _ { n } = \sigma V _ { i _ { - } n }
$$

# 2.8循环模型

根据上文所述PFPMT发动机热力循环结构将各部件组成发动机热力循环数学模型。部件进出口工质流量保持平衡，相邻两部件间交界面相同工质热物性参数相同。为确保风扇外涵道出口空气与涡轮出口燃气掺混可行，排气出口总压保持平衡：

$$
P _ { f 2 } = P _ { t 2 }
$$

# ChinaXiv合作期刊

基于部件模型中的能量守恒方程、部件间的流量守恒方程以及风扇旁路与涡轮出口的压力平衡关系，获得了确定风扇涵道比的非线性方程。通过将风扇压比、内涵预冷器或外涵预冷器燃料与空气流量之选为设计参数，可求得预燃室与主燃烧室出口排气温度：

$$
T _ { g 2 } = f \big ( \pi _ { f } , \gamma \big )
$$

$$
T _ { c c 2 } = f \big ( \pi _ { f } , \gamma \big )
$$

采用迭代方法进行求解，在求解过程中需首先给定变量的初始值。

采用Cantera接口开发了工质、部件以及发动机热力循环的Matlab数学模型。循环中所包含非线性方程组采用Matlab自带算法求解。

# 2.9性能计算

发动机单位推力 $F _ { s }$ 为非安装推力：

$$
F _ { s } = ( 1 + \gamma ) V _ { n } - V _ { 0 }
$$

比冲为：

$$
I _ { s p } = { \frac { 1 } { g } } ( { \frac { 1 } { \gamma } } + 1 ) V _ { n } - { \frac { 1 } { g \gamma } } V _ { 0 }
$$

通过热力循环模型计算尾喷管出口速度 $V _ { o u t }$ ，发动机单位推力 $F _ { s }$ 以及比冲 $I _ { S P }$ 。

# 3循环参数化分析

循环参数分析主要研究了工质热物性变化所揭示的不同飞行条件下，循环参数对设计点循环性能的影响。所选取的PFPMT循环参数包括：1)风扇压比 $\pi _ { f }$ ；2)内涵压气机压比 $\pi _ { C } : 3 )$ 风扇预冷器燃空比 $\gamma _ { f }$ ；4)内涵压气机预冷器燃空比$\gamma _ { c }$ 。与传统大涵道比分别排气风扇发动机不同，涵道比并非循环参数，因为该参数可通过上述4个循环参数以及风扇与涡轮的出口压力平衡条件确定。分析过程中部件参数取值如表1所示。

表1PFPMT循环部件参数Table 1. Constant parameters for the PFPMT cycle analysis  

<html><body><table><tr><td>Parameters</td><td>Values</td></tr><tr><td>内涵预冷器换热有效度</td><td>0.85</td></tr><tr><td>外涵预冷器换热有效度</td><td>0.85</td></tr><tr><td>内涵预冷器高温侧总压恢复系数</td><td>0.90</td></tr><tr><td>内涵预冷器低温侧总压恢复系数</td><td>0.90</td></tr><tr><td>外涵预冷器高温侧总压恢复系数</td><td>0.90</td></tr></table></body></html>

<html><body><table><tr><td>外涵预冷器低温侧总压恢复系数</td><td>0.90</td></tr><tr><td>混合器总压恢复系数</td><td>0.92</td></tr><tr><td>风扇等熵效率</td><td>0.89</td></tr><tr><td>压气机等熵效率</td><td>0.88</td></tr><tr><td>燃气发生器燃烧效率</td><td>0.96</td></tr><tr><td>燃气发生器总压恢复系数</td><td>0.95</td></tr><tr><td>涡轮等熵效率</td><td>0.89</td></tr><tr><td>燃烧室燃烧效率</td><td>0.98</td></tr><tr><td>燃烧室总压恢复系数</td><td>0.95</td></tr><tr><td>尾喷管速度损失系数</td><td>0.97</td></tr></table></body></html>

图2a)-e）为地面状态，不同风扇压比前提下涵道比、燃气发生器出口温度、燃烧室出口温度、发动机比冲及推力随内涵压比的变化规律。

在图2a)中，在给定风扇压比前提下涵道比随内涵压比的增加而增大。由于风扇外涵总压与涡轮出口总压保持平衡，涡轮膨胀比等于内涵压气机压比与风扇压比之商。因此，在风扇压比为常数前提下，随着内涵压比的增加涡轮膨胀比等比例增大。由于涡轮进口温度远大于内涵压气机入口温度，从式(27)中可看出，涡轮输出功的增量大于内涵压气机消耗功的增量。

$$
W = { \frac { k } { k - 1 } } R T _ { 1 } ( ( { \frac { P _ { 2 } } { P _ { 1 } } } ) ^ { \frac { k - 1 } { k } } - 1 )
$$

此时需增大风扇外涵空气流量以消耗过多的涡轮功，发动机涵道比增加。

在给定内涵压气机压比前提下，受风扇外涵与涡轮出口压力平衡约束，随着风扇压比的下降，涵道比增加而涡轮膨胀比下降。由于内涵压气机工作状态保持不变，多余的涡轮输出功需通过增大风扇消耗功来平衡。在风扇压比下降前提下，通过增大涵道比实现风扇消耗功的增加。因此，涵道比随风扇压比下降而增大。

从图2b)中可看出，在风扇压比一定时，随着内涵压气机压比的增加涡轮前温度下降。在内涵压气机压比一定条件下，随着风扇压比的增加涡轮前温度增大。根据上文所述，通过增大内涵压气机压比或减小外涵风扇压比，风扇流量及涵道比增加。由于外涵道燃空比取值为常数，流入燃气发生器的燃料随着涵道比的增加而增大，富燃燃气总温下降。

从图2c)中可看出，主燃烧室出口温度变化趋势与预燃室出口温度变化趋势相同，同样可基于涵道比的变化进行解释。在本文分析过程中，外涵燃空比取值约为内涵燃空比取值一半，若涵道比增加，主燃烧室中燃空比必然减小，进而导致燃烧室出口温度下降。

当内涵压比大于5时，发动机推力受内涵压比变化影响较小。由于内涵压比取值大于5对应涵道比大于2.5，此时燃空比与主燃烧室温度主要受外涵燃空比变化而非内涵燃空比变化的影响。因此，在高涵道比取值前提下内涵压气机压比对单位推力影响较小。而风扇压比的增加使发动机单位推力迅速增大。如上文所述，随着风扇压比的增加，燃烧室出口温度与尾喷管入口总压增大。以上两方面因素使得发动机推力在吸入空气流量一定前提下增大。

如图2e)中所示，发动机比冲随内涵压比与风扇压比的增加而增大。根据上文分析可知，内焓压气机增加导致涵道比增大以及燃烧室温度下降，发动机比冲增加。虽然外涵压比增大导致涵道比下降以及燃烧室温度上升，但尾喷管总压增大，发动机比冲上升。

从图2e)中可看出，发动机比冲随内涵压比增加而增大。发动机比冲可表示为：

$$
I _ { _ { S P } } = \frac { F _ { s } } { \gamma g }
$$

由于涵道比随内涵压比的增加而增大，同时外涵道燃空比取值小于内涵道燃空比，循环燃空比随内涵压气机压比的增加而下降。应注意单位推力对内涵压气机压比并不敏感，因此随着内涵压气机压比的增加发动机比冲增大。图2e)中同样显示，在 $\pi _ { { \scriptscriptstyle C } } = 4$ 时， $\pi _ { f } = 2 . 5$ 可获得发动机最大比冲。这是由于在 $\pi _ { C } = 4$ 条件下，随着风扇压比的增加发动机单位推力迅速增大而发动机燃空比缓慢下降。当内涵压气机压比大于5时，风扇涵道比大于2.5，发动机燃空比主要受外涵道燃空比影响。在内涵压气机压比大于5时，发动机比冲随风扇压比增加而增大。

![](images/eda88fdc29b2f4541386027f6e85fbbd718980b469141db60d37b16728a9d8e2.jpg)

![](images/e7cb44ecdb8845d89838d369c6d164e96f3d70cab4ad43831becc504ae51ee80.jpg)  
图 $2 \mathrm { M a } _ { 0 } { = } 0$ 发动机与循环参数随内涵压气机压比变化规律Fig.2 Cycle performance and parameters vs core flow pressureratio at $\mathrm { M a } _ { 0 } { = } 0$

对于速度 $\mathrm { M a } 5 . 0$ 、高度 $2 7 ~ \mathrm { k m }$ 飞行条件，部件与循环参数在不同外涵风扇压比下随着内涵总压的变化如图3a)－e)所示。除比冲之外，涵道比、燃气发生器出口温度、燃烧室出口温度和单位推力的变化趋势与图2基本一致。在Ma5，内、外涵压比及其差值明显下降，内、外涵的燃料比与在Ma0时相比更为接近。这样循环的燃料/空气比对涵道比变得不再敏感，单位推力基本不随着外涵压比的变化而改变。由于燃料/空气比正比于外涵压比，比冲作为单位推力和燃料/空气比的比值，会随着外涵风扇的压比而下降。

基于对循环参数之间相互关系的认识和理解，表2给出了在飞行速度为Ma0、3和5较为理想的PFPMT 循环参数。内涵和外涵压比均随着飞行马赫数的的升高而降低， $\gamma _ { f }$ 明显增加的原因是为了降低外涵风扇出口温度和涡轮进口温度至材料许用的水平。尽管这样，仍然需要采用低温氢蒸汽的气膜冷却，当飞行马赫数高于4时。同样由于增加的 $\gamma _ { f }$ ，燃烧室出口温度明显增加，有利于在高飞行马赫数下阻止单位推力衰减。在Ma5时，虽然比冲与地面Ma0状态相比下降了$20 \%$ ，PFPMT与冲压发动机在Ma5时大概在3000s左右的比冲相比仍然表现出了明显的优势。

表2不同飞行条件下循环参数  
Table 2.Cycle parameters at various flight conditions   

<html><body><table><tr><td>Parameters</td><td>Mao=0, H=0km</td><td>Mao=3, H=20km</td><td>Mao=5, H=27km</td></tr><tr><td>πc</td><td>5.0</td><td>4.0</td><td>2</td></tr><tr><td>π</td><td>2.4</td><td>1.8</td><td>1.3</td></tr><tr><td>Tc (K)</td><td>315</td><td>579</td><td>941</td></tr><tr><td>Tf(K)</td><td>315</td><td>546</td><td>927</td></tr><tr><td>Yc</td><td>0.035</td><td>0.035</td><td>0.036</td></tr><tr><td>Yf</td><td>0.017</td><td>0.023</td><td>0.029</td></tr><tr><td>BPR</td><td>7.3</td><td>7.3</td><td>7.3</td></tr><tr><td>TIT (K)</td><td>1312</td><td>1401</td><td>1773</td></tr><tr><td>π</td><td>2.0</td><td>2.1</td><td>1.5</td></tr><tr><td>Tc(K)</td><td>1907</td><td>2343</td><td>2772</td></tr><tr><td>Fs</td><td>944</td><td>1180</td><td>1129</td></tr><tr><td>Isp(s)</td><td>4965</td><td>4987</td><td>3860</td></tr></table></body></html>

![](images/73ca5e6494dce735a559d1a2fe2e7d0b9fc12147792a9b0b4078e6713bc176b1.jpg)  
a) BPR vs $\pi _ { C }$

![](images/1e70d06bcbc05dbacdfdf71fa985396f58f567488a8210db3d46b876055b7002.jpg)

![](images/e742c13186b1929d2a6930534984d45d16c86ee06b72c51ea15143d47e7458cf.jpg)  
图 $3 \mathrm { M a } _ { 0 } { = } 5$ 发动机与循环参数随内涵压气机压比变化规律Fig.3 Cycle performance and parameters vs core flow pressureratio at $\mathrm { M a } _ { 0 } { = } 5$

# 4结论

1)PFPMT热力循环分析表明PFPMT发动机能够实现地面水平起飞至高超声速飞行，具有良好的比冲性能。与SABRE和Simitar等复杂热力循环相比，PFPMT的突出优点是减小了系统的复杂性，没有无模态转换装置和采用第三工质的中间热力循环，能够明显提高发动机推重比。

2)参数化的PFPMT热力循环分析指明了部件设计变量对发动机性能和部件参数产生的影响作用，能够有效指导不同飞行条件下满足比冲和推力需要的PFPMT发动机总体性能方案设计。发动机比冲随着压气机压比的增大而增加，尤其是随着风扇压比增加的更为明显；单位推力主要随风扇压比增加而增加，受内涵压比增加的影响较小。

3)当给定外涵风扇压比时，PFPMT涵道比随着内涵压比上升而增加；当给定内涵压比时，PFPMT涵道比随着外涵压比上升而下降。涵道比的上升导致涡轮进口温度和燃烧室出口温度下降，单位推力降低，同时存在最优外涵压比使比冲最大。

# 参考文献

[1]Steelant,J.，“Sustained Hypersonic Flight in Europe: Technology Drivers for LAPCAT II,’16th AIAA/DLR/DGLR International Space Planes and Hypersonic Systems and Technologies Conference,

2009-7240,2009.   
[2] Kerrebrock J.L.; Reijnen D.P.; Ziminsky W. S.; Smilg L. M.， “Aspirated Compressors” ASME International Gas Turbine & Aeroengine Congress & Exhibition, 97-GT-525, June 1997.   
[3] Tanatsugu,N.，Sato，T.，Balepin，V.，et al., "Development Study on ATREX Engine,” Acta Astronautica, Vol.41, No.12, 1997, pp. 851-862.   
[4]Varvill， R.， Bond， A.，“The SKYLON Spaceplane,” Journal of the British Interplanetary Society, Vol.57,2004, pp.22-32.