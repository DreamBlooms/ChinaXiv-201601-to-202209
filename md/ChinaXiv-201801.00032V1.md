编号：161221

# 机房自然冷却用 $\mathrm { C O } _ { 2 }$ 热虹吸管实验与节能分析

张海南1,2邵双全1,²田长青1,2金听祥3（1.中国科学院低温工程学重点实验室，理化技术研究所，北京100190;2.热力过程节能技术北京市重点实验室，中国科学院理化技术研究所，北京100190;3.郑州轻工业学院，郑州450002）

摘要：数据中心机房自然冷却技术作为一种有效的数据中心节能冷却方法日益受到重视。基于热虹吸管的自然冷却装置具有小温差下优异的传热性能，有着良好的应用前景。本文针对以 $\mathrm { C O } _ { 2 }$ 为工质的机房自然冷却用热虹吸管进行了实验和节能效果分析研究，并与R22进行了对比。实验结果表明，与以R22为工质相比， $\mathrm { C O } _ { 2 }$ 热虹吸管性能受充液率的影响更加明显。最佳充液率为 $1 5 0 \%$ ，高于R22。对于处于最佳充液率的情况， $\mathrm { C O } _ { 2 }$ 和 R22热虹吸管的传热量均随室内外温差的增加而增大，且 $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量高于R22。当充液率或室内外温差较小时，蒸发器上部存在蒸干区，随充液率或温差的增大而逐步消失。节能效果分结果表明采用 $\mathrm { C O } _ { 2 }$ 工质替代R22可以显著提升数据中心全年的热虹吸自然冷却时间。

关键词：数据中心；自然冷却；热虹吸管； $\mathrm { C O } _ { 2 }$

中图分类号：

文献标识码：A

# Experimental investigation and energy-saving analysis of a ${ \mathsf { C O } } _ { 2 }$

# thermosyphon for free cooling of data centers

ZHANG Hai-Nan1² SHAO Shuang-Quan1² TIANChang-Qing1,² JIN Ting-Xiang3 (1. Key LaboratoryofCryogenics,Technical Institute ofPhysics and Chemistry, CAS,Beijing 100190,China;

ijingKeyLaboratoryofealSieneandTechnologyTechicalIstituteofysicsandChemistryCAS,Beijng9,C

3. Zhengzhou University ofLight Industry, Zhengzhou 45oo02,China)

Abstract: Free cooling is attracting more and more attentions as an effective method for energy-saving of data center cooling.Free cooling equipment based on termosyphon has good heat transfer performance under smal temperature diference therefore it has good application potential.This paper investigates the performance and the energy-saving effect of a thermosyphon with $\mathrm { C O } _ { 2 }$ as the working fluid for free cooling of data centers and compared with that of R22. The experimental results show that the performance of $\mathrm { C O } _ { 2 }$ thermosyphon is affected more significantly by the filling ratio compared with R22 thermosyphon. The optimal filling ratio is $1 5 0 \%$ ,higher than R22.For the conditions with optimal filling ratio, the heat transfer rates of $\mathrm { C O } _ { 2 }$ thermosyphon and R22 thermosyphon both increase with indoor and outdoor temperature difference, and the heat transfer rate of $\mathrm { C O } _ { 2 }$ thermosyphon is higher than that of R22.When the filing ratioor the temperature difference is small,there is dryout region in the upper part of theevaporator, which disappears withthe increase oftemperature diference or filingratio.The energy-saving analysis shows that the annual thermosyphon free cooling time of a data center will be improved obviously when $\mathrm { C O } _ { 2 }$ is utilized instead of R22.

Key words: Data center; Free cooling; Thermosyphon; $\mathrm { C O } _ { 2 }$

# 0引言

耗已经成为数据中心节能减排的必然要求，相关的节能制冷技术得到了快速发展。

随着信息产业的飞速发展，数据中心的数量和能耗也在迅猛增长，目前全球数据中心能耗已占全世界总能耗的 $1 . 1 \mathrm { - } 1 . 5 \% ^ { [ 1 ] }$ 。在数据中心能耗的组成中，制冷系统能耗超过 $30 \%$ [2,3]。因此，降低制冷能

