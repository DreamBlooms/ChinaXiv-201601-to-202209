# 塔式光煤互补系统变工况性能研究

段立强1，余晓辉1，王步云1，冯涛1，张金生2(1．华北电力大学能源动力与机械工程学院，北京市，102206)(2．神华国华（北京）电力研究院有限公司，北京市，100025）

摘要：为了节约能源和保护环境，太阳能辅助燃煤发电系统得以迅速发展。本文针对敦煌地区660MW燃煤机组提出了一种塔式太阳能与常规燃煤电厂集成方案。基于仿真平台TRNSYS，建立了光煤互补系统模型。依据TRNSYS 软件里的气象数据库，在煤炭节省型运行模式下，对互补系统在不同的辐照强度以及不同工况下进行了模拟分析，从而得到了典型日和典型年的热力性能，揭示了光煤互补系统的热力特性。结果表明，本文中的互补系统年光电转换效率为 $1 5 . 3 6 \%$ ，相对于现有单一的太阳能热发电技术，由于光煤互补更加节约成本，因此具有一定的优势。本文研究结果为改造现有燃煤电站提供了新的途径和理论指导。

关键词：光煤互补发电；塔式太阳能；变辐照；变负荷；热力性能；

中国分类号：TK519文献标志码：A

# Study on Off-design Performance of Tower Solar Energy Aided Coal-fired Power Generation System

Duan Li-Qiangl Yu Xiao-Hui1 Wang Bu-Yun1 Feng Taol Zhang Jin-Sheng² (1.School ofEnergyPowerand MechanicalEngineering,NorthChinaElectricPowerUniversity,Beijingl02206,China) (2.Shenhua Guohua (Beijing) Electric Power Research Institute Co.,Ltd., Beijing 10o025, China)

Abstract:In order to save the fosil energyand protect the environment,the solar aided coal-fired power generation system has been developed rapidly.The integration scheme of tower solar energy colector and conventional 660MW coal-fired power plant in Dunhuang is proposed. Based on the simulation platform TRNSYS,the model of the solar energy-aided coal-fired power generation system is established. According to the meteorological database in TRNSYS software,the simulation and analysis of the complementary system under diferent solar radiation intensities and diferent turbine loads are carried out with the operating mode of coal saving.The thermodynamic performances of the complementary system in typical days and typical year are obtained,and the thermal characteristics of the complementary system are revealed. The results show that the annual solar-to-electric efficiency of the complementary system is $1 5 . 3 6 \%$ ，which has a certain advantage with lower cost than the existing independent solar thermal power generation system.The achievements from this paper willprovide a new wayand the theoretical guide for retrofitting the existing conventional coal-fired power plant.

Key words:Solar energyaided coal-fired power generation system; Tower solar energy; Varying direct normal solal radiation; Varying turbine load; Thermodynamic performance;

# 0前言

自第一次工业革命起，化石能源在人类文明进步中担任重要角色。但从上世纪50年代欧洲的光化学污染，到如今的国内雾霾，化石能源消耗带来的环境污染问题已经严重影响到人们健康。如今节能减排已经成为国际共识，发展多元化能源结构是各国努力的目标[1-3]。太阳能以其独特的优势逐渐被重视，总体来讲发展太阳能有以下优势：无温室气体（主要是 $\mathrm { C O } _ { 2 }$ ， $\mathsf { N O } _ { \mathrm { X } }$ ）或有毒气体（ $\mathrm { S O } _ { 2 }$ ，颗粒）排放；增加区域/国家能源独立性；太阳能为可再生能源，能量充沛而且廉价[4]。而我国 $7 0 \%$ 的电力来自于火力发电厂，然而受到资源和环境的制约，节能减排的工作越来越重要，许多耗煤量较高的中小型火力发电厂即将面临关停的命运。因此能源的互补利用逐渐开始成为能源系统重要的发展趋势[5-8]。我国的太阳能资源非常丰富，太阳能辅助燃煤发电系统逐渐受到大家的重视。

国内相关研究中，杨勇平等[9-10]探究了在设计辐照下不同负荷互补系统的性能，对设计工况下集成方式的选择进行了探讨。金红光等[11]对太阳热与汽轮机抽汽品味相匹配的热互补机理进行了研究，抛物槽式集热器产生的 $3 0 0 ^ { \circ } \mathrm { C }$ 左右的中低温太阳能与燃煤电站回热系统温度相匹配，提出太阳热能替代给水加热器的级数越高，集热场效率越高。

西方发达国家均把太阳能光煤互补协同发电技术的研究作为21世纪能源研究的主要方向，并做了很多相关研究。TeresitaLarrain等[l2]建立了化石能源辅助太阳能加热给水发电100MW系统模型，并利用智利沙漠的气候参数进行研究，希望找到在混合系统效率最佳的时候最小的化石能源用量。DimityPopov[13]利用欧洲皇家经济学会流体软件建立朗肯蒸汽循环模型，用菲涅尔式太阳能集热场直接加热给水并取代高压加热器。

由于太阳辐照时空分布不均匀、不连续以及汽轮机运行负荷的变化都会使得系统性能偏离设计值，因此对系统变工况运行特性的研究是很有必要的。本文依据TRNSYS软件里的气象数据库[14]，在煤炭节省型操作模式下，对互补系统在不同的辐照以及不同工况下进行了模拟分析，从而得到了典型日和典型年的热力性能，揭示了光煤互补系统的特点。本文旨在寻求改造现有燃煤电站的新途径，为改造燃煤电站提供一些理论参考。

# 1系统描述

# 1.1燃煤发电系统

![](images/766cce45b9a862e3bd3547d0faf724f77614b4c37b98502326d9dbd2c7011129.jpg)  
图1燃煤发电系统原理图

# Fig.1Schematic diagram of the coal-fired power generation system

本文中，以一台660MW超临界火电机组作为基础系统。燃煤发电系统的简化原理图如图1所示。表1则给出了5种运行工况机组的主要相关参

数，5种工况即汽机 $1 0 0 \%$ 负荷、 $8 5 \%$ 负荷、 $7 5 \%$ 负荷、 $6 0 \%$ 负荷和 $5 0 \%$ 负荷。

表1五种工况下机组主要参数  
Table.1Mainparametersofunitunderfiveturbineloads   

<html><body><table><tr><td>参数</td><td>100%</td><td>85%</td><td>75%</td><td>60%</td><td>50%</td></tr><tr><td>功率 (MW)</td><td>658.3</td><td>559.6</td><td>493.7</td><td>395</td><td>329.1</td></tr><tr><td>主蒸汽压力(MPa)</td><td>24.2</td><td>22.9</td><td>20. 1</td><td>16.5</td><td>13.5</td></tr><tr><td>主蒸汽温度(℃)</td><td>566</td><td>566</td><td>566</td><td>566</td><td>566</td></tr><tr><td>再热蒸汽压力(MPa)</td><td>4.2</td><td>3.9</td><td>3.1</td><td>2.8</td><td>2.1</td></tr><tr><td>再热蒸汽温度(℃)</td><td>566</td><td>566</td><td>566</td><td>566</td><td>566</td></tr><tr><td>主蒸汽流量(t/h)</td><td>1920.8</td><td>1594. 0</td><td>1391. 3</td><td>1097. 5</td><td>913.5</td></tr><tr><td>给水温度(℃)</td><td>273.5</td><td>260.7</td><td>254.0</td><td>239.4</td><td>230.5</td></tr><tr><td>乏汽压力 (kPa)</td><td>5.3</td><td>5.3</td><td>5.3</td><td>5.3</td><td>5.3</td></tr><tr><td>乏汽焓值(kJ/kg)</td><td>2351. 5</td><td>2372. 9</td><td>2387. 1</td><td>2408.4</td><td>2422. 4</td></tr></table></body></html>

# 1.2太阳能系统与锅炉系统的集成

本文利用熔融盐作为工作介质吸收太阳能，并将热量释放到燃煤发电系统中，通过汽轮机做功并

发电。本集成方案设置了两个太阳能加热器。图2就是塔式太阳能系统与燃煤锅炉系统集成的示意图。

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

由于采用节省煤炭型模式，高温过热器出口蒸汽温度会有所降低。#1太阳能加热器加热来自锅炉汽水分离器的锅炉抽汽，然后将抽汽与高过出口蒸汽混合，维持主蒸汽（高压缸进汽）温度不变（ $5 6 6 ^ { \circ } \mathrm { C } \ .$ ；

由于采用节省煤炭型模式，高温再热器出口蒸汽温度会有所降低。#2太阳能加热器加热高再出口蒸汽，维持再热蒸汽（中压缸进汽）温度不变（ $5 6 6 ^ { \circ } \mathrm { C }$ 。

![](images/7215b86bd03387741669c004c375dcb970ac03fcab654e965c7ef2879be4086a.jpg)  
图2塔式太阳能系统与燃煤锅炉系统集成的示意图

Fig.2Schematic diagram of integration of the solar tower system with the boiler system of the base system

# 1.3光煤互补系统

在本文中，提出了一种塔式太阳能与常规燃煤电厂集成方案,并在节煤运行模式下（给水流量恒定，降低给煤量）进行了热力性能的研究。图3是光煤互补发电系统热力循环示意图。

本文中的光煤互补系统流程主要有以下三个优点。

（1）该系统利用#2太阳能加热器加热再热蒸汽，作为调控再热汽温主要手段，烟道挡板法作为辅助调节手段，避免了挡板法可能失效的问题。传统的烟道挡板法用分割烟道挡板法调控再热蒸汽温度的优点是结构简单，操作方便，已被许多大型电站锅炉采用。其缺点是汽温调节的时滞太大，挡板的开度与汽温变化为非线性关系，开度有效范围较窄。一般通常认为，烟气挡板在 $4 0 \% \sim 6 0 \%$ 开度具有良好的调节性能，烟气份额在 $3 0 \% ^ { \sim } 7 0 \%$ 具有良好的汽温调节性能。但如果烟气份额低于 $2 5 \%$ 或高于$7 5 \%$ ，挡板将启不到调节作用，再热器汽温的调节手段将失效，不再能保证再热器的额定汽温。由于实际运行时煤种、负荷都会有一定的波动，烟气成分、份额会有变化，再加上不稳定的太阳能资源，对挡板调节的灵敏度和速度提出了更高的要求。

（2）与以往采用太阳能加热给水/凝结水方案相比较，本文采用太阳能加热高温蒸汽，由于没有回热抽汽量的变化，就不会影响整个汽轮机通流中的蒸汽流量、压力、温度和所做功的分布。也就不用为了保证机组的安全运行，对各级叶片重新进行计算考核。

（3）由于超临界直流锅炉没有汽包，储热容量小。因此，在同一程度的干扰下，蒸汽温度的变化相比汽包锅炉会更明显。而本方案可以很好地控制住主蒸汽和再热蒸汽的温度。

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

![](images/80b871a540b5d48f049dbe94c52d53dfc784e690fde7b29624fd630b6f9a1009.jpg)  
Fig.3Schematic diagramof the solar-hybrid coal-fired powerplant

# 2 模型建立

本文的光煤互补系统搭建在TRNSYS模拟平台

上。图4是用TRNSYS软件搭建的光煤互补模拟系统。

![](images/d417378437f875833297a08fc2a013502e1ec9dfd592f9b9327ab3cf685440f5.jpg)  
图3光煤互补发电系统热力循环示意图  
图4TRNSYS软件搭建的光煤互补模拟系统

# Fig.4 Simulation system of the solar-hybrid coal-fired power plant built by TRNSYS

# 2.1定日镜场

定日镜场模型需要用户提供一个效率矩阵以此来计算镜场效率field，效率矩阵含有很多组数列，

每组数列由方位角、天顶角以及此刻的镜场效率三个参数组成，然后软件利用线性插值法求出其他方位的镜场效率，可见矩阵包含的组数越多，拟合得

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

更好[14]。吸热器接受到的来自镜场的功率 $\mathrm { Q } _ { \mathrm { r e c } }$ 计算如下：  
Qrc= Afed Ped·Infed (1)其中:  
$\dot { Q } _ { r e c }$ ：吸热器接受到的来自镜场的功率 $( \mathrm { { k J / h } ) }$ ：（204号 $A _ { f i e l d }$ ：定日镜总镜面面积 $( \mathbf { m } ^ { 2 } )$ ：  
Pfield：镜场反射率;  
$I$ ：法向直接辐射 $( \mathbf { k J } / \mathbf { h } { \cdot } \mathbf { m } ^ { - 2 } )$ ；  
$\eta _ { \it \mathrm { \it f i e l d } }$ ：镜场效率.

# 2.2吸热器

在塔式太阳能系统中，吸热器是个光热转换设备。选取熔融盐（LiCl&KCI）作为吸热工质，LiCl和KCI组分比 $0 . 5 9 5 { : 0 . 4 0 5 }$ ，工作温度范围 $3 5 5 -$ $1 4 0 0 ^ { \circ } \mathrm { C }$ 。熔盐塔吸热器出口温度设计成定值$6 2 0 ^ { \circ } \mathrm { C }$ 。

吸热器出口状态取决于进口熔盐状态和输入的辐射。同时，模型中吸热器本体和管道的热损失都计算在内[15]。吸热器模型计算公式如下：

$$
\begin{array} { r l } & { \begin{array} { r l } { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \\ { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \end{array} ; } \\ & { \begin{array} { r l } { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { - \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } } \\ { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \end{array} ; } \\ & { \begin{array} { r l } { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { - \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \\ { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \end{array} ; } \\ & { \begin{array} { r l } { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { - \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } } \\ { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } \end{array} ; } \\ &  \begin{array} { r l } { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } & { - \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { e f f } } } { 2 } \frac { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { e f f } } } { 2 } } \\ { \hat { \rho } _ { \mathrm { e f f } } ^ { \mathrm { i n } } } &  \hat { \rho } _ { \mathrm { e f f } }  \end{array} \end{array}
$$

其中:

$\overline { { T } } _ { a b s }$ :吸热器平均温度（ $\mathrm { { } ^ { \circ } C ) }$ ·

tin:吸热器熔盐进口温度（℃)；  
$t _ { o u t }$ :吸热器熔盐出口温度（℃）；  
$\dot { Q } _ { l o s s \_ r a d }$ :吸热器辐射损失 $( \mathrm { { k J / h } ) }$ ；  
$A _ { p }$ :吸热器采光口开口面积 $( \mathbf { m } ^ { 2 } )$ ;  
$e p s _ { a b s }$ :吸热器发射率;  
$\sigma$ :斯特藩常数, $\sigma { = } 5 . 6 7 \mathrm { X } 1 0 ^ { - 8 } \mathrm { W } / \left( \mathrm { m } ^ { 2 } { \cdot } \mathrm { K } ^ { 4 } \right)$ ：，$\dot { Q } _ { a b s }$ :吸热器吸收的功率 $( \mathrm { { k J / h } ) }$ ;  
$e t a _ { o p t }$ :光学效率;  
$\dot { Q } _ { l o s s \_ p i p e }$ :管道热损失 $( \mathrm { { k J / h } ) }$ ，  
$A _ { p i p e }$ ：管道表面积 $( \mathbf { m } ^ { 2 } )$ ;  
（204号 $e p s _ { p i p e }$ :管道发射率;  
$k _ { p i p e }$ :管道对流换热系数 $( \mathbf { k J } / \mathbf { h } { \cdot } \mathbf { m } ^ { - 2 } { \cdot } \mathbf { K } ^ { - 1 } )$ ：’tamb :环境温度（℃);  
$\boldsymbol { Q } _ { l o s s \_ c o o l }$ $( \mathrm { { k J / h } ) }$   
$f _ { c o o l i n g \_ l o s s }$ :吸热器冷却损失系数;  
$\dot { Q } _ { n e t }$ :吸热器功率 $( \mathrm { { k J / h } ) }$ ；  
$\dot { Q } _ { t h }$ :熔盐塔热负荷 $( \mathrm { { k J / h } ) }$ ：  
$c _ { s a l t }$ :熔盐的比热容 $\left( \mathbf { k J } \ / \log \cdot \mathbf { K } ^ { - 1 } \right)$ ；  
.  
$m _ { s a l t }$ :熔盐总质量流量 $( \mathrm { { k g / h } ) }$ ：  
nrec :吸热器效率.

# 2.3热力性能指标

太阳能光电转换效率是本文评价互补系统性能的一项重要指标，公式如下：

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$$
\eta _ { s e } = \frac { 3 . 6 \bullet P _ { s } } { \dot { \mathcal { Q } } _ { s } } = \frac { 3 . 6 \bullet \left( P _ { z } - \frac { \dot { Q } _ { b } } { 3 . 6 } \bullet \eta _ { r e f } \right) } { \dot { \mathcal { Q } } _ { s } } = \frac { 3 . 6 \bullet P _ { z } - \dot { Q } _ { b } \bullet \eta _ { r e f } } { \dot { \mathcal { Q } } _ { s } }
$$

$\dot { Q } _ { s } = A _ { f i e l d } \bullet \rho _ { f i e l d } \bullet I$ （204号  
其中:  
$\eta _ { s e }$ ：光电转换效率;  
$P _ { s }$ :太阳能输出功率(W);  
$\dot { Q } _ { s }$ ：总的太阳能辐照能量 (kJ/h);Pz:互补系统输出功率（W);  
$\dot { Q _ { b } }$ ：锅炉总的热负荷 $( \mathrm { { k J / h } ) }$ ;  
$\eta _ { r e f }$ ：参考系统原燃煤电厂的效率.供电煤耗，计算如下：  
$b = \frac { 1 0 0 0 m _ { s c } } { E }$   
其中:  
$b$ ：供电煤耗 $( \mathbf { g } / \mathrm { k W h } )$ ：  
$m _ { s c }$ :转换到标煤的燃煤量 $( \mathbf { k g } )$ ：$E$ ：电厂输出的电能 (kWh).

