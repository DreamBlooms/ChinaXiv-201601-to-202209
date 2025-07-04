# 光伏电池建模及变步长MPPT控制

马爱华李磊师贺（南京理工大学自动化学院 南京210094）

![](images/10384a103a2b7cfc831e4cbeb0effac1e98a8da35def0c00791e6d5efb19b125.jpg)

马爱华女1991年生，硕士研究生，研究方向为电力电子在电力系统中的应用。

摘要：针对大环境下的能源短缺与环境污染问题，提出了一种常见新型能源光伏电池（PV）的建模方法。分析了常见的光伏电池MPPT算法，在此基础上对扰动观察法进行了改进，克服了传统扰动观察法在距离最大功率点远近各有限制的缺点。利用Matlab/Simulink 仿真平台搭建了光伏电池的数学模型，并根据改进的 MPPT 算法搭建了控制电路。结果表明，该数学模型可以很好地模拟实际光伏电池的工作特性，改进算法较好地弥补了传统算法的不足，可实现最大功率点跟踪。

关键词：光伏电池扰动观测法变步长Matlab/Simulink最大功率点跟踪中图分类号：TM615

# Modeling of Photovoltaic Cells and MPPT Control Algorithm with Variable Step

Ma Aihua LiLeiShi He (Nanjing University of Science and TechnologyNanjing 210094 China ）

![](images/476038951579eb08d9c9c1d230d33d2095b6b55550f4d41c85d3a72bbd4424d9.jpg)

李磊男1975年生，博士，副教授，博士生导师，研究方向为多电平技术和电力电子在电力系统中的应用。

Abstract: According to the problem of energy shortage and environmental pollution in large environment, a new modeling method of the new energy photovoltaic cell is proposed.Analyzing the common MPPT algorithm of photovoltaic cells,the disturbance observation method is improved on the basis of the analysis,which overcomes the shortcomings of traditional disturbance observation at a distance of maximum power point .Using Matlab / Simulink simulation platform to build a mathematical model of photovoltaic cells,and the control circuit is built according to the improved MPPT algorithm. The results show that the mathematical model can simulate the actual working characteristics of photovoltaic cells well,and the improved algorithm can make up for the deficiency of the traditional algorithm,which can realize the maximum power point tracking.

Keywords: Photovoltaic cell, disturbance observation method, variable step,Matlab/ Simulink, maximum power point tracking

# 1 引言

全球范围内的能源短缺和环境污染问题促进了清洁能源的利用，其中，太阳能由于具有可就地发电和使用，能量无穷无尽，无污染、噪声小，建设周期短等优点获得了广泛的使用[1]。现阶段大多数厂家给出的光伏电池参数都是在标准条件下测定的（温度为 $2 5 \mathrm { { ^ \circ C } }$ ，光照强度为 $1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ )，但在实际使用时，外界的温度和光照条件是实时改变的，需要建立一个较为精确的模型来实现光伏电池的输出。另一方面，为了最大限度地利用太阳能，实现最大功率点跟踪（MaximumPower Point Tracking,MPPT）意义重大。MPPT从本质上来说就是一个自寻优过程，常用的有：定电压跟踪法、电导增量法和扰动观察法等[2]，其中，扰动观察法（P&O）和电导增量法（INC）最为基本[3]，这几种方法各有优缺点。就扰动观察法而言，优点在于结构简单，测量参数少，易于实现。缺点也较为明显，受扰动步长影响较大[4]。

本文介绍了应用最为广泛的光伏电池数学模型，并根据相关公式搭建了模型。在此基础上，改进了传统的扰动观察法，在进行MPPT控制时，采用变步长的扰动方式。最后，通过仿真验证了搭建的光伏电池模块能有效实现实时条件输出，改进的MPPT 算法能够改善 MPPT性能。

# 2 光伏电池建模

# 2.1 公式推导

光伏电池是基于光生伏特效应（photovoltaiceffect）的分布式电源，可将光能转变为电能[5]。首先是由光子（光波）转化为电子、光能量转化为电能量的过程；其次，是形成电压过程。图1为常用的光伏电池等效模型。

