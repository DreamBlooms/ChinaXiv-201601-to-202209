# 透平叶栅非轴对称端壁的设计与优化

张健陈榴¹班宇¹戴韧¹王蛟2(1.上海理工大学能源与动力工程学院，上海200093;2．江苏科技大学,江苏 212003)

摘要采用 NURBS 曲面造型方法，在轴对称端壁上叠加径向高度变化量构造非轴对称端壁。采用最优拉丁超立方设计的方法，经过两轮实验设计，寻求性能较优的设计方案。结果分析表明：基于最优拉丁超立方的实验设计方法，定向搜寻透平叶栅的非轴对称端壁优化设计方案，是可行的。与圆柱端壁相比，优化后涡轮叶栅通道出口面积平均二次流动能减小 $5 . 4 8 \%$ ，总压损失系数减小了 $1 . 6 3 \%$ ，端壁换热状况局部有改善。非轴对称端壁通过改变端壁的静压分布削弱了涡轮叶栅通道中马蹄涡、通道涡的强度。非轴对称端壁使通道内靠近进口段和出口段端壁换热被削弱，尾迹区换热有所增强。

关键词非轴对称端壁；NURBS；实验设计；优化图分类号：TK47 文献标识码：A 文章编号:0253-231X(2017)08-1634-(

# Design and Optimization of Non-axisymmetric Endwall in Turbine Cascades

ZHANG Jian1 CHEN Liu1 BAN Yu1 DAI Ren1 WANG Jiao² (1.University of Shanghai for Science and Technology，Shanghai 2Ooo93,China; 2.Jiangsu University of Science and Technology，Jiangsu 2120o3,China)

AbstractNon-uniform Rational B-spline Surface (NURBS) is used to design non-axisymmetric endwall through adjusting the radial protrusion of axisymmetric endwall in turbine cascade.Design of experiment with optimal Latin Hypercube is applied to construct non-axisymmetric endwal scenarios for a high pressure turbine rotor. Results show that two-step direct search among the designing space constructed by the optimal Latin hypercube method is an efficient way to obtain optimal endwall contour. Compared with the axisymmetric endwall, non axisymetric endwal reduces 5.48% of the area averaged secondary kinetic energy and 1.63% of the relative total pressure loss at the passage exit. The heat transfer coefficients on endwall are also reduced in some areas. The non axisymetric emdwall changes the pressure distribution on the endwall and weaken the strength of the horseshoe vortex and the passge vortex in turbine cascade passage. Heat transfer decreases in the forward part of passage while increase in the aft part of passage. Heat transfer near the trailing edge is increased.

Key wordsNon-axisymmetric endwall; NURBS; DOE; Optimization

# 0引言

在小展弦比、高载荷的透平级内，由于端区流动产生的二次流损失约占总熵增的三分之一[1]。充分认识二次流损失机理、有效控制端区二次流是提高涡轮效率的重要技术途径之一。非轴对称端壁通过调整端壁的三维曲面形状，能够改变端壁流线曲率，减小通道中的横向压力梯度，有效地减小二次流损失。

Harvey[2] 和 Hartland[3] 通过计算和实验的方法表明非轴对称端壁能够改善叶栅出口气流的欠偏转和过偏转，减小通道内横向压差，二次流损失减小了 $3 0 \%$ 。在吸力面靠近尾缘附近产生一支强烈的角涡。Brennan[4]和 Rose[5]将Harvey[2] 构造非轴对称端壁的方法应用于TRENT500高压级透平静叶，使级效率提高 $0 . 5 9 \%$ 。Germain[6] 和 Scheupbach[7]将非轴对称端壁应用于1.5级透平叶栅的静叶和动叶，整级效率提高 $1 . 0 \% \pm 0 . 4 \%$ 。Praisner[8]比较了载荷系数不同的三种低压透平叶栅的非轴对称端壁气动特性，结果表明叶栅出口的总压损失与湍动能均有所减小，并且前加载叶片的效果最好，总压损失减小了 $1 2 \%$ 。

端壁热负荷的分布与非轴对称端壁对二次流的作用关系密切。Saha[9]通过数值计算对4类9 种不同型线设计的非轴对称端壁上的换热进行了评估，发现与平端壁相比，最优的非轴对称端壁设计可以使端壁上的平均换热水平降低 $8 \%$ 。Mahmood[10]实验结果表明非轴对称端壁上的Nu 数要比平端壁上的低，尤其在上游位置。Lynch[11]实验测量了Praisner[8]设计的非轴对称端壁上的换热系数，结果表明在端壁压力面高换热角区，非轴对称端壁的换热水平要比平端壁的低近 $2 0 \%$ ，雷诺数对端壁的换热系数几乎没有影响。

非轴对称端壁通常采用正交分解和轴向或者周向成型函数相结合的造型方法构造。傅里叶级数法[12]具有较大的造型空间，然而非轴对称端壁面会延伸到通道外部，并且输入参数与端壁形状之间的关系太过复杂。三角函数法[13]和衰减函数法[14]能够直观的构造端壁的凹凸形状，但是造型空间不足够大。利用NURBS曲面造型方法来构造非轴对称端壁，造型空间足够大，易于局部调整，并且能直观地将输入参数与端壁形状联系起来。

实验设计方法能够有效地处理非轴对称端壁设计时面临的多个设计因子及不同水平的问题。通过科学的样本空间的设计，构建不同设计变量与目标之间的函数关系，寻求目标约束下的有效设计。目前，实验设计方法作为一种高效经济的方法应用于叶轮机械的设计研发中[15]。

本文基于NURBS造型方法，根据圆柱端壁的气动特性，利用实验设计的方法寻求有效的非轴对称端壁。涡轮端区的三维流动复杂，本文主要研究非轴对称端壁对端区流动的作用机理及其对端壁传热特性的影响。

# 1叶栅模型与数值方法

本文以某高压级第一级动叶为研究对象。叶片轴向弦长为 $1 0 9 ~ \mathrm { m m }$ ，展弦比为1.606。上端壁为圆柱端壁，下端壁为非轴对称端壁。入口给定总温、总压、湍流度，出口给定平均静压，叶片表面和下端壁的热流密度设定为 $1 0 0 0 \ \mathrm { W / m ^ { 2 } }$ ，上端壁设置为绝热壁面。叶片旋转速度为 $1 2 0 0 \mathrm { r / m i n }$ 。为了适应叶片几何进气角沿径向的分布，在流道进口气流方向按照轴向和周向速度函数给定。

网格划分选用NUMECAAutogrid5提供的自动优化拓扑结构。计算域进口段和出口段均采用H型网格，长度为0.5倍轴向弦长。动叶拓扑结构采用默认的O4H结构。考虑到周向的周期性，计算对单个流道进行，周期性交界面采用相匹配的边界网格连接。网格设置如图1所示，在叶片和端壁表面生成边界层网格，计算后得到整个动叶流道内壁面 $Y ^ { + }$ 控制在1以内。

![](images/df42bce5bad2dbf86d9cb00efea20cec8f8594f0275d504c57d61dc231489864.jpg)  
图1网格设置Fig.1 Mesh Details

计算选择 SST 湍流模型，守恒方程中的平流项和湍流输运方程均采用CFX中的二阶差分格式。本文在原始叶片上采用如表1参数的4套网格计算，进行网格相关性验证。通过对比叶栅下游 $X / C _ { \mathrm { a x } } { = } 1 . 1$ 处周向平均总压损失系数，如图2所示，发现各方案计算结果的相对偏差随网格数的增加而逐渐减小。本文采用Mesh3网格方案。

表1网格参数Table 1 Mesh Setting  

<html><body><table><tr><td></td><td>流向节点数</td><td>周向节点数</td><td>径向节点数</td></tr><tr><td>Mesh1</td><td>103</td><td>59</td><td>97</td></tr><tr><td>Mesh2</td><td>107</td><td>67</td><td>113</td></tr><tr><td>Mesh3</td><td>135</td><td>75</td><td>125</td></tr><tr><td>Mesh4</td><td>155</td><td>83</td><td>133</td></tr></table></body></html>

![](images/51a2c81f90ccf8e1d45cf249ad03d1b2f7d224fb135490e84a1319fc9a101d44.jpg)  
图2叶栅出口相对总压损失沿叶高的分布Fig.2 Relative total pressure coefficients spanwisedistribution at passage exit

# 2非轴对称端壁的设计与优化

# 2.1非轴对称端壁参数化

本文利用NURBS 曲面造型方法将端壁形状表达为基于若干设计变量的参数方程的形式[16]。 $u$ 方向 $p$ 次、 $\mathbf { \sigma } _ { v }$ 方向 $q$ 次的 NURBS 曲面是具有以下形式的双变量分段有理矢值函数：

$$
S ( u , v ) = \frac { \displaystyle \sum _ { i = 0 } ^ { n } \sum _ { j = 0 } ^ { m } N _ { i , p } ( u ) N _ { j , q } ( v ) w _ { i , j } P _ { i , j } } { \displaystyle \sum _ { i = 0 } ^ { n } \sum _ { j = 0 } ^ { m } N _ { i , p } ( u ) N _ { j , q } ( v ) w _ { i , j } } \quad 0 \leqslant u , v \leqslant 1
$$

式中， $( m + 1 ) \times ( n + 1 )$ 个控制点 $P _ { i , j }$ 形成了$u , v$ 方向的控制网格， $\{ W _ { i , j } \}$ 是权因子， $\{ N _ { i , p } ( w ) \}$ 和 $\{ N _ { i , p } ( v ) \}$ 分别是定义在节点矢量 $U$ 和 $V$ 上的非有理B样条基函数。

$$
U = \left\{ \underbrace { 0 , \cdots \cdot 0 } _ { p + 1 } , u _ { p + 1 } , \cdot \cdot \cdot u _ { r - p - 1 } , \underbrace { 1 , \cdot \cdot \cdot , 1 } _ { p + 1 } \right\} ,
$$

$$
V = \left\{ \underbrace { 0 , \cdots \cdot 0 } _ { q + 1 } , \ v _ { q + 1 } , \cdots v _ { s - q - 1 } , \underbrace { 1 , \cdots \cdot , 1 } _ { q + 1 } \right\} \circ \cdotp
$$

其中，通过调整 $W _ { i , j }$ 和 $P _ { i , j }$ ，实现对 NURBS曲面的局部或者整体的修改和调整。

图3是端壁控制点分布。在叶片通道区域内，以两相邻叶片中分线为周期性边界。通道上游边界和下游边界分别距离前缘点和尾缘点0.5倍轴向弦长。一个周期内的端壁曲面通过 $1 1 \times 7$ 个控制点构造,其中可动控制点 $5 \times 5$ 个 (如图3实心点所示)。非轴对称端壁曲面 $\boldsymbol { S }$ 是原始轴对称端壁曲面 $S _ { 0 }$ 和端壁曲面径向变化量 $\Delta Z ( u , v )$ 叠加作用的结果。该NURBS曲面的参数化空间为 $( \Delta Z ( u , v ) )$ 。其中， $u , v$ 表示无量纲的轴向和周向位置。将各控制点的 $\Delta Z$ 取不同的值，即可实现非轴对称端壁曲面造型。

![](images/32dcf044cb6f6d58a2807515726b1b3a817e58b71f0a02ddacde12d09d251eb6.jpg)  
图3控制点分布Fig.3 Control points on endwall

# 2.2非轴对称端壁的设计与优化

非轴对称端壁设计的基本准则是在压力面侧凸起加速流体流动减小当地静压，吸力面侧凹下减缓流体流动增大当地静压，从而减小端部横向压差。Harvey[2]优化的非轴对称端壁在吸力面尾缘存在小幅度的凸起。根据圆柱端壁压力分布(如图4所示）与设计经验，本文提出以下设计准则：1)端壁压力面侧高压区凸起，最大幅值为 $1 0 \%$ 叶高；相应的吸力面侧端壁凹下，最大幅值为 $1 0 \%$ 叶高。2）压力面侧靠近前缘端壁允许最大幅值为 $6 \%$ 叶高的凸起。3)吸力面侧靠近尾缘位置允许 $\pm 3 \%$ 叶高的变化。