# 3结果与分析

在本文的设计计算中，将动力岛设计点选取为汽轮机 $1 0 0 \%$ 负荷，镜场设计应该与动力侧容量合理匹配。根据TRNSYS软件自带的气象数据库提供的敦煌地区（北纬40度，东经94度）典型年辐照数据（图5所示)，设计辐照强度选取为 $6 9 4 \mathrm { W } / \mathrm { m } ^ { 2 }$ （即 $2 4 9 9 \mathrm { { k J / h } } { \cdot } \mathrm { { m } } ^ { - 2 } .$ )。表2给出了设计点光岛的详细参数。

表2设计点光岛参数Table.2Parametersofsolarpowersystematdesignpoint  

<html><body><table><tr><td>参数</td><td>单位</td><td>数值</td></tr><tr><td>定日镜镜面面积</td><td>m²</td><td>120000</td></tr></table></body></html>

<html><body><table><tr><td>熔盐质量流量</td><td>kg/h</td><td>1.80 ×106</td></tr><tr><td>#1太阳能加热器熔盐进口温度</td><td>℃</td><td>620</td></tr><tr><td>#1太阳能加热器熔盐出口温度</td><td>℃</td><td>516.9</td></tr><tr><td>#2太阳能加热器熔盐进口温度</td><td>℃</td><td>620</td></tr><tr><td>#2太阳能加热器熔盐出口温度</td><td>℃</td><td>572.8</td></tr><tr><td>#1太阳能加热器锅炉抽汽出口温度</td><td>℃</td><td>600.4</td></tr><tr><td>#2太阳能加热器再热蒸汽出口温度</td><td>℃</td><td>566</td></tr><tr><td>熔盐塔热负荷</td><td>MW</td><td>41.39</td></tr><tr><td>最大瞬时光电转换效率</td><td>%</td><td>23.16</td></tr></table></body></html>

