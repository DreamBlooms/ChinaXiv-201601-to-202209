# 微波热点出现与维持的物理机制探讨

马建毅\*,a 胡永鑫a(四川大学原子与分子物理研究所 四川 成都 601165)

摘要微波加热反应和传统加热反应相比有反应速度快、产率高等特点。微波反应中不同于传统加热的现象被称为"微波效应”。被观测到的微波效应包括热现象、热点现象、选择性加热等。理解和有效控制微波效应中的微波热点效应对理解和应用微波加热至关重要。基于我们 2016 年提出的微波反应量子态识别主方程模型，本文研究发现微波热点这种非线性现象的出现，宏观上与体系的温度的不均匀分布及微波强度有关，微观上与微波吸收导致的非平衡行为直接关联。本文建议可以通过预先加热反应容器中的空间局域点从而在该点诱发微波热点，也可以通过激发特定分子中的局域基团来诱导分子内热点的形成。可控微波热点效应有望应用在其它领域，本文的结论表明从量子态层面理解宏观非平衡和非线性行为的物理机制是必要的。

关键词微波热点；非平衡；主方程模型；量子态；非热效应

# Discussion on the physical mechanism of the emergence and maintenance of microwave hotspots

Jianyi Ma\*,a Yongxin ${ \mathrm { H u } } ^ { a }$ (aSichuan University,InstituteofAtomicandMolecular Physics,Chengdu,Sichuan 61o65,P.R.China.)

AbstractMicrowave heating hasbeensuccessfullyapplied inchemistry.Compared withthe traditional heatingreaction,the microwave heating reaction has the characteristics ofhighreactionrate,high yieldandmildreaction conditions.The phenomenon different from thetraditional heating inmicrowavereaction iscaled "microwaveeffect".Theobserved microwave effects includethermal efects,superheatingorhotspotsandselective heating.These phenomenaarealmost impossibleinclasicalheatingandtheexistenceofnon-thermal efects isstillacontroversialtopic.Thehotspotefectisa phenomenonwhichisoftenobservedinmicrowavereactionandissignificantlydifferentfromthetraditionalheatingreaction. So,itis veryimportanttounderstandandcontrolthemicrowavehotspotefectinmicrowaveeffect.Inthispaper,weusethe quantum state specified master equation model of microwave reaction proposed in 2016 to studythe possible mechanismof microwave hotspots.The model includescollsion energy transfer terms,microwave energy transfer terms,andchemical reactionterms.Intheexperiment,thetemperatureofthemicrowaveotspotisigherthanthesurounding temperature,andit is oftenaccompaniedbyluminescence,sowedividethehotspots modelinto spacehotspotsandintramolecularhotspots,which correspond to thermalconductionand luminous behavior,respectively.Although the appearance of microwave hotspots is random,the probabilityofmicrowavehotspotsappearinginthesystem ishigherafterthetemperaturerises.Theappearanceof this non-linear phenomenonis related totheunevendistributionoftemperatureand microwave intensityin the macroscopic level,anddirectlyrelatedtothenonequilibriumbehaviorcausedbymicrowaveabsorptioninthemicroscopiclevel.Inthis paper,it issuggestedthatmicrowavehotspotscanbeinducedbyheating the givenregions inthereactionvesslinadvance, andthe formationofintramolecularhotspotscanalsobeinducedbyexciting thelocal groups inspecific molecules.Theresults showthat it is ncesary tounderstand the physical mechanismofmacroscopic nonequilibriumand nonlinear behavior from the quantum state level.

Keywordsmicrowave hotspots; nonequilibrium; master equation model; quantum state; nonthermal effect

# 1引言

