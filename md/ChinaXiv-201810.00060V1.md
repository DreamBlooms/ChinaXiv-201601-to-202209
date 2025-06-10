# 基于可能度容差关系的多粒度粗糙决策分析方法

骆公志，许鑫鑫(南京邮电大学 管理学院，南京 210023)

摘要：在不完备区间值决策信息系统中，针对可能度容差关系和多粒度决策粗糙集的各自优点，提出一种基于可能度容差关系的多粒度决策粗糙模型。首先提出可能度的概念，定义新的容差关系；然后构建了基于可能度容差关系的乐观和悲观多粒度决策粗糙集模型，给出模型的上下近似，并对相关性质和定理进行证明；最后以实例验证了模型的有效性与适用性。结果表明，通过调整属性相似度阈值 $\omega$ ，可使模型具有一定的容错能力和很强的分类能力。

关键词：不完备区间值决策信息系统；容差关系；粗糙集 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.07.0381

# Rough analysis method of multi-granularity decision rough set based on possible degree tolerance relation

Luo Gongzhi, Xu Xinxin† (College ofManagement,Nanjing Universityof Posts & Telecommunications,Nanjing 21ooo3,China)

Abstract: According totheadvantagesofmulti-granularityroughsetandpossibledegreetolerancerelation,this paperproposed arough setbasedonposibledegree tolerancerelationship.Firstly,itcameupwith possble degreeand proposedthepossible degree tolerancerelation.Then,basedonposibledegree tolerancerelation,itdefined theoptimisticandpessimisticmultigranulation decisionrough set.Andrelevant theorems and propertiesare provedintheincomplete interval-valued information system.Finaly,byuseofacase,verifythat the new method has feasibilityand effectivenessThe experimentalresults show thatthemulti-granularity decision rough set basedon possble degree tolerance relation has a fault tolerance and strong classification ability by adjusting the parameter $\omega$

Key Words: incomplete interval-valued decision information system; tolerance relation; rough set

# 0 引言

粗糙集作为分析处理不确定性的数学工具，已被广泛应用于众多领域[1-4]。经典粗糙集模型[5]基于等价关系处理完备的离散型信息系统。而现实生活中，本文面对的信息系统除了包含离散型数据外，很多测量值都表示为一定范围内的区间值，且往往是不完备的，这就使得传统粗糙集在实际应用中存在一定局限性。为解决这一问题，众多学者对传统粗糙集模型进行扩展[7\~l0]。Yang[11]以不完备区间值信息系统为研究对象，构建了基于 $\alpha$ -优势关系的粗糙集模型，并通过给定判断定理和可辨别函数，来计算粗糙集的下近似和上近似。Dai[2]等进一步在不完备区间值信息系统中定义了最大和最小相似度，并基于属性相似度构建了基于 $\alpha$ -弱相似关系的粗糙集模型，以评估不完备区间值信息系统中的不确定性。

当前对不完备区间值信息系统的研究中，大部分学者主要用优势关系[13\~15]代替等价关系来处理缺失值。部分学者从属性集的相容度、差异度和对立度的角度定义相似度容差关系，并以此关系建立粗糙集模型[16-17]。Dai[18]等在不完备区间值信息系统中提出可能度容差关系，有效解决了不完备区间值信息系统的缺失值问题。从粒计算的角度来看，上述基于不完备区间值信息系统的粗糙模型都是从单个等价关系或单个优势关系来对论域进行分类，无法从多粒度、多层次的角度对问题进行分析和处理。Qian等人[19]提出多粒度粗糙集，采用一族不可分辨关系对目标进行逼近，包括乐观多粒度粗糙集和悲观多粒度粗糙集。在此基础上，学者们提出了各种扩展模型[20-23]。Sang 等人[24]利用贝叶斯决策理论分析了多粒度粗糙集模型中的概率融合关系,构建了乐观多粒度决策粗糙集模型和悲观多粒度决策粗糙集模型。

针对不完备区间值决策信息系统，本文将可能度容差关系引入多粒度决策粗糙模型中，构建新的多粒度决策粗糙模型，验证了模型的相关性质，并对模型的定理进行证明。同时，研究了属性相似度阈值 $\omega$ 的变化对分类的影响。该模型综合了可能度容差关系和多粒度决策粗糙集的优点，有效

拓展了模型的适用范围，理论分析和实验结果均证明了该方法的有效性和实用性。

# 1 基本概念

# 1.1不完备区间值决策信息系统

定义 $\mathbf { 1 } ^ { [ 1 6 ] }$ 信息系统为一四元组 $K = ( U , A { = } C \cup D$ ， $\operatorname { \delta } V , f )$ ，其中 $U = \{ x _ { 1 } , x _ { 2 } , . . . , x _ { n } \}$ 为有限对象集，称为论域； $c$ 为条件属性集， $_ D$ 为决策属性集； $f = \{ f _ { k } : k \leq m \}$ 为对象属性映射集，其中（20 $f _ { k }$ $U \to V _ { k } ( k \leq m ) \$ ， $V _ { _ k }$ 是属性 $a _ { \scriptscriptstyle k }$ 的有限值域，即 $x _ { i } \in U \ , f _ { k } ( x _ { i } )$ （204号$\in V _ { k }$ ： $V = \bigcup _ { a _ { k } \in A } V _ { k }$ 称为全体属性值域。若 $f _ { k } ( x _ { i } ) = [ l _ { i } ^ { k } , r _ { i } ^ { k } ] \ , \ l _ { i } ^ { k } \ \leq r _ { i } ^ { k }$ ，则称 $K$ 是区间值决策信息系统。若存在 $x _ { i } \in U , a _ { k } \in A  \ , \ f _ { k } ( x _ { i } ) = *$ (“\*”表示缺失值)，则表明对象 $x _ { i }$ 在属性 $a _ { k }$ 上的值未知，此时称 $K$ 是不完备区间值决策信息系统。

# 1.2多粒度决策粗糙集

设 $K = ( U , A = C \cup D , V , f \}$ 是一完备决策信息系统，其中$R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $\mathbf { \Sigma } _ { m }$ 个属性子集， $\Omega =$ $\{ \omega _ { 1 } , \omega _ { 2 } , . . . , \omega _ { s } \}$ 是 $s$ 个有限状态集， $A = \{ a _ { 1 } , a _ { 2 } , . . . , a _ { m } \}$ 是 $n$ 个有限行动集，其中 $\lambda _ { \scriptscriptstyle k } ( a _ { \scriptscriptstyle i } | \omega _ { \scriptscriptstyle j } )$ 表示第 $k$ 个粒结构在状态 $\omega _ { j }$ 下采取行动$a _ { i }$ 的风险代价： $P ( \omega _ { j } \mid x _ { k } )$ 为第 $k$ 个粒结构下对象 $x$ 在状态 $\omega _ { j }$ 下的条件概率，假设 $\lambda _ { k } ( a _ { i } \mid \omega _ { j } ) = \lambda _ { l } ( a _ { i } \mid \omega _ { j } )$ ，可以得到给定对象 $x$ （204号在 $\mathbf { \Sigma } _ { m }$ 个粒度结构下采取行动期望风险为

