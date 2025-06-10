# GIS母线用热补偿型波纹管伸缩量设计分析

贾耿锋　李　军²　蒋晓旭 郅啸² 郭煜敬 闫建欣2（1.平高集团有限公司 平顶山 4670012.国网青海省电力公司检修公司西宁 810008）

贾耿锋男 1987年生，工程师，从事高压断路器灭弧室开发研究工作。

摘要：由于GIS母线用热补偿型波纹管设计存在的问题，导致变电站运维过程中不能补偿由于温度变化引起的筒体变形，造成固定支撑产生裂纹或开裂。针对以上问题，分析GIS母线用波纹管变形的主要因素和设计原则，通过电磁场与温度场的耦合仿真计算，确定GIS 筒体在额定电流下的温升，为波纹管伸缩量设计提供关键参数，并通过试验进行验证。试验结果表明：仿真计算结果与温升试验结果一致，能够为波纹管设计提供可靠的理论依据。

关键词：GIS 母线波纹管 伸缩量 电磁场 温度场中图分类号：TM216

# The Analysis of Expansion Amount Calculation of Thermal Compensation Bellows for GIS Busbar

![](images/7ba76b0ee7e9991b43d71a16db7e0980419bfdc0278c5eb006491d59e3d40084.jpg)

Jia Gengfeng' Li Jun²Jiang Xiaoxu'Zhi Xiao²Guo Yujing' Yan Jianxin (1.Pinggao Group Co.,Ltd. Pingdingshan 467001 China 2. Maintenance of Company of Qinghai Electric Company Xining 810008 China）

![](images/fccaed23a2c0f0b26d4a54d7382a9dc2a19d2f1d756d0db75cb1487680c84976.jpg)  
收稿日期：2016-07-11

李军男1974年生，高级工程师，从事高电压与绝缘领域的研究工作。

Abstract: Due to the problems in design of the thermal compensation bellows for GIS busbar， the deformation caused by the temperature changing can't be eliminated in the substation operation process，and cracking can be found in the fixed support. To solve the problems,the major factors of deformation and principles are analyzed in the design of busbar bellow.By the united simulation in electromagnetic and temperature field, the temperature rise of the GIS cylinder is determined under the rated current, and the critical parameter is provided for the design of the bellow. The experimental results also conform the analysis and the calculation are acquired.The results show that the simulation of the temperature rise is consistent with the test,the theory evidence is provided for the reliability design of bellows.

Keywords: GIS busbar, bellow, expansion amount, electromagnetic field, temperature field

# 1 引言

由于GIS开关设备具有占地面积小、可靠性高以及免维护等优点，因此在电网建设中得到越来越多的应用[1-2]。但GIS设备在运行中受到周围温度的变化，使得GIS筒体及筒体的固定支撑处要承受温度变化产生的热应变和应力，特别是在大温差地区，电站中GIS的固定处容易出现固定支撑开裂问题，严重时甚至导致GIS中气体的泄漏。

GIS 设备为解决温度变化产生的热应力，通常在设备中设置热补偿型波纹管，以补偿温度变化产生的应力及应变，而波纹管伸缩量的设计将对GIS设备的固定强度具有重要的影响，特别是在高海拔大温差地区，由于较大的昼夜温差造成温度应力很大，容易造成GIS固定支撑开裂问题。

为此本文将研究波纹管伸缩量设计原则，通过研究GIS母线在额定电流下的电磁场分布，确定由通流所产生的筒体温升；再根据不同地区温度变化，设计GIS热补偿型波纹管的伸缩量，从而保证GIS开关设备安全可靠的运行。

# 2 GIS热补偿型波纹管伸缩量设计原则

GIS 热补偿型波纹管伸缩量的设计将直接影响GIS设备运行的安全性，特别是在高海拔大温差地区变电站中，由波纹管设计及安装导致GIS母线支撑开裂的问题较为常见，表1为2013年青海省桃园变电站 $1 1 0 \mathrm { k V }$ 设备部分时间段支撑开裂的检测情况，图1为青海省桃园变电站 $1 2 6 \mathrm { { k V } }$ GIS母线固定支撑的开裂情况。

