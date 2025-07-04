# 风电场接地系统辅助设计软件的研发

邓少平康慨熊力曲名新翟学王羽（湖北省电力勘测设计院有限公司武汉430040）

![](images/892b9a6380c10fefd8600a17efb7e19dd175ad64a0fde43a99a999c18fba363e.jpg)

邓少平男 1967年生，本科，高级工程师，主要从事电厂电气设计研究工作。

摘要：风电场的接地不但要满足工频短路电流，还要满足雷电冲击的要求。如果风电场的接地装置设计存在缺陷，会造成系统振荡、设备烧毁、全场停运甚至人员伤亡等严重后果。发变电站接地系统的参数评估是电力系统设计的重要环节，进行准确细致的接地网参数仿真计算是非常重要的。本文开发的风电场接地设计软件主要采用数值计算方法，能够较为全面地考虑实际影响因素，为风力发电场的设计、建设和运行提供有效的帮助。

关键词：高土壤电阻率风电场接地设计软件参数仿真数值计算法中图分类号：TM614

# Development of the Computer Aided Design Software of Wind Power Grounding Systems

![](images/394b913e082c392099834d064870c24da952ca54d4551504811a7e0f3513c112.jpg)

Deng Shaoping Kang Kai Xiong Li Qu Mingxin Zhai XueWang Yu （PowerChina Hubei Electrical Engineering CorporationWuhan 430040 China ）

康慨男1987年生，硕士，主要从事新能源发电及微电网研究工作。

Abstract: The grounding of wind farm should not only meet the demand of power frequency short-circuit current, but also meet the requirements of lightning impulse current.If there are defects in the design of the grounding device of the wind farm, it will result in the consequences of system shock,equipment burning,the suspension of the whole field and even personnel injury. The parameter evaluation of the grounding system of the transformer substation is an im-portant part of the design of power system,and it is very important to carry out accurate and detailed simulation calculation of grounding grid parameters.The wind farm earthing design software developed in this paper mainly adopts numerical calculation method,which can consider the influence factors in the actual situation more com-prehensively and provide the help for the design,construction, and operation of wind farm.

Keywords: High soil resistivity, wind power plant, earthing design software, parameter simulation,numerical calcula-tion method

# 1 引言

风力发电作为新能源的重要组成部分，近年来得到迅速发展，根据国家“十三五”规划，到2020年，风电规模将达到2.1亿kW以上，虽然我国的风力发电发展迅速，但对于高土壤电阻下的风电场接地问题一直缺乏有效的解决办法[1]。目前国内风力发电场接地电阻一般按如下要求进行：根据《GB51096—2015风力发电场设计规范》，风力发电机组的接地电阻不应大于 $4 \Omega ^ { [ 2 ] }$ 。根据中国船级社《风力发电机组规范》中规定，其工频接地电阻一般应小于4Ω，在土壤电阻率很大的地方可放宽到 $1 0 \Omega$ 以下。

本文通过研发一套风力发电场专用设计软件，可精确计算风力发电场接地系统相关参数，通过计算在高土壤电阻率下风电场的不同接地方案，并对方案进行技术经济对比，得出最优的接地设计方案，为风力发电场工程接地设计提供技术支撑。

接地系统接地参数的计算方法可以分为两类，一类是采用理论公式进行简单的估算（简称公式法)，另一类则是采用数值计算方法进行比较精确的计算（简称数值法）[3]。由于公式法运用了等效简化的处理，采用公式法计算发变电站接地系统接地参数必然存在一定的误差。过度的简化在一些情况下甚至会产生较大的误差，这是公式法最大的缺点。随着接地理论方面取得的最新突破、计算机硬件性能大幅的提升和数值计算技术的发展，各国学者将各种数值计算方法应用到接地参数的数值计算中来，如有限差分法、有限元法、模拟电荷法、边界元法和矩量法等[4]。相比于公式法，数值计算法能够较好地模拟实际情况，使得计算结果更为准确，因此，本文基于数值计算法来进行风电场接地软件的设计。

# 2 风电场接地算法简介

