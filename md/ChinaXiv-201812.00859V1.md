# 基于MOPSO的电力变换器多目标优化

郑沛琪　王久和}　陈启丽」　马　亮²（1.北京信息科技大学自动化学院 北京 1001922.北京京仪敬业电工科技有限公司北京100069）

![](images/1e8225ed4104a0d0278c84b070b24f00279b3adf745f5e4b233aaa06bed4f9b8.jpg)

郑沛琪 女 1994年生，硕士研究生，研究方向为电力电子装置多目标优化。

摘要：为克服电力变换器优化设计中各种目标的相互冲突，以效率、物理尺寸（体积、质量和面积）和成本为优化目标建立电力变换器多目标优化模型，采用多目标粒子群优化（MOPSO）算法对建立的模型进行求解，决策者可在最终提供的最优解集中找到不同折衷的最优解。本文以Vienna 整流器和Buck 变换器作为研究对象，分别建立各自的多目标优化函数，导入器件数据库，在Matlab上实现了MOPSO 算法。仿真实验结果表明了MOPSO 算法的可行性、覆盖性和收敛性，并能在比较短的时间里收敛到最优解集。

关键词：电力变换器 MOPSO 算法多目标优化 中图分类号：TM46

# Multi-Objective Optimization of Power Converter Based on MOPSO

