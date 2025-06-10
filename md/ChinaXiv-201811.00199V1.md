# 毕达哥拉斯模糊Heronian算子的多属性决策方法

彭定洪，杨扬

(昆明理工大学质量发展研究院，昆明 650093)

摘要：针对毕达哥拉斯模糊环境下的多属性决策问题中的信息集成问题，其中方案的属性间相互关联相互影响，提出了一种毕达哥拉斯模糊 Heronian算子的多属性决策方法。首先将毕达哥拉斯模糊数与Heronian算子相结合，提出了毕达哥拉斯模糊 Heronian算子和毕达哥拉斯模糊加权Heronian算子，并讨论了这些算子的性质，给出了相应的证明。在此基础上，提出了基于毕达哥拉斯模糊Heronian 算子的多属性决策方法。最后将其应用国内四家航空公司服务质量评价中，说明了该算子的有效性和可行性。

关键词：毕达哥拉斯模糊数；Heronian 算子；毕达哥拉斯模糊Heronian 算子；多属性决策中图分类号：TP39 doi: 10.19734/j.issn.1001-3695.2018.06.0484

# Multi-attribute decision making method for Pythagorean fuzzy Heronian operators

Peng Dinghong, Yang Yang (InstituteofQualityDevelopment,Kunming UniversityofScience&Technology,Kunming 65o093,China)

Abstract: Aimingat theinformation integrationproblemin the multi-atribute decision making problemofPythagorean fuzzy environment,theatributesof the schemearerelated toeach other,anda multi-atribute decision-making method based on Pythagorean fuzzy Heronian operator isproposed.Combining Pythagoreanfuzzy numberswith Heronianoperators, Pythagorean fuzzy Heronian operators andPythagorean fuzzy weighted Heronian operators are proposed.The propertiesof these operators are discussed.Corresponding proof.On this basis，amulti-atribute decision making method based on Pythagorean fuzzyHeronianoperatorisproposed.Finall,itisapplidtotheservicequalityvaluationoffourdomesticirlies, and the effectiveness and feasibility of the operator are illustrated.

Key words: Pythagorean fuzzy numbers; Heronian operators; Pythagorean fuzzy Heronianaggregationoperators; multiple criteria decision making

# 0 引言

