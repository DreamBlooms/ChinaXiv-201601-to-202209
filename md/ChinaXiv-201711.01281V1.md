# 月面近距离探测仿真系统的实现与应用

张静1,2,3，刘建军1,3，高兴烨1,3，陈铮4（1.中国科学院国家天文台月球与深空探测研究部，北京100012；2.中国科学院大学，北京100049；3.中国科学院月球与深空探测重点实验室，北京 100012；4.北京航空航天大学，北京 100083)

摘要：构建月面近距离探测仿真系统，用于月面实时视景显示及载荷运动模拟。系统以开源的面向对象的图形渲染引擎（Object-oriented Graphics Rendering Engine，OGRE）为基础，结合建模软件3DMAX、集成开发工具Visual Studio、3DS 格式转 MESH格式工具3ds2mesh及地形生成插件等，完成了着陆器及相关载荷的三维实体模型构建，并对月表环境进行了真实模拟。借助开源的CEGUI图形界面库设计了参数面板，用于数据的显示和人机交互。同时基于微软基础类库构建了三维场景调试界面，以便于直接控制三维场景更新及调整实体模型姿态，仿真有效载荷的探测过程。最后以全景相机为例进行仿真试验。

关键词：视景仿真；月面探测；模型构建；OGRE；全景相机中图分类号：TP399 文献标识码：A 文章编号：1672-7673(2017)04-0461-11

