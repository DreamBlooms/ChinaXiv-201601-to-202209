# 三相PWM整流器模型预测控制的研究

刘丛伟 林跻云

(北方工业大学电气与控制工程学院北京100041)

![](images/634ddc74fd0d548b0a77c30d1442a0b777881fd54b78421f27ce8ec8529af4fc.jpg)

刘丛伟男 1969年生，副研究员，博士后，研究方向为电力电子变换器基础理论，高压大功率变流器，电机控制系统以及光伏和风力发电系统。

摘要：本文建立并分析了三相PWM整流器的数学模型，研究了基于模型预测控制的PWM整流器控制系统。通过对传统单矢量与双矢量模型预测控制方法的分析和仿真，研究了传统双矢量模型预测和单矢量模型预测网侧THD性能不佳的原因，为了提高模型预测控制系统网侧电流THD的性能，提出改进双矢量和改进单矢量模型预测控制方法。该方法提高了网侧电流THD性能，同时也保持了最好的电流和电压动态性能，仿真结果验证了该方法的可行性和有效性。

关键词：PWM整流器 模型预测控制目标函数THD中图分类号：TM461

# Research on Three-Phase PWMRectifier Model Predictive Control

Liu Congwei Lin Jiyun (Institute of Electrical and Control Engineering North China University of TechnologyBeijing 100041 China)

![](images/8664357ff9fccef6e3dec7819f606e774a4525b59d9d010fd02d99d47ee9e0a7.jpg)

林跻云女 1992年生，硕士研究生，研究方向电力电子与电力传动。

Abstract: This paper builds and analyzes the mathematical model of three-phase PWM rectifier, and the model predictive control for PWM rectifier. By analysis and simulations for traditional single and double vector model predictive control,the reason why the total harmonic distortion (THD) performance of grid current in rectifier is researched. To improve THD performance of rectifier under model predictive control, this paper proposes modified single and double vector model predictive control methods, The methods improve the THD performance of grid current, and keep the best current and voltage dynamic performance.The simulation results verify the validity and effectiveness of proposed methods.

Keywords: PWM rectifier, model predictive control, target function, THD

# 1 引言

三相PWM整流桥通过桥臂中的6个半导体全控开关管的开通与关断实现其整流功能，与传统二极管整流器相比，PWM整流器具有很好的网侧电流和直流侧电压控制性能以及能量双向流动能力；但是开关管的开关损耗是整流桥重要的损耗来源。为了提高三相PWM整流器的效率，在保持系统高控制性能的同时，降低开关损耗是研究的重要方向。

理论分析与仿真验证可知：如果PWM整流器工作在经典闭环双PI控制下，想要得到很好的控制效果，就需要较高的开关频率，而且随着其开关频率的不同，PI参数也需要进行调节，即其对PI参数较为敏感，较为不便[1]；直接功率控制（DPC）则是使用功率内环等效替代电流内环，通过对有功功率和无功功率直接进行控制达到控制效果，虽然控制速度快，但是控制的稳态性能劣于双闭环PI控制[2-5]；模型预测控制是根据整流器数学模型进行的一种较为精准的控制，可以根据目标函数中各个控制指标的不同达到不同的控制效果，但正是因为如此，随着控制目的不同就需要对目标函数进行改进[6-8]

文献[9]和文献[10]提出了单矢量和双矢量模型预测控制，在相同的采样频率下，双矢量模型预测控制可以得到更优的THD控制效果，但是在相同的较低的开关频率下得到的控制效果并不是很理想，在相同的开关频率下，双矢量控制效果反而劣于单矢量控制。

本文在传统双矢量模型预测控制[10]的基础上,提出了一种改进算法，使得在同样的开关频率下，改进双矢量模型预测控制得到了更优的THD，并且保持了良好的动态性能，本文也利用改进算法对传统单矢量模型预测控制进行了改进。通过计算机仿真实验对比了经典双闭环PI控制方法、单矢量模型预测控制、双矢量模型预测控制、改进单矢量模型预测控制和改进双矢量模型预测等几种控制方法在相同开关频率下的THD指标的优劣，验证了改进方法的可行性。

