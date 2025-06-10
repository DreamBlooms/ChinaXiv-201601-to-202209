# 多粒度粗糙集粒度权重确定的综合方法

彭连贵，阎瑞霞，陈昭君(上海工程技术大学 管理学院，上海 201620)

摘要：针对现有粒度权重的确定方法主观性较强的问题，提出一种基于粒度信息量的权重确定方法。首先，将信息量引入粗糙集的下近似分布中，定义粗糙集下近似分布中粒度集的信息量；其次，基于信息量定义了粒度的重要度，以粒度的重要度作为启发信息，设计了基于信息量来确定粒度权重的综合方法；通过引入权重系数，决策者根据实际情况选择粒度权重的确定方式：经验主导型、客观主导型。最后，通过实例验证了算法的有效性。分析结果发现，经验主导型的确定方法强化了非核粒度的重要性，客观主导型的确定方法强化了核粒度的重要性。

关键词：多粒度粗糙集；信息量；粒度重要度；权重 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.05.0302

# Synthetic method for granularity weights of multi-granularity rough set

PengLiangui, Yan Ruixia, Chen Zhaojun (SchoolofManagement,Shanghai University ofEngineering Science,Shanghai 201620,China)

Abstract: Inorder toovercome the problem that mostofthemethods for granularity weights hasstrongsubjectivity,this paper proposeda weight determination method based on the granularityinformationquantity.Firstly,the method introduced the informationquantityinto the lower approximatedistributionof therough set.It defined the information quantityof the granularitysetintheapproximatedistributionundertheroughset.Secondly,itdefinedthimportancedegreeoftheraularity based onthe informationquantity.Itused the importance degreeofthe granularityas the heurstic information.Itproposeda synthetic methodbasedonthequantityofinformationtodetermiethe granularityweight.Inthis method,introduceda weight coeffcient.Acording to theactual situation，the decision maker chooses the granularity weight determination mode: empirically-orientedandobjectively-riented.Finally,weuseanexample toverifytheeffctivenesofte metod.Weanalyze results found thattheempirically-orienteddetermined method strengthens the importanceofnon-nuclear granularity,and the objectively-oriented determination method strengthens the importance of nuclear granularity.

Key Words: multi-granularity rough set; information quantity; granularity important degree; weight

# 0 引言

现实的决策过程中,为了合理地评价决策对象,通常会建立一个全面的评价指标体系。在指标选定之后,需要一种行之有效的方法来确定指标权重。指标权重反映了指标在决策过程中重要程度，权重确定方法因此也成为决策和评价领域研究的热点。常用的指标权重确定的方法主要集中在德尔菲法、层次分析法(AHP)[1]、灰色关联分析法、属性重要性排序、朴素贝叶斯方法[2]、环比评分法、主成分分析法等方法上。然而,这些方法一般由专家根据主观性经验给出权重,其知识水平的不同和对于特定粒度的偏好，会影响决策结果的客观性，会额外增加评价代价、分析的时间及空间复杂度。

