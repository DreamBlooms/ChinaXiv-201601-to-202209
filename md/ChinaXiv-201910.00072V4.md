# 不确定性原理与客观确定性判则

段德龙↑

（中国科学院空天信息研究院，中国科学院电子学研究所，北京100190）

# 摘要:

[目的]分析解决不确定性原理及量子理论在物理诠释方面的分歧。

[方法］对海森堡不确定性原理数学关系式的原始推导、物理涵义以及爱因斯坦光子箱思想实验进行了重新检视分析，并考察了不同作用图景下该关系式的极限。[结果]在电磁作用图景下，通过对量子力学量的统计分布及其全概率空间的分析，首次获得了非统计诠释下的不确定性关系式在数学上被破坏的结果；利用傅里叶变换，导出了虚拟作用图景下相应共轭力学量的标准差约束关系式；通过考察电磁作用图景、引力作用图景以及虚拟作用图景所构成的集合，率先得到了微观量子客体力学状态的确定性判则；经过对爱因斯坦光子箱思想实验的重新检视分析，证伪了玻尔在索尔维会议上的论证结论。

[局限]未分析量子纠缠。

[结论] $\textcircled{1}$ 非统计诠释存在逻辑矛盾，不确定性关系、现行量子力学理论仅在统计诠释下，才能对微观量子客体在电磁作用图景中的力学状态作出恰当的描述； $\textcircled{2}$ 确定性判则显示，微观粒子的力学状态具有客观确定性，其波函数是对电磁作用图景下的微观粒子力学状态统计呈现相的表述；量子力学非统计诠释所指称的个体几率性实质是微观粒子与作用图景之间互作用统计呈现相的概率反映。

关键词：量子力学，不确定性（原理）关系，哥本哈根诠释，概率分布，索尔维会议-光子箱，引力波

PACS: 03.65.Ca，03.65.Ta，05.30.ch，02.50.Sk，01.70.+w，95.85.Sz

# The Uncertainty Principle and the Certainty Rule

DUAN De-Longt (Aerospace Information Research Institute，Chinese Academy of Sciences; Institute of Electronics， Chinese Academy of Sciences,Beijing,100190)

# Abstract:

[Objective] Analyze and resolve differences between the uncertainty principle and quantum theory in physical interpretation.

[Methods] The original derivation and physical meaning of the mathematical relationship of Heisenberg' s uncertainty principle and the Einstein's photon box thought experiment were re-examined, and the limits of the relationship under different action scenarios were investigated.

[Results]Under the electromagnetic interaction scenario, through the analysis of the statistical distribution of quantum mechanical quantities and its full probability space， the result of the destruction of the uncertainty relationship under non-statistical interpretation is obtained; After re-examination and analysis of Einstein's photon box thought experiment， falsified the Bohr's argument conclusion produced at the Solvay Conference; The virtual action scenario is derived using Fourier transform Under the standard deviation constraint relation of the corresponding conjugate mechanical quantity; through the investigation of the set of electromagnetic interaction scenes， gravitational interaction scenes， and virtual interaction scenes, the deterministic criterion of the mechanical state of microscopic quantum objects is obtained.

[Limitations] Unanalyzed Entanglement.

[Conclusions] （20 $\textcircled{1}$ The non-statistical interpretation has logical contradictions, the uncertainty relationship, and the current quantum mechanics theory can only properly describe the mechanical state of the microscopic quantum object in the electromagnetic interaction scene under the statistical interpretation; $\textcircled{2}$ The deterministic criterion shows that the mechanical state of microscopic particles is objectively certain， and its wave function is an expression of the statistical appearance of the mechanical state of microscopic particles in the context of electromagnetic interaction.The quantum probabilityofnon-statistical interpretation refers in essence to the description of the statistical probability of the interaction between microscopic particles and the interaction scene.

Keywords:quantum mechanics，uncertainty principle (relation)， Copenhagen interpretation of quantum mechanics，probability distribution，Solvay-Conference Photon-Box，gravitational waves

# 1引言

量子力学被雅默称之为关于微观基元过程唯一逻辑一贯的理论，它奠定了现代科学的基础，是当代物质与信息科学技术发展的基石，获得了科学史上前所未有的巨大成功[[2][3][4]。与此同时，发端于海森堡不确定性原理的量子力学物理诠释纷争——玻尔与爱因斯坦所代表的两种诠释之间的根本分歧，长期以来却一直存在[2]。

不确定性原理作为在量子力学理论体系中被冠以“原理”称谓的命题[5]，被波尔学派的泡利狄拉克等称为量子力学理论的基石。量子力学数学形式体系的构建超前于其物理诠释，海森堡为了解决量子力学形式体系 $\textcircled{1}$ 是否容许一个粒子的位置与速度在一给定的时刻只能以有限的精度被确定， $\textcircled{2}$ 理论允许的精度与实验测量中获得的最佳精度是否相容这两个问题[1][3][4[6]，于1927年3月推导出了不确定性关系式并提出不确定性原理[1][6]。不确定性原理的提出，被认为是科学史中的一个重大成就——它展现出了量子力学非决定性(indeterminacy)与经典力学中的决定论(determinism)所形成的截然反差，是量子力学理论与经典力学理论之间本质差异的标志[5][7]。

海森堡的不确定性关系式及其物理诠释甫一提出，随即引起了爱因斯坦和玻尔的注意，在当年10月举行的索尔维会议上，爱因斯坦与玻尔就此展开了激烈的辩论。从与量子理论的逻辑自洽性等价的不确定性原理逻辑一贯性到EPR理论所针对的量子力学理论的完备性，从1927年到二人去世，爱因斯坦与玻尔之间持续进行的论战历时几十年。尽管经过1927年和1930年在两次索尔维会议上与玻尔的辩论，爱因斯坦曾不再公开质疑不确定性原理的有效性，但实际上他始终未对玻尔-海森堡的诠释基础表示过认同。并且，应该注意到，玻尔直至1962年去世，对于他本人与海森堡等一直坚持的不确定性原理与量子力学非统计性诠释也并非完全地自信与肯定[I][8]。

对于不确定性关系式的数学推导，物理学界并无异议，根本性分歧在于始自爱因斯坦-玻尔时代的不确定性原理的物理诠释。不确定性关系的物理诠释，依照雅默的研究，主要分为以下两个流派[1];

I统计诠释——即爱因斯坦、薛定谔所坚持的诠释：不确定性关系描述的是全同制备的量子系统所构成的系综，其正则共轭变量统计分布的标准差之积下限为 $ { \mathrm { { \hat { h } } } } _ { / _ { 2 } }$ 。其实质是坚持而不是放弃经典因果决定性的精确化图景描述。

Ⅱ非统计诠释—一玻尔-海森堡诠释：不确性关系是对个体量子系统的描述，其正则共轭变量不能同时被精确地确定、不确定度之积下限为h/2 为。这是量子力学主流诠释，亦被称为量子力学正统诠释、哥本哈根诠释，其本质是坚持量子力学的个体几率性。

目前量子力学应用技术在快速发展,但其理论诠释却依然二元对立不能统一，这种微妙的状况对以量子力学为理论基础的新理论、新技术的进一步完善与提高造成了很大的困扰。鉴于不确定性原理所标志的量子力学理论在物理诠释方面的历史和现状，本文将首先检视不确定性原理关系式的原始推导、物理涵义，在电磁作用图景下对非统计诠释的不确定性关系式进行概率分析和讨论；尔后在引力作用图景中对相应的数学关系式进行类比推导，最后通过虚拟作用图景基本作用量单元的极限分析，考察不确定性关系与波函数数学形式的演化。

# 2不确定性原理关系式的提出与非统计诠释

海森堡1927年3月发表了《论量子理论的运动学和力学的直观内容》[1[6]，提出海森堡不确定性原理并给出关系式的数学推导，1929年H.P.罗伯逊用量子力学算符表示给出不确定性关系的规范证明[1]。

海森堡在[6]中通过量子力学数学形式导出了下面的关系式：

（201 $\Delta q \Delta p \geq \mathrm { ^ { \hslash } } _ { 2 }$ （20 (1)式中 $\Delta { \bf q } \equiv \sqrt { ( \Delta { \bf q } ) ^ { 2 } } = \sqrt { ( x - \overline { { x } } ) ^ { 2 } } .$ 、 $\Delta \mathfrak { p } \equiv \sqrt { ( \Delta \mathfrak { p } ) ^ { 2 } } = \sqrt { ( \mathfrak { p } _ { x } - \overline { { \mathfrak { p } _ { x } } } ) ^ { 2 } }$ ，同时又以 $\gamma$ 射线显微镜及电子的单狭缝位置测定等思想实验为例对不确定性原理进行了物理诠释[I[2]，定义不确定性关系式是量子理论对同时测量几个不同物理量的精确度限制，强调任何一个测定位置 $q$ 的实验,每一次观测必定会在某种程度上干扰对速度（动量) $p$ 的认识（反之亦然)；并且这种改变的不确定程度必定使得在实验完成之后，对于电子运动关于位置 $q$ 和速度（动量) $p$ 的知识（精度）要受到不确定性关系式的限制[o，“任何一个确切的观测结果（精度）都要遵守不确定度关系”[8]。

认为不确定性原理保护着量子力学的逻辑自洽性[10]，强调不确定性关系式是对同时测量不同物理量的最佳精度作出的限制，突出精度限制的物理来源是测量操作带来的无法避免的干扰[6][9][1][1][2][3]，是量子力学哥本哈根学派非统计诠释的核心。

非统计诠释也是目前绝大部分中外量子力学、理论力学教科书以及自然哲学专著和有关科普量子理论的著作[1][2][][14][5][16]，教授和介绍有关海森堡不确定性原理时所使用的标准诠释（后文以《关系式： $\Delta { \sf q } \Delta { \sf p } \geq \hbar . 7 ? . .$ （1a)式》表示非统计诠释诠释下的不确定性原理关系式）。

# 3不确定性原理分析探讨

# 3.1不确定性关系式非统计诠释的检视分析

3.1.1力学量 $q , p$ 的统计分布与非统计诠释的符合性分析

与[6]海森堡导出不确定性关系数学表达式时所作假设相同，记函数 $\Psi \bigl ( q ^ { \prime } \bigr )$ 、 $\Psi ( p ^ { ' } ) \}$ 依次为电子的力学量 $q , p$ 分布的概率幅，设 $q , p$ 为高斯分布，其概率幅 $\Psi ( q ^ { \prime } ) , \Psi ( p ^ { \prime } )$ 表达式（同[6]中定义）如下}

$$
\begin{array} { r l } & { \Psi \big ( q ^ { * } \big ) = \frac { \nu _ { \mathrm { H } } ^ { * } } { \Theta ^ { * } } \frac { \nu _ { \ell } } { \mathcal { Z } } \langle \boldsymbol { \cdot } e ^ { - \frac { \big ( q ^ { * } - \bar { q } \big ) ^ { 2 } } { 4 \overline { { ( \Delta q ) ^ { 2 } } } } - \frac { 2 \pi i } { h } \bar { p } q ^ { * } } } \\ & { \quad \quad \quad \Psi \big ( p ^ { * } \big ) = \int \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \mathrm { \hbar } } q ^ { * } p ^ { * } } \Psi \big ( q ^ { * } \big ) \mathrm { d } q ^ { * } } \end{array}
$$

$\textcircled{1}$ 定义 $\Delta q ^ { \prime } = q ^ { \prime } - \overline { { { q } } }$ 为任意单次测量 $q$ 对 $\overline { { q } }$ 的偏差（后文 $\Delta q ^ { \prime } , \Delta p ^ { \prime }$ 的定义皆与此相同)，以表示对 $\mathsf { q }$ 的单次测量精度。记 $\boldsymbol { q ^ { \prime } }$ 满足 $q ^ { \prime } \in ( \overline { { q } } - \Delta q , \overline { { q } } + \Delta q )$ 即 $\Delta q ^ { \prime } { < } \Delta q$ 的概率为 $\boldsymbol \eta _ { \boldsymbol { q } ^ { \prime } }$

$$
\eta _ { q ^ { \prime } } = \{ \int _ { \overline { { { q } } } - \Delta q } ^ { \overline { { { q } } } + \Delta q } { \left| { \Psi \left( { q ^ { \prime } } \right) } \right| ^ { 2 } } d q ^ { ' } \} / \left\{ { \left| { \Psi \left( { q ^ { \prime } } \right) } \right| ^ { 2 } } d q ^ { ' } \right\}
$$

其中 $\Delta q$ 为(1a)式q为高斯分布时对 $\cdot { \Delta q }$ 的定义（后文3.1.2的分析过程所使用的 $\Delta q$ 定义与此相同)。

