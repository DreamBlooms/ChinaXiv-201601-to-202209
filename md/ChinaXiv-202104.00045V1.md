# 两种新的多维计算机化分类测验终止规则

任赫 陈平

（北京师范大学中国基础教育质量监测协同创新中心，北京，100875）

摘要计算机化分类测验（Computerized Classification Testing,CCT）由于具备分类的功能，目前在职业资格考试、健康与护理问卷等以分类为目的的测验中得到广泛应用。作为CCT的重要组成部分，终止规则不仅决定测验停止的条件而且直接影响分类准确率及测验效率。然而，目前少有研究对多维CCT（MulitidimensionalCCT,MCCT）的终止规则进行探索。针对已有MCCT终止规则的不足，提出两种新的MCCT终止规则（即基于马氏距离的多维序贯似然比规则 Mahalanobis-SPRT 和随机缩减的多维广义似然比规则M-SCGLR)，并开展模拟研究在不同实验条件下（比如，不同的题库结构、能力维度间相关及分界函数）考查它们的表现。结果表明：（1）在使用补偿性分界函数的条件下，Mahalanobis-SPRT规则具有较高的分类精度和与同类方法相近的测验长度；（2）在几乎所有实验条件下，M-SCGLR规则不仅在测验精度上大幅优于已有的多维随机缩减规则，而且具有较短的测验长度。

关键词计算机化分类测验，终止规则，多维项目反应理论，马氏距离，随机缩减

# 1引言

计算机化分类测验（Computerized Classfication Testing,CCT）是一种特殊的计算机化自适应测验（ComputerizedAdaptive Testing,CAT)，它能够高效地将被试划分到两个（即达标和未达标)或多个（比如，合格、良好和优秀）不同的类别中。CCT将计算机作为测量媒介，使用自适应的选题策略和终止规则，基于被试当前的能力估计值精准地匹配测试题目，直到满足终止规则的要求，停止测验并提供对被试能力进行分类判断的结果。目前，这类测试已被广泛应用于职业资格考试(Huebner&Fina,2015)和健康与护理问卷(Finkelman etal.,2011;Smits&Finkelman,2013)，其中的健康与护理问卷可以针对某种疾病或与护理计划直接相关的某些阶段将患者划分至有风险/无风险的类别中。尽管可以将各种心理测量理论作为CCT的基础，但是近年来大多数研究与应用都将焦点集中在基于项目反应理论（Item ResponseTheory,IRT）的可变长度的 CCT研发上（Huebner& Fina,2015; Li et al.,2020; Wang et al.,2020)。

完整的CCT和CAT 均包括IRT模型、题库、选题策略、能力参数估计方法以及终止规则五个核心组成部分（郭磊 等,2015)。但是两者在测验目的上并不相同：CAT的目的是对被试能力进行准确估计（陈平,2016)，而CCT只需要输出对被试的类别划分。这就对测验的终止规则（也即测验应该如何停止以及如何给出测验结果）提出不同的要求，因此有必要对CCT 的终止规则进行单独研究。在可变长度的二分类测验的背景下，已有的CCT终止规则可以被分为两类：似然比规则和贝叶斯规则。似然比规则的基本思路是通过事先规定不同类别被试的真实能力分界值，来构造似然比统计量并进行假设检验，从而完成对被试的分类。最早的似然比终止规则是Wald（1947）提出的序贯似然比检验（Sequential Probability RatioTest,SPRT）。Bartroff等（2008）则将广义似然比（Generalized Likelihood Ratio,GLR）方法应用于变长的CCT中，并对GLR的良好性质进行证明。Thompson（2011）通过模拟研究发现：相比于 SPRT，GLR方法能够在维持分类精度的基础上较大幅度地提高测验效率（或缩短测验长度)。此外，研究者发现：由于受制于现实因素（比如疲劳效应、练习效应)，往往不可能要求被试一直作答直至满足 SPRT 的条件。在这种情况下，如果结合随机缩减（stochasticcurtailment）技术就有可能提高测验效率。由此，Finkelman（2003,2010）在 SPRT的基础上结合随机缩减技术,开发出随机缩减的 SPRT(Stochastically Curtailed SPRT,SCSPRT）以及有预测能力的 SPRT（SPRTwith Predictive Power,PPSPRT）。Huebner 和Fina（2015）则将随机缩减技术与GLR方法相结合，提出基于GLR的随机缩减方法(Stochastically CurtailedGLR,SCGLR)。模拟研究的结果表明：使用随机缩减的方法能够提高测验效率（Finkelman,2008;Huebner& Fina,2015;Wang et al.,2020)。另一方面，贝叶斯规则的基本思路则是通过作答反应获取被试能力的后验分布，并使用后验分布计算损失函数值，从而完成对被试的分类。Lewis 和 Shehan（1990）率先引入先验函数和损失函数，并提出基于贝叶斯决策理论的终止规则。接下来，本文仅在变长的二分类测验情境下关注基于似然比规则的终止规则。

值得注意的是，上述终止规则都建立在单维IRT（Unidimensional IRT,UIRT）的基础上,即假设测验仅考察被试单一维度的能力。但是在心理或教育测验的实践中，测验往往同时考察被试在多个维度上的潜在特质，这就与上述的单维性假设相悖（康春花，辛涛,2010）。为解决这一问题，基于多维IRT（Multidimensional IRT,MIRT）构建多维CCT（MultidimensionalCCT,MCCT）就显得十分必要。迄今，关于MCCT的研究较少，只有少数研究者将特定的似然比规则从单维情境推广至多维情境（Nydick,2013)。在 MCCT中，似然比规则的基本思路与单维情境的一致，但是能力参数的多维性导致各类别间的能力分界点转变为能力分界曲线（二维情境下）或能力分界曲面（三维及以上情境下)。为此，Nydick（2013）提出用似然函数约束的方法构建约束的 SPRT（Constrained SPRT,C-SPRT）、使用空间投影的方法构建投影的 SPRT（Projected SPRT,P-SPRT）以及在此基础上开发随机缩减的多维 SPRT（Multidimensional SCSPRT,M-SCSPRT）。此外，Nydick（2013）还首先将多维GLR 检验（Multidimensional GLR,M-GLR）引入MCCT。

综上，基于MIRT 构建MCCT 终止规则能够更好地适应现实测验的需要。本文在总结与分析已有MCCT终止规则的基础上，提出两种新的MCCT终止规则：第一种是基于马氏距离的多维序贯似然比终止规则（Mahalanobis-SPRT)，具体思路是将马氏距离融入P-SPRT方法；第二种是多维随机缩减的GLR 规则（Multidimensional SCGLR,M-SCGLR)，可以被视为 SCGLR在多维情境下的推广。两种新终止规则相对于已有规则的表现，将通过模拟研究在多种实验条件下进行全面评价。

本文的剩余部分将按如下方式进行组织：第2节首先简要描述本文使用的MIRT模型以及四种已有的MCCT终止规则（即C-SPRT、P-SPRT、M-GLR以及M-SCSPRT)，然后详细介绍两种新提出的MCCT终止规则（即Mahalanobis-SPRT和M-SCGLR)。第3节将介绍模拟研究设计，并在第4节展示研究结果与结论。最后一节进行讨论并展望未来的研究方向。

# 2方法

# 2.1MIRT模型

本文假设所有题目都由多维三参数逻辑斯蒂克模型（MultidimensionalThree-ParameterLogisticModel,M3PL）建模。在该模型中，能力向量为 $\pmb { \theta } _ { i }$ 的被试i正确作答二级计分题目j的概率为（Reckase&Mckinley,1982）,

$$
\begin{array} { r } { P _ { j } ( \pmb { \theta } _ { i } ) \equiv \mathrm { P r o b } \big ( Y _ { i j } = 1 \big | \pmb { \theta } _ { i } , \mathbf { a } _ { j } , d _ { j } , c _ { j } \big ) = c _ { j } + \frac { 1 - c _ { j } } { 1 + \exp \left[ - \left( \mathbf { a } _ { j } ^ { T } \pmb { \theta } _ { i } + d _ { j } \right) \right] } , } \end{array}
$$

其中， $Y _ { i j }$ 是取值为0或1的伯努利随机变量，表示被试i在题目 $j$ 上的二级计分作答反应。 $\pmb { \theta } _ { i } = \left( \theta _ { i 1 } , \theta _ { i 2 } , \ldots , \theta _ { i p } \right) ^ { T }$ 表示被试i的 $p$ 维能力向量， $T$ 表示转置。 $\mathbf { a } _ { j } = \left( a _ { j 1 } , a _ { j 2 } , \ldots , a _ { j p } \right) ^ { T }$ 为题目 $j$ 的 $p$ 维区分度参数向量，有 $\begin{array} { r } { \mathbf { a } _ { j } ^ { T } \pmb { \theta } _ { i } = \sum _ { k = 1 } ^ { p } a _ { j k } \theta _ { i k } } \end{array}$ ；标量 $d _ { j }$ 是与题目难度相关的截距参数，标量 $c _ { j }$ 则是题目的伪猜测参数。为方便对模型参数的含义进行解释，Ackerman（1994）定义（204号 $M D I S C _ { j } = \left( a _ { j 1 } ^ { 2 } + a _ { j 2 } ^ { 2 } + \cdots + a _ { j p } ^ { 2 } \right) ^ { 1 / 2 }$ 作为题目j的多维区分度（multidimensional discrimination），定义 $\begin{array} { r } { M D I F F _ { j } = \frac { - d _ { j } } { M D I S C _ { j } } , } \end{array}$ -dj作为题目j的多维难度（multidimensional difficulty）。

由此，被试i对j'道题目的作答反应 $\mathbf { Y } _ { i j ^ { \prime } } = ( Y _ { i 1 } , Y _ { i 2 } , \ldots , Y _ { i j ^ { \prime } } )$ 的似然函数为，

$$
\begin{array} { r } { L \big ( \pmb { \theta } _ { i } | \mathbf { Y } _ { i j ^ { \prime } } \big ) = \prod _ { j = 1 } ^ { j ^ { \prime } } \big [ P _ { j } ( \pmb { \theta } _ { i } ) \big ] ^ { Y _ { i j } } \big [ Q _ { j } ( \pmb { \theta } _ { i } ) \big ] ^ { 1 - Y _ { i j } } , } \end{array}
$$

其中， $Q _ { j } ( \pmb { \theta } _ { i } ) = 1 - P _ { j } ( \pmb { \theta } _ { i } )$ ，表示被试i错误作答题目 $j$ 的概率。

# 2.2已有的MCCT终止规则

# 2.2.1 似然比思想与C-SPRT、P-SPRT以及M-GLR规则

