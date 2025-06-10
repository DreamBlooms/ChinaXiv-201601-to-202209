# 轴流式冷却循环泵非稳态流激特性数值研究

李 忠1付立志1 顾海飞²龚卫锋²倪 丹1(1．江苏大学能源与动力工程学院，镇江 212013;2．上海船舶设备研究所，上海200031)

摘要轴流式冷却循环泵是舰船动力系统中的关键设备之一，泵内非稳态流动诱发的压力脉动是影响泵振动水平的主要水力因素。运用特定设计方法对某比转速为471的循环泵进行了设计并通过实验测量进行了性能验证。基于非定常数值计算，获得了不同工况下循环泵多个截面上压力脉动系数的变化规律。研究表明：叶轮进口压力脉动系数沿径向呈递增趋势，轮缘处流体激励能量最大且主要集中于叶频；叶轮出口压力脉动系数在轮缘和轮毂处取得极大值，主要激励频率为叶频及其高次谐频；导叶出口压力脉动系数沿径向基本一致，主要激励频率为1/5叶频；叶轮出口诱发的叶频压力脉动是决定泵振动水平的主导因素。研究结论为循环泵减振技术的发展提供了一定的理论支撑。

关键词冷却循环泵；压力脉动；叶频，数值计算中图分类号：TH312 文献标识码：A 文章编号:0253-231X(2017)05-1001-06

# Numerical Study on Pressure Pulsation Characteristics of Axial-flow Cooling CirculatingPump

LI Zhong1 FU Li-Zhi1 GU Hai-Fei² GONG Wei-Feng² NI Dan1 半 (1.School of Energy and Power Engineering,Jiangsu University，Zhenjiang 212013,China; 2. Shanghai Marine Equipment Research Institute, Shanghai 20o031, China)

AbstractAxial-fow coling CiredMng pump is oneofthe keyequipment inship power sytem. The pressure pulsation inducedhyits unsteady fow is the main hydraulic factor affecting the pump vibration level. The circulating pump with a specific speed of 471 was designed according to a special method and the performance verification was carried out through the experimental measurements. Based on unsteady numerical simulation, the variation of pressurepulsation coefficients in three sections of the pump under diffrent operating conditions wereanalyzed. The results show that the pressure pulsation coeffcient at the inlet of impeller increases along the radial direction.The fuid excitation at the shroud is maximum and mainly depending on the blade passing frequency （ $f _ { \mathrm { B P F } } ,$ ). The pressure pulsation coefficient at the shroud and hub in impeller outlet section also has a maximum value and the main excitation frequency is $f _ { \mathrm { B P F } }$ and its higher harmonic frequency. The pressure pulsation coefficient in guide yaneoutlet section is basically the same along the radial direction and the main excitation frequendyis 1/5 fBPF. The greater pressure pulsation coefficient at （204号 $f _ { \mathrm { B P F } } \mathrm { i s }$ , the higher vibration will be. The research achievements are helpful to provide some reference for furthering the vibration reduction technology.

Key wordscooling circulating pump; pressure pulsation; blade passing frequency; numerical simulation

# 0引言

轴流式冷却循环泵 (以下简称循环泵)是舰船动力系统二回路中的关键设备之一，主要用于主冷凝器中工质的冷却以及其它设备的冷却和冲洗。当舰船处于倒车、停车或低速正车状态下，循环泵运行于主动旋转工况以满足舰船动力系统安全稳定运行

的需求。

噪声辐射水平是影响舰船综合战斗性能的关键因素，降低噪声源的噪声强度、控制振动噪声的传递途径是现在和未来舰船噪声控制技术研究的重点和发展方向[1]。循环泵主动旋转工况下泵内非稳态流动诱发的压力脉动是影响泵体振动噪声水平的关键水力因素，其诱发的低频段噪声信号是舰船的主要目标特征信号之一。近年来，我国和欧美等发达国家之间在循环泵减振降噪技术水平上的差距正在逐步缩小，如何进一步降低水力因素诱发的振动噪声水平是目前研究的重点和难点问题，其关键之一就在于深入对各种非稳态流动诱发的激励特性认识，因此对循环泵内非稳态流激特性的研究具有十分重要的学术和应用价值。

