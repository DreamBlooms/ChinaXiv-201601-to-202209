# 基于最优近似粗糙集的属性约简

罗来鹏，刘二根，范自柱(华东交通大学 理学院，南昌 330013)

摘要：为了更好地获取由边界域产生的不确定性规则知识，提出最优近似粗糙集的属性约简方法，为此首先给出了近似空间上粗糙集最优近似集的判定与计算，然后引入最优近似分布协调集、最优近似分布约简概念。讨论了Pawlak属性约简、分布约简、最优近似分布约简之间关系，最后得到在协调决策表中它们是等价的，在不协调决策表中最优近似分布约简是分布约简子集。从UCI数据集选取5个数据集进行实验，结果表明基于最优近似分布约简能够获得较少的约简属性。

关键词：粗糙集；属性约简；相似度；最优近似集；分布约简；最优近似分布约简中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.12.0856

# Attributes reduction based on optimal approximation set of rough set

Luo Laipeng,Liu Ergen,Fan Zizhu ((SchoolofSciences,East China JiaotongUniversity,Nanchang 33oo13,China)

Abstract:Toobtainthe knowledgeof uncertaintyrules generatedbytheboundaryregion,thepaperdevelopedanattribute reductionalgorithmbasedontheoptimalapproximaterough set.Firstlythis paper presentedthe judgementandcalculationof theoptimalapproximationstofroughsetinapproximate space;scondly,itintroducedtheconceptsoftheoptialapproiate distributioncoordinationsetsandtheoptimal approximate distributionreduction,anddiscussed.therelationsamong Pawlak attributesreduction,distrbutionrductionanddistributionreductionbasedontheoptipalapproximationsetofroughset finaly itobtained theconclusion thattheyareequivalentinthecoordinationdecision tableandthedistributionreductionsetbasedon theoptipalapproximationsetofrough setissubsetofthedistributionreductionsets.Experimentresultsondatasets fromUCI showthatthe atribute reduction algorithmbased on the optimal approximate rough set can achivelesssetof attibutes.

Key words:rough set；atributes reduction;similarity degreeoptimal approximationset；distributionreduction；optipal approximation distribution reduction

# 0 引言

属性约简是粗糙集理论[的应用核心,基于它的知识获取往往存在不确定性。一方面是因为近似空间上知识的粒太大而造成概念的不确定性；另一方面是由于近似空间上粗糙集边界造成的系统不确定性[2]。对于一个给定的近似空间，概念的不确定性往往无法改变，因此如何更好挖掘系统不确定性所蕴涵的知识一直是众多研究者关注的焦点。当前比较典型的研究模型有变精度粗糙集模型和概率粗糙集模型.变精度粗糙集模型主要是通过引进粗糙性测度或近似精度来实现。米据生等人讨论了变精度粗糙集模型[3\~5],并利用它进行属性约简,取得了较好的效果[10]，并由此发展了粗糙集的三支决策[6-8]。Yao 和 Ziarko等人[9,10]结合概率论和包含度提出了概率粗糙模型,也取得了较好的理论成果。这两个模型都是在基本粗糙集模型的基础上，通过引入一个在区间（0.5,1]上阈值作为分类正确率而建立。阈值的具体取值对模型的属性约简结果具有直接影响,在实际应用中很难确定一个最优的阈值.此外这两个模型目标概念的表示仍然使用上、下近似的表示方法.那么在目标概念的上、下近似集之间哪个集合更为近似目标概念呢？近几年张清华教授对这个问题展开了研究，提出目标概念新的刻画，即粗糙集的最优近似[11]。文献[12,13]以集合的相似度大小为准则,通过模糊截集的方法,在目标概念的上、下近似集之间构造一个隶属度大于或等于 $r$ 集合 $R _ { \lambda } ( X )$ ,讨论 $R _ { \lambda } ( X )$ 和目标概念两个边界集作为目标概念最优近似集的条件,并就最优近似集的问题作了进一步的研究得到一些新的理论成果.但是对于一个具体的目标概念集未讨论如何求解最优近似集，尤其基于粗糙集最优近似集表示下属性约简问题.针对上述问题本论文提出粗糙集的最优近似集新判定与计算,并在此基础上提出最优近似粗糙集的属性约简算法,并讨论该算法约简结果与其他相关算法约简结果之间关系。

# 1 相关概念

定义[II1设U是有限论域,R是U上的等价关系,由此构成一个近似空间为(U,R),等价关系 $\mathrm { ~ \tt ~ R ~ }$ 决定的等价类也称为近似空间(U,R)上基本知识，表示为 $\mathrm { U / R } = \ \{ [ x _ { i } ] _ { R } { \big | } x _ { i } \in U \}$ 其中$[ x _ { i } ] _ { R } = \{ x _ { j } \big | ( x _ { i } , x _ { j } ) \in R \} \ ,$

定义 $^ { \lbrack 1 \rbrack } 2$ (U,R)为近似空间, $X \subseteq U$ 为目标概念，则${ \underline { { R } } } ( X ) = \{ [ x ] _ { R } { \big | } [ x ] _ { R } \subseteq X \} , { \overline { { R } } } ( X ) = \{ [ x ] [ x ] _ { R } \cap X \not = \phi \}$ 分别称为目标概念X关于近似空间(UR)下近似集、上近似集。$B N _ { _ R } ( X ) = { \overline { { R } } } ( X ) - \underline { { R } } ( X ) , N E G _ { _ R } ( X ) = U - { \overline { { R } } } ( X )$ 分别称为目标X在近似空间(U，R)上边界集和负域。

定义 $\mathbf { 3 ^ { [ 1 ] } }$ (U,R)为近似空间,目标概念 $X \subseteq U$ ,若 ${ \underline { { R } } } ( X ) = { \overline { { R } } } ( X )$ ，则称目标概念 $\mathrm { \Delta } \mathrm { X }$ 在近似空间(U,R)上是可以定义的精确集,否则为粗糙集。

如果X是近似空间(U,R)上的粗糙集,一般用它的上、下近似集作为边界来表示即 $( \underline { { R } } ( X ) , \overline { { R } } ( X ) )$ 。

定义 $^ { [ 1 4 ] } 4$ 设(U,R)为近似空间, $X \subseteq U , Y \subseteq U ,$ 若映射S:$U \times U \to [ 0 , 1 ]$ ,即 S(X,Y)满足以下条件:a)有界性。 $0 \leq S ( X , Y ) \leq 1$ ,特别地 ${ \mathrm { S } } ( { \mathrm { X } } , { \mathrm { X } } ) { = } 1$ ， ${ \mathrm { S } } ( { \mathrm { X } } , { \mathrm { Y } } ) { = } 0$ 当且仅当 $X \cap Y = \phi$ 。b)对称性。 $S ( X , Y ) = S ( Y , X )$ 。$\mathbf { c } ) \widetilde { X } \subseteq Y \subseteq Z , S ( X , Y ) \geq \mathrm { S } ( \mathrm { X } , Z ) , \mathrm { S } ( \mathrm { Y } , Z ) \geq \mathrm { S } ( \mathrm { X } , Z ) \circ$ 称S为集合X，Y的相似度，对于经典集合，两个集合的相似定义度可定义为$S ( X , Y ) = { \frac { \left| X \cap Y \right| } { \left| X \cup Y \right| } }$ 其中||表示集合基数，下文都是这种约定.

