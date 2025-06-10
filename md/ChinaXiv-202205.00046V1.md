# 基于FDS和元胞自动机动态耦合的火灾疏散模型

李超ab，李宇飞ab，霍非舟ab，张钦钦a,b(武汉理工大学 a.中国应急管理研究中心;b.安全科学与应急管理学院，武汉 430070)

摘要：为研究火灾场景下温度、烟气和CO浓度等灾害因子对疏散的影响，建立基于FDS和元胞自动机动态耦合的火灾疏散模型。模型将FDS 的网格和元胞自动机的元胞一一对应，把由FDS 运行得到的灾害数据通过Python 等技术手段实时加载到元胞中，使灾害数据持续影响行人转移概率，从而实现灾害和疏散的动态耦合；以单层教学楼作为仿真场景进行模拟分析，对火源位置和热释放速率等因素进行讨论，得出这些因素对行人疏散进程的影响规律；将模型与传统软件和同类方案进行对比，以对比其异同。研究表明：火灾导致的高温和烟气会影响行人对疏散路径和安全出口的选择；热释放速率越大，行人越早处于危险状态，同时处于危险状态的行人也越多；该模型相比传统疏散软件不仅能考虑火灾产生的致灾因子对行人疏散的动态影响，还能确定行人最早处于危险状态的位置和时间，并用可视化的方式表现出来。

关键词：火灾疏散；FDS；元胞自动机；动态耦合；仿真模拟 中图分类号：TP15 doi:10.19734/j.issn.1001-3695.2022.03.0086

Fire evacuation model based on dynamic coupling of FDS and cellular automata

Li Chaoa, b,Li Yufeia b,Huo Feizhoua,bt, Zhang Qinqina,b (a.China Research Center for Emergency Management,b.School of Safety Science& Emergency Management, Wuhan University of Technology,Wuhan Hubei 430070,China)

Abstract: To studythe influence of disaster factors suchas temperature,smoke,and CO concentration on evacuationat the fire scene,establishedafire evacuation modelbasedon the dynamic couplingofFDS and cellar automata.Mappedthe grid ofFDS andthecellofcellularautomata one byone,and loaded the disaster data obtained from theoperationofFDS into the cell in rea-timethrough Pythonandother technical means,sothat the disasterdatacancontinuouslyafect thepedestrian transferprobability,torealize thedynamiccouplingbetweendisasterandevacuation;Taking thsingle-storyteachingbuilding as the simulation scene forsimulation analysis,discussd the factors suchas firesource locationand heatrelease rate,and obtained the influence lawofthese factors onpedestrian evacuation process; Comparedthemodelwith traditional software and similarschemes tocompare their similaritiesand diferences.Theresearch shows thatthe high temperature and smoke caused by fire willaect thechoiceofpedestrian evacuationpath and emergencyexit; The greater theheat releaserate,the earlierpedestriansarein danger,andthemore pedestriansarein dangeratthesame time; Compared with the traditional evacuationsoftware,the modelcannotonlyconsiderthe dynamic impactofthe disastercausing factors caused by fire on pedestrian evacuation butalso determine the location and time of pedestrians in the first dangerous state,which can be displayed visually.

Key words: fire evacuation; FDS; cellular automata; dynamic coupling; analogue simulation

# 0 引言

近年来，建筑火灾频发，造成了大量的人员伤亡和财产损失。据近10年的数据统计，我国一共发生过3.1万起高层建筑火灾，死亡人数474人，直接经济损失约15.6亿元[1]。发生火灾后，人员在恐慌、从众、冲动等心理特征下，难以冷静应对形势并作出理性的逃离决策。因此，为最大程度地减少火灾造成的人员伤亡，开展火灾条件下的人员疏散动力学研究是非常必要的。

考虑到火灾条件的危险性，在现实中不可能进行火灾疏散实验，因此随着计算机技术的发展，计算机模拟成为一个非常重要而可行的工具。国际上开发的较为成熟的行人疏散模拟软件包括Pathfinder[2]、BuildingEXODUS[3]和$\mathrm { F D S + E V A C ^ { [ 4 ] } }$ 等。这些疏散仿真软件在工程实践中具有较高的应用价值。但仿真软件也基于固定的行人疏散模型，用户不能改变疏散的实际移动规则，这是疏散软件最大的局限。例如，一些学者通过使用FDS计算出建筑发生火灾后的可用疏散时间(ASET)，然后再通过Pathfinder等软件计算出该建筑行人的必须疏散时间(RSET)，最后通过比较RSET与ASET的大小来确定建筑是否满足防火和疏散的要求，这样就没能很好地考虑到火灾灾害因子对疏散过程的影响[1,5]。