自Pawla[3提出粗糙集理论以来,凭借其在处理不精确与不完全数据的优势,在决策分析、人工智能、模式识别以及等方面得到了广泛的应用和研究。由于粗糙集具有不需要先验信息的优点,学者们就尝试将粗糙集与决策问题的权重赋值结合起来进行研究。常见的基于粗糙集的权重确定方法有信息熵、模糊决策矩阵、依赖度等方法。

与此同时，Zadeh[4在1979年首次提出并讨论的模糊信息粒化问题之后，粒计算逐渐发展起来.在集合理论和区间分析、模糊集[5]、粗糙集[6]、概率论[7]、熵空间[8]理论等架构内不断地发展.Qian[通过分析粒计算与粗糙集理论之间的关联，将粒计算和粗糙集结合起来并提出动态粒度理念，之后将单粒度粗糙集扩展到多粒度粗糙集.在多粒度粗糙集研究中，粒度权重问题同指标权重一样是研究者研究的热点。Xue等人[10]基于三支决策理论重新定义了属性确定度和约简度,提出了基于三支决策的属性权重构造方法。Meng 等人[1]将信息量引入悲观多粒度粗糙集的下近似分布约简，定义了粒度的重要度，以粒度的重要度作为启发信息,设计了基于信息量的悲观多粒度粗糙集启发式粒度约简算法,但作者并未对粒度权重做进一步的讨论。Wang等人[12]探讨了不同粒度的重要性差异,对决策结果的影响，但其并未给出明确地确定粒度权重的方法。Zhou[13]针对多属性决策问题,从不同粗细粒度的商空间多角度、多层次地综合分析各个属性的重要程度，较为准确地确定属性权重，使决策更为合理。Wang等人[14]提出基于粒计算的犹豫模糊多准则决策方法，通过构造模糊偏好矩阵确定各属性权重。这些方法利用粗糙集及粒计算的知识，立足与获得的数据来确定属性权重.然而，考虑到数据噪音及其他影响因素的存在，单一的考虑客观因素仍有不足。

本文在粗糙集的理论基础上,提出一种基于粒度信息量来确定粒度权重的方法。将通过数据获得的粒度权重与专家经验结合起来，避免过度依赖所得数据，通过主观与客观相结合的方式来确定粒度的综合权重。通过引入的权重系数,决策者在进行决策时可以考虑主要参考的对象,并通过权重系数进行主客观权重占比的调整,确定权重确定的偏移方向。最后给出算例验证了所提方法的有效性,并将主客观偏移情况下确定的粒度权重值进行对比分析发现,经验主导型的确定方法强化了非核属性的重要性,客观主导型的确定方法强化了核粒度的重要性.同时，有效避免了单一方法的不足。

# 1 基础知识

定义1信息系统 $( I S )$ [15]通常定义为一个四元组：$I S = \langle U , A T , V , f \rangle$ 。其中：论域 $U$ 为非空有限全体对象的集合；AT为非空有限属性集合； $\forall a \in A T , V a$ 表示属性 $a$ 的值域;$V$ 为全体属性值域的集合，即 $V = V _ { A T } = \bigcup _ { a \in A T } V _ { a }  { } _ { ; J }$ $f$ 为信息函数，$\forall x \in U , a \in A T$ ， $f ( x , a ) \in V _ { a }$ 表示 $x$ 在属性 $a$ 上的取值。如果$A T = C \bigcup \{ d \}$ ， $C$ 为条件属性集， $d$ 为决策属性，则$\langle U , C \cup \{ d \} , V , f \rangle$ 又被称为决策信息系统 $( D I S )$ 。

定义2设 $I S = \langle U , A T , V , f \rangle$ ， $\forall A \in A T$ ,则 $A$ 上的不可分辨关系定义为[15,16]

$$
I N D ( A ) = \{ ( x , y ) \in U ^ { 2 } : a \in A , f ( x , a ) = f ( y , a ) \}
$$

由式(1)易知,不可分辨关系 $I N D ( A )$ 是 $U$ 上的一个等价关系,根据粒计算的观点：等价关系 $I N D ( A )$ 对应一个粒度, $U$ 上的划分 $U / I N D ( A ) = \{ [ x ] _ { A } : x \in U \}$ 对应一个粒结构或粒度空间,等价类 $[ x ] _ { A }$ 被称为知识粒。

定义3设 $I S = \langle U , A T , V , f \rangle$ 是一个完备决策信息系统[17], $\forall A \in A T$ ， $A = \{ A 1 , A 2 , \dots \cdot , A m \}$ ， $\emptyset \neq X \subseteq U$ ,定义 $U$ 中$X$ 关于 $A 1 , A 2 , \ldots , A m$ 的下近似和上近似集分别定义为

$$
\sum _ { i = 1 } ^ { m } A _ { i } ( X ) = \{ x \in U \mid [ x ]  \in X , i \leq m \} ,
$$

$$
\overbrace { \sum _ { i = 1 } ^ { m } A _ { i } ( X ) } ^ { m } = \sim \sum _ { i = 1 } ^ { m } A _ { i } ( \sim X ) .
$$

定义4设 $I S = \langle U , A T \cup D , V , f \rangle$ 是一个完备决策信息系统 $[ \mathrm { ~ 1 ~ 1 ~ } ]$ ， $A 1 , A 2 , \ldots , A m \subseteq A T , A = \{ A 1 , A 2 , \ldots , A m \}$ $U / D = \{ Y 1 , Y 2 , . . . , Y r \}$ ，定义

$$
I ( A / D ) = 1 - \frac { 1 } { \mid U \mid ^ { 2 } } { \sum _ { j = 1 } ^ { r } } \big | \bigcap _ { A i \in A } \underline { { A } } ( Y _ { j } ) \big | ^ { 2 }
$$

为粒度集 $A$ 下的信息量，这里·表示集合的基数。

定义5设 $I S = \langle U , A T \cup D , V , f \rangle$ [11]是一个完备决策信息系统， $A 1 , A 2 , \ldots , A m \subseteq A T , A = \{ A 1 , A 2 , \ldots , A m \}$ $U / D = \{ Y 1 , Y 2 , . . . , Y r \}$ ,粒度 $A i$ 在粒度集 $A$ 中的重要度定义为

$$
S G F ( A i , A ) = I ( A / D ) - I ( A - \{ A i \} \mid D )
$$

粒度 $A i \in A$ ，在粒度集 $A$ 中是必要的，当且仅当$S G F ( A i , A ) > 0$ 。

定义6粒度集 $A$ 的核定义为[11]$C o r e ( A ) = \{ A i \in A | S G F ( A i , A ) > 0 \}$

# 2 基于信息量确定粒度权重的综合方法

本方法基于粒度集信息量定义粒度重要度,并设计了多粒度粗糙集的下近似分布粒度权重确定的综合方法。基本思路是首先计算粗糙集的下近似分布,计算不同粒度的信息量。通过逐个去除粒度，观察信息量变化的情况.对于信息量变化大的粒度，对于决策的重要度就大;反之,引起信息量变化小的粒度,重要度就小.以粒度重要度作为启发信息,对粒度重要度进行归一化处理,进而获得各粒度的权重值：

$$
\omega ( A i ) = { \frac { S G F ( A i , A ) } { \displaystyle \sum _ { i = 1 } ^ { m } S G F ( A i , A ) } }
$$

考虑到此方法忽略专家经验的作用，为能够科学的进行评价，综合考虑粒度权重，因此引入权重参数λ.通过给出的权重系数调节主客观偏向问题，使得属性权重的确定更合理，决策更科学。现基于数据集本身给出参数 $\lambda$ 的定义：

$$
\lambda = \mid \frac { \mid C o r e ( A ) \mid } { \mid A \mid } - 0 . 5 \mid
$$

$\left| C o r e ( A ) \right|$ 表示粒度集 $A$ 的核的基.当不存在核粒度时,

${ \frac { | C o r e ( A ) | } { | A | } } = 0$ ;当全部粒度都为核粒度时 $\frac { | C o r e ( A ) | } { | A | } { = 1 }$ （2因为0≤ $0 \le \frac { \vert C o r e ( A ) \vert } { \vert A \vert } \le 1$ ，所以 $0 \leq \big | \frac { \vert C o r e ( A ) \vert } { \vert A \vert } - 0 . 5 \vert \leq 0 . 5$ 即 $\lambda \in [ 0 , 0 . 5 ]$ .由此可以得到粒度权重确定的综合算法公式为

a）经验主导型：

$$
\alpha _ { \mu } ( A _ { i } ) = \lambda \omega ( A _ { i } ) + ( 1 - \lambda ) \mu ( A _ { i } )
$$

b）客观主导型：

$$
\alpha \omega ( A i ) = ( 1 - \lambda ) \omega ( A i ) + \lambda \mu ( A i )
$$

其中： $\omega ( A _ { i } )$ 表示根据客观数据计算出的粒度权重, $\mu ( A i )$ 表示专家根据经验给出的粒度权重.

# 算法1

输入：完备决策信息系统 $I S = \langle U , A T \cup D , V , f \rangle$ ，$A 1 , A 2 , \ldots , A m \subseteq A T , A = \{ A 1 , A 2 , \ldots , A m \} \ \circ$ （20

输出：决策信息系统各粒度的客观权重 $\omega ( A i )$ 。

a)对于每一个 $A i \in A$ ,计算 $U / A i , U / D$

b)在每一个粒度空间 $U \ / \ A _ { i }$ 和 $\forall Y j \in U / D$ 下，计算 $\underline { { A i } } ( Y _ { j } )$ ，$I ( A / D )$

c)依次剔除 $A i$ ，并在 $U \ : / \left( A - A i \right)$ 和 $\forall Y _ { j } \in U / D$ 下,计算$I ( A - \{ A i \} / D )$

