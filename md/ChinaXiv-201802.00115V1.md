# 垃圾焚烧烟气扩散的多尺度模拟与分析

崔鹏义　吴志根 陶文钰\*（同济大学环境科学与工程学院，上海200092）

摘要垃圾焚烧会产生大量的二次污染，使得原本极为推崇的垃圾焚烧发电倍受质疑。本文利用CFD技术对垃圾焚烧产生的烟气通过烟肉高空扩散的规律进行数值模拟，研究在多尺度空间条件下流场和污染物分布。采用标准 $k \cdot \varepsilon$ 湍流模型及组分输运模型，分析不同排烟高度和速度对排烟地点下风向1.4公里小区建筑群内污染物分布的影响。研究表明 $\mathrm { S O } _ { 2 }$ 、二恶英等烟气污染物在小区建筑间的浓度分布随着排烟高度和速度的增加而减弱，但由于气流分布产生涡旋的影响使得建筑物背风面污染物浓度较高。本文将计算结果与正态分布假设下的高斯烟羽模型计算结果进行比较，两者有较好的一致性。

关键词 垃圾焚烧；数值分析；二恶英；高斯烟羽模型中图分类号：X51 文献标识码：A 文献编号：

# Multiscale Simulation and Analysis on the Diffusion of

the Waste Incineration Flue Gas

CUI Peng-YiWU Zhi-GenTao Wen-Quan\* (College of Environmental Science and Engineering, Tongji University, Shanghai 20oo92, China)

Abstract The large number of secondary polutants,which were produced from waste incineration flue gas, would cause the highly admired waste incineration power generating project into questions.The CFD technology was applied to simulate the difusion characteristics of waste incineration flue gas from chimney,to investigate the flow and pollutant distribution at multiscale space conditions. The standard $k \cdot \varepsilon$ turbulence model and component transport model were adopted to evaluate the polltant distribution influence between buildings at downwind $1 . 4 \mathrm { k m }$ from discharge position with different exhaust height and velocity.It was found that the concentration distribution of flue gas pollutant, such as $\mathrm { S O } _ { 2 }$ and TCDD,decreased with the increase of exhaust height and velocity,and a higher pollutant concentration on the leeward of buildings was causedby the vortex induced from wind field.Finally, the analysis results of Gaussian plume model were found to be in a good agreement with the simulation results.

Key wordswaste incineration; numerical simulation; TCDD; Gaussian plume model

# 0引言

城市生活垃圾的主要处理方式有卫生填埋、堆肥和焚烧。其中，近30年中来发展起来的垃圾焚烧技术是目前较为经济有效的垃圾处理技术之一[1-3]。然而，垃圾焚烧会产生大量的二次污染，所生成的烟气中含有至今毒性最强的物质二恶英4。目前，全球二恶英的产生量几乎全部来自生活垃圾焚烧厂排放出来烟气[5]。

烟气从烟肉排出后扩散规律的研究主要包括理论分析、实验方法和数值模拟[6-10]。理论分析中最著名的是高斯烟羽扩散模型[11]，实验方法是一类依据观测资料的分析方法，其精度很大程度上取决于观测密度。CFD技术是近年来迅速发展起来的一种研究流动传质、传热与反应等的有效手段，在环境工程领域作为一种研究手段越来越受到人们重视[12,13]。与实验方法相比,CFD 技术具有经济、高效的特点，相比于理论分析，其能够求解更为复杂的流动扩散问题。本研究利用FLUENT软件，构建多尺度数值计算模型，研究垃圾焚烧产生的烟气经不同高度和速度排放之后，在大气中扩散传质的规律，对大气环境污染控制与评价具有一定指导意义。

# 1数学模型及求解

# 1.1几何模型与网格划分

如图1所示，计算区域为 $8 0 0 \mathrm { m } \times 8 0 0 \mathrm { m } \times 3 0 0 0$ $\mathbf { m }$ 长方体区域，前后两个正方形分别是计算区域的入口和出口。烟肉为直径 $5 \mathrm { m }$ 的圆柱，高为 $H$ ，在计算中 $H$ 取值为 $2 5 \mathrm { ~ m ~ }$ 、 $5 0 ~ \mathrm { m }$ 和 $1 0 0 ~ \mathrm { { m } }$ ；烟肉位于入口平面下风向 $4 0 0 \mathrm { m }$ 处，小区位于入口平面下游$1 . 8 ~ \mathrm { k m }$ 处，也就是烟肉下游 $1 . 4 ~ \mathrm { k m }$ 处，小区内建筑的尺寸如图1中放大部分所示。计算区域的选择考虑到烟肉排出的烟羽有充分发展的空间，不会受到计算空间四周边界的影响，保证计算区域的出口可以采用充分发展流动的边界条件。