![](images/29b8a3c59db7e20031a5ba23a7dbe83fd39c07cc2c13111ff996c181f8a9943a.jpg)  
图5敦煌典型年辐照数据

# Fig.5DNI data of typical year in Dunhuang $( \mathbf { k J } / \mathbf { h } { \cdot } \mathbf { m } ^ { - 2 } )$

# 3.1变工况运行

本文选取了滑压运行五种工况，分别是 $5 0 \%$ 负荷、 $6 0 \%$ 负荷、 $7 5 \%$ 负荷、 $8 5 \%$ 负荷和 $1 0 0 \%$ 负荷。图6示出了不同工况下熔盐塔进出口温度的变化情况。本文熔盐塔吸热器出口温度设计成定值$6 2 0 ^ { \circ } \mathrm { C }$ ，因此随着负荷的降低，熔盐塔出口温度不变，始终为 $6 2 0 ^ { \circ } \mathrm { C }$ 。而熔盐塔进口温度随着负荷的降低会有所升高，这是因为负荷降低，与熔盐换热的蒸汽量变少，换热量减少，此时熔盐塔里熔盐温升范围下降，从 $1 0 0 \%$ 负荷时温升 $6 9 ^ { \circ } \mathrm { C }$ 下降到 $5 0 \%$ 负荷时温升 $3 9 . 7 \mathrm { { ^ { \circ } C } }$ ，也就意味着一定数目的定日镜没有利用造成资源浪费，此时光电转换效率下降明显。

