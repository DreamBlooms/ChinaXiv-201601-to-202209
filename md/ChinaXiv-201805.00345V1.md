# 温室移动机器人复合栅格地图构建方法研究

史兵aʰ，段锁林ab，李菊ʰ，王朋ä，朱益飞a(常州大学a.城市轨道交通学院;b.机器人研究所，江苏 常州 213164)

摘要：针对温室环境中机器人依靠自身携带的传感器无法获取全面的环境信息，从而常导致路径规划错误的问题，提出了一种结合外部传感器系统获取温室环境信息，构建复合栅格地图的方法。首先，利用无线传感器网络定时采集对机器人通过性有影响的温度、湿度环境信息，并发送给机器人；其次，当温度或湿度数据的变化率达到设定阈值时，机器人利用阈值分割和插值法分别建立温度和湿度栅格地图；最后，将温度栅格地图、湿度栅格地图和室内障碍物物栅格地图相结合，构建动态更新的复合栅格地图。经测试，采用常规A\*算法规划路径时，基于环境数据变化率阈值设定为 $\pm 1 0 \%$ 的复合栅格地图的成功率和完成时间，分别是基于普通栅格地图成功率的2.5倍，和1.05倍。结果表明，复合栅格地图能提高路径规划的成功率，并且不会由于动态更新复合栅格地图，导致机器人响应时间明显增加，实时性能满足系统的实际需求。

关键词：温室；移动机器人；栅格地图；阈值分割；无线传感器网络 中图分类号：TP doi: 10.3969/j.issn.1001-3695.2017.09.0963

# Research on construction of composite grid map for mobile robot in greenhouse

Shi Binga,b, Duan Suolina, b,Li $\mathrm { J u ^ { b } }$ ,Wang Penga, Zhu Yifeia (a.SchoolofUrbanRailTransit,b.CenterforRobotResearch,Changzhou University,Changzhou Jiangsu213164,China)

Abstract:Amobile robot based on a normal grid mapcould not obtain the comprehensive environmental information in a grenhouse becauseoftheless numberand limitedlocationofcarried sensors.An incorrect planningpathmayarise.The system adopted a waytobuild acomposite grid map based on thecomprehensive environmental information in greenhouse.Firstly, wirelessensor network regularlycolected dataoftemperatureand humidityand sent them to the robot.Thesedata had heavy impacts onmobile robot's pasing through in greenhouse.Secondly,when therateofchangeof temperature orhumiditydata reachedthe threshold,thesystem used the methodof threshold segmentationand interpolation to establishthegrid maps for temperatureand humidityrespectively.Finally,te systemcombined the grid map for temperature,the grid map forhumidity andthe grid map forinterior material barierin a grenhouse tobuilda dynamicallyupdatedcomposite grid map.After testing, whenthe system adopted theA \*algorithm,therateofsuccesstoavoid area ofhigh temperature and high humidity based on the composite grid map at threshold of $\pm 1 0 \%$ was 2.5 times to normal grid map. The time of completion was 1.05 times to normal grid map.Theresults show that thecomposite grid mapcan improve the sucessrateof thepath planning andthe robot does not meet the problemofslowresponseoftherobot due tothe dynamic updatingof thecomposite grid map.Thereal-time performance satisfies the actual requirements of the system.

Key Words: greenhouse; mobile robot; grid map; threshold segmentation; wireless sensor network

# 0 引言

移动机器人的应用技术，已经做了许多研究，其中机器人的自主导航方法是重点研究内容之一。

温室移动机器人是温室自动化技术的一种集中体现，主要用来在温室环境中搬运、采摘、精确施肥等方面的工作，有利于提高劳动效率，降低生产成本。目前，国内外学者针对温室

人工设置导航标志是温室移动机器人可采用的一种引导自主导航的方法。有的是在机器人将要移动的道路上铺设引导磁条，移动机器人通过感应，按照既定路线前进或后退，到达目的地。有的则是直接在温室的道路上铺设专用轨道，用于机器人的往返移动，此种方法完全避免了移动机器人与温室中的作物发生碰撞的可能，安全性很高。以上两种方法所实现的导航均有可靠性高、移动速度快等优点，但其实现起来将会均会增加成本，特别是铺设专用轨道的方法，只适合于一些超大型的温室[1,2]。

