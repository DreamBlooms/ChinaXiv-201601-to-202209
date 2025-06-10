彩色印刷(不需要)

# 再入飞行器流场热辐射输运解算方法库研究

王京盈‘ 郝佳傲² 杜广生1 李椿萱²(1．山东大学能源与动力工程学院， 济南 250061;2．北京航空航天大学航空科学与工程学院， 北京 100191)

摘要：基于若干热辐射输运求解方法的一维辐射平衡和温度间断算例结果的对比分析，提出了一个由离散坐标法、${ \bf P } _ { 1 }$ 近似和光学厚度极限近似构建的热辐射输运解算方法库，该方法库可与再入飞行器热化学非平衡流场控制方程实现有效耦合模拟。利用该方法库模拟了 $6 0 \mathrm { k m }$ 高空、马赫数35的球头算例，计算表明热辐射对高温流场具有显著的“冷却”作用；辐射传热与对流传热水平相当，流场非耦合热辐射计算的辐射热流将高出耦合计算值 $2 7 \%$ ，此类飞行条件下的数值模拟研究应当考虑热辐射耦合效应。

关键词：热辐射；高超声速；气动热；再入中图分类号：V211.3；O354.7 文献标识码：A

Thermal Radiation Solving Method Library for the Reentry Vehicle

# Flowfield Simulation

WANG Jing-Ying1 HAO Jia-Ao² DU Guang-Sheng' LEE Chun-Hian² (1. School of Energy and Power Engineering, Shandong University, Jinan250100，China; 2. School of Aeronautic Science and Engineering, Beihang University, Beijing 100191，China)

Abstract: Based on comparisons of the results of the one-dimensional radiation equilibrium and temperature discontinuity model cases,a thermal radiation solving method library consisting of the discrete ordinates method, ${ \bf P } _ { 1 }$ approximation,and the optically limiting approximation is proposed. The library can achieve the effective coupled simulation with equations describing the thermo-chemical nonequilibrium flow over the reentry vehicle.In the $6 0 ~ \mathrm { k m }$ altitude and Mach number 35 sphere model case,it is found that the thermal radiation can ‘cool’ the high temperature shock layer remarkably. It is also demonstrated that the radiative heating is comparable to the convective heating, and the radiative heating of the simulation uncoupled with the radiation overestimates $2 7 \%$ of the coupled value,which illustrates that coupling effects of the radiation should be considered in corresponding research.

Key words: radiation; hypersonic; aerothermodynamics; reentry

# 0引言

