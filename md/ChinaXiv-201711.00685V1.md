编号：163243

# 基于热响应法的航天器推进剂质量测量热模型

胡振文」，孙克新²，艾青1\*，邢栋¹，张高雄²，夏新林1(1.哈尔滨工业大学能源科学与工程学院，哈尔滨 150001；2.上海卫星工程研究所，上海 201109)

摘要：本文以热响应法测量航天器微重力条件下贮箱推进剂剩余质量为背景，建立了航天器贮箱内外热环境耦合作用下的整体热分析模型，通过将航天器贮箱外部热环境视为第二类浮动热边界条件，实现贮箱气液两相分布下的热分析解耦计算，为热响应法提供精确的温度场计算方法。采用该方法，针对热响应法测量微重力条件下某航天器贮箱内部推进剂质量所需的温度场分布，通过数值仿真获得了空间在轨阶段，热响应法加热工作时贮箱内外热环境整体耦合下的温度场分布，并依据特定检测点的瞬态温度变化，反演得到了剩余推进剂的质量。研究发现采用热响应法测量推进剂质量时，贮箱温度场不仅受贮箱内部加热影响，在轨外部热环境也会明显影响贮箱壁面温度的均匀性。

关键词：热响应法；微重力；推进剂质量；温度场中文分类号：TK124 文献标识码：A

# A Thermal Model for Measurements of Aircraft Propellant Mass Based on the Thermal Propellant Gauging System Method (TPGS)

HU Zhen-wen1, SUN Ke-xing², AI Qing1\*, XING Dong1, ZHANG Gao-xiong², XIA Xin-lin' (1.School of Energy and Power Engineering; Harbin institute of Technology,15ooo,Harbin

2.Shanghai Institute of Satellite Engineering,201109, Shanghai)

Abstract:This paper isbasedonThermal Propellant Gauging Systemmethod(TPGS)to measure propellnt massin microgravity.A thermalanalysismodelforaircraft propellantsystemcoupled efectsof space environment.Takingthe efectsof theoutside environmentas Neumannboundarycondition.Decouple thecalculatiosofthermalanalysisanddistributioninphaseofgasndliquid. ProvidingamethodologyforaccuratethermalanalysisofThermalPropellnt Gauging Method.Utilizedthis methodanalyzeda temperature fieldofpropelantsystem.Utilizednumericalsimulations tocalulatethehatingprocesofThermal Propellant Gauging Methodandobtainthetemperaturedistributionofpropelantsystem.Acordingtothetemperatureresponseofmonitorpint,temass of propelantwascalculated.Itwasfoundthat theoutsideenvironmenthasavitalefectsonthrmaldistributionofpropelanttank.

Key words: Thermal Propellant Gauging Method; microgravity; propellant gauging; temperature field

# 0引言

随着我国航天技术的不断发展，不少液体推进剂得到了广泛应用。而推进剂的多少直接与航天器的寿命相关联，故在航行时准确的估算出贮箱内推进剂的剩余质量显得至关重要[1]。在地面上测量液体质量已有成熟的技术，然而对于微重力条件下，由于其特殊的环境限制，液体体积测量相当困难。由于液体处于微重力或零重力条件下，常规的依赖于重力加速度和浮力的称重法，静压差法等均不能应用。又由于微重力条件下，液体的表面张力为主导作用力，容器内部有各种复杂结构，使得液体的位置不稳定，使得辐射法，光学法等地面测量技术也难以应用[2]。从19 世纪60 年代开始，已经提出了十几种在轨条件下推进剂的测量的检测技术[3-8]。其中，热响应法在推进剂剩余量较低的时候具有非常高的精度，在航天器寿命末期可以确定推进剂准确的剩余量[1]。热响应法是以微重力条件下推进剂瞬态热响应来反演推进剂质量的一种方法，其测量机理主要是在测量过程中向贮箱内输入特定热流，不同的推进剂剩余质量在贮箱内的气液分布不同。因此在输入特定热流时，其热响应不同。根据这个差别，进行反演计算得到推进剂的剩余质量。传统热响应法分析只考虑微重力下的气液分布对贮箱热响应的影响。实际在轨条件下，航天器和贮箱不停的与外界环境进行热交换，复杂的热作用势必影响贮箱表面的热响应。