![](images/e2a3c042e2b68c8b3929392f0cec53559863182064d8b956a1b71396579ce0a4.jpg)  
图6不同工况下熔盐塔进出口温度变化  
Fig.6The variationof inletand outlet temperatureformolten

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

# salt towerunder five turbine loads

图7为不同工况下锅炉受热面热负荷的变化规律。横坐标（WW、Div、Back、Hsh、HRh、LSh、LRh、Eco）从左到右依次是水冷壁、分割屏、后屏、高过、高再、低过、低再、省煤器。acegi是原系统在5种负荷下的情况，bdfhj是互补系统在5种负荷下的情况。互补系统与原系统相

比，热负荷变化率从大到小的顺序依次是LSh（HSh）>Back(Div)>LRh>HRh>Eco>WW，其中，在不同汽轮机负荷下，LSh和HSh热负荷变化率接近，Back和Div热负荷变化率也接近。热负荷变化率最大的接近 $1 5 \%$ ，最小的接近 $1 \%$ 。

![](images/5dc81168970e513822d3bce3691cd48b17f7389f381e59497a3831a531b2dd8f.jpg)  
图7不同工况下锅炉受热面热负荷变化

# Fig.7The variation of thermal load of boiler heat exchanger under five turbine loads

图8为原系统与互补系统在不同工况下供电煤耗的对比图。可看出，随着负荷的降低，供电煤耗相应的增大。在 $1 0 0 \%$ 负荷时，互补系统相比原系统煤耗减少了 $7 . 7 \mathrm { g / k W h }$ ，在 $5 0 \%$ 负荷时，互补系统相比原系统煤耗减少了 $6 . 5 \mathrm { g / k W h }$ 。反映到机组效率上就是，随着负荷的降低，机组效率也是降低的，而且互补系统在原系统的基础上所提高的效率也是略有下降的。

