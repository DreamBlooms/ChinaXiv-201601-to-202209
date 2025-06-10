# 径向轮缘密封预旋盘腔流动换热特性数值研究

程舒娴晏鑫　李志刚宋立明　李军(西安交通大学叶轮机械研究所，西安710049)

摘要本文通过 SST 湍流模型求解 RANS 方程组，研究了带径向轮缘密封的预旋盘腔流动换热特性，并采用附加变量法研究径向密封的封严特性。比较了不同冷气量，不同进气预旋比下的盘腔内流动系数、转盘表面努塞尔数和封严效率。结果表明：在中分面处，预旋比随进气预旋比的增大而增大，静压系数沿径向线性增大。主流入侵使转盘壁面绝热温度升高，根据流动状态计算得出的 $N u$ 较实际略大。进气预旋提高封严效率。

关键词涡轮；轮缘密封；预旋进气；数值模拟中图分类号：TK474.7 文献标识码：A 文章编号:0253-231X(2017)08-1647-08

# Numerical Investigations of the Flow and Heat Transfer in a Pre-swirl Rotor-Stator Cavity With Rim Radial Seal

CHENG Shu-Xian YAN XinLI Zhi-GangSONG Li-Ming LI Jun (Institute of Turbomachinery,Xi'an Jiaotong University，Xi'an 71oo49,China)

AbstractThe flow and heat transfer in a pre-swirl rotor-stator cavity with rim radial seal are numerically investigated by RANS equations and SST turbulence model, and the additional pasive tracer method is used to simulate the mainstream ingestion phenomenon. The variations of fow coefficient in cavity, the Nusselt number on rotor surface and sealing efficiency with different sealing fow rate or pre-swirl ratio are investigated. The numerical results show that in the split, pre-swirl ratio increases with the increase of the ratio of inlet pre-swirl. Static pressure coefficient along the radial direction increases linearly. On account of the mainstream ingestion which makes adiabatic temperature on rotor rise,The nusselt number calculated by the flow state is slightly larger than the actual. Inlet pre-swirl is beneficial to sealing effciency.

Key wordsturbine; rim seal; pre-swirl system; numerical simulation

# 0引言

涡轮盘腔冷却是燃气透平冷却系统的重要组成部分。在实际流动中，主流的高温燃气经由轮缘处的密封结构入侵轮盘腔室，同时主流燃气对轮盘边缘的加热作用会使得轮盘温度升高，热应力增大，最终导致轮盘变形，存在安全隐患。在盘腔冷却中，最常用的方法是向盘腔中通入从压气机中引出的冷却空气。冷却空气进入盘腔对转盘壁面进行冷却，同时作为封严气体对轮盘腔室密封。通过减少从压气机引入的冷气量，可以提高透平气动效率，因此对盘腔内流动与换热特性的研究具有重要意义。

