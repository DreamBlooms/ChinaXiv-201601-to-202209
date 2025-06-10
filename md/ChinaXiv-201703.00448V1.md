# 基于NIPC的压气机叶片加工误差不确定性分析

蔡宇桐1,2 高丽敏1,2马 驰1,2郑天龙1,2(1．西北工业大学动力与能源学院，西安710072;2．先进发动机协同创新中心，北京100191)

摘要压气机叶片加工误差的存在使得叶片实际尺寸偏离设计初衷，对压气机性能造成一定的影响。为了分析加工误差对叶片性能的影响，首先通过三坐标测量仪对大量叶片进行误差检测与分析获取了轮廓误差的真实分布规律，其次运用五点四阶非嵌入式混沌多项式对加工误差影响进行了不确定性量化，最后分析了加工误差对气动性能的真实影响规律。研究结果表明，加工误差的存在使得叶型性能有所恶化，但其影响主要体现在叶型性能稳定性；建议在进行误差影响分析时应充分考虑误差的随机特性并使用标准差等具有统计意义的变量进行分析，相对于传统的影响评价方法能更加客观对误差影响进行评判与描述。

关键词加工误差；不确定性量化；NIPC；气动性能中图分类号：V231.3 文献标识码：A 文章编号：0253-231X(2017)03-0490-08

# Uncertainty Quantification on Compressor Blade Considering Manufacturing Error Based on NIPC Method

CAI Yu-Tong $^ { 1 , 2 }$ （20 GAO Li-Min $^ { 1 , 2 }$ （20 MA Chi $^ { 1 , 2 }$ （204号 ZHENG Tian-Long $^ { 1 , 2 }$

1.School of Power and Energy,Northwestern Polytechnic University，Xi'an,PRC，710072; 2.Collaborative Innovation Center of Advanced Aero-Engine Beijing,China，100191)

AbstractThe existence of compressor blade manufacturing error causes the actual dimensions varying from design dimensions, which makes impacts on compressor performance.In order to analyze the influence of manufacturing error on blade performance, first adopted coordinate measuring machine to do error measuring and analysis,getting the real distribution patterns of contour error, and then applied 5,4 order non-intrusive polynomial chaos for uncertainty quantification of the influence on manufacturing error,at last analyzed the real efects law of manufacturing error on aerodynamic performance. The results show that the existence of manufacturing error worsens the performance of blade,but its influence mainly lies in stability of airfoil performance.It is suggested that random characters of error should be taken into consideration when analyzing the influence of error,and statistically significant variables such as standard deviation should be used for this analysis. Compared with traditional impact assessment methods,uncertainty analysis can assess and describe the influence of error more objective.

Key wordsmanufacturing error; uncertainty quantification; NIPC; aerodynamic performance

# 0引言

叶片是构成压气机的基本单元，由相邻叶片构成的流道内的流动情况决定了压气机性能，因此叶片对于压气机性能起着决定性作用。同时它也是航空发动机中数量最多、加工难度最大的关键零部件之一，其生产工作量可占整台发动机的 $3 0 \% ^ { [ 1 ] }$ 。因此，压气机叶片的最终加工质量与几何型面直接决定着压气机乃至航空发动机整体生产成本与运行性能。

由于压气机叶片在空间上呈现出弯、扭、掠相结合的特点，其具有极高的加工难度然。在数控加工过程中会因为装卡定位、残余应力等因素容易产生加工变形，不可避免的产生加工误差[2]。Garzon等[3]的误差检测结果表明理论叶型与实际叶型存在不同程度的偏差，且偏差的大小及位置呈现出高度随机性，而这样的偏差会使得最终的叶片性能无法满足设计意图。随着压气机设计逐渐精细化，关于加工误差对气动性能的影响引起了更多的关注。

