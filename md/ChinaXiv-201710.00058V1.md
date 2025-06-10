# 激光全散射法测量燃煤颗粒物浓度的实验研究

徐义书 刘小伟 崔江 陈栋 韩金克 徐明厚（华中科技大学能源与动力工程学院，煤燃烧国家重点实验室，武汉 430074)

摘要：本研究在激光全散射法颗粒物浓度检测系统上进行了不同性质、浓度燃煤飞灰颗粒的质量浓度测量实验。结果显示，联合全散射法颗粒物浓度检测系统和反演计算方法能良好的测算标准颗粒的质量浓度，误差 $\sim 7 \%$ 。对于燃煤飞灰颗粒，测算结果能反映气流中颗粒浓度的变化，然而测算值高于真实值约 $1 9 . 3 \% { \sim } 2 7 . 2 \%$ 。并且，对除尘器前级电场飞灰的测算偏差大于第四电场飞灰。进一步的理论计算结果表明，随颗粒粒径增大，散射光分布逐步向前向（即 $0 ^ { \circ }$ 方向）集中，导致光电探测器在收集透射光的同时收集部分前向散射光，使得反演计算值大于真实值。而前级电场飞灰中含有更多的大粒径、非球形颗粒且粒径分布范围更宽，偏离了反演算法的假定条件，导致对测算偏差增大。

关键词：全散射法；飞灰；颗粒物；质量浓度；光学测量中图分类号： TK16 文献标识码：A

# Mass concentration measurements of the coal-derived fly ash particles via light

# extinction method

XU Yi-Shu LIU Xiao-Wei CUI Jiang CHEN Dong HAN Jin-Ke XU Ming-Hou (State Key LaboratoryofCoal Combustion,School ofEnergyand power Engineerging,Huazhong UniversityofScience& Technology, Wuhan430074, China)

Abstract: Light extinction method appears as one of those techniques；while its performance and feasibility to detect the real coal-derived fly ash remains to be improved.In the present study, measurements of the real-fly-ash-loaded gases of various concentrations were carried out on a self-designed light-extinction-based particle concentration measuring system.Results showed that the inversion results based on the system and inversion method agreed well with the real value for the standard spherical $\mathrm { S i O } _ { 2 }$ powders with deviations of $\sim 7 \%$ .As for the real fly ash,the inversion results reflected the variation of the concentrations; while were $1 9 . 3 \% { \sim } 2 7 . 2 \%$ higher than the real values.Further theoretical calculations of the scattering light distribution of particles showed that for the larger particles, the scattering light concentrated to the forward direction $( \sim 0 ^ { \circ } )$ ，which resulted in larger detection results. Moreover, the higher contents of the fly ash of larger particle size, nonspherical shape and of broader size distribution led to the worse performance of the inversion method.

Key words: light extinction method; fly ash; particulate matter; mass concentration; optical measurement

# 0引言

随着燃煤电站颗粒物的排放浓度不断降低，实现颗粒物质量浓度准确检测的重要性和紧迫性日益凸显[1,2]。一方面，亟需通过在线检测确定颗粒物排放浓度是否达到排放要求；另一方面，只有及时、准确的检测获得颗粒物浓度才能实现除尘器的反馈调节，实现除尘器高效、经济运行。激光全散射测量方法是可以满足以上需求的一种在线测量方法，具有测量过程方便、对监测设备要求低、测量结果精确度高、响应速度快、重复性好等优点，受到广泛关注[1,3-6]

