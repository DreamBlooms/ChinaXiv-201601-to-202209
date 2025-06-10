# 电压型PWM整流器无模型预测电流控制

张永昌 焦健刘杰

（北方工业大学电力电子与电气传动北京市工程研究中心北京100144）

![](images/4ae2a5377bc9ac281c8adead62b6d9fbb63038af80425fc0aab5ff9f74f60986.jpg)

张永昌男 1982年生，博士，研究员，主要研究方向为模型预测控制在电力电子与电机控制中的应用。

摘要：模型预测控制近年来在电压型PWM整流器上得到深入研究，具有原理简单、动态响应快、易于实现等优点，其不足之处是计算量大且需要精确的系统模型和系统参数。通过分析PWM整流器模型，结合预测控制算法与快速矢量选择，得到直接电流控制方法。该方法可通过一次预测计算和比较得到当前时刻使得控制效果最好的一个矢量，简化后得到无模型预测电流控制，其特点是每个控制周期内仅需对电网电流进行一次采样，不依赖于整流器模型和参数。该方法鲁棒性强且动态、稳态性能良好。本文从稳态、动态性能和鲁棒性等方面对直接电流控制和无模型预测电流控制进行了对比，实验结果证明了两种方法的正确性和有效性。

关键词：PWM整流器 直接电流控制无模型预测电流控制 鲁棒性中图分类号：TM46

# Model-Free Predictive Current Control of the Voltage Source PWM Rectifier

![](images/f474bfb6a7da980106c9e52dd196c31d49a3cad9ef240bd8f0e69c3586498e09.jpg)

