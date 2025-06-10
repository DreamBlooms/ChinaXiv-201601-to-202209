# CN 53-1189/P ISSN 1672-7673

# 基于CFD软件的桁架式望远镜遮光筒扰流分析

李陶然1,2

(1.中国科学院光学天文重点实验室（国家天文台），北京1012；2.中国科学院大学，北京100049)

摘要：遮光筒会影响主镜上方的空气流动，不利于主镜表面与周围空气的热交换。以兴隆基地 $5 0 \ \mathrm { c m }$ 望远镜为例，应用CFD软件分析了两种消杂散光装置（遮光筒和独立挡光环结构)对主镜区域气流运动和温度的影响。同时根据温度数据计算主镜视宁度。分析结果表明，遮光筒会造成温度分布不均匀、湍流影响范围大、非对称的漩涡绕流等影响。独立挡光环结构的情况下，主镜视宁度减小 $74 \%$ 。由此说明，在主镜散热和空气流通方面，主镜遮光筒有较大弊端。将该分析方法与杂散光分析结合，可合理选择杂散光抑制方案，对望远镜设计及改造具有一定参考和应用价值。

关键词：桁架式望远镜；CFD；遮光筒；湍流模型；主镜视宁度中图分类号：P111.21 文献标识码：A 文章编号：1672-7673(2017)01-0070-08

杂散光是到达光学系统像面的非成像光线。对于望远镜系统，杂散光增加像面的背景噪声，降低星像的信噪比[1]。在国内外关于开放桁架式望远镜杂散光抑制的研究中，最常用的方法是使用遮光筒和挡光环[2-3]，如图1。在望远镜主镜中心孔处安装遮光筒可有效抑制大角度入射的杂散光。挡光环通常安装在主镜遮光筒内部，用于阻挡内部散射光线，与遮光筒相比，杂散光抑制能力稍弱。然而，空气经过遮光筒后会产生扰流（圆筒绕流），影响主镜上方区域的气流运动，造成星像抖动，降低望远镜的成像质量。 $2 . 5 \mathrm { ~ m ~ }$ 斯隆数字巡天（Sloan Digital Sky Survey，SDSS）望远镜[4]和LCOGT（LasCumbres Observatory Global Telescope Network，LCOGT）的 $1 \mathrm { m }$ 望远镜5即采用独立挡光环的形式避免海业管选成的气流协动

