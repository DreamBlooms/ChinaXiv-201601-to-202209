# 电动汽车直流充电桩散热系统优化分析

侯春光　唐　帅　高有华　韩　颖　曹云东（沈阳工业大学电器新技术与应用研究所沈阳110870）

![](images/cf4053e09aede179339a04a46b0d43dcb4e4eabf657294d2c37591505d9ff3d4.jpg)

侯春光男 1978年生，博士，副教授，研究方向为智能电器。

摘要：为解决充电桩在输出功率增加、内部结构复杂和室外工作环境恶劣等新需求条件下散热难的问题，对充电桩进行热特性分析具有一定的必要性。本文以150kW直流充电桩为研究对象，建立其热特性模型。利用有限体积法对强迫风冷充电桩内的流场和温度场进行热仿真分析，并且对系统通风冷却方案进行优化，对比分析了实际通风和改进通风方案下充电桩的散热效果，进一步对桩体风扇风量和输出功率等因素对充电桩温度场的影响进行研究。结果表明：改进通风优化方案更有利于减少风阻，加快系统散热，为直流充电桩产品开发提供理论指导。

关键词：充电桩有限体积法 流场温度场 热仿真中图分类号：TM501

# Optimization Analysis of Heat Dissipation System for DC Charging Pile of Electric Vehicle

![](images/c18cad3af0425027a212f4b5935ea893c8886ff675eb03951c3adb08bcdbdaad.jpg)

唐帅男1989年生，硕士研究生，研究方向为电机与电器、电场温度场仿真分析。

