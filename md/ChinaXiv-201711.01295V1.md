# DSO在轨检测方案的设计与结构分析

王强，胡企千，倪厚坤，章海鹰（中国科学院国家天文台南京天文光学技术研究所，江苏 南京210042)

摘要：为论证深空太阳天文台的主望远镜桁架结构在火箭发射过程中，能否经受严苛的发射环境，并能继续正常工作，以及经历严苛的发射环境后，望远镜是否需要设置在轨调整系统，使主镜与准直镜的相对位置能够精确地保持，提出了一种可行的在轨检测方案，并对主望远镜的桁架结构进行静应力分析、动载荷分析、模态分析及频响应分析，分析了其安全性，发现桁架结构需要减振机构降低晓振造成的响应，从而初步论证了在轨调整的必要性及可行性，初步验证了结构设计及工艺流程的合理性。针对主望远镜桁架的正弦振动试验及在轨检测试验部分，给出了试验的具体步骤及实施方案，为后续试验工作的开展提供了技术支持。

关键词：力学分析；在轨检测；静应力；动载荷；频响应分析中图分类号：V414.1；V414.5；V417+.6 文献标识码：A 文章编号：1672-7673(2017)04-0526-07

太阳深空探测是我国深空探测规划中重要的目标之一，也是我国未来航天领域发展的必然选择。鉴于此，我国科学家自主提出了深空太阳天文台（Deep-space Solar Observatory，DSO)任务，通过深空太阳天文台搭载的主光学望远镜、极紫外成像望远镜、高能辐射谱仪、全日面 $\mathrm { H } \alpha$ 和白光望远镜、太阳和行星际射电频谱仪及莱曼阿尔法望远镜等仪器对太阳进行协同观测，将改变我国缺乏深空太阳观测能力的现状，大幅提高我国太阳物理和空间科学的研究水平，显著增强我国对太阳风暴的监测、预报和警报能力，对于实现我国深空探测整体规划目标具有重要意义。大型空间望远镜作为极其精密的观测设备，需经历严苛的力学发射环境，并在恶劣的空间热环境中正常工作。考虑到光学系统容差、结构设计制造可能性[1]及以往工作经验等因素，深空太阳天文台在发射之前，必须确认是否需要设置在轨调整系统。

# 1问题分析

深空太阳天文台主望远镜的桁架结构由5片环梁组成[2]。为减轻重量，环梁边缘打减重孔。边缘用配重块结构模拟搭载的其他光学仪器载荷。主镜室位于桁架结构的最底层环梁上，准直镜架位于桁架结构的最顶层环梁上。桁架结构整体尺寸约为 $1 . 5 \mathrm { m } \times 1 . 5 \mathrm { m } \times 4 . 1 \mathrm { m }$ ，结构总质量约 $1 2 0 0 \mathrm { k g } ^ { [ 3 ] }$ 。

按照设计方案，卫星通过搭载CZ-3B(G2)运载火箭升空。为减少在轨检测和调整的自由度，文中设计了一种基本结构：在深空太阳天文台主光学望远镜桁架结构的主镜和准直镜之间，用4根等长细杆连接，形成可平移的结构。该结构经过发射环境后，主镜与准直镜的相对位置的保持性，及主镜与准直镜之间的平移性，是确定深空太阳天文台是否设置在轨调整系统的主要依据。

考虑到火箭发射过程中桁架的安全性问题，桁架结构应满足以下要求：（1)足够高的刚度和强度（安全系数大于1.25），能承受火箭发射过程中出现的最大静力及火箭在全发射过程中的运载动力，防止发射过程中出现不允许的永久变形；（2)主桁架及有效载荷满足火箭发射的基频要求，一阶横向固频大于 $1 0 ~ \mathrm { H z }$ ，一阶纵向固频大于 $3 0 ~ \mathrm { H z } ^ { [ 4 ] }$ ；（3)为应对火箭发射过程中的纵向耦合振动(POGO)现象[5]，需对桁架结构进行响应谱分析，以找出振动过程中的共振频率段，并针对可能出现的该频率段范围内的振动，采取必要的减振措施；（4)按照火箭发射要求，桁架结构应当进行正弦振动试验，使其能够经受力学考验并正常工作，同时检验材料、制造工艺是否存在缺陷，保证卫星在轨运行的可靠性[6]。

本文运用有限元法分析火箭发射过程桁架结构的安全性、平移性问题，对试制的桁架结构进行正弦试验，并记录分析试验前后的数据，以测定主镜与准直镜的位置精度保持性。