d)计算各粒度 $A i$ 的重要度：

$$
C o r e ( A ) = \{ A i \in A | S G F ( A i , A ) \}
$$

e)计算各粒度 $A i$ 的客观权重值及权重参数 $\lambda$ ：

$$
\omega ( A i ) = \frac { S G F ( A i , A ) } { \displaystyle \sum _ { i = 1 } ^ { m } S G F ( A i , A ) } , \lambda = \vert \frac { \vert C o r e ( A ) \vert } { \vert A \vert } - 0 . 5 \vert
$$

算法2各粒度权重的综合评价值

输入：由专家给出各粒度的主观权重值 $\mu ( A i )$ 和算法1得出的客观权重值 $\omega ( A _ { i } )$ 及 $\lambda$ 。

输出：各粒度的综合评价权重值 $\alpha _ { \mu } ( A _ { i } )$ 或 $\alpha _ { \omega } ( A _ { i } )$ 。

经验主导型： $\alpha _ { \mu } ( A i ) = \lambda \omega ( A i ) + ( 1 - \lambda ) \mu ( A i )$ ,否则转到客观主导型。

客观主导型: $\alpha _ { \omega } ( A i ) = ( 1 - \lambda ) \omega ( A i ) + \lambda \mu ( A i )$ 。

# 3 算例分析