鉴于上述原因，越来越多的研究人员将目光投放到建立疏散模型上。总体上讲，疏散模型可大致分为宏观模型和微观模型两类6。宏观模型将人群移动视为流体运动，能够高效计算出大规模人群的疏散时间，但宏观模型过于理想化，无法反映个体之间的相互作用和异质性。而作为微观模型典型代表的元胞自动机模型不仅能够反映出行人个体间的差异还能体现出行人在疏散过程中典型的心理特征和行为反应，受到广大研究者的关注。Zheng等[7\~9]考虑了火灾和烟气对行人运动的影响以及烟层场对疏散过程的影响，改进了基于场域模型的元胞自动机模型。金泽人等[10]考虑了火灾导致的恐慌心理对行人移动方向的影响，提出基于火灾场景的元胞自动机疏散模型。萨木哈尔·波拉提等[1]使用量化的趋近移动强度来定义人员移动规则，通过竞争占点原则解决人员疏散过程中的冲突问题。江雨燕等[12]通过分析已有的元胞自动机理论，结合人员疏散的特点，构建了火灾疏散模型，研究表明在陌生的疏散环境或紧急情况下，适当的从众行为会提高疏散效率。陈长坤等[13]为研究火源对人员疏散的影响，结合元胞自动机提出一种考虑多出口吸引、人员从众行为与火源威胁三者耦合作用的场域疏散模型。

上述内容表明，很多学者已经考虑到了火灾因素对行人疏散过程的影响，并建立了相应的数学模型。然而，这些模型对火焰蔓延和烟气扩散的描述过于简单化和理想化[7\~13],难以真实地再现实际火灾下的疏散过程。Cao等[14]通过FDS将火灾数据导入到元胞自动机中，建立了更符合火灾实际的疏散模型。但模型仍然存在场景设置比较简单(没有考虑建筑空间内障碍物结构对烟气扩散和行人疏散的影响)和可视化程度较低的问题。因此，本文提出一种基于FDS和元胞自动机动态耦合的火灾疏散模型。

# 1 模型描述

# 1.1FDS 和元胞自动机简介

FDS是具有三维可视化动态功能的火灾模拟软件，其基于火源驱动流体的CFD模型能够有效描述低马赫数气体流动问题，可以很好地计算火场中的温度变化和气体浓度变化，既能计算烟气流动和热传递过程，还可用来观察火场内的烟气、温度、能见度、热释放速率、燃烧产物浓度等参数随火灾变化而变化的情况[15]。FDS的基本思想是根据质量(组分)守恒、动量守恒和能量守恒定律建立相应的基本方程，其方程如下：

$$
\frac { \partial \rho } { \partial t } { + \nabla \cdot \rho \pmb { u } } = 0
$$

$$
\frac { \partial } { \partial t } ( \rho \pmb { u } ) + \nabla \cdot \rho \pmb { u } \pmb { u } + \nabla p = \rho g + \pmb { f } + \nabla \cdot \pmb { \tau } _ { i j }
$$

$$
\frac { \partial } { \partial t } ( \rho h ) + \boldsymbol { \nabla } \cdot \rho h \boldsymbol { u } = \frac { \mathrm { d } p } { \mathrm { d } t } + \dot { \boldsymbol { q ^ { m } } } - \boldsymbol { \nabla } \cdot \pmb { q } _ { r } + \varphi
$$

$$
p = { \frac { \rho R T } { \overline { { W } } } }
$$

其中： $\rho$ 为气体密度， $\mathrm { k g / m ^ { 3 } }$ ； $\pmb { u }$ 为速度矢量， $\mathrm { m / s }$ ； $g$ 为重力加速度， $\mathrm { m } / \mathrm { s } ^ { 2 }$ ； $f$ 为外部力矢量， $\mathrm { ~ N ~ }$ ； $\tau _ { i j }$ 为牛顿流体黏性应力张量， $\mathrm { ~ N ~ }$ ； $h$ 为显焓， $\mathrm { J / k g }$ ； $p$ 为压力，Pa； $\dot { q ^ { \dag } }$ 为单位体积的热释放速率， $\mathrm { W } / \mathrm { m } ^ { 3 }$ ； ${ \pmb q } _ { r }$ 为热通量矢量， $\mathrm { W } / \mathrm { m } ^ { 2 }$ ； $T$ 为温度，K； $\varphi$ 为耗散函数； $R$ 为理想气体常数； $\overline { { W } }$ 为气体混合物相对分子质量。

元胞自动机起源于1951年冯·诺依曼提出的生命游戏理论，在20世纪80年代被应用于公共建筑中的行人疏散研究中，该模型不同于其他的动力学模型，它不是由严格意义的物理方程或函数来确定，而是用一系列模型构造的规则构成。元胞的状态是按照构造的规则和周围其他元胞的状态进行实时更新，从而构成动态系统的演化。常见的元胞空间结构和邻域类型分别见图1和2所示。

# 1.2FDS和元胞自动机的动态耦合模型

FDS对烟气流动和热传递过程的计算是基于网格的，即在一定的时间间隔内，可以计算出每一个网格由火灾产生的灾害数据，如温度、CO浓度、烟气浓度等。同时，元胞自动机疏散模型中的行人运动也是基于元胞(网格)的。基于此，将FDS运行得到的数据通过Python 等数据处理工具进行处理后，以与疏散更新相同的时间间隔(时间步)加载到元胞自动机模型中，实时变化的灾害数据通过动态改变元胞自动机中行人运动的综合场值从而持续影响行人各方向的运动转移概率，这样便实现了每一个时间步灾害数据和疏散行为的动态耦合，如图3所示。将灾害数据和疏散行为进行动态耦合，能够实时反映出灾害因子对行人疏散过程的影响，更加符合疏散实际。