Zadeh[提出的模糊集理论是描述事物的不确定性和模糊性的有力工具。为了更好地理解客观世界的不确定性并因此能够解释它，该理论的一些扩展形式已经被提出，如区间犹豫模糊集（IVHFS）、2-型模糊集（T2FS）、模糊多集（FMS）、直觉模糊集（IFS）等。其中直觉模糊集理论由Atanassov[2]于1986年提出，是对经典 Zadeh 模糊集理论最为重要的拓展之一，其理论与应用的研究在模糊集理论领域取得了广泛的研究成果并产生了深远的影响。直觉模糊集用隶属度和非隶属度来表示对同一概念的肯定程度和否定程度，从而能够更加全面和细致地刻画现实中模糊和抽象的概念。但是在直觉模糊决策过程中，可能出现如下情况：决策者给出的方案满足属性的隶属度和非隶属度之和大于1。基于此，Yager[4对直觉模糊集进行拓展，提出了毕达哥拉斯模糊集，满足隶属度和非隶属度之和大于1，但平方和不超过1。因此使得决策者不用修改其隶属度和非隶属度的值，能够更加准确和细致地刻画现实情况。

自从毕达哥拉斯模糊集问世以来，也取得了丰硕的研究成果。例如，Zhang[1]提出了一种层次QUALIFLEX 方法的毕达哥拉斯模糊决策模型；Peng等人[1]研究了区间值毕达哥拉斯模糊集及其决策应用;Ren等人[12]提出了毕达哥拉斯模糊TODIM方法，并将其应用于多属性决策中；Guo等人[3]建立了毕达哥拉斯模糊函数，并详细研究了其性质，包括连续性、可导性和可微性；Yager[4提出了毕达哥拉斯集成算子，包括毕达哥拉斯模糊信息集成的加权平均(PFWA）算子和有序加权几何算子(PFOWG)及其性质；刘卫锋等人[14]研究毕达哥拉斯模糊决策环境下的集成算子及其决策应用，给出了拟加权几何集成算子和拟有序加权几何算子的概念，并分析它们的性质。Zhang 等人[5]定义了毕达哥拉斯模糊数的运算及距离，并提出了基于毕达哥拉斯模糊集的 TOPSIS 法及其决策应用；丁恒等人[15]研究了毕达哥拉斯模糊环境下的多属性群决策问题，提出毕达哥拉斯模糊幂加权平均(PFPWA)算子，并研究所提算子的基本性质。

上述研究的毕达哥拉斯模糊集结算子和毕达哥拉斯模糊决策方法均假定属性间相互独立。实际决策中，不同属 性之间会存在不同程度的联系，如互补、冗余、偏好关系等等。因此研究属性间相互关联关系的多属性决策问题具有非常重要的理论意义。在多属性决策问题中，集成算子是众多决策方法的基础，因此在毕达哥拉斯模糊环境下，集成算子的研究也显得尤为重要。到目前为止，大多数的多属性决策问题的研究仅仅建立在属性相互独立的情况下，然而在现实情况中，由于现实情况相对复杂，属性之间往往并不是相互独立，而是或多或少存在着相互关联关系，一方面，可以根据决策者的经验和知识来主动识别属性间的相互关系，如产品的售价和产品的成本，通常产品成本越高其售价也会越高；另一方面，属性间还可能存在无法直接识别的相互关系，那么可以根据决策者所提供的评价值去识别这些隐藏的关系。在本文的航空公司服务质量评价的中，订票和售票程序可能和登记程序相互影响，客舱服务和响应性也可能相互影响。为了处理这类相互影响的多属性决策问题，考虑到 Heronian 平均（Heronian means）算子是一种处理属性间相关联的集结算子[7-9]，并且基于HM 算子的研究也得到了迅速的发展。例如，Liu[6]基于幂均算子和 Heronian 算子的优点，将其两者相结合，拓展到区间直觉模糊的环境下，提出了区间直觉模糊Heronian（IVIFPHA）集结算子，并建立了基于此算子的多属性决策模型。Liu 等人[17]等针对多属性群决策问题，属性权重和专家权重采用精确数的形式，属性评价值采用直觉语言变量形式，结合Heronian 算子，提出了一种新的直觉不确定语言加权算术Heronian平均（IULWAHM）算子、直觉不确定语言几何Heronian平均（IULGHM）算子和直觉不确定语言加权几何Heronian平均（IULWGHM）算子，并运用于多属性群决策问题。 $\mathrm { Y u } ^ { [ 1 8 ] }$ 研究了直觉模糊环境下的属性间有相关性假设下的多准则决策问题，提出了直觉模糊信息的一种新的集成算子，包括直觉模糊几何Heronian 平均（IFGHM）算子和直觉模糊几何加权Heronian平均（IFGWHM）算子。

综上所述，现在关于属性间具有相关性的毕达哥拉斯模糊集集成算子研究还处于探索阶段，且关于毕达哥拉斯模糊环境下的集成算子存在以下不足：a)未能考虑到属性间可能存在相关联相互影响的情况，现有的集成算子无法处理此种情况；b)现有集成算子大多不涉及参数的选择问题，不能灵活地反映决策者的自身偏好态度。基于此，本文分别将毕达哥拉斯模糊集与Heronian 算子相结合，提出了毕达哥拉斯模糊Heronian算子和毕达哥拉斯模糊加权Heronian 算子。其中Heronian 算子含有参数p、q，决策者可以根据自身偏好灵活地选择其参数。因为更具有动态性和主观性，并进一步提出了基于毕达哥拉斯模糊Heronian算子的多属性决策方法。

# 1 预备知识

在本章中简要介绍直觉模糊集、毕达哥拉斯模糊集和Heronian 算子的基本概念。其中毕达哥拉斯模糊集是直觉模糊集的推广形式，能更加细致地刻画现实情况，Heronian算子是一种处理属性相关联的集结算子。

定义 $\mathbf { 1 } ^ { [ 2 ] }$ 设 $X$ 为论域, $A = \left\{ \left. x , \mu _ { A } \left( x \right) , \nu _ { A } \left( x \right) \right. \middle | x \in X \right\}$ 称为 $X$ 上的一个直觉模糊集，其中 $\mu _ { \scriptscriptstyle A } : X \to [ 0 , 1 ]$ ， $\nu _ { _ { A } } : X  [ 0 , 1 ]$ 为 $X$ 上的模糊集， $\mu _ { _ A } ( x )$ 和 $\nu _ { _ { A } } ( x )$ 分别表示 $X$ 上元素 $\boldsymbol { \mathfrak { X } }$ 属于 $A$ 的隶属度和非隶属度，且 $\forall x \in X$ ， $\mu _ { _ A } ( x )$ 、 $\nu _ { \scriptscriptstyle A } \left( x \right) \in \left[ 0 , 1 \right]$ ，有 $\mu _ { _ A } \left( x \right) + \nu _ { _ A } \left( x \right) \leq 1$ 。

定义 $2 ^ { [ 3 , 4 ] }$ 设 $X$ 为论域， $A = \left\{ \left. x , \mu _ { _ A } \left( x \right) , \nu _ { _ A } \left( x \right) \right. \middle | x \in X \right\}$ 称为 $X$ 上的一个毕达哥拉斯模糊集，其中 $\mu _ { _ A } : X  [ 0 , 1 ]$ ， $\nu _ { _ { A } } : X  [ 0 , 1 ]$ 为$X$ 上的模糊集， $\mu _ { _ A } ( x )$ 和 $\nu _ { _ { A } } ( x )$ 分别表示 $X$ 上元素x属于 $A$ 的隶属度和非隶属度，且 $\forall x \in X$ ， $\mu _ { _ A } ( x )$ ， $\nu _ { \scriptscriptstyle A } \left( x \right) \in \left[ 0 , 1 \right]$ 有 $\mu _ { A } ^ { 2 } \left( x \right) + \nu _ { A } ^ { 2 } \left( x \right) \leq 1$ 。称 $\pi _ { A } \left( X \right) = \sqrt { 1 - \mu _ { A } ^ { 2 } \left( x \right) - \nu _ { A } ^ { 2 } \left( x \right) }$ 为 $\boldsymbol { \mathfrak { X } }$ 属于 $A$ 的犹豫度。称 $\alpha = \left. \mu _ { \alpha } , \nu _ { \alpha } \right.$ 为毕达哥拉斯模糊数[5]，全体毕达哥拉斯模糊数的集合记为PHN。

定义 $\mathbf { 3 } ^ { [ 5 ] }$ 设 $\alpha = \langle \mu _ { \alpha } , \nu _ { \alpha } \rangle , \alpha _ { i } = \left. \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \right. \left( i = 1 , 2 , . . . , n \right)$ 为毕达哥拉斯模糊数，定义：

$$
\alpha _ { 1 } \oplus \alpha _ { 2 } = \left. \sqrt { \mu _ { \alpha _ { 1 } } ^ { 2 } + \mu _ { \alpha _ { 2 } } ^ { 2 } - \mu _ { \alpha _ { 1 } } ^ { 2 } \mu _ { \alpha _ { 2 } } ^ { 2 } } , \nu _ { \alpha _ { 1 } } \nu _ { \alpha _ { 2 } } \right.
$$

$$
\alpha _ { 1 } \otimes \alpha _ { 2 } = \left. \mu _ { \alpha _ { 1 } } \mu _ { \alpha _ { 2 } } , \sqrt { \nu _ { \alpha _ { 1 } } ^ { 2 } + \nu _ { \alpha _ { 2 } } ^ { 2 } - \nu _ { \alpha _ { 1 } } ^ { 2 } \nu _ { \alpha _ { 2 } } ^ { 2 } } \right.
$$

$$
\lambda \alpha = \left. \sqrt { 1 - \left( 1 - \mu _ { \alpha } ^ { 2 } \right) ^ { \lambda } } , \nu _ { \alpha } ^ { \lambda } \right. , \lambda < 0
$$

$$
\alpha ^ { \lambda } = \Biggl \langle \mu _ { \alpha } ^ { \lambda } , \sqrt { 1 - \bigl ( 1 - \nu _ { \alpha } ^ { 2 } \bigr ) ^ { \lambda } } \Biggr \rangle , \lambda < 0 \Biggr )
$$

为了对毕达哥拉斯数进行排序，下面给出毕达哥拉斯模糊数的得分函数和精确函数及其毕达哥拉斯模糊数的排序方法。

定义 $\mathbf { 4 } ^ { [ 5 ] }$ 设 $\alpha = \left. \mu _ { \alpha } , \nu _ { \alpha } \right.$ 为毕达哥拉斯模糊数，其得分函数为 $S \left( \alpha \right) = \mu _ { \alpha } ^ { 2 } - \nu _ { \alpha } ^ { 2 }$ ，且 $S ( \alpha ) \in \left[ - 1 , 1 \right]$ 。

定义 $\pmb { 5 } ^ { [ 6 ] }$ 设 $\alpha = \left. \mu _ { \alpha } , \nu _ { \alpha } \right.$ 为毕达哥拉斯模糊数，其精确函数为 $h ( \alpha ) = \mu _ { \alpha } ^ { 2 } + \nu _ { \alpha } ^ { 2 }$ ，且 $h \left( \alpha \right) \in \left[ - 1 , 1 \right]$ 。

定义 ${ \bf 6 ^ { [ 6 ] } }$ 设 $\alpha _ { i } = \langle \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \rangle ( i = 1 , 2 )$ 为毕达哥拉斯模糊数则:

a)若 $S \left( \alpha _ { 1 } \right) > S \left( \alpha _ { 2 } \right)$ ，则 $\alpha _ { 1 } > \alpha _ { 2 }$ 。