随着嫦娥一号、二号和三号任务的实施，我国已圆满实现探月工程[1]一期“绕”和二期“落”的科学目标，正在进行三期“回”的工程研制。三期工程的任务目标是实现月面无人自动采样返回，并开展月面近距离探测[2」，主要任务由嫦娥五号月球探测器承担，包括对着陆区的现场调查和分析，以及月球样品返回地球以后的分析与研究[3]，为实现这两个目标，嫦娥五号不仅搭载了参与月球采样的机械臂、监视相机等一些工程载荷，以实现采回 $2 \mathrm { k g }$ 月球样品的目的，同时为开展着陆区的现场调查，还搭载了全景相机、月球矿物光谱仪、雷达、降落相机等科学载荷，进行近距离探测，获取月球样品的月面背景信息。进行月面近距离探测时，日、器、月之间的三体关系，载荷转动的几何关系以及载荷科学探测的约束条件和影响因素(比如光照和地形环境)都对探测结果存在一定影响，同时科学探测过程具有唯一性，事先模拟月面的空间环境，对月面近距离探测任务进行地面仿真试验，将仿真数据信息化转换为以三维图形图像表示的、随时间和空间变化的可视化仿真[4过程，有利于科研人员实时掌握试验过程中的各个细节，从而起到重要的辅助作用。利用仿真技术可重复的特点，进行多次模拟试验，通过比较试验结果，对就位探测过程进行相应的调整，为任务方案的最终决策提供重要的依据，从而优化探测计划。

为了实现月面近距离探测时如何探测、何时探测、探测对象选择、探测效果展示以及探测过程回放的目标，设计了仿真系统。系统可实时驱动三维可视化场景更新，系统内所有有效载荷的科学探测都可通过开发的三维场景调试界面直接控制。通过调试界面能够直接快速地进行科学探测过程仿真、任务规划以及探测过程回放。根据用户需求自主编写探测流程脚本文件，并通过三维调试界面调用脚本文件，完整地展示月面就位探测的探测流程以及探测效果，实现高要求、高速率的人机交互。

# 1月面近距离探测仿真系统的设计

# 1. 1 系统功能需求

现阶段国外的三维视景仿真多是基于OpenGL图形库，如美国国家航空航天局德莱顿飞行中心开发的飞行训练系统[5」和实时飞行仿真系统[6；美国 MultiGen-Paradigm公司开发的三维视景软件Creator/Vega开发简捷的视景仿真；美国华盛顿大学基于面向对象的图形渲染引擎开发了移动机器人视景仿真系统；澳大利亚昆士兰理工大学基于DerectX开发了机器人视景仿真系统[8。采用基于OpenGL 和 DerectX 图形库的方式有一定的优势，但使用几何图元对于复杂三维场景需编写大量代码[9]。

月面近距离探测仿真系统建立在OGRE $^ +$ VisualStudio的基础上，有一定优势。面向对象的图形渲染引擎是源于 $\mathrm { C } { + } { + }$ 开发的面向对象的三维图形渲染引擎，能使开发人员更方便直接地开发基于三维硬件设备的应用程序。面向对象的图形渲染引擎采用面向对象的思想对于引擎中的类库不仅对更底层的系统库(Direct3D 和OpenGL)的全部使用细节进行了抽象和封装，而且提供了基于现实世界对象的接口和其他类[10]，支持渲染到纹理、多细节层次技术、场景管理以及高级插件的粒子系统等图形技术，很好地满足了月面近距离探测从任务规划到科学探测再到结果显示的条件。面向对象的图形渲染引擎拥有很高的效率，提供了多平台及三维渲染应用程序编程接口支持，对数据格式和材质提供了高效的支持。这些优势使得系统更方便快捷地实现以下功能：

(1)时间流逝速率调整：根据用户要求设定系统内部时间分辨率，动态改变显示速率。  
(2)空间位置更新：根据星历数据动态更新着陆器，日、地、月空间位置并完成三维动态显示。  
(3)具体载荷近距离探测：根据指令脚本文件与着陆器各载荷参数，仿真月面近距离探测过程。  
（4)人机交互：参数面板和三维场景调试面板实现人机交互。  
(5)探测流程回放：操作流程按自定义格式记录并保存成脚本文件，能随时调用回放探测过程。  
(6)任务仿真：自定义编写脚本文件，通过调用脚本文件实现用户需求的科学探测仿真。

1.2系统总体框架

根据系统功能需求，月面近距离探测仿真系统按照模块化的思想设计[11]。主要包括模型构建模块、仿真驱动模块以及人机界面模块，各模块相互独立，内部功能相对集中，易于功能扩展和维护，总体框架如图1。

![](images/707a0ffd258c0cb9eaea82ce0d6bd462cb5d36e0ce6dd2c75bb4eecd17b7af67.jpg)  
图1系统总体框架  
Fig.1 General framework of the system

模型构建模块包括三维实体模型及月表地形模型的构建；仿真驱动模块主要通过三维场景调试界面实现三维实体模型姿态及日、地、月空间位置的更新；人机交互模块主要指参数面板显示界面以及来自键盘、鼠标的输入。

# 1.3 系统仿真流程

月面近距离探测仿真系统采用基于场景图技术的三维图形引擎。运行面向对象的图形渲染引擎时分两步：（1)场景初始化，包括创建根对象、解析资源配置文件、配置渲染系统、选择场景管理器、创建摄像机与视口、加载资源、创建初始场景以及创建帧、监听器等；（2)场景渲染，进行帧循环并完成每一帧的渲染以及消息响应。系统分模块进行设计，灵活性和可扩展性强，初始化时可选择是否需要某一功能从而决定是否加载某一插件或库文件，具体仿真流程如图2。

初始化面向对象的图形渲染引擎与资源文件的同时加载相关的场景解析库、用于参数界面的CEGUI库、用于三维场景调试的微软基础类程序库以及用于日地月空间位置更新的星历数据库，与此同时开启监听用户消息从而获得仿真控制指令、运动实时数据以及用户输入信息。

# 2月面近距离探测仿真系统的实现

# 2.1 模型构建

模型构建主要包括月表地形模型构建以及三维实体模型构建。

# 2.1.1 月表地形模型构建

面向对象的图形渲染引擎本身不提供三维模型的建立，它支持的模型格式为.mesh文件格式，属于一种网络模型。地形绘制是探月活动的主要科学目标之一[12]，利用地面验证试验获得的 $2 \mathrm { m m }$ 分辨率的正射影像数据和 $2 \mathrm { m m }$ 空间分辨率的高程数据构建的地形代替月表地形模型，以方便对系统仿真结果进行验证。首先对地形的高程模型数据和正射影像数据进行金字塔处理生成多细节层次（LevelsofDetail，LOD)模型，然后生成.mesh文件格式的地形文件。考虑到大规模地形数据流畅绘制的问题，采用多细节层次模型绘制算法绘制地形地貌，引入“分而治之”的思想，根据地形的不同复杂程度和人眼观察地形的特点，对地形的不同区域采取不同细节的描述和绘制。这种算法在不降低表现效果的前提下，可以尽量减少三角形的数量，以便于提高图形绘制效率，实现地形的实时交互可视化[13]。通俗的讲就是将一块地形划分为无数小块区域，对于离视点越近的区域，或者该区域地形越复杂(起伏大，如山区)，绘制的三角形数目越多，地形描述精度越高；对于离视点越远的区域，或者该区域越平坦，绘制的三角形数目越少，地形描述精度越低。图3展示了建立的地形模型。

![](images/eb0a008ab3e75204078e2b7eafb971898517ef44dcff6057ee9f7a3b0c46ff06.jpg)  
图2系统仿真流程图Fig.2Flow chart of system simulation

![](images/8063b2a5a9f2762c31f1268ec0b14842f6d0a206169794e46e85959d063d5649.jpg)  
图3地面验证实验地形模型  
Fig.3Terrain model of ground validation experiment

# 2. 1. 2 三维实体模型构建

因系统用于降落后的月面科学探测，所以嫦娥五号有效载荷主要包括着陆器、全景相机、月球矿物光谱仪、国旗以及采样机械臂等。有效载荷模型采用真实模型参数比例，并且参考了全景相机转台实验动画、月球矿物光谱仪运动视频和机械臂表取采样、提罐、放回运动视频，最终借助3DMAX2015完成三维模型的构建。太阳模型和地球模型是规则的球形，通过简单的纹理贴图实现。3DStudio MAX是个人计算机上最普及的三维动画和建模软件，集成了丰富的第三方插件，支持多种格式导人与导出[14]。3DMAX构建的3D模型为.3ds格式，此格式不能被面向对象的图形渲染引擎直接支持，通过第三方插件3ds2mesh 将.3ds 格式转换为面向对象的图形渲染引擎可识别的.mesh文件格式。

# 2.2 仿真驱动

仿真驱动主要通过三维场景调试界面实现整个三维场景更新，主要包括三维实体模型姿态控制和日、地、月空间位置更新，另外也可通过脚本驱动。

# 2.2.1基于微软基础类库的三维场景调试界面

微软基础类库（MicrosoftFoundation Classes，MFC)是一个 $\mathrm { C } { + } { + }$ 类库，主要封装了大部分的WINDOWS应用程序编程接口函数，并且包含一个应用程序框架。系统基于微软基础类库设计了一个三维场景调试界面，界面对于整个系统仿真具有重大意义，在进行月面近距离探测时存在很大的优势，能够直接快速地控制三维场景内的实体模型姿态并对每一次探测过程进行记录并保存，通过调用脚本文件可回放探测过程，同时可根据用户需要改写或编辑脚本文件进行特定的探测仿真，另外通过调试界面可直接对系统时间进行设置并设置时间流逝速率或更改时间点。具体界面设计如图4，整个界面分为仿真数据回放和仿真数据记录两部分，其中仿真数据记录部分包括着陆器和各有效载荷的姿态控制、视角选择以及时间调整。