某公司现面临一个投资问题,制定了8个投资方案作为备选，公司邀请专业内的专家对这8个方案进行评价，每位专家根据评价指标 $A i ( i = 1 , . . . , 5 )$ 对方案 $x _ { j }$ $( j = 1 , . . . , 8 )$ 进行评估,其中评价指标被分成5类 $e = \{ 1 , 2 , 3 , 4 , 5 \}$ ,分别表示 $\scriptstyle \mathbf { e } = \left\{ \begin{array} { l l } { \begin{array} { r l r l } \end{array} } \end{array} \right.$ 很好,好，一般,稍差,差}。表 $1 ^ { [ 9 ] }$ 是由专家给出的关于公司投资方案的评估表。将这个评估表看做一个完备决策信息系统$I S = \langle U , A T \cup D , V , f \rangle$ ，并用等价关系构造每个方案X $ { j } ( j = 1 , . . . , 8 )$ 的等价类,将每个评价指标的评估方案看成一个粒度空间。令 $D = \{ 0 , 1 \} , 1$ 表示为yes 决策,0代表no 决策。在多粒度空间下基于信息量确定不同粒度的权重大小，决策信息系统的粒度集 $A = \{ A 1 , A 2 , A 3 , A 4 , A 5 \}$ ，决策属性 $D$ $U / D = \{ Y 1 , Y 2 \}$ 。

表1公司投资方案表  

<html><body><table><tr><td>Plan</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td><td>D</td></tr><tr><td>X1</td><td>1</td><td>3</td><td>1</td><td>1</td><td>3</td><td>1</td></tr><tr><td>X</td><td>2</td><td>2</td><td>3</td><td>2</td><td>3</td><td>1</td></tr><tr><td>X</td><td>3</td><td>3</td><td>1</td><td>3</td><td>4</td><td>1</td></tr><tr><td>X4</td><td>4</td><td>4</td><td>3</td><td>5</td><td>2</td><td>0</td></tr><tr><td>X5</td><td>5</td><td>1</td><td>5</td><td>5</td><td>4</td><td>0</td></tr><tr><td>X6</td><td>4</td><td>5</td><td>5</td><td>4</td><td>5</td><td>0</td></tr><tr><td>X7</td><td>1</td><td>1</td><td>2</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Xs</td><td>4</td><td>5</td><td>4</td><td>4</td><td>2</td><td>0</td></tr></table></body></html>

