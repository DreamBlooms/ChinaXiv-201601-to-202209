# 基于EEMD的太阳绕太阳系质心运动和太阳活动Hallstatt周期分析

王琳琳¹，王建²，孙威,4，王婕¹  
(1.南京师范大学地理科学学院,江苏 南京210023；2.江苏第二师范学院城市与资源环境学院，  
江苏 南京211200；3.上海工程技术大学数理与统计学院,上海201620；4.安庆师范大学资源环境学院，安徽 安庆246133)

摘要：基于行星会合指数运动学方程，推演出太阳质心到太阳系质心距离变化的计算公式，并利用该公式重建太阳质心相对于太阳系质心的距离变化时间序列，作为太阳轨道运动的替代性指标,使用聚合经验模态分解（Ensemble empirical mode decomposition,EEMD)方法分析 $0 { \sim } 2 5 . 0 \mathrm { k a }$ BP太阳质心到太阳系质心的距离与 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列。结果显示：两者均存在蕴含\~2300a周期(Hall-statt cycle)的IMF分量；互相关分析证实两者蕴含的Hallstatt周期分量间具有相关性， $0 { \sim } 1 3 . 9 \mathrm { k a }$ BP与 $1 3 . 9 { \sim } 2 5 . 0 \mathrm { k a B P }$ 年代相关系数分别可达0.52、0.44，并且太阳质心到太阳系质心距离的变化超前于太阳活动指标 $\Delta ^ { 1 4 } \mathrm { C }$ 的变化。表明太阳质心远离太阳系质心时，大气 $^ { 1 4 } \mathrm { C }$ 含量增加，对应于太阳活动较弱的时期;太阳质心靠近太阳系质心时，大气 $^ { 1 4 } \mathrm { C }$ 含量减小，对应于太阳活动较强的时期。这一认识对于进一步探究太阳活动Hallstatt周期的成因机制提供了新的依据和思路。

关键词：太阳系质心；太阳活动；Hallstatt周期；聚合经验模态分解(EEMD)

# 文章编号：

太阳活动的强弱直接或间接影响地球系统动力学过程,对许多地球物理现象影响深远[1]。因此,对于太阳活动变化规律的研究一直受到学者们的关注和重视[2-3]

