# 未知环境下多AUV协同避障方法研究

刘亚1,2.3，曾俊宝1,2†

(1.中国科学院沈阳自动化研究所机器人学国家重点实验室，沈阳110016;2.中国科学院机器人与智能制造创新研究院，沈阳110169;3．中国科学院大学，北京 100049)

摘要：针对多AUV(autonomous underwater vehicle)系统在未知环境中进行路径规划时，难以兼顾避障与编队的问题，提出了一种基于领航-跟随者与行为的多AUV协同避障方法。首先，通过构造碰撞危险度及偏离目标评价函数，设计了AUV局部路径规划方法；在此基础上，结合编队控制方法，分别为领航者和跟随者设计不同的行为以及行为选择模式。半物理仿真实验结果表明，该算法能够实现多 AUV 系统在未知环境中的协同避障，且队形偏离度与恢复队形时间优于传统多机器人避障算法。实验结果证明了该算法的可行性与有效性。

关键词：路径规划；多AUV；协同避障；领航-跟随者；行为 中图分类号：TP242 doi:10.19734/j.issn.1001-3695.2022.03.0115

Research on multi-AUV cooperative obstacle avoidance method in unknown environment

Liu Ya1.2.3, Zeng Junbao1,2† (1.State Key Laboratoryof Robotics,Shenyang InstituteofAutomation,Chinese Academy ofSciences,Shenyang0016, China;2.Institutes for Robotics & Inteligent Manufacturing,Chinese AcademyofSciences,Shenyang 10169,China; 3.University of Chinese Academy of Sciences, Beijing 10o049, China)

Abstract:Aimingat theproblem thatitisdificult totake intoacount bothobstacle avoidanceand formation when multiAUV system plans path inunknown environment,this paper proposed a multi-AUVcooperative obstacle avoidance method basedonleader-followerand behavior.First,this paper designed alocalpath planning method forAUVbyconstructing the evaluation functionofcolisionrisk and deviation fromthetarget;onthisbasis,combined with formationcontrolmethod, this paper designed diffrent behaviorsandbehavior selectionpatterns for leader and followers respectively.The semiphysicalsimulation experiment results show that the algorithmcan realize the cooperative obstacle avoidanceof multi-AUV systeminunknownenvironment,andthformationdeviationandrecoverytimearebetter than traditionalmulti-robotobstacle avoidance algorithms.Experimental results verify the feasibility and effectiveness of the algorithm.

Key words: path planning; multi-auv; cooperative obstacle avoidance; Leader-Follower; behavior

# 0 引言

多机器人系统相较于单机器人而言，具有灵活性好、探索范围广、鲁棒性强等优点，并且能够完成单机器人难以完成的任务。AUV是探索与开发海洋的重要工具，随着对海洋环境研究的不断深入，多AUV系统开始逐渐应用于目标搜探、协同定位等领域。在多机器人系统中，编队控制作为一个重要问题被广泛研究。目前主要的编队控制方法包括领航-跟随者方法[1]、基于行为的方法[2]、人工势场法[3]、虚拟结构法[4]等。

在多机器人系统执行任务的过程中，由于缺少对环境的先验知识，提前规划好的路径上可能会出现障碍物。机器人需要实时规划路径以躲避障碍物，同时还要避免因路线发生改变而与其他机器人碰撞。除此之外，机器人之间的距离不能过远，否则可能会影响机器人之间的通信，甚至在避障结束后无法恢复编队。因此，为了保证机器人的安全以及后续任务的正常执行，机器人之间需要通过相互协作，在躲避障碍物的同时兼顾编队需求。由于系统中的每个机器人受到障碍物位置以及队形的多方面约束，使得多机器人协同避障问题更为困难。

目前，很多学者在编队控制方法的基础上，对多机器人协同避障问题展开了研究。文献[5]在领航-跟随者队形结构的基础上，将编队整体看做刚性结构，通过为领航者进行路径规划以及设置队形转向实现障碍物环境下的编队控制。这种方法虽然将多机器人避障简化为了单机器人的避障问题，但使得领航者路径规划算法的复杂度提高，并且在严格保持队形的情况下，会使得编队整体无法通过狭窄区域；文献[6]中采用了基于行为的编队控制方法，为每个机器人设置驶向目标点、避障、沿墙、避碰以及编队等不同行为，实验证明编队整体能够顺利通过障碍物区域。但每个机器人通过不同行为的加权进行决策，使得队形不易保持；文献[7]采用人工势场法实现了多AUV系统的实时避障，但编队效果不佳；除此之外，部分学者通过将不同的编队控制方法相结合，比如将人工势场法与一致性算法结合[8\~10]，领航-跟随者与人工势场法结合[11,12]，领航-跟随者与基于行为方法结合[13,14]，弥补单一方法的缺陷，提升了多机器人避障的效果。

考虑到障碍物环境的复杂与多样性以及机器人的能耗问题，一般不将多机器人系统看做刚性结构。在这个前提下，由于每个机器人需要同时考虑编队约束以及障碍物约束，多机器人系统难以保持原有队形，需要局部调整位置进行局部队形变换，或者根据障碍物环境选择合适的队形进行整体队形变换。目前对于整体队形变换的研究包括障碍物约束下队形选择方法[15]、队形变换的策略[16,17]。文献[18]中引入障碍物密度的概念，机器人通过感知到的障碍物密度局部调整位置，这种方法使多机器人系统呈现出自适应队形变换的特点，但障碍物密度这一指标实际上难以计算。

