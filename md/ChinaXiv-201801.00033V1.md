编号：161043

# HFO-1234ze(Z)热解机理的DFT研究

张浩¹，刘朝¹，吴小阳²，曹宇¹，徐肖肖‘（1.低品位能源利用技术及系统教育部重点实验室，重庆大学动力工程学院，重庆 400030;

2．重庆市特种设备检测研究院，重庆401121)

摘 要:通过密度泛函理论（DFT）对1,1,1,3-四氟丙烯（ $\cdot \mathrm { H F O } { - } 1 2 3 4 \mathrm { z e } ( Z )$ ， $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ ）的热解反应路径进行研究，对可能得热解产物（ $\mathrm { C F } _ { 3 } \mathrm { H }$ $\mathrm { C F } _ { 4 }$ ,HF）进行了分析。结果表明：在均裂反应中， $\mathrm { C F } _ { 3 }$ 自由基最易生成，其活化能为 $2 1 0 . 2 5 ~ \mathrm { k J ~ m o l ^ { - 1 } }$ 。相比之下，由于较高的活化能，F自由基最难产生。在随后的链式反应中，生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ 所需的活化能最低为 $6 4 . 2 3 \mathrm { k J m o l ^ { - 1 } }$ 。而生成 $\mathrm { C F } _ { 4 }$ 和 HF 所需的活化能较高。本文从分子尺度研究了HFO-1234ze的热解机理并为研究有机工质的热稳定性提供了参考。

关键词：HFO-1234ze；热解；密度泛函理论(DFT)

# Mechanism of Thermal Decomposition of HFO-1234ze(Z) by DFT Study

Zhang Hao1, Liu Chao1,Wu Xiao-Yang²,Cao $\mathrm { \Delta Y u } ^ { 1 }$ , Xu Xiao-Xiao 1 (1.KeyLaboratoryofLow-grade EnergyUtilzationTechnology &System,MinistryofEducation,Colege ofPowerEngineer, Chongqing University, Chongqing 40o030, China; 2. Chongqing Special Equipment Inspection and Research Institute, Chongqing 401121, China)

