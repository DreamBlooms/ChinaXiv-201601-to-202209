# 低温化学影响下的火焰不稳定性研究

杨帆¹，刘再刚12，孔文俊¹(中国科学院轻型动力重点实验室，中国科学院工程热物理研究所，北京100190;2中国科学院大学，北京 100049)

摘要考虑详细化学反应及输运过程，对不可压N-S方程直接数值求解，研究了低温化学影响下的火焰水力学及胞状不稳定性。结果表明，预热后已发生低温化学反应的混合气，其火焰的扰动增长率明显大于未发生低温反应的混合气火焰。通过对预热后混合气火焰的关键参数分析，发现和未预热混气火焰相比其无量纲释热量、Lewis 数及Zeldovich数都显著减小。依据已有理论可知，在Lewis数大于1的条件下，上述参数的减小将使得胞状不稳定性对扰动增长的抑制作用减弱。因此，预热后火焰的增长率明显增大。同时，在低温反应中，大量自由基和其它小分子的形成，使得预热后混合气火焰 Lewis 数减小，从而其火焰胞状结构的深度和高度都变小。

关键词低温化学反应；DME/空气；水力学不稳定性；胞状不稳定性中图分类号：TK16文献标识码：A文章编号：

# Studies of low temperature chemistry on flame instabilities

YANG Fan LIU Zai-Gang KONG Wen-Jun

(1.KeyLaboratoryofLight-duty Gas-turbine,InstituteofEngineering Thermophysics,Chinese AcademyofSciences,

Beijing 100190 China;

2.University of Chinese Academy of Sciences,Beijing 10oo49, China)

Abstract Numerical simulation on the incompressble N-S equation was completed to study the low temperature chemistry on flame instabilities by using the detailed chemical kinetics and transport property.The results show hat the flame disturbance growth rate of the mixed gas involving low temperature chemistry (LTC) is significantly greater than that without LTC.By the analysis of the key parameters of the preheated mixed gas flame,it is found that the dimensionless heat release,Lewis number and Zeldovich number are significantly reduced compared with that of the flame without preheating.On the basis of the existing theory that the reduction of the above parameters makes the cellular instability decreased inhibitory efect on the growth of disturbances as Lewis number greater than 1. As aresult,the growth rate offlame is obviously increased after preheating. At the same time,alarge number of free radicals and other small molecules are formed in the low temperature reaction,which makes the flame Lewis number ofthe preheated mixture reduced,and the depth and height of the flame celllar structure become smaller.

Key words: low temperature chemistry; DME/air; hydrodynamic instabilities; cellular instabilities

# 0前言

预混火焰水力学不稳定性和胞状不稳定性通常耦合出现。当Lewis数小于1时，后者强化前者，大于1时则抑制。水力学不稳定性在各个波数下都会发生，而在考虑火焰厚度以及拉伸效应后，其在很小波数下是不发生的。上述不稳定性诱发了火焰面的褶皱，从而增大了火焰传播速度。这是燃烧室火焰自湍流化，以及爆燃转爆震的重要机制。在当前先进发动机内，广泛采用增压及贫预混燃烧。由于压力的增大，预混气体的点火延迟时间显著减小。特别是对于航空煤油、汽油及柴油等大分子燃料混合物，其存在明显的低温化学反应。因而，高压及高预热温度使得其低温反应强烈，同时低温点火延迟时间不断减小。当火焰低温反应时间尺度和燃烧室大尺度流动时间尺度相似时，即出现低温化学影响下的火焰动力学过程[1]。此时，未燃混气并非初始氧化剂以及燃料，而是低温反应路径中的中间产物，以及剩余的燃料和氧化剂。在此之前，关于水力学及胞状不稳定性的研究都是基于高温燃烧的，而没有学者考虑过低温反应下火焰面传播时的不稳定性机理。而在实际燃烧室中，当低温反应发生时，混合气的化学及热性质都发生了显著变化，火焰传播不稳定机制也一定会发生变化。本文就将对贫燃预混二甲醚/空气，低温化学反应影响下的火焰传播不稳定性进行研究。

# 1物理及数学模型

本文考虑的是二维，非稳态反应流。对不可压NS 方程采用分步投影法进行直接求解。方程离散保持四阶精度，非稳态项采用C-N格式。化学反应机理采用已在DNS中成功使用的，去除反应刚性的简化机理[2]。此机理包含30个组分和175步反应。计算过程中，本研究耦合Chemkin 软件包[3]，考虑详细的化学反应。为了精确计算组分输运，同时耦合 Transport 软件包[4]。和之前应用此机理的DNS研究不同，本文考虑详细的组分输运过程。研究的物理模型为二维平面火焰，左侧为未燃混气进口，右侧为已燃气体出口。上下边界采用周期边界条件。