国内外学者已经对盘腔的流动换热和轮缘密封的封严效率两个方面进行了多次实验及数值研究。在轮缘密封的封严效率方面，Patinios 等[1］采用低雷诺数相似的实验装置对1.5级双重密封的盘腔系统进行了封严效率的实验研究，发现静边界层内气流轴向穿过核心区到达动边界层，同时核心区预旋比决定盘腔径向压力分布，因此对核心区的流动状态研究十分重要。Sangan 等[2-4]进行了单级透平实验，对轮缘密封外部诱导入侵 (EI)、旋转诱导入侵 (RI)和双重密封的封严特性进行了实验和理论分析，提出了经实验验证的孔板模型。Paul等[5]为得到高质量的非定常轮缘密封模型，实验测量盘腔内外压差随密封内流速的定常变化，并对转动时盘腔内压力分布频率，进行频谱分析。Svilen 等[通过实验测量，比较简单密封和双重密封对封严气量、叶片压力场、大尺度下的不均匀入侵、非设计工况下的主流流动变化时的敏感度。

在流动与换热方面,Liu等[7]对预旋喷嘴位于盘腔不同径向位置的实际绝热系统进行研究，其预旋温降与功耗呈线性负相关。Zhang等[8,9]通过CFD数值计算，比较了不同长径比接收孔时排气系数、绝热效率等流动和换热特性的变化，研究了实际结构的盘腔系统不同预旋角度下盘腔的整体流动情况，确定预旋角度为 $2 0 ^ { \mathrm { o } }$ 时性能最为优越。Tao 等[10]运用PIV实验方法和CFD数值方法，研究了自由转静盘腔系统的风阻温升，研究得出转盘温升受盘腔间隙影响较小，仅为在一定湍流系数下，旋转雷诺数和通流雷诺数的函数。Luo 等[11]采用 TLC 技术对实际结构的低位进气预旋盘腔进行实验，研究了不同转速与冷气量对盘腔换热特性的影响，给出了实验得到的Nu转盘分布云图。Owen 等[12]改进了先前的孔板模型，使得压力测试可用于计算发动机内的封严效率，并使用CFD的方法与实验数据验证。Lalwani等[13]进行了定常计算，比较了不同冷气量下轮缘密封盘腔内的流动及封严特性。

由于现今预旋盘腔的研究中通常将轮缘密封结构简化，分开研究预旋盘腔与轮缘密封。本文将进气预旋与轮缘密封结合在一起，研究进气预旋与轮缘密封的相互影响。本文以文献[14]中模型为基础，采用轴向进气，对带径向轮缘密封的预旋盘腔系统进行CFD数值研究，重点研究在旋转雷诺数 $0 . 8 \times 1 0 ^ { 6 }$ 下，不同无量纲冷却气体流量和进气预旋比的范围内，盘腔内的流动换热特性，深入分析进气预旋对封严效率的影响和考虑轮缘密封后盘腔内部流动传热特性的变化。

主流通道与轮缘密封间隙处网格结点完全匹配，在间隙处布置了37个网格节点；网格最小正交角度为$3 2 ^ { \mathrm { o } }$ ，质量良好。节点总数为162万，满足网格无关性要求。主流计算域壁面第一层厚度设为 $0 . 0 1 \ \mathrm { m m }$ 5盘腔计算域壁面第一层厚度为 $0 . 0 0 1 \mathrm { m m }$ ，以满足采用软件ANSYS-CFX数值求解三维RANS方程进行数值计算研究时，SST 湍流模型对壁面网格 $y ^ { + }$ 的要求。

![](images/c0751191efb76e4a08ad7a19cd5c3badc5ea9ea06f56477afdc28787720bb122.jpg)  
图1主流盘腔结构与计算域模型示意图 Fig.1 The mainstream and cavity configuration and computational domain

# 1计算模型和数值方法

图1(a)给出了计算模型静止域、旋转域、动静交界面及盘腔中分面的位置示意。根据文献[15]中的研究，将动静交界面设定在盘腔左侧，静叶流道计算域为静止域，动静交界面右侧的动叶流道和盘腔计算域为旋转域。盘腔左侧壁面为静止壁面，右侧壁面随旋转域旋转。同时图1(b)给出了计算模型的结构示意图，其主要参数如表1所示。冷却空气从盘腔左下角的进气口通入盘腔，并带有一定预旋度,对转盘壁面进行冷却，最后经轮缘处的径向密封进入主流，起到封严作用。同时主流燃气经轮缘间隙入侵盘腔。盘腔内的流动换热同时受冷却气体和入侵燃气的影响。

采用商用软件进行模型构建网格划分和数值计算。图2为运用软件NUMECA生成的多块结构化计算网格，主流通道采用 H-O-H拓扑结构化网格。主流通道中静叶周向节点为49个，轴向节点为 49 个;动叶周向节点为67个，轴向节点为33个；主流沿叶高方向布置了37个节点；为保证求解精度，生成的

表1径向轮缘密封预旋盘腔的主要结构参数(mm)Table 1 Dimensions of the pre-swirl rotor-statorcavity with rim radial seal(mm)  

<html><body><table><tr><td>结构参数</td><td>数值</td></tr><tr><td>内半径α</td><td>120</td></tr><tr><td>外半径b</td><td>190</td></tr><tr><td>间距c</td><td>5</td></tr><tr><td>动静叶间距d</td><td>12</td></tr><tr><td>冷气进气位置rp</td><td>121</td></tr><tr><td>主流道径向高度h</td><td>10</td></tr><tr><td>盘腔间距s</td><td>20</td></tr><tr><td>冷却气体进口宽度 sin</td><td>2</td></tr><tr><td>盘腔轴向间隙 sax</td><td>5.3</td></tr><tr><td>轮缘密封轴向间隙 sc,ax</td><td>2</td></tr><tr><td>轮缘密封径向间隙 sc,rad</td><td>2.4</td></tr></table></body></html>

流体介质采用理想气体，转速 $ { 3 0 0 0 }  { \mathrm { \ r / m i n } }$ ；主流进气给定进气量 $0 . 5 1 ~ \mathrm { k g / s }$ 和总温 $3 2 0 ~ \mathrm { K }$ ；冷气进口给定进气速度矢量和静止参考系下总温 $3 0 0 ~ \mathrm { K }$ ；主流出口以大气压强为静止参考系平均静压；固壁面均设为无滑移壁面；盘腔静止壁面绝热；转动壁面采用给定温度 $2 9 3 \mathrm { ~ K ~ }$ 与绝热壁面两种边界条件，以便 $N u$ 的分析研究；计算中动静交界面以冻结转子法（FrozenRotor）连接；两侧轮盘周期面设为旋转周期关联面。当连续方程、能量方程、湍流方程和动量方程的均方根残差均小于 $1 0 ^ { - 6 }$ ，且观测点附加变量值保持不变时，认为计算收敛。

![](images/c45270e86cd25a9f23ce79228b69f6513fe71edf644d7fccb9684f2f350685de.jpg)  
图2径向轮缘密封盘腔模型的计算网格 Fig.2 Computational mesh of the pre-swirl rotor-stator cavity with rim radial seal

实验中测量盘腔轮缘密封的封严效率采用浓度法，即在主流中加入一定浓度的示踪气体，通过盘腔内固定测点示踪气体浓度表征轮缘密封的封严效率。封严效率 $\varepsilon _ { \mathrm { c } }$ 定义为：

$$
\varepsilon _ { \mathrm { c } } = ( c _ { \mathrm { s } } - c _ { \mathrm { a } } ) / ( c _ { 0 } - c _ { \mathrm { a } } )
$$

式中， $c _ { \mathrm { a } }$ 为主流进气时示踪气体的浓度； $c _ { \mathrm { s } }$ 为参考点的示踪气体浓度； $c _ { 0 }$ 为冷气流进口处示踪气体的浓度。

本文采用添加附加变量的方法模拟示踪气体在主流通道和盘腔内部的输运扩散，冷气进口示踪变量 $\mathrm { C O _ { 2 } }$ 设为1，主流进口设为0，并设置动能扩散系数 $D _ { \varphi }$ 辅助计算( $3 0 0 \mathrm { ~ K ~ }$ 标准大气压下, $\mathrm { C O _ { 2 } }$ 在空气中 $D _ { \varphi } = 1 . 6 \times 1 0 ^ { - 5 } ~ \mathrm { m ^ { 2 } / s ) }$ 。由于冷气进口示踪变量$\mathrm { C O _ { 2 } }$ 为1，主流进口为0，则 $c _ { 0 } = 1$ ， $c _ { \mathrm { a } } = 0$ ，封严效率 $\varepsilon _ { \mathrm { c } }$ 等于附加变量 $C O _ { 2 }$ 的值。

# 2结果与讨论

# 2.1盘腔流动特性

盘腔内预旋比分布直接反映进气预旋对流动的影响。定义进气预旋比 ${ \beta } _ { \mathrm { p } }$

$$
\beta _ { \mathrm { p } } = V _ { \varphi , \mathrm { p } } / r _ { \mathrm { p } } \varOmega
$$

式中， $V _ { \varphi , \mathrm { p } }$ 为进气位置中分面处气流切向速度; $\varOmega$ 为转盘转速。

定义湍流系数 $\lambda _ { \mathrm { T } }$

$$
\lambda _ { \mathrm { T } } = C _ { \mathrm { w } } R e _ { \varphi } ^ { - 0 . 8 }
$$

图3给出了不同冷却气体进气量，不同进气预旋比时盘腔中分面 $z / s { = } 0 . 5$ 处预旋比沿径向的分布。比较图 $3 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ ，进气预旋比越大盘腔内预旋比越大；同时，随着冷气进气量逐渐增大，相应的进气预旋比变化对盘腔内流动影响加大。

当 $C _ { \mathrm { w } } = 1 5 0 0$ 时， $\lambda _ { \mathrm { T } } = 0 . 0 2 8$ ，进入盘腔的冷气流受转静盘壁面边界层影响极大，流动处于黏性主导；随着径向位置的增大，进气流与盘腔原有气流逐渐混合，不同 ${ \beta } _ { \mathrm { p } }$ 下的 $\beta$ 分布受盘腔内气流影响相应增大减小，直至 $r / b { = } 0 . 9$ 时趋于一致。当 $C _ { \mathrm { w } } = 3 5 0 0$ 时， $\lambda _ { \mathrm { T } } ~ = ~ 0 . 0 6 9$ ，流动逐步从黏性主导向惯性主导过度， $\beta _ { \mathrm { p } }$ 对盘腔内预旋比分布影响增大，代表不同$\beta _ { \mathrm { p } }$ 的四条曲线更加分散，中分面旋转核心区受壁面影响减小。当 $C _ { \mathrm { w } } = 6 0 0 0$ 时， $\lambda _ { \mathrm { T } } = 0 . 1 1 3$ ，流动为惯性主导，湍动剧烈， $r / b = 0 . 6 4$ 处由于进气流的影响可以明显看到 $\beta$ 波动；由于壁面边界层影响减小，至$r / b = 0 . 9 5$ 处 $\beta$ 才急剧增大。

![](images/47f9c946af291576d05643e1271e05f5d38de2b733f33722b893f73399b34e28.jpg)

![](images/cb3db50b803714a1f0acda43f9414d9dcf1dedb89f8038d5cc9d84ae5e85c56a.jpg)  
图3预旋比沿径向分布Fig.3 Radial variation of pre-swirl ratio

![](images/1046d33fae0a4680378ad468d01d2c2d81b6c7148511fef6bd0f339c7b6a99da.jpg)

![](images/8de3fbe09069a7817b8928defbbc768e140c06981fa138284e8adf09769283c6.jpg)  
图4 $r = 1 8 2 . 6 ~ \mathrm { m m }$ 处预旋比轴向变化 Fig.4 Axial variation of pre-swirl ratio at $r = 1 8 2 . 6 ~ \mathrm { m m }$

图4为不同冷却气体进气量，不同进气预旋比时盘腔气流进入密封时！ $( r = 1 8 2 . 6 ~ \mathrm { m m } )$ 预旋比沿轴向的分布。当 $C _ { \mathrm { w } } = 1 5 0 0$ ， $\lambda _ { \mathrm { T } } = 0 . 0 2 8$ 时，如图4(a)所示，流动处于黏性主导，湍动较小，进气与盘腔内气体混合均匀，气流流至密封时已不受进气预旋的影响，此时转静壁面边界层主导盘腔内流动状态。当进气流逐渐增大，湍动增强，如图4(b)、(c)所示，流动受边界层影响逐渐减弱，进入密封时气流仍受进气预旋影响，研究密封处流动时 ${ \beta } _ { \mathrm { p } }$ 影响不可忽略。同时随着近壁面边界层影响减小，进入密封气流的$\beta$ 整体减小。

图5为不同冷却气体进气量，不同预旋比时预旋比在盘腔内子午面的分布云图。如图所示，当$C _ { \mathrm { w } } = 1 5 0 0$ 时，进气预旋比变化仅影响到盘腔中上部，盘腔顶部 $\beta$ 分布相似。 $C _ { \mathrm { w } } = 3 5 0 0$ 时，进气流系数对盘腔整体流动影响加强。 $C _ { \mathrm { w } } = 6 0 0 0$ 时，进气预旋明显影响密封内流动状态。

![](images/98c11ccfeacd4f158c5b93a4dc95b715734bf61655fb0059169a412b1a9d8549.jpg)  
图5预旋比在盘腔内子午面的分布云图  
Fig.5 Distribution of pre-swirl ratio in the meridional plane

定义无量纲静压系数 $\xi$ ：

$$
\xi = 2 ( p - p _ { \mathrm { p } } ) / ( \rho \varOmega ^ { 2 } b ^ { 2 } )
$$

式中， $p _ { \mathrm { p } }$ 为中分面进气处静压。

图6为不同冷却气体进气量，不同进气预旋比时静压系数沿径向的变化。如图6所示，由于旋转泵效应，静压随着半径的增大存在明显的压力梯度， $\xi$ 沿径向线性增大，且其斜率主要受进气 ${ \beta } _ { \mathrm { p } }$ 影响。图6(a）中进气流量较小，盘腔内流动受转静盘边界层影响大，旋转泵效应愈加明显，曲线斜率较大。图6(b),(c)中，流动处于惯性主导， $\xi$ 受流量影响较小,斜率由进气 ${ \beta } _ { \mathrm { p } }$ 主导。此外，当 $\beta _ { \mathrm { p } } = 1$ 时， $\xi$ 分布几乎不受流量影响。

轮缘密封处燃气入侵现象出现在主流压力高于盘腔压力处，进气预旋增大盘腔静压，由此推测进气预旋有利于轮缘密封封严效率的提高，但在冷气流量较小时，受转静盘边界层影响，进气预旋对盘腔内流动影响较小，静压变化不大，因此封严效率提高有限。

![](images/e6a7e57db99987e33bcfb50ef4999c1222c3c029c8b4bdfd1732b7e95245fa3b.jpg)  
Fig.6 Radial variation of static pressure coefficient

![](images/951275104518cc0123e5daa5ddc3cacbc117a355314d04eb12fb84b696abf885.jpg)  
图6静压系数沿径向变化

定义无量纲总压系数 $\xi _ { 0 }$

$$
\xi _ { 0 } = 2 ( p _ { 0 } - p _ { 0 , \mathrm { p } } ) / ( \rho \varOmega ^ { 2 } b ^ { 2 } )
$$

式中 $p _ { \mathrm { 0 , p } }$ 为中分面进气处总压。

![](images/0950d64da99f1df4dedda35f79ae78f115d80d30070014030442e929aa9139e0.jpg)

![](images/187434ade07fddece5e6829bdb2c06cfd3713211e8c7d02f8728514854052a08.jpg)  
图7总压系数沿径向变化 Fig.7 Radial variation of total pressure coefficient

由于轮缘处存在燃气入侵，为研究入侵燃气对盘腔内部的换热的影响，比较式(6)与式(7)计算得出的努塞尔数结果。图8为不同冷却气体进气量，不同预旋比时 $N u$ 沿径向分布。如图所示，当 $C _ { \mathrm { w } }$ 较小,燃气入侵较严重时， $N u$ 明显大于 $N u _ { 2 }$ ，而当 $C _ { \mathrm { w } }$ 较大,封严较好时，两种方式计算所得 $N u$ 相差不大；因此可知当存在燃气入侵时，由于燃气较高温度的影响，盘腔内气流温度受热上升，实际 $T _ { \mathrm { w , a d } }$ 大于根据旋转核心区流动状态计算所得， $N u _ { 2 }$ 小于 $N u$ ；而当封严较好时， $N u$ 与 $N u _ { 2 }$ 相近，盘腔内换热计算可忽视主流入侵影响。此外，进气 $\beta _ { \mathrm { p } }$ 的增大会导致转盘进气高度处 $N u$ 局部增大，这种 $N u$ 的局部变化两种计算方法均可得到，且随着冷气量的增加，湍动的增强，变化愈加明显。

图7为不同冷却气体进气量，不同进气预旋比时总压系数沿径向的变化。与 $\xi$ 变化不同的是，盘腔内 $\xi _ { 0 }$ 的沿径向基本不变；由总压定义可知，总压与静压，与速度平方成正比，由于盘腔环境中切向速度较大，因此 $\xi _ { 0 }$ 与 $\xi$ 和 $\beta ^ { 2 }$ 成正比，符合如图3、图6中 $\beta$ 沿径向减小, $\xi$ 沿径向增大的趋势。对比图$7 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ ，当冷气量逐渐增加时，流动受近壁面边界层影响减小，单位冷气量受转盘壁面作用功减小, $\xi _ { 0 }$ 减小。同时，随着进气预旋比的增大，相对转盘气流速度减小，转盘对气流的作用功减小， $\xi _ { 0 }$ 减小，级效率提高。此外，在进气位置附近，进气流与盘腔内气流混合，并冲击到转盘表面，一部分动能转化为热，因此总压急剧下降，尤其是当 $\beta _ { \mathrm { p } } = 1 . 0$ 时，进气初速度较大，混合冲击均较剧烈， $\xi _ { 0 }$ 明显较小；而高位近上壁处，受壁面影响，切向速度迅速增加， $\xi _ { 0 }$ 上升。

# 2.2盘腔换热特性

表征换热能力大小的努塞尔数 $N u$ 定义如下：

$$
N u = h r / k = q _ { \mathrm { w } } r / \left[ k ( T _ { \mathrm { w } } - T _ { \mathrm { w , a d } } ) \right]
$$

式中， $h$ 为表面传热系数； $q _ { \mathrm { w } }$ 为壁面热流密度； $k$ 为导热系数; $T _ { \mathrm { w } }$ 为壁面温度; $T _ { \mathrm { w , a d } }$ 为壁面绝热温度。

在过去的研中，转静盘系统壁面绝热温度$T _ { \mathrm { w , a d } }$ 常依据文献[16]，由下式根据盘腔流动计算得出：

$$
T _ { \mathrm { w , a d } } = T _ { \mathrm { 0 , p } } - \frac { v _ { \varphi , \infty } ^ { 2 } } { 2 c _ { \mathrm { p } } } + R \frac { \varOmega ^ { 2 } r ^ { 2 } } { 2 c _ { \mathrm { p } } } \left( 1 - \frac { v _ { \varphi , \infty } } { \varOmega r } \right) ^ { 2 }
$$

式中， $T _ { \mathrm { 0 , p } }$ 为进气总温, $v _ { \varphi , \infty }$ 为旋转核心处切向速度； $R$ 为温度恢复系数(取 $P r ^ { 1 / 3 }$ )。

![](images/7ec408afa37a043631e8aef1308daee4defbd65c1f2f674917459a7e479511b2.jpg)  
图8转盘表面 $N u$ 沿径向分布  
Fig.8 Radial variation of the nusselt number on rotor

图9中无量纲温度系数 $\Theta _ { \mathrm { w } }$ 定义如下：

$$
\theta _ { \mathrm { w } } = ( T _ { \mathrm { w , a d } } - T _ { 0 , \mathrm { p } } ) / ( T _ { 0 , \mathrm { i n } } - T _ { 0 , \mathrm { p } } )
$$

式中 $T _ { 0 , \mathrm { i n } }$ 为主流进气总温。

图9为不同冷却气体进气量，不同预旋比时转盘壁面温度变化云图。在轮缘处，入侵燃气对转盘的加热主导壁面温度的变化。如图9所示，入侵燃气对转盘密封处壁面的绝热温度影响较大，且存在明显的周向不均匀性。当 $C _ { \mathrm { w } } = 1 5 0 0$ 时，封严较差，入侵量大，将影响整个盘腔的温度分布；随着冷气量的逐步增加，封严效率的提高，入侵气流对密封处转盘壁面及盘腔内的温度影响也逐渐减小。对比不同进气预旋比时的温度云图变化，当 $\beta _ { \mathrm { p } } = 1 . 0$ 时入侵对密封壁面温度影响减弱，但局部温度梯度增加;当进气预旋增大时，入侵气流对密封壁面的影响控制在了更小的范围内。

![](images/6e2f5df797865559d94ef248cbf4a619b7c54278bc2bc531aaf35acba390ce06.jpg)  
Fig.9 Distribution of adiabatic temperature on rotor surface

# 2.3轮缘密封封严特性

封严效率 $\varepsilon _ { \mathrm { c } }$ 由式（1）定义，取静盘表面 $r =$ $1 8 2 ~ \mathrm { m m }$ 处 $\varepsilon _ { \mathrm { c } }$ 决定径向密封的封严效率。图10 是3种进气预旋比下轮缘密封的封严效率随冷气量变化折线图，如图所示， ${ \beta } _ { \mathrm { p } }$ 的增加提高径向密封封严效率，但在冷气量较小时影响有限；冷气量达到$C _ { \mathrm { w } } = 6 0 0 0$ 时， $\varepsilon _ { \mathrm { c } }$ 达到1。

主流压力系数 $\xi _ { \mathrm { a } }$ 定义为：

$$
\xi _ { \mathrm { a } } = 2 ( p _ { \mathrm { a } } - \bar { p } _ { \mathrm { a } } ) / ( \rho \varOmega ^ { 2 } b ^ { 2 } )
$$

式中， $\begin{array} { r } { p _ { \mathrm { a } } } \end{array}$ 为轮毂处主流静叶尾缘与轮缘间隙中间位置处的静压； $\bar { p } _ { \mathrm { a } }$ 为 $\begin{array} { r } { p _ { \mathrm { a } } } \end{array}$ 的平均值。

图11为主流通道处周向压力分布，如图所示，主流存在周向的压力波动，波动导致主流气体对盘腔的外部诱导入侵 (EI)，这种入侵占据主流入侵的主要部分[5]；主流压力受冷气量与冷气进气预旋比的影响不大。

![](images/aeff0dbf07e2d0e39dcb5dc14b79c45374652612cc294993248174c6e7037459.jpg)  
图10不同冷气量下轮缘密封的封严效率

![](images/33d52f78fffc088e700b8befca8ee89051239363e4b669cf1dab5d8faf861fca.jpg)  
图9转盘壁面温度云图  
Fig.10 Effect of sealing flow rate on sealing efficiency   
图11 主流通道处周向压力分布  
Fig.11 Circumferential distribution of static pressure coefficient in annulus

图12为密封间隙处径向速度云图。如图12所示，即使冷气量达到封严所需，主流气流由于高压作用仍会对密封间隙有一定的入侵；主流气流在周向 $\xi _ { \mathrm { a } }$ 峰值出入侵盘腔，与封严气流混合，一部分流入盘腔内部造成更深度的主流入侵，大部分随封严气流自 $\xi _ { \mathrm { a } }$ 谷值位置附近流出间隙。

图 13 为径向密封不同高度在 $r = 1 8 2 . 6 \ \mathrm { m m }$ $1 8 8 . 8 \ \mathrm { \ m m }$ 和 $1 9 4 ~ \mathrm { m m }$ 处的封严效率云图，如图13所示，随着冷气量的增加，主流入侵的深度减小。 $C _ { \mathrm { w } } = 1 5 0 0$ 时，湍动较小，气流混合均匀，密封处周向不均匀性较低，同时由于混合充分，在 $\xi _ { \mathrm { a } }$ 较小的位置入侵气流无法排尽，导致盘腔的封严效率较低。当 $C _ { \mathrm { w } } = 6 0 0 0$ 时，达到最小封严气量，主流的入侵对盘腔的影响基本控制在密封的轴向间隙密封段。

![](images/a66bce1b13cd0a729f49d5c4640418d66028b5c8f72fa4f1f322e0f45cc46a41.jpg)  
图12轴向密封间隙处径向流速云图

![](images/1502e6dae61c2fe5f8e67292860496f5c323719e0ccff59edd6f0b150ff15f34.jpg)  
Fig.12 Distribution of radial velocity in axial clearance   
图13径向密封处封严效率多层云图  
Fig.13 Distribution of sealing efficiency at different radius

# 3结论

本文采用附加变量法，数值求解了三维RANS方程组和SST湍流模型，分析了三种不同冷气量下，四种冷气进气预旋比时，带径向轮缘密封和轴向预旋进气的转静盘腔的流动换热特性与轮缘处密封的封严特性，得出如下结论：

1)盘腔内中分面处预旋比随半径的增大而减小,其总体随进气预旋比的增大而增大；中分面处静压系数沿径向线性增大，斜率大小与进气预旋比成正比；中分面处总压系数与预旋比平方及静压系数成正比，沿径向基本不变，略有增大。

2）当入侵较大时转盘壁面绝热温度升高，壁面绝热温度无法通过理论公式由盘腔内流动状态得出，理论式得出的Nu 较实际略大。此外主流入侵对密封处壁面温度影响较大，使壁面绝热温度出现明显的周向温度梯度，温度梯度随进气预旋比增大而增大。

3)封严效率随冷气量增大而增大，进气预旋提高封严效率。随冷气量增加，入侵气流与盘腔内的气流掺混控制在密封轴向间隙与小部分径向间隙中。

# 参考文献

[1]PatiniosM,ScobieJA,SanganAM,et al.Measurements and Modelling of Ingress ina New1.5-Stage Turbine Research Facility [R].ASMEPaper GT2016-57163,2016   
[2] Sangan C M,Pountney O J,Zhou K Y,et al.Experimental Measurements of Ingestion ThroughTurbine Rim Seals-Part I: Externally Induced Ingress [J].ASME Journal of Turbomachinery, 2013,135(2):319-329 [3] Sangan C M,Pountney O J,Zhou K Y,et al. Experimental Measurements of Ingestion Through Turbine Rim Seals-Part II: Rotationally Induced Ingress [J].ASME Journal of Turbomachinery,2013,135 (2):319-329 [4] Sangan C M,Pountney O J,Scobie J A,et al．Experimental Measurements of Ingestion Through Turbine Rim Seals-Part II: Single and Double Seals [J].ASME Journal of Turbomachinery, 2013,135(5):1790-1791 [5] Beard P A,Chew J,Gao F,et al.Unsteady Flow Phenomena in Turbine Rim Seals [R].ASME Paper GT2016- 56110, 2016 [6] Savov S S,Atkins N R, Uchida S, Comparison of Single and Double Lip Rim Seal Geometry [R].ASME Paper GT2016-56317,2016 [7] Liu G,Wu H, Feng Q,et al. Theoretical and Numerical Analysis on the Temperature Drop and Power Consumption of a Pre-swirl System [R]. ASME Paper GT2016- 56742,2016 [8] Zhang F,Wang X,Li J,Numerical Investigation of Flow and Heat Transfer Characteristics in Radial Pre-Swirl System with Different Pre-Swirl Nozzle Angles [J]. International Journal of Heat And Mass Transfer,2016,95:984- 995 [9] Zhang F,Wang X, Liao G,et al. Computational Fluid Dynamics Analysis for Effect of Length to Diameter Ratio of Nozzles on Performance of Pre-Swirl Systems [J]. Proceedings of the Institution Of Mechanical Engineers Part a-Journal of Power And Energy, 2015,229 (4):381-392   
[10] Tao Z, Zhang D,Luo X,et al. Windage Heating in a Shrouded Rotor-Stator System [J].ASME Journal of Engineering for Gas Turbines and Power，2014，136(6): 0626021-6260210   
[11] Luo X, Wang L, Zhao X,et al. Experimental Investigation of Heat Transfer ina Rotor-Stator Cavity with Cooling air Inlet at Low Radius [J].International Journal of Heat And Mass Transfer,2014,76:65-80   
[12] Owen J M,Wu K,Scobie J A,et al.Use of Pressure Measurements to Determine Effectiveness of Turbine Rim Seals [J].ASME Journal of Engineering for Gas Turbines And Power,2015,137(3):V05CT16A004   
[13] Lalwani Y, Sangan C M,Wilson M, et al. Steady Computations of Ingress Through Gas Turbine Rim Seals [J]. Proc. IMechE Part A: Journal of Power And Energy, 2015, 229(1): 2-15   
[14] Scobie JA,Sangan C M, Owen JM,et al. Experimental Measurements of hot Gas Ingestion Through Turbine Rim Seals at Off-Design Conditions [J].Proc.IMechE Part A: Journal of Power And Energy, 2014, 228(5): 491-507   
[15]高庆,李军.径向轮缘密封封严效率的数值研究[J].西安交 通大学学报，2014,48(9):55-61 GAO Qin,LI Jun. Numerical Investigations for Sealing Efficiency of the Turbine Rim Radial Seal [J]. Journal of Xi'an Jiaotong University, 2014, 48(9): 55-61   
[16]Karabay H,Wilson M,Owen J MPredictions of Effect of Swirl on Flow and Heat Transfer in a Rotating Cavity [J]. International Journal of Heat and Fluid Flow,2001, 22(2): 143-155