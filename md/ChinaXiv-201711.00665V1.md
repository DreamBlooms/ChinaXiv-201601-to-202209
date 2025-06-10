# 新型氢氧-燃煤联合循环系统热力学性能分析

徐钢，赵世飞，周璐瑶，董伟，杨勇平

(热电生产过程污染物监测与控制北京市重点实验室，能源动力与机械工程学院，华北电力大学，北京 102206)摘 要：本文在传统燃煤发电机组和氢氧联合循环的基础上，提出一种新型的氢氧-燃煤联合循环系统。该系统把超超临界燃煤机组与氢氧联合循环相耦合，实现了氢能和燃煤的高效利用，丰富了两种燃料的利用形式。本文使用EBSILON对该系统进行了初步模拟，研究结果表明，该系统在蒸汽初压为 $2 5 . 6 \mathrm { M P a }$ ，最高温度为1 $3 0 0 ^ { \circ } \mathrm { C }$ 时，发电效率可达到 $49 . 7 4 \%$ ，并可通过提高循环最高温度和燃气透平膨胀比达到更高的发电效率。

关键词：氢氧联合循环；燃煤机组；热力学性能；关键参数中图分类号： $\mathrm { T K } 1 1 { + } 4$ 文献标识码：A

# Thermodynamic analysis of a novel ${ \sf H } _ { 2 } / 0 _ { 2 }$ -coal fired combined cycle

XU Gang, ZHAO Shi-Fei, ZHOU Lu-Yao, DONG Wei, YANG Yong-ping (BeijingKeyLaboratoryofEmission SurveillanceandControl forThermal PowerGeneration,North China Electric Power University, Beijing 102206, China)

Abstract: Based on the traditional coal fired power plant and $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ combined cycle, this article presents a novel $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ - coal fired combined cycle. Because of a high degree of coupling of ultra-super critical coal fired power plant with $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ combined cycle, the novel cycle provides an efficient approach for using coal and hydrogen，which enriches the forms of fuel utilization. In this paper,the software EBSILON professional is used for system simulation.Research shows that the net energy efficiency of the novel cycle can reach $4 9 . 7 4 \%$ with the parameters of the live steam of $2 5 . 6 \mathrm { M P a } / 1 3 0 0 ^ { \circ } \mathrm { C }$ .As the maximum temperature of the cycle and the pressure ratio of the gas turbine enhance,the greater energy eficiency can be achieved.

Key words: $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ combined cycle; coal fired power plant; thermodynamic analysis; key parameters

# 0引言

“十二五"规划对我国能源行业提出了明确要求。到2020年，非化石能源占一次能源消费的比重要达到 $1 5 \%$ 左右，单位GDP的 $\mathrm { C O } _ { 2 }$ 排放量比2005年下降 $4 0 \% { \sim } 4 5 \% ^ { [ 1 ] }$ 。为了实现我国承诺的2020 年能源结构调整及温室气体排放控制目标，我国电力工业亟须加快转变发展方式，除了优化煤电布局，还需要大力发展清洁能源[2]。

在众多的新能源中，氢为完全不含碳、最清洁的二次能源，同时也具有热值高、来源广泛等特点。从长远看，零污染排放的氢能有着广阔的发展前景[3]。早在上世纪90 年代初，中、日、美等国科技工作者几乎同时提出了利用氢能的氢氧联合循环的设想[4-7]。现在，美国与日本均有科研计划将之付诸实用。氢氧联合循环以氢气作为燃料，透平的背压为蒸汽的冷凝压力，而不是普通的燃气透平排气的大气压，透平出功远远大于普通燃气透平；另外，大部分联合循环在顶循环和底循环之间需要一个余热锅炉来耦合，余热锅炉的排烟温度一般在 $1 5 0 ^ { \circ } \mathrm { C }$ 左右，因而损失了很大一部分能量，但对于氢氧联合循环，就没有这部分损失，因而能达到较高的效率[8-9]。近年来，不少学者也在此方面做了相关研究，其中方钢[4]，M.Gambini[10]，S.P Cicconardi[11]，徐鸿[9,12]等均对氢氧联合循环进行了设计、分析和改进，结果表明氢氧联合循环是一种高效、清洁的发电系统。考虑到氢氧燃烧产物只有水蒸汽，与传统燃煤机组做功工质相同，因此可以考虑通过采取适当的形式，利用现有的设备使氢能在传统的燃煤机组得以利用。