$$
R ( a _ { i } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) = \sum _ { k = 1 } ^ { m } \lambda _ { k } ( a _ { i } | \omega _ { j } ) P _ { \sum _ { j = 1 } ^ { s } R _ { i } } ( \omega _ { j } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } )
$$

其中： $P _ { \sum _ { j = 1 } ^ { s } R _ { i } } ( \omega _ { j } \mid x _ { 1 } , x _ { 2 } , . . . , x _ { m } )$ 是不同多粒度融合策略下的概率统一表示形式。

设状态集 $\Omega = \{ X , X ^ { c } \}$ ，给定 $\mathbf { \Omega } _ { m }$ 个粒结构，其中决策行动包括正域决策（ $P O S ( X ) ~ )$ 、负域决策（ $N E G ( X )$ ）和边界决策${ \bf \Xi } ( { \bf \Lambda } _ { B N D ( X ) } )$ ，记决策集为 $\{ a _ { 1 } , a _ { 2 } , a _ { 3 } \}$ ，其对应的期望损失分别为

$$
R _ { 1 } = R ( a _ { 1 } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) =
$$

$$
\lambda _ { 1 1 } \underset { \ldots } { \underbrace { P _ { _ m } } } ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) + \lambda _ { 1 2 } \underset { \ldots } { \underbrace { P _ { _ m } } } ( X ^ { c } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } )
$$

$$
R _ { 2 } = R ( a _ { 2 } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) ^ { = }
$$

$$
\lambda _ { 2 1 } P _ { \underset { i = 1 } { m } } \ : ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) + \lambda _ { 2 2 } P _ { \underset { i = 1 } { m } } \ : ( X ^ { c } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } )
$$

$$
\lambda _ { 3 1 } P _ { \underset { i = 1 } { m } } \ : ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) + \lambda _ { 3 2 } P _ { \underset { i = 1 } { m } } \ : ( X ^ { c } | x _ { 1 } , x _ { 2 } , . . . , x _ { m } )
$$

其中： $\begin{array} { l l l } { \lambda _ { i 1 } = \lambda ( { a } _ { i } | X ) , } & { \lambda _ { i 2 } = \lambda ( { a } _ { i } \big | X ^ { c } ) ~ , } & { i = 1 , 2 , 3 } \end{array}$ 。决策代价函数值的大小满足 $\lambda _ { 1 1 } \leq \lambda _ { 3 1 } \leq \lambda _ { 2 1 } , \lambda _ { 2 2 } \leq \lambda _ { 3 2 } \leq \lambda _ { 1 2 }$ ，决策规则如下：

$$
\begin{array} { r l } & { \underset { \underset { i = 1 } { \overset { \ldots } { \sum } } R _ { i } } { \overset { P _ { w } } { \sum } } ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) \geq \alpha , x \in P O S ( X ) } \\ & { \underset { \underset { i = 1 } { \overset { \ldots } { \sum } } R _ { i } } { \overset { N } { \sum } } ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) \leq \beta , x \in N E G ( X ) } \\ & { \underset { \mathrm { i = 1 } } { \overset { P _ { w } } { \sum } } R _ { i } } \\ & { \delta < \underset { \underset { i = 1 } { \overset { \ldots } { \sum } } R _ { i } } { \overset { N } { \sum } } ( X | x _ { 1 } , x _ { 2 } , . . . , x _ { m } ) < \alpha , x \in B N D ( X . } \end{array}
$$

其中： $\alpha = \frac { \lambda _ { 1 2 } - \lambda _ { 3 2 } } { ( \lambda _ { 3 1 } - \lambda _ { 3 2 } ) - ( \lambda _ { 1 1 } - \lambda _ { 1 2 } ) } ~ , ~ \gamma = \frac { \lambda _ { 1 2 } - \lambda _ { 2 2 } } { ( \lambda _ { 2 1 } - \lambda _ { 2 2 } ) - ( \lambda _ { 1 1 } - \lambda _ { 1 2 } ) } ~ ,$ $\beta = \frac { \lambda _ { 3 2 } - \lambda _ { 2 2 } } { ( \lambda _ { 2 1 } - \lambda _ { 2 2 } ) - ( \lambda _ { 3 1 } - \lambda _ { 3 2 } ) } ~ , ~ 0 \le \beta < \gamma < \alpha \le 1 \circ$

定义 $\pmb { 2 } ^ { [ 1 9 ] }$ 设 $K = ( U , A = C \bigcup D , V , f \}$ 是一完备决策信息系统，给定 $\mathbf { \Sigma } _ { m }$ 个粒度结构 $R _ { 1 } , R _ { 2 } , . . . , R _ { m } \subseteq C$ ， $\forall X \subseteq U$ ，其中$0 \leq \beta < \alpha \leq 1$ ，则乐观多粒度决策粗糙集的下近似、上近似和边界区定义为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \alpha ) } ( X ) = \{ \mathbf { x } { : } P ( \mathbf { X } | [ x ] _ { R _ { 1 } } ) \geq \alpha \lor P ( \mathbf { X } | [ x ] _ { R _ { 2 } } ) \geq \alpha \lor
$$

$$
\dots \lor P ( \mathbf { X } \vert [ x ] _ { _ { R _ { m } } } ) \geq \alpha , x \in U \}
$$

$$
\begin{array} { r } { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \beta ) } } } ( X ) = U - \{ \mathrm { x } \colon P ( \mathrm { X } \| [ x ] _ { R _ { 1 } } ) \leq \beta \wedge P ( \mathrm { X } \| [ x ] _ { R _ { 2 } } ) \leq \beta \wedge P ( \mathrm { X } \| [ x ] _ { R _ { 1 } } ) , } \end{array}
$$

$$
\dots \wedge P ( \mathrm { X } | [ x ] _ { _ { R _ { m } } } ) \leq \beta , x \in U \}
$$

$$
\mathbf { B N } _ { \sum _ { i = 1 } ^ { m } R _ { i } } ^ { o } = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \beta ) } } } ( X ) - \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \alpha ) } } _ { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \alpha ) } } ( X )
$$

其中：P(X[x]m） $P ( \mathrm { X } | [ x ] _ { R _ { m } } ) = { \frac { \left| [ x ] _ { R _ { m } } \bigcap X \right| } { \left| [ x ] _ { R _ { m } } \right| } }$ 为条件概率。

定义 $\ 3 ^ { [ 1 9 ] }$ 设 $K = ( U , A = C \cup D , V , f \}$ 是一完备决策信息系统，给定 $\mathbf { \Sigma } _ { m }$ 个粒度结构 $R _ { 1 } , R _ { 2 } , . . . , R _ { m } \subseteq C$ ， $\forall X \subseteq U$ ，其中$0 \leq \beta < \alpha \leq 1$ ，则悲观多粒度决策粗糙集的下近似、上近似和边界区定义为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { { ( P , \alpha ) } } ( X ) = \{ \operatorname { x } { \operatorname { x } { \mathord { : } } P ( \operatorname { X } \lvert [ x ] _ { R _ { 1 } } ) } \geq \alpha \land P ( \operatorname { X } \lvert [ x ] _ { R _ { 2 } } ) \geq \alpha \land P ( X \lvert [ x ] _ { R _ { 2 } } ) \geq \alpha \land P ( X \lvert [ x ] _ { R _ { 1 } } ) \}
$$

$$
\dots \wedge P ( \mathrm { X } | [ x ] _ { _ { R _ { m } } } ) \geq \alpha , x \in U \}
$$

