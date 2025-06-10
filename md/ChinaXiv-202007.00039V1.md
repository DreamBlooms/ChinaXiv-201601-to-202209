# 远程高精度测量设备性能评价方法研究

于东俊1，朱子暄²，宋本宁1，邓申雄1（中国科学院国家天文台，北京，100101北京师范大学附属实验中学，北京，100032）

摘要：随着激光测量技术的不断发展，有着"测量机器人"美誉的全站仪，在测量精度、灵活机动、快速便捷等方面，有着其它测量技术不可比拟的优势。全站仪作为"天眼"中主要的测量设备，在现场室外大尺度环境下，如何克服大气折射的影响，了解全站仪动态测量性能，实现高精密的快速扫描测量和高精度的动态跟踪测量，是其中的关键和难点所在。要克服测量过程中不确定因素影响，需了解其影响程度。本文内容包括介绍研发的“风琴式护罩运动平台、实验过程和数据分析方法。评价全站仪在现场环境下的测量精度和实时性，通过实验测试得到全站仪的时滞在195-295ms之间，测量精度约为 $5 . 3 \mathsf { m m }$ 。此结论为后续误差修正提供依据。

关键词：FAST，全站仪，运动平台，时滞，测量精度

# 1 引言

500米口径球面射电望远镜（FAST）是最大的单口径射电望远镜，拥有世界上最高的测量灵敏度，对于距离我们较为遥远的暗弱脉冲星、暗物质、暗能量的发现等具有重要意义，而要达到这样的灵敏度需要馈源和反射面高精度的测控技术保证。FAST高质量天文观测数据依赖于望远镜的高精度运行[]。汇聚信号的 500米口径反射面是实时变形的，运载信号接收系统的馈源支撑也实时跟踪运动，因此高精度实时测量系统是实现FAST高精度运行的关键。FAST望远镜最高观测频率设计为3GHz，反射面节点调整的定位精度要求达到RMS5mm，分配给测量精度为 RMS2mm；馈源舱的实时定位测量精度要求达到RMS3mm；公里量级达到毫米级精度只有具有“测量机器人”美誉的高端全站仪可以实现2，因此 FAST主要的实时测量任务都是由全站仪完成[3]。

全站仪是兼有电子测角、电子测距、数据计算和传输功能的自动化、数字化三维坐标测量与定位系统[4]。它由测角精度很高的水平、垂直度盘和测距仪构成。全站仪测量系统测距的基本原理是利用电磁波在空气中传播的速度为已知这一特性，测定电磁波在全站仪与靶标间往返传播的时间来求得距离值。在室外大尺度环境下，当大气密度不均匀时，就像看水中物体一样，除了传播速度变化，还造成传播方向的误判，测角测距都受影响，因此大气折射的影响是全站仪误差的主要来源。本文主要介绍研发的“风琴式护罩高精度运动平台”、实验过程和数据分析方法。评价全站仪在FAST现场特殊条件下的测量精度和实时性，为后续误差修正提供依据。

# 2 风琴式护罩高精度运动平台设计

# 2.1设计指标

FAST现场大气密度不均匀性非常明显，温、湿度场分布极为复杂，高差约150米，大气压有20多个毫帕的变化，折光影响异常大；不符合连续折射率变化的球壳分层模型无法用常规补偿修正。从全站仪到被测点沿途地面均铺设反射面面板，金属表面的海市蜃楼现象会对原始观测量的测量精度产生影响；全范围铺设面板也限制了评价设备的尺寸、安放和运输。

# 表1．风琴式护罩运动平台

Table 1. Organ type shield moving platform   

<html><body><table><tr><td>技术参数</td><td>技术指标</td></tr><tr><td>平台有效行程</td><td>1m</td></tr><tr><td>运行速度</td><td>12mm/s，18mm/s，24mm/s</td></tr><tr><td>定位精度</td><td>0.08mm</td></tr><tr><td>控制方式</td><td>内置PLC</td></tr><tr><td>通讯方式</td><td>有线、无线兼容</td></tr><tr><td>平台尺寸</td><td>小于2米</td></tr><tr><td>电器柜尺寸</td><td>最大边小于1m</td></tr></table></body></html>