![](images/e9a801e9d13e65c9b42f4ab37be60889c48a7e1adf80982223750aad35d26fed.jpg)  
图4三维场景调试界面  
Fig.43D scene debugging interface

# 2.2.2 日、地、月空间位置更新

微软基础类库将原始日、地、月的位置数据转换为以时间为索引的数据库文件存储，根据输入的时间及JPLDE421精密行星星历文件路径，计算该时间太阳、地球相对于月面观测点的方位和高度角。随着系统运行，调用星历数据库，实现日、地、月空间位置更新，主要表现在太阳高度角及阴影效果等方面。

# 2.2.3 脚本驱动

自定义编写脚本文件，通过三维调试界面进行脚本仿真，以驱动整个三维场景更新。借鉴嫦娥五号月面工作程序，编写的脚本文件内容如图5。首先假设着陆器确认安全着陆时间为2018-1-102：00：45；其次在2018-1-102：05：45时着陆器太阳翼展开至初始位置；再者在 2018-1-104：59：45时月球矿物光谱仪防尘罩打开开始探测；然后于2018-1-204：16：55时国旗展开；最后全景相机从2018-1-204：23：25开始进行自主探测，其中第1列表示日期，第2列表示时间，第3列表示载荷，第4列和第5列则表示载荷姿态，每列之间用“，”隔开。调用上述编写的脚本文件，得到的仿真结果如图6。

