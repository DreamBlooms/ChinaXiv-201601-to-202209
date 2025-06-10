# 一种基于改进分层置信规则库的社交账户可信度评估方法

吴菲，王维

(长春工业大学 数字媒体教研室，长春 130012)

摘要：社交账户可信度评估是确保网络社交生态良性发展的重要环节。针对社交账户可信度评估指标多维、数据信息不确定性多样等问题，提出了一种基于改进分层置信规则库的可信度评估方法。首先从账户属性、交际属性和内容属性三个角度分析了可信度评估各指标之间的相互关系，并依此构建了置信规则库的分层结构。其次，在信息转换函数中引入了自适应系数以更好描述和处理指标间的特性差异。最后，为了弥补专家知识局限性带来的模型误差，采用带有投影算子的协方差矩阵自适应进化策略对自适应系数和模型参数进行了优化。以新浪微博账户作为实验对象，结果表明该方法能够在数据样本有限的情况下获得更高的可信度评估精度。

关键词：置信规则库；社交账户；可信度评估 中图分类号：TP3 doi:10.19734/j.issn.1001-3695.2022.01.0047

Credibility evaluation method for social accounts via improved hierarchical belief rule base

Wu Fei†,Wang Wei (Dept. ofdigital media,Changchun University ofTechnology,Changchun Jilin 130012,China)

Abstract: Social account credibilityevaluation is an important link to ensure thebenigndevelopmentof network social ecology.Aimingat theproblems ofmulti-dimensionalcredibilityevaluation indexesand various datainformationuncertainty, this paper proposed acredibility evaluation method based on the improved hierarchical beliefrule base.Firstly,this paper constructedahierarchical structure byanalyzingtherelationship betweentheindicatorsofcredibilityevaluation from hree perspectives:account attibute,communicationattibute,andcontent attibute.Secondly,this paper introducedanadaptive coeffcientintothe information transformationfunctiontobeterdeal withthecharacteristicdiferences between indicators. Finally,to makeupforthe model error causedbythelimitationof expert knowledge,this paper used thecovariance matrix adaption evolution strategy with projection tooptimize the adaptivecoeficients and model parameters.Taking Sina Weibo account asthe experimental object,theresults show that this methodcanobtain higheraccuracywhenthedata samplesare limited.

Key words:belief rule base; social accounts;credibility evaluation

# 0 引言

随着互联网技术的不断发展，网络社交媒体逐渐成为了人们发布、传播、获取信息的主要方式。社交媒体为人们带来生活便利的同时，其开放共享的信息传播机制也逐渐成为了我国意识形态、信息安全、防疫防控等领域的风险隐患[1,2]。尤其是，在国际局势不断恶化、新冠肺炎等全球公共安全事件频繁发生的大背景下，境外极端份子借助社交媒体散布谣言和钓鱼链接等违法信息，欲达到实施网络诈骗、窃取国家机密甚至颠覆政权的目的。这些行为严重威胁了网络社交生态的良性发展，造成了社会舆论引导混乱，影响了社会安定。

社交账户是媒体信息发布的源头。准确判断账户是否可信，有利于相关部门采取合适的手段来对危害信息进行管控。现有的研究通常采用包括机器学习、统计分析等在内的多种建模方法对社交账户的状态进行判断[3,4]。王峥等人提出了一种特征加权贝叶斯神经网络模型，并将之应用于微博账号的异常检测中[5]。但是该模型依赖于高质量的训练数据样本。胡学韬等人基于粗糙集理论设计了社交账户信任度模型，通过该模型可以将社交账户的状态区分为正常和异常[1]。路金泉等人基于贝叶斯算法和层次分析法提出了一种账户可信度评估方法，该方法将社交账户评估为可信与不可信两级[2]。这两种方法能够分别有效处理模糊不确定性和概率不确定性但对账户可信度的量化分析不够。刘亚尚等人的研究中，将社交账户的状态分为正常账户、被入侵账户和僵尸账户三类，采用所提的并行支持向量机算法实现了账户状态的识别[4]。该方法对训练样本数量的要求不高，但同样在不确定性描述和可信度量化方面存在短板。基于D-S证据理论的可信度评估方法能够有效融合专家主观判断和有限的客观数据，其采用置信辨识框架来描述信息的不确定性。但该评估方法在处理冲突证据方面存在不足[6.7]。

置信规则库(BeliefRuleBase,BRB)是英国曼彻斯特大学杨剑波教授在D-S证据理论、模糊理论和IF-THEN规则的基础上发展而来的一种基于半定量信息的评估方法67]。该方法通过在传统IF-THEN规则中引入置信框架来量化描述各类不确定性，通过在D-S证据理论中引入证据权重形成证据推理算法(Evidential Reasoning,ER)来处理冲突证据。BRB能够有效融合专家判断和样本数据进行建模，降低了对高质量数据集的依赖7。目前，BRB已经广泛应用于复杂工程系统的健康状态评估、性能评估和大型工业结构的安全性评估中[7,8]。

账户可信度的评估涉及多维指标，如用户关注数、评论率等，每个指标具有不同的特性。因此，要充分结合指标含义构建多层评估指标体系。指标体系构建完毕后，可采用分层BRB实现对多维多层指标的评估。然而，在现有分层BRB模型中，不同指标常常共用一种信息转换方法，且这些方法不具备自适应性，不能较好反映个指标的特点。鉴于此，本文提出了基于改进分层BRB的账户可信度评估方法(ImprovedHierarchicalBeliefRule Base,IHBRB)，主要贡献总结如下：

1)提出了账户可信度评估指标，并依此构建了分层BRB评估模型;

2)提出了一种自适应指标信息转换方法，并通过智能优化算法实现了相关参数的自适应调整。

# 1 研究思路

本文提出的基于IHBRB的应用于社交账户可信度评估的主要思路如图1所示。首先，进行可信度评估指标的选取，并结合指标构建多层评估指标体系；然后，针对指标体系构建IHBRB模型，提出自适应信息转换方法；最后，构建优化模型，将IHBRB的置信度、属性权重、规则权重、参考值和信息转换方法参数等作为待优化参数进行自适应调整。优化后的评估模型即可用于社交账户可信度评估。

![](images/c216f6d71ed9047ea8c74aa6eed71044062fed36ffd8002368ce8e3a8c56be47.jpg)  
图1基于IHBRB的社交账户可信度评估研究思路 Fig.1Research idea of the social account credibility evaluation based on IHBRB

# 2 可信度评估指标体系构建

结合现有研究，本着“指标信息获取成本低”的原则，从多个角度选取了能够反映账户状态的指标[1,9\~11]。

账户年限，记为 $C _ { 1 }$ 。该指标能够反映了账户使用的历史。在网络社交中，极端份子为了短时间内制造高强度的舆论压力，通常需要短时间内创建较大规模数量的僵尸账号。从这个角度出发，账户年限越短，其是僵尸账号的可能性越大，其可信度也就越低。