a）根据算法1的StepI计算可得

$$
U / D = \left\{ Y 1 , Y 2 \right\} , Y 1 = \left\{ X 1 , X 2 , X 3 , X 7 \right\} , Y _ { 2 } = \left\{ X 4 , X 5 , X 6 , X 8 \right\}
$$

$$
\begin{array} { l } { { U / A = \{ \{ x _ { 1 } \} , \{ x _ { 2 } \} , \{ x _ { 3 } \} , \{ x _ { 4 } \} , \{ x _ { 5 } \} , \{ x _ { 6 } \} , \{ x _ { 7 } \} , \{ x _ { 7 } \} , \{ x _ { 7 } \} } } \\ { { U / A _ { 1 } = \{ \{ x _ { 1 } , x _ { 7 } \} , \{ x _ { 2 } \} , \{ x _ { 3 } \} , \{ x _ { 4 } , x _ { 6 } , x _ { 8 } \} , \{ x _ { 5 } \} \} , } } \\ { { U / A _ { 2 } = \{ \{ x _ { 1 } , x _ { 2 } \} , \{ x _ { 3 } \} , \{ x _ { 4 } \} , \{ x _ { 5 } , x _ { 7 } \} , \{ x _ { 6 } , x _ { 8 } \} \} } } \\ { { U / A _ { 3 } = \{ \{ x _ { 1 } , x _ { 3 } \} , \{ x _ { 2 } , x _ { 4 } \} , \{ x _ { 5 } , x _ { 6 } \} , \{ x _ { 7 } \} , \{ x _ { 8 } \} \} } } \\ { { U / A _ { 4 } = \{ \{ x _ { 1 } , x _ { 7 } \} , \{ x _ { 2 } \} , \{ x _ { 3 } \} , \{ x _ { 4 } , x _ { 5 } \} , \{ x _ { 6 } , x _ { 8 } \} \} } } \\ { { U / A _ { 5 } = \{ \{ x _ { 1 } , x _ { 2 } \} , \{ x _ { 3 } , x _ { 5 } \} , \{ x _ { 4 } , x _ { 8 } \} , \{ x _ { 6 } \} , \{ x _ { 7 } \} \} } } \end{array}
$$

b）由算法1的 $_ { \pmb { b } ) \pmb { c } ) }$ 计算得:

$$
I ( A / D ) = \frac { 5 9 } { 6 4 } ; I ( A - A _ { } 1 / D ) = \frac { 5 9 } { 6 4 } ;
$$

$$
I ( A - A _ { 2 } / D ) = \frac { 5 6 } { 6 4 } ; I ( A - A _ { } 3 / D ) = \frac { 5 1 } { 6 4 } ;
$$

$$
I ( A - A 4 / D ) = \frac { 5 9 } { 6 4 } ; I ( A - A 5 / D ) = \frac { 5 6 } { 6 4 }
$$

c）由算法1的 $\mathbf { \Delta } \mathbf { \mathcal { A } } )$ 得

$$
S G F ( A 1 , A ) = S G F ( A 4 , A ) = 0
$$

$$
S G F ( A 2 , A ) = S G F ( A 5 , A ) = \frac { 3 } { 6 4 } ;
$$

$$
S G F ( A 3 , A ) = \frac { 8 } { 6 4 } ; C o r e ( A ) = \{ A 2 , A 3 , A 5 \}
$$

d）由算法1的 $\mathbf { \sigma } _ { f } )$ 得各粒度 $A i$ 的客观权重值（Obj）及权重参数 $\lambda$ ：