Hou Chunguang Tang Shuai Gao Youhua Han ying Cao Yundong (Institute of Electrical Apparatus New Technology and Application Shenyang University of TechnologyShenyang11o870China ）

Abstract: In order to solve the problem of difficult steadying heat dissipation new demand for charging pile,which is caused by the increasing output power, complex internal structure and poor outdoor working environment, thermal analysis is highly necessary. This paper takes $1 5 0 \mathrm { k W }$ DC charging pile for research object, the thermal characteristic model of DC charging pile is established. The flow field and temperature field in the forced air cooled charging pile are simulated by finite volume method.At the same time,the ventilation and cooling scheme is optimized. The heat dissipation effect of charging pile under actual ventilation and improved ventilation scheme is compared and analyzed.The improved ventilation scheme is more favorable to the system heat dissipation by simulation analysis.Further more,the influence of the fan volume and the output power on the temperature field of the charging pile is studied. The results show that the improved ventilation optimization scheme is more conducive to reducing windage resistance and accelerating system heat dissipation,and provides theoretical guidance for the development of DC charging pile.

Keywords: Charging pile, finite volume method, flow field, temperature field, thermal simulation

# 1 引言

由于当前生态环境逐渐恶化，全球各国都意识到环境保护的重要性，我国正推进电动汽车应用步伐，从而推动了设计与开发电动汽车充电桩的工作。到2015年年底，国内已经投入运营的电动汽车充电站近800座，内部设有充电桩为3.5万个，可以向14万辆电动汽车提供不间断充电任务[1]。直流充电桩特点是：功率足够大、输出电压电流范围广及短时间快充。由于当前对快速充电的需求，直流充电桩在实际运行时，功率模块中整流模块内部产生大量热损耗，使整个桩体热量越聚越多，加上桩体空间有限，对充电桩的散热有更大难度，为了保障充电可靠和设备的长期正常使用，须在直流充电桩设计过程中对其进行散热分析。统计数据显示，正常温升条件下，电子元器件失效率随元器件温度的升高呈指数增加；据估计，元器件环境温度每升高$1 0 \mathrm { { ^ \circ C } }$ ，其可靠性会减半[2-6]，元器件的失效进而影响整个充电桩的可靠充电。故高效的散热设计是充电桩设备结构设计的重要内容，也是确保设备稳定运行的重要因素之一。

随着电子设备向着小型化、轻量化、多功能化、高功率密度以及高可靠性方向的发展，许多情况下不仅要考虑解决设备的散热问题，还要尽量提高散热的效率、降低成本和提高可靠性，因此热设计中的优化问题也越来越受到重视。热设计优化问题的难点一方面在于流动和换热方程求解，另一方面在于优化目标与参变量之间难以找到一个显式的目标函数[7-10]。目前热设计优化问题的研究主要集中在两个方面：散热器优化设计和元器件布局优化。

当前计算流体动力学（CFD）已经成为热仿真分析问题的重要手段[11-13]，进行CFD仿真数值分析可以提前对仿真模型中任意位置的速度分布、温度分布和压力分布有直观认识。所以在产品的前期设计构思阶段，通过CFD仿真分析能够对其准确快速地多方案对比，节约产品研发时间和样机试验成本。本文根据充电桩散热、工作特性要求，针对实际 $1 5 0 \mathrm { k W }$ 电动汽车直流充电桩产品，对其进行结构和参数设计，建立仿真模型，对电动汽车充电桩在强迫空气对流冷却下的流场和温度场进行了数值仿真，分析了桩体风扇风量和输出功率对充电桩散热效果的影响。

# 2 结构与参数

# 2.1充电桩结构

$1 5 0 \mathrm { k W }$ 直流充电桩由功率模块、直流母线、交直流绝缘检测系统、辅助电源、进线开关和外壳等组成，利用建模软件对充电桩建立三维模型，充电桩的外形尺寸为 $1 8 8 0 \mathrm { m m } \times 7 8 6 \mathrm { m m } \times 6 9 5 \mathrm { m m }$ ，结构如图1所示。

![](images/f94370c0086ed5be39e3713d67200eac6ce0ec6c551e23b4e15512e0fa1e5363.jpg)  
图1直流充电桩结构示意图  
Fig.1 Structure of DC charging pile

# 2.2通风系统分析

本直流充电桩采用了EVR700-15000型功率模块，模块本身自带有4个从模块前侧向后侧鼓风风扇，所以充电桩采用了桩体后侧加装抽风风扇的强迫空气冷却，在众多的散热方式中，强迫对流风冷的散热能力远优于自然对流风冷，相对于水冷和油冷更简单，易实现，可靠性较高，是常用户外机柜装置的主要散热方式[14-15]。设备运行时，在充电桩后侧抽风风扇的作用下，外界冷空气经由功率模块的散热器翅片通道，与安装在散热器底板上的功率器件发生对流换热后，热空气进入充电桩后侧，由后侧的抽风风扇排出。

# 2.3充电桩散热量和通风量的确定

依据直流充电桩的工作环境温度条件和功率模块本身的工作特性[16]，对充电桩工作温度范围规定如下：功率模块工作温度范围 $- 2 5 \sim 7 5 \mathrm { ^ c }$ ；桩体稳定工作温度范围 $- 2 5 \sim 6 0 \mathrm { ^ { \circ } C }$ 。

充电桩工作时，需要桩体后门风扇提供充足的抽风风量，将流过功率模块内散热片排出的热量得到有效排出，确保元器件温升在有效范围内，功率模块中吸收电容、变压器和支撑电容等安装在模块内，只要空间距离足够，并确保充分空气对流，即可满足散热要求。每个功率模块实际满载工作输出电流20A，输出电压 $7 0 0 \mathrm { V }$ ，其工作效率为$9 5 \%$ ，损耗的发热量为 $7 3 6 . 8 \mathrm { W }$ 。故功率模块的散热设计主要考虑安装在散热器基板上的24只开关器件IGBT，设每个功率模块损耗平均分配到24只IGBT，经计算器件功率损耗为30.7W/只。该充电桩安装10个功率模块，总损耗为 $7 \ 3 6 8 \mathrm { W }$ ，再考虑其他线路热损耗，整个充电桩热损耗约为 $7 5 0 0 \mathrm { W }$ 。

强迫空气对流冷却散热时，设备的大部分热量通过对流换热由空气带出充电桩，设备计算时忽略辐射换热散发的热量。风量、总耗散热量及空气温升之间的关系为[17]

$$
q _ { \mathrm { m } } = \frac { \textit { Q } } { \Delta t C _ { \mathrm { p } } }
$$

式中， $\scriptstyle q _ { \mathrm { m } }$ 为空气的质量流量（ $\mathrm { | k g / s \rangle }$ ； $\boldsymbol { \mathcal { Q } }$ 为总发热量(W); $C _ { \mathfrak { p } }$ 为空气的定压比热容！ $\left( \mathrm { J / ( k g \cdot K ) } \right)$ ，常温下取 $C _ { \mathrm { p } } = 1 \ 0 0 5 \mathrm { J / ( k g \cdot K ) }$ ： $\Delta t$ 为风扇出、进风口的空气温差（℃）。

另外，空气的体积流量与其质量、流量的关系为

$$
q _ { \mathrm { v } } = 6 0 q _ { \mathrm { m } } \gamma ^ { - 1 }
$$

式中， $q _ { \mathrm { v } }$ 为空气的体积流量（ $\mathrm { { . m ^ { 3 } / m i n } }$ ）； $\gamma$ 为空气密度 $( \mathrm { k g / m } ^ { 3 } )$ )，常温常压下取 $\gamma = 1 . 2 3 \mathrm { { k g / m } } ^ { 3 }$ 。

