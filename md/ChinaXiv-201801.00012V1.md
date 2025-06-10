# 一种新型旋转风能系统中聚热棚的模拟和实验研究

张铭旭 顾兆林 罗昔联 苏军伟 段翠娥（西安交通大学人居环境与建筑工程学院，西安710049）

摘要：自然界中的尘卷风蕴含的较大能量，据此提出的一种新型类尘卷风旋转风能系统已证实能够形成稳定旋转风场。带有预旋导流叶片的太阳能聚热棚是该系统中提供热源产生旋转气流的核心部件。本文通过数值模拟结合实验研究的方法，改变聚热棚模型的尺寸参数(聚热棚半径、叶片入射角度)和加热温差，模拟得到不同条件下出口处旋转风场特征风速值的变化规律，选取出适合的聚热棚入射角度；此外，通过模拟和实验结果与相似理论综合分析得出该入射角度下聚热棚尺寸与特征风速值在不同加热温度下的曲线关系图，并给出符合火星气候条件的同类曲线，为合理预测该系统结构及运行参数，以及更进一步太空中的应用前景提供重要参考。

关键词：旋转风能系统；聚热棚；数值模拟；实验研究；相似理论中图分类号：TK513 文献标识码：A

Numerical Simulation and Experimental Test on the

# Solar-energy-collecting Shed in a New Whirlwind Energy System

ZHANG Ming-Xu GU Zhao-Lin LUO Xi-Lian SU Jun-WeiDUAN Cui-E (School of Human Settlements and Civil Engineering, Xi'an Jiaotong University, Xi'an 710049, China)

Abstract: Dust devils in nature usually contain abundant wind energy, a new dust-devil-like whirlwind energy system has been proposed which could generate stable swirling wind. A circular solar-energy-collcting shed with pre-rotation vanes has been devised to generate the whirlwind flow by heating the air inflow into the shed.The effects of geometrical parameters(shed radius and air inflow incident angle)and temperature differences on the whirlwind characteristic velocities were evaluated by numerical simulation and experimental test. With the distribution and trend we could obtain the optimal incident angle.By simulating the cases with this incident angle,together with the similarity analysis, we could summarize the confines of the solar-energy-collcting shed size under different heating temperature diferences,which could help to choose the optimal structural and operating parameters for the system. In addition,the confines obtained from the initial conditions on Mars also draw a future application prospect of the system working in space.

Key words: whirlwind energy system; solar-energy-collecting shed; numerical simulation; experimental test; similarity analysis

# 0引言

近年来，随着传统化石能源危机和环境污染问题的日益加剧，人们不断加强在风能、太阳能、核能、潮汐能及地热能等各种可再生能源利用技术方面的研究力度，与此同时，一些新型的可再生能源利用技术的研究也逐步引起科研人员的重视。

尘卷风，这一自然界中存在的特殊天气现象给我们以启示。尘卷风是一种具有较高温低压核心和较短生命周期的旋转气团。尘卷风发生于大气对流边界层内，其直径能达到十几米至几十米，近地面的水平速度可达到 $5 \mathrm { m / s }$ ，垂直速度达到 $1 5 \mathrm { m / s }$ ，在尘卷风内核附近的最大风速值能达到 $2 5 \mathrm { m / s }$ ，可将地面沙尘碎屑等物体扬起，蕴含着可观能量[1-3]。根据已有研究表明[4]，尘卷风的形成是由于热地面对上方紧贴空气进行加热，造成了一种不稳定状态，即一层热空气之上覆盖着一层冷空气；由于空气不能整层的翻转，在上升对流集中处就发育小型的热气囊一热对流胞，同时周围的风给热对流胞以一定的角动量；随着热对流胞的上升，近地空气向热胞处汇聚，补充热空气上升造成的空缺，角动量随着气流的汇聚而加强，在热胞底部的中心部位形成尘卷风，形成尘卷风的必要条件为地面的加热和环境中空气的初始涡量。