认证情况，记为 $C _ { 2 }$ 。该项指标涉及身份认证、兴趣认证、问答认证、会员认证等，其能够反映账户信息的完备情况。在社交媒体中，非认证账户更加普遍，进行违法信息生产和传播的成本也更小。因此，可认为非认证账户的可信度要低于认证账户。

粉丝数和被转赞评数，分别记为 $C _ { 3 }$ 和 $C _ { 4 }$ 。这两项指标主要反映账户的影响力。通常，粉丝数多的账户其可信度更高，相应的被转赞评数也会越多。但是部分异常账户发布谣言后，在僵尸账户的操纵下，其被转赞评数量也可能会出现增多的情况。因此，对于粉丝数少且被转赞评数多的账户，其可信度可能处于较低水平。

信息原创率，记为 $C _ { 5 }$ 。该项指标可采用如下公式计算：

$$
C _ { 5 } = \frac { r _ { o } } { r _ { a } } , 0 \le C _ { 5 } \le 1
$$

其中， $r _ { o }$ 表示账户发表的原创信息条数， $r _ { a }$ 表示账户所发表信息的总条数；信息原创率能够从一定程度上反映用户自身的活跃度。信息原创率越高的账户，是僵尸账户或被入侵账户的可能性越低。

信息存疑率，记为 $C _ { 6 }$ 。无论是原创信息还是转发信息，当信息内容含有异常链接、杂乱表情以及无含义文字时，可认为该信息存在违规嫌疑。信息存疑率可采用如下公式计算：

$$
C _ { 6 } = \frac { r _ { s } } { r _ { a } } , 0 \leq C _ { 6 } \leq 1
$$

其中， $r _ { s }$ 表示账户发表的存疑信息条数。所发布信息的存疑率越高，账户的可信度就越低。

上述六个指标中，账户年限 $C _ { 1 }$ 和认证情况 $C _ { 2 }$ 、粉丝数 $C _ { 3 }$ 和被转赞评数 $C _ { 4 }$ 、信息原创率 $C _ { 5 }$ 和存疑率 $C _ { 6 }$ 分别从账户属性、交际属性和内容属性三个角度反映了账户的可信度。基于这些角度反映的可信度便可进一步对账户的整体可信度进行评估。

因此，可构建如图2所示的账户可信度评估指标体系。其中，用 $B$ 表示社交账户的可信度，用 $B _ { 1 }$ 、 $B _ { 2 }$ 和 $B _ { 3 }$ 分别表示账户属性可信度、交际属性可信度与内容属性可信度。

![](images/9bd633c4f23d90e127bb57ed3c3c5c2a9800b79c83f28586952255976b019466.jpg)  
图2账户可信度评估分层指标体系

# 3 基于IHBRB的可信度评估模型构建

# 3.1基于IHBRB的可信度评估框架

结合分层指标体系，可构建如图3所示的基于IHBRB的可信度评估模型框架。其中，BRB-1子模型、BRB-2子模型和BRB-3子模型分别用于建立三种属性可信度与各指标之间的关系，而BRB-3子模型则用于建立三种属性可信度与账户可信度之间的非线性关系。IHBRB模型采用由底至上的逐层推理模型得到最后的结果。

![](images/80cdf95f1422d7168eca636d75eae7c45a2df77c1f65d1771bc3b21633f6146a.jpg)  
Fig.2Hierarchical index system for account credibility evaluation   
图3基于IHBRB的可信度评估模型框架  
Fig.3Credibility evaluation model framework based on IHBRBIHBRB模型中的第 $h$ 个子模型记为BRB- $\cdot h$ ，它有一系列置信规则组成，其中第 $k$ 条规则描述为

$R _ { k } ^ { h }$ :if $X _ { 1 } ^ { h }$ s $A _ { 1 } ^ { k , h } \wedge \ldots \wedge X _ { M } ^ { h }$ is $A _ { M } ^ { k , h }$ $\mathrm { t h e n } \{ ( D _ { 1 } ^ { h } , \beta _ { 1 , k } ^ { h } ) , . . . ( D _ { N } ^ { h } , \beta _ { N , k } ^ { h } ) \} ,$ with rule weight $\theta _ { k } ^ { h }$ and attribute weights $\delta _ { i } ^ { h }$ $( i = 1 , . . . , M )$ （24其中， $X _ { i } ^ { h }$ 表示模型的第 $i$ 个输入指标，例如 BRB-1中的 $C _ { 1 }$ 和$C _ { 2 }$ ； $A _ { i } ^ { k , h } ( k = 1 , . . . , L )$ 表示第 $k$ 条规则中 $X _ { i } ^ { h }$ 的参考等级， $\textbf { \em L }$ 为规则的总条数， $M$ 表示输入指标的数量； $\wedge$ 表示逻辑关系“与”；$\theta _ { k } ^ { h }$ 表示第 $k$ 条规则的规则权重；同理， $\delta _ { i } ^ { h }$ 表示 $X _ { i } ^ { h }$ 的权重，称为属性权重； $\{ ( D _ { 1 } ^ { h } , \beta _ { 1 , k } ^ { h } ) , . . . ( D _ { N } ^ { h } , \beta _ { N , k } ^ { h } ) \}$ 表示第 $k$ 条规则结论部分中各个不同可信度等级的置信分布。其中， $0 \leq \beta _ { n , k } ^ { h } \leq 1 , ( n = 1 , 2 , . . . , N )$ 表示第 $k$ 条规则中对于第 $n$ 个可信度等级 $D _ { n } ^ { h }$ 的支持度，也称对 $D _ { n } ^ { h }$ 的置信度。

输入信息转换是IHBRB模型的关键步骤，其主要目的是采用合适的转换方法将多种形式的输入信息统一至置信框架下。本文在传统信息转换方法的基础上提出了一种新的自适应信息转换方法。

# 3.2自适应信息转换方法

IHBRB 模型输入指标 $X _ { i } ^ { h }$ 转换为置信分布形式的过程可用如下公式表示：

$$
f ( X _ { i } ^ { h } ) = \left\{ \left( A _ { i , j } ^ { h } , \alpha _ { j } ^ { i , h } \right) , j = 1 , 2 \cdots J , \ i = 1 , 2 \cdots M \right\}
$$

其中， $\alpha _ { j } ^ { i , h }$ 表示第 $i$ 输入指标相对于第 $j$ 个参考等级的匹配度，$J$ 表示参考等级的个数， $A _ { i , j } ^ { h }$ 表示属性参考值， $f ( \bullet )$ 表示转换函数。在现有研究中，传统BRB模型的定量输入通常采用式(5)所示转换方法：

$$
\alpha _ { j } ^ { i , h } = f ( x _ { i } ) = \left\{ \begin{array} { l l } { \displaystyle \frac { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - x _ { i } } { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - A _ { i , j ^ { \prime } } ^ { h } } \qquad j ^ { \prime } = j \mathrm { ~ i f ~ } A _ { i , j ^ { \prime } } ^ { h } \leq x _ { i } \leq A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } } \\ { \displaystyle - \frac { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - x _ { i } } { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - A _ { i , j ^ { \prime } } ^ { h } } \quad j = j ^ { \prime } + 1 } \\ { 0 \qquad j = 1 , 2 , \ldots J _ { i } , j \neq j ^ { \prime } , j \neq j ^ { \prime } + 1 } \end{array} \right.
$$