收稿日期：

基金项目：本文由国家自然科学基金重点项目 (No.U1261210)和面上项目(No.51476053)资助作者简介：徐钢（1978-），男，副教授，工学博士，主要从事能源动力系统优化与节能、污染物控制及脱除等研究

有鉴于此，本文提出了一种新型的氢氧-燃煤联合循环，具体细化了系统的一些关键环节，实现了氢能和燃煤的高效利用，丰富了两种燃料的利用形式。

# 1氢氧-燃煤联合循环系统

# 1.1传统超超临界燃煤机组 (参比机组）

本文选取某典型1000MW一次再热超超临界机组作为参比机组，该系统流程简图如图1所示。参比系统的锅炉为超超临界参数变压直流锅炉，汽轮机为 $\mathrm { N } 1 0 0 0 { - } 2 6 . 2 5 / 6 0 0 / 6 0 0$ 型超超临界、一次中间再热凝汽式汽轮机，具有8级非调整回热抽汽。表1给出了参比机组主要的运行参数。

![](images/d7cbfc793a9d6513a78506935a72da5237959aa5e87ee49208c68cffba6cc4b0.jpg)  
图1典型1000MW一次再热超超临界机组热力系统图Figure1 Schematic diagramofa typical1oo0MWultra-supercritical unit

表1参比机组的主要运行参数  
Table1 Main parameters of base case   

<html><body><table><tr><td>参数</td><td>单位</td><td>数值</td></tr><tr><td>最大蒸汽压力</td><td>MPa</td><td>26.25</td></tr><tr><td>再热压力</td><td>MPa</td><td>5.5</td></tr><tr><td>凝汽器压力</td><td>kPa</td><td>5</td></tr><tr><td>过热/再热温度</td><td>℃</td><td>600</td></tr><tr><td>发电效率</td><td>%</td><td>44.78</td></tr></table></body></html>

# 1.2氢氧-燃煤联合循环系统的提出

在传统燃煤机组的基础上，结合氢氧联合循环，本文提出了氢氧-燃煤联合循环系统，其系统流程图如图2所示。主蒸汽离开锅炉后经高压蒸汽透平膨胀做功，排汽经再热预热器加热后进入燃烧室。燃烧室以纯氢作为燃料，以纯氧作为氧化剂，反应生成高温水蒸汽，与高压蒸汽透平排汽混合后进入燃气透平膨胀做功。由于燃气透平的排汽有较高的温度，因此排汽先经再热预热器来预加热再热蒸汽，之后在给水预热器加热锅炉给水，然后才进入低压蒸汽透平。蒸汽在低压燃气透平做功后凝结成水，分离出氢氧燃烧产生的水量后经给水泵升压，给水预热器加热后进入锅炉，从而完成一个循环。

![](images/6959b74bbfdb30cbc675e8154a5803b287cd7ab909cec3691988318fafe47ae5.jpg)  
图2氢氧-燃煤联合循环系统图  
Figure2 Schematic diagram of $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ - coal fired combined cycle

新系统的设计主要在于：（1）取消了燃煤锅炉的再热系统，蒸汽的再热由氢氧燃烧室完成；（2）由于燃气透平内蒸汽温度过高，出于工程安全和换热损失考虑，取消抽汽回热系统；另外，燃气透平排汽温度较高，因此添加再热预热器和给水预热器回收部分热量，此种考虑遵循"温度对口，梯级利用"的原则，可以提高系统热量利用效率。图3为该系统的温熵图。

![](images/17e2d6840481c00673c30bd5e392db4b1a110d8209b75b3a68a4e9b56eaf144e.jpg)  
图3氢氧-燃煤联合循环温-熵图  
Figure3 T-S diagram of $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ - coal fired combined cycle

由图3可以看出，与传统超超临界燃煤机组相比，蒸汽在热温度得到了很大的提高，因而提高了系统的平均吸热温度；同时，燃气透平的高温排汽经7-8加热高压蒸汽透平排汽4-5，经8-9加热锅炉给水1-2，排汽的热量经过回热系统得到了有效的利用。

# 2 热力学性能分析

# 2.1热力学分析模型

