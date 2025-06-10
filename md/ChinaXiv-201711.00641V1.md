# 接触热阻对燃料电池温度分布影响的数值模拟

曹涛锋，母玉同，丁靖，何雅玲，陶文钰

（西安交通大学能源与动力工程学院，热流科学与工程教育部重点实验室，西安，710049）摘要：本文采用三维、非等温、以及考虑各向异性扩散层性质的燃料电池模型分析了气体扩散层和流场板肋板之间的接触热阻对电池温度分布和性能的影响。计算结果表明，接触热阻对电池最高温度及温度分布均有很大影响。电池输出电压为0.3V时，有接触热阻工况电池最大温度高于无接触热阻工况约 $8 . 5 \mathrm { K }$ 。此外，有接触热阻计算工况MEA内温度分布近似为“”型，而无接触热阻计算工况MEA内温度分布近似为“A”型。因此，对于燃料电池温度分布的准确预测，不能忽略接触热阻的影响。

关键词：质子交换膜燃料电池，数值模拟，温度分布，接触热阻中图分类号：TK121 文献标识码 A

# Numerical Investigation the Temperature Distr ibution of PEM Fuel CelI With the Effect of Thermal Contact Resistance

CAO Tao-Feng,MU Yu-Tong,DING Jing,HE Ya-Ling,TAO Wen-Quan (SchoolofEnergyandPowerEnginering,KeyLaboratoryofThermo-Fluid Science and Engineering ofMOE,Xi'anJiao tong University, Xi'an, 710049, China)

Abstract: In this paper, a three dimensional non-isothermal PEM fuel cell model with anisotropic gas diffusion layer(GDL) is applied to investigate the effect of the thermal contact resistance(TCR) between flow plate rib and GDL on celltemperature distribution and performance.From the numerical results, it is found that both the maximum cel temperature and the temperature distribution are greatly affected by TCR. When the output cellvoltage equals to 0.3V,the maximum cel temperature with TCR is about 8.5K larger than that of without TCR.Furthermore,the temperature profile of thermal contact resistance case looks like a "l" style,however, the temperature distribution without thermal contact resistance looks like a "A" style. Therefore,it is concluded that, to accurately predict the temperature distribution of a PEM fuel cell the thermal contact resistance between flow plate rib and gas diffusion layer cannot be ignored.

Keywords: PEM fuel cel; numerical simulation; temperature distribution; thermal contact resistance

# 0前言

操作温度是影响质子交换膜燃料电池性能的关键参数之一，为了确保燃料电池的稳定运行，必须将其工作温度控制在合适的范围之内。温度过高会加快质子交换膜及催化剂的衰减，影响电池寿命；温度过低会使电化学反应速率下降，或者引起电极“水淹”，造成电池性能下降。因此，合理的电池热管理方法对燃料电池的稳定运行极为重要。而理解燃料电池内传热机理以及电池温度分布则是制定电池热管理策略的基本依据。

过去十年里，学者们对电池温度分布进行了广泛研究。Vie[1]，Wang[2]， $\mathrm { L i n } ^ { [ 3 ] }$ ，以及Thoms[4]等人采用实验方法研究了不同工况下燃料电池的温度分布；与此同时， $\mathrm { J u } ^ { [ 5 ; 6 ] }$ ，Sui[7; 8]， $\mathrm { W u } ^ { \left[ 9 \right] }$ 等人则以数值方法模拟了燃料电池内的温度分布。与实验方法相比，数值模拟方法具有经济实惠，方便易用，可以得到详细的场分布等优点。

采用数值模拟方法预测燃料电池温度分布时，其准确程度依赖于以下几个问题：（1）电池热边界条件；（2）电池内热源；（3）电池各组件的导热系数；（4）电池不同组件之间的接触热阻。然而，绝大多数数值计算模型忽略了接触热阻的影响。2005年，Birgersson[1]等人采用二维模型分析了接触热阻对电池温度分布的影响。近来，Sadeghi[11;12]等人发现接触热阻是电池总热阻的主要部分，忽略接触热阻将会导致电池温度分布预测错误。

基于以上分析，本文采用燃料电池两相非等温模型研究了电池流场板肋板与气体扩散层间的接触热阻对电池温度分布的影响。以下分别介绍了该燃料电池两相非等温模型及接触热阻的实施方法，之后分析讨论了接触热阻对电池温度分布及性能的影响，最后给出了结论。