本文针对热响应法的需求，建立了卫星贮箱内外热环境耦合作用下的整体热分析模型，通过将卫星贮箱外部热环境视为第二类浮动热边界条件，不仅考虑了贮箱内的气液分布对热响应的影响，同时考虑了航天器在轨条件下外界环境热作用对贮箱的影响。采用该方法，针对热响应法测量空间微重力条件下某航天器贮箱内部推进剂质量所需的温度场分布，通过数值仿真获得了空间在轨阶段，热响应法加热工作时贮箱内外热环境整体耦合下的温度场分布。

为了得到贮箱准确的热响应，首先要计算微重力条件下不同推进剂剩余质量的气液两相分布。其次要建立在轨条件下航天器内部与外界环境复杂的热交换模型。最后将在轨条件外界换热作为边界热流与微重力条件下的气液分布耦合计算，模拟热响应法加热阶段的热响应。耦合计算流程图如图2所示。

# 1 理论模型

在轨条件下，航天器内外部件与外太空环境进行复杂的热交换，传热模型如图1所示。

![](images/9d19a4689a186ddd8eeff9efeb0368baee2fdd642dcf879ad9186571af1d9444.jpg)  
图1在轨条件下的换热模型  
Fig.1 The schematic diagram of heat transfer model when in the orbital motion

![](images/12530fa59223ddc5cd6780d60a56d0391ae48e3d26ac8502edd0c84d695c5520.jpg)  
图2耦合计算流程图  
Fig.2 The diagram of coupled computation process

两相流动的基本控制方程是动量方程9]：

$$
\frac { \partial } { \partial t } ( \rho \vec { \nu } ) + \nabla \cdot ( \rho \vec { \nu } \vec { \nu } ) = - \nabla p + \nabla \cdot \left[ \mu \left( \nabla \vec { \nu } + \nabla \vec { \nu } ^ { \ T } \right) \right] + \rho \vec { g } + \vec { F }
$$

采用FLUENT进行模拟计算微重力条件下推进剂气液两相分布。其中采用的是有限体积法中的VOF计算模型。过引入 $\mathsf { q }$ 相的体积分数变量 $\alpha _ { \_ q }$ ，计算相界面。追踪相界面主要是依靠求解单相或多相的容积比率的连续方程来完成的。对第 $\mathsf { q }$ 相，方程如下[9].

$$
\frac { 1 } { \rho _ { q } } \Bigg [ \frac { \hat { \sigma } } { \hat { \sigma } t } \big ( \alpha _ { q } \rho _ { q } \big ) + \nabla \cdot \big ( \alpha _ { q } \rho _ { q } \vec { \nu } _ { q } \big ) = S _ { \alpha _ { q } } + \sum _ { p = 1 } ^ { n } \big ( \dot { m } _ { p q } - \dot { m } _ { q p } \big ) \Bigg ]
$$

式中， $\dot { m } _ { \boldsymbol { q p } }$ 为q相传递到 $\mathfrak { p }$ 相的质量， $\dot { m } _ { \textit { p q } }$ 为 $\mathfrak { p }$ 相传递到 $\mathsf { q }$ 相的质量，源项 $S _ { \alpha _ { q } }$ 为0。主相容积比率的计算基于如下的约束：

$$
\sum _ { q = 1 } ^ { n } \left( \alpha _ { q } \right) = 1
$$

而在轨条件下航天器与外界环境的换热计算采用

SINDA/FLUENT进行模拟计算。通过设定在轨工况和轨道参数，建立航天器在轨条件下的热模型，计算热量分布。采用的计算模型主要为热网络法和蒙特卡洛法。热网络法基本控制方程为节点的能量守恒方程：

$$
\rho c \frac { \partial T } { \partial \tau } = \lambda \nabla ^ { 2 } T + Q _ { c } + Q _ { r } + Q _ { o }
$$

式中， $Q _ { c }$ 为表面间的对流换热量； $Q _ { r }$ 为表面间的辐射换热量； $Q _ { o }$ 为发热设备的内热源项。蒙特卡洛法计算大型复杂系统换热量方程为：

$$
\Phi _ { i , j } = \sigma ( A _ { i } \varepsilon _ { i } T _ { i } ^ { 4 } \cdot R D _ { i , j } - A _ { j } \varepsilon _ { j } T _ { j } ^ { 4 } \cdot R D _ { j , i } )
$$

式中， $\Phi _ { i , j }$ 是 $A _ { i }$ 向 $A _ { j }$ 的辐射传热热流量， $[ \mathrm { W } ] ; A _ { i }$ $A _ { j }$ 是面积， $[ \mathbf { m } ^ { 2 } ] ; R D _ { i , j } \setminus R D _ { j , i }$ 分别是 $A _ { i }$ 对 $A _ { j }$ 、$A _ { j }$ 对 $A _ { i }$ 的辐射传递系数