![](images/7cdec3a015ad1d645266708c21efef5421bd32516189227db422fbeece017673.jpg)

![](images/87e07265be68e25673e23d7ca34eb30cdc127ceb795204dabd4bf7d4e2a27f37.jpg)  
Fig.1 Common cellular spatial structure   
图2常见的邻域类型

![](images/7af458498773dec665e90ecd0e99a62a6d5eb04b154b82a390c30632c8d5200d.jpg)  
图1常见的元胞空间结构  
Fig.2Common neighborhood types   
图3技术路线图  
Fig.3Technology roadmap

值得注意的是，FDS得到的灾害数据是三维空间中的，但元胞自动机的行人运动空间为二维平面，因此在设置的时候，对数据进行了这样的处理：

1)FDS每个网格的高度为楼层高度。

2)根据建筑性能化防火设计的最不利原则，选取每个网格温度、烟气浓度和CO浓度的最大值作为最终导入数据。

3)模型时间步更新频率设置为1步/0.25s，即每0.25s加载一次灾害数据并更新行人位置。

基于FDS和元胞自动机动态耦合的火灾疏散模型建立在二维网格内，元胞大小设置为 $0 . 4 \times 0 . 4 \mathrm { m }$ 对应地，FDS中的网格平面大小也设置为 $0 . 4 { \times } 0 . 4 \mathrm { m } )$ ，每个元胞或为空或被墙壁以及行人占据。边界为墙壁和安全出口，人员运动到安全出□即为疏散成功。选取矩形网格作为疏散基本单元；选取

Moore 型邻域作为行人疏散的概率转移矩阵，以此来确定行人的运动方向。行人的转移概率 $P _ { i j }$ 如式(5)所示。

$$
P _ { i j } = N ^ { - 1 } \exp ( k _ { S } S _ { i j } + k _ { D } D _ { i j } - k _ { C } C _ { i j } - k _ { T } T _ { i j } ) ( 1 - n _ { i j } ) \varepsilon _ { i j }
$$

$$
N = \sum _ { i } \sum _ { j } \exp ( k _ { s } S _ { i j } + k _ { D } D _ { i j } - k _ { C } C _ { i j } - k _ { T } T _ { i j } ) ( 1 - n _ { i j } ) \varepsilon _ { i j }
$$

其中： $N$ 为概率的正规化处理，确保 $\sum P _ { i j } = 1$ ； $i , j$ 分别为目标元胞的横纵坐标； $S _ { i j }$ ， $D _ { i j }$ ， $C _ { i j }$ 和 $T _ { i j }$ 分别表示静态场、动态场、烟气场和温度场； $k _ { s }$ ， $k _ { D }$ ， $k _ { c }$ 和 $k _ { T }$ 分别为 $S _ { i j }$ ， $D _ { i j }$ ， $C _ { i j }$ 和 $T _ { i j }$ 的权重敏感系数，反映了不同场强对总场强的贡献大小，且有 $k _ { s }$ ， $\boldsymbol { k } _ { D }$ ， $k _ { c }$ ， $k _ { T } \in [ 0 , \infty ]$ ； $n _ { i j }$ 和 $\varepsilon _ { i j }$ 分别表征了其余行人和障碍物的占据信息，其取值方法分别如式(7)和(8)所示。