传统数据中心机房全年均通过压缩机做功获取冷源，消耗大量电能。对我国大部分地区来说，全年有相当多的时间室外气温低于室内温度，利用这部分时间中自然界的低温冷源冷却数据中心，可以节约压缩机的能耗，这一技术称之为自然冷却。以热虹吸管为传热设备的自然冷却技术由于相变传热效果好、不破坏室内空气质量和湿度环境，是具有良好应用潜力的自然冷却方法。近年来利用热虹吸管的自然冷却受到广泛关注，很多学者针对不同结构形式、不同工况与充液率下自然冷却用热虹吸管的性能进行了实验和仿真研究[4-8]。同时热虹吸管换热器的全年能耗特性，以及围护结构、设定温度的影响也有研究[9,10]。

然而，目前大多数研究以氟利昂作为工质[4-10]。这一类工质处于环保的考虑即将被替代，因此研究环保型工质充注下的性能是热虹吸自然冷却未来发展与应用的必然要求。 $\mathrm { C O } _ { 2 }$ 作为环境友好型工质，具有良好的热力性质，适合作为这一领域氟利昂的替代工质。目前，针对 $\mathrm { C O } _ { 2 }$ 热虹吸管的研究还十分有限。Tong等[1,12]实验研究了 $\mathrm { C O } _ { 2 }$ 热虹吸管的性能,研究表明 $\mathrm { C O } _ { 2 }$ 充注下的传热量与R22相比更高，且以蒸发器内容积为标准的最佳充液率为 $100 \%$ 。由于目前这一领域的研究结果有限，且研究中热虹吸管的换热器均为翅片管式换热器，因而有必要针对$\mathrm { C O } _ { 2 }$ 热虹吸管特别是不同换热器形式下的 $\mathrm { C O } _ { 2 }$ 热虹吸管的性能进行研究，并探究其温度和循环流动特性。

本文针对采用微通道平行流蒸发器和冷凝器的$\mathrm { C O } _ { 2 }$ 热虹吸管，研究其在不同充液率与工况下的性能和节能效果，并与R22充注下进行对比。为探究其循环流动特性，采用红外热成像方法对 $\mathrm { C O } _ { 2 }$ 热虹吸管的温度分布进行了分析。本文的研究结果对于$\mathrm { C O } _ { 2 }$ 热虹吸管、特别是采用微通道平行流换热器的热虹吸管的设计与应用具有指导意义。

# 1 实验装置

实验针对带有微通道平行流蒸发器与冷凝器的$\mathrm { C O } _ { 2 }$ 分离式热虹吸管进行。采用焓差实验台进行实验，实验装置如图1所示。蒸发器放置在室内侧，冷凝器放置在室外测，二者保持1.0米高差以维持工质循环。采用FLIR公司T610型热成像仪记录热虹吸管蒸发器的温度分布。

热虹吸管的结构参数和实验的工况参数如表1所示。蒸发器和冷凝器均采用微通道平行流换热器，上升管和下降管采用空调用铜管。

# 2结果与分析

# 2.1传热量分析

不同充液率下，充注 $\mathrm { C O } _ { 2 }$ 的热虹吸管与充注R22情况下的性能对比如图2所示。室内外温差保持为$1 0 ~ ^ { \circ } \mathrm { C }$ 。可见，随着充液率的增加， $\mathrm { C O } _ { 2 }$ 与R22充注下热虹吸管的传热量均是先增加后下降。 $\mathrm { C O } _ { 2 }$ 的最佳充液率约为 $1 5 0 \%$ ，低于最佳充液率的情况下， $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量下降明显，但高于最佳充液率的情况下， $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量变化不大；R22的最佳充液率约为 $1 1 0 \%$ ，高于或低于其最佳充液率，传热量变化幅度相对较小。可见，以 $\mathrm { C O } _ { 2 }$ 为工质的热虹吸管与以R22为工质相比，更加适合较大的工质充液率，在充液率较低情况下的传热量受到的影响更为明显，应尽量避免充液不足的情况。

![](images/bd7ced4a76133c37898cded6200b38d8b009f2b2cc81a5721b5423d6a7eead41.jpg)  
图1实验装置（a）室内侧；（b）室外侧Fig.1Experimental facility (a) Indoor (b) Outdoor