$$
\begin{array} { r } { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \beta ) } } } ( X ) = U - \{ \mathrm { x } : P ( \mathrm { X } \vert [ x ] _ { R _ { 1 } } ) \leq \beta \vee P ( \mathrm { X } \vert [ x ] _ { R _ { 2 } } ) \leq \beta \vee } \end{array}
$$

$$
\dots \lor P ( \mathrm { X } | [ x ] _ { _ { R _ { m } } } ) \leq \beta , x \in U \}
$$

$$
\mathbf { B N } _ { \sum _ { i = 1 } ^ { m } R _ { i } } ^ { P } = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \beta ) } } } ( X ) - \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \alpha ) } } _ { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \alpha ) } } ( X )
$$

# 2 基于可能度容差关系的多粒度决策粗糙集

定义 $\pmb { 4 } ^ { [ 1 8 ] }$ 设 $K = ( U , A = C \cup D , V , f \}$ 是一不完备区间值决策信息系统， $a _ { k } \in C$ ， $x _ { i }$ ， $\boldsymbol { x } _ { j }$ 为 $U$ 中的任意两个对象，当 $x _ { i }$ ，$\boldsymbol { x } _ { j }$ 关于属性 $a _ { k }$ 的属性值均不为单值时，则 $x _ { i }$ ， $\boldsymbol { x } _ { j }$ （20

关于属性 $a _ { \scriptscriptstyle k }$ 的相似可能度 （x²≥x²）定义为

$$
\begin{array} { r } { P _ { ( x _ { i } ^ { * } \geq x _ { j } ^ { * } ) } = \left\{ \begin{array} { l l } { \operatorname* { m i n } \{ 1 , \operatorname* { m a x } ( \frac { r _ { i } ^ { k } - l _ { j } ^ { k } } { r _ { i } ^ { k } - l _ { i } ^ { k } + r _ { j } ^ { k } - l _ { j } ^ { k } } , 0 ) \} , f ( x _ { i } , a _ { \star } ) = [ l _ { i } ^ { k } , r _ { i } ^ { k } ] \neq \ast , f ( x _ { j } , a _ { \star } ) = [ l _ { j } ^ { k } , r _ { j } ^ { k } ] \neq \ast } \\ { \quad } \\ { \quad } \\ { \operatorname* { m i n } \{ 1 , \operatorname* { m a x } ( \frac { r _ { \mathrm { m a x } } ^ { k } - l _ { j } ^ { k } } { r _ { \mathrm { m a x } } ^ { k } - l _ { \mathrm { m i n } } ^ { k } + r _ { j } ^ { k } - l _ { j } ^ { k } } , 0 ) \} , f ( x _ { i } , a _ { \star } ) = \ast , f ( x _ { j } , a _ { s } ) = [ l _ { j } ^ { k } , r _ { j } ^ { k } ] } \\ { \quad } \\ { \operatorname* { m i n } \{ 1 , \operatorname* { m a x } ( \frac { r _ { i } ^ { k } - l _ { j } ^ { k } } { r _ { i } ^ { k } - l _ { i } ^ { k } + r _ { \mathrm { m a x } } ^ { k } - l _ { \mathrm { m i n } } ^ { k } } , 0 ) \} , f ( x _ { i } , a _ { \star } ) = [ l _ { i } ^ { k } , r _ { i } ^ { k } ] , f ( x _ { j } , a _ { \star } ) = \ast } \\ { \quad } \\ { \quad } \\ { \quad } \\ { \quad } \end{array} \right. } \end{array}
$$

当 $s _ { i } , \ x _ { j }$ 关于属性 $a _ { k }$ 的属性值均为单值时，两对象属性值若相等，则 $x _ { i } \ , x _ { j }$ 关于属性 $a _ { k }$ 的相似可能程度为1，不相等则为0。

定义5设 $K = ( U , A = C \cup D , V , f \}$ 是一不完备区间值决策信息系统， $a _ { k } \in C ~ , ~ x _ { i }$ ， $\boldsymbol { x } _ { j }$ 为 $U$ 中的任意两个对象，当 $x _ { i } \ , x _ { j }$ 关于属性 $a _ { k }$ 的属性值均不为单值时，则 $x _ { i } \ , \ x _ { j }$ 关于属性 $a _ { k }$ 的相似度定义为

$$
S _ { \mathrm { i j } } = 1 - \left| P _ { ( x _ { i } ^ { a _ { k } } \geq x _ { j } ^ { a _ { k } } ) } - P _ { ( x _ { j } ^ { a _ { k } } \geq x _ { i } ^ { a _ { k } } ) } \right|
$$

其中： $P _ { ( x _ { i } ^ { a _ { k } } \geq x _ { j } ^ { a _ { k } } ) }$ 是這 $x _ { i } \ , x _ { j }$ 关于属性 $a _ { k }$ 的属性值均不为单值时，xi，xj关于属性αk 的相似可能度，|P为集合P的基数。

定义6给定一不完备区间值决策信息系统 $K = ( U , A =$ $C \cup D , V , f \}$ ，对于 $a _ { k } \in C \ : , \ : \ : \omega \ : ^ { \mathrm { ~ ( ~ } } 0 \leq \omega \leq 1 ^ { \mathrm { ~ ) ~ } }$ 是给定相似度阈值，基于不完备区间值信息系统上的容差关系定义为

$$
\Gamma _ { A } ^ { \omega } ( \mathrm { X } ) \ = \ \{ ( x _ { i } , x _ { j } ) \in U ^ { 2 } \big | S _ { i j } \geq \omega , \forall a _ { k } \in C \big \}
$$

显然： $\Gamma _ { A } ^ { \omega }$ 满足自反性、对称性，但不满足传递性。

定义7设 $K = ( U , A = C \cup D , V , f \}$ 是一不完备区间值决策信息系统， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $\mathbf { \Sigma } _ { m }$ 个属性子集， $\forall X \subseteq U$ ， $a _ { k } \in C$ ， $\omega$ 是给定相似度阈值，且 $0 \leq \omega \leq 1$ ，$0 \leq \beta < \alpha \leq 1$ ，则基于可能度容差关系的多粒度决策粗糙集的下近似、上近似和边界区定义为：

$$
\underline { { R } } _ { i } ^ { ( \omega , \alpha ) } ( X ) = \{ x \big | P ( \mathbf { X } | \Gamma _ { R _ { i } } ^ { \omega } ( x ) ) \geq \alpha , x \in U \}
$$

$$
\overline { { R } } _ { i } ^ { ( \omega , \beta ) } ( X ) = \{ x \big | P ( \mathbf { X } | \Gamma _ { R _ { i } } ^ { \omega } ( x ) ) > \beta , x \in U \}
$$

$$
\mathbf { B N } _ { \sum _ { i = 1 } ^ { m } R _ { i } } ^ { ( \omega ) } = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( \omega , \beta ) } } } ( X ) - \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( \omega , \alpha ) } } _ { = 1 } ( X )
$$

