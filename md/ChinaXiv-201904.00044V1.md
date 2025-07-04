# 不完备混合决策系统的三支决策模型与规则获取方法

钱文彬a,b，彭莉莎a，王映龙‘，段德林b(江西农业大学 a.计算机与信息工程学院;b.软件学院，南昌 330045)

摘要：现有三支决策主要针对各类完备信息系统或不完备单一型信息系统进行研究，而现实应用领域中数据往往呈现不完备性和复杂性等特征，为此，构建面向不完备混合决策系统的三支决策模型与规则获取方法。首先，计算不完备混合数据的完备邻域容差类，并将其代替等价类计算三支决策模型的条件概率；然后，根据扩展的损失函数区间概念获取各对象在“乐观"“折中"和"悲观"决策下的不同阈值，进而针对不完备混合决策系统构造三种决策风险下的三支决策模型；最后，通过理论分析和医疗诊断实例详细分析了算法的有效性和可解释性，并通过实验比较和分析可知：所构模型较其他已有模型的分类过程更加合理有效，同时该模型也扩充了三支决策模型和知识发现的理论与应用研究。

关键词：粗糙集；三支决策；不完备混合数据；规则获取；粒计算 中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2018.10.0806

Three-way decisions model and rule acquisition method for incomplete composite decision system

Qian Wenbina, b,Peng Lishaa†, Wang Yinglonga, Duan Delinb (a.Schoolof Computer& Information Engineering,b.Schoolof Software,Jiangxi Agricultural University,Nanchang 330045, China)

Abstract:The existing three-waydecisions mainly focus onvarious types ofcomplete information systems or incomplete single-type information systems,while the datain thereal application fieldsoften exhibit incompletenessandcomplexity. Therefor this paper proposed the three-waydecisions model andrule acquisition method for incomplete composite decision system basedona newcomplete neighborhood tolerancerelation.First，the algorithm designed the new complete neighborhood tolerance classes underthe incomplete mixeddata,whichcan substitute forequivalenceclasses tocalculate theconditional probabilities intheclassicalthree-waydecisions model.Then,thealgorithmalso improvedtheconceptof the loss function interval to obtaindiferent thresholds of each objectunder the“optimistic”，“compromising”and “pessimistic”decisions and constructed there three-way decisions modelsand rule acquisition method under three decision-making risks forthe incompletecomposite decisionsystem.Finaly,asriesoftheoretical analysisandamedical diagnosis exampleanalyzed thevalidityand interpretableof thealgorithm indetail,andtheexperimentalresults basedon diferent datasets show thatthe proposed model outperformed the state-of-the-art models interms ofclasification process and expand the theory and application of three-way decisions and knowledge discovery.

Key words: rough set; three-way decisions; incomplete composite data; rule acquisition; granular computing

# 0 引言

Yao教授提出的三支决策[1,2]提供了对粗糙集理论的深入理解和其在粒计算中的实际应用，现已成为知识发现领域中一个重要的研究方向。三支决策的延迟策略可一定程度提高分类准确率和降低误分类损失。近几年，三支决策扩展了对知识系统的研究范围，并在数据分析和处理中发挥着关键作用，在理论扩充和实际应用也获得极大发展。理论扩充主要有三支聚类[3]、三支概念分析[4]、三支属性约简[5,6]、序贯三支决策[7]、三支 $+  { \mathrm { X } }$ （X：模糊集、区间集等）[8\~10]等。应用领域主要有推荐系统[11]、人脸识别[12]、恶意软件分析[13]和垃圾邮件过滤[14]等。

在实际应用中，由于数据采集限制或测量误差等原因，使得在知识获取时往往存在数据不完备的现象。经典粗糙集无法直接处理不完备数据，现有针对不完备符号型数据的处理方法有基于容差关系[15]、非对称相似关系[16]、限制容差关系[17]、完备容差关系[18]、改进的完备容差关系[19]等多种扩充粗糙集模型，而针对不完备连续型信息系统的处理方法则大多基于邻域容差关系模型。在对不完备符号型信息系统的三支决策研究中，Liu等人[20]利用概率分布计算近似类，并利用区间概念计算各对象的三支阈值，为该类不完备符号型信息系统构建了一种新的三支决策模型。在现实应用领域中，一个信息系统中同时存在多种类型的数据是一种普遍现象。例如，在高校信息系统中，学生所选课程和任课老师等是符号型数据，学号和成绩等则是连续型数据；在医疗检测结果中，性别和血型等是符号型数据，血糖和血压等是连续型数据，包含伴有不同程度缺失的此类数据的系统都是不完备混合型信息系统。现有针对不完备混合信息系统的处理有拆分处理法和通用处理法，姚晟等人[21]通过考虑属性值的概率分布分别为不完备的连续型数据和离散型数据构造不确定性度量方法；Zhao等人[22]提出邻域容差关系用于计算不完备混合数据的近似类，并构建邻域条件熵作为评估标准进行属性约简；然而在三支决策理论模型中，对于同时包含连续型、整型和符号型数据的不完备混合决策系统的研究相对尚少。

为此，本文为不完备混合决策系统构建三支决策模型和规则获取方法。对于条件概率的计算，以改进的完备容差关系为基础，定义一种新的完备邻域容差关系并将其用于计算不完备混合数据的近似类，进而有效替代等价类计算条件概率；针对阈值的获取，由于未知属性值的不确定性和不稳定性，每个对象都应设置不同的阈值，为此，改进文献[20]中近似类的损失函数区间值获取方法，首先为各对象设置损失函数区间，然后通过改进“乐观”“折中”和“悲观”损失函数具体值设置方式计算各对象的“乐观”“折中”和“悲观”三支阈值。本文模型的主要优势是能利用通用的数学范式计算同时包含不完备符号型、整型和连续型数据的对象的近似类，且可根据三种风险偏好分别为各不完备对象设置不同的阈值，进而制定三种风险偏好下的三支决策规则。通过理论分析和医疗诊断的实例证明了本文所构模型的有效性和可行性，且通过UCI数据集的实验分析了参数的变化对该模型的影响，对比邻域容差关系等其他三种方法，本文方法的分类过程更合理，具有更好的可解释性和扩展性。

# 1 基础知识

给定不完备混合决策系统 $I D S = U , C , D$ ，其中： $U$ 为对象集； $c$ 为条件属性集； $D$ 为决策属性。令 $\forall B \subseteq C$ ，且 $B = B _ { C } \cup B _ { N }$ ，$B _ { c }$ 为符号型属性子集， $B _ { N }$ 为连续型属性子集。预先设定“\*”代表未知属性值(空值)，通常未知属性值分为遗漏值和缺失值，对于遗漏值而言，未知值只是遗漏但确实存在，且可与任意同类属性值进行比较，即各对象具有潜在的完备信息；而对于缺失值而言，未知值可能是不可获取的或者根本不存在的数据，不能与其他属性值相比较。本文只对遗漏值进行研究。

为处理不完备混合决策系统中的连续型数据，将邻域概念用于容差关系、限制容差关系、完备容差关系和改进的完备容差关系下的近似求解。

定义 $\mathbf { 1 } ^ { [ 5 ] }$ 给定不完备混合决策系统 $I D S = U , C , D$ ，设混合属性子集 $B \subseteq C$ ， $\forall a _ { k } \in B$ ， $a _ { k } \left( x \right)$ 和 $a _ { k } \left( y \right)$ 分别表示对象 $x$ 和 $y$ 在属性 $a _ { k }$ 上的属性值，则对 $\forall x , y \in U$ ，邻域距离函数定义为

$$
{ \Delta } _ { B } \left( x , y \right) = \left( \sum _ { k = 1 } ^ { n } \left| a _ { k } \left( x \right) - a _ { k } \left( y \right) \right| ^ { p } \right) ^ { 1 / p }
$$

其中：当 $p = 1$ 时， $\Delta _ { B } \left( x , y \right)$ 为曼哈顿距离；当 $p { = } 2$ 时， $\Delta _ { B } \left( x , y \right)$ 为欧氏距离。

# 1.1邻域容差关系

在容差关系[15]下，“\*”与任意值相等。结合邻域概念定义邻域容差关系：

定义2给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall B \subseteq C$ ，$B = B _ { C } \cup B _ { N }$ ， $\delta$ 为邻域参数，则对 $\forall x , y \in U$ 在 $B$ 下的邻域容差关系定义为

$$
\begin{array} { r } { N T _ { B } ( x , y ) = \{ ( x , y ) \in U ^ { 2 } \mid \forall _ { a _ { k } \in B } ( \forall ( a _ { k } ( x ) = ^ { * } \setminus a _ { k } ( y ) = ^ { * }   } \\ {   ( a _ { k } \in B _ { N }  \Delta _ { a _ { k } } ( x , y ) = 0 ) \wedge ) ) \} } \end{array}
$$

$N T _ { B }$ 满足自反性和对称性，但不满足传递性。对 $\forall x \in U$ 在混合属性子集 $B$ 下的邻域容差类定义为

$$
N T _ { B } \left( x \right) = \left\{ y \in U \middle | y \in N T _ { B } \left( x , y \right) \right\}
$$

定义3给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall X \in U$ ，则在混合属性子集 $B$ 下，基于邻域容差关系的三支决策规则定义为

若 $\alpha \leq P ( X | N T _ { B } ( x ) ) \leq 1$ ，则 $x \in P O S _ { B } ^ { N T } \left( X \right)$ 若 $\beta < P ( X | N T _ { B } ( x ) ) < \alpha$ ，则 $x \in B N D _ { B } ^ { N T } \left( X \right)$ 若 $0 \le P ( X | N T _ { B } ( x ) ) \le \beta$ ，则 $x \in N E G _ { B } ^ { N T } \left( X \right)$

其中： $P ( X \vert N T _ { B } ( x ) ) = \frac { \left. X \cap N T _ { B } ( x ) \right. } { \left. N T _ { B } ( x ) \right. }$ ，为 $N T _ { B }$ 属于 $\boldsymbol { \cal X }$ 的条件概率；  
$\alpha$ 和 $\beta$ 为三支决策阈值。

