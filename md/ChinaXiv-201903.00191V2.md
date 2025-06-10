# 论文

# 等离子体非线性手性：有螺湍流态及呼吸子

陈鹏1，杨焱12，朱建州1\*

1.南京市高淳区速诚基础与交叉科学研究中心,高淳，南京211316;2.中国科学院力学研究所高温气动实验室，北京100190\*联系人,E-mail: jz@ sccfis.org

收稿日期：2019-?????；接受日期：2019-???？？;田园学派基金（编号:27182818)；国家自然科学基金(编号:11672102)资助项目摘要等离子体湍流（如太阳风）中体现的（矢端图）螺旋现象和信号（近似）谐振现象并不一定表示线性波动行为。不同环境下等离子体可以有不同的动力学特征，容许存在各种非线性结构。这里讨论在一定时空范围内与线性螺旋波表现类似的由单手性主导的湍动涡模态和呼吸子。前者先通过回顾最近利用扩展磁流体模型统计解特征研究太阳风中的建议得以说明；后者的具体例证还是一个开放的问题，但是我们列举各种来自水波、等离子体和玻色-爱因斯坦凝聚的信息来说明太阳风中应该存在这样的结构。

关键词有螺湍流，太阳风等离子体，呼吸子，回旋波，等离子体流动控制

PACS: 47.27.Rc, 47.27.-i, 52.30.?q,52.35.Ra, 02.30.Ik

# 1引言

螺旋是三维运动的基本模态，这由速度场的数学表示所决定[1]。以简单三维单连通区域内的场为例，运动分为左旋，右旋和无旋三部分，没有别的神秘之处。如何选择和组织出手性结构却是动力学的。等离子体中，可以表现为螺旋波、螺旋涡流和磁力线扭曲缠绕，等等，既有局部又有全局特征。因此，局部螺度和全局螺度在湍流动力学中是基础性、内容丰富而又涵义深刻的[2,3]。

太阳物理磁流体尺度问题研究中磁螺度和电流螺度的相关手征性是一个热点问题（如，张洪起[4]、Chen[5]、Bi等[6]、欧阳雨等[7]，以及本专辑中高裕[8]、徐海清[9]和杨尚斌[10]文章及其中参考文献)。本文主要考虑亚离子尺度动力学。

我们通过单手性主导的非线性涡模态和呼吸子两个典型例子讨论文献中通常解释为（线性）螺旋波观测现象[11]的可能不同解释，也讨论一些湍流理论中以线性波为基础的不必要和/或不充分性，及其它更合理的可能。我们的分析有些具有较严格的基础；有些讨论则尚无具体例证，但并不比相应的线性波论据更不严格。

我们先从具体的扩展磁流体（extendedMHD:XMHD）基础统计动力学出发，然后借其针对太阳风亚离子尺度动力学相关具体案例进行分析，最后更加开放地讨论太阳风中的呼吸子（breather)。

在聚焦等离子体和太阳风之前，我们先指出近年来关于不同力学和物理系统中的呼吸子的研究已经很多[12]，涉及领域包括水波，玻色-爱因斯坦凝聚和（纳米）光学等。文献[13]包含了太阳物理相关等离子体动力学中二维旋转形态常规非周期孤立波的详细介绍。

# 2XMHD手性与太阳风湍流

文献[14]中部分内容针对Meyrand&Galti-er[15]和Abdhamid,Lingam&Mahajan[16]在他们的工作中严重依赖于线性波论据的讨论进行了分析。这是目前对等离子体亚离子尺度非线性手性问题的一个最佳说明例子。此问题结论很简单，但是细节非常微妙。相关讨论不可避免地比较技术性，下面我们稍简化说明，但是也不得不给出足够的细节。