![](images/7b313dd34e66b3937639ffab7f519a3b01730e54c8535e7ba3401b2612b80e92.jpg)  
图1计算区域

本模型计算区域较大，流动的特征尺度从整个计算区域的几千米到住宅小区的几十米，属于系统多尺度问题[14,15]。系统多尺度问题可以采用统一方程整场求解以及分层求解逐级细化两种方法，根据本文的具体情况采用整场求解的方法，在网格的划分上充分考虑了不同区域对网格疏密的要求和计算精度与求解速度之间的平衡。网格尺度从一米到几百米范围变化，在反映污染物排出的烟肉附近，污染物影响的小区周围以及排放源到小区之间污染主要经过的区域，采用较高的网格密度；在其他污染物很难到达的高空及烟羽影响较小的两侧采用较粗的网格。如图2所示，烟肉附近采用0.1-0.5米的分辨率的网格尺度，图3所示的小区及附近采用0.5-1米的网格尺度，而在其两侧及500米以上的高空网格尺度则在十到几十米不等。总体网格数在400万左右，网格利用Gambit软件生成。

![](images/419ba3b3b591f1e4a9252cb486deb25d85436b3663eed200492eff1bb540c9a5.jpg)  
图2烟肉及附近网格

![](images/b64571a015c3a2ef367e5ef6acf25760222aabc88c59951e016b4dbae496b9cd.jpg)  
Fig.1 Computational domain   
Fig.2 Chimney and nearby grid   
图3小区及附近网格  
Fig.3 Community and nearby grid

# 1.2控制方程与边界条件

将烟气排放的扩散传质过程视为不可压缩流体流动过程，由于烟气排放温度较高，对其密度影响较大，一般排放口的烟气密度 $\rho _ { \mathrm { s } }$ 与环境大气的密度 $\rho _ { 0 }$ 不同，在垂直方向的动量方程中要考虑到浮升力效应的影响。在其余方程中，可以用环境大气密度 $\rho _ { 0 }$ 代替烟气密度 $\rho _ { \mathrm { s } }$ ，控制方程由连续性方程、动量方程、能量方程、组分输运方程以及封闭上述方程的湍流方程即标准 $k \texttt { - } \varepsilon$ 两方程组成[14,15]。控制方程由商业软件FLUENT求解。

FLUENT软件中参数的设定：湍流施密特数$S c _ { \mathrm { t } }$ 取值0.7；系数 $C _ { \mu }$ 取值0.0845；本文不考虑烟气压力、温度以及其他组分变化对 $\mathrm { S O } _ { 2 }$ 和二恶英扩散系数的影响，将扩散系数视为常数，取为 $2 . 8 8 \times 1 0 ^ { - 5 }$ $\mathrm { m } ^ { 2 } / \mathrm { s } ^ { [ 1 6 ] }$ ；计算区域入口采用速度入口边界条件，大气边界层速度入口边界符合以下方程：$U / U _ { \mathrm { t h } } { = } l n ( z / z _ { 0 } ) / l n ( z _ { \mathrm { t h } } / z _ { 0 } )$ ；其中， $z$ 为距离地面的高度；$z _ { 0 }$ 为地面粗糙高度，设为 $0 . 3 \mathrm { ~ m ~ }$ ; $z _ { t h }$ 为烟肉排放口的高度； $U _ { \mathrm { t h } }$ 为烟肉排放口所在高度环境风速，设为 $4 . 5 \mathrm { m / s } ^ { [ 1 7 ] }$ 。入口环境大气温度为 $2 8 8 \mathrm { K }$ ，烟气等污染物质量浓度为0。烟气的入口设置在烟肉的底部，该处采用速度入口条件，该入口设置烟气温度为 $4 3 3 \mathrm { ~ K ~ }$ ， $\mathrm { S O } _ { 2 }$ 的质量浓度为 $8 . 9 9 \times { { 1 0 } ^ { - 4 } }$ ，二恶英的质量浓度为 $8 . 3 3 \times 1 0 ^ { - 1 1 }$ 。计算区域出口取在入口的对面，边界条件为 $\partial \varphi / \partial n = 0$ ， $\varphi$ 代表所有求解变量。计算区域顶部和两侧设为对称边界[17]，对称边界条件要求垂直该边界的速度分量的值为0，而其它标量及平行于该边界的速度分量的一阶导数为0。地面、小区建筑和烟肉表面为速度无滑移，物质无渗透的壁面边界。