栅格地图（gridmap）是机器人自主导航中常用的一种环境地图，是将传统的几何地图离散化表示，用栅格将目标区域分割成连续的区域。栅格通常为正方形，大小一致。根据障碍物的位置，将其所对应的栅格赋值，表示占用情况。栅格地图表示清晰、直观应用广泛，也常被应用在温室环境中的机器人自主导航中[3]。

人工设置导航标志的方法需要改造温室的现有环境，增加了成本，通用性不好，在实际应用中使用不多。目前，温室环境下的栅格地图的应用，通常只考虑温室内的实际障碍物所构成的普通栅格地图，和机器人自身而忽略如温度、湿度等其他因素，或是在机器人运动时，停止一些对机器人造成不利影响的工作，如喷灌、加热等[4-5]。前一种方法无法获得全面环境信息，可能会导致路径规划错误，而后一种方法显然缺乏灵活性，自动化程度低，不利于提高效率。本文采用栅格地图与外部传感器系统相结合的方案，利用无线传感器网络定时监测环境信息，将可能会对机器人造成损害的高温、高湿环境信息，引入到栅格地图中，构建复合栅格地图，既能保证地图信息的全面准确，又能提高温室移动机器人的工作效率。

# 1 系统结构

本系统由3部分构成，分别是工作现场单元、监控中心单元和远程单元，系统结构如图1所示。

数据库 Web 远程浏览服务器 服务器 客户温室 H Internet1. ? TCP/IP作物 作物 作物区域 区域 区域TCP/IP 远程控制： 通信服 客户传感器节点■移动机器人工作现场单元 监控中心单元 远程单元

工作现场单元由无线传感器网络和移动机器人组成。无线传感器网络负责采集温室实时环境数据。移动机器人则根据生成的环境地图自主移动到目的地，完成搬运、采摘等任务。同时，移动机器人还承担将温室环境信息中转到监控中心单元的任务。

工作现场单元的工作过程：一方面，无线传感器节点每隔1s采集一次温室环境参数，并采用单跳或者多跳的方式传递给安装在移动机器人上的网关节点，网关节点通过USB接口将数据送给移动机器人，移动机器人再通过由无线路由器搭建的无线局域网，将数据发送给监控中心的通信服务器。另一方面，移动机器人接到移动指令后，即生成地图，并进行定位。当自身位置、目的地位置和地图都具备之后，采用路径规划算法，确定一条全局最优路径。移动机器人运动控制器生成控制命令，由电机的驱动器最终实现机器人的移动。

监控中心单元为上层单元，由通信服务器、数据库服务器和Web服务器组成。通信服务器是下层数据上传，更高层控制命令下传的中间层。通信服务器采用多线程机制，实现移动机器人与通信服务器、远程控制客户与通信服务器、通信服务器与数据库服务器之间的Socket通信。数据库服务器存储温室的环境数据，温度、湿度、光照度、 $\mathrm { C O } _ { 2 }$ 量和含氧量等。数据库是系统的数据中心，和Web服务器实现交互，以提供各种数据信息。

远程单元为系统最高层用户，有远程浏览客户和远程控制客户2类。远程浏览客户通过各种浏览器均可直接访问Web服务器，以图形界面的形式显示数据。远程控制客户需要安装客户端软件，通过Socket通信与监控中心的通信服务器联系，远程客户端的控制命令由通信服务器接收，然后由通信服务器控制机器人。系统配置通信服务器的目的是避免远程单元客户直接控制移动机器人，这种设置中间层的架构大大提高了系统的安全性。本文将重点讨论温室环境中，复合栅格地图的构建方法。

# 2 构建温室环境复合栅格地图

本系统中，复合栅格地图的建立过程有3个主要步骤：首先获取环境信息；然后选取对机器人移动有重大影响的关键环境信息，并对离散的关键环境信息建立连续模型；再对各关键环境信息，使用阈值和单元分解分别建立栅格地图；最后将各个栅格地图相结合，得到复合栅格地图。

1）环境信息获取

利用传感器系统获取温室各处多种离散的环境信息，如温度、湿度、光照度、 $\mathrm { C O } _ { 2 }$ 量和含氧量等。温室中温度过高或者湿度过大的区域，都对移动机器人本身有不利的影响，应避免进入该区域。因此，在众多的环境信息中，温度和湿度为关键环境信息，将会直接影响到环境地图的建立。如果在室外环境，则地形的坡度信息，应该成为关键环境信息之一。