# 2 基于最优近似集的属性约简

# 2.1粗糙集的最优近似集

设 X 是近似空间(U,R)的目标概念，令 $\alpha = \frac { \left| \underline { { R } } ( X ) \right| } { \left| X \right| }$ $\beta = \frac { \left| X \right| } { \left| \overline { { R } } ( X ) \right| }$ $B _ { \ u { X } } = \left\{ [ x ] _ { \ u { R } } \big | 0 < \frac { \big | [ x ] _ { \ u { R } } \cap \ d { X } \big | } { \big | [ x ] _ { \ u { R } } \big | } < 1 , \ u { x } \in U \right\}$ $C _ { X } = \{ \left[ x \right] _ { R } \left. \frac { \left. \left[ x \right] _ { R } \cap X \right. } { \left. \left[ x \right] _ { R } - X \right. } \geq \alpha , \left[ x \right] _ { R } \in B _ { X } \right. \}$ ，则 $B _ { \scriptscriptstyle { X } }$ 是 $\mathrm { \Delta } \mathrm { X }$ 在近似空间（U,R)上的边界域, $\alpha , \beta$ 分别为X与它的下近似集、上近似集的相似度，且 $C _ { \chi } \subseteq B _ { \chi }$ 。对于任意 $A \subseteq B _ { X }$ ， ${ \underline { { R } } } ( X ) \cup A$ 都是 $\mathrm { \Delta } \mathrm { X }$ 的近似集,因此 $\mathrm { \Delta } \mathrm { X }$ 在近似空间上的近似集合会有很多个。