由定积分性质可知，若在[ab]上有函数 $f ( x ) { \geq } 0$ 成立，则

$$
\int _ { a } ^ { b } f ( x ) d x \geq 0
$$

必定成立。又因为 $\left. \Psi \bigl ( q ^ { \prime } \bigr ) \right. ^ { 2 } > 0$ 且 $\begin{array} { r } { \int { \left| { \psi ( q ^ { ' } ) } \right| ^ { 2 } } d q ^ { ' } = 1 } \end{array}$ ，所以有

$$
\eta _ { q } , = \dot { \{ \int _ { \bar { q } - \Delta q } ^ { \bar { q } + \Delta \dot { q } } \left| \Psi \big ( q ^ { \prime } \big ) \right| ^ { 2 } }  d q ^ { \prime } \} \mathcal { A } \int \left| \Psi \big ( q ^ { \prime } \big ) \right| ^ { 2 } d q ^ { \prime } \} > 0
$$

（ $\textcircled{2}$ 因 $q$ 和 $p$ 为高斯分布，所以（la)中 $\Delta q$ ， $\Delta p$ 满足 $\Delta q \Delta p = \mathrm { \AA } _ { 2 }$ ， $\Delta p$ 为（1a)式 $p$ 为高斯分布时对 $\cdot _ { \Delta p }$ 的定义（后文3.1.2条数学推导过程所使用的 $\Delta p$ 定义与此相同)。记满足 $\{ p ^ { \prime } \in ( \overline { { p } } - \Delta p ,$ （204

$\bar { p } { + } \Delta p ) , \Delta q \Delta p = \ L ^ { \mathrm { \scriptsize ~ \mathrm { \scriptsize { h } } } } / \Sigma$ 的寶 $( q ^ { \prime } , p ^ { \prime } )$ 的概率为 $\boldsymbol { \mathsf { \Pi } } _ { \mathsf { \Pi } } _ { \mathsf { \Pi } } _ { p _ { } }$ ， $( q ^ { \prime } , p ^ { \prime } )$ 满足 $\{ q ^ { ' } \in ( \overline { { q } } \ – \Delta q , \overline { { q } } \cdot \Delta q ) , p ^ { \prime } \in ( \overline { { p } } \ – \Delta p , \overline { { p } } \cdot \Delta p ) ,$ $\Delta q \Delta p = \ L ^ { \mathrm { \scriptsize { h } } } / _ { 2 } \ L \}$ 的概率为 $\boldsymbol \eta _ { \boldsymbol { q } ^ { \prime } \boldsymbol { p } ^ { \prime } }$ ，则：

$$
\begin{array} { c } { { \displaystyle \eta _ { p ^ { \prime } } = \int _ { - \Delta p } ^ { + \Delta p } \Psi ( p ^ { \prime } ) \Psi ^ { * } ( p ^ { \prime } ) d p ^ { \prime } } } \\ { { = \int _ { - \Delta p } ^ { + \Delta p } \left( \int \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { j } \ddot { p ^ { \prime } } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \right) \left( \int \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { j } p ^ { \prime } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \right) ^ { * } d p ^ { \prime } } } \\ { { \displaystyle \eta _ { q ^ { \prime } p ^ { \prime } } = \int _ { - \Delta p } ^ { + \Delta p } \left( \int _ { - \Delta q } ^ { + \Delta q } \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { j } \ddot { p ^ { \prime } } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \right) \left( \int _ { - \Delta q } ^ { + \Delta q } \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { j } p ^ { \prime } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \right) ^ { * } d p ^ { \prime } } } \\ { { = \int _ { - \Delta p } ^ { + \Delta p } \left| \int _ { - \Delta q } ^ { + \Delta q } \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { j } \ddot { p ^ { \prime } } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \right| ^ { 2 } d p ^ { \prime } } } \end{array}
$$

由式(4b)和定积分性质可得 $( q , p ^ { \prime } )$ 概率 $\eta _ { \boldsymbol { q } ^ { } \flat }$

$$
\begin{array} { r } { \eta _ { q ^ { \prime } p ^ { \prime } } = \int _ { - \Delta p } ^ { + \Delta p } \bigg | \int _ { - \Delta q } ^ { + \Delta q } \frac { 1 } { \sqrt { \mathrm { h } } } \mathrm { e } ^ { \frac { \mathrm { i } } { \hbar } q ^ { \prime } p ^ { \prime } } \Psi ( q ^ { \prime } ) \mathrm { d } q ^ { \prime } \bigg | ^ { 2 } d p ^ { \prime } > 0 } \end{array}
$$

此时 $p ^ { \prime } \epsilon ( \bar { p } { - } \Delta p , \bar { p } { + } \Delta p )$ 即 $\Delta p ^ { \prime } { < } \Delta p$ 的概率 $\eta _ { q ^ { \prime } p } ,$ 为

$$
\eta _ { q ^ { \prime } p ^ { \prime } } > 0
$$

$\textcircled{3}$ 由(4b)、(5)、(6)式得，满足条件；亦即当下式：

$$
\Delta q ^ { \prime } \Delta p ^ { \prime } < \ L ^ { \mathrm { \scriptsize { h } } } \big / _ { 2 }
$$

成立时，存在(7a)式

$$
\eta _ { q ^ { \prime } p } , ~ { > } 0
$$

概率分析结果(7a)式与非统计诠释的预言相矛盾，表明“任何一个确切的观测结果（精度)都要遵守的不确定度关系式”凹 $^ { \alpha } \Delta q \Delta p \geq ^ { \hslash } { _ { 2 } } ^ { , \prime }$ h/2”（1a)失效、不成立。

3.1.2不确定性原理关系式在全概率空间的预言符合性分析

同3.1.1条定义， $q , p$ 为高斯分布，分布函数分别为 $\Psi ( { \sf q } ^ { \prime } ) , \Psi ( p ^ { \prime } )$ ，（本节 $\Delta q , \Delta p , \Delta q ^ { \prime } ,$ （20$\Delta p$ 的定义同3.1.1条）。

$\textcircled{1}$ 定义事件 $( p ^ { \prime } , ~ q ^ { \prime } )$ 的全样本空间为 $\Omega$ ， $q ^ { \prime } \epsilon ( - \infty , \ + \infty )$ ， $p ^ { \prime } \epsilon ( - \infty , \ + \infty )$ 。对于全域 取值事件 $( p ^ { \prime } , ~ q ^ { \prime } )$ ， $\Omega$ 概率 $\boldsymbol { \eta } _ { \boldsymbol { q } ^ { \prime } \boldsymbol { p } } ^ { \Omega }$ （

$$
\begin{array} { c } { { \displaystyle \mathsf { \eta } _ { q ^ { \prime } p ^ { \prime } } ^ { \Omega } = 1 } } \\ { { \{ q ^ { ' } \in ( \bar { q } { \ - } \Delta q , \mathrm { ~ } \bar { q } { \ - } \Delta q ) , \mathrm { ~ } p ^ { ' } \in ( \bar { p } { \ - } { \Delta p } , \mathrm { ~ } \bar { p } { + } \Delta p ) , \mathrm { ~ } \Delta q { \Delta p } = } } \end{array}
$$

$\textcircled{2}$ 记 $A$ 为 $( p ^ { \prime } , ~ q ^ { \prime } )$ 满足$\mathfrak { h } _  / _ { 2 } \}$ 即 $( p ^ { \prime } , \ q ^ { \prime } )$ 满足条件 $\Delta q ^ { \prime } \Delta p ^ { \prime } < \Delta q \Delta p = \ L ^ { \mathrm { \scriptsize ~ \hslash } } \big / _ { 2 }$ 的事件集合，由(4b)式和定积分的性质可知其发生概率 $\boldsymbol \eta _ { A }$

$$
\mathfrak { \eta } _ { A } = \mathfrak { \eta } _ { \boldsymbol { q } ^ { \prime } \boldsymbol { p } ^ { \prime } } ^ { A } > 0
$$

$\textcircled{3}$ 记A为 $( p ^ { \prime } , \ q ^ { \prime } )$ 满足不确定性原理关系式(1a)的所有事件集合，按海森堡关于不确定性关系式的定义，事件 $( p ^ { \prime } , ~ q ^ { \prime } )$ 集合A概率 $\eta _ { \\\\overline { { A } } }$ 必须以全概率存在于样本空间 $\varOmega$ ，即

$$
\mathfrak { \eta } _ { \overline { { A } } } = \mathfrak { \eta } _ { \begin{array} { l } { q ^ { \prime } p ^ { \prime } } \end{array} } ^ { \overline { { A } } } = 1
$$

$\textcircled{4}$ 由 $\textcircled{1} \textcircled{2} \textcircled{3}$ 定义可知， $\scriptstyle { \mathcal { Q } } = A \ U { \overline { { A } } }$ ，从(8)、(9)两式可得集合A的概率 $\eta _ { \\\\overline { { A } } }$

$$
\begin{array} { c } { { \eta _ { \bar { A } } = \eta _ { q \dot { p } } ^ { \Omega } - \eta _ { A } } } \\ { { \Rightarrow \qquad \eta _ { \bar { A } } < 1 } } \end{array}
$$

即在全样本空间 $\Omega$ 上，由不确定性关系式(1a)决定的事件集合A的概率 $\mathfrak { \eta } _ { \bar { A } } < 1$ ，为非全概率。

$\textcircled{5}$ 在全样本空间 $\Omega$ 上， $\overline { { A } }$ 的概率 $\eta _ { \\\\overline { { A } } }$ 由 $\textcircled{3}$ 、 $\textcircled{4}$ 两条依次进行分析，分别得到式(10)与(11)两个相互矛盾的不同结果：式(11)破坏了(3)条中满足海森堡不确定性原理关系式 $\Delta q \Delta p \ge ^ { \mathtt { h } } / _ { 2 }$ （204号(la)的所有事件 $( p ^ { \prime } , ~ q ^ { \prime } )$ 集合A必须为式(10)决定的全概率即 $\mathfrak { n } _ { \overline { { A } } } = 1$ 的要求。

通过对 $( p ^ { \prime } , ~ q ^ { \prime } )$ 全样本概率空间 $\Omega$ 的分析，与3.1.1条相同、同样得到了非统计诠释下的不确定性原理关系式 $^ { \mathfrak { a } } \Delta q \Delta p \geq ^ { \mathfrak { h } } / _ { 2 } , ^ { \mathfrak { , } }$ （la)不成立的结果。

