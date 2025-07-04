# 3D打印进程中曲率对直立墙结构力学的影响

刘轩廷1,t) 孙博华\*+)

1(西安建筑科技大学理学院,西安710055)\*(西安建筑科技大学土木工程学院,西安710055)(西安建筑科技大学力学技术研究院，西安710055)

摘要对于打印墙结构往往因为稳定性而失效的问题,本文提出了采用直立波纹墙的方法,即适当增加墙体沿轮廓方向的曲率,以求提高打印墙稳定性.本文通过将波纹墙的单个波纹视为单胞进行研究,取曲率为常数,并进行结构闭合处理,以求稳定性最大化,即分析柱壳形直立墙在3D打印进程中的力学性能.此模型利用Goldenveizer-Novozhilov壳体理论,加入打印进程参数,包括打印速率、打印材料固化特征、柱壳几何特征、以及自重作用影响,对圆柱壳的两种破坏机理:弹性屈曲和塑性破坏进行分析.利用Suiker[22 首次提出的无量纲参数ス（暂称Suiker数),对柱壳形直立墙弹性屈曲与塑性破坏间的竞争关系进行描述.将结果与文献[22]进行比较,发现当参数完全相同情况下,将柱壳形直立墙比矩形直墙结果对比发现,稳定性提升了两倍有余.同时给出了通过曲率的改变达到此类参数下柱壳结构稳定性最大化的方法,即通过拟合的手段,得到失效高度随曲率变化函数,据此对失效机制区域进行划分.这表明该模型可用于探讨打印进程中曲率对直墙结构的力学性能影响,并可通过调整参数对结构作出优化.同时,通过引入曲率,将直立墙沿轮廓方向打印成波纹墙,对于提高打印墙结构稳定性是一个简单可行的方案

关键词曲率,柱壳,增材制造,弹性屈曲,塑性破坏

# Analysis of mechanical performances of cylindrical wall in 3D printing processes

LIU Xuan-Ting\*\*†SUN Bo-Hua\*t) 1(School of Science,Xi'an University of Architecture and Technology,Xi'an710o55,China) \*（SchoolofCivil Engineering,Xi'anUniversityofArchitectureand Technology,Xi'an7lOo55,China) +(InstituteofMechanicsandTechnologyXi'an UniversityofArchitectureandTechnology,Xi'an70o55,China)

AbstractIn order to enhance the overallstructural stabilityof 3D printed concrete wall,this paper propose a novel scheme to produce a wavy wall with curvature along its contour direction.To validate the idea of the scheme,a single wave wallis set as a cylindrical wallandits mechanical performances are analyzed.The mathematical 3Dprinting model of the wavywallis formulated by the shellteory while taking into account of additional parameters of the printing proceses,the model will be used toanalyze the two failure mechanisms ofthe cylindrical wall:elastic bucklingand plastic colapse.Compared with theresults of Suiker's straight wall,it is found that when the parameters were same,the stabilityof thecylindrical wallis more thantwiceof the rectangular wall.Our studies indicate thatit'safeasible scheme to improve the printed structural stability by increasing curvature.

Key words curvature ,cylindrical wall, 3D printing, elastic buckling, plastic collapse

# 引言

3D打印的概念是由CharlesHull于20世纪80年代初提出,其也可以称为增材制造(AM)快速成型(RP),无固体成型(SFF)等.自问世以来至今30余年间，3D打印技术发展尤为迅速，并取得了巨大的成功.其应用包括生物医学工程,车辆工程,机械工程,航空航天工程,食品工程,建筑土木工程等[1-7].术语"增材制造"最终由美国材料协会(ASTM)选择,以与传统"减材制造"相区分，并于2013年将增材制造(AM)技术分为七类:(1)材料挤出、(2)粉末床融合、(3)还原光聚合、(4)材料喷射、(5)粘结剂喷射、(6)片状分层和、(7)定向能量沉积[8].其主要形式是通过建立三维模型数字文件,利用软件将此模型进行切分(精度取决于打印分辨率)最后使用打印设备进行逐层打印成型[9].AM技术相对于传统制造的优点是:能制造复杂几何形状的部件,减少材料浪费,减少能量损耗,增加面对客户的灵活性等[10-11].