$$
\omega ( A 1 ) = \omega ( A 4 ) = 0 ; \omega ( A 2 ) = \omega ( A 5 ) = 0 . 2 1 4 ;
$$

$$
\omega ( A 3 ) = 0 . 5 7 2 ; \lambda = 0 . 1
$$

e）根据算法2得到：各粒度 $A i$ 的主观权重值（ $S u b$ ）$\mu ( A 1 ) = 0 . 1 ~ ; ~ \mu ( A 2 ) = 0 . 1 5 ~ ; ~ \mu ( A 3 ) = 0 . 5 ~ ; ~ \mu ( A 4 ) = 0 . 1$ $\mu ( A 5 ) = 0 . 1 5$ 。进而得到

（a）经验主导型：  
$\alpha _ { u } ( A 1 ) = 0 . 0 9 ; \alpha _ { u } ( A 2 ) = 0 . 1 5 6 4 ;$ （20  
$\alpha _ { \mu } ( A _ { 3 } ) = 0 . 5 0 7 2 ; \alpha _ { \mu } ( A _ { 4 } ) = 0 . 0 9 ; \alpha _ { \mu } ( A _ { 5 } ) = 0 . 1 5 6 4$ (b）客观主导型:  
$\alpha _ { \omega } ( A _ { 1 } ) = 0 . 0 1 ; \alpha _ { \omega } ( A _ { 2 } ) = 0 . 2 0 7 6 ;$ （20  
$\alpha _ { \omega } ( A _ { 3 } ) = 0 . 5 6 4 8 ; \alpha _ { \omega } ( A _ { 4 } ) = 0 . 0 1 ; \alpha _ { \omega } ( A s ) = 0 . 2 0 7 6$

![](images/609956a224d0dcc68ee16aed558d671fadfc86981e0728b3b6d7e868bdb33208.jpg)  
图1经验主导型与客观主导型求得粒度权重对比

通过图1的权重值对比分析可以发现：

a）两种方法求得的粒度权重中,核粒度的权重大于非核粒度的权重,即 $\alpha _ { ( \mu , \omega ) } ( A _ { 3 } ) > \alpha _ { ( \mu , \omega ) } ( A _ { 2 } ) =$ $\alpha _ { ( \mu , \omega ) } ( A 5 ) > \alpha _ { ( \mu , \omega ) } ( A 1 ) = \alpha _ { ( \mu , \omega ) } ( A 4 )$ ,用权重大小来确定一种优先顺序关系为 $\{ A 3 \} \succ \{ A 2 , A 5 \} \succ \{ A 1 , A 4 \}$ 。

b）从图中数据可以看出在核粒度的权重上$\alpha _ { \infty } ( A _ { 3 } ) > \alpha _ { \scriptscriptstyle \mu } ( A _ { 3 } ) , \alpha _ { \scriptscriptstyle \omega } ( A 2 ) = \alpha _ { \scriptscriptstyle \omega } ( A 5 ) > \alpha _ { \scriptscriptstyle \omega } ( A 2 ) = \alpha _ { \scriptscriptstyle \omega } ( A 5 )$ .观察在非核粒度的权重上,可以得到$\alpha _ { \mu } ( A 1 ) = \alpha _ { \mu } ( A 4 ) > \alpha _ { \omega } ( A 1 ) = \alpha _ { \omega } ( A 4 )$ ,经验主导型计算权重的方法强化了非核粒度的重要性.客观主导型算法强化了核粒度的重要性。可以知道经验主导型、客观主导型各粒度权重的方差分别为 $R _ { \mu } = 0 . 0 2 4 4 7 5$ ， $R _ { \omega } = 0 . 0 4 1 0 9$ 。经验主导型的计算方法求得的权重值离散程度小，更倾向于为每个粒度赋予同样的权重，弱化各粒度之间的差异性.间接导致对非核粒度的强化，对核粒度的弱化。

c)现实决策过程中，决策者选定的指标都具有不可替代性。在单一的权重确定方法中,往往会出现权重为零的现象。显然,具有不合理性。文章提出的综合确定方法有效避免了冗余指标权重为0的情况；不仅如此,综合方法求得的权重具有保留了单一方法波动的特性，反应信息比原有方法更加全面。