基于以上分析，本文将两种编队控制方法相结合，提出一种未知环境下基于领航-跟随者与行为的多AUV协同避障方法。领航者负责队形选择以及规划编队整体前进路线，每台AUV通过行为的选择进行决策，使多AUV系统在避障的同时能够自适应调整队形，并且根据环境的需要变换合适的队形。仿真实验证明了水下不同场景下算法的有效性。

# 1基于前视声纳的AUV局部路径规划方法

机器人的路径规划一般分为环境建模与路径搜索两部分[19]。目前主要的环境建模方法包括栅格法、几何表示法以及拓扑表示法等[20]，本文采用几何学表示的方法。同时，考虑到多边形相较于圆形可拟合的轮廓形状更为广泛，因此采用障碍物轮廓的最小凸多边形进行环境建模。

如图1所示，AUV使用前视声纳对环境进行感知，返回的声纳图像中包含探测到的前方环境信息。实验中采用的前视声纳水平开角为130度，作用距离 $L = 1 0 0 \mathrm { m }$ 。将前视声纳的探测区域平均分成 $N$ 部分，则每部分 ${ S _ { i } } ( i = 1 , 2 , . . . , N )$ 的探测范围为 $[ - \frac { 1 3 } { 3 6 } \pi + \frac { 1 3 \pi ( i - 1 ) } { 1 8 N } , - \frac { 1 3 } { 3 6 } \pi + \frac { 1 3 \pi i } { 1 8 N } ) \ ,$

规定划分的每部分探测区域的中间航向 $\psi _ { i } ( i = 1 , 2 , . . . , N )$ 为此部分的代表航向，通过建立评价函数对 $\psi _ { i }$ 进行评估，以确定AUV下一时刻的航行方向。

![](images/403764640b63fc22c496ab24713d3e719d1f7dac06ed41da595d65bfe6260da9.jpg)  
图1前视声纳模型

当目标点航向上不存在障碍物时，AUV会直接朝着目标点航行；当存在障碍物时，AUV需要改变航向以避免碰撞。某一航向上AUV与障碍物的距离越近，说明沿着该航向航行碰撞危险性越高。因此，评价函数包含两部分：第一部分为与目标点航向的偏离程度，第二部分为与障碍物碰撞的危险程度。

$$
G o a l ( \psi _ { i } ) = 1 8 0 - \big | \psi _ { i } - \psi _ { g o a l } \big |
$$