b)若 $S \left( \alpha _ { _ 1 } \right) = S \left( \alpha _ { _ 2 } \right)$ ，(a)若 $h \big ( \alpha _ { 1 } \big ) > h \big ( \alpha _ { 2 } \big )$ ，则 $\alpha _ { 1 } > \alpha _ { 2 }$ ；(b)若 $h \big ( \boldsymbol { \alpha } _ { 1 } \big ) = h \big ( \boldsymbol { \alpha } _ { 2 } \big )$ ，则 $\alpha _ { 1 } \sim \alpha _ { 2 }$ 。

定义 $7 ^ { [ 7 - 9 ] }$ 设 $p > 0$ ， $q > 0$ ，且 $p$ 与 $q$ 不同时为 $\mathbf { \boldsymbol { 0 } }$ ，$a _ { i } \left( i = 1 , 2 , . . . , n \right)$ 为非负实数，若：

$$
H M ^ { p , q } \left( a _ { 1 } , a _ { 2 } , . . . , a _ { n } \right) = \left( \frac { 2 } { n ( n + 1 ) } \sum _ { i = 1 , j = 1 } ^ { n } a _ { i } ^ { p } a _ { j } ^ { q } \right) ^ { \frac { 1 } { p + q } }
$$

则称HM为Heronian 平均算子。

# 2 毕达哥拉斯模糊Heronian 算子

在本章中给出了毕达哥拉斯模糊Heronian算子的定义及其性质，并进一步提出了毕达哥拉斯模糊加权Heronian算子的定

义。

定义8设 $p$ 与 $\boldsymbol { q }$ 不同时为0的非负实数，且 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle$ ，${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ 为毕达哥拉斯模糊数，则毕达哥拉斯模糊Heronian(PFHM)算子定义如下：

$$
\begin{array} { l } { { \displaystyle P F H M ^ { p , q } \left( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } \right) } } \\ { { \displaystyle = \left( \frac { 2 } { n ( n + 1 ) } \bigoplus _ { i = 1 , j = 1 } ^ { n } \left( \left( \alpha _ { i } \right) ^ { p } \otimes \left( \alpha _ { j } \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } } \end{array}
$$

定理1设 $p$ 与 $\boldsymbol { q }$ 不同时为0的非负实数，且 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle$ ，${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ 为毕达哥拉斯模糊数，经过PFHM算子集成的结果仍然是毕达哥拉斯模糊数，且

$$
\begin{array} { r l } & { P F H M ^ { p , q } \left( \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n } \right) } \\ & { = \left( \sqrt { 1 - \left( \displaystyle \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( \mu _ { i } \right) ^ { p } \left( \mu _ { j } \right) ^ { q } \right) \right) ^ { \frac { 2 } { p + n + 1 } } } \right) ^ { \frac { 1 } { p + q } } , } \\ & { = \left( \sqrt { 1 - \left( 1 - \left( \displaystyle \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } \right) \right) ^ { \frac { 2 } { p + n + 1 } } \right) ^ { \frac { 1 } { p + q } } } \right) } \end{array}
$$

证明 由式（4）可得

$$
\begin{array} { c } { { ( \alpha _ { i } ) ^ { p } = \left. \left( \mu _ { i } \right) ^ { p } , \sqrt { 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } } \right. } } \\ { { { } } } \\ { { \left( \alpha _ { j } \right) ^ { q } = \left. \left( \mu _ { j } \right) ^ { q } , \sqrt { 1 - \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } } \right. } } \end{array}
$$

从而由式（2）有

$$
\left( \alpha _ { i } \right) ^ { p } \otimes \left( \alpha _ { j } \right) ^ { q } = \left. \left( \mu _ { i } \right) ^ { p } \left( \mu _ { j } \right) ^ { q } , \sqrt { 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } } \right.
$$

由此可得

$$
\begin{array} { r l } & { \underset { i = 1 , j = 1 } { \overset { n } { \bigoplus } } \left( \left( \alpha _ { i } \right) ^ { p } \otimes \left( \alpha _ { j } \right) ^ { q } \right) } \\ & { = \left. \sqrt { 1 - \underset { i = 1 , j = 1 } { \overset { n } { \prod } } \left( 1 - \left( \left( \mu _ { i } \right) ^ { p } \left( \mu _ { j } \right) ^ { q } \right) ^ { 2 } \right) } , \right. } \\ & { \underset { i = 1 , j = 1 } { \overset { n } { \prod } } \sqrt { 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } } } \end{array}
$$

因此：