![](images/cd28a310625fce7420af3ff8bd5397b625e40c0066d1bc082c959bf7d9ab6b50.jpg)  
图4圆柱端壁静压系数  
Fig.4 Static pressure coefficients on cylinder endwall

最优拉丁超立方设计(OptimalLatinHypercubeDesign,OptLHD）具有非常好的空间填充性和均衡性，使因子和响应的拟合更加精确真实。本实验以25 个可动控制点的径向坐标变化量 $\Delta Z$ 为因子，根据本文提出的非轴对称端壁的设计准则设定因素的水平约束，确定实验数目为40。经过NURBS参数化造型、TurboGrid5生成网格、CFX计算得到40组结果。目标函数由CFD数值模拟的后处理阶段提供，通常为总压损失系数、二次流动能等。二次流速度是以不同径向位置不受二次流影响的截面周向平均速度来定义的。

$$
\beta = \beta \left( r \right) = \tan ^ { - 1 } \left( \frac { V \left( r \right) } { U \left( r \right) } \right)
$$

$$
V _ { s } = U \cos { ( \beta ) } + V \sin { ( \beta ) }
$$

$$
V _ { n } = - U \sin { ( \beta ) } + V \cos { ( \beta ) }
$$

$$
V _ { z } = W
$$

其中， $U , \ V$ 、W分别是笛卡尔坐标系下速度的 $x$ 轴， $y$ 轴, $z$ 轴分量。二次流速度由 $V _ { n }$ 和 $V _ { z }$ 决定，所以，二次流动能 $S K E = \frac { 1 } { 2 } \left( { V _ { n } } ^ { 2 } + { V _ { z } } ^ { 2 } \right) ,$ 。

如图5所示，是叶栅出口面积平均二次流动能和相对总压损失系数的所有结果。相对于圆柱端壁，NAEW15的叶栅出口二次流动能减小了 $4 . 5 5 \%$ 总压损失系数减小了 $1 . 5 1 \%$ ，效果最佳。

![](images/03890f727b0305fddbfe071300df15eaa1b34a6c95b24b563aca4a755814a27a.jpg)  
图5最优拉丁方设计计算结果Fig.5 Results of first experiment

率大于 $4 \%$ 的11个因素进行第二轮实验设计。以第一轮实验设计中的最佳设计NAEW15为基准，基于最优拉丁方设计方法，重新细化11个因子的水平。如表3所示，是第二轮实验设计的所有因子及水平范围，实验数为20。同样地，经过非轴对称端壁参数化造型、网格生成、数值计算得到20组计算结果。从叶栅出口二次流动能和相对总压损失系数来看，如图7，可以发现，除了NAEW42和NAEW54,第二轮实验设计的结果均优于圆柱端壁。综合来看，相对圆柱端壁，NAEW49的叶栅出口平均二次流动能减小了 $5 . 4 8 \%$ ，总压损失系数减小了 $1 . 6 3 \%$ ，也优于第一轮实验设计的较优的NAEW15，所以，经过两轮设计，选取NAEW49为最佳设计。

表3第二轮实验设计变量及水平范围  
Table 3 Design factors and level range in the second experiment   

<html><body><table><tr><td></td><td>P11</td><td>P13</td><td>P21</td><td>P34</td><td>P35</td><td>P41</td></tr><tr><td>下限/mm</td><td>3.897</td><td>0</td><td>0</td><td>-10</td><td>-2.667</td><td>-7.385</td></tr><tr><td>上限/mm</td><td>7.897</td><td>5.308</td><td>3.282</td><td>-7.487</td><td>-0.667</td><td>-3.385</td></tr><tr><td></td><td>P43</td><td>P45</td><td>P51</td><td>P54</td><td>P55</td><td></td></tr><tr><td>下限/mm</td><td>-8.385</td><td>-3.308</td><td>-3.256</td><td>0.436</td><td>-4.436</td><td></td></tr><tr><td>上限/mm</td><td>-2.385</td><td>-1.308</td><td>0</td><td>4.436</td><td>-0.436</td><td></td></tr></table></body></html>

![](images/54832d9e6a3de4d38ab79c9879a9baeb9f8cc163fec1c18e99abb38a1c29823b.jpg)  
图7第二轮实验设计计算结果Fig.7 Results of the second experiment  
图6所有因子对 SKE 的贡献率Fig.6 Contribution Rate of factors on SKE

12 h Control points

# 3优化结果验证与分析

以叶栅出口面积平均二次流动能最小为目标，以25个控制点的径向坐标变化量为因子进行了敏度分析。图6反映了实验设计的结果中所有因子对目标函数二次流动能的贡献程度百分比。选取贡献

下文以两次优化得到的非轴对称端壁结果进行详细分析。其具体形状如图8所示，压力面侧端壁凸起，幅值范围呈窄长状。吸力面侧端壁凹下，最大幅值位于吸力面肩区，凹下的程度逐渐减缓与压力面侧相接，并且吸力面侧端壁的幅值约为压力面侧的2倍。压力面侧靠近尾缘有 $2 ~ \mathrm { m m }$ 左右的凸起。

![](images/76a261aec4d042925a6c6e436a48892be8df3f9177d63abb93b622da7520346a.jpg)  
图8非轴对称端壁几何参数

![](images/b10751983005d514b594185c58ee67fe586d548e91183c03cf0fde10cbab3751.jpg)  
Fig.8 Geometric parameter and shape for contoured endwall

径向的分布。由于通道涡的影响，在叶栅出口Nor-malSpan $_ { - 0 . 2 }$ 附近出现高损失段，其峰值的大小反映了通道涡的强度。非轴对称端壁的应用，使高损失段的峰值由0.47减小到0.42，减小了 $1 1 . 9 \%$ 。同时，Normal Span 在 $0 . 0 5 \mathrm { \sim } 0 . 5$ 区段，周向平均相对总压损失均小于圆柱端壁。但是，靠近端壁附近，相对圆柱端壁，损失略有增加。非轴对称端壁加剧了近端壁流体的掺混、扰动，增加了损失。

图10是 $5 \%$ 叶高处叶片表面静压系数。可以看到,在 $X / C _ { \mathrm { a x } } { = } 0 . 3 { \sim } 0 . 7$ 范围内，非轴对称端壁压力面上静压系数显著减小，吸力面基本不变，通道内横向压差减小，有助于抑制二次流的发展。图11是 $2 0 \%$ 叶高处叶片表面静压系数分布。在 $X / C _ { \mathrm { a x } } { = } 0 . 3 { \sim } 0 . 8$ 范围内，压力面上静压系数小于圆柱端壁上的，横向压差减小。

![](images/d739c5baa05dc376a459c391290be7be3a40a38df6205b99743dd18abcab0c02.jpg)  
图 $1 0 \ 5 \%$ 叶高叶片表面静压系数

![](images/e46264a621bca9165365e6bd8148ac01002423d586e710fa8861a143aae10aeb.jpg)  
图9周向平均相对总压损失系数沿径向分布Fig.9 Radial distribution of pitchwise averaged total pressurecoefficients  
Fig.10 Blade static pressure at $5 \%$ span   
图11 $2 0 \%$ 叶高叶片表面静压系数  
图9是叶栅出口周向平均相对总压损失系数沿  
Fig.11 Blade static pressure at $2 0 \%$ span

图12叶栅出口二次流动能的云图。可以看到，由于通道涡的作用，在上下端壁产生了高二次流动能区。与圆柱端壁相比，上端壁附近几乎没有差别，但是在下端壁侧二次流动能的峰值减小了，说明通道涡的核心区的强度被削弱。同时，周期性流道右侧二次流动能也有所减小。但是，在贴近端壁附近,二次流动能有所增加。说明非轴对称端壁加剧了该处的流动阻力，扰动增强。

![](images/c18724bb16ef7568cfcf3eb11a665bfccb37ac834576a698f59573548ea0a2e0.jpg)  
图12叶栅出口二次流动能 Fig.12 SKE contour at passage exit

![](images/34c40861e4e0113d14e02c556a4f7e5f6d607ca7a23a44775b8f31d1aa966c06.jpg)  
图13端壁 $\mathbf { \nabla } _ { S t }$ 数分布  
Fig.13 Stanton number contour on endwall

端壁的换热特性与其流动特征的关系密切。图13是端壁 $\mathit { S t }$ 数的分布。由于前缘马蹄涡的作用，圆柱端壁高换热区从前缘压力面侧延伸到通道内，非轴对称端壁减弱了该处的换热，说明非轴对称端削弱了前缘马蹄涡的强度。非轴对称端壁在压力面侧前部换热有所增强，流道内靠近进口区端壁换热有所减弱，流道内靠近出口端壁换热也明显减弱。非轴对称端壁使尾迹区换热有所增强，靠近压力面侧端壁 $\mathit { S t }$ 数梯度增大。

# 4结论

本文采用NURBS构造非轴对称端壁的造型方法，基于最优拉丁超立方的设计方法，以二次流动能为目标，分析所有因子对响应的贡献程度，经过两轮实验设计，寻求性能较优的设计方案。并以优化后的非轴对称端壁为研究对象，分析其对动叶流动与传热的影响。优化后涡轮叶栅通道出口面积平均二次流动能减小 $5 . 4 8 \%$ ，总压损失系数减小了 $1 . 6 3 \%$ ，由于二次流导致的总压损失系数峰值减小了 $1 1 . 9 \%$ 。

1）采用基于拉丁超立方的实验设计方法对透平叶栅的非轴对称端壁优化设计时方便可行的，其计算效率较高。对于后续可能采用数学规划优化方法进行优化设计而言，优化的结果对于给定合理的优化初始点和合适的约束函数具有指导意义。

2)通过改变端壁的静压分布减小通道内横向压差，削弱通道涡的强度。但是靠近端壁附近流动状况并没有得到改善。