$$
D i s t ( \psi _ { i } ) = \left\{ \begin{array} { l l } { D _ { i } } & { D _ { i } < D _ { s } } \\ { L } & { D _ { i } \geq D _ { s } } \end{array} \right.
$$

其中 $\psi _ { g o a l }$ 为目标点航向， $D _ { i }$ 为 $\psi _ { i }$ 方向上与障碍物的距离， $D _ { s }$ 为设置的距离阈值。

在计算总评价函数之前，需要对评价函数中的两部分分别进行归一化处理：

$$
G o a l _ { n } ( \psi _ { i } ) = \frac { G o a l ( \psi _ { i } ) } { \displaystyle \sum _ { j = 1 } ^ { N } G o a l ( \psi _ { j } ) }
$$

$$
D i s t _ { n } ( \psi _ { i } ) = \frac { D i s t ( \psi _ { i } ) } { \displaystyle \sum _ { j = 1 } ^ { N } D i s t ( \psi _ { j } ) }
$$

根据下式对待评估航向进行评分，分值最高的航向为当前时刻的决策航向：

$$
E \nu a l u a t e ( \psi _ { i } ) = \alpha \cdot G o a l _ { n } ( \psi _ { i } ) + \beta \cdot D i s t _ { n } ( \psi _ { i } )
$$

# 2 多AUV协同避障方法

# 2.1基于领航-跟随者的编队控制方法

领航-跟随者是一种常见的编队控制方法，主要包括 $\ l - l$ 控制及 $l - \varphi$ 控制[2I]。本文采用 $l - \varphi$ 控制方法，跟随者需要与

领航者保持一定的距离和角度。

AUV的位姿采用 $( x , y , \psi )$ 表示，其中 $( x , y )$ 为AUV在固定坐标系下的坐标， $\psi$ 代表AUV的航向角。

如图2所示，领航者的位姿为 $( x _ { L } , y _ { L } , \psi _ { L } )$ ，根据领航者信息及队形参数可以计算出跟随者的期望位姿：

$$
\begin{array} { r } { \left[ \begin{array} { c } { x _ { i r } ( t ) } \\ { y _ { i r } ( t ) } \\ { \psi _ { i r } ( t ) } \end{array} \right] = \left[ \begin{array} { c } { x _ { L } ( t ) + l _ { i } \cos ( \varphi _ { i } + \psi _ { L } ( t ) ) } \\ { y _ { L } ( t ) + l _ { i } \sin ( \varphi _ { i } + \psi _ { L } ( t ) ) } \\ { \psi _ { L } ( t ) } \end{array} \right] } \end{array}
$$

![](images/0429ed0d8f70e87383d9bb60cb6aadf42d7822845fc54e90d78535a15cb77c31.jpg)  
图2领航-跟随者模型 Fig.2Leader-follower model

# 2.2多AUV协同避障控制架构

如图3所示，本文在领航-跟随者结构的基础上，结合基于行为的编队控制方法，分别为领航者和跟随者设置不同的行为。领航者的目标点为多AUV系统避障最终目标点，跟随者的目标点为满足期望队形的虚拟目标点。每一时刻领航者通过环境感知及避障目标点进行行为选择与决策，规划编队整体前进路线，同时进行队形选择，并将当前位姿与队形参数发送给跟随者；跟随者实时计算虚拟目标点，并结合自身的感知信息进行行为选择与决策。

![](images/91b32958d69564cab09beb5ead0d0d8070eba4fbce1a74700cfa031494e3460e.jpg)  
Fig.1Forward looking sonar model   
领航者  
图3多AUV协同避障控制架构

Fig.3Multi-AUV cooperative obstacle avoidance control architecture

# 2.3领航者行为设置与队形选择

根据提出的多AUV协同避障控制架构，本节分别对领航者的行为设置、行为选择及队形选择方法进行说明。

为保证AUV的平稳运行，规定领航者在避障过程中的速度大小 $u$ 保持不变。为领航者设置驶向目标点以及避障两种行为。设领航者的决策速度为 $\boldsymbol { V } _ { L }$ ，

$$
V _ { L } = \left[ J _ { 1 } \quad J _ { 2 } \right] \stackrel { \left[ V _ { m o v e \_ t o \_ g o a l } \right] } { \left[ V _ { a v o i d \_ o b s t a c l e } \right] }
$$

其中 $\boldsymbol { \jmath }$ 为行为选择矩阵，每一时刻其中的元素只有一个为1，其余为0。 $V _ { m o v e \_ t o \_ g o a l }$ 与 $V _ { a w o i d \_ o b s t a c l e }$ 分别为驶向目标点行为和避障行为的决策速度。

1）驶向目标点行为

驶向目标点行为的决策速度可以表示为

$$
V _ { m o v e \_ t o \_ g o a l } = \frac { u } { \rho ( X , X _ { g } ) } \Bigg [ x _ { g } - x \Bigg ]
$$

其中 $( x _ { g } , y _ { g } )$ 为目标点坐标， $( x , y )$ 为当前位置坐标， $\rho ( X , X _ { g } )$ 为当前位置与目标点的欧式距离。

# 2）避障行为

领航者的避障方法已在本文第1章中详细阐述。为避免在避障过程中跟随者之间发生碰撞，增大领航者与障碍物之间的安全距离 $\boldsymbol { d } _ { L }$ 。设跟随者与障碍物之间的安全距离为 $^ d$ ,跟随者之间允许的最小距离为 $d _ { \operatorname* { m i n } }$ ，则设置

$$
d _ { L } = d + \frac { d _ { \mathrm { m i n } } } { 2 }
$$

避障行为的决策可以表示为

$$
V _ { a v o i d \_ o b s t a c l e } = u { \left[ \begin{array} { l } { \cos \psi } \\ { \sin \psi } \end{array} \right] }
$$

其中 $\psi$ 为局部路径规划方法的决策航向。

# 3）行为选择

领航者行为选择方法如下：

a)判断前视声纳视野内是否存在障碍物，若不存在，执行驶向目标点行为；否则，转向步骤b);

b)计算目标点航向与障碍物的距离 $D$ ，若小于所设定的距离阈值 $D _ { s }$ ，执行避障行为；否则，执行驶向目标点行为。

# 4）队形选择

共设置三角形(原队形)以及一字形两种队形。若领航者的决策航向在当前位置与两障碍物切线之间，认为领航者决定从两障碍物之间通行(图4)，此时计算两个障碍物之间的最近距离 $D _ { \mathrm { m i n } }$ 。若 $D _ { \operatorname* { m i n } } \geq d _ { \operatorname* { m i n } }$ ，选择三角形队形；否则选择一字队形。

![](images/7fe0158b4c6f5a19ee9d667cc41112e29abd6d033ac96189f36e60c96bb0de1c.jpg)  
图4从两障碍物之间通行  
Fig.4Pass through between two obstacles

# 2.4跟随者行为设置与行为选择

根据提出的多AUV协同避障控制架构，跟随者需根据领航者发送的位姿信息、队形参数计算当前时刻的虚拟目标点，并结合感知信息进行行为的选择与决策。因此，本节对跟随者的行为设置及行为选择进行说明。

为跟随者设置四种不同的行为，分别为驶向目标点行为、避障行为、保持行为以及跟随行为。不同于领航者，跟随者具有编队以及队形变换需求，因此在避障过程中速度大小发生改变。设跟随者的决策速度为 $\boldsymbol { V } _ { \boldsymbol { F } }$ ，

$$
V _ { F } = \left[ J _ { 1 } \quad J _ { 2 } \quad J _ { 3 } \quad J _ { 4 } \right] \left[ \begin{array} { c } { { V _ { m o v e \_ t o _ { - } g o a l } } } \\ { { } } \\ { { V _ { a v o i d \_ o b s t a c l e } } } \\ { { } } \\ { { V _ { k e e p } } } \\ { { } } \\ { { } } \end{array} \right]
$$

