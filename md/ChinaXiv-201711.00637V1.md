# 乙烷着火化学反应动力学机理研究

陈毅臻，胡二江\*，张自航，潘伦，黄佐华(西安交通大学动力工程多相流国家重点实验室，西安710049)

摘要：本文利用激波管测量了乙烷在不同压力、温度和当量比下的着火延迟期，并利用CHEMKIN 软件结合GRI-Mech3.0机理对预混合气着火过程进行了模拟计算和化学反应动力学分析。结果表明，GRI-Mech 3.0机理不能很好的预测乙烷的着火延迟期。通过对着火过程进行敏感性分析，得出反应 $\mathrm { C } _ { 2 } \mathrm { H } _ { 5 } { + } \mathrm { O } _ { 2 } { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 4 } { + } \mathrm { H } \mathrm { O } _ { 2 }$ 和 $\mathrm { C } _ { 2 } \mathrm { H } _ { 4 } \mathrm { + } \mathrm { H } \mathrm { + } \mathrm { M } \mathrm { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 5 } \mathrm { + } \mathrm { M }$ 对着火延迟期的影响较大，并对其反应速率常数进行了修正。修正后的机理能够较好地改善对乙烷着火延迟期的预测，并同时保持了对层流燃烧速度的准确预测。

关键词：乙烷；着火延迟期；GRI-Mech3.0机理；化学反应动力学；敏感性分析中图分类号：TF055 文献标识码：A

# Study on the chemical kinetic mechanisms of ethane ignition

CHEN Yi-Zhen,HU Er-Jiang’ZHANG Zi-Hang,PAN Lun,HUANG Zuo-Hua tate Key LaboratoryofMultiphaseFlow in Power Engineering,Xi'anJiaotong University,Xi'an 710049

China)

Abstract: Ignition delay times of ethane were measured behind reflected shock waves under different pressures， temperatures,and equivalence ratios. Simulations and chemical kinetic analysis on the ignition process of the mixtures were carried out using CHEMKIN II package with GRI-Mech 3.0 mechanism.The simulation results showed large scatters with the experimental data especially at lean mixtures. Reaction （20 $\mathrm { C } _ { 2 } \mathrm { H } _ { 5 } \mathrm { + } \mathrm { O } _ { 2 } \mathrm { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 4 } \mathrm { + } \mathrm { H O } _ { 2 }$ and reaction $C _ { 2 } \mathrm { H } _ { 4 } \mathrm { + } \mathrm { H } \mathrm { + } \mathrm { M } { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 5 } \mathrm { + } \mathrm { M }$ were found to havesignificantinfluenceon the ignition process of ethane,and their rate constants were modified in order to give more accurate prediction. The optimized mechanism can give better prediction of ignition delay times of ethane and maintains its good prediction onthe laminar flame speed.

Key words:ethane; ignition delay time; GRI-Mech 3.0; chemical kinetic; sensitivity analysis

# 0引言

当今世界面临着化石能源不可再生并日益枯竭的问题，同时污染气体排放与温室气体控制的压力巨大，因此提高化石能源的燃烧效率并同时寻找清洁的替代燃料是全球共同的研究热点。有关低碳燃料的燃烧基础研究在解决这两大难题的过程中占有十分重要的地位，其中就包括乙烷的燃烧与化学反应动力学研究。首先，乙烷是天然气中次于甲烷的最重要的一种组分，而天然气则是目前发展最为成功的代用燃料之一。其次，乙烷作为中间产物广泛地存在于碳氢化物的氧化过程中，而且许多较大分子碳氢化物的化学反应动力学机理都是以低碳碳氢化物的化学反应动力学机理为基础构建的。因此，详细而准确地研究乙烷的化学反应动力学，对于理解乙烷的燃烧氧化过程，和发展更大分子燃料的化学反应机理，都是十分重要的。

