# 非线性绝缘电介质介电特性表征与测试

李忠华

![](images/fcd1b32a6f02986c7305194f7ccc87e863b7c4a8c74ea0f112e1aeb84e006913.jpg)

李忠华男 1962年生，博士，教授，博士生导师，主要从事非线性聚合物绝缘理论与相关测试技术、电缆绝缘与诊断技术等方面的研究工作。

（哈尔滨理工大学工程电介质及其应用技术教育部重点实验室哈尔滨150080）

摘要：非线性是导致问题复杂化的关键因素之一，且存在于几乎所有物理现象之中。电气绝缘介质的非线性介电行为在科学层面提供了更广泛的研究空间，同时在工程技术层面为电气绝缘结构设计、更高电压等级电力设备研发提供了新的破解瓶颈问题的技术途径。具有电场调控功能的非线性绝缘材料，被称为“智能绝缘材料”，已在大型电机端部绝缘和电缆附件防电晕结构得到广泛的应用。随着高压直流绝缘技术的进步，电气绝缘材料和绝缘结构非线性介电特性和机理研究得到越来越广泛的关注。非线性绝缘介质介电特性的表征和测试技术是极具挑战的研究课题，又是基础研究和工程应用技术研究不可回避的关键性基础问题。稳态直流电场下，非线性绝缘介电特性用伏安特性或电导率与电场强度关系来表征，相应测试技术比较简单。稳态交流电场场下，用等效（相对）介电常数和等效电导率与电场强度关系来表征，测试技术的关键是如何准确地分解阻性和容性电流。暂态电场下非线性绝缘介电特性的表征参数体系尚未建立，测试技术最为复杂，相关研究亟待开展。

关键词：非线性绝缘电介质介电特性表征参数暂态介电特性测试技术中图分类号：TM215

# Characterization and Measurement of Dielectric Properties of Nonlinear Insulating Dielectrics

Li Zhonghua