其中： $_ { J }$ 为行为选择矩阵， $V _ { m o v e \_ t o \_ g o a l }$ ， $V _ { a v o i d \_ o b s t a c l e }$ Vkeep， $\boldsymbol { V } _ { f o l l o w }$ 分别对应四种行为的决策速度。

1）驶向目标点行为

驶向目标点行为的决策可以表示为

$$
V _ { m o v e \_ t o \_ g o a l } = \frac { u + \varepsilon \rho ( X , X _ { \nu g } ) } { \rho ( X , X _ { \nu g } ) } \Bigg [ x _ { \nu g } - x \Bigg ]
$$

其中 $( x _ { \nu g } , y _ { \nu g } )$ 为虚拟目标点坐标， $( x , y )$ 为当前位置坐标，$\rho ( X , X _ { \nu g } )$ 为当前位置与虚拟目标点的欧式距离， $u$ 为领航者速度大小， $\varepsilon$ 为速度增益。

# 2)避障行为

跟随者的避障方法已在本文第1章中详细阐述。当跟随者执行避障行为时，由于偏离了虚拟目标点方向，因此无法保持编队队形。这种情况下，出于以下两点的考虑，跟随者与领航者之间保持距离不变，只改变角度是较为理想的情况：a)保证领航者与跟随者的通信距离；b)保证跟随者与领航者之间不会发生碰撞。

如图5所示，建立以领航者为中心，半径为i的圆，i为跟随者与领航者的编队距离。当决策航向所在的直线与圆有交点时，与跟随者距离较近的交点为跟随者的当前目标；当决策航向所在的直线与圆无交点时，扩大圆的半径直至相切，切点为跟随者的当前目标。

![](images/85bb30616ec1ee3702c13784f712959785dfd35f1715d2ddd17ba5c17de78298.jpg)  
图5避障行为当前目标点的计算

Fig.5Calculation of current target for obstacle avoidance behavior避障行为的决策可以表示为

$$
V _ { a v o i d \_ o b s t a c l e } = \left\{ \begin{array} { l l } { { \left( u + \varepsilon \rho ( X , X _ { c } ) \right) \left[ \cos \psi \right] } } & { { \left| a ( X , X _ { c } ) - \psi \right| = 0 } } \\ { { { } } } & { { { } } } \\ { { \left( u - \varepsilon \rho ( X , X _ { c } ) \right) \left[ \cos \psi \right] } } & { { \left| a ( X , X _ { c } ) - \psi \right| = \pi } } \end{array} \right.
$$

其中 $\rho ( X , X _ { c } )$ 为当前位置与当前目标点的欧式距离， $\psi$ 为局部路径规划算法决策航向， ${ a } ( X , X _ { c } )$ 表示从当前位置指向当前目标点的射线与 $x$ 轴的夹角。

# 3）保持行为

在 $l - \varphi$ 的编队控制结构下，当领航者航向角发生改变时，跟随者的虚拟目标点位置会发生突变。对位于领航者转弯内侧的跟随者来说，目标点可能会位于其后方。此时使跟随者转弯以跟随后方目标点显然是不合理的，保持行为设置其维持当前航向，并减速等待目标点。保持行为的决策可以表示为

$$
V _ { k e e p } = ( u - \varepsilon \rho ( \boldsymbol { X } , \boldsymbol { X } _ { \nu g } ) ) \binom { \cos \psi _ { c } } { \sin \psi _ { c } }
$$

其中 $\rho ( X , X _ { \nu g } )$ 为当前位置与虚拟目标点的欧式距离， $\psi _ { c }$ 为AUV当前航向。

# 4）跟随行为

当领航者发布队形为一字队形时，说明前方可通行的宽度较小。此时，在形成编队后，跟随者直接跟踪领航者的轨迹，即跟随者将领航者发送的位置信息保存，作为自己的目标点序列。

# 5）行为选择

跟随者行为选择如下：

a)若当前队形为一字形且已经形成编队，执行跟随行为；否则转向步骤b);

b)判断虚拟目标点位于当前位置的前方或后方，若为前方，转向步骤c)；否则转向步骤d);

c)计算目标航向与障碍物的最近距离 $D$ ，若小于设置的阈值 $D _ { s 1 }$ ，执行避障行为；否则执行驶向目标点行为；

d)计算当前航向与障碍物的最近距离 $D ^ { ' }$ ，若小于设置的阈值 $D _ { s } ^ { ' }$ ，执行避障行为(当前航向作为避障算法的目标航向);否则执行保持行为。

需要说明的是，在领航者发布变换队形的指令后，为了快速形成编队，跟随者的行为选择方式有所不同。此时，若当前位置与目标点之间无障碍物，选择驶向目标点行为，待新的编队形成后，恢复上述的行为选择方式。

# 3 仿真实验

为证明算法的可行性，本文采用视景平台以及真实的水下机器人控制软件进行了仿真实验，包括单台AUV的避障实验以及三台AUV协同避障实验。如图6、7所示，视景平台在实际的多波束测深数据、海图数据等的基础上构建了逼真的三维场景，可以设置多台AUV并接收显示AUV的实时位姿。同时，视景平台还可以设置前视声纳的作用距离，并根据AUV在前视声纳探测范围内不同角度距障碍物的距离实时模拟并返回前视声纳图像，这与真实前视声纳的成像原理类似。平台可以设置不规则形状、长方体、圆柱体三种不同类型的障碍物。水下机器人控制软件能够按照一定的频率模拟AUV之间的通信。实验中每台AUV均在 $1 0 0 \mathrm { m }$ 深度定深航行。