$$
\begin{array} { r l } & { P H P H ^ { ( 1 ) } \left( \varepsilon , \eta , \varepsilon , \eta , \varepsilon , \eta , \varepsilon , \eta \right) } \\ & { = \left( \frac { 2 } { \pi \left( \varepsilon + 1 \right) \varepsilon } \frac { \tilde { \eta } _ { \varepsilon } ^ { \varepsilon } \left( \left[ \tilde { \eta } _ { \varepsilon } \left( \varepsilon , \eta \right) \right] ^ { 2 } \left( \varepsilon , \eta ^ { \prime } \right) \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } { \varepsilon } \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } \\ & { = \left( \frac { \tilde { \eta } _ { \varepsilon } ^ { \varepsilon } \left( \varepsilon \right) \left( \varepsilon - \left( \varepsilon + \eta ^ { \prime } \left( \varepsilon , \eta ^ { \prime } \right) \right) \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } { \varepsilon } \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } \\ & { = \left( \frac { \tilde { \eta } _ { \varepsilon } ^ { \varepsilon } \left( \varepsilon \right) \left( \varepsilon - \left( \varepsilon + \eta ^ { \prime } \left( \varepsilon , \eta ^ { \prime } \right) \right) \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } { \varepsilon } \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } \\ & { \quad \times \left( \frac { \tilde { \eta } _ { \varepsilon } ^ { \varepsilon } \left( \varepsilon \right) \left( \varepsilon - \left( \varepsilon + \eta ^ { \prime } \left( \varepsilon + \eta ^ { \prime } \right) \right) \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } { \varepsilon } \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } \\ & { = \left( \sqrt { \frac { \tilde { \eta } _ { \varepsilon } ^ { \varepsilon } \left( \varepsilon - \left( \varepsilon \right) \left( \varepsilon - \eta ^ { \prime } \left( \varepsilon - \eta ^ { \prime } \right) \right) \right) ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } { \varepsilon }  ^ { \frac { 1 } { 2 \eta ^ { 2 } } } } } \end{\right)array} \end{array}
$$

由 $0 \leq \mu _ { i } \leq 1$ ， $0 \leq \nu _ { i } \leq 1$ ， $0 \leq \mu _ { i } ^ { 2 } + \nu _ { i } ^ { 2 } \leq 1$ ， ${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ ，知：

$$
0 \leq \left( \sqrt { 1 - \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( \mu _ { i } \right) ^ { p } \left( \mu _ { j } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n \left( n + 1 \right) } } } \right) ^ { \frac { 1 } { p + q } } \leq 1 ,
$$

和

$$
0 \leq \sqrt { 1 - \left( 1 - \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n \left( n + 1 \right) } } \right) ^ { \frac { 1 } { p + q } } } \leq 1
$$

以及

$$
\begin{array} { l } { \displaystyle 0 \le \left( 1 - \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( \mu _ { i } \right) ^ { p } \left( \mu _ { j } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } \right) ^ { \frac { 1 } { p + q } } + } \\ { \displaystyle 1 - \left( 1 - \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( 1 - \nu _ { i } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { j } ^ { 2 } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } \right) ^ { \frac { 1 } { p + q } } \le 1 } \end{array}
$$

成立，因此定理1成立。

下面讨论毕达哥拉斯模糊Heronian(PFHM)算子的性质，包括其幂等性、单调性和有界性，并给出相应的证明。

性质1幂等性。设 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle \ ( i = 1 , 2 , . . . , n )$ 为一组毕达哥拉 斯模糊数，若 $\alpha _ { i } = \alpha$ ， ${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ ，则有 $P F H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) = \alpha$

证明

$$
\begin{array} { l } { { P F H M ^ { P , q } \left( \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n } \right) } } \\ { { \ } } \\ { { \displaystyle = \left( \frac { 2 } { n ( n + 1 ) } \sum _ { i = 1 , j = 1 } ^ { n } \left( \left( \alpha _ { i } \right) ^ { p } \otimes \left( \alpha _ { j } \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } } \\ { { \displaystyle = \left( \frac { 2 } { n ( n + 1 ) } \sum _ { i = 1 , j = 1 } ^ { n } \left( \left( \alpha \right) ^ { p } \otimes \left( \alpha \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } } \\ { { \displaystyle = \left( \frac { 2 } { n ( n + 1 ) } \sum _ { i = 1 , j = 1 } ^ { n } \left( \alpha \right) ^ { r + q } \right) ^ { \frac { 1 } { p + q } } = \alpha } } \end{array}
$$

性质2单调性。设 $\alpha _ { i } = \langle \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \rangle ( i = 1 , 2 , . . . , n )$ ， $\beta _ { i } = \big \langle \mu _ { _ { \beta _ { i } } } , \nu _ { _ { \beta _ { i } } } \big \rangle ( i = 1 , 2 , . . . , n )$ 为两组毕达哥拉斯模糊数，且 $\mu _ { \alpha _ { i } } \leq \mu _ { \beta _ { i } }$ ， $\nu _ { \alpha _ { i } } \geq \nu _ { \beta _ { i } }$ ，则

$$
P F H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) \leq P F H M ( \beta _ { 1 } , \beta _ { 2 } , . . . , \beta _ { n } )
$$

证明因为 $\mu _ { \alpha _ { i } } \leq \mu _ { \beta _ { i } } \ , \nu _ { \alpha _ { i } } \geq \nu _ { \beta _ { i } }$ ，且 $p$ 与 $\boldsymbol { q }$ 不同时为0的非负实数，由函数单调性和毕达哥拉斯模糊数运算法则有

$$
\begin{array} { l } { \left( \sqrt { 1 - \displaystyle \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( \mu _ { \alpha _ { i } } \right) ^ { p } \left( \mu _ { \alpha _ { j } } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } } \right) ^ { \frac { 1 } { p + q } } } \\ { \leq \left( \sqrt { 1 - \displaystyle \left( \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( \mu _ { \beta _ { i } } \right) ^ { p } \left( \mu _ { \beta _ { i } } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } } \right) ^ { \frac { 1 } { p + q } } } \end{array}
$$

$$
\begin{array} { r l } & { \sqrt { 1 - \left( 1 - \left( \displaystyle \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( 1 - \nu _ { \alpha _ { i } } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { \alpha _ { j } } ^ { 2 } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } \right) ^ { \frac { 1 } { p + q } } } \ge } \\ & { \sqrt { 1 - \left( 1 - \left( \displaystyle \prod _ { i = 1 , j = 1 } ^ { n } \left( 1 - \left( 1 - \nu _ { \beta _ { i } } ^ { 2 } \right) ^ { p } \left( 1 - \nu _ { \beta _ { j } } ^ { 2 } \right) ^ { q } \right) \right) ^ { \frac { 2 } { n ( n + 1 ) } } \right) ^ { \frac { 1 } { p + q } } } } \end{array}
$$

故 $P F H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) \leq P F H M ( \beta _ { 1 } , \beta _ { 2 } , . . . , \beta _ { n } )$ 0

性质3有界性。设 $\alpha _ { i } = \left. \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \right. , ( i = 1 , 2 , . . . , n )$ 为一组毕达哥

拉斯模糊数， $\alpha _ { \mathrm { m i n } } = \operatorname* { m i n } _ { i } \{ \alpha \}$ ， $\alpha _ { \mathrm { { m a x } } } = \operatorname* { m a x } _ { i } \{ \alpha \}$ ，则

$$
\alpha _ { \mathrm { m i n } } \leq P F H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) \leq \alpha _ { \mathrm { m a x } }
$$

证明

$$
\begin{array} { r l } & { P F H M ^ { p q } \left( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } \right) } \\ & { = \left( \frac { 2 } { n ( n + 1 ) \underbrace { \tilde { \bigoplus } } _ { i = 1 , j = 1 } } \left( \left( \alpha _ { i } \right) ^ { p } \otimes \left( \alpha _ { j } \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } \\ & { \leq \left( \frac { 2 } { n ( n + 1 ) \underbrace { \tilde { \bigoplus } } _ { i = 1 , j = 1 } } \left( \left( \alpha _ { \mathrm { a n c } } \right) ^ { p } \otimes \left( \alpha _ { \mathrm { a n c } } \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } \\ & { \leq \left( \frac { 2 } { n ( n + 1 ) \underbrace { \tilde { \bigoplus } } _ { i = 1 , j = 1 } } \left( \left( \alpha _ { \mathrm { a n c } } \right) ^ { p + q } \right) \right) ^ { \frac { 1 } { p + q } } } \\ & { = \alpha _ { \mathrm { m a x } } } \end{array}
$$

同理可知 $\alpha _ { \mathrm { m i n } } \leq P F H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } )$ ，故得证。

定义9设 $p$ 与 $q$ 不同时为0的非负实数，且 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle$ ，${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ 为毕达哥拉斯模糊数， $\boldsymbol { \omega } = \left( \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { n } \right) ^ { T }$ 为权重向量,$\omega _ { i } \in \left[ 0 , 1 \right]$ ， $\sum _ { i = 1 } ^ { n } \omega _ { i } = 1$ ，则毕达哥拉斯模糊加权 Heronian(PFWHM)算子为

$$
\begin{array} { l } { \displaystyle P F W H M ^ { p , q } \left( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } \right) } \\ { \displaystyle = \left( \frac { 2 } { n ( n + 1 ) } \bigoplus _ { i = 1 , j = 1 } ^ { n } \left( \left( \omega _ { i } \alpha _ { i } \right) ^ { p } \otimes \left( \omega _ { j } \alpha _ { j } \right) ^ { q } \right) \right) ^ { \frac { 1 } { p + q } } } \end{array}
$$

定理2设 $p$ 与 $q$ 不同时为0的非负实数，且 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle$ ，${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ 为毕达哥拉斯模糊数， $\boldsymbol { \omega } = \left( \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { n } \right) ^ { T }$ 为权重向量,$\omega _ { i } \in \left[ 0 , 1 \right]$ ， $\sum _ { i = 1 } ^ { n } \omega _ { i } = 1$ ，经过PFWHM算子集成的结果仍然是毕达哥拉斯模糊数，且

$$
\begin{array} { r l } & { P F W H M ^ { \varepsilon \nu } ^ { \varepsilon \nu } ( \alpha _ { \nu } , \alpha _ { \nu } , \ldots , \alpha _ { \kappa } ) } \\ & { = ( \frac { 2 } { n ( n - t ) \underbrace { \frac { n } { \mathrm { d } \alpha _ { \nu } } \int _ { \alpha _ { \nu } } ( ( \omega _ { \alpha _ { \nu } } \varepsilon ) ^ { \nu } \otimes ( \omega _ { \alpha _ { \nu } } \varepsilon ) ^ { \nu } ) ^ { \frac { 1 } { \nu \mathrm { d } \alpha _ { \nu } } } } _ { \mathrm { d } \varepsilon } }  } \\ & { = ( \sqrt { 1 - ( \prod _ { i = 1 , i = 1 } ^ { N } ( 1 - ( \mu _ { \iota } ^ { \alpha } ) ^ { \nu } ( \mu _ { \iota } ^ { \alpha } ) ^ { \nu } ) ) ^ { \frac { 2 } { \mathrm { b } \alpha _ { \alpha + 1 } ^ { \alpha } } } } ) ^ { \frac { 1 } { \nu \mathrm { d } \alpha _ { \nu } } } , } \\ & { ( \sqrt { 1 - ( 1 - ( \prod _ { i = 1 , i = 1 } ^ { N } ( 1 - ( ( 1 - \nu _ { \iota } ^ { \alpha } ) ^ { \nu } ) ^ { \nu } ) ^ { \alpha } ( ( 1 - \nu _ { \iota } ^ { \alpha } ) ^ { \alpha } ) ^ { \nu } ) ^ { \frac { 2 } { \mathrm { b } \alpha _ { \alpha + 1 } ^ { \alpha } } } ) ^ { \frac { 1 } { \nu \mathrm { d } \alpha _ { \nu } } } } ) ^ { \frac { 1 } { \nu \mathrm { d } \alpha _ { \alpha } } } ) ^ { \frac { 1 } { \nu \mathrm { d } \alpha _ { \nu } } } . } \end{array}
$$

证明过程类似定理1，限于篇幅，此处从简，故略。

下面讨论毕达哥拉斯模糊加权Heronian(PFWHM)算子的性质，包括其幂等性、单调性和有界性。

性质4幂等性。设 $\alpha _ { i } = \langle \mu _ { i } , \nu _ { i } \rangle \ ( i = 1 , 2 , . . . , n )$ 为一组毕达哥拉 斯模糊数，若 $\alpha _ { i } = \alpha$ ， ${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ ，则有 $P F W H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) = \alpha$

性质5单调性。设 $\alpha _ { i } = \langle \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \rangle ( i = 1 , 2 , . . . , n )$ ， $\beta _ { i } = \big \langle \mu _ { \beta _ { i } } , \nu _ { \beta _ { i } } \big \rangle \big ( i = 1 , 2 , . . . , n \big )$ 为两组毕达哥拉斯模糊数， （204号 $\boldsymbol { \omega } = \left( \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { n } \right) ^ { T }$ 为权重向量， $\omega _ { i } \in [ 0 , 1 ] , \sum _ { i = 1 } ^ { n } \omega _ { i } = 1$ 且 $\mu _ { \alpha _ { i } } \leq \mu _ { \beta _ { i } }$ ， $\nu _ { \alpha _ { i } } \geq \nu _ { \beta _ { i } }$ ，则

$$
P F W H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) \leq P F W H M ( \beta _ { 1 } , \beta _ { 2 } , . . . , \beta _ { n } )
$$

性质6有界性。设 $\alpha _ { i } = \left. \mu _ { \alpha _ { i } } , \nu _ { \alpha _ { i } } \right.$ ， ${ \big ( } i = 1 , 2 , . . . , n { \big ) }$ 为一组毕达哥

拉斯模糊数， $\omega = \left( \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { n } \right) ^ { T }$ 为权重向量， $\omega _ { i } \in \left[ 0 , 1 \right] , \sum _ { i = 1 } ^ { n } \omega _ { i } = 1$ $\alpha _ { \mathrm { m i n } } = \operatorname* { m i n } _ { i } \{ \alpha \}$ ， $\alpha _ { \mathrm { { m a x } } } = \operatorname* { m a x } _ { i } \{ \alpha \}$ ，则

$$
\alpha _ { \mathrm { m i n } } \leq P F W H M ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { n } ) \leq \alpha _ { \mathrm { m a x } }
$$

性质4\~6证明过程完全类似性质 $_ { 1 \sim 3 }$ ，限于篇幅，故略。

# 3基于毕达哥拉斯模糊加权 Heronian 算子的多属性决策方法

在本节中，应用毕达哥拉斯模糊加权Heronian 算子建立了毕达哥拉斯模糊优先的多属性决策方法，其中属性的评价值用毕达哥拉斯模糊数表示，设有 $m$ 个备选方案和 $n$ 个属性，备选方案集为 $A = \left( { { A _ { 1 } } , { A _ { 2 } } , . . . , { A _ { m } } } \right)$ ，决策属性集为 $\boldsymbol { C } = \left( C _ { 1 } , C _ { 2 } , . . . , C _ { n } \right)$ ，$\boldsymbol { \omega } = \left( \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { n } \right) ^ { T }$ 为权重向量， $\omega _ { i } \in \left[ 0 , 1 \right]$ ， $\sum _ { i = 1 } ^ { n } \omega _ { i } = 1$ 。决策者给出方案 $A _ { i }$ 关于属性 $C _ { j }$ 的评价值为毕达哥拉斯模糊数，表示为$\alpha _ { i j } = \left. \mu _ { i j } , \nu _ { i j } \right.$ ，从而可以得到决策者给出的毕达哥拉斯模糊决策矩阵 $Q = \left( \alpha _ { i j } \right) _ { m \times n }$ 。根据上述信息，对 $m$ 个备选方案进行排序或者择优。

下面给出一种基于毕达哥拉斯模糊加权Heronian算子的决策方法的步骤如下：

a)根据属性的特性对 $Q = \left( \alpha _ { i j } \right) _ { m \times n }$ 进行标准化处理得到的标准化毕达哥拉斯模糊矩阵 $\overline { { \boldsymbol { Q } } } = \left( \overline { { \boldsymbol { \alpha } } } _ { i j } \right) _ { m \times n }$ ，其中：

b)利用毕达哥拉斯模糊加权Heronian算子对毕达哥拉斯模糊决策矩阵的评价值进行集成，其中：

$$
\begin{array} { r l } & { P F W M M ^ { \mathcal { H } ^ { n } } ( \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n } ) } \\ & { ( \frac { 2 } { n ( n + 1 ) \underbrace { \hat { \omega } _ { n , \ldots } ^ { \mathrm { i n } } ( ( \omega _ { n } ) ^ { p } } _ { \mathrm { = : } \alpha _ { 1 } , \ldots , \alpha _ { n } } ) ^ { p } ( \omega _ { n } , \alpha _ { j } ) ^ { q } ) ^ { \frac { 1 } { p ^ { n + 1 } } } } } \\ & { = ( \sqrt { 1 - ( \frac { \displaystyle \hat { \Pi } } { \displaystyle \prod _ { s = i - 1 } ^ { N } ( 1 - ( \mu _ { n } ^ { x } ) ^ { p } ( \mu _ { n } ^ { x } ) ^ { p } ) ) ^ { \frac { 2 } { p ^ { n + 1 } } } } ) ^ { \frac { 1 } { p ^ { n + 1 } } } } , } \\ & { \sqrt { 1 - ( \mathbb { 1 } - ( \frac { \displaystyle \hat { \Pi } } { \displaystyle \prod _ { s = i - 1 } ^ { N } ( 1 - ( ( 1 - \nu _ { i } ^ { x } ) ^ { p } ) ^ { p } ( ( 1 - \nu _ { j } ^ { x } ) ^ { p } ) ^ { p } ) ) ^ { \frac { 2 } { p ^ { n + 1 } } } } ) ^ { \frac { 1 } { p ^ { n + 1 } } } } ) ^ { \frac { 1 } { p ^ { n } } } } ) ^ { 1 }   \end{array}
$$

且 $p$ 与 $q$ 不同时为0的非负实数。

c)利用毕达哥拉斯模糊数的得分函数计算各方案的综合评价值。

d)利用定义6对各方案的综合属性值从大到小排序，得到最优方案。

e)结束。

# 4 实例分析

本章为前面章节研究结果的具体应用，将上文研究所得到的毕达哥拉斯模糊加权Heronian算子和决策模型应用于国内航空公司服务质量评价的实际问题中，以验证本研究的有效性和合理性。

国内航空市场在快速发展的同时，竞争也日趋激烈。在价格战之外，服务质量已成为航空公司保持竞争力的关键要素。改革开放四十年以来，我国社会不断发展，经济飞速增长，人民生活水平日益提高，人们更有能力选择适合自己的方便快捷的交通运输方式出行，航运也不再是富裕者才能进行的奢侈行为。显然，航运作为一种最为方便快捷的交通运输方式已经走进了千千万万普通家庭，已成为人们出行旅游的首要选择。科技的发展使世界进入信息化时代，航空公司在提供同质化的基础服务之外，运用高科技发展特色服务来吸引客户成为必要手段。不论来自国内还是国外，我国民航公司的压力都是巨大的。作为典型的一类垄断竞争性服务行业，要想在夹缝中顽强生存下来并发展下去，对国内民航服务质量的研究分析十分必要。服务质量是民航运输业竞争力的重要内容，也是行业竞争优势的重要来源。民航作为我国服务业的重要组成部分与人们的生活息息相关，如何提高我国民航的服务质量，进而提高乘客满意度就显得更加不容忽视。

在本研究中，假设经专家组的初步筛选后，对国内四家航空公司 $A = \left( A _ { 1 } , A _ { 2 } , A _ { 3 } , A _ { 4 } \right)$ 的服务质量进行评价[17]，鉴于篇幅，四家航空公司的具体情况在此不加以赘述，在现有文献基础上，经专家组的数论讨论，确定为 $C _ { 1 }$ ：订票/售票服务、 $C _ { 2 }$ ：登记程序、$C _ { 3 }$ ：客舱服务、 $C _ { 4 }$ ：响应性，为四个评价指标，为了真实的刻画专家的评价信息，其评价结果采用毕达哥拉斯模糊数表示，其各评价指标的权重为 $\omega = \left( 0 . 1 5 , 0 . 2 5 , 0 . 3 5 , 0 . 2 5 \right) ^ { T }$ ，取 $p = 1$ ， $q = 1$ 。为确保本次评价的科学性和合理性，邀请了来自科研机构、政府部门和非盈利组织等机构的数名专家参与此次评价活动。在评价期初，专家们承受着时间压力，参考资料也有限，以及自身对相关问题的经历也有限等问题，专家组表示愿意采用毕达哥拉斯模糊数表示对相关问题的判断，有利于反映自己对评价问题的不确定性。其专家的评价结果如表1所示。

表1毕达哥拉斯模糊矩阵  
Table 1Pythagorean fuzzy matrix   

<html><body><table><tr><td></td><td>C</td><td>C</td><td>C</td><td>C4</td></tr><tr><td>A</td><td>{0.9,0.3)</td><td>(0.7,0.6)</td><td>{0.5,0.8)</td><td>{0.6,0.3)</td></tr><tr><td>A</td><td>(0.4,0.7)</td><td>(0.9,0.2)</td><td>(0.8,0.1)</td><td>(0.5,0.3)</td></tr><tr><td>A</td><td>(0.8,0.4)</td><td>(0.7,0.5)</td><td>(0.6,0.2)</td><td>(0.7,0.4)</td></tr><tr><td>A</td><td>(0.7,0.2)</td><td>{0.8,0.2)</td><td>(0.8,0.4)</td><td>(0.6,0.6)</td></tr></table></body></html>

a)此评价指标均为效益属性，无须对矩阵进行标准化。

b)利用毕达哥拉斯模糊加权Heronian算子对毕达哥拉斯模糊决策矩阵的评价值进行集成，其中：

$$
\begin{array} { r l } & { P F W H M ^ { 1 1 } ( \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n } ) } \\ & { ( \frac { 2 } { n ( n + 1 ) \displaystyle \sum _ { i = n , m ^ { \prime } } ^ { \infty } ( ( \omega , \alpha _ { i } ) ^ { p } \Phi ( \omega , \alpha _ { j } ) ^ { q } ) ) ^ { \frac { 1 } { p \sigma _ { i } } } } } \\ & { =  ( \sqrt { 1 - ( \displaystyle \prod _ { i = 1 , m ^ { \prime } } ^ { \infty } ( 1 - ( \mu _ { i } ^ { \alpha } ) ( \mu _ { i } ^ { \alpha } ) ) ) ) ^ { \frac { 2 } { \sigma _ { i } } } }  ^ { \frac { 1 } { 2 } } , } \\ & { \sqrt { 1 - ( 1 - ( \displaystyle \prod _ { i = 1 , m ^ { \prime } } ^ { \infty } ( 1 - ( 1 - \nu _ { i } ^ { 2 } ) ^ { \alpha } ) ( ( 1 - \nu _ { j } ^ { 2 } ) ^ { \alpha } ) ) ) ^ { \frac { 2 } { 2 \sigma _ { i } } } ) ^ { \frac { 1 } { 2 } } } } \end{array}
$$

