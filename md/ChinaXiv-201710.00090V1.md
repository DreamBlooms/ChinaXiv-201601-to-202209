# 集成 $\mathbf { S C O } _ { 2 }$ 动力循环的燃煤电站余热回收系统研究

刘明张旭伟 王朝阳李根严俊杰(西安交通大学动力工程多相流国家重点实验室，西安710049)

摘要低温烟气热能的高效梯级利用是火电厂节能减排的重要方向之一。本文结合某 $1 0 0 0 ~ \mathrm { M W }$ 超临界机组，对常规低温省煤器烟气余热利用系统进行了热力学分析，发现该系统可使系统发电标准煤耗率降低 $2 . 5 0 \ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ ，但烟分析发现，空气预热器焊耗散占输入烟的 $2 2 . 0 3 \%$ ，多于锅炉排烟所携带的烟。为此，本文提出了集成 $\mathrm { \ S C O _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统，旨在减少空气预热器中的烟耗散。对 $\mathrm { { S C O } _ { 2 } }$ 动力循环参数进行了优化，在优化参数下该系统可以使发电标准煤耗率降低 $3 . 6 2 ~ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ ，进一步集成低温省煤器可使发电标准煤耗率降低达 $5 . 5 8 \ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ ，最后采用烟分析结果解释了系统节能的本质原因。

关键词火力发电厂；低温余热； $\mathrm { \ S C O _ { 2 } }$ 动力循环；烟分析中图分类号：TK112 文献标识码：A 文章编号:0253-231X(2017)08-1613-06

# Study on Heat Recovery System of Coal-Fired Power Plant Integrated With $\mathbf { S C O } _ { 2 }$ Power Cycle

LIU Ming ZHANG Xu-Wei WANG Chao-Yang LI Gen YAN Jun-Jie (State KeyLaboratoryof MultiphaseFlowinPower Engineering,Xi'anJiaotong University，Xi'an710049,China)

Abstract The efficient use of energy carried by low temperature flue-gas is a hot topic of energy saving in thermal power plant.The thermodynamic analyses on conventional low temperature economizer with a reference case of l00o MW supercritical power plant were carred out.Results show that the standard coal consumption rate for power generation could be decreased by 2.50 （204号 $\mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ . However a big portion of exergy was destructed in air pre-heater, about 22.03% to the total exergy put into the air pre-heater,which is bigger than the exergy carried by the boiler exhaust. Therefore,a waste heat utilization system integrated with SCO2 power cycle was proposed in this paper,which is designed to decrease the exergy destruction in air pre-heater. Then parameters of SCO2 power cycle were optimized. The standard coal consumption rate for power generation could be decreased by $3 . 6 2 ~ \mathrm { g \cdot ( k W \cdot h ) ^ { - 1 } }$ with optimal parameters.The standard coal consumption rate for power generation could be further decreased by $5 . 5 8 ~ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ when low temperature economizer were also integrated. Finally the essential reason for the energy saving were revealed by exergy analysis. Key wordsthermal power plant; low temperature waste heat; SCO $^ 2$ power cycle; exergy analysis

# 0引言

2015年我国发电量达5.81万亿千瓦时，其中火电占 $7 3 \%$ ，火力发电依然是我国电力生产的主体，同时也是污染物排放的主要来源之一。提高火电厂效率，对我国经济社会的可持续发展具有重要意义。提高火力发电厂效率主要有提高主蒸汽压力温度、蒸汽再热等方法[1，目前新蒸汽参数研究已达到 $7 0 0 ^ { \circ } \mathrm { C } ^ { [ 2 ] }$ ，两级再热机组也已投入运行。火电厂节能已向着全工况节能、动态过程节能[3]、低温烟气余热深度利用的方向发展。

低温烟气余热利用是火电厂节能起步较早的研究方向之一。从上个世纪80年代，我国学者就开始了低温省煤器节能的相关研究工作[4]。经过多年的努力，低温省煤器技术已经非常成熟，已经成为了火电厂节能领域的常规手段之一[5,6]。同时，采用低温省煤器技术降低进入除尘器的烟气温度，已经成为火电厂烟气污染物协同处理的重要环节[7]。然而，由于锅炉排烟能量本身品位较低，低温省煤器技术节能效果有限。

近年来，超临界 $\mathrm { C O _ { 2 } }$ 作为新一代的动力循环工质，在太阳能[8,9]、核能发电[10,11]等领域逐步引起人们的重视。 $\mathrm { S C O _ { 2 } }$ 动力循环采用布雷顿循环结构[12]，由于 $\mathrm { C O _ { 2 } }$ 处于超临界状态，不存在恒温的相变过程，超临界 $\mathrm { C O _ { 2 } }$ 与热源放热曲线匹配性较好，不可逆损失较小。随着 $\mathrm { S C O _ { 2 } }$ 动力循环研究的深入,将其用作火力发电厂工质将成为一个有前景的研究方向。

基于以上讨论，火电厂低温烟气的热能的高效梯级利用是火电厂节能的重要方向之一，目前，主要采用低温省煤器技术回收锅炉排烟余热。同时， $\mathrm { S C O _ { 2 } }$ 动力循环具有很强的应用潜力。为此，本文将 $\mathrm { S C O _ { 2 } }$ 动力循环与火电厂低温烟气热能利用相结合，提出了集成 $\mathrm { S C O _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统。本文首先对某 $1 0 0 0 \mathrm { M W }$ 燃煤发电机组实例集成低温省煤器进行热力学分析，采用烟分析的方法获得 $\mathrm { { S C O } _ { 2 } }$ 动力循环集成节能的本质原因。进而，对集成 $\mathrm { S C O _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统展开理论与参数优化研究。

# 1常规火电厂低温烟气热能利用系统

# 1.1 实例机组

本文以某 $1 0 0 0 ~ \mathrm { M W }$ 超超临界燃煤发电机组为例，对低温烟气余热利用系统进行定量分析。该实例机组燃用煤质参数如表1中所示，该煤种的低位发热量和高位发热量分别为 $1 4 . 5 9 ~ \mathrm { M J } { \cdot } \mathrm { k g } ^ { - 1 }$ 、13.30$\mathrm { M J \cdot k g ^ { - 1 } }$ 。回热系统主要参数如表2中所示。该

Table 1 Parameters of feeding coal of power plant/%   

<html><body><table><tr><td>Mt</td><td>Aar</td><td>Vdaf</td><td>Car</td><td>Har</td><td>Nar</td><td>Oar</td><td>Star</td></tr><tr><td>37.6</td><td>8.9</td><td>45.95</td><td>39.68</td><td>2.04</td><td>0.5</td><td>11.1</td><td>0.18</td></tr></table></body></html>

# 表2回热系统热力参数 $/ \mathbf { k J } { \cdot } \mathbf { k g } ^ { - 1 }$

表1机组燃用煤质参数/ $\%$   
Table 2 Thermodynamic parameters of heat regenerative system $/ \mathbf { k J } { \cdot } \mathbf { k g } ^ { - 1 }$   

<html><body><table><tr><td>加热器编号</td><td>抽汽焓</td><td>疏水焓</td><td>出口水焓</td><td>进口水焓</td></tr><tr><td>1</td><td>3198.8</td><td>1155.1</td><td>1302.8</td><td>1127.8</td></tr><tr><td>2</td><td>3064.9</td><td>953.5</td><td>1127.8</td><td>936.5</td></tr><tr><td>3</td><td>3463.7</td><td>822.3</td><td>936.5</td><td>810.7</td></tr><tr><td>4</td><td>3247.8</td><td>1</td><td>773.3</td><td>653.1</td></tr><tr><td>5</td><td>3095.2</td><td>581.3</td><td>653.1</td><td>557.7</td></tr><tr><td>6</td><td>2953</td><td>477.2</td><td>557.7</td><td>454.1</td></tr><tr><td>7</td><td>2798.9</td><td>379</td><td>454.1</td><td>356.3</td></tr><tr><td>8</td><td>2656.4</td><td>174.4</td><td>356.3</td><td>147.6</td></tr></table></body></html>

机组锅炉效率为 $9 2 . 1 \%$ ，管道效率为 $9 9 . 0 \%$ ，锅炉排烟温度为 $1 4 8 . 0 ^ { \circ } \mathrm { C }$ ，汽轮发电机组热耗率为7354.0$\mathrm { k J \cdot ( k W \cdot h ) ^ { - 1 } }$ 。计算得到该机组发电标准煤耗率为$2 7 5 . 5 7 ~ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 。

# 1.2定量分析

# 1.2.1节能潜力分析

常规低温烟气热能利用系统原理图如图1所示。在系统中，锅炉排烟的热量用于加热回热系统凝结水，从而降低回热系统抽汽量，进而降低燃煤发电系统发电标准煤耗率。本文计算过程中，低温省煤器凝结水取自No.8低压加热器入口，返回No.7加热器出口，而凝结水参数加热至与No.7出口相同。

![](images/908f47e7ca7d6a90f45b364ec874f9a77a9d25f07243cacfc020fca988a05128.jpg)  
图1常规低温省煤器烟气热能利用系统 Fig.1 Fluegas heat utilization system of conventional low temperature economizer

本文采用等效热降法对该 $1 0 0 0 ~ \mathrm { M W }$ 机组耦合低温省煤器的节能潜力进行定量分析。对于如图1所示的并联方式的低温省煤器系统，流量为 $D _ { \mathrm { s } }$ 的凝结水从No.8低加入口引出，在低温省煤器中加热后返回No.6低加入口，根据等效热降的基本法则，相对于单位新蒸汽而言，并联系统新蒸汽等效热降增量为：

$$
\Delta H = \left( { \frac { D _ { \mathrm { s } } } { D _ { 0 } } } \right) [ \tau _ { 7 } \eta _ { r 7 } + \tau _ { 8 } \eta _ { r 8 } ]
$$

式中， $\tau _ { 7 } , \tau _ { 8 }$ 为第7、8级回热加热器凝结水焓升； $D _ { 0 }$   
为新蒸汽量。

低温省煤器系统使机组发电标准煤耗率的降低量为：

$$
\Delta b = - b \cdot \delta \eta _ { \mathrm { i } } = - b \cdot { \frac { \Delta H } { H + \Delta H } }
$$

式中， $H$ 为新蒸汽等效热降， $\mathrm { k J \cdot k g ^ { - 1 } }$ ： $b$ 为机组发电标准煤耗率, $\mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 。

利用以上模型计算得到该机组集成低温省煤器的节能潜力如表3中所示。同时，将能量分析结果采用桑迪图表示，如图2所示。从图中可以得到，通过集成低温省煤器，锅炉排烟中有 $4 1 . 1 0 \%$ 的热量得以回收，使得系统发电标准煤耗率降低 2.50$\mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 。

表3低温省煤器计算结果  
Table 3 Calculation results for low temperature economizer   

<html><body><table><tr><td>项目</td><td>Ds/kg·s-1</td><td>Snc/%</td><td>△b/g:(kW·h)-1 b/g:(kW·h)-1</td><td></td></tr><tr><td>数值</td><td>211.46</td><td>0.9276</td><td>2.50</td><td>273.07</td></tr></table></body></html>

![](images/00570a2919b8f60f7d22bc5ac2c24bb31c2ea0ff9334ccc4c3f6f4d86fda4b23.jpg)  
图2低温省煤器系统能量流桑迪图 Fig.2 Sandy diagram for energy flow of low temperature economizer

# 1.2.2 烟分析

为进一步挖掘锅炉低温烟气段的节能潜力，以下对包括空气预热器在内的锅炉低温烟气热能利用系统进行烟分析。

系统中锅炉烟气、空气的烟可以表示为：

$$
E _ { \mathrm { g a s } } = m _ { \mathrm { g a s } } \cdot C _ { p , \mathrm { g a s } } \cdot \left( T _ { \mathrm { H } } - T _ { 0 } - T _ { 0 } \mathrm { l n } \frac { T _ { \mathrm { H } } } { T _ { 0 } } \right)
$$

式中， $m _ { \mathrm { g a s } }$ 为气体质量; $T _ { \mathrm { H } } , T _ { 0 }$ 分别为气体温度、环境温度， $\mathrm { ~ K ~ }$ 。

锅炉排烟的部分热量被汽轮机凝结水带走，其烟采用下式计算：

$$
e _ { \mathrm { w } } = h _ { \mathrm { w } } - h _ { \mathrm { w 0 } } - T _ { 0 } ( s _ { \mathrm { w } } - s _ { \mathrm { w 0 } } )
$$

式中， $h _ { \mathrm { w } } , h _ { \mathrm { w 0 } }$ 分别为凝结水在计算参数和环境参数下的焓值， $\mathrm { k J } / \mathrm { k g } ; s _ { \mathrm { w } } ,$ $s _ { \mathrm { w 0 } }$ 分别为凝结水在计算参数和环境参数下的熵。

本文烟分析过程中环境压力取 $0 . 1 \mathrm { M P a }$ ，环境温度取 $2 0 ^ { \circ } \mathrm { C }$ 0

利用以上公式，计算得到锅炉低温烟气段烟分析桑迪图，如图3所示。

从图3中可以看出，在集成低温省煤器系统的低温烟气利用系统中，空气预热器存在大量的不可逆损失，烟耗散达到28.94MW，比锅炉排烟中所携带的烟的总量（26.27MW）还要大。这是因为：空预器热空气与锅炉烟气入口温差为 $2 8 . 1 ^ { \circ } \mathrm { C }$ ，而锅炉烟气出口与空气入口温差达 $1 2 8 . 0 ^ { \circ } \mathrm { C }$ ，空气与烟气换热曲线匹配不佳。在低温省煤器中回收的烟为9.51MW，占排烟携带烟的 $3 6 . 2 0 \%$

![](images/125252b79ba4dafd1f90f1034c597be7f0487b44a7f18a38d725ac6581359b52.jpg)  
图3低温省煤器系统烟分析桑迪图Fig.3 Sandy diagram for exergy analysis of low temperatureeconomizer

# 2集成 $\mathrm { S C O _ { 2 } }$ 动力循环的余热回收系统

# 2.1系统提出

基于以上分析发现，在火力发电厂空气预热器中，存在以下关系：

$$
m _ { \mathrm { f } } C _ { p , \mathrm { f } } > m _ { \mathrm { a i r } } C _ { p , \mathrm { f } }
$$

式中， $m _ { \mathrm { f } }$ 、 $m _ { \mathrm { a i r } }$ 分别为烟气、空气流量； $C _ { p , \mathrm { f } }$ 、 $C _ { p , \mathrm { f } }$ 分别为烟气、空气比热容。

![](images/72f960dd9448c9bfc3d0ba8c1d07f51ae1d6283549c4152a2d13af10280acc1c.jpg)  
图4集成 $\mathrm { \ S C O _ { 2 } }$ 循环的燃煤电站余热回收系统 Fig.4 Heat recovery system of coal-fired power plant integrated with $\mathrm { { S C O } _ { 2 } }$ Cycle

因此，锅炉排烟单位温降放热大于锅炉送风单位温升吸热量，空气预热器中热烟气放热曲线与冷空气吸热曲线匹配较差，空气预热器烟气出口侧换热温差大，达到 $1 0 0 ^ { \circ } \mathrm { C }$ 以上，由此造成空气预热器不可逆损失较大。

为此，本文提出仅分流一部分烟气进入空气预热器，使得：

$$
m _ { \mathrm { f } } ^ { \prime } C _ { p , \mathrm { f } } = m _ { \mathrm { a i r } } C _ { p , \mathrm { f } }
$$

环热端换热器冷端温差 $( t _ { \mathrm { F 1 } } - t _ { \mathrm { C 2 } } )$ 不同，其规律如图7(b)所示。

从而降低空气预热器中的烟气-空气换热的不可逆损失。该系统在锅炉尾部采用分隔烟道，将进入空气预热器烟气分流部分烟气作为热源驱动 $\mathrm { S C O _ { 2 } }$ 布雷顿循环。同时，利用布雷顿循环冷端换热器对进入空气预热器前的烟气进行预热，一方面补充分流烟气带来的烟气热量不足，另一方面可以有效降低空气预热器的腐蚀风险。

# 2.2SCO2动力循环参数优化

集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统各状态点示意图如图5所示。对主要系统参数的假定列于表4之中。为了减少空气预热器中的不可逆损失，保持空气预热器两端换热温差相同 (均为 $2 8 . 1 ^ { \circ } \mathrm { C } )$ 。考虑到烟气的酸露点温度，空气在布雷顿循环冷却器中被加热到 $1 0 0 ^ { \circ } \mathrm { C }$ ，此时锅炉排烟温度为 $1 2 8 . 1 ^ { \circ } \mathrm { C }$ 。

![](images/91ceb220dcc876db0ea6136bee34ba6020893ae73f7fa35969e0cada6664b0cd.jpg)  
图5集成 $\mathrm { \ S C O _ { 2 } }$ 循环的燃煤电站余热回收系统状态点示意图 Fig.5 Schematic diagram of state points of heat recovery system of coal-fired power plant integrated with $\mathrm { { S C O } _ { 2 } }$ Cycle

表4 $\mathbf { S C O } _ { 2 }$ 循环基准参数  
Table 4 Reference parameters of $\mathbf { S C O } _ { 2 }$ cycle   

<html><body><table><tr><td>项目</td><td>透平相对 内效率/%</td><td>压缩机相对 内效率/%</td><td>预热空气 温度/C</td><td>tc1/C</td><td>(tFO-tC3) /C</td></tr><tr><td>数值</td><td>85</td><td>80</td><td>100</td><td>40</td><td>20</td></tr></table></body></html>

$\mathrm { S C O _ { 2 } }$ 动力循环性能受压比的影响，计算初压分别为 $8 \mathrm { M P a }$ 、 $1 0 \mathrm { M P a }$ 和 $1 2 \mathrm { M P a }$ 条件下, $\mathrm { { S C O } _ { 2 } }$ 动力循环效率随着压比的变化规律，所得结果如图5所示。从图中可以得到 $\mathrm { S C O _ { 2 } }$ 动力循环存在最佳压比,循环性能同样受循环初压的影响，而最佳初压在 10MPa 附近。

变化 $\mathrm { S C O _ { 2 } }$ 动力循环初压，在最佳压比条件下,得到 $\mathrm { S C O _ { 2 } }$ 动力循环效率随初压的变化规律，所得结果如图7(a)所示。不同初压条件下， $\mathrm { \ S C O _ { 2 } }$ 动力循

![](images/735c996c092d24652ce5f1168ef720761968e23341ad36e28fb462e6546a78ff.jpg)  
图6 $\mathrm { \ S C O _ { 2 } }$ 循环效率随压比的变化规律 Fig.6 The changing role of the $\mathrm { \ S C O _ { 2 } }$ cycle efficiency along with pressure ratio

![](images/ca2b5e38ec6d9bb99a734dd64bc1f72b5cb7cc096dd16c6077986251744b7311.jpg)  
图7初压的影响规律  
Fig.7 The Influence of initial pressure

根据图7中循环效率与换热温差的综合分析结果，选择最佳初压为 $9 . 1 2 5 ~ \mathrm { M P a }$ ，最佳压比为5.8,此时 $\mathrm { S C O _ { 2 } }$ 循环效率为 $1 7 . 3 9 \%$ 。由此得到 $\mathrm { \ S C O _ { 2 } }$ 动力循环各点参数如图8所示。从图8中可以得到，这一优化参数下， $\mathrm { S C O _ { 2 } }$ 动力循环输出的机械功率为13.58 MW.

![](images/6a38c00362238de76056c4933bb1e3670f5cb5f865929678a38e50266e00a175.jpg)  
图8 $\mathrm { \ S C O _ { 2 } }$ 动力循环计算结果 Fig.8 Calculation results of $\mathrm { { S C O } _ { 2 } }$ cycle

# 2.3发电系统能量利用效率分析

# 2.3.1理论分析模型

以下计算耦合 $\mathrm { { S C O } _ { 2 } }$ 动力循环对发电系统效率的影响情况。 $\mathrm { \ S C O _ { 2 } }$ 动力循环产生机械能转化为电能的量为：

$$
\Delta P e = \boldsymbol { W _ { \mathrm { c } } } \cdot \boldsymbol { \eta _ { \mathrm { c m } } } \cdot \boldsymbol { \eta _ { \mathrm { c e } } }
$$

式中， $\eta _ { \mathrm { c m } } , \eta _ { \mathrm { c e } }$ 分别为 $\mathrm { \ S C O _ { 2 } }$ 动力循环机械效率和发电机效率。

进而得到耦合 $\mathrm { S C O _ { 2 } }$ 动力循环后，系统发电效率为：

$$
\eta _ { \mathrm { c p } } ^ { 1 } = \eta _ { \mathrm { c p } } \left( 1 + \frac { \Delta P e } { P e } \right)
$$

式中， $\eta _ { \mathrm { c p } }$ 为原发电系统发电效率。

$\mathrm { { S C O } _ { 2 } }$ 动力循环出口烟气与锅炉排烟汇合后，可以进一步集成低温省煤器，省煤器参数依然选取常规低温省煤器参数。

此时发电效率可以表示为：

$$
\eta _ { \mathrm { c p } } ^ { 2 } = \eta _ { \mathrm { c p } } \left( \frac { 1 } { 1 - \delta \eta _ { \mathrm { i } } } + \frac { \Delta P e } { P e } \right)
$$

式中， $\delta \eta _ { i }$ 为集成低温省煤器引起的汽轮机绝对内效率的相对变化量。

# 2.3.2系统能效对比

$\mathrm { \ S C O _ { 2 } }$ 动力循环机械效率、发电机效率均取$9 9 \%$ 。由此得到各种系统结构发电标准煤耗率，如图9中所示。从图9中可以得到，通过集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环，系统发电标准煤耗率可以降低3.62$\mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ ，比低温省煤器系统的节煤率提高了1.12$\mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 。如果进一步集成低温省煤器系统，发电标准煤耗率降低量可以达到 $5 . 5 8 ~ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 。由此,可知集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统具有很大的节能潜力。

![](images/1d0cfa6d1cc60d5edb427b86b49ce13ecb3c6844f0c90d86d46698b12a953d31.jpg)  
图9不同系统发电标准煤耗率对比

将集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环和低温省煤器系统低温烟气段能量平衡关系用桑迪图表示在图10 之中。在该系统中， $3 3 . 1 0 \%$ 的烟气分流至 $\mathrm { S C O _ { 2 } }$ 动力循环中， $\mathrm { S C O _ { 2 } }$ 动力循环承担了 $6 4 . 5 3 \mathrm { M W }$ 的空气预热负荷（占总空气预热负荷的 $2 6 . 5 0 \%$ )，并产生 $1 3 . 5 8 \mathrm { M W }$ 的机械能用于发电。而后，两股烟气混合，在低温省煤器中将 $5 0 . 3 2 ~ \mathrm { M W }$ 的热能用于加热回热系统凝结水。

![](images/7ec9c2ebccaa04ba1c3aa71c64e974f7689b28e0cdcd834859f531213ee6abc9.jpg)  
Fig.9 Comparison of different systems on standard coal consumption rate to generate electricity   
图10集成 $\mathrm { \ S C O _ { 2 } }$ 动力循环和低温省煤器系统能量流桑迪图 Fig.10 Sandy diagram for energy flow in system integrated with $\mathrm { { S C O } _ { 2 } }$ power cycle and low temperature economizer

# 2.4发电系统焊分析

为进一步解释系统节能的原因，应用烟分析模型对以上系统各流股的烟进行计算，将整个低温烟气热能利用系统的烟分析结果用桑迪图示于图11之中。从图11中可以看到，通过集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环,空气预热器中的烟耗散大幅度下降，由低温省煤器系统中的 $2 8 . 9 4 ~ \mathrm { M W }$ 下降至 $6 . 2 5 ~ \mathrm { M W }$ 。而在 $\mathrm { \ S C O _ { 2 } }$ 动力循环中，由于压缩机、透平、传热过程等处存在的不可逆损失，使得其中产生了 $1 2 . 9 5 ~ \mathrm { M W }$ 的烟耗散。由于空气预热器后烟气温度与 $\mathrm { S C O _ { 2 } }$ 动力循环出口烟气温度有所差别，所以烟气混合过程产生了0.16MW的烟耗散。

由此得到，集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环可以有效的降低空气预热器中的烟耗散，这是系统节能的本质原因。同时，也可以看到， $\mathrm { S C O _ { 2 } }$ 动力循环自身的不可逆性较高，畑耗散达到 $1 2 . 9 5 ~ \mathrm { M W }$ ，如果设法提高压缩机、透平的等熵效率，可以进一步提高整个发电系统的发电效率。

图例： 燃烧器烟流烟耗散 X烟损失热空气：  
锅.炉烟气 空热器 68.66MW 回热系统锅炉烟气12.96MW 烟气 锅炉烟气 低温 74结  
4.烟气 超界1294MWW 混合 22.27MW省煤器 0.1w 锅.炉气力循环 热空气：7.47MW机械功：燃烧器13.58MW

发电标准煤耗率降低量可以达到 $5 . 5 8 ~ \mathrm { g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ ·4)对集成 $\mathrm { S C O _ { 2 } }$ 动力循环和低温省煤器的低温烟气热能利用系统进行了烟分析，结果表明该系统大幅度降低了空气预热器中的烟耗散，这是系统节能的本质原因。

# 参考文献

[1]严俊杰，黄锦涛，张凯,等.发电厂热力系统及设备[M].西 安交通大学出版社，2003 Yan J J, Huan J T, Zhang K, et al. Thermal System and Equipments of Thermal Power Plant [M]. Xi'an Jiaotong Press, 2013   
[2] Bugge J,Kjaer S,Blum R.High-Efficiency Coal-Fired Power Plants Development and Perspectives [J]. Energy. 2006,31(10):1437-1445   
[3] Stoppato A,Mirandola A,Meneghetti G,et al. On the Operation Strategy of Steam Power Plants Working at Variable Load: Technical and Economic Issues [J].Energy. 2012,37(1):228-236   
[4] 徐永康，林万超，李笑乐,等．低压省煤器系统及其节能效 益[J]．电力技术,1984(10):21-24 Xu Y K,Lin W C,Li X L,et al．The Low Pressure Economizer Systeam and Its Benefit of Saving Energy [J]. Elelctric Power Technology,1984(10): 21-24   
[5] Yang Y, Xu C, Xu G, et al. A new Conceptual Cold-End Design of Boilers for Coal-Fired Power Plants with Waste Heat Recovery [J]. Energy Conversion and Management. 2015,89:137-146   
[6]鄢晓忠，符慧林，刘亮,等. $6 7 0 ~ \mathrm { t / h }$ 煤粉锅炉省煤器改造设 计[J]．热力发电,2004(04):40-44 Yan XZ,Fu HL,Liu L,et al. Design for Retrofitting Economizer of a $6 7 0 ~ \mathrm { t / h }$ Pulverized Coal Boiler [J]. Thermal Power Generation. 2004(04):40-44   
[7]桂本，王辉，王为,等．燃煤电站烟气污染物协同治理技术 [J]．中国电业 (技术版),2014(10)：5-9 Gui B,Wang H,Wang W,et al. Cooperative Governance Technology for Flue-Gas Pollutant of Coal-Fired Power Plant [J].Electric Power Industry in China (Technology), 2014(10): 5-9   
[8] Padilla R V,Soo Too Y C,Benito R,et al．Exergetic Analysis of Supercritical CO $^ 2$ Brayton Cycles Integrated with Solar Central Receivers [J].Applied Energy, 2015, 148:348-365   
[9] Iverson B D,Conboy T M,Pasch J J,et al. Supercritical CO2 Brayton Cycles for Solar-Thermal Energy [J]. Applied Energy, 2013,111: 957-970   
10] Dostal V,Driscoll MJ,Hejzlar P.A Supercritical Carbon Dioxide Cycle for Next Generation Nuclear Reactors [R]. Massachusetts Institute of Technology，Dept of Nuclear Engineering,Cambridge,MA,Paper No. MIT-ANP-TR100,2004   
11] Dostal V, Hejzlar P, Driscoll M J. High-performance Supercritical Carbon Dioxide Cycle for Next-Generation Nuclear Reactors [J].Nuclear Technology. 2006,154(3): 265- 282   
12]沈维道，童钧耕．工程热力学[M].高等教育出版社，1965 Shen W D,Tong JG.Engineering Thermodynamics [M]. Higher Education Press,1965