引入焓ⅡI，常规磁场和矢势 $\nabla \times \boldsymbol { A } = \boldsymbol { B }$ ， $\mathcal { B } =$ $\boldsymbol { B } { + } d _ { e } ^ { 2 } \nabla { \times } ( \nabla { \times } \boldsymbol { B } )$ ，矢量势 $\nabla \times \mathcal { \mathcal { H } } = \mathcal { B }$ ，以及电子 $( d _ { e } )$ 和离子！ $( d _ { i }$ ）趋肤深度。考虑理想正压XMHD系统（采用Alfvenic单位）：

$$
\begin{array} { r l r } & { } & { \partial _ { t } \rho = - \nabla \cdot ( \rho \boldsymbol { u } ) , } \\ & { } & { \partial _ { t } \boldsymbol { u } = - \nabla \left[ \Pi + \boldsymbol { u } ^ { 2 } / 2 + ( d _ { e } \nabla \times \boldsymbol { B } ) ^ { 2 } / ( 2 \rho ^ { 2 } ) \right] + } \\ & { } & { + \boldsymbol { u } \times ( \nabla \times \boldsymbol { u } ) + ( \nabla \times \boldsymbol { B } ) \times \mathcal { B } / \rho , } \\ & { } & { \partial _ { t } \mathcal { B } = \nabla \times ( \boldsymbol { u } \times \mathcal { B } ) - d _ { i } \nabla \times \left[ ( \nabla \times \boldsymbol { B } ) \times \mathcal { B } / \rho \right] + } \\ & { } & { + d _ { e } ^ { 2 } \nabla \times \left[ ( \nabla \times \boldsymbol { B } ) \times ( \nabla \times \boldsymbol { u } ) / \rho \right] . } \end{array}
$$

取极限 $d _ { i } \to 0$ 可得惯性磁流体模型（inertialMHD）,这被认为在亚电子（sub-electron）尺度的磁层和太阳风等离子体中相关；取 $d _ { e } \to 0$ 就得到熟悉的霍尔磁流体（HaIlMHD）模型；而理想单流体磁流体形式地可通过同时取 $d _ { e }$ 和 $d _ { i }$ 趋于零得到。

这个方程还可写为两个广义涡量冻结于两个流体（Lie携带[3]）的形式，相应地有两个广义螺度守恒定理：它们不仅是卡西米尔(Casimir)不变量，而且是对于伽辽金（Galerkin）截断鲁棒地保持的，所以必扮演重要的动力学角色。比如，螺度可导致湍流中的单手性主导态。上述讨论相关的更多细节可见于[14]及其参考文献。开篇提到的运动分解对应于将变量（如，速度） $\boldsymbol { v }$ 通过旋度算子 ${ \cal C } = ( - \nabla ^ { 2 } ) ^ { - 1 / 2 } \nabla \times$ 的本征态展开。比如，考虑不可压缩 ${ \pmb u } ^ { \pm }$ 有广义傅里叶展开 $\begin{array} { r } { \boldsymbol { u } ^ { s } = \sum _ { n } \hat { \boldsymbol { u } } _ { n } ^ { s } \phi _ { n } ^ { s } } \end{array}$ ， $\nabla \times \phi _ { n } ^ { s } = s \lambda _ { n } \phi _ { n } ^ { s }$ (Beltramity), ${ \lambda } _ { n } > 0$ 这里， $s = \pm$ 表征手性（相对论量子力学中手征算子和螺度算子是独立的，我们的经典问题中不作区分。）在周期盒子 $\mathcal { D } = [ 0 , 2 \pi ) ^ { 3 }$ （或说轮胎 $\mathcal { T } ^ { 3 }$ ）内，对于无散的 $\boldsymbol { v }$ ，我们有标准傅里叶展开

$$
\pmb { v } = \sum _ { s } \pmb { v } ^ { s } = \sum _ { \pmb { k } , s } \hat { \pmb { v } } ^ { s } ( \pmb { k } ) e ^ { i \pmb { k } \cdot \pmb { r } } = \sum _ { \pmb { k } , s } \hat { \nu } ^ { s } ( \pmb { k } ) \hat { \pmb { h } } _ { s } ( \pmb { k } ) e ^ { i \pmb { k } \cdot \pmb { r } } ,
$$

其中 $\hat { i } ^ { 2 } ~ = ~ - 1$ ， $\hat { i } \pmb { k } \times \hat { \pmb h } _ { s } ( \pmb k ) = s k \hat { \pmb h } _ { s } ( \pmb k ) , \hat { \pmb h } _ { s } ( - \pmb k ) =$ $\hat { h } _ { s } ^ { * } ( k ) \ = \ \hat { h } _ { - s } ( k )$ 以及 $\hat { \pmb { h } } _ { s _ { 1 } } ( \pmb { k } ) \cdot \hat { \pmb { h } } _ { s _ { 2 } } ^ { * } ( \pmb { k } ) = \delta _ { s _ { 1 } , s _ { 2 } }$ 。对于 $\boldsymbol { k }$ （类似地 $\pmb { p }$ 和 $\pmb q$ ）的手性表为 $s _ { k }$ 。再不引起混淆时，我们也会采用如下不言自明的简化表示 $\hat { v } _ { k } ^ { s _ { k } }$ 。螺旋基可取 $\hat { h } _ { s } ( \boldsymbol { k } ) = ( s \hat { i } l + l \times k / k ) / ( \sqrt { 2 } l )$ ，其中 $\iota$ 任意模为l，垂直于 $k$ 的矢量。

# 2.1线性回旋波之外的非线性手性

Meyrand和Galtier[15]用如下线性波色散关系论证霍尔磁流体的手性

$$
\hat { \pmb u } ( \pmb k ) = - \frac { B _ { 0 } k _ { | | } } { \omega } \hat { \pmb b } ( \pmb k ) , \hat { \pmb a } ( \pmb k ) = \frac { s } { k } \hat { \pmb b } ( \pmb k ) = \frac { s \hat { i } \pmb k \times \hat { a } ( \pmb k ) } { k }
$$

其中 $\boldsymbol { B } = B _ { 0 } + b , \boldsymbol { b } = \nabla \times \boldsymbol { a }$ and $B _ { 0 } k _ { \parallel } = \boldsymbol { B } _ { 0 } \cdot \boldsymbol { k }$ .借助

$$
\sigma _ { m } = \frac { \hat { a } ( k ) \cdot \hat { b } ^ { * } ( k ) + c . c . } { 2 | \hat { a } ( k ) | | \hat { b } ( k ) | } , ~ \sigma _ { c } = \frac { \hat { a } ( k ) \cdot \hat { b } ^ { * } ( k ) + c . c . } { 2 | \hat { u } ( k ) | | \hat { b } ( k ) | }
$$

通过方程(5)发现磁极化（magneticpolarization）$P _ { m } ( k ) = \sigma _ { m } \sigma _ { c } = \pm 1$ (Alfven离子回旋波色散关系对应于 $^ { + 1 }$ ，而哨声波对应-1。）他们分析涡冻结形式的霍尔磁流体

$$
\partial _ { t } \Omega _ { h } = \nabla \times ( { \boldsymbol u } _ { h } \times { \boldsymbol \Omega } _ { h } ) , \qquad ( h = R , L )
$$

其中 $\Omega _ { R } = B , { \boldsymbol u } _ { R } = { \boldsymbol u } - d _ { i } \nabla \times { \boldsymbol B }$ and $\pmb { \Omega } _ { L } = \pmb { B } + d _ { i } \pmb { \nabla } \times$ ${ \pmb u } , { \pmb u } _ { L } = { \pmb u } _ { \circ }$ 让方程(7)中离子流体速度 ${ \pmb u } _ { L } = { \pmb u } = 0$ 使得霍尔磁流体退化为电子磁流体（eMHD）方程

$$
\begin{array} { r } { \partial _ { t } \boldsymbol { B } = - d _ { i } \nabla \times [ ( \nabla \times \boldsymbol { B } ) \times \boldsymbol { B } ] . } \end{array}
$$

其线性波对应于 $P _ { m } = - 1 { \it \Delta }$ ，它们进一步解释 $k ^ { - 7 / 3 }$ -支的谱为电子磁流体的结果。类似地取电子流体的速度为零，以得到离子磁流体（iMHD）

$$
\partial _ { t } ( 1 - d _ { i } ^ { 2 } \Delta ) B = d _ { i } \nabla \times [ ( \nabla \times B ) \times ( 1 - d _ { i } ^ { 2 } \Delta ) B ] ,
$$

其中离子速度 $\pmb { u } _ { i } = d _ { i } \nabla \times \pmb { B }$ 。对应线性波有 $P _ { m } = 1$ 它被用于确定它们数值模拟湍流的手性。

文献 $[ 1 5 ] P _ { m }$ 的两个极端值 $\pm 1$ 是从线性波得到的，而其数值模拟中并无平均场 $B _ { 0 }$ 来支持其论据，所以似乎并不适于刻画其iMHD和eMHD湍流。但是，其中关于iMHD和eMHD流动在顺次尺度中主导的洞见应是合理的，或可称为单流动主导态（OFDS)。恰当的非线性理论可通过联合OFDS和单手性主导态（OCSDS）得到。

既不引入背景平均场又不做线化处理，对于同手性情形就有 $\sigma _ { m } ~ = ~ s ~ = ~ - \sigma _ { c }$ ，也即，对于 $\hat { u } _ { R } ^ { s } = - s k d _ { i } \hat { b } ^ { s }$ ，将L动力学去除，有

$$
P _ { m } = \sigma _ { c } \sigma _ { m } = \frac { \sum _ { s } - s k d _ { i } | \hat { u } ^ { s } ( \pmb { k } ) | ^ { 2 } } { \sum _ { s } k d _ { i } | \hat { u } ^ { s } ( \pmb { k } ) | ^ { 2 } } \cdot \frac { \sum _ { s } s k | \hat { a } ^ { s } ( \pmb { k } ) | ^ { 2 } } { \sum _ { s } k | \hat { a } ^ { s } ( \pmb { k } ) | ^ { 2 } } = - 1 . 1 0 )
$$