氢氧-燃煤联合循环系统的物质平衡关系：

$$
m _ { _ { G T } } = m _ { _ { L P S T } } = m _ { _ { H P S T } } + 9 m _ { _ { H } }
$$

式中： $m _ { _ { G T } } \mathrm { ~ , ~ } m _ { _ { L P S T } } \mathrm { ~ , ~ } m _ { _ { H P S T } }$ 分别为燃气透平、低压蒸汽透平以及高压蒸汽透平的流量， $\mathrm { k g / s }$ ： $m _ { H }$ 为进入燃烧室中氢气流量， $\mathrm { k g / s }$

循环得到的总功：

$$
\begin{array} { c c } { { W _ { ^ { T o r } } = m _ { ^ { H P S T } } \times \left( h _ { ^ 3 } - h _ { ^ 4 } \right) + m _ { ^ { G T } } \times \left[ \left( h _ { ^ 6 } - h _ { ^ 7 } \right) + \left( h _ { ^ 9 } - h _ { ^ { 1 0 } } \right) \right] } } \\ { { } } & { { } } \\ { { = W _ { ^ { H P S T } } + W _ { ^ { G T } } + W _ { ^ { L P S T } } } } & { { ( 2 ) } } \end{array}
$$

式中： $h$ 表示不同点的焓值， $\bf k J / \ k g$ ： $W _ { H P S T }$ ， $W _ { G T } \mathrm { : }$ $W _ { L P S T }$ ，分别为高压蒸汽透平、燃气透平以及低压蒸汽透平所做的功， $\mathrm { k W }$ 。

由于考虑到氢能终端的利用系统效率，因此对氢和氧的压缩功不加考虑，所以系统出功为：

$$
W _ { N E T } = W _ { T O T } \ – \ W _ { F W P }
$$

式中： $W _ { F W P }$ 给水泵消耗的功， $\operatorname { k W }$ 。

进入系统的热量：

$$
\mathcal { Q } = m _ { H P S T } \times \left( h _ { 3 } - h _ { 2 } \right) + m _ { G T } \times \left( h _ { 6 } - h _ { 5 } \right)
$$

$$
= m _ { H P S T } \times ( h _ { 3 } - h _ { 2 } ) + m _ { H } \times Q _ { L H V }
$$

式中： $\varrho _ { L H V }$ 为氢气的低位发热量， $\mathrm { k J / k g }$ 。系统的发电效率：

$$
\eta _ { e } = \frac { W _ { \scriptscriptstyle { N E T } } } { Q } \eta _ { \scriptscriptstyle { g } } \eta _ { m }
$$

式中： $\eta _ { m }$ 为机械效率, $0 \%$ $\eta _ { \mathrm { g } }$ 为发电机效率, $9 \%$ 。循环的最高温度 $T _ { m a x }$ 定义为燃气透平入口温度；燃气透平膨胀比 $\beta$ 为其入口压力与出口压力之比。

# 2.2计算结果分析

本系统沿用参比机组的主汽参数以及高压缸排汽参数，燃气透平排汽压力为 $0 . 1 \mathrm { M P a }$ ，并对系统关键参数进行假定，其主要参数如表2所示。

# 表2循环系统计算的主要参数及假定条件

Table 2 Main parameters and assumption conditions of the

cycle   

<html><body><table><tr><td>参数</td><td>单 位</td><td>数值 参数</td><td>数 值</td></tr><tr><td>高压蒸汽透平进口 温度</td><td>℃</td><td>600 锅炉效率</td><td>94%</td></tr><tr><td>高压蒸汽透平进口</td><td>MPa</td><td>25.6 蒸汽透平效率</td><td>88%</td></tr><tr><td>压力 再热预热器上端差</td><td>℃ 50</td><td>燃气透平效率</td><td>92%</td></tr><tr><td>燃气透平进口温度</td><td>℃</td><td>1300</td><td>机械效率 99%</td></tr><tr><td>燃气透平进口压力</td><td>MPa</td><td>5.5 发电机效率</td><td>99%</td></tr><tr><td>燃气透平膨胀比</td><td></td><td>55</td><td>燃烧室效率 99%</td></tr><tr><td>给水预热器下端差</td><td>℃</td><td>80 失</td><td>燃烧室压力损 3%</td></tr><tr><td>低压蒸汽透平排气 压力</td><td>kPa</td><td>5</td><td>换热器压损 3%</td></tr></table></body></html>