众所周知，太阳能光伏发电是现在应用较广泛的清洁能源利用方式，其工作原理是通过太阳能电池板将太阳能转化为电能。但是，在转化过程中，太阳能电池板转化效率不到 $2 0 \% ^ { [ 5 ] }$ ，太阳能光伏电池板的温度也过高，甚至达到 $1 0 0 ^ { \circ } \mathrm { C }$ 以上[，大部分能量以余热的形式被浪费，所以针对太阳能余热的收集利用所进行的研究工作也正进一步展开[7,8]。

基于以上两点，结合已有研究中低温太阳能集热产生热浮力射流的概念[9]，本文提出一种新型的太阳能光伏-旋转风能利用系统，该系统基于自然界中尘卷风的形成机制，人为的满足形成旋转风的条件及提供热源和初始环境涡量，形成稳定的旋转热浮力射流即旋转风场，探寻该旋转风能系统的利用价值，该系统可与太阳能光伏系统复合使用，将电池板作为聚热棚，利用其预热提供热源。

# 1系统介绍

该系统的结构和运行示意图如图1所示，通过设置内侧带有预旋导叶片的聚热棚装置为气流提供初始涡量，聚热棚的上表面可以排布太阳能电池板，电池板实现常规的光伏电能输出，余热用以形成并维持旋转风的热源。系统运转时，棚内空气被加热后向上运动，经过预旋导叶片的预旋从中部出口以旋转风的形式流出，该流动本质上是一种热浮力射流，随着气流流出，外界空气进入系统，重复以上过程，产生稳定的旋转风场。

![](images/6a66f60ab7c33867956379b775f325d34f0c6ce395765444b016034b94905646.jpg)  
图1系统运行示意图  
Figure 1 System operation description

已有的研究结果[9,10]表明，该系统可以形成稳定的旋转风，并通过改变热源温度控制旋转风风速大小；在聚热棚尺寸达到一定大小时，可以输出足以驱动低速风力机的风速值。但是，影响旋转风风速值的影响因素如加热温度，气流入射角度等还缺乏研究，这对以后设计该系统中这类参数的选取缺乏有力的指导，本文对该系统内加热条件，聚热棚结构参数对形成旋转风风速值的影响进行了数值模拟研究。

# 2 研究方法

# 2.1物理模型

我们数值模拟所采用的聚热棚物理模型和结构参数如图2(a)所示。

![](images/caef65ab7176bac3190bebfd583de406898f0406906925a4c3cd9e22b5f978c2.jpg)  
图2物理模型（单位m）(a)结构参数，（b）进气入射角度 Figure 2 Physical model (unit: m) (a)Structural parameters, (b)Air inflow incident angle

该聚热棚带有一定的坡度，在棚内侧嵌有八枚预旋导流叶片，根据文献[10]，对相同结构和初始条件下，带四枚、六枚、八枚和十二枚预旋叶片的聚热棚所产生风场进行初步的数值模拟，发现出口风场的合速度值接近的情况下，六枚叶片以上的旋转风速值明显高于四枚，十二枚叶片的旋转风速值并未明显高于六枚和八枚，故我们主要选取研究的叶片数量为六枚或者八枚；对于预旋叶片的长度，当叶片靠近聚热棚圆心的距离为聚热棚半径一半时，系统所获得的旋转风速值最大，故我们采用图2(a)的结构。

需要特别指出的是，为了使出口气流稳定存在，在出口处设置了一个高 $1 0 \mathrm { ~ m ~ }$ 的柱形壁起稳流的作用。为了研究不同入射角度的影响，我们还采用了三种不同弧度的叶片对应进气入射角度分别为$0 ^ { \circ }$ ， $3 0 ^ { \circ }$ 和 ${ { 6 0 } ^ { \circ } }$ 进行模拟，如图 2(b)。

# 2.2实验模型及方法

根据聚热棚的物理模型结构，我们对其整体尺寸缩小100倍（聚热棚半径 $2 \mathrm { m }$ ）制造了实验所用的实物模型(初次设置模型为六枚叶片)，如图3(a);将模型倒置，搭建实验台完毕后，如图3(b)；在模型底部设置可调节温度的加热板进行加热，在中心出口处放置一有机玻璃材质的圆柱壁面（半径为10cm，与中心出口尺寸一致)，在壁面的侧面一定高度处钻孔，将图3(c)所示热线风速仪伸入测量特征点的风速值。所有实验用仪器装置见表1。