其中： $P ( \mathrm { X } | \Gamma _ { R _ { i } } ^ { \omega } \left( x \right) ) = \frac { \left| \Gamma _ { R _ { i } } ^ { \omega } \left( x \right) \bigcap X \right| } { \left| \Gamma _ { R _ { i } } ^ { \omega } \left( x \right) \right| }$ 为条件概率。

定义8设 $K = ( U , A = C \cup D , V , f \}$ 是不完备区间值决策信息系统， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $\mathbf { \Psi } _ { m }$ 个属性子集,$\forall X \subseteq U$ ， $a _ { k } \in C$ ， $\omega$ 是给定相似度阈值，且 $0 \leq \omega \leq 1$ ，$0 \leq \beta < \alpha \leq 1$ ，则基于可能度容差关系的乐观多粒度决策粗糙集的下近似、上近似和边界区定义为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( X ) = \{ x : P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \geq \alpha \vee P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \geq \alpha
$$

$$
\bigtriangledown . . . \bigtriangledown P ( \mathrm { X } \big | \Gamma _ { R _ { m } } ^ { \omega } \left( x \right) ) \geq \alpha , x \in U \}
$$

$$
\begin{array} { r } { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( X ) = U - \{ x { : } P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \leq \beta \land P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \leq \beta } \end{array}
$$

$$
\land \dots \land P ( \mathbf { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \leq \beta , x \in U \}
$$

$$
\mathbf { B N } _ { \sum _ { i = 1 } ^ { m } R _ { i } } ^ { ( O , \omega ) } = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( X ) - \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } } _ { = 1 } ( X )
$$

可以看出，当 $\alpha { = } 1 , \beta { = } 0$ 时，基于可能度容差关系的乐观多粒度决策粗糙集将退化为可能度容差关系下的乐观多粒度粗糙集。

定理1给定一不完备区间值决策信息系统$K = ( U , A = C \cup D , V , f \}$ ， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $m$ 个属性子集， $\forall X \subseteq U \ , \quad a _ { k } \in C$ ， $\omega$ 是给定相似度阈值,且 $0 \leq \omega \leq 1 , \ 0 \leq \beta < \alpha \leq 1$ ,可知， ${ \overline { { \sum _ { i = 1 } ^ { m } { R _ { i } ^ { ( O , \omega , \beta ) } } } } } ( X ) = \bigcup _ { i = 1 } ^ { m } { \overline { { R _ { i } } } ^ { ( \omega , \beta ) } } ( X )$

证明对 $\forall x \in { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } } ( X ) \iff$

$$
U - \{ x . P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \leq \beta \wedge P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \leq \beta \wedge
$$

$$
\dots \cap P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } \left( x \right) ) \leq \beta , x \in U \}
$$

分

$$
x \in \{ x ; P ( \mathrm { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) > \beta \lor P ( \mathrm { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) > \beta \lor
$$

$$
\dots \lor P ( \mathbf { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) { > } \beta , x \in U \}
$$

$$
\{ x { \cdot } P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) { \succ } \beta , x \in U \} \lor \{ x { : } P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) { \succ } \beta ,
$$

$$
x { \in } U \} \subset \ldots \lor \{ x : P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) { > } \beta , x { \in } U \} \Leftrightarrow
$$

$$
x \in \{ \overline { { R } } _ { 1 } ^ { ( \omega , \beta ) } ( X ) \setminus \overline { { R _ { 2 } } } ^ { ( \omega , \beta ) } ( X ) \lor \ldots \lor \overline { { R _ { m } } } ^ { ( \omega , \beta ) } ( X ) \} \Leftrightarrow
$$

$$
x \in \bigcup _ { i = 1 } ^ { m } { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X )
$$

所以， ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } } ( X ) = \bigcup _ { i = 1 } ^ { m } { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X ) ~ \operatorname { c }$ （

由定理1可知，基于可能度容差关系的乐观多粒度决策粗糙集的上近似是各粒度分类规则下的上近似集合的并。

定义9设 $K = ( U , A = C \cup D , V , f \}$ 是一不完备的区间值决策信息系统， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $m$ 个属性子集，对于 $\forall X \subseteq U \ , \ a _ { k } \in C \ , \ \omega$ 是给定相似度阈值，且 $0 \leq \omega \leq 1$ ，$0 \leq \beta < \alpha \leq 1$ ，则基于可能度容差关系的悲观多粒度决策粗糙集的下近似，上近似和边界区定义为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \alpha ) } ( X ) = \{ x : P ( \mathbf { X } \vert \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \geq \alpha \land P ( \mathbf { X } \vert \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \geq \alpha
$$

$$
\land \dotsc \land P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \geq \alpha , x \in U \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( X ) = U - \{ x . P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \leq \beta \lor P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \leq \beta
$$

$$
\bigtriangledown . . . \bigtriangledown P ( \mathrm { X } \big | \Gamma _ { R _ { m } } ^ { \omega } \left( x \right) ) \leq \beta , x \in U \}
$$

$$
\mathbf { B N } _ { \sum _ { i = 1 } ^ { m } R _ { i } } ^ { ( P , \omega ) } = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { { ( P , \omega , \beta ) } } } } ( X ) - \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { { ( P , \omega , \alpha ) } } } _ { = 1 } ( X )
$$

可以看出，当 $\alpha { = } 1 , \beta { = } 0$ 时，基于可能度容差关系的悲观多粒度决策粗糙集将退化为可能度容差关系下的悲观多粒度粗糙集。

定理2给定一不完备区间值决策信息系统$K = ( U , A = C \cup D , V , f \}$ ， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $\mathbf { \Sigma } _ { m }$ 个属性子集， $\forall X \subseteq U \ , \quad a _ { k } \in C$ ， $\omega$ 是给定相似度阈值，且 $0 \leq \omega \leq 1 , \ 0 \leq \beta < \alpha \leq 1$ ，可知， ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } } ( X ) = \bigcap _ { i = 1 } ^ { m } { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X ) \ \circ$ 证明对 $\forall x \in { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } } ( X ) \iff$ （20