微波化学是目前发展比较快速的一个新兴领域，与传统加热反应化学相比,它具有独特的优势[1,2]。特别是在有机合成中，微波反应表现出产率高、反应时间短及反应条件温和等特点。人们甚至还发现了一些在加热条件下不能发生，在微波条件下却可以发生的反应[3,4]。在研究中，通常用“微波效应"来描述微波反应中不同于传统加热的现象，进一步的，又将微波效应分作热效应和非热效应来解释一些由单纯加热不可能实现的特性。其中，在微波非热效应是否存在的问题上还有很多争议[5-9]。实验上，由于加热机制不同，分别用微波和传统加热无法构造出相同的温度场，使得微波非热效应无法从热效应中分离出来研究。理论上，使用非平衡分子力学模拟的方法也无法给出非热效应的合理定义[10]。同时，许多研究表明，对微波非热效应更敏感的是生物体系，如在 $4 5 ^ { \circ } \mathrm { C }$ 以上时，暴露于微波辐射下的大肠杆菌的死亡率高于在相同温度下常规热灭菌的大肠杆菌死亡率[1]。所以，研究并发现微波反应的完整机制对更有效的利用这项技术进行有机合成等问题都至关重要。

目前，常被观测到的微波效应包括过热现象，热点现象，选择性加热等，这些现象在传统加热中并不存在。详细研究这类现象的微观机制有助于全面认识微波效应。其中，微波热点效应很容易被观察到。据报道，有的热点的出现与溶液中活性炭的颗粒大小和浓度有关，有的和其它的成分有关，也有的是随机出现的[12]。热点的出现是否有内在的物理机制，是什么样的原因造成了这种非线性行为[13]？众所周知，单个微波光子的能量是很小的，而很多微波热点出现时会伴随发可见光的情况，表明微波可以持续被热点吸收，使其达到可发光的能态。有意思的是，微波热点虽然会发出可见光，但这些热点的实测温度却并不很高。这些现象都是值得研究的。

我们基于量子动力学研究成果提出的微波反应量子态识别主方程模型有望描述各种微波效应。本文将利用该理论研究微波热点形成和维持的机制。首先，我们将讨论微波场作用下热点产生的原因、产生的条件和物理机制。其次，我们将讨论如何可控的产生空间热点和分子内热点。最后，我们将讨论可控非平衡效应产生和应用问题。

# 2计算细节

# 2.1 理论部分

微波反应量子态识别主方程模型中量子态密度的演化规律由主方程描述[14],

$$
\begin{array} { r l } & { \cfrac { d N ( S _ { \cdot } , t ) } { d t } } \\ & { = Z _ { \overline { { s } } } ^ { \ast } \Big [ P ^ { w \kappa } ( S _ { \cdot } ; S _ { \cdot } ^ { \prime } ) N ( S _ { \cdot } ^ { \prime } , t ) - P ^ { w \kappa } ( S _ { \cdot } ^ { \prime } ; S _ { \cdot } ) N ( S _ { \cdot } , t ) \Big ] } \\ & { + \sum _ { \overline { { s } } } ^ { \ast } \Big [ W ( S _ { \cdot } ; S _ { \cdot } ^ { \prime } ) N ( S _ { \cdot } ^ { \prime } , t ) - W ( S _ { \cdot } ^ { \prime } ; S _ { \cdot } ) N ( S _ { \cdot } , t ) \Big ] } \\ & { - \sum _ { k } ^ { k \operatorname* { m i n } } ( S _ { \cdot } ; S _ { \cdot } ^ { \prime } ) N ( S , t ) } \\ & { = Z _ { \overline { { s } } } ^ { \ast } \Big [ P w ( S _ { \cdot } ; S _ { \cdot } ^ { \prime } ) N ( S _ { \cdot } ^ { \prime } , t ) - P w ( S _ { \cdot } ^ { \prime } ; S _ { \cdot } ) N ( S _ { \cdot } , t ) \Big ] } \\ & { - \sum _ { k } ^ { k \operatorname* { m i n } } ( S _ { \cdot } ; S _ { \cdot } ^ { \prime } ) N ( S _ { \cdot } , t ) } \end{array}
$$

$$
P w ( S _ { i } ; S _ { i } ^ { \prime } ) = P ^ { M W } ( S _ { i } ; S _ { i } ^ { \prime } ) + W ( S _ { i } ; S _ { i } ^ { \prime } ) / Z
$$

