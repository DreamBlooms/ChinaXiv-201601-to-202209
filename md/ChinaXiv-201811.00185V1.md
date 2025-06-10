# 基于模糊理论的最优序贯拍卖策略研究

纪颖，马刚，屈绍建(上海理工大学 管理学院，上海 200093)

摘要：基于模糊理论，通过将之前拍卖的类似物品回报进行模糊参数化，采用均值一方差对其进行收益和风险的刻画和度量。针对这两个准则提出基于柯布一道格拉斯生产函数的多准则优化函数，进而构建了基于模糊理论的序贯拍卖的顺序策略优化模型；其次，通过集成模糊模拟算法和多准则0-1遗传算法，用于求解该顺序策略优化模型；最后，算例分析比较了五种顺序策略以及优化策略，显示通过模型求解得到的最优策略能够以较低风险取得较高收益。

关键词：序贯拍卖；模糊理论；最优策略；多准则0-1遗传算法 中图分类号：F713.359 doi: 10.19734/j.issn.1001-3695.2018.05.0497

Optimal sequential auction strategy based on fuzzy theory

Ji Ying, Ma Gang†, Qu Shaojian (Business School,University ofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract:Thispaperadopts fuzzytheorytocreatethe fuzzy parameterofthereturn byhistorydataofsimilar products anduses Mean-variance model tocarve and estimate returnand risk.Moreover,based onadapting Cobb-Douglas productionfunction to building themulti-criteriaoptimalfunction,theoptimalsequencestrategymodelisbuilt.Then,integrating thefuzzysiulation and multi-criteria O-1genetic algorithmcansolve the model.Lastly,the numeral example shows theoptimal strategythat is derived by model is superior to the strategy that only other five sequence strategies.

Key Words: sequential auction; fuzzy theory; optimal strategy; multi-criteria O-1 genetic algorithm

# 0 引言

随着“互联网 $+$ ”的发展，二手车网上拍卖平台开始大量出现。2014年，二手车线上拍卖市场成交量便已到达了350000辆，成交额达192.6亿。2014年建立的“人人车”线上二手车拍卖平台，于当年便迅速覆盖21个城市，月交易量达到3000辆[]。二手车拍卖竞价作为连续购买环境下的典型代表，其产生的热点问题，即拍卖商关心的重点往往是针对不同的物品，如何制定拍卖顺序策略，才能以较低的风险获取较大的收益。尤其近年来该行业异常火热，因此研究序贯拍卖策略具有重要的理论意义和实际价值。

由于决策环境的不确定性和复杂性，对于不同的商品，如果采用不同的拍卖顺序，其成交价便存在各种变化的可能性。所以，特别是在拍卖商缺乏竞拍者的现有相关信息如对物品的估值分布、支付意愿等的情况下[3]，怎样对不同价值物品的拍卖顺序进行决策，便成为序贯拍卖顺序策略的研究热点。Salladarré等人[2采用实证研究说明即使是同样的商品，在一天内的价格都会受众多因素影响而发生异常减价的现象，从侧面说明了对于不同的物品在不同的拍卖顺序下带来的收益也将存在极大的不确定性。

不同次序拍卖策略的不确定性主要有以下四个方面：a）在实际拍卖过程中，市场走势千变万化，获取当前竞拍者准确的相关信息（估值分布、其他信息数据）极其困难；b）不同策略或是不同的情形下，竞拍者对物品的估值信息以及报价都会发生变化，即同一物品在不同次序下进行拍卖会产生不同收益和风险；c）任何拍卖都存在流拍的可能，即物品在拍卖结束时存在未达成交易的可能性；d)拍卖中竞争程度的不确定性，如拍卖商无法准确判断将要举行的拍卖会竞价的激烈程度。因此，参照之前类似商品拍卖的收益或回报制定的策略，可以为拍卖商提供些许帮助。

在以往的研究中，最常见的一种顺序策略是按物品的价值由高到低的进行拍卖物品，即“高一低”策略；以及文献[4]描述的策略：拍卖商更偏好从低到高的顺序拍卖物品，即“低一高”策略。在这两种极端顺序策略之间，还有很多顺序策略。如想要先拍卖低价值的物品进行热场[5的“低一高一低"策略，以及用于吸引买者的“高一低一高”策略[。为了研究最优的顺序策略，本文在算例分析中比较分析了这四种顺序策略的收益和风险。

对拍卖商而言，如何制定顺序策略进行拍卖，使自己以较低的风险得到较高的收益，是目前序贯拍卖策略研究的难点。不管制定哪种顺序策略，都将使得拍卖产生不确定性。而前人对拍卖顺序策略的研究，大多集中于竞拍者的出价策略和购买行为上，如从竞拍者预算约束的角度考虑购买顺序[7]，从竞拍者竞价顺序[8]以及是否选择预定[9等行为角度进行决策思考。但是采用模糊理论对拍卖顺序策略不同导致物品回报（最高报价）的不确定性的研究,目前还鲜有人涉及。

前人基于模糊理论研究拍卖问题，大多只是使用模糊参数描述出价意愿并将其取代估价作为收益或效用分析[10]，或是采用模糊粗糙集的方式评估物品多属性[11,12]等，均未涉及对不同次序拍卖产生收益的模糊化的研究。本文将某物品于某次序进行拍卖的回报定义为模糊变量，从而由均值一方差模型得到相应次序的拍卖物品的不确定性收益（均值)和不确定性风险（方差)。而模糊变量的获得和确定往往是根据历史数据（之前类似物品的成交价）获得和确定[13]。

为了更全面地描述序贯拍卖不同次序策略的收益和风险，本文参考模糊理论对参数或数据的不确定性处理方法，如多期投资组合的收益和风险不确定的研究[13]、经济寿命评估中参数不确定性的模糊模拟[14]等，建立序贯拍卖策略不同次序的不确定性收益一风险优化模型（F-SAmodel)。

