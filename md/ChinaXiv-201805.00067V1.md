# 面向虚拟维修训练的自抓取虚拟手交互行为构建\*

董健康，王启峰，耿宏(中国民航大学，电子信息与自动化学院，天津 300300)

摘要：针对当前维护训练模拟器（MTD）不能很好地向受训者展示飞机维修过程中的具体维修动作的问题，构建一种自抓取的虚拟手与相应的交互行为，以提高机务培训质量。通过分析维修的基本动作要素，定义与构建基于蒙皮骨骼的虚拟手动作库；在场景漫游阶段，实时获取视角位置来驱动虚拟手运动，减轻场景漫游下的虚拟手控制负荷；在具体维修操作阶段，利用所提的交互行为算法，将虚拟手的位置自调节与骨骼动画osgCal相结合，通过调取动作库中的相应动作，完成具体的维修任务。实验结果表明，所提出的方法能较好地展现具体的维修操作，对于虚拟维修训练具有良好可用性。

关键词：虚拟维修；虚拟手；骨骼动画osgCal；人机交互 中图分类号：TP391. doi:10.3969/j.issn.1001-3695.2017.10.1021

# Self-fetching virtual hand interaction behavior building with virtual maintenance training

Dong Jiankang, Wang Qifeng, Geng Hong (College ofElectronic Information & Automation,Civil Aviation UniversityofChina,Tianjin 30o300,China)

Abstract:Focusing on the problem thatthe currnt maintenance training device (MTD)can't perfectlyreflects the specific maintenanceactions during theaircraft maintenance for traines,this paper establishedaself-fetching virtual handand the interaction behaviors toimprovethetrainingquality.Byanalyzingthebasic elements ofmaintenance operations todefineand builthe virtualhandoperation librarythatbasedon Sinned Mesh.In thesceneroaming stage,inorder toreducethecontrol load,itriventhevirtualhandbytheviewpointpositionwhichacquiredinrealtie.Inthespecificmantenaceoperatiostage, itused theinteractivebehavioralgorithmtocombine thepositionself-adjustmentof thevirtualhandwiththeskeletonnimation osgCal,bycallngtheelevantactionsinteactionlibrarytocomplete thespecificmaintenancetasks.Theexperimentalresults showthat he proposed methodcanreflect the specific maintenance operations andhavea goodusabilityforvirtual maintenance training.

Key Words: virtual maintenance; virtual hands; skeleton animation osgCal; human-machine interaction

# 0 引言

MTD通过模拟真实飞机的操作效应和内部逻辑，采用虚拟驾驶舱（VC）、3D虚拟飞机（VA）和动态原理图三种形式来提高受训者的理论和实践水平。在VA中，受训者可以利用键盘和鼠标进行机外和机内的漫游，了解飞机内部结构和各系统部件位置，排除教员设置的各种故障，熟悉飞机维修操作的流程，但是其对具体的维修操作动作却缺少展示，而让受训者能在MTD中就能认知具体的维修操作对于提高受训人员的实践技能有着实际需求。

虚拟手作为虚拟现实技术的重要组成部分，其在虚拟装配、虚拟维修等领域正扮演着越来越重要的作用[1]，具有虚拟手的维修训练系统除了能使受训者熟悉维修流程外，还能使受训者认知具体的维修操作动作。当前基于虚拟手的交互模式有基于外部设备驱动的虚拟手与自抓取虚拟手两种。基于外部设备驱动的虚拟手如文献[1]中的数据手套模式和文献[2]中的Kinect模式，其主要利用外部设备采集人手姿态信息，然后将人手动作实时映射到虚拟维修环境中的虚拟手，驱动其完成相应的维修操作。这种模式能使受训者很好地掌握实际维修时的操作动作，但是其成本高，需要配置虚拟现实头盔或者立体眼镜，易产生疲劳，操作负荷繁重[3,4]，不适用于满足多人培训的二维MTD。对于自抓取虚拟手，文献[5]中作者基于Kamper 等人[6]对抓取过程中指尖轨迹的研究结论，提出了基于轨迹线的自抓取虚拟手，但其需要提前利用外部设备采集真实人手抓取物体的指尖数据，才能完成抓取轨迹线的绘制，不利于维修动作的扩展和细化。文献[7]中作者通过3D鼠标驱动虚拟手，构造了一种虚拟手的交互行为，但是其在物体周围设置包围盒感知区的交互方式不适合复杂且需要精细操作的场景，易造成交互命中率低的问题，控制过程较为繁琐。