Zhang YongchangJiao Jian Liu Jie (Power Electronics and Motor Drive Engineering Research Center of Beijing North China University of TechnologyBeijing100144China ）

焦健男1993年生，硕士研究生，主要研究方向为双馈电机及PWM整流器模型预测控制。

Abstract: Model predictive control in voltage source PWM rectifier has been extensively studied for many years,which has several advantages such as simple principle, fast dynamic response and easy implementation. However, it poses high computational burden and requires the accurate system model and parameters. By analyzing the mathematical model of PWM rectifier,and combining prediction control and fast vector selection,a direct current control (DCC) is obtained. This method can select the optimal vector through only one prediction and comparison. Then the proposed DCC can be simplified into a new model-free predictive current control (MFPCC), which is characterized by sampling the grid current only once in each control cycle and is independent of the rectifier model and parameters.This method has strong robustness and good dynamic and steady state performance.A comparative study between DCC and MFPCC is carried out in terms of steady state performance,dynamic response and robustness.Finally, the correctness and effectiveness of those methods is experimentally validated.

Keywords: PWM rectifier, direct current control, model-free predictive current control, robustness

# 1 引言

三相电压型PWM整流器具有能量双向流动、直流电压输出恒定、网侧电流谐波低和功率因数可控等一系列优良的性能，被广泛应用于电机调速、新能源并网发电、功率因数校正等领域[1]。PWM整流器的控制方法主要包括电压定向矢量控制(Voltage Oriented Control，VOC）[2]、模型预测控制（Model PredictiveControl，MPC）[3]和直接功率控制（Direct Power Control，DPC）[4]。其中模型预测控制原理简单、动态响应快、容易实现，最近成为PWM整流器的研究热点。

MPC根据受控变量的区别可以分为预测功率控制（Predictive Power Control，PPC）[5-6]和预测电流控 制（Predictive Current Control，PCC）[7-8]。PWM整流器网测电流可测，电流预测控制相比于功率预测控制更为直接，这使得PCC 成为一个重要的研究方向。传统PCC基于PWM整流器离散模型和测得的电网电流值计算得到下一时刻的电流，然后枚举电压矢量使得目标函数最小，从而选出最优电压矢量，这种方法的缺点在于计算量过大，以及最终实现过程中考虑一步延时补偿[后会进一步加重算法的计算负担。

基于PWM整流器离散模型，本文得出一种直接电流控制（DirectCurrentControl，DCC）方法。该方法在一次预测计算后可以得到当前时刻最优的非零矢量，与零矢量作用效果进行比较后得到最优作用矢量。该方法仅包括一次预测和比较环节，与传统的预测电流控制对比而言，计算量降低，却仍然具有出色的控制性能。

直接电流控制的基础是PWM整流器的离散数学模型，所以预测过程中需要准确的参数。当电感参数发生变化时，控制效果会受到很大影响。为了增强这种直接电流控制算法的鲁棒性，文献[10]基于永磁同步电机提出一种无模型预测电流控制，该方法采用上一时刻的电流差分和当前时刻的采样电流来预测下一时刻电流，无需任何系统参数，具有很强的鲁棒性，通过在永磁电机上进行实验验证了其有效性。该方法主要缺陷在于每个周期内都要对电流二次采样，控制周期初始时刻采样一次，延时一段时间后再采样一次。这种采样方式增加了硬件采样次数和软件实现的难度。当控制周期大小改变或者程序执行时间变化时，电流采样时刻也需要相应地做出调整，从而使得这种控制算法应用不方便。另外，该方法的缺陷还表现在控制算法只在三相静止坐标系下实现，电流差分数据会占用较大存储空间。针对PWM整流器，本文在文献[10]的基础上提出了一种改进的无模型预测电流控制(Model-Free Predictive Current Control，MFPCC），该方法只需在每个控制周期对电流采样一次，降低了计算量。事实上，由于采样频率高，单次电流采样即可实现电流差分的计算，从而简化了算法。不同于文献[10]，本文提出的MFPCC是基于两相静止坐标系，只需较小的数组来存储电流差分值，从而减小计算量，方便数字实现。利用搭建的基于TMS320F28335DSP的两电平PWM整流器实验平台进行了相关实验，对比了DCC和MFPCC两种方法的动态、稳态性能和参数鲁棒性，结果表明以上方法原理正确，具有较好的控制性能。

# 2 直接电流控制

# 2.1预测电流计算

三相电压型PWM整流器电路如图1所示，电网侧的各相交流电压分别为 $e _ { \mathrm { a } }$ 、 $e _ { \mathrm { b } }$ 和 $e _ { \mathrm { c } }$ . $L$ 和 $R$ 表示交流侧电抗器的等效电感和电阻。

利用式（1）将三相静止坐标系变换至两相静止坐标系，即

$$
\pmb { x } = 2 \big ( x _ { \mathrm { a } } + \mathrm { e } ^ { \mathrm { i } 2 \pi / 3 } x _ { \mathrm { b } } + \mathrm { e } ^ { - \mathrm { j } 2 \pi / 3 } x _ { \mathrm { c } } \big ) / 3
$$

![](images/0a38c08114ec23d2593a7feef4c946e3ce8b27f028fad019b6504d16c22458eb.jpg)  
图1三相电压型PWM整流器电路  
Fig.1Main circuit of three-phase voltage source PWM rectifier

其中， $x$ 为两相坐标系下的复矢量。

将整流器模型中的各个电量按式（1）变换到两相坐标系下，则三相PWM整流器模型可以表示为

$$
e = R i + L { \frac { \mathrm { d } i } { \mathrm { d } t } } + \nu
$$

式中， $e$ 为网侧电压复矢量； $i$ 为网测电流复矢量；

$\nu$ 为整流器交流侧输出电压复矢量。

式（2）中包含的 $\mathrm { d } i / \mathrm { d } t$ 可以采用一阶欧拉离散法进行离散化，得

$$
\frac { \mathrm { d } i } { \mathrm { d } t } { \approx } \frac { i ^ { k + 1 } - i ^ { k } } { T _ { \mathrm { { s c } } } }
$$

将式（3）代入式（2）进行离散化，得

$$
{ \dot { \pmb { i } } } ^ { k + 1 } = \left( 1 - { \frac { R T _ { \mathrm { s c } } } { L } } \right) { \dot { \pmb { i } } } ^ { k } + { \frac { T _ { \mathrm { s c } } } { L } } ( { \pmb { e } } ^ { k } - { \pmb { \nu } } ^ { k } )
$$

根据式 (4)，利用 $k$ 时刻采样得到的网侧电压$e ^ { k }$ 、网测电流 $i ^ { k }$ 和整流器交流侧电压 $\boldsymbol { \nu } ^ { k }$ 可以计算出$k + 1$ 时刻的电网电流预测值 $\boldsymbol { i } ^ { k + 1 }$

利用采样得到的电网电压 $\boldsymbol { \mathscr { e } }$ 和网测电流 $i$ 可以计算出网侧复功率 $\pmb { S } ^ { [ 1 1 ] }$ ，即

$$
S = P + \mathrm { j } Q = 1 . 5 ( i ^ { ^ { * } } e )
$$

其中，“\*”表示共轭。

$$
\boldsymbol { i } ^ { \mathrm { r e f } } = \frac { 2 } { 3 } \left( \frac { \boldsymbol { S } ^ { \mathrm { r e f } } } { e } \right) ^ { * }
$$

# 2.2选取最优作用矢量

两电平电压型PWM整流器可以输出8种电压空间矢量，对应表示8种开关状态。其中有6种非零作用矢量 $\left( \pmb { u } _ { 1 } , \pmb { u } _ { 2 } , \cdots , \pmb { u } _ { 6 } \right)$ 和两种零矢量 $\left( { \pmb u } _ { 0 } , { \pmb u } _ { 7 } \right)$ 。传统的模型预测电流方法需要枚举8次，计算量大，本文提出一种快速的矢量选择方法。

由式（4）电网电流预测可改写为

$$
\pmb { i } ^ { k + 1 } = \pmb { i } _ { 0 } ^ { k + 1 } - \frac { T _ { \mathrm { s c } } } { L } \pmb { \nu } ^ { k }
$$

其中

$$
{ \pmb { i } } _ { 0 } ^ { k + 1 } = \left( 1 - \frac { R T _ { \mathrm { s c } } } { L } \right) { \pmb { i } } ^ { k } + \frac { T _ { \mathrm { s c } } } { L } { \pmb { e } } ^ { k }
$$

式中， $\pmb { i } _ { 0 } ^ { k + 1 }$ 为零矢量作用时的预测电流。

式（7）表明预测电流 $\pmb { i } ^ { k + 1 }$ 可以用 $\pmb { i } _ { 0 } ^ { k + 1 }$ 和 $\boldsymbol { \nu } ^ { k }$ 表示。

参考电流与预测电流之间的误差矢量可以表示为

其中，由零矢量产生的误差矢量为

$$
\pmb { \varepsilon } _ { 0 } ^ { k + 1 } = \pmb { i } ^ { \mathrm { r e f } ^ { k + 1 } } - \pmb { i } _ { 0 } ^ { k + 1 }
$$

如图2所示，若误差矢量 $- \mathbf { \delta } \mathbf { \delta } \mathbf { \delta } \mathbf { \delta } \mathbf { \delta }$ 在图中的阴影区域中，则矢量 $\pmb { u } _ { 1 }$ 导致的误差矢量的幅值最小，可以判定 $\pmb { u } _ { 1 }$ 为当前时刻可以选出的最优非零矢量；将该矢量代入式（7）中可得 $\pmb { u } _ { 1 }$ 作用下的电流误差矢量 $\pmb { \varepsilon } _ { 1 } ^ { k + 1 }$ ；分别得到 $\vert \pmb { \varepsilon } _ { 0 } ^ { k + 1 } \vert$ 和 $\vert \pmb { \varepsilon } _ { 1 } ^ { k + 1 } \vert$ 的大小后，如果 $\vert \pmb { \varepsilon } _ { 0 } ^ { k + 1 } \vert > \vert \pmb { \varepsilon } _ { 1 } ^ { k + 1 } \vert$ ，那么最优电压矢量是非零矢量 $\pmb { u } _ { 1 }$ ，如果 $| \pmb { \varepsilon } _ { 0 } ^ { k + 1 } | < | \pmb { \varepsilon } _ { 1 } ^ { k + 1 } |$ ，那么最优电压矢量为零矢量，如果最终得到的最优矢量是零矢量，那么需要遵循当前时刻开关动作次数最小的原则，考虑上一时刻作用的矢量，选取使得作用后开关次数较少的那个零矢量作为要发出的矢量。

根据式（5）得电流参考值 $i ^ { \mathrm { r e f } }$ 为

$$
\pmb { \varepsilon } _ { \nu } ^ { k + 1 } = \pmb { i } ^ { \mathrm { r e f } ^ { k + 1 } } - \pmb { i } ^ { k + 1 } = \pmb { \varepsilon } _ { 0 } ^ { k + 1 } + \frac { T _ { \mathrm { s c } } } { L } \pmb { \nu } ^ { k }
$$

![](images/977e1ef1cf81df502033a4081f47a77199b5c3df12ede18d17a1f9f4d339c319.jpg)  
图2快速矢量选择示意图  
Fig.2Diagram of fast vector selection

# 2.3一拍延时补偿

$k$ 时刻采样获得的电流 $\pmb { i } ^ { k }$ 后，数字信号处理会进行一段时间，选出的电压矢量 $\pmb { u } _ { k }$ 只能作用于 $k + 1$ 时刻。这将导致额外的功率脉动，为实现对电流的精确控制，需要采用提前预测一步的方法解决控制延时问题。具体过程为 $k$ 时刻预测 $k + 1$ 时刻的网测电流 $\pmb { i } ^ { k + 1 }$ ，利用预测得到的电流值结合快速矢量选择选出 $k + 1$ 时刻需要发出的最优电压矢量。加入一拍延时补偿后，式（10）改写为

$$
{ \pmb \varepsilon } _ { 0 } ^ { k + 2 } = \pmb { i } ^ { \mathrm { r e f } ^ { k + 2 } } - \pmb { i } _ { 0 } ^ { k + 2 }
$$

其中

$$
{ \pmb i } _ { 0 } ^ { k + 2 } = \left( 1 - \frac { R T _ { \mathrm { s c } } } { L } \right) { \pmb i } ^ { k + 1 } + \frac { T _ { \mathrm { s c } } } { L } { \pmb e } ^ { k + 1 }
$$

# 3 无模型预测电流控制

因为每个控制周期只选出一个要作用的电压矢量，所以无模型预测电流控制在理论上可以实现，并且根据当前采样的电流和电流差分来预测下一时刻的电流。因为系统控制周期较短，在每个控制周期中，考虑网测电流仅存在线性变化。基于这种考虑，每个周期的电流差分可以精确计算。在实际系统中，电压跳变和死区对采样精度有影响，为了得到更准确的电流差分，文献[10]中提出的无模型预测电流控制中，一个控制周期内对电流进行两次采样，之后预测电流差分值，这种方法增加了硬件采样次数和软件实现的难度，同时增加了计算负担，而且有可能导致检测到电流尖峰。为了避免出现这种情况，通常的做法是电压矢量作用后延迟一段时间进行第二次电流采样。然而延时时间需要靠经验来调试，不利于此方法的推广。

本文采用单次电流采样方法，即在每个控制周期内仅采样一次电流。由于每个控制周期开始时刻的采样值也是上个周期结束时刻的采样值，完全可以实现相同的效果。因为需要考虑一拍延时造成的影响，当前 $k$ 时刻应该对 $k + 2$ 时刻的网测电流进行预测，如图3所示，可以得到 $k + 2$ 时刻的电流为

![](images/bdef47edcad261d4b051307c0b3be6a2e7b029a08fe7cc169d5579bce62963ec.jpg)  
图3无模型预测电流控制电流预测示意图Fig.3Diagram of current prediction in MFPCC

$$
\pmb { i } ^ { k + 2 } = \pmb { i } ^ { k } + \Delta \pmb { i } ^ { k } ( \pmb { u } ^ { k } ) + \Delta \pmb { i } ^ { k + 1 } ( \pmb { u } _ { x } )
$$

其中

$$
\begin{array} { l } { { \Delta { { \dot { t } } ^ { k } } \left( { { \pmb u } ^ { k } } \right) = { { \dot { t } } ^ { k + 1 } } - { { \dot { t } } ^ { k } } } } \\ { { \Delta { { \dot { t } } ^ { k } } \left( { { \pmb u } _ { x } } \right) = { { \dot { t } } ^ { k + 2 } } - { { \dot { t } } ^ { k + 1 } } } } \end{array}
$$

式中， $\Delta i ^ { k } ( u ^ { k } )$ 为 $k \sim k + 1$ 时刻之间 $\pmb { u } ^ { k }$ 作用下的电流差分矢量； $\Delta { { i } ^ { k } } ^ { + 1 } ( { { u } _ { x } } )$ 为 $k + 1 \sim k + 2$ 时刻之间 $\pmb { u } _ { x }$ 作用下的电流差分矢量。可以看到， $k + 2$ 时刻的预测电流无需任何整流器参数。

由式（13）可知，在 $k$ 时刻无法计算得到 $\Delta i ^ { k }$ 和 $\Delta \boldsymbol { i } ^ { k + 1 }$ 值，因为它们分别是在 $k + 1$ 和 $k + 2$ 时刻进行计算的。预测控制的基本思想是根据系统现在和过去的信息来预测未来的信息。如果采样间隔足够短，现在和过去的电流差分可以直接用来预测下一时刻的电流，换句话说， $\Delta \boldsymbol { i } ^ { k }$ 和 $\Delta \mathfrak { i } ^ { k ^ { + 1 } }$ 可以用之前存储的电流差分矢量来近似，则 $\Delta \pmb { i } ^ { k }$ 和 $| \Delta \mathfrak { i } ^ { k ^ { + 1 } }$ 可表示为

$$
{ { \Delta } { \dot { \pmb { i } } } ^ { k } } \approx \Delta { { \dot { \pmb { i } } } _ { \mathrm { { o l d } } } ^ { i } } \Big | _ { S _ { i } = S _ { k } } \quad { \dot { \imath } } = 0 , \cdots , 7
$$

$$
\Delta \pmb { i } ^ { k + 1 } \approx \Delta \pmb { i } _ { \mathrm { o l d } } ^ { j } \Big | _ { S _ { j } = S _ { k + 1 } } \quad j = 0 , \cdots , 7
$$

式中， $\Delta \boldsymbol { i } _ { \mathrm { o l d } } ^ { i } \big | _ { S _ { i } = S _ { k } }$ ， $\Delta \pmb { i } _ { \mathrm { o l d } } ^ { j } \big | _ { S _ { j } = S _ { k + 1 } }$ 为过去时刻电压矢量 $\boldsymbol { S } _ { i }$ 和$S _ { j }$ 作用下的电流差分。将式（16）、式（17）代入式(13)，得到 $k + 2$ 时刻的电流为

$$
\pmb { i } ^ { k + 2 } = \pmb { i } ^ { k } + \Delta \pmb { i } _ { \mathrm { o l d } } ^ { i } \bigg | _ { S _ { i } = S _ { k } } + \Delta \pmb { i } _ { \mathrm { o l d } } ^ { j } \bigg | _ { S _ { j } = S _ { k + 1 } }
$$

由式（18）可知， $k + 2$ 时刻的预测电流只取决于当前时刻的电流和电流差分。为了更准确地近似$\Delta i ^ { k }$ 和 $\Delta \boldsymbol { i } ^ { k + 1 }$ ，在每个采样周期内，以前存储的电流差分应该被新的计算值更新。不同电压矢量电流差分的更新频率不一样，这可能会导致在某些电压矢量作用下的电流预测不精确，但是由于采样频率比较高，不同更新频率所带来的影响并不大。

定义目标函数

$$
g = \left| i ^ { \mathrm { r e f } } - i ^ { k + 2 } \right|
$$

将7个电压矢量代入式（18）、式（19）中，由式（19）中目标函数计算得到的值最小对应的电压矢量作为最终选出的矢量。

# 4 实验结果

# 4.1稳态性能

实际搭建了两电平PWM整流器样机对DCC和MFPCC控制策略进行实验验证。实验平台的实际架构如图4所示，控制板选用DSPTMS320F28335型控制器，为了方便观测内部变量，在控制板上增加了4通道DA。实验过程中，使用电流探头直接测出电流，剩余电量通过12位DA输出。整个系统包含的参数有：交流侧线电压有效值 $1 5 0 \mathrm { V }$ ，频率$5 0 \mathrm { { H z } }$ ，交流侧电感 $1 0 \mathrm { m H }$ ，直流母线电容 $8 4 0 \mu \mathrm { F }$ ，

![](images/e7d08358a912134d9a392e996b44c499de34c94996e3b1eb3840069583108e1d.jpg)  
图4PWM整流器实验平台实物图 Fig.4Experimental setup ofPWM rectifier

采样频率 $3 0 \mathrm { { k H z } }$ 。

为比较这两种方法的稳态性能，本文选取在母线电压开环、仅有功率闭环下进行分析。图5a和图5b分别为DCC和MFPCC在有功参考值 $1 \ 0 0 0 \mathrm { W }$ ，无功参考值0var的稳态波形。从上到下示波器的4路通道分别为有功功率参考值、实际有功和无功功率、交流侧A相电流。

![](images/53bcf5afcc4e557686fc25050c360293d7828ca49b753a4119ec2a7ed1e16a1b.jpg)  
图5DCC和MFPCC的稳态响应  
Fig.5Steady state response for DCC and MFPCC

图5表明，DCC的稳态性能比MFPCC的差，有功脉动和无功脉动较大。进一步量化分析，通过计算0.1s内有功功率和无功功率的均方差得到DCC的有功脉动为33.4985W，无功脉动为31.6836var，其A相电流THD为 $2 . 2 0 0 ~ 8 \%$ ；MFPCC方法中有功脉动为 $2 0 . 9 6 3 \ 2 \mathrm { W }$ ，无功脉动为22.0266var，其A相电流THD为 $1 . 9 3 3 4 \%$ ，这表明MFPCC稳态性能优于DCC。

# 4.2动态性能

图6a和图6b分别为PWM整流器采用DCC和MFPCC时有功功率从 $6 0 0 \mathrm { W }$ 阶跃到 $1 \ 0 0 0 \mathrm { W }$ 的实验波形。从图6可以看出，两种方法动态性能相似，实际有功快速跟踪参考值且无超调。证明DCC和MFPCC具有类似的优异动态性能。

# 4.3鲁棒性

图7a和图7b分别为DCC和MFPCC两种方法在有功参考值 $1 \ 0 0 0 \mathrm { W }$ 和无功参考值0var稳态时，模型电感值由 $1 0 \mathrm { m H }$ 变化到 $5 \mathrm { m H }$ 的波形。由上述分析可知，两种方法具有相似的稳态性能，但电感变化时DCC的有功和无功功率脉动均增大，而MFPCC功率脉动保持恒定，呈现出较强的参数鲁棒性，其原因是MFPCC本身不依赖于系统参数。

![](images/f554eacfa703d0fecee1dbeff256f912ac502ffd85eae7cf19ba06b2f79cc3aa.jpg)  
图6DCC和MFPCC的有功功率阶跃响应

![](images/eed8f930df28d9c41623d236d483a650f3947d2a531d4f9a9cfa9a412c7aefdb.jpg)  
Fig.6Step responses of active power in DCC and MFPCC   
图7电感变化时DCC和MFPCC的稳态响应 Fig.7Steady state response for DCC and MFPCC when the inductance varies

图8为在模型电感分别等于 $1 0 \mathrm { m H }$ 和 $5 \mathrm { m H }$ 时

DCC 和MFPCC的有功脉动、无功脉动和THD对比。

![](images/1e7621b691fa3054fa38a46d6564d488c6882bfbb9f301aac068dc4f5f1d5d6b.jpg)  
图8DCC和MFPCC的有功脉动、无功脉动和THD对比图  
Fig.8Comparisons of active power ripple，reactive power ripple and current THD for DCC and MFPCC

从图7和图8可知，相比DCC，MFPCC有更 强的参数鲁棒性。

# 5 结论

本文首先提出了一种直接电流控制方法，利用预测计算得到的电流矢量及其矢量误差比较获得最终要选取的矢量，因为整个过程仅需要一次预测和一次比较，与传统直接电流控制相比，计算量和复杂程度都得到了减小。然后提出一种无模型预测电流控制方法，这种方法在一个周期中采样一次网测电流，无需整流器参数即可获得最终要选取的最优电压矢量，鲁棒性强，相较于所提出的直接电流控制方法更容易实现。两电平PWM整流器样机的实验结果表明，在理想参数情况下，DCC稳态时的有功脉动、无功脉动和电流THD均大于MFPCC，说明MFPCC稳态性能优于DCC，动态时二者的性能十分相似。考虑到MFPCC有较强的参数鲁棒性，因此在实际系统中MFPCC有较大的实用价值。

# 参考文献

[1] Rodriguez J,Dixon J,Espinoza J,et al. PWM regenerative rectifiers:state of the art[J].IEEE Transactions on Industrial Electronics,20o5,52(1): 5-22.

[2] Blasko V, Kaura V.A new mathematical model and control of a three-phase AC-DC voltage source converter[J]. IEEE Transactions on Power Electronics, 1997, 12(1): 116-123.   
[3] Cortes P, Rodriguez J,Antoniewicz P, et al. Direct power control of an AFE using predictive control[J]. IEEE Transactions on Power Electronics,2008, 23(5): 2516-2523.   
[4] Noguchi T, Tomiki H, Kondo S,et al. Direct power control of PWM converter without power-source voltage sensors[J]. IEEE Transactions on Industry Application, 1998, 34(3): 473-479.   
[5] Zhang Y, Xie W. Low complexity model predictive control-single vector-based approach[J]. IEEE Transactions on Power Electronics,2014,29(10): 5532-5541.   
[6] Zhang Y, Xie W, Li Z, et al. Model predictive direct power control of a PWM rectifier with duty cycle optimization[J]. IEEE Transactions on Industry Electronics,2013,28(11): 5343-5351.   
[7] Jeong S G, Woo M H. DSP-based active power filter with predictive current control[J]. IEEE Transactions on Industry Electronics,1997,44(3): 329-336.   
[8] Morel F, Linshi X, Retif JM, et al.A comparative study of predictive current control schemes for a permanent magnet synchronous machine drive[J]. IEEE Transactions on Industrial Electronics,2009, 56(7): 2715-2728.   
[9] Cortes P, Rodriguez J, Silva C,et al. Delay compensation in model predictive current control of a three-phase inverter[J]. IEEE Transactions on Industrial Electronics,2012, 59(2):1323-1325.   
[10]Lin Chengkai, Liu Tianhua, Yu Jente, et al. Modelfree predictive current control for interior permanent magnet synchronous motor drives based on current difference detection technique[J]. IEEE Transactions on Industrial Electronics,2014,61(2): 667-681.   
[11]Akagi H, Kanazawa Y, Nabae A. Instantaneous reactive power compensators comprising switching devices without energy storage components[J]. IEEE Transactions on Industry Application,1984,20(3): 625-630.