# 2在轨检测方案

# 2. 1 系统组成

在轨检测系统，由主镜（primary mirror）、准直镜（collimating mirror）、上镜面系统（upper mirrorsystem）、下镜面系统(lower mirror system)组成，具体如图1，对应的零件见图2。

![](images/9ade2d6f6d75c1c9356b0c765afc0378c938ad4bde51d6ebc15ebd416e3cf05b.jpg)  
图2深空太阳天文台主望远镜桁架结构图Fig.2The truss system of the DSO Primary Optical Telescope

![](images/9c77b87ee45a4708938830d2dcde6e0a0e1d6bc1a7cc76ef197a5d60780d910f.jpg)  
图1在轨检测方案图  
Fig.1Principle of the on-orbit detection scheme

上镜面系统由一块 $4 5 ^ { \circ }$ 平面大反射镜( $4 5 ^ { \circ }$ reflective plane mirror）、一块小平面镜（small planemirror)与一块刻有十字丝的分划板(cross reticule)组成，固定在准直镜架(collimating mirror holder）上,下镜面系统由一块小平面镜(small plane mirror)与一块小球面镜(small spherical mirror)组成，固定在主镜（primary mirror）处。

2.2 原理及方法

(1)将测微准直光管对准无穷远处调焦，观察侧微光管焦面十字丝通过 $4 5 ^ { \circ }$ 大平面镜及上、下两块小平面镜的反射像（两块小平面镜事先调整至合适方向并固定），记录反射像沿 $X$ ， $Y$ 方向的距离示数 $x _ { 1 }$ ， $y _ { 1 }$ ，可得主镜与准直镜的相对倾斜（图3（a））。

若主镜与准直镜间沿 $Y$ 方向偏角为 $\alpha _ { 1 }$ ，经计算，可得 $y _ { 1 } = \left( b + h \right) \mathrm { t a n } 2 \alpha _ { 1 }$

则 $\alpha _ { 1 } = \frac { 1 } { 2 }$ arctan $\frac { y _ { 1 } } { b + h }$

若主镜与准直镜间沿 $X$ 方向偏角为 $\alpha _ { 2 }$ ，由数学公式，计算得 $\alpha _ { 2 } = \frac { 1 } { 2 } \arctan \frac { x _ { 1 } } { b + h } .$ （204号

![](images/9bd9f3f05c20d3dbcfdf0c9146a024aa97aa5051abef30554a69a9d7bf278dd2.jpg)  
图3在轨检测原理简图.（a）相对倾斜角计算；（b）偏心量计算Fig.3Theoreticaldiagramoftheon-orbitdetectionscheme.（a）Theinclinationcalculation；（b）Theeccentricitycalculation

(2)将测微准直光管对准安装在准直镜架上的分划板十字丝调焦，测该十字丝正好处于主镜上小球面镜球心的位置。测出并记录分划板十字丝及其反射像沿 $X$ ， $Y$ 两个方向的距离示数 $\cdot _ { x _ { 2 } }$ ， $y _ { 2 }$ ，可得出主镜与准直镜的偏心量(图3(b)）。

若主镜与准直镜间沿 $Y$ 方向偏心量为 $d _ { 1 }$ ，经计算，得 $d _ { \mathrm { 1 } } \mathrm { = } h _ { \mathrm { 0 } } \mathrm { t a n } \beta _ { \mathrm { 1 } }$ ; $y _ { 2 } = \left( b + h _ { 0 } + h \right) \mathrm { t a n } \beta _ { 1 }$ 所以，di=b+h+h；若主镜与准直镜间沿X方向偏心量为d，得d= $d _ { 2 } = \frac { x _ { 2 } h _ { 0 } } { b + h _ { 0 } + h }$ ：

分别记录正弦振动前后主镜与准直镜相对倾斜量与偏心量，可以检测其相对位置的精度保持性。

# 3力学分析

# 3.1 静应力分析

根据长征系列发射火箭用户手册（以下简称用户手册)提供的资料与要求，进行3阶段3方向共9次有限元分析，记录分析文件中准直镜架处的最大变形与安全系数，结果见表1，由表1可知，结构整体最小安全系数远大于1.5，达到用户手册要求。沿平面 $X$ ，Y方向的变形为主要变形方向，准直镜与主镜的平移性能满足设计要求。

# 3.2 动载荷分析

卫星在动力飞行中，本身的动力学环境对卫星及星上组件造成结构性破坏，引起卫星设备故障，可能影响卫星飞行任务的完成，甚至导致整个飞行任务的失败。因此，动力学环境对卫星工作可靠性的影响不容忽视[7]

表1桁架静应力分析结果  
Table1The analysis result of Static stress of the truss system   

<html><body><table><tr><td rowspan="2">Stage</td><td rowspan="2">Directions of loads</td><td colspan="2">Maximum Displacements of the collimator holder</td><td rowspan="2">Minimum safety factor</td></tr><tr><td>X/mm</td><td>Y/mm Lateral/mm</td></tr><tr><td>Transonic</td><td>X</td><td>-1. 021</td><td>-0.007 2 -0.458 5</td><td>>1.5</td></tr><tr><td>Phase&</td><td>Y</td><td>-0.016 6</td><td>-0.9658 -0.458 2</td><td>>1.5</td></tr><tr><td>MDP</td><td>Z</td><td>-0. 743 5</td><td>-0.694 1 -0. 459 6</td><td>>1.5</td></tr><tr><td>Stage-1</td><td>X</td><td>-0.584</td><td>-1. 324 -0.216 7</td><td>>1.5</td></tr><tr><td>Engines</td><td>Y</td><td>-1. 337</td><td>-0.556 -2. 071</td><td>>1.5</td></tr><tr><td>Shutdown</td><td>Z</td><td>-1. 343</td><td>-0.566 -0.204 8</td><td>>1.5</td></tr><tr><td>1/2nd</td><td>X</td><td>-0.872 5</td><td>0.386 6</td><td>0.214 3 >1.5</td></tr><tr><td>Stage</td><td>Y</td><td>-0.369 4</td><td>-0. 875 6 0. 221 4</td><td>>1.5</td></tr><tr><td>Separation</td><td>Z</td><td>-0.877 5</td><td>-0.3694 0.212 5</td><td>>1.5</td></tr></table></body></html>

根据用户手册提供的火箭发射全程纵向加速度曲线(图4)，将火箭发射全程受力导分析中。

根据文「8，选择模态阻尼值0.025，得到运动过程的最大应力与整体最大位移如图5。

图5是全步长下桁架整体最大节应力/最大位移图。可知，最大应力不超过 $4 7 \ \mathrm { M P a }$ ，最大变形仅 $0 . 0 9 2 \mathrm { m m }$ ，其安全系数均远大于4.2，满足用户手册要求。

# 4模态分析与响应谱分析

# 4.1 模态分析

根据用户手册要求，分析前五阶振型，结果见表2。

![](images/66ee1452b1020ed476675fd63057f56fba03177ea887aada9e7fe0f86bc7f990.jpg)  
图4火箭发射全程纵向速度、加速度时间曲线Fig.4The longitudinal speed-time curve and acceleration-timecurve of thelaunchvehicle

![](images/a2c447bdaa520da9681daa163fb792496112880084cf784a396b273801d066ed.jpg)  
图5桁架动载荷分析图.（a）最大应力图；（b）最大位移图 Fig.5The truss system's dynamic load analysis during the whole process of launch （a）Maximum stress nephogram；（b）Maximum displacement nephogram

表2桁架前五阶固有频率  
Table 2Initial fifth order natural frequencies of the truss system   

<html><body><table><tr><td>Mode</td><td>Freq(rad/s)</td><td>Freq/Hz</td><td>Cycle/s</td><td>Main vibration mode</td></tr><tr><td>1</td><td>103. 71</td><td>16. 505</td><td>0. 060 586</td><td>Lateral swing</td></tr><tr><td>2</td><td>104. 08</td><td>16. 565</td><td>0. 060 367</td><td>Lateral swing</td></tr><tr><td>3</td><td>239. 72</td><td>38. 153</td><td>0. 026 21</td><td>Lateral twist</td></tr><tr><td>4</td><td>339.58</td><td>54. 046</td><td>0. 018 503</td><td>Longitudinal swing</td></tr><tr><td>5</td><td>346.37</td><td>55.126</td><td>0. 018 140</td><td>Longitudinal swing</td></tr></table></body></html>

由表2可知，一阶振动为横向摆动，频率 $1 6 . 5 0 5 \mathrm { H z }$ ；二阶振动也为横向摆动，且方向与一阶振动方向垂直，频率 $1 6 . 5 6 5 \mathrm { H z }$ ；三阶振动为横向圆扭动，频率 $3 8 . 1 5 3 \mathrm { H z }$ ；四阶振动为纵向摆动，频率$5 4 . 0 4 6 \ \mathrm { H z }$ ；五阶振动为纵向摆动，且方向与四阶振动方向垂直，频率 $5 5 . 1 2 6 ~ \mathrm { H z }$ 。结构安全性能满足用户手册要求。

# 4.2 频响应分析

火箭在发射过程中，液体火箭结构系统与推进系统特性相互耦合，产生纵向的不稳定低频振动，该现象被称之为纵向耦合振动。它发生于火箭飞行的各个时刻，持续时间很长，使得运载器的安全性与可靠性均受到巨大威胁。

响应谱分析能够计算结构在振荡载荷作用下对每一个计算频率的动响应。根据用户手册中卫星的鉴定试验条件，对桁架结构进行3个方向的频响应分析，参考点的分析结果见图6。

![](images/2b68341457b7f88ae57fff4d048c5131eb8a6cb4cf4c2c2b97895408a179b0ae.jpg)  
图6桁架参考点频响应分析图

(a) $X$ 方向最大应力响应；（b) $X$ 方向最大位移响应；（c) $X$ 方向最大加速度响应；(d) $Y$ 方向最大应力；（e) $Y$ 方向最大位移响应；（f) $Y$ 方向最大加速度响应；(g) $Z$ 方向最大应力；（h) $Z$ 方向最大位移响应；（i) $Z$ 方向最大加速度响应Fig.6The reference points'Response spectrum analysis of the struss system