# 2结果分析及讨论

本文在相同大气条件下，对垃圾焚烧烟气在相同排烟温度不同排烟高度和排烟速度条件下，研究了 $\mathrm { S O } _ { 2 }$ 和二恶英等污染物在大气中扩散的规律以及对下风向 $1 . 4 \mathrm { k m }$ 处居民小区的影响，并做了细致的分析。

# 2.1排烟高度对烟气扩散的影响

图4、图5表示在相同排烟速度（ $6 \mathrm { m / s } .$ ）条件下， $\mathrm { S O } _ { 2 }$ 和二恶英在 $z = 1 . 5 \mathrm { m }$ 和 $z = 2 4 \mathrm { m }$ 小区截面平均质量浓度分布。可以看出随着排烟高度的不断增加，小区居民生活范围内 $\mathrm { S O } _ { 2 }$ 和二恶英浓度明显降低，排烟高度从 $2 5 \mathrm { ~ m ~ }$ 、 $5 0 \mathrm { ~ m ~ }$ 到 $1 0 0 \mathrm { ~ m ~ }$ ，两种污染物质量浓度都有近一个数量级的减少，可见排烟高度的增加可以在很大程度上使得污染稀释扩散到高空大气，从而大大减弱对下游近地面附近的污染程度。

![](images/1002ec4f96f2a4f9dac88357e4fb1c7c03089f450c6243cc6916b3c1e12bc5f6.jpg)  
图 $4 \ : V = 6 \ : \mathrm { m / s }$ 下 $\mathrm { S O } _ { 2 }$ 平均质量浓度Fig.4 Average mass fraction of $\mathrm { S O } _ { 2 }$ at $V { = } 6 ~ \mathrm { m / s }$

![](images/05d07b617ed4828e0a957ccfe545bd38e333733c3907d5d782525ffd37605c0f.jpg)  
图 $5 V = 6 ~ \mathrm { m / s }$ 下二恶英平均质量浓度Fig.5Average mass fraction of TCDD at $V { = } 6 \mathrm { m / s }$

# 2.2排烟速度对烟气扩散的影响

图6给出了在相同排烟高度（ $\mathrm { 5 0 m } )$ 不同排烟速度条件下，小区建筑范围内 $\mathrm { S O } _ { 2 }$ 和二恶英在人呼吸截面（ $z = 1 . 5 \ : \mathrm { m } \mathrm { , }$ ）所达到的最大质量浓度。排烟速度的增加意味着单位时间污染物释放量增加，各点污染物的浓度值也应随之成比例增加；但排烟速度的增加会提高烟气上升的动量，烟气的抬升高度$\Delta H$ 和有效源高He $\scriptstyle ( H \mathbf { e } = H + \Delta H )$ 也将随之增加，根据高斯烟羽模型理论[11]，有效源高的增加有利于烟气中污染物的高空扩散，从而降低其对近地面的污染程度。因此排烟速度的增加对近地面污染程度有两面性。根据图6本文所建模型的情况分析可知，烟气的排放速度由 $6 ~ \mathrm { m / s }$ 、 $1 0 ~ \mathrm { m / s }$ 增加到 $1 5 \ \mathrm { m / s }$ $\mathrm { S O } _ { 2 }$ 和二恶英两种污染物对近地面小区的影响随着烟气排放速度的增加而减弱，说明了高空大气对烟气的稀释程度要大于烟气排放量的增加对近地面的影响程度，也进一步说明提高烟气排放的有效源高（包括增加烟肉的几何高度）有利于减弱烟气污染物对近地面的影响。