为了有效评估不确定性收益和不确定性风险，本文采用均值一方差模型来评估不同的序贯拍卖策略下拍卖商的收益和风险。鉴于收益、风险是拍卖商考虑拍卖顺序策略的两个重要准则，本文采用多准则方法进行决策优化。不同于刘树林等人[15]将柯布一道格拉斯生产函数（Cobb-Douglas production function）使用在进行竞拍者效用与获胜的偏好选择，本文主要通过该函数，从拍卖商的角度对收益最大化、风险最小化两个目标进行决策分析。同时在上述研究成果的基础上，综合考虑收益不确定性和风险不确定性，采用均值一方差模型进行多准则优化。基于模糊理论，为制定序贯拍卖的顺序策略构建了多准则优化模型，并提出了基于模糊模拟的多准则遗传算法（F-MCGAalgorithm）求解该模型。特别在算例分析中针对不同价值的多个物品，比较了在“高一低”“低一高”“低一高一低”“高一低一高”、文献[10]中的策略以及优化策略六种不同策略下的拍卖商的收益和风险。

# 1 模糊理论

给定一个全集（Universe） $\Gamma$ ， $p ( \Gamma )$ 是其中的幂集（powerset），每一个 $p ( \Gamma )$ 元素都是一个事件。置信性测度 $\mathrm { C r }$ （credibility measure）是 $p ( \Gamma )$ 的集函数（setfunction），且$\mathrm { C r } \in [ 0 , 1 ]$ 。刘宝锭等人[16,17]通过提出模糊变量、期望值算子等概念建立起完整的模糊理论，从而为处理模糊变量提供了理论依据。

公理1对于全集 $\Gamma$ ， $\mathrm { { C r } \{ \Gamma \} = 1 }$ 。

公理2对任意事件 $\mathbf { A } \subseteq \mathbf { B }$ ，且 $\mathbf { A } , \mathbf { B } \in \Gamma$ ，则$\mathbf { C r } \{ \mathbf { A } \} \le \mathbf { C r } \{ \mathbf { B } \}$ 。

公理3事件 ${ \bf A } ^ { \mathrm { c } }$ 是事件的A的补集，那么$\scriptstyle \mathbf { C r } \{ \mathbf { A } \} + \mathbf { C r } \{ \mathbf { B } \} = 1$ 。

公理4对于S $ { \operatorname { u p } } _ { i } \mathrm { C r } \{  { \mathbf { A } } _ { i } \} { < } 0 . 5$ 的事件 $\{ \mathbf { A } _ { i } \}$ 的任意组合,都有 $\scriptstyle \mathbf { C r } \{ \mathbf { U } _ { i } \mathbf { A } _ { i } \} = \mathbf { s u p } _ { i } \mathbf { C r } \{ \mathbf { A } _ { i } \}$ 。

所以，当 $\mathrm { C r }$ 是置信性测度时， $( \Gamma , p ( \Gamma ) , \mathrm { { C r } ) }$ 被称做置信性空间。当 $\xi$ 是一个 $( \Gamma , p ( \Gamma ) , \mathrm { { C r } ) }$ 置信性空间内的模糊变量时，对于实数集 $\Re$ ，有以下定义。

定义1若 $\xi$ 是一个 $( \Gamma , p ( \Gamma ) , \mathrm { { C r } ) }$ 置信性空间的一个模糊变量，从其置信性测度中得到 $\xi$ 的置信性函数，$\boldsymbol { \varpi } ( \boldsymbol { x } ) = \mathbf { C } \mathbf { r } \{ \boldsymbol { \xi } = \boldsymbol { x } \} , \ \forall \boldsymbol { x } \in \mathfrak { R } \ \circ$ （20

定义2 $( \xi _ { 1 } , \xi _ { 2 } , . . . \xi _ { n } )$ 是定义在 $( \Gamma , p ( \Gamma ) , \mathrm { { C r } ) }$ 置信性空间上的模糊向量，那么它的联合置信性函数也可以从置信性测度中得到，即 $\nu ( x _ { 1 } , x _ { 2 } . . . x _ { n } ) = \mathbf { C r } \{ \xi _ { 1 } = x _ { 1 } , \xi _ { 2 } = x _ { 2 } , . . . \xi _ { n } = x _ { n } \}$ ，$( x _ { 1 } , x _ { 2 } . . . x _ { n } ) \in \mathfrak { R } ^ { \mathfrak { n } }$ 。

定义3只有当条件 $\begin{array} { r } { \nu ( x _ { 1 } , x _ { 2 } . . . x _ { n } ) = \operatorname* { m i n } _ { 1 \leq x \leq n } \varpi _ { i } ( x _ { i } ) } \end{array}$ ，(x,x.X)∈R"满足时，,,.才是相互独立的模糊变量,模糊向量(,,.n)的联合置信性函数为min1<x≤s(x）。

定义4若 $\xi$ 是模糊变量，其置信性函数为 $\nu$ ，对任意的实数集 $B$ ，都有