2018.1.1,2:0:45,EVENT_ENV,-8.00,-5.00,2.00,0.00,0.00,0.00   
2018.1.1,2:5:45，EVENT_BOARD,1.00   
2018.1.1,2:21:45，EVENT_ANTEON，1.00   
2018.1.1，4:59:45,EVENTCALIB，1.00   
2018.1.1,4:59:45,EVENT_MIRROR,-30.00   
2018.1.1,5:0:45,EVENTMIRRORCAM,1.00   
2018.1.1,5:16:20,EVENT_MIRROR,-25.00   
2018.1.1，5:16:25，EVENT_MIRROR，-20.00   
2018.1.1,5:16:30,EVENT_MIRROR,-15.00   
2018.1.1,5:16:35,EVENT_MIRROR,-10.00   
2018.1.1,5:16:40,EVENT_MIRROR,-5.00   
2018.1.1,5:16:45,EVENT_MIRROR,0.00   
2018.1.1,5:17:15,EVENTMIRROR,-30.00   
2018.1.2，4:10:55,EVENT_PANOMAN,0.00,0.00   
2018.1.2，4:12:55,EVENT_PANOCAM,1.00   
2018.1.2，4:16:55,EVENT_FLAG,1.00   
2018.1.2，4:23:25，EVENT_PANOMAN，12.00，0.00   
2018.1.2，4:23:26,EVENT_PANOMAN,24.00,0.00

![](images/9ea46e18af56dded3c4d9109f25a166bb161e5d07a4211d221542abaf3354f43.jpg)  
图5仿真记录脚本文件Fig.5Simulation record script file  
图6仿真结果 Fig.6Simulation results diagram   
图7参数面板界面设计图  
Fig.7Interface design of parameter panel

# 2.3 人机交互

参数面板显示界面基于CEGUI实现，它是一个自由免费的图形用户界面库，使用 $\mathrm { C } { + } { + }$ 实现，完全面向对象设计，同时支持多个图形库，官方提供了界面编辑器 LayoutEditor 和 Imageset[15]。LayoutEditor采用可视化的方法进行UI设计，生成XML格式的布局文件，将文件放入面向对象的图形渲染引擎资源目录可直接加载布局。系统设计的参数面板界面如图7，F12 键控制参数面板的显示与否，通过鼠标可自由选择所要显示的参数界面。

显示控制面板着陆器位置×： 0.001米 着陆器位置X： 0.001米 着陆器位置×： 0.001米 参数显示切换 参数面板显示1位： 0.002米 着位置： 0.00米 着陆器位： 0.002米 0.003米 左视窗显示切换 不星示着陆器俯仰角： 0.001度 着陆器俯仰角： 0.001度 着陆器培仰角： 0.001度着陆器滚转角： 0.002度 着陆器滚转角： 0.002度 着陆器滚转角： 0.002度 右视窗显示切换 不星示着陆器偏航角： 0.003度 着陆器偏航角： 0.003度 着陆器偏航角： 0.003度 视角控制 绑定着陆器1L ?参数面板显示1 不显示 不显示 绑定着陆器参数面板显示2 全景相机视角（左） 全景相机视角（右） 自由视角参数面显示 二维转镜视角（左） 二维转镜视角（右） 绑定上机参数面板显示5 月壤结构探测仪视角 降落相机视角 绑定国旗

比如在视点控制栏，可选择绑定具体载荷或者自由视角实现视点切换，当选择绑定着陆器时，以整个着陆器为屏幕中心，这里有两种模式：（1)通过鼠标完成整个着陆器的放大、缩小以及旋转，因为着陆器是静止固定的，所以整个空间环境都会随着着陆器一起运动；（2)通过F1键还原为以着陆器为中心，然后通过“W、A、S、D”这4个键控制着陆器的大小远近。当选择绑定全景相机时，全景相机始终处于屏幕中心，其他空间环境的变化都随着全景相机的运动而变化，这种局部视点的设计方式为全景相机的近距离探测仿真试验提供了方便，更能清楚直接地展示仿真结果；当选择自由视角时，可任意选择感兴趣的视点。

# 3月面近距离探测仿真系统的应用

