# 红外成像灰度随距离变化的李群表达

李晨曦1,2,3，史泽林1,，刘云鹏1,3(中国科学院沈阳自动化研究所1100162中国科学院大学 北京 100049中国科学院光电信息处理重点实验室 沈阳110016)

摘要：大气对红外辐射传输的影响引起的红外成像灰度变化，是红外目标跟踪应用需要应对的问题。本文的研究目的是对红外成像灰度变化规律进行李群建模，对设计高效、鲁棒的目标跟踪算法有重要意义。首先分析了红外辐射传输模型，并结合红外成像机理，得到红外成像灰度变化模型。进一步从理论上证明了大气影响下红外成像灰度变化规律符合李群结构，提出了红外图像灰度动态变化的一种非欧数学表征。最后根据红外成像灰度变化模型对不同环境下采集到的外场实验数据进行拟合，回归分析结果表明了该模型的准确性，进而说明了本文对红外成像灰度变化规律进行李群表达的合理性。

关键词：大气辐射传输；李群；红外辐射；目标跟踪中图文分类号：O432.1文献标识码：A

# Lie group representation of infrared imaging grayscale variation with distance

Li Chen-xi1,2.3,Shi Ze-lin1,3,Liu Yun-peng1,3 (l Shenyang Institute of Automation, Chinese Academy of Sciences, Shenyang 110016 ² University of Chinese Academy of Sciences, Beijing 100049 3 Key Laboratory of Optical-Electronics Information Processing, Chinese Academy of Sciences, Shenyang 110016)

Abstract: The infrared imaging grayscale variation caused by the influence of atmosphere on infrared radiation transmission is a problem that infrared target tracking application needs to cope with. The object of this paper is to model the law of infrared imaging grayscale variation in Lie group, which is important to design an efcient and robust target tracking algorithm.This paper firstly analyzes the infrared radiation transmission model,and then derives the brightness model of infrared imaging by considering the mechanism of infrared imaging. Furthermore,it is theoretically proved that the infrared imaging grayscale variation caused by the atmosphere obeys to the Lie group structure,and a non-Euclidean mathematical representation of the infrared imaging grayscale variation is proposed. Finally, according to the infrared imaging grayscale variation model, the field experimental data collected under different environments are fited,and the regression analysis results demonstrate the correctness of the model, which validates the rationality of the Lie group representation of the infrared imaging grayscale variation.

Key words: Atmosphere radiation transmission; Lie group; Infrared radiation; Target tracking

# 0引言

随着红外成像技术的发展，红外探测器在民用和军事领域获得了广泛应用。探测目标的红外辐射特性经过大气到达探测器，在传输过程中红外辐射受到大气两方面的影响。一方面，目标红外辐射会被传输路径上的大气成分的吸收和散射而衰减。另一方面，传输路径上的大气成分本身发出红外辐射被红外探测器接收到，使红外辐射增强。在这两方面的影响下，辐射传输距离的改变导致目标的成像灰度发生变化，对红外目标的探测、识别、跟踪带来不利影响。本文对红外目标跟踪应用中大气辐射传输影响下目标成像灰度变化规律进行研究。