目前大多数关于MCCT 的终止规则都是基于单维CCT的终止规则而构建。一个单维序贯似然比规则的构成可以总结为四个步骤：（1）构造假设检验；（2）确定不同等级间的能力阈值 $\theta _ { 0 }$ ；(3）在 $\theta _ { 0 }$ 处给定一个 $\delta$ 邻域，即 $( \theta _ { 0 } - \delta , \theta _ { 0 } + \delta ) \equiv ( \theta _ { l } , \theta _ { u } )$ 。当能力值落在该区间时，认为未获得足够信息对被试进行分类，因此该区间也被称为无差别区间；而当能力值大于 $\theta _ { u }$ 时认为被试属于“达标”的类别，当能力值小于 $\theta _ { l }$ 时认为被试属于“未达标”的类别；（4)构建似然比统计量并确定拒绝域。在将终止规则从CCT推广到MCCT时，需要定义能力分界曲线或曲面才能将不同类别的被试区分开来。由此，单维情境下的能力分界点 $\theta _ { 0 }$ 就变为多维空间中的能力分界曲线或曲面 $g ( \pmb \theta ) = 0$ ，其中 $g ( \pmb \theta )$ 为分界函数，具体可分为补偿性的分界函数（比如， $g ( \pmb \theta ) = \theta _ { 1 } + \theta _ { 2 }$ ）和非补偿的分界函数（比如， $g ( \pmb \theta ) = \left\{ { \theta } _ { 1 } , \mp \frac { * } { \sqrt { \pmb \theta } } \theta _ { 2 } \geq 0 \atop { \theta } _ { 2 } , \mp \pmb \theta _ { 1 } > 0  \right.$ 。此时的一个研究问题是如何将分界曲线或曲面转化为单维情况下的分界阈值 $\theta _ { 0 }$ 。另外，即使获得 $\theta _ { 0 }$ 多维空间中的 $\theta _ { 0 }$ 在不同方向上可以构造任意多个 $\delta$ 邻域，因此如何选择 $\theta _ { l }$ 和 $\theta _ { u }$ 是另一个需要解决的问题。C-SPRT、P-SPRT以及M-GLR分别从三个不同的角度提供解决方案。

首先，似然比规则需要构造假设检验，

$$
\begin{array} { c } { { H _ { 0 } { : } \pmb \theta \in \pmb \Theta _ { n } } } \\ { { H _ { 1 } { : } \pmb \theta \in \pmb \Theta _ { m } } } \end{array} ,
$$

其中， $\Theta _ { m }$ 表示属于“达标”类别的被试的能力空间， $\displaystyle \Theta _ { n }$ 表示属于“未达标”类别的被试的能力空间。于是，接受原假设 ${ \bf \ddot { \it H } } _ { 0 }$ 表示被试属于“未达标”类别，接受备择假设 ${ \bf \mathcal { H } } _ { 1 }$ 则表示被试属于“达标”类别。

# （1）C-SPRT

基于构造的上述假设，C-SPRT 的基本思路是使用约束在分界曲线或曲面上的能力估计值替代能力分界点 $\theta _ { 0 }$ ，并计算相应的 $\pmb { \theta } _ { l }$ 和 $\pmb { \theta } _ { u }$ （分别对应 $\Theta _ { n }$ 的上界与 $\Theta _ { m }$ 的下界上的点)。具体地说，在被试i作答完j'道题目后，C-SPRT方法首先将在分界曲线或曲面上计算得到的能力参数估计值 $\widehat { \pmb { \theta } } _ { 0 }$ 作为能力分界点 $\theta _ { 0 }$ 的估计，即

$$
\widehat { \pmb { \theta } } _ { 0 } = \underset { \pmb { \theta } \in \Theta _ { 0 } } { \arg \operatorname* { m a x } } \big [ \log L \big ( \pmb { \theta } \big | \mathbf { Y } _ { i j ^ { \prime } } \big ) \big ] ,
$$

其中， $\Theta _ { 0 } = \{ \pmb { \theta } : g ( \pmb { \theta } ) = 0 \}$ 表示能力分界曲线或曲面。上式表示将 $\mathbf { \boldsymbol { \Theta } } _ { 0 }$ 上使得 $\log L \left( \pmb { \theta } | \mathbf { Y } _ { i j ^ { \prime } } \right)$ 取最大值的点记为 $\widehat { \pmb { \theta } } _ { 0 }$ 。C-SPRT方法然后在 $\widehat { \pmb { \theta } } _ { 0 }$ 处 $g ( \pmb \theta ) = 0$ 的法向量方向上构造 $\delta$ 邻域。记 $\pmb { \theta } _ { \delta }$ 为该方向的单位向量，即s=g( ，其中V为哈密顿算子，表示微分运算， $\left\| \cdot \right\| _ { 2 }$ 表示欧几里得范数，用于衡量欧氏空间内的距离。于是可得到无差别区间的上下限分别为

$$
\begin{array} { c } { { \widehat { \pmb { \theta } } _ { u } = \widehat { \pmb { \theta } } _ { 0 } + \delta \pmb { \theta } _ { \delta } , } } \\ { { \widehat { \pmb { \theta } } _ { l } = \widehat { \pmb { \theta } } _ { 0 } - \delta \pmb { \theta } _ { \delta } . } } \end{array}
$$

根据Wald（1947）提出的似然比检验构造似然比统计量，得到

$$
C _ { i j ^ { \prime } } = \log \bigl [ \mathrm { L R } \bigl ( \widehat { \pmb { \theta } } _ { u } , \widehat { \pmb { \theta } } _ { l } \big | \mathbf { Y } _ { i j ^ { \prime } } \bigr ) \bigr ] = \log \biggl [ \frac { L \bigl ( \widehat { \pmb { \theta } } _ { u } \big | \mathbf { Y } _ { i j ^ { \prime } } \bigr ) } { L \bigl ( \widehat { \pmb { \theta } } _ { l } \big | \mathbf { Y } _ { i j ^ { \prime } } \bigr ) } \biggr ] .
$$

记第一类和第二类错误率分别为 $\alpha$ 和 $\beta$ ，令 $A = A ( \alpha , \beta ) , B = B ( \alpha , \beta ) , C _ { l } = \log ( A ) , C _ { u } =$ $\log ( B )$ 紅且間 $\begin{array} { r } { C _ { 0 } = \frac { C _ { l } + C _ { u } } { 2 } , } \end{array}$ 在分类测验的背景下，通常取 $\begin{array} { r } { A ( \alpha , \beta ) = \frac { \beta } { 1 - \alpha } . } \end{array}$ 愛和機 $\begin{array} { r } { B ( \alpha , \beta ) = \frac { 1 - \beta } { \alpha } } \end{array}$ (Finkeman,2003)。在被试i作答完 $j ^ { \prime }$ 道题目后，计算 $C _ { i { j ^ { \prime } } }$ ，并基于似然比检验规则给出如下判断：若

$$
C _ { i j ^ { \prime } } \leq C _ { l } ,
$$

则停止测验，测验长度为 $j ^ { \prime }$ ，并判断被试属于“未达标”；若

$$
C _ { i j ^ { \prime } } \geq C _ { u } ,
$$

则停止测验，测验长度为j'，并判断被试属于“达标"；否则，即

$$
C _ { l } < C _ { i j ^ { \prime } } < C _ { u } ,
$$

则继续给被试作答下一道题。

Wald-Wolfowitz定理表明：在测验可以持续进行直至满足上述终止规则的情况下，SPRT是具有同等检验力的检验中所需观测个数最少的假设检验，即最优序贯检验（Wald&Wolfowitz,1948)。但是在现实情境下，由于疲劳效应、练习效应等因素的影响，不可能要求被试一直作答直至满足不等式（8）或（9)。因此在单维CCT中，一般通过事先设定最大测验长度J以满足上述现实需要。于是，研究者在设计不定长的 MCCT终止规则时也沿用这一附加的强制结束条件。这就是说，若达到最大长度/时测验仍未结束，则根据下述准则对被试进行强制分类：若 $C _ { i J } \leq C _ { 0 }$ ，则停止测验，测验长度为J，并判断被试属于“未达标”；若$C _ { i J } > C _ { 0 }$ ，则停止测验，测验长度为J，并判断被试属于“达标”（记该准则为最大测验长度下似然比检验的判断准则)。

记被试最终完成测验的实际作答题目数为 $K$ ，分类判断结果为 $D$ （ $D = m$ 表示被试属于“达标”， $D = n$ 表示被试属于“未达标")，最大测验长度为J，则整个C-SPRT 的判断规则

可以概括如下，

停止测验, $K = j ^ { \prime } , D = n$ 若 $\left\{ j ^ { \prime } < J , C _ { i j ^ { \prime } } \leq C _ { l } \right\}$ 或 $\{ j ^ { \prime } = J , C _ { i j ^ { \prime } } \leq C _ { 0 } \}$ （202 停止测验, $K = j ^ { \prime } , D = m$ 若 $\left\{ j ^ { \prime } < J , C _ { i j ^ { \prime } } \geq C _ { u } \right\}$ 或 $\begin{array} { r } { \{ j ^ { \prime } = J , C _ { i j ^ { \prime } } > C _ { 0 } \} . } \end{array}$ （204号 继续测验 否则

（2）P-SPRT

P-SPRT与C-SPRT唯一的区别在于它采用不同方法将分界曲线或曲面转换为可用于假设检验的分界点。具体地说，P-SPRT将基于当前作答得到的被试能力估计值投影至 $g ( \pmb \theta ) =$ 0所刻画的边界上，并将投影视作分界点。在被试作答完j'道题目后，对其能力估计值进行投影的表述如下：

$$
\widehat { \pmb \theta } _ { 0 } = \underset { \pmb \theta \in \Theta _ { 0 } } { \mathrm { a r g m i n } } \big \| \widehat { \pmb \theta } _ { i } - \pmb \theta \big \| _ { 2 } ,
$$

其中， $\widehat { \pmb { \theta } } _ { i }$ 表示被试i的能力估计值。由于 $\left\| \cdot \right\| _ { 2 }$ 代表欧氏空间内的距离，因此公式（12）表示将 $\mathbf { \boldsymbol { \Theta } } _ { 0 }$ 上与 $\widehat { \pmb { \theta } } _ { i }$ 距离最近的点记为 $\widehat { \pmb { \theta } } _ { 0 }$ ，也就是将 $\widehat { \pmb { \theta } } _ { i }$ 投影至 $\mathbf { \Theta } _ { \mathbf { 0 } }$ 上，并将投影得到的点记为 $\widehat { \pmb { \theta } } _ { 0 }$ 确定 $\widehat { \pmb { \theta } } _ { 0 }$ 后，P-SPRT也依照等式（5）、（6）和（7）得到 $\widehat { \pmb { \theta } } _ { u }$ 、 $\widehat { \pmb { \theta } } _ { l }$ 以及 $C _ { i { j ^ { \prime } } }$ 。

（3）M-GLR

M-GLR方法在构造似然比统计量的思路上与P-SPRT 和C-SPRT都不同。GLR统计量$C _ { i { j ^ { \prime } } }$ 是似然函数在不同类别被试（即“达标”与“未达标"）的能力空间中的最大值之比的对数，它不同于等式（7）需要确定 $\widehat { \pmb { \theta } } _ { u }$ 和 $\widehat { \pmb \theta } _ { l }$ ，因此从理论上可避免“多维情境下要将分界曲线或曲面转换为分界点”的需求。M-GLR统计量定义为