月面近距离探测仿真主要是关于有效载荷探测过程、探测效果以及探测任务的仿真。考虑到载荷几何运动、光照效果的影响，为了更好地反映视景仿真特点，选取嫦娥五号全景相机进行月面近距离探测，仿真时系统可输出仿真时间、太阳高度角、太阳方位角、有效载荷姿态等参数，后期利用仿真系统输出的数据可做一些科学分析与结果验证。

# 3.1月面环拍覆盖分析

全景相机是为了获取着陆区高分辨率月表图像以及表取采样区高分辨率图像，用于着陆区地形地貌研究和综合研究。受着陆器、上升器相关部件遮挡以及全景相机转台运动范围等因素的影响，全景相机科学探测获取的立体图像只能覆盖嫦娥五号着陆区的南半部分，即着陆点附近水平 ${ 1 8 0 } ^ { \circ }$ 范围和俯仰向下 $9 0 ^ { \circ }$ 范围内的全景图像称之为全景相机月面环拍图像覆盖区域。假设全景相机初始位置为（偏航 $0 ^ { \circ }$ ，俯仰 ${ 0 } ^ { \circ }$ )，全景相机转台总共需要俯仰8次（俯仰角依次为 ${ 0 } ^ { \circ }$ 、 $- 1 2 ^ { \circ } 、 \cdots - 8 4 ^ { \circ }$ ，步长为$1 2 ^ { \circ }$ ），每次俯仰对应的半圈内需要偏航15 次（偏航角依次为 $- 8 4 ^ { \circ }$ 、 $- 7 2 ^ { \circ }$ 、·….、 $- 1 2 ^ { \circ }$ 、 ${ 0 } ^ { \circ }$ 、 $1 2 ^ { \circ }$ 、…、$7 2 ^ { \circ } , 8 4 ^ { \circ }$ ，步长为 $1 2 ^ { \circ }$ )，总共有120个成像位置，获取120 对立体图像就能覆盖着陆点南部水平${ 1 8 0 } ^ { \circ }$ 范围内的月面区域，但是此时获得的图像区域并不是最大月面覆盖区域，这与月面地形起伏以及全景相机初始位置有关。

当着陆器处于理想水平状态时，全景相机初始俯仰角设置为 $\alpha$ ，情况如图8（a），由图可知：

$$
\cos \beta = { \frac { h _ { 1 } + h _ { 2 } } { d } } \ , \qquad \beta = \operatorname { a r c c o s } \left( { \frac { h _ { 1 } + h _ { 2 } } { d } } \right) , \qquad \alpha = 9 0 ^ { \circ } \ - \beta \ .
$$

当着陆器受月面起伏的影响倾斜一定角度 $\theta$ 时，情况如图8（b），表1给出了全景相机的成像策略。全景相机成像时，每圈成像15次。当全景相机俯仰8次时，共成像120对立体像对；当全景相机俯仰7次时，共成像105对立体像对。