表1热虹吸管结构参数与实验工况  
Table 1 Geometry parameters and working conditions of the thermosyphon   

<html><body><table><tr><td>参数</td><td>值</td><td>参数</td><td>值</td></tr><tr><td>扁管高/mm</td><td>2.0</td><td>上升管长/内径/m</td><td>2.71/0.017</td></tr><tr><td>扁管宽/mm</td><td>25.4</td><td>下降管长/内径/m</td><td>2.71/0.014</td></tr><tr><td>扁管长/mm</td><td>710</td><td>室内温度/℃</td><td>20.0</td></tr><tr><td>管间距/mm</td><td>10.0</td><td>室内相对湿度</td><td>50%</td></tr><tr><td>管数</td><td>63</td><td>室外温度℃</td><td>4.0~14.0</td></tr><tr><td>排数</td><td>1</td><td>蒸发器风量/ms1</td><td>0.52</td></tr><tr><td>高度差/m</td><td>1.0</td><td>冷凝器风量/ms1</td><td>0.80</td></tr></table></body></html>

![](images/221a90151f385ea3bd498f3c773b0a7c9f8d34bccdd2b9d03c8e576960e3ba85.jpg)  
图2传热量随充液率的变化

Fig.2Heat transferratevariedwith fillingratio不同室内外温差下，充注 $\mathrm { C O } _ { 2 }$ 的热虹吸管与充注 R22情况下的性能对比如图3所示。实验中 $\mathrm { C O } _ { 2 }$ 和R22的充液率分别为 $1 5 0 \%$ 和 $1 1 0 \%$ ，为各自的最佳充液率。如图3可见，两种工质充注下热虹吸管的传热量均随室内外温差的增大而几乎线性增加，在相同的室内外温差下， $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量与R22相比有明显提高。可见， $\mathrm { C O } _ { 2 }$ 适合作为数据中心自然冷却用热虹吸管的替代工质。

![](images/cb0971b9e3c4e15f4896cccdb35be02838adf16ff4e1a0dda0914ec89b6ecc9b.jpg)  
图3传热量随室内外温差的变化

# 2.2热成像分析

为进一步研究 $\mathrm { C O } _ { 2 }$ 热虹吸管的温度分布和循环流动特性，对不同充液率与温差下 $\mathrm { C O } _ { 2 }$ 热虹吸管进行了红外热成像分析。室内外温差为 $1 0 ^ { \circ } \mathrm { C }$ 时，不同充液率下蒸发器的热成像图如图4所示。可见，在较小充液率下，蒸发器上部热成像图呈红色（浅色），代表其壁面温度高于下部。这是由于蒸发器内的工质自下而上循环流动过程中，在某一部位发生蒸干，从而使得上部区域为气态工质，蒸发器壁面不能得到良好冷却因此温度较高。随着充液率的增加，蒸干区逐渐减小，在充液率达到 $1 5 0 \%$ 左右时，蒸干区完全消失。这也解释了上文最佳充液率为 $1 5 0 \%$ 的原因。

![](images/78facb60d0aa6e7fd5e61d979b5e9f649dba99f8fb11f3046e2c69046f568f9a.jpg)  
图4不同充液率下的蒸发器热成像图：(a) $1 1 0 \%$ ；(b) $120 \%$ (c) $1 3 0 \%$ ；(d) $140 \%$ ；(e) $1 5 0 \%$ ；(f) $1 6 0 \%$   
Fig.4 Thermal imaging of evaporator at different filling ratio: (a) $1 1 0 \%$ ； (b) $120 \%$ ；(c) $1 3 0 \%$ ；(d) $140 \%$ ；(e) $1 5 0 \%$ ；(f) $1 6 0 \%$

在充液率为 $1 5 0 \%$ 时，不同室内外温差下蒸发器的热成像图如图5所示。可见，当室内外温差较小时，蒸发器上部存在蒸干现象，但随着室内外温差的增加，蒸干区逐步消失。这是由于在较小的室内外温差下，系统内循环动力不足、循环流量较小，使得工质在蒸发器内受热后很快全部蒸发。可见，蒸干区的存在是小温差下的传热量较小的原因之一。