$$
\begin{array} { r } { C _ { i j ^ { \prime } } = \log \frac { \underset { { \theta _ { 1 } \in \Theta _ { m } } } { \operatorname* { s u p } } \left[ L \left( \pmb { \theta } _ { 1 } \big | \mathbf { Y } _ { i j ^ { \prime } } \right) \right] } { \underset { { \theta _ { 2 } \in \Theta _ { n } } } { \operatorname* { s u p } } \left[ L \left( \pmb { \theta } _ { 2 } \big | \mathbf { Y } _ { i j ^ { \prime } } \right) \right] } . } \end{array}
$$

其中， ${ \pmb \theta } _ { 1 } \in { \pmb \Theta } _ { m }$ 表示 $\pmb { \theta } _ { 1 }$ 是“达标”被试的能力空间 ${ \pmb { \Theta } } _ { m }$ 中的任一值， ${ \pmb \theta } _ { 2 } \in { \pmb \Theta } _ { n }$ 表示 $\pmb { \theta } _ { 2 }$ 为“未达标”被试的能力空间 $\Theta _ { n }$ 中的任一值。公式（13）的分子部分即为在“达标”被试的能力空间内似然函数的最大值，而分母部分即为在“未达标"被试的能力空间内似然函数的最大值。由此可以发现，与单维的GLR方法相比，M-GLR只是将 $C _ { i { j ^ { \prime } } }$ 中求极值的集合由单维的能力区间变为多维能力空间中的区域，其性质并没有变化。需要说明的是，尽管C-SPRT、P-SPRT与 M-GLR在构造统计量的具体方式上存在差异，但都是基于公式（3）所对应的假设检验，而且仅依赖构造的似然比统计量进行判断。因此，在得到 $C _ { i { j ^ { \prime } } }$ （序贯似然比统计量或广义似然比统计量）后，P-SPRT和M-GLR的判断准则也都通过与 $C _ { l }$ 、 $C _ { u }$ 或 $C _ { 0 }$ 进行比较得到测验结果，即按照公式（11）所定义的规则对被试做出分类判断。

# 2.2.2 随机缩减与M-SCSPRT规则

如前所述，由于最大测验长度j的引入与Wald-Wolfowitz 定理的前提假定相悖，因此在同等条件下，SPRT不再具有最大检验力。这种低效不仅增大测验长度，而且导致测验时间和题目曝光率的上升。因此，在维持 SPRT 分类准确率的基础上缩短测验长度有助于 MCCT的应用。随机缩减（Finkelman,2008;Huebner&Fina,2015）正是解决该问题的一种方法：即如果被试接下来的作答反应在较大概率上不会改变当前对被试的分类判断，那么此时便结束测验是合理的。

M-SCSPRT 规则是一种将随机缩减与C-SPRT 相结合的多维似然比终止规则，它在完整保留公式（11）所定义判断准则的基础上，对原本需要继续作答的被试i再次进行判断。具体地说，M-SCSPRT按照等式（4）至等式（7）计算约束下的似然比统计量 $C _ { i { j ^ { \prime } } }$ ，并计算被试作答至最大测验长度J时，对被试的分类判断与当前一致的概率

$$
P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big ) ,
$$

其中 $D _ { j ^ { \prime } }$ 表示被试作答完 $j ^ { \prime }$ 道题目时，对被试的预分类； $D _ { J }$ 表示被试作答完/道题目时，对被试的最终分类。预分类的判断准则与最大测验长度下似然比检验的判断准则一致，即

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { D _ { j ^ { \prime } } = n , } & { C _ { i j ^ { \prime } } \leq C _ { 0 } } \\ { D _ { j ^ { \prime } } = m , } & { C _ { i j ^ { \prime } } > C _ { 0 } ^ { \phantom { ' } } } \end{array} \right. } \end{array}
$$

由公式（11)，在 2.2.1节所述的三种似然比检验中，若 $j ^ { \prime } < J$ 且 $C _ { l } < C _ { i j ^ { \prime } } < C _ { u }$ ，测验将继续进行。但是，M-SCSPRT方法在 $j ^ { \prime } < J$ 时，对公式（11）进行了如下调整，而在 $j ^ { \prime } = J$ 时不变，

停止测验, $K = j ^ { \prime } , D = n$ 若 $\left\{ C _ { i j ^ { \prime } } \leq C _ { l } \right\}$ 或 $\{ C _ { l } < C _ { i j ^ { \prime } } \le C _ { 0 } , P ( D _ { J } = n | C _ { i j ^ { \prime } } ) \ge 1 - \epsilon _ { 1 } \}$ 停止测验, $K = j ^ { \prime } , D = m$ 若 $\left\{ C _ { i j ^ { \prime } } \geq C _ { u } \right\}$ 或 $\{ C _ { u } > C _ { i j ^ { \prime } } > C _ { 0 } , P ( D _ { J } = m | C _ { i j ^ { \prime } } ) \geq 1 - \epsilon _ { 2 } \} _ { }$ 继续测验 否则

其中， $\epsilon _ { 1 }$ 与 $\epsilon _ { 2 }$ 为事先设定的临界值。以往的模拟研究表明：当 $\epsilon _ { 1 }$ 与 $\epsilon _ { 2 }$ 都取0.05时，能在损失较小测验分类精度的前提下大幅缩短测验长度（Finkelman,2008,2010)。

# 2.3两种新的MCCT终止规则

# 2.3.1 Mahalanobis-SPRT

如公式（12）所述，P-SPRT 规则使用欧氏距离对被试能力估计值进行空间投影。但是，在CCT施测的初期阶段，对被试能力的估计往往不够准确，P-SPRT仅使用一次估计的能力结果 $\widehat { \pmb { \theta } } _ { i }$ 进行投影可能会使 $\widehat { \pmb { \theta } } _ { 0 }$ 不够稳定，从而影响分类结果（在高维情境下这种影响可能会尤为突出)。因此在多维情境中，“按欧氏距离对被试能力值进行投影”这种做法有待商榷。

本文基于聚类分析的思想，提出基于马氏距离的Mahalanobis-SPRT规则，以克服P-SPRT的上述不足。在测验初期，尽管单个被试能力估计值并不准确，但是如果将多个能力估计值综合起来，就可以大致描绘出被试真实能力值所处的范围。具体地说，测验初期的能力估计值是在真值附近上下波动的，而并非一致地高于或低于真值，所以多个能力估计值的均值，往往就更加接近真值。图1表示某名被试在一个二维测验过程中，其能力估计值随作答题目数量变化而变化的情况。其中，蓝色的三角形点代表该被试的能力真值，红色的圆形点代表对被试能力的估计值，红色越深表示得到该能力估计值时被试作答的题目数量越多。由图1可以看到：在被试作答的题目数量较少时，被试的能力估计值与真值相差较大。但与此同时，在两个维度上，能力估计值都是围绕真值上下波动的。因此，在测验初期，多个能力估计值的均值就能够对被试能力真值进行比较准确的描述。

![](images/20c503f0fd3fc7bfd544c97b304c154ae363efa2eef9a48fbda0d7549da6a484.jpg)  
图1二维情境下某名被试的能力估计值随作答题数的变化图

综上，使用分界曲线或曲面上的点中，到“已得到的多个能力估计值的均值”的马氏距离最近的点作为 $\widehat { \pmb { \theta } } _ { 0 }$ （这也正是Mahalanobis-SPRT方法的做法）比P-SPRT中直接使用分界曲线或曲面上到 $\widehat { \pmb { \theta } } _ { i }$ 的欧氏距离最近的点要更合理。于是，我们可以定义Mahalanobis-SPRT 规则下的分界点 $\widehat { \pmb { \theta } } _ { 0 }$ ，即

$$
\widehat { \pmb \theta } _ { 0 } = \underset { \pmb { \theta } \in \Theta _ { 0 } } { \mathrm { a r g m i n } } \Big \Vert \overline { { \pmb \theta } } _ { i j ^ { \prime } } - \pmb \theta \Big \Vert _ { M } .
$$

其中， $\left\| \cdot \right\| _ { M }$ 代表马氏距离; $\overline { { \pmb { \theta } } } _ { i j ^ { \prime } }$ 是被试i作答完j"道题目后得到的 $j ^ { \prime }$ 个能力估计值的均值，代表对被试能力真值的近似刻画。如果将被试i作答完第 $j$ 道题目后得到的 $p$ 维能力估计值记为 $\widehat { \pmb { \theta } } _ { i j } = \left( \widehat { \theta } _ { i j 1 } , \widehat { \theta } _ { i j 2 } , \dots , \widehat { \theta } _ { i j p } \right)$ ，那么 $\begin{array} { r } { \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } = \left( \sum _ { j = 1 } ^ { j ^ { \prime } } \hat { \theta } _ { i j 1 } / j ^ { \prime } , \sum _ { j = 1 } ^ { j ^ { \prime } } \hat { \theta } _ { i j 2 } / j ^ { \prime } , \dots , \sum _ { j = 1 } ^ { j ^ { \prime } } \hat { \theta } _ { i j p } / j ^ { \prime } \right) \mathrm { , } } \end{array}$ 。另外，如果将这 $j ^ { \prime }$ 个能力估计值的协方差矩阵记为 $\hat { \mathbf { Z } } _ { i j ^ { \prime } }$ ，那么根据马氏距离的定义且当 $\pmb { \Sigma } _ { i j ^ { \prime } }$ 可逆（即$\left. \pmb { \Sigma } _ { i j ^ { \prime } } \right. \neq 0$ ）时，有

$$
\widehat { \pmb { \theta } } _ { 0 } = \underset { \pmb { \theta } \in \Theta _ { 0 } } { \operatorname { a r g m i n } } \big \| \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } - \pmb { \theta } \big \| _ { M } = \underset { \pmb { \theta } \in \Theta _ { 0 } } { \operatorname { a r g m i n } } \sqrt { ( \pmb { \theta } - \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } ) \Sigma _ { i j ^ { \prime } } ^ { - 1 } \big ( \pmb { \theta } - \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } \big ) ^ { \mathrm { T } } } .
$$

定义 $\pmb { \theta } _ { \delta }$ 为 $\overline { { \pmb { \theta } } } _ { i j ^ { \prime } }$ 与 $\widehat { \pmb { \theta } } _ { \mathbf { 0 } }$ 的差向量方向上的单位向量，即

$$
\begin{array} { r } { \pmb { \theta } _ { \delta } = \frac { \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } - \widehat { \pmb { \theta } } _ { 0 } } { \lVert \overline { { \pmb { \theta } } } _ { i j ^ { \prime } } - \widehat { \pmb { \theta } } _ { 0 } \rVert _ { 2 } } . } \end{array}
$$