针对上述问题，结合在VA中需要大场景漫游、多场景切换、设备复杂繁多、且不同设备之间间隔空间有限、对于线路排故需要精确操作等特点，文中采用基于蒙皮骨骼的虚拟手建模方法，构建一种新的虚拟手交互方式，依旧采取鼠标作为物体拾取工具，实现了在不增加操作负荷和外围设备的同时，向受训者展现了具体的维修操作动作。

# 1 自抓取虚拟手的交互流程

图1为自抓取虚拟手的交互流程。在场景漫游阶段，用户通过鼠标和键盘控制漫游，接近需要交互的虚拟物体，此时虚拟手会实时获取视角矩阵，根据视角矩阵调整自身位置进行视角的跟随，实现漫游阶段的虚拟手位置自适应调节；在交互阶段，当待交互虚拟物体处于视角合适范围内时，用户通过鼠标命中虚拟物体，并发出事件命令，此时虚拟物体的位置姿态信息和其抓取动作手势属性会传递给虚拟手，虚拟手会进行自身位置的调整与调取骨骼动画库，实现其在不同交互状态机之间进行转换，完成相应的抓取和释放等任务。而用户可根据实时视觉反馈信息调整虚拟手的交互状态，进行返回或继续下一步任务。通过以上工作流程，可以实现在不增加操作负荷和减少交互命中率的情况下，向受训者展示出维修过程中的具体操作动作。

![](images/1bb0f7f1d7a8b34f3eba51e6929ca710f505f73866f589c35f71e926ed78af91.jpg)  
图1虚拟手交互流程

# 2 虚拟手动作库建模

# 2.1手势动作库的定义

动作手势库是实现自抓取虚拟手的基础，手势库的定义与具体的维修对象与维修任务有关，定义得过少不能有效真实地完成操作任务；定义过多则会产生冗余，造成系统资源浪费。根据吉尔布雷斯动素分类，以实验室自主研发的空客A320飞机维修综合训练器（HDMTD-2）为例，其3D外场维修仿真已开发的维修训练项目中涉及到的基础操作手势可主要分为如图2 所示七种。其相关定义如下。

基础手势：

a）释放 $G _ { b a s e }$ 。五指伸直张开，用于释放物体，工具等。b）普通握 $G _ { 1 }$ 。四指并拢弯曲，用于握手柄、扳手、保护盖、工具等。c）铆接握 $G _ { 2 }$ 。拇指与食指张开呈握状，其余三指弯曲紧握，用于铆接不同物体、线、管等。d)按压 $G _ { 3 }$ 。食指伸直，大拇指靠近食指弯曲，其余三指弯曲紧握，用于按压跳开关、按钮等。e）捏 $G _ { 4 }$ 。食指与拇指伸直呈夹取状，用于拿螺钉、螺帽等小物件。f)抓 $G _ { 5 }$ 。五指张开弯曲，用于抓取圆形保护堵盖等较大零件、物件。g）拧 $G _ { 6 }$ 。拇指稍张开，其余食指紧握，拇指与食指之间留一定间隔，用于拧动开关、旋钮等。