# 3结论

高效地对火电厂低温烟气段的热能进行利用是提高火电厂发电效率的有效途径，然而常规低温省煤器系统节能效果有限。为此，本文提出了集成$\mathrm { S C O _ { 2 } }$ 动力循环的火电厂低温烟气热能利用系统方案，并对这一系统方案展开研究，所得主要结论如下：

1）对常规低温省煤器系统进行了热力学分析，发现其可以降低发电标准煤耗率 $2 . 5 0 \mathrm { \ g } { \cdot } ( \mathrm { k W } { \cdot } \mathrm { h } ) ^ { - 1 }$ 系统烟分析发现，集成低温省煤器系统的火电厂低温烟气段的不可逆损失很大，主要发生在空气预热器之中；

2）对集成于发电系统低温烟气段的 $\mathrm { { S C O } _ { 2 } }$ 动力循环进行了参数优化，得到的优化初压为9.125$\mathrm { M P a }$ ，压比为5.8，循环效率为 $1 7 . 3 9 \%$

3)对不同结构的低温烟气段热能利用系统进行了计算，发现集成 $\mathrm { { S C O } _ { 2 } }$ 动力循环可以降低发电标准煤耗率 $3 . 6 2 ~ \mathrm { g \cdot ( k W \cdot h ) ^ { - 1 } }$ ，若进一步集成低温省煤器,