# 2）关键环境信息建模

建模的目的是将原本离散的关键环境信息，通过某种方法变成连续的，覆盖整个目标区域的方程。当模型建立后，在目标区域内，根据任一点的坐标，即可求得该点的环境参数值，为地图的构建做好准备。

系统使用三角形插值法，根据此方法，对已知的空间点进行划分，所有三角形互不交叉，且使任何一个三角形的最小内角为所有可能的划分中最大，这样可以保证误差最小。对于三角形除3个顶点外的任意坐标（x,y)，其 $z$ 值根据插值法进行估算。图2假设为已经划分好的某三角形，A,BC为三角形的顶点，数据是已知的，现在要求出其内部任意点D处的 $z$ 值。

![](images/2d78f483edfbaadac52606d40d2aaa9caaa25d7f4812fa85a19466487b2473f8.jpg)  
图2三角形插值

空间向量有如下关系：

$$
\overrightarrow { A C } \times \overrightarrow { A B } \bullet \overrightarrow { A D } = 0
$$

则有

$$
\operatorname* { d e t } { \left( \begin{array} { l l l } { x 3 - x 1 } & { y 3 - y 1 } & { z 3 - z 1 } \\ { x 2 - x 1 } & { y 2 - y 1 } & { z 2 - z 1 } \\ { x - x 1 } & { y - y 1 } & { z - z 1 } \end{array} \right) } = 0
$$

将式（2）行列式展开可得

$$
Z = { \cfrac { z 1 + ( x - x 1 ) \operatorname* { d e t } { \left( \begin{array} { l l } { y 3 - y 1 } & { z 3 - z 1 } \\ { y 2 - y 1 } & { z 2 - z 1 } \end{array} \right) } - ( y - y 1 ) \operatorname* { d e t } { \left( \begin{array} { l l } { x 3 - x 1 } & { z 3 - z 1 } \\ { x 2 - x 1 } & { z 2 - z 1 } \end{array} \right) } } { \operatorname* { d e t } { \left( \begin{array} { l l } { x 3 - x 1 } & { y 3 - y 1 } \\ { x 2 - x 1 } & { y 2 - y 1 } \end{array} \right) } } }
$$

利用式(3)可求出三角形中，任一点的 $z$ 值。当任意点 $( \mathbf { \boldsymbol { x } } , \mathbf { \boldsymbol { y } } )$ 密集选取时，就可构成一个连续的曲面。

# 3）建立复合栅格地图

a)将温室地表平面逻辑上划分成大小一致的栅格，通常为正方形，栅格边长应大于移动机器人最宽处，即移动机器人能通过栅格。

b)利用式（4）判断栅格对应的环境量，是否有利于移动机器人运动的通行，若栅格 $( \mathbf { x } , \mathbf { y } )$ 处的 $Z ( x , y )$ 超过某阈值 $Z _ { 0 }$ ，则认为不利，则此栅格逻辑上被赋值1，表示被占用；反之，被赋值为0，表示可以通行；当有多个环境量时，则需要在相同的栅格划分的基础上，分别求出不同环境信息时，各个栅格的占用情况。

$$
G ( x , y ) = \left\{ { 1 i f ( Z ( x , y ) \geq Z _ { 0 } ) } \right.
$$

c)根据所得的多种环境信息下的栅格地图，按式（5)将其叠加起来，获得最终的复合栅格地图。

$$
T ( x , y ) = G _ { 1 } ( x , y ) \bigm | G _ { 2 } ( x , y ) \bigm | G _ { 3 } ( x , y ) \bigm | \ldots \bigm | G _ { n } ( x , y )
$$

式（5）中 $T ( x , y )$ 表示复合栅格逻辑值； $G _ { n } ( x , y )$ 表示第 $n$ 种环境信息下的栅格逻辑值。

# 3 构建地图实例

# 3.1环境信息获取