![](images/4a05b49f4ff2800a0e7ed78dc13f3e1489d6874de0c66200a3d24483f7488d8b.jpg)  
图8（a）理想水平状态图；（b）非理想状态图 Fig.8（a）Ideal level state diagram; (b）Non ideal state diagram

# 表1着陆器等效倾角与全景相机成像策略

Table 1Equivalent inclination and panoramic   

<html><body><table><tr><td colspan="3">camera imaging strategy</td></tr><tr><td>序号</td><td>等效倾角/°</td><td>起始俯仰角/°</td></tr><tr><td>1</td><td>0= 0</td><td>-7，俯仰7圈</td></tr><tr><td>2</td><td>0<θ≤1</td><td>-6，俯仰7圈</td></tr><tr><td>3</td><td>1<θ≤2</td><td>-5，俯仰7圈</td></tr><tr><td>4</td><td>2<θ≤3</td><td>-4，俯仰7圈</td></tr><tr><td>5</td><td>3<θ≤4</td><td>-3，俯仰7圈</td></tr><tr><td>6</td><td>4<0≤5</td><td>-2，俯仰7圈</td></tr><tr><td>7</td><td>5<0≤6</td><td>-1，俯仰8圈</td></tr><tr><td>8</td><td>6<0</td><td>0，俯仰8圈</td></tr></table></body></html>

系统环境中，根据实际情况调整全景相机姿态以获取高分辨率月表覆盖图像。通过三维调试界面输入全景相机姿态参数，仿真全景相机获取图像的过程，得到14对立体图像并依次输出，合成系统内全景相机环拍最大覆盖区域范围内部分图像覆盖图(28幅图像），如图9(a)。图9(b)为全景相机左右相机(各14幅)图像合成的红绿立体图像[16]。

![](images/1c1f944824e39950ebfd8e51cc8ac9b26c8d193d143fc25ba6742184b711702e.jpg)  
图9（a）全景相机14对立体图像覆盖图；（b）全景相机红绿立体图

Fig.9（a）Stereo imagecoverage of panoramic camera；（b）Red and gren thre-dimensional mapof panoramic camera

# 3.2成像几何参数计算

为了保证探测数据具有较高的信噪比，需要掌握探测期间的光照条件，以判断载荷是否具备开机条件。同时，不同光照条件下，由于二向反射特性的差异，需要获取成像期间的高度角、方位角和相位角，以进行光度校正处理[17] 。

太阳方位角一般是以目标物正北方向为起始方向，以太阳光入射方向为终止方向，按顺时针方向测量的角度 $\alpha$ ，太阳高度角则是太阳光线与月平面的夹角 $\beta$ ，示意图如图10，十字形为全景相机位置，五角星为全景相机成像目标， $\theta$ 为相位角（即太阳光入射光线与成像目标出射光线之间的夹角）。

计算出月球上2018年1月嫦娥五号预着陆点一天时间的太阳方位角和太阳高度角，取月昼时间的角度，变化情况如图11(a)和图11(b）。

![](images/8336008ffe31ef30cdf113e762f0fa726a7722d7b3f8520f5f2c3604e24bfcd3.jpg)  
图10太阳方位角、太阳高度角以及相位角示意图 Fig.1OSchematic diagram of solar azimuth，solar elevation angle and phase angle

![](images/ec3c7949de1785aebfe25b942d5c76463d70ef702ab929fa45556be19b2b8a3b.jpg)  
Fig.11（a）The change of solar azimuth；（b）The change of solar elevation angle

全景相机初始位置(偏航 ${ 0 } ^ { \circ }$ ，俯仰 ${ 0 } ^ { \circ }$ )为正南方向(即目标物正北方向），将太阳入射光线的反方向向量记为单位向量 $A$ ，出射光线方向向量记为单位向量 $B$ ，由 $\scriptstyle \cos \theta = A \cdot B$ 得 $\theta { = } \operatorname { a r c c o s } \left( A \cdot B \right)$ 。设全景相机成像目标位置为原点，目标正东方向为 $x$ 轴，正北方向为 $y$ 轴，垂直于月平面向上为 $z$ 轴,根据几何关系可知： $\mathbf { \delta A } = \left[ \cos \beta \mathrm { s i n } \alpha \right.$ ， $\mathrm { c o s } \beta \mathrm { c o s } \alpha$ ， $\mathrm { s i n } \beta ]$ ，

$\boldsymbol { B } = \left[ ~ \mathrm { c o s } f \mathrm { s i n } ( ~ - p ) ~ , ~ \mathrm { c o s } f \mathrm { c o s } ( ~ - p ) ~ , ~ \mathrm { s i n } f \right] ,$ （20其中， $\alpha$ 为太阳方位角； $\beta$ 为太阳高度角； $f$ 为全景相机俯仰角绝对值； $p$ 为全景相机偏航角（正南方向为 ${ 0 } ^ { \circ }$ ，偏东为正，偏西为负)。图12给出满足全景相机开机条件的同一时刻，即太阳高度角不变的情况下，全景相机环拍各姿态对应的 $\theta$ 值变化情况。

![](images/ef00ad09b78229ed556e9d16e09a370b984c80a5efbc88dbf1cacc2b8e909492.jpg)  
图11（a）太阳方位角变化图；（b）太阳高度角变化图  
图12 不同姿态下的 $\theta$ 值  
Fig.12Theta value of different attitude of panoramic camera

由图可知，相位角 $\theta$ 随着全景相机姿态的改变而变化，当俯仰角不变时，相位角随着偏航角的增大而增大；在一个偏航周期内，相位角随俯仰角的增大而减小。

此外，当全景相机姿态固定时， $\theta$ 随着太阳高度角的改变而变化，根据上文得出的太阳方位角和太阳高度角数据，计算出月昼时间内不同太阳高度角下 $\theta$ 的值，变化情况如图13，由图可知，全景相机姿态固定时，相位角与太阳高度角在一定范围内呈正相关，在一定范围内呈负相关。当俯仰角较小时，相位角较大，成像范围较广，此时相位角与太阳高度角变化趋势相同；当俯仰角较大时，相位角较小，成像范围变小，此时相位角与太阳高度角的变化趋势相反。

![](images/2827dc0b49b4e895cf54b6d1e03f745b462083d8a87b3159e174e0d7658cd1d3.jpg)  
Fig.13Phase angle variation of different solar elevation angle

用此仿真系统模拟不同太阳高度角下全景相机的探测效果，图14(a)和图14(b)分别是不同 $\theta$ 角下全景相机所拍图像。由图可知， $\theta$ 角不同，全景相机拍摄图像质量存在一定差异，这就说明太阳光照对全景相机工作效果有一定的影响。

![](images/41e703fd901ec39f1a103dde60942c304c74c4ea6931f04d5fe0b8a5a06ed3fc.jpg)  
图13不同太阳高度角下相位角变化图  
图14不同相位角下的拍摄图像 Fig.14Images taken at different phase angles

# 4结论

随着探月工程的不断推进，灵活、快速、可扩展、可交互的三维可视化仿真系统的研究具有明显的现实意义。构建的月面近距离探测仿真系统能够对嫦娥五号着陆器进行实时视景演示，不仅仅适用于全景相机，对于其他有效载荷同样适用。系统的三维场景调试界面可直接控制三维场景更新及载荷姿态运动，实现有效载荷的探测过程及探测任务仿真。系统最大的优势是采用灵活性和可扩展性强的模块化思想进行设计，各模块相互独立又相辅相成，支持系统的后续完善和开发，通过更改各模块内容同样适应于其他行星表面近距离探测。对全景相机进行了月面环拍覆盖仿真和分析，并与全景相机实验中的拍照结果进行比对，验证了仿真系统的正确性。当然该系统还有可完善的空间，比如可以考虑与三维立体硬件相结合开展主动立体显示，采用双目立体显示技术能够使人眼在二维显示平面获得立体视觉[18]

# 参考文献：

[1］叶培建，孙泽洲，饶炜．嫦娥一号月球探测卫星研制综述［J].航天器工程，2007，16(6)：9-15.Ye Peijian，Sun Zezhou，Raowei.Research and development of Change-1 ［J]. SpacecraftEngineering，2007，16(6） : 9-15.  
[2] 潘晨，庞丹，五轩.中国探月再给国人一个惊喜（上）一探月工程三期再入返回飞行试验任务透视［J]．中国航天，2014(11)：6-9.Pan Chen， Pang Dan，Wu Xuan. Chinese lunar give people a surprise (a)-three lunar explorationrentry return flight test mission perspective [J]. Aerospace China,2014(11）:6-9.  
[3] 张巧玲.欧阳自远院士描绘嫦娥工程后续蓝图［N].科学时报，2011-12-9（1).  
[4] 曾鑫．可视化仿真技术设计与实现［J].黑龙江科技信息，2008(36)：85.Zeng Xin. Design and implementation of visual simulation technology [J]. Heilongjiang Scienceand Technology Information，2008(36）: 85.  
[5] Shy K S,Hageman JJ,Le JH. The role of aircraft simulation in improving flight safety throughcontrol training ［M]. California:National Aeronautics and Space Administration Dryden FlightResearch Center，2002.  
[6] Curlett B P.A software framework for aircraft simulation [R/OL].（2008-10-01）[2017-03-05]. https://ntrs.nasa.gov/search.jsp? $\mathrm { R } = 2 0 0 8 0 0 4 2 3 8 0$ ：  
[7] Faust J, Simon C,Smart W D.A video game-based mobile robot simulation environment [C]//2006 IEEE/RSJ International Conference on Inteligent Robots and Systems. 2O06:3749-3754.  
[8] Dunn T L，Wardhani A.A 3D robot simulation for education [C]// Proceedings of the 1stinternational conference on Computer graphics and interactive techniques in Australasia and SouthEast Asia. 2003:277-278.  
[9] 肖笛．电子对抗中三维仿真关键技术的研究与实现［D].南京：南京航空航天大学，2010.  
[10]杨波.基于OGRE 图形渲染引擎的视景仿真技术的研究与实现［D]．成都：电子科技大学，2006.  
［11］黄卫权，王晓明，陈怀友.某型导弹视景仿真系统设计与实现［J].计算机仿真，2012，29(7): $2 5 2 - 2 5 5 + 2 5 9$ ：Huang Weiquan，Wang Xiaoming，Chen Huaiyou. Design and Implementtain on visual simulationof missile system [J]. Computer Simulation，2012，29(7）: $2 5 2 - 2 5 5 + 2 5 9$ ：  
[12］王亚明，苏彦，封剑青，等．月球两极探测进展［J].天文研究与技术，2016,13(3)：300-309.Wang Yaming，Su Yan，Feng Jianqing，et al.A review of lunar polar exploration［J].Astronomical Research & Technology，2016，13（3）：300-309.  
[13］雷军环，曾凡喜，吴名星.基于四叉树的视点相关LOD地形仿真算法研究［J]．制造业自动化，2010,32(8)：211-214+228.Lei Junhuan， Zeng Fanxi，Wu Mingxing. The study of the LOD algorithm based on quad-treestructure [J]. Manufacturing Automation，2010,32(8）: 211-214+228.  
[14］王琦.Autodesk 3ds Max 2010 标准培训教材［M]．北京：人民邮电出版社，2009：32-33.  
[15］宗群，徐锐，李庆鑫.基于OGRE的无人机全轨迹实时 视景仿真系统［J]．控制工程,2015(1) : 1-7.Zong Qun，Xu Rui,Li Qingxin.A real time visual simulation system for unmanned aerial vehicle[J].Control Engineering of China，2O15（1）：1-7.  
[16] 李伟锋.基于红绿立体影像的地形三维可视化研究——地形数字像对的立体显示［J].科技风，2010(11)：207-209.Li Weifeng. Study on 3D terrain visualization based on stereo images of red and green-Stereodisplay of terrain digital image pairs [J]. Technology Trend，201O(11）:207-209.  
[17] 许学森，刘建军，刘斌，等.月表光度模型研究进展［J].遥感技术与应用，2016,31(4)：（204 $6 3 4 - 6 4 4 + 6 5 2$ ：Xu Xuesen，Liu Jianjun，Liu Bin，et al. Progress on research of lunar photometric model [J].Remote Sensing Technology and Application，2016,31(4） : $6 3 4 - 6 4 4 + 6 5 2$   
[18] 高兴烨，刘建军，任鑫，等．双目立体显示技术在月表形貌三维可视化中的应用［J]．天文研究与技术，2016，13(3)：358-365.Gao Xingye，Liu Jianjun，Ren Xin，et al. Application of binocular stereo display technology inthree-dimensional visualization of the Moon [J].Astronomical Research & Technology，2016,13(3) : 358-365.