$$
U - \{ x . P ( \mathrm { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \leq \beta \vee P ( \mathrm { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \leq \beta \vee
$$

$$
\dots \lor P ( \mathbf { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \leq \beta , x \in U \} \Leftrightarrow
$$

$$
\begin{array} { r } { x \in \{ x ; P ( \mathrm { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) > \beta \land P ( \mathrm { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) > \beta \land } \end{array}
$$

$$
\dots \wedge P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } \left( x \right) ) { > } \beta , x \in U \} \iff
$$

$$
x \in \{ x . P ( \mathrm { X } \big | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) > \beta , x \in U \} \land \{ x . P ( \mathrm { X } \big | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) > \beta
$$

$$
, x \in { U } \} \land \dotsc \land \{ x : P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) > \beta , x \in { U } \} \Leftrightarrow
$$

$$
x \in \{ \overline { { R } } _ { 1 } ^ { ( \omega , \beta ) } ( X ) \land \overline { { R } } _ { 2 } ^ { ( \omega , \beta ) } ( X ) \land \ldots \land \overline { { R } } _ { m } ^ { ( \omega , \beta ) } ( X ) \} \Leftrightarrow
$$

$$
x \in \bigcap _ { i = 1 } ^ { m } { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X )
$$

所以 ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } } ( X ) = \bigcap _ { i = 1 } ^ { m } { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X )$

由定理1可知，基于可能度容差关系的悲观多粒度决策粗糙集的上近似是各粒度分类规则下的上近似集合的交。

定理3 给定一不完备区间值决策信息系统$K = ( U , A = C \cup D , V , f \}$ ， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $m$ 个属性子集， $\forall X \subseteq U \ , a _ { k } \in C$ ， $\omega$ 是给定相似度阈值,且 $0 \leq \omega \leq 1$ ， $0 \leq \beta < \alpha \leq 1$ ，基于可能度容差关系的多粒度决策粗糙集模型具有如下性质：

$$
\begin{array} { r l } & { \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , o , o , i ) } ( \mathcal { Q } ) } _ { = \lambda _ { i } } = \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , o , i ) } ( \mathcal { Q } ) = \mathcal { Q } } \\ & { \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , o , o ) } ( U ) = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , o , i ) } } } ( U ) = U } _ { \lambda _ { i } } } \\ & { \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , o , o ) } ( \mathcal { Q } ) = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , o , o , i ) } } } ( \mathcal { Q } ) = \mathcal { Q } } _ { = \lambda _ { i } } } \\ & { \underbrace { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , o , o , i ) } ( U ) = \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , o , o , i ) } } } ( U ) = U } _ { = \lambda _ { i } } } \end{array}
$$

证明：由定义7-9易证。

定理4给定一不完备区间值决策信息系统$K = ( U , A = C \cup D , V , f \}$ ， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $m$ 个属性子集， $\forall X \subseteq U \ , \quad a _ { k } \in C$ ， $\omega$ 是给定属性相似度阈值且 $0 \leq \omega \leq 1$ ， $0 \leq \beta < \alpha \leq 1$ ，可知

a) ${ \underline { { \sum _ { i = 1 } ^ { m } } } } R _ { i } ^ { ( O , \omega , \alpha ) } ( X ) \supseteq { \underline { { R _ { i } } } } ^ { ( \omega , \alpha ) } ( X )$ b) ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } } ( X ) \subseteq { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X )$ c) ${ \underline { { \sum _ { i = 1 } ^ { m } } } } R _ { i } ^ { ( P , \omega , \alpha ) } ( X ) \subseteq { \underline { { R _ { i } } } } ^ { ( \omega , \alpha ) } ( X )$ d) （204号 ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } } ( X ) \supseteq { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X )$

其中， $i = \{ 1 , 2 , 3 , . . . m \}$

证明a）对 $x \in \underline { { R } } _ { i } ^ { \ ( \omega , \alpha ) } ( X ) , i = \{ 1 , 2 , 3 , . . . m \} \Leftrightarrow$

$$
x \in X , P ( \mathrm { X } | \Gamma _ { R _ { i } } ^ { \omega } \left( x \right) ) \geq \alpha
$$

$$
\Rightarrow x \in X , P ( \mathbf { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \geq \alpha \setminus P ( \mathbf { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \geq \alpha \vee
$$

$$
\dots \lor P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \geq \alpha
$$

$$
\implies x \in \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( X )
$$

所以， ${ \underline { { \sum _ { i = 1 } ^ { m } } } } R _ { i } ^ { ( O , \omega , \alpha ) } ( X ) \supseteq { \underline { { R _ { i } } } } ^ { ( \omega , \alpha ) } ( X )$

b）对 $x \in { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } } ( X ) , i = \{ 1 , 2 , 3 , . . . m \} \Leftrightarrow$

$$
\begin{array} { r } { U - \{ x { \cdot } P ( \mathrm { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \leq \beta \wedge P ( \mathrm { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \leq \beta \wedge } \end{array}
$$

$$
\dots \wedge P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \leq \beta , x \in U \}
$$

$$
\Rightarrow x \in X , \left\{ P ( \mathrm { X } | \Gamma _ { R _ { 1 } } ^ { \omega } ( x ) ) \geq \beta \vee P ( \mathrm { X } | \Gamma _ { R _ { 2 } } ^ { \omega } ( x ) ) \geq \beta \vee \right.
$$

$$
\dots \lor P ( \mathrm { X } | \Gamma _ { R _ { m } } ^ { \omega } ( x ) ) \ge \beta \} \Rightarrow \ x \in { \overline { { R } } } _ { i } ^ { ( \omega , \beta ) } ( X )
$$

所以， ${ \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } } ( X ) \subseteq { \overline { { R _ { i } } } } ^ { ( \omega , \beta ) } ( X ) ~ ^ { }$ 同理可证（3）、（4)。

定义10设 $K = ( U , A = C \cup D , V , f \}$ 是一不完备的区间值决策信息系统， $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { m } \}$ 是条件属性集 $c$ 上的 $m$ 个属性子集，对于 $\forall X \subseteq U$ ， $a _ { k } \in C$ ， $\omega$ 是属性相似度阈值，且$0 \leq \omega \leq 1$ ， $0 \leq \beta < \alpha \leq 1$ ，则集合 $\boldsymbol { x }$ 在乐观与悲观条件下的分类精度分别定义为

$$
\begin{array} { r } { \alpha _ { R } ^ { ( O , \alpha , \beta ) } ( X ) = \left| \frac { \displaystyle \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \alpha , \alpha ) } ( X ) } { \displaystyle \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \alpha , \beta ) } ( X ) } \right| } \\ { \alpha _ { R } ^ { ( P , \alpha , \beta ) } ( X ) = \frac { \displaystyle \left| \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \alpha , \alpha ) } ( X ) \right| } { \displaystyle \left| \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \alpha , \beta ) } ( X ) \right| } } \end{array}
$$

分类质量分别定义为

$$
\gamma _ { R } ^ { ( O , \alpha ) } ( X ) = \frac { \displaystyle \left| \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( X ) \right| } { \displaystyle \left| U \right| }
$$

$$
\gamma _ { R } ^ { ( P , \alpha ) } ( X ) = \frac { \displaystyle \left| \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \alpha ) } ( X ) \right| } { | U | }
$$

# 3 实例分析