![](images/efc2c427987b6f1521ff09c1753c7cc3a0036f3855f9210b00fdd26f9714b832.jpg)  
图6视景平台  
图9本文算法在不同场景下规划结果 Fig.9Planning results of the proposed algorithm in different scenarios

![](images/6b52878debe573c51c334e7ff5d4231514d69826919c07fff1d94e4e579693c5.jpg)  
Fig.6Viewing platform   
图7前视声纳图像  
Fig.7Forward looking sonar image   
表1不同场景下避障性能指标统计

每台AUV的仿真框架如图8所示：在视景平台上设置障碍物，平台会回传每个AUV的前视声纳信息；每个AUV根据感知信息以及目标点按照本文算法进行决策，得到速度指令V；分别将速度大小及速度方向(航向)传给对应的 PID控制器，得到相应的控制量；将控制量传入AUV模型，从而得到更新后的位姿；最后将位姿传给视景平台进行实时更新显示。这种仿真方式从AUV的环境感知、运动控制及通信等方面较大程度地模拟了真实AUV的情况。

# 3.1单AUV避障仿真实验

为验证本文AUV局部路径规划算法，设置单AUV避障仿真实验。实验中AUV的速度大小保持不变，设置 $u = 1 . 5 \mathrm { m / s }$ 。分别在离散障碍物场景、不同类型障碍物场景、复杂场景以及海山场景中采用本文算法进行实验，规划结果如图9、表1所示。以距障碍物的最小距离、运行时间、路径长度以及路径平滑度作为衡量规划结果的指标，其中路径平滑度使用避障过程中航向总变化量计算。实验结果显示，在不同场景下AUV均顺利通过障碍物区域，并在避障过程中与障碍物保持足够的安全距离。

![](images/39ed34d7e1e79fc4476832f9d13f3c72322a411b0dcfa9a9b8bba6a00465fc7b.jpg)  
Fig.8Simulation framework ofAUV

50 50避障航线 避障航线原定航线 -原定航线-50 -50 1  
(u)/ ()/-150 -150-250 -250-50 50 150 250 -50 50 150 250X/(m) X/(m)(a)离散障碍物场景 (b)不同类型障碍物场景350航线 700 避障航线--原定航线250购] 500  
150 (u)/X 三Y 30050 100-50 -100-100 0 100 200 -100 100 300 500 700X/(m) X/(m)(c)复杂场景 (d)海山场景

Tab.1 Statistics of obstacle avoidance performance indicators in different scenarios   

<html><body><table><tr><td>场景</td><td colspan="4">最小距离/m运行时间/s路径长度/m路径平滑度/(°)</td></tr><tr><td>离散障碍物</td><td>10.15</td><td>289.68</td><td>430.37</td><td>108.34</td></tr><tr><td>不同类型障碍物</td><td>10.21</td><td>314.72</td><td>459.56</td><td>350.25</td></tr><tr><td>复杂场景</td><td>7.73</td><td>286.67</td><td>418.50</td><td>322.73</td></tr><tr><td>海山场景</td><td>10.42</td><td>922.17</td><td>1374.82</td><td>257.18</td></tr></table></body></html>

为进一步验证本文算法的有效性，在离散障碍物场景下采用人工势场法及RRT算法进行规划，并与本文算法规划结果进行对比，结果如图10、表2所示。实验结果表明，在安全距离相当的情况下，本文算法相较于人工势场法路径更为平滑，运行时间更短。RRT算法由于具有较大的随机性，规划的路径较为曲折。

![](images/631f9b80b2749631055ba1388c61658f72d9364c873e277bae3e37d9ab93954c.jpg)  
图8AUV仿真框架  
图10人工势场法及RRT算法规划结果  
Fig.1OPlanning results of artificial potential field method and RRT

Tab.2Comparison of performance indicators of different algorithms   

<html><body><table><tr><td>算法</td><td colspan="3">最小距离/m 运行时间/s 路径长度/m</td><td>路径平滑度/°</td></tr><tr><td>本文算法</td><td>10.15</td><td>289.68</td><td>430.37</td><td>108.34</td></tr><tr><td>人工势场法</td><td>9.93</td><td>356.48</td><td>440</td><td>2283.82</td></tr><tr><td>RRT</td><td>5.32</td><td>379.07</td><td>461.73</td><td>1666.57</td></tr></table></body></html>

# 3.2多AUV协同避障仿真实验

表2不同算法性能指标对比  

<html><body><table><tr><td>参数</td><td>安全距离/m</td><td>避障距离阈值/m</td><td>速度区间/(m/s)</td><td>α βε</td></tr><tr><td>领航者</td><td>15</td><td>80</td><td>1.5-1.5</td><td>0.60.4/</td></tr><tr><td>跟随者</td><td>10</td><td>80</td><td>0-3.0</td><td>0.6 0.4 0.1</td></tr></table></body></html>

为验证本文提出的多AUV协同避障算法，采用三台AUV进行仿真实验。算法参数选取如表3所示。