3.1.3对不确定性原理非统计诠释失效的探讨

海森堡在[6]中从量子力学数学形式体系出发对不确定性关系式进行推导证明时，不仅用到了坐标表象和动量表象两种统计性的波函数，还用到了表象变换和对变换函数的统计诠释；而且在他对 $\gamma$ 射线显微镜进行的定性物理分析中，也同样用到了隐含的统计性关系—-爱因斯坦-德布罗意关系。没有统计性的波函数、没有德布罗意关系，海森堡就无从得到其不确定性原理关系式。不确定性关系式作为量子力学数学形式体系的一个直接推论、即通过狄拉克-约尔当变换理论获得的一个结论[1][2][3][]，它在数学上表征了共轭力学量 $p , q$ 的统计分布弥散程度的标准差之间的约束关系，是与统计诠释等价的数学表述。

单纯数学形式本身的明晰性对于一个物理命题没什么（物理）价值，完备的物理解释应当绝对地高于其数学形式体系[I[I4]，海森堡为了给予量子力学一个直观清晰物理图像，在推导出关系式（1）之后，将关系式中的方差 $\overline { { \Delta q ^ { 2 } } }$ 、 $\overline { { ( \Delta p ) ^ { 2 } } }$ 定义为电子位置和动量的不准确程度用以表示测量的精确度，把该数学关系式诠释为表示量子理论中对于运动电子的位置 $q$ 和速度（动量） $p$ 的知识所要受到的限制[10]和同时测量两个不同物理量的精确度[]之间要遵从的约束关系。

不确定性关系式（1）中的方差 $\overline { { ( \Delta q ) ^ { 2 } } }$ ， $\overline { { ( \Delta p ) ^ { 2 } } }$ 表示力学量 $q , p$ 值的弥散程度、呈现的是$q , p$ 值的统计分布特征[I[2]l3]，二者都必需经过对大量高精度的测量进行统计分析才能获得、无法仅仅通过单次测量就得到[5]；而在海森堡非统计诠释的关系式（1a）中却明确地用其表示测量精确度一一精确度为参量 $q , \ p$ 获得值对真（期望）值的偏离度，是与单次测量有关的个体特性量；海森堡将关系式（1）中的 $\Delta q . \ \Delta p$ 重新诠释定义为测量精确度，使其失去了原本在统计理论中的标准差的数学涵义，在概念上造成了 $\Delta q$ 、 $\Delta p$ 的数学/物理涵义发生由均方根差 $$ 不确定度 $$ 测量精确度的改变、内涵前后不一。无容置疑，这违背逻辑一贯性原则;而且，一个物理量的测量精确度要远远小于其多次测量结果所构成分布的标准差[3]，因此上文的3.1.1和3.1.2条在对非统计诠释进行概率分析时，都得到了关系式（1a）遭破坏、非统计诠释不成立的结果。

不仅如此，非统计诠释迄今为止还没有直接获得过真实实验的验证支持[1Is]，曾经为其提供过诠释支撑的海森堡 $\gamma$ -射线显微镜、电子的单缝位置测定和爱因斯坦光子箱（见3.4条分析）等几个思想实验[iI6]，在后来的再次检视分析工作中，都得到了与3.1.1/2条分析证明相一致的——关系式（1a）遭到破坏的研究结果[5][17][18][19][20]。

统计诠释仅仅未被电磁作用图景描述下的实验所否定[1]（见3.4条)。作为统计诠释等价数学表述的不确定性原理关系式，仅仅表示电磁作用图景下系综的共轭力学量q、p标准差之间的约束关系，是对现行量子力学描述之统计模糊性的度量；而对与标准差来源不同的单次测量行为之精度则没有必然的约束、不存在任何的限制，也不能对力学量 $p$ 、 $q$ 的单次测量精确度之积 $\Delta q ^ { \cdot } \Delta p ^ { \cdot }$ 作出任何限制。单次测量的精确度没有上下限，统计诠释并不否定微观粒子可同时具有确定的位置与动量[3][7][18][19]，而且，统计意义上的不确定性关系并非量子力学所独有，在经典理论中同样不乏其对应的存在[3]。

概率分析与思想实验检视证明了海森堡-玻尔一直以来所坚持的非统计诠释缺乏逻辑一贯性。不确定性关系与现行量子力学理论，仅在统计诠释下才能对电磁作用图景中微观量子客体的力学状态作出恰当的描述，从这个意义上说，海森堡诠释定义的不确定性关系并没有解决当时认为的量子力学形式体系所面对的两个问题。

# 3.2非电磁作用图景的讨论

3.2.1非电磁作用图景下的共轭力学量标准差约束关系参照[6][21][22]导出不确定性关系式的方法，设有某一待定作用图景 $X ( \varepsilon _ { \mathrm { x } } )$ ，定义其基本作用量单元为 $\varepsilon _ { x }$ 。在 $\mathrm { X } ( \varepsilon _ { x } )$ 作用图景下，有一个粒子处于某一有限空间区域内，这个空间区域沿三个坐标轴方向分别为 $\mathbf { x }$ ，y，z；为简单起见只讨论三个空间坐标中的一个——x坐标。令粒子沿 $\mathbf { x }$ 方向运动， $\mathfrak { p } _ { x }$ 为该粒子的动量， $\mathbf { x }$ 和 $\mathrm { P } _ { x }$ 为共轭力学量。与电磁作用图景相同，设其坐标 $x$ 波函数形式为中 $( x )$ ，动量 $\mathbf { \dot { p } } _ { x }$ 波函数形式为 $\Psi ( p _ { x } )$ 。

用标准偏差来表明坐标和动量的不确定度

$$
\Delta x = \sqrt { \overline { { ( x - \overline { { x } } ) ^ { 2 } } } } , \Delta \mathrm { p } _ { x } = \sqrt { \overline { { ( \mathrm { p } _ { x } - \overline { { \mathrm { p } _ { x } } } ) ^ { 2 } } } }
$$

为分析简单计，仅考虑一维的情况，其波函数 $\Psi ( \mathbf { x } )$ 只依赖于一个坐标，并假定这个态中的 $\mathbf { x }$ 和 $\mathfrak { p } _ { \mathrm { x } }$ 的平均值都等于零。

考虑下列明显成立的不等式

$$
\begin{array} { r } { \int _ { - \infty } ^ { \infty } \left| \alpha x \psi + \frac { d \Psi } { d x } \right| ^ { 2 } d x \geq 0 } \end{array}
$$

其中 $\alpha$ 是一个任意的实常数。计算上述积分时，由于：

$$
\begin{array} { r l } & { \qquad \int x ^ { 2 } | \Psi | ^ { 2 } d x = ( \Delta x ) ^ { 2 } } \\ & { \int \left( x \frac { d \Psi ^ { * } } { d x } \Psi + x \Psi ^ { * } \frac { d \Psi } { d x } \right) d x = \int x \frac { d | \Psi | ^ { 2 } } { d x } d x = - \int | \Psi | ^ { 2 } d x = - 1 } \\ & { \int \frac { d \Psi ^ { * } } { d x } \frac { d \Psi } { d x } d x = - \int \Psi ^ { * } \frac { d ^ { 2 } \Psi } { d x ^ { 2 } } d x = \frac { 1 } { \varepsilon _ { x } ^ { 2 } } \int \Psi ^ { * } \widehat { p } _ { x } ^ { 2 } \Psi d x = \frac { 1 } { \varepsilon _ { x } ^ { 2 } } ( \Delta p _ { x } ) ^ { 2 } } \end{array}
$$

我们得

$$
\begin{array} { r } { \alpha ^ { 2 } ( \Delta x ) ^ { 2 } - \alpha + \frac { 1 } { \underline { { \varepsilon } } _ { x } ^ { 2 } } ( \Delta p _ { x } ) ^ { 2 } \geq 0 } \end{array}
$$

如果这个关于 $\alpha$ 的抛物型二次三项式对所有的 $\alpha$ 而言都是非负的，则它的判别式必须为非正的实数值，从而给出下列不等式

$$
\begin{array} { r } { \Delta x \Delta p _ { x } \geq \frac { 1 } { 2 } \pmb { \varepsilon } _ { \mathrm { x } } } \end{array}
$$

$\Delta x \Delta p _ { x }$ 乘积的最小可能值为 $\frac { 1 } { 2 } \pmb { \varepsilon } _ { x }$ ，此时波包的波函数呈下列形式：

$$
\begin{array} { r } { \Psi = \frac { 1 } { ( 2 \pi ) ^ { 1 / 4 } \sqrt { ( \Delta x ) } } e x p \left( \frac { i } { \varepsilon } p _ { 0 } x - \frac { x ^ { 2 } } { 4 ( \Delta \mathbf { x } ) ^ { 2 } } \right) } \end{array}
$$

其中 $\mathtt { p } _ { 0 }$ 和 $\Delta x$ 都是常数，这个态中的坐标概率值为

$$
\begin{array} { r } { | \Psi | ^ { 2 } = \frac { 1 } { \sqrt { ( 2 \pi ) } \cdot \Delta x } e x p \left( - \frac { ( x - \bar { x } ) ^ { 2 } } { 2 ( \Delta x ) ^ { 2 } } \right) } \end{array}
$$

这是对称于原点（平均值 $\bar { x } = 0$ ）的高斯分布,标准偏差为 $\Delta x$ 。动量表象中的波函数为