确定 $\widehat { \pmb { \theta } } _ { 0 }$ 与 $\pmb { \theta } _ { \delta }$ 后，Mahalanobis-SPRT按照等式（5）、（6）和（7）得到 $\widehat { \pmb { \theta } } _ { u }$ 、 $\widehat { \pmb { \theta } } _ { l }$ 以及 $C _ { i { j ^ { \prime } } }$ 然后按照公式（11）所述的判断准则对被试进行分类。

需要指出的是，公式(17)中有两处与P-SPRT所定义的公式(12)不同：第一,Mahalanobis-SPRT 使用“已得到的多个能力估计值的均值 $( \overline { { \pmb { \theta } } } _ { i j ^ { \prime } }$ )”代替 P-SPRT 中的单个能力估计值；第二，Mahalanobis-SPRT 使用马氏距离作为距离的度量方式，而非P-SPRT 中的欧式距离。总之，Mahalanobis-SPRT新规则使用被试能力的一系列序贯估计值，并将分界曲线或曲面上距其均值最近的点作为 $\widehat { \pmb { \theta } } _ { 0 }$ ；相较于P-SPRT使用单一能力估计值进行投影，新规则理应能够获得更加稳健的结果。

# 2.3.2 M-SCGLR规则

Huebner 和Fina（2015）提出的 SCGLR规则将随机缩减的方法与GLR相结合，在保持测验分类精度的前提下能够缩短测验长度。因此，本文将 SCGLR方法推广至MCCT情境，并得到多维的 SCGLR规则（记为M-SCGLR)。M-SCGLR直接沿用M-GLR的方式构造GLR统计量，如等式（13）所示。

但是，在对被试进行分类判断时，M-SCGLR采用的是随机缩减方法，即对公式（11）在 $j ^ { \prime } < J$ 的情况下进行如下调整：

停止测验, $K = j ^ { \prime } , D = n$ 若 $\left\{ C _ { i j ^ { \prime } } \leq C _ { l } \right\}$ 或 $\{ C _ { l } < C _ { i j ^ { \prime } } \le C _ { 0 } , P ( D _ { J } = n | C _ { i j ^ { \prime } } ) \ge 1 - \epsilon _ { 1 } \}$ 停止测验, $K = j ^ { \prime } , D = m$ 若 $\left\{ C _ { i j ^ { \prime } } \geq C _ { u } \right\}$ 或 $\{ C _ { u } > C _ { i j ^ { \prime } } > C _ { 0 } , P ( D _ { J } = m | C _ { i j ^ { \prime } } ) \geq 1 - \epsilon _ { 2 } \} ,$ 继续测验 否则

在公式（20）中，

$$
\begin{array} { r } { P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big ) = 1 - P \big ( D _ { J } = m \big | C _ { i j ^ { \prime } } \big ) \approx \Phi \left( \frac { C _ { 0 } - \mathbb { E } _ { \theta } \left( C _ { i J } \big | C _ { i j ^ { \prime } } \right) } { \sqrt { \operatorname { v a r } _ { \theta } \left( C _ { i J } \big | C _ { i j ^ { \prime } } \right) } } \right) , } \end{array}
$$

其中,

$$
\begin{array} { r } { \mathbb { E } _ { \pmb { \theta } } \big ( C _ { i j } \big | C _ { i j ^ { \prime } } \big ) = C _ { i j ^ { \prime } } + \sum _ { j = j ^ { \prime } + 1 } ^ { J } \mathbb { E } _ { \pmb { \theta } } \Bigg ( \log \frac { \operatorname* { s u p } _ { 1 \pm \Theta _ { m } } ^ { \mathrm { s u p } } \big [ L \big ( \pmb { \theta } _ { 1 } \big | Y _ { i j } \big ) \big ] } { \operatorname* { s u p } _ { \pmb { \theta } _ { 2 } \in \Theta _ { n } } ^ { \mathrm { s u p } } \big [ L \big ( \pmb { \theta } _ { 2 } \big | Y _ { i j } \big ) \big ] } \Bigg ) , } \end{array}
$$

$$
\begin{array} { r } { \operatorname { V a r } _ { \pmb { \theta } } \big ( C _ { i j } \big | C _ { i j ^ { \prime } } \big ) = \sum _ { j = j ^ { \prime } + 1 } ^ { J } \operatorname { V a r } _ { \pmb { \theta } } \Bigg ( \log \frac { \operatorname* { s u p } _ { \pmb { \theta } _ { 1 } \in \pmb { \theta } _ { m } } \big [ L \big ( \pmb { \theta } _ { 1 } \big | Y _ { i j } \big ) \big ] } { \operatorname* { s u p } _ { \pmb { \theta } _ { 2 } \in \pmb { \theta } _ { n } } \big [ L \big ( \pmb { \theta } _ { 2 } \big | Y _ { i j } \big ) \big ] } \Bigg ) , } \end{array}
$$

其中， $\Phi ( \cdot )$ 为标准正态分布的分布函数。公式（21）、（22）和（23）的具体推导过程，感兴趣的读者可参见附录1。

需要注意的是，当能够事先知道第 $j ^ { \prime } + 1$ 道题到第j道题目的选取时，上述计算并不困难。但在自适应序贯选题的情境下，无法提前获知接下来的题目。此时，为计算等式(22)与(23)，可以使用一组合适的题目替代被试接下来要实际作答的题目。比如，当使用D最优选题策略时（即最大化Fisher 信息矩阵的行列式)，可以基于当前的能力估计值计算所有剩余题目的Fisher 信息矩阵的行列式，然后选择值最大的 $J - j ^ { \prime }$ 道题目作为替代的题目。单维情形下的研究表明：当使用替代题目时，需适当减小错误率 $\cdot \epsilon _ { 1 }$ 和 $\dot { \epsilon } _ { 2 }$ 的值（Finkelman,2008）。

# 3 实验

本研究采用R3.4.2自编计算机程序开展模拟研究，共有两个研究目的：（1）将新提出的2种 MCCT终止规则（即 Mahalanobis-SPRT 和M-SCGLR）与已有的4 种终止规则（即C-SPRT、P-SPRT、M-GLR以及M-SCSPRT）进行比较，并评价它们在测验精度和测验效率两方面的表现以揭示各种方法的优缺点以及适用情境；（2）对比上述6种终止规则对于具有特定能力水平的被试的分类表现，以探究各种规则对特定被试的分类敏感度是否存在明显差异。

考虑到不同题库结构、能力维度间相关及能力分界曲线会对MCCT的结果产生影响，本研究设置2种题库结构、3种能力维度间的相关水平和2种分界曲线，对6种MCCT终止规则展开模拟研究，也即采用 $2 \times 3 \times 2 \times 6$ 的实验设计（共产生72 种实验条件，12 种MCCT 测验情境)实现研究目的一。另外，本研究还分别选取靠近或远离能力分类曲线的36种特定能力取值的被试及2种分界曲线以实现研究目的二。

# 3.1题库与被试生成

MIRT的研究中通常考虑两种题库结构，即题目内多维（within-itemmultidimensionality）和题目间多维（between-item multidimensionality)。其中，题目内多维是指题库中的每道题目均测量一个或多个维度，而题目间多维则是指题库中的每道题目有且仅测量一个维度（Hartig&Hohler,2008;Wang＆ Chen,2004)。由于题库结构会对被试能力向量的估计精度产生影响（Chen&Wang,2016)，因此本文按照公式（1）所定义的MIRT模型生成两个MCCT题库：题库1采用题目内多维的结构，题库2采用题目间多维的结构，每个题库均包含900道题目。题库1中每道题目都测量两个维度（即 $p = 2$ )，由此可记题库中的题目参数向量为${ \pmb { \gamma } } = ( a _ { 1 } , a _ { 2 } , d , c ) ^ { T }$ 。题库2中的一半题目仅测量第一个维度，另一半则仅测量第二个维度。为使模拟情境尽可能地接近现实情况，本研究按照Nydick（2013）的做法模拟各个参数：

(1） $a _ { 1 }$ 和 $a _ { 2 }$ 参数。从均值为 $\mu _ { l o g } = 0 . 5$ 、标准差为 $\sigma _ { l o g } = 0 . 1$ 的对数正态分布中随机抽取区分度参数MDISC（即 $\sqrt { a _ { 1 } ^ { 2 } + a _ { 2 } ^ { 2 } } )$ 。于是在题库1中，可以从均匀分布 $U ( 0 , M D I S C ^ { 2 } )$ 中抽取$a _ { 1 } ^ { 2 }$ ，则 $a _ { 2 } ^ { 2 } = M D I S C ^ { 2 } - a _ { 1 } ^ { 2 }$ ；而在题库2中，设置对应维度的 $a$ 参数等于MDISC即可。

（2） $d$ 和 $c$ 参数。从 $U ( - 3 . 5 , 3 . 5 )$ 中随机抽取与难度相关的参数 $b$ 。由此，在题库1中，与之相关的参数 $d = - b \cdot \mathbf { a 1 }$ ，其中1是元素全为1的2维列向量；在题库2中， $d$ 为 $b$ 和对应维度的 $a$ 参数的乘积的负值。此外，固定参数 $\mathit { \Pi } _ { \cdot \ c }$ 为0.2。

另一方面，本文模拟3000 名被试参与测验，被试的能力向量 $\pmb { \theta } = ( \theta _ { 1 } , \theta _ { 2 } ) ^ { T }$ 随机抽取自均值向量为μ=(0,0)、协方差矩阵为Σ=(。 的二维正态分布 $\mathbf { M V N } ( \mu , \pmb { \Sigma } )$ ，其中 $\rho = 0$ 、0.5和0.8，分别对应能力维度间没有相关、中等相关和高度相关3种水平（Chen et al.,2017)。此外，本文模拟 36 个特定的能力向量值 $( \theta _ { 1 } , \theta _ { 2 } )$ 用于实现研究目的二，其中 $\theta _ { 1 } , \theta _ { 2 } \in$ $\{ - 0 . 5 , - 0 . 3 , - 0 . 1 , 0 . 1 , 0 . 3 , 0 . 5 \}$ （6 个点在两个维度上完全交叉共形成36个点)，每个能力点上生成500名被试参与测验。

对模拟生成的数据进行描述统计，得到的结果如表1所示。

表1研究1中各参数的描述统计表  