类似地，去除R动力学，如果只有单手性一支，就有 $\sigma _ { m } = s = \sigma _ { c }$ 和 $P _ { m } = 1$ 。因此，同手性非线性理论给出了 $P _ { m } = \pm 1 { \ : }$ 0

# 2.2 XMHD“手性分子”绝对统计平衡

为简便，我们考虑不可压缩情形。此时XMHD有（也可能只有）如下积分

$$
\begin{array} { r l } { \frac { d \mathcal { H } } { d t } = } & { \frac { d } { 2 d t } \int _ { \mathbb { R } ^ { 2 } } [ u ^ { \beta } + B ^ { 2 } + d _ { \epsilon } ^ { \nu } ( \nabla \times B ) ^ { 2 } ] d ^ { 3 } r } \\ & { = \frac { d } { 2 d t } \sum _ { k ^ { \prime } } \vert k ^ { \prime } \vert ^ { 2 } + \frac { \vert \vec { \beta } \vert ^ { 2 } } { ( 1 + \epsilon _ { k } ^ { 2 } \kappa ^ { 2 } ) ^ { 3 } } \vert = 4 , } \\ { \frac { d M _ { \mathrm { d } } } { d t } = } & { \frac { d } { 2 d t } \int _ { \mathbb { R } ^ { 2 } } [ \nabla \cdot \mathcal { B } + d _ { \epsilon } ^ { \nu } \nabla \times \boldsymbol { u } - \boldsymbol { u } ] d ^ { 3 } r } \\ & { = \frac { d } { 2 d t } \sum _ { k ^ { \prime } } \vert k ^ { \prime } d ^ { 2 } \vert t \vert ^ { 2 } + \frac { \vert \vec { \beta } \vert ^ { 2 } } { k } \vert ^ { 2 } = 0 , } \\ { \frac { d M _ { \mathrm { C } } } { d t } = } & { \frac { d } { 2 d t } \int _ { \mathbb { R } ^ { 2 } } [ 0 . \boldsymbol { u } \cdot \mathcal { B } + d \nabla \times \boldsymbol { u } \cdot \boldsymbol { u } ] d ^ { 3 } r } \\ & { = \frac { d } { 2 d t } \sum _ { k ^ { \prime } } \vert k ^ { \prime \prime } \vert ^ { 2 \nu } \hat { \mathcal { B } } ^ { \ast } + \epsilon . c . + s t d . \vert k \vert ^ { 2 } \vert = 0 , } \end{array}
$$