（a）Maximum stress response in direction $X$ ；（b）Maximum displacement response in direction $X$ ；（c）Maximum acceleration response in direction $X$ ；（d）Maximum stress response in direction $Y$ ；（e）Maximum displacement response in direction $Y$ ； (f) Maximum acceleration response in direction $Y$ ；（g）Maximum stress response in direction $Z$ ；（h）Maximum displacement response in direction $Z$ ；（i）Maximum acceleration response in direction $Z$ （204

横向 $X$ ， $Y$ 方向振动时，当火箭振动频率在 $1 6 \sim 2 0 \ \mathrm { H z }$ 范围，最大加速度响应超过 $2 2 { \mathrm { g } }$ ，在 $7 7 \sim 8 1$ $\mathrm { H z }$ 时，最大加速度响应超过 ${ \mathfrak { g } } _ { \mathbf { \xi } _ { \mathbf { \xi } } } $ ，此时桁架结构出现了破坏性振动，尤其是 $1 6 \sim 2 0 ~ \mathrm { H z }$ 的情况，对桁架结构破坏很大。纵向振动时，当火箭振动频率在 $7 3 \sim 8 1 ~ \mathrm { H z }$ 时，最大加速度响应超过 $1 7 \mathrm { \ g }$ ，在100Hz 左右时，最大加速度响应超过 $7 \mathrm { { g } }$ ，个别点甚至超过了 $6 5 \mathrm { \ g }$ ，此时桁架结构出现了破坏性振动。