在基础手势的基础上继续根据具体的维修对象定义最终的抓稳手势 $G _ { i j }$ （其中 $i = 1 , 2 , . . . , 6 ; j = 1 , 2 , 3 , . . . n$ ， $i$ 为基础手势编号，$j$ 为对应基础手势 $i$ 的最终抓稳手势编号)。每个基础手势与其对应的一系列最终抓稳手势手型是一样的，只是在抓取深度上有区别，基础手势 $G _ { b a s e }$ 、 $G _ { i }$ （ $i = 1 , 2 , . . . , 6$ ）与最终抓稳手势 $G _ { i j }$ 一起构成手势动作库与动画关键帧。

YIYYYY $G _ { b a s e }$ G1 G G G4 G5 G6

# 2.2骨骼动画手势动作库构建

逼真的虚拟手在增加训练效果方面具有更好的表现[8]，不同的维修任务所要求的手势动作不同，即使是针对同一维修任务，也有可能存在手势动作库需要扩展或更新的现象。因此从虚拟手的几何逼真性以及手势动作库的易实现性、动态扩展性三个方面考虑，采用3DMAX进行虚拟手建模与构建骨骼动画，并采用图3所示的动作库构建流程。

![](images/fcf1cf912a5d25efc7af16d6736f0942f8baa7ed66c3f7ffe3ca1bab7eb26cf1.jpg)  
图2定义基础手势  
图3动作库构建流程

动作库构建流程主要分为三维骨骼动画构建和模型数据转换与导出过程。首先在3DMAX中进行虚拟手网格模型的绘制与平滑操作，并为其进行纹理贴图，提高虚拟手的几何真实感;然后为虚拟手创建骨骼和添加蒙皮，并对两者进行绑定，调整骨骼对蒙皮的影响权重，根据定义的手势动作进行手势骨骼动画的制作；最后利用Cal3DExp进行骨骼动画数据的转换，并依次导出骨骼文件（.csf)、网格文件（.cmf)、纹理文件（.xrf)和动画文件（.caf)，在导出上述数据文件后，建立动作库文本配置文件（.cfg）记录骨骼动画信息，供OSG环境加载调用。图4中，从左到右依次为3DMAX中建立的原始虚拟手网格模型、平滑后的虚拟手网格模型和最后进行纹理贴图且绑定骨骼蒙皮之后的虚拟手模型。从图4可看出，文中构建的虚拟手模型其几何真实感强。

H Ww

# 3 虚拟手交互行为算法实现

# 3.1位置匹配过程的实现

位置匹配过程通过调整虚拟手位置与方向，使其姿态轴能与虚拟物体的姿态轴完成匹配，使虚拟手处于能正确抓取虚拟物体的位置， $G _ { b a s e } \to G _ { i }$ 也在此阶段完成。如图5所示，以虚拟手抓取螺丝的过程为例，讨论位置匹配过程的实现。

由于手指与手指、指段与指段之间存在互相牵连的矩阵约束关系，所以一个固定手势动作 $G _ { i }$ 的手型信息可以用五指中其中一指的远指段的方位信息体现出来，同样整个虚拟手的位置与方位信息也可以用五指中其中一指的远指段位置与方位信息体现出来。以图5为例，图中拇指远指端 $c$ 的位置与方位信息$P _ { c }$ 与整个虚拟手的位置与方位信息 $P _ { D }$ ，可以用食指远指端 $B$ 的位置与方位信息 $P _ { { _ B } }$ 通过方位矩阵变换得到，即满足下列等式：