本系统采用无线传感器网络获取温室内的环境信息，其中温度、湿度参数将会被用于制作环境地图。温室长 $1 0 0 \mathrm { m }$ ，宽$4 0 \mathrm { m }$ ，按任一行和列的相邻传感器节点间隔均为 $2 0 \mathrm { m }$ 规律布置，传感器节点布置如图3所示，左下角的坐标为(0.0）。

![](images/b979c39c35c422c738feec7675f6c51d1b5e9b241c825112ea201c74a86e1772.jpg)  
图3传感器节点布置

传感器节点通常采用2层结构，底层为各种传感器设备及其调理电路，本系统中的传感器有温度、湿度、光照度、CO2量和含氧量等。上层结构采用TI（texas instruments）公司CC2530无线收发芯片，该芯片是一个功能强大的微处理器，由存储设备、增强型8051处理器和支持ZigBee协议的无线收发单元构成[6\~8]。在TI公司推出的Z-STACK开发包的基础上，能够较为容易的开发出传感器节点、路由节点和网关节点的程序[9-I1]。三种节点的硬件完全相同，仅通过是否连接传感器和运行不同程序加以区分，通用性很强。

传感器节点每1s采集一次数据，发送给网关节点，网关节点将数据传递给机器人，此时的数据是离散的，表示传感器节点所在位置的环境信息。

由于大部分时间内，温室的温度和湿度均表现稳定，不会出现剧烈变化。在测试中，为了体现特殊情况，在坐标为(80,0)处放置了加热炉，在坐标为（60，20）处开启喷灌头，模拟特殊情况下构建地图的效果，以及移动机器人的运动情况。

# 3.2关键环境信息建模

根据已知的温度和湿度离散信息，在MATLAB平台，根据式（3）编写程序，即可建立温度、湿度的连续模型，如图4所示，其中图4（a）表示温度模型，图4（b）表示湿度模型。

![](images/b3e737f0a9e2615abd826b373c0def34652e0e2a8d6ad25b001e3da136a08b3f.jpg)  
图4温度、湿度连续模型

从图4（a）模型中得出，坐标（80.0）处温度最高，随着距离的增加，温度逐渐降低，可以看出，即使在 $2 0 \mathrm { m }$ 的距离上，也明显受到热辐射的影响而温度升高。从图4（b）模型得出，坐标（60,20）处湿度最大，随着距离的增加，湿度也呈下降趋势。但湿度的影响范围较小，超过 $2 0 \mathrm { m }$ 的距离，湿度几乎不受影响。

# 3.3建立复合栅格地图

本系统所使用的移动机器人尺寸为：机体宽度 $4 8 5 \mathrm { m m }$ ，总长 $4 9 4 \mathrm { m m }$ ，高度 $4 9 5 \mathrm { m m }$ ，为了保证机器人能够通过，并留有余地，将温室地表平面逻辑上划分成边长为 $4 \mathrm m$ 的正方形栅格，如图5所示。

![](images/e6541fc4c2c3140833481c2948b56dc39d5b747fe3235eb1ed39e33700625a46.jpg)  
图5温室平面栅格

由于栅格是一个平面，若仅使用某一点 $( x , y )$ 代替整个栅格平面，再利用式（3）（4）确定栅格的逻辑值，有可能会造成栅格逻辑值误判，当栅格面积越大，发生误判的概率也越大。因此，在图6中栅格的顶点和各边中间距离取点，分别为（204 $a , b . . . . . h$ ,其坐标分别对应为 $( a x , a y ) , ( b x , b y ) , . . . . . . , ( h x , h y )$ 。式（4)可相应变化为