现有研究主要根据大气红外辐射传输理论对目标的红外辐射进行计算以及红外图像的仿真模拟。例如，刘连伟等人[1]对无人机的红外辐射进行建模，生成红外序列图像。林娟等人[2]对舰船排气羽流的红外辐射特性进行了仿真计算。郭立红等人[3提出了一种提高目标红外辐射特性测量精度的方法。更早的，韩玉阁等人[4]通过LOWTRAN7软件对大气对红外辐射传输的影响进行了仿真验证，并给出红外序列图像仿真结果。探测距离的改变导致接收到的目标红外辐射发生变化。田昌会等人[5分析了这种变化对目标与背景对比度计算产生的影响。易亚星等人[6]对红外探测器与目标距离越近，目标灰度越低这一现象进行分析，指出了大气背景辐射对目标灰度的影响。

在目标跟踪过程中图像的几何变化（针对近似平面物体）一般可以用仿射群或射影群来表征。这些几何变换群具有非欧李群(Lie group)结构。文献[7，8]根据几何变换的李群结构分别设计了逆复合（IC,InverseComposition）和二阶优化（ESM,Efficient Second-orderMinimization）算法进行图像匹配。文献[9]根据可见光图像的几何变换和灰度变换的李群结构设计了高效的适应光照变化的图像匹配算法。

对于红外目标来说，大气辐射传输影响造成目标跟踪过程中成像灰度随距离的变化规律是否符合李群结构是一个值得讨论的问题。如果这种变化规律能够用李群来建模，那么据此可以设计更加快速鲁棒的跟踪算法。本文结合探测器成像机理，证明大气影响下红外成像的灰度变化的确服从李群规律，并建立目标成像灰度变化李群模型。最后利用不同环境下采集到的真实数据对模型进行线性回归分析以验证结论的合理性。

# 目标成像灰度变化的李群表达

首先分析大气对红外辐射传输的影响，得到目标辐射亮度随距离变化公式。然后结合红外探测器成像机理，给出目标成像灰度随距离变化关系。最后对目标成像灰度变化规律进行李群表达，并给出其李代数参数化形式。

# 1.1大气对红外辐射传输的影响

大气成分非常复杂，主要包括氮气，氧气，水汽，二氧化碳，气溶胶等。气体分子对红外辐射的吸收以及气溶胶颗粒对红外辐射的散射造成目标红外辐射的衰减。传输路径上的大气本身发出的红外辐射被红外探测器接收，造成红外辐射信号的增强。下面对这两方面的影响进行综合分析。

对于短时间的跟踪应用来说，可以假设大气是均质恒温的。在此假设下讨论分析会得到简化。

![](images/b77eb86725dbd52a24fc6dfc16f55e83ee4f8217bba50b52f0aaf86ebd757b07.jpg)  
图1：大气辐射传输示意图。  
Fig.1: Sketch map of atmospheric radiation transmission.

设目标固有光谱辐射亮度为 $I _ { \lambda } ( 0 )$ ，在大气中经过 $s$ 距离的传输后，目标光谱辐射亮度为$I _ { \lambda } ( s )$ 。下面我们根据大气的影响推导 $I _ { \lambda } ( s )$ 。目标在大气中的辐射传输如图1所示。由于大气的吸收和散射效应，经过 $d s$ 距离后辐射变化量$d I _ { \lambda } ( s )$ 为

$$
d I _ { \lambda } ( s ) = - \mu _ { \lambda } I _ { \lambda } ( s ) \cdot d s
$$

式中大气的光谱衰减系数为 $\mu _ { \lambda }$ ，在上面的假设下与路径无关；负号表示辐射衰减。考虑到传输

路径上大气的辐射及多次散射效应，辐射变化量$d I _ { \lambda } ( s )$ 还需要加上增强项，式(1)改为

$$
d I _ { \lambda } ( s ) = - { \mu } _ { \lambda } I _ { \lambda } ( s ) \cdot d s + { \mu } _ { \lambda } J ( s ) \cdot d s
$$

上式中，等号右边第一项表示辐射衰减项，第二项表示辐射增强项。例如，在 $3 { \sim } 5 \mu m$ 波段内，二氧化碳的吸收作用占主要地位，在 $8 { \sim } 1 4 \mu m$ 波段内，水汽的吸收作用占主要地位。 $J ( s )$ 为大气源函数，引起接收辐射的增强。 $J ( s )$ 一般与大气的温度有密切关系，所以其随高度的变化而变化。本文假设大气是均质恒温的，尤其是在本文实验条件，考虑水平探测路径，高度不变，从而可以认为它与路径无关，在文献[10]中为大气的普朗克函数。求解(2)式可以得到

$$
I _ { \lambda } ( s ) = I _ { \lambda } ( 0 ) \mathrm { e x p } ( - \mu _ { \lambda } s ) + J ( 1 - \mathrm { e x p } ( - \mu _ { \lambda } s ) )
$$

上式即为目标光谱辐射亮度在大气中的传输公式。

# 1.2红外成像灰度变化关系

上一节分析了大气对目标的红外辐射传输的影响。本节结合红外探测器成像机理来分析目标的成像灰度变化。红外探测器成像单元接收到的目标辐射亮度由(3)式给出，那么所激发的信号电压[3,6]为

$$
V ( s ) = \int _ { \lambda _ { 1 } } ^ { \lambda _ { 2 } } M ( \lambda ) I _ { \lambda } ( s ) d \lambda
$$

式中 $M ( \lambda )$ 为成像单元的光谱电压响应率。目标成像灰度为

$$
L ( s ) = a \cdot V ( s ) + b = \int _ { \lambda _ { 1 } } ^ { \lambda _ { 2 } } a \cdot M ( \lambda ) I _ { \lambda } ( s ) d \lambda + b
$$

式中 $a$ 为显示增益系数， $\textit { \textbf { b } }$ 为显示白平衡基数。假设在波段 $\lambda _ { 1 } \sim \lambda _ { 2 }$ 内成像单元的光谱电压效应率为常数 $M$ 。通过平均当量参数法[1将光谱辐射亮度 $I _ { \lambda } ( s )$ 转化为波段辐射亮度 $I ( s )$ ，去掉光谱符号 $\lambda$ ，得到

$$
I ( s ) = I ( 0 ) \exp ( - \mu s ) + J ( 1 - \exp ( - \mu s ) )
$$

$\mu$ 为波段 $\lambda _ { 1 } \sim \lambda _ { 2 }$ 内大气平均衰减系数。将(6)式代入(5)，去掉积分号得到

$$
L ( s ) = a M \cdot ( I ( 0 ) \mathrm { e x p } ( - \mu s ) + J ( 1 - \mathrm { e x p } ( - \mu s ) ) ) + b
$$

上式为距离 $s$ 处目标成像灰度模型，描述了成像灰度与距离的变化关系。

# 1.3目标成像灰度变化建模及其李群结构

本节根据目标成像灰度模型(7)来考察任意不同距离处目标成像灰度的变化规律。将式(7)写成矩阵形式

$$
{ \begin{array} { r } { { \left[ \begin{array} { l } { L ( s ) } \\ { 1 } \end{array} \right] } = { \left[ \begin{array} { l l } { a M } & { b } \\ { 0 } & { 1 } \end{array} \right] } { \left[ \begin{array} { l l } { \exp ( - \mu s ) } & { J ( 1 - \exp ( - \mu s ) ) } \\ { 0 } & { 1 } \end{array} \right] } . } \\ { { \left[ \begin{array} { l } { I ( 0 ) } \\ { 1 } \end{array} \right] } } \end{array} }
$$

在上式中令 $s = 0$ ，得到

$$
{ \left[ \begin{array} { l } { L ( 0 ) } \\ { 1 } \end{array} \right] } = { \left[ \begin{array} { l l } { a M } & { b } \\ { 0 } & { 1 } \end{array} \right] } { \left[ \begin{array} { l } { I ( 0 ) } \\ { 1 } \end{array} \right] }
$$

结合(8)和(9)两式，得到

$$
{ \begin{array} { r } { { \left[ { \begin{array} { l } { L ( s ) } \\ { 1 } \end{array} } \right] } = { \left[ \begin{array} { l l } { \exp ( - \mu s ) } & { ( a M J + b ) ( 1 - \exp ( - \mu s ) ) } \\ { 0 } & { 1 } \end{array} \right] } . } \\ { { \left[ { \begin{array} { l } { L ( 0 ) } \\ { 1 } \end{array} } \right] } } \end{array} }
$$

上式为目标零视距下成像灰度 $L ( 0 )$ 与距离 $s$ 处的目标成像灰度之间的关系。可以看出灰度变化关系与目标辐射亮度变化关系(6)形式类似，只不过是原来的大气源函数 $_ { J }$ 由常数 $a M J + b$ 替代。在下面的叙述中，记 $B = a M J + b$ 。容易验证任意不同距离处的目标成像灰度变化都有(10)的形式，即

$$
\begin{array} { r } { \left[ \begin{array} { c } { L ( s _ { 2 } ) } \\ { 1 } \end{array} \right] = \left[ \begin{array} { c c } { \exp ( - \mu \Delta s ) } & { B ( 1 - \exp ( - \mu \Delta s ) ) } \\ { 0 } & { 1 } \end{array} \right] . } \\ { \left[ \begin{array} { c } { L ( s _ { 1 } ) } \\ { 1 } \end{array} \right] } \end{array}
$$

式中， $\Delta s = s _ { 2 } - s _ { 1 }$ 为距离差。

根据式(11)定义集合

$$
\begin{array} { r l } & { A t m I = } \\ & { \{ \mathbf { P } ( s ) = [ \begin{array} { c c } { \exp ( - \mu s ) } & { B ( 1 - \exp ( - \mu s ) ) } \\ { 0 } & { 1 } \end{array} ] \} s \in \mathbb { R } \} } \end{array}
$$

集合 $A t m I$ 只与大气和探测器成像机理有关，与目标辐射无关。可以证明该集合在矩阵乘法运算下满足李群定义[12]，因此大气与成像机理的综合影响作用满足李群结构。

证明：集合AtmI在矩阵乘法运算下为李群。

证：首先， $\mathbf { P } ( 0 ) = { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] }$ 为单位元。通过计算容易得到 $\mathbf { P } ( \alpha ) \mathbf { P } ( \beta ) = \mathbf { P } ( \alpha + \beta )$ ，因此满足群的封闭性。另外，计算得到

$$
\begin{array} { r l } & { ( \mathbf { P } ( \alpha ) \mathbf { P } ( \beta ) ) \mathbf { P } ( \gamma ) = \mathbf { P } ( \alpha + \beta + \gamma ) } \\ & { = \mathbf { P } ( \alpha ) ( \mathbf { P } ( \beta ) \mathbf { P } ( \gamma ) ) } \end{array}
$$

，从而群的结合律满足。而$\mathbf { P } ( \alpha ) \mathbf { P } ( - \alpha ) = \mathbf { P } ( - \alpha ) \mathbf { P } ( \alpha ) = \mathbf { P } ( 0 )$ ，所以 $\mathbf { P } ( - \alpha )$ 与${ \bf P } ( \alpha )$ 互为逆元。因此集合 $A t m I$ 满足群的定义，并且是仿射李群 $G A ( 1 ) = \left\{ { \left[ \begin{array} { l l } { a } & { b } \\ { 0 } & { 1 } \end{array} \right] } { \left| { a , b \in \mathbb { R } , a \neq 0 } \right. } \right\}$ 的子群，从而集合 $A t m I$ 在矩阵乘法运算下为李群。证毕。

# 1.4李群 $A t m I$ 的季代数及群作用

AtmI是一个一维李群，其李代数为

$$
a t m i = \{ \mathbf { A } ( s ) = [ { - \mu s \quad B \mu s } ] \} s \in \mathbb { R } \}
$$

