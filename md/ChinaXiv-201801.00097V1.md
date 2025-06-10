编号：166133

# 表面活性剂溶液粗粒化模型couette流动模拟

刘飞1，周文静²，魏进家1(1，西安交通大学动力工程多相流国家重点实验室，西安7100492.西安交通大学化学工程与技术学院，西安 710049)

摘要：本文主要利用粗粒化分子动力学方法对不同浓度下表面活性剂水溶液在couette 流动过程中胶束的形成、速度分布与流变性规律进行了研究。结果表明，对于相同浓度的表面活性剂溶液，随着剪切速率的增大，胶束完全动态平衡时间越来越小；而随着表面活性剂分子浓度的增加，胶束动态平衡时间也越来越小，形成胶束越来越快。在剪切速率与溶液剪切粘度关系方面，保持表面活性剂分子浓度不变情况下，随着剪切速率的增大，剪切粘度逐渐减小，呈现剪切稀化特征。

关键词：表面活性剂溶液；粗粒化分子动力学模拟；couette流动；剪切粘度中图分类号：0561.2 文献标识码：A

# A coarse-grain molecular dynamics simulation for surfactant aqueous solution in couette flow

LIUFei1 ZHOU Wen-Jing² WEI Jin-Jial

1.State Key Laboratoryof Multiphase Flow inPower Enginering,Xi'an Jiaotong University, Xi'an 710049,China;

1. School ofChemical Engineering and Technology,Xi'an Jiaotong University,Xi'an 71Oo49,China)

Abstract: In this paper,the formation of micele，velocity distribution,and rheological behavior in surfactant aqueous solution under couete flow were studied using coarse-grained molecular dynamics simulations.Simulation results show that the dynamic equilibration time becomes shorter with the increase of shear rate on the condition of the same surfactant aqueous solution concentration.Ifthe shear rate is a constant number,the formation ofa micelle Was more rapid when the surfactant molecular concentration increases in the aqueous solution. When the surfactant molecular concentration keeps constant, the shear viscosity becomes smaller with the increase of shear rate,and the shear-thinning characteristic can be obtained.

Key words: surfactant aqueous solution; Coarse-grained molecular dynamics simulations; couete flow; shear viscosity

# 0引言

随着我们对能源的需求量越来越大，新能源的开发以及能源的高效利用就变得越来越重要，而减阻作为一种有效减小管道内流动阻力的方法，可以达到节能降耗的目的。所以减阻用表面活性剂的研究成为目前的研究热点之一[1-4]。而表面活性剂在溶液中的微观结构是影响表面活性剂流变性的关键，因此深入了解表面活性剂在溶液中的胶束形成和流变性质具有重要意义。