表12013年桃园变电站110kV设备支撑开裂部分数据

Tab.1The part of data statistics of cracking of Taoyuan substation in 2013   

<html><body><table><tr><td>检测时间</td><td>开裂位置</td></tr><tr><td>2月29日</td><td>Ⅲ母1气室与2气室之间母线支架</td></tr><tr><td>3月12日</td><td>I母开关西侧支架</td></tr><tr><td>4月12日</td><td>Ⅲ母1气室刀开关端子箱处母线支架</td></tr><tr><td>5月22日</td><td>Ⅲ母7气室处母线支架</td></tr></table></body></html>

由图1可以看出，由环境温度带来的变形和应力对GIS设备的影响较大，固定支撑处的开裂逐步发展，可能导致 ${ \mathrm { S F } } _ { 6 }$ 气体泄漏，甚至造成电网事故[3]。因此在GIS开关设备中安装波纹管及其设计十分重要。

GIS热补偿型波纹管伸缩量由两固定支撑间筒体的最大变形决定，波纹管安装的简化模型如图2所示。

![](images/6dfec813e8c2268e2f2a669e644b3d0558357aeb997f41178def93f7371f0da2.jpg)  
图1温度变化导致的固定支撑开裂

![](images/a0b164950393c89f0cd216dd0f00ed040e7871b83ea191df7d8f7ce4cb4d7202.jpg)  
Fig.1Cracking of the support with the change of temperature   
图2波纹管安装位置示意图  
Fig.2Diagram of the installation position of the bellows

由变电站运维经验可知，一般情况下GIS变形主要由温度变化引起，个别地区还受地区地基沉降的影响，本文研究筒体变形时不考虑地区沉降因素，因此GIS筒体变形的影响因素主要有GIS安装地区的温度范围、GIS现场安装的温度范围、GIS额定电流下的温升、光照引起的筒体最大温升以及两固定支撑间的距离[4]。温度变化引起GIS轴向长度的变化量[5-9]为

$$
\Delta l = \alpha l \Delta T
$$

式中， $l$ 为GIS原长； $\alpha$ 为筒体材料的线膨胀系数；  
$\Delta T$ 为温度改变量。

由式（1）可得波纹管伸缩量计算式为

$$
\Delta L _ { _ { \parallel \parallel } } = [ \alpha _ { 1 } ( K _ { _ { \mathrm { 1 m a x } } } - K _ { 2 \operatorname* { m i n } } + K _ { _ { m 1 } } + K _ { _ { m 2 } } ) -
$$

$$
\alpha _ { 2 } ( K _ { \mathrm { l m a x } } - K _ { 2 \operatorname* { m i n } } ) ] L
$$

$$
\Delta L _ { \ � } = [ \alpha _ { 1 } ( K _ { 2 \operatorname* { m a x } } - K _ { \operatorname* { m i n } } ) - \alpha _ { 2 } ( K _ { 2 \operatorname* { m a x } } - K _ { 2 \operatorname* { m i n } } ) ] L
$$

式中， $\alpha _ { 1 }$ ， $\alpha _ { 2 }$ 分别为筒体和地基的线膨胀系数；$K _ { \mathrm { 1 m a x } }$ 、 $K _ { \mathrm { 1 m i n } }$ 分别为该安装地区的最大温度和最小温度； $K _ { 2 \operatorname* { m a x } }$ 、 $K _ { 2 \mathrm { m i n } }$ 分别为现场安装的最大温度和最小温度； $K _ { \mathrm { m 1 } }$ 为额定电流引起的温升； $K _ { \mathrm { m } 2 }$ 为光照引起的温升。其中地区的温度范围、现场安装温度范围以及光照引起的筒体最大温升都是客观数据；而两固定支撑间的距离是由设备自身强度要求及挠度控制决定；GIS在额定电流下的温升则需要通过试验或者计算确定。下面将通过电磁场与温度场耦合仿真计算得到GIS在额定电流下的温升。

