# 一种用于纳型卫星在轨分离释放装置的设计

周伟}²,杨 萱,杨华³

(1.中国科学院复杂航天系统电子信息技术重点实验室,中国科学院空间科学与应用研究中心，北京 100190；2.中国科学院大学,北京100049；3.内蒙古电子信息职业技术学院,呼和浩特010011摘要：针对纳型卫星分离载荷的在轨分离释放需求,给出弹簧式分离释放装置的设计方案，解决国际上的商用现货产品不适用于这种非标准质量体积比的纳型卫星的问题.设计的分离释放装置能承载体积6U（1Unit即 $1 ~ \mathrm { d m } ^ { 3 }$ 体积），质量 $1 0 ~ \mathrm { k g }$ 的分离载荷.由设计要求出发,给出包括中心承力构架、分离释放机构和对接环的方案,进行结构模态分析和过载分析.最后给出两两对称分离的在轨分离释放过程.结构设计结果表明该方案能满足一般的运载发射要求.该设计为任务的实施提供了有效可行的解决方案.

关键词：纳型卫星;分离载荷；分离释放装置;结构设计与分析  
中图分类号：V44 文献标志码：A 文章编号：1674-1579（2015)01-0026-05  
DOI:10.3969/j. issn.1674-1579.2015.01.005

# Design of System for Nanosatellite on-Orbit Release and Separation

ZHOU Wei1'²，YANG Xuan’， YANG Hua³ (1.Key Laboratory of Electronics and Information Technology for Space Systems, NSSC，CAS，Beijing 100190，China ; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China ; 3.Inner Mongolia Electronic Information Technical College，Hohhot Olool1，China）

Abstract:Concerning requirements for the on-orbit release and separation of nanosatellite-fractionated payloads，a design of the spring-loaded separation system is presented.It is aimed at the problem that the international commercial-off-the-shelf products are inadaptable for the nonstandard ratio of weight and volume. The separation system is able to support 6 U( $1 \ \mathrm { u n i t } \ = \ 1 \ \mathrm { d m } ^ { 3 }$ volume）and $1 0 ~ \mathrm { k g }$ payload. Taking into account the design constraints，the plan consists of the central bearing frame,separation mechanisms and the docking ring.Modal and acceleration loading analyses are carried out.Accordingly the on-orbit simultaneous separation process of two opposite ones is presented.Analyses results show that the structural design meets the requirement for launching.The designed plan serves as an effective and applicable solution for the mission.

Keywords: nanosatelite；fractionated payloads；separation system； structural design and analysis

# 0 引言

动.为了实现空间物理场的多点时空协同探测，使用多颗有效载荷配置相同的纳型卫星，利用商业化的立方星和纳星技术，形成分离载荷的卫星星座.这种分布式组网探测方式将达到成本更低、布局更灵活、风险更小的目标.分离载荷的分离释放过程直接影响了

地球空间环境特性的探测和研究一直被给予高度重视，多个国家已计划和开展了空间科学探测活分离后的构型演化，更存在卫星碰撞风险.因此精确在轨释放分离是实现卫星组网探测的关键技术之一.

分离释放装置用于主控载荷(主星)释放分离多颗分离载荷（子星），是两者之间的机械接口.分离释放装置在发射和飞行初期阶段能将分离载荷安全可靠地锁紧，可受控随时释放出分离载荷，分离速度能达到一定的大小.分离释放的速度和方向对编队飞行的卫星的姿态和轨道构型的控制有着重要的影响，

随着立方星和纳星编队探测计划增多，国际上众多科研和工商业部门研制了多种型号的分离释放装置商用现货产品，采用搭载方式发射这些卫星.目前已取得了多次的成功飞行应用经验，形成了一些通用的设计标准".国际上应用较成功的分离释放装置主要有美国的P-POD、加拿大的X-POD、荷兰的 ISIPOD[1-3],此外还有美国的 NPSCuL、德国的SPL、日本的T-POD、J-POD 和CSS 等.它们均采用较简单的弹簧分离方式.

但是国际上的这些分离释放装置几乎都按照星体1U体积（1Unit即 $1 ~ \mathrm { d m } ^ { 3 }$ 体积)为 $1 ~ \mathrm { k g }$ 质量的标准来设计，若卫星的体积和质量不满足标准值则不能直接采用该产品.即使对于承载能力范围较大的X-POD 装置[2],为保证装置结构的基频达到 $1 0 0 ~ \mathrm { H z }$ ，其8U型号额定承载 $7 . 5 ~ \mathrm { k g }$ ,最大的 $1 6 \mathrm { ~ U ~ }$ 型号额定承载 $1 4 ~ \mathrm { k g }$ ,承载能力有限.其次，这些产品均作为运载火箭上的结构，并不与主星一起飞行.为确保安全，多数的分离释放装置结构冗余较大，装置过重，难以满足主控载荷卫星结构对部件的重量要求.