3)有效的非轴对称端壁会局部改善端壁的换热状况。在压力面侧前部换热有所增强，流道内靠近进口区端壁换热有所减弱，流道内靠近出口端壁换热也明显减弱。同时，非轴对称端壁使尾迹区换热有所增强。

# 参考文献

[1]Denton JD.The 1993 IGTI Scholar Lecture:Loss Mechanisms in Turbomachines [J].Journal of Turbomachinery, 1993,115(4):621-656   
[2] Harvey N W,Rose M G,Taylor M D,et al. Nonaxisymmetric Turbine End Wall Design: Part I—ThreeDimensional Linear Design System [J].Journal of Turbomachinery,2000,122(2):278-285   
[3]Hartland J C,Gregory-Smith D G，Harvey N W，et al.Nonaxisymmetric Turbine end wall Design: Part IIExperimental validation [J]. Journal of turbomachinery, 2000,122(2):286-293   
[4] Brennan G,Harvey N W,Rose MG,et al. Improving the Efficiency of the Trent 5OO-hp Turbine Using Nonaxisymmetric end Walls-Part i: Turbine Design [J].Journal of Turbomachinery, 2003,125(3):497-504   
[5] Rose M G,Harvey N W,Seaman P,et al. Improving the Efficiency of the Trent 5OO HP Turbine Using NonAxisymmetric End Walls:Part II—Experimental Validation[C]//ASME Turbo Expo 2001:Power forLand,Sea, and Air.American Society ofMechanical Engineers,2001:

