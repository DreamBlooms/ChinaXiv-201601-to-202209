# 过热液滴闪蒸过程数学模型的建立与应用

季璨王乃华崔峥程林(山东大学热科学与工程研究中心，济南250061)

摘要本文以闪蒸蒸发机理的特殊性为出发点，基于过热液滴闪蒸所需热量由其内部过热能量提供这一理论基础，建立了全新的过热水滴闪蒸的现象学模型，使用 MATLAB/Simulink 进行求解，通过实验验证其有效性。经计算得出了闪蒸过程中液滴温度、直径、质量、蒸发速率和蒸发率的变化规律，并利用控制变量法，研究初始温度、闪蒸压力和液滴粒径对液滴温度变化、蒸发速率、蒸发率和闪蒸时间的影响，得出了具有代表性的结论。

关键词过热液滴；闪蒸；数学模型；影响因素中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)04-0869-07

# The Development and Application of a Mathematical Model for Superheated Droplet Flash Evaporation

JI Can WANG Nai-Hua CUehng CHENG Lin

Abstract Considering the particularity of the mechanism of flash evaporation,a new phenomenological model for superheated droplet fash evaboration was built. This model was based on the idea that the heat needed for evaporation was provided by the superheat energy inside the droplet. The model was calculated using MATLAB/Simglink and was validated by experimental data. The evolution of the droplet's temperature, diameter，mass, evaporation rate and flash effciency was obtained. The infuence of initial temperature, evaporation pressure and droplet diameter on the droplet's temperature evolution,evap6ration rate, flash effciency and fash duration time was investigated and representative conclusions were made. >

Key wordssuperheated droplet; fash evaporation; mathematical model; influencing factors

# 0引言

液滴和喷雾的蒸发因在工程上有重要应用价值而成为数十年来的研究热点。其中，喷雾闪蒸作为一种特殊的蒸发形式，在工业余热利用、航空航天内燃机等领域的应用前景广阔，近年来逐渐受到重视。液滴闪蒸是喷雾闪蒸过程的重要组成部分，其蒸发特性和传热传质机理具有较高的研究价值。

液滴闪蒸的实验和理论研究均取得一定进展。Owen 等[1]对直径为 $1 { \sim } 3 \ \mathrm { m m }$ 的液滴在不同过热度下的闪蒸强度进行了实验研究，发现过热度对液滴闪蒸强度有重要影响。周致富等[2」以制冷剂R134a闪蒸喷雾为研究对象，得出了液滴直径和液滴速度在喷雾场中的分布。Shin 等[3]首先提出了扩散控制蒸发模型，用于预测液滴真空闪蒸结冰过程，该模型在液滴真空闪蒸研究中得到广泛应用[4,5]。Cheng 等[6]在此基础上提出了有效热导率模型，得出了比 Shin 模型更为准确的结论。Muthunayagam等[7」采用蒸汽扩散模型预测液滴真空闪蒸特性，并以实验验证模型的有效性。Adachi等[8]提出了过热液滴闪蒸过程中传热系数的关联式，在很大的过热度范围内均可使用，因此被普遍应用于燃料喷雾闪蒸研究领域[9,10]。Raju等[11] 对一个过热蒸发模型进行改进，使之同时适用于过热和非过热蒸发过程，并使用MonteCarlo方法对喷雾闪蒸进行计算。

综合来看，前人对于液滴闪蒸的研究多集中于压力极低、接近真空的范围；所用工质多为液态燃料；所选用的模型，例如前文提到的扩散控制蒸发模型、有效热导率模型和蒸汽扩散模型等，均是基于蒸发过程由扩散作用驱动这一假设。而在工程实际中，过热的水在常压甚至高于大气压力下的闪蒸亦有重要的应用价值。这一过程由传热驱动，前述模型并不适用。因此，本文运用质量守恒、能量守恒和传热传质等基本定律，建立过热液滴在较高压力下闪蒸的现象学模型，研究其蒸发过程和影响因素，拓展液滴闪蒸的研究范围，为过热液滴闪蒸的工程应用提供参考。

# 1过热液滴闪蒸数学模型

本文所研究的过热液滴闪蒸的基本过程是：初始温度为 $T _ { \mathrm { d } 0 }$ 、初始直径为 $D _ { \mathrm { d 0 } }$ 的过热水滴，在压力为 $\boldsymbol { p _ { \mathrm { e v } } }$ 的水蒸汽环境中发生闪蒸，环境温度维持在该压力对应的饱和温度 $ { T _ { \mathrm { b } } }$ 。为了简化计算过程，突出闪蒸的基本特点，作如下假设：1）液滴在闪蒸过程中保持为球形；2)将液滴分为内部和表面两个区，认为内部温度均匀变化，没有温度梯度；闪蒸发生在液滴表面，表面温度维持在沸点；3）忽略液滴与周围环境的辐射及对流换热；4)不考虑液滴内部因过热产生的微爆效应；5)忽略液滴内部气泡对蒸发的影响；6）在同一工况下，闪蒸罐内部温度和压力恒定。 学扑

