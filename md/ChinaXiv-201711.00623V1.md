# 离心泵非设计工况内部流动特性研究

高波 王兴宁 李忠 张宁 杨敏官（江苏大学能源与动力工程学院，江苏镇江212013）

摘要：本文以单级蜗壳式离心泵为研究对象，基于RANS 进行了全流场的非定常数值计算，探讨了叶轮的非定常流动特征，重点分析了叶轮出口沿轴向变化的圆周面流域内各节点的压力分布特性。结果表明：在叶片压力面及叶片后缘尾迹区发生了剧烈的湍流脉动现象；不同工况下叶轮出口圆周方向的压力系数 $C _ { p }$ 均在隔舌附近产生极值；额定工况 $\mathrm { { Q } / { Q _ { N } } = 1 }$ 时，叶轮出口圆周方向的压力系数 $C _ { p }$ 呈稳定周期性分布，随着工况的改变，压力系数 $C _ { p }$ 沿蜗壳周向分布不均匀性增加；小流量工况下叶轮流域内发生了明显的流动分离现象，流道内产生了较大尺度的分离涡，破坏了叶轮出口圆周方向压力系数 $C _ { p }$ 的周期性分布特性；叶轮出口圆周压力系数 $C _ { p }$ 沿中截面两侧的流域内几乎对称分布；在 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 小流量工况下，压力脉动频谱图低频段内出现了较多复杂的激励信号，认为这与流域内的分离涡结构具有一定关联。

关键词：离心泵；非定常流动；非定常压力分布；流动分离中图分类号：TH311 文献标识码：A 文章编·

# Study on the Internal Flow Characteristics of the Centrifugal Pump under Non-design Conditions

GAO Bo WANG Xing-Ning LI ZhongZHANG NingYANG Min-Guan (School of Energy and Power Engineering, Jiangsu University, Zhenjiang 212013, China)

Abstract: Set the single stage volute centrifugal pump as research object meanwhile based on the RANS to simulate the unsteady flow characteristics of the whole flow field,and then researched on the unsteady flow characteristics of the impeler, which focused on the pressure distribution and fluctuation characteristics of each node along the axial direction that changes in circumference field of impeler outlet. The results shows that: the phenomenon of intense turbulence pulsation happened in the pressure surface and the trailing edge of the blade; the pressure coefficient $C _ { p }$ in the circumferential direction of the impeller outlet reached to the extreme value around the tongue under different conditions; the pressure coefficient $C _ { p }$ in the circumferential direction of the impeller outlet has a stable periodic distribution under the rated condition, the non-uniformity of the pressure coefficient $C _ { p }$ along the circumferential direction increases while the working condition changed; the flow separation phenomenon occurrd obviously under smallflow rate condition and appeared large scale separation vortex which destroyed the periodic distribution of the impeler outlet pressure coefficient $C _ { p }$ along the circumferential direction. Complicated exciting signals were found in the pressure pulsation frequency graph at smallflow rate condition, which may related to the vortex structure in the pump.

Key words: Centrifugal pump; unsteady flow; unsteady pressure distribution; flow separation

# 0引言

离心泵作为一种基本的能量转换和流体运输装置广泛应用于工农业，航空推进和日常生活中[1]。不对称结构的蜗壳和高速旋转的叶轮，在流体间产生了动静干涉作用，导致离心泵的运行不稳定性及产生随时间变化的压力脉动[2-4]，这将对泵的性能产生影响并导致机械部件疲劳过度，引起振动和噪声。因此，深入分析离心泵内部的压力分布及脉动特性将成为迫切关注的焦点[5.6]。