[1，目标元胞被墙或障碍物占据 nij= 0，目标元胞无墙或障碍物占据

静态场 $S _ { i j }$ 表示出口对行人的吸引作用，若疏散场景中不存在障碍物，其大小直接由距离式(9)计算即可，但如果场景中存在复杂障碍物(如“U”型障碍物)时，直接使用距离公式可能会出现行人因陷入局部最优的陷阱而无法行动的状况。解决此问题的常用方法是采用Dijkstra算法计算各元胞位置与出口的距离，本文设置的场景存在障碍物，故采用该算法对静态场进行求解。

$$
\begin{array} { l } { S _ { i j } = \underset { ( i , j ) } { \operatorname* { m a x } } \left\{ \underset { ( i _ { e _ { k } } , j _ { e _ { k } } ) } { \operatorname* { m i n } } \sqrt { ( i _ { e _ { k } } - i ) ^ { 2 } + ( j _ { e _ { k } } - j ) ^ { 2 } } \right\} - } \\ { \underset { ( i _ { e _ { k } } , j _ { e _ { k } } ) } { \operatorname* { m i n } } \sqrt { ( i _ { e _ { k } } - i ) ^ { 2 } + ( j _ { e _ { k } } - j ) ^ { 2 } } } \end{array}
$$

其中， $( i _ { e _ { k } } , j _ { e _ { k } } )$ 为不同出口位置坐标，其中 $k$ 是出口数量， $\boldsymbol { e } _ { k }$ 表示第 $k$ 个出口。

动态场 $D _ { i j }$ 则通过参考其他行人走过的线路信息，描述行人间的从众行为，表达式如式(10)所示。

$$
\begin{array} { r l } & { D _ { i j } ^ { t } = ( ( 1 - d i f ) \cdot ( 1 - d e c ) ) \cdot D _ { i j } ^ { t - 1 } + } \\ & { ( ( d i f \cdot ( 1 - d e c ) ) / 8 ) \cdot \mathrm { s u m } D _ { i j } ^ { t - 1 } + d _ { 1 } - d _ { 2 } } \end{array}
$$

$$
\mathrm { s u m } D _ { i j } ^ { t - 1 } = D _ { i - 1 , j } ^ { t - 1 } + D _ { i - 1 , j - 1 } ^ { t - 1 } + D _ { i - 1 , j + 1 } ^ { t - 1 } +
$$

$$
D _ { i , j - 1 } ^ { t - 1 } + D _ { i , j + 1 } ^ { t - 1 } + D _ { i + 1 , j } ^ { t - 1 } + D _ { i + 1 , j - 1 } ^ { t - 1 } + D _ { i + 1 , j + 1 } ^ { t - 1 }
$$

其中， $d i f$ 和 $_ { d e c }$ 分别表示扩散和衰减系数，这里均设置为$0 . 3 ^ { [ 1 6 ] }$ 。在初始时间，所有元胞的动态场值为0。每当有人通过元胞 $( i , j )$ 时， $D _ { i j } = D _ { i j } + 1$ 。 $d _ { 1 }$ 和 $\boldsymbol { d } _ { 2 }$ 是两个修正系数，当上一个时间步元胞 $( i , j )$ 为空且当前时间步存在行人时， $d _ { \mathrm { 1 } } = 1$ ，否则 $d _ { \mathrm { { 1 } } } = \mathrm { { 0 } }$ ；当上一个时间步元胞 $( i , j )$ 存在行人且当前时间步也存在行人时， $d _ { 2 } = 1$ ，否则 $d _ { 2 } = 0$ ·

在真实的火灾场景下，烟气的扩散比火焰的蔓延更快、更严重。一般情况下，火灾导致的其他威胁因素如结构失效等，不会先于烟气达到危险状态。据统计，在建筑火灾中约$7 5 \% \sim 8 5 \%$ 的死亡是由烟气导致的[17]。烟气场 $C _ { i j }$ 表示烟气浓度对行人的排斥作用，其值直接由FDS导出。值得说明的是，烟气浓度与能见度成反比例关系，如式(12)[18]所示，使用烟气场即可表征烟气浓度对行人疏散的影响，故本模型不再引入文献[14]提出的能见度场。

$$
R = C / ( M _ { s } \cdot K _ { m } ) = C / K
$$

其中， $R$ 为能见度； $c$ 为经验常数； $M _ { s }$ 为烟气粒子的质量浓度； $K _ { \mathfrak { m } }$ 为烟气粒子的消光率。

火灾造成的高温也会对行人疏散造成严重威胁，行人在疏散过程中会基于本能远离高温区域，向温度较低的区域疏散，因此用温度场 $T _ { i j }$ 来表示温度对行人的排斥作用，具体计算方式如式(13)所示。

$$
T _ { i j } = \frac { T } { T _ { 0 } }
$$

其中， $T$ 为温度数据，由FDS导出，并由Python 导入到元胞自动机中； $T _ { 0 }$ 为环境温度，取 $2 0 ^ { \circ } \mathrm { C }$ 。

模型对行人处于危险状态的考虑：

a)大多数烟气中毒死亡的事故都是由CO 造成的，当行人所在元胞的CO 浓度大于等于 $5 0 0 \mathrm { p p m }$ 时[19]，即可说明行人处于危险状态。

b)极端的温度也会导致行人死亡。根据已有研究[17]，人在 $6 5 ^ { \circ } \mathrm { C }$ 的空气中无法呼吸，因此确定 $6 5 ^ { \circ } \mathrm { C }$ 作为楼层火灾危险临界温度。在模型中：当行人目标元胞的温度场 $T _ { i j }$ 大于等于3.25时，即可说明行人处于危险状态。

本文 $k _ { s }$ ， $k _ { D }$ ， $k _ { c }$ 和 $k _ { T }$ 的取值如表1所示。

表1本文的参数取值

Tab.1Parameter value in this article   

<html><body><table><tr><td>参数 取值</td><td></td><td>说明</td></tr><tr><td>ks</td><td>1</td><td>静态场为行人运动基本场</td></tr><tr><td>kp</td><td>0.01</td><td>行人越熟悉环境，动态场值应越低</td></tr><tr><td>kc</td><td>10000</td><td>使烟气场值的数量级与静态场一致</td></tr><tr><td>KT</td><td>1</td><td>温度场值已作处理，系数取1即可</td></tr></table></body></html>

# 1.3演化更新规则

模型采用并行更新的规则对场景中所有行人的位置进行更新，具体更新规则如下：