在国内除了少数的单颗微小卫星在轨释放伴飞的应用4，对专用的分离释放装置还未有公开的研究及飞行应用.

为了解决国际上的分离释放装置商用现货产品不适用于这种非标准质量体积比的纳型卫星的问题,按照分离载荷任务要求，对国际上相应的产品进行改进设计，对结构承载能力进行了分析，以实现弹簧动作在轨释放分离纳型卫星的具体应用.给出的分离释放过程也可满足卫星的轨道姿态控制需求.

# 1设计要求与子星布局、搭载形式

# 1.1 设计要求

分离释放装置的主要设计要求有： $\textcircled{1}$ 根据探测科学目标，为实现四面体编队且具有冗余，主控载荷需分离释放4颗分离载荷； $\textcircled{2}$ 能承载 $6 ~ \mathrm { U }$ 体积，最大质量 $1 0 ~ \mathrm { k g }$ 的分离载荷； $\textcircled{3}$ 可靠地锁紧与释放分离，满足分离速度要求； $\textcircled{4}$ 为满足轨道构型设计，分离载荷需两两对称分离，且分离方向与主控载荷飞行方向共线； $\textcircled{5}$ 满足运载发射的力学环境条件，具有足够的强度与刚度.

# 1.2子星布局与搭载形式

作为子星的分离载荷与作为主星的主控载荷的布局关系需考虑分离释放后的轨道和姿态控制要求.发射的搭载方式也需考虑.

参考美国LockheedMartin公司的EELV运载火箭为搭载子星设计的ESPA（EELV secondarypayloadadaptor)结构,如图1(a)所示[5],多颗搭载子星沿圆周分布在主星周围.因此，4个分离载荷可由分离释放装置夹紧分布在主控载荷的4个面上.这样可以实现分离载荷的两两对称分离释放，对主控载荷的飞行姿态扰动较小，且分离方向可由主控载荷的姿态控制来决定.

![](images/13bb70b7481e24acec843367be7c6d85ac4e1b24edb86460b2408f1ea73f74bc.jpg)  
图1子星搭载布局形式  
Fig.1Secondary payloads piggyback structural configuration

日本JAXA的Akatsuki卫星任务搭载了多颗CubeSat卫星和小卫星.其中一颗小卫星IKAROS灵活地放置在主星Akatsuki的适配器结构内部，如图1(b)所示[6].在主星星箭分离以后，适配器抛掉，IKAROS被分离.由于主控载荷应携带4个分离载荷作为集合体从运载火箭上分离，该集合体搭载在主星适配器内部的方式较优.适配器内部可提供足够大的空间，同时该搭载方式不会对主星任务产生任何影响，安全性较高.

# 2 结构总体设计与分析

# 2.1 结构总体设计

分离载荷的分离释放装置由中心承力构架、4个分离释放机构和对接环组成，如图2所示.4个分离释放机构分布在中心构架的4个面上.中心构架的底部采用对接环包带连接以实现与运载火箭分离.中心构架与主控载荷之间也采用对接环连接.在完成分离载荷的释放分离后，主控载荷可以抛离分离释放装置以减重.

