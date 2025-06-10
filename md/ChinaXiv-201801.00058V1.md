# 垄沟集雨系统Laio土壤水分动态随机模型参数敏感性分析及优化

尹鑫卫1,2；李晓玲³；王琦4；张永梅1,2

：中国科学院新疆生态与地理研究所/阜康荒漠生态国家野外科学观测研究站新疆乌鲁木齐830011;2.中国科学院大学北京100049;3．甘肃农业大学水利水电工程学院兰州 730070;4．甘肃农业大学草业学院兰州730070)

摘要：水文模型参数的敏感性分析、优化和验证对提高模型率定效率和计算精度具有重要意义。为探讨Laio 土壤水分动态随机模型(Laio模型)各参数在垄沟集雨系统的敏感性，同时确定参数优化和模型验证的最佳方案，本文结合多因素敏感性分析法以及改进单纯形法(ISM)、粒子群优化算法(PSO)和混合粒子群优化算法(HPSO)，利用中国气象局定西干旱气象与生态环境试验基地 $2 0 1 2 - 2 0 1 3$ 年垄沟集雨燕麦生长季降雨、径流和土壤水分等实测数据，对垄沟集雨系统Laio 模型的13个参数进行敏感性分析、优化和验证。结果表明，平均降水量 $\alpha$ 和凋萎系数 $s _ { w }$ 对土壤水分概率密度函数（204号 $p ( s )$ 最敏感，且 $p ( s )$ 对参数 $\alpha$ 的敏感性在低土壤含水率下更明显，而对参数 $s _ { w }$ 的敏感性在高土壤含水率下更明显;3种算法(ISM、PSO和HPSO)的优化参数值均能对垄沟集雨系统土壤水分概率密度函数进行较好模拟，其峰值(CPV)、峰值位置(PP)和 $9 5 \%$ 置信区间 $( \mathrm { C I 9 5 \% } )$ )实测值与模拟值的相对误差均小于 $10 \%$ ,CM指数均大于0.5；同时，HPSO 算法优化参数的模拟效果和收敛速度均显著优于PSO算法和ISM算法，且能较显著克服 ISM算法和PSO算法存在的缺陷。故HPSO算法可作为垄沟集雨系统土壤水分动态随机模型参数优化的待选方案。该研究可为Laio模型的区域应用和模型调参提供科学指导依据。

关键词：垄沟集雨系统；土壤水分动态;Laio土壤水分动态随机模型；敏感性分析；模型参数优化

中图分类号：S152.7 文献标识码：A

# Sensitivity analysis and optimization of Laio soil moisture dynamic stochastic model parameters in ridge-furrow rainwater harvesting system

YIN Xinwei1,2, LI Xiaolin³, WANG $\mathrm { Q i ^ { 4 ^ { * * } } }$ , ZHANG Yongmei1,2

1.FukangStationforsertEcosyteObserationdExperiment,XinjagIstituteofEcoogandGogapyCineeAcadeyf Sciences,Urumqi830l,China;2.UniversityofChineseAcademyofSciences,Beijing10o049,China;3.Collegeof Water   
ConservancyandHydropoerEnginering,GasuAgriculturalUnversityLanzhou3o,China;4.CollgeofGrassandience, Gansu Agricultural University,Lanzhou 73oo7o, China)