本文设定进风口空气的环境温度为 $4 0 \ \mathrm { { ^ \circ C } }$ ，出风口空气温度低于元器件最高工作温度，设为 $6 0 ^ { \circ } \mathrm { C }$ 左右，则 $\Delta t = 2 0 ^ { \circ } \mathrm { C }$ 。通过以上两个公式计算出散热所需要的风量约为 $1 8 . 2 \mathrm { m } ^ { 3 } / \mathrm { m i n }$ 。由于系统中存在风阻，风扇的最大风量一般为所需风量的2～4倍，取总风量 $7 0 . 3 8 \mathrm { { m } ^ { 3 } / \mathrm { { m i n } } }$ ，根据整体结构布局选取12个风扇。因此，充电桩后门可统一选用最大风量为$5 . 8 6 5 \mathrm { m } ^ { 3 } / \mathrm { m i n }$ 的风扇，型号为CR.12038H24。

# 3 充电桩的CFD仿真分析模型

功率模块由前后进出风口、上下镀铝锌板和内部散热器等组成，10个功率模块从下到上的顺序依次排列，第8个模块和第9个功率模块中间安装直流母线、交直流检测部分和辅助电源，功率模块底部安装交流接触器和进线开关等。有限体积模型如图2所示。有效地简化了三维模型，将换热和气流

变化不大的部件省略。充电桩实际通风采用桩体后侧和顶部装风扇抽风，外界空气由桩体两个进风口和顶底部进风孔进入模块，再经过模块内风道由后侧出口排出热量的通风路径。

![](images/1daddfb09fdf9eca337dde1139d5da06b943b90a5d67a69f9a399617f3f94e6c.jpg)  
图2充电桩模型

模型的计算域限定在充电桩内，充电桩的柜面和功率模块外壳导热系数为 $1 5 \mathrm { W / ( m \cdot K ) }$ ，功率模块的热损耗设定在功率模块中是均匀布局的，空气入口的环境温度为 $4 0 \mathrm { { ^ \circ C } }$ ，通风风扇给系统强迫对流散热的风量，风扇最高转速下的风扇特性曲线设置为桩体风扇的边界条件，系统风扇特性曲线如图3所示。由计算通风风量和系统的压力损失确定桩体风扇的最大静压为 $2 4 0 \mathrm { { P a } }$ ，采用柜后8个风扇并联抽风和柜顶4个风扇抽风冷却。每个功率模块内部自带4个风扇，由模块内风扇型号PVA080G12R-R14的风扇特性曲线直接读取对应风扇最大静压为$1 1 6 . 6 \mathrm { P a }$ ，最大风量为 $2 . 0 4 6 \mathrm { { m } ^ { 3 } / \mathrm { { m i n } } }$ 。

![](images/4402fc02af3469b33f230eb86260d1f5ddc354a7e601a9db04abdfe8fe363800.jpg)  
Fig.2Model of charging pile   
图3充电桩系统风扇特性曲线  
Fig.3Fan property curve of charging pile system

充电桩系统模型采用六面体非结构化网格进行剖分，在局部风扇、进风口和散热片处分别进行建立Assembly剖分较细网格，剖分网格数达到6 263 073个。

# 4结果分析及方案优化

# 4.1实际通风结果分析

计算仿真得到充电桩的温度场分布和流场分布，由图4看出，功率模块热源最高温度为 $7 8 . 8 \mathrm { { \dot { C } } }$ ，在顶部第3个模块，因为模块入风口处有接线盒，阻挡进风冷气流风量。各模块的整体温度分布沿着空气流动方向逐渐增加，模块内部前后最大温差比较大，根本原因是模块内风道沿程较长，位于热气流下游的热源源自原来冷却空气已被上游热气流加热。从流场分布图看出，充电桩柜后入风口存在风道短路问题，使风扇有效散热风量降低；柜顶部风扇位置流体轨迹线相对比较少，这些因素都影响了系统散热。