其中， $x _ { i }$ 表示第 $i$ 指标的输入值。可以看出，上述转换方法是线性的，难以准确描述输入与置信分布间的非线性关系。

鉴于此，对式(5)进行一般化构造，增强其非线性描述能力。构造的转换方法如下：

$$
\begin{array}{c} \alpha _ { j } ^ { i , h } = f ^ { \prime } ( x _ { i } ) = \left\{ \left[ \begin{array} { l l } { \displaystyle { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - x _ { i } } } \\ { \displaystyle { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - A _ { i , j ^ { \prime } } ^ { h } } } \end{array} \right] ^ { s }  & { j ^ { \prime } = j \mathrm { ~ i f ~ } A _ { i , j ^ { \prime } } ^ { h } \leq x _ { i } \leq A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } } \\  \displaystyle { A _ { j } ^ { i , h } = f ^ { \prime } ( x _ { i } ) = \left\{ \begin{array} { l l } { \displaystyle { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - x _ { i } } } \\ { \displaystyle { A _ { i , ( j ^ { \prime } + 1 ) } ^ { h } - A _ { i , j } ^ { h } } } \end{array} \right\} ^ { s } } & { j = j ^ { \prime } + 1 } \\ { 0 } & { j = 1 , 2 , \ldots J _ { i } , j \neq j ^ { \prime } , j \neq j ^ { \prime } + 1 } \end{array} \right. 
$$

其中， $f ^ { \prime } ( \bullet )$ 表示改进后的转换函数； $A _ { \scriptscriptstyle i , f } ^ { h } \le A _ { \scriptscriptstyle i , ( \textit { j + 1 } ) } ^ { h }$ 分别表示相邻两个参考值； $s , s > 0$ 为自适应系数，其决定着 $f ^ { \prime } ( \bullet )$ 的非线性能力，其可由专家给定，也可通过优化的方式得到。

为了说明这一点，假设 $A _ { i , j ^ { \prime } } ^ { h } \leq x _ { i } \leq A _ { i , ( \ j ^ { \prime } + 1 ) } ^ { h } , A _ { i , j ^ { \prime } } ^ { h } = 1 , A _ { i , ( \ j ^ { \prime } + 1 ) } ^ { h } = 1 0$ ，且$g ( x _ { i } ) = \left[ ^ { ( A _ { i ( f + 1 ) } ^ { h } - x _ { i } ) } \Big / _ { ( A _ { i ( f + 1 ) } ^ { h } - A _ { i , f } ^ { h } ) } \right] ^ { \prime }$ ，当 $s$ 取不同值时， $g ( x _ { i } )$ 的输出如图4所示。可以看出，当 $0 < s < 1$ 时， $g ( x _ { i } )$ 为凹函数；当 $1 < s$ 时， $g ( x _ { i } )$ 为凸函数；特别地，当 $s { = } 1$ 时，式(6)退化为式(5)，其描述的是线性关系。

在实践中，针对不同指标的转换方法赋予不同的自适应系数，即可实现更加精准和有效的信息转换。

![](images/84b19ccd8336a30382e929b836868d86e71cf3848670d8b2936a1e34fe8be9b0.jpg)  
图4信息转换函数曲线图  
Fig.4The curve of the information transformation function

# 3.3可信度评估模型推理方法

IHBRB模型中，各子模型的输入信息在转换为置信分布后，需要进行规则激活和融合，其输出结果作为下一层子模型的输入，依次完成逐层推理。不同子模型间的推理模式相同，以第BRB- $\cdot h$ 为例，其推理的主要步骤如下：

Step1(规则的激活)：在获取匹配度后，需要结合属性权重和规则权重来计算相应规则的激活权重。规则激活权重用以表示输入信息对规则的激活程度，其计算方法为

$$
w _ { k } ^ { h } = \frac { \displaystyle \theta _ { k } ^ { h } \prod _ { i = 1 } ^ { M } \big ( \alpha _ { i } ^ { k , h } \big ) ^ { \bar { \delta } _ { i } ^ { h } } } { \displaystyle \sum _ { l = 1 } ^ { L } \theta _ { l } ^ { h } \prod _ { i = 1 } ^ { M } \big ( \alpha _ { i } ^ { l , h } \big ) ^ { \bar { \delta } _ { i } ^ { h } } } ~ , ~ \overline { { \delta } } _ { i } ^ { h } = \frac { \delta _ { i } ^ { h } } { \displaystyle \operatorname* { m a x } _ { i = 1 , \dots , M } ^ { \Delta _ { i } ^ { h } } }
$$

其中， $\boldsymbol { w _ { k } ^ { h } }$ 表示第 $k$ 条规则的激活权重，当 $0 < w _ { k } ^ { h } \le 1$ 时则认为相应规则已被激活； $\theta _ { k } ^ { h }$ 表示规则权重； $\alpha _ { i } ^ { k , h }$ 表示该规则中第

$i$ 个输入相对其参考值的匹配度； $\delta _ { i } ^ { h }$ 表示属性权重； $\overline { { \delta _ { i } } } { } ^ { h }$ 表示归一化后的相对属性权重。

Step2(规则的融合)：对于激活的规则，可使用证据推理(evidentialreasoning，ER)算法将规则融合，ER解析算法表达式为

$$
\hat { \beta } _ { n } ^ { h } = \frac { \mu \Bigg [ \prod _ { k = 1 } ^ { L } \biggl ( w _ { k } ^ { h } \beta _ { n , k } ^ { h } + 1 - w _ { k } ^ { h } \sum _ { i = 1 } ^ { N } \beta _ { i , k } ^ { h } \biggr ) - \prod _ { k = 1 } ^ { L } \biggl ( 1 - w _ { k } ^ { h } \sum _ { i = 1 } ^ { N } \beta _ { i , k } ^ { h } \biggr ) \Bigg ] } { 1 - \mu \Bigg [ \prod _ { k = 1 } ^ { L } \bigl ( 1 - w _ { k } ^ { h } \bigr ) \Bigg ] }
$$

$$
\mu = \Biggl [ \sum _ { n = 1 } ^ { N } \prod _ { k = 1 } ^ { L } \Biggl ( w _ { k } ^ { h } \beta _ { n , k } ^ { h } + 1 - w _ { k } ^ { h } \sum _ { i = 1 } ^ { N } \beta _ { i , k } ^ { h } \Biggr ) - \left( N - 1 \right) \prod _ { k = 1 } ^ { L } \Biggl ( 1 - w _ { k } ^ { h } \sum _ { i = 1 } ^ { N } \beta _ { i , k } ^ { h } \Biggr ) \Biggr ] ^ { - 1 }
$$

其中， $\beta _ { n , k } ^ { h }$ 表示第 $k$ 条规则对第 $n$ 个参考等级 $D _ { n }$ 的置信度；${ \hat { \beta } } _ { n } ^ { h }$ 表示输出中第 $\textbf { \textit { n } }$ 个参考等级 $D _ { n }$ 的置信度，且满足$0 \leq \hat { \beta } _ { n } ^ { h } \leq 1 , \sum _ { n = 1 } ^ { N } \hat { \beta } _ { n } ^ { h } \leq 1$ 。