根据文献[5-6]，采用数值计算方法，能够比较全面地考虑公式法不能处理的因素，如： $\textcircled{1}$ 复杂的土壤模型，如层状土壤（常见的站址土壤模型）或块状土壤(水电站模型)，或者层状块状组合的土壤。 $\textcircled{2}$ 接地网的实际形状和结构及故障电流流散时的实际情况，即考虑到接地网不同部分导体散流的不均匀性，满足任意复杂形状接地网的接地计算要求。$\textcircled{3}$ 复杂的不对称接地故障电流分布和最大入地电流的计算。 $\textcircled{4}$ 考虑接地导体的内存阻抗和导体间的互感，以及入地电流在接地系统上注入的位置。 $\textcircled{5}$ 瞬态电流激励的情况。 $\textcircled{6}$ 最大跨步电位差和接触电位差模式识别。 $\textcircled{7}$ 空间电位、电场和电流密度分布的分析计算。 $\textcircled{8}$ 接地系统的优化设计。 $\textcircled{9}$ 其他的情况。

根据文献[7-8]，风力发电场的接地参数包括接地阻抗、接触电位差、跨步电位差、网孔电位差及接地网上面的地表面电位分布等。接地网参数计算一般需要考虑以下三要素： $\textcircled{1}$ 接地系统本体，即接地导体的材料特性、截面形状和尺寸，接地系统的形状、尺寸、埋深及接地导体布置图。 $\textcircled{2}$ 接地系统所处大范围土壤的电阻率分布特性，如10倍于接地系统尺寸广度和深度土壤电阻率分层/分块的情况。$\textcircled{3}$ 注入/流出接地系统电流源的特性，如电流源的频率、幅值及波形等。

接地网参数计算三要素的数值法求解体系是比较复杂的[9-10]，本文只讨论接地系统本体的数值处理/求解方法，并不涉及土壤电阻率和电流源的数值法。另外，本文并不讨论冲击接地问题，故接地系统本体的数值计算方法是基于恒流场的理论而展开，即当直流或交流电流流经接地系统时，任一点的电位满足泊松/拉普拉斯方程。通过将组成接地系统的导体进行剖分离散化处理，从而使计算空间电位的复杂积分变为求和的形式。通过计算各剖分后得到支路的自电阻和互电阻来求得接地网的泄流电流分布，从而得到空间内任意点的电位。接地系统本体的数值处理/求解方法主要在于求解电阻系数与沿接地系统泄流电流分布，其计算精度、计算繁杂程度、计算时间的长短及占用计算机内存是数值法研究的对象。目前随着硬件技术的发展，计算机的运算速度及内存的大小已经不再是阻碍数值法应用的因素，数值法应从计算精度、与实际情况的吻合程度等方面进行改进。如考虑接地网所处土壤的分层／分块的情况，而不是只对采用等值电阻率的均匀土壤结构进行分析。

# 3接地仿真方法

接地系统本体数值法的第一步，就是对接地系统进行剖分离散化，即剖分接地系统为多个节点和支路的集合，微观的支路模型如图1所示。

![](images/e4cacc89909e02957de5c9a5d6b586d0758aef69859c93bc89222aa83aaef61c.jpg)  
图1接地支路模型示意图  
Fig.1Schematic diagram of ground branch model

图1中支路1连接2个节点 $N _ { 1 }$ 和 $N _ { 2 }$ ，流入和流出节点的电流分别为 $I _ { \mathrm { N 1 } }$ 和 $I _ { \mathrm { N } 2 }$ 。支路上微元 $\mathrm { d } l$ 上导通电流和散流电流分别为 $C ( l )$ 和 $S ( l )$ 。在接地参数分析中，均匀土壤为半无限大各向同性的媒质，一般采用导电率或电阻率来表示其性能。接地系统的局部范围与交流 $5 0 \mathrm { { H z } }$ 或 $6 0 \mathrm { H z }$ 工频电流的透入深度相比要小得多，因此可以忽略传播时间，在交流或直流情况下接地系统特性可以基于恒定电流场理论进行分析。如果电流流入埋设在地中的接地装置，根据恒定电流场理论，以无限远点为参考点，应用格林函数的原理可以得到电极泄流电流在任意一点$p$ 产生的电位 $\boldsymbol { V } _ { \mathrm { p } }$ 为

