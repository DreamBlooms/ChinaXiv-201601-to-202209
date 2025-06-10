# 基于NT降阶的乘积型区间二型模糊控制器结构分析

施建中，李荣，杨勇，梁绍华(南京工程学院 能源与动力工程学院，南京 211167)

摘要：目前区间二型模糊控制器的结构分析主要基于Zadeh的取小推理和KM降阶算法。KM算法是一循环迭代过程，没有解析解，无法进行控制器的稳定性分析，且取小推理需要进行输入空间的划分，过程较为繁琐。提出了一种简化的区间二型模糊控制器分析方法，该方法首先采用乘积推理，模糊规则的激发隶属度为输入变量隶属度的乘积，统一了控制器的表达式形式，避免了输入空间的划分过程，模糊控制器的结构分析更加简单。二型模糊集合采用 NT降阶算法，该算法直接利用首隶属度函数的上、下限的平均值来进行解模糊化操作，避免了迭代计算，简化了降阶过程。控制器的表达式等效于一个增量式PI（位置式PD）控制器，其比例增益、积分增益以及补偿项均为非线性可调。而且还能得到控制器的闭环表达式，易于进行区间二型模糊控制器的稳定性分析与设计等。

关键词：区间二型模糊控制；KM降阶；NT降阶；乘积推理；结构分析中图分类号： $\mathrm { T P } 2 7 3 { + } . 4$ doi:10.3969/j.issn.1001-3695.2017.10.0782

# Structural analysis of product interval two fuzzy controller using NT type reduction

Shi Jianzhong, Li Rong, Yang Yong, Liang Shaohua (School ofEnergy&Power Engineering,Nanjing InstituteofTechnology,Nanjing 21l167,China)

Abstract: The structure analysis ofinterval type2fuzzycontroleris basedon Zadeh's min inference andKMtypereduction, whichisaniterativeprocesswitoutanalyticalsoutionforthtabilityanalysisofcontrollr,andinputspacedividingisadopted under min inference,thus the process is tedious.Thia paper proposed asimplify structure analysis method inthisarticle,used theproduct inference,thefuzzyrules fired membershipfunctionofwhichobtainedbythe productofthe membershipdegree of theinput variable.Itunifiedtheexpressionofcontrolerandavoided division processofiput space,andthe structureanalysis offuzzycontroler was more simple.Itused NTtypereductionalgorithm inthis method,which defuzificationbythe average ofupper and lower limitsoffirst membership function,avoided iterative processand simplified type reduction process The controller expression was equivalent toan incrementalPIcontroller(or positionPDcontroler）with nonlinearadjustable proportionalgain,integralainandompensationterm.Moreover,theclosed-loopexpresionofthecontrollercouldbobtained, and the stability analysis and design of the controller were easy to be carried out.

Key Words: interval type 2 fuzzycontrol; KM typereduction; NTtype reduction; product inference; structure analysis

# 0 引言

随着区间二型模糊集合理论的研究深入，区间二型模糊控制系统在很多实际应用中都优于传统的一型模糊控制系统。为什么区间二型模糊控制器具有较好的控制效果，很多学者对区间二型模糊控制器的结构进行了详细的分析。目前常见的区间二型模糊控制器的分析来源于一型模糊控制器的结构分析，将模糊系统的输入变量的空间划分为若干个区间，每个区间对应不同的模糊规则激发隶属度[1\~3]。区间二型模糊控制器和传统一型模糊控制器的重要区别就是存在降阶过程，区间二型模糊控制器表达式的推导还需要考虑降阶问题。