由图6可知，对应火箭发射过程中出现的 $1 6 \sim 2 0 ~ \mathrm { H z }$ 、 $7 3 \sim 8 1 ~ \mathrm { H z }$ 的振动，桁架结构三向出现了强度破坏性的振动。因此，要求在结构设计中必须加入减振措施，降低桁架结构的响应，避免出现结构的破坏。

# 5 正弦振动

为模拟桁架结构在火箭发射过程中的受力与变形情况，需要进行正弦振动试验。试验执行标准按照《GB/T2423.10-2008电工电子产品环境试验第2部分：试验方法》进行，在桁架结构中布置好传感器监测点，输入正弦激励信号如表3。观察桁架的振动情况，并记录传感器读数，给出幅频特性参数。

表3正弦振动试验要求  
Table3SC-sinusoidal Vibration Test Specification   

<html><body><table><tr><td colspan="2">Frequency/Hz</td><td>Test Load</td></tr><tr><td>Longitudinal</td><td>5~8</td><td>4. 66 mm</td></tr><tr><td rowspan="3">Lateral</td><td>8~100</td><td>1.2g</td></tr><tr><td>5~8</td><td>3.5 mm</td></tr><tr><td>8~100</td><td>0.9g</td></tr><tr><td>Scan rate(Oct/min)</td><td>/</td><td>2</td></tr></table></body></html>

# 6结论与展望