平台尺寸过大不利于运输和测试时安放，运动有效行程过小影响测试功能，设定有效行程1米最大尺寸小于2米，电器柜最大边小于1m；观测时馈源舱运动速度为 $1 1 . 7 \mathrm { m m / s }$ 和23.4mm/s，故设定三挡运动速度 $\mathrm { 1 2 m m / s }$ ， $1 8 \mathrm { m m / s }$ ， $2 4 \mathrm { m m / s }$ ；要求平台定位精度 $0 . 0 8 \mathrm { m m }$ ；通讯方式有线无线兼容。

2.2远程高精度测量设备性能评价硬件系统组成及工作原理

远程高精度测量设备性能评价硬件系统包括计算机、全站仪、运动平台及靶标；其中，全站仪、计算机、靶标是采购产品；运动平台、通讯、数据采集及控制是研发产品。

如图1所示，靶标通过连接板固定安装在滑块上，滑块与运动平台的丝杠连接，并随丝杠的旋转水平移动；数据采集计算机与运动平台连接获取运动平台上靶标的移动数据；全站仪测量靶标的移动数据通过无线或有线方式输送至数据采集计算机；由数据采集计算机对比通过连接运动平台直接获取的靶标的移动数据以及全站仪测量的靶标的移动数据得出全站仪的时滞及差分测量精度数据。运动平台的误差来源包括丝杠误差、编码器误差、通讯传输延时误差等，通过评估这些误差引起的单位误差在亚毫米，相对全站仪的 5mm 的测量误差可以忽略，所以可以以平台移动数据为基准评价全站仪的性能。

![](images/23a4d8c618f71b1f8036bddbbd5808a063ec162de481ce3703274dd3a448cec5.jpg)  
Figure 1.Performance evaluation hardware system of remote high-precision measuring equipment

运动平台如图2所示包括丝杠导程为5mm；丝杠两端安装限位传感器，当检测到限位信号时控制电机反转，使运动平台往复运动；丝杠及传感器由风琴罩保护适应野外工作环境；安装靶标的 滑块随丝杠运动；减速机减速比为8；电机编码器分辨率为100脉冲/转；电控箱内包含空开、驱动器、电源和无线模块等。平台每运动1mm 需要的脉冲数 $\mathbf { \Psi } = \mathbf { \Psi }$ 编码器的分辨率\*减速比/丝杆导程 $= 1 0 0 0 0 { * } 8 / 5 { = } 1 6 0 0 0$ ；电机运行转速 $\underline { { \underline { { \mathbf { \Pi } } } } } = \cdot$ 平台运行速度 $* 6 0 *$ 减速比/丝杆导程 $= 1 2 * 6 0 * 8 / 5 \mathrm { = } 1 1 5 2$ RPM。

![](images/ff4a84ee1ed1673212d2d812762003e3c40f15f47049bdd382442034cd63511b.jpg)  
图1.远程高精度测量设备性能评价硬件系统

# 2.3 测试方法设计

全站仪能实现三维测量，风琴式护罩高精度运动平台只有一维准确信息，需要设计相应的测试方案，完成全站仪三维评价。

架设全站仪输入相应气象参数，全站仪内部完成常规改正；按设计的方向和位置安放运动平台；将靶标安装在平台滑块上，先采集靶标静止时数据，分析数据时根据靶标启动点进行时间对齐；平台按不同速度多次往复运动并采集数据；将靶标运动数据在 XYZ三轴上投影，可分析出不同轴向全站仪测量性能。

