# 基于多入渗模型的荒漠砂质土壤积水入渗模拟对比

周宏1.2

（1.西北师范大学旅游学院,西北师范大学河西走廊研究院,甘肃 兰州730070;2.中国科学院西北生态环境资源研究院,中国生态系统研究网络临泽内陆河流域研究站，甘肃 兰州730000)

摘要：包气带土壤水分人渗在水文循环中起着至关重要的作用,深人了解降雨-积水-人渗过程的相互关系对评估荒漠环境下土壤水分补给和降水再分配具有重要意义。本研究以自然沙丘的丘间低地为研究对象，通过土壤剖面入渗原位观测试验。采用Kostiakov Green-Ampt、Philip入渗模型和 Hydrus-1D、Hydrus-2D/3D水文模型模拟了土壤水分垂直人渗过程,旨在寻求土壤积水人渗可接受的方法。模拟与实测结果比较表明:综合考虑平方和误差、均方根误差等验证指标，Philip模型能够预测砂土入渗率、累积入渗量和湿润锋推进过程,并且整个湿润区,Hydrus-3D模拟土壤含水量的效果明显优于Hydrus-2D，RMSE均值和 $R ^ { 2 }$ 系数分别达到了 $0 . 0 1 8 ~ \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 }$ 和0.93。综上所示,Philip与Hydrus-3D模型结合可有效地估算砂土积水入渗参数和模拟水分传输过程,进而提高土壤水分入渗研究效率。

关键词：包气带；积水人渗；数值模拟；砂质土壤

入渗是指水分进入土壤的过程，而土壤水分入渗作为水文循环中关键环节，对连接地表水资源和降雨以及调控水分分配至关重要[1-2],许多学者基于不同尺度、不同土壤和气候区域进行了深入研究[3]。在非均质土壤中提出了用以表征入渗速率、累积入渗量等参数入渗模型，包括Kostiakov和Horton经验模型,Philip近似物理模型和Green-Ampt、基于Rich-ard方程算法的Hydrus-1D/2D/3D等物理模型。但不同土壤条件中模型应用范围存在差异，Kostiakov方程简单，能够很好地拟合实测入渗数据，但其参数无物理意义,无法解析入渗过程详细信息[4-5],Philip是估算最终入渗速率较常用的模型，已在砂质土壤[6]、黏土-壤土农田中得到了验证[7-8]。Green-Ampt模型主要用于均匀土壤介质中的积水人渗，借助其简便性和物理基础，扩展模拟了一系列条件下的入渗、降雨和径流过程[9-12]。非饱和水分运移过程模拟主要采用基于质量守恒定律和达西定律的Rich-ards方程来表达[13],但Richards方程通常用非线性描述，无法求解析解，导致计算过程较复杂，特别在复杂的初始和边界条件中。由美国农业部盐渍土实验室开发的Hydrus-1D软件可广泛用于模拟饱和-非饱和介质中一维土壤水分运移，其Hydrus-2D/3D软件应用于模拟二维或三维土壤水分运移和空间分布,并已获得大量的验证和应用[14-16]

干旱区绿洲荒漠区有许多代表性的景观单元类型,如荒漠、沙丘和农田等[17]。其中沙丘及其丘间低地在荒漠生态系统水力连接和水循环中扮演着重要的角色[18],事关荒漠生态系统的结构功能演化和绿洲稳定。在年均降水量小于 $2 0 0 \mathrm { m m }$ 干旱区,降水具有降水稀少、变率大、历时短等特征[19],尽管降水量少，但确是干旱生态系统中唯一水分补给来源，尤其是储存在浅层土壤水分调控地表径流和降雨入渗及其再分配过程[20]。水分入渗作为土壤水文过程重要组成部分，许多学者已针对不同尺度的干旱荒漠生态系统土壤包气带水分入渗方面开展了广泛研究[21]。积水入渗是由于入渗强度小于降雨强度导致一种压力入渗[22],尤其在土壤结皮较厚的干旱区，水分停留时间延长，相应入渗量会降低，易导致积水人渗现象发生，而在丘间低地入渗速率降低，会导致下垫面土壤含水率提高[23]

国内外有关土壤人渗过程研究方法较多，如土柱回填法、单双环入渗、Hood土壤入渗仪等，其中采用单环定水头对水分入渗进行原位测量，可用于估算土壤水分入渗特性[2.24-25]。然而,由于野外试验需要花费大量的时间和费用，而简单、可靠的渗透试验数据处理方法显得尤为必要。但由于土壤异质性，导致大量入渗模型在模拟土壤水分变化时仍然有很大局限性。因此，不同时空条件下，土壤水分运移过程模型的识别和选择仍需不断尝试，基于此，本研究通过野外原位入渗试验，分析砂质土壤中水流入渗过程并评价不同模型在土壤水分入渗模拟中的性能，旨在寻找降雨条件下适宜模型，以便合理预测沙丘积水入渗过程，提升对荒漠沙丘局地土壤包气带水分运移及交换过程认知。

# 1材料与方法

# 1.1 研究区概况

研究在巴丹吉林沙漠北部边缘的中国科学院临泽内陆河流域研究站进行，该站属于中国生态系统研究网络（CERN），地理位置位于 $1 0 0 ^ { \circ } 9 ^ { \prime } 3 0 ^ { \prime \prime } \mathrm { E }$ ，$3 9 ^ { \circ } 2 4 ^ { \prime } 4 1 ^ { \prime \prime } \mathrm { N }$ ,海拔 $1 3 8 1 \mathrm { ~ m ~ }$ 。年均气温 $7 . 5 ~ \mathrm { { ^ \circ C } }$ ,最高气温 $3 9 ~ \mathrm { ^ { \circ } C }$ ，最低气温 $- 2 7 \ \mathrm { { ^ circ C } }$ ,年均潜在蒸发量变化为$1 9 0 0 { \sim } 2 0 8 8 ~ \mathrm { m m }$ ，全年湿度变化为 $7 . 3 \% { \sim } 8 0 . 9 \%$ 。多年平均降雨量为 $1 2 0 ~ \mathrm { m m }$ ,高峰出现在7—9月。降雨是研究区域最敏感的气象因子，2006—2017年该区域共接收到降雨事件约500次(图1)，地下水埋深约为 $4 . 9 \mathrm { m }$ ,地下水的饱和毛管上升不会影响表层土