Abstract: The reaction pathways of thermal decomposition of 1,1,1,3-tetrafluoro-1-propene (HFO-1234ze(Z), $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ ）were presented to investigate the formation mechanism of some possible products( $\mathrm { C F } _ { 3 } \mathrm { H }$ $\mathrm { C F } _ { 4 }$ ,HF) by using density function theory (DFT) simulations. The results point out that $\mathrm { C F } _ { 3 }$ is the most preferred product in homolytic cleavage reaction with the lowest energy barrier of $2 1 0 . 2 5 ~ \mathrm { k J / m o l }$ .Fradical is hard to be generated during thermal decomposition processes becauseof its higher energy barrier. In subsequent radical attacking chain reactions,a lower energy barrier $\left( 6 4 . 2 3 \mathrm { \ k J / m o l } \right)$ ）isrequired to form $\mathrm { C F } _ { 3 } \mathrm { H }$ ： $\mathrm { C F } _ { 4 }$ and HF will be generatedwithhigherenergybarrers.Our work presentsthe mechanismof thermal decompositionofHFO-1234ze fromamolecule level and provides a reference for studying the thermal stability of organic working fluids.

Key Word: HFO-1234ze; Thermal decomposition; Density function theory (DFT)

# 0前言

近些年来，随着全球变暖趋势加剧，欧盟已经颁发了一系列的法律法规来限制氟化温室气体（F-gas）的排放。这就意味着，现今使用的一些GWP值超过150的制冷工质（如R134a等）将会逐渐被取代。第四代 HFO 系列制冷工质，如1,1,1,3-四氟丙烯1 $\mathrm { \langle H F O - 1 } 2 3 4 \mathrm { z e } ( Z )$ ， $\mathrm { C F } _ { 3 } \mathrm { C H = C H F } .$ )，其ODP值为0,GWP值为6，在大气中的寿命只有18天，被认为是最有潜力的替代工质之一。HFO-1234ze(Z）在ASHRAE标准中被列为A1类，即为低毒不可燃物质，具有良好的物理化学性质。目前对HFO-1234ze(Z)

的研究较少而对其同分异构体HFO-1234yf的研究较多，主要集中在工质的热物理性质。Tanaka 等[1]通过实验研究了HFO-1234yf的临界温度、临界压力和临界密度等参数，发现与R134a的性质接近。之后，Yamada等[2]比较了HFO-1234yf与其它常见ORC工质的性能系数，发现HFO-1234yf更适用于中低温ORC系统。在之后的许多研究中[3-5]表明HFO-1234yf与某些工质存在共沸现象。HFO-1234ze(Z)作为HFO-1234yf的同分异构体，热力性能差别不大，且价格较为低廉，在制冷循环、热泵以及有机朗肯循环（ORC）中应用前景较好。

但是，相比于制冷循环和热泵，ORC系统更容易出现超温过热的情况，工质将发生热分解，导致系统热效率的下降。另外，工质热分解产生的不凝性气体和残留物可能还会对系统安全造成影响[6]。在选择ORC系统工质时，工质的热稳定性将是首要考虑的问题之一。国外学者对于工质的热稳定性研究起步较早。Angelino 等[7]通过实验对5 种不同的HFC系列工质在ORC系统中的热稳定性进行了比较。Ginosar等研究了环戊烷的热稳定性，发现空气对环戊烷的热分解起促进作用。然而，HFO-1234ze(Z)在ORC系统中的热稳定性还未见报道。

密度泛函理论（DFT）已经被广泛地用于研究有机工质的化学反应[8-11]和生物质的热解[12]。BenniDu等[13]采用密度泛函理论得到了 $\mathrm { C F } _ { 3 } \mathrm { C F C H } _ { 2 } \mathrm { + O H }$ 反应的主要反应路径。Qu 等[14]研究了丙烯热解的反应路径，并详细地分析了110个过渡态和50个中间产物。密度泛函理论（DFT）从微观的角度解释了许多反应机理，对研究工质热解问题起了很关键的作用。

本文采用密度泛函理论（DFT）计算研究了HFO-1234ze(Z)的热解反应路径和可能生成的产物。

# 1 计算细节

# 1.1设计反应路径

整个热解反应主要分为均裂反应和抽提反应。根据Qu 等人的研究[14]，在热解初期， $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 会从基态激发到三重激发态 $\mathrm { C F } _ { 3 } \mathrm { C F C H } _ { 2 }$ 。之后通过均裂反应生成不同种类的自由基(主要为H,F和 $\mathrm { C F } _ { 3 }$ ）。最后， $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 中的H和F原子会被自由基抽离，从而生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ ， $\mathrm { C F } _ { 4 }$ 和 HF等物质。具体的反应路径详见图1,5和7。

# 1.2计算方法

本文所有的量子化学计算均在Gaussian09软件中进行。采用 $\mathrm { M 0 6 { - } 2 X / 6 { - } 3 1 { + } G ( d , p ) }$ 基组对所有反应物，生成物进行结构优化并对过渡态进行计算。之后，在相同基组下对优化得到的结构和计算得到的过渡态进行振动频率分析，保证反应物和生成物无虚频且过渡态只存在一个虚频。另外，通过IRC计算确认过渡态连接反应物和生成物。

相应的反应能量在 $\mathrm { M 0 6 { - } 2 X / 6 { - } 3 1 { + } G ( d , p ) }$ 基组下,通过计算获得。所有计算的条件为 $\mathrm { T } { = } 2 9 8 . 1 5 \mathrm { K }$ 和 ${ \bf P } =$ $0 . 1 \mathrm { M P a }$ 。

# 2 结果与讨论

2.1 C-H键,C-F 键 和C-C 键的均裂反应

![](images/cb5343c71eef2b50116c47b4cac3f9116006b012ae805723b368d49eeba3f42e.jpg)  
图1C-H键，C-F 键 和C-C 键的均裂反应的反应路径 Fig.1.The proposed reaction pathways initiated by the cleavage of C-H bond, C-F bond and C-C bond

![](images/0e1057abcf51004856d9b0df28ee9c798dee68e99d761c571a6d6baf122e6ce8.jpg)  
图 $2 \ \mathrm { C - H }$ 键,C-F 键 和C-C 键的均裂反应中的反应物，生成物和过渡态。

Fig.2.Optimized geometries for reactants,transition states, and products initiated by the homolytic cleavage of C-Hbond, C-F bond and C-C bond.

图1为HFO-1234ze(Z)通过均裂反应生成各种自由基的反应路径。图2为均裂反应中的反应物，生成物以及过渡态的优化结构。值得强调地是，在发生分解反应时，基态的 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 会激发为三重激发态 ${ \mathrm { C F } } _ { 3 } { \mathrm { C H - C H F } }$ ，同时也会通过均裂反应直接生成自由基。但是通过图3可以看出， $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 激发所需的能量比直接均裂反应所需的能量要低很多。所以，本文认为在热解最开始阶段 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 会优先激发为三重激发态 $\mathrm { C F } _ { 3 } \mathrm { C H - C H F }$ ，然后才会进行均裂反应。

# 2.1.1 反应路径1和2

从图1可以看出 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 中的H原子分别连接在不同的C原子上，所以C-H键的均裂反应应该有两条不同的反应路径（反应路径1和2)，相应的过渡态为TS1和TS2。图3为反应路径1-5的能量图。在-CHF基团上的H原子通过过渡态TS1离解从而生成 $\mathrm { C F _ { 3 } C H = C F + H }$ ，其活化能为 $2 3 4 . 6 0 \mathrm { k J \ m o l ^ { - 1 } }$ 。与中间C相连的H原子经过过渡态TS2发生离解后产生 $\mathrm { C F } _ { 3 } \mathrm { C = C H F + H }$ ，活化能为 $2 4 0 . 4 3 \mathrm { k J m o l ^ { - 1 } }$ 。这两个反应路径所需的活化能相差不大。

# 3.1.2 反应路径3和4

考虑C-F键的均裂反应。-CF和 ${ \mathrm { . C F } } _ { 3 }$ 基团中的F原子分别通过过渡态TS3和TS4产生离解。其中，-CF 基团中的F原子通过过渡态TS3离解产生$\mathrm { C F } _ { 3 } \mathrm { C H = C H + F } ,$ 其活化能为 $2 5 2 . 8 7 \mathrm { k J } \mathrm { m o l } ^ { - 1 }$ 。对于 ${ \cdot } \mathrm { C F } _ { 3 }$ 基团中F原子的离解，只找到一个过渡态TS4，其活化能为 $2 7 7 . 5 2 \mathrm { k J } \mathrm { m o l } ^ { - 1 }$ 。

![](images/04d340b780e25081a3cc9db6e7486919f5665cb8147c3a108c423549ac2694bb.jpg)  
图3均裂反应中各反应路径能量图  
Fig.3.The energy profiles of reaction pathways initiated by the homolytic cleavage.

# 3.1.3 反应路径5

从图1可以看出，除了H和F原子， $\mathrm { C F } _ { 3 }$ 基团也会在热解时发生离解。 $\mathrm { C F } _ { 3 } \mathrm { C H }$ -CHF通过过渡态

TS5发生均裂反应生成 $\mathrm { C F } _ { 3 } { + } \mathrm { C H C H F }$ ，其活化能为$2 1 0 . 2 5 ~ \mathrm { k J ~ m o l ^ { - 1 } }$ 。从图3可以看出， $\mathrm { C F } _ { 3 }$ 离解所需的活化能最低。

在最初的热分解反应中，F原子因为其较高的反应活化能很难离解出来，所以在下面讨论中，只考虑了 $\mathrm { C F } _ { 3 }$ 和H自由基与 $\mathrm { H F O - } 1 2 3 4 \mathrm { z e } ( Z )$ 的反应。

# 3.2H抽提反应和F抽提反应

以上讨论表明， $\mathrm { C F } _ { 3 }$ 自由基和H自由基在热解初期的均裂反应中较容易产生。在后续的反应中，由于 $\mathrm { C F } _ { 3 }$ 自由基和H自由基有较高的化学活性，会继续与 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 发生反应，将 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 中的原子从分子结构中抽提出来。

本文主要考虑H抽提反应和F抽提反应。图4表示链式反应的反应物，过渡态和生成物的优化结构。 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F } + \mathrm { C F } _ { 3 }$ ·和 $\scriptstyle \mathrm { C H = C H F + H }$ ·反应路径如下：