![](images/5b77b82461e7b35e856a8dfcbee903dafd1faa7a3d851d2fd26eba0f22f4e42f.jpg)  
图6不同排烟速度下 $\mathrm { S O } _ { 2 }$ 和二恶英最大质量浓度Fig.6Maximum mass fraction of $\mathrm { S O } _ { 2 }$ and TCDD atdifferent exhaust velocity

# 2.3楼宇间的街区峡谷对烟气扩散的影响

图7显示了楼宇间街区中 $\mathrm { S O } _ { 2 }$ 质量浓度分布的模拟结果。由图可见，小区建筑间与风主方向平行的街区 $\mathrm { S O } _ { 2 }$ 等污染物浓度要明显低于与来风主导方向垂直即建筑背风面的街区，这种现象与建筑物布置对环境风速度场的影响有关，从图8可以看出，建筑的背风街区产生明显的涡流，不利于新风量的更新，也不利于污染物的随风扩散稀释，造成污染物浓度积累，使得建筑背风街区局部空气质量明显下降。

![](images/73c3fa5673774477dffb4211a18092fceb84810659e321fe89683a20df035549.jpg)  
图 $7 \mathrm { S O } _ { 2 }$ 质量浓度在 $\mathsf { z } { = } 1 . 5 \mathrm { m }$ 截面分布 Fig.7Mass fraction on the plan at $\mathsf { z } { = } 1 . 5 \mathsf { m }$

![](images/d5d48e7e10ee7f5cbf8c28dd18983fcd6b8ae912729bf50a2410dbb1cbead7d1.jpg)  
图8街区竖直截面速度分  
Fig.8 Velocity vector distribution on vertical plan

# 2.4模拟结果与烟羽模型理论分析结果比较

在大气环境流场稳定，忽略横向、竖向流速及纵向弥散作用，对于有效排放高度为 $H \mathbf { e }$ 的连续排放点源，污染物浓度的空间分布符合连续排放点源的高斯模式[]。如图9 所示，本模型轴线 $y = 4 0 0$ $\mathrm { ~ m ~ }$ 近地面 $\mathrm { S O } _ { 2 }$ 质量浓度分布与高斯烟羽模型理论值有较好一致性。本文在污染排放几何高度为 $5 0 \mathrm { m }$ 排放速度 $1 0 ~ \mathrm { m / s }$ ，温度 $4 3 3 \mathrm { ~ K ~ }$ 等条件下，地面 $( z =$ $0 \mathrm { m } ) \mathrm { S } 0 _ { 2 }$ 质量浓度在 $2 \mathrm { k m }$ 左右达到最大，理论分析在 $1 . 8 \mathrm { k m }$ 左右为最大。由于地面轴线在 $x = 1 . 8 \mathrm { k m }$ 处受小区建筑群的影响，使得本模型近地面污染物浓度模拟与理论计算值之间存在一定差别。

![](images/fe2732af4d7098542ff72e3b0bbf36a1832721e985bb226dde079b9e6eb26ebb.jpg)  
图9 $\mathrm { S O } _ { 2 }$ 浓度分布理论与模拟值比较 Fig.9 Comparison between theoretical and simulation valuesof $\mathrm { S O } _ { 2 }$ concentration distribution

# 3讨论

本文中应用计算流体力学技术对生活垃圾焚烧产生的烟气污染物通过烟肉高空排放后，在大气环境中的稀释扩散过程和规律进行了多尺度数值模拟研究，计算在包含污染源排放点及其下风向影响小区在内的一个足够大的空间进行，研究了烟肉高度及排烟速度的影响。分析了不同条件下污染源（ $\mathrm { S O } _ { 2 }$ 、二恶英等污染物）在空间扩散的规律及在小区内分布特点，对于垃圾焚烧厂附近环境影响评价有一定的指导意义。本模型考虑的是在稳定的气象条件下，污染物随气流的扩散，但大气环境瞬息万变，局部气流变化具有随机性，因而对大气中污染物的扩散有很大的影响，也就是说烟气等大气污染物排放到大气中后，其运动扩散规律有很大随机性，如何把握这种规律也是以后研究的重点。

# 4结论