# 3 GIS母线电磁场分析计算

由于趋肤效应的存在，额定电流通过管状导体的阻抗和电流密度分布都会发生变化，通过GIS母线参数建立GIS单相母线模型如图3所示。

![](images/e57c3286783950a71dd356dd78de6aa5e93dcd554f309b961ed86d07ed4d111e.jpg)  
图3GIS单相母线模型

由电磁场方程可以得到电磁场计算方程[0]为

$$
\nabla \times ( \gamma \nabla \times \boldsymbol { A } ) = \boldsymbol { J } \quad \boldsymbol { J } \in \Omega _ { 0 }
$$

$$
A = A _ { 0 } A _ { 0 } \in \Omega _ { 1 }
$$

考虑筒体的涡流损耗，由式（4）可得

$$
\frac { \partial } { \partial x } \left( \mu \frac { \partial \pmb { A } } { \partial x } \right) + \frac { \partial } { \partial y } \left( \mu \frac { \partial \pmb { A } } { \partial y } \right) + \frac { \partial } { \partial z } \left( \mu \frac { \partial \pmb { A } } { \partial z } \right) = - J + \mathrm { j } w \sigma A
$$

式中， $A$ 为矢量磁位； $\mu$ 为非导磁材料的磁导率； $\sigma$ 为筒体的电导率； $\mathbf { \Omega } \Omega _ { 0 }$ 为求解区域； $\pmb { \Omega } _ { 1 }$ 为无穷远边界； $A _ { 0 } = 0$ 。

运用Workbench中的电磁场模块进行仿真计算，取母线中一小段建模，设定额定电流为 $4 ~ 0 0 0 \mathrm { A }$ ，频率为 $5 0 \mathrm { { H z } }$ ，进行电磁场计算，得到GIS母线电流密度分布如图4所示。

![](images/ec9a6fde6ed77777c56539e0ea0493fe6a088f4effbfa72704d9af88d991792a.jpg)  
Fig.3The model of the single-busbar of GIS   
图4GIS母线电流密度分布图  
Fig.4Distribution of the current density ofGIS busbar

计算结果见表2。

表2GIS母线电磁仿真计算结果  
Tab.2Results of the electromagnetic simulation of GIS busbar   

<html><body><table><tr><td rowspan="3">名称</td><td>导体最大</td><td>筒体最大</td><td>导体损耗</td><td>筒体损耗</td></tr><tr><td>电流密度</td><td>电流密度</td><td></td><td></td></tr><tr><td>/(A/mm2)</td><td>/(A/mm2)</td><td>/(W/m)</td><td>/(W/m)</td></tr><tr><td>计算数值</td><td>1.22</td><td>0.31</td><td>87.43</td><td>13.16</td></tr></table></body></html>

# 4 GIS母线温度场分析计算

# 4.1GIS电磁场与温度场耦合计算

通过GIS的电磁场计算，得到导体及筒体在额定电流下的电流密度分布，由于导体及筒体都会产生损耗发热，为了简化计算，采用二维温度场进行计算，其截面损耗功率计算方程组[11-13]为