由于循环泵结构的特殊性，对其内部非稳态流激特性的试验测量较为困难且周期较长。随着CFD技术的日益成熟，国内外学者普遍采用基于非定常数值模拟的手段研究泵内流激特性[2-4]。施卫东等[5]在考虑叶顶间隙的情况下对某轴流模型泵在不同采样频率和采样时间下的全流场进行了非定常数值计算和分析，研究指出应选取较高的采样频率，同时建议采用12倍旋转周期的采样时间；黎耀军等[6数值研究了不同叶顶间隙对轴流泵叶片轮缘区压力脉动的影响，获得了叶片工作面和背面近轮缘处压力脉动的主频；TsukamotoH等[7]研究发现叶频及其高次谐频是泵内主要激励频率，泵内周向压力的旋转是由叶轮和导叶间的动静干涉催用引起。

以上研究表明，采用合适的非定常数值计算方法可较准确地获得泵内压力脉动特性，常规轴流泵内非稳态流激特性已较为清楚。循环泵的运行需求较为特殊，其水力设计方法和过流部件结构参数和常规轴流泵有较大的区别，因此其内部非稳态流激特性必然有别于现有研究结论。

本文以某舰船用循环泵为研究对象，运用特定设计方法进行设计并基于实验测量开展泵性能验证。在此基础上，通过全流道非定常数值计算,对不同工况下循环泵多个截面上压力脉动系数的变化规律进行分析，初步揭示了该型泵内轮缘固壁和轮毂轴系上流体激励的主要频率及影响泵振动水平的主导诱因，为该型循环泵的安全稳定运行和优化提供了理论支撑和发展方向。

# 1循环泵物理模型及性能验证

# 1.1循环泵物理模型

循环泵的名义比转速为471，相关设计参数为：流量 $3 3 0 ~ \mathrm { m ^ { 3 } / h }$ ，扬程 $5 . 1 \mathrm { ~ m ~ }$ ，转速 $1 4 5 0 ~ \mathrm { r / m i n }$ ，设计工况效率大于 $8 0 \%$ ，汽蚀比转速大于1050。

循环泵叶轮和导叶的水力设计方法参照舰船用轴流泵设计方法开展，其设计要点为：叶轮通径为$2 0 0 ~ \mathrm { { m m } }$ ，叶轮外缘的圆周速度小于等于 $\mathrm { 1 5 ~ m / s }$ ，叶轮环量分布系数沿外法线方向先增加后减小，叶轮和导叶的叶片数分别为5和11。

循环泵为卧式，采用水平进口、 $9 0 ^ { \circ }$ 弯管出口型式，叶轮旋转中心线至泵弯管出口中心线距离为300mm。循环泵叶轮和导叶均采用数控加工方式成型，从而保证了数值计算对象和实验对象的一致性。

# 1.2循环泵性能验证

为验证循环泵设计方法的有效性以及数值计算方法的精确性，构建了如图1所示的闭式回路实验系统并开展了相关的泵性能测量实验。

![](images/e8373a93f0c2be0aa5ba59a7cb46ce4b7afee0d3a0f6259c1462da048055a50e.jpg)  
图1实验系统Fig.1 Experimental setup

系统中流量的测量精度为 $0 . 3 \%$ ，泵进出口静压的测量精度为 $0 . 0 7 5 \%$ ，功率和转速的测量精度为$0 . 2 \%$ ，符合GB/T3216-2005国家标准中1级精度要求。能量性能实验和汽蚀性能实验中运行工况的调节分别基于系统出口阀门开度调节和系统真空度调节而实现

循环泵设计工况下实测的性能参数为：扬程√5.13 m，效率 $8 0 . 1 \%$ ，汽蚀比转速1100，满足设计性能指标。

# 2数值计算

# 2.1计算区域及网格划分

以循环泵实际尺寸参数为依据进行三维流道造型，结合循环泵内流特点，将计算区域分别划分为进口区、叶轮区和导叶出口区三个区域，同时在模型泵进出口各顺延四倍管径长度的直管段以提高计算的稳定性，计算区域如图2所示。

鉴于循环泵叶轮和导叶内流道的三维扭曲特征，采用ICEM软件中对不规则区域具有强适应性的非结构化网格对上述区域进行网格划分。以泵扬程和水力效率随网格数增加是否趋于稳定为依据进行网格无关性验证，最终确定的各计算区域网格数分别为：进口区428501、叶轮区1956019、导叶出口区946152.

![](images/c4f520eb5fa6cb61c0e9909d11facdb54f42bfa4b96356fa15bca166d00073f0.jpg)  
Fig.2 Three-dimensional computational domain

# 2.2数值计算方法

计算模型进口采用速度进口边界条件，来流速度由计算工况点流量确定，出口采用压力出口边界条件。依据循环泵过流部件实测粗糙度设置各固壁的表面粗糙度，固壁采用无滑移条件，近壁区采用标准壁面函数法。采用 SIMPLEC 算法实现压力种速度之间的耦合，对压力项采用 Standard格式进行离散，其它各项均采用一阶迎风格式进行离散，残差收敛精度设置为0.00001。 七

定常计算中采用Realizable湍流模型封闭控制方程组，非定常计算中采用基于Realizable $k { - } \varepsilon$ 模型的DES 湍流模型封闭控制方程组，其中：采用Realizable $k { - } \varepsilon$ 模式模拟接近固壁边界的区域和涡流长度尺度小于最大格点尺寸的区域，对其它区域使用LES模式进行求解[8]。为满足Courant-Friedrich-Levy稳定准则，时间步长设置为叶轮旋转 $1 ^ { \circ }$ 所对应的时间，即 $1 1 4 . 9 ~ \mu \mathrm { s }$ ，采样时间取为12倍旋转周期所对应的时间。 +

![](images/00b449a03cc31790566b4d084335abab7843951a0c1b1d8e60b16d1647b8660d.jpg)  
图2计算区域

# 2.3非定常数值计算初始值验证

为提高计算的稳定性和收敛速度，通常将定常计算结果作为后续非定常数值计算的初始值，因此准确的定常数值计算结果是有效的非定常数值计算的重要前提。在设计工况流量 $\left( Q _ { \mathrm { d } } \right)$ 下，定常数值计算所得的泵扬程为 $5 . 2 8 \textrm { m }$ ，和实验值之间的误差仅为 $2 . 9 \%$ ，在 $0 . 9 \ Q _ { \mathrm { d } }$ 和 $1 . 1 ~ Q _ { \mathrm { d } }$ 时的误差均在 $3 . 5 \%$ 以内，表明非定常数值计算初场的精确性符合要求。

# 2.4监测点设置

为综合分析循环泵流道内主要特征位置处的压力脉动特性，分别在泵叶轮进口、出口和导叶出口截面上设置压力脉动监测点。各截面上从轮毂至轮缘沿径向均布4个监测点，各监测点的编号及位置如图3所示。

# 3计算结果分析

本文中采用的无量纲参数压力脉动系数定义如下：

$$
C _ { \mathrm { p } } = { \frac { p - { \bar { p } } } { { \frac { 1 } { 2 } } \rho U ^ { 2 } } }
$$

式中， $p$ 为瞬时压力值， $\bar { p }$ 为采样时间内的平均压力， $\rho$ 为液体的密度， $U$ 为叶轮外缘的圆周速度。

# 3.1设计工况下压力脉动分析

图4为设计工况下叶轮进口截面上各监测点处压力脉动的时域图。由图可知，在叶轮进口处，压力脉动的幅值沿径向外法线方向呈递增趋势，因此叶轮进口处流体诱发的激励主要作用于轮缘固壁。

![](images/4a1d5d2cd9d7cc3e3fa2f50cdff9f3bef3a76f504edf0f7ced8ba5202f50aa9d.jpg)  
图3监测点位置示意图Fig.3 Location of monitoring points

![](images/833f928fdd7e9ba7f7a21dff741ed50bb3a8e601079c97f19c3f3ec6857c064d.jpg)  
图4 $1 . 0 Q _ { \mathrm { d } }$ 工况下叶轮进口各监测点处压力脉动时域图Fig.4 Pressure signals in time domain of impellerinletpoints at $1 . 0 Q _ { \mathrm { d } }$ 血理

图5为叶轮进口截面上各监测点处压力脉动的频域图。由图可知，叶轮进口处压力脉动的特征频率为1/5叶频 $( 2 4 . 2 ~ \mathrm { H z } )$ 、叶频 $( 1 2 1 ~ \mathrm { H z } )$ 及二倍叶频$( \mathrm { { 2 4 2 } \ H z ) }$ 。沿径向外法线方向，各监测点1/5叶频压力脉动幅值基本一致、叶频压力脉动幅值呈快速递增趋势、二倍叶频压力脉动幅值呈缓慢递增趋势。通过比较各监测点不同特征频率处压力脉动幅值的大小可知，叶轮进口轮缘处流体激励能量最大且激励。能量主要集中在叶频，叶轮进口轮毂处流体激励能量主要集中在1/5叶频。流体产生的激励必定通过轴系或固壁向外界传递或辐射，因此叶轮进口处影响振动噪声水平的关键水力因素是叶轮外缘处叶频压力脉动幅值的大小。

图6为设计工况下叶轮出口截面上各监测点处压力脉动的时域图。由图可知，在叶轮出口处，压力脉动的幅值沿径向外法线方向呈先减小后增大的变化趋势且叶轮轮缘和轮毂处压力脉动幅值的大小基本相等，因此叶轮出口处流体对轮毂轴系和轮缘固壁的激励水平基本相当。

图7为叶轮出口截面上各监测点处压力脉动的频域图。由图可知，叶轮出口处压力脉动的特征频率为1/5叶频、叶频及其高次谐频。各监测点1/5叶处压力脉动幅值的变化规律和叶轮进口一致，叶频和二倍叶频压力脉动幅值沿径向外法线方向呈先减小后增加的变化趋势，约在 $7 5 \%$ 半径(B3)处取得极小值。通过比较各监测点不同特征频率压力脉动幅值的大小可知，叶轮出口处流体激励能量主要集中于叶频，其次为二倍叶频，轮缘固壁处叶频激励能量略小于轮毂处，而其叶频高次谐频激励能量则略大于轮毂处。结合压力脉动的时域图可知，叶频及其高次谐频对轮缘固壁和轮毂轴系的综合激励基本相等。

由上述分析可知，时域图中压力脉动的幅值和频域图中主要特征频率的脉动幅值沿径向的变化规律相一致，因此循环泵导叶出口处仅给出如图8 所示的压力脉动频域图。由图可知在导叶的整流作用下，导叶出口处压力脉动幅值明显减弱且沿径向基本一致，其主要特征频率为 $\mathcal { T } / 5$ 叶频和2/5 叶频。通过比较各监测点不同特征频率压力脉动幅值的大小可知，导叶出口处非稳定流动诱发泵体振动的主频为1/5叶频且对轮缘固壁和轮毂轴系的激励水平相等。

![](images/29745897594b9446891be3fc57f8e7e81e0392a3bf166cababb508ff78ac416f.jpg)  
图5 $1 . 0 Q _ { \mathrm { d } }$ 工况下叶轮进口各监测点处压力脉动频域图Fig.5 Pressure speetrum of impeller inlet points at $1 . 0 Q _ { \mathrm { d } }$

![](images/1951b1b99594a3f5b376220d8f593f26d2c3711f8546a133b1ccf780acef7b42.jpg)

![](images/576cccfdb042316fd0291ce9527f31d8badd5593695c565d4fbabd726ea60a8c.jpg)  
图6 $1 . 0 Q _ { \mathrm { d } }$ 工况下叶轮出口各监测点处压力脉动时域图 Fig.6 Pressure signals in time domain of impelleroutlet points at $1 . 0 Q _ { \mathrm { d } }$

结合图5、7、8中压力脉动幅值的变化趋势可知，循环泵流道中非稳定流动诱发的1/5叶频激励沿轴向基本一致，叶频激励主要体现在叶轮出口处且其激励能量远大于其它特征频率产生的激励，由此可见泵叶轮出口处诱发的叶频压力脉动是诱发泵振动的主导水力因素。

![](images/352bea0bddb2d94abfe55b2f25667bd2337b91b8046362586efcc6b2ff6301e5.jpg)  
图7 $1 . 0 Q _ { \mathrm { d } }$ 工况下叶轮出口各监测点处压力脉动频域图Fig.7 Pressure spectrum of impeller outlet points at $1 . 0 Q _ { \mathrm { d } }$   
图9为轮毂上各监测点处的压力脉动频域图，

![](images/fa3b083fad93dc4ef1fb05698036b551347c3fe0e4ae900350f41038a1529cc4.jpg)  
图8 $1 . 0 Q _ { \mathrm { d } }$ 工况下导叶出口各监测点处压力脉动频域图Fig.8 Pressure spectrum of guide-vane outlet pointsat $1 . 0 Q _ { \mathrm { d } }$

![](images/43b9e163637f2ab1ff75fc44f36f3291c8fc4a3daa20dfd1d18c11153fbf7b6f.jpg)  
图9 $1 . 0 Q _ { \mathrm { d } }$ 工况下轮毂各监测点处压力脉动频域图Fig.9 Pressure spectrum of hub points at $1 . 0 Q _ { \mathrm { d } }$

# 3.2不同工况下压力脉动对比分析

图10为不同工况下各监测点处压力脉动系数的均方根误差对比图，图中：横坐标为监测点编号，各监测点对应的三个柱状图从左至右分别对应$0 . 9 Q _ { \mathrm { d } }$ 、 $1 . 0 Q _ { \mathrm { d } }$ 和 $1 . 1 Q _ { \mathrm { d } }$ 工况；纵坐标为压力脉动系数的均方根误差，其表达式如下：

$$
R M S E = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( C _ { \mathrm { p } i } - { \overline { { C } } } _ { \mathrm { p } } ) ^ { 2 } } { n } } }
$$