其中 $\mathrm { N } ( \mathrm { S i } , \mathrm { t } )$ 表示分子内第i个区域S态在t时刻的密度分布，Z表示分子碰撞频率。 $P ^ { M W } ( S _ { i } ; S _ { i } ^ { \prime } )$ 表示微波环境下两个态之间的碰撞转移概率， $W ( S _ { i } ; S _ { i } ^ { \prime } )$ ）表示在微波作用下两个态之间的跃迁概率。 $k _ { j } ^ { M W } ( S _ { i } ; S _ { i } ^ { \prime } )$ 表示第i个区域S态向第j个区域分子内传能的速率的反应速率常数。我们假设本文讨论的微波热点效应不涉及反应过程，包含反应速率的项可以忽略，同时量子态指标S可以转换成能量指标。

上述模型中，包含了碰撞传能项，微波传能项和化学反应项，每一项遵循的规则在很多的文献里有讨论[15-17]。碰撞传能速率受温度、密度和压力的影响，一般发生的时间尺度为 $1 0 ^ { - 1 0 } \mathrm { s }$ 。简单起见，本文采用$Z = Z _ { o } T ^ { { \scriptscriptstyle I } / { 2 } }$ 计算碰撞频率，相应的碰撞传能函数采用常用的双指数函数形式[18]。

$$
P _ { { D o w n } } ^ { { M W } } ( S _ { i } , S _ { i } ^ { \prime } ) = e ^ { - ( S _ { i } ^ { \prime } - S _ { i } ) / ( C _ { l } + C _ { 2 } S _ { i } ^ { \prime } ) } , S _ { i } ^ { \prime } > S _ { i }
$$

$$
P _ { \mathrm { u p } } ^ { \mathrm { M W } } ( S _ { i } , S _ { i } ^ { \prime } ) / P _ { \mathrm { D o w n } } ^ { \mathrm { M W } } ( S _ { i } , S _ { i } ^ { \prime } ) = \frac { \rho _ { S _ { i } ^ { \prime } } } { \rho _ { S _ { i } } } e ^ { - ( S _ { i } ^ { \prime } - S _ { i } ) / k T }
$$

其中 $\mathrm { C } _ { 1 }$ 和 $\mathbf { C } _ { 2 }$ 为依赖于体系的参数， $\rho _ { s _ { i } }$ 是体系能量为 S 时的态密度，具体形式取作 $\rho _ { s } = \dot { 1 } 0 ^ { 0 . 0 7 \sqrt { s } }$ [19]。下标"Down”和"Up”表示分子在碰撞过程中失去或

者获得能量。微波的受激吸收和发射速率常数由 Lorentzian函数给出，