闪蒸与普通蒸发在机理上最主要的区别是，普通蒸发所需热量主要由来自周围气体的外部传热供应；而闪蒸所需热量主要由液滴本身的过热能量提供，蒸发速率受液滴由内向外的热量传递控制。在较低的过热度下，液滴内部的导热和对流是主导的传热过程；在很高的过热度下，蒸汽空化占主导。相关过程极其复杂，无法建立分析解。因此，在建立液滴闪蒸数学模型的过程中，使用基于经验的传热系数，忽略液滴内部气泡形成、生长和破碎等因素的影响，在满足工程应用精度的前提下，达到简化计算、提高效率的目的。闪蒸蒸发速率表达式是： 6

$$
\dot { m } _ { \mathrm { e v } } = 4 \pi r _ { \mathrm { d } } ^ { 2 } \alpha _ { \mathrm { s } } \frac { T _ { \mathrm { d } } - T _ { \mathrm { b } } } { h _ { \mathrm { f g } } } = \pi D _ { \mathrm { d } } ^ { 2 } \alpha _ { \mathrm { s } } \frac { T _ { \mathrm { d } } - T _ { \mathrm { b } } } { h _ { \mathrm { f g } } } \dot { \ltimes } \dot { \ l V } _ { 1 ) } ^ { \sim }
$$

式中： $\dot { m } _ { \mathrm { e v } }$ 是蒸发速率， $r _ { \mathrm { d } }$ 是液滴半径， $T _ { \mathrm { d } }$ 是液滴温度， $ { T _ { \mathrm { b } } }$ 是沸点温度, $h _ { \mathrm { f g } }$ 是汽化潜热， $\alpha _ { \mathrm { s } }$ 是从液滴内部向表面的总传热系数，单位是 $\mathrm { k J \cdot s ^ { - 1 } \cdot m ^ { - 2 } \cdot K ^ { - 1 } }$ 0该传热系数取自Adachi 提出的关联式[8]，考虑了液滴内部成核对换热的强化，涵盖了很大的过热度范围：