![](images/bb12615ab43390c224d530c275fb4fb2d99f9036208c0623d641a1fb7822cd39.jpg)  
图4H抽提反应和F抽提反应中的反应物，生成物和过渡态。 Fig.4. Optimized geometries for transition states,and products initiated by the H-abstraction and F-abstraction reactions.

# 3.2.1反应路径 $6 { \sim } 9$

图5表示了 $\scriptstyle \mathrm { C F } _ { 3 } \mathrm { C H = C H F + C F } _ { 3 }$ ·反应路径，图6为 $\scriptstyle \mathrm { C F } _ { 3 } \mathrm { C H = C H F + C F } _ { 3 }$ ·反应能量图。-CHF基团上的H原子被 $\mathrm { C F } _ { 3 }$ 自由基抽离生成 $\mathrm { C F _ { 3 } H + C F _ { 3 } C H C F } ,$ 其过渡态为TS6，活化能为 $6 4 . 2 3 \mathrm { k J m o l ^ { - 1 } }$ 。同理，连接中间C 原子的H原子通过过渡态TS7反应生成$\mathrm { C F _ { 3 } H + C F _ { 3 } C C F H }$ ，活化能为 $6 8 . 3 6 \mathrm { k J \ m o l ^ { - 1 } }$ 。F原子也会被 $\mathrm { C F } _ { 3 }$ 自由基抽离生成不同的产物。反应路径 8和9分别表示生成 $\mathrm { C F } _ { 4 }$ 的反应路径，其活化能分别为 $1 8 5 . 3 1 ~ \mathrm { k J ~ m o l } ^ { - 1 }$ 和 $1 6 7 . 1 7 ~ \mathrm { k J ~ m o l } ^ { - 1 }$ 。通过比较活化能可以看出，生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ 比生成 $\mathrm { C F } _ { 4 }$ 所需的活化能低很多，这意味着，在 $\mathrm { C F } _ { 3 }$ 自由基攻击 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F }$ 时， $\mathrm { C F } _ { 3 } \mathrm { H }$ 比 $\mathrm { C F } _ { 4 }$ 更易产生。