如图11所示，实验中三台AUV的期望队形为三角形队形，变换队形为一字队形。队形参数的选取如表4所示。

![](images/a5fc6db23add0f5eab2723fc99fd4ab98f3c59586b5ea3cdf42d2960e6f4b2da.jpg)  
图11 三角形及一字队形

Tab.3 Selection of algorithm parameters   
表4队形参数选取  
Tab.4Selection of formation parameters   

<html><body><table><tr><td colspan="3">三角形</td><td colspan="2">一字形</td></tr><tr><td>1</td><td></td><td></td><td>1</td><td></td></tr><tr><td>30m</td><td>150°</td><td>15m</td><td>30m</td><td>180°</td></tr></table></body></html>

3.2.1算法仿真

根据上述的算法参数及队形参数设置，在三种不同的场景下进行仿真实验，分别为离散障碍物场景、简单场景以及复杂场景。场景设置及实验结果分别如图 $1 2 { \sim } 1 4$ 、表5所示。采用平均队形偏离度及恢复队形时间作为衡量规划结果的指标。其中队形偏离度 $\delta$ 由当前队形与期望队形计算确定：

$$
{ \delta \mathrm { { = } } \sum _ { i = 1 } ^ { n } } \lvert d _ { i } - l _ { i } \rvert
$$

其中 $d _ { i }$ 为当前时刻AUV间距离， $l _ { i }$ 为期望队形AUV间距离。恢复队形时间定义为从最后一台AUV避障结束开始，到队形偏离度小于7.5所用时间。

![](images/a3fd6aa4e3aa48f8da6dcddfb46e37c25eef3d51a41ad50e98282374fd019675.jpg)  
Fig.11Triangle formation and inline formation   
图12离散障碍物场景多AUV协同避障轨迹 Fig.12 Collaborative obstacle avoidance trajectories of multi-AUV in discrete obstacle scenario

从实验结果可以看出，领航者规划编队整体前进路线，跟随者通过与领航者进行信息交互及环境感知躲避障碍物，从而在避障过程中兼顾编队需求。从队形变化中可以看出，多AUV系统能够根据障碍物情况自主压缩队形，呈现出自适应队形变换的特点，且AUV之间能够保持一定的距离，保证AUV的安全。多AUV系统在避障结束后能够快速恢复原始队形，继续在原定航线上执行任务。

![](images/d04bd49421d881346d4e01154014d3fd98af1fc553c75091a9264a6f8441251a.jpg)  
图13简单场景多AUV协同避障轨迹

![](images/0398cb6d389220aa49b6dfab3d55c204a0246d052411e6954f084d8d6690232a.jpg)  
Fig.13 Collaborative obstacle avoidance trajectories of   
图14复杂场景多AUV协同避障轨迹

表3算法参数选取  
表5不同场景下协同避障指标统计  
Tab.5Statistics of collaborative obstacle avoidance performance indicators in different scenarios   

<html><body><table><tr><td>场景</td><td>平均队形偏离度/m</td><td>恢复队形时间/s</td></tr><tr><td>离散障碍物场景</td><td>9.86</td><td>4.01</td></tr><tr><td>简单场景</td><td>8.32</td><td>3.02</td></tr><tr><td>复杂场景</td><td>9.14</td><td>3.02</td></tr></table></body></html>

为验证算法提出的队形变换以及跟随行为，设置狭窄水道场景，五部分的宽度分别为 $6 0 \mathrm { m }$ 、 $4 0 \mathrm { m }$ 、 $2 8 \mathrm m$ 、 $2 3 \mathrm { m }$ 、 $2 8 \mathrm m$ ，多 AUV协同避障实验结果如图15、16所示。

![](images/2f17dbe92830ebc6c0ca1724c79dced6e3f15c84e2b61d8211de0c017153d002.jpg)  
Fig.14 Collaborative obstacle avoidance trajectories of multi-AUV in complex scenario   
图15狭窄水道场景多AUV 协同避障轨迹 Fig.l5Collaborative obstacle avoidance trajectories of multi-AUV in narrow waterway scenario

实验结果显示，多AUV通过狭窄水道可分为以下几个阶段：

a)在 $6 0 \mathrm { m }$ 宽的水道中，编队保持原队形即可安全通过，当跟随者发现航行前方存在障碍物且距离小于设定的阈值时，开始躲避障碍物；

b)在 $4 0 \mathrm { m }$ 宽的水道中，两个跟随者均需要避障，队形宽度压缩。当领航者计算前方可通行宽度小于编队可压缩最小宽度时，发布变换一字队形命令，并将自身与障碍物之间的

安全距离调整为 $1 0 \mathrm m$

c）当一字队形形成后，跟随者执行跟随行为，将领航者的轨迹点作为自己的目标点，进行轨迹跟踪;

d)当领航者声纳视野内不存在障碍物时，开始驶向避障目标点。考虑到跟随者的安全，领航者在40s后发布恢复队形的命令，跟随者变换为三角形队形；

e）到达避障目标点后，多AUV继续在原定航线上编队执行任务。

![](images/613cf2fddd1c36df2fd6640914efbb06cdfe8dc02c9ee5d225a677e558540d4e.jpg)  
图16跟随者执行跟随行为

3.2.2对比实验