(Key Laboratory of Engineering Dielectrics and its Application Technology， Ministry of EducationHarbin University of TechnologyHarbin15oo80China ）

Abstract: Nonlinearity is one of the key factors leading to the complexity of the problem,and exists in almost all physical phenomena. The nonlinear dielectric behavior of electrical insulating dielectric provides a more extensive research space on the scientific,and it provides the new way to solve the bottleneck problem in the R & D of higher voltage class power equipment. The nonlinear insulating material with the function of electric field regulation is called "smart insulating materials",and has been widely used in the corona protection structures in large motor and cable accessories. With the development of HVDC insulation technology, more and more attentions have been paid to the study on nonlinear dielectric properties and mechanism of electrical insulating materials and insulation structures. The characterization and measurement of dielectric properties of nonlinear insulating dielectrics is an extremely challenging research topic,and it is also the inescapable key fundamental problem.In the steady-state DC field, the dielectric characteristics of nonlinear insulating dielecrics is characterized by volt-ampere characteristics or the relationship between electrical conductivity and electric field strength, and the corresponding measurement technique is relatively simple.In the steady-state AC field,the dielectric characteristics of nonlinear insulating dielecrics are characterized using the relationships of the equivalent (relative)dielectric constant and the equivalent conductivity with the electric field,and the key technique of measurement is how to decompose accurately the resistive current and the capacitive current.The parameters system for characterizing the dielectric characteristics of nonlinear insulating dielectrics under transient electric field has not been established,and the measurement technology is the most complex,so the related research needs to be carried out urgently.

Keywords:Nonlinear insulating dielectrics,dielectric characteristics,characterization parameters,transient dielectric characteristics,measurement technology

# 1 引言

非线性绝缘介质是指其电导率和（或）介电常数（更确切地讲，应该是极化率）随电场变化而变化的绝缘介质[1-3]。具有场致增强型非线性电导和（或）非线性介电常数的绝缘材料可以实现材料性能参数与空间电场大小的自适应匹配，达到智能改善绝缘结构中空间电场分布均匀性的效果[4]，为此这类材料被称为“智能绝缘材料”[5-6]，在工程应用领域又称为“电应力调控材料”（electricalstressgrading materials[7] 或 electrical stress controllingmaterials[8]）。

非线性绝缘材料具有简化绝缘结构设计、减薄绝缘厚度的效果，在高电压复杂绝缘结构设计和制造领域具有广泛的应用前景。事实上，非线性绝缘介质在高电压绝缘领域已得到了较为广泛的应用，如高压电机定子线棒端部防电晕结构中的防电晕带[8-9]、电缆终端用电场应力控制片（或管）等[10-]非线性绝缘介质在高压直流电缆主绝缘和附件绝缘结构[12]以及高压复合绝缘子[13-17]中具有潜在应用前景。在世界范围内，高压直流输电技术得到广泛的关注，在我国“十三五”期间也将得到更快发展[18]。高压直流输电技术的迅猛发展对电力设备绝缘技术是一个巨大挑战，因为直流绝缘技术相比交流绝缘技术要复杂，其原因之一就是非线性问题。

在直流绝缘体系中，单一聚合物绝缘介质的电导率明显依赖于电场强度，而聚合物基复合绝缘电导率对电场强度的依赖程度则更为明显，可呈现几倍甚至几十倍的变化[19]。同时，绝缘材料的电导率随温度变化是不争的事实，绝缘结构中必然存在温度场分布，直流绝缘结构电场分布无法回避非线性问题，更重要的是非线性因素提供自适应调控的条

件[2.20]。为此，非线性绝缘介质相关研究得到国内清华大学[20-22]、西安交通大学[23-24]、天津大学[25-26]和哈尔滨理工大学等多家研究机构的重视。

绝缘结构中电场分布的计算是电气绝缘结构设计和优化的基础。含有非线性绝缘介质的绝缘结构稳态电场分布计算很难通过求解理论解析解的方式进行，有效解决途径则是采用计算机数值计算进行求解，而暂态电场分布的计算只能采用数值解[27-29]。受非线性绝缘测试技术发展的限制，目前人们尚不能提供令人满意的基础介电参数，尤其是非线性绝缘介质暂态介电参数。正如2007年电气绝缘领域国际知名专家StevenBoggs教授曾指出的那样：测量非线性介质特性是一个重大挑战；计算技术引领测量技术，人们有能力进行瞬态非线性有限元分析已经十余年，但仍无法提供进行数值分析所需要的介电特性测量数据[30]

非线性绝缘电介质在工程上的应用亟待包括暂态介电机理和测试技术在内的理论和技术支撑。受非线性问题自身复杂性的限制，到目前为止仍未形成表征非线性绝缘介质暂态介电特性的参数体系及相应的测试技术[30-33]；同时受测试技术的限制，有关非线性绝缘介质暂态介电机理的研究几乎为空白。

# 2 国内外研究进展

电介质理论是建立在唯象学基础上的，唯象理论是通过实验现象的概括、总结和提炼形成相应的物理规律，由此可见测试技术研究必然是理论研究的前提。测试技术和表征体系又是一对孪生兄弟,表征体系的确定往往是针对测试技术发展的现状做出的明智抉择[2.34]，因此表征体系的建立既要考虑参数体系是否满足科学研究和工程应用的需要，更要兼顾测试技术能否实现其测量问题。从这个意义上讲，表征体系将随测试技术的进步不断完善。

# 2.1非线性绝缘直流稳态介电特性

非线性绝缘介质直流稳态介电特性则用电导率与电场强度的函数关系（电流密度与电场强度曲线或伏安特性曲线）来表征[35]。从原理上讲，非线性直流稳态性能测试技术相对比较简单。从技术角度看，非线性绝缘直流稳态介电特性面临三个技术难点：其一是在高电场下测试时如何消除试样因焦耳热引起的温升，已有研究者设计了特殊形式的试样室，通过注入冷却的氮气来排除因焦耳热产生的热量[8；其二是弱电流信号测试时干扰问题，除了选用高稳定度直流电源和提供良好的屏蔽外，同时也可以采用时域数字信号插值滤波技术；其三是消除绝缘介质极化过程吸收电流的影响问题，个别绝缘介质极化建立过程十分缓慢，测试时间达到105s仍未达到真正意义的稳态，具体的方法是采用极化电流与去极化电流求和运算求得。采用极化电流与去极化电流求和运算实现稳态传导电流测试仍存在一定的问题，因为求和运算获取稳态电流技术是建立在极化充分建立和极化与去极化过程是对称这两个基本假设基础上的。在实际测量过程中，这两个假设条件并非真正意义上的满足。

由于非线性直流稳态介电特性表征和测试技术相对成熟，相关机理研究也趋于完善，如空间电荷限制电流理论、热激跳跃电导理论、肖特基效应和普尔-费兰凯尔效应等成功地建立直流稳态电导率与温度和电场强度的非线性函数关系[36]

本课题组通过大量实验研究，得出LDPE/SiC复合材料的非线性稳态电导影响因素及其规律；结合非线性复合材料的微观结构和经典电介质理论，提出了复合材料的三步输运电导模型；根据所建立的三步输运电导模型，理论推导得出了聚合物基非线性复合材料稳态直流电导率与表观平均电场强度和温度的近似理论[37]，即

$$
\begin{array} { r l } { \gamma ( E , T ) = \displaystyle \frac { q n _ { \mathrm { p } } \nu a } { 3 E } \exp \biggl ( - \frac { \phi _ { \mathrm { p } } } { k T } \biggr ) . } & { } \\ { \sinh \left\{ \displaystyle \frac { q a ( d _ { \mathrm { p } } + d _ { \mathrm { i f } } + 2 \delta ) E } { 2 k T \biggl [ \exp \biggl ( \displaystyle \frac { \phi _ { \mathrm { i f } } - \phi _ { \mathrm { p } } } { k T } \biggr ) \frac { 2 a ^ { 2 } } { \delta } + d _ { \mathrm { p } } \biggr ] } \right\} } \end{array}
$$

该理论公式包含聚合物基体属性、半导电无机

填料属性和界面厚度、界面势垒等微观信息，并定性地解释了复合材料非线性电导与电场强度、温度、填料粒径和填加浓度的关系。

# 2.2非线性绝缘交流稳态介电特性

关于非线性绝缘电介质交流稳态介电性能表征问题，国内外从事工程电介质研究的学者普遍借鉴线性绝缘介质交流稳态介电特性表征途径，即用并联等效电路模型表征介于平板电极间的绝缘介质，不同之处在于采用电压控制性电阻和电容。与此对应的表征非线性绝缘交流稳态介电特性参数体系为电场依赖型电导率和相对介电常数。

非线性绝缘交流稳态介电特性测试，同样可沿用线性绝缘介电特性的测试方法，但可能面临一些技术问题。

高压交流电桥法通常用于线性绝缘介质介电常数和损耗因数（或复介电常数）的测量。采用高压交流电桥研究非线性绝缘交流稳态介电特性时，通过不同幅值交流电压的多次测量可以得到介电常数和损耗因数与电场强度的关系（或复介电常数实部和虚部与电场强度的关系)。常用高压交流电桥均为工频高压电桥，只反映工频条件下交流稳态特性，所获的信息局限性很大，更重要的是高压交流电桥平衡条件与频率有关，非线性绝缘电介质在标准正弦交流电压作用下响应电流含有高次谐波，因此电桥不可能实现平衡。

介电谱仪是研究线性绝缘介质介电特性最有效的工具，但由于常用介电谱仪中激励信号为小幅值交流电压，所以常用介电谱测试无法直接用于非线性绝缘频谱的测量。用于铁电材料测试用介电谱仪可用于非线性绝缘交流稳态特性的测量，电源系统采用幅值可调的高压直流电压源和小幅值交流电压复合电源系统，通过不同幅值直流电压下介电频谱的测量得到不同频率下非线性绝缘等效复介电常数与电场强度的关系[38-39]。由于所测得等效介电参数是在直流高压基础上叠加交流小信号条件下进行测试，所得参数属于“微分等效介电参数”或“动态等效介电参数”[40-41]

从2000 年起，英国曼彻斯特大学B.R.Varlow等针对热固性聚合物/非线性无机填料共混复合非线性绝缘材料的测量建立基于信号发生器 $^ +$ 线性高压放大器为电源交流介电性能测试，实现了 $5 0 \mathrm { { H z } }$ 交流稳态特性的测量[42-45]，具体测试系统原理如图1所示。

法拉第笼1远程计算机击穿保护电容 采样：计算软件0.04uF 保持器试样RMeas 数字在储23920Ω  
信号  
发生器 Q O Q 比较互感器 示波器CCTDoorV=18VCatch

Fig.1Schematic diagram of testing system for the nonlinear insulation steady-state ACdielectric characteristics of B.R. Varlow laboratory

B.R.Varlow等在忽略阻性电流前提下，通过不同工频交流电压幅值下电压等效电容的测量得到电容－电压（介电常数－电场强度）曲线，进而得到了静态和动态介电常数与电场强度的关系。

继B.R.Varlow之后，2005年美国国家标准测量研究院[46-47]、2009年加拿大滑铁卢大学[48]和2013年美国桑迪亚国家实验室[49分别建立各自的交流稳态测试系统，实现高频、高压条件下非线性绝缘电介质交流稳态特性的测试。三个测试系统的共同特点是基于激励电压和响应电流时域波形的测量，同时采用信号发生器和大功率线性放大器构造电源系统，具体原理如图2所示。

![](images/82f66dcbba1cb2054ad86c8261d2fd97f3def858dfe4af0e8e174541d4a90783.jpg)  
图2非线性绝缘电介质高频、高压伏安特性测试系统 Fig.2The testing system for high frequency and high voltage volt-ampere characteristics of nonlinear insulated dielectrics

美国桑迪亚国家实验室测试系统实验能力最强，最高频率为 $1 \mathrm { G H z }$ ，最高电压可达 $2 0 \mathrm { { k V } }$ ，最大电流可达10kA，可实现电容值在 $1 \sim 5 0 \mathrm { n F }$ 范围内的非线性电介质试样极化强度与电场强度（ $\left( P { - } E \right)$ 电滞回线的测量，代表着当今非线性绝缘介质交流稳态介电特性测试领域在硬件方面的最高水平。

本课题组从2007年开始，针对非线性绝缘介质介电性能表征、介电机理及其应用技术开展了较为系统的研究。搭建基于激励电压和响应电流时域瞬时信号数字化测试的非线性绝缘介质交流稳态介电特性测试平台[50]。考虑提高测试精度，分别采用直接法和差分法两种测试系统，如图3所示。

![](images/016a68f3ca48e96919574be3b5e52d08da9b467fc2d3357a39f27b95a7d79bc3.jpg)  
图1B.R.Varlow实验室非线性绝缘交流稳态介电特性测试系统原理图  
图3本课题组非线性绝缘交流介电特性测试平台原理图 Fig.3Schematic diagram of the measuring platform for the AC dielectric properties of non-linear insulation developed by our team

图3a为直接法，适用于低频测试；图3b为差分法，适合高频测试，通过标准电容器 $C _ { \mathrm { N } }$ 支路平衡掉非线性绝缘试品中线性容性电流分量，从而提高了测试系统的灵敏度。

利用上述测试系统，实现激励电压和响应电流的时域测量。提出了“加减运算法”和“时域最小二乘法”响应电流分解技术[50-51]，实现了响应电流阻性和容性电流的分解。根据获得的阻性电流、容性电流和激励电压时域波形信息得到表征非线性绝缘介质和绝缘结构基本特性曲线，由基本特性曲线求得相应的静态、动态参数及其特性曲线。提出了表征非线性绝缘材料及绝缘结构交流稳态介电特性的参数体系，具体见下表。

综合国内外研究发现，几乎所有研究者均仿照线性绝缘介质的等效电路建立非线性绝缘交流稳态特性非线性并联等效电路，没有将极化过程松弛极化行为和非松弛极化行为分开，导致同一试样不同频率下的测试结果不同[52]。松弛极化行为和非松弛极化行为混在一起，所得表征参数无法反映非线性

# 表非线性绝缘材料及绝缘结构介电特性表征参数体系

Tab.Caracterizationparameters system fordielectric properties ofnonlinearinsulating materials and insulation structures   

<html><body><table><tr><td>表征对象</td><td>基本特性曲线</td><td>静态参数特性曲线</td><td>动态参数特性曲线</td><td>等效参数特性曲线</td><td>表征行为</td></tr><tr><td rowspan="4">非线性绝缘结构</td><td rowspan="2">阻性伏安（IR-U）特性</td><td>G及Gs-U特性曲线</td><td>Gd及Gd-U特性曲线</td><td>Gef及Gef-U特性曲线</td><td rowspan="2">阻性</td></tr><tr><td>R及R-U特性曲线</td><td>Rd及Rd-U特性曲线</td><td>Ref及Refr-U特性曲线</td></tr><tr><td rowspan="2">电荷－电压（Q-U）特性</td><td>Cs及Cs-U特性曲线</td><td>Cd及Cd-U特性曲线</td><td>Cef及Cefr-U特性曲线</td><td rowspan="2">容性</td></tr><tr><td>静态复阻抗及其与电压</td><td>动态复阻抗及其与电压</td><td>等效复阻抗及其与电压</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td>特性曲线</td><td>特性曲线</td><td>特性曲线</td><td rowspan="2">阻性</td></tr><tr><td>Y及Y-E特性曲线</td><td>Yd及Yd-E特性曲线</td><td>Yeff及Yef-E特性曲线</td></tr><tr><td rowspan="5">非线性绝缘材料</td><td></td><td>p及ps-E特性曲线</td><td>pd及pd-E特性曲线</td><td>Pefr及pef-E特性曲线</td><td rowspan="2">容性</td></tr><tr><td>D-E特性曲线</td><td>ε及ε-E特性曲线</td><td>εd及εd-E特性曲线</td><td>εefr及εf-E特性曲线</td></tr><tr><td>P-E特性曲线</td><td>x及x-E特性曲线</td><td>Xd及Xd-E特性曲线</td><td>Xefr及Xef-E特性曲线</td><td rowspan="2"></td></tr><tr><td></td><td>静态复介电常数及其</td><td>动态复介电常数及其</td><td>等效复介电常数及其</td></tr><tr><td></td><td>与电场特性曲线</td><td>与电场特性曲线</td><td>与电场特性曲线</td><td>综合</td></tr></table></body></html>

绝缘介质极化行为的物理本质。由于交流稳态介电参数表征体系没有反映非线性绝缘介质极化行为的物理本质，非线性绝缘交流稳态介电机理研究必然存在相当大的局限性。

# 2.3非线性绝缘介质暂态介电特性

非线性绝缘介质暂态介电特性是指非线性绝缘介质在脉冲、阶跃以及直流叠加脉冲等非周期瞬变电场下表现出的宏观介电响应特性。

为了探索非线性绝缘电介质暂态介电特性测试技术，1997年，S.A.Boggs等基于暂态瞬时时域信号测试技术建立了如图4所示的冲击电压下非线性绝缘暂态介电特性测试系统[53]。

![](images/50fe384346c6138034d09acc1cddf0e4d81c06fe29f4c9d30cb7f17e63a879c1.jpg)  
图4Boggs实验室冲击电压下非线性电介质暂态介电性能测试系统

在测试结果分析时，S.A.Boggs等沿用了非线性绝缘交流稳态并联等效电路来表征非线性绝缘暂态介电性能，并以此为基础提出了冲击电压下响应电流分解算法，得到冲击电压下非线性绝缘电导率和介电常数随电场强度变化的曲线[53]。基于所建立的测试系统和信号分解算法，S.A.Boggs等对 $z _ { \mathrm { n O } }$ 阀片和聚合物基非线性电场调控材料进行了非线性介电机理研究[54-55]。研究中发现一些令人困惑的现象，为此2001年S.A.Boggs针对非线性绝缘在冲击电压下介电松弛行为给出两个修正后的等效电路模型[3.56]，如图5所示。

![](images/f33a65c93015e51044587a20a411362668a4c7b223d8ac947e30cb4708b24426.jpg)  
Fig.4The measurement system for transient dielectric Properties of nonlinear dielectrics under impulse voltage in Boggs laboratory   
图5Boggs非线性绝缘暂态等效电路 Fig.5Boggs transient equivalent circuit for nonlinear insulation

图5中只有电阻 $R _ { 1 }$ 为非线性的，其他参数（ $C _ { 1 } .$ $C _ { 2 }$ 和 $R _ { 2 }$ ）均为常数。近期，S.A.Boggs课题组仍采用这个等效电路模型来研究具有场致增强介电常数型非线性绝缘材料的介电机理[57]。S.A.Boggs 和日本工业界合作研究非线性应力控制材料在变频电机绝缘结构中应用，在非线性绝缘暂态介电特性表征方面没有实质性的变化和发展[58-62]。

2012年，挪威耐克森公司的B.Sonerud、S.Josefsson及法国耐克森公司的L.Boyer、P.Mirebeau等[3]研究了非线性绝缘介质在脉冲电压和直流阶跃电压下的暂态介电特性。在模型表征方面没有新意，仍采用无松弛行为的非线性RC并联等效电路。但文献[63]作者在论文的讨论和结论中明确指出了非线性绝缘暂态介电特性表征和测试技术亟待深入研究的问题。

# 3关于非线性绝缘介质暂态介电特性表征和测试技术的思考

# 3.1关于暂态介电特性的表征的思考

为了克服现有非线性绝缘介质暂态介电特性等 效电路模型在表征非线性松弛极化行为的不足，参 照线性绝缘暂态特性等效电路模型，可采用图6所 示的非线性绝缘暂态介电特性等效电路模型，

![](images/f3eb77da7bfcfc10bbf7e2427b56898c2f03c11bad9114e281d784a9ef79c02a.jpg)  
图6非线性绝缘暂态介电特性等效电路模型 Fig.6Equivalent circuit model for transient dielectric characteristics ofnonlinear insulation

该等效电路模型中， $G _ { \mathrm { { D C } } } ( U )$ 表征非线性直流稳态电导特性； $C _ { \infty } ( U )$ 表征高频非松弛极化非线性极化特性； $C _ { \mathrm { { S } } } ( U )$ 和 $R _ { \mathrm { s } } ( U )$ 串联支路表征非线性绝缘松弛极化特性，非线性松弛时间用 $\tau ( U ) = C _ { \mathrm { { S } } } ( U ) R _ { \mathrm { { S } } } ( U )$ 来表征，其中， $C _ { \mathrm { { S } } } ( U )$ 表征非线性绝缘松弛极化对直流静态电容的增量。表征松弛极化特性的支路可以有多个支路的并联，支路个数取决于松弛极化机制的个数。模型中除 $R _ { \mathrm { s } } ( U )$ 外， $G _ { \mathrm { { D C } } } ( U )$ 、 $C _ { \infty } ( U )$ 和$C _ { \mathrm { { s } } } ( U )$ 均具有明确的物理意义，但 $R _ { \mathrm { s } } ( U )$ 与 $C _ { \mathrm { { s } } } ( U )$ 共同表征松弛极化的松弛特性。暂态激励电压 $U$ 是时间的函数，所以上述所有参数均是时间的函数。

在平板均匀电场条件下，消除试样几何尺寸因素后可得到表征非线性绝缘介质暂态介电特性参数$\chi _ { \infty } ( E )$ ， $\chi _ { \mathrm { s } } ( E )$ 、 $\gamma _ { \mathrm { { D C } } } ( E )$ 和 $\tau ( E )$ 。由于暂态过程松弛极化行为是出于动态随时间变化的，故用极化率和$\tau ( E )$ 来表征，而不是 $\varepsilon _ { \mathrm { s } } ( E )$ 和 $\tau ( E )$ 。各参数与电场强度的函数形式可采用多项式，由此可定义类似非线性光学中的高阶电导率和极化率。

非线性绝缘暂态介电特性参数体系全面反映其介电属性和物理本质，换言之，通过暂态介电参数进行理论计算可得到任意激励电压形式的稳态及暂态介电响应特性。

# 3.2关于非线性绝缘暂态介电特性测试技术的思考

非线性暂态介电特性的表征涉及多个物理量与电场强度的函数关系，测试技术就是通过实验的途径获取这些参数及其函数形式。对测试技术而言，可测得不同形式波形和幅值暂态电压（电场）时域波形和对应响应电流时域波形。

如何以测试得到的激励电压和响应电流时域信号为基础数据获得非线性绝缘电介质介电特性表征参数是非线性绝缘介质暂态介电特性测试技术的关键。这一过程和自动控制领域的非线性模式在原理上是相同的，非线性参数数量越多，自由度越高，模式识别难度越大，或鲁棒性越差。

为了克服非线性模式识别因自由度高、鲁棒性差的问题，从理论上讲需要适当增加约束条件。每一种测试条件下测得一组激励电压和响应电流时域信号数据为一个约束条件，这就要求进行多种激励电压波形的组合测试。电压波形组合的合理优化，可有效减少测试次数和提高非线性绝缘介质介电参数的测试精度和准确性。要实现这一目标需要开展大量基础理论研究和实验研究。

非线性绝缘介质暂态介电特性参数测量的基础是如何准确测得激励电压和响应电流时域信号。这就要求测试系统能提供各种可能的暂态激励电压，同时满足响应电流信号的宽频段、宽量限精准测量。往往仅靠硬件电路的优化设计很难满足宽频段、宽量限精准测量，需要通过软件进行测试系统的校验和响应电流信号时域波形的重构。

# 3.3关于非线性绝缘暂态介电特性表征和测试技术后续需要开展的研究

非线性绝缘介质的暂态介电特性表征和测试技术研究现状十分落后，甚至处于空白状态。测试技术是支撑相关基础理论研究和工程应用技术研究的手段。综合分析非线性绝缘介质暂态介电行为，建议开展以下几方面的研究工作：

（1）非线性绝缘暂态介电特性表征参数体系的建立。可借鉴非线性光学的表征途径，建立高阶电导、高阶极化率和极化松弛特性形状函数等参数体系。表征参数体系中，非线性松弛极化的形状函数的确定难度最大，需要通过大量实验规律的总结和理论分析来确定。

(2）非线性绝缘暂态介电特性等效电路的建立。等效电路的作用是建立非线性绝缘介质介电参数体系和激励电压、响应电流时域信号关联的桥梁，即首先通过激励电压和响应电流信号作为基础数据，通过适当的算法求取非线性等效电路非线性器件参数函数，而后消除试样几何尺寸因素得到介质表征参数。需要通过理论和实验综合研究确定等效电路的形式，以确保等效电路的有效性。有效性的评价应通过验证性实验进行验证。

(3）非线性等效电路非线性器件表征函数和参数的求取。即以激励电压和响应电流信号作为基础数据，通过适当的算法确定非线性等效电路非线性器件参数函数和求取函数中的具体参数。该过程可借鉴非线性模式识别技术得以实现。(4）激励电压波形组合的优化。每一种激励电压与响应电流时域测试数据视为一个约束条件，至少需要多少组测试数据可保证非线性模式识别的鲁棒性是值得深入研究的问题。(5）非线性绝缘暂态介电特性测试平台的建立。搭建测试平台的硬件系统和开发软件系统。硬件系统主要由电源与激励电压和响应电流测试系统组成。电源系统可采用可编程信号发生器和高精度线性高压放大器组合构成。激励电压和响应电流测试系统应满足宽频段、宽量限精准测量的要求，可通过硬件设计和软件修正两个环节得以实现。

# 4结论

非线性绝缘暂态介电行为十分复杂，涵盖直流稳态和交流稳态及极化动态松弛行为。非线性绝缘介质暂态介电特性表征参数体系将是反映材料介电属性最完备的参数体系。采用暂态介电表征参数体系开展相关基础理论研究和应用技术研究可实现研究过程的全面性、系统性和彻底性。然而，因非线性和暂态双重因素，非线性绝缘介质暂态介电特性表征和测试技术面临极大的挑战。非线性绝缘介质暂态介电特性测试技术研究不仅为非线性绝缘电介质理论研究和工程应用研究奠定基础，同时可促进包括铁电体在内的非线性功能电介质介电特性研究。

# 参考文献

[1] Varlow B R.Nonlinear fillers in electrical insulation[J].IEE Proc Sci Meas Technology, 1997,   
144(3):453-461. [2] QiX,Zheng Z,Boggs S.Engineering with nonlinear dielectrics[J].IEEE Electrical Insulation Magazine,   
2004,20(6): 27-34. [3] Sun Ying，Ma Shilei,Steven A Boggs.Mechanism for omposite materials with dielectric constant which increases with electric field[J]. IEEE Transactions on Dielectrics and Electrical Insulation, 2015,22(3): 1719-1722.   
[4] 何金良，谢竟成，胡军．改善不均匀电场的非 线性复合材料研究进展[J]．高电压技术，2014, 40(3): 637-647. He Jinliang,Xie Jingcheng,Hu Jun. Progress of nonlinear polymer composites for improving nonuniform electrical fields[J]. High Voltage Engineering,2014, 40(3): 637-647.   
[5] Tavemier K,Varlow B R,Auchland D W, et al. Inprovement in electrical by nonlinear fillers[J]. IEE Proc Sci Meas Technology,1999,146(2): 145-149.   
[6] Donzel L,Freuter F,Christen T.Nonlinear resistive electric field grading part 2: materials and applications[J]. IEEE Electrical Insulation Magazine, 2011,27(2): 18-29.   
[7] Staubach Christian,Hildinger Thomas, Staubach Axel. Comprehensive electrical and thermal analysis of the stress grading system of a large hydro generator[J]. IEEE Electrical Insulation Magazine, 2018, 34(1): 37-39.   
[8] Al-Gheilani A, Rowe W, Li Yongxiang, et al. Stress control methods on a high voltage insulator: a review[C]. ICEP,2016: 95-100.   
[9] Sharifi E,Jayaram S H, Cherney EA. Temperature and electric field dependence of stress grading on formwound motor coils[J]. IEEE Transactions on Dielectrics and Electrical Insulation, 2010,17(1): 264-270.   
[10]胡军，赵孝磊，杨霄，等．非线性电导材料应力 锥改善电缆终端电场强度分布[J]．高电压技术, 2017，43(2): 398-404. Hu Jun, Zhao Xiaolei, Yang Xiao, et al. Improving the electric field strength distribution of cable terminals by stress cone of nonlinear conductivity material[J]. High Voltage Engineering,2017, 43(2): 398-404.   
[11]冯鑫，佟庆彬，袁立敏，等．超导电缆终端用 非线性复合材料研究进展[J]．绝缘材料，2017, 50(12): 10-14. Feng Xin, Tong Qingbin, Yuan Limin, et al. Research progress in nonlinear polymer composites for superconducting cable terminal[J]. Insulating Materials,2017, 50(12): 10-14.   
[12]Boggs S A,Dammon D H. Effect of insulation properties on the field grading of solid dielectric DC cable[J]. IEEE Transactions on Power Delivery, 2011, 16(4): 456-461.   
[13]Sellars A G, Macgregor S J. The design of dielectric barriers for HVDC bushings[C]. IEE Colloquium on Field Modelling: Applications to High Voltage Power Apparatus,London, UK,1996: 3/1-3/6.   
[14]Ying S,Cherney E A,Jayaram S H. Electric stress grading of composite bushings using high dielectric constant silicone compositions[C]. IEEE International Symposium on Electrical Insulation, Indianapolis, USA,2004: 320-323.   
[15]Monga S,Gorur R S, Hansen P, et al. Design optimization of high voltage bushing using electric field computations[J].IEEE Transactions on Dielectrics and Electric Insulation, 2006,13(6): 1217-1224.   
[16] Onneby C,Martensson E,Gafvert U, et al. Electrical properties of field grading materials influenced by the silicon carbide grain size[C]. Proceedings of IEEE 7th International Conference on Solid Dieletrics, Eindhoven, Netherlands,2001: 43-45.   
[17]Hubert Bilodeau, Saman Babaei,Bruno Bisewski. Making old new again: HVDC and FACTS in the northeastern united states and canada[J]. IEEE Power and Energy Magazine,2016,14(2): 42-56.   
[18]国家能源局．电力发展“十三五”规划（发布稿). 2016.   
[19]Steven Boggs, Dwight H Damon, Jesper Hjerrild, et al. Effect of insulation properties on the field grading of solid dielectric DC cable[J]. IEEE Transactions on Power Delivery,2001, 16(4): 456-462.   
[20]胡军，杨霄，何金良．电导及介电自适应调控的 复合绝缘材料及其应用[J]．高电压技术，2016, 42(9): 2902-2908. Hu Jun, Yang Xiao, He Jinliang. Composite insulating material with self-adaptively adjusted conductivity/permittivity and its applications [J]. High Voltage Engineering,2016, 42(9): 2902- 2908.   
[21]Yang Xiao, Zhao Xiaolei, Li Qi, et al. Nonlinear effective permitivity of field grading composite dielectrics[J]. Journal of Physics D: Applied Physics, 2018, 51(7): 1168-1171.   
[22]Yang Xiao, Zhao Xiaolei, Hu Jun,et al. Grading electric field in high voltage insulation using composite materials[J]. IEEE Electrical Insulation Magazine,2018, 34(1): 15-25.   
[23]Han Yongsen, Min Daomin,Li Shengtao. Nonlinear conduction and surface potential decay of epoxy/SiC nanocomposites[J]. IEEE Transactions on Dielectrics and Electrical Insulation, 2017,24(5): 3154-3164.   
[24]Yu Shihu, Li Shengtao. Effects of surfacemodification on properties of Graphene/Epoxy composites[C]. 1st International Conference on Electrical Materials and Power Equipment, 2017: 460-493.   
[25]Du Boxue,Li Jin,Li Zhonglei, et al. AngEffects of non-linear conductivity on charge trapping and de-trapping behaviours in epoxy/SiC composites under DC stress [J]. IET ScienceMeasurement and Technology, 2018,12(1): 83-89.   
[26]杜伯学，李忠磊，杨卓然，等．高压直流交联聚 乙烯电缆应用与研究进展[J]．高电压技术，2017, 43(2): 344-354. Du Boxue,Li Zhonglei, Yang Zhuoran,et al. Application and research progress of HVDC XLPE cables[J]. High Voltage Engineering, 2017, 43(2): 344-354.   
[27]Takahiro Umemoto, Takao Tsurimoto, Tomohito Kisakibaru, et al. Novel evaluation methods of endturn stress grading materials for converter-fed high voltage rotating machines[C]. IEEE Conference on Electrical Insulation and Dielectric Phenomena, 2016: 307-310.   
[28]李忠华，刘乐乐，郑欢，等．HVDC 电缆电场分 布影响因素的仿真研究[J]．中国电机工程学报, 2016，36(9): 2563-2571. Li Zhonghua, Liu Lele, Zheng Huan, et al.Simulation on the influence factors of electric field distribution in HVDC cable[J]. Proceedings of the CSEE,2016, 36(9): 2563-2571.   
[29]郑欢，刘乐乐，李忠华，等．直流叠加冲击电压 下 HVDC电缆暂态电场分布特性研究[J]．中国电 机工程学报，2016，36(24)：6682-6692. Zheng Huan, Liu Lele, Li Zhonghua, et al. Research cable under DC voltage superimposed impulse voltages[J]. Proceedings of the CSEE,2016, 36(24): 6682-6692.   
[30]Boggs S. Applications of nonlinear analysis in power engineering[C]．西部地区研究生精品课程 大讲堂－工程电介质及其应用(专题十)，西安, 中国，2007：1-37.   
[31]Greijer H, Predhan M,Eriksson G. On the estimation of AC behavior of field grrading composite[C]. Annual Report Conference on Electrical Insulation and Dielectric Phenomena,Montreal, Canada, 2015: 67-71.   
[32]Jiang G, Rhyner J, Boggs S. Measurement of nonlinear dielectric properties-theoretical analysis[C]. Conference on Electrical Insulation and Dielectric Phenomena,Minneapolis, USA,1997: 206-209.   
[33]Goran Eriksson, Helena Greijer, Manoj Pradhan, et al. Stress dependent conductivity of field grading materials under time varying electrical fields[C]. Annual Report Conference on Electrical Insulation and Dielectric Phenomena, 2012: 165-169.   
[34]Thomas Christen,Lise Donzel, Felix Greuter. Nonlinear resistive electric field grading part 1: theory and simulation[J]. IEEE Electrical Insulation Magazine, 2010,26(6): 47-59.   
[35]Gao L, Yang X, Hu J, et al. ZnO microvaristors doped polymer composites with electrical field dependent nonlinear conductive and dielectric characteristics[J]. Materials Letters,2016,171:1-4.   
[36]陈季丹，刘子玉．电介质物理[M]．北京：机械工 业出版社，1980.   
[37]郭文敏．聚合物／无机填料复合材料非线性电导特 性及应用[D]．哈尔滨：哈尔滨理工大学，2010.   
[38]Thomas Christen, Roman Kochetov, Louise Almquist. High-voltage low-frequency dielectricspectroscopy used for characterization of nonlin ear insulation materials[C]. IEEE International Conference on Dielectrics,2016,2: 848-851.   
[39]Furukawa T, Nakajima K,Koizumi T, et al. Measurement of nonlinear dielectricity in ferroelectric polymers[J]. Japanese Journal of Applied Physics,1987,26(7): 1039-1045.   
[40]谢竟成，胡军，何金良，等．压敏陶瓷-硅橡胶复 合材料的非线性压敏介电特性[J]．高电压技术， 2015，41(2): 446-452. Xie Jingcheng,Hu Jun,He Jinliang, et al.Nonlinear dielectric and conductivity properties of ZnO varistor/silicone rubber polymer composites[J]. High Voltage Engineering,2015, 41(2): 446-452.   
[41]Thomas Christen,Roman Kochetov. Insulation characterization with nonlinear impedance spectroscopy[C]. ETG Symposium on High Voltage Technology, 2016: 1-6.   
[42]Varlow B R, Li K. Non-linear AC properties of a ceramic/resin composite[C]. The 6th International Conference on Properties and Applications of Dielectric Materials,Xi'an, China,200o: 89-92.   
[43]Donnelly K P, Varlow B R. Non-linear DC and AC conductivity in electrically insulating composites[J]. IEEE Transactions on Dielectrics and Electrical Insulation,2003,10(4): 610-614.   
[44]Robertson J, Varlow B R.A comparison between the dynamic and static AC conductivity characteristics of barium titanate flled acrylic resin[C]. IEEE ICSD, Toulouse,France,2004: 246-251.   
[45]Robertson J, Varlow B R. Non-linear ferroelectric composite dielectric materials[J]. IEEE Transactions on Dielectrics and Electrical Insulation,20o5,12(4): 779-790.   
[46]Obrzut J, Kano K. Non-linear dielectric testing at high AC voltages using waveforms and harmonics[C]. IEEE Annual Report Conference on Electrical Insulation Dielectric and Phenomena, New York, USA,2005: 573-576.   
[47] Obrzut J, Kano K. Impedance and nonlinear dielectric testing at high AC voltages using waveforms[J]. IEEE Transactions on Instrumentation and Measurement, 2005,54(4): 1570-1574.   
[48]Sharif E,Jayaram S H, Cherney E A.AC modeling and anisotropic dielectric properties of stress grading of form-wound motor coils[J]. IEEE Transactions on Dielectrics and Electrical Insulation, 2010,17(3): 694-700.   
[49]Zutavern F J, Brennecka G L, Glover S F. A testbed for high voltage, high bandwidth characterization of nonlinear dielectrics[C]. 19th IEEE Pulsed Power Conference, 2013: 1-6.   
[50] 郑欢．非线性复合绝缘电介质交流介电特性测试 技术研究[D]．哈尔滨：哈尔滨理工大学，2012.   
[51]郑欢，李忠华，黄志鹏，等．非线性绝缘电介质 AC 介电特性参数及其测量[J]．中国电机工程学 报，2013，33(4)：201-208. Zheng Huan,Li Zhonghua, Huang Zhipeng, et al. AC dielectric characterization parameters of nonlinear insulating dielectrics and their measurement[J]. Proceedings of the CSEE,2013,33(4):201-208.   
[52]Han Yongsen,Li Zhonghua, Zheng Huan,et al.A decomposition method for the total leakage current of MOA based on multipleLinear regression[J]. IEEE Transactions on Power Delivery, 2016,31(4): 1422- 1428.   
[53]Jiang G, Rhyner J, Oesterheld J, et al. Measurement of non-linear dielectric properties: theoretical analysis[C]. IEEE Annual Report Conference on Electrical Insulation and Dielectric Phenomena, Minneapolis,MN,USA,1997(1): 206-209.   
[54]Li, Lillian, Boggs,Steven A. Circuit to cancel ac displacement current to reveal dissipative and nonlinear conduction phenomena[J]. Review of Scientific Instruments, 1999,70(9): 3749-3754.   
[55] Boggs S A, Zhou JY. Dielectric property measurement of nonlinear grading materials[C]. IEEE Annual Report Conference on Electrical Insulation and Dielectric Phenomena, Victoria,BC, Canada,2000: 764-768.   
[56]Zhou JY, Boggs S A. Measurement of nonlinear dielectric properties effect of dielectric dispersion[C]. IEEE Annual Report Conference on Electrical Insulation and Dielectric Phenomena,Kitchener, Ont, Canada,2001: 153-156.   
[57]Sun Ying,Ma Shilei, Boggs Steven A. Mechanism for composite materials with dielectric constant which increases with electric field[J].IEEE Transactions on Dielectrics and Electrical Insulation, 2015,22(3): 1719-1722.   
[58]Takahiro Umemoto,Takao Tsurimoto,Boggs Steven A.Considerations on evaluation methods for reliable stress grading systems of converter-fed high voltage rotating electrical machines[C]. IEEE Conference on Electrical Insulation and Dielectric Phenomena, 2015: 47-50.   
[59] Boggs Steven A, Akiko Kumada, Tetsuo Yoshimitsu. Measurement of stress grading conductivity to $1 . 6 \mathrm { M V / m }$ and $1 5 5 ^ { \circ } \mathrm { C }$ computation of grading power density and temperature rise for PWM waveforms[C]. Proceedings of International Symposium on Electrical Insulating Materials, 2014: 54-56.   
[60] Boggs Steven A,Akiko Kumada, Tetsuo Yoshimitsu. Rotating machine end turn grading during PWM transitions[C]. IEEE International Conference on Dielectrics, 2016(1): 1-4.   
[61]Boggs Steven A,Akiko Kumada, Tetsuo Yoshimitsu. Analytical approximations for the rotating machine end-turn field distribution[J].IEEE Transactions on Dielectrics and Electrical Insulation,2015,22(6): 3146-3152.   
[62]Boggs Steven A,Akiko Kumada, Tetsuo Yoshimitsu. End-turn grading for PWM-driven machines[C]. IEEE Electrical Insulation Conference,2015:158- 160.   
[63] Sonerud B, Josefsson S, Boyer L. Impulse and step voltage measurements on materials with non-linear V-I characteristic[C].Annual Report Conference on Electrical Insulation and Dielectric Phenomena, 2012: 207-210.