![](images/acb508298b179fa783045c071866bb58dfde7be02f6f85d9849ed67afe55c289.jpg)

图8不同工况下煤耗的变化Fig.8The variation of standard coal consumption under fiveturbine loads

# 3.2典型日热力性能

选取春分、夏至、秋分、冬至四个典型日（3月20日，6月21日，9月22日，12月21日）对互补系统热力性能进行分析。图9为四个典型日太阳能光电转换效率随时间的变化规律。

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/bfc0630c17e88d41c0fea98e9ebea674f32053db61f66e8b5b5fc9a674bf734a.jpg)  
图9典型日太阳能光电转换效率随时间的变化

Fig.9The variation of solar-to-electric efficiency with time on typical days

从图中可以看出，春分和秋分太阳能利用小时 数接近，夏至最高。而冬至，由于DNI值太低，不

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

足以达到熔盐塔出口温度 $6 2 0 ^ { \circ } \mathrm { C }$ 的条件，因此光岛整天都不运行。在春分日和秋分日， $1 0 0 \%$ 负荷时，日均光电转换效率在 $1 8 \%$ 左右； $5 0 \%$ 负荷时，日均光电转换效率在 $1 0 \%$ 左右。在夏至日， $1 0 0 \%$ 负荷时，日均光电转换效率在 $2 1 \%$ 左右； $5 0 \%$ 负荷时，日均光电转换效率在 $1 1 \%$ 左右。其中，光电转换效率变化趋势与当天的太阳能辐照情况有关。正午时分DNI大，但由于不能充分利用，因此效率反而不高。