我们选取圆柱壁面上端出口中心点O作为垂直向上速度的特征点，选择如图3(d)中位于聚热棚出口平面（柱形壁面下端进口）上方 $5 \mathrm { c m }$ 平面处的两个同心圆周上的测量点ABCD（半径为 $8 \mathrm { c m }$ ）四点和EFGH（半径为 $5 \mathrm { c m }$ ）四点，作为测量该平面上距离中心 $8 \mathrm { c m }$ 和 $5 \mathrm { c m }$ 的距离上切向旋转风速值的特征点。通过模拟与实验中相同结构相同初始条件的模型，验证方案的可行性与数学模型的可靠性。

![](images/2dbeb3e1f5fe7f6c5bf972860644b5b12f12edf4c91baaea771cce2a69cf9311.jpg)  
图3 实验系统和测点布置 (a)含六枚叶片的集热棚模型，(b) 实验系统，(c)热线风速仪和圆柱形导流壁，(d)测点的选择 Figure 3 Experimental system and mesurement points (a)Shed with6 vanes,(b)Experimental systems,(c)Hot-wire anemometer and cylindrical induced wall,(d)Mesurement points

表1实验所用仪器装置  
Table1 Experimental apparatus   

<html><body><table><tr><td>型号名称</td><td>作用</td><td>相关参数</td></tr><tr><td>圆柱形导流壁</td><td>稳定气流，便与测量</td><td>半径10cm，高度50cm</td></tr><tr><td>电加热板</td><td>提供加热</td><td>方形2mX2m</td></tr><tr><td>ED330L 温控仪</td><td>控制加热板温度</td><td>精度为±1℃</td></tr><tr><td>TM902C热电偶</td><td>测量加热板表面温度</td><td>量程-50-1300℃</td></tr><tr><td rowspan="2">TSI9515风速仪</td><td></td><td>精度为读数的±5%，分辨率</td></tr><tr><td>测量中心出口风速值</td><td>为0.01m/s，使用温度范围</td></tr><tr><td></td><td></td><td>为-18-93℃</td></tr></table></body></html>

# 2.3数学模型和算例设置

本文运用开源计算流体力学软件OpenFOAM进行模拟，采用标准 $\mathbf { k } { - } \mathbf { \varepsilon }$ 两方程模型，所有待求解变量 $\phi$ （速度、温度、湍动能和耗散量）由通用传输方程（1）求解：

$$
\frac { \partial \big ( \rho \phi \big ) } { \partial t } + \mathrm { d i v } \big ( \rho \mathbf { U } \phi \big ) = \mathrm { d i v } \big ( T _ { \phi } \mathbf { g r a d } \phi \big ) + S _ { \phi }
$$

其中， $\rho$ 代表所计算流体的密度， $\mathbf { U }$ 代表三维速度矢量 $( \boldsymbol { u } , \nu , \boldsymbol { w } )$ ， $\Gamma _ { \phi }$ 是扩散系数， $S _ { \phi }$ 是源项。

对于计算区域，我们采取矩形网格剖分，在聚热棚区域附近采用加密网格，合计网格数为22000左右。采用PIMPLE(PISO $^ +$ SIMPLE)算法处理压力-速度项。数值格式方面，时间项离散通过一阶隐式格式，梯度和扩散项采用二阶无界高斯插值的方法，散度项采用Gamma格式，表面插值格式采用中心差分的线性插值格式。残差设置上，对于压力项设置为 ${ { 1 0 } ^ { - 8 } }$ ，其他设置为 ${ { 1 0 } ^ { - 6 } }$ 。

边界条件为，周围环境温度为 $2 7 3 \mathrm { ~ K ~ }$ ，加热条件简化为底面加热，加热面与聚热棚底面投影形状尺寸相同，提供温差为 $4 0 \mathrm { K }$ ， $6 0 \mathrm { K }$ 和 $8 0 \mathrm { K } .$ ，边界压力为一个标准大气压 $( 1 0 ^ { 5 } \mathrm { \ P a } )$ ，底面和聚热棚表面处初始速度都是0，聚热棚表面绝热。