atmi是一个一维向量空间，其基为$\left[ { \begin{array} { l l } { - \mu } & { B \mu } \\ { 0 } & { 0 } \end{array} } \right]$ AtmI与atmi通过指数映射联系，$\forall \mathbf { P } ( s ) \in A t m I \ ,$ （204号

$$
\begin{array} { l } { \mathbf { P } ( s ) = \left[ \begin{array} { c c } { \exp ( - \mu s ) } & { B ( 1 - \exp ( - \mu s ) ) } \\ { 0 } & { 1 } \end{array} \right] } \\ { \mathbf { \Phi } = \exp \left( \left[ \begin{array} { c c } { - \mu s } & { B \mu s } \\ { 0 } & { 0 } \end{array} \right] \right) } \end{array}
$$

最后一项的指数运算为矩阵指数。通过李群与李代数的指数映射关系建立了 $A t m I$ 的参数化表示。

定义李群 $A t m I$ 的元素 $\mathbf { P } ( s )$ 对目标成像灰度$L$ 的群作用为

$$
\mathbf { P } ( s ) \circ L = \exp ( - \mu s ) L + B ( 1 - \exp ( - \mu s ) )
$$

上式表示经过距离 $s$ 后，目标成像灰度的变化规律。根据李群的性质，容易证明$\mathbf { P } ( s _ { 2 } ) \circ ( \mathbf { P } ( s _ { 1 } ) \circ L ) = ( \mathbf { P } ( s _ { 2 } ) \mathbf { P } ( s _ { 1 } ) ) \circ L = \mathbf { P } ( s _ { 2 } + s _ { 1 } ) \circ L$ 这表明先经过距离 $s _ { 1 }$ 再经过距离 $s _ { 2 }$ 后的成像灰度与经过距离 $s _ { 1 } + s _ { 2 }$ 是一样的。