应。Candler和Park[2]采用一维切平板公式求解热辐射输运，耦合热化学非平衡流场计算，给出AFE模型在近地点 $7 8 \mathrm { k m }$ 高空、 $9 \mathrm { k m / s }$ 速度的飞行状态下驻点辐射传热约 $\scriptstyle 1 6 \times 1 0 ^ { 4 } \ { \mathrm { W / m } } ^ { 2 }$ 。Feldick[3]分别利用一维切平板近似、蒙特卡洛模拟和 $| { \bf P } _ { 1 } - |$ 蒙特卡洛混合方法与DPLR(DataParallelLineRelaxation)程序结合，对MPCV(Multi-Purpose CrewVehicle)返回舱开展非平衡流场耦合热辐射模拟，发现切平板近似预测的辐射热流比蒙特卡洛模拟高估 $30 \%$ 。高铁锁等[4在光学厚度薄极限假设下沿空间路径积分发射系数获得辐射热流，高温流场通过求解化学非平衡N-S方程得到，认为再入热环境严酷区中返回舱辐射热流贡献高达总热流的 $30 \%$ 。

高速再入飞行器高温大气流场特性极为复杂，分子振动能激发和多组分化学反应等热化学非平衡过程与热辐射强烈耦合。此时飞行器气动加热预测，除考虑传导和对流作用外，必须计及热辐射耦合效

目前，国内外研究多采用单一的已有热辐射输运求解方法直接与流场数值格式开展耦合模拟。然而，现有高精度方法对热辐射在无穷维光谱和传播方向上的刻画，无疑会给耦合模拟带来庞大的运算量和存储量；而简化热辐射模型又存在预测精度不足的问题。因此，单一热辐射输运求解方法无法满足当前再入飞行器气动热环境高效模拟需求。本文基于一维热辐射输运模型算例分析，充分考虑再入飞行条件下流场的光学厚度和数值格式特征，构建了适用与再入飞行器热化学非平衡流场方程耦合模拟的热辐射输运解算方法库，并利用该方法库成功实现了Ma $= 3 5$ 再入飞行条件下球头算例的流场热辐射耦合模拟。

# 1 一维热辐射输运模型

采用统一的一维模型算例对现有若干热辐射输运求解方法开展对比分析，模型算例几何描述同文献[5]，示意见图1：两无穷大各向同性漫射平行壁面间充满参与性灰介质，介质热力学和辐射特性与温度无关。平行壁面间距 $L$ ，法向坐标y，光学厚度坐标 ${ \boldsymbol { \tau } } = _ { K \mathcal { Y } }$ ， $\kappa$ 为介质辐射吸收系数。壁面1、2的温度分别为 $T _ { w 1 }$ 、 $T _ { w 2 }$ ，发射率分别为 $\lvert \varepsilon _ { 1 }$ 、 $\varepsilon _ { 2 }$ 。辐射强度I与y轴方向夹角y，周向角 $\varphi$ 。该模型具有一维轴对称性质，不妨取等间隔空间离散，离散点总数目$N { + } 1$ ，物理间隔 $\Delta y { } = L / N _ { \cdot }$ ，光学厚度间隔 $\Delta \tau { = } \tau _ { L } / N _ { \circ }$

# 2各方法的一维模型算例对比分析

选取目前研究中常用的多种热辐射输运求解方法进行一维模型算例对比分析研究。本文考察的方法有切平板近似(Tangent Slab Approximation)、蒙特卡洛模拟(Monte Carlo Method)、离散坐标法(DiscreteOrdinatesMethod）、 ${ \bf P } _ { 1 }$ 近似 $( \mathrm { P } _ { 1 }$ Approximation)以及两种光学厚度极限近似方法：光学薄近似(Optically Thin Approximation)和光学厚近似(Optically ThickApproximation)。切平板近似实际上是热辐射输运方程的一维积分解析解，对于图1所示情形，切平板近似有辐射热流：

$$
q _ { r } \left( \tau \right) = 2 \left[ J _ { 1 } E _ { 3 } \left( \tau \right) - J _ { 2 } E _ { 3 } \left( \tau _ { L } - \tau \right) \right]
$$

$$
+ 2 \sigma \biggl [ \int _ { 0 } ^ { \tau } T ^ { 4 } \left( t \right) E _ { 2 } \left( \tau - t \right) d t - \int _ { \tau } ^ { \tau _ { L } } T ^ { 4 } \left( t \right) E _ { 2 } \left( t - \tau \right) d t \biggr ]
$$

其中T表示温度， $E _ { 2 }$ 和 $\dot { E } _ { 3 }$ 分别为二阶和三阶且指数积分函数，且有

$$
\left\{ \begin{array} { l l } { { { J } _ { { 1 } } } = { { \varepsilon } _ { 1 } } \sigma T _ { { w } 1 } ^ { 4 } } \\ { \quad \ + 2 \left( 1 - { { \varepsilon } _ { 1 } } \right) \left[ { { J } _ { { 2 } } } { { E } _ { 3 } } \left( { { { \tau } _ { L } } } \right) + \sigma \int _ { 0 } ^ { { { \tau } _ { L } } } { { { T } ^ { 4 } } \left( t \right) { { E } _ { 2 } } \left( t \right) d t } \right] } \\ { { { J } _ { { 2 } } } = { { \varepsilon } _ { 2 } } \sigma T _ { { w } 2 } ^ { 4 } } \\ { \quad \ + 2 \left( 1 - { { \varepsilon } _ { 2 } } \right) \left[ { { J } _ { { 1 } } } { { E } _ { 3 } } \left( { { { \tau } _ { L } } } \right) + \sigma \int _ { 0 } ^ { { { \tau } _ { L } } } { { { T } ^ { 4 } } \left( t \right) { { E } _ { 2 } } \left( { { { \tau } _ { L } } } - t \right) d t } \right] } \end{array} \right.
$$

蒙特卡洛模拟结果在样本量足够大时亦可认为是热辐射输运的准确解[]，因此本文一维算例模拟可以切平板近似和蒙特卡洛模拟的结果作基准。光学薄近似一般要求特征光学厚度 $\tau _ { L } < < 1$ ，而光学厚近似则要求 $\tau _ { L } \ > > 1$ 。各方法的具体原理和详细表达可参见文献[6]和[7]。本文通过FORTRAN自编程实现上述各方法计算。

![](images/c9f1409865967afbb2867dd4e27a423de8dea54602d9671bc45a7082a6c031a1.jpg)  
图1一维热辐射输运模型几何示意图  
Fig.1Sketch of one-dimensional radiative transfer model

# 2. 1 辐射平衡

假定图1中两壁面间介质辐射平衡，辐射热流 $\boldsymbol { \cdot } \boldsymbol { q } _ { r }$ 空间梯度为零，即 $d q _ { r } / d y = 0 \ \mathrm { W } / \mathrm { m } ^ { 3 }$ ；取壁面温度 $T _ { w 1 }$ $_ { \mathrm { = } 1 0 0 0 \mathrm { ~ K ~ } }$ ， $T _ { w 2 } = 7 0 0 ~ \mathrm { K }$ ，发射率 ${ \varepsilon _ { 1 } } = { \varepsilon _ { 2 } } = 1 . 0$ ，分别计算 $_ { \cdot \kappa = 0 . 7 }$ 、1.5、 $3 . 0 \mathrm { m } ^ { - 1 }$ 的工况。取 $L { = } 1 . 0 \mathrm { m }$ 。定义无量纲辐射热流：

$$
\hat { q } _ { r } = \frac { q _ { r } } { \sigma \Big ( T _ { w 1 } ^ { 4 } - T _ { w 2 } ^ { 4 } \Big ) }
$$

为确定离散点数目 $N$ ，针对基准方法切平板近似开展网格无关性计算，结果如图2所示。图2说明，离散网格点数目 $N { > } 3 0$ 时，切平板近似的辐射热流值基本稳定，同时无量纲温度分布数据也不再随网格加密而变化。因此，本文一维算例的 $N$ 取值均大于30，以保证切平板近似方法计算的准确性。本节辐射平衡算例取 $N { = } 5 0$ 。

![](images/17cb7a5d0ffa3f5d22e9f2cf0f830810891b043eb8a14ebfe13b2d74a6c07003.jpg)  
图2切平板近似网格无关性计算：(a)无量纲热流,(b）无量纲温度分布

图3展示了本节辐射平衡算例各方法的温度分布结果。离散坐标法(DOM)与基准方法切平板近似(TSA)以及蒙特卡洛模拟(MC)的温度值几乎一致，${ \bf P } _ { 1 }$ 近似 $\left( \mathsf { P } _ { 1 } \right)$ 计算值也与基准解接近。光学薄近似(THIN)的温度为固定值，而光学厚近似(THICK)同切平板近似的数据也存在很大差异，但随着总光学厚度值 $\tau _ { L }$ 增大，光学厚近似预测效果会逐渐改善。

![](images/9f3d83f3c12f661ee854f75088a6ff4a0514625ca69ce9f77832987ed51c4c23.jpg)  
Fig.2Grid independent simulation for tangent slab approximation: (a) nondimensional radiative heat transfer, (b) distribution of nondimensional temperature

![](images/1adc885cba1b9660c1d34178b266b035a6fa24ce2ace8aa3b5284f86abc5b7d8.jpg)  
图3一维辐射平衡问题各方法温度分布结果 Fig.3Temperature distributions of one-dimensional radiative equilibriumcalculated by different methods

各方法的无量纲辐射热流结果见表1，表中误差为以切平板近似热流值为基准计算的相对误差。切平板近似与蒙特卡洛模拟两类基准方法的差异极小，离散坐标法对辐射热流预测精度很高，而 ${ \bf P } _ { 1 }$ 近似的辐射热流误差均在 $5 \%$ 以内，但两种光学厚度极限近似的热流值误差均很大。

# 表1各方法无量纲平衡辐射热流值对比

Table 1 Comparison of non-dimensional equilibrium radiative heat fluxes calculated by different methods   

<html><body><table><tr><td>Method</td><td>TL = 0.7</td><td>Error</td><td>TL =1.5</td><td>Error</td><td>T=3.0</td><td>Error</td></tr><tr><td>TSA</td><td>0.634</td><td>0.000E+00</td><td>0.457</td><td>0.000E+00</td><td>0.301</td><td>0.000E+00</td></tr><tr><td>MC</td><td>0.634</td><td>8.883E-06</td><td>0.457</td><td>1.734E-04</td><td>0.302</td><td>6.968E-04</td></tr><tr><td>DOM</td><td>0.635</td><td>7.150E-04</td><td>0.458</td><td>1.304E-03</td><td>0.302</td><td>2.978E-03</td></tr><tr><td>P1</td><td>0.656</td><td>3.369E-02</td><td>0.471</td><td>2.915E-02</td><td>0.308</td><td>2.077E-02</td></tr><tr><td>THIN</td><td>1.000</td><td>5.764E-01</td><td>1.000</td><td>1.187E+00</td><td>1.000</td><td>2.318E+00</td></tr><tr><td>THICK</td><td>1.905</td><td>2.003E+00</td><td>0.889</td><td>9.440E-01</td><td>0.444</td><td>4.744E-01</td></tr></table></body></html>

# 2.2 温度间断

仿照再入飞行器高温激波层流场，设计温度间断算例：两壁面间介质温度分为均匀两层，分段位置 $y / L = 0 . 3$ ，近壁面1处为高温层，温度与壁温 $T _ { w 1 }$ 同为 $1 0 0 0 0 \mathrm { ~ K ~ }$ ；近壁面2处为低温层，温度与壁温

$T _ { w 2 }$ 均为 $3 0 0 \mathrm { K }$ 。分别计算 $\kappa { = } 0 . 0 1 , \ 0 . 1 , \ 1 . 0 , \ 5 . 0 \ \mathrm { m } ^ { - 1 }$ 的工况。取 $L { = } 1 . 0 \mathrm { m }$ ， $N { = } 1 0 0 0$ 。定义无量纲辐射能量源项：

$$
\hat { \omega } _ { r } = - \frac { d q _ { r } / d y } { \kappa \sigma \Big ( T _ { w 1 } ^ { 4 } - T _ { w 2 } ^ { 4 } \Big ) }
$$

各方法无量纲辐射能量源项计算值见图4。所有光学厚度条件下，离散坐标法与基准方法切平板近似结果高度一致， ${ \bf P } _ { 1 }$ 近似稍有偏差。小光学厚度$\tau _ { L } ~ = 0 . 0 1$ 时，光学薄近似与切平板近似结果相近，但随 $\tau _ { L }$ 增大，逐渐失去合理性。光学厚近似辐射能量源项值始终为零。

3.0 o.o@i(l0i0i0ieiOlOl0i0id!il0l0i0ioiol -1.0 TSA DOM △i ： P -2.0 THIN O1 THICK -3.0 0.000 0.002 0.004 0.006 0.008 0.010 T (a) τ =0.01 3.0 +0-4-444-2-4-2 o.oill010i0iliolOi0i0i0|i0lO10i0ioliol -1.0 TSA DOM A = P -2.0 THIN THICK -3.0 0.00 0.02 0.04 0.06 0.08 0.10 T (b) t =0.1 3.0 s A A 4 中 + 二 o.oei0l010i0iei0l010i0ioli0l010i0ioiol 4 TSA 4 A DOM A A △i ： PHIN O1 THICK -3.0 0.0 0.2 0.4 0.6 0.8 1.0 T (c) $\tau _ { L } = 1 . 0$ （204号

![](images/3a9ecdf9f8782f64a53bfc58f9dd408827ead9dbe7fb45591a92b790d7164bd6.jpg)  
图4温度间断各方法无量纲辐射能量源项结果 Fig.4Non-dimensional radiative energy source terms of temperature discontinuity using different methods

$\tau _ { L } \ { = } 0 . 1$ 时各方法的无量纲辐射热流值见表2，表中误差仍是以切平板近似热流值为基准计算的相对误差。离散坐标法与切平板近似的辐射热流基本相同， ${ \bf P } _ { 1 }$ 近似也能给出正确值。此类小光学厚度条件，光学薄近似结果具有一定可靠性，但光学厚近似只能给出零热流结果。其他总光学厚度条件下，计算结果表现出类似特征。

表2 $\tau _ { L } \ = 0 . 1$ 各方法两壁面处无量纲辐射热流结果对比 Table 2Non-dimensional radiative heat transfers at two walls calculated by different methods with $\tau _ { L } = 0 . 1$   

<html><body><table><tr><td>Method</td><td>wall 1</td><td>Error</td><td>wall 2</td><td>Error</td></tr><tr><td>TSA</td><td>0.944</td><td>0.00E+00</td><td>0.878</td><td>0.00E+00</td></tr><tr><td>DOM</td><td>0.943</td><td>7.38E-04</td><td>0.876</td><td>1.45E-03</td></tr><tr><td>P1</td><td>0.963</td><td>2.05E-02</td><td>0.892</td><td>1.58E-02</td></tr><tr><td>THIN</td><td>1.000</td><td>5.93E-02</td><td>1.000</td><td>1.39E-01</td></tr><tr><td>THICK</td><td>0.000</td><td>1.00E+00</td><td>0.000</td><td>1.00E+00</td></tr></table></body></html>

# 3热辐射输运解算方法库

再入飞行器热化学非平衡流场耦合热辐射求解必然耗费更大的计算资源，由2节可知各类热辐射输运求解方法性能差异显著，单一方法难以满足耦合模拟需求[3]。本文提出如下解决思路：集成多种方法构建一个热辐射输运解算方法库，依特性、按需求并分阶段地选择库中方法执行热辐射耦合模拟。解算库中方法应满足：可准确预测辐射热流，尽量降低计算成本，能与流场数值格式协同求解，适合大规模并行计算。基于2节模型算例对比分析，同时考虑各方法程序求解执行过程，总结出各方法性能特点列于表3，表中预测精度主要针对辐射能量源项与辐射热流计算而言。

切平板近似是一维积分解析解，针对一维问题求解是精确的，但其只能沿一个维度路径积分，因而用于高维计算有失合理性，精度难以界定。蒙特卡洛模拟在样本量充足时可认为精确解，但会相应带来计算量的问题。离散坐标法在一维求解时与基准方法切平板近似和蒙特卡洛模拟结果高度一致，是基于完整的辐射传输方程的直接离散方法，且容易实现高维扩展。 ${ \bf P } _ { 1 }$ 近似求解的是简化的辐射传输方程，精度适中。光学薄和光学厚近似只有在极小（一般 $\tau _ { L } < 0 . 0 1 )$ 或极大光学厚度条件下才合理。

表3各类热辐射输运求解方法特点对比  

<html><body><table><tr><td colspan="6">radiative transfer</td></tr><tr><td>方法</td><td>预测精度</td><td>存储量</td><td>计算量级</td><td>高维扩展</td><td>并行化</td></tr><tr><td>TSA</td><td>仅一维精确</td><td>小</td><td>N²</td><td>复杂</td><td>可行 需大量传值</td></tr><tr><td>MCM</td><td>精确</td><td>很大</td><td>一般很大</td><td>容易</td><td>可行</td></tr><tr><td>DOM</td><td>高</td><td>适中</td><td>N×M</td><td>容易</td><td>容易 传值量适中</td></tr><tr><td>P1</td><td>适中</td><td>小</td><td>N</td><td>容易</td><td>容易 传值量小</td></tr><tr><td>THIN</td><td>接近光学厚度</td><td></td><td>很小</td><td></td><td>容易</td></tr><tr><td>THICK</td><td>极限条件时合理</td><td>小</td><td>无需循环</td><td>容易</td><td>传值量很小</td></tr></table></body></html>

在计算资源占用方面，切平板近似沿一维路径进行数值积分，存储量不大，但在各网格点处均要进行上、下游逐点积分，一轮计算需完成 $N ^ { 2 }$ 次代数运算，其中 $N$ 为离散网格点数，计算量相当可观。蒙特卡洛模拟需要追踪每个能束吸收和发射的历程，往往巨大的能束样本量会占用很大的存储资源和计算量。离散坐标法需要存储各角方向上的辐射强度，在每个网格点处需求解离散角方向数目 $M$ 个代数方程，需占用一定的存储和计算成本。 ${ \bf P } _ { 1 }$ 近似仅求解关于投射辐射(incidentradiation)的二阶微分方程，存储和计算量均不大。光学厚度极限近似由温度场直接显式计算辐射量，求解成本很低。表4列出了求解2节中辐射平衡算例各方法所消耗的CPU时间，其中蒙特卡洛模拟所需的能束样本量为100万个，离散坐标法考虑的角方向为10个。从表4中可以看出，各方法所耗费的实际计算时间与表3中的定性分析是一致的。切平板近似和蒙特卡洛会消耗大量计算时间，而离散坐标法和 ${ \bf P } _ { 1 }$ 近似计算效率较高，而光学厚度极限方法几乎不消耗时间。

除切平板近似难以推广至高维外，其余方法则易于扩展至高维情形。同时，切平板近似还会在并行求解过程时出现跨区域积分问题，需要各并行区域间进行大量传值。离散坐标法和 ${ \bf P } _ { 1 }$ 近似均是传递相邻区域交界处的热辐射相关量。光学厚度极限近似则只需传递相邻区域交界处温度值。

Table3 Characteristics of different methods solving   
表4辐射平衡算例各方法所消耗CPU时间(单位：s) Table 4 CPU time consumption of solving radiative equilibrium case by different methods (unit: s)   

<html><body><table><tr><td>Method</td><td>CPU time/s</td></tr><tr><td>TSA</td><td>8.7813</td></tr><tr><td>MC</td><td>10.7813</td></tr><tr><td>DOM</td><td>0.3906</td></tr><tr><td>P1</td><td>0.1719</td></tr><tr><td>THIN</td><td>0.0000</td></tr><tr><td>THICK</td><td>0.0000</td></tr></table></body></html>

综上，本文放弃不利于高维求解和并行处理的切平板近似与高计算成本的蒙特卡洛模拟。本文热辐射输运解算方法库最终选定由离散坐标法、 ${ \bf P } _ { 1 }$ 近似和光学厚度极限近似(含光学薄和光学厚近似)三类不同层次的方法构成。该方法库面对热辐射输运求解的一般执行原则为：与流场开展非耦合精确求解时直接选用离散坐标法；与流场进行耦合求解时，若流场的光学厚度满足极限条件，可先用光学厚度极限近似进行耦合模拟，收敛后转用离散坐标法以节约计算量；若不满足光学厚度极限条件，则先用${ \bf P } _ { 1 }$ 近似耦合求解，收敛后转用离散坐标法。上述使用原则如图5所示。

![](images/d3b4f4bd2de5d3d2fe0152513ac10c7faeaa7d2f7cd4b01086105bb4beaad39c.jpg)  
图5热辐射输运解算方法库操作原则  
Fig.5Operation procedures of the thermal radiation solving method library

# 4再入飞行算例耦合模拟演示

选取 $M a = 3 5$ 的 $R = 1 . 0 \mathrm { m }$ 球头模型开展再入飞行条件下高温流场与热辐射耦合模拟，演示本文构造的热辐射输运解算方法库与流场数值格式耦合求解的有效性。取自由来流密度 $\rho _ { \infty } { = } 3 . 1 { \times } 1 0 ^ { - 4 } \mathrm { k g / m } ^ { 3 }$ ，温度 $T _ { \infty } { = } 2 4 7 \mathrm { K }$ ，大气质量分数组成 $Y _ { \mathrm { N } 2 } = 0 . 7 7$ ， $Y _ { 0 2 }$ $\scriptstyle = 0 . 2 3$ ，上述取值对应 $6 0 \mathrm { k m }$ 高空地球大气参数。高温流场求解采用文献[8-10]中给出的数值格式，采用Park两温度热力学非平衡模型["和Gupta的11组分 20 反应化学反应动力学模型[12]。热辐射特性计算采用Anderson 两台阶模型[7]。壁温取 $T _ { w } = 1 0 0 0 ~ \mathrm { K }$ ，壁面发射率 $\varepsilon = 1 . 0$ ，取完全催化壁面条件。流场与热辐射耦合算法见文献[8]。流场求解和热辐射解算方法库均采用FORTRAN自编程实现。计算网格量$6 0 \times 7 0$ ，按照气动热预测需求，壁面法向第一层网格间距 $1 . 0 { \times } 1 0 ^ { - 6 } \mathrm { m } ^ { [ 1 3 ] }$ 。该球头模型计算量相对较小，因此流场耦合热辐射求解可直接采用解算方法库中高精度的离散坐标法开展。

图6给出了流场耦合热辐射计算的压强和温度分布，此时激波层很薄，激波脱体距离不到球头半径的1/15，波后驻点区域平动-转动温度和振动-电子温度均超过 $1 0 0 0 0 \mathrm { ~ K ~ }$ 。图7展示了流场内热辐射量分布结果，辐射能量源项和平均吸收系数分布形式完全对应于流场的温度分布。投射辐射最大值虽然分布在激波层内，但高投射辐射值分布也扩展到了激波上游来流，更具扩散性。

$\scriptstyle { M a = 3 5 }$ 飞行状态下，辐射能量源项已具有相当量级(约 $1 0 ^ { 8 } \ \mathrm { W / m } ^ { 3 } )$ ，热辐射对流场作用显著，但激波层的光学厚度仍然很小，不足0.005。因此，本文还采用了解算方法库中的光学薄近似与流场开展耦合计算。图8比较了流场非耦合热辐射(uncoupled)、耦合光学薄近似(coupled_thin)和耦合离散坐标法(coupleddom)的驻点线温度结果。与非耦合相比，耦合计算的激波层温度更低，激波层更薄，凸显了辐射冷却作用[7]。光学薄近似比离散坐标法耦合计算的辐射冷却效果更明显，原因在于光学薄近似忽略了辐射吸收作用，仅考虑辐射发射，辐射能量源项值更大，对流场作用更显著。

图9分别给出了流场非耦合热辐射与耦合光学薄近似和耦合离散坐标法计算的驻点线 $\mathrm { \Delta N ^ { + } }$ 和e质量分数分布。耦合计算给出的 $\mathrm { \Delta N ^ { + } }$ 和 $\mathrm { e } ^ { - }$ 的质量分数明显低于非耦合值，原因可能是辐射冷却作用抑制了电离反应。因此，高速再入飞行条件下高温大气化学反应和热辐射存在显著的耦合效应。还可以看到，光学薄近似耦合计算辐射冷却效果更显著，其 $\mathrm { ~ \bf ~ N ~ } ^ { + }$ 和 $\mathrm { ~ e ~ } ^ { - }$ 质量分数低于离散坐标法耦合计算值。

图10给出了流场非耦合热辐射与耦合光学薄近似和离散坐标法计算的驻点线热辐射量。耦合计算的热辐射量绝对值均小于非耦合值，光学薄极限近似耦合计算的热辐射量绝对值减弱更明显。

![](images/5e5a7ff6bc6c9f6c3526c28cf729b949d2f94f61b825c0b6265f77648356ff71.jpg)  
图6耦合热辐射的流场模拟结果：(a)压强(单位： $\mathrm { \ P a }$ ，(b)平动-转动温度(单位：K),(c)振动-电子温度(单位：K)Fig. 6Flowfield simulation results coupled with radiation: (a)pressure (unit: $\mathrm { P a }$ ),(b) translational-rotational temperature (unit:K),(c) vibrational-electronic temperature (unit: K)

表5给出了流场非耦合与耦合光学薄近似和离散坐标法计算给出的驻点对流热流 $( q _ { c } )$ 和辐射热流$( q _ { r } )$ 值。非耦合辐射热流值是在流场的收敛结果基础上，再以离散坐标法进行求解得到的；光学薄近似无法给出辐射热流值，其辐射热流同样是在耦合计算收敛后的流场基础上，以离散坐标法求解获得。由表5可知，非耦合与耦合热辐射给出的对流热流值接近，但非耦合给出的辐射热流明显高于耦合值，高出光学薄近似耦合结果 $48 \%$ ，高出离散坐标法耦合值 $2 7 \%$ ，光学薄近似耦合计算较离散坐标法耦合计算的辐射热流值低。此时，流场的辐射传热可与对流传热水平相当。因此，开展此类再入飞条件下气动热研究时，必须考虑流场的热辐射耦合效应。

![](images/cdf52852aabf3e4bd0324cd079cb665879b9db9c8aa01020c3539dd8e37212b5.jpg)

![](images/27e449644ea863ca571ffcc9116347772ee5a754fc6a0eaf6cc44d3a7eec57ab.jpg)  
图7流场中热辐射量分布:(a)辐射能量源项(单位: $\mathrm { W / m } ^ { 3 }$ ） (b）平均吸收系数(单位： $\mathrm { ~ m } ^ { - 1 }$ ),(c）投射辐射(单位： $\mathrm { W / m } ^ { 2 } ,$ Fig.7Contours of radiation variables ofcoupled radiation simulation:(a) radiation source (unit: $\mathrm { W / m } ^ { 3 }$ )，(b)total absorption coefficient (unit: $\mathbf { m } ^ { - 1 }$ ),(c) incident radiation (unit: （204   
图8流场非耦合与耦合热辐射计算的驻点线温度 Fig.8Temperature distributions along the stagnation line of uncoupled and coupled radiation simulations

![](images/fb5004465547d0f64d142b877972fe93184677ab15be5497e4cb23bb2553d871.jpg)  
图9流场非耦合与耦合热辐射计算驻点线组分质量分数结果(a) $\mathrm { N } ^ { + }$ (b)e

![](images/68cec02ef3254029c89386c8d98f884b4b32c416314d24ba35dfbaad4b0246ab.jpg)  
Fig.9Mass fraction distributions along the stagnation line of uncoupled and coupled radiation simulations: (a) $\mathrm { N } ^ { + }$ ，(b) $\mathrm { e } ^ { - }$   
图10流场非耦合与耦合热辐射计算驻点线热辐射结果：(a)辐射能量源项(单位: $\mathrm { W / m } ^ { 3 } .$ ),(b）平均吸收系数(单位： $\mathrm { m } ^ { - 1 }$ ，(c)投射辐射(单位： $\mathrm { W / m } ^ { 2 }$ ）

Fig.10Radiation results along the stagnation line of uncoupled and coupled radiation simulations: (a) radiation source (unit: $\mathrm { W / m } ^ { 3 } .$ ,(b) total absorption coefficient (unit: $\mathrm { m } ^ { - 1 }$ ）, (c) incident radiation (unit: $\mathrm { W / m } ^ { 3 }$ ）

表5Ma $= 3 5$ 热辐射非耦合与耦合计算的驻点热流值(单位： $ { \mathrm { M W / m ^ { 2 } } } )$   
Table 5 Radiative heat transfers at the stagnation point of uncoupled and coupled radiation simulations with Ma $= 3 5$ (unit:MW/m²)   

<html><body><table><tr><td>Heat flux</td><td>uncoupled</td><td>coupled_thin</td><td>coupled_dom</td></tr><tr><td>qc</td><td>2.63</td><td>2.51</td><td>2.70</td></tr><tr><td>qr</td><td>3.72</td><td>2.52</td><td>2.92</td></tr></table></body></html>

# 4结论

本文设计了辐射平衡和温度间断两个一维热辐射输运模型算例，对比分析了各类热辐射输运求解方法的性能。同时考察各方法在实际求解过程中的存储量、计算量和并行化特点，放弃了一维精确解切平板近似和计算量庞大的蒙特卡洛模拟，提出了由离散坐标法、 ${ \bf P } _ { 1 }$ 近似和光学厚度极限近似三类不同层次方法构建热辐射输运解算方法库，同时给出了该方法库的使用原则。该解算方法库可准确求解热辐射输运，能与流场数值格式高效耦合求解，并适合大规模并行计算。

利用构建的热辐射输运解算方法库耦合再入飞行器高温热化学非平衡流场数值求解格式实现了$M a = 3 5$ 的球头算例演示模拟。相应再入飞行条件下流场与热辐射耦合效应显著，热辐射对流场具有“冷却”作用；流场非耦合与耦合热辐射计算的对流传热接近，但非耦合计算的辐射热流远大于耦合计算值。同时，耦合模拟预测的辐射传热与对流传热水平相当。开展相关模拟研究时，应当考虑流场的热辐射耦合效应

# 参考文献

[1]卞荫贵，徐立功．气动热力学[M]．合肥：中国科学技术 大学出版社,2011:1-2 BIAN Yingui, XU Ligong. Aerothermodynamics[M]. Hefei:University of Science and Technology of China Press,2011:1-2   
[2] Candler G,Park C.The Computation of Radiation from Nonequilibrium Hypersonic Flows[C]// 23rd Thermophysics,Plasmadynamics and Lasers Conference. San Antonio: AIAA,1988:1-12   
[3] Feldick A.Coupled Nonequilibrium Flow,Energy and Radiation Transport for Hypersonic Planetary Entry[D]. Park: The Pennsylvania State University,2013   
[4]高铁锁，江涛，丁明松，等．辐射加热对返回舱气动热 环境影响的数值研究[J].空气动力学报，2015，33(1): 36-41 GAO Tiesuo，JIANG Tao，DING Mingsong，et al. Numerical Study of Radiative Heating Influence on Aerothermal Environment over a Reentry Capsule[J]. Acta Aerodynamic Sinica,2015,33(1): 36-41   
[5]Wang JY, Gao Z X, lee C H. An Iterative Technique for CoupledConduction-RadiationHeatTransferin Semitransparent Media[J].Numerical Heat Transfer, Part A: Applications,2015,67(11): 1208-1231   
[6]Modest M F.Radiative Heat Transfer[M]. San Diego: Academic Press,2003:423-432   
[7]Anderson J D Hypersonic and High-Temperature Gas Dynamics[M]. New York: McGraw-Hill Book Company, 1989: 653-674   
[8]王京盈．高速高温流动的热化学非平衡及热辐射耦合效 应研究[D]．北京：北京航空航天大学,2015 WANG Jingying. Numerical Study on Coupled Chemical Nonequilibrium and Thermal Radiation Effects in High Speed and High Temperature Flows[D]. Beijing: Beihang University, 2015   
[9]Wang J Y,Gao Z X,Lee C H, et al. An Decoupled ProcedureforConvection-RadiationSimulationin Scramjets[J]. Science China: Technological Science, 2014, 57(12): 2551-2566   
[10] Hao J A，Wang J Y, Lee C H. Numerical Study of Hypersonic Flows over Reentry Configurationswith Different Chemical Nonequilibrium Models[J].Acta Astronautica, 2016,126: 1-10   
[11] Park C. Nonequilibrium Hypersonic Aerothermodynamics[M].NewYork:Wiley,1990: 119-126   
[12] Gupta R N, Yos JM, Thompson R A, et al. A Review of Reaction and Thermodynamic and Transport Properties for an 11-Species Air Model for Chemical and Thermal Nonequilibrium Calculations to 300oo K[C]// Technical Report. Washington: NASA,1990: 1-73   
[13] Bertin J J，Cummings R M. Critical Hypersonic Aerothermodynamic Phenomena[J]． Annual Review of Fluid Mechanics,2006,38: 129-157