d)方差是衡量随机变量或一组数据时离散程度的度量，对比主观型（Sub）、客观型（Obj）、经验导向型（μ）、客观导向型（ $\omega$ ）等四种方法求得的各指标权重的方差，分析其差异性（ $\varepsilon \mathrm { ~ . ~ }$ )。通过数学计算得到： $\mathcal { E } \mu = 0 . 0 2 3$ ， $\varepsilon \omega = 0 . 4 3 8$ ，$\mathcal { E } s u b = 0 . 0 2 4 5$ ， $\mathcal { E } o b j = 0 . 0 4 1 1$ ．差异性大小对比为$\mathcal { E } \mu < \mathcal { E } s u b < \mathcal { E } o b j < \mathcal { E } \omega \ ,$ 0

从各种方法的差异性（ $\varepsilon$ ）的值对比发现纯主观方法求得的各指标权重差异性最小,相似性较大,不能够很好地表现指标的不同;由经验主导型计算方法算得的粒度权重值波动情况稍大于纯主观性方法,各粒度之间差异性相比于客观主导型仍然不足.而由客观主导型计算方法得到的粒度权重值波动较大,各粒度之间差异较大,更能表达各粒度之间的差异性，能够很好地表现出各指标的不同.虽然,这种方法看起来更接近现实情况,但在实际的决策情况下要根据决策对象选择适宜的方法.此外，虽然纯客观的计算方法求得的差异值最大，但这种方法过多的依赖得到的数据，忽略专家经验,显然具有不合理性,如医药行业，专家经验具有不容忽视的作用.综合来看无论是经验主导型，还是客观主导性的计算方法都优于纯主观或纯客观的计算方法，具有更大的灵活性,考虑的情况也更全面.

# 4 结束语

决策问题中,针对单一指标权重确定方法中的不足，文章提出一种基于信息量的多粒度粗糙集粒度权重确定的综合算法.该算法以粒度重要度为启发信息,来确定粒度的客观权重.通过引入权重系数λ,解决决策过程中过度依赖一种权重的问题.此权重确定的方式，能够根据决策者的现实需求来选择权重确定的公式,具有很大的灵活性和全面性.同时，该方法很好的避免指标权重为0的情况.文章通过一个简单的算例来说明算法的有效性，比较了经验主导型以及客观主导型确定粒度权重的不同情况.结果发现经验主导型强化了非核粒度的重要性，客观主导型算法强化了核属性的作用.不仅如此,综合权重方法克服了单一方法在权重确定上不够全面的问题.

# 参考文献：

[1]万荣，阎瑞霞．基于粗糙集和模糊层次分析法的客户需求权重确定方 法[J].科技管理研究,2018,38(4):204-208.(Wan Rong,Yan Ruixia. Method for determining customer demand weight based on rough set and FAHP[J]. Science and Technology Management Research,2018,38 (4): 204-208.)   
[2] 张伟，王志海，原继东，等．一种局部属性加权朴素贝叶斯分类算法 [J]．北京交通大学学报,2018,42(02):14-21.(ZhangWei,Wang Zhihai, Yuan Jidong,et al.A locally attribute weighted naive Bay-es classifier [J]. Journal ofBeijing Jiaotong University,2018,42(02): 14-21.)   
[3]Pawlak Z.Rough sets [J]. International Journal of Computer and Information Sciences.1982,11:341-356   
[4]Zadeh LA.Fuzzy sets and information granularity [C]//Advances in Fuzzy

Set Theory and Applications.1996:3-18.

[5]胡谦，米据生．多粒度模糊粗糙集的表示与相应的信任结构[J].计算 机工程与应用,2017,53 (19):51-54.(Hu Qian,MiJusheng.Representation of multigranularity fuzzy rough sets and corresponding belief structure [J]. Computer Engineering and Applications,2017,53(19):51-54.)