根据聚热棚半径（ $\mathrm { ~ 2 ~ m ~ }$ ， $2 0 \mathrm { m }$ 和 $2 0 0 ~ \mathrm { { m } } \mathrm { { , } }$ ，进气 入射角度（ $\left( 0 ^ { \circ } \right.$ ， $3 0 ^ { \circ }$ 和 ${ { 6 0 } ^ { \circ } }$ ）和加热温差设置（40 K， $6 0 \mathrm { K }$ 和 $8 0 \mathrm { K }$ ）分别设置算例。

# 2.4Froude数相似准则

对于上百米直径的聚热棚，我们很难通过实验来测量其产生的风速值，除了运用数值模拟的手段外，也可以通过流体力学中的相似理论，对小尺度聚热棚模型所产生风速值（实验值)，通过相似流动相似准则数相等来预测对应比例增加的同结构大尺寸聚热棚所产生的风速值。

聚热棚中心出口处的旋转风，本质上是一种浮力射流，浮力射流主要由浮力，惯性力和粘性力决定。根据试算结果，本文中所涉及的旋转风是湍流，故可以忽略粘性力的影响，我们采用惯性力与浮力的比值Froude数（简写为 $F r$ ）作为相似准则数，如方程(2):

$$
F r = u _ { 0 } ^ { 2 } \rho _ { 0 } / \left( g L ( \rho _ { a } - \rho _ { 0 } ) \right)
$$

其中, $u _ { 0 }$ 表示中心出口处附近的最大速度值（由于聚热棚结构不变，流场特征相似，为了简便，这里采用流场稳定后某一时刻的最大风速值)， $\rho _ { 0 }$ 是出口气流密度； $g$ 是重力加速度； $L$ 为中心出口的直径； $\rho _ { \mathrm { a } }$ 是周围空气的密度。

如果两个不同尺度浮力射流流动相似，那么其$F r$ 数也相等，据此，两个不同尺度下流动的特征速度比值 $\delta _ { u }$ 与特征尺寸比值的关系 $\delta _ { L }$ 应该满足(3)式：

$$
\delta _ { \scriptscriptstyle u } = \sqrt { \delta _ { \scriptscriptstyle L } }
$$

故特征速度值与特征尺寸值会满足一定的指数关系。本文将根据同一预旋入射角度的聚热棚，只改变其扩大的倍数（半径为 $2 \mathrm { m }$ ， $2 0 ~ \mathrm { m }$ ， $2 0 0 ~ \mathrm { { m } } .$ )，根据半径 $2 \mathrm { m }$ 条件下的实验值和模拟值，结合半径$2 0 \mathrm { m }$ 和 $2 0 0 \mathrm { m }$ 条件下的模拟值，可以得到一定条件下聚热棚半径，与其所产生总风速值的关系。

# 3结果与讨论

# 3.1实验结果

实验系统搭建完毕后，待周围环境基本无风后，开启加热板，加热温差与环境温差为30K，40K和$5 0 \mathrm { K }$ ，待风场稳定后开始测量。对于ABCDEFGHO共九个测量点，每个点记录时间为 $3 \ \mathrm { m i n }$ ，通过风速仪求一段时间内均值的功能，取 $3 \ \mathrm { m i n }$ 内的平均值记录，每个点不连续的测量三次，最后取三次的均值作为该点的最终值，ABCD四个点的最终值求平均，EFGH四个点的最终值求平均，得到两个圆周上平均风速值的最终实验值并记录；测量中心点O的垂直向上速度值，也是不连续的测得 $3 \ \mathrm { m i n }$ 内的均值，最后再求平均得到最终实验值。

最终实验值与模拟值的对比如图4，模拟过程的初始边界条件与实验条件大致一致。

![](images/60c5d6f6bbd4c933b5a4e470ec77a851eb328e87cf84abe488761748c4ffd1fe.jpg)  
图4 出口风场实验测量值与模拟值的对比 Figure 4 Comparison of experimental outlet velocity values and simulation ones

根据图4的结论，出口风速（垂直风速和切向风速）的实验测量值都要略高于模拟值，考虑到实验系统的系统误差（加热装置的温控精度和风速计精度）以及随机误差（实验环境中的温度速度变化，人为因素等，本文以采取延长测量时间等方法控制随机误差),结合实验测量值和模拟值有较好的趋势一致性（风速值随温度升高而增加)，我们可以认为该系统能够产生稳定的旋转风场，我们所选取的数学模型也是合理的。

# 3.2出口风场及影响因素

在计算过程达到稳定之后，我们重点关注中部柱形导流壁出口附近的速度场分布。