![](images/04c6172de21b12ec797690b4ed26d36aa2fb854d896421035de527cda4158a64.jpg)  
图 $5 \mathrm { C F } _ { 3 } \mathrm { C H } { = } \mathrm { C H F } { + } \mathrm { C F } _ { 3 }$ ·反应的路径

![](images/2f6a65816b26815e4f073d61cf5875ba08b7970150f4a6474fd4a20ab80dec4e.jpg)  
Fig.5.The proposed pathways of $\scriptstyle \mathrm { C F } _ { 3 } \mathrm { C H = C H F + C F } _ { 3 }$ reactions.   
Fig.6.The energy profiles of reaction pathways initiated by the $\scriptstyle \mathrm { C F } _ { 3 } \mathrm { C H = C H F + C F } _ { 3 }$ :reactions.

# 3.2.2反应路径10和11

图7表示了 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F + H } .$ 反应的路径，图8为 $\mathrm { C F } _ { 3 } \mathrm { C H = C H F + H }$ 反应能量图。-CHF基团中的F原子被H自由基抽离生成HF，其过渡态为TS10，活化能为 $1 5 4 . 9 3 \mathrm { k J } \mathrm { m o l } ^ { - 1 }$ ${ \mathrm { - } } \mathrm { C F } _ { 3 }$ 基团中的F原子也会被H自由基抽离，经过过渡态TS11生成 $_ \mathrm { H F + C F _ { 2 } C H C H F }$ 其活化能为 $1 4 3 . 1 4 \mathrm { k J } \mathrm { m o l } ^ { - 1 }$ 。