计算得

$$
\begin{array} { r l } & { A _ { 1 } = \left. 0 . 9 8 3 7 , 0 . 1 5 6 2 \right. ; A _ { 2 } = \left. 0 . 9 8 4 9 , 0 . 0 6 0 9 \right. ; } \\ & { A _ { 3 } = \left. 0 . 9 8 5 7 , 0 . 0 8 7 9 \right. ; A _ { 4 } = \left. 0 . 9 8 9 0 , 0 . 0 8 0 3 \right. } \end{array}
$$

c)利用式（6）计算 $A = \left( A _ { 1 } , A _ { 2 } , A _ { 3 } , A _ { 4 } \right)$ 的得分函数，分别为

$$
{ \mathrm { S } } \left( A _ { _ { 1 } } \right) = 0 . 9 4 3 0 0 \ ; { \mathrm { } } S \left( A _ { _ { 2 } } \right) = 0 . 9 6 6 4 \ ; { \mathrm { } } S \left( A _ { _ { 3 } } \right) = 0 . 9 6 3 9 \ ; { \mathrm { } } S \left( A _ { _ { 4 } } \right) = 0 . 9 7 1 6
$$

d)根据其得分函数的值，方案优劣排序为 $A _ { 4 } \succ A _ { 2 } \succ A _ { 3 } \succ A _ { 1 }$ ，即 $A _ { 4 }$ 是最优的。