在我们的研究中，我们期望利用的是出口处风场的总动能，故合速度场中的速度分布具有更大意义，图5(a)是根据图2(a)中模型所获得的合速度场的分布，一般低速风力机的启动风度为 $3 \mathrm { \ m / s ^ { [ 1 1 ] } }$ ，在虚线框中的合速度值都高于 $3 \mathrm { m / s }$ ，再次表明该系统可以产生足以驱动低速风力机的风速值。图 5(b)是导流壁出口A-A剖面上的切向速度矢量场，即为旋转速度矢量场，证明进气气流经过预旋导流叶片的预旋，在中部导流壁出口处形成了旋转向上的旋转风场。

![](images/2dcaf87fa40940bdedf818f329656563538bcc9520847caf445adb0815ec547a.jpg)  
图5速度场分布 (a)旋转风合速度场，(b)A-A旋转矢量场Figure5Velocitydistribution(a)Resultantvelocity,(b)Tangential (Swirling) vectors

2.1节中我们已经得到了叶片数量和叶片长度对于风场的影响，针对该半径为 $2 0 0 \mathrm { m }$ 的聚热棚模型，我们继续模拟得到了不同进气入射角度下( $\cdot \boldsymbol { 0 } ^ { \circ }$ ，$3 0 ^ { \circ }$ 和 ${ 6 0 } ^ { \circ }$ )，对应特征点的旋转风速值 $U _ { \mathrm { z } }$ 和合速度值 $U _ { \mathrm { m a g } }$ ，其随加热温差的变化趋势如图6。

风速值随着加热温差的增大而增大；较大的叶片弧度对应较小进气入射角度，但带来更加充分的预旋，故切向旋转风速值会越大；对于合速度值，由于充分预旋带来的速度损耗，其变化趋势与旋转风速值变化趋势相反。我们需要较高的合速度值，但是气流的充分旋转能够有效提高风能的密度，在这三组中， ${ { 6 0 } ^ { \circ } }$ 的合速度值虽然最大，但是其旋转风速值过小， $3 0 ^ { \circ }$ 与 $0 ^ { \circ }$ 相比，虽然 $0 ^ { \circ }$ 的旋转风速值略高但是两者非常接近， $3 0 ^ { \circ }$ 的合速度值略高于 $0 ^ { \circ }$ ，该结论意味着 $0 ^ { \circ }$ 和 $3 0 ^ { \circ }$ 在能量密度近似的情况下， $3 0 ^ { \circ }$ 有更高的合速度即出口总动能，故$3 0 ^ { \circ }$ 为此三组角度中更加合适的进气入射角度。

![](images/c243f4396062ab28e7e8ba5dbb0ce4abe0e7fc77f55ea316d1bdf86aa545359b.jpg)  
图6不同入射角度下所产生速度随加热温差的变化趋势 Figure 6 Increase in the velocity due to the heating temperature difference with different incident angles

# 3.3应用前景初步分析

当聚热棚半径分别为 $2 \mathrm { m }$ ， $2 0 \mathrm { m }$ 和 $2 0 0 \mathrm { m }$ 时，结合相似准则分析和这些尺寸下的模拟值，参考文献[12]的分析方法，本文绘制了如下的曲线图图7(a)。该曲线图的意义在于，在确定预旋叶片的进气入射角度和聚热棚加热温差范围后，划分了能够产生 $3 \mathrm { \ m / s }$ 以上最大风速值所对应的聚热棚尺寸范围，为未来该类型结构聚热棚的结构运行参数的选取，提供了技术参考。

同时，随着人类对太空空间的探索以及制造技术的提升，未来该能源系统有望在火星上实现。火星的自身特点较地球而言更适宜该系统的运行，首先，火星上有更大的空间制造安放聚热棚，其次，火星表面主要是沙漠地区，砂石的比热低，同时，火星的大气层较薄，故火星上的昼夜温差也远远高于地球，更大的温差可以获得更大的旋转风；该系统亦能在火星上体现出优势，首先，人类生活于叶片内部，系统内已有的太阳能集热条件，再加以温湿度控制以及空气发生等装置，可以在叶片内部获得适合人类生存的条件，其次，聚热棚中心出口所产生的旋转风能以及太阳能电池板的电能，可以直接作为生活在叶片内部人类所需能量的来源。