国内外学者对离心泵内部不稳定流动进行了广泛研究，袁建平等采用LES 数值模拟了离心泵内部的非定常流动结构，认为内部压力脉动变化明显是由于动静干涉所致；Wang[8等基于LES 模型对离心泵叶片进口及蜗壳基圆线的压力脉动特性进行了数值研究及试验验证，沿蜗壳基圆各监测点的压力分布周期与叶片数一致。总的来说，由于离心泵内部的非稳态流场的复杂性，其内在机理仍处于计算探索和试验研究阶段。

本文基于RANS并采用 $\mathbf { k } { - } \omega$ 湍流模型对单级蜗壳式离心泵的内部流动进行了三维非定常的数值计算及分析，重点探讨了叶轮出口的非定常流动特性，同时采用统计法分析了叶轮出口沿轴向变化其圆周面内各节点的压力分布特性。通过不同工况下的对比分析，揭示了离心泵叶轮出口流域内的非定常流动特性，其结果可为离心泵内部非定常流动的研究提供一定的理论支撑。

# 1参数及数值计算方法

# 1.1 模型泵参数

文中所用离心泵基本性能参数如表1所示，叶轮和蜗壳的三维实体均采用 $\mathrm { P r o / E 5 . 0 }$ 造型。

表1.离心泵基本参数  
Tablel Basic parameters of centrifugal pump   

<html><body><table><tr><td>主要参数</td><td>数值</td></tr><tr><td>设计流量QN (m/h)</td><td>29</td></tr><tr><td>扬程H/m</td><td>9.8</td></tr><tr><td>转速n (r/min)</td><td>1450</td></tr><tr><td>比转速ns</td><td>86</td></tr><tr><td>叶片数Z</td><td>6</td></tr><tr><td>叶轮出口宽度b/mm</td><td>14</td></tr><tr><td>叶轮进口直径Dj/mm</td><td>80</td></tr><tr><td>叶轮出口直径Dz/mm</td><td>184</td></tr></table></body></html>

# 1.2 数值计算方法

# 1.2.1 网格划分及计算模型

整个模型由一个动叶轮水体、一个静止蜗壳水体及进出口延伸段组成，并将上述四个子域整体作为数值计算求解区域。

本文采用ICEM网格划分软件对整个计算域进行了结构化网格划分，整个流道区域所划分网格总数为1128281，其中叶轮部分网格数为566716，蜗壳部分网格为435128。经网格无关性检验可知，当网格数大于110万以后，随着网格数的增多，数值模拟的结果显示扬程和效率波动性很小。因此，计算采用的物理模型及离散格式具备了空间收敛性和数值稳定性，达到了计算的精度要求。数值计算区域的局部网格划分如图1所示，为了得到更为精准的数值计算结果，分别在流动区域径向截面所处位置如叶片周围及蜗壳隔舌等位置进行了网格的局部加密，一定程度上调整了网格的节点数。

![](images/d12f5974dd90478a826eb23ac196cc553bfd121f6f6e6c06c6363d9192c5b249.jpg)  
图1模型泵网格示意图

# 1.2.2 湍流模型的选择

为了研究不同湍流模型对计算结果的影响，本文分别采用标准 $\operatorname { k } \mathrm { - } \varepsilon$ 模型、 $\mathbf { k } - \omega$ 模型及SST模型对相同边界条件下泵的能量性能进行计算，并与模型泵的实验结果进行了比较分析。图2为模型泵在不同工况下采用四种湍流模型计算所得结果和实验结果进行对比，其中 ${ \psi { = } \mathrm { g H / u } _ { 2 } } ^ { 2 }$ 表示无量纲扬程系数，横坐标为运行工况点流量与额定流量的比值，由$\mathrm { { Q } / \mathrm { { Q } _ { N } } }$ 表示。

![](images/066f27ec5e223edd7fef4a028b15e4021e2fd9b4941024e204f95a56bf4e52d0.jpg)  
Figure.1 Mesh of the model pump   
图2模型泵性能曲线  
Figure.2 Performance characteristics of pump

通过对比发现，所采用的三种湍流模型计算所得能量性能曲线与试验结果在整体变化趋势上大体一致。当运行工况处于 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 6 { \sim } 1 . 2$ 范围内时，数值计算扬程值和试验结果吻合较好，最大误差小于$5 \%$ ；在大流量工况下，随着流量的增大，数值计算误差增大，但通过各模型所得计算结果之间却相差不大；此外，由效率特性曲线可以看出，与其它几个计算模型相比，小流量工况下 $\mathrm { ~ k ~ } - \omega$ 模型所得计算结果与试验结果吻合度最高，考虑到需针对离心泵外特性得到相对准确预测结果方面的需求，并综合计算的收敛性及误差等因素，最终湍流模型采用标准 $\mathrm { ~ k ~ } - \omega$ 模型。

# 2.2.3 边界条件

通过ANSYS CFX13.0 对离心泵计算域进行非定常流动计算，采用多重坐标系求解。壁面采用无滑移边界条件，近壁区域采用标准壁面函数处理，考虑到加工精度方面的有限性，对各壁面进行粗糙度定义为 $0 . 1 \mathrm { m m }$ 。进口采用速度进口边界条件，出口设置为自由出流。在进行非定常计算时，叶轮区域相对计算域其它网格运动，将动静交界面设置为瞬态动静转子模式，这对于计算动静干涉作用是至关重要的。非定常数值模拟将定常计算结果作为初始条件，取叶轮每旋转1°作为一个时间步长，即$\Delta \mathrm { T } { = } 1 . 1 4 9 { \times } 1 0 ^ { - 4 } s$ ，每计算360 步为叶轮旋转的1个周期。

# 3计算结果分析

# 3.1湍动能分布特性

为了较为直观的分析离心泵内部产生的周期性湍流脉动强度，根据文献定义了湍流强度系数Tu，计算式如下所示：

$$
T _ { \scriptscriptstyle u } ( x , y , \varphi ) = \frac { \sqrt { K ( x , y , \varphi ) } } { U _ { \scriptscriptstyle 2 } }
$$

式中 $K$ 表示湍动能， $U _ { 2 }$ 表示叶轮出口速度。

图3所示为 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 、1.4工况下离心泵叶轮中间截面处某时刻的湍动能强度系数 $T _ { u }$ 分布图，通过坐标对叶轮流域展开后得到。由图可以看出，在$\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 工况下在叶轮流域内叶片压力面附近的湍动能产生较为剧烈的变化，且叶片后缘尾迹区内湍动能变化较大，湍流不稳定性明显，此时发生了剧烈的湍流脉动现象，能量耗散较大。而与 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 工况相比较后可知， $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$ 时由于没有发生流动分离因而湍动能变化不大。

![](images/85d4ce9222ddd434de81ae984b2b3ccb8f74dde7f41152c7d7411a24593981b8.jpg)  
图 $3 . \mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 、1.4工况叶轮流道中间截面的湍流强度系数Figure.3 Parameter distributions on middle plane of the impellerunder $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ and 1.4

# 3.2叶轮出口的压力分布特性

本文所用压力分布采取了标准化形式，即定义了无量纲压力系数。通过计算基于叶轮圆周速度 $\mathrm { U } _ { 2 }$ 与压力标准化后的比值得到所求无量纲的压力系数$C _ { p }$ ,其中变量 $P _ { i } ( x , y , z , t )$ 用于表示计算流域内任意网格节点的压力，由此定义的无量纲压力系数[10] 如式（2）所示：

$$
C _ { P _ { i } } = \frac { \left( P _ { i } - P _ { r e f } \right) } { 0 . 5 \rho U _ { 2 } ^ { 2 } }
$$

为了得到叶轮旋转过程中叶轮出口圆周方向节点压力随时间的变化规律，通过全流域的非定常计算，得到如图4所示的离心泵中间截面处叶轮出口沿轴向变化的圆周面流域内各节点的压力分布特性沿圆周方向的压力系数 $C _ { p }$ 分布。由图可以看出在离心泵运行过程中，不同工况下的叶轮出口圆周方向所得压力系数 $C _ { p }$ 均在隔舌附近达到了极小值（图中出现极小值点为 $\theta = 2 6 ^ { \circ }$ 时)，通过分析可知这与隔舌处强烈的动静干涉作用相关；与小流量工况下所得压力系数分布曲线相比，在额定工况 $\mathrm { { Q } / { Q _ { \mathrm { { N } } } } = 1 }$ 时叶轮出口圆周方向的压力分布呈稳定的周期分布，其周期与叶片数一致，且各流道出口压力分布均匀；