通过上述分析结果，在轨检测方案的安全性分析结果如下：

静应力分析结果、动载荷分析结果和频率分析结果均满足安全性要求，但频响应分析结果不满足安全性能要求，需要采取减振措施降低结构的响应。

主镜与准直镜之间保持的平移性，根据分析结果，主要变形方向满足设计要求。

因此，目前的工作已说明在轨检测方案设计的不完善。不完善之处在于频响应的分析结果发现桁架在处于危险频率段内的振动强度过大，足以破坏结构强度。

主镜与准直镜的相对位置的保持性，限于时间及条件因素，该步骤尚未进行。后续工作将针对在轨检测方案的试验、正弦振动试验及桁架结构采取减振措施后的响应进行分析，得出进一步的结论。

# 参考文献：

[1] 袁家军，于登云，陈烈民，等.卫星结构设计与分析（上）［M].北京：中国宇航出版社，2004.  
[2] 刘梅，胡企千.空间太阳望远镜 $1 \mathrm { ~ m ~ }$ 主镜支撑结构的研究［J］.天文研究与技术—国家天文台台刊，2004，1(2)：99-106.Liu Mei，Hu Qiqian. A study on support structure of the one-meter primary mirror of the spacesolar telescope [J].Astronomical Research & Technology——Publications of National AstronomicalObservatories of China，2004，1(2）:99-106.  
[3] 胡企千，刘梅.空间太阳望远镜镜筒桁架的优化［J]．光学精密工程，2003，11(2)：151-156.Hu Qiqian，Liu Mei. Optimization of tube truss for space solar telescope ［J].Optics andPrecision Engineering，2003，11(2）:151-156.  
[4] 陈志平，陈志远，杨世模.空间太阳望远镜主桁架的模态分析与试验［J].光电工程，2004,31(12) : $^ { 1 - 3 + 7 }$ ：Chen Zhiping，Chen Zhiyuan，Yang Shimo.Modal analysis and experiment on the main truss ofSpace Solar Telescope [J].Opto-Electronic Engineering，2004，31(12） : $^ { 1 - 3 + 7 }$ ：  
[5] 王小军，于子文，张兵，等.国内外运载火箭POGO 抑制技术研究进展［J]．中国科学：技术科学，2014，44(5)：492-503.Wang Xiaojun，Yu Ziwen， Zhang Bing，et al. Progress of POGO suppresson technology oflaunch vehicles at home and abroad [J]. Scientia Sinica: Technologica，2014，44（5）: 492-503.  
[6] 沈凤霞.正弦振动试验及结构响应数据处理方法［J].航天器环境工程，2004，21(4)：7-13.Shen Fengxia. Sine vibration test techniques and data processing method of structure response[J].Spacecraft Environment Engineering，2004，21(4）:7-13.  
[7] 柯受权，黄本诚，何传大，等.卫星环境工程和模拟试验（下）［M]．北京：中国宇航出版社，1993，11.  
[8] Adams V，Askenazi A.Building beter products with finite element analysis [M].[S.l.]:Thomson Learning，1998.

# Design and Mechanics Analysis for a Space-Based Detection Scheme of DSO Primary Optical Telescope

Wang Qiang，Hu Qiqian，Ni Houkun， Zhang Haiying (NationalAstronomical Observatories/Nanjing Instituteof Astronomical OpticsandTechnology，ChineseAcademyof Sciences, Nanjing 210o42,China，Email：qiangwang@niaot.ac.cn)

Abstract:In order to demonstrate whether the truss system of the main optical telescope of the Deepspace Solar Observatory could live through the relentless launch condition and remain working during the launch period，and to demonstrate whether it is necessary to build a space-based adjusting system for the Deep-space Solar Observatory so thatthe relative position of the main mirror and the colimator could be kept accurately，this thesis put forward a feasible space-based detection scheme，and made static stress analysis , dynamic load analysis，the modal analysis and response spectrum analysis of the truss system，which were to analyze the structural safety，and discovered that the truss system needed structures of vibration atenuation to reduce the response of POGO.This demonstrated preliminarily the necesity and the feasibility of the spacebased adjusting scheme，verified preliminarily the correctnessof the structure design and the technological process.This thesis also provided the test procedure of the Sinusoidal Vibration Test and the space-based detection test，which provided the necessary contrast data and basic work of the next vibration test technically. Key words: Mechanics analysis；Space-based detection； Static stress；Dynamic load； Vibration response