$$
\alpha _ { s } = \left\{ \begin{array} { l l } { 0 . 7 6 \Delta T ^ { 0 . 2 6 } } & { ( 0 \leqslant \Delta T < 5 ) } \\ { 0 . 0 2 7 \Delta T ^ { 2 . 3 3 } } & { ( 5 \leqslant \Delta T < 2 5 ) } \\ { 1 3 . 8 \Delta T ^ { 0 . 3 9 } } & { ( \Delta T \geqslant 2 5 ) } \end{array} \right.
$$

式中 $\Delta T$ 是液滴的过热度， $\Delta T = T _ { \mathrm { d } } - T _ { \mathrm { b } }$ 。

液滴的温度变化可以写作：

$$
\frac { \mathrm { d } T _ { \mathrm { d } } } { \mathrm { d } t } = - \frac { A \alpha _ { \mathrm { s } } \left( T _ { \mathrm { d } } - T _ { \mathrm { b } } \right) } { c _ { \mathrm { p } } \rho _ { \mathrm { d } } V } = - \frac { 6 \alpha _ { \mathrm { s } } } { c _ { \mathrm { p } } \rho _ { \mathrm { d } } D _ { \mathrm { d } } } \left( T _ { \mathrm { d } } - T _ { \mathrm { b } } \right)
$$

式中： $c _ { \mathrm { p } }$ 是液体比定压热容， $\rho _ { \mathrm { d } }$ 是液体密度， $A$ 是液滴表面积， $V$ 是液滴体积。

液滴质量的变化是：

$$
{ \frac { \mathrm { d } m _ { \mathrm { d } } } { \mathrm { d } t } } = - { \dot { m } } _ { \mathrm { e v } }
$$

式中 $m _ { \mathrm { d } }$ 是液滴质量。

液滴直径的表达式是：

$$
D _ { \mathrm { d } } = \left( \frac { 6 m _ { \mathrm { d } } } { \pi \rho _ { \mathrm { d } } } \right) ^ { 1 / 3 }
$$

液滴的蒸发率是：

$$
\mathcal { k } \llap { / } \llap { / } \llap { / } \llap { / } \llap { / } \llap { / } \llangle B _ { \mathrm { d 0 } } = \left( m _ { \mathrm { d 0 } } - m _ { \mathrm { d } } \right) / m _ { \mathrm { d 0 } } \times 1 0 0 \%
$$

式史是液滴的蒸发率， $m _ { \mathrm { d 0 } }$ 是液滴的初始质量。

# 求解方法

使用MATLAB软件的仿真平台Simulink，对过热液滴闪蒸过程进行建模与求解。根据方程 $( 1 ) { \sim } ( 6 )$ 5建立如图1所示的系统模型。为使系统清晰简洁，过热度的指数项和物性的表达式均封装在子系统内。采用固定步长三阶Runge-Kutta 算法，通过计算得出闪蒸过程中液滴温度、直径、质量、蒸发速率和蒸发率的变化情况

# 3计算绪果与讨论

# 3.1模型有效性验证

为验证数学模型的有效性，在课题组搭建的喷雾闪蒸实验台上进行实验，以工程中重点关注的参数——蒸发率为研究对象，将实验结果与计算结果作比较。虽无法对单个液滴的闪蒸过程进行直接观测，但考虑到喷雾闪蒸的基础是液滴闪蒸，其总体的蒸发率能够代表单个液滴闪蒸的结果，因此这种验证方式是可行的。实验系统如图2所示，该实验台的特点是可以在较高的液体温度和闪蒸压力下安全稳定运行。蒸发率通过计算闪蒸蒸汽流量与供水流量之比获得。

选取3组不同的工况，最终蒸发率的计算结果与实验结果的对比见表1。可以看出，计算结果与实验结果相差非常小，且计算结果均偏低，偏差的可能成因包括数学模型选用的经验公式的准确度、计算过程中物性的准确度等。这样的误差属于工程上可以接受的范围，可以认为本文建立的数学模型能够准确的描述液滴闪蒸过程。

![](images/164396a39590c7708141ef8cbe00ebeea2807c605b73decf18363d16138612ee.jpg)  
图1系统模型Fig.1 Systematic model

![](images/afed56dd5048ffa3eb8a5ea57711fbf11341740417181002e8bb62bd2eb13afe.jpg)  
图2闪蒸实验系统

# 表1蒸发率的计算值与实验值对比

Table1 Comparison between calculated and experimental results   

<html><body><table><tr><td>case</td><td>Tdo/K</td><td>Pev/kPa</td><td>ncal/%</td><td>nexp/%</td><td>error/%</td></tr><tr><td>1</td><td>414.7</td><td>120</td><td>6.76</td><td>6.92</td><td>-2.3</td></tr><tr><td>2</td><td>415.6</td><td>126</td><td>6.68</td><td>6.82</td><td>-2.0</td></tr><tr><td>3</td><td>419.2</td><td>131</td><td>7.13</td><td>7.35</td><td>-2.9</td></tr></table></body></html>

# 3.2闪蒸过程典型曲线

通过求解多个工况下的液滴闪蒸方程发现，液滴温度、直径、质量、蒸发速率和蒸发率在各工况下的变化规律相同、曲线形式一致。以液滴初始温度$4 1 8 \mathrm { K }$ 、初始直径 $1 \mathrm { m m }$ 、闪蒸压力 $\mathrm { 1 3 1 \ k P a }$ 为例，计算得出的上述各参数变化曲线如图 $3 { \sim } 7$ 所示。可以看出，蒸发在刚一开始速度非常快，液滴的温度、直径和质量都迅速降低，其中液滴温度在0.44s内就下降了 $9 0 \%$ 。随着液滴温度趋近饱和温度，蒸发速率迅速减小。与之相对应，液滴蒸发率在开始后较短时间内即大幅上升至接近最大值，此后缓慢增加直至不再改。总体来看，液滴闪蒸在很短时间内即可完成，速度非常快，远高于普通蒸发。

![](images/7c9965e36fc8e9a8441117065f6316fb01cda871ad4c4c4c904aaeea24d12882.jpg)  
Fig.2 Flash evaporation experimental system   
图3液滴温度变化曲线 Fig.3 Evolution of droplet temperature

# 3.3不同初始温度下的液滴闪蒸特性

图 $8 { \sim } 1 0$ 分别是5组不同初始温度的液滴在 $\mathrm { 1 3 1 ~ k P a }$ 的闪蒸压力下发生闪蒸时，其温度、蒸发速率和实时蒸发率随时间变化的曲线。初始温度的不同仅影响一开始较短时间内的温度曲线和温度变化速度，最终的平衡温度是相同的。初始温度越高，温度降低的速率越快。类似地，蒸发速率的差异也只在初始阶段较为明显，温度越高的液滴，蒸发速率越快；随着时间的推移，蒸发速率均迅速减小趋近0。由图10可以看出，初始温度越高，最终达到的蒸发率越大。在一定的闪蒸平衡压力下，初始温度的提高意味着过热度的增大，由式（2）可知,过热度增大则传热系数增大，从液滴内部传递的可用于蒸发的能量增多，故蒸发率增大。图11则表明，初始温度对完成闪蒸所需时间基本无影响。

![](images/c8daee8d616df2eca0ec7b46f42955e6c1f0c2a03ffd656c72368812ce9e3fb4.jpg)  
图4液滴直径变化曲线 Fig.4 Evolution of droplet diameter

![](images/c0d2501ac0f852025ea4eba082856514a1eb7deb18426f73f9e465ab3be03d6e.jpg)

![](images/4cffb3aa96a9712de804e7bc105bb36fc82943937471084fa586bac6b1bee53c.jpg)  
图5液滴质量变化曲线Fig.5 Evolution of droplet mass  
图6液滴蒸发速率变化曲线 Fig.6 Evolution of droplet evaporation rate

![](images/474f95d9ad0412143876d0fdba2b4533404a124c0920c9bcf7b1655f7b2cd6ac.jpg)  
图7液滴蒸发率变化曲线

![](images/26eb193533e0bf18a2673aaa1bf167e83ec38fd97d2ae594b65db0f92ed74fc2.jpg)  
Fig.7 Evolution of droplet fash efficiency   
图8不同初温下的温度变化曲线Fig.8 Evolution of temperature of droplets at different initialtemperatures

# 3.4不同闪蒸压力下的液滴闪蒸特性

图 $1 2 { \sim } 1 4$ 是初始温度 $4 1 8 \mathrm { ~ K ~ }$ 的液滴在6组不同的压力下进行闪蒸时，温度、蒸发速率和蒸发率随时间变化的曲线。闪蒸压力越高，最终的平衡温度越高，蒸发速率越低，最终达到的蒸发率也越低。蒸发率的降低是由于过热度的减小带来的传热系数的减小，进而引起传热量的减小所致。但是由图15看出蒸发时间基本不受闪蒸压力的影响。

![](images/175cf5daf645dcdc17286bb92638baaa9c252c0185ae8aea5d45e6df9adcc9fe.jpg)  
图9不同初温下的蒸发速率变化曲线Fig.9 Evolution of evaporation rate of droplets at differentinitial temperatures

![](images/599906698f1fad44f1ca1aba635532b522822e153e22f66c58d7ee8b632a088c.jpg)  
图10不同初温下的蒸发率变化曲线 Fig.1O Evolution of flash efficiency of droplets at different initial temperatures   
Fig.3Dvolution of evaporation rate of droplets at different D evaporation pressures

![](images/41843724b9fbb2f011e6eef84063e0c182ee2012a8e3f68a60e543a303f02f40.jpg)

![](images/6cca5d6713e8ff7c0d566264aba50cfc24a5387b363d346f921e39b9bdb4d312.jpg)  
图12不同压力下的温度变化曲线

![](images/75214a0d6d7e61961d667c3d195d9901b31e38b9deb06219cfc7f65a6c755f3b.jpg)  
Fig.12 Evolution of temperature of droplets at different evaporation pressures   
图13不同压力下的蒸发速率变化曲线

![](images/67803b2e2564b16df8d615d1e07dd9102e8795e3496f9c061da3177472363637.jpg)  
图 11闪蒸时间与初始温度的关系 Fig.11 Relationship between flash duration time and initial temperature   
图14不同压力下的蒸发率变化曲线  
Fig.14 Evolution of flash efficiency of droplets at different evaporation pressures

![](images/7949cf1a39766122a3d578cd2ad60c9d47e322d75d34fd6b065b695c640505a6.jpg)  
图15闪蒸时间与闪蒸压力的关系 Fig.15 Relationship between flash duration time and evaporation pressure

# 3.5不同粒径的液滴闪蒸特性

图 $1 6 { \sim } 1 8$ 是5组粒径不同的液滴在初始温度均为 $4 1 8 \mathrm { ~ K ~ }$ 、闪蒸压力均为 $\mathrm { 1 3 1 \ k P a }$ 的条件下蒸发时，液滴温度、蒸发速率和蒸发率随时间变化的曲线。可以看出，粒径的大小并不影响最终的平衡温度，只影响温度变化速度；粒径越大温度降低的越慢。但是粒径越大，初始阶段的蒸发速率越快。即使如此，较大的液滴仍需要较长的时间完成蒸发，最终达到的蒸发率是相同的。通过图19可以看出，闪蒸时间与粒径呈线性关系。虽然液滴的大小并不影响其最终的蒸发率，但在工程应用中，考虑到闪蒸空间的大小有限，液滴停留时间受限，应选择雾化性能良好的喷嘴，使液滴能在有限的时间内完成蒸发。

![](images/634feb4fa8e03dafbaace38e3cf8dbb0d3c54e33678ee1505aed3b8d4998822c.jpg)  
图17不同粒径下的蒸发速率变化曲线Fig.17 Evolution of evaporation rate of droplets withdifferent diameters

![](images/1d3eacb00c88af408f9c88ab7214f247aff134ae5d67c752d2189d779c81845b.jpg)  
图18不同粒径下的蒸发率变化曲线 Fig.18 Evolution of flash efficiency of droplets with different 1 diameters

![](images/6795639508af6392072b45292b8648ca4a05fdeaacde8d5631c7b8e886a65820.jpg)  
图19 闪蒸时间与粒径的关系 Fig.19 Relationship between flash duration time and droplet diameter

![](images/7c168adc3532dbee0a60d015be0dac377bbbd36d4f20826b31cd578e107e89ea.jpg)  
图16不同粒径下的温度变化曲线  
Fig.16 Evolution of temperature of droplets with different diameters

# 4结论

本文以闪蒸蒸发机理的特殊性为出发点，建立了全新的过热水滴闪蒸数学模型，并利用实验结果验证其有效性。计算得出闪蒸过程中液滴温度、直径、质量、蒸发速率和蒸发率随时间变化的曲线，并通过控制变量法研究初始温度、闪蒸压力和液滴粒径对蒸发特性的影响，得到以下主要结论：

1)过热液滴闪蒸所需热量由其内部的过热能量提供，蒸发速率受由内向外的传热速率控制。  
2)液滴闪蒸过程中，温度、直径、质量、蒸发速率和蒸发率在初始阶段迅速变化，随后变化速度减缓直至不变。液滴闪蒸过程进行的十分迅速。  
3)在闪蒸过程中，液滴初始温度影响其温度变化速度、蒸发速率和蒸发率，不影响闪蒸平衡温度和闪蒸时间。  
4)闪蒸压力影响平衡温度、蒸发速率和蒸发率,不影响闪蒸时间。  
5)液滴粒径影响其温度变化速度、蒸发速率和闪蒸时间，不影响最终的蒸发率和平衡温度。