# 2 实验验证

本文通过外场采集到的红外图像数据来验证所提模型的合理性。红外成像灰度变化规律的李群表达模型(12)的合理性建立在红外成像灰度变化关系式(10)上，因此只需对(10)的准确性进行验证即可说明对成像灰度变化规律李群表达的合理性。这里通过对采集到的真实数据进行回归分析来验证。

# 2.1实验设置

探测目标是一座未完工的楼房，拍摄过程中红外探测器远离目标，并记录距离信息，得到不同距离下探测目标的成像。实验使用法国Sofradir（索芙拉蒂）MWMARS中波红外热像仪，波段为 $3 { \sim } 5 \mu m$ 。为了验证不同环境下模型的准确性，在5月份（环境温度为 $2 0 ^ { \circ } \mathrm { C }$ ）采集了两组数据，在7月份（环境温度为 $2 8 ^ { \circ } \mathrm { C }$ ）采集了一组数据，这样得到三组实验数据。图2给出不同距离处采集到的红外图像的示例。值得指出的是，模型验证过程使用的是原始14位数据，即没有经过调光处理的数据。为了显示，在图2中做了调光处理。从图像中选取两种灰度差异明显的材质。为了便于观察，对选取材质的细节做了放大，如图像中箭头所示。在放大的区域，白色方框为材质1，黑色方框为材质2。