如需在某一方向获得最大分量可调整运动平台放置方向进行多次实验和数据采集。增大单一分量的平台方向设计原则：平台水平放置，使靶标的移动方向与全站仪的激光水平方向一致，获得该方向最大位移分量，启动测量，采集数据可计算出不同速度下全站仪X轴测量精度；再次平台依然水平放置使靶标的移动方向与全站仪的激光方向在水平方向垂直，可计算出不同速度下全站仪Y轴测量精度；靶标的移动方向与铅锤方向一致，可计算出不同速度下全站仪Z轴测量精度。

# 3全站仪性能测试实验

为提高工作效率，制造了工装安装在滑块上可同时测三台全站仪。运动平台上分别放置三个靶标，三个靶标构成边长约为1米的三角形；运动平台电机编码器和全站仪测量数据由同一台计算机采集，计算机接收数据是记录计算机时间，保证数据到达的时间基准统一；运动平台按12mm/s、18mm/s和 $2 4 \mathrm { m m / s }$ 三档速度运行，每个速度档采集时间为10分钟。

实验分为室内和室外两部分见图3，室内实验采用三台全站仪，全站仪与运动平台距离约为8米，实验前统一设站，保证三台全站仪在同一坐标系内；室外实验用两台全站仪，全站仪与运动平台距离约 230米，两台全站仪放在同一基墩并统一设站，分别测运动平台上两个靶标，室外实验分别使用了三种靶标。

![](images/f270cb76b9f35868e01f796b250aee522411957bf8770c30e50a96e9d034190a.jpg)  
图2. 运动平台照片Figure 2. Photos of moving platform  
  
Figure 3.Photos of indoor and outdoor experiments

# 4 数据分析结果

# 4.1数据分析方法

运动平台电机编码器和全站仪测量数据由同一台计算机采集保证了数据的时间一致性;

全站仪采样率 $5 \mathrm { - } 7 \mathrm { { H z } }$ ，采样周期不均匀，电机编码器采样率高于全站仪测量速率，对运动平台数据进行线性差值，按照全站仪时间标签重新采样，使全站仪数据与平台数据时间对齐;

将移动平台和全站仪测量数据均投影到全局坐标系下，以编码器数据为基准分析在不同方向上全站仪的点位误差，距离差代表综合误差；

通过运动平台数据与全站仪数据做相关分析得出全站仪动态测量时滞；

将全站仪数据在时间轴上统一移动时滞量后再与平台数据进行比较。

4.2室内实验分析结果

运动平台运动方向与本地坐标系X轴方向基本一致，分别分析三种速度下三个全站仪的时滞、点位误差和综合误差，见表2.

表2．三台全站仪时滞、点位误差及综合误差  
Table 2. Time delay， point position error and comprehensive error of three total stations   