$$
\left\{ \begin{array} { l l } { P _ { c } = P _ { \scriptscriptstyle B } \bullet M A T _ { c } } \\ { P _ { \scriptscriptstyle D } = P _ { \scriptscriptstyle B } \bullet M A T _ { \scriptscriptstyle D } } \end{array} \right.
$$

其中： $M A T _ { c }$ 和 $M A T _ { D }$ 为 $4 \times 4$ 的方位变换矩阵，在虚拟手的骨骼动画制作阶段，可以利用3DMAX提供的位置与姿态信息计算得到。由于当前定义手势动作中，任何的维修操作都有食指的参与，所以以食指远指端作为姿态轴匹配基准。

在XML文本中记录的关于图4中螺丝的部分信息如下：

Ⅱ <hotzone> <type>3</type> <obj_name>SDAC1_right_screw</obj_name> <sub-system>Elec824_System</sub-system> <prop> Device/PosSDAC1_right_screw/Elec824_System/SDAC1_right_screw </prop> <id>803</id> <notify>false</notify> </hotzone>   
日 <animation> <type>rotate</type> <center> <x>-393.891</x> <y>323.872</y> <z>339.293</z> </center> <match_prop>G4</match_prop> <match_axis> <x>0.00</x> <y>0.00</y> <z>0.00</z> </match_axis> n

对于图5中的抓取过程，螺丝为可操作的热区物体，类型为3（视觉反馈方式为小手)，拾取ID为803,维修运动属性为旋转，其初始位置为 $( - 3 9 3 . 8 9 1 , 3 2 3 . 8 7 2 , 3 3 9 . 2 9 3 )$ ，基础抓取手势属性为捏，虚拟手与螺丝的匹配特征为虚拟手 $G _ { 4 }$ 的食指远指端B 应与螺丝A处于 $\ x , \ y , \ z$ 轴共线同向。在鼠标拾取螺丝后发出抓取命令，虚拟手将获取螺丝A的位置与方位信息，根据A的位置与方位信息和匹配特征属性，可求得处于 $G _ { 4 }$ 状态的虚拟手的食指远指段 $B ^ { \prime }$ 应处的位置和方位信息，根据式（1）便可计算出虚拟手需要变换到的位置与方位 $D ^ { \prime }$ 。根据 $D ^ { \prime }$ 的矩阵信息，在虚拟环境OSG中进行矩阵的平移与旋转运算，实现虚拟手从 $D$ 到 $D ^ { \prime }$ 的位置与方位变换，完成虚拟手与交互对象的位置匹配过程。

![](images/cbecb09dd65a1fc6132655b0ff2638d817c66e4b32bbe4aa98daea5f17164d71.jpg)  
图4虚拟手模型  
图5虚拟手抓取螺丝

# 3.23.2虚拟手交互行为状态机模型

图6为虚拟手交互状态机模型，其初始状态为 $G _ { b a s e }$ 。虚拟手根据交互状态的不同，手势状态分为三种： $G _ { b a s e }$ 表示开始抓取虚拟物体前的状态，即手势动作库中定义的释放手势，在

3DMAX中该手势为骨骼动画 $G _ { b a s e }  G _ { i }$ 变换的初始帧，在操作者通过键盘进行场景漫游时，该手势一直跟随视角矩阵，保持其相对视角位置不变； $G _ { i }$ 表示初步抓取状态，其中 $i = 1 , 2 , . . . , 6$ ，代表基础手势动作库中除 $G _ { b a s e }$ 外的其他六种手势，在3DMAX中，该手势作为虚拟手

由 $G _ { b a s e }$ 状态变换到初步抓取状态 $G _ { i }$ 的结束帧，同时作为由$G _ { i }$ 到最终抓稳状态 $G _ { i j }$ 的开始帧； $G _ { i j }$ 表示状态 $G _ { i }$ 对应的最终抓稳手势状态，其中 $i = 1 , 2 , . . . , 6$ ， $j = 1 , 2 , 3 , . . . , \mathrm { ~ n ~ }$ ，因为同一基础手势可以根据抓取对象直径和分类的不同有多种最终抓稳手势，$j$ 取值范围可以根据需要进行扩展，在3DMAX中，该手势是作为 $G _ { i }$ 到 $G _ { i j }$ 变换的结束帧。