[6]骆公志，钱佳丽．基于多阈值的变精度邻域多粒度粗糙决策方法 [J/OL].计算机应用研究,2018,35(10).[2018-07-11].http://kns.cnki. net/kcms/detail/51.1196.TP.20171010.1730.048.html.(Luo Gongzhi, Qian Jiali. Neighborhood multi-granulation rough set based on multithreshold for variable precision decisions [J].Application Research of Computers，2018，35(10)．[2018-07-11].http://ns.cnki. net/kcms/detail/51.1196.TP.20171010.1730.048.html.)

[7]张清华，郭永龙，薛玉斌.概率统计下的多粒度搜索算法研究[J].模 式识别与人工智能,2015,28(5): 422-428.(Zhang Qinghua,Guo Yonglong, Xue Yubin.Multi-granularity Search Algorithm Based on Probability Statistics [J].Pattern Recognition and Artificial Intelligence,2015,28 (5): 422-428. )

[8]熊升华，吴胜，陈振颂，等．广义直觉模糊熵及其在权重确定中的应用 [J].控制与决策，2017,32(5):845-854.(Xiong Shenghua,Wu Sheng, Chen Zhensong,et al.Generalized intuitionistic fuzzy entropy and its application in weight determination [J]. Control and Decision,,2017,32(5): 845-854.)

[9] 钱宇华．基于粗糙集的粒度计算理论与方法研究[D]．太原：山西大学, 2005.(Qian Yuhua.Research on theory and method of granularity computing based on rough set [D]. Taiyuan: Shanxi University, 2005.)

[10]薛占熬，朱泰隆，薛天宇，等.基于三支决策理论的条件属性权重构造 方法[J].计算机科学，2015,42(8):265-268,272.(Xue Zhanao,Zhu Tailong,Xue Tianyu,et al.Methodology of attribute weights acquisition based on three-way decision theory [J]. Computer Science,2015,42 (08): 265-268,272.)

[11]孟慧丽，马媛媛，徐久成．基于信息量的悲观多粒度粗糙集粒度约简 [J].南京大学学报：自然科学版,2015,51(2):343-348.(MengHuili,Ma Yuanyuan,Xu Jiucheng.The granularity reduction of pessimistic multigranulation [J]. Journal of Nanjing University:Natural Sciences,2015,51 (02): 343-348.)

[12]汪小燕，沈家兰，申元霞．基于加权粒度和优势关系的程度多粒度粗糙 集[J].山东大学学报：理学版，2017,52(3):97-104.(Wang Xiaoyan, Shen Jialan, Shen Yuanxia. Graded multi-granulation rough set based on weighting granulations and dominance relation [J]. Journal of Shandong University: Natural Science,2017,52 (03): 97-104.)

[13]周丹晨．采用粒计算的属性权重确定方法[J]．智能系统学报,2015,10 (2):273-280.(Zhou Danchen.A method for ascertaining the weight of attributes based on granular computing [J].CAAI Trans on Intelligent Systems,2015,10(2):273-280.)

[14]王宝丽，梁吉业，胡运红．基于粒计算的犹豫模糊多准则决策方法[J]. 模式识别与人工智能,2016,29(3):252-262.(Wang Baoli,Ling Jiye,Hu Yunhong.Granular computing based hesitant fuzzy multi-criteria decision making [J]. Pattern Recognition and Artificial Intelligence,2016,29 (3): 252-262. )

[15]张明，程科，杨习贝，等.基于加权粒度的多粒度粗糙集[J].控制与 决策,2015,30 (2): 222-228.(Zhang Ming,Cheng Ke, Yang Xibei,et al. Multi-granulation rough set based on weighted granulations [J],Control and Decision,2015,30(2):222-228.)

[16]Xu W H, Sun W X,Zhang X Y,et al.Multiple granulation rough set approach to ordered information systems [J].International Journal of General Systems,2012,41 (5): 475-501.

[17]黄卫华．多粒度粗糙集模型[J].西南师范大学学报：自然科学版,2017, 42 (5):137-143.(Huang Weihua. On a Multi-granulation rough set [J]. Journal of Southwest China Normal University: Natural Science Edition, 2017,42 (05):137-143.)