# 液氨温区VM-PT制冷机的数值计算研究

张通1,2 潘长钊1刘思学1周 远1,2 王俊杰1,2(1.中国科学院低温工程学重点实验室 (理化技术研究所)，北京100190;2．中国科学院大学，北京100049)

摘要本文对液氮温区Vuilleumier 耦合脉冲管（VM-PT）制冷机进行了数值计算研究。为了减小来自室温的漏热，将气库置于一级冷头之上。采用 SAGE 软件建立了数值计算模型，以无负荷制冷温度为目标函数对制冷机运行参数进行了优化。为了进一步了解制冷机的工作原理，研究了脉冲管制冷机内焓流、声功、熵流、压力波、体积流率及温度的沿程分布，并对其相位关系和可用能损失进行了分析。计算结果表明，该制冷机可在平均压力 $0 . 9 \mathrm { M P a }$ 、压比1.61、运行频率0.8$\mathrm { H z }$ 时得到3.69K的无负荷制冷温度，在4.2K时可提供 $1 6 . 2 4 ~ \mathrm { m W }$ 制冷量。

关键词液氮温区；VM制冷机；脉冲管制冷机；数值计算分类号：TK123 文献标识码：A 文章编号:0253-231X(2017)04-0690-0

# Numerical Study of VM-PT Cryocooler Operating at Liquid Helium Temperature

ZHANG Tong1,2 PAN Chang-Zhao1LIU Si-Xy ZHOU Yuan1,2 WANG Jun-Jie $^ { 1 , 2 }$ （20 (1. CASKey laboratoryof Cryogenics,Technical Instituteof Physicsand Chemistry，Beijing 100190,China; 2.University of Chinese Academx df Sciences，Beijing 10o049, China)