# 1计算模型与数值方法

# 1.1燃料电池两相非等温模型

本次计算采用的燃料电池两相非等温模型以本课题组开发的燃料电池宏观尺度模型为基础[13;14],加入了各向异性气体扩散层对燃料电池性能的影响。模型假设电池稳态运行，反应气体为理想气体，流动状态为层流，气体通道中无液态水，并忽略电池不同组件间的接触电阻。模型控制方程包括质量、动量、能量、组分以及电荷守恒方程，各控制方程表达式见表1，控制方程源项表达式见表2，模型参数及其他附加方程详见文献[15-18]。

# 1.2计算区域与边界条件

# 1.2.1计算区域

本文计算区域如图1所示，为平行流场板典型单元。考虑到平行流场板结构沿y方向对称，因此，计算区域取为通道和肋板的一半，包括燃料电池的所有构成部分。图1中，截面1为流动方向中心截面，Line-1为截面1上肋板与通道交界线。

# 1.2.2边界条件

不同界面的边界条件可表述为：

（1）进口边界：

给定速度及反应气体质量分数及温度，即，

$$
u _ { \mathrm { k , i n } } = \zeta _ { \mathrm { k } } \frac { I _ { \mathrm { a v } } } { n _ { \mathrm { k } } F } A _ { \mathrm { m } } \frac { R T _ { \mathrm { i n } } } { p _ { \mathrm { i n } } } \frac { 1 } { w _ { \mathrm { k , i n } } } \frac { 1 } { A _ { \mathrm { c h } } }
$$

$$
\begin{array} { r l } & { Y _ { H _ { 2 } } = Y _ { H _ { 2 } , i n } , Y _ { O _ { 2 } } = Y _ { O _ { 2 } , i n } , Y _ { H _ { 2 } O } = Y _ { H _ { 2 } O , i n } , } \\ & { T _ { i n } = T _ { c e l l } } \end{array}
$$

（2）出口边界：

假设出口边界为充分发展条件，即

$$
{ \frac { \ P f } { \ P \ x } } = \ 0
$$

（3）左右边界：

假设左右边界为对称边界，即，$\nu = 0 , \frac { \ddagger { \dot { \varkappa } } } { \ddagger { \dot { \Psi } } } = 0 , \frac { w } { y } = 0 , \frac { ? f } { ? y } = 0$

（4）上下边界：

计算区域上下边界与外部环境接触，给定电池操作电压以及温度，即，

$$
\phi _ { s , a } = 0 , \phi _ { s , c } = V _ { c e l l } , T = T _ { c e l l }
$$

计算区域几何参数及边界条件相关取值见表3。

![](images/d5264876a2d4dcab17a52c5c3941d2b97cde1773404e72a6d3f16fc5b5fc2a81.jpg)  
图1计算区域  
Fig.1 Computational domain

# 1.3接触热阻的实施方法

气体扩散层一般由碳纸制成，其表面粗糙，无法与气体通道肋板充分接触，通常在二者接触面上产生接触热阻，增加传热阻力。由于接触界面的间隙很小，无法直接建模。因此，本文在实施接触热阻时，将流场板肋板划分为两部分，如图1所示。通过改变靠近气体扩散层部分肋板的导热系数，使其产生的热阻与接触面形成的接触热阻相当，以达到接触热阻的效果。单位面积热阻通常表示为：

$$
R _ { _ A } = { \frac { d } { l } }
$$

因此，靠近气体扩散层部分肋板薄层的导热系数为，

$$
l = \frac { d _ { R i b \_ S } } { R _ { A , c t } }
$$

<html><body><table><tr><td>质量守恒方程</td><td>V（pug)=Sm</td></tr><tr><td>动量守恒方程</td><td></td></tr><tr><td>组分守恒方程</td><td>V（ρu@)=V（ρDkeV@k)+S</td></tr><tr><td>电荷守恒方程</td><td>V.(Φ)=S， V.(oVΦm)=S</td></tr><tr><td>能量守恒方程</td><td>V（pcpuT)=V（(kefrVT)+ ST</td></tr><tr><td>液态水饱和度方程</td><td></td></tr><tr><td>膜水含量方程</td><td>V.(DwVcw)-V. =Sd i nF)</td></tr></table></body></html>

