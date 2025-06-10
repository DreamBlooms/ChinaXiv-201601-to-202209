# 涡轮端区密封结构泄漏流动气热耦合研究

安玉戈' 刘火星¹ 邹正平1

(1.北京航空航天大学，能源与动力工程学院，航空发动机气动热力国家级重点实验室，北京，100191）

摘要：本文采用气动传热耦合计算方法研究了轮毂封严冷气和叶冠泄漏流动对涡轮性能以及热负荷的影响。研究结果表明端区泄漏流动会引起流动损失并导致涡轮做功能力下降，不同股泄漏流动对涡轮效率的影响可以近似满足线性叠加规律。固体部件热传导对叶片气动负荷几乎没有影响，而由轮毂封严冷气造成的温度梯度会显著改变壁面换热特性，此时必须采用气热耦合计算才能准确预测热负荷。

关键词：燃气涡轮；计算流体力学；热分析；泄漏流动中图分类号：V235.1 文献标识码：A

# Aerothermal Analysis of a Turbine with Endwall Leakage Flow

AN Yu-Ge' LIU Huo-Xing ZOU Zheng-Ping (1.NationalKeyLaboratoryfScienceandTechnologyonAero-EnginesAero-Thermaldynamics,choolofEnergyandPower Engineering,Beihang University,Beijing100191,China)

Abstract:This studypresents theresultsof theaerothermalanalysisofanaxial turbine with endwalleakage flowusingconjugate heattransfercomputation (CHT).As itturnsout,alinearrelationshipofperformancepenaltybetween diferentflowsystems is observed.Theresultsof thermalanalysis demonstrate thatalthough heatconduction haslitle impactontheaerodynamic characteristics,ittronglyects tetmperaturedistrbutionspeiallintepresenceofcooantandlargetmperatureadients.

Keywords:Gas turbine; Computational fluid dynamics; Thermal analysis; Leakage flows

# 0前言

航空发动机遵循布雷顿循环，提高涡轮前温度从而增大循环功并提高热效率是研制高推重比高性能先进航空发动机的重要途径。现代航空发动机的涡轮燃气温度已经远远超过了部件材料的耐温能力，因此在航空发动机中广泛采用冷却技术保证涡轮部件的安全工作，尤其是在转静子之间的盘腔会采用封严冷气来防止燃气入侵[1]，并在叶顶采用带冠结构减少泄漏流量。据统计在发动机中引自压气机的冷却气体高达主流流量的 $2 0 \% ^ { [ 2 ] }$ ，其中仅涡轮封严冷气就可以消耗整机耗油率的 $6 \% ^ { [ 3 ] }$ ，由于叶冠泄漏流体不做功也会引起效率随泄漏流量的线性下降[4]。先进航空发动机对涡轮性能越来越高的要求迫使研究者们开始关注泄漏流动对涡轮性能和热负荷的影响，采用精细化设计减小冷气量和附加的气动损失。

随着技术的进步越来越多的研究者针对泄漏流动对涡轮流场和热负荷的影响展开研究，例如Ong等人[5采用非定常的实验和数值方法研究了封严气体对于涡轮性能以及二次流动带来的影响，并且分析研究了冷气预旋角度对冷却效果以及附加的流动损失的作用；Ameri 和Bunker通过绝热壁和等温壁的CFD计算获得转子叶顶的对流换热系数分布，指出了叶尖热负荷与泄漏流动结构密切相关，精确把握流动结构特征是准确预测热负荷的前提；Haller和 Hilditch[7研究了叶冠外表面的对流换热特性。以上热分析方法仅仅通过CFD计算获得绝热壁温或流体域边界换热特性，如果需要得到实际部件温度还需要进行额外的热传导计算，因此被称作非耦合热分析方法。随着计算技术的进步，气动传热耦合计算方法（Conjugate heat transfer，CHT）也逐步在涡轮叶片热分析[8]，优化内冷系统设计[9]上获得应用。这些研究加深了我们对涡轮端区密封结构泄漏流动对主流流场和热负荷的影响的认识。然而在实际工作中，涡轮主流流动会同时受到轮毂叶冠等多股泄漏流动的影响，在封严冷气引起的强温度梯度的影响下固体域热传导现象也会影响到部件的换热特性，随着涡轮负荷的进一步增大，主流和泄漏流动系统之间的相互作用、流场和温度场之间的耦合影响必将更加强烈。这就要求我们对传统研究针对单一的轮毂或叶冠泄漏流动进行的分析得到的结论以及采用单纯CFD 计算获得涡轮部件热负荷分布规律的适用性和可推广性进行审视。欧盟的第六框架计划中的MAGPI[2]和AITEB[10]项目也开始展开类似的探讨，针对计及真实涡轮环境的端区泄漏流动引起的气动传热相关现象进行研究。

本文研究工作采用气动传热耦合的计算方法研究了轮毂封严冷气和叶冠泄漏流动对某单级涡轮流场和性能的影响以及不同流动系统之间流动特征的非线性叠加效应；针对轮毂封严冷气对部件热负荷的影响进行了研究，并在此基础上分析了强温度梯度条件下的涡轮部件温度场与流场的耦合作用机制及其对传统非耦合热分析方法计算精度带来的影响。

# 1数值模拟方法

# 1.1计算程序

本文工作采用商用程序CFX进行气动传热耦合计算，流体域求解雷诺平均的NS方程，采用SST(shear stress transport)湍流模型对方程进行封闭，使用 $\gamma _ { - R e _ { \theta } }$ 转挨模型预测转捩并考虑其对流动和换热带来的影响，在固体域通过求解能量方程来模拟热传导。对于非耦合热分析方法，首先采用绝热壁CFD计算得到参考温度 $T _ { r e f }$ 的分布，并通过式(1)算得壁面温度 $T _ { w }$ 分布，其中8T为可以使壁面产生热流的微小温升；再采用给定壁面温度的方式进行第二次CFD计算获得热流密度q的分布，进而可以通过式(2)得到流体域边界的对流换热系数；随后以采用第三类边界条件以绝热壁温为参考温度，并给定边界换热系数来求解固体域导热方程，即可获得涡轮部件温度分布。

气入侵。同时对于本涡轮转子盘的后表面直接暴露于燃气中，因此在封严冷气和主流燃气的影响下在转子盘内部形成了非常强的温度梯度，流场和温度场之间也会有强相互作用。在计算中主流进口给定总温总压，封严冷气进口给定流量和温度，在流体域转动部件和静止部件之间采用掺混面模型，流体和固体域边界保证温度和热流连续，在固体域的外边界给定温度分布。计算网格如图2所示，主流道采用分块结构化网格，由16个网格块构成，轮毂、叶冠封严腔和固体域采用了非结构化的六面体网格，在近壁面进行了加密，保证y $^ +$ 小于1，三维计算网格总单元数为830万。在计算分析之前进行了网格无关性验证，结果表明当继续增加网格数目时涡轮输出功和叶冠泄漏流量及叶片平均温度几乎无变化。

![](images/415d99a0e45bdce4c7a3fb69550e4e49443f1d67e7d1c8cf378d4340d5a9f695.jpg)  
图1涡轮结构示意图

$$
T _ { \scriptscriptstyle w } = T _ { \scriptscriptstyle r e f } + \delta T
$$

$$
\alpha = \frac { q } { T _ { \scriptscriptstyle { w } } - T _ { \scriptscriptstyle { r e f } } }
$$

# 1.2计算模型及网格

![](images/a90f2663015dc5dedcd7b7cd89a1dd32d77369f3d9124342258c3092c51231a3.jpg)  
Fig.1Turbine model geometry   
图2计算网格  
Fig.2 Computational grid

采用带有盘腔及叶冠结构的某发动机单级跨音涡轮为算例进行研究，该涡轮结构如图1所示。涡轮设计转速 $1 7 0 0 0 \mathrm { r / m i n }$ ，设计点膨胀比为1.8，载荷系数为1.95。冷却气体通过迷宫封严进入转静子之间的盘腔，降低涡轮盘热负荷，并最终注入主流道防止燃

# 2计算结果及讨论

# 2.1泄漏流动对性能的影响

为分析轮毂和叶冠泄漏流动对涡轮性能的影响及各个泄漏流动系统之间的相互作用，本文分别对理想主流道流动、叶冠泄漏影响下的流动、轮毂封严冷气影响下的流动以及叶冠泄漏和轮毂封严同时作用下的流动进行了计算研究。图3给出了各种不同几何复杂度计算获得的涡轮效率，定量地比较了轮毂叶冠泄漏流动对涡轮性能造成的影响。值得注意的是，在气冷涡轮发展过程中众多的学者和研究机构以及企业基于多种掺混做功模型对涡轮效率的定义进行了研究，然而就目前而言尚未对效率的定义方式达成一致[11]，本文的分析研究采用了工业上广泛采用的效率定义方式，如式(3)所示，分母为燃气和冷气的等熵膨胀功，分子为扭矩乘以转速即涡轮实际输出功。从图中可以看出轮毂封严冷气会导致涡轮效率下降 $1 . 1 8 \%$ ，而叶冠泄漏流动会引起高达$2 . 2 9 \%$ 的效率下降。当同时存在着叶冠泄漏和轮毂封严时效率的下降与两者分别造成的效率损失之和非常接近，仅有 $0 . 0 2 \%$ 的效率差别。这说明在本算例轮毂和叶冠泄漏流动系统对性能的影响可以看做是线性叠加的。同时需要进一步指出的是对于本文计算模型，叶冠泄漏流量高达主流流量的 $2 \%$ ，按照传统的叶冠损失理论，泄漏流量造成的做功能力损失及效率下降等于其流量百分比，因此叶冠泄漏的做功损失是本算例泄漏流动最大的损失来源。

$$
\eta = \frac { P } { P _ { _ { i s } } } = \frac { T \mathbb { Z } \omega } { \dot { m } _ { m } C p _ { g } \Delta T _ { t g i s } + \dot { m } _ { c } C p _ { c } \Delta T _ { t c i s } }
$$

![](images/ea5025e05ca74f1675a8497106806efccd0424fee26ceff153a6b002336de500.jpg)  
图3泄漏流动对涡轮效率的影响 Fig.3 Influence of leakage flow on efficiency

# 2.2泄漏流动对热负荷的影响

端区泄漏流动在对主流燃气流动结构以及涡轮性能造成显著影响的同时，也影响着涡轮部件热负荷的分布。如图4即为通过气热耦合计算获得的涡轮固体部件的无量纲温度分布，无量纲温度0可以通过式(4)求出。由于封严冷气和主流燃气之间存在着温差，导致涡轮盘内部形成了很强的温度梯度，尤其是存在于转子叶根的温度梯度会对结构强度产生不利影响。在这种情况下涡轮盘的热传导现象也会显著地影响封严气体的流动换热特性，而换热特性的改变又会反过来影响温度分布，从而形成一个耦合问题。图5给出了采用气热耦合计算和绝热壁计算获得的转子叶片 $5 \% . 5 0 \%$ 和 $9 5 \%$ 叶高三个截面的等熵马赫数分布，等熵马赫数可以通过式(5)计算获得，其中 $p _ { r e f }$ 是转子进口的平均总压。计算结果表明绝热壁计算获得的气动负荷分布与通过气热耦合计算获得的结果几乎完全相同，这说明叶片热传导对气动负荷的影响非常小，在气动设计与计算中完全可以将之忽略。

![](images/d461211d0e63e2c9a1644d1cacb52974ff6d16a3fbe99320bfa60838f1d91bf5.jpg)  
图4涡轮部件温度分布

![](images/1227cd3f1f07fdf27a6e907269849ae36a37f5f47a099a2710cafede525986ff.jpg)  
Fig.4 Temperature distribution of the turbine   
图5转子叶片表面等熵马赫数分布Fig.5Isentropic Mach number distribution

$$
\theta = \frac { T - T _ { c } } { T _ { 0 } - T _ { c } }
$$

$$
M a _ { i s } = \sqrt { ( { ( \frac { p _ { r e f } } { p } ) } ^ { \frac { \gamma - 1 } { \gamma } } - 1 ) \frac { 2 } { \gamma - 1 } }
$$

传统的非耦合热分析方法通过给定壁面温度获得表面对流换热系数或努赛尔数等参数的分布来评价涡轮部件热负荷，必须通过额外的热传导计算才可以获得温度分布，这种计算方法无法考虑真实固体壁面温度对于流体换热特性的影响。图6对比了采用CHT计算、非耦合计算以及绝热壁计算获得的转子盘盘腔一侧温度径向分布。可以看出在实际工作中涡轮盘的温度远高于绝热壁温。由于涡轮盘的后表面直接暴露在高温燃气中，热传导现象导致了盘腔内壁温度升高，进而改变了壁面换热参数。图7给出了CHT计算和非耦合计算获得的无量纲化的对流换热系数分布，可以看出由于非耦合计算相当于获得的是参考温度附近的换热特性，因此较实际值发生了偏差。

燃气温度， $T _ { f }$ 和 $T _ { s }$ 分别为壁面两侧第一层单元流体和固体温度分布， $\varDelta n _ { f }$ 和 $\varDelta n _ { s }$ 分别为网格单元宽度。在轴向温差驱动下平板发生热传导，热流密度 $q$ 可以通过公式(6)计算获得，联立公式(2)和公式(6)即可得到壁面温度 $T _ { w }$ 的表达式如式(7)。正是由于非耦合计算获得了偏低的壁面对流换热，因此导致了对壁面温度预测偏高。

![](images/86c9635f9d00c30346c905382a8fa915bacf91462994bd6479747caf4b81e88b.jpg)  
图6转子盘温度分布

![](images/3d2ed42d7f91503a3f3623b7f0812c1fc856b25833bf18a6f41fa5b8c28c4cdc.jpg)  
Fig.6 Temperature distribution on the disk   
Fig.7Heat transfer coefficient of the disk

图8详细给出了采用CHT计算方法和非耦合计算获得转动部件的温度分布之比，在这里可以认为气热耦合计算的结果更接近物理实际。结果表明非耦合计算方法高估了盘腔表面的温度分布，并直接导致了转子叶根的温度预测值偏高，而叶根处的热负荷恰恰对机械强度分析非常重要。为进一步分析存在较大轴向温度梯度条件下的转子盘气动传热耦合问题，将其简化为一个厚度为 $L$ 的平板，如图9所示，其中 $T _ { w }$ 为盘腔壁面温度， $T _ { r }$ 为转子盘后壁

![](images/6c65575fe77bf20b87d1ddd63b8e95f46cd6b8234450d5eb68472d8ca0455717.jpg)  
图8气热耦合计算与非耦合计算结果对比Fig. 8 Temperature ration distribution

![](images/89a100e30ee82deee1c3dacb585d7accc199514b526533bec63525e824d46205.jpg)  
图7转子盘对流换热系数分布  
图9热传导对转子盘温度的影响

Fig.9 Conjugate heat transferof the disk

$$
q = k _ { s } \frac { T _ { r } - T _ { w } } { L }
$$

$$
T _ { _ w } = T _ { r } - \frac { T _ { r } - T _ { r e f } } { 1 + \displaystyle \frac { k _ { s } } { L \alpha } }
$$

# 3结论

本文采用了气动传热耦合计算方法研究了轮毂和叶冠泄漏流动对涡轮性能和热负荷的影响，并比较分析了涡轮部件的耦合和非耦合热分析方法对热负荷预测的准确度。主要结论如下：

1)轮毂和叶冠泄漏流动会引起流动损失并导致涡轮做功能力下降，不同复杂度的泄漏流动系统对性能的影响符合线性叠加规律。

2）固体部件热传导对热负荷分布具有重要影响，尤其是在轮毂封严冷气造成的温度梯度的作用下这一现象更为突出，然而热传导对叶片气动负荷几乎没有影响，因此对于气动性能工程设计和计算采用绝热壁面假设是合理的。

3）当涡轮部件内部温度梯度较大时，热传导会影响壁面温度进而影响对流换热系数，必须采用气动传热耦合计算才能获得符合物理实际的温度分布。

# 参考文献

[1] Chew JW. Developments in Turbomachinery Internal Air Systems[J].Proceedings of the Institution of Mechanical Engineers,Part C: Journal of Mechanical Engineering Science, 2009,223(1): 189--234   
[2] Dixon JA, Valencia A G, Coren D,et al. Main Annulus Gas Path Interactions—Turbine Stator Well Heat Transfer[J]. Journal of Turbomachinery,2014,136(2): 21010   
[3] Bohn D E,Decker A, Ohlendorf N,et al.Influence of an Axial and Radial Rim Seal Geometry on Hot Gas Ingestion Into the Upstream Cavity of a 1.5-Stage Turbine[R]. ASME Paper, GT2006-90453,2006   
[4] Rosic B,Denton JD,Curtis E M. The Influence of Shroud andCavityGeometryonTurbinePerformance:An Experimental and Computational Study-Part I: Shroud Geometry[J]. Journal of Turbomachinery,2008,130(4): 41001 [5] Ong J,Miller R J, Uchida S. The Effect of Coolant Injection on the Endwall Flow of a High Pressure Turbine[J].Journal of Turbomachinery, 2012,134(5): 51003--51008   
[6] Ameri A A,Bunker R S.Heat Transfer and Flow on the First-Stage Blade Tip of a Power Generation Gas Turbine: Part 2---Simulation Results[J]. Journal of Turbomachinery,2000, 122(2): 272--277   
[7] Haller B R,Hilditch M A. External Heat Transfer on a Shrouded HP GasTurbine Stage[R]. ASMEPaper, GT2007-27168,2007   
[8] York WD,Leylek JH. Three-Dimensional Conjugate Heat Transfer Simulation of an Internally-Cooled Gas Turbine Vane[R].ASME Paper, GT2003-38551,2003   
[9] Eifel M,Caspary V, Honen H,et al.Experimental and Numerical Analysis of Gas Turbine Blades With Different Internal Cooling Geometries[J]. Journal of Turbomachinery, 2011,133(1): 11018--11019   
[10] Janke E，Wolf T. Aerothermal Research for Turbine

Components: An Overviewof the European AITEB-2 Project[R].ASME Paper,GT2010-23511,2010 [11]Young JB,Horlock JH.Defining the Efficiency of a Cooled Turbine[J].Journal of Turbomachinery,20o6,128(4): 658--667