# 3.3全年热力性能

为了获得互补系统全年运行的热力性能数据，简单假定电厂全年都是以 $1 0 0 \%$ 负荷运行。图10为太阳能月利用小时数的一年变化情况。图10可以看出，冬季太阳能利用小时数最少。这是由于冬季环境温度低，因此散热损失大，而且冬季太阳能入射角大，因此余弦损失也大。再加上DNI值也低，所以系统处于互补运行模式的时间最短。

用限 250  
200  
150 山  
100 50 □  
01 ) 3 4 5 6 1 8 9 10 11 12月份

# Fig.10Monthly utilization hours of solar energy

表3为设计点下全年热力性能参数。互补系统年利用太阳能2047个小时，太阳能年发电量$3 . 7 2 \times 1 0 ^ { 7 }$ 度，年光电转换效率为 $1 5 . 3 6 \%$ ，年节省煤量10414吨。

表3全年热力性能  
Table.3Annualperformancesatdesignpoint   

<html><body><table><tr><td>参数</td><td>单位</td><td>数值</td></tr><tr><td>太阳能年利用小时数</td><td>h</td><td>2047</td></tr><tr><td>太阳能年发电量</td><td>kWh</td><td>3.72×107</td></tr><tr><td>年光电转换效率</td><td>%</td><td>15.36</td></tr><tr><td>年节省煤量</td><td>t</td><td>10414</td></tr></table></body></html>