$$
G ( x , y ) = \left\{ \begin{array} { l l } { 1 } & { \mathrm { i f } ( ( Z _ { a } ( a x , a y ) \geq Z _ { 0 } ) \big | ( Z _ { b } ( b x , b y ) \geq Z _ { 0 } ) \big | \cdots \big | ( Z _ { h } ( h x , h y ) \geq Z _ { 0 } ) ) } \\ { 0 } & { \mathrm { e l s e } } \end{array} \right.
$$

本系统中温度阈值 $Z _ { \mathrm { 0 i f f } }$ 取 $5 0 ^ { \circ } \mathrm { C }$ ，湿度阈值 $Z _ { 0 \dot { \imath } \boxed { 1 } \ast }$ 取$8 0 \% \mathrm { R H }$ ，逻辑值为1的栅格用黑色填充，表示被占用。

将式（3）和式（6）结合使用，获得温度和湿度环境下栅格地图，分别如图6（a）和图6（b）所示。温室中如图1所示意的作物区域，是阻碍机器人移动主要障碍，也必须将其反映到栅格地图中，该工作由人工输入障碍物的坐标位置，计算机经过简单的处理即可形成障碍物的栅格地图，如图6(c)所示。

最后，利用式（5）将温度栅格地图、湿度栅格地图以及障碍物栅格地图进行复合，获得完整信息的复合栅格地图，如图7所示。

图7所表示的复合栅格地图，是根据传感器网络在某次采集温度、湿度环境信息后绘制出来的。理论上传感器网络每1s采集一次数据，机器人应该绘制出一张复合栅格地图，但这将会大大增加机器人的负担，导致响应慢、实时性差的问题。系统在实际运用中，采用当采集到温度或者湿度数据变化率达到$\pm 1 0 \%$ 阈值时，则更新整个温室复合栅格地图，并重新规划路径，其动态过程如图8所示。

![](images/ceefb5e5339661e23c8acdc1ffe52327ce724d30b378ac29764043b7a67250b4.jpg)  
图6温度、湿度和障碍物栅格地图

![](images/b276039ca26518d8c6c382c1ce51e8e603871e4ff6c92c40367e5f17e841af04.jpg)  
图7复合栅格地图

![](images/776815b03e264bf76670dbd5e852b5137651060944da7f5671741d4c86abf1e6.jpg)  
图8动态更新复合栅格地图

# 4 现场移动测试

# 4.1移动机器人介绍

本系统采用上海英集斯自动化技术有限公司提供的轮式移动机器人作为开发测试平台，其主要参数如表1所示。

表1移动机器人参数  

<html><body><table><tr><td>项目</td><td>主要参数</td></tr><tr><td>系统架构</td><td>2层结构：工业级嵌入式计算机（上 位机）+运动控制卡（下位机);</td></tr><tr><td rowspan="5">计算机</td><td>Intel PM1.8G 低功耗、高速处理器；</td></tr><tr><td>SATA 80G 高速硬盘，DDR 512M内存，</td></tr><tr><td>6个串口（包括485、422通信接</td></tr><tr><td>□)，8个独立USB 接口，PCI插槽，</td></tr><tr><td>双通道RTL8110S自适应以太网口;</td></tr><tr><td rowspan="3">运动控制卡</td><td></td></tr><tr><td>专用高速数字信号处理器（DSP)</td></tr><tr><td>TMS320LF2407;</td></tr><tr><td>尺寸/重量</td><td>495 mm ×480 mm×600 mm/30Kg;</td></tr><tr><td>电池</td><td>24V，20Ah动力锂电池；</td></tr><tr><td>外接电源</td><td>DC24V，25A;</td></tr><tr><td>电机</td><td>24V,70WMAXON电机;</td></tr><tr><td rowspan="2">传感器</td><td>超声波、温湿度、摄像头、火焰传感</td></tr><tr><td>器、烟雾传感器</td></tr></table></body></html>

本系统应用的机器人是个具有多功能模块的开发平台，可以通过加载不同的硬件模块，配合相应的软件包，实现多种功能，并可将自己所研究的算法或控制策略，替换相应的软件包，并查看运行效果，实现再次开发[12-14]。

# 4.2 机器人移动测试

在温室中，设定A(16,4)点为起始点，T1(20,20)，T2(48,20)，.,T10(60,12)分别为目标点，具体位置如图9所示。移动机器人采用广泛使用的传统A"路径规划算法，进行路径规划[15\~18]。

![](images/209374e1ed807cd5e1bed85a051275f9ce0d82d413ad5ffe14c0a4b8cc33ceab.jpg)  
图9移动测试目标点位置

对10个目标点进行分组测试，每组分四种情况，分别对应：不能更新的普通栅格地图和温度、湿度数据变化阈值分别为 $\pm 5 \%$ 、 $\pm 1 0 \%$ 、 $\pm 2 0 \%$ 时，动态更新的复合栅格地图，具体数据如表2所示。

表2测试数据统计  

