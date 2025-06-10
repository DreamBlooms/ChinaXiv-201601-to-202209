# 基于致动面模型的风力机尾流数值研究

周洋1许昌1韩星星1 Wenzhong Shen 张明明 陈星莺1

(1.河海大学能源与电气学院，南京211100;2.丹麦科技大学风能系，LyngbyDK-2800;3.中国科学院工程热物理研究所，北京100190)

摘要致动面模型利用无厚度的平面代替风力机叶片，在平面上施加不连续压力来模拟叶片对气流的作用，结合 N-S方程,在FLUENT中进行数值模拟计算，是对致动线方法的延伸与改进。运用该方法能够简化风力机的模型，从而减少网格数量和计算时间。采用线性分布下的致动面模型，提出一种致动面网格的辨识方法，对单台 Nibe A型风力机的远近尾流区域进行模拟计算，包括尾流风速变化，湍流强度，涡结构，并将数值模拟的结果与致动线模型计算结果以及实验数据进行对比分析，主要是风轮后特定距离截面的风速变化，验证了致动面方法的优越性以及用于风力机尾流场计算的可行性。

关键词致动面；尾流；源项分布；网格辨识中图分类号：TK89 文献标识码：A 文章编号:0253-231X(2017)03-0535-06

# Numerical Study of Wind Turbine Wake Modeling Based on a Actuator Surface Model

ZHOU Yang1 XU Chang1 HAN Xing-Xing1 SHEN Wen-Zhong $^ 2$ ZHANG Ming-Ming3 CHEN Xing-Ying1