$$
\operatorname { C r } \{ \xi = B \} = { \left\{ \begin{array} { l l } { \displaystyle \operatorname* { s u p } _ { x \in B } \varpi ( x ) , \operatorname* { s u p } _ { x \in B } \varpi ( x ) < 0 . 5 } \\ { \displaystyle 1 - \operatorname* { s u p } _ { x \in B } \varpi ( x ) , 1 - \operatorname* { s u p } _ { x \in B } \varpi ( x ) \geq 0 . 5 } \end{array} \right. }
$$

定义5假设 $\xi _ { 1 } , \xi _ { 2 } , . . . \xi _ { n }$ 是相互独立的模糊变量，如果函数 $f$ 是 $\Re ^ { \mathfrak { n } }$ 到 $\Re$ 的映射，那么模糊变量 $f ( \xi _ { 1 } , \xi _ { 2 } , . . . \xi _ { n } )$ 的置信性函数 $\mu ( z )$ 为

$$
\mu ( z ) = \left\{ \begin{array} { l l } { \underset { f ( x ) } { \operatorname* { s u p } } \underset { 1 \leq i \leq n } { \operatorname* { m i n } } \varpi _ { i } ( x _ { i } ) , \underset { x \in B } { \operatorname* { s u p } } \underset { 1 \leq i \leq n } { \operatorname* { m i n } } \varpi _ { i } ( x _ { i } ) < 0 . 5 } \\ { 1 - \underset { f ( x ) } { \operatorname* { s u p } } \underset { 1 \leq i \leq n } { \operatorname* { m i n } } \varpi _ { i } ( x _ { i } ) , \underset { x \in B } { \operatorname* { s u p } } \underset { 1 \leq i \leq n } { \operatorname* { m i n } } \varpi _ { i } ( x _ { i } ) \geq 0 . 5 } \end{array} \right.
$$

其中： $z \in \Re$ ； $\varpi _ { i }$ 是 $\xi _ { i }$ 的置信性函数， $i = 1 , 2 , . . . n$ 。

定义6当 $\xi$ 是一个 $( \Theta , \operatorname { P } , \operatorname { C r } )$ 置信空间内的模糊变量时，它的期望值为 $E ( \xi ) = \int _ { 0 } ^ { + \infty } \mathrm { C r } \{ \xi \ge r \} d r - \int _ { - \infty } ^ { 0 } \mathrm { C r } \{ \xi \le r \} d r$ ，其中两个积分中至少有一个是有限的。

定义7当 $\xi$ 是一个具有期望值 $E ( \xi )$ 的模糊变量时，其方差可以表示为 $V ( \xi ) = \int _ { 0 } ^ { + \infty } \mathbf { C r } \{ [ \xi - E ( \xi _ { i t } ) ] ^ { 2 } \geq r \} d r \ \mathrm { ~ c ~ }$ （20

# 2 模糊序贯拍卖顺序策略模型

拍卖商共有 $n$ 个不同价值的物品，整场拍卖共有 $T$ 次序（顺序拍卖策略的次序)。拍卖商决定在第 $t$ 次序 $( t = 1 , 2 , . . . T )$ 拍卖物品 $i$ ， $( i = 1 , 2 , . . . n )$ 。将拍卖商的决策：是否将物品 $i$ 在第 $t$ 次序进行拍卖，定义为决策变量 $x _ { i t }$ ， $x _ { i t } \in \{ 0 , 1 \}$ 。用模糊变量 $\xi _ { i j }$ 表示该决策带来的不确定性，即将物品 $i$ 第 $\mathbf { \Phi } _ { t }$ 次序卖出的不确定性收益。

在第 $t$ 次序拍卖物品 $i$ 的收益为

$$
\textstyle R _ { t } = \sum _ { i = 1 } ^ { n } \xi _ { i t } x _ { i t } ~ , ( i = 1 , 2 , . . . n )
$$

整场拍卖的收益为

$$
w _ { T } = \sum _ { t = 1 } ^ { T } R _ { t } + \sum _ { i = 1 } ^ { n } \Biggl ( 1 - \sum _ { t = 1 } ^ { T } x _ { i t } \Biggr ) \nu _ { i } - \sum _ { i = 1 } ^ { n } \Biggl ( 1 - \sum _ { t = 1 } ^ { T } x _ { i t } \Biggr ) c _ { i } \ ,
$$

$$
( \sum _ { t = 1 } ^ { T } x _ { i t } \leq 1 ; i = 1 , 2 , . . . n ; t = 1 , 2 , . . . T )
$$

式子的第一部分为物品 $i$ 在第 $t$ 次序的收益。拍卖商选择保留物品 $i$ 不进行拍卖，则收益应为其本身的价值 $\nu _ { i }$ ，即上式的第二部分。第三部分是物品 $i$ 未卖出需要支付的存储成本 $c _ { i }$ ，假设 $\nu _ { \mathrm { } _ { i } } > c _ { \mathrm { } _ { i } } > 0$ 。

根据式（2）可以知道，拍卖的总收益函数 $w _ { T }$ 是关于模糊变量 $\xi _ { i t }$ 的函数，所以 $w _ { T }$ 也是一个模糊变量。通过模糊模拟计算收益 $w _ { T }$ 的期望 $E ( w _ { T } )$ 和风险（方差） $V ( w _ { T } )$ 。

对于拍卖商而言，追求收益的最大化 $E ( w _ { T } )$ 和风险的最小化 $V ( w _ { T } )$ 是两个主要的目标。对上述两个目标，本文通过柯布—道格拉斯生产函数（Cobb-Douglas production function），对两个目标的重要性进行权衡决策分析。假设其最低的预期收益为$a$ ，能接受的最大风险为 $b$ 。则目标函数 $f$ 为

$$
f = E ( w _ { T } ) ^ { \alpha } \Biggl ( 1 { - } \frac { V ( w _ { T } ) } { b } \Biggr ) ^ { \beta }
$$

其中： $\alpha$ 和 $\beta$ 分别表示拍卖商对预期收益和预期风险这两个目标的偏好程度，且 $\alpha + \beta = 1$ 。则基于模糊理论的不确定性序贯拍卖顺序策略模型（F-SAmodel）如下：

$$
\operatorname* { m a x } { f } = E ( w _ { T } ) ^ { \alpha } \left( 1 - \frac { V ( w _ { T } ) } { b } \right) ^ { \beta }
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { E ( w _ { T } ) \geq a } \\ { V ( w _ { T } ) \leq b } \\ { \displaystyle } \\ { \sum _ { t = 1 } ^ { T } x _ { t } \leq 1 } \\ { x _ { t } \leq \{ 0 , 1 \} } \\ { \quad } \\ { \quad } \\ { \quad } \\ { i = 1 , 2 , . . . n } \\ { \quad } \\ { t = 1 , 2 , . . . T } \end{array} \right. } \end{array}
$$

# 3基于模糊模拟的多准则遗传算法（F-MCGA algorithm)

为了求解上述模型(F-SAmodel)，本文采用模糊模拟算法（Fuzzy simulation）[18]计算 $E ( w _ { T } )$ 和 $V ( w _ { T } )$ 的值；然后针对多准则问题的柯布一道格拉斯目标函数进行多准则遗传算法（F-MCGAalgorithm）求解。

# 3.1随机模糊模拟算法

模糊模拟（fuzzysimulation）可以通过一系列的离散模糊向量 $y$ 来计算具有隶属度分布函数的模糊变量 $\xi$ 的近似值，进而估算 $\textstyle \sum _ { i = 1 } ^ { n } \xi _ { i t } x _ { i t }$ 的值。

决策变量 $\mathbf { x } = ( x _ { 1 1 } . . . x _ { n 1 } , x _ { 1 2 } . . . x _ { n 2 } , . . . , x _ { 1 T } . . . x _ { n T } )$ ，模糊变量（204号 $\boldsymbol { \xi } = ( \xi _ { 1 1 } . . . \xi _ { n 1 } , \xi _ { 1 2 } . . . \xi _ { n 2 } , . . . , \xi _ { 1 T } . . . \xi _ { n T } )$ 。根据上文的分析， $w _ { T }$ 是关于 $\mathbf { x }$ 和 $\xi$ 的函数。假定模糊变量 $\xi$ 有联合置信函数 $\varpi$ 。