$G _ { b a s e }  G _ { i }$ 的转换条件为鼠标发出拾取虚拟物体的命令，$G _ { i }  G _ { i j }$ 转换条件为鼠标发出抓取命令； $G _ { i j } \to G _ { i }$ 的转换条件为键盘R或者 $\mathrm { ~  ~ { ~ r ~ } ~ }$ 键按下，且虚拟物体处于可以放置的正确位置，$G _ { i }  G _ { b a s e }$ 转换条件为键盘B或者b键按下。

其具体抓取虚拟物体过程为：用户操作鼠标和键盘进行场景漫游，靠近虚拟物体，当鼠标触到可用虚拟手操作的物体时鼠标会变成小手状，以提供视觉反馈。此时用户在虚拟物体上按下鼠标右键，弹出右键菜单，若用户选择pick命令，且当前状态机处于 $G _ { b a s e }$ ，则虚拟手获取虚拟物体的姿态轴矩阵数值和虚拟物体的基础抓取手势属性；然后根据获取的信息，完成位置匹配，同时调取osgcal动画，完成手势从 $G _ { b a s e } \to G _ { i }$ 变换，实现初步抓取虚拟物体，并标志虚拟手状态为 $G _ { i }$ 。若用户继续按下鼠标右键，选取grasp 命令，且当前状态机处于 $G _ { i }$ ，则调取osgcal动画，完成手势从 $G _ { i }$ 到 $G _ { i j }$ 变换。通过 $G _ { b a s e }  G _ { i }  G _ { i j }$ 的状态机转换，实现虚拟手对物体的抓稳操作。

算法1自抓取虚拟手交互行为算法 输入：虚拟手参数，手势动作库，基于层次约束结构的A320外场维修模型， 鼠标，键盘发出事件命令 输出：抓稳或者释放物体，完成交互任务 1:Initialize:State_machine $$ Flag_Gbase 2:function1(Grasp_object)//抓取虚拟物体 3: ifmouse_right_click_hot_objectthen//鼠标右键点击热区物体，弹 出右键菜单 4: ifselect_pick&&State_machine $\mathbf { \Sigma } = \mathbf { \Sigma }$ Flag_Gbasethen//选择拾 取，状态机为Gbase 5: Object_position $$ Get_object_position()//物体位置 6: Gesture $$ Get_object_base_gesture()//物体初步抓取手势 7： Adjust_hand_position(Object_positon)//位置匹配 8: Change_Gbase_to_Gi(Gesture)//调取osgCal动画，状态机转 到Gi,初步抓取 9: State_machine $$ Flag-Gi//标志状态机状态为Gi 10: else 11: ifselect_grasp&&State_machine $\ c =$ Flag_Githen//选择拾 取，状态机为Gi 12: Gesture $$ Get_object_final_gesture()//物体抓稳手势 13: Change_Gi_to_Gij(Gesture)//调取osgCal动画,状态机 转到Gij，抓稳 14: Maintain_stage $\gets$ Get_action_stage()//维修动作步骤 5: while Maintain_stage not enddo//维修未结束 6: Hand_action(Maintain_stage)//调整虚拟手动作 7: Maintain_stage++//下一维修步骤 8: end while 9: State_machine $$ Flag-Gij//标志状态机状态为Gij 0: end if 1: end if 2: end if 3:end functionl

![](images/a2a15b3790d23b51c456d8681d3a4f49b11dda6052db4c2879fb0ca2d2bdc494.jpg)  
图6虚拟手交互状态机模型

其释放虚拟物体的过程为：当前状态机处于 $G _ { i j }$ ，键盘B或者b 键按下，则调取osgCal动画，完成手势从 $G _ { i j } \to G _ { i }$ 的状态转换，实现初步释放虚拟物体。若当前状态机处于 $G _ { i }$ ，继续按下键盘R或者 $\mathrm { ~  ~ { ~ r ~ } ~ }$ 键，则调取osgCal动画，完成手势从 $G _ { i } \to G _ { b a s e }$ 的状态转换，并调整虚拟手到漫游状态，通过 $G _ { i j } \to G _ { i } \to G _ { \mathrm { b a s e } }$ 的逆向变换，实现完全释放物体。