<html><body><table><tr><td></td><td colspan="4">题库1 (题目内多维)</td><td colspan="4">题库2（题目间多维）</td><td colspan="2">被试（p=0)</td><td colspan="2">被试（p=0.5)</td><td colspan="2">被试（p=0.8)</td></tr><tr><td>统计量</td><td>a1</td><td>a</td><td>d</td><td>C</td><td>a1</td><td>a</td><td>d</td><td>c</td><td>01</td><td>02</td><td>0</td><td>02</td><td>0</td><td>02</td></tr><tr><td>平均数</td><td>1.103</td><td>1.098</td><td>0.086</td><td>0.200</td><td>0.830</td><td>0.833</td><td>0.131</td><td>0.200</td><td>- 0.010</td><td>0.021</td><td>0.022</td><td>0.006</td><td>0.016</td><td>- 0.025</td></tr><tr><td>标准差</td><td>0.428</td><td>0.414</td><td>4.348</td><td>0.000</td><td>0.839</td><td>0.842</td><td>3.336</td><td>0.000</td><td>0.998</td><td>0.996</td><td>1.011</td><td>0.991</td><td>0.999</td><td>1.000</td></tr><tr><td>最小值</td><td>0.038</td><td>0.040</td><td>- 9.327</td><td>0.200</td><td>0.000</td><td>0.000</td><td>- 6.281</td><td>0.200</td><td>- 3.331</td><td>- 3.125</td><td>- 3.614</td><td>- 3.196</td><td>- 4.016</td><td>- 3.267</td></tr><tr><td>最大值</td><td>2.285</td><td>2.065</td><td>8.873</td><td>0.200</td><td>2.196</td><td>2.329</td><td>7.220</td><td>0.200</td><td>3.252</td><td>3.332</td><td>4.269</td><td>3.071</td><td>3.264</td><td>3.712</td></tr><tr><td>相关系数矩阵 bu</td><td>1</td><td>- 0.782</td><td>- 0.011</td><td>1</td><td>1</td><td>- 0.981</td><td>- 0.001</td><td>1</td><td>1</td><td>- 0.002</td><td>1</td><td>0.486</td><td>1</td><td>0.803</td></tr><tr><td></td><td>0.782</td><td>1</td><td>0.009</td><td>1</td><td>- 0.981</td><td>1</td><td>0.004</td><td>1</td><td>- 0.002</td><td>1</td><td>0.486</td><td>1</td><td>0.803</td><td>1</td></tr><tr><td></td><td>- 0.011</td><td>0.009</td><td>1</td><td>1</td><td>- 0.001</td><td>0.004</td><td>1</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

注：表1中仅呈现为实现研究目的一而生成的各参数的描述统计量，这是因为研究目的二是针对36种特定能力值的被试。

# 3.2MCCT的模拟程序描述

从能力估计方法、选题策略以及终止规则等三个方面对MCCT的模拟过程进行描述：

（1）能力估计方法

本研究采用约束的极大似然估计法（Maximum Likelihood Estimation,MLE）估计被试的能力向量值0，记为 $\widehat { \pmb { \theta } }$ ，参数的估计范围限定在 $[ - 4 , 4 ] \times [ - 4 , 4 ]$ 的正方形区域，公式如下，

$$
\widehat { \pmb { \theta } } = \underset { \pmb { \theta } \in [ - 4 , 4 ] \times [ - 4 , 4 ] } { \arg \operatorname* { m a x } } \{ \log [ { L ( \pmb { \theta } | \mathbf { Y } ) } ] \} .
$$

具体的估计过程由R3.4.2 中的donlp2 函数实现。

# （2）选题策略

根据以往研究（Nydick,2013; Segall,1996)，使用经典的D最优（D-optimality）策略选取题目。D最优策略选择最大化Fisher信息矩阵的行列式的题目，它等价于选择最小化未知参数协方差矩阵的行列式（即 $\pmb \theta$ 的置信椭球体积）的题目。针对（1）式定义的MIRT模型，任一题目j的Fisher信息矩阵为，

$$
\begin{array} { r } { I _ { j } ( \pmb \theta ) = - \mathbb E \left[ \frac { \partial ^ { 2 } \log \left[ L ( \pmb \theta | Y ) \right] } { \partial \pmb \theta \partial \pmb \theta ^ { \operatorname { T } } } \right] = \frac { \left[ 1 - p _ { j } ( \pmb \theta ) \right] \left[ p _ { j } ( \pmb \theta ) - c _ { j } \right] ^ { 2 } } { p _ { j } ( \pmb \theta ) \left[ 1 - c _ { j } \right] ^ { 2 } } \mathbf { a } _ { j } \mathbf { a } _ { j } ^ { \operatorname { T } } . } \end{array}
$$

在模拟的二维情境下，上述Fisher信息矩阵是一个 $2 \times 2$ 的矩阵。在选择第j道题目时，关于 $\pmb \theta$ 的Fisher信息矩阵是“已作答的 $j - 1$ 道题目的信息矩阵”与“候选的第j道题的信息矩阵”之和（也即 $\begin{array} { r l } { \sum _ { k = 1 } ^ { j - 1 } I _ { k } ( \pmb { \theta } ) + I _ { j } ( \pmb { \theta } ) ) } \end{array}$ 。由此，被试能力估计值的置信椭球的体积为，

$$
\begin{array} { r } { \mathrm { V a r ~ } \left( \pmb { \theta } \right) = \left| \sum _ { k = 1 } ^ { j - 1 } { \cal I } _ { k } ( \pmb { \theta } ) + { \cal I } _ { j } ( \pmb { \theta } ) \right| ^ { - 1 } , } \end{array}
$$

使用 $\mathrm { ~ D ~ }$ 最优策略选择的第j道题目就是剩余题库中使得公式（26）达到最小的题目。另外，由于在测验初期难以获得对被试能力的准确估计值（Chang&Ying,1996)，难以达到精准选题的目的。因此，本研究中每次测验的前4道试题从题库中随机抽取产生。

（3）终止规则与分界曲线

本研究采用C-SPRT、P-SPRT、M-GLR、M-SCSPRT、Mahalanobis-SPRT、M-SCGLR 等6 种规则终止测验。按照 Thompson（2010）的设置，这里令 $\alpha = \beta = 0 . 1$ 且 $\epsilon _ { 1 } = \epsilon _ { 2 } = 0 . 0 2 5$ 。为考察不同类型的分界曲线对结果的影响，本研究设置两种分界曲线：补偿性分界曲线和非补偿的分界曲线。其中，补偿性分界曲线是指不同维度间的能力是通过线性组合的方式结合在一起，此时被试在某个维度上能力的不足可以由其在其他维度上的高能力来补偿。否则，当被试不同维度间的能力无法相互补偿时，即为非补偿性分界曲线。参考Nydick（2013）的做法，本研究选取的补偿性分界曲线为 $g ( \pmb \theta ) = \theta _ { 1 } + \theta _ { 2 } = 0$ ，非补偿的分界曲线为 $g ( \pmb \theta ) =$ $\begin{array} { c } { { \left\{ \theta _ { 1 } = 0 , \theta _ { 2 } \geq 0 \right. } } \\ { { \left. \theta _ { 2 } = 0 , \theta _ { 1 } > 0 \right. } } \end{array}$ 0（也即笛卡尔坐标系中构成第一象限的坐标轴)。

# 3.3评价指标

选择平均测验长度（AverageTestLength,ATL）、正确分类率（Percent ofCorrectClassification,PCC）以及损失函数（loss）评价每种终止规则。

ATL 是某种测验情境下所有被试的最终测验长度的平均值，在一定程度上反映测验效率。PCC 是被正确分类的被试占该测验情境下所有被试的比例，反映测验分类精度。Finkelman（2010）定义的loss是对某次测验的测验精度和效率的综合评价指标，

$$
\mathsf { l o s s } = R \times \pmb { 1 } _ { W } + K ,
$$

其中， $\mathbf { 1 } _ { W }$ 表示错误分类的示性函数（当对被试错误分类时取值为1，当没有误判时取值为0)； $R$ 表示错误分类的惩罚程度，一般为非负值，其取值越大就表示对错误分类的惩罚越大，即对精度的要求越高（在计算时需由研究者根据测验对错误分类的厌恶程度给定);$K$ 和前文一样，表示被试最终完成测验时实际作答的题目数。在某次测验中，如果将被试错误分类，loss 的值为惩罚值 $R$ 与该次测验的长度之和；否则，loss 的值就等于该次测验的长度。如果在多次测验中固定 $R$ ，并将式（27）取平均，即可得到平均损失，

$$
\overline { { \mathrm { l o s s } } } = R \times \left( 1 - \mathrm { P C C } \right) + \mathrm { A T L } ,
$$

由此，平均损失是一种结合PCC 和 ATL 的综合评价指标。具体地说， $R$ 确定后，对于某个终止规则而言，其 PCC 越大且ATL 越小，则平均损失就越小，表示该方法表现越好；相反地，PCC越小，ATL越大，平均损失就越大，表示该方法表现越差。根据平均损失的大小，就可以指导实际测验中终止规则的选择。

# 4结果

# 4.1各种规则的分类精度与效率

图2呈现了6种终止规则在各种MCCT测验情境下的ATL及PCC结果。

![](images/4882a1fef5466d285dbe414cc227ba3af6f93cedcfd90d0358ae4f135f11fe1d.jpg)  
图26种终止规则在各种测验情境下的结果对比图

在图2中，根据是否采用随机缩减技术可以将6种规则分为两类。在所有的12种测验情境中，未采用随机缩减技术的C-SPRT、P-SPRT、M-GLR以及新提出的Mahalanobis-SPRT规则的PCC 均较高，而采用随机缩减技术的M-SCSPRT以及新提出的M-SCGLR的PCC 相对较低（但也都在 $80 \%$ 以上)。与此同时，采用随机缩减技术的2种规则的ATL 明显低于未采用随机缩减的4种规则。也就是说，随机缩减的方法尽管可能损失一定的分类精度，但能较大幅度地缩短被试作答的测验长度。

考察本研究提出的两种新方法的表现。对于本文提出的Mahalanobis-SPRT，在补偿性分界曲线的情境下，其总体上具有较高的PCC：在题目间多维时，该方法的PCC 仅仅略低于表现最好的P-SPRT方法，而在题目内多维时，该方法具有6种方法中最高的PCC；而在非补偿性分界曲线的情境下，虽然该方法的PCC 低于其他未使用随机缩减的方法，但是 ATL也有相应的降低，而且可以看到其表现随能力维度间相关的升高有更大改善。对于本文提出的另一种终止规则（即 M-SCGLR)，在几乎所有测验情境下，相比于同样采用随机缩减的

M-SCSPRT，它的PCC 有较大提高，而ATL 增加的却并不多。在使用非补偿性曲线和题目内多维的情境下，M-SCGLR的PCC 甚至能够接近未采用随机缩减技术的规则的水平。

考察能力维度间的相关水平对各终止规则的影响，可以发现：随着能力维度间相关系数$\rho$ 的增加，6 种终止规则的 ATL 有减少的趋势，而 PCC 则有升高的趋势。以 Mahalanobis-SPRT规则为例，随着 $\boldsymbol { \rho }$ 的增加，其在每个 $\cdot \rho$ 值下的四种测验情境里的平均PCC由0.916逐渐增加到0.925 和0.942，而平均ATL 则由 57.037下降到 54.437和 52.384。考察分界曲线对各终止规则的影响，可以发现：相比于非补偿的分界曲线，6种终止规则在几乎所有的补偿性分界曲线情境下的ATL均有所下降，而PCC 则有所升高。考察题库结构对各终止规则的影响时，情况就变得复杂起来。由图2知，它与分界曲线会对各终止规则的表现产生交互作用。也就是说，在补偿性分界曲线的情境下，相比于题目间多维的条件，6种终止规则在题目内多维条件下的ATL均有所下降，而PCC 均有所升高。而在非补偿分界曲线的情境下，6 种规则在题目内多维与题目间多维的差异就没有统一规律。