着火延迟期是描述燃料着火特性的基础参数，是实际燃烧装置燃烧室设计和优化的重要依据，同时也是构建燃料动力学模型的必要数据。国际上对于乙烷着火延迟期的测量和研究已经有很多。在1970 年，Bowman[]率先使用激波管测量了乙烷在压力为 $0 . 2 \mathrm { - } 0 . 8 \ \mathrm { M P a }$ 下的着火延迟期。Cooke等人[2在1975年测量了乙烷在高温下 $1 4 0 0 { - } 2 2 0 0 \textrm { K }$ 的着火延迟期。Hidaka等人[3-4]利用激波管研究了乙烷的热解和氧化机理并测量了其中间物种的浓度。Shim等人[5]和Lamoureux等人[也都在激波管上测量过乙烷的着火延迟期。Tranter等人[7利用激波管研究了超高压力下（34MPaand $6 1 . 3 \mathrm { M P a }$ ）乙烷的热解和氧化，发现已有机理能较好预测超高压力下乙烷着火延迟期de Vries等人[8测量了乙烷的着火延迟期并与前人的实验结果作了对比，发现不同研究者测得的乙烷着火延迟期的拟合式有一定差异。由此可见，虽然乙烷的着火延迟期已被广泛地测量过，其热解和氧化机理也已经被较详尽地研究，但是实验数据主要集中于压力在 $0 . 0 2 \mathrm { - } 1 . 0 \mathrm { M P a }$ ，当量比为0.5-2.0之间。在更广泛工况下更丰富的实验数据有利于乙烷着火化学反应动力学机理进一步的发展。

本文采用激波管和CHEMKIN软件研究乙烷在不同温度和压力下的着火延迟期。研究混合气初始参数（温度、初始压力和燃料浓度）对着火延迟期的影响，重点研究和验证了乙烷的化学反应动力学机理——GRI-Mech 3.0 机理。该研究获得的基础实验数据既可以丰富乙烷基础燃烧数据，同时也对发展乙烷化学动力学模型起到促进作用。

# 1实验方法与计算方法

# 1.1实验装置和方法

本文测量着火延迟期的实验利用激波管实验平台完成。由不锈钢钢管组成的激波管管体被PVC膜分成低、高压段两部分，长度分别为 $5 . 3 \mathrm { m }$ 和 $2 . 0 \mathrm { m }$ 。激波管在实验前抽真空至 $1 \times 1 0 ^ { - 3 } \mathrm { k P a }$ 以下。三个压力传感器（PCB113B26）安装在距离实验段端面不同位置处，用于测量入射激波速度，并通过一维理想正激波方程计算反射激波后的温度和压力。实验混合气在不锈钢混气灌中混合 $2 4 \mathrm { ~ h ~ }$ 以上，配气前混气罐抽真空至 $1 \times 1 0 ^ { - 3 } \mathrm { k P a }$ 以下。通过安装在低压段端面处的压力传感器（PCB113B03）和相同位置的光电倍增管（PMT）共同诊断混合气的着火。PMT前放置窄带通滤光片，用于探测波长 $4 3 0 \mathrm { n m }$ 的 $\mathrm { C H ^ { * } }$ 自发光信号。详细的实验装置介绍见文献[9]。

表1激波管实验混合气组分  
Table 1 Compositions of the test mixtures   

<html><body><table><tr><td colspan="5">ruoreTConposrronsOrtnetesthnxtures</td></tr><tr><td>混合气</td><td></td><td>Xethane/% X02/%</td><td>XAr/%</td><td>p/MPa</td></tr><tr><td>1</td><td>0.5</td><td>1.0 7.0</td><td>92.0</td><td>0.12, 0.5, 2</td></tr><tr><td>2</td><td>1.0</td><td>1.0 3.5</td><td>95.5</td><td>0.12, 0.5, 2</td></tr><tr><td>3</td><td>2.0</td><td>1.0 1.75</td><td>97.25</td><td>0.12,0.5, 2</td></tr><tr><td>4</td><td>1.0</td><td>0.75 2.625</td><td>96.625</td><td>0.5</td></tr><tr><td>5</td><td>1.0</td><td>1.5 5.25</td><td>93.25</td><td>0.5</td></tr><tr><td>6</td><td>1.0</td><td>2.0 7.0</td><td>91.0</td><td>0.2,0.5</td></tr><tr><td>7</td><td>0.5</td><td>0.25 1.75</td><td>98.0</td><td>0.11</td></tr></table></body></html>

实验所用的乙烷纯度为 $9 9 . 9 \%$ ， $\mathbf { O } _ { 2 }$ 纯度为$9 9 . 9 9 5 \%$ ，Ar和He 纯度为 $9 9 . 9 9 9 \%$ 。实验工况为：当量比为0.5、1.0、2.0。着火压力 $\mathsf { p } { = } 0 . 1 2 { - } 2 . 0 \ \mathrm { M P a }$ 混合气中各成分的摩尔分数如表1所示。

![](images/ea755e21609775623abbf0e7943a99fb1dcaffc92abe5228c356debbf7311438.jpg)  
图1着火延迟期定义  
Fig.1The definition of ignitiondelaytime

图1给出了本文着火延迟期的定义。着火延迟期定义为入射激波到达激波管端面的时刻与 $\mathrm { C H ^ { * } }$ 信号曲线最大斜率处切线在基线处交点之间的时间间隔。首先，通过位于壁面及端面的四个压力传感器(PCB,B26)测得压力数据和压力升高的时刻，并触发三台位于壁面的时间间隔计数器(FLUKEPM6690)。然后，对所得的三个时间间隔进行线性插值可以推算入射激波速度。 $\mathrm { C H ^ { * } }$ 信号是由位于端面的光电倍增管测得。

# 1.2计算方法和化学反应机理

本文还利用化学反应动力学软件CHEMKIN中的 SENKIN 模块对乙烷的自着火特性进行了数值模拟和动力学分析。本文所用机理为GRI-Mech3.0机理[10].同时，基于本文的实验数据和 DeSain 等人[11]的计算结果，本文对GRI-Mech3.0机理进行了敏感性分析并进行修正，修正后的机理能够同时较好地预测乙烷的着火延迟期和层流燃烧速度。

# 2结果与分析

# 2.1着火延迟期实验值的验证

图2给出了在压力为 $0 . 1 1 \ \mathrm { M P a }$ ，当量比为0.5，乙烷摩尔分数为 $X _ { \mathrm { e t h a n e } } { = } 0 . 2 5 \%$ 时，以及压力为 $0 . 2 \mathrm { M P a }$ 当量比为1，乙烷摩尔分数为 $X _ { \mathrm { e t h a n e } } { = } 2 \%$ 时，deVries等[8的实验结果与本研究的实验结果对比。可以看出，在这两个工况下本文的实验结果与deVries等人的实验结果吻合很好，说明本文的实验结果具有较好的重复性，对于验证乙烷的化学反应动力学机理有很好的参考。

![](images/5d6074f056ae9b5eb47a0d8a1538f1aa25f65440a9de9f2dafd4bf5542f0a37c.jpg)  
图2着火延迟期实验值对比

# 2.2着火延迟期实验值与计算值对比

图3给出了乙烷着火延迟期实验测量值和计算值的对比。点为激波管实验值，虚线为GRI-Mech3.0机理的计算值，实线为修正后GRI-Mech3.0机理的计算值。由图可知，在当量比和燃料浓度不变的情况下，初始压力越高乙烷的着火延迟期越短，而在初始压力和当量比不变的情况下，燃料浓度越高乙烷的着火延迟期越短，说明初始压力和燃料浓度的提高对乙烷的着火有促进作用。由乙烷着火延迟期的计算值可以看出，在当量比为0.5和1.0的工况下，GRI-Mech3.0对乙烷着火延迟期的计算值都明显高于实验值，在个别工况下两者的差别甚至达到一个数量级。因此，本文对GRI-Mech3.0机理进行了修正，在这两种工况下，而修正后的机理能够较好地预测乙烷的着火延迟期。而在当量比为2.0的工况下，原机理与修正后机理的预测情况均不理想，有待进一步的研究。以下部分通过化学反应动力学分析详细地阐述了对机理的修正过程。

# 2.3化学反应动力学分析

为了确定各基元反应对着火延迟期的影响，本文对乙烷的着火延迟进行敏感性分析。敏感性分析

![](images/981166d5c01f1d4c41eaafad1e3a062493863b276e9925b1b5c29ae4d5b7b271.jpg)  
Fig.2 Comparison between present measured data and the measured data fromreference   
图3着火延迟期实验值与计算值对比（点：实验值；虚线：GRI-Mech3.0计算值；实线：修正后的GRI-Mech3.0计算值）

Fig.3Comparison between experimental and modeling results (Symbols: measurement; dash dot lines: GRI-Mech 3.0; solid lines: Modified GRI-Mech 3.0)

是指定量地研究某一因素发生变化时对结果的影响程度，根据Petersen 等人[12的定义，着火延迟期的敏感性系数如下公式所示：

$$
S = \frac { \tau ( 2 . 0 k _ { i } ) - \tau ( 0 . 5 k _ { i } ) } { 1 . 5 \tau ( k _ { i } ) } (
$$

其中 $\tau$ 为着火延迟期， $k _ { i }$ 为第 $i$ 个基元反应速率系数。敏感性系数为正的反应生成稳定的产物或自由基，降低总体反应活性，使着火延迟期增加；而敏感性系数为负的反应能够生成活性更强的自由基或更多的自由基，增强总体反应活性，使着火延迟期缩短。由于低压时原机理的着火延迟预测偏差较大，故主要对该工况进行敏感性分析。图4给出了 $p { = } 0 . 1 2  { \mathrm { M P a } }$ $T = 1 2 5 0 ~ \mathrm { K }$ ， $\phi = 0 . 5$ 条件下GRI-Mech3.0机理着火延迟期的敏感性系数。与其他碳氢燃料相似，在高温条件下R8（ $\mathrm { \Delta ( H + O _ { 2 } = O + O H }$ ）是敏感度最大的促进着火的反应。在列出的敏感性系数最大的11个反应中，与乙烷燃料分子相关的反应有6个：

R74: $\mathrm { C _ { 2 } H _ { 4 } + H ( + M ) = C _ { 2 } H } _ { 5 } ( + M )$ R78: $\mathrm { C } _ { 2 } \mathrm { H } _ { 6 } \mathrm { + } \mathrm { H } \mathrm { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 5 } \mathrm { + } \mathrm { H } _ { 2 }$ R112: $\mathrm { C } _ { 2 } \mathrm { H } _ { 4 } \mathrm { + O H } { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 3 } \mathrm { + H } _ { 2 } \mathrm { O }$ R158 $: 2 \mathrm { C H } _ { 3 } ( + \mathrm { M } ) { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 6 } ( + \mathrm { M } )$ R175: $\mathrm { C } _ { 2 } \mathrm { H } _ { 5 } { + } \mathrm { O } _ { 2 } { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 4 } { + } \mathrm { H } \mathrm { O } _ { 2 }$ R294: $\mathrm { C _ { 2 } H _ { 3 } + O _ { 2 } } \mathrm { = C H _ { 2 } C H O + O }$ 其余均为小分子物种反应，这些小分子物种反应在验证其它燃料如氢气、甲烷等燃烧特性时，已经被大量的实验结果所验证，故本文对GRI-Mech3.0机理的修正主要集中在这6个与乙烷燃料分子相关的反应上。

![](images/6fccfdc100cbf8abce0ac9c110ddeabebe09c74793b1c967574902814fd6df83.jpg)  
图4着火延迟期的敏感性系数

Fig.4Sensitivity analysis of ignition delays

Zhang 等人[13]在对乙烷进行反应路径分析时发现乙烷大部分是被生成乙基的脱氢反应所消耗。生成的乙基会进一步发生脱氢反应，其中部分乙基与氧原子发生反应生成乙烯和 $\mathrm { H O } _ { 2 }$ 自由基。DeSain等人[11]在2003年提出了 $\mathrm { C } _ { 2 } \mathrm { H } _ { 5 } { + } \mathrm { O } _ { 2 }$ 的反应速率常数的理论计算值，它包含多个反应通道。由于本文的研究范围主要集中于高温区，而在高温区 $\mathrm { C } 2 \mathrm { H } 5 { + } \mathrm { O } 2 \$ 的反应通道主要是 ${ \bf C } _ { 2 } \mathrm { H } _ { 5 }$ 与 $\mathbf { O } _ { 2 }$ 的直接脱氢反应，即$\mathrm { C } _ { 2 } \mathrm { H } _ { 5 } \mathrm { + } \mathrm { O } _ { 2 } \mathrm { = } \mathrm { C } _ { 2 } \mathrm { H } _ { 4 } \mathrm { + } \mathrm { H O } _ { 2 }$ ，因此在GRI-Mech3.0机理中只考虑这一反应通道具备一定的合理性。但是GRI-Mech3.0中R175的反应速率常数的值与DeSain等人的理论计算值相差很大。在将 ${ \mathrm { C } } _ { 2 } { \mathrm { H } } _ { 5 }$ 与 $\mathrm { O } _ { 2 }$ 的直接脱氢反应的DeSain等人的理论计算值代入GRI-Mech3.0后，预测的着火延迟期明显降低，但是在个别工况下仍然高于实验值。此外，反应中大部分乙基则会发生单分子反应生成乙烯与H自由基，从而增加反应中H自由基的浓度。事实上链分支反应R74能明显促进乙烷的着火。考虑到原机理预测的乙烷着火延迟期过长，在将R74的反应速率常数的高压极限和低压极限同时提高一倍以后，修正后的机理能够相对较好地预测着火延迟期的变化。本文的实验与模拟工作为R74反应速率常数的改进提供参考与依据，为R74的反应速率常数的高精度计算提供了重要参考。

为了进一步验证修正后机理对乙烷层流燃烧速度的预测，图5给出了GRI-Mech3.0对乙烷的层流燃烧速度的计算值与修正后机理的计算值的对比。从图中可以看出，修正后的机理与原机理在乙烷层

![](images/bec9c5125794c9fa2c573acbf34847a6dfbb7849531b09689136b7e22f53bc2d.jpg)  
图5层流燃烧速度实验值与计算值的对比（点：实验值；虚线：GRI-Mech3.0计算值；实线：修正后的GRI-Mech3.0计算值)

Fig.5 Comparison between experimental and modeling results of laminar flame speed (Symbols:measurement;dash dot lines:

GRI-Mech 3.0; solid lines:Modified GRI-Mech 3.0)流燃烧速度的预测上差别并不大。根据Hassan等人[14]及Jomaas 等人[15]的实验值，GRI-Mech 3.0 对乙烷的层流燃烧速度的预测较为准确。所以修正后的机理在维持了原机理对乙烷层流燃烧速度的较准确的预测结果的基础上，对GRI-Mech3.0的乙烷着火延迟期的预测有所改善。

# 3结论

本文利用激波管和化学反应动力学软件CHEMKIN开展了不同温度、压力、当量比和燃料浓度时乙烷的着火延迟期测量和动力学分析，获得的主要结论如下：（1）获得了乙烷不同条件下的着火延迟期，在本研究工况范围内，压力的增加和当量比的增加对着火有明显的促进作用。着火延迟期的对数与温度的倒数呈良好的线性关系。（2）着火延迟期的实验值和计算值对比发现，GRI-Mech3.0机理预测的着火延迟期偏高。（3）通过敏感性分析，找出了GRI-Mech3.0机理中影响乙烷着火延迟期最主要基元反应，并对其速率常数进行了优化，修正后的机理能够较好的预测实验结果。

# 参考文献

[1] Bowman C T.An Experimental and Analytical Investigation of the High-Temperature Oxidation Mechanisms of Hydrocarbon Fuels[J].Combustion Science and Technology，1970,2(2-3): 161-172.   
[2] Cooke DF,Williams A. Shock Tube Studies of Methane and Ethane Oxidation[J]. Combustion and Flame,1975,24: 245-256. [3] Hidaka Y,Tanaka Y,Kawano H, et al.Mass Spectrometric Study of C2-Hydrocarbons-Oxidation in Shock Waves[J]. Journal of the Mass Spectrometry Society of Japan,1981,29(2): 191-198.   
[4]Hidaka Y,Sato K,Hoshikawa H,et al.Shock-Tube and ModelingStudy ofEthane Pyrolysisand Oxidation[J]. Combustion and Flame,2000,120(3):245-264.   
[5] Shim S, Jeong H S, Shin S. Shock Tube Study of Ignition in Ethane-Oxygen-Argon Mixtures[J]. Journal of the Korean ChemicalSociety, 1999, 42: 575-578.   
[6]Lamoureux N,Paillard C E,Vaslier V.Low Hydrocarbon Mixtures Ignition Delay Times Investigation behind Reflected Shock Waves[J]. Shock Waves,2002,11(4): 309-322.   
[7] Tranter R S, Sivaramakrishnan R,Brezinsky K,et al. High Pressure，High Temperature Shock Tube Studies of Ethane Pyrolysis and Oxidation[J].Physical Chemistry Chemical Physics,2002,4(11): 2001-2010.   
[8] de Vries J, Hall JM, Simmons S L, et al. Ethane Ignition and Oxidation behind Reflected Shock Waves[J]. Combustion and Flame,2007,150(1):137-150.   
[9] Hu Erjiang, Jiang Xue,Huang Zuohua,et al. Experimental and Kinetic Studies on Ignition Delay Times of Dimethyl Ether/N-Butane/O2/ArMixtures[J].Energy& Fuels,2012, 27(1): 530-536.   
[10] Smith G P，Golden M D，Frenklach M,et al. http://www.me.berkeley.edu/gri_mech/   
[11]DeSain J D，Klippenstein S J，Miller J A，et al. Measurements, Theory，and Modeling of OH Formation in Ethyl+O2 and Propyl+O2 Reactions[J].The Journal of Physical Chemistry A,2003,107(22): 4415-4427.   
[12] Petersen E L，Davidson D F，Hanson R K.Kinetics Modeling of Shock-Induced Ignition in Low-Dilution CH4/O2 Mixtures at High Pressures and Intermediate Temperatures[J]. Combustion and Flame,1999,117(1): 272-290.   
[13] Zhang Jiaxiang,Hu Erjiang, Zhang Zihang，et al. Comparative Study on Ignition Delay Times of C1-C4 Alkanes[J].Energy& Fuels,2013,27(6): 3480-3487.   
[14] Hassan M I,Aung K T,Kwon O C,et al. Properties of LaminarPremixedHydrocarbon/AirFlamesatVarious Pressures[J]. Journal of Propulsion and Power,1998,14(4): 479-488.   
[15] Jomaas G, Zheng Xiaolin, Zhu Delin,et al.Experimental Determination of Counterflow Ignition Temperaturesand Laminar Flame Speeds of C2-C3 Hydrocarbons at Atmospheric and Elevated Pressures[J].Proceedings of the Combustion Institute,2005,30(1): 193-200.

# 附页

陈毅臻  
地址：西安市西安交通大学兴庆校区硕3013班1693  
信箱  
手机：15594992891  
E-mail: cyzlmh@gmail.com