首先随机生成 $N$ 个向量 $\mathbf { y } _ { 1 } , \mathbf { y } _ { 2 } { \ldots } \mathbf { y } _ { \mathbf { N } }$ ；然后计算其置信性测度， $\varpi _ { k } = \varpi ( \mathbf { y } _ { \mathrm { N } } ) , k = 1 , 2 . . . N$ 。

根据定义6和7，为计算 $E ( w _ { T } )$ 和 $V ( w _ { T } )$ ，要先计算置信性函数 $\mathbf { C r } \{ w _ { T } ( x , \pmb { \xi } ) \geq r \}$ 和 ${ \bf C r } \{ w _ { T } ( { \bf x } , \boldsymbol { \xi } ) \leq r \}$ 的近似值。

根据定义4，有 ${ \bf C r } \{ w _ { _ T } ( x , \pmb { \xi } ) \geq r \} =$

$$
\left\{ \begin{array} { l l } { \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) \ge r \right. \} , \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) \ge r \right. \} < 0 . 5 } \\ { 1 - \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) < r \right. \} , \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) \ge r \right. \} \ge 0 . 5 } \end{array} \right. ;
$$

$$
{ \bf C r } \{ w _ { \scriptscriptstyle T } ( x , \xi ) \leq r \} =
$$

$$
\left\{ \begin{array} { l l } { \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) \le r \right\} , \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) \le r \right\} < 0 . 5 } \\ { 1 - \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) > r \right\} , \operatorname* { m a x } \{ \varpi _ { k } \left| w _ { T } ( x , y _ { k } ) > r \right\} \ge 0 . 5 } \end{array} \right.
$$

然后通过模糊模拟算法求出模糊变量的均值和方差。具体过程如算法1所示。

算法1模糊模拟算法 1设定参数0=0。

2 随机生成向量 ${ \bf y } _ { 1 } , { \bf y } _ { 2 } . . . { \bf y _ { N } }$ ，并计算置信性测度 $\varpi _ { 1 } , \varpi _ { 2 } . . . . \varpi _ { N }$ 。

3设定参数 $\iota = \min \{ w _ { _ T } ( x , y _ { 1 } ) , w _ { _ T } ( x , y _ { _ 2 } ) . . . w _ { _ T } ( x , y _ { _ N } ) \}$ 以及$\rho = \operatorname* { m a x } \{ w _ { T } ( x , y _ { 1 } ) , w _ { T } ( x , y _ { 2 } ) . . . w _ { T } ( x , y _ { N } ) \} \$

4 随机生成一个实数 $r = [ \imath , \rho ]$ 。

5如果 $r \geq 0$ ,设 $\theta  \theta + \mathrm { C r } \{ w _ { T } ( x , \xi ) \geq r \} .$

6如果 $r < 0$ ,设 $\theta  \theta + \mathrm { C r } \{ w _ { T } ( x , \xi ) \leq r \}$

7重复步骤 $2 { \sim } 6$ ，重复 $N$ 次。

8返回值 $E ( w _ { T } ) = \operatorname* { m a x } \{ \iota , 0 \} + \operatorname* { m i n } \{ \rho , 0 \} + \theta \cdot ( \rho - \iota ) / \ : N \circ$

对于 $V ( w _ { T } )$ ，也可以通过上述算法实现，只要将 $\mathbf { \Phi } _ { t }$ 和 $\rho$ 分别替换为 $\iota = \operatorname* { m i n } \{ ( w _ { { } _ { T } } ( x , y _ { 1 } ) - E ) ^ { 2 } , . . . ( w _ { { } _ { T } } ( x , y _ { n } ) - E ) ^ { 2 } \}$ 以及$\rho = \operatorname* { m a x } \{ ( w _ { T } ( x , y _ { 1 } ) - E ) ^ { 2 } , . . . ( w _ { T } ( x , y _ { n } ) - E ) ^ { 2 } \}$ ，即可。

# 3.2多准则0-1遗传算法

Guo等人[13]提出的通过集成模糊仿真算法和遗传算法来求解多期投资组合的模糊问题后，该方法也被众多学者采用。因此，本文将集成模糊仿真算法和多准则求解0-1问题的遗传算法，求解多准则模糊随机不确定性序贯拍卖中顺序策略问题。以下为遗传算法求解步骤。

a)建立初始化种群。

首先将该问题的解，即决策变量 $\mathbf { x }$ ，进行编码成为具有二进制染色体个体的C，并对每一个个体中的染色体进行约束条件的判断，要求 $\sum _ { t = 1 } ^ { T } x _ { i t } \leq 1$ ，以及 $E ( w _ { T } ) \geq a$ ， $V ( w _ { T } ) \leq b$ 。只有满足所有条件的个体称为有效个体。定义一个整数参数 $n$ ，为种群规模。该步骤生成 $n$ 个有效个体，即规模为 $n$ 的种群farm。

b)适应度函数。

适应度函数，也叫评估函数，是为了将最优的染色体选出来而定的标准。最优的染色体有着较好的适应性，也就是说在下一代中出现的可能性比较大。只有不断地选出较优的染色体，才会在种群的不断演化中得到本文想要的结果。此不同于文献[13]，直接选取目标函数作为适应度函数。为便于计算，只取结果的实数部分进行比较。适应度函数为

$$
f ( c _ { i } ) = r e a l \bigg \{ E ( w _ { T } ) ^ { \alpha } ( 1 - \frac { V ( w _ { T } ) } { b } ) \bigg \}
$$

c)交叉重组与选择。

在 $n$ 个个体的种群随机选出某两个个体，分别将其任意多列进行倒序重组，生成两个新的个体。重复该生成过程，直到新个体数量达到 $2 n$ ，并与原种群合并为规模为 $3 n$ 的种群。将该种群满足约束条件的个体组成新的种群newfarm，计算其所有个体的适应度函数值，将其函数值最大的个体选出来，复制两次，替代newfarm 种群中任意两个个体，如算法2所示。

算法2交叉重组与选择

1从原 $n$ 种群中任意取出两个个体。