$\mathcal { H }$ 称为哈密顿 (此为能量)， $\textstyle H _ { M }$ 为广义磁螺度，$H _ { C }$ 为广义横螺度。现实等离子体现象和数值模拟中本质上只有有限个模态，因而有理由认为只有那些经过伽辽金截断后还保持的性质具有重要的物理作用。可以验证，前述XMHD的三个积分保持守恒，像空间体积也保持守恒（Liouville定理)，这样我们就可以进行由李政道[17]、Kraichnan[18]以及Frisch等[19]发展，Zhu等利用手性分解计算讨论[20]的绝对统计平衡分析[2,14]：写出正则分布 $\sim \exp \{ - \alpha \mathcal { H } - \beta H _ { M } - \gamma H _ { C } \}$ ，并取 $a : = \alpha , b : = \beta / k .$ $c : = \gamma , f : = k ( \beta d _ { e } ^ { 2 } + \gamma d _ { i } )$ 和 $d : = \alpha / ( 1 + k ^ { 2 } d _ { e } ^ { 2 } )$ ，就可以算出比文献[21]更精细的三维谱密度，比如

$$
U _ { \mathcal { B } } ^ { s } ( \mathbf { k } ) : = \langle | \hat { \mathcal { B } } ^ { s } | ^ { 2 } \rangle / 2 = ( s f + a ) / \Delta _ { X } ^ { s } ,
$$