![](images/bbe731efec64fa9a0978bffe925259ce876fd66536b52784ca660565ac87dcf6.jpg)  
图4实际通风下充电桩的温度场分布和流场分布 Fig.4The temperature field and flow field distribution of charging pile under the actual ventilation

# 4.2通风方式的改进

充电桩由10个功率模块构成，充电桩的充电可靠性和工作寿命主要由散热情况最坏的单个功率模块决定，这就必须使充电桩的整体温度场分布的一致性达到好的效果。为改善温度场分布的情况，应使散热空气流动路径尽可能短，保证每个功率模块气流温度和散热通风量的一致性。依据充电柱现有布局形式的基础，对原来功率模块放置方案和通风系统方案进行改进，将顶部两个功率模块和直流母线部分调换位置，将桩体风扇全部设置在柜后用作抽风风扇，去掉桩后下侧进风口和桩体顶底部四周进风孔，增大前进风口面积，前侧增加上进风口，形成从前面向后面通风的并行排风路径。并行通风方式下充电桩的温度场和流场分布如图5所示，因为每个功率模块在前后通风路径上的进风口和出风口基本对称，进风口提供了足够的冷空气通风量，使热源得到更多的散热，模块热源的最高温度为 $7 1 . 4 \mathrm { { \dot { C } } }$ ，极大降低了系统温度，流场和温度场分布也更加一致，每个功率模块最大温度差得到降低，功率模块内部热源的温度场分布有很好的一致性。从流场分布图看出，整个系统气流更加通畅，气流出风口速度远高于实际通风系统，改进了实际通风方案的通风短路和风扇风量浪费问题。

![](images/e45168f3776b5e4d2b6aa364054c035584e4e7320fd04c2816a05d89f4f8b3bf.jpg)  
图5改进通风下充电桩的温度场分布和流场分布 Fig.5The distribution of temperature field and flow field of charging pile under ventilation condition are improved

# 4.3充电桩温度场的影响因素

# 4.3.1桩体风扇风量

由图6中曲线分布可以得到，随着桩体风扇的通风量逐渐增加，充电桩内热源的最高温度将会降低，所达到的散热效果也会越来越好；由于风量越大风速越高，风扇本身需要克服的压力越大，风扇将会承受更大的阻力而且没有更大的散热效果，并且风量越大对风扇本身性能有更高要求，所以合理选择风扇风量工作值很有必要。

![](images/60dcc7b74b9dc2d694800cb948d8c6445ac168a2a1c1e3d64775ff484f699619.jpg)  
图6风量对温度值的影响  
Fig.6Effect of blowing rate on temperature

# 4.3.2 输出功率

充电桩最高温度点在 $50 \%$ 、 $7 5 \%$ 和 $100 \%$ 输出功率时充电桩的温度场仿真计算结果见下表。环境温度为 $4 0 \ \mathrm { { ^ circ C } }$ ，在 $50 \%$ 输出功率时充电桩具有更好的散热效果，功率模块的最高温度高出环境温度的温升低于 $2 2 ^ { \circ } \mathrm { C }$ ，更加利于元器件长期工作。而在较高输出功率时因为充电桩输出电流和输出电压较大，导致整个充电桩热损耗迅速增加，在 $100 \%$ 输出功率工况时充电桩的最高温度达到 $7 1 . 4 \mathrm { { \dot { C } } }$ ，在长时间的高输出功率时模块的散热效果相对较差。

# 表不同输出功率下充电桩内温度场分布

Tab.Distribution of temperature field in charging pile under different output power   

<html><body><table><tr><td>输出功率(%)</td><td>100</td><td>75</td><td>50</td></tr><tr><td>最高温度/℃</td><td>71.4</td><td>66.1</td><td>61.5</td></tr></table></body></html>

# 5 结论

本文借助绘图软件建立了充电桩的三维物理模型，采用有限体积软件对其进行了温度场和流场仿真计算，得到以下几点结论：