2 对这两个个体中的任意多列进行交换处理。  
3重复步骤1、2，直到生成 $2 n$ 的个体数量为止。  
4 将步骤3生成的 $2 n$ 规模种群与原种群合并，形成 $3 n$ 的种群。5对 $3 n$ 的种群中每个个体进行约束条件的判断， $E ( w _ { T } ) \ge a$ 以及$V ( w _ { T } ) \leq b$ 。  
6 对满足条件的标记为1， $\mathrm { F L A G } ( c _ { i } ) = 1$ ；不满足的标记为0,$\mathrm { F L A G } ( c _ { i } ) = 0$ 。对于所有满足条件的个体，组成新的种群newfarm。7计算新种群newfarm中所有个体的适应度函数值，  
$f ( c _ { i } \mid n e w f a r m ) ~ .$   
8 选择适应度函数值最大的个体随机复制两次替代farm种群中任意两个个体。

d)变异。

设定参数 $p m$ 为变异率， $r$ 是[0,1]上的随机数。当 $p m > r$ 时，第 $i$ 个个体中的任意染色体突变为1，否则突变为0。将突变后个体进行约束条件的判断，只有满足条件的个体替代种群farm中的第 $i$ 个个体，如算法3所示。

算法3变异

1 设定变异率 $p m$ ，以及 $i = 1$ 。  
2 产生一个随机数 $r \in [ 0 , 1 ]$ 。  
3当 $p m > r$ 时，第 $i$ 个个体中的任意染色体突变为1，否则突变为  
0。  
4 对每个个体进行约束条件进行判断， $E ( w _ { T } ) \ge a$ 以及 $V ( w _ { T } ) \leq b$ 。  
5 满足约束条件的个体替代farm 种群中的第 $i$ 个个体。  
6重复步骤 $2 { \sim } 5$ ，直到产生 $n$ 个个体。

将上述多准则0-1遗传算法总结为算法4。

算法4多准则0-1遗传算法

1生成初始 $n$ 个满足约束条件的个体，即种群farm。  
2 取出任意两个个体，对任意多列染色体进行交叉重组，直至生成 $2 n$   
数量的个体，并与种群farm合并为 $3 n$ 种群。  
3对 $3 n$ 种群中的个体进行约束条件的判断，将满足约束条件的个体  
组成新的种群newfarm。  
4计算种群newfarm每一个个体的适应度函数。  
5选取适应度大的个体作为复制两次替代原种群farm任两个个体。  
6变异更新种群farm 染色体。  
7重复步骤 $2 { \sim } 6$ ，重复次数为种群演化代数。  
8 得到演化后适应度函数值最大的个体，对应问题最优解。

# 4 算例分析

在一次二手车拍卖会上，拍卖商有10 辆不同的二手车将要出售，拟采用5次叫拍，完成整场拍卖。本文选取三角模糊数和梯形模糊数分别对模糊变量进行刻画。

对于不同价值的10辆二手车，其价值分别为$V _ { 0 } = [ 0 . 8 \ 1 . 0 1 \ 0 . 8 \ 1 . 1 \ 0 . 9 5 \ 1 . 2 \ 1 . 3 \ 0 . 8 8 \ 1 . 0 2 \ 1 . 0 5 ]$ ；若选择不售卖，将会支付存储费用c=[0.4 0.6 0.250.32 0.2 0.40.7 0.60.50.4]。拍卖商最低可以接受的期望收益为 $a = 1 0 . 5$ ，最高可以接受的风险为 $b = 0 . 2$ 。此外，假设目标函数中拍卖商的决策 $\alpha = 0 . 8$ ，

$\beta = 0 . 2$ 。

为比较策略“高一低”“低一高”“低一高一低”以及“高一低一高”的收益和风险，本文按10辆二手车的价值进行排序，分为高、较高、中等、较低、低五个等级，如表1所示。

Table1Value rating of different used cars   

<html><body><table><tr><td>价值等级</td><td>高</td><td>较高</td><td>中等</td><td>较低</td><td>低</td></tr><tr><td>二手车</td><td>6,7</td><td>4,10</td><td>2,9</td><td>5,8</td><td>1,3</td></tr></table></body></html>

# 4.1 三角模糊数算例

10辆不同的二手车在不同次序拍卖中会产生不同模糊变量，其三角模糊数如表2所示。

表2模糊变量的三角模糊数 (单位：十万)

表1不同二手车的价值等级  

<html><body><table><tr><td>二手车</td><td>次序1</td><td>次序2</td><td>次序3</td><td>次序4</td><td>次序5</td></tr><tr><td>1</td><td>(0.90 1.10 1.12)</td><td>(0.80 1.00 1.20)</td><td>(0.85 1.15 1.30)</td><td>(0.80 1.10 1.24)</td><td>(0.82 1.20 1.25)</td></tr><tr><td>2</td><td>(0.80 1.15 1.30)</td><td>(0.82 1.10 1.24)</td><td>(0.88 1.20 1.24)</td><td>(0.90 1.20 1.30)</td><td>(0.91 1.18 1.32)</td></tr><tr><td>3</td><td>(0.60 1.12 1.40)</td><td>(0.68 1.20 1.50)</td><td>(0.80 1.30 1.60)</td><td>(0.76 1.28 1.50)</td><td>(0.70 1.30 1.50)</td></tr><tr><td>4</td><td>(0.80 1.12 1.40)</td><td>(0.70 1.40 1.70)</td><td>(0.76 1.10 1.20)</td><td>(0.70 1.20 1.30)</td><td>(0.72 1.20 1.40)</td></tr><tr><td>5</td><td>(0.95 1.10 1.15)</td><td>(0.90 1.10 1.20)</td><td>(0.90 1.20 1.30)</td><td>(0.90 1.15 1.3)</td><td>(0.88 1.12 1.28)</td></tr><tr><td>6</td><td>(0.90 1.20 1.21)</td><td>(0.92 1.10 1.20)</td><td>(0.90 1.08 1.18)</td><td>(0.92 1.10 1.20)</td><td>(1. 00 1.05 1.25)</td></tr><tr><td>7</td><td>(0.88 1.10 1.34)</td><td>(0.80 1.10 1.40)</td><td>(0.72 1.31 1.62)</td><td>(0.78 1.31 1.62)</td><td>(0.80 1.20 1.30)</td></tr><tr><td>8</td><td>(0.96 1.08 1.20)</td><td>(0.94 1.01 1.22)</td><td>(0.94 1.10 1.18)</td><td>(0.90 1.10 1.15)</td><td>(0.92 1.09 1.16)</td></tr><tr><td>9</td><td>(0.50 1.20 1.30)</td><td>(0.40 1.30 1.42)</td><td>(0.55 1.20 1.60)</td><td>(0.50 1.22 1.58)</td><td>(0.60 1.25 1.65)</td></tr><tr><td>10</td><td>(0.65 1.30 1.70)</td><td>(0.70 1.20 1.50)</td><td>(0.70 1.40 1.50)</td><td>(0.72 1.38 1.48)</td><td>(0.70 1.40 1.60)</td></tr></table></body></html>