Table 2 Source terms in different regions   
表3模型几何尺寸及操作参数  

<html><body><table><tr><td>控制方程</td><td>源项</td></tr><tr><td>质量守恒方程</td><td>催化层：Sm=Sn+S+Sw</td></tr><tr><td>动量守恒方程</td><td>扩散层及催化层：Su =-μgug/KKrg</td></tr><tr><td>组分守恒方程</td><td>阴极催化层：S。=-(ic/4F)M。，阳极催化层：Sn=-(ia/2F)Mn 催化层：S=Sa+S，扩散层：S=S,</td></tr><tr><td>电荷守恒方程</td><td>阳极催化层：S,=-i，阴极催化层：S=ic 阳极催化层：Sm=ia，阴极催化层：S,m=-ic</td></tr><tr><td>能量守恒方程</td><td>催化层：S=(n+𝜏)+²，质子交换膜：S=² Km dTKm</td></tr><tr><td>液态水饱和度方程</td><td>ShD(1-s)(Pw-Pso）)q+Apred S= Apore ShD s(pw- Psa)(1-q)</td></tr><tr><td>膜水含量方程</td><td>阳极催化层：Sd,a=-γa(Cw,a-cwa) 阴极催化层：Sd.c=-γd(cw.c-cw.c)+ic/2F</td></tr></table></body></html>

表2不同区域源项表达式  
Table3 Model geometric dimension and operating parameters   

<html><body><table><tr><td>参数</td><td>符号</td><td>单位</td><td>值</td></tr><tr><td>操作温度</td><td>Tcell</td><td>K</td><td>353</td></tr><tr><td>操作压力</td><td>Pa/pc</td><td>Pa</td><td>101325/101325</td></tr><tr><td>阳极/阴极化学计量比</td><td>5a15</td><td></td><td>3/3</td></tr><tr><td>入口氢气/空气相对湿度</td><td>RHa/RHc</td><td></td><td>60%/60%</td></tr><tr><td>流道尺寸</td><td>lx创w，h</td><td>mm</td><td>25创 0.6</td></tr><tr><td>扩散层厚度</td><td></td><td>mm</td><td>0.257</td></tr><tr><td>膜厚度</td><td>hmem</td><td>mm</td><td>0.23</td></tr><tr><td>催化层厚度</td><td>h</td><td>mm</td><td>0.0284</td></tr><tr><td>接触热阻</td><td>Rct</td><td>m²-k·w1</td><td>2.5×10-4</td></tr></table></body></html>

# 2 结果和讨论

计算用到的电池操作条件见表3。为了分析接触热阻对电池温度分布和性能的影响，本节对比了有接触热阻和无接触热阻两种工况的温度分布，阴极液态水饱和度分布，以及电池极化曲线。

# 2.1 温度分布

电池输出电压为0.6V时，两种工况下的电池温度分布如图3所示。可以发现，两种工况下，电池流道下温度均高于肋板下温度，这是因为通道中气体导热系数远小于肋板导热系数，肋板下的热量较通道下更容易散出。有接触热阻时，电池最高温度高出无接触热阻工况约 $3 ^ { \circ } \mathrm { C }$ ，且电池中心高温区较大，这是因为接触热阻增大了传热阻力，使得电池内产生的热量不易散出。

不同电压下，沿流动方向中心截面位置，流道与肋板交接处温度沿 $z$ 方向变化情况如图4所示。可以看出，随着电压的升高，电池最高温度降低，这是因为，电压升高时，电流减小电池产生的热量减小。对比图 4(a)和(b)可以发现，有接触热阻时电池最高温度高于无接触热阻时，电池电压为0.3V时，有接触热阻时电池最高温度约为365K，而无接触热阻时，电池最高温度仅为356.5K，二者相差8.5K。这同样是由于接触热阻增大了传热阻力，阻碍电池内产生的热量向外散发。此外，两种工况下温度分布曲线亦有很大不同。有接触热阻时，肋板上温度几乎不变，到达气体扩散层时，突然升高，另外，MEA内温度变化相对平缓，尤其气体扩散层内温度变化较小，温度分布近似呈“”型。