![](images/855fb17e9dc386b7d204c21d11eb23231986a979ca0d6b27fc72b769ac65f981.jpg)  
图4.不同工况下叶轮出口圆周方向的压力系数分布

Figure.4Pressure parameter distributionsonthecylindrical directionaround theimpeller under different workingconditions

而小流量工况下， $\theta > 2 6 ^ { \circ }$ 时的压力系数 $C _ { p }$ 沿圆周方向出现增大的趋势，且 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 工况下更有压力分布周期性发生明显变化，叶轮出口一个流道内产生了两个峰值，这是因为小流量工况下流动较为复杂，叶轮流域内发生了明显的流动分离现象，流道内产生了涡流所致，从而破坏了流动的稳定性与周期性。

图5所示为与图4工况相对应的叶轮流域内的相对流速分布图，可以看出在小流量工况下叶轮流道内出现了大尺度的流动分离涡，分别位于叶片进口、叶片出口工作面及叶片出口背面，部分流道漩涡明显严重后时出现堵塞流道现象，而额定工况时明显看到相对流速分布均匀。

本文采用统计法分析了叶轮出口圆周沿叶片厚度变化的流域内各节点的压力分布特性，得到了$\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$ 工况时压力系数沿叶轮出口圆周面的分布如图6所示。从图中可以看出，叶轮出口圆周面的压力系数 $C _ { p }$ 在隔舌前后具有较大的压力梯度，与小流量工况相反，大流量工况叶轮出口圆周方向压力系数 $C _ { p }$ 在隔舌前表现为极小值，在隔舌附近出现了拐点，紧跟着出现的是压力系数 $C _ { p }$ 的极大值，而后压力系数 $C _ { p }$ 沿圆周方向呈递减趋势；总的来看，压力系数 $C _ { p }$ 的变化周期基本可划分为 $6 0 ^ { \circ }$ ，与叶片流道数一致。叶轮出口圆周压力系数 $C _ { p }$ 沿中截面两侧的流域内几乎对称分布。