其中 $\Delta _ { X } ^ { s } = f b + a d - c ^ { 2 } + s ( a b + f d ) _ { \circ }$

OFDS应由等离子体物理中的尺度、质量比等参数定。而OCSDS则是非线性有螺热化动力学过程的结果：这可以从分析绝对统计平衡谱得到。比如，相反手性谱的分母所对应的极点互为反号出现，而 $k > 0$ 决定只有正极点可取到，也就是说极点附近的谱是由其中一个手性主导的（如图1所示)。另外，还有一些特殊的物理可能对应于手性非对称截断，可以提供所需的手性选择和放大机制[20]。有两个极限可取：

$d _ { e } \quad \to \quad 0$ ：霍尔磁流体OFDS $^ +$ OCSDS:文献[14]对前人的一些相关讨论（比如，文献[15]主张的自发对称破缺）进行批判性的评述。我们这里不再讨论。

$\begin{array} { r l r l } { d _ { i } } & { { } \to } & { 0 ; } \end{array}$ ：惯性磁流体OFDS $+$ OCSDS:文献[16]对亚电子太阳风和星际磁场提出唯像理论。他们也采用 $\hat { u } _ { k }$ 和 $\hat { b } _ { k }$ 间的顺排，和文献[15]一样也是由线性色散关系得到，不过说的是非线性项刚好为零的任意幅值的波。如果认为湍流是由这些精确模叠加，那么就没有非线性相互作用，也就没有能流，而这并非湍流的特征。而我们可以从 $\mathrm { \hbar ^ { \circ } O F D S + O C S D S ^ { \prime } }$ 进行论证：两个广义涡的（Lie）携带速度分别为 $\pmb { u } _ { \pmb { \mathrm { ~ \pm ~ } } } = \pmb { u } - \kappa _ { \mp } \nabla \times \pmb { B } _ { \pmb { \mathrm { ~ \mp ~ } } }$ 。其中 $\boldsymbol { \kappa } _ { \pm }$ 由 $\kappa ^ { 2 } - d _ { i } \kappa - d _ { e } ^ { 2 } = 0$ 定。这就意味着，在 $d _ { i } = 0$ 的惯性磁流体极限下， $\pmb { u } _ { \pm } = \pmb { u } \pm d _ { e } \nabla \times \pmb { B } _ { }$ 。因此 $\hat { \pmb { u } } _ { k } =$ $\mp d _ { e } \hat { i } k \times \hat { B } _ { k }$ 可以将其中一个流动去除而得到。也即，$\pmb { u } _ { \pm } \approx \pm 2 d _ { e } \nabla \times \pmb { B }$ 在 $u _ { \mp } \approx 0$ 时成为主导。同样，同手性或OCSDS意味着 $\hat { i } k \times \hat { B } _ { k } \approx s k \hat { B } _ { k }$ ，其中 $s = \pm$ 依手性而定，进而有 $\hat { \boldsymbol u } _ { \boldsymbol k } = - s k d _ { e } \hat { \boldsymbol B } _ { \boldsymbol k }$ 。这种 $\hat { u } _ { k } \propto k \hat { B }$ 关系正是文献[16]用以推得Kolmogorov唯像标度律 $k ^ { - 1 3 / 3 }$ 的。总结来说，非线性的OCSDS和OFDS联合构成了惯性磁流体湍流级串的本质。