图3呈现的是6种终止规则在各种 MCCT测验情境下的标准化平均损失。图中的横坐标代表错误分类的惩罚R（详见公式（28))，其从区间[0,3000]按步长为1取值，共得到3001个点；纵坐标是在各个R值下6种规则的平均损失的标准化值1。

![](images/a9966381d13338b8dfd149de109587cbe05f53ffa19f2133d12ffce55b2dad74.jpg)  
图36种终止规则在各种测验情境下的标准化平均损失变化图

根据平均损失的定义，随着R值的增加，平均损失对误判的敏感度不断上升。当R值约小于500 时，ATL较小的规则（即M-GLR、M-SCGLR和M-SCSPRT）平均损失较小；当R值大于约1000时，平均损失对测验分类精度更敏感，分类精度较高的规则（即C-SPRT、P-SPRT和Mahalanobis-SPRT）平均损失更小。

对于新提出的Mahalanobis-SPRT，在补偿性分界曲线的所有情境下，该方法在对精度要求较高（即R取值较大）时，具有更低的平均损失（这与其在补偿性分界曲线的条件下具有更高的PCC 是对应的)；在非补偿分界曲线的所有情境下，无论R的取值如何，其平均损失的值整体上处于6种方法的中间位置。这就是说，在实际测验中，该方法更适用于以下两种情境：一是使用补偿性分界曲线且对精度要求较高的情境。在该情境下，Mahalanobis-SPRT的平均损失较其他规则更低，表现更好；二是使用非补偿性分界曲线且不能确定对精度的具体要求的情境。此时，虽然 Mahalanobis-SPRT 的平均损失并不是最低，但是由于测验对精度的要求并不确定，选择其他规则可能会导致在精度要求较高/较低时产生较大的损失。因此，可以将 Mahalanobis-SPRT作为一种相对“保守”的选择。对于本研究提出的另一种规则（即 M-SCGLR)，在几乎所有测验情境下，该方法在R很小（约小于200）时的平均损失略高于同样使用随机缩减技术的 M-SCSPRT。但是，在R的值稍高(约大于 200)时,M-SCGLR的平均损失较M-SCSPRT有明显的降低（这与“其PCC较M-SCSPRT有较大提高，而ATL的增加则相对较少”相对应)。这表明在多数情境下，M-SCGLR在测验精度上明显优于M-SCSPRT。

# 4.2各种规则对特定被试的敏感度

对应于第二个研究目的，图4和图5呈现了能力为各种特定值的被试在6种终止规则下的 PCC 结果。需要说明的是，图4中的黑色实线表示补偿的能力分界曲线 $g ( \pmb \theta ) = \theta _ { 1 } +$ θ=0，图5中的黑色实线则表示非补偿的能力分界曲线g(0)={=0, >0°

![](images/6f64ae790d50faf94dd82fea69d44a68dabe931f853723d56dba9965b259d1dd.jpg)  
图4能力为各种特定值的被试在补偿性边界下6种终止规则的PCC结果

![](images/b9122641f7a37020a1305dd0d65ac40aab3ff991a35a4de791172ecd013fb12a.jpg)  
图5能力为各种特定值的被试在非补偿性边界下6种终止规则的PCC结果

由图4和图5可知，无论采用哪种分界曲线，6种终止规则在PCC 指标上对各种特定能力被试的敏感度呈现出一致的变化规律。具体而言，对于能力值靠近能力分界曲线的被试，其测验的PCC 都较低；而对于能力值远离能力分界曲线的被试，其测验的PCC 都较高。这说明能力值越靠近能力分界曲线的被试，越难对其进行准确的分类。上述能力为各种特定值的被试在ATL上呈现的规律则与PCC 恰好相反。也即对于6种终止规则，能力值越靠近能力分界曲线的被试，其ATL 越大。限于篇幅，此处不再呈现ATL的结果。

# 5讨论及未来的研究方向

本研究采用测验分类精度及测验效率两个方面的指标，将新提出的两种MCCT终止规则与已有的终止规则进行比较。在单维CCT中，基于不同类别被试间的能力阈值即可构造似然比统计量，并进行假设检验，从而达到对被试进行分类的目的。但在 MCCT中，由于不同类别被试的分界点变为分界曲线或曲面，故需要对传统CCT中的方法进行调整以适应这一变化。在已有的MCCT终止规则中，C-SPRT与P-SPRT规则分别使用约束与投影的方式，将能力分界曲线或曲面“压缩”为分界点；M-GLR规则对统计量的定义域进行一定的调整；M-SCSPRT 规则将随机缩减技术与C-SPRT 相结合，大大提高测验效率。值得注意的是，由于P-SPRT仅使用一次估计的能力结果进行投影，在测验初期可能会使投影得到的 $\widehat { \pmb { \theta } } _ { 0 }$ 不够稳定，从而影响测验分类。对此，本文提出基于马氏距离的Mahalanobis-SPRT新规则，以弥补这一不足。另外，本文在MCCT情境中还对单维的 SCGLR方法进行多维拓展，并得到M-SCGLR 新规则。

根据 4.1的结果，有一些值得讨论的发现：（1）对于本研究提出的M-SCGLR方法，在非补偿曲线和题目内多维的情境下，其PCC 较高，接近未使用随机缩减技术的方法。这可能是因为以广义似然比为基础的M-SCGLR方法不需要“将分界曲线转化为分界点”，所以受分界曲线的影响更小，而其他规则的PCC 在非补偿曲线的情境下会明显下降；（2）对于Mahalanobis-SPRT方法而言，尽管预期其能够弥补P-SPRT 在测验前期所产生的能力估计问题，但是它在模拟结果中的表现并不尽如人意。这可能是由于该方法在测验后期时，会使用较多测验前期的作答信息，从而加大测验前期作答对结果的影响。本研究所设置的最大测验长度为100，这意味着在测验结束时，往往能够得到比较准确的被试能力估计值。因此，Mahalanobis-SPRT方法对P-SPRT初期的能力估计问题的弥补可能就无法很好体现。当最大测验长度较小时，该方法可能会有更好表现；（3）在未使用随机缩减的4种规则中，M-GLR规则的ATL 较其他3种规则有较大幅度的减少，这与 Thompson（2011）在单维情境下得到的结论一致；（4）随着能力维度间相关系数 $\overset { \cdot } { \rho }$ 的增加，6种终止规则都有更好的表现。这主要是因为增加维度间相关有助于提高能力向量的估计精度。这也与贝叶斯统计中的普遍观点（即从高度相关的维度中借用信息会产生更准确的能力估计）一致；（5）相比于非补偿的分界曲线，6种终止规则在几乎所有的补偿性分界曲线情境下都有更好的表现，这是因为本研究所使用的M3PL模型是补偿性模型，其与补偿性的分界曲线更为契合，所以导致“在补偿性曲线情境下，各个终止规则的表现更好"；（6）题库结构与分界曲线会对终止规则的表现产生交互作用。具体而言，在补偿性分界曲线的情境下，相比于题目间多维的条件，6种终止规则在题目内多维条件下的表现更好。这可能是因为相较于题目间多维的题库结构，题目内多维的题库结构能够提供更高的多维区分度，从而提高能力估计的准确性。具体来说，对于有着题目内多维结构的题库1来说，每个维度被所有900个题目测量；而对于有着题目间多维结构的题库2来说，每个维度只有450个题目测量（一半题目的 $a _ { 2 } = 0$ ，另一半题目$a _ { 1 } = 0$ )。但是在非补偿分界曲线的情境下，6种规则在题目内多维与题目间多维的差异就没有统一规律。这可能是由于本研究考虑的非补偿边界其实就是直角坐标系中构成第一象限的坐标轴，所以边界上的能力阈值都只具有单一维度，导致题目内多维的上述优势不能很好发挥。

此外，还需要注意的一点是MCCT中的能力维度数量。理论上看，随着维度数的增加，平均测验长度会逐渐增加，而测验精度则会有下降趋势。但是，MCCT是一个相当复杂的系统。当维度数不断增大时，平均测验长度和测验精度将会呈现何种变化趋势（是指数式的变化还是线性的变化？）、不同终止规则与不同选题策略的组合会对结果造成何种影响以及随机缩减技术的优势是否会进一步扩大，都有待进一步的研究。同时，当维度数增大到一定程度时，计算机还将会面临一些计算上的挑战。

本研究仍有一些不足之处，比如：本文主要局限于提出新规则以及模拟实现上，在对新规则理论性质的推导和证明等方面仍有待完善。本研究所讨论的规则均限定在对被试进行二分的情境下，而没有考虑多分类的情况。在模拟研究的设置上，本研究没有考虑非补偿 MIRT模型、其他的多维区分度参数生成方式、不同的维度数以及不同的最大测验长度对结果的影响。

未来可以从以下四方面进一步开展研究：（1）提出新的多维似然比统计量。考虑构造将能力分界曲线或曲面转化为分界点的新方法，使得“在保证良好的分类准确率及测验效率的同时，能较好解决目前方法中存在的问题"；（2）开发多分类MCCT的终止规则。目前，有研究者对多分类的CCT终止规则进行探索（比如，Wangetal.,2020)，但是对多分类MCCT终止规则的研究仍未见公开报道。构造多分类MCCT终止规则可实现在多维情境下对被试的更细致分类，值得今后进一步探索；(3)考虑融入过程性信息，比如反应时(response time)。已有研究表明，反应时能够提高能力估计精度（Wang＆Hanson,2005）。结合反应时构造MCCT终止规则，预期在保证测验效率的同时还能进一步提高分类精度。此外，由于马氏距离具有“不受量纲影响”和“能够同时考虑能力与反应时信息”等特点，因此本研究提出的Mahalanobis-SPRT可为这方面的探索提供一种可行路径；（4）在模拟研究中，考虑更丰富的条件设置（比如，不同的MIRT 模型、多维区分度参数的生成方式、维度数以及最大测验长度等)，考察其对结果的影响。

# 6结论

模拟结果显示：（1）在使用补偿性分界函数的条件下，新提出的Mahalanobis-SPRT 规则具有较高的分类精度以及与其他未使用随机缩减的方法相近的测验长度；（2）在几乎所有实验条件下，新提出的M-SCGLR 规则不仅在测验精度大幅优于同样采用随机缩减的 M-SCSPRT 规则，而且具有较短的测验长度；（3）6种终止规则在PCC 和ATL上对具有不同能力被试的敏感度呈现出一致的变化规律。

# 致谢

感谢不列颠哥伦比亚大学（UniversityofBritishColumbia）的在读博士生陈冠宇对本文摘要修改提供的帮助。

# 附录1M-SCGLR中 $P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big )$ 的推导

将被试作答至最大测验长度/时，对被试的分类判断与当前（作答 $j ^ { \prime }$ 道题）一致的概率记为 $P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big )$ 。具体地说，如果目前的临时判断为被试属于“未掌握”类别，则被试作答至最大测验长度时仍被判断为“未掌握”的概率为 $P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big )$ ；如果目前的临时判断为被试属于“掌握”类别，则被试作答至最大测验长度时仍被判断为“掌握”的概率为$P \big ( D _ { J } = m \big | C _ { i j ^ { \prime } } \big )$ 。不失一般性，我们对 $P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big )$ 的计算过程进行推导。