(1）通过计算求出特定散热功率下充电桩需要的通风量，进一步确定了充电桩采用的风扇型号。(2）利用基于计算流体动力学的数值仿真方法计算出了充电桩的温度场和流场分布，然后对通风散热方案进行改进，提出重新布局模块位置和柜后抽风的方案，明显降低了充电桩内的温度。(3）通过分析桩体风扇风量和不同输出功率对充电桩温度场的散热影响，可以有效指导直流充电桩的散热设计。

# 参考文献

[1] 卫建荣，袁庆民．电动汽车直流充电桩控制系统 设计[J]．电子世界，2016，12(3)：25. Wei Jianrong, Yuan Qingmin. Design of DC charging pile control system for electric vehicle[J].Electronic World,2016,12(3): 25.   
[2] Erik C W de Jong,Ferreira JA,Pavol Bauer. Design hniques for thermal management in switch mode nverters[J].IEEE Transactions on Industry Plications,2006,42(6): 1375-1386.   
[3] 徐殿国，李向荣．极限温度下的电力电子技术[J]. 电工技术学报，2006，21(3)：15-23. Xu Dianguo, Li Xiangrong.Power electronics in extreme temperature applications[J]. Transactions of China Electrotechnical Society,2006,21(3):15-2.   
[4] Anandan S S, Ramalingam V. Thermal management of electronics: a review of literature[J]. Thermal Science,2008,12(2): 5-26.   
[5] Won Tae Kim, et al. Effect of heat transfer on air jet impingement of electronicscomponents[C]. Proceeding International Electronic Packaging Conference,1993: 58-68.   
[6] 王萌，徐晓婷．高密度密封电子设备热设计与结 构优化[J]．电子工艺技术，2006(6)：339-343. Wang Meng,Xu Xiaoting. Thermal design and structural optimization of high density sealed electronic equipment[J]. Electronic Process Technology, 2006(6): 339-343.   
[7] 郭晓丹，刘小琛，邹琪，等．电动汽车交流充电 桩检定系统[J]．电气应用，2016，35(24)：76-79.   
[8] Copeland.Optimization of parallel plate heat sinks for forced convection[C]. Annual IEEE Semiconductor Thermal Measurement and Management Symp-Osium,2000: 266-272.   
[9] Khan W A,Culham JR,Yovanovich M M. Optimization of pin-fin heat sinks using entropy generation minimization[J]. IEEE Transactions on Components and Packaging Technologies, 2005, 28(2): 247-254.   
[10]于慈远，于湘珍，杨为民．电子设备热分析／热 设计／热测试技术初步研究[J]．微电子学，2000, 30(5): 334-337. Yu Ciyuan, Yu Xiangzhen, Yang Weimin. Preliminary research on thermal analysis /thermal design/ thermal test technology for electronic equipment[J]. Microelectronics, 2000,30(5): 334-337.   
[11]Anandakrishnan M,Balaj C.CFD simulations of thermal and flow fieldsInside a desktop personal computer with multi-core processors[J]. Engineering Applications of Computational Fluid Mechanics, 2009,3(2): 277-288.   
[12]Yu C W, Webb R L. Thermal design of a desktop system using CFD analysis[C]. Seventeenth IEEE Semi-Therm Symposium,2001: 18-26. [13] Zhao Z.Thermal design of a broadband communication system with detailed modeling of TBGA packages[J].Microelectronics Reliability,2003,43(5):   
785-793. [14] 杨旭，马静，张新武．电力电子装置强制风冷散 热方式的研究[J]．电力电子技术，2000，34(4)：   
36-38. Yang Xu,Ma Jing,Zhang Xinwu,et al.Research on heatsinking mode of the power electronic equipment with forced cooling[J].Power Electronics,2000,   
34(4): 36-38.   
[15] 邱成悌，赵惇殳，蒋全兴．电子设备的结构设计 原理[M]．南京：东南大学出版社，2001.   
[16] QGDW1591—2014．国家电网电动汽车非车载充 电机检验技术规范[S]．2014：5-6.   
[17] 何文志，丘东元，肖文勋．高频大功率开关电源 结构的热设计[J]．电工技术学报，2013，28(2): 188-189. He Wenzhi,Qiu Dongyuan,Xiao Wenxun.Thermal design of high frequency high power switchedmode power supply[J].Transactions of China Electrotechnical Society,2013,28(2): 188-189.