考虑螺度的经典拓扑解释，可以分析理想XMHD在其约束下的弛豫状态，其结果也能体现有趣的手性特征[14]。此不展开讨论。

![](images/64b419ecc8240859b473a857518a09a29b7226d38e4b3ba604fbe07af94c480b.jpg)  
图1取如下参数得到的手性分解磁螺度一维谱，在极点附近显示单手性主导态： $\alpha = 1 0 , \beta = 9 . 8 9$ $\gamma = 0 . 9 8 7$ $d _ { i } = 0 . 1$   
Figure1 Chirally decomposed sample spectra of the magnetic helicity spectra,showing OCsDS nearly the poles,obtained with the following parameters: $\alpha = 1 0 , \beta = 9 . 8 9$ $\gamma = 0 . 9 8 7$ $d _ { i } = 0 . 1$ 5 $d _ { e } = d _ { i } / \sqrt { M } , M =$ 1836.

# 3等离子体螺旋呼吸子近似或类似结构

上一节事实上已经针对最近的一些目前看来还是既非充分有非必要的线性螺旋波论据提出了具体的非线性备选机制。这一节，我们再讨论一个具体的非线性机制，它可能提供解释现象的局部物理图像。从目前人们据以认定为线性回旋波的两个观测依据—周期性震荡和旋转矢端图一来看，有一种非线性结构都具备，它就是呼吸子。

呼吸子是时间周期但空间局域或空间周期时间局域的非线性结构，它为描述水波和玻色-爱因斯坦凝聚等现象的各种非线性（如，薛定谔）方程所容许[12]。特别指出的是，虽然很多时候水（表面）波被用势流来描述，但是还有讨论涡旋流中的波甚至各种方程描述有涡旋的波（见邹志利[22])。事实上，对于水表面波，初步分析表明是可以有螺旋的呼吸子近似或类似结构的，很可能是海洋中“来无影去无踪（appear from nowhere and disappearwithoutatrace）”的怪波（freakwave）的形成机制。等离子体在不同环境中，如太阳风，可能由简化的的非线性方程描述。最近Wang等人[23]就研究了非均匀等离子体中特别修正的非线性薛定谔方程的呼吸子。虽然目前讨论的还是一维情况，但是从其它三维水波和玻色-爱因斯坦凝聚等案例可以推断，等离子体在适当环境中是容许三维螺旋呼吸子近似或类似结构的。

综上，一般等离子体活动，尤其是太阳（风)剧烈湍流中，应能有螺旋呼吸子近似或类似结构出现（精确解及稳定性需严格的数学，暂不确定），虽然具体物理环境和数学模型有待确定：这种非线性结构兼具观测中看到的周期性（时间或空间）和回旋性，所以当在观测信号中看到这两个特征时，不能一概而论为何物，需要再求证其它信息。

# 4结语