<html><body><table><tr><td>全站仪编号</td><td>运动速度 (mm/s)</td><td>时滞（ms）</td><td>X误差（mm）</td><td>Y误差（mm)</td><td>Z误差（mm）</td><td>综合误差 (mm）</td></tr><tr><td rowspan="3">Z1</td><td>12</td><td>220</td><td>2.7</td><td>1.03</td><td>0.4</td><td>2.8</td></tr><tr><td>18</td><td>230</td><td>4.2</td><td>1.3</td><td>0.4</td><td>4.2</td></tr><tr><td>24</td><td>230</td><td>5.5</td><td>1.7</td><td>0.4</td><td>5.6</td></tr><tr><td rowspan="3">Z2</td><td>12</td><td>270</td><td>3.3</td><td>1.1</td><td>0.5</td><td>3.3</td></tr><tr><td>18</td><td>270</td><td>4.8</td><td>1.4</td><td>0.4</td><td>4.9</td></tr><tr><td>24</td><td>275</td><td>6.4</td><td>1.8</td><td>0.4</td><td>6.5</td></tr><tr><td rowspan="3">Z3</td><td>12</td><td>275</td><td>3.1</td><td>1.4</td><td>1.1</td><td>3.4</td></tr><tr><td>18</td><td>295</td><td>5</td><td>1.9</td><td>0.3</td><td>5.3</td></tr><tr><td>24</td><td>295</td><td>6.5</td><td>2.5</td><td>0.3</td><td>6.9</td></tr></table></body></html>

图4.(a)靶标1在基本沿X轴方向运动时平台测量靶标1相对起始点运动距离与全站仪测量的靶标1相对起始点运动距离的轨迹图；图4.(b)是以平台运动为基准，全站仪测量靶标1在XYZ三轴上误差，图中所示有明显系统差；从时滞分析中可以看出测量误差的系统差主要源自全站仪时滞图4.(c)显示消除时滞对误差起到明显的抑制作用；图4.(d)是全站仪采样周期，图中可见采样周期集中分布在 $1 1 0 \mathrm { m s }$ 带上，由于全站仪存在周期性内外光路切换，约每分钟一次，内外光路切换时间约0.8s形成周期性停拍，停拍是导致误差数据出现大幅度跳变的主要原因。

![](images/1a92a9f2a34ab0d464ed7637c826c764bdc203dc15ea4d6aff941f6ab45d9e28.jpg)

![](images/9a87cfe1dfaf78ad51aca474beb2900950e5424b3efb1f690f1bde6fb29773ca.jpg)  
图4. 室内实验数据分析图  
Figure 4. Analysis of indoor experiment data

运动平台运动方向与本地坐标系Y轴方向基本一致，分别分析三种速度下三个全站仪的时滞、点位误差及综合误差见表3。

# 表3.三台全站仪时滞、点位误差及综合误差

Table 3. Time delay， point position error and comprehensive error of three total stations   

<html><body><table><tr><td>全站仪编号</td><td>运动速度 (mm/s)</td><td>时滞（ms）</td><td>X误差（mm）</td><td>Y误差（mm)</td><td>Z误差（mm）</td><td>综合误差 （mm）</td></tr><tr><td rowspan="3">Z1</td><td>12</td><td>220</td><td>1</td><td>2.8</td><td>0.5</td><td>2.7</td></tr><tr><td>18</td><td>225</td><td>1.1</td><td>4.4</td><td>0.6</td><td>4.4</td></tr><tr><td>24</td><td>220</td><td>1.2</td><td>4.8</td><td>0.7</td><td>4.8</td></tr><tr><td rowspan="3">Z2</td><td>12</td><td>200</td><td>0.7</td><td>2.8</td><td>0.9</td><td>2.5</td></tr><tr><td>18</td><td>200</td><td>0.9</td><td>3.7</td><td>1.2</td><td>3.8</td></tr><tr><td>24</td><td>200</td><td>1.1</td><td>4.8</td><td>1.2</td><td>4.9</td></tr><tr><td rowspan="3">Z3</td><td>12</td><td>225</td><td>0.6</td><td>2.7</td><td>0.9</td><td>2.7</td></tr><tr><td>18</td><td>230</td><td>1</td><td>2.8</td><td>0.7</td><td>2.8</td></tr><tr><td>24</td><td>205</td><td>1.3</td><td>4.8</td><td>1.2</td><td>5</td></tr></table></body></html>

三台全站仪测同一个靶标，分别分析三种速度下三个全站仪的时滞、点位误差及综合误差见表4。

# 表4.三台全站仪时滞、点位误差及综合误差

Table 4. Time delay， point position error and comprehensive error of three total stations   