Du等人[4利用输入空间划分的方法，将所有的模糊规则都考虑取平均，得到了区间二型模糊PI（PD）控制器的一般表达式。该方法的一个好处就是避免了降阶过程，但要处理的模糊规则数较多，达到了16条。Nie等人5利用常见的区间二型模糊集合KM降阶算法，分析得到了区间二型模糊PI和PD控制器的一般表达式。

文献[4,5]采用的区间二型模糊控制器的首隶属度函数都是对称的线性形式，采用的都是Mamdani 模糊控制的结构。而Zhou等人将区间二型模糊器的首隶属度函数进行了扩展，同样将输入空间进行划分，采用KM降阶算法，得到了更一般的线性区间二型Mamdani模糊控制的结构形式[和T-S模糊控制器形式[7]。文献[8]针对区间二型模糊控制器采用非线性的首隶属度函数进行了分析，得到了具有非线性形式首隶属度函数的区间二型模糊PI（PD）控制器的一般结构。文献[9]提出了一种基于乘积型的二型模糊控制器的结构，针对对称线性的首隶属度函数和KM降阶算法，得到了此种情况下区间二型模糊控制器的解析结构推导。

除了文献[4]以外，文献[5\~9]都采用了KM降阶算法，但是KM降阶算法是目前区间二型模糊集合降阶算法中效率最低的，虽然有很多效率更高的降阶算法，如EKM[I0]、EIASC[1I]、ODS[12]等，但这些算法的本质与KM一样，都是求取两个切换点以得到降阶的两个端点，在取平均值得到降阶结果。除了文献[9]以外，文献[4\~8]在模糊推理部分都采用的Zadeh的AND推理，也即取小，那么该过程需要将输入空间进行划分，根据参数的不同，划分的区间个数也不同，分析的空间数量较多，每个输入空间对应不同的控制器表达式，过程也较为繁杂。

本文采用乘积型模糊推理，避免了对输入空间进行划分，大大减少了控制器表达式的求取量，在降阶部分采用NT降阶算法[13]，既避免了KM降阶算法的重复迭代过程，也避免了文献[4]的取平均过程，分析过程进一步简化。

# 1 区间二型模糊集合首隶属度函数

一般模糊控制器的输入都选择为误差 $e$ 和误差的变化率 $\dot { e }$ (de/dt)，输出为控制器的增量 $\Delta u$ 。前件为两个输入各定义的模糊变量，后件为单值或者多项式形式，分别对应了Mamdani和T-S 模糊控制器。本文采用三角型首隶属度函数，其模糊变量的定义如图1和2所示。

![](images/4af80a0d7a8ae0d5a3a5ccb1b863ebc49bfa2b93c4d4368fedb84a43dd24c964.jpg)  
图1误差首隶属度函数

![](images/5e9e4fe0ddd6c0079bb759e58505ca6606e78968b3e28893e0a35ce84df44dc0.jpg)  
图2误差变化率首隶属度函数

由图1和2的定义，本区间二型模糊控制器一共有 $m { \times } n$ 条规则。区间二型模糊集合的不确定域通过参数 $p _ { i }$ 和 $q _ { i }$ 实现。

大多数区间二型模糊控制器为了简化起见，后件参数选择单一值。通常情况下，笔者认为任意的误差和误差变化率同时只激活相邻的两个模糊集合，且相邻两个模糊集合的隶属度函数上限之和为1。那么实际上，每次推理只激活四条模糊规则如下：

规则1if $e$ is $\tilde { A } _ { i }$ and $\dot { e }$ is ${ \tilde { B } } _ { i }$ ， then △u=H(i,i)=y1   
规则2ifeis Aand éis Bi+1 then $\Delta u { = } H ( i , i { + } 1 ) { = } y _ { 2 }$   
规则3if $e$ is $\tilde { A } _ { i + 1 }$ and $\dot { e }$ is ${ \tilde { B } } _ { i }$ ， then $\Delta u = H ( i + 1 , i ) = y _ { 3 }$ （20   
规则4ifeis A+andéis Bi+1, then $\Delta u { = } H ( i { + } 1 , i { + } 1 ) { = } y _ { 4 }$ （204号

对于误差来说，定义在区间 $[ L _ { \mathrm { i } } , L _ { \mathrm { i + l } } ]$ 相邻两个模糊集合 $\tilde { A } _ { i }$ 和$\tilde { A } _ { i + 1 }$ 的上、下隶属度函数如式（1）～（4）所示。

$$
\underline { { u } } _ { \tilde { A _ { i } } } ( e ) = \frac { p _ { i } \times ( e - L _ { i + 1 } ) } { L _ { i } - L _ { i + 1 } } = p _ { i } \times ( a _ { i } \times e - b _ { i } )
$$

$$
\overline { { \boldsymbol { u } } } _ { \tilde { \boldsymbol { A } } _ { i } } \left( \boldsymbol { e } \right) = \frac { ( \boldsymbol { e } - \boldsymbol { L } _ { i + 1 } ) } { \boldsymbol { L } _ { i } - \boldsymbol { L } _ { i + 1 } } = \boldsymbol { a } _ { i } \times \boldsymbol { e } - \boldsymbol { b } _ { i }
$$

$$
\underline { { u } } _ { \tilde { A } _ { i + 1 } } \left( e \right) = \frac { p _ { i + 1 } \times ( e - L _ { i } ) } { L _ { i + 1 } - L _ { i } } = p _ { i + 1 } \times ( a _ { i + 1 } \times e - b _ { i + 1 } )
$$

$$
\overline { { u } } _ { \tilde { A } _ { i + 1 } } \left( e \right) = \frac { \left( e - L _ { i } \right) } { L _ { i + 1 } - L _ { i } } = a _ { i + 1 } \times e - b _ { i + 1 }
$$

其中：

$$
a _ { i } = \frac { 1 } { L _ { i } - L _ { i + 1 } } , b _ { i } = \frac { L _ { i + 1 } } { L _ { i } - L _ { i + 1 } } ,
$$

$$
a _ { i + 1 } = \frac { 1 } { L _ { i + 1 } - L _ { i } } , b _ { i + 1 } = \frac { L _ { i } } { L _ { i + 1 } - L _ { i } }
$$

对于误差变化率来说，定义在区间 $[ S _ { j } , S _ { j + 1 } ]$ 相邻两个模糊集合 $\tilde { B } _ { j }$ 和 $\tilde { B } _ { j + 1 }$ 的上、下隶属度函数如式（5）～（8）所示。

$$
{ \underline { { u } } } _ { \tilde { B _ { j } } } ( \dot { e } ) = { \frac { q _ { j } \times ( \dot { e } - S _ { j + 1 } ) } { S _ { j } - S _ { j + 1 } } } = q _ { j } \times ( c _ { j } \times \dot { e } - d _ { j } )
$$

$$
\overline { { u } } _ { \overset { . } { B _ { j } } } ( \dot { e } ) = \frac { ( \dot { e } - S _ { j + 1 } ) } { S _ { j } - S _ { j + 1 } } = c _ { j } \times \dot { e } - d _ { j }
$$

$$
\underline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) = \frac { q _ { j + 1 } \times ( \dot { e } - S _ { j } ) } { S _ { j + 1 } - S _ { j } } = q _ { j + 1 } \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } )
$$