#

V001T03A081   
[6] Germain T,Nagel M,Raab I,et al. Improving Efficiency of a High Work Turbine Using Nonaxisymmetric Endwalls—Part I:Endwall Design and Performance [J]. Journal of Turbomachinery, 2010,132(2):021007   
[7] Schuepbach P,Abhari R S,Rose M G,et al.Improving Efficiency ofa High Work Turbine Using Nonaxisymmetric Endwalls—Part II: Time-Resolved Flow Physics [J] Journal of Turbomachinery, 2010,132(2):021008   
[8]Praisner TJ,Allen-BradleyE,GroverEA,et al.Application ofNon-Axisymmetric Endwall Contouring to Conventional and High-Lift Turbine Airfoils [C]//ASME Turbo Expo 20O7:Power forLand,Sea,andAir.American Society of Mechanical Engineers,2007:653-661   
[9] Saha A K,Acharya S.Computations of Turbulent Flow and Heat Transfer Through a Three-Dimensional Nonaxisymmetric Blade Passage [J].Journal of Turbomachinery, 2008,130(3):031008   
10]Mahmood GI,Acharya S.Measured Endwall Flow and Passage Heat Transfer ina Linear Blade Passagewith Endwall and Leading edge Modifications [C]//ASME Turbo Expo 2OO7:Power for Land,Sea,and Air.American Society ofMechanicalEngineers,2007:917-930   
11] Lynch S P,Sundaram N, Thole K A,et al. Heat Transfer for a Turbine Blade with Nonaxisymmetric Endwall Contouring [J].Journal of Turbomachinery, 2011,133(1): 011019   
[12]李国君,任光辉,马晓永,等.叶栅非轴对称端壁成型技术的 初步研究[J].工程热物理学报，2006,27(S1)：97-100 LIGuojun,REN Guanghui,MA Xiaoyong,et al. The Preliminary Study of Nonaxisymmetric Endwall Design in a Cascade[J].Journal of Engineering Thermophysics,2006, 27(S1): 97-100   
[13]李国君，马晓永，李军．非轴对称端壁成型及其对叶栅损 失影响的数值研究[J]．西安交通大学学报，2005，39(11): 1169-1172 LiGuojun,Ma Xiaoyong,Li jun.Nonaxisymmetric Turbine Endwall Profling and Numerical Investigation of Its Effect on the Turbine Cascade Loss [J]. Journal of Xi'An Jiao Tong University,2005,39(11):1169-1172   
[14]Nagel MG,FottnerL,BaierR.Optimization of Three Dimensional Designed Turbine Blades and Side Walls [C]// ISABE.2001   
[15]杨剑秋，王延荣.基于正交试验设计的空心叶片结构优化设 计[J].航空动力学报，2011,26(2):376-384 Yang Jianqiu，Wang Yanrong.Structural Optimization of Hollow Fan Blade Based on Orthogonal Experimental Design [J]. Journal of Aerospace Power,2011,26(2):376- 384   
[16]皮尔,特莱尔,赵罡,等.非均匀有理B 样条[M].北京：清 华大学出版社，2010 Les Piegl,Wayne Tiller,Zhao Gang,et al．The Nurbs Book[M].Beijing:Tsinghua University Press,2010