Bourell等65人[12]于2009年开展了关于AM技术发展规划研讨会,探讨了关于AM技术发展的重要方面,包括：设计,过程建模与控制,材料、打印进程与打印机器,生物医学应用,能源及可持续发展.关于增材制造(AM）的多元化发展,BehrokhKhoshnevis提出“轮廓工艺”，即混凝土3D打印技术.此技术由于材料的局限性,经济性等原因,尚未挖掘出其真正潜力,但是在某些极端条件下,有效的弥补了传统建筑的弱项,如在防疫方舱医院的应用,于其他星球建造栖息地等[13-16]．目前就3D打印进程中的力学性能分析相对较少,国内外主要研究集中在材料科学方面[17-21].但由于3D打印进程中所涉及参数的复杂性与多样性，包括打印物体的几何特征,时间效应对材料强度的影响,不均匀的自重载荷，喷头的移动速率，不可避免的几何缺陷,通常来说，打印参数的设定采用试错的方式进行，而针对混凝土构件在打印进程中的力学性能分析的研究更是少之又少.

根据A.S.J.Suiker[22]针对混凝土3D打印进程中的力学性能研究发现,弹性屈曲与塑性破坏是结构破坏的主要机制[23-24].Suiker针对直壁结构3D打印进程中的力学性能进行分析，并首次给出了相应的力学模型,在引入混凝土固化性能与打印参数下,将参数模型结果与试验数据进行对比分析，发现可较好地分析结构在打印进程中的破坏行为,预测直壁结构打印层数,并为找寻最佳打印参数集给予了理论指导.但从其结果发现,矩形布置的墙体结构稳定性仍有不足,即发生结构屈曲而失效,而不是达到材料塑性极限发生破坏.由于稳定性研究对于提升材料利用率,快速成型和增强结构的承载力等方面至关重要。特别是，在不改变打印速度的情况下，使用混凝土等流动性强固化慢的3D打印材料时，如何提高打印墙结构的整体稳定性是个关键科学问题。

为了解决这个问题，我们提出了一个简单可行的普适方案，即适当增加直立墙沿轮廓方向的曲率将直立墙沿轮廓方向打印成波纹形状，打印方案见图1。直立波纹墙每个波纹，其可以是圆柱形也可以不是，同时其曲率也可以变化。为了验证我们的方案，本文对于柱壳形直立墙在3D打印过程中力学性能进行了研究。

小

具体讲，在第2节,推导柱壳的压曲控制方程.在第3节，描述了3D打印进程中柱壳结构可能发生的两种失效机制.第4节,利用数值计算方法得到了两种固化参数影响下的屈曲结果,并使用Suiker数对柱壳墙的两种失效机制间竞争关系进行评判.第5节,采用与文献[22]完全相同的打印参数,对由曲率控制的柱壳结构稳定性和由材料属性控制的塑性极限进行了对比分析.

# 1非均匀内力作用下的非均质柱壳

如图2所示,我们取波纹墙的一个单胞进行分析,其曲率是可以变化的,即 $k = k ( r )$ $r =$ variable.但当我们取曲率为常数，即 $r = c o n s t a n t$ ，并进行结构闭合处理,明显将得到一个结构稳定性与承载力最大化的柱壳形直立墙.

![](images/91b6e9e22b31c0a711fec1d1ac465122212cd7ca567294e03c07dc1bbdd94563.jpg)  
图2:直立墙演化示意图.

在3D打印进程中，柱壳形直立墙会因为材料固化行为影响，在垂直方向呈非均质性.此外,柱壳结构承受的载荷为自重载荷,其应力在垂直方向(自重方向)同样是不均匀的.与之对应的是,需基于平衡方程与边界条件,对此非均匀内力作用下的非均质柱壳的力学模型进行描述.因此,本节通过柱壳的势能最小化原理将其压屈微分方程进行推导.

# 1.1势能

![](images/fa70da51200e869d3eb862c29480ad34961a24adfca9d7b40181bedd2dc29e62.jpg)  
图3：柱壳在自重作用下示意图.

如图3所示，柱壳半径为 $R$ ，高度为 $l$ ,均匀厚度 $h$ .轴对称情况下, $u ( x , \theta ) = u ( x )$ ， $\nu = 0$ $w ( x , \theta ) = w ( x )$ .根 据Goldenveizer-Novozhilov壳体理论,应变位移关系可 以表示为:

$$
\begin{array} { r l r } { \displaystyle \varepsilon _ { x } = u _ { , x } , } & { { } ~ \displaystyle \varepsilon _ { y } = \frac { w } { R } , } & { \displaystyle \varepsilon _ { x y } = 0 , } \\ { \displaystyle \chi _ { x } = - w _ { , x x } , } & { { } ~ \displaystyle \chi _ { y } = 0 , } & { \displaystyle \chi _ { x y } = 0 . } \end{array}
$$

其中 $\begin{array} { r } { u _ { , x } = \frac { d u } { d x } } \end{array}$ $\begin{array} { r } { w _ { , x x } = \frac { d ^ { 2 } w } { d x ^ { 2 } } } \end{array}$ ， $x$ 为纵向坐标, $y$ 为环向坐标,$\varepsilon _ { x } , \varepsilon _ { y } , \varepsilon _ { x y }$ 为壳体中面线性应变分量, $\chi _ { x } , \chi _ { y } , \chi _ { x y }$ 为曲率变化, $u , \nu , \nu$ 分别为纵向,切向,径向位移.

柱壳总应变能 $U$ ，由薄膜应变能 $U _ { s }$ ，与中面拉伸 弯曲应变能 $U _ { b }$ 组成:

$$
U = U _ { s } + U _ { b } ,
$$

其中

$$
U _ { s } = \int \int \frac { E _ { * } h } { 2 ( 1 - \nu ^ { 2 } ) } \left[ \varepsilon _ { x } ^ { 2 } + \varepsilon _ { y } ^ { 2 } + 2 \nu \varepsilon _ { x } \varepsilon _ { y } + \frac { 1 - \nu } { 2 } \varepsilon _ { x y } ^ { 2 } \right] d y d x ,
$$

$$
U _ { b } = \int \int \frac { D _ { * } } { 2 } \left[ \chi _ { x } ^ { 2 } + \chi _ { y } ^ { 2 } + 2 \nu \chi _ { x } \chi _ { y } + 2 ( 1 - \nu ) \chi _ { x y } ^ { 2 } \right] d y d x ,
$$

星号"\*”代表材料参数在空间中是非均匀的(为方便起见，取 $\nu$ 为常数). $E _ { * }$ 为非均匀弹性模量,非均匀弯曲刚度由下式给出：

$$
D _ { * } = \hat { D } _ { * } ( x , y ) = \frac { E _ { * } h ^ { 3 } } { 1 2 ( 1 - \nu ^ { 2 } ) } E _ { * } = \hat { E _ { * } } ( x , y ) .
$$

柱壳屈曲过程中自重所做的功可表示为：

$$
W = \frac { 1 } { 2 } \int \int \rho g h ( x - l ) \left[ ( \frac { \partial \nu } { \partial x } ) ^ { 2 } + ( \frac { \partial w } { \partial x } ) ^ { 2 } \right] d y d x ,
$$

结合公式(2)(6),可以得到总势能 $\pi$ ：

$$
\begin{array} { l } { \Pi = U - W } \\ { = \displaystyle \int \int \displaystyle \int \frac { E _ { * } h } { 2 ( 1 - \gamma ^ { 2 } ) } \Biggl [ \varepsilon _ { x } ^ { 2 } + \varepsilon _ { y } ^ { 2 } + 2 \nu \varepsilon _ { x } \varepsilon _ { y } + \frac { 1 - \nu } { 2 } \varepsilon _ { x y } ^ { 2 } \Biggr ] d y d x } \\ { + \displaystyle \int \int \displaystyle \int \frac { D _ { * } } { 2 } \left[ \chi _ { x } ^ { 2 } + \chi _ { y } ^ { 2 } + 2 \nu \chi _ { x } \chi _ { y } + 2 ( 1 - \nu ) \chi _ { x y } ^ { 2 } \right] d y d x } \\ { - \displaystyle \int \int \displaystyle \frac { 1 } { 2 } \rho g h ( x - l ) \left[ \nu _ { x } ^ { 2 } + w _ { x } ^ { 2 } \right] d y d x . } \end{array}
$$

# 1.2平衡方程与边界条件

将公式(7)进行势能最小化处理,可以得到非均匀内力作用下的非均质柱壳的平衡方程:

$$
\begin{array} { l } { \displaystyle \delta \Pi = \frac 1 2 \int \int D _ { * } \big [ w , _ { x x } \delta w , _ { x x } + w , _ { x y } \delta w , _ { y y } } \\ { \displaystyle \quad + \nu w , _ { x x } \delta w , _ { y y } + \nu w , _ { x y } \delta w , _ { x x } + \frac { 2 ( 1 - \nu ) } { R ^ { 2 } } w , _ { x y } \delta w , _ { x y } \big ] d y d x } \\ { \displaystyle \quad + \frac 1 2 \int \int \frac { E , h } { 1 - \nu ^ { 2 } } [ u , _ { x } \delta u , _ { x } + \frac { 1 } { R ^ { 2 } } w \delta w + \frac { \nu } { R } w \delta u , _ { x } } \\ { \displaystyle \quad + \frac { \nu } { R } u , _ { x } \delta w + \frac { 2 ( 1 - \nu ) } { R ^ { 2 } } u , _ { x } \delta u , _ { x } ] d y d x } \\ { \displaystyle \quad - \frac 1 2 \int \int \rho g h ( x - l ) [ \nu , _ { x } \delta \nu , _ { x } + w , _ { x } \delta w , _ { x } ] d y d x , } \end{array}
$$

当处理柱壳轴对称屈曲问题时.将(1)式带入,进行位移变分可得柱壳压屈微分方程：

$$
( D _ { * } w _ { , x x } ) _ { , x x } + \frac { 1 } { R } \left( \nu \rho { g } h ( x - l ) + \frac { E _ { * } h } { R } w \right) - ( \rho { g } h ( x - l ) w _ { , x } ) _ { , x } = 0 ,
$$

此外,柱壳沿壳边缘 $x = 0$ 和 $x = l$ 的边界条件分别为：

$$
\begin{array} { r l } { w | _ { x = 0 } = 0 , \quad } & { { } w _ { , x } | _ { x = 0 } = 0 , } \\ { w _ { , x x } | _ { x = l } = 0 , \quad } & { { } ( D _ { * } w _ { , x x } ) _ { , x } | _ { x = l } = 0 . } \end{array}
$$

# 23D打印进程中柱壳的失效

![](images/afeba9a0aa86f38a289f0109f732b96856f512f9925c44d77c468682444b0a07.jpg)  
图4：失效机制示意图.

如图4所示,在3D打印进程中可能发生两种失效机制,分别为弹性屈曲和塑性破坏.其中当材料硬化速率比打印速率相对较慢情况下,在结构底部会出现较大变形,文献[29]中试验观测,第一层材料由于受约束变形较小,而第二层在结构塑性破坏情况下,最终厚度将达到第一层两倍以上,可称这种现象为"Elephant foot deformation".这种现象的合理利用,可在一定程度上增强结构稳定性

在本节中建立了这两种失效机制的控制方程.弹性屈曲的控制方程可以由第一节中所导出的压屈微分方程和边界条件所得.引入打印材料固化过程和印刷速度有关的时间效应的影响因素.本节最后给出了弹性屈曲与塑性破坏的竞争标准

![](images/b7df01c7b3abf6d5f7edf0373c126793c23b0879a9aaf43f59bbb856edc620f1.jpg)  
打印时间因素对柱壳的屈曲影响  
图5：柱壳打印过程示意图

,底部为拉格朗日坐标系 $x ,$ ，打印喷头处为欧拉坐标系 $X$

由于柱壳体长度 $l$ 随打印进程增长,其增长简化为整个柱壳结构沿 $x$ 轴方向按恒定速度 $\begin{array} { r } { \frac { d l } { d t } = { \dot { l } } } \end{array}$ 的连续增长过程.其中速度 $i$ 由打印进程中的参数决定，它可以从流量关系 $Q = i \nu _ { n } h T _ { l }$ 得到,即

$$
 \dot { l } = \frac { Q } { \nu _ { n } h T _ { l } } ,
$$

其中 $\boldsymbol { \mathrm { \ell } }$ 为打印材料从喷头每单位时间排出体积, $\nu _ { n }$ 为喷头水平移动速度， $T _ { l }$ 为打印单个材料层所需时间， $h$ 为壳体厚度.如图5所示，打印过程可以通过采用附着在喷嘴末端的欧拉坐标系进行判定.其中欧拉坐标 $X$ 与拉格朗日坐标 $x$ 的关系： $l = x + X$ ，可以得到欧拉坐标 $X$ 如下:

$$
X = { \hat { X } } ( x , t ) = x - l ,
$$

一般情况下可以认为打印速率是固定的,即 $\begin{array} { r l } { \displaystyle i } & { { } = } \end{array}$ constant,并设时间 $l ( 0 ) = 0$ ，有关系 $l = i t .$ 这样上式可以简化成

$$
X = { \hat { X } } ( x , t ) = x - { \dot { l } } t ,
$$

其中 $t$ 代表时间.如果打印速率是变化的问题就比较复杂了，将在今后的研究中考虑

考虑材料在点 $x = 0$ 处,固化过程中弹性刚度随时间演化可表示为：

$$
\hat { E } _ { * } ( x = 0 , t ) = \hat { g } _ { * } ( t ) E _ { 0 } ,
$$

其中 $g _ { * } = \hat { g } _ { * } ( t )$ 为固化特征函数, $\phantom { + } E _ { 0 }$ 为材料从喷嘴喷出的初始刚度.如文献[22]所示，可以得到欧拉坐标系

下目前最具代表性的两种固化特征函数。

(a)线性固化特征函数

$$
\hat { \overline { { { g } } } } _ { \ast } ^ { l } ( \overline { { { X } } } ) = 1 - \overline { { { X } } } ,
$$

(b)指数衰减固化特征函数

$$
\hat { \overline { { g } } } _ { \ast } ^ { e } ( \overline { { X } } ) = \gamma _ { E } + ( 1 - \gamma _ { E } ) e x p ( \overline { { X } } ) , ~ \gamma _ { E } = \frac { E _ { \infty } } { E _ { 0 } } ,
$$

其中

$$
\overline { { { X } } } = \frac { \xi _ { E } X } { i } , ~ \xi _ { E } \in \{ \xi _ { E } ^ { l } , \xi _ { E } ^ { e } \} .
$$

上述公式中参数上的横杠表示其为无量纲参数

将时间影响因素结合固化速率 $\xi _ { E }$ 以及打印速度 $i ,$ 可得:

$$
\overline { { X } } = \hat { \overline { { X } } } ( x , t ) = \frac { \xi _ { E } } { \dot { l } } x - \xi _ { E } t , \xi _ { E } \in \{ \xi _ { E } ^ { l } , \xi _ { E } ^ { e } \} ,
$$

将(18)式代入(9)式可得无量纲屈曲方程：

$$
\begin{array} { l } { ( \overline { { g } } _ { \ast } \overline { { w } } _ { , \overline { { X X } } } ) _ { , \overline { { X X } } } + \frac { \nu } { \overline { { h } } ^ { 2 } } \frac { \overline { { h } } } { \overline { { r } } } \frac { 1 } { \overline { { \xi } } _ { E } ^ { 5 } } \overline { { X } } + \frac { 1 2 ( 1 - \nu ^ { 2 } ) } { \overline { { h } } ^ { 4 } } ( \frac { \overline { { h } } } { \overline { { r } } } ) ^ { 2 } \frac { 1 } { \overline { { \xi } } _ { E } ^ { 4 } } \overline { { g } } _ { \ast } \overline { { w } } } \\ { - \frac { 1 } { \overline { { \xi } } _ { E } ^ { 3 } } ( \overline { { X } } \overline { { w } } _ { \overline { { X } } } ) _ { , \overline { { X } } } = 0 , } \end{array}
$$

其中无量纲参数 $\overline { { w } } , \overline { { r } } , \overline { { h } } , \overline { { l } } _ { c r } , \overline { { \xi } } _ { E }$ 分别为:

$$
\begin{array} { l } { { \overline { { \boldsymbol { w } } } = w / h } } \\ { { \displaystyle } } \\  { D _ { 0 } = \frac { E _ { 0 } h ^ { 3 } } { 1 2 ( 1 - \nu ^ { 2 } ) } , \quad \quad { \overline { { \boldsymbol { r } } } = ( \alpha \frac { \rho g h } { D _ { 0 } } ) ^ { \frac { 1 } { 3 } } \boldsymbol { r } , \quad \quad \overline { { h } } = ( \alpha \frac { \rho g h } { D _ { 0 } } ) ^ { \frac { 1 } { 3 } } h , } } \\ { { \displaystyle } } \\ { { \overline { { \boldsymbol { l } } } _ { c r } = \overline { { \boldsymbol { \xi } } } _ { E } \kappa = ( \alpha \frac { \rho g h } { D _ { 0 } } ) ^ { \frac { 1 } { 3 } } \boldsymbol { l } _ { c r } , \quad \kappa = \frac { \xi _ { E } \boldsymbol { l } } { \boldsymbol { l } } , } } \\ { { \overline { { \boldsymbol { \xi } } } _ { E } = ( \frac { 1 } { \alpha } \frac { D _ { 0 } } { \rho g h } ) ^ { \frac { 1 } { 3 } } \frac { \xi _ { E } } { \boldsymbol { l } } , \quad \xi _ { E } \in \{ \xi _ { E } ^ { l } , \xi _ { E } ^ { e } \} , } } \end{array}
$$

其中 $\alpha$ 为无量纲增幅系数,其目的在于在参数固定时,利用 $\alpha$ 使得 $\overline { { h } } = 1$ ，式(19)可变换为.

$$
( \overline { { g } } _ { * } \overline { { w } } _ { , \overline { { X } } \overline { { X } } } ) _ { , \overline { { X } } \overline { { X } } } + \nu \frac { \overline { { k } } } { \overline { { \xi } } _ { E } ^ { 5 } } \overline { { X } } + 1 2 ( 1 - \nu ^ { 2 } ) \frac { \overline { { k } } ^ { 2 } } { \overline { { \xi } } _ { E } ^ { 4 } } \overline { { g } } _ { * } \overline { { w } } - \frac { 1 } { \overline { { \xi } } _ { E } ^ { 3 } } ( \overline { { X } } \overline { { w } } _ { \overline { { X } } } ) _ { , \overline { { X } } } = 0 ,
$$

其中 $\overline { { k } }$ 为无量纲曲率,屈曲方程将被曲率 $\overline { { k } }$ 与固化速率 $\overline { { \xi } }$ 控制.

$$
{ \overline { { k } } } = { \frac { 1 } { \overline { { r } } } } .
$$

将(18)式代入边界条件(10),可得柱壳边界条件 沿 ${ \overline { { X } } } = - \kappa$ 和 ${ \overline { { X } } } = 0$ 分别为:

$$
\overline { { { w } } } ^ { c } | _ { \overline { { { X } } } = - \kappa } = 0 , ~ \overline { { { w } } } _ { , \overline { { { X } } } } ^ { c } | _ { \overline { { { X } } } = - \kappa } = 0 ,
$$

$$
\overline { { { w } } } _ { , \overline { { { X X } } } } ^ { c } \vert _ { \overline { { { X } } } = 0 } = 0 , ( \overline { { { g } } } _ { * } \overline { { { w } } } _ { , \overline { { { X X } } } } ^ { c } ) _ { , \overline { { { X } } } } \vert _ { \overline { { { X } } } = 0 } = 0 .
$$

# 2.2特征值问题的求解过程

微分方程(21)可利用伽辽金（Galerkin）方法进行求解:

$$
\int _ { \overline { { X } } = - \kappa } ^ { 0 } ( \overline { { R } } \delta \overline { { w } } _ { n } ) d \overline { { X } } = 0 ,
$$

其中余函数 $\overline { { R } }$ 为

$$
\begin{array} { l } { { \displaystyle \overline { { { \cal R } } } = \widehat { \overline { { { \cal R } } } } ( \overline { { { \cal X } } } ) = ( \overline { { { g } } } _ { \ast } \overline { { { w } } } _ { , \overline { { { X X } } } } ) _ { , \overline { { { X X } } } } + \nu \frac { \overline { { { k } } } } { \overline { { { \xi } } } _ { E } ^ { 5 } } \overline { { { X } } } + 1 2 ( 1 - \nu ^ { 2 } ) \frac { \overline { { { k } } } ^ { 2 } } { \overline { { { \xi } } } _ { E } ^ { 4 } } \overline { { { g } } } _ { \ast } \overline { { { w } } } } } \\ { { \displaystyle ~ - \frac { 1 } { \overline { { { \xi } } } _ { E } ^ { 3 } } ( \overline { { { X } } } \overline { { { w } } } _ { \overline { { { X } } } } ) _ { , \overline { { { X } } } } = 0 . } } \end{array}
$$

其中 $\delta \overline { { w } } _ { n }$ 为试函数． $\overline { { w } } _ { n }$ 可以设为满足边界条件的基函数与未知广义坐标 $C _ { n }$ 的线性组合,即 $\begin{array} { r l } { \overline { { w } } _ { n } } & { { } = } \end{array}$ $\textstyle \sum _ { n = 1 } ^ { N } C _ { n } { \overline { { X } } } ^ { n - 1 }$ .在式(24）中,每个广义坐标通过 $\delta \overline { { w } } _ { n }$ $\mathbf { \Sigma } = \mathbf { \Sigma }$ $( \partial \overline { { w } } / \partial C _ { n } ) \delta C _ { n }$ ，其得出的相应方程必须同时求解.通过采用增量迭代(牛顿迭代法)对得到的广义坐标代数方程组进行数值求解.其为描述柱壳轴对称屈曲的特征值问题.

考虑式(20)(22)中的无量纲参数,柱壳径厚比 $r / h$ 厚度 $\overline { { h } }$ ，屈曲长度 $\hat { l } _ { c r }$ ，固化速率 $\overline { { \xi } } _ { E }$ ，增幅系数 $\alpha$ ，以及垂直方向打印速度 $i$ 的影响.可得到广义屈曲长度函数, $\bar { l } _ { c r } = \hat { \overline { { l } } } _ { c r } ( \overline { { \xi } } _ { E } , \overline { { k } } )$

# 2.3柱壳的塑性破坏

除弹性屈曲外,柱壳也会因自重因素影响,达到材料塑性屈服强度 $\sigma _ { p }$ 而发生破坏,其中的下标 $p$ 代表"塑性破坏”通常来说,塑性破坏的关键位置为柱壳底部，即 $x = 0$ 处,此处因自重产生的轴向应力达到最大值.柱壳底部塑性破坏的屈服极限强度通常可表示为:

$$
\rho g l = | \sigma _ { p } | ,
$$

其中|I代表屈服强度 $\sigma _ { p }$ 的绝对值，l为圆柱壳的长度.与弯曲刚度 $D _ { * }$ 变化进行相似处理.由于固化进程因素影响,屈服强度在圆柱壳长度增长方向是不均匀的.在x轴方向,可将 $\sigma _ { p }$ 由 $\sigma _ { p * }$ 代替,圆柱壳底部屈服强度随时间变化可以给定为：

$$
\hat { \sigma } _ { p * } ( x = 0 , t ) = \hat { h } _ { * } ( t ) \sigma _ { p , 0 } .
$$

其中 $\sigma _ { p , 0 }$ 为打印进程中 $\mathit { t } ~ = ~ 0$ 时刻的屈服强度 ${ } , h _ { * } ~ =$ $\hat { h } _ { * } ( t )$ 为屈服强度随时间演化的固化特征函数.

由于塑性屈服极限由材料所决定，几何参数曲率对其无影响，可得出与文献[22完全相同的两种无量纲塑性破坏长度随固化速率变化函数，

(a)线性固化屈服函数：

$$
\overline { { l } } _ { p } = \frac { 1 } { 1 - \overline { { \xi } } _ { \sigma } ^ { l } } 0 \leq \overline { { \xi } } _ { \sigma } ^ { l } < 1 ,
$$

(b)指数衰减固化屈服函数：

$$
\begin{array} { r } { \overline { { l } } _ { p } - [ \gamma _ { \sigma } + ( 1 - \gamma _ { \sigma } ) \exp ( - \overline { { \xi } } _ { \sigma } ^ { e } \overline { { l } } _ { p } ) ] = 0 , } \end{array}
$$

文献[22]利用Newton-Raphson迭代法将(29)求解,得出一个封闭的精确逼近的数值解,并将其拟合,拟合优度 $R ^ { 2 }$ 介于0.993与0.999之间：

$$
\begin{array} { r l r } & { } & { \bar { l } _ { p } = \bar { l } _ { p , 0 } \left( 1 + \frac { \gamma _ { \sigma } - 1 } { 1 + \left( \frac { \bar { \xi } _ { \sigma } ^ { e } } { \bar { \xi } _ { r e f } } \right) ^ { - p } } \right) , \quad } \\ & { } & { \overline { { \xi } } _ { r e f } = \overline { { \hat { \xi } } } _ { r e f } ( \gamma _ { \sigma } ) = \frac { 1 . 1 8 1 } { 1 + 0 . 8 4 4 \gamma _ { \sigma } } , \quad } \\ & { } & { p = \hat { p } ( \gamma _ { \sigma } ) = 1 . 4 6 6 ( \gamma _ { \sigma } ) ^ { 0 . 3 2 2 } , \quad } \end{array}
$$

其中无量纲参数,塑性破坏长度 $\overline { { l } } _ { p }$ ，固化速率 $\overline { { \xi } } _ { \sigma }$ 分别为

$$
\begin{array} { r l } & { \displaystyle \overline { { l } } _ { p } = \frac { \rho g l _ { p } } { | \sigma _ { p , 0 } | } , } \\ & { \displaystyle \overline { { \xi } } _ { \sigma } = \frac { \xi _ { \sigma } | \sigma _ { p , 0 } | } { \rho g \dot { l } } \xi _ { \sigma } \in \{ \xi _ { \sigma } ^ { l } , \xi _ { \sigma } ^ { e } \} . } \end{array}
$$

![](images/96275fdc4c9a9cc3adbf59d29c53e5fdd4b078e0bc8df93b153a5d22d0a2dd4c.jpg)  
图6:线性固化速率影响下,柱壳塑性屈服长度 $\bar { l } _ { p }$ 随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { \sigma } ^ { l }$ 变化曲线图.

![](images/457e8f05633466ac2a75b915d91c7581c3a50ea9054e428c04924de8a1c683a7.jpg)  
图7:指数衰减固化速率影响下,柱壳塑性屈服长度 $\overline { { l } } _ { p }$ 随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { \sigma } ^ { l }$ 变化曲线图.

如式(31)所示,从材料性能和打印工艺数据中，可以先验性地计算无量纲固化速率 $\overline { { \xi } } _ { \sigma } ^ { l }$ ．如式(28)所述,当 $\overline { { \xi } } _ { \sigma } ^ { l } \to 1$ 时,无量纲屈服长度 $\bar { l } _ { p }$ 接近无穷大.因此,对于线性固化过程，固化速率趋近1的这个值应该被认为是塑性破坏的上限.当 $\overline { { \xi } } _ { \sigma } ^ { l } > 1$ 时,如式(31)所示，固化速率 $\xi _ { \sigma } ^ { l }$ 引起的屈服强度的增长快于打刷速度 $i$ 所控制的应力的增长.因此，圆柱壳底部的应力不再达到屈服强度，则不会发生塑性倒塌

如式(30)所述,当 $\overline { { \xi } } _ { \sigma } ^ { e }  \infty$ 时其塑性破坏长度 $\bar { l } _ { p }$ 收敛于 $\bar { l } _ { p , 0 } \cdot \gamma .$ 因此,对于指数衰减固化过程, $\bar { l } _ { p , 0 } \cdot \gamma$ 应该被认为是塑性破坏的上限.

# 2.4Suiker数与弹性屈曲与塑性破坏的Suiker判据

当塑性屈服长度小于弹性屈曲长度,即 $l _ { p } ~ < ~ l _ { c r }$ 时,圆柱壳会发生塑性坍塌;同样,当塑性屈服长度大于弹性屈曲长度，即 $l _ { p } \ > \ l _ { c r }$ 时,圆柱壳会发生弹性屈曲.这一用于分析可能失效机制的标准可以通过调用几何、材料和打印参数来方便地表示,利用式(20)与(31)可得

$$
\begin{array} { r l } { \displaystyle \frac { \overline { { l } } _ { c r } } { \overline { { l } } _ { p } } < \overline { { \Lambda } } : } & { { } ~ e l a s t i c ~ b u c k l i n g , } \\ { \displaystyle \frac { \overline { { l } } _ { c r } } { \overline { { l } } _ { p } } > \overline { { \Lambda } } : } & { { } ~ p l a s t i c ~ c o l l a p s e , } \end{array}
$$

其中

$$
\begin{array} { l } { \displaystyle { \overline { { \Lambda } } = ( \alpha \frac { h } { D _ { 0 } } ) ^ { \frac { 1 } { 3 } } \frac { | \sigma _ { p , 0 } | } { ( \rho g ) ^ { \frac { 2 } { 3 } } } , } } \\ { \displaystyle { \overline { { l } } _ { c r } = \widehat { \bar { l } } _ { c r } ( \overline { { \xi } } _ { E } , \overline { { k } } ) , \quad \mathrm { ~ } \overline { { l } } _ { p } = \widehat { \bar { l } } _ { p } ( \overline { { \xi } } _ { \sigma } ) . } } \end{array}
$$

Suiker[22]首次提出式(33)中所述无量纲参数 $\overline { { \Lambda } }$ 由于其重要性,称 $\overline { { \Lambda } }$ 为Suiker数． $\overline { { \Lambda } }$ 在被打印物体几何参数,材料参数固定时为常数,不随时间变化.当评判具体直壁结构弹性屈曲和塑性破坏之间的竞争关系时，完全可以预先计算出，以便对破坏机制进行预测.在实际打印过程中,常采用试错的方式,来对直壁结构的失效进行分析，即使在相同的材料参数下,由于几何参数的差异,失效机制同样会发生变化.而Suiker数 $\overline { { { \Lambda } } }$ 的给出,为通过提升材料性能或改变几何参数来达到材料的最大利用率明确了方向,这对于分析3D打印进程中直壁结构的力学性能及其失效机制方面具有十分重大的意义，

# 3柱壳失效问题数值解

在结果分析中,首先通过计算临界屈曲长度来考虑屈曲的情况,临界屈曲长度 $\hat { \bar { l } } _ { c r } ( \overline { { \xi } } _ { E } , \overline { { k } } )$ 可从方程(19)的弱解形式与边界条件(23)解得.将 $\overline { { w } }$ 代入方程弱解形式(24),转换成特征值问题.所求最小特征值代表临界屈曲长度 $\hat { l } _ { c r }$ ，通过假设位移为多项式形式来进行计算.

$$
\hat { \overline { { w } } } ( \overline { { X } } ) = \sum _ { n = 1 } ^ { N } C _ { n } \overline { { X } } ^ { n - 1 } \quad n = 1 , 2 , . . . , N .
$$

其中 $C _ { n }$ 代表未知广义坐标.采用式(33)给出的评判机制,可以进行临界屈曲长度 $\hat { \overline { { l } } } _ { c r } ( \overline { { \xi } } _ { E } , \overline { { k } } )$ 与塑性屈服长度 $\hat { \overline { { l } } } _ { p } ( \overline { { \xi } } _ { \sigma } )$ 分别在线性固化进程以及指数衰减固化进程中的竞争关系对比评判

# 3.1固化进程影响下数值求解分析

对于圆柱壳在固化进程影响下的数值求解分析,通过调整式(20)增幅系数 $\alpha$ ，使得 $\overline { { h } } = 1$ 时，无量纲临界屈曲长度取决于两个无量纲参数,固化速率 $\overline { { \xi } } _ { E } ^ { l }$ ，曲率 $\overline { { k } } .$ 即 $\hat { \bar { l } } _ { c r } ( \overline { { \xi } } _ { E } ^ { l } , \overline { { k } } )$ .其中泊松比 $\nu = 0 . 3$ ，并设定设定无量纲曲率取值范围为 $\begin{array} { r } { \frac { 1 } { 2 0 } \le \overline { { k } } \le \frac { 1 } { 5 } } \end{array}$

![](images/8fcf6665d7780be9d286dd4c67a432cb19b14819a6e4b27204b138f889c6e488.jpg)  
图8：柱壳在3D打印进程中，由于线性固化参数影响,屈曲长度 $\bar { l } _ { c r }$ 随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { E } ^ { l }$ 变化曲线图,其中曲率 $\begin{array} { r } { \frac { 1 } { 2 0 } \le \overline { { k } } \le \frac { 1 } { 5 } } \end{array}$ ：

由图8可以看出,在线性固化进程影响下,当曲率 $\overline { { k } }$ 固定时，屈曲长度随固化速率 $\overline { { \xi } }$ 的增加呈指数形式增加;当固化速率 $\overline { { \xi } }$ 固定时,屈曲长度 $\overline { { l } } _ { c r }$ 随曲率 $\overline { { k } }$ 的增大而增大;当曲率 $\overline { { k } }$ 取值越大时,屈曲长度随固化速率 $\overline { { \xi } } _ { E } ^ { l }$ 的增长幅度明显增大;当固化速率 $( \overline { { \xi } } _ { E } ^ { l } \to 0 )$ （204号时，描述的为底部固支，上部自由的均质柱壳在自重作用下的屈曲行为

![](images/802700c46f54773d39bc5d3bc2cdf01a85cc888b0d60eea911027fa8dfbc8203.jpg)  
图9：柱壳在3D打印进程中，由于指数衰减固化参数影响,屈曲长度 $\hat { l } _ { c r }$ 随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { E } ^ { l }$ 变化曲线图,计算方便起见,其中曲率 $\begin{array} { r } { \frac { 1 } { 2 0 } \leq \overline { { k } } \leq \frac { 1 } { 5 } } \end{array}$ ， $\begin{array} { r } { \gamma = \frac { E _ { \infty } } { E _ { 0 } } = 2 } \end{array}$ ，

由图9可以看出，在指数衰减固化进程影响下，当曲率 $\overline { { k } }$ 固定时,屈曲长度随固化速率 $\overline { { \xi } }$ 的增加而增加,并当 $\bar { \xi } \to \infty$ 时,屈曲长度收敛于 $\overline { { l } } _ { c r , 0 } \cdot \gamma ;$ 当固化速率 $( \overline { { \xi } } )$ 固定时,屈曲长度 $\bar { l } _ { c r }$ 随曲率 $\overline { { k } }$ 的增大而增大;当曲率 $\overline { { k } }$ 取值越大时,屈曲长度随固化速率 $\overline { { \xi } } _ { E } ^ { l }$ 的增长幅度明显增大;当固化速率 $( \overline { { \xi } } _ { E } ^ { l } \to 0 )$ 时,所得屈曲长度与线性固化进程中完全相同,同样描述的为柱壳自

重作用下的屈曲行为，

通过图7图8的分析可以看出，二者均描述了打印进程中均质柱壳到非均质柱壳的自重作用下屈曲长度的变化特性,以及曲率对结构稳定性的影响,且符合在时间参数影响下屈曲长度应随材料固化速率增加而增加的一般事实规律.

# 3.2弹性屈曲与塑性破坏数值求解比较分析

对于柱壳弹性屈曲与塑性破坏数值求解,分析线性固化进程与指数衰减固化进程下的弹性屈曲与塑性破坏竞争关系。

线性固化进程情况下,选取曲率 $\overline { { k } } ~ = ~ \frac { 1 } { 6 . 2 5 }$ ,并对此参数所求数值解进行拟合,可用近似函数表示,其拟合优度 $R ^ { 2 } = 0 . 9 9 9$

$$
\overline { { l } } _ { c r } = 8 . 7 1 9 2 + 3 . 0 6 5 2 \exp ( 1 8 . 2 6 3 9 \overline { { \xi } } _ { E } ^ { l } ) ,
$$

其中当 $\overline { { \xi } } _ { E } ^ { l }$ 趋近于0时,即无量纲临界屈曲长度与固化速率无关时 $\bar { \ J } _ { c r , 0 } \ = \ 1 1 . 6 5 .$ 同时可用式(28)(35),即所得拟合近似函数，对弹性屈曲与塑性坍塌的竞争关系进行表述.

$\frac { \overline { { l } } _ { c r } } { \overline { { l } } _ { p } } = ( 8 . 7 1 9 2 + 3 . 0 6 5 2 \exp ( 1 8 . 2 6 3 9 \overline { { \xi } } _ { E } ^ { l } ) ) ( 1 - \beta \overline { { \xi } } _ { E } ^ { l } ) ,$ 其中 $\beta = \overline { { \xi } } _ { \sigma } ^ { l } / \overline { { \xi } } _ { E } ^ { l }$

![](images/dc5a09d9e0b0a2a239d9d758e26362c54a3060822735806e417f0cb3ec2e7a04.jpg)  
图10:线性固化进程中,圆柱壳打印失效图.长度标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 在选定的固化比下,随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { E } ^ { l }$ 变化曲线图.其中 $\beta = \overline { { \xi } } _ { \sigma } ^ { l } / \overline { { \xi } } _ { E } ^ { l }$ ，其范围从5到10.此曲线由式(34)绘制,其中 $\overline { { \Lambda } }$ 代表了线性固化进程中,弹性屈曲与塑性破坏之间的竞争关系.

如图10所示，其中 $\beta$ 的取值为,5.6,7,8.9,10.具体来说,当标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 曲线上的点大于 $\overline { { { \Lambda } } }$ 的值时,将发生塑性坍塌,反之将发生弹性屈曲.弹性屈曲与塑性坍塌的竞争关系明显依赖于 $\beta$ 值的变化.当 $\beta$ 取值越大时,标度比 $\overline { { l } } _ { c r } / \overline { { l } } _ { p }$ 曲线下降越快.对于图9而言,当 $\beta \geq 6$ 时,只要 $\overline { { \Lambda } } \geq \overline { { l } } _ { c r , 0 } = 1 1 . 6 5$ 时,塑性坍塌将不会发生,弹性屈曲为唯一的失效机制.

当 $\overline { { \Lambda } } \ \leq \ \overline { { l } } _ { c r , 0 } \ = \ 1 1 . 6 5$ 时,塑性破坏将发生在当固化速率 $\overline { { \xi } } _ { E } ^ { l }$ 较小时，弹性屈曲将发生在固化速率 $\overline { { \xi } } _ { E } ^ { l }$ 较大时.随着 $\overline { { \xi } } _ { E } ^ { l }$ 的增大， $\bar { l } _ { c r } / \bar { l } _ { p }$ 向 $x$ 负轴方向减小,直到 $\bar { l } _ { c r } / \bar { l } _ { p } \ = \ 0$ ，弹性屈曲为唯一失效机制.具体来说,当 $\beta = 5$ 时,当 $\overline { { \Lambda } } ~ > ~ ( \bar { l } _ { c r } / \bar { l } _ { p } ) _ { m a x } ~ = ~ 1 4 . 5 8$ 时，弹性屈曲为唯一失效机制。当 $0 < \overline { { \Lambda } } < ( \bar { l } _ { c r } / \bar { l } _ { p } ) _ { m a x }$ 时， $0 <$ $\overline { { \xi } } _ { E } ^ { l } < a , b \le \overline { { \xi } } _ { E } ^ { l }$ 为弹性屈曲， $a \leq \overline { { \xi } } _ { E } ^ { l } < b$ 为塑性破坏， $a _ { \mathrm { { } } }$ $b$ 可由 $\hat { \bar { \xi } } _ { E } ^ { l } ( \bar { l } _ { c r } / \bar { l } _ { p } )$ 求得，其中 $( \bar { l } _ { c r } / \bar { l } _ { p } ) = \overline { { \Lambda } }$

指数衰减固化进程情况下,对 $\bar { l } _ { c r } , \bar { l } _ { p }$ 所求数值解进行拟合，可用近似函数表示,其拟合优度 $R ^ { 2 } = 0 . 9 9 9$

$$
\overline { { { l } } } _ { c r } = 2 2 . 9 1 6 8 - 1 1 . 4 9 1 6 \exp ( - 8 . 0 5 5 9 \overline { { { \xi } } } _ { E } ^ { e } ) .
$$

其中当 $\overline { { { \xi } } } _ { E } ^ { e } \ = \ 0$ 即无量纲临界屈曲长度与固化速率无关时, $\overline { { l } } _ { c r , 0 } ~ = ~ 1 1 . 6 5$ ．同时可用拟合近似函数,结合式(30)(37)对弹性屈曲与塑性破坏的竞争关系进行表述,可得

$$
\begin{array} { l } { \displaystyle \frac { \overline { { l } } _ { c r } } { \overline { { l } } _ { p } } = \left( 2 2 . 9 1 6 8 - 1 1 . 4 9 1 6 \exp ( - 8 . 0 5 5 9 \overline { { \xi } } _ { E } ^ { e } ) \right) } \\ { \displaystyle \left( 1 + \frac { \gamma _ { \sigma } - 1 } { 1 + \left( \frac { \overline { { \xi } } _ { c r } ^ { e } } { \overline { { \xi } } _ { r e f } ^ { e } } \right) ^ { - p } } \right) ^ { - 1 } . } \end{array}
$$

![](images/df61668ae622285bc5aaa70b92652319c6995fb5143f321297cf92155361a919.jpg)  
图11:指数衰减固化进程中，圆柱壳打印失效图.长度标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 在选定的固化比下,随固化速率 $\overline { { \xi } } = \overline { { \xi } } _ { E } ^ { e }$ 变化曲线图.其中 $\beta = \overline { { \xi } } _ { \sigma } ^ { l } / \overline { { \xi } } _ { E } ^ { l }$ ,其范围从0.1到40.此曲线由式(38)绘制,其中 $\overline { { \Lambda } }$ 代表了指数衰减固化进程中，弹性屈曲与塑性破坏之间的竞争关系.

如图10所示， $x$ 坐标采用对数坐标.其中 $\beta$ 的取值为0.1，0.2，0.5，1，2，5，10，20，40.具体分析与上述类似,当标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 曲线上的点大于 $\overline { { { \Lambda } } }$ 的值时.将发生塑性破坏,反之将发生弹性屈曲.如图10所示,当 $\beta ~ \geq ~ 2 0$ 时,只要 $\overline { { \Lambda } } ~ > ~ 1 1 . 6 5$ ，塑性破坏将不会发生.弹性屈曲为唯一的失效机制,当 $\overline { { \Lambda } } ~ < ~ 1 1 . 6 5$ 时，$0 < \overline { { \xi } } _ { E } ^ { l } < a , b \leq \overline { { \xi } } _ { E } ^ { l }$ 为塑性破坏, $a \leq \overline { { \xi } } _ { E } ^ { l } < b$ 为弹性屈曲, $a , b$ 可由 $\hat { \overline { { \xi } } } _ { E } ^ { l } ( { \bf \bar { \it l } } _ { c r } / { \bar { \it l } _ { p } } )$ 求得.

具体来说,当 $\beta = 0 . 1$ ,当 $\overline { { \Lambda } } > ( \overline { { l } } _ { c r } / \overline { { l } } _ { p } ) _ { m a x } = 2 2 . 5 4$ 时,弹性屈曲为唯一失效机制.当 $0 < \overline { { \Lambda } } < ( \bar { l } _ { c r } / \bar { l } _ { p } ) _ { m a x }$ 时， $0 < \overline { { \xi } } _ { E } ^ { l } < a , b \leq \overline { { \xi } } _ { E } ^ { l }$ 为弹性屈曲, $a \leq \overline { { \xi } } _ { E } ^ { l } < b$ 为塑性破坏, $a , b$ 可由 $\hat { \overline { { \xi } } } _ { E } ^ { l } ( { \bf \bar { \it l } } _ { c r } / { \bar { \it l } _ { p } } )$ 求得,其中 $( \bar { l } _ { c r } / \bar { l } _ { p } ) = \overline { { \Lambda } }$ （2

通过图9图10的分析可以看出,固化比 $\beta$ 对弹性屈曲与塑性破坏之间的竞争关系影响巨大.当 $\beta$ 越小时,越容易发生塑性破坏;当 $\beta$ 越大时,越容易发生弹性屈曲.而标度率曲线与 $\overline { { { \Lambda } } }$ 值相交处，代表两种破坏机制的临界位置.通过对标度比曲线的变化趋势发现,线性固化进程中,当 $\beta = 5$ 时,标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 为先增加在减少;而当 $\beta > 5$ 时,标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 为单调递减.在指数衰减固化进程中,当 $\beta \leq 5$ 时,标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 为先增加再减少;当 $\beta \geq 1 0$ 时,标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 为先减少再增加.由此可以看出，固化比 $\beta$ 对标度比曲线的变化趋势也有很大的影响,即在给定几何参数下,固化比 $\beta$ 决定了弹性屈曲与塑性破坏这两种失效机制的主导地位.

# 4给定打印参数下的影响分析

本节首先使用商用有限元软件ABAQUS对3D打印进程中柱壳结构的屈曲行为进行了模拟,对上文所得屈曲参数模型进行了验证.随后采用了与Suiker[22]完全相同的打印参数,将圆柱壳结构与其所研究的 $b = 6 2 5 m m , d = 2 5 0 m m$ 矩形布置直壁结构进行对比分析.最后针对该类混凝土所打印圆柱壳结构的失效机制,即弹性屈曲与塑性破坏之间的竞争关系进行了具体分析.

# 4.1 弹性屈曲

![](images/6f0bd8f0a14fe9a244ce1512d76c02ff8f8d0674f8d8e2963052f5b61b4f3a99.jpg)  
图12:柱壳屈曲生长示意图.

图11中描绘了柱壳由于在X轴方向以恒定速率生长,结构从最初小变形，其次达到临界屈曲高度而发生失稳直至结构失效的示意图.针对柱壳结构弹性屈曲分析中所使用的参数列于表1,对在自重作用下屈曲的力学行为进行析,其中选择了线性固化以及指数衰减固化两种常见的固化方式进行模拟.根据式(14)(20)，对线性固化进程选择了 $\begin{array} { r } { \overline { { \xi } } _ { E } ^ { l } ~ = ~ } \end{array}$ 0.02，0.05，0.1，对指数衰减固化进程选择了 $\overline { { { \xi } } } _ { E } ^ { e } ~ = ~$ 0.02，0.1,0.2进行模拟,以便对参数模型进行验证.

表1Suiker打印固化参数  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>壳体厚度</td><td>h = 43.5(mm)</td></tr><tr><td>单层高度</td><td>t = 9.2(mm)</td></tr><tr><td>材料密度</td><td>p= 2020(kg/m³)</td></tr><tr><td>喷头速度</td><td>Vn = 83.3(mm/s)</td></tr><tr><td>泊松比</td><td>v = 0.3(-)</td></tr><tr><td>线性固化</td><td></td></tr><tr><td>初始弹性模量</td><td>Eo = 78100(Pa)</td></tr><tr><td>固化速率</td><td>E = 0.02,0.05,0.1(-)</td></tr><tr><td>指数衰减固化</td><td></td></tr><tr><td>初始弹性模量</td><td>Eo = 78100(Pa)</td></tr><tr><td>固化速率</td><td>E = 0.02,0.1,0.2(-)</td></tr><tr><td>刚度比</td><td>ye = =2(-）</td></tr></table></body></html>

注意,为贴合实际打印尺寸以及数值计算方便，式(20)中的 $\alpha$ 为无量纲系数,当实际打印壳体厚度为 $4 3 . 5 m m$ 时,通过调节 $\alpha = 8 . 2 9 7$ 来确保无量纲壳体厚度 $\overline { { h } } = 1$ .其中,在参数一定的情况下,无量纲固化速率 $\overline { { \xi } } _ { E }$ 与固化速率 $\xi _ { E }$ 为正线性关系.即无量纲固化速率 $\overline { { \xi } } _ { E }$ 愈大,固化速率 $\xi _ { E }$ 也愈大.由式 $( 3 3 ) _ { 4 }$ 可得,当无量纲壳体厚度 $\overline { { h } } = 1$ 时，无量纲屈曲长度 $\hat { l } _ { c r }$ 由无量纲固化速率 $\overline { { \xi } } _ { E }$ ，以及无量纲曲率 $\overline { { k } }$ 决定,即 $\bar { l } _ { c r } = \hat { \overline { { l } } } _ { c r } ( \overline { { \xi } } _ { E } , \overline { { k } } )$

![](images/f5cf8b4e5c97a486f17939a74796f2ecccb3c3af358d463f662446dd699ab816.jpg)  
图13:线性固化参数影响下，FEM结果与数值计算结果对比图

由图12可以看出：在线性固化参数影响下,得出的有限元分叉屈曲模拟与参数模型的结果整体较为接近.但是随着 $\overline { { \xi } } _ { E } ^ { l }$ 的增大,有限元结果与参数模型结果差距增大.具体来说,当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 0 2$ 时,二者相差 $3 . 1 \%$ ：，当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 0 5$ 时,二者相差 $8 . 6 \%$ ；当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 1$ 时,二者相差 $2 5 \%$

![](images/54c60be1c99184100f72fec1a778f3949fccc9b6885a5b178ee5eaf3e26d7146.jpg)  
图14:指数衰减固化参数影响下，FEM结果与数值计算结果对比图

$\begin{array} { r l r } { \overline { { \xi } } _ { E } ^ { l } } & { { } = } & { 0 . 0 2 5 4 . } \end{array}$ $\begin{array} { r l } { { \frac { 1 } { 5 } } } & { { } \leq } \end{array}$ $\overline { { k } } \leq \frac { 1 } { 1 0 }$ 时,无量纲固化速率 $\overline { { \xi } } _ { E } ^ { l }$ 的范围由0.0199 增长至0.0397，在此范围内，有限元模拟分叉屈曲结果与参数模型结果相差不大，说明参数模型能对混凝土3D打印柱壳的分叉屈曲行为进行较好的模拟，

在经典理论中,对于柱壳屈曲的控制方程的解采用正弦近似的方式写出级数形式： $w \ = \ \sum \Sigma A$ ：$s i n ( \alpha x ) { \cdot } s i n ( \beta y )$ ，其解沿圆周方向同样采用屈曲波形为正弦形式,此解更加符合实际情况.而本文在第一节的理论推导中，考虑到混凝土3D打印圆柱壳由于其初始抗弯刚度 ${ { E } _ { 0 } }$ 较低,不可能在较大挠度下仍保持完好,所以构建的为轴对称情况下的参数模型,将解设置为 $w = w ( x )$ .在对于 $\overline { { \xi } } _ { E } ^ { l }$ 值较大时,混凝土3D打印柱壳屈曲长度更高,而距离壳体底部距离越大处，其水平屈曲形态的差异越大，有限元模拟分叉屈曲结果与参数模型结果相差也越大.

# 4.2 对比分析

根据Suiker[22]研究发现, $b = 6 2 5 m m , d = 2 5 0 m m$ 矩形布置直壁结构.其失效机制的上界由塑性破坏决定(而不是侧面固支下的弹性屈曲),下界由侧面简支下的弹性屈曲决定,具体参数列于表1,固化进程由式(39)(40)决定.当采用了与Suiker完全相同的参数时,曲率 $\overline { { k } } \approx 1 / 6 . 4$ ，即 $h = 4 3 . 5 m m$ ， $r = 2 7 8 . 4 m m$

Suiker通过对直径为70mm, 高度为140mm的4到6个圆柱形混凝土试件进行单轴压缩试验，测量出混凝土弹性刚度与抗压屈服强度在不同时间点的实验数据,对此实验数据采用最小二乘法进行拟合,得到

(1)弹性刚度 $\hat { E } _ { * } ( P a )$ 随固化时间 $t ( s )$ 线性变化函数，拟合优度 $R ^ { 2 } = 0 . 9 9 5$

由图13可以看出：在指数衰减固化参数影响下,对于有限元模拟，得出的有限元模拟分叉屈曲结果与参数模型的结果整体同样较为接近.但是随着 $\overline { { \xi } } _ { E } ^ { l }$ 的增大,有限元结果与参数模型结果差距增大.具体来说,当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 0 2$ 时,二者相差 $1 . 9 \%$ ；当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 1$ 时,二者相差 $7 . 2 \%$ 当 $\overline { { \xi } } _ { E } ^ { l } = 0 . 2$ 时,二者相差 $10 \%$

当 $b ~ = ~ 6 2 5 m m , d ~ = ~ 2 5 0 m m$ 时,曲率应为 $\begin{array} { r } { \overline { { k } } { \mathrm { ~ \scriptsize ~ = ~ } } } \end{array}$ $\begin{array} { r l r } { \frac { 2 ( b + d ) } { 2 \cdot \pi \cdot 4 3 . 5 } } & { { } \approx } & { 1 / 6 . 4 } \end{array}$ ，其中柱壳厚度为 $4 3 . 5 m m$ ，单层打印高度为 $9 . 2 m m$ ，根据式(11)(1)(40)可得 $\begin{array} { r l } { \xi _ { E } ^ { l } } & { { } = } \end{array}$ $0 . 0 0 0 2 5 6 ( s ^ { - 1 } ) , \dot { l } ~ = ~ 0 . 0 0 0 4 3 8 ( m / s )$ ，代入式 $( 2 0 ) _ { 4 }$ 可得,

$$
\hat { E } _ { * } ( t ) = 7 8 1 0 0 + 2 0 t ,
$$

(2)抗压屈服强度 $\hat { \sigma } _ { p * } ( P a )$ 随固化时间 $t ( s )$ 线性变化函数，拟合优度 $R ^ { 2 } = 0 . 9 9 1$

$$
\hat { \sigma } _ { p * } ( t ) = 5 9 8 4 + 2 . 4 5 t .
$$

在此打印进程参数与几何参数影响下,侧面简支的矩形布置直壁结构屈曲高度 $l _ { c r } ^ { s } = 0 . 2 1 0 m$ ，侧面固支情况下 $l _ { c r } ^ { f } = 0 . 4 3 1 m$ ，塑性破坏长度 $l _ { p } = 0 . 4 2 1 m$ 因此矩形布置的直壁结构实际失效尺寸范围应为 $0 . 2 1 0 m \leq$ $l _ { c r } \le 0 . 4 2 1 m$ ，进一步由纵横比 $b / d = 2 . 5$ 确定出侧壁对主壁提供的转动刚度,从而得出更加确切的屈曲高度 $l _ { c r } = 0 . 2 6 9 m$

在参数完全相同情况下，混凝土3D打印柱壳的无量纲屈曲高度 $\bar { l } _ { c r } = 1 3 . 3$ 等同于 $l _ { c r } = 0 . 5 7 8 m$ .由式(31) (28)可以得出,此时 $\overline { { \xi } } _ { \sigma } ^ { l } = 0 . 2 8 2$ ，圆柱壳无量纲塑性破坏长度 $\bar { l } _ { p } = 1 . 3 9 3$ 等同于 $l _ { p } = 0 . 4 2 1$ ．即当曲率 $\overline { { k } } \approx 1 / 6 . 4$ 时,柱壳结构会因为达到抗压屈服强度而发生塑性破坏.

令柱壳屈曲高度与Suiker计算相同时,即 $\begin{array} { r l } { l _ { c r } } & { { } = } \end{array}$ $0 . 2 6 9 m$ 等同于 $\overline { { l } } _ { c r } = 6 . 1 8 4$ ，带入式(43),可得曲率 $\overline { { k } } =$ 17.74.即代表着相同的稳定性要求时，柱壳结构能比矩形布置直墙结构拥有更大的框架，

显然,相比于矩形布置的直壁结构，由于结构的完整性(相当于侧面完全固支)以及曲率的引入，柱壳结构能更加充分利用材料,即在单层打印材料用量相同的同时，柱壳结构能达到更高的层数,具有更强的稳定性.

# 4.3 失效机制分析

具体来说,对于柱壳限定的几何参数,当 $\begin{array} { r l } { h } & { { } = } \end{array}$ $4 3 . 5 m m$ 时,为了计算方便,通过调整 $\alpha$ 的值,使得 $\overline { { h } } =$ 1,通过式(20)计算可得, $\alpha = 8 . 2 9 7$ 即 $\begin{array} { r } { ( \alpha \frac { \rho g h } { D _ { 0 } } ) ^ { \frac { 1 } { 3 } } = 2 2 . 9 9 } \end{array}$ 由此可得 $\bar { l } _ { c r } = 2 2 . 9 9 \cdot l _ { c r }$

对于限定的混凝土材料及固化参数，当其弹性刚度和抗压屈服强度由式(39)(40)给定时，即此类参数均被给定， $\begin{array} { r } { \xi _ { E } ~ = ~ \frac { 2 0 } { 7 8 1 0 0 } ~ = ~ 0 . 0 0 0 2 5 6 ( s ^ { - 1 } ) , \xi _ { \sigma } ~ = ~ \frac { 2 . 4 5 } { 5 9 8 4 } ~ = ~ } \end{array}$ $0 . 0 0 0 4 1 ( s ^ { - 1 } ) , \rho ~ = ~ 2 0 2 0 ( k g / m ^ { 3 } ) , g ~ = ~ 9 . 8 1 m / s ^ { 2 } .$ 由式(20)(31)可以看出，唯一决定无量纲固化速率 $\overline { { \xi } }$ 的只有柱壳轴向增长速率 $\dot { l } .$ 打印材料从喷头每单位时间排出的体积 $Q \ = \ \nu _ { n } h t _ { l }$ ，每层材料打印所需时间 $T _ { l } =$ $2 \pi r / \nu _ { n }$ ，结合式(11),可得

$$
\dot { l } = \frac { Q } { \nu _ { n } h T _ { l } } = \frac { t _ { l } \nu _ { n } } { 2 \pi h } \cdot \frac { h } { r } = 0 . 0 0 2 8 0 \frac { h } { r } ,
$$

结合式(41),并带入上述参量可得出无量纲固化速率 $\overline { { \xi } } _ { E }$ 与 $\overline { { \xi } } _ { \sigma }$ 随曲率k的变化函数

$$
\begin{array} { l } { { \displaystyle \overline { { \xi } } _ { E } = ( \frac { 1 } { \alpha } \frac { D _ { 0 } } { \rho g h } ) ^ { \frac { 1 } { 3 } } \frac { \xi _ { E } } { \bar { l } } = 0 . 0 0 4 \overline { { k } } , \hfill } } \\ { { \displaystyle \overline { { \xi } } _ { \sigma } = \frac { \xi _ { \sigma } | \sigma _ { p , 0 } | } { \rho g \bar { l } } = 0 . 0 4 4 0 9 \overline { { k } } , \hfill } } \end{array}
$$

将式 $( 4 2 ) _ { 1 }$ ，以步长为0.5,曲率 $\overline { { k } }$ 范围从1/5到1/10,计算

所得散点图，进行指数拟合，拟合优度 $R ^ { 2 } = 0 . 9 9 9$

$$
\overline { { l } } _ { c r } = 5 . 6 3 9 4 3 + 4 4 . 0 7 9 2 8 \exp ( - 0 . 2 8 5 0 9 \overline { { { r } } } ) .
$$

利用式(33),可计算出此类参数下,Suiker数 $\begin{array} { r l } { \overline { { \Lambda } } } & { { } = } \end{array}$ 6.94196.结合式 $( 2 8 ) ( 4 2 ) _ { 2 }$ 可得无量纲塑性破坏长度 $\overline { { l } } _ { p }$ 随无量纲半径r变化函数.将 $\hat { \overline { { l } } } _ { p } ( \overline { { r } } ) \cdot \overline { { \Lambda } }$ 与式(43)绘制于图14.

![](images/518bfea99ef2a0edc221d111b90a009de7254d1ad93ed15b683dd4df6b8d4ea6.jpg)  
图15：圆柱壳混凝土3D打印,在混凝土参数固定,打印参数固定的影响下,塑性破坏长度 $\bar { l } _ { p }$ 与弹性屈曲长度 $\bar { l } _ { c r }$ 随无量纲半径变化图.

如图12所示,当打印参数由式(39)(40)与表1决定时,Suiker数 $\overline { { { \Lambda } } }$ 也随之固定.而 $\hat { \overline { { l } } } _ { p } ( \overline { { r } } ) \cdot \overline { { \Lambda } }$ 与 $\hat { \bar { l } } _ { c r } ( \overline { { r } } )$ 两条曲线的交点 $A$ ，代表着塑性破坏与弹性屈曲两种破坏机制的竞争关系的临界点,即此时 $l _ { c r } = l _ { p }$ ，由图12,可以看出两条曲线的交点处,径厚比 $\overline { { r } } = 7 . 7 3 4 9 6$ ，失效长度 $\bar { l } _ { f } = 1 0 . 5 3 5 1 5$ ，其等同于曲率 $\overline { { k } } = 1 / 7 . 7 3 4 9 6$ ，失效长度 $l _ { f } = 0 . 4 5 8 2 m$ 当无量纲半径 $\overline { { r } } < 7 . 7 3 4 9 6$ 时,塑性破坏为结构的失效机制,当 $\overline { { r } } > 7 . 7 3 4 9 6$ 时,弹性屈曲为结构的失效机制！

![](images/b9fff08762a9f1beac43ff377295ae3cf05a24ff12a9631892663d9320366f0d.jpg)  
图16:圆柱壳混凝土3D打印,在混凝土参数固定,打印参数固定的影响下，有效长度与失效长度区域区分图.

如图13所示，当弹性屈曲长度 $\overline { { l } } _ { c r }$ 与塑性破坏长度 $\bar { l } _ { p }$ 通过Suiker数 $\overline { { \Lambda } }$ 联系起来时，可将有效长度与失效长度二者区域进行区分,弹性屈曲与塑性破坏二者区域进行区分.图13中，蓝色区域 $B$ 为有效长度区域.黄色区域 $c$ 为塑性破坏区间,红色区域 $D$ 为弹性屈曲区间.在参数固定的实际柱壳打印过程中，通过选择曲率大小,或者通过在不同失效区域采用相对应的辅助手段进行结构增强的方式，以达到预期打印高度.

# 5结论

为了提高3D打印直立墙的整体稳定性，我们提出了一个简单可行的普适方案，即适当增加直立墙沿轮廓方向的曲率将直立墙沿轮廓方向打印成波纹形状。直立波纹墙每个波纹可以是圆柱形也可以不是，同时其曲率也可以变化。为了验证我们的方案，本文在Suiker等人工作的基础上，通过增加曲率把直立板墙扩展到直立波纹墙，并对直立柱壳墙整体稳定性进行了细致研究。发现柱壳形直立墙的临界屈曲高度是矩形直墙的2倍多，表明增加直立墙沿轮廓方向的曲率是提高直立墙整体稳定性的合理方案。力学上，这个方案之所以可以提高直立墙整体稳定性本质上是通过增加曲率提高了直立墙的整体拓扑刚度，是提高直立墙整体稳定性的普适方法，而直立波纹墙结构是提高直立墙整体稳定性的简单可行的构形。具体可总结出以下六个结论：

(1)参数模型描述的是打印进程中均质圆柱壳到非均质圆柱壳在自重作用下屈曲长度的变化特性,即用公式描述了圆柱壳逐层打印过程中，结构力学性能在空间中不均匀的情况下,得出其屈曲行为的分析结果，且符合一般事实规律.

(2)在具体研究中,本文将每个波纹视为单胞进行研究,取单胞为柱壳形直立墙时发现,其屈曲长度对于曲率 $\overline { { k } }$ 有着较大的敏感性，随着曲率的减小,相同的无量纲固化速率增量 $d \overline { { \xi } }$ ，将会导致更大的屈曲长度增增量 $d \bar { l } _ { c r }$

(3)标度比曲线图(9)(10)描述的为标度比 $\bar { l } _ { c r } / \bar { l } _ { p }$ 曲线随固化速率 $\overline { { \xi } }$ 的变化趋势,可用于研究分析两种破坏机制的竞争关系.由式(33)所决定的Suiker数 $\overline { { { \Lambda } } }$ 描写的是塑性破坏与弹性屈曲分界,当 $\bar { l } _ { c r } / \bar { l } _ { p } > \overline { { \Lambda } }$ ，为塑性破坏,反之则为弹性屈曲.其中固化比 $\beta$ 参数对标度比曲线的变化趋势有很大的影响.其中 $\overline { { \Lambda } }$ 由材料的初始参数决定，固化比 $\beta$ 由材料的固化参数决定.这两个参数决定了弹性屈曲与塑性破坏这两种失效机制的主导地位.

(4)在数值结果与有限元结果的对比分析结果的差 异,我把其归结于我所建立的参数模型的简化,对于 真实混凝土打印参数，还是能较好的符合.

(5)采取了定量分析的方式,加入曲率 $\overline { { k } }$ 的影响,对比研究了文献[22]中矩形布置直墙结构与柱壳结构在3D打印进程中的失效形式,发现柱壳比矩形布置直墙结构的稳定性提升了2.15倍.与此同时,如图(13)所示,利用Suiker数∧,划分出了在一定曲率范围内的有效长度与失效长度区域区分图,可针对性的进行结构增强.

(6)如图(14)所示,利用Suiker数，可划分出一定曲率范围内的有效长度与失效长度区域区分图,在此基础上,可针对性的对结构进行增强.

在未来的工作中,将圆柱形单胞结构扩展至变曲率以及整个波纹墙进行研究.针对波纹墙中每个波纹,在参数给定的情况下,理论上存在材料使用率最高,结构稳定性最强的一个波形最优解

# 参考文献

1Paul GM,Rezaienia A，WenP，etal．Medical Applications for 3D Printing:Recent Developments.Missouri Medicine,2018, 115(1):75-81 2 Mathias W,Sebastian T,Christoph H.Rapid manufacturing of automotive polymer series parts:A systematic review of processes, materials and challenges.Additive Manufacturing,2020,36 3WongKV,Hernandez A.A Review of Additive Manufacturing. Isrn Mechanical Engineering,2012,2012:30-38

4KumarLJ,Krishnadas Nair CG.Current Trends of Additive Manufacturing in the Aerospace Industry. Advances in 3D Printing & Additive Manufacturing Technologies,2017:39-54   
5Le-Bail A,ManigliaB C,Le-BailP.Recent advances and future perspective in additive manufacturing of foods based on 3D printing. Current Opinion in Food ence,2020,35:54-64   
6 Roussel N,Spangenberg J,Wallevik J,et al. Numerical simulations of concrete processing:From standard formative casting to additive manufacturing.Cement and Concrete Research,2020,135:106075   
7 Bos F,Wolfs R,Ahmed Z,et al. Additive manufacturing of concrete in construction: potentials and challenges of 3D concrete printing.Virtual Physical Prototyping,2016:209-225   
8 Astm standard f2792,standard terminology for additive manufacturing technologies.2013.URL   
9 Bourell D,Chen Y ,Zhou C,et al. A layerless additive manufacturing process based on CNC accumulation. Rapid Prototyping Journal,2011,17(3):218-227(10)   
10 Williams C B,Mistree F,Rosen DW.A Functional Classification Framework for the Conceptual Design of Layered Manufacturing Technologies//ASME 2Oo8 International Design Engineering Technical Conferences and Computers and Information in Engineering Conference.2008   
11 Gao W,Zhang YB,Devarajan R,The status,challenges,and future ofadditive manufacturing in engineering.Computer-Aided Design, 2015,69:65-89   
12 David L B,Ming C L,and David WR .Roadmap for Additive Manufacturing,University of Texas at Austin,Austin TX,2009   
13 Fatemeh H, Farhad A．Additive manufacturing of cementitious composites:Materials,methods,potentials,and challnges.Construction and Building Materials,2019,218:582-609   
14 陈玲钰，张朝弼．基于BIM技术的3D打印装配式建筑应 用探讨//2020国际绿色建筑与建筑节能大会论文集,第十六届 国际绿色建筑与建筑节能大会暨新技术与产品博览会,苏州 市,2020年8月.北京：中国城市出版社,2020.659-661   
15 王香港,王申,贾鲁涛等.3D打印混凝土技术在新冠肺炎防疫方 舱中的应用.混凝土与水泥制品,2020,000(004):1-4,13   
16 陈蕾.突发疫情下BIM $+ 3 \mathrm { D }$ 打印的装配式建筑技术组合应用的优 势.武汉交通职业学院学报,2020,022(001):81-84   
17 侯泽宇,张宇,张超等.3D打印混凝土力学性能试验方法.混凝土 与水泥制品,2019,283(11):5-9   
18 雷波,解文峰.一种3D打印混凝土材料的试验研究.新型建筑材 料,2020,047(002):72-76   
19 马国伟,柴艳龙,王里等.3D打印陶砂轻质混凝土的制备与力学性 能测试.实验力学,2020.35(1):58-66   
20 马国伟,柴艳龙,王里等.3D打印陶砂轻质混凝土的制备与力学性 能测试.实验力学,2020.35(1):58-66   
21 段严,秦先涛.3D打印混凝土相关性能研究进展.混凝土与水泥制 品,2020(09):5-10   
22 A.S.J. Suiker.Mechanical performance of wall structures in 3D printing processes:Theory,design tools and experiments. International Journal of Mechanical Sciences,2018,137:145-170   
23 Bos F, Wolfs R R.,Ahmed Z Z,et al. Additive manufacturing of concrete in construction: potentials and challenges of 3D concrete printing. Virtual and Physical Prototyping,2016,11(3): 209-225   
（20 $2 4 { \mathrm { ~ V } } .$ Mechtcherine,F.P.Bos,A. Perrot,et al.Extrusion-based additive manufacturing with cement-based materials- Production steps, processes,and their underlying physics:A review. Cement and Concrete Research,2020,132   
25 Timoshenko SP. Strength of Materials.Lancaster Press,Inc.,Lancaster, PA; 1947   
26 Wolfs RJM,Bos FP,Salet TA M.Early age mechanical behaviour of 3D printed concrete: Numerical modeling and experimental testing.Cement & Concrete Research ,2018,106:103-116   
27 Vardoulakis I, Sulem J.Bifurcation Analysis in Geomechanics. Black Academic Professional, London; 1995   
28 Lim C w, Ma YF.Computational p-element method on the effects of thickness and length on self-weight buckling of thin cylindrical shells via various shell theories.Computational Mechanics,2003, 31:400 -408   
29 Suiker A SJ,Wolfs RJM,Lucas SM,et al. Elastic buckling and plastic collapse during 3D concrete printing. Cement and Concrete Research,2020,135:106016   
30 Wolfs RJM,Suiker A SJ.Structural failure during extrusion-based 3D printing processes. International Journal of Advanced Manufacturing Technology,2019,104(1-4):1-20   
31 祝恩淳,MandalP,CalladineCR.轴压圆柱薄壳的屈曲分析.土 木工程学报,2001(03):20-24+30   
32ReddyJN,JrJHS .General buckling of stiffened circular cylindrical shells according to a layerwise theory. Computers & Structures, 1993,49(4):605-616   
33 周承倜.弹性稳定理论.四川人民出版社,1982   
34 Timshenko SP, Gere JM. Theory of Elastic Stability.2nd ed.New York: Dover Publications Inc,2009   
35 Timoshenko SP, Woinowsky-Krieger S.Theory of Plates and Shells. McGraw-Hill Book Company, Singapore,1959   
36 Calladine CR,Barber JN .Simple Experiments on Self-Weight Buckling of Open Cylindrical Shels. Journal of Applied Mechanics,1970,37(4):1150   
37MillerJR,WeaverPM,JOHNSDJ. Self-weight-buckling of vertical circular cylindrical shells.AIAA Journal,1973   
38 Kumar,Yajuvindar Lal,R.The vibration and buckling of freely supported non-homogeneous orthotropic conical shels subjected to different uniform pressures.Journal of Applied Mechanics,2011, 061012   
39 Wang Y Q,Liu YF.Free vibration and buckling of polymeric shells reinforced with 3D graphene foams. Results in Physics,2019, 14:102510