针对加工误差对气动性能的影响，国内外学者们开展了一系列工作。NASALewis中心的Roelke等[4-5]试验研究了型面偏差对气动性能的影响并分析了误差位置的敏感性。国内学者[6-10]从加工误差引起的叶型参数偏差角度出发，通过数值及试验研究手段获得了不同类型的误差对于气动性能的影响，获取了参数变化对叶型性能的影响规律。上述研究对于误差影响分析具有一定的参考价值，但其局限在于研究中未能考虑加工误差的随机特性，本质上属于“确定性”研究。

针对考虑加工误差随机特性的误差影响研究，MIT 的Garzon 等[11]在 2003 年率先采用了概率统计方法，通过大量的误差统计与分析并运用主成分分析方法获得了影响气动性能的主要叶型参数，同样的研究思路在罗罗公司的Heinze[12]及Pa-niagua 等[13]的研究中也得到了运用。但局限于对误差影响的认识水平，上述研究未能形成完备且合理的误差影响评价体系，所得结论很难用于直接指导加工制造，且其所用方法具有一定的局限性导致工作量过大，不利于工程推广。

从实际加工及产品质量检测出发，并充分考虑工程上的不确定性及加工合格率，对于加工误差影响的合理评估应引起足够的重视。针对目前已有研究的不足，本文充分考虑了误差的随机特性并运用非嵌入式混沌多项式（Non-intrusive PolynomialChaos，简称NIPC）展开对误差影响进行不确定性分析，旨在建立合理的误差影响评价体系，获得误差的真实影响规律并为下一步的叶型稳健设计提供参考。

# 1研究对象及方法

本文以二维压气机叶型为研究对象对误差的影响规律进行分析，能够降低研究难度并易于将所得结论直接用于指导加工制造。选择二维压气机叶型的原因一方面在于理论叶型通常由等高截面数据给出，另一方面在于加工公差亦建立在二维截面上。

# 1.1研究对象

本文的研究算例为课题组自行设计的可控扩散叶型 (NPU-1)，其前后缘形状均为圆弧形，叶栅基本几何参数如表1所示。

表1叶型主要几何参数  
Table1 Main ParametersofResearched Airfoil   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>前缘半径/mm</td><td>0.5205</td></tr><tr><td>尾缘半径/mm</td><td>0.5850</td></tr><tr><td>弦长/mm</td><td>69.9456</td></tr><tr><td>叶型弯角/()</td><td>39.61</td></tr><tr><td>栅距/mm</td><td>30.4350</td></tr><tr><td>最大厚度/mm</td><td>3.5127</td></tr></table></body></html>

# 1.2研究方法

本文选取多项式混沌方法进行误差影响不确定性分析，其基本执行流程如图1所示。多项式混沌方法源于Wiener[14] 提出的同性混沌方法（Homoge-nousChaos)，该方法运用多项式对随机变量进行展开，将变量的随机特性转移到多项式系数上。根据随机变量满足的分布不同，选取不同形式的基函数对随机过程进行谱展开，Cameron-Martin[15]定理证明这种展开能够以正交多项式的形式描述任意二阶随机过程。

Wiener采用代表高斯型随机变量的Hermit多项式为基函数对随机过程进行展开，本质上混沌多项式是原始模型对标准正态随机变量的混沌多项式展开。

![](images/d6aa735b497c6246dbdef8e340d79b5de4416aac7169d2f2ba6271990f81980c.jpg)  
图1多项式混沌方法执行流程图[16] Fig.1 Flowchart of Polynomial Chaos Expansion[16]

设 $X ( \theta )$ 是概率空间 $( \Omega , F , P )$ 上关于随机事件$\theta$ 的随机过程，则 $X ( \theta )$ 可以展开为

$$
X ( \theta ) = a _ { 0 } I _ { 0 } + \sum _ { i _ { 1 } = 1 } ^ { \infty } \widehat { a } _ { i _ { 1 } } H _ { 1 } ( \xi _ { i _ { 1 } } ( \theta ) ) +
$$