<html><body><table><tr><td>全站仪编号</td><td>运动速度 (mm/s)</td><td>时滞（ms）</td><td>X误差(mm)</td><td>Y误差（mm)</td><td>Z误差（mm)</td><td>综合误差 （mm）</td></tr><tr><td rowspan="3">Z1</td><td>12</td><td>225</td><td>1.1</td><td>2.8</td><td>0.6</td><td>2.9</td></tr><tr><td>18</td><td>225</td><td>1.2</td><td>3.9</td><td>0.6</td><td>4.1</td></tr><tr><td>24</td><td>220</td><td>1.3</td><td>5.2</td><td>0.7</td><td>5.3</td></tr><tr><td rowspan="3">Z2</td><td>12</td><td>200</td><td>0.7</td><td>2.6</td><td>0.1</td><td>2.6</td></tr><tr><td>18</td><td>200</td><td>0.8</td><td>3.7</td><td>0.8</td><td>3.8</td></tr><tr><td>24</td><td>200</td><td>1.1</td><td>4.9</td><td>0.6</td><td>5</td></tr><tr><td rowspan="3">Z3</td><td>12</td><td>230</td><td>1.7</td><td>2.7</td><td>0.8</td><td>2.9</td></tr><tr><td>18</td><td>225</td><td>1.1</td><td>4</td><td>0.1</td><td>4.2</td></tr><tr><td>24</td><td>230</td><td>1.2</td><td>5.4</td><td>1.7</td><td>5.6</td></tr></table></body></html>

室内试验结果表明运动平台放置方向不影响全站仪时间特性时滞和周期特征一致；运动平台放置方向与某轴一致时体现了靶标的主要运动方向与该轴一致，另外两个方向分量很小近乎静止，体现了全站仪运动与静止时精度差异，静态误差相对动态要小些；每个方向以不同运动速度运动也表达了运动速度对精度的影响，运动速度越大误差越大。

# 4.3室外实验分析结果

棱镜不同会对测量精度产生影响[5]，两台全站仪分别测两个不同棱镜，分别分析低速和高速两种速度下两个个全站仪的时滞、点位误差及综合误差见表5。

# 表5.两台全站仪时滞、点位误差及综合误差

Table 5. Time delay， point position error and comprehensive error of two total stations   