# 2.2验证方法

根据(10)式，材质1与材质2的灰度随距离的变化关系为：

$L _ { i } ( s ) \mathrm { = } L _ { i } ( 0 ) \exp ( - \mu s ) + B ( 1 - \exp ( - \mu s ) )$ (17)式中 $i = \{ 1 , 2 \}$ 表示材质下标； $s$ 表示红外探测器与探测对象之间的距离（单位：米)。通过采集到的数据对(17)式进行拟合来考察该变化关系的合理性。材质初始灰度 $L _ { \ i } ( 0 )$ 、大气衰减系数 $\mu$ 以及常数 $B$ 是未知参数。

首先对这两种材质的灰度差进行回归分析，这样可以将非线性回归问题转化为线性回归问题，便于进行显著性水平分析。令$\Delta L ( s ) = L _ { 1 } ( s ) - L _ { 2 } ( s )$ ，那么

$$
\Delta L ( s ) = \Delta L ( 0 ) \exp ( - \mu s )
$$

对上式取对数，得到

$$
\ln \Delta L ( s ) = \ln \Delta L ( 0 ) - \mu s
$$

式中 $\ln \Delta L ( s )$ 与 $s$ 为已知量， $\ln \Delta L ( 0 )$ 与 $\mu$ 为待回归参数。根据采集到的数据对(19)式进行线性回归得到参数 $\mu$ 。

然后，将(17)式写为下面的形式：

$$
L _ { i } ( s ) { = } ( L _ { i } ( 0 ) - B ) \exp ( - \mu s ) { + } B
$$

式中 $L _ { i } ( s )$ 与 $\exp ( - \mu s )$ 为已知量， $( L _ { i } ( 0 ) - B )$ 与 $B$ 为待回归参数。上式同样是一个线性回归问题，根据采集到的数据进行线性回归，得到参数$L _ { i } ( s )$ 和 $B$ 。

![](images/1680c878bc819dfe48305921da8c550b1ef3c29c9ca6b752384b402e697ef365.jpg)  
Fig.2:Infrared images collected at different distances.White box narks material1,and black box marks material 2 in the enlarged

# 图2:不同距离采集到的红外图像。放大区域中白色方框标注材质1，黑色方框标注材质2。

region.

# 2.3实验结果及分析