$$
\overline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) = \frac { ( \dot { e } - S _ { j } ) } { S _ { j + 1 } - S _ { j } } = c _ { j + 1 } \times \dot { e } - d _ { j + 1 }
$$

其中：

$$
c _ { j } = \frac { 1 } { S _ { j } - S _ { j + 1 } } , d _ { j } = \frac { S _ { j + 1 } } { S _ { j } - S _ { j + 1 } } ,
$$

$$
c _ { j + 1 } = \frac { 1 } { S _ { j + 1 } - S _ { j } } , d _ { j + 1 } = \frac { S _ { j } } { S _ { j + 1 } - S _ { j } }
$$

由区间二型模糊逻辑系统的推理过程，模糊规则的激发隶

属度也为一区间 $[ 1 4 ]$ ，前面描述四条规则的隶属度区间如式（9)～（12）所示。

$$
[ \underline { { f } } _ { 1 } , \overline { { f } } _ { 1 } ] = [ \underline { { u } } _ { \tilde { A } _ { i } } ( e ) \times \underline { { u } } _ { \tilde { B } _ { j } } ( \dot { e } ) , \overline { { u } } _ { \tilde { A } _ { i } } ( e ) \times \overline { { u } } _ { \tilde { B } _ { j } } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 2 } , \overline { { f } } _ { 2 } ] = [ \underline { { u } } _ { \tilde { A } _ { i } } ( e ) \times \underline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) , \overline { { u } } _ { \tilde { A } _ { i } } ( e ) \times \overline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 3 } , \overline { { f } } _ { 3 } ] = [ \underline { { u } } _ { \tilde { A } _ { i + 1 } } ( e ) \times \underline { { u } } _ { \tilde { B } _ { j } } ( \dot { e } ) , \overline { { u } } _ { \tilde { A } _ { i + 1 } } ( e ) \times \overline { { u } } _ { \tilde { B } _ { j } } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 4 } , \overline { { f } } _ { 4 } ] = [ \underline { { u } } _ { \tilde { A } _ { i + 1 } } ( e ) \times \underline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) , \overline { { u } } _ { \tilde { A } _ { i + 1 } } ( e ) \times \overline { { u } } _ { \tilde { B } _ { j + 1 } } ( \dot { e } ) ]
$$

# 2 NT降阶算法

KM降阶算法是一迭代循环过程，初始化切换点以后，通过不断地比较得到最终的切换点，根据切换点来判断计算端点所需的上或者下隶属度。目前大部分的区间二型模糊控制器的结构分析都是基于KM降阶。

但在实际的控制过程中，使用KM降阶时，首先要对规则的后件参数进行从大到小排序，这是KM算法的实现过程所需要的。排完序以后，再进行迭代搜索得到左、右、切换点。得到左、右切换点以后，最终得到降阶的两个端点，取平均值得到控制器的最终输出。

KM降阶算法本质上是一迭代算法，用在区间二型模糊逻辑系统里面没有解析解，无法进行系统的稳定性分析。而Nie-Tan 降阶算法[15]利用模糊规则隶属度上、下限的平均值作为解模糊化的隶属度，这样就得到了区间二型模糊系统的闭环表达式，易于进行稳定性分析。