为进一步验证本文提出的多AUV协同避障算法的有效性，将其与目前常用于障碍物环境下编队控制的人工势场法进行对比，结果如图17所示。

![](images/44c965e60ea989166efdd98e5660a76afb0c4a7cdce0969c5b33080ce9854f5d.jpg)  
Fig.16Followers perform follow behavior

表6显示，在多AUV避障过程中，本文算法相较于人工势场法具有更小的平均队形偏离度，并且在避障结束后能够更快速恢复队形，有利于多AUV系统后续任务的执行。

表6海山场景本文算法与人工势场法实验结果对比

Tab.6Comparison of results of the proposed algorithm and artificial potential field method in seamount scenario   

<html><body><table><tr><td>算法</td><td>平均队形偏离度/m</td><td>恢复队形时间/s</td></tr><tr><td>本文算法</td><td>13.38</td><td>8.04</td></tr><tr><td>人工势场法</td><td>21.67</td><td>26.11</td></tr></table></body></html>

在目前的研究中，一部分学者认为当多机器人系统遇到障碍物时，避障的优先级相较于编队更高，多机器人系统应当解除编队，在躲避障碍物后恢复队形。基于此，将本文算法与编队拆分避障方法进行对比，结果如图18、表7所示。

由于编队拆分避障不具有队形偏离度的概念，采用AUV间距离进行对比。在实验场景中，采用编队拆分避障方法AUV各自进行避障，选择从障碍物两侧绕行，导致AUV距离过远，甚至造成失联。由于AUV距离过远，避障结束后要花费较长时间恢复队形。相较于编队拆分避障，本文算法在保证AUV之间保持一定距离的前提下，将AUV之间的最远距离维持在编队距离附近，能够在避障结束后快速恢复编队。

![](images/4bbcc4cd32c9e2e6d7cdc8da835c8885ed31d11349c752dcc62f4e74ac4d9d39.jpg)  
图18本文算法与编队拆分避障实验结果 Fig.18Results of the proposed algorithm and formation split 表7本文算法与编队拆分实验结果对比 Tab.7Comparison of results of the proposed algorithm and formation split

<html><body><table><tr><td>算法</td><td>AUV间最近距离/mAUV间最远距离/m恢复队形时间/s</td><td></td><td></td></tr><tr><td>本文算法</td><td>17.34</td><td>38.69</td><td>12.03</td></tr><tr><td>编队拆分</td><td>27.71</td><td>162.08</td><td>39.17</td></tr></table></body></html>

# 3.2.3算法可扩展性实验

上述实验对不同场景下三台AUV协同避障进行了算法验证，为验证算法的可扩展性，将AUV数量增加至五台，分别在简单场景及复杂场景中进行实验。五台AUV的编队队形及队形参数分别如图19、表8所示。

![](images/eac84b1a104309baad497987a25c9f22ec9d891bf0cb1ca7873bfc9f8d9a47c1.jpg)  
  
图19五台AUV队形设置Fig.19Setting of formation of five auvs表8五台AUV队形参数

Tab.8Formation parameters of five auvs  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>l/m</td><td>30</td></tr><tr><td>h/m</td><td>60</td></tr><tr><td>（°）</td><td>150</td></tr></table></body></html>

算法参数的选取与三台AUV系统相同，实验结果如图20、21所示。实验结果显示，本文算法在不同场景下应用于五台AUV系统均取得了良好的效果。

![](images/109eca6427c14092c4a620c97a53c7b2cca2f875ab75bd2cb2b1a86cd2ee017d.jpg)  
图17海山场景本文算法与人工势场法实验结果 Fig.17Results of the proposed algorithm and artificial potential field method in seamount scenario   
图20简单场景五台AUV协同避障轨迹 Fig.20Collaborative obstacle avoidance trajectories of five auvs in simple scenario

![](images/00be0576de82ce1f7457f41c86dffe761713ffca25b331d21198a02909ef3524.jpg)  
图21复杂场景五台AUV协同避障轨迹 Fig.21Collaborative obstacle avoidance trajectories of five auvs in complex scenario

# 4 结束语

本文基于前视声纳提出了一种AUV局部路径规划方法，并在此基础上，结合编队控制方法，提出了一种未知环境下多AUV协同避障方法。行为的设置不仅考虑了AUV与障碍物的碰撞，还考虑了AUV之间的相互碰撞。设计了避障行为下目标点的计算方法，使跟随者在避障过程中与领航者的距离基本维持在编队距离，保证AUV的通信与安全。水下多种场景的仿真实验均取得了良好的效果，证明本文方法能够实现多AUV在未知环境下的协同避障，兼顾避障过程中的编队需求，在避障结束后能够快速恢复编队，并具有可扩展性。未来的工作重点是依托实验室的AUV进行实物验证。

# 参考文献：

