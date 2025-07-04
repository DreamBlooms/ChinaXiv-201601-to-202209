# 肿瘤微波热疗的温度场模拟计算

崔闯，卢玟"，单彦广，李凌，霍睿敏（上海理工大学，能源与动力工程学院，热工程研究所，上海，200093）

摘要：本文通过对肿瘤与生物组织的物理模型简化，应用生物传热方程，建立肿瘤热疗的数学模型。运用数值模拟预演了热疗过程，通过控制探针的开关，控制了肿瘤中心温度在 $5 4 ^ { \circ } \mathrm { C }$ 以下，肿瘤边缘温度在 $4 3 { \sim } 4 5 ^ { \circ } \mathrm { C }$ 之间变化，分析了肿瘤内部的温度分布，提出了基于温度控制的热疗方案，为临床肿瘤热疗的温度控制提供理论依据。

关键词：肿瘤；热疗；温度场；数值模拟

中图分类号： 文献标识码：A

# A Numerical Study on Temperature Research for Microwave Thermal

Therapy of Tumor

Cui Chuang LU Mei\* SHAN Yan-Guang LI Ling HUO Rui-Min (SchoolofEnergyandPowerEngineering,UniversityofShanghai forScienceand Technology,Shanghai 2oo093,Chin

Abstract: This article simplifies the physical model of tumor and biological tissue,applies the bio heat transfer equation to build a mathematic model of tumor hyperthermia. A numerical method is adopted to previews the tumor treatment process, the tumor center temperature under $5 4 ^ { \circ } \mathrm { C }$ ，the tumor edge changes between $4 3 { \sim } 4 5 ^ { \circ } \mathrm { C }$ by controlling the switch oftheantenna,the temperature distribution within thetumoris alsoanalyzed,putforward the heat treatment scheme based on temperature control.The article provides theory foundations for temperature control of clinical tumor thermotherapy.

Key words: tumor; hyperthermia; temperature field; numerical simulation

# 0引言

热疗法是近年来迅速兴起的一种有效治疗肿瘤的手段。热疗法具有无创或微创的特点，无毒无副作用，因而治疗过程中病人的痛苦较小。热疗法不但能直接杀死癌细胞，而且可作为放疗、化疗的辅助治疗方法。

长期实践证明，微波热疗优于其他各种物理加热方法。介入微波热凝固疗法是欧美等国进行热疗的主要方法,对肿瘤有较好的疗效。近年来已开发出应用微波加热深部肿瘤的设备[1],实现了对体内比吸收率 SAR (specific absorption rate)分布的控制而达到对不同深度的肿瘤进行加热。朱光明等[2以前列腺癌热疗为研究考察对象，讨论介入式微波热疗对微波热疗过程中的温度场、热损伤分布以及血液灌注率的变化进行了数值模拟，得到了较为准确的热疗温度场预示。程志刚等[3]根据体模实验所得到的 SAR公式，利用有限元软件ANSYS模拟出 $9 1 5 ~ \mathrm { \mathrm { M H z } }$ 植入式探针的微波热场；同时考虑到微波加热体模后变形造成的部分参数的变化，对模拟中的相关参数进行了修改，从而得到了与实际测量较为接近的温升曲线。T.P.Ryan[采用三维有限元模型预测了腰痛治疗中脊椎组织附近电极产生的电场和热沉积作用的能量分布，发现模拟结果与活体动物以及人体标本实验的结果一致。

在上述作者的研究基础上，本文以肝脏肿瘤为对象，采用有限元方法，分析热疗过程的温度场，从而提出了基于温度控制的热疗方案。

# 1 微波热疗模型

# 1.1微波热疗物理模型

以肝肿瘤热疗为研究对象。在临床研究中，对于 $\scriptstyle \mathbf { D < } 2 \ \mathbf { c m }$ 的肝肿瘤，采用单一热源，一次凝固即可完成治疗。本文假定肿瘤为直径 $_ { \mathrm { D = 1 } . 5 \ \mathrm { c m } }$ 的球体，采用单一探针加热。

微波热凝固肿瘤热疗系统模型如图1所示（剖面图)，取 $9 1 5 \mathrm { M H z }$ 圆柱形微波探针，半径 $\scriptstyle \mathrm { R } _ { 1 } = 0 . 0 0 1$ m，前端微波有效发射长度 $_ { \mathrm { H = } 0 . 0 0 8 \mathrm { m } }$ ；计算区域取以肿瘤中心为球心、半径 $\mathrm { R } _ { 3 } { = } 0 . 0 4 5 \mathrm { ~ m ~ }$ 的球体，肿瘤周围计算区域为正常肝组织；探针有效发射端插入肿瘤中心，圆柱体中心与肿瘤中心重合。

![](images/909593a78073c9cd87db123a8667e7e9a0dd1e4d5204a90332752ebfc39b38bd.jpg)  
图1 肝脏肿瘤微波热疗示意图

# 1.2控制方程及定解条件

本文采用生物传热中最为广泛应用的Pennes方程，如式(1)所示。

$$
\rho c \frac { \partial T } { \partial \tau } = \lambda \nabla ^ { 2 } T + W _ { b } C _ { b } ( T _ { b } - T ) + q _ { m } + q _ { r }
$$

式中， $\rho$ 为组织或肿瘤的密度， $( \mathrm { k g / m } ^ { 3 } )$ ； $\mathbf { \Psi } _ { c }$ 为组织或肿瘤的比热容， $( \mathrm { J } / \mathrm { k g } { \bullet } \mathrm { K } )$ ； $\tau$ 为计算时间，(S)； $T$ 为温度，(K)； $\lambda$ 为导热系数， $\mathrm { ( W / m \bullet K ) }$ ； $\boldsymbol { W _ { b } }$ 为血液灌注率， $( \mathrm { k g / m ^ { 3 } } \mathrm { \bullet s } )$ ； $C _ { b }$ 为血液比热容， $( \mathrm { J / k g ^ { \bullet } K } )$ ； $T _ { b }$ 为血液温度， $( ^ { \circ } C )$ ； $q _ { m }$ 为组织的代谢产热率， $( \mathrm { W / m } ^ { 3 } )$ ; $q _ { r }$ 为单位组织所吸收的微波辐射能， $\mathrm { ( W / m } ^ { 3 } )$ 。

计算区域边界温度取为定值，热疗前的温度场为初始温度场。由于加热过程产生的热场是绕探针轴对称的，本问题可以采用二维数值模拟。

# 1.3 物性参数

血液灌注率 $W _ { b }$ 定义为单位时间单位体积组织内的血液流量，是活体组织区别于非生物材料的重要特性。血液灌注率按以下所示式(2)、式(3)计算[5]。

$$
W _ { l i v e r } = \left\{ \begin{array} { l l } { 0 . 4 5 + 3 . 5 5 ^ { * } \mathrm { e } ^ { ( - \frac { ( T - 4 5 . 0 ) ^ { 2 } } { 1 2 . 0 } ) } } & { T \leq 4 5 . 0 } \\ { 4 . \ 0 0 } & { 4 5 . 0 < T \leq 6 0 . 0 } \\ { 0 } & { T > 6 0 } \end{array} \right.
$$

$$
{ \it W } _ { t u m o r } = \left\{ \begin{array} { l } { 0 . 8 3 3 } \\ { 0 . 8 3 3 - \frac { \left( T - 3 7 . 0 \right) ^ { 4 . 8 } } { 5 4 3 8 } \quad 3 7 . 0 \leq T \leq 4 2 . 0 } \\ { 0 . 4 1 6 \quad \quad \quad \quad 4 2 . 0 < T \leq 6 0 . 0 } \\ { 0 \quad \quad \quad \quad T > 6 0 . 0 } \end{array} \right.
$$

比吸收率SAR是用来衡量电磁辐射对人体的影响的重要指标。SAR定义在单位时间内每千克的物质所吸收的电磁能量。计算中比吸收率SAR采用915MHz圆柱形微波探针实验数据[7]。

由于肿瘤组织代谢旺盛，因此肿瘤与正常组织代谢产热率差距较大，肿瘤与肝组织的代谢产热分别取 $q _ { m - t u m o r } { = } 2 9 0 0 0 \mathrm { W / m } ^ { 3 }$ 和 $q _ { m - l i \nu e r } { = } 4 5 0 \mathrm { W / m } ^ { 3 [ 8 ] }$ 。

其他物性参数取常数，具体取值如表1所示[7]。

表1物性参数 Table 1 The physical parameters   

<html><body><table><tr><td></td><td>p</td><td></td><td>C</td><td>qm</td></tr><tr><td>组织</td><td>kg/m³</td><td>W/(m·K) 0.465</td><td>J/(kg·K)</td><td>W/m3</td></tr><tr><td>肿瘤</td><td>1020</td><td></td><td>3840</td><td>450</td></tr><tr><td></td><td>1000</td><td>0.642</td><td>3500</td><td>29000</td></tr><tr><td>血液</td><td>1060</td><td></td><td>3770</td><td></td></tr></table></body></html>

# 2 数值模拟

# 2.1热疗前的初始温度场

把控制方程(1)式中等式左侧的非稳态项和等式右侧第四项分别置为零，就可用于计算热疗前的温度场，即模拟热疗过程的初始温度场。模拟所用的网格划分及模拟得到的初始温度场如图2所示，肿瘤中心最高温度为到 $4 1 . 2 9 ^ { \circ } \mathrm { C }$ ，这是由于肿瘤相对于正常组织而言代谢更旺盛所致。

![](images/77deb593b6a084d7545c25b5fdad09fef3eaa75a543fae28aa988921df782118.jpg)  
Figure.1 Schematic diagram of the liver tumor microwave hyperthermia   
图2模型网格划分与初始温度场  
Fig.2 The mesh and the initial temperature field of the model

# 2.2探针加热后的温度场

在初始温度场分布的基础上，加入微波热源。持续加热100s后的温度场如图3中左图所示，可以看出，此种探针形成了沿探针前后方向不对称的椭球形温度场，相同半径位置处垂直于探针方向的温度要明显低于沿探针方向的温度。为此本文选取肿瘤中心点1作为肿瘤中心温度监测点，选取肿瘤边缘外$1 \mathrm { m m }$ 的点2、点3、点4作为肿瘤灭活监测点，具体布置如图3中右图所示。

![](images/d617bd0b1962f8d8d3bbb892418eb05f1af936855aebb6c9848c0eb495835c1b.jpg)  
图3100s后的温度场和监测点、路径示意图

图4所示为微波持续加热过程中监测点温度随时间变化曲线；图5所示为加热100s后沿半径方向（图3中右图所示路径位置）的温度分布曲线。

![](images/77f125871d62518a15bab1ca4332cdcb7a12369c9d9c31f751d34a36b3aaeb08.jpg)  
Fig.3The temperature fieldforheating $1 0 0 \mathrm { s }$ byantenna and schematic diagram of measuring point and path

![](images/6734c3d72708fa52f713e7957367a39d2e445c59445ee74fc3173c2f9328ef0e.jpg)  
Fig.4 The time histories of the monitoring points' temperature   
图5沿半径的温度分布曲线  
Fig.5 The temperature distribution curve along radius

从图4温度曲线可以看出，当探针持续加热 $1 0 0 \mathrm { ~ s ~ }$ 后，肿瘤中心点1温度已达 $1 3 7 ^ { \circ } \mathrm { C }$ ，此温度会使肿瘤中心失水炭化，影响之后的热疗进程；同时三个肿瘤灭活监测点的最低温度值也已达 $9 2 ^ { \circ } \mathrm { C }$ ，严重伤害到周围组织。从图5温度分布曲线中可以看出沿着半径方向温度逐渐减低，在半径为 $0 . 0 2 5 \mathrm { ~ m ~ }$ 时温度趋于定值 $3 7 . 5 \mathrm { ^ { \circ } C }$ 。

# 3基于温度控制的热疗模拟

在微波热疗过程中，温度控制是通过实时监测来实现的，然而在现有条件下，有损测量会给病人增加痛苦；无损测量的精度暂时无法满足治疗过程中的要求。针对以上缺陷，本文运用数值模拟预演热疗过程，提出基于温度控制的热疗方案，实现既能杀死整个肿瘤组织，又能保证周围正常组织不受过度损伤。

# 3.1温度控制原则

为了获得一个理想的肿瘤热疗效果，加热时必须满足以下条件： $\textcircled{1}$ 在限定的时间内将肿瘤组织加热到 $4 3 ^ { \circ } \mathrm { C }$ 以上，并维持一定时间； $\textcircled{2}$ 在肿瘤组织内不能存在 $4 1 ^ { \circ } \mathrm { C }$ 以下的冷点； $\textcircled{3}$ 肿瘤周围组织温度必须保持在 $4 5 \mathrm { ^ \circ C }$ 以下[9]。

# 3.2控制方案

从图4可以看出当探针加热14s时，点4的温度为$4 5 ^ { \circ } \mathrm { C }$ ，点2、点3的温度为 $5 1 \mathrm { { ^ \circ C } }$ 左右，点1的温度为$5 4 ^ { \circ } \mathrm { C }$ ，对应的温度场分布如图6中左图所示。因此，为了保证热疗的效果，满足温度控制原则，必须控制使点4的温度满足热疗的要求，此时点2、点3的温度也不至于太高，不会过度伤害正常组织。

![](images/fd322222f88f23c5bdead2c7eb6502838413f9181c49f6ea073b29e107a6ba1c.jpg)  
图4监测点的温度随时间变化曲线  
图6热疗方案进行 $1 4 \mathrm { ~ s ~ }$ 、200s时的温度场  
Fig.6 Temperature fieldafter $1 4 ~ \mathrm { s }$ and $2 0 0 \mathrm { ~ s ~ }$ in heat treatment plan

按照温度控制原则，加热14s后关闭微波探针停止加热，让热量从中心高温处逐渐向外围低温处传导，此时由于血液的影响，将带走中心热量，从而使肿瘤与组织的温度降低。到200s时，对应的温度场如图6中右图所示，点2的温度下降到 $4 3 . 8 ^ { \circ } \mathrm { C }$ ，点3温度下降到 $4 4 . 1 ^ { \circ } \mathrm { C }$ ，点4下降到 $4 3 ^ { \circ } \mathrm { C }$ ，点1下降到$4 5 . 8 ^ { \circ } \mathrm { C }$ ，满足温度控制的要求，能够杀死肿瘤而不

损坏正常组织。

# 3.3热疗模拟

通过对模拟过程中相应的监测点的观测，本文制定了基于温度控制的热疗模拟，既能控制肿瘤中心点温度不会过高而炭化，也能控制肿瘤边缘温度，达到彻底消灭肿瘤且不损伤正常组织的要求。对温度控制，是通过控制探针的开关来实现的。接通微波探针，肿瘤边缘监测点4从初始温度 $3 7 . 5 \mathrm { ^ { \circ } C }$ 升高至$4 5 \mathrm { ^ \circ C }$ 后关闭探针，待监测点4温度降至 $4 3 ^ { \circ } \mathrm { C }$ 后再打开探针，以此控制整个热疗过程的温度。热疗模拟过程温度变化曲线如图7所示，可以看出，首次接通微波探针的加热时间为 $1 4 \mathrm { ~ s ~ }$ ，关闭探针的冷却时间为$1 8 6 ~ \mathrm { s }$ ，后续加热周期约为4s左右，冷却周期约为152s左右。

![](images/41e13a57420904a4ecb3cc2b3a530f5ab217c3b9089ac92781484878c15b1fb0.jpg)  
图7监测点基于温度控制随时间变化曲线  
Fig.7 The time histories based on the monitoring points

# 4结论

本文提出了基于温度控制的热疗方案，通过数值模拟预演了 $9 1 5 ~ \mathrm { { M H z } }$ 的单点介入式微波热源杀死肿瘤的热疗过程，数值模拟结果表明，可设定初期微波探针加热时间 $1 4 \mathrm { s }$ ，之后冷却至 $2 0 0 \mathrm { ~ s ~ }$ ，随后呈周期性加热与冷却，加热时间约为4s，冷却时间约为$1 5 2 \mathrm { ~ s ~ }$ ，可控制肿瘤中心最高温度在 $5 4 ^ { \circ } \mathrm { C }$ 以下，肿瘤边缘温度在 $4 3 { \sim } 4 5 ^ { \circ } \mathrm { C }$ 之间变化，达到控制肿瘤中心温度不致过高、同时杀死肿瘤又不会过度损伤周围组织的目的。

# 参考文献

[1]赵世俊．肿瘤热疗研究进展．国外医学临床放射学分册 [J].2004,27(4): 252-255 Zhao ShiJun.Advance in Tumor Hyperthermia. Foreign Medical Sciences Clinical Radiological Fascicle [J].2004, 27(4): 252-255   
[2]朱光明，刘伟，杨昆，等．肿瘤微波热疗的温度场预示及 热损伤研究[J].工程热物理学报 2005，6第26卷增刊 Zhu Guangming, Liu Wei, Yang Kun, et al， The Temperature and Thermal Injury Research for Microwave Thermal Therapy of Tumor [J]. Journal of Engineering Thermophysics.   
2005. Vol. 26 Supplement [3] 程志刚.915MHz植入式内冷却微波消融肝组织三维热场 计算机模拟及动物实验研究 [D].北京:中国人民解放军总 医院军医进修学院,2005 Cheng Zhigang.915 MHZ Implanted Internally Cooled MicrowaveAblation:Computer-simulationThreedimensional Thermal Fields of Liver Tissue and Experimental Study in Porcine Livers [D]. Beijing: The general hospital of Chinese People's Liberation Army, 2005 [4] Ryan TP,Patel SJ,Morris R,eta1. Three-dimensional Finite Element Simulations of Vertebral Body Thermal Treatment [C]// Proceedings of the SPIE-The International Society for Optical Engineering，2005: 137-155. [5] J. Lang, B. Erdmann and M. Seebass, Impact of Nonlinear Heat Transfer on Temperature Control in Regional Hyperthermia [J]. IEEETransactionson Biomedical Engineering. 1999, 46(9): 1129-1138. [6] 陈新，B超监测下的肝癌介入微波热凝固术的有限元模拟 [D]，北京：北京工业大学，2001 Chen Xin, Finite Element Analysis of Invasive Microwave Coagulation of Liver Tumors with B-Mode Ultrasonography Monitoring [D],Beijing:Beijing Universityof Technology,   
2001 [7] 刘方义，植入式水冷915MHz微波消融三维热场计算机模 拟及临床应用研究[D]．北京：中国人民解放军总医院军 医进修学院，2009 Liu Fangyi, 915MHz Microwave Ablation with Cooled-shaft antennae: the Experimental Study of Computer-simulated Three-dimensional Thermal Fields and the Study of Clinical Application [D], Beijing, The General Hospital of Chinese People's Liberation Army, 2009 [8] Subhadeep Mitra, C. Balaji. A Neural Network Based Estimation of Tumour Parameters from a Breast Thermogram [J].International Journal of Heat and Mass Transfer. 53 (2010) 4714-4727 [9] 刘静，邓中山．肿瘤热疗物理学[M]．北京；科学出版社，   
2008 Liu jing, Zheng zhongshan. Physics of Tumor Hyperthermia [M] Beijing; Science Press, 2008