仔细分析发现，在邻域容差关系下，认为 $\scriptstyle 6 6 * 7 ^ { 9 }$ 与任意属性值都相似或相等，虽然这种方式几乎不会影响对缺失数据较少的信息系统的划分，但会将那些拥有较多未知属性值的对象也划分到一个邻域容差类中，且对象的未知属性值越多，被划分到同一个类中的概率越大。例如，对象$x = ( 0 , ^ { * } , 0 . 1 , ^ { * } , 0 . 4 , ^ { * } , 0 . 7 , ^ { * } , 1 )$ 与对象 $y = ( ^ { * } , 1 , ^ { * } , 0 . 8 , ^ { * } , 0 . 5 , ^ { * } , 0 . 2 , ^ { * } )$ ，因为这两个对象实际上相似的概率很小，所以这种划分方式过于宽松，划分粒度过粗。

# 1.2限制邻域容差关系

限制容差关系[17]稍微弥补了容差关系[15]和相似关系[16]的不足。下面结合邻域概念定义限制邻域容差关系：

定义4给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall B \subseteq C$ ，$B = B _ { C } \cup B _ { N }$ ， $\delta$ 为邻域参数，则对 $\forall x , y \in U$ 在 $B$ 下的限制邻域容差关系定义为

$$
\begin{array} { r } { N L _ { B } ( x , y ) = \{ ( x , y ) \in U ^ { 2 } \middle | \forall _ { a _ { k } \in B } ( \begin{array} { c } { a _ { k } ( x ) = ^ { * } \vee a _ { k } ( y ) = ^ { * } } \\ { ( P _ { B } ( x ) \cap P _ { B } ( y ) \neq \emptyset ) \land } \\ { ( a _ { k } \in B _ { C }  \Delta _ { a _ { k } } ( x , y ) = 0 ) \land } \\ { ( a _ { k } \in B _ { N }  \Delta _ { a _ { k } } ( x , y ) \leq \delta ) } \end{array} ) ) \} } \end{array}
$$

其中： $P _ { \scriptscriptstyle B } \left( x \right) = \{ a _ { \boldsymbol k } \vert a _ { \boldsymbol k } \in { \cal B } \land a _ { \boldsymbol k } \left( { \boldsymbol x } \right) \neq \ast \}$ ， $N L _ { _ B }$ 满足自反性和对称性，但不满足传递性。对 $\forall x \in U$ 在混合属性子集 $B$ 下的限制邻域容差类定义为

$$
N L _ { B } \left( x \right) = \left\{ y \in U \middle | y \in N L _ { B } \left( x , y \right) \right\}
$$

定义5给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall X \in U$ ，则在混合属性子集 $B$ 下， $X$ 基于限制邻域容差关系的三支决策规则定义为

若 $\alpha \leq P ( X | N L _ { \mathit { B } } ( x ) ) \leq 1$ ，则 $x \in P O S _ { B } ^ { N L } \left( X \right)$ 若 $\beta < P ( X | N L _ { B } \left( x \right) ) < \alpha$ ，则 $x \in B N D _ { B } ^ { N L } \left( X \right)$ （204号 若 $0 \le P ( X | N L _ { B } ( x ) ) \le \beta$ ，则 $x \in N E G _ { B } ^ { N L } ( X )$

其中： $P ( X | N L _ { B } ( x ) ) = \frac { \left| X \bigcap { N L _ { B } \left( x \right) } \right| } { \left| N L _ { B } \left( x \right) \right| }$ 为 $N L _ { B } \left( x \right)$ 属于 $\boldsymbol { \cal X }$ 的条件概率;  
$\alpha$ 和 $\beta$ 为三支决策阈值。

两个对象在满足邻域容差关系的基础上还必须满足至少一个已知属性值相等或相似，才符合限制邻域容差关系，然而这种划分方式对于缺失程度大的对象仍然存在较大的缺陷。例如，对象 $\boldsymbol { x } = ( 0 . 5 , * , * , * , * , * , * , * , * , 1 )$ 与对象 $y = ( 0 . 5 1 , * , * , * , * , * , * , * , * , 1 )$ ， $x$ 与 $y$ 存在 $80 \%$ 的未知值，实际相似的概率很小，却被划分到同一个限制邻域容差类，显然这种划分方式也过于宽容，会导致划分粒度过大。

# 1.3完备邻域容差关系

由于不同的信息系统的完备度各不相同，所以完备容差关系[18]在限制容差关系的基础上考虑了单个信息系统内对象之间和多个信息系统之间的差异性，即在一个信息系统中的两个对象，基于完备容差关系被认为是可分辨的，但在另一个信息系统中可能被认为是不可分辨的。

定义6给定不完备混合决策系统 $I D S = U , C , D$ ，则对$\forall x _ { i } \in U$ ，其完备度定义为

$$
\gamma ( x _ { i } ) = \vert P ( x _ { i } ) \vert / \vert C \vert
$$

其中： $P ( x _ { i } ) { = } \{ a | a { \in } C \land a ( x _ { i } ) { \neq } ^ { * } \}$ 表示非空属性集； $\lvert \divideontimes \rvert$ 表示集合“ $\divideontimes$ ”的基数，则整个决策系统的完备度定义为

$$
\gamma = \left( \sum _ { i = 1 } ^ { | U | } \gamma ( x _ { i } ) \right) / | U |
$$

由以上范式可知， $\gamma ( x _ { i } ) \in [ 0 , 1 ]$ ， $\gamma \in \left[ 0 , 1 \right]$ 0

定义7给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall B \subseteq C$ ，$B = B _ { C } \cup B _ { N }$ ， $\delta$ 为邻域参数，则对 $\forall x , y \in U$ 在 $B$ 下的完备邻域容差关系定义为

$$
{ N M } _ { B } ^ { \delta } ( x , y ) = \{ ( x , y ) \in { U } ^ { 2 } \middle | \forall _ { a _ { k } \in B } (  \begin{array} { l } { ( P _ { B } ( x ) \neq \mathcal { Q } ) \wedge ( P _ { B } ( y ) \neq \mathcal { O } ) } \\ { ( \displaystyle \frac { | P _ { B } ( x ) \cap P _ { B } ( y ) | } { \operatorname* { m i n } ( | P _ { B } ( x ) | , | P _ { B } ( y ) | ) } \geq \gamma \wedge } \\ { ( a _ { k } \in B _ { c } \to \Delta _ { a _ { k } } ( x , y ) = 0 ) \wedge } \\ { ( a _ { k } \in B _ { N } \to \Delta _ { a _ { k } } ( x , y ) \leq \delta ) } \\ { } \end{array} ) ) \}
$$

在完备容差关系下，约定 $\boldsymbol { x } = ( ^ { * } , ^ { * } , ^ { * } , ^ { * } , ^ { * } , ^ { * } , ^ { * } )$ 不与任何对象相似。 $N M _ { B } ^ { \delta }$ 具有自反性和对称性，但不具备传递性。对 $\forall x \in U$ 在混合属性子集 $B$ 下的完备邻域容差类定义为

$$
N M _ { B } ^ { \delta } \left( x \right) = \left\{ y \in U \vert y \in N M _ { B } ^ { \delta } \left( x , y \right) \right\}
$$

定义8给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall X \in U$ ，则在混合属性子集 $B$ 下， $X$ 基于完备邻域容差关系的三支决策规则定义为

若 $\alpha \leq P ( X | N M _ { B } ( x ) ) \leq 1$ ，则 $x \in P O S _ { B } ^ { N M } \left( X \right)$ 若 $\beta < P ( X | N M _ { B } ( x ) ) < \alpha$ ，则 $x \in B N D _ { B } ^ { N M } \left( X \right)$ 若 $0 \leq P ( X | N M _ { \scriptscriptstyle B } ( x ) ) \leq \beta$ ，则 $x \in N E G _ { B } ^ { N M } \left( X \right)$ （20

其中： $P ( X | N M _ { _ B } ( x ) ) = \frac { | X \cap N M _ { _ B } ( x ) | } { | N M _ { _ B } ( x ) | }$ 为 $N M _ { \scriptscriptstyle B } ( x )$ 属于 $\boldsymbol { \cal X }$ 的条件概率;  
$\alpha$ 和 $\beta$ 为三支决策阈值。