[1]Cruz J.Leader-follower strategies for multilevel systems [J].IEEE Trans on Automatic Control,1978,23 (2): 244-255.   
[2]Brooks R.A robust layered control system for a mobile robot [J].IEEE Journal on Robotics and Automation,1986,2(1):14-23.   
[3]Khatib O.Real-time obstacle avoidance for manipulators and mobile robots[J]. International Journal ofRobotics Research,1986,5(1):90- 98.   
[4]Tan K H,Lewis MA.Virtual structures for high-precision cooperative mobile robotic control [C]//Proc of IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS).Piscataway,NJ: IEEE Press, 1996:132-139.   
[5] 王乐乐，畦泽智，蒲志强，等．一种改进 RRT 的多机器人编队路径 规划算法 [J]．电子学报,2020,48(11):2138-2145.(WangLele,Sui Zezhi,Pu Zhiqiang,et al.An improved RRT algorithm for multi-robot formation path planning [J].Acta Electronica Sinica,202o,48(11): 2138-2145.)   
[6]Xu Dongdong,Zhang Xingnan, Zhu Zhangqing,et al. Behavior-based formation control of swarm robots [J].Mathematical Problems in Engineering,2014,2014:1-13.   
[7]徐博，张娇，王超．一种基于人工势场多 AUV 集群的实时避障方法 [J]．中国舰船研究,2018,13(06):66-71.(Xu Bo,Zhang Jiao,Wang Chao.A real-time obstacle avoidance method for multi-AUV cluster based on artificial potential field [J]. Chinese Journal of Ship Research, 2018,13 (06): 66-71.)   
[8]Wang Ning,Dai Jiyang,Ying Jin.UAV formation obstacle avoidance control algorithm based on improved artificial potential field and consensus [J]. International Journal of Aeronautical and Space Sciences, 2021,22 (6): 1413-1427.   
[9] 张佳龙，闫建国，张普，等．基于一致性算法的无人机协同编队避障 Xi’an Jiaotong University,2018,52 (09): 168-174.) [10]付雷，秦一杰，何顶新，等．基于改进人工势场法的多机器人编队避 障[J].控制工程，2022,29(03):388-396.(Fu Lei,Qin Yijie,He Dingxin,et al. Obstacle avoidance in multi-robot formation based on improved artificial potential field [J]. Control Engineering of China,   
2022,29 (03): 388-396.) [11] Feng Yunduo,Wu Yanxuan,Cao Haozhe,et al.UAV formation and obstacle avoidance based on improved APF [C]// Proc of the 10th International Conference on Modelling,Identification and Control (ICMIC).Piscataway,NJ: IEEE Press,2018:1-6. [12]陈骏岭，秦小麟，李星罗，等．基于人工势场法的多机器人协同避障 [J]．计算机科学,2020,47(11):220-225.(Chen Junling,Qin Xiaolin,Li Xingluo,et al.Multi-robot collaborative obstacle avoidance based on artificial potential field method[J].Computer Science,2020,47(11):   
220-225.) [13] Lee G,Chwa D.Decentralized behavior-based formation control of multiple robots considering obstacle avoidance [J]. Inteligent Service Robotics,2018,11(1): 127-138. [14]常路，单梁，戴跃伟，等．未知环境下基于改进 DWA 的多机器人编 队控制[J/OL].控制与决策：1-10.(2021-08-02)[2022-01-20].DOI:   
10.13195/j.kzyjc.2020.1817.(Chang Lu, Shan Liang,Dai Yuewei,et al.Multi-robot formation control in unknown environment based on improved DWA[J/OL].Control and Decision: 1-10.(2021-08-02)[2022-   
01-20]. DOI: 10.13195/j. kzyjc.2020.1817.) [15]任立敏，王伟东，杜志江，等．障碍环境下多移动机器人动态优化队 形变换[J].机器人,2013,35(5):535-543.(Ren Limin,Wang Weidong, Du Zhijiang,et al. Dynamic and optimized formation switching for multiple mobile robots inobstacle environments [J]. Robot,2013,35(5):   
535-543.) [16] Vilca JM,Adouane L, Mezouar Y. Adaptive leader-follower formation in cluttered environment using dynamic target reconfiguration [C]//Proc of the 12th International Symposium on Distributed Autonomous Robotic Systems.Tokyo: Springer,2016:237-254. [17]吴军成，肖宇峰，霍建文．不确定环境下多机器人编队控制研究[J]. 计算机应用研究，2021，38(04):1123-1127.(Wu Juncheng，Xiao Yufeng,Huo Jianwen. Research on multi-robot formation control in uncertain environment [J].Application Research of Computers,2021,38 (04): 1123-1127.) [18] Wasik A,Pereira JN, Ventura R,et al. Graph-based distributed control foradaptivemulti-robotpatrollingthrough localformation transformation [Cl// Proc of IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS).Piscataway,NJ: IEEE Press,   
2016: 1721-1728. [19]郭银景，孟庆良，孔芳，等.AUV路径规划算法研究现状与展望[J]. 计算机科学与探索,2020,14(12):1981-1994.(Guo Yinjing,Meng Qingliang,Kong Fang,et al. Research status and prospect of AUV path planning algorithms [J].Journal of Frontiers of Computer Science and Technology,2020,14 (12): 1981-1994.) [20]隋玲玲．复杂未知环境下机器人路径规划算法研究[D].上海：复 旦大学,2O11.(Sui Lingling.Research on robot path planning algorithm in complex and unknown environment [D]. Shanghai: Fudan University,   
2011.) [21] Desai JP, Ostrowski JP, Kumar V. Controlling formations of multiple mobile robots [Cl//Proc of IEEE International Conference on Robotics and Automation. Piscataway,NJ: IEEE Press,1998: 2864-2869.