其释放过程的伪代码算法描述如下：

25:tunction2(Discharge_object)//栓放虚拟物体   
26: ifKey_b_down&&State_machine $\mathbf { \Sigma } = \mathbf { \Sigma }$ Flag_Gijthen//键盘b或 者B键按下，状态机为Gij   
27: Gesture $$ Get_current_gesture()//获取当前手势   
28: Change_Gij_to_Gi(Gesture)//调取osgCal动画,状态从Gbase转 到Gi，初步松开物体   
29: State_machine $$ Flag-Gi//标志状态机状态为Gi   
30: else   
31： ifKeyr_down&&State_machine $\mathbf { \Sigma } = \mathbf { \Sigma }$ Flag_Githen//键盘r或 者R键按下，状态机为Gi   
32: Change_Gi_to_Gbase()//调取osgCal动画，状态机从Gi转 到Gbase，释放结束   
33: State_machine $$ Flag-Gbase//标志状态机状态为Gbase   
34: Adjust_hand-position(Camera_positon)//调整虚拟手位 置，返回漫游状态   
35: endif   
36: endif   
37:end function2

# 4 实验结果与分析

实验在实验室自主研发的空客320飞机维修综合训练器（HDMTD-2）的外场3D虚拟飞机维修环境中进行。3DMAX版本为 2013X64，三维引擎为 OSG(OpenSceneGraph-3.0),PROE 版本为5.0，cal3d版本为0.11.0，osgcal版本为0.3.1,编程平台为Windows7X64下VS2012。图7所示为本文构建的虚拟手完成备用刹车储压器（2624GM)的补充油量的部分任务。图7(a)中，虚拟手跟随相机视角，在A320外场3D维修仿真第一场景中漫游；图7(b)中，虚拟手进入第二场景，靠近FILLINGEQUIPMENT-BRAKERESERVOIR。当鼠标触到可进行交互操作的热区物体手摇棒时，鼠标变成小手，提供视觉反馈，如图7(b)所示；鼠标在手摇棒上右击，弹出右键菜单，选择Pick 命令，如图7(c)所示；虚拟手通过位置匹配与osgCal骨骼动画调取，进行 $G _ { b a s e }  G _ { i }$ 变换，完成初步抓稳操作，如图7(d)所示;鼠标继续右击，发出 grasp 命令，虚拟手进行 $G _ { i }  G _ { i j }$ 变换，抓稳手摇棒，如图7(e)所示；图7(f)中，虚拟手根据获取的action_stage压下手摇棒，执行维修操作。

![](images/5f46bdcffdb5189cc5127e266192f76ccfc5d314fc8abf74f4252a03e13fd9fc.jpg)  
图7虚拟手握手摇棒

为评价文中方法的有效性，引入传统的MTD机务培训系统进行了对比实验。实验受试者为正在进行CCAR147（民用航空器维修培训机构合格审定规定）技能培训的大四学生，他们对飞机维修实操过程都具有一定认知，在大二阶段都有在MTD上进行理论学习和实践培训的课程。学生共40名，分成A、B两组，每组20人。A、B两组交替在传统VA和文中改进的VA中完成同样的虚拟维修训练项目，两组使用的电脑配置一致。为增加对比实验的可信度，评价分为客观指标（表1）和主观评价（表2）两部分。对于主观评价部分，在对比实验进行之前除了对受试者进行系统操作培训外，不说明实验目的，实验结束后填写体验调查问卷，问卷指标内容如表2所示，每个指标满分10分。

表1两种VA客观指标结果  

<html><body><table><tr><td rowspan="2">对象</td><td colspan="3">指标</td></tr><tr><td>交互设备</td><td>实时帧数均值/fbps</td><td>训练时间均值/min</td></tr><tr><td>传统VA</td><td>鼠标、键盘</td><td>54</td><td>26.8</td></tr><tr><td>改进VA</td><td>鼠标、键盘</td><td>54</td><td>27.2</td></tr></table></body></html>