$$
\begin{array} { r } { \Psi ( p _ { x } ) = \frac { 1 } { \sqrt { 2 \pi \varepsilon _ { x } } } \int _ { - \infty } ^ { \infty } \Psi ( x ) e ^ { \left( -  { \left( i / \varepsilon _ { \mathrm { x } } \right) } x p _ { x } - \frac { ( p _ { x } - \overline { { p _ { x } } } ) ^ { 2 } } { 4 ( \Delta p _ { x } ) ^ { 2 } } \right) } d x } \end{array}
$$

算出上式积分并求概率得到

$$
\begin{array} { r } { \left| \Psi \right| ^ { 2 } = \frac { 1 } { \sqrt { ( 2 \pi ) } \cdot \Delta p _ { x } } \times \exp { \left( - \frac { ( p _ { x } - \overline { { p _ { x } } } ) ^ { 2 } } { 2 ( \Delta p _ { x } ) ^ { 2 } } \right) } } \end{array}
$$

动量的概率分布 $\left| \left| \Psi \right| \right| ^ { 2 }$ 也是一个对称于平均值 $\overline { { p _ { x } } } = p _ { x 0 }$ 的高斯分布，标准偏差为 $\Delta p _ { x } =$ $\varepsilon _ { x } / 2 \Delta x$ ，即 $\Delta p _ { x } \Delta x$ 乘积为 $\begin{array} { l } { { \displaystyle { \frac { 1 } { 2 } } \varepsilon _ { x } } } \end{array}$ 。

3.2.2引力作用图景与不确定性关系式

自然界存在的四种基本作用力，都是由粒子传递的：胶子传递强核力，W和Z玻色子传递弱核力，光子传递电磁力，而引力则由引力子（graviton）传递，前三种力的传递子均早已被实验探测到[23]。尽管万有引力在我们现实中的宏观世界无处不在，且又最早为人类所感知，但由于引力较比之前三种力非常微弱，引力子与物质的相互作用极不容易在实验中观察到。虽然爱因斯坦在1915年11月完成了他的引力场方程之后，继而就提出引力作用应由引力子传播、广义相对论中存在着波动解—一其波动方程具有与麦克斯韦具有相同的形式，亦即我们现在所知道的引力波[24]，可是直到2016年LIGO 团队才依靠激光干涉的方法在实验中探测到了由宏观星体所引发的引力波[25][26][27]。

宏观星体间引力作用状态的变化可引发引力波，微观世界非零质量的粒子之间同样具有引力作用，其运动状态的变化也必然带来引力作用能以波的形式辐射。在微观原子世界中，由于引力相互作用强度仅为电磁互作用强度的 $1 0 ^ { - 4 2 } { \sim } 1 0 ^ { - 3 6 }$ （质子/质子[23]、质子/电子、电子/电子间的量级比依次为 $1 0 ^ { - 3 6 }$ 、 $1 0 ^ { - 3 9 }$ 、 $1 0 ^ { - 4 2 }$ )，引力作用对于电磁互作用状态的影响完全不重要，其存在对于原子内电子电磁跃迁的影响可以忽略不计。但在考察电子的电磁跃迁对于引力作用状态的影响时，则应该承认这种影响不仅不能被忽略，并且还是决定性的—一电子在电磁跃迁的同时还决定着引力能级状态的改变。

以氢原子为例，其能级跃迁辐射光子的能量由下式：

$$
\underbrace { 2 \pi \mathrm { { h } } \nu } _ { \mathrm { n  m } } = \mathrm { E _ { n } ^ { e } - E _ { m } ^ { e } }
$$

来决定，式中2πhv为氢原子的核外电子从能级 $\mathfrak { n }$ 跃迁到能级 $\mathbf { m }$ 时所辐射光子的能量， ${ \mathrm { E } } _ { \mathrm { n } } ^ { \mathrm { e } } \setminus { \mathrm { E } } _ { \mathrm { m } } ^ { \mathrm { e } }$ n→m  
分别为氢原子第n、 $\mathbf { m }$ 级能级的电磁能量、 ${ \bf E } _ { \mathrm { i } } ^ { \mathrm { e } }$ 数值由下式决定

$$
\begin{array} { r } { \mathrm { E _ { i } ^ { e } = - \frac { 1 } { 4 \pi \varepsilon _ { 0 } } \frac { e ^ { 2 } } { 2 r _ { \mathrm { i } } } } } \end{array}
$$

式中 $\mathbf { r } _ { \mathrm { { i } } }$ 为氢原子第i电磁能级的平均轨道半径，e为电子电量。氢原子在由能级 ${ \bf E } _ { \mathrm { n } } ^ { \mathrm { e } }$ 跃迁到能级 $\mathrm { E } _ { \mathrm { m } } ^ { \mathrm { e } }$ 时释放出能量为2πhv的光子；与此同时，引力作用能也由能级 $\mathfrak { n }$ 的 ${ \bf E } _ { \mathrm { n } } ^ { \mathrm { g } }$ （与引力能级 $\mathfrak { n }$ 相应的引力作用能记为 $\mathrm { E _ { n } ^ { g } }$ ）变化到能级 $\mathbf { m }$ 的 $\mathrm { E _ { m } ^ { g } }$ （与引能级 $\mathbf { m }$ 相应的引力作用能记为 $\mathrm { E _ { m } ^ { g } }$ ），两能级之间引力作用能之差值同样只能以引力子的形式释放。该能级跃迁辐射的引力子能量由下式决定：

$$
\underbrace { 2 \pi \varepsilon \textrm { v } } _ { \mathrm { n  m } } = \mathrm { E _ { n } ^ { g } - E _ { m } ^ { g } }
$$