表1为不完备区间值决策信息系统，其中C={a,a,a，a4,a,a,a,a,a,ao}为条件属性集合，D={d}为决策属性集合， $U = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { 2 0 } \}$ 为论域，设决策信息系统的条件属性子集族为 ${ \cal R } = \{ R _ { 1 } , R _ { 2 } , R _ { 3 } , R _ { 4 } \} = \{ \{ a _ { 1 } , a _ { 2 } \} , \{ a _ { 3 } , a _ { 4 } , a _ { 5 } \} , \{ a _ { 6 } , a _ { 7 } , a _ { 8 } \} ,$ $\{ a _ { 9 } , a _ { 1 0 } \} \}$ 。本文以 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9$ 为例，调整属性相似度阈值 $\omega$ ，获取不同情况下基于可能度容差关系的多粒度决策粗糙集的上下近似集。

a）根据决策属性 $D$ 划分决策类如下：

$$
U / I N D ( \{ d \} ) = \{ D _ { 1 } , D _ { 2 } \} = \{ \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 7 } , x _ { 9 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } ,
$$

$$
x _ { 1 7 } , x _ { 1 9 } , x _ { 2 0 } \} , \{ x _ { 3 } , x _ { 5 } , x _ { 8 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 4 } , x _ { 1 6 } , x _ { 1 8 } \} \}
$$

b)条件属性子集族R={R,R,R,R}={{a,a}{a,a4（204号 $, a _ { 5 } \nmid \{ a _ { 6 } , a _ { 7 } , a _ { 8 } \} , \{ a _ { 9 } , a _ { 1 0 } \} \}$ ，根据定义4\~9，计算基于不完备区间值信息系统的多粒度决策粗糙集的下近似和上近似分别如下：

<html><body><table><tr><td>U</td><td>a1</td><td>a2</td><td>a3</td><td>a4</td><td>a5</td><td>a6</td><td>a7</td><td>a8</td><td>a9</td><td>a10</td><td>d</td></tr><tr><td>x1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[3.22,4.87][7.80,9.42][5.27,7.14][1.69,3.68][8.53,9.670][2.21,4.08][4.43,6.07][7.47,8.610][3.96,4.58][61,7.76]</td><td></td><td></td><td>1</td></tr><tr><td>x2</td><td>[4.21,5.18]</td><td>*</td><td>[5.23,6.45][1.63,3.65][8.97,10.59][2.17,3.39][4.05,6.09][7.91,9.530]</td><td></td><td></td><td></td><td></td><td></td><td>*</td><td>[7.10,8.07]</td><td>1</td></tr><tr><td>x3</td><td></td><td>[3.00,4.24][8.17,9.34][5.31,7.02]</td><td></td><td>*</td><td>[7.87,9.610] [2.25,3.96]</td><td></td><td>*</td><td>[6.81,8.550] [3.33,4.50] [5.89,7.43]</td><td></td><td></td><td>2</td></tr><tr><td>x4</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[3.69,5.47][8.10,9.40][5.62,7.40][1.52,.75][8.89,10.27][2.56,4.40][3.96,6.19][7.83,9.210][3.26,4.56][6.88,8.66]</td><td></td><td></td><td>1</td></tr><tr><td>x5</td><td>[3.01,5.64][8.15,9.27]</td><td></td><td>*</td><td>[1.54,3.63] [8.56,9.890]</td><td></td><td>*</td><td></td><td>[3.98,6.07][7.50,9.830] [3.31,4.43] [5.98,8.61]</td><td></td><td></td><td>2</td></tr><tr><td>x6</td><td>*</td><td></td><td></td><td></td><td></td><td></td><td></td><td>[8.01,9.13][6.08,6.87][1.97,3.71][9.08,10.31][3.01,3.80][4.41,6.15][9.00,10.25][3.17,4.29]</td><td></td><td>*</td><td>1</td></tr><tr><td>x7</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[3.15,4.59][8.26,9.47][5.62,6.98][165,3.81][8.34,10.21][2.55,3.93][4.066.22][8.28,10.15][3.42,4.63][6.12,7.56]</td><td></td><td></td><td>1</td></tr><tr><td>x8</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[2.88,4.79][8.10,9.19][5.47,7.04][1.23,3.46][8.41,10.25][2.73,4.47][3.64,5.87][8.65,10.33][3.26,4.35][5.85,7.76]</td><td></td><td></td><td>2</td></tr><tr><td>x9</td><td></td><td>[3.41,4.81] [7.41,8.78][5.86,6.77] [1.84,3.58]</td><td></td><td></td><td>*</td><td>[3.12,4.03] [4.25,5.99]</td><td></td><td>*</td><td>[2.57,3.94][6.38,7.3]</td><td></td><td>1</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x10[3.11,5.27][7.52,9.88][5.30,676][1.12,181][8.21,9.690][2.56,402][3.53,422][8.29,9.770][2.68,5.04][67.]</td><td></td><td></td><td>2</td></tr><tr><td></td><td>x 11[4.23,5.20]</td><td>*</td><td></td><td></td><td></td><td></td><td></td><td>[5.13,6.35][1.71,3.70][8.82,10.47][2.29,3.41][4.15,6.19][7.70,9.310]*</td><td></td><td>[7.18,8.15]</td><td>1</td></tr><tr><td></td><td>x12[3.03,4.27][8.20,9.37][5.30,7.01]</td><td></td><td></td><td>*</td><td>[7.67,9.410] [2.23,3.94]</td><td></td><td>*</td><td>[6.80,8.530] [3.23,4.30] [5.77,7.21]</td><td></td><td></td><td>2</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x13[3.71,5.49][.12,9.46][5.52,7.30][162,3.85][8.7,1001][2.59,4.43][3.92615][7.63,9.020][3.164.30][6.92,8.78]</td><td></td><td></td><td>√</td></tr><tr><td></td><td>x 14[3.11,5.74] [8.23,9.36]</td><td></td><td>*</td><td>[1.52,3.61] [8.46.9.790]</td><td></td><td>*</td><td></td><td>[3.71,5.87][7.40,9.730] [3.41,4.63] [5.68,8.41]</td><td></td><td></td><td>2</td></tr><tr><td>x 15</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[8.11,9.23][6.09,6.88][1.92,3.66][9.18,10.41][3.11,4.01][4.52,6.26][9.12,10.35][3.27,4.39]</td><td></td><td>*</td><td>1</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x16[3.0,4.91][8.15,9.24][5.57,7.14][1.27,3.50][8.42,10.26][2.63.4.12][3.74,5.96][8.5,10.23][3.16,4.05][5.72,7.63]</td><td></td><td></td><td>2</td></tr><tr><td></td><td>x 17[3.42,4.34][7.61,8.98][5.76,6.57][1.74,3.48]</td><td></td><td></td><td></td><td></td><td>[3.23,4.13] [4.15,5.89]</td><td></td><td>*</td><td>[2.67,4.05] [6.5,7.42]</td><td></td><td>1</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x18[3.12,4.28][7.5,9.91][5.40,6.86][1.11,1.8][8.23,9.890][2.46,3.9][3.43,402][8.19,9.570][2.57,4.93][6.18,7.14]</td><td></td><td></td><td>2</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x19[3.17,4.61][8.16,9.37][5.52688][1.45,3.61][8.36,1026][2.59,397][4.176.33][838,1025][3.52,4.73][625,76]</td><td></td><td></td><td></td></tr><tr><td></td><td>x 20 [4.25,5.22]</td><td>*</td><td></td><td></td><td></td><td></td><td></td><td>[5.21,6.45] [1.73,3.72] [8.90,10.55][2.30,3.42] [4.15,6.21][7.75,9.360]</td><td>*</td><td>[7.19,8.16]</td><td>1</td></tr></table></body></html>

(a）当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9 ~ , ~ \omega = 0 . 7$ 时，基于可能度容差关系的乐观多粒度决策粗糙集的上下近似求得为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 6 } , x _ { 1 0 } , x _ { 1 1 } , x _ { 1 5 } , x _ { 1 8 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { 1 9 } , x _ { 2 0 } \}
$$

$$
{ \sum } _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( D _ { 2 } ) = \{ x _ { 1 0 } , x _ { 1 8 } \} 
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 1 } , x _ { 3 } , x _ { 6 } , x _ { 7 } , x _ { 8 } , x _ { 1 0 } , x _ { 1 2 } ,
$$