![](images/3cd80e95adb0e7da8230d78b08e82d55dc12546583b266b5e0824907c60c2a03.jpg)  
图5.不同工况下叶轮流域内相对流速分布

![](images/f4124f865454afaa17b3ed2e2d71265eb6796bc9d04e30fdcc28d9ed1b5789ca.jpg)  
Figure.5The relative velocitydistribution in the impeller flow filed under different working conditions   
图 $6 . \mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$ 工况下叶轮出口圆周面的压力系数分布  
Figure.6 Pressure parameter distributions on the cylindrical surface around the impeller at $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$

# 3.3蜗壳测点的压力脉动频谱分析

为了分析蜗壳内部由于内流场的不稳定流动所引发的压力脉动特性随流量的变化情况，进行非定常流场计算时布置监测点进行时域信号的监测，并最终通过快速傅里叶变换得到对应的压力脉动频域图如图7所示，选取P4和P5测点分析非设计工况下的压力脉动特性，其中P4测点表示蜗壳第IV断面，P5测点表示的是蜗壳第ⅡI断面。频域图中横轴表示频率值f,纵轴表示各频率下对应的压力脉动幅值A。

本文所用叶轮的旋转速度 $\mathrm { n { = } 1 4 5 0 r / m i n }$ ，计算模型泵的轴频 $f _ { \mathrm { R } } { = } 2 4 . 2 \mathrm { H z }$ ，且叶轮叶片数 $Z { = } 6$ ，故 $f _ { \mathrm { B P F } } { = } 1 4 5 \mathrm { H z }$ 。从图7可以看出脉动幅值明显集中在低频区，压力脉动的主峰值对应的是叶片通过频率 $1 4 5 \mathrm { { H z } }$ 处，叶频1倍频率对应幅值明显高于高次谐波下幅值，即叶频占主导作用，且同时可以在叶频整数倍处发现叶频高次谐波处均对应着一定峰值。此外由图7还可看出，在 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 极小流量下，测点的压力脉动幅值较 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$ 工况较大，且低频段内出现了更多的激励频率信号，这与小流量工况下内流场的复杂流动特性相关，认为与流域内的分离涡结构具有一定关联。