本文利用N-T降阶算法，避免了KM迭代，采用乘积型模糊推理，与取小模糊推理相比，避免了模糊空间的划分过程，控制器分析流程进一步简化。具体描述如式（13）（14）所示。

$$
\omega _ { k } = \frac { \underline { { f _ { k } } } + \overline { { f } } _ { k } } { 2 } ( k = 1 , \ldots , 4 )
$$

$$
\Delta u = \frac { \displaystyle \sum _ { k = 1 } ^ { 4 } \omega _ { k } \times y _ { k } } { \displaystyle \sum _ { k = 1 } ^ { 4 } \omega _ { k } } = \frac { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underbrace { f _ { k } + \overline { { f } } } _ { k } ) \times y _ { k } } { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underbrace { f _ { k } + \overline { { f } } } _ { k } ) }
$$

# 3 控制器结构分析

由式（9）～（12）可得

$$
\begin{array} { r l } & { \begin{array} { r } { [ f _ { j } , \overline { { f _ { 1 } } } ] = [ p _ { j } \times ( a _ { i } \times e - b _ { i } ) \times q _ { j } \times ( c _ { j } \times \dot { e } - d _ { j } ) , } \\ { ( a _ { i } \times e - b _ { i } ) \times ( c _ { j } \times \dot { e } - d _ { j } ) ] } \end{array} } \\ & { \begin{array} { r } { [ f _ { j , 2 } ] = [ p _ { j } \times ( a _ { i } \times e - b _ { i } ) \times q _ { j + 1 } \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } ) , } \\ { ( a _ { i } \times e - b _ { j } ) \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } ) ] } \end{array} } \\ & { \begin{array} { r } { [ f _ { j , 3 } , \overline { { f _ { 3 } } } ] = [ p _ { i + 1 } \times ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times q _ { j } \times ( c _ { j } \times \dot { e } - d _ { j } ) , } \\ { ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times ( c _ { j } \times \dot { e } - d _ { j } ) ] } \end{array} } \\ & { \begin{array} { r } { [ f _ { i , 1 } \times e - b _ { i + 1 } \times ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times q _ { j } \times ( c _ { j + 1 } \times \dot { e } - d _ { j } ) , } \\ { ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times ( c _ { i + 1 } \times e - b _ { i + 1 } ) \times q _ { j + 1 } \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } ) ] } \end{array} } \\ & { \begin{array} { r } { [ f _ { j , 4 } ] = [ p _ { j + 1 } \times ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times q _ { j + 1 } \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } ) } \\ { ( a _ { i + 1 } \times e - b _ { i + 1 } ) \times ( c _ { j + 1 } \times \dot { e } - d _ { j + 1 } ) ] } \end{array} } \end{array}
$$

将隶属度函数的具体表达式带入式（13）（14）可得 $\Delta u$ 的一般表达式，如式（15）所示。

$$
\Delta u = \frac { \xi _ { 1 } \times e \times \dot { e } + \xi _ { 2 } \times e + \xi _ { 3 } \times \dot { e } + \xi _ { 4 } } { \eta _ { 1 } \times e \times \dot { e } + \eta _ { 2 } \times e + \eta _ { 3 } \times \dot { e } + \eta _ { 4 } }
$$

其中：、、、4、 $\eta _ { 1 }$ 、2、 $\eta _ { 3 }$ 、 $\eta _ { 4 }$ 分别为与 $p _ { i }$ 、 $p _ { i + 1 }$ ，$L _ { i }$ 、Li+1、qi、 $q _ { i + 1 }$ 、 $S _ { i }$ 、 $\boldsymbol { S } _ { i + 1 }$ 相关的常数项。

由式（15）可以看出，基于NT 降阶算法的区间二型模糊控制器的输出与文献[9]分析的一样，该控制器等效于一个增量式PI（位置式PD）控制器，其比例增益、积分增益以及补偿项均为非线性可调。

$$
\Delta u = K _ { I } ( e , \dot { e } ) \times e + K _ { P } \times \dot { e } + \delta
$$

其中：

$$
K _ { I } ( e , \dot { e } ) = \frac { \xi _ { 1 } \times \dot { e } + \xi _ { 2 } } { \eta _ { 1 } \times e \times \dot { e } + \eta _ { 2 } \times e + \eta _ { 3 } \times \dot { e } + \eta _ { 4 } }
$$

$$
K _ { _ P } = { \frac { \xi _ { 3 } } { \eta _ { _ 1 } \times e \times { \dot { e } } + \eta _ { 2 } \times e + \eta _ { 3 } \times { \dot { e } } + \eta _ { 4 } } }
$$