Step3(评估结果的输出)：推理后得到的评估结果可表示为如下所示的置信分布形式：

$$
S \left( x _ { i } \right) = \left\{ \left( D _ { n } , \hat { \beta } _ { n } ^ { h } \right) \right\} , n = 1 , 2 , . . . , N
$$

其中， $s ( \bullet )$ 表示输出函数；上述结果以效用的形式输出可表示为

$$
\hat { y } \left( x _ { i } \right) = \mu ( S \left( x _ { i } \right) ) = \sum _ { n = 1 } ^ { N } \mu ( D _ { n } ) \hat { \beta } _ { n } ^ { h }
$$

其中 $\mu ( D _ { n } )$ 表示参考等级 $\textstyle D _ { n }$ 的效用，即其参考值； $\mu ( S \left( x _ { i } \right) )$ 为输出结果的效用。

在IHBRB 中, $s ( x _ { i } )$ 作为下一层子模型的输入信息进行推导，直到生成最终结果。

# 4基于IHBRB的可信度评估模型的自适应优化

对于社交账户的可信度评估问题，现有理论方法难以建立起精确的机理模型，但用户和专家在长期使用过程中能够积累一定的经验，通过网页爬虫等技术手段也可以获取一些数据样本。本文所提方法能够综合利用上述信息，即IHBRB模型的初始参数可由领域专家结合经验给定，后通过优化算法和数据样本对初始参数进行调整，以弥补专家知识局限性造成的模型误差[7]。

现有关于BRB模型优化的研究主要分为两类[12,13]：一类是在一定约束下调整待优化参数，使模型输出与实际系统输出之间的误差最小；另一类是在优化目标中引入结构参数，在提高模型建模精度的同时降低模型的复杂度。然而，这两类方法未在优化时考虑转换函数特性对建模性能的影响。鉴于此，在现有优化目标函数中引入转换函数的自适应系数作为待优化参数，新的优化目标函数及其约束条件可构建如下：

$$
\begin{array} { r l } & { \operatorname* { m i n } { \varphi ( \theta , \beta , \delta , s ) } } \\ & { \theta = ( \theta _ { 1 } ^ { 1 } , \dots , \theta _ { k } ^ { h } , \dots , \theta _ { k } ^ { H } ) , \beta = ( \beta _ { 1 } ^ { 1 } , \dots , \beta _ { n , k } ^ { h } , \dots , \beta _ { N , L } ^ { H } ) } \\ & { \delta = ( \delta _ { 1 } ^ { 1 } , \dots , \delta _ { i } ^ { h } , \dots , \delta _ { M } ^ { H } ) , s = ( s _ { 1 } , \dots , s _ { i } , \dots , s _ { M } ) } \\ & { s . t . } \\ & { 0 \leq \theta _ { k } ^ { k } \leq 1 , k = 1 , 2 , \dots L \cdot h = 1 , 2 , \dots , H } \\ & { 0 \leq \delta _ { i } ^ { h } \leq 1 , i = 1 , 2 , \dots M } \\ & { 0 \leq \beta _ { n , k } ^ { h } \leq 1 , \ n = 1 , 2 , \dots , N , \sum _ { n = 1 } ^ { N } \beta _ { n , k } ^ { h } = 1 } \\ & { 0 < s _ { i } , i = 1 , 2 , \dots M } \end{array}
$$

其中， $\theta , \beta , \delta$ 和 $s$ 分别为IHBRB中所有规则权重、置信度、属性权重和转换函数自适应系数构成的参数向量； $H$ 为IHBRB中子模型的个数； $\varphi ( \bullet )$ 为损失函数，用以描述模型输出与实际系统输出的区别。在本文中，损失函数用均方误差来计算，其具体描述如下

$$
\varphi ( \theta , \beta , \delta , s ) = \frac { 1 } { T } \sum _ { t = 1 } ^ { T } ( y _ { i } - \hat { y } _ { i } ) ^ { 2 }
$$

其中， $T$ 为输出的数量； $y _ { i }$ 和 $\hat { y } _ { i }$ 分别表示实际输出和模型输出。

现有研究已证明BRB模型是由多个复合函数组成的非线性非凸模型，这为其参数优化带来了挑战[14]。为了提高建模精度，许多优化算法被应用于BRB的优化，例如差分进化算法(DifferentialEvolution，DE)、粒子群优化算法(ParticleSwarmOptimization，PSO)和带有投影算子的协方差矩阵自适应进化 策略(Covariance Matrix Adaption Evolution Strategywith Projection,P-CMA-ES)[5\~18]。与DE 算法和PSO 算法相比，P-CMA-ES算法能够以专家确定的初始解为中心，以多维正态分布形式进行新解的生成，这有利于在模型优化过程中充分结合专家的初始判断[15]。同时，P-CMA-ES算法在高维非线性优化方面表现优越，能够在寻优过程中快速收敛至全局最优点[15]。P-CMA-ES的基本流程如图5所示。

