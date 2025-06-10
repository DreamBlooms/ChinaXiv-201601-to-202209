# 基于BIM的大型钢结构虚拟施工仿真系统研究及应用

胡德军1 张柏岩² 王帅1 寇金龙²(1．浙江耀厦控股集团有限公司，杭州_，310000;2．浙江大学建筑工程学院，杭州_，310058)

【摘要】本文研究了基于BIM的大型钢结构虚拟施工仿真系统并应用于实际工程之中。大型钢结构施工具有环境因素复杂、操作要求高、安全隐患多等特点，且难以周全考虑。针对这些难点，Unity3d 和 BIM结合的虚拟施工仿真系统，能够充分利用并可视化工程设计信息，逼真的展现不同情境下的施工现场，可用于施工现场管理和技术交底，全面排查各种质量安全隐患。该系统在杭州上城区体育中心大跨度钢桁架施工中的成功应用，大大提高了施工效率，充分保障了施工过程中的质量与安全。

【关键词】虚拟现实;Unity3d;BIM；钢结构；施工设计【中图分类号】TU17 【文献标识码】A

作者简介：胡德军（1974-)，男，企业技术负责人，高级工程师，主要研究方向：建筑新技术在项目施工管理中的应用。

# 1引言

伴随着信息技术的不断进步，施工管理的信息化程度日益发达，在施工成本、质量、进度和安全的控制等方面也得到了长足的发展。继住房和城乡建设部在《关于推进建筑业发展和改革的若干意见》中明确提出“推进建筑信息模型（BIM）等信息技术在工程设计、施工和运行维护全过程的应用，提高综合效益”，BIM技术近年来在建设工程中的应用逐渐走向成熟，在工程信息管理[1]、施工场地动态布置[2]、施工成本控制[3]等方面的应用大大提高了施工管理效率。

为进一步满足施工现场可视化的需求，帮助工程管理者更好地进行项目决策和现场管理、为工人提供高效的岗前培训与安全教育，虚拟现实技术（VR）与BIM技术的结合应用成为当下的研究热点。Unity3d是一款综合性VR开发平台，能够实现与BIM的高效对接，开发者能够通过编写C#脚本来实现不同的VR交互体验。以Unity3d为平台的虚拟仿真已经在装饰[4]、测绘[5]、矿山[、船舶[方面进行了相关开发与应用，并取得了不错的效果。

在施工领域VR的应用仍处于起步阶段，多数仍采用动画渲染或功能固定的商用模板化VR软件，交互体验不足，应用效果也会大打折扣。杭州市上城区体育中心大跨钢桁架整体提升工程具有工序复杂、操作要求高、安全隐患多等特点，故对VR系统的交互性要求较高。

本文针对该工程研究了BIM+Unity3D的大型钢结构虚拟施工仿真系统，并成功进行了工程应用，有效提高了施工效率、保障了施工过程中的质量与安全。

# 2 工程概况

杭州上城区体育中心为叠合式的体育综合场馆，主体结构为框架-剪力墙结构，局部钢结构。体育中心五层和九层分别为水球馆和篮球馆，楼盖为钢桁架结构，下部设混凝土看台。钢桁架楼盖由六榀大跨度钢桁架和联系钢梁组成，跨度39.2米m，宽度33.2米m，高4.1米m。该大跨钢桁架自重达390多t吨，经有限元分析计算，跨中最大变形约为 $\cdot$ 。经专家论证，采用先在混凝土楼面进行楼盖的拼装，然后利用液压提升系统将钢桁架楼盖整体提升到位的方法进行施工，如图1所示。

![](images/3005611eb45b97c936aa7e82ae740d071a726906aec364d566fd898a51ade8f2.jpg)  
图1钢桁架楼盖整体提升施工

该大跨钢桁架共设置12个提升吊点，并在安装位置上一层搭建提升平台、安装液压提升设备。在液压提升施工过程中需要严格保证不同提升吊点的同步性，要求各吊点与控制吊点间的高差控制在 $\pm 2 0 \mathrm { m m }$ 。当钢绞线的斜度大于1°时，需暂停提升，并通过钢丝绳将结构四角与邻近主体结构临时连接，起到限制水平摆动。此外，液压油缸以及液压同步控制设备也需要合理的现场布置从而把控整个施工过程。由于环境因素复杂，操作要求高、安全隐患多，故需要提高施工交底质量并逐一排查隐患、发现问题，以保障该大跨钢桁架结构液压提升的顺利进行。