式中， $\overline { { C } } _ { \mathrm { { p } } }$ 为压力脉动系数的平均值， $n$ 为压力脉动系数的计算个数。RMSE表征瞬时压力脉动系数相对于平均压力脉动系数的离散水平，其值越大表示压力脉动越剧烈。

![](images/ae2d63963ff560ff3d636bc7e1eccc08d9d5a728af94551a293a5d8fcfd6514f.jpg)  
图10不同工况下各监测点处压力脉动系数的均方根误差Fig.10 RMSE value of monitoring points at $0 . 9 Q _ { \mathrm { d } }$ ， $1 . 0 Q _ { \mathrm { d } }$ and $1 . 1 Q _ { \mathrm { d } }$ X

由图可知，随着流量的增加，压力脉动系数先减小后增加且在设计工况下取得极小值说明循环泵设计工况即其最优工况。综合对比不同工况下各测点处压力脉动系数均方根误差值的大小可知，循环泵导叶出口处压力脉动最小其次为叶轮进口处，叶轮出口处压力脉动最剧烈。在相同工况下，各轴截面上压力脉动的变化趋势和前面的论述相一致。在叶轮出口处， $0 . 9 Q _ { \mathrm { d } }$ 工况下的压力脉动显著大于 $1 . 0 Q _ { \mathrm { d } }$ 工况下的压力脉动，其原因可能是小流量工况下泵内剧烈的涡流分离所引起的，由此也说明本文所采用的设计方法存在一定的局限性，从减振降噪的角度来看，基于该设计方法所得的循环泵不适合运行于小流量工况。