计算流体动力学（Computational Fluid Dynamics,CFD)软件是通过计算机数值计算和图像显示，分析包含流体流动和热传导等相关物理现象的系统[。为辅助选取合适的消杂散光装置，本文以兴隆基地 $5 0 \ \mathrm { c m }$ 望远镜为例，应用计算流体动力学软件分析遮光筒和独立挡光环两种情况下主镜区域温度、湍流强度及风速的分布，并通过温度数据给出主镜视宁度。结合主镜视宁度的半经验公式验证计算流体动力学模型的准确性。

# 1计算流体动力学软件介绍

计算流体动力学软件广泛应用于航空航天、  
工业设计、环境模拟、建筑设计、生物医学等诸  
多领域。近年来，也有少量研究人员将其应用到望远镜设计上[7-8]

![](images/5af1e834096d530c7d6cc04ddd5c5fef0cb418226ddad99f8c2c08ffdbf8cfa0.jpg)  
图1（a）兴隆 $2 . 1 6 \mathrm { m }$ 望远镜主镜遮光筒；（b）SDSS望远镜独立挡光环Fig.1（a）Primarybaffle of the2.16m Telescopeat Xinglong station；（b）Vane structureof the SDSS telescope

。

本文采用的ANSYS@FLUENT是享誉业界的流体分析工具，已经被充分验证并广泛应用，可用于模拟不可压缩到高度可压缩范围内的复杂流动，包含丰富先进的物理模型，可以精确模拟无粘流动、层流和湍流模型①。尽管计算流体力学方法存在边界条件与实际不符、物理模型不完备等缺点，但由于成本较低，可以给出很多无法测量的结果，对流体力学分析有着难以替代的作用。将FLUENT 应用到望远镜设计上具有以下优点：

(1)可模拟复杂的实验环境，在任意位置设置测点，给出实测中难以得到的数据;(2)通过图形用户界面，可以直观地表现气流运动；(3)无需实测即可为望远镜设计和后期改造提供依据，减少成本昂贵的实验工作。

# 2计算流体动力学仿真模型描述

# 2.1 模型介绍

兴隆基地 $5 0 \mathrm { c m }$ 望远镜(图2)主镜直径 $5 0 0 ~ \mathrm { m m }$ ，中心孔直径 $1 3 0 ~ \mathrm { m m }$ ，厚约 $6 0 ~ \mathrm { m m }$ ，材料为微晶玻璃。主镜遮光筒外径 $1 4 0 ~ \mathrm { m m }$ ，内径 $1 3 8 ~ \mathrm { m m }$ ，高 $5 1 5 \ \mathrm { m m }$ 。挡光环共有7级，每级厚度 $1 ~ \mathrm { m m }$ ，外径 $1 3 8 ~ \mathrm { m m }$ ，内径均不相同，挡光环最高处与主镜表面距离为 $3 8 0 ~ \mathrm { m m }$ 。遮光筒和挡光环均使用发黑处理的铝材料。主镜区域另包含镜盖、主镜室及底支撑和侧支撑。

# 2.2计算方法及参数设置

FLUENT软件求解过程如图3。

![](images/30d45f10644eddc901b2ad569762afe371e4a8b04bc6f484c5920ded3940fcd4.jpg)  
图2 $5 0 \mathrm { c m }$ 望远镜示意图 Fig.2Layout of the $5 0 \mathrm { c m }$ Telescope

![](images/46db5fa09f5c0c4a4031897a254b3c68a3fb36b776617fa1dae9ac06365b5faa.jpg)  
图3 FLUENT求解过程  
Fig.3Solution procedure of FLUENT

对遮光筒扰流的分析只需模拟主镜区域，包含主镜及遮光筒/挡光环。同时为减小计算机负荷及处理时间，将 $5 0 \ \mathrm { c m }$ 望远镜模型简化（对有遮光筒的情况，由于挡光环在遮光筒内部，无需考虑挡光环的作用)。在简化模型外设置方形的流体域，用于模拟空气流动区域。流体域尺寸为 $1 . 5 \ \mathrm { m } \times 1 . 5 \ \mathrm { m }$ $\times 1 . 0 8 5 \mathrm { ~ m ~ }$ （若流体域过小，不能分辨流动空气经过遮光筒产生的绕流，且壁面会对结果产生影响；而流体域过大又会使网格增加，延长计算时间。经过多次模拟，除底面外的其余边界与望远镜距离均为$0 . 5 \mathrm { m }$ 较为合适。主镜底面流体无需考虑，因此设置底边界距主镜底面 $0 . 0 1 \mathrm { ~ m ~ }$ )。图4为望远镜原始模型与计算流体动力学软件简化模型，图中的立方体即为流体域。

![](images/026563b314747ea61d90259d099a15658f57d52211ce76edf7ee6150a2b4641e.jpg)  
图4（a）原始模型；（b）CFD简化模型(有遮光筒)；（c）独立挡光环Fig.4（a） Original model；（b）CFD simplified model with bafle；（c）CFD simplified model with vanes

网格划分应用ANSYS?Workbench的Mesh组件，具有强大的前处理功能。考虑设置时间、计算成本和数值耗散，对模型采用适应性较好的四面体网格。由于本文是对扰流及主镜散热的分析，所以只对流体域及主镜划分网格。

在流体力学中，常用雷诺数 $R e$ 表征流体的流动情况。利用雷诺数可区分流体的流动是层流或湍流。