式中ε为质子（氢核）与电子间引力作用的基本作用量单元（若定义电子间引力作用互作用量ε为其基本作用量单元，氢原子核的质子为1836倍的电子质量，则有 $\underline { { \varepsilon } } { = } 1 8 3 6 ^ { - 1 } \varepsilon ^ { ' }$ ，暂未将中微子间引力作用计入讨论)。

定义：

$$
\mathrm { E _ { i } ^ { g } = - G \frac { m _ { p } \ m _ { e } } { 2 r _ { i } } }
$$

${ \bf E } _ { \mathrm { i } } ^ { \mathrm { g } }$ 为氢原子第i电磁能级的万有引力作用能， $\mathbf { G }$ 为万有引力常数， $\mathrm { m } _ { \mathrm { p } }$ 为质子（氢原子核）质量， $\mathrm { m } _ { \mathrm { e } }$ 为电子质量， $\mathbf { r } _ { \mathrm { { i } } }$ 为氢原子第i级电磁能级的平均轨道半径。由(23）、(25)式得到处于同一轨道的电磁作用能与引力作用能之比为：

$$
\scriptstyle \mathrm { E } _ { \mathrm { i } } ^ { \mathrm { e } } \displaystyle  \mathrm { E } _ { \mathrm { i } } ^ { \mathrm { g } } = \{ \frac { 1 \quad \mathrm { e } ^ { 2 } } { 4 \pi \varepsilon _ { 0 } 2 \mathrm { r } _ { \mathrm { i } } } \}  \mathrm { G } _ { \mathrm { ~ } 2 \mathrm { r } _ { \mathrm { i } } } ^ { \mathrm { m _ { p } ~ } \mathrm { m _ { e } } }  \approx 1 0 ^ { 3 9 }
$$

电子由第 $\mathfrak { n }$ 能级跃迁到第 $\mathbf { m }$ 能级时电磁辐射子与引力辐射子能量之比：

$$
\begin{array} { r l } & { \underbrace { 2 \pi \hbar \nu } _ { \mathrm { n  m } } \bigg / \underbrace { 2 \pi \dot { \nu } \nu = \hbar / \dot { \varepsilon } } _ { \mathrm { n  m } } = \{ \frac { 1 } { 4 \pi \varepsilon _ { 0 } 2 \Gamma _ { \mathrm { n } } } \begin{array} { c } { 1 \mathrm { e } ^ { 2 } } \\ { 4 \pi \varepsilon _ { 0 } 2 \mathrm { r _ { m } } } \end{array} \} \bigg / \{ \mathrm { G } _ { \mathrm { \mu _ { \ge } } \mathrm { m } _ { \mathrm { e } } } ^ { \mathrm { m } _ { \mathrm { p } } \mathrm { m } _ { \mathrm { e } } } - \mathrm { G } _ { \mathrm { \mu _ { \ge } } \mathrm { m } _ { \mathrm { m } } } ^ { \mathrm { m } _ { \mathrm { p } } \mathrm { m } _ { \mathrm { e } } } \} \approx 1 0 ^ { 3 9 } \mathrm { \Omega } } \\ & { \qquad = > \dot { \varepsilon } ^ { \mathrm { ' } } = 1 0 ^ { - 3 9 } \hbar } \end{array}
$$

将 $\pmb { \varepsilon } \mathrm { = } 1 8 3 6 ^ { - 1 } \pmb { \varepsilon } ^ { \prime }$ 和(28)式代入(17)式，得到引力作用图景下的不确定关系式(17a):

$$
\Delta \mathrm { x } \Delta p _ { x } \ge \mathfrak { E _ { / 2 } } \approx 1 0 ^ { - 4 2 } ^ { \mathtt { h } } \big / _ { 2 } \ll ^ { \mathtt { h } } / _ { 2 }
$$

与电磁作用图景下讨论的情况相同，当在引力作用图景中 $\mathbf { x }$ 与 $p _ { x }$ 为高斯分布时，电子位置与动量不确定度之积为：

$$
\Delta \mathrm { x } \Delta p _ { x } = { \varepsilon _ { / } } _ { 2 } \approx 1 0 ^ { - 4 2 } { } ^ { \mathrm { \hbar } } / _ { 2 } \ll { } ^ { \mathrm { \hbar } } / _ { 2 }
$$

在万有引力作用图景下，运用与现行量子力学结构形式相同的数学工具，对一个微观粒子的力学状态进行描述时，得到了与电磁作用图景下数学形式完全一致的波涵数和不确定度关系式一一力学量的统计分布形态以及不确定度关系式的下限由万有引力基本作用量单元决定。引力作用图景对微观粒子的力学状态的描述，力学量的统计分布更集中，若以图像表示、相应共轭力学量的概率分布曲线更锐利，共轭力学量的不确定度的下限也更低—一引力作用图景的不确定度关系式(17a): $\Delta x _ { 2 } \Delta p _ { x 2 } \ge { \varepsilon _ { / } } _ { 2 } \approx 1 0 ^ { - 4 2 } { \^ { \mathtt { h } } } / { } _ { 2 } \ll { ^ { \mathtt { h } } } / { } _ { 2 }$ 其下限 $\varepsilon _ { / _ { 2 } }$ 仅为电磁作用图景下限 $\mathfrak { h } _ { / _ { 2 } }$ 的 $1 0 ^ { - 4 2 }$ ，远远突破了关系式（1）的下限。所以，较比电磁作用图景，引力作用图景给微观粒子力学状态的描述提供了更准确工具。

# 3.3虚拟作用图景的分析与微观粒子状态的确定性判则

3.3.1虚拟作用图景的分析

为了考察处于自由运动状态的微观粒子，构造基本作用量单元为 $\{ \varepsilon _ { \mathrm { x i } } \}$ 的虚拟作用图景$\{ \mathrm { X } _ { \mathrm { i } } \}$ 序列，其相应基本作用量单元序列 $\{ \varepsilon _ { \mathrm { x i } } \}$ （ $\mathrm { i } = 1 , 2 , 3 ^ { \cdots } \mathrm { n } ^ { \dots } )$ 元素间有下式的关系：

$$
\varepsilon _ { \mathrm { x 1 } } > \varepsilon _ { \mathrm { x 2 } } > \varepsilon _ { \mathrm { x 3 } } > . . . > \varepsilon _ { \mathrm { x n } } >  \cdots  0
$$

即：

$$
\operatorname* { l i m } _ { \mathrm { n \to \infty } } \mathfrak { E } _ { \mathrm { x n } } = 0
$$

由3.2.1条的推导可知，待定作用图景下微观粒子位置 $\mathbf { x }$ 与动量 $p _ { x }$ 的均方根差间存在的约束关系式：

$$
\begin{array} { r } { \Delta x \Delta p _ { x } \geq \frac { 1 } { 2 } \pmb { \varepsilon } _ { \mathrm { x } } } \end{array}
$$

在 $\mathbf { x }$ 与 $p _ { x }$ 为高斯分布时，坐标与动量不确定度之积满足下式：

$$
\begin{array} { r } { \Delta x \Delta p _ { x } = \frac { 1 } { 2 } \mathfrak { E } _ { \mathrm { x } } } \end{array}
$$

设虚拟作用图景 $\{ \mathrm { X } _ { \mathrm { i } } \}$ 下，微观粒子力学量位置 $X _ { \mathrm { i } }$ 与动量 $p _ { x i }$ 为高斯分布，此时有：

$$
\begin{array} { r } { \Delta x _ { \mathrm { i } } \Delta p _ { x i } = \frac { 1 } { 2 } \pmb { \varepsilon } _ { x \mathrm { i } } } \end{array}
$$

对应基本作用量单元 $\{ \varepsilon _ { \mathrm { x i } } \}$ 序列式(29)，有下面关系式成立：

$$
\Delta x _ { 1 } \Delta p _ { x 1 } > \Delta x _ { 2 } \Delta p _ { x 2 } > \Delta x _ { 3 } \Delta p _ { x 3 } > { } ^ { \cdots } \Delta x _ { \mathrm { n } } \Delta p _ { x n } > { } ^ { \cdots  } 0
$$

即：

$$
\operatorname* { l i m } _ { \mathfrak { n } \to \infty } \Delta x _ { \mathfrak { n } } \Delta p _ { x n } = 0
$$

当 $\mathbf { n }  \infty$ 时， $\operatorname* { l i m } _ { \mathfrak { n } \to \infty } \mathfrak { E } _ { \mathrm { x n } } = 0$ 时，由作用量定义可得：n→8

$$
\begin{array} { c } { \displaystyle \operatorname* { l i m } _ { \mathfrak { n } \to \infty } \Delta x _ { \mathfrak { n } } = 0 } \\ { \displaystyle \operatorname* { l i m } _ { \mathfrak { n } \to \infty } \Delta p _ { x n } = 0 } \end{array}
$$

此时，微观粒子的动量与位置波函数也随之演化至两个δ函数[28][29]：

$$
\begin{array} { r } { \displaystyle \operatorname* { l i m } _ { \Delta x _ { \mathfrak n } \to 0 } | \Psi | = \operatorname* { l i m } _ { \Delta x _ { \mathfrak n } \to 0 } \left| \frac 1 { ( 2 \pi ) ^ { 1 / 4 } \sqrt { ( \Delta x _ { \mathfrak n } ) } } e x p \left( - \frac { i } { \mathfrak E _ { \mathrm { x n } } } \overline { { p _ { x \mathfrak n } } } x _ { \mathfrak n } - \frac { { x _ { \mathfrak n } } ^ { 2 } } { 4 ( \Delta x _ { \mathfrak n } ) ^ { 2 } } \right) \right| = \delta ( \Delta x _ { \mathfrak n } ) } \\ { = 0 ) \qquad \mathrm ( 3 5 ) } \\ { \displaystyle \operatorname* { l i m } _ { \mathfrak E _ { \mathrm { x n } } \to 0 } | \Psi | = \operatorname* { l i m } _ { \mathfrak E _ { \mathrm { x n } } \to 0 } \left| \frac 1 { ( 2 \pi ) ^ { 1 / 4 } \sqrt { \varepsilon _ { \mathrm { x n } } } } \int _ { - \infty } ^ { \infty } \Psi ( x _ { \mathfrak n } ) e x p \left( - \frac { i } { \mathfrak E _ { \mathrm { x n } } } x _ { \mathfrak n } p _ { x \mathfrak n } - \frac { ( p _ { x \mathfrak n } - \overline { { p _ { x \mathfrak n } } } ) ^ { 2 } } { 4 ( \Delta p _ { x \mathfrak n } ) ^ { 2 } } \right) d x _ { \mathfrak n } \right| = \delta ( \varepsilon _ { \mathrm { x n } } \overleftarrow { p _ { \mathrm { x } } } ) } \\ { = 0 \qquad \mathrm ( 3 6 ) \qquad \mathrm ( 3 6 ) } \end{array}
$$

这样，就在微观粒子的状态描述中获得了位置 $x$ 与动量 $p _ { x }$ 的确定值。由此可得到微观粒子运动状态的确定性判则如下。

3.3.2微观粒子力学状态的确定性判则

构造基本作用量单元 $\{ \varepsilon _ { x i } \}$ ，实现虚拟作用图景 $\{ \mathrm { X } ( \varepsilon _ { x i } ) \}$ 作用量的量子化。依次以基本作用量单元序列元素 $\{ \varepsilon _ { \mathrm { x i } } \}$ 单调递减的虚拟作用图景 $\{ \mathrm { X } _ { \mathrm { i } } \}$ （其中 $\mathrm { i } { = } 1$ 代表电磁作用图景， $\mathrm { i } { = } 2$ 代表万有引力作用图景， $\mathrm { i } { = } \mathrm { n }$ 表示作用量渐次递减的各虚拟作用图景序列）对任一微观粒子力学状态进行的描述，所构造作用图景 $\{ \mathrm { X } _ { \mathrm { i } } \}$ 的基本作用量单元 $\{ \varepsilon _ { \mathrm { x i } } \}$ 系列有以下关系：

$$
\varepsilon _ { \mathrm { x } 1 } > \varepsilon _ { \mathrm { x } 2 } > \varepsilon _ { \mathrm { x } 3 } > . . . > \varepsilon _ { \mathrm { x } \mathrm { n } } > \dots  0
$$

亦即：

$$
\operatorname* { l i m } _ { \mathrm { n \to \infty } } \varepsilon _ { \mathrm { x n } } = 0
$$

当基本作用量单元 $\{ \varepsilon _ { x i } \}$ 序列取 $\mathrm { ~ n \to \infty ~ }$ 的极限时，微观粒子动量与位置的波函数随之演化至两个8函数，位置与动量的确定值则为相应作用图景下力学量的平均期望值，由此获得到该微观粒子力学状态的准确描述，微观粒子力学状态的客观确定性得以判定。

# 3.4玻尔与爱因斯坦关于光子箱论辩的回顾与检视分析

3.4.1玻尔关于爱因斯坦光子箱的论证

1930年10月20日至25日，在布鲁塞尔举行的第六届索尔维会议上，爱因斯坦提出著名的光子箱思想实验。爱因斯坦认为由于光子发射时 $\mathrm { \Delta T _ { a } }$ 和光子能量E这两种测量是独立和互不干扰的，测量精确度没有相互制约，所以实验会破坏不确定性式关系 $\Delta \mathrm { T } \cdot \Delta \mathrm { E } \geq \mathrm { h }$ ，从而可以证明“量子力学是不自洽的”。但玻尔在本次会议上又对爱因斯坦设计的思想实验进行了成功的反论证，当年绝大部分与会的科学家们以及后来几乎所有的有关学者也都接受了玻尔所持的观点[1][8][16]。

玻尔在会议上对光子箱思想实验的测量过程的分析如下[16]首先在光子逸出时，光子箱获得一个向上的动量P

$$
\begin{array} { r } { \mathbf { p } \leq \mathbf { T } _ { \mathbf { b } } \frac { E } { c ^ { 2 } } \mathbf { g } } \end{array}
$$

${ \mathrm { { T } } } _ { \mathrm { { b } } }$ 为光子箱自光子释放开始至达到新的平衡位置所需时间。而光子箱获得动量P的不确定

值△p为

$$
\begin{array} { r } { \Delta \mathbf { p } \leq \mathbf { T } _ { \mathbf { b } } \frac { \Delta E } { c ^ { 2 } } \mathbf { g } } \end{array}
$$

光子逸出前后，光子箱的两次平衡位置之差 $\Delta \mathbf { x }$ 是和 $\Delta { \mathfrak { p } }$ 有关的， $\Delta \mathbf { x } , \ \Delta \mathbf { p }$ 满足 (39)式

$$
\textstyle \Delta { \mathfrak { p } } \geq { \frac { h } { \Delta x } }
$$

因此，由 (38)&(39)推出

$$
\begin{array} { r } { \mathrm { h } \leq \mathrm { T } _ { \mathrm { b } } \frac { \Delta E } { c ^ { 2 } } \Delta x \mathbf { g } } \end{array}
$$

Tb的测量不确定值是由于位置不确定度 $\triangle \mathbf { x }$ 导致引力势不同从而影响钟表快慢所致，根据引力红移公式

$$
\begin{array} { r } { \frac { \Delta \mathrm { T } _ { \mathrm { b } } } { \mathrm { T } _ { \mathrm { b } } } = \mathbf { g } \frac { \Delta x } { \mathrm { c } ^ { 2 } } } \end{array}
$$

将(41)代入(40)即得出不确定性（原理）关系式

$$
\Delta \mathrm { E } \cdot \Delta \mathrm { T } _ { \mathrm { b } } \geq \mathrm { h }
$$

至此，会议上玻尔总结说光子箱思想实验的时间/能量测量同样满足不确定性（原理）关系式(42)式 $\Delta \mathrm { E } \cdot \Delta \mathrm { T } _ { \mathrm { b } } \geq \mathrm { h }$ ，并进一步说明量子力学是自洽的。玻尔的论证说服了除爱因斯坦之外的绝大部分与会者。

3.4.2对玻尔的论证的检视分析玻尔的论证过程，存在以下几个问题。

$\textcircled{1}$ 第一、整个论证过程数学符号涵义前后不一致

在“光子逸出前后，光子箱的两次平衡位置之差 $\Delta \mathbf { x }$ 是和△p 有关的， $\Delta \mathbf { x }$ 与 $\Delta { \mathfrak { p } }$ 满足(39)$\textstyle \Delta { \mathfrak { p } } \geq { \frac { h } { \Delta x } } ^ { , \prime \prime }$ $^ { 6 6 } \Delta \mathbf { x } ^ { \prime \prime }$ 位置不确定度 $\triangle \mathbf { x }$ 导致引力势不同从而影响钟表快慢所致，根据引力红移公式(41)式 $\begin{array} { r } { | \frac { \Delta \mathrm { T } _ { \mathrm { b } } } { \mathrm { T } _ { \mathrm { b } } } = \begin{array} { r l } \end{array} } \end{array}$ ”中的“△x”又用来表示位置不确定度。事实上光子箱两次平衡位置之差与其位置不确定度二者并不相同。

第二、玻尔论证过程中存在逻辑循环的问题：为了证明时间-能量的不确定性（原理）关系，玻尔在“光子逸出前后，光子箱的两次平衡位置之差 $\Delta \mathbf { x }$ 是和 $\Delta { \mathfrak { p } }$ 有关的，Δx、 $\Delta { \mathfrak { p } }$ 满足不确定性（原理）关系式(39)”中先验地断定并引入位置-动量不确定性（原理）关系式的变体△p≥。

{实际上，对于相对论性光子，若 $\begin{array} { r } { \{ \Delta x \Delta p \geq h \} } \end{array}$ 成立，直接由 $\begin{array} { r } { \langle \Delta x \Delta p \ge h \ 3 \Rightarrow \{ \frac { \Delta x } { c } \cdot \Delta p \cdot c \ge h \} } \end{array}$ $\begin{array} { r } { \Rightarrow \ \langle \Delta t \cdot \left( \frac { h } { \lambda _ { 1 } } \cdot c - \frac { h } { \lambda _ { 2 } } \cdot c \right) \geq h \ \rangle \Rightarrow \ \langle \Delta t \cdot \left( E _ { 1 } - E _ { 2 } \right) \geq h \ \rangle \Rightarrow \ \langle \Delta t \cdot \Delta E \geq h \ \rangle , } \end{array}$ 位置-动量与时间-质量关系式是等价的。此处玻尔先验地断定并引入式(39)属于不证自引，在论证逻辑上存在问题。 $\Bigg \{$ ：

玻尔对光子箱思想实验的论证过程中存在数学符号涵义前后不一、违背概念涵义的前后一贯性原则，且有循环论证之嫌，所作论证并非有效论证，其对于时间-能量的测量不确定度作出满足不确定性（原理）关系式的结论也不一定成立。

$\textcircled{2}$ 从公式(37)导出(38)式是错误的。若定义

$$
\begin{array} { r } { { \bf p } = \mathrm { T } \frac { \mathrm { E } } { \mathrm { c } ^ { 2 } } { \bf g } } \end{array}
$$

忽略高阶小量、可以得到

$$
\begin{array} { r } { \Delta \mathbf { p } = \Delta \mathbf { T } \frac { \mathrm { E } } { \mathrm { c } ^ { 2 } } \mathbf { g } + \mathrm { T } \frac { \Delta \mathrm { E } } { \mathrm { c } ^ { 2 } } \mathbf { g } } \end{array}
$$

所以从光子逸出时光子箱获得一个向上的动量 $\mathrm { ~ \bf ~ P ~ }$ 表达式得出动量的不确定值 $\Delta \mathsf { P }$ 表达式即由{式 （37) $\mathfrak { p } \le \mathrm { T } \frac { \mathtt { E } } { \mathrm { c } ^ { 2 } } \ \mathbf { g } \ \} \Rightarrow \ \mathrm { i }$ 式 $\begin{array} { r } { ( 3 8 ) \Delta \mathfrak { p } \le \mathrm { T } \frac { \Delta \mathrm { E } } { \mathrm { c } ^ { 2 } } \mathbf { g } \ \} } \end{array}$ （204号

的推导不成立。

$\textcircled{3}$ 关于“光子箱的两次平衡位置之差 $\Delta \mathbf { x }$ 和 $\Delta { \mathfrak { p } }$ 有关，存在{式(39) $\begin{array} { r } { \Delta \mathbf { p } \geq \frac { \mathrm { h } } { \Delta \mathbf { x } } ~ \} } \end{array}$ ”

设光子箱牵引簧的弹性系数为 $\mathbf { k }$ 、光子能量为E，则由质能方程可得光子箱释放光子前后两次平衡位置之差

此处位置之差 $\Delta \mathbf { x }$ 取决于光子能量E、与来源不明的 $\Delta { \mathfrak { p } }$ 并无关系， $\Delta \mathbf { x } , \ \Delta \mathbf { p }$ 二者不受关

系式(39)式 $\begin{array} { r } { \Delta \mathfrak { p } \geq \frac { \mathrm { h } } { \Delta \mathrm { x } } } \end{array}$ 的约束；同时玻尔在此处把数学形式的 $\Delta \mathfrak { p } \geq \frac { \mathrm { h } } { \Delta \mathrm { x } } ,$ 作为论据引入值得商榷，其中存在的逻辑循环问题如2.1条所述。

$\textcircled{4}$ 光子箱完成两次平衡位置之间过渡所需时间 ${ \mathrm { { T } } } _ { \mathrm { { b } } }$ 的测量

引力红移导致时钟变慢，记由此效应产生的 ${ \mathrm { { T } _ { b } } }$ 的变化量为 $\Delta \mathrm { T } _ { \mathrm { b 0 } }$ ， $\Delta \mathrm { T } _ { \mathrm { b 0 } }$ 的大小由光子箱释放光子前后的平衡位置之差 $\Delta \mathbf { x }$ 决定，由引力红移公式可得：

$$
\Delta \mathrm { T } _ { \mathrm { b 0 } } { = } \mathrm { T } _ { \mathrm { b } } \frac { \mathrm { g } \Delta \mathrm { x } } { \mathrm { C } ^ { 2 } }
$$

$\Delta \mathrm { T } _ { \mathrm { b 0 } }$ 为由(46)式可得到的确定量、尽管未知，不可以引入作为时间的不确定度。

记光子箱的位置不确定度为 $\Delta \mathbf { x } ^ { ' }$ ，由光子箱称重时对其平衡位置进行测量引发的扰动产生。Ax会引起引力势变化不确定，从而导致钟表快慢变化的不确定，由此带来的时间 ${ \mathrm { T } } _ { \mathrm { b } }$ 测量的不确定度应为

$$
\Delta \mathrm { T } _ { \mathrm { b } } = \mathrm { T } _ { \mathrm { b } } \frac { \mathrm { g } \Delta \mathrm { x } ^ { ' } } { \mathrm { C } ^ { 2 } }
$$

并非是非玻尔论证中的

$$
\begin{array} { r l } { \frac { \Delta \mathrm { T } _ { \mathrm { b } } } { \mathrm { T } _ { \mathrm { b } } } = \mathrm { g } \frac { \Delta \mathrm { x } } { \mathrm { c } ^ { 2 } } } & { { } \mathrm { \{ \ A \mathrm { } \mathrm { } \mathrm { / } \Delta \mathrm { T } _ { \mathrm { b } } = \mathrm { T } _ { \mathrm { b } } \frac { \mathrm { g } \Delta \mathrm { x } } { \mathrm { c } ^ { 2 } } } } \end{array} \}
$$

光子箱称重，通过测定光子箱指针在与其位移方向（定义为X）平行的标尺上的位置来实现。记与光子箱位移方向X相垂直的水平面内有方向 $\mathrm { Y }$ ，在对光子箱的位置测量时光沿此Y方向照射光子箱指针标尺，该过程给光子箱带来的冲量为 $\mathbf { P } _ { \mathrm { y } }$ ， $\mathrm { \sf P _ { y } }$ 沿着与X向相垂直的Y方向。照射光在X方向上的分量 $\mathrm { \bf P _ { x } }$ 为 $0 ^ { + }$ ，因此光子箱位置测量过程对处于平衡状态光子箱在X向位置零影响。所以在对光子箱前后两次平衡位置的测量/称重时，照射光对光子箱扰动所带来的X向位置不确定度 $\Delta \mathrm { x } ^ { ' } = 0 ^ { + }$ 。

尽管光子箱称重时间 ${ \mathrm { { T } _ { b } } }$ 可以任意长，但 $\mathrm { { . r _ { b } } }$ 为一有限量，由 $\begin{array} { r } { \langle \Delta x ^ { \prime } = 0 ^ { + } \lambda \Rightarrow \{ \frac { \Delta T _ { b } } { T _ { b } } = g \frac { \Delta x ^ { \prime } } { c ^ { 2 } } = 0 ^ { + } } \end{array}$ ， $\Delta E = \Delta \dot { x ^ { * } } k c ^ { 2 } \big / g = 0 ^ { + } \lambda \Rightarrow \langle \Delta T _ { b } = 0 ^ { + }$ ， $\Delta E { = } 0 ^ { + } \} { \Longrightarrow } \ \langle \Delta E \cdot \Delta T _ { b } = 0 ^ { + } \}$ ，强烈破坏海森堡时间-能量不确定性（原理）关系式即(42)式的 $\Delta \mathrm { E } \cdot \Delta \mathrm { T } _ { \mathrm { b } } \geq \mathrm { h }$ 。

$\textcircled{5}$ 依照玻尔的论证逻辑本文进行的再论证

假设：

$\left( - \right)$ 玻尔关于光子箱思想实验的时间/能量不确定性（原理）关系式成立

$$
\Delta \mathrm { E } \cdot \Delta \mathrm { T } _ { \mathrm { b } } \geq \mathrm { h }
$$

$\left( \stackrel { - } { - } \right)$ 当E与 $\mathrm { { T _ { b } } }$ 为高斯分布，有下式成立

$$
\Delta \mathrm { E } \cdot \Delta \mathrm { T } _ { \mathrm { b } } = \mathrm { h }
$$

记 $\Delta { \bf x } _ { 1 }$ 为光子箱释放光子时间 $\mathrm { { T _ { a } } }$ 内的位移

$$
\begin{array} { r } { \Delta \mathbf { x } _ { 1 } = \frac { \mathrm { ~ E ~ } } { 6 \mathrm { M C } ^ { 2 } } \mathbf { T } _ { \mathrm { a } } ^ { 2 } } \end{array}
$$

$\Delta \mathbf { X } _ { 1 }$ 小于称重过程光子箱的总位移 $\Delta \mathbf { x }$ 即 $\Delta \mathrm { x } _ { 1 } < \Delta \mathrm { x }$ 0

由引力红移公式式

$$
\begin{array} { r } { \frac { \Delta \mathrm { T } _ { \mathrm { b } } } { \mathrm { T } _ { \mathrm { b } } } = \bf { g } \frac { \Delta \Delta x } { c ^ { 2 } } } \end{array}
$$

可得到光子箱释放光子时间 $\mathrm { \Delta T _ { a } }$ 的不确定度 $\Delta \mathrm { T _ { a } }$ 满足

$$
\begin{array} { r } { \frac { \Delta \mathrm { T } _ { \mathrm { a } } } { \mathrm { T } _ { \mathrm { a } } } = \mathbf { g } \frac { \Delta \mathrm { x } _ { 1 } } { \mathrm { c } ^ { 2 } } } \end{array}
$$

因光子箱释放光子时间 $\mathrm { { T _ { a } } }$ 极短、光子箱称重过程的时间 ${ \mathrm { { T } } } _ { \mathrm { { b } } }$ 任意长，即 $\mathrm { T _ { a } \ll T _ { b } }$ ，又同时有 $\Delta \mathrm { x } _ { 1 } <$ Δx 成立，所以

$$
\begin{array} { r l } & { \Delta  { \mathrm { T } _ { a } } \ll \Delta  { \mathrm { T } _ { b } } } \\ { \Rightarrow } & { \Delta  { \mathrm { E } } \cdot \Delta  { \mathrm { T } _ { a } } \ll \Delta  { \mathrm { E } } \cdot \Delta  { \mathrm { T } _ { b } } } \end{array}
$$

在（二）中已设E满足高斯分布，即 (42a)式 $\Delta \mathrm { E } { \cdot } \Delta \mathrm { T } _ { \mathrm { b } } = \mathrm { h }$ ，所以预言光子箱释放的光子到达远方的时间/能量不确定性关系式满足(43a)式△E· $\Delta \mathrm { T } _ { \mathrm { a } } \ll \mathrm { h }$ ，该结果与 $\textcircled{4}$ 条的 $\left. \Delta E \cdot \Delta T _ { b } = \right.$ $0 ^ { + } \ : \boldsymbol { \jmath }$ 式一样，明显强烈破坏海森堡不确定性（原理）关系式(42)，与玻尔的论证相互矛盾。

通过以上的分析论证可以看出，玻尔对光子箱思想实验的论证只是对光子箱单一称重测量过程的笼统论述，没有包含光子箱释放光子过程的分析，论证不全面。同时玻尔的论证还存在逻辑循环和数学符号涵义的前后矛盾，最重要的是若对玻尔所得结论作进一步的逻辑推延，必定导致玻尔所论证成立的海森堡时间-能量不确定性（原理）关系式(42)和式(42a)均被强烈破坏，最后结果自相矛盾。因而，玻尔在第六届索尔维会议上关于光子箱思想实验的分析论证和作出的攸关海森堡不确定性（原理）关系式 $\Delta \mathrm { E } \cdot \Delta \mathrm { T } \geq \mathrm { h }$ 是否成立及量子力学正统诠释是否自洽与逻辑一贯性的结论无法成立。

除了未考虑引力红移效应，爱因斯坦关于光子箱思想实验的设计没有内在矛盾，该思想实验可有效证伪玻尔于会议上关于海森堡不确定性原理和量子力学正统诠释自洽与逻辑一贯性的论证。尽管经过本次索尔维会议玻尔的成功反论证，爱因斯坦没再重提量子力学的自洽性问题，但实际上爱因斯坦对玻尔之说始终并未认同；并且，应该注意到玻尔从1930 年索尔维会议结束到1962年去世，一直反复回到爱因斯坦光子箱思想实验这个问题上来。人们发现，在玻尔离世的当天他工作室的黑板上还有他头天晚上所画的爱因斯坦光子箱思想实验装置示意图。这应该可以说明玻尔内心可能并不认为自己在攸关量子力学正统诠释是否自洽与逻辑一贯的这一核心问题上已彻底说服了爱因斯坦[——纵然当年索尔维会议的绝大多数与会者都曾认为那场论辩是以玻尔胜利而告终并接受了玻尔的观点。

# 4进一步的讨论

作为一个由量子力学方程及伴随的概念、观念所构成的物理学理论体系[4，现行量子力学理论是在电磁作用图景下，以普朗克常数h为基本作用量单元、共轭力学量的傅里叶变换为纽带，运用统计波函数、算符和哈密顿正则方程等元素构建的数学形式体系，以实现对微观粒子运动状态的统计意义上的描述，不确定性关系则是量子力学数学形式体系的一个自然推论。

作为量子力学形式体系的直接推论，统计诠释下的不确定性关系式度量了现行量子理论的描述能力。而非统计诠释关于量子理论的描述能力与实验测量手段在精度上的相容性判断仅仅是一个主观性的理论断言，已被前文数学上的概率分析和对爱因斯坦光子箱思想实验的再次检视所否定；并且这种主观的相容性判断及其关于量子理论工具能力的描述，与微观粒子的位置/动量是否同时具有确定值、与微观客体力学状态的客观性/确定性无关。理论断言的不确定性与不确定性的理论断言只属于理论自身。

能否在现行量子理论的统计性描述中获得对微观粒子力学状态的客观、确定性的知识？本文得到的确定性判则运用量子力学形式体系之数学工具对于不同作用图景的通用性，在高斯分布条件下，通过现行量子力学电磁作用图景与所引入的量子化虚拟作用图景、引力作用图景共同构成作用图景集合，对作用图景集合相应的基本作用量单元序列取极限（与其对应的不确定性关系式下限具有结构形式的同一性)，以消除作用图景之统计模糊与不确定对微观粒子力学状态呈现相的影响，从而获得其运动状态的真实、准确描述。确定的客观性与客观的确定性属于被描述的微观粒子。

运用确定性判则对微观粒子力学状态进行客观确定性判定时，显示微观粒子波函数的形态随基本作用量单元序列 $\{ \pmb { \varepsilon } _ { x i } \}$ 元素趋向极限的过程而同步演化。各力学量所具有的明确演化终点表明，在演化起点与演化过程中表现出来的、非统计诠释指称的量子几率性，实际是微观粒子力学状态呈现相之统计描述中的概率。

对于微观粒子，没有相互作用就不会产生物理效应，没有物理效应就没有相应的物理呈现相描述，量子现象包括波粒二象性都同样如此。场在时域与空间分布（属有序的统计累积）的波动性、作为能量吸收或辐射单元的粒子性，粒子在时域与空间存在的个体奇异性-粒子性、统计（属粒子在作用图景中呈现的无时序累积）呈现的波动性，以及场与粒子都存在的波粒二象性，皆是通过粒子与作用图景场之间的相互作用而得以呈现。没有粒子与场之间的相互作用，粒子不会显现波动性、场和波也不会显现粒子性；没有相互作用在时域或者空间存在的累积，就没有统计性的波动的显现，粒子与波都不会有波粒二象性的呈现，波动性、粒子性以及波-粒二象性皆为互作用呈现相。

物理世界是因果决定性的还是本质上的几率性与不确定？在量子力学形成之前，对于选择前者的回答几乎没什么异议；但在量子力学诞生尤其是不确定性原理提出之后，这却成为困扰量子力学乃至物理学的一个根本性的问题。由于量子力学的数学形式体系工具在相关技术领域的广泛应用和获得的巨大成功，伴随1930年索尔维会议之后哥本哈根学派非统计诠释在量子力学理论中止统地位的稳固确立，否定因果决定性、失去对客观实在性的坚持所造成的影响已经波及物理学之外的自然学科乃至于社会人文领域[30]。量子力学正统诠释这种对实在性与因果决定性的放弃[1][30]受到了爱因斯坦、劳厄、薛定谔、德布罗意以及后来的玻姆等少数几位坚持实在论观点物理学家强烈一致的质疑与反对[I[2]，尤其是面对波尔直接提出了“上帝不掷骰子”的爱因斯坦，终其一生都在不断地对此进行拷问、质疑[。但是，由于自1930年的第六次索尔维会议之后，哥本哈根学派的量子力学非统计诠释在历史上很长的一个时期内一直占据着量子力学理论诠释的正统地位，导致绝大部分物理学家一度失去了对客观实在性、确定性与因果决定性的思考与坚持，以至于发生了时任国际力学联合会主席的 SirJamesLighthill以“在1960 年以前，我们认为世界是可预测的，但我们现在认识到我们散播的决定性的思想错了。”的言辞为以前用确定性误导了公众而代表力学界同仁向公众道歉[3][31的一幕，更甚至于出现了在严肃的科学研究中居然相信意识决定实在、未来的测量行为会改变现在物理状态等说法的现象[2]。究其原因，前文的分析显示其根源在于缺乏对非统计诠释下的不确定性关系式进行数学上的深度检视分析，同时也缺乏对电磁作用图景的类比扩展、对不同作用图景下微观粒子力学状态呈现相的考察和研究，缺乏对量子理论取得巨大成就的研究领域、研究对象的统计属性及电磁作用背景与量子理论自身工具属性的相关性分析，结果导致对微观粒子的客观实在性与量子理论断言的工具描述性、对客体力学状态的动态性/确定性与理论描述能力的有限性以及理论描述对象的客观性与作为描述工具的理论的主观性从属性之间的关系存在模糊认识。

理论对物理实在进行描述与度量，物理实在同时也实现了对理论的校验与反度量。客观实在既是作为工具的理论认识描述的目标对象，也是验证校准理论的工具与终极标尺；微观粒子量子客体与不确定性原理、与现行的量子理论，其关系亦同样如此。

# 5结论

# 5.1关于不确定性原理

(1)统计诠释是不确定性关系式在电磁作用图景下合乎逻辑的物理诠释。不确定性原理的非统计诠释存在逻辑矛盾、难以成立，非统计诠释下的量子力学理论同样不具有逻辑自洽性、也并非是“一个关于微观基元过程唯一逻辑一贯的物理理论”。

(2)在引力作用图景中，不确定度关系式的下限仅为电磁作用图景的 $1 0 ^ { - 4 2 }$ 的。若超出电磁作用图景，不确定性原理关系式（1）的断言以及现行量子力学理论的预言都不成立。

# 5.2关于确定性判则

(1)通过非电磁作用图景的引入，运用具有与现行量子力学结构形式相同的数学工具，得到的关于微观粒子力学状态的确定性判则显示微观粒子的力学状态具有客观确定性。

(2)客观确定性推论之一：现行量子力学理论之波函数是微观粒子力学状态在电磁作用图景下之统计呈现相的希尔伯特相空间表述。对于不同的作用图景，相应波函数的数学结构形式一致，唯一差别在于作为常数出现的量子化基本作用量单元；对于不同的虚拟作用图景，其波函数是相应作用图景之量子化基本作用量单元的因变量。

(3)客观确定性推论之二：量子力学的几率性并非微观粒子的内禀属性。非统计诠释指称的量子几率性，仅仅是微观粒子与作用图景之间互作用呈现相的统计概率。

# 5.3关于波粒二象性

波动性、粒子性以及波-粒二象性皆为粒子与作用图景场之间的相互作用呈现相。没有粒子与场之间的相互作用，粒子不会显现波动性，场和波也不会显现粒子性，粒子与波都不会有波粒二象性的显现。

# 6致谢

感谢北京理工大学李学文副教授、中国科学院电子学研究所李实研究员、吴谨研究员、王勇研究员、阴生毅研究员和旅美的李毅勇先生对本人在数学与物理方面所提供的诸多帮助，感谢北京邮电大学陈凌霄高工在文字录入方面付出的劳动。

# 参考文献

# 参考文献

[1]Jammer M. (translated by QIN Ke-Cheng) 1989 The Philosophy of Quantum Mechanics page1,73,73,126-186,94,73,73,84,76-78,67-100,78-79,76-78,97,87-90,126-186 U.S. (in Chinese)[M.雅默 著[美]（秦克诚译）1989 量子力学的哲学（北京：商务 印书馆印）第

1,73,73,126-186,94,73,73,84,76-78,67-100,78-79,76-78,97,87-90,126-186 页] {译 著} [2] SUN Chang-Pu Interpretation of Quantum Mechanics Physics.2017 Volume 468 P481-496(in Chinese)[孙昌璞 量子力学诠释问题 2017 物理.46卷 8期第 481-496页]{中文期刊} [3]CAO Ze-Xian's 2018 The physics of word chewingVolumes2(Hefei: China University of science and Technology Press), page 122-148 (in Chinese)[曹则贤 著 2018《物理学咬文嚼字》二卷（合肥：中国科学技术大学出版社）第122-148 页]{专著} [4] CAO Ze-Xian 2020 "What is Quantum Mechanics" Physics. Volume 49 (2020) Issue 2p91-100(in Chinese)[曹则贤《什么是量子力学》物理.49 卷 (2020 年)2期 第91-100 页]{中文期刊} [5] HAO Liu-Xiang Critical Review on the Interpretation of the Uncertainty Principle Journal of Dialectics of Nature 2019 Volume 41, Issue 12 (Total 256 Issues) P24-33 (in Chinese)[郝刘祥《不确定性原理的诠释问题》自然辩证法通讯2019第 41 卷 第12期（总 256期）第 24-33页]{中文期刊} [6]W. Heisenberg(translated by WANG Zheng-Xing, LI Shao-Guang, ZHANG Yu)1983 Physical Principles of Quantum Theory, Beijing (Science Press), page 16,11-16,3,16-17,11-16,17,1-43,16,17-18,16-21(in Chinese)[W. Heisenberg 王正 行 李绍光 张虞 译1983《量子论的物理原理》北京（科学出版社）第 16,11-16,3,16-17,11-16,17,1-43,16,17-18,16-21 页] {译著} [7] ZENG Jin-Yan 2013Commemorates the 100th anniversary of the publication of Bohr's "The Great Trilogy" and the 1Ooth anniversary of the establishment of the Department of Physics at Peking University Physics•42Issue 9,No. 661-667[曾谨 言 纪念Bohr 的《伟大的三部曲》发表100 周年暨 北京大学物理专业建系 100 周年 物理·42卷 (2013年)9期第 661-667页] [8] J. Carver (edited and translated by Ge Ge) 2012 N. Bohr Collected Works, Volume 7 (East China Normal University Press) ppl72,225 (in Chinese)[J.卡耳外尔 编 戈革 译2012《尼尔斯玻尔集》七卷（上海：华东师大出版社）第172，225 页]{译著} [9] W. Heisenberg (translated by KA Xing-Lin and ZENG Jin-Yan) "Review on the Origin of Uncertainty Relationships" University Physics 1984 (08) p47-48 (in Chinese)[W.Heisenberg 著 喀兴林 曾谨言译《关于测不准关系渊源的评述》大 学物理1984（08）第47-48页]{中文期刊译作} [10] R.P. Feynman (translated by GUAN Hong) 2O12 The Nature of Physical Law (Hunan Science and Technology Press)U.S. P133 (in Chinese)[R.P. Feynman 著[ 美］关洪 译 2012《物理定律的本性》（长沙：湖南科学技术出版社）第133 页]{译著} [11] P.A.M. Dirac (translated by CHEN Xian-Heng) 1965 Principles of Quantum Mechanics (Beijing Science Press) Page 100 (in Chinese)[P.A.M.狄拉克 陈咸亨 译喀兴林校1965《量子力学原理》（北京:科学出版社）第100页]{译著} [12] N. Bohr (translated by YU Tao) 1964 Atomic theory and natural description M(Beijing: Commercial Seal)pp.43-46 (in Chinese)[N.Bohr 著（郁涛译） 1964.原子论和自然的描述（北京：商务印书馆）第43-46页]{专著} [13] N. Bohr (translated by YU Tao) 1978 "Atomic Physics and Human Knowledge

Papers Continued" (Beijing: Commercial Printing) P108 (in Chinese)[N.玻尔著 （郁韬译）1978《原子物理学和人类知识论文续编》（北京：商务印书馆） 第108页]{专著}   
[14] W.Heisenberg1967 “Quantum Theory and its Interpretation” Niels Bohr-His Life and Work as seen by his Friends and Colleagues S. Rozental ed.(North-Holland, Amsterdam; Wiley, New York)p.98]   
[15] translated by PAN Chuan-Kang 1980"Comparison of Classical Mechanics and Quantum Mechanics Uncertainty” Nanchang University JournalNo.03P1-12(in Chinese）（American Journal of Physics Vol.47No.11979）[潘传康译 程齐贤校 经典力学与量子力学不确定性的比较 南昌大学学报 1980 年03 期第1-12 页 （American Journal of Physics Vol.47 No.1 1979）]{中文期刊}   
[16] Zhang Li Ge Mo-Lin 2O00 Frontier Issues of Quantum Mechanics (Beijing: Tsinghua University Press) Page 32 {Monograph}[张礼 葛默林著 2000 量子力 学的前沿问题（北京：清华大学出版社）第 32页{专著}]   
[17] GUAN Hong 1983The Meaning of Uncertainty Relationship (Part I) University Physics (9)P2-4 (in Chinese)[关洪 测不准关系的意义（上）大学物理1983（9) 第 2-4页]{中文期刊}   
[18] GUAN Hong 1987Review of Heisenberg's "γ-ray Microscope" Thought Experiments University Physics Vol.3,N0.6,P18-26 (in Chinese)[关洪 对海森堡 “Y射线显微镜”思想实验的回顾大学物理 Vol.3,N0.6,1987第18-26 页]{中 文期刊}   
[19] HUANG Xiang-You 1996 Classical Analogy of Uncertain Relations Phys. Journal 45:No.3(in Chinese)[黄湘友 1996 不确定关系的经典类比物理学报 第45卷第3期第353-359页]{中文期刊}   
[20] Blohintsev (translates by YE Yun-Li, JIN Xing-Nan) 2016 Principles of Quantum Mechanics (Harbin Institute of Technology Press) 40,45(in Chinese)[布洛欣采夫 著（叶蕴理 金星南译）2016量子力学原理（哈尔滨工大出版社）第36,40,45 页]{译著}   
[21] Lev Davidovich Landau, Livschitz (translated by YAN Su) 2Oo8 Quantum Mechanics Non-Relativistic (Higher Education Press), page 1, 41 (in Chinese) [朗 道 栗弗席兹著（严肃译）2008 量子力学非相对论性（北京：高教出版社） 第1,41页]{译著}   
[22] C.Cohen-Tannoudji, Bernard Diu and Franck Laloé (translated by LIU Jia-Mo CHEN Xing-Kui) 2016 Quantum Mechanics Volume I (High Education Press)p42 (in Chinese)[科恩.塔诺季，迪于，拉洛埃（刘家谟，陈星奎译）2016量子力 学 第一卷（高教出版社）第42页]{译著}   
[23] YANG Zhen-Ning1998 "YANG Zhen-Ning Collection" (Shanghai: East China Normal University Press) Page 335 (in Chinese)[杨振宁著1998《杨振宁文集》 （上海：华东师大出版社）第335页]{专著}   
[24] A. Einstein (translated by XU Liang-Ying, LI Bao-Heng, ZHAO Zhong-Li, FAN Xin-Nian) 2018 Einstein's Anthology Volume I (Beijing: The Commercial Press), p427-444,U.S.(in Chinese)[A.爱因斯坦 著[美]许良英 李宝恒 赵中立 范岱 年 译 2018《爱因斯坦文集》第二卷（北京：商务印书馆）第427-444 页] {专著}   
[25] CAI Ronggen1\*, WANG Shaojiang1, YANG Runqiu2, ZHANG Yunlong3 2018 p2484-2498(in Chinese)[蔡荣根 $1 ^ { * }$ ，王少江1，杨润秋2，张云龙32018年引力 的本质 科学通报 第 63 卷第 24 期：第 $2 4 8 4 { \sim } 2 4 9 8$ 页]   
[26] ZHU Zong-Hong1 WANG Yun-Yong 2016 “Prediction,Detection and Discovery of Gravitational Waves”Physics. Volume 45 Issue 5 p300-310 (in Chinese)[朱宗宏1 王运永<引力波的预言、探测和发现 $>$ 物理45卷 (2016年)5 期第300-310页]   
[27]SHAO Li-Jing† 2019 “GW170817: Is Einstein Right? ” Physics·Volume 48 Issue9p567-572(in Chinese)[《GW170817：爱因斯坦对了吗？》邵立晶†物 理·48卷 (2019年)9 期第 567-572页]{中文期刊}   
[28] SHEN Hui-Chuan 1994"The Mathematical Structure and Physical Characteristics of the Double Wave Theory ofQuantum Mechanics" Science1994-03p42-44 (in Chinese)[沈惠川《量子力学双波理论的数学结构和 物理学特征》科学 1994年03 期第 42-44 页]{中文期刊}   
[29] HUANG Xiangyou2013 "Complete Quantum Mechanics"(Beijing: Science Press.)p50-58(in Chinese)[黄湘友 2013《完全性量子力学》科学出版社.北京第 50-58页]{专著}   
[30] WANG Zheng-Xing 2017 Summary of the History of Quantum Mechanics Science and Culture Review Volume 14, Issue 3p43-63 (in Chinese)[王正行 2017 量子力学创立历史概要科学文化评论第14卷第3期第 43-63页]{中文期刊}   
[31] James Lighthill, J. M. T. Thompson, A. K. Sen, et al. The Recently Recognized Failure of Predictability in Newtonian Dynamics [and Discussion]. 1986, 407(1832):35-50.