显然，第2节中的讨论同样适用于等离子体双流体模型。它所体现的应该是等离子体物理本身具有的（近似）性质，不限于模型描述。等离子体湍流的结构非常丰富，其中既体现螺旋又体现（周期）震荡的现象非常普遍，人们对它的解释往往求助于线性动力学，指向电子或离子（线性）回旋波。但是，等离子体的动力学同样足够丰富，可以容许非线性的螺旋震荡结构。我们讨论了从湍流统计的角度提出的一种单手性主导的非线性解释机制，又提出三维呼吸子近似或类似结构的可能性。通常的孤立波在解释等离子体观测（如，文献[13]中动理学Alfven孤立波相关讨论）和湍流问题（如，文献[24]）已经为人们所熟悉，而三维呼吸子的相关研究还有待展开。应该说，自然足够多样，等离子体自身也足够活跃以形成各种（局部）环境，使得各种螺旋震荡结构形成机制都可能。我们期待在等离子体观测和数值模拟中得到更多的确

证。

我们最后指出，等离子体中手性选择和放大机制除了解释现象外，或可用于多场耦合等离子体流动控制。比如，射频等离子体（螺旋波）放电可以产生有螺流动，虽然能量小，但是我们可能设置适当的湍流环境使其通过非线性机制放大以用于控制螺度。

致谢感谢夏振伟博士帮助绘制图1。朱建州特别感谢何健森和赵国清教授在太阳风螺旋震荡结构方面，以及马玉祥和王岗教授在非线性水波方面的友好交流和亲切指导。

# 参考文献

1MosesHEigefuctiosoftleatootatioallvateoltdcatiotectroageictdu mechanics. SIAM(Soc.Ind.Appl.Math.) J.Appl.Math.,1971,21: 114-130.   
2朱建州.湍流手性：平衡与非平衡有螺可逆动力系综.中国科学（文稿）,2019：arXiv:1903.04804 [physics.flu-dyn].   
3邹文楠，朱建州，刘鑫.流动手性与结构的几何和拓扑图像描述.中国科学（文稿）2019：arXiv:1903.05349[physics.flu-dyn].   
4张洪起,杨尚斌,徐海清,等.探讨我国在太阳物理领域中螺度研究的进展.科学通报,2014,59:3561-3569.   
5ChenPF,HaaLKadFangCmagingdsectrosopicseatiosofaentheldheilicatiosforteatufoute streamings. The Astrophysical Journal,2014,784:50.   
6BiYet al. Observation ofa reversal of rotation in a sunspot during a solar flare.Nat. Commun.,2O16,7:13798.   
7Ouyang Y(欧阳雨), Zhou YH(周雨昊),Chen PF(陈鹏 $\updownarrow$ ）and Fang C(方成).Chirality and magnetic configurrations of solar filaments.The Astrophysical Journal,2017,835:94.   
8高裕.简单alpha效应的平均场发电机解和活动区螺度的观测.本专辑文章.   
9徐海清.电流螺度随磁场强度的分布研究.本专辑文章.   
10杨尚斌.太阳大气中磁螺度的传输和积累.本专辑文章.   
11如，太阳中：JianLKoyaPSViasAF,&StevesM.Electromageticcyclotrowavestesoarwind:Windobervatioandwave dispersionanalysis.AofereceProceedings,6,72(1):7;HeJarschE,TuCaondianHoibleevidecf Alfven-cyclotrowavesineleditrboofageticelicityfolardturbeceAstrops.J:85;ZaegH Q,WuDJ,PiGandHuangJ.OteGenerationMechanismofElectromagneticCylotronWavesintheSlarWindStatiticalesulsFro Wind Observations.ApJ（已接受，待发表)，及其中参考文献.   
12最近就有如,Qian C(钱超),RaoJ-G(饶继光),LiuY-B(刘尧彬),HeJ-S(贺劲松)．Rogue Waves in the Thre-Dimensional Kadomtsev - Petviashvili Equation.Chin. Phys.Lett.,2016,33(11):110201-1-110201-4; XuT,TianB,LiL-L,LuX,ZhangC.DynamicsofAlfvensolitons ininhomogeneous plasmas.Phys.Plasmas,2O1815:10307; ZhangY,GuoLXuuZHJeeacfgherderutisofteatieiearoingatioomr Sci Numer Simulat,201419:1706-1722; Yin Y,Tian B,Wu X-Y,Yin H-Mand Zhang C-R.Lump waves and breather waves for a $( 3 { + } 1 )$ -dimensional generalized Kadomtsev-Petviashvili Benjamin-Bona-Mahony equation for an offshore structure.Modern Physics Letters B,2O18,32:1850031; LiaoB,MaY,aX-YandDongGExprimetalvestigationoftheeregiBreatrofgravityavesofitewaterpth.RevE, 2018,97: 053102; Peng X,ZhangJngYD,agLenXoF&engpaotpoairyceusiavecketsiroglol nonlinear media. Scientific Reports,2018 8: 4174; GuoB,LigL,andLiuQ-PHigrderSolutionandeneralizedDarbouxTransfoatiosoferivativeNolinearShroedingerutios. Studies in Applied Mathematics,2012,0:1- 28; 贺锋涛,湛飞,石文娟,非均匀掺饵光纤中的可控呼吸子与多峰孤子.光子学报,2018,67:0619001;