# 4结论

通过对特定设计方法下循环泵压力脉动特性的数值计算和分析，得到以下结论：

1）叶轮进口轮缘处流体激励能量最大且激励能量主要集中在叶频，轮毂处流体激励能量主要集中在1/5 叶频。

2)叶轮出口处叶频和二倍叶频压力脉动幅值沿径向外法线方向呈先减小后增加的变化趋势，叶频及其高次谐频对轮缘固壁和轮毂轴系的综合激励基本相等；叶轮出口处的叶频压力脉动水平是决定泵振动水平的主因。

3）导叶出口处压力脉动系数沿径向基本一致,主要激励频率为1/5叶频。

4)基于该设计方法的循环泵不适宜运行于小流量工况。

# 参考文献

[1]王晓侠，刘见华．舰船水下辐射噪声的控制分析[J]．船舶, 2013,24(1):36-39 WANG Xiaoxia,LIU Jianhua. Control Analysis of Underwater Radiation Noise for Surface Ship [J]. Ship & Boat, 2013,24(1):36-39   
[2] WANG Fujun,LI Yaojun,WANG Yanli. CFD Simulationof 3D Flow in Large-bore Axial-flow Pump with Halfelbow Suction Sump [J]. Journal of Hydrodynamics, Ser. B, 2006,18(2): 243-247 MitohA,Yano T,Sekine K,et al.Computational Fluid Dynamics Analysis of an Intra-cardiac Axial Flow Pump [J].Artificial Organs, 2003,27(1): 34-40   
[4] LI,Yaojun，WANG Fujun.Numerical Investigation of Performance of an Axial-flow Pump with Inducer [J]. Journal of Hydrodynamics,Ser.B,2007,19(6):705-711   
[5] 施卫东,姚捷,张德胜,等.采样频率和时间对轴流泵压力脉 动特性的影响[J].排灌机械工程学报，2013，31(3)：190- 194 SHI Weidong,YAO Jie, ZHANG Desheng,et al. Influence of Sampling Frequency and Time on Pressure Fluctuation Characteristics of Axial-flow Pump [J].Journal of Drainage and Irrigation Machinery Engineering, 2013, 31(3): 190-194   
[6]黎耀军,沈金峰,洪益平,等.叶顶间隙对轴流泵轮缘压力脉 动影响的数值预测[J].农业机械学报，2014,45(5)：59-64 LI Yaojun, SHEN Jinfeng,HONG Yiping, et al. Numerical Investigation of Pressure Fluctuations on Axial-flow Pump Blades Affected by Tip-gap Size [J]. Transactions of the Chinese Society of Agricultural Machinery,2014, 45(5): 59-64   
[7] Tsukamoto H, Uno M,Nagai Y,et al. Pressure Fluctuation Downstream of Diffuser Pump Impeller [J]. Transactions of the Japan Society of Mechanical Engineers B, 1995,61(586): 2149-2156   
[8] 李忠，倪丹，杨敏官.翼型空化绕流特征和流激特性的关联 分析[J].工程热物理学报，2015,36(5)：1005-1010 LI Zhong,NI Dan,YANG Minguan.Association Research on Characteristics of Cavitation Flow Structure and Pressure Pulsation around Hydrofoil[J].Journal of Engineering Thermophysics,2015,36(5):1005-1010