$$
\sum _ { i _ { 1 } = 1 } ^ { \infty } \sum _ { i _ { 2 } = 1 } ^ { i _ { 1 } } { \widehat { a } } _ { i _ { 1 } i _ { 2 } } H _ { 2 } ( \xi _ { i _ { 1 } } ( \theta ) , \xi _ { i _ { 2 } } ( \theta ) ) + \cdot \cdot \cdot
$$

其中， $H _ { n } ( \xi _ { i _ { 1 } } , \xi _ { i _ { 2 } } , \cdot \cdot \cdot , \xi _ { i _ { n } } )$ 表示随机向量 $\xi \ = \ ( \xi _ { i _ { 1 } }$ $\xi _ { i _ { 2 } } , \cdots , \xi _ { i _ { n } } )$ 的 Hermit 多项式，其表达式为

$$
H _ { n } ( \xi _ { i _ { 1 } } , \xi _ { i _ { 2 } } , \cdot \cdot \cdot , \xi _ { i _ { n } } ) =
$$

$$
\exp \left( { \frac { 1 } { 2 } } \xi ^ { \mathrm { T } } \xi \right) ( - 1 ) ^ { n } { \frac { \partial ^ { n } \exp \left( { \frac { 1 } { 2 } } \xi ^ { \mathrm { T } } \xi \right) } { \partial \xi _ { i _ { 1 } } \cdot \cdot \cdot \partial \xi _ { i _ { n } } } }
$$

引入变量 $\psi _ { j } ( \xi )$ 与 $\widehat { \boldsymbol { a } } _ { j }$ 表述 $H _ { n } ( \xi _ { i _ { 1 } } , \xi _ { i _ { 2 } } , \cdot \cdot \cdot , \xi _ { i _ { n } } )$ 则式（1）可简化为下式

$$
X ( \theta ) = \sum _ { j = 0 } ^ { \infty } \widehat { a } _ { j } \psi _ { j } ( \xi )
$$