$$
R e = \frac { D V } { \nu } = \left\{ \begin{array} { l l } { { \displaystyle < ~ 2 0 0 0 ~ \sum _ { \perp } ^ { \perp } \Re ^ { 2 } } } \\ { { \displaystyle 2 ~ 0 0 0 ~ \sim ~ 4 ~ 0 0 0 ~ \mathrm { i } \sum _ { \perp } ^ { \perp } \Re ^ { 2 } \mathrm { i } \Re ^ { 2 } \mathrm { e } ^ { \perp } } } \\ { { \displaystyle > ~ 4 ~ 0 0 0 ~ \uparrow _ { \mathrm { f f f } } ^ { \perp \perp } \Im ^ { 2 } \mathrm { e } ^ { \perp } } } \end{array} \right. .
$$

该模型特征长度(遮光筒直径) $D = 0 . 1 4 \mathrm { ~ m ~ }$ ， $0 \mathrm { { ^ \circ C } }$ 时空气运动粘度为 $\upsilon = 1 3 . 2 7 ~ \mathrm { m m } ^ { 2 } / \mathrm { s }$ 。因此当 $\boldsymbol { V } >$ $0 . 3 8 \mathrm { m / s }$ ，雷诺数 $R e > 4 0 0 0$ ，模型处于湍流状态；当风速 $V { < } 0 . 1 9 \mathrm { m / s }$ 时， $R e < 2 0 0 0$ ，模型处于层流状态。根据兴隆基地气象站实测数据，良好的观测夜平均风速大约为 $V { = } 1 \ \mathrm { m / s }$ ，此时 $R e = 1 0 ~ 5 5 0$ ，望远镜基本处于湍流状态，因此只考虑湍流模型。

经过多次模拟，常用几种湍流物理模型在望远镜流场分析中差别不大，且工程应用精度要求不高，因此湍流模型选择工程上应用广泛的改进型 RNG $\mathbf { k } { - } \varepsilon$ 模型[9]，同时强调壁温及浮升力作用。传热模型包含热传导和自然对流换热，忽略主镜辐射散热。假设初始环境温度为 $0 \%$ ，主镜温度为 $5 \mathrm { ^ \circ C }$ 。在流体域左侧设置速度进口模拟圆顶天窗，风速设置为 $1 ~ \mathrm { m / s }$ ，右侧为出口，符合完全发展条件，设置为自由流出边界。流体域四周无影响，采用无滑移的壁面条件。

# 3计算结果分析

# 3.1 流体力学分析

遮光筒和独立挡光环模型(以下简称工况1、2)均在 $1 5 ~ 0 0 0 ~ \mathrm { s }$ 左右收敛，此时温度基本稳定无差异。在整个瞬态模拟的中间部分，两种工况下各参量对比较为显著，因此取程序开始后两小时（取整小时)的数据作分析。在分析中创建3个横截面以方便观察，各截面方向如下：风速方向为 $+ X$ 轴；侧视图法线方向为 $+ Z$ 轴；温度散点图法线方向为- $- X$ 轴；俯视图距主镜表面 $1 0 \ \mathrm { c m }$ ，法线方向为 $+ Y$ 轴。

图5为湍流状态下工况1、2的温度云图与温度散点图，散点图中白色点表示主镜表面温度，红色点表示主镜上方 $1 0 \ \mathrm { c m }$ 处的温度。从温度云图可以看出，工况1遮光筒内部与周围环境有温差。主镜散热不均匀，背风面散热慢，造成主镜表面空气存在温度差。由于处在望远镜光路中，温度差异引起的湍流会降低望远镜的分辨率。工况2主镜散热均匀，主镜表面温度梯度较小。从散点图看，工况2 在主镜上方 $1 0 \ \mathrm { c m }$ 处没有温度差异，且主镜表面温度比工况1小。而工况1主镜上方 $1 0 \ \mathrm { c m }$ 处仍有温差存在于遮光筒内。

