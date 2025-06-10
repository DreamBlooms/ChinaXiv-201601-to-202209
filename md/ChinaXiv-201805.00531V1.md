# 26米天线座架温度分布规律及变形影响分析

王惠，宁云炜，闫浩

（1.中国科学院新疆天文台，新疆乌鲁木齐，830011)

摘要：为满足大口径地面射电望远镜的高精度要求，开展射电望远镜热影响研究，保持结构的热稳定性，对提高望远镜指向精度有重要意义。以改造后南山 $2 6 \mathrm { m }$ 天线为研究对象，利用FEMAP软件建立座架结构模型，设定边界条件，得到某年6月4日全天各时刻天线座架上的温度场分布,将温度场结果与结构耦合，得到热变形，建立了温度测量系统，与仿真结果相比，当天局部最大温度可达 $3 1 . 3 3 ^ { \circ } \mathsf { C } ,$ 最大温差可达 $1 0 ^ { \circ } \mathsf C ,$ 最大位移量可达 $1 . 8 \mathrm { m m }$ ，与实测结果变化规律基本一致，分析座架温度分布规律及其变形影响，为后期天线的温度补偿和结构优化提供参考依据。

关键词：射电望远镜；指向精度；温度场；座架；仿真分析中图分类号：P111.44 文献标识码：A文章编号:1672-7673(2018)

为满足我国航天和天文学研究飞速发展的需要，望远镜朝高精度、大型化方向发展，对如此大型精密机械仪器，控制其精度对实现天线各性能指标有重要意义。重力、温度和风荷载等影响望远镜面形精度和指向精度。国内外对重力等因素已经有了很多研究，基本得到控制解决的方案[1-3]，而温度和风载荷具有不确定性和瞬时性，难以进行准确分析和控制。温度载荷工况包括季节性均匀温度变化和日照作用下非均匀温度变化，不同的载荷工况导致焦距误差、指向误差和面形误差等，这些对大口径射电望远镜都是不能忽视的，在以往的测量过程中发现,太阳照射对天线结构的影响非常明显[4]，天马 $6 5 \mathrm { m }$ 曾在报告中指出， $6 5 \mathrm { m }$ 量级的天线在日常观测中，温度能够造成 $2 0 ^ { \prime \prime } – 3 0 ^ { \prime \prime }$ 的指向变化，所以对大口径射电望远镜的热分析研究非常有意义。

座架的变形对天线指向的影响比较大，主要体现在太阳直接照射位置温度较高，没有被直接照射或者被遮挡的位置温度较低，由此产生的温差引起天线座架俯仰、方位轴的倾斜，导致俯仰、方位的指向误差。为满足中国绕月探测工程VLBI测轨系统、火星探测、国内VLBI网及其它的观测任务，南山 $2 6 \mathrm { m }$ 望远镜进行了改造。本文使用改造后的南山26m射电望远镜作为具体分析对象，研究天线座架处于一天不同时刻，考虑太阳辐射、热传导、对流和遮挡情况下，天线座架温度分布情况，同时分析温度导致的座架热变形情况，并且跟实测结果进行对比，发现变化规律基本一致。

1天线结构温度场分析方法

1.1基本原理