为了使得式(3）可用，需要通过截断略去高阶小量，考虑随机变量的维数及所采用的Hermit多项式阶次利用下式计算其上限

$$
P + 1 = \frac { ( p + n ) ! } { p ! n ! }
$$

其中， $P$ 为式（3）的求和上限， $p$ 为多项式阶数， $n$ 是随机变量维数。

于是，式 (3)最终写为

$$
X ( \theta ) = \sum _ { j = 0 } ^ { P } \widehat { a } _ { j } \psi _ { j } ( \xi )
$$

混沌多项式的构建关键在于求解式(5）中的系数 $( \widehat { a } _ { j } , j = 0 , 1 , \cdot \cdot \cdot P )$ 。NIPC不需要对求解程序进行修改，将确定性系统看成黑匣子处理，通过系统响应近似确定混沌多项式系数。混沌多项式系数可按照下式进行求解

$$
a _ { i } = \frac { \langle X ( \theta ) , \psi _ { i } ( \xi ) \rangle } { \langle \psi _ { i } ( \xi ) , \psi _ { i } ( \xi ) \rangle } { = } \int _ { - \infty } ^ { + \infty } \mathrm { d } \xi _ { 1 } \int _ { - \infty } ^ { + \infty } \mathrm { d } \xi _ { 2 } \cdot \cdot \cdot \int _ { - \infty } ^ { + \infty } \mathrm { d } \xi _ { n } *
$$

$$
\left[ X ( \theta ) \frac { \psi _ { i } ( \xi ) } { \langle \psi _ { i } \psi _ { i } \rangle } \prod _ { k = 1 } ^ { n } \frac { \exp ( \xi _ { k } ^ { 2 } / 2 ) } { \sqrt { 2 \pi } } \right]
$$

采用高斯Hermit积分公式计算上述积分，积分表达式可表示为

$$
a _ { i } = \sum _ { m _ { i } = 1 } ^ { m } \cdots \sum _ { m _ { n } = 1 } ^ { m } X ( x _ { m _ { 1 } } , x _ { m _ { 2 } } , \cdots , x _ { m _ { n } } )
$$

$$
\frac { \psi _ { i } ( x _ { m _ { 1 } } , x _ { m _ { 2 } } , \cdot \cdot \cdot , x _ { m _ { n } } ) } { \langle \psi _ { i } \psi _ { i } \rangle } \prod _ { k = 1 } ^ { n } w _ { m _ { k } }
$$

其中 $m$ 为积分点个数， $x _ { k }$ 和 $w _ { k } ( k = 1 , 2 , \cdots , m )$ 为一维Hermit 积分点和权值。

在求得混沌多项式的系数之后，根据多项式的正交性，随机变量响应的均值可根据下式求得：

$$
\overline { { { X } } } ( \xi ) = \int _ { R } X ( \xi ) W ( \xi ) \mathrm { d } \xi =
$$

$$
a _ { 0 } + \sum _ { j = 1 } ^ { P } a _ { j } \int _ { R } \psi _ { 0 } ( \boldsymbol { \xi } ) \psi _ { j } ( \boldsymbol { \xi } ) W ( \boldsymbol { \xi } ) \mathrm { d } \boldsymbol { \xi } = a _ { 0 }
$$

而响应方差可通过下式求得

$$
\begin{array} { c } { { \displaystyle \sigma ^ { 2 } = \int _ { R } ( \overline { { { X } } } ( \xi ) - a _ { 0 } ) ^ { 2 } W ( \xi ) \mathrm { d } \xi = } } \\ { { \displaystyle \sum _ { j = 1 } ^ { P } \sum _ { k = 1 } ^ { P } \int _ { R } a _ { j } \psi _ { j } ( \xi ) a _ { k } \psi _ { k } ( \xi ) W ( \xi ) \mathrm { d } \xi = \sum _ { j = 1 } ^ { P } \left[ a _ { j } ^ { 2 } \left. \psi _ { j } ^ { 2 } \right. \right] } } \end{array}
$$

# 1.3加工误差检测与分析

课题组前期在压气机叶片误差检测方面开展了大量的工作。具体地，运用三坐标测量仪对大量平面叶栅叶片进行了误差检测，对应的测量截面如图2所示。在误差统计分析方面，通过自编程序对上千个叶片截面的测量结果进行误差分析，统计得到了叶片轮廓误差分布如图3所示。从图中可以看出，叶片轮廓误差在 $\pm 0 . 1 \ \mathrm { m m }$ 内随机波动，且近似于满足$N ( 0 , 0 . 0 3 ^ { 2 } )$ 高斯分布。

![](images/32a2541414d2b2cdcb8e7b0bc68e9af0cf8778efe1ba25703d532698d8c118c2.jpg)  
图2叶片误差检测截面示意 Fig.2 Sections of Error Detection

![](images/223e76ab3c5ba7912247ea4a4a548f26e7bc37d33bc4fe8470523d10b0e4f843.jpg)  
图3轮廓误差统计Fig.3 Statistics of profile error

# 2加工误差不确定性分析

# 2.1数值验证

由于加工误差量级相对较小，对数值模拟精度要求较高，因此首先对数值计算精度进行了验证。本文经过大量的数值模拟试验后最终确定了如下数值方案：前缘延伸段为0.5倍弦长而尾缘延伸段给定为1倍弦长，使用 Autogrid5 模块生成O4H 型拓扑结构网格，网格总数为53434。叶片表面第一层网格尺度设为 $1 \times 1 0 ^ { - 6 } \mathrm { ~ m ~ }$ ，壁面 $Y ^ { + }$ 值小于4，满足所选Spalart-Allmaras(S-A）湍流模型的要求，按照上述要求生成了叶片网格，对应网格B2B截面如图4所示。计算边界条件进口给定总温总压和进口气流角，出口给定质量流量，保证型面发生变化时仍保持工况一致。

![](images/92a433c2d46e194820f03d527a34d892257a41d155900bf24a46a26e5f07ed5a.jpg)  
图4计算网格分布Fig.4 Distribution of Computational Grid

采用上述数值方法对叶型在设计工况下进行了数值模拟，并通过对比试验数据对数值精度进行验证。图5给出了叶片表面等熵马赫数对比图，其中$X$ 坐标代表沿叶片表面的无量纲弦长，而图6给出了叶栅出口损失沿栅距方向分布图，其中 $Y$ 坐标为沿栅距方向的无量纲长度。通过对比可以看出，本文中数值计算结果和试验结果吻合地较好，验证了本文数值方法的可靠性。其中损失的定义如下：

$$
\mathrm { l o s s } = { \frac { P _ { t 1 } - P _ { t 2 } } { P _ { t 1 } - P _ { 1 } } }
$$

![](images/3c24da6e918d237af91bcbc045f3371a8b7c5c512f2d8c65b0dfaf721102369b.jpg)  
图5叶片表面等熵马赫数分布Fig.5 Distribution of Isentropic $\mathbf { \nabla } \_ { M a }$

![](images/97f19b585cfeb9f564335755700a9152108fde9bac81fcd8c16fa2b1a5ad9671.jpg)  
图6叶栅出口损失分布Fig.6 Distribution of Exit Loss

# 2.2NIPC有效性验证

本文分别选取多变量非线性函数及轮廓误差影响两个算例对NIPC在不确定性量化（UncertaintyQuantification，简称UQ）分析中的有效性及精度进行验证，并通过对比传统的蒙特卡洛模拟（MonteCarloSimulation，简称MCS）方法，说明NIPC在预测精度及计算时间两方面的优越性。

# 1）函数测试算例

选取如式（16）所示测试函数对NIPC方法在UQ分析中的有效性进行验证。

Table 2 Simulation Result Using MCS Method   

<html><body><table><tr><td>样本数</td><td>均值</td><td>误差</td><td>方差</td><td>误差</td><td>时间/s</td></tr><tr><td>100</td><td>3.606476319</td><td>-0.04808877</td><td>0.392979869</td><td>0.06496805</td><td>13.22</td></tr><tr><td>1000</td><td>3.651849535</td><td>-0.00271555</td><td>0.3248997583</td><td>-0.00311205</td><td>132.43</td></tr><tr><td>5000</td><td>3.661833544</td><td>0.00726845</td><td>0.3258418855</td><td>-0.00216993</td><td>661.68</td></tr><tr><td>10000</td><td>3.652989212</td><td>-0.00157587</td><td>0.3290664209</td><td>0.001054604</td><td>1325.41</td></tr><tr><td>20000</td><td>3.651328545</td><td>-0.00323654</td><td>0.3318251148</td><td>0.003813298</td><td>2620.35</td></tr></table></body></html>

表3NIPC方法计算函数响应情况  
Table 3 Simulation Result Using NIPC Method   

<html><body><table><tr><td>样本数</td><td>均值</td><td>误差</td><td>方差</td><td>误差</td><td>时间/s</td></tr><tr><td>2</td><td>3.651480543</td><td>-0.00308454</td><td>0.318055653</td><td>0.009956162</td><td>0.26</td></tr><tr><td>3</td><td>3.654513940</td><td>-0.000051149</td><td>0.329222624</td><td>-0.001210808</td><td>0.40</td></tr><tr><td>4</td><td>3.654535717</td><td>-0.000029373</td><td>0.327749470</td><td>0.000262345</td><td>0.53</td></tr><tr><td>5</td><td>3.654586920</td><td>0.0000218300</td><td>0.328014950</td><td>-0.000003133</td><td>0.62</td></tr><tr><td>6</td><td>3.654543489</td><td>-0.000021601</td><td>0.327683793</td><td>0.000328023</td><td>0.79</td></tr></table></body></html>

$$
\begin{array} { l } { { Y = f ( X ) } } \\ { { \displaystyle } } \\ { { f ( X ) = 2 0 \times \left( \frac { \mathrm { e } ^ { - \frac { ( x + 2 . 7 ) ^ { 2 } } { 2 } } } { \sqrt { 2 \pi } } + \frac { \mathrm { e } ^ { - \frac { ( x - 2 . 7 ) ^ { 2 } } { 2 ( 2 ^ { 2 } ) } } } { \sqrt { 2 \pi } } \right) } } \\ { { X \sim N ( 2 , 0 . 5 ^ { 2 } ) , \mathrm { i . e } , p ( x ) = \frac { \mathrm { e } ^ { - \frac { ( x - 2 . 7 ) ^ { 2 } } { 2 ( 0 . 5 ^ { 2 } ) } } } { 0 . 5 \sqrt { 2 \pi } } } } \end{array}
$$

该函数的真实均值及方差可求得为：

$$
\begin{array} { c } { { \mu _ { Y } = 3 . 6 5 4 5 6 5 0 9 0 3 } } \\ { { \sigma _ { Y } = 0 . 3 2 8 0 1 1 8 1 6 2 } } \end{array}
$$

表2及表3分别给出了两种情况下均值与方差计算结果及所用时间对比结果，从中可以看出NIPC方法可以在保证精度较高的前提下，大幅度减少计算时间。

# 2)轮廓误差不确定性量化算例

为了进一步验证NIPC在UQ分析中的优越性，本文对于轮廓误差对气动性能的影响分别采用MCS与NIPC方法进行不确定分析，进一步验证NIPC的有效性。

基于前期误差检测结果可知轮廓误差满足高斯分布，本文将轮廓误差简化为均匀轮廓误差，误差叶型示意如图 7 所示。对上述 CDA 叶型在$\mathit { M a } { = } 0 . 7 5$ 、 $i { = } 5 ^ { \circ }$ 工况下分别采用MCS与NIPC方法进行了不确定性分析，具体计算方案及所耗费时间如表4所示。

对于MCS方法而言，当所取样本数目足够大时可以认为所模拟的结果能够代表理论结果。本文运用MCS方法对均匀轮廓误差不确定性影响进行了5000次仿真模拟，并以此作为理论结果以验证NIPC方法的有效性。本文分别选取损失均值(MeanLoss)、损失标准差(StdLoss)、静压比均值(Mean $\mathrm { P r } ^ { \mathrm { i } }$ 、静压比标准差（Std $\mathrm { P r }$ ）四个参数作为预测精度评判标准。

![](images/51e606b613c7177d9bbc76b060c7c0d15fa739fea44f8598515fef62e2c5e9e9.jpg)  
图7均匀轮廓误差示意图Fig.7Uniform Profile Error

# 表4 MCS与 NIPC计算方案

表2MCS方法计算函数响应情况  
Table 4 Simulation Schemes ofMCS&NIPC   
图8首先给出了叶型损失预测精度随NIPC阶  

<html><body><table><tr><td>方法</td><td>CFD 计算次数</td><td>耗费时间</td></tr><tr><td>MCS</td><td>1000</td><td>122.68 h</td></tr><tr><td>MCS</td><td>5000</td><td>589.39 h</td></tr><tr><td>NIPC(P = 1)</td><td>2</td><td>14.72 min</td></tr><tr><td>NIPC(P= 2)</td><td>3</td><td>20.39min</td></tr><tr><td>NIPC(P= 3)</td><td>4</td><td>29.44 min</td></tr><tr><td>NIPC(P = 4)</td><td>5</td><td>37.43 min</td></tr><tr><td>NIPC(P = 5)</td><td>6</td><td>44.45 min</td></tr></table></body></html>

数的变化情况，可以看出随着阶数的增加，NIPC方法预测结果逐渐接近于5000次MCS模拟的结果，预测精度逐渐提升；且当阶数为4或5时，对标准差的预测精度基本满足要求。图9给出了叶型静压比预测精度随NIPC阶数的变化情况，同样可以看出，随着阶数的增加，NIPC方法的预测精度逐渐提升；且当阶数为4或5时，基本满足精度要求。本文通过分析进一步验证了NIPC在UQ分析中的优越性，综合考虑预测精度及计算效率性，本文在后续的不确定性分析中，统一选用5点4阶的NIPC方法进行不确定性分析。

围内的型面偏差也必然具有高度随机性。此外，从质量检测角度而言，无论是按照加工制造或气动性能标准，通常要求成批的产品性能不确定性的影响下能够保持一定的合格率即可，亦是从概率统计角度出发对产品进行评价与分析。相对于传统误差影响研究中只关注性能单值的特点，NIPC方法能够同时获得响应均值及标准差，并运用这两个参数对误差影响进行分析能够更合理客观地对误差影响进行评估。

![](images/a007eb2d1f8da678cf5fa4ead8ae87c1e349d5f9718307c536af599c76d165f4.jpg)  
图8损失预测结果对比 Fig.8 Comparison of Predictive Loss

![](images/ac38ff73389b9ae9d8f1683263a164fd8e10123407eb790e8542520b91afb134.jpg)  
图9静压比预测结果对比  
Fig.9 Comparison of Predictive Static Pressure

# 2.3误差影响不确定性分析

从实际加工角度出发，加工过程中存在许多不确定性因素，即使对于合格的加工件在容许公差范

为了获得不同加工轮廓误差对叶型气动性能的影响规律，本文将轮廓误差均值保持为0，而其标准差依次设为0.01、0.02、0.03、0.04、0.05，标准差的逐渐增大反映了叶型加工的不稳定性增大。基于 5点4阶NIPC方法分别对各方案的误差影响进行分析，图10 给出了损失均值(MeanLoss)、损失标准差(StdLoss)、静压比均值(Mean $\operatorname* { P r }$ )、静压比标准中可以看出，随着标准差的逐渐增加，叶型性能整体呈恶化趋势。具体地，叶型损失均值逐渐增加、静压比减小逐渐减小，但这两者的变化很有限，但损失标准差、静压比标准差均产生较大的变化。因此，在对误差影响进行研究时应充分考虑到误差的随机特性，并从均值及标准差两个参数对误差影响进行评估，更多地关注气动性能稳健性。

![](images/710495af41d91f2e7d547930c3e25aa5def6647957559b5cffdbbc635db99c33.jpg)

![](images/98b330815ddd8ce8eddf026dbb6c683448e25f57e5707b625d826129a5ad4aad.jpg)  
图10叶型性能随误差标准差变化情况 Fig.10 Variation of airfoil Performance with Standard Deviation ofProfile Error

# 3结论

基于圆弧形前尾缘CDA叶型，数值研究了加工轮廓误差对叶型气动性能的影响。研究充分考虑了误差的随机特性，并基于5点4阶NIPC对误差影响进行不确定性分析，得到主要结论如下：

1)在加工误差影响不确定性分析方面，NIPC 能够在保证预测精度的前提下，大幅度地提升计算效率；2)轮廓误差的存在使得叶型性能有所恶化，具体表现为性能均值变化不大，但性能稳定性受到较大影响;3）加工误差的影响研究应充分考虑误差的随机特性，误差影响应使用标准差等具有一定的统计意义的变量进行描述，以充分考虑性能稳健性。

# 参考文献

[1]汤振宁．航空发动机叶片数控铣削方法研究[D].沈阳：沈阳工业大学，,2007TANG Zhenning. Aircraft Engine Blade CNC MillingMethod [D]. Shenyang：Shenyang University of Technol-ogy，2007

[2] 刘维伟,李杰光,赵明,等.航空发动机薄壁叶片加工变形误 差补偿技术研究[J].机械设计与制造，2009，47(10)：175- 177 LIU Weiwei,LI Jieguang,ZHAO Ming,et al．Research on the Compensation of Deformation Error in NC Machining of Thin-walled Blades [J]. Journal of Machinery Design and Manufacture,2009,47(10):175-177   
[3]Garzon V E.Probabilistic Aero thermal Design of Compressor Airfoils [D]. Massachusetts:Massachusetts Institute of Technology, 2003   
[4] Roelke R J,Haas JE.The Effect of Rotor Blade Thickness and Surface Finish on the Performance of a Small Axial Flow Turbine [J].Journal of Engineering for Gas Turbines& Power,1983,105(2):377-382   
[5]Suder KL,Chima RV,Strazisar AJ,et al.The Effect of Adding Roughness and Thickness to a Transonic Axial Compressor Rotor [J]. Journal of Turbomachinery,1995, 117(4): 491-505   
[6]陆宏志,吴洋洲,陆利蓬,等.压气机叶片前缘楔形角对前缘 分离泡的影响[J].工程热物理学报，2002,23(5)：569-572 LU Hongzhi,WU Yangzhou,LU Lipeng,et al. The Influence of the Compressor Blade Leading Edge Wedge Angle on the Leading Edge Separation Bubble [J]. Journal of Engineering Thermophysics,2002,23(5):569-572   
[7]曹利新,丛高伟.三元叶轮数控加工刀位规划误差对其气动 力性能影响[J].大连理工大学学报，2009,60(1)：65-70 CAO Lixin, CONG Gaowei. Effect of NC Tool-path Planning Error of Impeller on its Aerodynamic Characteristic[J].Journal of Dalian University of Technology, 2009, 60(1):65-70   
[8]刘业胜，曹玮，郭福水，等.钛合金空心风扇叶片加工误差 对其性能影响的初步分析[J].航空制造技术,2013,59(16): 58-64 LIU Yesheng,CAO Wei,GUO Fushui,et al. Analysis of Effect of Titanium Hollow Fan Blade Manufacturing Process Error on Its Performance [J]. Journal of Aeronautical Manufacturing Technology, 2013,59(16):58-64   
[9] 张伟昊,邹正平,刘火星,等.叶型偏差对整机环境中涡轮性 能的影响[J].工程热物理学报,2010,31(11)：1830-1834 ZHANG Weihao, ZOU Zhengping,LIU Huoxing,et al. Effect of Profile Deviation on Turbine Performance in Whole Engine Environment [J].Journal of Engineering Thermophysics,2010,31(11):1830-1834   
[10]高丽敏,蔡宇桐,李萍,等.叶片加工误差对压气机叶栅气动 性能的影响[J].推进技术，2017,38(3)：525-531 GAO Limin, CAI Yutong,LI Ping,et al. Effect of Blade Machining Error on Compressor Cascade Aerodynamic Performance [J] Journal of Propulsion Technology, 2017, 38(3):525-531   
[11]Garzon V E,Darmofal D L.Impact of Geometric Variability on Axial Compressor Performance [J].Journal of Turbomachinery, 2003,125(4):1199-1213   
[12]Heinze K,Meyer M,Scharfenstein J,et al.Probabilistic CFD Analysis of High Pressure Turbine Blades Considering Real Geometric Effects[C]// ASME Turbo Expo 2013 Turbine Technical Conference and Exposition: San Antonia Texas USA,ASME,2013:1-12   
[13]Paniagua,G.，Dénos,R.，& Almeida,S.Effect of the Hub Endwall Cavity Flow on the Flow-field of a Transonic High-pressure Turbine [J].Journal of Turbomachinery,2004,126(4): 578-586   
[14] Wiener N.The homogeneous chaos [J].American Journal of Mathematics,1938,60(1):897-936   
[15] Cameron R H,Martin W T.The Orthogonal Development ofNon-linear Functional in Series of Fourier-Hermite Functional [J].Journal of Annals of Mathematics,1947, 48(2):395-392   
[16]Montomoli F,Carnevale M,D'Ammaro A,et al.Uncertainty Quantification in Computational Fluid Dynamics and Aircraft Engines [J].Springerbriefs in Applied Sciences& Technology,2015,14(3):274-282