WangLLiXielreactiosddeoatoousesforeoogsiearge Maxwell-Bloch equations.Annals of Physics,2015,359:97-114. 13Wu D-J.Kinetic Alfven Wave.Science Press Beijing,2012. 14ZhuJZ.Calitededagedsatidpalsratfoaieoto Lett., 2017, 470: L87. 15Meyrand&ater.Sotaeoucalsmeryeakingofhallagetoydrodyictrbulenc.Pysev.Let.,2940. 16AbdelhamidHM,LingamM&MahaanSM.ExtendedMHDTurbulenceandItsApplications to teSolar WindApJ,016,29:87. 17Lee T-D.On some statistical propertiesof hydrodynamic and hydromagnetic fields.Q.Appl.Maths,1952,10:69-74. 18Kraichnan R H.Helical turbulence and absolute equilibrium.J.Fluid Mech.,1973,59:745-752. 19FrischU,ouqetA,LoatJ&azure.osibilityofisemageticicityasadeinagetodroymctrbuleud Mech.,1975,68: 769-778. 20ZhuJ-ZYng&ZuGurelycalbsotedraliof(agetofdblee.JFuidMec,9:40. 21MiloshevichGgooOecureatiticalfteeteddagodacsal of Physics,2017,19: 015007. 22邹志利.水波理论及其应用.科学出版社，2005. 23如，WangLiQiF-ndXuTulaioalsabilttoouseatesdogeafblettie nonlinear Schroedinger equation in the inhomogeneous plasmas.Phys.Plasmas 2O15 22: 032308. 24刘式达，刘式适.孤波和湍流.上海科技教育出版社,1994.

# Plasma nonlinear chirality: helical turbulence and breathers

Chen $\mathrm { { \bf P } } ^ { 1 }$ , Yang $\mathrm { Y } ^ { 1 , 2 }$ &Zhu ${ \bf J - } { \cal Z } ^ { 1 * }$

1.Su-ChengCentreforFundamental and Interdisciplinary Sciences,Gaochun,Nanjing2ll316,China;; 2.LHD,Institute ofMechanics,ChineseAcademy ofSciences,BeijinglOol9o,China

In plasma turbulence,suchasthe solar wind,the helicaland(nearly)periodic structuresarenot necessarilylinear waves. Plasmas in diferent environments present diferent dynamical characters,admiting various nonlinear structures.It is presented here twoalternativenonlinearmechanisms that lead torelevantchiralityissues insolarwind,the helicalturbulent modes and breathers.The former is explained by revisitingarecent proposal in studying solar wind with the extended magnetohydrodynamics,and the latter is argued with a listof sources of information from water waves,plasmas and Bose-Einstein condensates,though a concrete solar wind plasma model for it is still open.

helical turbulence,solar wind plasma,breather, cyclotron wave,flow control using plasma

PACS:47.27.Rc,47.27.-i, 52.30.?q,52.35.Ra,02.30.Ik