分离释放机构由滑轨、托盘、分离弹簧以及夹紧释放机构组成，如图3（a)所示.分离载荷与滑轨滑动摩擦接触，由压缩弹簧提供分离力使其分离出去，如图3(b)所示.在初始状态下，分离载荷被夹紧释放机构上的钢制带齿长销所锁定，如图3（c）所示.夹紧释放机构由控制电机驱动，通过带齿转盘转动角度的控制，可依次实现开门和拔出销钉的动作，从而释放被锁定的分离载荷.

![](images/a376a327efbcfda70686a2b28774a9646472ab43e52984f78ae0686e026ffcab.jpg)  
Fig.2 Overall structure of a separation system

![](images/fbe8a9f70fafe6314a59140bc17fcfd42a56a7d42a83cb5270ad9a77971951f4.jpg)  
图2分离释放装置总体结构  
图3分离释放机构与夹紧释放机构  
Fig.3Separation mechanism structure and hold-down and release mechanism

在发射阶段装置需承载较大的惯性载荷，故在承力方向的底板上布置了三角斜支撑结构.分离释放机构的门的设计用以保证装置的结构完整性，避免过大的变形.为避免装置的结构与星体上的可展开结构（如折叠伸杆结构）相干涉，在保证结构基频足够高的前提下，在装置结构上开出相应的孔.

如图3（b)所示，在发射前，分离载荷被装载在分离释放装置中，被夹紧释放机构锁定.到达预定轨道后，夹紧释放机构动作解锁.在分离弹簧作用下分离载荷被推出，实现与主控载荷的分离.

# 2.2 结构分析

使用有限元分析软件对装置结构进行模态分析与过载分析.建立分析模型，如图4所示.模型均由四面体单元Tet10建立.主控载荷、分离载荷和弹簧均分为多个点质量单元.边界条件为对接环下法兰表面所有节点的6个自由度全部限定.

![](images/40093481a0d2ead9a049421c374d633a7c7e5ae5d58c7ee44c96c6bc6cfad434.jpg)  
图4结构分析有限元模型

在发射过程中，根据卫星搭载所处的位置不同，其力学环境不同.模态分析可以检验结构在发射阶段能否满足整星对其基频要求.分离释放装置作为卫星的一个部件，要求其基频应高于整星的基频，避免结构共振.结构材料考虑采用铝合金.在额定的主控载荷 $5 0 ~ \mathrm { k g }$ 、每个分离载荷 $1 0 ~ \mathrm { k g }$ 以及每个分离弹簧 $1 \ \mathrm { k g }$ 的载荷作用下，结构模态分析结果显示，分离释放装置的第一阶自然频率接近 $1 0 0 ~ \mathrm { H z }$ ，能满足一般的运载发射要求.表1给出了各阶的频率和振型结果.图5给出了第一阶振型的云图，其频率为$9 8 . 4 ~ \mathrm { H z }$

表1模态分析结果  

<html><body><table><tr><td>阶数</td><td>自然频率/Hz</td><td>振型描述</td></tr><tr><td>1</td><td>98.4</td><td>整体横向扭动一阶</td></tr><tr><td>2</td><td>100.5</td><td>整体横向振动一阶</td></tr><tr><td>3</td><td>100.5</td><td>整体横向振动一阶另一方向</td></tr><tr><td>4</td><td>107.6</td><td>分离装置纵向振动一阶</td></tr><tr><td>5</td><td>112.9</td><td>分离装置纵向振动二阶</td></tr><tr><td>6</td><td>118.7</td><td>分离装置纵向振动二阶另一方向</td></tr></table></body></html>