比较反应活化能可以看出，生成HF所需的活化能在生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ 和 $\mathrm { C F } _ { 4 }$ 所需活化能之间。可以得出结论：在后续的链式反应中， $\mathrm { C F } _ { 3 } \mathrm { H }$ 最易产生，其次是HF， $\mathrm { C F } _ { 4 }$ 最难产生。

![](images/7cf378e02212df752ada5aadbaba87c09c1a74393d3a14e49e056bf2604a6b26.jpg)  
图 $\scriptstyle 7 \mathrm { C F } _ { 3 } \mathrm { C H = C H F + H } .$ 反应路径  
Fig.7.The proposed pathways of $\mathrm { C F } _ { 3 } \mathrm { C H = C H F + H \cdot }$ reactions.

表1为反应路径6\~11的反应活化能，反应焓和吉布斯自由能。生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ 所需的活化能最低， $\mathrm { C F } _ { 3 } \mathrm { H }$ 将成为热解反应的主要产物。相比于之前讨论的反应路径1\~5，生成 $\mathrm { C F } _ { 4 }$ 和HF所需的活化能均低于均裂反应所需的最低能量（ $2 1 0 . 2 5 \mathrm { ~ k J }$ mol-1)，而且生成 $\mathrm { C F } _ { 4 }$ 和 HF的反应路径（反应路径8\~11）吉布斯自由能变化小于0，这意味着生成 $\mathrm { C F } _ { 4 }$ 和HF在热力学上是可行的。

![](images/499b68d419e60f9cb3afec720685a31e85be90ac8180841c94fb9eeea7dda4df.jpg)  
图 $6 \mathrm { C F } _ { 3 } \mathrm { C H } { = } \mathrm { C H F } { + } \mathrm { C F } _ { 3 }$ 反应能量图  
图 $8 \mathrm { C F } _ { 3 } \mathrm { C H = C H F + H }$ ·反应能量图  
Fig.8.The energy profiles of reaction pathways initiated by the $\mathrm { C F } _ { 3 } \mathrm { C H = C H F + H \cdot }$ reactions.