定义5设X在近似空间（U,R）上所有近似集为 $X ^ { a p p s }$ ，若存在 $X _ { 1 } \in X ^ { a p p s }$ ，使得对于任意的 $X _ { _ 2 } \in X ^ { a p p s }$ ，有 $\operatorname { S } ( \mathrm { X } , \mathrm { X } 1 ) { \overset { } { \mathop { = } } } \mathrm { S } ( \mathrm { X } , \mathrm { X } 2 )$ 则称X1为 $\mathrm { \Delta } \mathrm { X }$ 在（U,R）上最优近似集。

接下来讨论近似空间上一个目标概念的最优近似计算

定理1X为近似空间(U,R)上的目标概念,若 $\Phi \subset { \cal C } _ { \scriptscriptstyle X } \subset \mathsf { B } _ { \scriptscriptstyle X }$ ,则X最优近似集为 $\underline { { R } } ( X ) \cup C _ { X }$ 。

证明 对于任意 $[ y ] _ { R } \in C _ { x }$ 有 ${ \frac { \left| [ y ] _ { R } \cap X \right| } { \left| [ y ] _ { R } - X \right| } } \geq \alpha$ ,不妨设  
$C _ { X } = \bigcup _ { i = 1 } ^ { k } [ y _ { i } ] _ { R }$ ，且 ${ \frac { \left| [ y _ { 1 } ] _ { R } \cap X \right| } { \left| [ y _ { 1 } ] _ { R } - X \right| } } \leq \cdots \leq { \frac { \left| [ y _ { k } ] _ { R } \cap X \right| } { \left| [ y ] _ { k } - X \right| } }$ 根据不等式性质有：$S ( { \underline { { R } } } ( X ) , X ) \leq { \frac { \left| { \underline { { R } } } ( X ) \right| + \left| [ y _ { 1 } ] _ { R } \cap X \right| } { \left| X \right| + \left| [ y _ { 1 } ] _ { R } - X \right| } } \leq \cdots \leq { \frac { \left| { \underline { { R } } } ( X ) \right| + \sum _ { i = 1 } ^ { k } \left| [ y _ { i } ] _ { R } \cap X \right| } { \left| X \right| + \sum _ { i = 1 } ^ { k } \left| [ y _ { i } ] _ { R } - X \right| } }$ 而对于任意 $\mathrm { j } ( \mathrm { j } { < } \mathbf { k } )$ 有：$S ( \underline { { R } } ( X ) \cup [ y _ { 1 } ] _ { R } \cup \cdots \cup [ y _ { j } ] _ { R } ) , X \} = \frac { | ( R ( X ) \cup [ y _ { 1 } ] _ { R } \cup \cdots \cup [ y _ { j } ] _ { R } ) \cap X | | } { [ ( R ( X ) \cup [ y _ { 1 } ] _ { R } \cup \cdots \cup [ y _ { j } ] _ { R } ) \cup X ] }$   
$= { \frac { \left| ( { \underline { { R } } } ( X ) \cap X ) \cup ( [ y _ { 1 } ] _ { R } \cap X ) \cup \cdots \cup ( [ y _ { j } ] _ { R } \cap X ) \right| } { \left| { \underline { { R } } } ( X ) \cup X \cup [ y _ { 1 } ] _ { R } \cup \cdots \cup [ y _ { j } ] _ { R } \right| } } = { \frac { \left| { \underline { { R } } } ( X ) \right| + \sum _ { i = 1 } ^ { j } \left| [ y _ { i } ] _ { R } \cap \mathbf { X } \right| } { \left| X \cup [ y _ { 1 } ] _ { R } \cup \cdots \cup [ y _ { j } ] _ { R } \right| } }$ $= { \frac { \displaystyle { \big | } { \underline { { R } } } ( X ) { \big | } + \sum _ { i = 1 } ^ { j } [ [ y _ { i } ] _ { R } \cap X { \big | } } { \displaystyle { \big | } X { \big | } + \sum _ { i = 1 } ^ { j } [ [ y _ { i } ] _ { R } - X { \big | } } }$ 即 $S ( \underline { { R } } ( X ) , X ) \leq S ( ( \underline { { R } } ( X ) \cup [ y _ { 1 } ] _ { R } ) , X ) \leq \cdots \leq S ( ( \underline { { R } } ( X ) \cup B _ { X } ) , X )$ 所以X最优近似集为 $\underline { { R } } ( X ) \cup C _ { x }$ 。根据上述结论得到以下两个结论：性质1若 $\scriptstyle \mathbf { C } _ { \mathrm { X } } = \phi$ ,则 $\mathrm { \Delta } \mathrm { X }$ 最优近似集为下近似集 ${ \underline { { R } } } ( X )$ □性质2若 $C _ { \chi } = B _ { \chi }$ ,则 $\mathrm { \Delta } \mathrm { X }$ 最优近似集为上近似集 ${ \overline { { R } } } ( X )$ 。

# 2.2基于最优近似的分布约简

定义6决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ,其中U为有限论域,C为条件属性集,D为决策属性集,V为属性值集合，f为信息函数，且 $\mathrm { U / C = \{ C 1 , C 2 , \mathrm { . . . C m \} , U / D = \{ D 1 , D 2 , D n \} \circ } }$

接下来讨论它的最优近似约简。

记 Di在 U/C 上的最优近似集表示为: $D _ { C } ^ { ( D _ { i } ) }$ ,Ci所在的最优近似集表示为 $\mathsf { D } _ { c } ( C _ { i } )$ 并称 $\mathsf { D } _ { C } ^ { * } = \{ D _ { c } ^ { ( \mathrm { D } _ { 1 } ) } , D _ { C } ^ { ( D _ { 2 } ) } , \cdots , D _ { c } ^ { ( D _ { n } ) } \} \ ( D _ { i } \in U / D )$ 为 $\mathrm { ~ D ~ }$ 在C上的最优近似分布。

定理2设决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ 是协调的,那么对于任意i有 $D _ { C } ^ { ( D _ { i } ) } = \underline { { C } } ( D _ { i } )$ ,反之不成立。

证明若决策系统 DS 是协调的,对于任意 $\mathbf { D } _ { \mathrm { i } } \in U / D$ 有$B _ { D _ { i } } = \Phi$ ，所以有 $D _ { C } ^ { ( D _ { i } ) } = \underline { { C } } ( D _ { i } )$ ，反之不成立，如U/C={{x1,x2},{x3,x4,x5},{x6,x9},{x7,x8}},U/D={{x1,x2,x3},{x$4 , { \mathrm { x 6 } } , { \mathrm { x 9 } } \} , \{ { \mathrm { x } } 5 , { \mathrm { x 7 } } , { \mathrm { x 8 } } \} \}$ ,对于任意 ${ \mathrm { D i } } \in { \mathrm { U } } / { \mathrm { D } }$ 在 U/C上的最优近似集为其下近似集,显然这个划分对应的的决策系统非协调。

定义7决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ,其中C为条件属性集,D 为决策属性集, $\mathbf { B } \subseteq \mathbf { C }$ ,若 $\boldsymbol { \mathrm { D } } _ { C } ^ { * } = \boldsymbol { D } _ { B } ^ { * }$ ,则称B为最优近似分布协调集.若B是最优近似分布协调集且B的任何真子集都不是最优近似分布协调集,则称B为最优近似分布约简。

定义8决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ 其中C,D 为条件属性集，决策属性集,CD决定的等价类为：$\mathrm { U / C } = \{ \mathrm { C 1 } , \mathrm { C 2 } , . . . \mathrm { C m } \} , \mathrm { U / D } = \{ \mathrm { D 1 } , \mathrm { D 2 } , ~ . . . \mathrm { D n } \} , \mathrm { F }$ 月 $f _ { k } ( C _ { i } )$ 表示属性 $a _ { \scriptscriptstyle k }$

关于 $\mathsf { C } _ { i }$ 中对象的取值,定义

$$
D ( C _ { i } , C _ { j } ) = \left\{ \begin{array} { c c } { \{ a _ { k } \in C : f _ { k } ( C _ { i } ) \neq f _ { k } ( C _ { j } ) } & { D _ { C } ( C _ { i } ) \neq D _ { C } ( C _ { j } ) \} } \\ { C } & { D _ { C } ( C _ { i } ) = D _ { C } ( C _ { j } ) } \end{array} \right.
$$

则 $D ( C _ { i } , C _ { j } )$ 为 $C _ { i }$ 和 $\mathrm { C } _ { j }$ 可辨识属性集。

定义9决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ,其中C,D分别为条件属性集,决策属性集 $\mathrm { , U / C = \{ C 1 , C 2 , \mathrm { . . . C m \} , U / D = \{ D 1 , D 2 , . . . , D n \} } }$ $D = \{ D ( C _ { i } , C _ { j } ) , i , j \le m \}$ 为最优近似分布可辨识矩阵。

根据辨识矩阵属性约简方法，得到如下定理：

定理3设目标信息系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ，辨识公式$\textstyle \bigwedge \{ \vee ( a _ { k } \in D ( C _ { i } , C _ { j } ) : i , j \leq m \}$ 的极小析取范式为决策目标系统的最优近似分布约简。

具体证明可参考相关文献[15]。

# 2.3基于最优近似集的属性约简算法描述

决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ，其中C,D分别为条件属性集,决策属性集且 $\mathrm { U / C = \{ X 1 , X 2 , \ldots X m \} , U / D = \{ D 1 , D 2 , \ldots , \ D n \} }$ ，最优近似分布约简步骤如下：

a)计算 $D _ { c } ^ { ( D _ { i } ) } ( i = 1 , 2 , \cdots , n )$ ,得到 $D _ { c } ^ { * }$ ,具体为:

(a)对于任意D ∈UID,计算R(D）,α= $\alpha = \frac { R ( D _ { i } ) } { \left| D _ { i } \right| }$

(b)计算

$$
B _ { D _ { i } } = \{ X _ { k } \Bigg | 0 < \frac { \Big | X _ { k } \cap D _ { i } \Big | } { \Big | X _ { k } \Big | } < 1 , X _ { k } \in U / C \} , C _ { D _ { i } } = \{ X _ { k } \frac { \Big | \Big | X _ { k } \cap D _ { i } \Big | } { \Big | \Big | X _ { k } - D _ { i } \Big | } \geq \alpha , X _ { k } \in B _ { D _ { i } } \}
$$

（c）判断与求解。若 $C _ { D _ { i } } = \Phi , D _ { i }$ 最优近似集为下近似集$\underline { { R } } ( D _ { i } )$ ；若 $C _ { D _ { i } } = B _ { D _ { i } }$ ，则 $D _ { i }$ 最优近似集为上近似集 $\overline { { R } } ( D _ { i } )$ ：$\Phi \subset C _ { D _ { i } } \subset B _ { D _ { i } }$ ,则 $D _ { i }$ 最优近似集为 $\underline { { R } } ( D _ { i } ) \cup C _ { D _ { i } }$ 。

b)计算不同类之间基于最优近似集的辨识属性集$D ( C _ { i } , C _ { j } ) ( i , j \leq m )$ 并构造最优近似分布分辨矩阵。

c)求出最优近似分布矩阵极小析取范式,得到最优近似分布。

# 3 最优近似分布约简与其他约简之间的关系

定义 $\mathbf { 1 0 ^ { [ 1 ] } }$ 决策系统 $\mathrm { D S } { = } ( \mathrm { U } , \mathrm { C } \cup \mathrm { D } , \mathrm { V } , \mathrm { f } ) , \mathrm { C }$ 为条件属性集，D为决策属性集,若 $B \subseteq C , p o s _ { B } ( D ) = p o s _ { C } ( ( D )$ ,且B是C的D独立子集,那么B为Pawlak属性约简也称正域约简.

记 $D ( D _ { j } / [ x ] _ { C } ) { = } \frac { \left| D _ { j } \cap [ x ] _ { C } \right| } { \left| [ x ] _ { C } \right| } ( j \leq n )$ ，则 $\mathrm { ~ D ~ }$ 为 $D _ { j }$ 与 $\left[ x \right] _ { C }$ 的包含度，$\mu _ { \mathrm { C } } ( x ) = ( D ( D _ { 1 } / [ x ] _ { C } ) , D ( D _ { 2 } / [ x ] _ { C } ) , \cdots , D ( D _ { n } / [ x ] _ { C } ) , ( x \in U )$ ，则称 $\mu _ { \scriptscriptstyle \mathrm { C } } ( x )$ 为关于属性C在决策系统DS 中的广义分布函数[2]。

定义 $\mathbf { 1 1 } ^ { [ 2 ] }$ 决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ ,其中C,D分别为条件属性集,决策属性集,C.D决定的等价类为 $\mathrm { U / C } { = } \{ \mathrm { C l } , \mathrm { C } 2 , \cdots$ $\mathrm  C m \} , \mathrm { U / D = \{ D 1 , D 2 , D n \} , }$ $B \subseteq C$ ,若对于任意 $x \in U$ 有 $\mu _ { c } ( { \boldsymbol { x } } ) = \mu _ { B } ( { \boldsymbol { x } } )$ 号则称B是分布协调集。若B是分布协调集且B的任何真子集不是分布协调集,则称B是分布约简。

定理4决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ 其中C为条件属性集,D为决策属性集,若决策表是协调的，那么决策系统的Pawlak属性约简、分布约简与最优近似分布约简等价。

证明若B是协调决策表 DS 的Pawlak 约简,则对于任意$D _ { i } \in { U } / { D }$ ，有 $\underline { { C } } ( D _ { i } ) = \underline { { B } } ( D _ { i } ) = D _ { i }$ ，即有 $p o s _ { c } ( D ) = p o s _ { B } ( D )$ ，和$\boldsymbol { D } _ { C } ^ { * } = \boldsymbol { D } _ { B } ^ { * }$ 且对于任意x $\mathsf { \Pi } _ { : \in \mathrm { U } , \frac { \left| D _ { i } \cap [ x ] _ { C } \right| } { \left| [ x ] _ { C } \right| } = \frac { \left| D _ { i } \cap [ x ] _ { B } \right| } { \left| [ x ] _ { B } \right| } }$ （204号 即 $\mu _ { c } ( x ) = \mu _ { B } ( x )$ 故B也是分布约简和最优近似分布约简。

而当决策系统是非协调时,最优近似分布约简与分布约简不等价。

定理5设决策系统 $\scriptstyle \mathrm { D S = ( U , C \cup D , V , f ) }$ 其中C为条件属性集,D为决策属性集， $B \subseteq C$ ,若B是决策系统的分布约简，则B是系统的最优近似分布协调集。

证明 对于任意 $D _ { i } \in { U } / { D }$ ， $\mu _ { c } ( { \boldsymbol { x } } ) = \mu _ { \scriptscriptstyle B } ( { \boldsymbol { x } } )$ ，（ $\mathbf { x } \in \mathbf { U } )$ ，即$\frac { \left| \mathbb { D } _ { i } \cap [ x ] _ { B } \right| } { \left| [ x ] _ { B } \right| } { = } \frac { \left| D _ { i } \cap [ x ] _ { C } \right| } { \left| [ x ] _ { C } \right| }$ 由等比性质得到 $\frac { | D _ { i } \cap [ x ] _ { B } | } { \| x \| _ { B } | - | D _ { i } \cap [ x ] _ { B } | } { = } \frac { | D _ { i } \cap [ x ] _ { c } | } { \| x \| _ { A } | - | D _ { i } \cap [ x ] _ { c } | }$ ，由集合性质得到 ${ \frac { \left| D _ { i } \cap [ x ] _ { B } \right| } { \left| [ x ] _ { B } - D _ { i } \right| } } = { \frac { \left| D _ { i } \cap [ x ] _ { A } \right| } { \left| [ x ] _ { A } - D _ { i } \right| } }$ ，所以有 $\boldsymbol { \mathrm { D } } _ { C } ^ { * } = \boldsymbol { D } _ { B } ^ { * }$ ,故 $\mathbf { B }$ 是最优近似协调集，

分布约简是最优近似协调集,但是未必是最优近似分布约简,最优近似分布约简是分布约简子集。比如决策系统 $\scriptstyle \mathrm { { D S = } } ( \mathrm { { U } } , \mathrm { { C } }$ U D,V,f),其中

U={x1,x2,x3,x4,x5,x6},C={a1,a2,a3,a4},D $\ L =$ {d},U/C={C1,C 2.C3,C4 $\{ \} , \mathrm { U / d } = \{ \mathrm { D } 1 , \mathrm { D } 2 \} \mathrm { D } 1 = \{ \mathrm { x } 1 , \mathrm { x } 5 , \mathrm { x } 6 \} , \mathrm { D } 2 = \{ \mathrm { x } 2 , \mathrm { x } 3 , \mathrm { x } 4 \} \mathrm { C } 1 = \{ \mathrm { x } 1 \} ,$ $\scriptstyle \mathbf { C } 2 = \{ \mathbf { x } 2 \} , \mathbf { C } 3 = \{ \mathbf { x } 3 , \mathbf { x } 5 , \mathbf { x } 6 \} , \mathbf { C } 4 = \{ \mathbf { x } 4 \}$

它的分布约简与最优近似约简如下：

D(C1,C2)={a1,a2,a3,a4},D(C1,C3) $) =$ {al,a2},D(C1,C4)={a1,a $2 , \mathrm { a } 3 \} , \mathrm { D } ( \mathrm { C } 2 , \mathrm { C } 3 ) = \{ \mathrm { a } 3 , \mathrm { a } 4 \} , \mathrm { D } ( \mathrm { C } 3 , \mathrm { C } 4 ) = \{ \mathrm { a } 3 \}$

辨识公式为

$( \mathbf { a } 1 \lor \mathbf { a } 2 \lor \mathbf { a } 3 \lor \mathbf { a } 4 ) \land ( \mathbf { a } 1 \lor \mathbf { a } 2 ) \land ( \mathbf { a } 1 \lor \mathbf { a } 2 \lor \mathbf { a } 3 ) \land ( \mathbf { a } 3 \lor \mathbf { a } 4 )$ ${ \mathrm { a 4 } } ) { \mathrm { a 3 } } { = } ( { \mathrm { a 1 a 3 } } ) \wedge ( { \mathrm { a 2 a 3 } } )$ ，即ala3,a2a3为目标系统的两个分布约简，

下面给出最优近似分布约简：

$$
D _ { C } ^ { ( { D _ { 2 } } ) } = ( \mathrm { C } 2 \mathrm { , C } 4 \} \mathrm { D } ( \mathrm { C } 1 \mathrm { , C } 2 ) { = } \{ \mathrm { a } 1 \mathrm { , a } 2 \mathrm { , } \mathrm { a } 3 \mathrm { , } \mathrm { a } 4 \} , 
$$

$$
\mathrm { D } ( \mathrm { C } 1 , \mathrm { C } 4 ) = \{ \mathrm { a } 1 , \mathrm { a } 2 , \mathrm { a } 3 \} , \mathrm { D } ( \mathrm { C } 2 , \mathrm { C } 3 ) = \{ \mathrm { a } 3 , \mathrm { a } 4 \} , \mathrm { D } ( \mathrm { C } 3 , \mathrm { C } 4 ) = \{ \mathrm { a } 3 \}
$$

辨识公式为

$( \mathrm { a 1 } \vee \mathrm { a 2 } \vee \mathrm { a 3 } \vee \mathrm { a 4 } ) \wedge ( \mathrm { a 1 } \vee \mathrm { a 2 } \vee \mathrm { a 3 } ) \wedge ( \mathrm { a 3 } \vee \mathrm { a 4 } ) \mathrm { a 3 } - \mathrm { a 3 }$ 即是说a3 为目标系统的唯一的最优近似分布约简.

综合得到：分布约简是最优近似协调集，但不是最优近似分布约简,最优近似分布约简是分布约简的子集，

根据定理1,还可以得到如下结论：设决策系统 $\scriptstyle \mathrm { { D S = } } ( \mathrm { { U } } , \mathrm { { C U } }$ D,V,f),其中C为条件属性集,D 为决策属性集，对于任意的$D _ { i } \in { U } / { D }$ 若 $D _ { C } ^ { ( D _ { i } ) } = \underline { { C } } ( D _ { i } )$ ,那么最优近似分布约简变为为正域约简或下近似约简,对于任意的 $D _ { i } \in { U } / { D }$ ，若 $D _ { C } ^ { ( D _ { i } ) } = \overline { { C } } ( D _ { i } )$ ,最优近似约简即变为上近似约简。这不仅进一步验证了上述结论，同时可以发现最优近似约简实际上是一种根据系统知识之间的关系而选择不同属性约简的综合，能更好地刻画了粗糙集不需要先验知识的特性。

# 4 实验

为了更好地说明本文所得到的结论，选用了UCI数据库中的5个数据集:Mushroom,Vote,Vehicle,Gene，Ticdata2000，就分布约简，最优近似约简的约简结果进行对比分析，用 $\left| { C _ { m } } \right|$ 表示约简后属性个数，采用MATLAB编程计算得到如表1所示结果。

从实验结果可以看出，在第一个数据集分布约简与最优近似分布约简的约简结果是一样，那是因为此时的最优近似约简和分布约简就是下近似约简，这也验证了最优近似约简与分布约简之间存在的关系，后四个数据集最优近似分布约简比分布约简得到更少的属性约简集,这些完全符合本文得到的理论结果。从压缩的比例来看，两个算法对这5个数据集对属性压缩比例如表2所示。

还是很显著。

# 5 结束语

面对不确定性系统的属性约简，目前比较流行的方法是变精度粗糙集和概率粗糙集模型,但是这两种方法都存在着参数如何设置问题.文提出的基于最优近似属性约简方法虽然也属于分布约简范畴,但是弱化了参数的设置。并且从约简结果之间关系可以看出基于最优近似集的属性约简不仅具有更少的属性约简个数，而且具有一定的泛化性能,为研究决策系统之间属性关系拓展了思路.那么粗糙集的最优近似、变精度近似与概率近似之间存在怎样关系，笔者认为这是一个值得研究问题，这对于进一步探索不同属性约简结果之间关系具有重要作用。

表1不同数据集的约简结果比较  

<html><body><table><tr><td>Datasets</td><td>u |C|</td><td>分布约简(Ic=l)</td><td>最优近似分布约简(lc)</td></tr><tr><td>Mushroom</td><td>8124 22</td><td>5</td><td>5</td></tr><tr><td>Vote</td><td>435 16</td><td>10</td><td>8</td></tr><tr><td>Vehicle</td><td>946 18</td><td>11</td><td>9</td></tr><tr><td>Gene</td><td>3190 60</td><td>11</td><td>9</td></tr><tr><td>Ticdata2000</td><td>5822 85</td><td>24</td><td>20</td></tr></table></body></html>

# 参考文献：

[1]Pawlak Z. Rough sets [J]. Computer and Information Science,1982,11 (5): 341-356.   
[2]张文修，梁怡，吴伟志．信息系统与知识发现[M].北京：科学出版社， 2003.   
[3]Mi Jusheng，Wu Weizhi，Zhang Wenxiu.Approaches to knowledge reduction based on variable precision rough set model [J]. Information Sciences,2004,159 (3-4): 255-272.   
[4]张贤勇.精度与程度逻辑差双量化粗糙集模型的属性约简[J]．系统工 程理论与实践,2015,35(11):2925-2931.   
[5]曾子林，张宏军，张睿，等．变精度粗糙集的逻辑解释及其约简[J]计 算机应用研究,2013,30(5):1385-1387.   
[6] 张鑫，李续武，路艳丽，等．基于不完备区间值信息系统的决策粗糙集 [J]．计算机应用研究,2017,34(1):110-112.   
[7]Feng Qinrong,ZhouYing. Soft discernibility matrix and Its applications in decision making [J].Applied Soft Computing,2014,24(11): 749-756.   
[8] 李美争，王国胤.三支近似概念格中基于对象-概念辨识矩阵的属性约 简方法[J].控制与决策,2016,31(10):779-784.   
[9]Yao Yiyu.Probabilistic rough set approximations [J].Approximate Reasoning,2008,49 (2): 255-271.   
[10] Ziarko W. Probabilistic approach to rough sets [J]. Approximate Reasoning, 2008,49 (2): 272-284.   
[11]张清华，王国胤，肖雨．粗糙集的近似集[J].软件学报，2012,23（7): 1745-1759.   
[12]张清华，薛玉斌，胡峰，等．粗糙集近似集不确定性研究[J].电子学 报,2016,44(7):1574-1580.   
[13]张清华，薛玉斌，王国胤．粗糙集的最优近似集[J]．软件学报,2016, 27 (2): 295-308.   
[14]袁修久，张文修．模糊粗糙集的包含度和相似度[J].模糊系统与数学, 2005,19 (1): 111-115.

表2不同数据集的属性压缩比例比较  

<html><body><table><tr><td rowspan="2">Datasets</td><td rowspan="2">|C</td><td rowspan="2">分布约简 压缩比例</td><td rowspan="2">最优近似分布</td><td rowspan="2">压缩比例 提高百分比</td></tr><tr><td>约简压缩比例</td></tr><tr><td>Mushroom</td><td>22</td><td>77.3%</td><td>77.3%</td><td>0%</td></tr><tr><td>Vote</td><td>16</td><td>37.5%</td><td>50%</td><td>12.5%</td></tr><tr><td>Vehicle</td><td>18</td><td>39%</td><td>50%</td><td>11%</td></tr><tr><td>Gene</td><td>60</td><td>81.7%</td><td>85%</td><td>3.3%</td></tr><tr><td>Ticdata200</td><td>85</td><td>71.8%</td><td>76.5%</td><td>4.7%</td></tr></table></body></html>

从表2可以发现最优近似分布约简对属性压缩比例要高，后面两个数据集之所以提高百分比不大，那是因为属性基数太大，属性个数改变对百分比的影响要小，但是从约简绝对个数