![](images/a60a4b7d35fc01a8c3e2de98f80049f72d0cc4c6a137492d4b46a6736af53235.jpg)  
Fig.3Heat transfer rate varied with indoor and outdoor temperature difference   
图5不同室内外温差下蒸发器热成像图：(a)温差 $6 ^ { \circ } \mathrm { C }$ ；(b)温差 $8 { } ^ { \circ } \mathrm { C }$ ；(c)温差 $1 0 ^ { \circ } \mathrm { C }$ ；(d)温差 $1 2 ^ { \circ } \mathrm { C }$ ；(e)温差 $1 4 ^ { \circ } \mathrm { C }$ ：(f)温差 $1 6 ^ { \circ } \mathrm { C }$   
Fig.5 Thermal imaging of evaporator at different indoor and outdoor temperature: (a) $6 { } ^ { \circ } \mathrm { C }$ ；(b) $8 { } ^ { \circ } \mathrm { C }$ ；(c) $1 0 ^ { \circ } \mathrm { C }$ ；(d) $1 2 ^ { \circ } \mathrm { C }$ (e) $1 4 ^ { \circ } \mathrm { C }$ ；(f) $1 6 ^ { \circ } \mathrm { C }$ （204号

# 2.3节能效果分析

从以上实验结果可见， $\mathrm { C O } _ { 2 }$ 工质作为自然冷却用热虹吸管的工质具有比传统工质R22更好的传热效果。为了研究 $\mathrm { C O } _ { 2 }$ 热虹吸管的节能前景，本节分析其节能效果并与R22进行对比。

采用图3的实验结果拟合 $\mathrm { C O } _ { 2 }$ 热虹吸管和 R22热虹吸管的制冷量与室内外温差的关系：

$$
Q _ { \mathrm { C O 2 } } { = } { - } 0 . 0 0 2 0 \Delta T ^ { 2 } { + } 0 . 3 6 9 5 \Delta T { - } 0 . 8 5 3 8
$$

$Q _ { { \mathrm { R } } 2 2 } { = } 0 . 0 0 1 7 \Delta T ^ { 2 } { + } 0 . 2 7 1 7 \Delta T { - } 1 . 1 7 0 9$ (2)其中， $\scriptstyle Q _ { \mathrm { C O 2 } }$ 、 $\mathcal { Q } _ { \mathrm { R } 2 2 }$ 分别为采用 $\mathrm { C O } _ { 2 }$ 和 R22为工质的热虹吸管的制冷量， $\operatorname { k W }$ ； $\Delta T$ 为室内外温差， $^ { \circ } \mathrm { C }$ 。

对于某信息设备发热量 $4 ~ \mathrm { k W }$ 的模块化数据中心，室内环境温度设定为 $2 7 ^ { \circ } \mathrm { C }$ 。采用热虹吸自然冷却设备其全年自然冷却的时间为热虹吸管制冷量大于信息设备发热量的总时间。结合哈尔滨、北京、上海、广州四个城市的天气数据[13]，分别计算使用以 $\mathrm { C O } _ { 2 }$ 和R22为工质的热虹吸管的全年自然冷却时间如图6所示。可见，采用 $\mathrm { C O } _ { 2 }$ 工质之后可以显著提升全年的热虹吸自然冷却时间。同时，对于我国南方地区自然冷却时间的提升效果比北方地区更加显著。

![](images/8721eba999414fdc40da5ecf482985db43315266140998cd28a6758aee7ece5b.jpg)  
图 $6 \mathrm { C O } _ { 2 }$ 和R22为工质的热虹吸管自然冷却时间对比 Fig.6 Comparison on the free cooling time of $\mathrm { C O } _ { 2 }$ thermosyphon and R22 thermosyphon

# 3结论