表2两种VA主观评价结果  

<html><body><table><tr><td rowspan="2">对象</td><td rowspan="2">指标</td><td rowspan="2">维修动作可 理解性</td><td rowspan="2">操作复杂</td><td rowspan="2">与实操相 似性</td><td rowspan="2">总体训练 效果</td></tr><tr><td>度</td></tr><tr><td>传统</td><td>均值</td><td>6.83</td><td>3.25</td><td>7.15</td><td>7.42</td></tr><tr><td>VA</td><td>标准差</td><td>0.68</td><td>1.02</td><td>0.88</td><td>0.75</td></tr><tr><td>改进</td><td>均值</td><td>8.82</td><td>3.27</td><td>7.93</td><td>8.67</td></tr><tr><td>VA</td><td>标准差</td><td>0.67</td><td>1.12</td><td>0.92</td><td>0.82</td></tr></table></body></html>

从表1的客观指标结果可以看出，构建自抓取虚拟手的VA系统，没有增加额外的交互设备，同时系统运行流畅度和完成一个训练项目的平均时间与传统VA一致。从表2的主观评价结果可以看出，改进的VA系统在基本没有增加操作复杂度的前提下，使得训练者更容易直观地理解具体的维修操作手势，而且其与实操的相似性感受也有一定提升，总体的训练效果较传统VA有较大的提高。

# 5 结束语

让受训者认知具体维修动作对于提高实践能力具有必要性，而当前的MTD 机务培训系统缺少这一功能，本文在不增加外围设备和操作负荷的前提下，对这一功能进行了应用开发。经实验证明，文中提出的方法能较好地向受训者展示具体的维修操作，相对于传统的VA系统，其对虚拟维修训练具有更好可用性。同时由于文中构建的虚拟手其手掌与指段部分依旧是刚体模型，尚无法实现虚拟手皮肤与物体的紧密熨帖，所以严格意义上的抓稳还需进一步研究与提高，此外由于当前虚拟手动作库中骨骼动画数量有限，其维修操作演示还较为生硬，后期可通过扩展虚拟手动作库，对维修动作进行细化来改善这一状况。

# 参考文献：