根据模糊仿真算法，对表2中的模糊数进行均值 $e _ { i t }$ 和方差$\nu _ { i t }$ 的求解(表3)。

Table 2Triangular fuzzy numbers of fuzzy variables (unit: one hundred thousand)   
表3模糊变量的均值（单位：十万）和方差  

<html><body><table><tr><td colspan="5">均值eit/方差Vit</td></tr><tr><td>二手车</td><td>次序1</td><td>次序2</td><td>次序3</td><td>次序4</td><td>次序5</td></tr><tr><td>1</td><td>1.06/0.036</td><td>1/0.064</td><td>1.11/0.01</td><td>1.06/0.01</td><td>1.12/0.0144</td></tr><tr><td>2</td><td>1.1/0.0144</td><td>1.07/0.01</td><td>1.13/0.01</td><td>1.15/0.01</td><td>1.15/0.0081</td></tr><tr><td>3</td><td>1.2/0.0576</td><td></td><td>1.15/0.0361 1.25/0.0324</td><td>1.21/0.0324</td><td>1.2/0.04</td></tr><tr><td>4</td><td>1.11/0.0169</td><td></td><td>1.3/0.0576 1.04/0.0121</td><td>1.1/0.0256</td><td>1.13/0.0256</td></tr><tr><td>5</td><td>1.08/0.0025 1.08/0.00491.15/0.01</td><td></td><td></td><td>1.13/0.0081</td><td>1.1/0.0081</td></tr><tr><td>6</td><td></td><td></td><td>1.13/0.0081 1.08/0.0036 1.06/0.0036 1.08/0.0036 1.09/0.0049</td><td></td><td></td></tr><tr><td>7</td><td>1.11/0.01</td><td></td><td>1.1/0.0144 1.11/0.0225 1.26/0.0361 1.13/0.0169</td><td></td><td></td></tr><tr><td>8</td><td></td><td></td><td>1.08/0.00251.09/0.0036 1.08/0.0036 1.06/0.0036 1.07/0.0036</td><td></td><td></td></tr><tr><td>9</td><td></td><td></td><td>1.05/0.0484 1.11/0.0784 1.14/0.0529 1.13/0.0625 1.19/0.0625</td><td></td><td></td></tr><tr><td>10</td><td></td><td></td><td>1.24/0.0529 1.15/0.0324 1.25/0.0484 1.24/0.0529 1.28/0.0529</td><td></td><td></td></tr></table></body></html>

策略“高—低”的拍卖顺序策略为HL(5,3.5,2,4,1,1,4,3,2)，即第一个物品在第5次序拍卖，第二个物品在第3次序拍卖，以此类推。目标函数值为 $\mathrm { H L } ( f ) = 4 . 0 6 7$ ，其中期望收益$E ( w _ { T } ) = 1 1 . 4 7$ （十万)，期望风险（方差） $V ( w _ { T } ) = 0 . 2 3 7 1$ 。

策略“低一高”的拍卖顺序策略为$\mathrm { L H } ( 1 , 3 , 1 , 4 , 2 , 5 , 5 , 2 , 3 , 4 )$ ，目标函数值为 $\operatorname { L H } ( f ) = 3 . 4 5 1 5$ ，其中期望收益 $E ( w _ { T } ) = 1 1 . 2 6$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 2$ 。

策略“低一高一低”的拍卖顺序策略为LHL(1,5,1,4,2,3,3,2,5,4)，目标函数值为 $\mathrm { L H L } ( f ) = 3 . 6 2 7 8$ ，其中期望收益 $E ( w _ { T } ) = 1 1 . 2 8$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 2 2 4$ 。

策略“高一低一高”的拍卖顺序策略为$\mathrm { H L H } ( 3 , 5 , 3 , 2 , 4 , 1 , 1 , 4 , 5 , 2 )$ ，目标函数值为$\mathrm { H L H } ( f ) = 3 . 7 3 0 9$ ，其中期望收益 $E ( w _ { T } ) = 1 1 . 5 8$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 2 3 2$ 。

通过模糊参数化的方法[10]，仅仅对收益进行衡量，即选取二手车在不同次序最大的收益(均值)，则从表3知晓其顺序策略为M(5.4.3.2.3.1,4,2.5.5)，收益为11.92，但对应的风险高达0.2876，超过了拍卖商承受风险的上限， $b = 0 . 2$ 。该方法仅仅追求收益最大化，忽略了收益背后的风险。

通过遗传算法求出的最优拍卖顺序策略为$\mathrm { O } ( 1 , 5 , 3 , 3 , 1 , 4 , 1 , 1 , 1 , 2 )$ ，目标函数值为 $\operatorname { O } ( f ) = 5 . 0 5 7 8$ 。其中期望收益 $E ( w _ { T } ) = 1 1 . 0 5$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 1 5 5 6$ 。其求解过程的适应度函数的迭代过程如图1所示。

![](images/caeaeedaacbe29ef1b554b4299e969e3ddb352f98eca2c31e3780d3d9e9b170c.jpg)  
图1最优适应度函数收敛曲线  
Fig.1Convergence curve of optimal fitness function

# 4.2 梯形模糊数算例

10辆不同的二手车在不同次序拍卖中会产生不同模糊变量，其梯形模糊数如表4所示。

表4模糊变量的梯形模糊数（单位：十万）