$$
\left\{ \begin{array} { l l } { I _ { \mathrm { e } } = \displaystyle \iiint J _ { \mathrm { e } } \mathrm { d } x \mathrm { d } y } \\ { \displaystyle P _ { \mathrm { e } } = I _ { \mathrm { e } } ^ { 2 } \frac { L _ { \mathrm { e } } } { \sigma S } } \end{array} \right.
$$

式中， $I _ { \mathrm { e } }$ 为有限元剖分单元格的电流； $J _ { \mathrm { e } }$ 为有限元剖分单元格的电流密度； $L _ { \mathrm { e } }$ 为母线的轴向长度。

导体及筒体的损耗发热作为热源进行热量传递。导体与 ${ \mathrm { S F } } _ { 6 }$ 、筒体与外界空气进行传导换热，其计算公式[14-15]为

$$
q _ { 1 } = h \Delta t
$$

式中， $h$ 为对流换热系数； $\Delta t$ 为两传递体的温度差。

${ \mathrm { S F } } _ { 6 }$ 气体以辐射和自然对流的方式进行热量传递，辐射计算公式为

$$
q _ { 2 } = \varepsilon A \sigma T ^ { 4 }
$$

式中， $\mathbf { \sigma } _ { \varepsilon }$ 为物体表面的辐射率； $\sigma$ 为玻尔兹曼常数；  
$T$ 为物体的热力学温度。

气体自然对流遵循以下方程质量守恒

$$
\frac { \partial ( \rho u ) } { \partial x } + \frac { \partial ( \rho \nu ) } { \partial y } = 0
$$

能量守恒方程

$$
\rho c u { \frac { \partial T _ { \mathrm { g } } } { \partial x } } + \rho c \nu { \frac { \partial T _ { \mathrm { g } } } { \partial y } } = { \frac { \partial } { \partial x } } { \left( \lambda { \frac { \partial T _ { \mathrm { g } } } { \partial x } } \right) } + { \frac { \partial } { \partial y } } { \left( \lambda { \frac { \partial t } { \partial y } } \right) } + q _ { \mathrm { v } }
$$

动量守恒方程

$$
\rho \left( u \frac { \partial u } { \partial x } + \nu \frac { \partial u } { \partial y } \right) = - \frac { \partial p } { \partial x } + \frac { \partial } { \partial x } \left( \eta \frac { \partial u } { \partial x } \right) + \frac { \partial } { \partial y } \left( \eta \frac { \partial u } { \partial y } \right)
$$

$$
\rho \left( u \frac { \partial \nu } { \partial x } + \nu \frac { \partial \nu } { \partial y } \right) = - \frac { \partial p } { \partial y } + \frac { \partial } { \partial x } \left( \eta \frac { \partial \nu } { \partial x } \right) + \frac { \partial } { \partial y } \left( \eta \frac { \partial \nu } { \partial y } \right) + \rho g \beta \Delta t
$$

式中， $\rho$ 为 ${ \mathrm { S F } } _ { 6 }$ 密度； $u$ 为气体速度在 $x$ 方向的分量； $\nu$ 为气体速度在 $y$ 方向的分量； $\mathbf { \Psi } _ { c }$ 为比热容； $T _ { \mathrm { g } }$ 为气体温度； $q _ { \mathrm { v } }$ 为单位时间内单位体积所发出的热流量； $\eta$ 为 ${ \mathrm { S F } } _ { 6 }$ 气体运动粘度； $p$ 为 ${ \mathrm { S F } } _ { 6 }$ 压力； $g$ 为重力加速度； $\beta$ 为膨胀系数； $\Delta t$ 为冷热面温差。

采用电磁场-温度场耦合计算，在Workbench中将电磁模块与流体温度场进行耦合，将电磁产生的损耗导入流体场中作为温度场计算的热源；导体面设置相应的辐射系数，筒体表面设置与实际相应的对流换热系数，不同环境的对流换热系数不同，本次对流换热系数取值为以往相同试验环境下试验仿真结果的修正值。包围模型的空气边界可作为恒温处理，不受热源影响，为与后续试验验证，将初始温度以及远场单元设置为环境温度 $1 4 ^ { \circ } \mathrm { C }$ ，即286K，计算得到GIS母线温度分布如图5所示。

![](images/843f7577070c9ec1c45a82e573adbd89724e930bd08ec67248bbdf284577c461.jpg)  
图5额定电流下的GIS温度分布Fig.5Distribution of temperature of GIS underthe rated current

计算可得筒体温度为307.7K，即筒体由额定电流产生的温升为21.7K。

# 4.2GIS母线温升试验验证

为验证GIS母线在额定电流下筒体的温升计算方法，进行GIS温升试验，试验原理如图6所示。

图6中，调压器提供试验电源，升流器提供试品温升试验所需试验电流，传感器用于监测试品所通电流的数值，当温升试验在额定电流值持续足够长时间以使得温升达到稳定值（通常如果在1h内温升变化不超过1K)，则认为试验已达到稳定状态[16]。