根据 Fineklman（2008)的研究，可以使用 Siegmund（1985）所描述的技巧。 $P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big )$ 实际上即为 $P ( C _ { i J } \leq C _ { 0 } | C _ { i j ^ { \prime } } )$ 。利用对数可加性以及中心极限定理，使用给定 $C _ { i { j ^ { \prime } } }$ 下条件分布的渐近正态性，可以得到

$$
\begin{array} { r } { P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big ) \approx \Phi \left( \frac { C _ { 0 } - \mathbb { E } _ { \theta } \left( C _ { i J } \big | C _ { i j ^ { \prime } } \right) } { \sqrt { \operatorname { v a r } _ { \theta } \left( C _ { i J } \big | C _ { i j ^ { \prime } } \right) } } \right) . } \end{array}
$$

由于 $C _ { i J }$ 中本身包含 $C _ { i { j ^ { \prime } } }$ 的部分，根据对数的可加性及条件期望的性质，可得到公式(A1)中 $\mathbb { E } _ { \pmb { \theta } } \big ( C _ { i J } \big | C _ { i j ^ { \prime } } \big )$ 的计算，即

$$
\begin{array} { r l } & { \mathbb { E } _ { \theta } \Big ( C _ { i j } | C _ { i j ^ { \prime } } \Big ) = \mathbb { E } _ { \theta } \left( \log \frac { \underset { \theta _ { 1 } \in \Theta _ { m } } { \operatorname* { s u p } } } { \underset { \theta _ { 2 } \in \Theta _ { m } } { \operatorname* { s u p } } } \big [ L ( \theta _ { 1 } | Y _ { i j } ) \big ] \bigg | \right) C _ { i j ^ { \prime } } \Bigg ) } \\ & { = \mathbb { E } _ { \theta } \left( \sum _ { j = 1 } ^ { j ^ { \prime } } \log \frac { \underset { \theta _ { 1 } \in \Theta _ { m } } { \operatorname* { s u p } } } { \underset { \theta _ { 2 } \in \Theta _ { m } } { \operatorname* { s u p } } } \big [ L ( \theta _ { 1 } | Y _ { i j } ) \big ] \big ] + \sum _ { j = j ^ { \prime } + 1 } ^ { J } \log \frac { \underset { \theta _ { 1 } \in \Theta _ { m } } { \operatorname* { s u p } } \big [ L ( \theta _ { 1 } | Y _ { i j } ) \big ] } { \underset { \theta _ { 2 } \in \Theta _ { m } } { \operatorname* { s u p } } } \Big | C _ { i j ^ { \prime } } \right) } \\ & { = C _ { i j ^ { \prime } } + \sum _ { j = j ^ { \prime } + 1 } ^ { J } \mathbb { E } _ { \theta } \left( \log \frac { \underset { \theta _ { 1 } \in \Theta _ { m } } { \operatorname* { s u p } } } { \underset { \theta _ { 2 } \in \Theta _ { m } } { \operatorname* { s u p } } } \big [ L ( \theta _ { 1 } | Y _ { i j } ) \big ] \right) . } \end{array}
$$

类似地，根据作答反应的条件独立性及条件方差的性质，可得

$$
\begin{array} { r l } & { \mathrm { V a r } _ { \theta } \big ( C _ { i j } | C _ { i j ^ { \prime } } \big ) = \mathrm { V a r } _ { \theta } ( \displaystyle \operatorname* { l o g } _ { \theta \ge \Theta } [ L ( \theta _ { 1 } | \nabla _ { i j } ) ]  C _ { i j ^ { \prime } } ) } \\ & { \quad = \mathrm { V a r } _ { \theta } ( \displaystyle \sum _ { j = 1 } ^ { N } \log [ L ( \theta _ { 2 } | \nabla _ { i j } ) ] ) } \\ & { \quad = \mathrm { V a r } _ { \theta } ( \displaystyle \sum _ { j = 1 } ^ { N } \log \frac { \mathsf { I } _ { i } ( \theta _ { 1 } | Y _ { i j } ) } { \theta _ { 2 } \in \Theta _ { n } } [ L ( \theta _ { 1 } | Y _ { i j } ) ] ) + \displaystyle \sum _ { j = j ^ { \prime } + 1 } ^ { N } \log \frac { \mathsf { I } _ { i } ( \theta _ { 1 } | Y _ { i j } ) } { \theta _ { 2 } \in \Theta _ { n } } [ L ( \theta _ { 2 } | Y _ { i j } ) ]  C _ { i j ^ { \prime } } \Bigg ) } \\ & { \quad = \displaystyle \sum _ { j = j ^ { \prime } + 1 } ^ { J } \mathrm { V a r } _ { \theta } ( \log \frac { \operatorname* { s u p } _ { \theta } [ L ( \theta _ { 1 } | Y _ { i j } ) ] } { \operatorname* { s u p } _ { \theta \in \Theta _ { n } } [ L ( \theta _ { 2 } | Y _ { i j } ) ] } ) . } \end{array}
$$

实际上，Huebner和Fina（2015)在单维情境下已对这一过程进行推导。与单维的 SCGLR相比，在本文考虑的 MCCT 情境中，M-SCGLR只是将 $C _ { i { j ^ { \prime } } }$ 中求极值的集合由单维的区间变为多维空间中的区域，因此其推导过程是一致的。

# 附录2各终止规则的模拟结果

表2图2所对应的模拟结果  

<html><body><table><tr><td>相关</td><td>分界曲线</td><td>题库结构</td><td>终止规则</td><td>PCC</td><td>ATL</td></tr><tr><td rowspan="4">p=0</td><td rowspan="4">补偿性</td><td rowspan="4">题目内多维</td><td>C-SPRT</td><td>0.948</td><td>52.959</td></tr><tr><td>P-SPRT</td><td>0.948</td><td>49.541</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.950</td><td>53.216</td></tr><tr><td>M-GLR</td><td>0.924</td><td>32.241</td></tr><tr><td></td><td></td><td></td><td>M-SCGLR</td><td>0.858</td><td>18.849</td></tr></table></body></html>

<html><body><table><tr><td colspan="3">题目间多维</td><td>0.807</td><td>12.649</td></tr><tr><td rowspan="9"></td><td rowspan="9"></td><td>M-SCSPRT C-SPRT</td><td>0.930</td><td>61.981</td></tr><tr><td>P-SPRT</td><td>0.929</td><td>57.835</td></tr><tr><td></td><td>0.930</td><td>58.876</td></tr><tr><td>Mahalanobis-SPRT M-GLR</td><td>0.904</td><td>36.016</td></tr><tr><td>M-SCGLR</td><td>0.851</td><td>20.848</td></tr><tr><td>M-SCSPRT</td><td>0.805</td><td>13.504</td></tr><tr><td>C-SPRT</td><td>0.908</td><td>69.070</td></tr><tr><td>P-SPRT</td><td>0.915</td><td>55.622</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.873</td><td>57.369</td></tr><tr><td rowspan="8">题目内多维 非补偿性</td><td>M-GLR</td><td>0.916</td><td>41.331</td><td></td></tr><tr><td>M-SCGLR</td><td></td><td></td><td>26.151</td></tr><tr><td>M-SCSPRT</td><td></td><td>0.879 0.829</td><td>17.048</td></tr><tr><td></td><td>C-SPRT</td><td>0.931</td><td>61.163</td></tr><tr><td></td><td>P-SPRT</td><td>0.927</td><td>58.847</td></tr><tr><td>题目间多维</td><td>Mahalanobis-SPRT</td><td>0.909</td><td>58.686</td></tr><tr><td>M-GLR</td><td></td><td>0.919</td><td>36.718</td></tr><tr><td>M-SCGLR M-SCSPRT</td><td></td><td>0.864</td><td>20.974</td></tr><tr><td rowspan="10">补偿性</td><td>题目内多维</td><td></td><td>0.825</td><td>14.012</td></tr><tr><td rowspan="7"></td><td>C-SPRT</td><td>0.949</td><td>51.839</td></tr><tr><td>P-SPRT</td><td>0.949</td><td>46.301</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.951</td><td>49.922</td></tr><tr><td>M-GLR</td><td>0.929</td><td>28.306</td></tr><tr><td>M-SCGLR</td><td>0.880</td><td>16.641</td></tr><tr><td>M-SCSPRT</td><td>0.848</td><td>12.333</td></tr><tr><td>C-SPRT</td><td>0.942</td><td>60.648</td></tr><tr><td rowspan="5">题目间多维</td><td>P-SPRT</td><td>0.943</td><td>54.795</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.942</td><td>55.901</td></tr><tr><td>M-GLR</td><td>0.921</td><td>32.052</td></tr><tr><td>M-SCGLR</td><td>0.879</td><td>20.429</td></tr><tr><td>M-SCSPRT</td><td>0.836</td><td>13.478</td></tr><tr><td rowspan="8">p = 0.5 题目内多维 非补偿性</td><td rowspan="8"></td><td>C-SPRT</td><td>0.915</td><td>69.277</td></tr><tr><td>P-SPRT</td><td>0.918</td><td>56.422</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.890</td><td>54.840</td></tr><tr><td>M-GLR</td><td>0.917</td><td>41.205</td></tr><tr><td>M-SCGLR</td><td>0.879</td><td>25.501</td></tr><tr><td>M-SCSPRT</td><td>0.843</td><td>16.417</td></tr><tr><td>C-SPRT</td><td>0.931</td><td>65.105</td></tr><tr><td>P-SPRT</td><td>0.931</td><td>61.374</td></tr><tr><td rowspan="5"></td><td>题目间多维</td><td>Mahalanobis-SPRT</td><td>0.917</td><td>57.084</td></tr><tr><td>M-GLR</td><td></td><td>0.925</td><td>37.549</td></tr><tr><td>M-SCGLR</td><td></td><td>0.876</td><td>21.250</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>M-SCSPRT</td><td></td><td>0.839</td><td>13.966</td></tr></table></body></html>