全散射法的测量原理是：当一束平行单色光照射到被测颗粒时，由于颗粒对光的散射和吸收作用，透射光的光强出现一定程度的衰减，依据透过光衰减的程度反演计算被测颗粒的浓度[5,7-9]。Kourti 等[10]对全散射法测量多分散颗粒的可行性进行了分析，并实现了 $2 { \cdot } 3 ~ { \mu } \mathrm { m }$ 以下颗粒的粒径测量。Paphael等[11]利用全散射法进行了高分子聚合过程中固体颗粒含量和平均粒径的在线测量。Wang 和Cai 等[12]对汽轮机中的雾滴进行了全散射光学测量。Marioth等[13]通过三波长全散射技术测量了超临界 $\mathrm { C O } _ { 2 }$ 气流中固体颗粒和水滴的粒径大小，指出该技术适用于超临界流体过程。Kocifaj等[14]分析了散射法对不规则形状颗粒的粒径反演计算。秦授轩和蔡小舒等[15,16]基于全散射原理，结合光脉动法和频谱分析法建立了光脉动谱法，实现了对锅炉入炉煤粉浓度和粒径分布的在线测量。Zhao 等[17依据散射积分法和全散射原理建立了用于在线测量烟气中炭黑（soot)浓度的方法，该方法不受炭黑颗粒粒径分布和平均粒径大小影响，在实验检验中获得了良好的结果。楼狄明等[18]和尹鹏飞等[19]实现了利用全散射理论对油雾滴的颗粒粒径分布测量。Chen 和 Lai 等[20]利用全散射法进行了大气颗粒物实时监测研究。崔江等[21]分析了颗粒的粒径分布特性对全散射法测量颗粒质量浓度的影响，结果显示，随着样品中无量纲尺寸因子（即 $\pi \mathrm { D } / \lambda$ ）大于30 的颗粒占比升高，浓度测算值与浓度真实值之间的偏差增大。针对烟尘和粉尘排放浓度和粒径的测量，王乃宁等[22,23]基于光散射理论提出了通过多角度散射光同步检测的理论和方法，并对其进行了初步验证。与其他检测粉尘对象相比，电站锅炉产生的粉煤灰具有形状多变、粒径范围广、成分复杂等特点，而目前利用全散射法进行燃煤飞灰颗粒物在线测量的相关研究报道十分有限[24-26]。因此，深入探究全散射法测量燃煤颗粒物的准确度高低、获得飞灰颗粒特殊的物理、化学性质对全散射法测量的影响规律具有十分重要的理论意义和应用价值。

本研究选用采取自真实燃煤电站锅炉的飞灰颗粒，在自行设计、搭建的激光全散射法颗粒物浓度检测系统上进行了燃煤飞灰颗粒质量浓度测量实验，依据全散射理论、入射光和透射光强度变化反演计算气流中颗粒物的浓度大小。同时，利用电子低压撞击式颗粒物采样仪进行在线浓度测量，与全散射法测算值进行比对，分析了全散射法测量燃煤颗粒物的准确度以及飞灰颗粒粒径大小、粒径分布特性和形状等性质对全散射法测量的影响。

# 1 实验

# 1.1 实验原料

实验包括两部分内容。第一部分选用单分散、球形 $\mathrm { S i O } _ { 2 }$ 标准颗粒进行实验，通过光学全散射法测量入射光和透射光的变化反演颗粒浓度，依据全散射理论反演计算颗粒浓度。同时，利用电子低压撞击式颗粒物采样仪（ELPI，见下文1.2）进行浓度实时测量。通过对比光散射法测算值与ELPI测量值，检验所用实验系统和实验方法的可靠性。 $\mathrm { S i O } _ { 2 }$ 标准颗粒样品的微观形貌和粒径分布特性曲线见图1。可以看到，该 $\mathrm { S i O } _ { 2 }$ 颗粒样品多呈规则球形，真密度为 $2 . 6 5 \ : \mathrm { g } / \mathrm { c m } ^ { 3 }$ ，且粒径分布集中在 $0 . 5 \mathrm { - } 1 . 5 ~ \mu \mathrm { m }$ 范围内，基本满足单分散、球形颗粒的要求。

![](images/dd8a5e16cf2863106f437dc2d2126d5ccc04cbf6a2effae0269c4066b73c362a.jpg)  
图1 $\mathrm { S i O } _ { 2 }$ 标准颗粒的微观形貌(a)和粒径分布(b)特征  
Fig.1 Micromorphology and size distribution of the standard $\mathrm { S i O } _ { 2 }$ particles