# 3基于BIM的大型钢结构虚拟施工仿真系统

该大型钢结构虚拟施工仿真系统的实现主要包括三维模型的导入、场景元素的渲染、交互指令的添加、操作界面的设计和系统的发布五个流程，如图2所示。

![](images/7babf26e6dd64036352bc805952c27b685894f9ab2175b5694c7be825692e064.jpg)

图2系统的实现流程

# 3.1三维模型的导入

调取已有的体育中心BIM模型，考虑钢桁架整体提升时的施工进度，仅保留整体模型五层及以下按进度已完成施工的部分模型，如图3(a)所示。

![](images/3cc2bcff99d0ac7402e24aa77d9d4d65679d3751859e40bba50c844582ffb3ce.jpg)

将模型在Revit平台下导出为FBX后缀的文件，并在Unity3d中进行导入，如图 3(b)所示。

模型导入后需要为模型添加物理特性，来加强模型对原型的还原程度。碰撞体积是模型最重要的特性，若缺乏碰撞体积，不同物体在运动时会出现互相穿越的现象。通过为模型添加属性，选择Physics-Collider可实现碰撞体积的添加，对于造型复杂的结构可以选择MeshCollider作为碰撞体。除了碰撞体积，要使模型能够在受到各种力的作用下产生真实的物理效果，如受到重力会下坠等，需要为模型添加刚体特性，选择添加Physics-Rigidbody属性即可。

# 3.2场景元素的渲染

为了逼真模拟实际施工现场的情景，在场景添加多种场景元素的渲染，这些元素包括音效、天空、光照、天气等。

在杭州上城区体育中心的施工现场主要存在四种声音，即现场多种交错的作业声、雨天的风雨声、人物的脚步声以及钢桁架整体提升时液压油缸的启动声。考虑前三种声音不论人物身在何处，声音的大小差不多相同，故为人物添加音效属性，选择Audio-AudioSource，并导入相应的音频文件。而液压油缸位置固定，启动声的大小随人物与液压油缸的位置远近而变化，故为液压油缸添加音效属性。

天空由Unity3d内置的Skybox控制，设置为晴朗无云的天空，太阳的位置可以随光源一同控制。

场景中一切物体的渲染通过光照来实现。默认光源为DirectionalLight，即表现为太阳光，具有方向性。通过控制光源的Rotation属性中 $x$ 、y、 $z$ 的值，可以控制光源的照射方向。当光源方向平行于地表，则表现为黄昏或清晨；当光源方向垂直于地表，且光源位于主体建筑之上，则表现为正午；当光源位于主体建筑之下，则表现为深夜。场景中的Skybox 和太阳会跟随光源产生相应的变化，如图4(a)和图4(b)所示。考虑夜间安装作业，本系统在相应位置布置了点光源进行照明，如图4(c)所示。

![](images/aa422368a11239287c1f647601e9e881aeb9f6ba5403757ca9f57c377d6ddfe8.jpg)  
图3考虑钢桁架提升时施工进度的模型  
(a)黄昏、清晨时分

![](images/a795beace4a20d154d04754d47ac00be889b167e22db787639d881aff79dda12.jpg)  
(b)接近正午

天气系统由ParticleSystem来表现。由于提升施工在夏季进行，故主要应考虑雨天对施工的影响。在Unity3d中粒子特效的控制参数接近上百种，但对于模拟雨天而言主要可以通过分别调整Duration、Start Speed、Maxparticles、Shape 和Renderer来控制雨滴的生命周期、下落速度、数量、方向和形状。图5为雨天施工的模拟情景。

![](images/b208c7ea941918539606c750756eccf7d076161be4a253e062db62682d19494c.jpg)  
图4不同光照下的施工场景  
图5雨天施工的模拟

# 3.3交互指令的添加

交互的实现主要通过编写C#脚本并绑定到对应的对象之上。Unity3d中人物的所有互动是由Animator模块和C#脚本共同控制。Animator模块主要作用是提供人物的动作动画，本工程所用的人物的动作动画逻辑如图6所示。每一个人物模型都包含一个附属模块Avatar，即按关节将人物划分了不同的部位，如手、脚、胳膊、腿、肩、脖子等。可以通过定义动作参数来实现不同部位的动作。C#脚本在控制人物方面的作用主要有两个：