(1.College of Energyand Electrical Engineering,Hohai University,Nanjing 21l1Oo,China; 2.Department of Wind Energy, Technical University of Denmark,Lyngby，DK-280o,Denmark; titute of Engineering Thermophysics,Chinese Academy Sciences,HaidianDistrict，Beijingl00190,Chin.

AbstractIn the Actuator Surface Model (ALM), the turbine blades are represented by porous surfaces of velocity and pressure discontinuities to model the action of lifting surfaces on the flow. The numerical simulation is implemented on FLUENT platform combined with N-S equations.This model is improved on the basis of actuator line model(ALM).By using ASM, the model of turbine can be simplified and the quantity of grids and computing time can be significantly reduced.A linear distribution model and a ASM Grid identification method are presented. This paper compares the ASM with ALM by computing both near and far wake of a Nibe A wind turbine,which combines wake velocity,turbulent intensity and vortex structure.Results show that ASM has better prediction accuracy and verify it's feasibility on numerical simulation of wind turbine wake.

Key wordsactuator surface model; wake; source term distribution; grid identification

# 0引言

近年来，计算流体力学（CFD）方法在风力机流场及其气动性能研究中得到越来越多的运用，该方法能够准确的描述出风力机及其周围的复杂流场。常规的风机CFD计算，为了保证风力机叶片及尾流区域的计算准确性，需要建立相对复杂的实物模型，先将固体的实体模型用专业的三维建模软件进行建模，建模完成后再对整个流场区域进行网格划分。三维模型的复杂性使得在整个过程中网格的划分成为了一个难点，而且由于在风轮下游远尾流区域内网格还要保持一定的精度，网格的数量大量增加，从而必然会导致计算量的增加。

研究人员通过将BEM理论与常规的CFD方法相结合，开发出了致动模型方法，即先用BEM理论求解风轮叶片的气动力，再将气动力作为体积力源项添加到N-S方程中求解，模拟叶片与流场的作用力。因为模型中没有真实的叶片的固壁边界，所以能够大大减少模型复杂程度以及网格数量，进而节约大量的计算资源。目前致动模型主要有致动盘模型、致动线模型和致动面模型。

Rajagopalanl1将致动盘概念与CFD计算相结合。他采用时间平均的体积力分布形式以及有限差分法对风力机流场的层流N-S方程进行了定常计算。沈翔和王同光[2引入致动盘模型，基于GarradHas-san风机尾流实验，对风力机尾流速度型的分布形态进行了研究。许昌和韩星星[3]将致动盘模型与拓展$k { - } \varepsilon$ 湍流方程结合，引入湍流耗散源项，改善尾流恢复过快问题，计算多种风速下的风力机尾流。

SorensenJN[4] 和 Shen WZ[5]将致动盘模型进行了改进，舍弃了致动盘模型的轴对称假设，提出了用于非定常计算的致动线方法，该方法更真实地模拟了风轮的转动情况。卞凤娇和王强等[6利用致动线模型，基于openFOAM平台对风力机的涡结构，尾流速度亏损做了数值模拟研究。

Shen 和Dobrev 等人[7-9]在致动线模型的基础上发展出了致动面模型。由于考虑了在弦长方向上受力的变化，使用致动面模型计算出的结果更加准确，致动面模型对翼尖涡以及近尾流流场的模拟精度得到了提高。

目前致动模型的主要计算研究方向是风力机叶片的载荷特性，转轮区域流场以及近尾流区域的流场特性。而风力机远尾流区域的计算对于风场开发、微观选址有着重要的参考意义，本文主要运用致动面模型对单台 NibeA 型风力机的尾流场进行数值模拟计算，包括速度、湍流变化以及涡量特性等，并与致动线模型的数值模拟结果进行对比，验证致动面模型方法运用在风场选址上的可行性。

# 1致动面模型

# 1.1体积力的求解

致动面模型实质上是将风力机叶片简化成无厚度的平面，在平面上施加不连续的压力来模拟叶片对气流的作用。叶片上各点压力用二维翼型气动数据，根据BEM理论计算确定。继而将分布的体积力在流场区域内用三维N-S方程求解，不可压缩N-S方程：

$$
\frac { \partial \vec { V } } { \partial t } + \boldsymbol { V } \cdot \nabla \vec { V } = - \frac { 1 } { \rho } \nabla p + V \nabla ^ { 2 } \vec { V } + \vec { f }
$$

式中： $f$ 为作用在旋转叶片上的体积力。

如图1所示，相对于叶片的空气流相对速度可以从上述速度三角形中得出：

$$
V _ { \mathrm { r e l } } = \sqrt { V _ { z } ^ { 2 } + ( \varOmega r - V _ { \theta } ) ^ { 2 } }
$$

式中： $\varOmega$ 为风轮转速； $V _ { \mathrm { z } }$ 为相对径向速度； $V _ { \theta }$ 为切向速度； $V _ { \mathrm { r e l } }$ 为合速度； $V _ { \mathrm { r e l } }$ 和旋转平面的夹角（入

流角）可用下式求得：

$$
\phi = \tan ^ { - 1 } \left( \frac { V _ { z } } { \varOmega r - V _ { \theta } } \right)
$$

![](images/7c314ccecd81c054a732010d4c62312341793092d078a41697475a971ab77853.jpg)  
图1叶素受力分析  
Fig.1 Thevelocity and force inblade element

当地攻角 $\alpha = \phi - \gamma$ ，其中 $\gamma$ 为安装角。叶片叶展方向单位长度上的体积力由下式确定：

$$
f _ { 2 D } = ( L , D ) = \frac { 1 } { 2 } \rho V _ { \mathrm { r e l } } ^ { 2 } c ( C _ { \mathrm { L } } e _ { \mathrm { L } } , C _ { \mathrm { D } } e _ { \mathrm { D } } )
$$

式中： $C _ { \mathrm { L } } = C _ { \mathrm { L } } ( \alpha , R e )$ 为升力系数； $C _ { \mathrm { D } } = C _ { \mathrm { D } } ( \alpha , R e )$ 为阻力系数，是以攻角和雷诺数为变量的函数； $e _ { \mathrm { L } }$ 为升力方向向量； $\boldsymbol { e } _ { \mathrm { D } }$ 为阻力方向向量；雷诺数 $R e$ 由弦长 $\mid c \mid$ 和来流速度确定。

# 1.2湍流模型

由于风轮在旋转过程中，对其前后流场产生扰动，加快了湍流动能的产生与耗散，为了尾流模拟的准确度，需要添加湍流耗散率源项[10]，平衡湍流产生率与耗散率。文献[10]中研究了拓展 $k { - } \varepsilon$ 湍流方程在水平轴风力机尾流计算中的运用。湍流耗散率源项为：

$$
{ S _ { \varepsilon } ^ { \mathrm { e x t } } = C _ { 4 \varepsilon } \frac { P _ { k } ^ { 2 } } { \rho k } }
$$

式中： $S _ { \varepsilon } ^ { \mathrm { e x t } }$ 为湍流耗散率，用来表征湍流从大尺度向小尺度过渡时候的能量传递速率； $P _ { \mathrm { k } }$ 为湍流动能生成率。其中参数 $C _ { 4 \varepsilon }$ 取0.37。源项 $S _ { \varepsilon } ^ { \mathrm { e x t } }$ 添加在风轮前后0.5倍直径区域。为更真实地模拟风机工作时的状态，本文添加了机舱源项 $S _ { \mathrm { d } }$ 和塔架源项 $S _ { \mathrm { t } }$ 具体如文献[4]所示。本文数值模拟使用拓展 $k { - } \varepsilon$ 湍流方程[11]。

# 2 计算方法

# 2.1风力机参数

本文采用丹麦NibeA 型水平轴风力机进行模拟计算[12]。风机的轮毂高度为 $4 5 \mathrm { ~ m ~ }$ ，风轮直径为

$4 0 \mathrm { m }$ ，叶片设计采用气动翼型NACA44系列，额定风速为 $\mathrm { 1 3 ~ m { \cdot } s ^ { - 1 } }$ 。根据G.J.Taylor等人在该风机流场内做了实验数据采集工作，以NibeA型风力机为模型在来流风速为 $8 . 5 ~ \mathrm { m \cdot s ^ { - 1 } }$ ，转速为 $3 . 5 ~ \mathrm { r a d / s }$ 的工况下，用致动面方法对风机尾流场进行了数值模拟，并将结果与实验测量值进行比较。

# 2.2 计算域

首先运用Gambit构建计算域并按照不同区域添加相应大小的非结构性网格。为了结合实际风场中的条件，整个计算域设计为一个规则圆柱体，半径 $1 4 0 \mathrm { m }$ ，总长 $\mathrm { 1 2 0 3 ~ m }$ 。具体划分如图2。

![](images/cff9e7b1f6633c059f042b3fdc929ac216f341fba34aaccb8acc391bfafe70c2.jpg)  
图2计算域划分示意图Fig.2 Diagram of computational domain

# 2.3体积力的分布

因为致动面模型中不存在真实的叶片固壁边界,所以风机叶片和流场之间的相互作用完全通过体积力源项的分布来表征。通过上文体积力的计算，得到的是沿叶片展向单位长度的体积力源项，未考虑到真实情况下风轮旋转时弦长方向上力的分布特征。致动面模型相比较于致动线模型，最明显的改进与优化就是在体积力的分布方式上考虑了叶片弦长上的变化。

![](images/b3d9d1c59bc7de604d8bc687f4fe3872ba8299a44b143181f8dec7ca915992ed.jpg)  
图3体积力分布方式Fig.3 Distribution of volume force

考虑到叶片弦长对叶片上体积力分布的影响，本文模型中体积力的分布采取分段线性分布方式[13]，如图3所示，以翼型的1/4 弦长位置为分界点，且保持1/4弦长位置处翼型的俯仰力矩为零。这样的分布方式更符合真实情况下的叶片固壁边界效应，能有效的改进近尾流区域的计算准确度。

# 2.3致动面的辨识

将体积力源项准确的添加到致动面模型所定义的无厚度平面上是计算中的重要环节。如图4，叶片所在平面即为致动面所在平面， $O$ 点为叶片旋转中心， $P$ 点是风轮旋转平面内任意一点，任意选择一个叶片， $Q$ 为该叶片弦线上一点。

若 $\overrightarrow { O P } \times \overrightarrow { O Q } \cdot \overrightarrow { k } > 0$ ，则 $P$ 点在叶片弦线右边;反之则 $P$ 点在叶片弦线左边。

式中， $\overrightarrow { k }$ 为Z轴正方向单位向量(与来流风速方向相反)。

若 $P$ 点在弦线右边，且 $\left| \overrightarrow { O P } \right| c / 4$ （， $\dot { } c$ 为叶片弦长则 $P$ 点在该叶片上；若 $P$ 点不在该叶片上，则再依次与另外两个叶片进行匹配，最终可确定点 $P$ 在平面上的位置。

叶片旋转后， $\overrightarrow { O Q }$ 随着时间 $\mathbf { \Psi } _ { t }$ 和角速度 $\omega$ 变化,在每个时间步长上对致动面网格重复以上步骤进行识别。

![](images/5da27ff1f2dcfcc3585a80b145b3f73c4ced97387dd23542bc3715ef107d3a98.jpg)  
图4致动面识别示意图Fig.4 Grid identification of ASM

通过上述致动面辨识技术，用户可以自定义函数UDF准确定位旋转中的致动面位置，这种方法很大程度上减少了模拟实际风电场建立致动面模型的工作量，对实际工程有很大的实用价值。

# 表1计算域尺寸及网格数

.able 1 Size of calculation domain and number of grids   

<html><body><table><tr><td>区域编号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>长/半径 (m)</td><td>3/140</td><td>80/140</td><td>3/140</td><td>200/140</td><td>200/140</td><td>600/140</td><td>3/140</td></tr><tr><td>网格数/104</td><td>38</td><td>10</td><td>53</td><td>133</td><td>17</td><td>26</td><td>2.5</td></tr><tr><td>总计/104</td><td colspan="7">281</td></tr></table></body></html>

# 2.4边界与求解

边界条件方面，计算域入口边界采用Inlet固定速度入口条件，出口边界采用Outlet零压力梯度出口条件，圆柱壁面采用Symmetry条件。数值模拟采用求解器的默认设置，压力－耦合采用SIMPLEC算法，控制方程的离散选用Standard方式，动量、湍动能和耗散率均采用二阶迎风格式，各松弛因子均采用默认值。

# 3计算结果分析

# 3.1体积力的修正

致动模型计算叶片体积力通过BEM理论，计算各截面位置的入流角和攻角大小，然后利用迭代法计算诱导因子，再根据二维翼型气动数据查表获得每个翼型升力系数和阻力系数最后由式(4)得出。因此在数值模拟过程中，叶片的三维特性不能够得到充分表现，且迭代后拟合过程也存在一定误差，从而影响计算结果准确度。综上考虑，添加一个体积力修正系数 $C _ { \mathrm { f } }$ 。那么体积力可表示为：

$$
 { f _ { \mathrm { 2 D } } ^ { \prime } } =  { C _ { \mathrm { f } } }  { f _ { \mathrm { 2 D } } }
$$

$C _ { \mathrm { f } }$ 拟定1.0，1.1 和1.2，分别进行模拟计算,选取风轮后 $2 . 5 D$ 及 $6 D$ 处截面风速，进行对比如图5。

比较后可见 $C _ { \mathrm { f } } { = } 1 . 2$ 时风速曲线与实验数据更吻合，因此选定体积力修正系数大小为1.2。

# 3.2计算结果分析

按照上文所述条件及设定，在FLUENT中耦合相关模型，对NibeA型风力机的流场进行数值模拟计算，计算时间全长为风机运转 $\mathrm { 1 4 2 ~ s }$ ，来流通过整个计算域。提取计算结果进行分析。

![](images/700c1e8bba584eae6e856c84a1d0d5f2b0164818ca9d83e44854dbdb0ffb15bc.jpg)  
图6是风轮叶片平面处速度云图及涡量图。

![](images/aa3ec77848dcbd9bb418e691250a7741a56c3d79b6567f4d6ff1b16d150ba81b.jpg)  
图5两种体积力修正系数对比 Fig.5 Comparison of two correction coefficient

从图6中可以看出，风轮平面速度分为3个扇形，不同位置处速度大小分布清晰，叶片外缘位置速度较大，而叶尖处速度最大。从涡量图可看到叶尖涡迅速发展成涡面，且可见到明显弦向脱落涡结构。

![](images/7b30340c6c16ec0207cc7ce8bde9b13a0332117343afd0b18439ece0d59e9242.jpg)  
图6转轮平面速度云图和涡量图Fig.6 Contour of velocity at wind turbine rotor andIso-surface vorticity of ASM

在轮毂高度取水平截面分析风力机尾流场，主要分析速度与湍流的变化，如图7、图8所示。图7中可以看出，风机尾流扩张角明显，速度变化规律明显， $3 D$ 距离后趋于稳定， $1 6 { \sim } 1 7 D$ 后风速基本恢复至来流风速。由图8可见，湍流在风轮前 $1 D$ 到风轮后 $3 D$ 范围内变化较为强烈，风轮后方 $5 D$ 距离后趋于稳定，在 $1 6 { \sim } 1 7 D$ 后基本可以忽略不计，这与速度云图趋势基本一致。

![](images/6c1cb5ad45c89bcfeb17164a45c17209d62beea94412062f7cc688b02aa55e07.jpg)  
Fig.7 Contour of velocity at horizontal plane

![](images/7978ab2d04abfa94c80d75d3931090ab50736f369fbd640b3c729976f68dfa44.jpg)  
图8水平面湍流云图  
Fig.8 Contour of turbulent intensity at horizontal plane

# 3.3致动面模型与致动线模型的对比分析

考虑到实际风场中风机间距一般在 $5 D$ 以上，如果想要将致动面模型运用于实际风场的流场计算之中去，那么只对近尾流区域进行计算是不够的。因此本文着重对风机后 $2 . 5 { \sim } 7 . 5 D$ 距离的风速情况作研究分析。在流场中轮毂高度截取水平面，分别导出在转轮后侧 $2 . 5 D$ 、 $6 D$ 和 $7 . 5 D$ 三处水平线上速度进行分析，同时将用致动线方法[14]模拟所得结果一并列出，与实验数据进行比较，得到图9。

从图9中可以看出，三个位置处致动线方法和致动面方法数值模拟的结果整体接近，与实验数据相比，两侧风速基本一致，最小风速都出现在中心位置。 $\pm 1 D$ 范围内尾流速度曲线坡度明显减小，与图7水平速度云图相互验证。

由图9(a)可见，在 $2 . 5 D$ 处，致动面方法与致动线方法的模拟结果和实验数据都很吻合，整体上都呈V型，致动线方法中心位置速度略有波动。但从图9(b)、(c)可以看出，在 $6 D$ 和 $7 . 5 D$ 处，致动线方法计算结果和实验数据偏差较大，轴线位置的实验最小风速为 $0 . 7 U$ 左右，而致动线模型最小风速只有$0 . 5 U$ 。致动线模型截面上风速曲线的趋势和实验数据有较大出入，依然保持 $\mathrm { \Delta V }$ 型速度曲线，尤其风轮位置 $( r / D = \pm 0 . 5 D )$ 风速明显偏小，误差超过 $2 0 \%$ 而实验数据中速度变化曲线呈浅U型。这说明在致动线模型的数值模拟中，远尾流区域动能耗散与恢复和真实情况误差较大，而致动面方法的模拟结果就相对准确很多，曲线走势基本一致，尤其是在远尾流区域依然保持了较高的吻合度。

# 4结论

本文通过使用致动面模型对NibeA型风力机尾流场进行计算和分析，并与致动线模型以及实验数据进行对比，得到以下结论：

1）使用致动面模型结合CFD软件对风力机尾流场进行计算，简便易行，计算量小，模型通用性较强；2）与致动线模型数值模拟结果对比，可看出致动面模型在数值模拟的精度上有一定优势，尤其是对远尾流区域的计算精度有很大的提升;3)致动面模型计算风力机流场所需计算资源不多，且对远近尾流区域的模拟有较高精确度，因此可以考虑变工况下风力机的流场数值模拟或者多台风机的计算。

![](images/b5a4a6b7c67891547a15dbecfa247231eba1973134a6a6d28ee997cb1f5fcfee.jpg)  
图7水平面速度云图  
图9风轮后 $2 . 5 D$ 、 $6 D$ 和 $7 . 5 D$ 处水平线上致动模型计算风速与实验数据对比 Fig.9 Comparison of velocity between ALM and ASM at 2.5,6 and $7 . 5 D$ behind wind turbine rotor

# 参考文献

[1]Rajagopalan R G,Klimas P C,Rickerl TL.Aerodynamic Interference of Vertical Axis Wind Turbines [J].Journal of Propulsion and Power,1990,6(5):645-653   
[2]沈翔，王同光,钟伟．风力机尾流速度型建模[J].太阳能学 报，2014,35(3):469-473 SHEN Xiang,WANGTongguang, ZHONG Wei.Modeling of theVelocityProfile ofWind Turbine FarWake[J].Acta Energiae Solaris Sinica,2014,35(3):469-473   
[3]许昌，韩星星，王欣，等.基于改进致动盘和拓展k-ε湍流 模型的风力机尾流数值研究[J].中国电机工程学报，2015, 35(8): 1954-1961 XU Chang,HAN Xingxing,WANG Xin et al. Study of Wind Turbine Wake Modeling Based on a Modified Actuator Disk Model and Extended k-ε Turbulence Model [J].Proceedings of the CSEE.2015,35(8):1954-1961   
[4]SorensenJN,Shen WZ,Munduate X.AnalysisofWake States bya Full-field Actuator Disc Model [J].Wind Energy,1998,1(2): 73-88   
[5] Troldborg N,Sorensen JN,Mikkelsen R.Actuator Line Simulation of Wake of Wind Turbine Operating in Turbulent Inflow [J].Journal of Physics:Conference Series, 2007,75(1):1-15   
[6]卞凤娇,徐宇，王强，等.基于openFOAM的风力机致动线 模型研究[J].工程热物理学报，2016,37(1)：72-75 BIAN Fengjiao,XU Yu,WANGQiang，et al.Numerical Study ofActuator Line Model ofWind Turbine Based on OpenFOAMPlatform [J].JEng Therm,2016,37(1): 72-75 [7] Shen W Z, Sorensen JN, Zhang J.Actuator Surface Model for Wind Turbine Flow Computations [C]//2007 European Wind Energy Conference and Exibition,2007 [8]Ivanell S,Sorensen J N,Mikkelsen R,et al.Numerical Analysis of the Tip and Root Vortex Position in the Wake of a Wind Turbine [J]. Journal of Physics: Conference Series,2007,75(01):20-35 [9] Shen W Z,Zhang JH,Sorensen J N.The Actuator SurfaceModel:ANewNavier-StokesBasedModel forRotor Computations [J]. Journal of Solar Energy Engineering, 2009,131(1): 284-289   
[10]El Kasmi A,Masson C.An Extended k- $\varepsilon$ Model for Turbulent Flow Through Horizontal Axis Wind Turbines [J]. Journal of Wind Engineering and Industrial Aerodynamics,2008,96(1):103-22   
[11] FLUENT INC.Fluent 6.3 User's Guide [M].Lebanon, NewHampshire,USA:Fluent Inc,2006   
[12]Pederson B M,Nielson P.Description of the Two Danish 630kWWind Turbines，Nibe-A and Nibe-B，and Some Preliminary Test Results [C]//Third International Symposium on Wind Energy Systems,DEFU,Denmark,1980   
[13]Dobrev I,MassouhF,Rapin M.Actuator Surface Hybrid Model [C]//Proceedings of the Journal of Physics:Conference Series,F.IOPPublishing,2007   
[14]邓力．风力机组尾流数值计算方法研究[D].南京：河海大 学,2015 DENG Li. Research on Numerical Calculation Method for Wake of Wind Turbine [D].Nanjing:Hohai University,2015