Abstract:Ecosystemdynamics inaridandsemiaridclimatesarestronglydependentonthesoilwateravailabilitywhich,nu,is theresultof anumberofcomplex and mutually interacting hydrological processs.Furthermore,soil moisture dynamics isan indispensablepartof theresearchonthe interactions and feedbacks between hydrological procesesandterrestrial ecosystem processes，which istheresultof non-linear interactionsamong aseriesofhydrological,climatic,and ecological proceses. Consequentlysoil moisturecontentand itsdynamics needs tobestudied by stochasticeco-hydrological models，whichcan reasonablydescribethecharacteristicsofsoil moisture dynamics includingthepulse,eratic,andrandom proceses.Moreover, eco-hydrologicalmodelcalibrationandvalidationareessentialformodel evaluationandapplication.Itisimportantformodel application toaccurately estimate the valuesof eco-hydrologicalmodel parameters andto further improve thecapacityof model prediction.Inthisstudytoestablishaneffective methodsystemforsensitivityanalysis,calibrationandvalidationofLaiosoil moisturedynamic stochastic model (Laio model) parameters ina ridge-furowrainwater harvesting system in semi-arid area,a fieldexperiment with arandomized complete block design was conducted during the2012and 2013oats growing seasons atthe Dingxi AridMeteorologyand Ecological EnvironmentExperimental Station.Theexperiment wasdesignedto investigate the parameters’sensitivityanddeterminetheoptimal plan fortheparameters’optimizationofLaiomodel in diferentmulching materials (common plasticfilm,biodegradablemulching filmand manualcompacted soil)anddiferent ridge-furrowratios $( 6 0 :$ 30, $6 0 : 4 5$ ，and $6 0 : 6 0 \ [ \mathrm { c m } : \mathrm { c m } ] ;$ ）of ridge-furrow rainwater harvesting system based on the multi-factor sensitivity analysis methodand theimproved simplexmethod(ISM),the particle swarmoptimizationalgorithm (PSO)andthe hybrid particle swarm optimization algorithm (HPSO).The results indicated that: (1） the mean amount of precipitation per rainfall event $( a )$ and the degree of soil saturation at wilting point $\left( s _ { w } \right)$ were the most sensitive parameters for the probabilistic density function of soil moisture $( p ( s ) )$ in different experimental treatments,and the sensitivity of $p ( s )$ to parameter $a$ and $s _ { w }$ is more obvious under soil moisture contentand high soil moisturecontent,respectively;(2）A good agreementbetween theresult of modelingby the optimized parameters ofLaio modelusingthreeoptimizationalgorithms (ISM,PSOand HPSO)andobservation was found based on the curve shape of $p ( s )$ which included the curve peak value (CPV),the position of the peak (PP),the confidence interval of $9 5 \%$ 0 $( \mathrm { C I 9 5 \% } )$ and the consistency measure (CM),indicating the optimized parameters of Laio model by the ISM,PSO and HPSO is able to estimate the $p ( s )$ in ridge-furrow rainwater harvesting system; and (3) HPSO not only improves the global optimization performance,but alsoquickens theconvergence speed andobtains robustresults with good qualitywhich indicates HSO isan efectiveoptimization methodforLaiomodelcalibrationandvalidation inridge-furrowrainwater harvestingsystem.This study could improve theeficiencyof model parameterscalibration,upgade theacuracyof model simulationresult,and provide guidance for the application research of Laio model in ridge-furrow rainwater harvesting system.

Keywords: ridge-furrow rainwater harvesting; soil moisture dynamic;Laio soil moisture dynamic stochastic model;sensitivity analysis;model parameters optimization

水资源短缺是全球旱地农业面临的共同难题。如何充分利用天然降雨资源、确保粮食生产安全和维持农田生态系统稳定是实现旱农区“农业-生态-经济”耦合系统协调、持续发展的关键[I。同时，研发和推广高效、低廉、环保的旱作栽培技术对提高旱农区作物产量及水分利用效率具有重要的意义[2]。垄沟集雨系统利用田间起垄、沟垄相间、垄面产流、沟内高效集雨，并依靠增温、抑蒸、保土等生理生态效应，已成为水分缺乏的半干旱区农田生态系统一项重要的集水节灌措施[3-4]。其在缓解旱农区人口急剧增长、粮食日益紧缺与农业生态恶化的矛盾中发挥着至关重要的作用。

土壤水分是半干旱农田生态系统植物水分的主要来源，是养分循环和流动的载体，在土壤-植被-大气系统物质和能量转化中起着核心和纽带的重要作用[5]。认识半干旱农田生态系统与土壤水分关系和相互作用机理，对揭示农田生态系统稳定性及其水土关键要素的变化过程具有重要意义。由于影响土壤水分动态的各因素(降水、蒸散发、土壤异质性、地形等)具有随机性，特别是降雨事件发生及降雨量分布的随机性，决定了土壤水分动态模型只有以概率形式描述才具有实际意义[7]。自 Eagleson 等[8首次将随机理念纳入土壤水量平衡方程，随后 Milly[9]、Rodriguez-Iturbe 等[0]、Laio 等[1]、Porporato 等[12]、Pan 等[13]先后对不同时空尺度的土壤水分动态建立了随机数学模型，并得到广泛的应用。Laio 土壤水分动态随机模型(Laio 模型)在蒸散发项上引进了2个土壤水分临界值(调萎系数和吸湿系数)，其能对干旱半干旱区农田生态系统土壤水分动态进行更真实地描述，可为旱农区土壤水分的有效利用与管理提供理论指导。

由于半干旱区垄沟集雨系统土壤水分与多种物理、化学和生物过程以及降雨、径流、蒸散发、土壤特性、微地形及覆盖材料等密切相关，长期处于动态变化状态，且变化过程比较复杂[14-16]，所以利用Laio模型对该系统土壤水分动态进行模拟和研究是很有必要的。Laio模型共涉及土壤、植被和气候等13个参数，部分参数很难通过观测直接获取，且参数值存在极大不确定性[17-18]。故在模型应用前需考虑模型"本地化"和"区域化"问题，即需要对模型参数进行敏感性分析和优化。目前针对Laio模型参数的敏感性及获取方法已有一些研究，如姚淑霞等7在科尔沁沙地对Laio 模型参数的敏感性进行了分析，并将参数按敏感性强弱分为了3类;Miller等9对Laio模型参数的获取及其敏感性分析发现，最大蒸散量 $E _ { \mathrm { m a x } }$ 和水分胁迫点 $s ^ { * }$ 最难获取，且其敏感性也最高；任庆福等[17利用 PSO 算法对太行山山前平原典型井灌农区Laio 模型参数进行了优化，发现经率定的参数能更好地模拟作物生长期土壤水分的随机变化特征。然而，在半干旱区对不同含水率条件下垄沟集雨系统Laio模型参数的敏感性，以及各种优化算法对模型参数优化的适应度和有效性尚缺乏系统研究。鉴此，建立方便可行的模型参数优化、敏感性分析和有效性验证的方法体系对提高参数率定效率，控制模型计算误差和拓宽模型应用领域具有极其重要的意义。

本文利用中国气象局定西干旱气象与生态环境试验基地2012一2013年垄沟集雨燕麦生长季降雨、径流和土壤水分等实测数据资料，采用多因素敏感性分析法，对半干旱区垄沟集雨系统Laio土壤水分动态随机模型参数的敏感性进行分析和分类。同时，基于ISM、PSO 和HPSO 算法，对垄沟集雨系统Laio 模型的13个参数进行优化和优选，并利用实测数据资料对3种算法优化参数的有效性进行验证和评价，以期建立垄沟集雨系统Laio模型参数敏感性分析、优化和验证的有效方法体系，为Laio 模型参数校正和区域应用提供科学理论依据。

# 1材料与方法

# 1.1 田间试验和数据测定

试验于 $2 0 1 2 { - } 2 0 1 3$ 年在中国气象局兰州干旱气象研究所定西干旱气象与生态环境试验基地 $( 3 5 ^ { \circ } 3 3 ^ { \prime }$ N, $1 0 4 ^ { \circ } 3 5 ^ { \prime } \mathrm { E }$ ，海拔 $1 8 9 6 . 7 \mathrm { m } \mathrm { \Omega }$ 进行，该基地属黄土高原西部丘陵区和半干旱地区，具有典型的温带大陆性季风气候[16]。 $1 9 7 1 - 2 0 1 4$ 年平均降雨量 $3 8 8 ~ \mathrm { m m }$ ，冬季和夏季月平均降雨量分别为 $2 0 { \sim } 8 0 ~ \mathrm { m m }$ 和 150\~270$\mathbf { m } \mathbf { m }$ 。降雨在年内分布极不均匀,7\~10月降雨量占年降雨量的 $8 6 . 9 \%$ ，蒸发强烈，年均潜在蒸发量达到1500$\mathrm { m m }$ 。试验地地势平坦，土壤为重壤土, $0 { \sim } 1 0 0 \ \mathrm { c m }$ 土壤平均容重为 $1 . 3 8 ~ \mathrm { g } { \cdot } \mathrm { c m } ^ { - 3 }$ ，田间持水量为 $2 5 . 6 \%$ ，饱和含水量为 $4 3 . 8 7 \%$ ，永久调萎系数为 $6 . 7 \%$ ，地下水埋深 $1 0 . 4 ~ \mathrm { m }$ ，土壤水与地下水的水力联系微弱。当地耕作制度为1年1熟，主要种植作物有春小麦(Triticum aestivum)、燕麦(Avena sativa)和马铃薯(Solanumtuberosum)等，主要种植牧草有紫花苜蓿(Medicago sativa)和红豆草(Onobrychis viciaefolia)等。

试验采用田间垄沟集雨覆盖种植技术，以燕麦(Avena sativa)为指示作物，垄覆盖作为集雨区，沟无覆盖作为种植区，小区随机排列，共设9个处理(3种沟垄比 $\times 3$ 种覆盖材料)，重复3次。3种覆盖材料分别为生物可降解膜、普通塑料膜和土壤结皮,3种沟垄比分别为 $6 0 \ \mathrm { c m } : 3 0 \ \mathrm { c m }$ 、 $6 0 \ \mathrm { c m } : 4 5 \ \mathrm { c m }$ 和 $6 0 \mathrm { c m } : 6 0$ cm(沟宽:垄宽)。生物可降解地膜和普通塑料膜厚度均为 $0 . 0 8 \mathrm { m m }$ ；土垄为人工原土夯实，经风吹雨打形成自然土壤结皮。土垄、生物可降解地膜垄和普通地膜垄的代表符号分别为 SR、BMR和CMR。根据当地种植经验，集雨垄的坡度为 $4 0 ^ { \mathrm { o } }$ ，高为 $2 5 \mathrm { c m }$ ，长为 $1 0 \mathrm { m }$ ，每1小区有4条垄和3条沟。试验设计示意图如图1所示。相关种植管理方法按前期研究者[9]所述进行。由于本试验的3种试验沟垄比对该垄沟集雨系统土壤水分时空动态影响不显著[16-19]，故本文结果和讨论部分用到的试验数据，均为同1覆盖材料下，3种试验沟垄比的平均值。

土垄/普通膜垄/生物可降解膜垄 燕麦Oat 土垄/普通膜垄/生物可降解膜垄 Ridge with compacted soil Ridge with compacted soil or covered with common plastic film or covered withcommon plastic film or biodegradable mulch film or biodegradable mulch film 20cm 流区。 20cm ，淘 蒸散发 降雨 种植区 Evapotranspiration Rainfall 60 cm or 45 cm or 30 cm 60 cm 60 cm or 45 cmor 30 cm 图1.1燕麦种植示意图 Plant interception Fig1.1 Schematic diagram showing ridge-furrow rainwater harvesting for oats production 植物截留 表1.1垄沟集雨种植燕麦试验设计 Table 1.1 Experimental design for oats production in ridge-furrow rainwater harvesting 作物   
Furrow种植沟 Crop 集雨垄Ridge 处理 沟垄比(cm) 垫面积(m) 沟面积(m2) 小区面积(m) 垄覆盖方式 Treatment Furrow : Ridge Ridge area Furrow area Plot area Ridge mulch style   
Runoff Runoff SR30 60:30 13.5 18 31.5   
垄面径流 W YY 垄面径流 SR45 60:45 20.25 18 38.25 土壤结皮 Soil crust 孔 ..........·.. 系层Zr 000 17185201735 1818181818 3356B Biog降解地e mu im 深层渗漏Leakage CMR45 60:45 20.25 1818 3825 Common plastic film 普通地膜覆盖

图1垄沟集雨系统土壤水分动态过程及其随机模拟试验设计示意图

Fig.1Schematic diagrams showing experimental design for stochastic simulationofsoil moisture dynamics in ridge-furrow rainwater harvesting

试验期降雨量数据由试验基地自记雨量计测定。在燕麦播种前(4月10日左右)、收获后(8月 20 日左右)和降雨后(降雨量 $> 5 ~ \mathrm { m m }$ )测定土壤含水量，土壤含水量采用烘干法( $1 0 5 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ，10 h)测定，测定深度为140cm，分层深度为 $2 0 ~ \mathrm { c m }$ ，共记录7个土层的土壤含水量，每1小区随机在沟内选取3个样点，同1层次土壤含水量取3个样点平均值。集雨垄径流量由降雨量数据基于美国水土保持局研制的 SCS-CN 模型反推确定[20]。土壤容重采用环刀法测定，测定深度 $1 4 0 \mathrm { c m }$ ，分层深度为 $2 0 \mathrm { c m }$ ，每层3个重复，取均值。根系层深度通过实地调查燕麦根系生物量分布范围测定[7]。同期气象数据由邻近的试验基地气象观测站获得。

# 1.2 Laio土壤水分动态随机模型

土壤水分随机模型的理论基础是物质平衡原理：单位时间内土壤含水量的变化等于土壤水分输入项和水分损失项的差。基于前期研究者[21I对土壤水分随机模型的研究，Laio等[通过引进两个临界土壤含水量(土壤吸湿系数和土壤凋萎系数)，在空间一点上建立了时间尺度为 1d 的土壤水分平衡方程，具体模型(Laio 模型)可表述为:

$$
n Z _ { r } \frac { d s ( t ) } { d t } = \varphi [ s ( t ) ; t ] - \chi [ s ( t ) ] = R ( t ) - \{ I ( t ) + Q [ s ( t ) ; t ] + E [ s ( t ) ] + L [ s ( t ) ] \} = 0 .
$$

式中： $n$ 为土壤孔隙度； $s$ 为土壤饱和度； $Z _ { r }$ 为根系层深度 $( \mathrm { c m } )$ ； $s ( t )$ 为 $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { \mathbf { \Psi } }$ 时刻的土壤相对湿度（2 $( 0 \leq s ( t ) \leq 1 )$ ，即 $s ( t ) = \theta ( t ) / n$ ，其中 $\theta ( t )$ 为 $\mathbf { \chi } _ { t }$ 时刻的土壤体积含水量 $( \% )$ ; $\varphi [ s ( t ) ; t ]$ 是降雨入渗率 $( \mathrm { c m } { \cdot } \mathrm { d } ^ { - 1 } )$ ，表示实际到达土壤的降雨量部分，即 $\varphi [ s ( t ) ; t ] = R ( t ) - I ( t ) - Q [ s ( t ) ; t ]$ ，其中 $R ( t ) , \ I ( t )$ 和 $Q [ s ( t ) ; t ]$ 分别为降水速率 $\left( \mathrm { c m } { \cdot } \mathrm { d } ^ { - 1 } \right)$ 、植物截留率 $\left( \mathrm { c m } { \cdot } \mathrm { d } ^ { - 1 } \right)$ 和地表径流率 $( \mathrm { c m \cdot d ^ { - 1 } } )$ ；蒸散发和渗漏构成损失项，即$\chi [ s ( t ) ] = E [ s ( t ) ] + L [ s ( t ) ]$ ，其中 $E [ s ( t ) ]$ 为蒸散发强度 $( \mathrm { c m \cdot d ^ { - 1 } } )$ ， $\boldsymbol { L } [ \boldsymbol { s } ( t ) ]$ 为深层渗漏率 $\left( \mathrm { c m \cdot d ^ { - 1 } } \right)$

将降雨随机过程同土壤水蒸散发和深层渗漏的土壤水损失项相结合是土壤水分随机模型建立的基础[21-22]。由于降雨是随机过程，故需建立土壤水分概率密度函数(Soil Moisture Probability Density Function)求解土壤水平衡过程(式1)。通过将 Laio 模型的各土壤水分损失过程转化为查普曼-柯尔莫哥洛夫前进方程(Chapman-Kolmogorov Forward Function)可分析求解导出土壤水分概率密度函数，其具体表达式[7,11,21-22]为:

$$
\begin{array} { r } { p ( s ) = \left\{ \begin{array} { l l } { \displaystyle \frac { c } { \eta _ { \epsilon } } e ^ { - s \kappa } \left( \frac { s - s _ { \epsilon } } { s _ { \epsilon } } \right) ^ { \frac { \kappa ( s - s _ { \epsilon } ) - 1 } { s _ { \epsilon } } } } & { s _ { \epsilon } < s \leq s _ { \epsilon } } \\ { \displaystyle \frac { c } { \eta _ { \epsilon } } e ^ { - s _ { \epsilon } } \left( 1 + \left( \frac { \eta } { \eta _ { \epsilon } } - 1 \right) \left( \frac { s - s _ { \epsilon } } { s } - s _ { \epsilon } \right) \right) ^ { \frac { \kappa ( s - s _ { \epsilon } ) } { \beta ( \eta _ { \epsilon } - s _ { \epsilon } ) } } } & { s _ { \epsilon } < s \leq s ^ { \prime } } \\ { \displaystyle \frac { c } { \eta _ { \epsilon } } e ^ { - s \kappa ^ { 2 } \frac { \kappa ( s - s _ { \epsilon } ) } { \eta _ { \epsilon } - \epsilon } } \left( \frac { \eta } { \eta _ { \epsilon } } \right) ^ { \frac { \lambda ( s - s _ { \epsilon } ) } { \eta _ { \epsilon } - \epsilon } } } & { s _ { \epsilon } < s \leq s _ { \epsilon } } \\ { \displaystyle \frac { c } { \eta _ { \epsilon } } e ^ { - s ( s - \eta _ { \epsilon } ) } \left( \frac { \eta } { \eta _ { \epsilon } } \right) ^ { \frac { \lambda ( s - s _ { \epsilon } ) } { \eta _ { \epsilon } - \epsilon } } } & { s _ { \epsilon } < s \leq s _ { \epsilon } } \\ { \displaystyle \frac { c } { \eta _ { \epsilon } } e ^ { - s ( s - \eta _ { \epsilon } ) \kappa \frac { \kappa ( s - s _ { \epsilon } ) - 1 } { \epsilon } } \left[ \frac { \eta _ { \epsilon } e ^ { \lambda s _ { \epsilon } } } { ( \eta _ { \epsilon } - m ) e ^ { \frac { \lambda ( s - s _ { \epsilon } ) } { \eta _ { \epsilon } - \epsilon } } + m e ^ { \frac { \lambda ( s - s _ { \epsilon } ) } { \eta _ { \epsilon } - \epsilon } } } \left( \frac { \eta _ { \epsilon } ^ { - s } + s _ { \epsilon } - s _ { \epsilon } \kappa ^ { 2 } s _ { \epsilon } ^ { - 1 } } { \eta _ { \epsilon } - m _ { \epsilon } } , ~ s _ { \epsilon } < s \leq 1 \right) \right. } \end{array} \right. } \end{array}
$$

式中：常数 $\boldsymbol { c }$ 由 $\int _ { s _ { h } } ^ { 1 } p ( s ) d s = 1$ 求解得出，其他模型参数含义及取值范围见表2所示，各处理待优参数值由蒙特卡洛试错法确定。模型相关假设条件及详细推导过程详见文献[]。

表1垄沟集雨系统Laio模型参数取值范围及其不同处理下的待优化值  
ible 1Values ranges and initial values of parameters in Laio model in ridge-furrow rainwater harvesting sy   

<html><body><table><tr><td rowspan="3">属性 Property</td><td colspan="2">随机模型参数 Parameters of Laio model</td><td rowspan="3">单位 Units</td><td colspan="2">参数取值范围 Values ranges of parameters</td><td colspan="3">不同处理参数待优化值 Initial values of parameters</td></tr><tr><td>符号Symbol</td><td>意义Meaning</td><td>UBV</td><td>LBV</td><td>SR</td><td>CMR</td><td>BMR</td></tr><tr><td></td><td>n</td><td>土壤孔隙度 Soil porosity</td><td>m3m-3</td><td>0</td><td>1</td><td>0.58</td><td>0.58</td><td>0.58</td></tr><tr><td></td><td></td><td>土壤孔隙大小分布参数 Parameter describing drainage in soil</td><td>/</td><td>10.00</td><td>20.00</td><td>14.8</td><td>14.8</td><td>14.8</td></tr><tr><td></td><td>Z</td><td>土壤活动层深度 Depth of rooting zone</td><td>cm</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td></tr><tr><td></td><td>K</td><td>土壤饱和导水率 Saturated hydraulic conductivity of soil</td><td>cm·d-1</td><td>10.00</td><td>30.00</td><td>19.5</td><td>19.5</td><td>19.5</td></tr><tr><td>土壤 Soil</td><td>Sh</td><td>吸湿系数 Absorption coefficient of soil moisture</td><td>m3·m-3</td><td>0</td><td>0.10</td><td>0.026</td><td>0.026</td><td>0.026</td></tr></table></body></html>

<html><body><table><tr><td rowspan="6"></td><td rowspan="2">Sw</td><td>调萎系数</td><td rowspan="2">m3·m-3</td><td rowspan="2">0.10</td><td rowspan="2">0.40</td><td rowspan="2">0.25</td><td rowspan="2">0.25</td><td rowspan="2">0.25</td></tr><tr><td>Degree of soil saturation at wilting point</td></tr><tr><td></td><td>水分胁迫开始点 Soil saturation at stress point</td><td>m3·m-3</td><td>0.40</td><td>0.70</td><td>0.56</td><td>0.56</td><td>0.56</td></tr><tr><td>Sfc</td><td>田间持水率 Degree of soil saturation at the field capacity</td><td>m3·m-3</td><td>0.70</td><td>1</td><td>0.72</td><td>0.72</td><td>0.72</td></tr><tr><td>Ew</td><td>调萎系数对应土壤蒸发 Estimated rate of evaporation from soil</td><td>cm</td><td>0</td><td>0.02</td><td>0.012</td><td>0.012</td><td>0.012</td></tr><tr><td rowspan="2">作物 Crop</td><td>4</td><td>植物截留阈值 Interception capacity of vegetation</td><td>cm</td><td>0</td><td>0.50</td><td>0.128</td><td>0.130</td><td>0.131</td></tr><tr><td>Emax</td><td>日最大蒸散量 Maximum evapotranspiration</td><td>cm</td><td>0</td><td>1.00</td><td>0.610</td><td>0.570</td><td>0.560</td></tr><tr><td>降雨</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>Mean rainfall frequency of growing season</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>a</td><td>生长季平均降水量</td><td>cm·d-1</td><td>同初始值</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>0.5949</td><td>0.8166</td><td>0.7673</td></tr><tr><td>Rainfall</td><td></td><td>Mean rainfall depth of growing season</td><td></td><td>Same as the initial value</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>生长季平均降水频率</td><td>d1</td><td>0.33</td><td>0.33</td><td>0.33</td><td>0.33</td><td>0.33</td></tr></table></body></html>

表中模型参数取值范围由相关实测数据和文献资料[,16获得;UBV:参数取值下限;LBV:参数取值上限;SR、CMR 和BMR 分别表示土垄、普 通膜垄和生解膜。下同heagefodelparaetersinheableisaedfrothrelevatmeasreddataandierature(e.g); UBV:upperboudauefoelpaetes;:oweroudaluefodelpraetes;ndCeredgsiopactedild with biodegradable mulch film and common plastic film,respectively .The same below.

# 1.3 模型参数敏感性分析原理

模型参数的敏感性分析是研究参数变化所引起的模型响应，是模型参数不确定分析的重要内容之一，也是研发和评价模型不可缺少的重要环节[23]。同时，参数敏感性分析有助于深入理解模型的特性并改进模型结构的稳定性[24]。为不失一般性，将土壤水分概率密度函数表示为:

$$
p = f \left( x _ { 1 } , x _ { 2 } , \mathrm { L } \ , x _ { i } , x _ { n } \right)
$$

式中： $p$ 为土壤湿度概率密度； $x _ { i }$ 为第 $i$ 个影响因素； $n$ 为影响 $p$ 的因素个数。

当所有因素都发生变化，分别由 $x _ { 1 }$ ， $x _ { 2 }$ ， $\mathbf { L }$ ， $x _ { i }$ 变为 $x _ { 1 } ^ { \prime }$ ， $x _ { 2 } ^ { \prime }$ ， $\mathrm { ~  ~ \cal ~ L ~ }$ ， $x _ { i } ^ { \prime }$ ，变化量分别为 $\Delta x _ { \mathrm { _ 1 } }$ ， $\Delta x _ { 2 }$ ， $\bot$ ，$\Delta x _ { i }$ 时， ${ x } _ { 1 } ^ { \prime } { = } x _ { 1 } + \Delta x _ { 1 }$ ， $\scriptstyle x _ { 2 } ^ { \prime } = x _ { 2 } + \Delta x _ { 2 }$ ， $\mathrm { ~  ~ \cal ~ L ~ }$ ， ${ x _ { i } ^ { \prime } = } x _ { i } + \Delta x _ { i }$ ，则土壤湿度概率密度 $p$ 也发生相应变化，由 $p$ 变为 $p ^ { \prime }$ ，则可用 $\Delta p = p ^ { \prime } - p$ 表示所有因素变化共同造成 $p$ 的变化量。利用多元函数的泰勒展开式为：

$$
\Delta p \approx { \frac { { \hat { \sigma } } p } { { \hat { \sigma } } x _ { 1 } } } \Delta x _ { 1 } + { \frac { { \hat { \sigma } } p } { { \hat { \sigma } } x _ { 2 } } } \Delta x _ { 2 } + \mathbf { L _ { \rho } } + { \frac { { \hat { \sigma } } p } { { \hat { \sigma } } x _ { i } } } \Delta x _ { i }
$$

式中： ${ \hat { c } p } / { \hat { c } x _ { i } }$ 为 $x _ { i }$ 对 $p$ 的偏导数； $\Delta x _ { i }$ 为 $x _ { i }$ 的变化量。如果只有 $x _ { i }$ 因素改变，其它因素都不发生变化，即$\Delta x _ { i } \neq 0$ ， $\Delta x _ { \scriptscriptstyle l } = 0$ ， $l \neq i$ ，则土壤湿度概率密度 $p$ 的变化量记为 $\Delta p _ { i }$ ，其是 $\Delta x _ { i }$ 对 $p$ 的影响值，可表示为$\Delta p _ { i } \approx \left( \hat { c } p / \hat { c } x _ { i } \right) \cdot \Delta x _ { i }$ ，显然 $p$ 的综合变化量为 ${ \Delta p } { = } { \sum } _ { 1 } ^ { n } { \Delta p } _ { i }$ 。

定义的变化量与 $p$ 因素 $x _ { i }$ 的变化量之比为 $p$ 对 $x _ { i }$ 的敏感度 $A _ { i }$ ，则 $A _ { i } { = } \big ( \Delta p _ { i } / p \big ) / \big ( \Delta x _ { i } / x _ { i } \big )$ ，其表示第 $i$ 个因素 $x _ { i }$ 变化1个百分点，将引起土壤湿度概率密度 $p$ 改变 $A _ { i }$ 个百分点。 $A _ { i }$ 为正表示 $\Delta { p } _ { i }$ 与 $\Delta x _ { i }$ 的变化方向相同。 $\left| A _ { i } \right|$ 越大，表明因素 $x _ { i }$ 对土壤湿度概率密度 $p$ 的影响越大，即 $p$ 对 $x _ { i }$ 越敏感，可认为 $x _ { i }$ 为敏感因素。敏感度 $A _ { i }$ 计算公式如下:

$$
A _ { i } { = } \frac { { \Delta } k _ { i } / k } { { \Delta } x _ { i } / x _ { i } } { = } \frac { \left[ \left( \partial { f } / \partial { x _ { i } } \right) / { \Delta x _ { i } } \right] / k } { { \Delta x _ { i } } / x _ { i } } { = } \frac { \partial { f } } { \partial { x _ { i } } } { \cdot } \frac { x _ { i } } { k }
$$

在获取垄沟集雨系统Laio 模型各参数敏感度时，首先借助Mathematica 8.0.4软件对模型各参数敏感度 $A _ { i }$ 的通式进行求取，然后选定土壤含水率 $s$ 的范围( $0 \leq s \leq 1$ )，采用表1中不同处理的待优化参数值,计算各处理对应参数的敏感度，确定不同处理下模型敏感性参数，同时基于SOM神经网络聚类法对垄沟集雨系统Laio模型参数敏感性进行分类，并探讨同一敏感性类别的参数特征及不同敏感性类别形成的主要原因。

# 1.4 模型参数优化算法原理

# 1.4.1 改进单纯形法寻优原理

单纯形法(Simplex Method,SM)也称可变多面体搜索法，是1种局部搜索方法，由 Nelder 和 Mead 于1965 年提出[25]。其基本思想是：在 $N$ 维欧氏空间中取 $N { + } 1$ 个点构成初始单纯形，假设每个点的坐标矢量为 $X _ { 1 } , X _ { 2 } , \mathrm { L } \ , X _ { N + 1 }$ ，比较这 $N { + } 1$ 个点处目标函数值的大小，求出函数值最大点 $X _ { \scriptscriptstyle w }$ 对剩余点$X _ { 1 } , X _ { 2 } , \mathrm { L } \ , X _ { w - 1 } , X _ { w + 1 } , \mathrm { L } \ , X _ { N + 1 }$ 形心 $X _ { c }$ 的映射 $X _ { r }$ ，然后用 $X _ { r }$ 替代点 $X _ { _ w }$ ，构成新的单纯形，反复迭代，使其顶点处的函数值逐步下降，从而逼近目标函数，即采用扩张、收缩、压缩和扬弃这4种方法对各点进行处理，直至满足收敛性指标，搜索到最佳点。

本文的改进单纯形法(Improved Simplex Method,ISM)是在基本单纯形法的基础上对步长作适当修改得到的寻优方法[26]。设定最佳点(函数值 $F$ 最小)、次佳点(函数值 $F$ 次小)和最差点(函数值 $F$ 最大)的坐标矢量 $\textstyle X _ { b } , X _ { n }$ 和 $X _ { \scriptscriptstyle w }$ 的函数值分别为 $F _ { b } , F _ { n }$ 和 $F _ { _ w }$ ，映射点 $X _ { r }$ 的函数值为 $F _ { r }$ ，于是根据反射值 $F _ { r }$ 可作不同的选择:

(1)如果 $F _ { r } < F _ { b }$ ，说明反射方向正确，求扩张点坐标矢量 $X _ { _ { e } } = X _ { _ { c } } + 2 * \left( X _ { _ { c } } - X _ { _ { w } } \right)$ ，其中（204 $X _ { _ { c } } = \left( \begin{array} { l l l l l l l } { X _ { _ { 1 } } + X _ { _ { 2 } } \textbf { k } } & { + X _ { _ { 1 } } } & { + X _ { _ { 1 } } } & { \mathbf { L } + } & { \mathbf { \Lambda } + X _ { _ { 1 } } ^ { \ast } } \end{array} \right) _ { 1 }$ 。若 $F _ { e } < F _ { b }$ ，则扩张成功，用 $X _ { e }$ 代替 $X _ { r }$ ；否则扩张失败，保留X,；

(2)如果 $F _ { b } < F _ { r } < F _ { n }$ ，则不扩张也不收缩，保留 $X _ { r }$ ·

(3)如果 $F _ { _ w } < F _ { r }$ ，说明反射方向不正确，需进行收缩，求收缩点坐标矢量 $X _ { t } = X _ { c } - 0 . 5 * \big ( X _ { c } - X _ { w } \big )$ ，用$X _ { t }$ 代替 $X _ { r }$ ：

(4)如果 $F _ { n } < F _ { r } < F _ { w }$ ，求收缩点坐标矢量 $X _ { \scriptscriptstyle u } = X _ { \scriptscriptstyle c } + 0 . 5 * \left( X _ { \scriptscriptstyle c } - X _ { \scriptscriptstyle w } \right)$ ，用 $X _ { u }$ 代替 $X _ { r }$ 。

按上述 $X _ { r }$ 的计算结果，从新构造新的单纯形，作收敛性检验，反复迭代直到满足终止条件为止。ISM迭代是否结束，需根据事先给定的条件来判断。通常，可用系统响应标准偏差 $s$ 与系统响应平均值 $\overline { { F } }$ 之比COV (偏差系数)作为判据，若 $C O V < 0 . 5 \%$ ，可终止优化。

# 1.4.2粒子群优化算法寻优原理

粒子群优化算法(Particle Swarm Optimisation,PSO)是1 种基于群智能方法的演化计算技术，由Kennedy 和 Eberhart于1995 年提出[27]。在PSO 算法中，每个优化问题的潜在解均可看作是搜索空间中的1个粒子。每个粒子均有1个被优化函数决定的适应值(Fitmess Value,FV)，同时有1个速度决定的移动方向和距离，可通过跟踪当前最优粒子的个体极值和整个种群的全局极值迭代搜索最优解。

PSO 算法的基本数学描述为[28]：设在1个 $D$ 维的目标搜索空间中，有 $N$ 个粒子组成1个群体，其中第 $i$ 个粒子表示为1个 $D$ 维向量 $X _ { i } \mathrm { = } \big ( x _ { i 1 } , \mathrm { x } _ { i 2 } , \mathrm { L } ~ , x _ { i D } \big ) \big ( i = 1 , 2 , \mathrm { L } ~ , N \big )$ ，每个粒子的位置就是1个潜在的解。将$X _ { i }$ 代入1个目标函数均可求出其FV，根据FV的大小衡量解的优劣性。第 $i$ 个粒子的移动速度也是 $D$ 维向量，记为 $V _ { i } { = } \big ( \nu _ { i 1 } { , } \nu _ { i 2 } { , } \mathrm { L } ~ , \nu _ { i D } \big ) \big ( i { = } 1 { , } 2 \mathrm { L } ~ , N \big )$ 。记第 $i$ 个粒子迄今为止搜索到的最优位置为$P _ { i } \mathrm { = } \big ( p _ { i 1 } , p _ { i 2 } , \mathrm { L } ~ , p _ { i D } \big ) \big ( i \mathrm { = } 1 , 2 , \mathrm { L } ~ , N \big )$ ，整个粒子群迄今为止搜索到的最优位置为 $P _ { _ g } { = } \left( p _ { _ { g 1 } } , p _ { _ { g 2 } } { , } \mathrm { L } { \ } , p _ { _ { g D } } \right)$ 。则可用下述公式对粒子的移动速度和位置进行更新:

$$
\nu _ { i j } \left( t + 1 \right) = \nu _ { i j } \left( t \right) w + r _ { 1 } c _ { 1 } \left[ p _ { i j } - x _ { i j } \left( t \right) \right] + r _ { 2 } c _ { 2 } \left[ g _ { i j } - x _ { i j } \left( t \right) \right]
$$

$$
x _ { i j } \left( t + 1 \right) = x _ { i j } \left( t \right) + \nu _ { i j } \left( t + 1 \right)
$$

式中， $r _ { \mathrm { { 1 } } }$ 和 $r _ { 2 }$ 是服从 $U { \big ( } 0 , 1 { \big ) }$ 分布的随机数； $c _ { 1 }$ 和 $c _ { 2 }$ 是随机因子，通常取 $\scriptstyle c _ { 1 } = c _ { 2 } = 2$ ; $w$ 是惯性因子。在每1维中，粒子均有1个最大限制速度 $V _ { \mathrm { m a x } }$ ，如果某1维的速度超过 $V _ { \mathrm { m a x } }$ ，那么这1维的速度就限定为 $V _ { \mathrm { m a x } }$ ，即 |ν|≤Vmax °

# 1.4.3混合粒子群优算法寻优原理

为提高优化算法在全局和局部意义下的搜索能力和收敛效率，以粒子群优算法流程为基础，引入改进单纯形搜索方法构成混合粒子群优算法(Hybrid Particle Swarm Optimization,HPSO)[29l]，即在每1次迭代中先用PSO算法对群体进行全局寻优，然后通过ISM算法对粒子群中部分精英粒子在其较优解领域内进行局部搜索，寻找更优解。

HPSO 算法的具体流程[29]为：对每次迭代中经过PSO优化后的所有 $P$ 个群体粒子( $P$ 为种群数)按适应度优劣值进行排序，选出适应度值最优的前 $s$ 个粒子构造1个包含 $s$ 个顶点的"单纯形"图形，从 $s$ 个顶点中选出最优响应的S-1个顶点 $X _ { 1 } , X _ { 2 } , \mathrm { L } \ X _ { s - 1 }$ ，并计算S-1个顶点形心 $X _ { c }$ ，由剩余顶点 $X _ { s }$ 通过形心 $X _ { c }$ “伸缩"映射生成 $X _ { s } ^ { \prime }$ 顶点，构造出新的"单纯形"图，按照上法多次重复产生S个新粒子。然后计算更新后每1 新粒子适应度值，从中选出最优响应的粒子替换原先群体中的最佳个体，并与原群体中剩余个体构成下1代新群体。接着比较新个体适应度值与其自身及群体pbest适应度值，确定最佳pbest位置。若粒子群进化计算达到所允许的最大代数 $T$ 或评价值小于给定精度 $\boldsymbol { \varepsilon }$ ，则输出最优结果gbest，迭代结束。一般而言，个体数 $s$ 值不宜过大， $S / P$ 值在 $10 \% { \sim } 2 0 \%$ 之间为宜。

# 1.5 Laio模型转换与参数优化

非线性模型参数优化问题是在模型结构(表达式为 $y = f { \bigl ( } x , \theta { \bigr ) } + e$ ， $e \sim N \left( 0 , \delta ^ { 2 } \right)$ ，其中， $x$ 为系统输入,$y$ 为系统输出， $\theta$ 为模型待优化参数集， $\mathbf { \Psi } _ { e }$ 是均值为0、方差为 $\delta ^ { 2 }$ 的白噪声。)已确定的情况下，根据已知的输入输出数据 ${ \big ( } x _ { i } , y _ { i } { \big ) } { \big ( } i = 1 , 2 , \mathrm { L } \ , n { \big ) }$ ，求出存在于非线性模型中的参数集 $\theta$ ，即求解偏差平方和$\textstyle F { \bigl ( } \theta { \bigr ) } = \sum _ { i = 1 } ^ { n } { \bigl ( } y _ { i } - f \left( x _ { i } , \theta \right) { \bigr ) } ^ { 2 }$ 为最小的 $\theta$ 值[30]。为不失一般性，对垄沟集雨系统Laio 模型进行参数优化时，根据已知数据 $\big ( s _ { i } , p ( \mathrm { s } ) _ { i } \big ) \big ( i = 1 , 2 , \mathrm { L } \ m \big )$ ，对目标函数 $\begin{array} { r } { F \big ( \theta \big ) = \operatorname* { m i n } \sum _ { i = 1 } ^ { n } \Big ( p \big ( s \big ) _ { i } - f \big ( s _ { i } , \theta \big ) \Big ) ^ { 2 } } \end{array}$ 进行求解，所得参数集 $\theta$ 即为模型参数优化值。 $F ( \theta )$ 越小，表明优化参数集越准确；反之，表明越不可靠。目标函数 $F ( \theta )$ 的优化求解需综合考虑模型参数的限制条件，故传统算法很难对其进行求解。由于众多现代非传统算法可用于非线性、不可微和多峰值的复杂函数优化问题的求解[31l。故本文选择局部搜索算法ISM、全局搜索算法 PSO 和混合搜索算法 HPSO 分别对 Laio 模型偏差平方和 $F ( \theta )$ 的最小值进行优化求解，并分别对ISM、PSO 和HPSO 算法收敛效率及优化参数有效性进行分析和验证。

# 1.6 模型的验证与评价方法

通过比较研究区不同处理实测土壤水分概率密度函数曲线与ISM、PSO 和HPSO算法优化参数值模拟曲线的特征，评价以上3 种算法对 Laio 模型参数优化的有效性。验证评价指标选择CM(ConsistencyMeasure)指数[32]，其表示两目标曲线的一致性程度，计算方法如下：

$$
C M = { \frac { 2 A _ { 1 \cap 2 } } { A _ { 1 } + A _ { 2 } } }
$$

式中， $A _ { 1 }$ 表示目标曲线1下方的面积， $A _ { 2 }$ 表示目标曲线2下方的面积， $A _ { 1 \cap 2 }$ 表示目标曲线1和目标曲线2下方的公共面积(见图2(a))。显然，目标曲线1与目标曲线2一致性越好， $A _ { 1 \cap 2 }$ 越大,CM指数越大；反之，一致性越差， $ { A _ { 1 \cap 2 } }$ 越小,CM指数越小。CM指数的变化范围为[0,1]，当 $\mathbf { C M } = 1$ 时，表明目标曲线1和目标曲线2一致性最佳；当 $\mathrm { C M } { = } 0$ 时，表明目标曲线1和目标曲线2之间不存在一致性(见如 2(b))。

![](images/e24c503b5f2ca1c6a0c6fc8093340918e7a922d9f5f82331d1bbf92fadb6ca51.jpg)  
图2一致性测度(CM)指数定义示意图  
Fig.2Schematic diagram showing definition of consistency measure(CM)

# 2 结果与分析

# 2.1Laio模型参数敏感性分析

![](images/32d2c89569997260afc96b90bdaa65d546418fbbe40ce211201d82697b970ffe.jpg)  
图3垄沟集雨系统Laio模型各参数敏感性分析结果  
Fig.3The sensitivity degree of parameters in Laio model in ridge-furrow rainwater harvesting system

采用表1中不同处理待优化参数值，借助 MATLABR2010a 软件，计算得出不同土壤含水率下$( s _ { h } < s < s _ { w }$ 、 $s _ { { \scriptscriptstyle w } } < s < s ^ { { \scriptscriptstyle * } }$ 、 $s ^ { * } < s < s _ { f c }$ 和 $s _ { f c } < s < 1$ )Laio 模型各参数的敏感度(图3)。从图3可以看出，在不同土壤含水率和不同处理条件下，模型参数敏感性表现不同。总体而言， $\beta \setminus \ K _ { s }$ 、 $s _ { h }$ 和 $s _ { f c }$ 对模型的输出影响甚微； $\Delta$ 和 $E _ { \mathrm { m a x } }$ 对模型的输出影响较小； $\alpha$ 和 $s _ { { } _ { w } }$ 对模型的输出影响较显著，为影响垄沟集雨系统土壤水分动态随机模拟的最重要因子；土壤含水率为 $s _ { h } < s < s _ { w }$ 时， $n \setminus Z _ { r }$ 、 $E _ { \scriptscriptstyle w }$ 和 $\lambda$ 对模型的输出影响较显著， $s ^ { * }$ 对模型的输出影响甚微，而在其他土壤含水率条件下，其均对模型的输出影响较小；各处理对应模型参数敏感度随土壤含水率的变化趋势基本一致。在相同土壤含水率条件下，处理SR 对应模型敏感性参数的敏感度显著大于处理CMR和BMR，处理CMR与BMR之间差异不显著。在相同处理条件下，低土壤含水率对应模型敏感性参数的敏感度显著大于高含水率条件下的敏感度。同时，除参数 $s ^ { * }$ 、 $\alpha$ 和 $\lambda$ 对应敏感度为正值外，其余各模型敏感性参数的敏感度均为负值，且均为土壤特征参数。

![](images/c7826ec487895ed439bdd97e864df5f55fc58dec6df63a9e1f585a44256ca809.jpg)  
图4基于SOM神经网络聚类法的Laio模型参数不同分类结果

Fig.4Different classification results of parameters inLaio model based on SOM neural network clustering methoo

采用 SOM神经网络聚类法对垄沟集雨系统Laio 模型各参数敏感性进行分类(图4)。从图4可以看出，将13个模型参数分为3类时，不同土壤含水率条件下的分类结果存在相同之处，即 $\beta \setminus K _ { s }$ 和 $s _ { f c }$ 均为弱敏感参数； $s _ { h }$ 和 $\lambda$ 均为中等敏感参数； $\alpha$ 和 $s _ { { } _ { w } }$ 均为强敏感参数。同时，不同土壤含水率条件下 $s _ { h }$ $\mathbf { \Phi } _ { h } \setminus \Delta \setminus E _ { \operatorname* { m a x } } .$ （204号$s ^ { * }$ 和 $s _ { { } _ { w } }$ 的分类结果存在差异。通过综合考虑不同土壤含水率条件下模型各参数敏感性分类结果，将垄沟集雨系统模型参数敏感性可分为3类：第一类为弱敏感参数，包括参数 $\beta$ 、 $K _ { s }$ 、 $s _ { f c }$ 和 $s _ { h }$ ；第二类为中等敏感参数，包括参数 $\Delta$ 、 $E _ { \mathrm { m a x } }$ 、n、Z,、 $E _ { \scriptscriptstyle w }$ 、 $\lambda$ 和 $s ^ { * }$ ；第三类为强敏感参数，包括参数 $\alpha$ 和 $s _ { { } _ { w } }$ 。这与姚淑霞等[7的分类结果基本一致， $\alpha$ 和 $s _ { { } _ { w } }$ 均为强敏感性参数， $K _ { s }$ 为弱敏感性参数；而与任庆福[17]的分类结果不太一致， $s _ { { } _ { w } }$ 在任庆福分类中为弱敏感性参数，但在本文分类中为强敏感性参数，造成这种差异的原因可能是其未对不同土壤含水率条件下的参数敏感性进行综合考虑。同时，不同研究区土壤质地、植被和气候特征之间存在的差异，也可能是造成模型参数敏感不一致的原因，故应根据研究区的具体环境条件对模型参数敏感性做相应分析。

![](images/68a059a166a4f0bb0550ec0a80a560a71f93e08a78be6f5e3f6dafd6088c54fe.jpg)  
图5参数 $\alpha$ 和 $\boldsymbol { s } _ { \scriptscriptstyle w }$ 对垄沟集雨系统土壤水分概率密度函数 $p ( { \mathrm { s } } )$ 的影响Fig.5The influence of parameter $\alpha$ and parameter $s _ { { } _ { w } }$ on $p ( \mathrm { s } )$ in ridge-furrow rainwater harvesting system

由于强敏感性参数 $\alpha$ 和 $s _ { { } _ { w } }$ 对模型模拟结果的影响显著高于其他参数，故需要进一步探讨 $\alpha$ 和 $s _ { { } _ { w } }$ 对模型模拟结果的影响。以处理CMR为例，当其他参数不变时，讨论 $\alpha$ 和 $s _ { { } _ { w } }$ 各自的单独变化对垄沟集雨系统土壤水分概率密度函数 $p ( { \mathrm { s } } )$ 的影响(图5)。由图5 可知，参数 $\alpha$ 在 $0 . 0 2 6 { \sim } 0 . 1 3 5 \mathrm { c m } { \cdot } \mathrm { d } ^ { - 1 }$ 范围内变化时， $\alpha$ 的增大引起 $p ( { \mathrm { s } } )$ 的非线性减少；参数 $\alpha$ 在 $0 . 1 3 5 { \sim } 1 \ \mathrm { c m { \cdot } d ^ { - 1 } }$ 范围内变化时， $\alpha$ 的增大引起 $p ( { \mathrm { s } } )$ 先非线性增加后非线性减小，且 $\alpha$ 为 $0 . 1 9 2 \ \mathrm { c m } { \cdot } \mathrm { d } ^ { - 1 }$ 时， $p ( { \mathrm { s } } )$ 达到最大值。同时，土壤含水率在 $0 . 0 2 6 { \sim } 0 . 2 5 ~ \mathrm { c m ^ { 3 } } { \cdot } \mathrm { c m ^ { - 3 } }$ 范围内时，参数 $\alpha$ 的变化能引起 $p ( { \mathrm { s } } )$ 显著波动，说明土壤水分概率密度函数 $p ( { \mathrm { s } } )$ 对 $\alpha$ 的敏感性在低含水率下更明显。表明在干旱半干旱区，垄沟覆膜集雨系统可将无效降水(小于 $5 \mathrm { m m } ,$ 转化为有效水分贮存于土壤，显著提高土壤含水率[1,33]。参数 $s _ { { } _ { w } }$ 的变化范围为 $0 . 0 2 6 \mathrm { \sim } 0 . 5 6$ ，在土壤含水率区间内， $p ( { \mathrm { s } } )$ 呈非线性增加趋势，且土壤含水率越大， $s _ { { } _ { w } }$ 变化引起的 $p ( { \mathrm { s } } )$ 变化越大，说明土壤水分概率密度函数 $p ( { \mathrm { s } } )$ 对 $s _ { { } _ { w } }$ 的敏感性在高含水率下更明显。表明垄沟覆膜集雨系统能在高效雨水收集的基础上，使作物摆脱干旱胁迫，显著提高土壤水分利用效率[1,34]。

# 2.2基于ISM、PSO和HPSO算法的模型参数优化

根据参数敏感性分析结果及参数优化原则，分别利用 ISM、PSO 和 HPSO 算法对Laio 模型中的 $n$ 、β、K、sℎ、sw、s\*、sfe、E、△、Emax共11个参数进行优化。各待优参数初值及取值范围见表1。在参数优化过程中，各算法参数设置如下：种群数均设为 80；最大迭代次数为1000；适应度函数 $f$ 采用偏差平方和形式(见1.5中);ISM算法扩张系数 $\gamma = 2$ ，压缩系数 $\beta { = } 0 . 5$ ; PSO 和HPSO 算法速度更新式中惯性权系数 $w$ 值线性递减，其中 $w _ { \mathrm { m a x } } = 0 . 9$ ， $w _ { \mathrm { m i n } } = 0 . 4$ ；学习因子取为 $c _ { 1 } = c _ { 2 } = 0 . 2$ ；HPSO 算法中用于改进单纯形局部搜索的优秀个体数 $S = 6$ ，扩张系数 $\gamma = 2$ ，压缩系数 $\beta { = } 0 . 5$ ；整体算法每进化一代，用改进单纯形法对选中的优秀个体搜索100步；参数 $Z _ { { r } }$ 、 $\alpha$ 和 $\lambda$ 均根据试验实测值确定。

为确保算法的优化精度和有效性，在算法运行的过程中符合下列3个终止准则之一时停止计算[35]。准则1：两次迭代的最优目标函数值对应的参数距离小于给定精度 $\varepsilon _ { 1 } \leq 1 0 ^ { - 5 }$ ；准则2：两次迭代的目标函数值之差小于给定精度 $\varepsilon _ { 2 } \leq 1 0 ^ { - 5 }$ ；准则3：循环的最大次数已达到。同时，为尽可能消除算法随机性对各算法比较的影响，每个优化算法均随机独立运行10次后取各参数平均最优解和计算效率。算法运行结果和优化参数验证见表2及图6所示。

表2基于ISM、PSO和HPSO 算法的垄沟集雨系统Laio模型参数优化结果  
Table 2Optimization results of parameters in Laio model in RFRHS based on ISM、PSO and HPSO algorithm   

<html><body><table><tr><td rowspan="2">模型参数 Parameters</td><td rowspan="2">单位 Units</td><td colspan="3">ISM算法参数优化值 Values after optimization using ISM</td><td colspan="3">PSO 算法参数优化值 Values after optimization using PSO</td><td colspan="3">HPSO 算法参数优化值 Values after optimization using HPSO</td></tr><tr><td>SR</td><td>CMR</td><td>BMR</td><td>SR</td><td>CMR</td><td>BMR</td><td>SR</td><td>CMR</td><td>BMR</td></tr><tr><td>n</td><td>m³m-3</td><td>0.5696</td><td>0.5814</td><td>0.5811</td><td>0.5637</td><td>0.5863</td><td>0.5809</td><td>0.5634</td><td>0.5866</td><td>0.5804</td></tr><tr><td>β</td><td>/</td><td>14.8003</td><td>14.8011</td><td>14.8008</td><td>14.2084</td><td>13.5025</td><td>14.0283</td><td>14.2012</td><td>13.5481</td><td>14.0315</td></tr><tr><td>Zr</td><td>cm</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td><td>140</td></tr><tr><td>Ks</td><td>cm·d-1</td><td>19.5004</td><td>19.5012</td><td>19.5007</td><td>15.5426</td><td>17.3944</td><td>17.5720</td><td>15.5407</td><td>17.3452</td><td>17.5699</td></tr><tr><td>Sh</td><td>mm-3</td><td>0.0258</td><td>0.0263</td><td>0.0263</td><td>0.0221</td><td>0.0288</td><td>0.0243</td><td>0.0261</td><td>0.0279</td><td>0.0238</td></tr><tr><td>Sw</td><td>mm-3</td><td>0.2495</td><td>0.2490</td><td>0.2494</td><td>0.1801</td><td>0.2066</td><td>0.2017</td><td>0.1302</td><td>0.1866</td><td>0.1817</td></tr><tr><td></td><td>mm-3</td><td>0.5803</td><td>0.5703</td><td>0.5698</td><td>0.6713</td><td>0.5611</td><td>0.5325</td><td>0.6910</td><td>0.5712</td><td>0.5341</td></tr><tr><td>Sfc</td><td>mm-3</td><td>0.7210</td><td>0.7210</td><td>0.7200</td><td>0.8206</td><td>0.7439</td><td>0.7454</td><td>0.8803</td><td>0.7468</td><td>0.7435</td></tr><tr><td>Ew</td><td>cm</td><td>0.0090</td><td>0.0063</td><td>0.0100</td><td>0.0152</td><td>0.0178</td><td>0.0182</td><td>0.0132</td><td>0.0167</td><td>0.0181</td></tr><tr><td>4</td><td>cm</td><td>0.1280</td><td>0.1293</td><td>0.1310</td><td>0.1438</td><td>0.1119</td><td>0.1171</td><td>0.1386</td><td>0.1123</td><td>0.1164</td></tr><tr><td>Emax</td><td>cm</td><td>0.6111</td><td>0.6712</td><td>0.5598</td><td>0.6115</td><td>0.6009</td><td>0.5316</td><td>0.6619</td><td>0.6002</td><td>0.5311</td></tr><tr><td>α</td><td>cm·d-1</td><td>0.5949</td><td>0.8166</td><td>0.7673</td><td>0.5949</td><td>0.8166</td><td>0.7673</td><td>0.5949</td><td>0.8166</td><td>0.7673</td></tr><tr><td></td><td>d-1</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td><td>0.3300</td></tr></table></body></html>

![](images/bb00ac2206c33cebc5307d1b5ac7d4227a19f93ff99d9b058dfc57389353a756.jpg)  
SMC 表示土壤含水量;NCF表示正态曲线拟合; $\mathrm { \Delta S _ { P S O } }$ 表示PSO优化参数模拟曲线; $\mathrm { S } _ { \mathrm { I S M } }$ 表示ISM优化参数模拟曲线; $\mathrm { \Delta S _ { H P S O } }$ 表示HPSO 优化参数模拟曲。epsueotepaitsarepresents ISM optimization parameters simulated curves; $ { \mathrm { S } } _ { \mathrm { H P S O } }$ represents HPSO optimization parameters simulated curves.  
图6基于ISM、PSO 和 HPSO 算法的Laio 模型参数优化效率和优化参数有效性验证结果 Fig.6Optimization eficiencyand validityverificationofparameters inLaio model in RFRHS basedon ISM、PSOand HPSO algorithm

从3 种算法(ISM、PSO 和HPSO)对 Laio 模型参数优化结果(表2)和优化效率(图6)可以看出,ISM算法优化参数的有效性明显不及另外两种算法，其对模型参数初始值依赖性较强，如果不事先用具有较强全局寻优能力的算法获取一组较优初始值，其优化结果将易陷入局部最优。PSO 算法具有较强的全局寻优能力，优化参数的有效性较强，但其在算法迭代后期收敛速度相对较慢，存在有早熟、局部收敛的缺陷。HPSO算法优化参数的有效性明显优于ISM算法和PSO 算法的优化解，其不但具有较强的全局搜索能力，而且具有较快的收敛速度，能较显著地克服ISM算法和PSO算法相互存在的缺陷。这与陈俊风等[29]对 HPSO 算法的仿真实验结论相一致，说明其有利于增强全局和局部意义下优化结果的可靠性和算法的优化性能，是求解优化问题的一种有效的算法。

# 2.3模型参数有效性验证与评价

采用试验区2012一2013年田间垄沟集雨系统各处理(SR、CMR 和BMR)降雨、径流、土壤含水率等实测数据资料，基于3种算法(ISM、PSO 和 HPSO)对 Laio 模型参数优化值，比较模型模拟与实测的土壤水分概率密度函数在曲线形状(峰值、峰值出现的位置、 $90 \%$ 置信区间)和CM指数之间的匹配程度，评价3种算法对Laio模型参数优化的有效性，选择较优模型参数优化值及参数优选算法类型。图6和表3为3种算法的垄沟集雨系统Laio模型优化参数有效性验证与评价结果。

表3基于ISM、PSO和HPSO算法的垄沟集雨系统Laio模型参数优化的性能比较   
Table 3Performance comparison of parameteroptimization in Laio model inRFRHS basedon ISM、PSOand HPSOalgorithn   

<html><body><table><tr><td rowspan="2">算法 Algorithm</td><td colspan="4">SR的p(s)曲线检验指标</td><td colspan="4">CMR的p(s)曲线检验指标</td><td colspan="4">BMR的p(s)曲线检验指标</td></tr><tr><td></td><td>Consistency test indicators</td><td></td><td></td><td></td><td>Consistency test indicators</td><td></td><td></td><td></td><td>Consistency test indicators</td><td></td><td></td></tr><tr><td></td><td>CPV</td><td>PP</td><td>CI95%</td><td>CM</td><td>CPV</td><td>PP</td><td>CI95%</td><td>CM</td><td>CPV</td><td>PP</td><td>CI95%</td><td>CM</td></tr><tr><td>ISM</td><td>0.0194</td><td>0.0333</td><td>-0.1493</td><td>0.519</td><td>0.0069</td><td>-0.0286</td><td>-0.0434</td><td>0.830</td><td>0.0111</td><td>0.0588</td><td>-0.0437</td><td>0.685</td></tr><tr><td>PSO</td><td>0.0126</td><td>0.0333</td><td>-0.0874</td><td>0.723</td><td>0.0068</td><td>-0.0286</td><td>-0.0490</td><td>0.957</td><td>0.0093</td><td>0.0001</td><td>-0.0210</td><td>0.864</td></tr><tr><td>HPSO</td><td>0.0001</td><td>0.0001</td><td>-0.0629</td><td>0.805</td><td>0.0061</td><td>-0.0286</td><td>-0.0241</td><td>0.994</td><td>-0.0024</td><td>0.0001</td><td>-0.0193</td><td>0.903</td></tr></table></body></html>

CPV:峰值；PP:峰值位置; $C I 9 5 \%$ $9 5 \%$ 置信区间；CM:一致性指数。CPV:the curve peak value;PP:the position of the peak; $C I 9 5 \%$ ：the confidence interval of $9 5 \%$ ; CM: the consistency measure.

从图6和表3可以看出,3种算法优化模型参数值均能比较准确地描绘出曲线的形状，捕捉到峰值的位置，描述出土壤水分概率密度函数的主要特征，且CPV、PP和 $C I 9 5 \%$ 实测值与模拟值相对误差均小于$10 \%$ ，CM指数均大于0.5，说明3种算法优化参数值对垄沟集雨系统土壤水分概率密度函数模拟效果较好。同时，HPSO 算法优化参数的模拟效果(CM指数均值为0.901)优于PSO 算法(CM指数均值为0.848),PSO 算法优于ISM算法(CM指数均值为0.678)，且HPSO算法优化参数的收敛速度(进化代数均值为285)均快于PSO算法(进化代数均值为503)，说明HPSO算法优化模型参数值可较显著提高垄沟集雨系统土壤水分概率密度模拟精度和效率，故 HPSO 算法可作为垄沟集雨系统土壤水分动态随机模型参数优选的较优待选方案。但是，相关研究表明[36]，全局算法与局部算法相混合得到的混合优化算法，尽管可以提高局部收敛速度和性能，但也加剧了陷入局部极小的可能。因此，构建能显著提高局部搜索能力，且能高概率搜索全局最优解的混合优化算法，有待进一步深入的研究。

# 3结论

本文采用多因素敏感性分析法，对半干旱区垄沟集雨系统Laio土壤水分动态随机模型参数的敏感性进行了分析和分类。同时，基于3种算法(ISM、PSO 和HPSO)，对垄沟集雨系统 Laio 模型的13个参数进行了优化和优选，并利用实测数据资料对3种算法优化参数的有效性进行了验证和评价。得到的主要结论如下:

1)通过综合考虑不同土壤含水率条件下模型各参数的敏感性，发现垄沟集雨系统Laio模型涉及的13个参数中，平均年降水量 $\alpha$ 和调萎系数 $s _ { { } _ { w } }$ 对模型输出影响最显著，为强敏感性参数;

2)强敏感性参数 $\alpha$ 和 $s _ { { } _ { w } }$ 在一定含水率范围内变化时，土壤水分概率密度函数 $p ( { \mathrm { s } } )$ 对参数 $\alpha$ 的敏感性在低含水率下更明显，而对参数 $s _ { { } _ { w } }$ 的敏感性在高含水率下更明显;

3)三种算法的优化参数值均能较好模拟垄沟集雨系统土壤水分概率密度函数，其中各处理的 CPV、PP和 $C I 9 5 \%$ 实测值与模拟值相对误差均小于 $10 \%$ ,CM指数均大于0.5;

4)HPSO 算法优化参数的模拟效果和收敛速度均显著优于PSO 算法和 ISM 算法，且能较显著克服ISM算法和PSO算法存在的缺陷，故HPSO 算法可作为垄沟集雨系统土壤水分动态随机模型参数优选的较优待选方案。

# 参考文献References

[1]莫非，周宏，王建永，等．田间微集雨技术研究及应用[J]．农业工程学报,2013,29(8):1-17. MoF,Zhou H,Wang JY,etal.Developmentandaplicationof micro-fieldrain-harvestingtechnologies[J].Transactionsof the Chinese Society of Agricultural Engineering,2O13,29(8):1-17.   
[2]ZhouLM,ZhangF,LiuCA.Improved yieldbyharvesting water withridges andsubgrooves using buriedandsurface plastic mulchs in a semiarid area of China[J]. Soil and Tillage Research,2O15,150(2015): 21-29.   
[3]DuYJ,LiZZ,LiWL.Effectofdiferent watersupplyregimes ongrowthand size hierarchyin spring wheat populations under mulched with clear plastic film[J]. Agriculture Water Management, 2OO6,79(3): 265-279.   
[4]Jia Y,LiFM, Wang XL.Soil qualityresponsestoalfalfa watered witha field micro-catchment technique intheLoess Plateau of China[J].Field Crops Research,2006,95(1): 64-74.   
[5]李小雁．干旱地区土壤-植被-水文耦合、响应与适应机制[J]．中国科学：地球科学,2011,12(41):1721-1730. Li X Y.Mechanismof coupling,response and adaptation between soil，vegetationand hydrology in arid and semiarid regions[J]. Scientia Sinica Terrae,2011,12(41): 1721-1730.   
[6]PorporatoA,Feng X,Manzoni S,etal.Ecohydrological modeling inagroecosystems:Examplesandchalenges[J].Water Resources Research,2015,51(7): 5081-5099.   
[7]姚淑霞，张铜会，赵传成．科尔沁沙地土壤水分动态分析及其概率密度函数模拟[J]．水科学进展,2013,24(1):62-72. Yao S X,Zhang TH,ZhaoCC.Analysis of soil moisture dynamics andits probability density function simulation in Horqin Sand Land[J]. Advances in Water Science,2013,24(1): 62-72.   
[8]EaglesonP.Cimate,soil,ndvegetation:1Introductiontowater-balancedynamics[J].Water ResourcesResearch98, 14(5): 705-712.   
[9]Milly PCD.Ananalytic solution of the stochastic storage problem aplicable to soil water[J]. Water Resource Research, 1993,29(11): 3755-3758.   
[10]Rodriguez-IurbeIPorporatoA,idolfiL,etal.Probabilisticmodelingofwaterbalanceatapoint:theoleofliateil and vegetation[J]. Proceedings of the Royal of Society A,1999,455(1999): 3789-3805.   
[]LaioF,orporatoA,dolfi,etal.Plants iaterotroledostes: Activeoleinrolgicproesssdse to water stres: II: Probabilistic soil moisture dynamics[J].Advances in Water Resources,2O01,24(7): 707-723.   
[12]PorporatoA,DalyE,Rodriguez-IturbeI.Soil waterbalanceandecosystemresponse toclimatechange[J].TheAmerican Naturalist, 2004,164 (5): 625-632.   
[13]PanXY,oterNJ,XiaJ,etal.Hopscaleprobabilisticharacterzationofsoilmoisturedamicsndaveragewater balance[J]. Hydrological Processes,2013,27(10): 1464-1474.   
[14]Ben-AsherJ，WarickAW.Eectofvariations insoil propertiesandprecipitationonmicrocatchment waterbalane[J]. Agricultural Water Management,1987,3(12): 177-194.   
[15]Li X Y,ShiPJ,SunYL,etal.Influenceofvarious in siturainwater harvesting methods onsoil moisture and growthof Tamarix ramosissimain the semiarid loessregionofChina[J].ForestEcologyand Management,2006,233(1):143-148.   
[16] Wang Q,Ren X,Song XYetal.Teoptimumidge-furrowratioandsuitableridge-covering material inainwaterhavesting for oats production in semiarid regions of China[J].Field Crops Research,2015,172: 106-118.   
[17]任庆福．气候变化下典型农田土壤水分随机模拟及应用[D].北京：北京林业大学,2016:83-94. Ren QF.Stochastic simulation for the typical farmland soil moistureunder climate changeand itsapplicationto the shijin irrigated district in Hebei province[D]. Beijing: Beijing Forestry University,2016: 83-94.   
[18]MillerGR,BaldocchiDD,LawBE,etal.Ananalysisof soil moisture dynamics using multi-yeardata fromanetworkof micrometeorological observation sites[J]. Advances in Water Resources,2007,30(5): 1065-1081.   
[19]任祥，王琦，张恩和，等．覆盖材料和沟垄比对燕麦产量和水分利用效率的影响[J]．中国生态农业学报，2014，22(8): 945-954. Ren X,Wang Q,Zhang EH,etal.Effctsof mulching materials andfurrow-to-ridgeratiosonoat grain/hayyieldand water use eficiency under rainwater harvesting cultivation[J]. Chinese Journal ofEco-Agriculture,2014,22(8): 945-954.   
[20]尹鑫卫，李晓玲，康燕霞，等．基于 SCS-CN 模型的沟垄微型集雨系统径流预测[J].生态学杂志，2015，34(12)：3502- 3508. Yin X W,Li XL, Kang YX,et al.Predictionofrunoffin ridge-furrow rainwater harvesting system based on SCS-CN model[J]. Chinese Journal of Ecology,2015,34(12): 3502-3508   
[21] 潘兴瑶，夏军，张橹．土壤水分随机模型支持下的土壤水平衡研究进展[J]．资源科学,2008,30(3):460-467. Pan XY,XiaJ,ZhangL.AReview of Soil WaterBalance Studies basedon Stochastic SoilMoisture Model[J].Resources Science,2008,30(3): 460-467.   
[22]胡健，吕一河．土壤水分动态随机模型研究进展[J]．地理科学进展,2015,3(34):389-400. HuJ,LuYH.Research progressonstochasticsoilmoisture dyamicmodel[J].rogress inGeogaphy2015,34(3):389400.   
[23] Vanrolleghem，PeterA，Mannina,etal.Global sensitivityanalysis forurban waterqualitymodeling:Terminology, convergence and comparison of different methods[J]. Journal of Hydrology,2015,522(2015): 339-352.   
[24]李毅，邵明安，王文焰，等．土壤非饱和导水率模型中参数的敏感性分析[J]．水科学进展,2003,5(12):593-597. Li Y,ShaoMA,Wang WY,et al.Sensitive analyses of parameters inunsaturatedsoil hydraulicconductivitymodel[J]. Advances in Water Science,2003,05(12): 593-597.   
[25] NelderJA,Mead R.A simplex method for function minimum[J].Computer Journal,1965,7(4): 308-313.   
[26] 刘欢培，黄建华．改进单纯形法寻优的MATLAB 实现[J]．浙江工业大学学报,2003,31(4):23-27. Liu HP,Huang JH. Realizationof improved simplex method using MATLAB.Journal of Zhejiang universityof Technology, 2003,31(4): 23-27.   
[27] KennedyJ,EberhartR.Particle SwarOptimization[C//EEEInt.Conf.onNeural Networks,Piscataway:IEEService Center,1995:1942-1948.   
[28] 刘苏宁，甘泓，魏国孝．粒子群算法在新安江模型参数率定中的应用[J]．水利学报,2010,41(5):537-544. Liu SN,Gan H,Wei G X.ApplicationofPSOalgorithm tocalibrate the Xin’anjang HydrologicalModel[J].Journalof Hydraulic Engineering, 2010,41(5): 537-544.   
[29]陈俊风，任子武，范新南．一种基于改进单纯形法和粒子群算法的混合优化算法[C]//中国自动化学会控制理论专业委 员会．第25 届中国控制会议论文集．哈尔滨：哈尔滨工业大学出版社,2006:7-11. Chen JF,Ren ZW,Fan X N.A hybridoptimizedalgorithm bastedon improved simplex methodand particle swarm optimization[C]//Technical commitee on Control Theory,Chinese AssociationofAutomation.Proceedings of the $2 5 ^ { \mathrm { t h } }$ Chinese Control Conference(Middle). Harbin: Harbin Institute of Technology Press,2O06:7-11.   
[30]陆克中，吴璞，王汝传．基于粒子群优化算法的非线性系统模型参数估计[J].计算机技术与发展,2008,18(6):57-59. Lu K Z,Wu P,Wang R C.A method of parameter estimation in a nonlinear system model based on particle swarm optimization[J]. Computer Techology and Development, 2008,18(6): 57-59.   
[31]吴春梅．现代智能优化算法的研究综述[J]．科技信息,2012,(8): $3 1 + 3 3$ ， Wu C M. A review of modern intelligent optimized algorithm[J].Techology Information,2012,(8): $3 1 + 3 3$   
[32] Zhu A X.Apersonalconstruct-based knowledge acqusitionproces fornatural resource mapping[J].Interational Jouralof Geographical Information Science,1999,13(2):119-141.   
[33]任小龙，贾志宽，丁瑞霞，等．我国旱区作物根域微集水种植技术研究进展及展望[J].干旱地区农业研究，2010,28(3): 83-89. Ren X L,Jia ZK,Ding R X,etal.Progress and prospect ofresearchonrot-zone water micro-collectingfarmingforcropin arid region of China[J]. Agricultural Research in the Arid Areas,2010,28(3): 83-89.   
[34]宋秉海．旱地地膜玉米"贫水富集"种植模式研究[J]．中国生态农业学报,2006,14(3):93-95. Song BH.Studyonplanting models ofrainwater harvesting technique of mulched maize in aridareas[J]. Chinese Journal of Eco-Agriculture,2006,14(3): 93-95.   
[35]江燕，刘昌明，胡铁松，等．新安江模型参数优选的改进粒子群算法[J]．水利学报,2007,38(10):1200-1206. JiangY,Liu CM,HuTS,etal.Improvedparticle swarmoptimization forparametercalibrationof Xin'anjiang model[J]. Journal of Hydraulic Engineering,2007,38(10):1200-1206.   
[36]俞欢军，许宁，张丽平，等．混合粒子群优化算法研究[J]．信息与控制,2005,34(4):500-504+509. Yu HJ,XuN,ZhangLP,etal.ResearchonHybridParticle SwarmOptimization[J].IformationandControl,25,4(4): $5 0 0 { - } 5 0 4 { + } 5 0 9$ ：