计算初始，将采用Chemkin的Premix程序计算得到的层流火焰结构，设置在二维计算域中，并设置火焰位置为 Sin 函数分布，扰动幅值为一个火焰厚度。

计算区域长度为60 倍火焰厚度，高度为一个扰动波长。网格分辨率为 $6 0 0 \times 1 2 0$ ，时间步长为$1 { \times } 1 0 ^ { - 6 } \mathrm { s }$ 。为了验证本程序的准确性，将此程序计算得到的一维火焰结构和Chemkin中Premix程序计算值进行了对比，如图1所示。从图中可以看到，当前程序以及网格分辨率，能够精确地计算层流火焰。

![](images/77d17c81a78a998dd6199e147c0f6ee657870758593cdc5c8a0715fd875859d5.jpg)  
图1DME/空气火焰在常压和当量比为0.5时的温度及释热速率分布  
Fig.1Profiles of temperature and heat release rate forDME/air flame under ambient pressure and equivalence ratio of 0.5

# 2结果与讨论

对于大分子燃料，在负温度系数（NTC）区域，存在显著的低温化学反应过程。本文选取了反应机理较简单的二甲醚，同样具有这种低温反应特性，并且是常用的替代燃料。其化学简化机理，已经和详细机理在不同压力和当量比下的火焰传播速度、点火延迟时间以及包括点火和灭火拐点的“S"曲线进行了对比。对比结果表明，此具有30组分，175步反应的简化机理，可以很好的模拟低温及高温反应影响下的火焰行为。图2是本文给出的DME/空气在当量比为0.5，压力分别为0.1MPa和1.5MPa时的点火延迟曲线。图2中实线为高温点火，而点线所代表的是低温点火。在NTC区域低温反应显著，从而出现了点火延迟时间更短的低温点火。在当前先进发动机中，随着压力和预热温度的提高，可以看到高温点火延迟时间缩短的同时，其高压下低温点火延迟时间更短。因此，在混合气进入高温反应区燃烧之前，就已经发生了低温化学反应，甚至已经发生了低温点火。本文选取初始温度为600K，当量比为0.5的DEM/空气混合气，对其二维平面火焰进行基于详细反应和输运的直接数值模拟。基于计算，研究其低温反应对火焰水力学及胞状不稳定性的影响。图3即为其释热速率以及重要中间组分随时间的变化。

![](images/0b26b476668fa7ed46c18e2b0294e25f5becdf9e79d720cba3a6cdf99f7330e1.jpg)  
图2当量比为0.5,DME/空气在常压及15个大气压下，点火延迟时间随初始温度的变化。

![](images/2fe54726cea60e313bede7b20d72a2ac1ce9e8ae58c49866d3a6990d06e6a7b7.jpg)  
Fig.2 Ignition delay time as a function of initial temperature for DME/air flames at equivalence ratio of 0.5 under ambient pressure and elevated pressure of $1 . 5 \mathrm { M P a }$   
Fig.3 Profiles of heat release rate and medium molecules versus time for homogeneous DME/air flames at NTC and autoignition

由于所取工况属于NTC区域，因此可以明显看到在0.1s处发生低温点火。可以看到低温点火过程中，有大量的 $\mathrm { H O } _ { 2 }$ 生成。这是因为，在低温反应过程中，DME 首先和 $\mathrm { O } _ { 2 }$ 反应，生成 $\mathrm { C H } _ { 3 } \mathrm { O C H } _ { 2 }$ (R)和 $\mathrm { H O } _ { 2 }$ ，即 $\mathrm { R H + O } _ { 2 } { = } \mathrm { R } + \mathrm { H O } _ { 2 }$ ，同时OH也会夺取RH中的H并也生成R，即 $\mathrm { R H + O H { = } R + H _ { 2 } O }$ 。生成的R与 $\mathrm { O } _ { 2 }$ 反应，形成重要的可逆反应 $R + { \bf O } _ { 2 } { = } { \bf R } { \bf O } _ { 2 }$ 。在低温条件下，正向反应占据主导，从而 ${ \mathrm { R O } } _ { 2 }$ 后续引发的链分支反应将引起低温点火。所以，大量的 $\mathrm { H O } _ { 2 }$ 产生，说明同时有大量的R，以及 ${ \mathrm { R O } } _ { 2 }$ 的产生，从而发生低温点火。在低温点火发生时，同时有大量的 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ 产生。这是由于 $\mathrm { H O } _ { 2 }$ 大量产生，反应$\mathrm { R H + H O } _ { 2 } { = } \mathrm { R } + \mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ ，以及 $\mathrm { H O } _ { 2 } + \mathrm { H O } _ { 2 } { = } \mathrm { H } _ { 2 } \mathrm { O } _ { 2 } { + } \mathrm { O } _ { 2 }$ ，都将生成大量的 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ 。此组分的不断积累，在温度升高后发生反应 $\mathrm { H } _ { 2 } O _ { 2 } { = } 2 \mathrm { O H }$ ，从而引发高温点火。因此，在高温点火前，可以看到大量的 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ 迅速减少，而OH在高温点火处迅速上升。