Zheng PeiqiWang JiuhelChen QiliMa Liang² (1.Beijing Information Science & Technology University Beijing 100192 China

![](images/1256f76c46ebf6623b03f4314b59608606279e139ba19ea361c5e179fb5e33c6.jpg)

王久和男 1959年生，教授，博士生导师，主要从事电能变换器非线性控制、电能质量控制及微电网等方面的研究。

2.Beijing Jingyi Jingye Electrical Technology Co.,Ltd.Beijing10o069China ）

Abstract: In order to overcome the conflicts among various objectives in the optimization design of power converters,a multi-objective optimization model of power converters with efficiency, physical size (volume,weight and area) and cost is established as optimization objectives in the paper. The model is solved by using multi-objective particle swarm optimization (MOPSO) algorithm and decision makers can find different compromise optimal solutions in the final set of optimal solutions provided. Vienna rectifier and Buck converter are taken as research objects. Their respective multi-objective optimization functions are established,and introduced into the device database,and the MOPSO algorithm is implemented on Matlab. Simulation results show that the MOPSO algorithm is feasible,coverage and convergence,and it can converge to the optimal solution set in a relatively short time.

Keywords: Power converter, MOPSO algorithm, multi-objective optimization

收稿日期：2018-07-26

# 1 引言

全球能源短缺的现状使人们的环保意识日渐提高，对可再生能源的需求日益增大，混合动力汽车（HybridElectricVehicle，HEV）和纯电动汽车(BatteryElectricalVehicle，BEV）、智能电网、并网型光伏（Photovoltaic，PV）以及其他可再生能源系统得到快速发展[1-3]。电力变换器作为上述系统中能量转换的重要部分也面临着更多的挑战。从最先进应用的发展趋势来看，可以预期市场对具有更高效率、可靠性以及更少成本、尺寸和开发时间的增强型电力电子变换器系统的需求将大大增加。

电力变换器的优化设计通常涉及了各种相互冲突的目标，是一个复杂而富有挑战性的问题。多目标设计现存的挑战主要是效率、物理尺寸、成本和可靠性这四个性能指标之间的相互耦合－权衡，如图1所示，而只有多目标优化才能保证设计空间的充分利用。电力电子变换器的多目标优化将从一个系统的效率、体积、成本等多个性能指标的角度出发，采用新颖的优化技术，从而使得系统的性能综合最优[4]，如图2所示。

![](images/9b384d16d14c2c271b1a826ccc39dcf0f9ddf3e893e00678bacdd8263ad61a9c.jpg)  
图1多目标设计挑战

![](images/aeaab8fad27f0f92cfb2501fd9836bacb1fcf4d30a240eed866a59aedbfb479b.jpg)  
Fig.1Multi-objective design challenge   
图2电力电子变换器性能趋势  
Fig.2Performance trend of power electronic converter

多年来，人们为了求解多目标优化问题的有效解（Pareto 最优解)，提出了许多种经典的解决方法，这些方法一般是将各种目标函数进行标量化并进行重复的单目标优化，如序列无约束极小化技术、增广拉格朗日法、牛顿－拉夫森法、连续二次规划算法、最陡下降算法、动态整数规划和随机牛顿优化等方法[5。相反，随后出现的智能多目标优化能够提供多种Pareto最优解的全部范围，能够在单次模拟运行中提供Pareto 最优前沿的形状，很快取得了许多在电力变换器优化设计上的成功应用。文献[6]考虑了用遗传搜索算法求解多目标优化问题，将算法思想应用到多目标优化问题中，开创了智能算法在多目标优化应用领域中的研究。文献[7]利用遗传算法实现双向DC-DC变换器的效率优化，但存在局部搜索能力较差、后期搜索效率较低和易早熟收敛的问题。文献[8]采用一种新颖的遗传算法 NSGA-II （Non-Dominated Sorting in GeneticAlgorithms-II)，以功率MOSFET、输出电感和输出电容为离散变量，解决了同步降压变换器效率、面积和成本的多目标优化问题。既要使优良个体得以保留，又要维持群体的多样性，这是遗传算法中较难解决的问题。文献[9]将粒子群算法应用于电力电子领域，与遗传算法[相比，粒子群优化(Partide SwarmOptimization，PSO）算法最大的优势在于简单易实现、收敛速度快，而且具备记忆功能，对于种群大小的依赖性较弱，近些年已经被广泛用于电力变换器优化设计中[1]。文献[12]采用粒子群算法，实现DC-DC变换器的多输入多输出(Multiple-InputMultiple-Output，MIMO）控制器效率和功率密度之间的优化，仿真结果很好地验证了其性能优越性。文献[13]提出了一种非支配排序粒子群算法，它结合了NSGA-II算法的主要机制，将粒子群算法转化为一种更新颖的多目标粒子群优化(Multiple-Objective Particle Swarm Optimization,MOPSO）算法[14-15]，与NSGA-II相比，这种方法表现出了更强的竞争力。

为了进一步研究电力变换器多目标优化，本文以Vienna变换器和Buck变换器拓扑优化模型为例，分别建立各自相应的多目标优化模型；基于群体智能原理的MOPSO算法来解决电力变换器的多目标优化问题。通过Matlab仿真实验验证了该方法的有效性，并通过与NSGA-II算法优化结果对比证明了该方法能够取得更好的优化效果。本文所提出的方法也可为其他电力变换器多目标优化问题提供参考。

# 2 多目标优化问题模型建立

电力变换器多目标优化设计通常包括多个目标，

是在一个探索空间上同时对多个目标进行探索。

（1）多目标优化问题。寻找矢量 $\vec { \pmb { x } } ^ { * } = [ x _ { 1 } ^ { * } , x _ { 2 } ^ { * }$ … ${ \boldsymbol { x } } _ { n } ^ { * } ] ^ { \mathrm { T } }$ ，同时满足

$$
\begin{array} { c l } { { g _ { _ i } ( \vec { x } ) \geqslant 0 } } & { { i = 1 , 2 , \cdots , m } } \\ { { } } & { { } } \\ { { h _ { _ i } ( \vec { x } ) = 0 \quad i = 1 , 2 , \cdots , p } } \\ { { } } & { { } } \\ { { \operatorname* { m i n } \vec { f } ( \vec { x } ) = \left[ \vec { f } _ { 1 } ( \vec { x } ) , \vec { f } _ { 2 } ( \vec { x } ) , \cdots , \vec { f } _ { k } ( \vec { x } ) \right] ^ { \mathrm { T } } } } \end{array}
$$

式中，矢量 $\vec { \pmb { x } } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ] ^ { \mathrm { T } }$ 为决策变量； $\Vec { f } ( \Vec { x } )$   
为多目标优化函数表达式； $h _ { i } ( \vec { x } )$ 为等式约束函数；  
$g _ { i } ( \vec { x } )$ 为不等式约束函数。

(2）目标函数。以电力变换器的效率、物理尺寸和成本作为三个目标函数，第一个目标函数考虑的是效率，即让输出功率与输入功率的比值最大化，效率为

$$
\eta = \frac { P _ { \mathrm { o u t } } } { P _ { \mathrm { i n } } } = \frac { P _ { \mathrm { i n } } - P _ { \mathrm { l o s s } } } { P _ { \mathrm { i n } } } = 1 - \frac { ( P _ { \mathrm { C } } + P _ { \mathrm { L } } + P _ { \mathrm { Q } } ) } { P _ { \mathrm { i n } } } = - f _ { \mathrm { l } }
$$

式中， $P _ { \mathrm { i n } }$ ， $P _ { \mathrm { o u t } }$ 分别为输入功率和输出功率； $P _ { \mathrm C }$ 为电容器的损耗； $P _ { \mathrm { ~ L ~ } }$ 为磁性元件的损耗； $P _ { \mathrm { Q } }$ 为开关器件的损耗。

虽然每个电子元件的损耗不仅取决于特定的器件参数而且还会受到其他参数（如开关频率、电流和电压波动）的影响，但可将式（4）改写为代表变换器总损耗最小化的函数，即

$$
\left. T o t a l _ { _ { P _ { \mathrm { l o s s } } } } = P _ { _ { \mathrm { C } } } + P _ { _ { \mathrm { L } } } + P _ { _ { \mathrm { Q } } } = f _ { 1 } \right.
$$

第二个目标函数和第三个目标函数考虑的分别是电力变换器的物理尺寸和成本，它们主要体现为各元器件的物理尺寸和成本的总和，可分别由简化的数学模型表示为

$$
T o t a l _ { \mathrm { s i z e } } = s _ { 1 } + s _ { 2 } + s _ { 3 } + \dots + s _ { i } + \dots + s _ { N } = f _ { 2 }
$$

$$
T o t a l _ { \mathrm { c o s t } } = c _ { 1 } + c _ { 2 } + c _ { 3 } + \cdots + c _ { j } + \cdots + c _ { N } = f _ { 3 }
$$

式中， $s _ { i }$ 为第 $i$ 号元器件的物理尺寸； $c _ { j }$ 为第 $j$ 号元件的价格； $N$ 为元器件的总数目。

(3）优化模型。电力变换器多目标优化模型为

$$
M i n i m i z e = \left( \begin{array} { c } { T o t a l _ { P _ { \mathrm { l o s s } } } } \\ { T o t a l _ { \mathrm { s i z e } } } \\ { T o t a l _ { \mathrm { c o s t } } } \end{array} \right)
$$

约束条件为

$$
x ^ { * } \in D a t a b a s e
$$

式中， $x ^ { * }$ 为离散变量；Database为各变换器元器件数据库。

# 3电力变换器效率及功率密度

（1）Vienna 整流器。Vienna 整流器主要由6个快速恢复二极管、3个升压电感器、3个双向功率开关管以及2组输出电容器等构成，如图3所示。分析可知，功率损耗集中在输入电感器、开关器件(IGBT）和二极管（Diode)，输出电容器损耗小可忽略不计[16]。

![](images/8b98070859ce1fd90afba888b13008bece641a73f6fe68f78c13999445931117.jpg)  
图3Vienna 整流器拓扑  
Fig.3Vienna rectifier topology

电感器损耗由输入铁心和绕组的损耗组成，其表达式为

$$
P _ { _ { \mathrm { L } _ { - } \mathrm { l o s s } } } = P _ { _ { \mathrm { C o } } } + P _ { _ { \mathrm { w } } } = 6 . 1 1 \times 1 0 ^ { - 1 8 } B ^ { 2 . 7 } f _ { \mathrm { s w } } ^ { 2 . 0 4 } + I _ { \mathrm { R M S } } ^ { 2 } R _ { \mathrm { L } } { \frac { V _ { \mathrm { I } } I _ { \mathrm { R M S } } } { \sqrt { f _ { \mathrm { s w } } } V _ { \mathrm { L } } ^ { \frac { 1 } { 3 } } } }
$$

式中， $B$ 为磁感应强度； $I _ { \mathrm { R M S } }$ 为电流有效值； $R _ { \mathrm { L } }$ 为绕组等效电阻； $f _ { \mathrm { s w } }$ 为开关频率； $V _ { \mathrm { I } }$ 为输入电压； $V _ { \mathrm { L } }$ 为电感器体积。

开关器件损耗由通态损耗和开关损耗组成，其表达式为

$$
\begin{array} { c l } { P _ { \mathrm { I G B T \_ l o s s } } = P _ { \mathrm { c o n d } } + P _ { \mathrm { s w } } } \\ { \displaystyle } & { = \displaystyle \frac { 1 } { 2 } \Biggl ( V _ { \mathrm { c E 0 } } \frac { I } { \pi } + r _ { \mathrm { c E } } \frac { I ^ { 2 } } { 4 } \Biggr ) + M \cos { \varphi } \Biggl ( V _ { \mathrm { c E 0 } } \frac { I } { 8 } + r _ { \mathrm { c E } } \frac { I ^ { 2 } } { 3 \pi } \Biggr ) + } \\ { \displaystyle } & { \frac { 1 } { \pi } f _ { \mathrm { s w } } ( E _ { \mathrm { s w ( o n ) N } } + E _ { \mathrm { s w ( o f f N ) } } ) \frac { I } { I _ { \mathrm { s } } } \frac { V _ { \mathrm { p n } } } { V _ { \mathrm { c E N } } } } \end{array}
$$

式中， $V _ { \mathrm { C E O } }$ 为门槛电压； $r _ { \mathrm { C E } }$ 为通态等效电阻； $M$ 为调制比； $f _ { \mathrm { s w } }$ 为开关频率； $E _ { \mathrm { s w ( o n ) } }$ 和 $E _ { \mathrm { s w ( o f f ) } }$ 分别为开关器件开通一次和关断一次损失的能量； $I _ { \mathrm { N } }$ 为额定工作电流； $V _ { \mathrm { C E N } }$ 为额定工作电压。

二极管损耗主要包括通态损耗、断态损耗和开

关损耗，其表达式为

$$
\begin{array} { r } { P _ { \mathrm { { D i o d e \mathrm { \_ l o s s } } } } = P _ { \mathrm { o n } } + P _ { \mathrm { o f f } } + P _ { \mathrm { { s w } } } = V _ { \mathrm { { F } } } I _ { \mathrm { { F } } } D + ( 1 - D ) V _ { \mathrm { { R } } } I _ { \mathrm { { R } } } + } \\ { \displaystyle \frac { 1 } { 2 } ( V _ { \mathrm { { f p } } } I _ { \mathrm { { f p } } } t _ { \mathrm { { f p } } } f + t _ { \mathrm { { b } } } I _ { \mathrm { { r p } } } V _ { \mathrm { { r p } } } f _ { \mathrm { { s w } } } ) } \end{array}
$$

式中， $V _ { \mathrm { F } }$ 为二极管正向通态压降； $I _ { \mathrm { F } }$ 为通态电流；$D$ 为占空比； $V _ { \mathrm { ~ R ~ } }$ 为二极管反向电压； $I _ { \mathrm { R } }$ 为反向漏电流； $V _ { \mathrm { f p } }$ 为正向峰值电压； $I _ { \mathrm { f p } }$ 为正向峰值电流； $t _ { \mathrm { f p } }$ 为正向恢复时间； $V _ { \mathrm { r p } }$ 为反向峰值电压； $I _ { \mathrm { r p } }$ 为反向峰值电流； $t _ { \mathrm { b } }$ 为反向电流下降时间； $f _ { \mathrm { s w } }$ 为开关频率。

以效率和功率密度作为优化目标建立多目标优化模型，效率及功率密度为

$$
\eta = \frac { P _ { \mathrm { { o } } } } { P _ { \mathrm { { I } } } } = \frac { P _ { \mathrm { { o } } } } { P _ { \mathrm { { o } } } + P _ { \mathrm { { l o s s } } } } = \frac { P _ { \mathrm { { o } } } } { P _ { \mathrm { { o } } } + \sum _ { m } P _ { \mathrm { { L } } } + \sum _ { n } P _ { \mathrm { { I G B T } } } + \sum _ { l } P _ { \mathrm { { D i o d e } } } }
$$

$$
\rho = \frac { P _ { \circ } } { V } = \frac { P _ { \circ } } { \sum _ { m } V _ { \mathrm { L } } + \sum _ { n } V _ { \mathrm { I G B T } } + \sum _ { l } V _ { \mathrm { D i o d e } } + \sum _ { p } V _ { \mathrm { C } } }
$$

式中， $P _ { \mathrm { ~ o ~ } }$ 为输出功率； $m , \ n , \ l , \ p$ 分别为Vienna整流器拓扑结构中电感器、开关器件、二极管和电容器数目。

(2）Buck变换器。同步降压型转换器如图4所示，其总损失为

$$
P _ { \mathrm { l o s s } } = P _ { \mathrm { c o n d } } + P _ { \mathrm { s w } } + P _ { \mathrm { d r i v e } }
$$

式中，通态损耗 $P _ { \mathrm { c o n d } } = I _ { \mathrm { \tiny ~ R M S } } ^ { 2 } R$ ；开关损耗 $P _ { \mathrm { s w } } = V _ { \mathrm { i n } } ^ { 2 } f _ { \mathrm { s w } }$ 驱动损耗 $P _ { \mathrm { d r i v e } } = Q _ { \mathrm { g } } V _ { \mathrm { g } } f _ { \mathrm { s w } }$ ; $I _ { \mathrm { R M S } }$ 为方均根电流； $R$ 为功率元件的电阻； $V _ { \mathrm { i n } }$ 为输入电压； $f _ { \mathrm { s w } }$ 为开关频率；$Q _ { \mathrm { g } }$ 为峰值栅极电荷； $V _ { \mathrm { g } }$ 为工作栅极电压。

![](images/3d8ab69317d10dc99348a3373b9941f367fac818d0eabff0f76f47b86ccef21d.jpg)  
图4Buck 变换器拓扑  
Fig.4Synchronous Buck converter topology

由于电容器主要在输出电压的波纹而不是效率上起作用[17]，因此在考虑功率变换器效率的优化时，可仅使用具有开关器件和电感器的数据库。由此可得，Buck变换器的损耗为

$$
\begin{array} { r } { P _ { \mathrm { S } _ { \mathrm { l } _ { - } \mathrm { l o s s } } } = I _ { \mathrm { o } } ^ { 2 } R _ { \mathrm { D S ( o n ) } } D + 0 . 5 V _ { \mathrm { i n } } I _ { \mathrm { o } } f _ { \mathrm { s w } } \left( t _ { \mathrm { r } } + t _ { \mathrm { f } } \right) + } \\ { \mathcal { Q } _ { \mathrm { g } } V _ { \mathrm { g } } f _ { \mathrm { s w } } + 0 . 5 \mathcal { Q } _ { \mathrm { o s s } } V _ { \mathrm { i n } } f _ { \mathrm { s w } } \quad } \end{array}
$$

$$
P _ { \mathrm { S } _ { 2 } \mathrm { l o s s } } = I _ { \mathrm { o } } ^ { 2 } R _ { \mathrm { D S } ( \mathrm { o n } ) } ( 1 - D ) + Q _ { \mathrm { g } } V _ { \mathrm { g } } f _ { \mathrm { s w } } + ( 0 . 5 Q _ { \mathrm { o s s } } + Q _ { \mathrm { \pi } } ) V _ { \mathrm { i n } } f _ { \mathrm { s w } }
$$

式中， $D = V _ { \mathrm { o } } / V _ { \mathrm { i n } }$ . $R _ { \mathrm { D S ( o n ) } }$ 为静态漏极到源极导通电阻； $t _ { \mathrm { r } } , \ t _ { \mathrm { f } }$ 为导通时间和开关时间； $\scriptstyle Q _ { \mathrm { o s s } }$ 、 $\scriptstyle Q _ { \mathrm { r r } }$ 为输出电容电荷和二极管反向恢复电荷。

以效率和功率密度作为优化目标建立多目标优化模型，效率及功率密度为

$$
\eta = \frac { P _ { \circ } } { P _ { \mathrm { { I } } } } = \frac { P _ { \circ } } { P _ { \circ } + P _ { \mathrm { { l o s s } } } } = \frac { P _ { \circ } } { P _ { \circ } + \sum _ { m } P _ { \mathrm { { L } } } + \sum _ { s } P _ { \mathrm { { M o s F E T } } } }
$$

$$
\rho = \frac { P _ { \mathrm { o } } } { V } = \frac { P _ { \mathrm { o } } } { \displaystyle \sum _ { m } V _ { \mathrm { L } } + \sum _ { s } V _ { \mathrm { { \scriptscriptstyle M o s F E T } } } + \sum _ { p } V _ { \mathrm { { c } } } }
$$

式中， $P _ { \mathrm { ~ o ~ } }$ 为输出功率； $m$ 、S、 $p$ 分别为Buck变换器拓扑结构中电感器、MOSFET和电容器数目。

# 4 MOPSO算法流程

本文采用的MOPSO算法流程如图5所示，算法参数设定值见表1。

(1）二进制编码粒子。对于每种类别元器件，如果器件数目为 $n$ ，则需要 $\log _ { 2 } ( 2 ^ { \log _ { 2 ^ { n } } } + n - 1 )$ 位。所有类别器件所需位数相加得到总共的二进制为整个探索空间，即 $2 ^ { N }$ ( $N$ 为总的二进制位）。以Buck 变换器为例，每个粒子标记2个MOSFET、1个电感器和1个电容器，其中MOSFET有20种，电感器有13种，电容器有9种，因此每个粒子需要用18个bit位表示。

(2）采用网格法对粒子进行选择。其主要思想是先将搜索空间分成若干网格，全局最优解在包含精英解较少的网格中随机地选取。在最优集里面即存档[18]中根据拥挤程度选择一个最优个体(领导者）。

(3）确定非支配解。根据支配关系进行第一轮筛选，将劣解去除后剩余的解加入到存档中。在存档中根据支配关系进行第二轮筛选，将劣解去除后计算存档粒子在网格中的位置。若存档数量超过了存档阈值，则根据自适应网格进行第三轮筛选，直到阈值限额为止，再重新进行网格划分。

表1MOPSO 算法参数设定值Tab.1 MOPSO parameter settings  

<html><body><table><tr><td>参数</td><td>设定值</td></tr><tr><td>种群数</td><td>200</td></tr><tr><td>迭代次数</td><td>200</td></tr></table></body></html>

![](images/bff21d213067baf427772ac0ecc554f2c2c6077f0af5bc8d09bc16019afe6434.jpg)  
图5MOPSO算法流程图Fig.5Flowchart of MOPSO algorithm

数中开关频率 $f _ { \mathrm { s w } }$ 、功率密度 $\rho$ 和效率 $\eta$ 互相制约，当开关频率 $f _ { \mathrm { s w } }$ 增加时变换器的效率 $\eta$ 减小，同时功率密度 $\rho$ 会增加。当开关频率 $f _ { \mathrm { s w } } = 1 2 0 \mathrm { k H z }$ 时，功率密度 $\rho = 6 . 7 \mathrm { k W } / \mathrm { d m } ^ { 3 }$ ，半导体芯片相对面积 $\tilde { A } _ { \mathrm { c h i p } } =$ $3 2 \mathrm { m m } ^ { 2 } / \mathrm { k W }$ ，开关管和二极管相对总导通损耗 $\varepsilon =$ 0.13，与电容相比电感的相对体积 $\gamma _ { \mathrm { { L } } }$ 略大，效率 $\eta$ 达到 $9 7 . 6 \%$ 。各个指标值均折衷在比较理想的位置，图形形状规则没有明显的偏折。

(2）Buck变换器。Buck变换器的参数见表3。通过由42个功率器件（20个场效应管，13个电感器和9个电容器）组成的数据库，获得了51597个可行组合的解决方案空间，如图7所示。MOPSO算法经20s后收敛到了Pareto前沿，如图8所示。

# 5 实验仿真结果

（1）Vienna整流器。Vienna整流器系统参数见表2。根据系统参数数据要求，对电感器、开关器件、二极管、电容器进行合适的选型，构建元器件数据库。基于此数据库和效率、功率密度模型构成多目标函数，采用MOPSO算法求解，并在优化所得的最优解集中找到一组折衷数据。

表2Vienna整流器参数 Tab.2Vienna rectifier parameters   

<html><body><table><tr><td>参数</td><td>设定值</td></tr><tr><td>输入电压Vi/V</td><td>400</td></tr><tr><td>输出电压V/V</td><td>800</td></tr><tr><td>开关频率fsw/Hz</td><td>50</td></tr><tr><td>系统功率P/kW</td><td>5</td></tr></table></body></html>

![](images/2373754dce33c12d2ae97cd826931157fc6bde5111be065b7377e65883dcdf82.jpg)  
图6为由这组折衷数据绘成的性能指标图，参  
Fig.6Performance index chart of Vienna rectifier

表3Buck变换器参数  
Tab.3 Buck converter parameters   

<html><body><table><tr><td>参数</td><td>设定值</td></tr><tr><td>输入电压Vin/V</td><td>12</td></tr><tr><td>输出电压V/V</td><td>1.5</td></tr><tr><td>最大输出电流IA</td><td>15</td></tr><tr><td>开关频率fs/kHz</td><td>300</td></tr></table></body></html>

![](images/9d9a7683899a5a8880f61b0db78ae3e8e69a7cba088bec92f0623f732aefa9a7.jpg)  
图7 可行解空间

![](images/edf0a3a3c855e3e4d7810ad5d2067815b081a7491d6369a25fde48ffe2dfffa3.jpg)  
图6Vienna整流器性能指标图  
Fig.7 Whole solution space   
图8MOPSO 算法结果 Fig.8MOPSO algorithm results

为了进行权衡分析，从图9最优解中选择的三个典型解A、B和C分别代表面积、成本和损失的最佳结果，见表4。文献[18]采用不同于本文的NSGA-I算法进行相同的多目标优化，从最优解中选择三个典型解进行权衡分析，见表5。

![](images/67dd26b5d0b0f7cf000e7b116ce4bac5b8523db1691b1c1741ef3b25542f5090.jpg)  
图9最优解集 (颜色编码成本)  
Fig.9The optimal solution (color-coded cost)

Tab.4Chosen typical solution for trade-off analysis (MOPSO)   

<html><body><table><tr><td>方案</td><td>功率损耗/W</td><td>面积/mm²</td><td>成本/元</td></tr><tr><td>A</td><td>1.82</td><td>257.58</td><td>14.01</td></tr><tr><td>B</td><td>4.50</td><td>119.62</td><td>37.61</td></tr><tr><td>C</td><td>2.83</td><td>197.54</td><td>8.00</td></tr></table></body></html>

# 表5选择典型方案进行权衡分析 (NSGA-II)

表4选择典型方案进行权衡分析(MOPSO)  
Tab.5Chosen typical solution for trade-off analysis (NSGA-II)   

<html><body><table><tr><td>方案</td><td>功率损耗/W</td><td>面积/mm²</td><td>成本/元</td></tr><tr><td>A</td><td>1.92</td><td>310.64</td><td>29.65</td></tr><tr><td>B</td><td>3.76</td><td>119.81</td><td>13.95</td></tr><tr><td>C</td><td>2.65</td><td>150.32</td><td>10.62</td></tr></table></body></html>

表4方案B与表5方案B相比时，虽然面积相对较小，但损耗较大，成本也较高；表4方案C与表5方案C相比，成本更低，但损耗和面积相对较大。当表4方案A与表5方案A相比时，不仅损耗和面积相对较小，成本也更低。由此得出MOPSO算法的最优解集中存在优于NSGA-II算法的一组解，该结果验证了MOPSO算法能取得更优解的可能性。

# 6 结论

本文提出了一种基于多目标粒子群优化MOPSO的电力变换器优化设计和选择方法。所提出的优化技术能够处理不同的冲突目标，对具有离散参数约束的Vienna整流器以及同步Buck变换器进行迭代搜索和优化。优化解的结果是一组近似最优的折衷值，Pareto前沿使决策者能够选择反映关键目标之间权衡的最佳折衷方案或接近最佳的方案。迭代仿真结果表明了多目标粒子群优化MOPSO方法的有效性，它允许操作者在所提出的目标之间找到接近最优的良好折衷，以筛选出最佳的电力变换器设计，可为其他电力变换器多目标优化问题提供参考。

# 参考文献

[1] Mirjafari M, Balog R S. Multi-objective design optimization of renewable energy system inverters using a descriptive language for the components[C]. In Proc.IEEE 26th Annu. Appl. Power Electron. Conf. Expo.,2011: 1838-1845.   
[2] Kolar JW,Biela J,Waffler S,et al.Performance trends and limitations of power electronic systems[C]. IEEE International Conference on Power Electronics Systems, Chicago, USA,2010: 182-205.   
[3] Kolar JW,Friedli T,Krismer F,et al. Conceptualization and multiobjective optimization of the electric system of an airborne wind turbine[J]. IEEE J. Emerg. Sel. Topics Power Electron.,2013, 1(2) : 73-103.   
[4] Kolar J W, Friedli T. The essence of three-phase PFC rectifer systems[J]. IEEE Transactions on Power Electronics,2014, 29(2) : 543-561.   
[5] Boussaid I, Lepagnot J, Siarry P. A survey on optimization metaheuristics[J]. Inf. Sci.,2013,237: 82-117.   
[6] Marglin S.Public investment criteria[M]. MIT Press, Cambridge, Massachusetts: 1967.   
[7] Chew K C, Kondapalli S R R. Modelling, analysis, simulation and design optimization (genetic algorithm） of DC-DC converter for uninterruptible power supply applications[J]. IEEE Transactions on Power Electronics and Drive Systems,2006,24(15) : 1530-1535.   
[8] Visairo H, Medina MA,Ramirez JM.Use of evolutionary algorithms for design optimization of power converters[C]. IEEE Applied Electrical Communication and Computers Conference,2012: 268-272.   
[9] Yoshida H, Fukuyama Y, Takayama S,et al. A particle swarm optimization for reactive power and voltage control in electric power systems considering voltage security assessment[C]. In Proc.IEEE Int. Conf.Syst.,Man,Cybern.,1999,6: 497-502.   
[10] Debnath S,Ray R N.Harmonic elimination in multilevel inverter using GA and PSO:A comparison[C].In Proc.IEEE Students Conf.Electr., Electron.Comput. Sci.,2012:1-5.   
[11] AlRashidi M,El-Hawary M.A survey of particle swarm optimization applications in electric power systems[J]. IEEE Transactions on Evolutionary Computation,2009,13(4):913-918.   
[12] Jasour A M Z,Khazraei M, Rahmati A. Design of a MIMO controller for a multimodul DC-DC converter based on particle swarm optimized neural network[J]. IEEE Transaction on Power and Energy, 2008,46(12):143-156.   
[13] Li X,A nondominated sorting particle swarm optimizer for multiobjective optimization[C]. In Proceedings of the Genetic and Evolutionary Computation Conference GECCO 2003,2003:37-48.   
[14] Coello CAC,Lechuga M S.MOPSO:a proposal for multiple objective particle swarm optimization[C]. IEEE Congress on Evolutionary Computation, Piscataway, New Jersey, 2002:1051-1056.   
[15] Coello C A C,Pulido G T,Lechuga M S. Handling multiple objectives with particle swarm optimization[J]. IEEE Transactions on Evolutionary Computation,2004, 8(3) : 256-279.   
[16] 常伟，王久和，陈启丽．基于NSGA-II算法 Vienna 整流器多目标优化[J]．中国电机工程学报, 2016，36(增刊）：179-185. Chang Wei,Wang Jiuhe,Chen Qili.Multi-objective optimization of Vienna rectifier based on NSGA-II algorithm[J].Proceedings of the CSEE,2016,36(S) : 179-185.   
[17] Chang Wei,Wang Jiuhe,Chen Qili.Multi-objective optimization of synchronous Buck converter based on NSGA-II algorithm[C]. International Conference on Mechatronics and Automation,Harbin,China, 2016:1391-1395.   
[18] Chen W N,Zhang J,Chung H S,et al.A novel set-based particle swarm optimization method for discrete optimization problems[J].IEEE Transactions on Evolutionary Computation,2010, $1 4 ( 2 ) : 2 7 8 \$ 300.