$$
x _ { 1 5 } , x _ { 1 6 } , x _ { 1 8 } , x _ { 1 9 } \}
$$

基于可能度容差关系的悲观多粒度决策粗糙集的上下近似求得为

$$
{ \sum } _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( P , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 1 1 } \} 
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } , x _ { 9 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 4 } , x _ { 1 7 } , x _ { 2 0 } \}
$$

$$
{ \sum _ { i = 1 } ^ { m } } R _ { i } ^ { ( P , \omega , \alpha ) } ( D _ { 2 } ) = \{ x _ { 1 0 } , x _ { 1 8 } \} 
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 8 } , x _ { 9 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 6 } , x _ { 1 7 } , x _ { 1 8 } \}
$$

(b）当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9 ~ , ~ \omega = 0 . 8$ 时，基于可能度容差关系的乐观多粒度决策粗糙集的上下近似求得为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , x _ { 6 } , x _ { 7 } , x _ { 9 } , x _ { 1 0 } , x _ { 1 1 } ,
$$

$$
x _ { 1 2 } , x _ { 1 3 } , x _ { 1 4 } , x _ { 1 5 } , x _ { 1 7 } , x _ { 1 8 } , x _ { 1 9 } , x _ { 2 0 } \}
$$

$$
{ \underline { { \sum _ { i = 1 } ^ { m } } } } R _ { i } ^ { ( O , \omega , \alpha ) } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( O , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 8 , } x _ { 9 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 6 } , x _ { 1 7 } , x _ { 1 8 } \}
$$

基于可能度容差关系的悲观多粒度决策粗糙集的上下近似求得为

$$
{ \sum } _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( P , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 1 1 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } , x _ { 6 } , x _ { 7 } , x _ { 9 } , x _ { 1 1 } , x _ { 1 3 } ,
$$

$$
x _ { 1 4 } , x _ { 1 5 } , x _ { 1 7 } , x _ { 1 9 } , x _ { 2 0 } \}
$$

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \alpha ) } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } \}
$$

$$
\begin{array} { r } { \overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 8 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 6 } , x _ { 1 8 } \} } \end{array}
$$

(c）当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9 ~ , ~ \omega = 0 . 8 5$ 时，基于可能度容差关系的乐观多粒度决策粗糙集的上下近似求得为

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( O , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } , x _ { 2 0 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } , x _ { 6 } , x _ { 7 } , x _ { 9 } , x _ { 1 0 } , x _ { 1 1 } ,
$$

$$
x _ { 1 3 } , x _ { 1 4 } , x _ { 1 5 } , x _ { 1 7 } , x _ { 1 8 } , x _ { 1 9 } , x _ { 2 0 } \}
$$

$$
\sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \alpha ) } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 7 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } , x _ { 1 9 } \}
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( O , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 1 } , x _ { 3 } , x _ { 7 } , x _ { 8 } , x _ { 9 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 6 } ,
$$

$$
x _ { 1 7 } , x _ { 1 8 } , x _ { 1 9 } , x _ { 2 0 } \}
$$

基于可能度容差关系的悲观多粒度决策粗糙集的上下近似求得为

$$
{ \sum } _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( P , \omega , \alpha ) } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 4 } , x _ { 1 1 } , x _ { 1 3 } \} 
$$

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { \scriptscriptstyle ( P , \omega , \beta ) } } } ( D _ { 1 } ) = \{ x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 9 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } , x _ { 1 7 } \}
$$

$$
{ \sum _ { i = 1 } ^ { m } } R _ { i } ^ { _ { ( P , \omega , \alpha ) } } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } \}
$$

$$
\gamma _ { o } ^ { ( \alpha , \omega ) } ( D ) = \frac { \left| \{ x _ { 2 } , x _ { 6 } , x _ { 1 0 } , x _ { 1 1 } , x _ { 1 5 } , x _ { 1 8 } \} \bigcup \{ x _ { 1 0 } , x _ { 1 8 } \} \right| } { \left| \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { 2 0 } \} \right| } = \frac { 2 } { 5 }
$$

(b）当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9 ~ , ~ \omega = 0 . 8$ 时

$$
\gamma _ { O } ^ { ( \alpha , \omega ) } ( D ) = \frac { \big | \{ x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } \} \bigcup \{ x _ { 3 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } \} \big | } { \big | \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { 2 0 } \} \big | } = \frac { 1 } { 2 }
$$

（c）当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9 ~ , ~ \omega = 0 . 8 5$ 时利用文献[16所构建的粗糙方法计算得到决策类的分类质量为$2 9 . 5 5 \%$ ， $3 6 . 5 \%$ ， $42 \%$ ；利用文献[17]所构建的粗糙集方法计算得到决策类的分类质量为 $2 6 . 3 3 \%$ ， $3 7 . 5 \%$ ， $5 5 . 7 5 \%$ ；利用文献[24]所构建的粗糙集方法计算得到决策类的分类质量为 $32 . 5 \%$ $46 \%$ ， $57 . 5 \%$ 。结果表明，本文构建的基于可能度相似容差关系的多粒度决策粗糙模型在处理不完备区间值决策信息系统时，相比于文献[16,17,24]构建的不完备区间值决策信息系统下的粗糙模型，分类质量有所提高。这是由于本文构建的新模型不仅借鉴了多粒度决策粗糙集能够从多层次、多角度综合考虑不同属性子集的优点，更能通过调整阈值 $\omega$ ，使模型具有一定的容错能力，同时充分考虑属性子集的特征，使得对象分类更为准确。

$$
\gamma _ { o } ^ { ( \alpha , \omega ) } ( D ) = \frac { \left| \left\{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 6 } , x _ { 1 1 } , x _ { 1 3 } , x _ { 1 5 } , x _ { 2 0 } \right\} \bigcup \left\{ x _ { 3 } , x _ { 7 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 8 } , x _ { 1 9 } \right\} \right| } { \left| \left\{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { 2 0 } \right\} \right| } = \frac { 3 } { 4 }
$$