本文使用软件EBSILON对氢氧-燃煤联合发电系统进行了模拟，EBSILON是一款专业的一体化电厂模拟软件，广泛被用于设计、评价以及优化电厂和其他热力系统。软件模拟结果如表3所示。

表3氢氧-燃煤循环系统热力学性能分析  
Table 3 Thermodynamic analysis of the H2/O2-coal fired   

<html><body><table><tr><td colspan="6">combined cycle</td></tr><tr><td>参数</td><td>单位</td><td>氢氧-燃煤联合循</td><td></td><td>参比机组</td><td></td></tr><tr><td></td><td></td><td></td><td>环</td><td></td><td></td></tr><tr><td>输入系统热量</td><td>MW</td><td>2010.3</td><td>100%</td><td>2233.1</td><td>100%</td></tr><tr><td>燃煤Qc</td><td>MW</td><td>861.2</td><td>42.84%</td><td>2233.1</td><td>100%</td></tr><tr><td>氢气QH 透平出功</td><td>MW</td><td>1149.0</td><td>57.16%</td><td>1</td><td>1</td></tr><tr><td>高压蒸汽透平</td><td>MW</td><td>127.1</td><td>6.32%</td><td>318.5</td><td>14.26%</td></tr><tr><td>燃气透平</td><td>MW</td><td>737.3</td><td>36.68%</td><td>385.0</td><td>17.24%</td></tr><tr><td>低压蒸汽透平</td><td>MW</td><td>155.2</td><td>7.72%</td><td>351.2</td><td>15.73%</td></tr><tr><td>凝汽器</td><td>MW</td><td>855.4</td><td>42.55%</td><td>1033.2</td><td>46.27%</td></tr><tr><td>各项损耗</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>换热器</td><td>MW</td><td>3.3</td><td>0.16%</td><td>10.6</td><td>0.48%</td></tr><tr><td>给水泵</td><td>MW</td><td>9.4</td><td>0.47%</td><td>34.4</td><td>1.54%</td></tr><tr><td>机械损失</td><td>MW</td><td>10.3</td><td>0.51%</td><td>10.5</td><td>0.47%</td></tr><tr><td>锅炉(燃烧室)</td><td>MW</td><td>120.6</td><td>6.00%</td><td>134.0</td><td>6.00%</td></tr><tr><td>发电机</td><td>MW</td><td>10.2</td><td>0.51%</td><td>10.4</td><td>0.47%</td></tr><tr><td>发电效率ne</td><td></td><td></td><td>49.74%</td><td></td><td>44.78%</td></tr></table></body></html>

从表3可以看出，在选定的工况下，氢氧-燃煤联合循环系统的发电效率得到了提升。在循环最高

温度为 $1 3 0 0 ^ { \circ } \mathrm { C }$ 时，最高压力为 $2 6 . 2 5 \mathrm { M P a }$ ，系统的发电效率可达到 $4 9 . 7 4 \%$ ，比参比机组提高了 $4 . 9 6 \%$ 。

定义 $\phi$ 为燃气透平出功量与蒸汽透平出功量之比， $\theta$ 为注入系统的热量中氢气与燃煤热量值比。由表3可以看出，循环的出功量以燃气透平为主，燃气透平循环出功量为737.3MW，约占总输出功的$7 2 . 3 2 \%$ ，而蒸汽透平的循环出功量为 $2 8 2 . 3 \mathrm { M W }$ ，约占总输出功量的 $2 7 . 6 8 \%$ ，出功比 $\scriptstyle { \mathcal { P } } = 2 . 6 1$ 。输入系统的热量中，氢气的比例也高于燃煤，占到了$5 7 . 1 6 \%$ ，热量比 $\scriptstyle \theta = 1 . 3 3$ 。

另外，由于使用氢氧燃烧室进行再热，燃煤消耗量降低。与原系统相比，燃煤消耗量降至 $3 8 . 6 \%$ 与之相应的污染物及温室气体的排放也随之降低，大大降低了污染物及温室气体的脱除能耗。

# 3氢氧-燃煤联合循环系统进一步分析

# 3.1关键参数对系统发电效率的影响