对采集到的三组数据进行线性回归分析。图3给出5月份第一组数据回归结果（图中显示原始数据的关系)，图4给出5月份第二组数据回归结果，图5给出7月份数据回归结果。从图中可以看出数据拟合效果很好。

为了定量地对回归结果进行评估，文中给出了回归结果的相关系数和P值，三组数据的分析结果分别见表1、表2和表3。相关系数反应了变量间的线性相关程度，该值越接近1，说明相关程度越高。P值是针对假设H0：假设两变量无线性相关而言的。一般P值小于0.05，就拒绝假设H0，说明两变量有线性相关关系。从三个表中可以看出数据拟合的相关系数均大于0.92，并且表示显著性水平的P值远小于0.05，从统计学意义上说明了模型(17)的合理性。另外也说明不同环境下模型(17)的通用性。

需要指出的是，模型(17)中的参数 $B$ 以及大气衰减系数 $\mu$ 一般与大气参数（温度、相对湿度和气体分子密度等）有关。本文实验均通过车载探测器获得，每组实验数据的获取均在3分钟内完成，时间跨度较小，可以认为大气参数不变，满足本文关于大气均质恒温的假设。

![](images/62bba35ce5e8393eeb8a1bab152c8945b33cbd4c05eb0cb970df3a224d8e735b.jpg)  
图3:第一组数据回归结果。(a)两种材质灰度差的回归结果；(b)材质1的回归结果；(c)材质2的回归结果。