D初始化操作给定初始参数 $\mathbf { K } ^ { 0 } , C ^ { 0 } , \rho , \varsigma , \varphi ^ { 0 } , \upsilon$ 分别表示初始参数向量、初始协方差矩阵、初始步幅、种群大小、后！代种群大小。 ${ \boldsymbol { \varphi } } ^ { 0 } = \mathbf { K } ^ { 0 }$ 表示初始均值。②采样操作$\mathbf { K } _ { i } ^ { g + 1 } \sim \boldsymbol { \varphi } ^ { g } + \rho ^ { g } \mathbf { N } ( 0 , C ^ { 0 } ) , i = 1 , 2 , . . . , \lambda$ 其中，K表示在第 $( g { + } 1 )$ 代中的第i个方案。N(-)是正态分布。③投影操作  
IK𝑠+(1+n×(j−1):n× j)=K𝑓+1(1+nx(j-1):n× j)-4×(Φ×4)-¹xK\*(1+nx(j-1):n×j)×4!其中，,=[11参数矩阵。n=1..2是在K中量的个数。④更新操作$\varphi ^ { g + 1 } = \sum _ { i = 1 } ^ { \upsilon } h _ { i : \lambda } ^ { g + 1 }$ （20  
其中， $h _ { i }$ 是权重系数。 ${ \bf K } _ { i : \lambda } ^ { g + 1 }$ 表示从第(g+1)代中选取的方案。U表示！  
最优方案。  
C\*+=(1-c-c）C&+cp（p1）+c∑h(K-φ²） (K𝑖-𝜑)Od p&  
其中，和C是学习速度。_P表示进化路径。  
③重复进行以上的步骤，直到获得最优的模型参数。

# 5 案例研究

# 5.1案例背景

新浪微博是国内典型的热门社交媒体，是谣言等危害信息发布的重要场所。在其长期的运营中，积累了大量的账户资料。本文以新浪微博中的社交账户作为研究对象，通过开放数据接口和通用爬虫技术对账户注册年限10年内的账户资料进行了搜集，获取了100个账户的基本信息。通过人工分析这些账户的交际行为、内容发布等诸多基本特征，将其分为了“完全不可信”、“部分可信”、“基本可信”三类。

社交账户可信度评估指标对应的数据如图6所示。可以看出，账户的多种属性与其年限均有一定关联性。但由于用户存在使用习惯、受教育水平以及生活地域等多方面差异，这些数据难以直观反映账户可信度，因此必须采用一定的建模方法实现可信度评估。本文将采用所提基于IHBRB的社交账户可信度评估方法开展实例研究。

![](images/2f0bfcb0f8585e2ef8a719280bf9bb35673fc6795e47bedaa6e8cb5f9bcc293e.jpg)  
图5P-CMA-ES 算法的主要流程Fig.5Main flowofP-CMA-ESalgorithm  
图6账户可信度评估指标数据  
Fig.6Data of account credibility evaluation indicators

# 5.2案例分析与模型构建

使用IHBRB 进行账户可信度评估时，首先需要选择评估指标及可信度的参考等级。

对于账户属性可信度、交际属性可信度和内容属性可信度，其是社交账户可信度的局部估计，因此其参考等级可与社交账户可信度设置的一致，即"完全不可信(U)”“部分可信(P)"和“基本可信(F)"。对应的参考值可分别取0,0.5和1。

对于评估指标，其参考等级和参考值可设置如表1所示，解读如下：

社交账户其使用年限可分为"短(S)”、“中(M)”“长(L)"三个参考等级。根据经验，可设置年限“短”的参考值为0年。同时，年限“中”和“长”的参考值分别设置为4年和10年。

对于账户的认证情况，认证的数量越多其可信度越高。账户认证数的参考等级可设置为“无(NO)”、“少(S)”和“多(M)"，其参考值可分别设置为0项、2项和5项。

账户粉丝数的参考等级可设置为四个，即“无(NO)”、“少 (S)”、“一般(N)”和“多(M)”。四个参考等级分别设置参考值 为0个、3000个、5000个和15000个。

被转赞评数的参考等级设置为"无(NO)”“少(S)"和“多 (M)"，参考值设置为0个、50000个和150000个。

信息原创率和存疑率的参考等级可设置为“低(L)”、“中(M)”和“高(H)"，相应参考值设置为 $0 \%$ 、 $50 \%$ 和 $100 \%$ 。

表1指标参考等级和参考值  
Tab.1The referential levels and referential values   

<html><body><table><tr><td colspan="2">C1</td><td colspan="2">C</td><td colspan="2">C3</td><td colspan="2">C4</td><td colspan="2">C5</td><td colspan="2">C6</td></tr><tr><td>等级</td><td>值</td><td>等级</td><td>值</td><td>等级</td><td>值</td><td>等级</td><td>值</td><td>等级</td><td>值</td><td>等级</td><td>值</td></tr><tr><td>S</td><td>0</td><td>NO</td><td>0</td><td>NO</td><td>0</td><td>NO</td><td>0</td><td>L</td><td>0</td><td>L</td><td>0</td></tr><tr><td>M</td><td>4</td><td>S</td><td>2</td><td>S</td><td>3000</td><td>S</td><td>50000</td><td>M</td><td>0.5</td><td>M</td><td>0.5</td></tr><tr><td>L</td><td>10</td><td>M</td><td>5</td><td>N</td><td>5000</td><td>M</td><td>150000</td><td>H</td><td>1</td><td>H</td><td>1</td></tr><tr><td>一</td><td>一</td><td>一</td><td>一</td><td>M</td><td>15000</td><td>一</td><td>一</td><td>一</td><td>一</td><td>一</td><td>一</td></tr></table></body></html>

结合上述指标参考等级和参考值，通过专家经验及数据的趋势性分析，可以针对各子模型的规则库给出初始参数，如表2所示。IHBRB中4个子模型输入的初始权重均设置为1，规则的初始权重均设置为1。此外，模型中6个输入指标转换函数的初始自适应系数均设置为1，即$s _ { 1 } = s _ { 2 } = s _ { 3 } = s _ { 4 } = s _ { 5 } = s _ { 6 } = 1$ 。在此情况下，该转换函数为线性函数。

# 5.3模型优化与结果分析

由于专家认知的局限性，需要结合有限的数据样本对IHBRB 模型的初始参数进行调整。优化目标函数依据式(12)和式(13)确定。

在所获取的数据集中，随机取 $50 \%$ 的数据作为训练集，以整个数据集作为测试集。对于P-CMA-ES优化算法，初始参数向量 $K ^ { \circ }$ 即为初始模型参数、初始协方差矩阵 $C ^ { 0 }$ 为单位阵，初始步幅设置为 $\rho ^ { \mathrm { 0 } } = 0 . 5$ ，优化迭代次数设置为200代。

优化后的IHBRB 模型的规则权重和置信度如表3所示，其中优化后的各子模型的指标权重分别为：0.75、1、0.55、1、0.3、1、0.93、0.91和1。优化后转换函数的自适应系数分别为：1.61、0.35、0.59、1.72、2.18和1.83。采用初始IHBRB和优化后的IHBRB模型对测试集中账户进行可信度评估，评估结果如图7所示，可见优化后的模型能够更好实现对社交账户可信度的评估。初始模型和优化后模型的输出结果均方误差分别为0.0562和0.0028，优化后模型的精度提高了 $9 5 \%$ 。

# 5.4对比研究

为了进一步验证所提方法的有效性，在本节的对比研究中，采用无自适应系数转换函数的IHBRB 模型(记为IHBRB-1)、神经网络模型(记为BPNN)、模糊推理模型(记为FRM)和回归支持向量机模型(记为SVR)对前述数据集中的账户进行可信度评估。BPNN、FRM、SVR为三种常用的评估模型。其中，BPNN模型具有精度高、易操作等优点；FRM模型能够有效描述和处理模糊不确定性，且能够较好融合专家判断；SVR模型不依赖于优化数据样本的数量，具有较高的建模精度。对比实验中，随机选取 $50 \%$ 的数据作为训练集，以整个数据集为测试集，进行10轮重复实验，以结果的平均值为最终结果。

Tab.2 The initial IHBRB   

<html><body><table><tr><td>BRB-1</td><td>C1</td><td>C</td><td>规则结论</td><td></td><td>BRB-4 BiBB</td><td></td><td>规则结论</td></tr><tr><td>1</td><td>S</td><td>NO</td><td>{0.5,0.5,0}</td><td>1</td><td></td><td>UUU</td><td>{0.6, 0.3, 0.1}</td></tr><tr><td>2</td><td>S</td><td>S</td><td>{0.3, 0.6,0.1}</td><td>2</td><td></td><td>UUP</td><td>{0.4, 0.6,0}</td></tr><tr><td>3</td><td>S</td><td>M</td><td>{0, 0.8, 0.2}</td><td>3</td><td></td><td>UUF</td><td>{0.1, 0.2, 0.7}</td></tr><tr><td>4</td><td>M</td><td>NO</td><td>{0.4, 0.5, 0.1}</td><td>4</td><td>UP</td><td>U</td><td>{0.5,0.3,0.2}</td></tr><tr><td>5</td><td>M</td><td>S</td><td>{0.1, 0.1, 0.8}</td><td>5</td><td></td><td>UPP</td><td>{0, 0.6, 0.4}</td></tr><tr><td>6</td><td>M</td><td>M</td><td>{0.1,0.2, 0.7}</td><td>6</td><td></td><td>UPF</td><td>{0.1, 0.4, 0.5}</td></tr><tr><td>7</td><td>L</td><td>NO</td><td>{0, 0.2, 0.8}</td><td>7</td><td></td><td>UFU</td><td>{0.2, 0.2, 0.6}</td></tr><tr><td>8</td><td>L</td><td>S</td><td>{0.3, 0.6,0.1}</td><td>8</td><td></td><td>UFP</td><td>{0.2,0.2,0.6}</td></tr><tr><td>9</td><td>L</td><td>M</td><td>{0.1, 0.3, 0.6}</td><td>9</td><td></td><td>UFF</td><td>{0, 0.7, 0.3}</td></tr><tr><td>BRB-2</td><td>C</td><td>C4</td><td>规则结论</td><td>10</td><td></td><td>PUU</td><td>{0, 0.6, 0.4}</td></tr><tr><td>1</td><td></td><td>NO NO</td><td>{0.1, 0.7,0.2}</td><td>11</td><td></td><td>PUP</td><td>{0.6,0.3,0.1}</td></tr><tr><td>2</td><td>NO</td><td>S</td><td>{0.2, 0.7, 0.1}</td><td>12</td><td></td><td>PUF</td><td>{0.1,0.7,0.2}</td></tr><tr><td>3</td><td>NO</td><td>M</td><td>{0.2, 0.5, 0.3}</td><td>13</td><td></td><td>PPU</td><td>{1,0,0}</td></tr><tr><td>4</td><td>S</td><td>NO</td><td>{0, 0.9, 0.1}</td><td>14</td><td></td><td>PPP</td><td>{0.9, 0.1, 0}</td></tr><tr><td>5</td><td>S</td><td>S</td><td>{0,0.8,0.2}</td><td>15</td><td></td><td>PPF</td><td>{0.3, 0.6, 0.1}</td></tr><tr><td>6</td><td>S</td><td>M</td><td>{0.1, 0.8, 0.1}</td><td>16</td><td></td><td>PFU</td><td>{0.1, 0.4, 0.5}</td></tr><tr><td>7</td><td>N</td><td>NO</td><td>{0.4,0.5, 0.1}</td><td>17</td><td></td><td>PFP</td><td>{0,0,1}</td></tr><tr><td>8</td><td>N</td><td>S</td><td>{0.3,0.7,0}</td><td>18</td><td></td><td>PFF</td><td>{0.1, 0.3, 0.6}</td></tr><tr><td>9</td><td>N</td><td>M</td><td>{0, 0.2, 0.8}</td><td>19</td><td></td><td>FUU</td><td>{0.1, 0.6, 0.3}</td></tr><tr><td>10</td><td>M</td><td>NO</td><td>{0.3,0.5, 0.2}</td><td>20</td><td>FUP</td><td></td><td>{0.6,0.3, 0.1}</td></tr><tr><td>11</td><td>M</td><td>S</td><td>{0.1, 0.6,0.3}</td><td>21</td><td>FUF</td><td></td><td>{0.3,0.5, 0.2}</td></tr><tr><td>12</td><td>M</td><td>M</td><td>{0, 0.1, 0.9}</td><td>22</td><td></td><td>FPU</td><td>{0.1,0.1, 0.8}</td></tr><tr><td>BRB-3</td><td>C5</td><td>C6</td><td>规则结论</td><td>23</td><td>FP</td><td>P</td><td>{0.2, 0.5, 0.3}</td></tr><tr><td>1</td><td>L</td><td>L</td><td>{0, 0.2, 0.8}</td><td>24</td><td>FP</td><td>F</td><td>{0.3,0.6,0.1}</td></tr><tr><td>2</td><td>L</td><td>M</td><td>{0.8, 0.1, 0.1}</td><td>25</td><td></td><td>FFU</td><td>{0.6, 0.3, 0.1}</td></tr><tr><td>3</td><td>L</td><td>H</td><td>{0.4, 0.5, 0.1}</td><td>26</td><td></td><td>FFP</td><td>{0.3,0.6, 0.1}</td></tr><tr><td>4</td><td>M</td><td>L</td><td>{0, 0.4, 0.6}</td><td>27</td><td></td><td>FFF</td><td>{0.8, 0.1, 0.1}</td></tr><tr><td>5</td><td>M</td><td>M</td><td>{0.2,0.8,0}</td><td></td><td></td><td></td><td></td></tr><tr><td>6</td><td>M</td><td>H</td><td>{0.4, 0.6,0}</td><td></td><td></td><td></td><td></td></tr><tr><td>7</td><td>H</td><td>L</td><td>{0.1, 0.6, 0.3}</td><td></td><td></td><td></td><td></td></tr><tr><td>8</td><td>H</td><td>M</td><td>{0.5,0.3,0.2}</td><td></td><td></td><td></td><td></td></tr><tr><td>9</td><td>H</td><td>H</td><td>{0.2,0.5,0.3}</td><td></td><td></td><td></td><td></td></tr></table></body></html>

初始IHBRB输出 基本可信一优化后的IHBRB输出0.8 样本标签  
度  
信0.6 可 部分可信 MAM AMY  
户  
0. wwwW0.2完全不可信00 10 20 30 40 50 60 70 80 90 100账户编号

实验结果如图8所示，可以看出这些模型经过优化均能够从一定程度上反映账户的可信度。对比IHBRB与IHBRB-1结果可以看出，转换函数自适应系数的引入对评估精度的提高有较大作用。FRM对“完全不可信”的评估精度高于对“部分可信”和“基本可信”的评估精度。

对于上图中的某一账户样本，其账户年限为10年，认证数为5项，粉丝数为37422人，被转赞评数为219054人次，信息原创率为 $9 7 \%$ 以及信息存疑率为 $3 \%$ ，通过专家判断其为基本可信账户。采用上述5种模型评估该账户：IHBRB输出的置信分布为 $\{ 0 . 0 0 , 0 . 1 6 , 0 . 8 4 \}$ ，对应可信度效用为0.92；IHBRB-1输出的置信分布为{0.05,0.21,0.74}，对应可信度效用为0.84；BPNN输出的可信度为0.81；FRM输出中对各可信度等级的隶属度分别为0.08,0.33和0.59，对应的可信度效用为0.755；SVR输出的可信度值为 $0 . 7 9$ 。可见，这些模型均认为该账户属于“基本可信”，但是IHBRB模型不仅能够输出相对于各等级的置信度，其量化评估的可信度更接近真实值。

![](images/297937c7eb64c62a2ce7faedb47ad362a90163b3e3bd0e44e8d3716f5894dfd6.jpg)  
图7账户可信度评估结果  
Fig.7The results of account credibility evaluation   
图8对比实验结果图

表2初始IHBRB 模型  
Fig.8The result of comparative study 表3优化的IHBRB 模型 Tab.3The optimized IHBRB   

<html><body><table><tr><td>BRB-1 权重</td><td></td><td>规则结论</td><td>BRB-4 权重</td><td></td><td>规则结论</td></tr><tr><td>1</td><td>0.60</td><td>{0.85,0.09,0.06}</td><td>1</td><td>0.73</td><td>{0.23,0.7,0.07}</td></tr><tr><td>2</td><td>0.31</td><td>{0.36,0.44,0.2}</td><td>2</td><td>0.55</td><td>{0.31,0.2,0.49}</td></tr><tr><td>3</td><td>0.09</td><td>{0.49,0.15,0.36}</td><td>3</td><td>0.95</td><td>{0.34,0.27,0.39}</td></tr><tr><td>4</td><td>0.51</td><td>{0.73,0.14, 0.13}</td><td>4</td><td>0.24</td><td>{0.47,0.23,0.3}</td></tr><tr><td>5</td><td>0.21</td><td>{0.45,0.06,0.49}</td><td>5</td><td>0.75</td><td>{1,0,0}</td></tr><tr><td>6</td><td>0.28</td><td>{0.52, 0.14, 0.34}</td><td>6</td><td>0.06</td><td>{0.36,0.29,0.35}</td></tr><tr><td>7</td><td>0.30</td><td>{0.08,0.18, 0.74}</td><td>7</td><td>0.72</td><td>{0.32,0.58,0.1}</td></tr><tr><td>8</td><td>0.24</td><td>{0.54,0.16,0.3}</td><td>8</td><td>0.24</td><td>{0.56,0.27, 0.17}</td></tr><tr><td>9</td><td>0.46</td><td>{0.03,0.13,0.84}</td><td>9</td><td>0.34</td><td>{0.33,0.31,0.37}</td></tr><tr><td>BRB-2</td><td>权重</td><td>规则结论</td><td>10</td><td>0.48</td><td>{0.14, 0.41, 0.45}</td></tr><tr><td>1</td><td>0.22</td><td>{0.13,0.75,0.12}</td><td>11</td><td>0.21</td><td>{0.2,0.53,0.27}</td></tr><tr><td>2</td><td>0.09</td><td>{0.33,0.1,0.57}</td><td>12</td><td>0.50</td><td>{0.38,0.45,0.17}</td></tr><tr><td>3</td><td>0.30</td><td>{0.25,0.49,0.26}</td><td>13</td><td>0.48</td><td>{0.38,0.39,0.23}</td></tr><tr><td>4</td><td>0.61</td><td>{0.11,0.76,0.13}</td><td>14</td><td>0.07</td><td>{0.31,0.38,0.31}</td></tr><tr><td>5</td><td>0.65</td><td>{0.16,0.13,0.71}</td><td>15</td><td>0.58</td><td>{0.32, 0.51, 0.17}</td></tr><tr><td>6</td><td>0.21</td><td>{0.17,0.31, 0.52}</td><td>16</td><td>0.36</td><td>{0.37,0.29,0.34}</td></tr><tr><td>7</td><td>0.14</td><td>{0.26, 0.33, 0.41}</td><td>17</td><td>0.42</td><td>{0.32,0.35,0.33}</td></tr><tr><td>8</td><td>0.21</td><td>{0.11,0.61,0.28}</td><td>18</td><td>0.75</td><td>{0.4,0.27,0.33}</td></tr><tr><td>9</td><td>0.30</td><td>{0.27,0.57, 0.16}</td><td>19</td><td>0.58</td><td>{0.46,0.33,0.21}</td></tr><tr><td>10</td><td>0.10</td><td>{0.26,0.16,0.58}</td><td>20</td><td>0.53</td><td>{0.41,0.21, 0.38}</td></tr><tr><td>11</td><td>0.74</td><td>{0,0,1}</td><td>21</td><td>0.71</td><td>{0.48,0.35,0.17}</td></tr><tr><td>12</td><td>0.89</td><td>{0.31, 0.51, 0.18}</td><td>22</td><td>0.05</td><td>{0.25,0.32,0.43}</td></tr><tr><td>BRB-3</td><td>权重</td><td>规则结论</td><td>23</td><td>0.83</td><td>{0.03,0,0.97}</td></tr><tr><td>1</td><td>1.00</td><td>{0.12, 0.48, 0.4}</td><td>24</td><td>0.40</td><td>{0.23,0.39,0.38}</td></tr><tr><td>2</td><td>0.74</td><td>{0.39,0.45, 0.16}</td><td>25</td><td>0.65</td><td>{0.62,0.06,0.32}</td></tr><tr><td>3</td><td>0.64</td><td>{0.26,0.33, 0.41}</td><td>26</td><td>0.88</td><td>{0.49,0.22,0.29}</td></tr><tr><td>4</td><td>0.32</td><td>{0.29,0.52,0.19}</td><td>27</td><td>0.31</td><td>{0.54,0.11,0.35}</td></tr><tr><td>5</td><td>0.08</td><td>{0.21,0.1,0.69}</td><td></td><td></td><td></td></tr><tr><td>6</td><td>0.35</td><td>{0.01,0.46, 0.53}</td><td></td><td></td><td></td></tr><tr><td>7</td><td>0.07</td><td>{0.35,0.39,0.26}</td><td></td><td></td><td></td></tr><tr><td>8</td><td>0.39</td><td>{0.4, 0.07, 0.53}</td><td></td><td></td><td></td></tr><tr><td>9</td><td>0.89</td><td>{0.48, 0.48, 0.04}</td><td></td><td></td><td></td></tr></table></body></html>

为了研究训练样本的减少对实验结果的影响，分别随机选择 $40 \%$ 、 $30 \%$ 和 $20 \%$ 的数据样本作为训练集。实验结果如表4所示，可以看出，当训练集的数量下降，5种模型输出的均方误差都增大。但是对于IHBRB、IHBRB-1和FRM这类能够通过专家知识确定初始参数的模型，其在优化数据样本较少时，仍能够达到较好评估性能。

Tab.4The mean square error of the comparative model   

<html><body><table><tr><td>数据样本</td><td>IHBRB</td><td>IHBRB-1</td><td>BPNN</td><td>FRM</td><td>SVR</td></tr><tr><td>50%</td><td>0.0028</td><td>0.0089</td><td>0.0074</td><td>0.0121</td><td>0.0087</td></tr><tr><td>40%</td><td>0.0044</td><td>0.0097</td><td>0.0111</td><td>0.0152</td><td>0.0219</td></tr><tr><td>30%</td><td>0.0102</td><td>0.0174</td><td>0.0453</td><td>0.0341</td><td>0.0476</td></tr><tr><td>20%</td><td>0.0236</td><td>0.0303</td><td>0.0951</td><td>0.0613</td><td>0.0899</td></tr></table></body></html>

为了进一步说明P-CMA-ES算法的有效性，分别采用PSO 算法和DE算法对初始IHBRB 模型进行优化。数据集和重复实验次数均与前述一致，优化后模型输出的均方误差如表5所示。可见，当训练集比例为 $50 \%$ 时，三种方法优化算法的性能相近。当训练集比例降低为 $20 \%$ 时，通过P-CMA-ES算法优化的IHBRB模型具有更好的建模精度。

表5不同优化算法下IHBRB 输出的均方误差

表4对比模型的均方误差  
Tab.5The mean square error of IHBRB with different optimization algorithms   

<html><body><table><tr><td>数据样本</td><td>P-CMA-ES</td><td>PSO</td><td>DE</td></tr><tr><td>50%</td><td>0.0028</td><td>0.0030</td><td>0.0031</td></tr><tr><td>40%</td><td>0.0044</td><td>0.0077</td><td>0.0089</td></tr><tr><td>30%</td><td>0.0102</td><td>0.0147</td><td>0.0166</td></tr><tr><td>20%</td><td>0.0236</td><td>0.0281</td><td>0.0273</td></tr></table></body></html>

# 6 结束语

本文针对社交账户可信度评估面临的指标多维且特性各异、数据信息不确定性多样等问题，从账户属性、交际属性和内容属性三个角度构建了账户可信度评估指标体系，提出了一种基于改进分层BRB的可信度评估方法。该方法通过分层结构和置信框架来描述指标间的关系和信息不确定性，同时引入了带有自适应系数的信息转换函数以更好处理指标间的特性差异。实验证明，该方法能够准确评估社交账户的可信度。但本文仍存在一些不足需要进一步研究，如可与深度学习等技术融合，挖掘更多信息以构建规则库，进一步提高评估过程的可解释性及输出结果的精度。

# 参考文献：

[1]胡学韬，陈秀真．基于信任度评估的社交网络虚假账户检测[J]．信 息安全与通信保密,2014,(5):90-94.(Hu Xuetao,Chen Xiuzhen.Fake account detection in online social network based on trust evaluation [J] Information Security and Communications Privacy,2014,(5): 90-94.)   
[2]路金泉．面向社交网络信息管控的信息可信度评估方法研究[D]. 郑州：解放军信息工程大学，2017.(Lu Jinquan.Researchon information credibility evaluationmethod for social network information control [D]. Zhengzhou: PLA Information Engineering University,2017.)   
[3]王坤．在线社交网络异常账户检测算法研究[D]．西安：西安电子 科技大学，2020.(Wang Kun.Research on online social network abnormal account detection algorithm [D].Xi’an: Xidian University, 2020)   
[4]刘亚尚．在线社交网络异常账户检测技术研究[D].南京师范大学, 2016.(Liu Yashang.Research on anomaly detection methods for online social networks [D].Nanjing:Nanjing Noraml University,2016.)   
[5]王峥，叶维，邱秀连．基于特征加权贝叶斯神经网络的微博异常账 号检测[J].计算机与数字工程，2018,46(11):2323-2328.（Wang Zheng,Ye Wei,Qiu Xiulian.Weibo abnormal account detect based on weighted bayesian neural network[J]. Computer and Digital Engineering, 2018,46 (11): 2323-2328)   
[6] Yang Jianbo,Liu Jun,Wang Jin,et al.Belief rule-base inference methodology using the evidential reasoning approach-RIMER [J]. IEEE Trans on Systems Man and Cybernetics: Systems,2006,36 (2): 266-285.   
[7] 周志杰，杨剑波，胡昌华，等．置信规则库专家系统与复杂系统建模 [M].北京：科学出版社，2011.(Zhou Zhijie,Yang Jianbo,Hu Changhua,et al.Belief rule base expert systems and complex system modeling [M]. Beijing: Science Press,2011.)   
[8] 周志杰，曹友，胡昌华，等．基于规则的建模方法的可解释性及其发 展[J].自动化学报,2021,47(06):1201-1216.(Zhou Zhijie,Cao You, Hu Changhua,et al. The interpretability ofrule-based modeling approach and its development.Acta Automatica Sinica,2021,47(06): 1201-1216.)   
[9]王越，张剑金，刘芳芳．一种多特征微博僵尸粉检测方法与实现[J]. 中国科技论文,2014,9(1):81-86.(Wang Yue,Zhang Jianjin,Liu Fangfang. Detection of micro-blog Zombie fans based on multi-features [J]. China Sciencepaper, 2014,9(1): 81-86.)   
[10]王培人，毛剑，马寒军等．基于用户信息的社交网络信任评估方法 [J].计算机应用研究,2018,35(2):521-526.(Wang Peiren,Mao Jian, Ma Hanjun, et al. User information based trust evaluation mechanism for social network [J].Application Research of Computers,2018,35 (2): 521-526.)   
[11]王路帮，李守伟．社交网络中基于网络结构支撑模型的谣言传播研 究[J].计算机应用研究,2019,36(10):3094-3097.(WangLubang,Li Shouwei.Rumor spreading based on network structural supportiveness model in social network [J].Application Research of Computers,2019, 36 (10): 3094-3097.)   
[12] Yang Jianbo,Liu Jun,Xu Donglin,et al.Optimization models for training belief-rule-based systems [J]. IEEE Trans on Systems Man and Cybernetics: Systems,2007,37 (4): 569-585.   
[13] Zhou Zhijie,Hu Guanyu, Hu Changhua,et al.A survey of belief rulebase expert system [J].IEEE Trans on Systems Man and Cybernetics: Systems,2021,51(8): 4944-4958.   
[14]胡蓉，易照云，钱斌．基于置信规则库的油浸式变压器故障诊断[J]. 北京工业大学学报,2021,47 (9):1000-1010.(Hu Rong,Yi Zhaoyun, Qian Bin.Fault Diagnosis of Oil-immersed Transformer Based on Belief Rule Base[J].JournalofBeijing UniversityofTechnology,2021,47 (9): 1000-1010.)   
[15]胡冠宇．基于置信规则库的网络安全态势感知技术研究[D].哈尔 滨：哈尔滨理工大学,2016.(Hu Guanyu. Study on network security situation awareness based on belief rule base [D].Harbin: Harbin University of Technology,2016.)   
[16] 刘栅杉，朱海龙，韩晓霞，等．基于主成分回归和分层置信规则库的 企业风险评估模型[J].计算机科学，2021,48(Z2):570-575.(Liu Shanshan,Zhu Hailong,Han Xiaoxia,et al.Enterprise risk assessment model based on principal component regression and hierarchical belief rule base [J]. Computer Science,2021,48 (Z2): 570-575.)   
[17] Chang Leilei, Zhou Zhijie,Liao Huchang,Generic disjunctive belief rule base modeling,inferencing,and optimization [J]. IEEE Trans on Fuzzy Systems,2019,27 (9): 1866-1880.   
[18] Qian Bin, Wang Qianqian, Hu Rong,et al.An effctive soft computing technology based on belief-rule-base and particle swarm optimization for tipping paper permeability measurement [J].Journal of Ambient Intelligence and Humanized Computing,2019,10 (3): 841-850.