# 2 三相PWM整流器数学模型[3-5]

三相PWM整流器主回路包含网侧三相电源、线路等效电感和等效电阻、整流桥、直流侧电容以及负载。其主回路电路图如图1所示。

![](images/e53d297da09749e6e00ce56a24cb0158e89f522c75f1e0cbd5f1edcfd51b3ffd.jpg)  
图1三相PWM整流器主回路

所以可以得到整流器主回路数学公式

$$
\left\{ \begin{array} { l l } { \displaystyle e _ { \mathrm { a } } = L \frac { \mathrm { d } i _ { \mathrm { a } } } { \mathrm { d } t } + R i _ { \mathrm { a } } + V _ { \mathrm { a } } + V _ { \mathrm { n o } } } \\ { \displaystyle e _ { \mathrm { b } } = L \frac { \mathrm { d } i _ { \mathrm { b } } } { \mathrm { d } t } + R i _ { \mathrm { b } } + V _ { \mathrm { b } } + V _ { \mathrm { n o } } } \\ { \displaystyle e _ { \mathrm { c } } = L \frac { \mathrm { d } i _ { \mathrm { c } } } { \mathrm { d } t } + R i _ { \mathrm { c } } + V _ { \mathrm { c } } + V _ { \mathrm { n o } } } \end{array} \right.
$$

式中， $e _ { \mathrm { a } }$ ， $e _ { \mathrm { b } }$ ， $e _ { \mathrm { c } }$ 为网侧三相电源电压； $L$ ， $R$ 分别为网侧线路等效电感和等效电阻； $V _ { \mathrm { a } }$ 、 $V _ { \mathrm { b } }$ 、 $V _ { \mathrm { c } }$ 分别为整流桥等效电压。

由于电网电源一般为三相正弦对称且稳定，所以可以将整流器主回路三相等效成如图2所示的等效电路图，其中将整流器桥直接等效为整流桥电源，由此推导得出整流器主回路的数学公式。

![](images/be6cacdb87ff191355d9e90c5309655a2aa5d599dce6719b00548c41ad857d6a.jpg)  
Fig.1The main circuit of Three phase PWM rectifier   
图2整流器主回路等效电路图  
Fig.2Equivalent circuit diagram of the main circuit rectifier

将式（1）的三相电压和电流量改写成复矢量形式，得到

$$
e = L { \frac { \mathrm { d } i } { \mathrm { d } t } } + R i + \nu
$$

式中， $\nu = V _ { \mathrm { a , b , c } } + V _ { \mathrm { n o } }$ 0

根据复功率定义[和功率与电流、电压的关系，经坐标系转换，可以得到

$$
S = \frac { 3 } { 2 } i ^ { * } e
$$

$$
S = P + \mathrm { j } Q
$$

式中， $i ^ { * }$ 代表电流复矢量的共轭值。

# 3 传统模型预测控制

# 3.1模型预测控制框图

基于模型预测控制的PWM整流器控制系统框图如图3所示。

![](images/a33dc3a2e328b444811c949ca9d14c3c68f86e9fbafc7e65f44201ddfb57b537.jpg)  
图3PWM整流器模型预测框图

显然，通过对交流侧电网电压及电流和当前时刻直流侧电压的检测，可以得到当前时刻的电压、电流以及功率值，并可依据现有的PWM整流器模型和已经确定的当前时刻有功功率和无功功率预测当前时刻施加不同开关矢量对下一时刻的有功功率与无功功率的影响，再通过目标函数的评价，就可以得出当前时刻应该施加的最优作用开关矢量。

# 3.2单矢量模型预测控制原理 [9]

根据PWM整流器的旋转坐标系下的数学模型，则可以得到

$$
e = L { \frac { \mathrm { d } i } { \mathrm { d } t } } + R i + \nu
$$

$$
\frac { \mathrm { d } S } { \mathrm { d } t } = \frac { 1 } { L } \Bigg [ \frac { 3 } { 2 } \Big ( \mid e \mid ^ { 2 } - \nu ^ { * } e \Big ) - \Big ( R - \mathrm { j } w L \Big ) S \Bigg ]
$$

假设当前时刻为 $k$ 时刻，对于单一矢量作用后的整流器有功功率和无功功率，通过模型预测方法可以得出现在所施加的开关矢量对有功功率和无功功率的影响

$$
{ \frac { \mathrm { d } p } { \mathrm { d } t } } = { \frac { 3 } { 2 L } } { \Bigl [ } | e | { \vphantom { \frac { 1 } { 2 } } } ^ { 2 } - \mathrm { R e } ( \nu ^ { * } e ^ { k } ) { \Bigr ] } - { \frac { R } { L } } p ^ { k } - w q ^ { k }
$$

$$
\frac { \mathrm { d } q } { \mathrm { d } t } = - \frac { 3 } { 2 L } \mathrm { I m } ( \nu ^ { * } e ^ { k } ) - \frac { R } { L } q ^ { k } + w p ^ { k }
$$

则可以推导出第一个矢量作用完毕， $k + 1$ 时刻

的复功率预测值

$$
\begin{array} { c } { \displaystyle { \left\{ p ^ { k + 1 } = p ^ { k } + \frac { \mathrm { d } p } { \mathrm { d } t } \Delta t \right. } } \\ { \displaystyle { \left. \left[ q ^ { k + 1 } = q ^ { k } + \frac { \mathrm { d } q } { \mathrm { d } t } \Delta t \right. \right. } } \end{array}
$$

根据目标函数

$$
F = \left| \boldsymbol { p } ^ { \mathrm { r e f } } - \boldsymbol { p } ^ { k + 1 } \right| ^ { 2 } + \left| 0 - \boldsymbol { q } ^ { k + 1 } \right| ^ { 2 }
$$

显然可以判定，当前 $k$ 时刻施加的开关矢量(选出的开关矢量为6个非零矢量和零矢量中的任意一个）。

# 3.3双矢量模型预测控制原理 [10]

相比于单矢量模型预测的方法，双矢量模型预测控制方法由于其在每一个PWM周期内可以作用两个开关矢量，所以在相同的采样频率下双矢量模型预测方法的开关频率因为高于单矢量控制，其效果明显优于单矢量控制；而在相同的开关频率下，其采样频率要低于单矢量模型预测方法。不仅如此双矢量模型预测控制选择开关矢量作用时间上有更好的灵活性，所以其控制效果理论上要优于单矢量控制。

如图4所示，基于双矢量模型预测控制在一个PWM周期内作用两个开关矢量（这两个开关矢量分别是6个非零矢量和零矢量中的一个开关矢量），假设第一个矢量作用完毕是 $k + 1$ 时刻，第二个矢量作用完毕是 $k + 2$ 时刻，第一个矢量作用时间为 $\Delta t$ 且其对有功功率的影响为 $\mathrm { d } p _ { 1 } / \mathrm { d } t$ ，第二个矢量对有功功率的影响为 $\mathrm { d } p _ { 2 } / \mathrm { d } t$ ，可以得出

![](images/e4c012c43712b14e67a9367701595f58b9a8f79f5717eebd022969a2144df9aa.jpg)  
Fig.3The predictive model diagram of PWMRectifier   
图4双矢量MPC有功功率控制示意图  
Fig.4Double vector MPC active control schematic

$$
\begin{array} { r } { \left\{ p ^ { k + 2 } = p ^ { k } + \displaystyle \frac { \mathrm { d } p _ { 1 } } { \mathrm { d } t } \Delta t + \frac { \mathrm { d } p _ { 2 } } { \mathrm { d } t } ( t _ { \mathrm { p w m } } - \Delta t ) \right. } \\ { \displaystyle \left. \left[ q ^ { k + 1 } = q ^ { k } + \frac { \mathrm { d } q _ { 1 } } { \mathrm { d } t } \Delta t + \frac { \mathrm { d } q _ { 2 } } { \mathrm { d } t } ( t _ { \mathrm { p w m } } - \Delta t ) \right. \right. } \end{array}
$$

依然通过单矢量模型预测方法的目标函数对两个矢量作用后的 $k + 2$ 时刻进行评价[9-10]，即

$$
F = \left| { p ^ { \mathrm { r e f } } - p ^ { k + 2 } } \right| ^ { 2 } + \left| { 0 - q ^ { k + 2 } } \right| ^ { 2 }
$$

显然通过目标函数衡量两矢量作用完后对有功功率和无功功率的影响进行评价，可以在 $k + 2$ 时刻获得良好的控制效果，如图3所示，选择第二种开关矢量进行作用。

# 4 改进模型预测控制

# 4.1改进双矢量模型预测控制

# 4.1.1改进双矢量模型预测控制原理

传统双矢量模型预测控制方法的目标函数针对的是一个PWM周期末 $k + 2$ 时刻有功功率和无功功率值偏差值优化。但第一个矢量作用后的 $k + 1$ 时刻的有功功率及无功功率偏差值失控的话，控制效果则依然会不佳，这就是为什么在同样开关频率下，传统双矢量模型预测控制THD比单矢量还差的原因，因为单矢量模型预测控制不存在失控的 $k + 1$ 时刻。

本文所提出的改进方法有如下两点：

（1）首先把双矢量控制的 $k + 1$ 时刻的功率偏差与 $k + 2$ 时刻功率偏差值和作为优化目标，从而消除了双矢量控制的失控时刻。

(2）改进不仅仅考虑对 $k + 1$ 和 $k + 2$ 这两个时刻的功率偏差值的优化，也考虑将从 $k$ 时刻到 $k + 2$ 时刻这一段时间的每一个时刻的偏差的积分值进行优化，该积分值几何上等于也就是考虑将无功功率和有功功率参考值与实际值的差对应的面积大小。要使其在 $k$ 到 $k + 2$ 时刻之间所有时刻积分值最小，也就是使得参考值和实际值差围成的面积最小。为了减少积分计算工作量，本文提出了一种使 $k + 1$ 时刻和 $k + 2$ 时刻偏差值符号相反的方法来确保在偏差大小差不多的情况下偏差与时间轴围成的面积更小，从而可以降低整个PWM周期的误差积分值，降低网侧电流THD数值。

如图5a所示，虽然开关矢量 $\pmb { \nu } _ { 1 }$ 在一个PWM周期结束后距离功率参考值最近，开关矢量 $\pmb { \nu } _ { 1 }$ 作用一个周期后并不是最接近参考值，但是根据图5b可以看出，开关矢量 $\mathbf { \nu } _ { \nu _ { 2 } }$ 与 $\pmb { \nu } _ { 1 }$ 与参考值 $p ^ { \mathrm { r e f } }$ 所包围的面积相比， $\mathbf { \nu } _ { \nu _ { 2 } }$ 矢量作用后， $t _ { 1 }$ 时间段偏差面积为接近长方形的梯形； $\pmb { \nu } _ { 1 }$ 矢量作用后， $t _ { 1 }$ 时间段偏差面积是分布在给定值两侧的两个三角形；显然由于分布在两侧的三角形面积较小，理论上仅有同一侧面积的1/2左右（三角形面积是1/2的底乘以高；长方形面积是底乘以高)，显然， $\pmb { \nu } _ { 1 }$ 开关矢量产生的功率偏差面积更小，其对应的网侧电流THD更小。

![](images/ee71259196a40d45cef8da1de39a036d078ff98863b4f7c0c19ec08efd08fad4.jpg)  
图5双矢量MPC与改进双矢量MPC有功功率控制原理示意图  
Fig.5Double vector MPC and improved double vector MPC active control schematic

由图5b可以推出，同时考虑 $k + 1$ 和 $k + 2$ 时刻有功功率和无功功率偏差的目标函数 $F _ { 1 }$ 为

$$
\begin{array} { l } { \displaystyle { \left\{ p ^ { k + 1 } = p ^ { k } + \frac { \mathrm { d } p _ { 1 } } { \mathrm { d } t } \Delta t _ { 1 } \right. } } \\ { \displaystyle { \left. \left[ q ^ { k + 1 } = q ^ { k } + \frac { \mathrm { d } q _ { 1 } } { \mathrm { d } t } \Delta t _ { 1 } \right. \right. } } \end{array}
$$

$$
\left\{ \begin{array} { l l } { \displaystyle p ^ { k + 2 } = p ^ { k } + \frac { \mathrm { d } p _ { _ 1 } } { \mathrm { d } t } \Delta t _ { _ 1 } + \frac { \mathrm { d } p _ { _ 2 } } { \mathrm { d } t } \Delta t _ { _ 2 } } \\ { \displaystyle q ^ { k + 1 } = q ^ { k } + \frac { \mathrm { d } q _ { _ 1 } } { \mathrm { d } t } \Delta t _ { _ 1 } + \frac { \mathrm { d } q _ { _ 2 } } { \mathrm { d } t } \Delta t _ { _ 2 } } \end{array} \right.
$$

$$
F _ { 1 } = \left| p ^ { \mathrm { r e f } } - p ^ { k + 1 } \right| ^ { 2 } + \left| 0 - q ^ { k + 1 } \right| ^ { 2 } + \left| p ^ { \mathrm { r e f } } - p ^ { k + 2 } \right| ^ { 2 } + \left| 0 - q ^ { k + 2 } \right| ^ { 2 }
$$

式中， $\Delta t _ { 1 }$ 为第一个矢量作用时间，为图5中 $t _ { 1 }$ ; $\Delta t _ { 2 }$ 为第二个矢量作用时间，为图5中 $t _ { 2 }$ ，且 $\Delta t _ { 1 } + \Delta t _ { 2 } =$ $t _ { \mathrm { p w m } }$ 。

由式（15）可知，该目标函数不仅将 $k + 2$ 时刻的有功功率和无功功率效果进行衡量，而且将 $k + 1$ 时刻的有功功率和无功功率进行评估，通过该目标函数可以很好地选出在 $k + 1$ 与 $k + 2$ 时刻同时对电压、电流波形影响最小的开关矢量，这样在各种情况下就不会出现 $k + 1$ 时刻控制效果劣于单矢量控制方法的现象。

为了进一步降低整个周期期间的偏差积分值，也就是降低偏差面积，需要在 $k + 1$ 和 $k + 2$ 时刻偏差目标函数的基础上，加上偏差的正负检测项 $F _ { 2 }$ 其为

$$
\begin{array} { c } { { F _ { 2 } = \left| p ^ { k } + p ^ { k + 1 } - 2 p ^ { \mathrm { r e f } } \right| ^ { 2 } + \left| q ^ { k } + q ^ { k + 1 } \right| ^ { 2 } + } } \\ { { \left| p ^ { k + 1 } + p ^ { k + 2 } - 2 p ^ { \mathrm { r e f } } \right| ^ { 2 } + \left| q ^ { k + 1 } + q ^ { k + 2 } \right| ^ { 2 } } } \end{array}
$$

综合考虑 $F _ { 1 }$ 和 $F _ { 2 }$ 的影响，因为 $k + 1$ 和 $k + 2$ 时刻的偏差 $F _ { 1 }$ 对面积的影响更直接，将 $F _ { 1 }$ 加权系数设为1， $F _ { 2 }$ 加权系数设为1/2，所以最终的目标函数为

$$
F = F _ { 1 } + \frac { 1 } { 2 } F _ { 2 }
$$

# 4.1.2开关矢量及其作用时间

根据两个开关矢量分别在6个非零矢量及一个零矢量中选择（两个零矢量按一个有效零矢量计算)，则理论上共计49种组合，但是只有42种有效组合，另外7种组合与这42种组合有重复情况出现。由于在目标函数中对控制稳态效果影响较大的是 $F _ { 1 }$ 部分，所以在计算矢量作用时间时以 $F _ { 1 }$ 为准进行计算。

显然，根据式（11）和式（15)，可以计算

$$
\frac { \partial { F _ { 1 } } } { \partial { \Delta t } } = 0
$$

得到第一个矢量最优的作用时间（第二个矢量作用时间为 $t _ { \mathrm { p w m } } - \Delta t \rrangle$

$$
\Delta t = \frac { ( p ^ { \mathrm { r e f } } - p ^ { k } ) ( 2 \Delta p _ { 1 } - \Delta p _ { 2 } ) + ( \Delta p _ { 2 } ^ { 2 } - \Delta p _ { 1 } \Delta p _ { 2 } ) t _ { \mathrm { p w m } } } { \Lambda } +
$$

$$
\frac { ( q ^ { \mathrm { r e f } } - q ^ { k } ) ( 2 \Delta q _ { 1 } - \Delta q _ { 2 } ) + ( \Delta q _ { 2 } ^ { 2 } - \Delta q _ { 1 } \Delta q _ { 2 } ) t _ { \mathrm { p w m } } } { \Lambda }
$$

其中

$$
\varLambda = ( \Delta q _ { 1 } - \Delta q _ { 2 } ) ^ { 2 } + \Delta q _ { 1 } ^ { 2 } + ( \Delta p _ { 1 } - \Delta p _ { 2 } ) ^ { 2 } + \Delta p _ { 1 } ^ { 2 }
$$

# 4.2改进单矢量模型预测控制原理

为了验证前节改进算法对其他模型预测控制算法也具有改进潜力，本节将前述的改进算法应用于传统单矢量模型预测控制算法，其原理是使 $k$ 时刻和 $k + 1$ 时刻有功和无功功率给定值与实际预测值的偏差数值的符号相反，而传统方法不考虑 $k$ 时刻和$k + 1$ 时刻偏差的符号变号，仅考虑在每个时刻偏差最小。如前面双矢量模型预测控制改进算法类似，改进算法通过安排前后时刻偏差变号，与不变号相比，可以确保在每个时刻的偏差大小差不多的情况下，偏差与横坐标围成的面积更小，从而可以降低整个PWM周期的误差积分值，降低网侧电流THD数值。

根据单矢量模型预测控制改进算法原理，将式 （16）和式（17）目标函数改进为

$$
F _ { 2 } = \left| p ^ { k } + p ^ { k + 1 } - 2 p ^ { \mathrm { r e f } } \right| ^ { 2 } + \left| q ^ { k } + q ^ { k + 1 } \right| ^ { 2 }
$$

$$
F = F _ { 1 } + { \frac { 1 } { 2 } } F _ { 2 } = \left| p ^ { \mathrm { r e f } } - p ^ { k + 1 } \right| ^ { 2 } + \left| 0 - q ^ { k + 1 } \right| ^ { 2 } +
$$

$$
\frac { 1 } { 2 } \biggl ( \left| p ^ { k } + p ^ { k + 1 } - 2 * p ^ { \mathrm { r e f } } \right| ^ { 2 } + \left| q ^ { k } + q ^ { k + 1 } \right| ^ { 2 } \biggr )
$$

由于单矢量模型预测控制在一个PWM周期内只作用一个开关矢量，所以其不需要再单独计算矢量作用时间。

# 4.3零矢量的选择

假若预测控制选择开关矢量的结果里有一个为零矢量，另外一个为非零矢量，则根据非零矢量选择零矢量为 $^ { 6 6 } 0 0 0 ^ { 3 }$ 还是“111”状态，若非零矢量中“1”状态较多，则选择“111”为有效零矢量，若“0”状态较多，则选取‘ $\cdot 0 0 0 ^ { \cdots }$ 为有效零矢量。

# 5 仿真结果分析

本文对SVPWM控制方法和传统的单矢量、双矢量模型预测控制进行了仿真。仿真中，PWM整流器各个参数为：交流侧电网电压 $e = 3 8 0 \mathrm { V }$ ；电感参数为 $L = 1 0 \mathrm { m H }$ ；电阻值为 $R = 0 . 3 \Omega$ ；直流侧电压给定为 $ { U _ { \mathrm { d c } } } ^ { * } = 6 8 0  { \mathrm { V } }$ ，电压给定突变时 $U _ { \mathrm { d c } } ^ { ' } = 6 8 5 \mathrm { V }$ ，$R _ { \mathrm { r o a d } } = 9 7 \Omega$ ，直流侧电容值为 $C = 8 4 0 \mu \mathrm { F }$ 。内环阶跃响应信号：模型预测控制为 $1 0 \ 0 0 0 \mathrm { W }$ ，SVPWM控制方法由于内环为电流环，所以根据电流功率对应关系给阶跃信号为14A。其中SVPWM控制方法的内环参数为 $P = 1 0$ ， $I = 1$ ，此时开关频率设定为$2 \mathrm { k H z }$ 。模型预测控制的仿真图如图6所示。

![](images/eccc4aaf5667feb762d43c72e3116c7f9b575e07f0a8d76d01ec4774c05cbde8.jpg)  
Fig.6Model predictive control simulation diagram

# 5.1动态性能指标对比

为了验证改进双矢量模型预测控制的动态性能，观察了系统的两种动态响应：电压外环给定突变以及内环的阶跃响应。根据以上仿真数据进行仿真的动态性能波形如图7所示。

![](images/33db48f8ed28ba85d331bf18b7364549f4a382343f64287ec0910686e1eaedce.jpg)  
图7显示了电压给定突变时直流侧母线电压的  
(b）单矢量MPC

![](images/ce3fb92d903ef96cb8a63b7b2fe99a30206c4dbb1c3c062c3d90d36c70edd0b0.jpg)  
图6模型预测控制仿真图  
图7电压给定突变动态响应图  
Fig.7Voltage given mutation dynamic response graph

变化，显然 $2 \mathrm { k H z }$ 开关频率时SVPWM控制方法的快速性能最差，而单、双矢量模型预测控制与改进的单、双矢量模型预测控制都几乎在0.0053s时达到稳定，但其中单矢量模型预测控制的电压超调量大于双矢量模型预测控制与改进双矢量模型预测控制，改进双矢量模型预测控制的快速性同时优于另外两种模型预测控制方法，其超调量在模型预测控制中也是最少的，改进单矢量模型控制的动态性能没有太大变化，验证了改进模型预测控制的动态性能优于另外3种控制算法。

图8显示的是内环阶跃响应，显然SVPWM控制方法的快速性能依然较差，单矢量模型预测控制虽然比双矢量模型预测控制方法与改进的控制方法早达到稳定状态，但是其反应时间几乎相同都是约为0.00035s，而改进双矢量模型预测控制方法的稳态功率波动是最优的。

# 5.2稳态性能指标对比

![](images/1a2d00180f52555a3e901faf8155323889553129370ae87ea497c77b284c76a5.jpg)  
图9显示的是稳态时网侧的电流波形，图10显

![](images/3626de9bfa33368015b2406fa24f7c05804c4fb52fef0d6f48c78164e5719f95.jpg)  
图8内环阶跃响应图

![](images/3d10e360c7ec2831b54cafda437b4c7b15b8e35661b6317672bafb62412c47e1.jpg)  
Fig.8Inner step response   
图9网侧电流FFT分析电流信号图  
Fig.9The grid current fft analysis of current signal diagram

示的是此时网侧电流的FFT分析频谱，下表则是统计了各种控制方法在 $2 \mathrm { k H z }$ 开关频率下的稳态THD指标。显然无论单矢量还是双矢量传统MPC控制其THD指标都劣于SVPWM，但是将改进方法应用到传统单、双矢量模型预测控制方法后，改进单矢量MPC比传统单矢量MPC降低了 $14 . 6 \%$ ，比SVPWM降低了 $9 . 2 \%$ ；改进双矢量MPC比传统双

(% 4 Fundamental (50Hz)=10.44, THD=9.86%   
32   
1   
0 hu L 0 5000 10000 15000 20000 f/Hz (a）SVPWM   
(% 302205050 0 $= 1 0 . 4 5 \%$ 20000 f/Hz (b）单矢量MPC   
(% 2.0 Fundamental (50Hz)=10.41,THD $= 8 . 9 5 \%$   
1.5   
1.0   
0.5   
0 0 2 4 6 8 10 12 14 16 18 20 f/kHz (c）改进单矢量MPC   
(% Fundamental (50Hz)=10.35, $\mathrm { T H D } = 1 1 . 9 8 \%$ （204号   
54321   
0 0 5000 10000 15000 20000 f/Hz (d）双矢量MPC Fundamental (50Hz)=10.37, THD=8.08%   
(% 53225000 0 5000 10000 15000 20000 f/Hz (e）改进双矢量MPC

矢量MPC 降低了 $3 2 . 6 \%$ ，比SVPWM降低了 $1 8 \%$ 。在所有方法中，改进双矢量模型预测控制的THD最小，为 $8 . 0 8 \%$ ，仿真结果验证了改进方法对提高系统的稳态THD指标有很大作用。

表各种控制方法THD对比Tab.The THD comparison of various control methods  

<html><body><table><tr><td>控制方法</td><td>Tpwm/s</td><td>THD(%)</td></tr><tr><td>SVPWM</td><td>0.000 5</td><td>9.86</td></tr><tr><td>传统单矢量MPC</td><td>0.000 091</td><td>10.45</td></tr><tr><td>改进单矢量MPC</td><td>0.000 092</td><td>8.95</td></tr><tr><td>传统双矢量MPC</td><td>0.000 21</td><td>11.98</td></tr><tr><td>改进双矢量MPC</td><td>0.000 211</td><td>8.08</td></tr></table></body></html>

此外，从SVPWM控制方法的频谱分析显示其谐波主要存在于开关频率或者倍频于开关频率附近，所以其THD主要由于开关频率造成，而模型预测方法主要是集中于低频段，尤其是改进后的双矢量控制方法将频谱向高频挪移，得到了较优的控制效果，该改进方法可望推广到其他模型预测控制算法以改进网侧电流THD性能。

# 6 结论

通过与传统单、双矢量模型预测控制及SVPWM控制方法的数据对比发现，改进单、双矢量MPC控制方法在相同的开关频率下的动态响应明显优于SVPWM，且稳态波动小于未改进之前的单、双矢量模型预测方法，其稳态THD指标明显优于另外3种控制方法，所以改进双矢量模型预测方法的动态性能和稳态性能都是最优的，改进单矢量模型预测方法其次，仿真结果充分验证了本文提出的改进方法在双矢量和单矢量模型预测控制算法上的可行性以及其优良的网侧电流THD性能。

# 参考文献

[1] 张兴，张崇巍．PWM整流器及其控制[M]．北京： 机械工业出版社，2012.   
[2] 许伯强，张晓峰．基于新型开关表的PWM整 流器直接功率控制[J]．电力科学与工程，2009, 25(8): 1-4. Xu Boqiang, Zhang Xiaofeng.Direct power control ofPWM rectifier based on new switch table[J]. Electric Power Science and Engineering,2009, 25(8): 1-4.   
[3] Zhang Yongchang,Xie Wei.Deadbeat direct power control of three-phase pulse-width modulation rectifiers[J].IET Power Electronics,2014,7(6): 1340-1346.   
[4] Zhang Yongchang,Li Zhengxi.A novel threevectors-based predictive direct power control of doubly fed induction generator for wind energy applications[C]. Energy Conversion Congress & Exposition,2012: 793-800.   
[5] 殷振环．PWM整流器直接功率控制的研究[D]. 北京：北京交通大学，2009.   
[6] Samir Kouro,Ulrich Ammann.Model predictive control—a simple and powerful method to control power converters[J].IEEE Transactions on Industrial Electronics,2009,56(6):1826-1838.