![](images/4d74d463d11cd304716028130b9c03e0294a6c00b960c3ee9c82e963b11ee8e1.jpg)  
图1光伏电池等效电路  
Fig.1Equivalent circuit of photovoltaic cells

由图1可知，光伏电池可等效为三个主要的部分，分别为光生电流源 $I _ { \mathrm { p h } }$ 、二极管VD及串、并联电阻（ $\left| R _ { \mathrm { s h } } \right.$ 和 $R _ { \mathrm { s } }$ )。光生电流 $I _ { \mathrm { p h } }$ 由所处环境的光照强度、光伏电池的有效面积和稳定性决定； $I _ { \mathrm { d } }$ 为暗电流，是无光照时流过二极管PN结的电流。接入负载 $R _ { \mathrm { L } }$ ，输出的电流值为 $I _ { \mathrm { L } }$ 。

根据基尔霍夫电流定律

$$
I _ { \mathrm { L } } = I _ { \mathrm { p h } } - I _ { \mathrm { d } } - I _ { \mathrm { s h } }
$$

一般情况下， $R _ { \mathrm { s } }$ 小于二极管正向导通电阻，故可以认为： $I _ { \mathrm { p h } } { = } I _ { \mathrm { s c } }$ ，且 $I _ { \mathrm { d } } = I _ { \mathrm { o } } \left( \exp { \frac { q U _ { \mathrm { d } } } { A k T } } - 1 \right)$ 代入式（1)，可得

$$
I _ { \mathrm { { L } } } = I _ { \mathrm { { s c } } } - I _ { \circ } \left( \exp { \frac { q ( U _ { \mathrm { { L } } } + I _ { \mathrm { { L } } } R _ { \mathrm { { s } } } ) } { A k T } } - 1 \right) - \frac { U _ { \mathrm { { L } } } + I _ { \mathrm { { L } } } R _ { \mathrm { { s } } } } { R _ { \mathrm { { s h } } } }
$$

式中， $I _ { \mathrm { s c } }$ 为光伏电池短路电流； $q$ 为电子电荷（ $1 . 6 \times$ ${ 1 0 } ^ { - 1 9 } \mathrm { C } \mathrm { \dot { \Omega } }$ ； $k$ 为玻尔兹曼常数！ $\mathrm { ( 1 . 3 8 \times 1 0 ^ { - 2 3 } J / K ) }$ 。

由式（2）可知，光伏电池输出电流与多个因素有关，输出电流与电压耦合在一起，计算起来十分复杂。且其中多个参数未知，无法准确测量，因此需要在保证一定准确性的前提下进行简化。考虑到光伏电池的最大功率点跟踪，引入特定温度和光照下最大功率点对应的输出电压 $U _ { \mathrm { m } }$ 和电流 $I _ { \mathrm { { m } } }$

首先考虑光伏电池开路和最大功率点的输出特性。

# 2.1.1开路条件

开路时， $I _ { \mathrm { L } } = 0$ ， $U _ { \mathrm { L } } = U _ { \mathrm { o c } }$ ，并令 $C _ { 1 } I _ { \mathrm { s c } } { = } I _ { \mathrm { o } } , \ C _ { 2 } U _ { \mathrm { o c } } { = }$ $A k T / q$ ，代入式（2）中，得

$$
I _ { \mathrm { L } } = I _ { \mathrm { s c } } \left[ 1 - C _ { 1 } \left( \exp \frac { U _ { \mathrm { L } } } { C _ { 2 } U _ { \mathrm { o c } } } - 1 \right) \right]
$$

# 2.1.2最大功率点处

光伏电池运行于最大功率点处时， $\begin{array} { r } { U _ { \mathrm { L } } = U _ { \mathrm { m } } , ~ I _ { \mathrm { L } } = } \end{array}$ $I _ { \mathrm { { m } } }$ ，代入式（2）得

$$
I _ { \mathrm { m } } = I _ { \mathrm { s c } } \left[ 1 - C _ { 1 } \left( \exp { \frac { U _ { \mathrm { m } } } { C _ { 2 } U _ { \mathrm { o c } } } } - 1 \right) \right]
$$