本文融合可能度容差关系和多粒度决策粗糙集的各自优点，在不完备区间值决策信息系统中提出一种基于可能度容差关系的多粒度决策粗糙模型，给出了乐观多粒度决策粗糙集和悲观多粒度决策粗糙集两种模型的完整定义，并着重讨论了基本性质和度量参数。其中，针对对象的划分探究了属性相似度阈值变化对分类质量的影响。通过 $\omega$ 的不同取值可以得到程度不同的对象分类，使得本文提出的模型具有一定的稳定性和灵活性。接下来，将进一步研究决策规则获取和属性约简等问题。

# 4 结束语

c)以基于可能度容差关系的乐观多粒度决策粗糙集为例，求得三种情况下决策类的分类质量：

以 $\alpha = 0 . 7 5$ ， $\beta = 0 . 4 9$ 为例，求得3种不同属性相似度阈值情况下，基于可能度容差关系的乐观多粒度决策粗糙集的决策类分类质量分别为 $40 \%$ 、 $50 \%$ 和 $7 5 \%$ 。对比发现，固定阈值$\alpha$ 和 $\beta$ ，随着给定属性相似度阈值 $\omega$ 的不断变大，不完备区间值决策信息系统中的对象越能被正确分类，当 $\omega$ 大到一定程度所有的对象都能被正确分类。这表明调整阈值 $\alpha \cdot \beta$ 和 $\omega$ ，在一定程度上可降低噪声的影响，使模型具有一定的容错能力和很强的分类能力。

为进一步验证模型能够更有效处理含有不完备区间值的决策信息系统，当 $\alpha = 0 . 7 5 ~ , ~ \beta = 0 . 4 9$ ，分别令 $\omega$ 为0.7,0.8,0.85,

$$
\overline { { \sum _ { i = 1 } ^ { m } R _ { i } ^ { ( P , \omega , \beta ) } } } ( D _ { 2 } ) = \{ x _ { 3 } , x _ { 8 } , x _ { 1 0 } , x _ { 1 2 } , x _ { 1 6 } , x _ { 1 8 } \}
$$

# 参考文献：

[1]Chen Yumin, Zhang Zunjun,Zheng Jianzhong,et al.Genes selection for tumor classification using neighborhood rough sets and entropy measures [J].Journal of Biomedical Informatics,2017,67: 59-68.   
[2]Kumar R S,Bera S.Approximation of rough soft set and its application on lattice [J].Fuzzy Information and Engineering,2015,7(3): 379-387.   
[3]Aggarwal M.Rough information set and its applications in decision making [J].IEEE Trans on Fuzzy Systems,2017,25 (2): 264-276.   
[4]Asit Das K, Shampa S,Bhata,et al.A group in cremental feature selection for classification using rough set theory based on genetic algorithm [J]. Applied Soft Computing,2018,65: 400-411.   
[5]Pawlak Z.Rough sets [J].International Journal of Computer and Information Science,1982,11(5): 341-356.   
[6]Pawlak Z. Rough sets decision algorithms and Bayes'theorem [J]. Europe Journal of Operational Research,2002,136:181-189.   
[7]Qiu Junda,Li Lei.A New approach for multiple attribute group decision making with interval-valued in tuittionistic fuzzy information [J].Applied Soft Computing,2017,61: 111-121.   
[8]Tan Anhui,Wu Weizhi,Li Jinjin,Lin Guoping.Evidence theory based numerical characterization of multi grainulation rough sets in incomplete information systems [J].Fuzzy Sets and Systems,2016,294:18-35.   
[9]YU Jianhang,Chen Minghao,Xu Weihua.Dynamic computing rough approximations approach to time-evolving information granule interval

valued ordered information system [J].Applied Soft Computing,2017,60: 18-29.

[10] Wan Shuping,Wang Feng,Dong Jiuying.Additive consistent intervalvalued atanassov intuitionistic fuzzy preference relation and likelihood comparison algorithm based group decision making [J]. European Journal of Operational Research,2016,263 (2): 571-582.   
[11] Yang Xibei, Qi Yong,Yu Dongjun,et al. -Dominance relation and rough sets in interval valued information systems [J].Information Sciences,2015,294: 334-347.   
[12] Dai Jianhua.Wei Bingjie,Zhang Xiaohonh,et al.Uncertainty measurement for incomplete interval valued information systems based on $\mathfrak { a }$ -weak similarity[J].Knowledge-Based Systems,2017,136:159-171..   
[13] Palmisano G O,LoisiR V,Ruggiero G. Using analytic network process and dominance based rough set approach for sustainable requalification of traditional farm buildings in Southern Italy [J].Land Use Policy,2O16,59: 95-100.   
[14]Peters G,Poon S.Analyzing IT business values:A dominance based rough sets approach perspective Research article [J].Expert Systems with Applications,2016,38 (9): 11120-11128.   
[15] Qian Jin,Dang Chuangyin,Yue Xiaodong,et al.Attribute reduction for sequential three-way decisions under dynamic granulation [J].International Journal of Approximate Reasoning,2017,85:196-216.   
[16]曾玲，何普彦，付敏．不完备区间值信息系统的粗糙集约简算法[J]. 南京理工大学学报,2013,37(4):524-529.(Zeng Ling,He Puyan,Fu Min. Attribute reduction algorithm based on rough set in incomplete intervalvalued information system[J].Journal ofNanjing University of Science and Technology,2013,37(4):524-529.)   
[17]张鑫，李续武，路艳丽，陈玉金．基于不完备区间值信息系统的决策粗 糙集[J].计算机应用研究,2017,34(1):110-113,122.(Zhang Xin,Liu Xuwu,Lu Yanli,Chen Yujin. Decision-theoretic rough set based on incomplete interval-valued information system [J].Application Research of Computers,2017,34(1): 110-113,122.)   
[18] Dai Jianhua,Wang Wentao,Mi Jusheng.Uncertainty measurement for interval-valued information systems [J]. Information Sciences,2013,251: 63-78.   
[19] Qian Yuhua,Zhang Hu,Sang Yanli,et al. Multigranulation decision theoretic rough sets [J]. International Journal of Approximate Reasoning, 2014,55 (1): 225-237.   
[20] Lin Guoping,Liang Jiye,Qian Yuhua.An information fusion approach by combining multigranulation rough sets and evidence theory[J]. Information Sciences,2015,314:184-199.   
[21] Zhang Ming,Cheng Ke,Yang Xibei,et al.Multigranulation rough set based on weighted granulations [J]. Control and Decision,2015,30 (2): 222-228.   
[22] Qian Yuhua.Local multigranulation decision theoretic rough sets [J]. International Journal of Approximate Reasoning,2017,82:119-137.   
[23] Sun Bingzhen,Ma Weimin, Qian Yuhua.Multigranulation fuzzy rough set over two universes and its application to decision making[J].KnowledgeBased Systems,2017,123:61-74.   
[24] Sang Yanli,Liang Jiye,Qian Yuhua.Decision-theoretic rough sets under dynamic granulation [J].Knowledge-Based Systems,2016,91: 84-92.