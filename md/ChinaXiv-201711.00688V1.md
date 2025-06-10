彩色印刷

# 磁场作用下液态金属膜流铺展特性的实验研究

阳倦成1²，齐天煜²，刘佰奇²，倪明玖²(1．西安交通大学航天航空学院机械结构强度与振动国家重点实验室，陕西西安710049)(2．中国科学院大学工程科学学院，北京100049)

摘要本文采用自行搭建的一套液态镓铟锡回路，并通过合理地设计液膜生成装置，开展了考虑液膜出口流速、水平磁场强度影响的金属液膜铺展特性实验研究。实验中采用高速摄像法并引入测量微小位移的高精度激光位移传感器获得了大量的金属液膜厚度特征数据。实验结果表明：金属液膜的波动特性随着Re数的增加而逐渐增大，波动从二维波转变成三维波，且高频率的波动逐渐占主导地位，而磁场的增强具有使液膜表面波趋于稳定的效果。

关键词金属液膜；磁流体力学；表面波动；铺展性中图分类号：0361.3 文献标识码：A

# Experimental Study on Spreading Characteristics of Liquid Metal Film under

# Influence of Magnetic Field

YANG Juan-Cheng1,2QI Tian- $\cdot \mathrm { Y u } ^ { 2 }$ LIU Bai-Qi²NI Ming-Jiu2 (1.StateKeyLaboratoryforStrengthandVibrationofMechaicalStructures,SchoolofAerospace,Xi'anJiaotongUniversity,ian ShaanXi710049，China; 2.School of Enginering of Science，University of Chinese Academy of Sciences，Beijing100080， China)

Abstract:In the present paper, we build a home-made liquid GaInSn loop and design a suitable liquid film generator to conduct the spreading characteristics of liquid film flows with the influence of inlet velocity and magnitude of magnetic field. The high-speed camera and high precision laser displacement sensor are used to get plenty of thickness data on liquid film.Experimental data show that with the increase of Re number, the fluctuation of liquid film surface is increased,the surface waves change from 2D model into 3D model, the high frequency fluctuation plays the leading role,while the increase of magnitude of magnetic field reduce the surface waves,and stabilize the film flows.

Key words liquid metal film; magnetohydrodynamic; surface wave; spreadability

# 0前言

液体的薄膜流动作为自然界中一种十分常见的流动现象受到学术界的广泛关注，如雨水流过窗户等，其流动的稳定性直接影响了液膜在固体壁面的铺展。Nusselt首次通过理论分析的方法研究了光滑壁面的液膜流动，获得了基于表面光滑层流并忽略气相作用力假设的液膜速度厚度解析解[。Kapitza父子[通过简单的实验观察到不稳定的表面波动流动以及液膜表面孤立波等复杂的液膜流动现象，向世人展示了液膜流动中所蕴含的丰富流动形态，吸引大量学者开始对其进行实验和理论研究。随后的近一个世纪以来，学者们从实验和理论研究方面对液膜流动开展了大量的工作，主要集中在分析液膜流动形态与流动参数的关系、液膜传热性能与液膜流动形态关系等。这些研究为膜流在相关学科的应用(如工程热物理学科的膜流冷却、材料学科的薄膜制备和镀膜、化学学科的蒸馏等)打下了坚实的基础。

然而，目前大量膜流相关研究的流动介质主要为常规流体如水、乙二醇等非导电液体，考虑的影响因素也仅有温度、重力、固体表面结构等，对于近些年发展起来的磁约束核聚变实验堆中涉及的液态金属膜流研究甚少。在该实验堆中，均匀、大面积铺展的液态金属锂膜流动被认为是面对等离子第一壁的最佳材料，但高温液态金属在核聚变堆中复杂强磁场环境下流动将受到洛伦兹力的作用而无法形成稳定流动，这种由磁场影响下流动现象的基本物理解释如下：高导电性的液态金属在磁场环境中流动时会因切割磁力线而产生感应电流，并进一步诱导产生洛伦兹力，该力将反作用于流动进而影响基本流。膜流流动本身的复杂性使得对应产生的洛伦兹力也较为复杂，进而增加了磁场环境下金属膜流研究的难度。其流动所产生的一系列现象、流动的不稳定特征也将与常规膜流完全不同，亟需从理论、数值模拟和实验方面开展大量的研究。

在理论分析方面，对磁场下的金属液膜流动稳定性的研究仍采用常规的线性稳定性和非线性稳定性分析方法。如Hsiehi和Ladikov[iv采用线性稳定性方法对横向磁场中忽略表面张力效应的液膜流动进行稳定性分析，结果显示：磁场耦合作用下的液膜流动相比Yih 等研究的无磁场下的液膜流动更为稳定。而 Gordeev 等[vi]、Korsunsky [vi的研究发现电场和磁场的耦合作用能控制流动的稳定和失稳，但这种说法仅存在理论中，未得到相应的实验验证。Mukhopadhyay 等[vi基于小磁雷诺数假设采用线性和弱非线性稳定性分析定量研究了中等雷诺数下电磁场对金属液膜流动的影响。线性稳定性分析结果表明磁场能使液膜流动稳定，电场对液膜流动稳定性的效果由其方向决定；而非线性稳定性分析却表明只有磁场对液膜流动稳定性有较大影响，电场对液膜流动稳定性影响非常小。

在数值模拟方面，运动的导电流体在磁场中所受到的作用力主要是通过求解电势方程或者磁诱导方程来获得。采用电势方程求解具有精确度高的特点，但由于忽略诱导磁场的影响，只能计算磁雷诺数较小的工况；而采用磁诱导方程能计算较大磁雷诺数的工况，但该方法边界条件较难处理，求解精度相比较低。Gao 等ix和 Huang 等x分别从二维和三维两个角度采用磁诱导方程求解磁场下的金属流体液膜流动，并采用VOF方法对液膜界面进行捕捉。研究表明采用这种方法能在一定程度上获得小Hartmann(Ha，电磁力和粘性力的比值)数(20 左右)下与实验结果有一定吻合的液膜流动特征，如液膜的波动以及液膜与槽道侧壁脱离的现象[xi]。在高Hartmann数研究方面,倪明玖等[xixi]发展了基于电势方程求解的相容守恒格式及软件平台HIMAG，成功地模拟了Hartmann数高达 ${ 1 0 } ^ { 4 }$ 的MHD 流动。目前，这种格式在全世界范围得到了广泛的应用。最近，许增裕等[xiv通过数值模拟研究了入口速度、入口膜厚、底壁宽度、壁面粗糙度对横向强磁场中金属锂膜流的影响，并初步给出了MHD稳定性的物理机制。然而，动量方程中电磁力项的加入极大地增加了方程的求解难度和计算量，使得与磁流体相关的理论分析和数值模拟进展较为缓慢。

在实验方面，UCLA的Abdou 教授带领的研究小组[xixv.xvi采用普通光学照相和超声波技术开展了一系列金属流体在磁场下的液膜流动实验研究。研究结果表明磁场对液膜流动的稳定性有较大影响，磁场中液膜由于受到电磁力的作用而产生沿流动方向逐渐变厚、流动阻力增大、流动与槽道侧壁分离且不能完整覆盖槽道底壁面的溪流等现象。当磁场强度较大 $( { > } 2 \mathrm { T } )$ 时，液膜流动表面会出现不稳定的波动现象。但由于测量手段的限制，他们并没能精细地获得各种不同条件下金属液膜波动的发展情况，也没有给出抑制磁场中液膜流动出现MHD不稳定性的方法。西南核物理研究院(SWIP)许增裕研究员带领的研究小组[vi,xvixix]基于已建成的液态金属回路开展了 $\mathrm { N a } ^ { 2 2 } \mathrm { K } ^ { 7 8 }$ 合金和镓铟锡合金的射流/膜流实验研究，获得了MHD 影响下的射流/膜流的流动形态。同时，实验结果表明非均匀磁场(2T左右)的作用使得射流射程变短，截面积变大，连续射流的长度变长。但实验中并未观察到UCLA团队所获得的射流在穿越横向磁场的时候所出现的射流崩溃效果[xvi]。而且SWIP 的实验中仅采用高速相机拍照获取膜流/射流的基本形态，因此也无法定量地研究膜流射流的详细流动特征。近期，日本大阪大学研究团队基于已搭建的液态锂回路开展了具有自由表面的锂膜流实验研究，验证了接触探针测厚法[x]、激光反射测厚法[xxi和高速摄像测速法[xxi]在较厚的高速（24号 $( 5 { - } 1 5 \mathrm { m / s } )$ 液态锂膜流动测量中的精确性，并获取了无磁场环境下高温锂膜的一些流动特征，但这些测量方法在磁场环境下测量的精确性还有待进一步的验证。本课题组基于已经搭建的液态镓铟锡回路开展了膜流初步实验，并通过可视化方法获得了铺展性较差的膜流基本形态以及磁场对膜流铺展形态的影响[xi]

尽管在实验、理论和数值模拟方面对磁场下的金属液膜流动已有一些研究，对磁场下液膜流动的大体特征有所把握(主要指液膜变厚、流动受阻、液膜的流动稳定性会受到影响等)，然而由于目前已开展研究有限以及其本身的复杂性，学术界对其的认识仍然匮乏。特别在实验方面，针对常规液膜流动一些测量技术(特别是光学测量方法)已无法适用于对液态金属膜流特征的测量，目前还未有一种对磁场下液态金属膜流较为精确的测量方法，因此相关精确的实验数据也极为缺乏。

本文在之前研究的基础上，进一步对膜流生成段结构进行了优化，采用高速相机可视化方法和激光位移传感器对磁场环境下的膜流流动进行定量的测量，获得了磁场影响下的金属液膜更为详细的流动特征。本文结构如下：第一部分介绍金属液膜产生的实验回路、磁场环境、实验测量方法及可靠性分析，第二部分主要介绍采用这两种方法所获得的实验结果及相关分析，第三部分对本实验所得到的结果进行总结，并展望后期所需开展的工作。

# 1 实验系统

实际磁约束聚变堆中用的液态第一壁为金属锂，然而由于实验室环境下操作液态锂的危险性，其并不适合开展前期的测量方法验证等基础研究。而电导率与锂类似、具有较小毒性、室温下为液态的镓铟锡合金被认为是开展液态金属相关基础研究的首选液体之一。以镓铟锡为流动介质，本实验室搭建了一套液态镓铟锡回路系统，用于开展液态金属的相关流动基础研究。

![](images/f1180e5cd1d39ae26d159201ea2c9abe9920153516732a6c987dd1877bad40bc.jpg)  
图1液态金属回路实物图  
Fig.1 Photo of liquid metal loop

# 1.1 实验回路介绍

图1为GaInSn液态金属回路实物图。该回路主要包括液态金属储存罐、循环罐、标定罐、电磁泵、电磁流量计、换热器、液膜生成结构、液膜铺展段、电磁铁所形成的强磁场、不锈钢管、波纹管、阀门等。由于液态镓铟锡易氧化而形成杂质，整个回路在运行过程中必须保证较低的氧含量以及惰性气体环境。

# 1.2实验测量方法介绍及误差分析

通过对已用于常规液膜流动测量方法进行调研，充分考虑金属流体不透明、易被氧化、磁场会对普通电子元件产生干扰等特性，寻找了两种适用于本实验液膜流动特征测量的手段，分别对液膜表面整体轮廓和不同时刻某一点液膜精确厚度进行测量。

图2为金属液膜生成实验段以及相应的测量方法示意图。整个实验段液膜铺展段内部空间高度为$1 8 0 \mathrm { m m }$ ，长度为 $8 0 0 \mathrm { m m }$ ，宽度(垂直于纸面方向)为$6 0 \mathrm { m m }$ ，液膜的出口处厚度可调节，为 $0 { - } 2 0 \mathrm { m m }$ ，液膜流动方向与水平方向的倾斜角 $\theta$ 也是可调的参数，实验段底板材质为有机玻璃。整个实验段插入气息间距为 $8 0 \mathrm { m m }$ 的均匀水平磁场中，磁场方向与纸面垂直且同时与流动方向垂直，磁场强度为0-2T且连续可调，整个液膜在该种磁场环境中流动。由于实验段仅在上部开有透明的观察窗，因此所有的测量方法都是从上面进行操作的。示意图中描述了两种测量方法：采用高速相机的可视化方法(约克公司生产的PhantomV341结合光源)和采用激光位移传感器(基恩士LJ-V7200)测液膜表面轮廓的方法。

![](images/60008efd37e5ed4c1f14ac80c0df26be82814d35b1e66b1305582939245cb53f.jpg)  
图2液膜实验段以及测量方法示意图

对于液膜的测量，采用高速相机主要是从定性上获得液膜的整体铺展宽度和液膜表面信息，而采用激光位移传感器则能从定量上获得液膜的厚度变化信息。激光位移传感器的测量误差大小主要受被测面对激光的反射的影响。对激光的反射越严重，位移传感器接收到的漫反射信号越弱，测量的结果误差越大。

![](images/05b8fa31e0937c2601e61aa1b1a3c13aa3daafeba045b43076276bb7939caf3d.jpg)  
Fig.2 Sketch of liquid film test section and corresponding measurement methods   
图3液膜平均厚度测量结果误差棒图  
Fig.3Error bars of the measured average film thickness

正式实验前，我们通过一个简易的测量方法来验证线激光位移传感器测量厚度的精确性：通过设定不同的液态金属膜厚值，采用位移传感器测量液膜的厚度，然后将测量值与实际值进行对比，对比结果如图3所示。从该图可以看出，对于静止的液膜，膜厚测量的误差较小，实验测量的误差均在 $10 \%$ 以内，而且对于较薄的液膜测量的精度越高。

# 2 实验结果与讨论

基于液态镓铟锡回路以及安装在回路中的实验段，本文开展了大量不同工况下的膜流实验，并用前一节中所描述的实验方法对膜流特征进行了详细的测量，分析了膜流出口流速、磁场强度对膜流流动特征的影响，具体实验结果及讨论如下：

# 2.1金属液膜表面形态

金属液膜的表面形态主要通过采用高速相机获得。实验结果如图4所示。

图4上部对应的四个子图为不同流速(Re)下液态金属膜流的表面基本形态。图中给出的结果均为流动达到稳定后的结果。图4上部的(a)到(d)四个图对应的流动Re数逐渐增大，从图中可以看出：在较小的流动Re数工况下 $( \mathrm { R e } { = } 1 0 8 0 . 7 )$ ，液膜表面较为光滑，只能看到很小的波纹；随着Re数的增大，液膜表面出现了明显的条纹，且条纹沿流动方向呈现抛物线形，类似于上游液体推动下游液体运动的二维滚动波；随着流动Re数的进一步增大，金属液膜表面的波纹变得更为复杂，由水平条纹的波转化成斜条纹交错分布的三维波，且从光线亮度在液膜表面的分布也可以看出波动的幅值也有所增加。值得注意的是，在Re数大于5079.5时，液膜位于下游10cm左右的位置处出现了很小的一部分未铺展区域，这有可能与该位置处侧壁面的粗糙情况有关。

当金属液膜流动引入与流动方向垂直的磁场时，磁场的作用会使得流动产生变化。图4下部对应的四个子图为不同磁场强度下固定流动Re数的的液膜表面流动特征(磁场强度从左至右依次增强)。为了定量描述电磁力与粘性力相对大小，这里通过采用 $\mathrm { H a } ( \mathbf { H } \mathbf { a } = { B L } _ { \sqrt { K / \mu } }$ ，其中B为磁场强度，L为特征长度，这里为液膜的厚度， $\kappa$ 为液态金属的导电率， $f ^ { \prime } _ { 2 } ( x ) = \frac { \sqrt { 3 } } { 2 }$ 为液态金属的动力粘度)数来进行定义。从图4下部的四个子图可以看出，液态GaInSn流过有机玻璃板时，对于固定 $\mathrm { R e } { = } 3 4 5 8 . 4$ ，随着 $\mathrm { H a }$ 数增加液膜表面波动发生明显的变化：对于 $\mathrm { H a } { = } 3 1$ 时，液膜表面波的宽度变窄，表面波的幅度增加，且随着Ha数的进一步增加，表面波宽度越来越小，往中心处靠拢。从刻度尺上可以看出，表面波的波长也相应地增加。

金属液膜流动在磁场的作用下产生上述现象的主要原因如下：流动的液态金属在磁场中会产生感应电流，且在液膜流动界面中心位置电流方向向上，则产生与流动方向相反的洛伦茨力，进而抑制液膜的波动；其次，对于以有机玻璃为底壁的液膜流动而言，其流动的自由表面以及底壁均为非导电边界，磁场环境下的液膜流动产生的电势线完全在膜流内部闭合，这一现象与本课题组之前开展的不锈钢底壁的液膜流动完全不同[23]。

![](images/94825f849e29913ef1e73d4c6c66e10922b3c9b7e0746efde03781e09082b5d5.jpg)  
图4金属液膜在有机玻璃底板上的流动形态随Re数和Ha数的变化

Fig.4 The flow paterns ofliquid metal film flow on the organic glass surface varied with Re number and Ha number

然而，由于相机拍摄角度所引起的图像变形可能引起一些视觉误差，为了进一步说明上述结果，本文接下来的部分将从位移传感器测量液膜厚度变化结果进行定量的分析。

![](images/4b5711451f6872696dcdf8e3406539ee466cd180c066aa2d1a573df64973bc81.jpg)  
图5固定点处不同Ha数下液膜厚度波动随时间演化 Fig.5 The fluctuation of film thickness varied with time for different Ha number at fixed point

# 2.2液膜表面统计特征

上一节的可视化数据从定性上把握了流动 Re数和Ha 数对液膜表面波动的影响，为了进一步开展定量研究，本节对实验过程中所获取的大量的液膜厚度实验数据分析，对这些数据的分析将有助于

更好地把握液膜的特征。

图5给出了三种不同情况下测量位置靠近边缘处的固定点液膜厚度随时间的变化。从该图中可以看出，对于同一Ha数不同Re数工况，较大Re数的工况下液膜的波动现象更为明显；当Re数不变时，Ha数增大(磁场强度增大)使得液膜厚度波动变缓，且液膜的厚度明显增加，增加近 $1 \mathrm { m m }$ 。

# 3结论

以核聚变托克马克装置中的液态锂膜如何均匀稳定形成为研究背景，本文主要研究了磁场作用下液态金属的铺展特性。实验中采用液态GaInSn作为金属液体开展了大量的研究，并采用高速摄像和激光位移传感器对膜流的特征进行了实验测量，随后对大量实验结果进行了详细的分析，得到的主要结论如下：

(1)高速相机的可视化结果表明随着流动Re数的增加，具有较大表面张力的液态镓铟锡表面波动性增强，从二维波动向三维波动转化，然而磁场的引入使得表面波动明显减弱，且随着磁场的增强，表面波的抑制效果越明显；

(2)采用激光位移传感器的定量测量进一步验证了可视化方法得到的上述结论，同时，定量的膜厚数据也表明：由于受到MHD阻力的影响，磁场作用下液膜的厚度有明显的增加;

(3)初步的实验结果表明文中两种测量方法的结合使用能获得磁场环境下液态金属膜流的基本流动特征，后期需基于这两种方法开展大量的实验以获取更为丰富的液态金属膜流原始实验数据。

# 参考文献

[1]NusseltW.DieOberflachenkondesation Des Wasserdamffes the Surface Condensation of Water [J]. Zetrschr. Ver. Deutch. Ing.,1916,60: 541-546.   
[2]Kapitsa P L, Kapitsa S P. Wave Flow of Thin Liquid Layers [J]. Zh.Eksp. Teor. Fiz.,1949,19:105-120.   
[3]Hsieh D Y. Stability of a Conducting Fluid Flowing down an Inclined Plane in a Magnetic field [J]. Physics of Fluids (1958-1988), 1965,8(10): 1785-1791.   
[4]Ladikov Y P. Flow Stability of a Conducting Liquid Flowing down an Inclined Plane in the Presence of a Magnetic Field [J]. Fluid Dynamics,1966,1(1):1-4.   
[5]Yih C S. Stability of Liquid Flow Down an Inclined Plane [J].Physics of Fluids,1963,6(3): 321.   
[6] Gordeev Y N,Murzenko V V. Wave Flows of a Conducting Viscous Fluid Film in a Transverse Magnetic Field [J].Journal of Applied Mechanics & Technical Physics,1990,31(31):431-435.   
[7] Korsunsky S.Long Waves on a Thin Layer of Conducting Fluid Flowing Down an Inclined Plane inan ElectromagneticField[J].EuropeanJournalof Mechanics - B/Fluids,1999,18(2):295-313.   
[8]Mukhopadhyay A, Dandapat B S,Mukhopadhyay A. Stability of Conducting Liquid Flowing Down an Inclined Plane at Moderate Reynolds Number in the Presence of Constant Electromagnetic field [J]. International Journal of Non-Linear Mechanics,2008,43(7):632-642.   
[9]Gao D, Morley N B, Dhir V. Numerical Study of Liquid Metal Film Flows in a Varying Spanwise Magnetic Field [J].Fusion Engineering and Design,2002,s 63-64(12): 369-374.   
[10] Huang HL, Ying A,Abdou M A. 3D MHD Free Surface Fluid FlowSimulation Based on Magnetic-Field Induction Equations [J]. Fusion Engineering and Design, 2002, s 63-64(02):361-368.   
[11] Narula M, Ying A,Abdou M A. A Study of Liquid Metal Film Flow, Under Fusion Relevant Magnetic Fields [J]. Fusion Science and Technology, 2005,47(3):564-568.   
[12] Ni M J,Munipalli R,Morley N B,et al.A Current Density Conservative Scheme for Incompressible MHD Flows at a Low Magnetic Reynolds Number. Part I: On a Rectangular Collocated Grid System [J]. Journal of Computational Physics, 2007,227(1):174-204.   
[13] Ni M J, Munipalli R, Huang P, et al. A Current Density Conservative Scheme for Incompressible MHD Flows at a Low Magnetic Reynolds Number. Part II: On an Arbitrary Collocated Mesh.Journal of Computational Physics,2007,227(1): 205-228.   
[14] 张秀杰，潘传杰，许增裕．聚变堆液态第一壁膜流 MHD 流动及其稳定性机制研究[J].核聚变与等离子 体物理,2013(4):289-296. Zhang X J, Pan C J, Xu Z Y. Liquid Metal MHD Film Flow and its Stability Mechanism for the Liquid First Wall of fusion reactor [J]. Nuclear Fusion and Plasma Physics. 2013(4): 289-296.   
[15] Morley N B，Burris J. The MTOR LM-MHD Flow Facility， and Preliminary Experimental Investigation of Thin Layer,Liquid Metal Flow in a I/R Toroidal Magnetic Field [J]. Fusion Science and Technology, 2003, 44(1):74-78.   
[16] Ying A Y, Abdou M A, Morley N, et al. Exploratory Studies of Flowing Liquid Metal Divertor Options for Fusion-Relevant Magnetic Fields in the MTOR Facility [J].Fusion Engineering and Design, 2004,72(1-3):35-62.   
[17] Xu Z Y, Pan C J,Kang W S. Experimental Investigation on MHD Instabilities of Free Surface Jet and Film Flow forLiquid Metal Divertor/Limiter Options[C]/. Proceedings of 24th Symposium on Fusion Technology, Warsaw, Poland. 2006.   
[18] Zhang X J, Xu Z Y,Pan C J. MHD Effect of Liquid Metal Film Flows as Plasma-Facing Components [J]. Plasma Science and Technology,2008,10(6):685-689.   
[19] 许增裕，潘传杰，康伟山,等．几种液体金属自由表面 的 MHD 不稳定性实验研究[J]．核聚变与等离子体物 理,2008,28(4):289-292. Xu Z Y, Pan C J, Kang W S. Experimental Investigation on MHDInstabilities ofFree Surface Jet and Film Flow for Liquid Metal Divertor/Limiter Options [J]. Nuclear Fusion and Plasma Physics, 2008, 28(4):289-292.   
[20]Okita T,HoashiE,Yoshihashi S,et al.Certification of ContactProbe Measurement of Surface Wave ofLi Jet for IFMIF [J].Fusion Engineering and Design,2015,98: 2050-2053.   
[21]Yoshihashi S,Masaoka T,Hoashi E,et al．Laser Reflection Measurement on Liquid Lithium Flow Surface [J].Fusion Engineering and Design, 2016,102: 108-111.   
[22]Sugiura H,Kanemura T,Yoshihashi-Suzuki S,et al. Experimental Study on Wave Propagation Behavior on

Free Surface of Lithium Flow for IFMIF [J].Journal of Nuclear Science and Technology,2011,48(9): 1230-1237. [23] Yang JC,Qi T Y,Ni MJ, et al. Flow Patterns of GaInSn Liquid on Inclined Stainless Steel Plate Under a Range of Magnetic Field [J].Fusion Engineering & Design,2016, 109-111:861-865.