以上分析结果是假设 $p = 1$ ， $q = 1$ 的情况，下面来讨论当 $p$ 、$q$ 取其他值的情况，其集结结果、得分值和排序结果如表2和3所示。

Table 2Pythagorean fuzzy weighted Heronian operator assembly result   
表3排序结果  

<html><body><table><tr><td>A</td><td>A2</td><td>A</td><td>A4</td></tr><tr><td>p=q=1 (0.9837,0.1562) (0.9849,0.0609) (0.9857,0.0879) (0.9890,0.0803)</td><td></td><td></td></tr><tr><td>p =q=2 (0.9780,0.1787) (0.9795,0.0730) (0.9804,0.1053) (0.9846,0.0959)</td><td></td><td></td></tr><tr><td>p =q=5 (0.9438,0.1975) (0.9452,0.0897) (0.9470,0.1294) (0.9564,0.1163)</td><td></td><td></td></tr><tr><td>p =q=10 (0.9700,0.1974) (0.9689,0.1001) (0.9693,0.1455) (0.9734,0.1279)</td><td></td><td></td></tr><tr><td>p =q=50 (0.9815,0.1646) (0.9765,0.1033) (0.9733,0.1577) (0.9701,0.1219)</td><td></td><td></td></tr></table></body></html>

表2毕达哥拉斯模糊加权Heronian 算子集结结果  
Table 3Sequence result   