壤水分。

# 1.2原位试验与设计

在选定的试验区开展单环入渗试验，首先去除土壤表面可能阻碍入渗环插入的残留物，然后用落锤将铁环夯实，嵌人深度约为 $5 \mathrm { c m }$ （铁环尺寸：直径$2 0 \ \mathrm { c m }$ ，高度为 $3 0 \ \mathrm { c m }$ )。此外，要注意保持铁环边缘与土壤表面垂直，并尽量减少对土壤扰动，试验开始前在环内垫上滤纸，以防止水流破坏土壤表面，造成水头不均匀(图2)，并沿着入渗环下端中心位置插入土壤水分观测探头，探头插人土壤剖面深度依次为 $1 0 \ \mathrm { c m } \cdot 2 0 \ \mathrm { c m } \cdot 4 0 \ \mathrm { c m } \cdot 6 0 \ \mathrm { c m } \cdot 8 0 \ \mathrm { c m }$ ，数据采集器连续收集土壤水分变化值，时间间隔 $1 ~ \mathrm { m i n }$ （图2）。

# 1.3土壤样品收集与分析

在研究区 $0 { \sim } 8 0 ~ \mathrm { c m }$ 内用土钻分层采集原状土壤样品，土样均来自入渗剖面中心，然后烘干法求土壤容重，浸泡法测饱和含水量，激光粒度仪获取土壤粒径组成，定水头法求饱和导水率 $K _ { s }$ ,土壤水力参数是水分运移模拟的关键因素，主要特征数据见表1。

# 2模型描述

# 2.1 Hydrus-1D/3D模型理论

三维水流运动可以用如下Richards方程来描述：$\begin{array} { r } { \frac { \partial \theta } { \partial t } = \frac { \partial } { \partial x } \bigg [ K ( h ) \frac { \partial h } { \partial x } \bigg ] + \frac { \partial } { \partial y } \bigg [ K ( h ) \frac { \partial h } { \partial y } \bigg ] + \frac { \partial } { \partial z } \bigg [ K ( h ) \frac { \partial h } { \partial z } \bigg ] - S } \end{array}$ (1)