<html><body><table><tr><td rowspan="7">补偿性</td><td rowspan="7">题目内多维</td><td>C-SPRT</td><td>0.960</td><td>50.987</td></tr><tr><td>P-SPRT</td><td>0.957</td><td>45.382</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.961</td><td>48.457</td></tr><tr><td>M-GLR</td><td>0.946</td><td>27.139</td></tr><tr><td>M-SCGLR</td><td>0.896</td><td>16.513</td></tr><tr><td>M-SCSPRT</td><td>0.858</td><td>12.313</td></tr><tr><td>C-SPRT</td><td>0.958</td><td>58.903</td></tr><tr><td rowspan="6">题目间多维</td><td>P-SPRT</td><td>0.958</td><td>52.540</td></tr><tr><td>Mahalanobis-SPRT</td><td>0.958</td><td>53.414</td></tr><tr><td>M-GLR</td><td>0.939</td><td>30.312</td></tr><tr><td>M-SCGLR</td><td>0.897</td><td>19.343</td></tr><tr><td>M-SCSPRT C-SPRT</td><td>0.851 0.920</td><td>13.860</td></tr><tr><td>P-SPRT</td><td></td><td></td><td>68.485</td></tr><tr><td rowspan="6">非补偿性</td><td></td><td></td><td>0.928</td><td>56.274</td></tr><tr><td>题目内多维 M-GLR</td><td>Mahalanobis-SPRT</td><td>0.916</td><td>52.433</td></tr><tr><td>M-SCGLR</td><td></td><td>0.917</td><td>39.755</td></tr><tr><td>M-SCSPRT</td><td></td><td>0.902</td><td>25.742</td></tr><tr><td>C-SPRT</td><td></td><td>0.856</td><td>16.835</td></tr><tr><td rowspan="6"></td><td></td><td>0.944</td><td></td><td>65.928</td></tr><tr><td></td><td>P-SPRT</td><td>0.941</td><td>61.900</td></tr><tr><td>题目间多维</td><td>Mahalanobis-SPRT</td><td>0.933</td><td>55.232</td></tr><tr><td>M-GLR</td><td></td><td>0.935</td><td>35.541</td></tr><tr><td>M-SCGLR</td><td></td><td>0.898</td><td>20.446</td></tr><tr><td>M-SCSPRT</td><td>0.857</td><td></td><td>14.111</td></tr></table></body></html>

# 参考文献

Ackerman,TA.994).reatingatestformatioprofilefortdmesionallatensace.AppliedsychologicalMeasuent, 257-275.   
Bartroff,J.ikelan,&aiT.L).deealsisdtslatiostoputeddaieg Psychometrika,73,473-486.   
Chang,H.-H,&ing,Z.(996).Agobalinformatioapproachtmputerizeddaptivetstig.AppliedPsyhlogicalMesuent 20,213-229.   
Chen,P.(2016).Twonewolinecalibrationmethodsforcomputerizedadaptivetesting.ActaPsychologicaSinica,48,84198.   
[陈平.(2016).两种新的计算机化自适应测验在线标定方法．心理学报,48,1184-1198.]   
Chen,P.,& Wang,C.(016).Anewolinecalibrationmethodforultidimensionalcomputerizeddaptivetesting.Psychometika,81, 674-701.   
Chen,P.,Wang,CXinT,&Chang,H.(217).Developingneoiecalibrationmetodsforultidimesioalomputerddaptie testing.British Journal ofMathematical and Statistical Psychology,70,81-117.   
Finkelman,M.(3).AndaptationofstohasticurtailmenttotruncateWaldsiomputerzeddaptivetesting(Cepot 606).Los Angeles,CA: National Center for Research on Evaluation, Standards,and Student Testing.   
Finkelman,M.(o08).OnusingstochasticurtailmenttoshortentheSPRTisequentialmasterytesting.JoualofEducatioalnd Behavioral Statistics,33,442-463.   
Finkelman,.().Vasstictatietialasterystingdoloicalasueme,4.   
Finkelman,M.,He,Y,Kim,W,&ai,A.M.(o).Stochasticcurtailmentfhealthuestioaires:amethodtoducesodet burden.Statistics in Medicine,30,1989-2004.   
Guo,L.,Zheng,CJ,&anY.F.(l5).Exposurecontrolmethodsandterinationulesinariable-lengthognitivediagotic computerized adaptive testing.Acta Psychologica Sinica,47,129-140.   
[郭磊，郑蝉金，边玉芳.(2015).变长CD-CAT中的曝光控制与终止规则．心理学报,47,129-140.]   
Hartig,J.,&Hr,J.(o).eprseationofompetecisiulimensioalodelsii-itdet multidimensionality.Journal of Psychology,216,89-101.   
Huebner,A.R,&Fina,A.D.o5).estohasticallurtailedgneraedlikeliodratio:nwtnationcriterioforable length computerized classification tests.Behavior Research Methods,47,549-561.   
Kang,C.,&XiT.().wevelopentitstthory:ulimesialitesponsetryAdancesinsyhologicalcienc 18,530-536.   
[康春花，辛涛.(2010).测验理论的新发展:多维项目反应理论．心理科学进展,18,530-536.]   
Lewis,C.,&Sheehan,K. (199o). Using Bayesian decisiontheorytodesignacomputerized mastery test.ApliedPsychological Measurement,14,67-86.   
LiX.,Zhang,J,&Chang,H.(2).Lookahadcontentbalaningmethodinriable-lengthcomputerzedclasificatiotesting. British Journal ofMathematical and StatisticalPsychology,73,88-108.   
Nydick,S.(o13).Multidimensional masterytesting with CAT(Unpublisheddoctoral dissertation).UniversityofMiesota.   
Reckase,.D,inley.L.(982).etetriinuiimesallttaceoCitym Service.   
Segall,D.O.(1996).Multidimensional adaptive testing.Psychometrika, 61,331-354.   
Siegmund,D.(1985).Sequentialanalysis:testsandconfidenceintervals.Springer-Verlag.   
Smits,N.,&Finkelman,M.(013).Acomparisonofomputerzedlasiicationtestingandomputerzeddptivetstinginlinical psychology.Journal ofComputerized Adaptive Testing,1,19-37.   
Thompson,NA.ue)loesiutdtioteeedtsce of the International Association for Computerized Adaptive Testing,Arnhem,the Netherlands.   
Thompson,..(1)aeedaioctntech&o 1-7.   
Wald,A. (1947).Sequential analysis.JohnWiley.   
Wald,A.,&Wfoitz,J.(94).OptialracterofeqialpobbilityatioesteAalsoftemicalti, 326-339.   
Wang,C.,Chen,P.,&Huebr,A.(2).Stoppingrulesforultiategoryomputerzedlasiicationtsting.BritishJouralf Mathematical and Statistical Psychology.Advance online publication. https:/doi.org/10.111/bmsp.12202   
Wang,T.,&Hanson,B.(oo5).Developmentandcabrationofanitemrsponse modelthatincorporatesresponsetime.Applied   
Psychological Measurement,29,23-339.   
Wang,W.C.,&Chen,P.H.(2o4).Implementationandmeasurement efciencyofmultidimensionalcomputerzedadaptivetesting. Applied Psychological Measurement,28,450-480.

# Two New Termination Rules for Multidimensional Computerized Classification Testing

REN He, CHEN Ping

(Collaborative Innovation Center ofAssessment for Basic Education Quality, Beijing Normal University, Beijing100875,China)

# Abstract

Computerized classification testing(CCT) is a subset of computerized adaptive testing (CAT),and it aims to classify examinees into one of at least two possible categories that denote results such as pass/fail or non-mastery/partial mastery/mastery (Huebner & Fina, 2015). Therefore, CCTs focus on increasing the accuracy of classification which is different from CATs designed for precise measurement (Nydick, 2O13). The termination rule is one of the key components of CCT. However, as pointed out by Nydick (2013), most CCTs (i.e., UCCTs) were designed under unidimensional item response theory (IRT), in which the unidimensionality assumption is easily violated in practice. Thus, researchers then began to construct multidimensional CCT termination rules (i.e., MCCT) based on multidimensional IRT. To date, however, these rules still have some deficiencies in terms of classification accuracy or test efficiency.

Most current studies on termination rules of MCCT are based on termination rules of UCCT. In UCCTs, termination rules require seting a cut point, $\theta _ { 0 }$ , of the latent trait to calculate the statistics; and when they are extended from UCCT to MCCT, the cut point will become a classification bound curve or even a surface (i.e., $g ( \pmb \theta ) = 0 ,$ ). At this time,a question is how to convert the curve or surface into $\theta _ { 0 }$ . To this end, the projected sequential probability ratio test (PSPRT), constrained SPRT (C-SPRT; Nydick, 2013),and multidimensional generalized likelihood ratio (M-GLR) were respectively proposed to solve the problem in different ways. Among them, P-SPRT and C-SPRT choose specific points on $\ g ( \theta )$ as the approximate cut point, $\widehat { \theta } _ { 0 }$ ,by projecting into Euclidean space or constraining on $\ g ( \theta )$ respectively; as for M-GLR, because the generalized likelihood ratio statistic can be calculated without a cut point, it can be directly employed in MCCT.To overcome the limitation that P-SPRT may lead to unstable results at the beginning of the test, this study proposed the Mahalanobis distance-based SPRT (MahalanobisSPRT).

In addition, stochastic curtailment is a technique for shortening the test length by predicting whether the classification of participants will change as the test continues. This article also combined M-GLR with the stochastic curtailment and proposed M-GLR with stochastic curtailment (M-SCGLR).

A full-scale simulation study was conducted to (1) compare both the Mahalanobis-SPRT and M-SCGLR with the P-SPRT, C-SPRT,M-GLR,and multidimensional stochastically curtailed SPRT (M-SCSPRT) under varying conditions; (2) compare the classification performance of the above six termination rules for participants with specific abilities to explore whether there is a significant difference in the sensitivity of various rules to classify specific participants.To achieve the first research objective,three levels of correlation between dimensions ( $( \rho = 0$ ，0.5,and 0.8), two item bank structures (within-item multidimensionality and between-item multidimensionality),and two kinds of classification boundary (compensatory boundary and noncompensatory boundary) were considered; to achieve the second objective,36 specific ability points $( \theta _ { 1 } , \theta _ { 2 } )$ were generated where $\theta _ { 1 } , \theta _ { 2 } \in \{ - 0 . 5 , - 0 . 3 , - 0 . 1 , 0 . 1 , 0 . 3 , 0 . 5 \}$ . The results showed that: (1) when the compensatory classification function was used,the Mahalanobis-SPRT led to higher classification accuracy and similar test length to the rules without stochastic curtailment; (2) under almost all conditions,the M-SCGLR not only possessed higher precision but also maintained the short test length, compared to M-SCSPRT that also uses stochastic curtailment; (3) the six termination rules showed a consistent change in the sensitivity of the precision and test length to specific participants.

To sum up, two new MCCT termination rules (Mahalanobis-SPRT and M-SCGLR) are put forward in this article.Although the simulation results are very promising,several research directions merit further investigation, such as the development of MCCT termination rules for more than two categories, and the construction of MCCT termination rules by incorporating process data like the response time.

Key words computerized classfication testing, termination rule, multidimensional item response theory, Mahalanobis distance, stochastic curtailment