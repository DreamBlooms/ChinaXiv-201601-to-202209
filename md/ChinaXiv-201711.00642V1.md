# 地热有机朗肯循环系统混合工质优化

刘广林，徐进良，苗政(华北电力大学 低品位能源多相流与传热北京市重点实验室，北京 102206)

摘要：本文针对低温饱和有机朗肯循环发电系统，以R134a、R245fa和R423a为有机工质，采用 EES 软件模拟分析有机朗肯循环发电系统膨胀机入口温度对系统输出功及其他参数的影响，确定低温有机朗肯循环发电系统的最佳工质选择。结果表明：随着膨胀机入口温度的增加，有机朗肯循环发电系统或膨胀机输出功存在最大值，且采用非共沸混合物R423a时系统或膨胀机输出的功最大，比采用R245fa为工质时系统输出功增加 $1 4 . 9 \%$ ；发电系统有机工质质量流量随膨胀机入口温度的增加呈相反趋势变化，回灌温度则与膨胀机入口温度变化趋势基本一致。

关键词：有机朗肯循环；非共沸混合物；地热发电；工质中图分类号：TK123 文献标识码：A

# Optimal of Mixtures Working Fluids for Geothermal Organic Rankine Cycle System

LIU Guang-Lin, XU Jin-Liang, MIAO Zheng (North China Electric Power University,Beijing Key Laboratory of Multi-phase Flow and Heat Transfer of Low-grade Energy,Beijing 102206, China)

Abstract:In this work, a thermodynamic analysis on the low temperature saturated organic Rankine cycle power generation system was carried out based on the software EES. The effects of the expander inlet temperature on the system output power and other operation parameters were studied. The system performances when using $\mathrm { R } 1 3 4 \mathrm { a }$ 、R245fa and R423 as working fluid were compared in order to select the suitable working fluid. The results showed that the maximum value of the expander output power existed with the increase in the expander inlet temperature. The system power achieved maximum when using non-azeotropic mixtures R423a as working fluids and it was about $14 . 9 \%$ higher than that using R245fa.The mass flow rate of working fluids became smaller with the increase in the expander inlet temperature, while the recharge temperature of geothermal fluids showed a consistent trend with the increasing expander inlet temperature.

Key words: organic Rankine cycle; azeotropic mixtures; geothermal power plant; working fluids

# 0引言

随着我国经济的快速增长，对能源的需求日益增加，同时化石能源短缺的问题日益严重，且出现各种环境问题。合理开发利用新能源日益成为人们聚集的焦点，地热能作为一种可再生能源，备受人们青睐。有机朗肯循环发电系统利用低品位热源将低沸点有机工质加热至气态，推动膨化机做功，可以实现低品位能源转换为高品位电能，在环保，效率等方面具有一定的优势。目前，国内外学者对有机朗肯循环发电系统已进行大量研究，主要集中在：工质选择、系统热力学优化分析和主要设备的研制等方面。文献[1]采用基于模拟退火算法对14中有机工质进行有机朗肯循环发电系统的分热力学分析，得到R245fa和R245ca作为工质时系统性能较优。文献[2]提出反问题求解方法对低温有机朗肯循环发电系统进行分析，得到R134a为适合循环系统的最优工质。文献[3]研究工作表明$7 0 \ \mathrm { ^ { \circ } C }$ 太能能为热源时，当有机工质在膨胀机入口为干饱和状态时，有机工质R134a较好。文献[4,5]对非共沸混合物相对于纯工质进行了分析计算。有机朗肯循环发电系统主要由膨胀机、蒸发器、冷凝器和泵四个设备构成，已有研究表明，其中蒸发器的不可逆损失对系统性能影响最大。纯工质亚临界循环系统中蒸发器为等温沸腾，导致热源与工质温度匹配较差，蒸发器的不可逆损失较大，采用混合工质发电循环系统可实现蒸发器优化匹配，减少损失[7.8]。适合小容量有机朗肯循环发电系统的膨胀机尚属于空缺，处于样机研发阶段，国内外研究人员进行了理论和实验研究[,10]。目前对低温热源混合工质研究成果较少。