<html><body><table><tr><td rowspan="3">组数</td><td rowspan="3">目标</td><td colspan="4">是否避开</td><td colspan="5">完成时间/s</td></tr><tr><td rowspan="2">普通栅格地图</td><td colspan="3">复合栅格地图</td><td rowspan="2">普通栅格地图</td><td colspan="3">复合栅格地图</td><td rowspan="2">±20%</td></tr><tr><td>±5%</td><td>±10%</td><td>±20%</td><td></td><td>±2%</td><td>±10%</td></tr><tr><td>1</td><td>T1</td><td>√</td><td>√</td><td>√</td><td>√</td><td>32.5</td><td></td><td>52.5</td><td>34.1</td><td>33.8</td></tr><tr><td>2</td><td>T2</td><td>√</td><td>√</td><td>√</td><td>√</td><td>38.2</td><td></td><td>61.1</td><td>40.1</td><td>39.5</td></tr><tr><td>3</td><td>T3</td><td>√</td><td>√</td><td>√</td><td>√</td><td>42.4</td><td></td><td>67.8</td><td>44.5</td><td>44.4</td></tr><tr><td>4</td><td>T4</td><td>×</td><td>√</td><td>√</td><td>√</td><td></td><td></td><td>81.1</td><td>52.6</td><td>52.1</td></tr><tr><td>5</td><td>T5</td><td>×</td><td>√</td><td>√</td><td>√</td><td></td><td></td><td>85.3</td><td>55.3</td><td>54.7</td></tr><tr><td>6</td><td>T6</td><td>×</td><td>√</td><td>√</td><td>√</td><td></td><td></td><td>112.5</td><td>73.0</td><td>72.3</td></tr><tr><td>7</td><td>T7</td><td>×</td><td>√</td><td>√</td><td>×</td><td></td><td>-</td><td>137.6</td><td>89.6</td><td>88.5</td></tr><tr><td>8</td><td>T8</td><td>×</td><td>√</td><td>√</td><td>√</td><td></td><td>-</td><td>123.4</td><td>81.1</td><td>80.4</td></tr><tr><td>9</td><td>T9</td><td>×</td><td>√</td><td>√</td><td>×</td><td></td><td>-</td><td>132.8</td><td>86.2</td><td>85.4</td></tr><tr><td>10</td><td>T10</td><td>√</td><td>√</td><td>√</td><td>√</td><td></td><td>47.6</td><td>76.2</td><td>50.1</td><td>49.7</td></tr></table></body></html>

表2中 $\surd$ 表示成功避开， $\times$ 表示未成功避开。

从表2中避开障碍物的成功率上看，利用普通栅格地图避开障碍物的成功率为 $40 \%$ ；利用温湿度数据变化率阈值分别设定为 $\pm 2 \%$ 、 $\pm 1 0 \%$ 、 $\pm 2 0 \%$ 时，动态更新的复合栅格地图，其成功率分别为 $100 \%$ 、 $100 \%$ 、 $80 \%$ 。普通栅格地图成功率低是因为仅靠自身携带的传感器无法获得全面的环境信息，且不更新栅格地图，导致路径规划出现错误。复合栅格地图考虑了全面的环境信息，且按条件更新地图，因此成功率大大提高。温湿度变化率阈值设为 $\pm 2 0 \%$ 时，复合栅格地图出现 $20 \%$ 的不成功率是因为，数据变化率阈值设定过高，或者说是地图更新过慢造成的。

图10中X轴坐标中的1、2、3和4分别对应普通栅格地图、变化阈值为 $\pm 2 \%$ 的复合栅格地图、变化阈值为 $\pm 1 0 \%$ 的复合栅格地图和变化阈值为 $\pm 2 0 \%$ 的复合栅格地图。Y轴表示完成时间。T1、T2、T3和T10分别表示不同目标时的完成时间曲线。图10中的完成时间的变化趋势可以得出，不同目标对应的完成时间曲线具有相似的变化趋势，阈值绝对值为 $2 \%$ ， $10 \%$ 、$20 \%$ 时，所对应的完成时间均分别是普通栅格地图1.60倍、1.05倍、1.05倍。

![](images/0e8276ee71507d4978aa3aff4735bda4610c2aeb2817da9e4c845963bb4e288f.jpg)  
图10测试完成时间变化趋势