$$
\delta = \frac { \xi _ { 4 } } { \eta _ { 1 } \times e \times \dot { e } + \eta _ { 2 } \times e + \eta _ { 3 } \times \dot { e } + \eta _ { 4 } }
$$

与文献[9]相比，本文控制器的结构分析过程大大简化，不需要对输入空间进行划分，也不需要针对每个划分的区间分别计算控制器的表达式，表达式的形式也更为简洁。而且还能得到控制器的闭环表达式，易于进行稳定性分析，这是基于KM降阶算法的区间二型模糊控制器所不具备的。

# 4 实例分析

本文选择典型的二阶迟延对象进行比较分析，其传递函数为

$$
G ( s ) = { \frac { 1 } { s ^ { 2 } + 2 \varepsilon \omega _ { n } s + \omega _ { n } ^ { 2 } } } e ^ { - L s }
$$

其中： $\varepsilon { = } 1 . 1 2 5$ 5 $\omega _ { n } { = } 0 . 4 5$ ， $L { = } 0 . 4$ 。

本例的首隶属度函数如图3所示。这里选择的误差与误差变化率的首隶属度函数相同。

![](images/f1c677afaf629f0c586e2a523e19b6f50ccd0504fc532d7b1a78bc63f6a36706.jpg)  
图3误差和误差变化率的首隶属度函数

由图3看出，本例对误差和误差变化率分别定义了五个模糊变量，分别为NB（负大）、NM（负中）、Z（零）、PM（正中）、PB(正大)。 $p _ { 1 } = p _ { 3 } = p _ { 5 } = 0 . 9$ ， $p _ { 2 } { = } p _ { 4 } { = } 0 . 3$ ， $L _ { 1 } { = } S _ { 1 } { = } { - } 1$ ， $\scriptstyle { L _ { 2 } = S _ { 2 } = _ { - } }$ 0.5， $\scriptstyle { L _ { 3 } = S _ { 3 } = 0 }$ ， $\scriptstyle { L _ { 4 } = S _ { 4 } = 0 . 5 }$ ， $\scriptstyle { L _ { 5 } = S _ { 5 } = 1 }$ 。

后件参数[16]定义为 $\mathrm { N B = - 1 , N M = - 0 . 8 , } Z = 0 , \mathrm { P M = 0 . 8 , P B = 1 } ,$ 通过输入模糊变量的定义，一共有 $5 \times 5 = 2 5$ 条模糊规则，具体的模糊规则[17]如表1所示。

表1区间二型模糊控制器规则  

<html><body><table><tr><td>dt E/dE</td><td>NB</td><td>NM</td><td>Z</td><td>PM</td><td>PB</td></tr><tr><td>NB</td><td>NB</td><td>NB</td><td>NB</td><td>NM</td><td>Z</td></tr><tr><td>NM</td><td>NB</td><td>NB</td><td>NM</td><td>Z</td><td>PM</td></tr><tr><td>Z</td><td>NB</td><td>NM</td><td>Z</td><td>PM</td><td>PB</td></tr><tr><td>PM</td><td>NM</td><td>Z</td><td>PM</td><td>PB</td><td>PB</td></tr><tr><td>PB</td><td>Z</td><td>PM</td><td>PB</td><td>PB</td><td>PB</td></tr></table></body></html>

这里的变量区间为[-1,1]，是通过误差和误差变化率的量化因子将实际的值映射到[-1,1]区间。

图4显示了采用PID控制器、传统一型模糊控制器以及本文算法的阶跃响应曲线。从图4可看出，对于给定的二阶迟延系统，传统的一型模糊控制器陷入了等幅震荡，PID控制器的上升时间教长，响应速度较慢，系统进入稳态时间也教长。而本文方法不仅能保证系统稳定，还能提高系统的响应速度，能够使系统快速稳定。

![](images/7de5314e01e953dd1fe78f10b9929ce2ce24e695d447f848b40a3b2b4d00043b.jpg)  
图4三种控制器的阶跃响应曲线

当系统运行到0.5s时，通过量化因子的误差和误差变化率的值分别为0.7654和-0.1576，那么误差隶属度函数激发的模糊变量为PM和PB，误差变化率隶属度函数激发的模糊变量为NM和Z，实际的四条模糊规则如下：

规则1 if $e$ is PM and $\dot { e }$ is NM, then $\scriptstyle \Delta u = Z = 0$ 规则2 if $e$ is PM and $\dot { e }$ is $Z$ ,then $\Delta u { = } P M { = } 0 . 8$ 规则3 if $e$ is PB and $\dot { e }$ is NM, then $\Delta u { = } P M { = } 0 . 8$ 规则4 if $e$ is PB and $\dot { e }$ is Z, then $\Delta u { = } P B { = } 1$