$$
V _ { \mathfrak { p } } = \int _ { l } S ( l ) G ( p , l ) \mathrm { d } l
$$

式中， $G$ 为格林函数，对均匀土壤，有 $G =$ 土壤电阻率 $/ ( 4 \pi ) \times [ 1 / ( p$ 与 $l$ 的距离） $+ ~ 1 / ( p$ 与 $l$ 镜像的距离）。补充一点，对于其他不均匀土壤的情况，如果格林函数 $G$ 可以理论上导出，则本文后面方法也适用于该种不均匀土壤，若格林函数 $G$ 理论上无解析解，则需要使用更复杂的方法进行求解，感兴趣的读者可查阅相关文献。

剖分后，接地系统细分为足够稠密的支路集合$\pmb { R }$ 。足够稠密的意义在于， $\pmb { R }$ 中所有支路均可以近似为 $S ( l )$ 处处相等。支路导体的两个端点的集合称为节点 $N$ 。剖分后接地网的等效模型由 $\boldsymbol { r }$ 根支路和$n$ 个节点构成。如某地网的模型示意图如图2所示。

![](images/c609c27b9eed458547f3ffd64742739929d552b073c8fa85cecdbd1ec5043bfb.jpg)  
图2地网模型示意图  
Fig.2Schematic diagram of ground network model

定义编号 $j$ 的节点电压 $V ( j )$ 是 $j$ 号节点的电位。由于支路导体足够稠密，近似认为第 $k$ 支路电压$U ( k )$ 恒定为两端点电位平均值，有

$$
U ( k ) = { \frac { V ( m ) + V ( n ) } { 2 } }
$$

式中， $\mathbf { \nabla } _ { m }$ 和 $n$ 为 $k$ 号支路两端点的编号。写成矩阵形式有

$$
U = K V
$$

式中， $\pmb { U }$ 为支路电压列向量； $\boldsymbol { V }$ 为节点电压列向量； $\pmb { K }$ 为支路－节点关联矩阵，当支路 $i$ 与节点 $j$ 相连时 有 $\pmb { K } ( i , j ) = 0 . 5$ ，否则为0。

考虑所有的支路电压和支路散流电流 $\boldsymbol { \mathsf { I } }$ 有

$$
\pmb { I } = \pmb { S } \pmb { U } = \pmb { H } ^ { - 1 } \pmb { U }
$$

式中， $s$ 为支路散流阵； $H$ 为支路的互电阻矩阵。 对于 $H$ 有

$$
H ( i , j ) = \int _ { l _ { i } \in R } \int _ { l _ { j } \in R } G ( l _ { i } , l _ { j } ) \mathrm { d } l _ { i } \mathrm { d } l _ { j }
$$

令支路散流电流 $\boldsymbol { { \cal I } }$ 分成两部分，等分到与之相连的节点有

$$
J ( b ) = \sum _ { i = 1 } ^ { r } c _ { i , b } { \frac { I ( i ) } { 2 } }
$$

式中， $\mathbf { \nabla } \ J ( \boldsymbol { b } )$ 为 $b$ 号节点的散流电流；如果节点 $k$ 与支路 $i$ 相连， ${ c _ { i , b } } = 1$ ，否则等于零。写成矩阵形式有

$$
{ \boldsymbol { J } } = { \boldsymbol { K } } { \boldsymbol { I } } 
$$

式中， $J$ 为节点散流电流列向量； $\pmb { K } ^ { \prime }$ 是 $\kappa$ 的转置。

运用电流守衡定律有

$$
F - J = Y V
$$

式中， $F$ 为故障入地电流列向量； $Y$ 为节点导纳矩阵。综合，有

$$
\pmb { F } = ( \pmb { K } ^ { \prime } \pmb { S } \pmb { K } + \pmb { Y } ) \pmb { V }
$$

接地网的节点导纳矩阵 $Y$ 求解公式为

$$
\pmb { Y } = \pmb { A } \pmb { Z } ^ { - 1 } \pmb { A } ^ { \prime }
$$

式中， $A$ 为关联矩阵，当支路 $k$ 和节点 $j$ 关联且它的方向背离节点，则 $A ( j , k ) = 1$ ，当支路 $k$ 和节点 $j$ 关联并且它的方向指向节点，则 $A ( j , k ) = - 1$ ，否则是零； $\mathbf { \mathcal { A } ^ { \prime } }$ 是 $A$ 的转置矩阵； $z$ 为接地网导体的支路阻抗矩阵，其元素为

$$
\pmb { Z } ( i , i ) = z \ d ( i ) \quad \pmb { Z } ( i , j ) = \mathrm { j } \omega \pmb { M } ( i , j ) \quad i \neq j
$$

式中， $M$ 为导体的外自感阵； $\boldsymbol { M } ( i , j )$ 为导体 $i$ 和导体 $j$ 间的互感； $z$ 为导体内自阻抗向量，第 $i$ 段圆柱导体的内自阻抗 $\it { z } ( i )$ 可表示为

$$
z \left( i \right) = \frac { \mathrm { j } \omega \mu _ { \mathrm { { c } } } } { 2 \pi a \sqrt { \mathrm { j } \omega \mu _ { \mathrm { { c } } } \sigma _ { \mathrm { { c } } } } } \frac { I _ { 0 } \left( a \sqrt { \mathrm { j } \omega \mu _ { \mathrm { { c } } } \sigma _ { \mathrm { { c } } } } \right) } { I _ { 1 } \left( a \sqrt { \mathrm { j } \omega \mu _ { \mathrm { { c } } } \sigma _ { \mathrm { { c } } } } \right) }
$$

式中， $\mu _ { \mathrm { c } }$ 和 $\sigma _ { \mathrm { c } }$ 分别为导体 $i$ 的磁导率和电导率； $\mathbf { \nabla } _ { a }$ 为圆柱导体的半径； $I _ { 0 }$ 和 $I _ { 1 }$ 分别为修正的第一类零阶和一阶贝塞尔函数。

根据电磁场理论，导体间的互感 $\boldsymbol { M } ( i , j )$ 的表达式如下

$$
\begin{array} { l } { { \displaystyle M ( i , j ) = \frac { \mu _ { _ 0 } } { 4 \pi } \int _ { l _ { i } \in { \cal R } } \int _ { l _ { j } \in { \cal R } } \frac { 1 } { r } \mathrm { d } \vec { l } _ { i } \mathrm { d } \vec { l } _ { j } } } \\ { { \displaystyle \ \quad = \frac { \mu _ { _ 0 } } { 4 \pi } \int _ { l _ { i } \in { \cal R } } \int _ { l _ { j } \in { \cal R } } \frac { 1 } { r } \mathrm { d } l _ { i } \mathrm { d } l _ { j } \cos \theta _ { _ { i , j } } } } \end{array}
$$

式中， $\theta _ { i , j }$ 为导体 $i$ 和导体 $j$ 之间的夹角。

由于注入节点电流向量 $F$ 已知，通过式 (9)就可以很方便地求出节点电压向量 $V$ ，然后相应求出支路电压向量 $\textbf {  { U } }$ 和支路散流电流向量 $I$ ，这样接地网的等效接地阻抗 $Z _ { \mathrm { g } }$ 和地表电位分布 $\lvert V _ { \mathrm { p } }$ 等问题都可以解决。

$$
V = ( K ^ { \prime } S K + Y ) ^ { - 1 } F
$$

$$
Z _ { \mathrm { g } } = { \frac { \operatorname* { m a x } { ( V ) } } { \displaystyle \sum F } }
$$

$$
\pmb { I } = \pmb { S U } = \pmb { S K V }
$$

$$
V _ { _ { \bf p } } = \int _ { \mathrm { \Lambda } _ { l \in R } } S ( l ) G ( { \bf \omega } { p } , l ) \mathrm { d } l = I H _ { _ { \bf p } }
$$

式中， $\boldsymbol { H _ { \mathrm { p } } }$ 为支路与观测点的互阻阵， $\pmb { H } _ { \mathrm { p } }$ 元素的计算公式与式(1)相同。

# 4 软件开发

风电场接地辅助设计软件架构如图3所示。按软件的设计思路，软件分为DXF风电场接地系统CAD数据导入模块、前处理模块（风电场土壤电阻率测试数据处理和反演模块、接地数值计算模块(接地电阻计算、地表电位/跨步电位差/接触电位差分析模块、降阻方案分析）和后处理模块（地表电位/跨步电位差/接触电位差可视化、接地计算结果综合和报告自动生成）。

DXF数据接口模块 接地系统CAD编辑模块土壤测量数据处理模块 土壤测量数据反演模块接地数值分析模块 跨步/接触电位差分析风电场接地计算结果 自动生成接地计算报告

该软件的最大特色是专门针对风电场接地系统的计算机辅助建模计算，最大限度地减轻接地设计人员的工作量。另外，该软件可以支持复杂的工况，避免使用简化公式的计算误差。下面就各个模块开展介绍。

# 4.1DXF风电场接地数据导入模块

接地设计往往是使用AUTOCAD一类的软件进行制图。图4是某风电场的接地系统CAD图纸。软件的数据导入模块能够导入图4的数据，从而大大降低接地系统建模的工作量。需要注意的是，图4的风电场接地系统DXF格式图纸是二维形式，并不能直接用于三维的接地系统建模，需要在导入二维数据后进行接地体埋深的人工编辑。最后，接地软件还需要额外指定不同部件导体参数，如材料特性、导体截面积等，为进行下一步的计算做准备。图5给出了软件的CAD界面，显示的接地系统为图4所示的风电场接地系统模型（该风电场位于湖北宜昌)。

![](images/1980ceba0178332532dc65685f52a39d089e2c038a7df22fc0732a1e7275e58c.jpg)  
图3风电场接地辅助设计软件的架构 Fig.3The architecture of grounding auxiliary design software forwind farm   
图4某风电场接地系统的CAD图纸  
Fig.4CAD drawing of the ground system of a wind farm

软件还提供了编辑导体几何参数的功能，方便用户进行更精细化的建模；增加了导体连接缺陷的容错功能，修复了CAD数据中导体无法精确连接的问题。

![](images/1b2753cd949a32da185caf9ecd064ac1e5999ef42f51949c8f1f793c5a1e2f30.jpg)  
图5图4接地系统在风电场接地系统辅助设计软件中显示的三维模型图  
图7风电场接地辅助设计软件的导体剖分网格 Fig.7Conductor mesh of the grounding auxiliary design software for wind farm

# 4.2土壤参数反演模块

风电场大地电阻率的测量使用电力系统传统的等距四极法进行。由于规程没有提供反演计算的方法，现场测量的大地电阻率往往被等效成均匀土壤的形式，这无疑与风电场场址复杂的大地参数相违背。软件的土壤参数反演模块就是为解决这一不足而开发的，如图6所示，通过对不同极距对应的视电阻率的反演，可以得到反演方均根误差最小的层状大地参数，这将大大地保证计算结果的准确度。

![](images/4848cc54d6e6001f5cd694fb225054851d7332af8fc9e242af9fe4ed40f19526.jpg)  
Fig.5The 3D model diagram of the grounding system in Fig.4 in the groundingauxiliary design software for wind farm   
图6风电场接地辅助设计软件的土壤反演模块 Fig.6Soil inversion module of the grounding auxiliary design software for wind farm

# 4.3接地计算模块

由于风电场的接地系统几何结构复杂，若简化为简单的几何模型，其接地参数计算误差将会超过工程允许值，给风电场的安全运行带来风险。软件的接地计算模块采取的是精确的接地仿真方法，即：第一步，接地体的网格剖分，示意图如图7所示；

GroundingCAD-[机组10与13.F4GCAD] X  
文件编辑(E）CAD士壤接地网电流计算 外延后处理显示视图（V窗口W帮助（H）测试  
D&喝电？  
单节点数量：349 82 85//183- 10403 √C1R4 77185 1389315317 28147 115 28 1922 23923827 325 28232327597 98042423272243/284122927132 /244/285 31 13799 1452872222 231  
.56 148 10100 11 /24288 3026 230 288 88 190328 3222291福 330 455 320,118 2720128/27334333 31 3003392303 341 130-300 34813132  
就绪 GCAD2017aby湖北省电力勘测设计院

第二步，散流导纳和导通导纳的计算(见式9)；第三步，人体安全（最大跨步电位差和最大接触电位差）的计算和检验。

# 4.4后处理模块

软件运行完毕后，将自动生成Word格式的计算结果，无需人工编写计算结果报告，大大提高了接地设计人员的办公效率。

# 4.5软件的应用与验证

对图4所示的湖北某风电场机组的场址进行大地电阻率的测量，结果见表1。运行软件的土壤参数反演模块，得到图6所示的双层大地参数，结果见表2，反演方均根误差为 $1 1 . 3 1 \%$ 。使用商用接地软件CDEGS的RESAP模块进行反演，方均根误差为 $1 1 . 6 8 \%$ ，结果如图8所示。两者结果相近，可见本文开发的软件在土壤参数反演方面是具有较高精度的。

表1大地电阻率的测量结果  
Tab.1 The measurement results of earth resistivity   

<html><body><table><tr><td>极距/m</td><td>视在电阻/Ω·m</td></tr><tr><td>1.00</td><td>183.67</td></tr><tr><td>2.00</td><td>231.21</td></tr><tr><td>3.00</td><td>244.52</td></tr><tr><td>5.00</td><td>416.87</td></tr><tr><td>7.00</td><td>739.43</td></tr><tr><td>10.00</td><td>960.76</td></tr><tr><td>20.00</td><td>1 318.14</td></tr><tr><td>30.00</td><td>1 976.39</td></tr></table></body></html>

CDEGS具有DXF图纸的导入功能，但结果并

# 表2水平双层大地的反演结果 (软件)

Tab.2Inversion results of horizontal double layer earth (by software)   

<html><body><table><tr><td>编号</td><td>厚度/m</td><td>电阻率/Ω·m</td></tr><tr><td>第一层</td><td>2.54</td><td>172.84</td></tr><tr><td>第二层</td><td>8</td><td>5 660.1</td></tr></table></body></html>

![](images/5877a9b533690bdced77ff0dc9ce4721fc84e85b402627e0721d30ad277e9739.jpg)  
图8CDEGS的土壤参数反演结果

不理想，示意图如图9所示。可见，商用接地软件在导入复杂风电场图纸的时候可能会出现问题，导入的导体信息并不完整。为了与本文的软件进行对比，本文软件导出了正确的几何数据，并输入到CDEGS中，再对两个软件进行接地参数计算结果的对比。

![](images/11f15610ea697794b92e5a8b2f366ae8649b5f6cd3d1a42ead0613be03ea0206.jpg)  
Fig.8Soil parameter inversion results of CDEGS   
图9CDEGS导入的图4所示的DXF图纸 Fig.9The DXF drawing of Fig.4 imported by CDEGS

以图4为例，软件计算出风电场接地电阻为

$9 . 6 5 \Omega$ ，CDEGS软件的计算结果为 $9 . 7 2 \Omega$ ，现场的测量值为 $9 . 3 \Omega$ 。对比表明，本文开发的软件所得风电场接地电阻值与CDEGS计算结果和实测值相近，其误差小，说明结果准确可靠。相比于国外的商用软件，本文开发的软件专门针对风电场接地，操作更灵活方便，更适用于我国风电场接地设计。另外，风电场接地辅助设计软件的可视化功能也是非常强大的，地表电位可视化示意图如图10所示。通过强大的可视化功能，设计人员可以方便地判断最大跨步电位差和最大接触电位差的位置，做到对跨步电位差和接触电位差的超标区域准确敷设高阻层，以保证人身安全。

![](images/20dcc27e5ce42abfa3418a773370e28c8785dd619d9b01d1240120c6f98088fd.jpg)  
地表电位、接触/跨步电压差三维可视化软件UN凸自出乡·，用，%，，哦。加中中xq四@□□  
图10风电场接地辅助设计软件的地表电位可视化功能 Fig.10Surface potential visualization of the grounding auxiliary design software for wind farm

# 5 结论

接地系统是风力发电场的重要组成部分，是维护系统安全可靠运行、保障运行人员和电气设备安全的根本保证和重要措施。当高压设备发生接地短路故障时，接地系统必须为故障电流提供可靠的回流路径。风力发电场接地装置对于保证电力系统安全运行起着至关重要的作用。随着我国风力发电的迅猛发展，对系统安全、稳定及经济运行的要求越来越高。为了确保风电场的安全稳定运行，提高供电可靠性，风电场需要有一个良好的接地装置，保证风力发电场接地电阻、跨步电压、接触电势等参数满足规程规范的要求。

本文所开发的风电场接地设计软件界面友好，操作简单，运行可靠，计算中可考虑多种因素，实用性强，可结合工程实际情况仿真模拟不同的风力发电场接地网设计模型，得出技术经济最优的方案，特别对高土壤电阻率下的风电场接地具有较强的工程应用价值。

# 参考文献

[1] 张柯林．变电站地网接地电阻的数值计算及改造技术的研究[D]．华中科技大学，2007.  
[2] GB 51096—2015风力发电场设计规范[S].  
[3] 林峰，张兰英，吕庭钦，等．风电场接地变及其中性点接地电阻的改进方案分析[J]．电网与清洁能源，2015，31(2)：126-130，134.Lin Feng, Zhang Lanying,Lv Tingqin, et al. Analysison improvement scheme of grounding resistance ofwind farm grounding transformer and its neutral[J].Power Grid & Clean Energy,2015,31(2):126-130,134.  
[4] 郭小斌，叶漫红．高土壤电阻率沙地风电场的接地研究[J]．电力勘测设计，2013(5)：72-75，80.Guo Xiaobin,Ye Manhong. Study on groundingof wind farm in high soil resistivity sandy land[J].Electric Power Survey & Design,2013(5):72-75,80.  
[5] 滕明尧.风电场 $3 5 \mathrm { k V }$ 系统接地研究[J].电子世界,2013(6):63-64.Teng Mingyao.Study on $3 5 \mathrm { k V }$ system grounding ofwind farm[J].Electronic World, 2013(6): 63-64.  
[6] 陈亮，白勇．风电场接地电阻选择设计[J]．电气制造，2013(2)：54-57.Chen Liang,Bai Yong.Design of groundingeesistance selection for wind farm[J].ElectricalManufacturing,2013(2): 54-57.  
[7] 刘阳．山区风电场接地设计方案分析[J]．林业科技情报，2010，42(4)：50-52.Liu Yang.Analysis of mountainous wind farmgrounding design scheme[J]. Forestry Science andTechnology Information, 2010, 42(4): 50-52.  
[8] 石巍，王秋红．风电场接地设计[J]．电气制造,2010(9): 48-49，66.Shi Wei, Wang Qiuhong. Wind farm groundingdesign[J].Electrical Manufacturing,2010(9):48-49,66.  
[9] 周静增.风电场风电机组的接地设计[J].能源工程,2010(3): 41-43.Zhou Jingzeng. Grounding design of wind turbine inwind farm[J].Energy Engineering,2010(3):41-43.  
[10] 郭继红，郭宝海．大型风电场集电网系统接地方式探讨[J]．水利水电工程设计，2009，28(3)：38-40.Guo Jihong,Guo Baohai. Discussion on groundingmode of large scale wind farm integrated power gridsystem[J]. Hydraulic and Hydroelectric EngineeringDesign,2009,28(3): 38-40.