# Implementation and Application of the Lunar Exploration Simulation System

Zhang Jing $^ { 1 , 2 , 3 }$ ， Liu Jianjun $^ { 1 , 3 }$ ， Gao Xingye $^ { 1 , 3 }$ ， Chen Zheng4 (1.TheSciencendAplcationCenterforooandDeepSaceExploration，NtioalAstrooicalObsevatio,Chnsecadeyfiec, Beijing 00o12,China,Email：zhangjing@nao.cas.cn；2.Universityof Chinese Academyof Sciences，Beijing10o049,China； 3.KeyLaboratoryof Lunarand Deep Space Exploration，National Astronomical Observatories，Chinese Academyof Sciences, Beijing 100012，China；4.Beijing University of Aeronautics and Astronautics，Beijing 100083,China）

Abstract：A3D display system for lunar exploration simulation is designed，which is used to lunar realtime visual display and load motion simulation.The system is based on the open source OGRE graphics engine，combined with the modeling software 3DMAX,integrated development tols Studio Visual,3DS format to MESH format tol 3ds2mesh，and terrain generation plug-ins，which completed the construction of 3D entity model and related land load,and the lunar environment were simulated.User interface of this system is built on CEGUI libraries.The 3D scene debugging interface is constructed based on MFC，which is convenient to directly control 3D scene update and adjust entity model atitude of the detection process simulation of payload. Finall，the simulation experiment is caried out with panoramic camera as an example.

Key words: Simulation； Lunar surface exploration； Model building；OGRE；Panoramic camera