第二部分实验，实验原料为某 $1 0 0 0 \ \mathrm { M W }$ 煤粉电站机组产生的真实飞灰颗粒。通过该部分实验，研究利用光学全散射法测量飞灰颗粒浓度的准确性，并结合Mie散射法理论计算分析飞灰物化特性等因素对光学测量的分析。飞灰颗粒取自机组配备的静电除尘器（ESP）下部灰斗。飞灰样品按烟气流向由前至后依次编号为第一电场灰、第二电场灰、第三电场灰和第四电场灰。由第一电场飞灰变换至第四电场飞灰后，飞灰颗粒的索太尔平均直径D(3,2)由 $4 . 2 2 ~  { \mu \mathrm { ~ m ~ } }$ 依次减小为3. $3 5 \ \textrm { \textmu m } . 2 . 5 3$ μ m和1.85$\mu \textrm { m }$ 。各电场飞灰颗粒的微观形貌见图2，可以看到，各电场中的飞灰颗粒粒径并不是严格的单分散、球形特性颗粒。并且，相比于第四电场，在前级电场中的颗粒粒径更大、不规则颗粒更多。各飞灰样品的真密度通过真密度分析仪（AccuPyc1330）测试得到，第一、二、三和四电场灰真密度分别为2.36$\mathrm { g } / \mathrm { c m } ^ { 3 }$ 、 $2 . 2 8 ~ \mathrm { g / c m } ^ { 3 }$ 、 $2 . 4 4 ~ \mathrm { g / c m } ^ { 3 }$ 和 $2 . 5 8 \ \mathrm { g } / \mathrm { c m } ^ { 3 }$ 。

![](images/c30a4cfbf34e7087e1c0f685284c05befe91292c4a78704bef1cd14d1223bdfa.jpg)  
图2 电站锅炉粉煤灰样品的微观形貌特征 Fig.1 Micromorphology of the fly ash particles from coal-fired power station boiler

# 1.2实验系统与方法

如前所述，实验在自行设计、搭建的激光全散射法颗粒物浓度检测系统上进行[21]。如图3所示，该系统主要由光路系统和气路系统两部分组成。光路系统主要包括激光光源（LBX-633）、可变光阑、聚焦透镜和光电探测器（ET-2030）组成。激光光源用于产生稳定的、波长为 $6 3 2 . 5 { \pm } 0 . 5 \ \mathrm { n m }$ （红光）的单色激光。激光射入检测腔内照射负载不同浓度飞灰颗粒的烟气（空气)，利用光电探测器接收透射光（出射光)，并转化为透射光光强模拟信号，通过多通道AD采集系统输入计算机计算。通过入射光光强（ $\left( { { J } _ { 0 } } \right)$ ）和透射光光强 $( I )$ 计算获得激光透过气流过程中的消光程度-ln $( I / I _ { 0 } ) ^ { . }$ )。值得注意的是，检测腔的光程为 ${ \mathrm { ~ 1 ~ m ~ } }$ ，其光路入口和出口分别装有高透过率的光学镜片，并且在镜片上加装高压气流吹扫装置，用以防止灰颗粒在镜片上散落、沉积造成干扰光学测量。

![](images/b3ae947895991c831da005204a912669a297a49c187a895e8dd3117ebb1bbed1.jpg)  
图3激光全散射法颗粒物浓度检测系统示意图 Fig.3 Sketch of the light-extinction-based particle concentration measuring system

气路系统主要包括压缩空气、气溶胶发生器（TSI3400A）、检测腔（有机玻璃材质，长 $\times$ 宽 $\vdots \times$ 高$= 1 0 0 { \times } 3 0 { \times } 3 0 \ \mathrm { c m } )$ 、电子低压撞击式颗粒物采样仪（ELPI）和真空泵。气溶胶发生器用于产生负载不同浓度（ $2 0 { - } 3 0 0 \ \mathrm { m g / m } ^ { 3 } .$ ） $\mathrm { S i O } _ { 2 }$ 标准颗粒或不同ESP电场飞灰颗粒的气流。实验过程中，颗粒样品和压缩空气通过气溶胶发生器产生设定浓度的负载颗粒物的气流，随后通入检测腔进行光学检测。由检测腔排出的气流和颗粒物进入ELPI收集，检测获得数目浓度和质量浓度。ELPI可以根据进入气流中颗粒的空气动力学直径大小分13级收集，通过颗粒的荷电、放电过程计算获得颗粒的粒径分布和浓度信息[27,28]。本研究中，通过对比光学反演结果与ELPI测量结果分析全散射法测量的准确性。同一工况进行3次平行实验，取平均值用于结果分析。