得到外界对贮箱的热影响以边界热流的形式输出。之后的耦合计算依然采用的是ANSYSFLUENT软件进行模拟计算，得到贮箱内特定点的温度响应。

# 2微重力下推进剂气液分布数值模拟

在数值模拟计算时，首先要建立贮箱内部的几何模型和网格文件。图3为贮箱系统的几何模型。微重力条件下液体的表面张力为主导，为了保证推进剂的持续输出，贮箱内一般会采用推进剂管理装置进行管理。推进剂管理装置对贮箱的气液分布影响显著，故贮箱模型内也包含了简单的管理装置。采用ANSYSCFDICEM建立非结构化网格文件，如图4所示。为保证计算结果进度，网格密度较高，网格体单元数为818394，网格面单元数1689015，网格节点数为164340。

![](images/9a630e80a296da5b710d39edc99bd612c31fc66b44d73a96d313ee3e8e9635d7.jpg)  
图3贮箱系统几何模型  
Fig.3 The geometry model of Propellant Gauging System

![](images/4fd3335a2415e59916350a99c1551e7e9c600e50ae7784c8d935785406087b30.jpg)  
图4贮箱网格划分图

![](images/c44ebb987c82eb9e0781190d277403e0f961b7eb87fae21f69d6df30f0849ad5.jpg)  
Fig. 4 The mesh of the tank

![](images/588e9928536a445f340dcbd86869e051ac0efe21c3493a698bdb65fd89b09e91.jpg)  
图5推进剂剩余质量 $6 0 \mathrm { k g }$ 时贮箱内气液两相分布 Fig.5 The distribution of liquid-phase volume fraction in the tank when the remaining mass of propellant is $6 0 \mathrm { k g }$   
图6推进剂剩余质量 $4 0 \mathrm { k g }$ 时贮箱内气液两相分布 Fig.6 The distribution of liquid-phase volume fraction in the tank when the remaining mass of propellant is $4 0 \mathrm { k g }$

以常用的液体推进剂甲基肼为工质，模拟了零重力加速度条件下，推进剂剩余质量为 $6 0 \mathrm { k g }$ 和 $4 0 \mathrm { k g }$ 时的两相分布。图5、图6分别为推进剂剩余质量为$6 0 \mathrm { k g }$ 和 $4 0 \mathrm { k g }$ 时贮箱内部液相体积分数分布图，其中数值为1表示为液相推进剂。数值为0表示气相。可见在推进剂管理装置的作用下，液态推进剂主要集中在贮箱下部份，且液面出现凹陷，推进剂沿着导液槽相上爬升，推进剂浸没下半球表面。

# 3 热响应耦合模拟计算

由于贮箱内的热响应过程是在轨条件下实施的热动作，在贮箱热仿真过程中需要实时考虑航天器的影响。航天器受到外热流、内功耗的影响，贮箱周围的环境实时变化。以地球同步卫星为例，采用SINDA/FLUENT模拟计算了在轨条件下贮箱内部热环境。采用的轨道为地球同步轨道，计算夏至日贮箱与环境的换热，得到在轨条件下的贮箱表面热流分布，将计算得到的热流分布作为浮动的热流边界进行输出。

提取在轨条件下得到的贮箱表面热流分布，与之前计算得到的贮箱内部推进剂分布耦合计算，以贮箱表面的热流分布为外界边界条件，计算在轨条件外界环境对贮箱的热影响。同时模拟实施热响应的加热过程，在贮箱表面特定位置，输入热响应加热热流，同时检测特定检测点的温度响应。通常实施热响应法加热过程为10-100h不等，本文采用的加热时间为 $2 5 \mathrm { h }$ 。如图7所示，为推进剂剩余质量分别为 $4 0 \mathrm { k g }$ 和 $6 0 \mathrm { k g }$ 时热响应法实施 25h 贮箱温度分布图。