[1]Liao J,Zhao G, Tan D,et al. Real-time virtual hand controling using OpenSceneGraph[C]//Proc of IEEE International Conference on System Science,Engineering Design and Manufacturing Informatization.2012: 264-268.   
[2]汤志波，张志利，梁丰，等．虚拟维修训练中的手势识别[J].计算机 工程与设计，2014,35(12):4278-4283.   
[3]周忠，周颐，肖江剑．虚拟现实增强技术综述[J].中国科学：信息科 学,2015,45 (2):157-180.   
[4]高源，刘越，程德文，等．头盔显示器发展综述[J].计算机辅助设计 与图形学学报,2016,28(6):896-904.   
[5]陈文锋．灵巧虚拟手自然交互研究[D].杭州：浙江大学,2014.   
[6]KamperDG,Cruz E G, Siegel MP.Stereotypical fingertip trajectories during grasp [J]. Journal of Neurophysiology,2003,90 (6): 3702-3710.   
[7]蔡娴娟，程成,MarwahA，等．虚拟制造环境中虚拟手的行为构造[J]. 计算机辅助设计与图形学学报,2015,27(3):499-507.   
[8]Aslandere T,Dreyer D,Pankratz F.Virtual hand-button interaction in a generic virtual reality flight simulator $[ \mathrm { C } ] / \hbar$ Proc of IEEE Aerospace Conference.2015:1-8.   
[9]Xia PJ,Lopes AM,Restivo M T, et al.A new type haptics-based virtual environment system for assembly training of complex products [J]. International Journal of Advanced Manufacturing Technology,2012,58(1- 4): 379-396.   
[10] Liu X, Cui X, Song G,et al. Development of a virtual maintenance system with virtual hand [J]. International Journal of Advanced Manufacturing Technology,2014,70 (9-12): 2241-2247.   
[11] Lu G,Shark L K,Hall G,et al. Dynamic hand gesture tracking and recognition for real-time immersive virtual object manipulation [C]// Proc of International Conference on Cyberworlds.[S.1.]:IEEE Computer Society,2009:29-35.   
[12] LiJR,Xu YH,NiJL,etal. Glove-based virtual hand grasping for virtual mechanical assembly [J].Assembly Automation,2016,36 (4): 349-361.   
[13]高伟，郭瑾．基于双重模型的计算机手语动作的实现方法[J].计算机 应用研究,2007,24(11):315-317,320.   
[14] Kumar V, Todorov E.MuJoCo HAPTIX: a virtual reality system for hand manipulation [C]// Proc of IEEE-RAS,International Conferenceon Humanoid Robots.2015: 657-663.   
[15] KimJS,Park JM.Physics-based hand interaction with virtual objects [C]/ Proc of IEEE International Conference on Robotics and Automation.2015: 3814-3819.   
[16]胡晨，张学聃，马惠敏．适应物体形状的虚拟手抓取[J].中国图象图 形学报,2017,22(5):663-670.   
[17]杨晓文，张志纯，况立群，等．基于虚拟手的人机交互关键技术[J]. 计算机应用,2015,35(10):2945-2949.   
[18]李懿，罗建勋，陈卫东，等．基于蒙皮骨骼的虚拟手交互碰撞模拟方法 [J]．浙江大学学报：工学版,2014,48(1):105-112.   
[19]胡弘，晁建刚，林万洪，等．基于虚拟手交互的航天员虚拟装配训练仿 真方法[J].计算机应用,2015,35(s2):200-203.   
[20]顾岩，何其昌，范秀敏，等．狭小空间虚拟人手臂装配运动规划及智能 寻优[J].计算机集成制造系统,2016,22(6):1447-1455.   
[21]刘汝强，黄海明，刘金刚．一种适用的角色控制系统的设计与实现[J]. 计算机应用研究,2009,26(12):4631-4634.   
[22] Sagayam K M, Hemanth D J. Hand posture and gesture recognition techniques for virtual reality applications: a survey[J]. Virtual Reality,2016, 21 (2): 1-17.   
[23] Chen N,Li W W,Nie L X,et al.Research on the simulation technology of virtual hand interventional manipulation in the virtual environment [J]. Applied Mechanics & Materials,2014, 665: 698-705.   
[24] Tang Y, Yang B,Gu H. Creating a realistic virtual hand for head-mounted displays [J].Electronics World,2013,119 (1925): 36-39.   
[25] Chen WF,Zhu SJ,Wan HG,et al. Dual quaternion based virtual hand interaction modeling[J].Science China Infor-mation Sciences,2013,56 (3): 1-11.   
[26] Wang KR,Xiao Bingjia,XiaJY,etal.Areal-time vision-based hand gesture interaction system for virtual EAST[J].Fusion Engineering& Design,2016, 112: 829-834.   
[27]熊巍，王清辉，李静蓉．面向虚拟装配的层次化交互手势技术[J]．华 南理工大学学报：自然科学版,2016,44(1):78-84.   
[28] Lin W,Du L,Harris-Adamson C,et al.Design of hand gestures for manipulating objects in virtual reality[C]//Proc of International Conference on Human-Computer Interaction. Cham: Springer,2017: 584-592.   
[29] Hirota K, Tagawa K. Interaction with virtual object using deformable hand [C]//Proc of IEEE Virtual Reality.2016: 49-56.   
[30]黄俊，景红．基于Leap Motion的手势识别在虚拟交互中的研究[J].计 算机应用研究,2017,34(4):1231-1234.