# 1.3基于全散射理论的颗粒浓度反演计算

当光束通过均匀负载了颗粒的气体介质时，透射光强和入射光强之间存在以下关系（即Lambert-Beer 定律[1,3,21]，如式（1):

$$
I { = } I _ { 0 } { \in } \mathrm { x p } ( \tau L )
$$

式中， $I _ { 0 }$ 和 $I$ 分别为入射光和透射光光强， $L$ 为光束的光程， $\tau$ 为负载颗粒物气体介质的浊度。当假定负载颗粒为规则球形，且在介质中的分布满足不相干的单散射时，介质中颗粒系的总浊度可由单个颗粒的消光系数计算获得，如式（2)：

$$
\tau = \frac { \pi } { 4 } \int _ { a } ^ { b } N ( D ) D ^ { z } K _ { \mathrm { e x t } } { \mathrm d } D
$$

式中， $\mathbf { \Delta } _ { a }$ 和 $b$ 分别为颗粒系粒径的下限和上限，

$N \varpi D )$ 为多分散系颗粒的数目粒径分布函数， $K _ { \mathrm { e x t } }$ 为颗粒的消光系数。消光系数 $K _ { \mathrm { e x t } }$ 与入射光波长 $\lambda$ 、颗粒相对周围介质的相对复折射率 $\mathbf { \nabla } _ { m }$ ，颗粒粒径 $D$ 等有关。按照等效消光系数原则，定义多分散系的平均消光系数 $K _ { \mathrm { m } }$ 和索太尔平均直径 $D ( 3 , 2 )$ ，分别如式（3）和（4)。

$$
K _ { \pi } = \frac { \int K _ { \mathrm { e x t } } ( V ( D ) D ^ { 2 } \bar { \mathrm { e } } D L ) } { \int N ( D ) D ^ { 2 } \bar { \mathrm { e } } D }
$$

$$
D ( 3 , 2 ) = { \frac { \int M ( D ) D ^ { a } \mathrm { d } D } { \int M ( D ) D ^ { a } \mathrm { d } D } }
$$

结合式(1\~4)，可得颗粒的体积浓度 $C _ { \mathrm { v } }$ 和质量浓度 $C _ { \mathrm { m } }$ 的反演计算式，分别为式（5）和式（6)：

$$
\bar { C } _ { v } = \frac { \pi } { 6 } \int _ { a } ^ { b } \bar { N } ( D ) D ^ { 5 } \mathrm { d } D
$$

$$
C _ { m } = - \frac { 2 \rho D ( 3 , 2 ) } { 3 L K _ { m } } \ln \left( \frac { I } { I _ { 0 } } \right)
$$

在已知入射光波长λ、被测颗粒的折射率 $\mathbf { \nabla } _ { m }$ 和粒径 $D ( 3 , 2 )$ 后，平均消光系数 $K _ { \mathrm { m } }$ 可按Mie散射理论求解获得[16]。由上式（6）可知，在同时知道入射光波长、被测颗粒的折射率 $\mathbf { \nabla } _ { m }$ 和索太尔平均直径 $D ( 3 , 2 )$ 以及光程 $L$ 的情况下，通过测量消光程度便可反演获得介质中颗粒的体积浓度和质量浓度。

# 2 结果与讨论

# 2.1实验系统的可靠性校验

图4为负载 $\mathrm { S i O } _ { 2 }$ 标准颗粒模拟气流中的颗粒物质量浓度的测算值与真实值之间的关系曲线。由结果可以看到，根据实验中激光穿过气流过程中的消光程度和全散射理论计算得到的颗粒物质量浓度与浓度真实值之间呈良好的线性关系，拟合度高达0.9984。更重要的是，测算值约为真实值的1.07倍，即计算值与真实值误差仅为 ${ \sim } 7 \%$ 。该结果表明，当气流中颗粒为标准球形颗粒时，根据实测的消光程度和光散射理论反演计算得到的颗粒物浓度值（即计算值）能较好的反映颗粒的真实浓度。