由图7可以看出，在外界热流影响下，贮箱内部的温度分布出现了不均匀性。推进剂剩余质量为$6 0 \mathrm { k g }$ 时，温度普遍低于 $4 0 \mathrm { k g }$ 时的温度。通过检测壁面上特定点的温度值，来反映贮箱热响应。图8为实施热响应法时壁面某监测点温度响应曲线。由图11可以看出，推进剂剩余质量为 $6 0 \mathrm { k g }$ 时检测点的温度均低于 $4 0 \mathrm { k g }$ 时的温度。在热响应法整个25h的加热时间内，壁面检测点的温度上升较大。对于推进剂剩余质量为 $6 0 \mathrm { k g }$ 时，最大温升为70度左右，而对于推进剂剩余质量为 $4 0 \mathrm { k g }$ 时，最大温升达到了170度。壁面检测点的位置选取对于热响应法十分关键。在推进剂剩余质量较少时，由于毛细作用附着于壁面的液体层厚度更薄，受到热响应法加热热流影响，温度上升更大。特别要注意的是，加热片的位置要选在液体覆盖区，若在气相区，温度会急剧上升，甚至烧坏壁面。可以看出推进剂质量仅相差 $2 0 \mathrm { k g }$ 而检测点的温度响应差异显著。而热响应法便是建立不同推进剂剩余质量检测点的温度响应数据库来推算实际推进剂剩余质量，温度响应差距越大，表明该方法的精度越高，表明热响应法在推进剂剩余质量较少时可以达到很高的精度。

![](images/72d9cddecc7f4332a66be9aae99ea3dbad28e4085f3af807f38cf955a86412d0.jpg)  
b）推进剂剩余质量 $6 0 \mathrm { k g }$

![](images/7db51385cbd30f50f07622fe00b44525d1e98494d3846f98875f8289096fc57a.jpg)  
图7热响应法加热25h不同推进剂剩余质量贮箱温度分布 Fig.7The temperature distribution in the tank when applied TPGS method to heat the system for $2 5 \mathrm { h }$ 、a) the remaining mass of propellant is $4 0 \mathrm { k g }$ ,and b) the remaining mass of propellant is   
图8热响应法加热25h壁面不同推进剂剩余质量监测点温度响应曲线  
Fig.8 The temperature of monitor point for different remaining

massof propellant when applied TPGS to heat the tank for $2 5 \mathrm { h }$

# 5结论

本文针对热响应法测量微重力条件下贮箱内推进剂剩余质量，建立了微重力条件下同时考虑贮箱内气液两相分布和在轨条件热边界的一体化分析方法。对贮箱进行建模，模拟计算了微重力条件下贮箱内部气液两相分布；在轨条件下外界环境对贮箱的热影响，以边界热流的形式与贮箱内两相分布耦合计算，模拟计算了热响应法的加热阶段，得到不同推进剂剩余质量，特定检测点的温度响应。结果表明在轨条件外界环境对贮箱表面温度分布有一定的影响，在外界热流作用下，贮箱表面温度分布出现了不均匀性。得到了推进剂剩余质量分别为 $4 0 \mathrm { k g }$ 和 $6 0 \mathrm { k g }$ 时贮箱壁面检测点的温度响应。推进剂剩余质量为 $4 0 \mathrm { k g }$ 时温度均高于 $6 0 \mathrm { k g }$ 时的温度。温差能够达到将近100 摄氏度。推进剂剩余质量仅相差$2 0 \mathrm { k g }$ ，检测点温度响应差距明显。表明热响应法在推进剂剩余质量较少时将有良好的测量精度。

# 参考文献

[1]Aparicio A. Thermal Propellant Gauging at EOL, Telstar 11 Implementation[C]// SpaceOps 2008 Conference.2008.   
[2]傅娟.微重力条件下贮箱液体推进剂量自主检测方法研 究[D]．国防科学技术大学,2010.   
[3]Yeh T P. Bipropellnt propulsion performance and propellant-remaining prediction for INSAT-1B[J]. Journal of Propulsion & Power,1992,8(1):74-79.   
[4] Monti R, Golia C. Liquid gauging technologies for space stations utilization[C]//Stockholm International Astronautical Federation Congress. Stockholm International Astronautical Federation Congress,1985.   
[5] Chobotov M V, Purohit G P. Low-gravity propellant gauging system for accurate predictions of spacecraft end-of-life[J]. Journal of Spacecraft & Rockets,1993, 30(1):92-101.   
[6] Roberti D,Durgin W W. An ultrasonic measurement technique to determine the location and volumeof spherical voids in fluids[J].Diabetes,2015,64(3):828-839.   
[7] Hansman R,Meserole J.Fundamental limitations on low gravity fluid gauging technologies imposed by orbital mission requirements[C]// Joint Propulsion Conference. 1988.   
[8] Challoner A.Determination of spacecraft liquid fill fraction[J].Aiaa Guidance,1993:254-264.   
[9] Cao J G, Qin Y J,Jie Z,et al. Numerical study on parameters of multi-zone cooling for work roll based on unsteady VOF model of Fluent[J]． Zhongnan Daxue Xueba0,2011,42(12):3742-3747.