a）初始化行人分布。根据叠加场强，运用相应公式求出行人转移概率，并确定行人下一步的位置。

b）当多个行人竞争同1个元胞时，随机等概率地选择1 位行人进入元胞，竞争失败的行人留在原地。

c）确定这一时间步处于危险状态的行人，并将其标记。

d）更新下一时间步所有行人位置，并将位于出口位置的行人从场景中移除。

e)重复步骤a) ${ \sim } \mathbf { e }$ 直到所有行人疏散完毕。

# 2 仿真模拟及结果分析

# 2.1疏散系统的物理环境假设

疏散仿真场景设置为 $4 8 . 4 \times 1 5 . 2 \mathrm { m }$ 的单层教学楼，对应的FDS网格数和元胞空间大小均为 $1 2 1 \times 8 6$ 网格(元胞)，如图4(a)和4(b)所示，教学楼层高 $3 . 6 \mathrm { m }$ 。设置两个分别位于场景左右两侧的安全出口，每个安全出口宽度为 $2 . 4 \mathrm { m }$ 。教室中存在大量桌椅，发生火灾时热释放速率(HRR)符合 $\mathfrak { a t } ^ { 2 }$ 增长规律[20]，依据最不利原则设置火灾增长类型为快速火，火灾增长系数取0.04689，HRR设置为 $5 0 0 0 \mathrm { k w } / \mathrm { m } ^ { 2 }$ ，初始火源面积为 $0 . 1 6 \mathrm { m } ^ { 2 }$ ，火源位置详见图4(a)。在FDS中桌椅材质设为“woodpine”，燃烧反应设置为“wood,theyieldof soot$\mathrm { y s } { = } 0 . 0 1 5 \mathrm { g } / \mathrm { g }$ and the yield of CO y $\scriptstyle \mathbf { s } = 0 . 0 0 4 \mathbf { g } / \mathbf { g } ^ { \prime }$ ，设定墙体、地板和楼板为不可燃烧的惰性材料。元胞自动机场景的黑色元胞代表桌椅和墙壁，绿色元胞代表固定分布的行人，数量为720。为了减小随机误差，所有疏散时间步数均取20次模拟的平均值。

在Pathfinder中选用“Steering”模式，设置行人的肩宽为 $0 . 4 \mathrm { m }$ ，行人行为设置为"Go toanyexit”，最大速度为 $1 . 6 \mathrm { m / s }$ 。Pathfinder的场景图如图4(c)所示。

# 2.2灾害因子对疏散过程的影响

120 时间步下的疏散过程和烟气扩散过程如图5所示，不考虑火灾时，教学楼内的疏散人员以最短路径向教学楼两侧的安全出口进行疏散，如图5(a)所示；当场景发生火灾时，左侧出口处的温度和烟气浓度较高,其烟气扩散状态如图5(b)所示，此时更多的行人分布在走廊右侧，如图5(c)所示，其中灰色元胞代表烟气，颜色越深，浓度越大。

高温和烟气影响了场景内行人的出口选择。相比图5(a)，图5(c)中的行人因左侧出口温度和烟气浓度较高，更多地选择向右侧出口进行疏散，这导致右侧出口严重拥堵，也因此增加了总体的疏散时间。

![](images/7cb3c31f4a0eabb137286c8cadb2cee029ca3e95d9954d57ba52be9e2bb72e12.jpg)

图4仿真场景图

![](images/d513ed30f66dd7c138fa7af4dd59f303cd2fafb223d4251fa118dbcc225fd65b.jpg)  
Fig.4Simulation scenario

# 2.3火源位置对疏散的影响

为了探究火源位置对疏散的影响，现分场景进行比较分析。每个场景对应一个火源位置，其他参数均相同，如图6所示。

![](images/2d7a81c4cad9123c2afa8d571a40b7d3e55c592ff6abfd4d7b4aef749228d436.jpg)  
图5120时间步时的疏散过程及烟气扩散图  
图6不同场景下的火源位置分布图  
Fig.6Fire source location distribution in different scenarios

图7显示了3个不同场景下左右出口的疏散人数随时间的变化规律。由图7可知，场景3的总疏散时间最少，160时间步时行人就基本疏散完成；其次是场景2，行人完成疏散需要200时间步；场景1的总疏散时间最长，260时间步时行人才全部疏散完成。这主要是由不同场景下两侧出口的利用率不同导致的，当火灾发生在中间位置时，行人向两侧疏散，两个出口都能都得到较好的利用(图7中场景三左出口和右出口两条曲线相差不大)；火源位置越靠近左侧的出口，左侧的出口就越不安全，越多的行人会选择向右侧出口疏散，从而导致了右侧出口的拥堵，例如，场景一左出口在120 时

间步后就无人通过了。

# 2.4热释放速率对行人处于危险状态的影响