综合表2和图10可以得出：当更新复合栅格地图的数据变化阈值设定成 $\pm 1 0 \%$ 时，均能成功避开实际障碍物，以及模拟出来的高温、高湿度障碍区，成功率是基于普通栅格地图的2.5倍；基于复合栅格地图运行时间较之基于普通栅格地图运行时间为1.05倍，表明此种情况下复合栅格地图的更新不会明显影响机器人的响应速度。

# 5 结束语

在无线传感器网络实时获取温室温度、湿度关键环境信息的基础上，利用阈值分割和单元分解法，并通过设定合适的温度、湿度数据变化率阈值，实现复合栅格地图的构建和动态更新。通过测试表明，当数据变化率阈值设定为 $\pm 1 0 \%$ 时，基于复合栅格地图的传统A\*路径规划均能成功避开障碍区域，通过与普通栅格地图比较，基于动态更新的复合栅格地图的机器人响应速度并未受到明显影响，能满足系统的实际需求。此外，当有更多的环境信息被引入后，复合栅格地图将包含更加丰富的信息，将具有更高的成功率。下一步工作将从更新栅格地图的局部信息入手，进一步减小机器人运算工作量，提高实时性。

# 参考文献：

[1]谭民，王硕．机器人技术研究进展[J]．自动化学报,2013,39(7):963-972.  
[2]胡静涛，高雷，白晓平，等．农业机械自动导航技术研究进展[J]．农业工程学报,2015,31(10):1-10.  
[3]高国琴，李明．基于K-means 算法的温室移动机器人导航路径识别[J].农业工程学报，2014,30(7):25-33.  
[4] 王新忠，韩旭，毛罕平，等．基于最小二乘法的温室番茄垄间视觉导航路径检测[J].农业机械报,2012,43(6):161-166.  
[5]贾士伟，李军民，邱权，等．基于激光测距仪的温室机器人道路边缘检测与路径导航[J].农业工程学报,2015,31(13):39-45.  
[6]曹鹏飞，赵振．无线传感器网络关键技术研究综述[J].微计算机信息,2012,35 (9): 389-391.  
[7]Harun A,Ndzi DL,Ramli MF, et al. Signal propagation in aquacultureenvironment for wireless sensor network applications [J].Progress InElectromagnetics Research-Pier,2012,131 (4): 477-94.  
[8]Tuna G,Gungor VC,Gulez K.An autonomous wireless sensor networkdeployment system using mobile robots for human existence detection incase of disasters [J].AdHoc Network,2014,13 (5): 54-68.  
[9]LiX,Falcon R,Nayak A,Stojmenovic I. Servicing wireless sensor networksby mobile robots [J].IEEE Communication Magazine,2012,50(7): 147-54.  
[10] Lee WY,Hur K,Hwang KI,et al.Mobile robot navigation using wirelesssensor networks without localization procedure [J].Wireless PersonalCommunication,2012,62 (2): 257-75.  
[11]张文，刘勇，张超凡，等．基于方向 A\*算法的温室机器人实时路径规划[J]．农业机械学报,2017,48(7):22-28.  
[12]王红卫，马勇，谢勇，等．基于平滑 $\mathbf { A } ^ { * }$ 算法的移动机器人路径规划[J].同济大学学报：自然科学版,2010,38(11):1647-1650,1655.  
[13]马飞，杨，顾青，等．基于改进 $\mathbf { A } ^ { * }$ 算法的地下无人铲运机导航路径规划[J]．农业机械学报,2015,46(7):303-309.  
[14]简毅，张月．移动机器人全局覆盖路径规划算法研究进展与展望[J].计算机应用,2014,23(10):2844-2849.  
[15] Vakilian KA,Massah J.A farmer-assistant robot for nitrogen fertilizingmanagement of greenhouse crops [J]. Computer Electronic Agriculture,2017,139 (12): 153-63.  
[16]李逃昌，胡静涛，高雷．基于级联式控制策略的农业机械鲁棒自适应路径跟踪控制[J]．机器人,2014,36(2):241-249.  
[17]李逃昌，胡静涛，高雷．基于级联式控制策略的农业机械鲁棒自适应路径跟踪控制[J].机器人,2014,36(2):241-249  
[18]赵德安，贾伟宽，张云，等．农业机器人自主导航改进自适应滤波控制器研究[J]．农业机械学报,2015,46(5):1-6.