本文利用CFD 技术在稳态条件下对垃圾焚烧产生的烟气污染通过烟囱扩散的规律进行了多尺度数值模拟，采用湍流标准 $k - \varepsilon$ 两方程模型及组分输运模型，研究了在较大区域范围条件下，烟气在空间上气流分布和污染物分布；分析了不同排烟高度和排烟速度条件下对距离排烟地点1.4公里处的小区烟气污染分布的影响。研究表明 $\mathrm { S O } _ { 2 }$ 、二恶英等烟气污染物在小区中的浓度分布随着排烟高度和排烟速度的增加而减弱，由于气流分布产生涡旋的影响使得建筑物之间的背风街区污染物浓度较高。计算结果与正态分布假设下的高斯烟羽模型进行比较，两者有较好的一致性。

# 参考文献

[1] LIU Zhiqiang,LIU Zhihua,LI Xiaolin. Status and Prospect of the Application of Municipal Solid Waste Incineration in China[J].Applied Thermal Engineering, 2006，26（11、12):1193-1197   
[2] Assamoi B, Lawryshyn Y. The Environmental CompariSon of Landfilling vs. Incineration of MSW Accounting for Waste Diversion[J]. Waste Management, May 2012, 32(5):1019-1030   
[3] Johnke B. Waste incineration—An Important Element of the Integrated Waste Management System in Germany[J] Waste Management & Research,1992，10（4):303-315   
[4] Whysner J， Gary M W. 2,3,7,8-Tetrachlorodibenzo-p -dioxin Mechanistic Data and Risk Assessment: Gene Regulation, Cytotoxicity, Enhanced Cell Proliferation, and TumorPromotion[J]. Pharmacology& Therapeutics, 1996，71(1、2): 193-223   
[5] CHENG Hefa, HU Yuanan. Curbing Dioxin Emissions from Municipal Solid Waste Incineration in China: Re-thinking about Management Policies and Practices[J]. Environmental Pollution,2010,158（9): 2809-2814   
[6]Bornoff R B. A Numerical Investigation of the Interactions Between Adjacent Cooling Tower Plumes[D]. Uxbridge, UK: Brunel University,1997   
[7]Bornoff R B,Mokhtarzadeh-Dehghan MR.A Numerical Study of Interacting Buoyant Cooling Tower Plumes[J]. Atmospheric Environment , 2001,35:589-598   
[8] Overcamp T J,Ku T. Plume Rise from Two or More Adjacent Stacks[J]. Atmospheric Environment,1988,22 (4): 625-637   
[9]Gregoric M, Davis L R, Bushness D P. An Experimental Investigation of Merging Jets in a Cross-flow[J].ASME Journal of Heat Transfer,1982,104:236-240   
[10] Saathoff P, Stathopoulos T,Wu H. The Influence of Free Stream Turbulence on Near Field Dilution of Exhaust from Building Vents[J]. Journal of Wind Engineering, 1978, 77&78: 741-752   
[11] ZHANG Xiubao,GAO Weisheng, YING Longgen. Conspectus on Gas Environmental Pollution[M]. Beijing: China Environment Science Press,1989   
[12] Fimbres-Weihs G A,Wiley D E,Review of 3D CFD Modeling of Flow and Mass Transfer in Narrow Spacer-fiedChannelsinMembraneModules[J]. ChemicalEngineering andProcessing: Process Intensification,2010,49(7): 759-781   
[13] Blocken B, Janssen W D,van Hooff T. CFD Simulation for Pedestrian Wind Comfort and Wind Safety in Urban Areas: General decision framework and case study for the Eindhoven Universitycampus[J]. Environmental Modelling & Software,2012,30:15-34   
[14] TAO Wenquan, Numerical Heat Transfer[M] $2 ^ { \mathrm { n d } }$ ed. Xi'an: Xi'an Jiaotong University Press; 2010，1-6,337-359.   
[15] Versteeg H K, Malalasekera W. An Introduction to Computational Fluid Dynamics，The Finite Volume Method[M]. New York: Longman,1995   
[16] DII Y I. GIO T X ZHANGM 7. Determination nf Flie

Gas Multi-component Diffusion Coefficient[J], Industrial Safety and Environmental Protection.2009,35(10):21-23 [17]K.onig C S,Mokhtarzadeh-Dehghan M R.Numerical Study of Buoyant Plumes from a Multi-flue Chimney Released into an Atmospheric Boundary Layer[J]. Atmospheric Environment,2002 (36): 3951-3962