<html><body><table><tr><td>pq</td><td>得分值</td><td>排序结果</td></tr><tr><td>p=q=1</td><td>S(A)=(0.9430,0.9664,0.9639,0.9716)</td><td>A4 γ Aγ A γ A</td></tr><tr><td>p=q=2</td><td>S(A)=(0.9247,0.9540,0.9501,0.9627)</td><td>A4 γ Aγ A γ A</td></tr><tr><td>p=q=5</td><td>S(A)=(0.8518,0.8854,0.8801,0.9013)</td><td>A4 >AγA >A</td></tr><tr><td>p=q=10</td><td>S(A)=(0.9020,0.9288,0.9183,0.9312)</td><td>A4 γ Aγ Aγ A</td></tr><tr><td>p=q=50</td><td>S(A)=(0.9363,0.9429,0.9225,0.9263)</td><td>A γ A γ Aγ A</td></tr></table></body></html>

由表3可以看出，在不同参数 $p$ 、 $q$ 取值下，其排序结果也略有不同。但进一步观察表3可知，当 $p$ 、 $q$ 的取值不断增大时，其集结结果和得分值也都有微妙的变化，导致排序结果也有相应的变化，说明排序结果受到决策者参数选择的主观影响，因此专家在评估时可以根据自己的主观偏好进行参数的选择。

上述分析是基于参数 $p = q$ 的情况下，在某种程度上存在一定的局限性。下面分析当 $\textit { p , q }$ 取值不同时，对集成结果的影响。其结果如表4所示。

由表4可以看出，当 $\textit { p , q }$ 取值不同时，其排序结果也不尽相同，最优方案为 $A _ { 2 }$ 或者 $A _ { 4 }$ ；当 $p$ 、 $q$ 的取值越大，属性间的相互作用就越强。在现实决策中，可以选用较为简单的值，以便于简化计算。P、q的灵活取值能更好地模拟现实决策环境，决策者也可以根据实际的决策问题来选取合适的 $p$ 和q值。

Table 4Score value and its sequence result   

<html><body><table><tr><td>p、q</td><td>得分值</td><td>排序结果</td></tr><tr><td>p=1,q=5</td><td>S(A)=(0.9184,0.9490,0.9399,0.9511)</td><td>A > Aγ A  A</td></tr><tr><td>p=5,q=1</td><td>S(A)=(0.9234,0.9504,0.9438,0.9536)</td><td>A> Aγ A  A</td></tr><tr><td>p =2,q =10</td><td>S(A)=(0.9069,0.9395,0.9257,0.9386)</td><td>A > A4 γ A γ A</td></tr><tr><td>p =10,q =2</td><td>S(A)=(0.9130,0.9403,0.9299,0.9409)</td><td>A4 > Aγ A  A</td></tr><tr><td>p=3,q=20</td><td>S(A)=(0.9098,0.9378,0.9182,0.9308)</td><td>A> A γAγ A</td></tr><tr><td>p =20,q=3</td><td>S(A)=(0.9169,0.9380,0.9225,0.9326)</td><td>Aγ Aγ AγA</td></tr><tr><td>p=4,q=30</td><td>S(A)=(0.9156,0.9398,0.9172,0.9284)</td><td>A> Aγ AγA</td></tr><tr><td>p =30,q=4</td><td>S(A)=(0.9224,0.9398,0.9211,0.9297)</td><td>A > A γ A γ A</td></tr><tr><td>p =5,q=40</td><td>S(A)=(0.9210,0.9422,0.9183,0.9278)</td><td>A> A>A> A</td></tr><tr><td>p = 40,q=5</td><td>S(A)=(0.9273,0.9422,0.9216,0.9288)</td><td>Aγ A4γ A γ A</td></tr></table></body></html>