本文针对低温地热源，以有机朗肯循环发电系统膨胀机输出功及系统净输出功为主要评价指标，同时分析系统工质流量和地热水回灌温度等参数。采用EES（Engineering EquationSolver）软件进行模拟分析，比较亚临界饱和有机朗肯循环发电系统采用氢氟烃R134a（湿流体）、R245fa（干流体）和非共沸混合物R423a为有机工质时系统的性能，从而优选出适合低温地热源的有机工质，为低温地热源温度的有机朗肯循环发电系统工质的选用等做参考。

# 1有机朗肯循环发电系统热力学分析

# 1.1有机朗肯循环发电系统

基本有机朗肯循环发电系统如图1所示，发电系统工作原理：液态有机工质在蒸发换热器E中被加热到饱和状态后进入膨胀机膨胀做功，膨胀机输出的轴功扭动发电机发电；从膨胀机出口排出的有机工质进入冷凝器C与冷却水换热冷却后变为液体，液态有机工质经过工质泵 ${ \bf P } _ { 1 }$ 加压后再次进入蒸发换热器进行换热，从而完成一个封闭的发电循环。高温地热流体进入蒸发换热器与有机工质换热，将液态有机工质加热为气体，然后从蒸发换热器中排出，排出的地热流体进行回灌或其他应用；冷却系统中冷却水进入冷凝器将从膨胀机中排出的有机工质冷凝为液态，由冷凝器出口端排出的冷却水散热后再次进入冷凝器进行冷凝。整个循环发电系统主要由膨胀机，蒸发加热器，冷凝器及工质泵等设备构成。

![](images/387fe69a16a451b57bb66751bc722ff9bde2edf91cbdbb0de2d57fb497bdb598.jpg)

根据工质在膨胀机入口处状态不同，有机朗肯循环系统又分为亚临界和超临界发电系统，其中亚临界循环发电系统包括饱和蒸气发电系统、过热蒸汽循环及气液两相循环发电三种形式。本文仅分析亚临界饱和发电系统采用氢氟烃和非共沸混合物时系统性能，图2为湿流体亚临界饱和蒸气有机朗肯循环T-s图，过程4-5-1是有机工质在蒸发换热器中由液态定压加热至饱和汽态，过程1-2是有机工质在膨胀机中膨胀做功实际过程，过程1-2s是等熵膨胀，过程2-3是有机工质在冷凝器中定压冷却，过程3-4是有机工质被工质泵加压。

![](images/b6b19c9c51abdf096b38024686d30464bf3f8b9343cf769dc42664efd9bacc5c.jpg)  
图1有机朗肯循环发电系统图 Fig.1 Organic Rankine cycle power generation system diagram   
图2有机朗肯循环发电系统T-s图Fig.2 T-s diagram of organic Rankine cycle system1.2热力学模型分析及参数选定

本文对比非共沸混合物与氢氟烃类作为工质时亚临界饱和有机朗肯循环发电系统的膨胀机输出功和发电系统的净功，并对比有机工质质量流量和地热水回灌温度。膨胀机输出功 $\textstyle \mathcal { W } _ { t }$ 为有机工质的质量流量与膨胀机进出口工质焓值的乘积，如公式1所示：

$$
W _ { t } = m _ { w f } \cdot ( h _ { 1 } - h _ { 2 } )
$$

系统输出的净功 $W _ { \mathrm { n } }$ 为发电系统膨胀机输出的功 $\boldsymbol { W _ { t } }$ 与有机工质泵 $W _ { P 1 }$ 和冷却水泵耗功 $\boldsymbol { W } _ { P 2 }$ 的差值，如公式2所示：

$$
W _ { \mathrm { n } } = W _ { t } - W _ { P 1 } - W _ { p 2 }
$$

中有机工质泵耗功 $\boldsymbol { W } _ { P 1 }$ 和冷却水泵耗功 $\boldsymbol { W } _ { P 2 }$ 的计算如公式3、4所示

$$
W _ { p 1 } = m _ { w f } \cdot \mathbf { v } _ { 3 } \cdot ( p _ { 1 } - p _ { 2 } ) / \eta _ { p 1 }
$$

$$
W _ { p 2 } = m _ { w } \cdot g \cdot H _ { 1 } / ( \eta _ { p 2 } \cdot 1 0 0 0 )
$$