为了探究不同热释放速率对行人处于危险状态的影响，在场景1设置三种不同的热释放速率进行对比研究： (a)$\mathrm { H R R } { = } 5 0 0 \mathrm { k w } / \mathrm { m } ^ { 2 }$ ，(b) $\scriptstyle \mathrm { H R R } = 2 0 0 0 \mathrm { k w } / \mathbf { m } ^ { 2 }$ ， $_ { \mathrm { ( c ) H R R = } 5 0 0 0 \mathrm { k w / m } ^ { 2 } }$ 0不同HRR下处于危险状态的最大人数和最早时间如图8所示。

![](images/bb92c182d6c1db52f04db62dc3467ed7e6b7bdfd8e1fbcbfbbb9d1cf2ff07d93.jpg)  
图7不同场景下疏散人数随疏散时间步的变化图Fig.7Variation of evacuation number and evacuation time steps indifferent scenarios

![](images/bed8cb7d2a9a3e7a7a78b631c732a0c1d8a83e5831a711de1f52bfed93d89937.jpg)  
图8不同HRR下处于危险状态的最大人数和最早时间 Fig.8Time and number of people in the first dangerous state and the first time under different HRR

从图8可以看出，热释放速率越高，行人就越早处于危险状态，同时处于危险状态的行人也越多。这是因为热释放速率升高导致场景内温度升高速率变快、烟气产量变大，更多靠近左侧出口的上下两个教室中的行人因教室门宽度限制而无法及时疏散。

除此之外，模型还可将某一时间步下处于危险状态的行人用可视化的方式直观地表现出来，图9为场景3在$_ { \mathrm { H R R } = 5 0 0 0 \mathrm { k w } }$ 下40时间步时处于危险状态的行人标记图，其中红色元胞代表处于危险状态的行人。

![](images/2dbe05149ec3f53a2b44c843effd938c0257f4a7c4a019850e488620dd187b86.jpg)  
Fig.5Evacuation process and smoke diffusion diagram at 30 time steps   
图940时间步处于危险状态的行人标记图  
Fig.9Pedestrian marker diagram with a dangerous 4O time steps

# 2.5与传统软件和同类方案的对比分析

Pathfinder的模拟过程如图10所示，与图5(a)相比，在同样的时间步下，其场景内存在更多行人。Pathfinder与本文模型(无火灾时)疏散人数随时间的变化对比如图11所示。本文的元胞自动机模型使用了Dijkstra算法计算静态场，Pathfinder 的路径规划基于A\*算法[21]，而A\*算法是Dijkstra算法的扩展[22]，在本质上二者相差不大。因此，造成差异的可能原因是：Pathfinder相比元胞自动机更多地考虑了行人之间的碰撞和速度的变化，如图12所示。

然而，Pathfinder最大的局限在于无法考虑火灾对疏散过程的动态影响，在场景一 $_ { \mathrm { H R R } = 5 0 0 0 \mathrm { k w } / \mathrm { m } ^ { 2 } }$ 的情况下，若用传统软件对该建筑进行人员疏散安全性的评估：其RSET为97.3s，ASET为56.7s，RSET $\mathrm { > }$ ASET，行人不能安全疏散，如表2所示。

![](images/ea830c3c99f9bf0494c82908d898849d152ac9a0948a30c66a3352662e6bbc7c.jpg)  
图10120时间步时的Pathfinder模拟过程图Fig.10Pathfinder simulation process at 120 time steps

据进行比较，并没有很好考虑到火灾在发展过程中对人员疏散路径和疏散行为的动态影响。此外，虽然文献[12]也构建了基于元胞自动机的火灾疏散模型并考虑了火源对行人的排斥作用，但该模型对火焰蔓延的设置过于理想化(Moore邻域随机扩散)且没有考虑到烟气扩散和温度变化对行人疏散的影响。在本文提出的基于FDS和元胞自动机动态耦合的火灾疏散模型中，火灾造成的灾害因子通过影响综合场值从而影响了行人的路径和出口选择行为，该模型不仅能够判断行人是否能安全疏散，同时还能够确定行人最早处于危险状态的位置和时间，并用可视化的方式表现出来。本文模型与文献[12]模型的具体对比如表3所示。

![](images/26cd634eb2cc1165f523bdb5a6fcfbf11d1de39d8b3bfaa7f4321083275f4653.jpg)  
图11Pathfinder与本文模型疏散人数随时间的变化对比 Fig. 11 Comparison of changes of evacuation number with time between Pathfinderand this model   
图12120 时间步时的Pathfinder行人速度分布图  
Fig.12Pathfinder pedestrian speed distribution at 120 time steps表2传统软件的疏散安全性评估结果

但该评估方法只是将两种软件分别运行，对所得到的数..

Tab.2Evacuation safety evaluation results of traditional software   
表3本文模型与文献[12]模型的具体对比  

<html><body><table><tr><td>灾害因子</td><td>标准</td><td>致灾时间</td><td>ASET</td><td>RSET</td><td>安全性</td></tr><tr><td>走廊能见度</td><td><5m</td><td>56.7s</td><td></td><td></td><td></td></tr><tr><td>烟气层高度</td><td><1.5m</td><td>-</td><td></td><td></td><td></td></tr><tr><td>左出口温度</td><td>>65℃</td><td>30.9s</td><td>56.7s</td><td>97.3s</td><td>危险</td></tr><tr><td>右出口温度</td><td>>65℃</td><td></td><td></td><td></td><td></td></tr><tr><td>走廊CO 浓度</td><td>>500ppm</td><td></td><td></td><td></td><td></td></tr></table></body></html>

