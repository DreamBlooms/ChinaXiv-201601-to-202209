# 纳米通道反电渗析的理论分析

张力，王沫然(清华大学工程力学系，热科学与动力工程教育部重点实验室，北京 100084)

摘要纳米通道内的反电渗析过程是一种将纳米通道两端由于浓度差造成的能量势差直接转化成电能的新方法。由于反电渗析中局部浓度随通道位置变化，壁面电荷密度也会随通道位置发生变化。本文引入双电层带电 Basic-Stem 模型，将壁面电荷密度与局部浓度关联，并在传统空间电荷模型的基础上，预测了反电渗析过程的电流-电压曲线和电动势。修正的空间电荷模型由于引入双电层带电模型，将难以测量的物理量，如壁面电荷密度，转化为较易测得的物理量和已知的模型参数。与过去模型的对比表明修正的空间电荷模型在合理选择模型参数的条件下更符合实验结果。

关键词反电渗析；空间电荷模型；Basic-Stern 模型；TMS 模型中图分类号：O364.1 文献标识码：A

# Theoretical Analysis of Reverse Electrodialysis in Nanochannel

ZHANG Li and WANG Mo-Ran (Department of Engineering Mechanics,Tsinghua University,Beijing 1Ooo84, China)

Abstract: Reverse electrodialysis is a kind of energy conversion method that generates electricity from the free energy in salinity gradient. Due to concentration gradient along the streamwise direction, surface charge density will consequentlyvary along channel. In this work,we introduce the Basic-Stern model to relate the surface charge density with local concentration and predict currnt-voltage curve and electromotive force in the reverse electrodialysis,based on the conventional space charge model. Our modified model converts the surface charge density,which is difficult to measure,into accessible physical quantities and model parameters. Compared with the previous models, our modified model fits the experimental results beter with proper parameters.

Key words: reverse electrodialysis; space charge model; Basic-Stern model; TMS model

# 0引言