<html><body><table><tr><td>全站仪编号 （棱镜类型）</td><td>运动速度 (mm/s)</td><td>时滞（ms）</td><td>X误差 (mm）</td><td>Y误差 (mm)</td><td>Z误差(mm)</td><td>综合误差 (mm）</td></tr><tr><td rowspan="2">Z1 （圆棱镜）</td><td>12</td><td>200</td><td>1.6</td><td>4.7</td><td>2</td><td>3.5</td></tr><tr><td>24</td><td>205</td><td>2</td><td>5.7</td><td>1.6</td><td>5.8</td></tr><tr><td rowspan="2">Z2 （圆棱镜）</td><td>12</td><td>250</td><td>1.9</td><td>4.5</td><td>3.2</td><td>4.6</td></tr><tr><td>24</td><td>200</td><td>1.7</td><td>5.5</td><td>2.1</td><td>5.6</td></tr><tr><td rowspan="2">Z1 (360°中号棱镜）</td><td>12</td><td>210</td><td>1.2</td><td>3.2</td><td>1.6</td><td>3.3</td></tr><tr><td>24</td><td>210</td><td>1.6</td><td>5.5</td><td>1.5</td><td>5.6</td></tr><tr><td rowspan="2">Z2 （360°中号棱镜）</td><td>12</td><td>215</td><td>1.1</td><td>3.1</td><td>1.3</td><td>3.2</td></tr><tr><td>24</td><td>210</td><td>1.5</td><td>5.7</td><td>1.3</td><td>5.8</td></tr><tr><td rowspan="2">Z1 (360°小号棱镜）</td><td>12</td><td>220</td><td>1.3</td><td>3.3</td><td>1.2</td><td>3.4</td></tr><tr><td>24</td><td>215</td><td>1.6</td><td>5.6</td><td>1.8</td><td>5.7</td></tr><tr><td rowspan="2">Z2 （360°小号棱镜）</td><td>12</td><td>195</td><td>1.2</td><td>3.1</td><td>0.1</td><td>3.1</td></tr><tr><td>24</td><td>210</td><td>1.4</td><td>5.7</td><td>1.7</td><td>5.8</td></tr></table></body></html>

图5.(a)全站仪Z2 测量小号 $3 6 0 ^ { \circ }$ 棱镜（靶标）时运动平台和全站仪测量的轨迹图；图4.(b)是以平台运动为基准，全站仪测量靶标在XYZ三轴上误差，图中所示存在系统差，但相对比例比室内小很多，远程室外大气扰动误差明显；图4.(c)显示消除时滞对误差的影响不然室内实验作用明显，大气扰动误差依然存在；图4.(d)是全站仪采样周期，图中可见室内外实验中全站仪时间特征基本不变。

![](images/7fa15320c8fe41c4c6f285f2c22f463521b63c7f243d6d6377723b85a3312b3a.jpg)  
图5．室外实验数据分析图  
Figure 5.Analysis of outdoor experiment data

室外实验与室内试验结果表明全站仪时间特性不变；静态误差相对动态要小；运动速度越大误差越大。

室外动态测量主要误差来源依然是全站仪时滞和采样周期不确定性，从消除时滞影响后的数据图像可见室外残差大于室内主要体现大气扰动影响，静态测量室内外差别主要表现为大气扰动影响实验结果显示室外误差明显大于室内。

# 5 结论

室内室外实验测试表明全站仪时间特性基本不变，采样周期集中分布在110ms 带上，由于全站仪存在周期性内外光路切换，周期约1分钟，内外光路切换时间约0.8s，此时间是导致误差数据出现大幅度跳变的主要原因，时滞在195-295ms之间；静态测量精度高于动态测量精度，测量点位精度与靶标运动速度正相关，基本呈线性关系；消除时滞影响可有效改善测量精度。

提高测量精度还需解决大气扰动的影响；需解决全站仪测量时滞，建立时滞模型和卡尔曼滤波算法，有效降低测量时滞；需解决全站仪测量数据同步问题，尤其在全站仪内外光路切换时间内需对测量数据进行有效预测。

# 参考文献:

[1] Peng Jiang, Qing-Wei Li, Ren-Dong Nan，Research on design of adaptive connectingmechanisms for the cable-net and panels of FAST ，Vol 17, No 9 (2017): (89-99)  
[2] 骆亚波，测量机器人在FAST馈源动态跟踪测量中的应用，解放军信息工程大学硕士论文，2003  
[3] LiChun Zhu， Introduction of measurement and control technology of FAST ， 2018 ，SPIE  
[4] 《全站仪原理》．徕卡全站仪技术手册  
[5] 骆亚波，陈华运，郑勇，夏治国， $3 6 0 ^ { \circ }$ 棱镜的结构性能及定位精度分析，测绘科学技术学报，Vol.23No. 6 p461-466

# Research on performance evaluation method of remote high precision measur ing equipment

Yu Dongjun'，Zhu Zixun²，Song Benning'，Deng Shenxiongl (National Astronomical Observatory,CAS，Bei jing，100101 The experimental high school attached to Bei jing normal university，Beijing，100032)

Abstract：With the continuous development of laser measurement technology,the total station with the reputation of "measurement robot" has incomparable advantages in measurement accuracy, flexibility,speed and convenience.As the main measuring equipment in the FAST, how to overcome the influence of atmospheric refraction,understand the dynamic measurement performance of total station, andrealize high-precision fast scanning measurement and high-precision dynamic tracking measurement are the key and dificult points.In order to overcome the influence of uncertain factors in the measurement process,it is necessary to know the degree of influence.This paper introduces the research and development of the "organ shield motion platform",the experimental and data analysis methods.Evaluate the measurement accuracy and real-time performance of total station in the field environment,Through the experimental test,The time delay of the total station is between 195 and

295ms and the measurement accuracy is about $5 . 3 ~ \mathsf { m m }$ . This conclusion provide basis for subsequent error correction.

Key word: FAST, Total station, Movement Platform, Time delay, Measurement accuracy