从文献[13-14]中可知，以氢为燃料的联合循环系统中，温度、压力和膨胀比及其分配都会系统的效率产生较大影响。在其它参数不变的情况下，本文分别选取燃气透平入口温度 $T _ { m a x }$ 以及燃气透平入口压力为变量，针对不同的参数对系统的作了分析，其中效率的变化如图4所示。

![](images/34653704694e7d53c32e5e1d1696c05a5b3f23e6ed26762633601d94f6ba5b65.jpg)  
图4不同参数下系统的发电效率Figure 4 Power Efficiency in different parameters

由图4可以看出，提高循环膨胀比 $\beta$ 和循环最高温度 $T _ { m a x }$ 均可使循环的发电效率提高，且温度的变化对系统效率影响较为明显。在 $\beta$ 为70， $T _ { m a x }$ 为$1 7 0 0 ^ { \circ } \mathrm { C }$ 时,该系统的发电效率可达 $54 . 1 \%$ 。循环最高温度 $T _ { m a x }$ 的提高受到燃气透平金属材料强度、热障涂层以及冷却技术的制约[15],随着这些技术的突破 $T _ { m a x }$ 会得到逐步提高，该系统的效率也会不断上

升。

# 3.2循环最高温度对出功比和热量比的影响

由于氢氧-燃煤联合循环为采用双燃料和两类透平的系统，因此本文对不同循环最高温度下透平出功比 $\phi$ 和氢气与燃煤热量比 $\theta$ 做了分析。模拟结果如图5所示。

![](images/05bb8ad7b14cd051dfedcfe83f485a15b6167d20dd40d9dd7b79e1a3621bfb10.jpg)  
图 $5 \mathrm { T } _ { m a x }$ 对出功比 $\Phi$ 与热量比0的影响Figure 5 The influence of the $\mathrm { T } _ { \mathrm { m a x } }$ on the $\Phi$ (output work ratio)and 0 (input thermal ratio)

由图5可以看出， $\phi$ 和 $\theta$ 始终大于1，表明系统出功以燃气透平为主，输入系统的热量以氢气为主。随着循环最高温度 $T _ { m a x }$ 的提高， $\phi$ 和 $\beta$ 也逐渐增大。在循环最高温度 $T _ { m a x }$ 为 $1 7 0 0 ^ { \circ } \mathrm { C }$ 时，燃气透平出功量为蒸汽透平出功量的3.5倍，氢气输入热量为燃煤输入热量的2.2倍。因此，改善氢气燃烧环境，优化燃气透平结构会对系统性能有较大提升。

# 4结论

本文在传统超超临界燃煤机组的基础上，结合氢氧联合循环，提出了一种氢氧-燃煤联合发电系统。该系统把传统燃煤电厂与氢氧联合循环相耦合，丰富了氢能和燃煤的利用形式。经模拟分析表明，该系统可以达到较高的效率，极大地减少了污染物及温室气体的排放。通过对膨胀比 $\beta$ 以及循环最高温度 $T _ { m a x }$ 的优化，系统的效率还能得到进一步的提高。（1）氢氧-燃煤联合循环系统与传统超超临界机组相比，循环的发电效率得到了提高。在循环最高温度为 $1 3 0 0 ^ { \circ } \mathrm { C }$ ，燃气轮机膨胀比为55时，循环发电效率可达到 $4 9 . 7 4 \%$ ，比参比机组提高了 $4 . 9 6 \%$ 。（2）新系统中，循环最高温度以及燃气轮机膨胀比对系统效率影响较大，提高循环最高温度和膨胀比都可使系统的效率得到提高。在膨胀比为70，系统最高温度为 $1 7 0 0 ^ { \circ } \mathrm { C }$ 时，循环发电效率可达到$54 . 1 \%$ 。（3）新系统出功以燃气透平为主，输入系统的热量以氢气为主。随着循环最高温度 $T _ { m a x }$ 的提高，出功比 $\phi$ 和热量比 $\beta$ 也逐渐增大。在循环最高温度 $T _ { m a x }$ 为 $1 7 0 0 ^ { \circ } \mathrm { C }$ 时，燃气透平出功量为蒸汽透平出功量的3.5倍，氢气输入热量为燃煤输入热量的2.2倍。

# 参考文献