有机工质及冷却水质量流量的计算如公式5、6所示：

$$
m _ { w f } = c _ { b } \cdot m _ { g } \cdot \left( t _ { a } - t { } _ { 5 } - { \varDelta } t \right) / ( h _ { 1 } - h { } _ { 5 } )
$$

$$
m _ { w } = m _ { w f } \cdot \left( h _ { 2 } - h _ { 4 } \right) / [ \left( t _ { x } - t _ { y } \right) \cdot c _ { b } ]
$$

高温地热水经过蒸发换热器后回灌温度的计算如公式7所示：

$$
t b = t _ { a } - m _ { w f } \cdot ( h _ { 1 } - h _ { 4 } ) / ( c _ { b } \cdot m _ { g } )
$$

式中： $m _ { w f } , m _ { w } , m _ { g }$ 为有机工质、冷却水和地热流体质量流量， $\mathrm { k g / s }$ ; $t _ { a }$ 及 $t _ { b }$ 分别为热源流体经换热器的入口温度和出口温度， $\mathrm { { ^ \circ C } }$ ; $t _ { x }$ 及 $t _ { y }$ 分别为冷却水经换热器的出口温度和入□温度， $\mathrm { { ^ \circ C } }$ ; $h _ { 1 }$ 、 $h _ { 2 }$ 、 $h _ { 4 }$ 、 $h _ { 5 }$ 为对应图2中各点焓值， $\mathrm { k J / k g }$ ; $\eta _ { p I } \backprime \eta _ { p 2 }$ 分别为工质泵和冷却水泵效率； $p _ { 1 } , p _ { 2 }$ 及 $\mathbf { \sigma } _ { \nu _ { 3 } }$ 为工质在图2中对应点的压力和质量体积； $\varDelta t$ 为蒸发换热器中窄点温差， $\mathrm { { ^ \circ C } }$ ; $H _ { 1 }$ 为冷却水泵扬程， $\mathrm { ~ m ~ }$ ; $\boldsymbol { c } _ { b }$ 为地热流体平均比热，参考水的比热值取4.186$\mathbf { k J } / \mathbf { k g } { \cdot } \mathbf { K }$ 。

高压液态有机工质在蒸发换热器中被加热到饱和温度后进入膨胀机做功，在蒸发换热器换热中某一点使得地热流体和有机工质存在最小温差，称为窄点温差，用 $\varDelta t$ 表示，通常模拟计算取 $3 { \cdot } 7 ~ \ \mathring { \mathrm { C } } ^ { [ 1 1 ] }$ ，本文中按照 $7 \mathrm { { ^ { \circ } C } }$ 进行计算；文章模拟分析中地热流体质量流量取1$\mathrm { k g / s }$ ，温度假设为 $3 8 0 \mathrm { K }$ ；工质泵及冷却水泵效率取 $7 5 \%$ ，膨胀机内效率取 $80 \%$ ，冷却水温度取 $2 0 \ \mathrm { { ^ \circ C } }$ ，在冷却器中温升取 $5 \ \mathrm { { ^ \circ C } }$ ，冷却水泵扬程取 $2 0 \mathrm { m }$ ；有机工质在系统设备及管道中假设无压力损失，忽略其他因素影响。

# 2工质选择

工质的选用对有机朗肯发电系统性能有重要的影响，本文选用文献中推荐使用较多的干流体R245fa，湿流体R134a和混合工质R423a作为有机工质进行模拟分析。三种有机工质的性质如表1所示。

# 表1部分选用有机工质性质

Tab.1Property of selection working fluids   

<html><body><table><tr><td>工质名称</td><td>类别</td><td>临界温度 ℃</td><td>临界压力 MPa</td><td>备注</td></tr><tr><td>R134a</td><td>氢氟烃类</td><td>101.1</td><td>4.06</td><td>湿流体</td></tr><tr><td>R245fa</td><td>氢氟烃类</td><td>154.1</td><td>4.43</td><td>干流体</td></tr><tr><td>R423a</td><td>非共沸混 合物</td><td>99.1</td><td>3.56</td><td>R134a与 R227ea</td></tr></table></body></html>

# 3计算结果及分析