假设π=- =min(P(xP(），经分析发现，当两个对象的已知属性存在包含关系时， $\pi$ 的值总会为1，它必然大于或等于整个信息系统的完备度 $\gamma$ 。例如，对象$\boldsymbol { x } = ( ^ { * } , ^ { * } , ^ { * } , ^ { * } , 0 . 5 , ^ { * } , ^ { * } , ^ { * } , 1 , ^ { * } )$ 与对象 $y = \left( 2 , ^ { * } , ^ { * } , ^ { * } , 0 . 5 1 , ^ { * } , 3 , ^ { * } , 1 , ^ { * } \right)$ ，因为$\pi ( x , y ) = 1$ ，其大于等于 $\gamma$ 的概率为 $100 \%$ ，在完备邻域容差关系下， $x$ 与 $y$ 被认为是不可分辨的。但实际上，它们相似的可能性很小。因此，完备邻域容差关系对缺失数据的处理也存在一定不合理性，且当信息系统的不完备度较大时，其不合理性更明显。

# 2 不完备混合决策系统的三支决策模型

不完备混合决策系统的三支决策模型的核心步骤为：定义新的完备邻域容差关系用于计算不完备混合数据的近似类，进而计算条件概率，然后通过新定义的损失函数区间概念计算“乐观”“折中”和“悲观”三支阈值。

# 2.1一种新的完备邻域容差关系近似度量

定义9给定不完备混合决策系统 $I D S = U , C , D$ ，令 $\forall B \subseteq C$ ，$B = B _ { C } \cup B _ { N }$ ， $B _ { c }$ 为符号型属性子集， $B _ { N }$ 为连续型属性子集，则对 $\forall x , y \in U$ ，其新的完备邻域容差关系定义为

$$
N R _ { B } ( x , y ) = \{ ( x , y ) \in U ^ { 2 } \big | _ { \displaystyle \wedge m i n } ( \frac { \bigvee _ { a } ( a _ { k } ( x ) = ^ { * } \vee a _ { k } ( y ) = ^ { * } } { m i n ( | P _ { B } ( x ) | , | P _ { B } ( y ) | ) } , \frac { \gamma ( x ) + \gamma ( y ) } { 2 } ) \geq \gamma \}
$$

其中：

$$
\begin{array} { c } { { P _ { _ B } ( x ) \cap P _ { _ B } ( y ) = \{ \{ \vphantom { [ | \begin{array} { l } { { a _ { k } | a _ { k } ( x ) | \ddag } a _ { k } ( y ) \} , a _ { k } \in B _ { C }   } } } \\ { {  \{ a _ { k } \mid \vphantom { a _ { k } | a _ { k } ( x ) | } \} a _ { k } ( x , y ) \leq \delta _ { a _ { k } } \} , a _ { k } \in B _ { N } } } \\ { { P ( x ) = \{ a _ { k } \mid a _ { k } \in B \land a _ { k } ( x ) \neq ^ { * } \} } } \\ { {   \vphantom { ( | a _ { k } | } \Delta _ { a _ { k } } ( x , y ) = | a _ { k } ( x ) - a _ { k } ( y ) | } \vphantom { a _ { k } ( x ) }   } } \end{array} \end{array}
$$

$\delta _ { a _ { k } }$ 为属性 $a _ { k }$ 上的邻域参数，为保证新的完备容差邻域类的计算的客观性， $\delta _ { a _ { k } }$ 由 $a _ { k }$ 的标准差 $s t d _ { a _ { k } }$ 和参数 $\boldsymbol { \vartheta }$ 表示，即=std;此处约定=,即x=(\*,\*..\*)不与任何对象相似。$N R _ { _ B } ( x , y )$ 满足自反性和对称性,不满足传递性,对 $\forall x \in U$ ,其在不完备混合属性子集 $B$ 下的新完备邻域容差类定义为

$$
N R _ { B } \left( x \right) = \{ y | y \in N R _ { B } \left( x , y \right) \}
$$

同样，对于定义7中给出的对象 $\boldsymbol { x } = ( ^ { * } , ^ { * } , ^ { * } , ^ { * } , 0 . 5 , ^ { * } , ^ { * } , ^ { * } , 1 , ^ { * } )$ 与对象 $y = \left( 2 , ^ { \ast } , ^ { \ast } , ^ { \ast } , 0 . 5 1 ^ { \ast } , 3 , ^ { \ast } , 1 , ^ { \ast } \right)$ ，在新的完备邻域容差下，计算得到 $\frac { \gamma ( x ) + \gamma ( y ) } { 2 } { = } 0 . 3$ ，在一个包含了 $x$ 和 $y$ 的系统中，γ值有 $70 \%$ 的概率在 $0 . 3 { \sim } 1$ 之间，而这意味着 $\frac { \gamma ( x ) + \gamma ( y ) } { 2 }$ 小于 $\gamma$ 的概率为$70 \%$ ，即 $x$ 与 $y$ 相似的概率仅为 $30 \%$ ，所以 $x$ 与 $y$ 被认为是不相似的。因此，对于不完备混合数据的处理，新的完备邻域容差关系更加客观合理。

定理1给定不完备混合决策系统 $I D S = U , C , D$ ，若新完备邻域容差类由 $P _ { B } \left( x \right) \cap P _ { B } \left( y \right)$ 决定，则当邻域参数 $\delta _ { a _ { k } } ^ { \delta _ { i } } \leq \delta _ { a _ { k } } ^ { \delta _ { j } }$ 时，有$N R _ { B } ^ { \delta _ { i } } \left( x , y \right) \subseteq N R _ { B } ^ { \delta _ { j } } \left( x , y \right) \mathrm { ~ } \mathrm { ~ o ~ }$ （204号

证明 根据定义9,对于 $\forall y \in N R _ { B } ^ { \delta _ { i } } \left( x , y \right)$ ，都有 $\Delta _ { a _ { k } } \left( x , y \right) \leq \delta _ { a _ { k } } ^ { \delta _ { i } }$ ，又因为 $\delta _ { a _ { k } } ^ { \delta _ { i } } \leq \delta _ { a _ { k } } ^ { \delta _ { j } }$ ，所以 $\Delta _ { a _ { k } } \left( x , y \right) \leq \delta _ { a _ { k } } ^ { \delta _ { j } }$ ，即 $y \in N R _ { B } ^ { \delta _ { j } } \left( x , y \right)$ ，所以可以得到 $N R _ { B } ^ { \delta _ { i } } \left( x , y \right) \subseteq N R _ { B } ^ { \delta _ { j } } \left( x , y \right)$ 。

定理2给定不完备混合决策系统 $I D S = U , C , D$ ， $N T _ { B } \left( x \right)$ 为 邻域容差类， $N L _ { \scriptscriptstyle B } ( x )$ 为限制邻域容差类， $N M _ { { \scriptscriptstyle B } } ( x )$ 完备邻域容 差类， $N R _ { \scriptscriptstyle B } ( x )$ 为新完备邻域容差类，若 $\forall _ { x \in U } \left( P ( x ) \neq \emptyset \right)$ ，都有

$$
N R _ { B } \left( x \right) \subseteq N M _ { B } \left( x \right) \subseteq N L _ { B } \left( x \right) \subseteq N T _ { B } \left( x \right)
$$

证明由定义2、4、7和9可证。

定义10给定不完备混合决策系统 $I D S = U , C , D$ ，在新的完备容差邻域关系下，对 $\forall X \in U$ ，其在不完备混合属性子集$B$ 下的上下近似定义为

$$
X _ { B } ^ { N R } = \{ x \vert x \in U \land N R _ { B } ( x ) \subseteq X \}
$$

$$
X _ { \mathit { N R } } ^ { \mathit { B } } = \{ x \vert x \in U \land N R _ { \mathit { B } } ( x ) \cap X \neq \emptyset \} = \bigcup _ { x \in X } N R _ { \mathit { B } } ( x )
$$

定理3给定不完备混合决策系统 $I D S = U , C , D$ ， $\mathbf { \Omega } _ { N T }$ 为邻域容差关系， $N L$ 为限制邻域容差关系，NM完备邻域容差关系，NR为新的完备邻域容差关系，若 $\forall _ { x \in U } \left( P ( x ) \neq \emptyset \right)$ ，则对$\forall X \in U$ 都有

$$
\begin{array} { c } { { X _ { B } ^ { N T } \subseteq X _ { B } ^ { N L } \subseteq X _ { B } ^ { N M } \subseteq X _ { B } ^ { N R } } } \\ { { X _ { N R } ^ { B } \subseteq X _ { N M } ^ { B } \subseteq X _ { N L } ^ { B } \subseteq X _ { N T } ^ { B } } } \end{array}
$$

证明 a)：若存在 $x \in X _ { B } ^ { N T }$ ，则有 $N T _ { \scriptscriptstyle B } \left( x \right) \subseteq X$ ，由定理1可知， $N L _ { B } \left( x \right) \subseteq N T _ { B } \left( x \right) \subseteq X$ ，即可得到 $x \in X _ { B } ^ { N L }$ ，因此 $X _ { B } ^ { N T } \subseteq X _ { B } ^ { N L }$ ，同理可证 $X _ { B } ^ { N L } \subseteq X _ { B } ^ { N M }$ 和 $X _ { B } ^ { N M } \subseteq X _ { B } ^ { N R }$ ，所以 $X _ { B } ^ { N T } \subseteq X _ { B } ^ { N L } \subseteq X _ { B } ^ { N M } \subseteq X _ { B } ^ { N R }$ 。

证明 b)：由定理1可知 $N R _ { B } \left( x \right) \subseteq N M _ { B } \left( x \right) \subseteq N L _ { B } \left( x \right) \subseteq N T _ { B } \left( x \right)$ ，又因为 $X _ { N R } ^ { B } = \bigcup N R _ { \scriptscriptstyle B } \left( x \right)$ ，所以 $X _ { N R } ^ { B } \subseteq X _ { N M } ^ { B } \subseteq X _ { N L } ^ { B } \subseteq X _ { N T } ^ { B }$ 。

# 2.2新的完备邻域容差关系三支决策模型

在决策粗糙集中，条件概率由等价类 $[ x ]$ 计算而来，且[x]中的对象共用相同的损失函数 $\lambda _ { \cdot \cdot } \left( \cdot = P , B , N \right)$ 。在本文中，条件概率由新完备邻域容差类 $N R _ { \scriptscriptstyle B } ( x )$ 计算而来，而 $N R _ { \scriptscriptstyle B } ( x )$ 中的对象都包含未知值，所以每个对象都应设置不同的损失函数。在不能准确地估计损失函数的情况下，可通过定义损失函数区间概念，利用区间值 $\lambda _ { \cdot \cdot } = \left[ \lambda _ { . . } ^ { - } , \lambda _ { . . } ^ { + } \right] { } ^ { [ 2 0 ] }$ 计算损失函数进而计算阀值，因此构建损失函数区间表如表1所示。

表1损失函数区间  
Table 1 Loss function interval   

<html><body><table><tr><td colspan="2">决策</td><td>X(P)</td><td>→X(N)</td></tr><tr><td>接受：ap</td><td></td><td>λpp =[pp,λp]</td><td>λPN =[2PN,λN]</td></tr><tr><td>延迟：</td><td>aB</td><td>λBp =[2Bp,λp]</td><td>λBN =[2BN,λN]</td></tr><tr><td>拒绝：</td><td>aN</td><td>λNP =[Np,λP]</td><td>λNN =[NN,λNN]</td></tr></table></body></html>

表中： $\forall X \in { U }$ 、 $\lambda _ { . . } ^ { - } \leq \lambda _ { . . } ^ { + }$ 、 $\left\{ \lambda _ { { \scriptscriptstyle P P } } , \lambda _ { { \scriptscriptstyle B P } } , \lambda _ { { \scriptscriptstyle N P } } \right\}$ 分别表示当对象 $x$ 属于对象子集 $\boldsymbol { \cal X }$ 时，接受、延迟和拒绝 $x$ 于 $\boldsymbol { \cal X }$ 类所造成的损失；$\left\{ \lambda _ { P N } , \lambda _ { B N } , \lambda _ { N N } \right\}$ 分别表示当 $x$ 不属于 $\boldsymbol { \cal X }$ 时，接受、延迟、拒绝 $x$ 于 $\boldsymbol { \cal X }$ 类所造成的损失，故作合理假设： $\lambda _ { { P P } } \leq \lambda _ { { B P } } \leq \lambda _ { { N P } }$ ，$\lambda _ { N N } \leq \lambda _ { B N } \leq \lambda _ { P N }$ 。

预先设定损失函数参数 $\mu$ ，将损失函数区间转换为具体的损失函数值： $\begin{array} { r } { \lambda _ { . . } = ( 1 - \mu ) \lambda _ { . . } ^ { - } + \mu \lambda _ { . . } ^ { + } } \end{array}$ 。其中，当 $\scriptstyle { \mu = 0 }$ 时， $\lambda$ 偏小，代表偏好风险设置法，即“乐观”设置法；当 $\scriptstyle { \mu = 1 }$ 时，偏大，代表厌恶风险设置法，即“悲观”设置法；当 $\mu = 0 . 5$ 时，λ为区间平均值，代表风险折中设置法，即“折中”设置法。由于文献[20]中近似类的损失函数区间获取时可能会出现没有交集或者没有并集的情况，所以本文定义新的损失函数区间概念如下：

定义11给定伴有损失函数区间的不完备混合决策系统$I D S = U , C , D , \lambda _ { \scriptscriptstyle - }$ ，则对 $\forall x \in U$ ，其在“乐观”“折中”决策和“悲观”决策下的损失函数 $\lambda _ { \cdot \cdot } ( \cdot = P , B , N )$ 定义为

“乐观”损失函数值： $\lambda _ { . } ^ { \gamma } \left( x \right) = \frac { \sum _ { x _ { i } \in N R _ { B } \left( x \right) } \lambda _ { . } ^ { - } \left( x _ { i } \right) } { \left| N R _ { B } \left( x \right) \right| }$ “折中”损失函数值： $\lambda _ { . } ^ { - } \left( x \right) = \frac { \sum _ { x _ { i } \in N R _ { B } \left( x \right) } \left( \frac { \lambda _ { . } ^ { - } \left( x _ { i } \right) + \lambda _ { . } ^ { + } \left( x _ { i } \right) } { 2 } \right) } { \left| N R _ { B } \left( x \right) \right| } ,$ “悲观”损失函数值： $\lambda _ { \cdot \cdot } ^ { \cdot } \left( x \right) = \frac { \sum _ { x _ { i } \in N R _ { B } \left( x \right) } \lambda _ { \cdot \cdot } ^ { + } \left( x _ { i } \right) } { \left. N R _ { B } \left( x \right) \right. }$ （2

以上范式中的上标符号分别表示：“ $\Upsilon$ ”一“乐观”，“ $\succ$ ”一折中，“人”一“悲观”。为使文章简洁，在下文中所出现的这些符号均表示该含义。

三支决策的“三分一三决策”模型的基本框架是通过一对阈值将论域划分为三个互不相交的域，即POS一正域、BND一边界域和NEG一负域，针对这三个域中的对象分别采取接受、不承诺和拒绝的策略。为此，基于新的完备邻域容差关系为不完备混合决策系统构建三支决策模型。

定义12给定不完备混合决策系统 $I D S = U , C , D , \lambda .$ ，令 $\alpha _ { \gamma }$ 和 $\beta _ { \mathrm { v } }$ 为基于损失函数 $\lambda _ { . . } ( \cdot = P , B , N )$ 计算而来的乐观三支阈值，当 $\alpha _ { \mathrm { v } } \ge \beta _ { \mathrm { v } }$ 时，在新的完备容差邻域关系下，对 $\forall X \in U$ ，其在不完备混合属性子集 $B$ 下，依据贝叶斯风险最小化决策准则制定的“乐观”三支决策模型为

若 $\alpha _ { \mathrm { v } } \leq P ( X | N R _ { \mathit { B } } ( x ) ) \leq 1$ ，则 $x \in P O S _ { B } ^ { N R } \left( X \right)$ 若 $\beta _ { \mathrm { v } } < P ( X | N R _ { B } ( x ) ) < \alpha _ { \mathrm { v } }$ ，则 $x \in B N D _ { B } ^ { N R } \left( X \right)$

若 $0 \leq P ( X | N R _ { \mathit { B } } ( x ) ) \leq \beta _ { \mathrm { v } }$ ，则 $x \in N E G _ { B } ^ { N R } \left( X \right)$ 其中：P(X|NRB(x)=|XONRB(x)

$$
\alpha _ { \checkmark } = \frac { \left( \lambda _ { P N } ^ { \vee } - \lambda _ { B N } ^ { \vee } \right) } { \left( \lambda _ { P N } ^ { \vee } - \lambda _ { B N } ^ { \vee } \right) + \left( \lambda _ { B P } ^ { \vee } - \lambda _ { P P } ^ { \vee } \right) } ,
$$

$$
\beta _ { \checkmark } = \frac { \left( \lambda _ { B N } ^ { \gamma } - \lambda _ { N N } ^ { \gamma } \right) } { \left( \lambda _ { B N } ^ { \gamma } - \lambda _ { N N } ^ { \gamma } \right) + \left( \lambda _ { N P } ^ { \gamma } - \lambda _ { B P } ^ { \gamma } \right) } \ : \mathrm { ~ o ~ }
$$

当 $\alpha _ { \mathrm { v } } < \beta _ { \mathrm { v } }$ 时，三支决策转换为二支决策，阈值$\gamma _ { \mathrm { v } } = \frac { \left( \lambda _ { P N } ^ { \mathrm { v } } - \lambda _ { N N } ^ { \mathrm { v } } \right) } { \left( \lambda _ { P N } ^ { \mathrm { v } } - \lambda _ { N N } ^ { \mathrm { v } } \right) + \left( \lambda _ { N P } ^ { \mathrm { v } } - \lambda _ { P P } ^ { \mathrm { v } } \right) }$ ，则对于 $\forall X \in U$ ，其在不完备混合属性子集 $B$ 下的“乐观”二支决策模型定义为

若 $\gamma _ { \checkmark } \leq P ( X | N R _ { b } ( x ) ) \leq 1$ 则 $x \in P O S _ { B } ^ { N R } \left( X \right)$ （204号 若 $0 \leq P ( X | N R _ { { B } } ( x ) ) < \gamma _ { \mathrm { v } }$ 则 $x \in N E G _ { B } ^ { N R } \left( X \right)$

根据定义12，给出三支决策模型的语义解释：当$x \in P O S _ { B } ^ { N R } \left( X \right)$ 时，代表接受 $x$ 于 $\boldsymbol { \cal X }$ 类中；当 ${ \boldsymbol { x } } \in B N D _ { B } ^ { N R } \left( { \boldsymbol { X } } \right)$ 时，代表延迟接受或延迟拒绝 $x$ 于 $\boldsymbol { \cal X }$ 类中；当 $x \in N E G _ { B } ^ { N R } \left( X \right)$ 时，代表拒绝 $x$ 于 $\boldsymbol { \cal X }$ 类中。

定义13在不完备混合决策系统 $\ I D S = U , C , D , \lambda .$ 中，令属性子集 $B { = } C$ ， $\forall X \in { U } / { D }$ 。则在“乐观”决策下，基于属性全集 $c$ 对决策属性 $D$ 的新的完备容差邻域关系下的正域、负域和边界域为

$$
\begin{array} { r l } & { P O S _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( D ) _ { N R } = \underset { X \in \mathcal { U } / D } { \bigcup } P O S _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( X ) _ { S } } \\ & { B N D _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( D ) _ { N R } = \underset { X \in \mathcal { U } / D } { \bigcup } B N D _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( X ) _ { S } } \\ & { N E G _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( D ) _ { N R } = \underset { X \in \mathcal { U } / D } { \bigcup } N E G _ { C } ^ { ( \alpha _ { \tau } , \gamma _ { \tau } , \beta _ { \tau } ) } ( X ) _ { S } } \end{array}
$$

由于“折中"和“悲观"决策风险下的三支决策和二支决策的基本模型与“乐观"决策风险下的基本模型类似，为了文章结构简洁，此处省略。

# 3 算法描述与实例分析

# 3.1算法描述

在面向不完备混合决策系统的三支决策算法中，核心步骤为条件概率的计算和阈值的求解：首先，本文构建新的完备邻域容差关系获取不完备混合数据的近似类，并利用近似类计算条件概率；然后，为各对象设置不同损失函数区间，并通过新的区间值计算范式求解各对象的“乐观”“折中”和“悲观”三支阈值；最终构建基于新的完备邻域容差关系的“乐观”“折中”和“悲观”三支决策规则。算法描述如下：

算法：基于新的完备邻域容差关系三支决策规则  
输入：不完备混合决策系统IDS。  
输出：“乐观”、“折中"和"悲观"三支决策规则。  
Begin  
对 $I D S$ 中连续型数据进行标准化和归一化  
初始化参数 $\boldsymbol { \vartheta }$ 、 $\mu$ 和损失函数区间值 $\lambda _ { \infty } = [ \lambda ^ { - } , \lambda ^ { + } ]$ ：  
计算 $\delta _ { a _ { k } } = \frac { s t d _ { a _ { k } } } { \mathcal { g } }$ ：//计算连续型属性下的 $\delta _ { a _ { k } }$ 值  
计算决策类 $X \in { U } / D$ ：  
for $x \in U$ do  
for $y \in U$ do  
基于新的完备邻域容差关系求解不完备混合数据的近似类 $N R _ { \scriptscriptstyle B } ( x )$ ：end//根据定义9

end根据 $N R _ { B } ^ { \delta } \left( x \right)$ 计算 $\{ \beta , \gamma , \alpha \} \hat { ! }$ //根据定义11for $x \in X$ do计算的条件概率 $P ( X | N R _ { B } \left( x \right) )$ endfor $x \in X$ doif $( \beta \leq \alpha )$ （20若 $1 \geq P ( X | N R _ { \mathit { b } } \left( x \right) ) \geq \alpha$ ，则将 $x$ 划分到类别 $X$ 的正域 $P O S _ { B } ^ { N R } \left( X \right)$ ；否则，若 $\beta < P ( X | N R _ { B } ( x ) ) < \alpha$ ，则将对象 $x$ 划分到 $X$ 的边界域$B N D _ { B } ^ { N R } \left( X \right)$ ：否则，将对象 $x$ 划分到 $\boldsymbol { \cal X }$ 的负域 $N E G _ { B } ^ { N R } \left( X \right)$ ：else若 $\gamma \le P ( X | N R _ { \scriptscriptstyle B } ( x ) ) \le 1$ 则将 $x$ 划分到类别 $X$ 的正域 $x \in P O S _ { B } ^ { N R } \left( X \right)$ ·否则，则将 $x$ 划分到类别 $X$ 的负域 $x \in N E G _ { B } ^ { N R } \left( X \right)$ ：end输出： $P O S _ { c } ^ { ( \beta , \gamma , \alpha ) } ( D ) _ { N R }$ 、 $P O S _ { c } ^ { ( \beta , \gamma , \alpha ) } ( D ) _ { N R }$ 和 $P O S _ { c } ^ { ( \beta , \gamma , \alpha ) } ( D ) _ { N R }$ ；//根据定义13end其中 $\{ \beta , \gamma , \alpha \} = \{ \{ \beta _ { \checkmark } , \gamma _ { \checkmark } , \alpha _ { \check { \Upsilon } } \} , \{ \beta _ { \prec } , \gamma _ { \prec } , \alpha _ { \prec } \} , \ P , \gamma _ { \wedge } , \alpha _ { \prec } \} \}$ 算法时空复杂度分析：算法的 Step1、Step3 的时间复杂度为 $O ( | U | | C _ { N } | )$ ， $C _ { N }$ 代表连续型属性个数；Step5 的时间复杂度为 $O \big ( | U | ^ { 2 } | C \big | \big )$ ；Step4、Step6、Step7、Step8的时间复杂度为 $O ( | U | )$ ，其余步骤的时间复杂度均为 $O ( 1 )$ 。因此，该算法的最坏时间复杂度是$O \big ( | U | ^ { 2 } | C \big | \big )$ ；此外，存储空间主要用于存放不完备混合决策系统中的数据，故算法的空间复杂度为 $O ( | U | | C | )$ 。

# 3.2实例分析

假定从某医院科室获取了一份包含不完备混合数据的诊断决策表 $I D S = U , C , V , D , \lambda .$ ，如表2所示，其中$U = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , x _ { 6 } \}$ 代表6位患者； $C = \{ a _ { 1 } , a _ { 2 } , a _ { 3 } , a _ { 4 } \}$ 代表四种检查项目： $a _ { \scriptscriptstyle 1 }$ —“咳嗽”、 $a _ { 2 }$ 一“过敏程度”、 $\left| a _ { 3 } \right|$ 一“胸闷程度”、 $a _ { 4 }$ 一“失眠程度”； $\boldsymbol { V }$ 代表检查结果，其中“1”—“有”、“0”—“没有”、“high”—“严重”、“low”一“不严重”，“\*”表示因特殊原因暂时无法获取的数据，小数代表对应症状的患病程度； $D$ 为诊断结果，符号“ $\Phi$ ”—“扁桃体炎症”、“ $\Psi$ ”—“病毒感染”、“ $\Omega$ ”—“过敏”； $\lambda .$ 代表各对象的损失函数区间，例如，对患者 $x _ { 1 }$ 而言， $\lambda _ { P P }$ 、 $\lambda _ { B P }$ 和 $\lambda _ { N P }$ 分别表示确诊其为扁桃体炎症患者后，对其进行治疗、延迟治疗和不治疗可能带来的风险损失; $\lambda _ { P N } \setminus \lambda _ { B N }$ 和 $\lambda _ { \scriptscriptstyle { N N } }$ 分别表示确诊其未患扁桃体炎症后，对其进行治疗、延迟治疗和不治疗可能带来的风险损失；其中“治疗”造成的损失主要包括检查费用和治疗费用等，“延迟治疗”造成的损失主要包括检查费用、治疗费用和病人因延迟治疗造成的身体损失等，“不治疗”造成的损失主要包括检查费用和病痛代价。通常情况下， $\lambda _ { _ { P P } } \leq \lambda _ { _ { B P } } \leq \lambda _ { _ { N P } }$ ，$\lambda _ { \scriptscriptstyle { N N } } \leq \lambda _ { \scriptscriptstyle { B N } } \leq \lambda _ { \scriptscriptstyle { P N } }$

表2中“ $\omega$ ”为不同环境下的损失单位，比如此处可表示“千元”。根据决策属性划分决策类： $D _ { 1 } = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } \}$ ：$D _ { 2 } = \{ x _ { 4 } \}$ ； $D _ { 3 } = \{ x _ { 5 } , x _ { 6 } \}$ 。令 $\scriptstyle { \mathcal { G } } = 1$ ，计算得到表2中连续属性的邻域参数： $\delta _ { a _ { 2 } } \approx 0 . 2 3$ ， $\delta _ { a _ { 4 } } \approx 0 . 2 9$ ；表2的完备度： $\gamma \approx 0 . 7 9$ 。

根据定义9，基于新的完备邻域容差关系对表1进行近似度量得到各对象的近似类：

新完备邻域容差类： $N R _ { c } \left( x _ { 1 } \right) = \left\{ x _ { 1 } \right\}$ ； $N R _ { c } \left( x _ { 2 } \right) = \left\{ x _ { 2 } , x _ { 5 } \right\}$ ：$N R _ { c } \left( x _ { 3 } \right) = \left\{ x _ { 3 } \right\}$ ; $N R _ { c } \left( x _ { 4 } \right) = \left\{ x _ { 4 } \right\}$ ； $N R _ { c } \left( x _ { 5 } \right) = \left\{ x _ { 2 } , x _ { 5 } \right\}$ ; $N R _ { c } \left( x _ { 6 } \right) = \left\{ x _ { 6 } \right\}$ 。

根据定义11计算患者的损失函数具体值，即分别设置$\scriptstyle \mu = 0$ 、 $\mu = 0 . 5$ 和 $\mu = 0 . 5$ ，再根据定义12，计算“乐观”、“折中”和“悲观”三支阈值，如表3\~5所示。

根据定义12计算出患者确诊患病的条件概率，并根据表3\~5计算而来的三支阈值，对患者进行分类诊断，并给出治疗方案如表6所示，其中“？”表示不确定患者是否患有对应疾病。

表2某医院不完备混合数据诊断决策表

<html><body><table><tr><td>U</td><td>a1</td><td>a</td><td>a</td><td>a4</td><td>D</td><td>Mpp</td><td>MBP</td><td>MNP</td><td></td><td>~BN</td><td>MpN</td></tr><tr><td>x1</td><td>1</td><td>0.2</td><td>high</td><td>0.15</td><td></td><td>[1ω,2ω]</td><td>[2ω,3ω]</td><td>[4ω,5ω]</td><td>[1ω,3ω]</td><td>[3ω,4.5ω]</td><td>[5ω,7a]</td></tr><tr><td>x2</td><td>0</td><td>*</td><td>low</td><td>0.7</td><td></td><td>[0ω,2ω]</td><td>[2.5ω,3ω]</td><td>[3ω,5.5ω]</td><td>[0.5ω,lω]</td><td>[1.5ω,3ω]</td><td>[4ω,5.5ω]</td></tr><tr><td>x3</td><td>*</td><td>0.5</td><td>*</td><td>0.2</td><td></td><td>[2ω,3ω]</td><td>[3ω,3.5ω]</td><td>[4ω,5.5ω]</td><td>[0ω,1.5ω]</td><td>[2ω,3ω]</td><td>[3.5ω,5ω]</td></tr><tr><td>X4</td><td>0</td><td>0.7</td><td>low</td><td>0.3</td><td></td><td>[0.5ω,2ω]</td><td>[4ω,4.5ω]</td><td>[5ω,6ω]</td><td>[0.5ω,2ω]</td><td>[2.5ω,3ω]</td><td>[3ω,6ω]</td></tr><tr><td>X5</td><td>0</td><td>0.8</td><td>low</td><td>0.8</td><td>Ω</td><td>[1ω,2.5ω]</td><td>[3ω,5ω]</td><td>[5ω,7ω]</td><td>[1ω,3ω]</td><td>[3ω,4ω]</td><td>[4ω,6ω]</td></tr><tr><td>X6</td><td>0</td><td>*</td><td>*</td><td>0.85</td><td>Ω</td><td>[1ω,1.5ω]</td><td>[2.5ω,4ω]</td><td>[4.5ω,6ω]</td><td>[2ω,3ω]</td><td>[4ω,5.5ω]</td><td>[6ω,7.5ω]</td></tr></table></body></html>

表3各患者的"乐观"三支阈值的计算过程

Table 2Incomplete composite data diagnosis decision table of hospital   

<html><body><table><tr><td colspan="10">eachpatient</td></tr><tr><td>患者</td><td colspan="4">“乐观”损失函数值</td><td colspan="4">“乐观”三支阈值</td></tr><tr><td>U</td><td>2pp</td><td>Bp</td><td>2NP</td><td>2NN</td><td>2BN</td><td>2PN</td><td>β</td><td>YY</td><td>aγ</td></tr><tr><td>X1</td><td>1</td><td>2</td><td>4</td><td>1</td><td>3</td><td>5</td><td>0.50</td><td>0.57</td><td>0.67</td></tr><tr><td>X2</td><td>0.5</td><td>2.75</td><td>4</td><td>0.75</td><td>2.25</td><td>4</td><td>0.55</td><td>0.48</td><td>0.44</td></tr><tr><td>X3</td><td>2</td><td>3</td><td>4</td><td>0</td><td>2</td><td>3.5</td><td>0.67</td><td>0.64</td><td>0.60</td></tr><tr><td>X4</td><td>0.5</td><td>4</td><td>5</td><td>0.5</td><td>2.5</td><td>3</td><td>0.67</td><td>0.36</td><td>0.13</td></tr><tr><td>X5</td><td>0.5</td><td>2.75</td><td>4</td><td>0.75</td><td>2.25</td><td>4</td><td>0.55</td><td>0.48</td><td>0.44</td></tr><tr><td>X6</td><td>1</td><td>2.5</td><td>4.5</td><td>2</td><td>4</td><td>6</td><td>0.50</td><td>0.53</td><td>0.57</td></tr></table></body></html>

表4各患者"折中"三支阈值的计算过程

Table 3 Calculation process of“optimistic”three-way thresholds of each patient   
[able 4 Calculation process of“compromising"three-way threshold: of each patient   

<html><body><table><tr><td>患者</td><td colspan="6">“折中”损失函数值</td><td colspan="3">“折中”三支阈值</td></tr><tr><td>U</td><td>2pp</td><td>2BP</td><td>2NP</td><td>2NN</td><td>2BN</td><td>2PN</td><td>β</td><td>Y</td><td>αx</td></tr><tr><td>X1</td><td>1.5</td><td>2.5</td><td>4.5</td><td>2</td><td>3.75</td><td>6</td><td>0.47</td><td>0.57</td><td>0.69</td></tr><tr><td>X</td><td>1.38</td><td>3.38</td><td>5.13</td><td>1.38</td><td>2.88</td><td>4.88</td><td>0.46</td><td>0.48</td><td>0.50</td></tr><tr><td>X</td><td>2.5</td><td>3.25</td><td>4.75</td><td>0.75</td><td>2.5</td><td>4.25</td><td>0.54</td><td>0.61</td><td>0.70</td></tr><tr><td>X4</td><td>1.25</td><td>4.25</td><td>5.5</td><td>1.25</td><td>2.75</td><td>4.5</td><td>0.55</td><td>0.43</td><td>0.37</td></tr><tr><td>X5</td><td>1.38</td><td>3.38</td><td>5.13</td><td>1.38</td><td>2.88</td><td>4.88</td><td>0.46</td><td>0.48</td><td>0.50</td></tr><tr><td>X6</td><td>1.25</td><td>3.25</td><td>5.25</td><td>2.5</td><td>4.75</td><td>6.75</td><td>0.53</td><td>0.52</td><td>0.50</td></tr></table></body></html>

Table 5Calculation process of“pessimistic”three-way thresholds of   
表6基于三支决策为各患者制定三种决策风险下的治疗方案  

<html><body><table><tr><td colspan="10">each patient</td></tr><tr><td>患者</td><td></td><td></td><td></td><td>“悲观”损失函数值</td><td></td><td></td><td>“悲观”</td><td></td><td>三支阈值</td></tr><tr><td>U</td><td>2pp</td><td>2BP</td><td>2NP</td><td>2NN</td><td>2BN</td><td>2PN</td><td>β</td><td>Y人</td><td>a</td></tr><tr><td>X1</td><td>2</td><td>3</td><td>5</td><td>3</td><td>4.5</td><td>7</td><td>0.43</td><td>0.57</td><td>0.71</td></tr><tr><td>X</td><td>2.25</td><td>4</td><td>6.25</td><td>2</td><td>3.5</td><td>5.75</td><td>0.40</td><td>0.48</td><td>0.56</td></tr><tr><td>X</td><td>3</td><td>3.5</td><td>5.5</td><td>1.5</td><td>3</td><td>5</td><td>0.43</td><td>0.61</td><td>0.80</td></tr><tr><td>X4</td><td>2</td><td>4.5</td><td>6</td><td>2</td><td>3</td><td>6</td><td>0.40</td><td>0.48</td><td>0.55</td></tr><tr><td>X5</td><td>2.25</td><td>4</td><td>6.25</td><td>2</td><td>3.5</td><td>5.75</td><td>0.40</td><td>0.48</td><td>0.56</td></tr><tr><td>X6</td><td>1.5</td><td>4</td><td>6</td><td>3</td><td>5.5</td><td>7.5</td><td>0.56</td><td>0.52</td><td>0.44</td></tr></table></body></html>

表5各患者"悲观"三支阈值的计算过程  

<html><body><table><tr><td>患者</td><td>条件概率</td><td colspan="3">“乐观"医疗诊断</td><td colspan="3">“折中"医疗诊断</td><td colspan="3">“悲观"医疗诊断</td></tr><tr><td>U</td><td>P(DINRB(x))</td><td>划分结果</td><td>诊断结果</td><td>治疗方案</td><td>划分结果</td><td>诊断结果</td><td>治疗方案</td><td>划分结果</td><td>诊断结果</td><td>治疗方案</td></tr><tr><td>X1</td><td>1</td><td>POSNR(Di)</td><td>扁桃体炎症</td><td>治疗</td><td>POSNR(D)</td><td>扁桃体炎症</td><td>治疗</td><td>POSNR(D)</td><td>扁桃体炎症</td><td>治疗</td></tr><tr><td>X2</td><td>0.5</td><td>POSNR(D)</td><td>扁桃体炎症</td><td>治疗</td><td>POSNR(D)</td><td>扁桃体炎症</td><td>治疗</td><td>BNDNR(D)</td><td>扁桃体炎症？</td><td>延迟治疗</td></tr><tr><td>X3</td><td>1</td><td>POSNR(Di)</td><td>扁桃体炎症</td><td>治疗</td><td>POSNR (D)</td><td>扁桃体炎症</td><td>治疗</td><td>POSNR(Di)</td><td>扁桃体炎症</td><td>治疗</td></tr><tr><td>X4</td><td>1</td><td>POSNR(D2)</td><td>病毒感染</td><td>治疗</td><td>POSNR(D2)</td><td>病毒感染</td><td>治疗</td><td>POSNR(D2)</td><td>病毒感染</td><td>治疗</td></tr><tr><td>X5</td><td>0.5</td><td>POSNR(D3)</td><td>过敏</td><td>治疗</td><td>POSNR(D3)</td><td>过敏？</td><td>治疗</td><td>BNDNR(D3）</td><td>过敏？</td><td>延迟治疗</td></tr><tr><td>X6</td><td>1</td><td>POSNR(D3)</td><td>过敏</td><td>治疗</td><td>POSNR(D3)</td><td>过敏</td><td>治疗</td><td>POSNR(D3)</td><td>过敏</td><td>治疗</td></tr></table></body></html>

在本例中，由于论域 $U$ 较小，所以各对象的在新的完备邻域容差关系下的近似类也较小，大多甚至只有本身，这使得条件概率大多都为1，进而使得大部分对象不论在“乐观”诊断下还是“折中”诊断下都被划分到正域并被推荐治疗；同时可以看到，在“悲观”诊断下，患者 $x _ { 2 }$ 和 $x _ { 5 }$ 被划分到了边界域中，即不确定 $x _ { 2 }$ 是否患有扁桃体炎症，不确定 $x _ { 5 }$ 是否患有过敏，都需要进一步诊断，因此，三支决策为真实决策过程提供了修正错误分类的方法，基于新的完备邻域容差关系适用于医疗诊断这类不完备混合决策系统，而且相比于下文所提的其他方法更加客观合理。

为了与新的完备邻域容差关系进行比较，利用邻域容差关系 $\mathbf { \Omega } _ { N T }$ 、限制邻域容差关系 $N L$ 、完备邻域容差关系NM对表2中的患者进行近似划分和分类诊断。详细计算结果如下：

基于邻域容差关系

根据定义2计算邻域容差类：$N T _ { c } \left( x _ { 1 } \right) = \left\{ x _ { 1 } \right\} \qquad ; \qquad N T _ { c } \left( x _ { 2 } \right) = \left\{ x _ { 2 } , x _ { 5 } , x _ { 6 } \right\} \qquad ; \qquad N T _ { c } \left( x _ { 3 } \right) = \left\{ x _ { 3 } , x _ { 4 } \right\}$ （204号$N T _ { c } \left( x _ { 4 } \right) = \left\{ x _ { 3 } , x _ { 4 } \right\} ; N T _ { c } \left( x _ { 5 } \right) = \left\{ x _ { 2 } , x _ { 5 } , x _ { 6 } \right\} ; N T _ { c } \left( x _ { 6 } \right) = \left\{ x _ { 2 } , x _ { 5 } , x _ { 6 } \right\}$

根据定义11计算基于邻域容差类的三支损失函数值，然后根据定义3划分三种决策风险下的正域、边界域和负域：

“乐观”： $P O S _ { C } ^ { N T } \left( D \right) = \left\{ x _ { 1 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , x _ { 6 } \right\}$ ； $B N D _ { C } ^ { N T } \left( D \right) = \left\{ \mathcal { O } \right\}$ ;$N E G _ { C } ^ { N T } \left( D \right) = \left\{ x _ { 2 } \right\}$ ：“折中”： $P O S _ { c } ^ { N T } \left( D \right) = \left\{ x _ { 1 } , x _ { 4 } , x _ { 5 } , x _ { 6 } \right\}$ ； $B N D _ { C } ^ { N T } \left( D \right) = \left\{ \mathcal { O } \right\}$ ;$N E G _ { C } ^ { N T } \left( D \right) = \{ x _ { 2 } , x _ { 3 } \}$ ：“悲观”： $P O S _ { C } ^ { N T } \left( D \right) = \left\{ x _ { 1 } , x _ { 5 } , x _ { 6 } \right\}$ ； $B N D _ { C } ^ { N T } \left( D \right) = \left\{ x _ { 3 } , x _ { 4 } \right\}$ ;$N E G _ { C } ^ { N T } \left( D \right) = \left\{ x _ { 2 } \right\}$ ：

分析结果发现：尽管患者 $x _ { 6 }$ 的“过敏程度”和“胸闷程度”都未检测到，但在邻域容差关系下却被划分到了 $x _ { 2 }$ 的“扁桃体患者”一类中，导致 $x _ { 2 }$ 被划分到负域中，间接就影响到了 $x _ { 2 }$ 的治疗方案一不治疗，而实际上， $x _ { 2 }$ 的检测项目中有 $7 5 \%$ 是已知的，应该被推荐治疗或延迟治疗。同样的情况也发生在 $x _ { 5 }$ 上，因此，对于不对未知值做任何处理的邻域容差关系而言，并不适用于类似于医疗诊断中伴有缺失数据的混合决策系统。相反，在新的完备邻域容差关系下进行分类诊断就不会出现此类不合理现象。

经过详细计算，在本例中由于实例对象较少，在限制邻域容差关系 $N L$ 和完备邻域容差关系NM下的近似度量结果与在邻域容差关系NT的近似度量结果一致，所以三域划分结果也相同。为避免重复，此处省略。同时也证明了NL和NM也不适用于类似于医疗诊断中出现的不完备混合决策系统。

通过该医疗诊断的实例证明，基于新的完备邻域容差关系的三支决策模型能客观合理地对患者进行医疗诊断，证明了新的完备邻域容差关系对于不完备混合数据处理的合理性和可解释性，扩充了三支决策对此类信息系统的研究范围。

# 4 实验分析与对比

为进一步验证本文方法对处理不完备混合决策系统的有效性和可行性，选取六个UCI混合型数据集进行实验分析。数据集的描述如表7所示。实验运行环境为：Win10，Intel(R)Core(TM),CPUi5-6300HQ2.30 GHz 和 $8 . 0 \mathrm { G B }$ 内存，用Python编程语言在开发平台Pycharm2017.3.4(community edition)上实现。为了便于实验分析和比较，用NTTWD代表邻域容差关系下的三支决策模型，NLTWD代表限制邻域容差关系下的三支决策模型，NMTWD代表完备邻域容差关系下的三支决策模型。本文方法—NRTWD代表新的完备邻域容差关系下的三支决策模型；为保证实验的公平性，以上方法均在曼哈顿距离下进行计算，同时为了消除量纲的影响，对所有的连续型数据进行标准化和归一化，并对同一份数据只通过“折中”阈值设置法做一次阈值的获取。实验将从以下度量函数指标进行分析和比较：

准确率为 $\mathrm { A c c } = { \frac { n _ { p p } } { n _ { p p } + n _ { n p } } }$ 覆盖率为 $\mathrm { C o v } = { \frac { n _ { p p } + n _ { n p } } { n _ { p p } + n _ { b p } + n _ { n p } } }$ 权衡因子为F=2\*AccCov（20误划分损失为 $\mathrm { C o s t } = { n _ { b p } } ^ { * } \lambda _ { b p } + { n _ { n p } } ^ { * } \lambda _ { n p }$ 其中：F代表分类能力；设 $n _ { p p }$ 、 $n _ { b p }$ 、 $n _ { n p }$ 分别为正域、边界域和负域中的对象数； $\lambda _ { b p }$ 和 $\lambda _ { n p }$ 分别为当对象实际属于某类别时被划分到该类别的边界域和负域所造成的损失。以下实验本文均设置 $\lambda _ { b p } = 0 . 3$ ， $\lambda _ { \scriptscriptstyle n p } = 0 . 7$ 。

Therapeutic schedule is provided based on three-way decisions for each patient   
表7UCI数据集描述  
Table 7Descriptions ofUCIdatasets   

<html><body><table><tr><td rowspan="2">数据集</td><td rowspan="2">对象数</td><td colspan="3">属性数</td><td rowspan="2">类别数</td><td rowspan="2">缺失程度</td></tr><tr><td>字符型</td><td>整型</td><td>连续型</td></tr><tr><td>Heart</td><td>270</td><td>0</td><td>8</td><td>5</td><td>2</td><td>0%</td></tr><tr><td>Automobile</td><td>205</td><td>10</td><td>1</td><td>15</td><td>6</td><td>1.2%</td></tr><tr><td>Credit Approval</td><td>690</td><td>9</td><td>0</td><td>6</td><td>2</td><td>0.65%</td></tr><tr><td>Cylinder bands</td><td>540</td><td>20</td><td>0</td><td>20</td><td>2</td><td>4.73%</td></tr><tr><td>Hepatitis</td><td>155</td><td>0</td><td>13</td><td>6</td><td>2</td><td>5.67%</td></tr><tr><td>Horse Colic</td><td>368</td><td>0</td><td>17</td><td>10</td><td>2</td><td>19.39%</td></tr></table></body></html>

# 4.1参数9对本文方法的单调性影响

由定义9可知， $\boldsymbol { \mathscr { s } }$ 的取值决定了邻域参数 $\delta$ 的大小，从而影响近似类的大小，最终影响NRTWD的分类结果，因此，本节将从表7中选取后五个真实缺失的混合数据集进行实验分析，讨论当9从0.1到1.0逐渐递增时，NRTWD的准确率和误分类损失的变化趋势。

$\boldsymbol { \vartheta }$ 对NRTWD的划分准确率的影响如图1所示。由图1可知，NRTWD的划分准确率大致随着 $\mathscr { s }$ 的逐渐增大而增大，除HorseColic 数据集外，其余数据集的Acc整体变化跨度不大，当 $\mathscr { s }$ 从0.5增大到0.6时，Automobile数据集下的Acc从0.9463增大到0.9610，CreditApproval从0.9609 增大到0.9725，HorseColic从0.9130增大到0.9348。但仔细观察发现，当 $\mathscr { s }$ 从0.1增大到O.2时，Cylinder bands下的Acc 却从0.9796降到了0.9444，类似地，该数据在 $\scriptstyle { \mathcal { S } = 0 . 5 \sim 0 . 6 }$ 间也略微下降了，可见9的变化不会引起NRTWD的分类精度的严格地单调性变化。 $\mathscr { s }$ 对NRTWD的误分类损失的影响如图2 所示。由图2可知，在大多数数据集下，NRTWD的误分类损失随着 $\mathscr { s }$ 逐渐增大而大致呈现下降趋势。例如， $\mathscr { s }$ 从0.1增大到1.0的整个过程中，HorseColic下的Cost从42.7不断降到了11.2，CreditApproval从25.9 降到了8.4，Automobile从9.8 降到了2.1,Hepatitis从7.7降到了0.7,而Cylinder bands下的Cost却在 $\scriptstyle { \mathcal { S } } = 0 . 1 \sim 0 . 2$ 时突然从7.7上升到了21，类似情况也发生在 $\scriptstyle { \mathcal { S } } = 0 . 5 \sim 0 . 6$ 间，由此可见， $\boldsymbol { \vartheta }$ 的变化也不会对NRTWD的误分类损失造成严格的单调变化。但总的来说， $\mathscr { s }$ 越大，NRTWD的Acc 越高，Cost越低。

![](images/2cd4b45681dd5dddb3c3825742f43dffe018884d53409248b4018cb32df3ed3b.jpg)  
图19对NRTWD的划分准确率的影响

![](images/a05f0e0ec1410507fe0d9f0d0bea957cbbbf9af72a104ff2284f99bd4180dc2f.jpg)  
Fig.1 Acc curves ofNRTWD varyingwith9   
图2 $\boldsymbol { \mathscr { s } }$ 对 NRTWD 的误分类损失的影响Fig.2 Cost curves ofNRTWD varying with $\scriptstyle { \mathcal { s } }$

# 4.2分类性能分析与比较

本节主要对比五种方法的分类性能。首先，对无缺失的Heart数据集进行随机缺失 $5 \% { \sim } 3 0 \%$ 处理，令 $\scriptstyle { \mathcal { S } } = 1$ ，通过NTTWD、NLTWD、NMTWD和NRTWD方法对其进行实验分析，并将Acc、F和Cost值展示在表8中。然后，通过以上四种方法对表6中除Heart数据集以外的其他真实缺失的数据集进行实验，并将各方法在 $\scriptstyle { \mathcal { S } } = 0 . 6 \sim 1$ 下的Acc、F和Cost的平均值展示在表9中。

如表8所示，对于随机缺失的Heart数据集，从整体情况分析，随着缺失程度不断提高，各方法的Acc和F都不断下降，Cost不断提高，由此可见，随着缺失程度逐渐提高，各方法的分类性能在逐渐降低；但仔细分析发现，NRTWD的Acc 和F值始终要高于、Cost 值始终要低于NTTWD、NLTWD和NMTWD，由此可知，NRTWD受缺失程度的影响要小于其他三种方法。例如，当Heart从缺失 $5 \%$ 到 $30 \%$ 时，NTTWD、NLTWD的Acc下降了 $1 3 . 6 4 \%$ ，F下降了 $7 . 4 1 \%$ ，Cost值上升25.9，NMTWD的Acc和F分别下降了 $1 5 . 5 6 \%$ 和 $8 . 5 \%$ ，而NRTWD的Acc只下降 $10 \%$ ，F只下降 $5 . 3 \%$ Cost只上升18.9。另外可以看到，NTTWD和NLTWD对于heart数据集的分类效果一致，一定程度上说明这两种方法对于不完备混合数据集的分类效果相差不大。

从表9看出，对于真实缺失的UCI数据集，在缺失程度低的Automobile 和 Credit Approval 数据集下，NRTWD 的Acc、F和Cost要优于NTTWD、NLTWD和NMTWD；而在缺失程度高的Cylinder bands、Hepatitis 和Horse Colic 数据集下，NRTWD 略低于NTTWD、NLTWD 和NMTWD，但仍然保持较高的分类效果。同时也可以看到，NTTWD和NLTWD的划分结果在以上所有数据集上是相同的。

综上所述，从理论上分析NLTWD要略优于NTTWD，但实验结果显示NTTWD和NLTWD方法对于大多数缺失程度或大或小的不完备混合数据集的分类结果基本都一致；NRTWD对于同一数据集的分类性能会随该数据的缺失程度逐渐增大而逐渐降低，但始终优于NTTWD、NLTWD和NMTWD，而对于真实缺失的数据集，NRTWD的分类性能在大多数情况下要优于其他方法，因此，结合理论分析和实验对比可知，对于不完备混合数据的处理，NRTWD的分类过程比其他方法更合理，分类效果更优。

表8各方法在Heart数据集下的分类性能对比  
Table 8 Comparison of classification performance of each method   

<html><body><table><tr><td colspan="7">underheart dataset</td></tr><tr><td rowspan="2">度量</td><td rowspan="2">不同关系</td><td colspan="5">缺失程度</td></tr><tr><td>5%</td><td>10%</td><td>15%</td><td>25%</td><td>30%</td></tr><tr><td rowspan="4">Acc</td><td>NTTWD</td><td>0.9926</td><td>0.9481</td><td>0.9519</td><td>0.8630</td><td>0.8556</td></tr><tr><td>NLTWD</td><td>0.9926</td><td>0.9481</td><td>0.9519</td><td>0.8630</td><td>0.8556</td></tr><tr><td>NMTWD</td><td>0.9926</td><td>0.9444</td><td>0.9185</td><td>0.8407</td><td>0.8370</td></tr><tr><td>NRTWD</td><td>0.9926</td><td>0.9593</td><td>0.9593</td><td>0.8741</td><td>0.8926</td></tr><tr><td rowspan="4">F</td><td>NTTWD</td><td>0.9963</td><td>0.9734</td><td>0.9754</td><td>0.9265</td><td>0.9222</td></tr><tr><td>NLTWD</td><td>0.9963</td><td>0.9734</td><td>0.9754</td><td>0.9265</td><td>0.9222</td></tr><tr><td>NMTWD</td><td>0.9963</td><td>0.9714</td><td>0.9575</td><td>0.9135</td><td>0.9113</td></tr><tr><td>NRTWD</td><td>0.9963</td><td>0.9792</td><td>0.9792</td><td>0.9328</td><td>0.9433</td></tr><tr><td rowspan="4">Cost</td><td>NTTWD</td><td>1.4</td><td>9.8</td><td>9.1</td><td>25.9</td><td>27.3</td></tr><tr><td>NLTWD</td><td>1.4</td><td>9.8</td><td>9.1</td><td>25.9</td><td>27.3</td></tr><tr><td>NMTWD</td><td>1.4</td><td>10.5</td><td>15.4</td><td>30.1</td><td>30.8</td></tr><tr><td>NRTWD</td><td>1.4</td><td>7.7</td><td>7.7</td><td>23.8</td><td>20.3</td></tr></table></body></html>

# 5 结束语

三支决策作为知识发现和人工智能领域中一种粒计算方法，近年来许多研究人员对三支决策理论及其应用开展了深入研究。本文分析了不同邻域容差关系下的三支决策模型，并在此基础上，提出了一种新的完备邻域容差关系为不完备混合决策系统构建三支决策模型，定义新的损失函数值计算公式用于获取各对象的乐观、折中和悲观三支阈值，最后给出了面向不完备混合决策系统的乐观、折中和悲观三支决策规则。通过医疗诊断的实例和实验证明，对于不完备混合决策系统的处理，本文所提的三支决策模型较其他模型更加客观合理，分类效果更优；同时，该模型也一定程度上丰富了三支决策的理论研究，合理解释了三支决策在应用领域中的实践意义。在下一步的工作中，本文将研究不完备混合数据系统下的三支属性约简模型，并探索其应用范围。

表9各方法在真实缺失的数据集下的分类性能对比

Table 9Comparison of classification performance of each metho under each truly missing dataset   

<html><body><table><tr><td>度量</td><td>数据集</td><td>NTTWD</td><td>NLTWD</td><td>NMTWD</td><td>NRTWD</td></tr><tr><td rowspan="5">Acc</td><td>Automobile</td><td>0.9571</td><td>0.9571</td><td>0.9571</td><td>0.9747</td></tr><tr><td>Credit Approval</td><td>0.9739</td><td>0.9739</td><td>0.9742</td><td>0.9803</td></tr><tr><td>Cylinder bands</td><td>1.0000</td><td>1.0000</td><td>0.9837</td><td>0.9837</td></tr><tr><td>Hepatitis</td><td>0.9974</td><td>0.9974</td><td>0.9780</td><td>0.9832</td></tr><tr><td>Horse Colic</td><td>1.0000</td><td>1.0000</td><td>0.8745</td><td>0.9457</td></tr><tr><td rowspan="6">F</td><td>Automobile</td><td>0.9780</td><td>0.978</td><td>0.9780</td><td>0.9871</td></tr><tr><td>Credit</td><td>0.9868</td><td>0.9868</td><td>0.9869</td><td>0.9900</td></tr><tr><td>Approval Cylinder bands</td><td>1.0000</td><td>1.0000</td><td>0.9918</td><td>0.9918</td></tr><tr><td>Hepatitis</td><td>0.9987</td><td>0.9987</td><td>0.9888</td><td>0.9915</td></tr><tr><td>Horse Colic</td><td>1.0000</td><td>1.0000</td><td>0.9329</td><td>0.9721</td></tr><tr><td>Automobile</td><td>6.16</td><td>6.16</td><td>6.16</td><td>3.64</td></tr><tr><td rowspan="4">Cost</td><td>Credit</td><td>12.6</td><td>12.6</td><td>12.46</td><td>9.52</td></tr><tr><td>Approval</td><td></td><td></td><td></td><td></td></tr><tr><td>Cylinder bands</td><td>0</td><td>0 0.28</td><td>6.16</td><td>6.16 1.82</td></tr><tr><td>Hepatitis Horse Colic</td><td>0.28 0</td><td>0</td><td>2.38 32.34</td><td>14</td></tr></table></body></html>

# 参考文献：

[1]Yao Y Y.The superiority of three-way decisions in probabilistic rough set models [J]. Information Sciences,2011,181 (6):1080-1096.   
[2]Fujita H,Li Tianrui,Yao Y Y.Advances in three-way decisions and granular computing [J].Knowledge-Based Systems,2016,91:1-3.   
[3]Wang Pingxin,Yao YY.CE3:A three-way clustering method based on mathematical morphology [J].Knowledge-Based Systems,2018,155 (1):54-65.   
[4]Hu Baoqing,Wong H,Yiu K F C.On two novel types of three-way decisions in three-way decision spaces [J]，International Journal of Approximate Reasoning,2017,82:285-306.   
[5]Chen Yumin,Zeng Zhiqiang,Zhu Qing-xin,et al.Three-way decision reduction in neighborhood systems [J].Applied Soft Computing,2016, 38 (1): 942-954.   
[6] Zhang Xianyong，Miao Duoqian．Three-way attribute reducts [J]. International Journal of Approximate Reasoning,2017,88:401-434.   
[7]Yang Xin,Li Tianrui,Fujita H,et al.A unified model of sequential three-way decisions and multilevel incremental processing [J]. Knowledge-Based Systems,2017,134:172-188.   
[8]刘久兵，张里博，周献中，等．直觉模糊信息系统下的三支决策模型 [J]．小型微型计算机系统，2018,39(6):1281-1285.(Liu Jiubing, Zhang Libo, Zhou Xianzhong，et al.Three-way decision model under intuitionistic fuzzy information system environment [J]. Journal of Chinese Computer Systems,2018,39 (6): 1281-1285.）   
[9]Yao Y Y,Wang Shu,Deng Xiaofei. Constructing shadowed sets and three-way approximations of fuzzy sets [J]. Information Sciences,2017, (412-413): 132-153.   
[10]Liang Deicui,Liu Dun.Systematic studies on three-way decisions with interval-valued decision-theoretic rough sets [J]. Information Sciences, 2014,276 (8): 186-203.   
[11] Zhang Hengru,Min Fan.Three-way recommender systems based on random forests [J],Knowledge-Based Systems,2016,91(1) :275-286.   
[12] Li Huaxiong,Zhang Libo,Huang Bing,et al. Sequential three-way decision and granulation for cost-sensitive face recognition [J], Knowledge-Based Systems,2016,91(1): 241-251.   
[13] Nauman M,Azam N,Yao Jingtao.A three-way decision making approach to malware analysis using probabilistic rough sets [J]. Information Sciences,2016,374:193-209,.   
[14] Fermandes V，Yevseyeva I. Mendez JR,etal.A spam filtering multi-objective optimization study covering parsimony maximization and three-way classification [J].Applied Soft Computing,2016,48: 111-123.   
[15] Kryszkiewicz M，Rough set approach toincomplete information systems [J].Information Sciences,1998,112 (1):39-49.   
[16] Stefanowski J,Tsoukias A.On the extension of rough sets under incomplete information [J]. International Journal of Intelligent System, 2000,16 (1): 29-38.   
[17]王国胤.Rough 集理论在不完备信息系统中的扩充[J].计算机研究 与发展,2002,39(10):1238-1243.(Wang Guoyin,Extension of rough set under incomplete information systems [J].Journal of Computer Research and Development,2002,39(10):1238-1243.)   
[18]盛立，杨慧中．基于完备容差关系的扩充粗糙集模型[J].控制与决 策,2008,23 (3): 258-262.(Sheng Li, Yang Huizhong.Extended rough set model based on completed tolerance relation [J]．Control and Decision,2008,23 (3): 258-262.)   
[19]马希骜，王国胤，张清华，等．基于改进的完备容差关系的扩充粗糙 集模型[J].计算机应用,2010,30（7):1873-1877.(Ma Xiao,Wang Guoyin,Zhang Qinghua et al.Extended rough set model based on improved complete tolerance relation [J].Journal of Computer Applications,2010,30(7): 1873-1877.）   
[20] Liu Dun, Liang Deicui,Wang Changchun.A novel three-way decision model based on incomplete information system [J].Knowledge-Based Systems.2016,91 (1): 32-45.   
[21]姚晟，汪杰，徐风，等．不完备邻域粗糙集的不确定性度量和属性约 简[J].计算机应用,2018,38(1):97-10.(Yao Sheng,Wang Jie,Xu Feng，et al. Uncertainty measurement and attribute reduction in incompleteneighborhood rough set [J].Journal of Computer Applications,2018,38(1): 97-103.)   
[22] Zhao Hua,Qin Keyun.Mixed feature selection in incomplete decision table [J]. Knowledge-Based Systems,2014,57 (2): 181-190.