过载分析检验了结构在较高的过载加速度作用下的响应.在最恶劣的发射力学环境下，结构产生的应力与应变不能过大.在纵向与横向 $2 0 ~ g$ 过载联合作用下，过载分析的结果显示结构变形较小，最大应力值仅 $8 6 . 5 \ \mathrm { M P a }$ ,远小于铝合金材料LY12CZ的屈服强度值，安全系数达3.06，故结构的强度与刚度能通过运载发射的考验.表2给出了装置结构的应力和变形结果.

![](images/e29feb4ae35b77ee293db9f97f74eea2ede21133e470a5fd3ad88c4164198026.jpg)  
Fig.4Finite element model of structure   
图5分离释放装置模态分析  
Fig.5Modal analysis of a separation system

# 表2过载分析结果

Tab.1 Results of modal analysis   
Tab.2 Acceleration loading analysis results   

<html><body><table><tr><td>分析结果</td><td>数值</td><td>位置</td></tr><tr><td>最大应力/MPa</td><td>86.5</td><td>下底板开孔根部一角</td></tr><tr><td>最大变形/mm</td><td>1. 22</td><td>分离释放装置门一端</td></tr></table></body></html>

# 3分离释放步骤

根据分离载荷与主控载荷的轨道姿态设计方案的要求，分离载荷的在轨分离释放过程如图6所示.其坐标系定义如下： $x$ 轴正向为主控载荷的飞行方向； $z$ 轴正向定义为星体质心指向地心方向；y轴正向与前述定义符合右手螺旋法则.分离释放过程可简述为：主控载荷携带4颗分离载荷搭载发射，在该集合体星箭分离以后，首先分离载荷上的伸杆全部展开，如图6(a)所示.飞行一段时间后，位于主控载荷飞行方向上的两个分离载荷首先同时释放分离，如图6(b)所示.然后主控载荷绕 $z$ 轴旋转 $9 0 ^ { \circ }$ ，将剩下的两个分离载荷转到飞行方向上，如图6（c）所示.两个分离载荷随后同时释放分离，如图6（d)所示.主控载荷上的折叠伸杆解锁展开，如图6（e）所示.最后，主控载荷可抛去分离释放装置，如图6(f)所示，调整姿态继续飞行，完成整个分离释放的

过程.

在分离释放过程中，分离载荷的伸杆能始终指向天顶方向，可提供重力梯度稳定力矩.在滑轨导向作用下，即使分离平面上存在扰动力矩，重力梯度控制模式也能较容易地实现分离载荷的姿态控制.由于分离载荷上资源配置相当有限，该分离释放过程能满足分离载荷不需要调整姿态的目标.主控载荷的姿态机动次数也较少，具有可行性.

![](images/1c6d989dad6c93de0c7e99dce99410d2b2e7a0fdb53fd3756dbd189e802343ec.jpg)  
图6在轨分离释放过程  
Fig.6Process of on-orbit separation

# 4结论

本文对分离载荷的分离释放装置进行了设计和分析，并给出了在轨分离释放的过程.与国内外相关设计相比，本文给出的设计具有以下特点：

紧释放机构.

1)在国际上现有的分离释放装置产品基础上进行改进设计，为非标准质量体积比的立方星和纳型卫星的分离释放任务提供了可行的解决方案；

2)采用弹簧作为分离动作元件，在设计中对分离弹簧力进行计算和仿真，可保证分离速度的精度，有利于分离载荷的准确姿轨控制，

本文的进一步研究旨在采用结构一体化设计来降低结构重量，并采用更简单可靠的方式来设计夹

# 参考文献

[1] ARMEN T.Redesign of the poly picosatellite orbital deployer for the dnepr launch vehicle［D].San Luis Obispo，California：California Polytechnic State University, 2007.

[2］MOHAMED R.Design and implementation of ground support equipment for characterizing the performance of xpod and cnaps $\&$ thermal analysis of CNAPS pressure regulator valve［D］．Toronto，Canada：University of Toronto，2009.

[3]NAKAYAK，KONOUEK，SAWADAH，et al．Tokyo tech cubesat：CUTE-I-design & development of flight

（下转第54页）