[1] 韩文科,李际“十二五"时期能源发展问题研究[J].宏观 经济研究,2010,(3):3-17 HAN Wenke,LI Ji. Energy Development Research "Twelfth Five-Year" Period [J]. Macroeconomic study, 2010, (3):3-17   
[2] GAO Dan，JIANG Dongfang，LIU Pei，et al．An Integrated Energy Storage System Based on Hydrogen Storage: Process Configuration and Case Studies with Wind Power[J].Energy,2014   
[3]欧训民.氢能制取和储存技术研究发展综述[J].能源研 究与信息,2009,(1):1 $- 4 { + } 1 6$ （204号 OU Xunmin. A Review on the Researchand Development of Hydrogen Production and Storage Technologies[J].Energyand Information, 2009, (1):1 $- 4 { + } 1 6$ （204号   
[4]方钢,蔡睿贤.氢氧联合循环_设计点及变工况初步分析 [J].工程热物理学报,1991,(3):238-241. FANG Gang，CAI Ruixian. Preliminary Analysis of Designand Off-Design Performancesof H2/O2 Combined Cycle [J].Journal of Engineering Thermophysics,1991,(3):238-241   
[5]Gaudernack B,Lynum S.Hydrogen From Natural Gas Without Release of CO2 to the Atmosphere [J].International Journal of Hydrogen Energy, 1998, 23(12):1087-1093   
[6] Yamada N,Mohamad M N A. Efficiency of Hydrogen Internal Combustion Engine Combined with Open Steam Rankine Cycle Recovering Water and Waste Heat [J].International Journal of Hydrogen Energy,2010,35(3): 1430-1442   
[7] Chiesa P, Lozza G, Mazzocchi L. Using Hydrogen as Gas Turbine Fuel [J].Journal of Engineering for Gas Turbines and Power, 2005,127(1):73-80 [8]马文通.燃气轮机及燃气—蒸汽联合循环在部分工况下 的仿真研究[D].上海交通大学,2009 MA Wentong. Simulating Research on Gas Turbine and Its Combined Cycle in Part Load [D].Shanghai Jiao Tong University, 2009. [9]徐鸿,荆汝林,高丹等.三种类型氢-氧联合循环系统热力 性能的比较 [J].动力工程学报,2010,(2):156-160 XU hong, JING Rulin, GAO Dan, et al. Comparison of Thermal Performance Among Three Hydrogen/ Oxygen Combined-Cycle Systems [J]. Journal of Chinese Society of Power Engineering,2010,(2):156-160 [10]Gambini M,Guizzi GL，Vellini M. $\mathrm { H } _ { 2 } / \mathrm { O } _ { 2 }$ Cycles: Thermodynamic Potentialities and Limits [J].Journal of Engineering for GasTurbinesand Power, 2005,   
127(3):553-563 [11] Cicconardi S P, Pera A， Spazzafumo GSteam Power-plantsFedByHigh Pressure Electrolytic Hydrogen [J].International Journal of Hydrogen Energy,   
2003,29(5):547-551 [12] 徐鸿,荆汝林,倪维斗等.氢-氧联合循环效率的主要影响 因素分析 [J].动力工程,2009,(7):79-83+98 XU Hong, JING Rulin, NI Weidou, et al. Main Affecting Factors of Hydrogen and Oxygen Hybrid Cycle Efficiency [J]，Journal of Power Enginering，2009, (7) $7 9 - 8 3 + 9 8 $ [13] ZHANG Xiaosong,LI Sheng,HONG Hui,et al． A HydrogenandOxygenCombinedCyclewith Chemical-looping Combustion [J]. Energy Conversion and Management,2014 [14]王逊,张世铮,蔡睿贤.改进型氢氧联合循环及其性能初 步分析[J].工程热物理学报,1997,(5):525-528 WANGXun, ZHANGShizheng, CAI Ruixian. Thermodynamic Analysis of an Alternative Hydrogen and Oxygen Combined Cycle [J],Journal of Engineering Thermophysics.1997,(5):525-528 [15]赵士杭.燃气轮机的新进展[J].燃气轮机技术,1998,(1): $1 - 1 4 + 2 9$ （204 ZHAO Shihang. New Progress in Gas Turbine [J].Gas Turbine Technology, 1998,(1):1-14+29