目前对于表面活性剂溶液的研究主要集中在实验测量阶段，即通过宏观流变性的测量来推测微观结构或者直接通过电镜对表面活性剂的微观结构进行观察[5-7]。在微观结构模拟方面，一般都是针对普通聚合物的胶束形成、断裂、流变性等方面的分子动力学模拟研究，但是具体到双亲性表面活性剂，在表面活性剂溶液分子动力学模拟方面的研究较少，N.A.Volkov、N.Arai等人的研究比较有代表性。其中N.A. Volkov[8]对十二烷基硫酸钠（Sodiumdodecylsulphate，SDS）溶液中胶束形成进行分子动力学模拟，发现NaC1的加入对形成大尺寸胶束更有利，该模拟详细描述了胶束的形状特性。N.Arai[9采用DPD方法研究了纳米尺度平行通道内表面活性剂溶液在剪切流场中的流变特性，发现通过对纳米平面通道内表面进行疏水-亲水化学改性，可以使表面活性剂溶液实现由剪切变稀-剪切增稠的改变。而A． Sambasivam[l0]则首次采用分子动力学（Coarse-grained molecular dynamics,CGMD）模拟方法对CTAC+NaSal溶液剪切流场下的棒状胶束变形和断裂行为进行模拟，通过能量分析方法对单体胶束长度和剪切流场下胶束取向分布进行了研究，其中得出了CTAC胶束长度平均值为 $5 . 4 \mathrm { n m }$ 的结论，该模拟的总时间长度为 $3 \mathrm { ~ \textmu ~ s ~ }$ 。在胶束形成时间和胶束大小的定量研究方面，WataruShinoda[11]模拟了聚氧乙烯等几种表面活性剂在空气-水、油-水界面上胶束形成过程，对胶束大小与胶束形成时间进行了定量计算。在粗粒化表面活性剂溶液couette流动在大剪切率情况下流变性研究方面，J.CastilloTejas[12]对十六烷基三甲基氯化铵（CTAC）表面活性剂溶液的couette 流动和poiseuille 流动进行了粗粒化非平衡分子动力学模拟，并且首次对CTAC单体进行了一个亲水头基和四个疏水尾基的粗粒化假定，得到了不同表面活性剂浓度下溶液couette流动剪切速度与剪切应力的关系，剪切速度与剪切粘度的定量关系。作为对J．Castillo-Tejas 模拟应用范围的发展，E.O．Castrejon-González[13]实现了水-表面活性剂分子-油溶液混合物在大剪切率情况下couette流动的粗粒化分子动力学模拟，得到了随着剪切速率的增加，溶液呈现由牛顿流体向剪切变稀，再向剪切增稠，甚至最后再向牛顿流体转变的结论。

综上所述，在胶束形成时间的研究方面，研究者通常使用比较精细的分子模型进行胶束形成研究，但是这种研究有两个缺点，即通用性差和计算量巨大。所以本文采用粗粒化分子动力学方法进行研究，简化了分子模拟所考虑的分子极性和不同基团之间的受力，得到胶束的形成时间。在对表面活性剂溶液的研究方面，与前人的研究相比，主要多考虑了溶液浓度和温度这两个变量，对表面活性剂的流变性进行了定性分析，得出了与目前宏观实验结果相近的结论，加深了对表面活性剂溶液流变性的认识。

# 1数值方法

本文中坐标xyz方向的表面活性剂溶液模拟区域分别为 $3 0 \sigma \times 2 0 \sigma \times 1 5 \sigma$ （上下壁面区域Y坐标分别为 $2 0 \sigma { \sim } 2 2 . 5 \sigma$ 和 $. 2 . 5 \sigma { \sim } 0 \sigma$ ），其中每个粗粒化表面活性剂分子由一个亲水头基（直径为$4 ^ { 1 / 3 } \sigma$ ）和四个疏水尾基（直径为 $\sigma$ ）组成，粗粒化水分子直径也为 $\sigma$ 。其中表面活性剂分子头基-表面活性剂头基、表面活性剂头基-粗粒化水分子、表面活性剂尾基-表面活性剂尾基、粗粒化水分子-粗粒化水分子之间的作用均采用LJ（12-6）模型，而表面活性剂头基-其它表面活性剂分子尾基、表面活性剂尾基与粗粒化水分子之间采用LJ9-6模型施加排斥力，如图1所示。

![](images/b4e12b8a976b40c2c574b9af2323eae2c7eef6b0efd8dd95135fd6ff955bc8bb.jpg)  
图1表面活性剂与水分子受力示意

表面活性剂分子头基与相邻尾基、尾基与相邻尾基之间采用Harmonic势能模型。表面活性剂溶液采用NVT系综，固体壁面采用NVE系综。粗粒化表面活性剂溶液couette 流动如图2所示。

![](images/381ac211bc9d16db6fda03cd8864b20b11524301a5375bd8ba9749ef7cdc8762.jpg)  
Fig.1Surfactant and water CG molecule interaction   
图2粗粒化表面活性剂溶液couette流动示意 Fig.2 The surfactant aqueous solution in couette flow

# $1 . 1 \mathrm { L } \mathrm { - J }$ 模型

L-J（12-6）势能表达式：

$$
U _ { i j } ^ { L J } = 4 \varepsilon \Bigg [ \Bigg ( \frac { \sigma } { r _ { i j } } \Bigg ) ^ { 1 2 } - \Bigg ( \frac { \sigma } { r _ { i j } } \Bigg ) ^ { 6 } \Bigg ] + \varepsilon , r _ { i j } \leq r _ { c }
$$

截断半径 ${ r _ { c } } \mathrm { { = } } 2 . 5 \sigma$ 。

排斥势能函数（Replusive potential）：

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

$$
U _ { i j } ^ { R } = \varepsilon \Biggl ( \frac { 1 . 0 5 \sigma _ { i j } } { r _ { i j } } \Biggr ) ^ { 9 }
$$

可以用LJ96 模型近似替代。

# 1.2 Harmonic 模型

Harmonic势能函数表达式：

布，排布后的各个粗粒化分子坐标信息作为模拟的初始条件。此非平衡态分子动力学（NEMD）模拟中，各工况的无量纲时间步长均为0.001，每组工况运行150万步，约为 $5 . 5 \mathrm { n s }$ 。

$$
U _ { \mathrm { } _ { b } } ( r _ { i j } ) = K ( r _ { i j } - \sigma _ { i j } ) ^ { 2 }
$$

而 $\sigma _ { i j }$ 通过Lorentz-Berthelot 法则：$\sigma _ { i j } = 0 . 5 \big ( \sigma _ { i i } + \sigma _ { j j } \big )$ 计算得到。

$1 . 3 \ : \mathrm { N V T }$ 与NVE系综

NVT正则系综（使用Nose-Hoover 恒温条件）的方程为：

$$
\begin{array} { l } { \displaystyle \frac { d r _ { i } } { d t } = \nu _ { i } } \\ { \displaystyle \frac { d \nu _ { i } } { d t } = \frac { F _ { i } } { m _ { i } } - \xi \nu _ { i } } \\ { \displaystyle \frac { d \xi } { d t } = \frac { 1 } { Q } \biggl [ \sum _ { i } \frac { p _ { i } ^ { 2 } } { 2 m _ { i } } - L T \biggr ] } \end{array}
$$

𝑟，Vi，F代表粒子i的位置、速度和受力；T为目标温度；L为自由度； $\xi$ 为热动力学摩擦系数；而Q定义为恒温质量，表达式为 $\scriptstyle Q = L T \tau ^ { 2 }$ ， $\tau$ 为系统的松弛时间。

NVE系综主要在壁面使用，系统的原子数、能量、体积保持不变。

# 1.4其它模拟细节

表1各物理量无量纲化公式Table1 Dimensionless of parameters  

<html><body><table><tr><td>物理量名称</td><td>无量纲化公式</td></tr><tr><td>长度</td><td>1=lo</td></tr><tr><td>时间</td><td>t=t*τ=t*(mo²/ε)1/2</td></tr><tr><td>密度</td><td>p=p*mg-3</td></tr><tr><td>温度</td><td>T =TskB1</td></tr><tr><td>剪切率</td><td>γ=y*(0²ε/m)1/2</td></tr><tr><td>力</td><td>f=f*εg-1</td></tr><tr><td>压力</td><td>p=p*εo-1</td></tr></table></body></html>

各个粗粒化分子使用MaterialStudio进行初始排

# 3模拟结果与讨论

# 3.1胶束形成时间分析

通过对胶束形成过程的可视化观测（使用Ovito开源软件，Openvisualizationtool），可以得出couette 流动剪切速率分别为0.03、0.06、0.1、0.15、0.20、0.25六种工况下表面活性剂粗粒化分子形成胶束的时间。胶束形成的典型过程一般为初始状态-小胶束团状态-大胶束团状态-完全动态平衡状态。以表面活性剂分子浓度0.20，剪切速率0.1为例进行说明，分别如图3a，3b，3c，3d所示。

蘇\*

![](images/00d0646606d07a8cb38eabc59edd9bc534434ff493f8b83485406dab1122efdf.jpg)  
束团

![](images/114bf9ef339592eb81b982837c96b8b10ef6620569ed8eb68238901172801078.jpg)  
(a）初始状态0ns 状态0.37ns   
(b)小胶

# (c)大胶束团状态0.73ns

# (d)完全动态平衡状态3.28ns

Fig.3 The dynamic equilibrium state of micelles

表面活性剂浓度分别为0.05、0.15、0.20下不同剪切率与胶束形成时间的关系对比，如图4所示。

![](images/e2d1bd9bbf61677b269d32fad030d652782567c79ded741b8ddab3cb8c1ff878.jpg)  
图4剪切速率与胶束形成时间

Fig.4 shear velocity and micelle formation time

可以看出，表面活性剂分子浓度分别为0.05、0.15、0.20情况下，随着couette 流动上板剪切速率的增大(剪切速率分别为0.03、0.06、0.1、0.15、0.20、0.25)，胶束完全动态平衡时间越来越小。而在相同剪切速率情况下，随着胶束浓度的增加，胶束动态平衡时间也越来越小，即胶束形成速度也越来越快。

# 3.2表面活性剂浓度与溶液速度分布

研究表面活性剂分子形成的胶束对couette流动流场的影响，以couette流动剪切速率为0.1、胶束浓度分别为0、0.05、0.15、0.20的速度分布为研究对象进行说明，得到胶束浓度与速度分布关系，如图5所示。具体实现办法：在Y方向上（即速度梯度方向）从 $0 \sigma$ 开始到 $2 0 \sigma$ 结束划分出100个等距离长方体空间，即每个小长方体空间的体积为 $3 0 \sigma$ $\times 0 . 2 \sigma \times 1 5 \sigma$ 。对每个切片长方体空间内的粗粒化粒子（包括表面活性剂分子和水分子）进行一段时间内的速度平均，计算系综达到动态平衡时各个切片空间内的平均速度。

![](images/076a631c0557ac6d0efdb27af2da72dd18926a7aff0baea481a9dbd73c1e9cf2.jpg)  
图3胶束动态平衡状态  
图5胶束浓度与空间平均速度分布  
Fig.5 The relationship between micelle concentration and the spatial mean velocity distribution

从图5可以看出，在剪切速率为0.1情况下，水溶剂（表面活性剂浓度为0，图示中黑线表示）的速度分布基本是单调递增的，成斜率为1的线性分布。在加入粗粒化表面活性剂分子以后，在Y方向 $0 { \cdot } 1 1 \sigma$ 区域平均速度大于水溶剂，而 $1 1 - 2 0 \sigma$ 区域速度则小于纯水。至于是否表面活性剂浓度越小，速度分布偏离纯水越小，模拟中的数据不予支持，因为表面活性剂分子浓度为0.15时在 $1 1 - 2 0 \sigma$ 区域与浓度为0.20时相比更加偏离纯水的速度分

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

布。所以可以得出一个结论，表面活性剂浓度大小与改变couette 流动速度分布的幅度大小没有必然关系。

# 3.3剪切速率与剪切粘度关系

剪切粘度由剪切应力与剪切速率得到，计算公式为：

$$
\eta = - \frac { P _ { x y } } { \dot { \gamma } }
$$

其中 $\eta$ 为剪切粘度， $P _ { x y }$ 为剪切应力， $\dot { \gamma }$ 为剪切速率，本文计算中都进行了无量纲化。

无量纲温度 $\mathrm { T } { = } 1 . 3 5$ 、无量纲剪切速率 $\dot { \gamma } ^ { * }$ 分别为0.01、0.025、0.05、0.1、0.15、0.2、0.25时，剪切速率与剪切应力、剪切粘度的关系，分别如图6、图7所示。

![](images/f29bda60eed80e3cf6d142baf145ed4c061f4ee43262794d82e9d5cb68b4dbd1.jpg)  
图6剪切速率与剪切应力关系

![](images/abee7d0c3399f6e51b64142714595af7d46adf3d3c99455954d5d4b4e5606754.jpg)  
Fig.6 The relationship between shear rate and shear stress   
图7剪切速率与剪切粘度关系  
Fig.7 The relationship between shear rate and shear viscosity

从图6可以得出如下规律：随着剪切速率的增大，剪切应力随之增加。而随着粗粒化表面活性剂分子浓度增大，剪切应力也越大。

从图7可以看出，除了剪切速率为0.01和0.025时剪切粘度分布有些杂乱，没有呈现出剪切稀化的特征之外，之后随着剪切速率的增大，剪切粘度逐渐减小，呈现剪切稀化特征。剪切速率太小（ $< 0 . 0 3 \AA$ ），粗粒化分子的热运动干扰过大，导致系统内各层粗粒化分子不能完全做有序的couette流动，所以只取0.05-0.25有效剪切速率区域进行分析。同时可以看出粗粒化表面活性剂分子浓度与剪切粘度之间呈现正相关，即表面活性剂浓度越大，剪切粘度越大。

# 4结论

本文主要对不同浓度的表面活性剂溶液couette流动进行了非平衡分子动力学模拟，得出couette流动中剪切速率与粗粒化表面活性剂分子胶束形成时间、表面活性剂浓度与溶液速度分布、剪切速率与剪切应力、剪切速率与剪切粘度的关系。发现表面活性剂浓度和剪切速率与胶束形成时间负相关，表面活性剂浓度与溶液速度分布无必然联系。在浓度一定情况下，剪切速率越大，剪切应力越大，剪切粘度越小，呈现剪切稀化特征。通过对表面活性剂溶液中这些特定参数的分析研究，可以更深入地了解表面活性剂溶液胶束的形成以及胶束的流变特性。

# 参考文献

[1]蔡伟华，李凤臣，张红娜，等.减阻水溶液槽道湍流特性 POD 分析．哈尔滨工业大学学报．2012,44(7):51-57   
CAI Weihua,LI Fengchen, ZHANG Hongna,etal.POD analysis for the turbulent characteristics of channel flow with dragreducing aqueous solution[J].Journal of Harbin Instituteof Technology,2012,44(7): 51-57   
[2]张成伟，魏进家．表面活性剂稀溶液中柔性胶束的模 拟研究．工程热物理学报．2013,34(6):1084-1086   
ZHANG Chengwei WEI Jinjia. Simulation Study of Flexible MicellesinDiluteSurfactantSolutions[J]. Journalof Engineering Thermophysics.2013,34(6):1084-1086   
[3] Wang Y,Yu B,Wu X,et al. POD Study on Large-Scale Structures of Viscoelastic Turbulent Drag-Reducing Flow. Advances in Mechanical Engineering.2014,6:574381   
[4] Tamano S,Kitao T,Morinishi Y.Turbulent drag reduction of boundary layer flow with non-ionic surfactant injection.Journal of Fluid Mechanics.2014,749:367-403   
[5]Liberatore M W,Nettesheim F,Vasquez P A，et al. Microstructure and shear rheology of entangled wormlike

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

micelles in solution[J]. Journal of Rheology,2009,53 (2): 441- 458   
[6] Lopez-Gonzalez M R,Holmes W M, Callaghan P T.RheoNMR phenomena of wormlike micelles[J].Soft Matter,2006,2 (10): 855-869   
[7]Dreiss C A.Wormlike micelles:where do we stand? Recent developments, linear rheology and scattering techniques[J]. Soft Matter,2007,3 (8): 956-970   
[8]Volkov N A，N.Tuzov N V，Shchekin A K.Molecular dynamics study of salt influence on transport and structural properties of SDS micellar solutions[J].Fluid Phase Equilibria. 2016,1: 1-8   
[9] Arai N,Yasuoka K, Zeng X C.Nanochannel with Uniform and Janus Surfaces: Shear Thinning and Thickening in Surfactant Solution[J].Langmuir.2012,28(5):2866-2872   
[10] Sambasivam A,Sangwai A V,Sureshkumar A.Dynamics and Scission of Rodlike Cationic Surfactant Micelles in Shear Flow[J].Physical Review Letters.2015,114(15): 158302   
[11]Wataru S,Russell D V,Michael L.K.Coarse-grained molecularmodeling of non-ionicsurfactant self-assembly [J].Soft Matter.2008,4,2454-2462   
[12] Castillo T G.Rheology of wormlike micelles from nonequilibrium molecular dynamics [J].Journal of Non-Newtonian Fluid Mechanics.166 (2011) 194 - 207   
[13] Castrej6n G E O.Rheological model for micelles in solution frommoleculardynamics[J].JournalofMolecular Liquids.198(2014),84-93

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538