Table 3Mean (unit one hundred thousand) and variance of fuzzy variables   
Table 4Trapezoidal fuzzy numbers of fuzzy variables (unit: one hundred   

<html><body><table><tr><td colspan="5">thousand)</td></tr><tr><td>二手车</td><td>次序1 次序2</td><td>次序3</td><td>次序4</td><td>次序5</td></tr><tr><td>1</td><td>(0.90 0.92 1.101.12)(0.80 0.90 1.021.12)(0.851.001.15 1.30)(0.800.95 1.091.24)(0.82 0.96 1.111.25)</td><td></td><td></td><td></td></tr><tr><td>2</td><td>(0.80 0.95 1.09 1.30)(0.82 0.96 1.10 1.24)(0.88 1.00 1.12 1.24)(0.90 1.00 1.201.30)(0.91 1.051.18 1.32)</td><td></td><td></td><td></td></tr><tr><td>3</td><td>(0.60 0.871.141.41)(0.68 0.95 1.231.5)(0.80 1.071.331.60)(0.76 1.011.231.50)(0.70 0.971.23 1.50)</td><td></td><td></td><td></td></tr><tr><td>4</td><td>(0.80 1.00 1.201.40)(0.701.031.371.70)(0.760.911.051.20)(0.700.90 1.10 1.30)(0.72 0.95 1.171.40)</td><td></td><td></td><td></td></tr><tr><td>5</td><td>(0.95 1.25 0.851.15)(0.901.001.10 1.20)(0.900.94 1.26 1.30)(0.90 1.00 1.20 1.30)(0.88 0.96 1.20 1.28)</td><td></td><td></td><td></td></tr><tr><td>6</td><td></td><td>(0.90 1.00 1.10 1.20)(0.921.011.111.20)(0.900.99 1.09 1.18)(0.92 1.011.11 1.20)(1.00 1.081.171.25)</td><td></td><td></td></tr><tr><td>7</td><td></td><td>(0.88 1.03 1.19 1.34)(0.80 1.00 1.20 1.40)(0.72 1.02 1.32 1.62)(0.78 1.06 1.34 1.62)(0.80 0.971.13 1.30)</td><td></td><td></td></tr><tr><td>8</td><td></td><td>(0.96 1.04 1.12 1.20)(0.94 1.031.13 1.22)(0.94 1.02 1.10 1.18)(0.90 0.98 1.071.15)(0.92 1.00 1.08 1.16)</td><td></td><td></td></tr><tr><td>9</td><td></td><td>(0.55 0.80 1.051.30)(0.400.74 1.08 1.42)(0.55 0.90 1.251.60)(0.500.86 1.221.58)(0.60 0.951.30 1.65)</td><td></td><td></td></tr><tr><td>10</td><td></td><td></td><td></td><td>(0.650.751.301.70)(0.700.971.231.50)(0.700.971.231.50)(0.720.971.271.48)(0.70 1.001.301.60)</td></tr></table></body></html>

根据模糊仿真算法，对表4中的模糊数进行均值 $\boldsymbol { e } _ { i t }$ 和方差$\nu _ { i t }$ 的求解（表5）.

表5模糊变量的均值(单位:十万)和方差   
Table 4Mean (unit one hundred thousand) and variance of fuzzy variables   

<html><body><table><tr><td rowspan="2">二手车</td><td colspan="5">均值eu/方差Vit</td></tr><tr><td>次序1</td><td>次序2</td><td>次序3</td><td>次序4</td><td>次序5</td></tr><tr><td>1</td><td></td><td></td><td>1.01/0.0050 0.96/0.0065 1.075/0.0122 1.02/0.0117 1.035/0.0111</td><td></td><td></td></tr><tr><td>2</td><td></td><td></td><td>1.05/0.0150 1.03/0.0106 1.06/0.0078</td><td>1.1/0.0117</td><td>1.115/0.0101</td></tr><tr><td>3</td><td></td><td>1.005/0.03951.09/0.0405 1.2/0.0385</td><td></td><td>1.13/0.0330</td><td>1.1/0.0385</td></tr><tr><td>4</td><td></td><td></td><td>1.11/0.0217 1.2/0.0602 0.98/0.0117</td><td>1/0.0217</td><td>1.06/0.0278</td></tr><tr><td>5</td><td></td><td>1.05/0.0050 1.05/0.0054 1.1/0.0163</td><td></td><td>1.1/0.0117</td><td>1.08/0.0131</td></tr><tr><td>6</td><td></td><td></td><td>1.05/0.0054 1.06/0.0047 1.04/0.0047</td><td></td><td>1.06/0.0047 1.125/0.0038</td></tr><tr><td>7</td><td></td><td></td><td>1.11/0.0127 1.1/0.0217 1.11/0.0488</td><td></td><td>1.2/0.0425 1.05/0.0150</td></tr><tr><td>8</td><td></td><td></td><td>1.08/0.0035 1.08/0.0047 1.06/0.0035 1.025/0.0038 1.04/0.0035</td><td></td><td></td></tr><tr><td>9</td><td></td><td></td><td>0.925/0.03390.91/0.06261.075/0.0664 1.04/0.07021.125/0.0664</td><td></td><td></td></tr><tr><td>10</td><td>1.175/0.1132 1.1/0.0385</td><td></td><td>1.1/0.0385</td><td>1.1/0.0409</td><td>1.15/0.0488</td></tr></table></body></html>

策略 $\mathrm { \Delta H L }$ 目标函数值 $\mathrm { H L } ( f ) = 4 . 2 2 6 9$ ，其中期望收益$E ( w _ { T } ) = 1 0 . 8 5 5$ （十万)，期望风险（方差） $V ( w _ { T } ) = 0 . 2 5 6$ 。

策略LH目标函数值 $\operatorname { L H } ( f ) = 2 . 9 3 5 5$ ，其中期望收益$E ( w _ { T } ) = 1 0 . 5 5 5$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 1 0 1$ 。

策略 $\scriptstyle { \mathrm { L H L } }$ 目标函数值 $\operatorname { L H L } ( f ) = 4 . 0 3 3 9$ ，其中期望收益$E ( w _ { T } ) = 1 0 . 6 9 5$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 4 7 1$ 。

策略 $\mathrm { \Pi _ { H L H } }$ 目标函数值 $\mathrm { H L H } ( f ) = 4 . 3 5 3 7$ ，其中期望收益$E ( w _ { T } ) = 1 1 . 1$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 2 5 9 5$ 。

根据模糊参数化的方法[10]，可以从表5知晓其顺序策略为M(5,5,3,2.3.5,4,1,2,1)，收益为11.355，但对应的风险高达0.3655，远远超过了拍卖商承受风险的上限， $b = 0 . 2$ 。通过遗传算法求出的最优拍卖顺序策略为 $\operatorname { O } ( 1 , 3 , 4 , 3 , 1 , 5 , 1 , 1 , 1 , 2 )$ ，目标函数值为 $\scriptstyle \mathbf { O } ( f ) = 4 . 8 9 9 5$ 。其中期望收益 $E ( w _ { T } ) = 1 0 . 6 9$ (十万)，期望风险 $V ( w _ { T } ) = 0 . 1 6 4 8$ 。其求解过程的适应度函数的迭代过程如图2所示。