误差的隶属度上、下限分别为

$$
\overline { { u } } _ { P M } \left( e \right) = - 2 \times \left( e - 1 \right) = 0 . 4 6 9 2
$$

$$
{ \underline { { u } } } _ { P M } \left( e \right) = 0 . 3 \times ( - 2 \times ( e - 1 ) ) = 0 . 1 4 0 8
$$

$$
\overline { { u } } _ { P B } ( e ) = 2 \times ( e - 0 . 5 ) = 0 . 5 3 0 8
$$

$$
\underline { { u } } _ { P B } ( e ) = 0 . 9 \times ( 2 \times ( e + 0 . 5 ) ) = 0 . 4 7 7 7
$$

误差变化率的隶属度上、下限分别为

$$
\overline { { u } } _ { N M } \left( \dot { e } \right) = - 2 \times \dot { e } = 0 . 3 1 5 2
$$

$$
\underline { { u } } _ { N M } ( \dot { e } ) = 0 . 3 \times ( - 2 \times \dot { e } ) = 0 . 0 9 4 6
$$

$$
\overline { { u } } _ { z } ( \dot { e } ) = 1 + 2 \times \dot { e } = 0 . 6 8 4 8
$$

$$
\underline { { u } } _ { Z } ( \dot { e } ) = 0 . 9 \times ( 2 \times \dot { e } ) = 0 . 6 1 6 3
$$

四条模糊规则的激发隶属度的上、下限为

$$
[ \underline { { f } } _ { 1 } , \overline { { f } } _ { 1 } ] = [ \underline { { u } } _ { P M } ( e ) \times \underline { { u } } _ { N M } ( \dot { e } ) , \overline { { u } } _ { P M } ( e ) \times \overline { { u } } _ { N M } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 2 } , \overline { { f } } _ { 2 } ] = [ \underline { { u } } _ { P M } ( e ) \times \underline { { u } } _ { Z } ( \dot { e } ) , \overline { { u } } _ { P M } ( e ) \times \overline { { u } } _ { Z } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 3 } , \overline { { f } } _ { 3 } ] = [ \underline { { u } } _ { P B } ( e ) \times \underline { { u } } _ { N M } ( \dot { e } ) , \overline { { u } } _ { P B } ( e ) \times \overline { { u } } _ { N M } ( \dot { e } ) ]
$$

$$
[ \underline { { f } } _ { 4 } , \overline { { f } } _ { 4 } ] = [ \underline { { u } } _ { \mathit { P B } } ( e ) \times \underline { { u } } _ { z } ( \dot { e } ) , \overline { { u } } _ { \mathit { P B } } ( e ) \times \overline { { u } } _ { z } ( \dot { e } ) ]
$$

如果采用常规的KM降阶算法，其计算过程如下：

a）将四条规则的后件参数按照从小到大排序，相应的模糊规则的隶属度也作位置调整。从前面的规则描述可看出，规则1\~4的后件正好是从小到大(0.0.8,0.8,1)，因此这一步已经完成。

b）通过KM计算左端点。

(a）初始化：

$$
c _ { l } ^ { ' } = \frac { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underbrace { f _ { k } } _ { \ell } + \overline { { f } } ) \times y _ { k } } { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underbrace { f _ { k } } _ { \ell } + \overline { { f } } ) } = 0 . 8 0 1 8
$$

(b)寻找左切换点 $L$ ，使得 $y _ { L } \leq c _ { l } ^ { ' } \leq y _ { L + 1 }$ ，观察得到 $L { = } 3$ 。（c）计算：

$$
c _ { l } = \frac { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } \times y _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } \times y _ { k } } { \overline { { \mathbf { \xi } } } } } { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } } { \overline { { f } } _ { k } } } = 0 . 7 3 6 2
$$

并令 $c _ { l } ^ { " } = c _ { l } = 0 . 7 3 6 2$ 。

(d)由于 $c _ { l } ^ { " } \neq c _ { l } ^ { " }$ ，令 $c _ { l } ^ { ' } = c _ { l } ^ { " } = 0 . 7 3 6 2$ ，接着寻找切换点 $L$ 使得 $y _ { L } \leq c _ { l } ^ { ' } \leq y _ { L + 1 }$ ，观察得到 $L { = } 1$ 。

（e）计算：

$$
c _ { l } = \frac { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } \times y _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } \times y _ { k } } { \ell } } { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } } { \ell } } = 0 . 6 9 6 5
$$