考虑到本文假设的地热流体的条件及有机工质的性质，模拟计算中取膨胀机的入口温度范围为 $5 5 ^ { \circ } \mathrm { C } { - } 8 0 ^ { \circ } \mathrm { C }$ 进行分析，具体计算结果如各图所示。图3和图4为发电系统中膨胀机输出功及发电系统净功随膨胀机入口温度的变化趋势。从图中可以看出，三种工质对应的输出功随膨胀机入口温度的增加呈现先增大后降低的趋势，即输出功存在最大值，且以非共沸混合物R423a为工质时输出功最大。这主要是由于非共沸混合物在蒸发换热器中与地热流体换热时，有机工质在两相区的换热过程不是等温的（图2中所示5-1过程)，而是温度不断升高，减少了蒸发换热器的不可逆损失，提高了能量的利用率，可见在380K地热流体为热源时，非共沸混合物R423a相对其他两种有机公式更适合低温地热发电系统。图3中所示的采用非共沸混合物R423a为工质时输出功最大为 $1 4 . 7 \mathrm { k W }$ ；采用干流体

R245fa为工质时，输出功最大时为 $1 2 . 5 \mathrm { k W }$ 。可见在相同的条件下，采用非共沸混合物R423a时，系统输出功比采用R245fa增加了 $14 . 9 \%$ 。

从图3和图4中可以看出，膨胀机和系统输出功最大时膨胀机的入口温度因工质的不同而不同；系统输出功扣除电站系统工质泵和冷却水泵耗功外与膨胀机输出功变化趋势是一致的。采用非共沸混合物R423a为有机工质时，当膨胀机入口温度为 $7 0 ^ { \circ } \mathrm { C }$ 时，膨胀机和系统输出功达到最大值；而采用R245fa为有机工质时，当膨胀机入口温度为 $6 0 ^ { \circ } \mathrm { C }$ 时，膨胀机和系统输出功达到最大值。

图5表示膨胀机入口温度与发电系统工质流量的关系，从图5中可以看出随着膨胀机入口温度的升高，有机工质质量流量减小，工质流量的变化规律一样。这是由于本文模拟计算时，设定了窄点温度，如公式5所示，在热源参数一定的情况下，当膨胀机入口温度增加或减小时，膨胀机入口焓值呈现增加或减小的同一趋势变化，而有机工质流量则呈现减小或增加相反的方向变化，且呈现直线关系。从图5中可以得到，对于相同的膨胀机入口，以有机工质R423a的质量流量最大，R245fa的质量流量最小，这主要与有机工质的物性（比热等）有关。

![](images/7b8b950e053f15f0c9ff075109bd5bb45aa8d8134525ea087069c2b48e68942e.jpg)  
图3膨胀机入口温度与输出功的关系Fig.3 Expander inlet temperature versus system output power

![](images/9335f4b316ee535ad2133e2358510656c1b4127ddeebaf2d8cbd8752cc239b5a.jpg)  
图4膨胀机入口温度与系统净功的关系Fig.4 Expander inlet temperature versus output net power

地热源发电为可持续性的新能源发电，这是因为回灌低温地热水将在地壳中进行热量，高温地热流体重新进入发电系统，相对应太阳能、风能等具有高度稳定性的特点。但是回灌温度在一定程度上影响高温地热流体的温度，直接影响系统的输出功。因此回灌温度对地热发电系统的性能有重要的影响。图6表示地热流体经过蒸发换热器后回灌温度与膨胀机入口温度的关系。从图中可以看出，有机公式的回灌温度随着膨胀机入口温度的增加而增加，且在相同的膨胀机入口温度下，有机工质R423a的回灌温度最低。如公式7所示，地热流体回灌温度主要与膨胀机入口温度相关，且呈现相同的变化趋势。因此需要根据系统输出功及回灌温度对系统的影响等因素最优确定地热流体回灌温度。以工质R423a为例，当系统输出功或膨胀机输出功最大时，地热流体回灌温度为 $6 1 ^ { \circ } \mathrm { C }$ 。

![](images/0e0bf8e658901586ce10e2bc4351103aa597b3f5addd4951edf871094d9e98d0.jpg)  
图5膨胀机入口温度与工质流量的关系  
Fig.5Expander inlet temperature versus working mass flow