# 4结论

本文针对敦煌地区660MW燃煤机组提出了一种塔式太阳能与常规燃煤电厂集成方案。基于仿真平台TRNSYS，建立了光煤互补系统模型。在煤炭节省型操作模式下，对互补系统在不同的辐照强度

以及不同工况下进行了模拟分析，从而得到了四季典型日和典型年的热力性能数据，结果表明：  
1）在 $1 0 0 \%$ 负荷时，互补系统相比原系统，煤耗减少 $7 . 7 \mathrm { g / k W h }$ ，全厂效率提高 $1 . 0 7 \%$ ；在 $5 0 \%$ 负荷时，互补系统相比原系统，煤耗减少$6 . 5 \mathrm { g / k W h }$ ，全厂效率提高 $0 . 8 0 \%$ 。  
2）设计功率 $1 0 0 \%$ 负荷下对应互补系统，光电转换效率高，煤耗小，优于其他四种参比负荷，最大瞬时光电转换效率可达 $2 3 . 1 6 \%$ 。  
3）在设计点探究了互补系统全年热力性能，年光电转换效率为 $1 5 . 3 6 \%$ ，对于现有单一的太阳能热发电技术，由于光煤互补更加节约成本，因此具有一定的优势。

# 参考文献

[1]金红光.能的综合梯级利用与燃气轮机总能系统[M].北京: 科学出版社,2008:637-639. JIN Hongguang. Comprehensive cascade utilization of energy and total energy system of gas turbine[M].Beijing: Science Press,2008:637-639.   
[2]Aldo Steinfeld.SolarThermochemical Process Technology[M]. Encyclopedia of Physical Science&Technology,2001:237-256.   
[3]中华人民共和国国务院.国家中长期科学和技术发展规划 纲要(2006-2020)[R].北京,2006. The State Council of the people's Republic of China. NationalLong-termScientificandTechnological Development(2006-2020)[R]. Beijing,2006.   
[4]何梓年.太阳能热利用[M].合肥:中国科学技术大学出版 社,2009,7. HE Zinian. Solar thermal utilization[M].Hefei: Press of University of Science and Technology of China, 2009,7.   
[5]陈静,刘建忠,沈望俊,等.太阳能热发电系统的研究现状综述 [J].热力发电,2012,41(4):17-22. CHEN Jing,LIU Jianzhong,SHEN Wangjun, et al. Status quo in research of solar energy thermal power generation system[J]. Thermal Power Generation,2012,41(4):17-22.   
[6]崔淑卿,陈娟,杨苏荣.我国太阳能发电前景分析[J],内蒙古 科技与经济,2009,17:77. CUI Shuqing, CHEN Juan, YANG Surong. Analysis of the Prospects for Solar Power Generation in China[J].InnerMongolia Science Technology&Economy,20o9,17:77.   
[7]朱俊生.中国新能源和可再生能源发展状况[J].可再生能 源,2003,2:3-10. ZHU Junsheng. Development situation of newand renewable energy in China[J]. Renewable Energy, 2003,2:3-10.

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