1）1、改变人物模型的空间位置及方向；

$\cdot$ 设置按键来实现动作参数值的改变，如下列语句就为按下"c"键控制人物蹲伏的部分C#语句：

Bool crouch $\ O =$ Input.GetKey (KeyCode.C);   
m_Character.Move (crouch);

图7为本工程使用的人物模型，人物能够实现站立、行走、奔跑、跳跃与蹲伏，可以全方位进行施工现场的体验。此外，本系统为还为人物添加ThirdPersonCamera和FirstPersonCamera来实现第三人称视角和第一人称视角，并通过C#脚本实现视角的切换：

Void SwitchCamera (int index) {   
int $\dot { \mathbf { i } } = 0$   
for $\mathbf { \dot { i } } = 0$ ;i<cameras.Length;i $^ { + + }$ {   
if(i $! =$ index){   
cameras[i].GetComponent<Camera>().enabled $\mathbf { \Sigma } = \mathbf { \Sigma }$ false; }   
else{   
cameras[i].GetComponent<Camera>().enable $\ O =$ true;}}}

除了人物的控制外，钢桁架提升过程中的关键工序也能够进行操作模拟。相比于BIM模型，钢桁架的VR模型被调整至混凝土楼板之上。每一榻桁架两端均创建液压提升的下吊点，通过小键盘的 ${ ^ { 6 6 } 8 } \mathrm { } ^ { \prime \prime }$ 和“5”键控制升降。部分控制C#语句如下：