![](images/883717f8432a081585e9767fcff677e9a5ac97b410de273948070aa0a3bd891e.jpg)  
(b） $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 1 . 4$ 工况下蜗壳测点压力脉动频谱图 图7.不同工况下P4、P5测点压力频谱图 Figure.7 Frequency domain signals of different conditions distributions at point4 and point5

# 4结论

1)不同工况下叶轮出口圆周方向的压力系数 $C _ { p }$ 均在 隔舌附近产生极值，在额定工况时，叶轮出口圆周 方向的压力系数 $C _ { p }$ 分布呈稳定周期性分布，且各流 道出口压力分布均匀，随着工况的改变，压力系数 $C _ { p }$ 沿蜗壳周向分布不均匀性增加。   
2）小流量工况下叶轮流域内发生了明显的流动分离 现象，流道内产生了较大尺度的分离涡，破坏了叶 轮出口圆周方向压力系数 $C _ { p }$ 的周期性分布特性; 3)叶轮出口圆周压力系数 $C _ { p }$ 在隔舌前后位置具有较 大的压力梯度，且 $C _ { p }$ 沿中截面两侧流域内几乎对称 分布；   
4）在 $\mathrm { Q } / \mathrm { Q } _ { \mathrm { N } } { = } 0 . 2$ 流量下，低频段内出现了更多复杂 的激励频率信号，认为与流域内的分离涡结构具有 一定关联。   
参考文献   
[1] C E Brennen, Hydrodynamics of Pumps, Oxford University Press,2011.   
[2] Raul Barrio,Jorge Parrondo,Eduardo Blanco.Numerical Analysis of the Unsteady Flow in the Near-Tongue Region in a Volute-type Centrifugal Pump for different Operating Points[J]. Compute and Fluids,2010,39: 859-870.   
[3] Q Z Liu,K Yang,D Y Liu eal.Research of fluid-induced pressure fluctuation due to impeller-volute interaction in a centrifugal pump[J]. Materials Science and Engineering 2013,52: 022026.   
[4] Spence R,Amaral-Teixeira J. A CFD parametric study of geometrical variations on the pressure pulsationsand performance characteristics of a centrifugal pump[J]. Compute Fluids,38(2009) 1243-1257.   
[5] R Dong, S Chu,and JKatz. Effect of modification to tongue andimpellergeometryonunsteadyflow, pressure fluctuations,and noise in a centrifugal pump.Journal of Turbomachinery.vol.119,no.3,pp.506-515,1997.   
[6] K A Kaupert and T Staubli. The unsteady pressure field in a high specific speed centrifugal pump impeller—part I: influence of the volute. Journal of Fluids Engineering.vol 121, no. 3,pp. 621-626,1999.   
[7] 袁建平，付燕霞，刘阳等．基于大涡模拟的离心泵蜗壳内 压力脉动特性分析[J]．排灌机械工程学报．2010,28(04): 310-314 YUAN Jianping,FU Yanxia, LIU Yang, et al. Analysis on pressure fluctuation within volute of centrifugal pump based on large eddy simulation[J].Journal of Drainage and Irrigation Machinery Engineering,2010,28(04): 310-314   
[8] W J Wang, YR Cui, Y Wang eal. Analysis on the blade inlet pressure fluctuation of the centrifugal pump based on LES[J]. Materials Science and Engineering.2013,52: 022025.   
[9] Feng J, Benra F-K, Dohmen H. Investigation of periodically unsteady flow in a radial pump by CFD simulations and LDV measurements [J].ASME Journal of Turbomachinery, 2011, 133(1) : 011004.   
[10] Ji Pei, Shouqi Yuan,Friedrich-Karl Benraetl．Numerical Predication of Unsteady Pressure Field Within the Whole Flow Passage of a Radial Single-Blade Pump[J]. Journal of Fluids Engineering.,2012,Vol. 134: 101103   
附：   
高波   
Add:江苏省镇江市学府路301号 江苏大学能源与动力工程学院 212013   
Tel:13921593118 0511—88783105   
E-mail: gaobo $@$ ujs.edu.cn