![](images/fd6871c93bca48d90ebc40b2cea505e253801deecaf0af1cc02301484d36dbbe.jpg)  
图5工况1、2温度云图与散点图。（a）工况1温度侧视图；（b）工况2温度侧视图;（c）工况1温度散点；（d）工况2温度散点  
Fig.5Temperature contours and scatter diagrams of working status 1 and 2.（a）Temperature contour of status 1: (b）Temperature contour of status 2；（c） Scatter diagram of status 1；(d） Scatter diagram of status 2

FLUENT软件还可以给出湍流强度的分布，如图6。由三维湍流云图可以看到，工况1整个模型湍流强度最大为 $2 1 . 6 3 \%$ ，在遮光筒外中上部分占据的区域很小，可以忽略。由于湍流强度 $I$ 与特征长度 $D$ 成反比 $( I \propto D \mathrm { - } 1 / 8 )$ ，工况2湍流强度最大为 $3 1 . 6 3 \%$ ，沿挡光环连接杆分布，距连接杆仅有$4 \mathrm { m m }$ ，所占面积较小。从俯视图可以看出，工况1影响较大的部分是黄色和绿色区域，湍流强度最大为 $1 6 . 3 3 \%$ 。而工况2影响最大的在挡光环右侧的蓝色区域，湍流强度仅为 $9 . 8 2 \%$ 。

流体经过绕流圆柱体时会产生卡门涡街②，形成交替的涡流。这种交替的涡流使阻流体两侧流体的瞬间速度不同。如图7，对于工况1，遮光筒之前风速呈对称分布，在遮光筒后形成了非对称的绕流漩涡对。从侧视图看，速度分布不均匀，遮光筒前后风速差别较大，最大速度为$1 . 4 2 ~ \mathrm { m / s }$ 。相比之下，工况2最大速度为1.37$\mathrm { m / s }$ ，无绕流现象。挡光环之前仍呈对称分布，$1 \mathrm { m m }$ 厚度对气流影响很小，整体上速度分布较工况1均匀。综合以上分析，工况1、2下温度、湍流强度和速度的范围如表1。

表1工况1、2下温度、湍流强度和速度的范围

Table1Temperature，Turbulent Intensity and Velocity   

<html><body><table><tr><td colspan="2">range of workingstatus1 and 2</td></tr><tr><td>参数 工况1</td><td>工况2</td></tr><tr><td>温度范围/℃</td><td>0~2.54 0~1. 79</td></tr><tr><td>湍流强度范围/%</td><td>0.44~21.63 0.47~31.63</td></tr><tr><td>速度范围/(m/s)</td><td>0~1.42 0~1.37</td></tr></table></body></html>

![](images/baa6920b57f68236c15035d04f9c7ef914b0dcb26b193719fbfb9fd4a1059e3f.jpg)  
14卷  
图6工况1、2湍流强度分布云图(黑色圆为主镜轮廓)。（a）工况1三维湍流分布；(b）工况2三维湍流分布；（c）工况1湍流分布俯视图；（d）工况2湍流分布俯视图Fig.6Turbulent intensitycontours（blackcircleindicates the miror'sprofile).（a）3Dturbulent intensitycontourofstatus1;(b）3D turbulent intensity contour of status 2；（c）Vertical view of the turbulent intensity contourof status 1;(d）Vertical view of the turbulent intensity contour of status 2

![](images/4b9dbe68efbf9467f025ff338bd5620c8aaacb06387772d0d9ab12fc93b38467.jpg)  
图7速度分布云图。(a）工况1速度分布；(b)工况2速度分布；(c）工况1速度分布俯视图；(d）工况2速度分布俯视图Fig.7Velocity contours.（a）Velocity contour of status 1；（b）Velocity contour of status 2;(c）Vertical view of thevelocity contour of status1；（d）Vertical view of the velocity contour of status 2

# 3.2两种工况下主镜视宁度对比

当主镜与周围环境有温差时，主镜表面的湍流层会降低图像质量，表现为星像半高全宽(FWHM)的增大。文[10]和文[11]对视宁度做了深入研究，将湍流惯性域中温度结构函数与大气折射率的柯西表达式结合，并忽略湿度影响，得到：

$$
C _ { \mathrm { T } } ^ { 2 } = \frac { < \textnormal [ T ( r ) - T ( r + \Delta r ) \textnormal ] ^ { 2 } > } { \Delta r ^ { 2 / 3 } } ,
$$

$$
C _ { \mathrm { N } } ^ { 2 } = \mathrm { C _ { T } ^ { 2 } } \left( 8 0 \times 1 0 ^ { - 6 } \frac { P } { T ^ { 2 } } \right) ^ { 2 } .
$$

其中， $C _ { \mathrm { N } } ^ { 2 }$ 、 $C _ { \mathrm { T } } ^ { 2 }$ 分别为折射率和温度结构系数； $\Delta r$ 为间距； $\lambda$ 为波长( $( \mu \mathrm { m } )$ ； $P$ 为压强( ${ \mathrm { ( } } { \mathrm { m b a r } } { \mathrm { ) } }$ ； $T$ 为温度（K)。星像半高全宽为点扩散函数峰值半高处的角直径 $\theta$ ：

$$
\theta = 1 . \ 0 8 5 4 \times 1 0 ^ { 6 } \lambda ^ { - \frac { 1 } { 5 } } \Big [ \left( c o s \gamma \right) ^ { - 1 } \int _ { H } C _ { _ { N } } ^ { 2 } ( z ) \mathrm { d } z \Big ] ^ { \frac { 3 } { 5 } } .
$$

假设天顶距 $\gamma = 0 ^ { \circ }$ ， $\lambda = 5 0 0 ~ \mathrm { { n m } }$ ，兴隆基地海拔 $9 6 0 \mathrm { ~ m ~ }$ （大气压约 $9 0 1 2 5 \mathrm { P a }$ ）， $P { = } 9 0 1 ~ \mathrm { m b }$ ， $z$ 为距主镜表面的高度，则：

$$
\theta = \frac { 8 . 4 1 8 \times 1 0 ^ { 5 } } { T ^ { 2 . 4 } } \biggl [ \int _ { H } C _ { T } ^ { 2 } ( z ) \mathrm { d } z \biggr ] ^ { \frac { 3 } { 5 } } .
$$

根据以上公式，只需探测镜面上方不同位置处的温度值，即可计算得到主镜视宁度。在计算流体动力学软件中设置主镜上方 $1 0 \ \mathrm { c m }$ 处对不同高度距离相同的温度监视点( $\Delta r = 0 . 3 )$ ，根据(2）、（5)式计算主镜视宁度。计算得到不同高度下 $C _ { \mathrm { T } } ^ { 2 }$ 的散点及拟合曲线如图8。由于工况1、2温度差随高度增加而降低，整体上 $C _ { \mathrm { T } } ^ { 2 }$ 呈下降趋势。工况2在主镜上方 $1 0 \ \mathrm { c m }$ 处基本没有温差，因此 $C _ { \mathrm { T } } ^ { 2 }$ 下降很快。在主镜表面到 $5 \mathrm { m m }$ 高度范围内， $C _ { \mathrm { T } } ^ { 2 }$ 逐渐增大到 $0 . 2 3 \mathrm { K } ^ { 2 } \mathrm { m } ^ { - 2 / 3 }$ 后开始下降。最终计算得到工况1主镜视宁度 $ { \theta } = 0 . 1 5 ^ {  { \prime } \prime }$ ，而工况2为 $0 . 0 4 ^ { \prime \prime }$ ，与工况1相比降低了 $7 4 \%$ 。因此，工况2条件下主镜视宁度优于工况1，但此时两种工况下主镜视宁度均很小，对望远镜成像不会产生实质性影响。

![](images/efed4a57f0871d4797b34c68291093eeda9039820e036a916276deb25e8d6b50.jpg)  
图8工况1、2 $C _ { \mathrm { T } } ^ { 2 }$ 随高度变化曲线 Fig.8 $C _ { \mathrm { T } } ^ { 2 }$ of working status 1 and 2 changing with height

# 4主镜视宁度计算方法验证

文[12]从 $2 5 \ \mathrm { c m }$ 望远镜[13]和 $6 2 \ \mathrm { c m }$ 望远镜[14]主镜视宁度研究中，得到了通风条件下星像半高全宽的半经验公式：

$$
\theta = 0 . 1 8 { \left( \frac { g D } { T U ^ { 2 } } \right) } ^ { 0 . 3 } \varDelta T ^ { 1 . 3 } ,
$$

其中， $g$ 为重力加速度； $D$ 为主镜直径； $U$ 为主镜表面风速； $T$ 为参考温度； $\Delta T$ 为主镜表面与环境温度差。由于主镜口径接近，将其应用到$5 0 \ \mathrm { c m }$ 望远镜主镜视宁度计算中，并设置参考温度为 $0 \%$ 。表2为不同温差和风速条件下(6)式和计算流体动力学软件计算的主镜视宁度对比，可以看出二者差异较小，主镜视宁度主要对温度变化较为敏感，这一点与文[15]的研究结果一致。

# 表2CFD与(6)式计算主镜视宁度对比

Table 2Comparison of mirror seeing between   

<html><body><table><tr><td colspan="4">CFD and equation (6)</td></tr><tr><td>△T</td><td>速度U</td><td>公式计算</td><td>CFD 计算</td></tr><tr><td>/C</td><td>m/s</td><td>seeing/"</td><td>seeing/"</td></tr><tr><td>0.5</td><td>0.5</td><td>0.03</td><td>0.02</td></tr><tr><td>0.5</td><td>1</td><td>0.02</td><td>0.02</td></tr><tr><td>0.5</td><td>2</td><td>0.01</td><td>0.02</td></tr><tr><td>1</td><td>0.5</td><td>0.08</td><td>0.04</td></tr><tr><td>1</td><td>1</td><td>0.05</td><td>0.05</td></tr><tr><td>1</td><td>2</td><td>0.04</td><td>0.05</td></tr><tr><td>2</td><td>0.5</td><td>0.20</td><td>0.10</td></tr><tr><td>2</td><td>1</td><td>0.13</td><td>0.11</td></tr><tr><td>2</td><td>2</td><td>0.09</td><td>0.11</td></tr></table></body></html>

# 5总结与展望

本文以兴隆 $5 0 \mathrm { c m }$ 望远镜为例，建立计算流体动力学仿真计算模型，分析遮光筒和独立挡光环结构两种工况下主镜区域的扰流状态，给出了实际测试中难以得到的温度、速度场与湍流的分布图，并根据温度数据计算得到主镜视宁度。通过对这几个参量的分析可知，独立挡光环结构在空气环流和主镜散热方面要优于传统的遮光筒。

由于计算流体动力学模型是建立在简化和假设的物理模型基础上，实际的湍流及大气不稳定性很难用数学模型完整描述。文中可定性地说明在主镜视宁度控制上独立挡光环结构优于遮光筒。关于流场定量分析的准确性还需要与实测数据对比，但 $5 0 \ \mathrm { c m }$ 望远镜实验成本高，速度和湍流分布难以实测，测量点和结果存在局限性，实测难度较大。因此，本文给出的模拟结果意义在于分析遮光筒与独立挡光环结构的扰流特点，为后续合理选择消杂散光装置提供参考依据。相比于有遮光筒的情况，采用独立挡光环具有以下优点：

(1)主镜散热均匀，整个模型内温度梯度较小;  
(2)在主镜区域影响较大的部分，湍流强度降低了 $6 . 5 1 \%$ ;  
(3)无绕流漩涡，挡光环厚度对空气流动影响很小，速度分布比有遮光筒时均匀;  
$( 4 ) C _ { \mathrm { T } } ^ { 2 }$ 降低，主镜视宁度下降了 $7 4 \%$ 。

综合以上扰流与杂散光分析结果，可选取合适的消杂散光装置。在后期的研究中，将计算流体动力学方法模拟的主镜散热过程与实测对比，可推广到分析任何望远镜的气流场和视宁度，对望远镜及圆顶的设计有一定应用价值。

# 参考文献：

[1] BelyPY.The design and construction of large optical telescopes[M]. Berlin：Springer，2003.  
[2] Siegmund W A，Limmongkol S,Hull $\mathrm { ~ C ~ L ~ }$ ，et al. Sloan digital sky survey $2 . 5 \mathrm { - m }$ telescope : lightbaffles [C]// Proceedings of SPIE.1998.  
[3] 赵飞，王森.兴隆 $1 \mathrm { m }$ 光学望远镜杂散光效应研究［J]．天文研究与技术—国家天文台台刊，2010，7(2)：158-167.Zhao Fei，Wang Sen. Study of stray light for the Xinglong 1-meter optical telescope [J].Astronomical Research & Technology———Publications of National Astronomical Observatories ofChina，2010，7(2):158-167.  
[4] Gunn JE，Siegmund W A，Mannery EJ，et al.The $2 . 5 \mathrm { m }$ telescope of the sloan digital skysurvey[J].The Astronomical Journal，2006，131(4）:2332-2359.  
[5] Haldeman B J,Haynes R M，Posner V，et al. Design and performance characterization of theLCOGTN one-meter Telescope Optical Tube Assembly [C]// Proceedings of SPIE.2010.  
[6] 王福军.计算流体动力学分析：CFD 软件原理与应用［M]．北京：清华大学出版社，2004.  
[7] Pazder JS，Vogiatzis K，Angeli G Z. Dome and mirror seeing estimates for the Thirty MeterTelescope [C]//Proceedings of SPIE.2008.  
[8] 张俊.蜂窝镜温度与镜面视宁度控制方法研究［D].北京：中国科学院大学（光电技术研究所），2013.  
[9] 唐家鹏.FLUENT14.0超级学习手册［M].北京：人民邮电出版社，2013.  
[10] Tatarskii VI. Wave propagation in turbulent medium [M]. New York:McGraw-Hill,1961.  
[11] Roddier F.V the effects of atmospheric turbulence in optical astronomy [J]. Progress in Optics,1981，19: 281-376.  
[12] Zago L. Engineering handbook for local and dome seeing [C]// Proceedings of SPIE.1997.  
[13] Iye M,Noguchi T,Torii Y,et al. Evaluation of seeing on a 62-cm mirror［J].Publications ofthe Astronomical Society of the Pacific，1991，103：712-722.  
[14] Lowne C M. An investigation of the efcts of mirror temperature upon telescope seeing [J].Monthly Notices of the Royal Astronomical Society，1979，188(2）:249-259.  
[15] Vogiatzis K，Upton R. TMT studies on thermal seeing modeling:mirror seeing model validation[C]// Proceedings of the SPIE.2006.

# A Study of Baffle Turbulence in Open Truss Telescope Based on CFD Software

Li Taoran1,2 (1.KeyLabratoryofOpticalAstrooy,atioalAstroomicalObservatoris，inseAcadeyofSienes，Beijingoina, Email：litaoran@bao.ac.cn；2.University of Chinese Academy of Sciences，Beijing 10oo49,China)

Abstract：Primary bafle would influence the airflow above the primary mirror，which is not conducive to heat exchange between the mirror's surface and the ambient air. The $5 0 \mathrm { { c m } }$ Telescope at Xinglong Observatory is influenced by two kinds of stray light suppression devices—bafle and vanes.In this paper，ananalysis of airflow and temperature around the primary mirror of the $5 0 \mathrm { { c m } }$ Telescope has been carried out with CFD software.Miror seeing has also been calculated with CFD data. Analysis results indicate that，the primary baffle will cause nonuniform temperature distribution，large area of turbulence and asymmetry vortex.In the case of independent vanes，mirror seeing decreases by $74 \%$ . These results show that the primary baffle has major disadvantages in respect of mirrorcooling and air circulation.With the help of airflow and stray light analysis，plans for stray light control can be chosen more reasonably.The CFD analysis method could be helpful to telescope design and transformation.

Key words: Open truss telescope；CFD；Baffle； Turbulent model； Mirror seeing