![](images/1339f8d1f53307b9a95b513cd25aa32a6d1f051a62d944fdaf5c1e75b77470c9.jpg)  
图3温度分布(a)接触热阻工况(b)无接触热阻工况 Fig.3 Temperature distribution (a) with TCR(b) without

![](images/b37d217b62267e86f4286b6c0159825ca4da6aaf329b8954fc8fb2787c658eed.jpg)  
图4不同电压下Line-1位置温度分布曲线（a）接触热阻工况，（b）无接触热阻工况  
Fig.4 Temperature profiles along Line-1 under different cell voltage (a) with TCR，(b) without TCR

而无接触热阻时，肋板内温度呈线性变化，从边界处逐渐升高；而MEA内温度变化较快，以阴极催化层为中心，近似呈“∧”型分布。因此，采用数值模拟方法预测电池温度分布时，不能忽略接触热阻的影响。

# 2.2阴极液态水饱和度分布

电池电压为0.6V时，流动方向中心截面处，阴极液态水无量纲饱和度分布如图5所示。由于饱和蒸汽压受温度影响较大，温度高时，水的饱和蒸汽压升高，饱和度降低，温度低时，水的饱和蒸汽压降低，饱和度升高。因此，电池肋板下饱和度高于通道下饱和度，扩散层内饱和度高于催化层。同样，有接触热阻时，电池内温度较高，所以，有接触热阻时，电池内液态水饱和度低于无接触热阻时。

![](images/0c531a2f5e1d919db69a3289046d4f490b35a659093a06f7791b551a424d3cb7.jpg)  
图5阴极无量纲饱和度分布（a）接触热阻工况，（b）无接触热阻工况

# 2.3电池极化曲线

两种工况下计算得到的电池极化曲线如图6所示。电压高于0.6V时，两种工况极化曲线无差别，电压高于0.6V时，有接触热阻时电池性能优于无接触热阻时，当电池电压为0.3V时，二者相差 $8 \%$ 。

![](images/df42cf01ebed68ca45e18aff7eb12ff49ce57cdda9e11cd9e80cee5a306bad59.jpg)  
Fig.5 Water saturation distribution of cathode electrode (a) with TCR，(b) without TCR   
图6电池极化曲线（a）接触热阻工况，（b）无接触热阻工况 Fig.6 Cell polarization curve(a) with TCR,(b) without TCR

值得指出的是，本文模型未涉及接触电阻，因此，极化曲线的差别仅由温度分布不同引起。之前的分析指出，接触热阻使电池内温度升高，液态水饱和度降低，减轻了水淹现象，有利于反应气体的扩散。电池电压较高时，浓差极化不明显，因此，二者极化曲线无差别；电压较低时，浓差极化作用逐渐加强，有接触热阻工况饱和度低，有利于传质，因此性能较无接触热阻时好。

# 3结论

本文采用三维两相非等温燃料电池计算模型分析了接触热阻对电池性能的影响，计算结果表明：（1）接触热阻对电池内温度分布有很大影响，有接触热阻工况，电池最高温度为365K，电池肋板内温度几乎保持不变，MEA内温度近似为“”型分布；而无接触热阻工况，电池最高温度为356.5K，电池肋板内温度从边界开始逐渐升高。MEA内温度呈“Λ"型分布。因此，模拟温度分布时不能忽略接触热阻的影响。（2）有接触热阻工况，电极液态水饱和度较低，此外，由于模型未涉及接触电阻，电池性能略高于无接触热阻工况，最大差别约 $8 \%$ 左右。

# 参考文献