天线结构热分析遵循热力学第一定律一能量守恒定律[7。瞬态热分析的能量平衡方程为

其中，为包含导热系数、形状系数、对流系数、辐射率系数的传导矩阵；T为节点温度向量；为考虑系数内能增加的比热矩阵；为对时间的一阶导数；为包含热生成的节点热流率向量。通过Femap有限元分析软件，利用模型尺寸参数、热物性参数以及边界条件，可生成。

# 1.2热传递方式

对于地面射电望远镜，在没有防护结构的情况下，温度场包括热传导、热对流及热辐射3种传递方式：（1）热传导：热量由物体高温部分传到低温部分，即天线结构间由于温度梯度而引起的内能交换；（2）热对流：热量通过流动介质的传播，即天线结构表面与周围空气之间由于温度不均引起的热量交换，对流可分为自然对流和强迫对流，本文主要考虑自然对流；（3）热辐射：热辐射指具有温度的物体发射电磁波的现象。物体温度越高，单位时间辐射的热量越多，且无需任何介质。热对流和热辐射以外荷载的形式施加于结构之上，而热传导属于结构内部的热量传递。地面望远镜与周围环境发生热交换主要包括：与空气、地面、天空的辐射换热，吸收的太阳辐射。

# 2天线结构及分析流程

2.1天线结构

以南山 $2 6 \mathrm { m }$ 天线作为分析对象，它由天线反射体、A-E型轮轨式座架、天线俯仰组合、天线方位组合、高频房、天线安全保护装置、副面旋转装置、平台扶梯等组成。具体参数为：主反射面直径 $2 6 \mathrm { m }$ ，副反射面直径 $3 \mathrm { m }$ ，主副反射面焦径比：，主反射面分为6圈，共计304块面板；背架包括16根辐射梁，中心体为正八边形棱柱体，8根伞形支撑，连接支撑到与俯仰轴成 $\pm 4 5 ^ { \circ }$ 、 $\pm 6 7 . 5 ^ { \circ }$ 的中心体底部外轮廓上，以加强中心体及天线反射体刚度的支撑刚度。副面撑杆采用空间桁架截面，分别固接在辐射梁的相应上弦节点。

# 2.2座架模型

假定天线座架位于方位0方向，即座架面向正北方向，确定天线尺寸参数，设定材料参数，利用FEMAP软件建模。本文座架结构材料是 $1 6 \mathrm { M n }$ ，选用梁单元建模，并设定材料各向同性，各材料属性如表1，初始温度为 $2 0 ^ { \circ } \mathsf { C } _ { \circ }$ 不同的热控涂层由于其吸收率和发射率的不同8，将会影响天线表面温度分布。天线选用的表面涂层为富锌底，白色醇酸漆，吸收率为0.18，发射率为0.80。

表1座架材料参数Tab.1Frame material parameters  

<html><body><table><tr><td>密度kg/m</td><td>泊松比</td><td>导热系数W/(m·K)</td><td>比热J/ (kg·K)</td><td>弹性模量N/m²</td><td>线性膨胀系数1/C</td></tr><tr><td>7870</td><td>0.31</td><td>52.34</td><td>480</td><td>2.12E+11</td><td>1.28E-05</td></tr><tr><td>7.87e-9t/mm³</td><td>0.31</td><td>0.05234W/(mm ·C)</td><td>0.48mj/(t ·c)</td><td>2.12e5N/mm²</td><td>1.28E-05</td></tr></table></body></html>

![](images/eca597fa588b601124c33c38f9d9ebc2bf9fd795beefe09a4daa31d0246ba2b1.jpg)  
图 $1 2 6 \mathrm { m }$ 天线座架模型图26月4日气温变化曲线Fig.1 26m Antenna frame modelFig.2 June 4 temperature curve2.3环境条件

天线位于乌鲁木齐南山站，地理位置是北纬 $4 3 ^ { \circ } 2 8 ^ { \prime } 1 5 ^ { \prime \prime }$ ，东经 $8 7 ^ { \circ } 1 1 ^ { \prime } 3 3 ^ { \prime \prime }$ 。选择某年6月4日作为分析时间。图2是当天(该天天气晴朗无云)前后连续25个时刻的气温变化曲线。当天的环境温度数据来源于当地环境温度监测传感器记录的数据。分析中使用当地时间，与北京时间相差两小时。对流换热系数的影响因素很多，例如结构外形、海拔高度、风速、空气密度等，本文考虑天线在无风的条件下，根据经验，对流换热系数由下式确定，设定为 $5 . 6 \mathrm { W } / \mathrm { m } ^ { \wedge } 2$ 。

# 2.4分析流程

利用 Femap 软件中的TMG Thermal Analysis 模块，它具有地面太阳辐射模块，自动提供了太阳这个随时间变化的热源，并给用户提供空气散射、反射、轨道属性、计算时间、阴影检测等方便易用的接口数据，便于计算地球上某纬度物体在太阳辐射下的温度场。

对模型进行网格划分后，在TMGThermalAnalysis 模块中，进行热分析的环境与边界条件设定（Boundarycondition），包括定义辐射控制（Radiation Request）、环境条件（Environment Temperature）、自然对流耦合（Convective）、昼间太阳加热（DiurnalHeating）、天线所处纬度、天线朝向(如前所述)等条件[9-]。分析中使用乌鲁木齐当地时间。

# 2.5温度分布与变形计算

在对热分析模型进行求解后，通过提取温度结果，在后处理中可得到24个时刻的座架温度分布云图(图3)，以及相对应的温度数值结果。

![](images/b46cf8712a49554a45364f112a2ad5e376da61d9f5b8b203bede552fa44ac3f5.jpg)  
图3不同时刻座架温度分布云图Fig.3 Temperature distributionat different times

设定参考温度为 $2 0 ^ { \circ } \mathsf { C } ,$ 定义位移约束等边界条件即将底边4点固定，提取不同时刻的温度场结果中各节点温度，作为静力学分析的输入载荷，施加在结构分析模型的各个节点上，从而将热分析模型和结构分析模型有机联系起来，以对结构热变形分布等进行解算分析。最终求解后，可以分别得到24个时刻的热变形，其部分结果如图4。

![](images/b1062ab8e2f962a345a70aa3a4754c77158c4ff48b50d31aead8c8320cecf30a.jpg)

![](images/4319d45ceda75548cac05720b93e33743e6302a5a2deee1ac134b13c25a1dd1f.jpg)  
图4不同时刻座架热变形Fig.4Thermal deformationat different times

2.5温度采集系统

为验证分析模型的准确性以及后期指向模型的建立，在座架结构上安装了32个DS18B20温度传感器。传感器由铜片通过磁铁压在座架表面，外罩不透光塑料盒，能较为准确地反应结构表面的温度变化。

![](images/892c706f5a35f03ffc2ba24c16383b074d380c6563ec8e71a87735e043dde1b4.jpg)  
图5温度采集系统图6实物图 Fig.5 Temperature acquisition systemFig.6 photo of the sensol

# 3结论

从图3可以看出,座架上各条梁温度随太阳位置的变化呈现对应的变化规律，因为太阳在乌鲁木齐时间4点半（北京时间6点半）左右升起，所以在5点钟前各条梁温度趋于一致，都在初始温度 $1 0 ^ { \circ } \mathsf { C }$ 左右。随着太阳升起，座架东侧的各条梁温度开始上升，随着太阳

的转动，高温区域自西向东移动。乌鲁木齐时间19点40（北京时间21点40）以后，太阳落下，各梁温度又逐渐趋于一致，在 $1 5 ^ { \circ } \mathsf { C }$ 左右。

# 图7各时刻温度分布曲线

图5是各个时间点的瞬态温度分布曲线，可以看到在18点各梁温度达到局部最大$3 1 . 3 3 ^ { \circ } \mathsf { C }$ 在4点到18点这段时间呈现上升趋势，主要是太阳辐射强度增强，之后到太阳落下之前都在减小。而各梁的最大温度差只是在太阳升起和落下的一段时间内呈增大趋势，中间一段时间内基本保持不变，温差最大可达 $1 0 ^ { \circ } \mathsf C _ { \circ }$ 对比实测温度曲线，发现与仿真值有一定偏差，一是因为仿真中设置的一些固定参数值，不能随着环境随时变化，二是由于仿真中未考虑反射体部分的遮挡，导致仿真结果与实际测量值有一定偏差，但两者变化规律基本一致。

# 图8各时刻最大位移量

Fig.8Displacementat different times

图4是座架不同时刻的热变形，列出了日出到日落这段时间的热变形情况。可以看到热变形引起座架的倾斜，从而导致俯仰、方位的指向偏差，图6是不同时刻的座架节点最大位移量，可以看到最大位移量与各时刻最大温度有关系，在乌鲁木齐时间14点时达到最大$1 . 8 \mathrm { m m }$ 。

5结束语

本文针对南山26m天线座架进行了热仿真分析，得到了太阳照射下座架温度场分布规律以及热变形的影响，但在仿真过程中并没有考虑风速影响，也并未考虑反射体部分影响，且使用了经验公式，仿真结果与实测数据有一定偏差，但基本能够反映一天中座架温度变化规律。进一步将利用安装的温度传感器进行北极附近源跟踪测量实验，积累数据，建立指向一座架温度修正模型，为之后的温度补偿提供依据。

# 参考文献

[1]Greve A, Bremer M. Thermal design and thermal behaviour of radio telescopes and their enclosures[M]. Berlin: Springer, 2010.   
[2]Mangum JG, Baars J W M, Greve A, et al. Evaluation of the ALMA prototype antennas[J]. Publications of the Astronomical Society of the Pacific, 2006,118(847): 1257-1301.   
[3]Ukita N. Thermal effects on the pointing of the Nobeyama 45-m telescope[J]. Publications of the National Astronomical Observatory of Japan,1999,5 （4） : 139- 147.   
[4]李永江,艾力,玉苏甫,张正禄，等.天线轨道变形精密测量与指向偏差模型研 究[J].武汉大学学报:信息科学版,2013,38(2):176-180.   
Li Yongjiang,AiliYusup,Zhang Zhenglu,et al.Antenna track deformation precise measurement and pointing errormodel[J].Geomatics and Information Science of Wuhan University,2013,38(2) :176-180.   
[5]常文文,艾力,玉苏甫,许谦等.基于有限元方法的 $2 5 \mathrm { m }$ 天线座架结构热特性分 析[J].机械科学与技术,2015,34(5):812-816.   
Chang Wenwen， AiliYusup， Xu Qian. Thermal characteristics analysis of $2 5 \mathrm { m }$ antenna mounts based on the finite element method[J]. Mechanical Science and Technology for Aerospace Engineering, 2015,34 (5): 812-816.   
[6]刘岩,钱宏亮,范峰.巨型射电望远镜结构日照非均匀温度场特性[J].建筑科学与 工程学报,2015,32(3):81-88. Liu Yan,Qian Hong-liang,Fan Feng. Characteristics of non-uniform solar temperature field for large radio telescope structure[J].Journal of Architecture and Civil   
Engineering.2015, 32(3):81-88.   
[7]孔祥谦.有限元法在热传导学中的应用[M]．北京：科学出版社，1998.   
[8] Long L E, Lum JL. Thermal control coating: U.S. Patent 5,589,274[P]. 1996-12- 31.   
[9]王从思,刘鑫,王伟,等.大型反射面天线温度分布规律及变形影响分析[J].宇航学 报.2013,(11):1523-1528.   
Wang Congsi, Liu Xin, Wang Wei, et al, Analysis method for temperature distribution characteristic and thermal distortion of large reflector antennas[J].Journal of   
Astronautics,2013,(11):1523-1228.   
[10]连培园,朱敏波,王伟,等.一种轴对称反射面天线温度场实时预估方法[J].机械 工程学报,2015,51(6):165-172.   
LianPeiyuan, Zhu Minbo, Wang Wei, et al. Estimation method of temperature field of large axial symmetric reflector antenna in real-time[J]. Journal of Mechanical Engineering,2015,51(6):165-172.   
[11]常文文,艾力,玉苏甫.基于ASHRAE 晴空模型的25米天线面板热特性分析 [J].天文研究与技术,2015,12（1）：23-29.   
Chang Wenwen， Aili Yusup.An analysis of thermal characteristics of the dish of a $2 5 \mathrm { m }$ radio antenna based on the ASHRAE clear-sky model [J]. Astronomy Research and Technology, 2015, 12(1): 23-29.

# Temperature Distribution and Deformation Impact Analysis of 26m Antenna Frame

Wang Hui'，Ning Yunwei，Yan Hao (Xinjiang Astronomical Observatory， Chinese Academy of Sciences, Urumqi， 830011)

Abstract: Studying the thermal influence of radio telescope and maintaining the thermal stability of the structure are important to meet the high precision requirements of large diameter ground radio telescope, Taking NanShan $2 6 \mathrm { m }$ antenna as the object, the FEMAP software was used to establish the frame structure model, and the boundary conditions were set. Then the temperature field distribution of the antenna of the day of June 4 are obtained,then coupled with the structure to obtain the thermal deformation. A temperature measurement system was established to compare with the simulation results,The results show that the local maximum temperature is $3 1 . 3 3 ^ { \circ } \mathsf { C }$ the maximum temperature difference can be up to $1 0 ^ { \circ } \mathsf { C }$ the maximum displacement can reach $1 . 8 \mathrm { m m }$ ,Which is consistent with the variation of measured results. Studying the temperature distribution anddeformation efects of the frame,which provides a reference for temperature compensation and the optimization of the structure.

Key words : radio telescope ； pointing accuracy ； temperature field； frame ； simulationanalysis