盐差能是不同浓度的溶液自发混合时可以利用的自由能差，广泛存在于江河入海口处。反电渗析是一种将盐差能转换成电能的方式。利用离子选择性膜的传统反电渗析过程在1954 年首次由 Pattle[1]提出并实现。1976年，Weinstein 和Leitz[2设计了一种电池组装置应用于反电渗析，并且给出了优化操作条件的理论依据。近年来，随着膜技术的发展，反电渗析重新得到重视，大规模的应用也进入试验阶段[3]。除此之外，由于纳米技术的快速进步，无机材料制成的纳米通道被应用于反电渗析中，为小尺度下能量转化提供了一种新的可能[4]。

当电解质溶液与固体接触时，固体表面自发的由于吸附或分解过程带电，从而在溶液中形成双电层。双电层内异种电荷离子（counter-ion）浓度远大于同种电荷离子（co-ion）浓度。由于纳米通道的尺寸与双电层厚度相当，甚至远小于双电层厚度，异种电荷离子将在通道内占主导。当通道两端存在浓度差时，由于双电层效应，纳米通道呈现出对不同电性离子的选择性，从而产生净电荷的传输。构成回路后，即可对外电路供电。

图1为Kim 等4设计的纳米通道反电渗析系统的示意图，采用 $\mathrm { \sf A g / A g C l }$ 作为极板。实验表明，纳米通道内反电渗析的功率密度比离子选择性膜要高出1-3个量级。同时，无机纳米通道稳定性更好，不会像有机膜一样缩水和膨胀。除此之外，依赖于成熟的CMOS流程的纳米通道加工技术相较于传统的膜工艺成本也较低[4]。最近，Kim 等[5]已研究出纳米通道阵列的反电渗析系统，大大提高了电流密度，纳米通道阵列组装形成的无机膜将有可能大大拓展反电渗析的应用范围。

![](images/19cdf946f43d010ba33de855772b68ffa1f59f39e94dfe382abf3bda645a2380.jpg)  
图1纳米通道反电渗析示意图  
Fig.1 Schematic for reverse electrodialysis in nanochannel

尽管实验已经有了初步成果，但是对于纳米通道内反电渗析过程的理论研究仍然较少。Fair和Osterle[最早采用空间电荷模型（space-charge mod-el）研究了反电渗析过程，但是其研究针对的是有机膜内的圆柱形纳米通道，并未应用于无机纳米通道的分析，另外，模型中采用了给定壁面电荷的假设。Kim 等[4]采用简化的基于 Teorell-Meyer-Sievers（TMS）模型的一维模型分析了电动势和迁移数等参数，得到了定性上正确的结果，但是在通道尺度很小或者溶液池内浓度较高时存在较大误差。Kim等7和Guo 等8分别采用有限差分和有限元方法计算了整个系统的电场和浓度场，他们均采用给定壁面电荷密度的边界条件，没有考虑浓度变化对电荷密度的影响。之前的研究已经表明[9-I]，表面电荷密度依赖于局部浓度等因素。因此，给定壁面电荷密度的假设在纳米通道反电渗析系统中难以成立。另外，当双电层厚度大于通道尺度时，双电层重叠导致的离子富集效应[9,12]也不可忽略。

# 1模型与方法

考虑两个无穷大平板组成的二维纳米通道，平板间距 $h$ 即为通道高度。在TMS模型中，忽略电势和浓度在截面方向的变化，仅考虑轴向的Nernst-Planck方程：

$$
\pmb { J } _ { i } = \left( - D _ { i } \nabla c _ { i } \right) + \left( - \frac { e z _ { i } D _ { i } } { k _ { b } T } c _ { i } \nabla \psi \right)
$$

$$
c _ { i } = c _ { i } \left( \begin{array} { l l l } { x } \end{array} \right) \qquad \psi = \psi ( x )
$$

以及进出口处的Donnan平衡。这里， $c _ { i }$ 为 $i$ 离子的

浓度， $\psi$ 为电势， $D _ { i }$ ， $z _ { i }$ 分别为 $i$ 离子的扩散系数和电荷数， $e$ 、 $k _ { b }$ 、 $T$ 分别为元电荷量，Boltzmann常数和温度。本文中， $T$ 取室温 $2 9 8 \mathrm { K }$ 。

在空间电荷模型中，将电势作如下分解：

$$
\Phi { = } \boldsymbol { \phi } ^ { * } \left( x \right) { + } \psi \left( x , y \right)
$$

根据Gouy-Chapman 的双电层模型, $\psi$ 满足截面上的Poisson-Boltzmann（PB）方程

$$
\frac { \mathrm { d } ^ { 2 } \psi } { \mathrm { d } y ^ { 2 } } = - \frac { 2 e c ^ { \ast } \left( x \right) } { \varepsilon } \mathrm { s i n h } \left( \frac { e \psi } { k _ { b } T } \right) ~
$$

其中， $c ^ { * } ( x )$ 是截面上的表征浓度，当双电层不重叠时， $c ^ { * } ( x )$ 即为通道中间浓度，当双电层重叠时，$c ^ { * } ( x )$ 视为外推至无穷远处的浓度。根据Basic-Sterm模型[10]可以得到不同的 $c ^ { * } ( x )$ 时的壁面电荷密度:

$$
\zeta ( \sigma ) = { \frac { k _ { b } T } { e } } \ln { \frac { - \sigma } { e T + \sigma } } - ( \mathrm { p H } - \mathrm { p K } ) { \frac { k _ { b } T \ln 1 0 } { e } } - { \frac { \sigma } { C } }
$$

$$
\sigma ( \zeta ) = \frac { 2 \epsilon k _ { b } T \kappa } { e } \sinh \left( \frac { e \zeta } { 2 k _ { b } T } \right)
$$

在给定 $\sigma$ 的边界条件下，通过求解不同截面处的PB方程，得到不同截面处的电势分布。在偏离平衡态不太远的条件下，考虑如下关于电流 $I$ 和溶质通量 $J$ 的线性唯象方程组[6],

$$
I = k _ { _ { 1 1 } } \left( - R T \frac { \mathrm { d } \ln c ^ { * } } { \mathrm { d } x } \right) + k _ { _ { 1 2 } } \left( - R T \frac { \mathrm { d } \phi ^ { * } } { \mathrm { d } x } \right) ,
$$

$$
J = k _ { _ { 2 1 } } \Biggl ( - R T \frac { \mathrm { d } \ln c ^ { * } } { \mathrm { d } x } \Biggr ) + k _ { _ { 2 2 } } \Biggl ( - R T \frac { \mathrm { d } \phi ^ { * } } { \mathrm { d } x } \Biggr ) ,
$$

其中， $k _ { i j } , i , j = 1 , 2$ 是唯象系数。

通过求解PB方程得到电势分布，在低Re数的条件下，流动方向速度可以由不可压的Navier-Stokes方程得到， $\boldsymbol { u } = u \left( y , c ^ { * } \left( x \right) , \boldsymbol { \phi } ^ { * } \left( x \right) \right)$ 。通过积分截面不同位置的通量，可推出电流 $I$ 的表达式，与唯象方程组比较后即得到 $k _ { i j } , i , j = 1 , 2$ 的形式。在二维纳米通道内，以 $k _ { 1 1 }$ 为例：

$$
\begin{array} { r l } & { k _ { 1 1 } = \cfrac { 4 w \left( c ^ { * } \right) ^ { 2 } } { \eta } \int _ { 0 } ^ { H } \cosh \psi \left( H ^ { 2 } - y ^ { 2 } \right) d y } \\ & { \quad + \cfrac { 2 w c ^ { * } } { R T } \int _ { 0 } ^ { H } \left( D _ { 1 } \exp \left( - \psi \right) + D _ { 2 } \exp \varPsi \right) d y } \\ & { \quad + \cfrac { 8 w \left( c ^ { * } \right) ^ { 2 } } { \eta } \int _ { 0 } ^ { H } \cosh \psi \left[ \int _ { y } ^ { H } \sinh \psi d y d y \right. } \end{array}
$$

参考 Sasidhar 等[13]的数值方法，首先将式(8)除以式(7)，得到 $\%$ 的表达式，从通道入口至出口积分，求解积分方程得到 $\%$ 。然后将是(8)代入式(7)，消去 ，积分后可求得 $I _ { \circ }$

# 3结果与讨论

模拟中采用 Kim 等[4的实验参数：电解质溶液为KCl,，浓溶液端浓度 ${ C _ { \mathrm { h } } } { = } 1 0 ^ { - 3 }$ mol/L，稀溶液端浓度 $C _ { 1 } { = } 1 0 ^ { - 4 } ~ \mathrm { m o l / L }$ ，纳米通道长宽高分别为 $1 4 0 ~ { \mu \mathrm { m } }$ ，$2 5 \mu \mathrm { m }$ 和 $2 6 \mathrm { n m }$ 。如图2所示，TMS 模型的模拟结果与实验存在较大的偏差，同时，由于TMS 模型中的壁面电荷密度 $\sigma$ 是未知量，只能采用拟合的方式与实验对比。

![](images/26061d1a806a33f5097a9be8f906b06711f2681d38bd16b539a0c9e54d9fbe6f.jpg)  
图2不同电荷密度下TMS模型得到的电流-电压曲线 Fig.2 Current-voltage curve from TMS model for different surfacecharge densities

采用修正的空间电荷模型计算的结果如图3所示，其中Basic-Stern模型中的参数如下方式选取： $c$ 与 $\boldsymbol { \Gamma }$ 采用Behren 等的建议[10] $C { = } 2 . 9 \ \mathrm { F / m } ^ { 2 }$ ，（204号 $\scriptstyle { \cal T } = 8 \mathrm { n m } ^ { - 2 }$ ; $\mathfrak { p H }$ 采用 Kim 等的实验值[4]，由于实验误差， $\mathrm { p H } = 5 . 6 \pm 0 . 3$ ，由于实验并未给出不同条件下的 $\mathfrak { p H }$ ，本文中采用实验误差范围内允许的值与实验进行拟合；根据 Hiemstra 等的表面杂化模型[14]，取反应常数 $\mathsf { p K } = 7 . 5$ ，但是考虑到本文中可能出现双电层重叠，同时 $\mathsf { p K }$ 作为界面的本征参数，其具体大小仍存在争议，本文中取 $\mathrm { p K } = 7 . 5 \sim 7 . 9$ 与实验进行拟合。计算结果对pH,pK值比较敏感，调整pH,pK值可以得到比较接近实验的结果，但是难以保证反电渗析系统的电动势和内电阻同时与实验符合得较好（即曲线的横截距和斜率）。这可能是进出口的Donnan平衡条件不能完全满足导致的。实际上，对于高度 $2 6 \ \mathrm { n m }$ 的通道，按照进口高浓度和出口低浓度计算的德拜长度分别为 $9 . 2 \mathrm { n m }$ 和 $2 9 . 2 \ : \mathrm { n m }$ ，进口双电层未完全重叠，而出口已完全重叠，这可能对结果带来影响。

![](images/a6f1c8d2248c9e9a520c79568723da8b763ad20cc6bc4c66602a29afc8fba53e.jpg)  
图3不同 $\mathrm { \tt p H , p K }$ 时修正空间电荷模型得到的电流-电压曲线Fig.3 Current-voltage curve from modified space chargemodel for different pH, pK

给定稀溶液端浓度 $C _ { 1 } { = } 1 0 ^ { - 3 } \mathrm { m o l / L }$ ，改变浓溶液端浓度，采用不同的模型计算电动势，结果如

![](images/0289dc29d319d33897ea57944565afae0775f3afbc662d248abe49bb4c0ee640.jpg)

图4所示。根据Kim的实验结果，给定$\scriptstyle \sigma = 0 . 0 0 2 C / \ m ^ { 2 }$ ，原始的空间电荷模型偏离实验结果较大，而TMS模型与修正的空间电荷模型比较接近，但均难以还原实验中当 $C _ { \mathrm { h } }$ 由 $1 0 ^ { - 2 } \ \mathrm { m o l / L }$ 增大到 ${ { 1 0 } ^ { - 1 } }$ mol/L时，电动势降低的情况。如图5所示，当给定浓度比，而改变通道高度时，修正的空间电荷模型得到的结果比TMS模型和原始空间电荷模型更接近实验值。图4和图5中取 $\mathsf { p H } { = } 5 . 3$ ， $\mathrm { p K } { = } 7 . 9$ ，在前述的误差范围内与实验结果最接近。

![](images/33813404011b5614b39512c3d5082fbafee6ab2f3e82b7bd03147c54ed6491a2.jpg)  
图4TMS 模型、空间电荷模型、修正空间电荷模型得到的不同浓度比时的电动势

Fig.4 Electromotive force from TMS model, space charge model, modified space charge model for different concentration ratios

![](images/3b60d8d34727a6a8d1aae6d73bf704eab0e5814cc9d2ecd1436fc600146b2c1d.jpg)  
图5TMS模型、空间电荷模型和修正的空间电荷模型得到的不同通道高度下电动势

Fig.5 Electromotive force from TMS model, space charge model, modified space charge model fordifferentchannel heights

# 4结论

由于修正模型综合考虑了壁面带电的复杂物理机制，建立了壁面电荷密度与局部浓度的关联，可以通过易测的物理量精确计算得到难以测量得到的壁面电荷密度，而不需要将壁面电荷密度作为拟合参数与实验比拟。同时，计算结果表明，修正的空间电荷模型在取合适参数的条件下，比TMS模型和未修正的空间电荷模型与实验结果符合得更好。

# 参考文献

[1]PattleRE.Production ofElectric Powerby Mixing Fresh and Salt Water in the Hydroelectric Pile [J].Nature,1954, 174(4431): 660-660.

[2] Weinstein JN, Leitz F B.Electric Power from Differences in Salinity:The Dialytic Battery [J]. Science,，1976, 191(4227): 557-559. [3] Veerman J. Reverse Electrodialysis: Design and Optimization by Modeling and Experimentation [D]. Netherlands: University of Groningen,2010. [4] Kim D K, DUAN Chuanhua, CHEN Yufeng, Majumdar A. Power Generation from Concentration Gradient by Reverse Electrodialysis in Ion-Selective Nanochannels [J].Microfluidics and Nanofluidics,2010,9(6): 1215-1224. [5] Kim J, Kim S J, Kim D K. Energy Harvesting from Salinity Gradient by Reverse Electrodialysis with Anodic Alumina Nanopores [J]. Energy,2013,51: 413-421. [6] Fair JC, Osterle JF.Reverse Electrodialysis in Charged Capillary Membranes [J]. The Journal of Chemical Physics, 1971, 54(8): 3307. [7] Kim D K. Numerical Study of Power Generation by Reverse Electrodialysis in Ion-Selective Nanochannels [J]. Journal of Mechanical Science and Technology， 2011, 25(1): 5-10. [8] GUO Wei, CAO Liuxuan, XIA Junchao, et al. Energy Harvesting with Single-Ion-Selective Nanopores: A Concentration-Gradient-Driven Nanofluidic Power Source [J]. Advanced Functional Materials,2010,20(8): 1339-1344. [9] WANG Moran, KANG Qinjun. Electrochemomechanical Energy Conversion Efficiency in Silica Nanochannels [J]. Microfluidics and Nanofluidics,2009,9(2): 181-190.   
[10] Behrens S H,Grier D G. The Charge of Glass and Silica Surfaces [J].The Journal of Chemical Physics,2001, 115(14): 6716.   
[11] WANG Moran,Revil A.Electrochemical Charge of Silica Surfaces at High Ionic Strength in Narrow Channels[J]. Journal of Colloid and Interface Science,2010,343(1): 381-386.   
[12] CHENG Lijing， GUO Lingjie. Rectified Ion Transport through Concentration Gradient in Homogeneous Silica Nanochannels [J]. Nano Lett 2007,7(10): 3165-3171.   
[13] Sasidhar V,Ruckenstein E.Electrolyte Osmosis through Capillaries [J]. Journal of Colloid and Interface Science, 1981, 82(2): 439-457.   
[14] Hiemstra T, Van Riemsdijk WH, Bolt G H. Multisite Proton Adsorption Modeling at the Solid/Solution Interface of (Hydr)Oxides: A New Approach [J]. Journal of Colloid and Interface Science,1989,133(1): 91-104.