[1] Vie P J S,Kjelstrup S. Thermal Conductivities from Temperature Profiles in the Polymer Electrolyte Fuel Cell[J]. Electrochimica Acta, 2004,49(7): 1069-1077.   
[2] Wang MH, Guo H,Ma C F.Temperature Distribution on the MEA Surface of a PEMFC with Serpentine Channel Flow Bed[J]. Journal of Power Sources,2006,157(1): 181-187.   
[3]Lin H,Cao T F,Chen L,et al. In Situ Measurement of Temperature Distribution within a Single Polymer Electrolyte Membrane Fuel Cell[J]. International Journal of Hydrogen Energy,2012,37(16): 11871-11886.   
[4] Thomas A,Maranzana $\mathrm { ~ G ~ }$ Didierjean S, et al. Measurements of Electrode Temperatures,Heat and Water Fluxes in PEMFCs: Conclusions About Transfer Mechanisms[J]. Journal of the Electrochemical Society,2012,160(2): F191-F204.   
[5] Ju H C，Wang C Y,Cleghorn S,et al. Nonisothermal Modeling of Polymer Electrolyte Fuel Cells Ii. Parametric Study of Low-Humidity Operation[J]. Journal of The Electrochemical Society,2006,153(2): A249-A254.   
[6] Ju H C，Wang C Y,Cleghorn S,et al. Nonisothermal Modeling of Polymer Electrolyte Fuel Cells- I. Experimental Validation[J]. Journal of The Electrochemical Society，2005, 152(8): A1645-A1653.   
[7] Sui P C, Kumar S, Djilali N. Advanced Computational Tools for Pem Fuel Cell Design: Part 1.Development and Base Case Simulations[J]. Journal of Power Sources， 2008,180(1): 410-422.   
[8] Sui P C,Kumar S,Djilali N.Advanced Computational Tools for Pem Fuel Cell Design Part 2.Detailed Experimental Validation and Parametric Study[J]. Journal of Power Sources, 2008,180(1): 423-432.   
[9]Wu H,Berg P, Li X. Steady and Unsteady 3D Non-Isothermal Modeling of Pem Fuel Cells with the Effect of Non-Equilibrium Phase Transfer[J]. Applied Energy,2010,87(9): 2778-2784.   
[10] Birgersson E, Noponen M, Vynnycky M. Analysis of a Two-Phase Non-Isothermal Model for a Pefc[J]. Journal of The Electrochemical Society, 2005,152(5): A1021.   
[11] Sadeghi E,Djilali N,Bahrami M.Effective Thermal Conductivity and Thermal Contact Resistance of Gas Diffusion Layers in Proton Exchange Membrane Fuel Cells.Part 1: Effect of Compressive Load[J]. Journal of Power Sources,2011,196(1): 246-254.   
[12] Sadeghi E,Djilali N,Bahrami M. Effective Thermal Conductivity and Thermal Contact Resistance of Gas Diffusion Layers in Proton Exchange Membrane Fuel Cells. Part 2: Hysteresis Effect under Cyclic Compressive Load[J]. Journal of Power Sources,2010,195(24): 8104-8109.   
[13] Tao W Q,Min C H, Liu XL,et al. Parameter Sensitivity Examination and Discussion of Pem Fuel Cell Simulation Model Validation: Part I. Current Status of Modeling Research and Model Development[J]. Journal of Power Sources,2006,160(1): 359-373.   
[14] Min C H, He Y L, Liu X L, et al. Parameter Sensitivity Examination and Discussion ofPemFuel Cell SimulationModel Validation[J]. Journal of Power Sources,2006,160(1): 374-385. [15] Cao T F,Lin H, Chen L,et al. Numerical Investigation of the Coupled Water and Thermal Management in Pem Fuel Cel[J]. Applied Energy,2013,112: 1115-1125.   
[16] Cao TF,Lin H,Mu Y T, et al. Evaluation of the Empirical Relations on Water Transfer Process in PEM Fuel Cell Models[C]. The 4th Asian Symposium on Computational Heat Transfer and Fluid Flow, 2013.   
[17] 曹涛锋，林鸿，何雅玲,等.PEMFC 气体扩散层内各向 异性传递过程数值模拟[J]．工程热物理学报，2012,33(6): 1051-1055.   
CAO Taofeng，LIN Hongkong，HE Yaling，et al. Numerical Investigation of The Anisotropic Transport Process Within PEM Fuel Cell[J]. Journal of Engineering Thermophysics,2012, 33(6): 1051-1055.   
[18] 林鸿，陶文钰．质子交换膜燃料电池的三维数值模拟[J]. 西安交通大学学报,2008,42(1): 41-45.   
LIN Hong, TAO Wenquan. Three-Dimensional Numerical Simulation of Polymer Electrolyte Membrane Fuel Cells[J]. Journal of Xi'an Jiaotong University, 2008, 42(1): 41-45.