$$
W ( S _ { \scriptscriptstyle i } , S _ { \scriptscriptstyle i } ^ { \prime } ) = I \rho _ { s _ { \scriptscriptstyle i } ^ { \prime } } \frac { I } { \pi } \frac { \gamma } { ( \mid S _ { \scriptscriptstyle i } - S _ { \scriptscriptstyle i } ^ { \prime } \mid - \omega _ { o } \mathrm { \ } ^ { 2 } + \gamma ^ { 2 } }
$$

中 $\scriptstyle \infty 0$ 表示微波频率， $\gamma$ 表示阻尼常数， $\rho _ { s _ { i } }$ 表明速率正比于末态密度，I对应于微波场强度。此处为了简化模型，假设不同能级间的跃迁偶极大小相等。对于实际的体系跃迁偶极的变化行为我们在前期的工作中做了相关研究，一般来说高能级时体系的非谐性和对称性降低有利于微波的吸收和发射[20]

另外，我们假设分子内传能速率反比于能量传输值，即：

$$
k _ { j } ^ { \scriptscriptstyle M W } ( S _ { i } ; S _ { i } ^ { \prime } ) = k _ { i j } ( S _ { i } - S _ { i } ^ { \prime } + { \varDelta } ) ^ { \scriptscriptstyle T }
$$

其中， $\mathbf { k } _ { 0 }$ 为速率因子， $\Delta$ 为能量间距，且 $S _ { i } > S _ { i } ^ { \prime }$ ：

本文采取动力学蒙特卡洛(KMC)的方法求解上述主方程[18,21,22]。Gillespie 算法中每步演化需要的时间 $\tau$ 由随机数 $\mathbf { r } _ { 1 }$ 和该步总速率kTOT决定。

$$
\tau = - \ln ( r _ { \mathrm { 1 } } ) / k _ { \mathrm { \mathrm { r o r } } }
$$

假如某一时刻总共有M个可能的能量转移路径，每个路径的速率为 $\bf { k } _ { \mathrm { { i } } }$ ，则 $\begin{array} { r } { k _ { \scriptscriptstyle T O T } = \sum _ { i = I } ^ { M } k _ { i } } \end{array}$ 。能量转移路径 $\mathbf { m }$ 的选择决定于另外一个随机数 $\mathbf { r } _ { 2 }$ 。

表格1微波反应主方程模型参数(能量单位 $\mathbf { c m - 1 }$ 门 Table1Parameters of the master equation model of microwave reaction (Energy in cm-1)   

<html><body><table><tr><td>parameter</td><td>expression</td><td>value</td></tr><tr><td>Collision frequency</td><td>Z=ZoT-1/2</td><td>Z0 =1E+9</td></tr><tr><td rowspan="2">Collision energy transfer</td><td> P(S,S)></td><td>C=100,C= 0.015</td></tr><tr><td>PumW(S,S)/ Pw(S,S! )= Down</td><td>T=100K,300K,500 K</td></tr><tr><td>Absorption emission rate</td><td>1 2 W(S,S）</td><td>I=0,5E+10 and 5E+11 @=8 cm-1,γ= 0.12 cm-1</td></tr><tr><td>Intramolecular energy transfer</td><td>kyw(S;S')=kj(S,-S'+△)1</td><td>kij=0,10,100,△=△S</td></tr><tr><td>Energy grid</td><td colspan="2">grid number = 1500/2500 ,△S= 10 cm-1</td></tr><tr><td>Independent sampling</td><td colspan="2">500</td></tr></table></body></html>

# 2.2热点模型

实验中，微波热点的温度高于周围温度，且常伴有发光的现象。微波热点的温度相对较高表明吸收微波造成的能量增加比热传导和热辐射造成的能量损失大，伴有发光现象表明热点区域有些分子的能量会升高到可以发射可见光的能级[12]。为了简化模型，本文假设微波热点分成空间热点[23]（图1）和分子内热点（图2）两种情况，分别对应于热传导和发光行为。另外，我们假定微观上极性分子、分子内极性基团或极性团簇是吸收和发射微波的基本单元，这些基本单元的振转态分布与其表观温度相关。

空间热点如图1所示，热点的温度明显高于周围温度，并且能够在微波照射下持续存在。分子内热点如图2所示，其行为与碰撞传能和分子内传能速度有关。一个大分子内存在"温度"分别为T1，T2和T3的基团，这3个基团之间的传能速率为 $\bf k _ { \mathrm { i j } }$ ，并通过分子碰撞方式与周围环境实现传能。在微波作用下，同一个大分子内3个基团"温度"的改变可能存在差异。

![](images/18154cf8b4023359db7951891a166c1a4785cab6ba4dcd017d7e4a3ed6f8b795.jpg)  
图1空间热点示意图Figure 1 Schematic diagram of space hotspots

![](images/26d959b98fc8ef7552181ece2f0bf806fd5172871f929a487a55edd40d2adb97.jpg)  
图2分子内热点示意图，一个分子内存在“温度"分别为T1，T2和T3的基团，这3个基团之间的传能速率为kij，并分别与环境通过分子碰撞传能（由ke表示）

Figure 2Schematic diagram of intramolecular hotspots.In a molecule,there are three groups with "temperature"T1, T2,and T3 respectively.The energy transfer rate between these three groups present by kij,and the collision energy transfer rate between these groups and the environment is denoted by ke

# 3结果与讨论

使用量子态识别主方程模型结合上述的微波模型我们试图研究微波热点效应。试图厘清两个问题：一个是热点如何产生的，一个是热点如何维持的。

环境温度300K的分子在微波作用下振转能级随时间的变化行为如图3所示。红色散点表示在能级在强微波作用下的变化，蓝色散点表示纯热碰撞下的变化行为。其中的子图(b)和(c)分别截取了平衡震荡时段和强吸收时段的图像。从图3(a）可以看出，分子受到微波和热碰撞的双重作用。作用时间小于1.5us时，碰撞传能占主导地位，分子能态杂乱的震荡。从图3(b)可以看出，这段时间里分子能级在微波和热碰撞作用下的演化行为和单纯热碰撞作用下的演化行为相近。微波作用1.5 us后，分子内能忽然快速上升。从图3(c)所示的细节图可以看到在热碰撞作用下分子能级会有所震荡，但主要趋势是吸收微波造成的内能快速升高。

![](images/dac636fd558697d53061d99aa33a68f3a70c34170366a8ac190f74f8723adf02.jpg)  
图3环境温度 $\mathbf { 3 0 0 K }$ 的分子在微波作用下振转能级的变化行为。红点表示微波作用强度为 ${ \pmb 5 } { \bf E } { + } { \bf 1 } { 1 }$ ,蓝点表示无微波作用。子图(b)和(c)分别截取 平衡震荡时段和强吸收时段。 Figure 3Time evolution of vibrational energy levels of molecules at ${ \bf 3 0 0 ~ K }$ under microwave irradiation. Subgraphs (b) and (c) intercept the equilibrium oscillation period and strong absorption period, respectively.

我们还模拟了环境温度为 $5 0 0 \mathrm { K }$ 时，分子在强微波场下振转能级的演化行为，其结果如图4所示。在图中可以看到许多沿着竖直方向的线状散点，表征了分子快速吸收微波的过程。由于模拟的能级上限设置为$1 5 0 0 0 \mathrm { c m } ^ { - 1 }$ ，所以当能级到达能量上限后会由于微波发射和分子碰撞释放能量。实际上， $5 0 0 ~ \mathrm { K }$ 时我们使用的外加微波强度比300K时小10倍，但对比图3和图4可以看到，当环境温度为 $5 0 0 \mathrm { K }$ 时分子吸收微波从而能量快速上升的概率比 $3 0 0 \mathrm { K }$ 时大很多。同时，我们还模拟了环境温度100K时，分子能级在强微波下的演化行为，经过较长时间的模拟并没有发现微波快速吸收的现象。从中我们可以发现，虽然微波快速吸收对应的热点出现的时刻是随机的，但温度升高更有利于微波的吸收，体系有更大概率出现微波热点。

![](images/484c3122258e5aa68df24478a4d55a135d499724218256cf560883393fb1f86c.jpg)  
图4环境温度500K的分子在强度为 $\pmb { 5 } \mathbf { E } { + } \mathbf { 1 0 }$ 的微波作用下振转能 级的变化行为。 Figure 4Time evolution of vibrational energy levels of molecules at 500K under the action of microwave with the intensity of $\pmb { 5 } \mathbf { E } { + } \mathbf { 1 0 }$

图4中出现的代表能级快速上升的竖线另一方面表明强微波可以明显的改变分子内态的布居情况，使得体系能态分布行为不再服从一般的热平衡分布。但图中竖线出现的时间相对较短，是否本质的影响分子能态分布需要通过考察分子能态的时间分布确定。

$\mathbf { 5 E + 1 0 }$ 图5表示环境温度分别为 $1 0 0 ~ \mathrm { K }$ (a)和 $3 0 0 \ \mathrm { K } ( \mathrm { b } )$ 时，分子在微波作用下振转态的时间分布概率。其中黑点表示没有微波作用；红点表示微波强度 $\scriptstyle 1 = 5 \mathrm { E } + 1 1$ ，起始能级 $\mathrm { S = 1 0 0 0 ~ c m ^ { - 1 } }$ ；蓝点表示微波强度 $\scriptstyle 1 = 5 \mathrm { E } + 1 1$ ，起始能级 $\mathrm { S } { = } 1 0 0 0 0 \mathrm { c m } ^ { - 1 }$ 。 $1 0 0 \mathrm { K }$ 时，初始能级取 $1 0 0 0 \mathrm { c m } ^ { - 1 }$ ，是否加较强微波作用500次抽样平均后能级时间分布没有明显差别。当初始能级取 $\mathrm { S } { = } 1 0 0 0 0 \mathrm { c m } ^ { - 1 }$ 时，微波作用处于完全主导地位，在抽样的时间内能级全部处于高能区域。 $3 0 0 \mathrm { K }$ 时，不存在微波作用或微波强度较弱 $\scriptstyle ( \mathrm { I } = 1 \mathrm { E } + 5 )$ （20时能级的时间分布处于热平衡状态。存在强微波作用时，能级的时间分布偏离热平衡分布，高能区域的布居明显增加，表现出较强的非平衡特征。同时可以看到在$3 0 0 \mathrm { K }$ 时，起始能级对能量布居的影响较小。

大分子中各个基团的极性不同导致吸收微波的效率不同，不同基团间传热速度也会有所差别。研究表明分子内传能的时间尺度从毫秒量级到皮秒量级不等[24,25]。这些特征表明分子内热点是可能存在的。基于图2 所示的分子内传能模型我们模拟了不同温度、微波强度和分子内传能速率条件下分子内各个极性基团能级的演化行为。当分子内传能速率较大时，三个基团的能态分布趋于一致。当分子内传能速度较小的时候，各个基团的能态分布会有较大差别。图6画出了环境温度为100K(a)和 $3 0 0 ~ \mathrm { K } ( \mathrm { b } )$ 时的多热点分子在微波作用下3个不同基团的振动态分布图，其中一个基团的起始能级设置为 $\mathrm { S } { = } 1 0 0 0 0 \mathrm { c m } ^ { - 1 }$ ，其余的基团起始能级设置为 $\scriptstyle \mathbf { S } = 1 0 0 0$ $\mathrm { c m ^ { - 1 } }$ 。

从图6(a)可知，与空间热点的行为类似，当环境温度为 $1 0 0 \mathrm { K }$ 时，起始能级几乎决定了各个基团的能级分布行为。当起始能级取 $\mathrm { S } { = } 1 0 0 0 0 \ \mathrm { c m ^ { - 1 } }$ 时，500次抽样中一部分由于微波的受激发射和碰撞传能回到了低能级状态，一部分吸收微波达到更高的能级，导致分子内微波热点的出现。当环境温度为 $3 0 0 \mathrm { K }$ 时，三个极性基团都有一定概率快速吸收微波使得高能级布居上升。且起始能级取 $\mathrm { S } { = } 1 0 0 0 0 \mathrm { c m } ^ { - 1 }$ 时，快速吸收微波到达高能级的概率比初始态为 $\mathrm { S } { = } 1 0 0 0 \ \mathrm { c m } ^ { - 1 }$ 时高大约10倍。

![](images/fdde6187cde8134439454e9bea9fe4aa2018feb6f5a5ca72dd75aeea7afdc531.jpg)  
图5环境温度100K(a)和 ${ \bf 3 0 0 ~ K ( b ) }$ 的分子在微波作用下分子振转态分布图。黑点表示没有微波作用；红点表示微波强度 $\scriptstyle \mathbf { I = 5 E + 1 1 }$ ，起始能级$\scriptstyle \mathbf { S = 1 0 0 0 \ c m - 1 }$ ;蓝点表示微波强度 $\scriptstyle \mathbf { I = 5 E + 1 1 }$ ，起始能级 $\mathbf { S { = } 1 0 0 0 0 ~ c m { - } 1 }$ 。Figure 5Molecular vibrational state distribution of molecules at $\mathbf { 1 0 0 ~ K }$ (a) and $\mathbf { 3 0 0 ~ K }$ (b) under the action of microwave.Black dots indicate nomicrowave effect; red dots indicate microwave intensity ${ \bf I } = { \bf 5 } { \bf E } { + \bf 1 1 }$ ,initial energy level $\mathbf { S } = \mathbf { 1 0 0 0 ~ c m { - 1 } }$ ; blue dots indicate microwave intensity $\mathbf { I } =$ ${ \pmb 5 } { \bf E } { + } { \bf 1 1 }$ ,initial energylevel $\mathbf { S } = \mathbf { 1 0 0 0 0 } \mathrm { c m } \mathbf { - 1 }$

从上述的模拟结果可以看出微波传能方式和碰撞传能方式的差别是微波热点效应出现的原因。强微波场可以驱使分子能态通过快速吸收微波能量的方式升高能量，并显著的偏离热平衡分布。分子的内部能态分布处于非平衡状态，温度的概念失效，通过构造相同温度场研究微波反应和普通热反应的差别具有局限性。虽然利用主方程模型模拟的结果符合现有的实验现象，理论预测的这些机制的可靠程度仍需要设计实验验证。

微波传能的一些特征显著的不同于一般加热，从而导致了各种微波效应。分子能级越高越容易吸收微波的性质是微波热点产生和存在的的物理机制，导致这一性质的微观基础如图7所示。分子处于低能级时，相邻能级差大于微波能量，分子无法吸收微波，碰撞传能占主要地位。对于一般的分子，随着能级的升高非谐性会越来越显著，相邻能级间的跃迁偶极会增大。对于几乎所有分子，随着分子能量的增加，分子量子态密度会增加。这两个特征表明能级越高越有利于微波的吸收或发射。微波加热金属和微波诱导产生等离子体的现象表明在一定条件下微波的吸收速度远大于体系能量的损耗速度。

根据上述微观机制，在微波加入过程中用高能光激发分子或分子基团可以显著增加微波热点发生概率，一定程度上控制热点的生成。也可以通过微波作用下物质的发光特性判断是否有微波热点正在生成。图7所示的物理机制表明通过组合不同频率和强度的光可以在一定程度是操纵分子的内部能量演化，为可控的利用非平衡行为提供了可能。

![](images/f85d10fb55bed920a5c8e3aa2ad7b8dcf370d56149b9bf6128ffa1ff9731416e.jpg)  
图6环境温度 $\mathbf { 1 0 0 \ K ( a ) }$ 和 ${ \bf 3 0 0 ~ K ( b ) }$ 时，包含多极性基团分子在微波作用下各基团振动态分布图，不同颜色表示不同的基团。基团1起始能级 设置为 $\mathbf { S { = } 1 0 0 0 0 ~ c m { - } 1 }$ ，另外两个的基团起始能级设置为 $\scriptstyle \mathbf { S = 1 0 0 0 \ c m - 1 }$ 。 Figure 6When the temperature is taken as $\mathbf { 1 0 0 ~ K }$ (a) and ${ \bf 3 0 0 ~ K }$ (b),the vibrational states distribution of each group of molecules containing multipolargroupsundertheactionofmicrowave,diferentcolorsidicatediferent groups.Theinitialeergylevelofgroupissetto $\mathbf { S } = \mathbf { 1 0 0 0 0 }$ $\mathbf { c m - 1 }$ ,and the initial energy level of the other two groups is set to $\mathbf { S } = \mathbf { 1 0 0 0 ~ c m - 1 }$

![](images/4b056b90fb6f7b816447821bebd4813b2858343eea08d3899ec2328e4333898a.jpg)  
图7微波传能的微观机制  
Figure7The microscopic mechanism of microwave energy transfer.

# 4结论

本文使用作者2016年提出的量子态识别主方程模型研究了微波热点出现的可能机制，试图厘清热点如何产生和维持的问题，给出微波传能的微观机制[14,20]。研究表明： $3 0 0 ~ \mathrm { K }$ 常温下较强的微波有一定的几率诱发分子快速吸收微波能量而导致能级上升； $1 0 0 ~ \mathrm { K }$ 的低温下诱发微波热点的几率几乎为0；通过预先激发分子的方式也可以使得出现微波热点的概率增大；分子吸收微波维持或提升其能量的概率随温度的升高而增加；文章结论支持可控的生成微波空间热点或分子内热点。

理论上，在分子内传能和分子间传能速率较低的时候，分子内微波热点可以通过局域官能团的振动态或电子态激发诱导。本文的研究为定点活化特定的化学键提供了一种可能的方法。同时，微波热点效应也可以被用来构造不均匀的温度场，由不同的温度分布耦合反应物分布达到优化化学合成的目的。可控微波热点和可控非平衡效应在其它领域也会有重要的应用，且本文的结论不仅限于微波传能方面[]。工业生产中，由于微波热点产生的随机性降低了大规模生产的可控性。通过监测发光行为可以判断微波热点的产生情况。在通讯领域，微波和毫米波的大量应用使得人们需要思考较高强度的高频辐射是否会对人体造成影响。辐射加热的不均匀性，特别是热点效应是可能造成生物体损伤的最大因素，局部温度的提高可能会损伤生物体。考虑到热点的产生和温度分布、辐射强度及辐射时间有关，可以通过这些特征来降低热点的发生。医疗上，可控的热点效应可以人为的促使生物体特定位置出现热点，从而使相关病灶失活。相关理论和应用将逐步在后续的研究中开展。

# References

[1]De la Hoz,A.,A.Diaz-Ortiz,and A.Moreno, Chem. Soc.Rev.2005. 34(2). 164.   
[2] Qinhan Jin ；Shushan Dai ；Kama Huang.Microwave chemistry, Science Press,1999 (in Chinese). (金钦汉，戴树珊，黄卡玛，微波化学，科学出版社，1999)   
[3] Kaiser,N.-F ；Bremberg,U；Larhed,M.；Moberg,C ；Hallberg, AAngew.Chem.Int.Ed..2000,39,3595-3598.   
[4] M.Nüchter ;B. Ondruschka ;W.Bonrath ;A.Gum.Green Chem., 2004,6,128. [5] Manabu Kanno ；Kosuke Nakamura ；Eri Kanai ；Kunihito Hoki ; Hirohiko Kono ;Motohiko Tanaka.TheJ.Phys.Chem.A2012,116, 2177-2183. [6]Kappe,C.O.; Pieber,B ;Dallinger,D.Angew. Chem. Int.Ed.,2013 52,1088-1094. [7]Rosana,Michael R；Tao,Yuchuan；Stiegman,Albert E；Dudley, Gregory B.Chem. Sci.2012.3(4),1240-1244. [8]D.A.C. Stuerga ;P.Gaillard.J.Microwave Power.1996.31(2),87- 100. [9] Westaway, K.C; R.N.Gedye.J. Microwave Power.1995.30(4),219- 230.   
[10] Blanco,C ;S.M.Auerbach.J.Am.Chem. Soc.2002,124,22,6250- 6251.   
[11] Banik,S; S.Bandyopadhyay ; S.Ganguly. Bioresour. Technol.2003. 87(2),155-159.   
[12] Khattak,H.K.;P.Bianucci ;A.D. Slepkov. Proc.Natl. Acad. Sci. 2019.116(10),4000.   
[13] Coleman,C.J.J.Austral.Math. Soc. Ser.B.2009.33(1),1-8.   
[14] Ma,J.J.Phys.Chem.A.2016.120(41),7989-7997.   
[15]Barker,J.R.Int.J.Chem.Kinet.2009.41(12), 748-763.   
[16] Miller,J.A.；S.J.Klippenstein ；C.Raffy.J.Phys.Chem.A.2002. 106(19), 4904-4913.   
[17] Linsebigler,A.L ;G.Lu;J.T.Yates.Chem.Rev.1995.95(3), 735- 758.   
[18]Barker,J.R.Int.J.Chem.Kinet.2001.33(4),232-245.   
[19]Ralph E Weston ；Thanh Lam Nguyen；John F Stanton ；John R Barker.J.Phys.Chem.A.2013.117(5),821-835.   
[20] Ruifang Wang ;Dandan Ma; ZhiweiLi;Haisheng Ren ; Jianyi Ma. Chem.Phys.Lett.2019.726,46-52.   
[21] Gillespie,D.T.J.Comput.Phys.1976.22(4),403-434.   
[22] Gillespie,D.T.J.Comput.Phys.1978.28(3),395-407.   
[23]Wang,W;Wang,B;Sun,J;Mao,Y;Zhao,X;Song,Z.RSCAdv. 2016.6(58), 52974-52981.   
[24]Dahinten,T.;J.Baier;A. Seilmeier.Chem.Phys.1998.232(1),239- 245.   
[25] Kaiser,W.Ultrashort Laser Pulses.Springer-Verlag Berlin Heidelberg,1993.