float up $\mathbf { \Sigma } =$ Input.GetAxis ("SteelTruss"); floatrisingHeight $= 9 . 0 1$ if $( \mathrm { u p } > 0$ { if (transform.position[1] $<$ risingHeight){ transform.Translate (2 \* Vector3.up \* up \* 'ime.deltaTime, Space.World); } } if $( \mathrm { u p } < 0 \dot { }$ { if (transform.position[1] $> 0$ {

transform.Translate (2 \* Vector3.up \* up \*Time.deltaTime, Space.World); }}

钢绞线也需要同钢桁架一起运动来实现钢桁架提升的视觉效果。相比于钢桁架，钢绞线还有变短或伸长的过程，故除了同步改变其空间位置属性，还需要调整Transform-Scale属性。图8(b)为钢桁架正在提升时的效果图。

![](images/170914c9dbe623ae4ba99987230e66803690744c8911680d896c165dddcb1985.jpg)  
图6人物动作动画逻辑关系

![](images/d24c475ad9eaca8816c8816bb9b3385b2ef7cad0b0ed75ad53b9962ba745e601.jpg)  
(d)蹲伏

![](images/6e0ed254543e813336b00cde9ea3a6f90ea6243d59488cfc8a2e95e6f99e9d84.jpg)

液压提升吊点之间提升略微不同步的情况，以全面模拟液压提升过程中的各种状况。为了能够同时展现不同天气、时间下的施工情景，本系统还为天气和光照添加相应的交互指令。天气为晴天和雨天之间的切换通过控制开关特效粒子系统实现：

if (Input.GetKeyDown (KeyCode.Tab)) { i $\mathrm { f } ( \mathrm { r a i n } = = 0 ) .$ {   
objects.SetActive (false);   
$\mathrm { { r a i n } } = 1 ; \}$ （20   
else{   
objects.SetActive (true);   
$\operatorname { r a i n } = 0 ; \~ \} \}$

粒子特效系统关(开)，对应于晴天(雨天)，按下"Tab"键可切换为开(关)，对应于雨天(晴天)。此外，还可以通过调整光照的明暗程度作进一步的修饰。

![](images/96417c699c236dfb3a936b17dc274b5ff8f6422961ac06ccfd99ac956b0de480.jpg)  
(f)第一人称视角图7场景人物的不同状态

![](images/4a9c0f9cde2ae7437a1e7e8c34bd88de98a23d0cba5cc2ab1797dfcf761b7521.jpg)  
(a）钢桁架待提升  
(b）钢桁架正在提升图8钢桁架整体提升过程的模拟

光照通过调 整Directional Light 中Rotation 属性中 $x , y , z$ 的值 $( - 1 8 0 { \le } x , y , z { \le } 1 8 0 )$ 进行控制，这里是通过改变 $x$ 值进行控制：

float $\boldsymbol { \mathrm { u p } } =$ Input.GetAxis ("SunLight"); transform.Rotate (Vector3.right （204号 $^ *$ up \* Time.deltaTime, Space.World);

这里若按下小键盘“ $\cdot _ { + } ,$ '则“SunLight”值为一正值，对应于 $x$ 值沿正方向变化，即场景中太阳自西向东运动；若按下小键盘“-”则"SunLight"值为一负值，对应于 $x$ 值沿负方向变化，即场景中太阳自东向西运动。

# 3.4操作界面的设计

操作界面(User Interface,UI)一方面可以帮助体验者快速上手虚拟施工仿真系统，另一方面也可以简化操作。

图9为本工程开始界面的UI，主要由标题、背景贴图、指示按钮组成。首先需要在Unity3d中创建一个新的 Scene，可以利用Unity3d自带的MainMenuGUI的C#脚本形成一个基础框架，在此基础上添加标题等元素并根据需求进行调整。

提升过程中还添加了风，并考虑了不同

![](images/3fbf4f195a4eb56c7eaff56fa0701fed6b125b2a3613701968c986d7d0f18e22.jpg)  
图9开始界面的UI

![](images/9c9e77d58f1a676901ed5d3deea3d860717466bcc8a31d2ba69ee53d8f751eb3.jpg)  
图10场景中的UI

值得注意的是从开始界面进入到场景之中需要针对按钮编写C#脚本语句，如这里“开始VR之旅"按钮赋予的C#语句为：

if(GUI.Button(new Rect(playButton),"开始 VR 之旅")){

StartCoroutine("ButtonAction","Hengjia");}

表明按下“开始VR之旅"按钮会跳转至“Hengjia"这个场景，即虚拟施工的场景。其他按钮对应的C#脚本与此类同。

选择需要发布的Scene和目标发布平台。Unity3d支持多平台程序发布，如Windows、Mac、Linus、IOS、Android等平台。发布之前需要整理好所有的Scene文件，一般大于等于两个，一个Scene用于开始界面的UI设计，其他的为各种施工场景，如图11所示。整理完毕之后选择Build即可完成系统的发布，生成.exe 格式的文件。

图10左上角和右上角的图标为施工场景中的UI按钮，分别可以实现重新开始和回到开始界面的功能。

# 3.5系统的发布

为了帮助项目管理者、工人等能够随时随地使用虚拟施工仿真系统，而不受限于开发软件，需要进行系统的发布。

选择File-BuildSettings进入发布界面

# 3.6系统的特色

(1)高效性

。可以有效地利用已有的BIM模型，与工程紧密结合，按照实际模型创建工程虚拟施工场景。

(2)_(2)逼真性

。真实地还原了施工场景，并引入了物理特性，实现碰撞、重力等模拟；音效、天

空、天气和光照等元素的组合能够展现各种可能的施工情景。

# (3）(3)高度交互性

。通过编写C#脚本，可以设计出丰富多样的交互形式，包括人物的控制、施工过程的控制、天气和时间的控制等，不受限于软件。

![](images/45f26565aa462bdeaeddd7078adf84b1719c7d430bf4915bb0e5b471cc76bd3d.jpg)  
图11系统的发布

# 4 工程应用验证

本文研究的基于BIM的大型钢结构虚拟施工仿真系统已成功应用于杭州市上城区体育中心大跨钢桁架整体提升工程的现场管理和工人培训之中。该系统全方位模拟了真实的现场情景，考虑了风雨天、阴天、晚上等环境因素对钢桁架提升作业的影响，同时也考虑了提升不同步等随机因素的影响，在实际应用中取得了出色的成效：

(1)1、通过虚拟仿真系统的漫游体验功能，全面考量了液压油缸以及液压同步控制设备的现场布置方案，如图12所示。最终选择布置在钢桁架拼装层的北侧，此处既有宽阔的场地空间又能提供充足的视野把控整个钢桁架液压提升过程。

# (a)VR中的布置方位

![](images/bb2e86dc34fdbfe6d52b3e9c7944f07e8ee3e0e6bd5069853ce1d815f9a61019.jpg)  
图12液压油缸以及液压同步控制设备的现场布置

![](images/243ace50139986ad14dfb1ac2d865cd0b0068b65177f810884db964e5ff19969.jpg)

（2）2、通过考虑风及液压提升吊点之间提升略微不同步对提升的影响，发现在提升过程中会出现钢桁架与型钢柱节点接触卡死的情况，导致无法继续提升。故利用虚拟施工仿真提前找出了容易发生接触卡死的型钢柱节点，并安排工人进行现场监控，在出现此类现象之时便第一时间进行解决，如图13所示，大大提高了施工效率。

# 5总结

以杭州市上城区体育中心大跨钢桁架液压整体提升工程为背景，研究了基于BIM的大型钢结构虚拟施工仿真系统。该系统有效地利用了已有的BIM模型，可以帮助工程管理人员快速地完成施工现场的虚拟施工仿真场景搭建工作。

该系统具有高效性、逼真性和高度交互性的特点，在上城区体育中心大跨钢桁架液压提升施工中的应用，帮助施工管理者一方面更加合理地设计了液压油缸以及液压同步控制设备的现场布置方案；另一方面提前为钢桁架与型钢柱节点接触卡死的情况做好了准备，大大提高了施工效率。此外，该系统可形象化地为工人进行施工前的交底与培训工作，有效地保障了施工质量与安全。

![](images/1aac169cabcf644701aa8e0c548f99ccd1cc0009626d5186f6be33d0f031c8a7.jpg)  
(a)VR中的情况

![](images/99add76be8a35e2153f41b8981a634a0008753f8aa279687f965fa868836ec24.jpg)  
图13钢桁架与型钢柱节点接触卡死情况

# (b）现场解决问题

# 参考文献

[1]叶浩文,邹俊,孙晖,杨玮.基于BIM的施工总承包管理系统研发与应用[J]施工技术,2016,45(12):29-33.  
[2]王廷魁,郑娇.基于BIM的施工场地动态布置方案评选[J].施工技术,2014,43(3):72-76.  
[3]胡铂.基于BIM的施工阶段成本控制研究[D].武汉：湖北工业大学土木工程与建筑学院,2015:1-57.[4] 邵正达,宋天任.基于BIM的建筑VR 交互技术研究与应用[J]土木建筑工程信息技术,2018,10(3):17-21.  
[5]季铮,谢予星,王玥.基于Unity3D的虚拟测量实验系统[J].测绘通报，2016,10:97-100.  
[6] 修春华,孙秀娟,苗坡.基于Unity3D的虚拟矿山漫游仿真系统设计与实现[J]金属矿山,2015,4:262-266.  
[7]臧睿.船舶虚拟吊装系统的优化设计及关键技术研究[D].杭州:浙江大学化学工程与生物工程学院,2016:1-73.

# Research and Application of a BIM based Virtual Construction System for Large Steel Structures

Hu Dejunl, Zhang Baiyan², Wang Shuai1, Kou Jinlong²

(1. Yaosha Holding Group Co., Ltd, Hangzhou 31000o, China; 2. Institute of Structural Engineering, Zhejiang University, Hangzhou 310058, China)

Abstract: A BIM based virtual construction system for large steel structures has been researched and applied in a construction project in this paper. Environmental complexity, high requirement for operation and multiple potential safety hazards are the basic features of the construction for large steel structures, which are difficult to be considered thoroughly. Aimed at those difficulties, the virtual construction system integrating Unity3d and BIM can fully utilize and visualize the information of construction design. It is able to help build a virtual construction system which vividly displays the construction scene under various circumstances, and can be applied for construction management, technical disclosure as well as thorough check for potential quality and safety hazards. The system has been successfully applied in the large-span steel truss construction process of Hangzhou Shangcheng District Sport Center project, which evidently enhanced construction efficiency and fully guaranteed the quality and safety in construction process.

Key Words: Virtual Reality; Unity3d; BIM; Steel Structure; Construction Design

第一作者胡德军相关信息：  
胡德军，男[1974-]，企业技术负责人，高级工程师，研究方向：建筑新技术在项目施工管理中的应用。  
电话：13173603690  
地址：杭州市莫干山路789号，美都广场A座。