下面进一步对比分析文献[4]中的PFWA 算子、文献[14]中的GPFOWA算子、文献[5]的TOPSIS方法和文献[15]中PFPWA算子的得分值和排序结果，如表5所示。

表4得分值及其排序结果  
表5对比分析结果  
Table 5Comparative analysis results   

<html><body><table><tr><td>得分值</td><td>排序结果</td></tr><tr><td>本文 S(A)=(0.9430,0.9664,0.9639,0.9716)</td><td>A4 > A > A > A</td></tr><tr><td>文献[4] S(A)=(0.0850,0.4250,0.3250,0.3650)</td><td>A > A γ A  A</td></tr><tr><td>文献[14] S(A)=(-0.0013,0.2122,0.1441,0.2174)</td><td>A4 γ A γ Aγ A</td></tr><tr><td>文献[5]</td><td>Aγ AγA γA</td></tr><tr><td>文献[15] S(A)=(0.2466,0.3695,0.2921,0.5630)</td><td>A4> AγAγ A</td></tr></table></body></html>

通过对比分析可知，本文的排序结果和文献[14]中的GPFOWA算子、文献[15]中PFPWA算子的最优方案同为 $A _ { 4 }$ ，而文献[4]中的PFWA算子、文献[5]的TOPSIS方法的最优方案同为 $A _ { 2 }$ ，且各方法所得到的得分值和排序结果也略微不同。造成差异的主要原因是以上几种模型均采用了不同的集结方法，其集结算子的侧重点也不尽相同，文献[4]和文献[5]所采用的的方法主要是研究属性间独立的情况，并未考虑到属性间的相关性，故最优方案不同。若采用文献[5]的TOPSIS方法，不仅最优结果不同，而且该方法在信息集结方面计算过于繁琐，时间复杂度较高，不利于实际的操作。在进行服务质量的评价时，评价属性间往往并不相互独立，而是相互联系相互影响，也就是说这些评价属性信息之间会存在相互的关联、互补等关系，因此只有充分考虑属性间的相互关联性才能使得决策更加的合理。而本文提出的毕达哥拉斯模糊加权Heronian算子的多属性决策方法充分地考虑了属性之间的关联性，且能够根据决策者的主观偏好选择其参数值，并且在算子集结计算方面简单易于操作。基于以上分析，本文得出的结论是合理且有效的。

# 5 结束语

考虑到现实中相对复杂的多属性决策问题，方案的属性之间往往相互关联相互影响，为更加精细地集结复杂环境下的决策信息，针对此类信息的集成问题，本文将毕达哥拉斯模糊数与Heronian算子的优点相结合，提出了毕达哥拉斯模糊Heronian算子和毕达哥拉斯模糊加权Heronian算子，弥补了现有的毕达哥拉斯模糊集成算子的不足，建立了基于毕达哥拉斯模糊加权算子Heronian的决策模型，丰富了毕达哥拉斯模糊集理论。最后将其应用国内四家航空公司服务质量评价中，并且将现已有的集成算子的集结结果进行比较分析，结果显示本文研究的属性间具有相关关系的多属性决策问题模型的正确性和可行性，也为以后的多属性决策研究提供了新思路。

# 参考文献：

[1]Zadeh LA.Fuzzy sets [J]. Information and Control,1965,8(3): 338-353.   
[2]Atanassov K.Intuitionistic fuzzy sets [J].Fuzzy Sets and Systems,1986,20 (1): 87-96.   
[3] Yager R R,Abbasov A M.Pythagorean membership grades，complex numbers and decision making [J].International Journal of Intelligent Systems,2013,28 (5):436-452.   
[4]Yager R R.Pythagorean membership grades in multi-criteria decision making [J].IEEE Trans on Fuzzy Systems,2014,22 (4): 958-965.   
[5]Zhang Xiaolu,Xu Zeshui.Extension ofTOPSIS to multiple criteria decision making with Pythagorean fuzzy sets [J]. International Journal of Intelligent Systems,2014,29 (12): 1061-1078.   
[6] Peng Xindong, Yang Yong. Some results for Pythagorean fuzzy sets [J]. International Journal of Intellgent Systems,2015,30 (11): 1133-1160.   
[7]Beliakov G,Pradera A,Calvo T. Aggregation functions:a guide for practitioners [M]. Berlin: Springer, 2007.   
[8] Sykora S. Mathematical means and average: generalized Heronian means [J].Sykora S Stan's,Library,2009.   
[9]Sykora S.Generalized Heronian Means II[M]. Sykora S Stan's,Library, 2009.   
[10] Zhang Xiaolu.Multi-criteria Pythagorean fuzzy decision analysis:a hierarchical QUALIFLEX approach with the closeness index-based ranking methods [J].Information Sciences,2016,330:104-124.   
[11] Peng Xindong, Yang Yong. Fundamental properties of interval-valued Pythagorean fuzzy aggregation operators [J]. International Journal of Intelligent Systems,2016,31 (5): 444-487.   
[12] Ren Peijia,Xu Zeshui, Gou Xunjia. Pythagorean fuzzy TODIM approach to multi-criteria decision making [J].Applied Soft Computing,2016,42: 246- 259   
[13] Gou Xunjia,Xu Zeshui，Ren Peijia. The properties of continuous Pythagorean fuzzy information [J]. International Journal of Intelligent Systems,2016,31 (5): 401-424   
[14] 刘卫锋，常娟，何霞．广义毕达哥拉斯模糊集成算子及其决策应用[J]. 控制与决策,2016,31(12): 2280-2286.(Liu Weifeng,Chang Juan,He Xia. Generalized Pythagorean fuzzy aggregation operators and applications in decision making [J]. Control and Decision,2016,31(12): 2280-2286.)

[15]丁恒，李延来．基于毕达哥拉斯模糊幂加权平均算子的多属性群决策 方法[J].计算机工程与应用,2018,54(5):1-6.(Ding Heng,Li Yanlai. Multiple atribute group decision making method based on Pythagorean fuzzy power weighted average operator [J].Computer Engineering and Applications,2018,54(5): 1-6.)

[16]Liu Peide.Multiple attribute group decision making method based on interval-valued intuitionistic fuzzy power Heronian aggregation operators

[J].Computers & Industrial Engineering,2017,108:199-122.   
[17]Liu Peide,Liu Zhengming,Zhang Xin.Some intuitionistic uncertain linguistic Heronian mean operators and their application to group decision making [J]. Soft Computing,2014,230 (12): 570-586.   
[18] Yu Dejian. Intuitionistic fuzzy geometric Heronian mean aggregation operators [J].Applied Soft Computing Journal,2013,13 (2):1235-1246.