基于热虹吸管的自然冷却技术是数据中心节能冷却的理想方法。本文针对带有微通道平行流蒸发器和冷凝器的分离式热虹吸管，研究 $\mathrm { C O } _ { 2 }$ 作为工质的系统性能和节能效果，并与R22进行了对比。主要结论如下：（1） $\mathrm { C O } _ { 2 }$ 和R22的最佳充液率分别约为 $1 5 0 \%$ 和$1 1 0 \%$ ，与R22相比， $\mathrm { C O } _ { 2 }$ 更加适合较大的工质充液率。低于最佳充液率的情况下， $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量下降明显。两种工质充注下热虹吸管的制冷量均随室内外温差的增大而增加，在相同的室内外温差下， $\mathrm { C O } _ { 2 }$ 热虹吸管的传热量与R22相比更大。（2）在较小充液率下，蒸发器上部存在蒸干区，随着充液率的增加，蒸干区逐渐减小，在充液率达到$1 5 0 \%$ 左右时，蒸干区完全消失。当室内外温差较小时，蒸发器上部存在蒸干区，但随着室内外温差的增加逐步消失。（3）采用CO2工质替代R22可以显著提升数据中心全年的热虹吸自然冷却时间。我国南方地区自然冷却时间的提升效果比北方地区更加显著。

# 参考文献

[1] Koomey J.Growth in Data Center Electricity Use 2005 to 2010 [R]. Oakland, CA: Analytics Press; 2011.   
[2]Ebrahimi K,Jones GF,Fleischer AS.Thermo-economic AnalysisofSteady StateWasteHeatRecoveryinDataCenters Using Absorption Refrigeration[J]. Appl Energy 2015;139: 384-97.   
[3]安真.数据中心的节能分析[J].智能建筑电气技术,2011, 5(5): 62-64. AN Zhen. Energy-saving Analysis Of Data Centers[J]. Electrical Technology of Intelligent Buildings, 2011,5(5): 62-64.   
[4]钱晓栋,李震,李志信.数据机房热管空调系统的实验研究 [J].工程热物理学报,2012,33(7):1217-1220. QIAN Xiaodong, LI Zhen, LI Zhixin. Experimental Study on Data Center Heat Pipe Air Conditioning System[J]. Journal of Engineering Thermophysics,2012,33(7): 1217-1220.   
[5] Zhang P, Wang B, Shi W, et al. Experimental Investigation on Two-Phase Thermosyphon Loop with Partially Liquid-Filled Downcomer[J]. Applied Energy,2015,160: 10-17.   
[6] Chehade A，Louahlia-Gualous H,Masson SL，et al. Experimental Investigationsand Modeling of a loop ThermosyphonforCoolingwithZeroElectrical Consumption[J]. Applied Thermal Engineering, 2015,87: 559-573.   
[7] Zhang P, Wang B, Shi W, et al. Modeling and Performance Analysis of a Two-Phase Thermosyphon Loopwith Partially/Fully Liquid-Filled Downcomer[J]. International Journal ofRefrigeration, 2015,58:172-185.   
[8] Zhang H, Shao S, Xu H, et al. Simulation on the Performance and Free Cooling Potential of the Thermosyphon Mode in an IntegratedSystem of Mechanical Refrigerationand Thermosyphon[J].Applied Energy, 2017,185:1604-1612.   
[9]周峰,田昕,马国远.IDC机房用热管换热器节能特性实验 研究[J].土木建筑与环境工程,2011,33(1):111-117. ZHOU Feng, TIAN Xin,， MA Guoyuan. Energy-saving Performance of Thermosyphon Heat Exchanger Applied in Internet Data Center[J]. Journal of Civil,Architectural & Environmental Engineering, 2011,33(1): 111--117.   
[10] Zhou F, Tian X,MaG Investigation into the Energy Consumption of a Data Center with a Thermosyphon Heat Exchanger[J]. Chinese Sci. Bull.,2011,56 (20): 2185-2190.   
[11] Tong Z, Ding T,Li Z, et al. An Experimental Investigation of an R744 Two-Phase Thermosyphon Loop Used to Cool a Data Center[J]. Applied Thermal Engineering,2015,90: 362-365.   
[12] Tong Z,Liu X,Li Z, et al. Experimental Study on the Effect ofFill Ratio on an R744 Two-Phase Thermosyphon Loop[J]. Applied Thermal Engineering,2016,99: 302-312.   
[13] Song F, Zhu Q,Wu R,et al. Meteorological Data Set for Building Thermal Environment Analysis of China[C]//Proceedings of the 10th International Building Performance Simulation Association Conferenceand Exhibition. Beijing: 2007, 9-16.   
联系人：   
张海南   
15810538105   
010-82543433-6   
zhanghn $@$ mail.ipc.ac.cn   
北京市海淀区中关村东路29号中国科学院理化技术   
研究所