Tab.3The model comparison between this paper and literature [12]   

<html><body><table><tr><td>对比项目</td><td>本文模型</td><td>文献[12]模型</td></tr><tr><td>对出口吸引的考虑</td><td>引入基于 Dijkstra 算法的静态场</td><td>引入基于Dijkstra 算法的出口吸引力</td></tr><tr><td>对行人从众的考虑</td><td>参考KirchnerA等人[1的经典动态场</td><td>根据视野范围各方向行人数量进行计算</td></tr><tr><td>对火源排斥的考虑</td><td>综合反映为温度和烟气浓度对行人的排斥</td><td>引入基于欧氏距离的火灾排斥力</td></tr><tr><td>对温度排斥的考虑</td><td>导入FDS数据，引入温度场</td><td></td></tr><tr><td>对烟气排斥的考虑</td><td>导入FDS数据，引入烟气场</td><td></td></tr><tr><td>对危险状态的考虑</td><td>设置高温和高CO浓度会使行人处于危险状态的规则</td><td></td></tr><tr><td>可视化程度</td><td>实现了火焰蔓延、烟气扩散和行人处于危险状态的可视化</td><td>实现了火焰蔓延的可视化</td></tr></table></body></html>

# 3 结束语

本文为研究火灾下的行人疏散提供了一个新的方法：建立基于FDS和元胞自动机动态耦合的火灾疏散模型后，可应用于不同的建筑场景，通过改变火源位置、燃烧材料、热释放速率和行人密度等参数，找到最不利点下的行人处于危险状态的时间，以评估发生火灾后该建筑中的行人能否安全疏散，为建筑性能化防火设计提供参考。研究表明：

a)火灾导致的高温和烟气会影响行人对出口的选择；随着火灾的发展，相比更短的距离，行人更愿意选择温度和烟气浓度较低的路径和出口。

b)热释放速率越大，行人就会越早处于危险状态，同时处于危险状态的行人也越多。

c)本文提出的模型相比Pathfinder能考虑火灾产生的致灾因子对行人疏散的动态影响，除了能评估行人是否能安全疏散外，还能准确得出行人处于危险状态的位置和时间。

今后在本文提出的耦合模型的基础上既可以加入前人提到的匍匐前进等行为，还可以考虑因火灾导致的行人恐慌心理。此外，可以进一步考虑多高层建筑火灾疏散的建模与分析，同时也可以将行人的预动作时间以及建筑的自动喷水灭火系统等消防性能也考虑在模型中。

# 参考文献：