并令 $c _ { l } ^ { " } = c _ { l } = 0 . 6 9 6 5$ 。

(f)由于 $\dot { c _ { l } } \neq \dot { c _ { l } }$ ，令 $c _ { l } ^ { ' } = c _ { l } ^ { ' } = 0 . 6 9 6 5$ ，接着寻找切换点 $L$ ，使得 $y _ { L } \leq c _ { l } ^ { ' } \leq y _ { L + 1 }$ ，观察得到 $L { = } 1$ 。

（g）计算：

$$
c _ { l } = \frac { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } \times y _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } \times y _ { k } } { \ell } } { \displaystyle \sum _ { k = 1 } ^ { L } \overline { { f } } _ { k } + \sum _ { k = L + 1 } ^ { 4 } \frac { f _ { k } } { \ell } } = 0 . 6 9 6 5
$$

并令 $c _ { l } ^ { " } = c _ { l } = 0 . 6 9 6 5$ 。

(h）由于 $c _ { l } ^ { ' } = = c _ { l } ^ { ' }$ ，那么迭代过程结束，左切换点 $\scriptstyle { L = 1 }$ ，左端点 $c _ { l } = 0 . 6 9 6 5$ 。

c）通过KM计算右端点。

（a）初始化：

$$
\dot { c _ { r } } = \frac { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underline { { f _ { k } } } + \overline { { f } } ) \times y _ { k } } { \displaystyle \sum _ { k = 1 } ^ { 4 } ( \underline { { f _ { k } } } + \overline { { f } } ) } = 0 . 8 0 1 8
$$

（b）寻找切换点 $R$ ，使得 $y _ { R } \leq c _ { r } ^ { ' } \leq y _ { R + 1 }$ ，观察得到 $R { = } 3$ 。（c）计算：

$$
c _ { r } = { \frac { \displaystyle \sum _ { k = 1 } ^ { R } { \underline { { f } } \times y _ { k } } + \sum _ { k = L + 1 } ^ { 4 } { \overline { { f } } _ { k } \times y _ { k } } } { \displaystyle \sum _ { k = 1 } ^ { L } { \underline { { f _ { k } } } + \sum _ { k = L + 1 } ^ { 4 } { \overline { { f } } } } } } = 0 . 9 2 2 0
$$

并令 $c _ { r } ^ { " } = c _ { r } = 0 . 9 2 2 0$

(d)由于 $c _ { r } ^ { " } \neq c _ { r } ^ { " }$ ，令 $c _ { r } ^ { ' } = c _ { r } ^ { " } = 0 . 9 2 2 0$ ，接着寻找切换点 $R$ ，使得 $y _ { R } \leq c _ { r } ^ { ' } \leq y _ { R + 1 }$ ，观察得到 $\scriptstyle R = 3$ 。

（e）计算：

$$
c _ { r } = { \frac { \displaystyle \sum _ { k = 1 } ^ { R } { \underline { { f } } \times y _ { k } } + \sum _ { k = L + 1 } ^ { 4 } { \overline { { f } } _ { k } \times y _ { k } } } { \displaystyle \sum _ { k = 1 } ^ { L } { \underline { { f _ { k } } } + \sum _ { k = L + 1 } ^ { 4 } { \overline { { f } } } } } } = 0 . 9 2 2 0
$$

并令 $c _ { r } ^ { " } = c _ { r } = 0 . 9 2 2 0$ 。

(f)由于 $c _ { r } ^ { ' } = = c _ { r } ^ { ' }$ ，那么迭代过程结束，右切换点 $R { = } 3$ ，右端点 $c _ { r } = 0 . 9 2 2 0$ 。

d）通过KM降阶结果，得到控制器的输出：

$$
\Delta u _ { { _ { K M } } } = \frac { c _ { l } + c _ { r } } { 2 } = 0 . 8 0 9 2
$$

即本文的分析结果，最终得到的控制器表达式以及输出为

$$
\Delta u _ { _ { N T } } = \frac { - 4 4 4 \times e \times \dot { e } + 7 9 4 \times e + 1 2 3 8 \times \dot { e } + 1 1 1 1 } { 7 2 0 \times e \times \dot { e } + 5 4 0 \times e - 1 8 0 \times \dot { e } + 3 6 5 } = 0 . 8 0 1 8
$$

本文控制器与利用KM降阶算法得到的最终结果相比差值为-0.0074，误差百分比仅为 $0 . 9 1 \%$ 。

从以上的分析过程可看出，每一个时刻控制器的输出如果采用KM降阶算法都要进行重复的迭代过程，这在实时控制系统中是较为耗时的，而本文方法可直接得到控制器的输出，实时性得到了保证，而且便于进行稳定性分析和控制器设计。

# 5 结束语

基于输入空间划分是进行模糊控制器的结构分析的主要方法，使用Zadeh的AND（取小）推理，将模糊控制器的输入划分为若干个区间，每个区间的激发隶属度为一确定的表达式。这种分析方法得到的控制器的表达式结构简单，但是输入空间数量较多且与参数有很大关系。此方法应用到二型模糊控制器时，目前主要采用KM降阶，通过一个简单的实例，KM降阶算法效率低下，通过KM算法的流程，其无法得出解析解。

本文基于乘积推理，避免了取小推理带来的输入空间划分步骤，可直接得出控制器的一般表达式，且该控制器等效于一个增量式PI（位置式PD）控制器，其比例增益、积分增益以及补偿项均为非线性可调，分析过程大大简化。文献[9]也是采用的乘积推理，但其在降阶部分依然是KM降阶算法。文献[9]虽然也得到了区间二型模糊控制器的闭环表达式，但依然要进行输入空间的划分，每个输入空间对应了特定的控制器的表达式。

本文利用NT降阶算法，该算法已经被证明了是KM降阶的一阶泰勒近似，可直接得到区间二型模糊控制器降阶结果。通过本文的实例可看出，两者的降阶结果非常接近，而且还能得到区间二型模糊控制器的闭环表达式，有利于系统进行稳定性分析与设计等。

# 参考文献：

[1]Ying Hao,Siler W,Buckley JJ. Fuzzy control theory: a nonlinear case [J]. Automatica,1990,26 (3): 513-520.   
[2]Siler W, Ying Hao.Fuzzy control theory: the linear case [J].Fuzzy Sets and Systems,1989,33 (3): 275-290.   
[3]Ying Hao.Deriving analytical input-output relationship for fuzzy controllers using arbitrary input fuzzy sets and Zadeh fuzzy and operator [J].IEEE Trans on Fuzzy Systems,2006,14 (5): 654-662.   
[4]Du Xinyu,Ying Hao.Derivation and analysis of the analytical structures of the interval type-2 fuzzy-PI and PD controllers [J]. IEEE Trans on Fuzzy Systems,2010,18 (4): 802 - 814.   
[5]Nie Maowen,Tan W W.Analytical structure and characteristics of symmetric karnik-mendel type-reduced interval type-2 fuzzy PI and PD controllers[J].IEEE Trans on Fuzzy Systems,2012,20 (3): 416-430.   
[6]Zhou H, Ying H.A method for deriving the analytical structure of a broad class of typical interval type-2 mamdani fuzzy controllers [J]. IEEE Trans on Fuzzy Systems,2013,21(3): 447-458.   
[7]Zhou Haibo, Ying Hao.Deriving and analyzing analytical structures of a class of typical interval type-2 TS fuzzy controllers [J]. IEEE Trans on Cybernetics,2017,47 (9): 2492-2502.   
[8]雷宾宾，保宏，许谦．区间二型模糊 PI//PD 控制器设计与结构分析 [J]．电机与控制学报,2016,20(6):50-62.   
[9] 龙祖强，许岳兵，李龙．一类乘积型区间二型模糊控制器的解析结构 [J]．控制理论与应用,2016,33(7):929-935.   
[10] Wu Dongrui,Mendel JM. Enhanced karnik-mendel algorithms [J]. IEEE Trans on Fuzzy Systems,2009,17 (4): 923-934.   
[11] Wu Dongrui,Nie Maowen. Comparison and practical implementation of type-reduction algorithms for type-2 fuzzy sets and systems [C]// Proc of IEEE International Conference on Fuzzy Systems.2011: 2131-2138.   
[12]胡怀中，赵戈，杨华南．一种区间型二型模糊集重心的快速解法 [J]. 控制与决策,2010,25(4):637-640.   
[13] Nie Maowen, Tan W W. Towards an efficient type-reduction method for interval type-2 fuzzy logic systems [C]// Proc of IEEE International

Conference on Fuzzy Systems.2008:1425-1432.

[14] Liang Qilian,Mendel J.M. Interval type-2 fuzzy logic systems: theory and design [J].IEEE Trans on Fuzzy Systems,200o,8(5): 535-550.

[15]Nie Maowen,Tan WW.Towards an efficient type-reduction method for interval type-2 fuzzy logic systems [C// Proc of IEEE International Conference on Fuzzy Systems.2008.1425-1432.

[16]Kumbasar T,Hagras H.Big Bang-Big Crunch optimization based interval type-2 fuzzy PID cascade controller design strategy [J].Information Sciences,2014,282:277-295.

[17]Kumar A,Kumar V.A novel interval type-2 fractional order fuzzy PID controller:Design,performance evaluation,and its optimal time domain tuning[J]. ISA Transactions,2017,68:251-275.