考虑到正常情况下 $\exp \frac { U _ { \mathrm { m } } } { C _ { 2 } U _ { \mathrm { o c } } } > > 1$ ，因此忽略式（4）小括号中的“-1”项。对式（3）作同样的处理，联立两式，可得

$$
C _ { 1 } = \left( 1 - \frac { I _ { \mathrm { m } } } { I _ { \mathrm { s c } } } \right) \exp \frac { - U _ { \mathrm { m } } } { C _ { 2 } U _ { \mathrm { o c } } }
$$

$$
C _ { 2 } = \left( \frac { U _ { \mathrm { m } } } { U _ { \mathrm { o c } } } - 1 \right) \left[ \ln \left( 1 - \frac { I _ { \mathrm { m } } } { I _ { \mathrm { s c } } } \right) \right] ^ { - 1 }
$$

结合式(2)、式(5）和式(6)，可推导出光伏电池在特定条件下的输出电流。

# 2.2工程用数学模型

一般光伏电池在出厂时厂家只会给出标准测试条件下的5个参数，即短路电流 $I _ { \mathrm { s c } }$ 、开路电压 $U _ { \mathrm { o c } }$ ，最大功率点处的电压 $U _ { \mathrm { m } }$ 和电流 $I _ { \mathrm { { m } } }$ 以及此时的功率$P _ { \mathrm { { m } } }$ 。但光伏电池在实际使用时的外界条件肯定与标况有差别，另外根据PV的工作特性，输出电流和电压也不会一成不变。根据上面推导的公式，可以得出特定温度和光照条件下的各个参数。一般情况下有

$$
I _ { \mathrm { s c } } ^ { \prime } = I _ { \mathrm { s c } } \frac { S } { S _ { \mathrm { n o m } } } ( 1 + \alpha \Delta T )
$$

$$
I _ { \mathrm { { m } } } ^ { \prime } = I _ { \mathrm { { m } } } { \frac { S } { S _ { \mathrm { { n o m } } } } } ( 1 + \alpha \Delta T )
$$

$$
\begin{array} { r } { U _ { \mathrm { o c } } ^ { \prime } = U _ { \mathrm { o c } } \left( 1 - \gamma \Delta T \right) \mathrm { l n } ( \mathrm { e } + \beta \Delta S ) } \\ { ~ } \\ { U _ { \mathrm { m } } ^ { \prime } = U _ { \mathrm { m } } \left( 1 - \gamma \Delta T \right) \mathrm { l n } ( \mathrm { e } + \beta \Delta S ) } \end{array}
$$

式中， $\alpha { = } 0 . 0 0 2 ~ 5 / \mathrm { ^ { \circ } C }$ ； $e$ 为自然对数； $\gamma { = } 0 . 0 0 2 ~ 8 8 / \mathrm { ^ { \circ } C }$ ·$\beta = 0 . 5$ ； $\Delta T$ 和 $\Delta S$ 为特定条件下温度与光照强度和标况的差值，有

$$
\Delta S = \frac { S } { S _ { \mathrm { n o m } } } - 1
$$

$$
\Delta T = T - T _ { \mathrm { n o m } }
$$

式中， $S _ { \mathrm { n o m } }$ 为标准测试条件下的辐照强度，取$1 0 0 0 \mathrm { W / m } ^ { 2 }$ ， $T _ { \mathrm { n o m } }$ 为标准测试条件下的温度，取 $2 5 \mathrm { { C } }$ 。

# 3 光伏电池MPPT控制

# 3.1传统的扰动观察法及其缺点

扰动观察法又称为爬山法，分为电压型和电流型，其中电压型更为常见。根据图2所示光伏电池输出 $P / / F$ 曲线，存在一个电压值 $U _ { \mathrm { m } }$ ，使得输出功率最大。在使用扰动观察法时，给电压一定的扰动$\Delta U$ ，计算光伏电池输出功率 $P$ ，如果输出功率增加，则说明扰动方向正确；反之，扰动方向相反。扰动观察法结构简单，测量参数少，易于实现。但传统的方法采用固定步长，受扰动步长影响较大，扰动步长过大时容易振荡，扰动步长过小时跟踪速度慢，无法适应快速变换的环境。

![](images/18f32b788fcb33b976f2f979495b337d675b7a294e888f3130786f7f469fe366.jpg)  
图2光伏电池输出功率特性曲线

# 3.2变步长扰动观察法

环境一定时，光伏电池的功率特性曲线是一个单峰值函数，存在一个最大值点 $P _ { \mathrm { { m a x } } }$ 。传统的定步长扰动观察法中电压增量为常数 $\Delta U$ ，即 $U _ { k + 1 } =$ ${ U _ { k } } \pm \Delta { U _ { \circ } }$ 由图2可知，扰动步长固定，距离最大功率点较远时，追踪速度较快，但是逼近最大功率点时功率波动较大[4。如果可以实现距离MPP较远时，步长较长，而逼近MPP时，步长变短，这样既可以保证收敛速度，又可以保证最大功率点处的稳定性。这里引进一个变步长因子 $\alpha$ ，利用它来调节扰动时的步长。 $\alpha$ 与距离最大功率点的距离有关，距离越远，值越大，这样可以保证在特性曲线两端的收敛速度，即 $U _ { k + 1 } = U _ { k } \pm \alpha \Delta U _ { \circ }$ 具体含义如图3所示。

![](images/ab0501349a37bed1765e76b588b5b09a2663dd5bed7ecd38a4acf4a81cf9aba5.jpg)  
Fig.2Output power characteristic curve of photovoltaic cells   
图3MPPT步长变化示意图  
Fig.3Schematic diagram of MPPT step change

由图3可知，变步长因子 $\alpha$ 的范围为 $0 \sim 1$ 在爬坡过程中，输出电压越小， $\alpha$ 值越大。具体来说，由功率差值 $\Delta P$ 或电压差值 $\Delta U$ 决定，以功率差为例， $\alpha$ 取值为函数值 $\left. 1 - \exp \left( - \left\| \Delta P \right\| ^ { 2 } \right) \right.$ 。变步长扰动观察法具体的控制流程如图4所示。

由图4可知，变步长扰动观察法与传统扰动观察法的区别在于引入了一个变步长因子 $\alpha$ ，它的值与扰动前后的输出功率差值 $\Delta P$ 相关。通过测量输出电压与电流，计算输出功率 $P$ 。并利用上一工作点的电压和功率，计算出 $\mathrm { d } U$ 和 $\mathrm { d } P$ 。根据 $\mathbf { d } U \times \mathbf { d } P$ 值的正负确定继续扰动的方向。

![](images/f21cd88c53989ed8573d1905c647709eb04ee608a46a09f071227d23e792e1c7.jpg)  
图4MPPT控制流程图

# 4 仿真分析及结果

根据图4给出的MPPT控制流程图，在Matlab/Simulink中搭建控制电路，如图5所示。

此外，光伏电池输出端经Boost电路向负载供电。整个光伏模块分为3个部分，分别为光伏电池输出电路、升压电路及可变负载电路。电路参数为：$C _ { 1 } = 5 5 0 \mu \mathrm { F }$ ， $C _ { 2 } = 3 ~ 3 0 0 \mu \mathrm { F }$ ， $L _ { 1 } = 5 \mathrm { m H }$ ， $R _ { 1 } = 2 5 \Omega$ ， $R _ { 2 } =$ $1 0 0 \Omega$ ，光伏电池额定功率为 $5 . 6 \mathrm { k W }$ 。母线电压即负载电压设为 $3 8 0 \mathrm { V }$ ，输出侧接 $2 5 \Omega$ 的负载，在0.3s时并联一个 $1 0 0 \Omega$ 电阻，在0.4s时外界环境温度由$2 5 \mathrm { { ^ \circ C } }$ 变为 $1 5 \mathrm { { C } }$ ，在0.5s时外界光照强度由 $1 \ { 0 0 0 } \mathrm { W / m } ^ { 2 }$ 变为 $6 0 0 \mathrm { W / m } ^ { 2 }$ 。光伏电池输出电压、电流及功率如6所示。 $t = 0 . 3 \mathrm { s }$ 时负载变为 $2 0 \Omega$ ； $t = 0 . 4 \mathrm { s }$ 时，光照强度从 $1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ 降为 $6 0 0 \mathrm { W / m } ^ { 2 }$ $t = 0 . 5 \mathrm { s }$ 时，外界温度从 $2 5 \mathrm { { ^ \circ C } }$ 降为 $1 5 \mathrm { { ^ \circ C } }$ 。

![](images/b92a7c7014ee525139d233602dd40869d9c80867402158bb1e4b90be64bb1b55.jpg)  
Fig.4Flow chart of MPPT control   
图5MPPT内部结构图  
Fig.5The internal structure of MPPT

由图6可以看出，在温度和光照不变的情况下，即使负荷变化，功率也几乎不变，维持在最大功率点。在温度降低后，功率有所降低。在光照强度降低后，功率大幅减少。但温度、光照变化发生后，功率、电流电压都很快到一个恒定值。

分别改变温度和光照条件，得到输出波形分别如图7所示。

由图7可知，光照强度变化对光伏电池输出影响大于温度变化的影响。

# 5 结论

本文根据光伏电池的等效电路推导了电池的输出电流表达式，并给出了特定温度和外界光照条件下主要参数的计算式。针对光伏电池的MPPT控制，分析了传统扰动观察法存在的局限，并在此基础上提出了改进，引入了变步长因子 $\scriptstyle a$ ，从而既能保证离最大功率点较远时的收敛速度，又能维持最大功率点附近的稳定性。仿真结果表明，所建立的模型和提出的改进方案是合理的，可运用到其他光伏发电系统中。

![](images/ea5ce88620c02df9c5f9e47b156d977a867959aa20f06b09daa00711e9dc901b.jpg)  
图6光伏模块输出波形图

![](images/3a96b8571e203b4784811609ee99caf45c643a152d5e0ee675094fcb53d1ea2a.jpg)  
Fig.6PV module output waveform

![](images/54c7e58655c01d542ead09af5c06ca65eaa7054221f2cca5b60f3b0ecb1bf7fc.jpg)  
图7光伏模块输出波形图  
Fig.7Photovoltaic module output waveform diagram

# 参考文献

[1] 余良辉．光伏发电最大功率跟踪技术及并网系统 研究[D]．南京：南京理工大学，2013.   
[2] Venkata RatnamKolluru，Kamalakanta Mahapatra,Bidyadhar Subudhi.Development and implementation of control algorithms for a photovoltaic system[J]. Engineering and Systems, Students Conference,2013:1-5.   
[3] 杨永恒，周克亮．光伏电池建模及MPPT控制策 略[J]．电工技术学报，2011，26(S1)：229-234. Yang Yongheng, Zhou Keliang. Photovoltaic cell modeling and MPPT control strategy[J]. Transactions of China Electrotechnical Society,2011,26(S1): 229-234.   
[4] 张慧慧．直流微电网建模与控制策略研究[D]．保 定：华北电力大学，2014.   
[5] Hiroto Kasai, Toshiyuki Sato.Impurity photovoltaic effect in crystalline silicon solar cells[C]. IEEE Photovoltaic Specialists Conference, 1997: 215-218.   
[6] 刘施宇，葛红娟，袁晶．光伏系统双轨迹最大功率 跟踪技术仿真研究[J]．电气应用，2016，35(7)： 67-71.   
[7] Suo Chunguang,Zhang Wenbin,Wu Guangmin,et al. Modellingand simulation ofMPPT algorithm for PV grid-connected system[J]. Integrated Ferroelectrics, 2015,162(1): 18-23.   
[8] Haque Ahteshamul. Maximum power point tracking (MPPT） scheme for solar photovoltaic system[J]. Energy Technology& Policy,2014,1(1):115-122.   
[9] Wu Qianqiong,Chang Xiaoying. Simulation of MPPT control algorithm for photovoltaic cell based on Matlab[C].International Conference on Electric Information and Control Engineering,2011:4468- 4471.   
[10] Jiang Yuncong,Jaber A,Abu Qahouq.Evaluation of output current PV MPPT controller with different step sizes and multiple panels or cells[C]. TwentySeventh Annual IEEE Applied Power Electronics Conference and Exposition,2012:1872-1876.   
[11] 王彩明．低压直流微电网中相关控制策略的研究 [D]．天津：天津理工大学，2015.