![](images/20c782e2bd92240d5231a1c2f9af5c9cdabd9fcf8b45f999efce407344956c03.jpg)  
图4 $\mathrm { S i O } _ { 2 }$ 标准颗粒的质量浓度测算值与真实值之间的关系  
Fig.4Relationship between the inversion values and the real values of the mass concentrations of the standard $\mathrm { S i O } _ { 2 }$ particles   
图5消光程度 $. \mathrm { l n } ( I / I _ { 0 } )$ 与颗粒物浓度之间的关系 Fig.5 Relationship between the extinction factors $. \ln ( I / I _ { 0 } )$ and the mass concentrations of the fly ash particles

# 2.2飞灰颗粒的浓度

图5为激光穿过负载ESP电场灰颗粒的气流产生的消光程度与颗粒物浓度之间的关系曲线。结果显示，各个电场灰的消光程度与颗粒浓度呈正相关关系，第一电场灰变换至第四电场灰的，其拟合度分别为0.9962、0.9975、0.9978和0.9983。该结果表明，各实验工况条件下，不存在相干的复散射，满足全散射理论的前提条件。同时，可以看到入射激光在穿过不同电场灰后的出射光信号有较大差别，表明不同电场灰对全散射法测量有不同影响。

0.18第一电场灰 R²=0.99830.15 第二电场灰第三电场灰01 第四电场灰R²=0.9978R²=0.99750.060.03- R²=0.99620.000 50　100 150 200 250 300 350浓度（ $\cdot \mathsf { m g } / \mathsf { m } ^ { 3 } .$ ）

由图5中消光程度和全散射理论反演计算获得的颗粒浓度计算值，各工况条件下的浓度计算值与浓度真实值之间的关系曲线见图6。结果显示，各电场飞灰颗粒物浓度的计算值均能一定程度的反映气流中颗粒浓度的变化，然而各飞灰测算值均高于真实值。定义计算值与真实值之间的差值为测算偏差，在各电场飞灰实验中的测算偏差与飞灰颗粒粒径之间的关系见图7。

![](images/5b607f87cafcb01024a1ab08d67454bf933768e17c10afcd8241da6b147e06d1.jpg)  
图6飞灰颗粒质量浓度的反演计算值与真实值之间的关系  
Fig.6 Relationship between the inversion values and real values of the mass concentrations of tested fly ash

由第一电场飞灰变换至第四电场飞灰后，飞灰颗粒的索太尔平均直径 $D ( 3 , 2 )$ 由 $4 . 2 2 ~ \mu \mathrm { m }$ 依次减小为 $3 . 3 5 ~ { \mu \mathrm { m } } . 2 . 5 3 ~ { \mu \mathrm { m } }$ 和 $1 . 8 5 ~ { \mu \mathrm { m } }$ 。与此同时，测算偏差由 $2 7 . 2 \%$ 依次减小为 $23 . 6 \%$ 、 $23 . 2 \%$ 和 $1 9 . 3 \%$ 而测试结果的拟合度由0.9962依次升高为0.9975、0.9978和0.9983。即对于燃煤飞灰颗粒物，激光全散射法对小粒径颗粒物质量浓度测量具有更高的准确性。

![](images/cf9e1f77ee5cde5a28079132b0bdce8239f33d4bc6793ab62f621aa664881dc7.jpg)  
图7不同电场灰的测量偏差、拟合度与颗粒粒径之间的关系  
Fig.7Relationship between the deviations,R-squared and the particle size

# 2.3飞灰特性的影响分析