式中： $\theta$ 为体积含水率 $( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } )$ ； $h$ 为压力水头$( \mathrm { c m } )$ )；t为时间 $\left( \mathrm { h } \right)$ $K ( h )$ 为非饱和导水率函数( $_ \mathrm { c m } \cdot$ $\mathbf { d } ^ { - 1 }$ ）； $z$ 为向上正的空间坐标 $\mathbf { \Pi } ( \mathbf { \Pi } _ { \mathrm { m } } ) ; S$ 为汇源项，通常表示根吸水率 $\mathrm { ( S ^ { - 1 } ) }$ ,本试验在裸露沙丘进行，不考虑根系吸水。其中简化的一维水流运动方程如下：

![](images/50ab8b872fe23d4b0627b4714141b1ccc8b224572ce6a29334cf397d19a40ff3.jpg)  
图1试验区多年降雨状况和干旱区沙丘-丘间低地地貌   
Fig.1Location of experimental site,rainfalland image of a mature dune slack in arid region

![](images/88cad12ab793704dcaee01a95232715b01d8ce2fc7dae55cc60ffa33bf03f453.jpg)  
图2单环试验示意图及土壤包气带剖面和探头深度  
Fig.2 The profiles of soil vadose zone and schematic diagram of single ring experiment

表1试验场地土壤水力学和物理特性  
Tab.1 Soil hydraulic and structural properties in experimental site   

<html><body><table><tr><td rowspan="2">土壤深度 /cm</td><td rowspan="2">容重/(g·cm3)</td><td rowspan="2">初始含水量 /(cm³·cm-3)</td><td colspan="3">土壤粒径分布/%</td><td rowspan="2">土壤孔隙 度/%</td><td rowspan="2">土壤质地</td></tr><tr><td>黏土(<0.002 mm)</td><td>粉土(0.002~0.05 mm)</td><td>砂土(>0.05 mm)</td></tr><tr><td>10</td><td>1.45</td><td>0.04</td><td>1.73</td><td>10.01</td><td>88.26</td><td>45.28</td><td>砂土</td></tr><tr><td>20</td><td>1.40</td><td>0.01</td><td>1.28</td><td>7.1</td><td>91.63</td><td>46.42</td><td>砂土</td></tr><tr><td>40</td><td>1.42</td><td>0.02</td><td>1.28</td><td>6.14</td><td>92.42</td><td>46.42</td><td>砂土</td></tr><tr><td>60</td><td>1.41</td><td>0.02</td><td>0.59</td><td>4.53</td><td>94.88</td><td>46.79</td><td>砂土</td></tr><tr><td>80</td><td>1.43</td><td>0.03</td><td>0.79</td><td>5.66</td><td>93.55</td><td>46.04</td><td>砂土</td></tr></table></body></html>

$$
\frac { \partial \theta } { \partial t } = \frac { \partial } { \partial z } \biggl [ K ( h ) \biggl ( \frac { \partial h } { \partial z } + 1 \biggr ) \biggr ] - S
$$

2.1.1土壤水力性质用VanGenuchten-Mualem(VG)模型描述土壤水分特征曲线，其土壤水力函数如下：

$$
S _ { e } ( \varphi ) = { \frac { \theta ( \varphi ) - \theta _ { r } } { \theta _ { s - \theta _ { r } } } } = \left[ 1 + \left( | \alpha \varphi | \right) ^ { n } \right] ^ { - m }
$$

$$
\begin{array} { r } { K ( \varphi ) = K _ { s } S _ { e } ^ { l } \Big [ 1 - \Big ( 1 - S _ { e } ^ { \bigvee _ { m } } \Big ) ^ { m } \Big ] ^ { 2 } } \end{array}
$$

式中： $\theta _ { r }$ 和 $\theta _ { s }$ 分别为土壤残余含水量和土壤饱和含水量 $\left( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } \right.$ ）； $S _ { e }$ 为饱和度(无量纲)； $K _ { s }$ 为饱和导水率 $( \cos \cdot \mathrm { d } ^ { - 1 } ) ; n$ 为孔径分布指数(无量纲）； $\scriptstyle { m = 1 - 1 / n }$ 为土壤水分特征曲线参数； $\varphi$ 为土壤基质势; $l$ 为孔隙连通性参数(无量纲)。基于VG模型土壤水力参数见表2。

# 2.1.2 初始和边界条件

（1）基于Hydrus-2D二维计算模拟

模拟区域入渗面以上DA、BC为不透水边界；地表DE、FC为大气边界，下底面AB为自由排水边界；EF在入渗开始后很快达到饱和，为定水头边界，其边界和初始条件如下：

$\textcircled{1}$ 初始条件：

$\theta \big ( x , y , 0 \big ) = \theta _ { 0 } , 0 \mathrm { ~ c m } \leqslant x \leqslant 2 0 0 \mathrm { ~ c m } ; 0 \mathrm { ~ c m } \leqslant y \leqslant 1 0 0 \mathrm { ~ c m } ;$ （204号$\scriptstyle t = 0$ （204号

式中： $\theta _ { 0 }$ 为初始含水量 $( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } )$ 。

$\textcircled{2}$ 边界条件：

DE、FC边界: $\begin{array} { r } { - \ K ( h ) \frac { \partial h } { \partial y } + K ( h ) = E ( t ) , 0 \ \mathrm { c m } \leqslant x \leqslant } \end{array}$ $2 0 0 \mathrm { c m }$ $y { = } 1 0 0 \mathrm { c n }$ $t > 0$

DA、BC 边界：- $K ( h ) \frac { \partial h } { \partial y } = 0$ $0 ~ \mathrm { c m } { \leqslant } x { \leqslant } ~ 2 0 0 ~ \mathrm { c m }$

表2试验地不同剖面土壤水力参数组成  
Tab.2Soil parameters fordifferent soil layers in the experiment site   

<html><body><table><tr><td>土壤深度/cm</td><td>饱和含水量/(cm·cm3)</td><td>残余含水量/(cm·cm)</td><td>进气值/cm</td><td>孔径分布指数</td><td>饱和导水率/(cm·d)</td></tr><tr><td>10</td><td>0.373</td><td>0.062</td><td>0.012</td><td>2.292</td><td>26.85</td></tr><tr><td>20</td><td>0.376</td><td>0.071</td><td>0.014</td><td>2.600</td><td>38.41</td></tr><tr><td>40</td><td>0.363</td><td>0.059</td><td>0.013</td><td>2.301</td><td>40.28</td></tr><tr><td>60</td><td>0.358</td><td>0.061</td><td>0.01</td><td>2.475</td><td>40.54</td></tr><tr><td>80</td><td>0.375</td><td>0.082</td><td>0.016</td><td>2.145</td><td>16.76</td></tr></table></body></html>

$0 ~ \mathrm { c m } { \leqslant } y { \leqslant } 1 0 0 \mathrm { c m }$

EF边界： $\theta \left( 0 , y , t \right) = \theta _ { s }$ ， $- K ( h ) \frac { \partial h } { \partial y } + K ( h ) = H ( t ) , t >$ $0 ; y = 0$

AB边界： $- K ( h ) \frac { \partial h } { \partial y } + K ( h ) = 0$ （ $t { > } 0$ $0 ~ \mathrm { c m } { \leqslant } x { \leqslant } 2 0 0$ cm; $y { = } 0$ 式中： $E ( t )$ 为人渗速率； $H ( t )$ 为恒定水头。

(2）基于Hydrus-3D三维计算模拟

三维模拟区域入渗面OPNM为大气边界；侧面OPGH、GPMJ、MNIJ和HION为不透水边界，下底面GHIJ为自由排水边界；以直径 $R { = } 2 0 ~ \mathrm { c m }$ 入渗圆面开始后很快达到饱和，为定水头边界，其边界和初始条件如下：

$\textcircled{1}$ 初始条件：

$\theta \big ( x , y , z , 0 \big ) = \theta _ { 0 } , \textnormal { O c m } \leqslant x \leqslant 2 0 0 \textnormal { c m } ; \textnormal { O c m } \leqslant y \leqslant 1 0 0$ cm; $0 \mathrm { c m } { \leqslant } z { \leqslant } 1 0 0 \mathrm { c m } ; t { = } 0$

$\textcircled{2}$ 边界条件：

OPNM边界： $- K ( h ) \frac { \partial h } { \partial y } = 0$ ， $0 ~ \mathrm { c m } { \leqslant } x { \leqslant } 2 0 0 ~ \mathrm { c m } ; ~ ($ ）$\mathrm { c m } { \leqslant } z { \leqslant } ~ 1 0 0 \mathrm { c m } ; y { = } 1 0 0 \mathrm { c m } ; t { > } 0$ OPGH、GPMJ、MNIJ 和 HION 边界： $- K ( h ) \frac { \partial h } { \partial x } =$ ’ $\scriptstyle x = 0 \ { \mathrm { c m } }$ 或 $2 0 0 \ \mathrm { c m }$ $- K ( h ) \frac { \partial h } { \partial z } = 0$ cm, $z { = } 0 \ \mathrm { c m }$ 或100cm

GHIJ边界： $- K ( h ) \frac { \partial h } { \partial x } + K ( h ) \frac { \partial h } { \partial z } + K ( h ) = 0 ,$ $t { > } 0$ $0 \mathrm { c m } { \leqslant } x { \leqslant } 2 0 0 \mathrm { c m } ; 0 \mathrm { c m } { \leqslant } z { \leqslant } 1 0 0 \mathrm { c m } _ { \mathrm { ~ o ~ } }$ 。

二维与三维模拟均采用 $1 \ \mathrm { c m }$ 压力水头作为单环入渗下的水流边界条件(图3)，并将模拟区域离散成径向网格间距为 $2 \mathrm { c m }$ 、垂直网格间距为 $1 \mathrm { { c m } }$ 的有限元，总模拟时长 $1 2 \mathrm { h }$ ○

# 2.2入渗模型理论

2.2.1Green-Ampt Green-Ampt模型最初是利用达西定律对定水头条件下土柱积水入渗进行分析，入渗方程如下：

$$
i = K _ { s } \frac { Z _ { f } + H _ { 0 } + S _ { f } } { Z _ { f } } = K _ { s } \Bigg ( 1 + \frac { H _ { 0 } + S _ { f } } { Z _ { f } } \Bigg )
$$

$$
Z _ { f } = \frac { I } { \theta _ { s } - \theta _ { i } }
$$

$$
i = \frac { \mathrm { d } I } { \mathrm { d } t } K _ { s } \Bigg [ 1 + \frac { \big ( \theta _ { s } - \theta _ { i } \big ) S _ { f } } { I } \Bigg ]
$$

式中： $I$ 为累积人渗量 $( \mathrm { c m } ) { \mathrel { \mathop : } } i$ 为入渗率 $( \mathbf { c } \mathbf { m } \cdot \mathbf { m } \mathbf { \dot { n } } ^ { - 1 } ) .$ ； $K _ { s }$ 为饱和导水率； $S _ { f }$ 为湿润锋面吸力； $Z _ { f }$ 为概化的湿

![](images/3470666d2d31b700c3456704140d0827133fc1ab74c1568cbc7c12d0fded605a.jpg)  
图3Hydrus-2D/3D模拟区域及边界条件  
Fig.3 The Hydrus-2D/3D simulation domain and boundary conditions

润锋深度 $( \mathrm { c m } ) ; \theta _ { i }$ 为初始土壤含水量 $( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } .$ ）

分层均质土壤入渗时，通过整合Green-Ampt模型推导出累积入渗量和湿润锋随时间变化的隐函数，分别表示如下：

$$
I = \sum _ { j = 1 } ^ { N } D _ { j } \big ( \theta _ { s , j } - \theta _ { i , j } \big ) + \big ( Z _ { f } - \sum _ { j = 1 } ^ { N } D _ { j } \big ) \big ( \theta _ { s , N + 1 } - \theta _ { i , N + 1 } \big )
$$

式中： $D$ 为土层厚度( $( \mathrm { c m } )$ ；下标 $i , s , j , N$ 分别表示初始状态、饱和状态、土层数和饱和层数。

$$
\begin{array} { r l r } {  { t - t _ { N } = \frac { \theta _ { s , N + 1 } - \theta _ { i , N + 1 } } { K _ { s } } } } \\ & { } & { \Bigg [ \Big ( Z _ { f } - Z \Big ) - \Big ( H _ { 0 } + S _ { f } \Big ) \mathrm { l n } \Bigg ( \frac { Z _ { f } + S _ { f } + H _ { 0 } } { Z + S _ { f } + H _ { 0 } } \Big ) \Bigg ] } \end{array}
$$

式中： $t _ { N }$ 为湿润锋到达第 $N$ 层界面所需时间 $( \mathrm { m i n } )$ 。

2.2.2Philip Philip模型最初由Philip提出,累积入渗量和入渗率表示为：

$$
i ( t ) = 0 . 5 S t ^ { 1 / 2 } + A
$$

$$
I ( t ) = S t ^ { 1 / 2 } + A t
$$

式中： $A$ 是关于土壤性质和水分导水系数函数( $\operatorname { i } \operatorname { c m } \cdot$ $\operatorname* { m i n } ^ { - 1 }$ );S为吸水率，是土壤基质势函数 $\left( \mathrm { c m } \cdot \mathrm { m i n } ^ { - 0 . 5 } \right.$ ）。

$$
Z _ { f } \Delta \theta = \frac { S ^ { 2 } } { 2 K _ { s } } - S _ { f } \Delta \theta
$$

式中： $\Delta \theta$ 为饱和含水量和初始含水量的差值。

2.2.3Kostiakov-Lewis修正后长周期的Kostiakov模型描述为[26]：

$$
\dot { \iota } \left( t \right) = B t ^ { - c } + \dot { \iota } _ { f }
$$

$$
I ( t ) = \frac { B } { 1 - C } t ^ { 1 - c } + i _ { f } t
$$

式中： $B , C$ 分别为方程参数 $\left( C { > } 0 , 0 { < } B { < } 1 \right) ; i \left( t \right) , \dot { \iota } _ { f }$ 分别为入渗率和稳定入渗率。

# 2.3模拟效果评价

模拟值与观测值比较用以评价模型性能，本研究以决定系数 $\left( R ^ { 2 } \right)$ 和均方根误差(RMSE)作为最终评价指标。

$$
R ^ { 2 } = 1 - { \frac { \sum _ { i = 1 } ^ { n } \bigl ( X _ { \mathrm { m o d } , i } - { \overline { { X _ { \mathrm { o b s } } } } } _ { i } \bigr ) ^ { 2 } } { \sum _ { i = 1 } ^ { n } \bigl ( X _ { \mathrm { o b s } , i } - { \overline { { X _ { \mathrm { o b s } } } } } _ { i } \bigr ) ^ { 2 } } }
$$

$$
{ \mathrm { R M S E } } = { \sqrt { \frac { \sum _ { i = 1 } ^ { n } \bigl ( X _ { \mathrm { o b s } , i } - X _ { \mathrm { m o d } , i } \bigr ) ^ { 2 } } { n } } }
$$

式中： $X _ { \mathrm { o b s } , i }$ 为观测值； $X _ { \mathrm { m o d } , i }$ 为模拟值; $\overline { { X _ { \mathrm { o b s } , l } } }$ 为观测样本均值, $\mathrm { o b s } , i$ 代表第 $i ( 1 , 2 , \cdots , n )$ 个观测值; $n$ 为观测数据总个数。RMSE指标值越小，表明模拟误差越小，而 $R ^ { 2 }$ 的指标值越接近1,表明模拟精度越高，

拟合度越好。

# 3结果与分析

# 3.1实测数据

结果表明，试验开始后人渗速率持续下降，300min左右达到稳定入渗速率 $0 . 5 7 \ \mathrm { c m \cdot m i n ^ { - 1 } }$ （图 $\mathrm { 4 a }$ ），累积入渗量随时间增加而递增，观测时段内累积入渗量达到 $3 9 8 ~ \mathrm { c m }$ （图4b)，入渗开始后湿润锋同时沿竖直和水平两个方向快速推进， $2 0 0 \mathrm { { m i n } }$ 后推进速度趋缓，人渗结束后，水平方向湿润锋距离较垂直方向湿润锋距离增加了 $45 \%$ （图4c）。可以发现幂函数可以较好的拟合实测数据 $( R ^ { 2 } { = } 0 . 8 5$ )。然而，幂函数只是估算土壤水分人渗的一个简单的经验模型，无具体物理参数意义。此外，结果表明，在10\~80$\mathrm { c m }$ 深度内土壤各个剖面含水量差异明显(图4d)，达到稳态土壤含水量随土层深度增加而降低，但20cm剖面的最大含水率明显低于其他剖面，且均低于饱和含水量，这可能与容重、粒径构成等土壤性质差异有关。

# 3.2观测与模拟结果比较

3.2.1入渗速率4种水文模型的入渗率模拟值与观测值对比如图5所示。结果表明，入渗率的 $R ^ { 2 }$ 系数均值在0.75\~0.95,Philip的 $R ^ { 2 }$ 系数最高（0.95），Kostiakov的模拟结果略大于观测值，相反Green-Ampt的模拟结果略低于观测值，尤其在入渗后期。Hydrus-1D模拟结果与实测匹配较低，决定系数 $R ^ { 2 }$ 较小(0.79)。总之，荒漠砂质土壤积水入渗条件下，Philip较其他入渗模型能更好地描述土壤水分入渗过程。

3.2.2累积入渗量模拟与观测累积入渗量关系如图6所示，结果表明，4种模型累积入渗量模拟值均与实测数据有较好的相关性。而Philip模型 $R ^ { 2 }$ 最高，RMSE系数最低，Kostiakov模型RMSE次之（表3),但Hydrus-1D模型下RMSE值系数相对较高，表明高估了累积入渗量，尤其在人渗初期，但4种入渗模型 $R ^ { 2 }$ 系数均达到了0.98以上，因此，4种入渗模型均是预测砂土累积入渗量较为有效的模型，尤其是Philip 模型。

3.2.3湿润锋距离模拟与观测湿润锋距离之间的关系如图7所示,结果表明,Green-Ampt和Hydrus-1D模型的湿润锋距离模拟值与观测值差异较大，尤其是Hydrus-1D明显高估了湿润锋推进距离，其均值 $R ^ { 2 }$ 小于Philip模型。一种可能的解释是Hydrus-1D忽略了土壤水侧渗和气流,以往研究表明,Hy-drus-1D高估了湿润区的蓄水能力，但综合RMSE和

![](images/1bbec32434ed81a58579e50b870e307d1b3aba5fce39ac182727b434d09f46c5.jpg)  
图4观测时段的入渗速率、累积入渗量、湿润锋距离和土壤含水量变化 Fig.4Dynamic of observed infiltration rate,cumulative infiltration, depth of wetting front and soil water content during the study period

![](images/42203d423cc2ba0da165fa05dd6329d3905d1618dcb278763f79ead4638bca29.jpg)  
注：直线表示数据之间可能存在1:1关系。下同  
图5人渗速率模拟值与实测值比较  
Fig.5Comparison of simulated infiltration rate from models with observed result

![](images/12aa0ef0cd2414108727577fba362bcaa378d2e9c7395f0b999fdc4ff4d87128.jpg)  
图6累积入渗量模拟值与实测值比较

![](images/92b7b300b28af653bdf10233fc6a46ca4159f40a1265d4503aa7d83c9a434381.jpg)  
Fig.6 Comparison of simulated cumulative infiltration from models with observed result   
图7湿润锋距离模拟值与观测值比较   
Fig.7 Comparison of simulated wetting front depth from models with observed result

$R ^ { 2 }$ 均值结果可知,Philip模型对砂土湿润锋推进距离的预测效果较好。3.2.4 土壤含水量与Hydrus-2D模拟 基于Hy-drus-2D模拟土壤含水量如图8所示。结果表明，土

# 表3模拟结果拟合优度参数

Tab.3 Goodness-of-fit parameters for simulation resultswith models   

<html><body><table><tr><td rowspan="2">试验测定项目</td><td colspan="2">Kostiakov</td><td colspan="2">Green-Ampt</td><td colspan="2">Philip</td><td colspan="2">Hydrus-1D</td></tr><tr><td>RMSE/(cm³·cm-3)</td><td>R</td><td>RMSE/(cm·cm-3)</td><td>R</td><td>RMSE/(cm³·cm-3)</td><td>R</td><td>RMSE/(cm·cm-3)</td><td>R</td></tr><tr><td>入渗速率/(cm·min-1)</td><td>0.003</td><td>0.85</td><td>0.002</td><td>0.84</td><td>0.0003</td><td>0.95</td><td>0.004</td><td>075</td></tr><tr><td>累积入渗量/cm</td><td>0.08</td><td>0.98</td><td>0.35</td><td>0.97</td><td>0.04</td><td>0.99</td><td>1.38</td><td>0.98</td></tr><tr><td>湿润锋距离/cm</td><td>二</td><td>二</td><td>1.85</td><td>0.81</td><td>0.24</td><td>0.94</td><td>二</td><td>0.27</td></tr></table></body></html>

注：RMSE表示均方根误差， $R ^ { 2 }$ 表示决定系数。下同。

![](images/4fc4517d0f120d6fd8989cd71beabd22ef40fcb180f32bbcfe2460662f0d6de3.jpg)  
图8基于Hydrus-2D模拟土壤含水量与实测值比较   
Fig.8 Comparison of simulated soil water content by Hydrus-2D model with observed result

壤水分模拟值与观测值拟合度较低， $R ^ { 2 }$ 均值仅为0.82,尤其在表层 $0 { \sim } 1 0 \ \mathrm { c m } , R ^ { 2 }$ 仅为0.65，综合 $0 { \sim } 8 0 \mathrm { c m }$ 的RMSE和 $R ^ { 2 }$ 均值结果可知，Hydrus $- 2 \mathrm { D }$ 模型并不能很好地预测积水入渗条件下土壤水分变化过程。3.2.5 土壤含水量与Hydrus-3D模拟 基于Hy-drus-3D模拟土壤含水量如图9所示，结果表明，土壤含水量模拟值与观测值基本一致， $0 { \sim } 8 0 ~ \mathrm { c m }$ 土壤剖面的 $R ^ { 2 }$ 均值为0.93,RMSE均值为 $0 . 0 2 ~ \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 }$ （表4）。尽管较Hydrus-2D相比，Hydrus-3D对入渗后期土壤含水量预测较低，但是综合考虑 $R ^ { 2 }$ 和RMSE值，Hydrus-3D是描述和模拟砂土积水条件土壤含水量较为理想的选择。

![](images/4a3bc6d1bcab069e8a1aa5af9ccf350779f47f358448005f6b6f592584c813f3.jpg)  
图9基于Hydrus-3D模拟土壤含水量与实测值比较   
Fig.9 Comparison of simulated soil water content by Hydrus-3D model with observed resul

# 4讨论

# 4.1土壤水分入渗特性

单环积水入渗仪是测量土壤水分入渗速率的最常用方法之一，已被广泛用于评估和监测降雨入渗进入土壤过程。研究表明，随着时间的延长，入渗速率随着人渗量的增加而降低，最终达到稳定入渗率[27]。本研究发现,砂土的稳定入渗率为0.55$\mathrm { c m } \cdot \mathrm { m i n } ^ { - 1 }$ ,这与前人研究砂土入渗速率范围为 $0 . 2 \sim$ $0 . 7 7 \ \mathrm { c m \cdot m i n ^ { - 1 } }$ 结果相一致[28],结果差异可能由于土壤质地、初始土壤含水量和地表覆盖条件导致。土壤水分运移过程中，非饱和区水分湿润锋推进动力学特性研究具有重要的意义，研究指出，单环入渗受环下水分横向运动影响，其基质势通量在湿润锋处占主导地位[29],本研究发现湿润锋距离水平方向较垂直方向大。此外，在入渗发生的前 $1 0 0 \mathrm { m i n }$ 内，表4Hydrus-2D和Hydrus-3D模拟结果拟合度参数湿润锋推进速度随时间增加而减小，之后保持恒定不变(图10)，一种可能的解释是砂土引发的漏斗流在水平方向上受基质势驱动，而在垂直方向上受重力势驱动。

Tab.4 Goodness-of-fit parameters for simulation results betweenHydrus-2D and Hydrus-3D   

<html><body><table><tr><td rowspan="2">土壤深度/cm</td><td colspan="2">Hydrus-2D</td><td colspan="2">Hydrus-3D</td></tr><tr><td>RMSE /(cm³·cm-3)</td><td>R</td><td>RMSE /(cm·cm-3)</td><td>R</td></tr><tr><td>10</td><td>0.02</td><td>0.65</td><td>0.013</td><td>0.94</td></tr><tr><td>20</td><td>0.024</td><td>0.83</td><td>0.021</td><td>0.84</td></tr><tr><td>40</td><td>0.017</td><td>0.91</td><td>0.026</td><td>0.96</td></tr><tr><td>60</td><td>0.032</td><td>0.85</td><td>0.021</td><td>0.93</td></tr><tr><td>80</td><td>0.015</td><td>0.94</td><td>0.009</td><td>0.98</td></tr></table></body></html>

![](images/cad3a1fc51bceb7834cb2ee9fadd98c90d6c5bd37c05517edd9ea7a779faf702.jpg)  
  
图10垂直和水平两个方向湿润锋推进速度 Fig.10 Comparison of observed the velocity of the wetting front with two directions

先前研究表明，Philip模型可用于砂质土壤入渗速率与入渗时间关系预测[30],Zolfaghari等也做了类似报道[31],然而,Duan等[28]和Ogbe等[32]通过研究入渗模型对砂土水分入渗适应性发现,Hortons模型较适宜累积入渗量预测,Wang等[13]通过模拟与实测值比较，证实Hydrus-1D能够预测层状土柱砂土积水条件下的入渗速率。然而，由于模型参数和性能随土壤条件和时间的不同而存在差异，需要大量试验以确定入渗模型适用范围和条件。

# 4.2土壤剖面水分状况

土壤水分分布状况是影响干旱区荒漠植物根系吸水有效性的重要因素，本研究结果表明，土壤含水量表层高于深层，积水入渗导致土壤水分在整个湿润区呈不均匀非饱和状态分布，这可能与土层结构对土壤的持水性能影响有关，尽管整个剖面土壤质地为砂土，但由于各层之间粒径组成比例有差异，导致持水性略有不同,出现土壤含水量空间变异[33-34]。此外,Hydrus-3D较Hydrus-2D对土壤含水量数值模拟结果效果最佳，其优点是考虑了水分在土壤中的三维变饱和多孔介质运动。

# 5结论

以自然沙丘中的丘间低地为研究对象，通过单环入渗试验，以确定土壤水力参数，并分析了砂土在固定水头渗流区的土壤水分变化对入渗响应，以验证几种入渗模型在积水入渗条件下的适应性状况，取得以下主要结论：

（1）入渗初期入渗速率随时间急剧下降，之后趋于稳定，整个入渗过程中，水平湿润锋的推进速度较垂直方向快，入渗速率、累积入渗量和湿润锋深度与时间呈幂函数关系。

(2）受边界和初始条件以及土壤水力参数设置等因素影响，Hydrus-1D水文模型在砂土水分入渗模拟中表现欠佳，但当前试验条件下，通过性能评价指标系数比较，特定土壤环境中Philip较GreenAmpt、Kostiakov-Lewis和Hydrus-1D模型能够合理描述砂土入渗参数，反映较真实的土壤水动力过程。

(3）单环入渗试验需要同时考虑环内一维和环外三维水流过程，而Hydrus-3D模型基本能反映砂土不同剖面三维土壤水分变化。总之,结合Philip和Hydrus-3D水文模型确定砂土入渗是可行的，但此结果只是基于砂土，能否应用其他类型土壤水分入渗过程的评估有待进一步研究。

# 参考文献(References):

[1] Reynolds W D.An assessment of borehole infiltration analyses for measuring field-saturated hydraulic conductivity in the vadose zone [J].Engineering Geology,2013,159:119-130.   
[2] Bagarello V, Sferlazza S,Sgroi A.Comparing two methods of analysis of single-ring infiltrometer data for a sandy-loam soil[J].Geoderma,2009,149(3-4): 415-420.   
[3] Xiao B, Sun FH,Hu KL.Biocrusts reduce surface soil infiltrability and impede soil water infiltration under tension and ponding conditions in dryland ecosystem[J]. Journal of Hydrology,2019, 568: 792-802.   
[4] VerbistK,Torfs S,Cornelis W M,et al. Comparison of single-and double-ring infiltrometer methods on stony soils[J]. Vadose Zone Journal,2010,9(2): 462.   
[5]Alagna V,Bagarello V,Di Prima S,et al. Determining hydraulic properties of a loam soil by alternative infiltrometer techniques[J]. Hydrological Processes,2016,30(2): 263-275.   
[6]Wang XJ,Li HL, Yang JZ, et al. Measuring in situ vertical hydraulicconductivityin tidal environments[J].Advances in Water Resources,2014,70: 118-130.   
[7]Daly E,Porporato A.A review of soil moisture dynamics: From rainfall infiltration to ecosystem response[J].Environmental Engineering Science,2005,22(1): 9-24.   
[8]任杰,沈振中,杨杰,等.基于HYDRUS模型低温水入渗下土壤 水热运移模拟[J].干旱区研究,2016,33(2):246-252.[Ren Jie, Shen Zhengzhong,Yang Jie,et al. Simulation of water and heat transfer in soil under low-temperature water infiltration based on the HYDRUS model[J]. Arid Zone Research,2016,33(2): 246-252.]   
[9]Regalado C M,Riter A,AlvarezB,et al.Simplified method to esti mate the Green-Ampt wetting front suction and soil sorptivity with the Philip-Dunne faling-head permeameter[J]. Vadose Zone Journal, 2005,4(2): 291.   
[10]Putte A V, Govers G, Leys A,et al. Estimating the parameters of the Green-Ampt infiltration equation from rainfall simulation data: Why simpler is better[J].Journal of Hydrology,2013,476: 332- 344.   
[11]Huo W,Li Z, Zhang K,et al. GA-PIC: An improved Green-Ampt rainfall-runoff model with a physically based infiltration distribution curve for semi-arid basins[J].Journal of Hydrology,2020,586: 124900.   
[12]Zhang J,Lei TG,Chen T Q. Impact of preferential and lateral flows of water on single-ring measured infiltration process and its analysis[J]. Soil Science Society of America Journal,2O16, 80(4): 859.   
[13]Wang C Y,Mao X M, Hatano R. Modeling ponded infiltration in fine textured soils with coarse interlayer[J]. Soil Science Society of America Journal,2014,78(3): 745-753.   
[14]Sansoulet JL,Cabidoche Y M, Cattan P,et al. Spatially distributed water fluxes in an andisol under banana plants: Experiments and three-dimensional modeling[J]. Vadose Zone Journal,2008,7 (2): 819-829.   
[15]Mashayekhi P,Ghorbanidashtaki S, Mosaddeghi MR,et al. Different scenarios for inverse estimation of soil hydraulic parameters from double-ring infiltrometer data using HYDRUS-2D/3D[J]. International Agrophysics,2016,30(2): 203-210.   
[16]Kandelous M M, Simunek J. Numerical simulations of water movement in a subsurface drip irrigation system under field and laboratory conditions using HYDRUS- 2D[J].Agricultural Water Management,2010,97(7): 1070-1076.   
[17]Yi J, Zhao Y, Shao M A,et al. Hydrological processes and eco-hydrological effects of farmland-forest-desert transition zone in the middle reaches of Heihe River Basin,Gansu, China[J].Journal of Hydrology,2015,529:1690-1700.   
[18]Stratford C J,Robins N S,Clarke D,et al.An ecohydrological review of dune slacks on the west coast of England and Wales[J]. Ecohydrology,2013,6(1): 162-171.   
[19] Zhang C C,LiX Y, Wang Y,et al.Responses of two desert shrubs to simulated rainfall pulses in an arid environment,northwestern China[J]. Plant and Soil,2019,435(1): 239-255.   
[20]Diego Rivera,Mario Lillo,Stalin Granda.Representative locations from time series of soil water content using time stability and wavelet analysis[J]. Environmental Monitoring and Assessment,2014, 186(12): 9075-9087.   
[21]Wang S,Fu B J, Gao G Y,et al. Responses of soil moisture in different land cover types to rainfallevents in are-vegetation catchment area of the Loess Plateau, China[J]. Catena,2013,101: 122- 128.   
[22]Dohnal M, Vogel T,Dusek J,etal. Interpretation of ponded infiltration data using numerical experiments[J]. Journal of Hydrology and Hydromechanics,2016,64(3): 289-299.   
[23]Chamizo S, Cantón Y,Domingo F,et al.Evaporative losses from soils covered by physical and different types of biological soil crusts[J]. Hydrological Processes,2013,27(3): 324-332.   
[24]Cheng Q B,Chen X, Chen X H, et al.Water infiltration underneath single-ring permeameters and hydraulic conductivity determination[J].Journal of Hydrology,2011,398(1-2):135-143.   
[25] 石兰君,乔晓英,曾磊,等.甘肃黑方台黄土水分运移规律模拟 [J].干旱区研究,2018,35(4): 813-820.[Shi Lanjun,Qiao Xiaoying, Zeng Lei, et al.Loess moisture migration in Heifangtai of Gansu Province[J]. Arid Zone Research,2018,35(4): 813-820.]   
[26] Smith R E.The infiltration envelope: Results from a theoretical infiltrometer[J]. Journal of Hydrology,1972,17:1-21.   
[27]Uloma A R, Samuel A C,Kingsley I K. Estimation of Kostiakov’s infiltration model parameters of some sandy loam soils of IkwuanoUmuahia, Nigeria[J].Open Transactionson Geosciences,2014,1 (1): 34-38.   
[28]Duan R B,Fedler C, Borrell J.Field evaluation of infiltration models inlawn soils[J]. Irrigation Science,2011,29(5): 379-389.   
[29]Lewis JD.Assessment of a Single-ring Sprinkle Infiltrometer Method for Evaluating Soil- based Stormwater Management Practices [D].North Carolina,Raleigh: Graduate Faculty of North Carolina State University,2016.   
[30]Sihag P,Tiwari N K,Ranjan S.Modelling of infiltration of sandy soil using gaussian process regression[J]. Modeling Earth Systems and Environment,2017,3(3): 1091-1100.   
[31] Zolfaghari A A,Mirzaee S,Gorji M. Comparison of diferent models for estimating cumulative infiltration[J]. International Journal of Soil Science,2012,7(3): 108-115.   
[32]Ogbe VB, Jayeoba O J, Ode S O.Comparison of four soil infiltration models on a sandy soil in Lafia,Southern Guinea Savanna

Zone of Nigeria[J].Production Agriculture and Technology,2011, 7(2): 116-126.

[33]孙程鹏,赵文智,杨淇越.绿洲边缘夹黏沙丘持水特性[J].生态 学报,2018,38(11):3879-3888.[Sun Chengpeng,Zhao Wenzhi, Yang Qiyue.Water retention of the clay interlayer of dunesat the edge of an oasis[J].Acta Ecologica Sinica,2018,38(11): 3879-

3888.]

[34]崔浩浩,张冰,冯欣,等.不同土体构型土壤的持水性能[J].干旱 地区农业研究,2016,34(4):1-5.[Cui Haohao,Zhang Bing,Feng Xin,et al. Soil water-holding properties of different soil body configuration[J].Agricultural Research in the Arid Areas,2O16,34 (4): 1-5.]

# A comparative study of ponded infiltration in a desert sandy soil based on multi-hydrological models

ZHOU Hong1,2

(1.Hexi Corridor Research Institute,Tourism College,Northwest Normal University,Lanzhou 73Oo70,Gansu, China;2.Linze Inland River BasinResearch Station,China Ecosystem Research Network,Northwest Instituteof Eco Environment and Resources,Chinese Academy of Sciences,Lanzhou 73oooo, Gansu, China)

Abstract: Water infiltration of the vadose zone plays a key role in the water cycle.A better understanding of the relationships among rainfall，ponded water,and soil infiltration processs is critical to estimate groundwater replenishment and redistribution in desert environments.However,research on the moisture distribution in the vadose Zone of sandy soil is stillimited. Inparticular,few studies have examined the water transport processes in the desert vadose zone.Therefore，we aimed to determine the soil moisture distribution and variation in homogenous sandy soil under ponded infiltration and to validate models using data from these observations.This study was conducted in a nature dune slack through dynamic in situ observations using profile infiltration experiment and continuous soil moisture measurements at 1 min intervals.A single-ring infiltrometer (diameter, $2 0 ~ \mathrm { c m }$ ； insertion depth, $5 ~ \mathrm { c m }$ ） was used to keep a constant water head. Kostiakov-Lewis, Green-Ampt, Philip, Hydrus-1D/2D/3D numerical software based on Richard's equation were used to describe the vertical infiltration and soil water movement processes and to identify suitable models for ponded infiltration processes in sandy soil. The validation indices included the sum of squared error and root mean squ are eror. A comparison between the simulatedand measured results indicated that the Philip model could predict the infiltration rate,cumulative infiltration, and weting front advancement correctly, with an RMSE value of O.0oo3,0.04,and $0 . 2 4 ~ \mathrm { c m \cdot m i n ^ { - 1 } }$ （204号 and $R ^ { 2 }$ of 0.95,0.99,and 0.94,respectively. These values were clearly less than those of the Kostiakov-Lewis, Green-Ampt,and Hydrus-1D models,although the other models also showed good overall agreement with the field measured cumulative infiltration.The Hydrus-3D model yielded abetter fit to the simulated soil moisture than the Hydrus-2D in the wetted zone based on the coefficient of determination,average RMSE ( $0 . 0 1 8 \ \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } )$ （2号 and $R ^ { 2 }$ (0.93).Altogether, it appears that the combination of the Philip and Hydrus-3D models isa highly effective approach to estimate ponded infiltration parameters and simulate the water transport process in variably saturated sandy soil.The three-dimensional soil water difusivity must be considered to predict water infiltration in sandy soils.Our results also demonstrate that the integration of numerical simulation and field measurements can improve the research efciency of soil water infiltration in dry environments.In practice,the accurate prediction of soil water infiltration can be done bythe selection of the proper models based on the soil properties of the particular sites.

Keywords: vadose zone； ponded infiltration； numerical simulation; sandy soil