[1]刘朝峰，许强，贾占超，等．高层住宅建筑火灾应急疏散模拟与策略 研究[J]．灾害学,2022,37(1):1-13.(Liu Chaofeng,Xu Qiang,Jia Zhanchao,et al. Study on simulation and strategy of high-rise residential building fire emergency evacuation [J].Journal of Catastrophology,2022, 37(1):1-13.)   
[2]肖木峰，周西华，白刚，等．基于Pathfinder 的装配式建筑施工安全 应急疏散研究[J]．中国安全生产科学技术,2021,17(07):124-129. (Xiao Mufeng,Zhou Xihua,Bai Gang,et al.Research on Emergency Evacuation ofPrefabricated Building Construction Based on Pathfinder [J].Journal of Safety Science and Technology,2021,17 (07):124-129.)   
[3]马伟伟，王洁，吴茜蒙，等．紧急疏散下的引导员设置与仿真模拟 [J]．安全与环境学报,2017,17(02):625-629.(MaWeiwei,Wang Jie, Wu Qianmeng,et al. Guide seting and simulation under emergency evacuation [J]. Journal of safety and environment,2017,17 (O2): 625- 629.)   
[4]颜春萍，颜向农.FDS+Evac 人员疏散模拟软件的理论探析与实战技 巧[J]．消防技术与产品信息,2008(07):8-12.(Yan Chunping,Yan Xiangnong.Theoretical Analysis and Practical Skills of FDS+Evac Evacuation Simulation Software [J].Fire Technology and Product Information,2008 (07): 8-12.)   
[5]邹馨捷，萨木哈尔·波拉提，郝明，等．基于Pyrosim 和 Pathfinder 的 高校学生宿舍火灾人员疏散安全性模拟分析[J].安全与环境工程, 2020,27 (04):195-200.(Zou Xinjie, Samuhar Polati,Hao Ming,et al. Analysis of evacuation safety of dormitory fire based on Pyrosim and Pathfinder [J]. Safety and environmental engineering,2020,27 (04): 195-200.)   
[6]王付宇，王骏．突发事件情景下地铁站人员应急疏散问题综述[J]. 计算机应用研究,2018,35(10):2888-2893.(Wang Fuyu,Wang Jun. Summary of emergency evacuation of subway station personnel in emergency situations [J].Application Research of Computers,2018,35 (10):2888-2893.)   
[7]Zheng Ying,Li Xingang,Zhu Nuo,et al. Evacuation dynamics with smoking diffusion in three dimension based on an extended Floor-Field model[J].Physica A: Statistical Mechanics and its Applications,2018, 507, 414-426.   
[8]Zheng Ying,Jia Bin,Li Xingang,etal.Evacuation dynamics considering pedestrians'movement behavior change with fire and smoke spreading [J]. Safety Science,2017,92,180-189.   
[9] ZhengYing，Li Xingang，Jia Bin，et al.Simulationof pedestrians'evacuation dynamics with underground flood spreading based on cellular automaton [J]. Simulation Modelling Practice and Theory,2019,94,149-161.   
[10]金泽人，阮欣，李越．基于元胞自动机的火灾场景行人流疏散仿真 研究[J].同济大学学报（自然科学版），2018,46(08):1026-1034. (Jin Zeren，Ruan Xin，Li Yue.Simulation research on pedestrian evacuation in fire scene based on cellular automata [J]. Journal of Tongji University (Natural Science),2018,46 (08): 1026-1034.)   
[11]萨木哈尔·波拉提，邹馨捷，郝明，等．基于元胞自动机的人员疏散 模型探讨[J].安全与环境工程,2020,27(05):122-127.(Samuhar Polati,Zou Xinjie,Hao Ming,et al. Discusson on evacuation model based on celular automata[J]. Safety and environmental enginering, 2020,27 (05):122-127.)   
[12]江雨燕，刘军．基于元胞自动机的普通超市火灾疏散模型的构建 [J].计算机应用研究,2019,36(11):3330-3333.(Jiang Yuyan,Liu Jun. Construction of an ordinary supermarket fire evacuation model based on cellular automata,Application research of computers [J].2019,36 (11): 3330-3333.)   
[13]陈长坤，孙华锴，童蕴贺，等．基于元胞自动机的火源威胁下人员疏 散模型[J]．中国安全生产科学技术，2020,16(10):47-52.(Chen Changkun,Sun Huakai,Tong Yunhe,et al.Evacuation model under fire source threat based on cellular automata [J]. Journal of safety science and technology,2020,16 (10): 47-52.)   
[14] Cao Shuchao,Song Weiguo，Liu Xiaodong，et al.Simulation of Pedestrian Evacuation in a Room under Fire Emergency [J].Procedia Engineering,2014,71: 403-409.   
[15]王明年，田源，于丽，等．城市综合管廊电缆火灾数值模拟及影响因 素分析[J]．中国安全生产科学技术,2018,14(1):52-57.(Wang Mingnian,Tian Yuan,Yu Li,et al.Numerical simulation and influence factors analysis of cable fire in urban comprehensive pipe corridor [J]. China safety science and technology,2018,14 (11): 52-57.)   
[16] Kirchner A, SchadschneiderA. Simulation of evacuation proceses using a bionics-inspired cellular automaton model for pedestrian dynamics [J]. Physica A:Statistical Mechanics and its Applications,20o2,312(1): 260-276.   
[17]许镇，唐方勤，任爱珠．建筑火灾烟气危害评价模型及应用[J].消 防科学与技术,2010,29 (08): 651-655.(Xu Zhen,Tang Fangqin,Ren Aizhu.Building smoke hazard assessment model and its application [J]. Fire science and technology,2010,29 (08): 651-655.)   
[18]王大鹏，刘松涛．火灾环境下空间能见度的计算与模拟[J].建筑科 学,2010,26 (09):71-74.(Wang Dapeng,Liu Songtao.Calculation and simulation of spatial visibility in fire environment [J]. Building science, 2010,26 (09): 71-74.)   
[19]黎强，刘清辉，张慧，等．火灾烟气中有毒气体的体积分数分布与危 害[J]．自然灾害学报，2003(03):69-74.(Li Qiang,Liu Qinghui, Zhang Hui,et al. Volume fraction distribution and harm of toxic gases in fire smoke [J].Journal of Natural Disasters,20o3 (O3): 69-74.)   
[20] GUNNARH,MichaelA.The initial convective flow in fire[J].Elsevier, 1989,15 (6): 471-475.   
[21]翟越，薄杰，侯亚楠，等．考虑多因素的元胞自动机室内人员疏散模 拟研究[J].灾害学,2020,35(04):72-76.(ZhaiYue,BoJie,Hou Yanan, et al.Research on indoor evacuation simulation of cellular automata considering multiple factors [J].Journal of Catastrophology,2020,35 (04): 72-76.)   
[22]黄昕，靳健，林作忠，等．基于A\*算法的深部地下空间火灾疏散路 径动态规划[J]．北京工业大学学报,2021,47(07):702-709.(Huang Xin, Jin Jian,Lin Zuozhong,et al. Dynamic fire evacuation path planning in deep underground space based on $\mathbf { A } ^ { * }$ algorithm[J]. Journal of Beijing Universityof Technology,2021,47 (07): 702-709.)