本文以火星上的气象条件为初始条件，如温度，压力，大气密度等，按照图7(a)的曲线的获得方法，得到了如图 7(b)所示的火星上的聚热棚直径-最大风速值曲线图。该曲线的意义在于，当确认了适合火星用的风力机启动风速后，可以确定类似于图7(b)的对应可用风速的聚热棚直径尺寸范围。

![](images/b0c51051b78dd33821f3fb149c06a366fbb6ec01b690d3987506529ca5b2427c.jpg)  
图7产生可用风速的聚热棚尺寸范围(a)地球环境，(b)火星环境  
Figure 7Regime of solar-energy-collecting shed size for the least cut-in velocity wind energyuse.(a)Earth,(b)Mars

# 4结论

本文通过数值模拟和实验分析的手段，对一种新型的旋转风能系统中的核心部件一聚热棚的结构参数进行了研究，得到了以下结论：1)通过提供热源和进气预旋，可以在聚热棚出口处形成稳定向上的旋转风场，且当聚热棚尺度达到一定范围时，所形成风场足以驱动低速风力机；2）加热温差的提高可以提高旋转风场风速值。对于预旋角度，越小的进气入射角度（更大的叶片弧度)，所带来的更加充分的预旋可以提高旋转风速值(切向速度值)，而合风速值的变化规律与此相反。对于该系统，应尽可能的提供更大的加热温度，并且选取合适的叶片进气入射角度，不宜太大或太小。3）得到一定加热温差范围内，地球环境和火星环境下，该旋转风能系统产生可用风速的聚热棚尺寸范围，初步评估了其应用前景。

参考文献   
[1]Balme M, Greeley R. Dust devils on Earth and Mars [J]． Reviews of Geophysics， 2006, 44(3) : 1-22.   
[2]Leovy C B. Mars: The devil is in the dust [J]．Nature，2003，424(6952)：1008-1009.   
[3]Hess G D, Spillane K T. Characteristics of dust devils in Australia [J]. Journal of Applied Meteorology，1990，29(6): 498-507.   
[4]顾兆林.风扬粉尘—一近地层湍流与气固两相 流[M].北京：科学出版社，2010:213-270. GuZ L. Aeolian dust transport: near-surface gas-solid two-phase turbulent flows[M]． Beijing: Science Press， 2010:213-270.   
[5]Skoplaki E，Palyvos JA. On the temperature dependence ofphotovoltaic module electricalperformance:A reviewof efficiency/power correlations [J]. Solar energy，2009，83(5): 614-624.   
[6] ZondagH A.Flat-plate PV-Thermal collectors and systems: A review [J]. Renewable and Sustainable Energy Reviews, 2008，12(4): 891-959.   
[7］张娜．中低温太阳能品位间接提升及系统集成 [J]．工程热物理学报，2010, 31 (06) :901-905. Zhang N. The indirect upgrading of low/mid temperature solar heat and its system integration[J]. Journal of Engineering Thermophysics．2010，31(06) :901-905.   
[8]黄志刚，李增耀，陶文钰．太阳能高温电解水 蒸气制氢系统热力学分析[J]．工程热物理学 报，2009，30(09) :1445-1447. Huang Z G. Li Z Y， Tao W Q. Thermodynamic analysis of solar hydrogen production with high temperature steam electrolysis[J]. Journal of Engineer ing Thermophysics. 2009, 30 (09) :1445-1447.   
[9］顾兆林，张铭旭．采用低温太阳能集热的旋转 热浮力射流风能利用概念[J]．西安交通大学 学报，2013，47(01) :7-10. Gu ZL. Zhang M X. A new wind energy concept ofswirling buoyantjet drivenby

low-temperature solar energy[J]. Journal of Xi’ an Jiaotong University. 2013, 47 (01) : 7-10. [10] 张铭旭．可控热成旋风风能系统聚热棚数值模 拟及模型试验研究[D]．西安交通大学，2013. Zhang M X. Numerical simulation and model experimental research on the heating shed of dust-devil-like whirlwind power

generation system[D]. Xi' an Jiaotong University.2013.   
[11] Sahin A D. Progress and recent trends in wind energy [J]. Progress in Energy & Combustion Science， 2004， 5(5):501-543.   
[12] ZhangMX，Luo XL，Li TY，et al．FromDust Devil to Sustainable Swirling Wind Energy [J]． Scientific reports，2015，5.