在没有考虑低温反应时，初始温度为600K的DME/空气预混火焰传播过程如图4所示。

![](images/a2d6ada0db54f4227227280506b56281bffe21aab6c1ef2bed72ba1df7302fb4.jpg)  
图3均质(0D)DME/空气在NTC区域自燃过程释热速率以及重要中间组分随时间的变化  
图4初始温度为 $6 0 0 \mathrm { K }$ ，当量比0.5的DME/空气火焰面随时间演化过程  
Fig.4 Evolution of flame surfaces for DME/air flames at initial temperature of 6ooK and equivalence ratio of 0.5.

在初始时刻，平面火焰位置叠加Sin函数扰动。区域高度为一个波长，此波长是根据火焰Lewis数确定的最不稳定波数下的波长。火焰在水力学不稳定性的作用下，发生皱折。在50个单位时间后，火焰基本稳定不再变化。这是由于，基于混合物热扩散系数和燃料的质扩散系数确定的火焰Lewis数为1.68。胞状不稳定性此时起到稳定火焰的作用，即在突出位置火焰速度减小，而在凹陷位置火焰速度增大。当凹火焰变形不断增大，即拉伸率增大的同时，当地火焰速度在扩散-热作用下会增大，最终形成稳定的胞状结构。而凸火焰由于其在低拉伸率下，火焰的减速和火焰前流场匹配，从而很快就形成稳定形态。为了进一步，研究火焰初始扰动A0，随时间的增长率，本文给出了基于Matalon 等[5和Landau[等的理论给出的解，以及计算得到的结果。从图5中可以看到，本计算结果和Matalon等给出的色散关系得到的增长率基本一致。而Laudau等的理论由于没有考虑胞状不稳定性的影响，其增长率明显偏大。这也再次指明，在当前Lewis数情况下，火焰胞状不稳定性显著的抑制由水力学不稳定性引发的扰动增大。

![](images/b9eb719828bab84f010871f6c7d6d9eb36305164e2e948ee14a073e05ea4c927.jpg)  
图5 扰动增长的理论与计算值比较 Fig. 5 Comparison of theory and calculation for the disturbance growth

为了研究低温化学对上述火焰不稳定性的影响，本文平面火焰左端进口为初温600K，预热0.4s后的混合气。从图6可以明显看出，预热后的混合气火焰，其演化过程和图4明显不同。

![](images/0ff10be237f5949a39f5735c9738547f7895ade2b539632977cdf8945dfb2eba.jpg)  
图6当量比0.5的DME/空气混合物，初始温度 $6 0 0 \mathrm { K }$ 预热0.4s后建立的火焰面随时间演化过程 Fig.6 Evolution of flame surfaces for DME/air flames at initial temperature of 6ooK and equivalence ratio of O.5 after preheated time of 0.4s

在经历15个单位时间后，火焰扰动逐渐不再放大。同时，胞状结构的深度，及高度都明显小于未预热混气火焰。对预热混气火焰和未预热混气火焰扰动增长进行比较发现，预热后的混气火焰其扰动增长率明显变大，如图7。

为了说明其原因，本文对预热前后重要参数进行了分析，如表1所示。

对于Zeldovich数，预热后明显减小。说明预热启动了低温反应过程，使得预热后混气火焰整体活化能变小，反应区相对增厚。同时，无量纲放热量Q的减小，说明由于低温反应，特别是低温点火的发生，将部分化学能已转换为热能释放。

![](images/ab5a8747dd762fb531808072f620e05fbb751fe69b909f936bf9ae300b92592a.jpg)  
图7预热混气火焰及未预热混气火焰扰动增长比较 Fig.7 Comparison of the disturbance growth of preheated flames and flames without preheating

表1未预热和预热0.4s后，火焰参数对比  
Table 1 Comparison of flame parameters for preheated O.4s and flame without preheating   

<html><body><table><tr><td></td><td>Ze</td><td>Q</td><td>Le</td><td>Lec</td></tr><tr><td>未预热</td><td>7.66</td><td>2.035</td><td>1.65</td><td>0.76</td></tr><tr><td>预热0.4s</td><td>4.67</td><td>1.025</td><td>1.29</td><td>0.67</td></tr></table></body></html>

对于Lewis 数，本文采用文献的方法，基于马克斯坦长度的计算，得到火焰的Lewis数。表中可以看出，预热后混气火焰的Lewis数显著降低了。这是由于，DME分子预热后，低温反应消耗了大量燃料的同时，产生了小分子自由基，以及H2、CO和CH4等较小的分子。Le是临界Lewis数，小于此值时，胞状不稳定性将促使扰动的增大。可以看到，预热后混合气火焰需要更小的Lewis数，胞状不稳定性才能有利于扰动增长。

上述这些火焰关键参数的变化，将使得预热后火焰本质不稳定性发生变化。基于Landau等及Matalon等的理论分析，本文给出了无量纲放热量、Lewis数及Zeldovich数与火焰水力学和胞状不稳定性的关系，如图8、9所示。 ${ \sigma } _ { 0 }$ 和 $\sigma _ { 1 }$ 分别表示水力学不稳定性及胞状不稳定性对总的扰动增长率的贡献。可以看出，当放热量增大时，火焰的水力学不稳定性增强。然而，由于Lewis数大于1，胞状不稳定性随着放热量的增大，其抑制扰动增长的程度变大。特别是，随着Lewis数的增大，这种抑制趋势更明显。同时，当Zeldovich数增大，胞状不稳定性对扰动增长的抑制程度更强。因此，和预热后混气火焰相比，未发生低温反应的混合气由于具有更大的Lewis数、放热量Q和Zeldovich数，在Lewis数大于1的条件下胞状不稳定性抑制扰动增长的能力更强。所以预热后混气火焰具有更大的增长率。同时，由于Lewis数的减小，其胞状深度及高度都更小，这也和之前基于一步总包反应和简单输运关系，针对不同Lewis数下高温燃烧火焰的数值模拟研究结果相同。

![](images/548a1f5de7a62ad1b6296a04610ca5576aa48cd221d11f21932f1fc054316576.jpg)  
图8预热混气火焰增长率随无量纲放热量的变化

![](images/d7694ebe53eb8a23ea09c2b360a35958420ec4aace59d632df831237cf36ba85.jpg)  
Fig.8Preheated flame growth rates versus the dimensionless   
图9预热混气火焰增长率随Zeldovich数的变化  
Fig.9Preheated flame growth rates versus Zeldovich numbers

# 3结论

本文针对平面二维贫预混二甲醚/空气火焰，进行了直接求解耦合详细化学反应和输运过程的N-S方程的数值模拟工作。采用的化学反应机理，能够准确的描述二甲醚低温反应特性。同时，考虑详细的输运过程，增加了模拟扩散-热引起的胞状不稳定性的准确度。文章将已发生低温点火的混合气建立的火焰和未发生低温反应的DME/空气混合气火焰，其扰动演化过程进行了对比。结果表明，预热后混合气火焰的扰动增长率显著增大。为了对这一现象进行分析，本文提取了基于拉伸火焰和平面火焰综合计算得到的Lewis数以及火焰的Zeldovich数和无量纲放热量。上述参数对比结果表明，在预热后混合气建立的火焰中，这些参数都显著减小。基于已有的理论分析可知，这些量的减小表明火焰胞状不稳定性在Lewis数大于1的条件下，将抑制初始扰动在水力学不稳定机制下的增长。从而，揭示了低温化学影响下，火焰水力学和胞状不稳定性的作用规律。同时，由于Lewis数的减小，可以看到预热后混合气建立的火焰，其胞状结构深度和高度都明显减小。

# 参考文献

[1]Won S H, Windom B, Jiang B, et al., The Role of Low Temperature Fuel Chemistry on Turbulent Flame [J]. Combustion and Flame,2014,161:475-483 [2]Bhagatwala A,Luo Z,Lu T F,et al.,Numerical and experimental investigation of turbulent DME jet flames [J]. Proceedings of the Combustion Institute,2015,35(2):   
1157-1166 [3]Kee R J,Rupley F M and Miller JA,Chemkin II:a FORTRAN chemical kinetics package for the analysis of gas-phasechemicalkinetics， SAND89-8009, Sandia National Laboratories 1989 [4] Kee R J，Dixon-lewis G Warnatz J，et al.,A Fortran Computer Code Package For The Evaluation Of Gas-Phase, Multicomponent Transport Properties, SAND86-8246, Sandia National Laboratories,1986 [5] Matalon M,Matkowsky B J，Flames as gasdynamic discontinuities [J]. Journal of Fluid Mechanics,1982,124:   
239-59 [6]Landau L D,Lifshitz E M, Fluid Mechanics [M]. Oxford: Pergamon, 1959 [7]Bouvet N, Halter F, Chauveau C,et al. On the effective Lewis number formulations for lean hydrogen/hydrocarbon/airmixtures[J].International Journal of Hydrogen Energy,2013,38: 5946-5960