![](images/dd0e1c806b6366038e021d23d79133a761edd018015f2e45104108a1d249a494.jpg)  
图2最优适应度函数收敛曲线  
Fig.2Convergence curve of optimal fitness function

# 4.3 总结

通过比较四种常见的拍卖顺序策略、文献[10]中的策略以及最优顺序策略可以发现，只有最优策略的风险控制在接受范围内，其他都超出承受上限 $b = 0 . 2$ □

观察两个算例发现，不管模糊变量使用三角模糊数还是梯形模糊数进行刻画，都将通过模糊模拟算法得到策略对应的收益（均值）和风险（方差)。然后通过本文的多准则0-1遗传算法求解的策略，相比其他策略，一定是在满足风险要求下的较高收益，即拍卖商追求的最优策略。而且最优策略的收益与五种策略收益的差值都保持在1（十万）以内。说明本文求解的最优策略能够有效地保证低风险下的较高收益。

综上所述，采用模糊理论描述不确定性，可以更好地评估收益不确定性和风险不确定性，为拍卖商制定策略提供更多支持。

# 5 结束语

本文提出收益和风险的多准则优化模型，为拍卖商提供了更好的拍卖顺序策略，保证了更低风险的收益，比以往单纯考虑收益的方法更加实际有效。主要结论如下：

a）本文考虑收益不确定性和风险不确定性，采用多准则优化，提出了基于柯布一道格拉斯生产函数的目标优化函数。b)本文采用模糊理论对序贯拍卖中顺序策略产生的不确定性用模糊变量进行刻画，进而提出则模糊随机不确定性序贯拍卖策略模型（F-SAmodel)。c）本文集成模糊模拟算法和多准则0-1遗传算法，提出基于模糊模拟的多准则遗传算法（F-MCGAalgorithm)，以求解文中提出的优化模型。d）算例分析的结果显示，采用F-SAmodel得到的优化策略能够以较低的风险获得较高的收益，能够满足拍卖商的多准则要求，因此具有实际意义。

综上所述，本文提出的模型和算法为序贯拍卖中顺序策略提供了新的理论视角，并为拍卖商制定顺序策略提供了决策支持。

# 参考文献：

[1]Centre for Automotive Management. China used car market report [EB/OL]. (2015）[2018-05-10]. https://www. giiresearch.com/report/rinc339575- china-used-car-market-report. html.   
[2]Salladarreé F, Guilltreau P,Loisel P,et al. The declining price anomaly in sequential auctions of identical commodities with asymmetric bidders: empirical evidence from the Nephrops norvegicus market in France [J]. Agricultural Economics,2017,48(6): 731-741.   
[3]胡二琴，赵勇，陈莹．序贯拍卖中报价排序信息披露的研究[J]．系统 工程学报,2016,31(3):317-327.(Hu Erqin, Zhao Yong,Chen Ying.Study of bids’ordinal ranks information disclosure in sequential auctions [J]. Journal of Systems Engineering,2016,31(3): 317-327.)   
[4]Elmaghraby W.Auctions within E-sourcing events [J].Production & Operations Management,2007,16 (4): 409-422.   
[5]Grether D M,Plott C R.Sequencing strategies in large,competitive, ascending price automobile auctions: an experimental examination [J]. Journal ofEconomic Behavior& Organization,20o9,71(2):75-88.   
[6]Raviv Y. New evidence on price anomalies in sequential Auctions [J]. Journal of Business & Economic Statistics,2006,24(3):301-312.   
[7]Ozturk O C,Karabati S.A decision support framework for evaluating revenue performance in sequential purchase contexts [J].European Journal of Operational Research,2017,263:922-934.   
[8]ChakrabortyA,Gupta N,Harbaugh R.Best foot forward or best for last in a sequential auction?[J].RAND Journal of Economics,2006,37(1):176- 194.   
[9]Elmaghraby W. The importance of ordering in sequential auctions [J] Management Science,2011,49 (49): 673-682.   
[10]黄海新，汪定伟．基于模糊博弈的英式拍卖动态模型[J].信息与控制, 2012,41 (4): 509-513.(Huang Haixin,Wang Dingwei.English auction dynamic model based on fuzzy game [J]. Information and Control,2012, 41 (4): 509-513.)   
[11]谢安石，李一军．基于模糊粗糙集的多属性网上拍卖决策[J].系统管 理学报，2005,14(2):182-184.(Xie Anshi,Li Yijun.Multi-atribute decision making based on fuzzy rough set in E-auction [J]. Journal of Systems and Management,2005,14(2): 182-184.)   
[12]秦全德，王晓晖，李荣钧．不完全偏好信息下国有企业并购多属性拍卖 的模糊决策[J]．管理工程学报，2012,26(4):169-175.(Qin Quande, Wang Xiaohui,Li Rongjun.Fuzzy multi-atribute auction model used for merger and acquisition decisions of state-owned enterprises under incomplete preference information [J].Journal of Industrial Engineering & Engineering Management,2012,26 (4): 169-175.)   
[13] Guo Sini,Yu Lean,Li Xiang,et al.Fuzzy multi-period portfolio selection with different investment horizons [J].European Journal of Operational Research,2016,254(3):1026-1035.   
[14]栗然，韩彪，卢云，等．基于随机模糊理论的变压器经济寿命评估 [J]. 电力系统保护与控制,2014(1):9-16.(LiRan,Han Biao.Transformer’s economic life assessment based on random and fuzzy theory [J].Power System Protection and Control,2014 (1): 9-16.)   
[15]刘树林，王明喜．拍卖基本理论与扩展[M]．北京：科学出版社,2010. (Liu Shulin,Wang Mingxi.Basic theory and extension of auction [M]. Beijing: Science Press,2010.)   
[16] Liu Xiang,Liu Baoding.A sufficient and necessary condition for credibility measures [J]． International Journal of Uncertainty，Fuzzinessand Knowledge-Based Systems,2006,14(5): 527-535.   
[17]刘宝锭，彭锦．不确定理论教程[M].北京：清华大学出版社，2005. (Liu Baoding,Peng Jin. Uncertain theory course [M].Beijing: Tsinghua University Press,2005.)   
[18] Liu Baoding,Iwamura K. Chance constrained programming with fuzzy parameters [J].Fuzzy Sets& Systems,1998,94(2): 227-23.