根据温升试验原理，用相同尺寸的GIS母线进行额定电流下的温升试验，搭建试验装置及温升埋点如图7、图8所示。

![](images/eacfaf02af02ded9666260771b0787fd4bdc33f1cf4f5d35f2e9c49296a8c852.jpg)  
图6GIS母线温升试验原理图

![](images/5b45281b4d30f19d1e4ae06afc12a57d3761d5a8aecdf26e7fc3831f7b110ecf.jpg)  
Fig.6The diagram of temperature-rise test   
图7GIS 母线温升试验

![](images/887bfe4e553f053e3aaec71ab9e9a08b61a39fede10352986d7e91963d17a1b2.jpg)  
Fig.7Temperature-rise test ofGIS busbar   
图8 GIS 母线温升埋点  
Fig.8Burying point of temperature ofGIS busbar

标准GB/T11022—2011中规定：试验时周围空气温度应高于 $+ 1 0 \mathrm { { ^ { \circ } C } }$ ，但低于 $+ 4 0 ^ { \circ } \mathrm { C }$ [17]。本次温升试验环境温度约为 $1 4 ^ { \circ } \mathrm { C }$ ，符合试验要求。按照GB/T11022—2011温升试验规定进行试验，最终得到筒体的温度见表3。

表3GIS母线筒体温升试验结果  
Tab.3 Results of the temperature-rise test of GIS busbar   

<html><body><table><tr><td>筒体</td><td>点1</td><td>点2</td><td>点3</td><td>点4</td><td>点5</td><td>均值</td></tr><tr><td>温度/℃</td><td>34.6</td><td>34.8</td><td>35.3</td><td>35</td><td>34.6</td><td>34.82</td></tr><tr><td>温升/K</td><td>20.6</td><td>20.8</td><td>21.3</td><td>21.0</td><td>20.6</td><td>20.86</td></tr></table></body></html>

通过温升试验，得到GIS母线筒体的温升均值为20.86K，与计算值较为接近，验证了额定电流下筒体温升仿真计算在波纹管设计中应用的可行性。

# 5 波纹管伸缩量计算示例

通过计算额定电流时的筒体温升值，可计算GIS 热补偿型波纹管所需的伸缩量，下面举例说明。

设GIS的温度条件如下： $\textcircled{1}$ 周围温度： $- 4 0 \sim$ $4 0 ^ { \circ } \mathrm { C }$ ； $\textcircled{2}$ 安装时周围温度： $5 \sim 3 2 ^ { \circ } \mathrm { C }$ ； $\textcircled{3}$ 光照引起筒体温升： $1 0 \mathrm { K }$ ； $\textcircled{4}$ 额定电流下筒体温升：21.7K；$\textcircled{5}$ 两固定支撑间距离： $1 0 \mathrm { m }$ 。

将以上条件代入式（1）、式(2)，可得GIS筒体最大伸长量为 $1 1 . 8 5 \mathrm { m m }$ ，最大收缩量为 $8 . 7 8 \mathrm { m m }$ 为保证安全系数，综合考虑GIS使用环境，波纹管伸缩量一般可设计为 $\pm 1 5 \mathrm { m m }$ 。

# 6 结束语