AbstractA detailed numerical study%f Vuillumier coupling pulse tube (VM-PT） cryocooler operating at liquid helium temperature presented in this paper. In order to reduce the heat leak from the room temperature ambitthe reservoir was located atthecoldend of the first stage. A numerical model of the cryoeooler was conducted by using the software SAGE. The operating parameters were optimized by taking the no-load temperature as the target function. In order to further study the coupling mechanism of the cryocooler, distributions of enthalpy fow,acoustic power, entropy flow, pressure wave,and volume flow rate are presented and discussed. Meanwhile, analyzes of phase relationship and exergy loss are also performed. A no-lad temperature of 3.69 K could be attained with a mean pressure of $0 . 9 \mathrm { M P a }$ , pressure ratio of 1.61, operating frequency of 0.8 Hz in the simulation and the cooling power at $4 . 2 \mathrm { K }$ is about $1 6 . 2 4 \mathrm { \AA } \mathrm { \textmu } \mathrm { \textmu }$ ：

Key wordsliquid helium temperature; VM cryocqoler; pulse tube cryocooler; numerical simulation

# 0引言

在低温超导、低温电子学、低温医学和空间技术等方面，液氮温区制冷机起着非常重要的作用。目前液氮温区制冷机主要有G-M制冷机、G-M型脉冲管制冷机以及高频斯特林型脉冲管制冷机。G-M制冷机和G-M型脉冲管制冷机采用氮气压缩机结合高低阀切换提供压力波动，不可逆损失导致其热效率较低，且需要定期维护[1]。同时，其体积过大的特点限制了它在空间领域的应用。液氮温区高频斯特林型脉冲管制冷机是近年来的一个研究热点，目前已采用二级到四级结构获得了液氮温度[2-4]，运行频率一般在 $2 0 { \sim } 5 0 \mathrm { H z }$ 左右。液氮温区制冷机一般要采用较小的颗粒状或球状磁性蓄冷材料填充蓄冷器，高频运行条件下，蓄冷器的流阻损失较大，效率较低。

VM制冷机是斯特林型制冷机的一种，和斯特林制冷机不同的是，它利用热压缩机进行驱动。理论上讲，VM制冷机具有和斯特林制冷机相同的效率。VM制冷机的运行频率一般低于 $5 ~ \mathrm { H z }$ ，其可采用较大粒径的蓄冷材料填充低温蓄冷器以减小流阻损失，可实现较高的蓄冷器效率。因此，研究液氮温区VM制冷机对发展高效液氮温区制冷机具有十分重要的意义。

在 $1 0 ~ \mathrm { K }$ 温区单级VM制冷机的基础上[5]，潘长钊等6提出了VM-PT 型制冷机，即在单级VM冷头上气耦合一级同轴型脉冲管制冷机。为了方便调节，采用了室温小孔-气库进行调相，并最终得到了 $4 . 4 \mathrm { ~ K ~ }$ 的无负荷制冷温度。但这种调相方式会引入来自室温的漏热，恶化一级冷头的性能，使得一级冷头温度偏高，进而影响无负荷制冷温度。同时，这种制冷机的耦合机理、相位关系等也有待于进一步研究。为了获得更低的制冷温度，本文开展了低温调相VM-PT制冷机的数值计算研究，将气库置于一级冷头之上以减小来自室温的漏热。为了对制冷机耦合机理和工作原理进行深入的了解并指导实验系统的设计，在对制冷机运行参数进行优化的基础上，本文开展了能流、相位及可用能损失分析，并对制冷机的性能进行了初步预测。

# 1制冷机结构

图1为低温调相VM-PT制冷机结构示意图。在单级VM制冷机的冷腔开一小孔，作为同轴型脉冲管制冷机的入口，这样，除了流动引起的损失外，脉冲管制冷机内的压力和 VM制冷机内基本相同。为了减小来自室温的漏热，脉冲管采用低温-小孔气库的调相方式。气库采用环形结构，置于一级冷，同时可作为脉冲管制冷机的冷屏。低温下宜布置阀门，因此小孔阀采用毛细管来代替

![](images/73caa8d621b40723b9113b80ecc65ca29c95f33730d3bf9696810f31fbf4f2c4.jpg)  
图1低温调相VM-PT制冷机结构图  
Fig.1 Schematic of VM-PT cryocooler with cold phase shifter

表1为制冷机初步设计参数，后续数值计算也按照此参数进行建模。其中，冷端蓄冷器采用两层方式进行填充，第一层填充 $4 5 \ \mathrm { m m } \ 2 0 0 \$ #不锈钢丝网，第二层填充 $8 0 \ \mathrm { m m }$ 直径 $0 . 4 { \sim } 0 . 4 5 ~ \mathrm { m m }$ 的铅球。脉冲管蓄冷器则全部填充直径 $0 . 2 { \sim } 0 . 2 5 ~ \mathrm { m m }$ 的 $\mathrm { E r _ { 3 } N i } .$

表1低温调相VM-PT制冷机主要结构参数Table1 Main structural parametersofVM-PTcryocooler with cold phase shifter  

<html><body><table><tr><td>部件名称</td><td>直径/mm</td><td>长度/mm</td></tr><tr><td>冷端排出器</td><td>24</td><td>190</td></tr><tr><td>冷端蓄冷器</td><td>23.6</td><td>125</td></tr><tr><td>脉冲管蓄冷器</td><td>外径18，内径8.9</td><td>85</td></tr><tr><td>脉冲管</td><td>8.5</td><td>85</td></tr><tr><td>毛细管</td><td>0.4</td><td>80</td></tr><tr><td>冷气库</td><td>外径51，内径 43</td><td>110</td></tr></table></body></html>

# 2数值计算模型

Sage软件是一款由美国GedeonAssociates创始人DayidGedeon开发的用于斯特林循环模拟的商用程序1995年正式命名为“Sage”，现在已经更新到第十一个版本。Sage 具有可视化界面，对每个部件单独建模，各个部件之间通过质量流、压力波和能量流来进行连接，可实现整机的模拟，并具有一定的优化功能。此外，Sage计算结果除了给出各个端面的物理量外，其solutiongrid文件还给出了各个节点上的计算结果，对其进行处理，可以得到各物理量的沿程分布，这对了解制冷机的工作原理十分有益[7]。本文采用Sage的Low-T coolerModel Class(深低温模块)对低温调相VM-PT 制冷机进行整机模拟，三个腔体及气库采用Genericcylinder 模块，排出器与蓄冷器整体采用 Constrained piston and cylinder 模块，换热器与连接管道采用 tube bundle 模块，室温热源和液氮槽采用 point heat source 模块，蓄冷器采用annular canister 模块，脉冲管采用compliancetube 模块。计算中，以无负荷制冷温度为目标函数，热腔温度为 $3 0 0 ~ \mathrm { K }$ ，中间腔温度为77K。

# 3计算结果与分析

# 3.1运行参数优化

数值计算中，首先对制冷机的运行参数进行了优化计算。图2给出了不同平均压力和运行频率下制冷机无负荷制冷温度的变化规律。增加平均压力和运行频率，质量流率会增加，蓄冷器做功能力增强，但同时蓄冷器损失也会增加，因此，平均压力和运行频率均存在最佳值。数值计算中，在运行频率$0 . 8 \mathrm { H z }$ 、平均压力 $0 . 9 \mathrm { M P a }$ 的运行条件下得到了3.69K的无负荷制冷温度，其在 $4 . 2 \ : \mathrm { K }$ 可提供 $1 6 . 2 4 \mathrm { m W }$ 的制冷量。值得注意的是，计算模型中未计算辐射漏热损失，而Sage软件对蓄冷器损失的计算结果比实验数值要小，因此实验中的最佳运行频率和最佳平均压力一般要比计算值略高。

![](images/3191d661c6e3cfad2b81c036eb7bb3062be26ad673cf32b129d4f0dd6fa81aae.jpg)  
图2运行参数对无负荷制冷温度的影响Fig.2 Influence of operating parameters on no-loadtemperature

# 3.2脉冲管制冷机内物理量分布

为了进一步分析低温调相VM-PT 制冷机的能量流动特性和耦合机理，本文在前述优化结果基础上，给出了脉冲管制冷机内关键物理量的分布情况。图3给出了脉冲管蓄冷器内气体温度的轴向分布规律。从图中看出，蓄冷器入口段具有较大的温度梯度，但其冷端部分温度梯度较小。在蓄冷器中部，工质的温度已经低于 $6 ~ \mathrm { K }$ 。因此在实验中，填充在此温度下比热大于 $\mathrm { E r _ { 3 } N i }$ 的 $\mathrm { H o C u _ { 2 } }$ 有助于改善制冷机性能。

![](images/23a01f53d8023e2a4cbf23f076f64a3499e83bb231fc432938d34c28c96f1a94.jpg)  
图3脉冲管蓄冷器气体温度分布 Fig.3 Distribution of gas temperature in pulse tube regenerator

图4给出了脉冲管制冷机内时均声功、时均焓流、时均熵流的分布情况。为了方便图形的绘制，将同轴型脉冲管示意为直线结构，并忽略了流向变化引起的声功和焓流的符号变化。若选择向右的方向为正，则冷端换热器出口至气库的声功和焓流为负号。

理想状态下，声功只在蓄冷器和调相机构内有所耗散，在其他部件中没有变化。从图4中的计算结果可以看出，声功依然主要消耗在蓄冷器和调相机构内部，但其他部件内也由于流动阻力损失有少量的消耗。根据热声理论[8]，消耗在蓄冷器内的声功会将热量不断的从冷端泵送到热端，而消耗在调相机构内的声功则主要起调节蓄冷器内部压力波和质量流相位的作用。

理想状态下，蓄冷器填料与工质之间无换热温差且填料热容远大于工质热容，无流阻损失和轴向导热损失，其时均焓流为零。但图4中流经蓄冷器的时均焓流并不为0，基本上为一定值。这主要是由于蓄冷器内流动阻力损失和不完全换热损失引起的，这部分焓流将直接影响制冷机的制冷量。由于制冷机内部各种损失引起的熵增，时均熵流沿轴向不断增大并趋于0。但在热端换热器内，由于向外界放热，熵流有一个减小的过程。

![](images/41fdc7649cc9a07f9f517a129c70b3a729c360bc4fed5a8c05fcec6bf43dc6e1.jpg)  
图4脉冲管制冷机内能量流分布  
Fig.4 Distribution of energy flow in pulse tube refrigerator

图5给出了脉冲管制冷机内压力波幅值和体积流率幅值的分布情况，从图中可以看出，在进入调相机构之前，压力波幅值基本保持不变，仅仅是由于流动阻力引起了一些减小。在气库内部，压力波幅值约为 $0 . 0 3 7 \mathrm { M P a }$ ，其压比约为1.07，远小于制冷机内部压比1.61，不会对制冷机性能产生影响。由于阻力的缘故，体积流率则沿轴向不断减小。

![](images/8796fb2cd91cf837d8067482f18f908d33dd056393b3f633c4b11021f1009220.jpg)  
图5脉冲管制冷机内压力波和质量流分布 Fig.5 Distribution of pressure wave and mass flow in pulse tuberefrigerator

蓄冷器的相位关系和惯性管－气库调相方式的相位具有很大的区别，更加接近于小孔－气库型调相方式[9]。因此，本文中虽然引入一段管道连接脉冲管热端和气库来进行调相，但由于其管径较小，运行频率较低，几乎没有惯性效应，只能起到阻力元件的作用。

对于气耦合型制冷机，两级蓄冷器之间除了能量流分配之外，还存在质量流的分配，两级之间的相位会相互影响。图6中冷端蓄冷器的相位关系与单级VM制冷机中的已有较大区别[11]，这会加大制冷机调相的难度。因此，相位调节是此制冷机性能改善的主要研究方向之一。

# 3.4可用能损失分析

参考热声发动机驱动的制冷机[12]，VM-PT制冷机中各部件可用能损失比例可按下式进行计算：

# 3.3相位分析

图6给出了低温调相VM-PT制冷机两级蓄冷器的压力波和质量流之间的相位关系图。由于制冷机内部压力波的幅值和相位基本保持不变，因此采用实轴来表示压力波。图6中向量与实轴的爽角表示了质量流和压力波之间的相位关系，负值表示压力波的相位落后质量流的相位，而向量的模表示了质量流的幅值。

![](images/97a8d99e7cfad1ec80146a60bee9699022eeb09ae75d48c11599a9be5937b5d9.jpg)  
图6两级蓄冷器压力波和质量流相位关系 Fig.6 Phase difference between pressure wave and mass flow in two stage regenerators

一般来说，为了获得较高的蓄冷器效率，压力波和质量流需要在蓄冷器中部达到同相[9]。但从图中可以看出，在脉冲管蓄冷器中部，质量流相位领先压力波接近50度。在如此大相位角的情况下，为了获得足够的声功，蓄冷器需要较大的质量流，这会使得蓄冷器的流动阻力损失增大，降低蓄冷器的效率。本文中所使用的调相机构最初是按照惯性管-气库调相方式设计的，但从图中可以看出，脉冲管

$$
\gamma = { \frac { E _ { \mathrm { l } } } { Q _ { \mathrm { h } } \left( 1 - { \frac { T _ { \mathrm { a } } } { T _ { \mathrm { h } } } } \right) } }
$$

式中， $E _ { \mathrm { l } }$ 表示各部件的可用能损失， $Q _ { \mathrm { h } }$ 表示热腔的吸热量， $T _ { \mathrm { h } }$ 表示热腔温度， $T _ { \mathrm { a } }$ 为中间腔温度。

图7给出了低温调相VM-PT制冷机中各主要部件可用能损失的组成。图7中， $A _ { \mathrm { f r i c } , } ~ A _ { \mathrm { Q w } }$ 和 $A _ { \mathrm { Q x } }$ 分别为流动阻力、不完全换热和轴向导热引起的可用能损失。从图中可以看出，在各蓄冷器中，可用能损失主要是由于不完全换热引起的，其次为轴向导热引起的可用能损失，而流动阻力引起的可用能损失相对较小在调相机构中，由于毛细管管径较小,气体流速较快，可用能损失主要是由于流动阻力引起的

![](images/b6859932b992763f4c7aa5f108f59013bbacdfcc640bba09fd7780340030d947.jpg)  
图7主要部件可用能损失比例Fig.7 Exergy lossratio of main components

# 3.5制冷量

图8根据计算结果给出了制冷机两级冷头的制冷量曲线。从图8中可以看出，一级冷头热负荷由0增加到0.2W时，无负荷制冷温度由 $3 . 6 9 \mathrm { K }$ 上升到$4 . 0 3 \mathrm { K }$ ，再增加至 $0 . 5 \mathrm { W }$ 时，无负荷制冷温度已没有明显变化。当二级冷头加一定热负荷时，也有类似的规律出现。这表明，该制冷机两级冷头在施加较小热负荷下相互影响较小，可以在液氮及液氢温区同时提供制冷量。

![](images/f07729727ce9a78b18d321f9defc1bf67c50e31427fd5415641fbf06b38b1fb1.jpg)  
图8制冷机制冷量曲线  
Fig.8 Cooling map of the cryocooll

社,2010 CHEN Guobang, TANG Ke. The Principle of Cryogenic Refrigerator [M]. Beijing:Science Press,2010   
[2] Olson J，Moore M,Champagne P. Development of a Space-Type-4-Stage Pulse Tube Cryocooler for Very Low Temperature [J]. Advances in Cryogenic Engineering, 2006,51:623-631   
[3] QIU Limin,CAO Qiang,ZHI Xiaoqin,et al. Operating Characteristics of a Three-stage Stirling Pulse Tube Cryocooler Operating around 5 K[J]. Cryogenics,2012, 52(7-9):382-388   
[4] QUAN Jia, LIU Yanjie,LIU Dong,et al.4 K High Frequency Pulse Tube Cryocooler Used for Terahertz Space Application [J].Chinese Science Bulletin,2014,59(27): 3490-3494   
[5] PAN Changzhao, ZHANG Tong, ZHou Yuan,et al. Experimental Study of One-stage VM Cryocooler Operating BelowBK[J].Cryogenics,2015,72:122-126   
[6] PAN Changzhao, ZHANG Tong, ZHOU Yuan, et al． A vel Coupled VM-PT Cryocooler Operating at Liquid Helium Temperature [J]. Cryogenics, 2016,77: 20-24   
[7] Gedeon D. Sage User's Guide [M]. Sage v8 Edition. Gedeon Associates,2011   
[8] Swift G W, Garrett S L. Thermoacoustics: A Unifying Perspective for Some Engines and Refrigerators [J]. Journal of the Acoustical Society of America,2003,113(5): 2379-2381   
[9] Radebaugh R. Development of the Pulse Tube Refrigeratorasan Efficientand Reliable Cryocooler [C]//Proceedings of Institute of Refrigeration,London, 1999-2000   
[10] Radebaugh R, Lewis M, LUO Ercang, et al. Inertance Tube Optimization for Pulse Tube Refrigerators [J]. AIP nference Proceedings,2006,823(1):59-67   
[11]张通,潘长钊,周远,等.单级VM制冷机的数值计算与实验 研究[C]//中国工程热物理学会学术会议工程热力学与能 源利用学术会议论文，2016 ZHANG Tong,PAN Changzhao, ZHOU Yuan et al. Numerical and Experimental Study of One-stage VM cryocooler [C]//Annual Conference of the Chinese society of Engineering Thermophysics, Engineering Thermodynamics and Energy Utilization, 2016   
[12] XU Jingyuan， HU Jianying， ZHANG Limin， et al. Effect of Coupling Position on a Looped Three-stage Thermoacoustically-driven Pulse Tube Cryocooler [J]. Energy，2015,93: 994-998

# 4结论

《工程热

本文利用 Sage软件对VM-PT 制冷机进行了数值计算研究。该制冷机由单级VM制冷机气耦合一级同轴型脉冲管制冷机组成。为了减小来自室温的漏热，制冷机采用低温调相方式进行调相。首先给出了各物理量如焓流、熵流、体积流、声功和温度的沿程分布，然后对制冷机相位关系进行了分析，结果表明该制冷机的相位关系与惯性管-气库调相方式有很大的区别，与小孔-气库调相方式类似。经过对运行参数的优化，制冷机可以在在平均压力 $0 . 9 \ \mathrm { M P a }$ /压比1.61、运行频率 $0 . 8 \mathrm { H z }$ 时可得 $3 . 6 9 \mathrm { ~ K ~ }$ 的无负荷制冷温度，在 $4 . 2 ~ \mathrm { K }$ 时有 $1 6 . 2 4 ~ \mathrm { m W }$ 制冷量。

# 参考文献

[1]陈国邦,汤珂．小型低温制冷机原理[M].北京：科学出版