$^ { 1 4 } \mathrm { C }$ 生产率和太阳活动强度变化有关[4-5],其作为太阳活动替代性指标被广泛应用于太阳活动变化规律的研究中。Suess[利用 $^ { 1 4 } \mathrm { C }$ 检测出太阳活动周期 2400a; Damon 和 Sonett[7]检测出周期 2241 a;Vasiliev和Dergachev&检测出周期 $2 4 0 0 \textrm { a }$ ;尹志强等[1]对Solanki等[9]利用 $^ { 1 4 } \mathrm { C }$ 重建的太阳黑子数据进行Lomb-Scargle谱分析,检测出周期 $2 2 7 0 \mathrm { a }$ 。但是，关于这个显著的\~2300 a太阳活动周期(Hallstatt cy-cle)产生的原因，还缺乏相对一致的意见。

对于太阳活动变化机制目前主要有两种解释[10]一种是太阳发电机理论[1I-12];另一种是太阳系行星系统驱动理论。太阳系行星系统驱动理论，又可分为两种，一是行星系统对太阳的引潮力作用[13-14]，二是行星系统作用下太阳绕太阳系质心的轨道运动[15-17],后者近年来逐渐成为学者关注的焦点。

Charvatova[16]首次提出2100\~2500a的振荡可能是由于太阳绕转运动，其利用一个简化模型模拟的太阳绕转运动，具有平均2402.2a周期，相当于木星-日心-地心排成一列( $9 . 8 8 5 \times 2 4 3$ ),在每一个周期中，都具有370a的标准三叶形循环模式，于8000a的 $^ { 1 4 } \mathrm { C }$ 代理记录中对应太阳活动较高时期。Scafetta等[18]计算行星系质心相对于太阳运动轨道的瞬时偏心矢量变化，发现具有2318a周期，与利用谐波曲线拟合 $^ { 1 4 } \mathrm { C }$ 去趋势分析后的残差记录对比，图像基本对应，相位差 $\pi / 2$ ，由此认为在Hallstatt周期尺度上，行星系质心相对于太阳运动轨道由更椭圆的形状演化为更圆的形状时，产生的放射性核粒子会更多，从而调节进人太阳系及地球的宇宙射线通量。刘复刚等[基于修正系数( $\scriptstyle q = 1 . 1 1 5 1 8 ,$ 计算行星会合指数图像与8000a的 $^ { 1 4 } \mathrm { C }$ 曲线对比，探讨两者之间的关系，认为行星会合指数极大值包络线中的谷值表明此时太阳所具有的势能较小，向行星际空间释放的能量相对减少，从而使进入地球大气的宇宙射线和能量粒子沉降增加， $^ { 1 4 } \mathrm { C }$ 含量增大。

前人研究已取得一些成果，但是在探究太阳轨道运动与 $^ { 1 4 } \mathrm { C }$ 关系时，采取简单图像对比，或预先设定函数关系式进行曲线拟合，于分析结果注人了人为因素;且研究年代大多集中在全新世，而放射性碳年表(INTCAL13[20])具有10a分辨率的 $\Delta ^ { 1 4 } \mathrm { C }$ 记录已拓展到 $2 5 . 0 \mathrm { k a B P }$ 。

2013年，刘复刚和王建提出行星会合指数 $K$ 研究行星系统运动规律，本文基于这个指数，推算出太阳质心到太阳系质心的距离公式，并计算其随时间变化的序列；利用EEMD方法对 $0 { \sim } 2 5 . 0 \ \mathrm { k a }$ BP太阳质心到太阳系质心的距离与 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列进行分析,直接分解出两序列的\~2300 a周期(Hallstatt cy-cle)IMF分量，并进行互相关分析，以太阳质心到太阳系质心的距离变化作为太阳轨道运动的指标，探索太阳轨道运动周期与太阳活动周期之间的关系。

# 1数据与方法

# 1.1太阳质心到太阳系质心距离变化计算公式与时间序列数据

1.1.1行星系质心绕日会合指数定义经过太阳系质心并且垂直于太阳系总角动量矢量的平面为不变平面，它与太阳系八大行星轨道平面的夹角平均为 $1 . 8 4 ^ { \circ }$ ,外行星的倾角都小于 $1 ^ { \circ }$ ，内行星除水星倾角较大为 $6 . 3 5 ^ { \circ }$ 外，其它行星都在 $2 ^ { \circ }$ 左右[22]，因此可以近似将各行星轨道平面视为在不变平面上，由此建立坐标系[23],如图1[21]所示。将太阳系中八大行星视为质点， $\boldsymbol { P } _ { i }$ ( $i = 1 , 2 , 3 , \cdots , 8 )$ 代表各行星以质量为权重的位矢末端， $m _ { i } \setminus \varphi _ { i } \setminus r _ { i }$ 分别为各行星的质量、日心经度以及其相对于太阳质心的位矢半径。则行星系质心（P）相对于太阳质心（S)的位矢 $r _ { \mathrm { { P } } }$ 为[24-25]：

$$
r _ { \mathrm { P } } = \mathrm { S P } = { \frac { \displaystyle \sum _ { i = 1 } ^ { 8 } m _ { i } r _ { i } } { \displaystyle \sum _ { i = 1 } ^ { 8 } m _ { i } } }
$$

![](images/10a14f17da72abb0a9f189150fe690fd3b961c6a2fce46e72fc204e19f814d5a.jpg)  
图1行星会合示意图  
Fig.1Sketch map of planetary rendezvous

公式(1)为太阳质心S到行星系质心P的位矢方程，位矢的始端为太阳质心，末端为行星系质心，由此可知，行星系质心是各行星以质量为权重距太阳质心的权重半径的矢量和。

根据此原理，刘复刚和王建[21把行星绕日旋转轨道的权重半径矢量和的模，定义为行星会合指数。太阳系行星会合指数 $( \kappa )$ 的运动学方程为[21]：

$$
K = { \sqrt { \left[ \sum _ { i = 1 } ^ { 8 } r _ { i } \sin ( \varphi _ { i } + \omega _ { i } t ) \right] ^ { 2 } + \left[ \sum _ { i = 1 } ^ { 8 } r _ { i } \cos ( \varphi _ { i } + \omega _ { i } t ) \right] ^ { 2 } } }
$$

式中： $K$ 为行星会合指数； $r _ { i }$ 为行星轨道的权重半径； $\varphi _ { i }$ 为行星的初始日心经度； $\omega _ { i }$ 为平均角速度; $\mathbf { \chi } _ { t }$ 为时间。行星会合指数可以指代行星相会合和相背离的程度，又因为行星以质量为权重的半径 $r _ { i }$ 的矢量和代表行星系统质心的位置，所以行星会合指数 $K$ 还表示行星系统质心与太阳质心之间的距离。1.1.2太阳质心到太阳系质心距离变化计算如果把太阳系八大行星看作一个系统，根据二体围绕共同质心相互绕转的规律，太阳质心和行星系统质心围绕太阳系质心相互绕转，3个质心在一条直线上。假设太阳和行星系统的质量分别为 $M _ { \mathrm { s } }$ 和 $M _ { \mathrm { P } }$ ，太阳质心和行星统质心距离及太阳系质心距离分别为 $| R _ { \mathrm { s } } |$ 和 $R _ { \mathrm { P } }$ 。则 $M _ { \mathrm { s } } R _ { \mathrm { s } } { = } M _ { \mathrm { p } } R _ { \mathrm { p } }$ ，又由于$K { = } R _ { \mathrm { s } } { + } R _ { \mathrm { p } }$ ,可推出：

$$
M _ { \mathrm { s } } R _ { \mathrm { s } } { = } M _ { \mathrm { p } } \big ( K { - } R _ { \mathrm { s } } \big )
$$

$$
R _ { \mathrm { s } } = K M _ { \mathrm { p } } \big / \big ( M _ { \mathrm { s } } + M _ { \mathrm { p } } \big )
$$

根据公式(2）、（4)，利用表1中的相关数据（八大行星的平均角速度，质量权重半径，2000年1月1

表1太阳系行星轨道相关天文数据(历年 $\scriptstyle = \mathbf { J } 2 \mathbf { 0 } \mathbf { 0 } \mathbf { 0 } = \mathbf { 2 } \mathbf { 0 } \mathbf { 0 } \mathbf { 0 }$ January 1.5)  
Tab.1 Astronomical data of the planetary orbits in the solar system   

<html><body><table><tr><td>名称</td><td>与不变平面倾角/</td><td>平均角速度/rad·a-</td><td>平均轨道半径/AU</td><td>质量/102kg</td><td>质量权重半径/AU</td><td>日心经度/</td><td>转换成弧度/rad</td></tr><tr><td>水星</td><td>6.35</td><td>26.088408</td><td>0.38709893</td><td>0.33</td><td>0.000048</td><td>252.25084</td><td>4.402608</td></tr><tr><td>金星</td><td>2.15</td><td>10.213444</td><td>0.72333199</td><td>4.87</td><td>0.001321</td><td>181.97973</td><td>3.176145</td></tr><tr><td>地球</td><td>1.57</td><td>6.283185</td><td>1.00000011</td><td>5.97</td><td>0.002238</td><td>100.46435</td><td>1.753434</td></tr><tr><td>火星</td><td>1.63</td><td>3.340667</td><td>1.52366231</td><td>0.64</td><td>0.000366</td><td>355.45332</td><td>6.203831</td></tr><tr><td>木星</td><td>0.32</td><td>0.529700</td><td>5.20336301</td><td>1898.19</td><td>3.702624</td><td>34.40438</td><td>0.600470</td></tr><tr><td>土星</td><td>0.93</td><td>0.213303</td><td>9.53707032</td><td>568.34</td><td>2.031931</td><td>49.94432</td><td>0.871693</td></tr><tr><td>天王星</td><td>0.99</td><td>0.074790</td><td>19.19126393</td><td>86.81</td><td>0.624538</td><td>313.23218</td><td>5.466933</td></tr><tr><td>海王星</td><td>0.74</td><td>0.038129</td><td>30.06896348</td><td>102.41</td><td>1.154374</td><td>304.88003</td><td>5.321160</td></tr></table></body></html>

注：第二列和第三列数据分别引自文献[22]和[24];其它基础数据引自NASA。

日12:00的日心经度，以及其与太阳的质量)进行计算，即可获得太阳质心到太阳系质心距离随时间变化的数据序列。

# 1.2太阳活动替代性指标 $^ { 1 4 } \mathrm { { C } }$ 数据来源

自然界中的 $^ { 1 4 } \mathrm { C }$ 主要是宇宙射线中的中子与地球大气 $^ { 1 4 } \mathrm { N }$ 相互作用的产物。由于地球存在磁场，宇宙射线在到达地球附近时会发生偏转，因此地磁场的强度会影响大气中的宇宙射线通量[25]。图2中$^ { 1 4 } \mathrm { C }$ 数据的长期趋势,正是由于地球磁偶极场的变化所导致的， $^ { 1 4 } \mathrm { C }$ 中的短期变动反映的则是太阳活动的变化[9.26]。太阳活动强烈,太阳黑子增加时,会伴随着更强的太阳风。太阳风的主要成分是质子和电子，是一种等离子体带电粒子流，其磁屏蔽特性会对宇宙射线产生较强的作用，从而使地球大气中的$^ { 1 4 } \mathrm { C }$ 生产率降低。因此太阳活动增强(黑子数增多)对应的是较低的大气 $^ { 1 4 } \mathrm { C }$ 生产率，太阳活动减弱（黑子数减少)对应的是较高的大气 $^ { 1 4 } \mathrm { C }$ 生产率，这些都被记录在生物有机体中(树轮、珊瑚等）。 $^ { 1 4 } \mathrm { C }$ 浓度随时间呈周期性变化,最著名的是\~210a(deVries cy-cle)和\~2300 a周期(Hallstatt cycle）。

图2显示 $5 0 . 0 \mathrm { k a }$ BP的 $\Delta ^ { 1 4 } \mathrm { C }$ 记录 $\mathrm { ^ { \prime } I N T C A L 1 } 3 ^ { [ 2 0 ] }$ ，数据来源网站 http://radiocarbon.webhost.uits.arizona.

![](images/5d8049a13a611ff6075d70be31b564a9f61a60105134dab15378186b9e6b386c.jpg)  
图2大气放射性碳水平 $\Delta ^ { 1 4 } \mathrm { C }$ Fig.2 Radiocarbon series $\Delta ^ { 1 4 } \mathrm { C }$

edu $/ , 0 { \sim } 1 3 . 9 \ \mathrm { k a }$ BP数据分辨率为5a, $1 3 . 9 { \sim } 2 5 . 0 \ \mathrm { k a }$ BP为 $1 0 \textrm { a } , 2 5 . 0 { \sim } 5 0 . 0 \mathrm { ~ k a ~ B P }$ 为 $2 0 \mathrm { ~ a ~ }$ 。 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列中,早于 $2 5 . 0 \mathrm { k a }$ BP的数据曲线更为平滑，且误差相对较大，因此本文研究集中于 $0 { \sim } 2 5 . 0 \ \mathrm { k a \ B P }$ 。需要引起重视的一点是，年表中 $0 { \sim } 1 3 . 9 \mathrm { ~ k a }$ BP数据主要来自树轮，而更早的数据主要来自海洋记录：珊瑚、有孔虫等。两者的不同在于，树木可以直接吸收空气中的碳，而珊瑚等海洋生物吸收的溶解在水里的碳可能已经被稀释相当长的时间[18.27]

# 1.3EEMD分析方法

1998年,Huang等[28提出了适用于非线性、非平稳序列信号分析的经验模态分解方法(Empiricalmodedecomposition，EMD），认为任何数据信号都是一系列有限的本征模态函数(IMFs)的混叠。EMD方法，按照高频至低频的顺序，剥离出这些IMF分量，分解过程不同于小波分析需要借助基函数，而是按照信号自身的特性自适应地把复杂数据序列分解成一系列具备平稳信号特征的IMFs[29]。这样分解出的每个分量所蕴含的周期及其物理意义便更加直观。EMD方法在广泛应用时，发现可能会存在模态混叠，导致分解出的IMF分量可能没有实在的物理意义。针对这一问题，2009年 ${ { \mathbb { W } } _ { \mathrm { } } } \mathrm { { u } }$ 等[30在EMD基础上加以改进，提出了聚合经验模态分解方法(EEMD)，通过向信号中加入高斯白噪声来避免模态混叠效应，使最终分解的IMFs保持了物理上的唯一性。EEMD方法能将时间序列分解成若干真实的有物理意义的IMF分量和表示序列总体趋势的趋势项[31]

以EEMD方法直接剥离出太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列的Hallstatt周期分量，而不

# 干吴区地理

需要预先设定函数关系式对数据序列进行拟合，减少注入人为因素，可以更大程度上保留周期信号，提高计算精度。

# 2结果与分析

# 2.1太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathbf { C }$ 时间序列的EEMD分析

由公式(2）、(4)计算得到 $0 { \sim } 2 5 . 0 \mathrm { k a }$ BP太阳质心到太阳系质心距离随时间变化的数据序列，数据间隔为1a，绘制成图3a（为方便与 $\Delta ^ { 1 4 } \mathrm { C }$ 数据作对比，以1950AD作为起始点），纵坐标表示太阳质心到太阳系质心的距离大小，单位为太阳半径，太阳质心距太阳系质心变化范围在 $0 { \sim } 2 . 2$ 之间，即最小时太阳质心变化可以与太阳系质心接近重合，最大时距太阳系质心超过一个太阳直径大小。使用EEMD方法对太阳质心到太阳系质心距离时间序列进行多时间尺度分解， $\scriptstyle \mathrm { N E = 1 0 0 } , \mathrm { N s t d } = 0 . 2$ ，即集合样本数取值100，白噪声标准差取原数据序列标准差的0.2倍。分解出高频至低频的13个IMF分量以及一个趋势项Res。各IMF分量对应周期列于表2。IMF10准周期为2273a，为Hallstatt周期分量(图3a)。

使用EEMD方法对 $0 { \sim } 2 5 . 0 \ \mathrm { k a \ B P }$ 的 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列进行多时间尺度分解，数据间隔为 $1 0 \mathrm { ~ a ~ }$ ，取 ${ \mathrm { N E } } =$ $1 0 0 , \mathrm { N s t d } { = } 0 . 2$ 。分解出高频至低频的10个IMF分量以及一个趋势项Res。各IMF分量对应周期列于表2,计算出的周期与文献[732]计算的 $\Delta ^ { 1 4 } \mathrm { C }$ 周期基本对应。IMF7准周期为2456a,为Hallstatt周期分量（图3b）。

太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列都包含\~2300a的Hallstatt周期分量，将两者绘制在图3c中，对比发现\~2300a的Hallstatt周期波动基本一一对应。为进一步探究两序列Hallstatt周期分量间的相关关系，利用IBMSPSSStatistics23数据分析软件对其进行互相关分析。

# 2.2Hallstatt周期分量间的互相关关系

$\Delta ^ { 1 4 } \mathrm { C }$ 年表中 $0 { \sim } 1 3 . 9 \mathrm { \ k a \ B P }$ 数据主要来自树轮，而更早的数据主要来自海洋记录，因此以 $1 3 . 9 \mathrm { { k a } }$ BP为分界线分别计算 $0 { \sim } 1 3 . 9 \mathrm { \ k a \ B P }$ 与 $1 3 . 9 { \sim } 2 5 . 0 \mathrm { k a }$ BP太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列Hallstatt周期分量间的互相关关系，如图4所示。

图4中横坐标的正值表示太阳质心到太阳系质心距离变化领先于 $\Delta ^ { 1 4 } \mathrm { C }$ 变化，负值则表示滞后于$\Delta ^ { 1 4 } \mathrm { C }$ 。图4a相关系数在相对位移为320a时达到极大值0.52（在0.01级别相关性显著），表示 $0 { \sim } 1 3 . 9 \mathrm { k a }$ BP太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列的Hallstatt周期分量间，具有正相关关系，太阳质心到太阳系质心距离变化领先于 $\Delta ^ { 1 4 } \mathrm { C }$ 变化 $3 2 0 \mathrm { ~ a ~ }$ 。这与Scafetta等[18计算的全新世行星系质心相对于太阳运动轨道的瞬时偏心矢量变化与 $\Delta ^ { 1 4 } \mathrm { C }$ 变化 $\pi / 2$ （约

![](images/4273323a21f2c7cd113bba792a7ad84b66330d1b3e7fe0d69fbc3507cda0ff3c.jpg)  
图3太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列的Hallstatt周期分量对比图 Fig.3 Components with Hallstatt cycle decomposed from the time series of $\Delta ^ { 1 4 } \mathrm { C }$ and distance between the solar centroid and the solar system's centroid

# 表2太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列各分量准周期

Tab.2 Period of the components decomposed from the time series of $\Delta ^ { 1 4 } \mathbf { C }$ and distance between the solar centroid and the solar system’ s centroid   

<html><body><table><tr><td>模态分量</td><td>质心距离准周期/a</td><td>△C准周期/a</td></tr><tr><td>IMF1</td><td>3.9~12.8</td><td>22.6~41.0</td></tr><tr><td>IMF2</td><td>12.8</td><td>74.0</td></tr><tr><td>IMF3</td><td>19.8</td><td>130.0~208.0</td></tr><tr><td>IMF4</td><td>35.3~45.4</td><td>357.0</td></tr><tr><td>IMF5</td><td>60.9~92.6</td><td>446.0~961.0</td></tr><tr><td>IMF6</td><td>171.0~185.0</td><td>926.0~2084.0</td></tr><tr><td>IMF7</td><td>568.0</td><td>2456.0</td></tr><tr><td>IMF8</td><td>735.0~1191.0</td><td>6253.0</td></tr><tr><td>IMF9</td><td>1136.0</td><td>25000.0</td></tr><tr><td>IMF10</td><td>2273.0</td><td>25000.0</td></tr><tr><td>IMF11</td><td>6250.0</td><td>1</td></tr><tr><td>IMF12</td><td>12500.0</td><td>1</td></tr><tr><td>IMF13</td><td>25000.0</td><td>1</td></tr></table></body></html>

注：“-"表示无结果。

580a)的相位差相似。

图4b相关系数在相对位移为1870a时达到极大值0.44(在0.01级别相关性显著），这可能是由于$\Delta ^ { 1 4 } \mathrm { C }$ 年表中 $1 3 . 9 { \sim } 2 5 . 0 \ \mathrm { k a }$ BP数据主要来自海洋记录，不同于树木可以直接吸收空气中的碳，珊瑚等海洋生物吸收的溶解在水里的碳已经被稀释相当长的时间[18]。因此 $1 3 . 9 { \sim } 2 5 . 0 \mathrm { ~ k a ~ l }$ 3P太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列Hallstatt周期分量间，仍具有正相关关系，但是相位差有所不同。

距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列Hallstatt周期分量间的互相关系数在相对位移为120a时达到极大值0.35(在0.01级别相关性显著)，呈正相关。

以上分析显示，太阳质心到太阳系质心距离变化与 $\Delta ^ { 1 4 } \mathrm { C }$ 变化均存在的\~2300aHallstatt周期分量呈正相关关系，太阳质心到太阳系质心距离变化可能领先于 $\Delta ^ { 1 4 } \mathrm { C }$ 变化 $3 2 0 \mathrm { a }$ 。即太阳质心到太阳系质心的距离增大时，大气 $^ { 1 4 } \mathrm { C }$ 含量增加;太阳质心到太阳系质心的距离减小时，大气剩余 $\cdot \Delta ^ { 1 4 } \mathrm { C }$ 含量减小。由于大气 $^ { 1 4 } \mathrm { C }$ 生产率与太阳活动强度呈负相关关系，因此\~2300a周期中太阳质心远离太阳系质心时对应于太阳活动较弱时期，太阳质心靠近太阳系质心时对应于太阳活动较强时期。太阳轨道运动通过影响太阳活动可能也影响了地球气候变化，如全新世$0 . 4 { \sim } 0 . 6 \ \mathrm { k a } , 2 . 8 \ \mathrm { k a } , 5 . 9 \ \mathrm { k a } , 8 . 2 \ \mathrm { k a } , 1 0 . 3 \ \mathrm { k a }$ 的5次冷事件[33-37]基本发生在太阳质心远离太阳系质心,太阳活动较弱时期。

太阳绕太阳系质心运动影响太阳活动的具体机制尚不清楚，Scafetta等[18]认为太阳轨道运动可能对太阳系动力学相关机制具有指代作用，原则上，行星运动可以直接产生引力或电磁力作用于太阳，并与日球层相互作用，从而调节地月系统周围的宇宙射线通量以及行星际宇宙尘埃浓度[38-39]。刘复刚4°认为太阳自转角动量与太阳绕太阳系质心的绕转角动量之和守恒。太阳质心远离太阳系质心时，太阳绕转半径增加，引起太阳绕转角动量增大，由于太阳自转角动量与绕转角动量之和守恒，太阳自转角动量减小，导致太阳自转速度减小，太阳活

![](images/7021178716a1a7b6e8fe37c494e1f308e515c83e2ef626d4915ebbde64c753c2.jpg)  
图4c中 $0 { \sim } 2 5 . 0 \ \mathrm { k a }$ BP太阳质心到太阳系质心  
注：表示在0.01级别(双尾)相关性显著。  
图4太阳质心到太阳系质心距离和 $\mathrm { \Delta ^ { \cdot } A ^ { \scriptscriptstyle 1 4 } C }$ 时间序列的Hallstatt周期分量互相关系数 Fig.4 Cross-correlation coefficient of the components with Hallstatt cycle decomposed from the time series of $\Delta ^ { 1 4 } \mathrm { C }$ and distance between the solar centroid and the solar system's centroid

# 干旱区地理

动减弱；反之，太阳质心靠近太阳系质心时，太阳绕转半径缩小，引起太阳绕转角动量减小，自转角动量增加，从而导致太阳自转速度增大，太阳活动增强。上述理论对于理解太阳质心到太阳系质心距离与太阳活动强度的负相关关系具有很好的启示作用，但具体机制仍要作进一步的研究

# 3结论

（1）文章基于行星会合指数，推算太阳质心到太阳系质心距离变化的公式，并计算出时间序列数据，发现其变化范围在0\~2.2之间（单位为太阳半径），即最小时太阳质心变化可以与太阳系质心接近重合，最大时距太阳系质心超过一个太阳直径大小。利用EEMD方法对 $0 { \sim } 2 5 . 0 \mathrm { k a B P }$ 太阳质心到太阳系质心的距离时间序列进行分析，分解出 $\sim 2 3 0 0$ a周期（Hallstatt cycle)的IMF分量。

（2）不同于传统方式对于 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列的去趋势、曲线拟合数据处理，采用EEMD方法按照信号自身的特性自适应地分解出具备平稳信号特征的Hallstatt周期分量，使其所蕴含的周期及物理意义更加直观准确。

(3）由于 $\Delta ^ { 1 4 } \mathrm { C }$ 年表中数据来源不同，以 $1 3 . 9 \mathrm { { k a } }$ BP为分界线分别计算 $0 { \sim } 1 3 . 9 \mathrm { \ k a \ B P }$ 与 $1 3 . 9 { \sim } 2 5 . 0 \mathrm { k a }$ BP太阳质心到太阳系质心距离和 $\Delta ^ { 1 4 } \mathrm { C }$ 时间序列Hallstatt周期分量间的互相关关系，互相关系数可达0.52、0.44，呈正相关。太阳轨道运动与太阳活动的关系研究不再局限于全新世，拓展到 $2 5 . 0 \mathrm { k a B P }$ O

(4）以太阳质心到太阳系质心距离变化指代太阳轨道运动，以 $\Delta ^ { 1 4 } \mathrm { C }$ 变化指代太阳活动，两者均存在$\sim 2 3 0 0$ a 的Hallstatt周期分量，并且具有相关性（太阳质心到太阳系质心距离变化与 $\Delta ^ { 1 4 } \mathrm { C }$ 数据呈正相关，即与太阳活动变化呈负相关)，表明太阳质心远离太阳系质心时，大气剩余 $\cdot \Delta ^ { 1 4 } \mathrm { C }$ 含量增加，即太阳活动减弱；太阳质心靠近太阳系质心时，大气剩余 $\cdot \Delta ^ { 1 4 } \mathrm { C }$ 含量减小，即太阳活动增强。

# 参考文献(References)

[1]尹志强,马利华,韩延本,等.太阳活动的甚长周期性变化[J].科 学通报,2007,52(16):1859-1863.[Yin Zhiqiang,Ma Lihua,Han Yanben,et al.Long periodic variation of solar activity[J].Chinese Science Bulletin,2007,52(16): 1859-1863.]   
[2] EddyJA.The maunder minimum[J]. Science,1976,192(4245): 1189-1202.   
[3]Friis-Christensen E,Lassen K.Length of the solar cyele: An indicator of solar activity closely associated with climate[J]. Science, 1991,254(5032): 698-700.   
[4]Stuiver M, Quay PD.Changes in atmospheric carbon-14 atributed to a variable Sun[J]. Science,1980,207(4426): 11-19.   
[5]范章云,戴开美.大气中 $^ { 1 4 } \mathrm { C }$ 浓度的变化[J].物理学进展,1984 (4): 3-25.[Fan Zhangyun,Dai Kaimei. Variations of $^ { 1 4 } \mathrm { C }$ concentration of the atmosphere[J]. Progressin Physics,1984(4): 3-25.]   
[6]Suess H E.The radiocarbon record in tree rings of the last 8000 years[J]. Radiocarbon,1980,22(2): 200-209.   
[7]Damon PE,Sonett CP.Solar and terrestrialcomponents of the atmospheric 4G variation spectrum[C/Sonett C P, Glampapa M S, Matthews MS.The Sun in Time.Arizona: The University of Arizona Press,1991: 360-388.   
[8]Vasiliev S S, Dergachev VA.The 240O-year cycle in atmospheric radiocarbon concentration: Bispectrum of $^ { 1 4 } \mathrm { C }$ data over the last 8000 years[J]. Annales Geophysicae,2002,20(1): 115-120.   
[9]Solanki S K, Usoskin IG, Kromer B,et al. Unusual activity of the Sun during recent decades compared to the previous 110oO years [J]. Nature,2004,431(7012): 1084-1087.   
[10] 周德帅.太阳Hale周期长度的预测反演及其在气候变化研究 中的应用[D].南京:南京师范大学,2016.[Zhou Deshuai.Prediction of the length of Hale cyele and its application in the study of climate change[D]. Nanjing: Nanjing Normal University,2016.]   
[11]Parker E N.Hydromagnetic dynamo models[J].Astrophysical Journal,1955,122(2): 293.   
[12]Beer J,Tobias S M, Weiss N O. On long-term modulation of the Sun's magnetic cycle[J]. Monthly Notices of the Royal Astronomical Society,2017,473(2): 1596-1602.   
[13]Hung C C.Apparent relations between solar activity and solar tidescausedbytheplanets[EB/OL].htps://trs.nasa.gov/search jsp?R=20070025111,2007-07/2020-06-02.   
[14]Hantzsche E.On the tidal theory of solar activity[J].Astronomische Nachrichten,1978,299(5): 259-267.   
[15]Jose P D.Sun’s motion and sunspots[J].Astronomical Journal, 1965, 70(3): 193.   
[16] Charvatova I. Can origin of the 24OO-year cycle of solar activity be caused by solar inertial motion[J]. Annales Geophysicae,2000,18 (4): 399-405.   
[17] 刘复刚,郑一,王建,等.太阳轨道运动的2400年周期与轨道周 期[J].空间科学学报,2015,35(4):381-392.[Liu Fugang,Zheng Yi, Wang Jian,et al.24OO years and track cycles of the Sun's orbital motion[J]. Chinese Journal of Space Science,2015,35(4): 381-392.]   
[18] Scafetta N,Milani F,BianchiniI A,et al. On the astronomical origin of the Hallstattoscillation found in radiocarbon and climate records throughout the Holocene[J].Earth Science Reviews,2016, 162: 24-43.   
[19]刘复刚,姚允龙,鲍锟山,等.准双世纪和Hallstatt气候变化周 期对太阳轨道运动调控太阳活动的响应[J].第四纪研究, 2018,38(6):1507-1517.[Liu Fugang,Yao Yunlong,Bao Kunshan,et al.Response of quasi bi-centurial and Hallstatt climate change periodic to the solar activity controlled by solar orbital motion[J]. Quaternary Sciences,2018,38(6): 1507-1517.]   
[20]ReamerPJ,Bard E,Bayliss A,et al.IntCall3 and Marinel3 radiocarbon age calibration curves O-5OooO years cal BP[J]. Radiocarbon, 2013,55(4): 1869-1887.   
[21] 刘复刚,王建.行星会合指数变化与太阳绕太阳系质心运转的 周期[J].地球物理学报,2013,56(5):1457-1466.[Liu Fugang, Wang Jian. Changes of the planet juncture index and solar revolution cycle around the mass center of the solar system[J]. Chinese Journal of Geophysics,2013,56(5): 1457-1466.]   
[22]Souami D,Souchay J. The solar system’s invariable plane[J].Astronomy and Astrophysics,2012,543:A133.   
[23] 戴文赛.太阳系演化学[M].上海:上海科学技术出版社,1979: 22-23.[Dai Wensai.The evolution of the solar system[M].Shanghai: Shanghai Scientific & Technical Publishers,1979: 22-23.]   
[24] 孙威,王建,陈金如,等.近两千年以来行星会合指数与行星系 日心经度变化及频谱分析[J].科学通报,2017,62(5):407-419. [Sun Wei,Wang Jian,Chen Jinru,et al.Variations of the planet juncture index and heliocentric longitude with spectral analysis for approximately 200O years[J]. Science China Press,2017,62(5): 407-419.]   
[25] 孙威,王建,陈金如,等.行星会合指数与行星系质心的日心经 度模型构建及数值模拟[J].地球物理学进展,2017,32(2):506- 515.[Sun Wei,Wang Jian,Chen Jinru,etal. Modeling of the planet juncture index and heliocentric longitude of the centroid of planetary systems and numerical simulation[J].Progress in Geophysics,2017,32(2): 506-515.]   
[26] USGS.The Sun and climate[EB/OL].htp:/greenwood.cr.usgs. gov/pub/fact-sheets/fs-0095-00/,2000-08/2020-06-02.   
[27]Adophi F, Muscheler R,Friedrich M,et al.Radiocarbon calibration uncertainties during the last deglaciation: Insights from new floating tree-ring chronologies[J]. Quaternary Science Reviews, 2017,170: 98-108.   
[28] Huang NE,Shen Z,Long S R,et al.The empirical mode decompositionand the Hilbertspectrum for nonlinear and non-stationary time series analysis[J].Proceedings of the Royal Society of London A,1998,454(1971): 903-995.   
[29]庄哲.基于振动数据驱动的受电弓裂纹故障诊断研究[D].成 都:西南交通大学,2018.[Zhuang Zhe.Research on vibration data-driven for pantograph crack fault diagnosis[D]. Chengdu: Southwest Jiaotong University,2018.]   
[30]Wu Z, Huang N E. Ensemble empirical mode decomposition: A noise-assisted data analysis method[J].Advances in Adaptive Data Analysis,2009,1(1): 1-41.   
[31] 唐洁.基于EEMD的陕西降水量与太阳黑子活动关系分析[J]. 干旱区资源与环境,2017,31(4):154-159.[Tang Jie.Relation between rainfall of Shaanxi Province and activities of sunspot based on ensemble empirical mode decomposition[J]. Journal of Arid Land Resources and Environment,2017,31(4): 154-159.]   
[32] 李玉霞,陈玲玲,江亭桂,等.基于EEMD的太阳活动对印度夏 季风的多尺度胁迫分析[J].地理科学,2018,38(4):628-635. [Li Yuxia, Chen Lingling, Jiang Tinggui, et al. Multi-scale modulation analysis of solar activity and Indian summer monsoon based on EEMD method[J]. Sientia Geographica Sinica,2018,38(4): 628-635.]   
[33]Bond G,Showers W,Cheseby M,et al.A pervasive milennialscale cycle in the North Atlantic Holocene and glacial climates[J]. Science,1997,278(5341): 1257-1266.   
[34]Mayewski PA,Rohling E E, Stager JC,et al. Holocene climate variability[J]. Quaternary Research,2004,62(3): 243-255.   
[35] 唐进年,丁峰,张进虎,等.库姆塔格沙漠东南缘BL剖面粒度记 录的全新世快速气候事件[J].干旱区地理,2017,40(6):1171- 1178.[Tang Jinnian, Ding Feng,Zhang Jinhu, et al.BL section re cording process of rapid climate change event of Holocene at southeastern edge of the Kumtagh Desert[J]. Arid Land Geography,2017,40(6): 1171-1178.]   
[36] 曹志宏,安成邦,尹丽颖,等.腾格里沙漠昂格尔图湖记录的 988 AD 以来的古气候变化[J].干旱区地理,2018,41(6):1251- 1259.[Cao Zhihong,An Chengbang,Yin Liying,et al. Climate change derived from Anggertu Lake in the Tengger Desert since 988 AD[J]. Arid Land Geography,2018,41(6): 1251-1259.]   
[37]杜丁丁,Mughal M S,Blaise D,等.青藏高原中部色林错湖泊沉 积物色度反映末次冰盛期以来区域古气候演化[J].干旱区地 理,2019,42(3): 551-558.[Du Dingding,Mughal M S, Blaise D, et al.Paleoclimatic changes reflected by difuse reflectance spec troscopy since Last Glacial Maximum from Selin Co Lake sediments,central Qinghai-Tibetan Plateau[J].Arid Land Geography, 2019, 42(3): 551-558.]   
[38]Ermakov VI, Okhlopkov V P, Stozhkov YI. The impact of cosmic dust on the Earth's climate[J]. Moscow University Physics Bulletin,2009,64(2): 214-217.   
[39] Ollila A.Cosmic theories and greenhouse gases as explanations of global warming[J]. Journal of Earth Sciences and Geotechnical Engineering,2015,5(4): 27-43.   
[40] 刘复刚,王建,商志远,等.太阳轨道运动长周期性韵律的成因 [J].地球物理学进展,2013,28(2): 570-578.[Liu Fugang,Wang Jian, Shang Zhiyuan,et al. Study on long-term cyclical rhythm of solar activity[J]. Progress in Geophysics,2013,28(2): 570-578.]

# Hallstatt cycle of solar inertial motion and solar activity based on ensemble empirical mode decomposition

WANG Linlin'，WANG Jian'²， SUN Wei³4， WANG Jie' (1.SchlofGeography,Nanjing NormalUniversity,NanjingO023,Jiangsu,China;2.SchoolofUrban&Resourcsand   
Environment,JangsucondoalUivesityNanjing2O,Jangsu,China;3.hoolfathematic,sicsandisi,   
Shanghai UniversityofEngineringScience,hanghai0l62O,China;4.ShoolofResouresandEnvironment,AnqingNoal University,Anqing 246133,Anhui, China)

Abstract: Solar activity, evidenced by $^ { 1 4 } \mathrm { C }$ proxies, shows a period of $\sim 2 3 0 0$ years (Hallstatt cycle). Its physical origin remains uncertain. Recent studies suggested that $\sim 2 3 0 0$ -year Hallstatt oscillations of solar activity may be caused bythe solar inertial motion (the Sun motion around the center of massof the solar system).In this study,a formula for calculating the distance between the solar centroid and the solar system'scentroid is deduced based on the kinematic equation of the planet juncture index.In the appropriate proxy of solar inertial motion, the time series of distance change is reconstructed using this formula.Ensemble empirical mode decomposition (EEMD) is a method with which any complicated signalcan be decomposed into several intrinsic mode functions (IMFs). This decomposition method is adaptive and highly eficient. It applies to nonlinear and non-stationary processes since the decomposition is based on the local characteristic time scale of the data.To compare the radiocarbon series of INTCAL13 data with the variations of the distance between the solar centroid and the solar system's centroid from 0 to $2 5 . 0 \mathrm { k a }$ BP, we employ the empirical mode decomposition method. The analysis results are as follows:(1) Various components have been identified bydecomposing the distance signal, including a significant component with a period of $\sim 2 3 0 0$ years.(2) Following the analysis of the time series of distance change, there is also a component with $\sim 2 3 0 0 \$ -year Hallstatt cycle in the data on the production rate of radiocarbon. The traditional method of $\Delta ^ { 1 4 } \mathrm { C }$ record preprocessing, applying a pre-selected detrending function, amounts to injecting external information into data.Diferent from the traditional method the true and more physical meaningful component with the Hallstatt cycle is decomposed by the adaptive EEMD method.(3) Next, the $\sim 2 3 0 0$ -year variations of the two series considered are compared. The last 13900 years data in INTCAL13 record derive mostly from tree-ring chronologies,while the older data is made using mostly marine records.Thus,cross-correlationanalysis is applied to the above two time-frames of thecomponents with the Halstatt cycle decomposed from the time series of the distance and $\Delta ^ { 1 4 } \mathrm { C }$ 、The cross-correlation coefficient is 0.52 from O to $1 3 . 9 \mathrm { { k a } }$ BP,and 0.44 from 13.9 to $2 5 . 0 \mathrm { { k a } }$ BP.The values confirm the assumption that the variations ofthe distance between the solar centroid and the solar system’s centroid and the production rate of radiocarbon are related.As discussed above,the study of the relationship between solar inertial motion and solar activity covers the Holocene and extends to $2 5 . 0 \mathrm { k a }$ BP. (4) It appears that solar inertial motion is the cause of the Hallstatt cycle found in solar activity proxy. The $^ { 1 4 } \mathrm { C }$ concentration of the atmosphere increases when the solar centroid moves away from the solar system's centroid, which corresponds to the period of weak solar activity.When the solar centroid is near the solar system's centroid, the $^ { 1 4 } \mathrm { C }$ concentration decreases which corresponds to the period of strong solar activity.

Key words: solar inertial motion； solar activity；Halstatt cycle；ensemble empirical mode decomposition (EEMD)