本文研究GIS母线用热补偿型波纹管伸缩量的设计，得到如下结论：（1）分析了GIS热补偿型波纹管伸缩量设计的重要型，提供了波纹管伸缩量的设计原则。(2）通过电磁场、流场及温度场耦合仿真计算，得到波纹管伸缩量设计中的关键因素，为波纹管设计提供重要参数。（3）通过额定电流下的GIS母线温升试验，验证了仿真分析方法的可靠性，为波纹管设计提供了强有力的试验支撑。

# 参考文献

[1] 尚振球，郭文元．高压电器[M]．西安：西安交通大学出版社，1992.  
[2] 黎斌. ${ \mathrm { S F } } _ { 6 }$ 高电压电器设计[M]．北京：机械工业出版社，2009.  
[3] 林莘．现代高电压技术[M]．北京：机械工业出版社，2011.  
[4] 中华人民共和国国家发展和改革委员会．JB/T10617—2006高压组合电器用金属波纹管补偿器[S]．北京：机械工业出版社，2007.  
[5] 宋帆，申春红，林莘，等． $8 0 0 \mathrm { k V }$ GIS 隔离开关磁场－温度场计算与分析[J]．高压电压技术，2008,34(7):1383-1388.Song Fan,Shen Chunhong,Lin Shen,et al.Calculation and analysis on magneto-thermalfields of $8 0 0 \mathrm { k V }$ GIS disconnector[J]. High VoltageEngineering,2008,34(7):1383-1388.  
[6] 范镇南，张德威，等．用电磁场和流场模型计算GIS 母线损耗发热[J]．高电压技术，2009，35(12)：3016-3021.Fan Zhennan,Zhang Dewei,et al. Calculation of lossand heat of GIS bus bar using electromagnetic feldand fluid field[J]. High Voltage Engineering,2009,35(12): 3016-3021.  
[7] 夏文，江洪，苏林英．126kVGIS产品主母线标准化设计[J]．高压电器，2009，45(6)：132-135.Xia Wen, Jiang Hong, Su Linying. 126kV main busstandardization design[J]. High Voltage Apparatus,2009, 45(6): 132-135.  
[8] 李大权，姜飞，万荣兴．关于 $8 0 0 \mathrm { k V }$ GIS 长距离母线筒位移研究[J]．电气技术，2012(5)：41-44.Li Daqun, Jiang Fei, Wan Rongxing. Study ondisplacement of $8 0 0 \mathrm { k V }$ GIS long-distance bus[J].Electrical Engineering,2012(5): 41-44.  
[9] 李海波，万荣兴，方勇．兰州东变电站750kVGIS 母线筒缺陷原因分析[J]．高压电器，2010,46(11): 12-15.Li Haibo, Wan Rongxing, Fang Yong. Defect analysisof the $7 5 0 ~ \mathrm { k V }$ GIS busbar tube of the Lanzhoudongsubstation[J]. High Voltage Apparatus, 2010, 46(11):12-15.  
[10]冯慈章，马西奎．工程电磁场导论[M]．北京：高等教育出版社，2000.  
[11]谢处方，饶克谨．电磁场与电磁波[M]．北京：高等教育出版社，2006.  
[12]范镇南，罗永刚．内部导体结构对GIS 母线损耗发热的影响[J]．电机与控制学报，2011，15(5)：22-27.Fan Zhennan, Luo Yonggang. Influences of the internalconductor structure to the loss and heat of GIS busbar[J].Electric Machine and Control, 2011,15(5): 22-27.  
[13]汪讽，康添慧，等．高压同轴GIS 母线三维磁-热耦合场的计算与分析[J]．湖南大学学报，2014,41(8): 73-77.Wang Feng, Kang Tianhui, et al. Analysis andcalculation of magnetic-thermal coupled field forhigh-voltage coaxial GIS busbar[J]. Journal of HunanUniversity (Natural Sciences),2014, 41(8): 73-77.  
[14]杨世铭，陶文钰．传热学[M]．北京：高等教育出版社，2006.  
[15] 陶文钰．数值传热学[M]．西安：西安交通大学出版社，2001.  
[16] 中国国家标准化管理委员会．GB1984—2014 高压交流断路器[S]．北京：中国标准出版社，2014.  
[17] 中国国家标准化管理委员会．GB/T11022—2011高压开关设备和控制设备标准的共用技术要求[S].北京：中国标准出版社，2012.