在检测过程中，入射光在照射到粉尘颗粒表面上时的同时会发生散射现象。而散射光在各个角度的分布与粉尘颗粒的粒径大小存在关联关系。不同粒径球形颗粒在空间中的散射强度分布可依据Mie散射理论计算得到[16]，针对粒径分别为 $0 . 0 2 1 ~ \mu \mathrm { m }$ 、$0 . 2 1 1 ~ { \mu \mathrm { m } }$ 、 $0 . 6 3 3 ~ { \mu \mathrm { m } }$ 和 $2 . 1 1 1 ~ \mu \mathrm { m }$ （无量纲尺寸因子$\pi D / \lambda$ 分别为0.1、1、3和10）的四种粒径颗粒的计算结果见图8。可以看到，随着颗粒的无量纲尺寸因子增大，散射光的强度越来越大，并且散射信号有向前（即 $0 ^ { \circ }$ 方向）集中的趋势。与之相比，对于小粒径颗粒（ ${ \mathrm { . } } D { = } 0 . 0 2 1 ~ { \mu \mathrm { m } } { \mathrm { . } }$ ，其后向（即 $1 8 0 ^ { \circ }$ 方向）散射与前向的信号强度基本均等。而进一步计算发现，当颗粒粒径进一步增大至 $6 . 3 3 4 \mu \mathrm { m }$ （无量纲尺寸因子为30）时，在前向附近 $\cdot \pm 5 ^ { \circ }$ 方向范围内分布的散射光强度已与透射光强度达到同一数量级。由于在全散射法浓度检测过程中，依据透射光强度和入射光强度的比值（即消光程度）来反演颗粒的浓度信息，当前向周围散射光强度过大时，会导致光电探测器在收集透射光的同时收集部分前向散射光，导致反演计算值大于真实值。

真实飞灰颗粒特性与全散射法计算过程中理想假设条件的差异也会引起测算偏差。一方面，颗粒粒径的大小会影响全散射法进行颗粒浓度的测算偏差。本研究中利用平均消光系数简化、替代颗粒系的消光系数，利用索太尔平均粒径简化、替代颗粒的粒径分布，而上述简化处理引入的测算偏差随粒径的增大而增大。在ESP前级电场中具有更多的大粒径颗粒物，因此由大粒径颗粒引起的测算偏差更为显著，从而导致图7中结果，即对第一电场灰测算偏差 $\mathrm { > }$ 第二电场灰测算偏差 $>$ 第三电场灰测算偏差 $>$ 第四电场灰测算偏差。另一方面，全散射反演计算过程中假定各颗粒为规则球形颗粒，而如图2所示，实验飞灰颗粒中存在大量不规律形状颗粒或颗粒团聚体，并且在第一电场中颗粒形状与规则球形的差异最为显著。由此推测，前级电场中存在的更多的不规则飞灰颗粒进一步导致了其表现出更大的测算偏差[29]。

![](images/d8cc4584aacd5176dc239ac43d5d5582bd55cf922fac46b6e3a0fbfd6e057f61.jpg)  
图 8不同粒径颗粒的散射光强空间分布  
Fig.8 Distribution of the scattering light around the particles of different size

# 3结论

本研究在激光全散射法颗粒物浓度检测系统上研究进行了不同性质、浓度燃煤飞灰颗粒的质量浓度测量实验。结果显示，联合自行设计、搭建的全散射法颗粒物浓度检测系统和反演计算方法能良好的测算标准颗粒（ $\mathrm { S i O } _ { 2 }$ ）的质量浓度，测算误差在$10 \%$ 以内。对于真实燃煤飞灰颗粒，全散射法测算结果值均能一定程度的反映气流中颗粒浓度的变化。然而，对所有四种飞灰的质量浓度测算值均高于真实值（高出 $1 9 . 3 \% { \sim } 2 7 . 2 \%$ )，且对除尘器前级电场飞灰的测算偏差大于第四电场飞灰。计算分析表明，随飞灰颗粒粒径增大，散射光分布发生向前（即$0 ^ { \circ }$ 方向）集中，导致光电探测器在收集透射光的同时收集部分前向散射光，导致反演计算值大于真实值。而前级电场飞灰颗粒含有更多的大粒径、非球形颗粒且粒径分布范围更大，偏离了反演算法假定条件，导致对其测算偏差增大。

# 参考文献