[8]崔映红,陈娟.太阳能热混合发电系统综述[J].现代电 力,2007,24(5):24-28. Cui Yinghong, Chen Juan.Review on Hybrid Solar Thermal Generating System[J].ModernElectric Power, 2007,24(5):24-28.   
[9]崔映红,杨勇平,杨志平,等.太阳能辅助燃煤一体化热发电系 统耦合机理[J].中国电机工程学报,2008,29(28):99-104. CUI Yinghong,YANG Yongping, YANG Zhiping，et al. Coupling Mechanism of Solar Supported Coal-fired Electric Generation System[J].Proceedings of the Chinese Society For Electrical Engineering,2008,29(28):99-104.   
[10]Yang Y,Yan Q,Zhai R,et al.An efficient way to use medium-or-low temperature solar heat for power generation integration into conventional power plant.Applied thermal engineering[J],2011,31:157-162.   
[11]Hong H, Zhao Y, Jin H.Proposed partial repowering of a coal-fired power plant using low-grade solar thermal energy[J]. International Journal of Thermodynamics,2011, 14(1): 21-28.   
[12]Larrain TJ,Escobar RA． Solar thermal power plant performance model to determine fossil fuel backup consumption for different locations in northern Chile[J]. Renewable Energy,2010,35:1632-1643.   
[13] Popov Dimityr.An option for solar thermal repowering of fossil fuel fired power plants[J].Solar Energy,2011,85: 344-9.   
[14] Peter Schwarzbozl,Ulrich Eiden,RobertPitz-Paal, et al. ATRNSYS Model Library for Solar Thermal Electric Components (STEC).A Reference Manual Release 2.2, 2002,34-37.

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538