![](images/93ccfb33fd84749a0a3f24f4efd2181c4f38fa16a0d67e4ae3c576a1309ad0a0.jpg)  
图6膨胀机入口温度与地热水排水温度的关系  
Fig.6 Expander inlet temperature versus injection temperature of geothermal water 4结论

针对热源为380K低温亚临界饱和有机朗肯循环发电系统，采用非共沸混合物R423a和R134a、R245fa氢氟烃类有机工质时进行对比分析，得到以下结论：

1.对低温有机朗肯饱和循环发电系统，采用非共沸混合物时系统或膨胀机输出的功比采用氢氟烃类有机工质时大，R423a为工质时系统输出功比采用R245fa为工质时增加了$14 . 9 \%$ 。

2.随着膨胀机入口温度的增加，有机朗肯循环发电系统输出功存在最大值，且当输出功达到最大值时，不同工质对应的膨胀机入口温度不同，以有机工质R423a的入口温度最大。3.发电系统有机工质流量和地热流体回灌温度随着膨胀机入口温度的增加基本呈现直线的变化趋势，流量呈相反趋势变化，而回灌温度则与膨胀机入口温度变化趋势基本一致。

# 参考文献

[1]王娟丽，何雅玲，程泽东等．基于模拟退火算法的有机朗肯循环的性能优化[J]．工程热物理学报, 2013,9(34):1606-1610 WANG Juanli, HE Yaling, CHENG Zedong, et al. Performance Optimization of Organic Rankine Cycle Based on Simulated Annealing Algorithm[J]. Journal of Engineering Thermophysics,2013,9(34): 1606-1610 [2]刘超，徐进良，陈奇成等．低温跨临界有机朗肯循环工质筛选[J]．中国电机工程学报,2013,23(33): 37-43 LIU Chao,Xu Jinliang, CHEN Qicheng,et al. Working Fluid Selection for Low Temperature Transcritical Organic Rankine Cycle[J].Proceedings of the CSEE,2013,23(33): 37-43 [3]Bertrand FT,George P,Gregory L.Fluid Selection foraLow-temperature Solar Organic Rankine Cycle[J]. Applied Thermal Engineering,2009,29: 2468-2476 [4] Chen Huijuan, Goswami DY,Muhammad MR, et al. A Supercritical Rankine Cycle Using Zeotropic Mixture Working Fluids for the Conversion of Low-grade Heat into power[J]. Energy,2011,36(1): 549-555 [5] Wang X D, Zhao L. Analysis of Zeotropic Mixtures Used in Low-temperature Solar Rankine Cycles for Power Generation[J]. Solar Energy,2009,83(5): 605-613 [6]Mago P J,Srinivasan K K, Chamra L M,et al. An Examination of Exergy Destruction in Organic Rankine Cycles[J]. International Journal of Energy Research,2008,32(10): 926-938 [7]Schuster A, Karellas S, Aumann R.Efficiency Optimization Potential in Supercritical Organic Rankine Cycles[J].Energy,2010,35(2):1033-1039

[8]Florian H, Markus P,Dieter B. Zeotropic Mixtures as Working Fluids in Organic Rankine Cycles for Low Enthalpy Geothermal Resources[J].Renewable Energy,2012,37(1): 364-370   
[9]Taniguchi H,Kudo K,Park I,et al.Analytical and Experimental Investigation ofTwo-phase Flow Screw Expanders forPower Generation[J].Journal ofEngineering for Gas Turbines and Power,1988,110(10): 628-635 [10]顾伟，孙绍芹，翁一武等．采用涡旋膨胀机的低品位热能有机物朗肯循环发电系统实验研究[J]．中国 电机工程学报,2011,31(17):20-25   
GU Wei,SUN Shaoqin,WENG Yiwu, et al.Experimental Study on Low Grade Heat Driven Organic Rankine Cycle by Scroll Expander[J].Proceedingsof the CSEE,2011,31(17): 20-25   
[11]严家．低温热能发电方案中选择工质和确定参数的热力学原则和计算式[J].工程热物理学报,1982, 3(1): 1-7   
Yan Jialu. Thermodynamic Principles and Formulas for Choosing Working Fluids and Parameters in Designing Power Plant of Low Temperature Heat[J]. Journal of Engineering Thermophysics,1982,3(1): 1-7