![](images/2f63556248817dcb14148dff24e4f3a440c24377063a048ebb8de0b63d590fd6.jpg)  
Fig.3:Regreslsfseofata.(agresultfgaaledireateals;gresultf material1:and(c) regression result of material 2.   
  
图4：第二组数据回归结果。(a)两种材质灰度差的回归结果；(b)材质1的回归结果;(c)材质2的回归结果。

ig.4:Regreslsfodata.olofaleieateals;(rol

![](images/3ddfa20122b134d2bc1a37a6b1eff76bcbeb08ef54d00ac682059c69600d9c2c.jpg)  
图5：第三组数据回归结果。(a)两种材质灰度差的回归结果；(b)材质1的回归结果;(c)材质2的回归结果。  
Fig.5:Regresltsfdata.eoltfatelsultf material 1;and (c) regression result of material 2.

Tab.1: Evaluation results of the first data set   
表2：第二组数据评估结果  

<html><body><table><tr><td>因变量</td><td>相关系数</td><td>P值</td></tr><tr><td>ln △L(s)</td><td>0.98</td><td>1.05e-17</td></tr><tr><td>L(s)</td><td>0.95</td><td>1.29e-13</td></tr><tr><td>L(s)</td><td>0.96</td><td>2.48e-14</td></tr></table></body></html>

表1：第一组数据评估结果  
表3：第三组数据评估结果  

<html><body><table><tr><td>因变量</td><td>相关系数</td><td>P值</td></tr><tr><td>ln △L(s)</td><td>0.96</td><td>2.35e-15</td></tr><tr><td>L(s)</td><td>0.94</td><td>4.11e-13</td></tr><tr><td>L(s)</td><td>0.95</td><td>1.51e-13</td></tr></table></body></html>

Tab.2:Evaluation results of the second data set   
Tab.3:Evaluationresultsofthethirddataset   

<html><body><table><tr><td>因变量</td><td>相关系数</td><td>P值</td></tr><tr><td>ln △L(s)</td><td>0.96</td><td>2.32e-16</td></tr><tr><td>L(s)</td><td>0.92</td><td>6.62e-13</td></tr><tr><td>L(s)</td><td>0.95</td><td>1.61e-15</td></tr></table></body></html>

# 3结论

本文详细分析了大气对红外辐射传输的影响，并结合红外探测器的成像机理得到大气影响下红外成像灰度变化模型。从该模型中抽象出大气与探测器成像机理的作用，理论上证明了该作用满足李群结构，得到红外成像灰度变化的李群表达，并给出其李代数参数化。为设计快速鲁棒的红外目标跟踪算法奠定理论基础。

为了验证红外成像灰度变化李群表达的合理性，通过采集到的不同环境下的真实数据对红外成像灰度模型进行回归分析。文中利用两种材质将非线性回归模型转化线性回归模型，便于对回归结果做定量分析。结果表明，回归分析得到的相关系数接近1，显著性P值远小于0.05，验证了红外成像灰度变化模型的准确性，从而表明本文对红外成像灰度变化李群表达的合理性。下一步工作为将得到的红外成像灰度变化李群引入到红外目标跟踪算法中。

# 参考文献

[1]Liu Lianwei, Yang Miaomiao, Zou Qianjin,Yao Mei,Wang Min,Xu Zhenling.UAV infrared radiation modeling and image simulation [J]. Infraredand Laser Engineering. 2017, 46(02):214-220.(in Chinese)

刘连伟,杨淼淼,邹前进,姚梅,王敏,许振领无人机红外辐射建模与图像仿真[J].红外与激光工程.2017,46(06):214-220.

[2] Lin Juan,Bao Xingdong，Wu Jie,Dong Yanbing.Computation of infrared radiation from ship exhaust plumes[J]. Infrared and Laser Engineering. 2016,45(09):86-91. (in Chinese)

林娟,包醒东,吴杰,董雁冰．舰船排气羽流红外辐射特性计算研究[J].红外与激光工程,2016,45(09):86-91.

[3] Guo Li-hong,Guo Han-zhou,Yang Ci-yin,

Li Ning. Improvement of radiation measurement precision for target by using atmosphere-corrected coefficients [J]. Optics and Precision Engineering. 2016,24(08): 1871-1877. (in Chinese)

郭立红，郭汉洲，杨词银，李宁．利用大气 修正因子提高目标红外辐射特性测量精度 [J]. 光学精密工程.2016,24(08):1871-1877. [4] Han Yu-ge,Xuan Yi-min. Effect of atmospheric transmission on IR radiation feature of target and background [J]. Journal of Applied Optics,2002,23(06):8-11. (in Chinese) 韩玉阁，宣益民．大气传输特性对目标与背 景红外辐射特性的影响 [J]．应用光学．2002, 23(06):8-11. [5] Tian Changhui, Yang Baiyu, Cai Ming, et al. Effect of atmospheric background on infrared target detection [J]. Infrared and Laser Engineering. 2014,43(02):439-441. (in Chinese) 田昌会，杨百愚，蔡明，范琪，等．大气背 景对红外目标探测的影响 [J].红外与激光工 程，2014，43(02):439-441. [6] Yi Yaxing，Yao Mei,Wu Junhui,Le Kaiduan.Factors of the detected luminance of an infrared target [J]. Infrared and Laser Engineering. 2014,43(01):13-18. (in Chinese) 易亚星，姚梅，吴军辉，乐开端．影响红外 目标探测亮度的因素 [J]．红外与激光工程， 2014， 43(01):13-18. [7] Baker, S. and I. Matthews, Lucas-Kanade 20yearson:Aunifyingframework[J]. International Journal of Computer Vision. 2004, 56(03): 221-255. [8]Benhimane，S.andE.Malis, Homography-based2Dvisualtrackingand servoing [J]. International Journal of Robotics Research. 2007,26(07): 661-676. [9] Bartoli，A.，Groupwise Geometric and Photometric Direct Image Registration [J]. Ieee Transactions on Patern Analysis and Machine Intelligence, 2008.30(12): p. 2098-2108. [10]K.N.LIOU.AnIntroduction to Atmospheric Radiation (Second Edition） [M]. Beijing:China Meteorological Press.2004. (in Chinese)

K.N.LIOU.大气辐射导论[M].北京：气象出版社，2004.

[11] Tan Heping,Xia Xinlin,Lin Linhua, et al. Numerical Calculation of Infrared Radiation and Transmission CalculationofThermal Radiation[M]. Harbin:Harbin Instituteof Technology Press.2006.

谈和平，夏新林等．红外辐射特性与传输的数值计算:计算热辐射学[M]．哈尔滨：哈尔滨工业大学出版社，2006.

[12]B.Hall.Lie Groups,Lie Algebras,and Representations:An Elementary Introduction [M. Springer, 2004.