# 参考文献

[1] Owen I, Jalil JM. Heterogeneous Flashing'iX'Water Drops[J].International Journal of MultiphaseFlow,1991, 17(5):653-660[2]周致富,吴威涛,王国祥,等.R134a闪蒸喷雾液滴动力学特征实验研究[J].工程热物理学报，2013,34(1)：87-90ZHOU Zhifu,WU Weitao,WANG Guoxiang,et al．AnExperimental Study on the Droplets Dynamics of Flash-

ing Spray with R134a [J]. Journal of Engineering Thermophysics,2013,34(1):87-90 [3] Shin H T,Lee YP,Jurng J.Spherical-shaped Ice Particle Production by SprayingWater ina Vacuum Chamber [J]. Applied Thermal Engineering,2000,20(5):439-454 [4] 高文忠,时亚茹,韩笑生,等.混合除湿盐溶液液滴闪蒸机理 [J].化工学报,2012,63(11):3453-3459 GAO Wenzhong，SHI Yaru，HAN Xiaosheng，et al. Droplet Flash Evaporation of Mixed Dehumidification Solutions [J].CIESC Journal,2012,63(11):3453-3459   
[5] Gao W Z,Sun W Z,Anderson K,et al. Investigation on Temperature Distribution of Flash Evaporation of LiCl Droplets Released into Vacuum [J]. International Journal of Heat and Mass Transfer,2014,74:414-420 [6] Cheng W L,Chen H,Hu L,et al. Effect of Droplet Flash Evaporation on Vacuum Flash Evaporation Cooling:Modeling[J].International Journal of Heat and Mass Transfer,2015,84:149-157 [7] Muthunayagam A E,Ramamurthi K,Robert PJ.Modellng and Experiments on Vaporization of Saline Water Low Temperatures and Reduced Pressures [J].Applied Thermal Engineering,2005,25(5/6): 941-952 Adachi M,McDonell V G, Tanaka D,et al． Characterization of Fuel Vapor Concentration Inside a Flash Boiling Spray[C]//International Congress & Exposition;Detroit, Michigan,1997   
[9] Zuo B,Gomes A M,Rutland C J.Modelling Superheated Fuel Sprays and Vaporization [J].International Journal of Engine Research,2000,1(4):321-336   
[10] Ra Y,Reitz R D.The Application of a Multicomponent Droplet Vaporization Model to Gasoline Direct Injection Engines [J]. International Journal of Engine Research, 2003, 4(3): 193-218   
[11] Raju M S. CFD Modeling of Superheated Fuel Sprays [R]. Washingt DC: NASA/CR-2008-215289, 2008