表1反应路径6\~11的反应活化能 $( \Delta G _ { 2 9 8 . 1 5 } ^ { \# }$ ），反应焓（20 $( \Delta _ { r } H _ { ~ 2 9 8 . 1 5 } ^ { \theta } )$ ）和反应吉布斯自由能变 $( \Delta _ { r } G _ { ~ 2 9 8 . 1 5 } ^ { \theta } )$ ）Table.1. Reaction Activation Energies ( $\cdot { \Delta G _ { ~ 2 9 8 . 1 5 } ^ { \# } } )$ , ReactionEnthalpies $( { \Delta _ { r } H } _ { 2 9 8 . 1 5 } ^ { \theta } )$ )andReactionGibbsFreeneries（20 $( \Delta _ { r } G _ { ~ 2 9 8 . 1 5 } ^ { \theta } )$ for pathway 6\~11

<html><body><table><tr><td colspan="3">Reaction △G298.15 △,H29813 298.15 pathways ( kJ/mol) ( kJ/mol) ( kJ/mol) △G</td></tr><tr><td>Path6</td><td>64.23 29.24</td><td>23.08</td></tr><tr><td>Path7</td><td>68.36 44.69</td><td>36.49</td></tr><tr><td>Path8</td><td>185.31 -25.44</td><td>-21.92</td></tr><tr><td>Path9</td><td>167.17 -57.79</td><td>-61.25</td></tr><tr><td>Path10</td><td>154.93 -44.47</td><td>-63.66</td></tr><tr><td>Path11</td><td>143.14 -76.81</td><td>-102.99</td></tr></table></body></html>

# 4结论

1）采用DFT方法对 $\mathrm { H F O - } 1 2 3 4 \mathrm { z e } ( Z )$ 的热稳定进行研究，对可能的产物（ $\mathrm { C F } _ { 3 } \mathrm { H }$ ， $\mathrm { C F } _ { 4 }$ 和 HF）进行了分析。2)HFO-1234ze在分解初期会优先从基态激发成三重激发态。  
3）在发生均裂反应时， $\mathrm { C F } _ { 3 }$ 和H自由基容易产生，F自由基较难产生  
4）在随后的链式反应中，生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ ， $\mathrm { C F } _ { 4 }$ 和HF所需的活化能比均裂反应所需的能量都要低，其中生成 $\mathrm { C F } _ { 3 } \mathrm { H }$ 所需的活化能最低。这3种产物都有可能在链式反应中产生。

# 参考文献

[1]Tanaka K and Higashi Y, Thermodynamic properties of HFO-1234yf (2，3，3， 3-tetrafluoropropene). International journal of refrigeration, 2010. 33(3): p. 474-479.   
[2] Yamada N, Mohamad MNA,and Kien T T, Study on thermal efficiency of low-to medium-temperature organic Rankine cycles using HFO- 1234yf. Renewable Energy, 2012.41: p.368-375.   
[3] HU Peng,CHEN Longxiang,ZHU Wanbao,et al., Isothermal VLE measurements for the binarymixture of2,3,3,3-tetrafluoroprop-l-ene $( H F O - I 2 3 4 y f ) + I$ 1-difluoroethane (HFC-152a). Fluid Phase Equilibria, 2014.373: p. 80-83.   
[4]HU Peng,CHEN Longxiang，and CHEN Zeshao, Vapor-liquid equilibria for binary system of2,3，3, 3-tetrafluoroprop-l-ene $( H F O - I 2 3 4 y f ) +$ isobutane (HC-600a).Fluid Phase Equilibria,2014.365: p. 1-4.   
[5] Kamiaka T, Dang C,and Hihara E,Vapor-liquid equilibrium measurements for binary mixtures of R1234yf with R32，R125，and R134a. International Journal of Refrigeration, 2013. 36(3): p. 965-971.   
[6]DAI Xiaoye, SHI Lin, AN Qingsong, et al., Chemical kinetics method for evaluating the thermal stability of Organic Rankine Cycle working fluids. Applied Thermal Engineering,2016.100: p. 708-713.   
[7] Angelino Gand Invernizzi C, Experimental investigation on the thermal stability of some new zero ODP refrigerants. International Journal of Refrigeration, 2003. 26(1): p. 51-58.   
[8] Mishra B K, Chakrabartty A K,and Deka R C, Theoretical investigation of the gas-phase reactions of CF2ClC (O) OCH3 with the hydroxyl radical and the chlorine atom at $2 9 8 K .$ Journal of molecular modeling,2013.19(8): p. 3263-3270.   
[9]Mishra B K, Lily M, Chakrabartty A K,et al., Theoretical investigation of atmospheric chemistry of volatile anaesthetic sevoflurane: reactions with the OH radicals and atmospheric fate of the alkoxy radical (CF 3) 2 CHOCHFO: thermal decomposition vs. oxidation. New Journal of Chemistry, 2014. 38(7): p.2813-2822.   
[10] Lily M, Mishra B K, and Chandra A K, Kinetics, mechanism and thermochemistry of the gas phase reactions of CF 3 CH 2 OCH 2 CF 3 with OH radicals: A theoretical study. Journal of Fluorine Chemistry, 2014. 161: p. 51-59.   
[11] Gour N K, Deka R C, Singh H J, et al., Theoretical study on the gas-phase reactions of ethyl butyrate with OH radicals at 298 K. Monatshefte fir Chemie-Chemical Monthly，2014.145(11):p. 1759-1767.   
[12] LIU Chao, ZHANG Yayun,and HUANG Xiaolu, Study of guaiacol pyrolysis mechanism based on density function theory. Fuel Processing Technology, 2014. 123: p. 159-165.   
[13] DU Benni, FENG Changjun, and ZHANG Weichao, Theoretical studies on the reaction mechanisms and rate constants for OH radicals with CF 3 CF CH 2. Chemical Physics Letters,2009. 479(1): p. 37-4.   
[14] QU Yena, SU Kehe, WANG Xin, et al.， Reaction pathwaysofpropenepyrolysis. Journalof computational chemistry, 2010. 31(7): p. 1421-1442.