[1] Xu R. Light Scattering: A Review of Particle Characterization Applications [J]. Particuology, 2015,18: 11-21.   
[2]张宸瑜．烟尘浓度光散射测量技术研究 [D]. 东南大学：东南大学图书馆,2015. ZHANGChenyu.TheStudy of Dust ConcentrationMeasurement Using Light Scattering [D]. Southeast University: Southeast University Library, 2015.   
[3] Black D L， Mcquay M Q，Bonin M P. Laser-basedTechniquesfor Particle-size Measurement: a Review of Sizing Methods and Their Industrial Applications [J]. Progressin Energy and Combustion Science,1996,22(3): 267-306.   
[4] Zhao Y, Meng F,Qu B.Soot Concentration Measurement System of the Stationary Pollution SourceUsingtheScattering-Transmission Method [J]. AASRI Procedia, 2012, 3: 721-76.. [5] Jones A R. Light Scattering for Particle Characterization [J]. Progress in Energy and Combustion Science,1999, 25(1): 1-53. [6] Choi M Y, Hamins A,Mulholland G W, et al. Simultaneous Optical Measurement of Soot Volume Fraction and Temperature in Premixed Flames [J]. Combustion and Flame,1994,99(1): 174-186.   
[7] Ramachandran G, Leith D. Extraction of Aerosol-size Distributionsfrom Multispectral Light Extinction Data [J]. Aerosol Science and Technol0gy, 1992,17(4): 303-325. [8] Ma L, Hanson R K. Measurement of Aerosol Size DistributionFunctionsby Wavelengthmultiplexed Laser Extinction [J]. Applied Physics B, 2005, 81(4): 567-576. [9] Su M, Xu F, Cai X,et al. Optimization of Regularization Parameter of Inversion in Particle Sizing Using Light Extinction Method [J]. China Particuology,2007, 5(4): 295-299.   
[10] Kourti T. Polymer Latexes: Production by HomogeneousNucleation and Methodsfor Particle Size Determination [D]. 1989.   
[11] Raphael M,Rohani S. On-line Estimation of Solids Concentrations and Mean Particle Size Using a Turbidimetry Method [J]. Powder technology, 1996, 89(2): 157-163.   
[12] Wang N N, Wei J M, Cai X S, et al. Optical Measurement of Wet Steam in Turbines [J]. Journal of Engineering for Gas turbines and Power, 1998,120(4): 867-871.   
[13] Marioth E,Koenig B,Krause H,et al. Fast Particle Size and Droplet Size Measurements in Supercritical $\mathrm { C O } _ { 2 }$ [J].Industrial & Engineering Chemistry Research,2000, 39(12): 4853-4857.   
[14] Kocifaj M, Horvath H. Inversion of Extinction Data forIrregularlyShaped Particles[J]. AtmosphericEnvironment,2005,39(8): 1481-1495.   
[15]秦授轩,蔡小舒．在线测量煤粉粒度分布和浓 度的实验研究[J]．中国电机工程学报, QIN Shouxuan， CAI Xiaoshu. Experimental StudyonIn-lineMeasurementofSize Distribution and Concentration of Pulverized Coal [J]. Proceedings of the CSEE，2010(32): 30-34.   
[16] 蔡小舒,苏明旭,沈建琪．颗粒粒度测量技术及 应用 [M]．化学工业出版社,2010. CAI Xiaoshu, SU Mingxu, SHEN Jianqi. Particle Size measurement techniques and applications [M]. Chemical Industry Press, 2010.   
[17] Zhao Y, Fanwei M, Bin Q. Soot Concentration Measurement System of the Stationary Pollution SourceUsingtheScattering-Transmission Method [J]. AASRI Procedia, 2012, 3: 721-726.   
[18]楼狄明,任洪娟,谭丕强等．发动机燃用乳化柴 油的颗粒粒径分布特性 [J]．同济大学学报(自 然科学版),2012(07):1083-1088. LOU Diming, REN Hongjuan, TAN Piqiang, et al. Characteristics of Particle Size Distribution from a Diesel Engine with Emulsified Diesel [J]. Journal of Tongji University (Natural Science), 2012(07): 1083-1088.   
[19]尹鹏飞,陈军,杨荟楠等．长光程消光在线测量 油雾过滤器的过滤效率[J].动力工程学报, 2015(02): 141-146. YIN Pengfei, CHEN Jun, YANG Huinan, et al. On-line Filtration Efficiency Measurement of Oil Mist Filter Based on Long Optical Path Extinction [J]. Journal of Chinese Society of Power Engineering, 2015(02): 141-146.   
[20] Chen X, Lai S, Gao Y, et al. Reconstructed Light Extinction Coefficients of Fine Particulate Matter in Rural Guangzhou, Southern China [J]. Aerosol and Air Quality Research， 2016, 16(8): 1981-1990.   
[21]崔江,刘小伟,陈栋等．颗粒粒径分布对全散射 法测量颗粒质量浓度的影响 [J]．中国电机工 程学报,2016(16): 4415-4421. CUI Jiang，LIU Xiaowei, CHEN Dong，et al. EffectofParticleSizeDistributionon ConcentrationMeasurementwithLight Extinction Method [J]. Proceedings of the CSEE, 2016(16): 4415-4421.   
[22]王乃宁,虞先煌,竺晓程．烟尘粉尘向大气排放 的激光监测技术研究[J]．中国激光，2001(11): 1032-1036. WANGNaining， YUXianhuang， ZHU Xiaocheng. Study of the Laser Based Measuring Technique for Smoke and Dust in Emission [J]. Chinese Journal of Lasers,2001(11): 1032-1036.   
[23]王乃宁,尉士民．排放源颗粒物浓度及粒径连 续监测技术的研究[J]．工程热物理学报, 1999(02): 238-241. WANG Naining YU Shimin. A Study on Continuously Monitoring Mass Concentration and Size for Particulate Emissions [J]. Journal of Engineering Thermophysics,1999(02): 238-241.   
[24] Xu M， Yu D， Yao H， et al. Coal Combustion-generated Aerosols: Formation and Properties [J]. Proceedings of the Combustion Institute,2011, 33(1): 1681-1697.   
[25] Yao Q, Li S Q, Xu H W, et al. Reprint of: Studies on Formation and Control of Combustion Particulate Mater in China: A Review [J]. Energy, 2010, 35(11): 4480-4493.   
[26] Liu X, Xu Y, Fan B, et al. Field Measurements on the Emission and Removal of $\mathrm { P M } _ { 2 . 5 }$ from Coal-fired Power Stations: 2. Studies on Two 135 MW CFB Boilers Respectively Equipped with Electrostatic Precipitator and Hybrid Electrostatic Filter Precipitator [J]. Energy & Fuels,2016, 30(7): 5922-5929.   
[27]龙正伟,姚强,黄斌等．用 ELPI测量颗粒物的分 级荷电量[J]．工程热物理学报，2006(02): 354-356. LONG Zhengwei, YAO Qiang, HUANG Bin, et al.Measurement of the Particle's Charge Distribution Using the Electrical Low-pressure Impactor (ELPI) [J].Journal of Engineering Thermophysics, 2006(02): 354-356.   
[28] Zhao Z, Du Q, Zhao G, et al. Fine Particle EmissionfromanIndustrialCoal-Fired Circulating Fluidized-Bed Boiler Equipped with a Fabric Filter in China [J].Energy& Fuels, 2014. 28(7): 4769-4780.   
[29] Feng Q, Yang P, Kattawar G W, et al. Effects of Particle Nonsphericity and Radiation Polarization on Retrieving Dust Properties from MODIS

Observations [J]. Journal of Aerosol Science, 2009,40(9): 776-789.

# 附页

（来稿请附页注明投稿人及联系人的简介、通信地址、手机号码、电话、电子信箱，以便于联系。）

投稿人：徐义书  
简介：男，山东潍坊人，博士研究生。主要从事燃煤细颗粒物和超细颗粒物的生成、控制和在线检测研究。通信地址：湖北省武汉市洪山区珞喻路1037号华中科技大学煤燃烧国家重点实验室 501  
手机号码：15171425740  
电话：027-87542417-8501  
电子邮箱：xuyishu@hust.edu.cn

联系人：刘小伟

简介：男，甘肃庆阳人，副教授。主要从事燃煤可吸入颗粒物形成机理和排放控制；低浓度颗粒物的在线监测；氧/燃料燃烧方式下煤中矿物质的转化机理、焦的物化特性和污染物排放；煤燃烧过程中痕量元素、Hg的迁移与转化特性等方面的研究。

通信地址：湖北省武汉市洪山区珞喻路1037号华中科技大学煤燃烧国家重点实验室 225  
手机号码：13277958686  
电话：027-87542417-8225  
电子邮箱：xwliu@hust.edu.cn